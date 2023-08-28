---
title: "126: Documenting Decisions"
description: "This week on the show, we talk about documentation. And not just the 'how' of software, but the 'why'."
date: 2023-05-10
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/126-documenting-decisions/id1544142288?i=1000612476787"></iframe>

This week on the show, we talk about documentation. And not just the "how" of software, but the "why" - the decisions that we've reached, as a team, regarding the technologies that we use and the architectures that glues everything together. Of course, writing the documentation is only part of the challenge; keeping the documentation up-to-date is a whole other source of friction for most teams.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/126-documenting-decisions.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** what keeps going through my head is like, what happens if, you know, you're on your way to your team, offsite, retreat sort of situation and the plane goes down and so now your entire team is dead you know, so they have to hire a bunch of people to come in and work after you.

[00:00:14] **Adam:** And now these people have

[00:00:15] **Tim:** I like a more positive one. Everyone won the lottery.

[00:00:17] **Adam:** There, there you

[00:00:18] **Carol:** There you go. Thanks, Tim.

[00:00:19] **Tim:** They won the lottery. They, they left and they've, they've moved like a remote location out in

[00:00:23] **Carol:** Costa

[00:00:24] **Tim:** And you can't call them.

[00:00:25] **Tim:** let's not kill these hypotheticals. Their lives matter.

## [00:00:29] Intro

[00:00:48] **Adam:** Okay, here we go. It is show number 126th. And on today's show we are going to talk once again about documentation. Although this time is slightly different angle. We're gonna talk about, not so much documenting like way the ways that the product works for your end users or like manual processes that developers and and support people might need to follow, but more like, design documentation for, revisiting why things are the way they are when you are confused about your product in five years and you're debugging or trying to, remove some technical debt, reoptimize, whatever.

[00:01:22] **Adam:** anyway, we'll get into that in a few minutes. As usual, why don't we start with our tramps and fails carol's back and, and so far no, uh, unscheduled showers.

## [00:01:33] Carol's Failure

[00:01:33] **Carol:** Yeah, guys, I'm gonna kick us off with some failures. Like Adam mentioned last week when we started recording, no sooner than we all get together, water starts dripping out of my ceiling, literally dripping out of my ceiling fan and light. Found out the air conditioner had backed up into the drain pan.

[00:01:52] **Carol:** The whole, like, everything up in the attic was wet. Our hallway has water damage, so that happened. We're getting that fixed this Thursday. The, the air's good, but now we have lots of water damage to fix. and then Sunday, I decided to get my covid booster because I'm going to my son's graduation in three weeks and I'm never around human.

[00:02:09] **Carol:** So I figured I'm the, like, perfect candidate to catch covid group of people if anyone's gonna still catch it. So, that has made my arm feel like it's a brick on my, on my shoulders. It hurts so bad. But then yesterday I decided it'd be a good idea to finish up painting and, you know, kind of cut my finger a little bit and needed some stitches and ended up getting a tetanus shot in the other arm.

[00:02:33] **Carol:** So now I'm walking around with just bricks instead of arms. So I'm giving up. I'm just gonna sleep the rest of this week away.

[00:02:40] **Adam:** Man,

[00:02:41] **Carol:** Yeah, it's not been a good week.

[00:02:44] **Adam:** I'm sorry for your luck.

[00:02:45] **Carol:** Oh yeah. It'll, it'll all wash out. It's good. What about you, Tim? Where are you at? Trams or Fells?

## [00:02:52] Tim's Triumph

[00:02:52] **Tim:** I'm going with the triumph. I'm feeling energized this week. I've been a few weeks of just, just really low motivation, low desire to, and I've I've become aware that I've been procrastinating things, which I don't like to do. my fore follow up flag in my email box has just been growing, growing, growing.

[00:03:09] **Ben:** Oh, I know that story.

[00:03:10] **Tim:** Yeah. You know how I love to be in box zero, but if it's like something I just can't deal with right now, I just kind of flag it and then I, so I got. You know, this week we're recording earlier than we normally do, but so far, the past couple days been really good in knocking everything out, getting things done.

[00:03:26] **Tim:** I, I've been getting more sleep, better sleep, drinking a bit less. I think that's really helped. So getting a little, a little more health conscious, you know, and not eating so much junk food all the time. But it, it does help. It does. Yeah. Something I had to change, so there's that. But also, I noticed that this will come out around May 10th, right?

[00:03:43] **Tim:** So that May 8th would be, my 24th wedding anniversary. So,

[00:03:49] **Adam:** Congrats.

[00:03:50] **Tim:** anniversary, honey. Happy 24 years,

[00:03:54] **Adam:** Wait a minute, Tim, you don't listen to this podcast. Why would your wife listen to it?

[00:03:58] **Tim:** I don't know, maybe to see what I'm up to. Yeah. She doesn't listen to it, but, uh, yeah, so that's, that's exciting. 24 years. And then, so today we got watched, um, The movie Ghosted. It's Chris Evans and Anna de Armas and, Christopher Mackie. And Stan Sebastian. It's an Apple Plus movie. It's kind of like a comedy, romance, spy thriller.

[00:04:24] **Adam:** Hmm.

[00:04:24] **Tim:** But my wife was an extra in it. And scene is like set in, like a, a Pakistani nighttime bazaar. And she told me it was just basically, it was a big parking lot, you know, and they kept walking around pretty much in circles to make it look bigger than it was. And she is in there probably 15, 20 times,

[00:04:45] **Adam:** Wow.

[00:04:46] **Carol:** Nice.

[00:04:47] **Tim:** but she's in full burka.

[00:04:49] **Adam:** Ray, you can't see her. I remember you telling us,

[00:04:51] **Ben:** to tell.

[00:04:52] **Tim:** So she's like, cuz it was her and two other women. And they would walk together, all three of them. And anytime you saw burka, you'd say, oh, that's me. That's me. Oh, that's me, that's me. And so she was excited about that. I was like, yeah, you could tell people that, but it's like, yeah.

[00:05:07] **Adam:** right? Yeah. I'm standing next to you.

[00:05:09] **Tim:** Yeah, that's me walking right behind Chris.

[00:05:12] **Tim:** Chris, Chris Evans.

[00:05:13] **Ben:** Is, is the movie, any good? Cause I, I saw the trailer and the Yeah, the trailer looks awful.

[00:05:18] **Tim:** It's so awful.

[00:05:20] **Carol:** So we shouldn't go watch it.

[00:05:21] **Tim:** I mean, if you want to watch it to laugh at it, it's one of those, it's like, it's so bad. It's hilarious. Just the whole premise of it. You're like, you don't know why this guy is chasing after this girl. And yeah, and just even like, yeah, I don't wanna give, give off.

[00:05:36] **Tim:** If you do wanna watch it, I don't wanna give the premise away, but it's like, it's a comedy of errors of assassins trying to catch this person. So yeah, it's pretty awful. The dialogue's awful.

