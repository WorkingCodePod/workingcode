---
title: "087: Note To Self v0.2.0"
description: "We get to pull up the floor boards and once again peer into the dark recesses of Ben's brain."
date: 2022-08-10
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/087-note-to-self-v0-2-0/id1544142288?i=1000575635824"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

On today's episode, we get to pull up the floor boards and once again peer into the dark recesses of Ben's brain: all the random and, frankly, sometimes incoherent chit-cat that Ben has with himself. Listen to him call B.S. on flaky tests; shake his first at overly-specific CSS selectors; preen about GulpJS build scripts; pontificate on the ROI (return on investment) of personal growth; and, theorize that building - not buying - can sometimes be the smarter (and less bureaucratic) move to make.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/087-note-to-self-v0-2-0.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** note to self. I wrote my first gulp JS plugin, 2015 called it wants its build script back.

[00:00:09] **Ben:** Yeah.

## [00:00:30] Intro

[00:00:30] **Adam:** Okay. Here we go. It is show number 87 and on today's show, we're going to do another edition of notes to self. I thought maybe we'd call it version zero two zero. Some our,our podcast themes here. but as usual, we'll start with our triumphs and fails. And Tim, we're gonna come to you first.

[00:00:47] **Adam:** What's going on, man.

## [00:00:48] Tim's No-umph

[00:00:48] **Tim:** So I'm gonna brand this a new term. I have a Noum.

[00:00:53] **Carol:** Mmm.

[00:00:53] **Adam:** Okay.

[00:00:54] **Tim:** a triumph. It's not a failure. It's just, there's no, there's not a whole lot to report.

[00:00:59] **Tim:** you know, things. Yeah.

[00:01:00] **Tim:** I mean, I guess it's good. Things are pretty steady state, business is growing, we're building new products, but it's like, yeah, I'm not feeling bad about that cuz you know, My, my role is slowly shifting.

[00:01:13] **Tim:** You guys might have to kick me off the podcast at some point where it's shifting from, an individual contributor to more of a product type, general manager type role in the company. so, I'm kind of slowly weaning myself off of certain things. I keep, some things to myself just for my own sanity, but which, which means I, I feel like my days are a lot more planned.

[00:01:33] **Tim:** I used to, I used to like to come in particularly like way back when I was like running the, the support department

[00:01:39] **Tim:** and it was like, didn't really have a plan for the day. It was like, we walk in the door and just ride the dragons tail

[00:01:44] **Tim:** till you go home. Right. It was very reactive, but now it's more, a lot more planning.

[00:01:48] **Tim:** Alright, what's our roadmap coming up. Okay. What are we gonna build? Let's talk to some customer, let's validate this stuff. and it's all fun stuff. I enjoy it. But it's like, I. Get that same rush of, I found this problem that's was endemic to the code. That's been there for years and no one could fix it.

[00:02:02] **Tim:** And I came in and single handedly fixed it. It's not that dramatic anymore. So,

[00:02:07] **Carol:** Yeah.

[00:02:07] **Tim:** yes, so it's a no, nothing bad, nothing good. Just steady state.

[00:02:11] **Carol:** So I have found with all this project planning that I've been doing and kind of road mapping stuff that. By the time I get the, like the planning part of it done, people need work. So I have to hand it off to let someone else start coding on it because I need to pick up like the next project to start planning.

[00:02:28] **Carol:** And I'm like, oh, I need to have a lull in between so that I can code some of it myself, because

[00:02:33] **Carol:** I did all the, I did all the like grunt work to get this off the ground. Now let me put my brain to use, like on the code and, oh man, I have to hand my baby over.

[00:02:43] **Adam:** it sounds like a very UN cathartic situation. Like it would be very frustrating to never see those things come to fruition.

[00:02:50] **Tim:** Yeah. Yeah. It's like that pimple that never pops, you know, you just left feel you're felt left, feeling scarred and hurt, but you don't get that satisfaction of that pop,

[00:03:00] **Carol:** I don't have that because I get super excited when my team does work it, and it gets wrapped up, you know, that I did the kinda upfront legwork to take some of the roadblocks out of the way for them so they could get done what they need to get done. So, I mean, I do get the, like the joy from the product finally releasing.

[00:03:16] **Carol:** I just wanna write more code. Okay. That's it just more,

[00:03:19] **Tim:** Well, I, what bugs me is like, so we're in our daily standup, right? So, we've said, here's what we're building. Here's what we know what we're working on. they'll have questions maybe for sort of the vision of right. how's the business businesses gonna use this, that sort of questions.

[00:03:31] **Tim:** But it's like, as far as the implementation details and you know how they do it, I give them almost no input on that unless they just ask a personal preference. Right.

[00:03:39] **Tim:** So it's like, yeah. And so that's kind of frustrating. It's like, I know you're really doing some really cool stuff here

[00:03:45] **Carol:** Mm-hmm

[00:03:45] **Tim:** I have zero input on it unless you kind of get stuck a little bit.

[00:03:49] **Carol:** yep.

[00:03:50] **Tim:** That's a little frustrating, but no, what's great is like whenever, something you had in your head and then, they do the initial demo of it and you take it, you start playing around with it and you're like, Hey, this is pretty close to what I wanted. And they're

[00:04:01] **Tim:** like, okay, let's tweak this here.

[00:04:02] **Tim:** Let's tweak that there. And then you've got new feature of product that you've been working on. So that's pretty

[00:04:07] **Tim:** cool, but

[00:04:07] **Carol:** That is.

[00:04:08] **Tim:** just, it's just different. It's not bad. How about you Carol?

## [00:04:11] Carol's Failure

[00:04:11] **Carol:** I'm gonna go with, I'm gonna call this a failure. I feel like it's a failure just because it's on me. Right. But it's probably not, it's probably not really a failure. So yesterday I had a full blown panic attack, like sitting on the floor, crying, couldn't breathe, chest hurting called my

[00:04:29] **Carol:** husband. Like, I don't know what's going on.

[00:04:31] **Carol:** I feel like I'm dying. There's something wrong. My son walks in the door because he was coming over from the other house was gonna have lunch with me on his way to see his grandparents he's freaking out because he doesn't know what's going on. And it was just. It was a disaster and ended up going to the doctor and then put me on some meds to lower my blood pressure, even though I don't have high blood pressure, but apparently it's the first route you can take for panic attacks to just help with preventing them.

[00:04:56] **Carol:** And it's like a temporary solution to just kind of work through everything. So it was like, take that meds and go for a hike. that was my prescription. She's like, you need to get outta the house. So you're spending too much time. Like gooped up, like just get out, go for a hike. Enjoy being outside. Don't.

[00:05:11] **Carol:** And just stare off or don't sit and like watch TV because that's when it makes things worse. So get out and do stuff. So I've realized that I'm spending way too much time inside, just cuz I work at home. I cook at home, I eat at home. I work out at home. I play with the dog at home. So I am going to try really hard to go outta the house more and just go do stuff.

