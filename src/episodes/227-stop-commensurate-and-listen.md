---
title: "227: Stop, Commensurate, and Listen"
description: "In this week's episode, Ben, Carol, and Tim are back to discuss picking the right tool for the right job."
date: 2025-08-14
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/227-stop-commensurate-and-listen/id1544142288?i=1000721947038"></iframe>

In this week's episode, Ben, Carol, and Tim are back to discuss picking the right tool for the right job. More specifically, the value of proportionality in effort and resource allocation, questioning when it's appropriate to cut corners versus maintaining high standards, when you should stick to what you know versus learning something new, and when you should pay more attention to context when making decisions.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/227-stop-commensurate-and-listen.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** there is no right tool for the job. There is the right tool for the current team in the current context for the current project,

[00:00:06] **Tim:** Yeah.

[00:00:06] **Carol:** Or for the old team and the old people and their projects and that you. Have to learn it.

[00:00:12] **Tim:** Yeah.

[00:00:13] **Carol:** Yeah.

[00:00:14] **Ben:** speaking for a friend.

[00:00:15] **Tim:** She's

[00:00:16] **Carol:** not

[00:00:16] **Carol:** bitter Not bitter. Just a little.

## [00:00:18] Intro

[00:00:38] **Carol:** All right. Welcome to episode 2 27. no Adam today, so I'll be your host. Yes, I do better anyways, you know, So on today's show, we're gonna talk about stop commiserate and listen. Did I

[00:00:52] **Ben:** You said commiserate.

[00:00:53] **Carol:** See it commiserate.

[00:00:56] **Carol:** Okay. Stop commiserate

[00:00:58] **Ben:** Commensurate.

[00:01:00] **Carol:** Commiserate, nevermind. What do you guys, yeah,

[00:01:03] **Tim:** Yeah. Stop commensurate and listen.

[00:01:06] **Carol:** that's the one we were looking for. But, as always, we'll go with Triumphs and fails.

## [00:01:11] Carol's Fail

[00:01:12] **Carol:** I'm gonna kick us off this week. I'm going with giant fails. You know, you guys have heard me complain for a bit about the people leaving and our team being so much smaller now, and we are finally hitting the point where everything that they were working on needs to go to product.

[00:01:27] **Carol:** So all of their apps that they had spun up and all their services that they had developed and everything, they've been tested to two through two testing cycles is now ready to go to stage for final approval. And I don't even know what the process is doing, more or less how the troubleshoot it or why auth isn't working on it and like what service is missing because.

[00:01:51] **Carol:** We, we typically create these things, right? And we go, we're gonna be here all the way through production. So we remember all the little check boxes and the little config steps that we need to do when we're not there. Suddenly. I don't know what needs to deploy. I don't know what got missed. All I know is you can't log in and I can't fix it yet.

[00:02:13] **Carol:** So it's been a frustrating two days of just troubleshooting other people's applications and having to review code and questioning why things were done, how they were, and having to make decisions on if we move forward or if we pause. And it's a little, a little disheartening right now just trying to get through some of this code.

[00:02:33] **Ben:** This is why the whole, when Elon Musk took over Twitter and fired like 80% of the people or something, and everyone was like, oh, look, Twitter still works. It's, it's such a different world just to let software continue to run than it is to actually build software and get it to work the first time

[00:02:51] **Carol:** Correct. Yeah. That the, these new services, like they're not built the way that we were doing stuff before. Like everything's completely different. I don't even know. And plus it doesn't help that we've made the switch from going to inCloud to back to on-prem. So all of these applications were created running in Azure and now this deployment of it needs to run in HyperV on-prem.

[00:03:16] **Carol:** And that's a whole different like beast in itself of knowing like, well, is this a firewall issue or is it not firewall? Like, is my app broken? Like did it actually get a database for it? Ugh.

[00:03:29] **Ben:** What does on-prem mean in the government context? Is there like a specified vendor or,

[00:03:35] **Carol:** no. We have a data center, so we have a, we actually have our own data center and backs up to another data center and yeah, we have our own hardware, everything. Yeah.

[00:03:45] **Ben:** That's pretty cool.

[00:03:46] **Carol:** on premise. Yeah.

[00:03:48] **Tim:** Yep. The cloud is just off-prem.

[00:03:51] **Carol:** I, that's the way I, that's the way I comprehend it. Yeah. It's this, the same thing I look at in this door versus in someone else's door.

[00:03:58] **Tim:** Yep. Server servers you own or servers you lease

[00:04:02] **Tim:** somewhere else. Yep.

[00:04:04] **Carol:** Yep. So that's me. what about you, Tim? What do you got?

