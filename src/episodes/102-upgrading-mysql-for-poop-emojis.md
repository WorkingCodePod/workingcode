---
title: "102: Upgrading MySQL For Poop Emojis"
description: "This week on the show, Adam shares the lessons that he learned while performing a large, multi-client, multi-cluster, week-long database migration for AlumnIQ."
date: 2022-11-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/102-upgrading-mysql-for-poop-emojis/id1544142288?i=1000587246776"></iframe>

Migrating data is always complicated. And, the more data that you have to migrate, the more complex your migration process becomes. This week on the show, Adam shares the lessons that he learned while performing a [large, multi-client, multi-cluster, week-long database migration][adam-post] for [AlumnIQ][alumniq]. This included moving roughly a dozen different databases from Amazon Aurora (MySQL 5) to Aurora 8. Late nights, indexes, and UTF-8 character encodings, oh my!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-post]: https://adamtuttle.codes/blog/2022/lessons-learned-migrating-large-mysql-databases/
[alumniq]: https://www.alumniq.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/102-upgrading-mysql-for-poop-emojis.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I was writing about some JSON stuff in MySQL and I posted this thing on Twitter And someone said, Oh, you should just use Postgres. It has much better JSON function.

[00:00:09] **Ben:** I said, I'm not very familiar with Postgres. What would this look like in Postgres? And the guy wrote up a little snippet equivalent and he's like, Actually, this looks much worse than Postgres.

[00:00:24] **Tim:** Have you heard of our Lord and Savior PostgresSQL?

## [00:00:48] Intro

[00:00:48] **Adam:** Okay, here we go. It is show number 1 0 2, and on today's show we're gonna talk about migrating large MySQL databases. Some of the things I've learned in the last week from doing that.

[00:00:58] **Adam:** But as usual, we're gonna start with our trium and fails. And how about Carol, why don't you go first this week?

## [00:01:05] Carol's Triumph

[00:01:05] **Carol:** Yeah. So I'm gonna throw out a big triumph. Only in half of a triumph, I suppose, but it's a big triumph I think. So we'll see. Previously we talked about the fact that we'd laid off some people at the company. So people are having to jump in and do other roles and pick up some responsibilities that they weren't doing previously.

[00:01:24] **Carol:** So I've had an email from the new, I'm gonna air quote this because I don't know what the job is, but time card holder, , the person who determines if you've clocked hours into products. So we know what's r and d and what's billable and like, you know, where your hours were spent. So most engineers need to put in, you know, you know, like 38, 40 hours and nobody questions anything.

[00:01:49] **Carol:** but for management, you don't have to log any hours. So I've had an email that said, Hey, , you log zero hours or you don't have enough hours, so can you log in and fix that? And I responded with, I thought I didn't have to do that. You know, the only time I log is when I'm physically coding. So I then went back and start looking at how much I'm not writing any code.

[00:02:13] **Carol:** And that's not a bad thing, right? Because I start looking at the hours I'm spending on a daily basis, working with my team to get them through roadblocks, to work them through processes, to review code with them. So while I looked at my code output and saw it's substantially decreased. Since I have taken on this role, my team's output has increased.

[00:02:36] **Carol:** And I feel like part of that is me being able to answer questions quickly and me being able to show workflows and show how things happen and to document more processes better and just, Do, a better job. I don't know what it actually is, but I'm really happy that overall the team's doing better. Even if looking at it on paper, I'm not putting out as much code.

[00:02:59] **Carol:** So I'm calling now the win.

[00:03:00] **Tim:** Yeah, I mean, that's a, that's a shift in your job focus, right? So,

[00:03:04] **Carol:** Yeah, yeah.

[00:03:05] **Adam:** Sounds like a win if you want it to be right. Like, uh, it's, it's all

[00:03:10] **Carol:** was a little, yeah, it was a little gut punch. You know, I'm like, Man, I should write more code. But then I'm like, Oh, if I'm writing more code, I'm, when I write code and I'm focusing code, I put my slack on do not disturb. So if someone wants to send me a message, they have to determine whether or not it's important because I'm, It shows on there like, I'm in do not disturb, so do you really wanna send that?

[00:03:33] **Carol:** So I feel like when I do that, my team don't, like, will not ask the questions that need to be asked. So I know I'm helping. So while it was a little gut punch, I was also very happy that I'm helping and feel like I'm doing a good job in this job. Calling it a win. That's me. Tim, what you got?

## [00:03:52] Tim's Fail

[00:03:52] **Tim:** I'm going with a failure. So, yeah, last week we had to let some senior leadership go, which was sad. Cause

[00:04:00] **Tim:** I mean, one of 'em had

[00:04:02] **Tim:** been with the company for a very long time, and, it just, you know, they, we weren't, they weren't getting the results that, they had promised and the direction they were going wasn't really working out.

[00:04:13] **Tim:** So they, they, you know, they let, I mean, I wasn't part of the decision to let them go. It's just

[00:04:18] **Tim:** I found out with everyone else, but it just means a huge reorg for, for the company now. I'm breaking off as my own separate thing, so it doesn't really affect me that much, but still it's like, it's people I've known for years.

[00:04:31] **Tim:** People are respect. And so it's just always sad to, to see that happen, particularly when they didn't see that coming, to see 'em blindsided like that. So, but you know, I understand the reasons why they had to do it. We've, you know, the entire week we've been very, the leadership teams have had meetings every morning, just kind of, you know, talking to every person in the organization, talking to all our of our customers, you know, making sure people understand, you know, you know, you see all these things in the news right now.

[00:04:57] **Tim:** Right now when while we're recordings, like, you know, I just learned today that,Amazon's letting 10%

[00:05:02] **Tim:** of their people go Twitter. Let a whole bunch of people go,

[00:05:05] **Adam:** I don't think that that's necessarily related

[00:05:07] **Tim:** mean, I know it's not related, but you know, it's like if you're.

[00:05:09] **Tim:** if you're.

[00:05:09] **Carol:** the Facebook was, I mean, it's, it's tech related. Yeah.

[00:05:12] **Tim:** Yeah. But, but what I'm saying is like when, when you see tech jobs, like, and people getting fired in, in mass and then all of a sudden you find out, you know, leadership, you know, some of the leadership's going, they're like, Are we next? Right.

[00:05:23] **Tim:** You know, they're, and so, you know, had an all hands meeting and just said, Listen, you know, we don't have any further plans letting gun go.

[00:05:30] **Tim:** This was just sort of a, you know, sometimes in the team isn't doing good, you gotta, you know, gotta fire the coach. So, uh, that, that's, that's what happened. So, yeah.

[00:05:38] **Carol:** That's a, that's a really good way to put it. It's, it's something I've never really thought about before. When you let leadership go, as you think of a coach, like if your team loses a season after season, you're going, Why aren't you firing the coach? Right. And when you use that analogy, it kind of clicks a little different in the head in a way.

[00:05:55] **Carol:** I have never thought about it before.

[00:05:57] **Tim:** Yeah, it wasn't me. He came up with that. So like, someone, she's like at the higher level, she's a huge Alabama fan. Unfortunately

[00:06:04] **Carol:** Roll tie, baby.

[00:06:05] **Tim:** not this year, they

[00:06:06] **Tim:** enroll in nowhere.

[00:06:08] **Carol:** no. Still love 'em. Still love 'em.

[00:06:10] **Carol:** Yeah.

[00:06:11] **Tim:** But, yeah, she, that's, that was her analogies. Like, you know, sometimes, you know, it's, you can't just make changes at the tactical level.

[00:06:17] **Tim:** Like maybe the strategy here was not Right. So, you know, whoever came up with that strategy, gotta replace them. So,

[00:06:23] **Adam:** Mm. Yeah. It makes me think about like, all these layoffs make me think about a potential future where, you know, I'm still at the same company, but, we have a bunch of people and, and we hit hard times. I hope that I'm in a position to, and that we do make the decision to, save ourselves from a similar like layoff type situation by reducing our, you know, executive level compensation.

[00:06:47] **Adam:** Like, I wanna be the guy, I want us to be the company that's willing to, and, to say, Okay, we are also hitting hard times, but we want you to let you know we're not gonna lay anybody off. We're cutting back our own salaries. We're doing, you know, these other cost cutting measures, but the people are, are what's important to us.

[00:07:03] **Adam:** And I like, I know, you know, no plan survives first contact with the enemy. That's just a plan. That's an idea. But, God, I really want to take care of our people.

[00:07:11] **Tim:** Yeah. And, and I mean, I think that's easier when you're a privately held company. you know, all the companies, all the companies we're talking about, including us, we're, we're, we're publicly traded. So it's like you, your responsibility is to the shareholders

[00:07:24] **Tim:** and you know, if, if you're going through tough times, you know, you can't say, Well, we really like our people, and like, No, you working for the shareholders.

[00:07:32] **Tim:** So that makes, it, makes it a bit harder. But I, I do, I I think Sean Corfield on our Discord had a good point to make that I, I think what we're seeing in the broader industry is really a correction.

[00:07:43] **Tim:** You had people shoveling huge amounts of money in the tech and they were hiring, they were just hiring too many people.

[00:07:49] **Tim:** You know, They really were, they were paying, paying people too much, hiring too many people. during Covid, they, they hired a whole bunch of people thinking, you know, because there was more demand for online stuff. Now that demand's kind of slackened a bit cause people are back to more, you know, normal methods of, of, of transacting business.

[00:08:05] **Tim:** And, I, I think it, yeah, I do think it's a correction. I mean, that's not, in our case, it wasn't a correction. We are not overhired by any means, but,

[00:08:13] **Tim:** hey,

