---
title: "228: Soft Deletes and Other Crimes"
description: "In this week's episode, Adam, Ben, and Tim discuss the never ending rabbit hole that is implementing soft deletes in a database."
date: 2025-08-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/228-soft-deletes-and-other-crimes/id1544142288?i=1000723865470"></iframe>

In this week's episode, Adam, Ben, and Tim discuss the never ending rabbit hole that is implementing soft deletes in a database. What starts as a simple solution cascades into countless challenges and pitfalls, such as referential integrity, data consistency and compliance. This and other coding crimes in this week's episode.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/228-soft-deletes-and-other-crimes.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** a lot of times people put the, like, the restore logic for a soft delete kind of as a tomorrow problem. They,

[00:00:06] **Tim:** they, they do all this stuff for,

[00:00:07] **Ben:** hundo.

[00:00:08] **Tim:** I mean, on

[00:00:11] **Tim:** And then the CEO is like, Hey, we need to restore that record. And you're like, oh, we haven't really tested this.

[00:00:16] **Tim:** I hope it works.

[00:00:18] **Ben:** Yolo.

## [00:00:20] Intro

[00:00:40] **Adam:** Okay, here we go to show number 228. On today's show, we're gonna talk about soft deletes and other crimes.but first, as usual, we'll start with our triumphs and fails. And Tim, it looks like I'm coming to you first.

## [00:00:52] Tim's Triumph: Hiring

[00:00:52] **Tim:** So I'm gonna go with the Triumph. I've been on a tear here hiring people. We've hired, two new developers in the past, probably 40 days, and I've just,

[00:01:00] **Tim:** just got a third one to agree today. He verbally agreed and tomorrow he should be signing the papers. Said what's cool is this one, he is a patron of the shot.

[00:01:08] **Tim:** I don't wanna name him, but, yeah, really good guy. I've been, I, I, I've actually interviewed him once before and it just, it, that position dried up before we could make a decision. So, so this time I really jumped on it and made sure that, I, I got him in the pipeline early, so, yeah, pretty cool. I've,

[00:01:23] **Tim:** I've, three for three, I've given

[00:01:25] **Tim:** out three, three job offers and three have accepted.

[00:01:27] **Tim:** So

[00:01:28] **Adam:** am I hearing right that if people need a job, they should be become a patron of this show?

[00:01:32] **Tim:** that's what I, yeah, that.

[00:01:33] **Ben:** hundred percent.

[00:01:34] **Tim:** A hundred percent. And it is a, it is a benefit of the show that we don't really talk about, but Yeah,

[00:01:39] **Adam:** I mean, okay. Let's be, let's be real here. At best, it's gonna get you like a face-to-face introduction with us. Right? Like, you'll, we'll, we'll get to have a conversation before you enter the process. Like, let's be honest, we're not just giving out jobs

[00:01:52] **Ben:** It is also a case in point that networking helps and, and in a lot of times it's just all the people you know. You know?

[00:02:00] **Adam:** Yeah, absolutely.

[00:02:01] **Tim:** Yep.

[00:02:02] **Adam:** Yeah. I got, I've gotten jobs through connections I made on Twitter, like, but yeah, networking. That's the, that's the thing.

[00:02:08] **Tim:** Yeah. And I don't, you know, people like rail against Nepo babies, and I get that there's, but it's like, like if you're, if you dad's an actor and your or director, you're just gonna be around people like

[00:02:19] **Ben:** Right. You're gonna be steeped.

[00:02:21] **Tim:** right. It, it's not that your parents are like handing you stuff on a silver pr, but you're, you're rubbing elbows with people in the industry.

[00:02:27] **Tim:** So obviously when, you know, if you've got skills and people in the industry recognize it and. You're gonna have a better chance than someone who doesn't. That's just life. That's, I, I

[00:02:37] **Tim:** know people think it's unfair, but

[00:02:38] **Tim:** I don't think it's unfair.

[00:02:40] **Adam:** well, they do exist in an unfair way, but it maybe not all of them are unfair. I can think of one particularly egregious orange example.

[00:02:50] **Tim:** Yeah. Just a small loan of several billion dollars.

[00:02:54] **Adam:** Anyway, it's not a political show. Let's move on.

[00:02:58] **Tim:** All right. Yeah. So that's me. That's, that's my triumph. So I, I feel pretty good by that. And I like, I do like hiring good people that, that, I, that I've, that I know personally that, so, yeah, it's going good.

[00:03:08] **Adam:** Yeah. Yeah. Cool.

[00:03:09] **Tim:** Actually, actually, five people I didn't think about the entire year. There was two others. So yeah. Five people that I personally know, either in person or through,

[00:03:18] **Adam:** The last month

[00:03:19] **Tim:** this Yeah. In with, within the past year have been

[00:03:22] **Tim:** hired. So, and, and I don't always do the hiring. I don't, don't always, well,

[00:03:25] **Tim:** actually, I don't, I don't do the hiring. I recommend them and they seem to go through, they, they interview well, so.

[00:03:31] **Adam:** I mean, at this rate, give it another year or two. You'll, you'll be employing everybody in our discord.

[00:03:36] **Tim:** That's the plan. All right. That's me. How about you, Adam?

[00:03:40] **Adam:** I'

## [00:03:40] Adam's Fail: No Code Written

[00:03:41] **Adam:** m gonna start with a fail, which is just that I haven't written any code at work in the last four work days. and that's because of, I guess I'm gonna call this a triumph that we're hiring and I am the applicant fire hose filter. Um,you know, it it

[00:03:57] **Tim:** Have

[00:03:57] **Adam:** in the past when we've hired Oh yeah. in the past, when, when we've hired, we've gone.

[00:04:02] **Adam:** We've leaned really heavily into personal networks. you know, like I, I talk to the people I know and my coworkers, I'll talk to the people that they know, and we just kind of put the, put it out through that. and this time we were a little bit more public about it, I guess you could say. Like, we tried to kind of be, not quiet, but, you know, I, what I didn't want was to get like literally a thousand resumes and have to deal with that.

[00:04:26] **Adam:** so the only thing we did was post it on ZipRecruiter and I shared it in our podcast Discord, because of course that's a great place to get hired. and, yeah, so ZipRecruiter, I did get a lot of matches really fast. I, I probably have about 200 unread applicants, in there right now. I, it got to the point where, yeah, like after about two days of reviewing all the ones that came in, like.

[00:04:50] **Adam:** So, you know, it takes a couple of hours to get spun up, but then it basically, they start coming in faster than you can review them. and it just got to the point where I was like, okay, I, I'm drawing the line in the sand here because I'm never going to finish if I just keep trying to go through them all.

[00:05:03] **Adam:** So, like everybody that's applied up to this point, I will review and, I started doing phone screens and so the process has started. We haven't even actually started interviews yet. We're probably gonna start that like tomorrow, but,

[00:05:15] **Ben:** Do you have any sense at all, like a vibe check that you're getting things that are written by ai because I,

[00:05:23] **Adam:** Yeah, that's a really good question. I have had a couple of suspicions. So the thing about resumes, man, you look at a resume and people. I don't wanna call about, call out anybody in particular, but you know, you get resumes and it's like, oh yeah, I worked at Apple and I worked at Amazon and I worked at this like, no name insurance company, you know, and I've got like 10 years of experience and eight of it is as a senior developer.

