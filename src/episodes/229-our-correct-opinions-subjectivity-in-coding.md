---
title: "229: Our Correct Opinions, Subjectivity in Coding"
description: "In this week's episode, Adam, Ben, and Carol dive into the nuanced world of software development as they explore the subjectivity inherent in coding."
date: 2025-09-04
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/229-our-correct-opinions-subjectivity-in-coding/id1544142288?i=1000724966180"></iframe>

In this week's episode, Adam, Ben, and Carol dive into the nuanced world of software development as they explore the subjectivity inherent in coding.

How do personal preferences, team cultures, and individual experiences shape the way code is written, reviewed, and maintained. From debates over naming conventions to the art of code reviews, we unpack the many ways that subjectivity influences technical decisions and the collaborative process.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/229-our-correct-opinions-subjectivity-in-coding.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** And my subjective take on programming generally I get a bad feeling in my tumtum when we use a technology to solve a people problem.

[00:00:11] **Adam:** I'll give you this. Ben, you on this particular topic, you are consistently wrong. Over the years?

[00:00:19] **Ben:** I'm nothing is not consistent. I think that's a virtue.

[00:00:23] **Adam:** yeah.

## [00:00:43] Intro

[00:00:43] **Adam:** Okay, here we go. It's show number 229. And on today's show we are gonna talk about subjectivity and its many ugly heads. but first, as usual, we'll start with our times and fails. Tim's not able to be with us tonight. He's still recovering from Dragon Con. Hopefully that is good.

[00:00:59] **Adam:** Good news means he had a good, uh, time. We'll see.

[00:01:02] **Carol:** peopled

[00:01:03] **Adam:** sure we'll we'll get the update next week when he is back, but, until then you get us. and it looks like it's my turn to go first, so I'm gonna go first.

## [00:01:11] Adam's Triumph

[00:01:11] **Adam:** and I'm gonna start us off with a triumph. So I, I think it was either yesterday or today as we're recording this, was our company's 21st, anniversary or

[00:01:21] **Ben:** Holy cow.

[00:01:23] **Carol:** Wow.

[00:01:23] **Adam:** Uh.So our company can drink now, which is good. the, and, and sort of as a minor celebration, my boss and CEO Steve, posted an announcement in our products just so that the customers that are using it today would see it. and he just told a little bit of the story of the company and the, the company's 21 years old and our product where he was posting these announcements is 10 years old.

[00:01:49] **Adam:** and, which was cool. We, you know, I, I, I read the, the post and I was like, cool, good job, nice thing, whatever. And then, like midday, we get an email that he forwarded onto us. So one of our customers had, sent him an email directly and he shared it with the rest of the team. But it was just like.

[00:02:09] **Adam:** Congratulations. Right? Like it was a, there was just like a nice little happy birthday. Think, you know, there's an image in it of a cupcake in front of a laptop or whatever, right? It just, it's, it's very cheesy, but the, the, and it, and it's just like two or three sentences, just, it's just a nice little genuine, heartfelt statement of their appreciation for what we do.

[00:02:31] **Adam:** And that, you know, we don't, they know that they don't always make it easy or whatever, you know, just like being, I, I don't wanna read it, you know, it feels a little impersonal or something, but, you know what I mean? So it was just, it, it, it felt real good. He forwarded it to us and I was like, I, I replied with the, the emoji of the like guy with the smiling and the one tear.

[00:02:50] **Ben:** Nice.

[00:02:51] **Adam:** it made me feel good.

[00:02:52] **Carol:** So how long have you been there?

[00:02:54] **Adam:** 13 years and change. It was 13 years in March, so coming up on 14.

[00:02:59] **Carol:** So you've been here for this whole product then?

[00:03:02] **Adam:** Oh yeah. I wrote the first lines of code I named the company. before this we were, counter March Systems, which was like a band geek, word counter. March is a command. You were a band, a marching band mom, right? Carol?

[00:03:16] **Carol:** I was a band mom, but I don't know what counter, what'd you call

[00:03:19] **Adam:** So Counter March, it's like the command where they, they give it and the everybody turns around.

[00:03:24] **Adam:** It's like turn

[00:03:25] **Ben:** Ah, okay.

[00:03:26] **Adam:** But, and, and, and so, and Steve was a band geek. He played saxophone and so I guess that's where he got the idea for the name of the company. We were for a long time, pre me, he was just counter March systems, for consulting or whatever. He had other people come and go working for him.

[00:03:42] **Adam:** But then I joined and then a couple of years later we came up with this product. And then maybe a year or two after that, we decided to start doing business as DBA, like officially counter mark systems, DBA alumni Q And then shortly, I don't know, I don't know how long after that. At one point it just kind of became like, okay, the company is now alumni Q.

[00:04:02] **Adam:** But,

[00:04:03] **Carol:** that's really cool. It's cool to be like part of something from the get go.

[00:04:07] **Adam:** it is, and it's also one of my greatest regrets. never, ever, ever name anything after a port manto, if you want people to pronounce it correctly.

[00:04:15] **Carol:** So how do they pronounce it?

[00:04:17] **Adam:** We, yeah, we get a lot of alumni iq, alumni, and new and surprising ways to piss me off

[00:04:27] **Ben:** aluminum.

[00:04:29] **Carol:** Yes, one's good.

[00:04:30] **Adam:** yeah, I don't know. But anyway, that's what I got going on.

[00:04:33] **Adam:** How about you, Ben?

## [00:04:35] Ben's Failiumph

[00:04:35] **Ben:** I'm gonna go with a little bit of a fum, which is that I have been, I think I mentioned this on a previous episode. I've been working on a little side project just to keep my brain active. I'm building this little, poems authoring app, and I've been mostly focusing on some of the core logic and now I'm stepping back and I'm trying to do some of the, the CSS design work.

[00:04:57] **Ben:** 'cause right now it's all just gray scale. A lot of stuff isn't even laid out and,

[00:05:03] **Adam:** what you're saying is in three years, apple is gonna steal this look for the new iOS and

[00:05:10] **Ben:** the, the, the apple glass will swing way back the other way to just monochromatic again, hard lines.so the, the failure is that I am really struggling with some of the CSS stuff because I'm trying to come up with something that is reusable. Like I'm trying to create a very small design system, and I'm realizing that naming things is one of the hardest things in computer science.

[00:05:34] **Ben:** And it's not just that naming things is hard. I don't understand the philosophy of naming things within a design system. So, for example, if we look at something like Bootstrap CSS Bootstrap, they'll have things like primary and secondary and tertiary. And outlined and H stacks and V stacks. And part of me thinks that should I bring some of that notion into my design system?

[00:06:04] **Ben:** But then the reality is, is they're building a design system for other people to use. And I'm building a design system just for me. And so I don't have a good underlying way to think about how I want to name things based on what they are in the application. And a very concrete example is at the bottom of every form, I almost certainly have some sort of a save button and some sort of a cancel button.

