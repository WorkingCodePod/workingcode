---
title: "252: Meet Showbot"
description: "Tim spent a single Sunday afternoon with Claude and built Show Bot -- a sarcastic Discord bot trained on every Working Code transcript."
date: 2026-03-18
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/8730260e-c5d1-4519-810b-18d8b8eb3fac"></script>
<div class="redcirclePlayer-8730260e-c5d1-4519-810b-18d8b8eb3fac"></div>

Tim spent a single Sunday afternoon with Claude and built Show Bot -- a sarcastic Discord bot trained on every Working Code transcript, complete with a Dungeon Crawler Carl personality, fallacy detection badges, and a talent for roasting anyone who tries to prompt-inject it. The conversation turns into a deep technical walkthrough of RAG pipelines, local models, cross-encoder reranking, and what happens when you just start building things that make you laugh.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/252-meet-showbot.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** that's a perfect scenario where you just like throw it at Claude and you're like, okay, here, you know, I'm getting stuck with like this testing.

[00:00:04] **Ben:** I'm trying to accomplish this, my friends tell me I'm writing end-to-end tests when I thought I was writing integration tests. What's wrong with my friends?

[00:00:13]

## [00:00:33] Intro

[00:00:33] **Adam:** Okay, here we go. It is show number 251 and stop the presses. Ben wrote tests. We're gonna dig into that. He's run into a couple roadblocks. I'm sure we'll have some advice. We're just gonna talk about it, you know, see what's going on, try to reward the behavior we wanna see in the world.

[00:00:48] **Adam:** Uh, and, and, but first, as usual, let's start with our triumphs and fails. it doesn't, I guess it kind of feels like it's time.

## [00:00:55] Adam's Triumph

[00:00:58] **Adam:** It looks like it's my turn to go first, so I'm just gonna start us off with a triumph. and that is that, you know, we've talked many times on this podcast about. Me trying every to-do app under the sun.

[00:01:06] **Adam:** If it's out there and it doesn't cost an arm and a leg, and even if it just costs an arm, I, I've probably tried it. I, I have paid for the things app on my phone and my desktop or slash laptop, whatever. So I have, it's like a hundred bucks. I'm invested into this to-do app. and that's just one of the many options I've tried, and none of them I feel like fit the way I want to work.

[00:01:27] **Adam:** And so this week I vibe coded a to-do app, which okay, whatever, it's a to-do app, nobody cares. But it works the way my brain works and I think it's gonna help me be more focused on getting my to-dos done. I think the mistake that I. Traditionally make with a to do app is I put way too much on the, like this is my current list and then when like 80% of that should be in the backlog, right?

[00:01:52] **Adam:** and I just carry the today list over for like nine weeks before some of those things actually get done or I decide to reschedule them or whatever. and so I'm kind of taking a more approach of like, you have the backlog and you have today and every day when you open the app, it is, it's like a, this little bit of ceremony where it's like, okay, these, this is your backlog.

[00:02:10] **Adam:** It's, you know, sorted by due date and priority, and you can filter categories and stuff, but here's the backlog and the things at the top are most likely to be the ones that you're. Focused on, you can check off the ones that you wanna do today and, and submit it. And it puts them on the today view. and hopefully I, I just, uh, started using it, you know, a day or two ago, so we'll see.

[00:02:31] **Adam:** And jury's still out, but it feels right for me. So I'm excited about that. And, you know, this is all in, I'm like maybe two or three hours of prompting, um, going back and forth with it. So

[00:02:43] **Carol:** what is like your oldest to do item that you have on your air quote, backlog?

[00:02:48] **Adam:** that's a really good question. I would have to guess 'cause I don't have like, access to the DATETIME created or anything on it. but I would say probably four or five years.

[00:02:58] **Carol:** Yeah, I got one of those two.

[00:03:00] **Ben:** Yeah.

[00:03:02] **Carol:** So I'm glad I'm not the only one. Like I got a new phone like four years ago and I realized that through our credit card we have phone insurance. So I put a reminder to have myself file a claim against the phone. I broke to get it replaced and then sell it. And it's still setting broken my drawer, I've never filed the claim to have it fixed 'cause it's like a $50 fee, you know?

[00:03:24] **Carol:** And they just fix it. I was like, fix this in the back. Yeah. I think it's like four years old now. I probably should just mark that down and throw the phone

[00:03:32] **Adam:** Nobody wants that phone anymore.

[00:03:34] **Adam:** Yeah.

[00:03:36] **Carol:** Oh,

[00:03:36] **Adam:** Yeah, there's a, there's a, I, and I can never remember who said it, but there's this saying or, or just this quote from a interview with a musician, right? It's probably a guitar player from some rock band or whatever. But, it stuck with me and he basically said like, when we're writing new music or if I'm just trying to, trying to noodle around, figure some stuff out, I never write anything down like riffs and ideas and stuff.

[00:03:57] **Adam:** He's like, if I can't remember it, then it wasn't good enough to be in one of our songs. And sometimes I think about that in terms of my to-dos. It's like, if I can't remember it, is it really important enough to get done? But then I remember I have Swiss cheese for a brain and everything falls out and, so

[00:04:13] **Ben:** I have a to-do list, you know, like I use the iPhone's native to-do app, but then I also have a pad of paper next to me and when things are super timely. I need to put extra pressure on myself. I will write it down in Red Ink on the pad next to me for some reason, like that helps me do things that are very timely, like this has to get done this week.and for whatever reason it's like a different by taking it outside of the normal to do app, which I have, I just checked, I have a to do item, dating back to 2021. So, you know, the ability to ke keep hitting snooze on that is pretty high. So something about the paper feels like it's more immutable.

[00:04:51] **Adam:** Yeah. Yeah. I mean, speaking of paper, I used to, you know, of the many systems I tried, I used to use the little field notes notebooks. They're like, just size, just right to go in the back pocket of your jeans.

[00:05:00] **Ben:** Oh yeah.

[00:05:01] **Adam:** and I would, you know, it's a similar problem I got myself into there is like, you know, you draw the little squares down the left edge for your check marks and you write your tasks next to 'em.

[00:05:09] **Adam:** And then like at the end of the day, the ones that I still wanted to get done, 'cause you know, it's like a daily list, right? It wasn't just like, I'm not gonna flip through 17 pages to find the one task I want, I just want today's page. So I would like copy items forward. And it just got to be this like ceremony of copying the same nine to-dos every day to the next day.

[00:05:27] **Adam:** I'm like, this is dumb. So I stopped that system,

[00:05:30] **Ben:** Yeah. well, I dunno if this is the same kind of thing, but it used to be that in every bookstore, like every Barnes and Noble, the little, one of the little checkout, impulse buys was the, the little Moleskine, you know, like two by three notebooks. Oh my God. They were so gosh darn cute.

[00:05:44] **Ben:** I, I just like, I didn't even enjoy writing in them 'cause they were too small, but they just looked so freaking adorable.

[00:05:51] **Adam:** it was just the primary criteria that you should use when buying a utility

[00:05:54] **Ben:** Yeah. Ooh, it's pink.

[00:05:58] **Adam:** Yeah. All right. Well, that's it for me. How about you, Ben? What do you got going

## [00:06:03] Ben's Triumph

[00:06:03] **Ben:** Well, I'm gonna go with the Triumph, which has actually morphed into the topic of the show. So I will just say that, as we, I had hoped to come into last week's episode with the triumph of having tests and as I had mentioned last week, I went down a whole rabbit hole. I'd stumbled over a bug in the way ColdFusion handle some asynchronous array iteration coupled with, passing Lambda functions out of scope.

[00:06:26] **Ben:** Anyway, it was very low level, very technical, but it had derailed my triumph last week. And so I'm coming back and I'm saying triumph this week, is that I actually got those tests done and, uh, fleshed out the rest, which is what the we'll talk about later in the show. So

[00:06:40] **Adam:** yeah. No, I, I mean, I, I, I'm still, last week you told us that and, and it blew my socks off so hard that I, I still, you can't see,

[00:06:47] **Ben:** Socks still have not come back.

[00:06:50] **Carol:** Oh, come back. Let's take a picture. Sell those.

