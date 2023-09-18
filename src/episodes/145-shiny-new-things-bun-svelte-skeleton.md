---
title: "145: Shiny New Things - Bun, Svelte, Skeleton"
description: "Adam, our early-adopter in residence, talks to Carol about Bun, Skeleton, and Svelte."
date: 2023-09-20
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/29db6b31-b160-4a00-9459-9697d441cd31"></script><div class="redcirclePlayer-29db6b31-b160-4a00-9459-9697d441cd31"></div>

Adam, our early-adopter in residence, talks to Carol about [Bun][bun], [Skeleton][skeleton], and [Svelte][svelte]. With a focus on introducing new tools to an existing team, the two mainly talk about Bun, a hot new all-in-one JavaScript toolkit that is simultaneously a _runtime_, a _server_, a _package manager_, and a _test runner_. Come find out why its feature-set and speed leave Adam singing, _My application don't want none unless you got Bun, hun!_

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[bun]: https://bun.sh/
[skeleton]: https://www.skeleton.dev/
[svelte]: https://svelte.dev/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/145-shiny-new-things-bun-svelte-skeleton.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** Your, take your plumber example. Now, imagine, it's people that really enjoy doing plumbing, and the plumbing company matches them up with people who need plumbing done.

[00:00:10] **Carol:** It's like Match.com, but not for relationships.

[00:00:14] **Adam:** Match.com for plumbers and people with broken sinks.

[00:00:18] **Carol:** Yeah, or Power Rangers down the toilet.

[00:00:21] **Adam:** Yeah, oh my god.

## [00:00:22] Intro

[00:00:22] **Adam:** Okay, here we go. It is show number 145. And on today's show, we're going to talk about some new stuff and things that are happening and things that we're doing. Greatest intro ever. We're going to talk about bun. We're going to talk about side projects. We're gonna just see where it goes. It's another, twofer.

[00:00:58] **Adam:** it's just myself, Adam and Carol.

[00:01:00] **Carol:** Hello.

[00:01:00] **Adam:** Tonight. Welcome back Carol. It's great to see your smiling face and hear your bubbly voice.

[00:01:06] **Carol:** I mean, you missed me on the last episode because you weren't around, but Ben already got reintroduced.

[00:01:11] **Adam:** That's true, that's, I only have myself to blame for that because my ambitions take me into a million different directions all at once. I couldn't be on the last episode because I was attending a, a meeting of the, the board of directors of my skydiving club. So, that's where I was.

[00:01:26] **Carol:** That sounds super fancy.

[00:01:28] **Adam:** It's a bunch of skydivers sitting around bickering about finance and airplane maintenance and policy stuff and

[00:01:36] **Carol:** Okay, not so

[00:01:37] **Adam:** out how to get there.

[00:01:38] **Adam:** Figure out how to keep it going. Yeah.

[00:01:41] **Carol:** Yeah.

[00:01:43] **Adam:** Anyway, like I said, we are going to talk about a bunch of new stuff, but first let's start with our triumphs and fails. Carol, you went first, last week, so I guess I'll go first this week. and we'll see how the new schedule goes once we get everybody back on.

## [00:01:55] Adam's Triumph

[00:01:55] **Carol:** I am going to start with a triumph. Woo woo.

[00:01:57] **Adam:** I, yeah, it's been a good week for me. I have spent a bunch of time this week writing code, which just feels very nice. And in particular, I've been working on a fun little project. it's not even like that complex or that difficult and it doesn't require that much cleverness, but it's just the end result is something extremely useful and, the customers I know are going to be thrilled to have it.

[00:02:21] **Adam:** So, basically... In our primary, I don't know, it's, so we have, I've talked in the past about, we have our two product. We have the platform, which is sort of like a whole bunch of, a whole bunch of different modules, for a variety of different things, like online giving, alumni association, membership management, events, email, et cetera.

[00:02:40] **Adam:** And then we have a second product, which is only for huge events where you might have thousands of people attending, and it's got to be built very differently to support that. That, that large event product, we call it our signature event system, has printing capability, right? So you have thousands of people coming to this event.

[00:02:58] **Adam:** When they show up, they get their name tag printed on demand as they check in. And here's a badge holder to stick it in and off you go sort of thing. And, our customers that use both systems have long wanted the ability to do nametag printing in the smaller event module that's built into the platform, which we agree would be a wonderful thing, but there's hurdles there.

[00:03:19] **Adam:** And one of those hurdles has always been that for these signature events, Some customers do more than one a year. I would say the average is very close to one a year. You know, like you might do, reunion and homecoming, right?

[00:03:32] **Carol:** Okay. Yeah.

[00:03:34] **Adam:** You know, some, some customers do like commencement, right? So only those events where you're really going to have a whole lot of people, you might have a whole lot of different events and activities for them to attend.

[00:03:42] **Adam:** So you're not going to do too many of those a year. For those, since it's only so infrequent, the nametag layout and design and all that is done, it's all like basically hard coded into the nametag for that customer for that event. And that obviously wasn't going to fly for a system where you have, you know, 20 different customers that each have 20 different events every month.

[00:04:05] **Adam:** And we're just not going to jump into that and bite that off. So the thing that I built, which is largely based on the code that Steve wrote. So he kind of took the first swing at it and said like, here is a framework within which you can work. And it has like some printing stuff built in and whatever.

[00:04:20] **Adam:** But, you know, he laid the groundwork and then I came in and I was like, and here is how we're going to make it super dynamic, right? We're going to define, here's, you know, 30 different fields you can choose from, which like, it might be your pronouns, or it could be your last name, it could be your last name at graduation plus your married last name, right, or, you know.

[00:04:38] **Carol:** Okay, okay.

[00:04:38] **Adam:** of different things, like, so you, there are options and you can, whatever makes sense for your event, right, you might want to see employer and job title or whatever, and so you can pick fields and drop them into the name tag, you can organize what goes on what line, and then for each line you can set, The height of the line in millimeters, um, and, and like margin above it.

