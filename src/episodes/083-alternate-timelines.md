---
title: "083: Alternate Timelines"
description: "The crew shares some of the other professions that could have been."
date: 2022-07-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/083-alternate-timelines/id1544142288?i=1000569773706"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

We all love writing code. Honestly, here on the show, it's hard for us to imagine doing _anything other_ than building beautiful digital products for our beloved customers. But, as a thought experiment - in these post-pandemic times - the crew wanted to share some of the other professions that _could have been_. From ice cream truck driver to organic chef to movie theater entrepreneur, we dive into the untapped world of alternate realities.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/083-alternate-timelines.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** My ultimate backup profession was gonna be working at blockbuster.

[00:00:06] **Tim:** I hate to tell you something.

[00:00:08] **Ben:** I thought if none of this computer mumbo jumbo worked out, then at the very least I could stock videos at the blockbuster

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go. It is show number 83 and on today's show, we're going to discuss what we would've done if we weren't software developers. but first as usual, we're gonna start with our Tramon fails.

[00:00:47] **Adam:** Carol has the, to be on a honeymoon. So, we're just gonna have to start without her.

[00:00:52] **Tim:** Crazy love

[00:00:56] **Adam:** I'm coming. What's.

## [00:00:58] Ben's Failiumph

[00:00:58] **Ben:** Yeah, I'm gonna kick it off with a, fail Y and that's a, an undecided triumph for failure. I started refactoring a bunch of code at work and,primarily what this entails is just moving things around the file system. we're on a very old angular JS platform and in the very, very early days, Angular JS their docs actually recommended splitting up controllers, views, and directives all into separate folders. And, the problem with that is that to look at a very specific feature, you now have to go search for files in various places of the file system. That just makes it a huge pain, even with keyboard shortcuts, for jumping to various files. So as I've been building new features, I've been, co-locating all of the related files in the same directories, and then trying to have a directory structure that more or less mirrors the visual hierarchy of the app itself so that you can think, oh, this is in the people section.

[00:01:59] **Ben:** And then it's in the team detail section. And then the file system sort of reflects that as well, but that's for the new stuff. So I have, a decade of really old, really poorly organized code, and I've started to shift around some of the files to be in, in the kind of more modern. Formatted file system.

[00:02:19] **Ben:** And, it's one of those things like you get eight or nine hours into refactoring stuff and because it's all source control, it's not like I'm just harmlessly, moving stuff around. Every time I move files around, it's a poor request that someone has to review and I have to try to keep it under,I don't wanna overwhelm people moving stuff around, so it has to be very incremental.

[00:02:37] **Ben:** And then I have to rename template pass to reflect the new folder, pass that things are located at it's not trivial work. And I got like eight hours into it. And I had started have this panic where I'm like, is anything that I'm doing actually adding value because I've been able to maintain the application up until now.

[00:02:55] **Ben:** So it's not like this is a roadblock and I need to unblock myself, but I think there is an implicit value to having better organized code. But it's just, I don't know if I'm just wasting time. Like I know in the past we've talked about just the act of talking about doing something there's like so much reward, self reward about talking about it.

[00:03:15] **Ben:** You actually can like never actually do the thing. and I'm wondering if refactoring just makes me feel good, cuz it feels like I'm doing something, but I don't actually know if it's gonna make my life any better at all. So all this rambling to say triumph in the fact that I think cleaner code has value to it, but possible failure in that.

[00:03:35] **Ben:** Am I actually unlocking any value that wasn't there before in terms of future refactoring, future maintenance, or am I just sort of treading water, and making myself feel better?

[00:03:46] **Adam:** Well, so Ken Beck, the guy who wrote the book on TDD, like literally has this great saying that I really like. That comes to mind here, which is

[00:03:55] **Adam:** first, make the change easy asterisk, then make the easy change. And then the asterisk is defined as this may not be easy. Right. So, but it rings true. Right? So sometimes you have to like rearrange stuff, refactor in order to make an upcoming change easier or, maybe it's just gonna make ongoing maintenance, easier, that sort of thing.

[00:04:17] **Adam:** So if you're setting yourself up for future successes, then there's value in that.

[00:04:21] **Ben:** and I think part of it too, is that I have to lean into the idea that this is not gonna be a fast refactoring, that there's so much code. That I can't one, I can't stop everything that I'm doing and refactor the code until it's clean. That's just, it's not feasible. and two, I have to realize that it's just gonna take a while and maybe I have to do it very incrementally.

[00:04:43] **Ben:** So instead of carving out large blocks of time to refactoring, maybe every day, one of the first things I do is spend half an hour refactoring, one piece of the old code. And then, if I look up in, in four months, maybe I've refactored a tremendous amount of code that would've otherwise felt overwhelming if I had tried to do it all in one shot.

[00:05:03] **Tim:** hate to ask this, I'm gonna put on my management hat. is this. Code that's the legacy code that's gonna be going away.

[00:05:12] **Ben:** So, yeah,

[00:05:13] **Tim:** so I'm coming for the point of what's the point, if you're just doing it, if you're just doing it so it could be better maintain and you're not gonna maintain it, you're just wasted, dime.

[00:05:21] **Ben:** Ah, I know. So, so that's the other thing that, that weighs into it, obviously. but I,the more clean the code is I think the more likely I am to wanna follow through with ideas for improving it, because it'll be less painful to work with. I don't know if that's entirely true, but I feel like that's true,but to your point, I'm also having doubts about arbitrarily changing the code.