[00:05:47] **Adam:** I'm like, hmm.so I don't know. Like I, the thing that has kind of rubbed me in the wrong way a little bit is I've been doing phone screens, right? Which is basically just like, just get 'em in on 15 minute phone call, on video chat. and I had very specific instructions. It's like, wear headphones and be prepared to be on video.

[00:06:08] **Adam:** Right? And if you couldn't do those two things, then it's, you know, I'll chalk to you just to be polite. It's only 15 minutes of my time, but that's gonna be an automatic no for me, because I said that I made it very clear in like three different places, wear headphones, be prepared to be on video. and if you showed up without headphones, it's a no.

[00:06:24] **Adam:** and, but then like. I would say like 98%, if not more, of people do the, like, blur my background or, or put a picture up as my background, which is generally fine. I don't have a problem with that. You know, you, you showed up, you're wearing headphones, you're on video, great. But then you hear like 15 people talking in the background, and I'm like, that's kind of shady.

[00:06:45] **Adam:** Are you interviewing? Yeah. Yeah. Are you interviewing from Panera or are you in like a call center? Like I I've heard of these.

[00:06:52] **Tim:** you North Korean

[00:06:53] **Adam:** yes, exactly. I don't know if you saw those stories, but like, there's, there's, it, it's people just trying to make money to send back to North Korea, I think, and,

[00:07:02] **Ben:** Crazy.

[00:07:03] **Adam:** or, or infiltrate American companies,

[00:07:05] **Tim:** one of, one of the articles I read that they were trying to infiltrate this company, the people interviewing figured out, they had asked him a question and they could see the reflection on his glasses that he was looking at, at, at an ai, like a chat GPT or equivalent to get the answer. And so they, they, they denied him and then they just started, but they actually started looking, reviewing the rest of their interviews.

[00:07:28] **Tim:** They had a bunch of people that were just, they were, yeah. North Korean spies that had been placed in there to try to get into the organization.

[00:07:34] **Adam:** Wow. Yeah, I mean, I did have one guy that he always seemed to need a minute to gather his thoughts before answering me. and I kind of pretty quickly realized, like with the tougher questions that, he was googling or, or asking an LLM or whatever. But, so, yeah, I mean, hmm.

[00:07:54] **Ben:** Yeah.

[00:07:55] **Adam:** it's a whole thing, you know, you're gonna get the fire hose.

[00:07:57] **Adam:** I, you know, my system so far has just been have these 15 minute phone calls with people, write down some notes, and then at the end of the call, I put a couple of emojis next to their name. I just use the red, yellow, and green circles. And it's like, you know, a red circle is no two red circles as hell.

[00:08:11] **Ben:** No. Um,yellow is like, eh, maybe. And then I do like one, two or three green circles.and, I think on the, so Chris Coyer does, he runs CodePen and they just recently re re restarted their CodePen Radio podcast, which is one of the ones I enjoy. And he was talking about, they just hired a person, or they're trying to hire a person and they got like a thousand submissions. And he said that he has a tool that filters things out based on an AI evaluation.

[00:08:46] **Ben:** He said, I feel totally gross doing it, but. I don't know what other options I have.

[00:08:52] **Tim:** Yeah.

[00:08:52] **Adam:** Yeah.

[00:08:53] **Tim:** Yeah.

[00:08:53] **Tim:** You drinking from the fire hose? I will say, and I do have to apologize. I know I slandered HR a couple episodes back about trying to get the link to the, but. You know, looking at how many that is the one nice thing that I didn't have to do that you're having to do, Adam, is like, I could just tell hr, I'm like, here's my minimum criteria for even bothering to show up to talk to these people. And he, you know, here it is. but then all that I did like sneak my, I'm like, oh, and by the way, if you see this resume from this person, I don't, I wanna talk to them 'cause I recommended them. So,

[00:09:22] **Adam:** Mm.

[00:09:23] **Ben:** Nice.

[00:09:24] **Tim:** so,

[00:09:25] **Adam:** Yeah. So,

[00:09:26] **Tim:** have that front line

[00:09:28] **Adam:** yeah,

[00:09:28] **Tim:** things out.

[00:09:30] **Adam:** it's weird though, like doing these phone screens. You know, I, I have a service that I use. Sorry, I bought my mic. I'm gonna retake that. It's, it's weird doing these phone screens. I have a service that I use that I can just like, send people a link and they can schedule on my calendar and it, it doesn't let them schedule when I have other meetings and stuff, which is nice.

[00:09:47] **Adam:** and that's another like, kind of disqualifying thing. Like if, if I send somebody the link and they can't figure out how to schedule with me, like, you're a web developer, you're supposed to be able to handle this sort of thing. but like. The, I I end up with a very disjointed day. It's like my whole day today I was doing phone screens.

[00:10:04] **Adam:** I had a couple, I had like a, a standing meeting for our Salesforce integration, and I had my break for lunch and, you know, a couple of like little things, but then it's like 15 minute meeting and then 20 minutes or, or 30 minutes off and then another 15 minute meeting and then 15 minutes off and 15 minute meeting.

[00:10:20] **Adam:** And it's just like a, a ton of these tiny little chunks of time where it's, there's no real way to get any actual, like, coding work done. So it's like, just try to stay on top of my email and I don't know,

[00:10:31] **Tim:** Gotcha.

[00:10:32] **Ben:** that's gotta be brutal. I mean, just the idea of not writing code in four days is, I feel like that only happens to me on vacation.

[00:10:39] **Adam:** I, I did qualify it. I did say no code for work

[00:10:42] **Ben:** Yeah, yeah,

[00:10:43] **Adam:** days. I have, yeah. Jump run I've been working on, but

[00:10:45] **Ben:** Nice toy.

[00:10:47] **Adam:** yeah. Right. It makes me second guess it a little bit. The idea of wanting to go in, I don't know. I think I got into that and like, you know, you're not, you're not hiring every week or you know, at least not at our scale.

[00:10:59] **Adam:** so there would be other things, but this week was kind of rough for me anyway. Why don't we move on? that's what I got going on. How about you, Ben?

## [00:11:07] Ben's AI Triumph and Fail

[00:11:07] **Ben:** I'm gonna go with a sort of a triumph fail split, and I'm gonna call it a split 'cause they're both in the AI adjacency world, but kind of two different takes. So we've talked previously about AI and agent to co-generation and we a little dabbled. We've touched, we've touched, and one of the things that I keep coming back to in my mind is, is the idea of software as craft dying.

[00:11:33] **Ben:** Do we actually care about the quality of the code that we're generating? If AI generates a 10,000 line pr, can we honestly say that we're going through and trying to clean that up and, and adhering to standards that we hold dear in our hearts and, and discord. show friends of the show, Sean Corfield and, and Adam Cameron, both of whom I believe have self-reported as making actually quite good use of ag agentic coding tools.basically were highly critical of something I had wrote, and I'm not gonna get into the pros and cons of whether or not they were right or wrong. but it, it was, it was I think, very helpful for me to see two people who both use AI also feel extremely strong about the quality of code. And that made me very hopeful.

