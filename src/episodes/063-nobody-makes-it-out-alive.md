---
title: "063: Nobody Makes It Out Alive!"
description: "This week, inspired in part by a post-mortem checklist created by Chrissy LeMaire, the crew shares their thoughts and experiences with death."
date: 2022-02-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/063-nobody-makes-it-out-alive/id1544142288?i=1000551993496"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Van Wilder reminds us to enjoy the moment, warning us _"Don't take life too seriously, you'll never make it out alive."_ And while this is a jocular take on our own mortality, the truth is such that the total cost of death isn't levied against the dead, it's wrought upon the living - the ones left behind. To ease their transition in the wake of loss, we can prepare for own departure; and, provide a plan for our own digital landscape and social networks.

This week, inspired in part by a [post-mortem checklist][chrissy-gh] created by [Chrissy LeMaire][chrissy-lemaire], the crew shares their thoughts and experiences with death. And what steps they've taken—_or not yet taken_—to ease the terrible, yet inevitable, burden on our loved ones.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[chrissy-lemaire]: https://github.com/potatoqualitee
[chrissy-gh]: https://github.com/potatoqualitee/froopyland-dr
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/063-nobody-makes-it-out-alive.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** sometimes I get concerned that my dog doesn't know how much of that. Like, I don't know that she can compute, what it actually means, but, I can just try to be good to

[00:00:10] **Ben:** her.

[00:00:11] **Adam:** knows. Ben,

[00:00:11] **Ben:** She knows.

[00:00:12] **Tim:** That's funny

[00:00:13] **Adam:** I've seen the pictures you posted that dog

## [00:00:35] Intro

[00:00:35] **Adam:** Okay. Here we go. It is show number 63 and on today's show, we're going to talk about death, but as usual, we're going to start with our triumphs and fails But I guess before I forget, because I usually would, I'll mention Carol, couldn't be with us tonight.

[00:00:49] **Adam:** She had something come up at the last minute

[00:00:51] **Adam:** scheduling conflict. So it's a boys show tonight. like I said, it's my turn to go first.

## [00:00:56] Adam's Triumph

[00:00:56] **Adam:** I'm going to start us off with the triumph. basically we have this part of our application that is pretty computationally expensive and, very valuable. Like the users love it. They use the heck out of it. and so it finally got to the point where it was time to, it's been past the time to, refactor it out to, to be sort of its own separate service so that it doesn't bring down the entire application and suffer from lag or cause the rest of the application to lag, because of its usage.

[00:01:25] **Adam:** So I've been working on that for about a week. I was TDD doing it. everything is going fantastic with that. I'm just really happy to have the opportunity to solve a hard problem. Right.

[00:01:35] **Ben:** Can you, talk more about what the area the application is doing?

[00:01:38] **Adam:** Yeah. So we've talked about this a bit. this is the tool that is used for segmentation. So we define a whole bunch of different criteria and those criteria have, can be combined. And, we build a SQL statement or a combination of SQL statements to, create a segment of the audience of the constituency.

[00:02:01] **Adam:** And, those queries, especially for if there's a lot of criteria that process of like creating and generating one list can be a pretty big lift as it were. So,

[00:02:12] **Ben:** I'd like to admit that, I throw out the word cohort sometimes, and I don't really know what cohort means, but I feel like it makes me sound very intelligent.

[00:02:21] **Ben:** So.

[00:02:22] **Adam:** like tranche. Yeah. I've seen that. I used to work at the university of Pennsylvania and they had cohorts within each class year. So like, you would be the class year, 2000 or whatever. but then you'd have, like, I think there would be three or four cohorts within the class year. So I think it's just sort of a way of further breaking down.

[00:02:44] **Adam:** but I don't think that at least in the case of those university student cohorts, I don't think that they were like segmented based on some aspect of the person. Right. It wasn't like boys here and girls

[00:02:56] **Ben:** we was just like next thousand people.

[00:02:58] **Adam:** right. Randomly assigned sort of

[00:02:59] **Ben:** Interesting.

[00:03:00] **Adam:** to the best of my knowledge, I could be completely.

[00:03:03] **Ben:** Next week I have to start building a migration system. That's going to help mirror some of the data in one system in another system. And we have to end up migrating something like. Maybe 6 million records or something.

[00:03:17] **Ben:** and I have decided to call the group of next users that were going to migrate a cohort. And, again, I just feel very fancy every time I say it.

[00:03:26] **Adam:** I don't think that's wrong. There's nothing wrong

