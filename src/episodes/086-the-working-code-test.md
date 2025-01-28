---
title: "086: The Working Code Test"
description: "This week on the show, the crew reviews The Joel Test."
date: 2022-08-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/086-the-working-code-test/id1544142288?i=1000574879560"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Twenty-two years ago, [Joel Spolsky][joel-spolsky] wrote an article titled, [The Joel Test][joel-test], which outlines 12-steps for evaluating the quality of a software team. At the time, Joel was working with Microsoft, building products that were delivered on CD-ROM. As such, his day-to-day workflow was somewhat different than the kind of work many of us are used to doing today. That said, much of what he had in his 12-point litmus test still holds true! Which I believe is a testament to how fundamental his insights were. This week on the show, the crew reviews Joel's list, gives each item our personal _Yay_ or _Nay_, and then adds a few requirements of our own.

Also, if you want a quick run-down of what we discussed, Adam summarized much of what we talked about in [The Working Code Test][adam-tuttle-test] over on his blog.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-tuttle-test]: https://adamtuttle.codes/blog/2022/the-working-code-test/
[joel-spolsky]: https://www.joelonsoftware.com/
[joel-test]: https://www.joelonsoftware.com/2000/08/09/the-joel-test-12-steps-to-better-code/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/086-the-working-code-test.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** so when I think about people who don't think about the formatting of their code while they're writing it,

[00:00:05] **Ben:** it's just like a moment where you're like, oh, this person sees the world in a way that is different than I see the world. And is that gonna become a point of friction for us? And it's a question, mark. So I forget how we got onto this

[00:00:20] **Adam:** Doesn't matter. It was. Do you have testers?

## [00:00:27] Intro

[00:00:27] **Adam:** okay. Here we go. It is show number 86, for August 3rd. And since I mentioned the date, you know, that it's important. it is going to be a couple of days from now when this, episode is released the 22nd anniversary of the Joel test, which we'll get into what that is. So we thought it would be a good opportunity to.

[00:01:03] **Adam:** Take a look back, maybe revisit it, and see what we might keep and what we might revise going forward. If we were, Kings of how you do business. But, as usual, we're gonna start with our triumphs and failures. Tim and Carol couldn't make it tonight. So once again, just me and Ben. so Ben, I guess that means I'm coming to you first.

## [00:01:20] Ben's Fail

[00:01:20] **Ben:** Yeah, absolutely. and I'm gonna kick us off with a failure, which is just that I have felt underwater lately. I had mentioned in the previous episode that we just moved into a new house and that's very exciting. But there's also just been a lot of work associated with that and just the emotional stress of settling in and unpacking.

[00:01:39] **Ben:** and, my, my network here, my network connection is not solid. So there's a little lag between, and I, if you guys hear us talking over each other a little bit, I gotta call spectrum and see if I can figure that out. And then just work has been really crazy. And, I just, I feel like I'm racing around.

[00:01:57] **Ben:** It's almost like I feel short of breath emotionally, if that makes sense. And, I just like, I just wanna a hot minute to relax. It feels like I haven't been able to relax

[00:02:07] **Adam:** Well, I think we can take care of the hot.

[00:02:09] **Ben:** oh my God. Speaking of hot, the, this heat waves are crazy.

[00:02:15] **Adam:** Yeah.

[00:02:16] **Adam:** I don't want to be, a total drag here. So I will end my rant with a small triumph, which is that I built a, a new dog bed. and when I say built, I mean, I constructed not that I carved or anything, but like Ikea.

[00:02:29] **Ben:** some yeah. I bought some, some wire Metro shelving and, I got some short poles and, you can adjust these things.

[00:02:36] **Ben:** I went to PECO and I bought a nice, big, like two foot by three foot bed. And it's like, eight times larger than my dog. And, I propped it up. So now she can get up and she can look out the window and she's sort of, chest height with me. So we have a lot of camaraderie during the day.

[00:02:51] **Ben:** And, I'm pretty excited about that. So, so that's a small victory here in the ability to,to pull a little value out of the, the failure.

[00:02:59] **Adam:** Nice seems like you, you really value spending that quality time with the dog while you're working.

[00:03:05] **Ben:** Oh, H yeah. Yeah. She's my co-pilot. That's all. That's awesome. Uh,what about you, Adam? What do you got going on?

## [00:03:11] Adam's Triumph

[00:03:11] **Adam:** I guess I'm gonna call it a triumph. so for those in the know, if you know, you know,I jumped in front of the SOC two bus and basically the triumph is I think I'm gonna live,SOC two, if you're not familiar, is a certification, it's called system and organization controls, I believe is what the, so part stands for.

[00:03:28] **Adam:** and it basically, it's a certification that you can get from of all things like, CPA that I think it's the I a CPA, the, like the international association of certified public accountants. but as a certification, you can get that you're meeting the standards that they set for this certification, right?

[00:03:44] **Adam:** So it's about security, privacy, confidentiality. There's a bunch of these,I forget what they're called, TSC trust system, whatever somethings, trust system controls, maybe, I don't know. and, basically a, it's a giant pain in the butt, way to prove. like in a B2B scenario, like a business to business, if you're trying to sell a product to a business, basically, especially if you are a SAS, a service as a software, as a service, it's a way to prove that you are doing your due diligence in terms of security, privacy, confidentiality, et cetera, et cetera.

[00:04:16] **Adam:** it's a, apparently a very laborious and, difficult and tedious process to go through on your own. There's like hundreds of questions and you have to provide all kinds of evidence of,everything from your password policy to does every developer's machine useful disc encryption to, like, our password is rotated after somebody leaves the company and there's, hundreds of these questions.

[00:04:41] **Adam:** and so you have to have policies like formal written policies on all of these different things and you have to. show evidence that you are obeying those policies and it's a whole complicated process. and of course, because of the complexity there, there's a bunch of vendors that wanna sell you compliance software in that space.

[00:05:01] **Adam:** And I've been interviewing them and working on figuring out which one I wanna go with. And,just trying to make my own life a little bit better, but basically, this was one of those situations where my CEO said, okay, we need to do this. I don't have the time to do it. Can I have a volunteer?

[00:05:16] **Adam:** And so I stepped in front of that bus

[00:05:18] **Ben:** what do you mean when you say you're looking for a vendor vendor to do what exactly.

[00:05:24] **Adam:** That's a good question. so, what they do, basically, each of these, companies that I've been talking to seems to have like a, an app, like, you and I provide apps to our customers, right? So similar idea, a website where you go in and it does stuff for you. And, you te you tend to start with a survey, that where you describe, like, what kind of business you do, what kind of data you collect from your customers and from end users, that sort of thing, and that narrows down which criteria and controls and whatever apply to you.

[00:05:55] **Adam:** and then they, will as much as possible, they try to automate checking on these things. So for example, if you use AWS and you have, cloud infrastructure and. Also if your business,deals with data in such a way that you need to have, customer data encrypted at rest and encrypted in transit, they can integrate with your AWS account in like a metadata only read only way, right.

[00:06:22] **Adam:** Principle of least privilege. so they can like read the configuration of your S3 buckets. Reading the contents of your S3 buckets, for example, so that you can say, okay, they can tell you, okay, well, you've got this S3 bucket. That's not encrypted at rest. and so that's out of compliance and you can either go in and say, okay, well that bucket in particular is only used for our internal information and doesn't need to be encrypted.

[00:06:46] **Adam:** So it's out of scope or you can, tell it that you're ready to remediate that. And it will give you the steps, like step by step with maybe screenshots in some cases, or like a deep link for you to just click on and it'll take you to the right place in the console where you can change the encryption settings.

[00:07:01] **Ben:** And it gives you a like a checklist of steps to do, to solve that particular issue. So that times probably like, a thousand and you are ready to be evaluated for SOC two compliance. so yeah,so that's intense. Yeah. I, we had to do some. We had to do SOC two stuff at work. And, I mean, thankfully the head of security, we had a security department and the head of it was the guy who was dealing with all that. And he would just pull people into the call at random times. He'd be like, Hey, I need you for 50 minutes.

[00:07:30] **Ben:** We need to talk about GitHub access and I'd go and talk about GitHub access. And then I wouldn't hear from him for a day. And then he'd pull me back into a meeting. It's like, Hey, we need to know about pull request and how many eyes get to look at a pull request before it gets merged into a production branch.

[00:07:44] **Ben:** And, yeah, so I don't know the full breadth of what goes into SOC too, but I know it was extremely laborious and,and quite intensive. So

[00:07:54] **Adam:** yeah. Yeah. Thanks. I'll have to ask you offline. if you guys, if you could find out what vendor you guys used and what you thought of them, but

[00:08:02] **Ben:** Yeah, sure. I'll I'll take a look or I'll ask around

[00:08:05] **Adam:** cool.

## [00:08:06] The Joel Test

[00:08:06] **Adam:** Okay. So I guess that brings us to our topic for the day. I'm calling it the working code test, cuz really there's this thing called the Joel test and it is amazingly 22 years old now, or it will be in a couple of days as of the release of this episode.

[00:08:19] **Adam:** it was, I guess, first published on August 9th, 2000. and it's gonna be August, third, 2022 when this episode comes out. So that's a long dang time. And I think, we should start by saying it's amazing that so much of this still holds up today. there's 12 like principles or criteria on here and just through our initial, look at it.

[00:08:44] **Adam:** I think we agree that a lot of it is totally still relevant.