[00:05:30] **Carol:** So today I went and worked at Steve's office with him instead of staying at home by myself. So I was like, okay, I'm gonna go to your office, sit at your desk, work with you today and then come home. So I mean, it felt good

[00:05:39] **Carol:** to just kind of be out and in a new environment, doing stuff. So hopefully everything's resolved and I don't have another one cuz that was not fun.

[00:05:48] **Carol:** I haven't had one since I was like a teenager and I thought that would never have them again and yeah, it was bad. Bad,

[00:05:56] **Tim:** Man,

[00:05:56] **Tim:** I'm sorry. I had to go through that.

[00:05:58] **Carol:** Yeah.

[00:05:59] **Ben:** did something specific trigger it or it just came outta nowhere.

[00:06:02] **Carol:** No, oddly enough, nothing triggered it. There wasn't like a point in time that was like, oh, this is stressing me out. Or something's going on? I was on my couch, decided I was gonna work on the couch and was in the middle of a merge conflict and was texting Steve and I just fell apart. Just was done. stupid Coke conflicts. So I opened up my laptop this morning. I was like, oh yeah, I was in the middle of fixing this merge conflict when it all.

[00:06:32] **Tim:** I could see how it might feel like a failure, but I mean, obviously you did all the right things to, to address it. So, I mean, it sounds like a triumph to me. It sucks. You had to go through that, but you know, Took care of

[00:06:44] **Carol:** Thanks.

[00:06:44] **Tim:** daughter,

[00:06:45] **Tim:** she just finished up her first, not semester. She was doing dual enrollment in college and she was just taking an online psychology course.

[00:06:53] **Tim:** And she's like, I'm just amazed. How much of psychology in our textbooks was all about, getting some exercise going

[00:06:58] **Tim:** outside and having a healthy diet.

[00:07:00] **Carol:** Right.

[00:07:01] **Carol:** It changes

[00:07:02] **Tim:** They weren't as shoeing medicine at all, but they're like, unless you've tried. Those first, those three things first, and you really haven't tried them yet.

[00:07:08] **Tim:** So

[00:07:08] **Carol:** Yeah. and what we do now, it's so easy to never leave your house. Like I realized I had just signed up for Instacart again to start delivering groceries cuz I hate grocery shopping. So I was like, okay, fine. I'm gonna cancel Instacart. I'll go to Publix. Fine. like I'll get outta the house even if it's for Publix.

[00:07:28] **Ben:** I love supermarkets. I love going to the supermarket and just walking up and down the aisles. I find it very relaxing.

[00:07:34] **Carol:** all the people.

[00:07:35] **Tim:** I used to then inflation came and I was like,

[00:07:37] **Tim:** oh, I feel like my dad now a loaf of bread for three 50. Are you

[00:07:41] **Tim:** kidding me?

[00:07:42] **Carol:** yeah. $5 for gas to get there. Yeah.

[00:07:47] **Adam:** I used to, when I was a kid, my mom would send me up to the scratch and dent bread and milk store.

[00:07:51] **Carol:** Yeah,

[00:07:52] **Adam:** had

[00:07:53] **Adam:** we

[00:07:53] **Tim:** the day old.

[00:07:54] **Carol:** yeah.

[00:07:54] **Adam:** Yeah, we had a store that was like, it was pretty much just like milk, eggs, and bread. And it was all super cheap, but it was like, you need to eat it in the next day or two

[00:08:03] **Tim:** it's 48 hours away from becoming penicillin.

[00:08:06] **Adam:** Yeah.

[00:08:08] **Carol:** well, that's it for me. What about you, Adam? What you got?

## [00:08:11] Adam's Triumph

[00:08:11] **Adam:** Well, I gotta triumph. I feel a little bit bad after your story. Like I have to follow that and follow it with a triumph, but

[00:08:19] **Adam:** guess I'm just gonna go for it. So, sorry.

[00:08:21] **Carol:** Be a winner.

[00:08:22] **Adam:** yeah. Right. so I just got back from a vacation. I went down to Texas to visit my brother. He lives in Austin and I took my family and we went down there for a week. actually mini tramp. I just realized we've been back for. Three or four days now and no signs of COVID. So we made it the whole trip, a bunch of flights and everything.

[00:08:40] **Adam:** Bunch of extra time in the airport, unexpected. No COVID so, I'll call that a major success and totally worth me forcing my family to wear N 90 fives instead of their cloth masks. anyway, I'm back from vacation to been back for a couple of days now. And, I feel like I'm just crushing it already,to steal a phrase from Ben.

[00:08:57] **Adam:** like today I sat down and before, like my typical day, I just kind of saunter into my office, like, it's approaching nine o'clock. I sit down and get my thoughts together for a morning meeting and that sort of thing. And my mornings don't tend to be rapid fire. For some reason today, I made it to my desk early and by like 9:00 AM, I think I had like three different poll requests opened and just like rapid fire, like, oh, I could, you know it, and it was, they were all of those things were like stupid fixes, right?

[00:09:24] **Adam:** Like I had a, I was in there looking at something else, doing some maintenance work. And I saw,a panel, like a bootstrap panel that we had, added a border, like a custom border to, and because of the difference in the like border around the panel and the border radius of the panel itself, there was like a little gap in the corner.

[00:09:45] **Adam:** So it's just this like tiny little CSS fix to, to make that gap go away so that it looks nicer instead of looking like, somebody's kid, brother coded it or whatever. but it's just like little things like that. I could fix that in two minutes, slam it together, test it, make a poll request, get it done, get it out there.

[00:10:00] **Adam:** Just like. I felt like I was firing on all cylinders this morning. So I'm real happy about that.

[00:10:04] **Tim:** cool. That's a

[00:10:05] **Tim:** good vacation then if you're ready to come back and get cranking.

[00:10:08] **Adam:** Absolutely

[00:10:09] **Carol:** about feeling motivated after just like your head's clear and after thinking about things for a while, like at work, you kind of just get zoned in and kind of stop seeing everything. So when you take a vacation and come back, you're like, oh, it's like fresh

[00:10:22] **Carol:** eyes all over again.

[00:10:24] **Adam:** Yeah. And it was definitely good to take some time off of work. But the one thing that I have to say is like vacationing with kids, especially kind of like special needs kids, both my kids have ADHD and, I don't think any of the four of us are without our issues. but, and trying to deal with that in, a different environment and tried out to like rock the boat too much while we're there.

[00:10:48] **Adam:** We were staying with my brother at his house and he has a kid and, just, you're just trying to make sure that everybody has the best time. That was a lot of stress. And so I felt like while I was on vacation from work, I really wasn't taking any time for myself. It was just like, I'm in a different environment trying to keep my family happy.

