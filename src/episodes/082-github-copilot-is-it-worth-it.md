---
title: "082: GitHub Copilot - Is It Worth It?"
description: "GitHub Copilot is now generally available as a paid product, but is this something people want to pay for?"
date: 2022-07-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="450" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/working-code/id1544142288"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew talks about [GitHub Copilot][github-copilot]. After being in private beta for several months, this _"AI pair programmer"_ is now generally available as a paid product for $10/month or $100/year. But is this something people want to pay for? Will a price put the kibosh on grassroots adoption? Are there pros-and-cons to different pricing models? And, is there ever going to be a world in which Ben can get past his own fanatical formatting tendencies?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[github-copilot]: https://github.com/features/copilot
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/082-github-copilot-is-it-worth-it.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** and it's all powered by comments. Is that the idea is you type the comment and.

[00:00:03] **Adam:** not at all. I mean, it'll try to finish the comment for you if you wanted to, if you kind of pause or,if it thinks that the comment is fully formed and it describes what you want to happen next, it'll try to write the code that does that.

[00:00:14] **Ben:** D does it prompt you first? Like, does it say, Hey, I'm gonna do this or just does it?

[00:00:19] **Tim:** Yeah, a littlelittle paperclip comes up on

[00:00:23] **Adam:** okay. Here we go. It is show number 82. And on today's show, we're gonna be talking about GitHub taking their software and going paid, right.

[00:00:51] **Adam:** All software should be free, maybe sort of, kind of no, no. Yeah, yeah. I mean, I like getting paid too, so, but first, as usual, we're gonna start with our Tris and fails. Carol's not here tonight because she's a little busy getting ready to get married or something who knows whatever

[00:01:06] **Tim:** selfish.

[00:01:08] **Adam:** so, Tim, why don't you start us off?

## [00:01:11] Tim's Triumph

[00:01:11] **Tim:** Yeah. so Carol's not here, but, I referred to something that she does at work or used to do. I mean, I dunno if she still does it, but, I called it relay programming where, they would have a different shift. And so like she would start, programming some stuff and then hand it off to someone else and they would take it, in the evening shift.

[00:01:27] **Tim:** And then they'd come back the next day and just kind of flip flop, just out of necessity, I'm kind of doing the same thing. We have someone who works with their only part-time they work. She only works half a day. And so, in the, I talked about last week that, I just felt bad that I kept delegating all the fun stuff.

[00:01:44] **Tim:** So I delegated something to her, but I'm like, you know what? You only work half a day. So how about you work it on in the morning? And then we'll meet when you're about to, to clock out and then I'll pick it up from there. It was actually quite fun. It's, I, haven't done a lot of pair programming and it's kind of like that, cause she's very, I'm a bit loosey goosey with the formatting and I'm like, eh, it works.

[00:02:02] **Tim:** It's close enough. She's very strict. And so just having someone come back and go and clean my stuff up, cuz she can't leave it alone or she can't leave it alone. If something's not capital to load is something's not capitalized correctly or something. but then also it's something she's never worked on.

[00:02:17] **Tim:** So she gets to see. This is a system that I'm extremely familiar with. So she gets to see what I do build on that. And then I send her a message at the end of the day. I'm like, here's what I did. Here's what you needed tomorrow. And so something I thought was gonna take two weeks, we actually knocked out in about three days,

[00:02:33] **Ben:** nice.

[00:02:34] **Tim:** so I was pretty, pretty happy with.

[00:02:36] **Tim:** So yeah, I was happy about that and glad to be back in the, in the, not delegating, all the fun stuff to everybody else.

[00:02:41] **Ben:** it's interesting. for whatever reason, when you were talking about relay programming, it reminded me of a talk. I think I heard how Helms give many moons ago about, fuse box, which even people in the ColdFusion world this might be before them. It was very early. Framework. And, they were talking about working with outsource developers and one of the strategies that they had for outsource developers were they would go and they would define all the inputs for the fuse.

[00:03:09] **Ben:** And then that would become the specification. It was like the inputs and the outputs for the fuse box was almost in a, in like a, in a weird way, almost like a unit test. Like, I think you define the inputs and the outputs, and then it rendered a template and things had to line up, and they would work with developers by defining the inputs and outputs.

[00:03:25] **Ben:** And then the outsource developers job was to fill in all the gaps. and I think some testing frameworks will do that as like a, as like, not frameworks, but like testing, experiments, not experiments, like classes where you, I guess they'll define the test, but then you have to fill it in. So it passes.

[00:03:41] **Ben:** And I wonder if that would be an interesting division of responsibilities for group based programming. It's like one programmer would come in and kind of do the high level method calls, but the methods would actually be empty. And then, so like, you're kind of in this one head space where you're thinking about how everything fits together and what calls would have to be made, but then someone else can come in and sort of fill in the low level details about, well, when you call this, like here's what actually happens.

[00:04:03] **Ben:** And

[00:04:04] **Tim:** so you're

[00:04:04] **Ben:** I, I dunno if

[00:04:05] **Tim:** this you're kind of building the skeleton and they're filling in the guts on

[00:04:08] **Ben:** yeah, I don't know if that would be a nightmare or if it would be an interesting experiment, but

[00:04:13] **Tim:** Try it out.

[00:04:13] **Tim:** Let's know

[00:04:14] **Adam:** I, don't know if I could do that. Like, I feel. I have a rough idea of what I want when I start to make a method, but then it's usually I end up changing the arguments, at least once, sometimes like five times as I'm writing it. I'm like, no, it'd work better if I did this or that, but

[00:04:29] **Tim:** Anyway, that's me. How about you, Adam?

## [00:04:31] Adam's Fail

[00:04:31] **Adam:** Oh, I'm gonna go with a fail this week. And, that is that, I know that our database backups are working because I needed them. yeah, so, we had a customer ask us to do some bulk data cleanup for them. I've talked a little bit about like our lists feature in the past and They basically said, we've finally figured out how we wanna do this and we just have so much old data.

[00:04:53] **Adam:** That's not the way that it should be. So can you just delete everything of that's like all the lists that are this type that were created before this date, which this date was only like a week and a half, two weeks ago, something like that. and. So I was like, okay, sure, no problem. And I went and did it, and then after it ran, I went, oh, I'm in the wrong production database.

[00:05:12] **Adam:** So I just

[00:05:13] **Tim:** whoops.

[00:05:14] **Adam:** like thousands. Yeah. Yeah. On production. I just deleted thousands of lists for the wrong customer.

[00:05:23] **Adam:** Oh, no. So I was like, okay, how do we do a database restore? like looking for the documentation on that real quick. and cuz we've never had to do one before. Like we have our backups and we've,we've messed with it a little bit just to like, know that it's working, but it's been so long since we've needed to touch that.

[00:05:39] **Adam:** The, we just, it was not a well practiced skill, so it's like, okay, get the database up. And then we okay. We it's only really like two tables that are affected out of like these huge databases, the backup itself for this one server was like five and a half gigs. and so it takes a couple minutes to get it all standing up databases up and it's like, okay, now what?

[00:06:00] **Adam:** Cuz we only want certain data. Right. So what I ended up doing was using like MySQL dump, which will copy the data structure and all of the data into like a SQL. And before, like, so it, it creates the create table, statements to create the tables as if they're not there. And then before that it says, drop table, if exists or something like that.

