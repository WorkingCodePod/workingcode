---
title: "035: Being a Swamp Guide"
description: 'Software is never "done". And, as it continues to evolve over time, it often gathers a lot of accidental and essential complexity. This makes it harder to on-board new engineers into a legacy application (and a legacy organization). Enter swamp guides: the aged and battle-hardened staff who know where all the bodies are buried.'
date: 2021-08-11
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/035-being-a-swamp-guide/id1544142288?i=1000531698395"></iframe>

Software is never "done". And, as it continues to evolve over time, it often gathers a lot of _accidental_ and _essential_ complexity. This makes it harder to on-board new engineers into a legacy application (and a legacy organization). Enter **swamp guides**: the aged and battle-hardened staff who know where all the bodies are buried. These guides can hand-hold new team-members as they walk fresh-eyes through the fog of war, helping them to understand where everything lives and how everything works. And, hopefully, leave the swamp a little cleaner than they found it.

## Notes &amp; Links

-  [Stack Overflow for Teams](https://stackoverflow.com/teams)
-  [Big Ball of Mud](https://en.wikipedia.org/wiki/Big_ball_of_mud)
-  [Hanlon's razor](https://en.wikipedia.org/wiki/Hanlon%27s_razor): "never attribute to malice that which is adequately explained by stupidity."

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/035-being-a-swamp-guide.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I'm fairly introverted. And just being with people, even people I like is exhausting. So the idea of onboarding people, which is a very Valiant and wonderful thing to do, it's still exhausting.

[00:00:12] **Ben:** for me personally, I can't speak for everyone, but it's exhausting for me. And it's like, even I get that slack message where they're like, Hey, can I, can we screen share for a minute? I'm a little confused. And I have to like center myself. I'm like, you can do this. It's okay.

[00:00:25] **Carol:** so

[00:00:26] **Adam:** I have to do when my kids are bugging me.

[00:00:28] **Carol:** it's the same thing, exact same thing.

## [00:00:47] Intro

[00:00:47] **Adam:** here we go. It is show number 35 and on today's show, we are going to talk about being a responsible swamp guide, and I guess what that entails and what that means. but as usual, we're going to start with our triumphs and fails. And Tim, you get to go first. What do you got?

## [00:01:02] Tim's Triumph and Fail

[00:01:02] **Tim:** Yay. I get to go first. Okay. mine's kind of, I guess it's it balances out a positive and a negative. Can I do a triumph, the NFL? Is that okay?

[00:01:11] **Adam:** Sure.

[00:01:12] **Tim:** Sure. Okay. Well, my triumph is I'm having to refactor a project that I had worked on for a good long time, but the triumph is the fact that the way I wrote it, unlike me, normally, I was smart enough to.

[00:01:26] **Tim:** It extract out the portion, the serve things into services that are easy to extend, excuse me. And, particularly this thing is, it's basically it's generating XML, but I have to generate XML on it a different way for a different service. and, but fortunately I have built a service that abstracts out building that XML.

[00:01:45] **Tim:** so it should be pretty simple, straightforward. We'll see. We'll let you know later it might be my fail later and yeah, exactly. That should be easy, famous last words. But the fail is the whole fact that I have to do this at all is because I really didn't do my due diligence. I picked a vendor, based off their API.

[00:02:05] **Tim:** I really liked their API and this, all the stuff they said about security and all the things that they said that they did. I'm like, okay, cool. That checks all the regulatory stuff we have to. And then when our audit came up this year, I asked for some documentation and some signatures on that and they just flat out said no. So

[00:02:27] **Carol:** The vendor said,

[00:02:28] **Tim:** the vendors said, no, we don't supply that. And I'm like, well, your website says, you have all these compliances. And they said, yeah, we do all that. But yeah, we don't hand out our,attestation of compliance, like, well then

[00:02:39] **Carol:** trust us.

[00:02:40] **Tim:** Yeah. Just trust us. we do

[00:02:41] **Carol:** We're there.

[00:02:42] **Tim:** Yeah. So

[00:02:43] **Ben:** the old security.

[00:02:45] **Tim:** got all, and this is not a small company.

[00:02:47] **Tim:** I got all the way up to this. I don't want to name them. So I got all the way up to their CEO and he basically just said, yeah, we're, we're not going to do that for you. Like, okay. So I went to their, one of their biggest competitors and I said, Hey, can you supply me this document? And I don't even have a relationship with them yet.

[00:03:00] **Tim:** They're like, they immediately emailed it to me. I, here it is. I'm like, okay, so now I have to refactor this one. Company's XML into someone else's ex. But like I said, I wrote that abstracted, that part out. So all the other business rules that are involved don't come in. So I'm glad I'm glad I applied a bit of clean code polymorphism on this so that,

[00:03:21] **Adam:** He did a really clean job of shooting yourself in the foot.

[00:03:23] **Tim:** I did. Yeah, I did. Yeah. Yeah. So, yeah, so that, that's, that's why I was asking earlier, if you guys have to deal regulations. Cause I, I broke my own rules. I really should've done a little bit more due diligence and have more people involved looking at it. I just like, oh, this is an awesome API. Like it and chose it.

[00:03:39] **Tim:** And then it shot me in the foot later.

[00:03:41] **Ben:** But that's crazy. I mean, we have people who send us these massive security questionnaires, and we return all kinds of information based on what their needs are. I mean, when you provide a service and people have to depend on that service, I think it's completely reasonable that you should be able to answer questions and provide documentation about stuff.

[00:04:02] **Tim:** Yeah. They just pointed to their website and said, say, it says we do all this. I'm like, yeah, but it doesn't say you take responsibility for it. That's true. Okay. Well, I will be going to your competitor. Bye.

[00:04:13] **Adam:** Yep.

[00:04:14] **Tim:** That's me. How about you, Carol?

## [00:04:16] Carol's Triumph

[00:04:16] **Carol:** Oh, yeah. So I am on the west coast doing some, yeah. doing some remote work, just hanging out with family. And I have to say, I understand now why. West coast is best coast, and this is going to sound awful for most people. But at like 2 57 to 59, I wake up every morning and my eyes are like, it's six.

[00:04:37] **Carol:** O'clock why aren't you out of the bed yet? And I'm like, oh man, it's three. So I go sleep another hour, hour and a half. And then I go run and then I get up and then get ready. And now work. And like, by the time I started working is like six o'clock, six 30. And I'm feeling like way motivated, like all day long.

[00:04:53] **Carol:** It's like that at home. It's like, okay, I'm up at, running six, working seven, eight sometime around then. And it just feels like it drags on. I don't know. It just feels different here. Maybe it's just the time zone or whatever, but.

[00:05:06] **Adam:** like maybe every six months you should just move three more times zones to the west so you can

[00:05:10] **Carol:** ke keep bumping it and keep bumping it. And then, I'm getting a whole lot of test coverage this week on that project that I did. Cause we had a lot of kind of floating requirements with what we were actually going to be finalized with. So we didn't add as much test coverage up front as we typically do.

[00:05:28] **Carol:** typically you can't have any serverless projects go out without a hundred percent coverage, like it's automatically denied. So we went ahead and went out with that, even though we didn't have the test there. So I've been doing a whole lot of testing this week and it's been interesting. I've run into a problem with mocking and how I implemented some things.

[00:05:47] **Carol:** So it's definitely proven beneficial because I didn't even realize that the way I was utilizing something would make it not able to be mocked. So that's been interesting but fun. So.

[00:05:57] **Tim:** Okay.

[00:05:59] **Ben:** A hundred percent test coverage. That's all. That's a very high coverage percentage.

[00:06:04] **Carol:** every line has to be covered.

[00:06:06] **Tim:** Wow.

[00:06:08] **Ben:** Is that? Do you, are you finding that to be a valuable number or does a hundred same arbitrary?

[00:06:15] **Carol:** yeah, sometimes it feels a little bit out there because I, okay. I didn't do it. Not me not taking credit for this, but we might have a test out there that just says, go ahead and mock this and call it. we're just gonna promise it back resolved as yes, it resolved. So resolved is true and that counts as coverage against the function.

[00:06:38] **Carol:** Even though there isn't really any tests going on, it just says you good. And now that chart says a hundred percent. I mean, lines are covered and I'm like, you know, you just said it was true every time.

[00:06:51] **Tim:** that's just pencil.

[00:06:52] **Adam:** So you're executing the lines and then you're just doing like expectations. Be true

[00:06:56] **Carol:** And truth is true.

[00:06:58] **Adam:** So yeah, that's a cheater way to get to a hundred percent code coverage, but I guess it works

[00:07:02] **Tim:** Okay.

[00:07:04] **Carol:** I didn't do it one may.

[00:07:08] **Adam:** definitely not.

[00:07:09] **Carol:** Yeah. Yeah. The song right.

## [00:07:15] Adam's Fail and Triumph

[00:07:15] **Adam:** Oh gosh, I'm gonna make a little callback here to something I talked about previously. And I think, I don't remember if it was a triumph or fail at the time, but I talked about a function like the signature changed. It was struct value array. and I basically, I had a struck value away array in my code.

[00:07:34] **Adam:** And, then a new version of Lucy came out and we were testing it and that code broke. So I was like, okay, we'll find this function is now a built in function. It must've been my thought at the time was, it must have been an undocumented, but available function. And the signature changed when they decided to go ahead and make it.

[00:07:52] **Adam:** Or documented, that turned out to be wrong. what the actual case was was that the function I was called calling was not an undocumented, but available function. It was a UTF that was just like a thousand lines down the same component. And so, no, no kidding. the method's signature is different.

[00:08:14] **Adam:** It's a built in function versus my UTF. And now they're doing different things. And of course, switching to the built-in, didn't like,just stuff broke and it's been broken in production for like, I don't know, a week and a half, two weeks. And I had no idea. And I feel like a total horse's patootie because this is a totally preventable.

[00:08:37] **Adam:** Yeah. Yeah. Like if I had just bothered to highlight the function name, copy command F command V and enter, I would have found the other instance of it

[00:08:48] **Carol:** For anyone who doesn't know that's copy and paste.

[00:08:51] **Adam:** yeah. Copy and paste it into the search. I would have found like if I just searched for it in that file would have found the other instance and I'm like, oh, okay.

[00:08:58] **Adam:** Let me just rename the function. No big deal. So that's what the fix ended up being. It was an easy fix. Right. Just sort of undo the fix that I did previously and change the functioning and okay, fine. Yeah. I just feel awful about that because it was the stupidest of stupid mistakes, but also triumph today.

[00:09:22] **Adam:** These are both today, actually. we put our first feature flag in production.

[00:09:25] **Ben:** No.

[00:09:26] **Tim:** No.

[00:09:27] **Carol:** and

[00:09:29] **Adam:** I mean, it's working great. Uh, the, and everybody that's touched the system so far loves it. So I showed it off at our engineering stand-up and, everybody seems to like it. And then,the mechanism that I built in for like publishing flags and getting them out and distributed to all those servers seems to be working really fast and flawlessly and knock on wood, tap on my, um, everything's going well.

[00:09:50] **Adam:** So

[00:09:51] **Carol:** So you said everybody loves that. You mean the users love the change that you've made under said feature flag or that the people who have saw the implementation of it have been impressed with it. Which did you mean

[00:10:02] **Adam:** the developers that have used it, yeah, the one feature flag that we've actually used for something useful. When I deployed the feature flag service to production, initially I included one active feature flag. That's just on for people with the developer role, we have a role in our security roles that is basically just our staff, so that we can have stuff that's visible to us or that sort of thing. And so it checks to see if you have this role and then it just displays a banner at the top of the page you see, after you log in and it says you are a developer.

[00:10:28] **Adam:** and that's it like, that's all I did just to show that it works and like, and we could toggle that flag on and off in the feature flag dashboard. And it would instantly, you refresh the page and that the banner goes away and comes back. Um, but so, so that was, our first feature flag, but it wasn't the first like real feature flag, this one, I mean, it's kind of kind of nothing, but also it, I mean, it turned out to be useful.

[00:10:48] **Adam:** so we, when we onboard a new client, we, First create a QA environment for them. And we don't create a production environment for them until we're ready to like go live. and once we are live where the customer, we disable our integrated support ticket system in their QA environment, so that there's no worry about people being confused and accidentally submitting a ticket in QA when it should be in production.

[00:11:11] **Adam:** and also like we do periodic database refreshes and we overwrite the QA database from production with some sanitisation. And if there were any actually valid, useful ongoing tickets in QA, they would get deleted. Right? So for multiple reasons, we disable support tickets and QA. However, that's a problem when you don't have a production environment.

[00:11:31] **Adam:** So what our feature flag is is for this particular customer who doesn't have a production environment, we turn on the feature flag. we turn on support tickets in QA. That's it? I mean, it only affects QA, even though it's a. Being evaluated on all production servers,

[00:11:50] **Tim:** Hmm.

[00:11:50] **Ben:** Well, it's still exciting, man. this is the first step on a journey that's going to change.

[00:11:56] **Carol:** This is the

[00:11:56] **Adam:** I'm excited.

[00:11:57] **Ben:** Yeah.

[00:11:57] **Tim:** spear.

[00:11:59] **Carol:** So let me ask you guys, did you guys all get a message from LaunchDarkly on LinkedIn?

[00:12:04] **Adam:** I don't think so. I'll message. Do you have to go into LinkedIn to see that? Because I have no idea.

[00:12:09] **Carol:** Yeah. I got emails. I had a message from someone, so I went and looked back, so I don't use it a lot. Right. And I don't know if it's because of like the stuff Ben's been posting, like with videos and stuff where we've had LaunchDarkly tagged and things, but at the email that was like, let's have lunch and talk.

[00:12:23] **Adam:** Hmm.

[00:12:24] **Carol:** us come in and tell you about LaunchDarkly and we'll bike pay for your whole team to have lunch.

[00:12:30] **Ben:** interesting. Indeed. How I never got one of those, but I've talked to people want to start with a bunch on and off.

[00:12:37] **Tim:** I'm jealous now, why didn't I get one? I would have ignored it.

[00:12:40] **Adam:** I'm the opposite of jealous because I didn't have to go on LinkedIn.

[00:12:43] **Tim:** Yeah. Who are these people?

[00:12:45] **Adam:** So that's me. I guess that leaves, Ben, what have you been up to, man?

## [00:12:49] Ben's Failure

[00:12:49] **Ben:** I'm going to go with a cascading failure, which is that I had a failure that reminded me of another failure. And I know I've mentioned on the show before that we have an angular JS app that is then partially running react internally. So it, it renders react components inside of the angular JS views, which is just a huge pain in the ass.

[00:13:11] **Ben:** And

[00:13:12] **Adam:** They call it being a polyglot, right?

[00:13:15] **Ben:** I think it's a glutton for punishment. Um,

[00:13:18] **Adam:** Okay.

[00:13:22] **Ben:** So I had to do the simplest task. I had changed an API endpoint that they react, that the react view consumes to return an error message. And previously, if it had returned an error message, it would've just shown a generic error on the client saying something went wrong, but there was a particular error code that actually wanted to trap and present a more meaningful error message.

[00:13:44] **Ben:** And I kid you not to get that error message out of the Ajax response into the react view. I had to touch 12 different files just on the client side code because the react stuff uses this old. of a, like a flux data flow where there's a central store and then like nothing can directly touch data.

[00:14:09] **Ben:** Everything triggers, these ads, actions, and these actions get listened to by the store. And then the store changes data internally, and then it emits change events and then things have subscribed to the store, but it's all just like very, everything is indirect. And it was just such, such a huge pain in the butt.

[00:14:26] **Ben:** It took me like 10 minutes to change the server side code to change the error message that gets sent back to the client. And I swear, it took me like four hours to actually take that error message and render it inside of the application, which then reminds me, me have a part in the angular app where this was just after people had started to build some of the react code inside of our app and they were using the flux stuff and everyone's like, oh, you gotta use flux.

[00:14:52] **Ben:** And you gotta use these like Redux style data flows. So I tried to recreate that in a part of the angular JS. And I went and I looked in that code just recently and it is just atrocious. It's a nightmare. And I remember thinking at the time, like people are telling me I have to solve this problem, and I don't quite understand the problem and why this solves that problem, but I'm going to do it anyway because this is what everybody's doing. And I'm just like, I feel so ashamed that that's the reason I built it the way it is. And not because I really understood the problem I was solving. And now it's just this garbage pile of legacy code.

[00:15:31] **Adam:** So did you just say that you wrote this code?

[00:15:34] **Ben:** I didn't write the react code. I wrote then later angular code that was inspired by that react code.

[00:15:41] **Tim:** Okay.

[00:15:42] **Adam:** Hmm.

[00:15:43] **Ben:** it was just failures all the way down.

[00:15:45] **Carol:** so Tim started with, I wrote nice code. That's easy to be refactored and you're ending with damn this code. Damn this go.

[00:15:54] **Tim:** Oh, trust me. I've got plenty of code, just like that.

[00:15:58] **Ben:** You implement it? It's like, I don't know. I'm sure a lot of people go through this phase where they start to read up on design patterns and then they go to write some code and they're like, oh, how do I fit all 20 design patterns that I just learned about inside this code that I'm about to write for the first time, because you think like, that's how code has to be written.

[00:16:15] **Ben:** And it ends up being that your code is ridiculously complicated because it starts solving a lot of problems that you didn't actually have. That's what I did. and I'm, so I feel so angry about it now in retrospect, because it didn't feel right at the time, but I thought that I had to solve something.

[00:16:30] **Ben:** I dunno. I just, I felt like I wasn't smart enough to solve it at the time or to understand why I was trying to solve it that way at the time and just makes me angry.

[00:16:40] **Carol:** We still love you, Ben.

[00:16:41] **Ben:** Thank

## [00:16:42] What's a Swamp Guide?

[00:16:42] **Ben:** you.

[00:16:43] **Adam:** So, Tim, you had this idea for being a good steward of the swamp.

[00:16:48] **Tim:** yeah. I mean, what Ben was talking about kind of illustrates that, right? I mean, you have some program that's organically grown over time. I don't know if swamp guide I was Googling it. I don't think it's a common term.

[00:17:00] **Carol:** Yeah. I was gonna say you have some people with a swamp gut is, cause I don't think a lot of

[00:17:03] **Tim:** guess maybe it's a term we just, we use at our work. So, a swamp guide is a person who knows you have a system that has grown over time.

[00:17:13] **Tim:** It's grown organically. It's been somewhat written and rewritten and there's, there's just lots of pit holes and places that are just convoluted and hard to understand them. So a swamp guide is a person it's not necessarily their job. A lot of times it just becomes you become anointed by just the fact that you've been there long enough.

[00:17:33] **Tim:** and no, the ground. And I think Ben and I probably fall into those categories of having been at a place so long that you just instinctively know, where the hidden bodies are. And so as the organization grows, obviously you have to maintain it. And you got. People that are like, well, I don't want to, I don't understand what is this doing?

[00:17:53] **Tim:** And they're like, well, go ask Tim, go ask Ben. And so that's your job now to be this swamp guide in addition to everything else you already have to do. So swamp guide kind of helps other people understand a system that a lot of times doesn't necessarily have very good documentation or any documentation at all, and help guide them through and understand the house of cards that has been built so that they can actually get their work done. So that's what I think of as a swamp guide. Yeah.

[00:18:24] **Ben:** Yeah, and stuff gets so complicated and you live with it for so long that you don't even realize just how complicated it is. I just, this morning was trying to get someone up and running in our legacy plan. And our legacy platform is dockerized meaning that it should be as simple as you set up some environment variables, and then you do Docker compose up and things should just work.

[00:18:48] **Ben:** And yada, yada yada three and a half hours later, we're still, screen-sharing trying to figure out why node packages are missing and why this commands not working or this thing's timing out. And,it, it's like I'm scraping the bottom of the barrel of like how I had to get things set up. And he had a slightly different version of Docker for Mac running, which I think was causing problems with how the volumes were being mounted.

[00:19:12] **Ben:** Even though the Docker compose file was the same version. And it was just.

[00:19:16] **Adam:** Yeah, it's makes me think about, a change that we had to make recently. How do I explain this? The, so it change to the way that we were compiling some JavaScript for a very small and deeply nested within our application part of our application. and as a result of that, change the environment, had the assumption that like you had changed directory down into, four, four layers deep into this folder and running NPM install.

[00:19:46] **Adam:** And if you don't do that, then the usual JavaScript compiling from the root folder just will blow up when it gets to that point. So, I guess what it made me think is. One of the things that you need to be thinking about as you're evolving your app over time is like, okay, when somebody comes in, when we hire somebody tomorrow, what are, what's going to be wrong with their environment that we need to prevent.

[00:20:08] **Adam:** Right. And so one of the things that I did as a result of kind of that I stumbled across this, in setting up some automated, testing for deploys and stuff. And what I ultimately decided was I created like a NPM script to do a, we call it a clean slate. and it is a designated place for dropping in like, okay, when you first start your environment, when you first clone this repository, these are the things you need to run.

[00:20:33] **Adam:** and so it does this like CD into that folder and when BMCI sort of thing, and that's that way we can use it, not only for our continuous integration, but also for new hires and that sort of thing. And then we just need to document. We also, and that makes me think we have a document. So we have, a Wiki available to our engineering team. Sorry, if you can hear my dog snoring.

[00:20:54] **Ben:** W where does

[00:20:55] **Carol:** Okay.

[00:20:55] **Ben:** live?

[00:20:56] **Adam:** so stack overflow has a, a product called stack overflow for teams and there's like a free, basic

[00:21:03] **Adam:** tier. Um, and so we, we use that as our company, as our engineering team Wiki. and yeah, and so it's just, it's nice. Cause it's sort of question and answer format and everything.

[00:21:14] **Carol:** That's great about stack overflow, except we don't really use the voting because it's not that useful to us. we used at the last job side note. And then if your question got upvoted or your, answer got the most votes and was accepted, then you go and buy like a gift card. So it like, it encouraged you to go answer your coworkers questions.

[00:21:33] **Tim:** Yeah.

[00:21:33] **Adam:** well there's all a five people in my entire company, so.

[00:21:37] **Carol:** So we did the same thing. We have, like a setup page that's on confluence, which is just part of our JIRA LaSeon product suite. And it's like, here's your developer set up? Here's the windows version. And it says at the top, like, laugh out loud. Why did you choose windows? And then, here's the Mac set up, which is like, you're a good guy.

[00:21:56] **Carol:** You got this.

[00:21:59] **Ben:** Yeah.

[00:21:59] **Adam:** Okay. So I have ours open. And since you mentioned the windows thing, I'm just gonna read this quick section. It says machine selection, Mac, Linux, or windows, we don't care. But that said, we do have some automations that assume you have Mac or Linux. So windows may not be the best choice if you're comfortable without it.

[00:22:12] **Carol:** Yeah. It

[00:22:13] **Carol:** was like, we prefer you choose the learn Mac than us support windows. Yeah. I switched to Mac development when I switched to Clare capital and then windows shop all before that.

[00:22:26] **Adam:** So, yeah, this Wiki doc that we have is basically it's labeled, it's like an onboarding doc and there's a lot of different things in here, just talks all the different stuff you have to know for onboarding from payroll to VPN, to everything else. But there's a huge list of, like must have software tools that you're going to need.

[00:22:44] **Adam:** And then, there's recommendations. And then there's like, here's all the software and the things that you are going to need to learn. It doesn't teach you the things about them, but it's just a bulleted list of like, these are the concepts that you need to understand before you can really dig in. And these are our goals as a team and that way, okay, if you don't understand this part yet, then who do I talk to about that?

[00:23:05] **Adam:** And you, you go solve

## [00:23:06] Documentation

[00:23:06] **Tim:** So, I mean, I think you're kind of hitting on one of the things I think. One of the top things of being responsible, swamp guide is whenever it's one thing to just, one-on-one tell a person how to, where to look, what to solve and how to just fix the problem. encouraging them, helping them, or maybe even doing it yourself, write down some documentation somewhere, whatever that is.

[00:23:25] **Tim:** If it's stack overflow, if it's a GitHub, Wiki or whatever, write down these things because they're not going to be the last person to have that problem, right. Someone else is going to be working on at some point. So write it down, write down the steps. if you counter this, here's how you can figure this.

[00:23:40] **Tim:** so creating documentation, you might feel like, well, that's really not my job. I didn't write this in the first place, but I mean, if they're coming to you for the problem, then chances are the next person who runs it into it. They're going to come to you again, but now you can point them to, well, okay, go here and read this.

[00:23:57] **Tim:** This explains, what's going on here? Why it's doing it that way. And then now you're making your job easier down there.

[00:24:04] **Ben:** At work, we have this weird dynamic where the people who have been at the company for a shorter period of time, actually understand the documentation much better because they've had to look it up. Whereas the people who have been there for a long time, don't even know that half the documentation exists because they've never had to look.

[00:24:21] **Ben:** And they don't even know that half the documentation got created because people were onboarded and were confused. And to Tim's point, like then people documented it because it was confusing. So like the guy that I was talking about earlier that I was trying to onboard this morning, he was like, oh, is there maybe a, like a service diagram or some sort of architectural diagram that I could look at?

[00:24:41] **Ben:** And I was like, don't think so. I mean, there might be, but I wouldn't even know where to locate it. If it's not in the read me of the repository that I'm working with. Like, I don't know where to go.

[00:24:51] **Tim:** Hm.

[00:24:52] **Carol:** Yeah. So you should have like a good document storage solution. Like confluence is really good. It is laid out. Like we have application documents in there that our SQA team has written that have some of the guidelines for how they even decided to build these stories. And you know, why it's so complicated and the complexity behind it.

[00:25:12] **Carol:** And then the onboardings on there and just general like questions and answers. it's. But again, we have a lot of people and you're a much smaller team, so you don't onboard as people as often as we do.

[00:25:25] **Ben:** and I have to admit, I find confluence very intimidating. I don't know why there's something about, I just have I go into it with this fear that I'm not going to be able to find the information that I need. And I don't quite understand how confluence is structured, which I think is silly because it's basically just folders and folders of folders, but there's, it's so vast that it makes.

[00:25:50] **Carol:** Okay.

[00:25:50] **Ben:** I don't know, I just get very intimidated and like I'll search for something like database migration and I'll get like 20 results. And I don't know which one's the right one. And then I immediately just freak out and decide that conference is not the place for me.

[00:26:04] **Carol:** He's so scared.

[00:26:06] **Ben:** don't know why it's so intimidating for me.

[00:26:08] **Carol:** Yeah, it shouldn't be, I mean, for me, I'll go in the ugly. We were working on story planning today and I had to find out what, I didn't even know what a word meant, and I didn't want to be the person going, what's a base because as B lowercase capital, a C E, and I'm like, I don't know what they're talking about, but we're modifying the base.

[00:26:26] **Carol:** And I'm thinking the whole time they're talking about like the base file, like, you know, everything's off base this space. Right. And I realize it's a whole nother word and I don't want to ask. So I just went and looked it up. Sure enough, there's SQL documentation for, I was like, oh, there we go. Now I know what it is.

[00:26:41] **Adam:** So, what is it? Cause we're all dying to know.

[00:26:44] **Carol:** a vendor integrate as like a vendor integration thing. So that's just something internal. My company has acronyms for everything. It's the worst because you don't know what any of it means that we need a swap guide for.

[00:26:58] **Adam:** Yeah. Right? The acronym.

[00:27:01] **Ben:** The thing that drives me crazy at work is they're always talking about quarters like this quarter

[00:27:06] **Ben:** of the financial year, 22, but the financial year at our company starts in February. So the quarters are all shifted

[00:27:15] **Adam:** by just one month though, that's weird. Yeah.

[00:27:17] **Ben:** but they're just one month. And also I just find quarters, like a really weird conceptual model to use in conversation.

[00:27:23] **Ben:** Like just say September, or like sometime between November of this year in February of the next year. It's like when you're learning a different language and someone says something to you in French, and then in your brain, you're converting it from French to English as you're consuming it.

[00:27:38] **Adam:** Yep.

[00:27:39] **Ben:** Don't make me do that. Just use months. Everybody understands months.

[00:27:42] **Tim:** Yeah. Well, so we work very heavily with universities and most of them because of the way the school year works, their fiscal year is either like July through June. Or like September through whatever month comes right before September, August. Okay.

[00:27:58] **Adam:** so, and the thing that trips me up the most with it is like, okay, so you've got a fiscal year starting on, just say like July 1st or whatever, but then, so is fiscal year 2021 the year that starts in 2021 and ends in 2022 or is fiscal year 2021, the one that ends in 2021,

[00:28:16] **Ben:** Oh, just use

[00:28:17] **Ben:** dates,

[00:28:18] **Tim:** Yeah.

[00:28:20] **Adam:** use the calendar. We all agreed on this stupid Gregorian calendar anyway,

[00:28:24] **Tim:** All

[00:28:24] **Carol:** do.

[00:28:25] **Adam:** and we're suffering through time zones. Just give us the count.

[00:28:28] **Tim:** Yeah.

## [00:28:28] Leaving The Swamp Cleaner Than It Was Before

[00:28:28] **Tim:** I was gonna say, I. Yeah, I'll throw something else out here, which I think, is it another responsible swamp guide principle? Cause I've seen this become contentious, is that it is not about trying to figure out why in the world it was built this stupid way blaming whoever wrote it. That stupidly that is just a pit of despair that you can't get out of once you start going down that hole.

[00:28:53] **Ben:** I find that I apologize a lot when I'm running people through the code. I'm like, I'm sorry. I know this is crazy. It's really old. This codes like the oldest code in the universe. I'm sorry. It

[00:29:04] **Tim:** Yeah, I do too. But I think it's not about that. What it's about is making sure that you or whoever is assigned to work on it, that you're guiding leave the swamp a cleaner place when you.

[00:29:17] **Adam:** So, it's funny that you mentioned this. I have this document that I've been working on for my company and long-term the intention is to like get the rest of the company to participate in it. But for right now, it's just sort of my observations of our culture as a company and whether it is something that I want for my team or that I'm recognizing in my team.

[00:29:39] **Adam:** I think it's a little bit of both. but one of the things in that document is that you should always assume positive intent, right? We didn't set out to write code that's a frigging mess or difficult to understand or hard to find the thing you need to work on. It just ended up that way because we were solving problems and maybe there was a tight deadline or low budget or, whatever the problem was.

[00:30:03] **Adam:** and that's absolutely something that every single one of us has gone through. And so we should be able to relate to it. And so to be angry at the people who did it before you is hypocritical, because you're going to be doing it next time.

[00:30:15] **Tim:** a waste. It's a waste of time. I mean that you can't change the past, right? It's th you got to where you got because of reasons, and those reasons felt very valid at the time. So there is no point getting upset and angry about it, just, and some people just can't let that go. They're like, this is what they should have done that.

[00:30:32] **Tim:** Yeah, they should have. We see that now. I think even the people who wrote it will probably see that now, but her ringing on that one point is doesn't solve the problem. let's fix the problem. let's make it better when we leave. And that's what I challenged. Like people, when people in some personalities just really hang on to that, they just really just want to hammer home how stupid this solution was.

[00:30:53] **Tim:** Okay. I get it. I want you to rewrite it to the point where if there's anything stupid in it, you have to take a hundred percent ownership of it.

[00:31:00] **Adam:** Okay. It's funny. Cause I was, as soon as I finished saying all that stuff about assuming positive intent, my gut reaction was to think like, well, but there are going to be times where somebody is doing something intentionally lazy or something like that. But at the, and then my reaction to my reaction was like, yeah, but also that being lazy can be a positive thing, right?

[00:31:22] **Adam:** Like they're not wasting company time on stuff that may not be completely

[00:31:26] **Tim:** sometimes it's just organizational failure. I mean, it's ignorance on the part of person working on it and the ignorance is not their fault.

[00:31:33] **Carol:** or you're also. Forced into something because you have shortsighted vision for management. So you have that, you were pushed down it and now you've got this big, giant debt. That's just going to sit there forever because you weren't given the time at the technical level to get it. Yeah. a coworker had sent me this was years ago, so I had to go look it up while you guys were talking, but it was, it's called the big ball of mud.

[00:31:56] **Tim:** Okay.

[00:31:57] **Ben:** Yeah.

[00:31:57] **Carol:** If you ever go look it up. I mean, there's a lot of really good insight in there. Basically, you end up with this giant ball of mud that you can get out of.

[00:32:06] **Carol:** So someone's got ed be the leader through it, and you gotta realize that it's not your swamp guides problem. It's not their fault. Like they didn't introduce this on their own, even if they were a part of it and the original like startup of it or the beginning phases of it, it's a big giant deal for them to you in there having them to walks around just like you.

[00:32:27] **Ben:** It's interesting. we've talked about this in a really early episode. This idea that there's a people get looked down upon. If you take the constructs from one language and you bring it into another language where they're like, don't go into ColdFusion and try to write it like a Ruby application, or like, don't go into go Lang and try to write it like a PHP application.

[00:32:48] **Ben:** But I wonder how much of that is from people. Had to work in a code base that they weren't familiar with. So they don't understand the constructs of the language. They don't understand how the application is organized. So they just try to write code to get things done. And then the people who are really familiar with the code base, look at that and be like, Ugh, that's what happens when you have a Java developer come and work inside your, you know,

[00:33:09] **Tim:** Could be

[00:33:10] **Ben:** but, but maybe like 10 to Tim's point.

[00:33:12] **Ben:** Like it's just naive. Like they just didn't know what they were doing. It's not like they were trying to do something wrong or they were trying to write a Java application inside of a PHP application. They just didn't know how that app is organized.

[00:33:25] **Carol:** I think it's easy to take the, the logic and the ability to write software to any company or any language. It doesn't always transpose over to what you're actually doing though. So it does come off looking sloppy sometimes.

[00:33:39] **Adam:** So this all reminds me of like Hanlon's razor, right. never attribute to malice that, which is adequately explained by stupidity. But, but I want to, I mean, I'm trying to come at this from a positive direction. Right. So instead of stupidity, I just want to change that for like, Benign ignorance.

[00:33:54] **Adam:** Right? So like it's not their fault. They just didn't know any better, whether they didn't have the coding chops to do it cleaner, or they didn't know the better process or they didn't know your system well enough, organize it better. if ignorance can explain it, then don't assume malice.

[00:34:09] **Carol:** I like

[00:34:10] **Tim:** Yeah. Yeah.

[00:34:11] **Ben:** there. There's almost a, I don't attribute malice necessarily, but I do get bothered by the fact that people make decisions and then they're not there to deal with them.

[00:34:21] **Carol:** Oh, we just talked about the suddenly

[00:34:23] **Ben:** So it's not like I'm not, it's like, I don't think that they were trying to screw me over, but like I

[00:34:31] **Adam:** your club, Ben.

[00:34:32] **Carol:** Okay.

[00:34:33] **Ben:** just, I do get frustrated. that I have to deal with it.

[00:34:37] **Adam:** Yeah,it's a crappy.

[00:34:38] **Ben:** Yeah.

## [00:34:39] Accepting Swamp Duties

[00:34:39] **Tim:** that's kind of another thing I would say is I'm trying to think of the principles here, involved in this is that it's the swamp guides job, even though sometimes it's not necessarily even his job or her job it's, but just because the other person can't do their job, unless they get help from you. This swamp guys, shouldn't be upset with the person asking for help,

[00:35:02] **Carol:** No, I agree.

[00:35:03] **Tim:** because I mean, if they didn't ask you for help, all they would do is make the swamp work.

[00:35:08] **Carol:** Yeah.

[00:35:09] **Tim:** you should be very privileged that they think enough of you to ask you for advice. And then they had the humility to say, look, I don't really understand what's going on here. Can you shed some light here? And yes, it's an interrupt in your day, but I mean, overall is better for the application. If you can help them understand it and then encourage them to, as I said earlier, leave the swamp a little bit cleaner than it was before.

[00:35:33] **Carol:** Yeah.

[00:35:35] **Adam:** Yep. Being a good swamp guide, I think falls under the category of other duties as assigned and nobody gets hired to be the swamp guy.

[00:35:43] **Tim:** Yeah.

[00:35:44] **Ben:** Although

[00:35:45] **Tim:** It just falls in your lap.

[00:35:46] **Ben:**

## [00:35:46] Who Gets To Be A Swamp Guide?

[00:35:46] **Ben:** When my team, like when my actual individual team at the company, when we were used to hiring people, we would have onboarding buddies. So every time a new person would get hired, you get assigned someone on the team and they would sort of walk you through and be your consigliere area over the next couple of weeks, about how things work. But, oh man, I'll tell you, like, there was nothing as joyful for me as when someone else on my team was excited about being the onboarding buddy. And I was like, yes, not me. And it's not because I don't, I'm fairly introverted. And just being with people, even people I like is exhausting. So the idea of onboarding people, which is a very Valiant and wonderful thing to do, it's still exhausting.

[00:36:31] **Ben:** for me personally, I can't speak for everyone, but it's exhausting for me. And it's like, even I get that slack message where they're like, Hey, can I, can we screen share for a minute? I'm a little confused. And I have to like center myself. I'm like, you can do this. It's okay.

[00:36:44] **Carol:** so

[00:36:44] **Adam:** I have to do when my kids are bugging me.

[00:36:47] **Carol:** it's the same thing, exact same thing. We assign those people to some of the newer hires, because like you guys were saying earlier, I'm not sure who it was, but one of you three, definitely. Was it? Oh, it was Ben. I got it. Now I knew who it was. It was Ben was saying he couldn't even like find the documentation and you don't even know where it is.

[00:37:02] **Carol:** Like the older people in the organization who've been there more tenured. Don't know what onboarding looks like. So I'm, I already know how to go find the calendar to put my time off on, because I just had to do that a few months ago, so I can still show someone. So we do kind of learning the ropes together through the newer people.

[00:37:21] **Carol:** And then as we get accustomed to being on the team, then you start getting assigned to work projects with more senior, more tenured people on the team to actually do work, work with. Yep. It works out well.

[00:37:33] **Ben:** quick wild tangent for a second. the idea of being able to teach things that you just learned actually makes you a better teacher for certain things. that's a topic that comes up. in various places, especially with regard to people who have imposter syndrome and they want to get into teaching.

[00:37:49] **Ben:** They want to get into blogging writing or doing stuff in public. And they're like, oh, I, I don't feel like I'm good enough to do this. There's all these people around me. Who've been doing this for years and they can talk about it much more effectively. but what those people don't have is that recency of the problem solving that you had to deal with.

[00:38:04] **Ben:** And I think it's a great, it's a great point that the people who had to struggle through something more recently are probably more capable of teaching you how to get through it because you're sort of in

[00:38:14] **Tim:** Yeah. I mean, how many times have you done like an online tutorial on something, learning some new thing and it's like, you get stuck on the first two pages because there is a huge assumption. There's a huge assumption there. And you're like, I, it I've run through that many times where I'm just like, I, it would take me days to get for that first few, couple chapters because they assume something or even worse,th the binaries or the code was an up-to-date and the thing I was reading, and it had updated as a new version of whatever language it is.

[00:38:42] **Tim:** And you have to use that new version, and that's not in the article. There's a huge amount of assumed knowledge. And I think you have been you're right when it comes to learning something new and just starting out, sometimes person with less experience is better at teaching that a person with a whole lot of experience, because there's a whole lot of assumptions.

[00:38:58] **Tim:** They make that a new person wouldn't,

[00:39:01] **Adam:** that actually has a name it's called the curse of

[00:39:03] **Adam:** knowledge. Right? So you've been working in the system for so long that you have actually created in your mind layers of abstraction and you're working at, layer seven or something on a daily basis. And when you're trying to explain something, it's the explanation works best when it's down at layer one.

[00:39:19] **Adam:** Right. And, so it's hard for you to go down those layers because you are so practiced at thinking at the high layer that, you, it takes you effort to go, okay, well really what does that mean? And that breaks down into two or three things, and each of those, you have to go well, but what does that mean?

[00:39:37] **Adam:** And you break it down further and further until finally you get like understandable. Directions. So just, you end up with a lot more directions because each of those layers of abstraction exists for a reason.

[00:39:48] **Ben:** Yeah, totally.

[00:39:50] **Adam:** updated, our onboarding doc. Cause I was reading through it, just looking for things to talk about while we were just, having this discussion here and I found one thing that was like already out of date. So I'm updating it off the clock

[00:40:04] **Carol:** Oh, one thing that we do in our doc that I meant to bring up earlier is we don't force anyone to use any specific ID. So you get to choose what you want. It's just, if you do one that we aren't doing, like if you use one that we aren't currently using, go add the documentation for it. So right now we have documentation for Adam.

[00:40:25] **Carol:** We have documentation for vs code and for, intelligence. So it has all the packages you need. It has how the get database connections in like all of that's been put up so that like, if you're going to spend the time learning how to use this IDE and how to configure it for our project, go ahead and spend the time creating the documentation.

[00:40:45] **Carol:** So someone behind you can do the same if they choose.

[00:40:47] **Adam:** Nice.

[00:40:48] **Carol:** So yeah.

[00:40:49] **Adam:** Yeah, we have the same attitude in our, like in our culture document. I think there's something in there too about that. And it's just like, you can use whatever you want, whatever's productive for you. But,our institutional knowledge currently is, and these things and what we can help you, but you know, like, we use prettier to make our jobs. Less ugly. And, and so we're going to expect that your whatever you're using is, also going to run prettier, whether you do choose to do that on the command line, or if it's integrated in your IDE or whatever, the assumption is just there that you're going to have run it. So do something that would.

[00:41:21] **Tim:** think I came up with one more kind of thing, I think is a good swamp guide, attitude. So let's say some people actually take pride in like being the swamp guide. Right. Cause other people come to them, ask for help. It does give you a feeling of importance and being needed, but sometimes even the swamp guide gets lost.

[00:41:38] **Tim:** and so it's

[00:41:39] **Tim:** the swamp guide needs to have the humility to say, I don't know. And either hell I'll help you figure it out together. Or we can go to someone else who might know. and I think Ben's example of what he did today, where he's, what spent three hours helping a person with a Docker problem.

[00:41:53] **Tim:** I mean, that's, you spend three hours, right? you didn't know the answer immediately. It wasn't like, oh no, you do this. It was frustrating. But as, but I mean, you did it, right. So if you don't know, figure it out together and learn from that experience or say, you know what, I, this is not my field.

[00:42:09] **Tim:** let me introduce you to this person. they know they might know how to answer.

[00:42:14] **Carol:** Yep.

[00:42:15] **Ben:** Yeah, we actually, and I go back and forth on whether or not I'm comfortable with this idea, but we have sort of swamp expertise where we have certain people who are the person, like the one person in the company who still knows about an area of the application. They tend to. The ones who will guide you through it.

[00:42:33] **Ben:** and I hate that a little bit because I, that's a pretty high bus factor. If that person were to get hit by a bus, right. Then nobody knows about that part of the application, but I then validate or not validate. I justify it by then remembering that I have other stuff to do.

[00:42:49] **Tim:** Yeah.

[00:42:51] **Carol:** there's one less thing. You have to know everything about.

[00:42:54] **Ben:** Yeah.

[00:42:55] **Carol:** You can know high level and it's okay. SMEEs, they're called SMEEs

[00:42:59] **Tim:** matter experts.

[00:43:01] **Carol:** use subject matter experts.

[00:43:05] **Tim:** Yeah. I don't know if it's a swamp guide. It feels a little bit different than an expert. It's like a swamp guide is just a person who's been through the battles. Right. They've got the scars and they got the stories at Dell, but they're important. I mean, it's like, if you got an older application, you need those folks.

[00:43:21] **Carol:** yeah. I mean, you just got to navigate it together.

[00:43:23] **Tim:** But like I said, I think the biggest thing is just leave that swamp a little bit cleaner before you leave

[00:43:28] **Adam:** okay, well, does that wrap it up then?

[00:43:31] **Ben:** Okay.

[00:43:31] **Adam:** All right. Well then.

## [00:43:34] Patreon

[00:43:34] **Adam:** This episode of Working Code was brought to you by the squam and listeners like you. And I feel like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. And we do have a new patron this week.

[00:43:46] **Adam:** So welcome aboard

[00:43:47] **Tim:** My favorite hater,

[00:43:49] **Carol:** Hey.

[00:43:50] **Tim:** favorite hater.

[00:43:51] **Ben:** heart, Matt.

[00:43:52] **Adam:** so to say, thanks for your support. We offer perks to our patrons. They all get an invite to our Discord server, where we hang out and chat about the podcast, work stuff, life stuff. We have other perks available, like early access to new episodes and our after show of which we're going to go record after this every week, we think our top patrons and since this week is part of every week, we were sending out a huge thank you to Peter.

## [00:44:15] Thanks For Listening!

[00:44:15] **Adam:** If paying for podcasts, isn't your thing. That's cool with us. We appreciate you taking the time to listen and you can help us out without spending any money by sharing the show with your friends and your coworkers. You can also leave us a rating and a review on iTunes or wherever you get your podcasts, because apparently that's helpful.

[00:44:29] **Adam:** Please send us your questions and your show topics on Twitter or on Instagram @WorkingCodePod. And it's been awhile since we've gotten any, if you guys are listening to this and you got an idea, send it in, or you can leave us a message at 512-253-2633 that's 512-253-CODE. We'll catch you next week.

[00:44:47] **Adam:** And until then,

[00:44:48] **Tim:** Remember guys, your heart matters, especially our new patron, Adam Cameron, your heart,

[00:44:52] **Ben:** Especially

[00:44:53] **Carol:** So

[00:44:54] **Tim:** and hate matters so much. So good. I feed on it.

[00:45:00] **Adam:** I don't know if we've actually set it on here. We've set it on Twitter and everywhere else. Your

[00:45:04] **Tim:** Your hate matters to me.

[00:45:09]

## [00:45:25] Bloopers

[00:45:25] **Ben:** The marathon made me think of nipples, which made me think of my internship. And, years ago. I was in college. I got this internship at this, at a web development company and like day two, the, one of the women who was like a founding partner at the company, she had just had a baby. And so she was nursing a lot.

[00:45:47] **Ben:** So she sent me to the store to get her nipple cream because her, she was all chafe.

[00:45:53] **Carol:** Oh, it's awful. Yeah.

[00:45:55] **Ben:** it was not something like, you know,

[00:45:58] **Ben:** a

[00:45:58] **Carol:** You ever thought, right?

[00:46:00] **Ben:** feels comfortable doing

[00:46:02] **Carol:** like I thought I was going to be giving you coffee,

[00:46:05] **Carol:** non nipple

[00:46:05] **Carol:** cream. Did you offer to apply it for her?

[00:46:11] **Ben:** no.

[00:46:13] **Carol:** She's him helping me check those out for you. I'm a professional here. I know what they're supposed to look like.

[00:46:19] **Tim:** this is back when he was doing kinky solutions stuff, right?

[00:46:23] **Carol:** Ooh,

[00:46:24] **Ben:** This

[00:46:24] **Ben:** this is pre kinky solution.

[00:46:26] **Tim:** it? Oh, wow.

[00:46:27] **Carol:** is what inspired kinky solutions.

[00:46:30] **Tim:** What was funny is Carol's face when you said talking about marathons made me think of no.

[00:46:34] **Ben:** It is a common complaint though, for

[00:46:36] **Adam:** Usually for guys

[00:46:36] **Adam:** though.

[00:46:37] **Tim:** Yeah. When they're

[00:46:37] **Ben:** Oh, is it just for guys? I didn't realize that.

[00:46:40] **Carol:** cause their shirts rub against it. We usually have on bras pulled us pretty tight.

[00:46:43] **Ben:** I just assumed that was like everybody's chafing.

[00:46:47] **Carol:** No, I get

[00:46:47] **Adam:** you see dudes running down the road and there's just like streams of blood on their shirt coming down from their nipples.

[00:46:53] **Carol:** it,

[00:46:53] **Ben:** All right, let's do this.

[00:46:55] **Carol:** I don't like mosquito, so I'll stay out of the squat to swamp. I keep wanting to say squawk. I don't know why I wouldn't put a Q in

[00:47:02] **Tim:** I mean, I'm the one who had dental work today. I should be slurring.

[00:47:06] **Carol:** I haven't had alcohol like a week.

[00:47:08] **Tim:** What.

[00:47:09] **Carol:** I think I'm like detoxing or

[00:47:11] **Ben:** You're too sober.

[00:47:12] **Carol:** to sober.

[00:47:14] **Carol:** just feel sweating all over it, even when there's done wiping down, like, know, I think I went to the gym and that makes sense.

[00:47:19] **Tim:** What

[00:47:19] **Adam:** talking about the gym. I think we were talking about the gym.

[00:47:23] **Carol:** Um, it popped up that something came up like with the podcast. I don't know if I didn't get the notification. The new episode came up. So when I tapped it and started playing it, it wouldn't stop

[00:47:31] **Tim:** oh,

[00:47:32] **Adam:**

[00:47:32] **Carol:** And I'm like, oh no, what? It's

[00:47:33] **Tim:** It's possessed. Get an Exorcist.

[00:47:35] **Carol:** I give up,

[00:47:37] **Adam:** with your phone while we're recording Carol.
