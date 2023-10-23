---
title: "149: Margin For Error"
description: "In this episode, Adam and Tim talk about margin for error in various aspects of software development, business and our personal lives."
date: 2023-10-18
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/149-margin-for-error/id1544142288?i=1000631722883"></iframe>

In this episode, Adam and Tim talk about margin for error in various aspects of software development, business and our personal lives.

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/149-margin-for-error.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** you're walking from point A to point B in life and your margin for error is how wide is the path in front of you, right?

[00:00:05] **Adam:** And, and if you take a misstep, but your path is 30 feet wide, it doesn't matter that much. But if you, You know, if your margin for error shrinks and shrinks until you're walking a tightrope, and then you lose your balance, then you're screwed, right? You might end up homeless, addicted to drugs, in jail, you know, et cetera, et cetera, et cetera.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 149. And on today's show, we're going to talk about margin for error and what that has to do with making decisions and your day to day work as a code miner, as a semi colon miner. but first, as usual, we'll start with our triumphs and fails. We are back at the bat at the top of the batting order.

[00:00:58] **Adam:** it is October. We're in October baseball here, and I'm just gonna, you know, we're Adam goes first. We're back at the top of the batting order, and,

## [00:01:05] Adam's Triumph

[00:01:05] **Adam:** I'm gonna kick us off. I got a triumph. I had what I hope will prove to be a, an insightful... Thought about our email processing pipeline today. we've discussed, at some length on the show, especially that episode that Ben and I did, just the two of us, not too long ago, you know, a lot of the hopes that we have to jump through and all of the process that we put in place to try and make this thing resilient.

[00:01:29] **Adam:** and despite that fact, I had a thought today about how, a certain, like, step in the process is a, is a common failure point and how we could improve that. And, I wrote up a quick proposal and I sent it to my team and of course they're all, like, traveling and stuff today, so, I don't, I don't have any feedback yet, but I'm excited about it. so. Quick and easy for me today. Ben has an excused absence. He is currently in Ireland. I guess we'll let that one slide. and

[00:01:55] **Tim:** and he's already over there complaining about this, the, the service at restaurants.

[00:01:59] **Adam:** is he?

[00:02:00] **Tim:** Yeah,

[00:02:01] **Adam:** I did see something from him on Facebook about, restaurant service, but I wasn't, I didn't put two and two together that he was

[00:02:06] **Tim:** he didn't even put the context there that he was in Ireland. He's like, you know, all I expect when I go to a restaurant is, you know, that, you know, they, they keep refilling your water and they ask you if you need anything and, you know, and I'm like, I knew he was in Ireland and I'm like, yeah.

[00:02:20] **Tim:** Food service norms are completely different over there. Absolutely. Completely different. They don't want to, they're like, they don't want to bother you. They're like, you know, if you need something, you need to ask, you got to be proactive, but America, we're spoiled. Cause they're always coming over. Can I refill your water?

[00:02:33] **Tim:** Or, you know, do you guys need anything? Just check in on you.

[00:02:36] **Adam:** Well, yeah, I mean, here they're, they're trying to, earn a living wage by, you know, earning a good tip

[00:02:43] **Tim:** So it'd be fun to hear his, his experiences when he get back, he should be back next week.

[00:02:48] **Adam:** and, Carol's off the hook. She had, something come up, family emergency tonight. So she's not able to make it. So it's just us tonight. So Tim,

[00:02:55] **Tim:** and Tim and Adam.

[00:02:56] **Adam:** with you, man?

[00:02:57] **Tim:** Well, I do not have an excused absence cause I'm here.

[00:03:01] **Adam:** You have an unexcused presence.

[00:03:03] **Tim:** Exactly. Why am I here? What am I doing? Why'd you invite me, Adam?

## [00:03:08] Tim's Triumph

[00:03:08] **Tim:** I'll go with a triumph. So, doing, I hate doing these. We do them every year toward the end of the, you know, the fourth quarter, we do talent reviews. And they're not, I always find them kind of nebulous and we have these qualities that we rank.