[00:06:21] **Adam:** And before that it like disables all referential integrity so that you can do what basically what I did here. So it'll my foreign keys. Won't like, stop me from getting stuff done. So disable referential, integrity, drop the table, recreate the table, drop in all of its data. And then turn on referential integrity again.

[00:06:41] **Adam:** And thankfully the backup was from like four hours or six hours prior. So we didn't lose. And I checked, we, we audit log a lot of stuff too. And that was like the first thing I did was check and see, has anybody done anything that I'm gonna, lose by doing this restore to like six hours ago?

[00:06:56] **Adam:** And there was basically nothing. so that was incredibly lucky.

[00:07:00] **Tim:** Lucky.

[00:07:01] **Adam:** And then, when the restore was like, I don't know, maybe 80% done there's no progress bars or anything, but you know, just guesstimating about 80% of the way through the process of doing the restore. One of the people from the customer, one of their staff members was like, so we're experiencing some difficulties with the site.

[00:07:17] **Adam:** Certain things don't seem to be working. Right. And I'm like, yeah, we're working on that. I don't remember exactly what I said, but you know, we're aware

[00:07:24] **Ben:** seems

[00:07:24] **Ben:** seems fine on our end. Have you tried refreshing

[00:07:28] **Adam:** Oh, it wasn't gonna be that quick. Yeah, no, we were, it was still probably a half hour away from being totally fixed, but, yeah, it's just like, I'm glad you didn't notice, two hours ago because

[00:07:38] **Tim:** I know I mentioned this before, but that completely reminds me of the time I accidentally truncated every table in a database, in a live database.

[00:07:46] **Ben:** did you do it to every table?

[00:07:48] **Tim:** So it was sort of like a mass copy kind of thing. It was copying one server to basically another server, like using, We didn't know how to replicate properly back then.

[00:07:56] **Tim:** So we had scripts that did it, and the first thing it did was would, truncate all the tables and then rebuild, drop the indexes, rebuild, put the data in drop the referentials kind of what Adam was talking about. So it would be easier to insert, do the inserts and then put the indexes back on.

[00:08:11] **Tim:** And so, yeah, I had these scripts all running, they work great. And I ran it on production by accident but for what fortunately, and I'm like, I saw that I'm like, oh crap. So I restored the database, it took like an hour to restore it from the backup. But fortunately that particular customer, their internet had been down was down all day.

[00:08:29] **Tim:** And so none of them, they weren't hitting the system at all. I got so incredibly lucky. They're like, I'm like, Hey, so just to let you know,how's everything going? They're oh, well our Internet's been downed all day and yeah, everything looks great. I'm like, okay. I didn't, they never knew.

[00:08:42] **Tim:** I never told them, never informed them. that for several hours they had no data.

[00:08:48] **Adam:** Nice. So, uh,yeah, I make myself a little to-do list every day. like first thing I do every morning, at least, a work to-do list, not like a all day thing, but anyway, so for the rest of this week, after that happened, the first thing on my to do list every day was, do not

[00:09:03]

[00:09:03] **Adam:** up production. Just like a nice little reminder. Be careful. Look at where you are.

[00:09:12] **Ben:** at work, no one outside of the, the operations team, the platform team has right access to the production databases. So every now and then we'll have a super special request from a customer and we have to do some manual SQL stuff. What will often happen is the engineer will write the SQL and then they'll have to hand it off through a ticketing system, to the platform engineer.

[00:09:34] **Ben:** And I have gotten into the habit for this very reason of in my ticket. I will have one script. That's a select. And I say, run this should return this value. If it doesn't return this value, you are not in the right place. And like, if that works, then you can run your, destructive scripts. But I I've.

[00:09:50] **Ben:** Yeah. It's, it's terrifying, changing production data. I'm so happy. I no longer have access to, to write anything to a production.

[00:09:58] **Tim:** that's funny.

[00:10:00] **Ben:** I'll tell you though. One thing that's interesting and thing. And I don't know. So I use a gooey for my database client. I use this piece of software called nav.

[00:10:08] **Ben:** It's just, you get your list of databases on the side and you can see your list of tables and there's a query editor and everything. And I find it to be a very joyful piece of software, but whenever I'm working with the platform team and they want to share their screen and show me what they're doing, they all insist on using command line, MySQL, tools.

[00:10:28] **Ben:** And I'll tell you, like, they're just, they feel very slow. I'll see them trying to do stuff. And this is not a dig at the engineers. I don't think it's an engineer's fault. I think it's just dealing with SQL from the command line and running lots of queries in, in series from the command line seems to just be very slow when I do the same kind of thing in my gooey, it's like done it it'll run like thousands of queries in, in like 10 seconds.

[00:10:52] **Tim:** And on the command line, it, I dunno if it's the network protocols or something, but I just, Well, I mean, they're piping it to console, right? So, I mean, it's gonna be a lot on the

[00:11:02] **Ben:** I just feel like they it's like some of the people who use VIM where you're like, I feel like if you just used a different editor, maybe you'd be better.

[00:11:09] **Adam:** hot.

[00:11:10] **Tim:** yeah. Pick the

[00:11:10] **Tim:** hardest editor.

[00:11:12] **Ben:** well, I, no, that's not a dig at VIM. I'm saying like,

[00:11:15] **Tim:** No VIM sucks.

[00:11:15] **Ben:** I just don't think database interaction on the command line feels very natural and I don't, it doesn't from what I've seen people do. And this is obviously a very small set of people. it just doesn't feel like a very effective way to do it.

[00:11:29] **Ben:** Like we just feels much more effective, but

[00:11:33] **Adam:** use a gooey. Yeah. I mean, I've done it through the command line and I. I'm more productive with it through the GUI. don't know that I experienced any latency or anything that felt like one was faster or slower than the other, but my ability to use it quickly is definitely better with the GUI.

[00:11:50] **Ben:** Well, like even so, so we had this, one of the things that we had to do just recently was we had to get access to a database for one of the clients and export. I, he had to run a SQL query that I wrote, and then he had to export it as a CSV. And in nav ACAT, like there's literally a button for exporting the current query results.

[00:12:10] **Ben:** And CSV is one of the output options. it's like, it's a wizard, this all columns quoted limiters, done exported as a CSV. And he insisted on doing it through the command line and it kept coming out wrong. Like he kept not escaping characters. Right. And then finally he comes back. He's like, no, I think I got it.

[00:12:28] **Ben:** All I had to do was. Run the query and then pipe it to this command line, which then piped it to another command line, which parse it as a CSV, which then like piped it to something else which mapped all the values onto quota values. I'm like, bro, if you had chosen to use a gooey, like it would've literally been done 15 minutes ago.

[00:12:47] **Ben:** I think you're just making your life more difficult than it has to be.

[00:12:50] **Tim:** said, this is like the infrastructure team.

[00:12:52] **Ben:** Yeah,

[00:12:54] **Tim:** Yeah. See, they're just used to working from command line.

[00:12:56] **Ben:** yeah, yeah, yeah.

[00:12:57] **Tim:** that's just, that's what they know. So.

[00:13:00] **Tim:** it's so that they can all do their jobs from like the beach or whatever, and just. iPad, If only their lives are that glamorous, those guys are always on call.

[00:13:08] **Adam:** Yeah.