## [00:04:07] Tim's Triumph

[00:04:07] **Carol:** yeah, so I'm, I'm going to go with a triumph, I'm, oh, I'm kind of stretching on this one. I hired, hired another person,

[00:04:15] **Tim:** y Yeah, Hired like two people in less than a month. So it's pretty awesome. But, and I kind like that, know, it's like I didn't even, we, we did put out a rec, we have to put out a rec. Position for Phil Spot, but it's like I already knew who the person was gonna be and I didn't interview him. I, well, I had a conversation with him, kind of casual just to see where he is in his life.

[00:04:35] **Tim:** Person I knew years ago who, didn't really work for us, but did work on our source code at some point. And, was looking for a job. So it's a nice fit when you can kind of help someone out. He's, I mean, the job market right now is absolutely ridiculous. He was just telling me horror stories, but yeah, I had one interview, they had one interview with him and immediately made him an offer and should be starting in a couple weeks.

[00:04:58] **Tim:** So

[00:04:59] **Tim:** that's, it was just nice. 'cause I maybe then, doesn't sound like a triumph to you guys out there, but when you're part of a, our HR is part of the bigger parent company, and so when you have like a big HR. Device, that's what I'm gonna call it. They take forever, ever to do anything. It's like you can't just, just, I've, we're, we're putting in a new requisition and I've been asking for three weeks.

[00:05:25] **Tim:** Can you give me the link to the job posting so I can send this to people? And I've get no response ever. I'm like, this is ridiculous. So, yeah. But anyway, that, that's cool to, to hire new folks, but.

[00:05:38] **Carol:** Well, I mean, you could just transition over to OPM where we handle all the hiring needs of the government.

[00:05:43] **Tim:** Yeah, your, your, your, your last fail really en encouraged me to join that team.

[00:05:48] **Carol:** mean, you don't need a link to get hired, do you? It's fine.

[00:05:52] **Tim:** That's right.

[00:05:53] **Ben:** We interviewed a guy one time at Envision. I was on the, the panel of people who interviewed him and, and he was a very well-known person. I, I won't say names just because, you know, I don't wanna, I don't wanna rub anyone in the wrong way. And, I was, everyone on the panel was immediately like, thumbs up, we gotta get this guy, you know, everyone who has worked with him raves about him.

[00:06:15] **Ben:** And days go by and I think like two weeks go by and I finally get an email from him saying, I just wanna let you know, I've, I'm, I've accepted an offer at another company. And I was like, oh, I'm so sorry to hear that. I, I wish we could have done more. Like, is there anything, you know, that we could have improved with our offers or a counter offer?

[00:06:34] **Ben:** He was like, literally no one ever contacted me after the interview and I was like, what?

[00:06:41] **Tim:** Yeah, yeah, yeah. I,

[00:06:45] **Tim:** I, I missed the days back when, you know, before we were bought. You know, before, prior to 2013, like I just hired someone on the spot. It's like, all right, here's the job. Here's your salary, you take it. We shake hands. It's done right. But now it's like, I'm not allowed to make the offer. You have to have HR do it.

[00:07:02] **Tim:** They have to, you know, there's a whole process like, but they don't do it. It's the dude would that we just hired was email. He emailed me like three times. They're like, Hey, you said I'd heard something by now, but I haven't heard anything. I go, I'm so sorry. I will check. And I'm like, Hey, where are we at?

[00:07:15] **Carol:** And they're like, oh, blah, blah, blah, blah. Like. Full crap. Workday. Workday. Workday,

[00:07:20] **Tim:** yeah.

[00:07:20] **Tim:** Workday. Workday is terrible.

[00:07:22] **Ben:** What is, what is, is It, it, it's It's like a HR software.

[00:07:27] **Carol:** Yeah, it's an HR system. Yeah.

[00:07:29] **Tim:** Yeah. It, yeah. So it's, it's just crazy

[00:07:32] **Tim:** when

[00:07:32] **Carol:** It's like how you make your job offers.

[00:07:34] **Tim:** yeah. So

[00:07:36] **Ben:** I, I've been hearing on various podcasts that. The you listen to podcasts? I, I dabble. I dabbled that people are being inundated with AI driven resumes. Are you finding that in any of your postings or

[00:07:53] **Tim:** Yeah. So when we opened this one up, and I don't know how they found the link 'cause I didn't know where it was. immediately the first day got like 45 apps.

[00:08:02] **Ben:** man.

[00:08:03] **Tim:** Immediately it's like, and, and then every day after that, we would get like a smattering, of like three to four or five, five to six. And it's like, I look at them and it's like, I, I don't know if these are real, you know?