[00:05:02] **Adam:** and so, and we use a JavaScript plugin to resize the text so that it always stays one line. So if you have somebody with a huge name and you put like first name and last name on the same line.

[00:05:14] **Adam:** Then, the text size will get shrunk down because we don't allow the text to wrap, right, it's always one line. So, but then somebody whose name is, you know, like four or five characters long is just gonna be, is gonna be huge, right, yeah. and so, you have to take that into consideration. So, it also has a live preview and the preview actually shows two previews.

[00:05:33] **Adam:** There's a, somebody whose data is all short and data, and another one where the data is all long,

[00:05:39] **Carol:** Look at you, smarty pants.

[00:05:41] **Adam:** it's so much fun to work on this because it's like, I can, I can just feel it. The energy is high working on this, right? Because I know the customers are going to be like, this is amazing.

[00:05:49] **Carol:** I can see it in your face, like you're very excited

[00:05:52] **Adam:** I'm pumped.

[00:05:53] **Adam:** It's exciting. It's, it's fun to work on because I, you know, it's fun to work on because I know it's going to be well received. I know it's like something that they're chomping at the bit for, and, and it's just, that makes it, rewarding, I guess.

[00:06:07] **Carol:** Yeah.

[00:06:08] **Adam:** Anyway, so I've been working on

[00:06:09] **Carol:** a, I was gonna say, it's a big problem solve. So that helps too. Like you're actually getting to innovate on something that needs to be done. So you're getting to do something new while you're also solving this problem. So that's always a win.

[00:06:21] **Adam:** Right. And then as with like most of my really interesting and useful and well done code, Steve will then turn around and steal it and put it back into the signature event system, and take full credit for it. And so, you know, it's, it's like, you know, a little, we kind of go back and forth, right? Like the signature system kind of outpaces the platform in some areas, and then we'll steal that and improve on it into the platform.

[00:06:43] **Adam:** And then it just goes back and forth, back and forth. We're always. Using one to push the other forward

[00:06:48] **Carol:** Is he the only one working on the signature system?

[00:06:51] **Adam:** for right now. Yeah.

[00:06:52] **Carol:** Yeah.

[00:06:53] **Adam:** Yeah. I mean, it's one of those things where like, you know, he started it by himself. That was the, the basis for our company, right? Like the, that product was what, what launched this company. And, you know, then we branched out and created the platform sort of as he hired me, like he was doing the events thing by himself for like three or four customers.

[00:07:12] **Adam:** Just make it at work by himself. And then like, he saw this need to, to branch out and do this other stuff. And so brought me on, we built the, the platform. And, so at that point it became like, this thing is his and this thing is mine. and we brought on other people to work on my thing. And he's still kind of, his thing by the time that we started the company was, pretty mature, at

[00:07:31] **Carol:** Yeah. Pretty stable. Yeah. Yeah. That makes sense.

[00:07:38] **Adam:** So anyway, now that I've rambled forever, that's my stuff. I'm just, I'm just excited and happy. And, and I didn't even mention, you know, as we're recording this, it's the week that, Bun 1. 0 was released. And so I've been like playing with Bun a little bit. It is super fast, and exciting. So. You know, that's another thing contributing to my hype level being up.

[00:07:58] **Carol:** Yeah I just did a quick Google to figure out what you were talking about because I've been living pretty much off the internet

[00:08:05] **Adam:** I bet you that's

[00:08:05] **Carol:** and I'm enjoying just time away and time with my husband and dog and yeah So I'm not up to date on anything current.

[00:08:14] **Carol:** I couldn't tell you news. All I can tell you is if it's gonna rain today That's it. That's my limit Yeah

## [00:08:21] Carol's Triumph

[00:08:21] **Carol:** I'm going to throw out a big triumph because I'm making it through one more day at a time. And, you know, if you listen to the last five gaps, you heard me and Ben talk about just small wins, small victories, getting through this very trying time in my life, moving across the country and kind of uprooting everything and trying to adjust.

[00:08:41] **Carol:** And it's one more day down. And I have 18 more to go before I finally get, you know, my desk back, my desk chair, my pots and pans, my coffee maker,

[00:08:52] **Adam:** All your stuff.

[00:08:53] **Carol:** my stuff, because it's still, you know, in storage waiting for us to move into our actual house. So just every day is one more day closer to getting to that happy point.

[00:09:04] **Adam:** You said 18 days left. How many days have you been without your stuff?

[00:09:08] **Carol:** for, let's see, what's today's date? I lost everything. I lost it. It sounds so sad. It sounds so terrible. my house was packed up on pretty much completely unusable on August 22nd.

[00:09:21] **Adam:** Oh my goodness.

[00:09:22] **Carol:** Yeah.

[00:09:23] **Adam:** Wow. It's a long time ago.

[00:09:25] **Carol:** Yeah, it's little things, too. It's like I went and bought a bag of dog food and realized I don't have a dog food storage container anymore because it went on the truck as well.

[00:09:34] **Carol:** So I had to put them in small supplied bags and then tape the bag shut to keep any rodents out of it and stuff. So it's just, it's little things I don't even think about until I'm like, oh. I don't have fingernail clippers, I have to go buy fingernail clippers. So, 18 more days, that's all I got. 18 more days.

[00:09:53] **Adam:** Yikes. Your nails can just get long for the next 18 days.

[00:09:56] **Carol:** Yeah, I can also just get a pedicure, I guess.

[00:09:59] **Adam:** Or chew on them.

[00:10:01] **Carol:** Yeah, my toenails, I'll pass on that one.

[00:10:05]

[00:10:06] **Adam:** well, let's talk about what's going on then. so I, I did listen to the episode that you recorded with Ben. and I, I apologize. I don't have it memorized. you, I remember you guys talked about when you're going to start your new job, but I don't think

