---
title: "025: Breaking Up With Your Stack"
description: ""
date: 2021-06-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/025-breaking-up-with-your-stack/id1544142288?i=1000523905989"></iframe>

There's no _one reason_ that companies _move away_ from or _onto_ a technology stack. Sometimes a given technology is no longer actively updated; sometimes the pool of developers that uses a technology shrinks, making it hard to hire new engineers or find community support; sometimes people just like the _new hawtness_; sometimes licensing costs become prohibitively expensive; sometimes there's a leadership change at your company; and, sometimes a team just _believes_ that a new technology will solve all of their problems (**spoiler alert**: _it won't_). This week, the crew meets to talk about reasons that they've move on from or stuck with a set of chosen technologies.

## Triumphs &amp; Failures

-  **Adam's Triumph** - All of our recent talk of testing and "clean code" has had a _very positive impact_ on how Adam is writing his own code. He's become much more cognizant of his application's boundaries and modularity; which, has enabled him to organize dependencies in order to make them more testable (and mockable). In fact, he's been so motivated by this new-found perspective that he's even gone back and refactored a mission critical portion of a legacy application that didn't have any tests at all.

-  **Ben's Failure** - He fancies himself quite good at debugging software. And yet, for the last 2-weeks, he's been _completely baffled_ by a bug in a portion of his application. No one on his team can reproduce the issue. So, all he's been able to do so far is add new logging statements and then comb through his log aggregator looking for clues. **It's maddening!**

-  **Carol's Triumph** - In episode 020 - ["Carol Needs A Consult"][working-code-020] - Carol laid-out her plans to build an email-based integration with her company's ticketing system. Now, only a month-and-a-half later, she's thrilled to see this product really coming to life. It hasn't always been easy; and, they've hit some significant bumps along the way; but, so far, they haven't faced anything that they couldn't conquer together as a team. She's feeling lucky to be working with so many wonderful people!

-  **Tim's Failure** - He created a Pull-Request titled, _"OMG, I can't believe I left this in the code"_. Apparently, while writing code for a new API-workflow, Tim hard-coded a failure-response into a network request so that he could test the "sad path" control-flow logic. And then, he **forgot to remove it**. For 3-days, he had production API calls all hard-coded to return failures. Fortunately, the code would fall-back to returning the _correct result_ on a subsequent retry. But, he's definitely feeling some acute Shame over this turn of events.

## Notes &amp; Links

-  [Semaphore](https://adamtuttle.codes/blog/2021/introducing-semaphore/) - A minimalist Feature Flag engine for CFML apps.
-  [Strangler Pattern](https://martinfowler.com/bliki/StranglerFigApplication.html) - A technique in which a new implementation slowly takes traffic from an existing implementation.
-  [JAM Stack](https://jamstack.org/) - JavaScript, APIs, and Markup stand as the pillars in this newly-coined architectural approach.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-020]: https://workingcode.dev/episodes/020-carol-needs-a-consult/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/025-breaking-up-with-your-stack.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:15] **Adam:** Okay, here we go. It is show number 25 for June the 2nd, and on today's show, we're going to talk about breaking up with your tech stack. But first, as usual, we're going to do triumphs and fails, and Carol's here, so Carol gets to go first.

[00:00:31] **Carol:** Hi Carol, welcome back and breakups are something I'm really good at. I've proven to be an expert in that topic as well. Um, yeah, I'm going to go with the Triumph this week. Uh, you know, I've talked about it for a couple of weeks. We have this new AWS project that we're working on. It's going to be an autoresponder for our customer service team.

[00:00:50] **Carol:** Um, this week we put everything together. So all of the developers work has been Put into one build, and now we have it running end to end, and we're able to see that it works together. Nice. And we're actually to start, we're actually to start, that's not a sentence. We are actually starting to, uh, see data and verify that it's actually going to, um, help us in the long run.

[00:01:15] **Carol:** So we're super, super stoked about it. The biggest triumph for me, though, is that we've hit roadblocks with this, and it's been hard at times. And we've Googled the hell out of every single question you could think of, but we haven't stopped. And it's just been really nice to have the support of my peers and of the team I'm working on to just go, Hey, let's jump in a call and let's just talk about it.

[00:01:39] **Carol:** Cause maybe we can't find a solution and we're going to have to work around it. So it's just been, it's been a lot of fun to, you know, troubleshoot with people, brainstorm and just feel supportive when you have these roadblocks. So it's going good. I'm, I'm happy. Really happy. Yay. Nice.

[00:01:52] **Tim:** Yeah.

[00:01:54] **Ben:** What about you, Ben?

[00:01:56] **Ben:** I, uh, I'm gonna go with a failure. I, I fancy myself someone who is good at debugging. I, I find a lot of joy in debugging and I, I like to believe it comes Easier to me than maybe it does to some other people, but for the last two weeks, I've been working with a cross team collaboration to figure out why people are getting logged out occasionally from a part of our system.

[00:02:22] **Ben:** And it is just baffling the heck out of me. I'm, I'm literally pouring through logs in a way that I've never done before. Like, typically the way I can debug is step one is reproduce the problem. And the issue we have here is that we don't know how to reproduce it. Um, no one on our team can reproduce it.

[00:02:44] **Ben:** And like the handful of times that maybe it happened. We didn't have the right login in place at the time, and we can't reproduce it since then. So, I'm literally just trying different combinations of queries in Logly as our log aggregator. And I'm looking at IP addresses, and I'm looking at machine serial numbers, and I'm trying to find errors, and I'm trying to cross correlate based on user IDs, and times, and...

[00:03:10] **Ben:** It's, it's, it's melting my brain. And the problem is I keep adding login and I keep maybe tweaking parts of the application logic, but since I can't reproduce it, I don't even know if these are having positive effects. So it's, it, it just feels like I'm fighting ghosts and it's very. Challenging emotionally.

[00:03:30] **Carol:** Yeah. Those are with

[00:03:31] **Adam:** the worst. Yeah, the worst. Do you happen to ha like, have customers that can

[00:03:36] **Ben:** Oh, oh, there's customers who are angry. ,

[00:03:41] **Adam:** I mean, uh, would be too, can you, can you like, jump on the phone with 'em or a screen share and get them, I, I think we're

[00:03:45] **Ben:** actually meeting with, uh, one of the customers who's able to reproduce it fairly consistently.

[00:03:51] **Ben:** Tomorrow. So I'm hoping that is fruitful or maybe, you know, best case scenario is they report back that they haven't been logged out in the last day and a half since we've started making some of the larger tweaks, but it's just

[00:04:03] **Adam:** been. Is that really best case scenario though? Because then the bug is

[00:04:09] **Carol:** still there.

[00:04:10] **Carol:** We don't know

[00:04:10] **Tim:** how we fixed it, but. Doesn't sound like a satisfying conclusion. It's really,

[00:04:14] **Ben:** it's just very challenging. And I'll tell you like the biggest challenging part of it. Is the cross team collaboration parts.

[00:04:21] **Carol:** So what type of team are you working with?

[00:04:23] **Ben:** So we're, uh, I work on the web app and then we have

[00:04:27] **Adam:** a...

[00:04:27] **Adam:** Rainbow team is working with the unicorn team. Yeah.

[00:04:30] **Ben:** The rainbow team is working with the craft team. Craft is a plugin that we have for Sketch, which is a design tool. And you can sync, you can sync designs from Sketch into the web app using this plugin and people are getting logged out of the plugin.

[00:04:47] **Ben:** But they shouldn't be. And part of the problem too is that the web app uses its own session management and then the craft plugin uses JWTs or JOTS and I don't have a whole lot of experience with why people use those or how they get used and how long they're supposed to live for and then there's the main JOT and then there's the refresh token to ask for new JOTS and it's, it's It's something that the web app doesn't have to think about at all.

[00:05:13] **Ben:** So I just, it's not part of my mental model. That

[00:05:18] **Carol:** has been everything I've been learning because I'm doing all the authentication piece for this new process that we're doing. So lots of fun. I didn't know it was pronounced jot until I listened to a YouTube video on authentication while I was in the shower.

[00:05:31] **Carol:** And he was like, it's JWT, which I was like, doesn't

[00:05:34] **Adam:** seem like that

[00:05:35] **Tim:** should be

[00:05:36] **Adam:** the, I'm

[00:05:37] **Carol:** going to keep calling it JWTs, JSON Web Tokens.

[00:05:40] **Ben:** It took me months to allow myself to call it a job. Like I was so emotionally

[00:05:45] **Adam:** against it. I still, like, similarly, I still struggle with, is it Jason or Jason? Jay son. That's what I think that's what

[00:05:53] **Ben:** I would say, Jason.

[00:05:55] **Tim:** Because I, because we have a Jason on our team. So it's like, I don't want,

[00:05:58] **Adam:** yeah. Yep. So do we.

[00:06:00] **Tim:** The Jason data is bad. What did Jason do? Does he need a reprimand?

[00:06:07] **Ben:** Anyway, uh, Adam, what do you got

[00:06:08] **Adam:** going on? Well, the streak continues. I have a triumph again this week. I'm sorry, but you know, my life is just going great right now.

[00:06:17] **Adam:** Life is a garden, dig it. Oh, I love that. You're a winner. You're a driver. That's right. I have to say the podcast has really helped me professionally lately. Um, you know, we read the book and I felt like just reading the book, Clean Code, has made me a better developer, but also the process of doing that and discussing testing here with you guys and discussing things with our patrons and with our other listeners.

[00:06:40] **Adam:** Has really kind of lit a fire underneath my behind for, uh, for testing in general. Right. And so today at work, I unilaterally decided like, there's a thing here that there's this one, uh, small repository of some logic that we use. This is pretty much missing mission critical. It's about as mission critical as you can get without being handling money.

[00:07:02] **Adam:** And So, and it's completely untested. So, I was like, and it's very testable, right? It's JavaScript and I actually have a reasonable knowledge of testing JavaScript at the moment. So, I just unilaterally decided I'm going to go write some tests for this stuff. And I figured it would take me, you know, maybe half a day and that would be good, right?

[00:07:20] **Adam:** The tests would give us a lot of confidence moving forward. And actually what ended up happening was, I found a bug in the logic that hasn't happened to Bytus yet. It's like, uh, if this certain error case were to happen, if somebody were to put like a token in some text wrong, then the function would call the callback twice, like with different arguments.

[00:07:40] **Adam:** Which would be, would be kind of bad. It would probably crash whatever the handler or the wrapping, the calling code. It would probably crash the calling code. And so just the process of going through and writing the test and seeing that the test expectations were being called twice with different results that was, you know, eye opening, I was like, oh, hey, there's a bug here.

[00:07:57] **Adam:** And I fixed that. And then, in addition to that, another file in the same repo that I was writing tests for, I just, I was going through and writing out all my test cases. And as I was doing it, I was like, this file, this module is just not very testable, right? It was kind of disorganized and, you know, a lot of nested functions and, um, nothing, a lot of functions to test because, or a lot of use cases to test because it's a complex thing, but it's written in a way that doesn't make it easy to mock any individual piece of that, which makes it different, makes it pretty much you have no choice but to do like end to end or integration tests on the whole thing all at once, which is.

[00:08:35] **Adam:** So, I'm just, I'm excited about all this testing stuff that I've been able to put together and the issues that it's helped me find. It's going to make our code better and I'm just real happy

[00:08:43] **Tim:** with it. Don't, don't let Adam Cameron sway you.

[00:08:50] **Tim:** He hates

[00:08:50] **Adam:** us to the core. As Amingo said, your hate matters. Your hate matters.

[00:08:57] **Ben:** Well, that's cool,

[00:08:57] **Adam:** man. Yeah, I'm loving it. So, uh, that leaves you, Tim. What do you got?

[00:09:02] **Tim:** All right. I want to say it's a triumph, but it's not. So Ben, you know, I've, I've taken your PR request advice to heart. I'm trying to do super small PR request, mostly because the person that, I only have one person to review it right now, and he's super busy on a project that I have him working on that's super important.

[00:09:23] **Tim:** So I don't want to bog him down with like 15 files and 60. Yeah, Hunt, you know, although to be fair, he totally bogs me down with like, he's sitting on a 70 file change right now that I'm going to get tomorrow. But anyway, sorry, Steve. Um, so do a super small, super small, and I found an issue yesterday. No, is it yesterday?

[00:09:48] **Tim:** I think it was yesterday. I put it on the, on our discord server for our patrons. I had to call the pull request. Oh my God. I can't believe I left this in the code. I put a screenshot of it and everything on the, on the Discord channel. So what happened was this, I was trying to, so I have a, a service that calls a bunch of other services and a lot of times I, I, you occasionally get just a connection.

[00:10:16] **Tim:** A connection timeout, right? Or a connection refused. And so I was trying to simulate that because I was getting these not often, but like once or twice a day, I would try to call a service, remote service, and the remote service wouldn't respond. Now, I have no control over that remote service. So it would just say, you know.

[00:10:35] **Tim:** You know, connection error. So I would, so I was simulating a connection error so that it could not just fail an error on the connection error and gracefully just go and say, okay, you failed that time. I'm going to try again. Are you ready now? No. Are you ready now? Okay, good. And move on. The problem is, when I was doing one of my little pull requests, I realized I left the code in there that manually set the JSON return to connection error.

[00:11:07] **Tim:** And that had been in production for three days.

[00:11:09] **Adam:** Oh no. Three whole

[00:11:11] **Tim:** days. Now I know it works because there were no errors. It totally, it totally just would do the call. It would get the call. And then I would manually set that to connection error and go. Tell me again.

[00:11:28] **Adam:** I saw that and said,

[00:11:29] **Tim:** Oh my God, I just need to go work at Burger King and be a fry cook. It's just,

[00:11:34] **Adam:** yeah. So

[00:11:35] **Tim:** I very quickly messaged my, uh, my cohort and said, Can you please approve this? And he looked at the name and he just started laughing. I said, please cover my shame. Cover my shame.

[00:11:48] **Adam:** Oh, that is amazing.

[00:11:52] **Ben:** So was there, was there a base case where it eventually returned the raw response? Like did it try a couple of times and then return the right thing? So it was just a lot

[00:12:01] **Adam:** of extra

[00:12:01] **Tim:** processing. Yeah, it was just, it was just, it would, it would do the call and it would get the correct result most of the time.

[00:12:07] **Tim:** And then I would manually set it to connection error and it would say, okay, let me go get it again. And then I'd get it the second time and it was fine. So I mean, for three days I had no, there was no errors. There was no problems whatsoever. Nothing actually happened bad in the application. It's just. I'm just like, I can't believe I left that in there.

[00:12:26] **Adam:** That's not quite so mortifying then. You didn't actually bring down production. You just introduced an artificial slowdown. You

[00:12:31] **Tim:** know what? Honestly, bringing down production would have been quicker because it wouldn't last for three days. I would have figured that out. I would have figured that out in like two minutes, right?

[00:12:38] **Tim:** Yeah. This is for three days where it's just doing an extra call going, I sent you something, send it back. Uh, I don't believe you. Send it again. I'm telling

[00:12:46] you,

[00:12:46] **Ben:** those small PRs, I deployed like, probably six times today, and each deployment was, was adding, you know, a line of debugging here. Two lines of debugging there.

[00:12:58] **Ben:** And if I had to wait 24 hours for someone to approve each one of those things, I mean, I'd be punching myself in the face.

[00:13:05] **Tim:** Yeah, no, yeah. I deployed like six times yesterday and it, you know, and he's fast to get to them because they're small, but also because I'm his boss.

[00:13:17] **Ben:** There was a guy on my team, he's still in the company, this guy, JD, great guy. But he just, he, he was given a number of tasks that all happened to have massive rewrites as part of them. So I remember he started off and he was refactoring this node service and he sent me a PR and I swear it was like 125 files had been changed or something.

[00:13:39] **Ben:** And I was like, dude, this is brutal. You really got to find a way to break these things up to be smaller. Like I I'll, I'll skim it and trust you for the most part, but like. This is, this is not acceptable. And then he has work on another thing. And like two weeks later, he sends me PR. He's like, dude, I'm so sorry.

[00:13:59] **Ben:** It was another like 90 file, like massive refactoring of something. And I was just like, JD, you're killing me here.

[00:14:06] **Tim:** You know, sometimes it's hard to slow your roll. It's like, I found with it. It was like, I was like, no, no, I need to stop. I need to stop and make this a PR. This is kind of an atomic piece of functionality here.

[00:14:20] **Tim:** Let me go ahead and do it. I can keep working, it's just, just remembering to do it. Oh

[00:14:27] **Ben:** man.

[00:14:27] **Adam:** Alright. Let's talk about breakups, huh? Well, I, um, what was the other thing, oh, so on the subject of feature flags, uh, those small PRs, right? We went back to feature flags.

[00:14:38] **Carol:** Nobody brought up feature flags.

[00:14:41] **Adam:** Don't hate.

[00:14:42] **Adam:** Sorry, Ben Jr. Um, no, the, the, we were talking about the really small, tiny PRs and those kind of pair with, okay, fine, I'll take my, you say so, okay. Yep. Yep. I'm going to take my podcast and go home. You're all fired. Um, I, I was just going to say, uh, the, it was either last week or two weeks ago. I had mentioned this new open source project.

[00:15:07] **Adam:** I started Semaphore. Um, I haven't used it yet. It's not in production yet, but I would say. As far as I can tell, it's feature complete. So it's ready for me to start playing with it. And it's, it's not that much code, right? It's like 150, it's less than 150 lines of code once you take out all the comments and crap.

[00:15:24] **Adam:** So what's it doing? It's for feature flags. You weren't here. You don't know. Oh, that's right. Yeah. We talked about that last week. And how many lines did you say? It's like less than 150 lines. Now, that is not a, like a management UI like flag definitions or anything. And it's not a storage mechanism. It's just like set the flags in the memory and the decision, the rules engine and all that.

[00:15:46] **Adam:** That's pretty cool.

[00:15:48] **Ben:** One thing that, um, I don't know if you've come across this in Lucy yet. I know you're converting. A lot of stuff I have converted over to Lucy. Um, they have some interesting cached within constructs that, that don't exist in Adobe ColdFusion. Um, in ACF, you could always cache a query, uh, but in Lucy, you can cache queries as well, but you can also cache function results.

[00:16:12] **Ben:** And they have it cached within equals request. So you can have a function or set of functions that literally just cache pure inputs and outputs for the duration of a request. So you can call that function as many times as you want, and it doesn't reprocess.

[00:16:28] **Adam:** So it's kind of like a memoization. Yep.

[00:16:30] **Adam:** Exactly. That's awesome. Thank you. Um, I was going to cut this section out of the show, but maybe I'll leave it. That's awesome. Thank you. Cool. So the thing we wanted to talk about today is breaking up with your tech stack, a topic that I think we've all thought about at least every, every now and then, right?

[00:16:48] **Adam:** You always, every licensing change

[00:16:50] **Tim:** for sure.

[00:16:53] **Adam:** So really, I guess, what does that mean? Right? So you're, you're working on a product or project. And it's running on classic ASP and you really want to move it to Go or something like that, right? You know, it's, you want to change the language that you're using, maybe a major framework move, something like that.

[00:17:10] **Adam:** Um, that's really what we wanted to talk about. So who wants to start us off?

[00:17:16] **Tim:** I will. So I would say it's important to set your expectations. You got to really understand the reason, your motivation for doing so, right? Developers are bad about thinking that a new language will fix their problems, right?

[00:17:34] **Tim:** They're like, oh, this sucks because we wrote it in X. Right. And X is

[00:17:38] **Adam:** our problem. It's not web scale. Right. It's

[00:17:41] **Tim:** not. Right. It is not web scale. Um, and if you really need to challenge those assumptions, is that really the problem? Or was, did, did your language, was your language okay? Or just as good as another language, and you just wrote it badly.

[00:17:58] **Tim:** Right. Well, changing languages isn't going to fix that problem. So, you really need to challenge your assumptions of why you want to change your

[00:18:07] **Adam:** tech stack now. Yeah, I mean, so like you said, it's not going to be a panacea and fix all of your problems. It could certainly fix some of your problems. I mean, I would say that your tech stack...

[00:18:18] **Adam:** is not, um, the first thing that you should think to change if you're having problems, but your tech stack can be holding you back. So the four of us, we're all at least experienced CFML developers. I don't know where we're all at on the spectrum of currently using, but something that frustrated me for a very long time when I was writing CFML and when I continue to write CFML here and there is The lack of, like, real time push support.

[00:18:48] **Adam:** They did, at one point, add, like, WebSockets. And in the before four times, There was, uh, Gateways, so you could like have stuff push information in, but I feel like Gateways just kind of like became this forgotten feature and it got, you know, uh, it kind of fell apart and I'm not even sure it works at all anymore.

[00:19:10] **Adam:** And WebSockets are great, but they don't really work for every use case. So what I was thinking about this for like the feature flags thing, right? So. When you make a flag update, uh, when you change the flag configuration, you want that to go as near real time as possible out to the servers. You don't want them to have to wait 15 minutes for a flag change.

[00:19:30] **Adam:** Right. But at the same time, the frequency that you're changing flags is probably pretty low. Unless you have like thousands of developers and thousands of flags, then you're... Probably only changing a few flags a day, a couple of times a day. And so while you don't want that update to take 15 minutes, you also don't want to be constantly polling for updates or anything like that.

[00:19:52] **Adam:** So a push mechanism would be, would be great if you could have it found ways to work around that. But that's just one of those things that I feel like other languages, other platforms have good solutions for a good, a good, like real time push. Story that CFML lacks.

[00:20:12] **Ben:** Although bringing up WebSockets is interesting because we've had a little bit of a history with this internally at the company.

[00:20:18] **Ben:** So the application that I work on is in CFML, Lucy CFML, and we use push technology, but we don't, we don't build it. We use a, um, a SAS provider called Pusher and Pusher, essentially the browsers. Connect to Pusher and then our servers make posts over to Pusher and then Pusher broadcasts it to all the subscribed users and there's authentication workflows that happen.

[00:20:45] **Ben:** And the nice part about that for us is that we've never really had to manage all of the WebSocket connections. We just have a Pusher JavaScript library that we include and it just sort of just works. Now, I'm on the legacy team. The newer teams have all opted to use Node. js. Socket. io. Socket. io, I think.

[00:21:08] **Ben:** And it's funny because I've been on a bunch of calls where they talk about the architecture that they're using and they love Socket. io, except for when servers go down or they have to add new nodes into the load balancer and they're like, yeah, but our clients and the browsers are connected to certain nodes that have the web socket connections held open.

[00:21:27] **Ben:** So when those go down, yeah, like the browser has to reconnect, but then the other servers don't know about those connections because they were stateful. And I'm like, uh, I'm listening to this. I'm like, you know, it'd be interesting if you maybe refactored all of the socket handling out into its own service, and then you could have N number of nodes connect to that service.

[00:21:47] **Ben:** And just post messages to that. And then that service could manage all the website connections. And they were like, yeah, that sounds good. And I'm like, yeah, now imagine if you just called that service, pusher app.

[00:21:59] **Ben:** And it was just funny because it's, um, there, there's a term that comes up on a lot of podcasts I listened to where they talk about, uh, differentiating and undifferentiating technology and that like your business. Should build the things that differentiate it. And like WebSockets don't differentiate you as a business.

[00:22:18] **Ben:** Unless of course, like the real time nature is a very, very, you know, as a huge focal point of how your application works, but like the stuff that we do, it's not a, it's not a huge focal point. Like we just want to do more, Hey, you know, your, your view model change. You should probably re fetch it from the server.

[00:22:37] **Ben:** Like that's basically the extent that we use it for. But, uh, I don't know. It's just interesting that, that, uh, they, they sort of reinvented the wheel and then realized that that wheel had a lot more going on than they thought it had in the, originally.

[00:22:50] **Adam:** I just had a conversation like that the other day with our CEO and we were talking, he put it in terms of these are our core competencies or they're not, right?

[00:22:59] **Adam:** Different, differentiators. And if it's not a core competency, it's something we should outsource. Like, for example, we built a, like a ticketing system into our platform initially. And it's fine, it works, but it's nowhere near as something, it's nowhere near as good as something like JIRA, um, or, or any of the a hundred other decent options.

[00:23:20] **Adam:** And so we're discussing now the possibility of moving that out of our product and getting rid of that module entirely. There, there are some little things that are nice about the way that we implemented ours. Like, um, for example, if somebody puts in a ticket with a priority level of like nine or above, um, then it sends an immediate alert to our on call person.

[00:23:40] **Adam:** I'm sure that there's ways to accomplish workflows like that, but... Just having it baked in, it's kind of nice.

[00:23:46] **Tim:** I, I would say from my experience, another reason why you would want to break up with your tech stack is because it is really, really old. Now, I, the, the industry I deal with... Ageist for sure. Sorry.

[00:24:01] **Tim:** Uh, the industry I deal with the most is insurance. And a lot of insurance companies, they, they made a lot of purchases back in the 80s to get... You know, computerized and they're running on AS400s, which are running on COBOL. And to be fair, most COBOL developers are probably in their 70s or 80s and they're very hard to find.

[00:24:25] **Tim:** And so, I mean, I think that is legitimate reason to want to. You're on a language that, and let's be fair, I've never found any community that said it's easy to find developers in that language. Every single community says it's impossible to hire those people. Every

[00:24:43] **Adam:** single one. Well, there's just a general developer shortage.

[00:24:45] **Tim:** Yeah, it's just, in general, developers are hard. There's a shortage of us right now? There's a shortage, yeah. They're hard to find. And good ones are even harder to find. That's true. Yeah. Yes. So, but, I mean, legitimately, some of these older languages, like Fortran... I mean, you're not going to find, kids coming out of school don't learn it.

[00:25:06] **Tim:** The people who learned it and are really good at it, they're, they're, they are getting up in years and most of them are pretty much retired. We had, uh, one of our sister companies. Like their main developer was like some 75 year old retired guy who lived on a river boat and just kind of floated around the Florida rivers, you know, and they're like, this is not a sustainable business model.

[00:25:30] **Tim:** So I mean, if that's your situation, yeah, you should be looking very seriously at going to a new tech stack. But, uh, a lot, a lot of times these, these languages that are like 10, 20 years old. It's it, it is more of a desire, a want than an absolute need. Yeah. To change

[00:25:50] **Adam:** your tech stack. I think going back to the hiring thing, an argument that you'll hear against that a counterpoint is gonna be that you shouldn't necessarily hire somebody because they're good with the stack that you have.

[00:26:02] **Adam:** You should hire them because they're a competent. Developer or they have the, you can see something in them that they're, you know, they have potential. That's what I'm looking for. Developer's mindset. Yeah. They have the, you can see that they have the potential to become a good developer, even if they don't have a ton of experience or anything like that.

[00:26:17] **Adam:** But, and, and I completely agree with that, but at the same time, You are not going to have a lot of luck if you are looking to hire recent college grads or people without a college degree that went to a JavaScript boot camp, boot camp. Boot camp. Yeah. And try to convince them to learn COBOL. Yeah. Right?

[00:26:36] **Adam:** Like, or that's just. It does nothing for your resume. I'm not saying it can't happen. But what I'm saying is you're going to have a hard time finding good people that want to do that or that are willing even to do that. Well,

[00:26:49] **Carol:** you also have the issue of the community support for that language as well. So you have kids out of school.

[00:26:54] **Carol:** I say kids, you know, because I'm old now. Kids you know, entering the workforce and they're looking into the community support of the languages. So you're not going to find someone who wants to pick up. Cobalt when, you know, the community support isn't there to help them learn it or help them problem solve through it, where if you put them on a Node project, suddenly it's infinite on what they're able to start working with.

[00:27:20] **Tim:** I think another good reason why you want to break up, and this one is near and dear to my heart, If you are paying for some reason, I don't know why anyone would pay for a language engine, but if you're paying for it and they continue, just continue changing their, their pay model and it gets more and more expensive, then the licensing is more and more prohibitive.

[00:27:43] **Tim:** You might want to start looking somewhere else. And

[00:27:45] **Carol:** the, um, the updates aren't there to you. Yeah. Yeah.

[00:27:54] **Tim:** It uses all the same language. The only thing you're not getting is the security updates. So they just keep pushing out new updates every two years and you have to continue to like buy new licenses. Otherwise you're out of compliance. So that is a good reason.

[00:28:08] **Adam:** So, I was curious and I just went and looked and you know, there's no, I don't think there's a perfect measure, but a useful statistic to look at.

[00:28:17] **Adam:** I went and looked at the number of questions tagged COBOL on Stack Overflow. It's a little over 4, 000, right? So 4, 166. I want you to guess. Don't look. No cheating. No cheating. How many do you think? Are tagged CFML. How many were on Cobalt? 4, 166. 27,

[00:28:36] **Ben:** 000. 7, 800. 10, 000.

[00:28:40] **Adam:** 2, 063. Oh, come on.

[00:28:44] **Carol:** You just did ColdFusion or did you do CFML?

[00:28:46] **Adam:** I did CFML. Let me, let me do ColdFusion. Yeah. Okay. ColdFusion has 34, 000. Okay. There you go. Thank you. I'm the winner. Life makes me think again. I think that tells you a lot about, uh, how much. Uh, Mindshare, ColdFusion has in the CFML community or market space. I imagine

[00:29:09] **Carol:** Ben's blog has way more hits

[00:29:10] **Adam:** than that.

[00:29:11] **Adam:** For

[00:29:11] **Tim:** sure. One thing that bothers me, so I mean, there was some, some things I was Googling today. It's like, and the answers that I get are from like 2013. Then always I'm like, That bug, that bugs me. Yeah. It really bugs me. It's like, and they're ColdFusion questions. And it's like, if my answer is from 2013 and that's the most recent thing I can find, then something's

[00:29:35] **Adam:** wrong here.

[00:29:35] **Adam:** Yeah. Okay. So, uh, I think we've pretty well covered, like, why would you want to break up with your tech stack? Does anybody have? Anything else you want to say there? Yeah,

[00:29:47] **Tim:** there's really bad reasons. Okay, yeah. Right, because someone new in the company comes in and they have, you know, they're an evangelist, right?

[00:29:53] **Tim:** They're like, you know, everything's, everything's utopian ideal, right? This person that sells it. And who's good at selling it. They're, they're the scariest people in the world because they, they, they, they get into the ear of the boss. They, they, they pour that sweet nectar into their ear and say that all these problems that you're having, they're all going to go away if you switch to X.

[00:30:13] **Tim:** And it is a complete lie.

[00:30:17] **Ben:** I think also, uh, sort of along those lines is that, um, I, I, I think sometimes people overestimate how limiting something is. And I, and I think about the thing that always comes to mind with regards to that is using JSON as your data transport format versus something like, uh, protobuf or, or some sort of like lower level, more optimal over the wire format and, and thinking that, well, look, we're going to save all this bandwidth and transfer costs and speed.

[00:30:54] **Ben:** And I always come back to this idea that I just don't think that's the thing that's holding you back. It's like the amount of junk you can shove over the wire. And maybe it is for some people, but like, probably not for the majority of people. And I, I just, I, you know, going back to the, I, we, we mocked earlier about the web scale stuff with MongoDB and, you know, maybe for people, MongoDB makes a ton of sense because of the way it can horizontally scale in the way that a relational database can't.

[00:31:26] **Ben:** But like, again, for the vast majority of people, horizontal scaling is probably not your limiting

[00:31:31] **Adam:** factor. So then, um, if you're, if you've made up your mind, you need to move on, what sort of things do you need to be thinking about?

[00:31:41] **Carol:** So one thing I would suggest is, I know, you know, Ben's not big on microservices and breaking things out, you know, but I would say if you're really pushing to do it, spin up a part of it and write it in the new code and really examine how they're going to work together or how they're going to differ.

[00:31:58] **Carol:** Because you may find that you're putting a lot of time in and you're not getting the results from it. So then you gotta circle back and figure out where your bottleneck actually exists at. Is it how you've written it? Is it something else? It may not be the language.

[00:32:12] **Adam:** So it sounds like you're saying you're advocating for like research and development, a quick, you know, take a week or sprint or whatever.

[00:32:18] **Adam:** And all right, hypothetically, we're doing this. So this is what it's going to look like. I'm going to just pretend and go for it and see what it looks like. And are we happy with where we're headed in that direction?

[00:32:27] **Carol:** Yeah, or treat it as an API endpoint and just go, Okay, now when I'm executing my application here, I'm going to, instead of process this refund on the main code, it's now going to process in this new language that we've checked out.

[00:32:42] **Carol:** And we're going to see what the application actually does and how it responds. Right. Maybe not refunds, let's not touch money, find something not so risky, but that was just the first thing that came to my mind.

[00:32:52] **Adam:** Right. Well, you, you're in FinTech, right? So. Yeah. Everything's money. Everything's money. I think.

[00:32:58] **Tim:** If you do decide that it is time to move on to a different stack, you got to plan for two things. One, you still have to maintain the existing one. Oh, yeah. That is going to be a much longer tail than you believe. You're going to estimate that, oh, two years, sure, we'll be completely off this. Get that out of your head, man.

[00:33:16] **Tim:** Just, just totally wipe that idea. It's not going

[00:33:19] **Adam:** to happen. Yeah.

[00:33:20] **Carol:** Put your budget to hold it

[00:33:21] **Adam:** for a while. Yeah.

[00:33:22] **Tim:** Just go ahead and, and yeah, put that in your budget. You're going to be maintaining that a lot longer than you think. Two, use that opportunity to figure out where you drew boundaries wrong. Yes.

[00:33:34] **Tim:** More than likely your app kind of organically grew. And as it grew, you didn't really set boundaries of, of concerns for each part of it. So that is, that is where you need to really spend the most of your time, breaking the things that your app does, breaking that into separate concerns and draw the boundaries around it, and then build those.

[00:33:58] **Tim:** In pieces, right? So you can't rewrite the whole thing from scratch. Tiger team. Right, the tiger team, like Uncle Bob talked about. It's not going to happen. It just won't happen. So break it up into discrete boundaries. Figure out, you know, what is, you can either say what's the most important. Or what's the most, what would be the least impactful?

[00:34:18] **Tim:** Yeah,

[00:34:18] **Carol:** let's do less impactful up front. Right, right,

[00:34:21] **Adam:** because you're going to

[00:34:22] **Tim:** learn on the less impactful one. So draw that boundary, build that as a service, an API, however, you know, you decide to do it in your new language. And then look at it again and see, alright, does this actually function better than what we had before?

[00:34:36] **Tim:** Right. If it doesn't, then refactor it till it does. Yeah. And then move on to the next boundary. So

[00:34:44] **Adam:** I actually have a little bit of experience doing this. Um, you know, we've talked about in our very first episode, we talked about how, you know, I'm, I've been trying for years to move away from CFML and I'm more successful in some areas than in others.

[00:34:58] **Adam:** And so we have our, our monolith is in CFML and we've been moving things out to microservices where appropriate. And none of those microservices are CFML. And some of them are like Lambda functions. And it's funny because AWS is where our application lives. And they keep adding things. Like when we first started on AWS and we first started moving things out to like Lambda functions, you couldn't attach a Lambda function as like a listener to a load balancer.

[00:35:29] **Adam:** You could run a Lambda function, it could do stuff. But it couldn't like respond to a web request. Um, and now you can. And so like, there's lots of these little iterative improvements that they've added over time and it's like, so in some ways our application has spread out a lot farther than it should because we have like the same type of change implemented three or four different ways because of new things that are now available to us that are, we think are better than the old way.

[00:35:54] **Adam:** But I guess the thing that I really wanted to say here was like, we're, we're on AWS and the thing that I really like is we're using the ALB, the application load balancer. Thank you. And you can put in rules there, a couple of different, they give you like a rules engine, right? So you can say like, for this host name, if the path contains this string, right?

[00:36:12] **Adam:** So in our case, it's like if the request is for a specific module or something, then I can fork that off and pass that off to this microservice, or to a lambda function, or to some other target group. And have that be the thing that responds. And they, we can have it share our sessions because our sessions are external to Monolith App Server and that sort of thing.

[00:36:31] **Adam:** So, it's very possible to break it up into smaller chunks, but you have to think about how it's all going to function and for the end user experience in, in an ideal situation, they shouldn't even notice that you're doing it, right? Right. It should be

[00:36:49] **Ben:** seamless. I don't know if we have mentioned this pattern, but there is a pattern called the Strangler pattern.

[00:36:54] **Ben:** Yeah.

[00:36:54] **Adam:** You've mentioned it before, but I'm not familiar with that. The general

[00:36:57] **Ben:** concept is that you rebuild something in a separate implementation, and then you slowly start to route traffic to the new implementation. And you, you know, you use that as an opportunity to make sure it's performing well, to make sure it's not throwing errors, to make.

[00:37:14] **Ben:** I'm sure that it's generally copacetic with the old implementation and then you just keep moving traffic over to it and eventually the new implementation, quote unquote, strangles the old implementation. The old implementation is no longer being used. It's based on a, on a vine, there's like a strangler vine that wraps around trees and kudzu.

[00:37:33] **Tim:** Yeah.

[00:37:34] **Adam:** Poison ivy. Nobody's going to get that joke because that was from before we were recording. Oh, yeah. Before we were recording.

[00:37:39] **Tim:** Yeah. Kudzu. Kudzu. So, uh, Ben, how do you, so I get that. I mean, that's, that's cool. The idea of like slowly moving, but, but how do you functionally

[00:37:48] **Adam:** do that? Yeah, I was wondering if there's something that maybe there's a feature in an ALB that I'm not aware of that can help you do that or something.

[00:37:56] **Adam:** It does sound like it kind of would need to be either a load balancer or a proxy involved. Or a feature flag. But the feature flag would be in front of the proxy, right?

[00:38:05] **Ben:** Well, you could have, uh, imagine you're making an API call to the monolith. And instead of having the monolith process the request, the first thing it does is check a feature flag and instead turn around and make a request to an external service and then essentially just proxies

[00:38:23] **Adam:** to it.

[00:38:23] **Adam:** I mean, I guess that would work if you're, if the thing that you're proxying the request to If the added overhead of that proxy, you know, the, the extra latency involved is not negligible.

[00:38:36] **Ben:** I mean, I think there are, I mean, here's the thing, I think the Strangler pattern when you're dealing with an external service is more complicated and probably is more associated with more complex architectures.

[00:38:51] **Ben:** You can use the Strangler pattern at smaller levels. Where it's not an external service, that you have a request coming in and you have a different database query implementation that you want to try. And so you just route traffic to the new query instead of to the old query, and you maybe do it 2% of the traffic coming in.

[00:39:09] **Ben:** You make sure the database is performing okay, and then eventually just move all the traffic over to that new query and delete the old query. I mean, that's, that's the same concept, just at a really localized scale. I've heard it talked about a lot more with, uh, really event driven architectures, where, uh, you'll have one service that consumes a certain event, and then they just build a totally different service that will also respond to that same event.

[00:39:38] **Ben:** And then I think they can make sure that that's consuming events properly. And then eventually just get rid of the old service. I'm definitely talking above my pay grade at this point, but, uh, I think in a distributed architecture, that's more event based, I think there's a whole bunch of strangler type patterns that get applied.

[00:39:58] **Ben:** One

[00:39:58] **Tim:** thing I found that we do is a traditional old school model of. Creating a CFML page was you got a whole bunch of CF params at the top, some queries at the top, and then you basically do some output at the bottom.

[00:40:16] **Adam:** But you got to wrap that top part in an if statement. Right. So like if the form posted, then do the queries.

[00:40:22] **Adam:** Yeah.

[00:40:23] **Tim:** So taking that kind of page model and refactoring it so that basically what I tend to do is I will abstract out all the. The data getting and the data manipulation that's tends to be at the top of an old school CFML page and that now becomes a call to an API. So I built an API in some other language or even the same language, it doesn't matter, but I built an API and the API really can serve any page, but I'm taking the existing stuff at that's at the bottom and refactoring it.

[00:40:58] **Tim:** So the now rather than. A bunch of conditional stuff. It's really just pulling, it's just a simple view page now is really all it is. Um, and that's sort of the, sort of my first step of, of refactoring this into another language is I'm still keeping the original language for the view, but honestly, it doesn't really matter where I'm getting these API calls from.

[00:41:22] **Ben:** I think that's a, I mean, I know that the. The JAMstack, the JavaScript API and markup, um, has becoming, is becoming a lot more popular in the last few years. And that's sort of, I think the basis of it is that you build your front ends kind of agnostic of all the backend technology. And then you could swap that out.

[00:41:44] **Ben:** I mean, it's hard to swap out a backend, but theoretically you could go from, you know, your own customized backend to like a headless. WordPress, I hear get mentioned a lot, um, and your front end is basically unchanged.

[00:42:02] **Tim:** So, I mean, the goal is to eventually to have a usable API that does everything that your original app did. And then the front end is pretty much agnostic of, you know, you can write it in view, you can write whatever you want and just consume the API and get the same results as you were from the original app.

[00:42:22] **Ben:** It's interesting stuff. I, I, there's, there's trade offs with everything in my, in my mind. I, I think, um, kind of going back to some of the stuff that Uncle Bob was talking about in the clean code that, I don't know if this is the right type of parallel, but that the thing should do one thing. I guess this is maybe not the best analogy here.

[00:42:43] **Ben:** I'm thinking maybe more of like things that change together should live together. I don't know if he mentioned that in the book. That sounds

[00:42:50] **Adam:** kind of like his argument against having multiple languages in the same file. Yeah, it could

[00:42:57] **Ben:** be. So sometimes I, I find at least my experience at work is that sometimes we'll break things up because we think they're different, but then you find that in practicality, you change part of one thing and then you always have to change a part of something else.

[00:43:14] **Ben:** And now that you've split them up, it sort of just becomes a pain in the butt. That every time you make a change, now I have to deploy two things. Whereas if they were together and maybe less quote unquote decoupled, it would, it would actually be a lot easier, but not, I'm not saying that's always the case, I'm saying that a lot of the, a lot of these things are always in contention with each other.

[00:43:36] **Ben:** One thing that. I think gets overlooked when you think about breaking up with technology is people underestimate how much they know about the current technology. Yeah. That when you've been working in something for a long time, there's so many little weird pieces of functionality and peccadilloes of the language and.

[00:43:58] **Ben:** Just things that you don't have to think about it. You just know how to do them. And when you move to another technology, you don't have that muscle memory anymore. You have, you have an understanding of how algorithms work and how request processing works. But you don't necessarily have at your fingertips, how do I share this variable with a, you know, a global request scope or like, can I abort a request the way that I might in the language if there's a, if there's a problem or like, just like little syntactic and functional pieces of a language, you have to relearn all of that.

[00:44:33] **Ben:** Yeah, that's, I think people underestimate how much work that is.

[00:44:37] **Carol:** Yeah, I've spent a lot of time Googling through all of this with, I mean, like you said, like, how do you dump something out? How do I get out of something? How can I stop this process right here to see what's actually going on with it? Because what it wants to do is it wants to finish.

[00:44:49] **Carol:** And then I don't know what went on right there. Like we've spent, I've personally spent a lot of time just trying to figure out how to debug in here and how to make it work right. And then you mentioned, uh, variables, right? So, I had to figure out why my environment variables aren't working because I was expecting them to be there.

[00:45:11] **Carol:** Well, then I found out, you know, it's all completely different. And this whole new stack of how it all gets set. So, it's just been a big learning curve. And it's taken a lot of time. Like, anyone who knew the language and knew what they were doing probably would have been done with this, like, done with what we're doing.

[00:45:25] **Carol:** But instead, I've spent... This is four weeks now on the project with three other developers and we're all learning it together. So, it's definitely a learning curve.

[00:45:36] **Tim:** Yeah, so multiply that across your whole organization. Yeah, it's huge. Unless you're planning on firing everyone and hiring all new developers that are proficient in the new language.

[00:45:45] **Carol:** You can't do that. But don't understand your app, right? Yeah, I mean, you can't hire new people to come write the language because they don't have the business knowledge for it. So, you're going to have them writing language for a process that doesn't work.

[00:45:57] **Tim:** If you feel that that's your solution, you got to realize that there's going, you're not going to be able to take the speed at what you're doing now and then continue at that speed, but just keep doing that in the new one.

[00:46:09] **Tim:** There's going to be a significant drop in production for an extended period of time, not a short period of time. Oh

[00:46:15] **Adam:** yeah, it's not quick. Yeah. I mean, when we converted from Adobe ColdFusion to Lucy, which. You hear so many people say, so I guess for those that aren't aware, Adobe ColdFusion is the paid CFML engine, requires a paid license, Lucy is the open source alternative, the Most prevalent and most, uh, modern.

[00:46:37] **Adam:** I don't know what the right word is.

[00:46:38] **Ben:** I think it's the, it's the open source version at

[00:46:41] **Adam:** this point. Yeah, for sure. Pretty much. Um, so many people say things like, oh, it just works, right? You just take your Adobe ColdFusion code and you move it over to Lucy and it just works. Maybe that's true if you have the world's simplest application, but...

[00:46:57] **Adam:** Five dagger. Yeah, I, I spent, uh, so we have a large application. It's not the world's largest application. There's like maybe a thousand different actions or twelve, a thousand, twelve hundred different actions that you can do. There's an admin interface and a public facing stuff. And it's a pretty complex application.

[00:47:14] **Adam:** Does a lot of stuff with spreadsheets and email and ORM, lots of different things. And. We didn't pick a specific amount of time, but it ended up taking nine months for me to port all the code over and That was, you know, we, we talked about like that coverage tool that I wrote. So just to make sure that we were testing everything.

[00:47:34] **Adam:** So we put a lot of work into that. And that was nine months, not just for me, but maybe another three months combined of everybody else's effort there at the very end to help drag it across the finish line. And when I say the finish line, I'm saying it was close enough to the point where we were like, the, the, we've reached the point of diminishing returns and we're well past it, right?

[00:47:53] **Adam:** The more time we spend in this, we're not getting the same level of, um, additional benefit. And so we got to that point where it was like, we're, we're close enough. Let's just turn it on and anything that breaks, we'll be here to fix it immediately. Right? Like, so we did nine months of development. We put it into production.

[00:48:12] **Adam:** And then those first, like two weeks was like, Oh God, what now? And then fighting fires. Right. But then it's done. Right. And every now and then now we'll find some, a little thing here and there, but for the most part, it's done. Did you switch OS's at the same time too? We did not. We will be switching from Windows to Linux here soon.

[00:48:30] **Adam:** That's one of my goals for 2021 is to get us on Linux in a docker container on Fargate. We're currently on Windows Easy 2. We did. The Adobe ColdFusion to Lucy port, and then we're gonna, the next sort of phase is Lucy on Windows to Lucy on Docker Linux. And one of the, one of the immediate challenges we see is that, uh, the operating system, like our Vue filenames and our CFC filenames and everything are going to be case sensitive.

[00:49:00] **Adam:** Case sensitive

[00:49:01] **Tim:** and different slashes. Yeah.

[00:49:03] **Carol:** When I was, uh, when I was dating Aurel, he came over and met with our Atlanta office at my, at where Tim is at now. He came up and met with them and was going through kind of what it would take to pour over. He worked at Lucy, right? Yeah, well, Rilo at the time.

[00:49:18] **Carol:** Yeah, him and Gert and all those guys. But yeah, so he came over and, you know, I kept hearing, oh, it's going to be so easy. And he's like, it's going to take a while. I was like, well, I'm glad like you're telling us up front, like, hey, you know, this is not going to be a quick thing because everybody's like, oh, it's going to be super fast.

[00:49:34] **Carol:** And I was like, no, but you need a lot of changes to make this work.

[00:49:38] **Ben:** You know, literally, I want to give a huge shout out to my teammate, Sean Grigson. He spent, with no exaggeration, three years trying to move us from Adobe ColdFusion to Lucy CFML, which was basically him every six months, just pulling down whatever the latest Lucy engine was.

[00:50:00] **Ben:** And seeing how much work it would take to convert over because there were there were huge issues with PDF generation, the image library, like the image processing libraries all changed the, um, there were all kinds of crazy edge cases, arrays getting passed by reference by default and Lucy not by copy like they do in Adobe Code Fusion, which caused some really crazy edge cases.

[00:50:24] **Carol:** How long ago was this? I wanted to know that before

[00:50:26] **Ben:** you kept going. So we've been fully on Lucy CFML, I think for like a year and a half. So it's, it, it was, it was like five years, four years up until about a year ago. And like every six months, he would just try it and see what he could do. And then finally he got to a point where.

[00:50:43] **Ben:** It was like Lucy 5. 2 or something. And he was like, I think this is finally

[00:50:49] **Tim:** feasible. Wow. Yeah. And to be clear for our listeners who aren't as familiar with CFML, this is porting one language, basically the same language to another language that just has to be run on another engine. And that's how long it took.

[00:51:04] **Tim:** So.

[00:51:05] **Carol:** Imagine completely

[00:51:07] **Tim:** switching technologies. Completely new languages. You not only have to do all that, you have to rewrite everything. So, you know, I'm, I'm not saying don't break up with your tech stack, but. No, I

[00:51:16] **Adam:** mean, if it's

[00:51:17] **Carol:** justified, do it. Break up with it.

[00:51:19] **Adam:** Yeah,

[00:51:20] **Tim:** if it's beating you, I mean,

[00:51:23] **Carol:** it doesn't deserve your

[00:51:24] **Adam:** love anymore.

[00:51:25] **Adam:** It doesn't deserve

[00:51:26] **Tim:** your love anymore,

[00:51:31] **Carol:** but it's not going to be quick and it's not going to be easy and it's not going to

[00:51:34] **Adam:** be painless. There will be tears and there will be blood. Yeah. You're

[00:51:37] **Carol:** going to have a lot of

[00:51:38] **Adam:** failure and loss.

[00:51:40] **Tim:** And that is exactly the reason why they're still looking for COBOL developers all these years later.

[00:51:45] **Adam:** And

[00:51:46] **Tim:** we're, and we're not talking about little companies.

[00:51:48] **Tim:** We're talking about fortune 500 companies, guys.

[00:51:50] **Carol:** Insurance companies are

[00:51:52] **Adam:** big.

[00:51:54] **Tim:** The Allstates

[00:51:55] **Adam:** and Geico's of the world. Anybody that has a mainframe is probably still employing a few COBOL developers and any extremely large company, you know, anybody over, I don't know, whatever, 10, 000 employees is probably got a mainframe.

[00:52:11] **Adam:** These AS400s,

[00:52:12] **Tim:** man, those, those machines are, they're beasts. You can like, you can like shoot a machine gun through them and they'll just keep chugging along. They don't care. They're amazing machines. They did it. They, they built them right. I'll say this to, to the business leaders out there who, you know, you, you went to, you went to business school, got your business degree, you know, nothing about tech.

[00:52:34] **Tim:** You really need to push back on, it is the engineer's job to make a good case for it and not just a good technical case, a good business case. Don't just assume that because they say this is going to make them prove it, right? And it's going to be hard for them because they're going to want to make the technical argument.

[00:52:54] **Tim:** That just tends to be what we engineers like to do. You look at it from the technical perspective and how it's going to affect us as developers, as engineers. But you're in charge of the business. You need to understand the effect it's going to have on your business. So make sure they have a good plan for that.

[00:53:11] **Tim:** And if they don't have it, help them build it. I'm not saying completely just push back and say no, but help them understand how this affects the business. Because ultimately we're not here to serve tech, right? We're here to serve a business and to create products and to create services available to our customers and our audiences, whatever they might be.

[00:53:31] **Tim:** So. You business guys, don't just, don't just swallow that red pill whole.

[00:53:38] **Ben:** One thing that was interesting just in terms of the business proposition of, of languages or of, of technologies is that your perspective on the cost of things changes over time. And I think when you're early in a company and you're early in projects, you look at the cost of the technology as being the limiting factor.

[00:53:58] **Ben:** And I think as companies continue to grow and age, you start to realize that it's the cost of developer time that is probably the most expensive. And I remember early on when a large portion of our company was trying to migrate from CFML over to Golang, there was a lot of conversation about like, Oh, you know, my Golang service.

[00:54:20] **Ben:** You know, it can run on 256 megabytes of RAM and I'm looking at my CFML pod and it's running like nine gigabyte heat space, right? And they're like, Oh, it's so expensive. And, and now, you know, years later, um, kind of at the different end of that spectrum, we had at one point looked at using, uh, Auth0 for user management.

[00:54:44] **Ben:** And at the time it would have cost something like a million dollars a year to manage the, the, the user base. And now, like four years later, we're re evaluating that decision to not, like, we manage all our users in house right now, which to me makes sense because, I don't know, that's the only thing I know how to do, but, but they're now re evaluating whether or not we want to try to migrate to an external, uh, user management provider and like cost isn't an issue for them anymore because they've realized like, oh yeah, building two factor authentication and social logins and, and, you know, passwordless logins.

[00:55:20] **Ben:** Like that costs a lot of people hours to build. Oh, yeah. Like that's not, yeah, that's not the limiting factor.

[00:55:25] **Adam:** Like it probably doesn't cost a million dollars a year though.

[00:55:28] **Ben:** Right, right, right. But I'm just saying like, like there it's before there was sticker shock and now they're realizing that you're paying for what you're getting and you could rather allocate those people to be building something else.

[00:55:40] **Ben:** Right.

[00:55:41] **Carol:** More development for your actual application as opposed to just user management.

[00:55:46] **Tim:** And I think, Ben, I think you, you make a broader point there. So it's a lot of times we, we try to build everything ourselves. I know I'm guilty of that. But I mean, you know, there's so many products out there that you can just, that are so much better than what you can build.

[00:56:05] **Tim:** That, you know, and some, and they're not prohibitive. I mean, just something as stupid as sending an email. Why, why do I want to build an email engine to try to track my emails and track my opens and my deliveries? And, you know, that is a lot of work, you know, that companies like SendGrid, just, just call their API and let, let them send your emails.

[00:56:24] **Tim:** And then all that reporting and all that goodness is, is baked in. For just pennies per

[00:56:29] **Adam:** email. So I want to make a counterpoint here. I think you guys are absolutely right, but I will also say that if you are just starting like a company, a product, something like that, you don't have money to burn, right?

[00:56:41] **Adam:** Oh no, you're detailed in house. So you would, I think the thing to do in that case is you, you send the emails yourself, you, you build your own feature flag service, uh, you know, stuff like that. You do your own authentication and you do just enough for it to pass, right? Yeah. People can log in. Maybe you don't have two factor auth and you don't have great email formatting and you can't, you don't have amazing email throughput, whatever.

[00:57:08] **Adam:** And you build it in a way so that when you have the money to outsource these things that aren't your core competencies... It becomes easy to swap in something else and start paying for that service. Totally. Single, single point of sending email, single point of authentication, I think is a little harder to do, but whatever the surface is going to be, uh, like we were talking about earlier with my tickets, right?

[00:57:32] **Adam:** Some sort of minimizing the surface area that you're going to have to change when you want to swap out a surface. Uh, Minimizing the surface area that you want to, take three, minimizing the surface area that you are going to have to touch when you want to, um, swap out a paid service for something you built yourself.

[00:57:53] **Adam:** Yeah. You're in house stuff. Yep. For sure.

[00:57:56] **Ben:** Wise words. Yo, talking about like building something that can be swapped out easily. And this is something that I did not learn a lesson early on. And it's been one of the worst problems that I've had to deal with. Is that if you have to do something that requires a lot of processing, make it asynchronous, even, even if you're not doing anything clever with it behind the scenes, build, build it so that it's asynchronous so that when you do eventually like put it behind a message queue or, or ship it off to some other external service for processing, like you've asynchronicity.

[00:58:34] **Ben:** Into it. I really, I really screwed the pooch on that one in a number of places. Yeah. And, and like, cause once you have, once you have a system that assumes that it's synchronous, it's a really hard sometimes to go back and start breaking that apart.

[00:58:53] **Adam:** Well, are we done? Yeah. Yeah.

[00:58:55] **Tim:** Okay, we're done. One thing we're not breaking up with is our listeners and our haters.

[00:59:02] **Adam:** Your hate matters transition. Hater. Your hate matters. Yeah. All right, if you like what we're doing here, you might want to consider supporting us on Patreon. You can find us there at patreon.com/WorkingCodePod. And new patron this week, Leon, welcome aboard. Thanks for joining. Every patron gets an invite to our Discord server.

[00:59:18] **Adam:** Hope to see you there soon. which is where we hang out and also where we organize fun stuff like the game night we had not too long ago and we have other perks available like early access to our new episodes and our after show. Our top tier on Patreon is for people who want to pay a little bit extra and to repay the favor we thank them by name or shout out something in their honor here in this section of the show.

[00:59:38] **Adam:** We currently have two top patrons so thank you especially to Peter and to Monte and to everyone that just listens to the show thank you for listening. You guys are awesome. Please share the show with your friends and co workers because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[00:59:59] **Adam:** Send us your questions and topic suggestions on Twitter or Instagram @WorkingCodePod, or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until

[01:00:11] **Tim:** then, your heart matters and so does your hate.

[01:00:36] **Tim:** So the schedule is tiny little

[01:00:37] **Adam:** peppercorns. Hey, you just smacked the mic while I was gonna let it go while you were letting everybody else talk, but you smacked the mic while you were talking. I can't edit that out. Oh

[01:00:44] **Tim:** yeah, sorry. Sorry.