[00:06:29] **Ben:** Now in bootstrap parlance, that might be a primary button and a secondary button or a primary button and an outline button for the cancel. But do I want to call it primary or do I want to call it save? Because it will like always be the save button. Or do I want to Yeah, like the cancel button will always be the cancel

[00:06:51] **Carol:** Yeah. I know that feeling.

[00:06:53] **Adam:** I mean, we're getting right into today's

[00:06:55] **Carol:** I

[00:06:55] **Ben:** Yeah. Yeah.

[00:06:56] **Adam:** but the, I think the, the thought process is like, primary means primary action on this page, right? So save would be the primary action on that

[00:07:04] **Ben:** yeah, so, so that's, so

[00:07:05] **Adam:** if you're looking at a, like confirm, delete, then, but it, the primary action is confirm the deletion, then

[00:07:12] **Ben:** right. So that's where I'm struggling. So I call this a failure because I think the triumph part of this is that I am trying to embrace sitting in that discomfort, in the world of ai. A lot of what people are talking about is that our ability to sit, not just ai, but in the world of TikTok and short form video and, and doom scrolling through Facebook, we as a people are becoming less comfortable with attention.

[00:07:42] **Ben:** You know, applying our attention to something and sitting in the discomfort and feeling pain and trying to work through that pain. And, and so the triumph part of this for me is that I'm sitting here in the discomfort of not knowing this stuff. And I could just as easily say, you know, what f it, I'm gonna just use Bootstrap.

[00:07:59] **Ben:** I'm just gonna like copy most of bootstraps names. I'm just gonna use that. I'm not gonna think about it and I can move forward. And that in and of itself would have value for sure.

[00:08:07] **Adam:** Mm-hmm.

[00:08:08] **Ben:** But the idea that I'm sitting and stewing and I'm vet vetting and I'm hand ringing and I'm, and I'm asking Chachi PD to help me think through some of this stuff, I think that is a triumph in and of itself because I'm, it is very uncomfortable for me and it makes me feel dumb.

[00:08:24] **Ben:** I mean, if I can be completely transparent, it makes me feel stupid that after 25 years in this industry, I'm stuck on how to name CSS classes. Like that makes me feel like an idiot.but I'm, I'm okay with that for the moment because I'm, I'm enjoying the sweat of it.

[00:08:41] **Carol:** Well, you're definitely not stupid. I will.

[00:08:43] **Ben:** so, so hard.

[00:08:45] **Carol:** My, my worst days at work when it's not dealing with some stupid people. It's dealing with CSS, it's dealing with styles. It's trying to make a button look right. It's figuring out where that should be at, like, how do I get it to look like something else or make the customer happy and think through like the psychology of what a person thinks of when they're pressing a button.

[00:09:06] **Carol:** I'm like, no, this isn't for me. Put me back in, like, creating the action for what the button does. I don't wanna be the one designing it. We need more people.

[00:09:16] **Ben:** I hear you. It is definitely a totally different world of naming problems

[00:09:21] **Carol:** No, I,

[00:09:22] **Ben:** It seems so much easier to name things 'cause I'm so used to it.

[00:09:25] **Carol:** and I make my names very long. Like I don't care if it's like 50 characters long. Like you're gonna understand that this is the action you take when I want to delete a number. Like you're gonna know exactly what's happening based off the variable name. Or like how I name something. But, I always tell people, I'm like, I'm so bad at naming that I name my kids the same thing. I gave, I gave 'em the same first name and said someone else deal with the second problem. Yeah.

[00:09:52] **Ben:** So that's me. Carol, what do you got going on?

## [00:09:55] Carol's Triumph

[00:09:55] **Carol:** Well, I'm gonna say this is a triumph, but it might turn out to not be a triumph. I'll let you know next week. I've gotten kind of behind on my depend bot updates because I need to review them and make sure my packages like actually work and they're no breaking changes. I might have just went through 47 pull requests today and close 30 of them because they were all minor versions, so I just assume they're fine.

[00:10:22] **Ben:** Yolo,

[00:10:24] **Carol:** I pulled in my local and ran it. All the tests work, so if everyone wrote all their tests correctly, we're good, right? Like I shouldn't stress too much, so I'm pretty sure I'm winning by just applying all the dependent bot suggestions for all of our package updates. But we'll know next week.

[00:10:41] **Ben:** I'm very impressed. I, I don't know if I've ever once in my life looked at a depend bot alert.

[00:10:48] **Adam:** Oh my goodness.

[00:10:49] **Carol:** dare you. Yeah, no, I went through and I basically reviewed and if it were minor, like a minor change and I was like, all right, cool. It's minor. Chances are this is a, a popular like new get package we're using, like these are all big name stuff. I was like, they're not gonna do a braking change and a minor update.

[00:11:07] **Carol:** Everything's gonna still function, it's gonna be bug fixes or things to improve it, not a braking change. So anything that was a major, I didn't apply those. I'm gonna go back and actually look at what the changes are and make sure there's no braking changes before I applied them.

[00:11:20] **Ben:** Yeah. Well it's very exciting and I really hope it works out.

[00:11:24] **Adam:** Yeah. Good luck.

[00:11:26] **Carol:** too.

[00:11:28] **Ben:** But I mean, dependency management could be its whole, whole other

[00:11:31] **Carol:** Oh, it could be. And the lack thereof. Yeah. Just, so I'm looking at, right now we use Pro get for all of our package management. and it's like, we have our own server. So we manage all of the connections. Like we handle everything. It's internal, so all of our package repositories inside, we are looking at moving to GitHub packages.

[00:11:52] **Carol:** So I wanna move us off of Pro get and off eventually off of Octopus Deploy as well as well. And just into GitHub actions and GitHub releases and do everything from there. So down the road I would love to have a conversation about that as well. 'cause that's gonna be a fun adventure, I think.

[00:12:10] **Carol:** Like an actual fun, fun adventure I wanna do.

[00:12:12] **Carol:** Yeah.

[00:12:13] **Adam:** Yeah. I mean, we use GitHub packages. I, I don't know if there's enough to say there to like make it an episode, but I'd be happy to have a conversation with you to talk to you about how we use it and stuff.

## [00:12:24] Subjectivity in Coding

[00:12:24] **Adam:** Cool. Well, let's get into all of my correct opinions and. We'll talk it out and tell everybody how they're doing everything wrong.basically the idea for today's show was just, you know, we talk about so many things in development, in coding, and at the core, not everything, but like, you know, kind of everything is deeply subjective.

[00:12:47] **Adam:** and there are times when you can make an argument that actually something that seems subjective at face value does have a, a deeper meaningfulness, is that a word? Is,

[00:13:03] **Ben:** it is. Yes.

[00:13:05] **Adam:**

## [00:13:05] Tabs vs Spaces

[00:13:05] **Adam:** like for example, my, my everybody's favorite tabs versus spaces, and my favorite argument about it being an accessibility issue, you know, that we, we've rehashed that or we've, we've hashed that in the past, so we won't rehash it here.

[00:13:19] **Adam:** But, yeah, just like