[00:08:48] **Ben:** Yeah, absolutely. It, I mean, I think it speaks a bit to what is so core to being productive at work and sort of, helps separate the wheat from the shaft is that the phrase where,where the things that, a lot of, startup culture and a lot of trendiness has shine, a light on things that people think are important that maybe just aren't really relevant to being productive.

[00:09:09] **Adam:** So, I guess, let me take yet another step back here. if you're not familiar, Joel Spolsky is a former Microsoft developer. He worked on Excel and then later he went on to found his own company that made among other things Trello so long before Trello, but after Microsoft, he was like tech blog famous.

[00:09:27] **Adam:** If you were, around and nerdy at the time. and he created something that he called the Joel test, which was basically just a bunch of criteria that you could use to rate either like a company or like a software team to help decide whether or not you would want to work there. And he called it the Joel test. and so maybe do you think we should just start by reading off what the 12 criteria are and then we can come back and talk about them individually. Okay, cool. Cause I'm sure, as we get into each one of these, there's gonna be some unpacking to do of like the original concept and then we'll get into, would we keep it, would we revise it?

[00:09:59] **Adam:** et cetera. And then I think at the end, we'll probably have some, we wanna add. Okay.

## [00:10:04] The 12 Criteria

[00:10:04] **Adam:** . So here's the original 12, number one, do you use source control seems like pretty table stakes thing these days. number two, can you make a build in one step number three, do you make daily builds? Number four. Do you have a bug database, number five. Do you fix bugs before writing new code number six?

[00:10:23] **Adam:** Do you have an up to date, schedule seven. Do you have a spec eight? Do programmers have quiet working conditions? Nine? Do you use the best tools? Money can buy 10. Do you have testers 11. Do new candidates write code during their interview? And number 12, do you do hallway usability testing. okay, so that was a lot,

## [00:10:45] 1. Do You Use Source Control?

[00:10:45] **Adam:** let's I guess start back at number one. So do you use source control? I think, like I said, that's kind of table stakes these days. I it's definitely a red flag if you don't have it. I have to say, I have worked with a couple of companies that weren't initially using source control.

[00:11:02] **Adam:** Like when I was a consultant, we would be called in to do some work and it was already sold. So, we were doing the work one way or another, so we dragged them into using source control and they,once they saw its benefits, they were like, oh yeah, this is awesome. Are there other things that we should be doing too?

[00:11:15] **Adam:** And, it kind of was nice to be able to bring them in, little bit more modern. So, like on the one hand, I kind of wanna say, I wouldn't totally write somebody off if they weren't currently using source control, as long as they were willing to learn and move up. But it's definitely a red flag in terms of like how much work is gonna be necessary.

[00:11:33] **Adam:** Like if you're not using source control, you probably are gonna get a really bad score on this test.

[00:11:38] **Ben:** Yeah. Like if that's the thing that you're not doing, then I have to imagine there's many other things here that you are also

[00:11:45] **Ben:** not

[00:11:45] **Adam:** Right. Right. And actually the thing that he wrote in the original article about this is like a score of 12 is perfect. Right. So if you get yeses on all 12, that's perfect. 11 is tolerable, but 10 or lower and you've got serious problems. So that's how he originally described it.

[00:11:59] **Ben:** and I'll say that,one of the huge benefits of source control isn't necessarily the historical control, which is obviously a killer feature. but one of the ways that I use source control daily is just being able to switch ideas. you're, you have a feature branch you're working on an idea and then You get interrupted with other things or a different idea pops into your head, or you're halfway down something, and you realize it's gonna actually be a lot more effort than you had anticipated. So you wanna go back to your main thing and with source control, it's just really easy to experiment and switch ideas and quickly switch back to a clean working copy of the actual application without all the stuff you just, spent the last four hours adding to it.

[00:12:41] **Ben:** and to me, that's the, that's like the main benefit. I mean, being able to go back in history and see who did what is very helpful, obviously, but those are more like the, I don't wanna call them edge cases, but that's like the least used feature of source control for me. it's the branching and switching that I don't think I could live without it at this.

[00:13:02] **Adam:** Hmm. Yeah, I agree. what that made me think of is, okay. So when he wrote this article, what version control systems do you think were in most popular use at the time? I have some like context I can add, but I wanna see what you think, Ben.

[00:13:17] **Ben:** I mean, I'm trying to think of it in terms of jobs that I was at. And I think TW so 20 years ago, 22 years ago, well, this came out in 2000, 2000. so I actually didn't even, I hadn't started working yet. I was still in college and what's the one that has the tortoise subversion,

[00:13:33] **Adam:** Some version subversion.

[00:13:35] **Ben:** CVS

[00:13:36] **Ben:** or

[00:13:37] **Adam:** Well, I,

[00:13:37] **Ben:** is different

[00:13:39] **Adam:** so you're probably thinking of, tortoise SVN, which is like a

[00:13:42] **Adam:** client for subversion.

[00:13:43] **Ben:** Okay. So, so that was the very first source control I had ever actually seen in person.

[00:13:50] **Ben:** And that was probably like in the mid two thousands.

[00:13:54] **Adam:** Right. So, subversion itself, the very first, like before, even an official release, they just called it milestone. One was released on October 20th, 2000. So after the Joel test, so that tells me, I think, now I don't have the whole timeline of everything right in front of me, but I would guess that, I mean, definitely CVS was around, which was the precursor to subversion, just like subversion became the precursor to get in terms of like the vast majority or maybe a plurality of people are using such and such system.

[00:14:26] **Adam:** I think the biggest chunk was using CVS and then the biggest chunk was using subversion. And now the biggest chunk is using Git. Uh, so if it's not CVS, I, my guess would be, Microsoft visual source safe VSS, which was technically version control. that one was a painful one to use. Did you ever have the, the pleasure.

[00:14:45] **Ben:** I don't think so. No, I think I basically went from Tor subversion. To get those are the only two that I've ever dealt with. And,if I can just say though, I mean, look at the,the how, I mean, I don't know what the rest of the people, I don't know what, like Microsoft and other massive companies were doing, but when we were looking into version of control of the company that I was at, no one had heard of it or, if they had heard of it, it was just theoretical.

[00:15:11] **Ben:** No one had ever really played with it at all. And for Joel to come out and say that these are table stakes. I mean, just how, again, I don't wanna say it was ahead of his time. Cause I don't know what the rest of the world was doing, but definitely was a, an early adopter. It feels like of, of something that ended up being super critical to any engineering team success.

[00:15:32] **Adam:** sure. Well, I mean, he worked on Excel. he was part of the office team. I don't know what he did before that, but, operating systems and stuff had been around for a long time. I'm sure that these teams were all using like anything enterprise, like truly enterprise at that time was probably using CVS or something of that ilk.

## [00:15:48] 2. Can You Make A Build In One Step?

[00:15:48] **Adam:** Okay. I think we've talked about source control enough. So, can you make a build in one step? so what I decided for this one was I would revise it a little bit. I think that a common theme that we're gonna see throughout this discussion is that, especially, from Joel in the year 2000, he was very much, I think in the head space of somebody who's developing a binary executable, that's gonna be put on a CD and sold on a store shelf, right.

[00:16:13] **Adam:** Like Excel. And,I have no idea what the ratio is of people that still do that kind of software. Like I have a buddy who is a video game developer. And so he's doing basically that same thing. but of people working on the internet and doing like web applications these days has absolutely exploded.

[00:16:32] **Adam:** So I, I feel like that's gonna be, a major division between, categories. And as far as I am concerned, you guys are welcome to disagree with me, but as far as I'm concerned, this podcast is about web development.

[00:16:44] **Ben:** Yep. Yep.

[00:16:45] **Adam:** and so I, the way that I look at it is can you deploy to production in a single action or step?

[00:16:51] **Ben:** Yeah. I think that makes sense. It,the one step build doesn't connect with me, but getting stuff to production makes sense.

[00:17:01] **Adam:** yeah. Then, as I was writing that, I was kind of thinking like, that's true. Like, I definitely have release automation like that, but at the same time, We have a bunch of like microservices as part of our application. And so they can kind of be released separately and we don't often, like develop changes to the monolith and a specific microservice in lockstep.

[00:17:27] **Adam:** Like occasionally it happens I guess, but for the most part, it's like, okay, well here's a bug fix for the microservice or, we might make a change to the microservice that's backwards compatible. And then like, to be able to support a or B workflow while we're still using a, in the monolith and then come by once that's deployed and, replace a with B in the monolith.

[00:17:47] **Adam:** So that, I guess that's kind of like a very rudimentary approach that you could consider like a feature flag sort of thing. so I guess what I was getting at though is like, we. Can do production deploys for all of our things in one action, one step, but we don't always deploy everything at the same time, if that makes sense.

[00:18:05] **Ben:** Yeah. And I think this actually ties into, you had an addition listed in the pre-show document here, do you automate almost everything that can be automated? And I think that sort of ties into this is as much of your build and deployment process automated behind some sort of tooling I think is as a critical step here.

[00:18:24] **Adam:** Word. Okay.

## [00:18:25] 3. Do You Make Daily Builds?

[00:18:25] **Adam:** so the next one is, do you make daily builds? and what I wrote down for this one was I would revise it.

[00:18:29] **Adam:** again, I think that the lens that we're looking at this, test through has changed, and. Instead of like daily builds. So, in his article, he goes into the detail, like what he means by this thing. Why is it important? And basically what I took away from that section is that, every day around lunchtime, they run a build.

