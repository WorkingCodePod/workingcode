---
title: "079: Potluck #5"
description: "This week on the show, Adam and Ben examine a variety of random topics."
date: 2022-06-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/079-potluck-5/id1544142288?i=1000566497626"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, Adam and Ben examine a variety of random topics: Adam loves watching conference videos on YouTube; Ben is feeling terribly insecure about falling behind in the field of web development; neither of us can believe that Elon Musk is forcing his employees back into the office; and, how is it possible that some people seem have so much free time - what the heck is their secret?!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/079-potluck-5.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I am in no way hating on Mongo DB at all. I don't have very much experience with it. My, my lack of experience is just that a lack of experience. It's not a, it's not a lack of preference. I prefer what I know and what I know is MySQL.

[00:00:14] **Adam:** I just got a text message from Tim. It says Postgres.

## [00:00:20] Intro

[00:00:20] **Adam:** Okay. Here we go. It is show number 79 and on today's show, we're going to do it a little bit of the same, a little bit different. so it's just me and Ben again tonight. Carol was supposed to be rejoining us, has gone Mia hope everything's okay.

[00:00:52] **Adam:** but the show must go on. Right. And Tim is still living the life of luxury in Barcelona. so just you and me again tonight, Ben, but I'm sure we'll.

[00:01:02] **Ben:** Yeah.

[00:01:04] **Adam:** but as usual, we'll start with our triumphs and fails. Ben, I guess let's why don't you start it cause it's just you and me

## [00:01:10] Ben's Triumph

[00:01:10] **Ben:** Let's do it. I'm going with triumph and that is that this week I'm on a staycation. So I've taken the week off for work, I guess Monday was Memorial day. So then I took the rest of the week off just to laze around and spend time with the wife and the dog. And, I got some sun and just been trying to relax.

[00:01:29] **Ben:** Yeah. Yeah. I, there was one day I spent a little too much time in the sun and I kept pressing down on my skin to see if it, like it goes white and then does it stay white? I think if it stays white, that's a bad sign. I don't know. I can't remember what the, what they're getting

[00:01:42] **Ben:** burned

[00:01:42] **Adam:** it's totally helpful when you're using this to determine whether or not you've gotten too much sun.

[00:01:50] **Ben:** so I've just been really enjoying, hanging out and do enough and I'm not typically very good about taking vacations. So a little healthy prodding from the misses gets me there, but,

[00:01:59] **Adam:** Yeah, this is not your first staycation during the podcast. so I have to ask, is a staycation your normal for vacation or is this, sort of, a result of COVID or is a staycation, a more normal approach for you

[00:02:13] **Ben:** It's

[00:02:14] **Ben:** I think it's almost more. Dog related? No, w we just have a lot of stuff going on right now. And, we're actually in the process of selling our apartment

[00:02:23] **Ben:** and moving

[00:02:24] **Adam:** Wow. Poor

[00:02:25] **Ben:** uh,and so there's just like a lot of spinning plates right now. And I think the idea of doing anything to add stress to that would have been a, an unpleasant.

[00:02:36] **Ben:** So it's nice to take the time and just relax and run errands and just, I keep wanting to read, but I don't actually do any reading for some reason. I find it when I was younger, it used to be so easy. I'd get a technical book and I would just jam it out in a week, like no problem whatsoever. And now, for some reason, the idea of reading is just, I it's like a huge hurdle.

[00:02:59] **Ben:** I don't know why. I don't know if that's just

[00:03:01] **Ben:** the season or my life or whatnot.

[00:03:04] **Adam:** yeah, I know you, every time we talk about reading, it sounds like you're reading nonfiction, like technical books, that sort of thing.

[00:03:12] **Adam:** Do you read

[00:03:12] **Adam:** much fiction?

[00:03:13] **Ben:** no, if I read fiction, it will be an audio book, but I have not done that lately.

[00:03:18] **Adam:** You should. I think a fiction really got me back into. Like, I was kind of in the same spot when I was younger and, I just kind of hit this wall.

[00:03:27] **Adam:** I think it was like between high school and college, they had so much required reading that I was just like, I hate reading. I don't ever want to do this again, because everything that they made me read was terrible and boring and it was just like memorization. And then, toward the end of college, a buddy of mine recommended a book and I read it and it was like, wow, that was so enjoyable. And so I just kind of fell into a reading fiction,

[00:03:51] **Ben:** Yeah, I definitely gotta try it. but, one other triumph is that the last time we recorded or maybe two times ago we recorded, I can't remember. I was racing to get a feature done at work before this vacation. So I guess that would have been the last time I recorded and I had hoped to get it done by Thursday nights that I would have all Friday to test it.

[00:04:07] **Ben:** Uh, triumph. I actually got it done. Wednesday night was able to turn the feature on Thursday and then plenty of time to make sure nothing exploded. Yeah. so I felt really

[00:04:17] **Adam:** Yeah, that's a

[00:04:18] **Adam:** total failure. You should have,

[00:04:20] **Adam:** you should've played a Minesweeper or something on Thursday. Let everybody think you were still working solitaire,

[00:04:31] **Ben:** but yeah, so I felt really good about that. of course I have analytics attached to it so I can see if anyone uses it and no one's used it, but whatever, I don't care. It's still funded. and I, you know, I put my little,my, a demonstration video in the, the internal releases channel on slack and of course got no response from anyone else in the company.

[00:04:52] **Ben:** So that's just par for the course though. So, I'm just leaning into the idea that no one cares at all about what I'm doing

[00:04:59] **Adam:** you're a ghost. This is like the sixth sense only. There's only one person at that company that can see you.

[00:05:07] **Ben:** Yeah, for real. but I'm actually, I'm going to lean into that hard. And so I actually have something that I wanted to release two years ago. And the engineering manager at the time, or he was like, a VP of product or something at the time I ran it by him. And he was like, no, you can't release that because there's some parody issues between the legacy platform, which I'm on and the new platform, but I'm like, you know what, that was two years ago.

[00:05:32] **Ben:** And, I'm just, I'm saying like the patent on your statement, there has run out and, I'm just going to release it because literally nobody cares what I'm doing at this point. So I'm just gonna start releasing stuff. People told me I can't release because, well, there doesn't seem to be a

[00:05:46] **Ben:** downside to it

[00:05:47] **Adam:** there's gotta be a way to get some attention, right?

[00:05:49] **Ben:** Yeah.

[00:05:50] **Adam:** If you can't, you're like a child, if you can't get the positive attention, you'll go after the negative attention.

[00:05:57] **Adam:** you made me wonder I had to go look and see what are. Currently still open pull request is it is from September of 2020,

[00:06:06] **Ben:** Well, that's not too bad actually.

[00:06:08] **Adam:** really? You think that's not bad

[00:06:10] **Ben:** That's a year and a half. yeah. Two. Yeah. it's like a year and three quarters. That's healthy. That's fine.

[00:06:16] **Adam:** as an open pool request,this from the guy who doesn't want a pull request to live more than a few hours, right? That was you,

[00:06:23] **Ben:** is it a feature that you could imagine? Oh yeah. Yeah, absolutely. Is it a feature you could imagine going into the application now that you're looking at it?

[00:06:29] **Adam:** yes, absolutely.