[00:08:14] **Adam:** The market as a whole.

[00:08:15] **Tim:** yeah, if we could snag some of those Facebook engineers or you know, people from Meta, that'd be great. There'd be some talent floating around.

[00:08:20] **Tim:** Finally, that's me. How about you, Ben?

## [00:08:22] Ben's Fail

[00:08:22] **Ben:** I'm also gonna go with a failure and it's a amorphous failure. It's a little hard to describe. I just feel a little lately that I don't have a lot of fight left in me at work, you know, so, so much of my relationship to the organization has been not, adversarial, but, but we're on separate sides of offense with me working on the legacy platform and everyone else working on the modern platform.

[00:08:48] **Ben:** And, and I have historically love the idea of getting up in the morning and fighting for those, those V6 users. And I don't know, I just, I'm tired. I'm tired of having those conversations and I'm tired of. Having to discuss when I'm gonna move over and I'm tired to discuss priorities. And I, I sort of just want someone to tell me to stop and to go do something specifically.

[00:09:12] **Ben:** Like I, I sort of want the decision to be taken out my hands. I, I almost need to

[00:09:18] **Carol:** Yeah, I mean,

[00:09:18] **Carol:** I mean

[00:09:19] **Adam:** You, you've banked your millions. you take a year off,

[00:09:22] **Carol:** yeah.

[00:09:23] **Adam:** fly around.

[00:09:24] **Carol:** Yeah. I mean, making that decision to stop is hard, right? Like no one wants to give up, no one wants to feel like they didn't do enough. And you, I think, feel like there's still fight to give this project, right? And there's still growth to put into it. So you deciding to not do it, It's different than someone saying, All right, today's the day we're done.

[00:09:45] **Ben:** Yeah. And you know, I was talking to my director and she started to bring up the idea that I would spend some time working on the legacy platform and some time working on the modern platform and. I just have no interest in doing that whatsoever. That feels like the worst of all worlds. And it's completely different Docker configurations and completely different workflows in terms of development and, and to straddle those worlds feels like it would just be a nightmare.

[00:10:16] **Ben:** I,

[00:10:17] **Carol:** different language as well?

[00:10:18] **Ben:** it's a lot of different languages. I mean, not a lot, you know, it's a handful of different languages. It's completely different developer tooling. It's completely different, access permissions for certain things. And, and, I, the analogy that I was given to my director was, was like learning a foreign language.

[00:10:34] **Ben:** If, if you all want me to learn a foreign language, don't put me in, you know, a class once a week. Immerse me, you know, make me move to another country and start learning their language. So I, I dunno, there was something about having to have those conversations again that just like, ugh, like something, like a switch flipped.

[00:10:54] **Carol:** Oh, I'm sorry.

[00:10:56] **Tim:** Yeah, I, I imagine you, you are a, a challenge for management, and I don't mean that in a bad way. It's just like they don't, I don't

[00:11:05] **Tim:** think they fully know what to do with you, and I think they're, they're a little unsure, but also kind of afraid, right? At the same time, Right. They don't wanna, they don't wanna,

[00:11:14] **Tim:** they really don't wanna set you.

[00:11:15] **Carol:** bear.

[00:11:16] **Tim:** right, They wanna make you happy, but at the same time, it's like they're really, you know, you don't know what you wanna do. A hundred percent doesn't sound like, and they're really not sure either, so, but they. You gotta do something, you work here. Right? So I I I imagine that it's a, it's a challenge on their side.

[00:11:33] **Tim:** Maybe ask them, what can you do to help the transition go easier?

[00:11:37] **Carol:** Yeah,

[00:11:37] **Ben:** Yeah,

[00:11:38] **Tim:** What do they, what do they need?

[00:11:40] **Carol:** there you

[00:11:40] **Ben:** yeah, that's like, I, I sort of just wanna be told instead of being asked, where do you want to go? Or like, what would make you happy? I feel like I don't know enough. To be able to answer that question, so I feel like someone needs to just say like, You go over there, do that stuff.

[00:11:58] **Tim:** Yeah. So you ask them, you know, you know, what, what would you, what would be the best thing for me to do? In your mind? What would, you know, make your world a lot easier? And then if they say something, you're like, Oh, I can do that, then, you know, And if they're like, do that, they're like, No, I can't do that.

[00:12:11] **Tim:** Then you make a plan accordingly.

[00:12:14] **Carol:** Yeah, that's actually the conversation that we had in Leadership Sync this week where there's a lot of things that need to be done, but there's no insight to people who can do it, right. So there are a lot of people on my team who are willing to jump in and take on these challenges, but they have no idea the challenge is even needed or that there's a problem because all they know is what exists in their world.

[00:12:35] **Carol:** So like we have a plan to open up to be like more transparent on opportunities outside of just this one team and where you can help other teams at. So you can make the decision like, Oh, I really wanna go do this, so now I know what the need is and I feel like I can solve this need for you, rather than just chugging along and not knowing what else is needed in the company.

[00:12:57] **Carol:** So,

[00:12:58] **Ben:** So, yeah, we'll see, we'll see how it next couple of weeks play out.

[00:13:03] **Carol:** yeah. Are you taking off any time for Thanksgiving?

[00:13:05] **Carol:** little break away from it.

[00:13:06] **Ben:** we get the Thursday and Friday off, and then I'll probably take off some time around the, you know, the Christmas and New Year's holidays.

[00:13:14] **Carol:** Yeah. Yeah. A little break might be good too.

[00:13:17] **Ben:** yeah. And one other thing, my directors had the conversation, which I, I, it was like, just to, it stuck in my head afterwards cause we're talking about what I would do.

[00:13:25] **Ben:** I, I'm, my title is principal, I'm a principal engineer. That probably means very different things at, at every company.

[00:13:32] **Carol:** Yeah.

[00:13:33] **Carol:** It's like an executive level or C, It's a C level job, but you don't have to deal with budgeting as the way, like I've always had to explain to me

[00:13:40] **Ben:** that's definitely less than what we do

[00:13:43] **Carol:** Okay.

[00:13:45] **Ben:** But, but my, my director did in sort of this like passing comment, she was like, Yeah, you know, we'll have to bring you more into alignment with the roles of a principal engineer. And I was like, are there like a bunch of people who don't think I'm doing my job right now? That'd be,

[00:13:58] **Carol:** Oh, that hurts. Yeah,

[00:14:01] **Ben:** Especially cuz I almost look at myself as, as the director of the legacy product.

[00:14:06] **Ben:** Like I, you know, I, I feel like I'm much more than an engineer right now. I'm a product, I'm a designer, I'm a product manager. I do the roadmap. I deal with customer support. I mean, it's, if anything, I feel like I do more

[00:14:18] **Ben:** than what a principal engineer does.

[00:14:21] **Carol:** Agree.

[00:14:22] **Ben:** Anyway. That's me. That's what I got. Adam. How you doing

## [00:14:26] Adam's Triumph

[00:14:26] **Adam:** Well, just coincidentally, uh, I happen to have spent the last week since we talked, staying up very late at night doing off hours database migrations. I can't tell if I wanna consider this a triumph for a fail. So I'm gonna put out, I'm just gonna explain what happened a little bit, and you guys decide I want the three of you to sort of vote on it or however you wanna figure it out, but, So we have, 13.

[00:14:49] **Adam:** So our business is b2b. We have 13 customers for this particular product. And, I would say more than half of them are relatively small databases, not that big of a deal. but then when we did the migration, so we were migrating from MyQ five to MySQL eight because we're on aws and RDS is doing end of life for the version of of AWS Aurora, which is sort of their flavor of MySQL, their rapper around it.

[00:15:13] **Adam:** and so their eol and the version we were on, which means we have no choice but to upgrade and, you know, we could just, you know, wait for them to upgrade us in place and hope nothing goes wrong. But that's not a very responsible way to run a business. So, for the last month or so, we've been running all of our dev and QA environments on like the sort of the latest and greatest of, Aurora, and it's been going great. You know, of course with that upgrade comes a lot of great things. So, something, a couple things that are not available on the version of MySEQ we were on that are available to us now include CTE's, common table expressions and JSON column type. That's just two things that we're really excited about in the move

[00:15:53] **Adam:** among other things.

[00:15:54] **Adam:** So, got those things. so, you know, when you're, when you're doing a move like this and we have a couple of database instances and each instance has several databases on it, and so we could, upgrade that instance in place, and just hope for the best. But that left an uneasy feeling in our stomachs.

[00:16:13] **Adam:** Like the rollback process on that is, is pretty terrible if something were to go wrong. So what we decided

[00:16:18] **Tim:** mean, you couldn't have snapshotted it and then just roll back to the snapshot.

[00:16:22] **Adam:** maybe, but, you know, there's a lot of effort involved in. Well, okay, so there's, there's actually two things involved in this migration. Yes, we could probably have Snapchat and rollback, we would have to have verified that in advance and all that. It probably possible, but what we chose to do was a path that would allow us an instant rollback.

[00:16:40] **Adam:** So, I mean, and when I say instant, I mean just change the config to point the, at a different host name and, and then rerun the app and everything's back to the old database. the, so in addition to moving from MySQL five, six to eight, whatever, we also are changing our encoding and collation is the emoji thing that I've been talking about on and off for a couple of weeks now.

[00:17:01] **Adam:** Um, and so what, what ultimately happened was like we exported all of our data, using MySEQ. and then I wrote a script that, because those, those files that it exports are like double to in some cases, like triple digit gigabytes, uh, text files. So I wrote a, a file that will stream through that, right?

