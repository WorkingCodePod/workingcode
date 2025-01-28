---
title: "202: Um, Actually!"
description: "Tim and Ben go head-to-head in a trivia game inspired by Cunningham's Law, answering questions, with points awarded for correct 'um, actually' corrections."
date: 2025-01-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/202-um-actually/id1544142288?i=1000684997856"></iframe>

In this week's episode, Tim and Ben go head-to-head in a trivia game inspired by Cunningham's Law, answering questions, with points awarded for correct 'um, actually' corrections.

The game reveals lesser-known facts and recent updates in HTML, CSS, JavaScript, and browser functionalities.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/202-um-actually.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** So here's your next question. You will soon be able to style every aspect of the select element with pure CSS.

[00:00:06] **Tim:** Me, me, me, me.

[00:00:07] **Adam:** Yes, Tim.

[00:00:07] **Tim:** Uh, actually all that is false. Cause soon in internet terms probably means 50 years.

## [00:00:34] Intro

[00:00:34] **Adam:** Okay, here we go, it is show number 202, and on today's show, I would like to play a game.

[00:00:39] **Tim:** Oh, scary.

[00:00:43] **Adam:** these guys have basically no idea what's going on, but we're going to play a game today. I'm going to pit the two of them against each other. Ben and Tim are here with me, unfortunately Carol is busy, I think she's traveling for work, so she's got an excused absence tonight. But before we get into our game, why don't we do our triumphs and fails, as usual.

[00:01:02] **Adam:** So Tim, why don't you go first?

## [00:01:04] Tim's Triumph

[00:01:04] **Tim:** I'm going to start with a triumph, two triumphs, one kind of life related or one sort of work related. So the first one is adulting. So as you know, I've got, you know, later stage teenage kids, 21, 19. today my wife was really not feeling it. She's in a lot of pain. And, so the kids just on their own said, Hey, we'll go to the grocery store.

[00:01:23] **Tim:** We'll pick up all the groceries. they didn't spend their money, obviously, but, they spent ours, but yeah, they went to the, went to Kroge, went down to Kroge or K Rogers, whatever you want to call it, picked up stuff to make hamburgers and fries and all that, and came back and cooked dinner for us.

[00:01:37] **Tim:** And I was really expecting that with the, would be unexplicably burnt on the outside and yet raw in the middle, but they actually were cooked, cooked pretty well, and you know, fries and some vegetables and some carrots and, you know, stuff like that. So, yeah,

[00:01:51] **Adam:** The coattails continue.

[00:01:53] **Tim:** Yeah, just, you know, it's, it's nice.

[00:01:55] **Tim:** You're proud of them when they like do cool stuff, like get awards and everything. But I mean, actually adulting is, is, seems to be really hard for young people these days, like doing normal stuff that you just should know. So for them to just drive to the store themselves. Buy the stuff and there was no, tears.

[00:02:14] **Tim:** Apparently they, they danced. They liked it. They liked to, they liked to dance to the, they do that to embarrass us. So every time they go to a store and there's music, they'll start doing this little cha cha groove to the music. That's very embarrassing. they did that together.

[00:02:27] **Adam:** That sounds like something I would do to my kids. Like it would be the other way around for us.

[00:02:30] **Tim:** I think it started that way.

[00:02:31] **Tim:** We would do that to our kids and they hated it. Now they do it to us. And yeah, so how the tables have turned.yeah, so proud of them. not a huge thing, but it's like, you know, it's, it's, it's nice to know they won't starve. and then work related, we're actually hiring some, some new people. We had some people leave and like, just, you know, it's, we're kind of at, I think in the, you know, I've been around this company 25 years, we've got a lot of gray hairs, in the company.

[00:02:56] **Tim:** And I think that's good, but I also think that's bad, right? People sort of get stuck in their ways. And it's sort of getting a rut and I think bringing some new, we're bringing in some younger folks, just kind of get that energy back. And, yeah, so we've been hiring several people, some IT folks. yeah, so I think that's, that's kind of cool to just see some new blood coming in and bringing some new ideas.

[00:03:17] **Tim:** So happy to see how that works out.

[00:03:19] **Adam:** Well, good luck on your hires.

[00:03:22] **Tim:** Well, I, they're not my, I'm not actually interviewing them. It's just, they've asked me for recommendations. I've recommended tons of people, which is cool. Cause they do have a, we do have a headhunter,

[00:03:31] **Adam:** You get a bonus.

[00:03:32] **Tim:** bonus that people pay. Uh,so, but yeah, so we've got several folks that, that I've recommended that they're talking to.

[00:03:39] **Tim:** So

[00:03:39] **Ben:** sorry, just going back to your first, Triumph there. Both your kids have graduated high school at this point, right?

[00:03:45] **Tim:** Yeah, Max has one semester left of college, so he'll be done with four years very shortly. And Lily, Lily's taking a year off to kind of figure out what she wants to do.

[00:03:53] **Ben:** Oh, nice.

[00:03:55] **Adam:** man. I remember when Max was just a wee boy.

[00:03:58] **Tim:** Yeah, bring it, bring them to conferences and stuff. So yeah. So anyway, that's my triumph. How about you Adam Tuttle?

## [00:04:06] Adam's Triumph

[00:04:06] **Adam:** I am also going to go with a triumph and it's a simple one. It's just that I went to work today, even though I really didn't want to. Uh, I woke up.Yeah, I woke up and you know, it's a good day to be above ground. I got to start there. but I had a really bad headache, and that plus it's just, the weather is awful.

[00:04:26] **Adam:** Like it's so cold and windy here. It was like 21 degrees Fahrenheit and like, 13 to 20 mile an hour winds. So the fields were like, was like barely two digits, you know, it might've been like 12 or something. And we just decided that's too rough. We're not going to go walk the dog in that. And so between that and the headache and just kind of feeling blah, I was like this close to calling out sick today.

[00:04:53] **Adam:** Just being like, you know what? I just need a mental health day to just lay down and watch a movie or something. But I powered through it and I got some important stuff done at work. And honestly, after a couple of hours, I was just in the groove, you know? that's it. Simple little thing.

[00:05:07] **Tim:** Hey, mind over mattress. Sometimes that's, that's what it takes. A little,

[00:05:14] **Ben:** I'll tell you, going just back to the idea of a headache. I'm going to say something that maybe is like super obvious to a lot of people, but it's not something that really occurred to me much in most of my adult life until recently, which is that I have been historically an Advil or an ibuprofen user.

