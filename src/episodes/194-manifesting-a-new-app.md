---
title: "194: Manifesting a New App"
description: "In this week's episode, Adam consults with Carol and Tim about various aspects and challenges involved in the development of an app intended to streamline and digitize the process of organizing skydiving jumps."
date: 2024-09-04
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/194-manifesting-a-new-app/id1544142288?i=1000668309630"></iframe>

In this week's episode, Adam consults with Carol and Tim about various aspects and challenges involved in the development of an app intended to streamline and digitize the process of organizing skydiving jumps.

They discuss overcoming technical difficulties, such as integrating drag-and-drop functionalities, managing data efficiently, and incorporating features like login systems, billing, and user authentication. They also explore potential UI/UX improvements, including touch interface adaptations and notifications for jumpers.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/194-manifesting-a-new-app.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** Things should be able to just slide around without me having to make selections and making changes. I should just put them where I want them.

[00:00:07] **Adam:** Yeah. I mean, I agree with you. It just feels like I'm being pulled in a bunch of different directions by my brain at once, and I need to I feel like I need to go drink, like, four Mountain Dews so I can focus.

[00:00:19] **Carol:** So I,

[00:00:19] **Adam:** pick a thing and work on it.

## [00:00:21] Intro

[00:00:21] **Adam:** Okay, here we go to show number 194. And on today's show, we are going to talk about my app that I'm working on. just figure I've got a captive audience here with Carol and Tim. And so I'm going to just kind of talk about where my little side project is at and get some, maybe some thoughts and some advice on how to work through some of these challenges.

[00:01:00] **Adam:** Maybe what I should work on next.

[00:01:01] **Carol:** I hear free consulting. Is

[00:01:03] **Adam:** Yeah. Yeah. Yeah,

[00:01:05] **Tim:** yeah, yeah. Okay.

[00:01:06] **Adam:** Why else would I invite you guys to be on my podcast?

[00:01:09] **Carol:** Yeah.

[00:01:10] **Tim:** Get what you pay for.

[00:01:12] **Adam:** so, but before we do that, as usual, we'll start with our triumphs and fails. Ben couldn't make it tonight. He's out partying, with all of his other extrovert friends,

[00:01:20] **Tim:** That's not true. You know, that's not true. He's at

[00:01:24] **Carol:** at a meetup. He's too cool to have friends.

[00:01:30] **Adam:** that means that Carol, you're going to start us off. What do you got going on?

## [00:01:33] Carol's Triumph and Fail

[00:01:33] **Carol:** Yeah, so I think I've got a both. Can I have a both? It's not allowed this week. I think I've earned it. Yeah. So a failure is that I'm just kind of missing the known. So I miss back home. I miss my friends being promoted to this new role. I miss being able to say, Oh, I know that. If I were working with Tim and someone asked me a question, I'd be like, oh heck, I know that.

[00:01:57] **Carol:** Here you go. Here's where it is.

[00:01:59] **Tim:** Yeah. You've had a lot of change in your last, last few years.

[00:02:02] **Carol:** yeah, a lot, right? So now I'm getting tagged with the, hey, what about this? And I'm going, I don't know our build process. I don't know what our pipelines look like. Like, I've never used GitHub Actions. And now all of a sudden, I am way outside my comfort zone, having to learn.

[00:02:21] **Carol:** And make decisions at the same time and to make my tummy a little rumbly,

[00:02:27] **Tim:** I bet.

[00:02:27] **Carol:** being honest,

[00:02:28] **Carol:** but overall, like I'm loving my new role. I'm loving the challenge and I'm loving the ability to just kind of step outside my comfort zone and learn. So I will say that like, that's a positive, right?

[00:02:39] **Adam:** Yeah, you are. And I know you're far away from home and everything, but like, how do you like Texas and the part of it that you're in the, the, the weather and, uh,

[00:02:50] **Carol:** It's not home.

[00:02:51] **Adam:** yeah. Oh,

[00:02:55] **Carol:** me get my triumph first. That might help you. This morning was the first morning I went outside and there was spa, there was like steam coming off my spa, like spa and hot tub, right? So it was like 68 degrees. I got in the hot tub before the sun came up. It felt nice. It's been 106 every day.

[00:03:12] **Carol:** There's no humidity. My, my like skin and hair doesn't understand how to function in this weather. Like they've been trained to react to humidity and my hair's like, what do you mean there's no humidity? I'm just going to break off your head then. Cause clearly that's what it's supposed to do when there's no humidity.

[00:03:30] **Carol:** So it's been a learning curve for my entire body to understand what it looks like to live in Texas. So, I've not adjusted to Texas very well, and I'm ready to leave it, but I will stay here as long as the army requires us to be here.

[00:03:44] **Tim:** I'm sorry. You can come visit anytime you want,

[00:03:47] **Carol:** Thank you. Thank you. Yeah. I'm planning a few trips back currently.

[00:03:51] **Tim:** man. Yeah. I mean, I mean, that's, that's such a cycle in life. You think about these cycles of chaos and order, right? So things sort of start out, you know, in life and very chaotic. And then you, you slowly start to learn and then you create order. And then sometimes at some point in your life, that order starts to get a little bit boring.

[00:04:13] **Tim:** So you shake things up and, and now it's chaos again. It's like, I think about like, I'm not a car guy, right? I, I, you know, I have a truck and I've, you know, restored it. I did that by paying people, but it's like, if you're driving and all of a sudden your vehicle breaks down and you realize I have no clue. This thing that I've relied upon, it was so orderly, it was working so well. And now I lift the hood and I see there's all this complexity and all this chaos and I understand nothing. And it's like, so you go, you go through these cycles of order and chaos. And so, yeah, you're in the chaos phase, but you know, at one point you were there earlier in your career and things were chaotic and it has a beginning, it'll have an end.

[00:04:53] **Carol:** Yeah. I just keep looking back to the times when things were chaotic, and I figured it out, and I learned, and I was able to answer the an I was able, sorry, I was able to like answer the questions. Going forward, and I hope that with all of this chaos right now, that in the future, when the questions are coming at me again, I'm able to go, okay, this time I know. This time I can say with certainty, here is the why and here's the how.

[00:05:22] **Tim:** And I have no doubt you get there.

[00:05:24] **Carol:** Thanks. All right. So what about you, Tim? What you got?

[00:05:27]

## [00:05:27] Tim's Fail

[00:05:27] **Tim:** well, it's a, it's a failure just in the fact that it, you know, scares me and it kind of affects my work and my team and my personal life. So one of the members of my team unexpectedly had a heart attack and had to have bypass surgery this week. And so it was. It was completely out of the blue, completely unexpected.

[00:05:49] **Tim:** And it just, just kind of, you know, you think about that, they're the same age as I am roughly. And you just think about that. It's like, you know, nothing is guaranteed, man. Nothing is guaranteed. You think you think you're good. And all of a sudden this chaos we're talking earlier, Carol, this chaos comes out of the chaos could be in your own body, right.

[00:06:09] **Tim:** Or your family or, you know, something we've all experienced. Always talk about the proverbial getting hit by the truck, but you know, what about having the heart attack? And now it's like, you know, I'm, I'm sure they're going to be fine. They're going to recover, but it's like, it's going to be a process, right?