[00:17:20] **Adam:** Like read a line out of it at a time and then update the UTF eight, Unicode C to utf, A four, Unicode ci, all that, right? And just like go through this entire file and update it. and then we would import that updated one on MyQ eight. So there's sort of two things at once, that worked really well. but then, you know, that also complicated the, the

[00:17:39] **Carol:** the rollback, right? I mean, you

[00:17:40] **Adam:** the rollback and also, right, like if, if we were to try and do like an upgrade in place, we would've had to upgrade in place, which would take a bunch of time and then go through and do all the encoding collation thing. So we just felt like this was the better, approach. So anyway, the, the triumph and fail portion of this is, because this was, you know, such a intense thing, we were bringing websites offline intentionally to prevent any new data from being added while we're doing the backup and restore process, all that.

[00:18:08] **Adam:** We're working off hours, right? So we would work during the day and then go have dinner and come back. We regather the team and, and some of our customers are not in the same time zones as us, so we have to wait until like, you know, west coast is in off hours time, so we're not even starting till like nine o'clock

[00:18:23] **Carol:** Gross.

[00:18:25] **Carol:** Yeah.

[00:18:25] **Ben:** bedtime.

[00:18:26] **Adam:** and then start this process and, you know, sometimes it would go better than others, but I'll just say like of the last, you know, maybe say eight nights, we have been up past midnight on, past even like 1:00 AM working on stuff. And a couple of those were past like two 30, getting close to three, which was rough.

[00:18:43] **Tim:** But, we learned a ton of lessons, which is something we're gonna be talking about here in a few minutes. And. with one minor hiccup, it went off. the, the final result was without a hitch. Like when we were, when we said we were done, everything was done except for one little hiccup. So, Sounds like a win

[00:19:00] **Ben:** exciting.

[00:19:00] **Carol:** I mean, Yeah.

[00:19:01] **Carol:** I'm calling that a win man.

[00:19:03] **Ben:** I mean, it

[00:19:03] **Adam:** I mean, what I don't like about it is the fact that we had to stay up until like 2 33, a bunch of nights. That was rough. You know, go to bed at 2 33, get up at 5 45 to get my kids

[00:19:13] **Carol:** Still gotta get the kids on the bus. Yeah. I mean, it doesn't sound like you did it in a way that anyone would wanna replicate or do again, but it definitely sounds like a win that you got it done.

[00:19:24] **Adam:** Yeah, it was tough. All right, well I'll put it in the wing column then.

[00:19:28] **Carol:** Yeah. Triumphs so half and half. I mean, I really just wanted at least two people to win this week, so,

[00:19:34] **Adam:** why it's a triumph.

[00:19:35] **Carol:** Yeah.

[00:19:35] **Tim:** There you go.

[00:19:36] **Tim:** All is balanced in the.

[00:19:38] **Ben:** one other thing that you might enjoy about MyQ eight is there's something called a lateral join,

[00:19:44] **Adam:** Oh

[00:19:44] **Ben:** is, is, like a

[00:19:45] **Carol:** is a lateral join.

[00:19:47] **Ben:** So with a reg traditional join, you're, you're, you're joining Rose to Rose, but in a lateral join, you're joining rows to subqueries. So you can essentially run a subquery per each row.

[00:20:02] **Ben:** And then the beauty of that is that you can reference that entire subquery in your, select statement.

[00:20:08] **Adam:** Hmm. I, I'll have to look that up and look at the syntax, cuz I already did a lot of stuff similar to that. Like just as a sub-select, as, you know, as if it were a table in my, from clause. or I've done sub-select as a, as a column in my, in my select statement too.

[00:20:22] **Ben:** yeah,

[00:20:23] **Carol:** didn't know it was called a lateral clause.

[00:20:26] **Ben:** Well, so, so when you do a, from. And then a select, that's a, I think that's a derived table. You're basically creating a table that you're joining to, you know, in memory table set, with the lateral one, you're doing it, you're, you're essentially doing that, but you're doing it per row of the previous table.

[00:20:44] **Ben:** So instead of it kind of creating an isolated table that you gen joined to, you're essentially doing that once per row. So it just, it's, it's a lot more work for the database, but it gives you more access to, the data.

[00:20:56] **Adam:** Interesting. Sounds incredibly inefficient.

[00:20:58] **Ben:** Yeah.

[00:20:59] **Tim:** Yeah.

[00:20:59] **Tim:** it does actually, although I'm sure

[00:21:02] **Tim:** they've optimized it.

[00:21:03] **Ben:** Yeah. Yeah, yeah. But anyway, it's, it's, it's one of those things to have in the back of your head.

[00:21:08] **Adam:** No, I, I appreciate that. It sounds like it could be interesting. So I'm gonna look that up and maybe I'll

[00:21:13] **Ben:** It's, it's like, so you know how you, you do your, you talked about your select statements, and you'll do a sub query inside of a select state.

[00:21:19] **Adam:** Yeah.

[00:21:20] **Ben:** The, the, the downside of that, or the, the drawback historically is you can really only reference one value coming out of that sub-select, unless you try to do like a group concat or like, or you know, something funky that joins columns together.

[00:21:35] **Ben:** If you wanted to say, do a sub-select and grab two columns, like can't do that. So the lateral join essentially allows you to do that because you're moving the sub-select into the join, and then you can reference the entire sub-select result in the select.

[00:21:50] **Carol:** Mmm

[00:21:51] **Ben:** you could do multiple columns, you could

[00:21:53] **Tim:** I mean, Postgres can do that. So

[00:21:56] **Carol:** Wait, wait.

[00:21:57] **Ben:** could I just do like a really quick aside for a second? I, I, I was, I was writing about some JSON stuff in MySQL and I posted this thing on Twitter and I said, Oh, this is a fun little thing I did. And someone said, Oh, you should just use Postgres. It has much better JSON function.

[00:22:13] **Ben:** And I said, I said, I'm

[00:22:15] **Ben:** The funniest thing that I said, I'm not very familiar with Postgres. What would this look like in Postgres? And the guy wrote up a little snippet equivalent and he's like, Actually, this looks much worse than Postgres.

[00:22:31] **Tim:** Have you heard of our Lord

[00:22:32] **Tim:** and Savior

[00:22:33] **Tim:** PostgresSQL?

## [00:22:35] Lessons From Adam's Databse Migration

[00:22:35] **Adam:** Alrighty. Well, I guess, uh,that covers tram and fails, so let's move on to the main portion of the show. I, I did write an article about this on my blog slash Digital Garden, but I thought it was worth, bringing over here and we could just, you know, kind of open it up and, and get some real time feedback from the three of you. the difficult part here was moving really big databases, right? And especially really big tables. So maybe the best thing to do is to start by saying, like, when I say big tables, I'm talking about, when you look in MySQL at the information on the table, it tells you, that it's somewhere between like a hundred and 150 gigs.

[00:23:07] **Adam:** And we we're talking about maybe anywhere between, you know, like 30 million and 150 million, rows in the tables. So it's, you know, quite a lot of data. and, you know, we went into this process kind of naive. You were like, Okay, well that's just MySQL dump and stream through the file to change the coalition in the encoding and then, you know, pass that into MySQL to import it and we'll be good.

[00:23:31] **Adam:** And that worked great for this, the databases for smaller customers. But, the customers with lots of data that did not work so great. for starters, the mice equal dump for the longest customers would take like several hours, and the dump is always way faster than the import.

[00:23:48] **Carol:** So you. You're up for a, a long night then? Yeah.

[00:23:52] **Adam:** and then

[00:23:53] **Ben:** Can I, can I interrupt you for one second, just for some clarity? So I, I think earlier in the trium and fails, you said you have four separate database instances, and then they each have multiple customers on them. Is that

[00:24:06] **Adam:** so yeah, let, let's talk about that a little bit. Um,

[00:24:09] **Ben:** I just, I I I, wanna understand like how many things have to happen in lockstep, essentially.

[00:24:14] **Adam:** So for these 13 customers, they are spread across two different, database clusters. so, we have two clusters. Each cluster has a read and a right dedicated node. so, and they're that way if there's a problem, they can fail over from the writer, the r the reader becomes the new writer, and the writer can get replaced as the, and become the new reader.

[00:24:35] **Adam:** and, so there's 13 customers spread as evenly as we can make 'em, both in number and in usage across those two clusters. So one has six, one has five. remember what, six and seven, Sorry, math, it's hard. so, yeah, the, the plan, the naive plan going in was MySQL dump and, and then import back into MySQL.

[00:24:56] **Adam:** and like I said, that that worked reasonably well to start. Um, and then we started hitting the big customers. And, like, how do I wanna explain this? I guess the, there's something that MySQL, MyQ dump does for you, that I guess we didn't think about when we started shifting our plans. So for these larger tables, one thing that we realized is that we, can export data to S3 as a CSV file, right?

[00:25:22] **Adam:** So, you can do a select statement, Oh, this is an Aurora specific feature, but you can do a select statement, and if you have all the right permissions and config hooked up, you can select. And then in that select statement you say like, you know, output to file on S3, this bucket with this file name, and it spits out, a very well formatted CSV file,

[00:25:39] **Adam:** which is very handy.

[00:25:39] **Adam:** We, this is something we've been meaning to look into anyway and when. When I had to learn how to do it at two o'clock in the morning some night, I was like, Okay, well this is definitely gonna come in handy cuz we're gonna start doing some reporting this way. but so you can export to S3 and then you can also like, you know how you can do like a load data local to just read a CSV file and import it into a table?

[00:25:59] **Adam:** You can also do the exact same thing, but pull it from S3 as well.

[00:26:03] **Carol:** Oh, so you don't have to ride it locally. You

[00:26:05] **Adam:** it, it never

[00:26:05] **Adam:** has to

