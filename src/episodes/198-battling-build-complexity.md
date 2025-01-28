---
title: "198: Battling Build Complexity"
description: "In this episode, the hosts discuss the complexities and frustrations of deployment automation and DevOps, particularly focusing on the challenges faced with makefiles, continuous integration (CI) processes, and build systems."
date: 2024-10-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/198-battling-build-complexity/id1544142288?i=1000671538571"></iframe>

In this episode, the hosts discuss the complexities and frustrations of deployment automation and DevOps, particularly focusing on the challenges faced with makefiles, continuous integration (CI) processes, and build systems.

They explore tools like ZX from Google and Oclif from Salesforce to find better solutions for running and organizing commands. The conversation also touches on the difficulties of maintaining older legacy systems like ColdFusion.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/198-battling-build-complexity.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** It's impossible to remember even what functionality is available, let alone what is the command that causes it to run, right? And so, like, I feel like we've got enough stuff that we're trying to do now that a menu would be better I'm just, I'm, I'm struggling.

[00:00:15] **Ben:** Yeah. Well, there's a, you just said a lot,

[00:00:19] **Tim:** Wish I could help you. I don't build it. I don't build any of that stuff. I have people who do.

## [00:00:23] Intro

[00:00:23] **Adam:** Okay. Here we go to show number 198. And on today's show, we're going to dig into deployment automation and a little bit of DevOps y stuff. Carol's not able to be with us tonight, so it's just the gentlemen.

[00:00:53] **Adam:** and as usual, we'll start with our triumphs and fails. so Tim, since Carol's not here, why don't we go to you first?

[00:00:59] **Tim:** Just want to know who in this group's a gentleman.

[00:01:01] **Adam:** okay. Scoundrels?

[00:01:02] **Tim:** There you go. A rogues gallery.

## [00:01:05] Tim's Fail

[00:01:05] **Tim:** I'm going with a fail. So just mostly cause I, I, I, lately, this past week I've been working mostly on kind of high level strategy kind of stuff and, putting some, my own coding work on a hold and it's just like, I want to stop talking about doing stuff and actually do stuff.

[00:01:22] **Adam:** Yeah.

[00:01:23] **Tim:** It's like, we've talked about it. We talked to, and I get it. You know, you gotta, gotta make. Good decisions and then go. But it's like, at some point it's like, all right, we've discussed this enough. Let's just move. So that's just kind of frustrating. Like when you, when you're like, do we really need that much detail to figure out the strategy?

[00:01:40] **Tim:** Cause you know, what is it they say about, strategy in a war? It never survives first contact with the enemy. And that's, that's the same thing with planning stuff. It's like, you, you're like, oh yeah, great. Everything's going to work great. And then you actually start doing stuff like bam, hit with the truck.

[00:01:54] **Tim:** And it's like, okay, I guess we're doing something different now. So. Yeah, that's my fail. I'm just a little frustrated, but I recognize the value of it, but I just want to get past this, this week. Yeah.

[00:02:05] **Ben:** I'll tell you, you said something a couple of episodes ago that has just kind of stuck with me and haunted me a little bit, which was you had a metaphor for giving value to the customers and you talked about holding your money so that you could save up enough before you put it into a high interest savings account.

[00:02:22] **Ben:** And, I dunno, I just, I mean, I'm, I didn't explain it very well just there perhaps, but there's something very visceral about that because I think people understand interest. And, and that paints such a good picture of why you should be giving value sooner than later. And it, cause it compounds and exactly like you're saying, no plan survives first contact with the enemy.

[00:02:44] **Ben:** Similarly, you know, no perceived value survives first contact with the customer. And the sooner you can start delivering value, the better product that you can build. All to say, the way you phrased it just has really, really stuck with me the last couple of weeks.

[00:03:00] **Tim:** Yeah. And I forget I, I was reading an article about that too, is, is basically that if you do work and it's just sitting there in between deployment to production, it's not doing anybody any good. Right. So it's only a value. You're only really gaining return on your investment when that stuff is posted to production and people are using it.

[00:03:19] **Tim:** You know, obviously you don't want to launch bad, you know, broken code, but at the same time, you don't want to sit on changes forever because those changes need to be out doing the work.

[00:03:29] **Ben:** Agreed.

[00:03:30] **Tim:** So anyway, that's me. How about you, Adam?

## [00:03:32] Adam's Triumph

[00:03:32] **Adam:** Well, I'm gonna go with a little bit of a triumph, and it's a very small triumph, but I'll take it, which is just that I, you know, I've talked recently about my struggles with my to do list, and I, I kind of realized I'm gonna go with a little bit of a triumph, and it's a very small triumph, but I'll take it, which is just that I, you know, I've talked recently about my struggles with my to do list, and I, I kind of realized Over the last week that I've been trying to fit my brain into a set of patterns that are supposed to help you get stuff done.

[00:03:52] **Adam:** Looking at my to do list app, you know, it's got different buckets where you can put stuff in and I just felt like it didn't map very well. And so I end up with, you know, a hundred things on my, like, look at this today list, which is just not, it's not a productive, you know, process. And so instead I've been trying to think about how can I alter the tools or use the tools in a way that fits the way my brain wants to work, right?

[00:04:17] **Adam:** Because the, the problem is I can't put these things on a schedule because I can't commit to them. I can't commit to like, okay, I'm going to work on it on this date. So it just has to go on the like, please pay attention to me list. But I can't, you know, you can't pay attention to a hundred things every day or in a day.

[00:04:34] **Adam:** And so. What I think what I'm trying to do is build like a list of like, these are the things that are important to get done soon. And then like, I'm trying to keep my today list to only the things that I'm actually going to do today. And if I, if I know for a fact I'm not going to get it done today, I push it off to the like, pay attention to this list.

[00:04:56] **Adam:** I don't know, names are hard,

[00:04:58] **Ben:** Yeah.

[00:04:59] **Adam:** um,like, yeah. I'm going to call it the soon list and the today list, I guess. And I feel like at the very least, it's helping me feel productive using the to do list app. Like I'm actually paying attention to it more and checking stuff off instead of coming back to it three days later and going, Oh yeah, okay.