[00:08:15] **Ben:** That's the worst part of all of this is I just feel like I can't trust anything anymore.

[00:08:19] **Tim:** Yeah. a

[00:08:21] **Carol:** it's funny you say that. I was going through and looking at some of the code that wasn't so great today, but in the process I found that some of our agencies have added assessment questions and one of them is like, have you used an LLM to generate any content for your application? You know, that can obviously be a screen out of if you did and you say no, and then it's easy enough to track back LLM data versus what you've written yourself, then suddenly you've screened yourself out from an athlete, from like a job opportunity just by not being honest.

[00:08:53] **Carol:** Yeah. Mm-hmm.

[00:08:55] **Tim:** Interesting. But I mean, how do they prove? Prove that, right,

[00:08:58] **Carol:** That's not my responsibility.

[00:09:00] **Tim:** I don't know if I can tangent.

[00:09:03] **Carol:** Yeah.

[00:09:04] **Ben:** Please.

[00:09:04] **Tim:** I could channel Ben a tangent. so on our discord, and if you're not on a discord, you should check it out. It's it's very, it's very quite busy. so, so one of the people on the Discord, they are looking for a new job.

[00:09:15] **Tim:** They unfortunately got laid off and they wanted to like, brush up on their interview skills. And so I agreed to meet with them and met with them. I think it was last Friday. And, they sent me the resume. I popped, you know, and then I interviewed them and it was, it went pretty good. They were like, oh, wow.

[00:09:32] **Tim:** These are really good questions. To be honest, I didn't actually read. Resume I threw 'cause it's, it's like there's a whole bunch of stuff I don't, I'm not a subject matter expert on anyway,

[00:09:41] **Tim:** so I threw it into chat GPT and I'm like, build me, a question answer in a rubric for this hire

[00:09:47] **Tim:** to see if I, if I could tell.

[00:09:49] **Tim:** And it came up with some really darn good questions and, you know, time box within 30 minutes. And, and so I, you know, but I did have some. Some advice for them, on how to, because sometimes, you know, they would be very quick to answer the question. I'm like, take your time. Answering the question right, that you, they asked the question.

[00:10:08] **Tim:** You don't do a knee jerk kind of do reflective listening. Maybe repeat the question back to them to make sure you understood it. 'cause I could tell that sometimes there were times when they didn't fully understand what I was asking.

[00:10:18] **Carol:** Sure.

[00:10:20] **Tim:** They just, they, they were like just their mouth engaged and the brain was in the background processing going, what was this thing that he said?

[00:10:27] **Tim:** and and then answered it. You could just, you could, as an interview, you could tell that, that like they're answering the question, but at the same time they're Ming and hawing and so I. If you're, you know, grading, you're gonna naturally just grade down on that. So, but yeah, overall it went really well. I think hopefully they got some good, good advice out of it.

[00:10:44] **Tim:** So yeah, if you're on Discord and you, looking for a job and wanna, wanna do that, I'll be happy to do that. Or just do what I did, throw it into chat, GPT and trial, run it. But it's always good to actually physically talk to someone, so,

[00:10:57] **Carol:** It takes some of the nerves out of it. If you can just get face to face with someone, even on a video call and just say, okay,

[00:11:03] **Tim:** Yeah.

[00:11:03] **Carol:** makes it feel less intense when you do it the next time.

[00:11:06] **Tim:** Yeah. Yeah. So if you're gonna fail, fail in front of, you know, the, the, the practice firing squad, not with live ammunition.

[00:11:13] **Tim:** So, anyway, that's me. Adam's not here. So Ben, what you up to?

## [00:11:18] Bens' Fail

[00:11:18] **Ben:** I'm gonna go with a, fail is not the right word, but just sadness in my life. my, I had mentioned on a previous episode that my dog had been diagnosed.bone marrow cancer. And then we actually thought maybe it was, an autoimmune disease because she had actually responded pretty well to a course of steroids.

[00:11:38] **Ben:** But, unfortunately it probably was cancer in the long run. And she declined really quickly out of nowhere. And,

[00:11:45] **Carol:** Oh no.

[00:11:45] **Ben:** her organs went into the, basically her organs started shutting down. We were supposed to, we had a vet appointment this past Monday. To not, not Monday, yesterday, Monday, a week ago, to, to, put her down.

[00:12:00] **Ben:** But we actually didn't even make it that long. Sunday. She just started to like, get very agitated, you know, she, she hadn't been in any pain, but then Sunday afternoon she started walking all around the house and trying to burrow into different rugs, into different beds and just couldn't get comfortable.

[00:12:16] **Ben:** So we ended up taking her to the emergency room.

[00:12:19] **Carol:** Oh