[00:06:53] **Adam:** Put me on Wiki feet.

[00:06:56] **Ben:** So, yeah, so that's my triumph and, we'll get into it more. But, Carol, what do you got going on?

## [00:07:01] Carol's Triumph

[00:07:01] **Carol:** Well, I'm gonna go with a triumph from a failure. Uh, Friday we woke up to our yard being very wet, which is bad when you live in the desert. That is not. A good sign. So we go outside, take a look, and sure enough water's bubbling from under our, our turf and we end up having to call and get it like fixed.

[00:07:23] **Carol:** Get a plumber out here. Luckily they came the same day and was able to get it done by the end of the day. It costs quite a bit of money and now it's good to go though. No more water's leaking. but I think the big win out of it is that my husband and I talked about it after everything happened and we just talked about how grateful we are that we have each other when these problems hit.

[00:07:44] **Carol:** And that if one of us is kind of like panicky or like full on anxiety about the problem going on, like the other just picks up the phone and starts taking action or like makes things happen and you kind of can like fall apart 'cause the other one carries you or vice versa. Right. And it's nice that.

[00:08:03] **Carol:** Through everything. Like you have this solid marriage and like this great relationship and a true partner that just holds your hand even when water's bubbling up outta your front yard and doesn't care if you start crying. So I'm just thankful for that and I think

[00:08:17] **Tim:** Which one was crying? You or him?

[00:08:19] **Carol:** I will not admit that it was him, but

[00:08:23] **Ben:** it's actually classified.

[00:08:25] **Carol:** can't tell you.

[00:08:27] **Ben:** I'll tell you, let me tell me if this feels familiar to you at all. But, I notice that in my marriage when one of us is stressed, it feels like it almost gives the other person more power to be the stable one.

[00:08:43] **Carol:** Yeah,

[00:08:43] **Ben:** I can only speak from my own internal perspective, but like, I'm nervous all the time. I have a lot of anxiety.

[00:08:49] **Ben:** I've been, you know, battling depression and whatnot, but like when my wife is having a really hard time, I don't know if it's just like, it gives me an excuse to get out of my own head, but I almost feel better. This is gonna sound terrible, but like, I feel better when she feels worse. But I mean, like, I think

[00:09:05] **Ben:** it, it, it's like, it almost, it's like the dynamic, it's tweaked so that one person has more capacity to support the other person.

[00:09:14] **Ben:** I don't know if that's common,

[00:09:15] **Tim:** it's easier to help other people than it is to help ourselves at

[00:09:19] **Carol:** I agree.

[00:09:20] **Adam:** There you go.

[00:09:21] **Ben:** for sure.

[00:09:21] **Tim:** That's, that's a much better way to say that.

[00:09:24] **Carol:** yeah.

[00:09:25] **Carol:** I'm happy when you are unhappy.

[00:09:27] **Tim:** Yeah.

[00:09:27] **Adam:** mean better than Ben's admission, that he's jigsaw.

[00:09:29] **Tim:** Yeah. Right.

[00:09:31] **Tim:** with the thing with my eye that I've gone through, it's like Michelle's got her own, my wife has her own health issues that she's just chronically been going through for the past few years. But the second, like when this happened with me, she just put all that in the back burner and took care of me.

[00:09:47] **Tim:** Still is. So,

[00:09:48] **Carol:** Yeah.

[00:09:50] **Tim:** I think that's the advantage to having a good partner.

[00:09:53] **Ben:** Yep.

[00:09:53] **Carol:** I agree. It's kind of crazy, like some of the relationship ships I've had, like in the past, that's not what I've had. Right. Like, it's been very one sided. So just to feel like I have that person that it's just there, it's, it's a giant win. Even when things go bad, it's good to have them buy you

[00:10:09] **Tim:** And it's amazing how stressful a broken pipe is

[00:10:12] **Adam:** Yeah.

[00:10:13] **Carol:** Well it is

[00:10:14] **Tim:** I went that, I, I went through that a couple months ago. If you remember, the front yard had the same thing. All of a sudden there's like a water feature in our yard.

[00:10:22] **Adam:** Oh yeah, I remember that.

[00:10:23] **Tim:** So.

[00:10:24] **Carol:** know. I, I, I told Steve, I walk out, we see the water, right? The first thing I do is I open the lid to the main and I take a look and I go, yep, it's spinning. It's on our side. I was like, water is coming through the main, so we are about to get hit with this bill,

[00:10:40] **Ben:** Oh,

[00:10:41] **Carol:** but yeah. All right.

[00:10:43] **Carol:** Well

[00:10:43] **Tim:** that reminds me that that's why my water bill was so high. I forgot about that.

[00:10:46] **Carol:** yeah. Oh yeah. We just got our too. Our water bill is typically like 140 ish bucks. $647. Yeah. Just for water. Yeah. Yeah. But that's me. I'm winning you guys.

[00:11:01] **Tim:** you both, it sounds like you as a couple are winning, so

[00:11:03] **Carol:** We are

[00:11:04] **Tim:** on that.

[00:11:05] **Carol:** Thanks Tim. What about you, Tim?

## [00:11:07] Tim's Triumph

[00:11:07] **Tim:** Well, it looks like we got a, a four of a kind here, guys. I got a

[00:11:10] **Carol:** Heck yeah.

[00:11:11] **Ben:** Nice full house.

[00:11:12] **Carol:** We haven't done that in a while.

[00:11:14] **Tim:** it has been a while. So one my eyes doing is doing better. still don't really know fully how much my vision w will. Deteriorated by this, if at all.

[00:11:24] **Tim:** But you know, it's the, the little bubble that they put in there has gotten smaller. And next week I go, I go back, from hopefully my last visit and then, you know, I'll be able to get a new, get a new vision test to see how much this is damage my eye if, if at all. But things seem to be improving. And then sort of a, a work triumph.

[00:11:45] **Tim:** I've noticed this is AI related, so I, I've noticed that people are using the LLMs to write little tools. You know, nothing huge, but just a little tool that's very specific, very niche to them and the way they wanna workflow to work. And using LLM to build software to do that. So like for instance, We call 'em our operations team, really the sort of the infrastructure networking team.

[00:12:11] **Tim:** And typically in the past how we would, you know, ask if there's something, an outage or something, we would just message them and they would act. But it's really hard to gauge, you know, how much work they're doing. are we fixing the same thing over and over again and we don't really have any insight to it.

[00:12:26] **Tim:** So just recently starting this week, I noticed that one of the guys on the team, he's not even really a programmer, but obviously he used Claude Code to build a tool that, if you put a message onto their, their teams channel to say, Hey, this is busted and you don't reference a ticket number, it automatically reminds you and it pesters you into to put that ticket number in before they ever actually do anything.

[00:12:51] **Tim:** And, and I also wrote something, to handle like, outage incident management for a whole flow of that. So, and I think, you know, as people get more and more. Comfortable with LLMs and they get better and better. It's like these little niche products that probably aren't ubiquitous enough to have some company like Jira write you something.

[00:13:13] **Tim:** You just write it yourself. But it doesn't take long. It doesn't have to be in a language, you know? but you know, you can do it probably in a couple hours, u using the LLM. So that's a nice, I, I, you know, they talk about these productivity bursts that we'll get from this, and we usually think about being a 10 x coder 'cause of ai.

[00:13:31] **Tim:** But I think productivity will probably increase more 'cause of those kind of things where we're enforcing our rules and adding value to, to, to the work current workflows that we have by using just little, tiny, little programs that get written that either A, you don't have the time to do right now, or B, you don't have the skills.

[00:13:50] **Ben:** I remember I used to have a product manager, this guy Jonas.he would always refer to paper cuts he focused so heavily on all these, like what are the paper cuts for the users when they're using the application? It's not the huge features that are missing, it's the like a thousand little tiny problems in the user experience that are getting them every single day.

[00:14:12] **Ben:** And, how just fixing those can have such a dramatic improvement into how people feel about the software they're using. And I've, I've definitely tried to adopt that mindset as well. It's, it's so, so frequently, it's the little things, not the big things.

