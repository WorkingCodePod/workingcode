---
title: "238: This Is Why We Can't Have Nice Things"
description: "This week, the hosts explore how good intentions collide with bad behavior—where success becomes punishment, communities ruin what was made for them, and the people who just wanted to share something cool are forced to walk away."
date: 2025-11-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/238-this-is-why-we-cant-have-nice-things/id1544142288?i=1000736575003"></iframe>

What happens when your passion project becomes so successful that you have to shut it down? Advent of Code creator Eric Wastl announced he was scaling back from 25 days to 12 and removing the global leaderboard. The reason? People were feeling bad at their jobs because they couldn't solve puzzles in 45 seconds like the leaderboard speedrunners.

Quiet UI launched with excitement, garnered incredible buzz, and shut down three weeks later when the demands became overwhelming.

This week, the hosts explore how good intentions collide with bad behavior—where success becomes punishment, communities ruin what was made for them, and the people who just wanted to share something cool are forced to walk away.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/238-this-is-why-we-cant-have-nice-things.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** But anyway, he said he's taken away the leaderboard. The main reason is that because people started to feel that they were bad at their job because they weren't good at the admin of code, which is one of, is not what he wanted to do. He wanted to help people like, you know, try to just do something fun,

[00:00:13] **Tim:** it just, it, it hurts my heart 'cause like why can't we have nice things?

## [00:00:37] Intro

[00:00:37] **Adam:** Here we go. It is show number 238. On today's show, we're gonna talk about why we can't have nice things. Everybody just ruins everything. Anyway, before I get all upset, as usual, we'll start with our trying and fails. We're gonna mix things up a little bit tonight. Carol's not here. She's, got an excused absence for Veteran's Day stuff where we're recording this on day.

[00:00:54] **Adam:** so thank you to all of our, active duty and,

[00:00:56] **Adam:** and other service members. but, anyway, like I said, we're gonna start with our triumphs and fails. I'm gonna mix it up, so I'm just gonna go first, and

## [00:01:02] Adam's Triumph: Adopting Liquibase for Database Migrations

[00:01:02] **Adam:** I'm gonna start us off with a triumph, which is just a, a simple one.

[00:01:05] **Adam:** I have mentioned in the past that we, at my company don't, have any sort of, like migration tool for our database. We've just been kind of raw dogging, MySQL, you know, you need to make a change. You just go over on an alter statement or whatever. which has worked. I mean, we've, we've got this product that's been, the product itself is 10 years old and, and things are going gangbusters for us.

[00:01:25] **Adam:** but it's, it's, you know, especially as we are now starting to, we, we hit kind of an inflection point on our number of customers chart and things are accelerating. and so we, we really need to work on things that reduce that, like onboarding costs. So we're, we're using, Liquibase now for database migrations.

[00:01:43] **Adam:** And I mean, it's not without its challenges, but hey, at least it's something right.

[00:01:48] **Ben:** We used Liquibase, at Envision and pretty successfully. I, I, I think we all enjoyed it. The, the biggest hurdle that I had, and I don't know if you've run into this, we were actually, I think we were actually technically using something called Exodus, but it was built on top of Liquibase.

[00:02:06] **Ben:** And when I switched from using my old MacBook Pro from like 2015 to using the, my current one, which is an Apple M1, the apple silicon chip with the arm processor, I kept having to rebuild all of the images for the Liquibase locally. 'cause they were all like our whole. Like our version of Docker Hub was everything was built for the Intel processor, so nothing worked on my machine.

[00:02:37] **Ben:** And every time I would wanna use the database migration, because we had this layered thing, it's like I had to build the base liquid, base image locally, and then I had to build the Exodus image on top of that locally. I could never just pull the images. It was so frustrating.

[00:02:51] **Adam:** Yeah, I mean, I'll say having a solution like a blessed, this is the way we're gonna do it. Solution is the most important part and we have that and it and it works and so that's great. If I do have like a primary complaint so far, it's that the you manage to change sets in YAML files. And I fricking hate YAML to begin with.

[00:03:10] **Adam:** Like a white space, is significant language. it is just to me a big red flag. Then, I guess like some of us have different IDE settings and like I have my stuff set up to like run prettier and, and like format on save. Right? So if I just edit a file and hit save, then it does, it fixes any indentation issues.

[00:03:31] **Adam:** It might like wrap things that weren't previously wrapped because of like max line width rules or something like that. Right. And the, the way that Liquibase works is every change set has, like a, a. A SHA or something, right? Like a, a check sum, something like that. of the content, of the change to that.

[00:03:49] **Adam:** And if you modify it at all, if you add a line break, if you add a space, you know, whatever, then if you change the indentation of that block of yaml, it changes the checksum. And now your database migrations are just like, oh, something's wrong. Don't know what to do. Hands in the air. I'm, I'm not gonna do anything.

[00:04:07] **Adam:** Go fix it. Which is incredibly frustrating. So we're, we're working through that, the speed bumps

[00:04:13] **Tim:** It's like having that pedantic friend who doesn't get the spirit of what you're doing.

[00:04:17] **Adam:** right, I, I, I feel seen or what's the, or no, I feel personally attacked.

[00:04:25] **Ben:** Where are you storing and versioning? the migration files themselves. Is it, is it part of the main repository? Is it a separate repository just for the migrations? What's your strategy there?

[00:04:37] **Adam:** our strategy in general in terms of like monorepo or not monorepo or, or all of that stuff. basically our approach is just the worst of all possible worlds. Like, gimme the worst of this approach and the worst of this approach and mix 'em together and hopefully create a new color of worst. We have, we have a mono repo with like our main monolith and a bunch of different things in there.

[00:04:57] **Adam:** And then we also have a bunch of, we have probably like 20 or 30 more other repos with different things in 'em. And the, the database, stuff, including Liquibase, is often a separate repo.

[00:05:09] **Ben:** Gotcha. It's like a monolith Plus. Plus.

[00:05:11] **Adam:** Yeah. Yeah.

[00:05:12] **Ben:** Nice.

[00:05:14] **Adam:** So, you know, it, it, it, it feels good to have a blessed solution. I'm happy that we're on that path. I'm happy that, you know, if we need to make an altar or something like, I don't have to open connections to all of the different databases and hope I don't forget one and hope I don't accidentally run a delete when I'm supposed to be running an altar.

[00:05:33] **Adam:** And, you know, all this stuff that like. Pretty much every time something goes down, my gut reaction, like when a, when AWS went down a couple of weeks ago, my gut reaction was like, oh God, some poor intern. made the smallest little mistake and it just like blows up half the internet.

[00:05:49] **Tim:** it's always DNS, though.

[00:05:51] **Adam:** yeah.

[00:05:52] **Ben:** You know, one thing that I didn't realize was in the Liquibase capabilities for the longest time, and this is maybe specific to MySQL, but part of the Liquibase specifications that you can say, create this new column. After another column. So for the first couple of years, all of my Liquibase migrations just added columns to the end of the table schema.