[00:11:04] **Adam:** And, I could use a vacation for myself right now.

[00:11:08] **Carol:** I get that. I completely get that.

[00:11:11] **Ben:** At

[00:11:11] **Ben:** work, we have a, every now and then if someone leaves the company, we'll have what we call a little happy hour

[00:11:16] **Ben:** to say goodbye

[00:11:17] **Ben:** and talk about, reflections of time, well spent, et cetera. I think this was Ben LER. He was one of our backend engineers left a couple of years ago. And in his happy hour, someone said, are you gonna take a vacation between this job and your next job?

[00:11:32] **Ben:** And he said something like I have kids. Once you have kids, you don't take vacation. You just go on trips. And

[00:11:38] **Adam:** mm-hmm yeah.

[00:11:42] **Adam:** that's just one of the best lines I've ever heard.

[00:11:44] **Adam:** Oh, that reminds me. I guess I didn't have a good opportunity to bring this up. Tim, when you were saying you didn't have a triumph for a failure, but, I wanted to say that maybe your failure is that your progeny hasn't done anything great that you can ride on his coattails this week. Yeah. All right. Well, that'll do it for me. So that leaves you, Ben, what's going on, man.

## [00:12:03] Ben's Failure

[00:12:03] **Ben:** Oh brutal week. this is a failure. This is a huge failure, probably the largest failure. I think I'll ever share on this show, which is that Invision, which just passed our 10 or 11 year mark. unfortunately we've reached a point where we have to become profitable, which I know sounds like a very funny thing to say about a company, but we're a venture back company and, for years and years, we're just burning money, trying to build the business, trying to build the brand, trying to shape, a business vertical,and that's just no longer sustainable.

[00:12:36] **Ben:** And, we unfortunately had to say goodbye to a very large portion of our staff. Across all of our departments. I think we ended up laying off somewhere between 50 and 60% of our total headcount.

[00:12:52] **Ben:** Uh, it, yeah, it's, it's just crazy. It feels so surreal. and I feel terrible about all the people who were blindsided by it.

[00:13:01] **Ben:** we had people, we were literally hiring new people weeks before we had to do this. and, unfortunately all those people were also let go. So it was just, it was really a, just a terrible week last week for everybody. But, hopefully from those ashes rises a Phoenix and, and the company can move forward, embracing more of a, an agile mindset internally.

[00:13:26] **Ben:** We've been talking about. Going back to our startup roots and just being more agile and reducing process and reducing organizational hierarchy and just giving people more independence. And, there's a lot there to be excited about, but obviously that's excitement in the, in the shadow of fairly tragic event.

[00:13:45] **Carol:** Right.

[00:13:46] **Adam:** Sure.

[00:13:47] **Carol:** That's heartbreaking.

[00:13:48] **Ben:** Yeah. Yeah. I made it.

[00:13:51] **Carol:** He made

[00:13:51] **Ben:** I'm I made the cut. I'm still there.

[00:13:54] **Adam:** So, I mean, I don't wanna be crass or,or downplay the unfortunate events of what happened to a bunch of these people, but in the context of this show and some of the things that we've talked about in the past, the very first question that comes to my mind is, and maybe it's too soon to know, but the first question that comes to my mind is does this change the plan for sun setting the legacy application?

[00:14:17] **Carol:** I

[00:14:17] **Carol:** wanted to ask the same

[00:14:19] **Carol:** question.

[00:14:20] **Ben:** Such a good question. my intent is to work on the legacy platform until someone shoots me. Uh so the, from what I've heard in the various meetings in sort of this post apocalyptic era is the plan is still to sunset the legacy platform. But I think to be a little bit more cautious about it, there's also, it comes up in very weird ways. For example, if we are gonna move a bunch of users from the old platform to the new platform, we have to let them know that's gonna happen via email for legal reasons.

[00:15:00] **Ben:** and we have like literally millions of users in our database. These aren't necessarily people who are actively using, we don't have that many active users, but we still have to let people know. And the cost of sending out millions of emails. It's like shockingly high, For whatever systems they, that they're looking, they were looking at using something called a customer IO, and it's just like, it's super expensive.

[00:15:23] **Ben:** And I think they were gonna look at Marketo and Marketo.

[00:15:26] **Ben:** it gets complicated cuz there's all kinds of deliverability stuff. Cuz now we're talking about legal liabilities for letting people know and I like sort of said, Hey, if you really can't do this, I can Jimmy something up for you. So, so we get into these weird conversations. We're like, is it more expensive to. Millions of emails and is just to let the legacy platform live forever. Like what's actually more expensive and, because the legacy platform is surprisingly cheap in certain ways. I actually just reduced our Docker replica account from like, we have two primary ColdFusion services and one, I reduced from like 30 nodes to 15 and then the other, I reduce from 20 nodes down to five and the CPU is still like whisper quiet.

[00:16:12] **Carol:** And it's being supported by a single person too.

[00:16:15] **Ben:** yo. And,to echo Adam, I feel like I'm crushing it. Uh, but, uh, yeah, so just a lot of stuff, a lot of stuff happening, right.

## [00:16:28] Carol's Versioning Query

[00:16:28] **Adam:** our main topic for the day is gonna be, we're gonna do another version of Ben's note to self. So if you're not familiar, way back. Oh goodness. When was it? totally not Ving for time to click the thing that says episodes and search for note, episode 62, which was, I guess, not that long ago, but still several, many weeks back.

[00:16:47] **Adam:** we did, a show where we went through some of Ben's notes that he left for himself in our private channel, in our Discord, and just, let that laundry air and discuss it a little bit. Ben, you like to leave yourself these, sometimes cryptic sometimes, I don't even know how to describe them.

[00:17:03] **Adam:** Just little notes to yourself. it's fun to go through and maybe revisit some of the ones that didn't, didn't become a full fudge thing. Yeah. So who wants to start us off?

[00:17:11] **Carol:** I have a question about the versioning number of this show.

[00:17:14] **Carol:** So in order to get a major release number, would it require one of us to start making our own note to selves? Then it

[00:17:21] **Carol:** would be like 1.2,

[00:17:24] **Adam:** So, what we're getting into for the uninitiated here is called SIM or that's short, first semantic versioning. I personally prescribe to SIM two. Oh oh.which it's just a, it's a, basically it's a contract in that, it's a set of rules that you are agreeing to abide. but it there's no penalty.

[00:17:43] **Adam:** If you don't, it's just, this is a way of trying to, be predictable for software versioning reasons. That's helpful. so you increment the major version number if you introduce a breaking change. So I would say if Ben left the show, that would be a breaking change. so yeah, I just went with ODOT two because, we're doing it again. It's another release. It's, there's some new content here, but we're gonna keep the same format.

[00:18:10] **Ben:**

## [00:18:11] Flaky Tests Are Sus

