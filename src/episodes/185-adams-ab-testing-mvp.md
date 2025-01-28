---
title: "185: Adam's A/B Testing MVP"
description: "On this week's show, Adam and Ben explore the complexities of implementing AB testing in email campaigns."
date: 2024-07-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/185-adams-a-b-testing-mvp/id1544142288?i=1000661085534"></iframe>

On this week's show, Adam and Ben explore the complexities of implementing AB testing in email campaigns.

The hosts tackle the challenge of integrating AB testing into existing systems without causing disruptions and examine methods for experimenting with various elements like subject lines, calls-to-action, and email contents. They also discuss strategies for automating the selection of winning variants based on metrics such as opens and clicks.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/185-adams-ab-testing-mvp.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** and I'll look at our, our email statistics and I'll see somebody open an email and I'm like, what the heck did they open? We didn't send any emails today. And you look and you're like, Oh, this is from the email that we sent three weeks ago

[00:00:09] **Adam:** since we're doing like click tracking and all that stuff, it, what, what really blows my mind is like people still clicking links from messages they received like two years

[00:00:17] **Ben:** Yeah. It's like how, how people will go to Google and Google for Facebook. com.

[00:00:23] **Adam:** Yeah.

[00:00:23] **Ben:** Right?

## [00:00:44] Intro

[00:00:44] **Adam:** Here we go to show number 185. And on today's show, we're going to talk about AB testing. it's myself and Ben again. Carol was going to join us, but, she had a fire at work. So not able to make it. Tim is still living the life in, in Ireland, hanging out with family, taking time off. So it's just me and Ben again.

[00:01:02] **Adam:** Hello again, Mr. Mr. Nadel.

[00:01:05] **Ben:** Good to see you, sir.

[00:01:06] **Adam:** All right. but first, as usual, we will start with the triumphs and fails. As I said, Carol and Tim are not here. Somewhat excused absences. We'll give them a little slack. Ben, you went first last week, so I'll go first this week.

## [00:01:18] Adam's Triumph

[00:01:18] **Adam:** and I'm going to start us off with a triumph, which is that, as actually as of today, like today was the day that it happened, I wrote and delivered my first ever performance review from like a supervisory type position, which is yeah, I, I talked previously about how I wrote a performance review for Steve, my CEO, you know, months back as part of the SOC 2 thing, which was like, you know, half genuine, half joke.

[00:01:44] **Ben:** Yeah, yeah, yeah. You ended on a very tongue in cheek, I'll, I'll allow you to be my boss for another year kind of a

[00:01:50] **Adam:** yeah, yeah. but this one was like legit. Now, having said that, it was, halfway through, so he's engaged with us for six months. That's his contract. And so this was like a three month sort of check in, you know, they, I guess they encourage you to do a three month, you know, midpoint review with them.

[00:02:08] **Adam:** the, the university that he's doing this program

[00:02:10] **Ben:** Oh, this is for the, the co op attorney guy?

[00:02:13] **Adam:** Exactly. Yeah. So yeah, to catch anybody up who may not have heard everything. So my company hired a co op, which is kind of like an intern, but, but different, a little bit more, technical, whereas we're not sending this guy out for coffee, right.

[00:02:25] **Adam:** He's writing tests and, and writing code. and. it's for a six month engagement. His first day was April 1st. His last day will be sometime in like mid to late September. and

[00:02:35] **Ben:** in school at this time? I can't remember.

[00:02:37] **Adam:** it's, it's, you know, it's a very interesting program. So he attends Drexel University. and the way that their program, their like computer science program is structured is, co ops.

[00:02:47] **Adam:** These like, you know, on the job experience things are part of the curriculum in such a way that like you do, there's a couple of different ways they could break it down, but it's, you can, you can kind of do like, I think it's, you can do five years with three co ops or you can do four years with two co ops or something like that.

[00:03:05] **Adam:** But, but is he, is he taking classes simultaneously or he's dedicated to the work study and then he goes back to classes after the six months kind of a thing?

[00:03:14] **Adam:** he did finish up one class. I don't know how the schedule works, but like he did a week or two ago have his final exam for like one class that he was taking that was overlapping with the co op. But I think the general structure is like you take a semester. Where you do academic courses, learning, prepare you for workforce stuff.

[00:03:31] **Adam:** And you do a semester where you're working on the job for somebody, and then you do another semester of school and another semester of a co op and another semester of school sort of situation.and it's very interesting because it gives them a lot of like real world experience before they even graduate.

[00:03:45] **Ben:** Yeah. That's

[00:03:46] **Adam:** it's, I would say that it, It does put a little more of the onus on us, the hiring company, to make sure that they have the skills that we need them to have before we hire them.

[00:03:55] **Adam:** We have to be a little more, I don't know, I hesitate to say we have to be more comfortable or more careful in the interview process because, you know, you need to be looking for these things anyway, but I guess there's a little bit less of an expectation or an assumption that they will have these skills.

[00:04:10] **Adam:** By the time they show up for the interview, right? Because potentially this is somebody who has like one semester of college under their belt. I believe that's the situation that we're in. I think that the guy that we hired, does have just like maybe a year or two, into college and this is his first co op.

[00:04:28] **Adam:** So, it's been, but you know, I've been very happy. We've been very pleased. his review went very, very well for him, which I think,

[00:04:35] **Ben:** get back to the review. I, I, I tangent to this.

[00:04:37] **Adam:** it's, I'm going to say the thing that I always say, and I can't not comment on it now. It's funny because I feel like he, made it too easy for me, right?

[00:04:47] **Adam:** Like he's just good. He's a junior developer. Expectations are pretty low, but, you know, like all of the,

[00:04:54] **Ben:** managed, not

[00:04:56] **Adam:** yeah, yeah,

[00:04:58] **Ben:** Expectations low sounds, sounds, Icky. Okay.

[00:05:08] **Adam:** The bar that I'm expecting him to be able to clear is not as high as it would be if he

[00:05:13] **Ben:** There you go. There you go.

[00:05:14] **Adam:** engineer or a senior engineer sort of thing.and, He easily did like, you know, meets expectations or better in everything. And so, you know, it wasn't, it wasn't a difficult emotional experience for me to have to deliver this, right.

[00:05:30] **Adam:** He made it easy for me in that regard. so I guess that it was a nice on ramp for me and, and it's just, it was a very pleasant experience overall. I wrote this thing up, you know, I did a lot of research. I read a bunch of different articles and guides on how to do performance views. Well. and put a lot of thought, it was like a four page document that I wrote.

[00:05:51] **Adam:** and, and then I had Steve review it. Yeah, I had Steve review it and I had, like my engineering management mentor review it. And both of them were like, this is, this is good. You know, it's, it's, it's not short of glowing, but a very positive review. It's balanced. And, and yeah, so it was just, I was very happy with that.

[00:06:13] **Adam:** And, you know, on one hand I was like, Okay, so I did a good job. That's great. But like, you haven't given me any advice on how to do better, right? Like there's no way I was perfect. And I certainly felt in the, in the conversation portion, right? So I wrote the document. That's easy because I can edit and review that and go over it 50 times.

[00:06:34] **Adam:** You can't do that with the conversational portion, right? You have to sit down and have the conversation. Try to sound like you know what you're talking about. Try not to rush through it. Try not to trample and leave room for their feedback and their comments. It's a wild experience, and I'm, I'm excited for more of it.