[00:12:20] **Ben:** she went out peacefully. She was, she didn't seem to be in any pain. And normally when we take her to the vet, she's very anxious, you know, all the smells and

[00:12:28] **Carol:** yeah.

[00:12:28] **Ben:** the hormones, you know, floating around in the air. She gets very angry. And we brought her and she was just laid there and she was very peaceful.

[00:12:35] **Ben:** And so I think, I think the timing of everything worked out really well. So I'm gonna call that a triumph. Like I think we handled the whole thing, as, as, as well as we could have handled it. So, but. It's been very sad and just trying to figure out what life looks like now. And we actually went to, me and my wife went to, a, a, a a couples counselor this week yesterday just to like.

[00:13:00] **Ben:** You know, this dog was, took up the oxygen in the room for 13 years and like, how do we communicate now when everything that we've really talked about in the last 13 years was like, where are we gonna take the dog? Has the dog eaten? Did the dog poo? How good was the poo? You know, oh, her poo wasn't great.

[00:13:17] **Ben:** Well, what did we feed her earlier that we shouldn't feed her again? You know, like that's been our life. So now it's more like, how do we. Rediscover how to be married and and

[00:13:27] **Tim:** Did they say get a, did they say get another dog?

[00:13:30] **Ben:** That's what my mom said. Mom's like, just get another dog immediately.

[00:13:34] **Carol:** No,

[00:13:35] **Ben:** But

[00:13:35] **Tim:** I'm

[00:13:36] **Tim:** so sorry.

[00:13:36] **Tim:** Ben.

[00:13:37] **Ben:** thank you. I

[00:13:38] **Tim:** So sorry that, that's actually why we didn't record last week out of, out of respect for passing of Lucy. So.

[00:13:44] **Ben:** I appreciate that. She did get, she did get one more bed hump in the day before.

[00:13:49] **Tim:** good, good for

[00:13:50] **Ben:** it on video. It was very exciting. It was her, she, you know, she lived, she lived hard

[00:13:57] **Tim:** yeah.

[00:13:58] **Ben:** and then died

[00:13:58] **Carol:** And horny,

[00:13:59] **Ben:** Yeah.

[00:14:00] **Tim:** yeah. See, that's kind of why, my wife, I, it was, I don't know, my wife doesn't know this, but I buy a pug every seven years. I,

[00:14:10] **Carol:** Just to keep a rotation

[00:14:12] **Tim:** Yeah. Just to keep a rotation going. Yeah.

[00:14:16] **Tim:** As, as, as our boy dog. 'cause I got the dog, you know, when my wife was diagnosed with, with bipolar and I got the dog for her then.

[00:14:24] **Tim:** And then it's like, I'm like, how long these things live. I'm like, okay, time to buy another one. And that way we just keep rotating them out.I'm not telling you to do that, Ben. I, I know your, your pain is fresh, so, but yeah.

[00:14:38] **Ben:** It's, it's, it was, it was, but, so it's been a little over a week now and it's just, it was a tough week. I do feel like. When I think about her now, it's a joyful thought. You know, it's, it's bittersweet, but it's, it's, I think about her as a, as a good memory.

[00:14:53] **Tim:** Good.

[00:14:54] **Ben:** but it's weird, like the house is so quiet, you don't realize how much noise dogs make.

[00:14:59] **Ben:** It's just like, you know, snoring and drinking and tick, tick, tick, tick, tick, walking around the house. There's

[00:15:06] **Carol:** The little collar ding.

[00:15:07] **Ben:** Yeah, there's just so much white noise. And now that, now that it's just the two of us. So quiet.

[00:15:15] **Carol:** Yeah. I think it may have been about two years ago, Ruby decided that she was going to eat a rope and, Not a good day. It was a bad, bad day. Ended up in the ER with her, getting her like looked at, they kept her, you know, they were like, oh, we're gonna watch, we may have to do surgery. Like this isn't good.

[00:15:31] **Carol:** It could block up her stomach. She literally has this rope toy stuck in her belly. Right. And when I left her, I went home and like as I'm just picking up every toy around the house that she had drug out, I'm just. Crying my eyes out at the, what if this dog doesn't come back? How am I supposed to deal with no squeaks in my life?

[00:15:51] **Carol:** Like I don't even know, like how they exist without her now. Like to go from a farm where animals serve a job or they get put down to, she's a equal with my child. And I don't know who I would take a bullet for first. That I don't know, like, I'm like, you've lived, she hasn't, you know, like, yeah, I get it.

[00:16:12] **Carol:** It's hard. Not, not where you wanna be at, but I hope it gets easier, man.