[00:06:32] **Ben:** Yo, just merge it right now.

[00:06:34] **Adam:** I, you know what, well, it, it hasn't passed CEI and I guess it looks like it has been code reviewed, but now that I think I'm looking at the name of the pull request. Almost certain that we have this as a recently developed feature, I'm guessing that it was backburnered cause it was like incomplete or not a good time for it.

[00:06:55] **Adam:** And it's out on the back burner for so long that somebody else requested it. And it was a high priority thing. And we just started from scratch.

[00:07:03] **Ben:** Yo, I can't tell you how many times. I'll just randomly started looking through the backlog on my teams, Kanban board, and a whole bunch of the tickets I will have created years ago and forgot about it and have since created and completed a ticket for the same exact thing. So, anyway, that's me. That's what I got going on.

[00:07:24] **Ben:** What do you have going on?

## [00:07:26] Adam's Triumph

[00:07:26] **Adam:** So I'm going to go with a triumph with a question mark on the end there, which is that I am crushing it at continuing to wake up every morning and convert oxygen into carbon dioxide.

[00:07:37] **Ben:** That's the way to

[00:07:38] **Adam:** uh,it's just been one of those weeks. I feel like, I wouldn't say that I'm spinning my wheels, but I do feel like I'm not making a whole lot of forward progress.

[00:07:44] **Adam:** I'm I am between events here, is our busy season. We talked about, the events that I work on the weekends this time of year. and so I don't feel bad about not making a whole lot of for-profits and it's like a few little things here and there, things that take time or maintenance work, like cleaning up tables and stuff in the databases that, just require that, occasional spring, cleaning tons of little stuff like that, that, doesn't move the needle on anything, but it's just that little.

[00:08:11] **Adam:** what's the word, not grunt work, but you know, just like little, whatever, throw away stuff. So I'm doing that. and I mean, I guess if I have another triumph and I've probably mentioned this before, but I feel like it's worth mentioning again, which is that it's getting to the point where I can't keep up with our podcast discord, although the community members in there

[00:08:30] **Ben:** A thousand

[00:08:31] **Adam:** are talking to each other, having a great time, whatever, being a community.

[00:08:36] **Adam:** And I try so hard if nothing else than to just read it and like stay up on what's going on. So I can jump in when I have something relevant to add to the conversation or whatever, but it's getting to the point where I can't always do that. Like there are days where I just have to like wake up and declare bankruptcy.

[00:08:51] **Adam:** It's like, sorry, I'm not going to read any of this unless I was tagged. And then, and I think that's a sign of a healthy community. So I'm happy about. I'm sorry that I miss all the messages. I try to read everything, but, yeah, take it.

[00:09:06] **Ben:** I second, everything you're saying

[00:09:08] **Adam:** I'm gonna, count that one in the win column.

[00:09:12] **Ben:** know, going back to your work in these events on the weekends, especially, I'm finding that as I've gotten older, my kind of, resilience. It's like has bottomed out completely. If I get one bad night of sleep, I'm like significantly worse. The next day, if I get two bad nights of sleep in a row, forget it.

[00:09:34] **Ben:** I'm just like, I'm a mess. And I feel the same way. If I ever have to work extended hours or put in an extra day on a, on like a Sunday or something. if there's an emergency or a maintenance window that has to be taken care of, I'm just like, I just feel so completely thrown off like the entire next week.

[00:09:53] **Ben:** We'll just feel wonky at work for some reason. I just, and when I was younger, I feel like it didn't matter, but now it has such a huge impact on just the rest of my life.

[00:10:03] **Adam:** I can relate, especially when, we talked last week about, those 18 hour days and like two or three of them in a row it's particularly Ruffin and that'll throw me off for like maybe three days. but I feel like also my baseline, like a, my baseline of quality of sleep has gone down.

[00:10:20] **Adam:** Right. I, as I'm getting older,just, I don't feel like sleep as is as restorative as it used to be. And then B. Like my baseline of being able to function and feel good and, just like maybe healthy and, honestly, maybe that's because I kind of stopped working out and I'm kinda, put on a few pounds and whatever.

[00:10:41] **Adam:** I'm not as baseline healthy as I used to be, but that just like that energy level. And, I dunno, I feel like I'm a pretty optimistic person. I think that, I've had multiple people in the last couple of weeks tell me that they were surprised that I was 40. people, I think pegged me for between 30 and 35, which I'll take, I'm fine with that.

[00:10:59] **Adam:** but I think I attribute that more to my attitude than anything else. Like, I'm just an optimistic person. I'm a kind of a go getter. Like, w why would I ever give up on anything? Right. if it's worth doing it's worth seeing to the end sort of thing. So anyway,

[00:11:16] **Ben:** well, that's cool. don't lose that.

[00:11:18] **Adam:** Yep. I'll take it, but yeah, like I said, I don't really have anything hugely triumphant or, hugely a failure this week, so I'll just, keep it on, keeping on. So,

## [00:11:29] Conference Talk Videos

[00:11:29] **Adam:** so let's, uh, this show we're going to do something, like I said, a little different, little bit the same. We're going to kind of take, since it's just the two of us, we're going to kind of take a different approach to the potluck.

[00:11:39] **Adam:** Instead of having like one topic each we are going to just kind of go back and forth for a little while, see how it goes on micro topics. So, I wanted to start here. I just want to say. I am so thankful for free YouTube recordings of conference talks and not just like it used to be, the conference talks,somebody in the front row would record it and it would be up on YouTube a month later and you might get two or three from the bigger conferences.

[00:12:05] **Adam:** and now through, I guess corporate sponsorships or whatever, like every conference just about has like professional recordings of every talk. And they're all online within a couple of weeks of the conference. And you can basically get the training, the learning, the inspiration of going to a conference for free, and on your own time, right?

[00:12:25] **Adam:** You don't, you can do it one at a time after dinner when the kids are in bed sort of thing, or on Saturday or during your lunch break or whatever. and I'm really glad for that because. I can't imagine having time to attend conferences in the last few years COVID aside. Right. Like even

[00:12:42] **Adam:** before there was a pandemic, I don't think I, I struggled to remember the last time I went to a conference.

[00:12:47] **Adam:** It was years and that's all just because we're like, we're so busy,

[00:12:51] **Ben:** Yo for real. I think the earliest conference talks that I remember seeing on YouTube, I think the Ruby conferences or Ruby on rails, they seem to be really early in the game for recording and releasing their videos they have, or at least their keynotes, maybe they recorded all their keynotes.

[00:13:06] **Ben:** I don't know. Those are some of the earliest videos that I remember watching on YouTube as far as conferences go. but absolutely, it's so great to have that content. I wish I was much better about allocating time to actually go and watch it. That's something I'm really been weak on in the last couple of years.

[00:13:25] **Adam:** You just mean like, even after the, even though you don't have to be there in real time, you still have struggled to find the time or to make the time to watch them.

[00:13:32] **Ben:** Yeah. Yeah. Yeah. I'm not good about it.

[00:13:35] **Adam:** you asked me what my strategy is.

[00:13:36] **Adam:** what I tend to do is I noticed that conferences will tend to drop a bunch of content all at once. They'll, they'll post 30 sessions or something. and I will pick through the list when I see it. I'm a big user of my YouTube watch later playlist, they make it real easy to add a video to that particular playlist with like a single click in most cases.