[00:12:27] **Ben:** I'm like, okay, the, we're not just gonna throw stuff in the trash and stop caring about it.

[00:12:33] **Adam:** That is not where I was expecting you to go with that. When I saw how you wrote this down in the show notes that don't exist.

[00:12:37] **Ben:** No, no. Like, 'cause I'm, I'm

[00:12:39] **Tim:** was a journey right there.

[00:12:40] **Ben:** part, me,

[00:12:41] **Adam:** I like it

[00:12:42] **Ben:** like, afraid people's desire to write good stuff is just dying.

[00:12:46] **Adam:** Yeah,

[00:12:47] **Ben:** and, and I don't, that's just that, that kind of made me hopeful. So I'm, I'm saying that's a triumph.

[00:12:51] **Adam:** yeah, for sure.

[00:12:53] **Tim:** I mean, you think about it, it's like that's their personality trait. I mean, Adam Cameron cares to an extreme level.

[00:13:01] **Ben:** No, I, I totally understand. Yeah. Yeah.

[00:13:03] **Tim:** yeah, even regardless of what tool he uses, he's still gonna care. But then you have other people who are like, they don't care, and they're

[00:13:09] **Tim:** like, oh, this, this is super, this is

[00:13:11] **Ben:** But then, but then they're not gonna care to begin with. So I'm, you know, I, I'm, I'm, I'm more this, this is why it was so interesting for me 'cause it was in the realm of people that I know care deeply and continue to care deeply. And it's not just AI hasn't come in and just completely trashed the way they've used software developed.

[00:13:28] **Adam:** And, and I can't speak for the either of them, but I, I would bet a large sum of money that neither one of the two people that you mentioned, even though they have, you know, used a lot of AI code generation has generated a 10,000 line PR and, and submitted it full stop. Right. That that's not even to say that they have submitted it without reviewing it, I just don't think that they have done it, period.

[00:13:48] **Adam:** Like maybe generate in small chunks or do whatever, but like that's just not a thing that people who care do.

[00:13:56] **Ben:** I can dig it. Alright, so, so that was the, I'm gonna call that the triumph. And then the failure side of AI is, I've seen a lot of people just rave about the voice mode of chat, GPT.

[00:14:08] **Adam:** Mm-hmm.

[00:14:09] **Ben:** And I tried it like a year ago and it was actually the reason that I originally upgraded to a paid version of Chat GPT. 'cause I kept running into my, like you could only talk for like 20 minutes a day or something.

[00:14:22] **Ben:** It was pretty small. I, but then I stopped using it. I've seen people just rave and rave about how great it's gotten, and they're driving in their cars and they're having these deep conversations. And so on Sunday, I was like, all right, let me actually try it again. Maybe it's improved greatly. And I had, I went for a walk and I had like a 45 minute talk with Chat GPT about the piece of software that I'm writing.

[00:14:46] **Ben:** And it just felt worthless. It felt like the whole time the Chat GPT was just agreeing with me. Even when I said, what am I not considering? How could I improve this? And I'm not saying this to toot my own horn, but it kept being like, oh no, you've thought so deeply about this. And like, I think, I think actually all the things that you've laid out are really, are really well thought through.

[00:15:08] **Ben:** And this is really, you're just, you're coming up with such interesting takes and ways to think about this problem space. And like literally, I'm sure you can with like a thousand things that I was doing wrong. And I don't know, it's. It just, it felt terrible and I'm, I don't know if it's just me continuing to hold it wrong or what, but I, I just, I find it so, so the gap between talking to Chat GPT's voice mode and talking to another human being feels so massive to me still, despite the fact that it sounds like a human.

[00:15:45] **Adam:** I have never once tried to have a long conversation with it, like I've done the voice thing. Just 'cause it's easier than typing.

[00:15:50] **Ben:** Yeah.

[00:15:52] **Adam:** Yeah, it's like maybe three question and response things in a row, and then like I'm done with it. I've gotten what I needed out of it and

[00:15:59] **Ben:** I mean, you know, to its credit, I was able to jump around a lot in the conversation, and it was the, the context that it held was actually pretty solid. You know, I've been like, oh, let's talk about rate limiting. Okay. Okay. Let's talk about some other security. Okay. Let's talk about some database schema.

[00:16:16] **Ben:** Yeah. A hundred percent and, and it could jump back and forth. So, you know,

[00:16:21] **Adam:** you tell it about the podcast you listened to?

[00:16:23] **Ben:** it clearly, it clearly is very good at keeping this context window, but it just, it just feels like it falls so short of having an actual, meaningful conversation.

[00:16:35] **Tim:** I, I I wonder if like, setting the context would be more important there to get a better result because I, I was looking at one of our patrons, I think it was Spiffy Tech, he, he put something in the channel about what he uses as sort of a base

[00:16:49] **Ben:** Yeah.

[00:16:49] **Tim:** level set. And one of it was, you know, I don't need you. To tell me how good I am.

[00:16:55] **Tim:** I don't need you to be Syco fan and, and, and build up my ego when, when I do crap, tell me I would do crap, you know,

[00:17:01] **Adam:** challenge me, things like that. Report confidence level.

[00:17:04] **Tim:** right, you're right before confidence level, things like

[00:17:06] **Tim:** that. So I, I think, you know, you're just using the vanilla settings and chat. GPT has made an assumption that, I assume it's chat, GPT you're talking about, but, that, that people want to feel good,

[00:17:17] **Tim:** right?

[00:17:17] **Tim:** When they ask a question, right? They don't wanna feel dumb. So it, it fault is, oh yes, you what a wonderful question. You're thinking so hard. And

[00:17:26] **Ben:** You, so then, so then I get frustrated because I'm like, I don't know if I'm just holding it wrong or if it makes me so sad that there are so many people who are like, oh, this is, this is what meaningful human conversations are like.

[00:17:42] **Adam:** Low bar.

[00:17:43] **Tim:** oh, someone who understands me.

[00:17:46] **Adam:** Ben, are you watching the season of South Park?

[00:17:49] **Ben:** I am. I didn't know if I should bring it up only because I, you know, I tend to go on tangents. On tangents. But yes, episode three, which I

[00:17:55] **Adam:** Yeah. Yeah, so good. I, I mean, to be fair, I have not been like a lifelong watcher. I, I took like 10 years off or

[00:18:03] **Ben:** Yeah, yeah. No,

[00:18:04] **Adam:** I heard the season was good, so I started watching it up again.

[00:18:06] **Ben:** I'm sure this season has brought a lot of people back.

[00:18:09] **Adam:** yeah. Anyway. So, let's move on. Carol is not able to be with us, obviously. She, I'm sure she would've had comments on all of the above.

[00:18:17] **Adam:** but, she's not with us tonight, so we're just gonna have to move on without her. And, we miss you, Carol.

[00:18:22] **Tim:** The

[00:18:23] **Tim:** show goes on,

[00:18:24] **Adam:** yeah.

## [00:18:25] Soft Deletes and Other Crimes

[00:18:27] **Adam:** So, as I mentioned at the top of the show, we're gonna talk about, soft deletes and other crimes today. well, why don't we start with soft deletes. Mm-hmm.

[00:18:32] **Tim:** and