[00:05:32] **Ben:** And that was my pain reliever of choice. And I just assumed that it sort of was the best thing for all, all that ails you. And I have only recently in like the last year, thanks to my who has turned me on the idea of you to zing. Tylenol or acetaminophen for headaches specifically and Advil for body aches and pains.

[00:05:53] **Ben:** And I have found that the Tylenol just works so much better for my headaches than the ibuprofen ever did. And I'm, you know, your mileage may vary. listeners, dear listeners, but it, I, I know that things like Advil and Tylenol and, Olive all work through different pathways in the body, but it never occurred to me that you could mix and match based on different types of ailments.

[00:06:16] **Ben:** So,

[00:06:17] **Tim:** What about aspirin? People stop using aspirin for some reason.

[00:06:20] **Ben:** I, I, I mean, it's a, it's a blood thinner, so I think some people have to be careful, but then I think some people take it specifically because it's a blood thinner, right? For, for heart stuff.

[00:06:29] **Tim:** I do. I take it specifically for blood thinning, but also it's really good on headaches because it's like A

[00:06:35] **Ben:** I see.

[00:06:36] **Tim:** that the pounding in your head is because the blood pressure is a little high, maybe, but that depends on what's causing your headaches. So,

[00:06:43] **Ben:** I mean, it's the best move to literally just take four different painkillers whenever you have a pain.

[00:06:48] **Tim:** it's, uh,

[00:06:48] **Adam:** it all, just.

[00:06:49] **Tim:** yeah, it sounds like that's bad news for your liver. So I would, I don't know if I'd do that.

[00:06:53] **Ben:** I mean, my liver doesn't complain.

[00:06:57] **Adam:** I mean, I would say it's all on the table, but you know, do one at a time. Take a Tylenol and then wait an hour. And if it's still not helping at all, maybe take an ibuprofen. If it's still not working after an hour, take an aspirin. I don't know if you can combine all three,

[00:07:09] **Tim:** they just take some Ivermectin and you know,

[00:07:12] **Adam:** that doesn't work, then it's bleach.

[00:07:14] **Tim:** yeah,

[00:07:14] **Adam:** and we have to say, we are not qualified to give medical advice, talk to your doctor, blah, blah, blah.

[00:07:19] **Tim:** I'm not qualified to put on a band aid. So yeah, don't, don't, don't listen to me.

[00:07:23] **Ben:** you know, bandaid on your finger and you're momentarily worried that you did it too tight? And you're actually cutting blood off and suddenly that's going to be like a necrotic problem.

[00:07:34] **Adam:** no, because it's every time I put on a bandaid, it is too tight. There's no such thing as not tight enough, on a finger bandaid. I'm not capable of putting it on the right, right tightness.

[00:07:45] **Ben:** I always have to adjust. Good times.

[00:07:49] **Adam:** so that's me. I went to work today. How about you, Ben? What do you got going on?

## [00:07:52] Ben's Triumph

[00:07:52] **Ben:** I will also go with a triumph, this one tech related, which is that, over the break, meaning between season one and season two in our little hiatus, I've been just Doing more experimentation in code and, I have come historically to Invision from a very, very heavy SPA or single page application architecture experience where you have an API and you have a thick client that makes calls to that API from the browser.

[00:08:20] **Ben:** And I have in the past couple of months really been trying to explore the MPA or multi page application space, which is more akin to a. You know, the old school request response where you do all the rendering on the server, return a fully rendered page, and Bob's your uncle. And I have just been really enjoying it.

[00:08:40] **Ben:** Obviously, there is a level of richness of interactivity that, that you have to give up when you're stepping away from that spa experience. But what I have found, especially when I'm in this sort of exploratory mental space, That not having to worry about creating a parallel API and a parallel front end and having to coordinate calls and make sure I handle all my AJAX errors and all that jazz correctly, it's just, I feel like allowed me to be much more free in my thinking about the thing I'm working on and not so much worried about the.

[00:09:14] **Ben:** The architecture itself. And, you know, I'm putting files here and then I'm not liking where they are. So I'm just moving them to another folder and I'm changing some, some routing and it, and it just works like, it's just, it's just much less to coordinate. And again, it's trade offs all the way down, of course, but I'm finding that it just allows me to have more fun with the code and more fun with the, the experimentation and the exploration.

[00:09:37] **Ben:** I've actually tried a bunch of different things lately that I don't think I would have tried. If I was really stressing the single page application architecture. So I'm just really calling that a huge triumph. I'm not recommending that multi page applications be used in lieu of spas or vice versa. I think they both have their place and Being able to have my feet in both ponds, I think is very, empowering for me.

[00:10:03] **Adam:** You heard it here first. Ben Nadell comes out strongly against single page apps.

[00:10:08] **Ben:** That's right. I don't even like CSS. It's just all the Times New Roman and black on white backgrounds. I will say, okay, so if I can hedge my, my triumph, my excitement with a, with a small failure, which is that the, ColdFusion 2025 beta came out in December, I think, or the very end of November. I can't really remember.

[00:10:32] **Ben:** And, you know, you go back 10, 15 years ago when betas would come out and I would just, it was like a stop the world moment where every other train of thought that I had was put on hold. I would install the beta. And I'd spend, you know, weeks digging into all these little features and how does the new beta work with this?

[00:10:50] **Ben:** And how's the new beta work with that? And as I've gotten older, I just, I've lost my, I don't want to say I've lost. I'm much less motivated. I'll say to put everything else in my life on hold to explore new betas. And that's not just with cold fusion. That's with all the other libraries that I use when, when pre releases come out or release candidates and betas.

[00:11:14] **Ben:** I just. I don't know. I just don't care as much anymore to be on that, on that bleeding edge of stuff. I'm much happier to let other people find those really early bugs.

[00:11:23] **Adam:** It's called getting old.

[00:11:25] **Tim:** It's called, it's called like, it's a really old, mature, let's say mature. That's a little nicer product. I mean, how much are they really going to change? They're, they're changed some stuff for charting. They changed some stuff for spreadsheets, apparently. I mean,

[00:11:38] **Ben:** massive.

[00:11:39] **Tim:** it's like, it's not doing new and really, really interesting things.

[00:11:43] **Tim:** And if. A lot of the things when they do add what they consider new and interesting, it's probably done better somewhere else already. So, I mean,