[00:06:52] **Adam:** So

## [00:06:52] Giving Constructive Feedback

[00:06:52] **Ben:** Yo, very cool. I, I feel like one of my biggest weaknesses historically in my career is I am not great at giving constructive feedback to people. And it's, I really, really wish that I was better at it because I think giving people constructive criticism is actually a very generous thing to do, especially if you can land it well in a way that balances the, I'm not trying to demean what you do here, but I, you know, like, I see potential.

[00:07:23] **Ben:** I just want you to reach that potential. And, I, I've sort of always erred on the side of letting people explore. A bad approach with the assumption that the badness of the approach will just come to light eventually. Like it'll become self evident that that was the wrong thing to do.but I, I, I think on one hand you could argue, oh, it's nice to give people some wiggle room, but on the other hand, I definitely do that more out of my own insecurities than I do out of a sense of generosity to, you know, go forth and explore and have fun.

[00:07:56] **Ben:** It's, it's, it's definitely something I've, always wanted to be much, much better at.

[00:08:02] **Adam:** it's emotionally easier to say nothing than to correct somebody. I mean, go ahead.

[00:08:07] **Ben:** I just, like, I sweat, I sweat how good people are at it sometimes. And I know that this is ridiculous to mention this because this is a fictional character, but I watched something like 16 seasons of Grey's Anatomy. And, and the chief of surgery, this guy, I think his name is Richard Webb, you know, a fictional character on the show.

[00:08:27] **Ben:** He was so freaking good at this. It was in a single conversation. He could go from being your best buddy to being a disciplinarian, then right back to being your best buddy. And everybody just went with it. And I would watch him like, dang, how am I, how can I build up a mentality where I can be more like.

[00:08:45] **Ben:** Richard Webb, and I, I've just never been able to do it.

[00:08:48] **Adam:** Well, what you need to do is get a full room of highly paid Hollywood writers.

[00:08:54] **Ben:** Yeah, that's right. I need a ghostwriter for my, mentoring.

[00:08:58] **Adam:** Right, but you need that in your brain so you can have it real time, and you need to, you know, 12 takes, again, and just right.

[00:09:05] **Ben:** Yeah,

[00:09:06] **Adam:** So I wanted to go back to, you know, you talked about giving feedback can be difficult and there were a couple of things that I kind of, I guess I instinctively knew a little bit, but like in my research about, engineering management and, and performance evaluations in particular that came up that, that really struck a chord with me that I liked.

[00:09:24] **Adam:** One of them was about, avoid the sandwich, right? Like that's sort of a, a, like a trope in a bad way, right? which is where you, you give a piece of good feedback and then a piece of bad feedback and then a piece of good feedback so that the person kind of doesn't see it coming and then can, can rebound with you on the good feedback.

[00:09:42] **Adam:** and, and everybody sees right through that now. And so, you know, I feel like it's, I don't know what, there's a word, there's like a phrase for describing that that's not coming to me, but I,

[00:09:52] **Ben:** Cliche? Well, I

[00:09:54] **Adam:** maybe that's a good one. You know, we'll go with that, sure. but, but like, you know, everybody sees through it, so it's just, it's kind of a, it's not recommended anymore.

[00:10:01] **Adam:** The other one was about like vulnerability, right? So, when you're giving somebody feedback, you're asking them to be vulnerable, to accept that feedback graciously. And, Take it as what it's meant to be, what it's hopefully meant to be, which is constructive and like, you know, this is something that you're not doing as good as you should be or could be.

[00:10:22] **Adam:** and, and here, hopefully some advice on how to work on that. Right. And so to make it easier for that person to be vulnerable, to accept that feedback, it is a good idea to demonstrate the vulnerability yourself and, and kind of broadly across the team in. Internally public spaces, right? So in, in like team chat, make it the norm to, not, not to like call people out on bad stuff, but like to just like, you know, give feedback in public where appropriate, right?

[00:10:58] **Adam:** Like not like, I don't know. I don't want to, I don't want to come up with a bad example, but you, you kind of hopefully get my point,

[00:11:03] **Ben:** Yeah, yeah. Totally understand. I, I think we've talked about this on the show before. I think maybe Tim talked about it or Carol. The, the concept of, hearts. Diamonds, clubs, and spades

[00:11:16] **Adam:** That sounds vaguely familiar.

[00:11:17] **Ben:** so it's like a heart is a very soft amorphous compliment. Like you're a hard worker and, and a diamond is a very sharp, specific thing.

[00:11:26] **Ben:** Like, oh, I love that you, you always give me an estimate and then you make sure you hit those estimates. Like, and, and similarly, a club is a very dull, blunted, demeaning thing. Like, I just wish you were more intelligent. And, you know, and a, and a spade is a very sharp thing, like. I wish sometimes you would, stop and think through your question a little bit more before you came and asked me, you know, something like that.

[00:11:53] **Ben:** And, I've always liked that as a framework, with the full caveat that I have never actually put it into effect. And, and I, and I think part of my problem is, is that I've never really had a direct report. I mean, you could squint and say there were brief periods where, you I was sort of technically people's bosses, but even in those contexts, it was always in a very flat organization.

[00:12:15] **Ben:** And so it, it always felt weird giving people very constructive criticism. One, because of my insecurities, but also because it's like, is that even my job? I don't know. But, but what you're saying, like make it a thing to just make that part of the day to day life is to, to help each other grow. I, again, I just wish I had been better at it.

[00:12:36] **Adam:** I don't know how I did this, but I have cultivated this relationship with Steve, who's my boss and the CEO of my company, where it's totally okay for me to disagree loudly and publicly with him. Like, I think you're wrong. You know, like, this is why, like, I I've mentioned on the show a couple of times, Being mad at users for doing something that the application let them do and like blaming them for it. And, and, you know, I, I constantly, and that's, that's him when I say it and I don't, it's like 99 percent of the time it's him. Cause that's just, you know, when you, when you're a solo developer and you don't have time to get to every feature and put up every guardrail, you rely a little bit more on training to get the users to understand the system and, and right.

[00:13:24] **Adam:** It's, it's like manual testing sort of thing. Right. Like There's no guardrail, but you know, if you're smart enough, you can do it. And, and so he comes from like 10 plus years of doing that. And now he's got a team of people and, and, you know, there's just a different paradigm and he's having to learn that the system should protect users from themselves. And so I, I, I like call him out on that. Somewhat regularly, you know, he gets upset about a ticket that comes in or that about a bug and I'm like, yeah, you're not wrong that it's annoying that this broke or whatever, but like you are wrong that it's their fault. It's not their fault that they put in three years in a report generation thing that, you know, brought down the database.

[00:14:04] **Adam:** It's, it's our fault for letting them put that in. and so, yeah, like I, the point I want to make is that, you know, we've cultivated this relationship where. we can and do disagree loudly and boisterously in our internal team public spaces, and at the end of it, we always are still fine, right? Like, we're not fighting, we're just loudly disagreeing, and then somebody eventually either wins and is like, you know what, you're right, or we're like, okay, well, you know, We're just going to disagree and we're going to have to be okay with that, you know, but like, and demonstrating, I think that I kind of view, it's weird.

