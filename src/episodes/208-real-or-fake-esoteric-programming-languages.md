---
title: "208: Real or Fake? Esoteric Programming Languages"
description: "In this week's episode, the crew play Real or Fake for esoteric programming languages. Are Whitespace, JSF***, Cow or DeadFish real or fake? Listen to find out."
date: 2025-03-06
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/48cb14c1-89eb-4b5d-9691-dcdd256d4a5f"></script><div class="redcirclePlayer-48cb14c1-89eb-4b5d-9691-dcdd256d4a5f"></div>

In this week's episode, the crew play Real or Fake for esoteric programming languages. Are Whitespace, JSF\*\*\*, Cow or DeadFish real or fake? Listen to find out.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/208-real-or-fake-esoteric-programming-languages.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** you, you look at these crazy, like bash languages. Where the, it's like an, if starts a block and then a fee ends the block. And I don't, it's like, did they come up with that before they invented curly braces? I don't

[00:00:12] **Adam:** They didn't have the word end back then.

[00:00:15] **Tim:** Great

## [00:00:16] Intro

[00:00:16] **Adam:** Okay, here we go. It is show number 208 and on today's show We're gonna play another game I've once again cooked up a game for my co hosts. We have everybody on the show tonight. Say hello everybody

[00:00:46] **Carol:** Hello,

[00:00:47] **Tim:** Hello, everybody.

[00:00:49] **Adam:** You guys can't, pass up the opportunity to make that tired joke. Can you?

[00:00:52] **Tim:** No, I'm a dad.

[00:00:54] **Adam:** Yeah.

## [00:00:55] Triumphs and Fails

[00:00:55] **Adam:** but first as usual, let's start with our triumphs and fails. and Carol, I'm going to go to you first. Are you still employed? As you said last week, you're going to keep letting us know.

## [00:01:02] Carol's Triumph/Failure

[00:01:02] **Carol:** Yeah. I should let, you know, that's a big triumph. I still have a, I still have a job. today I had a job. I'll let you know next week because tomorrow could change. Every day is a new day. I'm going to go with a triumph slash failure.I don't know about you guys, but whenever I get faced with a challenge, I just want to go like dive into it and figure out how to solve it.

[00:01:23] **Carol:** I don't want to hand it off to someone. I want to just be hands in it, troubleshooting it, figuring it out. So I was tasked to figure out some caching issues going on inside our GitHub packages, only to then be told, we have a DevOps engineer who's really good at this, you should hand it off and, you know, let them do it.

[00:01:41] **Carol:** I was like, all right, cool. I'll let someone else work on it. Totally bummed out and kept peeking at everything he was doing and commenting on it, even though I'm sure he didn't want me doing that.but then yesterday I got in another meeting and was told, congratulations, all DevOps jobs are coming back to engineers now due to like staffing issues.

[00:02:02] **Carol:** So I'm like, really? Like last week I handed this off and, and like, let my brain process that I wasn't going to be the one to solve the problem only to then be told now go solve the problem. So it's a win and a fail, fail not on my side, fail for them, win for me, I get to do something fun.

[00:02:21] **Adam:** Did your DevOps guy that was supposed to be working on it get riffed or

[00:02:25] **Carol:** No,

[00:02:26] **Adam:** doing that work anymore?

[00:02:27] **Carol:** just, a lack of resources is what we were told. So there were a lot of people that were on probation that got let go. There were people that just quit. We've had a lot of people walk away from the stress. we haven't seen RIFs in our department specifically. But, people are just kind of done there over a lot of this.

[00:02:43] **Carol:** So there isn't a support like there used to be. We used to have a DevOps engineer assigned to each one of our teams. So on my project, I have five teams. So there were five DevOps engineers. There were four DBAs that were shared between us. And now we're down to one DBA. And the last time I checked one DevOps engineer.

[00:03:01] **Adam:** Wow.

[00:03:02] **Carol:** Yeah. So they're having to share their resources across multiple projects now, not just dedicated to staffing.

[00:03:08] **Adam:** Oof.

[00:03:09] **Carol:** Oof, fun times. But yeah, that's me. What you got, Tim?

## [00:03:13] Tim's Triumph

[00:03:13] **Tim:** So I got a triumph, last week, a reason I wasn't on the podcast, cause I was on a work trip. I drove from my area in middle Georgia over to Tuscaloosa, Alabama.

[00:03:25] **Adam:** That's not a real place.

[00:03:27] **Tim:** I know, right?

[00:03:28] **Carol:** Roll tide, roll!

[00:03:29] **Tim:** If you, yeah, if you're an Alabama football fan, like, like. Like Carol, you'll know that's the home of, Alabama University.

[00:03:36] **Tim:** And, so it was there that, there, one of the companies that's in our company portfolio is there, and we were evaluating, we do sort of very similar stuff, we were evaluating if we were going to kind of co op some of their technology, and went over there with, Like four other developers, I was there just, to represent management and, yeah, I had a nice time caught up with a guy that he got hired around the same time I did back in.

[00:04:02] **Tim:** 2000, but he lives up in Maine and I haven't seen him in years. His name's Gavin, great guy. We used to hang out with him a lot when he lived down here, but then he moved up to Maine and haven't written. He's just kind of a quiet guy. You know, he's, he's there, people forget about him. I'm like, oh yeah, Gavin used to work here, but I got to hang out with him and some of the other folks.

[00:04:20] **Tim:** It was nice to catch up with them. Cause I don't work with them directly, but, I was just there representing another company and, yeah, it was, it was great. we mount up his saying, you know what? It's cool technology, but with the project that we're thinking of using it on, and we don't really have the timeline right now.

[00:04:36] **Tim:** So we're gonna have to, we had a plan B that, that we already knew about, but it's a plan B, but yeah, we're definitely gonna keep it in our back pocket, but it was nice, great drive. Weather was perfect. It was like in the eighties.

[00:04:49] **Tim:** You know, last week and yeah, it was nice. Fantastic. So

[00:04:53] **Carol:** Did you happen to wander downtown and get any really good barbecue while you were there?

[00:04:58] **Tim:** I did not, we were going, because we're going to be there like four days. And then once we were there, like the first day we, you know, kind of huddled up or like, yeah, this isn't going to work. We're like, there's no point staying. So the next morning we kind of met with the other team for like half a day.

[00:05:14] **Tim:** And then I hit the road, get, get back home. So I wish I had, I really wanted, really wanted to go kind of tour around downtown. Have you been there?

[00:05:23] **Carol:** Oh yeah, I lived there for several years. That's where my youngest was born, yeah. So when I got married the first time, that didn't work out, that's where he was in college at, was at the University of Alabama.

[00:05:33] **Tim:** Okay.

[00:05:34] **Carol:** a place downtown called Dreamland. It's the best barbecue I've ever had in my life.

[00:05:38] **Tim:** very cool. No, I did not. We, we went to a nice restaurant. It was like right across the way from the office we were at, but it was really nice. Kind of like French bistro kind of restaurant. It's delicious. So had a nice time. So that was me. It's been a while since I've done like a, a work trip that wasn't like going to a big, like leadership conference.