[00:13:57] **Adam:** and so I'll anything that looks interest. I'll I have no problem adding it to my watch later. And then if I have 30 minutes to kill, actually in my case, it's usually more like 15 minutes to go. Cause I can, I'll watch minimum two X,playback

[00:14:10] **Adam:** speed.

[00:14:11] **Ben:** Yeah. Yeah.

[00:14:11] **Adam:** but, yeah, if I have some time to kill, I might go through there and see if there's something that peaks my interest in that moment.

[00:14:18] **Adam:** Right? Like I might add 30 things to my watch later list. And over the course of human history, I'll watch 12 of those 30. Right. they maybe were interesting enough to make the list, but not ever interesting enough to actually get me to watch it. But yeah, so, it's lunch hour that I don't have anything else going on or,something like that.

[00:14:38] **Ben:** I keep considering, and this will actually bleed into another topic later on, but I keep considering maybe allocating a particular day of the week, like a Sunday or a Friday or something. And like, anytime that I might normally allocate to experimenting with code on that day, I would reallocate to either reading other people's blogs or watching videos like this.

[00:15:01] **Ben:** I toy around with that idea. I have not yet. But I toyed around with it and I'm just, I'm someone who I thrive inside of some sort of a structure and I haven't quite created the structure that makes it something that I don't have to think about. That's what I need is I need something I don't have to think about because it's just the thing I do.

[00:15:18] **Adam:** Right habits. Yeah. I mean,

[00:15:22] **Ben:** Yeah.

[00:15:23] **Adam:** So, I mean, another thing that I'll do, and I admit that this is not the healthiest habit, but, in part, because of my tinnitus, I tend to throw on some sort of video content on my nightstand every night when I'm going to sleep, because my wife has a, like a white noise machine that she uses to fall asleep and it, in on the worst nights really annoys my tinnitus and kind of makes it so that'll keep me up.

[00:15:48] **Adam:** So, something, yeah, so it often I'll watch like a TV show that I've seen a thousand times that really helps me like zone out and get bored and fall asleep or,sometimes I'll throw on my watch later playlist. Now I hope that I absorbed some of it through osmosis while it's

[00:16:01] **Adam:** playing while I'm sleeping.

[00:16:03] **Adam:** but yeah, no, I don't really have a good strategy. I don't have a set routine to consume that stuff. I agree if I did have some sort of a routine, It would be a good way to consume it. I guess, consumer getting through that list is just not high enough on the priority list for me. It's interesting.

## [00:16:19] Tinnitus

[00:16:19] **Ben:** I know of tinnitus, but I'm not super familiar with it. It is it consistent? Like, do you hear something all the time or does it come and go?

[00:16:26] **Adam:** I hear it pretty much all the time. so you've seen movies where like, somebody is relatively near an explosion or a gunshot or something like that. And in the movie there's like a

[00:16:38] **Ben:** It's all muffled and stuff.

[00:16:39] **Adam:** Yeah. so the, not the muffling part, but that, that really high pitch ringing noise at a low volume is there for me right now.

[00:16:47] **Adam:** I can hear it. even, I've got the noise canceling headphones on, so that actually kind of, some ways enhances the tinnitus because it's blocking out the noise from my ceiling fan and the kids and the weather outside and all the other things. So it's kind of isolating the tinnitus.

[00:17:01] **Adam:** Interesting.

[00:17:02] **Adam:** yeah, cause I think it's coming from the parts of my ear that are damaged from, volume being too loud from my years of listening to metal at a volume 12.

[00:17:13] **Ben:** Well, do we, is tonight as a thing that science understands or do we

[00:17:18] **Ben:** not really know what causes it?

[00:17:20] **Adam:** yeah, it's from hearing damage from loud noises and it can be a lot of different things. Like if you have, you can slowly degrade your hearing, right? So if you, working on the deck of an aircraft carrier and you're not wearing your hearing protection and all these planes are going by, really loud, and it's just a tiny amount of damage every day, building up over time, or, there's the movie thing that gunshot or explosion can cause it, and there've been people that have like gotten it for awhile and it'll go away.

[00:17:47] **Adam:** Mine is permanent

[00:17:49] **Adam:** so

[00:17:49] **Ben:** What about skydiving? I mean, you got air rushing

[00:17:53] **Ben:** into and past your ear. Is that cause a problem?

[00:17:56] **Adam:** no, I mean, if anything's got, having is great because it focuses my mind.

[00:18:01] **Adam:** On

[00:18:02] **Adam:** on the thing that I'm doing. Yeah. Literally there you're right there, there is 120 to 200 mile an hour wind going by my head and I don't hear it. I don't hear a thing, except my, I have an audible altimeter that just beeps a certain altitudes to let me know what's going on.

[00:18:15] **Ben:** And I hear that because I'm expecting, and I'm listening for it, but, I have no memory. I'm sure. Like if I focused on it, I could hear the wind during the jump, but it's not what I'm focusing my attention on. And so I, it just, it's not part of my memory of the event. That's so interesting.

[00:18:32] **Adam:** yeah, I mean, I've got a helmet on with padding in it and stuff, so it helps block some of it out.

[00:18:35] **Adam:** Some people wear earplugs. I think that's more for the airplane noise than the wind noise. But, yeah.

## [00:18:40] Attending Conferences

[00:18:40] **Adam:** I wanted to mention, since we're talking about conference talks, I w we have come a long way since conference box, but,I, as much as I am super glad that recordings of the talks are available, I still see so much value in attending.

[00:18:55] **Ben:** Right. And it's not even just like career-wise, although career is a huge reason to go. Like the networking opportunities. Yeah.

[00:19:02] **Adam:** I won't say that I've gotten jobs from going to conferences, but I know that I've made connections. That would land me a job if I needed one, at conferences. And there's just so, so much of a social aspect to programming that you can't get anywhere else

[00:19:16] **Ben:** and for me, it's such a, it's a social exercise, like I'm way outside my comfort zone when I go to something like that. So the act of pushing myself to do it feels like an accomplishment in and of itself,

[00:19:28] **Adam:** word. Yeah, I think, it's funny. I used to think of myself as an interim. And I think that was because I was shy, but over the recent years, when I've really started to understand the true difference between an introvert and an extrovert, it's like, what makes me feel energized is not being left alone in the quiet with myself and my thoughts, but it's spending time with people I enjoy spending time with so conferences or going out to the drop zone and hanging out with my skydiving buddies or, stuff like that. I think, I have learned that I am an extrovert, which is a weird thought for somebody that's shy.

[00:20:03] **Ben:** Well, that's good. Better understanding of yourself introspection.

## [00:20:09] Experience, Learning And FOMO

[00:20:09] **Adam:**

[00:20:09] **Ben:** All right. So I wanted to talk about some insecurities that I've been having, which is. Something we've sort of touched upon in previous shows this idea that a in a 10 year career, you can have 10 years of continued growth, or you can have the same year repeated 10 times, and you're still sort of a,a novice developer, even though you have a career under your belt.

[00:20:30] **Ben:** And, I definitely know that I've grown a lot as a, as an engineer and, not just as an engineer, but as someone who works with a team and who works with customers and with support staff, I feel like I have a very well-rounded set of experiences. but given the fact that I am still to this day, working on a legacy platform that has older technologies, I hesitate to call them legacy technologies.