[00:11:52] **Ben:** and, and I will say this also, because I have worked in a containerized environment, meaning Docker for Mac and, and. You don't, like, I almost never install anything software development related directly on my computer anymore, except for my IDE. It's, it's almost always inside of some sort of a container, and the, the ColdFusion 2025 beta is not available yet.

[00:12:19] **Ben:** For Docker, simply because I'm on an Apple M1 and the, the JVM platform emulation is like total dog slow. anyway, I just, I can't bring myself to install Cold Fusion directly onto my computer. Just feels weird. Like I don't even, I don't even know if I know how to do that anymore. Like, how do I even know

[00:12:42] **Ben:** How do I even know if it's running or, or if it is running, how do I know how to stop it? Literally, my whole development. Mindset has been centered around containers for the last 10 years. And everything I know now is Docker Compose up, Docker Compose down and, and Docker Compose YAML files. I don't know anything about, what is it, like plists or isn't there, there's like some sort of thing that makes sure a process starts when your computer starts.

[00:13:10] **Ben:** I don't know any of that stuff, but it's so foreign to me at this point. And so when something's not available via Docker, I'm just, I'm like doubly unmotivated to try it. So,

[00:13:22] **Adam:** okay. I was, I was having trouble following you for a minute there. And I was like, but I use Lucy and Docker all day, every day. And it's, and it's fine. And it's not that there's not performance issues or whatever. What you're saying is the ColdFusion 2025 beta. There's no docker available for that.

[00:13:37] **Ben:** right. There's a, there's an AMD Docker available, an AMD image for Docker, but not an ARM. I think I'm, I think Max, the M, the M chips are on ARM. That's the, the fancy, the

[00:13:50] **Adam:** There and you can, you can run it in like compatibility mode or, or whatever they call it

[00:13:55] **Ben:** Yeah. But it's

[00:13:56] **Adam:** like virtualized. Yeah. But it is slower.

[00:13:58] **Ben:** JVM, cause that's what I was trying to do when I first got this computer and it was like, A crapshoot whether or not the JVM would start.

[00:14:06] **Adam:** Mm-hmm

[00:14:07] **Ben:** Sometimes it would just hang mid boot. anyway, so, mostly triumphs, a little bit of fails. I wish I was more motivated to that, but,

[00:14:14] **Tim:** heard, so you heard it here. He's against spas and he's against 2025 cold fusion.

[00:14:21] **Adam:** And Java

[00:14:22] **Tim:** Yeah.

[00:14:23] **Adam:** and arm chips

[00:14:24] **Tim:** Yep. He's just a negative Nelly all the way down.

[00:14:27] **Ben:** right. Where's that cloud? Let me yell at it.

[00:14:30] **Adam:** Oh,

[00:14:31] **Ben:** All right,

[00:14:32] **Adam:** well, it sounds like we're all off to a, a shaky, but, successful nonetheless. Start for the year, so.

[00:14:38] **Ben:** we go.

## [00:14:38] Explaining The Rules

[00:14:38] **Adam:** Cool, well then, let's get into our game for the day, so, yeah,

[00:14:44] **Tim:** is, you, you sprung this on us.

[00:14:46] **Adam:** I did, and that was very intentional, so for, I'll kind of explain it two ways, a thing that we mention on the show a lot is cunningham's law, which is, if you, the fastest way to get the, I know you know, the fastest way to get the, the right answer is to post the wrong answer, right?

[00:15:02] **Tim:** to ask a question, but to post an incorrect answer.

[00:15:06] **Adam:** Right. and then, and that's specifically on the internet or whatever, but, and then, also for me, I'm a big fan of the, I guess you could say like video production company or something. So formerly CollegeHumor, now they're, they've kind of splintered off and done their own thing. It's called Dropout.

[00:15:23] **Adam:** They make a couple of shows that I really like, including Game Changer and Make Some Noise, but there's another show that they have called Actually.

[00:15:29] **Tim:** Actually. Me, me,

[00:15:31] **Adam:** Exactly, yes. And, and so on that show, the host reads a question. It's usually something incredibly nerdy like Dungeons and Dragons related, or Lord of the Rings, or like some 80s TV show, or some super nerdy book or whatever.

[00:15:44] **Adam:** We are not going to be doing that. Obviously, this is a web development podcast, so I'm going to read you, for today's game, it's going to be HTML facts. However, Something about the facts that I read you will be false, and it will be your job to identify what is false. And so there's a couple of things about this.

[00:16:02] **Adam:** To ring in, obviously we don't have like a buzzer technology. So I need you to both tell me what your buzzer sound is going to be. And when, when you want to, to, to bring in and answer the question, you have to make this noise. So Tim, what's your buzzer sound going to be?

[00:16:14] **Tim:** me. Me, me, me.

[00:16:17] **Ben:** And, and Ben, so they're not going to be difficult at all for me to tell them apart because they're, they're not similar at all. Thanks guys. I'll go ding, ding, ding, ding.

[00:16:28] **Adam:** There you go. Whatever. Just, just do something. It doesn't, doesn't even have to be the

[00:16:32] **Ben:** I'll be dinging so

[00:16:33] **Ben:** hard.

[00:16:33] **Adam:** Make it clear that you're, you're the, the one buzzing in, and then, you'll have to answer the question in the form of a nerdy correction.

[00:16:43] **Adam:** So you start with, actually, and if you don't start with, actually, then you don't get the point, even if you're right.

[00:16:49] **Tim:** Okay, okay, okay, okay. I smell you're stepping in.

[00:16:55] **Adam:** like I said, something about these statements will be false. Sometimes it'll be a little bit more obvious than others, but your job is just to identify what's false and come up with the, the, how it's false. Like, what is the correct version of what I said?

[00:17:08] **Tim:** Okay,

[00:17:09] **Adam:** I'll start it off easy.

[00:17:10] **Tim:** are the stakes here? What are

[00:17:12] **Adam:** Uh,

[00:17:12] **Adam:** internet points. I don't know. Maybe we can come up with something later. For right now, we're just going to go with points. Yeah, and we'll figure it out. Maybe I'll, you'll, you'll get, coins in my ICO or something.

## [00:17:28] Question 1

[00:17:28] **Adam:** anyway, we're start off easy, easy question to get you started on the, on the process, and then we'll get a, we'll try to sort of ramp it up from there. All right. So here's the first question. You can add a separator line to a select dropdown menu by adding a BR tag between the options where you want the line to appear. So just like on, you know, in windows, there's the menus across the top of the applications or