[00:18:48] **Adam:** And,if somebody checked in code that broke the build, then, that was like, oh, okay, that's the next thing that anybody has to fix. That person has to fix that problem. And they are then in charge of, babysitting the daily build until somebody else breaks it. and so for me,

[00:19:02] **Adam:** Looking at this question through the lens of web development, what I'm thinking is, continuous integration, right? Like we've talked about a couple of times recently, I'm checking in my work in progress code with its tests, and you're doing the same thing and we're making sure that my work in progress code doesn't blow up your work in progress code before either of those gets promoted to production.

[00:19:22] **Adam:** And I think that's kind of the same thing. And I think that maybe the reason this is a little bit different aside from the whole executable versus web thing is, that the cost of running these automated tests or builds if that's what you wanna call them,ha has gone down so dramatically, right?

[00:19:40] **Adam:** Like I think to build, to make a build of Excel probably was like a half hour or an hour long, script that ran. And so. You only did it once a day versus, when we do a deploy for production, it could take five, 10 minutes tops. So it's something that's really easy to just jump on and do you know, without any hesitation and whenever you, whenever you're checking a new code, right, we just kind of do it continuously.

[00:20:08] **Ben:** Right. and I think this is again where his mode of working is just so different than what most of us are used to where he's building a product that isn't shipping daily. it's, they're working towards some sort of a master release that's tied to,a CD rom or like maybe it's co released with windows or Microsoft office, I guess, would be more appropriate there.

[00:20:29] **Ben:** whereas I think the mode that most of us are used to working in is you write code and you ship it to production and it's deployed. you're not coordinating that deployment across 15 different teams that are all working in lockstep to create some massive. Product, most of us are independently to some degree working on a lot of different parts of the application.

[00:20:52] **Ben:** maybe you're over here working in the admin and someone else is over here working in billing and someone else is over here working in the nightly data sync from the customers. And, to your point earlier, sometimes that's just a lamb to function. And sometimes that's the main application.

[00:21:08] **Ben:** And sometimes it's,some SQL scripts that are being written and a lot of us, even though we're working as part of a much larger organization are working fairly independently and don't have this concept of one central bill that has to always be in a perfect working state.

[00:21:25] **Adam:** Uh, I cosign you wanna take the next one?

[00:21:27] **Ben:** uh, sure.

## [00:21:28] 4. Do You Have A Bug Database?

[00:21:28] **Ben:** Do you have a bug database and. I think what a bug database is gonna mean different things to different teams, because there's so many different technologies and software services that provide some sort of tracking. but ultimately what he was saying in his article is you can't leave it up to the minds of the developers.

[00:21:49] **Ben:** You can't have people just holding this backlog of information in their head. There has to be a recorded, list of bugs in the application. And people just have to be able to look those bugs up and not keep them inside of their head. And I, a hundred percent agree. I think this is absolutely critical.

[00:22:08] **Adam:** Oh, yeah. Total table stakes, hard cosign. And I think he goes into, in the article, he goes into some detail about some of the things that should be in that bug database, right? Like the description of the problem, the context needed to reproduce it any. Like stack traces that might be available, that sort of thing.

[00:22:25] **Adam:** So, yeah.

[00:22:26] **Ben:** Yeah. at work, we actually have our support team. Thankfully, they're the ones who enter a lot of the bugs into our bug system. and they actually have a support ticket template that they use that outlines all of the key pieces of information that you need to have in order to work the bug. And, that's been hugely helpful because they really put a lot of, screenshots and steps to reproduce and what browsers are being used and what kind of plan the user is on.

[00:22:54] **Ben:** and all of that really just makes the, the debugging and the subsequent fix so much easier to create.

[00:22:59] **Adam:** Yep. yep. No again, easy, hard agree there. So here's one where I think that, at least what we wrote down, we disagree or at least, maybe sort of partially disagree. So let's dig into that.

## [00:23:13] 5. Do You Fix Bugs Before Writing New Code?

[00:23:13] **Adam:** Do you fix bugs before writing new code?

[00:23:15] **Ben:** So I put this down as a revise and I think maybe this ties into what I was saying earlier, where we have people who work in fairly independent and decoupled parts of the application. So if there's Joe is over here working in the admin and Sally is over here working in the billing module. I don't think there's anything where Sally should have to worry about admin bugs before she starts updating billing features.

[00:23:44] **Ben:** Because those two, while they're part of the same macro product, They're fairly decoupled and fairly independent. I don't think that there should be some sort of overarching sense that we need to have a constant, like no bugs in the backlog before any of us can do any work that said, if you are working on a particular area of the application and you built something and it's buggy, and then you want to go to continue to work on that part of the application, I would say that you should probably focus on the bugs you created before you start adding new stuff.

[00:24:18] **Adam:** Okay. I think we probably agree more than we disagree. So, again, when I went back and reread that section of his article about this whole thing, what it came down to for him at the time was, I guess he related a story about. the being on the Microsoft Excel team and how the project managers at the time were like dead set on the schedule.

[00:24:37] **Adam:** we have a schedule, we're gonna stick to it. You're gonna meet your deadlines, et cetera. And so like, for example, just to try and meet the deadlines, the, it could be, apocryphal, but the story he related was that somebody, was assigned the task of writing a function that returns the height of a row in Excel.

[00:24:55] **Adam:** And do you know where this is going?

[00:24:57] **Ben:** Yeah. Yeah. Yeah.

[00:24:59] **Adam:** Okay. Yeah. and so, because he needed to meet the schedule and he could, he could deal with it as a bug later, he just wrote return 12. and so, okay, now I've met the schedule and we'll, I'll deal with the real implementation when I get the bug for it, because it doesn't work in every situation.

[00:25:14] **Ben:** I mean, to be fair, that's sort of test driven development in a nutshell right there. Right. Where you're doing the simplest thing you can to write the feature and then only coming back to change it when the test turns red.

[00:25:26] **Adam:** I mean, it's the first like step or two of TDD, but yeah, it's not the full process. That's for sure.

[00:25:34] **Ben:** I'm just, I'm just having a good time.

[00:25:35] **Adam:** yeah. Yeah, I get you. so, I, again, I took, I think maybe the reason that my gut kind of disagrees with this one is because maybe like my team or me personally, I don't pass it, which doesn't make me feel good.

[00:25:53] **Adam:** sometimes that's like, There's just bugs that are not worth fixing. Right? Like for example, I had a conversation with my team today. we have, our own support ticket table and we have like a support ticket UI built into our product to make it easy to integrate docs and, on call notifications for certain, severity tickets, that sort of thing.

[00:26:12] **Adam:** and somehow we managed to, get this far, or like 10 years into this product's life. We managed to get this far without a, a date time stamp, on the table of when the ticket was closed. We have like audit trails, like we have daytime created and we have audit logs of like every action that happened to that ticket, including closing it.

[00:26:32] **Adam:** But that's in another table and it's not just like a times stamp column you can grab right there next to daytime created. And it like, that's a bug, right. We should fix that. it's a, it's not a bug that causes us any, you. Broken functionality, but it certainly is not the way it should be.

[00:26:49] **Adam:** And it's just not one of those things. Like we agree. It would be easy to add the column. It would be easy to backfill all the existing data, but it's just not something that's worth spending our time on right now, because it's not causing any problems for anybody really like even doing some reporting on our, support tickets and finding out like, meantime to close or whatever.

[00:27:08] **Adam:** That's just, it, there's not even, a performance hit that's noticeable when you're trying to query that data out. So it's like, yeah, it's, I guess it's not right. It's not how we would design the system if we were omnipotent, but, it's not worth working on right now. And, to be fair, there's probably plenty of bugs that are actual bugs that we just haven't gotten around to yet be because of other things like deadlines and other stuff, taking priorities.

[00:27:34] **Ben:** well, and again, I think not to pick on what kind of work Joel used to do, but I think just to say that different working environments have different constraints. So if you're working to build a product that gets released on a CD or, gets released quarterly, You're really trying to hit a particular deadline that has a fixed set of features and a fixed expectations.

[00:27:58] **Ben:** But a lot of us who are working in web development where we're deploying every day, the, one of the benefits of being able to deploy every day and give new features and function functionality to the customers every day is that we have a very tight feedback loop. So we will often get feedback from customers that affects what we're gonna work on next, which we maybe didn't know.

[00:28:21] **Ben:** We, we didn't understand the importance of something until we built it. And then once we built it, we understand how to iterate or not iterate on it. and you can make those decisions. So even if you have bugs in the application, you have to weigh the cost of working on that bug versus the opportunity cost of not working on something else.

[00:28:38] **Ben:** And, again, just, if you have a product that gets released quarterly, you don't necessarily have that type of feedback. So. Very focused on a long term plant, but a lot of us are focused on much shorter term plans. And that allows us to be more agile, which allows us to be more, I don't know, maybe open-minded, I don't know what the right word is, but we're definitely, I think a lot of us have grown the muscle that allows us to live with more bugs for better or worse because we're doing other things that also have importance

[00:29:08] **Adam:** Right. No, I think you said it well, opportunity cost plays a huge role, but I think that everybody would agree that the function that just returns 12 should be fixed before you start working on, the one that returns the column with, right. Like,

[00:29:21] **Ben:** yeah.

[00:29:23] **Adam:** yeah. Cool.

## [00:29:25] 6. Do You Have An Up-To-Date Schedule?

[00:29:25] **Adam:** So the next one, do you have an up to date schedule?

[00:29:28] **Adam:** Oh, interesting. We disagree on this one too.