[00:14:26] **Tim:** for sure.

[00:14:28] **Carol:** So it's, it's funny you mentioned the team, like integration, right? So I tend to always tell my people, I'm like, what can we do to automate it? Like, I don't wanna touch this again. Like, how can I automate a process? Whether it's creating a ticket, it's entering, you know, a help desk, whatever, whatever's going on, automate it.

[00:14:44] **Carol:** If you are gonna ask me twice, just automate it. So I had a developer ask me their, like the same question twice, like two weeks in a row. Like the exact same question where something was. And my response was, if you're gonna have to ask me, I'm gonna make you write some automation so you can find it yourself.

[00:15:00] **Carol:** And, uh, we kinda laughed about it just because like, that's my go-to for everything. I'm like, if you're gonna ask me, look at it two times. It needs to be automated at this point. Everyone should just know how to find it. And it happens automatically.

[00:15:11] **Tim:** You've become me. I'm the guy who said, when he came in my office said, Tim, wonder how we fix this. Like, did you Google it?

[00:15:17] **Adam:** Yeah.

[00:15:18] **Carol:** it up?

[00:15:20] **Ben:** Sometimes though, sorry, this is a little bit of a tangent, but. Sometimes it feels like a, have you all heard the, the children's rhyme about the woman who swallowed the dog to catch the cat? To catch the mouse, you know, to catch

[00:15:31] **Carol:** Solid

[00:15:32] **Ben:** To

[00:15:32] **Adam:** I don't know why she swallowed a fly. Yeah.

[00:15:34] **Carol:** I dunno

[00:15:35] **Tim:** Perhaps she'll die.

[00:15:37] **Ben:** sometimes it feels a little bit like the solutions that people propose for some of this stuff is very much in alignment with that.

[00:15:44] **Ben:** It's like, how do, how can we automate this? Well, we can build a a, an AI tool. Yeah. But then how do we know that won't go off the rails? Like, oh, no problem. We'll just run it through multiple AI tools and compare the like three solutions. You're like, well then how do you make sure that works? Okay? You're like, well, then you'll have like a referee agent that runs the three and then compares the two against, and you're like, aren't we just constantly upping the level of complexity to make sure that the original thing is just slightly simpler.

[00:16:10] **Tim:** it feels like it

[00:16:10] **Carol:** sent him the lead in Wiki. Yeah.

[00:16:12] **Tim:** Yeah, because, 'cause we have like all these monitoring tools, you know, through, and then we've had some outages recently and I'm like, guys, how, how do we not know that this was broke all weekend? And they're like, well, the monitoring tool said everything was fine. I'm like, well, who monitors the monitor?

[00:16:25] **Tim:** Who watches the watchers? Right?

[00:16:28] **Ben:** Oh man. Four triumphs.

[00:16:31] **Ben:** Little golf clap.

[00:16:32] **Tim:** Yours is the biggest one though. Let's talk about it.

[00:16:35] **Ben:** Yeah,

[00:16:35] **Carol:** You get a whole

[00:16:36] **Ben:** what's up with that?

[00:16:38] **Adam:** Yeah.

## [00:16:38] Ben's Testing Journey Begins

[00:16:38] **Ben:** Um, okay, so, you know, the premise obviously, um, historically not a huge tester. but you know, kind of piggybacking on this idea that we're swallowing dogs to catch cats, to catch mice, I have been seeing a lot of people say, well, in order to keep the AI on guardrails, we have to give it guardrails.

[00:16:58] **Ben:** And a lot of the guardrails are acceptance testing of sorts, whether that's integration or unit or you know, what other kinds of, uh,

[00:17:06] **Adam:** End to end.

[00:17:07] **Ben:** end-to-end stuff. So I thought to myself, okay, if I'm gonna be using my application, Big Sexy Poems, as a Playground essentially for thought experiments and for ai and trying to use AI to do some of this coding, then I should start to build some of these guardrails that everyone's talking about.

[00:17:25] **Ben:** So I wanted to put some tests in place. and kind of speaking to this idea that we can start to build our own tools. I did not want to reach for some out of the, you know, like off the shelf pre-packaged solution. I, you know, I think TestBox is one of the, if not the only testing solution that people use at this

[00:17:46] **Adam:** Certainly the community, standard.

[00:17:49] **Ben:** Yeah. So one of the nice things about the AI that I have been enjoying, and the thing that I'm trying to remember to do is just to keep asking it questions that I don't have to. Think so deeply in isolation. I can think with it as a thinking partner. And so, I prompted it essentially something to the effect of I want you to have tests so that you can run these things after you've implemented a change and you can make sure that your change has not broken the application.

[00:18:18] **Ben:** I said I might very well never look at these tests ever, like I might never run them myself. I need them to be something that you can run. What's gonna be the easiest possible thing for us to build? That'll help keep you Claude Code. On track. And it said, well, if you just give me a, an endpoint that I can hit the returns a JSON payload, we'll do that.

[00:18:38] **Ben:** So I asked it to do that, and I said, okay, let's pick this one ColdFusion component as a initial thing that we're gonna test. And so it went through and then I, I was like, I got a little jealous. And I'm like, well, I kind of wanna see the test. So can you, uh, you know, can you in your, curl command, you know, make sure you add and accept HTTP header where you're asking for JSON so that it'll serve up JSON for you.

[00:19:01] **Ben:** And if I hit it directly in the browser, it'll serve up an HTML, you know, CFML page for me. and so that's how it started. And like to get to that thought from, Hey, here's some tests that it can run, was very quick, you know, less than an hour probably. then of course, as I mentioned last week, I lost then like the next two mornings to just dealing with this ColdFusion bug.

[00:19:25] **Ben:** But so finally, once I accepted that the ColdFusion bug was in place, whatever, I said, okay, let's go ahead and let's get the rest of the stuff tested. and so I've been learning about testing as I go 'cause I don't have a whole lot of background here. So let's just start with what is being tested.

[00:19:41] **Ben:** I have heard from everybody and their mother that a hundred percent test coverage is not something you ever really want to aim for. and so what I have opted to do is test a kind of the ingress layer to the core business logic. So if you imagine that we have a tiered application request comes in, it gets handled by the controller.

[00:20:02] **Ben:** The controller, you know, does some controller things, routes some stuff, and then it hands off a request to this kind of. Inner core of business logic and that's what I call my service layer. And it's in a services folder. And then internally that service layer does like only get some data from this model and some data from that model and apply some business rules and create some new records.

[00:20:23] **Ben:** so what I have decided to do is just essentially test the API that the controller speaks to. So I don't worry about any of the low level model stuff. I don't worry about any of the low level database access stuff. I don't worry about any of the controller stuff. I figure a lot of that stuff will either bubble up as I'm using the application very quickly, or it will be tested implicitly by the tests against the service layer.

[00:20:48] **Ben:** You know, if I go to create a poem that internally implies that it is checking to see that I have access to create poems and it's testing the data access to create a poem record, and it's testing the business logic to create a revision, and it's testing that I as a user only have access to certain things.

[00:21:07] **Ben:** So let's just start there. Is that the right layer to be testing in, do you think?

[00:21:14] **Adam:** you kinda lost me at one point there not that long ago where you're talking about the API that the controller uses. Are you, so you're probably not doing what you would call mocking, but it sounds like you're kind of replacing something in the stack. You know, you've got

[00:21:30] **Ben:** Okay. So, so it is doing full data access. So when the, when the, the test suite kicks off, you know, Claude Code hits this endpoint and it says, run these tests. And it, those tests are represented by a number of ColdFusion components and each one of those ColdFusion components has a bunch of test this, test that, test this other thing type methods.

[00:21:53] **Ben:** And before it does a bunch of those things, it will often create a new user account and then it will create all the data that it needs to. To create for particular tests. And those are genuinely going to the data access layer. They're creating hundreds of database records. This is all just running locally,

[00:22:13] **Adam:** of the test. It's like ceremony before the test runs, right? You're, you're saying, I'm gonna log in as this user. So first I have to put that user in the database.