[00:17:50] **Ben:** ding, ding.

[00:17:50] **Adam:** Okay, go ahead.

[00:17:52] **Ben:** actually, I know it's not the break tag, but I don't know what it is. so that's obviously not the right answer, but

[00:18:02] **Adam:** All right. I guess I'm going to go to Tim. Go ahead.

[00:18:06] **Tim:** we playing for? Oh. Ooh. Ding, ding, ding! actually, it's the HR tag.

[00:18:09] **Adam:** That is correct,

[00:18:10] **Ben:** you can have an HR tag inside your options.

[00:18:15] **Adam:** Yeah. Yeah. So you put an HR tag between your options and it gives you that little like line with a little bit of margin above and below it to like space out your options. Yeah. Yeah. Oh, you

[00:18:25] **Tim:** Actually, I just guessed. I, I, I'm like, nah, that probably should do it.

[00:18:30] **Adam:** yeah. Yeah.

[00:18:31] **Tim:** I've never actually done that in my life.

[00:18:33] **Ben:** on. I'm taking a note here in the doc just because I feel like I need to look that only because I can't tell you how many times I'm sure

[00:18:41] **Adam:** So I know I, I will, I have a whole spreadsheet here with the questions, answers and the, and some references. So I, when we're done, I will drop all the

[00:18:50] **Ben:** Okay. Then I am not going to

[00:18:51] **Adam:** so you'll be able to go look them all up.

[00:18:54] **Ben:** Toit.

[00:18:55] **Adam:** Um, okay, moving

## [00:18:58] Question 2

[00:18:58] **Adam:** on question number two, browsers are getting toggle switches. simply add a switch attribute to your input type equals checkbox, right?

[00:19:06] **Adam:** So input type equals checkbox and then switch just the word switch also inside that same tag. and the browser will take care of the rest.

[00:19:13] **Tim:** Ding, ding, ding.

[00:19:15] **Adam:** Go ahead, Tim.

[00:19:16] **Tim:** Actually, it's JavaScript.

[00:19:21] **Adam:** that is not the answer that I'm looking for.

[00:19:24] **Ben:** I feel so I, I knew I was listening to either shop talk show or syntax FM. They were talking about the switch. I can't remember what they said. I thought it was a checkbox with an attribute for switch. Cause then it could do graceful, like a graceful fallback to just a check. Is it, is it well, actually, actually that it's, it's not type checkbox with an attribute.

[00:19:47] **Ben:** It's type switch.

[00:19:49] **Adam:** That's a good guess, but no. So, I was a little trickier in how I hid the lie in here. So, As of the time that we're playing this game, January 2025, only Safari has implemented this feature, and it hasn't even been specced yet. Like, it's just a thing that works in Safari.

[00:20:07] **Tim:** Who uses Safari? Come on.

[00:20:10] **Adam:** Well, yeah, I agree. I am also not a fan of Safari, even though I'm a 100 percent Mac person. So I think that the, the Apple folks were just like, Oh, this is awesome. And they were like, yo, we're going to do it. I guess it was probably relatively easy for them to implement. So they were just like, yeah, sure.

[00:20:26] **Adam:** Here. And then maybe the spec will come later or something, but yeah, it just, it works in Safari and nowhere else. And there's no spec for it yet or anything.

[00:20:35] **Ben:** If I could do a quick side quest there for a second, cause I'm, I'm pretty sure in the little interview that I was listening to, it was probably syntax, they were talking at the checkboxes, even today's checkboxes have something called an indeterminate state. Which is where it's neither, it's technically, I think checked if you, if you check the, if you look into the checked property, but it's visually rendered as like a dash instead of a check mark.

[00:21:03] **Ben:** So it's neither blank nor check box or a check mark. and I, yeah, I, yeah, yeah. It's like Schrodinger's, check box. but I only recently heard that and I have yet to think of a use case for it. I think the only place I've actually seen it being used is one of those, Select all buttons. That's at the very top of a list of check boxes.

[00:21:23] **Tim:** It

[00:21:24] **Ben:** but other than

[00:21:25] **Adam:** selected some of them, but not all of them. So it's indeterminate. And if you, if you click, maybe it'll select all. And then if you click again, it'll select none.

[00:21:32] **Ben:** yeah, yeah. But other than, other than that, it just feels like it's a terrible user experience because it's very unclear as to whether or not it's actually a check.

[00:21:40] **Adam:** You're yeah. That's an interesting fact as well. I will say you gotta be kind of careful, Ben. This is a, this is a web dev facts game. So if you go off on too many tangents, you might spoil some of the

[00:21:49] **Ben:** So yeah. Okay.

[00:21:50] **Tim:** might give it to me. Yeah.

[00:21:51] **Adam:** Uh, but no, no points awarded for that one. sorry guys.

## [00:21:55] Question 3

[00:21:55] **Adam:** All right. So question three, an HTML search tag, right? Like open bracket or, or less than search greater than search. A search tag is being added to replace input type equal search. The justification is that it's just easier to remember.

[00:22:11] **Ben:** Ding, ding, ding.

[00:22:14] **Adam:** That's not even your buzzer sound.

[00:22:17] **Ben:** I'm going to, I'm going to say, actually, I don't know if this is even remotely true. I'm going to say that you're tricking us with the. Reasoning that it is coming, but it's not that it's easier to remember. It's that it will be easier to style.

[00:22:31] **Adam:** Oh, that's an interesting thought. That is incorrect. Tim, do you want to steal?

[00:22:38] **Tim:** actually, there's no good reason whatsoever.

[00:22:43] **Adam:** That is also incorrect.

[00:22:44] **Tim:** No, it's true.

[00:22:47] **Adam:** you guys can have more than one shot at it if you have other ideas, but, or I can just tell you

[00:22:51] **Tim:** Did you repeat the question one more time? Let

[00:22:52] **Adam:** Sure. Yeah. And an HTML search tag is being added to replace input type equals search. The justification is that it's easier to remember.

[00:23:01] **Tim:** actually it's, it's easier for the browser to parse.

[00:23:03] **Adam:** No.

[00:23:05] **Tim:** I'm guessing now. I was guessing from the

[00:23:07] **Adam:** All right. All right. So, again, I was being a little tricky here, so it is being added, but instead of replacing input type equals search, it replaces div role equals search. So previously for accessibility reasons, you're supposed to wrap your search input in a div role equals search for accessibility, but instead of that, you just wrap it in a search tag.