[00:20:55] **Ben:** So I'll call them older technologies.

[00:20:57] **Adam:** I

[00:20:57] **Adam:** don't hesitate. It is.

[00:20:58] **Ben:** I get, I get nervous that. Am I actually taking steps every day or week or month to move my mastery of web development forward because in an existing application where you have to maintain it over time, there's only so much that you can responsibly introduce.

[00:21:24] **Ben:** I can't just grab the new shiny thing. Cause I think it's fascinating unless there's a real business case for it. mostly I just have to nudge the current application to the left a little bit or to the right a little bit and fix bugs and remove frictions. And,I get nervous that I'm falling behind in terms of the value that I'm extracting or can extract from my day to day work.

[00:21:51] **Ben:** Does that connect with.

[00:21:52] **Adam:** Yes. so I guess my first thought is FOMO. So you see all this stuff happening and it's like the first reaction to that is like, oh yeah, we really need to be doing that type of work. like, for me that is, I'm seeing like different types of testing, things like react, storybook,so many different things.

[00:22:14] **Ben:** Yeah.

[00:22:14] **Ben:** Yeah.

[00:22:15] **Adam:** and, I totally can relate with your comment about like, Do I just want that because it's the new shiny, and it's a distraction from the work that I need to get done or do I want to do that? Because it will actually improve our development processes and make us more capable or more efficient or smarter because we've done it sort of thing.

[00:22:37] **Adam:** and God, I wish I had the answer to that, but that's like, for me, that's the big thing, right? Like I see all this stuff going on as my attention is mostly on the JavaScript and especially the react community. and there's so many people in that community, you are bound to have some actual genius geniuses in that group and they are getting so much done, introducing so many great new ideas, so many great new products and, processes and methodologies for things.

[00:23:05] **Adam:** And it's like, it's so hard to tell the difference between. hype and actually something that might be beneficial. and honestly, I think that the difference could be entirely from the, perspective of the person or the company trying to implement it. Right. Like, just because it's, only going to be hyped for us doesn't mean that it can't be actually beneficial to the company that started it or some other group that's trying to adopt it.

[00:23:30] **Ben:** Yeah.

[00:23:32] **Adam:** So, yeah. it's impossible. I feel like to get that right.

[00:23:36] **Ben:** I try to center myself in this belief that the things that I know aren't necessarily language or framework or syntax specific, like there's a relational database and there's NoSQL databases. And those are very different from a, from like a detailed point of view, but indexing documents and querying data and deleting data.

[00:24:00] **Ben:** That's like a highly transferable skill. And then like if I'm working in angular, JS on my legacy platform, that still I'm building a single page application and it has views and it has to fetch data and there's routing. So yes, that's really old compared to the way modern angular or the way react router does it, but it's not like fundamentally different.

[00:24:24] **Ben:** It's just a very different syntax, maybe in a different framework. So like theoretically, I should be able to take all that stuff and apply it in a new context with some additional learning. And I try to hold onto that thought and be like, you're not falling behind because the things that you're learning are transferable they're transferable the transferable.

[00:24:41] **Ben:** But that, that FOMO, you talk about it just, it sneaks in. And I guess, because I'm looking at these other technologies as an outsider, maybe that's what it is because I'm looking at them as an outsider. It's hard for me to see the similarities. I focus more on the differences and because I'm focusing on the differences, that's what makes me feel like I'm falling behind because there's a lot of stuff I don't know.

[00:25:05] **Ben:** but if I was more versed in those technologies, I'd see the, oh, actually this is like 90% the same stuff and I'd feel more comfortable, but it's tough. I, another strategy that I try to use to combat this insecurity is to be conscious of the idea. That I see something that's wrong in the code base.

[00:25:24] **Ben:** And I try to come up with a S a fixed for it, or I try to refactor it to be cleaner or more elegant. And as long as I'm constantly finding stuff that I'm dissatisfied with and thinking of ways that I might be able to tweak it or do it better, that to me also feels it's like this beacon, this reminder that I am growing, that if I wasn't dissatisfied, if I wasn't noticing these things is because I literally couldn't think of a better way to do it, despite all of the experiences that I've had.

## [00:25:54] What Makes A Junior Developer

[00:25:54] **Adam:** Yeah, made me think about, I, I've been kind of asking myself some questions lately. I'm not big on introspection as we just discussed, but,as an industry, we, I think could probably agree that we have a lot of people that are trying to break into the industry that are at the junior level or in a lot of cases, not even quite legitimately the junior level, they, they understand what they're trying to do, but they don't necessarily understand how to do it.

[00:26:22] **Adam:** I've been kind of asking myself, like, how do you truly interview for a junior developer role? Not that I have a whole role to fill, but just like trying to figure out for myself, what am I, what would I look for in a junior developer where, I'm trying to hire somebody that may be fresh out of school or bootcamp, or self-taught even, the things that I would look for are a solid grasp of some fundamentals beyond if else and. a good attitude and like an eagerness to learn, right? So like, if you can show me that you are willing to Google and see if a problem through, to the end, even if it's hard and it takes time and that you understand recursion to look, to give one example, right? That's something that's a fundamental, the basic case of it is not that hard, but it's also not a gimme, right?

[00:27:18] **Adam:** Like recursion is one of those things that I don't think people inherently understand. We all kind of have to learn it. then to me that I think qualifies you as a junior developer, like you, if you want to learn and you're willing to learn, and you have demonstrated the ability to learn, then. what more could you ask for, from somebody whose job is to come in and learn?

[00:27:42] **Adam:** Right.

[00:27:43] **Ben:** I feel like as someone who works at a company where we sort of only hire senior and above engineers, which, there's a lot of hand ringing around whether or not that's a good thing to begin with. I feel like it, before you even interviewed for someone at a junior level, you'd have to at least have a sense of the kind of work that is available at the company that can be junior.

[00:28:05] **Adam:** That's a really good.

[00:28:05] **Ben:** you know,

[00:28:05] **Ben:** like you wouldn't necessarily want to hire a junior person and then throw them into the, like the message queuing and data reprocessing thing that you're working on. I mean, like, yeah, could they do it, but it's like, And it might just be too complicated or it's, to the sort of eventual consistency of some of the data, that's like that in and of itself has a very advanced concept.

[00:28:28] **Adam:** you're dead on. I mean, when I try to think of like the course of my career, it's like, I was a junior at a time when web development was a junior, the industry, right. You know,we were doing Pearl CGI scripts and,post-bac was like the only option. Right. And before there ever even was Ajax and,people were like, what's a framework.

[00:28:50] **Adam:** And, so, so I got, I kind of grew up with the industry. So now. the problems that I deal with on a day-to-day basis. Yeah. there's always going to be like little bugs that somebody can wet their whistle on, but at the same time, how do you bridge that gap? I have no idea. wish I knew.

[00:29:06] **Ben:** Yeah, it's definitely hard. and I'll tell you, kind of looping back to your topic as well on the YouTube videos. That's I think if I just spent some time and watched videos from conferences or from meetup, online meetups, that kind of thing, I think that would help alleviate a lot of the insecurity because I think a lot of the insecurity is the black box nature of the things.