[00:14:46] **Adam:** I view a little bit of my job as like, because I am the first person that was hired beyond Steve working for himself at this company in this iteration. It's a whole complicated thing, but, for all intents and purposes, I'm the first hire of this company beyond the founder himself. And so I feel people kind of standing behind me as like, well, how would Adam handle this? And so I feel a responsibility to demonstrate how I want everybody else at this company to behave. And for me, that means calling people on that isn't necessarily right and being willing to back down if, and when I'm proven wrong. Right. And I feel like doing that contributes to everybody else feeling like it's okay to do the same thing.

[00:15:34] **Adam:** And hopefully everybodykind of incorporating that in the way that they hear feedback from myself and from everybody else.

[00:15:43] **Ben:** I mean, that sounds really great. It sounds really great. Honestly. yeah, I, I, I think if I reflect back on conversations that I've been in where I would have liked to push back more, but didn't, I think a lot of that was also that the people I was involved with in those conversations. We're, I think, looking to shut the conversation down. It wasn't so much a, it's interesting that you see it that way.

[00:16:10] **Ben:** Why is that? What are the assumptions that you're making that are different from mine, where your view is so different than mine? It was more like, I'm right and you're wrong, and I don't understand why you're wrong. And I, and I, you know, sometimes you get to a point in that conversation and you don't even want to fight anymore.

[00:16:27] **Ben:** Like it's, it's, it's a dead end.

[00:16:30] **Adam:** honestly, I think that having these loud public disagreements empowers those moments where Steve needs to say, you know, I'm the one in the field with the customers, I'm the one hearing their requests every day. And I need you to build this and I need it to work this way. Right. For him to say, like, I hear you.

[00:16:49] **Adam:** And, and I've got, I don't have the hour to sit here and, and explain to you everything that has been, you know, bombed into my email box, my inbox for the last six weeks to prove it. I need you to trust me. I have the evidence and this is the way I need it to be done. And when he says that, like, okay, cool.

[00:17:10] **Adam:** I trust you

[00:17:11] **Ben:** Nice.

[00:17:12] **Adam:** because I know when, when it is just a matter of opinion or something like that. And it's. Doesn't have that rock to like cling on to, to say like, this is the right thing. Then he is willing to have those disagreements and to, you know, try to find what's right. And that's the thing is like, you know, you, you disagree and you debate not to win because you believe you're right, but in order to find the truth, to find the right answer.

[00:17:41] **Ben:** It's so great that you say it, you position it that way, because I was just thinking about an experience that I had two days ago in our local CVS for, for people who are listening that don't know what that is. CVS is like a, a convenience store slash drug store slash pharmacy in the Northeast.I don't know what you would compare it to.

[00:17:58] **Ben:** Anyway, I w I was in there, I was getting a pill box, like a AM PM pill box for my dog, who now has a sufficient number of medications to warrant a seven by seven. Anyway. as I'm walking out, I have the dog in my arms and this old lady stops me and, and mentions how cute the dog is. And because I am not a people person, or I should say, because I'm not a very social person, when people do choose to interact with me voluntarily, I try to treat it almost like an improv class.

[00:18:29] **Ben:** Like, I find a way to yes and, oh, you think the dog's cute? Yes. And how can we start a conversation? And then she starts telling me about this cat that she adopted from her mother who was demented and she had to start giving it insulin. I'm like, oh, that's so interesting. How, how many years did you have to give the cat insulin?

[00:18:45] **Ben:** Anyway, we talked for like 15 minutes in the CVS. And I, I think why I enjoy those types of interactions so much and why I enjoy the digging is because I have no agenda or I should say my only agenda is to find out more information about this person. But when I'm in one of these confrontations, my agenda probably too often is to prove why I am right and, and not so much to better understand why it is that you think that I'm wrong and why you think you're right.

[00:19:17] **Ben:** And if I could. If I could get into the mentality of yes, anding that kind of a discomfort, an uncomfortable conversation, I think I'd be much more successful at it.

[00:19:28] **Adam:** Yeah, it's, it's a very tricky, like, knife edge to walk because you don't get into that situation without a strong opinion, right? You, you find yourself in that disagreement because you feel like you have evidence that says you should strongly believe. You know, X is true.

[00:19:47] **Ben:** Oh, that's, and there is, it kind of lies the crux for me because I either don't care enough to really push back because I don't have a strong feeling. So even if I think maybe you're wrong. I don't think that I'm right enough to really care that much or to, you know, to dig deep and explore, or I so clearly know that I'm right. And at which point it seems worthless to dig in and better understand why you are so wrong. And I don't know, I, I don't know. Anyway, this is, this aligns perfectly with the whole idea of giving people constructive feedback if I don't necessarily feel like they're supposed to be reporting to me because I don't know.

[00:20:29] **Ben:** Is it my place? That's what, that's, I always worry about whether it's my place and I'm not often confident enough to give people feedback if I'm not super confident that it's actually my place to do so. Oh,

[00:20:44] **Adam:** Yeah, that, I mean, there's a whole, we're already 20 minutes into the show and just on the one topic there. So obviously there's more to unpack there. But, in the interest of getting to our main topic today, why don't we cap that there? so that's my triumph. Ben, what have you got going on?

## [00:20:58] Ben's Failure

[00:20:58] **Ben:** I'm going to go with a and I will keep it short, which is that my personal site was down. unavailable and then mostly degraded for, from like Friday afternoon, late Friday afternoon to Sunday morning. sorry, to Monday morning. And I, I don't know what series of events took place, but I suddenly started getting emails Friday afternoon that my site was unavailable.

[00:21:22] **Ben:** This was from a Netlify cron function that runs every 10 minutes and sees if it can get a 200 and then if it can't, it sends me an email. So I was literally getting an email every 10 minutes. For something that I built and I have no way to snooze it because it's just a cron function. anyway, I have no idea what happened, but for whatever reason, Host Tech, which has been, not favorable in the eyes of the community the last couple of years, decided to, they had some emergency maintenance that they had to perform and somehow as a result of that, and I have no idea why it's very black box kind of situation, they upgraded my server to Java 17 and, from Java 11.

[00:22:03] **Ben:** And I'm on ColdFusion 2021 and 2021 is not compatible with Java 17. I have found out in the last couple of days,

[00:22:11] **Adam:** the hard way.

[00:22:13] **Ben:** the hard way. and then eventually I, after trying to get back to, And eventually after trying to get in touch with support and understand what was going on and getting available feedback, I was just doing more and more Googling and I saw in my program files that there was a Java 11 folder and a Java 17 folder.

[00:22:31] **Ben:** So I just went into the cold fusion administrator and in the Java settings, you can just point it to a JVM folder, a JDK folder, whatever it is. And I just pointed it back to 11 and then suddenly everything started working again.so, so my failure is one, just that the site was down. And that sucked. But the kind of underlying failure there is I just, I know so little about how servers and specifically how the JVM works and how ColdFusion really works as a server itself.

[00:22:59] **Ben:** I just know so little about that, that, you know, I'm sure someone who manages ColdFusion servers could have been like, Oh yeah, Java 17 isn't compatible. Just go back to Java 11. And all you have to do to do that is point this folder. And that took me three and a half days to figure out. And. I, I get so frustrated, but I also, I, I balance that frustration with pragmatism, meaning the, the easy answer would be to say, Oh, just get more familiar with how ColdFusion servers work and how you can manage stuff and how the Tomcat works and, and all that stuff.