[00:03:24] **Tim:** You know, on a person and we have like three levels of scoring, you know, red basically means you need to work on this aspect. It could be execution, timeliness, customer centric, strategic thinking, things, things of that nature. And, You know, I, I have, I avoid doing them, but I'm actually doing them on time this year and I'm just kind of taking a different tack at it than, so, you know, HR makes us do these cause in our company, we're being a, one of many, many, many hundreds of companies, part of our portfolio, they're always looking for.

[00:03:59] **Tim:** Talent, you know, that, that maybe, you know, they have an opening or a need in another company, or even within the same company, if it's big enough, where like, we really need someone to fill this role. What kind of qualities are we looking for that role? And so they can look through the annual talent reviews and see people that are.

[00:04:15] **Tim:** You know, A plus star players in certain areas. and so what I don't like about the talent review thing is that a lot of times you feel like you are being graded as a human being. I think there's so much to in every individual. Everyone, everyone's special,

[00:04:34] **Adam:** No, I, I totally get

[00:04:35] **Tim:** In their, in their own way, but it's like to boil you down.

[00:04:38] **Tim:** Right. Yeah. Ask you to pass judgment on people. First of all, I always make them, I say rate yourself. Rank yourself on pick three to four qualities that you have that you feel that you excel in and pick three or four, because there's about 20 of them. And pick three or four that you really think. You really need strong work on and then the rest, you know, kind of put in the middle, then we discussed them, but what I, by my speech to people when I do their reviews, it's like, you know, be careful what you grade yourself on and if you like, for instance, if you're a developer is really not a people person who wants to solve problems, but really has no time or inclination to like, You know, sit with customers and talk to customers and, and try to figure out what their problem is, and they're going to use wrong terminology and you want to correct them constantly.

[00:05:26] **Tim:** I'm like, don't put customer centric and don't put, you know, yourself as a, as a rockstar in communication and customer centric, it's like. You could wind up in a job, being offered a job that you really don't want. so be strategic about what you say your, your strengths and, you know, and weaknesses are.

[00:05:43] **Tim:** And, I think making them see it that way that like, you know, we're not saying that you don't communicate well because in some aspects of life you communicate well, in some aspects of life maybe you don't. But if that's what you thrive on, communication, being the person who's, the person who's always communicating and build, team building, if that's what you thrive on, You know, mark yourself good in that.

[00:06:03] **Tim:** so, so I've been avoiding those, but yeah, I've actually did a couple today and I got a few more tomorrow and

[00:06:11] **Adam:** What did you call you said like talent reviews or talent something?

[00:06:14] **Tim:** yet talent review interviews. So it's basically

[00:06:18] **Adam:** a performance evaluation.

[00:06:20] **Tim:** not really perform. No, it's so we have a separate like quarterly scorecard, which is performance. Like, you know, here's your goals, here's how close you are to doing your goals. But one, and that's every quarter we do those, but once a year we do talent reviews, just basically say, what are your.

[00:06:34] **Tim:** Core competencies, what, what are you good at and what are things that, that maybe you either need to work on or just maybe you're, you know, you know, you're not good at them, you don't really have any plans on ever being good at them and that's fine. This is, this is really more for HR to say, you know, who are the people that really excel in certain aspects of, of attitudes and skills that, you know, if, if we needed to say, you know, you know, someone wins the lottery and leaves, we need a person like that.

[00:07:05] **Tim:** Now we have already have it documented that yes, you're the kind of person who already has these attributes and could possibly take over.

[00:07:13] **Adam:** It's kind of like, you know, tagging on, on, I think, you know, the only thing I can think of is blog posts, right? So you write a whole bunch of blog posts and as you're writing them, you're tagging them. And so like, you know, this one blog post goes missing. So you need to find something that can fill that same slot.

[00:07:24] **Adam:** So you're like tagging humans. Okay. This one's good at strategic thinking.

[00:07:28] **Tim:** I mean, when you, when you have, I mean, across the entire organization across the globe, you know, you have hundreds of thousands employees and you're, you're looking for someone cause they do. That's one thing I do like, they do try to promote people internally. They always, there's always anytime there's a new position, it's always, vetted internally first to see if there's people internally that want to.

