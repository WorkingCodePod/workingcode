---
title: "007: Origin Stories Pt.1"
description: This week, we get personal with two of the crew and learn more about where they came from, what kind of stuff makes them tick, and what it is that they love about being web application developers.
date: 2021-01-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/007-origin-stories-pt-1/id1544142288?i=1000506745250"></iframe>

All super heroes have an origin story. And, **so do nerds**. Many of us can remember back to that moment when we realized that there was magic in the world - magic that we could be part of; and, magic that we could help create. This week, we get personal with the crew and learn more about where they came from, what kind of stuff makes them tick, and what it is that they love about being web application developers.

This Part 1 of a two-part series. Part 1 includes Tim and Ben. Part 2 will include Carol and Adam.

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Triumph:** He moved mountains of data using "pivot tables" in Google Sheets in order to build summaries of his newly-rolled-out test coverage at work! He's a hair's breadth away from fully converting his codebase over to an open-source platform.
- **Ben's Triumph:** He totally built something _without JavaScript_! I know, it sounds crazy: in the age of Single-Page Applications (SPA) and JavaScript frameworks, reaching for JavaScript is the default. But he managed to build something useful with _just HTML and CSS_!
- **Carol's Triumph:** Failure - She just passed the 4-month mark at her new job, like a boss! But, she been a little bit down in the mouth, concerned that she's not getting enough done and that she's not learning enough. She managed to turn the week around, however, getting some productive "Design Buddy" work (think "pair programming" for the planning phase) done.
- **Tim's Triumph:** He checked his old Coinbase account from 2015 and the $15 he left in there is now worth $85. He's about to wine and dine himself!

## Notes & Links