[00:03:28] **Ben:** Yeah.

[00:03:29] **Adam:** Is it arbitrary collection of

[00:03:31] **Ben:** There you go.

[00:03:32] **Adam:** Oh man. speaking of migrating records and larger amounts of data, another thing has been going on this week is we've just kind of been hitting a wall with performance for a variety of reasons. The, like those lists. We, so every person that's on a list, we call that a list member, surprisingly enough. And it's our list member table. a single person can appear in that list member table more than once, if they're on more than one list. Right. and we were starting to run into some trouble and found that list member table was over.

[00:04:04] **Adam:** If I remember correctly over 42 million rows. and we took a quick stab at like, okay, well, how many of these lists have never been used for anything? and are like significantly old. And we were able to like easily clean out 14 million rows, which was like on one hand, that's like, awesome. But on the other hand, it's like, yeah, but that barely put a dent in it.

[00:04:24] **Ben:** Here's something that I struggle with. when I have a number of tables that are related under a singular concept, but inside of an application that has a lot of different concepts. So right now you're talking about list management where I might have lists and lists members and like list delivery, status,

[00:04:45] **Ben:** And this is all just about lists.

[00:04:46] **Adam:** A bunch of related tables for one sort of module of the

[00:04:49] **Adam:** application.

[00:04:49] **Ben:** I have to in one table reference a column from the other table in that same little local group, I go back and forth on whether or not I want to prefix that value with the type of thing that we're talking about. So like you have your, list member table. If I have another table that wants to reference that, do I call it the list member ID?

[00:05:13] **Ben:** Or do I just call it the member ID with the assumption that everything in this little set of tables is referring to lists? So prefixing anything with lists would be somewhat redundant. and I don't know how I feel about it and I go back and forth.

[00:05:25] **Tim:** I do too. I do the same thing. So I'm like, you know what, I'm already, when I referenced the table, I got list member, I'll just call it ID. Right. So list member.id, but then it's like, but then sometimes I have the query and it's like, if I don't specify the table and then it's like IDs ambiguous.

[00:05:42] **Tim:** If I made it had a distinct name, it would never be ambiguous. So I go back and forth through

[00:05:47] **Adam:** Yeah. I mean, I used to vary on that a lot, myself and I feel like I've kind of settled into a pretty good routine, which is that I include the entire table name and then suffix it with ID for the primary key, and then do not do that for any of the other columns in

[00:06:06] **Adam:** the table.

[00:06:07] **Adam:** so in this case, lets member ID because the table is called list member list ID on the list table.

[00:06:11] **Adam:** but yeah, there was a time in my career and in school where I was convinced that every column in the table needed to have the full table name. So it would be like list member, email address, and like it's really expressive, I guess you could say like it's extremely clear. What's what, but

[00:06:29] **Tim:** it's

[00:06:29] **Tim:** a bit redundant

[00:06:31] **Adam:** murder on your line.

[00:06:32] **Adam:** Like.

[00:06:33] **Tim:** you've ever done that. I got to do exactly what you do most of the time.

[00:06:37] **Ben:** Yeah. Name spacing in general. It's just challenging in part, because it's like you run into limitations of the, I don't want to say technology, but you run into limitations of how you're actually organizing your application code and your components and your database schema is it's like, if there was a really easy way to, to just segment little, I don't want to call them domain boundaries because. Not

[00:07:01] **Ben:** something,

[00:07:05] **Tim:** It's all a circle.

[00:07:09] **Ben:** but you know, like if I could just, if I had to say an additional database schema, just for that set of tables, then I would reduce the verbosity of the table names themselves probably then the, and then the foreign key references within them. But it's the same thing with a dependency injection in the server side code, where if I have a dependency injection container and everything has to be globally, uniquely named within the application, then I start coming up with some crazy component names just because they have to be unique.

[00:07:39] **Ben:** Whereas if I can, if I could have folders of folders, kind of more like a Java style, name spacing be easier, but then it'd be harder to, I don't know,

[00:07:48] **Adam:** New record Ben getting quacked before

[00:07:50] **Tim:** Yeah, right.

[00:07:52] **Ben:** uh,

[00:07:54] **Ben:** All right. let's move on. so that was me, my triumph, I guess, Tim, that brings us to you.

## [00:07:59] Tim's Fail

[00:07:59] **Tim:** I got a failure. So and this happened to me from time to time. I get stuck in, not stuck, but I guess get into a rhythm. And I just not fully paying attention. I spent over an hour today, changing code and local, and then going into my browser and refreshing on wondering why it didn't change.