[00:26:06] **Adam:** leave your VPC trans. Yeah, it never has to download across the, the internet just stays right there in aws, which again, you know, is another little way that it improves the, the speed and efficiency. So, but the, the downside to that approach is that you have to do all of the little bits that that MySEQ dump would do for you.

[00:26:25] **Adam:** So you have to create the table, you have to add the indexes and the, the foreign key constraints, that sort of thing. And if you get them out of order, then it's inefficient, right? So for example, you create the table and you put on your foreign keys and the indexes just because like, In certain database management software, you can right click a table and say, Okay, gimme a create table statement.

[00:26:43] **Adam:** And it gives you the table with all the indexes and the four keys and everything. You're like, Okay, let me run that to recreate the table and the new thing and then I'll import the data, which was again, just be naive. and so that's where we started. And then we, you know, you're several hours into a single table load and you're like, Wait a minute, , this is not going fast enough.

[00:27:00] **Adam:** We're gonna be here all week just for this one customer. If we don't, if we don't figure out something better, that's where, okay, duh. You know, if you've got two or three foreign key constraints for 20 million rows, it has to go and check every single one of those rows that you insert against two or three other tables to make sure that, that the value exists when you know, because you just exported it half

[00:27:20] **Carol:** It's already

[00:27:20] **Carol:** there.

[00:27:21] **Adam:** the data is there, the integrity is fine.

[00:27:23] **Adam:** Those foreign key constraints protect you, like at app or on time, not at export, import. They can help you. I don't wanna misspeak, but, in this case, they weren't necessary. And so that was lesson number one is, is when you're doing those bulk inserts, disable the foreign key checks, which is such an easy command to run.

[00:27:41] **Adam:** And I'm, I'm 99% certain that that is one of the defaults in MySQL dump. But then, you know, this is one of the situations where we stepped away from MySQL dump.

[00:27:49] **Ben:** Sorry. You're saying that that's, You can, you can literally. Set and say like, Hey, the next couple of commands, like next couple of inserts that run, don't worry about foreign key constraints.

[00:27:59] **Tim:** Yeah,

[00:28:00] **Tim:** you just set

[00:28:00] **Ben:** that's pretty cool.

[00:28:02] **Adam:** Yeah. So, okay, so I, I have a blog post and we will link it in the show notes. Ben put it in the show notes,

[00:28:08] **Ben:** Yes.

[00:28:09] **Adam:** Um,and, and the lesson number one, sort of near the top there is the, the two statements that, you know, you disable foreign key checks and then reenable it at the end. And it, that setting. To the best of my knowledge only applies to the current session of the, the connection.

[00:28:26] **Adam:** Right. So if I said it, it only happens, it only takes effect for the requests that I make during that

[00:28:32] **Adam:** session. So, Right. So the application is still obeying foreign keys, but my

[00:28:38] **Tim:** but no one's hitting it

[00:28:39] **Carol:** But you took your application offline. Right.

[00:28:42] **Adam:** right. I'm just explaining for the, for the benefit of anybody who might choose to do this, you know, with

[00:28:46] **Carol:** Who like, I don't, I can't even wrap my head around how you would do this with the application online.

[00:28:53] **Adam:** I, I wanna come back to that. Let make sure you, when we're, when we get through lesson three and we're done with all that, ask me again and I'll, because part of my reason for sharing all this information here and on my blog, and once I got the blog done, I wrote it up like a Twitter thread and I posted it on Macon and everything.

[00:29:09] **Adam:** And part of my reason, my justification for sharing it everywhere was I wanted to invoke Cunningham's. So if you're not familiar with Cunningham's Law, basically it's, in order to get the right answer to a question, don't post the question online, post the wrong answer, and somebody will be so outraged that you posted

[00:29:28] **Adam:** the wrong answer, that they will come and give you the right answer. has nothing to do with our beloved Tim Cunningham here

[00:29:33] **Adam:** on the

[00:29:33] **Tim:** nope. No. It was Robert.

[00:29:35] **Adam:** just

[00:29:35] **Adam:** a lucky coincidence. Yeah. So I was hoping I was sharing this information, hoping that somebody will go, actually, you know, there's this really easy, great tool that would help you this and this and this. And I did get a couple of those things.

[00:29:45] **Adam:** So I wanna share those after we get through the, the initial stuff here. Okay? So, disable foreign key checks for bulk inserts that saves you a bunch of time. That's lesson number one of the, the three or four lessons that we learned, this week. the, the second was, well, you know, I, I, I've. Labeled that lesson number one.

[00:30:05] **Adam:** But really the first one was when we, decided to use, export to S3 and then load import from S3. Right? That was really lesson number one. and, and that worked out great for us. And then it's listed as lesson number three in my blog post, but

[00:30:18] **Tim:** And then when you create your new tables, you didn't put indexes on 'em.

[00:30:21] **Tim:** yeah, that is also true. it, it's tough to kind of figure out the best way to explain all this and, and have it make sense. But yes. When we did this s when we did this approach with S3, we, exported the data, recreated the tables with no indexes. No primary

[00:30:37] **Adam:** it did have, they did have primary keys. They,

[00:30:40] **Carol:** Well, if you didn't insert it with a primary key, wouldn't you have to run something after to say it was a primary key and it doesn't? That process take a long time.

[00:30:49] **Adam:** I probably would have to do a table scan. I don't know. But we, we did leave the primary keys and we defined the constraints, but we did, we again had them disabled, right?

[00:30:57] **Tim:** them off. Okay.

[00:30:58] **Adam:** Um, so, so we create the tables, do the S3 bulk import, and then go back and add the indexes and that sort of thing. So that was kind of lesson number one, less.

[00:31:07] **Adam:** Number two was disable to foreign key checks. And then lesson three, again, just being naive, we, again, I've talked recently about this like queued warehouse importer process. I, I built a couple of weeks or months ago, to, to queue up, requests to import data from our customers on a nightly basis.

[00:31:25] **Adam:** And that process does something kind of similar, right? Like it creates a new table, imports the new the data into their new table, and then indexes it and drops the old one and renames the new one to have the same name as the old one in a transaction. and so I just kind of like went and copied and pasted the syntax I was using in that job, over here to, to create indexes.

[00:31:46] **Adam:** And it was, it was naive. It was like, you know, if I need to create three indexes, it was create index, index name using beri on table name, parentheses, column name, right? So just like a very naive, just create an index on this table with this column, which seems fine. But then when you realize that, in order to make an alteration like that to a table, you have to do a full table copy.

[00:32:09] **Adam:** So if you're copying a table that is a hundred gigabytes and then making an alteration and doing a rename, and then you're ju and then you've got three or four more indexes you're

[00:32:18] **Adam:** creating, you're copying that table over and over and over, which just takes forever. So there's a way to make multiple.

[00:32:26] **Adam:** Alterations including, adding indexes, in a single command. So it'll do one copy, make the alteration, and then do the rename. And that saves you a ton of time. so that's, that's those the three big lessons that I picked up from that. and then sort of, we, we touched on it a little bit, doing the, the, indexes after the bulk import was huge.

[00:32:43] **Adam:** but adding those indexes when you have, you know, a hundred million rows is still gonna take a ton of time. And we didn't want that. I mean, we, we at one point saw, a query like that running, adding indexes run for more than six hours.

[00:32:59] **Ben:** Oh my

[00:32:59] **Adam:** This is, Yeah. Well, so one of these, one of these things, because the customers had stuff they didn't going on in the evening.

[00:33:05] **Adam:** They were like, You may not migrate us in the evening. You're gonna have to wait till the weekend. Fine. We'll do it on the weekend. So we, one of these days that we worked was Saturday, and we worked literally all day Saturday. Like we started eight or 9:00 AM and it went to two or 3:00 AM

[00:33:18] **Carol:** Oh my goodness. That's awful.

[00:33:21] **Ben:** no. Thank

[00:33:21] **Adam:** I would be so angry. , I'm sorry,

[00:33:25] **Adam:** well, I mean, we took breaks, right? We, we have multiple people working on, so we can kind of work in a little bit of shifts and do some, some overlap and some handover type stuff. But

[00:33:32] **Carol:** but you never get to turn your brain off

[00:33:33] **Adam:** no, I, I mean, it's kind of funny during that, during that process, while that was all going down, I took my kids, my whole family, we went, rock climbing for like an hour

[00:33:42] **Carol:** Oh, that's cool.

[00:33:44] **Adam:** and just like, you know, go out, have some fun family time. So one of the other sort of bonus tips that we, we figured out here was, since we were doing this S3 export from databases, when you, when you do that select into out file on S3, it automatically splits those files into six gigabyte chunks. So you get like, you know, file dot csv part 0,0,0 0, and then you get part 0,0 1, whatever,

[00:34:09] **Carol:** Is that good or bad?

[00:34:11] **Adam:** In this case, it worked out really well for us because what we did was, for a certain table, like for the largest table and the largest customer, what we ultimately ended up doing was, we were able to, do all the other imports except this huge table. And then we created the table. You know, again, no index.

[00:34:30] **Adam:** foreign keys, disabled. And then we only imported the most recent, actually, I think we did this for two tables and they were related, only imported the most recent file, like that last chunk. So the most recent data. and, and then we turned on the indexes, and, and everything. And then we turned the application back on so that things could, could go.

[00:34:49] **Adam:** And you have to be careful, you know, you have to, So there's, we use auto increment, primary keys, and you don't want a new insert to take up space that you kind of skipped at the beginning of the table.

[00:34:58] **Carol:** Ah.

[00:34:59] **Adam:** so you have to, when you create the table, you say, Okay, auto increment, all new values start at this number, right?