- [:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target) - CSS selector that matches elements whose id matches the URL fragment.
- [Coinbase](https://www.coinbase.com/) - a place to buy, sell, and manage your cryptocurrency portfolio.
- [Lost Passwords Lock Millionaires Out of Their Bitcoin Fortunes](https://www.nytimes.com/2021/01/12/technology/bitcoin-passwords-wallets-fortunes.html) - New York Times article about a millionaire who has two more chances to remember his password for quarter-billion in Bitcoin.
- [Google Sheets: Pivot tables](https://support.google.com/docs/answer/1272900) - creating and using pivot tables in Google Sheets.
- [Aqua Data Studio](https://www.aquafold.com/aquadatastudio) - a versatile database IDE with data management and visual analytics for relational, cloud, and NoSQL databases.
- [ELIZA](https://en.wikipedia.org/wiki/ELIZA) - an early natural language processing computer program.
- [Zork](https://en.wikipedia.org/wiki/Zork) - one of the earliest interactive fiction computer games.
- [Kaypro](https://en.wikipedia.org/wiki/Kaypro) - a computer manufacturer from the 1980s known for their line of rugged, "luggable" computers.
- [dBase](https://en.wikipedia.org/wiki/DBase) - one of the first database management systems for microcomputers.
- [CP/M](https://en.wikipedia.org/wiki/CP/M) - an early operating system.
- [Ultima Online](https://uo.com/) - one of the first MMO (Massively Multi-player Online) games.
- [Adobe ColdFusion](https://www.adobe.com/products/coldfusion-family.html) - a modern web development language.
- [Lucee CFML](https://www.lucee.org/) - the leading open-source CFML application server / engine - it's so good you might just freak out!
- [Sierra Entertainment](https://en.wikipedia.org/wiki/Sierra_Entertainment) - game company famous for King's Quest, Space Quest, and Leisure Suit Larry.
- [Hackers](https://www.imdb.com/title/tt0113243/) - one of the best movies in the computer / hacker genre - Hack the planet!
- [X-Files](https://www.imdb.com/title/tt0106179/) - 1990s tv drama about the FBI's paranormal phenomena research - the truth is out there!
- [QBasic](https://en.wikipedia.org/wiki/QBasic) - an early programming language and interpreter.
- [TI-82](https://en.wikipedia.org/wiki/TI-82) - a programmable calculator.

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/007-origin-stories-pt1.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:17] **Adam:** Okay, here we go. It's show number seven for January 27th, 2021, and today's show we're going to be giving Something a little bit different, our coding origin stories, and we figured since there's four of us, we'll break it up into two parts. Today we're going to do part one with Ben and Tim, and then I guess next week we will do part two with myself, Adam, and Carol.

[00:00:39] **Adam:** And, uh, just Kind of find out what, uh, makes these people tick and who they are. And I guess another reason is that, uh, some of the early feedback that we've gotten from the podcast was that some of our voices are kind of similar. So we thought this might be a good way for people to get to know us a little bit and, uh, and familiarize yourselves with who the person is and who their voice is.

[00:00:59] **Adam:** You guys

[00:01:00] **Carol:** should all just talk deeper. Then you won't sound like me.

[00:01:06] **Adam:** Yeah, Carol.

[00:01:08] **Carol:** See, there you go. Uh, I'm

[00:01:10] **Tim:** K Roll.

[00:01:13] **Adam:** Uh, but before we get to that, let's do our triumphs and fails. Um, Carol, why don't you go first?

[00:01:19] **Carol:** Yeah, so, I feel like I have a, kind of a mixture. Um, I know you, I've mentioned it before. I started a new job, which is now hitting the four month mark. Woo hoo!

[00:01:29] **Adam:** Ooh, four month

[00:01:29] **Carol:** mark.

[00:01:31] **Carol:** Yeah, yeah, yeah, that's a good point in what we do. I think you're kind of getting your, your feet wet and figuring out things. This week, I, um, Kind of, like, took a little depressed moment, I guess. I don't know. I just kind of felt like I'm not getting enough done. Like, am I learning enough? Like, are people, like, wondering what I'm doing?

[00:01:50] **Carol:** And it just kind of was a little bit of a rough patch for me the first three days of this week. But then, um, yesterday got handed some work from two other devs to kind of go, we do design buddies, and have started working with them on, like, a bigger project. And that's totally just kind of, like, flipped my...

[00:02:08] **Carol:** My attitude or like my mentality back around to being super motivated again and not feeling so much like, do I even know what I'm doing anymore? Cause it was, yeah, Monday and Tuesday was, was pretty rough. So then Wednesday turned out good. So, I mean, I guess it's a triumph and failure cause you know, I probably shouldn't have let myself get so freaked out wondering if I'm doing okay.

[00:02:30] **Carol:** And then, you know. I don't know how

[00:02:32] **Adam:** we get. Can you very briefly talk a little bit about Design Buddies? Is that something akin to pair programming?

[00:02:41] **Carol:** Yeah, it's pretty much the same thing. But whenever you start an effort, we get with someone and just go, Hey, this is what we're thinking about doing. You know, here's the architect that we're looking at designing.

[00:02:50] **Carol:** Here's how we're thinking about implementing it. You know, here's what we're looking at. You know, what's going to be touching. This is what we want to do. So there's three of us working on this big project. Um, it's. Pretty, pretty detailed. Um, and, you know, we just work together on it now. So, as we go forward, we'll release it in smaller chunks rather than all of it all

[00:03:09] **Adam:** at once.

[00:03:10] **Adam:** Cool. So, it's like pair

[00:03:11] **Carol:** planning. Yeah. Pre and then we code it together too, so. Okay. Cool. But not, you don't always code it together. Like, sometimes you just do the design side.

[00:03:20] **Adam:** Nice. Yeah. How about you,

[00:03:22] **Ben:** Ben? Uh, my big triumph this week is that I made something without using JavaScript. What? How? It does not compute.

[00:03:32] **Ben:** Yeah, my, my default instinct is to spin up some sort of an AngularJS or Angular style application. And, uh, I have this little graph that I wanted to make, kind of, uh, Bar chart, like, uh, a rotated bar chart. And, uh, I thought, oh, I'll do the

[00:03:50] **Adam:** calculations. I believe that's also called a bar chart.

[00:03:56] **Ben:** So I thought, you know, my, my initial thought was, I'll just dump the data into an Angular application and I'll do all the calculations and layout in Angular. And, um I was about to do that, and then I discovered the CSS selector colon target, which I had never heard of before, and apparently it's a really, really old, uh, CSS selector that will match the URL fragment.

[00:04:20] **Ben:** to an ID in the document. So you can basically say when this element matches the, the hash code and the URL, you can apply styling. And, uh, I ended up using that to hide and show things based on clicks within the document. And, uh, and so basically I pushed all of the... The number calculation into the server side, the ColdFusion code, and then it just dumps out, uh, you know, a huge HTML and CSS file and it's interactive, you know, very limited interactivity.

[00:04:49] **Ben:** But, um, it was just really nice to be able to, to kind of go back to the basics a little bit and build something without a lot of the, uh, the overhead that might come from, uh, from, uh. JS framework.

[00:05:03] **Adam:** It took me a minute to figure out what you were talking about there, but it sounds like, so you're talking about like a URL fragment, like hash.

[00:05:09] **Adam:** ID or whatever on the end of the URL, and then based on that, you hide or show part of the page using CSS. Yeah,

[00:05:16] **Ben:** and so basically you can do things like have a bunch of divs, for example, and they're all display none by default. And then as the URL fragment changes, you can say, well, this div that matches that URL fragment.

[00:05:28] **Ben:** ID, now I can show this div. So you can, you can create kind of rudimentary, uh, tabbed interfaces and hide and show things based on just the state of the URL and CSS, which is, I didn't even know that was a thing until like literally three days ago.

[00:05:43] **Tim:** Awesome. Yeah. I didn't

[00:05:45] **Adam:** know that either.

[00:05:46] **Tim:** CSS is like black magic to me.

[00:05:48] **Tim:** I don't know why I have that block.

[00:05:50] **Ben:** It's got some crazy stuff in it.

[00:05:52] **Carol:** It's the thing I hate the most.

[00:05:55] **Adam:** Yeah, I do okay with it for the basic design stuff, but then you see these people that are doing like SVG with a whole bunch of CSS and like animation stuff and like making this ridiculous 3D animated art with CSS only and I'm like, yeah, that stuff is crazy.

[00:06:12] **Adam:** No, I'll just, I'll stick to my colored boxes over here. Yeah, I know.

[00:06:17] **Tim:** I can't do it with a bootstrap. I don't know how to do it. Right. It needs

[00:06:20] **Carol:** to come ready for me.

[00:06:23] **Adam:** Okay, Tim, you got a triumph or a fail this week?

[00:06:27] **Tim:** Well, I mean, my triumph's small. Work related right now, we're, we're very deep in doing performance reviews for the entire company.

[00:06:34] **Tim:** So that's taken up a huge amount of my time being reviewed and reviewing others, uh, and then doing, you know, goals for 2021, setting everyone's scorecards for. For the next, for this come, this year. So, but my real triumph is, you know, we were talking about, uh, our goals for 2021. I talked about how I, I want to understand the technology of Bitcoin, uh, and blockchain, although I don't fully, you know, buy into it as a legitimate currency, even though, you know, people are making money off of it.

[00:07:06] **Tim:** And I remembered years ago, I had sold off a fair amount of Bitcoin. Probably way too early. I could be retired by now based off off some of that . I, I used to have hindsight, right? But I'm like, oh, I have an old Coinbase account. I wonder what happened to that. So I logged into it in 2015 when I sold everything.

[00:07:26] **Tim:** I just left $15 in there and now it's like $85. So yeah, I might, you know, buy a nice bottle of wine. Nice. Have a steak dinner or something. Did you,

[00:07:37] **Carol:** did you see the article about the guy who has like two more attempts left to access his account? Yeah,

[00:07:43] **Adam:** I saw

[00:07:44] **Tim:** that article and I, that's actually what prompted me to go log into my account.

[00:07:48] **Tim:** Because I'm like, man, I wonder if I can still remember my login and I have my password vault, so. That's why I have a

[00:07:54] **Carol:** password vault too, yeah. I was like, dumb guy.

[00:07:57] **Adam:** Do the,

[00:07:57] **Ben:** do the accounts like self destruct or something? I don't know anything about Bitcoin.

[00:08:01] **Carol:** I don't really know what happens. I just know he basically has two attempts left to get his password right.

[00:08:07] **Carol:** And there's some crazy dollar amount in his account with Bitcoin.

[00:08:14] **Adam:** Oh my goodness. I mean, it's cryptograph, cryptographically secure. There is no recovering it. If you don't have the password, then you don't have the password and your money is gone. Nobody else in the economy can get it either.

[00:08:26] **Tim:** And they tend to like, generate the password.

[00:08:28] **Tim:** It's like, it's a bunch of words. So it's like a bunch of random words. So it's like a sentence, you know, 20 words long. And just some random words put together. So it's like... If you, yeah, there's no way you're going to memorize it.

[00:08:40] **Carol:** I don't know how people don't have password vaults.

[00:08:43] **Adam:** Right?

[00:08:44] **Tim:** Yeah. It's ridiculous.

[00:08:45] **Tim:** I don't know any of

[00:08:46] **Ben:** my

[00:08:46] **Carol:** passwords. I don't even know my usernames. I generate usernames too, randomly. Like, I click the password and I put that in my username.

[00:08:55] **Adam:** Yeah, it's probably good for

[00:08:58] **Carol:** privacy. I'm like, well, if you hack one account, you're never going to get into the rest of them because it's not the same username.

[00:09:04] **Carol:** There you go. What about you, Adam?

[00:09:06] **Adam:** What you got? Um, you know, not a big thing, but I'm going to call it a triumph. So we've talked a couple of times now about my company's effort to port our application server from one language to another similar, but this time open source language. And Uh, previously I'd done a bunch of work to get data that the closest thing I can compare it to is test coverage.

[00:09:29] **Adam:** It's not exactly test coverage, but it's, it resembles that. And so now we're at the stage of this process where we're trying to have everything deployed by the end of January, so between when this podcast comes out and when the next episode comes out. Um. And, uh, they are currently deployed to QA. All of our QA servers are on the new platform.

[00:09:53] **Adam:** But, you know, that getting customers to test something on QA is like pulling teeth. It's just not going to happen. So, um, in an attempt to try to, uh, get... Some reasonably good coverage of our tests, what we're going to do is rerun the whole testing process in QA with the whole team this time instead of just a couple of us, and in order to, um, track that data in sort of real time, um, I figured out that Google Sheets now has pivot tables, so I can, uh, load all that data into a sheet and update it, uh, pretty rapidly, and then the, the pivot table shows us summary information about it.

[00:10:35] **Adam:** How different sections of the app are, uh, being tested, what has been tested and what hasn't, and where the errors are. So, um, it was just a fun little find today and, and, uh, it's going to make tomorrow afternoon a lot of fun.

[00:10:50] **Ben:** And what's a, what's a pivot table? I'm vaguely familiar with the term. So,

[00:10:55] **Adam:** um, I'm trying to think of the best way to explain it.

[00:10:58] **Adam:** It's, if you can think of like... It has to do with

[00:11:02] **Ben:** like rotating the table, right? Yeah, kind

[00:11:04] **Adam:** of. Yeah. So in my case, I've got a bunch of columns. So like, uh, my application is broken down into, so I call it separate apps. We've got a column for app where you've got like admin interface, our API and our public interface.

[00:11:19] **Adam:** And then within each of those, there's sections. And then within each section, there's like items. Those are the individual actions you can run. And then next to each of those, I show like a success count and error count and um, what the pivot table does is you, it lets you select, okay, I want to, I want to break down the data, like have roll ups at the app level, the module level, and the section level, and then the, the data that I want you to roll up is the, um, SuccessCount and ErrorCount, and it'll give me like percentages for those and all kinds of stuff.

[00:11:53] **Adam:** There's, I mean, pivot tables are incredibly, it's possible to do incredibly complex stuff with them, and I, I know just enough to get myself in trouble. Yeah. But, uh. Gotcha. When, when it works well, that's very handy. I spent like an hour trying to do just spreadsheet formulas to, to get the data out that I wanted to get, make it easy to see as we're testing.

[00:12:15] **Adam:** And about an hour into it, I went, you know, I bet a pivot table would do well for this. And I just like quick Google, Google Sheets, pivot table. And it's like, it's right there. They built it in. So.

[00:12:26] **Carol:** I used to use a program called Aquadata for all of MySQL, um, querying and stuff, and they actually, I love Aquadata.

[00:12:34] **Carol:** It's expensive. Sorry. It's expensive, but I love it. But what you could do in there is once your query runs, you basically could just right click and say, you know, open the pivot. Um, like the pivot window or whatever, I think it was pivot generator. I don't remember what it's called exactly. It doesn't matter.

[00:12:50] **Carol:** Um, but you would go in there and you basically drag and drop at that point. So you take your columns and you start moving it to where you want it to be. And then you just right click on it and say generate SQL. And it would generate the SQL for you in another window. So you could just rerun that continuously and it would give you the output.

[00:13:08] **Carol:** It was pretty awesome when you're doing big data.

[00:13:12] **Tim:** Yeah.

[00:13:14] **Adam:** Cool. All right. Well, I guess let's move on to our main topic for the day. We're gonna talk about origin stories. And, um, I don't know, what do we want to say to, to introduce this? In

[00:13:25] **Carol:** the beginning.

[00:13:29] **Tim:** Everyone has an origin story. Everyone starts somewhere.

[00:13:33] **Tim:** You either

[00:13:34] **Adam:** die a hero or you live long enough

[00:13:36] **Tim:** to become the villain. Still working on my villain. Tim is the

[00:13:41] **Adam:** villain. I

[00:13:43] **Tim:** have. I've lived long enough.

[00:13:44] **Carol:** He's requesting haters daily. That's

[00:13:47] **Tim:** right. Need more haters.

[00:13:50] **Adam:** So, yeah, I guess the general approach here is, how did you become the tech person that you are today, Tim?

[00:13:59] **Adam:** What are the signposts, the milestones, the things that put you where you are, technologically speaking? today.

[00:14:09] **Tim:** Yeah. So I can remember the very first time I ever saw a computer. I remember it clearly. So it's 1982. I'm a, a, a dorky tween and, uh, I'm visiting one of my best friends, Stephen Schibetta. Uh, I, I thought they were rich, uh, because they had a pool.

[00:14:30] **Tim:** Uh, looking back now, they were just kind of lower middle class, but they had a pool and, uh, his dad was always like a tinkerer. Um, He ran a concrete company, but he had like, he uh, was always into tech and gadgets and like always at Radio Shack and they bought a TRS 80. Does anyone remember the TRS 80? I remember the name.

[00:14:52] **Tim:** Yeah, so RadioShack carried a computer, uh, which was a green phosphor screen, uh, with floppies. Later they had hard drives, but it was like an early, early computer. It cost 399 at RadioShack. Which

[00:15:07] **Adam:** at the time was like a million

[00:15:08] **Tim:** dollars. Well, I mean, today's money is about 2, 500. So, yeah. And, uh, you know, it wasn't very powerful.

[00:15:16] **Tim:** It didn't have a lot of programs. There wasn't a lot to support it, but I was, I was visiting my buddy. We were swimming and then he's like, Hey, you want to see our computer? I'm like, yeah, let's check us out. Cause I'd never seen a computer before. And, um, so we go downstairs in his basement and he boots it up.

[00:15:31] **Tim:** And after several minutes of boot up and some typing and he puts in, uh, the program Eliza. Never heard of it. Eliza. So Eliza was, um, it's an early kind of an AI prototype, but it's really just you would type something and it would pretend to talk to you, but all it would really do is kind of parrot back things to you.

[00:15:54] **Tim:** It would try to learn some phrases and stuff. You'd say, Hi, Eliza. How are you? I'm fine. What is your name? And you'd put Tim and say, Okay, Tim. And, you know, it would just take the input that you gave it and build off of that input and I just thought, wow, that is, this is amazing. This is like, you know, uh, The original Siri.

[00:16:14] **Tim:** This is like, yeah, the original Siri. Eliza. Yeah, that was called Eliza. And then he's like, oh, then you want to play a game? So he popped in Zork and we loaded up Zork. Does anybody remember Zork? I've

[00:16:23] **Adam:** heard of it. Yeah, I heard the name. So

[00:16:25] **Tim:** Zork was a text only adventure from a company called Infocom, and so it starts out, you are at a, uh, you're at the end of a road and there's a mailbox in front of a house, and that's all you get is a sentence.

[00:16:40] **Tim:** And so you type, open mailbox, and it would have a bit of text to say, inside the mailbox is a letter. Get Letter. And so this entire game, and you would kind of, it was kind of like a, um, uh, sort of like a, a mud or a dungeon. And so you, you, like, there's wizards in it and you fight dragons, but it's all text based.

[00:16:59] **Tim:** Zero graphics. And you have to, like, Draw on piece of paper, all the, and I thought, oh my God, this is the most amazing thing ever. And so I went out and bought a, a, a micro cornucopia magazine. So this is not internet days. You can't go online and look stuff up, you know, you, you, I found 'em. Magazine called micro cornucopia.

[00:17:21] **Tim:** It was all about computers and some of it was about building electronics and stuff But it had programs and basic and stuff Um, so I would like get these magazines and I would just read basic code like all day long I didn't have a computer to try it on, but I would just read BASIC all day long. And I would, I would memorize all these BASIC programs.

[00:17:43] **Tim:** I would just watch and see, figure out how they work. And I couldn't run them until I would go swimming again. So we, you know, maybe once a week, we, on Wednesdays, we'd go over to Stephen's house and I'd swim as fast as I could. I'm like, can I use your computer? It's a good upstairs. And then for the next hour, hour and a half, I'm typing in by hand, all the BASIC code, running these.

[00:18:02] **Tim:** Little programs that would do something stupid, you know, like kind of like a fake asteroids game or something and I was hooked. I was hooked. You know, I, I was going to be a hacker. I was going to be, I was going to be war games, uh, Matthew Broderick hacking the Pentagon, you know, playing the game of war.

[00:18:23] **Tim:** That was, that was, I was totally going to be him. That's the only thing I wanted to do. And so, uh, get a little older, come to middle school. That's And our middle school, uh, we're just getting computers. So computers were not really a thing in school. And I lived, uh, I lived, uh, from Georgia, um, from a rural, very small, we had like maybe a hundred kids in our graduating class.

[00:18:46] **Tim:** So it was very small rural school, but they were just getting some Apple 2s and Apple 2Es in. And no one knew anything about them. Teachers didn't know how to use them. They didn't give me any instruction. And I was all about, so I'm in the library every day, setting up the computers, installing stuff on it.

[00:19:04] **Tim:** Um, and I sort of became the middle school and high school's tech guy. I was anything that needed to be done. I spent more time in the library than I did pretty much in any class because it's working on the

[00:19:18] **Adam:** computers and

[00:19:19] **Tim:** stuff. Yeah, because I would be sitting in, like, the middle of, you know, math or English and we'd hear, Can I borrow Tim for a second?

[00:19:30] **Tim:** It's another teacher. The teacher's like, I need Tim. And like, like, what do you need? He said, well, they have a problem with the computers. So they pulled me out of class and I would spend the rest of the day. You know, working on the computers for them. So I became the school's tech guy. And, uh, and again, I didn't have one at home.

[00:19:46] **Tim:** We, we didn't have enough money. We were, we were pretty modest in, in our income. My dad, you know, did, did manual labor jobs until later he started his own business. But yeah, we didn't, so we didn't have an Apple at home, but had one in middle school. So I was like always like. Getting Nibble Magazine, no, nibble was like a early Apple magazine and it would have, uh, tons of basic programming.

[00:20:09] **Tim:** Some of it was like assembly language. 'cause it would, they would try to do things that the machine, so yeah. I mean, typing in hex code, hex decimal in order to feed into an assembly language compiler on an apple. Yeah, that's, that's pretty hardcore, uh, particularly trying to debug that. But I mean, that's what I was doing like every day.

[00:20:28] **Tim:** That's all I wanted to do. Uh, and then my, so my dad, he had started a business. Um, we, my, my, my family, he manufactured car cleaning products. So he was a bit of a chemist and he would make car soap and car wax. And, you know, we had trucks all over the Southeast and would sell. And so. I officially was the warehouse guy.

[00:20:52] **Tim:** That was my teenage years job was I was the warehouse manager and I would move boxes and carry stuff around and move chemicals, uh, but we had a K Pro2. So K Pro. I don't know what that is. K Pro is, I'll put a link into it. K Pro was like considered the world's first portable computer, but they actually called it a Luggable.

[00:21:13] **Tim:** The thing was, yeah, the thing was the size of a suitcase. It had a metal case. And the, uh, keyboard would, would collapse into the, the, the, the top of the case and it would clip and it had a handle on the back of the keyboard. And so you could carry it around, but it weighed about 60, 70 pounds. Wow. Oh my goodness.

[00:21:32] **Tim:** And again, green phosphor screen, no color. And, uh, and my dad had that to like, you know, track payroll and, um, Uh, a friend of mine, he, he was a bit of a programmer and he wrote a program in Dbase2, which was an early kind of database kind of language. And so you had all these kind of text screens with Xs and stuff.

[00:21:54] **Tim:** So he wrote that and then he printed out all the code onto, you know, dot matrix printer, green bar, uh, sheet, and printed out all the code. And so. You know, he wasn't going to maintain it, so anytime we needed something, I would pull out that sheet and read all the code, and then if my dad needed new features, I'd add it, and so that was really my first.

[00:22:16] **Tim:** It wasn't, I wasn't getting paid for that. It was sort of like, that was my fun time. I was getting paid to carry boxes, but that's what I did. I would add, so, you know, Dbase2 on a CPM machine. This is not even a DOS machine, not even Windows. This is CPM, an early, um, uh, Um, that I just, I just loved it. So I just sit there and code all day long.

[00:22:39] **Tim:** All night long. I never went anywhere. I had no social life. I stayed home every weekend, this nerd sounds awesome. Yeah.

[00:22:50] **Carol:** Is it bad? Like, I want to go do this. Like, I never did any of that, so I'm just like, this sounds so interesting to

[00:22:57] **Tim:** me. It's nostalgia for me, but it's like I was w when we were. You know, talking about this, I was like Googling some, some links so I could put in the show notes for what these things are so people can visualize it.

[00:23:08] **Tim:** But I found like on eBay, like 200, I can buy an old Kaypro machine. I seriously, seriously want to buy it just for the, the nostalgia factor of it. Um, and, and then, so again, this is pre internet, but there was a thing called a BBS. Anybody remember, you know, that bulletin board?

[00:23:32] **Adam:** Yeah, I'm a little familiar with them.

[00:23:33] **Adam:** I wasn't a heavy user, but I'm, yeah,

[00:23:35] **Tim:** I'm aware. So, back before the internet, you know, you had a modem that actually hooked up to your phone line, and it was a bot, it would make audible, you know, noises, and that's how it would talk to other computers. But, um, you'd have people that would dedicate a phone line.

[00:23:54] **Tim:** And you have a bulletin board system, so you could call in to someone's computer, so there was a magazine called Computer Shopper, and Computer Shopper was, you know, super thick, probably like six, seven hundred pages. It was a super thick magazine, and like the last quarter of the magazine was just all phone numbers.

[00:24:15] **Tim:** So, state, and of course, this is, you know, everything was long distance outside of our area code of 404. So you tried to find... Oh, sweet area code. Yeah. You tried to try a 404. Uh, well, this is before, you know, the internet. So 404 meant nothing. Right. In fact, I didn't put the two and two together. You just said so.

[00:24:34] **Tim:** Yeah. That's, that's the, that's the greater Atlanta area is the 404. So I'd find a 404 area code and, and call, and of course, most of the time it was busy. And so you would just...

[00:24:56] **Tim:** ASCII kind of graphics, different color text. And, uh, and you could like play games on it. You could like, it wasn't really email, but you could leave messages. And so, uh, my dad's business was growing. And so we had like six phone lines at the, at the business. So. After work, I would always like leave the computer running and then hook it up to one of the phone lines.

[00:25:24] **Tim:** And so I was running my own wildcat BBS, which I thought, wow, I'm so interconnected. I could talk to one person at a time. Uh, yeah, so I'll put a YouTube video of like running a BBS as a video of a guy who's gone back and like rebuilt that.

[00:25:50] **Ben:** It's funny to think about a time when people considered, uh, the cost of phone calls. Yeah. Like, I remember dialing into AOL and having to pay phone bills. And now I'm like, I've never even considered the cost of a, of a phone call in the last like, 10 years. I don't even know if calling international costs more than calling continental.

[00:26:11] **Ben:** Like, those concepts don't mean anything

[00:26:13] **Tim:** anymore. Right. Or, or just the idea of, of, of not being connected online, right? Yeah. Yeah. Yeah. So, and then, so after I graduated, I went, went to school. I moved to New York City and, New York City. To Brooklyn and didn't. Didn't really get to do much programming there.

[00:26:33] **Tim:** I was kind of busy struggling and surviving, but I did as a side, kind of, you know, put together some PCs with, you know, 386, 486 processors, cutting edge stuff and, uh, hooking those up. And then after I left, left school and moved back home, I don't know, in my twenties, I kind of thought I was too cool to code, you know, I wanted to be an artist, I wanted to be a musician, an actor, I wanted to, you know, do something cool.

[00:27:00] **Tim:** Now that worked. I never,

[00:27:03] **Carol:** You're like, I need to pay the

[00:27:04] **Adam:** bills

[00:27:04] **Tim:** now. Yeah. Well, I was single and my, my parents business was doing extremely well and my, my, my dad actually kind of wanted to retire. So, um, I wound up mostly running that business for him. And so I was too busy doing that to really do anything much coding wise.

[00:27:22] **Tim:** But, uh, after I got married, Uh, in 1999, um, you know, my dad decided to sell the business. So he sold it and then, you know, cause it's a family business, he split the, you know, the, the proceeds with, with me and my sister and the people that bought it kind of kept me on one day a week to just kind of help just be there cause my dad was leaving.

[00:27:48] **Tim:** So I was sort of, you know. Uh, consulting with them. And so I was working one day a week making actually pretty good money for, you know, a a newly married, uh, you know, guy in his twenties. And, uh, so I, I just was like, just wasting all my time. , you know, of course you're newly married. We, we spend a lot of fun days together, doing fun stuff that married people do , but, uh, reading

[00:28:13] **Adam:** books and Yes.

[00:28:14] **Adam:** And playing the piano. Yes. Writing poetry to each other.

[00:28:17] **Tim:** Arm wrestling.

[00:28:20] **Tim:** And, uh, but we started playing this game called, uh, Ultima Online. Ultima Online was like one of the first, uh, MMOs massive. I played it, you know, massively on online game R P G, and I was just hooked on this game. And, but I, I wanted to know how it worked because, you know, coming from A B P S where everything can only talk one-to-one, the idea of these thousands of people all playing the same game at the same time was just, Fascinating to me.

[00:28:50] **Tim:** So there were people had written this emulator software where you could host your own server. And so I started building this myself and then that had a scripting language. I don't know if what it'd be like. It wasn't, it was a kind of a bit like JavaScript or VB script called Sphere Server. And so It's just started coding that and making stuff in building my own version of Ultima Online with some other folks.

[00:29:18] **Tim:** And we, you know, we had probably two, three hundred people would play on our server. I was like, wow, this is really cool. Um, so that kind of got me back into coding. And then, but the biggest thing that got me back into coding was I, I would start taking some classes. I didn't take, I wasn't a computer science major.

[00:29:34] **Tim:** I, I'm, mine was business and language arts. Um, but we found out we were having a kid. Yep. Changes everything, doesn't it? Changes everything. So it's like, I realized, alright, we're about, we're gonna have a kid and I'm, I'm kind of, you know, this You know, car wash, soap making business is not something I like and my dad's getting rid of it.

[00:29:59] **Tim:** And I don't really want to do that. I realized that, you know, when you have a kid that kind of settles you down, whatever you're doing at that point in your life, it's kind of like what you're going to be doing for a good little while. Um, so I said, I really, really want to be a programmer. And so I was like, looking, I was like, seriously, like meditating and praying and just like, I got to find what I, what I wanted was I wanted to find a company that was local to where we were.

[00:30:25] **Tim:** Uh, I wanted to find a company that was a startup and I wanted to find a company that would eventually, um, kind of like go i p o and or sell and, you know, and kind of get out of it. And so I, I found an ad for ColdFusion. I didn't know ColdFusion. I knew a S p, I knew Pearl. Um, I knew basic, um, ASP classic, not.net.

[00:30:50] **Tim:** Um, And a few other languages, but I didn't know much about ColdFusion. So I started like checking it out. I was like, Oh, that's, that's pretty cool. And they were looking for a ColdFusion programmer. So I went and interviewed and I didn't get the job. And I was like, I did get the job. I was just bummed. And it's like, because it was everything I wanted.

[00:31:12] **Tim:** I talked to the owner and he's like, yeah, we're, you know, we're just starting out, but we're planning on getting bigger. You know, we're going to go IPO or sell or whatever. I'm like, this is exactly what I want. You know, there's stock options and stuff like that. I'm like, okay. So, I, I kept contacting them.

[00:31:26] **Tim:** So, after they rejected me, I went to the owner. I went above the guy who interviewed me. It was JJ, by the way. I was like, who, who? It was JJ. And, uh, he, he hired, uh, he hired instead of me. I think it was David Clymer. Oh, that was

[00:31:41] **Adam:** a good hire. Yeah, it was a good hire. When you

[00:31:43] **Tim:** said JJ, was that JJ Allaire? No, no.

[00:31:45] **Tim:** I wish all I know. So just

[00:31:49] **Adam:** somebody,

[00:31:49] **Tim:** a random guy. Somebody that Carol would know. Yeah, Carol would know. Nobody else, nobody else will know. And so I talked to the owner of the company and I said, I said, listen, I'm working one day a week and all I do is code on the other days. I said, I didn't tell him about the arm wrestling with the wife, but I said...

[00:32:07] **Tim:** poetry. I was like, this is what I want to do. I will, I will come, I will work for free. I said, I work four days a week for you for free. Just let me come into the office. Let me learn what you guys are doing. And I, you know, he's like, you know, he's like, well, he says, I like what you, you know, I like what you're saying, but I have to pay you.

[00:32:25] **Tim:** I'm like, why? He's like, well, cause I don't pay you anything that there's nothing for you to lose if you leave. I'm like, okay. So I was basically a paid intern, you know, working for minimum wage. Um, And that's kind of how I got my start. I mean, I've really been at that company ever since 2013, we got bought by, uh, Constellation Software, which is like the third, uh, largest software company in Canada and, uh, got a bit of a payout for that.

[00:32:52] **Tim:** Yeah, I've been coding ever since and just it's the only thing I've really ever wanted to do.

[00:32:58] **Adam:** So it sounded like when you had a kid and you were settling down, you headed straight for the web. You, did you ever have a period where you were coding for desktop

[00:33:10] **Tim:** software? No. Okay. No, just the web. I mean, I had read an article when I was a teenager about hypertext, which I thought was the most revolutionary idea ever.

[00:33:24] **Adam:** You have to wear sunglasses while you're coding it.

[00:33:26] **Tim:** Yeah, hypertext. I was like, this is amazing. We can have a semantic web of ideas and everything, you know, all be linked together. And I was like, that just blew my mind. So yeah, I'm like, the web is where it's at. You have to

[00:33:39] **Adam:** wear your denim jacket. That's right.

[00:33:42] **Adam:** And your extremely gelled hair.

[00:33:43] **Tim:** Oh, mine still is, but.

[00:33:46] **Adam:** Well, it doesn't wash out when you put that much

[00:33:49] **Ben:** in it. Did you ever, uh, play any of the, um, Sierra games? King's Quest, Leisure Square Larry, Space Quest, I think. Yep. All of them. When you were talking about the text based Zork, and talking about like, there's a mailbox, open the mailbox, you have mail.

[00:34:07] **Ben:** It was very much those kind of games where it was visual, but you had to tell the character to do everything. So you were like, place a bet at the blackjack table, then ask you how much, then you tell it how much, and you want to say like, pick up that bottle, it says you're not close enough, so then you have to walk over and you have to pick up the bottles.

[00:34:23] **Ben:** That's like some of my earliest memories of playing, uh, on the computer is, uh, King's Quest.

[00:34:29] **Tim:** I think gaming is what gets a lot of people into computers. It's sort of the, uh, the gateway drug. And then you wind up, you know, doing insurance software. That's really boring.

[00:34:39] **Carol:** So you can play games

[00:34:41] **Adam:** in your free time.

[00:34:41] **Adam:** But then

[00:34:42] **Tim:** you come home and you don't want to see a computer ever again. You just like, if I see one more computer, I am so, I just want to go blacksmithing. Yep.

[00:34:53] **Adam:** Yeah, this is the thing that I'm enjoying the most about this is like, I know you guys, I've known you guys for years, but. We didn't have an excuse to have this conversation.

[00:35:01] **Adam:** I'm loving this. Like, get to find out a little bit more about who you are. Can't wait to hear Ben's. Yeah, for sure. Like, uh, when he tells a story about the time he spent in the circus, I'm really looking forward to that.

[00:35:13] **Tim:** He was, he was a Cirque du Soleil strong man.

[00:35:17] **Ben:** Well, when Tim was talking about hooking computers up with modems, I was thinking about, uh, The movie Hackers, and there's a scene in Hackers where they're over at, uh, the woman's house, and someone's like, whoa, what is that, a 36 6 bog modem?

[00:35:33] **Tim:** Risk

[00:35:34] **Adam:** architecture can change everything.

[00:35:36] **Ben:** Risk is good.

[00:35:39] **Carol:** I have seen that one.

[00:35:41] **Ben:** Yay. That movie's so good. So good. It's my favorite of all the hacker programmer genre movies, by far.

[00:35:51] **Tim:** I'm overdue for a rewatch. I got to meet, I got to meet the guy, uh, one of the hobbies that we picked up and abandoned. We were into robot battles, um, every year at DragonCon, they have, uh, where people build little fighting robots and kind of like the TV show.

[00:36:06] **Tim:** In fact, actually, yeah, in fact, actually several people from that are now on that TV show. But, uh, there's a guy, his name is, I forget his last name, his first name is Dale. That's all I know, but he makes some really cool robots, but he was the inventor of the Hayes Modem Protocol. So, Hayes Modem was like the original, you know, Baud Modem, uh, connection, and he wrote that whole protocol.

[00:36:31] **Tim:** So, uh, I got to meet him up.

[00:36:33] **Adam:** So I, I mean, I know they sped up over the years, but is that still the iconic connecting sound? Yes. Yeah. Okay.

[00:36:40] **Tim:** Yeah.

[00:36:45] **Tim:** You know, sometimes if your computer was like, your connection was slow, you would actually pick up the phone and listen to see if, you know, if there was still like beeps going on and then hang it up and you know, they hope it didn't drop your connection. Yep.

[00:36:58] **Ben:** There are going to be people listening to this that literally have no idea what you're

[00:37:01] **Tim:** talking about.

[00:37:01] **Tim:** I know. That's what's right. That's just, what's amazing to me. Like Carol's, this is right, right over her head.

[00:37:07] **Carol:** A lot of it is. Like you were mentioning ears and I was like.

[00:37:11] **Tim:** You weren't born yet.

[00:37:13] **Adam:** Not there for that one. The other night at the dinner table, I was explaining modems to my children, like how it made a noise and, and the, like the original modems, you took the handset off of the phone and you put it on a little device that's plugged into your computer and it had a speaker that would sit next to the mouthpiece of the phone and a microphone that would sit next to the earpiece and it would talk over the phone to other computers using like beeps and, and noises and they just blew their little minds.

[00:37:40] **Carol:** Yeah, I was listening to the radio the other morning and they were doing like this millennial challenge thing. And the question that nobody could answer is what was a dial tone?

[00:37:52] **Adam:** I was like, seriously, a dial tone? So you told me

[00:37:55] **Tim:** the

[00:37:59] **Tim:** millennial thing, um, they were asking like young people, millennials and younger, about the save icon. The save icon is a floppy disk, right? But most of them have never actually ever seen or used a floppy disk. So they ask, well, what is that? Why is it like that? Why does it look that way? They're like, it's just, it's just a wave.

[00:38:22] **Tim:** Yeah. But what is it though? What is it a picture of?

[00:38:25] **Adam:** It's a gray square. What would you like for it to be?

[00:38:27] **Tim:** I don't know. It's like a little door. I don't know what that a door? I don't know That's

[00:38:32] **Ben:** like I saw, I'm sure this was a meme, but someone had a photo of a floppy disk and the caption was like, my kid asked me if I 3D printed the save button.

[00:38:42] **Ben:** Nice.

[00:38:47] **Adam:** I'm going to have to do that. I'm going to have to like 3D print a floppy disk and give it to them as a save button. Okay, well, it sounds like a good time to move on. So Ben, why you is who you is.

[00:38:59] **Ben:** So, uh, as a kid, I didn't really play around with, uh, computers very early on. I was never one of those kids that took apart electronics and built electronics or got computer magazines.

[00:39:12] **Ben:** Um, I used a computer, we had a computer in our garage, which I used to play King's Quest quite often. Uh, I think I had some sort of flight simulator also. King's Quest was awesome. King's Quest was so good. So good. It was, and I tell you, like, I really enjoyed it more in the early days when it was much lower fidelity.

[00:39:33] **Ben:** And then as the versions of King's Quest came out, they become much more higher fidelity and like point to move things around. And I think it lost a lot of its charm. But

[00:39:41] **Tim:** that charm was in the story, right?

[00:39:42] **Ben:** It was, it was, it was just a good time. But so, I mean, that was really my exposure to computers was just as, as entertainment.

[00:39:49] **Ben:** Uh, I didn't really think about. Wanting to use them as any kind of a career path. Um, I actually wanted to be in the FBI for a long time, uh, primarily because I watched the X Files. I can see that, I can see you going FBI. Oh, it was so, me, this is like how nerdy it was. Me and, uh, my best friend, Luke, we would sit in our respective homes.

[00:40:16] **Ben:** I think we were just like having each other there watching the X Files, enjoying it. And, uh, I, I was, you could hear each other gasp. So, you know, the FBI was definitely the path that I wanted to be on for, for a while. And then, um, and

[00:40:30] **Tim:** that's, oh my God, Luke. It's a smoking man episode.

[00:40:35] **Ben:** What does he want? It wasn't in the stars.

[00:40:37] **Ben:** Apparently you need to be, I think they mostly accept lawyers and other very well educated people. I

[00:40:44] **Adam:** imagine it depends on what you want to do in the FBI. I

[00:40:46] **Ben:** suppose so. But anyway, I, um, I slowly started to get interested in, in the web itself, you know, first as just a consumer, but then more just, uh, curiosity.

[00:40:57] **Ben:** And um, I started to poke around on some HTML tutorials, uh, there was a website, I think it was called HTML goodies was. One that I, uh, used to read all the time. Um, but I, I didn't really, it wasn't anything that I followed very passionately. Uh, and, uh, one of my friends at school, this guy, Doug, had been taking a, I think it was a Pascal class in high school and, uh, it sounded very interesting.

[00:41:22] **Ben:** So I signed up for the precursor to that, which was QBasic, which was a very early Programming language, like line numbers, you could tell it to go to line 10, go to line 20, that kind of stuff. Yeah, I've never heard of that. It's, it was a lot of fun. It was a lot of fun. Um, and, and it was, it was kind of the most amazing thing I had ever seen, actually.

[00:41:42] **Ben:** It was, there was, I had always, I was always creative as a kid. Like I like to draw and I like to try and do things with the woodworking, but I was never, Particularly good at it and this idea that I could type stuff onto my screen and then make this world come alive on the uh, On the the rendering it just it blew my mind and it felt Hugely empowering in a way that nothing before that had felt like I could create uh, like I could with QBasic which I mean Not to blow it out of proportion.

[00:42:17] **Ben:** I mean, what I was doing was printing text on a screen or like occasionally I would print a line if the tutorials in class got pretty advanced. Um, but it was just, it was, it was super empowering. Um, but I'll tell you like one of my earliest memories from QBasic was that. There was, I think it was like, you had subroutines versus functions, and it had to do with whether or not it accepted arguments.

[00:42:41] **Ben:** I think a subroutine didn't accept arguments, but a function did. And the, the syntax rules for QBasic were that if it didn't accept arguments, you couldn't use parentheses. So you couldn't have, like, method name, open parenthesis, closed parenthesis, with no arguments. It would be a syntax error. And I remember thinking, like, this is the most ridiculous thing I've ever heard in my life.

[00:43:03] **Ben:** Like, I want to have parenthesis. I'm making a function call. It doesn't matter that it doesn't have arguments. It should have parenthesis. And, uh, You know, in hindsight, you can tell how violently against things like formatting, linting tools, which I am now today, that was clearly a very deep seated desire to have things my own

[00:43:26] **Tim:** way.

[00:43:28] **Tim:** Is it all your QBasic was in one narrow column with the Ben Nadell code? Formatting. But,

[00:43:36] **Ben:** uh, so, so I took this class. It was, it was super eye opening. And I immediately knew that this is, this is what I wanted to do with the rest of my life. Like, absolutely no doubt. This was, this was the path that I wanted to be on.

[00:43:50] **Ben:** And, uh, so I started to experiment with JavaScript. I started to learn. I think like that was just really, really new. Um, my, I had a, uh, an art teacher at the time, I think. I think her name was Mrs. Wall, who saw how much I was enjoying computers and she actually created a I don't know if you'd call it like a study program, but basically I had a class that was just me and her and, uh, and it was my opportunity to start to learn something called Macromedia Director, which was, I don't know if it was a precursor to Macromedia Flash or if it was like a parallel product that was used, I think, to create interactive CDs, that kind of stuff.

[00:44:30] **Ben:** Um, so I started to play around with that. And, uh, again, just like... It was, it was so exciting. It was all just so empowering, this ability to create these so silly, but just like online little worlds of, of expression. Um, so I ended up eventually going to school for computer science and uh, I, uh, side story, I applied to the school of liberal arts for computer science.

[00:45:01] **Ben:** My mother wanted me to have a very well rounded education and uh, some sort of clerical error, I was accepted into the school of engineering for computer science. They both had, uh, degrees. And so when I got to school and I found out what had happened, I asked my advisor at the time what the difference was between the computer science degree through the two schools.

[00:45:21] **Ben:** And she was like, well, if you do it through engineering, you have to take more of the, uh, core curriculum for engineering, like electrical, uh, digital logic and learning about some and NAND and NOR gates, that kind of stuff. And, uh, and then also you don't have a foreign language requirement. I was like, Done.

[00:45:37] **Ben:** Done. Solved. End of discussion. Oh my God, my mother was furious at the idea of me not having a liberal arts education. Really? But it was like basically the same curriculum. I had to take more credit, so I think it, it evened out. But um, uh, school, so the curriculum there was mostly. Things like assembly language and algorithms and C and uh, there was this one class, I think it was called intro to web development by this guy, Professor Couch.

[00:46:11] **Ben:** And it was super popular and it was always, uh, always, um, I don't want to say sold out. I know it was always like filled up, like you couldn't get into the course. And I remember I took a, I signed up for a class in cryptography, I think, and two days into it. It was so far over my head, all this like, Alice and Bob and people listening to conversations in between.

[00:46:34] **Ben:** I had no idea what was going on. And my advisor contacted me and said, Oh, someone dropped out of that intro to web course. Would you be interested in signing up? I was like, absolutely. Get me out of here. It was, I was like, I couldn't understand anything. And this guy, Professor Couch, he's just, he was just one of those people who.

[00:46:54] **Ben:** Absolutely loves what they do, and it's like you could, in every sentence, this just, just like unbounded joy is, is present. He was, you know, he would make himself giggle, and he's telling stories, and he's throwing stuff, and just, uh, just a delightful person. And it was a, it was just a class about web development, you know, CSS and a little bit of JavaScript.

[00:47:17] **Ben:** I didn't, was it even, it was like really, really basic rudimentary CSS at the time. And, uh... Just, like, reaffirmed everything that I had felt with QBasic, that programming was just... Everything that I wanted out of life and and now web development was even more specifically like this is where I wanted to go.

[00:47:38] **Ben:** The web seems so exciting and it took all of the feelings of empowerment that being able to write code and print text on the screen, like now being able to have some sort of a web page. I mean, that was like taking it to another level. Yeah. Um, this ability to create. And, uh, so I just started to get more and more into it.

[00:48:01] **Ben:** And, um, I took a sign up for a database class. And ironically, I almost failed out of my database class. I think I got like a D plus on my first test. And I think I maybe ended up. The class with a C plus average and, uh, today there's almost nothing that gives me more joy than writing a SQL. It's, it's one of the, it's the best.

[00:48:22] **Ben:** It's one of the most satisfying things I can do with my time is figure out why something's not running performantly, figure out where indexes are supposed to go. Um, but yeah, uh, so, so, uh, I did get during one of the summers, I got an internship at this company, Cocopelli New Media. And they just happened to be using, uh, ColdFusion 4.

[00:48:46] **Ben:** 5, and I had never heard of it before. Um, I had dabbled a little bit with, uh, ASP Classic and PHP in various, uh, courses at school, and it was okay. But then... I tried this ColdFusion code, and it was, to me, at the time, felt just like a night and day difference. It was, it was like everything that I wanted programming to be without all of the, uh, friction that I felt with some of the other programming languages.

[00:49:15] **Ben:** And, uh, I mean, that was in 19... 1999, I think? So, I've been coding in ColdFusion since then, so that's 21 years, and ColdFusion is today, for me, as thrilling as it was back in 1999 when I first discovered it. Especially, you know, at the time it was Macromedia, ColdFusion, Macromedia was eventually purchased by Adobe.

[00:49:41] **Ben:** And now I program in Lucy CFML, which is an open source engine for a ColdFusion compatible code. And uh, I don't know, I just, I wake up every day excited to be a programmer. And um, I, there's, there's been times in my life where I actually feel guilty about that. I feel, not guilty, I feel self conscious of how excited I am to be a programmer every day.

[00:50:06] **Ben:** Because I know that there are a lot of people who aren't in love with their jobs. And, you know. It's a privilege. It's a hundred percent a privilege. There are people in this world, a non trivial number of people who are waiting for Friday to roll around so that their weekend can start. And I wake up every day excited to do what it is that I get paid for.

[00:50:29] **Ben:** And it's, it's, it's something that I, you know, we're here in the company of friends. Like, that's not something that I tell everybody because it's not, that's not what a lot of people want to hear.

[00:50:39] **Tim:** You just told all 100 of our listeners. My mom knows

[00:50:44] **Carol:** now.

[00:50:46] **Ben:** But, um, yeah, I don't know. That's, uh, I hope I, I covered some of the, some of the finer points there.

[00:50:53] **Ben:** I sort of rambled a little bit, but I just

[00:50:56] **Tim:** love it. So, so Ben, you know what Tags sold me? Uh, this isn't a ColdFusion podcast because a lot, all of us have done ColdFusion at some point, but we've done a lot of other things too. But when I saw CFQuery and how you could write a SQL statement. That looks like a SQL statement, rather than some long parameter string like I had to do with ASP.

[00:51:16] **Tim:** I was like, oh man, this language has got something right there. Your eyes are big. Yeah. Yeah, that was like, oh wow, that, that looks fantastic. It, it definitely, the language had its problems and growing pains, but that made it, that right there, I'm like, yeah, that makes sense.

[00:51:31] **Ben:** Well, it's interesting. Uh, you know, I think about, obviously some apps are much more complicated than other apps.

[00:51:38] **Ben:** But. For the most part, I think a lot of apps are just glorified front ends to databases, right? They're not doing super heavy business logic. It's rendering records, allowing people to update records, creating new records, correlating records. And, and I think about the fact that And reports. And reports. And I think about your app as a glorified CRUD application, CRUD being create, read, update, delete, that wouldn't you want a language That gives you the best ergonomics around writing SQL.

[00:52:12] **Ben:** And I don't know how the CF query tag doesn't sell everybody. I don't know how people see that and don't think to themselves, that's what I want

[00:52:20] **Tim:** in my

[00:52:21] **Adam:** life. I think it did sell everybody in 19, you know, 98. It was one of like two languages where you could do that. You know, now that it's 20, 20 ish. And you can have pretty close to raw SQL in every language, or just about every language.

[00:52:39] **Ben:** It's not, I don't know, maybe.

[00:52:42] **Adam:** It was certainly early to that whole making hard things easy approach to app server platforms, whatever you want to call it. I get a lot of credit for that.

[00:52:58] **Tim:** And one thing you talked about that really took me back was the whole, the QBasic and the line numbers. Yeah. Were you ever the guy?

[00:53:07] **Tim:** 'cause I was always this guy. I'd go into a store if they had any computer that was sitting there like plugged in. That was like, for demo, I would control C, whatever they were doing, And I would look What does, what does control C do? So control C, typically they would have like some little. Advertisement on there, like, you know, the price of the computer or, you know, hey, buy me.

[00:53:28] **Tim:** They would have it on the screen. So, CTRL C would basically kill whatever program was running. Sometimes there's another key. So, that was the, that was the kill switch. It's kind of like CTRL

[00:53:36] **Adam:** delete for the command line.

[00:53:38] **Tim:** Exactly, yeah. Gotcha. And so, so I could drop to the, to, to, uh, the, the basic or QBasic terminal.

[00:53:44] **Tim:** And then I would just type a little program that was like, uh, print, Tim was here. On line 10, go to 10. And then it would just scroll infinitely down the screen. It would just constantly scroll. Tim was here, Tim was here, Tim was here, Every computer in all of middle Georgia was... Tim was here, obviously.

[00:54:04] **Ben:** I almost...

[00:54:05] **Ben:** I feel like I almost certainly did that.

[00:54:08] **Tim:** I bet you did.

[00:54:09] **Ben:** Oh, you know what I missed? There's a whole segment on the TI 82. Did anyone ever program a

[00:54:15] **Adam:** calculator? Yeah,

[00:54:17] **Ben:** that was a huge, that was in high school. Uh, I don't know what the kids are using these days, but when I was in high school, we had these big scientific calculators and, uh, you could program in it using, I don't know what it was, some very rudimentary programming language.

[00:54:31] **Ben:** I don't even know if it had

[00:54:32] **Adam:** variables.

[00:54:35] **Ben:** It was just, it was so, it was so much fun. You could draw little pictures, you know, like you actually turn pixels on and off to draw pictures. And, uh, I don't think it had variables. It had matrices, and I think you could store values in the mate, like, you know, A1, A2, B1, B2, that kind of stuff.

[00:54:52] **Ben:** And then you'd have to just remember what things reference what that was. That was really awesome. I totally had forgotten about that.

[00:55:00] **Tim:** Another thing you. Talked about that, that struck a chord with me. Was that your story about your teacher, like the, the one, particularly the one who like created sort of this personal course for you and then the other teacher in college who was so excited?

[00:55:13] **Tim:** Um, just, yeah, looking back, you know, I, I look, I, I felt like I was manipulating my teachers to let me use the computer because I was seriously, I was seriously like a drug addict when it came to, came to, I wanted, all I wanted do was spend time with those computers. Yeah. Looking back, I realized they were, they were nurturing me.

[00:55:31] **Tim:** Yeah, they saw it. They saw the potential there. And I think that if you have a teacher who truly loves their subject and truly cares about their students, that is the most transformative thing in a young person's life is to have a teacher like that. Only if you have one, it's all it takes.

[00:55:49] **Adam:** So thanks everybody for listening.

[00:55:51] **Adam:** Again, as usual, if you would Do us the favor of sharing this podcast with a friend. We would really appreciate it. Uh, it would also be a huge favor if you could rate us on Apple Podcasts. That is the only place that, yeah, again, the bug is still there. We're working on it, but you can only rate us five stars.

[00:56:08] **Adam:** Don't bother trying anything else. You know, we'll let you know when they get it fixed. Uh, the, I have looked other places, Google Podcasts and Stitcher and, and other places. I can't find anywhere else other than Apple Podcasts to rate us. So they always, every other podcast I ever listen to says rate us where you get your podcasts, but.

[00:56:25] **Adam:** I can't find any other place. So it lie. Yeah. I don't know. Whatever. Rate us if you, if you can find a place and if you're feeling generous and we would really appreciate it. Um, as always, we welcome your topic suggestions or your feedback on Twitter and on Instagram that in both of those places, we are @WorkingCodePod.

[00:56:43] **Adam:** And until next time, thanks everybody.

[00:57:05] **Adam:** In my generation and, and, uh, probably I would say Tim, you and I are overlapping generations, but not, uh, same, not, not different or same, but whatever. That was entirely going to get cut from the podcast.

[00:57:20] **Carol:** No idea what you just said other than it is, it's not.

[00:57:23] **Adam:** Right, yeah, that's why it's going to get

[00:57:24] **Tim:** cut.

[00:57:25] **Ben:** Apparently, uh, rats and squirrels can survive falls from an arbitrary height.

[00:57:33] **Adam:** They can. It's pretty crazy. And, and, like, pretty much anything, when you get down that small, spiders and ants and you couldn't throw a rabbit out of a 30th story window and, not that I've tried.

[00:57:45] **Ben:** I just, I don't. And

[00:57:50] **Adam:** then it's stuck on a rabbit.

[00:57:53] **Ben:** What was the scene in UHF where they have a show where the guy is just like, is continually throwing animals out the window?

[00:58:01] **Tim:** I don't remember

[00:58:01] **Adam:** that.