[00:18:11] **Adam:** note to self flaky tests feel suspicious to me, a non tester. The, the,the most fun part about this is trying to do like a, an introspective voice.

[00:18:23] **Tim:** Mm-hmm ASMR kind of voice.

[00:18:26] **Ben:** So, so I'll prefix this with the fact that I have, I don't test. I mean, I do manual testing. I don't have any automated testing, so I have pretty close to zero hands on experience

[00:18:38] **Tim:** You have no freedom of speech,

[00:18:41] **Ben:** And, it's one of those things. So I'll be listening to podcasts or I'll be hearing an advertisement for something and time and time again, people bring up this idea of flaky tests that is automated tests that just sometimes don't work.

[00:18:56] **Ben:** And,

[00:18:56] **Ben:** and it's like,

[00:18:59] **Ben:** I

[00:18:59] **Tim:** they give false negatives

[00:19:01] **Adam:** Yes.

[00:19:01] **Tim:** or

[00:19:02] **Tim:** false

[00:19:02] **Ben:** I think so.

[00:19:03] **Ben:** Yeah. Yeah. And so again, I don't have a hands on experience here, but I do program and like, I, if I'm good at anything in this life, it's following a request from start to finish and kind of understanding where things break. And so I feel like when people talk about flaky tests, again, huge caveat here, no hands on experience, et cetera, etcetera. It's like my like BS meter goes off a little bit.

[00:19:29] **Ben:** It'd be like,it'd be like, if you were talking to an engineer and they were like, Hey yeah, I run this query against the database. And like just every now and then the database gives me the wrong data. I'd be like, no, that's not how databases work.

[00:19:40] **Ben:** that's definitely a you problem.

[00:19:42] **Carol:** Let me ask you if this is considered a flaky test. So when we do an NPE refresh, which if you, that means we're taking our production data and we're bringing it down to non-production environment so that we have a nice testing and developing area, we clean it and everything. So no real data's there.

[00:19:58] **Carol:** That could cause problems. But anyways, when we bring that down, there are several tests that fail, because like, let's just say we have one that says, does user ID 10 have an active flag for this permission while in production, this user no longer has that permission flag, but no one's ever updated the test actually queried to see does that user.

[00:20:23] **Carol:** So every time we come back down, we have these MP failures in the test because we have to go in and manually change it back in the database to turn that permission back on. So now the test passes, when, there are ways to resolve that. I know it, but is that a flaky test?

[00:20:39] **Adam:** So I'm going to go out on a limb here and say, that's not even a test. That is just a waste of time.

[00:20:44] **Carol:** Yeah,

[00:20:45] **Adam:** that, that test doesn't prove anything except that some data exists in a database in the way that somebody at one time was maybe expecting for some reason, but it doesn't

[00:20:53] **Carol:** that the permission would never be removed, that the permission still exists is my under anyway. So

[00:20:58] **Carol:** we won't go into the details of why someone wrote it, but this

[00:21:01] **Carol:** I'm just asking, is that a

[00:21:02] **Carol:** flaky test?

[00:21:04] **Adam:** it's a waste of time. It's not a test at all. I think either that test needs to be updated to, to represent what it's supposed to be testing or deleted,

[00:21:12] **Tim:** I'll say this to you, Ben. So in your scenario where you said I'm very good, like following through the request chain to see where the error is, that means that an actual person, either a tester or a customer has received that test at that point, the whole point of unit testing is to try to not have those in the first place so that you

[00:21:34] **Tim:** at the programming level.

[00:21:35] **Tim:** Right. So it's like.

[00:21:36] **Ben:** my, my, sorry, my, what I meant by that was that even as someone who doesn't write tests, I feel like I have technical understanding. And that's what, and that's all, I mean, is that when I, when someone tells me that they write code and then sometimes. The code just doesn't work the way they expected it to I'm like, like I just wanna call .

[00:21:57] **Ben:** Like

[00:21:58] **Adam:** Yeah,

[00:21:58] **Adam:** no, your instinct is dead on, a flaky test is a real thing and it is a problem. and it's a symptom of a larger problem, right? the problem isn't that the test is flaky. The problem is that the test is not either the test is not, well written or the system is not well testable.

[00:22:15] **Adam:** so I'll give you an example of an actual flaky test that I had to deal with, which was, we had, some, it was a CFML application, and to run the tests, we were using CommandBox and it would, I think it was like a, this was okay. This was back before GitHub workflows. and we were doing this on Travis CI. And in order to make that work, I didn't put this together. I was not smart enough to be able to get stuff like this, working on Travis either at the time or possibly still currently. I was copying somebody else's work and modifying it to, to get it working, whatever, but long story short, our test suite would run and that involved, downloading, command box from, a package registry, like a, not NPM, but like a, RPM or Yu install or, app get that sort of thing.

[00:23:01] **Adam:** And the server that hosted the package that was trying to be installed was flaky. Like it just would sometimes go offline. And if you can't install the thing that you need in order to run the test, then the tests sometimes pass and sometimes fail. And it became so. almost like consistently 50% that you, we just had zero trust in the test anymore.

[00:23:23] **Adam:** and no, everybody stopped paying attention. When the tests failed, it was like, oh, they're failing. It must be because the thing is offline again. and then the tests that were actually running and we're actually reporting real failures got ignored because we didn't have confidence that the test suite itself was useful.

[00:23:42] **Adam:** That is a flaky test. That is a terrible problem. And so we completely changed our testing approach because of that

[00:23:48] **Ben:** Yeah.

[00:23:48] **Adam:** And

[00:23:49] **Ben:** And I will also say that anything that has to hit the network. I mean, that's just outta your hands. that is definitely gonna be flaky. Cuz networks just have

[00:23:58] **Carol:** No

[00:23:58] **Adam:** unreliable. Yeah,

[00:24:00] **Carol:** Hey, you have no control. Yeah.

[00:24:02] **Adam:** Uh, that's all I have to say about that. I, yeah, like, I

[00:24:04] **Carol:** tests are the worst. We agree.

[00:24:06] **Adam:** yes. Okay. Carol, why don't you do one.

## [00:24:08] Overly General CSS Selectors

[00:24:08] **Carol:** All right. Dear diary, overly general CSS selectors are the worst. The worst input type techs makes it much harder to override PS. I discovered sunglasses and they're amazing love then

[00:24:29] **Ben:** so this is, a frustration that I feel on the daily because, again, I'm working in a legacy application and the legacy application. we hired someone years and years ago to build just kind of the core CSS. And he pulled in bootstrap and then modified it as the core of our application.

[00:24:49] **Ben:** And this is not to throw shade on bootstrap. but bootstrap makes some very specific choices about how it wants to style things like, and then the guy who built our core CSS then also had some very specific ideas about how things should be done. So it's like every label element, like core label element has a bottom margin.