[00:05:45] **Ben:** I think maybe what I need to do is if I have an idea for an improvement in a specific area of the application, this is actually going right back to what Adam was saying is maybe first that's the opportunity to clean up that particular piece of code. Then once it's in a cleaner state, I can apply some more improvements, but the, yeah, not just arbitrarily, like.

[00:06:06] **Ben:** Shooting across the entire code base, trying to improve it just like focus in on one particular area. I think maybe that was the panic that I had after my day of refactoring, where, it just felt like it was gonna be overwhelming. There's so much to do, and I just need to do a piecemeal. And then I think maybe the missing ingredient there was that the piecemeal aspect should be, I wanna do something else here.

[00:06:29] **Ben:** And the piecemeal part will be the prerequisite to, to clean up some code before I do the thing I actually wanna do.

[00:06:37] **Tim:** Yeah,

[00:06:37] **Ben:** just, it's having dirty, disgusting code is painful, emotionally painful.

[00:06:42] **Tim:** I get it.

[00:06:44] **Ben:** Anyway, so that's what I got going on, Tim. What about you?

## [00:06:47] Tim's Triumph

[00:06:47] **Tim:** I'm gonna go with a triumph. So I talked last week. How. Was it last week Carol was here. So maybe it was two weeks ago how I was delegating all the fun parts of my job.

[00:06:57] **Tim:** mm-hmmAnd so I'm trying, I'm finding a better balance there, a balance in the force,coding versus my management duties. So this week, they dropped on me some strategic, strategic kind of.

[00:07:08] **Tim:** Quarterly review stuff that I have to do. it's a new responsibility for me that I haven't had to do in the past. It's a, so I'm going up to the next level of delivering information to people. I've been kind of dreading it. I knew this day would come, but I've been working on that this week, but at the same time,working on some interesting tech and some stuff that, that I'm actually excited about doing and, manage not to.

[00:07:32] **Tim:** Because normally in the past, I would just kind of focus on what I enjoyed and then kind of put off the other stuff. So I would I'm block scheduling my time to say, all right, I'm at least spending an hour and a half, at this time, early in the morning. to deal with the, the strategic stuff that doesn't really grind my gears and spread spreadsheets and PowerPoint presentations and stuff.

[00:07:56] **Tim:** And then after that,I can work on the fun stuff. So it's like, I've been keeping a better balance. So I'm proud of myself for that. Don't know how long that'll last This is a good week. last week I had a few days where I just didn't feel like, even getting out of bed, but, yeah,this week's been a lot better.

[00:08:13] **Tim:** So feeling good about that.

[00:08:15] **Ben:** Nice.

[00:08:16] **Tim:** Anyway, so, so that's me. How about you, Adam?

## [00:08:18] Adam's Triumph

[00:08:18] **Adam:** I'm gonna go with the triumph, but it's gonna start in a little bit of a dark place. I , , I, so I have depression, I take antidepressants for it. I had a day this week where my depression kind of kicked into high gear. and I had some important meetings that day, so I couldn't really take off. but you know, like one of my, it was just one of those days where like, I don't feel like doing anything, it just, everything pissed me off and I, there were important things to do, but I just didn't feel like doing any of it.

[00:08:41] **Adam:** it would've been a bad day for there to be an emergency, but Hey, luckily there wasn't. so what I did, what I ended up. Was I picked like the lowest priority thing on my to-do list. And I just did that, like, meaning like the most menial, tedious, like boring, but it requires no mental effort task that I had available to me.

[00:09:02] **Adam:** It's just like, I'm just gonna do this. And what it ended up being was, like updating hundreds, if not thousands of SQL files and just making like small changes to them, basically wrapping a transaction around two things that we were doing a lot, like steps that would come after each other and making sure that they always were executed in a, in an atomic set.

[00:09:23] **Adam:** So if one failed, then the other would fail with it. and yeah, man, like, and it took me a day and a half to go through that for all of the scripts that I needed to update, but it was a good way to get through.

[00:09:32] **Ben:** So you have like dot SQL files laid around what.

[00:09:35] **Adam:** Yeah. Okay. So I was, it's not that I'm trying to hide it, but I was trying not to get too into the weeds on this. So it's again, referencing this project that I've got where we're doing the queued file imports. Right. And so

[00:09:49] **Ben:** The nightly ones.

[00:09:50] **Adam:** Yeah. Yeah. And so each file,it's not just import the file, there's more to it than that, right.

[00:09:54] **Adam:** So we have to create a new table, import the data into the table. You might have the massages a little bit, you might have to update some lookups that reference that data,and other things. and so the way that it works is that each step in that build process is a separate file. And some of those are SQL files, which would just, like load off the disc and then, send the contents of that to the database.

[00:10:14] **Adam:** As a query. There are some also that are in this case, JavaScript files that are so, okay. It loads the JavaScript file as a component. Like you would load any node module. and it, contains it exports, a function called execute, which expects a few specific standardized documents, like the, a connection to the database and some helper functions for various things so that it can do a variety of different things that you can't do with just standard SQL, where you might need to go fetch something from an API and, and deal with it that way, or sort of thing, something that sort of thing.