[00:05:47] **Ben:** We watched the trailer the other day and I was like, oh, that was the woman from Saturday Night Live. I had no idea who Anna De Armas was.

[00:05:54] **Tim:** Oh yeah. Yeah. She was in knives out, the original knives out,

[00:05:59] **Adam:** And she was in, the remake of Blade Runner.

[00:06:03] **Tim:** And she was also Marilyn Monroe in the latest

[00:06:05] **Ben:** Oh, I haven't seen that blonde.

[00:06:08] **Tim:** Blonde. Yeah. So anyway, so those are all great things and so I'm feeling good. So triumph, how about you, Adam?

## [00:06:15] Adam's Triumph

[00:06:15] **Adam:** let's see. I'm gonna go with the triumph as well. mine is, I, I mean, I guess you could say the real triumph here is that we hired a smart person and, we continued to get smart solutions out of them, which is great. You know, I, I don't suppose I can take personal credit for hiring this person.

[00:06:30] **Adam:** I knew him, but, I was not the person that brought him into the company. But I, I'll, I'll talk a little bit of the story of, you know, why, what made me think of that today. so you might have heard, I might have mentioned on the podcast that I haven't been doing a whole lot of coding lately because I'm working on all this compliance stuff and dealing with stale access keys and all that.

[00:06:49] **Adam:** So one of the things that we're doing for this, effort, Is getting closer to the top of, of our game on, you know, secrets management sort of thing. So we are heavy users of one password, which I cannot recommend enough. I love the, the app and all of the features that they have are fantastic. but they also have some additional, sort of enterprise-y features, if you have a business account.

[00:07:15] **Adam:** And those things have been tremendously helpful in this process. They have, sort of two things that are really interesting right now. One is, I know I've talked about on the show before, which is called Connect Server, which allows you to stand up a couple of docker containers inside of your cloud vpc right in, in your, applications environment, which you give it some secrets and then it can just connect to the one password like cloud and, and have access to your secrets.

[00:07:41] **Adam:** You know, you have to choose which vault it has access to and that sort of thing, but using that, you can basically have access to your secrets. At runtime, through effectively arrest api or they have like SDKs so that you can, you know, just make some JavaScript function calls, that sort of thing, if that's what you're looking to do.

[00:08:00] **Adam:** And it's been really nice and I've been using it to do like automated key rotations. So that's the part that we've talked about before. The other part is, it's called service accounts, which is basically, you can kind of think of, it's a, it's new, it's in beta. but it, you can kind of think of it as instead of like a human user, you've just designated like a, not a robot, but you know what I mean, like an a, a computer, account that acts as if it is a user, right?

[00:08:23] **Adam:** It can sort of, you can assign it access to different vaults and it, so it can see those secrets and has all the same permissions as a, a user that would have access to those, vaults and secrets. and, that can be used. For, that's primarily like on the command line, right? So you can say like, I want to fill in this environment variable to start a, a service.

[00:08:47] **Adam:** And the environment, environment variable's a secret that I'm pulling from one password at startup via the command line, which is pretty neat. one of the things that has been kind of difficult about this whole process is you get into like a, who watches the watchman type situation, right? So you've got all of your secrets in, in my case, in one password, and you need a secret to access those secrets.

[00:09:08] **Adam:** So then it's like, okay, well, but then what do I do with this secret? Right? I can't put it in any of my usual places, right? If you're not supposed to have it embedded in the code, you're not supposed to have it in, a config file somewhere. You're not supposed to have it in an environment variable. The environment variable thing kind of took me by surprise, right?

[00:09:23] **Adam:** Like

[00:09:24] **Ben:** Yeah, that one also feels very weird to me.

[00:09:26] **Adam:** Yeah, it seems like that's sort of the industry standard advice. It's like, oh yeah, yeah, you put your secrets in environment variables, which. I think for 90% of people and 90% of solutions, it's probably a fine thing. But, when you start to get into like PCI compliance and all these other, you know, things, it's like, eh, that's not really ideal, I guess, because

[00:09:50] **Ben:** I, I had this conversation at work cuz, because my point of view was if someone has gotten onto your machine to a place where they can start to inspect your environment variables, I'm like, aren't you hosed already? Like, can't they just already do basically whatever they want? And, and the response from the security guy was like, maybe it depends on how everything's set up.

[00:10:11] **Ben:** He's like, it's not that this is gonna stop everything, it's just that it's supposed to make it harder. So it's one of those trade offs where I feel like sometimes you gotta squint really hard to see the value add.

[00:10:22] **Adam:** I mean, I, I see the idea, right? It, it's not a guarantee, but it's like, okay, well we're striving for a goal, right? So if your machine does get honed, like. How do we keep that from, meaning that the whole business is honed, right. So,

[00:10:36] **Ben:** right.

[00:10:38] **Adam:** anyway, so, you know, we, we were kind of thinking about different options.

[00:10:41] **Adam:** There's like AWS Secret Manager, cuz we're on aws, and I had heard of that. So I looked into it and it's, it seems like a fine ish, option. But then this coworker, really smart guy, who happened to be aware of another service that Amazon offers that is actually free for, like, for our use case, right?

[00:10:59] **Adam:** There's a certain, there's a free tier to it basically. and since we only have one secret that we need to store, it's totally free to us. Basically it's called Parameter Store. and effectively like it, it's only used, it's only usable by certain services. So, which is the services that we're using, like, ecs, elastic Container.

[00:11:20] **Adam:** Service. so you configure your containers and you can say, okay, I want you to pull this environment variable out of parameter store as the container is starting up. So when you, like, when you start the container, it's got the name of the environment variable and it says, load it from parameter store and here's the like, key name to pull it out of parameter store.

[00:11:38] **Adam:** And then you also have to execute that container using a role that has access to parameter store, right? So you've got all the, all the authentication configured, but the secrets are all completely hidden, which has been pretty nice. So, yeah, just hire par, hire smart people, get smart solutions.

[00:11:56] **Tim:** a secret management. I mean that, that's a tough one.

[00:11:59] **Adam:** Yeah, maybe, I mean,

[00:12:01] **Carol:** Yeah, that would be a good show,

[00:12:02] **Adam:** yeah, I mean, I think, I think it would end up being a shorter show, but I think that, some of my co-hosts would appreciate that.

[00:12:07] **Carol:** Ben and myself, if you're curious on who those are. Mm-hmm.

[00:12:11] **Tim:** Teach.

[00:12:12] **Carol:** Mm-hmm.

[00:12:13] **Adam:** So, yeah, let's put it on the list. Maybe we'll get to that one. but anyway, so that's me. Hire smart people, get smart solutions. I guess that brings us to Ben.

## [00:12:22] Ben's Triumph

[00:12:22] **Ben:** yo, yo, yo. I, I, I've been feeling a little logy lately. the last couple of episodes I've had some, some failure is just about feeling ma and lost and whatnot. So I'm gonna, I'm gonna try to dig deep here and pull out a triumph. And that's that. as I've mentioned, I've been migrating my blog to use Hotwire, the, Basecamp framework.