[00:16:16] **Ben:** Yeah. Well, it's funny because it, it's such a life adjustment, just, just every little activity. So we didn't, say, let's say we would have the dog in the car and we'd be going out. And then we wanna go into a store, like go into the supermarket or something. If we both wanted stuff, my wife would go in and I'd stay in the car with the dog and then she'd come back and then I'd go in and she'd stay with the dog.

[00:16:38] **Ben:** And now we'll start to do that. And then one of us will be like, wait,

[00:16:42] **Tim:** Oh, wait, we can go together.

[00:16:43] **Ben:** go in.

[00:16:44] **Tim:** That's, that's funny.

[00:16:47] **Tim:** Oh,

[00:16:49] **Tim:** yeah.

[00:16:49] **Ben:** yeah. But, I'm back and just, Getting through my days right now, so I'm happy to see you. I'm happy to see familiar faces

[00:16:56] **Carol:** yeah.

[00:16:57] **Tim:** Yeah. Good to see you, man. So,

[00:16:59] **Carol:** right.

## [00:16:59] Stop, Commensurate, and Listen

[00:16:59] **Carol:** So what we talking about? Somebody else say, this works clearly, I got it all wrong and I don't even know what it means.

[00:17:05] **Tim:** commensurate.

[00:17:06] **Ben:** commensurate. Yeah, so this was a word I had never, I don't think I'd ever even heard of it before until there was a whole season of Curb Your Enthusiasm with Larry David and Lin Manuel Miranda. And, the backstory there, having nothing to do with the topic of the show is that Larry Wrongs, Lin Manuel and Lin Manuel constantly wants an apology.

[00:17:27] **Ben:** And every apology that Larry David offers up, Lin Manuel complains that it's not commensurate with the offense. And it, and it's becomes this ongoing multi episode arc about doing things that are commensurate. So,

[00:17:39] **Tim:** Okay, now. Now I gotta hear the code tie in.

[00:17:41] **Ben:** So, so the, the, you know, to, to say it in another way, it's proportionality like doing things in proportion with, with, the need.

[00:17:49] **Ben:** And I've been thinking obviously a lot about AI as I think a lot of other people have, but just generally about programming, because I'm working on a little side project and it has no framework, which is to say it has a homegrown framework, and it has no tests. And, you know, the, the, there's basically,

[00:18:07] **Tim:** So you're right at home.

[00:18:08] **Ben:** I'm right at home. I'm right, I'm right in my comfort zone. But it, it's gotten me thinking about doing things that are proportional to the requirements and I think that that's very uncomfortable for people in general. I think that's very, I, I can speak for myself that I tend to wanna find the one way to do things like this is the one database I like to use and this is the one server side language I like to use.

[00:18:34] **Ben:** And this is the one JavaScript framework I. And, and I, I just like consistency for the sake of consistency, and I think a lot of people do. And, and, I just don't, I don't understand what it is in myself that it's so challenged by this idea that you don't actually have to do it the same way all the time because not everything merits the same amount of effort.

[00:19:01] **Ben:** I almost wonder if it's like a, a code, not code, smells not the right word, but if it's like a litmus test or an indicator that I don't feel comfortable being able to make a decision about how much work and effort should be put in. So I lean on the idea that there is a, like a one way, a cookie cutter approach to problem solving so that I don't feel like I have to have that, Degree of critical thinking. And I mean, that's, that's putting maybe too negative a slant on it. But, I don't know. I mean, do you guys, how do you feel about consistency for the sake of consistency? Do you find yourselves being able to cut corners when it feels like it's okay? Or do you, do you always wanna do the same thing?

[00:19:44] **Carol:** So for me, I have a hard time with the cutting corner parts, period. Like I get in there and like today I'm looking at this code and all I need to do, all I need to do is wire up app insights. That's it. They forgot to put the, the piece for like app insights

[00:20:02] **Ben:** Is that like an analytics

[00:20:03] **Carol:** Yeah. It is Azure app inside so that it logs everything to like our centralized logging

[00:20:09] **Tim:** Like a fusion react.

[00:20:10] **Carol:** yeah.

[00:20:10] **Carol:** Yeah. So I get in there and I immediately go. Why are they not like cascading the build at like process here? Like why are they calling Build on their app and then doing a bunch of stuff and then calling Run? Like everything should be function driven, everything should be clearly laid out. And all I wanna do is just go rewrite everything they've done and this specific piece of the API and I go.

[00:20:33] **Carol:** Okay, just stop a back. We need to like, just put in that inside. So for me, like I don't wanna cut the corners. And one thing you said was, you know, consistency for the safe sake of consistency. But yet like. I find my customers want change just for the sake of change. Sometimes I'm like, well, tell me why.