[00:10:46] **Adam:** Anyway. So yeah, we have hundreds, approaching probably thousands of these, files. And like, it's funny because like, the they process is, create a, if the table is called warehouse it's warehouse, underscore new create warehouse, underscore new, populate it, do all the things you need to do.

[00:11:01] **Adam:** And then the last two steps are delete warehouse and rename warehouse underscore new to warehouse so that you were just replacing it. Well, the thing that I was combining is delete and rename so that you never have like delete. And then for some reason, renamed fails. Get you get stuck in a position where you just don't have that table.

[00:11:19] **Adam:** and so I was wrapping that in a, MySQL transaction.

[00:11:22] **Ben:** seems like a good one to have in a transaction.

[00:11:25] **Adam:** and it's, it was not difficult work, but it was a day and a half of like, I could probably sit here and list out all the keyboard strokes that I was doing, cuz I was doing the same stuff over and over. It's like, okay, open these two files, copy from here, paste it over there and blah, blah, blah.

[00:11:39] **Adam:** I don't wanna go through literally all the keyboard strokes, but I could tell you what they were to like, move stuff around and paste from this level of my history and

[00:11:46] **Ben:** that's really good though. I think the small tasks to keep the movement going, to keep the machinery firing the blood pumping. I think there's a huge power in that in, in being able to lean on that. Yeah.

[00:11:57] **Tim:** I admire you for being open about it, about depress. I'll be honest. I only said I saw on the show notes, you were gonna talk about that. And that's the only reason I mentioned last week that, several days, couple days there where I didn't even wanna get outta bed, I don't think I suffer from depression, but there's just days it's like, I can't, I just can't.

[00:12:17] **Adam:** Oh man. world right now is not helping either

[00:12:20] **Adam:** at least our country.

[00:12:21] **Tim:** Yeah. Stuff so crazy right now. It's just, it's like, what is the point sometimes? we're just gonna get in world Wari and then yeah. So I don't know if necessarily that was like foremost of my mind is just like,

[00:12:32] **Tim:** Yeah, but being able to talk about it, I think it's important, especially men. I don't think men talk about, Hey man, I'm just, I'm a little depressed today, right? We're tough. Right. we wanna be tough. We wanna project strength. We don't wanna look weak. so just to talk about it, normalized talking about it, I think's important.

[00:12:46] **Tim:** So I appreciate that.

[00:12:48] **Adam:** I agree. Yeah. I mean, I will be the first one in line to tell people that there's nothing wrong with taking medication for things like depression and other mental health issues and seeing therapists. I've done a bunch of be who, of those things. and it's made me a better person and better able to deal with my life and, just to be a healthy, happy person. So

[00:13:10] **Ben:** I haven't, I've not been on, on, on like mood altering medications. So I can't speak to that obviously, but,

[00:13:16] **Adam:** you

[00:13:16] **Adam:** sound like you could use some antipsychotics.

[00:13:20] **Tim:** Wow.

[00:13:20] **Tim:** I,and I hope this analogy doesn't trivialize anything. Cause that's not my intent, but I have this thought the other day. So my wife recently turned me on to sunglasses. I'm I haven't had sunglasses my entire life said, turn me on. And I, that's not what I thought

[00:13:36] **Ben:** I,

[00:13:38] **Adam:** there's there.

[00:13:39] **Ben:** I have like real official prescription sunglasses with the. Good frame, you know,good lenses and, was it polarized lenses and everything? Anyway, I'm sure I'm not telling most people hear what they don't already know because they own sunglasses, but it, it, it like, I could not get over how much more comfortable they made it to be outside.

[00:13:59] **Ben:** Like, it didn't just change how I looked at things like it changed my whole physical demeanor outside. I felt more comfortable. Temperature wise. I felt better. And it's just like everything from being able to see anyway, I'm going somewhere with this. I promise.

[00:14:13] **Tim:** wait, please tell me. They're like,they're like Tom cruise aviators.

[00:14:16] **Ben:** they're like Maui gyms or something.

[00:14:18] **Ben:** it's not a brand I'd ever heard of before for

[00:14:21] **Adam:** Maow Jim is kind of a big brand, but go

[00:14:23] **Ben:** is it maybe that's not what it is. I don't even know. I don't even know.

[00:14:26] **Tim:** your wife has good taste.

[00:14:27] **Ben:** it was it's the optometrist help pick it out for me.

[00:14:30] **Tim:** Your optometrist has good taste. they're probably expensive. That's why they wanted you to get 'em.

[00:14:33] **Ben:** I'm going somewhere with this. So I really enjoy having the sunglasses on outside. They do make the colors just slightly less vibrant.

[00:14:43] **Ben:** Like I have a gray lenses. I don't know what that means. Exactly. but I walk outside and it's, I can see everything better. I function better, but there's like, everything's slightly less intense. Like it's less vibrant. The greens are less

[00:14:58] **Tim:** it's almost as if it's filtering out some of the light to make it less intense.

[00:15:03] **Ben:** so, and so what I'll do sometimes is I just try to take them off.

[00:15:06] **Ben:** I'm like, oh, you know what I want, I wanna be exposed to that, like intense outside experience

[00:15:11] **Ben:** It's not gonna turn you into the Hulk. It's not gamma radiation, man. mm-hmmSo I'll take them off. And I'm like, oh yeah, things are brighter. And then they're more vivid, but then I'm just eventually, like two minutes later, I'm like, yeah, but I'm squinting and I'm uncomfortable. So I wanna put my sunglasses on anyway, going back to mood altering drugs, a lot of what I see in pop culture.