[00:35:05] **Adam:** And we just left a whole bunch of head space for our inserts, for our, like if our, if our max value or max primary key was, you know, 150 million, then we would've done like 170 or 180 million, right? Just to leave a room.

[00:35:19] **Carol:** Yep.

[00:35:21] **Adam:** And, and then that leaves you all those, those first 180 million keys that you can insert from your bulk backup.

[00:35:27] **Adam:** so we, we did that. We, we just imported that last chunk file, which is something less than or equal to six gigs. I mean, I think on one of 'em, it was like one and a half gigs. But, we imported that data and then turned the application back on and we just posted an announcement that said, Okay, the application is up.

[00:35:42] **Adam:** Everything's fine. You just have, some historical data in these two tables that are still slowly loading. Everything else is fine and new data is working fine. And that was at, you know, whatever, 2:00 AM we posted that announcement

[00:35:57] **Tim:** I'm sure they were all checking their email on that

[00:35:59] **Carol:** Yeah,

[00:35:59] **Adam:** right. And, and then we queued up the imports of all those other files, that were, you know, parts zero through whatever, through n minus

[00:36:08] **Carol:** was. Yeah.

[00:36:09] **Adam:** And, and and then went to bed. We're like, We'll check on it in the morning.

[00:36:13] **Adam:** And cuz we knew

[00:36:14] **Carol:** what files, right?

[00:36:15] **Adam:** Especially because not only was it going to be doing, the foreign key checks that that would slow it down, it's also gotta rebuild the indexes for every row that it

[00:36:24] **Carol:** Yeah. It's gonna

[00:36:24] **Adam:** which is just forever. So we cued that up.

[00:36:27] **Adam:** We went to bed. I, first thing I did when I woke up in the morning was go check on. I was like, What is the status? You know, how far along is this thing? And I, I couldn't believe it at first. When I looked at it, it said it was done. I check like the, the script said it was done running. I checked the database and it was quiet, Nothing was there.

[00:36:41] **Adam:** And I checked the tables and it's like, I've got values one through, you know, whatever that, that max primary key was. They were all there. I'm like,

[00:36:50] **Tim:** 155,834,091

[00:36:53] **Adam:** Whatever it was. Yeah, it, it quite a lot. and so it, it, it worked surprisingly well after so much, sleep deprivation. I'm surprised we came up with a plan that worked as well as it did. I said, you know, a couple of people have made suggestions, but.

[00:37:09] **Carol:** usually projects like that, you just keep repeating the same failures over and over again because you're not in any state of mind to make adjustments that make anything better. You just keep doing it poorly and usually make it worse. So good news to you for not doing worse, and it sounds like you made it better.

[00:37:27] **Adam:** Well that, that's the thing is like we could tell if we didn't try to find ways to improve with each, each night that we were doing this, that we were going to be well over the 24 hour mark for a, a customer migration. And that's just was not gonna fly. We had to find a better way.

[00:37:44] **Carol:** Oh.

## [00:37:45] Fail-back Plan

[00:37:45] **Tim:** So let me ask you what was, I mean, you, you should always go into these things with, assuming you're gonna figure it out, but what was your fail back plan if things just

[00:37:54] **Tim:** really went badly?

[00:37:56] **Adam:** so. The way we set things up. When we were to start a migration, the first thing we did was we have a load balancer and we, we, at the load balancer just took that entire customer website, every URL you could possibly hit and just send it to like a, a, we send a 5 0 2, which is a quick text response, like, we're down for maintenance will be right back.

[00:38:14] **Adam:** Right? So any of our external services that are calling APIs, like we have, mail gun and they'll send us web hooks to say, Oh, this message was opened or this link was clicked, or whatever it's gonna be. We didn't want any of those to be even acknowledged with a 200 because mail gun would interpret that as, Okay, you got the data and I can stop trying to send it to

[00:38:32] **Adam:** you. So we needed every request to get a 500 response. We did that at the load bouncer and that took the entire website offline. Nobody could do anything. And then once that was done, that's when we started our final backups, which actually maybe that's another thing I can mention is so these bulk S3 exports took so long that one thing that we did, was, and I don't think this even made it into the, the blog post, I'll have to think about going back and adding it, is, we did that bulk export initially during the day.

[00:39:03] **Adam:** So like if I, on on Friday morning for this one customer that we ended up running on Saturday, on Friday morning, I started exporting just the like three, four largest tables to S3. And the plan was they're gonna continue writing to that, but at some point this export is gonna finish and it's gonna be up to Row n right?

[00:39:21] **Adam:** And you know, they might have n plus 10,000 rows or something like that, but that 10,000 rows is gonna be a lot easier to add as a secondary backup, right? So if it's called a table, like, I dunno, API log or something, right? So you've got all this data backed up and then, after you bring the website offline, you have an extra 10,000 rows that you need to export.

[00:39:43] **Adam:** But you don't have to start from the beginning cuz the most of it's already done. So you just need to select those rows. You know, greater than the greatest primary key that you already exported and, and export that to another file and you just import those all and you're good. It doesn't even, the order you import them doesn't even matter because the primary key is part of the export.

[00:40:03] **Carol:** Assuming your table doesn't allow deletes.

[00:40:05] **Carol:** yes, you are absolutely right. That was something that we did, think about actually it, which is that, this process only works for what we were calling append only tables. Otherwise you gotta check backwards or redo it all.

[00:40:17] **Adam:** Yeah. And so there were a few of the larger tables that we had no choice but to wait until the website was down to do the backup, cuz otherwise we were just gonna have to repeat the work.

[00:40:25] **Adam:** so yeah, we took the website down, took last, we called them last sliver backups are the ones that I was able to back up in advance. and then full backups of any of. Tables that we deemed too large to include in our MySQL dumps, which for us, we just did it for anything over like a gig or gig and a half.

[00:40:42] **Adam:** there's a query you can run in MySQL to give you the size of the, the data in the table. And so that's what we used, to, to make our determination. and so then, you know, the, from there we were to start on the process of restoring. But to answer your question, Tim, what we did was we left the existing database clusters and databases alone.

[00:41:03] **Adam:** The only thing we did to change them after all of our exports was done was we changed the passwords on all of the users so that anything out that we're not thinking about that we might forget to update, would fail to connect.

[00:41:14] **Adam:** so like if we have, you know, microservices or whatever that are trying to connect directly to the database, we, by changing the password, we make sure that none of them can actually still connect to the old database.

[00:41:24] **Adam:** and, and, So then they would, they would start failing and we would get notifications to, to go fix those things. and then, and, and we still have of course records of all the old passwords in our team, password manager. But, to, again, to answer your question, if something were to go wrong with the restore and we needed to go back, it was as easy as changing those users passwords to be what they should be.

[00:41:46] **Adam:** And then going back and updating the config to point the host name. I, at this point, we probably wouldn't have even changed the host name. It would still be pointing at the old database and just turn it back on. Let it all still point there.

[00:41:57] **Carol:** So you, you, you didn't leave your old database online anywhere. You upgraded what was there. Right.

[00:42:05] **Adam:** No, no. We created new databases with the new versions and, and move the data or copied the data over

[00:42:11] **Carol:** So you've still had those. Technically they could be turned back online.

[00:42:14] **Adam:** there. Yeah, they're actually still running. In parallel, we're gonna probably

[00:42:17] **Adam:** give it a you. Yeah.

[00:42:19] **Tim:** Yeah.

[00:42:20] **Adam:** you're taking notes. There's gonna be a quiz later.

## [00:42:22] In-Place Upgrade

[00:42:22] **Tim:** was an in place upgrade, not available. I mean, did you try that first? Like just doing an in place upgrade?

[00:42:28] **Adam:** I believe it is available. but between the worry about something going wrong and no, no idea of how long it would take, we just, and then combine that with the need to do the encoding and coalition change as well.

[00:42:43] **Tim:** Right.

[00:42:44] **Adam:** we just decided it was better to combine them

[00:42:46] **Tim:** you said

[00:42:46] **Tim:** you were going from which vers, which version to which version?

[00:42:49] **Adam:** it was 5.6 to whatever the latest, MyQ version is that Aurora offers, which I've, I remember correctly is, 8 0 2 or three, or is it 23? Whatever is, It's a very recent version of

[00:43:01] **Tim:** Okay. We just set your mind at ease. We did, we tried to do a, this wasn't Aurora, but this was actually, an on-prem upgrade. Tried to do it in place, upgrade from 5.7 to eight. It failed miserably.

[00:43:14] **Ben:** Really?

[00:43:15] **Tim:** Absolutely. Just did not work.

[00:43:17] **Adam:** Vin.

[00:43:18] **Tim:** Yeah. Did not work at all. So we had to, we had to, we had to back up and go, kind of do kinda what you're doing and, you know, just, just import the data and rebuilding everything.

[00:43:27] **Tim:** So, yeah.

[00:43:29] **Adam:** Nice. Ben, did you get the reference? Is that why you were laughing?

[00:43:31] **Ben:** no, I, What's the

[00:43:33] **Adam:** Oh, it was a Brooklyn 99 reference. Sorry.

[00:43:35] **Ben:** I'm Brooklyn nine s on my list of things to watch.

[00:43:38] **Tim:** Yeah, I've watched it, but I missed that reference. So.

[00:43:40] **Ben:** I had to step away for a moment. Earlier when you guys were talking about disabling the indexes for the, uh, the bulk insert, did that include the primary key or was that just secondary indexes?

[00:43:51] **Adam:** I can tell you the exact command that I use, but I can't answer that question. I don't know.

[00:43:54] **Ben:** Oh, it was a

[00:43:55] **Ben:** command.