[00:05:56] **Tim:** This was just like a, Hey, let's go talk to a customer or, you know, go see a partner with a couple of our, you know, fellow employees, so that was cool. Got to go do that. So how about you, Adam?

## [00:06:08] Adam's Triumph

[00:06:08] **Adam:** I'm gonna go with a triumph. I mentioned recently that, I was excited to get back to work on my skydiving manifest app, and try to make AI do a lot of the heavy lifting for me. And, I have had some, let's say halting success. with that so, you know, I kind of got started with the with asking ai to do most of the heavy lifting and Spot that i'm in right now.

[00:06:31] **Adam:** I'm i'm very opinionated so i'm doing more of the work myself than than asking ai to do it But I have a feeling i'll be getting back to like here. I want you to do this and this experience has really helped me to better utilize the ai stuff in my daily work, right i've kind of figured out a better workflow and how to use the tools to my To best fit my flow, I guess.

[00:06:57] **Ben:** what, what tools are you using? I'm very, so, you know, my failure is, is along the lines of AI, so I'm very keen to

[00:07:04] **Adam:** Okay, cool. Yeah. so you asked what tools i'm using just basically what's built into vs code I for a while I had turned off github copilot and I was using a different one called super maven which was you know, fine, but then you know copilot released some new features like they added the chat thing and they added like a Interactive editor thing which is very similar to the chat, but you can like say, okay I want you to edit this file and instead of Responding in the chat with like suggested that it's, it will just edit the file and you get like a diff view and you can, accept or reject

[00:07:36] **Ben:** Wait, this is. This is VS code itself, or this is a plugin in VS code,

[00:07:41] **Adam:** It's a plugin for VS code. Yeah.

[00:07:43] **Ben:** but who's it, who's it by

[00:07:45] **Adam:** it's by Microsoft, the, the copilot extension for VS code.

[00:07:49] **Ben:** is sorry. I, I know code, the term co pilot has sort of been co opted GitHub had a co pilot. Is this

[00:07:56] **Adam:** Yeah. And when I say Microsoft, I mean, you know, it, it, Microsoft owns

[00:08:01] **Ben:** yeah, yeah, yeah, yeah. I just didn't know if this had become a new thing or I haven't been following

[00:08:06] **Adam:** it's, I think it's just the latest evolution of that original GitHub copilot.

[00:08:10] **Ben:** Okay. Okay. Gotcha. Gotcha.

[00:08:12] **Carol:** Yeah, it's, mine's, my GitHub copilot, my copilot is tied into my GitHub subscription. So that's where I can see my history and my connections and stuff.

[00:08:20] **Adam:** Yeah. And I mean, it took me a little while to figure out how, I still don't think that the UI is amazing. It's very opinionated on where it wants to be in your editor and how you can interact with it and stuff. But it works. You know, I'm, I'm learning to live with, like, it wants to be on the left side of the screen.

[00:08:37] **Adam:** I usually keep like my, my file browser and everything over on the right side. Uh,cause I don't like, right. Well, when I, when I hide and show the browser, right. To get more screen real estate. The, the, the file explorer, that's what I meant to say, not the browser and hide and show the file explorer to get more screen real estate.

[00:08:55] **Adam:** I don't want the file contents to jump around, right? If you have it on the left, then the left edge of your file is constantly shifting from the left edge of the screen to the edge of the file explorer. And I just, I don't like that. That's one big reason why I like the file explorer on the right. And, and most of my other panels as well.and this one is like, you can only have it on the left. I haven't figured out how to move it or anything else. I'm just, I'm dealing with it.

[00:09:20] **Ben:** I've been thinking because I'm still a sublime text person and for a long time, I kept thinking to myself, Oh, I just don't want to switch to VS code. I've tried a little bit and I just, whatever. It feels like it's going to be too much of a, of a pain to get all the right things working. I had a revelation, which is that I don't think I actually have to use it.

[00:09:38] **Ben:** Meaning I think I can use my sublime text as my primary editor and just have something like. Cursor or VS code with co pilot open as well. And just point to the same directories. And anytime I want to do a big modification, that's AI driven. I can just jump over into VS code and ask it to do it. And then I can jump back into sublime text to,

[00:10:00] **Adam:** Yeah, because why swim with the flow of the river when you can swim against it?

[00:10:04] **Tim:** You're like that woman on those kayak commercials. I'm not gonna use Kayak to automatically search to airlines at once. I do it by myself and she stuffs her shirt with the hay and then goes hops up on the on the scarecrow to scare the the crows away by

[00:10:19] **Ben:** I just like my tools. But, I mean, in theory, you know, I think that would work. I digress. so, so, so tell us a little bit more about your experience. Cause now I'm, I'm wondering what it was like, like, what is the outcome of the AI generated code for you? Is it, is it,

[00:10:38] **Adam:** well, sure. The what I've done so far has very much been in the wheelhouse of AI generated code, right? It's all getting started with XYZ stuff, right? Like I want you to add this node module and and use it here to do this. And that's like, you know, basically pulling right out of the documentation and other open source projects and stuff like it can pretty much figure out immediately what it, what I need it to do.

[00:11:03] **Adam:** so where is going to get more interesting is for like, you know, I want to, I want you to refactor this and do it this way or that sort of thing. And I have done that. Right. So, one of the early things that I did, I told you about my experience originally, I think it was last week where we talked about, like I used, bolt.

[00:11:17] **Adam:** new. And I tried to have it generate the whole app from the functional spec. And I was frustrated that, you know, I ran out of tokens real, real quickly. well, so I still had that functional spec and I just, I didn't, I did not try dropping that whole thing into GitHub copilot. I just, after that initial experience, I was like, okay, this is clearly not the, the move let's go in a more iterative back and forth process.

[00:11:41] **Adam:** So I just started with the, like, okay, we're going to write an app that does this. Here are, here's my, my rough, data layer, right? These are the entities. These are the properties that I'm going to have on each of them. And I want you to write,TypeScript, you know, model objects that I can then use to read and write from the database for each of these things.

[00:12:00] **Adam:** And it did that. It's like, okay, cool. Now I want you to take all these, this model code that you just wrote, like keep it as context. And then I want you to write script to create all these tables in postgres So the table that you just defined now, I want you to write the create sql for those tables and it did It did a really good job.

[00:12:18] **Adam:** There was a couple of little things that I think I don't know if they technically qualify as hallucinations, but like postgres has got a real bee in its bonnet for snake case all lowercase and underscores instead of like camel case. and It just my my brain is I was Kind of brought up on camel case.

[00:12:37] **Adam:** So I, I, typed that way without even thinking about it 90 percent of the time. And so somehow it got some wires crossed and it started like mixing snake case and

[00:12:46] **Carol:** Oh no.

[00:12:48] **Adam:** not, not a bad way, it just was like, you know, maybe three or four different tables had like one column from a, from a single table, but it had the wrong, casing, I guess you would call it like snake case versus camel case.

[00:13:01] **Adam:** And then I, and I just went and it was faster to fix it than it would have been to ask the AI to fix it. So it wasn't that big of a deal.but yeah, I mean, like I said, it hasn't been perfect, but it's been very helpful. Like I've gotten a lot done and actually, so my triumph circling back has a second part to it, which I'm very excited about.