[00:20:53] **Carol:** What you're wanting even makes sense. Like, you know, like what we're doing works. Like let me just adjust maybe a column. Let me give you a little bit more data, and you have, instead you want like a whole new endpoint to get it a whole new way. And I'm going just keep it working. Just keep it working. Yeah.

[00:21:11] **Tim:** So Ben, I, I'm not sure if, if I understand your problem statement, so let me just kind of quiz you on that. So, is this where you're attacking? It's a new problem. You don't really know how to attack the problem, but you're natural leaning is to, well, here's how I attack every other problem. So I'm gonna apply that regimen. To this problem, and hopefully it'll work out. And if it doesn't, I'll just kind of cut corners a little bit. I, I don't,

## [00:21:41] Adjusting to Contexts

[00:21:41] **Ben:** Yeah, I, I think it's, I think it's definitely, it's a, it's, it is that, I don't know how to articulate it other than through, I guess maybe more concrete examples. So a couple of episodes ago I talked about participating in the Adobe Cold Fusion 2025 hackathon, and one of the things, or one of the features that I included in my hackathon submission was this ability to.

[00:22:07] **Ben:** Write the user data to user specific CSV or comma separated value files, and it's a hackathon submission. It will never run in production anywhere. I don't think it ran anywhere, period, other than in my local development environment. And as I was building it, I kept thinking to myself. I should probably add some sort of rate limiting here.

[00:22:28] **Ben:** Or like what if I have a thousand users and, and or you know, thousands users and they start to write all these CSV files. Do I have to write a background tasks to clean up these datas? And it's like, that's the kind of thought you would have in a production grade build. It's, and it's like my brain couldn't stop and say, dude, this is a hackathon submission.

[00:22:50] **Ben:** You don't have to worry about rate limiting. You don't have to worry about protecting the file server. There's no file server that this will ever be running on. But it's, it's things of that nature. It's the, Hey, I wanna put up a welcome page. Do I want to drop in a a cold box content management system, or do I wanna just deliver an index CFM file?

[00:23:10] **Ben:** It's like you might only be used to building applications with ColdBox, so that's just your default, you know, command box, install ColdBox kind of a thing, and now you have a thousand files to deliver up a, you know, coming soon. Yeah. You know, or, or like, you know, any, anything to that effect where it's, it's like I don't have, I don't have good decision tools to say, Hey.

[00:23:34] **Ben:** This is not the quote unquote normal context, so I don't have to put in the quote unquote normal amount of work. And I find it very hard to just deviate and I, and I, and I don't know, I just don't know. Part, part of why I've been thinking about this a lot is because, there's been a tremendous amount of talk in the, in the ether, in the tech space about all of the vibe coding and the AI agentic code generation.

[00:24:02] **Ben:** Some people have this conversation and they'll call things like, well, I heard one person called like cousin wear,

[00:24:09] **Carol:** What.

[00:24:10] **Ben:** you're gonna have the AI generate code because the only person who will ever run it is your cousin. And like, it'll never have to run in any kind of unsafe context. So like, who cares what the code looks like?

[00:24:20] **Ben:** It's kind of a, a run once and throw it away kind of thing and, and like, but the problem is, is. In that context. Sure, it makes sense. If you're gonna, you don't even have to look at the code. Who cares if it's secure? It's just for personal use. But then there are people who are using the ag agentic coding for much more production oriented things.

[00:24:40] **Ben:** And, and I can't, I can't kind of see those two different lenses. Like in my mind it's all just ag agentic co-generation. But if. I guess again, it's like there's nothing proportionality in the way that I'm consuming it and thinking about it, if you were to say, Hey, I'm gonna write this script once and never run it again, I still get like a, like a tumtum feeling like, oh, what if the code's unsafe?

[00:25:05] **Ben:** And like, what if it has, you know, a sequel injection vulnerabilities? You're like, dude, it is like, we'll literally never run anywhere public. You're like, oh, but I know, but what about the underlying code?

[00:25:18] **Tim:** Yeah. It's funny what the problem you're describing to me almost sounds a bit like the use case. Not problem with, with ai, you have to give the AI a good context window. So in your first example, your context window, this is a proof of concept for a hackathon, I just need to show that this thing that I'm trying to achieve is, is workable in the least amount of, you know, possible way.

[00:25:43] **Tim:** I'm not right. So that's the context window. So you don't care about security. You don't care about scalability. That's the context window. And so therefore, it's like you don't need all those things that, that the, the things you're, you're throwing away, they're commensurate to the problem because the context window says you don't need those because that's will never be used that way. The same thing with, with production. It's like you have to give the AI a good context window of here's what we're doing, here's the situation, here's what needs to be thought about, you know, and go do it. If you don't give it that good context window, perhaps it's gonna give you an unsafe information, right?