[00:29:31] **Ben:** I don't know. It's like, I remember the first time I started learning about XML and before that I was like, oh, XMLs is really complicated data to. And then you start to learn about, and you're like, oh no, actually that's super simple. It's just tags and attributes and child tags, like the mystery of it has gone.

[00:29:49] **Ben:** and I think if I focused on allocating some amount of time every week to watching some new content, even if it wasn't something that I could apply at work, per se, it would at least, I think, stamp out that FOMO that there's this whole world of technology that's moving. And even if I don't use it, at least I know it's there and maybe I'd feel better about it.

[00:30:14] **Ben:** Cause it, cause again, it's, I think a lot of what I know is a highly transferable, but because I don't really know these other things, I don't recognize the transfer. Context for that, those other technologies represent. So if I could see people talk about them, I can say, oh, okay. I understand those ideas.

[00:30:30] **Ben:** Now that you're discussing them, I could visualize myself moving in that direction. Or I could take ideas that you're presenting and think about how they map back onto the stuff that I'm doing. and it would make me feel like my, understanding is more relevant than it might feel in isolation.

[00:30:47] **Adam:** Yeah, maybe you should go back and finish seven languages in seven weeks.

[00:30:51] **Ben:** Well, I, one of the ones I wanted to try is seven databases in seven weeks. because I basically only know MySQL and I guess I know red S and I think that's in that book. but that's it, Mongo DB, I will query when I have to, but that's basically as much as I know about it. I think seeing different data storage systems would really be very interesting.

[00:31:11] **Adam:** Hmm.

## [00:31:12] What's Going On With MongoDB

[00:31:12] **Ben:** Is Mongo DB that this is like a stupid question maybe, but like, is Mongo DB still a hot technology? Are people loving on it?

[00:31:19] **Ben:** Do you know?

[00:31:19] **Adam:** Oh,

[00:31:20] **Ben:** the, this is, you're going to get us canceled. no. Cause it was so hot. It was so hot for a

[00:31:27] **Ben:** while. And then

[00:31:29] **Ben:** maybe it

[00:31:30] **Ben:** just moved into like now it's battle-tested I dunno.

[00:31:32] **Adam:** Yeah, I think there's a lot of people out there using it. I don't think that, I think that the hype curve it's kind of come down from that peak, that initial peak,and people are finding where it actually fits in is, a valuable use case.

[00:31:45] **Adam:** So I think your instinct or your read of the room here is about right. Like it's not as, it's not as hyped as it used to be. People are talking about it less. I think part of that is just because like, there's less to say, right? It's either you have been convinced and you're now using it, or you are probably never going to need it.

[00:32:06] **Adam:** And so there's, there's no need to continue repeating the same conference talks or whatever, over and over.

[00:32:15] **Ben:** Cause, cause it, it definitely felt for a while. I'd say for like a S a couple of years, at least that Mongo was just. At least in the vocal community was the default choice. Oh, I'm going to spin up a web application. Of course, I'm going to choose Mongo. I mean, even there was the mean stack M E a N, which I think was Mongo express, angular and node.

[00:32:39] **Ben:** Obviously that was a very angular focused, stack. But, I, it, again, like, it was just this default new application, of course I'm going to choose a document database, but I've always been a relational guy, so I don't, I was not necessarily on that bandwagon.

[00:32:53] **Adam:** Yeah. I think you're right. There's a, there's some correlation between what I feel like I have seen is that there's some correlation between people who don't have a whole lot of relational experience and people who. We're like leading the hype train on Mongo. not that they did anything wrong, but like, you are going to champion the thing that, you know, nine times out of 10.

[00:33:17] **Ben:** Yeah. Yeah. and just to be clear, here I am in no way hating on Mongo DB at all. I don't have very much experience with it. My, my lack of experience is just that a lack of experience. It's not a, it's not a lack of preference. I prefer what I know and what I know is MySQL.

[00:33:33] **Adam:** I just got a text message from Tim. It says Postgres.

[00:33:36] **Ben:** Oh, that's so good. Oh yeah.

[00:33:48] **Adam:** I didn't even think it was that good of

[00:33:49] **Ben:** we miss you. Well, it just tickled me because I know like, I don't know. It just didn't hit me. It hit me out of nowhere.

## [00:33:59] Returning To The Office And Remote Work

[00:33:59] **Adam:** so I want to talk about Elon Musk's, email that kind of went a little bit viral about, requiring all Tesla workers to return to the office. I pulled up a Reuters article about it, and I'm gonna read a couple of quotes from the letter, cause I know Ben, you said you haven't seen this.

[00:34:14] **Adam:** So couple of things. so it starts out, everyone at Tesla is required to spend a minimum 40 hours in the office per week. and then let's see what else, if you don't show up, we will assume you have resigned. the more senior you are, the more visible you must be your presence. Yeah. and he wrote like, that's why I lived in the factory so much so that those on the line could see me working alongside them.

[00:34:33] **Adam:** If I had not done that Tesla would long ago have gone bankrupt. Like there's some truth to that. Like as the founder. You have to have more skin in the game than anybody else, right? Like if you don't believe in your mission to the point that you will sleep on the factory, break room couch or whatever, then you're not going to get people to rally behind your mission. But, also I think that he is a victim of his own success. I think that he has some legitimately good ideas, his gumption to make this is a space X thing, but his gumption to make,propulsively landing rockets and reusable rockets a thing. And he was just willing to throw money at that problem until it was solved.

[00:35:15] **Adam:** Like, obviously that's better for the world and I am grateful to him for that, but also like on balance, he's done. So many things that are awful, right? Like he called the guy, he called the guy that saved kids in the cave, collapsed thing, like a PIDO with no evidence. he like this, I think this is just another example of kind of how he is, if not completely, at least on his way to completely out of touch with reality.

[00:35:48] **Adam:** Like the, I don't know, you're not going to be able to remote work when you worked at like, as a cook at a fast food restaurant, that's not going to happen. There's some jobs that just can't be done. You, your garbage man can't work from home, right? Like there's just some jobs inherently you have to be onsite for.

[00:36:08] **Adam:** But if if it's a knowledge job, like research or coding or something like that, I really feel like The paradigm has changed, especially after COVID. I got, I hope to be able to say that we are in a post COVID world someday. but even now during COVID like, it's proven so much that

[00:36:29] **Ben:** Yeah,

[00:36:30] **Adam:** is not a necessity.

[00:36:32] **Adam:** And I mean, you and I know this very well. We've both not had, I guess you have an office at Invision, but you've been heavily remote for a long

[00:36:41] **Adam:** time now, too.

[00:36:42] **Ben:** no. no. We have where Invisions entirely remote.

[00:36:46] **Adam:** Okay. Maybe the, so there was a video I saw of you, in an office. I forget what the point of it was. this is this, some old video of you had dug up on YouTube or something, but,

[00:36:55] **Ben:** Yeah, that may have been an epicenter. That's where Invision was started. Epicenter had an office, but you know, it was also like four people. but I, so when people talk about what they miss about being in an office, a lot of it is this, incidental conversations that pop up and now people are sharing ideas and suddenly new ideas are being generated and people are creating new features based on random conversations.