[00:10:18] **Carol:** Yeah, the 25th. No, I haven't started yet. I started the 25th. So the week after this podcast releases, this episode releases, I'll be starting that following Monday.

[00:10:28] **Adam:** Oh, that's cool.

[00:10:29] **Carol:** Yeah, I'll be writing code again. I'm really eager to get in and write code again. Like I've had things I could have been working on for people and I've just turned everything down for the past.

[00:10:39] **Carol:** I don't know, two months now, just because I've wanted time away and I've wanted to be able to get everything handled without a lot of stress, but the itch is back. So like today when I was just like reading through what you had sent over, you know, just go with a bun, I was like, oh, I'm so eager to get back in code.

[00:10:56] **Adam:** hmm. Mm hmm.

[00:10:57] **Carol:** it. I miss technology.

[00:10:59] **Adam:** Oh yeah. Yeah. I've been doing all this compliance work for so long that like any opportunity that I get to do anything technical is like super exciting.

[00:11:07] **Carol:** Right.

[00:11:08] **Adam:** I spent. Like an hour after I was done with work yesterday, messing with Docker stuff, right? So I, I came up with this idea of like a way that we could improve our build times for our Docker containers, like our, our CFML monolith.

[00:11:22] **Adam:** It also includes a whole bunch of JavaScript, right? Client side JavaScript bundles get built and put in the right places and stuff. And. I just thought of like, oh, I wonder if we did this, if it would, you know, reduce the number of steps that have to be built, you know, like split out, right? Like the CFML code is on one side over here and the JavaScript code is on the other side and only update the one that needs to be updated.

[00:11:44] **Carol:** And nothing else matters, right? Like it's not been touched. Don't touch it. Yeah.

[00:11:49] **Adam:** and yeah, it's just like, it's so easy to get sucked in now. Cause I'm, I'm on, I'm kind of starved for, for tech to

[00:11:56] **Carol:** Yeah. Yep.

[00:11:58] **Adam:** so super excited about it.

## [00:12:00] Bun

[00:12:00] **Adam:** So yeah, when I saw like bun dropped, so if you're not familiar, bun is this, it's been around for a while. Like people have been aware that it was a thing and that, this small team had been working on.

[00:12:11] **Adam:** and. At least in my own personal awareness, it was just like a node replacement, right? So it was a new runtime that you could use to run JavaScript code, like server side or scripts or whatever, and they were trying to make it faster than node. I was like, okay, that sounds cool. You know, when it launches, I'll check it out.

[00:12:29] **Adam:** And then it launched, and the... I don't know how much of this was public before they went 1. 0, but it turns out that in addition to being a node runtime, it's also a package manager. So it replaces NPM. It's a bundler. So, you know, you don't have to do, you know, if it's, if you're using something with Grunt or Browserify or Webpack or, you know, like Snowpack, any of these things, it replaces all those, it's built in.

[00:12:54] **Adam:** what are some of the other things that it does? And I pull up their blog posts cause it's crazy. It's

[00:12:59] **Carol:** Yeah. That's what I was looking at. Like.

[00:13:01] **Adam:** community tools. It all just replaces all of them.

[00:13:04] **Carol:** Yeah, like, the testing framework of everything, right? Like, it's, if I'm understanding it right, like, it's, you don't have to use Jest, right? Like, it just works. So.

[00:13:15] **Adam:** and it'll, it'll, transpile your TypeScript. I think it can, I don't want to, I don't want to give false information, but I'm pretty sure I saw somewhere that it will just run TypeScript, right? You don't have to say. You don't have to have a transpiling step. You just say, okay, here's my code and it's TypeScript and it runs it, which

[00:13:35] **Carol:** Yep.

[00:13:35] **Adam:** super dope.

[00:13:37] **Carol:** yeah, I didn't really know exactly what was going on with it, but it was like, oh, but you can still keep your TypeScript files for type, like, checking, but it's almost as if it's not really needed. So I'm curious to see how it works.

[00:13:52] **Adam:** And speed is a huge thing. Like everything that they talk about, it's like, okay, not only does it do this, but it does it faster than everything else that's currently available. It's a, yes, it's a package manager, but it's a package manager. That's faster than Yarn, faster than NPM. You know, it's faster TypeScript compilation.

[00:14:08] **Adam:** It's faster testing. oh, and this is another thing that I'm super excited about because this is, I mentioned this I think in a, a recent episode that I was on, how, you know, like working with TypeScript and how there's like, TypeScript and CommonJS, I'm sorry, TypeScript and not TypeScript are sort of two things and then you've got like CommonJS versus ESM, right, the import versus require thing.

[00:14:30] **Adam:** and that's another thing that Bun is just like, nah, we'll take care of it, don't worry about it, just

[00:14:34] **Carol:** We'll handle it.

[00:14:35] **Adam:** you want, and we'll make it work.

[00:14:37] **Carol:** That's so nuts.

[00:14:38] **Adam:** exactly what you want from a tool, so like, I'm super excited about this, I will say. I, so, I did have, my hype meter went so high that I was like, screw it.

[00:14:48] **Adam:** I'm, I'm trying it, right. I'm gonna, just

[00:14:51] **Carol:** Today, we're just putting it in here.

[00:14:53] **Adam:** I did, I was like, you know, I'm not telling anybody. I'm just going to go, you know, create a branch and try to swap in bun instead of our bundler, bun instead of our package manager, bun for this and that. And it ran and it was fast and it created our bundles and the bundles didn't work.

[00:15:11] **Adam:** So, oh man, so, you know, I don't know if it's a specific, something specific about the way that we wrote the code or if it's like just this one library that I ran into an issue with this incompatible... Which is moment. js, you know, you probably are familiar with that one,

[00:15:25] **Carol:** Yeah. Yeah. The time. Yeah. Yep.

[00:15:29] **Adam:** is generally regarded as not what you should be using anymore, but this is old code, and it's still working, and