[00:13:19] **Adam:** I, I, this is not my first experience with database migrations. I have used them in the past, but it was always for like, Just little toys like, oh, cool. This is a thing that you could do, right? Like when I first started learning Ruby on Rails, it was like, oh, yeah, rake db migrate. Cool. That's, that's neat.

[00:13:33] **Adam:** And then, you know, you write your to do app and then you go and you're like, okay, well now I need to do this for a real thing and the database already exists and we don't have migrations and all that. So, oh, well, we're not doing that. but so for this app, I'm, I'm starting from scratch. It's like Let me see if I can find something that will do my database migrations for me.

[00:13:50] **Adam:** And I was like, I was frustrated at first because all of the migration stuff that I'm aware of off the top of my head is built into ORMs. And that's just, no, I'm not, I'm not going down that road again.so I was looking around and I managed to find one. I believe it was node PG migrate, if I remember correctly, the name of the package I ended up using.

[00:14:12] **Adam:** So it's using Postgres, of course, our Lord and savior. and, And it's, yeah, I mean, it's basically, it's specifically for Postgres and it only does the database migrations. There's no ORM or anything like that built into it. So, it's very focused and seems to be simple and straightforward. So it's working well for me so far.

[00:14:31] **Adam:** I'm, I'm very excited about it. it's great when you like, you know, you, you create a migration file, you make some changes to the database, you commit that and push it and your database gets updated along with the application. And Oh man. It's just so, it's invigorating to have like new stuff to play with that makes me excited.

[00:14:50] **Adam:** You know, like I almost wanna be like, sorry honey, I don't wanna watch TV tonight with you. I'd rather go hack on my app . But no, I just, I kind of do half of both and do neither Well,

[00:15:03] **Ben:** Nice. Well, there you go. That's so interesting. If I can jump on my failure now, cause my

[00:15:08] **Adam:** Yeah. Yeah. Yeah. So that's, that's me. Why? What do you got going on, Ben?

## [00:15:11] Ben's Failure

[00:15:11] **Ben:** So my failure is that. I just feel like the gulf between what I experience as an AI consumer and the hype that people are talking about, I feel like that gulf is just beginning to widen to a point where I feel like I'm going to be left behind unless I'm really actively working on trying to learn this stuff, like actually putting a lot of time into it.

[00:15:35] **Ben:** I just. So there's two things, there's two things that I keep trying to hold in my head and, and they're not, not in concert. So one is the quality of the AI experience, and one is the quality of the AI output. So the quality of the experience is, is kind of amazing. I mean, it's gone from nothing to the chat stuff.

[00:16:00] **Ben:** And then over the weekend, I started to use the. The voice modality in, on the chat GPT app. So I'm, I'm walking my dog and I'm literally having an out loud conversation with chat GPT, and I'm asking it questions about software architecture and, and forming proper boundaries around stuff and naming conventions and, you know, pragmatism around cohesion and, and, and decoupling and stuff.

[00:16:27] **Ben:** And so the, the experience is just, it's kind of mind boggling how easy that was to do. But then I step back and I think about, oh, what did I get out of this conversation? And I feel like it's taken the really crummy rubber duck and it's made it a really amazing rubber duck. But at the end of the day, I feel like I'm just not getting anything out of these conversations that I'm not putting into it.

[00:16:53] **Ben:** And maybe it's just, I'm not asking it the right things, or I'm not asking it to be strong enough in its opinions. But so many of the conversations that I have with it boil down to me saying something to the effect of, I'm not quite sure how I want to approach this. I understand that I could do it this way.

[00:17:11] **Ben:** And I understand that I could do it that way, but I'm not sure what to do, you know, help, help me make a decision. And it literally just regurgitates exactly what I said, like, Oh yeah, you have to take these things into account and you have to take these things into account, but like, doesn't actually move me.

[00:17:26] **Ben:** Yeah. It's like, it doesn't actually move me down the field in any, in any substantially different way than I'm doing in my head, just having the conversation and so like, I'm very frustrated by that because. I, I, everyone is talking about how revolutionary this is and I just feel like I'm not doing it right

[00:17:48] **Tim:** Yeah,

[00:17:49] **Ben:** and I,

[00:17:52] **Tim:** get you're saying I got two opinions on this. So one, I think it's still very early days, right? So I think. Three to five years from now, tools that people are using and, and how they do it aren't going to be absolutely completely different. So everyone's kind of in the experimental phase.so there's no right way to do it based on what you're trying to do.

[00:18:15] **Tim:** And even down the road, there won't be a right way to do it, but there'll become a standard way to do it, I think, at some point. And, and the other thing is, That, I think how you ask the question kind of influences the answer.

[00:18:30] **Ben:** yeah, like maybe I'm doing, that's why I feel like maybe I'm just not understanding the right strategies.

[00:18:35] **Tim:** Because there was an article that I read that really helped me kind of put into perspective. Because I'm like with you, I'm like, does it really help that much? You know, I put some code thing in there and it kind of spit something out and, but usually I have to spend more time reworking it than, but sometimes it does help me with the blank paper problem where you don't know where to start.

[00:18:53] **Tim:** it was TLDR a while back, I'll, I'll put a link in there, but there was, it's from Harper. blog. So My LLM code gen workflow at the moment, and it has a couple of use cases. I'll put it in here so you can take a look at it while I, while I talk about it.

[00:19:10] **Tim:** but one of the things I never thought about using it for is like plan doing project planning. So it has an example here, like you have a greenfield project. And you put, and the way he models the prompt is very, very different than how I would think to do it. It gives like instructions to The LLM, like it's a five year old child, but just, I'll just read a little bit.

[00:19:35] **Tim:** I won't read all of it, but, draft the detailed step by step blueprint for building this project. And once you have a solid plan, break it all down into small interim chunks that build on each other, look at these chunks and then go another round to break it into small steps. I mean, I never would have thought to say those words, but he seems to get good mileage out of it.

[00:19:54] **Tim:** And that can change over time, but I would, you know, I would kind of describe, here's my problem. What do you think the solution is? And I would probably get very vague answers, but he's not only telling it what the problem is, but he's telling it how to break it down, how to attack the problem and the expected output that he's getting at the end, which I thought was interesting.

[00:20:16] **Ben:** See, I feel like I need to learn how to think that way. Part of me wants to try to find a course that like on, on Maven or Udemy or something about. Learning about AI, my, my, my hesitation with doing courses for things like this is I feel like those courses are always by people who are only teaching you how to do the thing, but don't necessarily have a proven track record on, on it's like, here's my course on publishing books, but like, I'm not a published author.

[00:20:47] **Ben:** Or like, here's my course on making money in real estate, but like, I haven't made money in real estate. I've

[00:20:51] **Tim:** Otherwise I'd be making money

[00:20:53] **Ben:** Right, right. Like, then why are you doing this course? And I feel like my concern would be like, here's the people who know how to use AI, but to what end, you know, to the end that they could teach me a course on how to use AI.

[00:21:05] **Ben:** Like, that's my, that's my concern. But.

[00:21:08] **Carol:** I don't know if you remember a few months back when I was finally getting access to GitHub copilot, I had to do the mandatory, prompt engineering course to understand how to write prompts to AI. And I was like, are you kidding me? I now find myself doing things like, how many breaking changes were between these packages?