[00:12:43] **Ben:** And, I had to refactor a bunch of things, and I had to pull my comment form. So at the bottom of the blog post, there's a comment form where you can leave a comment. I had to pull that out into a separate page. For a while because I was having trouble getting things loading properly. And, my triumph is that I've, I've got everything sort of back to the previous user experience, but now using Hotwire.

[00:13:05] **Ben:** And, there was some stumbling blocks along the way where I wasn't quite sure how I wanted to do some stuff. And, I, I think I finally came up with some solutions that I'm pretty pleased about there. There is some experiential stuff that I feel like, was better previously, but if, if you step back for a second and think abstractly about what Hotwire is trying to do, it's trying to allow you to create advanced interactions with a minimal amount of client side JavaScript.

[00:13:34] **Ben:** So I think as with all things, the pendulum swings a little too hard in the other direction for a while. So I kind of went from fully customized JavaScript to trying to remove all the customized JavaScript. And I think what I really need to do is have something somewhere in the middle where it's like, 80% hot wire and H T D P and then like 20% adding back in some of the, the, that user experience with some additional JavaScript.

[00:13:59] **Ben:** But, you know, just, trying to find my footing there. But I'm, I'm excited that I've, I feel like it's basically done. Like I've basically got the hot wire implementation. I'm pretty happy about that.

[00:14:10] **Adam:** So how much time are you spending working on this, cuz I know it's in your personal website and so it's not something you're working on. Eight. Hours a day,

[00:14:15] **Ben:** No, no, no. it, it's, it's dribs and drabs. It's a couple hours here, a couple hours there. I, I probably spent more time on it than I expected to for sure. Just because it's, it's been a lot of,

[00:14:26] **Adam:** that's the way learning goes.

[00:14:27] **Ben:** yeah. Well, and it's, and it's, it's learning. It's like, it's not just learning the technology, it's learning the way in that, There, you, you know, like with woodwork, right?

[00:14:36] **Ben:** Like, you can work with the grain or you can work against the grain. And the problem is like, I don't quite know where the grain is pointing right now, so I'm doing a lot of cutting only to find out that that's not the way Hotwire wanted me to do the thing, and now I'm refactoring and, and trying to find the right path.

[00:14:52] **Ben:** And, so there's, there's definitely been some trial and error. And then like sometimes

[00:14:56] **Tim:** This is the way.

[00:14:57] **Ben:** yeah, yeah. Sometimes I'll hit something. I'm like, this was clearly not the way, and then I'll spin off a little demo where I can do some experimentation and I'm like, okay, that, that proves or disproves a particular approach.

[00:15:07] **Ben:** And then I go back to the blog and then I start to implement this, the learnings from that previous experiment. So there's been a lot of side quests and, but I'm, I'm pretty excited about it actually.

[00:15:16] **Tim:** Cool.

[00:15:17] **Ben:** Yeah. Yeah.

[00:15:19] **Tim:** Is it speeding up your page? Any or this? Just more for learning a new tech.

[00:15:23] **Ben:** it has zero impact on page load. I think, you know, as I talked about on a previous episode, my CDN is actually slowing down my page delivery. It turns out more than anything else, I guess the, you know, the DDoS protection from CloudFlare ends up adding quite a significant amount of overage. I mean, I gue, I dunno, I guess it depends on where your servers are and everything, but, no, it's so sorry.

[00:15:48] **Ben:** Long story short, it really has had no impact whatsoever on page load.

[00:15:52] **Tim:** Gotcha.

[00:15:53] **Adam:** like what you've learned, you could or would apply at work? And so like, you know, even though you haven't gotten a direct benefit out of it now, it you've, you've kind of added a tool to your tool belt. I.

[00:16:05] **Ben:** Yes, in fact, okay, so, What I really want to do is now take the hot wire learnings and start rolling them into a new application. I, I've, I've dreamt of forever building some sort of a fitness app, which seems completely silly. Granted that there's like a saturation of fitness apps in the market, but, I write all my stuff down in the iPhone notes app, which is like the worst of all solutions for tracking anything.

[00:16:32] **Ben:** So what I really wanna do is create a fitness app and build it using Hotwire. So I think all of the stuff that I've been learning, applying it to my blog, I can now take and apply to, this kind of a more applicationary context.

[00:16:47] **Adam:** So if you wanna throw down the gauntlet like that, I will go ahead and I will make a better, or I'm sorry, a worse fitness application. I'll just take like the Apple Notes application interface and like after every time that you write a line in there, I'll make you watch an Unskipable 32nd ad.

[00:17:05] **Tim:** Genius.

[00:17:07] **Ben:** Good time. Good.

[00:17:08] **Adam:** It can always be worse. Great. Well then, I guess that brings us to our topic for the day. So, basically I guess we wanted to talk about design documents, right? And, and maybe what we each do, what we would like to start doing differently. What, what do we like and dislike about our current processes?

[00:17:26] **Adam:** What could be better sort of thing. So, should I kick it off?

[00:17:29] **Ben:** Kick it off

[00:17:30] **Adam:** Okay, cool.

[00:17:32] **Ben:** just one time. Kick it.

[00:17:34] **Adam:** so, I guess one thing that I don't like about my current process is that we don't have one. we d we just like have a discussion on video chat. you know, with the, the developers that are gonna be involved. sometimes we will have, you know, sometimes we will have a discussion with the customer directly, like the whole team that's gonna be working on it, and kind of write down what we learned from that discussion.

[00:17:58] **Adam:** Sometimes like one person has a discussion with the customer and then brings that back to the team and we go from that and it works. We create products and we are have a, a, a business that's doing fine. So, you know, the, in that sense, you know, it's working for us, but, I heard something on the, what is it?

[00:18:18] **Adam:** Js Party podcast. Recently they were talking about, documenting your decisions so that you can look back on them in the future and, you know, understand why a decision was made. Understand why the code is the way it is. You know, sometimes it seems like there's a more obvious implementation and you're wondering why wasn't it done that way?

[00:18:37] **Adam:** So being able to document that sort of thing sounds like a good idea. and I have lots of thoughts on like ways that could be better and tools and stuff, but I kind of wanna start with like, what do you guys each do?

## [00:18:48] Living Documents

[00:18:48] **Carol:** So to take a step back, whenever we're looking for products to use, so say we're looking to implement something like what we've used in the past is the, I don't know if people say this like as a name, but it's d a c i, which is in Confluence. And basically it comes with the template. And in there you have the ability to lay out who's responsible for what you lay out, who is involved with it.

[00:19:10] **Carol:** and then you have sections at the bottom where you do a pros and cons and a cost. So you lay out everything that you research. So if you're looking for, you know, I remember doing it when we were looking at comprehend. So we were looking for what a good, solution would be for natural language processing.