[00:06:15] **Ben:** And then literally, I was trying to find an example of something, and I'm just going back through the different migrations, looking for an, I think I had to like add an index and I was looking for the command for that, and I just randomly opened one file. I saw it was a column creation, and then there was like a after user id.

[00:06:31] **Ben:** I'm like, what? I'm like this, this just changed everything.

[00:06:38] **Tim:** It does my heart Good. I mean, so I mean, many years ago I, I gave a talk at a conference about database source control,

[00:06:45] **Tim:** migrations kind of

[00:06:46] **Ben:** was there, bro.

[00:06:48] **Tim:** You were there. You were, yeah. You had good questions, but it's like it wasn't a fully baked thing at that time. It was really something I was playing with and I was really just kind of encouraging people to, some people were a bit salty about that, like, oh, so you don't have a solved solution?

[00:07:00] **Tim:** Like, no, I don't, I don't think anybody does right now. And they, no one really did. And now it's like, it's pretty common. It's like people are like, yeah, I could run into Migrations. Net has some solutions. Bunch of different language have solutions,

[00:07:12] **Adam:** So I've been talking about, the work I've been doing with Jump Run and I, in my Agent MD file, I explained how the migrations work, right? And so when I, when I do like, you know, not vibe coding, but agentic coding, stuff on, on jump run, now I've got it set up where if there's database changes necessary, it like runs the command to create a new migration.

[00:07:31] **Adam:** And it requires renaming a file and it, and it fills it out. It's great. I love it. Like database changes included now in my, in my agent decoding,

[00:07:39] **Tim:** It's so nice you just deploy your code set and not have to have a separate parallel. Oh, we gotta make sure we time everything up so that with the database migrate, you know, changes get, no, you don't worry about that. Just run your code set. It'll take care of the database. That's fantastic.

[00:07:55] **Tim:** But, but I, but I find it, a lot of times it works. Some people just, they, they can't wrap their head around it.

[00:08:01] **Tim:** like, no, I'm used to going and clicking and adding or running a script, you know, in the brow in. My, my SQL tool or whatever it is, it's

[00:08:09] **Adam:** Mm-hmm.

[00:08:10] **Tim:** stop it's code. Treat it like code, stop

[00:08:14] **Adam:** Yeah.

[00:08:15] **Tim:** In fact, we projects where we set stuff up to do that and then we walked away and like worked on other stuff.

[00:08:21] **Tim:** We come back like, where's all the data Mic basic, oh yeah, we couldn't get it to work and blah, blah, blah. I'm like,

[00:08:28] **Tim:** y'all just, y'all just didn't even try, did you?

[00:08:30] **Adam:** Yeah.

[00:08:31] **Tim:** You just gave up. 'cause it was hard Rather than learning.

[00:08:34] **Ben:** On my little personal projects. I don't use anything sophisticated like, like a, like a real migration system, but

[00:08:42] **Adam:** IDE, sorry,

[00:08:47] **Ben:** that's funny.

[00:08:48] **Adam:** just over here, firing shots.

[00:08:50] **Ben:** But I will still, I, I have a directory that is just. A directory of SQL files, and it's really just create table and alter table statements and it's part of the repository so it gets versioned. And the nice thing is, is that because I'm using Docker. Composed locally to spin up like my cold fusion and my database and like my mail ho fake SMTP server.

[00:09:16] **Ben:** I can mount that, that one directory as the like in it D folder for my sql, which is like, if my seql hasn't been created yet, it'll run all the scripts alphabetically in that folder. So even though I'm just running one at a time during development, I know that I can always blow away my, all of my database schema and my SQL will just create it the next time it gets built, which is, you know, it's not migration in a sophisticated sense, but it, it gets me like it's an 80 20 rule for me.

[00:09:47] **Adam:** I just wanna point out and take a moment to appreciate early on in the, in the annals of this podcast, Ben, you were like, a goal for me, like distant future. I wanna learn docker. And now you're just like dropping. Oh yeah, I'm using Decker Compose. Like it's a whole thing.

[00:10:02] **Ben:** I did have a goal from like, oh man, I feel like it was like 2021. My goal was to deploy a service using a container, and that still has not happened.

[00:10:12] **Adam:** But at least you're using it locally. Like that's step one.

[00:10:14] **Ben:** Oh, no, I, I, I feel like I can't do anything else at this point, have to use containers.

[00:10:20] **Adam:** All right. He's been half Docker pilled.

[00:10:22] **Ben:** There you go. They, they're just, it's, it's, and, and I'm definitely learning new stuff constantly about it.

[00:10:28] **Ben:** Mostly because I'm breaking stuff and trying to understand why it doesn't work. But it, there's so much stuff in there. It's bonkers. But chat, GPT, this has actually been one thing that I do consistently go to chat GPT for, is. How do I change this Docker compose, or like

[00:10:45] **Adam:** Mm-hmm.

[00:10:46] **Ben:** keeps telling, Docker keeps complaining about this error.

[00:10:48] **Ben:** What do I do? And chat. GBT is, I wanna say like 95%. Right on its Docker compose suggestions.

[00:10:57] **Adam:** Yeah. And, you know, the, the stuff that I've been seeing lately that's like kind of somewhat anti ai, but not like completely anti ai. It basically, I think the thesis statement of what I've been getting lately is like. It's okay to use ai, but use it in a way that makes you better, not that surpasses you, if that makes sense, right?

[00:11:18] **Adam:** Like, so if you don't know how to do something, don't just ask the AI to do it and blindly accept what it gives you. Like ask it to teach you, right? Oh, I don't understand how to make this docker change. What am I, you know, what, what concept am I missing? How do I make this change? And then learn that, rather than just like, make the thing, do the thing and commit.

[00:11:38] **Ben:** Agreed, agreed.

[00:11:40] **Adam:** Okay, well, that's enough for me on my, Liquibase migration stuff. so Ben, what do you got going on?

## [00:11:45] Ben's Fail: Form Usability vs Aesthetics

[00:11:45] **Ben:** I, I'm gonna call this a failure. It's not really a failure, but it feels like a internal struggle that I have trouble passing, which is this healthy tension, let's call it, between usable forms, like data entry forms and forms that look good. And I just feel like those two do not play together nicely unless you have a really common pattern.

[00:12:13] **Ben:** Everybody has entered an address field where it's address one, address two, and then like city, state, and zip might all be on the same line. It's like as a pattern, our brains just sort of understand that, or credit card information. I think we've all done one where it's like name, card number and then you know, expiration date CVV and zip code all in one line.

[00:12:32] **Ben:** So these sort of a horizontally scanning fields. When it's a a common paradigm, I think it's very easy to. Wrap your head around. But what I find myself struggling with is that for uncommon form fields where we're getting a whole bunch of random data that doesn't fit neatly into these things that someone sees on every checkout form, I want to use that same horizontal scanning.

[00:12:58] **Ben:** You know, like a, oh, these two fields could easily fit on the same line and are loosely related, so I should put them horizontally, not stacked. It looks good. You know, when I put them horizontally in a couple of rows of horizontal inputs and I render the page, my immediate reaction is, this page just looks good.