[00:05:16] **Adam:** I did that one. And I did that one out of the hundred things on the list. I'm actually coming back to it five or 10 times a day and saying, okay, I did that one. This is what's next. sort of thing, which that's helpful for me. I feel like my productivity has gone up doing that. I just don't, but I think what I struggle with is like, so the, the getting things done method that we talked about.

[00:05:36] **Adam:** Whatever, a couple of weeks ago. Part of that is that you like set aside, you know, you say like Sundays at 7 PM, I'm going to sit down and I'm just going to go through my, my like inbox of all the stuff that needs to be organized and I'm going to put it on a schedule or I'm going to like put it on my list for tomorrow sort of thing. And I just don't have a good time to be able to do that, right? Like my day is pretty much, you know, wake up, go. And then I have like an hour to unwind at the end of the day and then I go to bed and then I repeat and then on the weekends, 90 percent of weekends, it's like I got a thing planned that I'm trying to get done that weekend so I don't have, it's not like I can make Saturday morning, you know, set aside two hours to, to parse and clear up my, my, my My to do list for the week or whatever, because some Saturdays I might, but most I won't.

[00:06:23] **Adam:** And so like, I have to find that like way that I can put it into the consistent routine, I think, to get it to click into a system that's going to work together.

[00:06:34] **Ben:** Do you guys work on a sprint schedule at all or any kind of periodic? Okay. I was going to say that in the past, I think I've taken that post sprint closing, like Friday afternoon, we're closing out the sprint. And then I'll take that as an opportunity to look at my board and just see if there's anything I want to move around. But,

[00:06:54] **Adam:** Yeah, no, we're just like, here's your thing, work on it when it's done, deploy it, go do the next thing, type of shop.

[00:07:01] **Ben:** that's the most frustrating conversation to have at work between engineers and managers. I think. Where a manager will pose the question, do you guys feel more comfortable working in one week sprints or two weeks sprints? And, and the engineers will be like, literally has no difference whatsoever.

[00:07:17] **Ben:** Cause all we do is work on the next task. And the manager will be like, well, if it's just a one week, it's harder to plan, but two weeks gives us something to plan. And we're like, plan what? All we do is work on the next task. But, uh, I will say that I, I can, I think our methodologies are different, but I can definitely relate to the idea that you either fight against a tool or you find a way to make the tool work for you.

[00:07:44] **Ben:** And one place that I find myself different than other people is my in progress column, which I think is historically supposed to be. The one thing you're working on, I'll sometimes have like seven tickets in that column. And some of those tickets will sit there for weeks. And it's just, I can't move it to an earlier column or to the backlog because I'll just forget about it.

[00:08:08] **Ben:** And I don't have the muscle of reviewing the backlog periodically, or even being good about grouping my onboard, which is like the pre in progress column that I have. And so having a pile of things in the in progress. Helps me keep them in the front of my mind without necessarily bogging me down. And I might drag things higher and lower in that list, but there is like a front of mind bucket that is the in progress.

[00:08:37] **Ben:** And so if I remember on a team where they have a WIP limit, WIP being work in progress for the listeners, where you can say, Oh, you can't have more than three WIP items across the team. It just, it just doesn't work for me. My brain just doesn't work that way. I'm not saying I'm right. I'm just saying that that's how my brain works.

[00:08:55] **Adam:** So, I mean, I, I am very similar, but mine is, mine is, I'm similar when you zoom out to the macro level, right? Like at work, I tend to have one, maybe two things that I'm working on concurrently, unless you get these things where it's like, okay, you know, this is going to be a six month project. I can do something on it today.

[00:09:12] **Adam:** And then it just has to sit and I'm waiting for a date to come, or I'm waiting for, A response from somebody like, I'm not counting those, right. But then aside from that, one, maybe two things are sort of my WIP, but if I zoom out and I look at life in general, right, like I've got a couple of different woodworking projects that I'm kind of like waiting for motivation or inspiration to work on.

[00:09:33] **Adam:** And, you know, there's like stuff that needs to get done around the house. And it's like, these are all sort of like the nebulous, like just kind of the clouds hovering over my head. Right.

[00:09:42] **Ben:** Absolutely. Well, exactly. Because there's like a, a different energy level you want to put into certain tickets. So I might have a ticket that I'm interested on, interested in, but isn't a high priority. But I know that if I have, let's say two hours of free time, it's something I want to do. So I don't want to move it out of the in progress because I'll forget about it.

[00:10:01] **Ben:** But if I leave it in the in progress. And suddenly I'm blocked on something else. I can look and say, Oh yeah, this one, this is now, this is the time. This is the moment I'm going to do this tick.

[00:10:11] **Tim:** I would imagine though, I mean, how many people you got working with you? Cause I would imagine the rule of like only keeping a few things in WIP is so that you're not sitting on something that someone else should be working on. But if it's just you, then what does it matter?

[00:10:24] **Ben:** that's mean everything, everything now is just me.

[00:10:27] **Adam:** Yeah, I

[00:10:27] **Tim:** So what does it, what does it matter?

[00:10:28] **Tim:** But

[00:10:29] **Adam:** I feel like the limiting WIP thing is the, I mean, for me, I'm, I get that from the books that we read, the, the Phoenix project and the Unicorn project. and that, so that very much comes from like a manufacturing mindset where WIP is actually like parts that have some work done on them that are waiting for the next process or whatever.

[00:10:51] **Adam:** And they're literally sitting there next to the workstation like. Blocking people from being able to walk through the aisle or whatever, right. Like that. And also, you know, like we were talking about earlier, right? You've invested money in that part, right? You've spent the time on it, you spent the materials on it, and now it's sitting there not making you money.and so,

[00:11:10] **Tim:** if you're the only one in the factory.

[00:11:12] **Adam:** but like I, I, I struggle a lot of times to see how that translates to software. And I'm sure that there are some ways, but it's just not immediately obvious to me. I've, other than like, you know, like we're just talking about the, the time investment and it's not making you money, but all right, well, that's enough for me.

[00:11:29] **Adam:** how about you, Ben? What do you got going on?

## [00:11:30] Ben's Fail

[00:11:30] **Ben:** I'm going to go with a fail, which is that, I've been just having a lot of trouble figuring out how I want to organize and build the client side portion of my file system. So I've mentioned, I'm working on this little companion app to my feature flags book. And it's just a little educational app showing people how feature flags work, or at least attempting to show people how feature flags work.