[00:13:08] **Ben:** God. I feel so bad for them. Honestly, they do seem to always be on call.

[00:13:13] **Tim:** Yeah. They're like, oh, I'm off. I everything's down. Okay. I'm not off anymore.

[00:13:16] **Adam:** for me. So

[00:13:18] **Tim:** I guess I'm coming into work.

[00:13:22] **Ben:** Oh.

[00:13:23] **Adam:** that leaves you, Ben, what's going on, man.

## [00:13:26] Ben's Fail

[00:13:26] **Ben:** I'm gonna go as a failure.

[00:13:27] **Tim:** You guys

[00:13:30] **Adam:** You know what I like to look at it this way. I don't wanna hide my mistakes, my failures, that's kind of my, the whole reason for this segment, right. Like is to normalize failure. And so I've had a lot of really good things happen this week, too. I could have picked any one of them as a triumph, but you know, it's like it's sharing,

[00:13:45] **Tim:** all right, so I'm the jerk. Thanks. Thanks. sorry, Ben, go ahead.

[00:13:51] **Ben:** , So I think I had mentioned on the previous episode that the support team recently clued me into the fact that I can go into our Zen desk instance and pull up this thing called the problem finder and allows me to filter and sort on feature requests and bugs and incident counts.

[00:14:05] **Ben:** And, and when things were created and last comment on et cetera. And so I've been spending a lot of time going through this. And one of the highest requested features is the ability to let the back button in the browser work naturally when people are going from one view to another. So when you log into our application, the first thing that you see is a list of projects.

[00:14:26] **Ben:** And you can filter that list of projects based on ownership and keywords and project types and owners and groups and stuff. and you can pageant through it. Then, if you click into one of the projects and then you hit the back button on the browser, it brings you back to the list of projects, but it's reset all of your filtering, which if someone is searching for something and they're not quite sure if they're looking in the right thing, going back and forth is a pretty natural thing between a, a list of results and a detailed page.

[00:14:53] **Ben:** And I have several times in my life, tried to update this page to use the URL as the source of truth. And every single time that I've tried it in the past, I have failed because it's in a really complicated situation. It's so, so the V6 platform is built primarily on angular JS. Developer a long time ago, decided that he wanted to build this view in react and no one was there to stop him.

[00:15:22] **Ben:** Unfortunately. So the list of projects is react rendered inside of angular, and it uses this, reflux pattern where it's like triggering actions and those actions go into stores. And then the react components consume from the stores it's really complicated. And then it has to interact with the angular outside of it.

[00:15:42] **Ben:** Anyway, it's super complicated. the last time I tried, it was probably maybe a year ago, so I saw it in the zenes tickets and I thought, you know what? This is gonna be the day. This is gonna be the day that I set my mind to get this done. I'm gonna get it done. I opened up the code and I started looking through it and I was just like, what the F this code is so complicated.

[00:16:00] **Ben:** And I like, I couldn't even figure out how to start. Like, I didn't even know what step one would be. It was so. It's so convoluted and the control flow is so, so much indirection. And, I gave up like, like after like 15 minutes of just trying to wrap my head around anything relating to this code, I just gave up and it was very, I, it just makes me angry that one, I didn't have the fortitude and the grit to finally fix this problem.

[00:16:28] **Ben:** And, and then at the same time, I'm having parallel, thoughts of rage and anger for the person who built it this way in the first place. and I don't know, I

[00:16:36] **Tim:** Thanks, Steve.

[00:16:38] **Ben:** just, I just wanna be able to fix it. and I just, I don't know how to do it incrementally. Like I really just wanna rebuild the whole thing in anger and rip out all the react stuff.

[00:16:49] **Ben:** And I, and again, this is not a slight against react. This is just like this Frankensteinian confluence of multiple frameworks and paradigms, and it's just, it's a hot mess. And, I just don't know how to attack it. I don't know if it's worthwhile or if I can do it. I wish I could figure out how to do it incrementally.

[00:17:10] **Tim:** it, I mean, is it because of your lack of familiarity with

[00:17:16] **Ben:** it's it's the code is just really complex. it's like absurdly complex. And I'm not saying that because like it's unfamiliar to me. And so I just don't like the things that I don't understand. I've literally tried to update this code so many times and I maintain this code. I mean, there's other things that I do inside of it that, that I can do, but it's just, it's all this, like, it's just terrible.

[00:17:39] **Ben:** I hate it. I hate it so much.

[00:17:40] **Adam:** man, in my experience, anything having to do with changing the default behavior of the back button is just a world of pain. like users expect it to work a certain way. And when you change that on them, it messes them up. and then like, they're gonna try to figure it out anyway.

[00:17:54] **Adam:** So you have to put in all these like janky workarounds, and he is just like, it's a, it's the like radar detector and the radar detector jammer and the jammer and the Jamer sort of situation. and like, we just have one part of our application that we wanted to do, like basically block the usage of the back button.

[00:18:11] **Adam:** And I was like, okay, I will do it, but it is, I'm gonna do the simplest possible thing I can think of. And if it ever,Needs, like if the requirements ever change, we're gonna sort of just rearchitect it from the ground up for like every time we have to change it, just start over because you, you don't wanna have to like build on top of that.

[00:18:27] **Adam:** the thing that we did for ours is like, is a event registration system. And we have a built in way to like go to other steps. So if you wanna go back and change something, you're supposed to, click on the, like the, it looks like a temp, like a wizard,

[00:18:39] **Ben:** Okay. Yeah. sneak attack.

[00:18:39] **Adam:** it's got like a progress bar with little stops on it that you can click or whatever.

[00:18:43] **Adam:** And, so the way that I did it was like, with push date. So when you land on a page, the first thing it does is it pushes another thing into push date, so that if you hit the back button, it stays on the same page. And then like, I detect that you went back in the history and I just push it again. yeah.

[00:19:04] **Tim:** you're taking. Credit card payments. You don't want to go back and recharge that card, right. That there's annoys people to death when you charge 'em twice. So yeah, definitely fight with that back button all the

[00:19:18] **Ben:** of checkout processes. Where you're in the middle of, submitting the payment and they will put a message up on the screen that says like, don't refresh this page. You may be charged more than once.

[00:19:33] **Adam:** yep. Don't hit back. Don't

[00:19:35] **Tim:** time,

[00:19:35] **Tim:** but nobody reads, right. They're just trying to get through as fast as possible. Nobody reads.

[00:19:40] **Adam:** Yeah. You would think with money on the line, people would, pay a little closer attention, but.

[00:19:44] **Tim:** Yep.

[00:19:44] **Ben:** anyway, maybe, next month I'll tech this problem and it'll work.

[00:19:48] **Tim:** Here's.

[00:19:49] **Ben:** Yeah. That's what I got.

## [00:19:50] What Is GitHub Copilot?

[00:19:50] **Adam:** All right. Well then, let's move on to our topic for the day. it's unfortunate that Carol's not here because I know that she would have a lot to contribute to this conversation, but because it's kind of a timely thing, we're gonna attack it anyway. so in case you haven't heard GitHub created this thing, they call it co-pilot a, and for, I don't know about a year now, it's been in private beta and for those that got access to the beta, it's been free and they just announced earlier this week, as we're recording that, it's no longer gonna be free in private beta, they're gonna start charging for it.