[00:19:27] **Carol:** So we looked through many options, did our pros and cons, did you know what we thought it or how we thought it would help the company where it had shortfalls at? And then we brought that all back to the table and we made a decision on it. And then, At the very bottom of that document, you have your decision why you made that decision.

[00:19:46] **Carol:** And it's ultimately there for anyone to see. And it's a living document. So if we make changes down the road, you just update with, we've made a new decision, you know, we've made changes and here's why

[00:19:56] **Adam:** I love the idea of living documents for something like this, right? So,

[00:20:00] **Carol:** it has to be otherwise, what's the point of it? Because things change in technology all the all the time.

[00:20:05] **Adam:** yeah, so many things are just capture a point in time and then it gets outdated within like a month, and then you're looking back on it in two years and there's been so many decisions that, changed since then.

[00:20:16] **Adam:** And it's a totally useless document.

[00:20:18] **Ben:** How do you remember Carol, to go back and actually make it living and not just a moment in time.

[00:20:25] **Carol:** I mean, that's our own responsibility. Sometimes it's good when the product owner was involved with it initially because they will be looking at that document to figure out what the decisions were, and then they'll be writing specs to say, Hey. Here's what we, here's where we're having a problem, send that to engineering and say, how do you solve this problem?

[00:20:45] **Carol:** And then we look back at that document. So it's just a responsibility of people using the system and or not using the system, the people writing the system, and the people designing like the request to know to go look and see if there is one. If not, let's start making one.

[00:21:00] **Adam:** I don't know that you can have technology that's like, oh, don't forget, this is a thing that needs to, you need to update your document. But

[00:21:07] **Tim:** We need clippy.

[00:21:08] **Tim:** Hey, I

[00:21:10] **Carol:** I love

[00:21:10] **Tim:** your specifications out out of the original design project. Do you need to update your living document?

[00:21:15] **Ben:** yo, but you joke. But there's almost certainly some team out there who has decided that they're. GitHub poll request template should include a checklist of documents that are supposed to be adjusted after h pr and like that's, that's like the inevitable, worst case scenario of process implementation.

[00:21:35] **Adam:** Yeah, and I mean, I think that is a, a good intention, overdone or something like that, right?

[00:21:42] **Ben:** percent.

[00:21:44] **Adam:** where I was headed was like, okay, so we all try to remember to update the document whenever it's appropriate to do so. We all try to remind each other. So I was thinking like code review would be a good opportunity, right?

[00:21:55] **Adam:** When you're reviewing

[00:21:56] **Adam:** somebody else's code.

[00:21:57] **Ben:** didn't, mean to pre poop on

[00:21:58] **Adam:** No, no, no, no. I, I, no, I I still think there's a huge distinction to make here, right? You, what you said was, every PR has a template, and one of the things in that template is have you, you know, a checkbox, have you updated the documentation for this project or whatever?

[00:22:12] **Adam:** And not, not every PR is gonna do that, especially if it's a Ben Nadel pr where you're like, you know, you're just adding a PR because you added 74 lines of white space. Like

[00:22:23] **Ben:** It's

[00:22:23] **Adam:** that that has no effect on the

[00:22:25] **Ben:** this area has been left blank.

[00:22:28] **Adam:** So just a comment with like 74 blank lines, and then it says, this space intentionally blank, then another 74 white, blank lines. no, so like, I, I think it has to be very manual, but like, you know, you, you get better at it through practice, right? You're gonna screw it up a little bit and, and like everybody involved

[00:22:45] **Adam:** from Yeah, yeah, yeah.

[00:22:47] **Adam:** Everybody involved from the developer to the code reviewers. And then like, if you have, like, if you're the. Fortunate type that has like product managers and you have like project managers, like everybody involved can be like, okay, well this seems important. Did we update the, the document about this?

[00:23:03] **Ben:** I, I just, can I jump in for a second? Because I feel now bad about how strong I came out against pull, pull request templates, and, and I wanna be transparent that that, jagged response there is the result of having something like that at work. We used to have what we called the, the, change, I think it was like the change request board, C P D or, or something

[00:23:25] **Ben:** like that. It was like a group of people that were designated as, like, they're, they're the ones that have to look at all the prs and they decided about this, this template that would be in the poll request. And it got to the point where people would open up a poll request, just delete the entirety of the content that was prepopulated, and then fill out their own pr.

[00:23:45] **Ben:** And to this day, this was like five years ago, and to this day, people will still bring it up. They'll be like, dude, don't rock the boat, or else they're gonna implement another change request board. Again, we don't want that to happen. So I feel like I'm still the, you know, the, the pain of that has echoed through the years.

[00:24:03] **Ben:** I, you know, I brought, brought some of that to the conversation, so I apologize.

[00:24:07] **Tim:** It's

[00:24:07] **Adam:** No, no, no. Don't apologize cuz it's accurate. It's true. And it's a valid opinion. Like, and, and I agree with it. Like, you know, I think that, you know, helping each other get there is, is good. And I don't think that necessarily saying, like having a checkbox on there that says, if appropriate, did you update the, the document for this project for any, you know, changes, design changes that were.

[00:24:32] **Adam:** Decided on or whatever, right? Like, it, it costs you one or two seconds to look at that and go, okay, yeah, no, there were no, there's nothing to document and check the box. Right? And then it, it helps you remember if that is appropriate. I think where people get that negative taste in their mouth is like when all of a sudden you have 150 of those check boxes for every poll request.

[00:24:49] **Adam:** That's, that's ridiculous.

[00:24:51] **Carol:** Yeah, cuz you know, you're just saying yes to everything at that point. Not looking at any of it.

[00:24:56] **Ben:** Yeah.

[00:24:56] **Tim:** and, and very, I mean, once you start going down a path, not everything's a design change, right? We're talking about like a major. Major issue, right? So to have that check there every single time for the very small percentage of times where someone who just doesn't know why someone was designed that way, decides to redesign something cuz they don't understand the six system.

[00:25:16] **Tim:** I, I mean, I don't know if that's necessarily the best way to catch it. I, I'll tell you what, what we do is we will do, we don't use Confluence or anything like that. We, you know, pretty small team. We just use, we'll create a research ticket. So we have this new thing, we're trying to design it. We create a research ticket, research ticket, says, states the problem and then says, you know, what?

[00:25:38] **Tim:** We researched to say what would solve the problem we think would solve the problem. What things were, looked at, what things were thrown out and why, what was chosen and the reasons why. And, you know, how we believe that in the future it will benefit us. And here's, and maybe some of the things that we know might be challenges to overcome due to whatever.

[00:25:59] **Tim:** Solution we decide upon, but I don't think we ever go back and update it.

[00:26:04] **Ben:** I I also think that part of the problem with the documentation that we have in a lot of places in terms of remembering to go back and update it, is that it's so distributed in so many places.

[00:26:16] **Adam:** Mm-hmm.

## [00:26:17] Documentation in One Place

[00:26:17] **Ben:** I, I have tried to pitch this at work several times and literally everyone thinks that I'm crazy, but I think at least on the, at the team level, maybe I don't, I don't know how, what the Blast Radius is here, but I feel like a team should have one document that they control and that's it.