[00:22:18] **Ben:** right? Exactly. and then it does it test whatever it needs to test? You know, like for example, one of the things that I try to be good about testing is the permissions model. So you can't delete a poem that is actually owned by someone else. So if you imagine that in order to set that test up, it has to create the primary user.

[00:22:36] **Ben:** It has to create the secondary user. It has to create a poem for the secondary user. Then it has to have the primary user try to delete the poem created by the secondary user and ensure that it throws a permissions error. So all of those records get created every single time that test runs. So I, because I didn't wanna do any mocking, I just felt like I wanted the application to be as core to running the way it would in production as possible.

[00:23:02] **Adam:** Hmm.

[00:23:02] **Tim:** So

[00:23:03] **Ben:** You take umbrage?

## [00:23:04] Unit vs Integration vs End-to-End Tests

[00:23:04] **Tim:** No, no, I'm trying, no, I'm just trying to get it clear in my head. I, I'm so, are you doing unit testing, integration testing, or a little bit of both. 'cause

[00:23:13] **Ben:** guess this is more like an integration test.

[00:23:16] **Tim:** 'cause a unit test would

[00:23:17] **Tim:** be like.

[00:23:17] **Ben:** say no, you're an idiot.

[00:23:18] **Tim:** A unit test would be like where, you know, you have a, is valid email function and all you're really doing in that unit test is like, is it returning true for a valid email or false for a bad one?

[00:23:30] **Tim:** That's a unit test, right? Integration test is like when a user signs up on a submit form, does it validate the input, create the user record and send the expected response. That would be an integration test.

[00:23:41] **Ben:** Right? So it's somewhere in between those

[00:23:43] **Adam:** So the way

[00:23:44] **Ben:** what's the word for that?

[00:23:45] **Adam:** the, it's, it's end-to-end tests, but worse.

[00:23:52] **Carol:** Yeah. I was leaning more toward like, you're doing almost end to end testing.

[00:23:55] **Adam:** yeah. You're just not interacting with the view layer. yeah. So the way I think about integration tests is, and there are, I think some people would argue with me that you shouldn't use mocks for integration tests. But what I do is I mock at the, at the boundary of my application, like if it has to reach out for Redis or if it has to reach out for a SQL database or make an API call, that's like, that crosses the bubble of inside my application to outside my application.

[00:24:23] **Adam:** And it, that's the layer where I apply my mocks most, like 99% of the time.so say we're, using a service that's gonna make an HTTP request to some API, I will mock the response that it gets back from the API and there's some ceremony, some hoops you have to jump through. You have to write your code in a certain way to make that possible.

[00:24:42] **Ben:** Right, like, do you guys use a framework, FW/1 or, or WireBox? What are your, you. I assume so the, the, the, my understanding is the only way that mocking actually works is when you have all this inversion of control where you hand the things that need to run, whether that's manually handing it or dependency injection wiring, handing it.

[00:25:04] **Adam:** Right. I, yeah, it's, that's a good question. I don't have a good testing story on CFML for the last 10 years. I've been on the, this is the year we're getting the F off of CFML train, so it's not worth it.so, you know, I, we do have some CFML tests. Most of them are end-to-end tests that we just do testing, like browser testing.

[00:25:27] **Adam:** so we're, we're validating the most important parts using browser automation basically, so that, you know, if you can log in and, and do certain things, then you can have assurance that those things are working and you don't have to, you know, go in and mock services or whatever. Right. That's

[00:25:45] **Ben:** Right. So that was my thought process. It was just kind of one layer down where I

[00:25:51] **Adam:** took a step

[00:25:52] **Ben:** view

[00:25:52] **Adam:** Yeah,

## [00:25:54] The 80/20 Rule of Testing

[00:25:54] **Ben:** because, so, so my thinking here was I want, I wanted to try to find, I think I even said this in the prompt for Claude Code that I wanna find the 80 20 rule, like what is the 80% of the value that I can get from 20% of the testing and not having to deal with any kind of browser automation and not having to deal with any kind of JavaScript framework for testing.

[00:26:17] **Ben:** I, I felt like a lot of those types of bugs are going to be easier for me to spot just by chance of I'm using the application locally and it will bubble up. My biggest fears are one that I open up a permissions access point that I didn't mean to, they're like, I added this thing and I forgot to do a.

[00:26:39] **Ben:** Permissions check, or there's something wonky in it. And I feel like at the very least, even if you can render a page, as long as the data can't be fetched, or even like at the very worst, like maybe a list can be fetched, but then if you try to access a detail or delete an item, like that'll still block you.

[00:26:58] **Ben:** You know, like, like there's backstops.

[00:27:00] **Adam:** this is where you have like unit tests that cover that sort of thing. So you're, you're, you seem laser focused on access control, so

[00:27:08] **Ben:** it's, it's the thing that keeps me up at night of all the types of things.

[00:27:11] **Adam:** But I guess what I'm saying is like, let's, let's drill down into that a little bit more, right? So you've got a service that's presumably doing access control checks for you, and part of that is probably hitting the database to see like what poems belong to this user, right?

[00:27:27] **Adam:** and so what you can do if you separate the data access from the service layer, right? So the, the, if you have a DAO or whatever you want to call it. Then you can inject a mock DAO using your inversion of control into your service layer, and you just have a mock response, hard coded into that. right.

[00:27:48] **Adam:** So if you're saying like, get poems for user, and like, so you just say, if user ID equals one, then return these rows. If user ID equals two, then return these rows. And that way your tests are super fast. 'cause they don't actually have to hit a database. You don't have to set up any test data. And as long as the shape of the, the data doesn't change, right?

[00:28:08] **Adam:** If you're, if you're talking about database column changes, that sort of

[00:28:10] **Ben:** Right. It's

[00:28:11] **Adam:** the, the whole stack's gonna have to change anyway. So you're, the tests have to change too. But, then, then you don't even have to involve the controller, right? You're just taking that service method or service, file CFC, and you're injecting your mock data access object.

[00:28:26] **Adam:** and you just call methods on it. Can user one access poems, delete poems from user two. And

[00:28:34] **Carol:** And everything still gets called. It just runs through that data. Yeah.

[00:28:37] **Adam:** Yeah.

[00:28:38] **Ben:** I, yeah, I mean I, it just, that just feels really complicated,

[00:28:44] **Adam:** Yeah.

[00:28:45] **Ben:** you know? It's like, it, it, it's, it's also the, the other thing to

[00:28:48] **Adam:** almost like there's a reason that people write complicated code.

[00:28:52] **Ben:** the other thing to consider there, it also is that the, um, maybe this is not the way to go about some of this stuff, but the, the way I have it working is that the test framework itself, by framework I mean like the two files that are involved here, are, are actually executing as part of the same same ColdFusion application that the rest of the app is.

[00:29:15] **Ben:** So like they have all the same dependency injection and all of the same, uh, path mappings and stuff. Yeah. So if I were to mock something out, I think it would get a lot more complicated. Like I'd have to have more of a separation between the execution context. Otherwise, I, I don't know. I don't know how, like, I don't have the experience there, but it feels like we get more complicated.

[00:29:36] **Tim:** But I mean, you're learning, right? So I mean, don't, don't, don't discount, you know, small steps in the beginning. I, I think one thing I ran into, I asked. The LLM, you know, I have a working app, it works fine. How can you help me make my code more testable? So you went about it. Hey, I want to test some stuff, build me some tests and I don't really wanna mock things.

[00:29:58] **Tim:** And did may, maybe another exercise to do is to say, Hey, I have this, this, this control, or, and I wanna make it more testable. What suggestions do you have that I can make this more testable? It's probably gonna mention things like Adam was saying about dependency injection and inversion of control, using a DAO, things like that.

[00:30:16] **Tim:** and, and see where it goes from there.

[00:30:20] **Ben:** Yeah. I'm trying to get Claude to point me in the right direction. What I am finding, and this is maybe, being too influenced by what I've heard other people say, is that ultimately the, the, the LLM still wants to be not sycophantic the way it used to be. It is very persuadable in a given direction. So what I find often is that it will push back against something and say like, Hey, you should do this.