[00:11:51] **Ben:** And it doesn't have a lot of interactivity. It's mostly a multi page application. You click from one screen to another screen, but I have some hover effects. And then of course, there's a lot of CSS that just goes into styling anything on the web these days. And it's, if I was in an Angular app or if I was in a Svelte app, you know, or something of that ilk.

[00:12:14] **Ben:** There'd be a much more prescriptive approach to how you want to organize your files and what build scripts, and maybe even the framework comes with its own build process and you figure out, and it figures out like how to concatenate and split files and where the, you know, hashing content into file names and that jazz.

[00:12:31] **Ben:** and I'm, I'm finding that when you leave that arena and you're more in the simple world, there's not a lot of guidance, Or if there is guidance, it's like, there's a lot of sharp edges on it works when you do it this way, but not when you do it that way. And I'm just struggling to find the right balance of co location of files versus ease of build versus actual working build.

[00:12:58] **Ben:** So one of the things that I really like, for example, in Angular and Svelte and a number of the other frameworks is the co location of functionality. You have your HTML. And your CSS and your JavaScript, whether it's one component or it's files literally next to each other on the file system, I think that's less of an issue, but there is a co location of functionality.

[00:13:19] **Ben:** And there's something really, really beautiful about that. And now in a multi page application, what I'd almost kind of love is to have a cfm file that is my view, my cold fusion view, and then literally right next to it, a js file and a less file for my my CSS. And then somehow have a build process that scours the file system and pulls all those things together, or, you know, extracts the JS and the CSS from the ccfm L and compiles it down.

[00:13:48] **Ben:** And I, and I think,the, the mental model is actually not very complicated, but I just, I don't know enough about build processes to know where it is that I'm, things aren't working, so I'm just frustrated.

[00:14:01] **Adam:** I mean, you're, you're describing the growing pains that the, the front end community has been going through over the

[00:14:07] **Ben:** Right. Yeah, exactly.

[00:14:09] **Adam:** And, and I feel like that's why these frameworks are so popular right now, because it's like, all you have to do is pick your favorite framework. And it's like, okay, this is where you put your CSS.

[00:14:16] **Adam:** This is where you put your JavaScript. And you just hit the, you run npm run build and your project's done, right?

[00:14:22] **Ben:** it's so, there is something so attractive about it, but there is also something so attractive about just an old school request response model. I, I don't know. I mean, it's not that those aren't request response models. Also, everything is ultimately a request response model. It's more like, how does it actually get represented in the file system?

[00:14:41] **Ben:** How does it get represented in the user experience? And then like, what is the actual overhead costs of doing all these things? And I don't know, I'm just frustrated. I just wish it was easier. I don't, I don't mean like, it's one of those things where, if you're not doing it all the time, you relearn it at least to some degree, every time you go to do it, you don't have that stored up muscle memory, you kind of have to remember, oh yeah, this is kind of how we did it, but the last time we did it, certain tools didn't exist.

[00:15:09] **Ben:** Now. Newer tools exist. And I got to kind of go and learn those, but I don't want to learn them too in depth because I don't really want to, it's like, this is not the thing that I'm doing. This is just the thing that's blocking me from doing the things that I want to do. And, chatGBT doesn't necessarily help very much.

[00:15:23] **Ben:** And, and Google even isn't helping very much. Like just to paint a picture, I have, one JavaScript file and I'm importing the AlpineJS library. And then I import one of my libraries. And then in my library, I go to import AlpineJS there as well, because I have to register something. And in that file, it can't find AlpineJS, even though it could in the previous file that included it.

[00:15:49] **Ben:** I'm just like, I don't know what to do. It's, it's not like, it's not a path that it's trying to resolve. It's one of those, I forget what the term is, but it's like one of those pathless, you know, like importing React or importing Svelte, that kind of a thing. Anyway, I'm just, I, I'm just, I'm frustrated because I'm stuck on the thing that is not the point of the thing that I'm doing. So, fail. And all, and my wrists hurt. And I think part of that is all the stress.

[00:16:16] **Adam:** the, the, you're holding the stress in your wrists.

[00:16:19] **Ben:** Yes, I, I hold a lot of stress in my wrists. And for some reason I hold a lot of stress specifically in my right trap. And I don't know what that's about.

[00:16:28] **Adam:** Oh man. My left trap

[00:16:30] **Ben:** Yo, why are traps so dumb? Ha,

[00:16:35] **Adam:** I've been this afternoon while I was working, I was laying on a heating pad, like on my couch. trying to just, just help that thing relax.

[00:16:42] **Ben:** Yo, I take a lacrosse ball sometimes and I'll put it on the wall and I lean up against it and I just gyrate, you know, like every direction I can think of and trying to get the crunchies out and it, I don't know, I think maybe it works, but I'm never sure.

[00:16:56] **Tim:** look like a bear rubbing his back

[00:16:57] **Ben:** Yeah. Yeah, absolutely. Give me like a chain link fence or a pine tree or something.

[00:17:03] **Ben:** Anyway, that's me. That's my fail.

## [00:17:05] DevOps Automation

[00:17:05] **Adam:** Okay. Well, then let's get into the topic for the day, which is, kind of like a deployment automation slash development environment automations. you know, so way back in the history of this show, I ranted and raved about my love for Make files. probably a little too much if we're being honest.and it's come full circle.

## [00:17:26] Revising Adam's Build System

[00:17:26] **Adam:** I have started to hate our architecture Make files. not because the tooling is bad or wrong or anything like that. I just feel like. It almost feels like we have discovered a very powerful thing, and we just went like, zoom, we just dove straight into the deep end. And we made a lot of mistakes and now it's hard to back those out.

[00:17:48] **Adam:** And it's just, everything's overwhelming and, and confusing. So I'll give an example. We had, we have some tests for our cold fusion code and we have, GitHub that run our tests for pull requests, and we have a workflow that does our deploys, right? So when we're, when we merge the pull requests, then we go and we find the workflow that says CFML prod deploy, we click run now, and, and it runs.