[00:43:55] **Adam:** say probably not. Cuz the command is set, four in key checks equals zero, so it probably

[00:44:00] **Ben:** Gotcha. Okay. Okay. The funny, I mean, just from a technical standpoint, my understanding is that the primary key acts like influences the actual storage, like the physical storage of the record so that they're next to each other on disc.

[00:44:19] **Ben:** So I didn't know if, if you could, I didn't know if you had to keep a primary key in place when

[00:44:26] **Adam:** So we actually didn't,

[00:44:28] **Ben:** Yeah,

[00:44:29] **Adam:** Yeah, we did this in a way that wouldn't change any primary keys. So they would all still have the same value. Now we may not insert them in the right order, and if, if somebody out there, happens to know that this was a terrible thing that we did by, you know, keeping the same values but inserting them in different sequence.

[00:44:45] **Adam:** Please let me know. Yell at me, mac it on Twitter or whatever, however you can get ahold of me.

[00:44:49] **Ben:** I think

[00:44:50] **Adam:** I

[00:44:52] **Ben:** So I think the issue there is that as you insert. values that have to be next to each other, it has to then start shifting records around on disk. I, I don't really,

[00:45:04] **Tim:** So when you, when you create, when you, create a primary care, you think it's, it's actually moving things physically to different blocks on the disc

[00:45:09] **Ben:** Yeah, I think it creates, like, I'm doing error quotes here pages, and I don't really know what a page is, but it's like a certain amount of information and

[00:45:17] **Ben:** I

[00:45:17] **Adam:** could be, Yeah.

[00:45:18] **Tim:** page.

[00:45:19] **Adam:** and

[00:45:19] **Adam:** there's also sharding, which is not something we're currently using.

[00:45:22] **Ben:** Yeah. Yeah. So were you, uh, sorry, different topic. you talked, you have several clusters and each cluster has like five to six customers on it.

[00:45:30] **Ben:** Were you moving a, an individual customer at a time to a new Myse eight cluster? Is that how that

[00:45:38] **Adam:** for the most part, yes. So when we had, you know, we started with our smallest customers thinking like, okay, let's, let's kind of kick the tires on this gently and, you know, see what we can learn early, when, when things are gonna be easy and, and work our way up to the, to the biggest, hardest

[00:45:54] **Ben:** Well, that's great. I mean, that builds

[00:45:55] **Adam:** by itself. Yeah. and so for that first, like the very first night, I think we did three customers at once. And so we, we pulled one from each of the, of the two clusters and then we pulled a third, just whatever seemed small. and I think we ended up, doing them sort of sequentially, right?

[00:46:11] **Adam:** We were like, let's run the two in parallel cuz they're both coming from, let's just say cluster A and B, and then we're moving them to MySQL eight cluster A and B. Right. And so, there's, there's like no overlap in CPU or, or anything. The only, only way they would have any, Conflicts or, or, collision memory collisions or anything.

[00:46:30] **Adam:** Network collisions is, they were both technically running from the same server. So this was another thing that we did that, that I'm sure saved us a bunch of time and, and stuff, is we spun up an EC two instance. We have, an EC two instance that we keep for sit for situations like this where we want to, ETL basically extract, transform, and load, data off of a database, do something to it, and then push it somewhere else, inside of our vpc.

[00:46:53] **Adam:** So like for example, when we refresh

[00:46:55] **Adam:** QA from

[00:46:56] **Carol:** what's a vpc?

[00:46:58] **Adam:** cloud, it's just like our, our a group of resources, on aws. And you can have like multiple VPCs. It's like a, kinda like a subnet. I, I don't wanna speak too authoritatively there. I don't know that much about all of that, but

[00:47:11] **Carol:** Since I only live in like coding now, I miss out on a lot of these terms that I used to know when I worked with him and at my other job, because you had to know everything. I don't have to know all that anymore because we have DBAs, we have devs engineers, we have IT support, so I don't have to know that stuff.

[00:47:32] **Carol:** So I'm like, Where does it live again?

[00:47:34] **Tim:** It must be

[00:47:35] **Carol:** Tell me where it goes. Tell me how to get there.

[00:47:38] **Adam:** Yeah, so, so we have, just a regular like EC two windows instance that when we want to, for example, refresh QA from production data, we remote desktop into this Windows EC two instance and do like a MySQL dump and then import it into the, the new one. And that way it never leaves our, VPC on the cloud.

[00:47:54] **Adam:** So it doesn't have to, you don't have to like download a five gig database back and then re-upload it, Right? It's all right there. It's like, you know, whatever. I, I hope that's clear and I don't have to continue making analogies, but, So we use that same

[00:48:06] **Carol:** he's currently, for everyone listening, he's currently pointing at his screen and making lots of circles while he talks about where things are at. Sorry, you can't see it.

[00:48:15] **Adam:** hand, wavy gestures, probably a lot of that in episode 100. If you wanna go watch the video, I hear

[00:48:20] **Carol:** Yeah.

[00:48:23] **Adam:** if you only listened and you, and you haven't watched, there have been several people that have told me that, they were, they were listening to episode 100, or they decided to switch over and watch the YouTube video and it was well worth, re-listening to the beginning to catch up to where they were and, and see the whole thing.

[00:48:38] **Adam:** So,

[00:48:38] **Tim:** Yeah, you, you, gotta see the pain. I mean, being doubled over.

[00:48:42] **Tim:** Dropping duck, duck, duck, bombs.

[00:48:46] **Carol:** I've been told I fidget a lot. I don't know why they think that.

[00:48:51] **Adam:** you

[00:48:51] **Adam:** never.

## [00:48:55] utf8 to utf8mb4

[00:48:55] **Ben:** One thing that I don't fully understand when it comes to the character and codings. Is that my understanding is that, old school utf a meaning the ut a, that wasn't really feature complete. it's like things took up to two characters, like up to two bites per character maybe. And then with the ut f a and before, which is the real ut F eight, it can like take anywhere between two and four bites or something depending on how big the emoji is.

[00:49:22] **Ben:** But like, I don't, I think that's only for data you haven't stored yet. Meaning does, does the physical size of the data that you took from MyQ five six and moved it to MyQ eight, did any of the tables like blow up in size or it's all really the same data, so it's all the same number of bites really?

[00:49:41] **Adam:** Does that, does that question make sense?

[00:49:42] **Ben:** Like I, I'm, I'm, I'm always

[00:49:43] **Adam:** you're headed with this, so. And I can answer this actually, as far as I know, no, nothing, nothing blew up. So if, if something took up two bites on our old database, it takes up two bites now. And MyQ, or I'm sorry, UTF eight M four was available to us on MySQL five six. but we had been kind of kicking the can on that upgrade, in large part because, of problems with indexes.

[00:50:08] **Adam:** So I don't have any definitive proof that this is the case, but based on my testing, it seems that a limitation in MySQL five six has been increased or fixed or whatever in MySQL eight. And so part of the reason that we didn't immediately convert to MB four on five, six years ago when we learned that that was the problem stopping us from supporting emoji was, an indexed VAR column or VAR car, depending on how you like to pronounce it.

[00:50:38] **Adam:** I say gif and gif just to piss everybody off. an index column, you can have any length that you want, but you can only index up to 767 bites on MyQ five, which works out to, if you're using two bites per character, 255 characters. So if you try to index something greater than 255 characters, oh God, it's been weeks slash months since I've been down in the details of this, so I'm probably gonna get some of the little parts wrong.

[00:51:09] **Adam:** Please be forgiving and generous here,

[00:51:12] **Carol:** And you've had many nights of no sleep or little sleep, so.

[00:51:16] **Adam:** But whatever the particular numbers are, it was not big enough for us, right? So we have, you know, we send emails and things like that and so, you know, an email subject is probably not a great idea to have a 500 character email subject, but there's nothing stopping you from doing it.

[00:51:31] **Adam:** And so our system needs to support that. Right. And, and lots of other similar situations where you've got potentially a lot of data and you need to index that so that you can search it. Right? Where was my message that, you know, mentioned football or whatever. Right? and so we thought of a couple of possible workarounds, like having a column that, is the, like a UTF eight two bite and UTF eight, and before like having two separate columns to contain the same data and just like cleaning the high ask characters out of the two bite column.

[00:52:01] **Adam:**

[00:52:01] **Adam:** so that that one could be indexed without, you know, any special characters, which Okay. You know, then if you searched for your emoji, it wouldn't come up or something. But, you know, you get partial credit on your searches sort of thing. that for whatever reason, that doesn't seem to be a problem anymore. I haven't specifically tried, but I have to believe that, you know, we've got really large columns, you know, in the vicinity of 500 or. A thousand characters that are MB four that are indexed now on MySQL eight. So that's another bonus to the upgrade.

[00:52:34] **Tim:** Hmm.

[00:52:34] **Ben:** Very.

[00:52:35] **Tim:** cool.

[00:52:36] **Adam:** yeah, so, I mentioned like we did all this work, 13 customers going through this getting increasingly harder, longer, more data tireder as you would go.

[00:52:46] **Adam:** and, and we made it to the finish line and everything, was, you know, honky door, we reported to our customers. Everything's done, everybody's up. All, all is right with the world.

## [00:52:56] Adam's Error

[00:52:56] **Adam:** here's the one thing that I screwed up. that, Yeah, that, that like, oh, I can't believe I missed that. Right. So, the process that I talked about a little bit earlier, the queued warehouse importer.

[00:53:06] **Adam:** So on a nightly basis, all of our customers send us updated copies of their canonical data, right? this is

[00:53:14] **Carol:** oh, no.