[00:26:20] **Ben:** Yeah,

[00:26:22] **Tim:** So it's almost as if, you're, you're working like an AI and you just gotta figure out what your context window is in this particular situation.

[00:26:30] **Tim:** For the problem.

[00:26:31] **Ben:** so, and, and you know, I don't want to, AI is, I think what keeps a lot of this hamming and hawing front of mind for me, but it's certainly not ai. Specific, I think we've joked about it on the past, on past episodes where you'll go to a GitHub repository for a, a single JavaScript file that has one function that does something small.

[00:26:53] **Ben:** But you look at the GitHub repository and it's like 17 files because they have an editor file and an ES lint file and like a ts config file and you know, a read me and a contributing doc and, and, what's the one where you're talking about how people can behave? What's that one?

[00:27:09] **Carol:** Like rules of behavior.

[00:27:10] **Ben:** anyway, it, it, it's like, it's like that's not proportional with the file that you were trying to publish, you know? It's like, why do you need an editor config for a 10 line JavaScript file? I mean, that seems crazy to me. Like, can you not just buy muscle memory, write a couple of lines of code without having something auto formatted for you?

## [00:27:29] Picking the Right Tool for the Job

[00:27:29] **Ben:** I mean, you know, now we're, I don't wanna, I don't wanna yuck anyone's, yum. But I, I just, it's like, I think we, again, I can speak really only for myself here, but I think it probably pertains to other people. It's like I get so locked in to the way I like to do a particular thing, that there is no proportionality to how I apply that thing. I, I don't know. I mean, I don't have any like, deeper thought other than I'm, I'm frustrated by the fact that, that that's happening.

[00:27:56] **Tim:** it's, it's like the old, proverbial when the only tool you have is a hammer.

[00:28:00] **Ben:** Yes. Everything looks like a nail.

[00:28:02] **Tim:** Yep. So if the only code you love is cold fusion, then

[00:28:07] **Ben:** yo. Then everything could be a ColdFusion app.

[00:28:10] **Tim:** exactly.

[00:28:11] **Ben:** I was, so I was listening to a podcast, I don't know, maybe two weeks ago. Someone was talking about, they were building a small proof of concept application. This was not coefficient. I think this was in Node or something or, or maybe it was a live wire, PHP live wire kind of a thing.

[00:28:27] **Ben:** And they may, they alluded to the idea that they were just going to an index file and then using query string parameters in the URL to dictate what the page should do as opposed

[00:28:39] **Tim:** Oh, that sounds like good sequel injection problem

[00:28:42] **Ben:** No, but they, and they called it like, oh yeah, this is old school, like query string usage. I'm like. I'm like, what old school?

[00:28:50] **Ben:** Like literally that's how URLs work. Like, I don't know, the fact that you called it old school just makes me like, it made me angry in the moment. I'm like, oh, I'm sorry. You don't have like funky, route-based nesting in your next JS app and suddenly you think that's the only way web apps can work is with this fancy S-E-S-U-R-L schemas.

[00:29:11] **Ben:** I, I, I dunno. But it is like that kind of thing where you're like. Well, the URL parameters worked perfectly well for your application. So why do you think that's bad? Like, that was sufficient? I, I don't know. I don't know. I'm, I guess it, it's like, it, it makes me angry that I don't know. I dunno. I'm just having a lot of feelings.

[00:29:32] **Ben:** I'm

[00:29:32] **Tim:** Ben has feels,

[00:29:35] **Ben:** Like I think about, event sourcing. Have you guys heard of the term event sourcing?

[00:29:40] **Carol:** wait. What does that mean?

[00:29:41] **Ben:** I, I don't think I could even fully explain it exactly. The event sourcing my understanding in the, in the lightest weight sense is that what your application does, instead of storing database records per se, it stores events about how that data changes over time.

[00:29:59] **Ben:** So you would store an event for like contact created and store another event for contact updated. And the idea is that you could blow away your whole database and just replay all of your events from the beginning of time and you'd come up with the same thing. And there are people who just swear by event sourcing, like, this is the only way to build stuff.

[00:30:17] **Ben:** And, and it's like, again, one of those things where like, yeah, that's the only way to build stuff if you're building a very complicated application, but not anything that most people deal with.

[00:30:27] **Tim:** What's the context right?

[00:30:29] **Ben:** Yeah. Yeah, exactly. And I dunno,

[00:30:33] **Carol:** I can't even think of a place I would wanna use that.