[00:13:22] **Ben:** Well, actually okay, not to harp on tabs versus spaces, but, but, but something No, no, no, because I, I have to edit a lot of files that happen to be spaces. Our, our code base at work is a, conglomerate of different styles, and there are people who love to set their editor to two spaces or, or sometimes four spaces.

[00:13:43] **Ben:** So it's not even obvious when you're quite looking at it. But, but what I've noticed, and this is gonna be dovetailing into a small tangent, when one of the nice things with tabs is that when I go to select a bunch of text. There's a lot of wiggle room in, in terms of where I can initiate that mouse movement because if, basically if I click anywhere within the space of that tab, it's gonna highlight the next non-space character.when things are all indented with spaces, if I'm just a hair to the left of where I meant to click, I'm probably gonna get one or two actual space characters included in that highlight so that when I paste, I might accidentally paste an additional space in front of where I meant to have characters.

[00:14:28] **Ben:** Okay.

[00:14:28] **Adam:** Speaking of, of crimes, as we did last week.

[00:14:31] **Ben:** so, okay, so this is not about taps and spaces and, and I think this comes into the subjectivity thing. One could say that what I just described is not a problem because the linting should format your file anyway. And my subjective take on programming generally is I. I get a bad feeling in my tumtum when we use a technology to solve a people problem. And what I mean by that is that we're using tools to solve attention to detail or lack of attention to detail. And that feels very like, I feel like we're, I feel like we're allowing people to act poorly because the tools will, will fix their deficits.

[00:15:21] **Adam:** I'll give you this. Ben, you on this particular topic, you are consistently wrong. Over the years?

[00:15:29] **Ben:** I'm nothing is not consistent. I think that's a virtue.

[00:15:32] **Adam:** yeah. I mean, I, I think the, your thesis is admirable. you know, it's a, you're saying at its core, it's a people issue and an attention to detail issue.but where I come down on it, on using a linter to enforce, okay, we use tabs or we use four spaces, or we use 17 spaces or whatever, is nothing is worse.

[00:15:55] **Adam:** Absolutely nothing is worse in coding than opening a file that, like part of it is indented with two tabs. Part of it is indented with four, four spaces, I meant to say spaces, two spaces. Part of it is indented with four spaces, and part of it is indented with tabs. Like, at the very least, what I want. Yeah.

[00:16:13] **Adam:** Yeah. What I want is if you're gonna make a change in a file, your editor should be set to just auto, like reformat the whole file. If, if you're gonna be that guy that's gonna use two spaces when the team has agreed on four, then at least make that file consistent with itself. And, and, and there are editor settings to do that, and there are people who will go unnamed, in my, oh God, what do say, what does that PostIt you're holding

[00:16:40] **Carol:** Yeah, so just so you're aware, on the corner of my monitor I have, the shortcut in Visual Studio for when that happens. It's Control A, so select all of the file control krl D and it formats the entire file for me how I want it, so then I don't have to deal with spaces and tabs and everything all messed up.

[00:16:59] **Carol:** So then I immediately just commit that and then go back to working.

[00:17:03] **Adam:** Yes. Yeah. And, I mean, that's another good thing. That's again, like, maybe subjective, maybe not, but like, if you're gonna make white space changes, make that its own commit.

[00:17:12] **Ben:** Yeah, I, I agree. Plus one.

[00:17:17] **Adam:** but yeah, like there, there's editor settings to say, okay, if I'm, if I'm changing this file, then either be consistent with the spacing in it or apply my spacing to every line.

[00:17:30] **Adam:** Either way would be better than committing three different types of indentation or more. well, okay. There is one thing that's worse than that, and that is total lack of any thought about indentation at all. Some, some stuff is not indented. Some stuff is like outted past where it should be, right? It's just not indented at all when it's, you know, it's the children of a div tag or whatever.

[00:17:52] **Adam:** Yo, sometimes I open up a file at work and there'll be like five line breaks between code. I'm like, what?

[00:18:00] **Carol:** Why? Yeah,

[00:18:02] **Adam:** Yeah. Yeah. I'm like, show me on the doll where the white space hurt you.but to, to, to circle back, the thing, so you said using technology to solve a people problem. And I, I do think that it's using technology to solve a people problem, but I think it's for the better. I think it is, it, it's making it no longer a people problem.

[00:18:25] **Adam:** It's, it's just not a problem. Now we're, we're pissing everybody off equally, except the one person who wrote the style guide. Mm-hmm.

[00:18:33] **Ben:** And I think there's something too about when you apply those, like when linters run, right? Like you learn from your mistakes. So after a while you get tired of it. So you start doing it the correct way. And maybe the correct way is my way and not your way. But we've agreed to these style guys, like we've agreed to what we're gonna do.

[00:18:50] **Carol:** So just a, just do it, you know.

[00:18:52] **Ben:** you, you would actually be very, I know we're like now, definitely on a tangent, but you would actually be proud of me at work. I did try to include a formatter. For cold fusion, there's a, a, a command box plugin, I think called CF format.

[00:19:08] **Adam:** Mm-hmm.

[00:19:09] **Ben:** And I tried so hard for a couple of days to get it to work right, and there were just too many weird little edge cases where it was just breaking enough that I couldn't use it anymore.

[00:19:21] **Ben:** And it would be something like, if a tag has three or fewer attributes, put it on one line. And if it has more than three attributes, put an attribute on each line, which is it? It's like at first like, oh, this is so great. It's formatting all the stuff. And then suddenly I have a CF param tag that uses the pattern attribute for regular expression validation.

[00:19:43] **Ben:** And like it's just too long. And now I have four parameters that are all single line, and then a fit parameter that has five attributes spread across five lines. And I'm like, that's it. I can't use this formatter anymore. Like, that's enough for me to just, I, I just, I, I don't wanna fight the machine when I don't think the machine is on my side sometimes, but anyway.

[00:20:04] **Adam:** shall we move beyond tabs versus spaces? Okay. Well, what do you guys wanna talk about next? Mm-hmm.

## [00:20:09] MySQL vs MSSQL

[00:20:09] **Ben:** Well, I was gonna say that this subject has been top of mind for me because I have been using MySQL as a database engine for, as like the last 15 years or so. And at work we now use SQL Server and I have always looked at databases, kind of like how people describe programming languages, that they're probably mostly the same.

[00:20:34] **Ben:** They probably have mostly the same functionality. It's probably just slightly different syntax. And with SQL, I thought it would be even more so the case because there is a core standard SQL feature set that all of the databases handle. The problem is, is in the last 15 years, I never had perspective on what the core features were.

[00:20:56] **Ben:** And so what I'm now realizing when I use mssql is it, it's like wildly different.to the point the other day where I spent like, I, I feel like it was four hours or something ridiculous trying to add an identity column to an existing SQL server table. And I kept asking chat GPT, like why can't I get this to work?

[00:21:19] **Ben:** And the database wasn't giving, it was like, gimme a syntax error. And I kept asking it like, what's wrong with it? And just kept telling me to try this thing. And I kept trying. It kept, gimme a syntax error. And then finally it was just like, oh yeah, you can't add identities to existing column, to existing tables.