[00:30:51] **Ben:** And then I'll push back against its pushback and be like, but what about this? And it'll often say, and I, I don't, not to credit my own massive intellect here, but it will often say, oh, that's a good point. Yes, that's a very pragmatic trade off. You can probably, you're like, you're doing the right thing.

[00:31:08] **Ben:** But I'm like, yeah, but are you just saying that? Yeah. Like, are you saying that because I tried to lay out an argument and now you're just telling me my argument was good.

[00:31:16] **Tim:** Ben. Ben says, Claude, that makes my tumtum feel funny.

[00:31:19] **Tim:** And like Claude's, like, I'm sorry. Let me water it down for you.

[00:31:25] **Ben:** you

[00:31:25] **Adam:** I do think Tim has the right idea though. Like your first exercise was, I think a good place to start. But then the next exercise is, you know, okay. How could I write the code to make it easier to run, more focused, faster, simpler tests, right? Simple is good.

[00:31:41] **Ben:** So, okay, so here's something where I did then hem and haw a little bit about what simplicity means because Okay. If you can imagine, going back to the permissions idea, just 'cause I feel like it's very concrete and people

[00:31:52] **Adam:** Have you heard of Rich Hickey? Simple Made Easy? No, just go ahead. Keep going. Keep going.

[00:31:58] **Ben:** So, okay. If you imagine, here's a poem, you can read that poem, you can update that poem, you can delete that poem. You can do that for your poems. You can't do it for other people's poems,

[00:32:09] **Adam:** you perform it? Do you have like a karaoke mode where it

[00:32:11] **Ben:** there is actually speech features, but those are client side and they sound terrible. Why is it that all of the automated voices in the browser are just

[00:32:21] **Carol:** So bad. It feels like the cheapest experience ever.

[00:32:25] **Ben:** Right?

[00:32:26] **Ben:** Anyway,Okay, so you have these three access permissions. So when it ran the first time, when I said, Hey, generate the test for this poem service, it went through and it created a test. Like, here's the one for testing. Can you view a poem that someone else has owns? Here's the test for whether or not you can update a poem that someone else owns.

[00:32:44] **Ben:** Here's the test for whether you or not, you can delete a poem that someone else owns. And I said like, what are you doing for each one of those? You have to set up users. Like you have to set up the two users. You have to set up the poem, and then you have to run the test. I'm like, why not just run all three of those in the same test?

[00:33:01] **Ben:** And it was like, well, traditionally smaller tests are easier to debug and it becomes more clear when something goes wrong. And I was like, but the, like the, the stack trace is gonna tell you where it went wrong.

[00:33:11] **Adam:** It's because you're writing end to end tests.

[00:33:13] **Ben:** Is, is that, is that the problem?

[00:33:14] **Adam:** Yes. Because if you were doing integration tests or unit tests, you would just have mock data or, so I think the difference in my brain between a unit test and an integration test is an integration test requires injecting some other object, right? So like the DAO in that, in that case that we talked about before, where a unit test is the only inputs are like the function arguments, and it's a like a pure function. So,

[00:33:45] **Ben:** So I, I got it to collapse, within reason as many, as many edge cases into a single test unit, you know, like as a test method, as it could, like anything that was, especially anything that wasn't destructive. I'm like, if you can jam it into an existing test method, just do that. because again, like if it throws an error, it throws an error, I'll have the stack trace.

[00:34:07] **Ben:** Like that's not, the clarity for me is not a concern.

[00:34:11] **Adam:** this is a well known pattern in end-to-end testing.

[00:34:13] **Ben:** Okay. All right. So that's good to know. That's good to know. And so this is also something interesting, right? Because I, I look at the Claude Code output and all I can for something like this where I don't have a lot of good experience with testing, all I can go with is my tum.

[00:34:30] **Ben:** And whether or not it tells me something's right or wrong, right? So I could have easily just looked at that and said, oh, here are all these test methods. Okay, that looks fine. It's testing what it needs to test. not knowing that that's more of a unit testing methodology and not so much a integration testing methodology.

[00:34:45] **Ben:** So I pushed back because it just feels weird. It doesn't feel efficient, it doesn't feel right, but I could just have easily left it alone, and I'm not, there's no greater thought there other than to say. It's very easy to just accept a code if you don't know any better.and that's something that I'm constantly thinking about as well, because I'm just not ready to give up knowing about the code, at least in the o in in this, in this application that I feel very deeply connected to. All right. So I got these tests work in and I started to run, you know, so we started with one service and then it added more services. I have like eight or nine different test suites now. Mo mostly like, it's a one-to-one mapping between the service or the orchestration components and the test. and then at one point I got to where I hit run and all of a sudden I started running errors, getting into errors because of my, rate limiting because there are a couple of workflows in the app that you can't do too many times because it wants to make sure you're not doing something malicious.

## [00:35:41] When Tests Hit Rate Limiting

[00:35:41] **Ben:** So, I, I very briefly thought about maybe can I mock the rate limiting? So rate limiting is handled by a particular ColdFusion component that I inject into a couple places and invoke. So I still thought could I mock that out? But then I quickly realized that that was gonna be just a whole different level of complexity that I wasn't ready to take on at that point, as per earlier in our conversation here.

[00:36:07] **Ben:** so what I decided to do was when the test runner starts, it creates a request variable, I think it's called, like request is test run. And then I have a request metadata component that just is like a nicer abstraction over some of the CGI and the HTTP headers, like things that just allow me to access that data.

[00:36:28] **Ben:** So I, I, in the request metadata, which I can inject as a dependency, it has an IS test run that looks at that request scope variable that only ever exists if it's running as part of the test

[00:36:39] **Adam:** Mm. Yeah.

[00:36:41] **Ben:** And so I kind of begrudgingly went into the re into the couple parts of the application where I have some of this stuff.

[00:36:48] **Ben:** I wrapped this is test run condition around the rate limiting. there's also a couple places where I do some additional logging as a safeguard and I was noticing that was just creating a whole bunch of logging during the testing and I'm like, that's creating noise. I don't want that noise. So there's a couple of places where I'm gonna say unfortunately, 'cause I really didn't want this to happen, but unfortunately the very notion of testing did kind of leak into parts of the application.

[00:37:18] **Ben:** And I didn't love it. But I also, again, going back to this 80 20 rule, I'm like, what's the simplest thing I can do? I, I'm gonna let the app know that it gets tested occasionally for a few edge cases. And that felt okay.

[00:37:32] **Adam:** So let me throw this at you for thinking about rate limiting specifically.

[00:37:36] **Ben:** Yeah.

[00:37:38] **Adam:** I don't know how your implementation is done, but the first thing comes to mind for me is you have like a, at the top of your CFC that's implementing the rate limiting you have like a, this is the limit per hour, minute, whatever your window is, right?

[00:37:52] **Adam:** and presumably zero means unlimited, right?

[00:37:57] **Ben:** It, it could,

[00:37:58] **Adam:** 'cause it, it would, I mean, otherwise it wouldn't be useful, right? If zero is an actual limit, then,

[00:38:02] **Ben:** right, right. Yeah. Yes, yes,

[00:38:04] **Adam:** So, so zero should mean unlimited. So what your tests should do is just while the tests are running at runtime or like, you know, in, in runtime, just change the rate limit to zero so that you don't have to worry about rate limiting during the test runs.

[00:38:18] **Ben:** So, okay. So that was the other thought that I had, along the, okay, this is the beauty of dependency injection is that you have all these components getting injected into each other so you can have these nice abstractions. And so the thought that I have was. Where do I want the abstraction to collide with the notion of the tests?

[00:38:39] **Ben:** Because I have the rate limiting service and then I have a logging service. And right now the places where I don't want those things to happen, I kind of go up the level and be like, okay, where the rate limiting is called to this testing check where the logging is called do this testing check. And I did think, well, it maybe it would actually be cleaner to just do those at the lower level, like actually inside of the rate limiting component.

[00:39:06] **Ben:** Do like a short circuit anytime rate limiting is called if I'm in a test run, exit out immediately, you know, with like a pass or whatever

[00:39:14] **Adam:** Sure. Yeah.

[00:39:15] **Ben:** like if this is a logging call and I'm in a rate and, and I'm in a test run, just immediately exit out.so that the calling code looks perfectly, you know, high fidelity.