[00:18:15] **Adam:** And one of the things that it does as sort of a final, safeguard is it actually reruns the tests as part of the deploy workflow so that If for some reason, you know, two different PRs got merged, similar timing, you know, it's like a final check of everything integrated together before deploy. I'm sure that's, kind of a best practice, but it's extremely frustrating for a bunch of reasons.

[00:18:42] **Adam:** Mostly because the, our build chain with ColdFusion, and I, I don't, I don't think that this is unique to us. Let me put it that way. our, our ColdFusion build chain is slow.and you know, like I've said before, I'm sure that an expert in this stuff could make it reasonably fast. That's not us. And we have bigger fish to fry.

[00:19:03] **Adam:** So it's just slow. When I say it's slow, I mean that, you know, you've got your GitHub action. If you take away all the stuff that's not. Build the containers that you need in order to run the tests, start them and run the tests. If you take away everything else, or I'm sorry, if you only look at the, the stuff that's not those steps, you're looking at, it maybe takes 20 seconds, right?

[00:19:23] **Adam:** It's the startup costs and reporting, success, fail, that sort of thing. But the, the part that's important, building the containers and starting them and running the tests takes like eight, nine minutes. And to the point where, sometimes, so the, this is a frustrating thing too. In some ways, like if you make certain types of errors, I'm not, and I, I can't think of off the top of my head, I guess it would have to be syntax errors.

[00:19:51] **Adam:** Like the CFML engine will just sort of like fail to start up or it starts, but the, the framework can't start, right? Like you've got DI1 going to do your dependency injection and, and you're like the application itself won't start. And so the application, the container never becomes healthy because it can't respond to a request because that, you know, every, every request just goes to an error page basically.

[00:20:13] **Adam:** And so, because the container never becomes healthy, through the, the nuances of all of this, like Docker stuff, it can take it, I think. Potentially it could sit there forever. Like I think it could sit there for an hour or two hours, never becoming healthy, and so the test never runs. So we have a thing that's like, okay, start that CFML container and then only give it, you know, X number of minutes or seconds for it to become healthy.

[00:20:41] **Adam:** And if it doesn't become healthy within say five minutes, then consider that a timeout, kill the container, mark the test as failed and continue. So that was happening, right? So we had a very minor issue, but it was, it was kind of eye opening, right? So minor issue just needed to get a bug fix pushed, made the change, works locally, tested it locally with manual testing, And then, put the pull request up and I forget if the pull request tests passed or not, but long story short, you know, we merged the PR, we tried to deploy it and the tests, the, the, the test part of the deploy script is timing out every single time, like I reran it, reran it like four or five times, which is, you know, like, like an hour's worth of waiting for this thing to run the tests, basically, cause it, it waits for five to six minutes, and then fails.

[00:21:34] **Adam:** And so after that many failed attempts, I was like, okay, this is not acceptable. We, we cannot be sitting here without the ability to deploy code to production.because of tests that let's be honest, are not that valuable, not because testing is invaluable, but because our tests for our code for this particular part of the application are not that valuable.

[00:21:57] **Adam:** It's, it's slow and it's not that valuable. So I was like, I'm done. I quit and I just, I, I made a pull request. It's like, you know, it goes into the make file and it's like, okay, this is where the tests run. And I commented out the part that actually builds the containers and runs the tests. And I said, you know, echo skipping tests because dumpster fire, and I committed that and pushed that and got that through PR and that got merged and I went to deploy and it still failed because.

[00:22:27] **Adam:** I fixed the wrong makefile, right? We've got like makefiles that go on, that extend other makefiles, that extend other makefiles, that include other makefiles and, you know, there's just different test targets in different places for different reasons. And I, like, I changed the one that's used for local development, not the one that's used for CI builds sort of thing.

[00:22:47] **Adam:** And I was, I was just kind of furious and fed up. And so I actually sat down and I wrote like a document of like, okay, starting from scratch. Knowing what I know now, what makes a good build system, like what are the must haves, the nice to haves, and the must nots?and just was like, okay, and, and the, on the must haves list was like, it has to be built with technology that my team is familiar with, So it either has to be built with CFML or JavaScript or some fork of those things that, that we're all familiar with on my team, like TypeScript would be okay, for example, or like maybe Bash.

[00:23:25] **Adam:** You know, these are the things like, I don't want something that's built in Rust because nobody on my team, I think I have one guy on my team who's poked at Rust a little

[00:23:31] **Ben:** Right. Right. Makes sense.

[00:23:33] **Adam:** so that's on the, the must haves list. So I just kind of wanted to come at it from first principles, like, okay, it has, and I made a list of all the stuff that the current builds are doing.

[00:23:42] **Adam:** Like these are all the Docker commands that are being run for various things. I just, I, I'm still failing to find something that satisfies all of my needs.

[00:23:52] **Ben:** Yeah. It's a really complicated landscape. And then also the complexity of apps has increased. And so you have these containers that are responsible for multiple things, essentially, right? There's serving up the CFML, which is rendering the HTML. And then there's probably also. JavaScript and styling build systems.

[00:24:13] **Ben:** I know you have your Svelte areas and if that's all part of the same build, or maybe it's part of a different build, or you have to decide whether it's part of a different build, and then if it's part of a different build, does it get pushed to a CDN, for example, because if you think about living in the world of containerization.

[00:24:33] **Ben:** You're not just pushing up one container, you're building an image, and then that's getting deployed to multiple containers, presumably. So at any moment, Production has different versions of the application running for some period of time and a user makes a request and who knows what container it gets routed to.

[00:24:54] **Ben:** And then that container might request a different JavaScript file. So you have to like make sure that the wrong JavaScript file doesn't get cached. It it's I'm not, I have no answers, but it's just complicated.

[00:25:05] **Adam:** Yeah, I mean that what you were going through there kind of to me sounds like some stuff you've mentioned from the architecture at your company where you

[00:25:12] **Ben:** yeah, yeah, yeah. A hundred percent.

[00:25:14] **Adam:** that's not exactly how ours works, but you know, it made me think my, this, this issue that I've been dealing with, especially today, but just like for the last week or so. Sounds to me like it is the sort of the, the enterprise, you know, TM, version of your fail from today, right? You know, you're, you're struggling against, you're trying to like, I think when you were talking about your fail, I was sitting there going, you know, this would be so much easier if you weren't so strongly clinging on to CFML, right?