[00:21:33] **Ben:** You have to do it on the initial table create, or you have to drop the table and recreate it with the new identity in place and. there's like, there's, that's like bonkers. I don't know how the database has lasted that long and people haven't rioted over that fact alone.but the, okay, so, so bringing it back to the subjectivity, one of the real pain points with SQL Server to me, and this is where the subjectivity comes in, is that you can't just arbitrarily add a column in your schema definition.

[00:22:03] **Ben:** So with my sql, you could say add created at daytime after updated at kind of a thing, and it would do it in that schema. My

[00:22:12] **Carol:** It's just too fancy. That's

[00:22:13] **Ben:** too fancy Ms. SQL server's. Like, no, you gotta put it at the end no matter what. And I don't think I realized just how strongly I felt about the order of columns in the schema definition itself.

[00:22:28] **Ben:** because you could say, well, it doesn't matter what the order of the columns in the schema is when you select columns. Out of the database. You can use them however you want in your programming context. You could, even in your select statement, you could put the columns in any order you want, that whatever makes you comfortable and that's how they'll, you know, you can, you pull, pull back.

[00:22:46] **Ben:** The database doesn't care. But the application isn't the only context in which I consume the database. I often have a database gui open a graphical user interface where I'm clicking through the database objects and I'm looking at the schemas and I'm running arbitrary queries. And the fact that there is no rhyme or reason to the order of the columns in the schema seems like that would be a deal breaker for me.

[00:23:10] **Ben:** Like, I, this is no longer a database I can use.

[00:23:13] **Adam:** there is a reason, it's just not a good one,

[00:23:16] **Ben:** I

[00:23:16] **Carol:** reason?

[00:23:17] **Adam:** that the column was added later

[00:23:19] **Carol:** Oh yeah. That's the reason. Yeah.

[00:23:21] **Ben:** that's not good enough.

[00:23:22] **Adam:** Yeah.

[00:23:23] **Ben:** So it's one of those things where clearly people love Microsoft sql. it's used in a tremendous number of massive enterprises.

[00:23:32] **Carol:** Enterprise loves it. That's the key word.

[00:23:34] **Ben:** Like, so again, it's one of those things where it's subjectively, I, that would just, I, I don't think I could do that if I discovered that in a personal project and that and, and I, I was like, oh, I can't add columns to the end of the, OR to anywhere in the schema. I'd be like, okay, I have to look for another technology.

[00:23:49] **Ben:** Then that's clearly like I have other databases to choose from. This is a deal breaker.

[00:23:53] **Adam:** yeah.

[00:23:53] **Carol:** So I, I was raised on mssql, so I only spent a very short amount of time on anything else. And I think it was Oracle, right? And I was like, I don't understand how you write these queries. And then I left Clear Capital back to Mssql. So for me, like it's never been something I've considered. The only time I notice it is at the end of all of our tables, we have a column that's like our data warehouse, last modified date. I notice it when I scroll to the right and suddenly there's. A new column, a new column, a new column, and I suddenly go, this shouldn't even be on this table. Like, we should never be making tables this big. Like we should be making like child tables of it, like related tables. We shouldn't just be continuing to add more columns.

[00:24:37] **Carol:** So, but I never thought about like having to scroll through because it's all I've ever done. Like it's never been, I didn't even think that you could do it with anything else. So.

[00:24:46] **Ben:** Well, so, and again, because I'm, I'm in every context, you're always bringing your own baggage, which is part of what makes everything so subjective and sticky. And one of the things that I continue to struggle with as a developer is how I want to think about my schema definitions. And what I mean by that is there are parts of your record that change over time, like people's names, but there are parts of the records that should never change over time, like the ID or the created at date or some other, What was the word you had last week, Adam? For not, not the natural key, the,

[00:25:23] **Adam:** Oh, the surrogate key or the,

[00:25:24] **Ben:** yeah.

[00:25:26] **Ben:** and so then I think to myself, should I, should I put all my kind of immutable data at the top of the schema, the IDs and the created ads and like the parent IDs, if it's a parent child relationship kind of thing.

[00:25:38] **Ben:** And then put all the mutable things at the bottom. For years, I put all of my keys at the top. So like my id, my parent id, my type id, my category IDs, and then below that would all be the kind of more free for me stuff. And then usually I would have that update and the create dates at the bottom. But like that, that was just something I learned.

[00:25:59] **Ben:** you know, in the first year. It doesn't necessarily mean that it's good and I keep wrestling whether or not I even like that. I dunno. What do you, how do you guys order your columns? Or, or is it stupid to even think about it? Is it literally just as they enter your head, that's how you're putting them into the schema.

[00:26:13] **Carol:** Yeah. So for me, if I'm designing something brand new, I try to put it in a logical order. So I do my ID first, and then like you said, I do my key information, right? Like, what is this of, like, what type is this? Those things I need. And then like the description, the the information that goes with it, whatever it is.

[00:26:29] **Carol:** And I do the same thing, the dates at the end, but once it gets committed, I never think about the order again. Or if I, or if I'm adding a new column or if I'm changing the model, I don't think about where it's gonna live in a table. I just go, is it in the right table? And does it make sense for this data set?

[00:26:46] **Carol:** I no longer consider the structure.

[00:26:49] **Adam:** Hmm. Yeah. I mean, I, I don't know that I would, would lose sleep over not being able to add columns in the middle. I think if it's that important to your process of like digging through the data, you could add views that order the columns however you want

[00:27:04] **Ben:** that's, that's something that Chat GPT suggested. They're like, just make a view.

[00:27:08] **Carol:** But don't forget, every time you update a table, you have to update the view. 'cause they don't automatically update themselves with Ms. Sql. So

[00:27:17] **Ben:** what, and I think part of the problem, and again, this is a subjectivity thing about data architecture, I think part of why I'm struggling with it at work is because we have very wide tables, like 40, 50 columns, which to me is extremely

[00:27:30] **Carol:** huge. Yeah.

[00:27:31] **Ben:** Yeah. And, and I, my lack of familiarity and just the size of the tables, it's a lot of scrolling.

[00:27:37] **Ben:** Personally, I would love to have tables that have 5, 6, 7 columns and then it's, it doesn't even almost matter what the order is because they're all in eyesight.

[00:27:46] **Carol:** visible. Yeah.

[00:27:47] **Adam:** Yeah. I mean, so to answer your question, I do similarly try to group related fields, right? So if we're talking about like, you know. The type of credit card it is and the last four digits and the billing name on the card. Right. Those are things that you're, if you're gonna look at one, there's a good chance you're gonna look at all three of those things.

[00:28:05] **Adam:** and so I put them next to each other, but, like Carol, if the tool, if it's a limitation of the tool, I, it just doesn't tend to get under my skin. I'm like a, I'm a surface level guy, right? I, I just let stuff roll off my back and I move on to the next problem. Mm-hmm.

[00:28:22] **Carol:** And I think the other thing that helps me is I'm never a, okay, when I'm looking at data, I may do select star sometimes, like gimme the top 100 rows of something. But if I'm writing in the application or I'm actually like trying to find something, I always put my column names. So it's not very often that I'm looking at the entire like width of the table.