[00:08:18] **Tim:** The reason was because I was making the change in local, but I was refreshing and testing in the QA environment, which I hadn't promoted. So

[00:08:27] **Adam:** Yeah. Yeah. Okay. Quick poll. Raise your hand. If you've never done this and all the listeners you're included. Look at that.

[00:08:34] **Tim:** Nobody's

[00:08:34] **Tim:** has see. Yeah, you do that. You feel so stupid and you start coming up with these esoteric reasons why I'm clearing caches and check and stuff. I'm like, and then it's eventually I look up at my browser. I'm like, oh wait. Yeah, I'm not in local. You dummy. me that hour back.

[00:08:51] **Ben:** I have that sometimes where usually when I have my Chrome dev tools open, there's a little checkbox in the network tab that says disabled cash. So that as you're making changes to your local JavaScript and CSS and HTML, the Chrome always goes and gets the new version. But every now and then I need to make sure that cache headers are working.

[00:09:09] **Ben:** So I'll, reenable the cash so that I can make sure that cash hits are happening and things are not being refreshed. And then I'll forget that I do that because I almost never do it. And then it's exactly the same kind of thing where I'm making changes locally and I'm refreshing and they're not there.

[00:09:24] **Ben:** And I'm like, what? And I'm, start logging stuff to the console and I'm checking my, my, terminal output and everything seems like it's working. And then yeah, like 15 minutes will go by and I realized, ah, network

[00:09:34] **Ben:** caching,

[00:09:35] **Tim:** I was even running my tea. I was running my unit tests and they were passing a hundred percent. I'm like they should be working that's yeah, I'm running the QA unit tests, not my local ones. but, and I'm sure listeners are sick of me bragging about my family, but on. the positive side, my results came out this week and my son is indeed the valedictorian.

[00:09:54] **Tim:** So

[00:09:54] **Ben:** That's awesome.

[00:09:55] **Tim:** super proud of him. He's super excited. And yeah,

[00:09:59] **Tim:** he's, uh,he's working on his speech, so

[00:10:02] **Ben:** yo, two speeches in one

[00:10:04] **Ben:** half

[00:10:05] **Tim:** yeah. Right. dinner, and then I'll spin out speech. So super proud.

[00:10:09] **Ben:** out of control. very cool.

[00:10:11] **Tim:** Well, that's me. Carol is out today. So we'll skip over to you.

## [00:10:15] Ben's Triumph

[00:10:15] **Ben:** I'm going to go with a triumph this week and that's that I built a thing. yeah, I, this is basically the same story as last week, which is on Monday or something. I had an idea and then I just. Chipping away at it. And then today at like 4:00 PM, I turned on, I'm going to call the very and thrilling MVP version of that thing in production.

[00:10:36] **Ben:** but it's very exciting for me because at the onset of starting to build this feature, I was actually quite unmotivated and it felt overwhelming, but as I've been trying to focus on in the past, if I can just solve the next problem and then the next column after that, and I, and then it just starts to, it starts to materialize in front of me.

[00:10:56] **Ben:** And then finally it's sort of done and then I can turn it on, but it's. been really leaning heavily into this phrase that it's not good enough, but not good enough is better than nothing. And in that vein, I just, like, I just want to get something in front of the users so that they can try it out and provide feedback.

[00:11:13] **Ben:** And I'm not going to worry about gold plating it, and I'm not going to worry about polishing it and I'm just gonna throw it out there and see what happens. See what sticks. And, yeah, I feel like, it was a successful week.

[00:11:24] **Tim:** That's cool. Yeah, I'm very close to finishing up an MVP that I started today. Well, the thing I was doing today that I was tested and screwing up on. Yeah, probably tomorrow I'll wrap up the MVP and get it in production. I love it. When you can do something in a couple of days and just like you, I was avoiding doing this.

[00:11:42] **Tim:** I'm like, you know what, just open the code and just write the, write the first part, this, all, this is all text messaging stuff where you're sending reminders, text messages. And, so I'm like just build the part where you can opt in or opt out, just build that part. And I built that. And the next thing you know, I pretty much almost finished.

[00:11:59] **Tim:** So love it when you can kind of just motor along. That's why I'm so tired right now. I'm keep yawning. I was like, I started in this thing. I was working right up until we started recording. I didn't like, I didn't want to stop. So my brain hurts.