[00:06:24] **Tim:** And so our T, we have to adjust and he has to adjust to a new life. And so it's just, it's, got me thinking about my own mortality. Let's put it that way.

[00:06:33] **Carol:** That's never fun.

[00:06:35] **Tim:** No, no. So, yeah, so been thinking about them a lot, you know, keeping in touch with them, letting them know we're there to support them.make sure that, you know, we, we as a company do whatever we can to support them and, and, the, the, you know, we'll keep the lights on while, while they recover.

[00:06:53] **Tim:** So,

[00:06:53] **Carol:** So this is probably a really bad question to ask. I've always had the feeling that if I just dropped off, that things would cease to function for a very small amount of time, but then they would revamp. To write back where they were. Like people would pick up with where things were missing. And have you seen that with a big part of your team kind of having to just be gone now that the rest of the team is recovering from it and that they're doing what they're supposed to do, which is cover for their teammate?

[00:07:24] **Tim:** I mean, we'll have to wait and see. There was, there was some kind of deliverables that may have to slide a month.but as far as anything catastrophic, as far as like coverage, I don't, I don't see a problem, but sort of, sort of new work going on can be, Could be a little bit of an issue. So, yeah,

[00:07:44] **Carol:** Well, I hate that.

[00:07:46] **Tim:** I just, I just hope they get well soon. How about you, Adam? Bring us out of this morass of chaos.

[00:07:53] **Carol:** do.

[00:07:55] **Adam:** I know this is a wild idea. So just please give me a little bit of leverage here, or a little bit of, of, not, not leverage, whatever the word is, a little bit of,

[00:08:03] **Carol:** Leeway.

[00:08:04] **Tim:** Leeway.

[00:08:05] **Adam:** Thank you. That's a

[00:08:05] **Carol:** Mm hmm.

[00:08:06] **Adam:** But I have something that I want to bring to the podcast. And it's a technical topic. I'm sorry, you know, to put it on topic here, but

[00:08:12] **Tim:** Oh, wow.

## [00:08:15] Adam's Triumph

[00:08:15] **Adam:** so I have a triumph.

[00:08:17] **Adam:** And that is that we had a page for one particular customer, right? So our application is on its way to becoming multi tenant. It's multi tenant in, as far as the Git repository is aware of, but it's you know, separate installations. And so we have this one customer with a buttload of data and only for them because they have all the, all their data, we had a dashboard page that was taking like two minutes to load.

[00:08:43] **Adam:** Like the, the, the sort of the entry page to this one module, which was unacceptable, right? It's crazy. And so it's our, our email marketing module. It's about sending emails and tracking how they're performing and that sort of thing. and it's, I mean, it's. Legitimately got a few less than perfect ideas in there, but I'm going to say like, maybe we're 50 percent to blame for slightly naive coding and they're 50 percent to blame for sending 73 emails in the last 14 days, to,

[00:09:17] **Carol:** Yeah. 73 emails doesn't sound like a lot of emails.

[00:09:20] **Adam:** well, so that's not 73 recipients. That is 73 messages, each of which is going to somewhere between, you know, 5, 000 and 300, 000 people.

[00:09:30] **Carol:** Oh, okay.

[00:09:32] **Adam:** Yeah, yeah, yeah. And. And many of those emails are going to the same people, right? So like they have a weekly newsletter and that's going to pretty much everybody, right?

[00:09:41] **Adam:** And then they'll have maybe appeals for making a donation before the fiscal year ends or something like that. Right? And so as a, as a constituent of this organization, as an alumni or whatever, you might, in the last 14 days, you might have gotten of these 73 different messages that they sent out. You might've gotten 30 of them.

[00:10:03] **Adam:** 40 of them. And we've been on them for years about like, this is just not a healthy program.

[00:10:11] **Carol:** No. Mm

[00:10:12] **Adam:** know, you were going to

[00:10:13] **Carol:** when I block you.

[00:10:14] **Adam:** yeah, yeah, exactly. this is almost as many emails as I've been getting from the, the Harris Walls campaign. This is ridiculous.

[00:10:20] **Carol:** Yeah.

[00:10:22] **Adam:** so, you know, like I said, it's, we take some responsibility here.

[00:10:27] **Adam:** You know, everything, my, my approach to coding in general is do it naively first. Right. Do the easy thing. Just, you know, you don't have to worry about like, are, is there going to be terabytes of data that you're going to have to sift through? Because 99 percent of the time, there's not going to be that much data.

[00:10:41] **Adam:** And then when you hit that performance issue, then you make it smarter and better and more efficient. And so we did hit that issue. So I took this page that was like somewhere between a minute and a half to two minutes to render, to like gather all the data,

[00:10:53] **Tim:** So it's a, it's a page. Is it also sending emails?

[00:10:56] **Adam:** no, no, no. This was just like the, let's, here's an overview of the last two weeks and the next two weeks all on one page,

[00:11:03] **Tim:** Okay. So it's like a consult consolidation of different,

[00:11:06] **Adam:** Right. And so, right. So they sent out, they sent 73 messages to their different audiences over the last 14 days. and so when, when we, it's aggregating data about like how many opens they had, how many clicks they had, how many people reported them as spam, how many people, all these different things.

[00:11:23] **Adam:** And then we, I need the numbers per message and I need the like aggregate over the two weeks. And so when each of those things, right? So I have, I have a table where we track, okay, Tim opened this message. Carol clicked a link in this message,

[00:11:36] **Carol:** And said you were spam for sending me 30 messages.

[00:11:40] **Adam:** Those are in there too, right? And so, the, for those 73 messages 14 days, there was, 700, 000 activity records that I had to sift through just for like the last 14 days for those particular messages.

[00:11:53] **Adam:** to generate that one page. And the problem is we were doing all of that, you know, real time, right? Every

[00:11:57] **Carol:** yeah. On the fly.

[00:11:59] **Adam:** There was, there was some caching of the queries there, but it was like, you know, cache it for five minutes so that if they refresh the page, then it doesn't have to redo that, but so, we, we had some roll up, jobs running that would like aggregate this data, every couple of hours and timestamp it so that, you know, at least if it takes that roll up job, two minutes to run or five minutes to run, who cares, right?

[00:12:23] **Adam:** It's just reading data and pushing some aggregate data into the database. And then I can query that and display it. And I got the, so this was a 90 seconds to two minutes. render time for this page, most of which was querying the database. I got that down to like around two seconds on average and mostly down to less than one second by just changing that all over to use that aggregate table.

[00:12:45] **Carol:** Holy moly. That's a huge win.

[00:12:48] **Tim:** So do you have to run like benchmarking, like on a regular basis to get that aggregate table updated?

[00:12:53] **Adam:** I don't know what you mean necessarily by benchmarking, but we do have a job that runs like every two or three hours. That's just like, okay, let me look at the last 14 days on a rolling basis. Like

[00:13:02] **Carol:** Keep it going.

[00:13:03] **Adam:** that I'm querying. That I have activity for over the last two weeks. Okay. These, those are all the message IDs.