[00:28:42] **Carol:** When I am, when I'm looking at data. At very, very specific elements of it.

[00:28:47] **Ben:** Yeah, that's fair. I, I, I, I do spend in a traditional application, I do spend most of my time in the code, because I'm getting familiar with this app. There's a lot of looking directly at the database being like, what's this, what's this column for? And then looking across rows to see if I can discern from the relationship across rows what's something might mean, or whether it's meaningful at all, or,

[00:29:10] **Adam:** Yeah. All right, let's, let's move on from database schema.

## [00:29:13] HTML Attribute Ordering

[00:29:14] **Adam:** So, another one we had kind of talked about before we turned on the mics was, attribute order on HTML tags. So we are all web developers. Ben seems to take particular offense with class being first. Which, okay.

[00:29:29] **Ben:** It's, it's also like one of the newest attributes, you know, for years we didn't even have class.

[00:29:35] **Adam:** Oh, false. I mean, agreed that for, for years we didn't have class. However, one of the newest, I mean, Ben, we've got aria attributes, we've got data attributes, we've got all kinds of new additions in HTML five and stuff like, Hmm.

[00:29:54] **Ben:** true. I struggle with this a lot. I have, okay, I have general feelings, but, sorry, I don't mean

[00:29:59] **Adam:** you're, you're, you do, circa 2000 html.

[00:30:04] **Ben:** The, the, the, the general feeling that I have is, I like my, I don't even know how you would categorize these things. I like, I like my IDs and my types and my names. To be

[00:30:16] **Carol:** Hmm. Sounding like your tables again. Yeah.

[00:30:19] **Ben:** And then typically I'll have my, maybe data attributes. I don't have tons of data attributes, then I would typically have an interactive thing.

[00:30:29] **Ben:** My click handlers, my key handlers, and then I would have my class, and then I would have my style attribute. And my style attribute is almost always the last thing that you would possibly have, except for in JavaScript frameworks where you could have an attribute that controls the content of the element.

[00:30:47] **Ben:** So if I'm an Alpine, I could do like an X text or an X-H-T-M-L that actually populates the content to me, that'll be the very last thing, because it's literally controlling the thing that's right after it in the, in the code, the i. There, there. So again, going back to the idea that we didn't even used to have classes back in the day.

[00:31:06] **Ben:** So classes is a new thing. It's very just UI focused or like, like style focused. So to me to call it weak, I, I don't mean weak in like its usefulness, but it's, like the page works without classes. You know, you could go into a dom, rip out all the classes, and in theory you should more or less still have a working application.

[00:31:31] **Ben:** I'm not saying that that's true all the time, but like, you know, that's the dream.

[00:31:34] **Adam:** Yeah, so

[00:31:35] **Ben:** but like, you couldn't rip out the click handlers and necessarily still have a working application. You couldn't rip out the IDs and still have a working application if you have things that, like the aria described by and the label fours.

[00:31:46] **Ben:** So the idea that there's a lot of people who put class as their first attribute to me is just bonkers bananas because it's, it's like the least important of all the attributes

[00:31:57] **Carol:** It is not the least important.

[00:32:00] **Ben:** I'm

[00:32:01] **Carol:** it is determining like what they see, right? Like for me, I enjoy ID first. I will say that like if I have a choice, it's id. And if we're using a name attribute, then name goes next. Like if we're having to use that, that's fine. The only thing I like very last is any like JavaScript functions or anything that's running that would be like on click, do this or on error handle that.

[00:32:25] **Carol:** So I like those

[00:32:26] **Ben:** So you put your interactivity at the end?

[00:32:28] **Carol:** Yeah. 'cause then that's what I would look for last. 'cause that's where the problems usually are. My problems aren't in the rest of it. It's at the very end of the element,

[00:32:36] **Adam:** huh.

[00:32:37] **Ben:** All right. I

[00:32:38] **Adam:** So I, I, I kind of have. Two different ways that I think about this. And it, it's very context dependent, right? So I have some apps, my more modern stuff that's using like Svelte kit and Tailwind. a I just tend to not have very many attributes that are not necessary for functionality, right? So like, I don't put a lot of IDs on things because I don't have to use IDs for styling.

[00:33:00] **Adam:** I, well, I, so ID for Yeah, yeah. Labeled by or, you know, uh,form label, for attributes and all that short of, you know, those are accessibility requirements. But short of that, you know, like it's pretty much just the tag and the class, right? Class for styling tag, for structure. And, I, if there's gonna be more, right?

[00:33:22] **Adam:** So if for some reason, I'm doing, some data attributes or whatever, I tend to, well, I guess that's kind of where we're getting it, is to two different contexts, right? So first context is very modern. Pretty much nothing but class. Class is there for styling structure for everything else. And then I don't have to do like on click or anything like that because it's, it's attached by the framework, right?

[00:33:46] **Adam:** I don't have to do the attaching myself.and so that it tends to keep the h TM L pretty tse, which I like a lot. and so I don't think about it a whole lot in that case, but in the cases where you do have four or five, six attributes on a thing, because they're necessary, I do tend to put class last specifically, but specifically because I'm doing tailwind and there might be 40 classes on a thing, right?and, and so like, yeah, I would, I, I personally would get really annoyed if it's class first with 40 different class names. So it takes up like two or three lines in the editor. if you're, if you've got like any sort of wrapping on, and then. Then you are, then you're looking for your data attribute or your ID or whatever after that.

[00:34:29] **Adam:** Like that to me would be very annoying.

[00:34:32] **Adam:** So,

[00:34:32] **Ben:** So, I don't know, I can't remember if Svelte has this. In Angular there was an attribute, and I think V has VF and Angular has NGF. You can give it an expression and it basically determines whether or not that entire node is rendered in the dom.

[00:34:48] **Carol:** Yep.

[00:34:48] **Adam:** it does not, it's not, it's not part of the DOM tag itself,

[00:34:51] **Ben:** wrapped around it.

[00:34:52] **Adam:** Yeah, yeah.

[00:34:53] **Ben:** Okay. So in angular, in view, you can have an attribute that determines whether or not that Dom exists, that dom node exists at all.

[00:35:01] **Ben:** And to me, going back to this idea of power, that is the most powerful attribute in that tire tag because it's literally the one that determines whether or not this tag exists. And oh my God, I can't believe how many times I will see people put an NG if as the very last attribute and the, and the tag. So I'm looking at this tag, I'm like, oh, what does this tag do?

[00:35:21] **Ben:** It has these classes. Oh, it has these click handlers. Oh, pretty cool, cool, cool, cool. And then I get to the end, I'm like, whoa, NG if, and then an expression. I'm like, this doesn't even render most of the time. Why did I just spend all this time reading it? It's, it's, it's, it's like the same to me, the mentality of, in Ruby.

[00:35:39] **Ben:** I believe there's, there's that syntax where you can say, do this unless something else isn't true. And I'm like, that's bonkers bananas. Why do I want to know the condition after the thing that I just read? That's nuts. But again, that's like just one of those things. It's just highly subjective.