[00:18:32] **Ben:** soft delete, so, so this is something that I wanted to talk about because at work I am using the CF Wheels framework, which is based on the Ruby on Rails framework. So it's a very fully baked. Framework comes with its own ORM and the O, the ORM or object relational mapper, I think is what it stands for, has baked into it this notion of soft deletes where essentially for those who are not familiar with the term, a soft delete is a way to mark a record in the database as having been deleted or deactivated or archived, whatever your terminology of choice is without actually physically deleting the record from your table.

[00:19:16] **Ben:** so the idea would be that you can keep that record around for historic reasons, or you can keep it around for reference reasons. If you have in it referential integrity, you have to worry about, so anyway, WHEELS has this baked in where if you have certain columns in your database, like deleted at it will automatically invoke this soft deletion mechanics and yeah, it so, so.

[00:19:43] **Ben:** I've dabbled with soft deletes in general in usually a much more highly scoped way. Like I want this one table to have records that are soft deleted for reasons that are very specific to the business. I, I've never done it in a general cross the board behavior, so I don't have good instincts for it, but I was excited to get into trying it.

[00:20:04] **Ben:** And so we're implementing soft deletes across all the records, and it's in the world of manufacturing. So there's actually a lot of interesting compliance stuff that they have to deal with where we, I think we actually do need to keep a lot of these records around, both for historical reasons, but also for audit trail types of reasons.

[00:20:22] **Ben:** And, like so many things in programming, it feels like just because you can do it doesn't mean you can do it without a plan. I had no plan going into it, and I don't think anyone on my team necessarily had a plan going into it. And what I'm realizing is that there are a lot of questions that probably need to be answered before you can just willy-nilly spread soft deletes across your entire application.

[00:20:50] **Tim:** Mm-hmm.

[00:20:51] **Adam:** Oh yeah, totally agree. I, I kind of, painted myself. I won't say I painted myself into a corner, but I dabbled with soft leads, kinda like you're talking about without a plan in jump run. And I, I guess maybe I could say it's, I can't think of a concrete example, but I can, I feel like it has caused me, caused me grief here and there.

[00:21:09] **Adam:** Like, oh, that's, that's soft deleted. And I didn't think about, you know, okay, I gotta hide that data, or it doesn't apply in this case, or, or whatever. I mean, in some places it's definitely gonna be important, right? So like, if somebody deletes their account, you know, they still have, they may, they could still have history with like, you know, jumping on at somebody's airport or whatever.

[00:21:29] **Adam:** And we need to be able to keep a record of that. So that soft delete makes sense there, but there's certain things where I feel like maybe I shouldn't have done a soft delete. And it, I, what I don't have, is a good understanding of like black and white, clear line of this is a good candidate versus a bad candidate for a soft delete.

[00:21:49] **Adam:** Do

[00:21:49] **Ben:** Well, so let me, let me paint a concrete picture just because this, I, I had a very specific scenario that I came across where it clarified in my mind that I had no, I idea what I was doing, which is, if you think about, if you think about a, a, a data model where you have kind of your big, beefy main models, like,you might have a, a flight or a jump or something, or a user, and then you have your sort of, what I typically refer to as a my lookup table models, like my, account type or my plane model kind of a thing.

[00:22:25] **Ben:** and what I realize, all of these things currently have the ability to be soft deleted. You could imagine, let's say you have a user who signs up for jump run and when they sign up, they sign up for a paid plan. And let's say the paid plan's called like, you know, August, 2025 giveaway. I'm just making

[00:22:42] **Adam:** Sure. Yeah. Yeah.

[00:22:43] **Ben:** And so they sign up for that and they get a price and they're using the system. And then you say, you know what? I don't want that plan to be available anymore, so I'm gonna soft delete it from the system. So the, they still have it, but no one when they're signing up can pick that plan anymore 'cause it's been soft deleted.

[00:22:58] **Adam:** Right.

[00:22:59] **Ben:** Now imagine that you go into some administrative UI and you go into edit that user. And part of editing a user is the ability for the administrator to just arbitrarily change the person's plan. 'cause maybe it changes something about their quotas. All right, well if you go in to edit a user who has a plan that's been deleted, soft deleted, you're like, well, normally I wouldn't wanna show that in the dropdown menu of the plans that the person can select.

[00:23:25] **Ben:** But if the person already has this plan. I have to be able to select it because otherwise I might go to save the form and the administrative section says, whoa, this user can't have this form. It doesn't exist. Or this, sorry, user can't have this plan. It doesn't exist anymore. And you're like, well, they already have this plan.

[00:23:40] **Ben:** I'm just trying to edit their name. It just happens that the plan type is also being submitted with that form and being validated. And so something like that happened and I was like, oh wow. This is a huge problem. Like it's a huge problem that I don't know what I'm doing.

[00:23:53] **Adam:** Yeah.

[00:23:54] **Tim:** It,

[00:23:54] **Tim:** it's definitely a rabbit hole, right? I

[00:23:56] **Tim:** mean, you start, you start thinking about, so for instance. You think, well, I'm just adding a field to a column is deleted equals true.

[00:24:03] **Tim:** Do you need to know what the date it was deleted?

[00:24:06] **Adam:** Right.

[00:24:07] **Ben:** right,

[00:24:08] **Tim:** And, and then also you're adding sort of a performance tax, but now it's a field that you basically have to filter on every single time.

[00:24:15] **Ben:** right. Then you have to think about your index

[00:24:16] **Tim:** you gotta think about your indexing. Yep. And then you got, so if the table's relational, and most of them are, so if you delete a parent one, it is deleted and it's flagged as deleted. Do you have to delete all the children?

[00:24:30] **Tim:** Right. And, and then are, are you really auditing it? So if you're still updating, like say you update things in the row, but you're not deleting it, you're not really preserving history

[00:24:41] **Ben:** Yeah. And yeah. Yeah, exactly. It's not like it's an event stream.

[00:24:44] **Tim:** right, let's say you're working in, in Europe where you know, a person says, I want you to delete my data, and you just hit a flag. You haven't really deleted it, it's still there. So what do you do in that case?

[00:24:56] **Ben:** Oh, that's interesting. Right. That's kind of part of the GDPR compliance and the right to be forgotten kinds of stuff.

[00:25:02] **Adam:** Yep.

[00:25:02] **Tim:** then you think, and you say, well, one of the benefits is I can easily restore it. Is it really easy because you flip that flag now, do you have to go and cascade to everywhere else that parent record and all the child cons, you know, constraints and joins are, you

[00:25:16] **Tim:** have to go restore those so it, it gets, it seems simple like, oh, just create a flag.

[00:25:21] **Tim:** We'll mark

[00:25:21] **Tim:** it as deleted. And then it's like you start thinking about it. It's like, no, this thing really kind of goes

[00:25:28] **Tim:** deep.

[00:25:29] **Ben:** Yeah. The other thing that we've run into, or I should say I've run into is that a lot of our, a lot of the models within this manufacturing scheme have synthetic, not synthetic keys. synthetic key would be like a primary key, an auto increment or a, like a semantic key or, or a normal key.

[00:25:49] **Ben:** What do they call it? Like when you use your social security number,

[00:25:51] **Adam:** gay.