[00:15:30] **Ben:** And I don't know if this is representative of anything. Is like, people will function much better on mood altering drugs, but then they get to a point where they feel like they want to go off it because they're functioning well and they, or like, or they,

[00:15:42] **Tim:** Keep saying mood altering drugs. We're not talking peyote. We're talking

[00:15:46] **Adam:** yeah, yeah, yeah, yeah. I just mean, like something that, that is affecting how you experience the world is all, I mean, that's to, to the point you were making though, Tim, like, some people, if they're having like anxiety or whatever, CBD is, a very valid.

[00:15:59] **Ben:** you,

[00:16:00] **Tim:** My daughter takes it like every day.

[00:16:02] **Tim:** Yeah. Ben, go

[00:16:04] **Ben:** I, you know what, the only thing is like, it was an analogy that I suddenly felt like I could relate to on some level, world maybe different from what other people are experiencing. But it's this idea that like you're cognizant of the fact that maybe.

[00:16:19] **Ben:** There's something just like something little missing or like something's a little different, like your emotions are not as intense or like, your highs and lows are like, not as, quite as high and low. And there's something that you can sort of miss about that even though, that you're functioning better with those things.

[00:16:33] **Ben:** And it's like, for me, like the sunglasses I have, like, it made sense all of a sudden to me that I function and I'm much more comfortable to sunglasses on, but every now and then I

[00:16:41] **Tim:** like these people that are bipolar, they're really good on the meds. And they're like, oh, but I, I'm missing those highs. So they stop it and their life falls apart. Is that kind of what you're

[00:16:50] **Ben:** I, I guess so. I mean, I don't know, bipolar. I don't even know if it has to be that degree of swing. I'm just saying like some people, I, I don't know, forget it. This is it just, I felt like the sunglasses gave me insight into something that I had. cause like when I was younger and like my brother, I think my brother's always been very hesitant.

[00:17:08] **Ben:** he's had a lot of, Anger issues, maybe. I don't know. He's got some mood issues and I think he's always been very hesitant to go on anything because he didn't want that dampening effect. And when I was a kid, I couldn't understand it. I'm like, why would you not wanna take something that would just make you better?

[00:17:24] **Ben:** Like, it seems I couldn't understand any hesitation. cuz cause you know, I only approached it from a very logical sense because I didn't have anything to relate to. but so sorry, I know this is rambling and ridiculous, but the sunglasses gave me that sort of like epiphany, but I'm like, oh, okay. I get it. Like I get what you're saying now.

[00:17:47] **Tim:** Well,

[00:17:48] **Ben:** okay. I'm sorry.

[00:17:48] **Ben:** I apologize.

[00:17:50] **Adam:** why I take steroids every day. oh, Ben, I love you.

[00:17:51] **Tim:** you've had a life altering experiences due at sunglasses. That's awesome.

[00:17:55] **Ben:** I love my sunglasses.

[00:17:56] **Adam:** Yep. Okay. well, who wants to start? If you couldn't be a coder right now, what would you do? Like there's a, there's so many different ways we could look at that and that's why I thought this was a good question. A good way to good topic.

[00:18:09] **Tim:** Yeah. I appreciate who one of our patrons or.

[00:18:12] **Adam:** So that was from Brian Connor.

[00:18:14] **Tim:** Brian. Yeah. So, Brian, thanks that's a good question.

## [00:18:17] Tim's High School Aspirations

[00:18:17] **Tim:** Cuz if you had asked me in high school now I love computers. I mean you, if you listen to the origin stories, episodes, I mean 12, 13, 14, 15. I was all about the computers. That's all I did all the time was coding and I was school's it guy, but then I got, once I, I hit my growth spurt and I got taller and better looking, all of a sudden I was getting attention. I did. I was, I didn't wanna be seen as computer nerd anymore. I, so

[00:18:42] **Adam:** looking like Gollum

[00:18:43] **Tim:** so I, I got into like a drama club and, just into different, like entertaining. I became very much an entertainer. I was voted the class clown. I mean, In high school. I was, if you'd asked me then I was going to be on Saturday night live. And that was like a real goal of mine. I knew every line of every Saturday night life.

[00:19:03] **Tim:** . This is one of the golden ages of SNL where we had Eddie Murphy on the show, Billy crystal. I mean, every skit, well, looking back, of the

[00:19:11] **Adam:** Some of them age better

[00:19:12] **Tim:** yeah. Some of them made and so it's like, I knew all, and there was a guide school Blair and him and I would riff every day, like doing skits and like coming up with skits.

[00:19:23] **Tim:** So if you'd asked me when I was in high school, I would definitely would've been a comedian, a standup comedian.

[00:19:28] **Adam:** Were you like the class clown, like disruptive wise

[00:19:31] **Tim:** Uh, yes. Yeah. I'm there. If

[00:19:34] **Adam:** hated you? I.

[00:19:35] **Tim:** most teachers love me, but if I, if a teacher bored me, I. Because I usually knew the subject pretty well, that the teacher was talking about. There was one teacher, she was a history teacher and I was really into, I loved history. So I would read extra books, say, if I knew we were discussing this part of the, like the Roman empire, I would read like biographies of all these different, like, people and find like the most juicy, period details about every single emperor.

