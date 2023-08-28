---
title: "054: We're So Quacked!"
description: "At 3:30 AM the day before Thanksgiving, Ben received an emergency page about a failing API end-point. Rushing to his desk, groggy-eyed and in various states of undress, he jumped into the #incident channel on Slack to see what was happening. What unfolded over the next 30-hours was the manifestation of Ben's worst nightmare."
date: 2021-12-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/054-were-so-quacked/id1544142288?i=1000545765948"></iframe>

At 3:30 AM the day before Thanksgiving, Ben received an emergency page about a failing API end-point. Rushing to his desk, groggy-eyed and in various states of undress, he jumped into the `#incident` channel on Slack to see what was happening. What unfolded over the next 30-hours was the manifestation of Ben's worst nightmare. The moment he had been dreading for the last 4-years had finally come to pass: **two of his database columns had run out of storage space**! Using feature flags, emergency hot-fixes, shadow tables, and a database migration being performed over a transient and unstable terminal session, he and his team somehow made it through to the other side just in time to enjoy Thanksgiving turkey and pumpkin pie!

> "Hug your data engineers - they are amazing people!" &mdash; **Ben Nadel**

## Notes &amp; Links

-  [Liquibase](https://www.liquibase.org/)
-  [Percona Tooklit](https://www.percona.com/software/database-tools/percona-toolkit)
-  [MySQL's Information Schema](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)
-  [Datadog](https://www.datadoghq.com/)
-  [CFSearching: CFQueryparam Matrix for MySQL 5](http://cfsearching.blogspot.com/2010/01/cfqueryparam-matrix-for-mysql-5.html)
-  [Ben Nadel: CAUTION: Silent Value Truncation In CFQueryParam Tag In Lucee CFML 5.3.7.47](https://www.bennadel.com/blog/4157-caution-silent-value-truncation-in-cfqueryparam-tag-in-lucee-cfml-5-3-7-47.htm)
-  [Ben Nadel: Recording Datadog / StatsD Gauges For Database Key Utilization](https://www.bennadel.com/blog/4166-recording-datadog-statsd-gauges-for-database-key-utilization-in-lucee-cfml-5-3-7-47.htm)
-  [Ben Nadel: Inspecting Primary And Secondary Index Key Utilization For MySQL](https://www.bennadel.com/blog/4165-inspecting-primary-and-secondary-index-key-utilization-for-mysql-5-7-32-in-lucee-cfml-5-3-7-47.htm)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633 (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/054-were-so-quacked.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I turned that on and suddenly my logs just exploding with 500 errors. And, it was very confusing at first what I was seeing. So I look at the error message and I dig down to the code and I'm seeing it where it's, that error is being thrown in to look like maybe something malicious was happening. Like it's a guard statement that a user should really never run into.

[00:00:21] **Ben:** It should just be something that, that only if you were trying to break the system, you'd get. So I was still very confused and I'm looking up a record in the database and I'm realizing that the record in the database doesn't actually match what's in the error message. and I'm looking at it and I had this moment of realization, and I'm not one who curses, right?

[00:00:40] **Ben:** I don't, I never really curse on this call. I'm not a very,salty individual, but I'm just like, Oh, Oh, We're So, This is so I was like, I couldn't, it was like, all of my worst fears had come, had just come to fruition.

[00:00:54] **Ben:** All of a sudden,

## [00:01:14] Intro

[00:01:14] **Adam:** okay, here we go. It is show number 54. And on today's show, we're going to talk about, I don't know, those times that things just go like very, very wrong. Maybe sometimes you saw it coming. Sometimes you didn't just stuff goes wrong and you got to deal with it. But as usual, we're going to start with our triumphs and fails.

[00:01:29] **Adam:** We've got the whole crew here. We're going to do a normal episode. So, why don't we just start with you, Tim? What do you got going on?

## [00:01:35] Tim's Triumph

[00:01:35] **Tim:** Hey, I'm back

[00:01:36] **Ben:** Welcome back

[00:01:37] **Ben:** to him.

[00:01:38] **Tim:** Although I did do the interview with, Adam layman last week, but yeah, as far as where the whole group is going to be back, a couple wins. So, and I don't know if there's a HIPAA violation, but I told you guys that, the reason I was out, I had a little, I had, I said I had a routine procedure.

[00:01:54] **Tim:** Really? Wasn't true. I got some good news yesterday, so they remove a tumor from me and

[00:02:02] **Adam:** good news is

[00:02:03] **Tim:** it's not cancer.

[00:02:04] **Carol:** Yay.

[00:02:06] **Ben:** That's

[00:02:07] **Adam:** Glad to

[00:02:07] **Tim:** I'm quite relieved. Two weeks just kind of sitting on eggshell, just wondering if my whole life is about to change and go into. Yeah. But no,it's all clear. It's all good. So

[00:02:16] **Tim:** quite

[00:02:17] **Carol:** so stressful.

[00:02:18] **Ben:** Yeah.

[00:02:19] **Tim:** For sure. So folks, when the doctor tells you to get your a checkup and your particularly your colonoscopy go

[00:02:26] **Carol:** Do it,

[00:02:27] **Tim:** do it, it is a pain in the butt literally, but, uh, don't avoid it.

[00:02:31] **Carol:** Hey, you get to lose a few pounds.

[00:02:33] **Tim:** Yeah. Doctor said,doctor said six months from now that could have been a real big issue. So,

[00:02:38] **Carol:** Oh, dang

[00:02:40] **Tim:** but anyway,

[00:02:40] **Adam:** It's too bad that we're sticking to PG. Cause I got some jokes I'd love to crack right now.

[00:02:45] **Carol:** after show, please.

[00:02:46] **Tim:** for sure. But as far as professional goes, so we have been, we've been postponing upgrading. We have an old, and I hate talking about ColdFusion so much in this podcast, but you know, it is a part of all of our lives. At some point I'm an old ColdFusion, Adobe ColdFusion 10 machine that is no longer supported, so we have to get it upgraded.

[00:03:05] **Tim:** So we upgraded it to 2021 and I just been, I mean, I put it off all year and it's like getting the end of the year. We got to do this before the end of the calendar year. We did it. It wasn't as bad as I thought, so that's the win, but the pain of the butt is so they changed Adobe changes thing where you could do a date format.

[00:03:25] **Tim:** And if you wanted like. month, dash day, dash year, you do capital M capital M dash capital D capital D dash Y Y Y. Now, for those of you who don't do cold vision go fusion usually cares nothing about case sensitivity. You do upper or lower. Well, they did a change and they didn't tell anyone. It was not in any of the 500 pages of the doc release between 2018.

[00:03:48] **Tim:** And this version that if you do a uppercase D D for day, that will actually give you the day of the year. So like

[00:03:59] **Adam:** 350,

[00:04:01] **Tim:** December seven to be 341 days. So you would have 12 dash 3 41 dash 2021, which obviously is not the date you

[00:04:10] **Tim:** want.

[00:04:11] **Adam:** that's how they do it in Europe, right

[00:04:13] **Adam:** in Canada.

[00:04:14] **Tim:** I mean, I get why they do it.

[00:04:15] **Tim:** It's sort of, it's a Java things the way Java is, but it's like, yeah. I mean, fortunately I, I dealt with the libraries where you have to do that. And as soon as I saw what it was outputting like, oh, this must be, I didn't even find the bug until later. So it changed it everywhere and it wasn't a huge issue, but just knowing that there's this breaking change that they didn't announce.

[00:04:36] **Tim:** And I had to dig through some people's blogs to find out what was going on with it after the fact. But yeah. But anyway, other than that, it went okay.

[00:04:45] **Adam:** Was this an intentional change or was this a bug that slipped out?

[00:04:49] **Tim:** I think it's a bug that slipped out from them because yeah, like I said, it was not in any of their documentation about the changes. So anyway, that's me. How about you, Carol?

## [00:04:58] Carol's Triumph

[00:04:58] **Carol:** Oh, I'm going to go with the triumph. So, I guess it was two episodes ago maybe. Cause I was out the last episode. I talked about my triumph. Them was, I was super excited that we had hired a new executive VP of engineering and that it was a female. Well, First meet and greet with her. And like we did it as the whole department.

[00:05:18] **Carol:** So everybody went through and told what they had for breakfast, like every day. So she could get to know us better. And two things about ourselves, just random facts, whatever. And I had said, yeah, I was like, Anna, do a tech podcast with three of my buddies, you know?And she was like, oh, I'm so excited. Send me the link.

[00:05:35] **Carol:** I'm going to start listening to it. So not only is she like really cool with wanting to get to know more about us and wanting to be in videos with us. So she gets faces with names because we're still all remote. She also really is intrigued by a lot of what we do. So I was just super impressed with not just that we have a female executive vice president of engineering that she's also really awesome to work with so far.

[00:05:59] **Carol:** So I'm just, I'm really excited about this. If you can't tell it makes me super happy.

[00:06:03] **Ben:** Cool.

[00:06:04] **Carol:** Yeah.

[00:06:05] **Tim:** Good deal. He has great to see more women in tech

[00:06:08] **Carol:** I agree. I agree.

[00:06:10] **Adam:** Especially in leadership roles.

[00:06:11] **Carol:** Exactly. Exactly. Yep. You need some diversity to make decisions. what about you, Adam?

## [00:06:16] Adam's Triumph

[00:06:16] **Adam:** Oh gosh. I have so much to be thankful for and happy about right now. It's hard to pick. I guess I'll start with I'm in the spirit, right. we're heading up to Christmas time here in the U S or I guess it's Christmas around the world, but.

[00:06:27] **Carol:** Oh, happy holiday

[00:06:29] **Carol:** is,

[00:06:29] **Adam:** anyway, I'm in the spirit. I just, I'm just, I'm in that place where it would take a lot to get me down. that's not to say that nothing's getting me down. Like I've had a couple of rough days here and there, but,my average is way up right now and, things are just going well.

[00:06:43] **Adam:** I've had, like a really good week at work, but we're pushing hard on our multi-tenant. what's the word? Not objective, like initiative initiative. And, and making a lot of progress. Things are, it's funny. I started this, I made like a roadmap and get hub issues and, I put a whole bunch of check boxes in there.

[00:06:59] **Adam:** like you can check them off in the description or whatever, and it'll show you like, okay, this is the percentage complete. And it's like, every time I check one off, I go, I realize I have to go on, I add two or three more. So the percentage, I keep checking things off, but the percentage keeps going

[00:07:15] **Carol:** Yeah.

[00:07:17] **Adam:** So that's whatever. I mean, we're getting stuff done. We're pushing hard, making a lot of progress, whether or not that percentage is going in the right direction. So I'm just happy. I've been wanting to work on this for years and we're finally are, and it's going forward. So I will take it.

[00:07:33] **Carol:** So we like to do this thing where we have this big project. Right. And we're trying to roll it out. And in order to make it feel like you're making progress on it, we start putting phases in there. So instead of putting everything into the main release, we're like, all right, here's phase one, let's get through phase one and maybe we need to add a few things to it, but what can, what of this can roll into a phase two so that you feel like you're getting to completion on something and you're not just continuously adding more and more to your checklist.

[00:08:01] **Carol:** So I love,I love phases when I'm doing my checklist. I'm like, okay, I'm completing something. Yes.

[00:08:08] **Adam:** yeah. and, this roadmap that I made is broken up into something like four or five phases and almost every single individual step of that is releasable. So each ofeach of those check boxes is something we can release and do release.

[00:08:20] **Carol:** Sweet. That's awesome. That's awesome. Hey,

[00:08:23] **Adam:** yeah, like I said, I'm in the spirit. I'm happy all as well.

[00:08:26] **Adam:** So, how about you, Ben?

## [00:08:27] Ben's Fail / Worst Nightmare

[00:08:27] **Ben:** Ooh. let's fail your time

[00:08:30] **Tim:** Oh

[00:08:30] **Tim:** no.

[00:08:31] **Ben:** and we're going to, we're going to roll this failure right into the show topic here. the day before Thanksgiving at 3 38.

[00:08:39] **Adam:** Ooh.

[00:08:39] **Ben:** my phone started going crazy. It was this loud screeching. I thought it was like an Amber alert. I don't know if anyone gets Amber alerts on their phone sometimes where it's like a flash flood warning.

[00:08:50] **Ben:** Like it was that kind of panic. And,

[00:08:52] **Ben:** I pick up the phone and I'm looking at it, through groggy eyes here. And, it starts to, I said, I'm getting a call also. So I answered the call and it's PagerDuty. I am on a team that deals with a legacy platform. I've been paged like three times in my entire life.

[00:09:06] **Carol:** Oh

[00:09:07] **Ben:** so immediately I'm like, this can't be good. I run to my desk, my desk, uh, I am in various stages of undress. Uh,so I jumped into our incident channel on slack and, it turns out one of the guys on one of the other teams had paged me explicitly. So I touched base With, him. I said, Hey, what's going on? He says, Hey, there's some API end points that are just returning 500 server errors on every single road. So I look at the logs and I don't see anything in the logs at all, which is weird. and I look in the metrics and I don't really see anything interesting in the metrics. Again, it's a very legacy part of the application, so it was not instrumented very well. so I jumped into a feature flag that allows me to turn on special, lower level, basically tracing and debugging level logs, which we don't normally admit in production.

[00:09:57] **Ben:** I turned that on and suddenly my logs just exploding with 500 errors. And, it was very confusing at first what I was seeing. So I look at the error message and I dig down to the code and I'm seeing it where it's, that error is being thrown in to look like maybe something malicious was happening. Like it's a guard statement that a user should really never run into.

[00:10:18] **Ben:** It should just be something that, that only if you were trying to break the system, you'd get. So I was still very confused and I'm looking up a record in the database and I'm realizing that the record in the database doesn't actually match what's in the error message. and I'm looking at it and I had this moment of realization, and I'm not one who curses, right?

[00:10:37] **Ben:** I don't, I never really curse on this call. I'm not a very,salty individual, but I'm just like, Oh, Oh, We're So, This is so I was like, I couldn't, it was like, all of my worst fears had come, had just come to fruition.

[00:10:52] **Ben:** All of a sudden,

[00:10:54] **Tim:** Tourette

[00:10:54] **Ben:** you know, it was, it was

[00:10:56] **Ben:** crazy. Oh my God, it was,

## [00:10:59] The Problem

[00:10:59] **Ben:** it was awful. The moment I realized exactly what was happening,

[00:11:02] **Tim:** what

[00:11:03] **Tim:** was it?

[00:11:04] **Ben:** So, which was that, all of our primary keys in our database are supposed to be unsigned integers. So we use, MySQL. So this may not be relevant for all different databases, but in MySQL numeric columns, whether they're tiny ants or medium ends or begins or ends, can be defined as signed or unsigned.

[00:11:25] **Ben:** And essentially if it's signed, it means it can go both negative and positive. So, I don't know the exact numbers off hand, but a regular column can handle something like negative 2.1 billion up to positive, 2.1 billion. And if you're going to create an unsigned and essentially you shift all of that into the positive space.

[00:11:46] **Ben:** So instead of going from negative 2.1 to positive 2.1, you go from zero to 4.2 billion. So you essentially on an auto incrementing column, it? doubles the amount of integers you can store. so most of

[00:11:59] **Ben:** our

[00:11:59] **Tim:** one table

[00:12:00] **Ben:** Yeah, yeah, yeah.

[00:12:01] **Tim:** okay.

[00:12:01] **Adam:** Okay. For that one column

[00:12:03] **Ben:** Right. For that one column. So our primary keys are typically unsigned INTS.

[00:12:08] **Ben:** And if they're not, it's a mistake. Now we have secondary columns and other tables that reference primary keys in, in another table? like a foreign key, but we don't actually have foreign key constraints configured, and two different columns, which are referencing this one primary key were defined as signed in.

[00:12:28] **Ben:** So they can only go up to 2.1 billion. Whereas the primary key they were referencing can go up to 4.2 billion.

[00:12:33] **Tim:** Was that a mistake?

[00:12:34] **Ben:** that was a mistake? And at about 1:00 AM that morning. So about two and a half hours before I was paged the primary key in the one table surpassed what could be stored in assigned in and suddenly all

[00:12:47] **Tim:** It's breaking the constraint.

[00:12:48] **Ben:** Yeah. All rights to that other table that had these two secondary columns referencing that primary key started repeating. To be written, and it basically broke a very, high volume area of the application. It didn't take the application completely offline. Everything that didn't touch that one particular table was completely fine.

[00:13:06] **Ben:** It's just that table is really critical in one very high volume workflow.

[00:13:11] **Carol:** But wait, I thought you said that it really shouldn't be getting access. Cause you thought this was just an, a guard statement.

[00:13:17] **Ben:** so it got really weird.

[00:13:18] **Carol:** Okay. There's more.

[00:13:20] **Ben:** well, we, as we're digging into what was going wrong, It turns out that not only were there. Foreign key constraints, not having the appropriate data type they were signed in when they should have been unsigned. Well, our prepared statements, so ColdFusion, one of the core tenants of the ColdFusion language dating back to like 15 years ago was SQL.

[00:13:44] **Ben:** Injection is terrible, and we're essentially gonna design a language that makes SQL injection and possible. So with their CF query tags and their CF queer pram tags, they made it just very, very trivial to prevent SQL injection. And you do with these parameter binding inside our prepared statements.

[00:13:59] **Ben:** And when you create a parameter within a prepared statement, you tell it what type of data you're writing into. So you're saying this is a VAR car field, or this is An inter a big end or a tiny end or a bit column anyway. unbeknownst to me, the CF SQL integer parameter. Can only handle signed integers because it's being validated as assigned Java int under the

[00:14:27] **Ben:** hood. So even though we have primary keys that are using unsigned ins in the database, the parameter binding for the queries that we're using to talk to that database can handle the unsigned in. So going back to Carol's question, the guard statement what happened was in Lucy CFML, which is what we were using. It's doesn't throw an error. If you, if you use something that goes above a Java 32 bit signed in, it'll just quietly truncate it to be whatever the max into jury is and just pass that through to the database.

[00:15:05] **Carol:** Oh, that's terrible.

[00:15:06] **Ben:** oh,

[00:15:06] **Ben:** it's so terrible.

[00:15:08] **Carol:** That's terrible. Oh my gosh.

[00:15:10] **Ben:** So that's why we were getting these really bizarre guard statements, because someone was saying like, Hey, give me this record with my ID.

[00:15:16] **Ben:** And my ID is really high and the wrong ID was being passed through to the database. And that's where, or, as being passed down to the database and we were getting the wrong record back, and that's why I was sending like, Hey, you're asking for a record that you shouldn't be having access to. Now.

[00:15:32] **Ben:** Luckily, I mean, on the face of it. that's like terrible security incident waiting to happen because you're essentially saying, Hey, I'm authorized to request this ID, but you're getting the wrong records back from the database. Like I'm telling you when I realized this I'm like, oh All this is so

[00:15:48] **Carol:** thinking the same words in my head right now.

[00:15:50] **Ben:** oh my God. It was so ridiculous.

[00:15:53] **Ben:** I mean,

[00:15:53] **Tim:** But fairly minor quacks in my head. That's odd.

[00:15:57] **Adam:** Um,

[00:15:59] **Tim:** going on there.

[00:15:59] **Ben:** so just by grace and coincidence. We happened to then have that guard statement that was doing one additional check to see, like, is this record something, it was a contextual check was basically saying this record that You. asked for, is it part of, is it owned by the correct parent object? And it wasn't because the wrong data was coming back and th and the whole thing was blowing up and saying, Hey, you're doing something not supposed to, like, had we not had that, that we would have been again AFT we would have been totally after.

[00:16:31] **Carol:** So, I mean, yeah, so it's, it's kind of like, Hey, I'm going to go grab this photo. And if I have the photo ID, I'm good to get it. But you weren't checking to make sure that the photo was actually owned by that user. Right. Is that a

[00:16:44] **Ben:** Right. Cause we had already validated parts of the data before we went to the database.

[00:16:48] **Carol:** But then you're good. But your guard statement is what did that second check, right? It was like, well, you got the photo, but do you actually own that photo? And, yeah. Okay. Yeah.

[00:16:56] **Ben:** So, in the heat of the moment, it seemed very, very, very terrible.

[00:17:00] **Ben:** Uh,

[00:17:00] **Ben:** and you know,a very important part of the system was down. So it was very terrible, but as sort of the moment cooled, and we had some more time to think about what's going on from a security standpoint, it was less of a dumpster fire than it could have been because the values are being truncated, but they were always being truncated to the same ID, which was the max signed in.

[00:17:21] **Ben:** So could we have leaked data? Yes. But the blast radius. Yeah. Yeah.

[00:17:27] **Ben:** The blast radius of the problem would have been.

[00:17:29] **Carol:** Everybody got the same pitcher.

[00:17:32] **Ben:** Yeah.

[00:17:32] **Ben:** It's like things broke really bad, but they broke in a, in an order that actually saved us from having a lot worse of a situation.

[00:17:42] **Tim:** and it wasn't a bad actor that was taking advantage

[00:17:44] **Tim:** of it. This was just the system itself because of constraints in the database.

[00:17:50] **Carol:** poor

[00:17:50] **Carol:** design of the language you're writing, not even that you wrote something obviously bad, like the core issue is the language that you're writing and had a problem that yeah, you said something wrong in your database, but that's a big issue with the data type with the parameter, not matching and not telling you what that should throw an error.

[00:18:12] **Carol:** It should say problem too

[00:18:13] **Carol:** big. Can't go into.

[00:18:15] **Ben:** Adobe is credit. Adobe ColdFusion will throw an error. if you use a binding outside of its potential, outside of its storable range, Lucy and I filed this as a, well, I actually found a ticket in their JIRA for this same issue. And I basically went and said like, yo, this is a super critical problem.

[00:18:33] **Ben:** You guys should fix this and this tickets from sometime in 2020.

[00:18:37] **Ben:** but what is not documented anywhere either on the Lucy side of the Adobe ColdFusion site is the fact that CFC goal integer doesn't work with unsigned encounter. Which that's kind of terrifying. Like that should be pretty documented with like big blinking

[00:18:53] **Adam:** I was going to ask, is there, what should you use instead?

[00:18:57] **Ben:** Big end. Well, Okay.

[00:18:59] **Ben:** So, I w once, once we started, once we realized what was happening, we did a bunch of Googling. We found this, CF searching site from like 2010. I think this blog post is

[00:19:10] **Tim:** We're all the rich stuff is from way back.

[00:19:13] **Carol:** You know,it's right. If it's pre 22,

[00:19:16] **Ben:** where someone, the CF searching site, I think has been an anonymous site forever. I don't think that person ever identified themselves in public. but so on this site, the author essentially, talked about all the different data types and What they can use and what they can't use and why you should use what we ended up just using begin in the heat of the moment.

[00:19:33] **Ben:** Like we had to fix it,on the CF searching site, they talked about using a numeric type with scale. And actually, James Moberg on Twitter was saying that he uses something similar numeric with a scale of zero

[00:19:46] **Carol:** what scale is zero? Do.

[00:19:47] **Ben:** I believe that means how many decimals. So the numeric, I don't know.

[00:19:51] **Ben:** I don't know what numeric means in this context, but I know scale means decimals.

[00:19:56] **Adam:** So scale is another argument or attribute on the CF

[00:20:02] **Ben:** I think it's both part of the table schema. And then also part of the query parameter binding.

[00:20:08] **Carol:** I thought that was called precision.

[00:20:10] **Adam:** Yeah, that's what I would,

[00:20:11] **Ben:** I think the precision on the table is defined by the scale on the query perimeter. I think it's, I think it might be the same thing,

[00:20:18] **Carol:** I'm getting it all across, up in my head. Okay. Scale zero. Keep going.

[00:20:23] **Adam:** it will be in the show notes, Carol.

[00:20:25] **Carol:** So you see. Sweet. Good. I'll go read about it.

## [00:20:27] The Fix

[00:20:27] **Ben:** so at this point it's like four 30 in the room. And, me and Eric, this other guy on the call, he was the one who paged me. We're trying to figure out what to do.

[00:20:35] **Carol:** Oh, wait question. Have you put on clothes yet?

[00:20:39] **Tim:** Inquiring minds want to know.

[00:20:41] **Carol:** We're just, we're all. We're all curious. If you

[00:20:43] **Carol:** have

[00:20:43] **Ben:** was zoom video off. I was still in panic mode. no clothing. So, the easiest thing to do would just be to migrate the table and change the column from assigned into an unsigned int so that the primary key in the one table would now match the secondary keys in the other two tables.

[00:21:03] **Ben:** We had two different tables that had reached this limit at the same time. and at work we use, this thing called liquid base. it's like, I don't exactly understand what it is. We use something called Exodus, Exodus uses Liquibase and then liquid base, I think uses Percona toolkit. It's like various levels here of

[00:21:20] **Carol:** So many words. Yeah.

[00:21:22] **Adam:** is there for database.

[00:21:23] **Ben:** yeah, yeah, yeah. So essentially what you do is you define your database migrations as these, like schema change definitions. Do you like it's like DML database markup. I don't know. I never know what they stand for. where essentially you're saying change this table with this column and give it this type.

[00:21:41] **Ben:** and the way that, you can't just change arbitrary schema on the fly, because there's all this data that's been written to disk and the database Kansas arbitrarily changed the type of data type that you're using. So what Liquibase does and via Percona toolkit under the hood is it creates a shadow table with the new schema and then incrementally copies rows.

[00:22:03] **Ben:** So essentially you're saying, Hey, I have table a and I need to change a column type. So it creates table B in the background with the new column. It sets up triggers on table a, so that inserts, updates, and deletes then insert, update and delete on table B. And then while those triggers are in place and essentially walks over table a and starts copying rows and to table B.

[00:22:27] **Ben:** So it does essentially a full table scan on table, a copies, all of the data into table B and then the triggers make up any difference that the traversal doesn't hit. but you know, we just reached the max of the signed in, which is 2.1 billion records, which it doesn't just copy in a second now, as, as clever as the shadow table approach is it still uses a lot of resources, especially because it's copying like 40,000 rows a second or something like it's really trying to churn through it.

[00:22:57] **Ben:** So Percona toolkit has a number of things that it puts in place to help prevent from taking the data. Down, essentially from having to do this work. So it'll check to see how many threads are running. And if it sees the number of running threads, start to climb, it'll short circuit out of its process.

[00:23:14] **Ben:** It will also look at replication lags. So we have primary databases and then we have some read replicas, and it'll look to see if there's been replication, lags, starting to grow. And if the replication lag starts to increase, it'll short circuit its process again, because it doesn't want to do more harm to the database. So we're sitting there and we deploy this migration behind the scenes as me and just this other guy. And, watching a tick up, it's like a copy of 5 million rows, 10 million rows. And all of a sudden the sh the shadow table would disappear. And then it would reappear again at zero. And, it's copied a hundred rows thousand rows, and it goes through this couple of times and the deployment finally fails.

[00:23:48] **Ben:** And now we're trying to dig through the logs to figure out why the deployment failed and it reached these max threads. Like the database.

[00:23:55] **Ben:** looked like it was working too hard. So it's short circuit. We had to set up. I think you could have up to a hundred threads running at a time. So we revert the deployment.

[00:24:04] **Ben:** We try to redeploy it again, see if let's work again, continues to fail. And now it's like six o'clock in the morning. So we page the data services team. Cause we don't know what to do at this point. And the data services team just bad confluence of issues. The data service guy who was on call had somehow, I don't know, like put his code as a phone into do not disturb mode, even for critical apps.

[00:24:30] **Carol:** Oh,

[00:24:30] **Carol:** no.

[00:24:31] **Ben:** So we're sitting there for like two more hours before the data services guy like happens to wake up and check his phone and he's three times zones ahead of us. So

[00:24:42] **Ben:** it

[00:24:42] **Ben:** was really early for him.

[00:24:43] **Carol:** Yeah,

[00:24:44] **Ben:** So he happened to just wake up and check his phone. And so he jumps online. Yes, we're trying to figure out what to do. and, we're looking through the logs and we see that It's because of the threads. So he has to spin up, what do you call it? A bastion machine? I don't exactly understand what a bastion machine is. It's like he has to spin up a, machine in the

[00:25:04] **Tim:** a, it's a machine who doesn't know who his daddy is.

[00:25:07] **Carol:** that's exactly what I was thinking, Tim. Yep. Yep.

[00:25:11] **Tim:** Oh, wait, bastion, sorry, sorry, sorry. Sorry.

[00:25:14] **Ben:** So he has to spin up his, machine in production so that he can run the migration manually from within inside whatever private network the database lives inside of. So he sets the, the short-circuiting thresholds. We had it at a hundred threads. He said, it's something like 10,000 threads. And he starts running it and it's cruising along. And, we realized it's going to take a long time it's to take like 22 hours to run this migration. And it keeps giving us the. These things. Right. and it's the day before Thanksgiving

[00:25:45] **Tim:** Oh, my God.

[00:25:47] **Ben:** terrible. Oh my God.

[00:25:50] **Tim:** Can you like shut down that portion of your app and just say not available while it's like doing

[00:25:54] **Ben:** that's what we did. So, so well, this migration is running. We put in a feature flag. cause so we have, we

[00:26:00] **Ben:** also have different,

[00:26:00] **Tim:** a feature

[00:26:02] **Ben:** we have different tiers of applications. So this was in our multi-tenant system, which means it has a bunch of different tenants. we also have a bunch of single tenant environments, which are completely isolated environments for a specific user or aa specific subset of related users.

[00:26:18] **Ben:** and because the single tenants have totally different databases and they have much lower volume, they're not affected by this issue. it's going to be forever before they hit these kinds of caps on their records. So we had to create this feature flag.

[00:26:30] **Ben:** that would allow us to shut up. This particular feature, but just inside of the multi-tenant environment so that the single-tenant environments could continue to function properly.

[00:26:40] **Ben:** So as the migration is running, we're doing this, we're dealing with support. and then we realize again, but it's going to take quite a while. And the guy who kicked off the migration, he did it through his,like a T mux terminal connection or something. I don't really

[00:26:55] **Carol:** Yeah. So it has to stay over.

[00:26:57] **Ben:** yeah. So it has to

[00:26:58] **Ben:** stay open.

[00:26:59] **Ben:** So like, if he lost his VPN connection for a second, or like, if anything, the whole migration would be, it would essentially terminate the entire execution of the bastion machine.

[00:27:10] **Carol:** I'm sorry. I'm so sorry.

[00:27:14] **Ben:** And we didn't really, he didn't, he didn't understand the implications of that until we were already like four hours into the migration and it was just, oh my God, it was. It was so terrible. And like, I kept trying to message, like various directors of engineering and and like, but it's the day before Thanksgiving.

[00:27:34] **Ben:** So like half the people aren't even in the office anymore and they're all in do not disturb mode. Oh, my God. It was so terrible. It was so terrible.

## [00:27:42] Ben Worrying About The Problem Earlier

[00:27:42] **Ben:** I mean, thankfully, the whole incident was about 27 hours, 28 hours before the migration finally finished. And we were able to turn the feature back on with the feature flag, but it was just, it was my worst nightmare. And I say, I, and I say, it's my worst nightmare is because it was literally something that I had been fearing

[00:28:01] **Ben:** for.

[00:28:02] **Ben:** I'd say the better part of four years. And I know how long it was, because I actually could look, I searched for slack for the phrase, like in space or run out of in space, something like that. And I could find messages back to like 2016. We're always talking to people like, Hey, are we ever going to run out of its space on these columns?

[00:28:20] **Ben:** Like how,how are we going to know about this? And I have, I had a, I know I had talked to the director of platform like two years ago about this. And now he cause he used to be the manager of our teams. And then he became the director of platform. And I kept trying to pitch him on this idea, like, Hey, we have a bunch of product engineers.

[00:28:40] **Ben:** They can do database stuff, but they're not database engineers. They're not going to know about things like, Hey, am I necessarily using the right type of data? am I using a long text when I should be using a VAR card, 2000 or something? Right.

[00:28:54] **Ben:** Depending on how the data is actually stored on disc, I said, Hey, we need to have our data services team become essentially consultants with the product.

[00:29:03] **Ben:** And help them manage and monitor their databases. And I very specifically was like, and they should help the product teams know when they're going to run out of storage space on their tables. And I have a screenshot from, July of 2020, where I'm saying, this is exactly what I want this team to do. And bullet point number two is make sure that these tables, that people are designing, don't run out of space and how do they make sure the doc run a space and how do we know ahead of time so

[00:29:29] **Ben:** that people have time to react if we think it's going to happen

[00:29:33] **Adam:** Yeah. Keep those receipts.

[00:29:34] **Ben:** Yeah. Yeah. And now, 16 months later, 18 months later, my, the thing that I've been worrying about for the past four or five years finally came true, at 1:00 AM the day before Thanksgiving.

[00:29:45] **Tim:** At least you can gloat that you were

[00:29:47] **Carol:** yeah, I'm, I'm hearing a big giant. I told you, so

[00:29:53] **Carol:** told you

[00:29:54] **Ben:** man. So,

[00:29:55] **Carol:** now I have a question. So how long has this table been writing data?

[00:29:58] **Ben:** years.

[00:29:59] **Carol:** Eight years. So you just hit 4 million records,

[00:30:02] **Ben:** to 2.1.

[00:30:04] **Carol:** oh, wait. So what's the four, that's the unsigned.

[00:30:07] **Ben:** Yes. sign.

[00:30:08] **Carol:** So what are you going to do in eight years?

[00:30:11] **Ben:** Well, I'm on the legacy platform team. And by, on the team, it's me, I'm the legacy platform team. So I think, the legacy platform will not be around in eight years?

[00:30:24] **Carol:** So in the eight years when this crashes you're going to be like, man, I should've changed that.

[00:30:29] **Carol:** Sorry guys. So, sorry. Sorry

[00:30:31] **Carol:** guys.

[00:30:32] **Adam:** business doesn't increase linearly. It's going to crash again in four years or

[00:30:36] **Tim:** Exactly.

[00:30:37] **Ben:** Well, that's a great point because it's not like we've been steadily writing records to this table. This table is now a cornerstone of our sinking process with design files. And that had really picked up in the last couple of years. so it definitely was sort of a hockey stick growth for this particular table.

[00:30:57] **Ben:** where it just so the, in the weeks, since this incident, basically it's been a bunch of QAI quality assurance item tickets. So when we have incidents at work, we have to write up a, an RCA, a root cause analysis. And then as part of the investigation, we have to generate QAI quality assurance issues that help us make sure that whatever just happened doesn't happen again.

## [00:31:22] Monitoring As A Precaution

[00:31:22] **Ben:** So, one of the things we did was actually something that Adam was just sharing with us just before the call, which is I had to figure out a way to monitor In space or the key space that we're using in the table to say, Hey, all of these columns have our various data types. And those various data types allow for a certain amount of values to be stored in them.

[00:31:42] **Ben:** And today you're at value X and you can go up to value Y and what percentage of that is, is being utilized. so I had to figure out a way to do that with MySQL there's something called the information schema, which is essentially a database that sits next to your database that has a bunch of meta information.

[00:31:59] **Ben:** So I was able to write up a ColdFusion script that queries the information schema and looks for the way I have it set up as it looks for numeric columns that are the first column in any of the indexes on that table. and if you're not familiar with how indexes work, essentially you can have one or more columns in an index, and the first column or the leading columns are called the pre.

[00:32:22] **Ben:** And essentially you can quickly look up anything in the prefix of an index. So I knew that, given a numeric column, that's the prefix of an index. I can immediately find instantaneously the max value within that table because of how the indexes are structured in memory and on

[00:32:37] **Tim:** Max via. So that's one thing I was going to ask you, cause you were saying the amount of rows, but really it's the biggest number that can be stored

[00:32:45] **Ben:** Right.

[00:32:46] **Tim:** So if you, so if you had 2.1, 3 billion, You, and then you went to 2.1, 4 billion. He would run out of space even though there's maybe like, just a, a few lines.

[00:32:58] **Ben:** Yeah. A hundred percent. And then that was one of the things that we had to take into account, because for example, we have one table that is sort of an intermediate. Garbage table before something gets fully deleted. So if you can imagine a user deletes a record and we take that record out of the original table, we put it into this garbage table for like 30 days.

[00:33:18] **Ben:**

[00:33:18] **Adam:** It's the recycle

[00:33:19] **Ben:** Yeah, exactly. It's the recycling bin. for a very It's I don't even know why it was designed this way, but that's how someone designed it. and then after 30 days, the garbage files get removed. So essentially that table itself is actually quite small, but it has foreign key references to these other primary keys.

[00:33:35] **Ben:** So even though it may be only has, let's say a hundred thousand records in it, it might have keys in it that are in the like 2 billion range because they just happen to be getting cycled. So, Yeah. we couldn't just use the number rows in a table, cause that could give us a lot of false negatives of where we're doing.

[00:33:50] **Ben:** So I had used this information schema to get reflective information about the database. And then I ended up, storing that in Datadog, which is our APA. And, metrics. So we started in Datadog as engaged. So now I have a graph, a very pretty graph that has straight lines going across. Cause it's going to take a long time for the lines to actually look like they're moving, but I can see like, oh, this table is using 51% of its primary key available primary key in space, and most tables are vastly smaller.

[00:34:21] **Ben:** So like most of them are in the like five to 12% of their entire space, but

[00:34:28] **Adam:** the screenshot that I shared with you where I kind of did the same thing. So mine was much less sophisticated. I wasn't coming up with a general solution for like all of our stuff. I just, I knew that this was the table. If we were going to have this problem, this would be where it would happen because this is where we churn through so many records.

[00:34:43] **Adam:** And, so. I the way that I accomplished that was since I really only cared about one column, I just did select max right. For, to give me the current max value of that column. And, yeah. So it's, I guess it's an unsigned integer, it's four point around up 4.3 billion is the max. Then it's currently at 26 million.

[00:35:05] **Adam:** So that's, just a hair over half of 1% up. And we've been in business for, eight or 10 years. So yeah, I think we're good for awhile.

[00:35:11] **Carol:** Yeah.

[00:35:11] **Carol:** Yeah.

[00:35:12] **Carol:** Way to be proactive, Adam.

[00:35:14] **Tim:** Yep. Yeah. So you switched a big, an unsigned and then you'd be like, two to the power of 64.

[00:35:19] **Ben:** I don't even know what I mean. That's like an, it's like the number of atoms in the universe or

[00:35:23] **Ben:** Something I don't know.

[00:35:24] **Tim:** that. Ridiculous.

[00:35:26] **Ben:** So anyway, that's my story. It was terrifying. It's probably the scariest, I don't know, 24 hours that I've had in the last seven years. I, II've had, when we talked, when we had our episode about, burnout way back, I think this is like episode 13 or something like that.

[00:35:42] **Ben:** I had talked about having panic attacks. ironically, those panic attacks were also related to database failures. we had a corrupted database, like a number of corrupted rows that would just randomly causing our database to crash. What not put episode

[00:35:56] **Adam:** Episode number three was burnout.

[00:35:58] **Ben:** Oh man. so Yeah, so, it seems that all of my darkest moments are related to databases.

[00:36:03] **Ben:** So I guess how hug your data engineers? They're pretty amazing people.

[00:36:09] **Tim:** What's it, database is one of those things. We just work, work, work, work, work. But when they don't, it's like really bad. It is these, it tends to be the single point of failure in your application.

[00:36:18] **Ben:** Yeah.

[00:36:18] **Carol:** Way too often. Yup.

[00:36:20] **Ben:** it's not like you can just karate chop fixes, there's so you hit limits when you have so much data and it takes a long time to move that so much data or refactor that so much data into something that becomes more scalable,

[00:36:33] **Carol:** And usually the one failure cascades very quickly.

[00:36:36] **Ben:** you know? Oh, man.

[00:36:38] **Carol:** will you,

[00:36:39] **Carol:** you've definitely have me sweating over here and Barry like panicked for you, but I'm glad it turned out better than I was expecting the story to go. So,

[00:36:48] **Tim:** Yeah. I mean, what I just learned from this is that, know, she should have been using Postgres,

[00:36:54] **Adam:** I knew it was coming.

[00:36:55] **Ben:** I should have been using Mongo, DB. It's web-scale I don't know if you knew that.

[00:36:59] **Tim:** Mongo, DB as Webscale.

[00:37:02] **Carol:** Oh my goodness.

## [00:37:03] Having People With You During An Incident

[00:37:03] **Ben:** I'll tell you though. I mean, one of the things, when you're, when your stuff is on fire, one of the things you become very cognizant of is that when you're on a call and it's just you and one other person it's super, super terrifying. And then as more people join the call, it just generally gets less terrifying.

[00:37:23] **Ben:** And, uh, uh,and I just kept thanking people. I was like, thank you all for being here. Like I know half of you are just sitting here listening. I'm trying to understand what's going on the incident, but just your presence here is making everybody less stressed. So

[00:37:37] **Ben:** thank you. Thank you. Thank you. for being here.

[00:37:39] **Carol:** Cause it's one thing to be bouncing ideas off one person, but it's a whole nother when you have a room full listening who may interject with one thing, that one thing is something you and the other person might not know. And it's just good to have the knowledge around. Yeah, that's always a

[00:37:54] **Carol:** valued.

[00:37:55] **Tim:** I was going to say bed, in my experience, I've gone to those sort of similar things. But unfortunately, because some of the apps that we do are very customed to a customer and it's running their business and it's going through that failure. Yeah, you need to have that call with a customer on the call who is not necessarily, they don't really care about any technical stuff.

[00:38:13] **Tim:** They just want, you know,yeah, it's going to take, you were moving this, tables and it's going to take, 27 hours to move this over. They'd be like, what?

[00:38:20] **Adam:** It only takes me 23 hours to find somebody to replace you.

[00:38:23] **Tim:** All right, go ahead buddy.

[00:38:26] **Ben:** Oh, so, yeah,

[00:38:28] **Tim:** I am sorry you had that week, man, but I'm glad you got through it. You can laugh about it now. It seems

[00:38:33] **Ben:** I made it to Thanksgiving and I almost an entire pumpkin pie by myself,

[00:38:38] **Carol:** you deserved it.

[00:38:41] **Tim:** You earned it.

[00:38:42] **Carol:** Absolutely.

[00:38:43] **Ben:** man. Pumpkin pies are good.

[00:38:45] **Carol:** They're the best. Do you put cool whip on yours?

[00:38:48] **Ben:** I, I will do a what? Regular whipped cream. I don't know if you're generically, just referring to,

[00:38:54] **Ben:** I

[00:38:54] **Ben:** know.

[00:38:54] **Carol:** cool. Whip is the one you go get from the freezer section and you sit it out on the counter and you use it right

[00:39:01] **Carol:** after it thaws. Yeah. Yeah, it has to be cool with whipped cream is not the same thing. Cool,

[00:39:08] **Ben:** Quip.

[00:39:10] **Tim:** Cool

[00:39:10] **Carol:** cool. I don't know. I probably had it all

[00:39:15] **Adam:** you guys are weird. Why did I start a

[00:39:16] **Adam:** podcast with

[00:39:17] **Adam:** you?

[00:39:18] **Carol:** cause we love cool whip.

[00:39:20] **Adam:** Well, I know we kind of said at the beginning that maybe we would do multiple stories here. I'm really glad that w I'm glad everything turned out well. And that was a great story. I'm glad you told it, Ben. It was a little on the long side, which is fine, but I a, I don't think we have really time to get into more and be, I don't think anybody can follow that.

[00:39:38] **Carol:** no,no, gosh, no. I don't think my heart can handle any more stress either tonight. Yeah.

[00:39:45] **Tim:** no.

[00:39:46] **Adam:** Nope.

[00:39:47] **Adam:**

## [00:39:47] Patreon

[00:39:47] **Adam:** So this episode of Working Code is brought to you by wearing pants to bed, just in case you get paged at 3:00 AM

[00:39:54] **Adam:** and listeners like you. If you like what we're doing here, you might want to consider supporting us on Patreon. And you can do that by going to patreon.com/WorkingCodePod

[00:40:03] **Adam:** you can support us for as little as $4 a month and all of our patrons get, after show access and they get early access to new episodes as they, are edited and ready to go. And of course we have to think our top patrons, Monte, and Peter, you guys rock, we really appreciate your continued support.

## [00:40:19] Thanks For Listening!

[00:40:19] **Adam:** and for everybody else that just is here to listen. That's cool. thanks for listening. And, yeah. So please send us your questions and show topics on Twitter or Instagram @WorkingCodePod, or leave us a message at 512-253-2633 that's 512-253-CODE or join our justat workingcode.dev/discord.

[00:40:38] **Adam:** And not only can you send us your questions and topics, but you can converse with the community. You talk to us, the hosts, talk to each other and talk to our. so yeah, that'll do it. we'll catch you next week and until then,

[00:40:49] **Tim:** Remember guys, your heart matters. Even if you have more than 2 billion, 147 million, 483,647 records in your database.

## [00:41:01] Bloopers

[00:41:01] **Ben:** Sorry.

[00:41:21] **Ben:** I didn't, I did not realize that you had intended to have other stories. That's why I was just sort of

[00:41:25] **Adam:** It

[00:41:25] **Adam:** was

[00:41:26] **Tim:** that's fine. You

[00:41:27] **Carol:** No, no, I didn't really have one to tell anyways.

[00:41:31] **Adam:** Yeah, me neither. I was sitting here the whole time, like, uh,

[00:41:34] **Tim:** I'm glad it went that long.

[00:41:35] **Carol:** that's what she.