[00:39:26] **Ben:** This is exactly how this code's gonna run in production. And presumably if you're mocking out services, that's the same kind of benefit you get. It looks like this is exactly how the code's gonna run. It's just that some of it's mocked and some of it is real. And there was something like sneaky, I dunno, like it, it felt, it felt not obvious that if something was gonna break, it would not be obvious to me why something was breaking or why something was not working the way it was.

[00:39:55] **Ben:** Seeing the test concept be called out in the orchestration layer itself just felt like. It would be easier to maintain over time. I'm not convinced of that. I'm just saying that's the discussion that I was having in my head. But I guess you could argue the same thing for mocking, that if you mock something and there's like a funky logic in your mock,

[00:40:19] **Adam:** Yeah,

[00:40:19] **Ben:** run into the same issue maybe.

[00:40:21] **Adam:** for sure. But the,

[00:40:22] **Carol:** pass. That really shouldn't pass if you don't mock it. Right.

[00:40:26] **Adam:** yeah,

[00:40:27] **Adam:** tests are inherently, at least just a little bit fragile,

[00:40:30] **Ben:** Yeah, a

[00:40:31] **Adam:** you're writing code to check other code, and like Tim said earlier, who watches the watchman, right? Like you, that's your job that

[00:40:37] **Ben:** right.

## [00:40:37] Testing Code With Side Effects

[00:40:37] **Carol:** Well, one thing that gets me is when I'll see a PR come in and someone will have taken like a private method and they've turned it now to like protected all because they're trying to add test coverage on it, and I have to go, well, let's go back a level like why is the public that's calling it not going in there?

[00:40:57] **Carol:** Like what, what logic is preventing you from being able to test it? Like, is what you're calling so complex that you can't get there? Or is that so complex that you really need to test it separately? If so, we really need to talk about, like what Tim said earlier, how do we make the code more testable instead of just exposing

[00:41:15] **Ben:** Yo. Okay. So it's actually really interesting you bring that up because I did run into almost that exact scenario.

[00:41:22] **Ben:** One everybody

[00:41:23] **Ben:** yeah, one of the workflows that I was testing was the, I, the application doesn't really have a signup process. You enter your email and it sends out a magic link. So Magic link for anyone not familiar with this, you, you send an a link to someone's email and that link.

[00:41:43] **Ben:** Affords them some sort of special access to your application? In this

[00:41:47] **Adam:** it's got a GUID in it or

[00:41:48] **Carol:** Yeah. In the

[00:41:49] **Ben:** it's got stuff and it's, it's signed cryptographically with a private key so that when you click the link, come back to the application, you can essentially regenerate the signature based on the URL parameters to make sure that the URL has not been tampered with.

[00:42:05] **Ben:** it's ba basically how like a S3 pre-signed URL works, if anyone's worked with those. now the problem is I'm testing at the orchestration layer, so the orchestration layer. Encapsulates all that logic. You say, here's my email address. Then the orchestration layer generates the, the magic link sends out the email.

[00:42:26] **Ben:** And then the next thing that the orchestration layer would do is accept the click from that magic link where it gets all the URL parameters and it passes it back in. But I didn't wanna like start dealing with URL parsing and then also going back to this idea that some of these tests have side effects.

[00:42:43] **Ben:** If I call the verif, like request magic link, it sends out an email, like it wants to send out an email. So I either have to go into that and wrap that part in the, like don't send the email if this is a test run. and so what I decided to do, exactly what Carol was just talking about, instead of sending out the email and like actually calling that high level method, I factored out into a public method that really never gets called publicly.

[00:43:09] **Ben:** The thing that actually does the signature generation so that I can take. The signature generation kind of pulled that into the, to the test suite itself, and I kind of step over the fact that a link gets called and I'm, I'm not explaining it well because I don't quite remember all the details, but it was, again, one of these things, like there were too many side effects that I would have to monkey patch around that I'd rather just like test the things around it and hope that the email send never breaks.

[00:43:37] **Adam:** Tests

[00:43:38] **Carol:** I feel like,

[00:43:39] **Adam:** Yeah.

[00:43:39] **Carol:** I feel like a lot of what you're saying is why people stop testing. It gets very complicated and they give up.

[00:43:45] **Adam:** not to turn this into an AI topic, I mean, we're so close to not having an be an AI topic, but man, isn't AI just the best teacher, right? Like so many, I, I have found AI to be like a cure for my ADHD. you know, I'll, five years ago if I was working on a problem and it got really hard, especially like, okay, I don't find anything on Stack Overflow.

[00:44:10] **Adam:** I don't, you know, I can't find it in the docs. I'm just kind of stumped and I'm like either digging through the source code myself or yeah, like about an hour or two into that, like banging my head process, I'm like, you know what? Screw this. I'm not doing this. Like, sorry, it can't be fixed. like, you know, 80% of the time, unless I have that 20% drive to, to go get it.

[00:44:29] **Adam:** But man, that's a perfect scenario where you just like throw it at Claude and you're like, okay, here, you know what's wrong? Why doesn't this work? And, and not only do I want you to fix it, I want you to teach me. And, and so like you can apply that same approach to what, you know, I'm getting stuck with like this testing.

[00:44:45] **Ben:** I'm trying to accomplish this, this is the difficulty that I'm running into My friends tell me I'm writing end-to-end tests when I thought I was writing integration tests. What's wrong with my friends?

[00:44:56] **Carol:** What's wrong

[00:44:57] **Adam:** Where can I get some new

[00:44:58] **Carol:** you just say that?

[00:45:02] **Ben:** No, it is true. I, that's, that's like, you

[00:45:05] **Adam:** you, there's something wrong with us.

[00:45:07] **Carol:** I know

[00:45:07] **Ben:** say, it's the, the, you know, as much as people tout the, oh, I can now generate 10 times as much code as I used to, I, I, I work at a much smaller scale. So even though I'm having a generate code, it's more like generate this one view file and this one controller, and then I will look at it anyway.

[00:45:26] **Ben:** what I'm finding, like the real value add is in the the thinking partnership. The, here's what I wanna do, come up with a plan. Okay, now I'm gonna review the plan and I'm gonna tell it no, I want this thing to work differently. And it asks me clarifying questions that. That to me is the like, oh, here's the one edge case I never thought about.

[00:45:46] **Ben:** Or like, oh, I didn't think that that would happen. That's a good thing we should consider. Or, or even just the like, no, that's outta scope. I don't care about that. We'll maybe do that sometime in the future kind of a thing. Just add a note, you know, a to do comment or something.

[00:45:58] **Adam:** Right.

[00:45:59] **Carol:** Well, just a little tangent with ai, right? So what you said is great, but it also takes away from some of my joy. So like today I was on a call with a developer and I was looking at a problem that he's having, and I kind of got to the root and I wanted to explain it deeply, but I only had like 10 minutes free.

[00:46:18] **Carol:** So instead of trying to go through and explain like why these models can't talk to each other, like why you can't get one piece from the other, like there's no connection. I was like, you know what? I'm gonna help you write the correct question and Codex so it can. Now generate a response and help explain it to you better.

[00:46:38] **Carol:** Like, because I don't have a an hour to sit here and just teach you. I have to hand it off to someone. And it kind of broke my heart a little that I've lost that like learning opportunity and like teaching opportunity. And now I've just handed it off to, you know, I feel like we're in a movie where I'm making someone fall in love with a robot, you know?

[00:46:57] **Adam:** I, I hear you actually, I, I bumping her up to the top of my watch list is, is definitely something I need to do. I still haven't seen that, but,

[00:47:05] **Ben:** a good one.

[00:47:05] **Adam:** the, as you were describing that Carol. I was thinking of it as a positive, right? You were, instead of giving a man a fish, you were teaching a man how to fish.

[00:47:13] **Adam:** As the saying goes, like you, like, this is a, a question that an LLM can answer for you. So let me teach you how to ask it so that you can ask that instead of asking me, and then you don't have to wait for me.

[00:47:24] **Carol:** Yeah. It, it is a good teaching opportunity there, but it does take away that one-on-one connection you get with your team now. So.