[00:23:28] **Adam:** I guess that's easier to remember. So you'll be more likely to do it for accessibility reasons.

[00:23:33] **Ben:** Gotcha. So it's, it's more of a landmark than it is

[00:23:37] **Ben:** a

[00:23:37] **Adam:** kind of. Yeah. It's a,

[00:23:40] **Ben:** like a, like the main and the header and the footer and the

[00:23:43] **Adam:** Yeah,

[00:23:45] **Ben:** the,

[00:23:45] **Ben:** aside, if you will,

[00:23:47] **Adam:** there's a word that I'm struggling to come up with, not syntactically, but like

[00:23:51] **Tim:** Semantic.

[00:23:52] **Adam:** semantic. Yeah. So it's more semantic.

[00:23:55] **Tim:** Actually, I was, that was what I was trying to think to say earlier. Semantic, but like, probably wouldn't think of that either.

## [00:24:01] Question 4

[00:24:01] **Adam:** Okay, here we go. you shouldn't be adding rel no opener, no referrer to external links anymore. So if you remember, there was a big hubbub several years ago about, whenever you link offsite, in order to not give that link access to the page that opened it, right? If you, if you're linking offsite with like a target blank to open in a new window or new tab, if you don't use rel no opener, no referrer, no referrer.

[00:24:27] **Adam:** Then that page that you're opening would have some access to the page that opened it. So it was a big hub up to like, you have to always, whenever you're doing external links or with the target equals underscore blank, make sure you put that on there. but here's, so here's the question. You shouldn't be adding those to external links anymore.

[00:24:44] **Adam:** Finally, adding functionality to automatically apply this behavior in 2025. Chrome became the last browser to do this. As it turns out, adding no opener and no refer opened a security hole that could have leaked user information or opened the door to phishing.

[00:25:01] **Ben:** Ding, ding, ding.

[00:25:03] **Adam:** Yes.

[00:25:05] **Ben:** actually you should still add these. Is the entire premise of the question wrong?

[00:25:14] **Adam:** incorrect.

[00:25:15] **Ben:** I 100 percent thought that this was still a best practice.

[00:25:20] **Adam:** So did I, until I read the, the, the source material on which I based this question.

[00:25:24] **Ben:** Oh,

[00:25:25] **Tim:** ding. what was mine? Me, me, me, me.

[00:25:28] **Adam:** Go ahead.

[00:25:29] **Tim:** actually it has something to do with cors, which I never understood anyway.

[00:25:34] **Adam:** I can't say that that's false, but it's not the answer that I'm looking for. So I'll just give it to you because I don't think I did try to emphasize it a little bit in the question, but it was, so it is true. Just basically how I said it there. and Chrome was the last to add the feature, but it didn't happen in 2025.

[00:25:51] **Adam:** It happened in

[00:25:53] **Tim:** Oh, come on now.

[00:25:54] **Adam:** 2021.

[00:25:56] **Ben:** I'm, are you, is what you're saying that the browser When you're linking to, I'm going to say a different origin, it's, it automatically implements that behavior anyway.

[00:26:07] **Adam:** I believe that is true, at least when you're doing target equals underscore blank. I think it has something to do with the, the parent page and the child page and being able to access like window dot parent.And so, it only applies, this is a guess, but I'm pretty sure it only applies, when you've got that, like, new tab, new window situation going on.and, and yes, the browser is automatically, doing the right thing for you, and from what I understand, and again, all my notes will be in the show notes, the, adding no opener, no referrer actually makes things worse. Then what the browser is doing by default as of 2021. Yeah, you learn stuff, new stuff all the time, don't you?

[00:26:50] **Tim:** It makes me realize how little I actually program HTML these days.

[00:26:55] **Ben:** I only know this. I had never heard of this before until it was opened as a, as a bug bounty thing, I think at work, and then the security team came up with a set of best practices. But again, this was. Six years ago. So

## [00:27:11] Question 5

[00:27:11] **Adam:** All right, let's go back to HTML selects.

[00:27:14] **Ben:** can we just for the, for the reader's benefit, it should be stated that the score is neck and neck at one to zero.

[00:27:23] **Adam:** Yes, Tim has one, Ben has zero. I might have made this game a little too hard.

[00:27:27] **Tim:** Yes. I think, I think you way overestimated our, our, our, our understanding of HTML.

[00:27:33] **Adam:** We shall see. So, all right, we're going back to selects. So here's your next question. You will soon be able to style every aspect of the select element with pure CSS. Eliminating the need for creating custom select components made of divs that give you the power to style them however you want, but also the responsibility of re implementing every little detail of a select from keyboard shortcuts, keyboard focus, to hover, to accessibility, probably keyboard shortcuts as well.

[00:27:59] **Adam:** Even better, you can do all of this without changing the HTML of your existing selects.

[00:28:05] **Tim:** Me, me, me, me.

[00:28:07] **Adam:** Yes, Tim.

[00:28:08] **Tim:** actually all that is false. Cause soon in internet terms probably means 50 years.

[00:28:16] **Adam:** that is not the answer I'm looking for.

[00:28:18] **Ben:** All right. I'll go ding, ding, ding, ding.

[00:28:21] **Adam:** Ben,

[00:28:22] **Ben:** I, I think that, the, actually the part of that that's incorrect is that you will have to change the HTML.

[00:28:29] **Adam:** exactly right.

[00:28:31] **Tim:** oh, it's tied.

[00:28:32] **Ben:** Nice.

[00:28:33] **Adam:** good job. So yeah, it's funny. The, there's very little changes that will be required to your HTML, but the big thing is that because they're kind of giving us more control over, what the, the, button on the page, right. The part that gets rendered on the page before you interact with it, that's going to be a button.

[00:28:52] **Adam:** And then within that, there's going to be a new tag called selected option, which will have some custom stuff about it. That'll like let you say, okay, this is the, this is the text that was selected, whatever you can style at all, whatever that there there'll be links in the show notes where you can go look up all the details, but basically, yes, there's some new HTML that you're going to have to add, but I'm really excited about this because, it's gonna just like a whole category of custom components that are super popular to make.

[00:29:20] **Adam:** and difficult to get right, it's just going to go right in the garbage because it's going to be built in now.

[00:29:25] **Tim:** right. And I feel like I'm so late to this party and by late, I mean, I have not yet arrived.He's still at home thinking about