[00:53:17] **Adam:** Carol sees where this is going. This is the, you know, the source of truth of information about all the people that they keep track of, right? This is, Carol's, graduation year and her home address and her phone number and email and all that other data that they have.

[00:53:30] **Adam:** and the application that I wrote, the microservice that does, handles all these files in acute fashion. I had anticipated this problem and created poll requests once, one for each customer because I wasn't able to anticipate which customers would go at which time. That would definitely wouldn't all be going at the same time.

[00:53:49] **Adam:** So I created individual poll requests for each customer to update their scripts to specifically say, Okay, use UTF eight M four for all these tables that we're creating.

[00:53:59] **Ben:** Hmm.

[00:54:00] **Adam:** And we completely forgot about every single one of them. Uh, and so we did all these deploys. And then, and everything's great, everything's honky dory.

[00:54:09] **Adam:** And then the next day they come in and they, you know, their, their automated processes import their latest data and, and again, that's fine, it works. But now you've got a table with UTF eight, Unicode C trying to do, joins against U T F UTF eight and before you code ci, which works, MyQ will do it for you, but it is slow

[00:54:31] **Adam:** af

[00:54:32] **Tim:** Mm. Mm-hmm.

[00:54:34] **Adam:** And so we started getting, we started getting alerts like, why is this process all of a sudden just slow, you know, something that used to run near instantly. And it's not, it's not like it's trying to update one row or we're talking about, you know, create a temp table and

[00:54:48] **Carol:** It's all the ro Yeah, it's

[00:54:50] **Adam:** and, join it to this thing and delete a bunch of stuff.

[00:54:51] **Adam:** It's a lot of data moving around, but it's stuff that previously was running super efficiently. We kind of fine tune. All of a sudden it just started blowing up. We're like, What? Nothing changed. What is going on? Well, something did change, and that's the problem.

[00:55:06] **Adam:** and so, we just had to merge all those pull requests, redeploy the, the cube warehouse importer.

[00:55:11] **Adam:** And we, we, that was something that we spent some time on today, was like, okay, we could either try to upgrade all these tables in place that are, are in the wrong encoding, or we can re-import them with the importer, which would require like moving files on S3 and queuing up jobs to re-import them. We ended up, updating them in place,

[00:55:30] **Adam:** uh, and it worked okay.

[00:55:31] **Adam:** it was faster than I expected, you know, out of a system. You know, the, the entire application, you've probably got 150 plus or minus tables. and 20, 25 of them are those customer tables that they provide to us. So it wasn't a ton of data, but.

[00:55:48] **Ben:** Well, and also I, I believe on MySQL eight, it, it can do more, modifications online, meaning not, not having to do the copy the table and move all the rows with the new structure. and I, and I wonder if some of the things that you had to do were now possible to just do in the table metadata as opposed to actually copying rows. Now that you're on my C eight

[00:56:09] **Adam:** right? Yeah, I, I don't know the answer to that

[00:56:11] **Adam:** question, but

[00:56:12] **Tim:** was, That was deep, bro. That was deep goodest to you.

[00:56:16] **Adam:** Carol, was there

[00:56:17] **Carol:** I was, Yeah. Yeah. I just wanted to ask, if you had just reached out to the customer and said, Hey, can you re-import again? After you did the, the merge pr, would you still have to do any table work or would the process just create correctly since it creates a new table each time and drops the.

[00:56:35] **Adam:** I can't explain why, but. To the best of my, sleep addled brain,to the best of the ability of my sleep add brain. See, I can't even speak. I feel like there were some tables that were not these customer imported ones that ended up with the wrong coalition in encoding. I don't know if it was somehow caused by the inner joins that were going on or other things that we were doing to create tables on the fly.

[00:56:59] **Adam:** We do that sometimes. so, that would've covered like 90% easily

[00:57:03] **Adam:** if they had done that. But that was, that was not something that we wanted to ask them to do. Right? Like, if you can, if you can avoid going to your customer and saying, I screwed up, I need you to, to do this for me, then you should avoid it.

[00:57:13] **Adam:** Right? Like, we took the work on ourselves,

[00:57:16] **Carol:** I, I kinda see things differently. I'm like, Hey, we got everything right until this one point and your, your import this morning just needs to be reran again. Like,

[00:57:26] **Tim:** But we, but we've been doing it

[00:57:27] **Tim:** for years. Why

[00:57:28] **Carol:** Yeah. do you mind just rerunning this again? Because it lets them see you're human right, and that you're humble and that you admit when you have a failure and you're okay to say, Look, I screwed up.

[00:57:38] **Carol:** Like to me, I would much rather work with someone who's humble and can admit that they've done something wrong than someone who just fixes it all on the back end and makes it look pretty. So,

[00:57:47] **Adam:** we do, you know, there are times that we have no choice but to eat humble pie, but,

[00:57:51] **Carol:** you didn't want to, this

[00:57:52] **Adam:** we don't wanna, If you don't have to, then, then I would

[00:57:54] **Carol:** and, and plus you said it, it sounded like there was like 10% that you still were gonna have to do manually, or there were some, See if you were gonna have to do part, just do it all.

[00:58:03] **Adam:** Yeah. And, not only that, but I know for a fact that certain customers who have, like some of our larger customers, they have a job that, you know, prepares all the data to send to us. You know, they're, they're exporting from their Oracle databases or whatever, and creating CSV files and uploading those to S3. I, I believe I've heard a figure in the six to eight hour range for them to run their portion of the job

[00:58:24] **Adam:** to export their, Yeah. So I, I, I can't say for certain, but I feel like that's the, the number that jumps out at me. And

[00:58:31] **Adam:** so like that would be kind of a big ask.

[00:58:33] **Carol:** This isn't just taking the Excel sheet and clicking the button again and going, Hey, I already have it. Just click the button again. One more time please. Yeah.

[00:58:41] **Adam:** Right.

## [00:58:42] Online Migration

[00:58:42] **Carol:** Okay. So back to my original questions. how could you do this upgrade with the application online?

[00:58:49] **Carol:** And you said, you know, you

[00:58:50] **Carol:** put the question out there. Let's come back to it. I'm, I've been,

[00:58:54] **Adam:** You've been waiting very patiently. so I, I had mentioned Cunningham Law and I got two recommendations that I have not looked into yet, but that I most definitely want to look into. One was a, a product called Per Kona, I believe I'm pronouncing that correctly. P E R C O N A, which.

[00:59:10] **Adam:** again, have very little research into this. I've just kind of read a couple of tweets and, and like five minutes looking at their webpages. But, my understanding is that Perona will allow you to, they, they advertise it as basically like you can alter tables without table locks. And the way that they Yeah, the way that they do it is, I believe they still do all of the exact same work.

[00:59:31] **Adam:** Right. You know, they're copying the table, altering the copy, and then renaming it. But if I'm not mistaken, they like add triggers to the original table so that while they're doing the copy and modify any new data that comes in, or any changes that come in, also move over to their temporary copy until like everything is caught up for just a moment or, you know, long enough and then it'll do a hot swap, you know, a transactional, you know, rapid end transaction.

[00:59:54] **Adam:** Drop this table, rename this one.

[00:59:56] **Carol:** that's so sexy.

[00:59:58] **Adam:** Yeah. But it's also, you know, like the, the first thing that I saw on their website was like, don't try this unless you know you have good backups, , and.

[01:00:06] **Adam:** And, and,

[01:00:07] **Ben:** doesn't work with the foreign keys. If you try to run their, their, it's like, it's called like PT Online transform tools. That's what we use at work. And it it because it does the shadow table and it sets up triggers and it copies rows. If it sees that the table that you're working with has foreign keys, it, it refuses to run.

[01:00:26] **Ben:** Or at least

[01:00:27] **Adam:** Oh,

[01:00:27] **Carol:** you serious?

[01:00:28] **Carol:** Interesting.

[01:00:29] **Tim:** Mm.

[01:00:30] **Ben:** Cause it

[01:00:30] **Tim:** Yeah.

[01:00:31] **Tim:** we used per Kona for years as well. We, we've stopped using it in the past, like four or five years. But yeah, it was, it was pretty good when we had it. But

[01:00:37] **Adam:** okay.

[01:00:38] **Carol:** So you said there was one, What was the second

[01:00:41] **Adam:** Yeah. let me find it. It's in my Macon mentioned. Here we go. so this is a guy who,

[01:00:46] **Carol:** When you say Macedon, I always think of a dinosaur. I don't know why.

[01:00:49] **Adam:** mean, Macon was kind of

[01:00:51] **Adam:** yeah, it's like a

[01:00:51] **Ben:** Is that what a wooly

[01:00:52] **Adam:** uh,

[01:00:53] **Adam:** wooly mammoth. type of thing. Yeah.

[01:00:55] **Tim:** Yeah.

[01:00:55] **Carol:** Oh, okay.

[01:00:57] **Adam:** The guy who sent me this, his bio on Macon says he's a myse community manager. Oracle, I don't know,

[01:01:04] **Adam:** maybe it means he works at Oracle as a myse community manager. but what he sent me was, you should take a look at Myse. Shell dump and load utility.

[01:01:11] **Adam:** so again, this just sounds like

[01:01:14] **Ben:** It sounds like what

[01:01:15] **Adam:** really

[01:01:15] **Tim:** I, mean, shell dump sounds like you would be like doing it local, which I mean, when you're,

[01:01:19] **Adam:** Yeah, entirely

[01:01:21] **Carol:** that doesn't seem like application online still.

[01:01:24] **Tim:** Yeah. If you're doing it on I don't know. It's just, that's my gut feel on

[01:01:29] **Tim:** that. Shell dump

[01:01:30] **Adam:** I, I'll have to take a look at it. You know, I'll do some research, but maybe I can report back