[00:37:21] **Ben:** I used to work in an office for years and that never happened for me. If I was talking to people, it was about movies. It was about TV shows. we were never randomly talking about work stuff. Every, if you were working at your desk, you were doing work stuff. So that to me, I don't miss that because it didn't, I never had it.

[00:37:41] **Adam:** no it did happen is, six people would stop by your desk and say, Hey, we're going to go down to the break room and get some coffee. Do you want to come?

[00:37:47] **Adam:** And, and you know, by the time you got there, there would be 15 people in a group, burning half an hour. Chit chatting about, you know,what restaurant they went to over the weekend. So,

[00:37:58] **Ben:** be clear. I do miss some of the social aspects of being in an office. I used to work at a company where every Friday for there was like a six month period. It was glorious where every Friday we would all get, Buffalo wings for the place in the city called atomic wings. And so you would get this trough.

[00:38:15] **Ben:** I mean, it was literally a trough of Buffalo wings and we'd all just hoard around a table and eat. And it was just great. Like, I really do honestly, miss that kind of comradery,even trying to replicate that over zoom, it's just, it's very awkward. I think we've tried to do little happy hours and like brown bag lunches kind of thing.

[00:38:37] **Ben:** And it's just not the same. So I

[00:38:39] **Ben:** miss that

[00:38:40] **Adam:** let me ask you this. So I have kind of kept my eye on the Philly has this, like what do they call it? People first businesses, there's a film, a company based out of Philly, called Wildbit and they consider themselves a people first business. their goal as a company is to basically survive as a company like doing whatever it takes to survive, to make a good place to work for their people.

[00:39:05] **Adam:** Right? So they, their first priority is to their people. The second later priorities are the work that they need to get done. and so it just was an interesting concept to me. So I've kind of kept an eye on them and they created this whole sort of movement and there's a bunch of other companies and something I noticed among a lot of these companies is that they do like a company retreat yearly, or sometimes even more often than yearly.

[00:39:27] **Adam:** And they'll go like somewhere, halfway around the world and they'll fly all like 75 people in the company from, middle America, all the way to Barcelona or wherever they'll go to the Netherlands or something. And like that alone has got to be a ridiculous amount of money. And then you got to feed these people and give them a place to stay and all, and then you gotta do some activities and you gotta have place for all these people to hang out together during the day.

[00:39:50] **Ben:** So you need a big venue. and, my first thought is like, let's cut the office out of the equation and spend the office budget on,on company. what did I call it? Retreats.

[00:40:01] **Adam:** yeah, retreats or, anything like that?

[00:40:05] **Adam:** I think that makes sense. because there is something very healthy about meeting your coworkers in person. it just changes the way you feel about them. absolutely.

[00:40:15] **Ben:** there was one person, obviously I will not name names. There was one person I used to have to get on calls with, and it always just felt very tedious.

[00:40:23] **Ben:** And I literally think it was just the tone of their voice. Like there was something in the tone of their voice that I found very. Exhausting to explain it. And then I met them in person for the first time at a conference, like a work conference. And it completely changed the way that I felt about them.

[00:40:41] **Ben:** Like just seeing them in physical form. and then being on calls with them after that was totally different. And it was just that the magic of the in-person thing. But, I don't need to do that every day to get that magic. I did it once and it worked. so

[00:40:54] **Ben:** I don't know the whole Elon Musk thing.

[00:40:56] **Ben:** That's

[00:40:56] **Adam:** I can totally relate. but instead of coworkers, for me, it's customers, right? So there are a lot of people that I interact with solely through help tickets. and if maybe they're having a rough day or, they feel like they've asked for this same bug to be fixed a bunch of times or whatever, like they can come off as very annoyed and like, you see that enough and you start to develop this mental image of them as just this like disgruntled unhappy person.

[00:41:22] **Adam:** And then, it becomes a chore to respond to their tickets and you just, it creates this negative relationship, but then you go and you spend a day onsite. that's something we used to do. especially when it was just me and Steve, but I'm still a little bit. And in more recent years pre COVID, we would just like for no reason at all, we would just go do a day onsite at one of our relatively local customers.

[00:41:44] **Adam:** We would go and work out of their office just to like, get some FaceTime with the customers.

[00:41:48] **Ben:** Yup.

[00:41:49] **Adam:** that did wonders for personal relationships.

[00:41:52] **Ben:** Well, it'll be interesting to see what happens with the Elon Musk stuff, because especially in today's job market at just seeing us with the great resignation. There's job opportunities all over the place.

[00:42:07] **Adam:** Yeah.

[00:42:07] **Ben:** I dunno. I wonder if there's going to be a lot of people that leave,

[00:42:10] **Adam:** there was a ton of people that were I'm sorry, there was a ton of. job opportunities in tech prior to the great resignation. So I got to believe that people are moving on to companies that will treat them better. And the companies that are finding themselves unable to find and retain talent are needing to take a good look in the mirror.

## [00:42:30] Crypto Update

[00:42:30] **Ben:** random side tangent, just talking to my job opportunities. I don't know anything about the crypto world. and as far as I knew everything was going well, but I have noticed on a couple of podcasts, I have listening to people are like, people are talking about like, oh, don't panic. It's going to be okay.

[00:42:48] **Ben:** Don't panic. it did something. Did the crypto market like crash or something?

[00:42:53] **Adam:** yeah, so Bitcoin crashed significantly. And I think that as a result, like all the other ones, especially the quote unquote _(quack)_ coin,the, mean coins, I guess they would prefer to be called, kind of took a nosedive along with them.

[00:43:07] **Adam:** So,

[00:43:08] **Ben:** Not doge coin. I hope doge coin still

[00:43:10] **Adam:** uh,so I still have a little bit of money in doge because I, I put some in, at a bad time and it crashed and I was like, well, it's only a hundred bucks, so I'm just going to wait until I can get most of that back. And so it's been sitting there in Robin hood and it's very amusing to me because.

[00:43:25] **Adam:** Two or three notifications a day that it's like, don't just up 5% to eight and 8.90 cents per coin or whatever. And I'm like, okay, that's great. And then later in the day, I'll get a notification that dojo is down 5% to 8.50 cents. And I'm like, okay. Yeah. So it's one of those things where it's like, it changes so little on a day-to-day basis. And I mean, ever since the kind of bottom fell out of it, it's just been like, whatever, if I ever get my money back, that'd be great if I don't. Okay. I gambled a little bit and I lost it and that's why I didn't put any more in than I was willing to set on fire, Like,

[00:44:07] **Ben:** Absolutely

[00:44:09] **Adam:** so

[00:44:10] **Adam:**

## [00:44:10] Time Management And Hobbies

[00:44:10] **Ben:** All right. I get jealous slash resentful of people who seem to have a lot of hobbies. And let me explain when I was in high school, I'm like decently smart, I think. And like, I always, I've always done decently well in school, but it was always a lot of work. And I had friends that really just seemed to sort of skate through school and crush it.

[00:44:36] **Ben:** I had a friend who literally didn't even bring a notebook to his classes and was just crushing it all the time. And I was always so jealous of people who just, some things just seem to come easy to them. And I'm sure that's an oversimplification. of what goes on, but it definitely, from my perspective, it seemed like there are people who just did not have to work as hard as I had to work.