[00:20:03] **Tim:** and I would just lead her, I'd ask questions, fanning interest, and then lead it into a dirty joke. and so one, one day, one class, she just, she basically just threw the chalk to the ground and went outta the room, crying after a joke. I pulled, I mean, every, the whole class, just, I don't remember what, I don't even remember what it was cuz I was doing it constantly to her cuz she just, she wouldn't tell interesting facts about these people.

[00:20:27] **Tim:** And so I brought something up, she threw the chalk down, storms out crying the whole.

[00:20:32] **Adam:** like laughing so hard, she's crying sort of thing, or just upset

[00:20:35] **Tim:** up frustrated, crying.

[00:20:36] **Tim:** She was angry Ang. She was angry, crying. not, she wasn't laughing cuz everyone was laughing at me, but they were also laughing at her cuz the joke was pointed at her.

[00:20:44] **Tim:** But anyway, so I went outside, said everyone looked at me like Tim, what'd you do? I'm like, oh, so I went outside. I'm like, what's going on? She's like, I just can't get through to you. You're so smart. But you just don't I'm like, I'm sorry. Yeah. So yeah, sometimes, but most of the time I was a force for good, but yeah, but sometimes it could be evil.

[00:21:04] **Ben:** were voted class clown. I was voted first to get married.

[00:21:09] **Tim:** How'd that work out

[00:21:11] **Ben:** It took a long time. I finally got there.

[00:21:14] **Tim:** now? All your classmates can finally get married. Congratulations.

[00:21:18] **Ben:** I.

[00:21:18] **Adam:** They've been waiting for you.

[00:21:19] **Tim:** Yeah.

## [00:21:20] Ice Cream Truck Driver

[00:21:20] **Adam:** like I was saying, there's a lot of different ways we could look at this and I feel like, the first one I wanna throw out there is ice cream truck driver. which is what I say on any given day. I probably say it a hundred times a year.

[00:21:30] **Adam:** Now, you know that like, if something's really frustrating me, if I'm trying to figure out how to use some third party API in the documentation's garbage, and I'm just like, I chose this career path, I could have chosen anything, but I chose to come here and read your crappy documentation and be frustrated and lose my hair and, grind my teeth at night because you can't write good technical documentation.

[00:21:51] **Adam:** and so I always say like, I could have been an ice cream, man. you show up, you flip on the music, you drive around, give the kids, their ice cream and you go home Could have been so much easier. and like, it's a joke, but also is it.

[00:22:04] **Ben:** There's some fancy ice cream trucks. I see sometimes with like, artisanal ice cream. So it's a, you could really have some fun

[00:22:11] **Adam:** Oh yeah. Like food trucks can do anything anymore. it's like there's chicken and waffles trucks or there's I don't know. there's all kind, there was one I was trying to think of in Philly, but I don't eat the little cookie things that they make, so I don't know what they're called.

## [00:22:22] Movie Theatre Owner

[00:22:22] **Ben:** When I was a kid, I was absolutely in love with movies. I watched as many movies as I could, and I would go to the movies all the time and I would talk about movies with my friends and we would quote movies constantly. and I always thought it would be amazing to own a movie theater.

[00:22:40] **Adam:** Oh yeah.

[00:22:40] **Ben:** And,and I had all these fantasies about it being super plush, which nowadays there's actually movie theaters that are kind of like what I had fantasized about where people would have these big plush recliners and food service.

[00:22:53] **Ben:** and like now you can actually go to movie theaters that have recliners and food service. So, in a way, I guess I was sort of a trend setter, even though I wasn't actually demonstrating any of that , but I, even today, I still think it would be really fun to have a little movie theater and put your own slant on it and make it quirky and decorative.

[00:23:13] **Adam:** And I don't know. Well, you guys are buying a house or in the process of it, right?

[00:23:17] **Ben:** Yes.

[00:23:18] **Adam:** Did you, I mean, it's your first house that you've owned, so obviously, there's nowhere to go but up, but, did you, by any chance find something that's and I know you're in New York, too, so spaces at a premium, but did you find something that, where you can have like a, a movie room where you have like, perfect seating and a big screen and good sound?

[00:23:37] **Ben:** I, so there's a finished basement and I think there might be some opportunity there. Uh,yeah, so that could be,that could be my future

[00:23:45] **Ben:** little, little popcorn machine or something. I

[00:23:47] **Tim:** Yeah. Little so. Yeah. That, so when we bought this house 11 years ago, it was a mostly unfinished, like used to be a garage and it was turned into a mother-in-law suite, but it had a huge, this huge giant, like rectangle room, like movie theater.

[00:24:04] **Adam:** Mm-hmm

[00:24:04] **Tim:** the 3d projector and the big screen on the wall and we used it a lot starting out with, but it's like, now we maybe use it like once a month.

[00:24:13] **Tim:** It's gotta be, it's gotta be an experience. Right. It's gotta be like a movie. We really wanna watch the whole family.

[00:24:19] **Adam:** oh, man, I can't wait till top gun comes out on like, if it's on their streaming or, when you can finally get it, on blue Ray or buy it from 'em or whatever, like. Oh, it's gonna be, that's gonna like, just be so awesome. I really enjoyed it in the theater. I would more than happily pay another 20 bucks to go see it again.

[00:24:34] **Adam:** And probably about the third time that I paid 20 bucks to go see it again. My wife would smack me and say, you can wait.

