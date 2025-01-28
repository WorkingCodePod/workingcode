---
title: "001: Adam's Secret Shame"
description: What could it be??
date: 2020-12-16
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/001-adams-secret-shame/id1544142288?i=1000502586051"></iframe>

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're **@workingcode.dev** on [Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Triumph:** His team realized that they could write a tool that would log, per controller method, how many times it had been run, whether or not it threw exceptions, and some performance stats, which is reducing the pain of transitioning app server platforms without a comprehensive test suite. They're currently at 90% tested!
- **Carol's Fail:** Having just started a new job, she thought she would make a good first impression by bringing down the production site!
- **Tim's Triumph + Fail:** A product he's been working on developing in secret for FOUR years is finally going to see the light of the day... just not through his years of persistence trying to push it past the finish line.
- **Ben's Triumph + Fail:** A R&D project failed to get any traction, but on the plus side he got to delete thousands of lines of code!

## Notes & Links

- The VS Code plugin that Adam couldn't think of is [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Cargo Cult Programming](https://en.wikipedia.org/wiki/Cargo_cult_programming)
- CFML ("ColdFusion Markup Language") a.k.a. [ColdFusion](https://coldfusion.adobe.com/) is a web-dev language and app server that the four of us have some shared history with. [Lucee](https://www.lucee.org/) is its open source alternative engine.
- Spoiler alert: You can write awful code in every language!
- "Life with chapters" is a concept stolen from the [No Dumb Questions](https://www.nodumbquestions.fm/) podcast, which is fantastic, and a huge inspiration for Working Code. If you don't already listen, give them a shot!
- There are a variety of different ways people prefer to learn, but teaching a concept is the best way to help yourself find your weak spots.
- Never compare your beginning to someone else's middle!
- The Martian is a fantastic [movie](https://www.imdb.com/title/tt3659388/?ref_=fn_al_tt_1) and a better [book](https://amzn.to/3g2S3qp); and yes, the [audiobook](https://www.audible.com/pd/The-Martian-Audiobook/B082BHJMFF?pf_rd_p=83218cca-c308-412f-bfcf-90198b687a2f&pf_rd_r=N31P5MVW485ZX4RD8C5D&qid=1606956278&ref=a_search_c3_lProduct_1_1&sr=1-1) was narrated by Wil Wheaton, of Star Trek fame.
- [GraphQL](https://graphql.org/) is an interesting new(ish) idea in the world of web API's.
- "The right tool for the job"? NOPE. The right tool for the job, for the team, at that particular point in time. You heard it here second!

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/001-adams-secret-shame.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:16] **Adam:** Alright, you guys ready? Here we go. This is episode number one, for some point in the future, we're not even exactly sure when yet. And today on the show we're going to talk about my secret shame. But first

[00:00:27] **Tim:** we want to try something a little different. We're going to start with something called Triumphs and Fails.

[00:00:32] **Adam:** Adam? So I guess I'll start with a triumph. Um, I, uh, and my team are converting our application, which is a really big, you could even call it a platform, from a paid, uh, closed source programming language to an open source platform. Um, and one of the reasons that we're doing that is that, uh, The closed source one that we're coming from is not slow, but it's difficult to test for.

[00:00:58] **Adam:** There's not a great testing ecosystem around it. And as a result, we don't have a whole lot of tests. And so we have this application with thousands of... Actions that you can run, um, and no tests. And so it's, it was been kind of a nightmare to figure out how are we going to go through this process with any level of confidence and be able to tell our customers, okay, it's time to turn on the new environment and we need you to move over here.

[00:01:25] **Adam:** Um, and so one of the things that we did, and this is, I think, where the triumph comes in is that, um, the framework that we're using, it, um, it provides Lifecycle hooks, so you can tell, like, before a request runs or before the controller method runs, after the controller method runs, and a couple of other spots here and there.

[00:01:48] **Adam:** And you can sort of inspect what's been going on in the request. So one of the things that we did was we wrote, I guess you could call it something inspired by a code coverage tool where, um, There's some code that does discovery and it writes to a database table like these are all the actions, the controller methods that could be run.

[00:02:11] **Adam:** And so we have a list of all the things that need to be tested and then as you use them it logs was it successful, was there an error, what was the page load time, that sort of thing. And that way we can tell what's been tested, what threw errors, what's performing poorly, and get through it all with a pretty high level of confidence that.

[00:02:33] **Adam:** Um, we're going to at least have minimal errors when we finally do go to QA and production with this. What is the

[00:02:43] **Carol:** code coverage tool you're using?

[00:02:45] **Adam:** Oh, it's all hand rolled. So, it's inspired by code coverage. It's, um, it's just like a way to be able to say, uh, we know we've tested everything, and, uh, we know that we found all the, at least all the obvious errors, um, and so it's just logging, you know, I wrote some code that does discovery and looks through our controllers and, and, um, inspects them.

[00:03:11] **Adam:** And for each controller method, it created a row in a database table. And that table has columns for, uh, like number of times it's been run, the last time that that row was reset. So we can, um, if, for example, one of the big things that happened in the last couple of weeks was we, uh, had a major overhaul to one of our, um, So we have a, an events module and of course events, you know, nobody's getting together in person right now.

[00:03:41] **Adam:** Um, so we found this was a good time to make a change. We wanted to add time zone support in part to support virtual events because, um, Oh, so you're not talking about like, you're talking about

[00:03:51] **Tim:** actual

[00:03:52] **Adam:** physical events, not like programming events. Yeah, that's

[00:03:55] **Carol:** why I was like, oh, he's talking about where people get together.

[00:03:58] **Carol:** I'm seeing it now. Not triggers, not

[00:04:00] **Adam:** events. Yeah. Meet space events. Yeah. Um, and. Uh, yeah, so adding time zone support was a big deal. It was a, the code, the branch was forked about a year ago and we only just landed it. A couple of weeks ago, um, thanks to, uh, the, the downtime provided by the coronavirus, at least for that module.

[00:04:21] **Adam:** Um, but as a result, uh, now that whole module had to be retested again on the new platform. So, um, it was easy to go back and reset just that section of the code in the, in the database and say, okay, these need to be tested again. So that, you know, it kind of It took a scenario where we were kind of scared pantsless, uh, of like, how the heck are we going to do this with any level of confidence?

[00:04:47] **Adam:** And it's, we're feeling great about it. We are currently at over 90% tested. That includes our API surface. That includes, um, end user facing as well as our customers. So they have sort of their own little backend admin area. Um, it's well over a thousand different actions. So it's, it's been going really well and we're really, we are pretty proud of it.

[00:05:11] **Adam:** I think this

[00:05:12] **Carol:** is when we should insert some clapping. That is awesome. Like 90% is huge when you're talking about code coverage.

[00:05:20] **Adam:** And of course, uh, you know, 90% we hit that. And then, um, then the boss is like, okay, well we need to put that aside for a few minutes and for a few days and work on this other project.

[00:05:29] **Adam:** So it's been sitting on the shelf for a week while I worked on this other. 90% is about as far as

[00:05:35] **Tim:** you ever get on anything in life. The last 10% is the hardest.

[00:05:39] **Adam:** I always like to say, you know, okay, the first 90% is done, and so now all that's left is the last 90%. Yeah. Who wants to go next?

[00:05:49] **Carol:** Oh, I can throw one out from this week.

[00:05:52] **Carol:** So for me, you know, you guys know I started a new job, right? So, um, I got super, super excited because, you know, I'm finally having code roll into production. And my code hits out, and you know, test through, everything's good, and gets to production, and everyone's like, woohoo, good job, you got your code out, and then about five minutes later, bust production.

[00:06:17] **Carol:** But luckily it's an area that everyone who's been there is like, this is why we never touch this. You know, we've renamed things throughout, you know, years where we know that a version's actually referencing a group ID, but you wouldn't know that because you've never looked back that far. So. I just had to go in and rename a few things, and then it worked fine.

[00:06:39] **Carol:** But it went from that immediate, like, woohoo, I have success. I've put code in production at my new job. And then, you know, production fails. And then I have to figure out how to undo everything that broke from it being broke, when I don't even know what the process is yet. So I had a nice failure this week.

[00:06:57] **Adam:** Nicely done. Yeah, it sounds like a

[00:07:00] **Tim:** failure in lower environment synchronization.

[00:07:04] **Adam:** Yeah,

[00:07:04] **Carol:** and I think if the integration processes would have been running lower, we would have caught it. But since we weren't doing all of the integration, it's just. It, it got skipped. The

[00:07:14] **Adam:** proverbial works on my machine. Right?

[00:07:17] **Adam:** So your triumph here is that you help them understand, uh, how their environment is not doing a good job at surfacing bugs before they make it to production. No extra charge. I am not gonna say that at the

[00:07:28] **Carol:** new job.

[00:07:28] **Adam:** Your process is great. , no extra charge.

[00:07:31] **Tim:** I showed you your flaws,

[00:07:34] **Ben:** right? We used to joke, uh, that you weren't truly a member of the team until you took down a production server.

[00:07:40] **Ben:** Mm-hmm.

[00:07:41] **Carol:** I need the dunks hat. Like, you know, that's what you need.

[00:07:44] **Adam:** Well, it's

[00:07:44] interesting

[00:07:44] **Ben:** to see how different team cultures deal with it. And how quickly someone who crashes production then deploys again. Yeah. Right. Cause there's the people who are like, immediately, how do I fix that problem? And I get back on the horse.

[00:07:56] **Ben:** And then there's the people who are like, uh, I'm not going to touch any code for a little while. What's that management

[00:08:02] **Adam:** track about? Yeah.

[00:08:05] **Carol:** No, for me, I definitely push up a fix real quick.

[00:08:09] **Tim:** So my triumph is also my fail. So I've been working, trying a very large credit card processing company that's out there that everyone would know.

[00:08:21] **Tim:** I'm not going to name names, but for years I've been trying to build a new product with them. They give you access to the developer.

[00:08:32] **Tim:** You can sign up and get access to their API. The problem is, is that once you get past that, it's extremely hard to get their attention to ever go to production. And so, like, for about four years now, we've been stuck in this kind of administrative limbo with them, um, trying to find the right person that we need to talk to in order to really get this thing going.

[00:08:54] **Tim:** And this week, uh, I was actually on PTO, uh, and I get a call. from one of our salespeople who say that this company, their product manager, reached out to him and I thought, great, awesome, my years of persistence has finally paid off. Nope, that wasn't it. They, they saw an ad in one of the journals that we put ads in for our company and he reached out to us.

[00:09:22] **Tim:** So we had a meeting with their product manager, and now it seems like all those roadblocks that I was hitting, coming from the developer side, got bypassed from the top down, uh, from the sales and marketing side. So, it's a triumph in that, you know, I'm going to get what I want in the end, but it's sort of a fail somewhere.

[00:09:41] **Tim:** Because it shouldn't be that hard to try to help sell someone else's product, because really it's a partnership kind of thing. So, I'm just happy that we're going to finally get it going after all these years.

[00:09:50] **Ben:** That's some serious stick it to it iveness, though. I don't think I've ever waited four years for anything.

[00:09:55] **Ben:** Yeah,

[00:09:55] **Tim:** the code's ready. You get to the question of, uh, well, so what's the pricing on this? And it's like, oh, I don't know. And then you get meeting shuffled for three and a half years.

[00:10:07] **Adam:** Oof.

[00:10:08] **Carol:** It's because those marketing guys are smooth talkers. They're like, we don't want to talk to engineers. You guys are not fun.

[00:10:13] **Carol:** We're just going to avoid this call.

[00:10:15] **Adam:** Yeah,

[00:10:15] **Tim:** what's funny is we talked to the product managers, so they're all like... So, you know, I, I do a lot of marketing for tech guys as well, too, but they're talking to our, to our sales guy. So, it's like, he can't help you. Let's talk to me. Yeah.

[00:10:26] **Adam:** So, you said that this, uh, kind of fixed your roadblock.

[00:10:30] **Adam:** Does that mean that the ball is now moving and that this product might actually get to see the light of day? Yeah, yeah, it seems

[00:10:35] **Tim:** like it. And it should be pretty quick because the technical side is done, so there's a few other relationships that we got to iron out with. This is all financial stuff. So, it's dealing with banks and credit cards and, and the like, so.

[00:10:48] **Ben:** So, actually, so my triumph. And fail kind of dovetailing with what Tim just said is it's something along the same lines if I may, uh, so at work I have the what I've been assigned work and then I have the self directed side hustle kind of work, um, and this week I deleted it. 67 files and something like 5, 100 lines of code of a feature that I was trying to build and get some internal traction for at the company, but unfortunately, it didn't get any traction whatsoever.

[00:11:23] **Ben:** Uh, so it was a, it was a fail in that. It was something that I've, I mean, dozens of hours and lots of passion into and nothing came of it. But at the same time, I feel like deleting it felt a little bit like a triumph. Like, um, I was able to detach from the code. And, uh, I think a lot about, uh, sunk cost fallacies and like constantly throwing more effort and time and money into something just because like, I've already thrown a lot of time, effort and money at it.

[00:11:53] **Ben:** And, uh, it feels freeing to be like, Nope, that's a dead end. I'm just going

[00:11:57] **Adam:** to stop right where it is. Yeah, I totally agree. That's both a triumph and a fail. Like, it's gotta hurt. You're kind of like... Yeah. Killing a pet there or something, but at the same time, um, like you said, it's uncost fallacy. You're, you're doing what's best for the business and, um, there's a, there's a odd, um, satisfaction in deleting code.

[00:12:18] **Adam:** Like it's less code that needs to be maintained. Um, yeah, so I, whenever I, I get to do something like that, like delete thousands of lines of code, I screenshot the, the little diff, um, graphic that GitHub shows us. You added three lines of code and deleted 10, 000. Yes. And like, yes, win.

[00:12:37] **Carol:** It's like, I'm sitting there drinking my wine at night, looking at those numbers going, ah, success.

[00:12:42] **Tim:** And it's something I think as you, as you do this job more and more. You, you, early on, you take your code really personally. It's like, it's, it's a part of you, right? It's your baby. And as you get

[00:12:55] **Adam:** older, you know,

[00:12:56] **Tim:** you have to, if you want to survive. Emotionally in this business, you've got to distance yourself emotionally from the code.

[00:13:03] **Tim:** You, you can't take it personal because something that was genius five years ago now is probably the bane of someone's existence and to feel that and to, to die on that hill and say no, you know, this is the best thing ever just because you wrote it. It's hard. I mean, it's hard. You got to have a level of humility and say, well, it did its job.

[00:13:24] **Tim:** It's time for it to die and don't take it personal. But that, that, that's sort of a growth thing. If you haven't hit that point in your career yet, you're going to, and you need to face it and accept it. Because otherwise, if you can't move on and realize that, Code just grows old and dies and it has nothing to do with you.

[00:13:42] **Tim:** So don't take it personal.

[00:13:44] **Adam:** Yeah,

[00:13:45] **Ben:** absolutely I always I always like to say that the worst code that I ever wrote was the code. I wrote six months ago Mm hmm. It just feels like I'm always six months Looking back, thinking, oh, terrible choices. Terrible.

[00:13:59] **Adam:** Oh, I love there's a, there's a VS Code plugin for, I think, what is it called?

[00:14:02] **Adam:** Um, not GetGutter. I think that was a Sublime Text thing. Um, there's a, I forget the name of it, but there's a VS Code plugin that shows sort of in a very low contrast your, uh, GetBlame at the end of every line. Um, and so I'm, I'm, Always the guy posting screenshots in Slack of what a hole wrote this awful code.

[00:14:27] **Adam:** And in the screenshot, you can see my name next to it. Yeah. Yeah, I've been on many of the screen

[00:14:32] **Carol:** You gotta be able to laugh at it. You just have

[00:14:34] **Tim:** to laugh at it. Yeah. I've been on many of the screen shares where they go, Hey, Tim, I don't know what this line's doing here. And I'm like, uh, commuted by Tim Cunningham, 2015.

[00:14:42] **Tim:** Like, yeah, you know what? I don't remember

[00:14:43] **Adam:** either. I think I've made those calls to you. You probably have when you worked with us, yeah.

[00:14:52] **Ben:** One that, um, I've, I've heard a number of times people say is, uh, strong opinions loosely held.

[00:15:00] **Adam:** And... Explain that. Like,

[00:15:02] **Ben:** that you can feel very strongly about doing something a particular way, but don't feel like it's a hill you have to die on.

[00:15:10] **Ben:** And if someone comes in and explains, well, actually, maybe we can do it this way. You're like, oh, okay. Yeah, you should be okay. I can, I can let go of that strong

[00:15:16] **Adam:** opinion now. Yeah. Oh, okay. I

[00:15:18] **Ben:** get that. But it's funny, because when Tim was talking about not being too emotionally attached to your code, I almost feel like...

[00:15:26] **Ben:** You

[00:15:26] **Tim:** struck there? Did I strike you?

[00:15:27] **Adam:** It hurt me a little bit.

[00:15:31] **Ben:** Because I am, like, super emotionally attached to my code, but at the same time, I'm not attached to it being correct. But I'm attached to it's success. So, like, if I deploy code and I see that there's a bug in an edge case, I see in the logs or something, or so, you know, support team raises, Hey, you know, this user can't do this thing now that we've deployed this change.

[00:15:56] **Ben:** Like, I feel super compelled to now take. Responsibility for that. And now I feel like, you know, I have to create a ticket. I have to make sure that that gets put in my backlog and I have to go fix it. So I, I do feel like there's a certain degree of leverage that I can have when I am very attached to my code.

[00:16:16] **Ben:** But at the same time, having the perspective where I can, you know, slash and burn it if it's not

[00:16:23] the

[00:16:24] **Adam:** right choice. Or

[00:16:25] **Carol:** someone else come behind you and slash and burn it. That's a harder bar.

[00:16:29] **Adam:** That's a harder one.

[00:16:31] **Tim:** That's sort of what I was talking about, where there's a part of the system that you originally architected.

[00:16:36] **Tim:** And now I'm off doing other stuff and they say, all right, it's time to refactor this portion and to start working on it. And you know, you know, I, you can't take a hundred percent cause a team worked on it. Right. But you started it and then other people took it. And now it's like now they're refactoring and it's like, just go like, all right, I got to let it go.

[00:16:55] **Tim:** You know, I, my way worked fine for many years, but it's like someone else has to deal with this now because, you know, always be proud of what you write, you know, when you push it, you should be proud of it. But at some point later in life, you're not gonna be proud of it anymore.

[00:17:11] **Tim:** Well, one, one term that I really love that I learned, I know you didn't come up with it then, but I saw it on. Your blog was CargoCulting. That term, I hadn't, I hadn't come across that until I read that on your on your blog. And I was like, man, that so describes.

[00:17:27] **Ben:** Explain that for the listeners?

[00:17:29] **Adam:** Yeah, I don't, yeah,

[00:17:30] **Carol:** someone should tell

[00:17:31] **Adam:** me.

[00:17:31] **Adam:** Oh,

[00:17:31] **Tim:** so Cargo, well, Ben, you, you, you, you told it to me, so you tell it to Carol.

[00:17:37] **Ben:** Alright, well, I hope I'm remembering it correctly

[00:17:40] **Adam:** now. We're getting old. I'll put you on the

[00:17:42] **Ben:** spot. CargoCulting is implementing practices. Because that's just what the team has always done and not necessarily doing them because they're the right way to do it or because they've been thought

[00:17:54] **Tim:** through.

[00:17:55] **Tim:** Yeah, and I, I looked up on the, on the wiki and sort of, it's sort of a throwback to where, you know, some primitive tribes, you know, they find a Coca Cola bottle and they don't know what it is and it becomes their god. They don't know how, you know, what it does. And it's sort of, sort of the same thing with cargo colting with code is that you have sections of code that no one really understands, but it works.

[00:18:16] **Tim:** And so they kind of just take that and they just keep moving it around and they keep supporting it, propping it up. And if there's bugs in it, they don't stop to break down how it works. They just start patching stuff onto it. It becomes sort of this sacred totem that you can't really do anything to because no one understands it, but as long as it's working, it's fine.

[00:18:38] **Tim:** That's sort of, you know, I've seen that in, in many organizations where it's, it's. Don't stop to think how the process is working. Don't fully understand the whole thing before you start working on it. Just make it work. Just keep, keep propping that, that false idol up. And yeah, that, I saw that term. I'm like, man, you know, not everyone, but there's a lot of people that just sort of follow that and I don't really understand the process, but I ain't got time to figure it out.

[00:19:04] **Tim:** So I'll fix this one bug and hopefully it's someone

[00:19:07] **Adam:** else's problem. I bet you that, uh, a lot of that code that people don't understand why it works, or how it works, or how it possibly works because it doesn't look like it should, um, I bet you a lot of that is, like, somebody's prototype that they're like, oh, we'll come back and we'll fix this later.

[00:19:24] **Adam:** Right, right. You know, it'll never make it to production like this, and then ten years later... This will be a day two product. Right. Yeah,

[00:19:31] **Tim:** yeah, that's, you know, that's one thing I think managers... People who manage the coders in the system really need to understand is that there is no such thing as a short term fix.

[00:19:43] **Tim:** There's no, I mean, sure, if... You don't patch things. Because years later, someone comes back and goes, well, that was just a short term fix. Well, it's been years later. If you can't buy the time, buy the time to fix it now and do things right, you're going to, eventually you're going to pay for it. You're always going to pay for it.

[00:20:04] **Ben:** That's funny. I was actually just looking through some code the other day. And I had commented something out from 2016 and I had, I put this huge comment in about like, this shouldn't be commented out, but it's causing a really bad performance problem on the database. And we'll come back and figure out how to refactor the queries to make them work.

[00:20:23] **Ben:** But for now, like, I'm just going to assume that it's going to be okay to comment this out. And, you know,

[00:20:27] **Adam:** four years later,

[00:20:29] **Carol:** one more time, 2016, this shouldn't be commented out in 2016. And today it's so commented out.

[00:20:36] **Adam:** Yep. Yeah. Nice. Yeah,

[00:20:40] **Carol:** we've all done it, we've all done

[00:20:41] **Tim:** it, it happens.

[00:20:44] **Ben:** Well, I'll tell you, it's one thing that I think about triggering off of something Tim said about people trying to take time to understand how something works.

[00:20:53] **Ben:** I, I think one thing that. Is a skill that I didn't necessarily think of as a skill early on in my career was being able to step back and just at a high level, understand request control flow, which sounds like, how could you program if you don't understand request control flow, but I think that, you know, if you think about what your browser is making requests to the server, and then the servers routing it to some sort of a controller, and then the controller is making a request to some other.

[00:21:24] **Ben:** You know, probably service layer or domain situation that's calling the database and the database is returning data, and then you're transforming the data and you're returning it to a a P I response and the browser's rendering it. I think there's a lot of people who like, don't necessarily have the, I don't know, again, like I, I hesitate to call the skill, but like they get very befuddled by the very procedural nature of how requests get routed and if something goes wrong.

[00:21:55] **Ben:** They don't necessarily always understand how you can even start debugging it. They're like, well, it's just, it's breaking. It's not returning what I expected. And you're like, okay, we'll step back and think about all the steps that you had to take in order to get the

[00:22:06] **Adam:** data. Right. Do you know

[00:22:07] **Carol:** the process? Do you know where it started at?

[00:22:10] **Carol:** And I think, I think we talked about that on the last show where it was like, you know, people know that little peek. Yes, and you need to know all of it to be able to do it correctly. But how did you

[00:22:20] **Tim:** learn that, Ben? I mean,

[00:22:23] **Ben:** Well, I think it's, you, it's a practice, I guess. You, at some point, you just, you're so focused on fixing a problem.

[00:22:33] **Ben:** And I think when the problem is not presenting its solution very clearly, you have to learn to step back and like question your inputs and outputs.

[00:22:44] **Adam:** Yeah.

[00:22:47] **Tim:** And that's one thing I always enjoyed about your writing, Ben, on your blog is, uh, you do step back and take a look at the whole process. Like, you're talking about the request flow when you break down everything involved in the HTTP request.

[00:23:00] **Tim:** Uh, those are always very informative because if you don't really at least have a high level understanding of that, you're going to get stuck in a certain, you're going to get stuck trying to fix the thing you know how to fix, and maybe the fix isn't there.

[00:23:13] **Carol:** Yeah, it may not even exist there. Maybe it's outside of that piece.

[00:23:18] **Ben:** 100%. I love debugging, actually. It's one of my favorite things, too.

[00:23:26] **Carol:** It's like there's this giant unknown that I have to just go solve, and I get super excited. When I can't figure it out, I'm like, okay, who can? And how did you figure it out? Because now next time I want to know, like, how you got there.

[00:23:41] **Adam:** You mean my CSI glasses?

[00:23:44] **Ben:** Well, I was gonna say, it's the closest that I ever feel like Sherlock Holmes and his like deductive abilities.

[00:23:50] **Adam:** So

[00:23:53] **Carol:** Adam suggested our topic for today. So Adam, what is it that you are so ashamed of?

[00:24:00] **Adam:** Yeah, I mean, I wrote it down as shame because it feels like that's a succinct way to describe it. But I guess I should start by saying it's not total shame. Like, you know, it's just, um, there's a, I have a monkey on my back, a chip on my shoulder, you know, something, it's just this mental block for me.

[00:24:16] **Adam:** And it's no surprise to you guys because we all come from a CFML background, but, um, I started my career doing CFML and it's taken me... So

[00:24:24] **Carol:** what is, what is CFML for people who don't know what CFML

[00:24:28] **Adam:** is? That's a good question. Is it CAML? Something? Yeah, fair, fair question. CFML is, uh, acronym for ColdFusion Markup Language.

[00:24:36] **Adam:** So people may have heard of the Adobe ColdFusion product as it's currently owned by Adobe. Prior to that, it was owned by Macromedia. Prior to that, owned by, I believe, Alayer. which is the company where I was started, um, and so it's been around just as long as PHP. They were both invented in the same year and, um, if I remember correctly, also the same year that JavaScript was invented.

[00:24:56] **Adam:** So we're talking old tech here, although, um, all of these things, JavaScript, PHP, and CFML, have all seen many revisions since then, obviously. Um, so the language has grown a lot and, uh, it continues to grow. I have kind of in recent years made a conscious effort to step out of that, um, out of that role or out of that, uh, yeah, we'll go with out of that role.

[00:25:21] **Adam:** And Try to branch out into other languages, other tools. Um, I'm doing a lot more with JavaScript. We do a lot, we, we have a ton of infrastructure on Amazon Web Services, um, including Lambda. We're doing, um, using Fargate, which is like Docker containers, um, on demand and, and orchestration of all that. Um, and we have a bunch of React.

[00:25:46] **Adam:** js apps. I've written some GraphQL code, but no matter how much I've done, and of course it never feels like enough because we have this giant legacy code base of CFML that we maintain, and For better or for worse, we continue to add to it because we don't have time to get everybody completely up to speed to the point yet where we can completely cut over to something that's not CFML.

[00:26:12] **Adam:** So as I mentioned or alluded to earlier, we are in the process of Porting from Adobe ColdFusion to Lucy, that is the open source CFML engine that we've been using. And it's, you know, 90 ish percent compatible depending on what features you use. But even though, you know, I've done all this other stuff, I've done some pretty advanced stuff with AWS and with Node and React and GraphQL, I still feel like I have this monkey on my back.

[00:26:42] **Adam:** I feel... embarrassed to admit in public. I wouldn't, I wouldn't want to attend ReactConf and be like, oh yeah, you know, 80 ish percent of my work is, is CFML. But I do, you know, I do react and stuff too. Like, don't, please don't throw anything at me. Don't judge me. Right. Like, so it's the same feeling that I had the time that I walked, um, into a New York Giants football game wearing my Philadelphia Eagles jersey.

[00:27:08] **Adam:** Um, I literally, this is not a joke, I was literally ducking flying beer bottles as I was walking into the stadium and multiple people tried to start a fight with me. Of course, they were probably drunk, but multiple people started, tried to start a fight with me, uh, you know, as we're squeezing through, uh, the, the doors to get into the stadium.

[00:27:28] **Adam:** Like, you know, you hear things like, nice haircut, and I'm like, you don't have a haircut? Like, that's the worst you could do is make fun of my haircut? But at the same time, like, You know it with enough of it out there it starts to to get to you just the fact that it's there. The difference with that analogy

[00:27:44] **Tim:** though Adam is that that'd become more like I think it would be more analogous to analogous to you walking into a New York Giants football game wearing a second tier rugby league.

[00:27:59] **Tim:** Put them in the

[00:28:02] **Adam:** comments. Let us know in the

[00:28:06] **Tim:** comments. Thanks a million for

[00:28:10] **Adam:** coming on, until we talk

[00:28:14] **Carol:** next time. We'll see you later. Okay.

[00:28:23] **Carol:** Clueless has no idea like what I'm even talking about. Yeah,

[00:28:27] **Adam:** exactly. They haven't heard of it or they have heard negative things and most people haven't seen it for themselves. Right. And it's funny because like I have made a wonderful career for myself and much of that was very proudly CFML. I can remember it wasn't that long ago that I was saying like, you can have all the negative opinions that you want.

[00:28:46] **Adam:** I'm going to come over here and I'll take the consulting gigs all the way to the bank. You know, like I was. Making good money. Still am making good money from doing CFML. But, um, for me, for my team, for our product, it's not the future. And so I guess because it's not what I want to be doing right now. And I, you know, I feel that stuff out there in the rest of the world that I really want to grab onto and like grab the tail of the dragon and have it fly off with me.

[00:29:13] **Adam:** Um, but it's not quite within reach yet. It's this, like I said, it's this monkey on my back. And, um, Yeah, like, like you said, it's something that, um, I know I shouldn't be ashamed of, but... For better or worse, I am. Yeah. I find

[00:29:29] **Carol:** myself when people ask, um, what languages I know, even though I've written, you know, CF since 2010.

[00:29:36] **Carol:** The first one I say is NET. I'm like, Oh, you know, I know C sharp. I know NET. Like, you know, I can write some front end and angular, you know? And then I'm like, Oh, and I know CF. And I don't know why. I don't know why that is because to me, CF hasn't been bad for me. The problems I've had with CF is poorly written.

[00:29:58] **Carol:** Yeah. I have that issue in any language. I have problems when people write. Like, I have problems when Angular doesn't work because you didn't write it right. So when I find it written correctly, it works fine and it's easy to understand.

[00:30:14] **Adam:** Yo, can

[00:30:15] **Ben:** I, I need to jump in because you just, you just. hit one of my pet peeves, which is, I hear this all the time on other podcasts, where people will compare two solutions for one problem, you know, two different languages, one problem, and they'll be like, oh, you know, I tried running, I tried building this thing in Ruby on Rails with ActiveRecord.

[00:30:38] **Ben:** And I had to process data, and it was processing, you know, a hundred records a second, and I did some back of the napkin math, and it would have taken, you know, 14 days in Ruby on Rails to, to, uh, to migrate all this data. So I was like, you know what, let me invest four hours into trying this with, uh, Golang, because I've been really interested in Golang, and they're like, And, you know, so I spent a Saturday afternoon writing this in Golang, and I ended up processing it in 12 minutes.

[00:31:04] **Ben:** And they're like, so their takeaway is, well, Ruby on Rails must be garbage because it would have taken four days. And like, to Carol's point, like, no, the code you wrote in Ruby on Rails was garbage. This is

[00:31:15] **Carol:** bad. You are good, not the

[00:31:17] **Adam:** language.

[00:31:18] **Ben:** Like, oh, that drives me crazy. Because like, you know, time and time again, You'll hear, the database is your bottleneck, right?

[00:31:28] **Ben:** People talk about network latency and all this stuff, and they're like, your database is your problem. So, immediately when someone talks about data access in one language versus data access in another language, and, and the, the language being the limiting factor, I'm like, mm, no, I think you're the limiting factor because the database should have been your problem, but you somehow made the language your problem.

[00:31:48] **Ben:** Okay, sorry, alright, it gets me very riled up. I think

[00:31:53] **Carol:** we've all, we've all seen it.

[00:31:55] **Ben:** Because I am Ben, and I am also a CFML developer.

[00:31:59] **Adam:** Hi Ben! Is this an AA group? What's going on? Shh, don't give away our secret. I mean,

[00:32:07] **Tim:** Adam, I think everyone at some point in their life, you know, we've all been coding a pretty long time.

[00:32:13] **Tim:** I've been, I mean... As a hobby coding since I was 13. I'm, yeah, I'm about to be 50, so, you know,

[00:32:22] **Adam:** wait a minute. You're too old for us. This, this what? The cool kid cards? . Alright, I gotta go.

[00:32:27] **Tim:** Uh, well I don't, I'm not a cool kid, but I played one on tv. Yeah.

[00:32:31] **Adam:** Okay. That's close enough. Yeah, so, I

[00:32:32] **Tim:** mean, but you know, I started my first programming job when I was 18, so I've been doing this a long time.

[00:32:37] **Tim:** At some point everyone is gonna feel like that because they're going to have picked up. They're going to work in some field, that's where it takes them, and then things are going to progress. That's just the programming world in general, is that the thing you cut your teeth on at some point is going to become passé.

[00:32:55] **Tim:** And so, that's just part of the growing process of realizing, you know what? It's like bell bottoms back in the 70s. You know, they were cool then, but... They ain't cool anymore, or maybe they are. You know, things come back, right? Yeah, they come back. You know, 30 years from now, when all these, uh, CFML machines need to need to play for support, you know, you can make a really cool retirement gig just, you know, keeping those things up and running.

[00:33:19] **Tim:** So, that's what the Cole Ball guys are doing now. Oh, they are. They're making it

[00:33:22] **Adam:** killing. They're killing it, so. And, like, something said that Ben said recently, um, was that, you know, your customers don't care. And they just care that it works, that it's, that it's not completely, uh, hideously ugly and, and that it's, you know, reasonably performant and that it works correctly.

[00:33:41] **Adam:** Well, I don't care about the layer.

[00:33:44] **Ben:** I don't know if anyone, uh, is familiar with Robert Martin, Uncle Bob. He's one of the, uh, the clean coders. He's part of the whole agile and, uh, solid principles. Um, and his, his back of the. envelope math is that the population of developers doubles every five years, I think he says.

[00:34:04] **Ben:** Wow. So his, his takeaway from that is, you know, when you're talking to a group of people, half of them or, you know, some huge number of them have only been coding for a couple of years. And when I think about where I was as a young developer, like That's when I was most ride or die ColdFusion. I was like, best language ever, like, you guys are all stupid if you don't use ColdFusion.

[00:34:26] **Ben:** And now that I'm, you know, older and smarter, hopefully, it's much more I'm just trying to get the job done and using the right tools at the right time. But, you know, if you have a huge population of people who have been coding for less than five years, Most of them haven't even heard of ColdFusion. Yeah.

[00:34:42] **Ben:** Like, it makes sense that people are like, why would you even do that? Because they're at the point in their career where they're most ride and die for whatever they're learning to cut their teeth on, as Tim said.

[00:34:51] **Adam:** Yeah.

[00:34:53] **Tim:** Whatever they first got passionate about, that's gonna be the thing that, you know, that they're most excited about and evangelist for.

[00:35:02] **Tim:** And eventually, you know, another five years from now, that'll be passé and they're gonna feel silly and listen to this podcast and we're just here to say... It's okay.

[00:35:11] **Adam:** You're in good company. Okay. Virtual hugs. Well, so, I mean, while we're, obviously this is, if this is going to be the first episode of our podcast, then it's, it's pretty obvious that we're, you know, kind of figuring this out as we go.

[00:35:23] **Adam:** But one of the things that I've been kind of doing is drawing inspiration from other podcasts that I like. And there's this, this, uh, concept that I picked up from the No Dumb Questions podcast with, uh, Dustin from Smarter Every Day and a friend of his. And that is, uh, the concept of a life with chapters.

[00:35:41] **Adam:** Um, and, and when you feel yourself moving from one chapter to another, it can be unsettling, it can be, um, kind of scary, but at the same time, um, it should be celebrated. Like it's, it's the start of something new and exciting. So when it came up in their podcast, uh, Destin was quitting his job as a... literal rocket scientist, uh, like a rocket, uh, uh, ballistics engineer, I think.

[00:36:06] **Adam:** Um, and, and he was going to go back to school to get a PhD and they were just, you know, celebrating a life with chapters and that, that really obviously stuck with me cause that was a long time ago and, and I still think of it regularly now.

[00:36:19] **Tim:** Yeah, that's true. Yeah, life with chapters, because we all have them.

[00:36:23] **Adam:** The hardest part is turning the page

[00:36:24] **Tim:** sometimes. It is. Yep.

[00:36:28] **Ben:** Well, it's so hard to go from, in one context, you have so much historical understanding and tribal knowledge about how stuff works, and you can lean on that at every moment of the day. And then to start the next chapter, where you're going to the documentation online and you're looking at Stack Overflow for, you know, how you do.

[00:36:50] **Ben:** String searches. I mean like basic stuff and it's incredibly

[00:36:54] **Adam:** humbling. Yeah.

[00:36:55] **Carol:** It's intimidating. It's intimidating too. To me, it's like, it's terrifying to not know and to not know like what I've known for so long. It's hard to switch.

[00:37:08] **Adam:** It's an interesting thought about Stack Overflow. Like, it just made me realize, you know, I've been, I've been a longtime user of Stack Overflow.

[00:37:14] **Adam:** I followed the podcast before they launched and everything. And, um, my user ID number, I think it's like, it's triple digit. I think it's like 751 or something. Um, so I got, you know, I was on the, the, the, um, you know, if you, if you want to become one of our beta testers, sign up on this Google form sort of thing.

[00:37:32] **Adam:** And, uh, so that was, that was fun. Um, but it, it, what it made me think was the. Like, there was this period in my life, this chapter in my life, where I spent a ton of time on Stack Overflow, not just, um, helping other people, but also asking questions for myself, um, and I can't even tell you the last time that I didn't get to Stack Overflow via, like, a DuckDuckDuck, DuckDuckGo search, um, Because, uh, it's just, it's not a place where I spend time anymore.

[00:38:03] **Adam:** Like it's, it's a great resource. I love it. I still participate while I'm there, you know, I upvote and downvote and flag things as, as appropriate while I'm there, but I don't choose to spend my time there, right? Like it's, it's a tertiary resource for me. And I think that when I do, like, finally flip this page where CFML is kind of fading into the background for me, and whatever the next thing is, it's probably going to be React.

[00:38:30] **Adam:** Like, full, I guess, front end, back end, full stack, server side React and everything, too. I'm sure that I'll be spending a lot more time on Stack Overflow, uh, as a consumer.

[00:38:46] **Ben:** It's interesting. Everybody has different, uh, learning strategies. And, um, I, and everybody learns most effectively in different ways. I'm curious. So when I start to learn something new, I have this like phased approach where phase one is typically like Neo in the chair, plugged into the matrix. Like I want to read, I want to read two books on the topic before I even write a line of code just to like.

[00:39:12] **Ben:** I had this big peripheral vision of what the, of what the landscape even is. And then phase two for me is typically, okay, now let me start to have little R and D projects, you know, to do lists. And how do I create this little, you know, list detail kinds of situation. And then that sort of naturally. Segues into all of the, I'm finding Stack overflow on my, on my Google searches and, and so on and so forth.

[00:39:42] **Ben:** Um, I'm, I'm curious to hear how you, it, it seems, it seems to me like I, uh, books are going out of favor for a lot of people. I don't if I'm a dinosaur in that respect. And then you blog about

[00:39:51] **Tim:** it too. Yeah.

[00:39:52] **Adam:** Yeah. Yeah. Well that, so a lot of people believe, and I'm one of 'em, that teaching is an important part of learning.

[00:40:00] **Adam:** Um, you know, yeah. Hundred percent. When you're trying to, uh, prepare materials or, or even to just get through a conversation where you're teaching somebody something, it forces you to think about things differently. How do I simplify this? How do I make it relatable? How do I, you know, compare it to something that they're already comfortable with?

[00:40:18] **Adam:** Um, and that might help you understand it better than you did before. So I've written a book about, um, REST APIs. And I started writing that book because I felt like I've been working on in this field. Um, specifically API design creation and consumption for, I think at the time I had been working on that sort of stuff for between five and ten years and I knew it like the back of my hand.

[00:40:45] **Adam:** And I was like, okay, well, this is something I'm clearly, I hesitate to call myself an expert, but I'm, I'm clearly pretty good at. And I feel like I enjoy teaching and enjoy sharing knowledge. And at the time my blog was fairly popular. And so I, I wrote a book, um, and I learned way more in the process of writing that book and doing the research to, you know, uh, shine light in the dark corners, um, than I, than I had known before I started.

[00:41:12] **Adam:** And it was, uh, a great process for me. I learned a ton. Um, so I can only, I can only, uh, I can't think of the word. What Bill was talking about,

[00:41:25] **Tim:** about learning something new. Um, I'm kind of like you in that regard. I'm not so much Neo up front. I'm a little more impatient. I just want to go to like a very simple tutorial.

[00:41:35] **Tim:** It's alright. Give me the basics of this first. And then I have sort of a little pet project. It's not... anything work related. I just had a thing, you know, that maybe in my personal life, I have a little idea that I wanted to work on or, you know, something or some, a friend of mine has, hey, you know, could you do this?

[00:41:53] **Tim:** I'm like, all right, I'll use this to maybe learn this technology or new language or whatever the new thing is, and then build it. And then in the process of building something that I actually. Slightly care about, but don't really care about. You know, it's not life or death or, or it's not your job. Um, you know, learn, learn the skills through that.

[00:42:14] **Tim:** Of course, you don't get a hundred percent. You're always going to run into something later when you actually are doing it for real that you didn't run into in your pet project. But that's the way I do it. Uh, I wish I had the, the chops that you do to just. Take the extra step and blog about it later, because I think that would help me retain it, because I find I'm always having to go back and do a Stack Overflow search to figure out, all right, I know I know how to do this, so I Google it, and then I go and reread it.

[00:42:38] **Tim:** The simplest thing, yeah. Reread it, and I'm like, oh yeah, yeah, that's right, that's how you do it. I just need that. But maybe if I search my own blog,

[00:42:46] **Adam:** I was going to say the best thing that ever happens to me is when I'm like, I don't know how to do this thing. Let me Google it. And I, I do. And then it takes me to my own blog when I wrote about it.

[00:42:53] **Adam:** And the blog post is like, I'm writing this for future me because I know I'm going to forget. So

[00:42:58] **Tim:** on your own

[00:42:59] **Adam:** stack overflow answer. Yeah. Done that too.

[00:43:02] **Ben:** So one, I can't underscore how hugely helpful it has been to write things down. And in fact, um, I don't know if DuckDuck, Craig, I guess DuckDuck goes a search engine out of browser.

[00:43:13] **Ben:** It is, yeah. But in Google Chrome, you can go into the settings and you can hook up I don't know what the right term is. Like these little short tokens that will then become search engines. Yep. And I go and I set up the token Ben to point to my own website because I know that I've written about something.

[00:43:31] **Ben:** So I'll just do like Ben, Lucy, CFML, Regex. And I'm like, okay, now here's all my posts via Google from Regex. Yeah. And I, multiple times a day, am I looking up stuff that I wrote? Because I know that I knew it, I just don't know it right now.

[00:43:51] **Tim:** It's like I tell my kids, never memorize something you can Google.

[00:43:54] **Tim:** Right? That's just a waste of headspace.

[00:43:57] **Adam:** Yeah. It's funny because, uh, that makes me think of all the times in school when um, people would tell you like, are you gonna have a calculator with you for the rest of your life? You have to learn how to do this math. I'm like, well, look at me now. Yeah. Look at me now, Mrs.

[00:44:15] **Adam:** Gallagher. I do have a computer in my pocket everywhere I go.

[00:44:21] **Tim:** I don't know if we helped you with your shame, Adam.

[00:44:24] **Adam:** Uh, you know, honestly, I think so. Uh, you know, talking about, just talking it through, talking about life with chapters and um, just sharing and, and knowing that you guys kind of feel similar. That helps. We've been in the same boat. Yeah. Yeah. One phrase, I forget

[00:44:43] **Tim:** where I heard it, but I, I stole it and used it at a conference I spoke at one time was, never compare your beginning to someone

[00:44:52] **Adam:** else's middle.

[00:44:54] **Adam:** Yep. I, I, when, as soon as you said, there was a phrase that you spoke at a conference, I was like, light bulb. I knew I was there in the room when you said it. And I knew exactly what was going to come out of your mouth. Yeah. So

[00:45:04] **Tim:** that's when I heard that, that it stuck with me because it happens so much, you know, early on you, you look up to people and you're like, Oh my God, they're, they're so amazing.

[00:45:13] **Tim:** And you talk to them and they're like, they're the normal people. And then later in life, some people come up to you and say, they're doing the same thing to you and you don't feel any different. Um, the issue is where you are, where you are in your journey. What chapter are you on? Um, you feel, you know, you might feel right now like you don't know anything.

[00:45:33] **Tim:** Other people might be looking at you thinking, thinking, you know, a lot more. It's because you're just in different parts of the journey. And if you try to compare those where you are right now, what chapter you're on now, it's impossible to compare. So it's a worthless exercise. It's self defeating. So don't do that.

[00:45:49] **Tim:** Just, you know. Yeah, yeah. Do your best and keep, keep moving forward. Keep turning chapters.

[00:45:54] **Adam:** And the other thing that is comforting when I'm having those dark thoughts of shame is that, uh, just the knowledge that, you know, 90% of what I know is concepts and approaches and algorithms. And yeah, the other 10% is syntax of this particular language, but I can learn the syntax of another language and apply those same, uh, strategies and algorithms to That and be productive there, too.

[00:46:19] **Adam:** Having the brain

[00:46:20] **Carol:** to do what we do transfers easy to languages. Yeah. Like, that's kind of what I've found out. That, like you said, it's all syntax. It's all about figuring out how to make it execute in a different

[00:46:31] **Adam:** language. My kids ask me sometimes how many languages I know, and I'm like, well, you know, uh, three, four, five, six or seven.

[00:46:39] **Adam:** Only English as a spoken language. But, you know, code languages, you know, it's up there a lot. And as we were

[00:46:45] **Tim:** talking earlier, it's the problem solving. It's really all about problem solving. Got those skills, you know, and keep honing them because you never, you never graduate from problem solving. There's always new problem.

[00:46:59] **Tim:** Yeah. And that's, that's actually the best and worst thing about our jobs.

[00:47:04] **Carol:** Yeah. It's kind of, it's kind of crazy. I volunteered last year as the band booster president and everyone like The moms are all like, how do you just figure this stuff out? Like, how do you get all of this done? I was like, you understand this is what I do for a living, right?

[00:47:19] **Carol:** Is I find a problem, I fix it, I move on. I find a problem, I fix it, I move on. I find like, I just repeat the cycle over and over again. I was like, so doing it in code isn't that much different than doing it in my life. You just problem solve. That's it. Find the solution. If you don't have the solution, someone does.

[00:47:38] **Carol:** Find that person.

[00:47:41] **Ben:** There's a, I don't know if anyone here has seen the movie, The Martian with Matt Damon.

[00:47:45] **Adam:** Of course. Just, you know, like 15 or 200 times.

[00:47:49] **Ben:** So I don't want to spoiler alert here, but I guess it's, it's,

[00:47:53] **Adam:** it's a couple, it's old enough. Past the watershed.

[00:47:56] **Ben:** Right. So, so the basic premise of the movie is that he's on Mars, lots of stuff goes bad, and then he has to just figure out how to make it all work.

[00:48:03] **Ben:** And, uh, at the very end of the movie, he's back on earth, presumably, and he's teaching this class to the future astronauts. And he, and he says something along the lines is along the lines of something's going to go wrong inevitably, and all you have to do is solve a problem and then solve the next problem and then solve the problem after that.

[00:48:24] **Ben:** And if you solve enough problems, you get to come home. And I, and I think about that at work all the time, like. Stuff's always going wrong. Something's always breaking in production. Like, there's always bugs in the code. I'm just going to keep solving one problem after another until I get it done. Oh yeah.

[00:48:42] **Tim:** My kids are annoyed by how much I

[00:48:48] **Adam:** watch that movie. And the, the, the thing is like, they don't know the half of it because I read the book at least once a year or two. If you haven't read the book. Oh my god, that's amazing. Like, Ben, have you read the book?

[00:49:02] **Ben:** I'm not even sure I knew it was based

[00:49:04] **Adam:** on a book. I didn't know it was based on a

[00:49:06] **Tim:** book.

[00:49:06] **Tim:** The Audible book is awesome too.

[00:49:07] **Adam:** Oh, yeah, it's,

[00:49:08] **Ben:** it's it. I'm

[00:49:09] **Adam:** Audible all the way. It's Audible. It's Audible. It's Audible. Oh, the Audible book was by, um, it was read by Will Wheaton, wasn't it? No. Oh, that must have been a different book that I was thinking of, because I, there was a book that I re read, uh, multiple times, like I had read it on paper, um, and then, like, I found out that the Audible book was read by Will Wheaton.

[00:49:29] **Adam:** I was like, well, now I have to get that. Probably Ready Player One. That, yeah, okay, that was probably Oh, that was good. Um, but anyway, so you, you were talking about how many problems he has to solve to come home in the movie. The, the movie doesn't even, like, do it justice. There are so much worse, so many more problems, so much more difficulty that he has to get through in the book, and it is Amazing.

[00:49:51] **Adam:** I love it. Can't recommend it enough. Well,

[00:49:54] **Tim:** it's kind of a little off topic, but I was, when the movie first came out, I was telling one of our marketing people about the premise of the story that, you know, it's this man who did a team that gets, they go to Mars and he gets left behind and survives. She goes, is it based on a true story?

[00:50:11] **Tim:** Like, no, no,

[00:50:12] **Adam:** it's fiction. Not yet. Not

[00:50:13] **Tim:** yet. And that man was Elon Musk. Yes.

[00:50:19] **Adam:** I almost did a spit take.

[00:50:24] **Ben:** Well, talking about skills being transferable and, and... Intellectually, I understand that. Obviously, there's a lot of fear, uncertainty, doubt when it comes to whether or not I can actually apply those in a new context. But it does make me think of when people talk about solving problems in an idiomatic way within a particular language, like, this is, this is idiomatic Ruby, or this is idiomatic Golang.

[00:50:51] **Ben:** I always, We should say, I

[00:50:56] **Adam:** think, that idiomatic means, like, the blessed way, right? Yes, yes. The right way to do it. Yes. Where have you been?

[00:51:02] **Ben:** Well, and going back to what Tim was brought up earlier about cargo culting, I always think to myself that idiomatic just means that's the way people have been doing it.

[00:51:13] **Ben:** It doesn't necessarily mean it's the right way to do it. And ColdFusion, maybe for better or worse, I feel like there's a lot of people doing The same thing a lot of different ways in the course. So

[00:51:23] **Adam:** many different ways. Yeah.

[00:51:25] **Ben:** And, and so I think about other languages and I'm like idiomatic golang, like that's.

[00:51:30] **Ben:** What does that even mean? Are you guys not solving the same problems that we're solving? Because I'm pretty sure that if I solve the problems, I understand how to solve. It may or may not look like the code you wrote, but I, I, I just never felt comfortable with the term Idio. Idiomatic.

[00:51:45] **Tim:** And I have to back up and apologize.

[00:51:46] **Tim:** Adam The Martian has been read by Will Wheaton as well. The one I have is a different, a different, but yeah, he did, he, they, they released it with him doing the auto audible, the reading. So I apologize,

[00:52:00] **Adam:** Well, I forgive you. Thank you. Who else has read it? Because I know there's more than one, right? Yeah, I've tried.

[00:52:07] **Adam:** It won't come up on my phone right now. Okay, I'll look

[00:52:14] **Tim:** it up. Google

[00:52:15] **Ben:** it. One thing that, one thing you said, Adam, made me think about also where we're coming from as a group, because we've all not only been in the co infusion world but in the programming world in general for

[00:52:29] **Tim:** quite a while. Mm-hmm.

[00:52:31] **Adam:** and, um, 10 plus years.

[00:52:33] **Ben:** Yeah. And, and, and I think about, and we touched on this in the last call, where because of where we started, there were certain responsibilities that we had to have. That maybe people today don't necessarily have to have the breadth of responsibilities that we typically did. Um, and, and you talk about, you wrote a book about REST and you're also now learning more about, uh, GraphQL.

[00:52:59] **Ben:** And, and I always think about what problem does it solve? Right? When someone comes to me and says, Oh, you shouldn't program in ColdFusion, you should program in Golang. I'm like, well, what problem does it solve that... I can't solve today. And it's an interesting conversation because you lose perspective on where other people are coming from sometimes.

[00:53:17] **Ben:** So, and this I find to be particularly meaningful in the GraphQL world where people are like, well, GraphQL really allows me to quickly get new data for new pages without having to write back end code. And in my perspective, I'm like, just write the back end code. And you forget the fact like, oh, I'm talking to someone who's only been programming for Five years and doesn't necessarily know how to write SQL or doesn't even have access to the back end You know server to write new

[00:53:43] **Adam:** endpoints.

[00:53:44] **Adam:** Well, so you're talking to the API guy. Do you want to dig into this?

[00:53:48] **Ben:** And but you know, I think it's it's just you lose sight of everybody's coming from such different places. Yeah And it's, and it's, um,

[00:53:57] **Adam:** So I think what I would say is sometimes there's an answer, right? Like, so you're, you know, somebody says, Oh, you should really be using such and such other tool.

[00:54:06] **Adam:** Um, 99 times out of a hundred, I would agree with you. Like, it really doesn't matter as long as you can get the job done. That's all that matters. But sometimes, um, like if, if you want to write a CLI. application right now. Um, you technically can get it done using CFML and some other tooling with uh, command box and some other stuff.

[00:54:27] **Adam:** Um, but, and it'll work and that's fine. If it works for you, then great. There's nothing wrong with that. But, uh, if you wanted to, if you need it to be particularly performant, if you're using this as, as one link in a chain of tools that are going to be processing massive amounts of data and performance is important, then you need something that's going to run faster than a CLI written by somebody written in CFML.

[00:54:49] **Adam:** Like, the startup cost of that is just, uh, comparatively astronomical. Um, and that was part of one of the motivators for me to learn Node in the first place, however many years ago. I was like, oh, I can write CLI apps with that. And it's JavaScript, and I know that. I've been doing that on the web a long time, but it's now, it's, it opened up a door to a new paradigm for me.

[00:55:09] **Adam:** CLI and server side stuff, um, was, was awesome. Yeah, I, I

[00:55:15] **Ben:** wholeheartedly agree that they're definitely the right tool for the right job. And sometimes the rightness of the tool is much more right than it is in other cases. Um, but I don't know. I don't even

[00:55:29] **Adam:** know where I was going.

[00:55:33] **Ben:** Oh

[00:55:33] **Tim:** yeah. So looking at it, here's my take on it. Um, here's

[00:55:38] **Adam:** what I assume. Here's what I assume it's for. So it sounds like with GraphQL you can

[00:55:46] **Tim:** get many resources in a single request. So it sounds to me like you're doing API calls and that's really all you can do. Is it API calls? I'm dying over here to explain it.

[00:55:55] **Tim:** Yeah, so this is, yeah, here's a complete hot take of an ignorant person. Yeah, I don't quite get, why would you, I guess it consolidates a bunch of

[00:56:06] **Adam:** calls? Can someone explain this to me? I don't know what it would be, I don't know what use case. Can I please? Okay, so let's, um, let's start with the problem. So you, you have a REST API.

[00:56:18] **Adam:** Let's talk, let's just say like a blog, right? So you've got, um, comments and, uh, or let's start from the top, right? So you've got like authors and their posts and the posts have comments and maybe the comments can refer to other comments, that sort of thing. And so if you want Everything relevant about one particular blog post, then you have to like, okay, you get the, you get the post, and that tells you like the author ID, and you have to go fetch the author.

[00:56:43] **Adam:** That's a second request. And then you get the list of comments, and some of those have like, you know, whatever links to other things. Um, and so the, one of the I, for, for my memory and I'm, I'm, I'm not an expert in GraphQL. I've barely, I haven't a GraphQL API in production. So that, you know, I've met the minimum level of capable of talking about this, but I'm not an expert on it, but I can, but I can explain some of this.

[00:57:08] **Adam:** So, um, one of the foundational reasons that GraphQL exists and the way that And the reason that it works the way it does is that, um, it lets you get all that data in one request. So part of the, part of the problem is that the round tripping of the request is a lot of additional latency. Um, whereas if you can make it all in one request, then, then that's fine.

[00:57:36] **Adam:** And to Ben's point, if you can... predict the way people are going to need this data and, and provide one REST resource that provides all the data necessary in one lump, then that's, that solves the same problem. But where GraphQL kind of excels is you can kind of define, you're defining data types, right? So think of it like TypeScript or something where you're saying, okay, these are, this is my posts, and this is my authors, and this is how comments, and comments have a different type of author, and this is how they all interrelate to each other.

[00:58:04] **Adam:** And then you can write client side. You can write a query that says, okay, here's an ID for a post and these are all the details that I want about it and I can go as deeply nested in the tree as I want. So I can, I can like find a post and it has comments and the, the, the comment happens to be written from another author on the same blog and I can go find the posts of that author and the comments on those posts and you can go as deeply nested down the tree as you want.

[00:58:29] **Adam:** And that is entirely client side driven, and it doesn't require any additional rewriting of the resources or the, the, the jobs on the server side of things. So it's a way to avoid round tripping. Yeah. To be able to get it without having... I mean, there's other benefits too, but... Yeah. Alright.

[00:58:45] **Tim:** I mean, that's kind of where I was kind of headed with.

[00:58:47] **Tim:** And, and, from, to Ben's perspective, I'm coming from it, like, I'm the guy who's going to be writing the API and writing the client that's consuming it. So if I run into that problem... I'm just going to create an endpoint that does that, you know, I could see that if you're, if you're working on an API that it's someone else's API, that would be a fantastic tool.

[00:59:05] **Adam:** Yeah, yeah. So that like the Facebook API is probably where this thing whole, whole thing got started. And, you know, GitHub has a pretty good GraphQL API, so like kind of, it's a good way to explore somebody else's data. But if

[00:59:16] **Tim:** you're writing both sides of it, it seems like extra

[00:59:19] **Adam:** work.

[00:59:20] **Ben:** Well, and then, and tying back again to the whole.

[00:59:24] **Ben:** Uh, starting point of, of this segment about atoms. Deep feelings of shame that, that everybody is coming at it from a different perspective and that there are people who would look at him writing ColdFusion and be like, that's silly. But then you start to talk to them and you realize that they don't know how to do half the things that Adam knows how to do.

[00:59:47] **Ben:** And it's, you, you sometimes lose that finer detail in the, in the sort of butting of, of heads or locking of horns on, on specific technologies.

[00:59:58] **Carol:** I find myself trying to not, um, challenge people on the way they want to do something. Instead, I just want to understand why they chose that and what got them to that path.

[01:00:11] **Carol:** Because even if I don't agree, it's, it's still somehow they ended up there and I want to understand more of how they got there.

[01:00:19] **Tim:** Yeah, that that's one of the biggest questions when someone comes to me with a problem that they say, hey, I need help with this and they're focused on the bug. I always have to step back and say, all right, what's the problem?

[01:00:31] **Tim:** What are you trying to solve here? Why are you even asking me that you think this is an issue? Because you're stepping back and it's the same thing with these technologies. You know, we have a lot more tools now than we had 20 years ago. Right. So 20 years ago, the kind of the tools did everything and now you have tools that only solve a certain slice of the entire stack.

[01:00:54] **Tim:** And so, you know, if you only know this one tool that does this one thing, you're going to want to use that one tool for everything. But that's not necessarily perhaps the best way to go about it. Be familiar with, with a lot of tools. And, uh. Maybe some are better than others.

[01:01:14] **Ben:** Oh, it's so

[01:01:14] **Adam:** complex,

[01:01:18] **Ben:** my brain hurts. I, I was listening to a podcast. I can't remember which one. This was a while back and they were talking about how you always hear the term, the right tool for the job. And they said, it's. It's actually the right tool for the job for the team at that particular point in time and like nobody ever thinks about that.

[01:01:38] **Adam:** I feel like I heard that. Do you know what podcast it was on? No.

[01:01:42] **Tim:** No, I do not. It's on this one now. I know where it was. You heard it here first. Or second.

[01:01:54] **Adam:** Okay, well, is there more to say?

[01:01:58] **Ben:** I was just gonna say that I just love programming

[01:02:00] **Adam:** stuff.

[01:02:01] **Ben:** So say it. I just love programming stuff. So I feel a little bit, because this started as a shame topic, I think I immediately reverted into like, old man, get off my lawn, my technology is great mindset. But like, most of the time when I'm talking about technology, it's usually, this stuff's so exciting, I love what I do.

[01:02:22] **Ben:** All I want to say is that in future episodes, I'm going to be more positive than I was this time. I don't think

[01:02:30] **Adam:** you came

[01:02:31] **Carol:** back. I think today was positive. I

[01:02:33] **Adam:** don't think it was bad. Yeah, no, even I, you know, the person with the shame, was looking at it through a positive light. Overall, I think it's just what it is, is it's, uh, you know, for me, this is kind of like a therapy thing, but, uh, you know, this is me admitting to myself that there are negative feelings there and that, um, you know, it's normal to have them, but at the same time, like, I, I shouldn't feel, um, that they are correct or that, um, I have to.

[01:03:07] **Adam:** Feel that way, or that I owe that to people who have had the privilege of not working at CML. Lucky _(quack)_ s.

[01:03:17] **Tim:** Well, I mean, you know, it's like, remember high school and the people that you cared about there at

[01:03:22] **Adam:** Biggins? Do you

[01:03:24] **Tim:** remember high school? I barely. But now you look on Facebook and you're like,

[01:03:28] **Adam:** why did I...

[01:03:29] **Adam:** Walk uphill both ways. Now

[01:03:31] **Tim:** you look on Facebook and you look at these people and you're like, why did I ever care what they think? Right. It's the same thing. It's like, you know, so what? You, you, you program ColdFusion, you, you bit your teeth on that, you know? So what if someone doesn't like it? He got you paid.

[01:03:45] **Adam:** Yeah. They're probably looking for a job. Yeah.

[01:03:49] **Carol:** I have very little competition when I'm in the market looking for a job.

[01:03:54] **Adam:** Heck yeah. And, and, well, so, I mean, if we're on the topic, uh, you know, we are, I work for a really small company. Uh, there's five of us right now. Three of us are like full time coders, one sort of part time and one that's only like operations and, and, um, support sort of stuff.

[01:04:11] **Adam:** And. It's been kind of difficult to get to those five people, um, you know, hiring people as a really small company. We can't really yet afford to hire people that are coming on with zero knowledge of what we're doing. You know, as a, as we talked before about how the skill can transfer and then you just have to learn the syntax, um, CFML.

[01:04:36] **Adam:** Can be somewhat difficult, um, or finding people that, um, I think more often you'll find people that have worked with CFML for a while, but that if they haven't been super passionate, like the type to attend conferences and listen to podcasts and all that sort of thing, they Really don't have, they're, they're not at that like sort of senior developer level, um, where a company as small as ours really needs everybody to be for a little while longer before we can do more of our own in house mentoring.

[01:05:07] **Adam:** And, and, um, I don't know, I'm kind of reaching here for like a, a grow your own crops sort of metaphor, but it's not coming to me. So I think you'd be surprised, honestly, maybe. Um, but, uh, you know, it's, it's something that we want to do. Um, but, uh, it's, it, it's been. Difficult to find a way to do it. Well, thank you guys for doing a podcast with me.

[01:05:33] **Adam:** This was fun. Yeah, it was exciting. Yeah, I had a blast. Looking forward to doing more. Yeah, I hope we

[01:05:37] **Tim:** talk less about CFML in the next episodes, so.

[01:05:41] **Adam:** Please. I want to be a little bit more general. Yeah, oh yeah, for sure. And, and, uh, you know, help, let's, let's all push each other to the next chapter.

[01:05:51] **Tim:** Love it.

[01:05:52] **Carol:** All right, well that's going to do it for us today.

[01:05:54] **Carol:** Thanks

[01:05:55] **Adam:** for listening.

[01:05:55] **Tim:** Hey, if you like the show, please share it with a friend. Don't just think about doing it. Pick three names, three names right now who you think enough. One, two, three, okay. On your contacts, send them an email and suggest they listen. More than anything else, what we need right now is word of mouth referrals.

[01:06:11] **Ben:** And after that, if you're still feeling generous, please rate us on iTunes or wherever you get your podcasts. That would also be a huge help. And thank you so

[01:06:19] **Adam:** much for your support. And if you have something that you'd like to hear us discuss on the podcast, reach out to us on Twitter or on Instagram. On both of those platforms, we are @WorkingCodePod.

[01:06:30] **Adam:** And on Twitter, our DMs are open if you want to submit your topic anonymously. So I guess with that, thanks for listening and we'll catch you guys next time.

[01:06:58] **Adam:** I

[01:06:58] **Tim:** think Adam just died. COVID.

[01:07:04] **Adam:** Water went down the wrong pipe. Got the Rona. COVID. Got the Rona. So that's one of the reasons that we're doing multi track recording. So you kept talking while I was choking, which is great. Am I supposed to be recording too or something? No, but uh, so since we did a multi track recording, if my mic picked any of that up...

[01:07:21] **Adam:** Um, Oh, I see. Then I can just cut that out. It's four instead of one. Okay. Right. It'll be just your microphone in that case. Okay.

[01:07:29] **Carol:** That's a setting you can do.

[01:07:32] **Adam:** Yeah.

[01:07:33] **Tim:** Does the host do that?

[01:07:35] **Adam:** Whoever's recording? Yeah, whoever's recording. It's a setting in your Zoom. Good job, man.

[01:07:43] **Ben:** I followed the directions. That's

[01:07:45] **Tim:** the hardest part.

[01:07:46] **Adam:** Oh, man.

[01:07:47] **Carol:** You read

[01:07:47] **Adam:** them, that was step one. Yeah, you revoked your man card

[01:07:50] **Tim:** for reading directions.

[01:07:53] **Adam:** I can make it up. Ben will just lift you above his head. I'll bench press you above his head.