[00:13:07] **Adam:** So now I, now that I have the list of messages that I care about, let me update the stats for all of them.

[00:13:12] **Tim:** Got you. Okay.

[00:13:14] **Adam:** so, you know, big win. certainly, I mean,it's pretty bad when the page takes so long to render that the app server is just like, nah,

[00:13:23] **Carol:** Yeah.

[00:13:24] **Adam:** gonna, I'm just gonna return nothing,

[00:13:26] **Carol:** Yeah. I feel like our, I feel like our SQL timeouts had 30 seconds.

[00:13:30] **Adam:** could

[00:13:30] **Carol:** So like if we don't get, like in my application, if we don't get data back in 30 seconds, we assume there's a problem and we're timing out that query and you're done, so

[00:13:40] **Adam:** and that's the problem. It's like, you know, I've got these jobs that I need to run for five minutes, to do their thing, to do the aggregation. So I need. To not have it like a global setting, 30 seconds or whatever, but, I would prefer to have that for like user facing pages, for sure.

[00:13:57] **Carol:** for sure. Yeah. Geez, well, congratulations. That's awesome. I'm glad that you're winning when we're failing.

[00:14:04] **Adam:** And that, you know, kind of going to the, something we were talking about before we started recording, which was like, getting the opportunity to code every now and then is nice too.

[00:14:14] **Carol:** Yeah. That's going to be a challenge with my new role. I'm seeing that now. Yeah.

[00:14:19] **Adam:** Yeah.

[00:14:20] **Carol:** Yeah. Already. And that even though like, like a message came out that was like, Oh, if you had architects that don't code, then we could just give them access to all these security views and all of the reports from security, but since they have access to the code, we can't give them access to security reporting because they can change the code.

[00:14:38] **Carol:** I'm like, seriously, just let me build great processes.

[00:14:42] **Adam:** So, I mean, how are you supposed to fix problems if you can't get a listing of what the problems are? Is there supposed to be like some sort of separation there?

[00:14:51] **Carol:** Yeah, there's supposed to be separations in our ISO. So our security team has to aggregate the problems. They then have to deliver it to me. Then I have to build a report and I have to build stories off of what those issues look like, make the adjustments with my team, make the fixes. But in reality, We just like, part of this week is we're migrating from on prem to GitHub Cloud Enterprise.

[00:15:14] **Carol:** So in there we have like, CodeQL. CodeQL is spitting back all of these security warnings. Like if I could just go in there, I could already add the stories, have them fixed before security even needs to review it. So they're looking at making changes to allow for some of that. But it was the whole like, if your architects don't write code, then we can give them access.

[00:15:33] **Adam:** But I mean, all it sounds like all they're asking is to make more bureaucracy because they like, okay, let's create more jobs where people can't do the work

[00:15:44] **Carol:** Do you want to know where your taxpayer dollars go?

[00:15:46] **Tim:** Government, baby.

[00:15:49] **Carol:** Yeah, no, we, we constantly say that. Like I will say that on my side of the house and where we're at, there is constantly this, communication that we send in, in a group chat that's like, where are, where, where are the taxpayer dollars going and that does this make sense?

[00:16:06] **Carol:** Does this process at all add up? If not, let's not do it. Like, let's make a way to make sense. Let's be some, like, let's be an efficient company here. I

[00:16:16] **Tim:** And is it even more secure, right? I mean, you're treating your architects as if they're a risk, you know, these people have been clearanced and I'm sure they're monitoring them and, and, and there's code reviews and things. I mean, it's not necessarily making the code any better or safer or more secure.

[00:16:33] **Tim:** It's just adding layers of friction where people can't, can't get their work done.

[00:16:38] **Carol:** I even asked for read only access. Like, can I get read only access to the reports so that I can build stories in our, like, an ADO to be like, hey, let's go work on these things to get them done. The answer was currently no, but we'll ask again. we'll, we'll get through it. We'll get through

[00:16:55] **Adam:** I, I could never work for the government. Bless you for, for doing that, Carol.

[00:16:59] **Carol:** Pension, baby. Pension. Yeah.

[00:17:01] **Adam:** Hopefully. right. Well then, let's, let's move on.

## [00:17:05] Adam's App

[00:17:05] **Adam:** I, I thought we would talk about, you know, we're going to, I'm going to get my, my pound of flesh from you guys today, my, my application. it's a Svelte app, surprising everybody, I'm sure.

[00:17:14] **Tim:** You could take the pound that's right around my middle. Just, just, just take that pound.

[00:17:19] **Adam:** three or four,

[00:17:20] **Tim:** Yeah. Take more if you want. Yeah. That's

[00:17:21] **Adam:** Me too. but so let me, I guess explain what it is this app is trying to replace so that we kind of have a good, baseline here, right? So, this is for skydiving purposes. not to be used while you're in the air, obviously. It's like an organizational, data management type of application.

[00:17:41] **Adam:** So, for years and years, small clubs like mine have used what amounts to basically a piece of paper on a clipboard and you, when you want to make a jump, you walk up to the clipboard and you write your name down in a box, you know, the, so the, the plane can hold X number of people. And so you might get a group of people together and say, okay, the four of us want to go together and we're the whole plane load.

[00:18:04] **Adam:** Or you might just be like, okay, well, I want to make a jump and I don't have people to jump with, so I'm just going to put my name down and other people who are in a similar situation will put their names down and we will. Find out that we're together and we'll figure out what we're gonna do once we are all on the piece of paper. So we call that manifesting, right? So that's like kind of organizing, gathering groups of people together to make skydives. And, when you start to get to the point where you have two or three aircraft, and managing like, okay, well, when does this one need to get fuel? How many people fit on this plane versus how many people fit on that plane?

[00:18:41] **Adam:** You know, keeping track of where there's an open slot. If somebody decides, oh, I got to go, or the weather's too, you know, the wind is blowing too hard for me, so I'm not going to jump right now. So you can kind of all of a sudden find yourself with like a load right before it's going to take off, you go, wait a minute, we only have three people, we're supposed to have four people, right?

[00:19:00] **Adam:** Like why, why is there only three on this load? Because people just don't realize that somebody has, we call it scratching, has scratched their name off of the clipboard, right?

[00:19:10] **Carol:** Scratching like when you like, what is it called when you're playing pool and the white ball goes in the hole

[00:19:16] **Adam:** That is called scratching.

[00:19:17] **Carol:** start out, yeah, yeah, you scratch me.

[00:19:19] **Adam:** Yeah, so, I mean, it's called scratching because you were, you know, in the old days, you would walk up to the clipboard, which is hanging on the wall, and you'd scratch your name off the list. Like, I'm not jumping right now. So, right. So that's the, that's kind of the, context for this thing.

[00:19:33] **Tim:** The problem, the problem we're trying to solve. A better way to organize these jumps. So

[00:19:37] **Adam:** right. So, if you could take that clipboard and make that into a digital app, what things would make that better, right? So, right off the bat, you can have. by making it digital, you can make it easy to move things around by doing drag and drop. Right. you can, you can allow people to like sign up on their phone.