[00:24:40] **Tim:** Yeah, right? Yeah. 4k streaming. So,

[00:24:44] **Adam:** Oh man. Good movie. okay, cool. So, another angle that I wanted to think about here is what if like the reason you can't be a coder is because the technology stuff just like doesn't exist. Right? So, there's no, there's, it's just doesn't exist as a job. Not that you can't do it for whatever reason.

[00:25:01] **Adam:** what then?

[00:25:03] **Tim:** So this is an alternate universe

[00:25:05] **Adam:** Yeah, I guess so like the, yeah, so you didn't even know it was ever an option.

## [00:25:10] Parks Department

[00:25:10] **Ben:** Well, I'll tell you. So I went to school for computer science and I think like the summer of my junior year, like between junior and senior year in college, I had this sort of. Moment of panic, where I thought that, being inside in an office was just gonna be absolutely terrible. and I had just been really starting to get into hiking and reading, like, bill, Bryson's a walk in the woods and looking at trail maps and stuff.

[00:25:39] **Ben:** and I had this idea that maybe what I should do with my life is become a parks department employee, and like maintain trails and the yeah. Yeah. Like being outside all day and hiking through the woods and fixing up camp sites and helping people who are in trouble, it seems super attractive.

[00:25:56] **Ben:** and I, and for a brief moment, I mean, this is maybe like a two, three week period. I thought I had made a terrible mistake going to school for computer science, that passed. And I've since been,extremely happy, but, But there was a brief period where I really thought it would've been awesome to be in the parks department, communing with

[00:26:17] **Tim:** It's funny. So I'm so I'm thinking about my early life. I, yeah, after I made that pivot where I decided I didn't wanna be a nerd

[00:26:25] **Ben:** really.

[00:26:25] **Tim:** I had this, like, I, I was full nerd and then I was like, no, I don't wanna be a nerd anymore. went totally like creative type. So like when I moved to Brooklyn, 1990, I was in Brooklyn for four years and, had a band, I was trying to break through as a musician.

[00:26:40] **Tim:** I was a singer trying to get into acting and stuff. So yeah. Yeah. It was complete failure and I couldn't afford living there, so I eventually had to move back. but yeah, I mean, I guess that's kind of why I do the, the extra background work. Just kind like get that taste of what could have been.

[00:26:56] **Adam:** I could have been a contender. I just needed someone to gimme a break. You know,was your band called?

[00:27:02] **Tim:** my band, the Caesars.

[00:27:05] **Adam:** Okay. That's why

[00:27:06] **Tim:** yeah. That's why I failed. Yeah. Yeah, again, that history tie in. So yeah. But yeah, we had different bands. We, it, it was during the swing dance kind of phase. So it was kind of a slight, it wasn't a full big band and we couldn't afford that, but you know, it was kind of like the Harry con Jr kind of kind of stuff.

[00:27:24] **Tim:** So yep. Did not work at all.

## [00:27:29] Lawyer/Doctor

[00:27:29] **Adam:** Yeah, the, actually the whole reason that I went into computers in the first place, I mean, I guess it was in part just because I was kind of following in my dad's footsteps, but also a big part of the reason that I did, like the full commit at an early age was, he told me like, computers are definitely gonna just continue to grow and climb and be more and more important in everybody's lives.

[00:27:51] **Adam:** And this was like around the year, 2000, if not a little bit earlier. And I mean, obviously he was right, but,he had that foresight to be like, go and learn how to. Right software, because there's gonna be a ton of need for that. And there will be a huge amount of money there. And that's why I went that way.

[00:28:09] **Adam:** And I, if I, if technology, wasn't what it is now, if we're in this alternate universe, I think probably where I would've gotten that advice to go. Would've been, doctor or lawyer, which I think our interesting things to, for me to consider. Cause I love a good argument. like, and I'm,I'm willing to, own the gray area when it comes to rules and stuff.

[00:28:31] **Adam:** which is fine by me. but the doctor thing, like, as it turns out, I, there's no way I would've known this at that time, but as it turns out, I get really squeamish, like looking at the inside of somebody's body or my own I, one of my medications that I have to take completely unrelated to mental health, just physical health is, is an injection that I give myself at home.

[00:28:50] **Adam:** And, the one that I'm on now is an auto injector, like an EpiPen sort of situation. But the one before that was just like, here's a syringe with some drugs in it, you know, stick yourself and do that. And I can't do that. I had my wife do that for me.

[00:29:02] **Tim:** You'd be a terrible heroin addict.

[00:29:03] **Adam:** oh yeah, I would absolutely. as much as I obviously, being a doctor comes with a lot of benefits, like good money and lots of opportunities. But, I would've had to have found a way to be a doctor that like, doesn't have to cut people open.

[00:29:15] **Adam:** Right? Like I could be like a podiatrist or , like a, oh, there was like a OSIS doctor or something which is bad breath, if you don't know. I, yeah, I don't know, like that was really why I committed was just like this is a career path. That's gonna have lots of opportunities and good money in the future.

[00:29:33] **Adam:** And it was a good bet, but that, that would be, I think, where I would've been pushed instead.

[00:29:37]

## [00:29:37] Farm to Table Chef