[00:13:15] **Ben:** Like it looks, you know, masonry layout, kind of a vibe. But then as I go to use it, I'm like, ah, scanning across form fields just feels like garbage. And I've, you know, spent years scanning up and down pages and scanning up and down form fields. Just feels. More natural. It feels more scannable. There's less confusion.

[00:13:37] **Ben:** My eyes isn't darting all over the place, but you look at a page like that where it's just this stack of form fields and it looks kind of crummy, but it's so much more usable. And I, and I, I get my failure is that I'm, that this is still a point of tension for me. Like it should just be obvious. I should just stack the fields.

[00:13:55] **Ben:** It's more usable, it has less friction, less confusion. Your eye knows where to go 'cause it can only go in one direction. Like, why can't I just give into that and let that happen? But I can't, like, I'm like

[00:14:05] **Adam:** Because you got feel feels in your

[00:14:06] **Ben:** the feel feels and I want the horizontal sometimes.

[00:14:10] **Adam:** So I actually have two rants that I want to go on

[00:14:12] **Ben:** Okay. Ran away my friend.

[00:14:13] **Adam:** I, let me mention them both before I forget. One. One is the, the government studies and the other is, countries being last in a, in an address set of fields. Have I, have I ranted on the country being last before Tim thinks Yes. It looks

[00:14:27] **Tim:** No, no, no. I don't think you have. I, I agree. I I agree with your

[00:14:30] **Adam:** Yeah. Yeah. So, you know, typically with the address fields, right? You, you put in, okay, this is my name and I live on this street, in this city, in this state, in this country. But if you're not American then, or if you're not domestic for whatever country, like owns the website, right? So if it's Canada, then the, then you have to put in your province before country or whatever, right?

[00:14:52] **Adam:** Well then you're the way that you are, if you, if you, you know, if you live in France or China or whatever, right? You're probably. Mentally already trained yourself to jump to the end of the form or the end of the address, section of the form, change the country, because that might change the, the, you know, city, state, zip fields.

[00:15:10] **Adam:** If the, if the form, you know, isn't internationalized at all. and then you go through and you fill it out, which is just dumb. And so, like, this is five years ago, something like that. In some of our address forms, we tried moving country to be like first thing after name, if I'm not mistaken. Like early in the form.

[00:15:29] **Adam:** Right. which makes perfect sense. Like what is the correct format for a date? You go most broad to least right. Year, month, day. That is canonically correct? In anybody who would disagree with me is wrong and I'll fight you. And same way, you know, I believe strongly the same way for, for address forms.

[00:15:47] **Adam:** I would be very happy to come across an address form that's like name, country, whatever state, city Street, right? Like, that makes perfect sense to me. It, it will feel very awkward at first, but it, it's nothing you change in line One is going to have to be redone because you get to line five and, oh, now something I entered on line five, the most specific is.

[00:16:09] **Adam:** Affecting line one, my country. Right. So anyway, there's that, that rant over, my other thing. Yeah. Yeah.

[00:16:16] **Ben:** to the country for a second. And this is totally a, you know, America is the center of the world kind of a thing.

[00:16:22] **Adam:** Mm-hmm.

[00:16:22] **Ben:** we're the United States and you is pretty far down on the list, alphabetically of countries. It's like third from the bottom or something.

[00:16:29] **Adam:** Yeah.

[00:16:30] **Ben:** And it just drives me crazy when I go to select a country and it's not like Canada and us as the first two options, and then like dash, dash, and then like all countries alphabetically.

[00:16:41] **Ben:** I don't know why. I mean, that's just like, again, me being, yeah, I'm like, what do you mean America's not the default one?

[00:16:48] **Tim:** It's like, yeah, it, it's like I get mad when the, the date of birth, the year. It's like it's, I have to scroll so far. I get vertigo.

[00:16:56] **Ben:** You know? And then the ones where it's a. It's not a native select menu. It's like some, you know, fancy menu and you can't just type in the numbers

[00:17:05] **Adam:** yeah.

[00:17:06] **Ben:** 'cause it, they didn't wire that up. So you actually have to scroll down to like, I don't know, like 1872 or.

[00:17:11] **Tim:** with the, with the, with the United States thing that they really should just sense geolocate where you're coming from first, right? And just make that. Make that

[00:17:21] **Tim:** top one sort of like, yeah, are you in Portugal? Put it on the top in the United States, put it to the top and then change it there.

[00:17:27] **Tim:** But I agree with, yeah, I, I never thought about it the way you did Adam, but yeah, having the country coming prior to all the other stuff is, particularly if you're gonna change, like instead of zip code, it's postal code, or maybe they don't have zip codes or they have a whole different scheme of, of numbering things.

[00:17:46] **Tim:** It's gonna change the form. It's, yeah. We're very privileged United States. We just assume, okay, we we're good. Our country last 'cause yeah, everyone's American.

[00:17:55] **Adam:** Yeah. So, I mean, I guess I should mention what we do is, whatever country is domestic for the school, right? So we have schools that are outside the United States, and so whatever their home country is for the, the campus, that's what we put at the top of the list and then the dash, dash and the entire list.

[00:18:12] **Adam:** So I'm, you know, and, and honestly like, I don't get my fifis hurt. if United States isn't at the top of the list, I, I just click on the select and I hit the letter U on my keyboard, and I'm like, within two or three of scrolling to the right spot anyway.

[00:18:26] **Tim:** Unless you are mobile, then you can't hit it.

[00:18:29] **Adam:** That's true. That, that is a teeny tiny, well, you know what, though, on mobile I have like auto, I just, I have like auto-fill out profile things, right?

[00:18:38] **Adam:** I just, I tap on the first name field, and it's like, oh, do you want me to fill in your home address? I'm like, yes, tap. Done.

[00:18:44] **Tim:** But you know, a lot of times. The country code doesn't always populate on it. I found that very common, that like you, it starts to autofill and it's like, it does, it does everything right except

[00:18:55] **Adam:** recognize that. Yeah, yeah. No, you're right.

[00:18:58] **Ben:** and I can't tell you how many times, even just recently. I have auto filled a form and it's like, oh, you have to enter zip code. And I'm like, the zip code literally has information in it right now. And you're like, oh, yeah, but you didn't manually type it. So our, our event handlers didn't see that that happened.

[00:19:15] **Ben:** I'm like, why are you using event handlers to see if I entered that data?

[00:19:17] **Tim:** go, could you go in and tab outta that field for me please? So I can see what it actually is? That'd be great.

[00:19:23] **Ben:** Just the tab, please.

[00:19:25] **Tim:** Okay.

[00:19:27] **Adam:** so, my other, rant is, so I don't know you guys, if you guys know this, the, the US government because, the government regulations on accessibility and stuff has done studies of, what. forms. Now, I'm not talking about online in input forms or whatever. I'm talking about like the forms you get that, that you have to fill out for your taxes, right?

[00:19:45] **Adam:** Like, what is a form, what is the most usable way of, designing that form? Like, how do you make sure that they understand that they put their name in this box and their phone number in this box, right? And like, where do you put the, the, the label for the input or the input, the box, whatever. and this was years ago I saw this, but somebody had made like a mockup of.