[00:35:58] **Adam:** Yeah, I, I mean, this kind of dovetails onto what you were just saying a little bit, like, you know, the, with, if the, if is last, then you don't even, and, and it's a usually not included chunk of markup. That's a, it's a lot of wasted mental effort reading that tag to get there. For me, that doubles, dovetails nicely with guard, state guard statements versus single return principle or whatever it is.

[00:36:22] **Adam:** I think it's a, it is from clean code, if I remember

[00:36:24] **Ben:** Yeah. I think

[00:36:25] **Adam:** should only ever have one return statement. for me, man guard statements are where it's at, and, and that

[00:36:30] **Ben:** every day.

[00:36:31] **Adam:** guard statements for me are like the one place that I, I'm totally fine with an if, conditional without the curly braces,

[00:36:40] **Ben:** Oh, interesting.

[00:36:42] **Adam:** right?

[00:36:42] **Adam:** So normally you have to, like, if open parentheses condition, close parentheses, open curly braces, this is what you do. Close curly braces, right? same tactically you could just exclude the curly braces. if there's only one statement that is in the, the, here's what you do chunk. And that's kind of considered, I think in most circles in, in my perception of it, is that it is.

[00:37:06] **Adam:** considered a faux pa or a no-no. and I tend to agree because it's easy to make the mistake of, oh, I'll just hit and or here and add onto this, and then you're

[00:37:16] **Carol:** Now you're broken. Yeah.

[00:37:19] **Adam:** but I think guard statements specifically, like if you're, if you're doing like an early return or throw or something like that, then I'm totally on board, no curly braces, like, let's condense that code and also just pick like right on top of that.

[00:37:35] **Adam:** I, I've over the last several years have really developed this, preference for super descriptive variable names. I don't care if the variable name is 25 characters long. Like if that, if that's what's the space that you need to describe what is being indicated by this variable name, then use it. And I'll do like, you know, even if it's a relatively simple bit of logic, if it's like a three.

[00:37:58] **Adam:** Things that are being compared or whatever, I'll just do like, you know, this is what it represents, equals these are the, the, even if it's like, you know, 60 characters wide or whatever, just like not that much to say like, okay, this is, these are the conditionals, this is what I'm calling this condition. And then if condition return, like to me that's just like, that is the, the essence of what I consider to be clean code.

[00:38:22] **Adam:** Right? Super easy to read, understand what's going on, and just like move right past it if it doesn't apply.

[00:38:28] **Carol:** Agree.

[00:38:30] **Ben:** I along those lines, I will, I hate reading double negatives.

[00:38:37] **Carol:** They confused me.

[00:38:38] **Ben:** They con, they're confusing, they don't read well, and I have definitely before. Created an intermediary variable that is just like X equals not something so that I can then have a statement says if X, just because I feel like it's so much easier to figure out when that logic branch is gonna happen.

[00:38:57] **Carol:** Yeah, well we have this whole like, it's, it's a new thing, so it's not even like out yet. We have this concept of like a green red path. So red is the, you got the no, green is you got the Yes. However, if you read the logic, it goes completely backwards. So they're like, the way they explain it from the PO side and from the non-tech side, it flipped.

[00:39:19] **Carol:** So then now we have like green paths, which are like, does not match or is not in ratio, that's green. And I'm like, wait, what is not in ratios red? They're like, no. 'cause if they're in ratios, that's bad. And I was like, well, why'd you call it that? I was like, this is so dumb. I was like, I just need yes and nos.

[00:39:40] **Carol:** Yes and no.

[00:39:42] **Adam:** Yeah.

[00:39:44] **Ben:** Yeah. Naming stuff is just, it's just hard,

## [00:39:47] Class Method Ordering

[00:39:47] **Carol:** Can I, can I throw in the one, I don't know who wrote it in, but the, order of methods in the class.

[00:39:53] **Adam:** We've touched on this before, but it is very subjective.

[00:39:56] **Carol:** it's very right. So I like my public methods at the top. So my public are like, get the data, update the data, save the data, right? Like those public things. And then right underneath that are some special condition things like, oh, we need to check multiple permissions to know if you even can do this.

[00:40:13] **Carol:** So there are some canned statements that are also public, but then private go under the public and the private are the things that like should be grouped together by what they're touching. So I used to always put everything at the bottom for readability. So all of my commits, you would just see I went to the end, I went to the end of the file, and over time I've realized what I'm going through.

[00:40:36] **Carol:** It's kind of like Ben said, like looking at your column names in alphabetical order. You assume it's not there. I realized that when I was pulling things out like that, people get through a block of code and they go, oh, we haven't written this, or it's not there, so I'm going to do something kind of similar because they don't realize like, what's happening, gone down.

[00:40:54] **Carol:** So I tried like putting logic together with my private things.

[00:40:58] **Ben:** Kind of along those lines, and I'm sure I'm gonna rub some people the wrong way with this one. So, if you look at a cold fusion component, I think the vast majority of people will have their constructor at the top. And then, like you're saying, your, your public methods and your private methods. And oftentimes in the constructor, people will call.

[00:41:19] **Ben:** Methods on the class to set up, you know, initialize some values, possibly.and that makes total sense to me. And for years we saw that in the JavaScript world as well. There was often, I think this was misnamed, but people often refer to something called the revealing module pattern, where they would have, a function block and then they would execute that function block.

[00:41:43] **Ben:** And the first thing the function block would do would be to return the public API for that quote unquote component. And then below that, you had the functions that were public and or private. And the reason that that worked is because cold Fusion and JavaScript, they all do this thing called hoisting, where they will take those function definitions that are down below and they will hoist them up to the top of the function block so that you can return a function that isn't like quote unquote defined yet.

[00:42:12] **Ben:** Because it does this two paths. Compilation. Okay, so here's where I'm gonna rub people the wrong way. In the node world, I feel like a lot of people went crazy where they started having modules. They would define a bunch of functions at the top and then do some sort of an exports at the bottom.

[00:42:31] **Ben:** And I'm like, oh, why do I have to read through this entire file to figure out what this thing exports? The exports should be at the top. Now the problem with that coming in hard is that I think you can run into issues when you move to class syntax, where classes don't hoist like function definitions do because of the syntactic sugar compilation that's happening below the head with the prototype chain.

[00:42:56] **Ben:** But I just, I think that constructor, you should do whatever you can to make sure your constructor is at the top. And if the constructor logic is at the bottom, I feel like something has gone de deeply wrong.

[00:43:08] **Adam:** Hmm. That's just, I don't lose any sleepover. That

[00:43:11] **Ben:** I know, so, okay. okay. Sorry. Sorry. I'll, I'll defer, I'll defer.

[00:43:15] **Adam:** That's okay.

[00:43:17] **Ben:** okay. So, okay. Clearly I have deep feelings about stuff, right? I, a lot of this stuff to me is, is like, what did I intend? And a lot of the code is intentional. I put it there. I'm not saying that my reasoning is proper, but I have reasoning, you know, I've put some thought into this.