[00:29:30] **Ben:** I think this one ties into kind of what I was just saying, where if you're working towards a quarterly release of a CD rom you're acting under very different constraints than we have a backlog of 300 feature ideas. And we wanna see which ones connect with customers and which ones will help drive revenue.

[00:29:52] **Ben:** And we're doing experiments, with AB testing and feature flags and, we're seeing what people respond to. I mean, that's just a very different world and it's a very different mindset. and so for me, I think it's important to have people at the company who have a long term, big picture vision of where you want the company and the product and the platform to go.

[00:30:14] **Ben:** But you also have to have a lot of people who are. Very flexible and not gonna enter a death March towards a feature. As new evidence is starting to show up daily as you're getting customers to interact with the product and provide feedback.

[00:30:29] **Adam:** Okay. Yeah. I mean, I guess for me, my gut reaction to this one was more,that's just not how we do it anymore. The, when I think of a schedule, I think of like a Gantt chart. and I know there's other ways to schedule too, but, I, for me, and, again, in our business, in our industry, I think it's much more common to have a roadmap and say like, these are the things that we're working on.

[00:30:49] **Adam:** This is what's coming up next. And, there's sort of an understanding. that to some degree, things are gonna take a variable amount of time. That can be unpredictable. so I feel like a roadmap is held slightly different vehicle for the same goal.

[00:31:03] **Adam:** Although, there are plenty of times too, where, there's some trade show or some reason that you have to have certain features done and at least done enough to be able to show them off. Right. So that you can go on a sales road show or whatever. So.

[00:31:20] **Ben:** well, a lot of what we did at work and especially in the earlier days was what we sort of joked about as being marketing driven development, where the marketing team wanted to release something and they had a particular date and that date corresponded with blog posts and press releases and paid advertising.

[00:31:39] **Ben:** And. The development team had to hit those dates because that marketing campaign was going out and we had to either get everything done or we had to start, I hate to say, but we had to start cutting corners in order to make sure that we hit those dates. And I, let's just say less than stellar code was sometimes involved in that corner cutting process,

[00:32:01] **Adam:** always.

[00:32:03] **Ben:** I'll and I have talked about the base camp people,formally 37 signals, several times on the show. I'm very enamored with their whole mindset to product development and to business. And one of the things that they talk about, which I'm just fascinated by is this idea of appetite.

[00:32:21] **Ben:** And essentially they work in these six week increments where they have an idea for something that they want to build or something they wanna prove. And they essentially. Give themselves six weeks to do that thing or to do some portion, some fixed portion of that thing. And they hit that mark. And if they think they're not gonna hit that, mark, what they do is they start to pair back, what they're gonna be building in order to hit that mark.

[00:32:46] **Ben:** So they almost work on these like, mini roadmaps. it's very fascinating to me, but, I'm not explaining it well, but they have hard deadlines and I think it works really well for them.

[00:32:56] **Adam:** Yeah. I mean, I've read a little bit of their stuff. I'm not, I don't mean to disparage you at all in saying this, but I'm, I don't think I'm as much of a 37 signals fanboy as you are. and I hope you would agree with that statement, like, that you're are a little bit of a fanboy, and that, not that there's anything wrong with that.

[00:33:10] **Adam:** No, not at all.

[00:33:11] **Adam:** anyway, okay. let's just move on.

## [00:33:13] 7. Do You Have A Spec?

[00:33:13] **Adam:** do you have a spec.

[00:33:14] **Ben:** So I'll jump in here and just say that the moment of specification is written it's out of date that there's no one can keep specs up to date with the living, breathing dynamic nature of a working piece of software. And as, as much as it would be great to have things documented, it just, I've never seen it done well.

[00:33:36] **Ben:** And maybe that's just a reflection of the companies that I've worked on. I've just never seen it done well, and I've never seen it kept up to date.

[00:33:43] **Adam:** Yeah, I would agree. I think that, again, this is gonna go back to, an executable on a CD rom versus A web app, that's gonna change and be totally not totally different, but you know, it's gonna grow week to week. Whereas your CD Ram is you get what you get. And maybe, in the last 10 years they started doing,updates over the internet or whatever.

[00:34:03] **Adam:** But, I, it's funny cuz like I see the value in, the specifying exercise because if you're good at it, you can see potential pitfalls and incompatibility during that exercise. And it's much easier to go back and rewrite that portion of the specification than it potentially could be to go back and rewrite that chunk of the code.

[00:34:25] **Adam:** you've probably, I know I've probably, I know I certainly have had, the experience of writing a chunk of code and then realizing like it's gonna. It doesn't match up that, that we were trying to dig a tunnel from both ends and we're not gonna meet in the middle. And so I have to like go back a good ways and change directions.

[00:34:41] **Adam:** And I think the people who are good at writing a spec can prevent that and do it in a very efficient manner. But at, again, we've talked about my company in particular, a bunch of times in the show, we're very lean team. We have a total of five people. None of us is a dedicated technical writer or anything like that.

[00:35:01] **Adam:** we are basically, three and a half full-time programmers, a support guy and a CEO. And. So, nobody has time to sit down and write a spec that said, I have tried to like, kind of sit down and write technical documents, occasionally like a plan for a thing to just get input from my team.

[00:35:19] **Adam:** But that's only like when I can see something coming really far away, like I can see, okay, this particular service is gonna need to be rewritten for XYZ reasons. here are the lessons we learned from the current implementation. Here are the things that we need to do better. Next time. Here are some,

[00:35:36] **Adam:** nascent thoughts on how we can accomplish these goals and how I might go about it. And then just kind of throw that out to the team and say like, look, we're planning on starting this.

[00:35:46] **Adam:** I'll probably start working on this in two weeks. So if you have any ideas or comments that you can kind of percolate into this document in the meantime, that would be great. But that's about as far as we go with a spec, eh, I mean, for anything significant, sometimes there's like, you'll get a ticket and the ticket serves as a spec, right?

[00:36:03] **Adam:** Like a support ticket for a bug. that's a spec for exactly what's wrong and how to fix it. but yeah, like our applications just evolve constantly and there's no way we could keep a spec up to date.

[00:36:13] **Ben:** Yeah. A hundred percent.

[00:36:14] **Adam:** So I definitely agree with you that the act of writing the specification can be very powerful and it can certainly help you as an engineer or as a product head. Think more effectively about what it is that you want to do. Invision obviously our mainstay, our bread and butter has historically been building prototype.

[00:36:33] **Ben:** And I've from time to time said that prototypes are worthless, but building a prototype is priceless. and in that, what I mean

[00:36:42] **Ben:** the act of building the prototype forces you to think. But once the prototype is done, it's almost something akin to the,strong opinions loosely held.

[00:36:50] **Ben:** Like, just because it's in the prototype. If you start to build out the application and something isn't right. Or the usability doesn't feel right, or there's technical things that come to light that no longer make sense with the prototype, like change it don't feel like you're married to the prototype.

[00:37:05] **Ben:** The prototype was a starting point. It was a level of abstraction,and a facilitation of. But once you're past it, don't be married to it. Just keep going, get more high fidelity, get more, evidence as you build the application. and I guess you could, I don't know how good this would be.

[00:37:22] **Ben:** Maybe this would be a terrible way to think of a spec, but you could think of a spec in some ways like that. The spec helps you think about what you want to build, but once you start the build and if you run into roadblocks or you run into things that don't work the way you thought they were gonna do, thought they were gonna work, like that's fine.

[00:37:39] **Ben:** That's the reality of the situation. So you change the way that you're coding the, whether you go back and update the spec. Maybe that's a little bit more where I diverge. I probably wouldn't go back and update the spec cuz to me the spec, like again, I just think they're always out of date. They're do not be trusted.

[00:37:56] **Adam:** yeah. As you were talking about all this, I couldn't help, but think of like the Apollo mission software, right? There's that famous picture? Oh, I wish I could remember her name, the woman that, was like shorter than the stack of all the printed out code that she wrote.

[00:38:09] **Ben:** yes.

[00:38:09] **Adam:** and like, absolutely for something like that.

[00:38:12] **Adam:** Right. there's no second chance, right? There's no, you can't send it over there. Update to the Apollo capsule, halfway to the moon. so, I think situationally aspect can be really important, but if you have that opportunity to update the software continuously, then yeah. Maybe a spec is a little bit outmoded

[00:38:33] **Ben:** Yo, I have to say you guys were telling, I think this was just, I think we had discussed this on the show or in the after show or pre-show we were talking about the M one chips for apple and mechanical engineering has always kind of sat in my head as this as. Whole different level of art form when it comes to building that there's so much more, I don't wanna call science or like real engineering, but it feels very different to me than software because of this.

[00:39:02] **Ben:** You have to get it right. And there's so much, low level atomic action of how things are working. but then we were talking about the M one chip. And I think I was saying that I read this article that the M one pro and like the M one are actually the same physical chip. It's just that some parts of it are turned off because it's less expensive to build the same chip and then just,deactivate part of it.

[00:39:26] **Ben:** And I think, Yeah.

[00:39:27] **Ben:** and then I think one of you guys was saying that they build chips and just a lot of the transistors don't work after the Chip's been built and they just have to test it and say like, oh, this number of the transistors are working. So it's like the really good chip or like, like a certain number of the transistors are broken.

[00:39:44] **Ben:** So it's the less expensive chip and.

[00:39:47] **Adam:** Yep. That was

[00:39:47] **Ben:** Forgive

[00:39:48] **Ben:** me.