[00:45:02] **Ben:** And in the technology world, I listened to a lot of podcasts and these people who seem to be very successful professionally are always talking about all these hobbies that they have. And I mean, think like you were saying earlier, I go to movies, I do watch a lot of TV. I happen to love TV. and I work out and walk the dog and stuff, but I don't know, maybe I don't take full stock of all the things that I do, but, I feel like I spent a tremendous amount of time trying to hone my craft.

[00:45:33] **Ben:** And when I see people who feel very successful and they're talking about all the hobbies they do, part of me is always like, why do you get to have so much time for your hobbies? Like, that's not.

[00:45:45] **Ben:** That's not fair, which I had more time, but then I get nervous. So going back to my insecurities about doing the same year over and over again, sometimes I worry that so much of my time is spent moving the craftmanship needle from like 95 to 96.

[00:46:04] **Ben:** And like, am I investing a lot of time and stuff that doesn't have a really good return on investment or is like microscopically incrementally better than I was yesterday? Kind of a thing. But,

[00:46:14] **Ben:** I don't know. I just, I get jealous.

[00:46:16] **Adam:** you alluded to this in our, you said, like when we were talking earlier about you going to see movies, I said, well, we had a brief discussion before we started recording about, the hobby thing. And you said, I told you that, going to see movies is one of your hobbies. And it just occurred to me while you were talking through all that stuff.

[00:46:31] **Adam:** Like you are a prolific. you blog has got to be almost every day. And I would say that even though it has professional benefit has gotta be a hobby of yours. And

[00:46:43] **Adam:** I mean, I don't know how much of that you do, quote unquote on the clock, but,even if it is a hundred

[00:46:48] **Adam:** percent on the clock, okay.

[00:46:49] **Adam:** Like I say, even if it's a hundred percent on the clock, I would still consider it a hobby. and when you started talking about, you see these people that have gained some minor celebrity in development communities,and being jealous of them and their hobby time, I thought you were going to go to a different place with that, which was that I thought you were going to say, like they spend some time on their stuff and they've got this, whatever minor celebrity status.

[00:47:12] **Adam:** why is that out of your grasp? I don't know. I would say that within your bubble, the ColdFusion community, most people would agree that you have. Celebrity status. I think that, the bubble itself is a C or D list. And so th the benefits that, that celebrity confers are, lower down on the list there.

[00:47:33] **Adam:** But, so I think that

[00:47:35] **Ben:** That's hilarious.

[00:47:36] **Ben:** I, I love you, Ben. I'mYou're right. No, no,no. I totally agree with exactly what you're saying.

[00:47:42] **Adam:** okay.

[00:47:43] **Ben:** But let me ask you a question. Cause I know we've talked about how you have to start preparing to get the kids ready for school the night before, like you have to start planning, do you find that you it's like you finish one thing and then immediately you have the next thing and then you finish that and you immediately have the next thing in your day.

[00:48:02] **Ben:** I feel like I am constantly out of. That I'm running up to the end of some window that I've allocated some effort for. And that finishes and immediately I have to go into a meeting and in the moment the meeting ends, I have to start working on some code and then like that finishes, then I have to go do something else.

[00:48:20] **Ben:** I it's like constant motion. Did, is that relatable? Are you feeling like that at all?

[00:48:25] **Adam:** Are you specifically talking about work? Are you specifically talking about

[00:48:29] **Adam:** life.

[00:48:30] **Ben:** life. I

[00:48:31] **Adam:** Okay.

[00:48:32] **Adam:** yes. I would say on for any given week, there might be, so Monday through Friday, so like I'm talking my free time, but outside of work, but like, during the work week, I, so during those five days, I would say I get maybe three to four now I should.

[00:48:52] **Adam:** Okay. So three to four days where maybe like twice a day, I'll find myself with somewhere between 15 minutes and an hour of like personal. Everything else is allocated to work or family. So, it's like, I either have time where I've, finished my Workday. I've gotten to a really good stopping point and I have no personal conflict.

[00:49:16] **Adam:** no like mental conflict with like, just calling it a day at 4 45. And,dinner's at six. So I find myself, like I clean up my stuff from the day and I've got my, I've got an hour until dinner. The kids are busy watching their YouTube videos of people playing Minecraft or whatever.

[00:49:30] **Adam:** and my wife is making dinner and I'm like, okay, I'm available. Can I help with dinner? She's like, no, there's not really anything for you to do. It's already in the oven and we're just waiting sort of thing. and I'm like, okay, I guess I will watch YouTube or I will read a book or something. That happens a couple of times a week. And then, just because of the way our schedules work out, I often these days find myself with somewhere between a half hour and an hour of free time. Most mornings, the kids get on the school bus pretty early. Most days, my wife, is going back into her office.

[00:49:59] **Adam:** Now she is a therapist. and she's got maybe about a 50, 50 ratio of people who want to be seen in person versus want to be seen over telehealth. and so like, everybody else is out of the house, but it's still 7:00 AM. I'm like, I guess I could go to work and then I'd be done. I mean, being truthful to myself, I would still work until five or six most days.

[00:50:21] **Adam:** and so that would just be

[00:50:23] **Adam:** for lack of a better word, it would be punishing myself or, giving the company free money or whatever. Like, and not that I have any problem with that. if there's something that I'm excited to work on, I'll go work on it at seven. That's fine. But, The other thing that I guess is kind of coming into that equation is, I hesitate to look up how long it's been, but I haven't worked out in my home gym stuff in far too long.

[00:50:49] **Adam:** And that morning time used to be where I would go to the gym go workout. So, to answer your question, yes, most of my time is allocated, right? It's like work and then maybe some free time family dinner, and then it's like family together time and then it's put the kids to bed. And then my wife and I usually have somewhere between a half hour and an hour to like watch some TV decompress from our day.

[00:51:13] **Adam:** We might not even watch any TV at all. If we have like a lot of stuff to talk about, to plan out the week or to deal with whatever's going on with the kids. Cause there's always something going on, mental health things or got to prepare for school stuff or whatever's going on. And then it's like, okay.

[00:51:28] **Adam:** And it's, my wife has really good about, bedtime. And I think it's just because she's a, not a night person, right. that time of night, like 9, 9, 15 comes around. She's like, I am exhausted. I am going to bed and I've trained myself to try to be really good about following her, like, okay, I'm going to come to bed too.

[00:51:47] **Adam:** because once I'm in bed and the lights are off and I've got, an old episode of Archer on or something like I'm out within five minutes anyway, which is really good for me, like to be able to get enough sleep, because whether I go to sleep at nine 15, when she wants to go to bed, or if I were to follow my own body's clock and stay up until 1130, the alarm is going to go off at 5 45, no matter what.

[00:52:07] **Adam:** So I might as well get that extra sleep, but yeah, you're right. Like our entire weekday schedule is heavily based on what time the kids have to get on to school. Yeah, that dictates what time we have dinner at. It dictates what time we get up in the morning. It dictates so much, and it's a blessing and a curse, right?

[00:52:28] **Adam:** Because especially with kids, both my kids have ADHD. I have ADHD, that routine and that structure to the day can be extremely helpful. It can also be annoying when you want to try and be spontaneous. But, having that structure at least gives us an anchor point to, make things feel like, less of a struggle, right?