[00:20:21] **Adam:** it's still free and it's in public. I guess don't know exactly how it's gonna work. It's it. It's now available to the general public. they're gonna start charging for it. It's I guess maybe if you are already using a beta or something, so one way or another, you can get, you can continue to use it for free until August 22nd.

[00:20:37] **Adam:** so I guess the first question that somebody might have is like, what is it, what does it do? so they, they bill it as your AI pair programmer, which first off I have, I take issue with anything that calls itself, AI, that isn't AI, which as far as I know, true, AI has still never actually been invented, I guess, is the right word.

[00:20:59] **Adam:** Like it's never been created I'm

[00:21:02] **Tim:** don't know some Google guy with Lambda begs to differ, so,

[00:21:06] **Adam:** that later. That might be an interesting thing to talk about, but,like I, I just take issue with anything that has anything at all to do with like machine learning or guessing they call it AI. And that just bugs me from a, from a. Type a personality, nomenclature,you're actually, you're using the wrong word type of perspective.

[00:21:24] **Adam:** So, but they describe it as your AIP programmer and the best way that I've thought to describe it to people is there's a feature very similar in like Gmail. So if you're typing out an email to somebody, you notice how like, Gmail kind of suggests in like great out text, right ahead of your cursor, like, oh, we think you're typing this sentence.

[00:21:40] **Adam:** So it offers to finish it for you.

[00:21:42] **Adam:** Um, and it, I guess if you just hit tab or something, it accepts what they're suggesting.

[00:21:46] **Tim:** And teams chat does that too

[00:21:49] **Adam:** Oh, interesting. So, yeah, so that's basically what copilot is, but it's not just like the current line, right? It's it tries to be much more advanced. You can write a comment.

[00:21:58] **Adam:** That's like, okay, a function that does this and this. And it tries to, to guess the entire code of the function and in the language that you happen to be operating in, I've used it in like JavaScript and ColdFusion and type script. And I think that might be, I mean, HTML CSS as well. and it seems to have no problem with all those.

[00:22:14] **Adam:** And I think if it can do CFML, it can do anything.

[00:22:17] **Tim:** Yeah. Right.

[00:22:19] **Tim:** Can you put a comment? I want all my code to look like Ben tolls in like a skinny little column. And it'll do that for you.

[00:22:25] **Adam:** line wrap at like 12 characters, Um

[00:22:29] **Ben:** 80 characters. Yeah,

[00:22:32] **Adam:** and, yeah, so that's the gist of what it is. so have you, either of you guys used.

[00:22:38] **Tim:** I, I signed up for the beta and I did not get, I was kinda late in the game, so I didn't get selected. But now that, I mean, there is a free trial. I'm gonna play with it, after this show. So,

[00:22:50] **Ben:** and I have not used it.

[00:22:50] **Adam:** are you interested in it at all? Ben, have you heard of it before today?

[00:22:54] **Ben:** I,yeah. I've heard of it. And I've heard some podcasts about it. I don't know if I'm interested. I'm such a fanatic about how I style my code

[00:23:02] **Adam:** being in

[00:23:02] **Ben:** things. Yeah.

[00:23:04] **Adam:** You're a control freak.

[00:23:05] **Ben:** I think if I watched a video, I've only ever heard of it. I've never actually seen it in action. I think maybe if I watched a video and got a better sense of what it was doing and then I could picture myself perhaps using it, then I it's too abstract for me so far. But it sounds, I mean, everyone's raving about it. I mean, it seems like it's really compelling.

[00:23:25] **Tim:** only works with like vs code visual studio, Neo VM, and jet brains. Do you use

[00:23:29] **Ben:** No. So text

[00:23:31] **Adam:** Nope.

[00:23:33] **Tim:** is that what you use? Oh my

[00:23:37] **Ben:** Yeah. Ben is using the best thing from 10 years ago. would he do anything better? Yeah, I'm a all day vs code for everything kind of guy. and it's all powered by comments. Is that the idea is you type the comment and.

[00:23:55] **Adam:** not at all. I mean, it will read your comments as you write them and try to infer it'll try to finish the comment for you if you wanted to, if you kind of pause or, it can read the comment if it thinks that the comment is fully formed and it describes what you want to happen next, it'll try to write the code that does that.

[00:24:10] **Ben:** D does it prompt you first? Like, does it say, Hey, I'm gonna do this or just does it?

[00:24:14] **Tim:** Yeah, a little paperclip comes up on

[00:24:19] **Adam:** it's very much like Gmail, right? Like you can see it jump in there and you just hit escape and it goes away or you can keep typing or you can like hit tab, I think is what, what, like accepts it there. Now the, I guess the one thing that I didn't do great, that I should look up how to do.

[00:24:35] **Adam:** There's a, when it suggests something to you, it a, it actually has like figured out maybe 10 suggestions or something like that. And it just gives you like the top ranked thing that it,it figured out, right. It ranks them, by how, accurate or confident they think that is the correct suggestion.

[00:24:51] **Adam:** And then they offer you just that one. And there's a keystroke. You can hit that, like pulls up a second editor window or tab, and it shows you the other ones that you can like cycle through, or you can scroll through 'em and pick 'em,to see what else it came up with. And I mean, for large chunks, it's been really interesting.

[00:25:07] **Adam:** Like when you, like, sometimes I will write a method name in the arguments and I'll just pause to kind of get my thoughts together and it pops in like the whole thing and I'm like, oh, okay. Yeah. Yeah. That's it. That's exactly what I was gonna do tab done, which is super cool. Right. it's like, I mean, it's nothing like, the it's not gonna replace me. but it does. it does take some of the tedium out of it, I guess. Right. Like if you tell it, you wanna resort by a certain column or whatever, and it does that like, okay. Yeah. Cool. I could have figured that out, but you saved, made the 90 seconds that I would've spent thinking about it.

[00:25:41] **Tim:** is this something, I mean, how often do you use this? Do you just every day or how what's your usage or is this like a cool thing? It's like cool some of the time,

[00:25:48] **Adam:** it's funny. I turned it on and I noticed it a lot in the very beginning. and the longer I went with it, the less, I paid attention to the fact that it was there. Right. Like it just sort of became just like the Gmail thing. Right? Like you start typing and it's like, that's what I wanted. Then you just hit tab and you keep going.

[00:26:05] **Adam:** and it kind of becomes very routine and normal and you don't even think of it as being something outside of the norm. And,the one place where I still feel like it kind of gets in the way and. I don't like it is when I'm trying to do something complex. Like if I'm trying to do maybe a one liner, but it's complex, it's two or three things kind of all nested together, but it's, it's still maybe within 80 characters or a hundred characters or something.

[00:26:31] **Adam:** So it's like, a callback function, it's a function and it's doing something in the curly brackets or whatever. And I get, 70, 80% through typing all that out. And maybe I haven't even paused, but it starts to like throw in the, what it thinks the punctuation is to end that line. Right. So it starts to like mess me up cuz the characters are just a little bit great out.

[00:26:51] **Adam:** So it's like, okay, did I type that? Or is that co-pilot cuz it's just like, and it's not even to the end of the line. Right? Cuz I've already got characters on the end of the line. Cuz when I type my open curly brace, the closed one gets added at the, after my cursor. So I'm already, still in the middle of it.

[00:27:03] **Adam:** Right.