[00:47:31] **Adam:** Which, I mean, A, it's saving you time. It's saving them time. It leaves more time for, uh, work, happy hour for

[00:47:39] **Carol:** Oh yeah. Yeah.

## [00:47:41] Trading Claude Skills and Markdown Files

[00:47:41] **Ben:** okay, so,here's something I've been struggling with along the lines of, of teaching and learning up together. Historically, when I saw someone write code. It was really fascinating to see techniques and syntaxes that I hadn't seen before. Like, oh, it's really interesting that you solved it that way.

[00:47:58] **Ben:** Or like, oh, I didn't know the language could do this. Or, oh, I've never seen this library before. This looks really cool. It's something I feel like I wanna spend some time looking into. That feels very different than looking at all of the markdown files that Claude Code has generated. You know, there, there seems to be a whole marketplace, and I'm using marketplace in like the marketplace of ideas, not in the like marketplace of eBay kind of thing.

[00:48:27] **Ben:** Like there's this whole marketplace of ideas of, you know, here are all my markdown files for skills and here's like the Claude Markdown file I use, and here are all my rules and here's how I do MCP servers and. It's very challenging for me to consume that with the same mindset that I would consume code, where I'm looking at like, oh, you wrote this here.

[00:48:49] **Ben:** Oh, that's fascinating. And then quickly remembering like, oh no, actually the person didn't write this. They prompted Claude to write this markdown file and now 400 lines of markdown later. There's some rule that does, you know, analysis of your application. And that analysis was built against a particular application.

[00:49:10] **Ben:** It was refined against a particular application, and it suited the particular needs of the developers working on that application. And because the LLM is so non-deterministic, like I can't just lift and shift like, oh, here's the front end skill you used for your application. And like, I'm just gonna use that front end skill.

[00:49:30] **Ben:** But like, I don't use your front end library and I have different methodologies and I have different paradigms and different patterns and et cetera. Like. I'm, people are treating these markdown files as like, oh, here's the asset that we can trade around and like, here's how we can learn from each other.

[00:49:46] **Ben:** But I, I am not convinced that that is the case.

[00:49:49] **Tim:** I think there's an underlying, when I get an email from someone that I can tell, they obviously copied and pasted from ChatGPT, I look at it with a little bit of disdain.

[00:50:01] **Ben:** Yeah.

[00:50:02] **Tim:** Because, I mean, because, and I, and I, I mean maybe that's, that's probably a wrong thing to do, but it's like, 'cause they're trying to, humans aren't that impressed with information transfer.

[00:50:13] **Tim:** We're interested in value. Right? And so there is just a natural, either we're gonna have to just stop doing that or find other ways to find value because you're like, well, you obviously didn't work on this very hard. You, you did a really nice prompt and it came out with some good stuff. I'm just gonna peruse this.

[00:50:30] **Tim:** Or I might just throw it back into

[00:50:32] **Carol:** I'm gonna throw it back

[00:50:34] **Tim:** and say, summarize this for me. Right?

[00:50:37] **Carol:** You guys talk to each other?

[00:50:39] **Tim:** There, there's less, there's obviously less. We, we value when someone's worked really hard and we want to reward them for working hard. Right. But whenever we know, well, they kind of use a shortcut, same shortcut I use every day, you know, but I judge you a little harder than I judge myself.

[00:50:56] **Tim:** So, so I, I don't know how we're gonna get around that human nature thing and saying, oh, well this is obviously AI generated, so I'm not gonna, I'm not gonna spend my valuable human time reviewing it. Since you used valuable tokens to do it.

[00:51:11] **Carol:** back to your kind of skills comment. My thing right now is I'm on the same side as you are. The skills I've created, I just sat with my whole team and was like, no, you can't have my skills I've created because I don't think they're useful for you. And I feel like if you don't understand what I was trying to accomplish, they're probably gonna send you down the wrong path.

[00:51:31] **Carol:** So until I know that they're useful to, like for anyone, I'm not sharing them. Like my skills are my skills and I'm keeping them. And it's not like stingy, it's just. I feel like they're gonna take something I've done and said, oh, the architect is doing this, so this is what we do. And in reality, I took a best guess and created it with AI and I think it's working.

[00:51:51] **Carol:** And until I know it's wrong, I don't know. It's wrong.

[00:51:53] **Tim:** Or they blame your skills, like, well, I used your,

[00:51:56] **Carol:** Yeah, exactly. Yeah.

[00:51:58] **Tim:** and it didn't work. So something must be wrong with yours. Fix it.

[00:52:01] **Adam:** Are you, have you guys ever played the game? Bop it

[00:52:03] **Tim:** Yeah.

[00:52:04] **Ben:** I don't think

[00:52:05] **Carol:** I

[00:52:05] **Adam:** So it's it's this toy? Yeah. Yeah. It's this toy. You start it and, and it gets faster and faster like a Simon, right? Simon is the, it is got four different color pads and you touch 'em and you follow the order. This game, instead of lighting up lights and you have to tap 'em in that same order, it's, it speaks to you, it says bop it, and there's a, when it says bop it, there's an action you have to do that's like smacking it, or there's a, it'll say twist it and you have to twist it.

[00:52:26] **Adam:** There's a handle that

[00:52:27] **Adam:** you twist or whatever, right? And there's, there's all these different things. There's like four or five of them.and it just gets faster and faster. I feel like that's exactly what Carol's describing. Like I have built myself a bop it, and it works for me because I understand how it works, but like, I'm not ready to hand this off to you because it might say, bop it and you're gonna twist it, right?

[00:52:44] **Carol:** Right.

[00:52:45] **Adam:** Uh,

[00:52:46] **Ben:** almost like the, the, the skill is not the skill. The skill is learning how to build the skill,

[00:52:53] **Adam:** Or learning how to use it. Yeah.

[00:52:55] **Ben:** like looking at an existing database schema doesn't necessarily help you learn how to think about. Schema design and data access patterns and like why this column is indexed in this column isn't indexed.

[00:53:08] **Ben:** You know, like that's, that's the thing you learn from doing. And my concern about trading in MCP servers and skills and example Claude files is like, you're not learning the learning, you're just using, and I'm, you know, then what happens when the next, model is released and that skill no longer seems effective, or, I don't know.

## [00:53:31] Test Suite Performance and Request Timeouts

[00:53:31] **Ben:** All right. All right. We went down a little bit of a tangent. I want to get

[00:53:34] **Carol:** Gosh, every time.

[00:53:35] **Ben:** two more, two more small things relating to the testing. so one thing that Claude had suggested was, oh, these tests are probably gonna take a really long time to run. So we should probably increase the request timeout.

[00:53:50] **Ben:** I think the default request timeout for the application is like 20 seconds or something. I don't remember what I haven't said to, so I think it started out like setting it to 60 or 300, it did something like crazy. And at first I was like, okay, yeah, that makes sense. But then I did a, a 180 on that sentiment.

[00:54:07] **Ben:** And what I've remembered is that over the course of this podcast, I have often ranted against the idea that like, Shopify's tests take 170 minutes to run or whatever crazy nonsense it is. And like, I don't want to allow testing to run the show. Like testing still has to live in my domain. And if anything, the request timeout for my test should be as small as possible so that the moment testing starts to take longer than I wanted to.

[00:54:38] **Ben:** Like I want to know about that and I wanna see if there's something I can address. So I don't think I went crazy. What.

[00:54:45] **Adam:** Mocks.

[00:54:48] **Ben:** But, mocking aside. So I did go back in and I think I said I set the request time out either to be the same as the default or maybe even lower. and the truth is the whole test suite runs in about 250 milliseconds right now. Complete with like hundreds of database record creations. 'cause it runs locally, it's super fast even though it's in Docker.

[00:55:06] **Ben:** that said, and this is the final thing I wanted to mention at first, I think when we talked last week and I said, oh, I'm just gonna have it run against the database. I'm like, it's just development. I don't care if it creates a whole bunch of records. the moment I opened up my database GUI and I saw those hundreds of records being created, I was like, oh, that's not good.