[00:25:52] **Ben:** surrogate key. Yeah. So a lot of the things in this world have a surrogate key. That'll be something like the first three letters of the name of a machine,

[00:26:02] **Adam:** that's more like a natural key. A

[00:26:03] **Ben:** na Okay. Now, yeah. Yeah. Natural key. Natural key.

[00:26:05] **Adam:** yeah, surrogate key is when you do like a 1, 2, 3, 4, 5, because you don't wanna use social security number or, or whatever. You don't wanna expose that personal information as the key, even though it would be poten, not social security number is a bad example because it's not supposed to be a key, but you get my point,

[00:26:21] **Ben:** I get your point. So, so there might be, machines that buffer that, the DBER stuff. So you might have a machine that's like Dber one and then Dber two and Dber three. And these are being named by the engineering team, by the mechanical engineering team. So they have to be unique, and we try to enforce that at the code level.

[00:26:41] **Ben:** And eventually we'll probably try to enforce that with some sort of a unique index on the tables. But then you throw soft deletes in there and suddenly now you have to, well, it has to be unique, but what if you've already deleted a field that has that code on it? Well, that's really only unique across the active ones, not the inactive ones.

[00:27:00] **Ben:** And then going back to Tim's point. What if they wanna reactivate an old machine that has now a conflicting key with another existing thing? There's just it. It's just rabbit hole upon rabbit hole, and I'm realizing that I had no plan. I'd never really stopped to think about how any of it should be used, only that the framework made it available in a fairly easy mechanic, so let's just do it

[00:27:23] **Tim:** So I, I guess really you need to kind of maybe look at what's your use case, right? So you're just looking for a quick and easy way to hide some data and it's not, and you know, it's not gonna get any more complex than that. You know, a flag for a soft delete is probably okay. You know, make sure your ORM has the filters built into it, or maybe put it in the view, a database view or something. But really, if your thing is you want an audit trail of what's happened, you need, you need versioning,

[00:27:51] **Ben:** right. That needs to become a lot

[00:27:53] **Tim:** audit tables are event sourcing

[00:27:55] **Ben:** Ah, but it, it's so interesting 'cause you also mentioned the, well, what if you soft delete one record that has semantically children records? Do you then have to soft delete all of those records? And that's even something when I've dealt with this stuff in the past, I've sort of hand waved over, the way that I've historically handled soft deletes is I will actually have a sibling table that is for the deleted records.

[00:28:20] **Ben:** So I might have a user table and then a user archive table. And if you're gonna delete that user, I physically, you know, I have a, an army of machines do this for me, of course, move one record in from that table into another table. But I don't cascade that to all of the records that might reference a user, you know, like a user preferences table.

[00:28:42] **Adam:** Yeah.

[00:28:43] **Ben:** I, I don't archive all those things because they'll just, they'll just point to a record essentially that no longer exists because it's been moved, and I've just kind of been okay with that.

[00:28:51] **Adam:** are you not enforcing referential

[00:28:53] **Ben:** No, I don't, I hate, hate foreign keys.

[00:28:56] **Tim:** Oh buddy.

[00:28:57] **Adam:** Ugh. Yep.

[00:28:59] **Ben:** They make everything so hard.

## [00:29:00] Archiving vs Soft Deleting

[00:29:00] **Tim:** See, see that's, see that's where it gets sticky. 'cause like, I think a lot of times people will overload, archiving with deleting, right? They're like, you know what I

[00:29:09] **Tim:** mean? So that they're like, I, I, I, I, I don't wanna get rid of this thing, right? So I'm just gonna do a soft lead. But really what you maybe we, what you're really, and and eventually that is, and then eventually you think, well now that I'm archiving, now that I'm soft deleting this, I need to like maybe just hide this stuff.

[00:29:25] **Tim:** And you, you're conflating archiving the soft deleting and they're

[00:29:28] **Tim:** really two separate things,

[00:29:29] **Adam:** Yep, yep, yep, yep. I was gonna say the same thing. we have tables where we have millions and millions of rows and it's like, well, we, we kind of need to keep this data for historical purposes in case something comes up, but we don't want it there. Like it's not used in everyday use. The only thing it does on a daily basis is slow down queries, because now there's when, when you occasionally hit the thing that has to do a full table scan, oh, now it has to look at 5 million rows when it could just look at 750,000 if we had done some, semi aggressive archiving.

[00:30:00] **Adam:** and so we, we do have some semi aggressive archiving processes that just move rows over into an archive table, and I was like, I don't know, Ben, you might wanna just call that table deletes instead of archives.

[00:30:12] **Ben:** So, so here's something even fun in that regard because I, that's how I've done it historically, and I ran into, let's call it a, a pretty extreme edge case. But I did run into this, and this might be very specific to MySQL, the. I had, thankfully this only ever happened in local development where I actually had full control over the database and it wasn't dealing with any kind of high transactions.

[00:30:35] **Ben:** but if you can imagine when you're inserting records into a table and there's a auto incrementing primary key on the table, you insert a record, it gets one, you insert the next record, it gets two, and so on and so

[00:30:45] **Adam:** A surrogate key. Go on.

[00:30:46] **Ben:** Yes, exactly. Thank you. and then let's, okay, so let's say this is a user table and you're incrementing, incrementing, incrementing, and then you also have a separate table for user preferences, and it's using the user ID as it's foreign key, primary key.

[00:31:03] **Ben:** So it's basically like an extension of the user table.and like I was just saying earlier, I've done things where I archive, quote unquote archive the record out of the user table. But I don't worry about the user preferences table because it kind of just becomes this orphan record

[00:31:17] **Adam:** Mm-hmm.

[00:31:18] **Ben:** I discovered, at least in my sql, if you restart the database.

[00:31:24] **Ben:** It basically, truncates the difference between the max ID in a table and the last used primary key. So let's say I, I created user 100,

[00:31:36] **Adam:** Mm-hmm.

[00:31:36] **Ben:** and then the next user that would be created was user 1 0 1. And the user after that was 1 0 2. So let's say I go in now and I archive 1 0 2, 1 0 1, and 100.

[00:31:45] **Tim:** It goes back to

[00:31:46] **Ben:** Even, even at that point, if you were to then create another user, it would be 1 0 3.

[00:31:51] **Ben:** But if in between the archiving and the next user creation, you restart the database service, the next user record becomes 100. Again, because, I don't know, it cleaned up whatever, INM memory counters or something. And I ran into an issue where it was like, oh, your user preferences record with 100 already exists.

[00:32:09] **Ben:** And I was like, what? And then I was like, I really panicked, because I'm like, oh crap. How long have I been doing this? But I, you know. It's, you'd have to be restarting and archiving right at the head of the table for this to be meaningful, but it did give me a moment of panic.

[00:32:24] **Adam:** Hmm. I could see it biting you. Yeah.

[00:32:27] **Ben:** Yeah, it, it's, it's a non-zero chance, but it's definitely an outlier, like a pretty heavy outlier.

[00:32:33] **Adam:** Interesting. I, I mean, we use MySQL. I don't recall ever running into anything like this, although we don't, we, we enforce referential integrity, like a sane person. So, uh,you know, maybe that's what saved us. But, yeah, I don't know.