[00:21:29] **Carol:** And there's so many, it can't tell me. So I'm like, why did I even ask that here? This was dumb. It's like, go find It's like, you should reference, like, the Nuget, like, package store for this. And I'm like, okay, fine. I'll click the link. I was hoping you could just tell me.

[00:21:43] **Adam:** So one, one trick that I've learned, going back to your sort of original problem, Ben, of like you, it doesn't really answer your question, just kind of regurgitates what you said back at it, at you, I, as much as I don't, spend my personal time on Reddit anymore, I do acknowledge that there are a lot of people on there and, some number of them are smart and, and they have, you know, they have a lot of discussions on every topic under the sun.

[00:22:07] **Adam:** So what you can do is you can say like, I, you know, I'm considering, I'm trying to solve this problem. What do people on Reddit usually say, you know, like what, what is their preferred solution

[00:22:17] **Ben:** Oh, you're saying use that as a prompt.

[00:22:19] **Adam:** Yeah. And it'll, it'll like the one that I use most often for, for prompts like that is built into Raycast, my, my launcher.

[00:22:29] **Adam:** I, I just find that to be the most productive for me, right. It's just command space, type my question and hit tab. And, and I am there instead of having to like go open the chat GPT tab and start a new conversation or whatever. and so I don't know exactly off the top of my head what engine it's using, whether it's Claude or, or GPT 4 or whatever, but, it gives me the response, but then it gives me like links at the bottom of that, that I can, it'll, it'll link to four or five different Reddit threads or whatever, so that I can go and like verify what it summarized or dig into the details more.

[00:23:01] **Adam:** So I find that pretty helpful.

[00:23:04] **Ben:** And I, you know, I want to be clear that I'm not like a, I'm not an AI pessimist in that I don't think it's useless. I mean, I do get value out of it, but I'm like, even if it's just the rubber ducking, I do find that is valuable. It does help me think through my thoughts better by forcing myself to articulate them into questions that, but I also do get value out of, of real more concrete things.

[00:23:27] **Ben:** You know, I'm trying to understand. Like if I have to do a HMAC, an HMAC SHA 512 hash, like what's the proper length of key that I should be using with that? And it'll usually give me some sort of answer, you know, because that's a security related thing. I will then also try to Google it and find Microsoft's recommendation.

[00:23:45] **Ben:** Cause I figured they're on the ball when it comes to that kind of stuff. And like, it lines up and I'm like, okay, if the chat GPT and Microsoft are saying the same thing, I'm going to go with it. But, it, I think it just seems to, when I ask it more philosophical things. Or maybe things that don't have a definitive answer, you know, things that are, it depends.

[00:24:05] **Ben:** I find that it really doesn't have any opinions. And I mean, I guess it can't, cause it's not a thing, you know, it's not a thinking thing. It's just regurgitating statistically what other people have said. So it's, I, you, we get lulled into this, not, it's like kind of an uncanny valley where it's like, you want so hard for it to be a personality, but it is not a personality.

[00:24:28] **Adam:** Right. Have you seen the movie Her? Her.

[00:24:30] **Ben:** Yeah. Yeah. Yeah. Of

[00:24:31] **Carol:** I've been thinking about that the whole time. It's one of the few movie references I actually get.

[00:24:37] **Adam:** I didn't really have anywhere to go with that. I just based on what you were saying It was it seemed like it would be a good watch for you.

[00:24:43] **Ben:** Well, it's such a, there's such an interesting moment in that movie. I mean, this is a spoiler alert. So anyone who's listening, who hasn't seen it, you know, earmuffs in the movie, Joaquin Phoenix's character is developing this deep relationship with the, with the operating system. And then at one point he asks her if she's having conversations with anybody else currently.

[00:25:03] **Ben:** And she's like, yes, I'm currently talking to like 10, 951 other people. And it's like that. Like you're, you're so insignificant in, in it's like the, the bi directionality of this relationship is so uneven. And that's how sometimes I feel with the AI stuff. It's like, I want it to be more opinionated. I like, I want it to have more personality.

[00:25:26] **Ben:** I want it to have, I don't know, just like a little bit more magic and the experience is magical, but that almost makes it more disappointing when you realize how. Not magical, and I, and I, that's not the right term, but like how not magical it actually is, it's very mechanical. I'm done.

## [00:25:45] Real or Fake Programming Languages

[00:25:45] **Adam:** Well, I guess then that brings us around to our game for the day.

[00:25:48] **Ben:** Fa fa fa fa faaaa!

[00:25:50] **Adam:** basically, I didn't want to give the hosts here the opportunity to prepare so i'm springing this on them They have no idea what we're going to be doing. it's very different from the last game that we played So they they complained that I made the last game too hard.

[00:26:03] **Adam:** So this this gamewe're gonna have 10 questions and on every question you have a 50 50 chance of getting it right because it's you just choose One thing or the other right? So we're going to play a game of real or fake. and it's going to be esoteric programming languages edition.

[00:26:23] **Tim:** Cool.

[00:26:24] **Adam:** I'm going to tell you a little bit about a programming language and you just have to decide, is it real or is it fake?

[00:26:29] **Adam:** And I know this was a little bit of a debacle last time. Cause we were just sort of figuring it out. I have, I have a good way to keep track of points. Uh,I have a spreadsheet. It's going to add them up for me. We're all good to go.

[00:26:41] **Tim:** Cool.

[00:26:41] **Adam:** and nobody has to like beat each other in on the buzzer or anything like that.

[00:26:45] **Adam:** Everybody gets to answer every question.

[00:26:47] **Ben:** Nice.

[00:26:47] **Adam:** I'm going to describe a programming language, and then in whatever order you want, you can try to influence each other or whatever. I don't, I don't care. you're just going to tell me if you think it's real or fake. And if it's real and you choose real or if it's fake and you choose fake.

[00:27:00] **Adam:** If you get it right, you get a point. If you get it wrong, you don't get a point. Pretty easy, right?

[00:27:04] **Carol:** No Google link?

[00:27:06] **Adam:** No Googling. No, no research as we go on the fly here. That would be cheating.

[00:27:10] **Tim:** Yes, they are real and they are fabulous

[00:27:15] **Adam:** that sounds so familiar. What is

[00:27:16] **Ben:** a Seinfeld reference.

[00:27:18] **Adam:** Yeah. Okay.

[00:27:19] **Ben:** It's the the, the, the, what's it like, the Clark Bar heiress? Not Clark Bar, but you know, like the Hundred Grand Bar heiress. No, no, no. I don't know. Nevermind. Yes, Seinfeld.

## [00:27:29] GCAT

[00:27:29] **Adam:** All right. Our first programming language is called GCAT. Here's the description exclusively uses the characters G, C, A, and T, which you may recognize as the nucleotide bases of DNA so that it can ultimately be stored as physical DNA, which comes with a host of benefits, including. extreme compactness for storage, and backups via DNA's self replicating behavior. Real or fake?

[00:27:56] **Tim:** You want to call us an order or not?

[00:27:59] **Adam:** Whoever wants to answer, you guys can try to influence each other, discuss amongst yourselves.