[00:15:34] **Carol:** It still exists. Yeah, don't change it until you have to sometimes. I mean, and we are saying like, this has only been dropped for five days. Like, I know you said it just came out, but I mean, I think it came out on the 8th, right? And the 13th. So, I mean, it's only five days out there.

[00:15:49] **Adam:** mm hmm, yeah, I mean, it's, it's, they've been working on it, I think, for a year or two, but, but, yeah, they've declared it as 1. 0 and production ready. As of just a couple of days ago,

[00:16:00] **Carol:** Yeah. Yeah.

[00:16:01] **Adam:** it's got, I mean, and it's faster. I should also mention it's somewhat faster than like ESBuild, too. That's where, so that's what we're currently using for our bundling.

[00:16:11] **Adam:** we, we switched from Browserify to ESBuild. I don't know, you'll have to go back in the, the podcast catalog because I'm sure I mentioned it then, too.

[00:16:19] **Carol:** several times. Yeah.

[00:16:21] **Adam:** and so, yeah, let's see what else. Oh, and they have,

[00:16:24] **Carol:** I am

[00:16:25] **Adam:** go ahead.

[00:16:26] **Carol:** now just gonna say I'm super excited It's about the testing side of it because I remember running jest and it would just it seems so slow And it seemed like it would take forever and I didn't understand why it would check a file and then check a file again I'm like, why does it feel like there's just redundancy here?

[00:16:41] **Carol:** I don't maybe we had things wrong or whatever But when I'm reading through their blog posts, it's like oh When you run Jest, you know, your code can be parsed three times by various tools and, you know, all your duct tapes and plugins, like things just, you know, aren't very easy to figure out what's going on and they get rid of that.

[00:16:59] **Carol:** So I'm like, woohoo.

[00:17:01] **Adam:** That was always a pain point as well with the, with the Jest tool chain, right? So if you're using like TypeScript and if you're bundling with Webpack, then there's like ways to hook that in to Jest, so that you're using, you know, TypeScript and, and Webpack to run your tests that slows the tests down.

[00:17:20] **Adam:** But then you have. in theory, identical context for running your test and running the application. Or you can, you know, go other ways that'll keep things faster, but then you, are, are sort of in slightly different sandboxes, right? So production wouldn't match where you're running your tests identically because instead of Webpack you're using ESBuild or, you know, whatever.

[00:17:45] **Adam:** and yeah, that was always a pain point for me with Jest. Again, it's just like, it makes so much sense for these tools to be integrated. Like what other language other than JavaScript, if we just set JavaScript off to the side for a minute, what other language doesn't have package manager built in, doesn't have test runner built in, doesn't have, I mean, if I think bundling is sort of its own thing because that's specific to the web and JavaScript, but like all these other things it's baked in.

[00:18:13] **Adam:** And the only reason that it's, not. I don't know, that's not the only reason it's not baked in with Node, but like, I think, early on Node, they were like, this is, look, it's possible, we made it work, hooray, and, and the whole, like, ecosystem is evolving now from, like, look what we've managed to scrabble together to, like, something with actual sophistication and intentional design and, you know, trying to gain those benefits of, doing it the same way.

[00:18:42] **Adam:** Right, run your tests the same way that you build the bundles, the same way that you run the code locally, right, like all the same vertical stack, just makes so much sense. So I'm, let's, let's call it, I'm optimistic about BUN, right, like I'm, I'm hoping that it, I'm, I'm sure that there's some growing pains, right, they're 1.

[00:19:02] **Adam:** 0, I'm sure they have a lot of attention, a lot of issues to deal with, I did file, an issue on there. GitHub repository for the thing in my bundle that wasn't working. No response yet, but you know, it's only been a couple of days.

[00:19:14] **Carol:** Yes. And they've only been out a couple of days, right? So, I mean, like, and I'm glad that you're using it and you're taking the time to file those so they can get things resolved. Because that's what's great about community support.

[00:19:26] **Carol:** For sure. So, Oh, I was going to say, you said you already kind of jumped in and was like, Oh, I'm just going to add this to a branch and see if it works. But when you are thinking of adding stuff like this to your project, like, what are your thoughts? Like, how do you go through that process of being like, okay, now's the time I want to do it.

[00:19:43] **Carol:** Is it just because, Oh man, Adam's a fanboy. So Adam's going to do it today. Or is it, do you actually look at, okay, here's how I think that it can improve our application and improve the process.

[00:19:54] **Adam:** That is a really good question, and the answer is, it depends. so, you know, like, with bun, initially, it's, for me, I guess, I guess it kind of depends on a couple of things, so. If it can be just a drop in replacement, like if I can just say like, you know, here's how you install bun, it's a curl command for your system and then it's installed and you just change from, right, instead of npmci, you're doing bun install, and that installs your stuff, and then other than that, you would do like npm, if previously you would do npm run build, then now you do bun run build, right?

[00:20:28] **Adam:** You would Just replace that thing. And if it would be that simple for my entire team to, to make the switch, then I'll just see if I can kind of, what's the, the word for a, like a startup? Oh, stealth mode. Right. I'll go stealth mode. I'll spend an hour or two on it, see if I can make it work. and, and if I can, then I'll be like, hey, look guys, here's a thing.

[00:20:48] **Adam:** and it, it, that's what I did with ESBuild. I was like, here's the thing, you, absolutely nothing changes for you except that, the builds are faster now, right? Like I set it up so that, yeah, I was like, it's all the exact same commands, it's still npm install, it's still whatever, but then the builds use a different tool to build and they, they come out faster.

[00:21:06] **Adam:** and there's, they still work the same. and that was well received and that's fine. And that's kind of what I was trying to do with BUN until I ran into issues. And so I kind of had to set it aside. I've got my branch and, and you know, if, You know, if they do like a 1. 1 or if they reply to my, my issue or whatever, if I just decide to try it later and everything's fixed, then, then good.

[00:21:26] **Adam:** You know, I can try to pick up where my branch left off.