[00:23:34] **Ben:** But the pragmatic part of me is always looking at like a product. Is, is that my core differentiator is knowing how to manage servers. I mean, that's why I have managed hosting is because I don't know about servers. So is learning how to manage servers the best use of my time or is building the actual product?

[00:23:51] **Ben:** I say products here in a heavy, heavy air quotes, cause it's my blog and like a couple of other little side things. I don't know. I get frustrated for my lack of information, but I also maybe justify that by saying this, that's just not my primary concern, managing servers. So I don't want to spend that much time worrying about it.

[00:24:10] **Adam:** don't blame you.

[00:24:11] **Ben:** Oh, it's so frustrating though. I, I wish I could get to the point where I could just, Build a docker image and deploy it. And this brings us back to like a season one of the working code podcast.

[00:24:23] **Adam:** Wait, we're not still in season one?

[00:24:25] **Ben:** We're in episode 185 of season one.it's one of those things where you, developers always underestimate the complexity of stuff. So I could, in my head say, Oh yeah, if I could just build an image and deployed someone like Elastic Container Services on Amazon, and you're like, well, then what about database backups?

[00:24:44] **Ben:** And what about the attached file system? Or, or do I have to store, you know, gigs worth of images in my. Docker image, or do you know, do I have to push those images somewhere else? You basically have to have an answer for everything that replaces the, I can just remote into my windows server and FTP files up.

[00:25:02] **Ben:** And there's a lot of complexity in that and disaster recovery plans that manage hosting. you know, in theory has, this is one of those things, like I've never actually had to test whether or not my hosting provider's disaster recovery works because I haven't had a disaster. fingers crossed. Anyway, I'm, I'm just rambling.

[00:25:21] **Ben:** The site was down. That's that's my failure.

[00:25:23] **Adam:** You know, the, the whole Java thing, right? I always felt when I was writing a lot of cold fusion, that there was like this wall I would hit when it, when it got to the point where like something didn't work or, or, you know, if you have to do something weird with SSL certificates, right, you kind of, you have to put that in the JVM

[00:25:42] **Ben:** Yeah. It's got to go in the CA certs, thing. And then, yeah.

[00:25:46] **Adam:** And, and these are not insurmountable tasks, but I, I, something that I felt kind of broke down about working in the Coltusion ecosystem, for me, was that all of the material is like, okay, we have this. DSL that runs on the JVM. And as long as you want to color inside those lines, go nuts, you're fine.

[00:26:05] **Adam:** But the moment that you need to step out of that, it's like stepping from a waiting pool to the Mariana Trench, right? You're just, you're on your own. Here's the Java docs, figure it out. And there was, there's like very little help to make that transition. And if you're not a trained Java developer, then it is, extremely overwhelming.

[00:26:27] **Adam:** And

[00:26:28] **Ben:** Yo, just, just garbage collection, you know? Oh, my site has some bad performance. Someone's like, well, what garbage collection algorithm are you using? And I'm like, I don't know. I'm a product developer. Yeah. Like that, that is not the world that I live in. And I, and then I get angry. I'm like, I don't want to have to know about garbage collection or I don't, I, I like to understand that it's the reason I don't have to allocate and deallocate things explicitly, but beyond that, I kind of want to have a guy, you know, it's like they always tell you on TV shows, like, yeah, I got a guy for that.

[00:26:59] **Ben:** Like that's what I want a guy for all that stuff that I don't have to, that I don't want to have to know about on a daily basis.

[00:27:05] **Adam:** Let's, let's set that aside. Let's move on.

## [00:27:10] AB Testing

[00:27:10] **Adam:** so I, I mentioned that we wanted to talk about A B testing. This is entirely selfish for me, because for years now, our customers have been not so subtle hints that they want A B testing specifically for emails, right? So we've talked, In the past about how my product sends a lot of email,

[00:27:27] **Ben:** So, sorry, can I just ask you a framing question for my own

[00:27:30] **Adam:** please.

[00:27:31] **Ben:** thinking here? When you first said A B testing, my mind immediately went to, you want to A B test the product to build for, to build it for your users, but are you saying that actually your users want the ability to A B test their own stuff?

[00:27:46] **Adam:** Exactly. So they want to be able to send emails and like, hopefully this is what they're thinking that they'll change, you know, the subject line and nothing else about the email or they'll change the color of the call to action button, right? Like keep it simple. but basically, you know, they want to have the ability to send emails with two variants and to a, a small percentage of the total audience for the message.

[00:28:10] **Adam:** You know, wait a certain amount of time or like, I, I went briefly down a rabbit hole today, thinking of like all the different ways that I could immediately think of. I came up with like nine different, potential types of tests. Right. So, and a lot of it is like, okay, this or that branched off of this or that branched off of this or that.

[00:28:30] **Adam:** Right. So you've got like, when you talk about emails, you might be more interested in opens versus clicks, right? If, if you're just trying to get people to open and read a message versus get them to click or.you might be interested in getting them to click and then do something, right? Like click and make a donation, right?

[00:28:46] **Adam:** And I, we do have a mechanism by which I can say this donation was, I can tie it back to this user receiving an email. and so like a couple, I came up with a bunch of different variations of that and, and I, Just in a, like a Google sheet, kind of threw together a mock UI. Like this is kind of what I'm thinking of in terms of the form.

[00:29:07] **Adam:** These are the potential tests.and I sent that along with my thoughts on some data organization stuff over to my team, all right. Because this was like a, we got an email from the boss a week or so ago, actually while I was on vacation last week. and.he's like, you know, okay, we have an official request.

[00:29:30] **Adam:** They're like, you know, please do it. We, you know, we want you to spend our portion of the development time, on, on this feature. so they want us to work on this and. So now it's, it's kind of like, okay, we're doing this. How it's time to figure out how we're going to do this.

[00:29:45] **Adam:** and so where I'm a little bit stuck is like, we need to bolt this onto an existing email system that was built without. The thought of adding A B testing to it, right? So we have a system where you can have a list of users or a list of recipients, a message, and it'll generate individual personalized messages.

[00:30:10] **Adam:** So maybe a quick vocab. So we, we have, we use, we humans use, message and email almost interchangeably, right? But in my product, a message is the content of the message before it's been Personalized and an email is, after personalized, right? So I might write a message and say, I'm going to send it to all listeners, the working code podcast.

[00:30:34] **Adam:** And you might receive a message that says, Hey, Ben, you know, go here and join our Patreon. so the one that you receive is an email and I've got a hundred thousand of those, and I've got one message. For having sent those a hundred thousand,

[00:30:46] **Ben:** And if I remember correctly, you have some sort of system where you say, I have a hundred thousand people that need to get this email, I'm going to generate a hundred thousand messages and put that on, on Amazon's SQS, and then something will churn through those and send them out, is that?

[00:31:03] **Adam:** you're barking up the right tree. It's not SQS, but yeah, we, we go from that there's a moment in time, right. Four hours prior to those emails starting to be delivered. We have this like moment in time where we pivot, right. Or it kind of like springs into action. And that message then generates, all of the, we call them stubs, which is just like an empty email record. And it says, okay, this one's going to Ben, this one's going to Adam, this one's going to Tim, this one's going to Carol. With all the IDs to tie things back to the appropriate places. And each of those files that gets written to S3, with the indicators of like, this is who it's for, this is the message that they'll be receiving, then triggers a series of events that render it and prepare it to be delivered.