[00:25:40] **Adam:** Like if

[00:25:40] **Ben:** it was just a next project or

[00:25:42] **Adam:** right? And the exact same thing can be said to me. Now, to be fair, I think maybe six or seven years ago, I put up, of not a vision board, but you know, just like a, okay, this is the, I put up a cork board in my office and I was like, okay, this is stuff that has to get done this month.

[00:25:59] **Adam:** This is stuff that has to get done next month. And I put up like four months and then I had like the, like a block of it was like for sometime in the next year and sometime in the next five years, right? Just like, Keeping abreast of what's going on.and in the, this was, you know, granted six or seven years ago and in the sometime in the next five years block, the only thing in there was GTFO CFML.and here we are still on it. You know, I, I've gotten spelt's foot in the door for us, but it is so hard to get off of legacy product that is still working, that is still making money for just for the purpose of. Basically developer experience, right? That's really the only value add, which is so hard.

[00:26:43] **Tim:** Yeah, the old, the old need to make money. Always getting in the way of our fun.

## [00:26:48] Growth in Complexity

[00:26:48] **Ben:** Well, I I'm so jealous sometimes of, I know Tim has described his, his laptop build. Where it's just a bunch of scripts that run some installs and pull some things and he could, his laptop could catch on fire and it wouldn't be a problem because he would just hit run again and it would just build a new laptop for him.

[00:27:05] **Ben:** And I don't know, I just, there's something so

[00:27:07] **Tim:** Although I haven't tested that in many years,

[00:27:11] **Ben:** but there's

[00:27:12] **Tim:** the battery is starting to get old on this thing. I may need to test it out pretty soon.

[00:27:15] **Ben:** there's something very powerful about a script that can just brute force, an action. And I think sometimes that's what I lament is, is the complexity of some of the scripts where almost what I wish I had was just. Either a node file or a CFML file. And literally I'm just doing file directory stuff and concatenating things and maybe running it through a CSS compiler.

[00:27:39] **Ben:** It's like, you, you'd miss a lot of the really nice stuff that some of the modern stuff gives you, but it would be so clear what's happening and you could throw in some log statements and figure out where something's going wrong. But it's your, you'd be trading off ease of debugging and understanding with With robustness and it's so frustrating that it feels like that has to be a choice.

[00:28:05] **Adam:** And again, I'm also really, thinking hard about the thing that we've said before. I'm sure it's one of those like laws of software, it's like a complex system that works is inevitably found to have evolved from a simple system that works. And I mean, not to say that we started with something complex, you know, we did.

[00:28:24] **Adam:** Originally start with like, okay, here's a makefile and it just has like some targets in it that run docker commands. Like that's easy peasy, right? And then we started to, do things with like, we, I guess we probably, wanted it to be able to work for a couple of different kinds of projects, right?

[00:28:40] **Adam:** Some of our lambdas use docker. Some of them are just like zip files of JavaScript code. And then we've got our, CFML app, right. And that's in Docker as well. And then like about a year ago, more or less, I mean, we really buckled down and finished it right before our co op started, but approximately a year ago, we were like, okay, we really need to be more professional about our secrets management.

[00:29:02] **Adam:** And so we, you know, we, we've had 1Password and we use it, but we still had a lot of, secrets, you know, embedded in the code or just an environment variable, like env files, that sort of thing. and so we actually found some really cool tooling from 1Password. They have some stuff that you can like, You can have on your server so that they can do real time lookup of secrets out of specific vaults.

[00:29:28] **Adam:** and you can do like, sort of compile time secrets stuff, which is interesting. So I've mentioned our configs, like our central config service before, which is basically just like some JavaScript files that we compile down to JSON files. and then, it's all hooked up to a web service where you can say, okay, I need This setting for this customer in this environment, right?

[00:29:50] **Adam:** I need like, Ben University production, admin URL, right? And it'll, you know, go look that up out of the JSON file and give it back to you. And, there's also secrets in that as well, right? So we, we talked to a couple of weeks ago about the changes that I made for S3, right, where it was, there was a whole bunch of S3 settings and I cleaned that up and moved it down to just a handful, and, and a lot of that was duplication of, secrets.

[00:30:16] **Adam:** For the various S3 buckets and stuff too. And so what ended up happening there is you get, like there's a specific syntax where you can say, okay, here's a token and it represents, and there's like text in that token that says, okay, this is the vault name. This is the item name in one password. This is the, like the field, right?

[00:30:33] **Adam:** I want the username here or the password or whatever. and it'll interpolate those into your file sort of like at compile time, or I think we have one that runs, on, on application startup. It'll do that. And so that's very useful as well. But, and then you've got, okay, so now my config files just have these like tokens in them, right?

[00:30:52] **Adam:** It doesn't have the actual secrets, but I need to be able to run my local development environment locally. So I need to be able in my local environment to do that interpolation as well. And so they have like tooling where you can hook that up and it, it'll say, it'll use whatever your token is in your personal one password vault, right?

[00:31:12] **Adam:** So it used to be. I think it was called personal, but they, they're, they had some, confusion issues with like people who would have one password for work and one password for home and personal just felt like too much home. And so they called it, they switched it and now it's called the employee vault or whatever, which is like every employee gets their employee vault, but it's your personal private stuff.

[00:31:34] **Adam:** anyway, so we have a, we have a command line command. That will, it looks them some stuff up in files on your on our local machine to say, okay, these are the, these are the environment variables that I want to create for the duration of this command. and it'll go look them up out of one password, right?

[00:31:51] **Adam:** So like if we're going to be pushing to AWS or pushing to GitHub, it'll pull GitHub and AWS tokens out of one password, set them up as, you know, environment variables just for the lifetime of this command, run the command, and then the command ends and those environment variables are now sort of cleared out and it's, so it's more secured that way.

[00:32:10] **Adam:** And it uses my personal token out of my employee vault to do that interpolation, to like make the connection to one password to get the, the secrets that it needs. And so Like me as an admin of r1password, I have access to everything, but like maybe you as a junior developer don't. And so if you try to run the same command, it would not let you interpolate them because you are junior yet.