[00:21:29] **Carol:** Nice. So, it sounds like you take the initiative to go ahead and get it working since there's little,like, sacrifice from the team to make adjustments and to have to learn as much, like, In the startup phase of it.

[00:21:42] **Adam:** Yeah, it, it's, there's so many different like touch points, right? Like, so with bun, not only did my own excitement, you know, inspire me to spend some time trying it. I did also mention it to a couple of my coworkers. We have this one ancient JavaScript project. It's a React app, it's built into our CFML monolith, if it's just this like tiny little standalone app within our app.

[00:22:07] **Adam:** it's an image library, right, so you can go in there and you can view our existing images from S3 and you can add new ones. And it still works, but we can't compile it. You know, the, the tool chain has just rotted. You know, it got left neglected for so long that we, we cannot make changes. We cannot recompile it.

[00:22:24] **Adam:** We can't, it's just, it's there. And hopefully nobody needs to touch it because nothing's changing. and so, I, you know, I mentioned this, to one of my coworkers and he's like, ooh, I wonder if it can recompile the image library. So, you know, we tried that and it cannot.

[00:22:38] **Carol:** No. Darn.

[00:22:40] **Adam:** that thing is just too, too, too far gone.

[00:22:43] **Adam:** You know, instead of being mostly dead, it's completely dead.

[00:22:47] **Carol:** I think, so a lot of what I've touched and a lot of what I've worked on have parts like that, like we've had applications that are just pretty much dead, but I mean, I've definitely worked in several projects where there were pieces you knew. It was very fragile or it was completely outdated and it would remain outdated and nobody saw it enough to know that there was something that was not quite right, but you left it alone and you knew going forward it would be there redo or just move around it

[00:23:15] **Adam:** Right.

[00:23:15] **Carol:** those things tend to sit isolated.

## [00:23:19] Svelte Replatforming

[00:23:19] **Adam:** So that's, that's kind of how I think about something that would be mostly a drop in replacement for the team. And sort of the other side of that coin is like, okay, if this is something that I'm interested in and I think could potentially be good for my team, but let's just like, so let's just use Svelte as an example, right?

[00:23:39] **Adam:** So I'm interested in Svelte personally. I think that, it might be a good way for my team to. A good direction for my team to move in. And so what I, what I did ultimately do with them was, you know, sent them, this has a really good interactive tutorial for like, this is how you learn the language and it kind of walks you through with different, it's got a built in online REPL, R E P L, read, evaluate, print, which is if you just type node into your command line with no arguments after and you start it, that's what.

[00:24:10] **Adam:** That's what that is. It's a REPL, right? It starts it up and it's okay. Write some JavaScript code and it, so you type in code, it evaluates it, prints the result, and then waits for you to type in more code, right? That's what a REPL is. The, Svelte REPL is in the browser. It's kind of like a code sandbox or whatever, right?

[00:24:27] **Adam:** You type in code and it evaluates it online. but they, they built. That REPL into their tutorial. So you've, you've got the tutorial on one side of the screen and it's like explaining stuff to you, but then there's the code right there, built into the thing, and you can mess with it. You can see what it's doing.

[00:24:44] **Adam:** And it's, it gives you a prompt. Like here's a, here's an app in a, in a start state. And the, the prompt explains, you know, what you need to learn to figure out how to get it into the finish state. And then, you know, you do it there live to, to learn it instead of just reading. which is a pretty good thing.

[00:25:01] **Adam:** So I sent that to my team and I was like, here, you know, when you have some time, check this out, I'm interested in this. Do you think that you would be interested or willing to learn this? And they were, they, you know, they, they liked it better than React. You know, we, we've gotten to the point as a team where we are competent with React, but we don't get to live in React all day, every day.

[00:25:22] **Adam:** And so as a result, it's very fatiguing to work on, you know, we, it's impossible to stay up to date with it. They're, they're changing React itself too frequently for us. and then the, the meta frameworks, things like Next. js that we try to use to encompass some of that complexity are abstracted away from our ourselves.

[00:25:42] **Adam:** It works, but then those frameworks themselves move too fast, right? I feel like there's a new version of Next. js like twice a year. That's, that's just, you know, what it feels like to me. It's probably more like once every three quarter year or something like that, but still just,

[00:25:57] **Carol:** But that's, that's a learning curve that you have to to take into account when you're on a small team and you're all having to relearn things.

[00:26:05] **Adam:** right. And we have, you know, we don't just have one app. We have probably a collection of like 20 apps that together make up our product, right? And so we've got the, like the image library thing, right? That's a good example of like, it worked. And so there was no need to go touch it for years and years and years and years.

[00:26:23] **Adam:** And now we try to go back and it's like, sorry, you're SOL. You're on, you want what? You want Webpack version one dot what? No. yeah, and all the, you know, just stuff stops working together when it's that old, so you kind of have to keep it up to date. And so that's something that goes into my decision about like what I'm gonna bring to the team and when I'm gonna bring it in and how I'm gonna bring it in.

[00:26:47] **Adam:** So, for me, like kind of continuing on the thread of like, okay, if I want to... Bring in Svelte and make that sort of like, a couple of episodes back, we were talking about how I would like to, strangle a pattern. I don't, I guess that you weren't on that episode. I'm sorry, Carol, but, I don't know if you listened to the episodes.

[00:27:05] **Adam:** the, talked about using a strangler pattern to sort of replatform,

[00:27:09] **Carol:** Oh, I think I was on this one.

[00:27:11] **Adam:** were you, okay,

[00:27:12] **Carol:** Maybe. Or we've talked about it another

[00:27:14] **Adam:** talked about it in the past, but this is like, just within the last couple of weeks, I don't

[00:27:17] **Carol:** Okay, then maybe not. Yeah, I was on that one then. Okay.

[00:27:20] **Adam:** the, but the, In order to do that, to use a strangler pattern to, sort of spin something up parallel to our existing application and then like port over one module at a time, or one screen at a time,