[00:26:35] **Ben:** Like, no, no, like here's the Read me and then the Read Me links to the contributing doc and then the contributing doc links to the Getting It Running Locally Doc, which links to the e d e tests recommendations Doc, like I think you should have one doc. I can pull it up and I can do a command F and be like, look for Docker compose, or look for e t E or look for, flow diagrams or something.

[00:26:57] **Ben:** I at least if it was all in one place, you get that constant, one pressure to be like, is this worth adding to make this document even longer than it already is? But then also a reminder that all that information actually exists and is it maybe need to be cleaned up or is it something I should be updating?

[00:27:16] **Ben:** But again, everyone thinks I'm nuts. No one, no one likes that idea except me.

[00:27:20] **Carol:** A large, a large document, like that's very intimidating to me, though. I would get lost in it and my a d D would kick in and I would find nothing, and I would ultimately close it, go figure it out myself, and it would take a lot longer.

[00:27:33] **Ben:** I, I don't disagree with that out as well. I can't push back hard.

[00:27:38] **Adam:** so I'm just trying to understand, are you saying one document for everything that the entire team works on, or like one document per like project? Per per

[00:27:47] **Ben:** Well, that's what I'm saying is I, I don't quite understand where the radius is, but I, I just, I just know that people, I think, get obsessed with creating new documents because maybe it's so easy and they can be done in isolation, so it doesn't feel like it has a lot of weight to it. But documentation, I think, has a, you know, to the point of this conversation, it gets out of date very easily and very quickly.

[00:28:12] **Ben:** And if it were harder to create good documentation, maybe people would be better about keeping it up to date.

[00:28:20] **Adam:** Yeah, I think that's a really interesting point about it being really easy to create a new document in whatever random system you feel like creating a document in, right? Like you can just go to, what is it? docs.new, right? Boom. You're already open in a brand new Google doc, right? versus, okay, I have to go find the right database page in notion to add a document to, for the, for this project or for, you know, whatever it is that I need to document or, or whatever tool, right?

[00:28:48] **Adam:** If, if it's, if it's in a get repo, like how do I know where it belongs inside that repo? Yeah. I,

[00:28:56] **Ben:** Like I like,

[00:28:58] **Adam:** for it to, to be useful, you have to just agree as a team that, like, even if it's not a perfect solution, having a single place where this type of document lives, is itself of high value, right? So we're, we just agree we're not gonna have markdown files in GitHub and Notion and Confluence and a, you know,

[00:29:21] **Carol:** Too many places.

[00:29:22] **Adam:** Yeah, yeah, yeah.

[00:29:23] **Adam:** All the things and a Trello board and all this. Like, just pick one, whatever it's gonna be, whatever you can get people to agree to, like pick one thing and that's gonna be the thing. And yeah, there's gonna be friction and there's gonna be people that don't like it. And there's gonna be, like, it would be easier if, but the value of like having it all in one place means you only have to go to one place to, to search.

[00:29:44] **Adam:** I agree with that.

[00:29:44] **Adam:** that that's huge. Yeah.

[00:29:46] **Carol:** And I like the idea of using compliments or doc or you know, wherever else you wanna put it. That's not technical, because then that doesn't limit you to who can add and contribute to it. Because our product owners and product managers don't wanna be learning markup to go write files that need to be checked into code somehow or stored somewhere.

[00:30:06] **Carol:** They just need to be able to go into the system where they're working, which is Jira, usually open a page, create a new document and attach to it either you know, an epic or a story or a bug, something that just links together easy for them.

[00:30:20] **Adam:** Yeah. Now, so I wanna say this as somebody who has never, I've touched Jira a little bit, but other than that, I've never really dove into the, like, whole Jira ecosystem, the Atlassian ecosystem. Never seen Confluence that I know of, you know, any of that, but, I think that if you can make it work, like if the people using it are technical enough, I see a huge amount of value in using markdown files in the get repo.

[00:30:48] **Adam:** I think I would want that get repo to be separate from the product itself. Right. You don't wanna have to

[00:30:52] **Carol:** I think it has to be. Yeah.

[00:30:54] **Adam:** all, all those documents to be included when you're like

[00:30:56] **Carol:** I would be annoyed looking at the code. Yeah. Yeah. I would be so annoyed opening those folders. I'd be like, no, there's extra.

[00:31:02] **Adam:** and, and here's the sort of the killer feature reason why I think it should be marked down in a, a get repo and that is get blame, right?

[00:31:10] **Adam:** So if this is a living document and things are changing over time, you wanna be able to look and see when was this updated? By whom, what did they change? Show me a diff of what changed. And I feel like that would be huge.

## [00:31:26] Confluence

[00:31:26] **Carol:** Yeah, confluence has that with the documents. So you see versions and whenever you create a new version of it, you add a comment so people can see like why you'd make the change If you put a comment, obviously. and then you can actually open up a compare of the two versions.

[00:31:42] **Ben:** I did not know that,

[00:31:43] **Ben:** and we used Confluence. I

[00:31:44] **Adam:** That sounds useful.

[00:31:46] **Carol:** It shows the versioning. I think it's up in the right hand corner. You just do the little drop down that says, show the previous versions.

[00:31:52] **Ben:** my, the one thing that I dislike about Confluence, which I think is ironically. The reason that a lot of people like it is all the embedded widgetry. Like I just want an editable document. I I, I get very confused when you go to edit a document and it has all kinds of linked tables of contents and other data grids and flow diagrams all embedded, but they're actually different widgets and you gotta go into other places to edit them.

[00:32:20] **Ben:** Or like, you can include documents or sections from other documents. I mean, it's pretty amazing that it can do all that. But at the end of the day, like I just want a document that I can edit.

[00:32:30] **Tim:** Just a simple man with simple needs.

[00:32:33] **Ben:** I'm just a

[00:32:33] **Ben:** click and a pointing kind of guy.

[00:32:36] **Carol:** what the Scrum masters can do is, has always been amazing to me. Like they put down our, put the burn down charts in there, put velocity on it. I'm like, where'd you get this data from? They're like, oh, you just hit like, Open bracket, the date, a sprint thing, close it and it just populates it.

[00:32:52] **Carol:** And I was like, here, I'm thinking you're doing this crazy fancy stuff and it's just a tag. I'm like, okay. This is why everybody does love it, because those widget trees and magic little things are pretty easy to just pop in and make a document look very sophisticated.

## [00:33:09] Agile

[00:33:09] **Adam:** Quick, quick tangent. The three of you, do you have strong opinions on whether Agile is good, bad, or otherwise?

[00:33:18] **Carol:** I, I would say, I,

[00:33:20] **Tim:** a quick tangent.

[00:33:21] **Carol:** yeah, it's not, it's definitely not gonna be a quick one. The short answer would be it depends on the need and how the team works and it works successfully as agile sometimes. And then other times it needs to say like a combat style where we just go with what's thrown at us. It just depends on what your product does and how your team works.