[00:28:03] **Ben:** I think that's got to be real because that feels, that feels like something somebody wanted to make real so badly that they spent, you know, a thousand hours of their personal time making it happen.

[00:28:15] **Tim:** And there is, they have talked about applications of genetic computers because it can store a huge amount of data. So I'm going to go with real too.

[00:28:24] **Carol:** Yeah. I agree. Yeah. I just read something about encoding and putting chips and DNA and, like, what you were capable to, like, put in. I was like, yeah, this seems way far beyond what I want to learn right now.

[00:28:35] **Adam:** Okay, well the good news is you guys all guessed the same thing. So no matter what it's still a tie game

[00:28:42] **Tim:** The bad news is,

[00:28:43] **Adam:** The bad news is you're all wrong at least as far as as far as I know I just made this up because I was like that would be so cool

[00:28:50] **Ben:** Oh, man.

[00:28:51] **Adam:** Now I'll caveat if somebody knows of something close enough then then maybe we can retroactively come back and give you all the point for it or something, but you know, to me, it was like, it sounded just close enough to real that I could get away with it.

[00:29:06] **Adam:** So that's why I started there. So no, I, I made that up.

[00:29:10] **Tim:** okay.

[00:29:11] **Ben:** Oh. Has anyone ever seen the movie Gatica?

[00:29:14] **Tim:** Yeah.

[00:29:14] **Ben:** It, it's a solid movie for listeners, it's, Ethan Hawk and, Jude Law. It's pretty good.

[00:29:21] **Adam:** Okay. Thanks for that reference. That

[00:29:23] **Ben:** Well, Gatica is spelled, no, no, Gatica. The, the mood title is spelled with. The nucleotide

[00:29:29] **Adam:** A's and T's. Interesting. Okay. All right. Our next language is going to be chameleon. The code changes its meaning based on the color of the text, making it a visual programming language that requires constant color adjustment to understand. Did somebody

[00:29:46] **Ben:** hope this isn't real.

[00:29:49] **Carol:** I'm

[00:29:49] **Adam:** Did somebody make this just to be a complete jerk about it? Or did I make it up?

[00:29:55] **Tim:** sound very accessible.

[00:29:57] **Adam:** No,

[00:29:59] **Tim:** What if you're, what if you're red, green colorblind?

[00:30:02] **Adam:** I didn't say it was red and green. I just said color changes.

[00:30:05] **Tim:** That's true.

[00:30:06] **Carol:** going with fake. This doesn't

[00:30:08] **Ben:** Please be fake. Please be fake.

[00:30:10] **Tim:** I'm going with fake too.

[00:30:11] **Adam:** Okay. Everybody says fake.

[00:30:13] **Carol:** Yeah. Woohoo!

[00:30:13] **Adam:** Everybody is correct.

[00:30:15] **Ben:** All right.

[00:30:17] **Adam:** Yep, I just made that one up too. Alright, uh,

[00:30:20] **Carol:** you asking, like, ChatGPT to help you make up fake software? Like, languages? Like, programming languages?

[00:30:25] **Adam:** I did get some help from ChatGPT toward the end. Cause I was, I was, you know, it's real hard to come up with a bunch of fake ones

[00:30:30] **Ben:** Yeah, absolutely.

[00:30:32] **Carol:** Note to self, he said a bunch of fake ones,

[00:30:34] **Carol:** so

[00:30:36] **Adam:** dropping hints or, strategically trying to convince you that the rest of them are fake. all right.

## [00:30:42] JSF

[00:30:42] **Ben:** The, the next one we're going to go to here is, sorry, Matt, you're going to have to crack this. It's called JSF\*\*\* My

[00:30:50] **Adam:** I'll read you the description here. It says inspired by brain This language is more or less a clone of its cranial namesake, but with a different set of allowed characters. Whereas, brain f**_ uses the characters plus, minus, less than, greater than, comma, period, open square bracket, and close square bracket, js f_** uses open square bracket, close square bracket, open parenthesis, close parenthesis, exclamation mark, and plus.

[00:31:12] **Adam:** And in so doing, becomes valid JavaScript. That is, JS f\*\*\* programs can run using a standard JavaScript engine.

[00:31:22] **Tim:** Ooh, that's a lot of quacks. A

[00:31:24] **Carol:** Poor Matt. I hope you're giving him, like, a bonus for this episode.

[00:31:29] **Tim:** quack bonus.

[00:31:30] **Carol:** Mm mm.

[00:31:31] **Adam:** Real or fake?

[00:31:32] **Carol:** Real.

[00:31:33] **Ben:** Fake.

[00:31:34] **Tim:** I think some jerk just wanted that name. I know. I know, Carol. I think, think me, you, me and Mark Mandel created a language.

[00:31:45] **Carol:** Oh yeah. Well, it's a framework. It's a framework. Yeah, let's be real.

[00:31:50] **Tim:** yeah, it was a framework, but yeah, I'm going to say some jerk actually went out of their way to create this. I mean, anybody, their dog can create a JS language. So

[00:31:59] **Adam:** so we have one fake and two reals,

[00:32:01] **Carol:** Real. I'm going with real.

[00:32:02] **Ben:** on. Fake.

[00:32:04] **Adam:** So the correct answer is real.

[00:32:08] **Ben:** you guys suck

[00:32:10] **Adam:** So, as a matter of fact, JS f\*\*\* has been used in XSS attacks on sites like eBay because it looks innocuous enough. It looks just like regular text at first glance. And so it can evade a lot of XSS detection stuff.

[00:32:24] **Ben:** crazy.

[00:32:26] **Adam:** Yeah. All right. so the store, the score stands that Ben has one point, Carol and Tim both have two.

[00:32:31] **Carol:** Oh, woo hoo!

[00:32:34] **Tim:** Let's

## [00:32:34] Invert Lang

[00:32:34] **Adam:** All right. Our next lang language, invert lang. This JavaScript clone simply requires you to write all keywords backwards and all statements in reverse as well. So the statement, if X, Y, Z is greater than one would become one greater than Z, Y, X fee.

[00:32:54] **Carol:** Hell no. There's no way that's real. Who would want to spend any time on that?

[00:32:59] **Ben:** you, you look at these crazy, like bash languages. Where the, it's like an, if starts a block and then a fee ends the block. And I don't, it's like, did they come up with that before they invented curly braces? I don't

[00:33:12] **Adam:** They didn't have the word end back then.

[00:33:15] **Tim:** Great. I'm, I'm going fake.

[00:33:19] **Ben:** I'm going through that now. I gotta

[00:33:21] **Tim:** All right.

[00:33:21] **Ben:** I gotta make up some ground here.

[00:33:23] **Carol:** gotta lose, is what I heard? No.

[00:33:26] **Adam:** Well, Ben, I'm sorry to tell you you're wrong again. that's another one that I made up.sorry, no, no fun facts about that one because it

[00:33:34] **Adam:** just came straight out of my brain hole.

[00:33:35] **Carol:** I mean, I feel Me

[00:33:39] **Tim:** so I mean, it's, it's not really fair.

[00:33:42] **Tim:** If You say that one, he'll definitely say it's true.