[01:01:35] **Tim:** unless you can run, shell dump on aws.

[01:01:37] **Adam:** I don't know.

## [01:01:39] Compliance

[01:01:39] **Ben:** well as someone who, was deeply involved in a SOC compliance audit several weeks ago, what, what's your company's official data retention policy for these old aws, these old RDS clusters?

[01:01:52] **Carol:** Oh my goodness.

[01:01:54] **Adam:** so we haven't set the policy in stone yet. you know, the, we haven't begun our SOC two, audit period. we're still getting our initial ducks in a row and, and the, the prep work has kind of got pushed off to the back burner. So we're, we, you know, we've spent a certain amount of money to get the software to help us get our ducks in a row, and we've started getting our ducks lined up, but we're not ready to begin the audit process yet.

[01:02:17] **Adam:** The, the, I think they call it an audit period, whatever the, we're doing a type two. So type one is, okay, we looked at your stuff and, and you are audit your a attest that you obey your policies. Okay. Verified. You have a, you have a, so type one, so two type. Type two is, basically you on day one, you need to be able to pass a type one, and then you have to maintain that for some period of time.

[01:02:45] **Adam:** Like in theory, they could come in and audit you on any given day and you would pass, a, a, a type one check, right? You're obeying all of your policies. You have the necessary checks in place and, and things like that. but to the point of the retention policy, I've kind of figured out what different things retention policies are gonna be.

[01:03:03] **Adam:** And, you know, we're, it varies from, you know, like two weeks for certain types of logs all the way up to, you know, well, so for things that we will delete, I think the, the longest is like two years. And then there's certain types of data that we, reserve the right to retain indefinitely, un until such time that like the customer.

[01:03:22] **Adam:** our customer, right? Like a certain university ends their contract with us. Then we will expunge whatever data we don't need for our own, like tax reporting purposes, that sort of

[01:03:31] **Ben:** right. right.

[01:03:32] **Adam:** as long as we don't need it in order to continue doing business in a non fraudulent way, then we will happily delete it and stop paying to store it, you know, when we part ways, but,

[01:03:42] **Ben:** Very

[01:03:43] **Adam:** gosh.

[01:03:44] **Adam:** So that was a whole adventure that, that my last week was a, a true learning experience and a nightmare and, a pleasure. Like, like a, a blessing and a curse at the same time.

[01:03:56] **Tim:** I mean, it sounds like he came out of it pretty unscathed, so good job.

[01:03:59] **Adam:** Thank You Yeah. Live and learn

[01:04:02] **Carol:** Yep.

[01:04:02] **Ben:** And now poop emojis for everyone.

[01:04:06] **Adam:** Oh my god. And that's the funny thing. the, so we, of course we posted an announcement with a couple of emojis in it when everything was said and done to all the customers. And it's like, you know, the thing was successful, everything's going great. And for the longest time now, we've had the ability. So, you know how when you go on Facebook, you can like, react to somebody's post?

[01:04:24] **Adam:** We've had a very similar like emoji looking reactions, an image, and you can click, okay, I like the heart or the thumbs up, or the math face, whatever. and, almost all of our announcements get like zero interactions with the little, you know, nobody clicks the, the thumbs up or anything. Occasionally you'll get one or two, right?

[01:04:42] **Adam:** We've gotten so many more like thumbs up and hearts on, on this particular thing than anything else. Like you, if you combine all previous likes and thumbs up and everything, it's probably less than the amount of hearts that we got in like the first 12 hours

[01:04:57] **Tim:** So just checking it out, like does it really work? Click Oh, yeah, it does. Yeah.

[01:05:02] **Adam:** I mean all, it wasn't even using emoji before, like this particular feature where they can click and, and react to the announcement. It's just incrementing a counter and you know, it's like a little picture of a heart next to it. Right?

[01:05:13] **Carol:** It's like the, like on Facebook.

[01:05:14] **Adam:** right. So they've, they've been able to do that since long before we had support for them to enter emojis into text fields.

[01:05:20] **Adam:** but it, it's just like this is, you know, Steve said something like, this is how populism happens. Right. You know, just people don't want the things that actually make them better at their jobs or that make their life easier. They want,

[01:05:33] **Carol:** emojis.

[01:05:34] **Adam:** they want emojis. So,

[01:05:36] **Carol:** know.

[01:05:37] **Ben:** Yeah.

[01:05:39] **Tim:** Good story.

[01:05:41] **Adam:** So hopefully that was useful for somebody. again, the link to

[01:05:44] **Adam:** my blog post was, some of this information will be in the show notes. Was that Carol?

[01:05:48] **Carol:** I said it was for me, it was,

[01:05:50] **Adam:** Okay. I thought you were

[01:05:51] **Ben:** Yeah. This was, No, no, this was

[01:05:53] **Carol:** No, no, no, no. It was super useful for me. I appreciate it.

[01:05:56] **Adam:** Sure, glad to share. And again, I'm intentionally invoking Cunningham's Law. If you think that, there's something I could have done better, please hit me up. Hit hit up the podcast working Code pod on Twitter,

[01:06:06] **Tim:** Yeah, so obey my law.

[01:06:09] **Adam:** and, and, come yell at me. Tell me what I did wrong. That's very welcome.

## [01:06:12] Working Code Merch

[01:06:12] **Adam:** Okay, cool. So, we are gonna get ready and go record our after show. but before we do that, last week, I believe it was last week again, haven't had much sleep. I believe it was last week that, on our little after show tease here, I had mentioned that we are gonna tell our patrons about our newly available merch.

[01:06:29] **Adam:** And we did that and a bunch of them bought it. And they look awesome in their sweatshirts and their stickers and all kinds of

[01:06:34] **Adam:** great stuff. Um, we've been getting ,we've been getting pictures from all around the world of, of our stickers on stuff and, People wearing our shirts. Yeah, sweatshirts.

[01:06:44] **Adam:** So, yeah, so you can, it's public now.

[01:06:48] **Adam:** you can go find it, you can go to workingcode.dev/merch and you can buy all kinds of fun stuff. There's hats, T-shirts, I believe. There's dresses, throw pillows, blankets, laptop covers, phone covers. you can, you can even get a backpack with a cursing duck on it.

[01:07:04] **Tim:** Mm-hmm.

[01:07:05] **Adam:** yeah, so, check it out.

[01:07:07] **Adam:** Working code.dev/merch. as I mentioned, we're gonna go record our after show, I think tonight on the after show. Carol wants to talk about the new Black Panther movie,

[01:07:14] **Carol:** like Yeah, I do. I do.

[01:07:17] **Adam:** Carol always wants to talk about pop culture. Tim, you are apparently no longer fasting and we're gonna get into

[01:07:22] **Tim:** Yeah. Well, yeah. Talk about that.

[01:07:25] **Adam:** And, uh,

[01:07:26] **Carol:** I wanna ask. Yeah, yeah. I wanna ask Tim a question. So I've been hearing a lot about Venmo being added to payments and this whole like, idea of payment planning out things you purchase ahead of time. And since he's in the financial world with payments, I wanna know what he thinks about it.

[01:07:46] **Tim:** Yeah. I, It's funny, funny bringing it up. We just did a survey on that to our customers, so I can talk about

[01:07:50] **Carol:** I keep hearing about it like every morning on my like routine of waking up. So,

[01:07:56] **Adam:**

## [01:07:56] Patreon

[01:07:56] **Adam:** All right. Well then this episode of Working Code is brought to you by Lateral joining to your emoji filled indexes and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:08:11] **Adam:** Patrons cover our recording and editing costs, and we couldn't do this every week without them. So big thank you to all of those guys

[01:08:16] **Adam:** and gals.

[01:08:17] **Adam:**

[01:08:17] **Adam:** special thanks of course to our top patrons, Monte, Sean and Giancarlo. if you wanna help us out, you can go to patreon.com/WorkingCodePod.

## [01:08:25] Thanks For Listening

[01:08:25] **Adam:** let's see, homework this week.

[01:08:27] **Adam:** you know what, I'm gonna ask for a review. Again, If you're enjoying the show and you want other people to find out about us, you're obviously more than welcome to tell them. But a another great way that you can help people find us and people believe we're worth listening to, is to leave a rating on your local, Apple Podcast.

[01:08:42] **Adam:** And you can get to that spot, even if you're not an Apple Podcast's user. you can get there by going to workingcode.dev/review, and it will go to the appropriate place for your local market, even if you're outside of the usa. We really appreciate you leaving us a nice five star review. If I, last time I checked, we're still at all five stars in all of the places that I checked, so you guys are awesome.

[01:09:04] **Adam:** Thank you so much for that. Oh, topics and questions. If you've got 'em, you can send 'em to us at working Good Pod on Twitter or Instagram. As long as Twitter stays online, I don't know, Musk might kill it before this even

[01:09:14] **Tim:** Hey. Yeah, don't, don't, don't try to do the two factor authentication with your, with your

[01:09:19] **Adam:** Yeah, don't sign out cuz you might not be able to sign back in

[01:09:22] **Adam:** anyway,

[01:09:23] **Tim:** for sure.

[01:09:24] **Tim:** Elon's killing it.

[01:09:25] **Adam:** if Twitter goes down, you can always find us on our Discord at workingcode.dev/discord. You can email us at WorkingCodePod@gmail.com, send us a voice memo to that same url and we'll play it on a show that's gonna do it for us this week.

[01:09:37] **Adam:** We'll catch you next week. And until then,

[01:09:39] **Tim:** Remember, your heart matters no matter how much your databases have Sharded.

[01:09:45] **Adam:** Oh my God.