[00:12:10] **Adam:** Well, I mean, again, Building things and finishing, this thing that I listed as my triumph, this whole sort of mini project I've been working on, I almost listed it as a failure because I spent like a week, working on it and pushing really hard. Cause I was like, Ooh, I might be able to get this done in a week.

[00:12:26] **Adam:** And I got sort of, I think I've talked in the past about the phrase feature complete, how like that's different than done. Right. Feature complete is sort of just the first milestone. And I got caught up in think in reaching feature complete.

[00:12:39] **Adam:** And I, that was what I was seeing at the end of that first week. Like, oh, I can get there. And then, so that's the first 90% and then I've spent the last week. So to the second week on this project doing the second 90%, and

[00:12:50] **Adam:** it,

[00:12:52] **Tim:** that last 10% is the second 90%.

[00:12:55] **Tim:** Yup.doing the

[00:12:56] **Tim:** unsexy

[00:12:57] **Adam:** just like. Bugs and wiring stuff together and yeah, it's just

[00:13:04] **Tim:** yeah, for me like doing the logging and reporting is like the least exciting part. I want to see the feature work, but it's like, okay, I need are really need to be logging all this stuff. I really need to be building things to report on it and just like it. doesn't crank my gears.

[00:13:17] **Adam:** Yeah.

[00:13:17] **Adam:**

## [00:13:18] Audible

[00:13:18]

[00:13:48] **Adam:** .

## [00:13:48] In Case Of Death

[00:13:48] **Adam:** Okay. let's talk about

[00:13:49] **Adam:** death. It's coming for us all. Yeah. I mean, so this all started because one of our patrons and a member of our Discord posted a link today to this, get hub repository, we'll have a link to it in the show notes. and it's basically the way I read it is it's sort of a checklist or a guide for something that you can leave in a safe place. So that in the event of your death, the people that depend on you for like, if you're the family, it manager, or, just taking care of stuff like that, if you're the one that pays the bills, all the auto pay stuff or whatever for your household, having all of that in a neat and tidy way, can really make dealing with your death a little easier.

[00:14:35] **Adam:** That seemed like a good idea. and my wife and I have done a couple of things, sort of with the same motivation, like, we have one password and, I have her master password in mine and she has my master password in hers, so that if one of us were to get hit by a bus, we could have access to each other's computers.

[00:14:52] **Adam:** And to being in one password means it's also in the cloud. So if her computer is with her, when she gets hit by a bus, then can still access all that. And it's all shared. And so

[00:15:01] **Ben:** I liked the idea of having each other's master password. Cause we also, we have a family, one password plan and, we have a shared vault which helps for some of that stuff. some people in my family are more diligent about putting stuff in the shared vault than others. but I think having the master password as a fail safe, that would make me the most comfortable.

[00:15:19] **Adam:** Yeah. A totally. yeah, we use a shared vault. We have our master passwords shared and also, I mean, like you said, we're on a family plan and, I've been trying to push, especially my mom, to use a password manager for a long time. And so to help her feel more comfortable with it, I've got her master password in our shared vault as well, so that, at any time she can call and say, I forgot my master password. What is it again?

[00:15:43] **Ben:** I'll tell you, if I can share a personal story for a second.

[00:15:45] **Adam:** that's kind of the whole point, right?

[00:15:47] **Ben:** my father died from gastric cancer. I want to say like 15 years ago, something like that. I'm not good with time, honestly. but he was battling it for a year and sorta got better and then started to get worse again. And I think in that entire struggle, he, at no point admitted to himself, I think that he may die. And as such took no precautionary steps at all to do anything, to make it easier for my, my mother. And, so when he did finally pass, there was just. Credit card bills and business accounts and all kinds of stuff. And we were ended up having to go through his computer to try and identify stuff.

[00:16:36] **Ben:** And she was screening telephone calls because like, people just come out of the woodwork saying like, Hey, how can we not paying your bills? And, but it's like bills related to his business, not related to the family. Anyway, it was like a real mess for a free for years. And, it, it goes to show, not just preparation in the abstract sense, but also that like end of life,

[00:16:59] **Adam:** Oh,

[00:16:59] **Ben:** you know, really trying to dot your I's and cross your T's

[00:17:03] **Ben:** and

[00:17:04] **Ben:** stuff.

[00:17:05] **Tim:** no one, likes to think of that right now. no one wants to think there'll be a day when they're not here. And if they do think there'll be a day, they're like, well, it's just so far off in the future. I got plenty of time, but I mean, you never know. Right. You can get hit by a bus, the proverbial bus tomorrow.