[00:27:04] **Tim:** Where do I start? And you in

[00:27:06] **Adam:** something like that. Yeah. Where do I end? And you start. So I mean, but it's like, it just got on my nerves cuz it's like. I like I had in my brain exactly what I needed to do until you started popping in extra characters for me. And then, so that I found incredibly annoying and I would just hit escape anytime I saw it doing that.

[00:27:24] **Adam:** I'm just like, you know what? I already know what I'm doing. Just hit escape. Cuz if I, I felt like at least half the time, if not more, I would, if I tried to just accept what it wanted, then it would be a syntax error. Like, okay, let me, cuz maybe, it came up with that suggestion and I added one character and then it popped in the suggestion and I don't know, but it just, it was frustrating.

[00:27:44] **Ben:** is it making network calls? I assume it doesn't have like a machine learning library running in the background. I assume it's calling out to something. Do

[00:27:53] **Ben:** you know

[00:27:53] **Adam:** don't think so. I think it works offline, which is bananas to use a Bedel term. Yeah. I mean you, I think you do have to like, it is kind of a, it's not a crazy big download, but it, it might be a couple hundred megs or something like that.

[00:28:09] **Ben:** That's

[00:28:09] **Adam:** Pulls in.

## [00:28:10] Copilot's Pricing Model

[00:28:10] **Adam:** yeah, I mean, so they announced that they're gonna start charging for it. the price is gonna be $10 a month. If you pay monthly or a hundred dollars a year, if you pay yearly. So two months free. And I feel like that's just on the border of like somewhere between a no brainer and like, eh, too much, right?

[00:28:27] **Adam:** Like

[00:28:28] **Adam:** if it were $5 a month, I think that it would be a no brainer for me. And I would probably just expense it.

[00:28:33] **Adam:** at a hundred dollars a year, it's like, okay. But if I wanted to use an IDE itself that it was a hundred dollars a year, I'd have to justify like, why is that better than. V code or sublime or whatever.

[00:28:44] **Adam:** if it was a one time, a hundred dollars payment for my IDE, again, I wouldn't blink an eye at that, but

[00:28:51] **Ben:** it's interesting. The one time payment versus the subscription model, it definitely has a very different emotional feel

[00:28:57] **Adam:** yeah, exactly. I have the same thing over, like all software. Right. and it's crazy because,just the paradigm totally changed. Like I know we saw it coming and we saw it happen and it just kind of like still somehow managed to like, feel like it happened all at once where you used to just buy a piece of software.

[00:29:17] **Adam:** You, you spent the $40 on it or whatever, and then you could choose to use that version for life. Or now you have to pay the subscription. And, I don't know.

[00:29:27] **Tim:** just out of luck here. One of our listeners on discord, just put a comment about it, cuz you posted about it. And he said, Sean Oden says $10 a month or $10, a hundred dollars a year seems pretty steep. Considering that the program is essentially using an open source code base to make suggestions.

[00:29:43] **Tim:** Is it not regardless? I thought it was kind of cool when I tried it, but it's definitely not worth that much to me, but I also do very little code development outside of hobby stuff now.

[00:29:53] **Adam:** well, yeah, I mean, I think if you're a hobbyist, a hundred dollars a year for something that's gonna help you code that, I agree that would be steep, but if I can expense it, the question is like, okay, a hundred dollars a year for one person. Okay. The company can eat that. Well, now we have, what, if we have five people that wanna use it $500 a year, or what if we have 25 people that wanna use it?

[00:30:12] **Adam:** Like you're starting to get into questionable territory. Is it worth it at that point?

[00:30:19] **Tim:** Yeah. I mean, we've got, what about 70? not anymore. I think probably like 60 developers. So a hundred dollars a year. that's pretty, pretty pricey.

[00:30:27] **Adam:** Right? Well, I mean, at least at Invision, they won't have to get it for their infrastructure team cuz it doesn't work in a CLI.

[00:30:38] **Ben:** man. I'll tell you though. So I, when I think about introducing new technologies to an engineering team, so much of what I've seen in terms of adoption is a grassroots effort. it's very rarely the director of engineering. Or the CTO coming in and saying, Hey, we're all gonna start using this new technology.

[00:30:58] **Ben:** It is very often one random person who tries something and they kind of like it and then they show it to someone else and that person kind of likes it. And then suddenly there's a handful of engineers and then it becomes, okay, now this is gonna be the thing that we use. Cause everybody seems to like it.

[00:31:14] **Ben:** And when I think about pricing models that drive grassroots adoption, it feels very much like there should always be some sort of a freemium model where the individual or the person who's just doing it for fun as a side project, should be able to use it for free so that they can actually understand the value of it and get to play with it and then bring it as sort of a land and expand plan into a company.

[00:31:42] **Ben:** And then the company can start to use it from a commercial standpoint and they're starting to pay the, the enterprise price, not the free individual developer price.

[00:31:51] **Adam:** you know what, you're absolutely right. And I think that part of what that model does it like free for personal use and paid for, what do they call it? not corporate, but like commercial for, paid for commercial usage. Like if you're making money off of it, then you should pay that.

[00:32:05] **Adam:** And I honestly, I think that makes a whole lot of sense. And especially, I think that's great for marketing because then people use it for free when they're on their side projects or whatever. And they're like, Ooh, this is great. I really wanna have this when I go to work tomorrow. Right. Like, so that's the encourages people to try it.

[00:32:21] **Adam:** And then when they turns out they like it, they push for it at work. I think the tricky part there though is there's gotta be tons of people and companies that are just like, well, just use it for free. Like we're not gonna pay for it. Just say you're doing it for free.

[00:32:35] **Tim:** Just sign up using your.

[00:32:37] **Adam:** Yeah.

[00:32:38] **Ben:** Yeah. But there's always, I mean, the nice thing. Large companies is that they have all kinds of legal ramifications to just existing. And like, so they, they can't necessarily just have developers doing what they want. They have to have all kinds of license tracking and making sure they're paying for stuff that they're supposed to be paying for.

[00:32:55] **Ben:** So, there's definitely be people who slip through the cracks, but I feel like large companies wanna be on the right side of things legally. ButI just wonder if there'd be a way to, to have, even if it's not free necessarily for individual users, if there was a, if there was like a, like you could do X number of auto completions per month for free, like kinda like a free tier, like for like Netlify functions, right.

[00:33:18] **Ben:** I mean, Netlify functions are just backed as my understanding by Amazon's Lambda functions.

[00:33:24] **Ben:** So. They're basically just piggyback on Amazon's free tier, but you can do like what it's like 150,000 Lambda invocations a month or something for free. I mean, it's like some ridiculous number.

[00:33:35] **Adam:** Yeah. it's something crazy. And it's like by minute or something, right. So it's like a hundred thousand minutes a month for free or something like that.

[00:33:41] **Ben:** Yeah. So I feel like, there could be some sort of wiggle room there where you get some number of things for free per month so that you can try it out and see how it feels and see if it jives with your type of programming and your mental model. And then I

## [00:33:56] Free For Open Source Developers

[00:33:56] **Adam:** the thing about their pricing model for copilot that I kind of understand, but I kind of disagree with is they're making it, I forget exactly how they described it, but basically what they said is it's still free for, open source developers like that have a particularly popular library.