[00:33:41] **Ben:** I was actually just talking to the CTO about it today and my take on it was the individual contributors don't care at all. Like they just work tickets. They don't care about sprints, they don't care about when one sprint ends and one sprint starts, and what the burn down was like.

[00:33:58] **Ben:** That only matters to managers. So it, to me it feels like it's up to managers to figure out whether or not they need to impose more structure in order to communicate upward within the organization. Cuz to me, as a, as more of an individual contributor, you're like, you wanna close out the sprint? Yeah, sure.

[00:34:17] **Ben:** I'm just gonna keep working on my tickets. Like I, that doesn't mean anything to me.

[00:34:20] **Adam:** Hmm.

[00:34:22] **Tim:** I mean, I think Agile's promise was to, to have managers, managers be able to give a somewhat accurate answer to the question, how long is it gonna take and what are we gonna get? but I don't think it in the end works out that way. It's like people put stuff in buckets or t-shirt sizes or estimations, and they're always wrong, that they're never correct.

[00:34:46] **Tim:** but I think that's more important whenever you have maybe to answer to a customer or you know, another party that's maybe paying for all the, the hours they're trying to figure out how much it's gonna cost them, which is, you know, obviously a good question to ask. But, you know, our form of business, we don't answer to a co We're building a product.

[00:35:04] **Tim:** We're just trying to get a product done in a way that makes sense. And it's like, all right, what do we work, what are the things we need to work on now in the next whatever timeframe to be able to get something out the door that people can see. And to be honest, it's like if, if you missed the timeframe, you missed the timeframe.

[00:35:25] **Tim:** You're not, I'm not gonna, we're not gonna ship broken stuff. Right.

[00:35:30] **Adam:** Yeah,

[00:35:30] **Tim:** So it gives you, it gives you some idea, but it's, I, yeah, I, I've heard the term agile waterfall.

[00:35:38] **Adam:** Mm-hmm. Yeah, yeah, yeah. It's agile until you like squint really closely or something, and then it's just like waterfall behind stuff. Yeah.

[00:35:44] **Tim:** So

[00:35:45] **Tim:** I'm, I don't, I, I, I get the idea, but I don't think the execution of it, I don't really know any people that do it well.

[00:35:54] **Adam:** thank you for entertaining my question. I, I, I, that was kind of the exact answers I expected, right? So I feel often very gullible because I read something and I just tend to like, like it, you know, I read, I read the, the at a LAN manifesto. I read the scrum guide, and I read, a book in O'Reilly book called Learning Agile.

[00:36:12] **Adam:** And it, it made sense to me. it sounded very interesting, potentially useful. It sounded like a lot of meetings, but, you know, if you got a hundred percent buy-in from all of the people, then maybe it could work. But it, I I, the, the impression that I get, whenever I hear about anybody talking about Agile tends to be, it's dumb.

[00:36:35] **Adam:** It's a waste of time. And, and I guess I'm only talking about developers, right? I'm not, I'm not going around interviewing upper management about whether Agile works for them. I'm talking to developers and it's just so bizarre to me that like, there seems to be such a dichotomy. There's people that are on the agile bandwagon, and then if you're not a hundred percent there than you are at least like 75% off, right?

[00:37:00] **Adam:** Like there's no, it, it's such a, there's such a void between Okay. tension over, I guess.

[00:37:06] **Tim:** In tangent, close bracket.

[00:37:09] **Adam:** So, do any of you guys do like an RFC type thing where you like, kind of make a, a tentative plan and get input from other people? Or

[00:37:18] **Carol:** What does RFC stand for?

[00:37:20] **Adam:** request for comments?

[00:37:22] **Carol:** Yeah.

[00:37:22] **Ben:** I think that's basically what the dci, the D A C I, that's how we use DCI's at work as the request for feedback.

[00:37:30] **Carol:** Yeah.

[00:37:31] **Adam:** And and does that get updated once the project has started?

[00:37:36] **Ben:** We don't, no, for us DCI are, are just documenting the decision at the time. No one goes back and updates 'em as far as I know.

[00:37:45] **Adam:** Okay.

[00:37:46] **Ben:** But Carol said that she goes back and updates hers.

[00:37:49] **Carol:** Yeah.

[00:37:50] **Tim:** Yeah, same, same for us. We, we basically put out the, you know, here's a new product we're trying to build, or an addition to an existing product. Here's the decisions we made. We put it in a research ticket. And then it's really just there for historical purpose purposes to say, when people ask, you know, well, why did we, didn't choose X, you know, technology over this technology or use this product and say, you know, so this, and we go, well, it wasn't on the list of things we looked at, oh, let me look at the date.

[00:38:18] **Tim:** Yeah, it didn't exist then. So yeah, we were working with what we had.

## [00:38:23] The Ideal Design Documentation

[00:38:23] **Adam:** So, what keeps going through my head is like, what happens if, you know, you're on your way to your team, you know, offsite, retreat sort of situation and the plane goes down and so now your entire team is dead and you know, so they have to hire a bunch of people to come in and work after you.

[00:38:40] **Adam:** And now these people have

[00:38:41] **Tim:** I like a more positive one. Everyone won the lottery.

[00:38:43] **Adam:** There, there you

[00:38:44] **Carol:** There you go. Thanks, Tim.

[00:38:45] **Tim:** They won the lottery. They, they left and they've, they've moved like a remote location out in

[00:38:50] **Carol:** Costa

[00:38:50] **Tim:** And you can't call them.

[00:38:51] **Adam:** yeah, there's no,

[00:38:52] **Tim:** you can't. there's they're living off the grid.

[00:38:55] **Adam:** Sure. If that makes you feel better than going down on a

[00:38:59] **Adam:** 7 37 max.

[00:39:01] **Tim:** let's not kill these hypotheticals. Their lives matter.

[00:39:05] **Adam:** You're killing my hypothetical. yeah. Anyway, so, but you know, imagine a situation where a bunch of people have to come in and figure out, the history. Of a product. Right? Here's the thing, it's currently working for us. We just need some changes. But, you know, you, you're coming into this situation, you have to figure out, well, is it safe to change this?

[00:39:25] **Adam:** Can I, can I do this? Or is this is pulling, this is removing this wall gonna make the whole house fall down? Right? And from what you guys are describing, it sounds like you would have to go back and find a whole bunch of these decision documents to see like, okay, these are all the documents that, reflect the decisions for this particular part of the application.

[00:39:46] **Adam:** And you have to kind of read them in chronological order to figure it out versus if you had like one

[00:39:50] **Tim:** Or you could do a search on the tickets and Jira.

[00:39:53] **Carol:** Mm-hmm.

[00:39:53] **Adam:** But still you're, you're, you're having to find all of, all of them and go through them, like in, in chronological order. Once you, okay, you, you said these seven documents apply to the, the event registration module. Right. Whatever it's gonna be. and you have to go, okay, well, I could start at the end and kind of work my way backwards and see like, you know, what's, what's new each time.