[00:17:20] **Tim:** I like it. I hadn't heard of this. I didn't look at this, but I like sort of the, how he just breaks down in this, get hub repository. The first thing is. Who to notify that I'm dead. Right? So he says, write up a little message, say what happened. And then on I messages, contact these people on WhatsApp, tell this person or these people on Facebook, tell these people, the people that you really care about that you want them to know.

[00:17:44] **Tim:** So it goes through all these different social media things and say, tell these people I'm dead. and then it goes through and just the different tech things like your emails, whereas where's the password store. What are your emails that you use? you'd be owning domains,where are they?

[00:17:56] **Tim:** your password manager on your computer. What's the login for that. And then all the subscriptions, like how to, cause they're in your name, they're going to your car and how do you keep those running? So I think it's a really well thought out document. I probably need to go through this.

[00:18:10] **Ben:** Yeah,

[00:18:11] **Adam:** I guess maybe I'm in the minority then, because like you said, most people are kind of in denial about all this. Or even if they're not in denial, they just kind of think it's not coming from me anytime soon. based on my hobbies, I've kind of chosen to, accept the fact that I could die at any time and be prepared for that.

[00:18:28] **Adam:** I'm not this prepared yet, but this is on my to-do list now.

[00:18:31] **Tim:** because I'm thinking about it. It's like I pay all the bills. I handle pretty much everything financial I handle. And it's like, if I died, my wife would had no clue. what was, what? So,

[00:18:40] **Adam:** Well, she doesn't know that it's there, but in my nightstand next to my side of the bed, I have an envelope with her name on it, my wife's name, and in there is a letter like my final

[00:18:50] **Adam:** goodbye sort of

[00:18:51] **Tim:** oh, wow.

[00:18:52] **Ben:** it's like a movie.

[00:18:53] **Adam:** yeah,

[00:18:54] **Ben:** Yeah.

[00:18:54] **Adam:** and it's like, I'm just leaving it there. I'm not telling her it's buried under a whole bunch of other garbage.

[00:18:58] **Adam:** Yeah. The intent is for her to find

[00:19:00] **Tim:** Wow.

[00:19:01] **Adam:** And I update it every five to

[00:19:02] **Adam:** 10

[00:19:02] **Tim:** . I know on Facebook they have a way you can appoint a legacy context so that when you die, they can, set up like a memorialize your account because nothing is more awkward.

[00:19:10] **Tim:** Like I've seen like people that have been dead for a couple of years and Facebook says it's birthday. And everyone's like, happy birthday, Joe, happy birthday. Joni has been dead two years. I mean, that's,That's really

[00:19:21] **Ben:** true.

[00:19:23] **Adam:** I've been personally relatively fortunate in terms of, losing people. I have my grandfather on my mom's side, one of my uncles. And that's like, all I can think of in terms of people who have died that

[00:19:37] **Ben:** Oh, wow.

[00:19:38] **Adam:** close to me. and like, and I haven't had to deal with any of the fallout. Right.

[00:19:42] **Adam:** and my wife, her she's lost, by now. all but two of her grandparents and the other two are getting old. I think, one of them is going to be a hundred this year

[00:19:54] **Tim:** Wow.

[00:19:55] **Adam:** or 99,

[00:19:56] **Ben:** That's a good genes right

[00:19:57] **Ben:** there.

[00:19:58] **Adam:** Yeah. But yeah, and it's just like seeing my in-laws deal with the estates of their parents.

[00:20:07] **Adam:** Kind of eyeopening and a little weird

[00:20:09] **Ben:** Yeah, it is really weird. It's weird too, because you're in the middle of it, I don't want to say sometimes it's hard to have empathy, but if you don't necessarily have the immediacy of the feelings, you're just like in this holding pattern, like you're in the supporting role, you have no idea when that supporting role is going to end.

[00:20:30] **Ben:** You have no idea what's going to happen in the next hour. you have no idea. What's going to be asked of you. it's just kind of, it's exhausting. I'm not complaining. I'm just, it's a weird place to be.

[00:20:40] **Adam:** yeah, absolutely. The other thing is I find loss of that type to be extremely awkward. Like the sort of standard thing you say is I'm sorry for your

[00:20:50] **Adam:** loss. And because everybody says that I always feel so. Trite saying it. And so part of me wants to not say that, but then it's like, but then I'm making it about myself.