[00:29:32] **Ben:** like the, between the, the summary and the details toggle that GitHub started using, I don't know, it feels like eight years ago. And the dialogue and the modal windows that are now mostly supported. And the new hotness is the anchor positioning.

[00:29:49] **Ben:** So you can see

[00:29:50] **Adam:** Oh yeah, yeah.

[00:29:51] **Ben:** the left of this button.

[00:29:52] **Adam:** yeah.

[00:29:53] **Ben:** And now this, it's like, it's so cool and so exciting. And I have no idea how well any of it is supported. And it just makes me so nervous that, that, I never know when it's going to be safe.

[00:30:06] **Adam:** The thing about new features on the web is like, that's great, especially if you have the freedom to say screw anybody who's not using an evergreen browser that was restarted within the last week. Right? not everybody has that freedom, right? There's a lot of, B2B apps or, you know, if you're, if your customers are just, You know, for whatever reason, still

[00:30:24] **Tim:** Laggard, laggards.

[00:30:26] **Adam:** IE11 or whatever, right?

[00:30:27] **Adam:** Like even that, as recent as it is, is, can be problematic, but, but the world, it does mean that like, these things are coming, right? So you may not be able to use it today, but you can probably use it in a year. And that's a lot sooner than you could use things that were coming out in the age of XP.

[00:30:44] **Ben:** I think we've talked about this on the show before, but I know now when you go to MDN, Mozilla Developer Network, they have at the top what they call either something is, what is like widely available or newly available. And then there's a baseline, I think, and Google has come up, they've basically drawn a line in the sand, my understanding here.

[00:31:08] **Ben:** Is that once something has been around, I think for 30 months, they're considering it widely available. And I mean, I don't know if that's any better metric than anything else, but it's, it feels like, well, if Google is going to say that this is the line in the sand, maybe that's at least something for me to anchor to anyway.

[00:31:27] **Adam:** Yeah, I mean, that's a reasonable place to start.

## [00:31:30] Question 5

[00:31:30] **Adam:** Alright, so we are five questions in. We've completed five questions and the score is tied at one to one. So why don't we just go until we get, let's go, we're about 30 minutes into the game here, so, or into the episode. So why don't we go until we get a, a tiebreaker, and then, we'll call the game there for tonight.

[00:31:44] **Adam:** And, well, maybe we'll have to revisit this again sometime. Alright, so, next question. let's stick with HTML. a new popover feature will allow you to create popovers that don't require any JavaScript to work. Unfortunately, it doesn't support the click anywhere outside of the popover feature, or click anywhere outside of the popover to dismiss the popover.

[00:32:06] **Tim:** Meme, meme, meme.

[00:32:07] **Adam:** Yes, it

[00:32:08] **Tim:** It does support clicking outside to get rid of it.

[00:32:12] **Adam:** does. Can you

[00:32:13] **Tim:** I'm actually, I'm actually, I'm

[00:32:18] **Adam:** All right.

[00:32:19] **Adam:** I'll give you that. can you, I'll give you credit, especially if you can tell me. what, it's not just automatically supported. There's a, like a way to toggle it on. Do you know how to do that?

[00:32:30] **Tim:** um,

[00:32:31] **Tim:** a, it's, are they called invokers? Executors,

[00:32:37] **Adam:** it's, I believe it is called an invoker. it's like one of the few things that is being implemented under the umbrella of invokers. so this was a really hard, I would have considered it a bone, like a bonus point, but, so you add the popover attribute to,a tag. I think it's so div and it makes it a popover.

[00:32:53] **Adam:** And if you do popover equals auto, then it will auto dismiss when you click outside of the popover

[00:32:59] **Tim:** so I think we got 50, 50 on that one.

[00:33:01] **Adam:** yeah, so it's called light dismiss.

[00:33:05] **Ben:** Tim, I, you know, we started this game and I was like, Tim is management. I'm going to freaking crush him. He's going to, I'm going to beat him so hard. His grandmother's going to feel it. And, I am eating my humble pie.

[00:33:22] **Tim:** I think we're at one and a half each.

[00:33:25] **Adam:** Yeah, we'll, we'll go with that. That seems, that sounds fair. Oops. 1. 5. Okay. and you know what, I'm, I'm just realizing that, all of these questions are from the same article. They're all like based on the same article. And so if I give you the references, you're going to be able to like prepare for the next time that we play this, or I'm going to have to throw away the rest of the questions.

[00:33:45] **Adam:** So let's just try to get through these, a little

[00:33:47] **Ben:** sure, sure, sure, sure. Less tangents.

[00:33:50] **Adam:** Yeah. Yeah.

## [00:33:50] Question 6

[00:33:50] **Adam:** So, this is a little bit more JavaScript specific, right? So you may be familiar with the syntax, import react from quote react quote. Right. That's sort of like. It's Tim's just shaking his head. No, we're already outside of, outside of his specialty.

[00:34:07] **Adam:** So the syntax import react from quote react quote is technically not valid JavaScript or even ESM. It's not even valid ESM ECMAScript modules to be clear.

[00:34:18] **Tim:** That's the question. That seems like a statement.

[00:34:20] **Adam:** That's it.

[00:34:22] **Ben:** So many compilers, when it gets to this kind of stuff, I lose track of what is

[00:34:27] **Adam:** You're, you're on the right track. Yeah. So. Why would a compiler be a useful aspect of that answer?

[00:34:36] **Ben:** I

[00:34:38] **Adam:** to watch you squirm, but I'm not sure it makes great radio.

[00:34:40] **Ben:** the, the, from React won't know how the compiler is the thing that's responsible for resolving what React is.

[00:34:48] **Tim:** actually,

[00:34:49] **Ben:** But, but I, I don't, but I don't know which part of the statement was wrong.

[00:34:58] **Adam:** Poor Ben, you were, you were, you, I would have given it to you,

[00:35:00] **Adam:** but, but then Tim snuck in the, um, actually, So it, it technically, as I read it, right, as it as it was written there, it not, it used to not be valid JavaScript or ESM because the quoted portion, either has to be a relative path or an absolute path.

[00:35:18] **Adam:** And just like the word react is neither of those things, right? If it was a relative path that would begin with like a dot slash or a.dot/, and if it was an absolute path, it would begin with like a forward slash or HDP or, or whatever, right? and so, it was neither of those things, and because of that fact, you would need something like a bundler, TypeScript compiler, whatever, to, to understand the convention of like, Oh, okay, this means it was something that's installed from NPM, and I'll just go look it up there.