[00:40:15] **Adam:** And I can kind of skip the stuff I already know about. Cuz that tells me, you know, I can only keep what's most recent. Or you can start at the beginning and say, okay, this is how it started and this is what changed and this is what changed and this was what changed. I mean, look, I'm not saying I have a, a, a perfect solution.

[00:40:29] **Adam:** I just think that there's a reason to consider a a single. So, I mean, lemme put it this way. If, if you joined a team and they said, here is a set of documents that describe our entire application and it's broken down logically by like sections of the application, different modules, different features, whatever.

[00:40:47] **Adam:** And each page described one feature or module or whatever, like some reasonable, blast radius of logic there. And it represents the current state of the application. And it's been perfectly kept up to date. And, Not only does it represent the current state of the application, but it, it has held onto all of the history of like how we got here and why.

[00:41:09] **Adam:** Right. We started with this implementation and it turned out that that wasn't performing enough, so now we're doing this instead. Right. That's gonna keep you from going back to the first implementation because you think it might be better because now you have direct evidence that it's not better. So if you could get to that world, would you not choose it?

[00:41:27] **Tim:** Sure sounds like a fairytale, but yeah.

[00:41:31] **Ben:** Well, and it would also be nice that there would be one place in theory that you could subscribe for like a weekly digest of everything that's changed in the system instead of having to

[00:41:40] **Carol:** Like a change Long.

[00:41:41] **Ben:** know, 74 different documents and like them so that you get updates.

[00:41:45] **Tim:** But that, that's only gonna give you the stuff during the period of time that you're subscribed to it. Right? So if it's, it was prior history,

[00:41:54] **Adam:** You're getting notifications about those updates. Yeah.

[00:41:56] **Tim:** Yeah.

[00:41:57] **Adam:** But if the document itself has a. All the relevant history and only the things that don't matter anymore have been removed.

[00:42:06] **Adam:** And

[00:42:06] **Tim:** how does one, how does one get to the Promised Land, Adam?

[00:42:11] **Adam:** um, you have to, first, you have to, like the Beatles, you have to wear sunglasses.

[00:42:15] **Ben:** No. Oh.

[00:42:17] **Adam:** Yeah. I don't know. I mean, I wish I had a silver bullet here, right? Like, I think that that is the reason it's the promised land is because nobody's figured out how to get there.

[00:42:28] **Carol:** Because we're all humans, and at some point, most of us are very lazy with what we're doing, where we're in a rush and we just get it done and move on.

[00:42:36] **Adam:** I

[00:42:36] **Adam:** think that's it.

[00:42:37] **Tim:** here's my nightmare scenario. You, you create this beautiful land of storytelling documentation about, about, about your documentation land. And then they don't even bother to read it.

[00:42:49] **Carol:** No, they

[00:42:49] **Tim:** They're like, oh, this, oh this. Oh, this is, that's too long. Can't, can't be bothered. I'm just gonna rip this out.

[00:42:55] **Tim:** I'm gonna rip this out and go back to this really cool solution I found, which turns out to be the one you left two years ago, cuz it wasn't performant. And yeah.

[00:43:03] **Adam:** We're just gonna

[00:43:04] **Adam:** rewrite

[00:43:04] **Adam:** it. Alan's

[00:43:05] **Tim:** now now what did, what did all that fairytale world building do for you?

[00:43:10] **Ben:** Well, I think we walk a, we walk a fine line because, when we believe that documentation is really important, I almost feel like we often err on the side of creating too much documentation and then it becomes overwhelming and burdensome. I, I think we would be healthier to vastly reduce the amount of stuff that we actually put in the documentation, like things that are actually meaningful.

[00:43:37] **Ben:** Not every decision has to be documented unless the decision can't be reversed in the future. Like you were saying, we moved away from something for performance reasons. That's probably something that we should document, but if we, you know, chose X, y, Z framework just because like that's what we knew and that's what's felt good, like, does that need to be documented?

[00:44:00] **Ben:** Because if we change our mind later, there's, you know, there's no contraindication that that change is, is inherently bad just because we're changing.

[00:44:09] **Adam:** I think it's, it might be worth minimal documentation for things like that. Right? So you say we chose spelt because we felt it had the best developer experience. Right? And then in 10 years, if you go, well, we feel like spelt is, man, I really, I dug myself into a hole here. Cause I don't wanna have to say something negative about spelt, but, uh, if we, if in 10 years we decide like, oh, this, all this crappy code that we wrote and felt, is, is holding us back, like, you know, you'll,

[00:44:37] **Tim:** we need to write, we need to write it in thick with two Cs.

[00:44:41] **Adam:** just two.

[00:44:42] **Tim:** Yeah. It's not, it's not spelled, it's thick.

[00:44:45] **Adam:** yeah, like it's almost like documenting your assumptions, right? So that if, if the world changes, right? If the application is fine or not, not fine. Like if the application. Starts suffering, right? And then all of a sudden, and you look at your document and it says, okay, well we're assuming we're gonna be running on aws.

[00:45:03] **Adam:** We're assuming that, you know, spot instances are, seemingly always available and, and at fair price or whatever, right? Like, then, and then, you know, your application starts, crashing. What was the thing you were talking about, Ben? Like, you know, and, and you couldn't

[00:45:17] **Ben:** out of spot instances.

[00:45:19] **Adam:** Yeah. And, and you're like, you go, okay, well now what?

[00:45:23] **Adam:** Right? So you can look back at that document and say, okay, well these assumptions are just no longer true. So we have to sort of reframe the thinking about this application based on the world we currently find ourselves in, not the world that we were in when we originally wrote it. So I think that some minimal, you know, baseline documentation has some value.

[00:45:44] **Adam:** I agree. We don't have to say like, look, we chose this shade of blue for the buttons because we feel like it, it has a 7% happiness boost over this shade of blue. We're like, that's We don't need that.

[00:45:55] **Tim:** Yeah. Is that really a design change? If you change that color blue, I mean it's

[00:46:00] **Adam:** Only if you're working at like Google or Facebook where like changing the shade of blue by like one saturation point could mean a million dollar difference on your conversions, right? Like

[00:46:11] **Ben:** Well, was this, I can't remember if this was talked about in the, in our Discord or if this was somebody, something that somebody at work shared, but someone posted a screenshot of some CSS variables that were called. It was like hot pink and like hot pink lighter, but all the colors were actually blue because at some point the brand had changed from pink to blue, but no one wanted to go and change all the variable names.

[00:46:33] **Carol:** You gotta love that.

[00:46:35] **Adam:** that's why you don't name your variables after what the, what's in them. You name them after what they're going to be used for. This is the brand color. This is the primary action color.

[00:46:45] **Ben:** Yeah. Well, still learning. Still learning.

[00:46:48] **Adam:** I, I don't recall seeing that in our Discord, although it does sound vaguely familiar. So maybe it was like posted in our Discord six months ago or something.