[00:21:03] **Adam:** Right. If I,if I try to say something else that always turns out to be like, I, whatever, I can't help, but try to relate. and so then I feel like I'm making it about myself. So then I just like, okay, when my brain goes there, I'm like, okay, back up, just say, I'm sorry for your loss.

[00:21:15] **Ben:** Yeah.

[00:21:16] **Tim:** They're everywhere. Everyone's very, can be very awkward about, talking to someone about the death of a loved one. But, from what I've read in the things that suggestions that, saying something, even if you're not sure it's the right thing, that they'll, it's important to say something right.

[00:21:30] **Adam:** Yeah.

[00:21:30] **Tim:** even more important is to maybe everyone like comes out of the woodwork whenever it happens. Right. And right then at that point that person's life, they're probably pretty much overloaded and a little bit numb. It's even more important to come, maybe come back a month or two and just say, Hey, and say something nice that you remember About the person, if you knew the person that died, if he didn't and say, I know you probably go on through a lot of loss, just thinking of you just doing those sort of things, really help people get through the grief process.

## [00:21:56] On Eulogies

[00:21:56] **Adam:** Yeah. as cheesy as it is, my wife and I watched the show called this is us.

[00:22:01] **Adam:** Um, sounds like you guys both

[00:22:03] **Tim:** man, actually it makes me cry every single time.

[00:22:06] **Ben:** Every.

[00:22:06] **Adam:** Yep. Yeah. not every episode, but

[00:22:08] **Adam:** almost every

[00:22:09] **Adam:** episode

[00:22:09] **Adam:** and the one I don't want to spoil anything, but the one that aired relatively recently where, Jack had to give a eulogy,that inspired me, honestly, like I started thinking about my parents and what I would say at their eulogy.

[00:22:28] **Adam:** And, it kind of, as I started to think of the things that I would say, I was like, there's no reason I shouldn't say this to their face. Right. So I, it was already late at night. So I wrote my mom an email. It's like, this is all on my mind, blah, blah, blah. And I sent her this really long email. It's just not a eulogy, but like, it was just a whole bunch of things that I thought of that were nice about her memories and things that I would want her to be remembered for and sent that to her.

[00:22:52] **Adam:** And she said, of course, when she got it, she like cried for half an hour.

[00:22:56] **Tim:** he thinks I'm dying.

[00:22:59] **Adam:** no spring chicken. She's what I think she's about your

[00:23:03] **Adam:** age, Tim.

[00:23:06] **Tim:** sure I'm dad.

[00:23:07] **Adam:** I'm pretty sure I'd be a lot handsomer if I was.

[00:23:11] **Tim:** Thanks.

[00:23:14] **Ben:** there is something very, uncomfortable, I think about giving someone access to your email, even if they're not actively using it, just knowing that it's out there. I'm like,it's not like I'm doing a lot of shady stuff, but there's 15 years of email in there.

[00:23:30] **Adam:** oh

[00:23:31] **Ben:** You

[00:23:31] **Ben:** that I didn't know you for those 15 years.

[00:23:35] **Tim:** All them kinky solution. Domain names.

[00:23:39] **Ben:** and, I think you obviously have to trust your loved ones, but, I don't know. That's tough. That's a

[00:23:43] **Adam:** Well, I mean, you don't want to tarnish their memories of you, but at the same time, like if they get disappointed in you or something like, it's not like you're going to be there

[00:23:52] **Ben:** Right. That's true.

[00:23:53] **Tim:** Yeah.

[00:23:53] **Adam:** it's not on this checklist in the GitHub

[00:23:55] **Adam:** repository, your browser history for

[00:23:58] **Adam:** you.

[00:23:59] **Tim:** right. Yeah. the first person you. contact is your bro. Who's got the job of clearing your

[00:24:07] **Adam:** Although, these days with the incognito mode, you just use that and you don't have to worry about

[00:24:12] **Tim:** yeah. Our duck, duck go.

[00:24:14] **Adam:** of us.

[00:24:14] **Tim:** Yeah. You talking about how about eulogies? if anyone's read Orson Scott card's book called speaker for the dead, it was, it was a sequel to Ender's game, but, the speaker of the dead sort of had this concept of that. Whenever a person would die, they would appoint a speaker for the dad who wasn't necessarily even a person that knew the deceased and their job was to investigate the life of the person who died.

[00:24:41] **Tim:** And then they would sort of give a third party. discourse at the end, and talk about their life to just pay homage to the person's life. Good and bad. Right. And,and I think about that, cause, in the story of injures game, of course, who killed basically, an entire species of aliens, he became speaker of the dead for them