[00:20:05] **Adam:** I mean, and basically, if I remember correctly, the, the way that they, the, the outcome of the research was that like the, the label needs to be inside the input. and so the, but then, oh, it, I mean, like I said, this was years ago. I don't remember the full details, but if I remember correctly, basically the way that they designed this input component was like, it's a text box and your placeholder text is like in there, right?

[00:20:29] **Adam:** And that's basically your label. But then when you click in or tab into that input. The placeholder, you can actually see it like animate. It slides up to be above the field, like just above it.

[00:20:39] **Ben:** uh, theGoogle material forms does.

[00:20:42] **Adam:** That might be, yeah. I don't know.I, I always liked that concept a lot. 'cause it, it, it feels like it declutters the page a little bit. Right. 'cause then, I don't know. Whatever. I don't wanna get too deep into it. We got a lot of, lots of stuff to get to, but,

[00:20:55] **Ben:** Oh, that's right. We have a whole other show to do.

[00:20:57] **Tim:** Oh yeah, we're just do try and fails today.

[00:21:01] **Ben:** All right. Well then I'll, I'll, I'll call mine there and I'll kick it over to Tim. Tim, what do you got going on?

## [00:21:06] Tim's Triumph: Completing Advent of Code 2024

[00:21:06] **Tim:** So I'm gonna go with the triumph. So for many years I've tried my hand at the advent of code. If so, for those of you who don't know, advent of code is around Christmas time. There's this coding challenge where it's, it's basically sort of computer science type problems, algorithm problems. and so they give you the little story and they have like the initial, initial description of the problem.

[00:21:33] **Tim:** They tell you the, the problem, and they tell you the answers should be this, right? So basically they're telling you you can build a test, right? So if you can, if you, if you can. Build a test, write the code, the test

[00:21:45] **Adam:** Ben, a test

[00:21:47] **Tim:** Yeah. For those of you who don't know, a test, nevermind. so it's, so then it gives you a, like a data set, a much bigger data set.

[00:21:57] **Tim:** So usually you can do the initial test problem pretty easily if you understand the problem, but then you get into the bigger data set. A lot of times what happens is you don't have a very efficient way of solving the problem. That's what I've always ran into. I, I've tried these in cold fusion and like, I don't, I don't have a, a, you know, a full CS degree kind of background as I was more web development.

[00:22:21] **Tim:** So I don't know all these algorithms and all these other things that, that my son is learning in, in college right now. so super jealous of him. But anyway, and so this year I decided, right, I'm going to try to do last year's. 2024 code in Python, which a language I've been trying to learn, and see how it goes.

[00:22:45] **Tim:** And it

[00:22:46] **Tim:** went

[00:22:46] **Adam:** just keep it online. You can like go back and look at last year's

[00:22:49] **Tim:** Yeah. You, you can go back several years. Yeah, you can go back. I'm pretty sure I went the beginning, but I just went back to last year's problems and put them all in in random. Yeah, so it was pretty cool. It was a, it was a good learning experience. I spent the whole weekend doing that. I did all 25 days now.

[00:23:07] **Tim:** Yeah, I did all 25 days and I learned a lot from it. And I think though, this kind of goes into our

[00:23:16] **Adam:** I think you're right. Yeah. 'cause we have, we have some inside in, not inside information, but we. Some preexisting knowledge of what happened to advent of code, and it's different now and, yeah, that, that dovetails nicely with the show topic today. For some reason, that just so happens to a neatly, fit together.

[00:23:33] **Adam:** Totally not pre-planned.

[00:23:35] **Tim:** what a crazy random happenstance. So, so, and the process of looking at that, I looked at his 2025 advent, like, what's coming up the next year, when does it start? And all that stuff. And he basically sort of had a disclaimer. I don't know, I don't know his name. I keep saying he, but it's a he. And it's only 12 days this time. Normally it's like last year was 25 days, which is a whole lot of work. This is one dude and probably he probably has some helpers,

[00:24:01] **Tim:** but, um,

[00:24:02] **Ben:** It's, I mean, I only tried it once, but it seemed. Sophisticated,

[00:24:05] **Tim:** very sophisticated. Very, I

[00:24:06] **Tim:** mean, they're very

[00:24:07] **Ben:** story, right?

[00:24:08] **Tim:** Yeah, it's, it's a whole story about, like last year was, was about trying to find the master historian of Santa's elves and you have to talk to the elves and the elves, you know, have to, Elves computer is busted and you have to like compact their, their memory for them.

[00:24:25] **Tim:** So you have to build a compact. Yeah. And then you have to find the best route for the reindeers to go like route finding. and so, but he's been doing this, I don't know, almost a decade and it's a whole lot of work. So he is cut it down to 12 days. But the thing that really hurt my heart. The thing I see a lot going on in the tech industry is he created this as a way for people to get better at their, at what they do.

[00:24:50] **Tim:** Right? That these are challenges. This is the way to flex your muscles. And he had a, like a leaderboard. And there were people like that Were solving these things in like 45 seconds. Really hard, hard problems, right? Chances are, they're probably ai. I don't, I don't know what, you know, what's going on. But anyway, he said he's, he's taken away the leaderboard. The main reason is that because people started to feel that they were bad at their job because they weren't good at the admin of code, which is one of, is not what he wanted to do. He wanted to help people like, you know, try to just do something fun, build some coding muscle rather than try to make them feel bad that they're not as good as other people who can do this in less than a minute, whereas it took you.

[00:25:33] **Tim:** Two, three hours. Yeah. I would spend, like last year I probably spent three, four hours on some of the problems and never actually got them done. Now I didn't feel bad about that. I just realized, you know, maybe ColdFusion sucks. It wasn't me, but, sorry, Ben.

[00:25:49] **Adam:** You just wounded this man.

[00:25:50] **Tim:** Uh,he's, he's crying. He's actually crying. No, no. I don't, I don't mean that all.

[00:25:55] **Tim:** But yeah. So it's like, it just, it, it hurts my heart 'cause like why can't we have nice things? He, the dude really put his heart and soul out there for us every year around Christmas, before Christmas time to do this. And you know, now he's having to dial it back 'cause of, yeah, people.

[00:26:11] **Ben:** I tried doing it. I don't know once. Three years ago or so, and I was so excited 'cause everyone had always talked about it for years and I always felt like I was missing out. And I tried it and I don't think I got past the first one. I remember it. Or maybe I got the first one and then I, I couldn't get the second one.

[00:26:30] **Ben:** I, I don't remember why exactly. It ended up, I think maybe it was just gonna be a lot more work than I had anticipated. I thought it was gonna be just kind of like a bunch of little. Lead code problems. You know, one every night where it's like I jump in for 10 minutes and I solve it. And it's definitely not that.

[00:26:46] **Ben:** You can see the amount of work and passion he put into it and, I could see why it's so enjoyable for people, but could never make it. But I'm, I'm jealous of the people who can.

[00:26:56] **Tim:** I, I think the years I tried to, the furthest I ever got was to day 10. And then I get, I get stuck and then I lose heart and like, I never actually, but I actually did finish this time.