[00:19:57] **Adam:** Instead of everybody having to like get in line behind the clipboard, you can just like pull it up on your phone, select which load do you want to get on, gather your group of friends or whatever sort of thing. And so there's opportunities there. and then like keeping track of the status of the planes, right?

[00:20:12] **Adam:** So if you. The person running, like, this is like a paid job basically for somebody to sit there and keep track of all this data and keep the drop zone running smoothly throughout the day so that you need to have sort of an admin view for somebody who is managing the data and then you want a separate view for people who are just like, just show me the current status of things.

[00:20:32] **Adam:** I want to get on a load what's available to me sort of thing.and then there's also things like, okay, so at the end of the day, I want to know how many jumps did I make, so I know how much money I owe, and I can bring the right amount of money with me up to pay at the end of the day, or stuff like that.

[00:20:45] **Adam:** and then, you know, when you, when you would sign up on the clipboard, not only would you write down, okay, I, this is my name, I'm gonna go make a jump, but you would typically put in, like, I'm, going to this altitude, right? So. Not everybody all the way, not everybody always goes all the way up to full altitude, which at my drop zone is usually 10, 000 feet.

[00:21:04] **Adam:** Some places go higher.sometimes people will just get out at 5, 000 feet, make a quick, we call it a hop and pop. You just get out of the airplane, wait a couple seconds and deploy your parachute because you're pretty much just doing it for the canopy ride at that point. Not so much for the free fall. So there's all these little details to keep track of, right? And, and when you are

[00:21:24] **Tim:** I've learned so much about skydivings.

[00:21:26] **Carol:** I know, right?

[00:21:26] **Tim:** being on this podcast with you.

[00:21:28] **Carol:** have a page of notes of just about skydiving things. Not even the problem yet.

[00:21:34] **Adam:** So, yeah. And then I guess the one last thing that comes to mind is, so not only do you write down your altitude that you're going to, but typically, especially when you get into larger airplanes that can hold more people, when you've got more people in the sky at the same time, it is more important to know what everybody else on the plane is doing so that you can organize because you would think everybody just gets out and you fall straight down and so it doesn't really matter.

[00:21:59] **Adam:** what order people get in and out, right? But it does matter because you don't just fall straight down. You know, depending on what you're doing, you might be moving significant, right? Think about like, you know, people that fly wingsuits, right? They can travel a ton of distance and then you can, you can do the same thing to a lesser extent without a wingsuit, right?

[00:22:18] **Adam:** You can travel maybe a third or a quarter of the distance, which is still a significant distance. And so you could theoretically fly under another jumper. and then they fall on you and kill you sort of thing. So it's important to know where other people are in this guy, what they're doing. So all of that is like details that need to be kind of tracked in this application.

[00:22:35] **Adam:** And I want to have like a, sort of a public view that you wouldn't mind, like even just sharing publicly, like put it on your, on your drop zone website. So people can see what's going on for the day. And I want to have like a manifest worker view where you get all the tools to say, okay, this load is currently airborne and it's going to need fuel before it goes up again.

[00:22:55] **Adam:** And, you know, can they're the ones that can do the drag and drop of moving people around that sort of thing.and so what I've done so far, and I sent Carol and Tim some links to look at these things. I've, what I've got so far is Designed primarily to fit like a iPad mini because that's what we use personally.

[00:23:13] **Adam:** right now.so it's responsive design, and it's, it's all right. I, you know, there's things about it that I like things that I don't like, but basically you've got boxes, that, that represent an airplane lift and then it's got details inside about. Details about that lift inside the box, right? So it's gets you the, the plane tail number, the status, right?

[00:23:32] **Adam:** Is it full or does there, is there open seats? Does it need fuel? Who's on the plane? What are the groups? And what's everybody doing? Like what's their altitude and what discipline are they doing?and this part, I feel like I pretty much have down. The, the data moving around is not, I haven't done any of that, right?

[00:23:52] **Adam:** Like the, the interfaces that I showed you guys, these are hard coded.

[00:23:55] **Carol:** Ah, okay. Okay.

[00:23:57] **Adam:** yeah, I, I mean, the, the manifest one, you can actually do some stuff. I don't remember. I, at one point I was messing around with a drag and drop library, and I ultimately decided to pull it out just because I felt like with the touchscreen, interface, it was going to be too. You know what? I'm not even sure. Yeah. Okay. So it does look like I did deploy it after I took that stuff out. with the touchscreen interface, it was just too There need The drag and drop stuff was okay, but then there's more that I want to add where like you can tap a name and that'll give you information about like how many times has that person jumped today and that sort of stuff.

[00:24:33] **Adam:** And it just felt like it's starting to put too much in one little area of space and it's going to become, you know, one of those apps where you're like, okay, I need to move my, my big fat meat finger over by one pixel and try again. and that's always

[00:24:47] **Carol:** Those are never fun.

[00:24:49] **Adam:** Right. So it's about like trying to find an interface that works on touchscreens and also on computers.

[00:24:58] **Adam:** Cause I'm sure like, ideally I'd love to, to like license this out and let other drop zones use it and make a little bit of money to pay for my own jumps. That would be great.but yeah, I don't know. I'm just like, I'm at that stage now where like, I've kind of, I've built the data model, right? it's, this is all, yeah, actually.

[00:25:16] **Adam:** So I do have the data model and that's done and I'm just kind of like mirroring it. I have a, like, it's a TypeScript thing. And so I just have like a TypeScript file that has like, here's the current status of the day, right? These are the loads. These are the people that are on, and it, and it displays based on that.

[00:25:32] **Adam:** And I don't have that hooked up to the database. And I'm, I'm just feeling a little stuck, right? Like there are things that I know I need to do that I haven't touched. And there are things that I know I need to do that, are adjacent to the things that I'm working on or that I have here that I just like, I need to figure out. Next steps.

[00:25:52] **Carol:** So, can I ask a few questions? Please,

[00:25:55] **Adam:** That's not, yeah, go ahead.

[00:25:56] **Tim:** okay. Short show.

[00:25:57] **Carol:** Yeah. Right. We're done after show, right? So when a load goes up, do they only drop at one altitude or can it take say 20 people up and five of them are dropping at 5, 000 and the rest are dropping at 10, 000 or is it one load is you're all going together?

[00:26:15] **Adam:** Typically at a small drop zone like ours, you might go to two different altitudes, right? So it's, it's inefficient to fly. So our planes, we have three planes, two of which hold four jumpers, one holds six jumpers. and so it's, It's, it would be inefficient to go, okay, we're going to drop at 4, 000 feet and at 6, 000 feet and at 10, 000 feet.

[00:26:36] **Adam:** Like if, if that were, if that's what people wanted to do, we would have a conversation and either the people going out at four and six would both get out at five as a compromise or, everybody, you know, they would just decide like, okay, we need to minimize the, we call them passes, right? So like the airplane flying over the airport, we need to go to one altitude.

[00:26:56] **Adam:** Let some people get out, go to the next altitude, let people get out, and then the plane needs to land. so does that answer your question?

[00:27:02] **Carol:** it does. It does. So it means that picking a load wouldn't necessarily mean that I have to go to that so I could pick up a flight based off my altitude and I could have like multiple sets of people in that load, correct?