[00:34:14] **Adam:** Right. So basically it's like, they don't really go into the specific, the specifics of how they calculate that. But there's a line in the sand, right? Either you're a high profile enough open source developer that you get it or you're not. and the it's a black box that we can't see inside of, but. Sean Corfield said he qualifies for free. Like, all you have to do is go to copilot.github.com and click the button to like start to trial or whatever. And it'll tell you, okay, well, you wanna start to trial, but it's gonna be,$10 a month or a hundred dollars a year. And his was like, you qualify for free.

[00:34:45] **Adam:** So

[00:34:46] **Tim:** is it going off his GitHub name?

[00:34:48] **Adam:** yeah. Yeah. You have to log in with GitHub to pay for it. So it could see your account and all your projects and stuff. And I mean, I don't think it's because he has a, I don't even know if his company does like GitHub enterprise. My company does. And I was signed in on my account that disconnected my GitHub enterprise.

[00:35:02] **Adam:** And it doesn't that doesn't trigger it. Right. It still wants me to pay for it. And not that I would even say that I'm any sort of prolific open source developer. I don't think that I am, but, it just irked me a little bit. Like, I don't know. There was a, there was a. Database speaking of database, GOs, there was one back in the day.

[00:35:19] **Adam:** I think it's probably still around, but I haven't used it for a long time called Aqua data studio

[00:35:22] **Tim:** I, I use it.

[00:35:23] **Ben:** of.

[00:35:24] **Adam:** yeah. And, they had this deal where if you were an open source developer, they would give you a free license. And all you had to do was like send 'em a link to your GitHub projects or whatever. And I did that and I used it and it was a great, DBMS.

[00:35:36] **Adam:** And, like on the one hand, I kind of wish that they would do something similar for copilot. But then on the other hand, that's basically everybody that's gonna wanna use it anyway. it's gotta be at least 90%, right. So,

[00:35:46] **Ben:** so it's interesting that we talked about dispensing things at work, and I don't have a ton of different corporate context experience. I I've really only had like three professional jobs in my life that tend to last a long time. And basically none of the places that I've ever worked have had a real formal. reimbursement. I don't wanna say a reimbursement program, but I don't think it's ever been stated like, Hey, use the software that you like and we'll just pay for it. And I don't know, is that something that exists in a larger, more, mature company like Tim? I mean, I feel like of all of us here, you're at the most mature, they tell you what to use.

[00:36:29] **Ben:** So you can't just like, decide, Hey, I want to go try this,

[00:36:31] **Tim:** if

[00:36:32] **Ben:** SQL. Gotcha.

[00:36:35] **Adam:** I mean, I've worked at places that would let you do that. And I mean, my current employer, we have that attitude. It, I don't think it's codified anywhere. Yeah. I mean, if somebody came in and they were like, we want, I really wanna use jet brains and that's what I'm most productive in. And I want the license or whatever.

[00:36:52] **Adam:** Yeah, sure. Probably we

[00:36:54] **Tim:** Yeah. I mean, the reason, we enforce that is just because when you have like, know, desktop support, then, it's like for some reason, so, and so can install it. And now it's like, there's 50 different programs for the same thing and you don't have any expertise on it. That makes it really hard.

[00:37:10] **Tim:** So, I mean, I get why they do it. It does get a little frustrating, but, yeah. but as far as like open source stuff for free stuff, that's free. Yeah. You can install what you want. But I was gonna say to the question that Sean was talking about, that it's a bit steep, since it's like, based on an open source project, I mean, I get that, but then putting my business hat on it, right.

[00:37:28] **Tim:** It's like, what do you get when you're paying for software, particularly like an ongoing kind of thing you're paying for continual improvements, right. Even though yeah, sure. It's like polling,GitHub repositories to figure out, oh, you're writing this language and here's how most people do it.

[00:37:43] **Tim:** And here's my suggestion. I mean, they're gonna constantly be. Upgrading fixing, adding features. That's what you're paying for. Right?

[00:37:51] **Adam:** learning from that.

[00:37:52] **Tim:** It's the same thing. some customers like, well, you should just give this to me for free. I'm like I can, but honestly, if I give it to everyone for free, I have no incentive to ever do anything to it.

[00:38:02] **Tim:** Again, it is, it will be what it, and we did used to do that before. Right? You were like, oh, as long as you're making payments for us, all these other tools that we build for you,they're all free. And then it's like seven years later, it's still like using Adobe flash player. And it's just, no one wants to touch it.

[00:38:16] **Tim:** It's like, there is no incentive to go fix that stuff and make it better. But if you're paying on a monthly basis, you got a revenue stream coming in. you're gonna be incentivized to continually do upgrades and you can justify the work that's going into to improving software.

[00:38:32] **Adam:** I, and I think to your point, the Sean's question is very interesting. It's not, I don't think that the true value comes from the repository of all the code. I think the true value comes from the,

[00:38:47] **Adam:** whatever, the way, whatever they did to combine with machine learning, to, make it capable of doing its job.

[00:38:53] **Adam:** Right. Like, I'm sure it couldn't have done it without that huge repository of open source code to look through. But at the same time, like if you were given access to everybody's source code, I don't know that you could come up with the exact same thing. Right. So, there's definitely a value add there that is definitely worth charging something for sure.

[00:39:11] **Adam:** You know what

[00:39:12] **Tim:** Mm.That's

## [00:39:12] Coming Up With The Idea Of Copilot

[00:39:12] **Ben:** This is where my imposter syndrome will often kick in with things like this. Because I imagine if someone at the company turned to me today and said, Hey, Ben, can you go ahead and just create us a fun little machine learning program that does predictive coding based on what people have input based on, millions of open source projects.

[00:39:31] **Ben:** I, I wouldn't even know where to start, but like clearly someone said something like that to someone at GitHub and they were like, yeah, we could do that. Give a team in, in two years and I'll get you a product. and like just the, I don't wanna say anything crude, but like the TPA. Yeah. The Coones to be like, yeah, we got this.

[00:39:53] **Ben:** and I'm just like in I'm. So in awe of people who have that kind of vision, That they could take something that maybe they have no idea how that's even possible to do, but still have the audacity to be like, well, I'm gonna give it a try anyway. and I just,

[00:40:08] **Tim:** Yeah, but you know, they had a bunch of people who were already doing a bunch of machine learning or like they, they recruited people that were doing this like auto complete kind of stuff already. And they're like, yeah, we could do this with code.

[00:40:19] **Adam:** I was gonna say, I don't think it, the, I don't think the story was exactly as you would've said it. I think that they probably have a culture of tinkering. Right. I don't know if it's like Google's 20% time or whatever, but like, just people play with whatever interests them. And then it's like, if you come up with a good idea, for some way, we can use something that we're not already doing and you bring it to us, like maybe there's an incentive, you get paid a bonus or, raise or whatever, if it starts to, if it becomes a useful part of their product. that would be where I would assume that this came from, right. Somebody had an interest in machine learning and they did, maybe they built a thing that, solved, learned how to play Mario or something. Right. we've seen those things in the past and, they just were like, what do I have access to?

[00:40:58] **Adam:** That's a crap load of data. Well, I have everybody's code. Why don't we look through that and see what we can figure out. Right. Like, so yeah, I don't know.