[00:33:44] **Ben:** you know, it drives me crazy though. And this is a real thing. And I think it's, maybe Ruby does this where they'll put an inversion at the end of a statement. They're like, call this unless something else is false. And I'm like, who, whose brain works like that? That's crazy,

[00:34:01] **Adam:** things about Ruby that like seem really cool from a syntactic, like nerdy language design. Like, oh, that would be cool to write the compiler that could do that. But then when you're like sitting there trying to use the language, it's like, Oh, I hate this. I hate it. Take it away. Go.

[00:34:15] **Ben:** right? It's like so much of how the brain operates is pattern matching. And if you're scanning a line and you see like. Do this method call, like half the time I have to imagine you just immediately assume it's going to happen, skip on to the next thing and don't worry about some esoteric unless at the end of the line.

[00:34:32] **Ben:** Anyway, invert lang, I guess it's good that it doesn't exist is

[00:34:35] **Adam:** Yeah.

[00:34:35] **Ben:** saying.

[00:34:37] **Adam:** Yeah. That, that sounds just painful.

## [00:34:39] Whitespace

[00:34:39] **Adam:** All right. Our next language is going to be called white space. White space uses only white space characters, space tab and return, ignoring all other characters, which can therefore be used for comments. It also allows white space programs to be hidden in the source code of programs in languages like C.

[00:34:57] **Tim:** I don't even

[00:34:57] **Ben:** Yo, this is 100 percent real, absolutely.

[00:35:01] **Carol:** I'm going with fake. I think Ben would know it because of all the whitespace he uses in everything he does. If anyone's gonna know something

[00:35:08] **Adam:** Oh, wait a minute. We got

[00:35:10] **Carol:** it's gotta be Ben.

[00:35:11] **Adam:** Yeah. We got it. We got to go put all of Ben's old blog posts through the whitespace language formatter and just see what it spits out his,

[00:35:19] **Tim:** He's got

[00:35:19] **Ben:** the, I love the idea,

[00:35:21] **Tim:** he's been working on.

[00:35:22] **Adam:** yeah,

[00:35:22] **Ben:** love the idea that non white space becomes comments then.

[00:35:26] **Adam:** yeah.

[00:35:27] **Ben:** I love it. I love it. I so hope this is a thing. Oh,

[00:35:32] **Tim:** going fake. What?

[00:35:34] **Adam:** Well, the scores are getting closer because it's real. real.

[00:35:39] **Tim:** What possible

[00:35:39] **Ben:** eat my tabs, fellas.

[00:35:44] **Carol:** New line, new line. Um. to, we're going to have to bleep that.

[00:35:50] **Tim:** this must be for like some sort of secret spy stuff where they're like sharing secret messages.

[00:35:55] **Carol:** whitespace? I don't even understand. My brain can't comprehend how this would work, so.

[00:36:01] **Adam:** Well, I mean, you'd have to have an editor that would show, like, different representations of that whitespace. So, like, in VS Code, you can turn on whitespace characters, and you can see, like, a long arrow for a tab, or a dot for a space. And return, obviously, just brings you down to the next line, but, I don't know.

[00:36:15] **Tim:** So one space is an I, two spaces is an E, a tab tab space is, it's like hex decimal.

[00:36:22] **Ben:** I wonder, I know so little about how fonts work, but I know that some of these editors can do the funky ligatures where it's like three triple equals becomes a big heavy equal block. I wonder if you could do something like where spaces and tabs are short beeps and long beeps for Morse code.

[00:36:39] **Ben:** And then literally have like. You know, space tab space ligature into a, into an app, actual ASCII character.

[00:36:46] **Adam:** Oh, that would be really neat to, like, I, I don't know enough about how ligatures work. I'm very familiar with them because I do use them, but, in terms of, like, you know, could you do this? I don't know. But it would be really cool to like, okay. So like, like Tim was saying, you know, okay, space and then a tab together might be the e characters you're at the e characters.

[00:37:03] **Adam:** So if you. Like could you make a ligature that's just space tab equals e and like it represents it in your ide as an

[00:37:10] **Adam:** e even though It's

[00:37:11] **Tim:** That's what I was

[00:37:11] **Adam:** tab together. That would be really cool. But no, that's a real one

[00:37:15] **Ben:** Oh yeah.

[00:37:17] **Adam:** Yeah. All right. So the scores right now ben has two points carol and tim have three getting close.

## [00:37:22] Malbolg

[00:37:22] **Adam:** All right our next language i'm not exactly 100 sure how to pronounce this malbolg I believe is how it's pronounced it's named after the eighth circle of hell in dante's infernowas designed to be the most difficult and esoteric programming language Among other features, code is self modifying by design.

[00:37:40] **Adam:** Arithmetic is done in base three. And the effect of an instruction depends on its address in memory. He

[00:37:52] **Tim:** eighties.

[00:37:54] **Ben:** I'm going to say real something about code that modifies itself feels real.

[00:38:00] **Carol:** And something about Adam not knowing how to say it makes it feel

[00:38:03] **Tim:** That could be a red herring.

[00:38:07] **Adam:** is a crafty little one.

[00:38:08] **Tim:** Yeah. I'm going, I'm going with real too.

[00:38:11] **Adam:** Carol?

[00:38:12] **Carol:** I feel

[00:38:13] **Tim:** Oh,

[00:38:13] **Ben:** sorry, I didn't hear you. So no, no change in the scores or no change in the difference in scores. But, yes, everybody's right. That one is actually real. That sounds awful.

[00:38:22] **Carol:** That sounds It does. Base it's, Yeah, I, I read,

[00:38:27] **Carol:** for?

[00:38:28] **Adam:** I, I'm not exactly sure it has a, an actual use other than people who have way too much free time and a deep interest in programming languages.

[00:38:36] **Adam:** It was someone's, someone's, computer science doctorate,

[00:38:40] **Adam:** if you, if you look up the Wikipedia page for it, you can find like example programs, you know, there's like hello world and stuff. And it just looks like,a password after it's been put through Bcrypt. It's just,

[00:38:50] **Carol:** wow.

[00:38:52] **Adam:** just a bunch of random characters.

[00:38:54] **Tim:** self modifying. Oh, it's gotta be great to beat the bug.

[00:38:57] **Adam:** Yeah. All right. O

## [00:38:59] Code Emoji

[00:38:59] **Adam:** ur next programming language is Code Emoji. Code Emoji is a language where only Unicode modifier characters are significant. All other characters are considered comments. You might recognize Unicode modifiers as the extra hidden characters that make it possible to customize emojis such as skin tone and gender variations.

[00:39:19] **Adam:** Visually, this means that an entire program could fit into a single character's real state. Because Unifode, Unifode, Unicode modifiers are zero width. It's just going to be tricky to read and write without the dedicated editor that makes it possible, though still not easy, to read and write these characters.

[00:39:37] **Adam:** I understood like half of that. Don't make me read it again.

[00:39:41] **Ben:** I'll

[00:39:41] **Tim:** So this is like that white space one

[00:39:44] **Carol:** just

[00:39:44] **Adam:** yeah, so it's, but instead of being just spaces, tabs, and returns, this is Unicode modifier. So, like, if you, there's a, there's one, Unicode character code point, I guess it would be the technical term for it. That means like, you know, a person standing and waving, right. And then you can, there's a modifier character that says.