[00:27:16] **Adam:** Typically you are going to want the next available load, in general, right? So I don't, I'm not going to pick a load that's three hours out just because it's going to the altitude that I want to go to. I'm going to say I want the next available load. And we will compromise it. Like if we can't agree on what the altitudes are, but generally, generally people are going to want to get out at like four or five or 10, or like full altitude.

[00:27:40] **Adam:** So,

[00:27:41] **Carol:** Is there, is there an option to add by experience? So you don't have five people trying to jump who is their very first time jumping versus like jumping alone versus I only want to allow two people who've never jumped alone and we want to move them to the next load if not

[00:27:58] **Adam:** so

[00:28:00] **Carol:** can probably add headache, right?

[00:28:02] **Adam:** yeah, I mean, there's, there is an element of that to the process, but I don't think that needs to be done in the app, right? So for people that are not licensed yet, that, so in order to get your, we call it your A license, it's your first license. you have to have. That is permission to jump by yourself.

[00:28:19] **Adam:** Yeah. you have to have a minimum of 25 jumps and you have to have done a whole bunch of, practical skills in the sky. And you have to have passed a written exam.and you have to have taken a first jump course, which is several hours of ground school.And so we kind of managed that process very hands on already.

[00:28:38] **Adam:** And so like for those people that are jumping with an instructor or whatever, like the, they typically your instructor will manifest you well, while you're a student, right? You they'll say, okay, I'm going to go take Carol up. She's my student right now. This is the altitude that we're going to go to. This is the discipline we're going to do.

[00:28:54] **Adam:** and that's,

[00:28:55] **Tim:** like Super Grover and Tuttle. They're doing a tandem.

[00:28:58] **Carol:** Yeah. Yeah.

[00:28:58] **Adam:** Yeah. So,yeah. So I am a tandem instructor. Among other things, and so when I take up a tandem student, typically I will go, I mean, Dropzone does this for me. That's a little bit of how it works. So like they'll say, okay, Adam is going to take this student and this is going to be the video guy, right?

[00:29:15] **Adam:** And so that's kind of makes it a group of us three people.and then they might move us from load to load, but they're going to keep the three of us together, until we go up.And then, but, but manifest is kind of in control of that. It's very similar with students, except that's more up to the instructors.

[00:29:31] **Carol:** Yeah. I guess for me, if I were brand new walking up, like I wouldn't want to write my name on a, on a clipboard full of people who had never done this before either. Right? Like I would want to make sure like it's pretty balanced. So I would want to know half of you have been doing this a while and I'm not going to crash into you.

[00:29:50] **Carol:** And if you see me crashing into you, you're going to know how to prevent it. Right?

[00:29:54] **Adam:** you're, you're thinking the right, you're thinking the right things, but, as like, that's just something we tend to manage on our own as the people jumping. Right. Yeah. So we go, okay,

[00:30:04] **Tim:** you got a lot of downtime, I imagine. You're sitting there waiting, and there's probably a lot of, Hey, it's my first time. And they're like, Oh, okay. Well, you know, these guys are experienced. You should probably go with them.

[00:30:12] **Carol:** Yeah. We don't want all five of you going together.

[00:30:15] **Tim:** Yeah. But you don't probably don't want a rating system where people are like, what do you mean?

[00:30:18] **Tim:** You know,

[00:30:20] **Adam:** Yeah. Yeah. Tim, he sucks. Don't jump with him.

[00:30:23] **Carol:** don't put Tim, he is an Tim gets a plane to his self.

[00:30:26] **Tim:** That's right.

[00:30:28]

## [00:30:28] The TO DO List

[00:30:28] **Adam:** So, yeah. the, I guess, so let me throw out some things that are on my mind in terms of

[00:30:32] **Tim:** Yeah. That's, that's kinda what I was wondering what I mean, like, so, I mean, where do you see this? I mean, the, the mockup is nice. It looks good. You got a nice public screen. You got a nice manifest screen. So I, I, I, I don't know what you're struggling with here. 'cause it, I mean, so far it's looking good.

[00:30:47] **Adam:** Yeah. so,things that I guess. Are maybe the things that are, I haven't even gotten anywhere close yet. These are probably on my mind and kind of, distracting me maybe, right? So I have not touched anything with like authentication yet. Like I just sent you guys these URLs and you can see them, right?

[00:31:05] **Adam:** It's treating you as if you are the manifest person. That's easy enough. Yeah, yeah.no sign up, no, no charging, right? So

[00:31:13] **Tim:** not a problem unique to, to your app, right?

[00:31:16] **Adam:** no, but it's just, it, it's not, but so I guess the, what I'm thinking though is like the whole, like, okay, I log in, it identifies who I am, what drop zone I'm looking at, pulls that specific set of data out of the database and displays that for me, right? That's, that's kind of like one flow. That I haven't touched yet.

[00:31:35] **Tim:** Right. I've just got like you, you load the page. It goes, okay, this is the hard coded data display it. so that's like one, thing that I'm, is on my mind. Then there's the whole like, sign up and billing piece.Money's important.

[00:31:48] **Adam:** yeah. I want to do. So we talked a little bit about author. I'm kind of thinking I want to do, magic link based login.

[00:31:57] **Adam:** Like I don't want to have to deal with passwords and all that crap. Like just you put in your email address, excuse me, you just put in your email address and, and it'll email you a link to sign in and it's like a magic link. And then it'll, I'm thinking maybe it'll stuff something in local storage. Or a cookie,

[00:32:16] **Carol:** does. Yep.

[00:32:17] **Adam:** either one.

[00:32:18] **Adam:** and that way when you come back, you're already logged in. And if you do happen to get signed out, or if you're on a new phone, new computer, whatever, you just send your email address and

[00:32:26] **Tim:** Here's what I mean. Here's the reason why I'm kind of poo pooing, like working on off next. It's just, it's not unique to your. Use case here, right? You have a use case. You've done all the stuff you've done so far is super unique to what you're trying to, the problem you're trying to solve. Auth is just auth.

[00:32:42] **Tim:** I mean, you know, it doesn't, yeah, cool. It might be cool to do that, but it's like, finish getting like the stuff unique to your problem and then work, worry about all the stuff that's just kind of generic, like reporting. Off, you know, if you, I don't know if you need to have like some sort of auditing to make, you know, when people make changes for the insurance, when you guys hit the ground and go swat.

[00:33:03] **Tim:** So work, work on the unique thing to your app and get that done. You see what I'm saying?

[00:33:12] **Adam:** Yeah. No, and that's a really good point. So that makes me think of, you know, I told you I, I had put in the drag and drop thing and that was working, but then I just felt like it was not the right solution. Right? So like it works, but then it kind of gets in the way of other functionality I need to pack into that same, you know, Square rectangle of space, right?

[00:33:31] **Adam:** I kind of want you to be able to tap on the name and like, you know, highlight all of your jumps or go to a report of your stuff or, or, or something. and

[00:33:40] **Tim:** That's unique to your, your situation. So work on that, work on that first.