[00:35:50] **Ben:** for node modules.

[00:35:51] **Adam:** Right. However, they are adding HTML import maps. and you will be able to define aliases. So you could say react equals and then like link to,

[00:36:02] **Ben:** just, um, actually yourself,

[00:36:07] **Tim:** apparently he did. Uh,

[00:36:09] **Adam:** okay. So what am I doing for points on that one?

[00:36:11] **Ben:** give that to Tim because Tim knew

[00:36:13] **Tim:** I mean, I didn't get it right. He just didn't get it. I don't

[00:36:16] **Adam:** All right. I tell you what, that, yeah,

[00:36:18] **Tim:** I think we're

[00:36:19] **Adam:** was on the right idea, but he didn't have the, I'm actually, so I'm giving you another

[00:36:22] **Ben:** all right. All right.

[00:36:23] **Tim:** Okay. Okay.

[00:36:25] **Tim:** All right. we're tied at two. This is, this is high drama. This is high drama. I love it.

## [00:36:29] Question 7

[00:36:29] **Adam:** alright, you can make an element and all of the DOM elements that it contains ignored completely from an interactivity perspective just by adding the inert attribute to an element.

[00:36:41] **Adam:** No clicks, no focus, the elements are gone from the accessibility tree and nothing can be selected. The only way to interact with the inert elements is that you can use the on page find command. Command to find the text in the inner elements.

[00:36:56] **Ben:** ding, ding, ding.

[00:36:57] **Ben:** ding. Go ahead.

[00:36:58] **Ben:** not even the find works? I'm actually not even the find works.

[00:37:02] **Adam:** Correct.

[00:37:03] **Tim:** yay. Me,

[00:37:05] **Ben:** That was a guess.

[00:37:08] **Adam:** That's it. not even find works. All right, Ben, you just took the lead. It's now three to

[00:37:13] **Ben:** player. Inert is another one of those things that it's like, Oh, I can't wait to use it. But is it safe yet? I don't know.

[00:37:20] **Adam:** Yeah. Yeah. I don't know. I'd have to look it up on can I use.

## [00:37:24] Question 8

[00:37:24] **Adam:** All right. similar to inner, let's talk about the hidden attribute. Hidden attribute is getting an upgrade. You can now set the value of the hidden attribute to until dash found. And then if an on page find, finds text that exists inside of a hidden until found element, all elements that contain the search text will immediately unhide to show the matches. Right, so you can, you can set like hidden on an element and that just makes it hidden, right? It's been kind of crummy, but it, it does work, like it kind of collapses out of the dumb. And now, even if it's hidden, if you run a, like a find on the page, command F, And search for something and it happens to match something that's in your hidden element.

[00:38:07] **Adam:** All of those elements with that, that have that text in it that are hidden will expand.

[00:38:13] **Tim:** me, me.

[00:38:14] **Adam:** Go ahead, Tim.

[00:38:15] **Tim:** Actually, they don't expand. They don't find

[00:38:17] **Adam:** Not the answer that I'm looking for.

[00:38:20] **Tim:** ah,

[00:38:21] **Ben:** That was going to be what I guessed also. I don't know. I've never, I've never used the hidden attribute.

[00:38:30] **Adam:** Okay, so this is true except that there, if there are multiple hidden matches, Only the next match is found when you collect like find next, right? So as you're searching, they will expand when it hits the one that's hidden.

[00:38:45] **Tim:** okay.

[00:38:46] **Adam:** Yeah.

## [00:38:47] Question 9

[00:38:47] **Adam:** All right. There's an opportunity for a bonus point here, which is there's a way to attach an event listener to these elements, to the ones that you're marking hidden, to be notified before they're displayed.

[00:38:59] **Adam:** Like before they're selected from the, the find next, can you tell me what the name of that event is?

[00:39:06] **Tim:** Me, me, me

[00:39:07] **Adam:** Go ahead, Tim.

[00:39:08] **Tim:** on find.

[00:39:11] **Ben:** Ding, ding, ding.

[00:39:12] **Adam:** Yes.

[00:39:13] **Ben:** on visibility change.

[00:39:15] **Adam:** No. So the, the answer, the event that I'm looking for is before match, on before match.

## [00:39:24] Question 9

[00:39:24] **Adam:** All right, last question.

[00:39:26] **Tim:** All right. Ben's winning three to two. Yeah. I got, I can, I can tie you, but I can't beat you.

[00:39:32] **Adam:** all right. Responsive video is catching up to responsive images. With the picture HTML element, you can use a source tag as a child to specify different sources for different situations, such as wider screens. Thanks. The HTML video tag is taking a page out of the picture tags book and allowing you to use the media attribute on source tags to specify when to use that source, such as landscape screen orientation or on smaller screens. This is another really tricky one.

[00:40:03] **Adam:** No guesses? Yeah, I'll read it again just in case. Or go ahead.

[00:40:07] **Ben:** is it ding, ding, ding. I'm actually, is it using a source set instead of a media? Ah, ah,

[00:40:18] **Adam:** that's a good guess. That's not correct. And also not what I'm looking for. I, yeah, I mean, I might've made this one a little too hard. So actually the video tag was the first to have this type of functionality. And it was largely implemented, but for some bizarre reason, it mostly got, like, de implemented.

[00:40:35] **Adam:** They took all this functionality back out, but not before it inspired the people who were implementing the picture tag. And so picture, like, was the first to fully land it, the features, and now it's coming back and video is getting those features.

[00:40:48] **Tim:** Don't call it a comeback. here for years.

[00:40:52] **Adam:** Alright, so I guess that the score at the end of our game is Ben has 3 and Tim has

[00:40:56] **Ben:** Oh, thank goodness.

[00:40:58] **Tim:** Oh, you won Ben,

[00:40:59] **Ben:** goodness.

[00:40:59] **Tim:** as you, as you should have. Can't

[00:41:01] **Ben:** I know. This is like the, Jake Paul, Mike Tyson fight.

[00:41:06] **Tim:** yeah, can't let these management guys beat you down.

[00:41:10] **Adam:** Wait, which,

[00:41:11] **Ben:** I don't know. I don't know which one.

[00:41:12] **Adam:** is the manager?

[00:41:13] **Tim:** I don't know. I don't

[00:41:14] **Ben:** meant like, it felt like it couldn't end well.