[00:52:50] **Adam:** The kids are used to having dinner at six, so we don't have to like fight with them, to put down the video games and come sit at the table. So,and, yes, I did just say we eat dinner at six. O'clock like a geriatric family, but

[00:53:03] **Ben:** Yeah. that's

[00:53:03] **Ben:** what I eat dinner. There's nothing wrong with that.

[00:53:06] **Adam:** Hey, do you, were you, so in college we used to joke about people that ate dinner at six o'clock and we made these jokes about people who he dinner six o'clock while we were quote unquote pre-gaming to go out partying.

[00:53:19] **Adam:** And we were doing that. Pre-gaming at like 10 o'clock at night.

[00:53:22] **Ben:** Yeah, yo in college, I used to eat dinner at five. I, yeah, PM is six is like, I'm so European eating dinner at six.

[00:53:37] **Adam:** yeah, I mean, I've gotten into a little bit of it. This goes with the hand in hand with the not working out, but I've got into a little bit about, of a bad habit of, having a, like a bedtime snack, maybe half hour before we go to bed. And I try to do something healthier. If I have the motivation, I'll do like an apple and peanut butter instead of a threat five pounds of Jesus.

[00:53:56] **Adam:** But, yeah, I don't know.

[00:53:58] **Ben:** Well, I brushed my teeth right after dinner and then I know if I eat again, I'd have to brush my teeth again so that I'm like, oh, that's too much work.

[00:54:05] **Adam:** that's an interesting

[00:54:06] **Adam:** approach. So, I mean, I w I, I don't want to let us leave the hobby topic, without addressing the fact that I have hobbies.

[00:54:14] **Ben:** No. No, I know. and I think what you said about me is very accurate. and I think a lot of the quote unquote professional development that I think that I do is I, you can categorize it as hobby as well.

[00:54:27] **Adam:** and I honestly, I think that it's fantastic. I think that it's, you were talking about transferable skills. I think that it's gotta be 90% plus of the stuff that you're spending your personal time on as like personal professional development is gotta be transferable skills, right. You're learning the fundamentals of things, or you're learning.

[00:54:44] **Adam:** how to debug or how to learn something new, right. You're learning a new technology or whatever. So those are all great things. I think that maybe it's because of the rigidity of our routine and our schedule that I have gotten so good at claiming my time, right. I used to be the type of person that would put in my 40 hours a week at work.

[00:55:05] **Adam:** And then I would go home and work on the exact same stuff, maybe personal projects, but same skills, blog posts about all that stuff. Kind of very similar to what you're doing. just because I was passionate about it and that was fine. But, having that rigidity of my schedule and not having any other opportunities except on the weekends and an evenings for me time,I've developed this weird ability and I say, it's weird because it's, it feels weird to me, but this weird ability to.

[00:55:34] **Adam:** Completely ignore all email, not just my work email, but like all email. and sometimes even like all text messages and everything to slack discord, all of it, on the weekends and even on non-business hours during the day. So like the only time that I can recall ever paying attention to work stuff, not during my business hours is when I'm on call and I get the on call alarm, or if something escalates to me when it's not my week.

[00:55:59] **Adam:** and I'm at the same time, like I'm proud of that because I think that's a very healthy approach to take when you're, when, I don't know. Maybe it's just a healthy approach to take in general, but if you, if your hobbies, if you enjoy, that professional development, I don't think there's anything wrong with that.

[00:56:14] **Adam:** I just, I guess maybe I kind of have. Lost interest.

[00:56:17] **Adam:** like I was saying, I've gotten really good at ignoring all those off. And what that does is that creates that personal time for me. and if I didn't shut out work, there's no way I would have time for woodworking and skydiving, which I would say are my two most prevalent hobbies.

[00:56:30] **Adam:** Although I've always been a person that has 11 hobbies, like you can see behind me here, I have a couple of guitars. I have a metal from a 5k run that I did,all kinds of, reading for me as a hobby. I like to just kind of sit down and enjoy a fiction So.

[00:56:45] **Adam:**

## [00:56:45] Patreon

[00:56:45] **Adam:** So this episode of Working Code is brought to you by the dealer service center. They've been trying to reach you about your cars, extended warranty, they just wanted us to let you know that you should reach out, and listeners like you.

[00:56:54] **Adam:** If you're enjoying the show, you should consider supporting us on Patreon. it's the best way to help keep the show running Patriot donations, cover the cost of our editing and recording. And we couldn't do this every week without your support. So we really appreciate your support, a special thanks.

[00:57:08] **Adam:** Go out to our top patron, Monte and new this week we have, so we have two new patrons. and I'll, I guess I'll start with Gavin pickin. He's a new top patron. So you're going to be here in Gavin's name every week.

[00:57:18] **Adam:** Welcome aboard. Thank

[00:57:20] **Adam:** you. Yeah, dude, those are awesome. Really glad to have you. we also have another new patron this week.

[00:57:25] **Adam:** Coleman's Brando, and I have to say a special shout out to Colin. I hope that your profile picture on Patreon is of you because it's a wing suitor. So I've got a fellow skydiver in the podcast here. Yeah. So, welcome aboard Coleman. and I wanted to go back in and also give a shout out to Gavin. I guess he kind of found the podcast a little bit later or when he found it, there was a bunch of episodes, so he's been going back and listening to the entire back catalog and every now and then, tweeting at us couple of interesting observations or whatever, as he listens on his bike rides and that sort of thing.

[00:58:00] **Adam:** but, yeah. Welcome aboard. Glad to have you, so all of our patrons get early access to an ad free version of new episodes and the after show, and actually on today's after show or, what did I say? It's going to be the after action review or the post-mortem post-mortem we're going to talk about a couple of things. We're gonna talk about a top gun Maverick.

[00:58:15] **Adam:** I went to go see it. and I have thoughts and, Ben wants to talk about love, death and robots. So we're going to talk about those things.

## [00:58:22] Thanks For Listening!

[00:58:22] **Adam:** but before we get out of here, let me give you a quick reminder. Like I said earlier, our Discord is growing rapidly and we, have a great little community there.

[00:58:29] **Adam:** So I just wanted to give you a reminder it's free. It's open to everybody. You can just go to workingcode.dev/discord. you get to join up and be part of that community. we are always looking for your topics and your questions, and you can send those to us @WorkingCodePod on Twitter or Instagram, or you can send them. an email or a voice memo, which is easy to record on your phone to WorkingCodePod@gmail.com. That's going to do it for us this week. We'll catch you next week and until then.

[00:58:55] **Ben:** Remember folks, your heart matters even. Playing hooky in Barcelona. We'd love you, Tim. And we miss you.

## [00:59:04] Bloopers

[00:59:04] **Adam:** Yeah, man. Oh, an introspection. I used

[00:59:26] **Adam:** to.

[00:59:27] **Adam:** Okay, I'll go. I used think of myself. Wow. There must be a terrible lag. I used to think of myself. and now I think I might've lost what I was going to say.

[00:59:39] **Ben:** Sorry.

[00:59:39] **Adam:** No, it's fine. As I'm sure it wasn't that valuable, but an insight. Go ahead.

[00:59:43] **Ben:** I didn't even remember.

[00:59:45] **Adam:** You

[00:59:46] **Adam:** forgot to,