[00:07:52] **Tim:** You know, move up or move on or just maybe get away from where they are now. and so that's good. so this helps with that.

[00:08:00] **Adam:** Well, good on you, man. I have worked for a couple of people who are, not great. They just kind of like kick the can indefinitely on doing performance evals and that sort of thing.

[00:08:10] **Tim:** Oh, I've been that guy.

[00:08:11] **Adam:** it's frustrating.

[00:08:12] **Tim:** It, it is, but I figure, you know, it's important. So I need to, you need to do it. So we'll be talking about today.

[00:08:19] **Adam:** yeah, I was gonna say short and sweet,with the triumphs and fails there.

## [00:08:22] Margin For Error

[00:08:22] **Adam:** Our topic for today is margin for error. and basically I kind of came across this in a totally different context. it was a political podcast and I heard somebody using it to discuss, like, sort of as a framework for, you know, how people end up in bad situations.

[00:08:41] **Adam:** and I, it kind of, a gentle bolt of lightning struck me, where I was like, wait a minute, this is a good way to think about, tech decisions or even just decisions in general on a day to day basis.

## [00:08:51] The Framework

[00:08:51] **Adam:** and so here's the, the basic framework of it, or yeah, I like to think of it as like a framework for making decisions, right?

[00:08:57] **Adam:** So, you have an, not innate, innate's not the right word, but like your current state, you know, your position at work, your, your company's position in the market, et cetera, you have a current margin for error, right? So to, to boil it down to the simplest, most extreme case. if you are self employed and you have one customer and you don't have a great relationship with that customer, then you could make one little mistake that winds up with them walking away from your, your relationship.

[00:09:26] **Adam:** Then you have zero customers, you have zero income, you're kind of screwed, right? So that is basically zero margin for error. You have, you have to do everything right, you have to be perfect all the time.

[00:09:36] **Tim:** Hmm.

[00:09:36] **Adam:** so then you can build up from there, right? You, maybe you have multiple clients, that increases your margin for error.

[00:09:41] **Adam:** So if one client walks away... You are not all of a sudden, going hungry because you can't, you don't have any income to feed yourself with. So everything that you do can either increase or decrease your margin for error. And I guess, you know, only, only Siths speak in absolutes, right? so I'm sure that there are some things that we can, can say that, or that we could come up with that don't.

[00:10:06] **Adam:** Either increase or decrease your margin for error, but that's a general rule of thumb. I think most things will either increase or decrease your margin for error. And I think that you can get to a point where you have so much margin for error, you're so comfortable that like, it doesn't even matter, right?

[00:10:21] **Adam:** You, you could skip work for a week and, and everything would be fine. uncomfortably That is so, the, the idea of having a job where I could like not show up for a week, not, not, I'm not talking about taking vacation, I'm talking about just like, eh, I'm not going to show up this week, don't tell anybody, nothing, and like, I still have my job, and the products are doing fine, like, if that were to be the situation that I was in, it would make me uncomfortable because it means that what I'm doing doesn't matter,

[00:10:51] **Tim:** Hmm.

[00:10:52] **Adam:** so, I guess, you know, I was just thinking about it in terms of like, okay, well, should we, This is a framework that you can use to help you make decisions, right?

[00:11:01] **Adam:** Should we build this feature into our application monolith, or should we, you know, branch out and use some distributed cloud service? Well, the way that you can kind of think about this is, using, you know, option A increase or decrease your margin for error, right? Um,and so like, if you, if you continuously make bad decisions, if you, or if you build a house of cards, right, we're, we don't have experience and we're, we're building a chain of like 36 different cloud services, and any one of them could break and we are not super familiar with it, then that's really decreasing your margin for error down to like nothing, right?

[00:11:36] **Adam:** And at any point, any one of those services could not work the way that you expect and then your whole system is hosed, right? So, go. What does that, what does that make you feel? What does that make you think, Tim?

## [00:11:50] Architectural Decisions