[00:39:48] **Ben:** if I'm misunderstanding or MIS. Yeah. And so like that sort of just paints that whole thing in a different light for me, whereas previously, creating, a chip with a trillion transistors on it, it's numbers that my brain can't even wrap around because of the microscopic nature of it.

[00:40:02] **Ben:** and you're telling me that, oh yeah, a lot of these things are just broken and that's how we deal with it by changing the pricing model and you're like, oh, okay. It's not this like super exact wizard science that I thought it was. I mean, obviously it is to some degree, but it's not, it's, we're all living in the constraints of a physical world and we're all just humans.

[00:40:20] **Ben:** and I dunno, I found that very comforting in a

[00:40:22] **Adam:** Yeah, well, it, I mean, we're pretty deep down a rabbit trail here, but,

[00:40:27] **Ben:** Yeah.

[00:40:28] **Adam:** in, in like machining, right? So if you're making a piston for an engine or something, right. So they tell you, it needs to be, 500,007 inch wide or whatever it's gonna be. but they give you a tolerance, right? So you need to, it needs to be 500,000 wide plus or minus, two th and so, like there's, it's that wiggle room.

[00:40:48] **Adam:** And I think that's, what's being put to use for like the transistor situation you were describing.

[00:40:54] **Ben:** Yeah. A hundred percent.

[00:40:56] **Adam:** okay, so let's, let's move on to the next one.

## [00:40:58] 8. Do Programmers Have Quiet Working Conditions?

[00:40:58] **Adam:** Do programmers have quiet working conditions? And I think this is an easy keep, right? I think it's been proven pretty well that, quiet working conditions are beneficial to creative thought and to programming in particular. at that said, I personally am nine times out of 10, or let's say 25 days out of the month, something like that, quite happy to put on music that is way too loud, in my headphones.

[00:41:24] **Adam:** And so in that situation, like I'm able to get my desired working conditions, even in an office. sometimes you just need that quiet and it's nice to like, in, in the article, he talks about giving developers, private offices with doors so that you can shut the door and just have whatever noise is going on down the hall blocked out.

[00:41:44] **Ben:** Yeah. I a hundred percent agree having a quiet working environment. I can't imagine working in a non quiet working environ. I actually don't even understand how people can go to coffee shops and work in a coffee shop. That idea of not having my own chair and my own desk and an external monitor and being with people who are talking, I it's so foreign to me.

[00:42:06] **Ben:** I can't even wrap my head around how they do anything.

[00:42:09] **Adam:** That's interesting. So it's like so multifaceted here. So I was gonna say I was gonna kind of come back to this one and say,maybe this is the place where we have a discussion about, being able to work remotely. In terms of, at home instead of, in an office, but at the same time, I, I've been working remote for a little more than 10 years now.

[00:42:26] **Adam:** And what I remember when I first started working remotely, it was like six months, eight months, something like that. I was working from home and that it was going fine, but I was starting to get some cabin fever then. And I found myself like maybe three or four days a week going out and working in a coffee shop for the first half of the day or something like that to just shake things up and feel normal.

[00:42:48] **Adam:** And I don't know if it's because,the context of my work has changed right? At that time we were doing like partial consulting, partial working on products. and we were, it was still just the two of us. and the difference between then and now is we have a specific set of products. We don't do any consulting and the pressure to get stuff done is so much higher.

[00:43:10] **Adam:** We just have such a back. that like they thought of trying to get work done out in a coffee shop or Panera or wherever is, going to it. It's just, I can already tell you I'm not going to be as productive out there as I would be at home. And I don't think it has anything to do with the noise. I think you're right.

[00:43:27] **Adam:** It's like the comfortable chair. I know I've got my steady supply mountain Dew, and I don't have to go break out the credit card every, 15 minutes winning another one. And just little things like that.

[00:43:36] **Ben:** and as someone who drinks a tremendous amount of fluid during the day, which leads to a tremendous amount of urination, I don't even know how I would do that. I mean, I can't leave my laptop, on a public coffee table while I'm in the bathroom. So I'd have to, I mean, I don't know what people do.

[00:43:54] **Ben:** Maybe they do that and they just, lock it. So it, even if it were stolen, it can't be used, but I dunno it, it would just be too stressful.

[00:44:03] **Adam:** Yeah. Yeah, it is very stressful. There's been a couple of times I remember, like kind of making a little bit of a friend while I was out at, whatever coffee shop or restaurant. And we were both like working from there. I'd be like, okay, look, when you gotta go to the bathroom, I'll watch your stuff.

[00:44:16] **Adam:** When I go, you watch my stuff sort of thing. but that wasn't always available and sometimes you're right. It's like, you gotta, all right, I'm gonna have to make this one quick, lock my machine, pray my stuff. Doesn't walk away and just go cause you're right. You can't, you don't, you wanna pack up all your stuff and take it into the bathroom and then come back and find like the one seat that had, an electrical outlet next to it is now being taken up by, a mom's club of like, you.

[00:44:39] **Adam:** 12 ladies hanging out and none of them is using the electrical outlet, but they're ticking your table, like, come on now.

[00:44:45] **Ben:** you. and then one thing that would be helpful. Being in a crowded environment where we'd have noise canceling headphones. but as someone who has had noise canceling headphones, I actually find them a little bit disturbing is not the right word, but I don't like feeling so disconnected from my environment.

[00:45:04] **Ben:** And part of it is working from home. And part of it is I have to know what's happening with the dog and if I'm out and about, I don't wanna step out into the street and not hear an oncoming car, but I have, I have stopped using the noise canceling feature of my headphones because it feels, I feel too disconnected from my surroundings.

[00:45:24] **Ben:** and I don't know if that would be, I don't know if sitting in a coffee shop, right. I'm not about to step out into a busy street. I don't have to worry about the dog. So maybe it would be different in that kind of a situation. I don't know if that's something that connects with anybody else.

[00:45:36] **Ben:** Cause I know noise canceling headphones are obviously a big deal. So, but that I have tried and lost my taste for them.

[00:45:44] **Adam:** Hm. Yeah. I mean, there, there're definitely situations where they're amazing, like having 'em on a plane when you're trying to watch a movie or even if you're trying to work. But I agree, like there can be dangerous too, trying to cross the street in the middle of a city or, yeah. So, but you know what?

[00:45:59] **Adam:** I don't think I've ever had a pair of head noise, canceling headphones that didn't come with a way to turn that feature off either.

[00:46:06] **Ben:** Yeah. That's great.

[00:46:06] **Adam:** Just gotta be vigilant of it.

## [00:46:08] 9. Do You Use The Best Tools Money Can Buy?

[00:46:08] **Adam:** Okay. so do you use the best tools money can buy? I forget what number we're on. I don't have, I'm looking at a spreadsheet, so they're not in the here. I'll come back. they are, it's number nine. Do you use the best tools money can buy? you had a funny response to this, so I'll let you go first.

[00:46:22] **Ben:** I said as long as I could still use sublime text,the joke there is that best tools for the job is somewhat, personal, I guess, the best tool is the thing that makes you the most productive. Not necessarily, I don't know what the opposite of that is. not necessarily like the industry darling.

[00:46:40] **Ben:** so that's why I think the underlying thing here is, is there friction that your developers are feeling that they don't have to? and I think that's the key is that instead of the best tools, it's how are you making your developers the happiest?

[00:46:55] **Adam:** yeah. Happiest and most productive, right? Like, so if you can buy them that M one pro and cut their compiled time down from 15 seconds to one second, or if, getting a second monitor means that they can be more productive then, like, those are easy things to spend money on that are gonna have long benefits.

[00:47:14] **Ben:** Yeah. Yo, I'll tell you. So, Docker for Mac, we use Docker at work, for local development and, Docker for Mac couple like a month ago released some update that used some experimental file system integration. Because, so the way development happens with Docker is you Mount volumes. So you have the code on your computer and then you spin up a Docker container, and then you Mount your code into the container and it does the synchronization.

[00:47:43] **Ben:** So it's essentially copying your code on an ongoing basis into the Docker container. And that, for reasons that I don't understand is extremely slow, relatively speaking. And they released some update a little while back where it's some new experimental file syncing protocol, but you had to upgrade to the latest, Mac operating system in order to take advantage of it.

[00:48:04] **Ben:** And I finally set aside some time to do that, and it literally cut my build times, like in half and my application boot up time in half, just because it was reducing some of the file IO overhead between the Docker container and the host operating system. So it's weird, like little things like that.

[00:48:21] **Ben:** You don't even realize how much of a difference they're gonna make until you see it in action. You're like, whoa, that's awesome.

[00:48:27] **Adam:** Yeah, cool.

## [00:48:30] 10. Do You Have Testers?

[00:48:30] **Adam:** number 10, do you have testers? I wrote revise. And you said you don't, you're not sure how you feel about this. so his explanation for it in the article was basically to, to give some rough generalizations, you are paying your programmers a hundred dollars an hour, and testers would cost you $30 an hour.

[00:48:47] **Adam:** So don't make your programmers spend their time manually testing things. And I think the mathematics of that checkout, but I think that the testing tools and methodologies and the collective knowledge of testing has come so far. Since then that, it makes more sense to automate away those people entirely take their jobs and disrupt them.

[00:49:15] **Adam:** again, that goes back to the one that you mentioned earlier that I have on my additions list of just automating everything that can be, if you can write an automated test that will complete, a dedicated person's daily work in five minutes, 10 minutes, 15 minutes, like, why wouldn't you do that? So,