[00:33:44] **Adam:** So let me ask you this. If drag and drop is not an option, let's just say like, it's too kludgy on a touch interface. You know, like it works okay for Trello, but just the, the, the Lego bricks that would make it, you know, Easy for me to implement.

[00:33:59] **Adam:** Don't make me, doesn't give me the exact interface that I want. Right. So let's just say I'm going to, I'm going to poo poo, drag and drop completely. What kind of interface when you're looking at this, would you expect when trying to move a person or a group of people? So you can kind of see how like in some of the boxes, some of the load boxes, there are groups of people that are kind of in a similar dark box, like a gray box, together.

[00:34:27] **Adam:** with space between the groups. So like, I, and you, right now you can see there's like little drag handles is what I'm thinking of them as. Those are just like groups of dots to the left of the group and to the left of each person's name

[00:34:37] **Carol:** hope our listeners can visualize all of this.

[00:34:39] **Adam:** yeah, I know it's, it's

[00:34:41] **Tim:** you got to post a, you have to post a picture here. I, I'm, I'm gonna be, I don't know. What do you think, Carol? I'm thinking the way you've designed it so far, it looks like you had from the very beginning, drag and drop in mind. And I, and I can't, I can't imagine it.

[00:34:55] **Carol:** Yeah, for our listeners who can't see what Adam's designed so far, when I opened this and I looked at the first thing I saw, I thought was Trello, a list of Trello like cards and Trello like slots on top of another list. So it just kind of keeps repeating. So it says Trello, like each like phase taking up a whole row or a whole slot on your screen.

[00:35:16] **Carol:** There's like multiple rows of Trello cards. And, and like, I don't know what the swim lanes, I don't know if they're called in Trello, but where you can move them around. Yeah.

[00:35:25] **Adam:** They're all blists, yeah.

[00:35:26] **Tim:** Yeah. And I can't, I don't know, I can't visualize what it is you want to add to this that makes this more kludgy. I mean, the way it looks now, I'm like, I'm, I'm trying to touch, I'm actually grabbing my mouse. I'm trying to

[00:35:40] **Carol:** I have to.

[00:35:41] **Tim:** around. I've been trying to, yeah, I've been trying to slide things around it.

[00:35:43] **Tim:** Cause I mean, that's just the intuitive thing to do. You might want to add other stuff. Maybe the, maybe the challenge is finding a different way to add those features without. Kludging up what you already have here or coming up with a completely different paradigm for displaying this.

[00:35:59] **Carol:** yeah, it's one of those things where, like, we use software in a way, right? Like we all have those habits and we have those tendencies that come with how we use software. And when I look at this, I automatically assume I can drag and drop things. It's just because of how it's laid out and because I have the dot, dot, dot next to the names.

[00:36:21] **Carol:** Things should be able to just slide around without me having to make selections and making changes. I should just put them where I want them.

[00:36:29] **Adam:** Yeah. I mean, I agree with you. It just feels like I'm being pulled in a bunch of different directions by my brain at once, and I need to I feel like I need to go drink, like, four Mountain Dews so I can focus.

[00:36:41] **Carol:** So I,

[00:36:42] **Adam:** pick a thing and work on it.

[00:36:43] **Tim:** Yeah.

[00:36:44] **Carol:** for me, I need to circle back to one question I wrote down. Like, is this, is the use case for this, the end user being the person jumping out of the plane? Are the, or is it the person coordinating the jumps?

[00:37:01] **Adam:** So it's intended to be sort of both, right? Except for students, right? Tandem students and solo students, they would be pretty much hands off. They would be able to like look up and see it on the wall and say, okay, that's, you know, they're calling for load, right? They're calling for load three now. I know I'm on load five, so I have 20 minutes and I can go to the bathroom, that

[00:37:20] **Carol:** Easy. Yep.

[00:37:21] **Adam:** but other than that, they would just be totally hands off. And then you're going to have like your experience jumper, It was going to be like, Oh, cool. They're going to look up on the screen and say, Oh, cool. There's, there's availability on load for there. So I'm going to take out my phone and I'm going to open up the website and I'm going to say, put me on load for,

[00:37:37] **Tim:** So,

[00:37:37] **Adam:** hopefully that's just a couple of clicks away.

[00:37:39] **Tim:** so you do sort of have some level of the students and experienced and there's

[00:37:43] **Carol:** There it is. Yeah,

[00:37:44] **Tim:** Yeah. So there is a little level of that, that you need to have to each. Attached to each user.

[00:37:50] **Carol:** I mean, tandem means you're attached to someone, right? So if I went on a tandem jump with you, I would literally be strapped to you. So I feel like you have to, account for that spot. Like I can't account for my own spot. I only can go where my jumper goes. Like that's where I have to go. But once I'm certified and can jump for myself, I can put my name in any slot.

[00:38:10] **Adam:** pretty much. Yeah. Yeah. and I'm sure that different organizations will operate slightly differently. This is just my experience at my club.

[00:38:19] **Carol:** Interesting. Okay.

[00:38:20] **Adam:** So

[00:38:21]

## [00:38:21] Thinking Through New Features

[00:38:21] **Carol:** You want to know where my tech brain goes?

[00:38:23] **Adam:** yeah, please.

[00:38:25] **Carol:** So some things I probably shouldn't know from being married to who I'm married to, but you should build in a fuel charts and how far your plane can actually go on path. And you could then determine the best altitude paths for each plane to determine where they should be flying to.

[00:38:44] **Carol:** And that way you only fly them at the right altitude and you put the right people at the right time and there's less guessing.

[00:38:52] **Adam:** That's, I mean, the way that you're talking about it is kind of like as if we were, as if the drop zone, we're saying, okay, Carol and Tim, you guys are jumping together because you make a good pair for weight and balance and fuel efficiency. That's not how it works at all.

[00:39:06] **Carol:** None of that's accounted for. Okay.

[00:39:08] **Adam:** No, because I, as, as a person, I'm coming to the drop zone.

[00:39:11] **Adam:** I am paying money to get out of this airplane. I'm going to do what I want to do. And the drop zone is just facilitating that. So I'm, I'm saying I'm going to go to this altitude and I'm willing to wait an hour to do it to get on a load that's going there or whatever, but this is what I'm doing. so it's, it's kind of a, it's a collaborative effort, right?

[00:39:28] **Adam:** The drop zone wants to send the planes up. The jumpers want to go do their thing. And you got to find that where you, you got to find the places where you can agree, right? Uh,and, and as long as the, the load is profitable, the drop zone doesn't care. The drop zone doesn't care if you send all hop and pops all day long because they price, you pay by what altitude you get out at

[00:39:48] **Tim:** Cause it costs more gas money.

[00:39:50] **Adam:** Right. It costs more gas to go higher. So the, to get out lower is a lower cost to make the jump. think of it like, you know, you went to a ski resort and you can buy a cheaper lift ticket, but it only ever takes you halfway up the mountain. Right. Right. But like, you, you

[00:40:06] **Tim:** bunny slope.

[00:40:08] **Adam:** so, yeah, so it, I get what you're saying about like, you can, you could try to like, learn about the different people and, and that sort of thing with fuel consumption and all that, but it's really, and the pilots, you know, this is a, this is a club.