[00:11:50] **Tim:** So you were talking about it and I, I, I don't know if I'd call it the margin for error, but in our, so the, our parent company Constellations software, they purposely buy software companies that are, they call them sticky. So that means these are, these are mission critical pieces of software that, that are inside of a company that are extremely hard to replace. You can replace them, but it's going to be painful and it's going to take a long time. And I think when you're in that position, you have a pretty good margin for error. I mean, if they're like, all right, so, you know, some, you know, some software is like, if you want to stop using Adobe Acrobat and use, what's a competitor of

[00:12:34] **Adam:** Whatever, Bob's free PDF reader.

[00:12:36] **Tim:** Yeah, it's different. Like a PDF expert or something, you know, something else. I mean, that, that's a pretty easy swap out. Right. but if you've got a piece of software that is like critical to your business and that if it stops working, you don't make money, that software company that writes that software has a pretty good margin for error, you will live with, with errors workarounds that can get the job done.

[00:13:01] **Tim:** and so, and I do look at that cause like our system, one of our Sister companies that we spun off of, you know, they run an insurance company, right? So if that software doesn't work, no one can, you know, do insurance quotes. No one can, you know, generate the paperwork for it. They can't do claims.

[00:13:18] **Tim:** That's. Extremely important, right? Mine is a little bit less. I mean, you know, we, we've lost competitors have been swapped out before, just the fact of making a payment, you know, a lot of payment companies out there, it is still somewhat painful, so we, you know, we don't have a huge amount of turnover. So I think about margin of error.

[00:13:36] **Tim:** I'm looking at sort of at the, at the company level, what's the margin of error or the, the margin of pain, I think really is kind of the measure there for your, for your software.

[00:13:46] **Adam:** Yeah, for sure. And I mean that, I think that that works both ways. Right. So I like, you know, the way that you framed that, you know, that does give you a certain level of comfort knowing that you can't just be at the drop of a hat replaced, but it also makes it that much harder to replace whoever they're already using when you're trying to sign a new customer.

[00:14:07] **Adam:** So you have to really demonstrate that it's worth all that pain to switch to you.

[00:14:15] **Tim:** And then I think, you know, from a software development perspective. So I was thinking about a margin for error. So I have a process that runs. For several clients every day, it just basically sends out a bunch of text messages, doing reminders,

[00:14:29] **Adam:** Mm hmm. Mm

[00:14:30] **Tim:** payment reminders. And the way I wrote it, it is not like in sort of some sort of message queue.

[00:14:38] **Tim:** So, okay. You know, so if something fails, I have to rerun the whole process again. Right. And it's all, it's, you know, it's idempotent. So it doesn't resend the same message. It knows. Which messages that have already been, been gone out. But it's like, I watched that and it's like, you know, if I get the message, I gotta go rerun it.

[00:14:56] **Tim:** I'm like, you know, there's gotta, gotta be a better way. That, that margin for error in the software itself. There's an error and that if I don't, if, if something isn't done, then that means anything after that error doesn't get sent out because it's a, it's a blocking operation, right? So I'm like, I probably should, refactor this and do some sort of message queuing so that if, you know, if one out of 10, 000 messages fail, just that one needs to go be redone and, you know, have it automatically redo it, not say it, you know, it's at 5, 000 and now 5, 000 other ones are kind of waiting out there and could possibly be an unsent message.

[00:15:33] **Tim:** So I don't know if that kind of falls into what you're talking about for margin for error.

[00:15:37] **Adam:** Yeah, I don't know. I wasn't thinking about that because it was, it was amusing to me that, you talked about, like, you know, this, this process that you have that could die and, and that needs to be manually restarted and it's idempotent and all that. That is basically what I was describing in my triumph that, you know, our, our mail system, I'll just briefly recover it, Early in the process after it figures out who we're sending email to, it writes a bunch of files to S3, and then we have, S3 events that trigger Lambdas to render those emails.

[00:16:06] **Adam:** Right. It, it, it writes the un rendered email body to a file on S three, which triggers a lambda to read that file, render it, and write it back out to a different place once it's rendered. And that's, it's worked well for us for many years now. but where it's starting to become a problem is we. Did not originally envision this system to need to support somebody who's going to write a single email that's going to go to a target audience of say 300, 000 people.