[00:31:49] **Adam:** And then there's another thing, you know, they kind of at the end of that, they just end up in this like ready to be sent bucket. And they might, if it takes 30 seconds to get through all of that, then they'll sit there for three hours, 59 minutes and 30 seconds. Cause like I said, it starts four hours prior to send.

[00:32:03] **Adam:** And then at the moment that it's time to start sending, then they'll start going out, or in some cases in the worst case scenario, they're still rendering. At that, at the moment that they're start, they're supposed to start sending. And so like the ones that are already rendered will start to send, but then there's others still working their way through the pipeline.

[00:32:20] **Ben:** Gotcha. So if you had, I'm just trying to think about at what point you'd be able to put something dynamic into the message. Email crossover.

## [00:32:31] Implementing Email AB Testing

[00:32:31] **Adam:** so I, after spending some time thinking about it, here's where I kind of landed, right? So the, the difficulty here is in adding additional functionality to our mail module that doesn't break any existing mail, right? We don't, we don't want to make A B testing a requirement for every message. Right? So. We can't break the existing functionality, but we need to give you the ability to say, okay, here's the list of people this time. I do want to AB test it.you know, so if you're giving me a list of 300, 000 people, what percentage of that list do you want to be the test audience and we'll split that 50, 50.

[00:33:06] **Adam:** Right. So if you've got, let's just keep the number simple. If you've got a hundred thousand recipients on the whole list. And you say, you want to go to 10 percent of people as a test group, then that brings it breaks down to 10, 000 people. So you've got 10, 5, 000 getting test case A, 5, 000 getting test case B.

[00:33:23] **Adam:** And then after some point you determine a winner and the remaining 90, 000 people get a copy of the winner from the test. So what I have thought of so far is at that moment that we talked about where four hours prior to delivery, where it starts to create the stubs,

[00:33:42] **Ben:** Right. You're doing your mail merge kind of a thing.

[00:33:44] **Adam:** Yeah. Yeah. It's very similar to a mail merge.

[00:33:46] **Adam:** it's just a, it's a very enterprise mail

[00:33:48] **Ben:** Yeah. Yeah.

[00:33:50] **Adam:** at that moment we'll have to go, okay, this is actually part of an A B test and we'll like generate new lists, right? So we've got this list of a hundred thousand people and I go, okay, but this message is actually part of an A B test. So I need to take my list of a hundred thousand.

[00:34:03] **Adam:** And from that, I need to generate a list of 5, 000, another list of 5, 000 and another list of What did I say? 90, 000, right? And so the first two lists get used for the two test variants. And then I've got like another, let's just say like an hour later, we, we determine our winner. We'll figure out what that means later. And we need to, clone the winner, assign that 90, 000 list member list to the clone of the winner and send it. Oh,

[00:34:35] **Ben:** It feels like my first gut reaction, because you have such a robust existing product, you're almost going to be fighting against the terminology that people use. Meaning, I'm just going to make up words for a second, if I have to send a hundred thousand emails to a list of, of potential donors, I'm just going to call that a campaign and inside of that campaign,

[00:35:03] **Adam:** this whole world is like the, the, the. Industry that we work in, we're in higher education. It's just rife with overlapping terminology. It is so hard to name things. It just, technology in general, it's hard to name things. And then you start like, okay, we're going to do technology for this non technical vertical.

[00:35:20] **Adam:** And so like a word that means something important to me also means something important to you. And there's zero overlap between them. Exactly.

[00:35:30] **Ben:** and then maybe inside the campaigns, let's just call them that we want to have experiments. And you could say, well, because we have so much infrastructure around sending campaigns, it's like really what we want to do is the experiments each kind of become their own campaigns.

[00:35:46] **Ben:** And then really you might have a set of campaigns that are tied together that become what the user thinks of as a campaign, but we actually think of as like a, I don't know, like a collection of campaigns. I'm not coming up with the right words, but then the problem is. You have a user who says, I want to run this experiment, but then under the hood experiment, maybe maps back to something in the software called a campaign.

[00:36:07] **Ben:** And now it's like, you never know how to refer to things. And then as your team grows, people are like, why is the campaign table querying the experiment table? You're like, ah, that's a great question because many years ago, it's like, how do you Baby step towards a comp, not a completely different solution, but it's almost like a completely different way of thinking about organizing the data, but without completely redefining all of the terms that people use every day. It's

[00:36:41] **Adam:** Yeah, and, and this is a very complex system. Like, it doesn't sound that complex. So just send some emails, right? But like, we're talking about, you know, we're, we're tracking clicks. We've got the ability to halt, a message in the middle of sending it, right? We're sending 300, 000 emails at like 4, 000 a minute.

[00:36:57] **Ben:** Something goes wrong.

[00:36:58] **Adam:** right. And they're like, Oh, we misspelled the president of the university's name. Stop the presses. And so, you know, they hit the button and it's got to like do its best to, to stop everything dead in its tracks and keep track of the people that have already received it so that when they fix it. We don't send a second copy to the people that got the first one, right?

[00:37:16] **Adam:** Cause that would just be annoying. and you know, like all of these little things, unsubscribed preferences, the people that recently bounced, you know, like I said, I think I might've mentioned, I can't get the words out of my mouth. Tracking clicks. I wanted to say clacking tricks for some reason.

[00:37:33] **Adam:** and like, you know, Each of those things can like have multiple paths that you can go down from there, right? It's not just tracking the click, but it's like, maybe there's, maybe there's some knock on effect to that.and so I'm trying to figure out how to add this functionality without rocking the boat too much, right?

[00:37:53] **Adam:** it's like, I need to, there's a word,

[00:37:56] **Ben:** you gotta boil it down to what is the least amount of information that I have to pass through. For everything to make sense, whether it's like a campaign ID or an experiment ID or a branch ID. And then, because if you, you have all of this stuff already built and you're going to have to go now change every link that gets generated and every button and every form submission to potentially propagate this new piece of information.

[00:38:23] **Ben:** Like it better just be one in one, you know, one token, as opposed to like, now I have to pass through all these seven variables.

[00:38:31] **Adam:** It feels a lot like to g to use like a computer science college y term. It feels a lot like. Overloading a function, right? We've got this function, it already does a whole bunch of stuff. And I just kind of want to add one little argument and like, if that argument exists, then do this stuff a little bit differently.

[00:38:48] **Ben:** And it's tough too, because I, I didn't even think about the knock on effects that you were just mentioning to, to make that concrete. You might want to both change the terminology in an email. And then one of the links that you can click on brings you to a landing page for a form. And maybe that form also now needs to change because you came from, from that email.

[00:39:10] **Ben:** And that's, that's like a whole nother level of complexity because now you have to have An experiment that says, okay, here's email content. And then here's,you know, form content as well. I'm not saying that you were thinking about doing this, but it sounded like maybe that's what you said you were doing.

[00:39:24] **Adam:** it's an interesting thought. We hadn't gone down, we're trying to like sort of MVP this,

[00:39:28] **Ben:** Yeah. A hundred percent.

[00:39:29] **Adam:** it was great that I came up with this like list of potential experiments that could run like, or, what is the right, Word here, like not vehicle, but like a different way to run the experiment, right?

[00:39:39] **Adam:** Whether it's, you know, percentage based or like first pass the post, whether they're talking to opens clicks, gift dollars, gift count, you know, whatever. but having that list is just like sort of a proof of concept that there is. Meet here, there's something interesting that we could dig into if we can get the basics right.