[00:32:48] **Tim:** Yeah.

[00:32:49] **Adam:** I've heard of index compacting, which it sounds like is what's, happening to you there

[00:32:53] **Ben:** That might be what happens.

[00:32:55] **Adam:** yeah. Dunno, buddy.

[00:32:57] **Tim:** I mean, and I, I'd also say, if you're going to do this, a lot of times people put the, like, the restore logic for a soft delete kind of as a tomorrow problem. They,

[00:33:07] **Tim:** they, they do all this stuff for,

[00:33:09] **Ben:** hundo.

[00:33:10] **Tim:** I mean, on

[00:33:12] **Tim:** And then the CEO is like, Hey, we need to restore that record. And you're like, oh, we haven't really tested this.

[00:33:18] **Tim:** I hope it works.

[00:33:20] **Ben:** Yolo.

[00:33:22] **Adam:** Lemme pull up the production database in my, in my.

[00:33:26] **Ben:** Yeah. Yeah. Lemme just run an update on the production database.

[00:33:29] **Ben:** No

[00:33:29] **Tim:** Whoops. It actually truncated this table. I don't know how that happened.

[00:33:33] **Ben:** So, yeah, I kind of don't know what to do right now other than I kind of want to go through and just remove every notion of soft delete, and then just let the business ask for it when it becomes necessary.

[00:33:48] **Adam:** Hmm.

[00:33:49] **Ben:** Because right now I think I'm just accruing a bunch of technical debt. That is only gonna continue to make the application harder and harder to maintain.

[00:33:59] **Adam:** It's an interesting thought. I mean, I guess the question is how, how much of this application or this, this functionality with softly has already been in the wild in production

[00:34:08] **Ben:** Okay, so the good news is this is all still in a staging

[00:34:13] **Adam:** pre-release. Gotcha. Yeah. Then I'm with you. Like I would, I would rip it out because in my experience, true need for soft deletes is. Somewhat rare, at least in, you know, in the verticals I've been working in. and so we do, well, you know, I say that, but we do also have like active and inactive. Like sometimes there's data that your admin users want to still know is there, but they just don't want it to be exposed to the, the, what we'll call 'em public facing users.

[00:34:42] **Adam:** Right. The, that's a, that, that's a word. I don't know, but keep going anyway. yeah, so, so we'll, we'll use like an active inactive situation, but not a, a softly and effectively it's kind of the same thing. You're just showing those inactive records to certain customers, the, the high privileged customers.

[00:35:02] **Adam:** But yeah, I mean the, they seem to cau soft deletes seem to cause more trouble than they save you from if you just do them willy-nilly.

[00:35:14] **Tim:** Mm-hmm.

[00:35:16] **Ben:** And to Tim's point, we're definitely gonna need an auditing system and, and this won't help

[00:35:21] **Ben:** us with that anyway.

[00:35:22] **Tim:** Yeah, yeah. I mean, maybe this, maybe it's the next project you work on, Ben, because I mean, I know like, so asp.net, they have like, entity framework audit tools, which we use, at, at work to like, it's a pretty easy nuget package to in store. And if you're using entity framework, it automatically handles like versioning of everything.

[00:35:43] **Tim:** An audit, complete audit log, which is. For us and financial stuff is extremely important. But yeah, create a, cold fusion, audit package for,

[00:35:53] **Adam:** CF entity Framework.

[00:35:54] **Tim:** there you go.

[00:35:56] **Ben:** Underneath it just as a, CF execute install framework.

[00:36:01] **Tim:** Calling

[00:36:02] **Ben:** Oh,

## [00:36:03] Other Crimes: Mutable Filtering

[00:36:03] **Adam:** Oh, so go Shall we move on to other crimes?

[00:36:06] **Ben:** sure. What other

[00:36:07] **Ben:** crimes.

[00:36:08] **Adam:** I'm, I'm gonna bring up something that was on the discord, but I didn't have time to follow it the day that it was on there.

[00:36:14] **Adam:** It's the day, it's what you mentioned earlier, the, the, code you posted that Sean and Adam had some, some negative comments about,I, I like,

[00:36:23] **Tim:** the what about filter?

[00:36:24] **Adam:** yes. So, so Ben posted some code, it used a filter and it had side effects, and like I said, array filter sort of situation, and it had side effects in it, and they were raking 'em over the co This is me

[00:36:36] **Ben:** No,

[00:36:36] **Adam:** the summary that I'm,

[00:36:38] **Adam:** yeah, yeah.

[00:36:39] **Ben:** a.

[00:36:40] **Adam:** I'm summarizing based on kind of like what I was able to skim, but yeah, it sounded like you were getting raked over the coals for it. I don't know if you would still defend that behavior or if that was AI written code or what, but,

[00:36:52] **Ben:** so, so here's the context. 'cause I still feel like, so this is actually in code that I have and I left it as is. 'cause it's, it's, it does what it's supposed to do. I think. I mean, the code's doing what I wanted it to do is what I should say. so essentially I'm, I'm making an API call to an external service that for reasons that are, are a little dodgy to me because the API is not really well documented.

[00:37:19] **Ben:** It'll return an array of items and sometimes those items have incomplete data. And I think it's because that service is itself using some other set of APIs to aggregate information. So I have this possibly incomplete set of items. What I want to do is normalize it into a structure that I know is predictable.

[00:37:42] **Ben:** So like if, let's say that there's, it's, it's ba it's for word stuff like language words. And so one of the things that I have is a syllable count, but sometimes the syllable count isn't included. 'cause maybe it didn't have that metadata for that word. I will just default to zero on my end so that I don't do like a syllable count doesn't, you know, as a null key on that object kind of a thing.

[00:38:05] **Ben:** So I want to normalize the response. And then also there are things that I can't normalize. Like they're just literally, it's data that I won't know what to do with. So in those cases, I just wanna ignore them. So I have one function, which is my filter operator, which both normalizes the data as it's iterating over the collection and filtering out the ones that are basically unrecoverable. So

[00:38:29] **Adam:** Okay. So it is doing filtering too,

[00:38:31] **Ben:** Yes, it's filtering and normalizing at the same time, and it's, it's in a very specific workflow, and it doesn't have variables being, it doesn't have intermediary variables. I basically make the API call and then call dot filter on that response. So it's, I don't know, like it's, it's just doing exactly what I hoped it would do.

[00:38:53] **Adam:** I'll be right back. I have to go get my pitchfork.

[00:38:56] **Ben:** So, so here's something interesting, right? Because I, we, we've talked on this show many times about the importance of words and, and words mean something, and you could very quickly come down on either side of this argument. I think

[00:39:11] **Adam:** No,

[00:39:13] **Ben:** so. So the, the big example that stands out in my mind is for years and years I have read and heard people say that singletons are an anti-pattern in software development,

[00:39:26] **Adam:** uhhuh.

[00:39:26] **Ben:** and in my mind, a

[00:39:28] **Adam:** How did the fart smell?

[00:39:30] **Ben:** And in my mind, a singleton is a thing. You have one instance of, because, that's just, that was the mental model I created when I heard the word singleton. And I was watching a presentation several years ago and one of the guys was saying that he likes to instantiate an object and then cashed in memory and then shared that for the rest of the application.