[00:16:33] **Adam:** And so we're basically writing 300, 000 files. And then that, that queues up 300, 000, Lambda function requests and it's massively parallel, but they're not that fast. And eventually those requests timeout and that S3 event doesn't have any sort of configuration for timeout, like how much, how long you're willing to wait for it before it times out, that sort of thing.

[00:16:55] **Adam:** So that's basically what's happening is, you know, we're queuing up 300, 000 and we might get through 200, 000 of them, but then 100, 000 are still sitting there and they time out and the process just stops, right? The, the, it's like those things got dropped on the floor and the apple cart carrying the rest of them continued on down the path, but the rest of them.

[00:17:12] **Adam:** Those 100, 000 that timed out just get sort of forgotten.

[00:17:16] **Tim:** Yeah, that was very similar to what I'm going through with sending SMS messages.

[00:17:20] **Adam:** right, and we have some monitoring in place and that sort of stuff to bring our attention to it and we have tooling around it to make it very easy to restart and only pick up, like you were talking about, you don't want to redo all 300, 000. We're just only going to pick up the 100, 000 that fell on the floor and fix those.

[00:17:36] **Adam:** But the insight that I had today, as you kind of mentioned, was to put it in a message queue, right? To throw those in SQS instead, because you can configure redrives, you can configure timeout, you can configure all these things. and basically our sort of pipeline that we push all of this mail through, would stay functionally identical, right?

[00:17:55] **Adam:** In terms of like what's happening where and, and that sort of thing. We're just talking about sort of rewiring, the communication between part A and part B. That's interesting that, that you had sort of the same thing.

[00:18:08] **Tim:** Are problems dovetailed?

[00:18:11] **Adam:** So, but let's see, so does that, how does that work in with margin for error?

[00:18:17] **Tim:** Well, I think it's an architectural decision, right? I work daily with such a huge number of messages, and it was just a process that, you know, if it failed, it doesn't really matter. I would say it has a low margin for error, right? If it doesn't, if it, if it fails and, and you know, no one's going to really notice that that's a low margin for error.

[00:18:35] **Tim:** I don't really need to put the work in to make the thing bulletproof. That's kind of what I was thinking about. But

[00:18:43] **Adam:** Yeah.

[00:18:44] **Tim:** with this, my margin for error is very low because if people don't get their messages and they don't pay their bill, you're going to have a lot of angry people.

## [00:18:52] Stack Decisions

[00:18:52] **Tim:** So if this is like a decision framework, I was thinking maybe we should think about some of the perhaps non obvious, things that can affect your margin for error, right? So, We talked about choose, what kind of technology you choose and actually this whole thing reminds me of a somewhat old presentation that I saw, which basically says the same thing, or, or maybe it's a narrower set of saying the same thing, but it's, there's a, you can view the presentation online, the, the URL is BoringTechnology.club and the, the presentation is called, Use Boring Technology and he basically describes, like, you have a set number of innovation tokens and once they're spent, they're spent. Then everything else you do has to be boring because, you if you use too many new shiny things, then, then you're increasing the odds that something is going to break and it's going to knock the whole house of cards over. And we're dealing with, we're dealing with, with something like that. So like I've said, or on the show before, a huge part of our stack's written in Scala and it is extremely hard to find Scala engineers. I mean, just there, there's just not a whole lot of them out there. And the ones that are usually in big data for some reason, and they're making a whole lot more money than I can offer them.

[00:20:02] **Tim:** so, you know, that, that's made the margin for error very thin. Fortunately, it's a very extremely stable stack. It runs pretty well. You know, we, we maybe that portion of it, we, we probably deploy once or twice a year to make changes and, and the stuff we're, we're dealing with is not the core architecture.

[00:20:21] **Tim:** It's kind of like the simple little stuff that's pretty easy to change. so I mean that I've been uncomfortable with that margin for error for. Really since we had a actual real Scala dev, I think seven years ago.

[00:20:34] **Adam:** Wow.

[00:20:36] **Tim:** So we are in the process of moving things over to ASP.NET because we do have a lot of internal people that.