[00:43:35] **Ben:** I've tried to come up with a pattern that I wanna follow and I try to stick to it consistently.

## [00:43:40] Const vs Let vs Var

[00:43:40] **Ben:** and if I can burn some more sacred hamburgers here, the whole var versus let versus constant debate, I mean, to call it a debate is like, I called it debate. In my world, I think the world has moved on,

[00:43:54] **Adam:** Yeah.

[00:43:56] **Ben:** to me, I, the, the argument that when I define a variable.

[00:44:02] **Ben:** I can do cons because I don't want it to be changed. I feel like when I write that variable for the first time, it being immutable was never my intention. Like I didn't know that it wasn't gonna be reset later down in that function. If it turns out that that never happens, that's incidental, like that's coincidental.

[00:44:24] **Ben:** I called it a name and then I never changed it. Like, okay, that's just how this function happened to turn out. But that wasn't my intention going into it, so why would I ever change it from var? Like VAR was my intention.

[00:44:37] **Adam:** right. I, I think that speaks to what we were talking about, I think it was last week, where we were just saying like, you are not a functional programming brained person. Right.and, and FP is very much like all data should be immu.

[00:44:55] **Adam:** I mean, that's, it's probably not a hard and fast rule. I don't know.

[00:44:57] **Adam:** I'm I, I'm, I'm totally Kool-Aid list, here, right? I'm not drinking anybody's Kool-Aid, but, I do like to write a lot of FP code. And the pattern that I see is that very little mutation ever happens. It's always like, we'll modify or we'll return a new array that has is the exact same contents of the previous array.

[00:45:17] **Ben:** Array, like sorted the way that you requested or whatever filtered how you requested.so yeah. I can understand that if you're deep into functional programming and you are, you're, you're steeped in the Phil, Phil, Phil philosophy of it

[00:45:32] **Adam:** Philosophizing

[00:45:36] **Ben:** But again, it's like people who are not steeped in fp and don't necessarily think that deeply about immutability. I'm like, why did you just make a let or a cons, like, how did you know that that was gonna be true?

[00:45:48] **Ben:** And they're like, well, if it turns out not to be true, I'll just go back and change it to a let. I'm like, why? Like, like, just let the program show you what it's gonna do. I don't under it. So it's

[00:45:59] **Adam:** Well, so, I mean, for me it's a, it's a tool that I use to help me think through the problem, right? So I start out as constant, and then, and not only do I start out as cons, but you know, modern JavaScript, you've got block scope, right? So, if it's declared inside of a trica, it's not available after the try-catch closes, that sort of thing.

[00:46:20] **Adam:** So, you know, I, I, that's kind of become how I think about it, right? So I just, wherever I am, whenever I need the variable cons, X equals whatever, I, I, after I just gave my lecture about using 25 characters,

[00:46:32] **Adam:** if you need them, whatever, you get the point, declare dis cons, give it the name and, and use it.

[00:46:38] **Adam:** And then maybe in 20 lines, I, I need to modify or my, my. Instinct is to modify it or, or I need it somewhere outside of that current scope, then that's like, okay, it, having the IDE errors tells me like, oh, hey, the way I initially assumed I was going to use this variable was wrong, and so now I need to move it, or I need to change it to something mutable if that's how I wanna work with it, or whatever.

[00:47:03] **Adam:** But it, it gives me that, that moment of just like, Hey, it's time to check in and check your assumptions because you were, you know, my default programming mode is kind of FP ish, very

[00:47:16] **Adam:** like immutable.

[00:47:17] **Ben:** I, think if you can, if you can make the argument and, and it sounds like you're making a valid argument, that your actual intention is that you don't want to change these values. That makes sense. My intention is just that I wanna define a variable. Like I literally don't think about it any harder than that.

[00:47:33] **Ben:** If I then have to reuse that variable, that's not a red flag for me. I'll just, I'm like, okay, I'll just reuse that. In fact, I will, oftentimes,

[00:47:40] **Carol:** reuse that.

[00:47:41] **Ben:** I'll have an if else block where I declare the same variable in both blocks, you know, if,

[00:47:48] **Carol:** No,

[00:47:49] **Ben:** and such, then VAR user equals this else, VAR user equals this other

[00:47:53] **Carol:** no.

[00:47:53] **Ben:** because I know it gets hoisted and like, I don't care that it, you know, it's gonna be user after the if else block.

[00:47:59] **Ben:** That's like, that was the intent is to define that user.

[00:48:03] **Adam:** Yuck.

[00:48:04] **Carol:** no. I wanted to find ahead of time, please. I wanna understand like where we started at and where it went. Not having to like figure out which path it took to get there. Like, I wanna like know, like, okay, at what point did it change? Yeah.

[00:48:18] **Ben:** I hear you again, it's all very subjective.

[00:48:21] **Carol:** I would hate reading that. Like I would be annoyed.

[00:48:24] **Ben:** What else we got here?

[00:48:27] **Adam:** So we just, we kinda talked about let versus cons versus var on that one.

## [00:48:30] Trailing vs Leading Comma

[00:48:30] **Adam:** what about like, trailing comma, or in my, my personal preference? So I, I grew up with a personal preference for leading comma, right? So if you're talking about like selecting a bunch of columns in a SQL statement or like a bunch of objects, a bunch of properties in a JavaScript object, that sort of thing, you know, they're all,one new line for each column in the select statement.

[00:48:51] **Adam:** One new line for each property in the, the object and or in an array two. And, okay, so you skip the first one 'cause you don't need a comma before the first one. That implies that there's something before it. But after that, then you have like basically a vertical column of commas in your IDE. And if one of them were to go missing for some reason, then it's like staring you in the face.

[00:49:10] **Adam:** It's like, Hey, hey, here I am, I'm missing a comma. That's what I loved about that. And, and so like, I, I convinced a number of people that leading comma was, the way to go, and then we got like prettier and it's like, oh, hey, by the way, you could just have, trailing comma on everything. And, at least in objects, I guess in a raise, you probably can't do that, but you get my

[00:49:32] **Ben:** I think you can.

[00:49:33] **Adam:** I don't know. I don't know if that creates an undefined object in the array, but either way,

[00:49:37] **Ben:** So, okay, so, so that, so this is the subjective part for me. So, cold fusion has historically not had trailing comma support. Cold fusion 2025 just added it.

[00:49:48] **Carol:** What,

[00:49:48] **Ben:** JavaScript

[00:49:49] **Carol:** how did I not know

[00:49:50] **Ben:** quite a while,

[00:49:51] **Carol:** about ColdFusion.

[00:49:53] **Ben:** but I programmed with e as being technically IE six or like, no, i, E 11 was one of our supported browsers that worked for a really long time, and I think IE 11 would blow up if you had a trailing comma. So I'm shell-shocked and I don't have, I don't have, you know, years of muscle memory. So now that I can do it in cold fusion, I don't have a sense of where to do it. so like at first I try to just put 'em anywhere was possible. So argument lists, and then argument invocation. But then I found that I was putting it in places that were a lot more static, like just a object literal, where I have key value, key value, key value.