[00:39:51] **Ben:** And one of the other guys on stage said, oh, you mean a singleton? And he goes, no, I mean, a single instance, a singleton is an entirely different pattern that doesn't allow you to create multiple instances of something. I'm not preventing you from creating multiple instances. I'm just caching one and I'm using that one.

[00:40:09] **Ben:** It's not the same thing. And I was like, oh my God, that makes, so, like, that's 'cause that's how I build my cold fusion apps. You know, I have a ton of cold fusion components. CFCs, I instantiate them, I store them in the application scope or in a dependency injection window or a, you know, whatever you call 'em.

[00:40:25] **Ben:** Um,yeah, thank. And so I'm like, oh, okay. I've been carrying around this guilt for something that I have misunderstood mechanically for years. Okay, so bring this back to filter for a second. Because like many people, I have used filters in a somewhat immutable context. I have one array. I want to create a totally separate array that has a different subset of items. So I've gone back and forth on abusing this several times in the past, and I came to this one where I'm talking about getting this API response in both filtering and normalizing at the same time. And I just, I didn't want to not do it for gut feelings, so I went to the MDN docs, the Mozilla developer network docs, and I said, you know, lemme just look at the filter documentation to see if there's any wiggle room here.

[00:41:14] **Ben:** Like

[00:41:15] **Adam:** you're talking about JavaScript specifically?

[00:41:17] **Ben:** yeah, yeah. I look and, and it says, what filtering does is it takes an array and it executes an operator. And if the operator returns true, it keeps it into the result and array. And if it, and if you return false, it removes it from the result and array. And at no point in any of the documentation does it say anything about the original thing being immutable, you shouldn't change the data.

[00:41:38] **Ben:** It literally just says, this is how the mechanics of the filter function work. So then I go to the array filter function on the adobe called Fusion developer docs. And it's basically the same thing. It says, this is the mechanics of the filter function, but it makes no reference to immutable data and, and how you should leave things alone or shouldn't leave things alone.

[00:42:00] **Ben:** And I'm like, and I'm like, okay. So I have built up in my mind this idea, you know, probably from, many things that people have said over the years,

[00:42:10] **Tim:** Like

[00:42:11] **Ben:** I'm realizing that.

[00:42:12] **Tim:** instructions.

[00:42:14] **Ben:** But you know, like, like you could be in the React ecosystem and understand that one way data structures or the, one way data flow is the only way you can possibly build something.

[00:42:26] **Ben:** Or you could be in the angular world and realize that two way data bindings on form controls is like a godsend. And how else would you ever wanna build forms, right? And both these people are right in their particular frameworks because that's what the frameworks allow or that's what the frameworks constraint.

[00:42:42] **Ben:** So, you know, I've listened to a lot of people and now I'm realizing that in my particular context, this is what I needed to do. And the mechanics of the language construct were not inhibiting me, nor, you know, implicitly or explicitly. So I went to use it and it worked out well.

[00:43:00] **Adam:** So what I'm hearing,

[00:43:01] **Ben:** basically by every other person on earth.

[00:43:06] **Adam:** rub my hands together here. What I'm hearing, Ben, is, that somebody handed you a loaded gun and you turned around and faced the rear of the shooting range.

[00:43:17] **Tim:** Because, because there was no sign that said, don't shoot behind. You

[00:43:20] **Adam:** Yeah. I will give you the slightest bit of, not credit, but maybe like leeway here because like you said, you went and looked at the docs on MDN, which are widely believed to be pretty authoritative.

[00:43:34] **Adam:** I'll give you some credit. 'cause you went and looked at that and it didn't specifically say, don't do this. However, if you did this in JavaScript, it wouldn't work because the filter method on an array or an Iterable is immutable. Like it does not if you, so filter, you get an instance of, you get like a copy of the object in that, in that index, in the array as it kind of loops over the array.

[00:44:01] **Adam:** Right.

[00:44:01] **Ben:** I'm not entirely sure that that's true.

[00:44:03] **Adam:** if you modify it, well, let's, we'll

[00:44:05] **Adam:** find out

[00:44:05] **Ben:** Okay.

[00:44:06] **Tim:** you,

[00:44:07] **Adam:** if you modify it.

[00:44:08] **Tim:** if you do, you're

[00:44:09] **Tim:** gonna start skipping and duplicating elements.

[00:44:11] **Adam:** Yeah. if you modify it, I'm pretty sure it doesn't save it. I'm pretty sure. like, so there's, there's like four each. There's map, which does save it, right? You got map, you get reduced, you got for each, you got filter, and, and so on. But, it sounds like what you needed, is a filter and a map where you filter it first to get rid of the ones that you wanted out and then map to defaults and values to zero, right?

[00:44:39] **Adam:** And that's inefficient. 'cause then you're doing, n times two O of n times two, right? You're looping over twice. So this is where reduce comes in. All of these, like, 99% of these other functional programming concepts can be written as a reduce, and they're, they're just helpers to like save you the syntax.

[00:44:57] **Ben:** So, so here's the thing.

## [00:44:58] Reduce vs Loops

[00:44:58] **Ben:** I, I mean, I feel like 99 times out of a hundred, whenever I think to myself, oh, this would be a perfect place for reduce. I go and I write it and it works, and I look at it and I'm just think to myself, this looks awful. I would much rather just do this as a for loop, like. I can't, I can't.

[00:45:19] **Ben:** So just the idea of, of,

[00:45:21] **Adam:** You are not a functional programmer at heart, I think, and I, I like it just sounds on brand for you.

[00:45:25] **Ben:** it's, it's, it's certainly possible. I mean, so, okay. So the, a lot of times what I wanna do is I wanna loop over a collection and, for lack of better term, reduce that collection down to a, a, a value or a set of values, like a, a set of statistics. And I will try it with the reduce.

[00:45:44] **Ben:** And you can take the, the, I don't know what the re I always call it the reduction. It's like the object that keeps getting passed from thing to thing or an accumulator. Yeah. Yeah. The accumulator.and I look at it, I'm like, this just doesn't look good. Like it doesn't look pleasing to me. And I will oftentimes then remove it and rewrite it with just an explicit var accumulator equals empty object, and then a for loop.

[00:46:07] **Ben:** And then inside the for loop, I'm just doing all the same accumulator, jazz, and it's ba and it's. I think it's oftentimes one less line of code reduces. It's like an oddly verbose thing. and I just, I just don't like the look of it. And then so I, I had said that either it was to Shaun or Adam, I don't remember who, and one of them was like, well, the way code looked is not how you should be judging the quality of code.

[00:46:34] **Ben:** And I'm like, ah, but like, isn't it?

[00:46:38] **Adam:** Well, so.

[00:46:38] **Ben:** and I think that's like where I just come down differently than a lot of people.

[00:46:42] **Adam:** I, I, I can kind of see both sides here because I think that what they're thinking about when you say how the way it looks and what you are thinking about, like, they're not thinking about the vanity, like the, the feels. It gives you the vibes of these six lines of code. They're thinking about does this look clean?

[00:46:58] **Adam:** Does, is this super understandable and is it efficient? And you're like, but it gives my tummy the, the rumbles.

[00:47:05] **Ben:** I got