[00:32:35] **Adam:** So just to, and I go through all of that just to illustrate, like it, just this one piece of the puzzle can be extremely complicated. And confusing to, to figure out. And then you got to, okay, we're hooking that in. So you, you might run this OP command before makefile, right? So it's like OP make up or whatever, and that'll run the make up command, but with the, with the environment variables added and the makeup will go, okay, we're going to push some, we're going to run some Docker builds, but it's going to take these environment variables that I assume are created, and I'm going to pass those in as arguments to the Docker builds.

[00:33:11] **Adam:** Right.

[00:33:12] **Ben:** And this is the compile time stuff you're talking about then.

[00:33:15] **Adam:** it's a little bit of

[00:33:15] **Ben:** Yeah. So a little, there's a little that.

[00:33:18] **Adam:** yeah. And so it's just like, we started with something simple and I think that we just kept bolting onto it in ways that worked, but that like, we just didn't have enough experience to go, but this is getting too messy, this, this doesn't feel right, and so now here we are like 10 iterations later, and it just, It now, to me, it is obvious that this is not a clean, maintainable system.

[00:33:44] **Adam:** And I'm feeling the frustration of that. So I took some time today and I was looking at some other alternatives or kind of evaluating other alternatives and based on like those criteria I mentioned before, right, the must haves and the nice to haves, it's like, it's got to be something that is going to be, that anybody on the team could work on.

[00:34:02] **Adam:** And so I was like, okay, well, I didn't want to do Bash because we do have a couple of Windows holdouts, you know, and, or potentially new hires on the team might want to be Windows and who knows what WSL, that's just like a black question mark to me. but, so like, I'm, I'm trying to avoid Bash by itself or like native Bash, so that to me kind of just leaves JavaScript and flavors of JavaScript.

[00:34:25] **Adam:** So there were two things that I looked at.one is called ZX, which is a project from Google.and it basically, it's like just kind of raw node with a lot of built in helpers for forking out to the command line, right? So you can do like await backticks, you know, cat package. json, pipe it to grep.

[00:34:44] **Adam:** Right, so that's your command. You're running that and then it gets that back as a, as a promise and you await that and, and so whatever the standard out from that command was, it is, yeah, it is pretty cool. and there's a lot of stuff built into it, which is pretty neat. the, and, and, you know, then you've got all of the, Node.

[00:35:04] **Adam:** js command line ecosystem of, of, you know, things that are useful to use there. there's a bunch of libraries that make, you know, colorization and JSON parsing and all this other stuff, like really interesting and useful.and there, there might be something there. the, I have kind of, that is for the moment, kind of where I've landed.

[00:35:24] **Adam:** But the, the immediate problem with that is organization, right? How do I write something that is going to allow us to organize this code cleanly? I need like a, I need like a Svelte kit for my CLI, to like, tell me, okay, put the command files here and this is how you organize it. It's how you build a menu sort of thing.

[00:35:43] **Adam:** and, but, so setting that aside. Before I decided to mess with that, I was looking at a project called Oclif, O C L I F, which I believe is like an open source command line framework. That's where that comes from. and That is, so that is, I mentioned ZX is a project from Google. OCLIF is a project i, I, I believe it's come, comes out of Salesforce.

[00:36:06] **Adam:** The, at the bottom of the OCLIF website, it says copyright Salesforce. So, whatever. But, and that, so again, that's just a JavaScript solution for building command line interfaces. It's got some, it, it's been around a long time. They just released version four stuff. They've got some pretty interesting like generators and stuff.

[00:36:24] **Adam:** And it does seem to like generate pretty organized code. I like that about it, but it doesn't have the, the DX of like a weight, this command line command. Right. And so I'm sitting here thinking like, I'm going to have to figure out how to, you know, fork out to run a Docker thing. I got to figure out the environment variables thing.

[00:36:46] **Adam:** all the, the, the args and stuff. And. Then, on top of all that, it's, class based JavaScript stuff, like the, the Oclif, just the way that it works. It expects classes, which rubbed me the wrong way. I am a, I'm a diehard, never classes, person in

[00:37:03] **Ben:** enough.

[00:37:05] **Adam:** not that I, not that I dislike classes in other languages, just like the, when I think of JavaScript, you know, I've got 20, 30 years of writing JavaScript under my belt.

[00:37:13] **Tim:** Never needed classes for anything, and so, you know, just like, thanks, no thanks. Functions first.

[00:37:19] **Adam:** Yeah, so, it's just, I'm just, so here's, here's where my head is at right now. I'm kind of thinking that from an organizational perspective, I would kind of like just to have a folder of files that are a command, right?

[00:37:34] **Adam:** Think of it like a folder of bash scripts, right? But let's, let's just say they're JavaScript files that do stuff. and so that I know, okay.this is the file that's going to be running the tests for our ColdFusion application. Right, I can look at it based on the file name and say, okay, this is the CFML tests thing.

[00:37:51] **Adam:** and it, it should not, I hope, or this is my intention, it should not, like, go crazy with, inheritance and extending this and that. I just want it to be like, here's the script, and it does, it goes docker up, box test, box run, you know, whatever the, the things are. Just, like, put it in there, sort of, as close as you can get to just, like, just plain English, right?

[00:38:10] **Adam:** Don't, don't go crazy. Architecture wise. And then something to like organize those and like, maybe hopefully make a menu out of them or something like that. That's another thing too, is like, we've got so many make commands in this one little, yeah, I say little ecosystem, but I mean, this is, you know, make files that extend make files that include five other make files.

[00:38:32] **Adam:** And so there's like a lot of commands available and we do have like a, you can do make help and it'll list them all for you. But aside from that,It's impossible to remember even what functionality is available, let alone what is the command that causes it to run, right? And so, like, I feel like we've got enough stuff that we're trying to do now that a menu would be better to just be like, okay, I want to turn on my development environment.

[00:38:56] **Adam:** Like, yes, typing a command might be a little faster if you can remember it. But, you know, it's not, if you can bring it down to like three clicks, it's Not clicks, but you know what I mean? Like three selections in the CLI. I'm okay with that. and then the more esoteric stuff, if it's four or five layers deep.

[00:39:15] **Adam:** Okay. That's fine. Whatever. But like, I'm just, I'm, I'm struggling.

[00:39:19] **Ben:** Yeah. Well, there's a, you just said a lot,