[00:27:33] **Carol:** Yeah. Yeah.

[00:27:34] **Adam:** before you can even take on that first bite of like, okay, I'm going to replace this screen, you kind of have to have some stuff figured out, right?

[00:27:41] **Adam:** You have to have the, the baseline application on its feet. You have to have like, how are we going to do session management and share sessions between... The app we're replacing and the app that's doing the replacing, and all that stuff. You have to figure all these things out and you also want to, especially when we're doing this whole like replatforming, it's like not only are we moving from CFML to a JavaScript thing, but like It's, it's an opportunity to try and get everybody on the same page a little bit better.

[00:28:10] **Adam:** Like, I feel like my team, we're all, we all developed the same style of writing our CFML code. And if we were to just be like, okay, it's a Wild West, everybody go write spelt code, it would be wildly different between the three of us.

[00:28:25] **Carol:** And good luck reading that, right?

[00:28:27] **Adam:** exactly. So my approach with this is going to be more like. I'm going to spend some time getting that baseline, you know, here's the application on its feet.

[00:28:36] **Adam:** It can run in parallel with our, our existing application. and you know, it'll probably be like URL based, right? If there, if there's a slash, you know, Adam or whatever it's going to be in the URL somewhere, then it'll route over to the new application. And, and then once that is on its feet, I will probably try to find like the smallest thing that is Well, the best balance of something that is small and easy to rewrite, but also has a good opportunity to write enough code to show like, this is how we should organize it.

[00:29:07] **Adam:** This is how we should think about

[00:29:09] **Carol:** right.

[00:29:09] **Adam:** how to write the code. And I want to, I want to kind of take all of that on, get that done, and then take like a day or maybe two days and just like, sort of like. Give, an onboarding as if they were new hires, right? Like

[00:29:22] **Carol:** Yeah,

[00:29:22] **Adam:** the new application. Here's where you go to write your controller logic.

[00:29:26] **Adam:** Here's where you go to write your CSS. Here's where you go to do this. And

[00:29:29] **Carol:** And here's the already created, like, template for how, you know, I think it should be working. Yeah,

[00:29:34] **Adam:** Yeah. And yeah, and that's the other thing too, like by, by starting by taking on some sort of a module or something. you know, whatever it is, if it's like, you know, four or five screens, that'll be enough to be like, okay, this is when you want to create a component that is reusable, but that's not as like broadly, you kind of have two different types of reusable components.

[00:29:55] **Adam:** You have like a button, which is going to be on almost every page, if not every page, right?

[00:30:00] **Carol:** submit.

[00:30:00] **Adam:** extremely reusable, a little versatile in the type of things that you want to send to it. And then on the other hand, you might have, you know, a user list or something, right? You're going to want that on more than one screen, but you're, it's not going to be on every screen.

[00:30:14] **Adam:** And so

[00:30:15] **Carol:** not going everywhere.

[00:30:16] **Adam:** Right. And, and so those are kind of two different things, right? You have like core components and then you have like a thing that I need for two or three screens that are all close together geographically in the application. And so, you know, you've got to figure out like where organizationally, where do those files belong?

[00:30:32] **Adam:** How do I reference them in the code? That sort of thing. So it's an opportunity to figure all that stuff out and then be like, and this is the right way to do it. Hooray!

[00:30:41] **Carol:** yep, yeah, you already have a good template, a good like way to go look at. Like that always makes me happy when I'm learning something new in an application and someone's like, hey, we're going to introduce this. Well, it's good that you already have working code using it. Because it's in an application I already understand.

[00:30:56] **Carol:** And did I understand the logic for us? And now you've just taken this new way of doing something and applied it to what I already knew. So I learned it so much faster that way.

[00:31:05] **Adam:** For sure. Does that answer your question?

[00:31:09] **Carol:** It does. It does. do you ever, so here's one thing I do, and I don't know if you ever do this. So I look at the shiny new thing. And because I have ADHD, I tend to jump to every shiny new thing that comes my way. And I commit about 5 percent to it and then I'm done and someone else should be responsible for it at that point.

[00:31:27] **Carol:** So, I will actually like put it on my list and then I'll wait like four or five days and if in four or five days, I'm still like, okay, I really think this is a good idea. That's when I start pursuing it. Like I don't jump on it just the first time I read about it. I'm like, okay. I'm not just going to throw it in here.

[00:31:44] **Carol:** I'm going to actually sit on it, look at a post it note for, you know, a week and make sure that throughout that week I see the use of it and I see how helpful it can be before I actually go, okay, let's just throw it in.

[00:31:55] **Adam:** Right. yeah, that's a good amount of self discipline. That's, I don't know if I do it. I certainly don't do it exactly that way. I think it ends up being very similar, right? Like I didn't, it wasn't the first time that I heard about Bun that I was like, oh, I gotta go try this. But, uh, you know, I waited until the hype kind of pushed me over the edge, right? That reminds me though, I want to say it's the band Jimmy Eat World, it might be, for all I know it could be, you know, Foo Fighters, right? But, like, somebody, I heard this from somebody that's in one of those, like, very famous bands, and they say that, yeah, yes, they write new songs all the time, but they never physically write them down.

[00:32:34] **Adam:** When they're working on new material, never write down the music, never write down tabs, never write down words, any of that, because they say, if I can't remember the song, it's not worth keeping it in our repertoire.

[00:32:45] **Carol:** See, yeah, I get that. That makes total sense to me.

## [00:32:48] Adam's Tandem Skydiving App Project

[00:32:48] **Adam:** So, we've, we've kind of been talking about side projects and stuff. I, I do have. I mean, I mentioned Svelte many times, in terms of like, you know, what I would like to bring into the company. And I mentioned at the top of the show that, I think I mentioned that I've been, in addition to writing this like name tag code and playing with bun, I've also, because I'm me, got other irons in the fire.

[00:33:10] **Adam:** I,