[00:47:06] **Ben:** the Tumtums looking at it.

[00:47:08] **Tim:** I mean, I, I just don't understand why you don't split it up into two things. It's not that hard, right? I mean, filter. Explains what it does and it should

[00:47:15] **Tim:** do one thing. It should filter, right, so you can do it, run a filter function dot, and then after that, do a map or some or

[00:47:22] **Ben:** So, okay, so like, like this is, so going back to the actual concrete example of making this API call to this word service and then filtering down. Literally the first thing I did was exactly what you were saying, Tim, is I filtered, I think I, I think I actually mapped it onto the normalized data structure and then I filtered out the ones that, that didn't work.

[00:47:43] **Ben:** I can't remember. I, I did, I did one or the other, I can't remember. And I got to the end of it. I just said like, wish I could just combine these two. And that's actually, that's actually when I went to look at the MDN

[00:47:54] **Tim:** but did the first episode work.

[00:47:56] **Ben:** The, the first thing, the first thing did work and it, it worked exactly like a, but I just, I was like, ah, this just seems unnecessary.

[00:48:03] **Ben:** So that's when I went to look at the docs just to, for a moment of inspiration and I'm like, oh, I'll just combine these things.

[00:48:09] **Adam:** So I think the, the real complaint underlying here is that, you know, you've been given the sort of damocles and you're using it as like an envelope opener, right? Like,

[00:48:20] **Ben:** But here's, so here's, here's an interesting thought experiment. Okay? Because, 'cause someone, someone on LinkedIn was saying, oh, we'll just use flat map. 'cause flat map is basically doing more or less what I want. It's, you can, so for those who are not familiar, the map function traditionally is a one-to-one.

[00:48:37] **Ben:** You're mapping this object onto another object. Flat map. You can return an array. You essentially can fold multiple objects into the result and array instead of just a one-to-one, so multiple meaning zero or more. So you could actually return an empty array that essentially does the same thing as a filter.

[00:48:56] **Ben:** but it just, the guy wrote it out for me. It's funny how people will write stuff out for you, like you don't understand how to do these things technically. Like I'm just like, oh, if only you saw the syntax, you would understand where you went wrong and the right. So someone wrote out the flat map example, and I'm like, this just again doesn't look good.

[00:49:18] **Ben:** Like this looks more complicated. And to me, more error pro than just having a slightly overloaded filter. But

[00:49:25] **Adam:** So I, I personally have two complaints. I think that, if you had just written it as a for loop and not tried to use the

[00:49:31] **Ben:** that's, that's what Adam Cameron says. He's like, this would all just be mood if you wrote a for loop.

[00:49:35] **Adam:** right? Because it, and that's because of complaint number two, which is that you're taking a functional programming concept which has been implemented with a bug in it, which is that it allows side effects and you're exploiting that bug.and that's my opinion,

[00:49:52] **Ben:** yeah, yeah.

[00:49:53] **Adam:** what makes it true. and yeah. So yeah, I mean, I think that that really kind of nails it down. It's like if it was a for loop, nobody would complain other than, hey, it would be maybe slightly less code and a little bit easier to, to parse mentally at a glance if you did fp. But, yeah, I don't know.

[00:50:17] **Adam:** That's.

[00:50:19] **Tim:** You sort of, I mean when you see filter there's a basic contract that, that you're breaking there when you do other stuff other than filter. That's my

[00:50:28] **Ben:** according to the mdn.

[00:50:29] **Tim:** No, no. M-D-M-M-D-M didn't explicitly say not to That doesn't mean you should. Right. The intent is clear. You're filtering something.

[00:50:38] **Tim:** You're

[00:50:38] **Ben:** a social contract.

[00:50:40] **Adam:** were so, you were so concerned on whether or not you could, you didn't stop to wonder if you should.

[00:50:44] **Tim:** Thank. Thank you, Jeff Goldblum.

[00:50:48] **Ben:** So, you know, and to be clear, I, I use Filter the way it's intended in 99.99%

[00:50:56] **Ben:** of cases. This, this is really

[00:50:57] **Tim:** so, so you just post this one to get

[00:50:59] **Tim:** everybody up in arms. Okay. I, I, I see you. I see you.

[00:51:03] **Adam:** Engagement bait.

[00:51:04] **Tim:** Cunningham's Law.

[00:51:06] **Ben:** there you go. Yeah. I felt that in full effect.

[00:51:11] **Ben:** Tim was Hoy Ploy a reference to Caddy Shack by any chance?

[00:51:16] **Tim:** it's a, it, I believe it's a Roman word. It's what they called the, i, I don't

[00:51:21] **Adam:** I've heard it before, but,

[00:51:22] **Ben:** There's a scene in

[00:51:23] **Tim:** means common people.

[00:51:25] **Ben:** there's a scene in Caddy Shack where he shows up to a yacht party and one of the guys like, oh,

[00:51:32] **Adam:** Hmm.

[00:51:33] **Tim:** It means the common people, the

[00:51:34] **Tim:** masses.

[00:51:35] **Adam:** Yeah.

[00:51:36] **Ben:** gotcha.

[00:51:36] **Tim:** It's Greek,

[00:51:39] **Ben:** Anyway, I

[00:51:39] **Ben:** didn't

[00:51:39] **Tim:** means the

[00:51:40] **Ben:** a very obscure movie reference, but

[00:51:43] **Tim:** yeah,

[00:51:44] **Ben:** you're just more educated

[00:51:45] **Ben:** than I am.

[00:51:46] **Tim:** I just read, I just read books.

[00:51:50] **Ben:** Aha.

## [00:51:52] Patreon

[00:51:52] **Adam:** so this episode of Working Code is brought to you by the JavaScript Array prototype filter, which, definitely does not allow mutation of the, the items being passed into the, the, the method there. So, you know, just, just in case anybody out there needs to hear this and listeners like you, if you're enjoying the show and you wanna make sure we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:52:16] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:52:25] Thanks For Listening!

[00:52:25] **Adam:** After show tease. Basically we are gonna get on here where the outros gonna play for the Hoi Pallo, and a and, the, the patrons, after the after show or after the outro music plays, will, will still be here on the mics, and they're gonna get to hear us chat about, you know, whatever's on our minds. what's on my mind, I wanna talk about solar panels, and, a, a podcast I listen to since, you know, Ben, Ben sneaks him in all the time.

[00:52:54] **Adam:** I gotta have mine. Ben wants to talk about Alien Earth and Tim wants to talk about Dragon Cons. So, you guys wanna hear about that kind of stuff. You're just gonna have to become a patron of the show.

[00:53:02] **Adam:** Sorry, but that's just, that's what it is.

[00:53:05] **Adam:** Uh, yep. If you'd like to do that, you can go to patreon.com/workingcodepod.

[00:53:10] **Adam:** Throw a few ducks our way and we'll throw some extra episode content at you. That's, that's how Commerce works. we'd love to have you join our Discord. That one's free. You can come join our Discord at workingcode.dev/discord. Come join us, hang out and maybe get a job. that's gonna do it process week.

[00:53:28] **Adam:** We'll catch you again next week. And until then,

[00:53:31] **Tim:** We will never soft delete or break the social contract of you, my friends. Your heart matters.