[00:39:23] **Tim:** Wish I could help you. I don't build it. I don't build any of that stuff. I have people who do.

[00:39:28] **Ben:** but it is the frustrating thing too, that I've seen looking at other people's makefiles and I know very little about makefiles other than high level. It's a series of commands. But there's inevitably some comment in the makefile where it's like, this is the makefile that, or like, this is the command that you run when doing local development.

[00:39:46] **Ben:** This is the command that you run when you're doing, like, development inside of an EC2 instance. This is the command that you run when you're building. Building for deployments. and, and I know that there's probably a hundred percent valid reasons for all of that, but I, I'm getting to a point where I'm very frustrated anytime there's something different between the way something works in production and the way something works in development.

[00:40:10] **Ben:** And I, and I know that that's just a reality, but if I can go on a side quest here for a second,

[00:40:16] **Adam:** hmm.

[00:40:17] **Ben:** I I've the idea of using like a mocked out version of a production system in a local development environment. just rubs me the wrong way. Like if I needed S3 bucket for development, I kind of just want to have an S3 bucket that I use for development.

[00:40:36] **Ben:** I don't want to have like a completely mocked out AWS services. Or if I have need for a Lambda function, like I kind of want to just make a call out to a Lambda function, but like, I don't know how that works necessarily. Like, how do you make sure that that live Lambda function doesn't accidentally do something in production?

[00:40:56] **Ben:** but I just, I, I hate the idea, not hate, hate's too strong a word here. don't like any surprises. And I'll only tell, I only say that I do run into surprises where some system that is two service calls away, which happens to be using some mock version of a system. We hit some edge case where suddenly file uploads don't work because it's not actually an S3 bucket and it works in production, but I can't test it locally cause that's not working and no one wants to spend the time to figure it out.

[00:41:27] **Tim:** Or where there's different firewall rules between production and

[00:41:31] **Ben:** exactly.

[00:41:32] **Tim:** right. This thing works, works great locally and in testing, but yeah, completely different firewall rules and production because of security reasons.

[00:41:40] **Adam:** yeah, that's another thing too. Like we're a small team, you know, my team is three full time developers, including myself, and now that our co op is complete, I am pretty much a full time developer where my current compliance duties are pretty minimal. So I'm considering myself a full time developer and. Even with all three of us, doing coding, we just have so much surface area of our product that there's no way we can stay on top of all of it all of the time, right? So even just like, you know, so we probably have, I don't know, 25 to 30 lambda functions. Each of those has a package JSON with NPM dependencies that are getting more and more out of date every day.

[00:42:21] **Adam:** and

[00:42:22] **Ben:** The struggle is real.

[00:42:23] **Adam:** like all, just take that, multiply it by another dozen for all the other things that are not just package. json, right? You've got other, other things that are similarly sort of rotting and need some upkeep and some garden tending. And you just, you can't, you've got to get other new work done as well.

[00:42:42] **Adam:** And so then you come back to that. There you go. So then you have a project that has you come back to this, you know, some project that you haven't touched, in, in months or years, and now the build process doesn't work or it does work, but only if you don't change anything about it. Right. If you don't upgrade any of the dependencies, it'll still work.

[00:43:03] **Adam:** and it's just, it's just. Extremely frustrating and it makes me want to, push back against breaking things out of the monolith, right? So it, if you were to simplify and just say everything has to be in the monolith and the monolith has one way to build things, one way to write code, all the JavaScript is handled the same way, all the CSS is handled the same way. That way, for a small team like ours, At least that part, the meta work of going from source code to runnable code is constantly being, the garden of that is constantly being tended. and you don't wind up with these build processes that are broken because you haven't touched that application in four years. At the cost, I guess, of you might have things that are running suboptimally, right? They just can't scale as much because you haven't broken them out to be a lambda function on its own or whatever.

## [00:43:59] DX vs Optimization

[00:43:59] **Ben:** I, I listened to a quote one time, I think it was in a podcast and I've brought it up, I think on this podcast before and I've brought it up to other people and it rubs people the wrong way a lot. And the quote was something like, I'd rather have consistently bad than inconsistently good.

[00:44:18] **Ben:** Meaning that if I can understand everything and it's consistent, even if it's suboptimal, it's still better than having these micro optimizations that are harder to understand. Yeah,

[00:44:28] **Tim:** the devil, you know?

[00:44:29] **Ben:** yeah, absolutely.

[00:44:31] **Adam:** I like that. I think that bad might be the wrong word there. Just, it makes it, it's very negative where I feel

[00:44:37] **Ben:** Right. Like consistently subpar, but I had a mental breakthrough and I don't mean like I discovered something. I mean, somebody finally said something in a way that clicked in my brain, which was that when I was thinking about things that were scaled. Independently, meaning maybe I have a web server and it doesn't get a lot of traffic, but then I have an image processor and it needs to be scaled very differently because it's processing images.

[00:45:04] **Ben:** Historically, I had always thought of those two things as being two completely different services written with completely different code and deployed in completely different ways. And someone was talking about the project that they were working on, but they were talking about it in the context of a monorepo where they had multiple services.

[00:45:25] **Ben:** Contained within a single source code repository. And the way they explained it was they were trying to dumb it down for me, but I think that it actually worked in a way that they didn't anticipate. They said, it's basically a monolith, but we're just activating different parts of it in different services.

[00:45:44] **Ben:** So here's this monolith and we deploy it in this way. And it only receives certain traffic to certain routes. And then we deployed over here and only, you know, like only the lambda functiony type parts of the monolith ever get called in this particular service. So it was actually the same code base being deployed in different places, but they were acting almost as two entirely different sets of services.

[00:46:05] **Adam:** It's really interesting.

[00:46:06] **Ben:** I was like, Oh my God, that, that made sense to me in a way that nothing had made sense previously, or it felt like some sort of mental breakthrough because it was this consistency of code base. And you could still scale parts of it independently without it actually being this totally isolated set of functionality. I don't know if that's terrible, but you know, cause like, we all know that, from our, from our work with ColdFusion, that it is a beefy, resource hog, you know, you can't, you can't compete with people who talk about Golang where they're like, Oh yeah, I can take a million requests a minute. And I'm running on four megabytes of RAM.