[00:25:00] **Tim:** and

[00:25:00] **Adam:** Yeah, spoiler. been what

[00:25:04] **Tim:** 25, 30 years. Yeah, So, but Ryan is a kind of what you did with your mom. It's like, you can't say those things afterwards, so, same now.

[00:25:14] **Adam:** Yeah, it was cathartic really to take a moment. Cause we all have these things, right. I should tell my parents that I love them more. I should call my parents more and just show that appreciation. And it was, I, I just got bit by the bug. I wanted to take some time to think about what I'm proud about and what I remember.

[00:25:35] **Adam:** And then when I was halfway through that list, I was like, this is stuff I should, share with my mom. Like, there's no reason to hide it and wait until after she's dead to say these nice things about her.

[00:25:46] **Ben:** Some, sometimes I get concerned that my dog doesn't know how much of that. Like, I don't know that she can compute, what it actually means, but, I can just try to be good to

[00:25:57] **Ben:** her.

[00:25:57] **Adam:** knows. Ben,

[00:25:58] **Ben:** She knows.

[00:25:59] **Tim:** That's funny

[00:26:00] **Adam:** I've seen the pictures you posted that dog.

[00:26:03] **Tim:** now, what I don't get. What is home labs at home labs on this?

[00:26:07] **Adam:** I think that's just like, that might be specific to the type of technology they were using, like VMware type thing. But, I, when I think about it, when I read that article, but like those sort of intro to the repository, I just thought of it as like my home office. Right. I've got a NAS in here. I've got my desktop computer.

[00:26:27] **Adam:** I've got my laptop and all this stuff, like how's the house networked, I've got cables running all over the place.

[00:26:32] **Tim:** Yeah. And then your online photos, I mean, that's a good point too. It's like people used to have photo albums and don't think most people do anymore. So everything's online. If you could lose your family can lose all those photos and if they didn't have access to them

[00:26:44] **Adam:** Yup.

[00:26:45] **Tim:** and then your virtual coin, your Bitcoin and everything,

[00:26:49] **Adam:** Oh God.

## [00:26:49] Work Arrangements

[00:26:49] **Ben:** Do you feel like you can put, important documents in your one password? I primarily use one password for log-ins, but I'm wondering if I should be scanning documents and just saving them into one past. And then it's like one point of presence for someone to have to know about.

[00:27:05] **Adam:** right. I don't do that, but I know that, so there's like secure notes and I've used those, like, so I used to have a pretty big freelancing client and they got a little spooked kind of early on about the idea of me getting hit by a bus. And so what I did because, you know,I was the sole administrator of their website.

[00:27:26] **Adam:** So what I did was I, made an arrangement with a buddy of mine and I was like, look, if something happens to me, here's my one password master password. Here's the, this is what you can search for in there to find the note, my wife will get you onto my laptop sort of thing. and, and then in that secure note was like, everything was.

[00:27:42] **Adam:** that client. So at least if I were to get hit by a bus, the deal was he would help them find somebody else that could take it over. He wasn't going to be responsible for it, but he would give them access.

[00:27:51] **Ben:** I have this filing cabinet next to my desk. It's like a two drawer filing cabinet. And I honestly, I don't even know what's in it at this point. That's probably half of it's probably just tax returns from the last 15 years. but now I feel like I should go through it and make sure that there's nothing super important in it and anything that's super important.

[00:28:08] **Ben:** I should make sure that there's a digital copy.

[00:28:09] **Adam:** yeah, we have a fireproof safe

[00:28:12] **Ben:** Oh,

[00:28:12] **Adam:** and yeah, I mean, it's not that huge. It's about the size. It's a little bit bigger than like your lunch box you used to take to school

[00:28:18] **Adam:** in elementary school. And, the, it's got keys, but I think. That's not. So it's not so much a safe, it's

[00:28:25] **Adam:** a fireproof box.

[00:28:27] **Adam:** And, my understanding is like, we just leave the keys hanging in it. And,important stuff is in there, like passports, birth certificates, the deed to our cars and our house and stuff. but then like if the house were to burn down the, like the hinges and stuff, I think like melon, it just kind of becomes sealed so that it can't get damaged on the inside.

[00:28:44] **Adam:** But

[00:28:44] **Adam:** then,

[00:28:45] **Adam:** the, I guess firemen or whoever are able to like crack it open, they have the right tools or whatever. So it's like the black box of the airplane

## [00:28:55] Thinking About Death