[00:49:32] **Adam:** yeah, just so I kind of feel like, it, it makes more sense to lean on automated testing than, testing staff, but at the same time, like if you don't have the automated testing, then sure. It makes sense to, to maybe hire some people on a temporary basis until you get those automated tests.

[00:49:48] **Ben:** so I'm conflicted about this one because on the one. I do believe that having dedicated testers increases the overall quality of the software that you're building,

[00:50:00] **Adam:** As long as they're like good at their jobs, right? Like have you ever had a tester that is like, gives you a failure, but it's like all of the human testers I've ever worked with, you have to provide them like a script. Right? So click on this, type, this in the box, hit this button, that sort of thing.

[00:50:16] **Adam:** And it's a, maybe it's a 12 step process. And the assertion that you're making is on step 12, but it fails at step three. And so they fail your test and you're like, well, but that's not the broken thing. , you're failing the wrong thing. There's some other test that should have this covered that you just did out of order or something.

[00:50:32] **Adam:** And.

[00:50:33] **Ben:** right. Right. Well, so here's my flip side to the coin is. If I could draw a parallel to pull request reviews, PRS, I think that the person writing the code, it's their responsibility to make sure that the code they're writing is successful. The person reviewing the pull request, their job is not to ensure the success of the code it's.

[00:50:59] **Ben:** If anything, to provide a sanity check to double check that, things are being done in a roughly intelligent way. But if a bug gets through or a suboptimal approach gets through, that's not the fault of the person reviewing the code, in my opinion,it's the person who wrote the code. They're the ones ultimately responsible.

[00:51:20] **Ben:** When it comes to bugs and testing, I follow the same sort of mentality that the person writing the code, it's ultimately their responsibility to make sure that the code behaves the way it's intended and expected to behave. And if you have testers, that's a nice to have, but I wouldn't wanna use testers as a gatekeeper to code getting to production.

[00:51:44] **Ben:** we've talked about, Carol over at, what's that company, silver mine. I think something like that.

[00:51:49] **Adam:** no, she's at Clear Capital now.

[00:51:51] **Ben:** Clear Capital. Thank you. they have a very strict workflow where it has to go through QA before things can go to production. At least that's my

[00:51:58] **Ben:** of what I've heard her say.

[00:51:59] **Ben:** And I, I have trouble imagining being in that world that feels like it, it just feels odd to me. it's not what I'm used to and. if the, do you have testers, Joel test here says it can't go to production until it's passed QA. Like, I don't think I could live in that world.

[00:52:19] **Adam:** Hm. It's definitely a very different world. I think you and I are both far from enterprise. I don't know if you've ever had the pleasure of working in enterprise software situation. I unfortunately have. And, it did not, jive well with my personality either for similar

[00:52:33] **Adam:** reasons.

[00:52:33] **Ben:** it's tough. and, I think even Carol has admitted this, that she believes whether or not she can point to evidence of this, but she gets the sense that when, you have a team of testers that have to approve code before it goes to production, you get sloppy as an engineer because you're just not as worried about it.

[00:52:55] **Adam:** Right. Interesting. I don't remember her saying that, but that's a very interesting theory.

[00:53:00] **Ben:** Yeah. So I'm very conflicted about it.

[00:53:02] **Adam:** So, I mean, if we are, rebranding, the Joel test, you know, we're making the working code test here, how do we, how would this land for us? I think for me, what I would repurpose this, particular rule is like, do you require an extensive test suite? not necessarily exhaustive, but like, I would want to, have like a policy that says like all mission critical,critical path processes have to have, almost like a tedious and BOR bordering on too many tests, automated tests, right?

[00:53:31] **Adam:** Like the things that, like if it broke, if you would want to be, woken up in the middle of the night to go fix it, that's the type of thing that you should have automated tests for so that it doesn't break in the middle of the night.

[00:53:44] **Ben:** I'll buy that. I'm not a huge automated tester, but I like what you're saying.

[00:53:49] **Adam:** news to me.

[00:53:50] **Ben:** let me draw one more thing here. and just because everybody has a different mindset and things are important to different people in different ways. So going back to this idea that having testers can make developers sloppy. it's a little bit to me when I hear people on various podcasts say that, oh, if you just use prettier or standard or something to that effect, then you don't have to worry about formatting your code.

[00:54:14] **Ben:** Like I'll just write garbage code on the screen. And I hit command S and the tool auto formats, the code for me. And I'm always like, wait, what? You're not thinking about the formatting of your code. Like. How do you do that? How do you not? And it'd be like writing pros without worrying about punctuation.

[00:54:32] **Ben:** Like you, as someone who thinks about writing, like, it wouldn't make sense. Like that's not a gesture that makes sense. Like it's mathematically impossible. and so that's why I get a little weary of having too much of a, of a safety net of a QA team. Cuz it's like, you just start to, it's like you turn off parts of your brain.

[00:54:52] **Ben:** And I don't mean like you're getting dumber. I just mean like it's like you're turning off parts of the algorithm that always used to be there. and I get very nervous about that.

[00:55:00] **Adam:** Well, yeah, I mean, again, no surprise to hear that you have concerns about ING, and four matters, but, I, and it's funny, cuz I used to have that exact same opinion. when I first saw and heard people talking about prettier, I was like, why? but I can just do that by hand, but, and I can't explain

[00:55:18] **Adam:** how

[00:55:19] **Adam:** I came to change.

[00:55:20] **Ben:** it's not even that you can do it by hand it's like my mindset is that I can't not do it. it's not like I'm opting in it's that in order to do it, I'd have to start opting out of that mentality. And I don't know how to, that feels more unnatural to me than worrying about formatting. let me draw an even crazier analogy. So, I have a big fear of physical violence. Like I have a big fear of getting attacked, by random people. And so over the years, I always, I play this game with myself where I see people do stuff that doesn't make sense to me. And I think to myself, What they're doing, doesn't make sense, like where on the scale of how likely they are to become violent, because their view of the world is so different than mine.

[00:56:01] **Ben:** and it's like super ridiculous things. Like you get into an elevator and then someone else gets into the elevator and you're in a closed space and they start whistling and you're like, whoa, that's crazy. And you're like, if you're willing to get into an elevator with someone else that you don't know and just start whistling, like how likely are you to then become violent?

[00:56:20] **Ben:** Because your view of the world is so skewed. And obviously that's like, a nonsensical jump, but like, it's a nuance scale.

[00:56:28] **Adam:** Like what if they have sunglasses?

[00:56:30] **Ben:** right. Yeah. Like you're inside and you have sunglasses on, come on, man. Like I'm like moments away from being attacked. but so when I think about people who don't think about the formatting of their code while they're writing it, I'm like, what else. What else are you not thinking about? Like what else in the world of software development's not important to you in a way that it is important to me? And like, how does that actually affect our ability to work together? So some of that linking is like a, I don't wanna say red flag is, that's like that's too.

[00:57:02] **Ben:** That's not really, it's not that extreme, but it's a, it's just like a moment where you're like, oh, this person sees the world in a way that is different than I see the world. And is that gonna become a point of friction for us? And it's a question, mark. So I forget how we got onto this

[00:57:21] **Adam:** Doesn't matter. It was. Do you have testers?

[00:57:35] **Adam:** So, okay. a final thought. I am a, I am pro linter pro formatters, like prettier. I still, cannot stop myself in most cases from adding a semicolon at the end of my lines of JavaScript, I've always been a semicolon user. and, that said, sometimes I've got, I'm balancing too many things in my head and I forget a semicolon and it's nice to know that when I hit save, the formatter is gonna add it for me.

[00:58:01] **Ben:** Yeah,I'm not gonna fight against that.

[00:58:04] **Adam:** And there are little things like that. if I don't, again, if I'm focused on something different in that exact keystroke moment, I might not follow my own spacing rules about, a space inside a curly bracket or something like that. and it's nice to know that it'll catch me and fix that for me anyway.

[00:58:20] **Adam:** Let's move on. cause we only got two more left and then we gotta talk about our additions here.

## [00:58:24] 11. Do New Candidates Write Code During Their Interview?

[00:58:24] **Adam:** So number 11 to new candidates write code during their interview. I think this one should be pretty easy for us, right?

[00:58:30] **Ben:** I also I'll say keep, but with the caveat that I've never actually been in an interview or given an interview where someone has coded . So I love it as an idea, but I've never actually seen it in practice.

[00:58:43] **Adam:** how many jobs have you interviewed for Ben?

[00:58:45] **Ben:** let me, maybe let me clarify. I've never, if I, I, I've neverbeen in an interview where someone has coded during the initial interview, but I have been and given interviews where there is a take home portion, so to speak where someone has to do like a, build out something or provide some sort of a sample.

[00:59:03] **Ben:** So I guess, I don't know if that counts, but yes, I think seeing someone's code is very important to understanding how they're gonna.

[00:59:12] **Adam:** Right. Yeah. It's funny because that's a whole thing, right? Like there's like gotcha. Tests. And there's like ridiculous trivia that is like, is obvious once the answer. And I think that those are bad things to do in interviews, but at the same time, like forcing somebody to code while you're standing over their shoulder, watching them.

[00:59:32] **Adam:** In some ways can be equally as bad, right? Like that's not how you're gonna work every day. Right. you're not gonna be self-conscious about what you're Googling, during your work day. I mean, as long as you're Googling, work related stuff, but,to, are you gonna be embarrassed that you have to look up the docs to array dot splice, in an interview?

[00:59:50] **Adam:** Right? So, I personally, I might be embarrassed about having to look that up during the middle of an interview, but I certainly have no qualms about looking it up during the middle of my Workday. Right.