[00:27:08] **Ben:** this reminds me of what was the, the, the Hack Tober Fest or something was like Datadog or, or maybe it was digital lotion, one of those companies. Started a month where if you, people would start to set aside public GitHub issues specifically for this contest, and then anyone who submitted a a, a pull request for something like a typo or, you know, updates to the documentation or fixing

[00:27:35] **Ben:** some weird little bug they've had, you would get a free T-shirt.

[00:27:38] **Ben:** I think it was, I wanna say it was Datadog

[00:27:40] **Adam:** that was actually Hacktoberfest and it was Digital Ocean that put that on.

[00:27:44] **Ben:** Okay, that makes sense. And because they gave out t-shirts, it was obviously a, a contest that had a real dollars and cents. Aspect to it. It wasn't just made up, you know, badges you could put on your GitHub profile or something. So I think they stopped doing it, or at least they stopped doing the t-shirt portion because people started to abuse the system where they were filing tickets for like tiny spelling mistakes and things that just weren't in the spirit.

[00:28:13] **Adam:** not even like tiny spelling mistakes, but just like. Making, almost like just making a, adding a new line to a markdown file. You know, just like, look, I made a change, sort of thing. Like, or just adding random characters that don't belong for any reason, like making it actually worse.

[00:28:30] **Ben:** Yeah. And so kind of kind of like what you're saying is people start with the right intentions. They start wanting to do something fun and something good, and something that'll. Actually have a beneficial effect on the people in the community. And, and, people make it bad and then they can't have nice things. And actually, I was just watching you guys know the Primo. I don't actually know his real name, but so he has, he has like a couple of different YouTube channels I think. And they were just the other day talking about, the guy, it's like, it's like one guy who maintains ff m Peg. Apparently went on a public rant because Google has this massive like billion dollar open source fuzzing project where they're constantly looking for and filing, security vulnerabilities on different projects.

[00:29:17] **Ben:** So they apparently, I, I'll get some of the details wrong here, but apparently they filed a ticket in FFM Peg for some codec, some video codec that nobody uses anymore and like hasn't been used since the nineties. And he was ranting. He's like, so you have a billion dollar mechanism for opening these tickets, but you don't have any money to put towards fixing stuff like this.

[00:29:39] **Ben:** Like, why are you making this my problem? They were talking just as a broader thing about how AI makes it easy to find these things, but doesn't necessarily mean that you're contributing, mostly you're just creating more work for other people when you're opening tickets. And I, you know, not, not to get off the topic of the show too much, but it's just like, it's another example of, you know, probably someone has the right intentions and then it just gets abused and it becomes a a point of friction and takes the.

[00:30:10] **Ben:** The joy out of it for somebody who just wanted to do a nice thing.

[00:30:15] **Adam:** I do wanna jump in here actually while we're, while we're being Debbie Downers, and to just. Just to point out, you know, we have the Working Code Discord, and I have not historically participated, although I'm feeling a little motivated to maybe think about it this year.

## [00:30:29] Working Code Discord Advent of Code Channel

[00:30:29] **Adam:** But, we have an advent of Code Channel, and you know, people in our Discord, you, the community will come in and they, they solve the challenges, and then there's discussion about like, you know, this is how I did it and this is why.

[00:30:41] **Adam:** And, you know, people might ask questions like they, and help each other, like, learn things and get better. Like, that is in the spirit of advent of code, right? and Tim, I don't know if this made the recording, I know you mentioned it before we started recording. Don't they have the ability to have like sort of private leaderboards?

[00:30:56] **Adam:** You can have your own. Yeah. So we should, if we don't already, we should have that for

[00:31:00] **Tim:** I, yeah, I think we should. So he, he did, like I said, he did take away the global, they had a global leaderboard. He took that away and asked people, please don't use the private leaderboards just to create a global one. 'cause you totally could do that if you wanted to. It's against the spirit of it, right?

[00:31:14] **Tim:** It's like you should be. Pushing yourself to do better, to make yourself better, not to compare yourself to other people. And, although a little competition kind of helps motivate you. But yeah, don't feel bad if like, it took you an hour, it took someone else, you know, two minutes. So I, I'm gonna have to give you a full disclosure here.

[00:31:35] **Adam:** Okay,

[00:31:36] **Ben:** Do it.

[00:31:37] **Adam:** just close away.

[00:31:39] **Tim:** So I, I a hundred percent use Claude. To do all those code things. 'cause I wanted to,

[00:31:45] **Adam:** but in my defense, I didn't do it. I didn't do it just so I could solve it. Right. I I, 'cause what I noticed was that the people, a lot of people, 'cause some people will put their whole GitHub repository out there of how they solved everything.

[00:31:59] **Tim:** And they have these like pre-baked, like, so like, what's it called? The Dijkstra algorithm. So they have these prebuilt like. Algorithms, like a little toolkit basically, because it's, tends to be the same problems, shortest distance, A\*, Dijkstra, all these other, you, you know, route finding, compaction problems, all these very known things that had I done a CS degree and had, I would've be, had been very exposed to these and I just would've thought, oh, okay, that's a Dijkstra problem and I'll, I'll use that, but I didn't.

[00:32:36] **Tim:** Right. So. It. I don't wanna just like, you know, bother Adam Cameron or Adam Tuttle and go, Hey, what, what does this mean? I don't know what this, 'cause I remember you brought up, oh, that's a Dijkstra problem. Like, I didn't know what that was at the time, but I've grown since then. And so the point was to build this library in Python, which I, like I said, I don't know Python very, very well.

[00:33:01] **Tim:** I've played around with it a lot, but I don't know super well. To solve the problems and every problem it would. Once I, so I had it built a library. I said, go back and look at prior AOC problems. Build these algorithms out.

[00:33:15] **Adam:** of code, not Alexandria Ocasio-Cortez.

[00:33:18] **Tim:** Yeah, HER two, I don't know. But anyway, so it did, it built them. And then I said, please ex.

[00:33:24] **Tim:** And then after it solved each one, I said, please explain to me how you got to your answer so that I can do it. So basically I asked it to teach me. And so that was really the exercise was a can it, can AI do it? And it did it extremely well and extremely fast.

[00:33:40] **Adam:** Mm-hmm.

[00:33:41] **Tim:** not only did it like solve the problem, I also had it built.

[00:33:44] **Tim:** You talked about ff eg it would build like animations to like draw out the problem and visualize it. 'cause I, I'm visual, so I'm good. I'm very good at like, looking at the visual rep because when I hear the problem, like, like it's a path solving problem, right?

[00:34:00] **Adam:** Mm-hmm.

[00:34:01] **Tim:** like, all right, how did I actually do that? Now I can see the path it took and then at the same time I said, alright, show me the code that's related to this path solving problem. And so the code would come up and then I could look at the code, I could look at how it was figuring out where to go. And so that was really the, the goal for me was to educate myself on how to solve this myself.

[00:34:27] **Tim:** Not using ai, I solved ai. I would do very, very well on leaderboard if I just cheated and used ai, but it would be a cheat.

[00:34:33] **Adam:** Right.