[00:40:01] **Adam:** apply this gender. There's a modifier character that says apply this skin tone. So you can have like a dark skinned person, a dark skinned man waving. And that's just one, it's the person waving with the male and the dark skin, modifiers applied

[00:40:15] **Tim:** and everything else is comments. Mm.

[00:40:17] **Adam:** and everything else is comments. Yeah.

[00:40:18] **Ben:** fake. Okay.

[00:40:25] **Tim:** I'm going, I'm going fake.

[00:40:29] **Adam:** right, everybody says fake and it is fake.

[00:40:31] **Tim:** Yeah.

[00:40:32] **Adam:** however, based on a kernel of truth. So I made this one up based on a blog post that I saw about smuggling arbitrary data through an emoji. which was itself inspired by a comment on Hacker News. I'll have a link that I'll put in the show notes. But basically, somebody just decided, okay, we're going to make up an alphabet using Unicode modifier characters.

[00:40:53] **Adam:** And then you just take a bunch of those modifier characters and, you know, you do replace, right, you know, instead of like A and, F switching places, you have A and gender, gender male or whatever switch places, right? So you have all these modifier characters and you just apply them all to a single emoji and then you can put that in a line of text.

[00:41:11] **Adam:** And your hidden messages in there. And then if you run it through the decoder, like, okay, it gets rid of all the normal characters until it's got nothing but the Unicode modifiers. And then it just reverses the replacements

[00:41:22] **Adam:** and you've got your original message back, which is really interesting.

[00:41:25] **Tim:** Yeah. So, I mean, in theory it could be used as, as, as the programming. Like we just, we'll just have to,

[00:41:31] **Adam:** Yeah. I mean, I saw that, that post and my first thing that I thought of was like, that would be like a, such a interesting way to do like a spy craft, right? Like I watch a bunch of TV shows where there's like spies and, you know, espionage type stuff and.

[00:41:44] **Tim:** yeah, that Harriet, she's something else.

[00:41:48] **Adam:** Harriet the Spy. Oh, poor, uh, what is her name? She just died.

[00:41:52] **Tim:** Transperg or

[00:41:53] **Adam:** Michelle Trachtenberg.

[00:41:54] **Tim:** Trachtenberg,

[00:41:55] **Adam:** Yeah.

[00:41:56] **Tim:** she had a, she had liver

[00:41:58] **Adam:** yeah, she had a liver transplant a few years ago. Thanks, Tim.

[00:42:03] **Adam:** Bringing it

[00:42:04] **Ben:** Yo, can I admit something though? this is

[00:42:07] **Adam:** You had a huge crush on Harriet the Spy

[00:42:09] **Adam:** no, I don't even know who that is. I mean, I've heard the movie, but I never saw it. ha

[00:42:13] **Ben:** is an unpopular opinion, I'm sure, but I find the skin tone emojis kind of creepy. Like I really liked it when everyone was just a fake yellow. There's something about people using skin toned emojis feels.

[00:42:28] **Ben:** Just really weird. Like it's making me think about them in like much more of a concrete way.

[00:42:34] **Tim:** than a Simpson.

[00:42:35] **Ben:** Yeah, exactly. I don't know. I

[00:42:39] **Tim:** don't know if that makes you racist or not,

[00:42:41] **Ben:** it's, it's, I feel like it's equally racist against all colors.

[00:42:46] **Tim:** Well, I

[00:42:46] **Adam:** the UTC of racism. I

[00:42:50] **Carol:** Am I the only one who uses the yellow one still?

[00:42:53] **Ben:** I use the yellow ones

[00:42:54] **Tim:** I, I, whatever's default I use.

[00:42:58] **Adam:** go back and forth.

[00:43:00] **Ben:** I don't know. It also just feels like it's a lot of work, although I guess, I guess it's something that just gets set once or something.

[00:43:07] **Adam:** Depends on your, your emoji picker, but yeah.

[00:43:09] **Carol:** Do you guys use iPhones?

[00:43:11] **Adam:** Yeah, I do now.

[00:43:12] **Carol:** Did, um, did you ever create the little character, like the little meme of yourself?

[00:43:17] **Tim:** I

[00:43:18] **Carol:** Yeah, whatever they were called, I don't remember. My niece created one, and I never took the time to, like, change it to be myself, so every time I send something, like, Laughing or whatever. It's always her. She is, these are my Asian nieces, by the way. So I

[00:43:34] **Carol:** think I confuse people a lot. I'm like, that's Ella. That's Ella.

[00:43:39] **Tim:** Yeah. I think you just made Ben's point.

[00:43:41] **Ben:** Yeah.

[00:43:43] **Adam:** Well, that's Memoji. Memoji is racist. Not skin tone emojis. All right, moving on, moving on. Scores are Ben has four points. Carol has five points. Tim has five points and we have three languages left to go.

[00:43:58] **Ben:** do it

[00:43:59] **Adam:** So get your, stake your claim now. Be, be different from everybody. All right. Ready?

## [00:44:05] Cow

[00:44:05] **Adam:** Our next programming language is called cow.

[00:44:08] **Adam:** As in C O W, Moo. the COW programming language was created by Sean Heber in 2003. COW has 12 unique instructions and is Turing complete. Most instructions are Moos. The only capitalization vary, only the capitalization varies. So you've got like lowercase m, uppercase o, lowercase o, lowercase m, lowercase o, uppercase o, lowercase m, uppercase o, uppercase o, uppercase m, lowercase o, lowercase o, and so on, right?

[00:44:35] **Adam:** So variations on mu, but only changing the capitalization. So that's not all of them, obviously, because there's a bunch of different variations. And then, yeah, whatever. So all other character combinations are ignored and treated as comments. Real or fake?

[00:44:49] **Ben:** real

[00:44:50] **Carol:** Real.

[00:44:51] **Tim:** thank.

[00:44:52] **Carol:** I'm going with real. Oh shoot!

[00:44:55] **Adam:** well, the score differential stays the same, but because Tim was wrong, that is a real programming

[00:45:02] **Tim:** That's real

[00:45:04] **Ben:** interrupting cow says moo Oh

[00:45:08] **Tim:** brought to you by speak and

[00:45:10] **Adam:** oh, actually, I messed up the

[00:45:13] **Tim:** yeah, so I should be in between Ben and Carol now,

[00:45:16] **Adam:** So Ben, Ben and Tim are, are, tied at five. Carol has six, because it was five, six, six, or it was four, five, five before. Yeah, yeah. Okay. All right.

## [00:45:26] Snake

[00:45:26] **Adam:** our next programming language is called Snake. Inspired by the game we all played on our graphing calculators in high school, this programming language requires you to write code in a grid, 81 by 81 characters, using Unicode arrows to indicate direction change, interpreting all other characters in sequence.

[00:45:43] **Adam:** The snake may not crash into itself and must use all available space in the grid before a new grid may be started after a blank line. In the first grid, the snake starts in the center, traveling up, but as it finishes each grid, it carries its current direction into the center starting point of the next grid. Real or fake?

[00:46:01] **Carol:** Let me, let me pull out my Razer phone from high school and play Snake like while we talk.