[00:30:36] **Ben:** it just, it, it, I, I've never used it myself, but it just, it seems to fall apart in my head every time I hear someone explain it.

[00:30:44] **Tim:** Where are they stor? Where is they storing the event? Sourcing

[00:30:47] **Tim:** can't be in the database 'cause you

[00:30:49] **Tim:** wiped it out.

[00:30:49] **Carol:** away.

[00:30:50] **Ben:** yeah, I think, I mean, Kafka. I think is the, is like the main event sourcing type of data system. I think it was created by LinkedIn.but I, the, I don't know, it, it makes no sense to me. I mean, it doesn't, not, it doesn't make no sense, but it makes it, again, it doesn't seem commensurate with most of the problems that people deal with, I think.

[00:31:12] **Tim:** Yep.

[00:31:12] **Ben:** That's not to focus on that. It's more just like, it's like everywhere I see people deciding how to do things, technology-wise, myself included, it's just this, there's such a momentum. And the worst part is that I think when we, we give into that momentum can make, it just makes other people feel bad. And I, again, I can only speak about myself, but you know, for people who want to build like, Every single little piece of web, of web property in React and then make me feel like an idiot because I don't like react and like I can just put up a static HTML file and accomplish, you know, something small and it's just like, now I feel like an idiot because what am I not seeing that you're seeing?

[00:31:56] **Ben:** But I feel like you're the idiot who thinks you need react to build a tiny little page.

[00:32:01] **Carol:** Yeah, I think my issue is that I get comfortable in what I know, so then I just wanna kind of keep doing that over and over. Right. So. I don't wanna go learn, react. I don't wanna have to go introduce it unless I know I'm gonna support it and going to keep doing it. So.

[00:32:18] **Tim:** Yeah. And then the opposite, opposite side is use boring technology. Right?

[00:32:23] **Tim:** And boring. What's boring for one person is not boring for another. Yeah.

[00:32:26] **Ben:** Right. And I think that's always the key to it, is that there is so much subjectivity and so much of what we do, that there is no, we've talked about this before, there is no right tool for the job. There is the right tool for the current team in the current context for the current project,

[00:32:42] **Tim:** Yeah.

[00:32:43] **Carol:** Or for the old team and the old people and their projects and that you. Have to learn it.

[00:32:49] **Tim:** Yeah.

[00:32:50] **Carol:** Yeah.

[00:32:50] **Ben:** speaking for a friend.

[00:32:52] **Tim:** She's not

[00:32:52] **Carol:** bitter Not bitter. Just a little.

[00:32:55] **Tim:** All right.

[00:32:55] **Ben:** I don't, I don't, yeah, I don't have much more to say about it other than, this is just something I've been thinking a lot about.

[00:33:00] **Tim:** All right. Well bring us home, Carol.

## [00:33:03] Patreon

[00:33:03] **Carol:** All right, so this episode of Working Go was brought to you by people who commiserate and listeners like you. If you enjoy the show and you wanna make sure we could keep putting more of whatever this is out to the universe, you could consider supporting us on Patreon. Our Patreons cover, our recording, editing and transcription costs, and we couldn't do it every week without them.

[00:33:23] **Carol:** Special thanks to top Patreons, Monte and Giancarlo

## [00:33:27] Thanks For Listening!

[00:33:27] **Carol:** and the after show teasers are, are we skipping the after show?

[00:33:31] **Ben:** I think we should just, I think it's bedtime.

[00:33:33] **Tim:** Oh,

[00:33:34] **Tim:** come on Ben.

[00:33:35] **Ben:** All right. You want a little bit of after show,

[00:33:37] **Tim:** bit after show.

[00:33:37] **Tim:** Come on

[00:33:38] **Carol:** I got a teaser. You just gonna have to go pop in to figure out what we're gonna talk about.

[00:33:42] **Tim:** He gotta find out.

[00:33:44] **Tim:** Sometimes it's sometimes note tease is the biggest

[00:33:46] **Carol:** Ooh. Okay. Well we're not teasing you this week. Come listen, if you'd like to help us out, you can join our Discord at workingcode.dev/discord and come have some conversations with us.

[00:33:58] **Carol:** that's it for this week. We'll catch you again next week, and until then.

[00:34:02] **Tim:** Remember. Here's the context window about this show. We are four developers, senior developers who've been around a long time that decided to create a podcast. That kind of simulated just being in the office, hanging out and talking about code, not talking about work necessarily. Not talking about code necessarily.

[00:34:23] **Tim:** Just kind of that, that work code relationship where you're just nerding out with your friends about things. That's the context window. And in that context window, I want you to know one thing and one thing above all. Heart matters,