[00:25:10] **Ben:** And, and it's like, now every time you want to use that somewhere, you have to explicitly say, don't give me a bottom margin or give me a different bottom margin. So it's, there's just so much general CSS that, it makes it very challenging to override. And then the example that Carol has there with the input of type equals text, It's like input and type people's texts are two different selectors

[00:25:35] **Ben:** in terms of specificity.

[00:25:36] **Ben:** So now it's, if I wanna override that, I can't just use a class because element and attribute is actually a higher specificity than class. So if I wanna override the styling on an input, I have to just add additional classes or do input dot class to make sure that I have an equal specificity.

[00:25:56] **Ben:** And it just, it's just such a nightmare. And it makes

[00:25:59] **Adam:** Yeah, you're not wrong. I'm over here, like trying to hold in my, my I'm biting my lips over here to, to hold it in. I had did a hack and I forget how I came across this, but you're absolutely right about the specificity being the problem. and one day I have no idea how I came across this idea.

[00:26:14] **Adam:** Maybe I thought it up myself, but if you just put a class on something and then when you're in your CSS file, where you're defining the rules, if you put like, so if your class name is Fu, if you do.food.food.food.food, do dot the the specificity. I don't like, I don't know if classes multiply or, if that's, IDs or whatever, but like, you can just repeat the same selector and that increases the specificity.

[00:26:39] **Ben:** Yeah, that's awesome. Yeah, I, cuz I think elements, attributes in classes, I think they all have the same level of specificity. So you just have to have more of that number than the other people.

[00:26:50] **Adam:** Right.

[00:26:52] **Carol:** I just wanna

[00:26:53] **Carol:** see this code, like popped up somewhere where it's just like one after the other. I'd like,

[00:26:59] **Carol:** what the hell are you trying to accomplish right now?

[00:27:02] **Adam:** I have no memory of what, where I did this. what the reason was or anything like that. And I'm sure it was like when I was, in that gap where like, I, I now know enough to get myself into deep trouble with CSS, but I'm not actually good at it yet. And I feel like I hopefully have grown beyond that now.

[00:27:18] **Adam:** And I can, not paint myself into that corner, but.

[00:27:21] **Ben:** Yo

[00:27:21] **Carol:** I just feel like I can't get good at it. Like I

[00:27:24] **Carol:** don't do it enough to get good at it. Yeah. And I get super frustrated when I'm doing it that I end up asking someone to help me and they take over because I'm doing such a bad job that I go back to doing something I'm good at.

[00:27:35] **Ben:** And CSS, I think is one of the hardest things to clean up in an application because

[00:27:42] **Ben:** nothing blows up. Right. If I, if I have a base style for input type equals. I can't just remove that because there's inputs of type, text everywhere in the application. And again, it's not like the code will suddenly break.

[00:27:56] **Ben:** It'll just, the UI will just look junky. and even if you had unit tests and integration tests, like unless you're doing, UI snapshotting, which from everything I've heard is a nightmare in and of itself.

[00:28:08] **Ben:** Uh, you're not gonna be able to find this and it,it's terrifying. I mean, that's why, thankfully a lot of, applications have moved towards, there's so many different names for it, like CSS and JS and component styles.

[00:28:20] **Ben:** And where it's, the CSS is very tied to a very specific

[00:28:24] **Carol:** To that module. Yeah.

[00:28:26] **Ben:** Yeah.

[00:28:26] **Ben:** Makes it so much easier.

[00:28:28] **Adam:** For

[00:28:28] **Carol:** But that usually required that usually ends up with duplication though, to you, right?

[00:28:32] **Ben:** Yes.

[00:28:37] **Carol:** Yeah.

[00:28:38] **Adam:** I, I would say that is the life story of CSS duplication is its game.

[00:28:43] **Carol:** Yeah.

[00:28:44] **Adam:** the, it's such a continuously evolving beast that there's, it's almost not worth it to try and prevent duplication in your CSS. It's like, just get it done.

[00:28:55] **Ben:** I think the, I can't remember if this is in the go world or if this is the Ruby world, but one, either Ruby or go has an idiom, a little duplication is better than a little coupling or something like that. and I think CSS, I look at CSS very much the same way. I'd rather have some CSS duplicated rather than having a whole bunch of elements now, coupled together, because they happen to share the same class or something like that.

[00:29:19] **Carol:** that.

[00:29:19] **Adam:** avoid hasty abstractions.

[00:29:22] **Ben:** yes, and one of these days I'll look at tailwind. People seem to rave about tailwind. Cause I think it solves a lot of these problem. Supposedly

[00:29:30] **Adam:** Tailwind is like, it's not really, so bootstrap, I would say is like paint by numbers. Right. It gives you things and okay. You can pick a color here and you can,put this control over there. Tailwind is like, I, I don't know, maybe bumper bowling, right? Like, it's,it keeps you in your lane, you, you set these specified like, okay, I want a large to be this big and a medium to be this big and a small to be this big.

[00:29:52] **Adam:** yeah. I don't know. That's the best I got.

[00:29:54] **Ben:** I'm

[00:29:54] **Ben:** gonna watch, like, I I think there's, I think there's some TMY courses on tailwind. I'll probably just start out by doing that, just to kinda let it wash over me. Cause I've looked at some of the code, like demo code and it just it's like reading another language to me

[00:30:09] **Ben:** until I guess you really understand what all the little shorthands for the CSS classes.

[00:30:14] **Adam:** The class names. Yeah. they can be kind of cryptic if you don't know what you're it's I think it's much easier to go. Okay. I wanna do, a bottom right. Border radius. How do I do that? And look it up than to read the code and go, oh, this is a bottom right. Border radius. Right. So it's like, REDX right.

[00:30:29] **Adam:** it's easier to write than it is to read. but there's cheat sheets and stuff to, to deal with that. And I think that, the way I would love to see it used in my applications going forward is tailwind classes on components. But then once you start using component you that. Is no longer something that you're looking at, right.

[00:30:45] **Adam:** I'm doing an accordion view and it's, it has some things inside it that control the styling, but that's not what I'm concerned about while I'm using the accordion.

[00:30:55] **Ben:** Well, and that's the thing that, that I fail to connect with. When I hear people talk about tailwind, because eventually someone will say, well, what happens when I have. 17 buttons. And I want them all to have the same style. And then they're like, someone will be just like, oh, well then you just created like a utility class that encapsulates all the other tailwind styles that you wanna add.

[00:31:14] **Ben:** And then I'm like, well then why am I using in the first place? Like, why don't I just have a button class that I want all those styles in and just write vanilla CSS. And it just feels like we eventually get back to the componentization of things anyway. So I, again, I don't have any experience here and I don't know anything about toe and really other than what I've heard.

[00:31:34] **Ben:** So again, I'm not throwing shade or