[00:39:58] **Adam:** And so now we're going to take a step back and just try to do, we'll, we'll like define, if you want to do an A B test, this is what we support. You can change anything you want about the, the variance of the message. If it's the subject line or the color of the button or, you know, change, I don't even know,

[00:40:12] **Ben:** I, I, I, I totally. And if I can reach back into my own experience as a user and say only that I think people are terrible about thinking in terms of, you know, what's Theoretical eventualities. And what I mean is like, I understand how to test one thing at a time. I don't understand, like my brain is almost not capable of thinking about two dynamic steps back to back.

[00:40:41] **Ben:** And the, the best analogy that I can think of is when I use LaunchDarkly at work, LaunchDarkly is a feature flag mechanism. And when you configure LaunchDarkly, you can actually make compound Rules for feature flag targeting. You can say like, only give this user this variant if they meet this criteria and this criteria and this criteria, you can make these compound rules.

[00:41:07] **Ben:** And in the like eight years that I've been using their system, I've never once built a compound rule because it's just so complicated. Like I can think of, you know, I want to show this feature to people who are from Harvard. Or show this feature to people who are from Cornell.I I've never once thought, show this feature to people who are from Cornell and graduated the class of 2010 and have an income greater than such and such, like, it's just, it's just too complicated, too much information to hold in my head.

[00:41:37] **Ben:** And I, and I give all of that preamble to say. It's, it's almost freeing for users to only be able to attack one constraint at a time, whether that's, all I want to do now is worry about click through rates on the email. I don't care about the form that they go to. That's another experiment once we've figured out how to increase the click through rate.

[00:42:00] **Ben:** And it's like a, a, a quote unquote more robust system might be able to have these sort of chained experiments. But I think from a consumer standpoint, that becomes so complicated from a, from a cognitive load. That it's, it's going to be, it's like, it's going to be really hard to build. And then probably I would guess most people don't use it anyway.

[00:42:20] **Adam:** yeah. And that's the thing is like, all of those variants that I, or not variants because those are the test A versus test B, but you know what I mean, the different types of experiments that you can do, whether we're talking about opens or clicks or percents or first past the post or whatever, like the sort of the defining characteristic of the list that I made is that they would all be simple to configure.

[00:42:41] **Adam:** Right. So if I'm sending to, if my test groups are 5, 000 each and I just want to say, okay, first one to a hundred GIFs, like that way we get there, we get to the, to the success state as fast as possible. Right. Instead of saying, oh, I'm going to let it run for three hours and see which is better. There, there, there's a sense of like

[00:43:04] **Ben:** I see. So you, you want almost like an automated, like the, the experiment needs to decide based on a threshold when it should start favoring one example over

[00:43:17] **Adam:** It, it, it has to be, the whole point of this is automation, right? For them to say, okay,

[00:43:21] **Ben:** You, you, you almost want to take the human out of the loop a little bit, like the humans decide what the experiment are, but then the machine should say, okay, experiment B is clearly winning over the first N thousand emails.

[00:43:34] **Ben:** So the next, X thousand emails, we're just going to use that one. But that, you know,

[00:43:39] **Adam:** Yeah, all in like in a, in a predetermined basket, right? These are all related to each other.

[00:43:46] **Ben:** It's. It's really

[00:43:48] **Adam:** the messaging right or whatever.

## [00:43:49] Asynchronous Workflows

[00:43:49] **Ben:** It's tough too, though, because you have to consider the fact that email is by nature, an asynchronous workflow. So

[00:43:56] **Adam:** Mm hmm.

[00:43:57] **Ben:** you might send 20, 000 emails before anyone even notices that one showed up in an inbox. So it's, it becomes, it just becomes hard to then A B test and then opens.

[00:44:10] **Ben:** You know, I can't tell you at work how many times I've sent an email and I'll look at our, our email statistics and I'll see somebody open an email and I'm like, what the heck did they open? We didn't send any emails today. And you look and you're like, Oh, this is from the email that we sent three weeks ago and they just opened it today for the first time.

[00:44:27] **Adam:** so, since we're doing like click tracking and all that stuff, it, what, what really blows my mind is like people still clicking links from messages they received like two years

[00:44:35] **Ben:** Yeah. It's like how, how people will go to Google and Google for Facebook. com.

[00:44:41] **Adam:** Yeah.

[00:44:41] **Ben:** Right? It's like, I, I'm guilty of this. I know. I'm like, oh, what the heck is my health care portal? Let me go to my email and search for Optum or Nuvance or something and I find my welcome email from three years ago And then I click on the patient portal, you know stuff like that happens We're, we're a path of least resistance. Well, it's like, it's like, we're weirdly a path of most resistance when it's the past of least, of least planning.

[00:45:08] **Adam:** Yeah. It's like we lay down that, that whatever the path is going to be, like almost first one. To, to make the connection in my brain

[00:45:16] **Ben:** Right. It's like, would it be way better if I just stopped right now and opened up my one password And went to my healthcare entry and added the website into the configuration. Yeah, that would be way better. But you know, it's easier right now to actually just search my email for, you know, Blue Cross Bruce Shield and, and find the email.

[00:45:34] **Ben:** It sounds crazy, but like, that's, that's where we are as people. Oh man, this is like, it's so interesting. There's so many Complexities here. Cause it's not just this, it's not just the mechanics of A B testing. It's the mechanics of A B testing inside this very asynchronous and potentially drawn out workflow.

## [00:45:59] UI For AB Testing

[00:45:59] **Adam:** Yeah. I mean, you mean just to, to, you know, expand on the picture I've been painting here, I thought I've had during this discussion that legitimately didn't occur to me until we were here is that my, it's like the UI mock up that I made. Would be a bad design in terms of user experience, right? So I just made this like screen where you go in and you say, okay, here's message variant one, here's message, or I'm sorry, I should say A and B, message variant A, message variant B, and you like go select from existing message drafts.

[00:46:29] **Adam:** Right. So in order to, if that was like step one of creating an A B test email campaign, right, then the, the prerequisites for starting an A B test email campaign would be go create a message, right. And then manually clone it yourself and change something about it and keep track of what those two messages were, whether it's like the name or subject or whatever you're going to do so that then you can come over to the A B test thing and say, okay, I want to start a new campaign.

[00:46:57] **Adam:** Here's my first message. Here's my second message. A better user experience would be, you know, like maybe it's a, opens a new tab sort of thing, but like, you know, you say, I want to start a new A B test. And the first thing you do, it does is like give you a button. Okay, click here to create a message and like, it'll automatically know what message you created and it'll fill that in for you.

[00:47:17] **Adam:** And then it's like, okay, do you want to create a totally different message? Because maybe the test that you're doing is like, worlds apart. A lot of A B testing. I think, I think people get caught up on the fact that like, okay, maybe Google A B tested like 77 different shades of blue for whatever button, right?

[00:47:33] **Adam:** Like maybe that's true, but. A totally valid, A B test is still in certain, I'm the, I'm the statistician. but I think that it's still valid to say like, okay, maybe this one appeals to emotion and this one appeals to, to the statistical brain, right. And like, which one is going to generate the outcome that you're hoping for.

[00:47:53] **Adam:** And so you might have totally different messages. So maybe in that case, it doesn't make sense to clone it, but maybe in some cases it does. Maybe you just want to change which emoji you're using in the subject line. Right. and so, give them the, give them the ability to create the message from within the A B test workflow and then an option to clone it and then make a minor edit or to start from scratch on test case B, right?