[00:46:06] **Ben:** I'm

[00:46:07] **Carol:** I feel like this is fake. I don't even know what this would be doing.

[00:46:12] **Ben:** I'm so confused. So I heard the description of what snake does, but you're saying that's a program.

[00:46:17] **Carol:** the programming language. It's what Snake does.

[00:46:19] **Adam:** so think of it, the snake is like where the, the compiler is reading your, your code, right? So it traces the path of the snake. And it reads the characters. So you're just filling in a grid of characters.

[00:46:33] **Ben:** Oh my goodness.

[00:46:34] **Tim:** but I mean each grid could be used to represent. I think it's real

[00:46:39] **Ben:** Fake. Fake.

[00:46:41] **Adam:** right,

[00:46:42] **Carol:** I go with fake, so.

[00:46:43] **Adam:** okay so we had tim was real and ben and carol said fake.

[00:46:47] **Carol:** Mm hmm.

[00:46:48] **Adam:** All right, it was fake.

[00:46:49] **Ben:** No.

[00:46:50] **Carol:** Woo hoo!

[00:46:51] **Adam:** I made that one up

[00:46:52] **Carol:** Hey, that was a good one, though. Mm hmm. Mm hmm.

[00:46:56] **Adam:** All right. We have reached the the last Esoteric programming language of our game. So

[00:47:01] **Tim:** So I'm at I'm out of it right I can't I can't make it

[00:47:04] **Adam:** yeah, I don't think so. I don't, I don't want to come up with a, like a tiebreaker or sort of thing at the end here, but so the scores as they stand right now, Carol has seven, Ben has six, Tim has five, but you can play for the, for, for the best

[00:47:15] **Tim:** for the

[00:47:16] **Tim:** glory

[00:47:16] **Ben:** There you go. I

[00:47:18] **Tim:** First place loser.

[00:47:19] **Adam:** yeah. All right.

## [00:47:20] Dead Fish

[00:47:20] **Adam:** Our last language is called dead fish. This language can produce output, but has no way to accept input. It has only four commands in total. increment, decrement, square, and output. It's also case sensitive, and when adding or subtracting, it can only deal with integer values.

[00:47:38] **Carol:** It's called what?

[00:47:40] **Adam:** Dead fish.

[00:47:40] **Carol:** Dead Fish. I'm gonna go with true.

[00:47:43] **Ben:** go with fake.

[00:47:44] **Carol:** I'm just thinking you're gonna try to, like, scam us at the end, you

[00:47:48] **Tim:** I'm going, I'm going, I'll go, I'll go true. Could you use to program calculators or

[00:47:53] **Carol:** Yeah.

[00:47:54] **Adam:** so we have Carol and Tim saying it's real, and Ben saying it's fake. Okay, that one is indeed real.

[00:48:01] **Ben:** Come on.

[00:48:02] **Carol:** Yeah! Yeah.

[00:48:03] **Adam:** Good job, Carol. All right, the final score, Ben has six points, Tim has six points, you guys are sharing second place on the podium, and Carol has eight points.

[00:48:13] **Ben:** Nice to done. Carat golf clap to you, ma'am.

[00:48:15] **Tim:** Golf club.

[00:48:17] **Carol:** you, thank you!

## [00:48:19] Wrapping Up the Game

[00:48:19] **Adam:** So, Did you learn anything interesting or fun about esoteric programming languages?

[00:48:25] **Ben:** You, you do have me wondering if I could build a snake program now, like just like a simple one that moves around the screen and like. I'm not, I'm, you

[00:48:33] **Adam:** Yeah. Are you going

[00:48:34] **Ben:** done games,

[00:48:35] **Adam:** what's going to be really interesting about that is how are you going to build snake in CFML?

[00:48:39] **Tim:** Right.

[00:48:40] **Ben:** It just refreshes. There's a meta tag that refreshes every second. Yeah.

[00:48:47] **Tim:** the white space program and see if you got any interesting comments.

[00:48:51] **Carol:** Yeah.

[00:48:52] **Tim:** You, you may like being protecting Powerball numbers and not even know it.

[00:48:56] **Ben:** Well, it'd be interesting too, is you could take the white space and then gzip compress it,

[00:49:03] **Adam:** Yeah.

[00:49:04] **Ben:** and it's basically, you know, three care, I guess it's really just combinations of spaces and tabs. And line breaks, I mean, cause you have a, a, a massive document that compresses down to like

[00:49:16] **Adam:** I mean, you're still, it still has to represent, it has to be able

[00:49:19] **Ben:** let's be patterns.

[00:49:20] **Adam:** Yeah. So it's not going to be, you know, if you have a 20 meg whitespace file, it might go down to 200 K or something, but

[00:49:29] **Ben:** Still, that'd be crazy.

[00:49:30] **Adam:** yeah. Okay. Yeah. Okay.

[00:49:32] **Ben:** I don't know why

[00:49:32] **Adam:** Okay. So that's, that's all that is prepared for the

[00:49:35] **Ben:** Yeah. Thank you,

[00:49:36] **Tim:** Yeah. Good job. That was, that was very entertaining.

[00:49:38] **Carol:** Yeah, I enjoyed that. I mean, mostly because I won, but

[00:49:41] **Tim:** Yeah. Your next game should be like a closest to the pin kind of game where you got to get something that's a value related and who can get closest without maybe going over or whatever.

[00:49:53] **Adam:** Yeah.

[00:49:54] **Tim:** Those are always fun.

[00:49:55] **Adam:** I will take that feedback for sure. and I, that's kind of one of the things I've been trying to think about for this season of the podcast is, I want to do games regularly. This is fun and it's a good way to distract ourselves from the negative things going on in the world. So

[00:50:09] **Carol:** I need it, so thank you.

[00:50:12] **Adam:** you're

[00:50:12] **Tim:** That's good.

## [00:50:13] Patreon

[00:50:13] **Adam:** All right, well then, this is the part where I say this episode of Working Code is brought to you by the seventh Circle of Hell, CFML and listeners like you What? No laughs from that one

[00:50:22] **Ben:** sorry. Sorry. I'm thinking about the after show.

[00:50:27] **Adam:** if you're enjoying the show and you wanna make sure that we can keep putting more, more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:50:38] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:50:42] Thanks For Listening!

[00:50:42] **Adam:** today on the after show, we are going to talk about dust storms, presumably in Texas or the Texas area, because only one of us lives in dust storm, part of the country. So, that's probably where that's coming from. the after show is just, you know, the outro music's going to play and the rest of us are who record or, pay for, our Patreon are going to get to keep listening.

[00:51:03] **Adam:** You can go to patreon.com/workingcodepod. And, we would really appreciate it. And you'll get early access to new episodes and more banter from us about totally random stuff. That's going to do it for us this week. We'll catch you next week.

[00:51:17] **Adam:** And until then.

[00:51:19] **Tim:** your five space character tab, seven space characters tab, six space character tabs, four space character tab, two, two tab, four space character tab, tab heart matters. And I did find an online encryptor, so

[00:51:36] **Adam:** Oh, wow. You really did.

[00:51:37] **Tim:** that's, that's actually spells the word heart.

[00:51:39] **Adam:** that's awesome.