[00:33:11] **Carol:** outside of skydiving, and outside of woodworking, and raising some kids, and dogs, and yeah. You got another thing on your plate?

[00:33:20] **Adam:** yeah, apparently, so I mean, it's, it's inspired by something that I need, right? So, I don't really need to get into the details of everything about this particular application, but let's just say, you know, it's an application, sort of like a bespoke scheduling application that, that allows, people that want to book a Tandem Skydive and the people that can provide those Tandem Skydives, sort of like,

[00:33:41] **Carol:** Link up! Yeah.

[00:33:44] **Adam:** say, okay, this is when I'm available and how many people I can take on any given day.

[00:33:47] **Adam:** And these are the people that, you know, they want to find the availability and sign up for a slot, right? Anyway, so that's the, the impetus for the thing. And so it's an opportunity for me to learn some new technology stuff and try it out and say like, okay, Is this something that I want to, kind of push into the company and say, like, I'm not forcing you, but like, I would like to go down this path, right?

[00:34:10] **Adam:** Here are some tools that I've been playing with on the side. And I like, in theory, hypothetically, if I, if it goes well, I've been playing with these things on the side and I like them and I think that they could do well for us. Here's, you know, the, the intro. What do you think? and so, that's what I've been messing with on the side for them.

[00:34:25] **Adam:** So, it's a, it's a SvelteKit thing, and the, the thing that I'm talking about is a UI library built specifically for Svelte, that uses Tailwind for styling, and it's a component library. It's called Skeleton. The website is skeleton. dev. and like I said, it's basically a set of Svelte components that are built using Tailwind and very specific, like sort of, they've done a lot of research in like what truly is the best way to build a design system that is themable, customizable, and overridable.

[00:35:01] **Adam:** But at the same time, very cohesive and, you know, like works well together and everything I've seen about it looks amazing. So I'm super excited to like play with it and see if it lives up to the, the marketing material. Right. I, I, the little bit that I have used Tailwind, I've really enjoyed it. I feel like it's, it's a, it's like bumper bullet for me, right?

[00:35:23] **Adam:** Tailwind and Bootstrap and stuff too, like, you know, they, if you just open the box and just use the tools that are in the box. You're going to get a decent design and

[00:35:33] **Carol:** gonna be okay.

[00:35:34] **Adam:** right, and then, you know, if you get really good at it and it goes for everything, it's, it's, you know, from bootstrap to knockout, right?

[00:35:41] **Adam:** Like if you, you get really good at it, you can use that as your building blocks and then you can add flourishes and customize things to make it your own. And so you, not everybody that lands on it with any sort of background is going to go, Oh, this is a bootstrap site. so

[00:35:57] **Carol:** Man, I didn't think I would ever hear knockout again. Like, I haven't used that in a long time.

[00:36:02] **Adam:** yeah.

[00:36:03] **Carol:** Yeah,

[00:36:04] **Adam:** That was, that was the paid one, right? Like it was a few years before Bootstrap came out. It was

[00:36:08] **Carol:** yeah, knockout. Mm

[00:36:09] **Adam:** design

[00:36:10] **Carol:** hmm. Yeah. Yep. Yeah. Whoo.

[00:36:13] **Adam:** Yeah. I never used it 'cause I, I never, I couldn't afford it and none of the cons companies that, I was working for used it. So I was just aware of it, but never used it.

[00:36:21] **Carol:** Yeah So with your idea, this isn't really the tech questions more of the application question So is your thought that each of the instructors would then purchase a subscription to this and then they would be able to customize? their own or would you go to like a skydiving company like a Like, you're skydiving school and they would be the ones that use this software.

[00:36:44] **Adam:** So the way that I'm approaching this is more, like, think of it as if like your spouse needed something and you're like, oh, I can write an app that does that. You're not gonna charge them for it. Right? Like, you're just gonna build a thing and like, here, I made your life better. Right. and that's kind of where I'm coming at it from.

[00:37:00] **Adam:** And, and, I will, if it works and we like it as a, as a team of people working together, then great. And if it starts to cost me more than a few dollars a month, then I'll be like, hi, excuse me, I've been funding this out of my own pocket. I would like the, if you would please give me 20 a month to just continue to host this and we'll keep using it to cover my costs, that would be great.

[00:37:20] **Adam:** and that's fine. I'm not trying to like turn this into a product and go sell it or anything like that right now.

[00:37:24] **Carol:** Okay, that's what I was wondering. Like, if you were thinking if this actually goes good, so you're basically going to use like your, the place you skydive with currently, if you're going to use them as like your guinea pig to the application, and if it goes well, then you could market it to other, other schools.

[00:37:40] **Carol:** Skydiving schools. I don't know what they're called. Teams, boards, peoples. Yeah.

[00:37:46] **Adam:** whatever. that's not out of the question, but it is not where I'm approaching it from. Like, I just want to build something useful for now and use it as an opportunity to learn.

[00:37:55] **Carol:** Yeah.

[00:37:56] **Adam:** you know, one day, if it's, if it becomes useful and I can figure out a way to, you know, turn it into a reusable product, then sure.

[00:38:04] **Carol:** Yeah. It seems like a good idea for more than just skydiving though. Like, I'm thinking of, I need someone to come to my house and do plumbing. So where's a plumber at? Who has availability tomorrow? So if you could throw in, you know, your hours.

[00:38:20] **Adam:** What is that? I've never used it, but, it's like somebody's list, Angie's list or something.

[00:38:24] **Carol:** Angie's list. Yeah.

[00:38:26] **Adam:** But that's more about just like, I, I vouch for this plumber,

[00:38:29] **Carol:** yep. That's it. Right. It's not an actual scheduling of, I really need someone to come to my house between the hours of noon and five and who's available for it.

[00:38:39] **Adam:** so, okay. Take your, take your plumber example. Now, imagine, it's people that really enjoy doing plumbing and they do it not for free, but for cost. Okay. And in, and they're kind of volunteering their time to work with this plumbing company and the plumbing company matches them up with people who need plumbing done.