[00:31:37] **Adam:** I, I think it has,you know, what I've been using utility classes for styling, just, my own made up utility classes for a long time, it's nice to, and I guess I was just doing it because the shorthand of writing like Mt. Five for margin top five pixels was handy rather than having to type out style equals margin five PX semicolon every time.

[00:31:59] **Adam:** Right. and so I, like when tailwind became a thing, the utility class thing, I was like, that's okay. That's kind of what I was already doing. What does this person, Adam wain, who created tailwind? what does he understand at a more fundamental level that I don't, and that kind of revisiting that and digging into that, I think made a lot of sense to me so I can understand how, if you haven't had that same experience, it doesn't click as easily.

[00:32:24] **Adam:** but yeah.

[00:32:25] **Ben:** and it is really amazing that they, it essentially caps the amount of CSS that your application can ever have because you

[00:32:32] **Ben:** have all this, these atoms, these atomic values of CSS, and you're just mixing and matching. So your HTML can continue to grow and grow forever. But the amount of CSS that you actually have is fairly finite, which is, I mean, that's pretty powerful.

[00:32:47] **Adam:** Yeah. And I mean, I don't wanna turn this into a tailwind love Fest, but they have a new, like J I T just in time compile sort of thing where like, you build your app I, I've only messed with it with SELT, but basically,tailwind is integrated into the build process.

[00:33:02] **Adam:** So the styles that you use in your components are the only ones that appear in the style sheet. So instead of like, including the bootstrap CSS file, and you've got all of these rules that you're not using, the CSS file that comes out of J I T approach is only the rules that you're using.

[00:33:16] **Adam:** So it's even more. I'm gonna say it it's even more SELT. It's slimmer.

[00:33:23] **Ben:** Awesome.

[00:33:24] **Adam:** Cool.

[00:33:24] **Carol:** Can we get one more in

## [00:33:26] 2015 Called, It Wants It's Build Script Back

[00:33:26] **Adam:** Let's do it.

[00:33:27] **Adam:** note to self. I wrote my first gulp JS plugin, 2015 called it wants its build script back.

[00:33:36] **Ben:** Yeah. Uh,

[00:33:38] **Carol:** laugh.

[00:33:38] **Ben:** build processes are something that I have very little experience with. I on our legacy application, some team seven or eight years ago build the build scripts. And it's literally been the same build script since then. And that team no longer exists. And all of those people have left the company, probably five years ago.

[00:33:59] **Ben:** And, I've been slowly trying to improve the legacy application shocker,and I needed to make some tweaks to the build script and it used golf. And,I don't even remember what the heck it did, cuz this note to self was from like a month or two ago. oh, I remember what it was. So in angular JS, you can define components and you can say that the template for this component exists at this URL.

[00:34:23] **Ben:** And there was a go script that would take that URL and essentially read it into some code. And pre-cash it using this angular JS very specific kind of a thing. but the way that angular was executing, that it was causing a whole lot of processing that it shouldn't have been. And so I needed to write a Gulf JS plugin that didn't just pre-cash it, but actually replace the template URL with the actual template itself.

[00:34:49] **Ben:** So essentially interpolate the content of the HTML into the code. And,it, I did it. I mean, it was pretty exciting. I know this sounds stupid. It ended up being like 30 lines of code and it uses through two streams and node. And I don't really know anything about streams and node. I actually, years ago spent like, God, it felt like four months trying to understand how streams and node work, just so that I

[00:35:09] **Ben:** could build a Gulf JS plugin.

[00:35:11] **Ben:** And then I ended up, then this team came in and they did all the builds anyway. So I never ended up having to use any of that information, but, I don't, I just felt super proud of myself for making this Gulf JS plugin. even though I know it's wildly out of date and,not supported by any known plugins in the NPM system anymore.

[00:35:32] **Ben:** but,

[00:35:32] **Adam:** I think it's on brand, you're still writing ColdFusion. You're still writing gulp. Those things go hand in hand.

[00:35:39] **Carol:** Ouch.

[00:35:41] **Ben:** but I, you know, you were talking about ES build the other day and

[00:35:46] **Ben:** I mean, I would love. To be able to upgrade our build process, to use something more modern, whether it's ES build or even web pack or roll up or,

[00:35:55] **Adam:** Just

[00:35:56] **Adam:** skip web pack.

[00:35:57] **Ben:** Just skip. What's the other one

[00:35:59] **Adam:** Go straight

[00:36:00] **Ben:** has like a box on it. Oh yeah.

[00:36:02] **Ben:** V I hear everyone's just raving about everything in the V E in, in the view

[00:36:06] **Ben:** ecosystem, people just are like, freaking out about how great everything is. So I don't have much more to say on that. It just, I was very proud of myself that I did this tiny little

[00:36:15] **Ben:** thing and it took me like six hours

[00:36:18] **Adam:** As someone who, 10 years ago, tried to write a plug in and had difficulty with it. I commend you because that's not an easy thing to accomplish, especially now that nobody uses gulp anymore. And you there's probably no good help for it.

[00:36:32] **Ben:** but it's interesting because it also did give me insight into serious blind spots, I would say in how build systems work. The way that this, that our build works is that we take a whole bunch of JavaScript files and we essentially can CAATE them together and identify them. and then they do sort of the same thing with the HTML files.

[00:36:53] **Ben:** But the problem is now I have this small subset of components that was actually pulling the HTML into the code itself. But the other part of the process didn't know that. So what I would've ended up doing was both pulling that code in one place and then concatenating it in another place. And it would've basically been a Noop in one way.

[00:37:14] **Ben:** Like it just like one process, would've put it somewhere that no one would've ever looked for it. but I realized that, it's one thing to look at a build step as a series of small steps, but oftentimes those small steps have to know about each other to some degree. And I don't understand the mechanics by which that happens.

[00:37:31] **Ben:** And that's, it's not just a golf issue. if you look at a web pack where it'll do things like. Code splitting or it'll pull CSS into other components and then it'll generate link tags that automatically get injected into HTML templates that, that point to that CSS and I'm, and it's just like, I don't understand how the communication between the different parts of the build happens.

[00:37:54] **Ben:** It all feels either's, it's either like extremely magical or it's just like so obvious. It's not obvious where it's like, they just keep a manifest of all the things that they've done and they pass that manifest to every single step so that every single it's like the in, in a note express app, you can pass requests down through all of your middleware

[00:38:13] **Ben:** that's how all the middleware can know about the other middleware that's executed.

[00:38:17] **Ben:** And you're like, oh, well, yeah, that's stupid. I mean, it's stupid. And that it's so obvious, like, yeah, you just take like the world of information. You just keep passing it down the pipeline so that anyone could add anything to it. And then anyone down the line can check to see if that thing was added. And it's like, I don't know if that's just what's happening and it's so Abdu that I can't see that's what's happening or if something actually like really magical is happening.

[00:38:40] **Ben:** That's a lot of rambling. Sorry. Builds are hard.