[00:20:42] **Tim:** Know ASP.Net, their ASP. net devs are a lot more common and, you know, in our area that that's what they teach that and, it seems that, Python is a pretty popular too in the, in the, in the colleges. That's what a lot of people know coming out either C, C sharp or Python coming out of school. So that, that's, you know, I'm trying to increase our margin for error there that if, you know, if something, you know, if we want to.

[00:21:06] **Tim:** Do something transformative to the stack or, you know, there's some issue that comes up, we're not living on the edge.

[00:21:13] **Adam:** Yeah, for sure. I mean, that's, that's pretty much directly what I was driving at, or at least adjacent. so yeah, you're saying your margin for error is reduced because you don't have a skilled person on staff to be able to work with that part of your product. And so if that part for some, you know, if a, what do they call it?

[00:21:31] **Adam:** bit flipping from cosmic rays. There, there's a name for it. I don't know. You know what I'm talking about? Like if something just totally, you know, an act of God sort of thing, like messes up your software and it brings that part of your stack down, like how hosed are you going to be?

[00:21:46] **Tim:** I just worry like, you know, some chain, cause some of this is hosted AWS as, as microservices and it's like, AWS makes a big change. Like, okay, we're, we're deprecating this technology. or they force you to upgrade to a version you're really not sure is compatible of something. It's like, yeah, I don't know how this is going to work.

[00:22:05] **Tim:** I mean, I have people I can call. We have contractors and former employees that will, that will, You know, contracted to do it, but it's like, still I'm uncomfortable with that

## [00:22:13] Life Decisions

[00:22:13] **Adam:** Oh yeah, for sure. That would terrify me. And along the same lines, you know, we talked about like having only one customer as a source of income. the other side of that same coin is, you know, if you're working by yourself and you get sick or you need to have surgery or you get, you know, it's not going to necessarily matter so much if you win the lotto.

[00:22:31] **Adam:** So let's take the grim side of the coin here. If you do get hit by a car and you're in the hospital for three weeks, like you're going to, not only are you going to have hospital bills, but now you don't have income from those three weeks, right? so, having multiple people on staff and increasing the size of your team increases your margin for error.

[00:22:45] **Adam:** Mm hmm.

[00:22:47] **Tim:** and you know, hopefully people that are in that situation, they're, you know, they're putting up a pretty good nest egg for those cases where, you know, either an in between gigs or, you know, they lose a customer or whatever. But, and it's kind of like what, you know, you were talking about this, this whole idea came from, like, that's sort of the problem with people in poverty.

[00:23:05] **Tim:** You know, when something big changes in their life, you know, they're living hand to mouth, paycheck to paycheck. With no savings, no, no social network to, you know, if they lost their job or, you know, something tragic happened to them that they didn't have any, safety net. And so I think we're sort of talking the same thing when it comes to like, you know, people in tech and. Dealing with, dealing with tech is, you know, hopefully you're doing whatever you can to make that margin for error more tolerable when bad things happen. But, you know, I don't know.

[00:23:40] **Adam:** Yeah, it's,

[00:23:40] **Tim:** I don't know. I, I, I've never been a software contractor and I just really marvel at people that have done it for years and they're successful at it because it's like the idea of, all right, I'm done with, I'm done with, you know, this project.

[00:23:54] **Tim:** I got to find another one and you don't have anything. It's like,

[00:23:57] **Adam:** Yeah, like when we had Nolan on and he was talking about, you know,

[00:24:00] **Tim:** sure.

[00:24:00] **Adam:** doing all that. So we've,

[00:24:02] **Tim:** he obviously have strategies, you know, that he does and does very well and has done well for years in that. So,

[00:24:08] **Adam:** Yeah, for sure. So, we've kind of mentioned, or we've been beating around the bush about where I got this idea for Margin, Margin for Error. So, why don't I just come out and say it? So, the, the podcast that, I'm kind of borrowing this idea from, right, it inspired me, was, the name of the podcast is The Problem with Jon Stewart.