[00:29:37] **Tim:** . So if you had asked, so that's when I was younger, if you'd asked me kind of let's like, say halfway through my career, someone said, gotta stop computer stuff and do something else. What would you be? And to my surprise, I was of ex I would say a farm to table chef. Which teenage me would totally not buy because I was the pickiest eater. I mean, so picky. I was Chicky nuggies and, but yeah, not even potatoes seemed like chicken nuggets and rice. I didn't even like potatoes. I mean, I was such a picky eater and now it's like, I eat anything and everything, and I love to garden and I have, a big vegetable garden and herb garden.

[00:30:15] **Tim:** So yeah, my dream job, if you had stopped me like 10 years ago would be, I'm gonna buy a plot of land. And then, maybe someplace like outside Asheville, North Carolina, near the Biltmore and have some farm and then like, I have a farm to table where you could like eat dinner in the middle of a vegetable garden.

[00:30:32] **Tim:** Yeah. And that, yeah, that would totally, in fact,

[00:30:36] **Tim:** honestly, I'd still do that right now. If I quit right now, that's what I do.

[00:30:40] **Adam:** you, you would have a very strange farm demo who have like alligators and, like sheep, testicles and

[00:30:46] **Tim:** Duct testicles.

[00:30:48] **Adam:** shark brains and who knows what else? But,

[00:30:50] **Tim:** Yeah, the name of the restaurant will be to table.

[00:30:58] **Ben:** my God. That's great.

[00:31:00] **Tim:** I gotta write that down.

[00:31:02] **Adam:** yeah. Right. So if, if for some reason that, like I just had to stop EMP takes out all the world. what are you laughing at?

[00:31:10] **Tim:** I'm laughing a bit laughing at me.

[00:31:12] **Adam:** Okay.

## [00:31:13] Helicopter Pilot with Chainsaws

[00:31:13] **Adam:** So yeah, like, like you were saying, if, if I had to stop right now or if I got the opportunity to reevaluate and decided I didn't wanna stay with computers anymore, what would I do?

[00:31:22] **Adam:** I hesitate to put one of my hobbies in here because part of me thinks that if I. Gonna do something else. I would try to like, monetize one of my hobbies, like do some sort of pro woodworking make and sell furniture, that sort of thing. or become like a professional sky diver. There's a bunch of different ways to do that.

[00:31:37] **Adam:** Right. Like instructor or, competitions and that sort of thing, and then, the, maybe the wild card answer for me is, you've probably seen the videos, where there's like a helicopter and it's dragging or there's underneath of it dangling, it's like a long pole with like 30 giant circular saws on it.

[00:31:53] **Adam:** And it's cutting the trees along the path where like the power lines cut through the woods that looks like so much fun.

[00:32:03] **Ben:** Yeah, that thing

[00:32:04] **Tim:** helicopter pilot with chainsaws,

[00:32:06] **Adam:** that's right.

[00:32:07] **Tim:** the most dangerous man in the room.

## [00:32:09] The Trades and Similarities to Coding

[00:32:09] **Ben:** Well, you talk about woodworking and I have before said that I'm not a very handy person. And I think because of that, I've always had this fantasy that a, I hesitate to call a backup career, but again, just a non-computer oriented career would be some sort of like construction or general contracting.

[00:32:28] **Ben:** I, I feel so unfamiliar with the housing that I am in. I don't know what's in the walls. I'm terrified of wires. I'm terrified of cutting my fingers off. I'm just, I don't feel like I can do anything beyond assembling Ikea furniture and to be someone who is trained to put up walls and patch, drywall and paint properly and carve things.

[00:32:52] **Ben:** I don't know. I have such a, I'm so enamored with that because it feels so into me.

[00:32:59] **Adam:** yeah, I mean, there's sort of two things there. There's the trades, right? Like building houses, building commercial buildings, and then there's like, I guess kind of the hint that I thought I was getting from you there, like carving is the thing that you said, but like making what, we in the industry would call fine furniture.

[00:33:14] **Adam:** Right? It's not just an Ikea thing. It's not just a, built out a two by four, but you know, nice wood and lot of intention and thought goes into it. Yeah.

[00:33:23] **Tim:** know, I kinda like to ask the listeners of the show. Like I think a lot of people who work in tech, they sort of have sort of this backup kind of cuz we, we build stuff, but it's all virtual. Right. And a lot of the stuff we can't like show off to people or take a photo of what we did is like a, maybe a screenshot, but I mean, who cares about that?

[00:33:39] **Tim:** It. They have like some sort of backup kind of endeavor as a hobby where they're like working with their hands, like me, it's gardening and my family, they do cosplay and build physical stuff that you can actually touch. I just wonder asking our listeners, what do you guys do?

[00:33:56] **Tim:** Is there, do you have, something you do to make you feel like you're creating something tangible that's real in the world rather than the virtual stuff that we all build?

[00:34:04] **Adam:** so it was, this reminds me, there was an article, that, my boss, Steve saw on, hacker news a couple of weeks ago. And it was like, why, coders love woodworking or something like that. And it was all, it was a whole bunch of like similarities between the world of coding and the world of woodworking.

[00:34:21] **Adam:** Like, I don't remember what they were, but it was like, communication, I think was one of 'em and just like a bunch of different, like ways that maybe not are immediately obvious that they're similar. But like, when you really think about it, it's kind of flexing the same muscle or, using that same part of your brain.