[00:38:42] **Adam:** I think we can have time for another. Let's Do

[00:38:44] **Carol:** Do we okay.

## [00:38:46] Sharpening My Blade

[00:38:46] **Carol:** Let's see. Note to self. I spend a lot of time sharpening my blade, which I often think is a waste of time. However, upon reflection. I see that so much of what I glean in my experimentation, is such that I end up applying to work.

[00:39:02] **Carol:** So maybe it's not a waste of time hearts and kisses, Ben.

[00:39:10] **Ben:** So I spend, I'd say an extraordinary amount of time looking at code and thinking to myself, what if it worked this way? Or what if I tried this? Or what if I passed this value into that value? Or can I reference this method in a funky way? Or can I store this in a scope and then try to reference later?

[00:39:32] **Ben:** Or what happens if I pass it through this weird serialization process? and I, so much of that feels like if you think about. the total amount of understanding someone can have for a particular area like gold fusion or JavaScript or CSS or whatever. It's like at some point there's a diminishing return on investment.

[00:39:54] **Ben:** LikeI'm adequate, I'm pretty proficient. And then all the time that I spend researching above and beyond that maybe is a waste of time. And maybe that time would be better spent learning something entirely newer or trying to have a completely different perspective. I love relational databases.

[00:40:09] **Ben:** So does it make more sense to understand how, indexes work or should I look at,a document database or a key value store or something like that, or an event stream to, to really radically shift the way I view the world, would that be a better investment in my time? and I struggle with this a lot.

[00:40:25] **Ben:** but then every now and then I'll be doing something at work. And we'll run into an issue and I'm like, oh, you know what? I actually looked at this a couple years ago. I totally know how to do this. And suddenly I see an opportunity to apply this like stupid little thing that I learned years ago. And now it's a breakthrough in what I'm doing at work.

[00:40:45] **Ben:** And now I'm like, holy monkeys,

[00:40:47] **Adam:**

[00:40:47] **Adam:** this is auch system. I know this.

[00:40:52] **Ben:** that's a

[00:40:53] **Ben:** Jurassic park reference But so every now and then, like, I'll realize that this silly esoteric piece of information that I've S scrolled away in my head and have not used, and maybe was a waste of time suddenly that's that it's at my fingertips and I'm using it to solve a problem.

[00:41:11] **Ben:** And I'm realizing, or I'm thinking that maybe all this random time that I spend looking at odd aspects of a language or technology like those actually do. Add value in the long run or, is a broken clock just still right. Twice a day. And coincidentally, something I learned is helpful, but I still would've been better served, not spending so much time nitpicking over little details.

[00:41:36] **Ben:** I, I struggle. I struggle with how I feel about my time allocation,

[00:41:41] **Adam:** I don't think it's ever wrong to be curious, and to go where your curiosity takes.

[00:41:45] **Carol:** yep. You only live once. Right? So whatever makes you happy do it. Like if it's learning more in depth about where you're at do that, if it's, learning something new, do it, like whatever makes you feel good. Let that be the thing that you do. That's okay.

[00:42:00] **Ben:** yo, and then sometimes it makes me really bitter if I can be super transparent for a second, cuz I do spend a tremendous amount of time. like I say, sharpening my blade.

[00:42:10] **Ben:**

[00:42:10] **Ben:** And then someone will say something flipping like, oh, what I love about react is like, you can just pick up react and be really good at it in two weeks.

[00:42:17] **Ben:** I'm like, you know what F you,

[00:42:18] **Ben:** I spend like years, trying to get better at any particular technology. And you're telling me that you can just step in with react and be really good at it in two weeks. Like, no, you're building terrible stuff. I guarantee it. And I like, I'm sorry. I just like, get that off my chest.

[00:42:33] **Tim:** too ignorant to know how bad you are.

[00:42:36] **Tim:** Right.

[00:42:38] **Adam:** That's exactly right.

[00:42:39] **Carol:** It's a very

[00:42:40] **Ben:** like, there's

[00:42:41] **Carol:** Yeah,

[00:42:41] **Ben:** you can't pick anything up and be good at it right away. That's just not how life works.

[00:42:46] **Carol:**

[00:42:46] **Adam:** Dunning Kruger at work.

[00:42:48] **Tim:** For

[00:42:48] **Tim:** sure

[00:42:49] **Adam:**

## [00:42:50] White Papers

[00:42:50] **Tim:** Note to self, there are people who read. White papers about programming and there are people that don't I'm the latter. Is that something that can change or is that a natural trait? Love

[00:43:08] **Tim:** Ben.

[00:43:09] **Ben:** I think they're just like, there are people not to paint with a broad stroke here, and I'm not gonna use the right words, but I feel like there are people who are just very academic,

[00:43:18] **Ben:** academically minded and they can draw on this rich history of computer science.

[00:43:24] **Ben:** And, oh, you know, when this guy invented this technology back in 1967at Xerox labs or at bell labs, I'm just like, I don't know any of that. And then people talk about, oh, DynamoDB is so groundbreaking. Look at Google's big table. And they wrote this white paper on. You can go and look up really interesting mathematics about how it works.

[00:43:46] **Ben:** I'm just like, I'm never gonna do that. I'm never gonna look at. A white paper on what makes a technology interesting. And I like, sometimes I feel bad about that, that one of the criticisms of the computer science world, orI maybe more specifically the web development world is that it has no history.

[00:44:04] **Ben:** Like everyone's just relearning the same things over and over again, because like the one generation isn't passing information down to the next or probably more accurately, the new generation is not learning from the old generation. And sometimes I feel like I'm part of that problem by not taking more of an interest in the history of things.

[00:44:22] **Ben:** But I just, like, I just don't care about it. That's not the right word. Karen's not the right word. It's just like, that

[00:44:29] **Tim:** You don't see the practical aspect of it, right?

[00:44:32] **Ben:** Yeah.

[00:44:33] **Adam:** Think I, I feel like you kinda hit the nail in the head when you related this to like the rich history of computer science. First of all, I think that the people who read white papers and who are inclined to read white papers are also the type of people who are inclined to write white papers. So, they're, that's a different, approach to the industry, but it reminded me of this, pretty famous Dykstra quote, computer sciences as much about computers as astronomy is about telescopes.

[00:44:59] **Adam:** Like it's just a tool for accomplishing the goal. Right. and like we said before, where, wherever your curiosity leads you, I think is the right path to go. And if your curiosity leads you into the theory of computer science and like, touring machines and that sort of thing, then fine go for it.

[00:45:17] **Adam:** that's great. You're probably gonna find more, useful content in white papers. Then you are in blogs for that.

[00:45:23] **Tim:** of see computer just the web, computer programming, the industry itself, because it's becoming more and more part of everyday life. I mean, everything is, deals with computers and computer systems and computer programming. I mean, so you have the people who design.