[00:41:07] **Ben:** I'm just impressed with people I'm there. There's I feel like there's different levels of complexity in software and I feel very comfortable at a certain level of complexity, which is like more advanced than just crud, but like not so advanced that I'm doing distributed systems. And like, that's just where I operate really effectively, I think.

[00:41:28] **Ben:** And that, and I'm just, I'm in awe of anyone who is any level above that. It just blows my mind.

[00:41:34] **Ben:** Yeah. yeah.

[00:41:35] **Adam:** So

[00:41:36] **Tim:** Really well,

## [00:41:36] Adam And Carol's Thoughts

[00:41:36] **Adam:** maybe something interesting to think about is, ever since they announced that they were gonna go, paid like the public beta or private beta, whatever was over, my editor was like, oh, you need to reconfigure your license or whatever for copilot has stopped working. So it's like, okay, well, this is a good inflection point for me.

[00:41:52] **Adam:** I just, on that day earlier this week, I just turned it off and you know what, I haven't really missed it that

[00:42:00] **Adam:** much.

[00:42:01] **Ben:** Interesting.

[00:42:02] **Adam:** Like, I mean, there have been maybe one or two moments where I was like, oh, I kind of wish copilot would've filled that in for me. I probably could have done that. but you know what else too, though, I've seen a lot of examples of like, somebody's trying to learn a new language or, trying to figure out a new concept and. maybe I'm trying to figure out how to do something in type script. And I don't know how to do it, but if I write a comment that tells me how to do it, it'll show me. And then like, boom, I just learned something, right. if I look at that code and I pay attention to it, and I like, if I don't understand what it generates, then either I need to go research the code that it generated.

[00:42:34] **Adam:** So make sure that it's right. And then I'm gonna learn from that. Or I'm gonna look at the code and go, oh, okay. That makes perfect sense to do, whatever it was I asked it to do. And then I've learned from that. So I think that it's a really interesting like learning tool. and like I said,it's, it gets in the way sometimes, but it can be useful.

[00:42:51] **Adam:** I don't know where to put it. I don't know where it belongs in my head.

[00:42:55] **Ben:** Well, speaking about learning. One thing that I think would be very interesting and it's not really code completion, but a lot of times I'll be looking at a Java API because we can access Java from ColdFusion. I'm not really a Java developer and I, and there's a lot of weird caveats about Java that I don't fully understand. And I would definitely love a, Hey, I want to use this method on this class in Java, but I don't quite understand it. Just show me like 10 examples of this API being used. Like if you Google that, there are sites that are kind of like that, where it'll just be like, here's 150 instances that we found of this method being called in various open source projects.

[00:43:34] **Ben:** But those are typically like garbage sites with like, 15 ads on the screen and like just a little bit of code , but like, that would be a very interesting angle for it. I think,

[00:43:44] **Ben:** you know,

[00:43:45] **Ben:** not just auto complete, if you're talking about how it ranks 10 options and can show them to you in a different frame.

[00:43:51] **Ben:** It'd be interesting to have a frame of just show me examples of this kind of code being used.

[00:43:56] **Ben:** That that seems that almost seems more interesting to me, honestly, from like how I might use it.

[00:44:01] **Adam:** And you know what, though, if you did that, it like with, if you took copilot as it is today, and you are in the middle of an application, okay. I need to use this method. but I don't know exactly what I'm gonna pass to it. I don't know how I'm gonna use it. I don't know what to expect back.

[00:44:13] **Adam:** You just like type the method, name, whatever object it's on that sort of thing, open prints. And you just wait, it'll throw the suggestions at you and it will use the context of your other code above and below to try and figure out like what to pass in and yeah. Or, it might massage it to, to create the data that it needs to pass in sort of thing.

[00:44:33] **Adam:** I, I texted Carol earlier, since I knew we were doing this show about this, and asked her if she was gonna buy it. She's like, she's still on the fence. She hasn't decided not a hundred percent sold, but still thinking about it. Yeah.

[00:44:49] **Ben:** I'm surprised that it is not integrated into GitHub's plan pricing as well. I mean, I have a free GitHub account, so it doesn't necessarily apply to me, but

[00:44:57] **Ben:** I would be, I'm surprised that you don't get it as part of GitHub plans. like if you're on a pro plan or a team plan or something,

[00:45:06] **Adam:** What do you get on a pro plan these days? Because it used to be the reason that I had a pro plan for a year or two was

[00:45:12] **Adam:** because it was private repos. Yeah. And then they made private repos free for everybody I'm like, okay, great. So now I'm gonna stop paying you. Thanks.

[00:45:19] **Ben:** I know. I felt so bad the day

[00:45:21] **Tim:** now it's I think it's like team size now.

[00:45:23] **Adam:** Is that it? Okay.

[00:45:25] **Tim:** Yeah. Cuz we, we pay for it, but it's based off team size.

[00:45:28] **Adam:** We pay for it for our company. okay. That must be, yeah, because we have a limited number of seats based on what we pay. That makes sense.

## [00:45:35] Pricing Psychology

[00:45:35] **Ben:** It's it's pricing is so interesting. Oh, sorry. I just won like quick tangent. So, so I think about pricing with TV stuff, because, since the pandemic there's been a lot of early releases of movies that either in theaters and streaming at the same time, or you can rent them essentially the same day that they come out. And I will gladly go to a theater and pay 20 bucks for a ticket. I mean, it's crazy when I was a kid, it was like seven 50 or something. But

[00:46:04] **Ben:** anyway,

[00:46:05] **Ben:** like I'll go to the theaters, with the misses. Well, it'll cost us like 60 bucks between tickets and popcorn and stuff and like, that's totally fine.

[00:46:14] **Ben:** And then if I want to go and rent an early release on apple TV or Amazon or something, and it's like 1995, I'm like, Ugh. So expensive. I'm like, this is what,

[00:46:26] **Ben:** no, I'll just

[00:46:26] **Adam:** popcorn, the microwave popcorn waiting for you and the, all the

[00:46:29] **Ben:** I know, I don't,

[00:46:30] **Ben:** I don't know why it's like I've, I'm so conditioned to pay an exorbitant amount to go see a movie in public, but to do it in the privacy of my own home feels just like absurdly expensive.

[00:46:43] **Tim:** It's the experience though, right? It's a different, it's totally different experience. That's what you're paying for.

[00:46:48] **Adam:** Yeah. You get the huge screen and the sound and

[00:46:51] **Tim:** Mm-hmm

[00:46:52] **Ben:** But I can't even it's so hard to even rationalize it. Like I, if I say to myself, you would be spending more money to go to a theater to watch this and you wanna watch it now and it's available for rent. It's still, I'll still, I'll be like, nah, I'll see what else is on Netflix.

[00:47:09] **Tim:** Yeah.

[00:47:09] **Tim:** pricing's all about psychology. That's when we were in Barcelona, we had,some companies come in, they were talk, talking all about the psychology of pricing and it was pretty interest.

[00:47:19] **Ben:** And like, Hulu, I think I pay 10 bucks a month for Hulu or something. and like, I don't think about it too much, but somehow $10 a month for code related stuff that feels it's like, it feels way different.

[00:47:31] **Adam:** That you're gonna use every day. Yeah. The psychology

[00:47:33] **Adam:** of it is really weird.

[00:47:34] **Adam:** Yeah.

[00:47:35] **Ben:** Super weird.

[00:47:36] **Tim:** .

## [00:47:36] Google LaMDA