[00:40:23] **Adam:** This is not a business that's trying to squeeze out every possible penny. This is a club that's just trying to make enough money to continue having fun. Right.

[00:40:32] **Tim:** And, and it, and they're not, I mean, it's not like the army where they're making sure they're optimizing the training of every single paratrooper that that's, it's going to hit the ground.

[00:40:40] **Carol:** Hey, what's about the page before this that lists everyone jumping for the day and their experience level so you connect to each other?

[00:40:48] **Adam:** Yeah, I like that. I, I had another thought too, and I, I just took it off the screen a couple of weeks ago, but, so one of the, one of the challenges, I think, at some drop zones is, you know, if you come up and you're a student and you're like, I don't know who to talk to, you know, how do I find out who's an instructor so that I can try to get somebody to take me up on a jump, um, pictures would be good, or,

[00:41:09] **Carol:** pictures.

[00:41:10] **Adam:** yeah, or even just like a list, like, okay, these are the instructors that are here today, right?

[00:41:15] **Adam:** They're, Like I can, maybe as an instructor, I could check into the drop zone for the day and say, I'm here and I'm willing to take students for the day. So it would put me on a list of like, okay, I'm willing to work with students today. The trouble is then like, you know, how does the student identify the person?

[00:41:32] **Adam:** The profile pictures would help with that. or, or

[00:41:36] **Carol:** Yeah. Yeah. Like LinkedIn with WhatsApp, right?

[00:41:40] **Adam:** Maybe, I don't know.

## [00:41:41] Integrating Payments

[00:41:41] **Adam:** The, I think in terms of integrations, the very first thing I'm going to have to do, we use, Square to do online booking for our tandems, right? So people will go online to our website and we'll say, click here to book your tandem, and it shows them like a calendar where they can pick a date.

[00:41:56] **Adam:** Cause we have so many slots available on certain days. Say, okay, there's available availability, you know, the second Tuesday of next week. and so they can click on that and say, well, I want to come in at noon and they can pay their deposit online. And then they are like in our square.you know, database or whatever.

[00:42:15] **Adam:** Right. So Square, Square, just like the, you know, remember a million years ago, you could get the little thing that plugged in

[00:42:21] **Tim:** the mayor.

[00:42:22] **Adam:** phones used to have a hole on them that you could plug in headphones to

[00:42:26] **Tim:** yeah. Yeah. Oh, you're talking about, you're talking about, okay.

[00:42:28] **Adam:** the Square reader, right? Yeah. So when Square, the, the company first came out there, one of their big things was like, they would for free send you a little thing, it was like a dongle and you could plug it into the headphone jack.

[00:42:39] **Adam:** And it was a card swipe. thing. It would read the magnetic stripe on the credit card and feed it into their app so that, you could like charge credit cards on your phone.so we have, their business has changed a lot since then.

[00:42:51] **Tim:** Yeah. Cause that wasn't PCI compliant.

[00:42:53] **Carol:** Yeah. Well,

[00:42:54] **Tim:** none of that was encrypted in transit, so they

[00:42:56] **Carol:** side, side tangent, I decided to have a yard sale one weekend many, many years ago and decided Square was the way I should take payment for people without cash. And exactly what Adam said, a package came to my house with a reader. I plugged in, downloaded the app and I could swipe anyone's credit card who wanted to hand it to me.

[00:43:18] **Tim:** great for

[00:43:19] **Adam:** nice. Well, you know what, Tim, my complaint about that whole, it's not PCI compliant thing is it's just right there in the magnetic stripe on the back of the card. All it's doing is reading what I've got sitting there, right? Like maybe they should think about encrypting the content of the card. Maybe the payment card industry should, should up their game instead of asking

[00:43:36] **Tim:** which is, which is why we have the chip now. So.

[00:43:38] **Adam:** Yeah. Well, and I'm not even going there. That's a, that's a whole nother show.

[00:43:43] **Carol:** New topic. Yeah. Yeah.

[00:43:47] **Adam:** So, so people sign up for their Tandems online, right? And so I need to make it easy for the person working Manifest at the drop zone. To go, okay, these are the people that signed up for Tandems today. Make it easy to go, okay, look, we have 15 Tandems scheduled. Let me go grab those names, pull them in, and I can start to put them out on loads.

[00:44:06] **Adam:** And move them around as necessary and start to assign them with a Tandem Instructor sort of thing.and, sure, it's easy enough for me to just like, open a box where they can type in the student's name. But then, if I have some sort of integration there, I might be able to find a way to like, Close the loop, market is complete or something in Square.

[00:44:22] **Adam:** So we have that because we do currently, we use Square for those registrations and we also use Square. To collect payments. Like at the end of the day, I go up and I say, okay, I made five jumps at full altitude today. What do I owe you? Okay. I owe you this much. Here's my credit card. And they, we do like all of our bookkeeping through that.

[00:44:40] **Adam:** Right. So we do that all day, every day. And then at the end of the day, we print out a report that's like, this is how much money we should have in cash. This is how much we should have in checks. This is how much we collected on credit cards. And it all goes in the bank bag. Just like if you're working at TCBY, right.

[00:44:54] **Adam:** That's a yoga place.

[00:44:55] **Tim:** Do those still exist?

[00:44:56] **Carol:** I don't know.

[00:44:57] **Tim:** know, they're, they're next to all the blockbusters. you,

[00:45:00] **Carol:** What's that tips? Sorry. You didn't say tips.

[00:45:03] **Adam:** What about them?

[00:45:04] **Carol:** So do you tip your tandem instructor?

[00:45:07] **Adam:** Some people do, but they usually just give me cash. yeah, I mean, I, I honestly, I don't know if it's ever come up at manifest. I should ask. I mean, it, it doesn't have any effect on my app because I'm the square would be like, where they would deal with all of that, but I guess it's possible that they could like choose to overpay in square with their credit card and then get cash from, get cash back that they then use to tip us.

[00:45:30] **Carol:** Yeah. I mean, in that case, it would be my payment is made associated to the jumper assigned to me. And my overpayment then goes to said jumper. Like said, I don't know if they're called, like what the actual name is, but my instructor, right? I never carried cash. So I always look at around here. It's really bad.

[00:45:49] **Carol:** I don't know why. Nowhere gives you a tip option when you run your credit card. Like they, you just sign, there is no option to put tip on it. So we go to restaurants. I'm like, we don't have cash. They can't get tips. I don't know why. Don't know what Texas does here or what here is, but we have to carry cash everywhere because we got.

[00:46:06] **Tim:** are you, you're on the border?

[00:46:08] **Carol:** We're on the border.

[00:46:09] **Tim:** There you go.

[00:46:09] **Carol:** They make everyone like, if I'm going to tip at dinner, I have to have cash to cover it because if I don't tell them ahead of time, they can't do it. Yeah.

[00:46:18] **Tim:** You're your, your server, your server is an unbanked person who doesn't have a

[00:46:22] **Carol:** Yeah.

[00:46:24] **Adam:** the, well, the place, I mean, listen, I live up in Pennsylvania. We're nowhere near any of the borders. I guess, unless you count the east coast of the United States, the border, but, there's an ocean there. and the place that I used to get my haircut was like, you could pay for your haircut with a credit card, but they, they would not allow you to do like cashback