[00:34:34] **Tim:** But I was using this to help me build a toolkit of things that I can understand. Now. I'm, I'm gonna try to actually solve this in ColdFusion

[00:34:43] **Adam:** Gotcha. So yeah, I mean, it sounds like what you were doing was using, 'cause the, a lot of times the hard part of learning is coming up with a reason to have this problem. Right? Like, you can only write so many to do apps and you don't need any route finding or, you know, sorting. Algorithms to, to to write a to do app.

[00:35:03] **Adam:** And so sometimes coming up with the problems are hard press. So that's a nice thing about advent of code is like, here's a whole bunch of different problems and every single one of 'em has a different, like part of your brain or different, a different lesson that is trying to teach you. And so you're trying to like learn these lessons.

[00:35:16] **Adam:** So, you know, this type of problem is, is solved by this type of algorithm. And now you, you're taking that long, you, you, you, it sounds like you intentionally did it with Python. It's easy enough for you to read. You can like use that to learn the concepts, but now you want to take that knowledge and apply it with a different programming language to sort of reinforce that learning, and I think that's brilliant.

[00:35:38] **Adam:** That's exactly what is the spirit of advent of code.

[00:35:42] **Tim:** And I think what you said earlier was is use AI to make yourself better.

[00:35:45] **Adam:** Mm-hmm.

[00:35:46] **Tim:** not just, I don't, I'm paraphrasing, you're paraphrasing, but make yourself better, not just to answer the question. 'cause you just answer the question, you're cheating. Right? It's like, it's like, I don't care how I got, you know, math test.

[00:35:58] **Tim:** I don't care how I, I don't wanna show my work. I just got the right answer. That's cheating. But if you understand the process, how you got to it, then that's learning.

[00:36:08] **Adam:** For sure.

## [00:36:09] Using AI to Make Yourself Better

[00:36:09] **Ben:** One thing that I struggle with with the AI, and I don't know. If, if you have any advice here is I'll ask AI the question and it'll give me, you know, like three pages of response. And I almost wish it would step through it because oftentimes what I find is I want to ask a question about like, the very first thing it said and not the two pages of content afterward.

[00:36:33] **Ben:** And I'm always, I'm like never quite sure how to, to navigate that disconnect and cadence.

[00:36:40] **Tim:** so I, I'll say this from my experience, Ben, what in what I did was there were certain problems. I, I saw how it solved it. I'm like, okay, that makes complete sense. I don't know why I didn't think of that. And other times I'm like, I really don't understand how you got to this answer. This doesn't not, and so my specific prompt was, I don't understand how you got to this answer.

[00:37:04] **Tim:** Please explain this algorithm and this problem to me. Like I'm a, I have a middle school education and it was extremely good of stepping through and it gave me like, illustrations and like, I don't know what, what's the word I'm looking for? It's like, it didn't just

[00:37:22] **Adam:** animations or whatever, like.

[00:37:23] **Tim:** Not, not animation, it wasn't animations, but it's like, it, it, it gave me like comparisons.

[00:37:27] **Tim:** Like, imagine that you are a so and so and you see this thing and, and if you, you know, so it was very like, it gave you concrete kind of visible, because I think human beings learn from creating images in their mind. Right? And so if you

[00:37:44] **Adam:** of us who can,

[00:37:45] **Tim:** yeah, it, I mean, abstract ideas are hard.

[00:37:48] **Adam:** yeah.

[00:37:48] **Tim:** They're, they're hard.

[00:37:49] **Tim:** And so it's a learned behavior to understand abstract ideas. So if until you can get that abstract idea in your head, having sort of an illustration, a metaphor to explain that abstraction is extremely helpful and it actually did a very good job of it doing that for me.

[00:38:06] **Ben:** You know, I had a moment the other day. Sorry, small side tangent here. Just underscoring that the whole thing is just a giant, really impressive statistical model. I was trying to work through a problem in chat GPT and it was trying to guide me and I was running into an error and I was typing in like, I'm trying to do what you're doing, but, and I went to type the open quotes for, for something and I accidentally hit the.

[00:38:37] **Ben:** Enter key instead of the quote key. So I submitted the question like without the actual question, part of the question, and it knew exactly what I was talking about. Like I knew exactly what I was gonna ask and be like, oh yes, of course you're running into this edge case where blah, blah, blah, blah, blah.

[00:38:52] **Ben:** And I'm like, what? That's bonkers.

[00:38:55] **Tim:** What, what's, so, what's what's bonkers is as I, so I started day one, I kept moving, and then at one point, I don't remember what day it was, it was probably around like day 12, 13 be, because there's a part, there's a, a, a test part, there's a, a part one, and there's a part two. Of every challenge, right? So there's like the test where you just build your tests and, and then there's a part one, which is the big data set.

[00:39:19] **Tim:** There's the second, the same data set, but you're looking for a different answer. And so I gave it the, I said, look at the data set over here. Here's the problem. And it gave me the answer for day one and day day one, or the day part one and part two, sorry. So it gave me the answer for part one and part two.

[00:39:38] **Tim:** I said, I'm sorry I didn't, I haven't given you the text, the clues for part two. How did you, why did you give me the answer for part two? He says, well, I extrapolated based off the, the first question, what the second question would be.

[00:39:56] **Adam:** Well, it probably is trained on advent of code data. That would be like prime training data.

[00:40:01] **Ben:** Yeah, but it's just,

[00:40:02] **Tim:** and it was right.

[00:40:03] **Adam:** Yeah.

[00:40:04] **Tim:** It was a hundred percent right. So.

[00:40:07] **Ben:** that is crazy. It's, it's like the, the numbers, the number machine that is running behind the scenes is so far beyond anything my stupid little human brain can even begin to comprehend.

[00:40:19] **Adam:** Yeah. I mean, I don't wanna, I don't wanna say nobody understands it, but to a degree, nobody understands it. Right? Like, this is, this is not a thing that somebody sat down and wrote.

[00:40:27] **Tim:** I mean, people, people understand the concept of it, but they

[00:40:30] **Adam:** I understand

[00:40:31] **Tim:** can't explain, they can't explain to you how it got to the answer it got.

[00:40:34] **Adam:** Right. Yeah. This is not a program that somebody wrote. This is a, like a plant that somebody grew basically.

[00:40:39] **Adam:** So like, yeah. You know, we planted the seed and we kind of encouraged it to grow in this direction, and we fed it and watered it, but it, it, it grew the way it grew and if we didn't like it, we would've thrown it away and grown another one, you know.

## [00:40:52] Blog Comments and Spam Moderation

[00:40:52] **Ben:** The other place where people have just ruined a good time is on blog comments. And I mean, this has happened across the internet, but it has also very much happened for me. just, you know, in addition to the fact that basically no one comments on stuff anymore. the people, this spam bots are happy to continue to comment with ferocious volume.

[00:41:13] **Ben:** And I did have to, a couple years ago add moderation to my commenting system, mostly just to prevent the spam. Because it's like, again, just people are trying to do a nice thing and you, you come and you ruin it.

[00:41:26] **Adam:** So what does your moderation system like? Are you just approving every comment before it goes live or