[00:45:39] **Tim:** A car and design the factory that builds the car. They're a very limited number of people and they have a very different skillset and a very different kind of mindset and education that they have. But then you have a huge amount of people that need to work on those cars and maybe not a popular opinion, but I think eventually computer programming jobs are gonna kind of be like the mechanics of the future.

[00:46:01] **Tim:** Right. That's it's gonna slowly as more and more people do it. There's gonna have less and less, demand cuz you have too many people doing it. You're gonna, they're gonna get paid less and less. it's gonna, but kind of be like, most people, a lot of people are in the computer industry and they're programming and it's kind of, stuff you learn at low quality schools and they get the job done, but it's like, none of 'em are super geniuses right.

[00:46:24] **Tim:** So, but the super geniuses of the people that are building the systems, right. Building the programming language. so yeah, I mean, not to paint us with a bad brush because I don't think any of us here are like, building, new systems and kind of things we're kind of working within the ecosphere that I've already been created.

[00:46:38] **Tim:** but yeah, I think it's just a mental attitude of I'm more interested in, what can I do with something than like, what's the history of it? what's the, how'd it get here and, how's it, different, technically different from, its predecessors and that sort of thing. I just wanna know how can I build something?

[00:46:54] **Ben:** Yeah, I'm very visual thinker, I think. And, and if I can't visualize how something works, I find it very hard for me to wrap my head around and, So I think, I think a lot of academic stuff until I can see it in sort of a hands on way. it doesn't sink in very well for me. So it doesn't feel like it's information that I connect with.

[00:47:14] **Tim:** Yeah. I mean, I learned from tutorials so much better than a white paper.

[00:47:17] **Adam:** Okay. Note to self building, instead of installing removes a lot of security and license considerations.

[00:47:27] **Tim:** does it.

[00:47:28] **Ben:** fact.

[00:47:29] **Adam:** it

[00:47:29] **Adam:** does,this is one that I agree with, but I also feel like. not to be rude, Ben, but I think it's maybe a little shortsighted. yes, it removes a lot of security and license considerations because when you, install an NPM package, you have to be concerned.

[00:47:42] **Adam:** Is this a, does it use a permissive license or is it like GPL and requiring that I GPL my code, that sort of thing. and that's not nothing that's, definitely something that we need to be considerate of as we're working. But I think the security thing, is a double edged sword. and, one way it cuts is really good.

[00:47:57] **Adam:** One way it cuts is really bad, by building, instead of buying, or building instead of installing as you put it, yes, you don't have to worry about some random person halfway across the world, introducing, intentionally, introducing a malicious backdoor into your app, but you also don't get all of the free security updates that come along from using community projects. raise your hand among the four of us. If, if you have ever found, a RegX based DDoS in any of your code vulnerability, right? Like, yeah. Nobody has our hand up, because that's just not something that I understand how to recognize. but you know, that's like probably the number one thing that I see come through in the NPM, security updates, right?

[00:48:39] **Adam:** Like somebody found another red X CDOs thing. Like, okay, well technically the chances of that being a problem are so low, but, Hey, why not fix it? It's there. It's free. It's been vetted.

[00:48:49] **Ben:** I, I, I,I agree. and I clearly I install stuff. I mean, there's projects that it's, I think it's just not feasible for someone to do on their own. I'm not gonna, I'm not gonna build my own mark down to HTML converter. I'm not gonna build my own database drivers. I'm not gonna build my own reds client.

[00:49:07] **Ben:** I'm not gonna build my own less compiler type script, etcetera.

[00:49:11] **Tim:** Or your testing library.

[00:49:13] **Ben:** Well, maybe, that actually feels like it could be tractable Um,but I don't know where the cutoff is. I don't know where I look at something and say, I could build that and that'd be fun and feasible.

[00:49:25] **Ben:** And I don't know where that becomes. I just wanna install it because I wouldn't be able to do this as, as well as someone else. I will say from a process standpoint, and this is obviously gonna vary from company to company, but at work, I can't just install something because I need it. I have to get it approved by the security team and they have to look at it and make sure that it's not problematic and they have to look at the licensing and make sure that's not problematic.

[00:49:49] **Ben:** So sometimes building something is just a way not to have a process, not to go through a conversation with another team and just get it done.

[00:49:58] **Adam:** Oh, bureaucracy.

[00:50:00] **Ben:** Yeah. VO show. but also, a lot of times when something is provided as a library, it has to take a lot of use cases into account. And sometimes the thing that you're doing exists in a very finite way, and you don't have all those use cases. I know the,what's the guy who did low dash John David Dalton, something like that. he talks about part of what makes low dash so fast is that it's not, it's like it doesn't adhere to a specification, that there are things that say, like the array for each method, the native array for each method does that low dash doesn't do because it's so esoteric. It's like such a weird edge case in the specification that no one actually needs it.

[00:50:42] **Ben:** So he doesn't account for it. And because he doesn't account for it, he's able to make his code that much faster. and I feel sometimes building stuff is you need the tiny sliver of the thing. This does. By just building the sliver. You don't get all of the weight and the performance issues that might come with the larger thing.

[00:51:00] **Adam:** Baggage.

[00:51:02] **Ben:** Yeah.

[00:51:03] **Adam:** Yep. Yep.

[00:51:03] **Ben:** It's a trade off for sure. it's not obvious. It's not very clear what needs to be done. it's always a calculation.

[00:51:10] **Adam:** Word. Cool. Well, we've been on for quite a while here, so let's, stop it there. So then that brings me to,

## [00:51:17] Patreon

[00:51:17] **Adam:** This episode of Working Code is brought to you by flaky tests.

[00:51:19] **Adam:** Just like grandma used to make and listeners like you. if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them special.

[00:51:36] **Adam:** Thanks to our top patrons, Monte Gavin and Sean, all patrons get early access to new episodes and our after show, tonight on the after show, Ben has a bday. We're gonna talk about that time that Donald Glover paid Tim to prank his director.

[00:51:49] **Adam:** and maybe if we have time, we'll get into Tim's thoughts on what it takes to become profitable.

## [00:51:55] Thanks For Listening!

[00:51:55] **Adam:** so homework this week, let's do, let's go back to leave us a review. So you can go to workingcode.dev/review, wherever in the world you live. And it will take you to your local iTunes where you can leave us a review.

[00:52:06] **Adam:** And we would really appreciate that. you can send us your topics and questions to @WorkingCodePod on Twitter or Instagram. You can join our Discord at workingcode.dev/discord. You can email us at WorkingCodePod@gmail.com. You can record a voice memo and send that to us at the same email address, and we will play it on the show.

[00:52:24] **Adam:** That's it for this week, we'll catch you next week. And until.

[00:52:27] **Tim:** Remember your heart matters. And particularly you Carol, sorry. You had a bad day yesterday. You mean the

[00:52:32] **Carol:** Aw. Thank you guys.