[01:00:00] **Adam:** So I think that, a take home test of, or, take home coding assignment makes a lot of sense.

[01:00:06] **Adam:** I, I understand why there might be some concerns about that people could be getting help from other people or whatever, and that would suck, but, yeah, I don't know what the solution is to that problem, but I agree,seeing somebody's coding style, seeing how they would solve certain problems is crucial.

[01:00:22] **Ben:** I was listening to an interview. I think I brought this up on the show before actually, and actually we did a whole episode about interviewing and I may have brought it up in there, but I'll, I find it so fascinating as a point of view. So I just wanna bring it up one more time. I can't remember who it was or where I heard it.

[01:00:34] **Ben:** It was on a podcast interview. Pretty much pretty sure this guy was saying that as an industry, we've basically fooled ourselves into thinking that we can glean any information about a candidate from an interview, or even from a set of code samples. That is basically. like a useless ceremony that we have and his take on it.

[01:00:53] **Ben:** And I don't remember exactly the details here, but his take was you just have to literally pay people to do work and then see what they produce. And that's really the only way that you'll understand whether or not they're gonna be a long term fit for the company. So his take on it was you have an initial interview.

[01:01:09] **Ben:** I think just get a rough sense of whether or not this person is gonna make it or not make it. And then you give them a contract of some sort like a month or, three months, and then like use that as the interview, so to speak, which I don't know how feasible that is, but I think

[01:01:23] **Ben:** There's a lot of meat in there, but, I don't know how scalable that is and for every company, but.

[01:01:29] **Adam:** Yeah, no, I think you, you said that pretty well. I agree. Like the only way to see how somebody is going to work is to put them to work and,there, that's what the interview process is trying to do is to figure that out. But, yeah, and also that could be, it's gonna be a lot easier for someone like Microsoft to pull off than it is for my five person company.

[01:01:48] **Adam:** Right. Can't just hire all five applicants to a job that made it past the initial interviews, and see how they do so. Okay, well then let's move on to Joels.

## [01:01:59] 12. Do You Do Hallway Usability Testing?

[01:01:59] **Adam:** Number 12 here. do you do hallway usability testing? So I guess maybe this bears a little bit of explanation. So basically what he describes as hallway usability testing is you get to a point where you have like some UI or something you need tested.

[01:02:13] **Adam:** and you just grab the next person that walks by down the hall. and you say, okay, here's what I need you to do with this software. I've been working on, go do it and you watch over their shoulder. that's what usability testing is. And you just, the hallway part is you grab the people that walk by.

[01:02:26] **Adam:** And his theory is that if you do this to five people, then you'll learn like 95% of what there is to learn about the usability problems in your code. So what do you think Ben.

[01:02:35] **Ben:** I mean, I'm a little biased here. Invision as a company is essentially founded on this idea of getting people to try stuff and get their feedback. So I'm fullthroated yes. on this usability stuff. and I'd even go so far as to say beyond prototyping, we've talked extensively about feature flags on this show and iterative development.

[01:02:57] **Ben:** And I am so heavily into the camp of just get something on the screen and let the users start to play with it, and then just see what happens and use that to help, formulate the path forward. So, I'd say, I almost like go beyond what I think Joel was intending to imply in this. And I just love getting feedback early and often.

[01:03:19] **Ben:** And what there's I forget who said this? Some someone said something to the effect of. if you're not embarrassed by the product that you're deploying, then you've waited too long to deploy it. There's some something along that line, there's somebody said somebody famous said something along those lines.

[01:03:35] **Ben:** And,and I'm, as I've gotten older, I've started to embrace that more and more that, get it out there, get feedback, get people using it. And, and then move forward.

[01:03:46] **Adam:** Oh yeah, for sure. Done is way better than perfect.

[01:03:49] **Ben:** Ah, every day

[01:03:51] **Adam:** Okay. Well, I mean, I agree. it's funny because like my team, my company is a hundred percent remote, so there is no hallway for anybody to be walking by, but we do pretty, like we have a daily meeting as a team and, one of the things that will come up is like, okay, I just finished this thing.

[01:04:07] **Adam:** and I wanna get you guys to mess with it and tell me what you think of the UI or, stuff like that. Just basically it's become such a common thing that we don't even talk about it anymore. It's just like, I'm working on this. You can test it here for me. Let me know what you think. And that's all the input that they get.

[01:04:23] **Adam:** And then, I get some notes back or I get some, yeah, it looks good, but yeah. Cool. okay.

## [01:04:27] Additions To The List

[01:04:27] **Adam:** Well, how do you wanna handle additions? I, it looks like I have a couple more on my list than you do, but maybe you've come up with some since then. Do you wanna go back and forth or.

[01:04:34] **Ben:** Yeah. Let's go back and forth.

[01:04:37] **Adam:** Well, I'll start. so, you and I have some things in common, Ben, we are both, middle aged white men, cisgendered white men, as far as I know, and, and straight to, so anyway, the point is the thing that I would add here, is, Do you have any women or minorities on the team?

[01:04:52] **Adam:** And I guess the point for me is,I need to put my foot down, right? Like I've been on teams of a bunch of white dudes too many times. And,if I don't do my part to make space for, underrepresented people then I, I don't feel like I'm being true to myself anymore. I certainly have grown a lot and learned a lot over the last 10 years.

[01:05:12] **Adam:** And for me, this is one of the ways that I wanna, implement what I've learned. And I think honestly, if I'm being, if I'm being truthful about where this comes from, I saw,a pretty well known developer. I don't wanna name names and whatever bring people up, but, pretty well known developer post on Twitter.

[01:05:28] **Adam:** This was years ago that he would no longer be participating in any panel discussions that didn't include women or minorities. And he's a straight CIS white middle-aged male. and that really clicked with me. I was like, yes, that is the perfect attitude to have. And so,

[01:05:43] **Adam:** I want to integrate that on all of my teams going forward.

[01:05:46] **Ben:** Yeah, I think that's really wonderful. And it's something that I think about, but I'm probably not in touch with it as much as I'd like to be. and it's not just,we keep here, it's not just about doing the right thing. It's that there's a material benefit.

[01:06:02] **Adam:** Oh,

[01:06:02] **Adam:** yeah,

[01:06:03] **Ben:** teams. it's, it's not just trying to help other people. It's helping the product and it's helping the customers.

[01:06:09] **Adam:** for sure. Well,

[01:06:11] **Ben:** All right, I'll go. I have one. So as you can tell from this discussion and many discussions before, I have feelings about software and those feelings tend to be pretty strong. And, so for me, it's important to have an understanding of how much independence engineers get, even just earlier in this conversation, I mentioned that the idea of having a QA team be a blocker, like a hard gatekeeper to having code reach production feels so far into me.

[01:06:38] **Ben:** And so I, I would need to be in a world. Engineers can be independent actors as much as possible, within limits. We don't want people going crazy. And, with things like, the SOC two compliance that we talked about earlier, you, there has to be limits, for security reasons, but I need to be in a place where engineers have a seat at the table that it doesn't go from like designers to product leads.

[01:07:05] **Ben:** And then like to low level engineers who are basically just clock punchers. Like I could never be a clock puncher.

[01:07:10] **Ben:**

[01:07:10] **Ben:** so I would need to know that I have some independence and some freedom of will and, and thought to get stuff done and to work with customers and stuff to that effect.

[01:07:21] **Adam:** So when you're coloring, you want a description of what should be on the page, but you don't wanna have lines to color inside

[01:07:27] **Ben:** Yes. yeah, exactly. bring me the set of markers. Don't bring me the, the book of outlines.

[01:07:32] **Adam:** word. Okay, so I'll go again. do you include accessibility concerns in testing and in code reviews? again, this is another one of those things that's like, I just took for granted. I took my privilege for granted for so much of my career. And now that I know better, I wanna do better. And accessibility is a really important thing, especially even for me personally, as I'm starting to get older, my, my eyesight is not as good as it used to be.

[01:07:55] **Adam:** And so that's become, an obvious thing for me where I start to recognize like, oh, font size is really small here, or the contrasted isn't as good here. and it's like, oh, okay. Yeah. All those people have been talking about all this stuff for so long. Like, maybe they know what they're talking about.

[01:08:10] **Adam:** so again, I just wanna put that best foot forward.

[01:08:13] **Ben:** And again, going back to the idea of having a diverse team where it's not just about the team, it's about everything. accessibility is the same thing. It doesn't just make something more accessible for some people by making it accessible for some people, you actually make it more accessible for everybody

[01:08:30] **Adam:** Yeah. Oh man. so, sorry, another rabbit trail here. You and I, Ben have talked, on this podcast, not that long ago, about how the tabs versus spaces, argument is an accessibility argument. and,I, I think deep down, I already agreed with that statement, but I had never really put it into those words in my head.

[01:08:51] **Adam:** And when you said it's an accessibility issue, it just like crystallized for me perfectly. And,I had, I came across a tweet not long ago, by the creator of felt rich Harris, where he was, I. Linking to a comment on a GitHub issue on some random repository that, basically the commenter was, and probably still is blind and uses a braille display.

[01:09:18] **Adam:** And, I, oh, that's what it was. So in, a future, like a request for a future version of prettier was to switch the default from spaces to Um, and uh, reasoning, I guess, for the request was that on a braille display, a tab can be a single character, whereas a space is a single character. So if you have a tab of four, then you have one tab or you have four spaces, right?