[00:28:55] **Ben:** Yeah. that's pretty cool. I'm feeling very under prepared. I don't think

[00:28:58] **Ben:** about it. I don't think about death very often.

[00:29:01] **Adam:** Memento, Mori death comes for

[00:29:03] **Adam:** us all. all. right. I think that just means death is coming, but to remember death.

[00:29:07] **Ben:** I don't think about death very often, but I do think about getting hurt. I think that the idea of getting hurt holds me not, I don't want to say holds me back, but definitely the idea of being in pain stops me from doing things in a good way. I think

[00:29:21] **Ben:** mostly,

[00:29:22] **Adam:** Elaborate.

[00:29:23] **Ben:** I don't know, like, I, I w I would maybe take more risks if I didn't think I would get hurt or like, I don't know.

[00:29:30] **Ben:** I, if you didn't think you could get hurt, he's probably started acting out super like superhero fantasies and stuff, like, I'm just saying that my, I don't think about my mortality in terms of death, but I think about my, like the mortality of the human body. And I don't want to, I don't want to get hurt.

[00:29:48] **Ben:** I don't want to be in pain. I don't want to get stabbed. I don't want to lose my teeth,

[00:29:51] **Tim:** I've drunk, constant recurring dreams. Like, I guess I grind my teeth, when I'm sleeping. And so I've dreamed that my teeth like crumble and like fall out and that is the worst. I'm like, Oh, my God, I'm going to look like a hick. I'm going to look like

[00:30:07] **Adam:** you some

[00:30:08] **Tim:** right. It just freaks me out. And I wake up and like, I touched my mouth.

[00:30:12] **Tim:** Okay. they're there. Okay.

## [00:30:13] Dead Man Switch

[00:30:13] **Ben:** I'm pretty sure there was one or two law and order episodes about these websites where, I think you'd have to check in with the website once a day or once a week or something as a, as like a dead man switch. And then if you didn't check in the website would send out announcements that, that you had been, you had died and killed something like that.

[00:30:31] **Tim:** so there's services like wind sinned.com. And future meet.org where you can basically compose an email, but not have it delivered until a certain date. I know I've used that in,

[00:30:43] **Adam:** You can actually, you can schedule email and Gmail, but I dunno if you can schedule it that far out.

[00:30:47] **Ben:** I think the one on law and order was specifically about the rapture and I, and it was specifically for people who wanted the email sent out after they had been taken in the rapture. And this was the email going out to everyone who had been left behind, but then the person running the service, I think was the person who was killed.

[00:31:07] **Ben:** And, and so they, I think they had to be able to do something every day. And if they didn't check in, that was also an indication of the rapture,

[00:31:14] **Tim:** I know outlook has a, do not deliver before option. Right? So if you want to send a that and outlook.

[00:31:20] **Adam:** Yeah. I mean, I guess that's it. So, just remember death it's coming for us all

[00:31:25] **Ben:** Absolutely.

[00:31:26] **Adam:** be prepared and check out the GitHub repo in the show notes.

[00:31:29] **Adam:** this all made me think of that episode of one division, where they were saying that, what is grief, but love persevering. That was

[00:31:39] **Adam:** a real nice.

[00:31:40] **Adam:** Well-written line of a TV show.

## [00:31:44] Patreon

[00:31:44] **Adam:** so this episode of Working Code was brought to you by death. It's coming for us all. Nobody makes it out alive and listeners like you. If you're enjoying the podcast, you should consider supporting us on Patreon and support from listeners. Like you helps keep the mics on and we appreciate each and every one of you, you can do that by going to patreon.com/WorkingCodePod.

[00:32:07] **Adam:** All of our patrons get early access to an ad free version of new episodes and our after show. That's what we're going to go record after we record this one, hence the name, and we really appreciate all their support, our biggest thanks. Go out to our top patrons, Monte and Peter, you guys rock.

## [00:32:21] Thanks For Listening!

[00:32:21] **Adam:** Do you have a question or a topic you'd like to hear us discuss? There's a lot of ways that you could get it to us, like sending it to @WorkingCodePod on Twitter or Instagram, you can join our Discord at workingcode.dev/discord. You can email it to us. I WorkingCodePod@gmail.com or you can even record a voice memo on your phone and email that to us so that we can play your lovely voice on the show.

[00:32:42] **Adam:** That's going to be it for us this week. We'll catch you next week. And until then,

[00:32:46] **Tim:** Remember guys, your beating heart matters. And when it stops, the memory of you will matter still.