[00:34:35] **Adam:** or actually maybe the, I think the article was like all the differences. Right. the, The things that you probably are immediately thinking of. Right. I'm working with my hands. I don't have to, I'm not sitting in a chair all day, blah, blah, blah. and then like one of the top comments in the hacker news thread was like, I also love woodworking and I'm a coder, but you know, it's because of all the similarities, which I found really interesting, right?

[00:34:54] **Adam:** Like some people love it for the reasons that it's different than coding. Some people love it for the reasons that are similar to coding.

[00:35:00] **Tim:** Yeah. Interesting.

[00:35:02] **Ben:** Kind of along the general contractor lines. And this is a personal gripe that I would love a crack at counteracting, which is. We've done a little bit of home renovation. Like we had our bathroom revamped and we had a washer dryer put in our closet and paint and that kind of stuff. And in my experience, general contractors are absolutely terrible communicators. Like as, as business owners, they're just terrible communicators that say, you know,I'll show up on Wednesday sometimes between, 10 and 12 and then at 5:00 PM, you're like, are you showing up today? And they'll be like, oh no, one of our jobs got pushed. We won't be able to make today.

[00:35:40] **Ben:** And you're like, well, were you planning on letting us know? Like, and that's not an unusual experience. Like every contract we've ever worked with, it's just terrible. and it boggles the mind because they're in a service industry essentially. And how is customer service, not the thing that they use as a differentiator.

[00:35:58] **Ben:** and I feel like if you were a general contractor and you're one. Point of messaging was we will always communicate like, are we great contractors we're average, but you know what? We will call you. And we will tell you what is going on. I feel like you would clean up because there's such a need for that, that just open communication.

[00:36:21] **Adam:** we're gonna charge you double, but we're gonna tell you all the time.

[00:36:25] **Tim:** we're not coming.

[00:36:26] **Ben:** and we'll tell you when we're getting there.

## [00:36:28] Blockbuster

[00:36:28] **Ben:** My ultimate backup profession was gonna be working at blockbuster.

[00:36:35] **Tim:** I hate to tell you something.

[00:36:36] **Ben:** I thought if none of this computer mumbo jumbo worked out, then at the very least I could stock videos at the blockbuster because I could get to watch movies and I get to talk to people about movies, but that obviously didn't, that's not gonna pan.

[00:36:51] **Adam:** when, when I was in college, I had a roommate who was a video store manager. It was just like a smaller chain. It wasn't blockbuster. and so I worked for him briefly just, to pick up some extra income nights and weekends, and it was a fun job, but it was boring as hell.

[00:37:05] **Ben:** yeah. I guess so. Sorry.

## [00:37:07] Patreon

[00:37:07] **Adam:** All right. Cool. So this episode of Working Code was brought to you by sunglasses. They're a thing.

[00:37:11] **Tim:** really.

[00:37:12] **Adam:** Yeah. In case you didn't know and listeners like you, . If you're enjoying the show, you should consider supporting us on Patreon. It's the best way to help keep the show, running your donations, cover the cost of recording and editing out all of our burps and fumbling over our words. Like I was just doing, we couldn't do this every week without our patrons.

[00:37:27] **Adam:** So thank you. and special. Thanks. Of course, to our top patrons, Monte and Gavin. anybody have anything you wanna tease for the after show Ben? Any other sunglass revelations?

[00:37:35] **Ben:** I'd be interested in talking about the

[00:37:39] **Adam:** Oh yeah, let's do it. Okay, cool. And then that sounds like something we're gonna have to bring back to the main show at some point here too. We can do a rough draft on the after show. Cool.

## [00:37:49] Thanks For Listening!

[00:37:49] **Adam:** So, your homework this week, I'm gonna ask you to, leave us a review, go to workingcode.dev/review. It should, if the algorithms are doing their jobs, take you to the, apple podcasts review place for your country.

[00:38:03] **Adam:** I think , if we've got this technology stuff figured out, as always, we could use your topics and questions to discuss on the show. you can send those to us @WorkingCodePod on Twitter or Instagram. You can email them to us at WorkingCodePod@gmail.com. You can record a voice memo with your phone and send that also to WorkingCodePod@gmail.com. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:38:27] **Tim:** your heart matters. Even you for sunglasses make the outdoors less intense, like filtering out the sunlight like sunglasses are supposed

[00:38:35] **Ben:** They're amazing. I literally like once a week, I'll tell my wife, I'm like, oh man, these sunglasses are great. Thank you so much.

[00:38:43] **Adam:** I almost, unless it's like dark and rainy out, I do not go outside without sunglasses.

[00:38:50] **Ben:** yo, that's where I am right now.

[00:38:51] **Adam:** I like, it's gotten to the point now where I think that my eyes have become so dependent on them. Right. Everything is just too bright, like literally too bright. It hurts my eyes to go outside just on during the daytime, without

[00:39:03] **Ben:** it's so intense.

[00:39:04] **Tim:** Yep.

## [00:39:05] Bloopers

[00:39:05] **Adam:** I hesitate to, to put one of my hobbies in here because you know, it's, it's such a double-sided coin or, uh, yeah, whatever.

[00:39:31] **Tim:** double edged sword.

[00:39:32] **Adam:** yeah, I was gonna say that, but then double ended sword came to mind and that went somewhere else that I didn't wanna go. And

[00:39:38] **Tim:** Wow. Okay.

[00:39:40] **Tim:** it gets you on both ends.

[00:39:45] **Adam:** God.