[00:46:56] **Ben:** maybe,

[00:46:57] **Adam:** I don't know.

[00:46:57] **Ben:** Yo, one thing I will say is, I'll say this on Twitter sometimes, or Facebook, where someone will, will preface their tweet with a lazy, like, I'm just being lazy here, guys. And then say, you know, like, Hey, what's a good 57 inch television with 4k? I don't know what TVs do. You know what I'm saying?

[00:47:16] **Ben:** And they're like, they're they're, they're admitting like, I could have Googled this, but I'd rather just ask so that someone informed can give me a better, better piece of information.

[00:47:26] **Tim:** and then I just Google it and tell them what my first result is.

## [00:47:29] Lazy Documentation

[00:47:29] **Ben:** I almost feel like documentation falls into that trap a little bit. Like yeah, I could spend a lot of time poking through all the Confluence docs or can I just go into the Lazy Docs Slack channel and be like, Hey, does anyone know why we're using MySQL eight over here, but MySQL five seven over here.

[00:47:48] **Ben:** Like is there a reason for that? And then hopefully someone who was part of that decision actually still works at the company and can

[00:47:54] **Carol:** And knows. Yeah. Yeah.

[00:47:56] **Ben:** it actually makes me wanna create a lazy doc Slack channel. Cause I do think that would be really helpful.

[00:48:01] **Carol:** I think it

[00:48:02] **Carol:** would

[00:48:02] **Ben:** have to get everyone to join it and that'd be a problem.

[00:48:04] **Carol:** make it public. Just slowly start sharing it with people.

[00:48:08] **Ben:** Just invite everybody so they have no choice.

[00:48:13] **Adam:** I think when you, create a new channel in Discord, everybody that has like access to, if you make it like a public channel or whatever, it, the whole, everybody's there by default.

[00:48:23] **Ben:** Oh, I didn't know that.

[00:48:24] **Adam:** I know this because I recently created our book club channel on our Discord server, and I

[00:48:28] **Carol:** I saw

[00:48:29] **Adam:** was by default there, so that

[00:48:31] **Carol:** I saw, haven't read it yet, but I will read your post.

[00:48:36] **Adam:** okay. Yeah, no, it's not a big deal. So, Sounds like we're basically done here.

## [00:48:41] Closing Thoughts

[00:48:41] **Adam:** Anybody else have any final closing thoughts on design docs?

[00:48:46] **Ben:** I'll, I'll add one closing thought, which is that just because something is documented doesn't mean it is still the, the way that something has to be done, meaning that the documentation is just that it's documentation, but it's not a final decision.

[00:49:03] **Adam:**

[00:49:03] **Ben:** if you see something in your infrastructure, your application, and you don't think it's optimal and you want to change it, just because the documentation tells you why they chose it, if that's not, in opposition to why you want to change it, I don't think people should feel pressure to somehow adhere to what the documentation said.

[00:49:22] **Ben:** Like, it shouldn't be A yeah.

[00:49:24] **Adam:** Like the documentation exists to explain why they are the way they are. Not to say you can't change it,

[00:49:31] **Adam:** right? It's, it's adding context for future decisions. So that's its whole job.

[00:49:35] **Tim:** I'll, I'll say my, my final take. I, I'll point out a glaring hole, a negative to this entire thing of documenting how the decision was made. It takes away a long time, either time-honored tradition of when someone in management says, why did we even do this in the first place?

[00:49:56] **Tim:** Why was it done this way? This is obviously stupid, and because you have it written down, you can't do what we all do now and say, well, Jeff, who left two years ago, that was his decision. And that's that, that's, that's a dangerous precedent. I don't know if we can, I don't know if we can sub that.

[00:50:15] **Carol:** Funny.

[00:50:16] **Adam:** Okay, well then. I guess, let me say this before we, before we close out the show, we actually happen to know what's gonna happen next week on the show. We have it already decided and picked out and, and lined up.

[00:50:28] **Tim:** am I on the right podcast?

[00:50:31] **Adam:** so, next week on the show we are gonna have a guest, we're gonna have Sean Corfield on to talk about, how tech interviewing is broken.

[00:50:39] **Adam:** That's something that he is pretty fond of saying recently. and he's a, he's the type of person to have strong opinions,

[00:50:46] **Tim:** Strongly held.

[00:50:47] **Adam:** eh, you know, whatever strongly

[00:50:48] **Adam:** held, weekly held whatever. He, he's been in tech a long, long time.

[00:50:52] **Tim:** Yes, he has.

[00:50:52] **Adam:** so, yeah, look forward to that next week.

## [00:50:55] Patreon

[00:50:55] **Adam:** but I guess this is the part where I say this episode of Working Code was brought to you by 0 4 9 2 C two Cian Blue, which is clearly better than six three C five D a sky blue, according to Jeff at least. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:51:23] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. We are gonna go record the after show. oh, you know what, I forgot to say. we have a new patron this week,

[00:51:35] **Carol:** yeah, yeah.

[00:51:36] **Carol:** yeah.

[00:51:36] **Adam:** oddly enough,somewhat of a coincidence, I guess you could say. our new patron is Sean Corfield.

[00:51:41] **Carol:** Awesome.

[00:51:42] **Adam:** Uh,so Sean, welcome

[00:51:44] **Tim:** he wanted, he wanted to hear that Sweet, sweet after show.

[00:51:49] **Adam:** So I, I guess Sean doesn't listen to a whole lot of podcasts, or any because, he, he doesn't like consuming media, audioly. By audio. Right? and then he prefers to read and he found out, or he figured out how to listen to podcast by like having the dictation app on his computer. Like print it on the screen so he can like watch sort of a live transcription

[00:52:09] **Carol:** so cool.

[00:52:10] **Adam:** So he's been reading

[00:52:11] **Tim:** That's cool. But he, he misses when we break Ben

[00:52:15] **Tim:** and he laughs for like a minute and a half. How, how they transcribe that.

[00:52:20] **Adam:** I would love to see it. Sean, send us a screenshot when you get there. Anyway, so we're gonna go record our after show and that is something that our patrons get. and if you would like to get that, then you can go to patreon.com/WorkingCodePod.

## [00:52:35] Thanks For Listening!

[00:52:35] **Adam:** Your homework this week is to join our Discord. Right? So we've talked briefly about the book club. We talked a little bit more about it last week.

[00:52:42] **Adam:** It's coming up. We picked our book. We've kind of picked a general format that we're gonna have these discussions. We're still ironing out the, day of week and time of day that we will be getting together to discuss the, the current chapters with our listeners in Discord. But if you wanna be part of those discussions, you're gonna have to join our Discord.

[00:53:00] **Adam:** So you can do that by going to workingcode.dev/discord. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:53:08] **Tim:** Remember, guys, gals, your hearts matter, except you. Jeff, why did you choose to stick with VB script for decades? Curse you, Jeff. Glad you're gone.