[00:48:18] **Adam:** And, like, all these things, just thinking about, you know, The workflow of creating this A B test, like what is the best user experience for them?

## [00:48:26] Sharing Test Data

[00:48:26] **Ben:** And you know, what's so interesting about the academic world is that when you, when it comes to recruiting students, all of these organizations are competitors. Harvard wants the best people, and UPenn wants the best people, and they don't, you know, they don't want to share with students. They want the, you know, the dollars.

[00:48:46] **Ben:** Once a student has graduated, these academic institutions can be synergistic. They're not, they're not competing for students anymore. It's not like Harvard can compete for Cornell graduate alumni dollars. I mean, maybe there's a way, but that's like, that's not the main focus. So you could be in an actually quite a good position to do a lot of cross pollination.

[00:49:09] **Ben:** You could say, Hey, people at Harvard, guess what? Yale ran this experiment last week. You know, I'm sure there's intellectual property kind of questions here, but like Yale ran this experiment last week with these two subject lines and this subject line converted at a 15 percent higher donation rate or, you know, something.

[00:49:28] **Ben:** And you could actually start to take the information that you've learned from one campaign. And help influence or improve the campaigns of the other organizations as a real possible value add.

[00:49:40] **Adam:** I mean, just like, even, so that would be an interesting way to like share information amongst our customers as like a value add for

[00:49:48] **Ben:** Yeah. Yeah. That's what I mean.

[00:49:49] **Adam:** to have to give us access to your data so that we can do this, but the benefit that you get in return is that we're accessing everybody else's data that we have access to, for your benefit, right?

[00:49:58] **Ben:** can be, you know, you can be like, Oh, you want to use an emoji in your subject line? Well, that's funny because it turns out that every test that we've run that has an emoji in the subject line actually converts at 2 percent less than the competing experiment. It like, I feel like people would love to know that kind of information.

[00:50:14] **Adam:** Yeah, for sure. Yeah. And, and like, you know, if at some point in the future, we start doing like a content marketing thing, like then we can take the data and it's anonymized and, you know, it's not like this was a Yale thing, it's, across all of our customers, you know, these are the experiments, experiments that we've seen run and what's successful and what's not sort of thing.

[00:50:34] **Ben:** I could, I could even see a world. In which the MVP for this is just subject lines, choose 10 subject lines. I mean, you know, that's crazy maybe, but you know, choose X number of subject lines for your campaign and we'll see which one of them converts better. And that's low enough from, from,what's the right word.

[00:50:54] **Ben:** It's like, that feels powerful enough from a consumer standpoint, but low enough from a cognitive load where like, Anybody who's sending out email campaigns can be like, Oh, that's actually pretty interesting. Let me try that. Like that, that would be an easy experiment for me to run because I can come up with subject lines all day long.

[00:51:11] **Adam:** Yeah, for sure. And if that was going to be a. Long term viable approach. I would definitely want to go down that path. Unfortunately, I don't think it'll work well for us because

[00:51:25] **Ben:** Hmm. Way to give me constructive criticism.

[00:51:31] **Adam:** don't think it'll be a good path for us because there are like on the edit message screen, there's something like, you know, easily 20, possibly as much as 40 different fields that you can edit.

[00:51:44] **Ben:** Nice.

[00:51:45] **Adam:** Now, not all of those directly affect the recipient, right? Like some of those are, you know, where do we send statistical updates about like, you know, much of the message has been sent?

[00:51:54] **Adam:** And like, cause you know, they are, when you send a message to, you know, a million people, it takes more than a few minutes and people. Like to know what's the status of things. And so we have the ability to say, okay, you know, it's 40 percent sent and, you know, 130 of them have failed because of bad email addresses or whatever, like that sort of thing.

[00:52:14] **Adam:** So there's fields for, for setting that sort of stuff up, but there's also like, you know, a preheader. Are you familiar with this concept? So, you've got, you've got your message body, and you've got a subject, and if you look at it in Gmail, sometimes, and other mail clients do this too, but Gmail is

[00:52:31] **Ben:** Oh, this is like the teaser kind of a

[00:52:33] **Adam:** right, but, so it's not the subject, but if you look in the body of the message, just open the message up and look at it with your eyeballs, You can't find that text in there.

[00:52:44] **Adam:** It's not quote unquote in the body of the message visually. Usually what's going on is it's hidden as like black text in a black background sort of thing, right? It's what was really going on is the Gmail and these other mail clients just show the first, you know, like it's, it's like between 80 and 140 characters, something like

[00:53:02] **Ben:** It's, it's the first non tag based content kind of a thing.

[00:53:06] **Adam:** First textual content in there. and so it gives you like, sort of like a little inside joke or, or, you know, a little, just a little subliminal place to drop some content to, to get people's attention.and so like, you know, that's just one of the fields that we have on there.

[00:53:21] **Ben:** Right. And that's one thing that could be an experiment. Yeah.

[00:53:24] **Adam:** Yeah, exactly. and so like, I like the idea of being, making it so simple that it's just like, okay, here's my message. And then. you know, I want to be able to put up four variations of subject line and, and try that out. But I think that, that kind of goes a little too far into oversimplification because it makes it almost too hard to implement the same approach across all the things that you might want to support.

[00:53:51] **Ben:** absolutely. so

[00:53:54] **Adam:** this was a fun conversation. I don't know that I really came up with anything, although I did have a couple of epiphanies while we were here. So that was helpful in that regard, but I don't know that,

[00:53:59] **Ben:** I want to say that I'm, so if I were approaching this problem, my immediate thought would be, what does the database have to look like? And to hear you say, Oh, I sketched out a wireframe of what I think the UI should look like, I'm like, Oh, that's so much more mature.

[00:54:16] **Adam:** well, you know, I did, I, I started with, I just opened up a Google sheet and I was like, okay, you know, test variant A, and I made the little box next to the right of that, like gray to say like select one, right? Like

[00:54:28] **Ben:** No, but still, it,

[00:54:29] **Adam:** 10 minute wireframe,

[00:54:30] **Ben:** brain always immediately goes to database schema. And I think

[00:54:34] **Adam:** mine too.

[00:54:34] **Ben:** it, it, it,

[00:54:36] **Adam:** But

[00:54:37] **Ben:** to, to go to the user experience first feels like the, then the database schema almost becomes a lot more informed.

[00:54:43] **Adam:** Yeah. This was such a complex change that I felt like I had to understand exactly what it is I need to, like, what, what additional data is necessary to make this work, sort of like minimum viable data. and that way I could figure out, okay, you know, obviously we have to have some sort of like a test ID and we have to have, you know, ways to tie those things together.

[00:55:07] **Adam:** And like with I did, I, I, so I emailed this, Spreadsheet to my coworkers. I said, okay, here's just a quick first draft mock up and also under that link, here are my thoughts, like, okay, we're going to have to add these columns to the list table and these columns here, this references that and like, oh, when, when you halt, one of the tests, right.

[00:55:27] **Adam:** If you're in the middle of sending the two test campaigns, then if you halt one of them, it should halt the other, right? Cause in theory, they're being sent at the

[00:55:34] **Ben:** interesting. Yeah, yeah, yeah, yeah.