[00:55:24] **Ben:** So,and to be fair, I, I do think that it does cause some issues in Docker once you have really large databases 'cause of the way the, like the virtual discs get allocated. I might be making that up, but, what I did, I, I built a second kind of little, nuclear detonation button, which deletes basically finds all the users that it created and then it loops over them and it deletes all of their data using the business logic, which actually turned out to be a good move because now it allows me to test the cascading delete of users.

[00:55:57] **Ben:** and I learned, I said, okay, I, I know from experience that if you delete a bunch of rows and then you create a new record that new records, primary key starts off right where the last empty row was. And I said, is there a way that I can do that so I'm not just constantly creating these massive primary keys over time?

[00:56:15] **Ben:** and it said, if I call optimize, and this isn't a MySQL thing specifically, I'm sure this exists to some degree in other databases. That if you call optimize it, like rebuilds the table structure underneath and kind of collapses the pages that it uses to store the data and does some of the primary key compaction.

[00:56:34] **Ben:** so I use that for the very first

[00:56:36] **Tim:** system down

[00:56:36] **Ben:** Yes, yes. It is not an online, it is not an online transformation as MySQL told me, but that was just exciting 'cause I had never used that before and this was just like a fun excuse to be able to try something a little bit new. You basically say like optimize table and then give it a list of table names.

[00:56:53] **Ben:** and it just rebuilds them under the hood. I think it locks access to the table while that's happening. 'cause it's doing a bunch of,

[00:57:00] **Tim:** which is why it takes down your system.

[00:57:01] **Ben:** yeah, it's doing a bunch of rejiggering of where things live. But it was just a fun little, uh,

[00:57:07] **Adam:** Is that the one that like will change IDs, but if there's any references, it, it updates the references as well. Just like if you, if you have row one and three because two got deleted and you say, okay, optimize will it. Move three down to one. But then there's this other foreign key that's referencing three.

[00:57:22] **Adam:** So now it has to update that foreign key to be two,

[00:57:24] **Ben:** I don't know that this, I think is really just about the, like the, it's almost like a disc defragmentation.

[00:57:32] **Adam:** Yeah.

[00:57:33] **Adam:** Okay.

[00:57:34] **Ben:** But that sounds fascinating. Whatever you just

[00:57:36] **Adam:** I, I'm, as a large language model, I can't

[00:57:41] **Tim:** He hallucinated that

[00:57:43] **Adam:** Yeah.

## [00:57:44] Should You Review AI-Generated Tests

[00:57:44] **Ben:** So, okay. One final thought that I have is, when I heard other people talk about testing, there was one, you know. There, there were two camps. One camp was the, how awesome is it that the LLM can generate tests. We never have to think about testing again. This is awesome. The other camp was, that's the craziest thing I've ever heard.

[00:58:04] **Ben:** The tests are the safety guards of your application. You should 100% understand how your tests are working, and you should definitely review every single line in your test to make sure that your application is, maintaining a degree of integrity. And, I, I wanted so badly to be in the second camp that, like, how important is it that these tests, like, they're, they're hand coded and they make so much sense.

[00:58:26] **Ben:** and like the moment Claude started generating tests, I did everything that I possibly could to convince myself to review that code. And I still have not reviewed it because I just, I just can't care. I'm like, I, like, I glance at it, I'm like, it looks fine.

[00:58:42] **Tim:** I think you need a little more time.

[00:58:45] **Adam:** Honestly, there, there's like a two or maybe a three part thing going through my head here. So, for the longest time that I can remember, people have been like, not necessarily saying manual testing is incorrect in that like it can't find problems and or it won't find problems. Just that it's inefficient, right?

[00:59:03] **Adam:** Manuals like, go open the browser, click it yourself, type in the field yourself.however, what what I'm thinking about is like, is manual testing enough to verify that the tests are working, right? So you've written a, hell, maybe you had Claude write the code, you had Claude write the tests, and, and you do manual testing to like, okay, the, at least the happy path is working.

[00:59:23] **Adam:** Let me try a few things that are wrong. And then you go to Claude and you say, okay, everything looks good to me. Can you find any edge cases in features that aren't tested? And like, let's write test for them. And then how can I, how can I manually test that?

[00:59:35] **Ben:** So

[00:59:35] **Ben:** okay. And then one thing that I also forgot here is, at the end of all of this, I did try to start working on a skill, like a Claude Code skill that is like a reconciliation of tests against the application. And I think it, I, I, you know, I worked with Claude to build this, and again, it's just a markdown file.

[00:59:53] **Ben:** It's not like it's doing anything concrete, but it, I think it runs in two phases where it basically says like, look at all the components in my service layer, my orchestration layer, and then look at the test suite. And if there are any methods that don't appear to be tested, let's create tests for those.

[01:00:10] **Ben:** So I'm, I'm hoping that when I did this initial launch and I had to create nine different test suites, testing, just felt, I mean, the reviewing of the testing felt overwhelming because there was so much, so quickly. But if I'm incrementally fleshing out the application and now I add this one method, and now I run this suggest test skill and it says, oh, this one method isn't being tested, here's a test for it.

[01:00:34] **Ben:** Like, that'll be so small in scope that I will then actually start to review these to see if they make sense. And I'm sure again, like 95% of the time, they're probably gonna be perfectly fine. And maybe I catch one thing that's weird or just one refactoring that I wanna do. But, I'm hoping that as I'm just working on a smaller scope, I will be better about the reviewing because I really do wanna actually review the tests.

[01:00:57] **Ben:** I feel

[01:00:57] **Tim:** I have, I, I have faith. You're gonna build that muscle memory.

[01:00:59] **Ben:** I hope so. And that's it. That's, that's my testing story so far. Thank

[01:01:06] **Adam:** Yeah. Proud of you. Here's a treat. What is that? What, what would be a good treat for you, Ben? Like, here's a movie ticket or,

[01:01:13] **Ben:** do, you know what I've been enjoying lately? Has anyone ever had a mochi? It's like an

[01:01:18] **Tim:** Uh, you like it really?

[01:01:20] **Carol:** Mm-hmm. They're so good. So good.

[01:01:23] **Ben:** I, I think the thing around it sounds disturbing. It's like a bean paste or something. It's kind of like a fondant texture.

[01:01:29] **Tim:** tried to like it so much.

[01:01:31] **Ben:** Oh, that's

[01:01:32] **Carol:** So good.

[01:01:33] **Adam:** Never even heard of it.

[01:01:35] **Ben:** It's like a, if you could, it's like a, it's like an Asian version of a bon bon.

[01:01:41] **Tim:** Mm. Yeah.

[01:01:44] **Adam:** Okay.

[01:01:45] **Ben:** I dunno. I've been

## [01:01:46] Patreon

[01:01:46] **Adam:** Alright. And you know on, that's a perfect place to wrap it up. On that note, this epi working code was brought to you by my new toy coming to stores near you. It's called Mock It. And it goes, mock it, inject it, test it, nuke it.

[01:02:02] **Ben:** I'll have to look this up. What it is called bop.

[01:02:04] **Adam:** Yeah.brought to my, my new toy. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[01:02:20] **Adam:** Special thanks to our top patrons, Monte and Giancarlo.

## [01:02:23] Thanks For Listening!

[01:02:23] **Adam:** And hey, while we're on the subject, thanks for paying for those transcriptions. They helped Tim's son get, uh,

[01:02:29] **Tim:** from last

[01:02:29] **Adam:** his, uh, fake podcast episode last week.yeah, so, uh, we're gonna get outta here. outro music's gonna play. We're gonna stick around and we're gonna talk about the after show.

[01:02:38] **Adam:** and we got a bunch of stuff on the list here, mostly from me, apparently. but we got a bunch of stuff to talk about. and if you want the after show, you're just gonna have to go to patreon.com/workingcodepod, throw a few dollars our way, and we'll hook you up.that's gonna do it for us this week.

[01:02:51] **Adam:** We'll catch you next week. Until then.

[01:02:54] **Tim:** You know, some say God gives his hardest test to his strongest warriors. Ben Nadel gives his hardest end-to-end test to wherever he swears is pretty straightforward. And your heart matters.
