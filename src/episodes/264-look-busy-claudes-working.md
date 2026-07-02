---
title: "264: Look Busy, Claude's Working"
description: "The promise was that AI would take the grunt work off your plate and leave you the good stuff. This week is the part no one advertised."
date: 2026-06-18
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/264-look-busy-claudes-working/id1544142288?i=1000773250507"></iframe>

The promise was that AI would take the grunt work off your plate and leave you the good stuff. This week is the part no one advertised: you got into this to make things — but what comes instead is the restless guilt of sitting there with nothing to do while the agent works, and the slow realization that when it finishes, the job left for you is mostly reviewing.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [xkcd: "Compiling"](https://xkcd.com/303/)

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/264-look-busy-claudes-working.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** here's the reality, is if I wasn't on video, none of this would even cross my mind because no one would be watching me.

[00:00:05] It's like the old xkcd comic where the people are fencing in the hallway, and it's like, "Get back to work," and they're like, "We're waiting for the compiler to run," you know?

[00:00:12] **Carol:** Mm-hmm.

[00:00:12] **Ben:** and now, like, Claude's the new compiler

## [00:00:34] Intro

[00:00:34] **Carol:** Okay, here we go. It's show number 264, and today we're gonna talk about data, metrics, and wage

## [00:00:41] Carol's Triumph

[00:00:48] **Carol:** theft. first, as always, I'm gonna kick us off with triumphs and fails 'cause, well, Adam's out to not tell me differently, so I'll do what I want.I'm gonna go with a big giant triumph because guess what? memory leak who? don't even think you exist anymore. Yeah. And I might have solved three in a row. Well, technically one was a hot thread, but we'll say same thing. we've had some issues going on with some code that had been written a little, a little while back, and finally had gotten turned on in prod and realized that we have some templates that whenever these templates get processed, they are just hanging up so, so long. So the first issue is CPU. out, if you don't write regex correctly and you're trying to loop over a giant HTML document that is reply and reply and reply to emails that includes all the attachments, your regex may take two hours to process, and there is no kill switch on that once that thread's kicked off in .NET. So I, grabbed a memory dump from production to see what was going on with a couple of our apps and found that if I use WinDbg, which is just like a, a memory dump tool, and throw in extension for it, it very quickly can link you to exactly where your hot threads are and point you back into the exact code where it's breaking. So as soon as I was able to get into the code that was causing the issue, I popped that line into AI, and within three commands, Claude was like, "Ding, ding, ding. Regex is your problem." So, I got the regex fixed and then checked out main again, wrote, a red test to confirm that it would take over three seconds to kind of process, and then wrote, a passing test once I put my code in, and then processed in milliseconds, and the PDF generates, and everything looks as it should. It really is important that you understand how trailing white space works and in regex, it could go badly, like two hours of processing time badly

[00:02:45] **Ben:** Yeah, I think that's, often referred to as catastrophic backtracking, which is actually, a malicious vector. Like if people figure out that their inputs can be processed as patterns or that, I guess, patterns are used to process their inputs, you can formulate your inputs such to trigger the catastrophic backtracking and do exactly what you're talking, drain all the CPU and everything

[00:03:08] **Carol:** Yep. It's, it's funny how Claude liked to mentor me on that and explained why it was very important we didn't do it again. So I was like, "I had no idea that this was exposure." So I've learned, and now we'll do better. But I was just happy with the, the red/blue testing up front that I wrote to confirm it was able to correct a code, and I was able to actually pull the exact HTML that was failing out of the memory dump and test that exact HTML to, to prove that it's good now. And then the second one was actually a memory leak, where we had an issue with Serilog being injected but never disposed of. So there were like 85,000 references to Serilog that turns out it has no reference to the app anymore because it's just consuming memory. So got that resolved. two big wins and a few more, and I'm very proud of myself that they were solved in hours using, you know, the tooling that we have available now versus days of digging and trying to piece it together

[00:04:08] **Tim:** Oh

[00:04:10] **Ben:** That, that I feel like is the one story in ColdFusion that I feel like has never been terribly good, is that, that like

[00:04:18] **Tim:** story?

[00:04:19] **Ben:** just it's that edge case that, where you have something like a memory leak, and there's really... Even when you're looking at something like Fusion Reactor, which has kind of been the best in breed class debugger for ColdFusion or the JVM I guess in general, the memory leaks are just hard to track down.

[00:04:37] And, and maybe it's just that I never learned how to use the tooling, but, we had cases at InVision where the DevOps people never even told us that this was happening. They would just go and programmatically set up these cron jobs that would restart the ColdFusion servers like twice a day. And I'd be like, "Why didn't you tell anybody that that was happening?"

[00:04:56] And they're like, "Eh, it was just easier to do this."

[00:04:59] **Carol:** I think, I think most of us have that story in our background somewhere, where the app will spin up at, like, 10:00 AM. We know by 10:00 AM printing is gonna take us down, so at 9:50, go ahead and do a quick service restart and just, you know, let it start fresh when that process kicks off. all been there

[00:05:19] **Tim:** I, I love the fact that every time, every single time you go to, Fusion Reactor, my face is on the front page. I put a, I

[00:05:25] **Ben:** Oh, that's right. You get the testimonial

[00:05:27] **Tim:** of me.

[00:05:30] Well, that was me. Tim, we're still on the show. How about you

## [00:05:33] Tim's Fail

[00:05:33] **Carol:** go?

[00:05:34] **Tim:** So I got a big old fail. So I guess about 10... More than 10 days ago, I'm sitting here, I, I built these deployment pipelines with GitHub actions and everything, and got them all installed on the servers. And yeah, and then I'll, I'm working, it's like 10:00 AM, and then 10:15 AM nothing, none of my s- works.

[00:05:57] And I go to log into GitHub, and I'm suspended. my

[00:06:01] **Carol:** What?

[00:06:01] **Ben:** What?

[00:06:02] **Tim:** my entire organization, not... It, it was a separate one that from my main company is just for, our payment side. GitHub has been completely locked down, and I can't add anything, I can't log... I can't even log in to log a ticket. They never told me what I did.

[00:06:19] It just, it's a very broad, "You were, you did something against the terms and services." And I don't know, I don't know what it was. It's

[00:06:28] **Ben:** That's crazy

[00:06:28] **Tim:** it's either spam or I, I was like reading what could do it. It's like you like going, going past the, The usages for the... Because it was using

[00:06:39] **Carol:** minute usage?

[00:06:40] **Tim:** line, but Claude was doing it and

[00:06:42] **Carol:** Mm-hmm. Mm-hmm

[00:06:42] **Tim:** And I saw, I saw months ago, like a couple times where it said, you know, you know, it told me to slow my roll, so I did, and I told it to...

[00:06:50] And I haven't-- But I never got an email, I never got a warning. I've put in a ticket and it's been, 10 business days, so more than two weeks, they have not responded, said a word. I have no idea. And it's like, I gotta work. what, what we did to work around is, is we created in a different org, created, a different user for me, copied all of our GitHub repositories to the other org, and then we,

[00:07:18] **Carol:** Holy moly

[00:07:19] **Tim:** do the runners, so we just have a script on each server that every five minutes does a Git pull and then I, I'm able to commit to master. But yeah.

[00:07:29] **Ben:** That's crazy

[00:07:31] **Carol:** Oh my gosh

[00:07:32] **Tim:** I have no idea if I'm ever gonna get that account. And, and that's-- But it's also my personal account, so all the personal things that I've done, it's all... I can't do anything to it anymore

[00:07:43] **Carol:** That is

[00:07:44] **Ben:** That's... Can you do like a public, decree of dissatisfaction?

[00:07:49] **Tim:** you know, Claude and my wife both said, "You need to go on Twitter or X or whatever it's called these days and, like, start complaining." And I'm like, I don't have the energy. I've got to work around already." I'm just mad at them. It's like you build-- You, you know, you start giving people tools to do AI stuff, that's what it is, if it's the fact that I was just going too fast for it.I just can't, I can't for the life of me figure out why I got the strike against me

[00:08:18] **Carol:** I mean,

[00:08:18] **Ben:** Yeah

[00:08:19] **Carol:** your, actions you created were doing something bad

[00:08:22] **Tim:** It was

[00:08:22] **Carol:** and you didn't know it. Oh

[00:08:24] **Tim:** Stu and his pulls, right? So I'm using their actions. It was all their stuff. So I, I do know that my username was being used on the server as well, and while we were wor- I wonder if the fact that I'm working locally on my machine and then someone else is working on another machine, they're actually using my credentials to do the pull down you get paid per...

[00:08:43] You know, you pay per seat. So, but I didn't even think about that, that the, the runners were running under my account while at the same time, at the same time my account locally and I'm... I was hitting it pretty hard. But yeah, I don't, I don't... No

[00:08:59] **Ben:** still, they should... I mean, it's not like you're a rando dude. You're running a company on GitHub. They should at least give you some insight. That's insane

[00:09:09] **Tim:** Or some-- And I email every day to the ticket. So you can't even log in to create a ticket. So you have to go to s-- There's a special way, and I was so angry. I'm sitting here, I'm, I have... Like, people are begging me, "I need this. I need this." I'm trying to... so I'm trying to, like, find a way to get around it and, like, I can't actually do anything. I'm trying to get in to, to log a ticket And they have the weirdest CAPTCHA. It's not a normal CAPTCHA. It's like, it's a s- it's a grid with the little train on a train track, and you gotta move it.

[00:09:39] **Carol:** What?

[00:09:40] **Tim:** It was-- I-- Took me five minutes just to figure out what I'm supposed to do to solve the puzzle, I finally figured out don't give you just one puzzle, they give you Five

[00:09:49] **Carol:** Oh my

[00:09:50] **Ben:** Oh my goodness.

[00:09:51] **Tim:** to log in

[00:09:52] **Ben:** You really got on someone's bad side

[00:09:54] **Tim:** Oh.

[00:09:55] **Carol:** the GitHub gods angry

[00:09:57] **Tim:** was so mad. So

[00:10:00] **Ben:** Have you, have you ever gotten that, CAPTCHA where you have to get like an image of a frog and then like rotate it so it's... They'd be like, "Have the frog stare at the car," and then you gotta like rotate it so that it looks like it's staring at the car, where you gotta like do things where you like bring it into a certain angle?

[00:10:16] they also have another one where you spin the sheep a certain way

[00:10:18] Yeah, yeah

[00:10:20] **Carol:** The ones I hate are when it's like four images and it's like pick out the starry cluster, and I'm like, "I don't even know what you're talking about, and I'm gonna have to go Google these words anyways." Like, how do I know which one is a starry cluster?

[00:10:35] **Tim:** Yeah. And I, and I wonder 'cause, you know, they use those things to build heuristics

[00:10:39] for the AI, and I wonder what problem they're trying to solve for the train track thing

[00:10:43] **Ben:** Right? Yo, do you not have a legal eagle at, uh, the company that could maybe exert some pressure?

[00:10:50] **Tim:** We do, but guys, they take forever. I mean, by the time, by the time they actually get around to my request, it, it'll be like four months from now and Go- GitHub will probably have fixed it already. So

[00:11:03] **Ben:** But that's a, that... I'd be furious. That's, that's awful

[00:11:06] **Tim:** Yeah,

[00:11:07] I, I am... I was furious, trust me. was not a good person to report to or to deal with that day. Nobody liked me that day. I was taking it out on everyone, and I feel... I apologized profusely afterward, but yeah, you did not want to be in a meeting with me that day. So

[00:11:25] **Carol:** I'm glad you have a workaround

[00:11:27] **Tim:** Yeah, me too. I just hope GitHub isn't listening to, to know that... 'cause technically creating another account is against the terms of services.

[00:11:36] **Carol:** If you've been suspended?

[00:11:38] **Tim:** So So, technically I'm just supposed to sit here and not be able to do anything with my code on GitHub till they deem to get around to me, which I have no confidence they, they will.

[00:11:49] **Ben:** That is just insane

[00:11:50] **Tim:** They're supposed to get back to you in five business days

[00:11:53] **Carol:** Yeah

[00:11:54] **Tim:** the reason, and they have not. So

[00:11:58] **Carol:** Hmm.

[00:11:59] **Ben:** Awful

[00:11:59] **Tim:** that's me. I don't want to bring it all up again. I got to... I need to go to counseling, so Adam is out. Ben, what you up

## [00:12:06] Ben's Triumph

[00:12:06] **Tim:** to?

[00:12:08] **Ben:** I'm gonna go with a simple triumph, which is that I have been refactoring the code on my blog, and, it just feels joyous to do some typing and to do some refactoring, which, I mean, if you squint hard enough, it's almost just busywork. I'm kinda just moving files around and trying to find better, folder structures and find out...

[00:12:31] A, a lot of times I'll create, say, a ColdFusion component and then put it in a, a utils directory or put it in some other directory, and I'm like, "This isn't really the right place for it," but I don't have... I don't care enough to worry about what it should be called or where it should be and what the name of it, why it violates, you know, other patterns.

[00:12:48] And so one of the things I've been doing as I'm refactoring the code is I'm just having Claude help me think through this. You know, like, what is it about this file? It doesn't feel right. I don't like the fact that it ends in the service suffix, and I... but it doesn't really act like the other services, but I also, you know, this and that.

[00:13:04] And Claude kind of tells me like, "Oh, you know, it really should be based on the actions that it's providing, and you should maybe roll it up into its own feature folder." And it,Like, none of it functionally changes the way the, the blog works, but I am hoping to lay some foundations for some future updates.

[00:13:23] But like I'm saying, like, really just my triumph is that I've had so much fun just typing with my fingers and thinking out problems and, like, reverting a little bit back to the way I used to feel like my days of programming were. And, I'm still using AI, like, I'm j-more as a conversational, foil.

[00:13:43] and then, like, if I wanna just move a whole bunch of files around to, like, different folder structures, that I feel like it can jam out that stuff really quickly and update all the references to the dot paths for the components and all that jazz. Like, that's the stuff. Like, that's the grunt, the gruntiest of the grunt work.

[00:13:58] Like, I don't, I don't wanna have to do that. That doesn't enhance the way I think about the world, so I'm more than happy to defer that.but one thing that's so interesting. So I'm trying not to go overboard with my CLAUDE.md file, which is like the Anthropic equivalent to the AGENTS.md file where you can kind of put directives that help guide the AI.

[00:14:21] And I feel like it, it just sticks to those things to a fault even when it's misunderstanding, I think, the intent that I was trying to include in the directives. And I don't know where that balancing line is. It's like if Claude makes a mistake and it's a judgment mistake- I wanna put something in the .md file that says, "Don't do this.

[00:14:46] Here's the reason why." But then if you don't, like, flesh out every edge case in that thought, it will stick so hard to it that if you try to purposefully violate that rule in some flavor or form, it will just constantly push back, "Oh, well, you're violating this rule and you're violating that rule." And I, I'm just...

[00:15:07] I don't know where the balancing act is between when it's helpful and when it's not helpful. Like, what I'm supposed to put in the CLAUDE.md file versus what I'm not supposed to put in the CLAUDE.md file. And like I, l- I, I know I'm just rambling here, but, but like part of me is, oh, well, I just wanna get to a point where Claude stops making mistakes for mundane tasks, and like maybe that's just not a reality.

[00:15:29] Like, I can't CLAUDE.md my way out of that kind of a situation.

[00:15:34] **Carol:** Definitely not for all of it. What kind of stuff do you have in your .md file that is so bound to exact instructions?

[00:15:41] **Ben:** It's not even like it's so bound. Okay, so one of the things I'm doing is I'm just rejiggering some of the folders for my components to kind of co-locate things that are of similar categories. Like, I have a models folder, which is more kind of low-level data access, and then I have a services folder, and that's more like high-level workflow orchestration stuff.

[00:16:05] And then I, and then I had for a while just a utils folder, which was like everything that doesn't kind of cleanly fit into models and services.

[00:16:13] **Carol:** We've all had those one day.

[00:16:14] **Ben:** yeah, exactly. So one of the things, for example, was a rate-limiting component where I can, you know, like using someone's IP address or using an email address or using a blog post ID, limit the number of things that can happen through a particular choke point in the application.

[00:16:31] And it starts to throw 429 rate-limiting errors. so as I'm doing... as I'm moving stuff around, I- Claude had gotten some directive into it that like, oh, things in the utils folder should be things that are application agnostic, and that, like, don't rely on data access. And the rate limiting doesn't actually rely on any data access.

[00:16:54] It's just an in-memory cache of basically counters. But it's not agnostic to the application because it has certain choke point identifiers like new comment, for example, or like contact form is application specific. But, like, it was so willing to die on the hill of, well, like, this doesn't use data access, ergo it's utility, not an application-specific concept.

[00:17:20] And every time I was like, "But it has application-specific terminology in it," and it'd be like, "Oh, but it doesn't do data access." And I'm like, "Yeah, I get that." Like, I get that we thought at, you know, one conversation yesterday this was an important facet on which we could do the litmus test for where does this thing live.

[00:17:38] But like, that, that doesn't apply to this kind of thing. And, you know, it- that's just like a silly example, but it's just... I, I, I can't imagine that people aren't just constantly f- stumbling over stuff like this. But I, I don't know. Maybe I care too much about where things are and why they're named certain

[00:17:55] things.

[00:17:56] **Carol:** And maybe it's the task that you're taking on. For me, I get stuck with the, you told me that document, or per, per our m- like, kn- knowledge or whatever," it'll be like, "We, we know that this application is no longer valid, that it's actually been sunset, and you should be going to this repo." And I'm like, "No, what I told you was that one day this will go away.

[00:18:19] We're running two versions of it, and not everything is cut over yet. So, any work has to be done in both." And no matter how many times I update the actual agent file, it still will go back and say, "But it's sunset." I'm like, "But it's not. It's not sunset yet." So one day I just deleted that whole section.

[00:18:38] I was like, "You're just gonna figure out the service every time you need to figure it out because I'm not telling you anymore."

[00:18:44] **Tim:** Yeah, sometimes you gotta do that. I've

[00:18:45] **Carol:** Mm-hmm.

[00:18:46] **Tim:** I, I've accidentally said something wrong and it keeps g- I'm like, "Delete that from your memory." does, so

[00:18:53] **Carol:** Mm-hmm.

[00:18:53] you mentioned, uh, kind of in the middle of it that the difference between the CLAUDE.md and the AGENTS.md file. found out that the majority of my like working team, so the team I do the mo-most work with, that those developers, they're all using Codex, which needs the AGENTS.md file. So every check-in I'm doing, I have Claude create the AGENTS.md file, and it literally has a line in there telling Claude or in CLAUDE.md that everything it needs to know is in the AGENTS.md file, and any other tooling behind it needs to use AGENTS.md as well. And that way my team doesn't get impacted by me checking in these massive CLAUDE.md files, and then they can't even really use them. So it's funny to see all my commits have two files, CLAUDE.md and AGENTS.md, CLAUDE.md's just literally a pointer to AGENTS.md.

[00:19:44] **Ben:** Well, and it's so silly because it-- I feel like AGENTS.md has been adop- adopted, from what I've heard, by basically every other tool except for Anthropic. And it seems like, just get on board. Like why do, why are you making it complicated? This is like the, the industry has spoken

[00:20:04] **Carol:** People gonna work around you anyways.

[00:20:06] **Ben:** Right, exactly. Like what's the value add for you as a company? It seems silly Anyway, so that's my triumph-ish.

[00:20:15] Apparently coding is joyous. Who knew?

[00:20:20] **Carol:** All right, so who wants to kick us off for the topic?

## [00:20:23] Wage Theft and the Performance of Working on Video

[00:20:23] **Ben:** All right. Here, here's something that I've been struggling with, and this might be a little specific to my, let's call it work situation. So at work, I, for a good part of the day, I hang out on a shared Zoom call, which is like the company, the IT Zoom room. And I think part of the reason this is happening is because we're not a fully on-site and we're not a fully remote company.

[00:20:50] So there are people that are on-site in physically in the IT room, and there are people that are off-site like me. So we're, I think, trying to create this sense of co-location, which it, it's, it's taking some getting used to. I'm just... It's, there's, there's like a cognitive load to the idea that you're on video.

[00:21:12] but it has also made me very self-conscious about the things that I am doing throughout the day when I'm on video, whether it's like even just like I'm going to the kitchen to get a drink, so, you know, I'm gonna just be... There's just gonna be an empty screen here for a little bit. Or I'm going to the bathroom, or like I'm taking the trash out for the trucks to pick up.

[00:21:34] Or, r-really, the, the thing that I have to contend with now is that it used to be in the old world, if I'm on video anyway, I'm just sitting here coding 'cause that was my job. So it, it was like the, the butts in seats kind of scenario. That's how I know people are doing stuff. In the world of AI, where I might prompt Claude even in a conversational sense, and it has to go into the code to do some deep research to understand the layout of the application and get the full context for the kind of questions it needs to answer, it, you know, it might go off and do that for five, six, seven minutes, and that's before we even come up with a plan, and then it kicks off the plan, and maybe that takes anywhere...

[00:22:16] This is, and this is the crazy thing, is like that might take three minutes or it might take 25 minutes. I don't know how long it's gonna take to, to complete.so I don't know if you guys can see it in your configuration, but over my top right hand, I have a stationary bike. You can see the seat here maybe.

[00:22:32] **Tim:** Yeah, I see the seat. Yeah

[00:22:33] **Ben:** So if I kick off Claude to go do some stuff for a couple minutes, I feel like maybe what I want to do is put on my headphones and get on the stationary bike for five minutes. 'Cause, like, it's either that or I'm sitting here and I'm staring at Claude doing stuff. And somehow when I'm sitting at my desk and I'm staring at Claude doing stuff, I feel like I'm working.

[00:22:55] But if I'm doing the same thing from six feet away, I feel like I'm wage thefting because, like, now I'm being paid to sit on the stationary bike.

[00:23:06] **Carol:** Oh,

[00:23:06] man

[00:23:07] **Ben:** it's...

[00:23:07] **Tim:** performative, right? It

[00:23:08] **Ben:** Yeah. A-

[00:23:09] **Tim:** yeah

[00:23:10] **Ben:** and, like, I, I don't know how to reconcile that. And, like, here's the reality, is if I wasn't on video, none of this would even cross my

## [00:23:20] Multitasking With Concurrent AI Agents

[00:23:20] **Ben:** mind because no one would be watching me.

[00:23:23] I, you know, academically understand how work works. I understand the limitations that I have with Claude, and there are gonna be downtimes. It's like the old xkcd comic where the people are fencing in the hallway, and it's like, "Get back to work," and they're like, "We're waiting for the compiler to run," you know?

[00:23:40] **Carol:** Mm-hmm.

[00:23:40] **Ben:** and now, like, Claude's the new compiler. So I, I don't know. It just feels really weird. Like, do you guys have any sense of tension when you're waiting for Claude to return with information?

[00:23:54] **Tim:** definitely. I, I, that's why I'd start another sub agent or another, uh, another, another project. But I'm, um, I'm

[00:24:01] **Carol:** Like they have ADD, yeah

[00:24:02] **Tim:** I'm... While I'm talking to you guys, I've got one, two, three, four, five, six, seven, eight, nine, different

[00:24:08] **Ben:** Oh my

[00:24:09] **Tim:** running.

[00:24:09] **Ben:** goodness. Are you serious?

[00:24:11] **Tim:** no, I'm dead serious.

[00:24:12] **Ben:** Holy cow

[00:24:15] **Tim:** remember, or before we started the show, you, you made a comment that applies to this. Well, actually not what you said, but my response to what you said. You said your dad would say that that's what rules are for,

[00:24:26] **Ben:** R- yeah, rules are, rules are here to keep honest people honest

[00:24:30] **Tim:** Right. And I told you that no principles of life are what keep us honest. Rules are meant to be broken. So I'll tell you how that same, like being on video back during like COVID days, our, our, our church services were on COVID, and everyone kept their cameras on, and I was kinda like running the Zoom meeting, and I ha- I just hated it.

[00:24:51] I absolutely despised it. I'm gonna tell you my hack that you can use to get around and break this rule. So download a program called OBS.

[00:25:05] **Ben:** is the, like, streaming platform?

[00:25:07] **Tim:** video, it's a video thing, and you can use it for streaming and everything. But you can download a, a... It's a virtual camera, so it creates a virtual camera for your machine.

[00:25:16] So rather than choosing whatever your camera is on your laptop, you'll have an OBS virtual camera, you do a pre-record of you just sitting at your computer

[00:25:26] **Carol:** Hmm.

[00:25:26] **Ben:** Just like, like having pensive thoughts and like

[00:25:30] **Tim:** yeah, just,

[00:25:30] **Ben:** at the screen

[00:25:31] **Tim:** yourself while you're just typically for like, you know, 30, 40 minutes, whatever.and then, then when you wanna get on your bike, just, you just switch cameras real fast and then play that. Go do whatever the heck you want while you wait for Claude to finish, and then get back-- When you're done, get back on and switch the camera back to you

[00:25:51] **Ben:** Yo, this is, this is actually... What's that?

[00:25:54] **Carol:** the same clothes, though.

[00:25:55] **Tim:** You would think, but I got awa- I would like wear different ties and different jackets, and no one ever caught on.

[00:26:03] **Ben:** this was the premise of a murder mystery episode I watched for one of the cop dramas, I can't remember what the name of the show was, where, some CEO did a all-hands meeting over Zoom. And, and she's like, "All right, I'm gonna give the presentation now. I'm gonna flip into the slides.

[00:26:18] Since I can't see you, please hold all your questions till the end." So she flips over to the slides, and it's a recording. Then she goes, and she does some murdering, and then she comes back and, and she comes back and, like, is there to answer any questions.

[00:26:30] **Tim:** Oh, wait, I shouldn't have said that out loud.

[00:26:32] **Ben:** You fool.

[00:26:34] **Tim:** You caught me.

[00:26:35] **Carol:** I think it's so strange you have to stay on cam- like, your camera stays on

[00:26:39] **Ben:** I mean, like, I get it, I, a- and like part of me, part of me likes it because it, you can have the same kind of conversations where if I was in an office, I could just wheel over to someone's desk and be like, "Hey, what's going on?" and, "Help me out with this problem."but

[00:26:53] **Carol:** do you do that in this like, is it like a big group chat that you have open or something and everybody's on video and you just start talking? Or do you have to still message that one person

[00:27:04] **Ben:** not, not everybody's on the video, I'll say that first of all. but the people who are on the video, I can just, I can just be like, "Hey, you got a second?" and then we can have a conversation. And so like that-

[00:27:15] **Tim:** that can be, difficult with the recording. "You got a second?" You're like, " Still recording." She's still typing.

[00:27:23] **Ben:** You're like, "Am

[00:27:24] I muted? Can anyone else hear me?"

[00:27:26] **Carol:** Mm-hmm.

[00:27:27] **Ben:** But like going, going back to the idea of it being performative. So I have a couple of times tried to be, let's call it like more efficient with my time. I can't reach a Cunningham level of nine agents running concurrently. And the reality is, when I even have two agents trying to run concurrently, it's like my brain is immediately overloaded and I forget even which tab I'm in and...

[00:27:53] Or like I'll be having just a kind of a research conversation going in one tab and the other tab is actually doing work. And then, the work part will finish so I have to go and look at that and then I forget to come back to the research or like, I, I don't know. Like it's just im- I'm just immediately overwhelmed by that kind of extreme multitasking.

[00:28:13] Yeah, I find myself opening Claude to do a lot of what I need to do. And when I need to multitask, I will open Codex. So I keep everything very separate.

[00:28:22] Oh, that's interesting

[00:28:23] **Carol:** I put it in Claude, I don't go back to the original, like, task I was on until I wrap something up. I get distracted so easy that by the end of the day I'll have like four things going.

[00:28:34] Only four, not 10 like Tim. But I'll have like four going and I'm going, "Oh, I forgot to finish that." So now my to-do list for tomorrow has at least three of those things on it I didn't wrap up because I tried multitasking while I was in one of those Claude thinking moments and it failed for me

[00:28:51] **Tim:** Hmm.

[00:28:52] **Ben:** Yeah, it's really tough. I mean, you know, like I've, I hear people talk about when they do the, the big time multitasking, they feel completely burnt out by like 1:00 in the afternoon.

[00:29:03] **Carol:** Yeah

[00:29:03] **Ben:** And I don't... Like, I don't necessarily wanna live that lifestyle either. Like, I had a boss who, who, who would always say, "It's a marathon, not a sprint."

[00:29:13] That, you know, you're not trying to get stuff done super fast, you're getting stuff done because this is what you're gonna be doing for the next, you know, however many years.

[00:29:22] **Tim:** yeah

## [00:29:22] Creator to Critic: The Emotional Shift of AI

[00:29:22] **Carol:** Yeah

[00:29:23] **Tim:** it's interesting. So a couple weeks ago, I haven't been on the show for a couple weeks, but, our bigger parent company asked me to be on a panel as one of the panelists about... It, it was, it's about mental health and, and wellness. So I'm like, "Yeah, you know, I'm going through therapy right now.

[00:29:39] I can talk about my experience without oversharing." But they didn't really tell me exactly what the topic was until, like, a couple days before. And it turned out it was about AI, which I thought was weird. but it, it actually turned out to be a pretty good session. It was probably, like, 80, 90 people on that call from

[00:29:53] **Ben:** Oh, wow

[00:29:54] **Tim:** different companies from all over the world. And, it, it was sort of about the stress levels that just the new normal with AI is creating. you know, I was one of, like, five panelists, but I made this point, and afterward everyone kept referring to my comment, so I guess it must have struck a chord. I said that, "So the, the disconnect for me is a lot of people think if you're not a coder, you might think of coders as just, like, robots."

[00:30:20] I said, "But honestly, all-- most of us think of ourselves as artists." I

[00:30:25] **Ben:** Mm-hmm.

[00:30:25] **Tim:** so thinking of you right then, Ben.

[00:30:26] **Ben:** Heck yeah

[00:30:28] **Tim:** and, I'm like, "So, you know, because it's the act of creation. You, you, you open up a code editor, it's a blank page, and you-- stuff comes out of your mind through your fingers and your hands into your fingers, and you type and you create something, and it's that process of giving birth to a thing that didn't exist before that gives you, like, an incredible amount of dopamine."

[00:30:49] **Ben:** Hmm.

[00:30:50] **Tim:** "And now with, with AI, the job has changed from being a creator of a reviewer and a critic. a completely different mental style set." And I said, "And that cognitive load of I don't wanna be a critic, I don't wanna be critical, I wanna be a creator and let someone else be critical. and so dealing with that shift has been very difficult for me, and I don't really know how to handle that." then that created a whole bunch of conversation. And people were, like, saying, you know, "Outsource, outsource, AI to the things you hate to do," blah, blah, blah. And I'm like, "I get it. I hear what you're saying.

[00:31:25] But if you can tell me how I can tell Volaris and Constellation that I, don't, I don't get the feels using Claude, and that I'm not gonna be 10 times more produc-productive in my code

[00:31:38] **Carol:** Mm-hmm.

[00:31:39] **Tim:** I want to lovingly hand roll every single thing because it makes me happy and still keep my job. If you can help me frame that conversation, I welcome it, please." So I, I I think what you're going through, Ben

[00:31:51] **Ben:** the other thing that, the other issue that I run into when it comes to the multi-agent stuff is that, I don't have one of those fancy setups where it's, it's like branching the database every time I need to create a new feature branch,

[00:32:05] **Tim:** Mm.

[00:32:06] **Ben:** and like doing all the fancy work tree stuff with Git.

[00:32:09] So the reality is, if I have two tabs open in my terminal working on the same application, like they're hitting the same database and the same schemas and the same test files. And like, I think the first time I tried to do it just as a experiment to see like, oh, what's all this stuff everyone's always talking about multi-agents?

[00:32:27] It was like immediately it started to step on each other because it would make changes, then it would have to run the TypeScript compiler, and then like the other tab was also making TypeScript changes, so the compiler was constantly breaking mid-compilation. I'm like, okay, this clearly... Like this is clearly not the thing that people are doing because this seems incredibly fragile

[00:32:48] **Carol:** Yeah

[00:32:48] no, for me, I have like 47 repos as part of the team I support. So at any point I am only working like the one thing on one repo, so I don't have to worry about that. However, something you said got me good this week. I didn't realize with the update we had gotten from how we're using Claude, I won't go into a bunch of details, but we've changed some stuff, that now every time I ask it to do something, it was creating a work tree.

[00:33:16] **Ben:** Hmm.

[00:33:16] **Carol:** hadn't used work trees before, so

[00:33:18] **Ben:** I'd never even heard of them.

[00:33:20] **Carol:** I was like, "Hey, this is cool," until I opened Visual Studio and tried loading my project and it couldn't go to the solutions folder because there's now 300 solution options because it's, it's scanning this entire folder to find it. And because they're inside the Git folder, they're not being ignored, and every one of them has created a, a clone of the repo. I'm like, "I can't even open Visual Studio. What's going on?" And I realized what's wrong, so I'm in there deleting, deleting all these work groups. I was like, "I don't know why we would do this.

[00:33:54] Can you stop doing that?" And it was like, "Sure, I'll just work on your, your like current working branch." I'm like, "Perfect.

[00:34:00] **Ben:** Right.

[00:34:01] **Carol:** what I need you to do."

[00:34:03] **Ben:** Right? It's like the magic is great until, until you run into the edges of the magic and you're like, "Oh, I really wish I understood that better," or, "I wish it wasn't doing that in the first place, 'cause now it feels like I'm trapped by the

[00:34:15] magic."

[00:34:16] **Carol:** Yeah. But that's how you would get around the issue you were seeing with the two agents

[00:34:22] **Ben:** Yeah

[00:34:22] **Carol:** base, 'cause then it would be in its own version and you wouldn't have to worry about it.

[00:34:26] **Ben:** All right, I'll call it

[00:34:27] there. so that, that's me trying to contend with how do I justify the time it takes me to get through my day

## [00:34:34] Owning Your Own Data

[00:34:34] **Carol:** I got another one. so I wanna talk about my data. and I mean my data by my data. I use these apps to do things like record my runs and record my workouts, and I wanna know my stats. I wanna be able to pull my data in and go, "How am I handling this load? Like, what does my threshold look like?" And in reality, almost all the apps I use now go, "Oh, you can't export data anymore. You're not allowed to pull that. If you want your data, you can go to our privacy policy and request a dump of everything

[00:35:09] **Ben:** Hmm.

[00:35:10] **Carol:** done, and we will send it to you in five to seven business days." I'm

[00:35:15] **Ben:** Ugh

[00:35:15] **Carol:** "I don't want that.

[00:35:16] I just wanna download a week's worth of my workouts." So I'm having to screenshot them and upload them. I've realized that I want to get away from using apps that don't let me have my data, because at the end of the day, I should be able to control what they're doing with it, and I should be able to use it as I want. I'm not asking for their algorithms. I'm not asking for their proprietary information on how they determine, you know, what my threshold is or how they judge my heart rate max and things like that. I just wanna be able to pull in some five or six values and say, "I ran 8K. It took me 59 minutes and 59 seconds," because I know that from my watch.

[00:36:02] Because over the past four weeks, I've hit like a plateau where my mile pace is 8:05, 8:05, 8:05. It's not changing. But that's bad when I'm trying to train for a half-marathon.

[00:36:17] I'm not getting any better. Like, everything is just completely stale, so it's saying that my long term I'm not gonna get any better, and I-- that's not what I want. And I realized that the plan I was using is not a good plan for me because it's not driven off my da- like, off my stats. It's just a preset plan. We're gonna do these workouts, and this is what it is for everyone who chooses to do this. So I've wanted to customize what I'm doing, and it's made it difficult when they don't let me pull in what should be mine, and that's frustrating to me

[00:36:48] **Tim:** Can I ask you, are, are th- are these apps paid apps

[00:36:51] **Carol:** so,

[00:36:52] **Tim:** or free?

[00:36:53] **Carol:** Garmin is absolutely paid 'cause you pay for it when you pay for your watch. And then Nike Run Club, was paid. I think it may be free now. Either way, I've had it so long I couldn't tell you

[00:37:04] **Tim:** Yeah, because I, I think in the days of AI, your data is their business model now

[00:37:10] **Carol:** And that's what bothers me. If you can use it for whatever you want, I should be

[00:37:14] **Audio Carol:** able

[00:37:14] **Carol:** to use my own data for what I want as well

[00:37:17] **Tim:** Yeah. you're not asking for everybody's data. I mean, that, that's a fair

[00:37:20] **Carol:** No. No, I just want mine

[00:37:22] **Tim:** guess you're just gonna have to, build your own using Claude

[00:37:24] **Ben:** Can you,

[00:37:25] **Carol:** my own plan

[00:37:26] **Ben:** can you like get a VPN and, and like log in from a European country and be like, "Under GDPR, I need to have my data"?

[00:37:36] **Carol:** So I tried Canada, but I didn't try any other. I will absolutely try that

[00:37:42] **Ben:** We had when the GDPR laws came into effect, like instantaneously we got dozens and dozens of people asking for all of their data to be downloadable, which I think in reality most of those people were not scammers, but were like people who were looking for reason... They're like trolls looking for reasons to,

[00:38:06] **Tim:** Legal reasons.

[00:38:08] **Ben:** find a company that's not compliant with, with the GDPR laws and then let's sue them and, you know, settle.

[00:38:13] **Carol:** Mm-hmm.

[00:38:15] **Ben:** did force us to build tools that allowed people to download their data

[00:38:19] **Carol:** Yeah

[00:38:20] **Tim:** That's why we don't sell our product to people in Europe. Just we don't. This is 100% United

## [00:38:25] Data Export, GDPR, and Product Design

[00:38:25] **Tim:** States

[00:38:26] **Ben:** as a person who builds applications, what would your ideal... Yes. No, no, me, me. a- and like you as a consumer in this pers- in this perspective, what would your ideal downloaded data format look like? Are you expecting CSV files, an Excel file, a SQLite database?

[00:38:51] **Carol:** You know what? For me, I go with CSV because almost every tool can use it. That's very universal. So I could put it in, you know, Google Sheets. I can put it in Mac Numbers. I can use a tool in SQL and import it to a database. To me, CSVs are always good 'cause it forces everything on one tab. It doesn't let you do multiple tabs.

[00:39:11] All your data is understood in one place, and it can be transposed in about any tool you want. So CSV is wonderful for me

[00:39:19] **Ben:** Yeah. I think CSV, for the listeners, that's comma separated values, is

[00:39:24] like

[00:39:24] **Tim:** sure our listeners know what CSV Maybe their moms don't

[00:39:30] **Ben:** It's like it's the engine that runs the business world. It's definitely

[00:39:34] **Tim:** It does,

[00:39:35] yeah

[00:39:35] **Ben:** fantastic. Would you be... Okay, now this is me just thinking from a product perspective. If I wanted to create a, a data download functionality for an application, would you be comfortable with a zip file full of ZS- CSVs, like for various pieces of data?

[00:39:51] **Carol:** I would say back in the day I'd be frustrated with that. Now, with the tooling I have available to me and how quickly I could just write something to loop over all those files and get what I need, give it to me how you want, and I will piece it together if I need to. And for me, I, like, I would be happy with a report that just said, "This is what you did over seven days. This is what you did over four weeks." Because I'm not expecting them to give me, you know, without paying a service fee, my trends and my performance improvements, but I wanna be able to get that myself, and I could pull that with a few stats

[00:40:26] **Ben:** I think about this. Sorry, I don't mean to take over the conversation here.

[00:40:30] **Carol:** please do.

[00:40:31] **Ben:** I,

[00:40:31] **Tim:** so

[00:40:32] **Ben:** I, think about this because I have a fitness app which, to be fair, I think me and James England are the only people who ever use it. and sometimes I think it'd be fun to have a download all of my fitness data, but I have wrestled with the, well, what does that actually look like?

[00:40:47] Because, you know, at a high level when I think about fitness data, it's the, it's the, you know, I did this exercise on this day for this sets and this weights. But like there's actually a lot more to it than that. There's the list of exercises that I like. You know, there's, I have a body weight journal.

[00:41:05] I have other kinds of, of like pain journal like, oh, on this day my shoulder hurt or like, you know, like there's all kinds of stuff that the app can present to you that could be considered data and like how do I make that into a meaningful export? And a zip of CSVs is the only thing I've come up with so far.

[00:41:23] Not that this exists. This is the conversation that happens in my head, you know, when I'm stealing wages waiting for Claude to finish its tasks.

[00:41:32] **Tim:** While you're not riding on the bike

[00:41:33] **Ben:** Yeah.

[00:41:34] **Carol:** does your app allow for run tracking?

[00:41:39] **Ben:** I mean, you could do a cardio thing, but I don't... not in any kind of, like, meaningful way. Sorry

[00:41:45] **Carol:** I could do, like, interval thresholds, GPS. This is where I was at,

[00:41:49] **Ben:** No, definitely not. You need a real app for that

[00:41:54] **Carol:** just need the data. That's what I need

[00:41:57] **Ben:** But here's the thing that always kills

[00:41:59] me.

[00:42:02] So like, hmm, this is like just a customer service question at some point, that I am shocked at how many times you sit there and you use an application and you can't imagine that someone hasn't thought of a way to do this, and that they had the thought, "Oh, this would make someone's life better. I should just put it into the app."

[00:42:23] And either, like the powers that be said you can't do that or they... There was like no good communication at work that allowed that kind of a workflow to happen or people can't take any kind of initiative because it doesn't fit cleanly into a sprint or it has to be signed off by, you know, a product manager who has to sign it off with his, creative director and then they have to do it on the...

[00:42:45] Well, like which six-month product life cycles does this fit in? Anyway, I'm, I, I just constantly get super frustrated by any, any kind of scenario where people can't have an idea of like, "Oh, how can I make someone's life better?" And then there's something in between that thought and them doing that thing.

[00:43:05] **Carol:** Well, what frustrated me was researching this just with Nike Run Club, for instance. I was researching it to try to figure out what was possible, only to find out it used to be. They killed it and claimed that they were releasing too much of the proprietary information on how they actually build, like, all of their plans for what people do. I'm like, "No,

[00:43:25] **Ben:** Yeah. Then don't put that in the export

[00:43:27] **Carol:** Yeah. I'm like, "Just give me my run." So anyways,

[00:43:32] **Ben:** lame

[00:43:34] **Carol:** that's me. I'm not gonna get my data. I'm just gonna have to make my own. I hope I don't break a leg. What about

## [00:43:38] Metrics Dashboards and the Refinement Arcade

[00:43:38] **Carol:** you, Tim? What were you gonna talk about tonight?

[00:43:41] **Tim:** I mean, it's AI related, but it just-- it really makes being able to make metrical dashboards. in my--

[00:43:51] **Carol:** Metricable dashboards

[00:43:53] **Tim:** So dashboards that, that show you metrics based off of whatever, you know, easy to read things that, you know, if you have like a ticketing system, it gets really, really complicated really fast, particularly when you have thousands and thousands of tickets people are doing work.

[00:44:08] and so trying to simplify it bybeing able to have my direct reports goals actually trackable. 'Cause goals, setting has always been a thorn in my side 'cause it's like, what should we measure? Like, we all get in a room like, "Yeah, we should measure this." And we're like, "Yeah, that's a good metric.

[00:44:27] We need to know that so and so isn't creating new bugs and that they're spending most of their time on this." But then it's like there's no way to actually track the work, right? And so, Claude actually has, has really helped me be able to actually track the work now and create a very simple, very pretty board that shows you red light, green light, versions of where are you on track, and that way I can have one-on-ones with my direct reports, which I went from having three to, What'd I say?

[00:44:58] Six to 16.

[00:45:00] **Ben:** Hmm, yeah

[00:45:01] **Tim:** A lot

[00:45:01] **Carol:** Big change

[00:45:02] **Tim:** Yeah, it's a big change. being able to have a conversation where it's not like, "Well, I feel like you're doing a good job," and feelings Right? It's not really a lot you can do with that. A- and then if you're having a bad day like, like I had doing that, they messed up my GitHub, like, "I feel like you're doing a terrible job." It's like, shouldn't be about what Tim's feeling that day. It should be like, "Okay, what's your, what's your actual metric?" So been a- absolutely amazing, and they look fantastic. So one of the things we were tracking is, like, having people actually, take the tickets and estimate them before we have the sprint planning meeting. 'Cause you get a sprint planning meeting and, and int- it's, you know, people-- No one's looked at the ticket. No one's looked at what it's trying to... And they're like, "So how long do you think it's gonna take?" They're like, "Dude, I just... This is... I'm, first time I'm looking at it. I have no idea." And you're like, "Well, give me a number 'cause we need to plan for the sprint. We need to know how many hours we're actually putting in." And they're, and they're like, "I, I can't give you an answer." And so you just throw it in there and hope and pray, which is terrible for planning. I, I know that, I know everyone hates estimating, and estimating is hard. I get that. But there has to be some good faith effort to try to

[00:46:12] **Ben:** Mm.

[00:46:13] **Tim:** properly. So I created, a, a site. I call it the Refinement Arcade, where I'm ga- where I'm gamifying the system. And it basically scores everyone to who actually, like... And it, it does like a balance of... 'Cause, you know, s- when you create a measure with that Goodhart's law, when you create a, a measure, that measure ceases to be a, a good m- a

[00:46:39] **Ben:** I can

[00:46:39] **Tim:** measurement, right?

[00:46:40] It's

[00:46:40] **Carol:** Yeah

[00:46:41] **Tim:** try to gamify it. So it tries to balance that with like, doing a lot of tickets is good, but doing tickets that actually are accurate is, is good too. So it balances those two things together.and it gives points rather than just saying, "Oh, you did 10 tickets," or, "You spent 12 hours refining." Or we call it refining when we do estimates. We have to do an estimate and have to put a technical analysis on it to back up the estimate.so gamifying it. And it's just really cool 'cause it took me probably two days worth of work to get that done, but it was so difficult. It's something that I would've probably spent a month on and then quit.

[00:47:19] **Ben:** Yeah.

[00:47:19] **Tim:** but now I did it

[00:47:21] **Ben:** what's the application?

[00:47:22] **Tim:** fantastic. I'm-

[00:47:23] **Ben:** What's the application that's hosting the, the dashboards?

[00:47:27] **Tim:** So the dashboard actually, it, it, it pulls the data. It's a Rust program, that pulls the data from our Jira instance

[00:47:36] **Ben:** Oh, so is this something that only you can see?

[00:47:39] **Tim:** No, I mean, I publish it. So at the

[00:47:41] **Ben:** Oh, okay. Gotcha. Gotcha

[00:47:42] **Tim:** it and then so everyone can see it. so, so the Rust application goes in, grabs all the data from Jira. There's rules, you know, to explain, know, what defines a ticket being done as far as refinement and estimation goes and how long it took them. It looks at the, the number of hours they put in, it looks at the technical analysis they put in, and it looks at what they've estimated it. So if they don't have those three things, it doesn't award them the points. And it-- then it lists every single ticket that needs to be worked on, right? And you can click it, and you can see what they've done. and it looks really cool 'cause, I used, impeccable.style, and it looks like

[00:48:22] **Carol:** Mm-hmm.

[00:48:22] **Tim:** arcade game. It looks like an arcade. It's

[00:48:24] **Carol:** Oh, that's cool.

[00:48:25] **Tim:** and

[00:48:25] **Carol:** Mm-hmm

[00:48:25] **Tim:** it's like these little, animations whenever the-- it like looks like quarters popping up everywhere.

[00:48:31] **Carol:** Let's go

[00:48:32] **Tim:** looks

[00:48:32] **Ben:** It's fun

[00:48:33] **Tim:** But it makes it-- Because in the past, it's like s- people, would like hand you a spreadsheet and go, "Here's a spreadsheet of everyone that's not refined. You know, we need this, this, and this." And just like, I'm not a spreadsheet guy. I hate looking at spreadsheets.

[00:48:46] **Carol:** Yeah

[00:48:46] **Tim:** webpage has animations and everything, and you can actually click stuff and drill down and see what needs to be done and what's left, and it updates. So it-- the Rust program pulls all the data in. It's on a schedule that runs every thirty minutes to update things, and then it pushes it to a static HTML page that's hosted that you have to have like our corporate login. It uses our SSO to log in. And so that way, you know, every standup that we have, I'll, at the end of the meeting, I'm the last one to go.

[00:49:14] I'm like, "Okay, the-- no one is... There's the arcade, no one's put any quarters in yesterday, and you, you all promised you're gonna spend at least one hour a day doing estimation so that when we have sprint planning meeting, it's not, doesn't feel like an interrogation." So it's pretty cool to be able to, to do that and quickly do-- and relatively quickly do that

[00:49:38] **Ben:** Yo,

[00:49:38] **Carol:** That's cool

[00:49:39] **Ben:** dashboards are just magical in general.

[00:49:42] **Tim:** They

[00:49:42] **Ben:** like it almost doesn't even matter what a dashboard is saying. They're just delightful to look at

[00:49:47] **Carol:** Until they load no data at all and you're like, "What went wrong?"

[00:49:51] **Ben:** Right.

[00:49:51] **Carol:** what Azure likes to do to me. Azure likes to give me these pretty little gray boxes that says, "Error loading data." I'm like,

[00:50:00] **Tim:** then, and

[00:50:01] **Carol:** "No."

[00:50:01] **Tim:** dashboard is the goals that so when I have my one-on-ones, I'll just pull up their individual scorecard get very, you know, in nice pretty color they can see where are they at. And so it, it's less of an argument about what, how I feel they're doing of, "Okay, you're green, green, green, green.

[00:50:17] There's a red. we need to do to get you green on this?" It's, it's more of a conversation about why they're struggling in that area. And the, and the, the struggle typically is not their fault. It, it tends to be like, well, there conflicting priorities that the organization putting on them, and, and I have to find a way to unstick that. And

[00:50:37] **Carol:** awesome.

[00:50:37] **Tim:** them

## [00:50:37] Measuring People Badly: Budgets and Goodhart's Law

[00:50:37] **Tim:** my goals above, right? So my

[00:50:39] **Carol:** Mm-hmm.

[00:50:39] **Tim:** the top, their goals are at the bottom. I'm like, "Your goals feed directly into my goals, so I don't wanna be red, and I don't want you to be red because I don't wanna be red." So

[00:50:48] **Carol:** That's awesome. one of our listeners, Jason, He was an architect on my team, now he's a supervisor for another team. But he created this process that's called the heartbeat, and it basically is a daily outline of what's coming up, what you did yesterday, and at the end of it, he has this process that says, "Oh, and by the way, review all of this and attach it to my performance plan so that when time comes to review it, I can then say these are the things I did to actually get there."

[00:51:18] Because we don't have a good process that says, "Are you meeting it? Are you not?" took his tool and I fed it to Claude, and I was like, "Hey, we're gonna do what Jason did, and we're just gonna add one thing, though." I was like, "I want a gap analysis. I need you to tell me everything I don't have to get an outstanding performance, and anything I can do, like lay those out for me." So we were going through and like listing them all. I was like, "Okay, I clearly see that in order for you to be outstanding, three of these, three of your things say you have to deliver within time or everything that you're handling is within time or on time and within budget, but nothing you're ever working on mentions budget."

[00:52:01] **Tim:** Hmm.

[00:52:02] **Carol:** I went, I went, "Wait, snuck budget into my performance plan?" Because I don't even have visibility into our budget. Like, no one lets me see the government money. I don't have-- I can't do that, you know?

[00:52:15] **Ben:** That's how they get ya

[00:52:16] **Carol:** I actually sent that over to my supervisor, and I was glad Jason had published this 'cause I sent that over to my supervisor and I was like, "Hey, performance plan says I can only get outstanding if I am delivering on budget, but you guys don't let me see the budget, so I don't know if we're delivering on budget." And he goes, "Yeah, let me take that to my boss 'cause you can't see the budget." I was like, "No, I can't see the budget." I was like, "So you're telling me I can never be outstanding, so someone needs to fix it." But had Jason not like taken the time to show all of us, in the, the ambassador group, had he not taken the time to show us like what he was doing and, and sharing that knowledge, then I would have went into the end of the year thinking I'm doing an amazing job because that's all the feedback I'm getting.

[00:53:00] But in reality, there's a checkbox I'm never able to check and no one cared to find out I couldn't check it. So I think it's really cool that you're creating something that helps them stay on track and keeps, you know, keeps them clear on, on where they're not meeting or where they are meeting and you know what to do then.

[00:53:16] **Tim:** Yeah

[00:53:16] your story is exactly thing that I, that was, I was working to get against. 'Cause it's like, you know how that happened, right? So a bunch of, I don't know the equivalent in government, but a bunch of executives got together and said, "Well, here's what we need to do. We make sure everything's on time and everything's on budget and blah, blah, blah."

[00:53:33] And everybody's like in the, in the room like, "That's a fantastic idea." And then they leave and no one thinks, "Well, do we know how to actually track that? do we track if it's on budget? What is the budget? Do, do people know what their budget is?" Right? And, and in the past before, it's like I would just be like, "Well, I felt like it was on budget.

[00:53:51] No one yelled at me." Right? and

[00:53:53] **Carol:** Yeah

[00:53:53] **Tim:** me being, you know, I wanna be a good manager. I don't wanna punish someone for something that they couldn't measure themselves. So I'm like, "Yeah, we'll just mark it good. We had no way to track it, our bad." now it's like this has pointed out things we weren't able to measure, and now we're actually measuring it.

[00:54:08] It's a shame it's in-- I got it done in June, I only received most of these direct reports in June, so not my fault. but yeah. being able to actually see it, and it, and then it points out the problems, and usually the problem's not the employees. Usually they're problems with management, and

[00:54:24] **Carol:** Yeah.

[00:54:24] **Tim:** so we have to change.

[00:54:25] **Carol:** one of the things I was told they look at is the number of items that get marked done in our AD, on our ADO board. And when I heard that, this was a couple months back, so I don't think it's really a thing, just to be clear to anyone listening, but I was rumor mill, it was how many things get marked done. I was like, "That's a problem," because I research things, put notes on it, pass it off to someone else. They finish it, they mark it done.

[00:54:47] **Tim:** Right

[00:54:47] **Carol:** a lot assigned to me gets marked done. You should go look at my code commits, or you should go look at my meetings to know how many things I'm doing. If you're really measuring my success on what gets marked done, I'm gonna get fired.

[00:54:58] **Tim:** Mm-hmm.

[00:54:59] **Carol:** aren't really measurables for everyone

[00:55:02] **Tim:** A-at

[00:55:03] the bottom, I, I explain how the scoring works. I wanna be very transparent. I want everyone to know, like, here's what-- how this number gets there, here's how this status is done, and here's what you need to do from get it from, to red to green. But at the very bottom, I have my favorite quote, and I've, I've said this on the show and I'll say it again. Eliyahu Goldratt from the Haystack Syndrome, says, "Tell me how you measure me and I'll tell you how I will behave. If you measure me in an illogical way, do not complain about illogical behavior." I love that

[00:55:34] **Carol:** I love it. Yeah, that's a good

## [00:55:35] Datadog vs. Grafana and Prometheus

[00:55:35] **Carol:** one

[00:55:36] **Ben:** one thing that I had, had wrestled with, just in terms of dashboards here, and this is a little bit of a tangent, but I think mostly on point. And it's kind of like dashboards meets product design. So at work for years, we had used Datadog, which, in my limited experience, it feels like the best in breed

[00:55:56] **Tim:** Mm-hmm.

[00:55:57] **Ben:** and just all around, yeah,

[00:55:59] **Carol:** pricey.

[00:56:00] **Ben:** best it goes.

[00:56:01] **Carol:** Mm-hmm

[00:56:02] **Ben:** But like, I feel like you're getting a lot of value for the thing that you're paying for. And the, the kind of like the entry-level use case is something happens in the application, and I increment a counter, and then I wanna put that counter on a dashboard to see, like, how many times a day, for example, or like an hour do, people hit this page or do people click this button kind of a thing.

[00:56:26] And you do that in Datadog, and you put the counter on a graph, and it's magical. And you can see like, oh, 20 to 30 people do this an hour, and it's consistent. But then like for some reason on Saturday, it spiked to like 80 an hour. What did we do at that point? And it's, and it's just so, thrilling to see those numbers for the first time.

[00:56:44] And then at some point, management was like, "Oh, it turns out that Datadog's stupid expensive. so we should start to explore using, Grafana and Prometheus," which is like the free self-hosted version of that stuff. And I remember trying to do the exact same thing. You take that counter and you put it on a graph, and it just goes up and to the right forever.

[00:57:07] And you're like, "What? That doesn't make any sense. Like, what am I doing wrong in my, in my Prometheus Grafana calculations?" And then it turns out that that's actually how counters work. They just go up and to the right forever. And that the thing that Datadog was technically doing was like actually graphing the delta over a time period of that counter.

[00:57:28] So the counter is actually going up and to the right under the hood, but they don't... But like the product hat goes on, and they're like, "Oh, that's stupid though. No one actually cares about that number.

[00:57:38] **Carol:** Yeah

[00:57:38] **Ben:** So let's make the obvious case the easy case, and we'll just make it the like implicit over time period kind of a graph."

[00:57:46] And, I don't know. Like when I saw that happen, it just made me so angry. Like forever and into the future, anytime I e- ever hear anyone talk about how great, Grafana is and Prometheus, I'm like, "It's only great because you haven't used a good product." Like there's nothing easy to use about that product at all.

[00:58:08] anyway, that's my little soapbox. Sorry.

[00:58:10] **Tim:** I, I don't know. I, I stood up-- I, I stood up like several Grafana plus Loki,

[00:58:16] **Ben:** Oh, I don't know, Loki

[00:58:17] **Tim:** I don't really know the separations of concerns

[00:58:20] **Ben:** Yeah, me neither

[00:58:20] **Tim:** One does-- One kind of does... does the-- has the dashboard side, and I think Loki is sort of the, the, the data source for it.

[00:58:29] **Ben:** Hmm.

[00:58:29] **Tim:** The, And then, Alloy will do the log aggregation. But in a couple of days, I was able to stand up s- really some nice dashboards. Mostly I just use it for Claude to Claude to go talk to Loki to research stuff in our logs so it can... Without me having to actually get on a server and go download the logs, so I have access to them all. But it's been super helpful.

[00:58:51] It's helped, it's helped di- find the more things that you can feed Claude, the quicker and more correctly it can solve a problem

[00:58:59] **Ben:** That's funny. I like that. I

[00:59:00] **Carol:** it can just get very lost

[00:59:02] **Tim:** True. Very true. Yeah, sometimes you just gotta tell it, "Nope, stop looking there." So, so

[00:59:08] **Carol:** I like to go, "Are you still on the correct path? Because I feel like you've been processing this a long time." And almost always it goes, "Yeah, no, I was definitely going about this the wrong way. Let me get back on task."

[00:59:22] **Tim:** Good catch, Carol. That was

[00:59:23] **Carol:** Yeah.

[00:59:24] **Tim:** call. You're amazing and super smart.

[00:59:28] **Carol:** if you spin for seven minutes, I'm gonna shut you off.

[00:59:33] **Tim:** yep, so that's my thing

[00:59:36] **Ben:** I feel like we did it

[00:59:37] **Tim:** We

[00:59:38] **Carol:** Yay, we did a show without

[00:59:38] **Tim:** it. up

[00:59:39] **Carol:** Adam.

## [00:59:40] Patreon

[00:59:40] **Carol:** All right. So that's gonna wrap it up for today. And this episode of Working Code was brought to you by the GitHub Banhammer and listeners like you.

[00:59:49] **Tim:** Too

[00:59:49] **Ben:** you're too soon and ongoing.

[00:59:54] **Tim:** Mm.

[00:59:55] **Ben:** Uh, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, consider supporting us on Patreon.

[01:00:01] Our patrons cover our recording, editing, and transcription costs, and we couldn't do this without you. Special thanks to our top patrons, Monte and Giancarlo. You guys are eternally the most amazing people in our universe.

[01:00:17] **Carol:** And we would give you your data

[01:00:22] **Ben:** at this point, we're gonna go

## [01:00:23] Thanks For Listening!

[01:00:27] **Ben:** and record the after show. If you wanna listen to the after show, become one of our Patreon members. And, until then

[01:00:30] **Tim:** Hey guys, the dashboard of my heart says your heart matters
