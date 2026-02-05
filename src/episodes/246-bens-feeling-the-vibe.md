---
title: "246: Ben's Feeling the Vibe"
description: "Ben finally takes the plunge with Claude Code. What he finds is unsettling."
date: 2026-01-29
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/246-bens-feeling-the-vibe/id1544142288?i=1000747168000"></iframe>

Ben's been circling vibe coding for months, kept at bay by a simple fear: what if he spends more time fighting the AI over formatting than actually building anything? What if he has to bolt on linters and test runners just to babysit the output? Then his work handed him a Claude plan, and he decided it was finally time to take the plunge. And then something unsettling happened—the code looked like _his_ code. Same line lengths. Same method ordering. Same obsessive formatting. Nobody told it to do that. It just... knew.

Meanwhile, Adam has gone full mad scientist. His ["Ralph" workflow][ralph-video] runs Claude in a loop, feeding it tasks from a JSON file while he walks away to eat dinner. When he comes back, features are done. Tests pass. The machine just keeps building. It's the kind of setup that makes you wonder why you're still manually typing commands into a terminal.

### Links

- [Adam's Ralph Workflow for Claude Code][adam-ralph] - Adam's blog post with his implementation
- [Matt Pocock's Ralph Primer Video][ralph-video] - The workflow Adam adapted for automated iterative development
- [Algorithm Maze Race][algorithm-maze] - Tim's vibe-coded game on itch.io
- Pro tip: Use `/resume` in Claude Code to return to prior sessions

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/246-bens-feeling-the-vibe.md
[ralph-video]: https://www.youtube.com/watch?v=_IK18goX4X8
[adam-ralph]: https://adamtuttle.codes/blog/2026/my-ralph-workflow-for-claude-code/
[algorithm-maze]: https://xeveous.itch.io/algorithm-maze-race

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** no, it was just, it had just written its own.

[00:00:02] **Tim:** Its own test.

[00:00:03] **Ben:** Yeah. It was just bonkers.

[00:00:06] **Adam:** I mean, in terms of tests, you know, like

[00:00:08] **Tim:** It obviously didn't learn that from you.

[00:00:10] **Ben:** Yo.

## [00:00:32] Intro

[00:00:32] **Adam:** Okay, here we go. It's show number 246. And on today's show, Ben is feeling the vibe. we're gonna be diving into some vibe, coding discussions and plot code and all that. Carol is working late tonight, not able to join us, so it's just the boys. so Tim, I'm gonna start with you first for our champs and fails.

[00:00:47] **Adam:** What do you got going on, my friend?

## [00:00:49] Tim's Meh

[00:00:49] **Tim:** I'm taking the third option between triumphs fails and growing for the meh.

[00:00:54] **Adam:** Okay.

[00:00:56] **Tim:** Yeah. There's nothing really significant to say. It's triumph and nothing bad to say it's a fail. So, you know, that's, I guess it's a good thing. Really got nothing. this time of year is kind of weird. It's the first month of the year.

[00:01:07] **Tim:** It's when you're part of a company that's part of a very, very big company. There's a whole lot of end of year, beginning of the year administration and miss trivia that you have to do. And what drives me absolutely nuts is so you have to build your strategic plan for the year, right? And so at the end of the year, they're like saying, okay, you need to review your goals from 2025 and start, you know, setting the, the individual employee goals for 2026.

[00:01:39] **Tim:** Honestly, by the time January rolls around, you are seriously just struggling to wrap

[00:01:45] **Tim:** up kind of the, the 2025 retroactive. And then you're trying to figure out your balance sheet goals for 2026, you don't really know where you are in January. So I just wish officially that our, our company would say, you know, don't worry about 20, 26 goals until February, because the, what happens almost every year is okay, we, we kind of guess we're like, here's what I think is gonna be important for next year before you've actually done all the sitting down and working it out.

[00:02:12] **Adam:** Mm-hmm.

[00:02:13] **Tim:** And so you create these goals for someone and then by the end of the year, next year you're going, well, that's what we thought it was, but you didn't really have to do this goal, so we're gonna strike this goal off and you're not gonna count against you. 'cause you know, things came up and we totally switched it around and now none of your goals really apply.

[00:02:28] **Tim:** And that happens so much. And I think part of it's just because it's like corporate's, like you gotta have the goals for 2026 in January. dude, we're still trying to figure out what 2025 was.

[00:02:38] **Tim:** We're still unwrapping, you know, unwrapping that thing. So yeah, I don't, I don't get it. But at the same time, it's like,if you're not good at your goals, and it's like, well, not my fault, everything's changed.

[00:02:50] **Tim:** Okay, so. I know that there are KPIs, key performance indicators, but then I feel like there's another type of goal setting that has another acronym. Did, did you? There's some likeAnd I, I do know this and it's not coming to me, they're gonna shoot me. 'cause I work with this all the time.

[00:03:11] **Adam:** you said not KPIs.

[00:03:12] **Ben:** not KPIs. It's more of like a

[00:03:15] **Ben:** philosophical goal. You know? It's Yeah. It's more of a strategic goal.

[00:03:19] **Ben:** yeah, yeah, yeah, yeah. But it has an acronym. I can't remember what the heck it.

[00:03:23] **Tim:** Yeah. I, yeah. Our, our listeners will call it out to us, but Yeah, I know what you're talking about.

[00:03:29] **Ben:** And that, that was the frustrating thing when I was at InVision when our team leads would have to come up with these, and the, it's one of these things where the philosophy meets the practicalities of human nature and they would start off as process saying, look, we want you to pick these goals.

[00:03:46] **Ben:** They're supposed to be goals that you're probably gonna fail. Like at least 30 or 40% of them. Like there's, you know, some of them are supposed to be doable and some of 'em are supposed to be stretch, humans don't like the idea of setting themselves up for failure, so how do you, it it was just, it was very conflicting trying to come up with the goals that we know we're gonna fail.

[00:04:04] **Ben:** And then we're like, why are we even putting them on the list then? That's dumb.

[00:04:07] **Tim:** Yeah. Now that's not our philosophy. We don't, we go for goals that might be slightly a stretch goal, like, you know, increase X by so many percentage and we're really aiming for 10, but we tell you 15, right?

[00:04:21] **Tim:** We do maybe do that, but it's yeah, we don't look for goals for people to fail. that seems bad.

[00:04:26] **Tim:** anyway, so yeah, that, that's me. in, in the land of Meh, how you, Adam?

## [00:04:31] Adam's Triumph

[00:04:31] **Adam:** I am gonna go with a nice, quick, simple triumph today, which is that, earlier this week I used AI to write my company's AI usage policy. So, I mean, look, it wasn't a total just like, Hey, right, I need an AI usage policy. Go, right? I, I fed it a couple of our existing policies as like, this is how it should be structured.

[00:04:51] **Adam:** This is kind of the general tone and vibe of the policies. and this is our position on things, right? this is what you are and are not allowed to do, and this is where the boundaries are. Now. Put all that information in policy format, and it did a really good first draft. You know, I didn't see, I was very carefully reading through it for, you know, signs that it was written by ai, right?

[00:05:12] **Adam:** Lots of m dashes and bulleted lists and stuff, but I think it followed the formatting of our, the policies. I gave it as context, really well. So, and, and I, so after I had it write it, I made a few minor edits, nothing significant, and then I passed it off to my team and I was like, okay, this is the first draft of our upcoming AI usage policy.

[00:05:33] **Adam:** you know, does your opportunity to influence the policy, right? If you, want changes, if you think I missed something, if you think I'm too lenient or too restrictive or whatever, like this is your chance to get it heard. Then I got a couple of, you know, things to change, but not a single person questioned whether or not I had used AI to write it.

[00:05:49] **Adam:** So

[00:05:50] **Adam:** I'm calling that a win.

[00:05:51] **Ben:** Heck yeah.

[00:05:52] **Adam:** so, uh, that's it for me. Ben. What do you got going on?

## [00:05:55] Ben's Failiumph

[00:05:55] **Ben:** I am gonna go with a emph that, dovetails with the show here. so the triumph part of this is that over the last couple of days, four or five days, I spent a good amount of time looking into text diffing algorithms, and this comes off the tail of, I had written up the, there's a, apparently a, a fairly well known refactoring code kata called the Gilded Rose.

[00:06:19] **Ben:** And, they didn't have a version of that in ColdFusion. So I wrote a version of it.

[00:06:22] **Adam:** Georgia O'Keefe painting or,

[00:06:24] **Ben:** I have no idea. I'll say yes.

[00:06:28] **Adam:** oh God,

[00:06:29] **Ben:** Don't bring your art education to this conversation, sir.

[00:06:32] **Adam:** that was a, well, that was less or less of an artistic, joke than you thought. Don't worry about it.

[00:06:37] **Ben:** Oh, okay.so anyway, so I, I wrote the version of this gilded rose kata in ColdFusion, and basically it just uses this brute force text diffing where you, generate output and then there's what call this like golden master, which is a text file that says if you run this and everything is correct, the output should look like this.

[00:06:57] **Ben:** So I ran it. I compared to the expected outcome and I could either say it was pass or fail on the test. So it was this binary either pass or failed. And when I got done with it,

[00:07:07] **Tim:** wait, wait, wait. You bury the lead.

[00:07:10] **Ben:** yeah,

[00:07:11] **Tim:** You wrote tests?

[00:07:13] **Ben:** I did run, yes, I wrote a single test

[00:07:17] **Tim:** job Ben.

[00:07:18] **Ben:** and

[00:07:19] **Tim:** encourage, always encouraged behavior. You wanna see?

[00:07:22] **Ben:** So I got to the end of this and I thought to myself, you know, this binary yes, no pass fail. It kind of sucks. Like it, I, it's like I, I realized that I have an error in my logic 'cause it says that the test failed. But I'm looking through, you know, kind of hundreds of lines of output trying to figure out where in that output something went wrong.

[00:07:41] **Ben:** so I said it'd be great to have something that looks a little bit more like a GitHub code diff, where I have reds and greens showing me where things were added and removed. So I spent a little while looking up, a text diffing algorithms and apparently there's one called the Myers Diff algorithm, which is, I guess the most famous one, kind of the granddaddy of all the text diffing.

[00:08:00] **Ben:** and it, I watched some videos on it and played around. It was a little hard for me to get my head wrapped around, but I finally figured it out and I was able to output, the Gilded Rose test. as showing little highlights of what lines were actually wrong and I could figure out what was added to this that shouldn't be there and what was removed from this that should have been there.

[00:08:21] **Ben:** And, uh, it was super satisfying to figure it out. It was an area of programming that I don't really do much with the, all the text, comparison algorithms so it was a triumph tool to get that done. The, the failure part of the failure fear is, so I spent, I don't know, four or five days, not straight days, but you know, like mornings and kind of stuff looking into that.

[00:08:42] **Ben:** And now I'm kind of in this existential crises where I wonder if that kind of what's called indulgent exploration of my mental faculties, is that even worthwhile anymore? And that, that's where we sort of get into the, the topic of the show here, which is, I'm stepping into vibe coding now at work and I'm struggling to understand, and I'm struggling to find the perspective on how non coding fits into that paradigm.

[00:09:13] **Adam:** Mm-hmm.

[00:09:13] **Adam:** Interesting. Yeah, I mean, in terms of how do I

[00:09:16] **Ben:** I, I, I, I keep trying to come up with a metaphor, so it's like the, the best metaphor that I've come up with so far is, coding is to vibe coding as physical activity is to an exoskeleton.if I have an exoskeleton that helps me lift things at work and move boxes around safely and more efficiently, and I don't get as tired, that doesn't mean I should stop being physically active and like I should stop exercising my muscles.

[00:09:45] **Ben:** It's not a replacement, it's an additive at work to make work faster and more effective.

[00:09:51] **Adam:** Yeah,

[00:09:52] **Ben:** That that's the best metaphor that I can come up with.

[00:09:54] **Adam:** Yeah. I, I, I do think of it very much like a tool. And it, it requires you to use it. Well, you know, I think we said that last week, but, you know, I, I think one of the thing, well, I mean, like you said, we'll get into it, but I think one of the things that's gonna become obvious to you after a day or two of trying to get it to be really productive for you is that when somebody first hands you this particular tool, you don't even see like, where am I supposed to hold it?

[00:10:22] **Adam:** Like, where's the handle? I don't get

[00:10:23] **Adam:** it. You know? And then once you find the handle, you're like, okay, but now which way do I hold it? Right? Like there's, there's a lot, there's a big kind of a steep learning curve in terms of getting really productive with it. and it is like asking the right questions and, and kind of working in stages sort of thing helps.

[00:10:39] **Adam:** but yeah, so I mean there's a lot to learn, lot to talk about there.

[00:10:43] **Ben:** Yeah. I'm definitely feeling all, I guess let's just roll into the show. Carol's not here, so we're done with our triumphs and fails. Let's just,

[00:10:50] **Adam:** did I say earlier? She's working late

[00:10:52] **Adam:** so she's not able to join us,

## [00:10:53] Vibe Coding Begins

[00:10:55] **Adam:** so yeah, let's get into it. so Ben, what editor do you use? And I know what the answer is. I just want to throw you under the bus real quick for it.

[00:11:03] **Ben:** I'm still on Sublime Text. Yeah, boy.okay, so, so that is, that's an actually very interesting segue into the conversation because everybody and their grandparent now uses Visual Studio Code to do their vibe coding or something like Cursor, but mostly Visual Studio Code, it seems.

[00:11:22] **Adam:** You said to do their

[00:11:23] **Adam:** vibe coding and kind of the whole point of vibe coding is you're not touching the

[00:11:27] **Ben:** Ah, okay. Okay, okay, okay.

[00:11:29] **Adam:** But

[00:11:30] **Adam:** anyway,

[00:11:31] **Ben:** so, visual Studio Code has been the main driver and. Part of why this is top of mind for me is because Claude, the way Claude wants to work is it just wants you to install the Claude command into your global NPM and then just run Claude from your terminal. And it has access to everything.

[00:11:52] **Ben:** And yes, it runs within a working directory, and there are some safeguards about what it can do, but from everything that I've seen and read and heard on podcasts, that's not like security theater, like there are safeguards, but basically there are ways

[00:12:08] **Ben:** to exfiltrate information simply because there are so many tools that Claude can use to get its work done.

[00:12:15] **Adam:** I absolutely guarantee you that Claude's asking for permissions has prevented more disasters than the TSA.

[00:12:24] **Ben:** I, yeah, I mean like, okay. So it has these prompts. You can either put it into sort of a YOLO mode where it can just run off and do stuff, or you can have it prompt you for when it wants to do things. so anyway, the, the idea of just installing it on my host has just left me feeling very uncomfortable in my tumtum.

[00:12:46] **Ben:** So I started to look up how can I run this inside of a Docker container? And when I first looked at that.a month ago, it feels like there was no great answer. The Claude website recommends dev containers, which is, this is where we get back into Visual Studio Code. Visual Studio code ties in very nicely with dev containers.

[00:13:09] **Ben:** It's a Microsoft protocol or framework or whatever the right word is, and it's essentially a way to secure a, uh, like a virtual machine somewhere running something isolated. But I just like, I don't wanna switch to Visual Studio Code, so I sort of gave up on that path. But apparently Docker Desktop just released, just recently released an experimental feature called Sandboxes.

[00:13:33] **Ben:** And it feels very much like they did it just for Claude. That's the examples that they have of how you run Claude inside these dev sandboxes. so I was able to get that running after a bunch of trial and another, so, so I've been vibe coding now at work for, let's see, what's today, Tuesday. So two days.

[00:13:50] **Adam:** So when you say you've been vibe coding at work, can you give us, and obviously you can't, like, this is what I built and this is how I built it, but give us a, a glimpse into how you're doing this work. I.

## [00:13:59] First Impressions with Claude Code

[00:13:59] **Ben:** Okay. So I, once I got the sandbox working, I'm like, I can run, I can, I can, turn on this virtual machine, this little micro vm, and it's, it automatically somehow mounts the current working directory behind the scenes like you would with, any kind of Docker Compose sort of situation.and I said, okay, I, I did this Gilded Rose thing that I was talking about for the, over the last couple days.

[00:14:19] **Ben:** So I copied in that ColdFusion component and I, and I said, you know what, take a look through this Claude and see if there are ways that I can prove it. Like I'm just baby stepping in just to kick the tires, see what it can do, and it goes off and it, it initializes with this CLAUDE.md file and it starts reading the things.

[00:14:36] **Ben:** And, you know, it's, it's tabulating and scintillating. It does, it does all these like little made up words. Yeah. It's levitating and whatnot. And it comes exactly all, all the operations. And, it comes back. And like my, my first reaction, I hate to say this, my first reaction, I was like, this is actually pretty good.

[00:15:00] **Ben:** And these suggestions was like, like, okay, so I've been avoiding all of this stuff for a long time and in my head I've had this story. It's just gonna be awful. It's gonna produce awful code. It's not gonna understand the way I like to write stuff.

[00:15:14] **Adam:** a year ago you would've been, right?

[00:15:18] **Ben:** And, and I'll tell you, I mean like the suggestions that it had, I didn't agree with all of them we're, we're like pretty spot on. And, and I was super impressed because I didn't really even explain what the code was doing. I said, I think I said maybe it's a text differing al algorithm. Look through it, come up with, with, with improvements.

[00:15:38] **Ben:** And it gave me, I don't know, six or seven things to improve. And I disagreed with two or three of them and I agreed with four of them. And we just started iterating. I said, okay, let's, I said, I said write this list to a file so that we can walk through it. And that I literally, like, that's what I said.

[00:15:54] **Ben:** I said, just write this list to a file so we can work it. And it did it, it put in a list, it did all these like check boxes and, and then it knew how to pick up where we had left off. 'cause I had to

[00:16:04] **Ben:** quit

[00:16:05] **Adam:** kind of file did it do? Did you like Plain text? Markdown.

[00:16:07] **Ben:** I think it did a markdown file. I think like every file, it's written as a

[00:16:11] **Adam:** It does seem to really love markdown files as input and output.

[00:16:15] **Ben:** But, okay, so I'm doing this and at the same time, I'm sort of struggling with the sandbox because the Sandbox has a really restrictive internal network proxy. So I couldn't, I couldn't quite get it to get all the network requests, right. so I'm turning this VM via, this, this Docker sandbox off, and I'm turning it back on and that resets the CLA session.

[00:16:36] **Ben:** And I would say too, it just, you know, let's pick up where we left off. And it just figured it out. I don't, I don't get how it did that,

[00:16:44] **Adam:** So there is a, there's, I, I don't know how this would interplay with the Docker sandbox and, and shutting it down, starting it back up. this may or may not have any effect on, or that may or may not have any effect on this, but you can like exit Claude and then you could do Claude dash dash continue and it will pick up like as if you had never exited your last session, has like all that same context window, or while you're in Claude, you can run slash resume and it'll give you a list of recent sessions and you can like arrow up and down.

[00:17:12] **Adam:** It gives you

[00:17:13] **Adam:** like that initial prompt, as like, okay, which one of these do you wanna work on?

[00:17:17] **Ben:** I wonder if that's what the sandbox is doing behind the scenes. 'cause you don't, I don't, I never run the Claude command. I just turn on the sandbox and it's doing something like, it just dumps me into Claude.

[00:17:27] **Adam:** Right.

[00:17:28] **Ben:** But okay, so, so I, I'm going through all these turn offs, turn back ons, and I'm just saying, Hey, let's just pick up what we left off.

[00:17:36] **Ben:** And he'll say, okay, we've completed one and two. Now we're on number three. And. It'll start working through, it'll like, okay, here's my recommendation. And I'll look at it and say, all right, well, I don't quite like the way you're doing it this way. I think this part should be factored out into a private function inside the CFC.

[00:17:53] **Ben:** And it goes off and it fan tabulates, and it scintillates and it coagulates and, and, and then it comes back and you know, it, it maybe cooks for 30 seconds, a minute, two minutes maybe. And it comes back with stuff. And, and it's showing me here's what it thinks it's gonna do. And it took me a while to understand when it was showing me stuff versus when it actually did something to a file.

[00:18:16] **Ben:** And, so, you know, use Git obviously is a, a day one lesson here. but okay, so as I'm doing this, I'm still thinking like a, like a regular programmer. I want to make this one tiny change. let's do this one small refactoring, and then let's do this one refactoring to a method, and then let's do this one renaming of variables and let's replace these two,dot replaces with an re a regular expression replace with a little bit of a regular expression pattern.

[00:18:42] **Ben:** and that, that was basically my entire Monday was just sort of stepping through all of these optimizations that it was making. And that was sort of my taking my, my perspective as a regular developer and trying to apply the Claude lens to it. You know, not really kicking, not really making Claude do too much.

[00:19:04] **Ben:** And again, I was just like super impressed actually with what it could do. my biggest fear was, is it could, it was just gonna do bat your crazy code style, you know, like spaces and like single quotes and, and like not having enough white space for my, and you know, like not having padding around parentheses and stuff.

[00:19:23] **Ben:** And like every piece of code that it wrote looked, I'd say 95% like code that I would

[00:19:31] **Adam:** Mm-hmm.

[00:19:32] **Ben:** And it was going off basically one, or I think maybe two different files. I had a CFC that had the algorithm, then I had a CFM to do the, the visual, rendering.

[00:19:44] **Adam:** Mm-hmm.

[00:19:44] **Ben:** And I don't know, I like, again, I'm just, I was very impressed that it could actually do the things that I thought it was going to very obviously fail at.

[00:19:52] **Adam:** Yeah.

[00:19:52] **Tim:** Yeah.

[00:19:53] **Ben:** All right. So, so, so then today I said, okay, let me push it a little bit harder. I said, or actually, let me also just say that as I was doing this, it just started writing tests for me. Like I never asked it to write tests. It just wrote tests. It figured out how to run it, figured out how to run them. And every time I had to make a change, it would just automatically run the test and it would find an error and then fix itself and then rerun the test until the error was gone.

[00:20:22] **Ben:** And

[00:20:22] **Ben:** again, like literally, I never asked it to do that.

[00:20:24] **Tim:** is It writing it in test box?

## [00:20:26] Claude Writes Tests Automatically

[00:20:26] **Ben:** no, it was just, it had just written its own.

[00:20:29] **Tim:** Its own test.

[00:20:30] **Ben:** Yeah. And like I, I, it gave it a, it gave it an endpoint to run like a, I dunno, test CFM or something. And it would just look for the output. It would basically do a curl against the,endpoint, and then it would look for text inside the response.

[00:20:49] **Ben:** It was just bonkers.

[00:20:50] **Adam:** I mean, in terms of tests, you know, like

[00:20:52] **Tim:** It obviously didn't learn that from you.

[00:20:54] **Ben:** Yo. And also, okay, so here's something.

[00:20:58] **Ben:** So

[00:20:58] **Adam:** it from you.

[00:20:59] **Ben:** as I'm going through this, I'm sort of evaluating my feelings. You know, I'm trying to, I'm trying to be introspective and I'm trying to reserve judgment as much as possible, but I'm trying to not ignore the, the, the tinglings and the jinglings that I have. And leading up to this, before I had done any of this, all I've really heard is stuff on podcasts.

[00:21:20] **Ben:** And people would talk about how Claude is fantastic at generating tests. And people don't even look in their tests. And then I would hear other people react to that saying oh my God, you can't have Claude write your tests. that's supposed to be the source of truth for how your application runs.

[00:21:35] **Ben:** Like, should never leave that up to ai. And you know, the second in row test. I immediately thought to myself, well, that's great. I never have to look at those again.

[00:21:44] **Tim:** See, I knew that was gonna be the takeaway you took.

[00:21:46] **Ben:** Yeah.

[00:21:47] **Adam:** But you know what,

[00:21:48] **Ben:** I was so ready to just hand over the

[00:21:50] **Tim:** better than none.

[00:21:51] **Ben:** and it like, in a disturbing velocity of,

[00:21:54] **Adam:** if, if this is what gets Ben to write tests, I'm okay with it. Look, so it's a, it, would it be better if there was like a hundred percent human input on those tests? Maybe, but also. I

[00:22:08] **Ben:** is better than no tests.

[00:22:09] **Adam:** that, yes, and also I don't write tests as well as, you know, somebody who does TDD all day every day does.

[00:22:16] **Adam:** Right? Like I, I'm not an expert test writer. I'm, I'm better at manual testing than I am at automated testing. And I struggle with it, and it's frustrating. And when I have Claude write something, I'm say, you know, Hey, by the way, write tests. And I read the test and I'm like, this is way more thorough.

[00:22:31] **Adam:** And Oh, cool. I didn't realize you could do that. And, you know, that sort of thing. it, it's just better at writing tests than me. And I'm fine with that. I read it, I make sure it's, you know, reasonable and, and correct. you know, I, I submitted a PR yesterday that had I don't know. 80 tests in it that I didn't write, and I read 'em and they all made sense to me and I submitted it.

[00:22:51] **Adam:** And then the, the one note I got back on the PR was like, you know, shouldn't this test be doing this? Instead of that like checking, like a expect X to be undefined should be like, expect X to be this invalid string or something. Right?

[00:23:06] **Adam:** Like just like a, a a nuanced little thing. I'm surprised that the person even picked up on it when they reviewed the code, but they did.

[00:23:13] **Adam:** And I was like, yeah, I think that sounds right to me. And I went and I, I looked at the, the code and the test. I'm like, based on the kind of implied spec here. Yes. That's the, the change you requested is, is a good change. So I made the change myself and, and pushed it, but like my tests are better thanks to having AI write them.

[00:23:34] **Ben:** Yeah. Well, I will also say that I was. Kind of blown away at the robustness of the test or, or like the landscape of the possible outcomes that it

[00:23:46] **Adam:** Mm-hmm.

[00:23:47] **Ben:** plucked out of thin air. So the way the text diffing algorithm works is you give it a, an original string and a modified string, and it spits back. Here are all the add, remove and equals operations.

[00:24:02] **Ben:** It would take to, to basically go from the original to the modified.and part of what the result does is just I, in addition to the set of operations, I also return a little stats struck that says, this is how many ads there were. This is how many deletes there were. This is how many equals there were.

[00:24:19] **Ben:** So when it wrote the test, again, completely unprompted. It ran through all of the possible combinations. It's like, here's what happens when we do completely equals things, and here's what we do when we only expect one equals and one delete and no inserts. And here's what we expect when it should all be deletes.

[00:24:34] **Ben:** And here's what we expect when it should all be inserts. And, and then it did it for case sensitive and case insensitive. And again, like I didn't explain any of this, it just did it and that was kind of, it was like both exciting and terrifying at the same time. Alright, so, so that was yesterday. That was the kind of just kicking the tires, trying to get my sandbox running, trying to understand how I could work through little details.

[00:24:57] **Ben:** And today I wanted to do something a little bit grander in scope. So, I wanted to say, okay, what I'd like is to. Take the simple ding. And now I want to add a way to not just diff the string, but have a whole rendering thing where you could automatically have it render the, the ads and the removes.

[00:25:18] **Ben:** And then if there was a, a delete followed immediately by a single line delete followed immediately by a single line add. It wouldn't just show you that one was added and removed, but it would show you which words in the line were added and removed. This is what GitHub does. This is how I came up with the idea.

[00:25:33] **Ben:** and I said, I don't know how that works. Let's just do it. And it went off for five minutes, you know, fan tabulating and justifying and all that jazz. And it came up with just a really robust plan for how to do this. And again, like its code looked, I'd say 95, 90 8% awake. I write code because as I was finding little things yesterday, I was saying add to your memory that,compound logical.

[00:26:03] **Ben:** Equations should always have parentheses wrapped around them. And if you have a return statement, it should always have a space after it if it has a parentheses or an expression after it. And it would add those to its CLAUDE.md files. And like I articulate it like a mad person, and then it compacts it into something meaningful for its CLAUDE.md files.

[00:26:20] **Ben:** So it just, and then it like basically just stops making those problems more or less. It still does, when it, when it, when it's doing a lot of things at the same time. But anyway, so I had to do this bigger thing and the way that I had it work today was Peter, my boss. It had me install this Claude plugin called feature Dev. And Feature dev is, I think so. I think Claude has for a long time had a slash plan, which basically asks a

[00:26:49] **Adam:** playing mode. Yeah.

[00:26:50] **Ben:** yeah. Yeah. So I think feature dev is sort of the paved cow path of that concept. Basically, the guy he works for, Claude took that idea of plan and codified it into a plugin where it'll ask clarifying questions and then it'll present you with several, it, it presents you with three different options.

[00:27:10] **Ben:** It's like, here's the smallest possible set of changes we can make. Here's the sort of medium set of changes we can make, and here's the cleanest possible architecture, but probably has the most number of changes to make. So it comes up and it's running these agents in parallel trying to come up with these plans, and you pick which one you want and then you can refine it, and then finally you're just like, okay, do it.

[00:27:31] **Ben:** And it just spins off and, you know, tabulates and contemporizes and collates and, and it wrote code and like it worked. Like it just worked. And I looked at the code, and the code was, again, it looked like code that I would write. And it was crazy and it was exciting and it was terrifying at the same

[00:27:53] **Tim:** characters wide By

[00:27:54] **Ben:** Oh, that's the other thing. That's the other thing, like, okay, so I have a strict, so I have, in my sublime text, I have a visual ruler that's always rendered and it's rendered at 90 characters. And so all of my code for the most part, unless it really has to go beyond I, I, I, I keep everything within those 90 characters.

[00:28:12] **Ben:** And it did that, it did that for all the code that it wrote, even code that was like a giant comment block. would wrap it at 90 characters. And again, I didn't tell it to do that. It's so just like there was a lot of those little niceties where I'm just shocked that it didn't screw up. And I was kind of hoping it would screw up.

[00:28:28] **Ben:** ' cause you know, that's what I wanted. Yeah. And I was, I was both excited and saddened to be prove proven wrong.

[00:28:37] **Adam:** So this whole episode

[00:28:38] **Adam:** is just, the gif of the guy that like black turtleneck guy

[00:28:41] **Ben:** Yeah, yeah,

[00:28:42] **Tim:** Yeah.

[00:28:43] **Adam:** like his, his hands up by his head. It had exploding and the, the galaxy,

[00:28:48] **Ben:** yeah,

[00:28:48] **Tim:** Yeah. I think it's Andy.

[00:28:50] **Tim:** I think it's Andy Kaufman. I think that's who

[00:28:52] **Ben:** yeah. Yeah. I think you're right.

[00:28:55] **Adam:** I never noticed that, but that's it. That's okay. Anyway,

[00:28:57] **Adam:**

[00:28:57] **Adam:** yeah, I mean, it, it, it's pretty cool. It does some cool stuff. It's good at it.

[00:29:01] **Ben:** It, it was pretty cool. And I would tell the thing, so it, it would, uh, sometimes if I wanted to refactor a method, split it up into something else, it would just put the new method right below the method that that was using before. And I said, no, you can't do that. That's not how I code. I said, I, I split my ColdFusion components up into section, so I have my constructor at the top, and then I have public methods, and then I have private methods.

[00:29:23] **Ben:** And I said, within each one of those sections, it should be listed alphabetically. And I said, oh, yeah, no, of course, no problem. I'll just do that. And it added some notes to the CLAUDE.md file. It moves some functions around. And then again, like going forward, every time I had to add a new function, you know, I'd say five out of six times it did it right.

[00:29:41] **Ben:** And then occasionally it would do it wrong and I'd have to remind it, and then it would fix it. But it just, it was a lot easier to get it to look like my code than I. Thought it would be. And the only reason I stress this is because to me the way the code looks is so important. that's just how I feel emotionally satisfied that the code is good.

[00:30:03] **Adam:** the more you vibe, the less you'll be looking at the code, and so it'll matter less and less to you over time.

[00:30:08] **Ben:** Yo, I know. And that's the scary part for me is well go Before we get to that for a second, this is something I wanted to ask. 'cause you were talking about at the top of the show here, how you had your AI policy written by AI first pass on ai. And so when I first started to experiment yesterday, and it was committing code, I was noticing it was just randomly writing commit messages, which is fine.

[00:30:31] **Ben:** And then it was saying this commit co-authored by Claude Code agent or something like that. I don't remember what it said

[00:30:36] **Ben:** exactly.

## [00:30:38] Co-Authored Commits Discussion

[00:30:51] **Ben:** And so one of the first rules I set in the CLAUDE.md file was I said, Hey, I'm the only one responsible for this code. If it goes to production, it's my fault if it breaks. I said, I don't want people to think I'm like, I don't want you to be the

[00:30:52] **Tim:** You can't be fire code.

[00:30:54] **Ben:** Yeah. I'm like, I'm the author. Please don't put your co-author signature in any of the commits. And I don't know, I just wanna throw that out there. I feel like that makes sense to me, but I, I didn't know how people feel about that. Is that, am I just overreacting

[00:31:06] **Adam:** I'm glad you brought it up. 'cause I have feelings and I, I don't know which way I come down.

[00:31:11] **Ben:** So

[00:31:11] **Tim:** Uh, my, my gut feeling without a super hard thinking about it is I just, I feel if you put that, that ai, LLM, whatever you wanna call it, has co-authored something with you. If it works, no one will ever look at that and go, oh, that's, 'cause Claude did a really good job. But if it breaks,

[00:31:29] **Tim:** everyone's gonna, everyone's gonna blame you.

[00:31:31] **Tim:** Like, well, you should, shouldn't have used AI in this. It's critical part of the infrastructure. You really should have looked at it yourself. you'll never get kudos for that, right?

[00:31:39] **Tim:** So

[00:31:41] **Tim:** what's the point of putting,

[00:31:42] **Adam:** so this is, you asked my, my feelings on it. on one hand, I agree with you, Ben. I'm responsible for the code that I generate, whether I generate it with my fingers on the keys or with, Claude or, or whatever else. And so I, I mean, I, I truly feel that ownership. And so I kind of started from the same position.

[00:31:59] **Adam:** But then the other side of the coin is am I hiding the fact that I used an LLM to help me with that by removing that co-authored note? and like it almost feels dirty, like I'm hiding a secret by taking that out.

[00:32:14] **Tim:** But, but as, but as we showed earlier, there are hooks in the background where we, managers and enterprise level people can see just how many lines of code you've accepted. We don't see to the

[00:32:23] **Tim:** granularity

[00:32:23] **Tim:** of of which ones, but it's yeah, if you're 40,000 lines of code accepted this month, you, you, you know that they're using it a lot.

[00:32:32] **Adam:** Yeah,

[00:32:33] **Ben:** So, okay, if I can follow up with another thought here, which is that earlier in the show I said that when Claude wrote tests, I immediately regressed to, okay, I don't have to care about tests ever again, essentially. And,

[00:32:47] **Adam:** did and I never will.

[00:32:49] **Ben:** but it, it was like I had expected to not want to fall into that, into that feeling, and then immediately fell into that

[00:32:57] **Tim:** as as soon as it worked and it looked good, you're like, yes,

[00:32:59] **Tim:** that's fine with me.

[00:33:00] **Ben:** A hundred percent. So I think part of wanting to remove the Claude byline from the commit is I do feel like if Claude is visually a participant in the authoring of this, I just think part of my brain is gonna be like, I just don't have to be as critical about this code.

[00:33:24] **Adam:** It's real easy to, to, oh, okay, it's done. I can just accept that. And I'm sure it did a fine job. 'cause 99% of the code that it writes is great. So,

[00:33:32] **Ben:** Right. And it's like, it looks good, and the test seemed to pass. I'm like, all right, it's fine. But I, I just feel like I'm gonna, I'm gonna slowly abdicate some of my responsibility.

## [00:33:42] The OCR Mishap

[00:33:42] **Adam:** I probably should have put this in as a fail. I just remembered something I did. or, or late last, I think it was yesterday. Oh my God.

[00:33:50] **Adam:** So, okay.

[00:33:51] **Adam:** I've talked about how much I love Raycast, and,

[00:33:54] **Ben:** the Spotlight competitor?

[00:33:56] **Adam:** yeah, spotlight or Alfred, if you're familiar with that. and it's like a launcher thing and it's got a LA ton of really useful features and I still love Raycast even after what I'm about to explain to you.

[00:34:06] **Adam:** one of the features that I use heavily is the clipboard history, right? You just copy a bunch of stuff to your clipboard. You can do command shift V instead of Command V, and it gives you like a list so you can just scroll through all the recent stuff off your clipboard, including images, right? You can take screenshots and have those go to your clipboard.

[00:34:21] **Adam:** and you could

[00:34:22] **Adam:** just scroll back through your, recent clipboard stuff and while you're doing that, while you're going through your, your clipboard history, if it's an image, there's like a little actions thing and you can say, copy the text out of this image. Right? And so it's basically you take a quick screenshot of something and then you could OCR it and just copy and copy the text out of whatever it was.

[00:34:41] **Adam:** You took a screenshot of.

[00:34:42] **Ben:** Pretty cool.

[00:34:43] **Adam:** So I had, I was fixing a bug. and the problem was it was very naive code. It was literally like insert into table name, select star from other table name, and it's it's an archive process copying data from one table to another and with a bunch of wear stuff specified after that. I don't remember why it was, you know, it was probably years ago that the like archive table was created. And they don't, they have all the same columns, the same types and everything, but they're for whatever reason in a different order,

[00:35:10] **Adam:** right? And so the bug was, all the data was being copied, but it's going in the wrong columns. Right. You've got dates showing up in text fields and a bunch of date fields are blank because they got like text thrown at 'em or whatever. Anyway, so I was fixing that and I was like, oh, I know I can do this real quick. I just popped open. My DBMS took a quick screenshot of the list of columns in the table, ocr, the, the list of columns out of the, the screenshot pasted in looks good to me.

[00:35:36] **Adam:** Ship it. and what happened? a bunch of, I as in you know, message id, the, I being an uppercase, I, for whatever reason got ocr. That's a lowercase L

[00:35:46] **Adam:** and15 places.and, and I didn't catch it. It went to production, started throwing errors. Somebody else, started seeing the errors and, and submitted a poll request to fix it.

[00:35:57] **Adam:** and they caught, you know, the first, like eight of them. And then a couple hours later, another poll request, they caught like another four of them. And then another poll request. A couple hours later they got more. I'm like, oh my God. That is the last time I ever do that. Actually, this was late last week 'cause I, I brought it up on our team standup on Monday, but,

[00:36:14] **Ben:** Oh man, that the

[00:36:16] **Tim:** that, that, that's when you say, yeah, Claude did that. That wasn't me.

[00:36:19] **Ben:** Yeah. So I was just listening to an interview over the weekend and someone was saying that, the OCR capabilities of the LLMs are actually outperforming the like native OCR technology.

[00:36:37] **Adam:** I, I, we've said OCRA bunch of stuff. I just wanna, I don't think we've actually said OCR stands for optical character recognition reading text out of images.

[00:36:44] **Ben:** Yeah, and I mean, I, I've, you can do it on, on, the preview app on Mac, and even if you take a photo with the iPhone, you can, I think, like press and hold on text in the photo and it'll give you the ability to copy it, which is really great on, you know, when you're out and about and looking things up off of signs.

[00:37:02] **Adam:** Yeah.

[00:37:03] **Ben:** but yeah, they were saying that the OCR is like only 60 or 70% accurate, but that the LLMs have proven that they're like 85, 90% accurate,

[00:37:15] **Ben:** just 'cause they're trained on so much

[00:37:17] **Ben:** image data. No,

[00:37:18] **Ben:** no,

[00:37:19] **Tim:** if I, if I can get it in text, so Adam's saying that he did that, I'm like, that surprises me. 'cause I would've just gone to the table, generated the create

[00:37:26] **Tim:** script, pasted

[00:37:27] **Tim:** that in, and then it would have everything. It would not only know what the table name table and fields were, but you know, what

[00:37:34] **Tim:** data types they are and all that stuff.

[00:37:36] **Tim:** Right. So anytime I have to, because I do that a lot, it's like just some data manipulation. I just say, here's the schema, here's the sample row of stuff that I've got. Create me some, you

[00:37:45] **Tim:** know, scripts to do that and.

[00:37:47] **Adam:** Yeah. I, I am very much, you know, this is as kind of, Ben was alluding to, like, I'm very vs code pilled at this point. I, I heavily used multi cursors. so yeah, if I didn't have that OCR thing, if that wasn't my gut reaction, I probably would have done what you said, copied the create table syntax.

[00:38:03] **Adam:** Dropped it into a cursor or vs code window, done multi cursors to just select all of the, column names. Just copy and paste that out so that, that's the only thing on the lines. And then paste that into where I wanted the code to be.yeah,

[00:38:16] **Ben:** Yeah. So

[00:38:17] **Adam:** you can bite it, it can bite you real, real easily if you're, if you get lazy.

[00:38:21] **Ben:** yeah, so that was actually one of the things that, again, using Git, any kind of source control, but I assume basically everyone's using Git. It is super important and I was trying to commit in between each. Smallish change that I was making day one. So yesterday, and there were one or two times where we would sort of go down a little bit of a rabbit hole and I said, you know what, after seeing this being implemented, I don't think it's a good idea anymore.

[00:38:46] **Ben:** And I said, just reset the branch. And it wiped out all the stuff that it had just done. Now I think maybe Claude has some stuff that it keeps behind the scenes that would make that easier even without Git, but I'm not a hundred percent sure on

[00:38:58] **Adam:** Oh. To be like, I don't like these last changes that you made. Undo it.

[00:39:01] **Adam:** Yeah, I feel like I was watching one of Theo T three nine Guy or whatever. T three. Just

[00:39:07] **Adam:** T three T. I, I, I feel like he's talked about that. Or maybe that was cursor. Maybe Cursor has a dot folder where it keeps some sort of pending changes that it can revert.

[00:39:16] **Adam:** Well, there's work trees, cursor in particular has an interesting work trees feature, but

[00:39:21] **Ben:** Okay, then maybe

[00:39:22] **Adam:** get work

[00:39:22] **Ben:** was what he was demoing. But anyway, the source control, obviously super important for rolling back, generally speaking. Also very important for this kind of stuff. And, yeah, so that, that brings me, that's that's my sort of brain dump here. it's lot, it's a lot to take in.

[00:39:37] **Ben:** It's a lot to try to understand where I live in the world now.

[00:39:41] **Adam:** yeah.

[00:39:41] **Tim:** yeah.

[00:39:42] **Ben:** And also, Yeah.

[00:39:43] **Ben:** go ahead.

## [00:39:44] Managing Context Windows

[00:39:44] **Adam:** uh, well I wanted to ask you, you know, you, you talked about this usage a lot. One thing you didn't really mention was thinking about managing the context window, right. In these sessions where you're using Claude, talking to Don to do stuff.

[00:39:59] **Ben:** Right now, I've just been talking at it

[00:40:02] **Adam:** Yeah.

[00:40:03] **Ben:** until it's in, until I have to restart my VM or something. I didn't, I I, I never at one point did a compact or summarize or whatever it does.

[00:40:11] **Adam:** I do think it has like automatic compaction built in. If you get to a certain

[00:40:15] **Adam:** fullness of the context window, it'll automatically compact. I try not to use that. I personally, so I, I've been having a lot of success with it. and I basically, my rule of thumb is once I get over 40,000 tokens, so the, the limit for Opus Claude, is, it, is, it's Claude something, Opus, right.

[00:40:35] **Adam:** I don't know, whatever.

[00:40:37] **Adam:** op, the, the new, the latest opus, whatever the, the token limit is 200,000. Once I get to about 40,000, I go, okay, I need to start wrapping this conversation up so that, it doesn't start to get dumb. Right? Like the, the more stuff you stuff into, the more things you stuff into context.

[00:40:53] **Adam:** like the, the more there's the,

[00:40:57] **Adam:** the, the the lower, the like signal to noise ratio is right. So the longer that conversation goes on, the more the early part of the conversation that doesn't matter anymore. the more kind of like important, it weights that, or, or the, the newer part of the conversation is less weighted, I guess is a better way of saying it.

[00:41:15] **Adam:** so yeah.

[00:41:16] **Tim:** I don't know if this is the best, this is what I do. 'cause I've ran into that where you're like, start the context window starts getting really, really long and it starts making really dumb mistakes. At the

[00:41:26] **Tim:** beginning it was a genius, and now it's like starting to make some dumb mistakes. I feel like almost like a video game, when you get to a good save point, right?

[00:41:33] **Tim:** You're like, okay, I just, I just, I'm just about to attack the big monster. So let me save right here. And, And,

[00:41:40] **Tim:** so what I'll, I'll tell Claude to do is summarize everything you've done up to this point. Create a markdown

[00:41:45] **Tim:** file for me and then I'll use that. I'll reference that markdown file and start a new.

[00:41:51] **Tim:** Conversation and say, based off of this conversation, now, dude, let, let's go attack this. Maybe this section of code that I'm super, super concerned about. 'cause I know it's difficult. and sometimes it works and sometimes I don't know. It doesn't. So I don't know if I'm, I, I've made that up. I've never read that.

[00:42:08] **Tim:** That's a good thing to do. So don't quote me on that.

[00:42:11] **Tim:** But that's, I, I more do it more for my own. 'cause when I start, particularly if you're like not really sure where, where you want to go and you've gone down a couple paths and they're not working out, I'll kind of back up and say, all right, let's, let's take an assessment of where we are now.

[00:42:25] **Tim:** I'm happy with it up to this point.

[00:42:28] **Tim:** Write me a markdown file very concisely that just says what we've done. And then I'll start working off of that one.

[00:42:35] **Tim:** Yep.

[00:42:36] **Ben:** I, I wonder if it would be helpful to give Claude like a whip, a work in progress folder that it could store stuff into, because I, it seems to just willy-nilly write text files wherever it wants to.

[00:42:47] **Tim:** I, I do tell it where to store, like

[00:42:50] **Tim:** document, it's not necessarily documentation 'cause it's not necessarily documentation. Like it, yeah, a WIP I guess is kind of a good name for it. I don't call it that, but yeah, I have a folder that I ignore 'cause I don't want it in my code, I don't want it pushed up to GitHub.

[00:43:02] **Tim:** but just a bunch of MD files that particularly if like I'm working over several days, if I wanna come back to it, I can go look at the markdown file and go, okay, I remember now what we were working on and where we're at, and then attack it from that point.

[00:43:15] **Ben:** Yeah.

[00:43:16] **Ben:** So, sorry, go ahead. Well, okay. I was just gonna say, so the last two days I've been working with Claude Code, but to your point with the context window, it's really been like three files. It's, you know, it's,

[00:43:29] **Ben:** it's

[00:43:29] **Adam:** you're, if you're, if you're asking and answering questions a hundred times, then that's filling up that context at the bottom of the

[00:43:36] **Adam:** window. It'll show you like token usage.

[00:43:38] **Ben:** But I, I all, all I, all I wanted to say was that, as far as the scope of changes that it could possibly make, it was still very limited in terms of, you know, cognitive load, breadth of files changed. Even when it was making a bunch of little changes at one time, it was still in a relatively confined space.

[00:43:57] **Ben:** And that I can understand because one, it's small, and two, it's the code that I was personally working on where I feel really actually quite nervous is what happens when someone else on the team commits code that I have not seen before. And, you know, I go to my command line to a git pull. You know, it's the morning I'm about to do my work.

[00:44:19] **Ben:** Let me do a git pull to refresh the development branch, see what's there. And, you know, 175 files come down. I don't, I don't have today. The mechanical patterns, the muscle memory, to know even how to begin to process that change. Like, how do I take that new change of someone just dumped on my face and, and, and weave it into my mental model of how this application

[00:44:45] **Ben:** works?

[00:44:47] **Adam:** review every commit or, or all the new changes as they come into your development branch from your coworkers every day?

[00:44:54] **Ben:** No, no, no. But I, it's usually small enough where I can say, oh, three files came down. It's in this area of the app. And I can at least make a mental note like, oh, someone's working in invoicing, or someone's working in user management. It's not like someone has refactored the way, link navigation works on a hundred different pages.

[00:45:14] **Ben:** You know, something like that.

[00:45:16] **Adam:** I understand the concern, but this is another reason that testing is useful, right? So if that person is modifying all those files and they're, they're putting in tests, then you don't really have to worry about it. If your changes conflict with theirs in a way that like you, you know, you're adding something that breaks their changes or whatever, then their tests are gonna fail.

[00:45:31] **Adam:** And, and then you go, Hey, I broke your tests. Let's talk about what you changed and why, and what I need to change. And we can figure out what the right thing is.or you just look at it and you go, oh, okay, they wanna do that now. Fine. That's, that works for me. You know, whatever. But the, the tests become a really useful tool in this whole like, iterative process.

[00:45:51] **Ben:** Oh, it's so, it's so funny slash frustrating because I think even two episodes ago we were having a related conversation and I said one of my big fears is that I'm gonna need to have. Mechanical solutions to human problems. And I feel like that's exactly where we are now. Like, yes. there's too much people in to be done, so we're gonna have to solve it with something engineeringy

[00:46:16] **Adam:** Yeah.

[00:46:16] **Ben:** and like, not that that's a bad thing, it was more like a, a a bumper in a bowling lane.

[00:46:23] **Ben:** Like I, I hit the side. no, that's a terrible, maybe it's a

[00:46:26] **Adam:** It's the, it's the feelings.

[00:46:27] **Ben:** Yes, exactly. It was like something, it's a, it's a, a whiff of code smell, not even code smell of people smell the best guy

[00:46:36] **Ben:** and

[00:46:37] **Adam:** Yeah.

[00:46:38] **Ben:** that something is weird. And, I guess that's just the reality now.

[00:46:42] **Adam:** Yeah. So we've talked a good bit in the last couple minutes about, like context management, right? And how, you know, if, if you are doing deep work, right? I'm making significant, complex modifications to the code. It actually doesn't take that long to kind of pollute the context pool with stuff that's just irrelevant to the next thing that you want to do,

[00:47:03] **Adam:** right?

[00:47:03] **Adam:** So you've got, you're working on a project, you've got two weeks of work ahead of you. and, and so, you know, you've got a lot of little tasks to do. So, you know, the way the, the things that you guys were describing there, it's funny how much they parallel. If you remember from,

## [00:47:20] The Ralph Workflow

[00:47:20] **Adam:** I think it was last week, it might've been the week before that I was talking about Ralph.

[00:47:23] **Ben:** Yeah. Ralph Wiggum.

[00:47:25] **Adam:** yeah.

[00:47:25] **Adam:** Tim was talking about, you know, okay, summarize what we've learned here in the last couple minutes and write it out to this file. And, and then you'll like, close that session, start a new one, and, and reference that as like a starting point to kind of like prime the pump.

[00:47:37] **Adam:** and, and even the whole, just like, close that session, start a new one just to get a, a totally empty context window to start your conversation with. That's useful stuff. those are the foundational principles that go into the whole Ralph technique.and actually I'm gonna, I'm gonna try something, I'm gonna share my screen with you guys.

[00:47:56] **Ben:** I see. I assume this is sublime text.

[00:47:59] **Adam:** this is, you would, this is Cursor my friend. so, basically I, I have up on my screen here for these guys. it's a shell script, right? It's just for me. It's called Ralph sh this one. so the, we were talking about managing context, and so the idea here is like to build automations that make it easier to work in that way, in a long-term automated fashion.

[00:48:27] **Adam:** Right? So the first thing that I actually do, I don't have it pulled up here. gimme a sec, cursor.

[00:48:36] **Ben:** But basically it looks like it's a command you can run. You can pass in as an argument. The number of iterations that are possible.

[00:48:43] **Adam:** Yes. So

[00:48:44] **Adam:** yeah,

[00:48:44] **Adam:** the, when I, when once I'm ready to get down to work, I just run Ralph and then I pass it a number, like I might say, you can run a max time, max 20 times or whatever, right? And that way it'll never get into an infinite loop and, and just run and do nothing. so, you know, whatever that number is, once you get there, just stop and, and let me review your progress.

[00:49:03] **Adam:** but. I'll read you the prompt. So basically it just runs a for loop, right? So it's like up to my max iterations print iteration, and then the current iteration number, and then run Claude with, a couple of flags like permission mode, accept edits, right? That's the, don't

[00:49:17] **Adam:** ask for permission to write.

[00:49:18] **Adam:** No, this is very

[00:49:19] **Ben:** Oh, oh, oh. Okay.

[00:49:21] **Adam:** So accept edits. This is like norm. If you just start Claude and you say, I want you to do this, it's gonna go, okay, these are the changes that I wanna make. Do you want me to edit this file? And you can say yes, or you can say yes and always allow editing during this session.

[00:49:36] **Adam:** Right? That's the like middle option. That's what this is. This accept edits,

[00:49:40] **Ben:** Okay. Gotcha.

[00:49:41] **Tim:** So you can look at it, you can look at it and say, no, I don't like that. And do

[00:49:44] **Tim:** so tell it. It'll say what you want me to do other than

[00:49:48] **Adam:** Right, if you're running in like interactive mode. And then the next thing I have here is a dash P. So it's claude dash dash permission mode, accept edits. Dash P, which is like print is it, which basically means run in like headless mode.

[00:50:00] **Adam:** Just run in the background. When you're done, print out the output and then I've got a, a string after that, which is my prompt. So I wanna read the guy, read you guys the prompt. it was also for the benefit of the listener, so it says Study Ralph slash prd json. So Ralph has just like a folder name in my

[00:50:17] **Adam:** project,

[00:50:18] **Adam:** where I'm gonna have some metadata files for what I'm doing.

[00:50:20] **Adam:** P is for, product requirements document json. So it's a JSON file, right? So study Ralph slash prd json study Ralph slash progress md. So that progress, md Tim, that's kind of like what you were referring to as like where did we leave off? What

[00:50:35] **Adam:** has been done, what lessons have we learned?

[00:50:38] **Ben:** Quick, quick interjection here. Your product requirements document as A-J-S-O-N strikes me as strange, is that the output of some other thing.

[00:50:47] **Adam:** It is. Yeah, we're gonna get to that,

[00:50:49] **Ben:** All right. Okay. Okay.

[00:50:50] **Adam:** So, study those two files and then here's the, the meat of the prompt. It says, one, find the highest priority item to work on and work only on that item. This should be the one that you, in all caps, you decide has the highest priority, not necessarily the first item in the list.

[00:51:05] **Adam:** And I should, stop here and just say, this is based heavily on,a similar script from Matt Pocock. I stole it. I modified it heavily. I've run a bunch of different, things similar to this, but, and I'll, I'll link to the video in the show notes where I got this. But anyway, so not necessarily the first item in the list two, check that the types check via NPM Run check.

[00:51:26] **Adam:** So TypeScript, code is what I'm working on in this project. So it says you can run NPM Run check to, to check. The TypeScript types if available, and that the tests pass via NPM run test if available. Three, update the PRD with the work that was done. Right. So I

[00:51:41] **Adam:** told it, you're, you're gonna be, working on this one feature when you're done, update the PRD to market as complete basically four.

[00:51:49] **Ben:** again, just just to emphasize here, you're saying update the PRD, but you're not saying update this specific file,

[00:51:56] **Ben:** it just knows what to

[00:51:58] **Adam:** Because I specifically called that file out at the top.

[00:52:01] **Ben:** I know, but like you didn't say this is the PRD file. I'm, I'm just underscoring that it makes these connections And it's

[00:52:07] **Tim:** that is, that is sort of a mind shift, is we've been all our life, we haven't been so specific

[00:52:12] **Tim:** with programming. You're like, no, you Ralph slash PD update the Ralph slash PRD

[00:52:18] **Ben:** Right,

[00:52:19] **Tim:** are too dumb to figure it out. Now you're just like, ah, it's the PD. They're

[00:52:22] **Tim:** like, what's PD? And it just goes, it must be this thing you talked about earlier.

[00:52:25] **Adam:** Yeah, absolutely. So that was three. Update the PRD with the work that was done. Four, append your progress to the progress.md file.

[00:52:32] **Tim:** Oh, progress text file.

[00:52:34] **Adam:** yeah.

[00:52:34] **Adam:** Yeah.

[00:52:35] **Adam:** I, this is, this is a, this was like a template that I copied into my

[00:52:39] **Adam:** project. I haven't updated the template, so I, I fixed it. Update your

[00:52:42] **Adam:** progress to

[00:52:43] **Tim:** at mdmd.

[00:52:44] **Adam:** file.

[00:52:45] **Adam:** Yeah. use this to leave a note for the next person working in the code base. So that way it like, kind of tells it how I wanna format the notes there. Five. Make a commit, make a git commit of that feature. And then there's a blank line and it says only in all caps, only work on a single feature. And then it says, if while implementing the feature, you notice that the PRD is complete, meaning everything is marked, passes equals true.

## [00:53:07] PRD Files and Automation

[00:53:07] **Adam:** I'll show you the PRD in a second, output. almost like it's XML, right? Promise. And then inside the promise is complete. And then end promise, like it's X XML or

[00:53:16] **Ben:** It's a.

[00:53:17] **Adam:** thing, right?and so that's the, that's the prompt that gets passed into Claude. and all that run. And this is like a bash script.

[00:53:24] **Adam:** So it runs in a way where we can capture the output of that command and save it as a variable called result. We echo that to the screen and then we check. Did that include the promise tag? Promise complete? If so, then it spits out, it echoes PRD, complete exiting. I've got mine playing a sound out of the, the system sound library.

[00:53:45] **Adam:** And then exit zero to just exit without, without an error. And so this is the, the basic form of Ralph, right? Just like in a loop, run this,prompt. And the prompt is written in a way that you can run the exact same prompt over and over, but it should always find new, different work to work on, right?

[00:54:02] **Adam:** Whatever's in that PRD file, and it gets to decide what's the next most important thing to work on, right? And it'll, it'll like figures out dependency order like I have to. If you, I, I, the thing I was running today was like, okay, we have this application in this folder. I want you to copy it to this folder, and I want you to make these changes to the config.

[00:54:23] **Adam:** And then we're gonna change the, the layout. Just get rid of that whole like, dynamic layout thing. We're just gonna do a static layout. You can delete these folders in this, in the routes, folder because we're not gonna need that. you know, I just have this, I'll, I'll get into it in a second, but I just have this conversation with it and say, okay, these are the requirements, and then you're gonna write them to the PRD JSON file.

[00:54:42] **Adam:** And, and then when I run Ralph, it's like, okay, this is the one I'm gonna work on next. And it does it.

[00:54:46] **Ben:** Yo,

[00:54:46] **Tim:** I'm interested to see your, your PD file.

[00:54:49] **Adam:** Okay, cool. So I've got a a PD example, json, and I copy this into my project as well, as into that dot Ralph folder. and, and this is just like for, I do this because then the, the next step after copy copying these files into my project is then I'm gonna run my plan script, which is just a separate Claude prompt that says, okay, we're gonna have a conversation to, to work out the requirements of this project.

[00:55:16] **Adam:** And then when we're done, you're gonna write it out to p js ON using pr Do example, do JSON as like a template.

[00:55:23] **Ben:** so just for the listener's benefit. Oh,

[00:55:25] **Ben:** okay. So it is A-J-S-O-N file and it is an array of objects, fairly simple objects that has category description, steps and passes. Those are all simple values except for steps, which is an array of step one, step two.

[00:55:43] **Ben:** I guess that's, Yeah.

[00:55:45] **Adam:** It passes is a boolean.

[00:55:47] **Ben:** thing.

[00:55:48] **Tim:** So, so is each step like a

[00:55:50] **Adam:** No, these are just like notes that it takes to, so okay. We're, we've looked at the example. Let me, let me pull in. let me see if I have my other window here somewhere.

[00:56:00] **Ben:** I, I, I wanna also say just as I'm, I'm using this at work now, and I have no idea how much any of this costs, which is, I'm, I'm feeling very thankful that I have no idea how much any of it costs because,

[00:56:12] **Adam:** my personal subscription is a hundred dollars a month.

[00:56:15] **Ben:** all

[00:56:15] **Tim:** enter enterprise or paying 1 25 per developer per

[00:56:19] **Ben:** developer per month.

[00:56:20] **Adam:** Yeah.

[00:56:21] **Ben:** All right. That's, that's reasonable. It's expensive, but it's reasonable,

[00:56:25] **Adam:** yeah, so, I've pulled up my, my prd json from my project that I was working on today. So we can look at, I mean, this is exactly what I just told you it was doing, right? So I had a conversation with my plan script, which I'll read you the prompt for that in a minute. But, this is what it spit out when I was done having that conversation, except where it says pass is true here, it said pass is false.

[00:56:43] **Adam:** That's how

[00:56:43] **Adam:** it writes it out initially from the template. And then as Ralph is going through and completing the, the steps here, when it's done, it just changes, passes. True. Sometimes it decides to add like notes, like you can see this one has a bunch of

[00:56:56] **Adam:** notes about the things it does. I don't care, whatever.

[00:56:59] **Adam:** but,

[00:56:59] **Tim:** so it's basically logging in the steps it took to complete the task that you gave it

[00:57:04] **Adam:** sometimes, yeah, sometimes it just marks it as complete.

[00:57:06] **Ben:** wait, wait. So are the steps, did it write the steps or you wrote the steps?

[00:57:11] **Adam:** So Ralph did not write the steps. My plan script wrote the

[00:57:16] **Ben:** Okay.

[00:57:16] **Ben:** Okay.

[00:57:17] **Adam:** right? So, but this is, you know, what we're just talking about. So like, okay, this first item in the list is category is set up. Description says clone pub sites SvelteKit to admins SvelteKit, right? This is a folder with the as we have our semi complete pub sites SvelteKit application.

[00:57:32] **Adam:** I'm starting on that admin, interface as well. So as I clone that folder to that folder and the steps are like, copy container slash pub sites SvelteKit to containers slash admins SvelteKit. And the next one is update package json to name admins SvelteKit, update description. next one is updates svelte.config js set path stop base from slash p to slash a, right?

[00:57:53] **Adam:** Like these are just notes for it to figure out or notes that it. It kind of summarizes my conversation with it and groups requirements together under like many chunks of steps, right? This is our clone and, and initial configuration sort of step, right? Okay. So it, it does all of that, spits that out to that Jason file, and then it can, you know, like just iterate on this file over and over until it's done or it's run out of iterations.

[00:58:19] **Ben:** There's hundreds of lines in this file, by

[00:58:21] **Adam:** Yeah. Yeah. So when I first did it

[00:58:22] **Adam:** this morning, it was about like 350 ish lines of code. it currently is at 634 lines because as the day is going on, I'm looking at what it's generating and I'm saying, oh, okay, well you messed up about this thing, so let me just add a new requirement that'll fix that.

[00:58:37] **Adam:** So I have, I pull up the plan script, even while it's running Ralph, I'll just pull up the plan script and say, you know, add this feature, add this bug fix or whatever. And it'll add more like this last, we're looking at the last item in the array. Right now it's a, this is one of the examples. so it's category is layout descriptions, move hamburger menu to the right side of the header because.

[00:58:57] **Adam:** Even though I gave it a screenshot and I told it where I wanted stuff it, for whatever reason, it decided to put probably, because that's where it usually is, they put the hamburger menu in the top left corner, like right before the, the logo.and so I, I opened it and I told it like, I need you to move the hamburger menu to the top right corner.

[00:59:13] **Adam:** And it's well, I don't understand 'cause it's in the, currently in the top left corner. And I said, no, you're wrong. It's in the top, it's in the top left corner. So,it, and it wrote that out here and I guess it's done 'cause it says passes through. I was, I was running this while I ate dinner before we jumped onto record.

[00:59:30] **Adam:** So it, it's probably done with that. Yeah. yeah, that's funny. So you can see in my VS code, when I highlight the line, it shows that it was committed an hour ago and it's like there's the commit message if it, if I stop moving my mouse.

[00:59:42] **Adam:** Um, so yeah. so, okay, cool. So that's the kind of that prd do js ON file and I'll, share my templates and stuff.

[00:59:49] **Adam:** yeah, I'll, put something up somewhere and we can link to it from the show notes. let me pull up the, the plan script. There it is right there. Actually, I already have it open. So here's, let me turn on a wrapping so I can read it. Okay. So this is

[01:00:02] **Adam:** it's another bash script. and it's got the same sort of like usage thing at the top.

[01:00:05] **Adam:** It reminds me to say plan. And then, I give it like in quotes, a a feature description. I don't think that's even really necessary. I could take that out. because it is, it literally, this one is, it runs Claude in interactive mode. It literally is just there, there's no special, shell script sauce around this one.

[01:00:21] **Adam:** It just says Claude and then a string after it.

[01:00:25] **Ben:** So it's basically just a hard coded prompt that you would normally copy paste, but now you don't have to copy

[01:00:30] **Adam:** E. Exactly. And then the one thing is since I did have that like argument for the feature description, I, in my usage, right? So normally I would say plan space quote, we're gonna work on the hamburger menu, right?

[01:00:41] **Adam:** and then, that gets added to the very end of the prompt. I'll, I'll come back to that. But here's the prompt. It says Study dot ralph slash prd. Example json. And if it exists, Ralph slash prd json help me plan the, help me plan changes to my project. First, give me an opportunity to brain dump my thoughts.

[01:00:58] **Adam:** And then when I ask you, when I ask if you have any questions, ask relevant slash clarifying questions to better understand the problems sta slash solution, and then add the result to Ralph slash prd json. The change we're planning is colon. And then I drop in the variable that is the, the first argument to the, to the command line thing, to shell script.

[01:01:21] **Adam:** So what

[01:01:21] **Adam:** happens is Claude spins up. And it's in interactive mode. It's I just ran Claude. Right? But it's got the, the prompt, prefilled, and it's running, trying to understand what I wrote, and then it just kind of gives me a thing. It's like, okay, go ahead and brain dump. and it, it is just the, the, the claw thing.

[01:01:35] **Adam:** And then I can just sit there and I, I might five times, right, okay, I need you to do this and this and this and this and this. And then this is where I'll heavily used dictation software too. I use a thing called Whisper Flow, and I just hold down a certain button on my keyboard, talk into the mic, and it takes it, and it's like, okay.

[01:01:49] **Adam:** Anything else? Anything else, anything else?and then when I'm finally done, like brain dumping, I'm like, alright, that's it. Do you have any questions? And it usually does, it usually asks me really good clarifying questions about, you know, what about this, what about that?

[01:02:01] **Tim:** how does it know where the co 'cause you're not referencing in this file, you're

[01:02:04] **Tim:** just referencing two JSON files. How does it also know the context window of your code project?

[01:02:11] **Adam:** so you're talking about how does it know, like which files am I wanna

[01:02:15] **Tim:** when it starts asking questions, how's it know? 'cause I mean, you just got two SON files

[01:02:19] **Adam:** Yes. Yeah, I mean, that's a good, really good question. so what I do is, as I'm like brain dumping specific things that I wanted to do, often I've got like a file that I would reference if I was gonna go look at it, right?

[01:02:30] **Adam:** If I wanna go copy, how do I do a modal, right? How did we do that before? I'll just go to the place that I would normally think of, and I would drop that into my prompt, right? In my brain dump section.

[01:02:40] **Adam:** I'm like, Okay.

[01:02:41] **Adam:** I would, I go look at this, at this view and do a modal in the same way that this view does it, but you're gonna put it in this file.

[01:02:47] **Adam:**

[01:02:47] **Adam:** that sort of thing.

[01:02:49] **Tim:** Okay. Okay.

[01:02:49] **Tim:**

[01:02:49] **Tim:** So that's not too different. How I do prompt engineering with, I'm a prompt engineer.how, how I write prompts using Claude Code just inside vs code. I'm like, go look at this folder, look at this function. I want a similar thing over here, blah, blah, blah.

[01:03:04] **Tim:** And then it just does it. But you're doing it in a structured kind of loop kind of

[01:03:08] **Tim:** thing.

[01:03:09] **Ben:** so you're, you're saying give me a chance to brain dump and then when I'm done you can ask clarifying questions. You being Claude, are you literally in the interactive CLI saying I'm done. Do you have any questions?

[01:03:22] **Adam:** sometimes I'll, I mean, you could be that literal if you want, or sometimes I'll just say any questions

[01:03:27] **Ben:** Gotcha.

[01:03:28] **Adam:** I'll say that's it and it'll be like, do, you know, that sort of thing. I'll say that 'cause often it will prompt me, you know, variations of is there anything else? Do you, is there anything else you wanna add?

[01:03:37] **Adam:** Do you have

[01:03:38] **Adam:** any more, you know, it, it's very non-deterministic, but it does figure out the intent.

[01:03:42] **Tim:** Mm-hmm.

[01:03:44] **Tim:** He says.

[01:03:46] **Adam:** I. Yeah. So I mean, the workflow generally at this point is I have a, I have an install, I call it Ralph Dash install. So I go into my working folder where, where I wanna run this stuff. I run Ralph, install it, copies in from all my templates into my project folder copies, the Ralph copies, my PRD example, copies, the, like an empty, basically.

[01:04:08] **Adam:** So, so are these are the, the Ralph, the plan, the PRD, is that all getting part of the source control or is this in some sibling directory That's outside

[01:04:17] **Adam:** this is in, I, I just, I put it in my project. And I also have in the Ralph install, I believe you can see there's a couple of things.yeah, so it echoes, Ralph into the .gitignore. So by default it ignores everything in the Ralph folder. But then I have kind of developed this habit now where I have it.

[01:04:35] **Adam:** I actually wanted to track the changes to the Progress MD and the, the PRDI will probably like before, this branch gets merged into Maine, I will probably delete those files so that they don't

[01:04:49] **Ben:** Oh, okay. So it's sort of like a transient folder to help you develop. Gotcha. Okay. So it's okay. I gotcha. I gotcha. Okay.

[01:04:58] **Adam:** Yep. So, yeah, I mean, it's, it's literally just like. Managing, getting information out of my head into a machine readable and easily, like chunked, file the json, the prd, do json. That's step one. And then step two is run in a for loop. Try to fix as much as you can, you know, and it's, it, it does seem to have, I I just realized I don't have anything in here that's like, I prefer that you write tests.

[01:05:25] **Adam:** It might be in my CLAUDE.md file in most of my projects. But, you know, like add tests for, for stuff that should have tests, but.it, it's not in any of my Ralph scripts to indicate that it should write tests, and it usually does anyway. yeah. So, yeah. But like, you know, make a plan, right? Spit out a p json and then I say Ralph, go.

[01:05:44] **Adam:** And as it's going, I'm like watching kind of in the browser what it's doing, or might be reading my email or talking with coworkers about stuff, whatever, eating dinner.and, and it's, it's great man. I'm loving it and like I said, I'll, I'll, I'll do some bare bones templates and put 'em all up on, I'll probably do like a GitHub gist and we'll link to it from the show notes

[01:06:03] **Adam:** about that.

[01:06:04] **Ben:** Yeah, just are so great. I mean, just like a really convenient way to wrap a couple of files together and make it public.

[01:06:10] **Adam:** Yeah,

[01:06:11] **Adam:** totally. this is great, man. I, I think so I had mentioned that I've been using this plugin called feature dev, and it, it feels like it does, it's in the spirit of this, but this is like much more, robust with all the PRD stuff for sure.

[01:06:29] **Adam:** Yeah. Like I said, it's not my original idea. I very much stole it from other people, but it's working really well for me.

[01:06:35] **Ben:** Well, everybody and their mother is talking about Ralph Wiggum these days, so it's, it is, it is taken the internet by storm and by internet, I mean, probably some tiny corner of the world that only nerds know about.

[01:06:47] **Adam:** Yeah. Our corner, we're taking it

[01:06:49] **Ben:** Yeah.

## [01:06:52] Is Hand Coding Still Valuable?

[01:06:55] **Ben:** Yo. Yeah. Okay. So just as maybe a closing thought here.It's like, again, there's, there's a bit of an existential crisis where if I want to just exercise my brain, is it valuable to do hand coding at this point?

[01:07:10] **Adam:** I think. Yes.

[01:07:11] **Tim:** think

[01:07:12] **Ben:** I mean, setting aside that I enjoy it, but I, I do think that there's a value. I think

[01:07:19] **Adam:** Well,

[01:07:20] **Ben:** just remembering how to learn and remembering how to think deeply and remembering how to struggle against a problem and figure it out.

[01:07:29] **Ben:** And I know you, I one could argue that's what the, the ai, you know, when you're prompting the ai, you're doing that, but it's at a higher level.

[01:07:37] **Adam:** yeah,

[01:07:37] **Ben:** And I think continuing to think at the lower level, I, I, I just, my gut says that that is, is always gonna be important.

[01:07:46] **Adam:** except for a few types of people. There's no point in working out and lifting weights.

[01:07:52] **Adam:** Right?

[01:07:52] **Adam:** Like, there are people who need to do it because if they don't, then they're in terrible health and, and

[01:07:56] **Ben:** Right, right. It's

[01:07:57] **Ben:** a, it's a joy.

[01:07:59] **Adam:** Right. For the rest of, well, I don't know that I would call it a joy. The, the rest of us do it because we have goals that we're trying to hit and that's how you get there.

[01:08:08] **Adam:** Right? I wanna, I wanna look good naked, or I want to be able to, you know, sometimes it is a health concern, but it's not like I'm gonna die next week if I don't

[01:08:15] **Adam:** lose 40 pounds. It's just I

[01:08:17] **Ben:** I

[01:08:17] **Ben:** just wanna

[01:08:17] **Ben:** be better.

[01:08:18] **Adam:** Yeah. you know, this is working out, exercising is not a thing that humans have to do, but we do it because it's good for us. The same way that like writing code, you are like if you, if you completely let your brain atrophy and just, you know, code via Claude from prompting, I. I don't think that that necessarily is gonna mean you can't get a job, but I do think that it's only going, you're only gonna be qualified for a different category of job, right?

[01:08:47] **Adam:** There's gonna be people who can write code with Claude, and then there's gonna be people who understand the code and can like, you know, really debug it when Claude can't figure it out sort of thing.

[01:08:57] **Tim:** yeah, what? When? Can't figure out.

[01:08:59] **Ben:** Yo. That's the thing I'm like most worried about is I know eventually I'm gonna slip into the. I don't fully understand how this works. 'cause it's react and it's using some weirdness hook that I don't understand, but it works. So I'm gonna ship it and then what happens when it just doesn't work?

[01:09:18] **Ben:** I'm like, I didn't learn this stuff very well because it worked. That's, that's, I'm not there yet. Obviously I'm on day two, end of day two here. But, that is something I have in the back of my head as a, as a

[01:09:29] **Tim:** Yeah, I mean, I'll give you an example from today. I, what I ran into, so. wrote some code. I, I actually wrote the code, but I had on, I need to turn off ChatGPT in VS Code. It has the auto complete and

[01:09:41] **Tim:** I hate the auto. I hate the auto complete. Messes me up so badly. I, I, I like Claude code 'cause I have my own separate tab and I talk to it and tell it what to do.

[01:09:50] **Tim:** It's in my folder so it knows what I'm talking about. But like, when it's doing the auto complete, a lot of times it's terribly wrong.and so I had an error. I, I didn't, didn't error in, I don't know why it didn't air in lower environments, but winter production, it was some sort of weird thing where Lucee couldn't compile the object.

[01:10:09] **Tim:** I'm putting in, I'm telling, all right, go to Claude. I'm like, all right, here's the error. Here's the file that's happening on, couldn't figure it out at all. Well, it wasn't the file I was actually getting the error on. It was the actual object that was trying to create, and ChatGPT had created for me a if, an if statement that was just if in two closed,

[01:10:31] **Ben:** Hmm.

[01:10:33] **Tim:** which was it couldn't compile it.

[01:10:35] **Tim:** Now, Lucee's error handling was not very good. It should have told me that,

[01:10:39] **Tim:** but I, I keep putting the error in the code and like asking and asking him like, I can't figure this out, can't figure this out. And I'm like, finally, I'm probably in the wrong file. Let me go look at another file. And I asked cla, I'm like, what's wrong with this file? And it goes, oh yeah, there's an if open closed parentheses here that Lucee can't compile. I'm like, oh, that makes sense. And it deleted it. And we were, we were done. But it's like a, a junior dev who didn't know that is just like, who's used to like, oh, the error is on this page,

[01:11:05] **Tim:** so I'm gonna go troubleshoot this page.

[01:11:07] **Tim:** Actually, no, the error is not on this page. It was on the page. It was actually calling and trying to instantiate. And if you don't know that, you're just gonna waste a whole day. And now that whole efficiency of AI has gone out the window for you, at least for that day.

[01:11:22] **Ben:** Yeah. Yeah. So I'm, I'm, I'm tentatively excited, but I'm treading softly and I'm trying to remember where I came from and we'll see. I'll keep you updated. I, I'm, I'm excited to see Adam excited because I feel like three episodes ago, Adam was like, we're talking about AI again, and,

[01:11:42] **Tim:** Yeah. Yeah, he has, he has taken a turn here lately. I've

[01:11:46] **Tim:** noticed that. Yeah. He has taken a turn.

## [01:11:49] AI Excitement vs AI Fatigue

[01:11:49] **Adam:** That's the thing is I'm excited to be using it. I, I still don't think it should be every podcast episode.

[01:11:54] **Tim:** Yeah, I get it. I get it. I'm, I agree with you there.

[01:11:57] **Adam:** The thing is we're like, especially this last like maybe two months, the, it feels like it's changing every week.

[01:12:05] **Adam:** It's like, oh, you're still doing the thing we learned last week. No, no, no. This is what you really need to be doing.

[01:12:10] **Ben:** Yo. Okay. So on that note though, I, I just don't want to be someone who cares about the models in the same way that I'm on Sublime Text, because I've been on Sublime Text for 10 years. Like, I don't want to be, oh, a new model just dropped. Let me go experiment with it. I'm like, no, I'm just gonna use the model that I've been using.

[01:12:30] **Ben:** I don't wanna think about what type of task I'm

[01:12:32] **Adam:** Do you know what that sounds like to me, Ben?

[01:12:34] **Ben:** what.

[01:12:35] **Adam:** It sounds like I really like my mini sledgehammer, so I'm gonna use it to eat my

[01:12:39] **Ben:** no, I'm just, I'm just saying I don't know, like it, I'm, for whatever reason, I'm just like, I'm not interested in that level of optimization. To me,

[01:12:46] **Ben:** that's

[01:12:47] **Ben:** like a that's like the, should it be a a four loop that counts from one to a hundred, or should it be a while loop that counts backwards from a hundred to greater than zero?

[01:12:55] **Ben:** And you're like, bro, it's a loop.

[01:12:58] **Ben:** And you're like, yeah, well, one's slightly more efficient. bro, it's a loop. I don't care.

[01:13:02] **Adam:** level of optimization doesn't

[01:13:03] **Ben:** You know, like that's, that's, and maybe that's a bad analogy, but like, that is the, that's like the vibe I have right now in my, in my

[01:13:11] **Ben:** brain.

[01:13:11] **Adam:** when you say, I don't care, what model are you talking? I don't care about the difference between Claude Opus versus Sonnet versus Haiku or, or are you saying more like, I don't care between Claude and, um,

[01:13:26] **Ben:** Oh, the, like Claude and Cursor, like, that's an even bigger conversation. I'm like way

[01:13:30] **Adam:** even

[01:13:31] **Adam:** that, but that cursor isn't a model. It's an IDE, but,

[01:13:33] **Adam:** they have their, own model called Composer one, but, and then there's, but like I was talking more you know, whatever it is, GPT five is out and

[01:13:41] **Adam:** you've got

[01:13:41] **Adam:** like

[01:13:42] **Ben:** look, there, there are people who are very happy to be like, well, this month Verizon is a hundred dollars, and next month, spectrum is $95 with a $5 rebate, so I'm gonna switch. And that's perfectly fine if that's like, you wanna spend that time thinking about that, but like, I don't care.

[01:14:01] **Adam:** Well, so I will say, I, I agree with you pretty much in spirit on that. The, just be willing to change when it is time, right?

[01:14:11] **Ben:** yes. But it's not gonna, if someone says, okay, this model is clearly better now across the board, I will use it, but I'm I'll, I just, I don't have the motivation and to be like, well, I'm writing an email, so I'm gonna switch to Sonnet, and now I'm doing code, so I'm gonna go back to something else. I'm,

[01:14:30] **Tim:** Yeah, I mean

[01:14:31] **Ben:** I want them to figure that out for

[01:14:32] **Tim:** we're so on the bleeding edge right now

[01:14:34] **Tim:** of the, this is so early. Eventually it was gonna become a commodity, right? It'd be like, you'll just go, all right, who's got the cheapest LLM

[01:14:43] **Tim:** coating LM that, that I know works? And there'll be two or three players and we'll just choose between them and they'll basically have a monopoly and they're gonna go up to $500 per developer, per per

[01:14:55] **Ben:** yo, that's the thing that. I mean, so a, a as, so I, I, I listened to two camps podcast wise. It's like they're the people who are the AI pilled, like the mixture of experts IBM podcasts where they're basically saying 90% of all code can be written by AI now. And then the other camp is this is all a giant bubble.

[01:15:16] **Ben:** NVIDIA's gonna back out OpenAI is gonna collapse. Anthropic's bleeding money, like everybody's bleeding money, nobody's actually making money. And then and then what happens? And I don't know which one of those is true.

[01:15:28] **Tim:** I mean, does, does it matter? I mean,

[01:15:29] **Tim:** so the, let's say it is a, the internet was a bubble, right? The internet legitimately was a bubble. A bubble is a stock market thing, right? People just pump money into what they think is gonna be in the,

[01:15:38] **Ben:** yeah. Yes-ish.

[01:15:40] **Tim:** of the internet bubble, we still had tons of routers.

[01:15:43] **Tim:** We still had

[01:15:43] **Ben:** Hundred percent. A hundred percent. I'm not

[01:15:45] **Tim:** So the, so I don't care if AI's a bubble or not, if it pops, we still have a lot of really cool LLMs out there to do stuff with. Actually, a bubble will be great 'cause they'll be cheaper. They'll be like begging for money. They're like not in growth mode anymore. They'll be like, okay, we're gonna give you a good product for a fair price.

[01:16:02] **Tim:** As long as the bubble keeps going, it's just like

[01:16:04] **Ben:** I guess so. I don't know. All, all I'm saying is that, that, that I, it makes me nervous that the future of it feels, depending on who you're talking to, either extremely obvious in a good way or extremely obvious in a bad way. And I, again, like I just don't, I don't

[01:16:19] **Tim:** I think, I think the people worry about if it's a bubble or not are the people who just wanna make money off of it. That what we care. I mean, I care about both, but what we care about in our day-to-day jobs is does it work? Is it a good tool? If it's not a good tool, I'm not using it.

[01:16:32] **Ben:** We go, we've been talking a while,

[01:16:34] **Adam:** Yeah, we've been going for quite a while. Alright, well then,

## [01:16:36] Patreon

[01:16:36] **Adam:** this episode of Working Code was brought to you by the Gartner Hype Cycle. We're ascending, what is it called? The, the peak of disillusionment or whatever it's called. peak of Inflated Expectations. That's what it's the trough of Disillusionment is next.

[01:16:51] **Adam:** Getting ready yeah, praise for impact.and listeners like you, if you are enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[01:17:08] **Adam:** Special thanks as always to our top pi, top patrons, Monte and Giancarlo, you guys rock.

## [01:17:13] Thanks For Listening!

[01:17:13] **Adam:** we are gonna go record after show. looks like this week somebody wants to talk about a new Game of Thrones show that's got my interest. and Tim has something interesting. He wants to cook and eat, and I'm not gonna tell you what it is.

[01:17:25] **Tim:** Oh, it's interesting. It's

[01:17:27] **Adam:** Um,

[01:17:28] **Ben:** you'll never fit that inside you. Sorry.

[01:17:31] **Adam:** Uh, I think he is gonna say challenge, accept it. And anyway, so if you wanna help us out, you go to patreon.com/workingcodepod, throw a few dollars per month our way. We'd be greatly appreciative. You'll get this, all prior and all future after shows. for as long as you're a patron, you'll have our undying gratitude, and a couple of other perks like get you, you get, special access to our discord.

[01:17:55] **Adam:** There's a private area there with the special patrons only room where we talk about all the non patrons,

[01:18:01] **Tim:** Lovingly,

[01:18:02] **Adam:** freeloaders. anyway, that's gonna do it for us this week. We'll catch you next week and until then,

[01:18:08] **Tim:** it's no bubble. Your heart matters.