[00:41:31] **Ben:** Yeah. You can get a, I can white list people, so if every comment that comes through that has not been approved, I can either approve it as a one-off or I can essentially say, approve this person, this author, and then they'll just be approved going forward. And then I can

[00:41:48] **Tim:** none of my posts get through.

[00:41:51] **Adam:** So at, at the risk of, opening Pandora's Box and giving the spammers the information that they need to get through, what are you whitelisting based off of? Is it like email

[00:41:59] **Ben:** Yeah, it's just email address. I, I, I had originally coded, coded it so that it was based on email address and. IP address specifically for this thing that to where you're alluding to as I, you know, you can't just come and use someone else's email address to sneak spam in because it would be from a different IP address.

[00:42:21] **Ben:** So I would've had to approve ips as well. And I, I think I tried that for like a day and then immediately got rid of it because even within that first day, someone left two comments from different IP addresses and I assume it was, I dunno, like a phone to a desktop or something,

[00:42:35] **Tim:** Or, or if you're like on A VPN or off a VPN re reboot your computer, you're gonna get a

[00:42:40] **Ben:** I'm like, forget about it. This is too much work. And so far it's been, it's been pretty good. 'cause it, I, I also have a bunch of other little spam filters where you can't have, you know, Viagra in the content. I have, like, I have like 3000 words that it looks for at this point that you can't enter.

[00:42:58] **Ben:** And I'm sure I blocked some people accidentally, but, you know, unless you're telling me to bet big at a casino. Like legitimately, I'm, I'm just gonna take, I'm, I'm just assuming that you're not a a, a good actor,

[00:43:12] **Adam:** Right.

[00:43:13] **Ben:** huh?

[00:43:15] **Adam:** Yeah. I mean, go ahead.

[00:43:17] **Ben:** freaking kids at Halloween, man. one year we just, we just didn't wanna participate.

[00:43:22] **Ben:** Like we wanted to give out candy, but we didn't wanna actively participate in Halloween 'cause the dog, and we don't want people coming to

[00:43:28] **Adam:** So what did you leave a bowl out or

[00:43:29] **Ben:** left a bowl out. literally within 15 minutes we got our first kid, kid took the entire bowl of candy. I'm like, what a whole neighborhood. Anyway, kids.

[00:43:45] **Adam:** Yeah, it's messed up.

## [00:43:46] Quiet UI: A Passion Project Shut Down

[00:43:46] **Tim:** So, have you guys heard about Quiet UI?

[00:43:50] **Adam:** yeah, I saw

[00:43:51] **Tim:** Quiet. No. Quiet UI.

[00:43:52] **Adam:** Quiet UI. Yeah, I saw this on our discord. I didn't look too much into it, but it's, it sounded like a sad story.

[00:43:57] **Tim:** Yeah. So it's sort of the same thing. So this, this guy, he, uh.It was a very successful programmer. Worked on several really cool projects. Had a little side project he was calling Quiet UI, which is a web components open source thing. Released it about three weeks ago and then almost immediately shut it down just for the same reason.

[00:44:17] **Tim:** 'cause it's just, it went from. Like it got super hyped, like it started showing up, like people started blogging about it. People started inquiring about it, and people started like making these amazing demands of this guy's time. Just this one person who's creating a, a, a thing. And so if you go to the, you know, quietui.org now, it, it says no longer do available to general public.

[00:44:39] **Tim:** I'll maintain it, my personal creative outlet, but I'm unable to release it to the world this time. He did release it like three weeks ago, but now he's, you know, basically shutting it down.

[00:44:50] **Adam:** Mm-hmm.

[00:44:51] **Tim:** And I just, I just feel bad for people like that. Really, really smart people. Like they have a passion project, they create it, it gets almost too good for itself.

[00:44:59] **Tim:** It gets too much traction. And then it's like all these expectations, all these, demands that people start putting on it. And he's like, I already have a job. I don't, I don't, I don't need an unpaid one. So. But unfortunately, it's like there's huge portions of the internet that that's, it's some dude or girl or you know, whatever. Just working on a passion project that is like a very important part of the internet that just when they die or just don't show up, you know, one day it's like the whole internet will just fall over

[00:45:30] **Adam:** Like you were talking about with the guy who maintains ff eg and, getting the tickets from Google and stuff like, I think it was you earlier. I'm, I'm trying to give credit where credit's due. Oh, maybe it was Ben. Well, but I think was it, wasn't it you that was telling the story about how, Google, has like, this big apparatus where they find issues and file issues,

[00:45:50] **Ben:** Oh yeah, this was like the open source fuzzing project.

[00:45:54] **Adam:** they're, but they're not contributing to the fixing of any of these issues. They're just like, yeah. yeah. And see that, that little meta discussion made me forget the point I was trying to make. Oh, well,

[00:46:05] **Ben:** And I, I do remember looking at Quiet ui. It, it was very robust. I mean, it was, it's a component library built in,custom components, like, like native custom web components.

[00:46:16] **Adam:** oh, web components. Yeah.

[00:46:17] **Ben:** And, and there were like 40 or 50 components. I mean like really and documented. I mean, the guy really put a lot of effort into it.

[00:46:24] **Tim:** some reason, his success, he is like, Nope, shut this down. I've, I've, I've seen this movie.

[00:46:29] **Adam:** Yeah. I mean, it's not the same thing. a big part of the reason that I have kind of stopped working on Taffy stuff, not that I have any significant changes to make, but a big part of the reason that I don't work on anymore is just the. The rigmarole in, you know, pushing up a new release, you know, preparing that, updating the documentation, all that stuff, right?

[00:46:48] **Adam:** Like if I could snap my fingers and, and say like, okay, make me a new modern repo with. All of the, like, all the automation that's available, right? Like run the tests on pull requests, and when I merge to Maine, I want, a new release to be generated with release notes and you know, this and that and, and I want the documentation to be auto updated from this particular markdown file or whatever.

[00:47:11] **Adam:** That would be nice, and that might get me more interested in, in working on it. Really, at this point, the only thing that I think I would have any significant interest in, in a big change would be to convert it all to the latest, like CF script stuff. So t is still, technically CF eight compatible, which is, yeah,

[00:47:29] **Ben:** end of life. I don't know if you know that.

[00:47:32] **Ben:** It's that grave has other graves on top of it at this point. I think 2021 just went end of life yesterday actually.

[00:47:40] **Adam:** just let's, to, to maybe for those that are listening but don't know quotation stuff. So there was 8, 9, 10, 11, and then it was after 11. They started going by years and I think it was 2016, if I'm not mistaken. So then they did, it wasn't yearly releases, but it was, you know, year numbered releases. And then so they did 20, you said 20, 21 just went EOL.

[00:48:00] **Ben:** I think I saw Charlie Erhardt post about that on LinkedIn.

[00:48:03] **Adam:** Yeah. So, there's definitely some baggage that Taffy is carrying around for CFA compatibility kind of at, for no reason at this point. so I would be curious to see like how much nicer the code could be to work on if it went full script instead of tag-based. 'cause that was, you know, it's gotta stay tag-based to be, CFA compatible, or at least at the very least, like everything has to be wrapped in tags and then you can put CF script tags inside of it.