[00:46:44] **Ben:** You know, like that's not the JVM period, right? So you only get so much mileage when you talk about scaling something independently, when there's a kind of a, a fundamental floor with how low you can go in terms of the resources you need to the point of being consistently suboptimal. If the whole thing is written in a language that you feel extremely comfortable with and a set of constraints that you feel comfortable with, like, yeah, maybe it sucks that some of your deployments require more RAM than they might normally, but at the benefit of, of ease of development.

[00:47:21] **Adam:** Yeah. It's just, for us, You know, I've had that realization, and would I do things differently if I could wind back the clock? Maybe slightly, but at the same time, like, I do feel like of the stuff that we have broken out of our monolith was, A, it has helped the monolith run better, and B, it has scaled way better than the monolith.

[00:47:45] **Ben:** Right.

[00:47:45] **Adam:** Now, granted, if we could get the, if we could GTFO CFML, uh, would that change the, the efficacy of the monolith? Probably. I don't know. Maybe one day I'll know, but, that day is not today.

[00:48:01] **Ben:** Oh, this stuff is so frustrating. I mean, this is why they have teams, you know, people who work on this kind of stuff. It is, it is a specialization.

[00:48:09] **Adam:** for sure. I do like that, that paradigm of like, okay, you know, we're just going to deploy the whole application in all the places and then only, you know, light up, only start that process for that one part or whatever. It's almost like a, like a sparse checkout mentality, right? So like when we deploy our lambdas, they're, our lambdas are in kind of a mono repo with our, with our monolith.

[00:48:32] **Adam:** And we, when we do those, you know, a lot of our Lambda functions are just like, okay, here's some JavaScript, put it in a zip file and use the AWS CLI to upload it. And that, you know, we're talking about like a two, three meg zip and it's in the same repo as our ColdFusion stuff. So what we do to make those builds run faster is we use a sparse checkout from Git.

[00:48:50] **Ben:** Interesting. So you check out just like a limited set of the files.

[00:48:54] **Adam:** Right. Yeah. So the, like the Git repo toward the root of it, not in the root, unfortunately, but toward the root has, like a lambdas folder. And in that lambdas folder, there's a folder for each one of our lambdas. And so like, if we're building the ABC one, two, three lambda, it's just get sparse checkout and here's the path.

[00:49:10] **Adam:** It's like, you know, like slash whatever slash lambdas slash ABC one, two, three. And then it's like, okay, zip that up and deploy that. And that way it doesn't have to check out the entire history of our, Get repo and all of our CFML code, which would add an extra 15, 20, 30, 50 seconds

[00:49:26] **Ben:** Yeah. Every little bit counts though.

[00:49:29] **Adam:** Absolutely.

[00:49:30] **Ben:** I've never done a sparse checkout. That's interesting.

[00:49:32] **Tim:** Yeah, me neither.

[00:49:33] **Ben:** Someone had, I think this is a good analogy here. Actually. someone was talking about the Apple. I think this was the M1 chips. It was like the M1 versus the M1 Pro. I'm probably not good at the product names.

[00:49:46] **Ben:** Right. Where. It's like you get more resistors in the M1 Pro, but it's literally the same chip. It's just like they disable parts of it. Or no, this is what it was like, the same chips all go through testing and on some of the chips, the transistors are broken and that's the M1 chip. And then when the transistors aren't broken, that's the M1 Pro, something to that effect.

[00:50:07] **Ben:** And that feels to me very much like the Monolith getting deployed into two different places where it's like, it's just literally less complex and less expensive for us to do it one way and then break it, you know, apart into two different throughputs than it is to have two totally different build processes.

[00:50:26] **Adam:** Yeah. I mean, that was an anecdote. I remember bringing up a while back and I don't think it was specifically the Apple Silicon, but like, you know, older Intel stuff, right. They would say like, okay, we're going to aim for, you know, whatever number of transistors working and then they just kind of bin them by roughly how many are working and that's that's the like clock speed or I don't know exactly how it works but that's that's basically it's like we tried and we only made it 80 percent of that and so this is a 600 megahertz instead of a 1200 megahertz or whatever so.so, all of that to say, if anybody has any awesome ideas, please join our discord and come help me out because we've got a, we've got a code help channel and I would welcome your ideas and your feedback because, this is a source of great frustration for me.

[00:51:12] **Tim:** I'm sure one of the Bryans will have some feedback.

[00:51:16] **Adam:** Or, you know, even if you don't have any ideas, but if your name is Brian, we also welcome you to the discord.

[00:51:20] **Ben:** very Brian friendly.

[00:51:22] **Tim:** Mary Bryson. Yeah.

[00:51:24] **Ben:** Not like those other podcasts,

## [00:51:27] Patreon

[00:51:27] **Adam:** All right. Well then, this episode of working code was brought to you by being consistently suboptimal and listeners like you. If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:51:39] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons Monte and Giancarlo, you guys rock.

## [00:51:47] Thanks For Listening!

[00:51:47] **Adam:** we're gonna go record the after show, and if you're not familiar, the after show is where the, outro music is gonna play, and then we're just gonna keep talking.

[00:51:56] **Tim:** And who knows what we're gonna talk about. I imagine there might be some Babaverse talk because Tim and I, are, are both, I think Tim's done reading the new Babaverse book. I have less than a half hour left in the audio book. Oh, I hear my tailhaut ends.

[00:52:09] **Adam:** no. And anyway, yeah, so we're just gonna noodle on about, you know, whatever comes to mind.

[00:52:16] **Adam:** And if you, if that's something that interests you, then, you should go to patreon.com/workingcodepod. Throw us a few dollars a month. and you'll get that. You'll get like special gold status in Discord, which opens up some secret channels, and make turns your name gold. So everybody knows that you're a supporter.

[00:52:32] **Adam:** if you'd like to do that, you can go to patreon.com/workingcodepod. We'd be happy to have you. Discord access is free. you can go to workingcode. dev slash Discord. and we would be happy to have you, especially if your name is Brian. That's it for this week. We'll catch you next week. And until then,

[00:52:48] **Tim:** It's not a whip or a work in progress. It is a fully shipped feature. Your heart matters.

[00:52:53] **Ben:** very nice.