[00:24:27] **Adam:** and the episode is Rethinking Crime and Punishment with San Francisco's Mayor. And so, the, the conversation they were having was about how... you know, people live with a margin for error. this was a very small part of the conversation, but it just, it struck a chord with me. And so you have a innate or, or, or a, a position or a margin for error in the way that your life is going.

[00:24:45] **Adam:** And so, you know, if you lose your job, then your margin for error goes down. Or if you're, you know, if you have mental health disorder, your margin for error goes down, you know, that sort of thing. And eventually you're, you're basically trying to like, you know, you're, you're walking from point A to point B in life and your margin for error is how wide is the path in front of you, right?

[00:25:03] **Adam:** And, and if you take a misstep, but your path is 30 feet wide, it doesn't matter that much. But if you, You know, if your margin for error shrinks and shrinks until you're walking a tightrope, and then you lose your balance, then you're screwed, right? You might end up homeless, addicted to drugs, in jail, you know, et cetera, et cetera, et cetera.

[00:25:18] **Adam:** So, that's where that came from. Anyway, well that was a, on a, on a On a bright note,

[00:25:25] **Tim:** pride her nose.

## [00:25:26] &quot;Nobody Chooses Windows&quot;

[00:25:26] **Adam:** So another thing that I wanted to mention too, is that, you know, we, the hosts of the podcast, obviously have limited visibility. we, to some extent, live in a bubble. I went out and had lunch with a friend today who happens to be a listener and a, and a, patron of the show. And, he called me up on our last episode when I was talking about how, Nobody chooses Windows.

[00:25:49] **Adam:** Nobody likes Windows. Now, I will. He was like, you know, what about NET developers and that sort of thing. And I will say, he's right. But I think that, you know, we're basically, at that point, we're probing the blind spots in my personal perspective. Right? And I acknowledge that they're there. But, I think that that's important to keep in mind as we're talking about these

[00:26:11] **Tim:** know what he's talking about, but I thought that developers use Mac.

[00:26:14] **Adam:** Do they? Okay. Well, hey,

[00:26:17] **Tim:** just fine.

[00:26:20] **Adam:** well, there you heard it here. yeah. And, and also he said that, he was almost certain that Reagan fired all of those air traffic controllers.

[00:26:28] **Tim:** Oh, really?

[00:26:28] **Adam:** Yeah. So, yeah, you know, we, we don't always get everything right, but, we do our

[00:26:33] **Tim:** We rarely do, honestly. It's a point of pride.

[00:26:37] **Adam:** We have a, we have a very wide margin for error

[00:26:39] **Tim:** We, we do, our, our, our listeners give us a very wide margin for error. Like, Tim doesn't know what he's talking about on a good day. We'll just let it slide.

[00:26:47] **Adam:** All right, well then, I think we're gonna, we're gonna call it a early show there. I'm not feeling great. I just got my COVID booster and my flu shot, and I'm starting to feel groggy. It's starting to hit me. I feel like I got hit by a train here.

[00:26:59] **Tim:** my margin for error is thinning. That's how you know it's working.

[00:27:03] **Adam:** Yeah, so, we're gonna wrap it up a little early here. I, I, I don't know what we're gonna do in the after show, but we'll, we'll figure something out. And if you, man, I'm, I'm ahead of myself. You can tell it's the COVID brain. It's the COVID vaccine brain kicking in.

[00:27:15] **Adam:** So, let me try and do this the right way.

## [00:27:17] Patreon

[00:27:17] **Adam:** this episode of Working Code is brought to you by mRNA vaccines, save lives and fog brains. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:27:31] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock. thank you, as always, but you know, we're talking about margin for error. Thank you guys for helping keep our margin for error.

[00:27:46] **Adam:** Sustainable. if you'd like to help us out and keep our margin for error sustainable, then you can go to patreon.com/workingcodepod.

## [00:27:54] Thanks For Listening!

[00:27:54] **Adam:** that's going to do it for us this week. We'll catch you next week. And until then,

[00:27:58] **Tim:** Remember, by a huge margin of error, Your Heart Matters. It's especially any of our listeners in Israel.

[00:28:05] **Adam:** oh my goodness.

[00:28:06] **Tim:** We're hoping the best for you guys.