[00:46:43] **Carol:** Yeah.

[00:46:44] **Adam:** so that you could do tips and, and they would not allow you to charge a tip.

[00:46:47] **Adam:** And I think it was because. Tips are kind of like a little bit of an under the table thing, right? So that it goes untaxed.But still, it was always annoying because, like you, I try not to carry cash. And I would, I would feel so bad on the times that I'm like, I'm rushing to get there on time and then I realize halfway there that I don't have cash.

[00:47:03] **Carol:** I'm like, oh my god, I'm, I'm such an I can't tell you how many times I've asked our waiters, like, do you have cash up or Venmo so I can tip you? Because we, we, we started like during COVID, we stopped carrying cash because during COVID. Nobody took cash! Nobody would touch your money cause it's dirty, right? Like we're not touching dirty money.

[00:47:22] **Carol:** And so everything became a card. So we just never have cash. So like with your app, like I'm thinking, how do I associate my tip to the person? Like some of that stuff.

[00:47:33] **Adam:** That's interesting. I have seen at some drop zones, like bigger, more like commercial drop zones, they'll have like, you know, a board up where they do their training and it's got like people's photos, like a headshot of them and it's like, you know, tips appreciated and it'll have like a QR code for each person.

[00:47:49] **Adam:** And I guess that probably goes to their Venmo or whatever, but, yeah, so.that's a, it's an interesting thought, but again, it's, it's a little outside the scope of this application. Yeah.

[00:47:59] **Tim:** I think it was good.

[00:48:00] **Carol:** think it looks good too.

[00:48:01] **Adam:** Thank you. I mean, if you guys, so I, I do kind of want to step away from the drag and drop thing. I'm like, if you could just imagine that the dots weren't there

[00:48:10] **Carol:** All right. They're gone.

[00:48:11] **Adam:** and drop thing. Yeah. And, like the only thing I'm thinking of is like, you click on somebody's name and it'll pop up like a modal with different options, right?

[00:48:19] **Adam:** Is that you can like scratch this jumper or move them to a different load, move their whole group to a different load. Yeah. Scratch the whole group, change their altitude or, or discipline. Mm hmm. Mm hmm. Mm

[00:48:30] **Carol:** So like if I were to check your name, right? So on flight one, you know, load one, I checked Adam Tuttle. I would want to be able to move you to a different load. I would want to be given an option that said, what action do you want to take?

[00:48:46] **Tim:** Yeah.

[00:48:48] **Carol:** Or do I want it to automatically say, move load, and then there's a dropdown that says to where, like load two, load three, load third, whatever's open, what has availability?

[00:48:58] **Adam:** hmm.

[00:48:59] **Tim:** message the end of somehow notify the individual that's Something's changed. Cause they signed up. They're

[00:49:04] **Carol:** Change. Yeah. You've got to have notification there. Yeah.

[00:49:09] **Adam:** Yes and no. I think that

[00:49:11] **Tim:** or they're looking at a screen. You think

[00:49:13] **Adam:** right. The, the notification thing matters more when you are geographically spread out, but we're talking about, you know, everybody is within 200 feet of. the same location, right?

[00:49:23] **Tim:** being at the airport and you're checking if you got your, your upgrade to comfort

[00:49:27] **Adam:** right. I, I, I can notify you by just going, hey, Carol, I changed our group from Freefly to, to Formation, right?

[00:49:34] **Adam:** So like, okay, cool.

[00:49:36] **Carol:** Fancy. Yeah.

[00:49:38] **Adam:** So yeah, I'm just trying to like,

[00:49:39] **Carol:** is there a limitation on it? So say you're in group one, is there a time constraint on it that says, you know, You can't move to anything sooner than limit three, like load three, because you should have already been packed, you should have already been through safety protocols, the max you can, like the, or the minimum you can go to is like load four.

[00:50:00] **Adam:** right. maybe, right. It's going to depend, like, I, I don't think that'll make the MVP, right. But so, so some apps that do similar stuff and really, so maybe I should say the reason, the whole reason I'm doing this is because there are other apps that do this, but they're just hella expensive, like more than my club can afford to pay for.

[00:50:17] **Carol:** Interesting.

[00:50:18] **Adam:** and so,I, you know, I'm just trying to do it on the cheap. so

[00:50:21] **Carol:** should have started with that, Adam. We could have looked at their things and figured out what you needed to add just to make you profitable here. You went the wrong route here, man.

[00:50:29] **Tim:** you

[00:50:30] **Carol:** Yeah.

[00:50:31] **Adam:** I'm trying, trying not to steal. so the, but for example, kind of what you mentioned is like, you know, you can't, at some places that you go, you can't scratch once there's less than five minutes until the plane takes off.

[00:50:44] **Carol:** Yeah, I mean, your load's been confirmed, sort of, you know? Yeah,

[00:50:48] **Adam:** Yeah.

[00:50:49] **Carol:** you should be, you should be strapped in and ready to go at this point.

[00:50:54] **Adam:** Yeah. A lot of places are very strict about that.

[00:50:56] **Carol:** Interesting.

[00:50:58] **Adam:** Okay. Well, I guess you guys have given me a good bit to think about. It's good to just get it off my chest and think out loud. I think

[00:51:04] **Tim:** go.

[00:51:05] **Carol:** I think you need a profile page at the beginning, at the front, so people can connect to each other with who's there.

[00:51:12] **Tim:** get gamified to help the club make more money. Yeah. There you go.

[00:51:15] **Adam:** maybe,

[00:51:16] **Tim:** Top dropper

[00:51:17] **Carol:** meet back up here, you know?

[00:51:19] **Adam:** Ooh, a leaderboard would be

[00:51:20] **Carol:** Yeah. Oh, leaderboard, there you go! Anything you can gamify is great.

[00:51:24]

## [00:51:24] Patreon

[00:51:24] **Adam:** Okay, well then, this episode of Working Code was brought to you by stealing other people's product ideas. And listeners like you, if you're enjoying the show and you want to make sure that you can, that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:51:38] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock!

## [00:51:46] Thanks For Listening!

[00:51:46] **Adam:** We are gonna go record our after show. I, we had some stuff in there, but it disappeared. I don't know what, what we're going to talk about an after show.

[00:51:54] **Adam:** but, we'll, we'll figure it out. That's kind of the whole point of the after show. It's, it's whatever, right? Maybe I'll talk about my fitness and dieting stuff. Maybe we'll get, What, what can Carol see over the border? I don't know. We'll figure it out.anyway.if you want to hear the after show, you are going to have to become a patron of the show.

[00:52:11] **Adam:** When you become a patron of the show, you get the after show and you get, special status in our Discord. If you want to join our Discord, it's totally free and open to the public. You can just go to workingcode.dev/discord. We'd love to have you come hang out. Great place to hang out. If you want to help us out on Patreon, you can go to patreon.com/WorkingCodePod. We would greatly appreciate it. That's going to do it for us this week. We'll catch you next week. And until then,

[00:52:32] **Tim:** My heart says hop and pop, your heart matters.