[00:48:27] **Adam:** But, yeah, like you were saying, you know, I have a job. I don't, I don't need to burden myself with deploy automation for a project that doesn't really need changes anymore. Like, it's, it's really stable. It works really well. My company's using it heavily.

[00:48:40] **Adam:** You know, we, we use it as a part of a system, sends 60 million emails a year, and collects many, many millions of dollars, every month.

[00:48:48] **Tim:** I use it every day.

[00:48:50] **Adam:** Yeah. So. And I have no issues, so.

[00:48:53] **Ben:** Yo. I remember year early on in my career, I had stumbled upon the fact that that that Java stuff that ColdFusion was using under the hood had that POI library, which is compatible with some of the early Microsoft products, specifically Excel was like the big one that people were trying to use. And I had like a, I think it was like poi, utils, cfc, just like a, a like a lightweight thing to call some of the Java methods.

[00:49:23] **Ben:** And I was so excited about it 'cause we were producing some Excel documents at work and you know, just to give people context, this was like 15 years ago and, it's like it all, it took to break my camel's back, which, you know. To be fair, I have a very low tolerance for inconvenience. Like, it all took us, like one or two people to be like, Hey, I'm trying to get this like fixed cell, you know, like fixed row to work or like, I can't get this to work and this version of Excel.

[00:49:49] **Ben:** I'm like, that's it, I'm done. I don't care. Like, like the thing that I was excited about has now become a problem and I don't wanna do that. And after, after that, I was like, that's it. I'm just never gonna. I'm never gonna release anything again, and I'm not throwing shade on anyone. You know, people had questions about how to use it.

[00:50:07] **Ben:** That's totally fair. It's just, it wasn't the journey I meant to sign up for, you know, I just wanted to share something fun. I didn't wanna maintain it or support it in any way whatsoever.

## [00:50:19] Ben's POI Utils and Low Tolerance for Inconvenience

[00:50:19] **Adam:** I mean, there's the temptation. I think these days you'd have to kind of start the project with this in mind, but I, I feel like if I found myself at the foothill of that mountain, I might be like, oh, okay. I made this thing that's useful to me, and you want a change to it. You are now a committer on the repository.

[00:50:35] **Adam:** Have fun.

[00:50:38] **Ben:** Yeah.But I, I've, I justify it in my, not justify is not the right word, I rationalize it, it feels like the wrong word also. Anyway, I rationalize it in just realizing there are people in this world who have different strengths at different things, and there are people who love being part of an open source project and they love maintaining, they love being part of that, that community and that culture and the team that works on it.

[00:51:03] **Ben:** and I'm just not one of those people and I'm like, I just have to be okay with that.

[00:51:08] **Tim:** Some people are just obsessed with a certain thing, right? That that's, that's their thing. They, and they're like, okay, I'm gonna just make sure this thing, I'm gonna be this thing and maintain it and whatever. The other people are like, I did a thing. Yeah, okay, that's cool. They drop it and go to something else.

[00:51:26] **Adam:** I was just thinking too, I mean maybe this is more of an after show topic, but maybe like doing advent of code with my kids might be a good way to like get them

[00:51:35] **Tim:** See, I'm, I'm, so, I'm trying to get Max. I, I introduced it to Max and I showed him what it does, and he is like, oh yeah, because a lot of the stuff he's learning in school is applicable to what advent of code is. I'm like, you. She's, we'll see. 'cause it is like his, his break. We'll

[00:51:51] **Adam:** Mm-hmm. Yeah.

[00:51:52] **Tim:** come on, let's, let's try it.

[00:51:54] **Tim:** So see if you can code against your old dad. I'm pretty sure he would beat my, I'm pretty sure he would beat my butt, but he's already building, like for his classes, he's having to build like a, a virtual machine that handles memory and, you know, simulates and like he's already doing some of these

[00:52:11] **Ben:** Dang.

[00:52:11] **Adam:** Right.

[00:52:12] **Ben:** I did not do any of those problems in school.

[00:52:15] **Adam:** So you said that this year's advent of code is only gonna be 12 days.I'm, That's fine. I, I am certainly not trying to throw any shade his way. And, let's, I, I did look it up. Let's, actually give credit where credit to is due. We've, we've said advent of code so many times, we have to say it's made by Eric Wastl.

[00:52:30] **Adam:** yeah. So, he doesn't give his pronouns on the about page, but I assume it's he, him. anyway, I, I was just curious like, If I was going to be, if I was in his shoes and I was changing it from 25 days to 12 days, then I might try to make it land on December 24th or 25th as the last day. But he's doing, starting December 1st.

[00:52:50] **Adam:** Do you have any sense of why he started on December 1st? Maybe just from tradition or,

[00:52:54] **Tim:** I think from traditionally, 'cause it's always where he started it,

[00:52:57] **Adam:** Hmm. Okay. Just.

[00:53:01] **Tim:** And they're ever gonna enjoy their actual Christmas without having to do code.

[00:53:05] **Adam:** Yeah, I mean, you, you might be onto something there

[00:53:08] **Tim:** I mean, who wakes up December, 2020 fifth and goes, ah, I gotta do my advent of code. So I get my best score. Oh, wait, I, I know who nerds.

[00:53:18] **Adam:** us, no. We're the, if they really, if it's that important to them, they're staying up till midnight so they can get it. Uh, it dropped.

[00:53:24] **Tim:** Yeah.

[00:53:25] **Adam:** Anyway,

## [00:53:25] Patreon

[00:53:25] **Adam:** well then this episode of Working Code was brought to you by the Working Code Podcast, discord advent of Code Channel, and listeners like you.

[00:53:33] **Adam:** If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our Patriots cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo.

[00:53:47] **Adam:** You guys rock.

## [00:53:48] Thanks For Listening!

[00:53:48] **Adam:** We, like I mentioned, are gonna go do the after show. That's the outro. Music keeps playing. And then if you are one of the few, the proud the patrons, then we keep talking while everybody else exits stage left. And we just keep putting more of this stuff in your ears. And you know, sometimes we're on topics, sometimes we're off topic, sometimes we talk about tv, sometimes we keep just rambling on.

[00:54:09] **Adam:** But, I think, I'm not even gonna get into it. If you wanna know what's on the after show this week, you're just gonna have to be a patron and then you'll figure it

[00:54:14] **Tim:** It ain't

[00:54:15] **Adam:** and you get,

[00:54:15] **Tim:** It's just a couple bucks.

[00:54:17] **Adam:** yeah, it's a cup of coffee,per month, minimum. And, and, you get access to all the, the back episodes of the after show as well.

[00:54:24] **Adam:** They're all there for you, with chapter markers. So, we would love to have your support. That's all I'm gonna say about that. If you wanna help us out, you can go to patreon.com/workingcodepod, throw a few bucks our way. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:54:36] **Tim:** so listen. You people are the reason we all have nice things, so your heart matters.

[00:54:42] **Ben:** Yo, so true.

[00:54:44] **Adam:** Thanks for potting with us, as they say.