[00:55:36] **Adam:** right? So like, just, I'm just like rapid fire, like whatever I can think of, like the whole ecosystem of this feature,

[00:55:43] **Ben:** and that's, you know, cause when we were originally talking about it in terms of a mail merge, my thought was, Oh, you have a hundred thousand emails that you have to send out. You sort of codify all a hundred thousand of those at one time, siphoning off a certain percentage of one experiment, a certain percentage of the other experiment.

[00:56:00] **Ben:** But then when you said, Oh, but then there should be something that automatically makes a decision that the rest of the emails should get this experiment because it's outperforming, you're like, well, that doesn't work if I've already generated a hundred thousand emails with the hard coded data.

[00:56:14] **Adam:** right? Yeah. So, and that's, that's where my head is at. It's like, I have to, I need to pre prepare the recipient list, but the content of the message that they'll receive is going to be determined later.

[00:56:26] **Ben:** So interesting.

[00:56:29] **Adam:** It's a

## [00:56:29] Pre Mortem for the Implementation

[00:56:29] **Ben:** If I could, if I could play not devil's advocate, but if I could do like a pre post mortem and yeah, pre mortem, and let's just say that, is there a world in which you literally won't get enough interaction before the entire campaign goes out to make any automated decisions?

[00:56:49] **Adam:** Yeah. I mean, these are good things to think about, right? So one of the, in a similar vein, another potential result that we thought about is like, well, what if there's. Close enough to no difference in the test results, that it, you know, it's just not statistically significant. I think that is a valid result, right?

[00:57:09] **Adam:** It tells you that the change that you made made no reasonable difference, but you still, at the end of the day, we're talking about an automation, so you still have to pick a winner somehow.

[00:57:18] **Ben:** Well, let me, let me challenge the automation question then for a second. Is, is it possible that the MVP of this, the minimum viable product doesn't have automation, that it is just the user making an experiment and then in a week or two coming back and seeing what the conversion, how the conversions did?

[00:57:37] **Adam:** I mean, could we do that?

[00:57:40] **Ben:** Do, do you think that that doesn't add enough value, I

[00:57:42] **Adam:** there's nothing stopping them from just creating two, messages now.

[00:57:49] **Ben:** Yeah, but that's, there's no afforda so I don't know your software. So forgive me if I'm painting with an incorrect brush here. but it feels like doing that. If the user is duplicating emails and, and, manipulating content, then there's likely not a ton of affordance in the product that says, okay, now let me correlate the results from these two emails.

[00:58:12] **Ben:** Maybe there is, but like the system wasn't designed for that probably.

[00:58:15] **Adam:** not at all.

[00:58:16] **Ben:** So the MVP could just say, how do I take that gesture and just make that so easy that now people can get information?

[00:58:24] **Adam:** so we do have, yeah. So when you send a message and, and, you know, you're looking at it the next day or a week later, it'll show you stats, right? It'll say, okay, you sent to a hundred thousand people of that 64, 000 people opened it at least once of those 64, 000 people that opened it at least once, you know, 37, 000 of them clicked something in the message, right?

[00:58:44] **Adam:** And then you can go and look at the list of links from the messaging and say, okay, well, there are 37, 000 unique clicks, but like. You know, 10, 000 of those went to our Instagram page and only, only 150 of them were actually clicks to call to the call to action or whatever. Right. Or,

[00:58:59] **Ben:** So, so.

[00:59:00] **Adam:** 000 of them were the unsubscribe button.

[00:59:07] **Ben:** So I, I'm wondering, and again, I'm just like trying to dig deep here and figure out the MVP, like the most, the most m of the MVP and it, it almost feels a little bit like a, when you go to Best Buy. And you want to buy the hard drive for your RAID backup system. And you're like, do I want this brand or this brand?

[00:59:28] **Ben:** And you're like, well, here's a checkbox where I can select up to three hard drives and compare them in a little feature grid. You know, like here's RPMs and like, here's the percentage of failures. It's like if, if MVP was, let me take the system exactly as it works today. And just come up with a great UI where someone could say, let me compare side to side, these three different campaigns for exactly what you're talking about with the click through rates and, and who, what types of links were clicked on.

[00:59:53] **Ben:** I feel like that in and of itself could be pretty powerful and pretty compelling.

[00:59:57] **Adam:** Yeah, for sure. And I will definitely float that back to the team, see what they think about that, cause that would be a lot less work to build. The question is, is that going to be enough to get. The interest of the customers. Cause it still leaves a lot of the manual work to them

[01:00:14] **Ben:** Yeah. Yeah. Well, I, you know, you could, you could handhold them almost into the experience where suddenly a button shows up one day and it's just compare this campaign to your last campaign. And, and it opens up and it's literally like, had they said, let me compare this campaign in the last campaign with checkboxes and hit submit, you know, I'm just doing that automatically for them to get them into that, Oh, now I can start to compare different campaigns.

[01:00:45] **Ben:** Oh, what does that mean? Is there a way that I can think more longitudinally about how choices that we're making in our emails, I don't know, can be observed and affect future campaigns. I mean, I'm, you know, I'm just shooting from the hip here.but, but I'm, Oh God, dang it. I freaking love talking about product.

[01:01:04] **Ben:** I like never get to talk about product anymore. That's so much fun.

[01:01:08] **Adam:** it is. Yeah,

[01:01:09] **Ben:** Oh, building stuff is awesome.

[01:01:11] **Adam:** yeah, yeah. All right. I think we should call it there. We're at a good stopping point.

[01:01:15] **Ben:** Let's do it.

## [01:01:16] Patreon

[01:01:16] **Ben:** Did

[01:01:21] **Adam:** which is tricking users into believing that you have features that don't exist yet. Uh,and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:01:31] **Adam:** Our patrons cover our recording, editing, and transcription costs. And we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo.

## [01:01:38] Thanks For Listening!

[01:01:38] **Adam:** You guys rock. Ben and I are going to go record the after show. Ben, what do you want to talk about in the after show?

[01:01:44] **Ben:** you watch the show, The Bear?

[01:01:46] **Adam:** I love that

[01:01:47] **Ben:** All right. I want to, I want to talk about the hellscape of working in a restaurant.

[01:01:53] **Adam:** I've never worked. Well, I worked in

[01:01:54] **Ben:** I've never worked in one, but it looks awful.

[01:01:58] **Adam:** I'm not even sure you could technically call what I did working in a restaurant, but we'll get into that in the after show. So if you want to hear that and, and other similar conversations that are way off topic, sometimes on topic, but way off topic for what this podcast is normally about, just more of us shooting the .

[01:02:11] **Adam:** The way that you do that is you go to patreon.com/workingcodepod, become a patron of the show for as little as 4 a month, or even less if you pay for a year at a time. and you'll get early access to new episodes as they're edited and ready for your listening ear, and, and our eternal gratitude, which, you know, that should be prize in and, present enough in itself, right?

[01:02:35] **Adam:** and, Anyway, you know, come join our discord, whether or not you're a patron, we'd love to have you. lots of great discussions there. We always have lots of fun. It's my favorite place to hang out. To do that, you go to workingcode.dev/discord, and come get your personalized welcome to the party pal gif sent to you when you join.that's going to do it for us this week. We'll catch you next week. And until then.

[01:02:57] **Ben:** Remember folks, 95 percent of you, your heart matters and an experimental 5%, your heart means nothing.