[00:41:21] **Adam:** Oh, well, that's a, that's all I got for the game. that was fun. I don't know. Do you guys think you want to play that one again

[00:41:26] **Ben:** Yeah, that was amazing.

[00:41:28] **Tim:** Yeah. I think you need to stop overestimating our intelligence. Seriously, we don't need trick questions. The questions themselves are hard enough.

[00:41:37] **Adam:** That could be true. It's probably going to be dependent on finding a good amount of source material that,

[00:41:45] **Tim:** I don't want to make this episode too much longer, but I will say I read a really good article in Wired the other day about how that, that HTML is actually a programming language, fight me, is just saying how it was one of the most significant computing languages ever developed, and I 100 percent agree with that.

[00:42:01] **Adam:** absolutely. So with CSS, they're declarative programming languages. They're just not.

[00:42:05] **Tim:** I mean, if you were around when HTML first came out, how mind blowing that was, that was ridiculous. Like you're like, it couldn't do a whole lot, but it's like, at the same time, you could just use. Notepad and create stuff that, that was readable and functional and searchable and, you know, even send an email, you know, it didn't have a whole lot of like really cool, you had to use really weird stuff like Perl or CGI back in the day, or later these languages like ASP and ColdFusion came along, but it's like, it was revolutionary.

[00:42:38] **Tim:** It really was. And it's still, it's basically what, at the end of the day, it's like what all these browsers are generating, right?

[00:42:45] **Adam:** It's, it's so good that a lot of native apps on, that run off of the internet, right? So like a native app on your phone, you can write that. A lot of interfaces are written in HTML and CSS. Like Discord, the Discord app is, is HTML and CSS. Yeah,

[00:43:01] **Tim:** So,

[00:43:02] **Ben:** It is crazy. And it's, and it's like mega backwards compatible. I think I've, I've heard that the very first page on the internet could still render properly.

[00:43:11] **Adam:** probably. Yeah. It probably didn't have too much

[00:43:14] **Ben:** Yeah. Yeah. Yeah. But like the parsing is all very forgiving, you know, nothing fails and sort of just falls back.

[00:43:21] **Tim:** opposed to anything running flash, which does not work at

[00:43:25] **Ben:** blue question mark.

[00:43:27] **Tim:** Yeah. Yeah. Big broken page question mark. So yeah, that was fun. Thanks. Thanks Adam. That would, we need to do that more often. Maybe we'll, we'll come up with one and stump you next

[00:43:37] **Adam:** yeah, go for it. I, I would love to come up with a name for the game that somehow references Cunningham's Law. I don't know if listeners have any ideas, you know, send them to us in our Discord or you know what I'll say? I'll even, I'll,

## [00:43:48] BlueSky

[00:43:48] **Adam:** I'll share a little bit of news here. the podcast is now on Blue Sky. So one of the neat things about BlueSky as a social network is that your handle can be, your domain. So if, if you're looking for us on BlueSky, our, our handle is workingcode.

[00:44:07] **Ben:** Nice.

[00:44:08] **Tim:** Yep. I found that out when I was registering mine and I read an article, like, Oh, I have a domain, I'll just use timothycunningham. com. Now that's my domain. That's my handle. That's pretty cool.

[00:44:19] **Adam:** So yeah, you can, if you have an idea for the name, you can hit us up on our discord, you can hit us up on BlueSky. Those are pretty much the only places that I, or I mean, technically email, and I'm, I'm pretty sure it's all in my like unified inbox, I would see it, but, Discord or BlueSky are the places I'm most likely to see it relatively quickly.

[00:44:35] **Adam:** Anyway,

[00:44:35] **Ben:** I only learned, so one of the other podcasts that I enjoy listening to is called Savage Lovecast, and it's, it's by this guy, Dan Savage, I think is his name, and, either Adam Savage or Dan Savage, I can never remember, anyway, it's, it's like a sex and advice, and relationship advice podcast.

[00:44:52] **Ben:** Dan Savage, yeah, yeah,

[00:44:53] **Adam:** Adam

[00:44:54] **Tim:** That is not Adam at all.

[00:44:55] **Ben:** Adam's the

[00:44:56] **Tim:** maybe done it twice in his life.

[00:44:59] **Ben:** Anyway, today is the Feast of the Ass. It's a, old Catholic holiday. So just wishing everybody a happy Feast of the Ass and, he's bringing it

[00:45:09] **Ben:** back.

[00:45:10] **Tim:** Is that top, is that tied to the sex pot? Yeah. What's, what's going on here?

[00:45:15] **Ben:** He's the one, he's like trying to bring it back into pop culture

[00:45:18] **Tim:** Yeah. But as if the, the, do we mean booty or do we mean

[00:45:22] **Ben:** so the feast, so apparently it is, it is the, it's in praise of the donkey that carried the Christ child away from danger. I don't really know the

[00:45:33] **Tim:** To Egypt. Yeah.

[00:45:35] **Ben:** like that. So this is celebration of that, of the donkey, but it's called the Feast of the Ass.

[00:45:39] **Tim:** Yeah, so there's a big difference.

[00:45:44] **Ben:** I'm just saying, it has its own Wikipedia page.

[00:45:50] **Adam:** I'm, I'm so confused. Okay,

## [00:45:53] Patreon

[00:45:53] **Adam:** this episode Work and code is brought to you by the Feast of the Ass. And listeners like you, there's gonna be so many

[00:46:01] **Ben:** I'll put, I'll put in the show notes.

[00:46:04] **Adam:** if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:46:11] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:46:19] Thanks For Listening!

[00:46:19] **Adam:** If you wanna help us out, you can go to patreon.com/workingcodepod, become a patron of the show. Cost you a couple of bucks.

[00:46:26] **Adam:** And in addition to the warm fuzzies that you get from supporting us, you'll also get extended episodes. Every episode we stick around after the mics are off and we just keep chatting about whatever's on our minds. We call it the after show because it has often nothing to do with the main show. It's just, it's just, we just keep blabber blathering on, blabbing.

[00:46:47] **Adam:** I don't know. Whatever. but that's it. Right. So, cool. Come hang out with us. Go to workingcode.dev/discord to join our discord free and open to the public, go to patreon.com/workingcodepod to throw a few dollars our way. We would really appreciate it. You can leave us a review on Apple podcasts or wherever you get your podcast, workingcode.dev/review.and that's going to do it for us this week. We'll catch you next week. And until then,

[00:47:07] **Tim:** Um, actually, your heart and apparently your matters.