[01:09:46] **Adam:** So those are like four characters could take up one. And if you have something that's indented four or five levels deep, it multiplies out versus. using tabs. It is, much less of that braille display with gets wasted on indentation.

[01:10:03] **Ben:** Yeah. I mean, I just feel so strongly about this one that I can't understand how anybody feels strongly in the opposite direction.

[01:10:11] **Adam:** Yeah, I added, so I replied to the tweet. I linked my article on my blog about the whole thing. I added that, that little exchange that I had with the guy, on Twitter to the blog post. So it kind of became this like self-referential thing, which was kind of funny to me. and, and still I got comments, I think honestly, probably the comments, the negative comments that I was getting were people who didn't take the time to read.

[01:10:33] **Adam:** They were just like, oh, I like spaces. You like tabs. So I'm gonna say mean things to you, right? Like.

[01:10:39] **Ben:** and I'll tell you, I don't have any real visual impairments. I mean, I'm nearsighted, right? I think that means I can, I can see much better up close than I can distance wise. but that's really my only issue. and even me, when I'm reading code that has only two space indentation and I'm scanning the code vertically, I actually have trouble following the code.

[01:11:00] **Ben:** Like, and I don't know how to describe this very well, but it's like my eye. I have trouble keeping it in a vertical line. Like my eye starts to jump around for reasons that I don't fully understand because the indentation isn't very clear to me. And I think, I don't know if it's like my brain is trying to constantly jump back up to previous lines of code to see where that indentation was.

[01:11:21] **Ben:** But when I'm looking at two space indentation, I'd literally have trouble reading it. it's like my, I have trouble focusing on the lines of code and I never have that problem with tab indentation.

[01:11:32] **Adam:** Well, I don't think I have the exact same physical mal if that's what we're gonna refer to it as, or box it in there. But,I can relate,I, I just have that same sort of trouble keeping things, vertically aligned. I even have a plugin for my IDE that will draw small, low contrast lines that at the like left edge of every indentation level and still it's difficult to keep things aligned.

[01:11:56] **Adam:** And so I often find myself using a tab, the four or five characters just to help it stand out.

[01:12:03] **Ben:** Yeah,

[01:12:03] **Adam:** And it's nice to be able to change it as an IDE setting. okay. Anyway,

[01:12:08] **Ben:** oh yeah. Yeah.

[01:12:12] **Adam:** we're both preaching to the choir here, so let's just move on.

[01:12:15] **Ben:** all right. All right. I'll do my last addition here, which is that I'd like to know how much contact engineers have with customers and or with the supporting teams. And that's simply because I find in my experience, there's nothing as grounding and focusing as understanding what your customers are actually doing and the pain points that they're having.

[01:12:39] **Ben:** And. The teams that I see that don't have that line of sight with actual customers and actual customer problems. They just have a very different mindset and it's this mindset of disconnection. and I, and that can be not as bad as I'm making now to be. but I think that people who deal with customers to some degree, they're just more focused in how they think about product building.

[01:13:07] **Ben:** And I'd wanna make sure that I'm in an environment where if I'm not dealing with customers directly, I'm at least dealing directly with the people who deal with the customers directly. So that I have that, that at least, still vibrant feeling of customer pain. I don't want to be, I don't want to be someone who's only contact with customers is through tickets.

[01:13:29] **Adam:** I agree. And, I think that if I can make an amendment to that, I, it's weird cuz I, I don't wanna like say all these things are required for E every team, but at the same time, there's definitely a benefit that I see to. Talking to somebody like face to face where you can see their face, even in the current, unprecedented times, even though they've been unprecedented for two years now, if you can get on a zoom with somebody, even if you can't go to their office or whatever, if you can just like, look them in the eye and hear their pain and let them give you that additional context, that they're not gonna bother to type into the ticket.

[01:14:00] **Adam:** That can go so much further, right? Like there are people who submit support tickets for us. And I have no idea who the person is never met them. Have no idea what they look like have never had a conversation with them. and it's so easy to write them off as lazy or, ignorant about the way the application is supposed to work.

[01:14:19] **Adam:** But if you just take that time to meet them, it's like, oh, okay, well, they haven't been given the proper training. So let's hook them up with somebody who can give them the training or, they have constraints that, maybe they don't have time to do everything that they're supposed to be doing in this process or something because of other business concerns.

[01:14:36] **Adam:** So I think that face to face, opportunity is really important.

[01:14:41] **Ben:** Yeah, a hundred percent.

[01:14:42] **Adam:** Cool. Well, so we already kind of touched on this one a little bit. Do you automate almost everything that can be automated? I think that it's easy to follow into a trap of like, if something can be automated, it should. So like, that's why I threw the almost in there. Right. there's the, of course there's an XKCD for everything.

[01:14:57] **Adam:** there's a, there's an XKCD chart of like, should you automate it? And,I think that's a good baseline. I would say. I would take things a little further, like he has a chart or his chart shows,kind of a line like you should automate on this side of the line and you shouldn't automate on this side of the line.

[01:15:14] **Adam:** I would be a little bit more forgiving, I think, like automate more than he would, but, that's just because I feel like, those automations tend to compound over time in a really beneficial way. So.

[01:15:26] **Ben:** Yeah,I agree. I wish more stuff in my life was automated and. I think it's on the ship it podcast. So it's one of the change log podcasts they're talking about that you should, when you're starting up a new project, you should really make the first effort to get all of the kind of platforming automation stuff done, like the build step and making sure that things compile and can be pushed to production because once you get that done and working smoothly, then everything else just goes so much more efficiently and quickly.

[01:15:58] **Ben:** And, and you just get so.

[01:16:01] **Adam:** For real, yeah. Toil is a whole, that's like something, I don't know if we've done a topic on that or if we've even talked about it at all, but like toil is such a big deal, that I find these days and something that really has to be squashed with prejudice. so yeah.

[01:16:15] **Adam:** All right, cool. Let's move on. we're running pretty long here. It's half the squad, twice the show kind of thing here. so my next one is, do you send your people to training in conferences? I think that, there's that, that famous, like, what if we pay to send them to training, and then they leave and then the other guy responds well, what if we don't and they stay.

[01:16:31] **Ben:** Yeah. I love that one.

[01:16:34] **Adam:** Yeah. I think that it's such a no brainer and it, you have to value continually improving your team's skills. and the only way you could do that is to give them the time and the budget to, to improve it. So to me, that seems like something a again, a lot of this goes back to, you're given the opportunity to interview the team or the company at the same time that they're interviewing you.

[01:16:57] **Adam:** Right. And these are the types of things that you should be asking them. So, all right. And then, the last one that I wrote down was, do you set career growth goals for your people, for your team? I think that's really important, right? Like it's one thing to be able to perform on the team. It's another thing for the team to make you better and to help you progress in your career.

[01:17:15] **Adam:** And I think that those are, when a team does that, it's, it says it kind of brings them up to a higher level. It says something about how much they care about. Your goals as much as their goals.

[01:17:26] **Ben:** Yeah, I, this is a tough one for me. And it's not that I disagree with you at all. It's that I've, I have never been effective at thinking about my own career goals and my career path. I get so mired in the technical details of the work, am I building the right thing? Do I understand what the heck I'm doing?

[01:17:46] **Ben:** Am I better technically than I was yesterday? I often fail to even consider. What does my job look like in a year or five years? Or what do I want to do? so it's, I agree with you. it's just a point of failure for me in general, is career oriented thinking

[01:18:04] **Adam:** All right. Let's, let's kill it there because we've been going for a really long time.

## [01:18:08] Patreon

[01:18:08] **Adam:** So this episode of Working Code was brought to you by revisiting 22 year old lists and seeing what they do. And don't still have to offer you and listeners like you. If you're enjoying the show, you should consider supporting us on Patreon.

[01:18:20] **Adam:** It's the best way to help keep the show running your donations, cover the cost of recording and editing. And, we couldn't do this every week without you. So thank you, uh, special. Thanks of course, as usual to our top patrons, Monte Gavin and Sean, if you'd like to help us out, you can go to patreon.com/WorkingCodePod.

[01:18:38] **Adam:** All of our patrons get early access to new episodes and the after show. And when I say early access, what I mean is generally we'll we're recording this tonight on Monday. usually we record on Thursdays and usually that episode that we record on Thursday night is available for patrons by Saturday, at the latest often on Friday.

[01:18:56] **Adam:** So, that's the kind of early access that you get. and if you're not a patron, you're getting it almost two weeks after we record it. so yeah, that if you want early access, that's how you get it. You become a patron you can do so for as little as $4 a month. and we also do the after show and patrons, get that as well.

## [01:19:11] Thanks For Listening!

[01:19:11] **Adam:** So your homework this week is to tell a friend,I still believe that word of mouth is probably the best way to, do marketing for anything. And if you like this show, one of the best ways that you can help us out is to tell somebody that you think would also like to show, I guess hopefully that means your colleagues, but you know, if your grandma wants to listen, we'll take it.

[01:19:28] **Adam:** and, as always we could use your topics and questions to discuss on the show. You can send those to us @WorkingCodePod on Twitter or Instagram. You can, join our Discord and discuss them with us there or submit them there. You can join by going to workingcode.dev/discord. If you wanna email us, you can send it to WorkingCodePod@gmail.com.

[01:19:49] **Adam:** Or if you wanna record a voice memo of your question or suggestion, you can send that to the same email address, WorkingCodePod@gmail.com. That's gonna do it for us this week. We'll catch you next week. And until then,

[01:20:00] **Ben:** Remember folks, your heart matters?
