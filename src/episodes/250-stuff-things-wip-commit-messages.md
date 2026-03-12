---
title: "250: Stuff, Things, WIP: Commit Messages"
description: "Do commit messages even matter anymore, or did pull requests kill them? Four developers, four different workflows, and a lot of knife emojis."
date: 2026-03-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/250-stuff-things-wip-commit-messages/id1544142288?i=1000753666050"></iframe>

Do commit messages even matter anymore, or did pull requests kill them? Ben works one commit per PR and thinks the commit message _is_ the PR description. Carol and Tim put all the context in the PR and treat commits as disposable breadcrumbs. Adam's somewhere in between — when he's not pushing thirty knife emojis and "nope, still not working" to QA. Meanwhile, Tim's back from emergency eye surgery with a gas bubble floating around his eyeball.

### Links

- [Ben Nadel's Blog][ben-blog]
- [Conventional Commits][conventional-commits]

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[ben-blog]: https://www.bennadel.com/
[conventional-commits]: https://www.conventionalcommits.org/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/250-stuff-things-wip-commit-messages.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** So I'm like testing on qa. So you have to commit and push to get it to, to go up, to, to deploy, to test. So it's like trying to fix it and then nope. Didn't work. And then, and then it's like a knife emoji, and then it's like three knife emojis, and then it's whip, and then it's like, Nope, still not working, right?

[00:00:13] **Adam:** These are my commit messages

[00:00:15]

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go. It is show number 250. And on today's show we're gonna talk about the differences between commit messages and PR messages. Pull request messages for the uninitiated. get the whole crew back. Welcome back, Tim. Or, or should I call you Cyclops, Tim, or,

[00:00:48] **Tim:** It's is fine. Yeah, it it's,

[00:00:50] **Adam:** feeling okay?

[00:00:51] **Tim:** yeah. I'm, I'm hanging in there. I'll be okay.

[00:00:54] **Ben:** Well, it's good to see you sir.

[00:00:55] **Adam:** Pretending we didn't just have a 15 minute conversation before we started recording. Anyway, the whole gang's here. Let's get started. We're gonna do a, a bit of a shorter show than usual just to Tim's, you know, got his eyes still healing, can't sit in front of a screen too long, and Carol's got a lot of drone fly through our house.

[00:01:09] **Adam:** So we're gonna keep it nice and short tonight.

[00:01:12] **Tim:** A drone?

[00:01:13] **Adam:** let's start with our triumphs and fails. Tim, why don't you go first?

## [00:01:16] Tim's Fail

[00:01:16] **Tim:** Well, my, my fail is obvious. My, my retina tour. I told you all that Star Trek is

[00:01:21] **Tim:** yeah, yeah. So I was watching TV and, and I had a little spot that had been there a couple days at the bottom of my eye. And then as I was watching Star Trek Thursday evening, all of a sudden I went from having like 10% of my vision, like blocked to like 90%.

[00:01:35] **Tim:** And so they eed me up to Atlanta, to the Emory University Hospital and basically did a little procedure where they inject my eyeball with, gas. And then that gas bubble floats up and pushes the retina back up against the eyeball wall, makes it stick, and then they laser it down. So I've gone through a couple rounds of lasering. It's annoying. So it's like working is kind of hard. 'cause I, this they don't, not wearing a patch, they don't gimme patch or drops or anything, but it's like having this gas, you can't see through it. So it's this like bubble that's floating around like at the bottom

[00:02:08] **Adam:** Mm-hmm.

[00:02:09] **Tim:** well technically it's the top of my eye, but because the eyeball reverses, flips everything and reverses it, it's the bottom left where the tear is actually in the top right.

[00:02:18] **Tim:** So I have this big bubble in the bottom and I can't really see

[00:02:21] **Adam:** Yeah. Didn't you know eyeballs are Missy Elliott?

[00:02:23] **Tim:** yeah.

[00:02:24] **Adam:** Flip it, reverse it.

[00:02:25] **Tim:** Oh god. There's a throwback. So yeah, so I'm dealing with that but work's been, you know, pretty understanding. I missed an entire week where pretty much I just slept the whole time and I have to keep my head in a certain position, to keep that, that gas bubble in the right spot.

[00:02:42] **Tim:** but hopefully in two weeks this should be all cleared up and then we'll see. I, I don't really know how good my vision is right now. We'll see after, after the

[00:02:51] **Carol:** of the bubble, right? Yeah.

[00:02:53] **Tim:** my, my prescription for my eyeglasses might change or, you know, it might be exactly the same. You never know.

[00:03:00] **Ben:** uh, you sleep, do you have to wear an eye patch? So you don't, like, absentmindedly scratch it or anything?

[00:03:06] **Tim:** no. I asked about that. You know, does it, you know, if I rub my, they're like, no, don't worry about you do norm. The only thing I can't do is I can't like, have my head like down a lot, like bending down where my head's like below, you know, standing on my head's completely out. Not that I would ever do that. And, you know, they're like, why did this happen? They're like, guys, you get older, you know, things just start to wear out and you're, you had probably a tiny tear and then that vitreous fluid pushed out and tore the, the rest of the eye's frame. So it was, not on my bingo card for things to do this, past few weeks.

[00:03:38] **Tim:** So.

[00:03:39] **Ben:** just crazy.

[00:03:40] **Adam:** new fear unlocked.

[00:03:41] **Ben:** Yeah. Big time.

[00:03:43] **Tim:** yeah. I'm not a, I I, I've gotten used to it, like I feel like I was in a James Gunn movie. 'cause you know, like he always has like eyeball violence. Did you watch the latest Superman? Like that? They, they were punching the big kaiju and the eyeball and, and there's other eyeballs that's like, that's what I felt like I've so many needles and things stuck in my eyeball

[00:04:02] **Ben:** And, and for the listeners, Tim is totally conscious and awake when they were doing

[00:04:07] **Tim:** yeah. They don't, they don't knock you out. Yeah. And I thought I was being a pretty big wimp. 'cause I would like kind of groan a little bit when they were like doing stuff. But while I was there, like there were two emergency, they, through the intercom system, they, it's like emergency medical in third floor, ophthalmology.

[00:04:24] **Tim:** I was like, what's going on? They're like, oh, some guy passed out when they started messing with his eye. So like, I thought I was being a whimp. But they, they, if he, and if you pass out up there, they have to basically take you. To the emergency room. So they, they take him outta there, put him in a gurney, take him to the emergency room.

[00:04:39] **Tim:** He's fine. He comes back and gets done. But yeah, I didn't pass out. So

[00:04:44] **Ben:** Oh, I

[00:04:44] **Adam:** Your trooper.

[00:04:45] **Tim:** yeah, I, I don't wanna talk about it

[00:04:47] **Carol:** do it.

[00:04:48] **Tim:** That's my fail. How about you, Adam? What you got?

## [00:04:51] Adam's Fail

[00:04:51] **Adam:** Uh, I also have a fail to go through here. So, yesterday I was doing some cleanup work. I was cleaning up, some logic around, uh, like a, we had a gift payment fail, and I was kind of tracing through. There was a, a database deadlock, and it just caused the whole process. The, the one that got deadlocked and, and thrown away, it just stopped in the middle.

[00:05:09] **Adam:** And so I had to kind of figure out, okay, where did it deadlock and manually go through the steps that it would've done in the code, right? Which was a bunch of queries that had ran and, and some other stuff. And while I was reading through the code, trying to figure out, okay, what do I need to do? I found some really complex logic that was like buried inside a conditional, right?

[00:05:26] **Adam:** It was like if, and then a whole bunch of variable references and it's like deeply nested like this object dot, this object dot some array, and then whatever, index in the array dot whatever, right? Complex thing to put in an if statement. That is kind of a pet peeve of mine. So what I did was I thought I was refactoring, it turns out I was just changing... I thought I was refactoring, and I was like, okay, this is a pet peeve of mine. I'll just take this logic and I'll make it a variable, right? And then I can reference that variable from the conditional, right? So instead of if complex logic, it's a, it's a named variable, so you can just more easily think about what this conditional is doing.

[00:06:04] **Adam:** So what it was doing was checking to see if a payment on a payment plan was paid, right? So, but the, the way that the logic was written, it was looking to see if it was. Not, not paid for whatever reason, like it was, it, it was looking up to see, I guess the way that the data was available. It made it easiest to just say, okay, this payment is not paid.

[00:06:24] **Adam:** And then it had the exclamation point in front of it, so it was not paid with an exclamation point. Right. So it was not not paid. It was paid. Right. So because of the way that the data was shaped, I created a variable called is not paid. and then I referenced it from the conditional. So I had if bang is not paid, and then I was looking at that, I'm like, that's a double negative, let me fix that.

[00:06:46] **Adam:** So I wrote another variable right under the first one that I did, and it was called is paid. and it just is paid equals bang is not paid right. So it's just inverting is not paid. So that part is correct, is

[00:06:59] **Ben:** I'm loving it all so far.

[00:07:01] **Carol:** Oh, I'm hating it all, but go ahead.

[00:07:03] **Adam:** and then I was like, okay, well cool, I'm done. So all I have to do is change that variable in the conditional, change it to change the is not paid to, is paid, okay?

[00:07:12] **Adam:** And boom, done, right? So I commit that goes through code review. Everybody approves it, it goes up to production. Come in this morning, two gifts have failed on that line or, or like, because of that line, um, they got into some bad state because of that. So it turns out I accidentally left that, that bang from the double negative in the inside, the conditional still there.

[00:07:32] **Adam:** So instead of is paid, I was doing not, is paid, which it was supposed to be, is paid. So, you know, like the code was fine. I was just trying to make it more readable

[00:07:42] **Ben:** Yeah.

[00:07:43] **Adam:** and in the process I added a regression. And the problem was, I'm sure, a bunch of people are thinking to themselves. I wasn't refactoring because I didn't have tests, I was just changing

[00:07:53] **Ben:** Yo. I will say though that having an interim intermediary variable that just reads nicer is such a power move. I freaking love that. I can't tell you how many times I have a method that does nothing but call another method and then do "not" of it

[00:08:10] **Adam:** Mm-hmm.

[00:08:11] **Ben:** where I, you know, like I have something like an IS live method and then I have an, an is local method or like an IS development or something like that, and all that does is call the is live and not it thing that things to that effect.

[00:08:22] **Ben:** I think it's just such a power move, man. The readability of code, pays dividends. I mean, other than the two gifts, that broke,

[00:08:29] **Ben:** but those will be returned to you sevenfold.

[00:08:32] **Adam:** Yeah, yeah, for sure. The, yeah, now the code is correct. The, I got the fixes done as fast as possible and I, and I got that, the updated code back through code review, and then I fixed the data that broke because of my bug. So that's fine. And now the code is more readable and I needed less caffeine to wake up this morning because my heart was pounding from having to deal with that.

[00:08:51] **Adam:** So,

[00:08:53] **Ben:** Let, let me ask you, as you're getting more and more AI pilled, are you guys exploring any of the automated code review bots that could be like, plugged into GitHub or something?

[00:09:06] **Adam:** are you asking me if, like my team is, or are you asking me personally?

[00:09:10] **Ben:** I, I guess as a team,

[00:09:13] **Adam:** No, the none of them are free and we're kind of, uh, frugal, I should say. Yeah, I'm aware of more than one. I think. was it Code Rabbit and Reptile are the two that come to mind immediately for me. and both I've heard good things about both and my personal experience, I've had just Claude doing code reviews of like, my branches before I submit them, that sort of thing.

[00:09:35] **Adam:** And I, I found it really good, and I'll be honest and say that I didn't even bother trying to find this bug. I just knew I was very likely because of my change. And so I, I pointed Claude at it. I was like, in this file yesterday, I made changes on this line or these, you know, four lines or whatever. and now I'm getting this error message, which is a direct, like, it was like a throw with this message, right?

[00:09:58] **Adam:** So it was, it was very definitely thrown from this line, right? Like, I'm getting this error thrown. I changed these lines yesterday. Did I screw something up? And it took it, you know, it ran for like 10 seconds and it goes, yep, you got the, some inverted logic there, big whoopsy, whatever. and do you want me to fix it?

[00:10:15] **Adam:** I'm like, yes, please. Thank you. And the, the I, the irony is if I had used Claude to make the change in the first place, it probably would've gotten it

[00:10:26] **Ben:** Uh, maybe, maybe that's a counterfactual. We'll never know.

[00:10:31] **Carol:** I can't tell you the number of times I've like pulled out a notebook and had to write down like logic steps to understand the double negatives. I'm like, okay, which way? Actually makes this true, and is it still true? I remember working with Tim and creating an Excel sheet for premiums because I didn't understand the double negatives that people were using.

[00:10:52] **Carol:** So I was like, premium is not paid, but not, not paid. I'm like, wait, what am I looking for? Did you pay your bill or not? I don't know. So now I need Excel to tell me and understand what this is doing.

[00:11:03] **Adam:** Yeah. Reminds me when I was first learning a program, we still use the, the green bar paper, and like dot matrix printers. You would print out your program and just like, okay, I'm tracing, I'm debugging, I'm tracing this one variable through a function, and I'm just like, on every line I write down what is the current value of my variable at the, when that line runs.

[00:11:21] **Carol:** Oh, that sounds so painful.

[00:11:23] **Adam:** It is.

[00:11:25] **Adam:** all right, well, that's enough from me. How about you, Ben? What do you got going on?

## [00:11:28] Ben's Failiumph

[00:11:28] **Ben:** I'm gonna go with a emph, which is that, I started off with the intention of, of bringing a sweet, sweet triumph to you guys today, which is that I did actually sit down with Claude Code and I had it start to try to write a small test suite and test runner for Big Sexy Poems.

[00:11:44] **Adam:** Um, I'm, you've got my attention. Keep

[00:11:47] **Ben:** I was like, I even teased it in the, uh, in the general room for Adam Cameron.

[00:11:51] **Ben:** I was like, oh, namesake's gonna be so proud of me. And, and then like Tuesday morning, I guess we started to test it and it, it had the test running. I mean, it just, it was like a, a proof of concept. So it had one test suite running and I said, you know what? You're, you're iterating over these test suites synchronously, like, you know, one after another.

[00:12:11] **Ben:** I said, we could just do these in parallel. Like I, that I was like, if anything that's better representation of the website itself, like the website should be able to handle parallel processing. So I said, okay, instead of doing this array as just an array map, let's do an array map of all the suites. But then you just throw in that little parallel equals true argument, which is like, come on, ColdFusion, you're so freaking beautiful.

[00:12:33] **Ben:** and immediately some of the tests methods just started breaking. That sent me down this huge rabbit hole where I was trying to isolate what was going wrong, because I know that historically ColdFusion has had some issues with like nested parallel things. Like you can't have threads inside of threads, unlike Lucee, which has supported that apparently forever.

[00:12:53] **Ben:** and I, I'm trying to isolate it 'cause I'm like, oh, okay, I'll be able to blog about it and I'll be able to write a ticket and then submit it to the Adobe tracker and two mornings go by. So, you know, probably like six hours-ish, maybe five hours-ish in total of me drilling down and debugging and deleting code is not, it doesn't need to be there to try and isolate exactly what's happening.

[00:13:12] **Ben:** and the good news is it is actually a bug in ColdFusion. It's not my fault. but the like really embarrassing thing is like, I actually ran into the same exact bug and blogged about it and opened up a ticket last August.

[00:13:25] **Adam:** Oh no, not even that long ago.

[00:13:26] **Ben:** not even that long ago. And, uh, it's the craziest thing. So if you do asynchronous.

[00:13:33] **Ben:** Array iteration.

[00:13:35] **Ben:** And then you, call a method that defines a closure and then passes that closure out of scope to another method. And then that secondary method invokes the closure. It destroys the argument scope of the parent method, so that if you then go to reference any of the arguments, they're just gone.

[00:13:57] **Adam:** Wow.

[00:13:57] **Ben:** It's crazy. It's, it's, it's bonkers. and like, you know, I could just take out the asynchronous iteration for now to, to make it work.

[00:14:05] **Adam:** right now, I'm sure that's been kind of difficult for people to follow. It was a little difficult for me to follow

[00:14:10] **Ben:** Yeah, yeah, yeah.

[00:14:10] **Adam:** watching you move your hands around, but I, I'm sure you have a blog post on this, so if you drop it in our show notes, we'll we'll have it there for people to who are interested to go follow up on.

[00:14:19] **Ben:** I, I do have a post and I'll drop it in. And the, the tracker, the ticket in the tracker is marked as fixed.

[00:14:26] **Adam:** Okay.

[00:14:27] **Ben:** But it is for an update that has not yet been released. So I'm

[00:14:31] **Carol:** Ah, so it's still coming out. Yeah.

[00:14:33] **Ben:** But, I was really, really, really hoping to drop the, the T-Bomb on you guys today, but, uh unfortunately,

[00:14:42] **Tim:** but, but accepting it as the first step,

[00:14:44] **Ben:** yeah,

[00:14:45] **Ben:** and

[00:14:46] **Tim:** so what are you using for your testing?

[00:14:47] **Tim:** Is it

[00:14:48] **Ben:** now this is the fascinating thing because this to me, sort of lines up with the whole SaaS apocalypse kind of mentality that people are talking about where this is, you know, AI is the death of SaaS because now people can just build their own stuff.

[00:14:59] **Ben:** I, I'm not saying I believe that, but that's what people are saying. So when I prompted Claude, I said, look, I want to have tests so that you can change things. I said, I may never look at these tests. so I don't care what this looks like. I just want to give you a URL that you can hit and it needs to return data that you can parse.

[00:15:19] **Ben:** So it's, oh, great, we'll just do this thing and it'll return like an array of responses, and then we'll just serialize it as JSON. And, and it built a couple of assert, like a assert true and assert equals, and like a cert throws kind of a thing. And like, that's it, that's the extent of it. And I don't know if it's gonna be sufficient in the long run, but, it was nice to, like, I don't, you know, it's two files.

[00:15:41] **Ben:** It's basically a test runner and a base test class. And, uh, we'll see if that works. But it's, it's nice

[00:15:48] **Adam:** to a GitHub

[00:15:49] **Ben:** throw it at AI and be like, build it and what's the, what's the smallest possible effort we can put into this? So to give you guard rails is my, my mental thought here.

[00:16:00] **Adam:** I like the thought process. I'll be very curious to see if you can, if it's something you can share the, like the test harness that it built?

[00:16:06] **Ben:** Yeah. And, and it'll, and it's interesting too. I, I went back to it, it creates this assert equal method where, you know, you give it. Two arguments, and then a message that it should throw if they're not equal. And I said to Claude, I said, Hey, you know, just so you know, this will only work with simple values.

[00:16:22] **Ben:** 'cause you can't, you can't take like a struct or an array and say, does this one equal that one in ColdFusion? And it was like, oh yeah, I know that. But we don't need to have complex equality. If we need that later. We can always create like an assert deep equals. and I'm like, all right, at least you're thinking about it.

[00:16:38] **Ben:** So like, you know, you're not just misunderstanding the premise of the language. So yeah, we'll see. We'll see how it goes.

[00:16:45] **Carol:** do you have a test in there yet for your super secret URL that no one should hit to get to your administration page?

[00:16:52] **Ben:** I, I do have, it's not live yet, but it, it, it's also gonna be in a part of the app that only runs, Assuming that I don't have a double, not equals, uh, mountain.

[00:17:02] **Adam:** Oh, low blow

[00:17:05] **Ben:** There is, there is basically just a subsystem that says only allow this to run in development. Which, you know, that's not the most security, but it is, it is some security.

[00:17:16] **Adam:** below the belt, minus 50 DKP.

[00:17:20] **Ben:** the other thing, and, and you guys have talked about testing. I think even Tim one time talked about like testing data access by just building SQL strings and then com, and then looking at the output of the SQL strings. Maybe it wasn't Tim, it was somebody,

[00:17:34] **Ben:** So I said, this is part of the prompting Claude.

[00:17:36] **Ben:** I said, look, I don't wanna mock anything, I don't wanna deal with anything that may not work once it's in production. I'm like, just create a new user every time you run the test suite and run it against the database. And if it ever becomes a problem, we'll deal with it then.

[00:17:50] **Carol:** Ooh.

[00:17:51] **Ben:** like, I'm just trying to give it like, as few constraints as possible and be like, as real world as possible.

[00:17:57] **Carol:** Does it clean up that user at the end of the

[00:17:59] **Ben:** no, I said, I said if we, I said, I said we'll accumulate data, if anything, that'll be a good, uh, I was like one that'll be very obvious if there's ever cross account leakage, like I'll start seeing test records in my account. and I, and you know, it'll also be good to know about, you know, SQL performance and like possible indexing that we have to add.

[00:18:18] **Ben:** 'cause I'll never run these tests in production. This is only for local development. So next week guys and gals, gonna

[00:18:26] **Carol:** you'll have accidentally, uh, created 20,000 new users.

[00:18:30] **Tim:** Do it. Do it

[00:18:32] **Ben:** So

[00:18:33] **Adam:** to Foghorn Leghorn. I said, I said,

[00:18:36] **Ben:** so that's my failure. Umph. Carol, take us home. What do you got going on

## [00:18:40] Carol's Triumph

[00:18:40] **Carol:** Guys, I'm gonna bring us in with a big old win. Um, I mentioned last week on the show that, I was, I had joined the AI ambassador program at work and I was super excited to be doing that. Um, well a couple days ago, um, it was, I. OCIO. These letters are hard to say. After a long day of working, emailed me and offered me the title of Lead ambassador

[00:19:06] **Ben:** wow.

[00:19:07] **Carol:** and the SME for developers.

[00:19:10] **Carol:** So I will be working to develop have lots of input on the developed. First training and what we will be teaching and kind of helping with the implementation of AI across the board. And then also, actually representing my agency as the lead ambassador. So it's a big deal. It feels like a big privilege and I'm just glad that, um, I'm giving this opportunity to have input 'cause.

[00:19:34] **Carol:** I even sent it in my email back to him for so long. Everything with federal jobs and technology has been, you know, you guys were updating ColdFusion 2019 and I was like, we just patched 2010. You know, like we were way back there and it's just, it takes so long. So to finally feel like. I'm with you guys and actually on cutting edge and, you know, out with everyone else in technology feels like a big honor and like a, a change in mentality and, and some leadership.

[00:20:04] **Carol:** So it's pretty awesome.

[00:20:06] **Tim:** That

[00:20:06] **Tim:** is

[00:20:06] **Ben:** Very cool.

## [00:20:07] Claude Blocked, OpenAI In

[00:20:07] **Adam:** So as we're recording this, I think it was like yesterday or the day before that there was a whole kerfuffle with like,

[00:20:14] **Adam:** uh, Anthropic is out and OpenAI is in. Has that affected

[00:20:17] **Adam:** your team at all? Yeah, I.

[00:20:19] **Carol:** has big time. Yep. So we, um, came in Monday to everything Claude blocked. Um, there were a few, there were a few exceptions like in place, I believe. Um, I don't, I don't, I'm not gonna go into details of that. But, just for some transition stuff, right. But yeah, everything was blocked. So it was interesting just even getting on copilot to just do my normal, like copilot chat about something and my only options is.

[00:20:42] **Carol:** ChatGPT, maybe a Codex thing, like nothing was there. And I'm even still struggling to explain to my developers how a model selection and copilot doesn't mean you're using open AI's codex. Like that's not what you're doing. They're going, Hey, codex sucks. Like, this is so bad. I'm like, you're not even using Codex, you're using a model from.

[00:21:06] **Carol:** GitHub's copilot called ChatGPT 5.2 Codex. Like you're not using Codex, you're using a model. So it's just been a bit of, a little frustration from my developers because the Claude models provided better output for what we do on a daily basis to then go to ChatGPT, and it's just like, whoa. Copilot, you don't get good answers, so you really have to go directly to open AI to get good answers out of the

[00:21:34] **Ben:** Oh wow.

[00:21:35] **Adam:** Yeah, it's, I think that's a really big fumble from OpenAI, if I'm not mistaken. So they, they have these like, flavors or forks or whatever you wanna call 'em, of some of their models where they call it. Okay. It's not that, it is just, it's GPT 5.2 Codex or 5.3 Codex, right. This is like the coding specific version of it.

[00:21:52] **Adam:** But then they also, if I'm not mistaken, have a tool which is kind of like Claude Code or Open Code or whatever that is called Codex,

[00:22:00] **Carol:** It is. Yep. You're exactly right.

[00:22:02] **Adam:** a terrible idea.

[00:22:04] **Carol:** Yeah.

[00:22:04] **Carol:** So Maya, that that was my developer today. They were like, why do I have to log into chat GPT? I'm using the, the model in Visual Studio already. I'm like, no, you're using. Copilot through GitHub and that model, you're not using the Codex tool. So it took me a little while to like have to explain that, and I just wish it were named different.

[00:22:26] **Carol:** If you've just named things differently, we wouldn't have this issue. But that's not how it works. Yeah.

[00:22:31] **Ben:** Yo

[00:22:31] **Tim:** It's, it's funny in the news they're talking about that after the whole kerfuffle where, Claude said they weren't gonna, you know, allow, you know, surveillance or military stuff to be used.

[00:22:43] **Ben:** Autonomous killing machines.

[00:22:45] **Tim:** Tons of people uninstalled ChatGPT and installed Claude

[00:22:50] **Adam:** Yep.

[00:22:51] **Tim:** in a protest.

[00:22:52] **Carol:** Yeah.

[00:22:53] **Ben:** Yo, just before we got on the call today, I got a LinkedIn alert that OpenAI just released ChatGPT 5.4.

[00:23:03] **Tim:** Oh yeah.

[00:23:04] **Ben:** don't know anything. I don't know anything about that. It just feels timely to mention.

[00:23:08] **Tim:** Yeah. I use ChatGPT for my personal stuff, and I use Claude through our company Enterprise version.

[00:23:16] **Carol:** I, I will say like I've been used, so I was using Codex actual like Codex or open ai, toward the end of the year. And then, you know, once we got put into the you know, once we got put into the Claude Code trial, I went to that and,

[00:23:28] **Carol:** Um, so now getting back into Codex CLI, it's really working really like. One-on-one for me. Like I'm not seeing a big difference from what I was getting from Claude versus what I'm getting going directly through Open AI's Codex tool.

[00:23:43] **Carol:** Um, the only difference is, is that their actual like Codex, application wasn't really written for Windows. So they just released that yesterday or day before. So I've gotta download it once it passes through security and give it a go. So I think once I have that in, I'll be, I'll be kind of rolling a little faster.

[00:24:02] **Carol:** But I will tell you, after doing some of these actual coding tools, I don't know that I will ever want to go back to just GitHub copilot chat.

[00:24:12] **Carol:** That is the worst thing ever. Now, it doesn't even like I, I don't know. I can't do it. It just seems like a waste of my time.

[00:24:20] **Adam:** I will say I, so, you know, I was using Cursor for a while because I was using their models and I switched to using, Claude Code. And so I turned off my cursor subscription and using the Cursor IDE, I was still using that IDE for a while. but then like without any of the AI stuff, I started to bump into all these like, rough edges, you know, keyboard shortcuts, got clobbered or, you know, little bugs here and there.

[00:24:44] **Adam:** And I finally was like, okay, well there's no point in me being on like a fork of VS code that's got all these bugs. Lemme just go back to VS code. So I, I switched back and I guess I'm getting the free co-pilot, like free level co-pilot tab completion type stuff in there. And I don't hate it. I mean, it certainly doesn't, it, it pales in comparison to using a true like coding agent.

[00:25:05] **Adam:** But, yeah, I mean, I'm not mad at it.

[00:25:08] **Carol:** I think I just remember my first days of, I say my first days, you know, back in October, you know when this was all brand new a couple months ago.

[00:25:15] **Tim:** her back there.

[00:25:16] **Carol:** I just remember being in there and like highlighting a line of code and being like, can you explain what they're trying to accomplish here? And being so happy that my chat could do it Now, I give it a prompt and I just let it go work, and I can't do that with the co-pilot stuff.

[00:25:31] **Tim:** Hmm,

[00:25:31] **Adam:** Okay. Are we ready to move on?

[00:25:34] **Tim:** I, I, since I was out for a little while, I'm gonna come back to my triumphs and fails and add a triumph. I just

[00:25:39] **Tim:** thought I would.

[00:25:40] **Carol:** I think you're allowed.

[00:25:41] **Tim:** thank you. Thank you, thank you. So it's kind of a in line. So during all this, with my eye that's going on and my, some other health issues, max, my son Max, who's doing his last semester of college one of the classes he's doing, it's like, I guess it's like online media kind of thing, but it's related to his, his CS degree.

[00:26:01] **Tim:** And so he was, had to interview someone who was in the, in, you know, in the industry. And so he. Picked me. He didn't tell me that he is picked me, but, so I'm like, here, like with my eye, just getting outta the hospital and he's like, Hey, I need to, can I record you? I need you to ask you some questions. Just hop on this mic and gimme some sound bites for, he has to do a fake podcast, right?

[00:26:23] **Tim:** and so he is asking me these questions and I'm like, super depressed. I've hadn't had sleep in like 20 hours. And he is like, so, you know, what are the keys to success in the, and he is asking me all these questions, like, very positive. And I'm like, I was looking like he sticks a microphone in front of my face, like, can you just, you know, answer these questions?

[00:26:40] **Tim:** I'm like, dude, I am so not in the mental space right now to do this. He, so I just felt bad. But he had a deadline. So what he did was he listened to, I don't know how many episodes, he just listened to our podcast, which he's never done before. And he, he took sound bites from me talking to you guys as part of, he built a fake interview using

[00:27:01] **Tim:** sound, sound.

[00:27:02] **Tim:** So when, when he's like, I'm like, so what'd you wind up using? He is like, you were talking about like, building KPIs and when strategy, you know, meets your t strategy versus tactics. Remember that episode? So he took that and took some things from that episode and then built this whole profile, took some, he had previously had taken some photos of me before my eye went kaput.

[00:27:22] **Tim:** And, yeah, so built the whole, built his little podcast and faked it to make it look like he was having a conversation, asking me questions. And then he would like, looked at the transcripts that we had, that all the transcripts, figured out some things that he wanted to pull those out, grab the audio, built it in, and yeah, so thank you guys.

[00:27:39] **Tim:** I got the historical record and Max actually listened to

[00:27:41] **Ben:** That's awesome.

[00:27:42] **Tim:** and he didn't cringe too much. I don't think. So he.

[00:27:47] **Ben:** No, it's very

[00:27:48] **Carol:** I love

[00:27:48] **Adam:** Good job,

[00:27:49] **Tim:** job, max.

[00:27:49] **Tim:** Yep. Good job, buddy.

[00:27:51] **Carol:** your heart matters.

[00:27:52] **Tim:** Yep.

## [00:27:54] Commit Messages vs PR Messages

[00:27:54] **Adam:** well with, uh, the sucking up to 22 year olds out of the way, talk about commit messages versus PR messages. Ben, I have a feeling you have feelings on this.

[00:28:06] **Ben:** I had some feelings about this, so. Okay. A lot of stuff gets said about AI and a lot of how I process my own feelings is I'd say like 60% internal monologue and then like 45 or like 35%, talking about it on the show and like in the Discord chat. And then 5% of me is just making, snarky comments in public.

[00:28:32] **Ben:** And, and so one of the things that has people always bring up, not always, but one of the things that I've heard repeatedly about all of the agentic coding is, oh, how great is it that the code agents make these wonderfully robust and in-depth commit messages? And, I, I've seen a lot of AI commit messages and to me it just feels like AI slop.

[00:28:57] **Ben:** And so I wrote a message, I dunno if it was this morning or yesterday, and I, and I said something to the effect of like. I think I can count on one hand the number of times that I've done a git blame in GitHub. You know, you could see like, who wrote this and when it was, and thought to myself, oh, I really would've loved a better commit message to understand what the hell this person was thinking.

[00:29:18] **Ben:** And like, yes, that's happened. But like a handful of times, most of the times from the code is either obvious enough or it's obvious from the commit message. and so in response to that Scott Stroz, friend of the show, former guest talking about Angular, I believe, said to me, I like to keep my commit messages small and tight, and I like to make my pull request messages more verbose and more insightful.

[00:29:46] **Ben:** It was that moment that after like 15 years of using version control, I don't think I have ever differentiated in my head between a pull request message and a commit message. And I think part of that is because for most of my career, it has been a one-to-one. I typically have one commit that becomes a pull request.

[00:30:07] **Ben:** And then GitHub will just take your commit message and make it your PR message automatically.

[00:30:12] **Adam:** Wait, wait. Did you just say that most of your prs are a single commit?

[00:30:17] **Adam:** Oh my God.

[00:30:18] **Tim:** How do you do

[00:30:18] **Carol:** I don't know. How do.

[00:30:20] **Ben:** So I work small. I work small. And so to me historically it like the clarity is in the commit message and the code is small enough to be represented by that commit message. and now I feel like. What I've been doing is not the norm, and I don't think I ever realized that before.

[00:30:41] **Ben:** I'm not saying I've never had a PR that hasn't had multiple commits. Like I might oftentimes, not often, but like I might have like a commit that does one part of the app and then another commit that does the part that consumes that commit kind of a thing. But that's definitely the minority of cases.

[00:30:57] **Ben:** It really has been a one-to-one kind of sitch for the vast majority of my career. So I wanted to put it to the group. How do you guys think about the difference between commit messages and PR messages and like how many commits make sense to be in a pr? Because I'm, I'm just realizing I'm, I'm in a different world and I don't know what people think anymore.

[00:31:18] **Carol:** So I don't really care about the number of commits. I care about the size overall. Like what is the end result? If you've got 50 files, let's talk about it like we're 49 of them all white spaces. If so, you should have just made that a pr, right? Like that's its separate thing. I don't want a bunch of commit messages because at the end of it, all my commits are gonna be squashed into one single commit, and I'm gonna have to go through that optional, like, what do I want my commit message to look like?

[00:31:45] **Carol:** I just want a, a small like set of information that lets me know when I am looking through application, submit like I'm in this file. What changed in it? Like. I needed to now get documents I needed to change a response, like something in there so I know which commit to go compare back to. Like I don't wanna have to just go like, 'cause I go into the file and I'll right click on it and I do get, and then view history.

[00:32:13] **Carol:** I don't usually do blame inside GitHub, I just do the view history and I view the previous commit. So if there's just a little bit of information, I can decide which ones I wanna look at. But I like the PR to be very descriptive. Sorry for the squeaks.

[00:32:27] **Adam:** It's okay.

[00:32:29] **Carol:** Um,

[00:32:29] **Carol:** I like the PR to be descriptive enough that when I read it, I understand if you're doing anything complex, so I don't have to kind of go, what were you trying to accomplish?

[00:32:38] **Carol:** Like, we had a PR come in and, and my first question was, why did you even change this repo? The answer was that, oh, well the way it's being consumed now changed, but you didn't say that the story is linked to a whole nother repo and you, there's no reason to have changed this code, except the consumer is different now.

[00:32:57] **Carol:** So it, the PR needs to be descriptive enough to be able to review it with confidence, but the commits to me just need to be something I can click on for the PR to open and maybe two or three words, you know, like, that's all I wanna see.

[00:33:12] **Adam:** All of Carol's commit messages are just Stuff, and things

[00:33:16] **Carol:** Stuff, things.

[00:33:16] **Carol:** Key words. Yeah. It says whip did not work.

[00:33:19] **Tim:** Yeah, so, so our in, in our company, what we're doing lately is 'cause we're using Azure, to do deploys and it kind of rolls all that together. Commit messages don't really matter at all. is the pr that really matters. 'cause the pr, whenever we, the automated pipeline deploys something, it puts a, uh, teams message out to everyone they can see and, what's being committed, what's the PR message.

[00:33:45] **Tim:** And then also you can click it and you can go in to see the, the ticket that created the change. So you can look at the ticket and see what was being done. You can also see the individual files that were changed and the diff so that kind of handles all that. But as far as commit message that they're kind of throwaway, I mean usually it's like at a debug or a.

[00:34:05] **Tim:** Things like that. The, the PR message is more, is more descriptive and that's kind of baked into our ticketing, ticketing Jira system.

[00:34:13] **Adam:** I do kind of agree with you guys. I will say I think that this is a wild position to have considering. Prs are a thing that were invented by GitHub, right? Like all of our careers began before GitHub existed. And, and, you know, commit messages, I guess were used differently or, or, you know, viewed and read from a different perspective back then.

[00:34:38] **Adam:** And so it was like, I think all of the guidance that you get in the, in, you know, how to write your commit messages or what makes a good commit message. I won't say that it is not true, doesn't apply. It is different now, but I think that maybe some of that intent needs to be moved up to the pull request level.

[00:34:53] **Adam:** 'cause I do kind of agree, you know, for me, do try to write useful commit messages, but I definitely don't put as much effort into it to generate something that looks even remotely close to what you'd get out of Claude. Right? Like when I had to do all that. ORM conversion. The commits are hilarious 'cause it's like, it does the whole like.

[00:35:11] **Adam:** Title line break, and then like a body underneath. It's almost like writing an email. Right. You know, it's got a title a subject in a body, and there's like, every single one of 'em is like two to three sentences, paragraph form, and, and it's like, I would just never write that much.

[00:35:26] **Ben:** So, okay. Just to interject for two seconds, because it's funny to me because in my mind, because commit messages and PR messages have always been kind of one and the same. I actually do write my commit messages as a subject and a, and a and a body, because that's how, talk about like, I guess like working to the form factor of the tool.

[00:35:49] **Ben:** If I do it that way, then the PR automatically has the subject line and the body. So I'm like, oh, okay. That's just like, so I guess that's just how commit messages work.

[00:35:59] **Tim:** But, but I mean, so it sounds to me like you're not working with it. So typically we'll have a team of people working on something and the pr they'll, they'll all work together on a pr but there'll be a whole lot of different commits

[00:36:11] **Tim:** from,

[00:36:11] **Carol:** get messy

[00:36:12] **Ben:** to know. I, I've never, even when working with a team, and even when that team is unified on a particular feature, every developer has always been doing their own isolated pr. And then, you know, we all merge it together into the same code base, but we've

[00:36:29] **Adam:** Yeah, because they're doing, they live behind feature flags.

## [00:36:32] AI-Generated PR Descriptions

[00:36:32] **Ben:** Okay, so let me, let me ask a question then just to, because this came up in the context of ai. Does anyone find the veracity of the Claude Code or whatever agent you're using? Does anyone find the veracity of the PR actually helpful or is it just like one more thing I'm never gonna read.

[00:36:50] **Tim:** yeah. TLDR most of the time,

[00:36:53] **Carol:** You know, I, I like it for my boss.

[00:36:56] **Tim:** Right. Yeah. Management

[00:36:58] **Carol:** does make me sound fancy.

[00:37:00] **Tim:** Yeah. You must have done a lot of work there 'cause you wrote a whole lot about it.

[00:37:03] **Carol:** Two

[00:37:04] **Carol:** paragraphs. You got it. Are you guys familiar with conventional commits?

[00:37:08] **Ben:** This is like the feat and the fix kind of things.

[00:37:12] **Adam:** Kind of, yeah. There's a bunch of different systems, but basically, so like, think about it from the perspective of an open source project, right? So you're, you're releasing a new version and you need to write release notes, right? And so kind of if you, if you conform your commit messages to a specific format.

[00:37:29] **Adam:** You can generate your release notes, right? So if all of your bug fixes are prefixed with either bug or fix or a specific emoji or whatever, and then you write your message after that. And then maybe that, sometimes there's like a, you have to write a, a sentence or whatever in the body that describes a change, whatever.

[00:37:46] **Adam:** That's, that's kind of the gist of, conventional commits. You, you pick a convention that describes, okay, this is a bug, this is a feature, this is a breaking change, that sort of thing. From that, you can then, okay, these are the commits that are gonna be included in this release. That's, you know, we're not already released.

[00:38:01] **Adam:** And so this is the release notes. I, I can see some value in the verbose commits there. Also knowing that and, and believing that there is value in that. I am also the guy who will do commit messages where it's like the, the what's going on is I'm, for whatever reason, I'm not able to, or I'm just not feeling like testing it in my local environment.

[00:38:24] **Adam:** So I'm like testing on qa. So you have to commit and push to get it to, to go up, to, to deploy, to test. So it's like trying to fix it and then nope. Didn't work. And then, and then it's like a knife emoji, and then it's like three knife emojis, and then it's whip, and then it's like, Nope, still not working, right?

[00:38:40] **Adam:** These are my commit messages. I'm like, I do end up squashing those and putting in a, a, a good commit message once I get the fix in there. But it is kind of amusing to hold both of those valid, quote unquote, or air quotes, approaches in my head at the same time.

## [00:38:56] Squash and Merge Workflows

[00:38:56] **Carol:** So you said you squash it post sending it to qa. So can you send like a testing branch to your QA or does it have to go into a shared branch? Because once you share your commit, you can squash it. Right.

[00:39:07] **Adam:** No. Well, so we, we do, we call it cutting a new branch, right? So, and it's not on a particular schedule or anything, but just when we feel like it's time, like maybe QA is too dirty, too many things got merged into QA that are never gonna go to production, we will just delete the QA branch and then, create a new branch called QA off of main, where from wherever main is.

[00:39:29] **Adam:** and so then it's, it's pristine and we can continue to merge into it and deploy that to the QA environment. so, you know, if I have my 30 knife emoji commits in there, I don't care. Like nobody's ever gonna look at that, at the history of that branch to figure anything out before it gets into main.

[00:39:46] **Adam:** That's when it has to be squashed, like in that pull request.

[00:39:49] **Carol:** Okay. That makes sense.

[00:39:51] **Adam:** this is making me think. 'cause I, I'm, again, I'm lazy. I I say it all the time. The, I often will do the squash through the GitHub merge, you know, the, the,

[00:40:00] **Carol:** the

[00:40:00] **Carol:** button, uh.

[00:40:01] **Adam:** Yeah. Which is, okay, that's super convenient.

[00:40:04] **Adam:** But it, it occurs to me that I, I believe what happens is when you click the initial, you have to click it twice. So you click, I want to merge with squash, and then it shows you what the title and body of that squash commit will be. And I, if I'm not mistaken, all of your commit messages that are being squashed get like appended to each other

[00:40:22] **Carol:** Yep, that's what I was talking

[00:40:24] **Adam:** Yeah. And so that's

[00:40:25] **Carol:** having to scroll through that. Yeah. I, I scroll through it and I just leave one sentence then. So like, in my local, I'll, I'll just like commit what I have open. I'm like committing and I'll just put. To help developer X because then I'll remember I went and helped her do something and now I'm gonna go back to where I was.

[00:40:44] **Carol:** Or I helped him do something and now I need to go back. And I don't ever want those like popping up 'cause you know, they're just my messages to know where to pick back up at.

[00:40:52] **Adam:** Yeah, I think I might put in something in my, like my CLAUDE.md or something. I do have stuff in there to say, like, always be super concise, right? Like, I value concision over grammar every time.

[00:41:04] **Ben:** Oh, bro. You're still using a CLAUDE.md file.

[00:41:09] **Adam:** that's, so last

[00:41:09] **Ben:** Yeah.

[00:41:10] **Adam:** um, the, so I do think I'm gonna put one in there that, that's like the same rule, but specific, like lay it out explicitly, you know, I prefer concise commit messages as well and see how that affects it. Mm-hmm.

[00:41:27] **Ben:** when I was at InVision, I tried to be in the habit of always including the Jira ticket number in any commit message. And now just in my personal stuff, I'm using the, GitHub issues and GitHub. I was, I was very excited to try to use their special notation where you could say like, if this gets committed, it automatically closes this issue.

[00:41:50] **Ben:** And it, this is like one of those things. I was like, I was so excited to try it, and the first time I did it, I was like, oh my God, I can't believe that worked. And then like two or three times later, I don't know, like I just, I either forget to do it or I close the issue and then I find a little bug and I'm like, well, now the issue's closed.

[00:42:05] **Ben:** Can I mention a closed issue anymore? That doesn't seem semantically, right? Yeah. And

[00:42:11] **Adam:** do it. It's fine.

[00:42:12] **Ben:** so I don't know. I, I, I, I, I just wanna go

[00:42:14] **Adam:** You can reopen an issue that's closed, so I don't see why not.

[00:42:18] **Ben:** Yeah. Can you do, I guess you can do that.

[00:42:20] **Adam:** You can do that. It wasn't a question. It's a statement of fact.

[00:42:23] **Ben:** it's a thing. You're telling me how it is. so I don't know. I, I was excited about the idea of automating some of the workflows via commit message body, but I think that's, that's thinking in like four D chess and I'm not

[00:42:37] **Adam:** You can, you can also put it, if you don't want it in the MI message, you can put it in the pull request body as well. Just say like, re resolves pound ticket number.

[00:42:45] **Ben:** I know, but those are one and the same for me.

[00:42:49] **Adam:** fair enough, fair enough.

[00:42:51] **Ben:** All right. This is, this is like so fascinating. So this, this whole like past year, for whatever reason, I think I've just been more introspective because of midlife crisis kind of stuff. And I have just continued to find more and more cases where. I realize that everybody sees the world like radically differently.

[00:43:11] **Ben:** It's like in some ways we see a lot of things in similarly, but then in so many other ways we just, it's, it's wild that we all have any sense of agreement at all because it's just everything's so different for people. So this is just another one of those things I realized. I am not like you.

[00:43:30] **Carol:** And we all agree that we all do more than one. That we all do more than one commit. Ben's the only one that ever gets away with a single

[00:43:38] **Ben:** how everybody worked, really, honestly.

[00:43:41] **Adam:** I.

[00:43:41] **Adam:** now, I wanna run stats on how many, like what's my median number of commits per pull request. I know my average is gonna be wild because I have so many commits or so many pull requests, so many being like maybe a dozen throughout my career that are like 500 commits or, or a thousand commits or whatever from these giant refactors.

[00:43:59] **Carol:** But And I, I feel like my commits have gotten, they've just increased with AI because now I push my branch up. number number counts because I'll push my branch up, do the pr. Copilot will be like, oh, but you know, this is more readable or. That's actually broken code and I have to go, wait, is it actually broken?

[00:44:19] **Carol:** Okay, it tested out fine. Like I need to rethink this. And then I feel like I have to put a comment to prevent it from like popping up again. So now I have like two more commits on it. So.

[00:44:30] **Ben:** Well, and there are a lot of things that I think historically would have risen to the level of, you know, like an interactive rebase or a squash or something. But now that I'm a little more hands off keyboard, I think I'm much more likely to just let the, the AI rip and not care so much. I, I have found that you can tell AI to amend the last

[00:44:55] **Ben:** commit. Yeah. You know, like if it does something and then it catches something else, or I catch something and be like, Hey, fix this, and then amend the previous commit and it'll it'll

[00:45:04] **Ben:** do right? You don't, you don't, not once it's pushed.

[00:45:07] **Adam:** You can do so, I mean I do this all the time. You can do a force push as long as you know you're the only one on the

[00:45:12] **Ben:** Yes, that's true. I have done it once or twice, but I also like to think it's the pedant's for Why risk

[00:45:19] **Ben:** the, the public shame to There's a, uh, I don't know what version of git they added this, but there's a new, it's --force-with-lease. Force-with-lease, which basically is, I'm, I'm gonna do a force push, but only if there hasn't been anything that somebody else pushed to the branch between the time that my last push and my, my force

[00:45:42] **Ben:** oh, I didn't know that was a

[00:45:43] **Adam:** So it stops you from making that clobber, somebody else delete somebody else's changes mistake, which is nice. Yeah. let's wrap it up there.

## [00:45:52] Patreon

[00:45:52] **Adam:** this episode of Working Code is brought to you by your local lead AI ambassador

[00:45:56] **Ben:** What, what?

[00:45:57] **Adam:** like you.

[00:45:57] **Carol:** Thank you, sir.

[00:45:59] **Adam:** If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:46:11] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:46:14] Thanks For Listening!

[00:46:21] **Adam:** We're gonna go record the after show. That is that the outro music's gonna keep playing or it's gonna start playing and then it finishes playing. And then, if you're not a patron, that's the end. But if you are a patron, it's not the end.

[00:46:26] **Adam:** We keep talking. Yeah. And on tonight's after show, we're gonna talk about Steve Yagi again. Ben always has like a thousand blog posts that he's read that he needs to get off his chest. So, we're gonna have to talk about Gastown to AI Vampire. I'm sure we'll have plenty of other stuff to talk about as well.

[00:46:42] **Adam:** so you know, if you wanna check that out, you can go to patreon.com/workingcodepod, throw a few dollars our way. We'll be greatly appreciative, and you'll get the after show and other perks in return.

[00:46:52] **Tim:** Listen to Starbucks coffee.

[00:46:55] **Adam:** Yeah, that's right. That's gonna do it for us this week. We'll catch you next week and until then,

[00:46:59] **Tim:** Listen, we definitely commit to this statement without an amendment, your heart matters.