[00:39:04] **Adam:** but. Each, each plumber is like, you know, I'm not, I'm not working all day, every day, Saturday and Sunday. I'm only, you know, okay, this upcoming Saturday, I'll do the afternoon, but not in the morning, Sunday I'll do all day, the following

[00:39:15] **Carol:** exactly.

[00:39:16] **Adam:** at all, right?

[00:39:18] **Carol:** Yeah,

[00:39:18] **Adam:** idea is like, each plumber can go in and say, okay, this is my availability.

[00:39:23] **Carol:** I love that.

[00:39:24] **Adam:** and then that, that kind of gets aggregated. So it's like, okay, well, Adam can do some plumbing in the morning on Saturday and Carol can do some plumbing in the afternoon on Sunday.

[00:39:33] **Carol:** And the job's done.

[00:39:34] **Adam:** Right, well, and then that opens it up on the calendar, right? So then the person coming in, they don't know that there's nine different plumbers trying to, uh, cooperate here.

[00:39:43] **Adam:** They're just like, I, my sink's busted and I want somebody to come out on Saturday morning. So, yeah, that's, that's the idea.

[00:39:50] **Carol:** Yeah, I like that. I think it's a really cool idea. That's why when you were saying it, I was like, I feel like if this does well, it could be more than just a skydiving. Like, this could be used in multiple areas for people.

[00:40:03] **Adam:** You just gotta figure out, like, what is the, how do you describe this in a way that makes it, you know, like, not industry specific, right? It's like, it's, availability, aggregation, and registration, right? Like,

[00:40:16] **Carol:** It's, it's like Match.com but not for relationships.

[00:40:22] **Adam:** Match.com for plumbers and people with broken sinks.

[00:40:26] **Carol:** Yeah, or Power Rangers down the toilet.

[00:40:28] **Adam:** Yeah, oh my god.

[00:40:30] **Carol:** Right? The things kids will flush.

[00:40:34] **Adam:** Speaking of kids putting things in places that they shouldn't go, at my last house, I'm pretty sure... In the H V A C, there are still children's toys. So, you know, the more modern housing instead of the, the vents for the, the air conditioning and heating being like on the wall. That's what I remember from growing up.

[00:40:52] **Adam:** They're built into the floor, right? So you've got the carpet on the floor and then there's just like metal grate

[00:40:56] **Carol:** Oh, yeah. Yeah.

[00:40:58] **Adam:** and you can just like pick up the metal rate and move it. There's, it's not screwed down or anything, and my toddlers would figure that out. And they're like, oh, look, it's a place that I can put things and they disappear, right?

[00:41:09] **Adam:** So they drop in all these little toys and, you know, you try to teach them not to do that, whatever. But, you know, I got at one point I was up like to my shoulder with my arm down in the floor, you know, it goes around a corner there, and I'm like pulling out, you know, Power Rangers and little pieces of like, toy food and, you know, all this other stuff.

[00:41:28] **Carol:** Or pennies.

[00:41:30] **Adam:** Yeah, yeah,

[00:41:31] **Carol:** Coins. Yep. Yep. Oh, yeah. Kids are fun. They're so much fun.

[00:41:35] **Adam:** for a

[00:41:36] **Carol:** I think you're, will they leave you? And then they become not so fun anymore.

[00:41:42] **Adam:** Then they gotta come visit.

[00:41:44] **Carol:** Yeah, yeah, they're, my boys are coming out for Christmas, so that'll be the first time I'm gonna see them for several months. It's gonna be different.

[00:41:51] **Adam:** that'll be a nice Christmas present.

[00:41:53] **Carol:** Yeah, yeah, we're excited for that. But yeah, I really think your side project sounds cool and I hope you enjoy learning. You said skeleton, right? And yeah, that sounds cool.

[00:42:03] **Carol:** I hadn't pulled it up and I'm gonna walk through the demo because I really want to kind of see their learning stuff on the side, see what it looks like, understand it better.

[00:42:12] **Adam:** right,

## [00:42:13] Patreon

[00:42:13] **Adam:** Okay, well then, that's gonna do it for us. So this episode of Working Closed is brought to you by your stuff. you, you love to have it until it's gone, and then you have to wait another 18 days to get it. So don't take it for, for granted. Thank you, thank your stuff for being yours and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:42:37] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. Carol and I are going to stick around and do some sort of an after show. We don't even know yet what we're going to talk about, but we'll figure it out.

[00:42:51] **Carol:** It's a surprise. Heh

[00:42:53] **Adam:** and if you want to find out what that is, you're going to have to become a patron. You can do that by going to patreon.com/workingcodepod. we even now added a, a free trial. I believe you get four weeks for free. And then, from there, if you want to keep listening to our, babbling after the outro plays, then you're going to have to pony up a whole 4 a month.

[00:43:14] **Carol:** woo.

[00:43:14] **Adam:** but you know what? I'm super grateful for all of our patrons, something that we've been wanting for years and years. Has it really been more than, more

[00:43:22] **Carol:** It has been. It's been more than two years officially,

[00:43:25] **Adam:** Yeah, I mean, I guess a hundred and whatever shows, one a week. Yeah, two years and change. anyway, so for multiple years now we have wanted transcripts and only recently we started adding them

[00:43:36] **Carol:** Thank you guys!

[00:43:37] **Adam:** only possible thanks to the support of our patrons.

[00:43:39] **Adam:** And so if you want to continue the show growing and evolving and getting better for everybody involved, we would really appreciate your support.

## [00:43:47] Thanks for Listening!

[00:43:47] **Adam:** That's going to do it for us this week. We'll catch you next week. And until then,

[00:43:51] **Carol:** Your heart matters, guys. Even the ones of you who write image libraries and never maintain them and now you can't touch them.

[00:44:00] **Adam:** Dead code on the vine.