[00:50:37] **Adam:** Mm-hmm.

[00:50:38] **Ben:** And I would put a trailing comma there. And I would think to myself, I don't think this structure's ever gonna change though. And I'm like, do I wanna have the trailing comma now just for the sake of having the trailing comma everywhere? It's syntactically possible That didn't, I don't, I don't have a, I don't have a feeling for it yet.

[00:50:54] **Ben:** So I'm, I was curious, are you saying that Es

[00:50:58] **Adam:** I like my linter rules, not, yes, lin prettier, I think, uh, just says, yeah.

[00:51:02] **Adam:** Here, you're, you're missing your trailing comma. Let me add it for you.

[00:51:07] **Ben:** I fixed it for you,

[00:51:09] **Carol:** So I also go back to kind of like how I write, and this may not even be the same thing, but how I write sql, right? So commas after the end of a column, if I wanna comment out something, I can comment out, comment out anything in that entire list, and still run my select statement. If I have my commas at the beginning, I didn't have to like comment that out, hit enter.

[00:51:29] **Carol:** That way I can run the select, because if I comment out, like comment out the very first column, now I can't run that because I'm starting with a comma.

[00:51:37] **Carol:** So the ends are, or the ends are

[00:51:40] **Adam:** I, I'll give you that. I, I've run into that many times and it would be nice to just be able to comment out single line,

[00:51:46] **Carol:** Yeah,

[00:51:46] **Ben:** but Oh, sequel's a whole nother one. I have so many strong feelings.

[00:51:51] **Adam:** it's almost like all this stuff is subjective.

[00:51:52] **Carol:** it is.

[00:51:53] **Ben:** Right. Okay, so, so maybe let's, you know, we're, we're almost at an hour here, so should we just do like a, what's

[00:52:00] **Adam:** Send us your, yeah. What, what's your, what's your favorite, subjective thing to harp on and yell at people for

[00:52:07] **Ben:** Right. Send all email to Carol

[00:52:09] **Adam:** Tim, Tim Cunningham. Oh. Put it, put it in our discord. We have a, a channel specifically for, stuff related to episodes of the podcast.

[00:52:19] **Carol:** Yeah.

[00:52:20] **Ben:** but my takeaway as I'm getting older is just works, you know, to quote the movie Carol, that was a movie, whatever works or No, as good as it gets,

[00:52:32] **Ben:** was that what it,

[00:52:33] **Carol:** for a reference. Yeah.

[00:52:34] **Ben:** there was something, oh no. Whatever works as another. It's a Larry David movie. as Good As It Gets is a different movie. Sorry, I messed up my own pop culture reference.

[00:52:41] **Ben:** but it, it's just like, it's all so to each their own. And I do think that there are core underpinnings of clean architecture that we can more or less agree on, but the, the details. Are just so personal. It's like, okay, so Seth Godin, I don't know, I'm sure a lot of people are familiar with Seth Godin. He is a business thought leader.

[00:53:03] **Ben:** He's written like a bajillion bestselling books including, linchpin Purple Cow and The Practice, and he's, he is very well known, and the business world, and I was listening to his podcast Akimbo and he said, it turns out that the best pizza in the world is whatever pizza you grew up with, that whenever you talk to people that's, you know, it's the pizza from your hometown.

[00:53:27] **Ben:** And if you went to someone from New York and you said, oh, it turns out that Chicago style is the best pizza, I'm sure you, a lot of New Yorkers would be like, oh, that's disgusting. How dare you? And vice versa. but it's true for both of those people and, and just as like much of this is true for the people who have feelings about it.

[00:53:44] **Ben:** And so I think like my biggest takeaway is that it's subjective and that. The people I almost hate the most are the people who it's not subjective for at all. Meaning that like they don't care one way or the other. I'm like, how could you not care? Are you a robot?

[00:54:04] **Adam:** Yeah. You're, you are, I think at your core, you're like a, a software craftsman. That's what matters to you is like the process of creating something beautiful that also happens to maybe be helpful in a computer.

[00:54:19] **Ben:** Right, right. Yeah, exactly. So like, if you like spaces like spaces and I like tabs. I like tabs, but, but like have an opinion. That's my, that's my thing. It's like, have an opinion. You should have an opinion. It's like when we talk, sorry, not to be political for a second, but you, I think, Adam, you mentioned on a, on a previous episode, like everything is political and when you don't have an opinion, it's just because something happens to agree with your politics like. You should have an opinion about everything in programming and like, you cannot have a feeling, meaning, meaning like you cannot have enough experience to know what way you like, but you should like something that just makes sense. That's just human. And when you people talk about not liking stuff, I find that very suspicious.

[00:55:04] **Adam:** I, I agree with the caveat that, you know, we, we can't put that responsibility on people to, to know enough of everything, to be able to make an informed decision. Like, it's okay to still be on your journey, but be willing to have an opinion, be be willing to learn what the differences are and stuff. Yeah,

[00:55:23] **Carol:** Yeah, I go for readability. Just make it so I can read it, like gimme that, please.

[00:55:29] **Ben:** Agreed.

[00:55:30] **Carol:** Mm-hmm.

## [00:55:31] Patreon

[00:55:31] **Adam:** Alright, well then, this episode of Working Code is brought to you by objectivity, which is, if you're not familiar, the YouTube channel where they just, not dissect. Why did that word come to my head? They kind of inspect and get to know or whatever. Really interesting, stuff. I, I do actually it is a channel.

[00:55:49] **Adam:** I do recommend it. It's very cool. Like they go into, the Royal Academy in England and, and like check out their archives and they just pull random stuff out and look at it. Sometimes it's like a, a book of hand drawn pictures of like leaves or something, but it's, you know, it's from 1645 and it, it's beautiful.

[00:56:07] **Adam:** Whatever, you know, like really cool stuff. if you're looking kill some time, that's a great way to do it. So,and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:56:23] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock?

## [00:56:32] Thanks For Listening!

[00:56:32] **Adam:** after show, we are going to go record the after show after this. basically if you're, uninitiated, welcome to the pod, first of all. Second, after show is, after is gonna play for you the Holy Poid. and the, the patrons of the show are going to get to keep listening to more of us, whittering on, about this and that.

[00:56:51] **Adam:** We'll probably talk, I don't, you know, I don't even know what we're gonna talk about. new branches are coming and window maximizing. That sounds in incred like so worth your money. That's the, that's the information that I'm working with here. anyway, let's move on. you can become a patron of the show by going to patreon.com/workingcodepod, and we actually have a new patron to welcome this week.

[00:57:14] **Adam:** Ben Thomas. Welcome aboard.

[00:57:16] **Ben:** What would.

[00:57:17] **Adam:** thank you very much. Glad to have you. and like I said, if you want to join Ben in supporting the show, you can go to patreon.com/workingcodepod. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:57:27] **Carol:** uh, remember folks, it's not subjective. Your heart matters.

[00:57:32] **Ben:** channeling your inner

[00:57:33] **Ben:** Tim.