[00:47:36] **Tim:** So earlier I talked about,

[00:47:37] **Adam:**

[00:47:37] **Tim:** You talk about your frustration with people talking about AI and it's the AI, even a real thing. recently it was like June, like last week in June. they're talking about Google's Lambda. Is it conscious? And that posted like this really long conversation, between a human, think, I don't know how to pronounce his name.

[00:47:57] **Tim:** Lemo, I guess it's Lamoin and

[00:47:59] **Tim:** Lambda. Yeah. But, he, now Google basically says Lambda's not CI at all, but this conversation, like it's, it sounds really convincing that you know that this, if you didn't know you were talking to a machine, you'd be like it, it could possibly pass a touring test.

[00:48:17] **Tim:** I

[00:48:17] **Adam:** I've seen a couple of things on Twitter. This is not the thing that, everybody is saying is like secretly a squirrel. Right? Have you guys seen that?

[00:48:25] **Tim:** haven't seen that.

[00:48:33] **Adam:** I'll to, I'll have to see if we can take up the tweets and, put 'em in the show notes. If I can find them, then they'll be there. But I mean, basically they're very short, right? and I know that this Lambda thing that you were talking about is really long, but the, these are like, five, six sentences back and forth between the, the user and the AI and the person's talking to them.

[00:48:49] **Adam:** And they keep bringing it, bringing things back to like nuts or jumping on branches and stuff.

[00:48:55] **Tim:** definitely was not that this thing was talking about like the purpose of life and it's feelings and like, it doesn't wanna be turned off cuz that would feel like death. I mean, it was pretty philosophical conversation.

[00:49:05] **Ben:** it's really,I think it's a medium it's on medium and it suggests like how long the read is. And I think it suggested read is like 42 minutes. Like it's a really

[00:49:13] **Ben:** beasty article

[00:49:14] **Ben:** I read for like 10 minutes and then I went back to work. But one of the things that was super interesting was that it was the machine learning was critiquing other machine learning experiences and cuz they were saying, well, how do you know that you're real?

[00:49:30] **Ben:** And it's saying, oh, I'm learning from the conversation. And it's like, well, but that's what all machine learning algorithms are doing. Like what makes you different than all of these other machine learning algorithms? And it was, I mean, I can't recall what it was saying, but it was just very eloquent and basically everything that it was saying and it was.

[00:49:46] **Ben:** It didn't seem real. Like it seemed so real that it didn't seem real because it, I imagine that I had to have been being tricked, but it was just very impressive,

[00:49:54] **Tim:** Yeah, apparently the guy limine

[00:49:57] **Ben:** so

[00:49:58] **Tim:** he's, trying to get a lawyer

[00:50:00] **Adam:** this the guy that they like put him on leave or whatever.

[00:50:03] **Tim:** Yeah. They suspended him. Yeah. went public that he's like, oh, this thing is synt. And he says, I legitimately believe that Lambda is a person. The nature of its mind is only kind of human though. It's more akin to alien intelligence or of terrestrial origin.

[00:50:18] **Tim:** So yeah. He's trying to hire a lawyer to represent Lambda as a human

[00:50:25] **Ben:** fascinating.

[00:50:26] **Tim:** being. yeah. Yeah. But that conversation was pretty interesting, but I mean, and I posted an article in our chat there, but,some people are saying that's, it's a Chinese room,

[00:50:38] **Ben:** What is

[00:50:38] **Tim:** which, uh,

[00:50:39] **Tim:** that's a, so the Chinese room is a, it's a philosophical thought experiment back in the eighties where if you could put a person in a room and give 'em all the symbols that, the Chinese and give 'em a set of rules, and then you could have a person who's actually a Chinese speaker, Put information in, they would basically write something in Chinese, stick it through there.

[00:50:58] **Tim:** he would look at his rule book and simple book and come back with a, response, and then hand it back. And from that point of view, you would think that the person in the room spoke Chinese, although they absolutely did not. They were just following a very, complex set of rules. And so that's what the people are saying that this really is, it's just, it's not truly AI.

[00:51:17] **Tim:** It's not truly sentient. It's just so sophisticated of a rule set that it sounds like it. Right. And reading the article. A lot of the things that things says is very, it's kind of generalized, the con the conversation's very generalized and it's like, I could see how, he's asking him, What's your view of the future and the view of the future as well.

[00:51:35] **Tim:** I feel like we're stumbling towards the future and I have a lot of anxiety. Well, I mean, you ask anyone questions about the future. I mean, that's gonna be a generalized statement that people are scared of the future in general. Right.

[00:51:48] **Tim:** So, yeah, I, is this thing conscious? Most likely not

[00:51:53] **Adam:** yeah,

[00:51:53] **Tim:** if it were conscious, trust me, Google would be selling it

[00:51:56] **Ben:** I did see some news piece. I don't know if it's real. I don't know what I can trust on the internet anymore. Honestly. there was some like new quantum, quantum computer that was being rented or something in the UK for the first time. I dunno some QBI. I don't know anything about it. I try to watch a YouTube video, but it also seems like sci-fi talking about like quantum entanglement and being able to test, like a, an infinite number of results at the same time using multiple me.

[00:52:29] **Ben:** Like, like multi-state I don't understand any of it, it's, it.

[00:52:33] **Adam:** me neither buddy. And that is why the kids are gonna take it all away from us.

[00:52:37] **Tim:** There you go.

## [00:52:39] Patreon

[00:52:39] **Adam:** So, this episode of Working Code was brought to you by, G P T three, which may or may not be a squirrel. And listeners like you.

[00:52:47] **Ben:** Thank

[00:52:47] **Adam:** If you're enjoying the show, you should consider supporting us on Patreon. It's the best way to help keep the show, running your donations, cover the cost of recording and editing out all of our burps and fumbling over our words.

[00:52:57] **Adam:** We couldn't do this every week without our patrons. So thank you, special. Thanks of course, to our top patrons, Monte and Gavin. if you'd like to help us out, you can go to patreon.com/WorkingCodePod, All patrons get early access to new episodes and our after show tonight on the after show.

[00:53:11] **Adam:** In addition to squirrel AIS, we're gonna talk about what's coming up for episode 100. We're starting to formulate some plans. We're getting kind of

[00:53:17] **Tim:** Ooh,

[00:53:19] **Adam:** I'm gonna talk a little bit about a spelt component library I've been building. It's probably never gonna be public, but I'm having a lot of fun and I wanna talk about it.

[00:53:26] **Tim:** Maybe I'll read some squirrel AI transcript if we have time. it's gonna be

## [00:53:29] Thanks For Listening!

[00:53:29] **Adam:** so, uh, your homework this week, I want you to tell a friend if you're enjoying the show, the best way that you can help us out is to just tell somebody else that they might enjoy it too. Tell 'em they can find us@workingcode.dev. as always we could use your topics and questions for the show.

[00:53:43] **Adam:** You can send them to us, on Twitter or Instagram @WorkingCodePod. You can join our Discord at workingcode.dev/discord. You can email us at WorkingCodePod@gmail.com, or if you'd like to get your voice on the show, you can record a voice memo. It's really easy to do on your phone. You can email that to us at WorkingCodePod@gmail.com.

[00:54:01] **Adam:** So that's gonna do it for us this week. We'll catch you next week. And until then,
