---
title: "038: Holding Developers Accountable"
description: 'Recently on Facebook, Hal Helms —highly respected author, speaker, and computer programmer— shared some of his views on the use of "Sprints" to drive engineering work on a product team. In short, he despises the idea of asking engineers to commit to achieving a goal within an estimated time frame. He likens this to asking prisons to build their own gallows. Everyone is terrible at estimating everything. So when companies start to use each "estimate" as a "contract" with which to punish engineers for under-delivering after over-promising, all it does is set the entire team up for a toxic cycle of disappointment.'
date: 2021-09-01
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/038-holding-developers-accountable/id1544142288?i=1000533977924"></iframe>

Recently on Facebook, [Hal Helms][hal-helms] —highly respected author, speaker, and computer programmer— shared some of his views on the use of "Sprints" to drive engineering work on a product team. In short, he despises the idea of asking engineers to **commit** to achieving a goal within an **estimated time frame**. He likens this to asking prisons to build their own gallows. _Everyone_ is terrible at estimating _everything_. So when companies start to use each "estimate" as a "contract" with which to punish engineers for under-delivering after over-promising, all it does is set the entire team up for a toxic cycle of disappointment.

This is the full text of Hal's post:

> "We have to be able to hold developers accountable."
>
> A friend and I were discussing the idea of "sprints" — a system where developers commit to achieving certain results within a specified time frame — usually two weeks.
>
> I hate and detest sprints. I despise asking developers to "commit" to achieving a goal within an estimated time frame. My friend disagrees. He's wrong.
>
> The first flaw in this system is what Nobel Prize-winning psychologist Daniel Kahneman termed "The Estimation Fallacy". When people are asked how long a goal will take to achieve, they predictably and chronically underestimate the time. And this is true even when they have considerable experience in being wrong in their previous estimates.
>
> A good estimate is one that's over half the time and under half the time. So, estimates are not really what developers are asked for. They're asked to commit to a date after which they can be held to blame if they have not achieved the goal. Every such "estimate" holds an implied threat.
> '
> Asking developers to provide their own deadlines is a bit too much like asking prisoners to build their own gallows.
>
> But let's say you have a taste for a bit of sadistic irony. It's still not a good idea — not if your goal is to actually increase the throughput of the system.
>
> Developers are not, by lot, stupid. So while inexperienced developers may believe their own deadlines are realistic, those of us with more road behind us are not so quick to be led to slaughter.
>
> If the boss demands a deadline that a more experienced developer thinks is probably five or six days, the deadline become two weeks — three if they can stretch it.
>
> And when they actually complete the work ahead of time — well, would you be quick to voluntarily re-enter the arena only to place yourself at risk again any earlier than you have to?
>
> It gets worse: you may know one part of the sprint goal while I know another, of which you're clueless. Can I help you? Sorry, I have my own deadline. How is this good for the developer, much less the organization?
>
> And so I circle back to my conversation with my friend. "We have to be able to hold developers accountable." One needs to hold people accountable for things they _don't_ want to do. Developers, on the other hand, _like_ to develop. Most of the ones I know do it in their spare time as well as their work hours.
>
> If I want you to do something you already want to do, what is the sense behind "holding you accountable"?
>
> Eat this ice cream — and I'll need to see status reports of how much you've eaten, accompanied by proof that you're actually eating it (to make sure you don't just dispose of the ice cream).
>
> I recently had a long discussion with a CEO who asked for what might be termed my "philosophy of management" when it comes to managing developers.
>
> I told him it was really quite simple: give developers what they need and protect them from upper management.
>
> CEOs don't produce software. CTOs don't. Product Managers don't. When upper management tries tricks like sprints to force their developers into deadlines — as if such a thing could be done by fiat — they effectively tell developers: we neither trust nor respect you.
>
> I'm not sure what genius management consultant had the flash of insight that disempowering workers and placing obstacles in their way was a surefire way to get the most out of them.

Inspired by Hal's post, we wanted to talk about how we view—and experience—developer motivation; how we employ Sprints at our respective offices; and, what we think an organization should be doing to help drive a project to completion. There's the idealized approach that Hal puts forward:

> Give developers what they need and protect them from upper management.

_Amen!_ But, there's also the practicalities of running a business, building a road-map, organizing marketing campaigns, and keeping users interested and excited in your product. None of it is easy. But you can be sure that _treating people with professional respect_ is certainly one of the necessary ingredients.

## Notes &amp; Links

- [Daniel Kahneman: The Planning Fallacy](https://en.wikipedia.org/wiki/Planning_fallacy)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[hal-helms]: https://www.linkedin.com/in/hal-helms-613a992/
[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/038-holding-developers-accountable.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** the way I was thinking about it when we were having this discussion earlier was just that, I agree that the accountability thing is wrong.

[00:00:05] **Carol:** Like in my organization, yes, we set deadlines and goals and stuff, but like, if you miss the deadline by a day, then you were like 99% there. You're, I'm not going to punish you for getting 99% of your goal done. And what is the punishment?

[00:00:18] **Adam:** I mean, flogging of course,

[00:00:20] **Carol:** Yeah, you get to wear the hat

## [00:00:42] Intro

[00:00:42] **Adam:** okay. It is show number 38 and on today's show, we're going to be discussing developer motivation and deadlines. Tim, thank you for writing that in there. Cause I didn't even remember that we hadn't discussed what the official name of the topic was going to be until I got to that point in what I say.

[00:00:57] **Adam:** Um,

[00:00:57] **Tim:** there you go. I'm here to help.

[00:00:59] **Carol:** Teamwork.

[00:01:00] **Adam:** so that's what we're going to talk about today. but I guess as usual, we'll start with our triumphs and fails and Ben, it's your turn to go first. So what do you got.

## [00:01:07] Ben's Triumph

[00:01:07] **Ben:** I'm going to go as a triumph. I, built a MVP, a minimum viable product at work. I've always felt like we underserve the administrative portion of an organization and we focus a lot on designers and managers. but there's a, there's an echelon of people who come in and their entire job is just to manage other people.

[00:01:28] **Ben:** And I feel like we've never really had. Great insight into how they might want to use the product. so over the last two weeks, I started to build out a more robust user management feature. but I didn't want to, I didn't want to assume everyone would use it. So I wanted to build just enough to make it sort of a read only, but you could click through to things that were more interactive, put some analytics on it, and now I'm just seeing if anybody clicks into it.

[00:01:53] **Ben:** And then I'll use that as a way to determine how much additional effort I want to put into fleshing out the more interactive features, but I don't know. I'm just a, what.

[00:02:05] **Adam:** I'm over here laughing because I, if I was going to develop this sort of feature, I think it would be, my first stop would be like to go talk to some of the users and then it occurred to me like Ben, doesn't like to people.

[00:02:16] **Carol:** Yeah.

[00:02:17] **Ben:** Well, I'm also in a weird position where I don't want to make a lot of noise. Cause the more noise I make, the more people have to get involved. Uh, and I, and then I find that maybe this is also like on topic a little bit like that sometimes just slows things down too much. so I kinda just like to put stuff out there quietly and see what happens and you either can see the analytics and you see people using it, or you can start to get support tickets where people are using it, but it's not fulfilling what they need and they complain and that's sort of like some degree of actual human feedback, but,

[00:02:47] **Tim:** It's here. The school of build it and they will come if it's good. And if it's not, you might need to

[00:02:51] **Ben:** yeah. and the idea behind them minimum viable product is that if I build it and they don't come in yet, Then it wasn't a huge amount of effort, so it wasn't a ton of time wasted.

[00:03:01] **Adam:** Well, I think that's going to dovetail nicely into the topic today, especially from this kind of, we had a brief discussion earlier today in our, podcast Discord about this topic, and that's why we're recording it tonight. So, some of the points I brought up in that discussion, I think are going to dovetail nicely with what you were just saying, Ben MVPs

[00:03:16] **Ben:** Nice, nice.

[00:03:18] **Carol:** It's going to be great because I didn't read everything. So

[00:03:22] **Adam:** and Carol, welcome back by the way you were out last week. And we didn't even mention it. I felt like a, a horse's patootie again, just not acknowledging

[00:03:29] **Carol:** are terrible. E

[00:03:30] **Tim:** we did miss you, but Brian was

[00:03:32] **Ben:** was, he was pretty great.

[00:03:33] **Carol:** it seemed pretty clear after you recorded that you didn't miss me that much. I had to chime in and be like, I am coming back. You can not keep him.

[00:03:41] **Ben:** Anyway, Tim, what do you got going on this?

## [00:03:43] Tim's Triumph

[00:03:43] **Tim:** the triumph. So I've been doing, you know, built lots of different products in the past couple of years, and now kind of, we really are getting our sales and marketing engine going. And I'm not a sales person. I'm not a marketing person, even though I have done those roles, it's not my, it's not my, ballywick, but I do like to help out with the technical demos.

[00:04:07] **Tim:** And I've sat in on a lot of technical demos and the worst ones are where people just show up and throw up. and they don't really, and they start talking about stuff you really don't care about. so I th the triumph is that, just doing it. I'm going to use a sales marketing term here, your due diligence beforehand to find out what is it they really want to see, what problem they're trying to solve.

[00:04:28] **Tim:** what are their concerns, figuring that out rather than just cranking out the same old, here's a bunch of screens and here's what it's doing without really understanding what it is they need. So we've been doing that recently and it's just, it's been really successful, in getting further conversations and further down the sales pipeline, because the worst thing that can happen on a technical demo is you show everything and people don't have any questions.

[00:04:54] **Tim:** That means they just checked out and they're like, yeah, this is not for us.

[00:04:57] **Carol:** You completely lost them.

[00:04:58] **Tim:** Yeah, you completely, it they're like what time's lunch. Right? So it's when they have a bunch of questions and they're like, yeah, that's really cool. or they start giving you ideas. Have you thought about this, adding this feature?

[00:05:08] **Tim:** Like, okay. Yeah, you're right. No, I haven't thought of that. That's really tough. Talk to me. what would that mean if we added this to the product and they start talking about that. So we've had a lot of those recently and it's been, yeah, it's been great. So I've just, I'm happy to see sort of the traction that comes when you, start getting feedback on your product and you start being able to see the value of it.

[00:05:30] **Tim:** And then also the feedback that it helps you continuously improve because building, and I know Ben likes to build in a vacuum sometimes and push it out there. But,you know, I got, hear, I got to hear some feedback, right? I'm lazy. If you don't tell me what to do, I'm not going to do it. I'm just going to, so yeah, that's me.

[00:05:47] **Carol:** No. I love that. I love when I'm doing technical demos. Like it's the best thing for me because I love that interaction. And I love, it's kind of almost like nerve wracking, like, oh my God, what are they going to think about it? Like, I'm going to be judged so harshly and I'm so nervous. And then at the end of it, I'm like, let's go have ice cream.

[00:06:02] **Carol:** Cause I'm so happy. I don't care if he just told me I failed or it was great either way. It's just like this huge success, no matter how the outcome is.

[00:06:09] **Tim:** Yeah, I get, so I get so nervous on those kinds of things. I just, I will not schedule anything in like the hour before, and I would just kind of I'll pace around the room, like for an hour and just and then I'm done with it. I'm like, why was I so nervous? It went great. So.

[00:06:24] **Carol:** because you have that bond to it. It's like, you're really connected with what you've been developing and doing.

[00:06:29] **Tim:** Yeah. And in particularly if it's like, they're like looking at another competitor in and people are so cagey about telling you what other people, typically you have to sign NDAs and they're not going to say, well, so-and-so does X, X, and X and X. Why don't you do that? but sometimes they actually do, but you know, like, you're you feel like you're being compared to someone else and you don't know what, you're like stripping naked and you have no idea what the other guy looks like. So, yeah.

[00:06:55] **Ben:** I think targeted customers is awesome. And I know that some, I. Quietly, but that's almost more of a political motivation than it is a workflow motivation. I, sometimes I go to my CFTR customer facing team and I just want to be put in front of a customer and they'd be like, well, what do you want to talk about?

[00:07:13] **Ben:** I was like, I don't care anything. I don't care if they're happy or if they're angry or they want to yell about something that product like, just let them start the conversation and see where it goes. And I will, I love to be in a call with a customer and just ask open-ended questions. Like if I think I was in one call just recently, and I said, like, if you were running our product team and you could do one thing, what would it do just to like, see the thing that they might not think to ask about, but it's like the thing that bothers them every day,

[00:07:42] **Adam:** Yeah.

[00:07:43] **Carol:** Oh yeah.

[00:07:43] **Tim:** have a similar question. So I'm like, look, you've seen what we've done here, or if it's an existing customer, you've been working for awhile. If you had a magic wand, what would be one thing you'd change. Right. And see what they say that's very enlightening to give them that.

[00:07:58] **Tim:** and a lot of times, honestly, it's like, it's not as pie in the sky, kind of visionary. Occasionally get those kinds of people. But mostly it's like some tiny little thing that you're like, oh, that's an issue.

[00:08:08] **Carol:** That's so simple to fix. Yeah.

[00:08:10] **Tim:** me a couple hours. we'll be done. So

[00:08:13] **Ben:** Yeah.

[00:08:14] **Carol:** Love it.

[00:08:14] **Tim:** So Carol, what you got going on? Welcome back.

## [00:08:16] Carol's Failure

[00:08:16] **Carol:** Yeah. Welcome back. Right. So, I have a salary. I'm on Zen desk this week, which is what we call when you're on call. Yours is in master and Megan, this Sox, I am really struggling because you know, you guys all know I started this job in October, was just getting the hang of things, learning the system.

[00:08:37] **Carol:** And then, around April, I completely went out of my everyday work, went out of the terminology, went out of everything related to like the weeds of my system and moved over to the GCP and AWS stuff. And, I had to pick up Zendesk and I'm looking at all these actors. I'm like, I remember nothing.

[00:08:57] **Carol:** I have everything I learned is. And so I'm like, what's an MIT what's PRP, what's FTD. Like that has to be like a flower delivery service. Like this can't be something I think in our system I'm like, how was this failing? So it's just then when, and my first rotation is in desk. I got one Zendesk. And everyone was like, oh my goodness, nobody ever only gets one.

[00:09:19] **Carol:** So of course, our business analyst was like, you remember that time? You only have one. Sorry. I was like, yeah, everything you tell me now is going to be not prod support. Sorry,

[00:09:30] **Carol:** So, yeah, so that's me. That's what I have going on. They'll a little bit, cause index sucks.

[00:09:35] **Tim:** I don't know the Zinnia is, I mean, it sounds like they, they kind of throw you in there at the beginning and then took you out. And now it's like, if you don't know those things, if that's not your ballywick,

[00:09:43] **Carol:** My ballywick my new word. My triumph, when the AA.

[00:09:48] **Tim:** then yeah, maybe they shouldn't be putting you on there with, without.

[00:09:52] **Carol:** Well, they like, I do have, I will say it probably a good win to this is my team is absolutely amazing. So I have been putting in our slack channel, like someone telling me what the FTD delivery failure means for this PRC thing that's going on. And like three people chime in. They're like, oh, here it is.

[00:10:08] **Carol:** Here's how you rerun it. Here's what's going on with it. I was like, oh, okay. I

[00:10:12] **Adam:** Sounds like you should be putting together like a on-call, cheat sheet sort of thing. Like with acronyms and jobs, three run, that's a situation and stuff

[00:10:21] **Tim:** Hmm.

[00:10:22] **Carol:** what I've done so far, she's opened up core issue so that the tickets don't come up

[00:10:26] **Carol:** again, like, Hey, go fix the problem. We don't want the core issue to happening. And exhibit repeats twice. There's a problem. And we've exited. So anyways. Yeah. Nice. Nice. Yeah. Cool. What about you, Adam?

## [00:10:36] Adam's Triumph

[00:10:36] **Adam:** I have a triumph. and I think it kind of fits nicely with our discussion topic for today. So, yesterday I, we have a morning meeting where we go through our plans for the day and talk about anything that's big, that needs discussion. and I talked to my team into not writing a feature yet. so basically we're developing this big feature, for some stuff.

[00:10:56] **Adam:** I think it might've discussed some of it in my time from last week, but, the, one of the user administration portions of that feature, like sort of a feature within itself is,it's tough to even discuss because it's so complex, right? There's a lot of potential different paths we could take.

[00:11:12] **Adam:** There's at least three, potential. User experience approaches that I could see us taking, and with the four of us discussing it, none of us could really clearly say for sure that any one of them was the right way to go. And so what I ended up doing was suggesting that we build none of them to start let's launch without any of them.

[00:11:35] **Adam:** And just tell the users, like, if you want to change this data, put in a ticket. And the reason for this not having administration for this is because we want to better understand how you want to use the feature before we build the interface so that you can do it yourself. so that we don't waste time and effort and money because time is money building the wrong thing, which is something we've done far too many times.

[00:11:55] **Adam:** So it was, I was like, I feel like my insight, my, I feel like my triumph here is that I've finally had an insight. I should have had several times in the past. Right? Like I, I recognized that we were on the precipice of doing the wrong thing again, and I stopped us from doing it. So I'm happy with that.

[00:12:11] **Carol:** that's really awesome and really hard to do because I just want to go build it all out. Knowing if they'll ever even use it. So it's hard to take that step back and go, well, let's just see how they want to interact with it before we build a front for them. So

[00:12:26] **Adam:** Thank you. Yeah. And like I said, we've done it in the past. either with this particular thing, I could see us building all three different variations as like separate interfaces and maybe only one of the three gets used or even worse, like building one sort of giant complex interface that can sort support every possible use case.

[00:12:45] **Adam:** And then it's a monster and everybody hates it because,

[00:12:48] **Carol:** Good Lux. And then actually supporting that if you do want to change it. Yeah.

[00:12:52] **Adam:** So, yeah, I'm happy.

[00:12:55] **Ben:** I remember listening to an interview one time. I can't remember where, and this guy was talking about how he was building. And one of the techniques that he used, which I've been dying to use is he'll actually put calls to action in his application. And when you go to click the call to actions, it'll pop up modal window that says something along the lines of like, we haven't built this feature yet, but here's an input where you can tell us why you might want to do this.

[00:13:20] **Ben:** And so he puts an ingress to something and then just sees if anybody clicks on it. And then he uses that as evidence as to whether or not he actually wants to build that feature.

[00:13:28] **Adam:** that's pretty smart. I like

[00:13:29] **Ben:** It's really interesting.

[00:13:31] **Tim:** Yep. And I've heard of people who like have an idea, like for a service. And so they build this kind of marketing ish kind of page that basically touts all the pros and cons of why you would want to use this kind of service and you sign up for it. And it looks like it's real, but you get to it. And they're like, this, sign up to find out further information when we start to build this.

[00:13:52] **Tim:** And so, cause sometimes you have this idea like, oh, this would be perfect. And you start putting all this blood, sweat and tears into it and then you release it and everybody's like, no, that's not a problem that I need to solve. but if you put it out there and you start getting people start subscribing to find out when it's going to be released, you're like, okay, there's actually some traction there.

[00:14:09] **Tim:** And that's, I mean, that's even prior to an MVP, that's like, like appetite research to find out here's the thing. Is there even appetite for this right now? Because if there's not, what's the point.

[00:14:22] **Adam:** like one foot in the entrepreneurial space for like side projects, like with my book and other stuff. And one of the things that I see, written about and spoken about frequently, there is the idea of using sales as market validation. Right? So before you make the product, before you write the book, sell it, like literally take people's money and, worst case scenario, it doesn't work out.

[00:14:43] **Adam:** You decide, oh, I didn't get enough sales. I'm not going to do it. You just refund their money.

[00:14:47] **Ben:** Okay.

[00:14:48] **Tim:** It's kinda like a Kickstarter, right? I mean, you say here's our idea. We want to build this, if you're

[00:14:52] **Adam:** right? Yeah. Cause there's

[00:14:55] **Adam:** yeah,

[00:14:56] **Tim:** we build it, you get it early for cheaper or get some other stuff. So yeah,you're gauging the market value of what your idea is. And I

[00:15:05] **Adam:** because probably only 10 to 20% of people who are willing to give you their email address. Cause they're kind of interested would actually spend the money.

[00:15:12] **Carol:** exactly. You're not getting all of it.

[00:15:14] **Ben:** It's interesting. Because I think is a perfect example of where there's a strong divide between people who build digital products and people who are used to building and running physical businesses, where if you're building a digital system, you freak out at the idea that there's going to be inconsistency.

[00:15:33] **Ben:** Like, oh, what if we sell a product? And then it turns out that, that product's not actually on a shelf somewhere. And then you talk to people who run businesses and they're like, yeah, that's a fact of life. Like that just happens all the time. What happens if you go to sell something off the shelf and it breaks while you're packaging it, like, that's the same thing.

[00:15:49] **Ben:** And, there's all these like little nuggets of wisdom where you realize that. Life is just not as consistent as we like to think it is in a digital world. And when you can lean into that instead of fighting it, I don't know, things get a lot more interest, not to say that I'm there, but I love the idea.

[00:16:06] **Tim:** Yeah. Okay.

[00:16:08] **Carol:** segue into what we're going to talk about.

[00:16:11] **Carol:** Yeah,

[00:16:11] **Carol:** I think all of this is kind of leading into good

## [00:16:13] Developer Deadline Accountability

[00:16:13] **Adam:** So, Tim, you found the, the original post that inspired all of this. Do you want to maybe read that.

[00:16:22] **Tim:** read the whole thing. It's kind of like,it's kind of lengthy. so I will say, so how Helms, he's a guy that, that many of us know he has been in the ColdFusion community, but he's an educator and, you know, they've been around a long time and, I follow him on Facebook and he posted this to Facebook talking about, how that we need to hold developers accountable and sort of his counter-argument to the idea of sprints.

[00:16:46] **Tim:** Now, a lot of us use sprints. But basically what he's saying. He says he hates sprints because he despises asking developers to commit, to achieving a goal within estimated timeframe. And I mean, I sort of see his point because he quotes, a Nobel prize, winning psychologist, Daniel con Neiman. I don't know how to say that.

[00:17:12] **Tim:** Conaman about the estimation fallacy and that is so true. I mean, the few times in my career where I actually have been in a place where I've had to give like sprint estimates, I always felt like I was lying every single time, or I was trying to figure out what the answer they wanted to hear was. And , people just don't really know in, in software and probably even in other areas too, but we're concerned about software is how to estimate how long something's going to take. And that's a problem because you have a customer who wants to know when somebody's going to be done, but you have, an unknown level of effort. And of course, he's, he talks about how he's having this, kind of argument with his friend who, is like a project manager kind of person who says that, you got to hold people accountable, but I agree with them that developers, they're not stupid.

[00:18:04] **Tim:** And they don't really need motivation. they sort of having developers, anyone who's worth their salt. And most of them, want to build something good. They have motivation. They want to see something done and complete and done. Right. But they need to be given the time for it. And the time is unknown, right?

[00:18:22] **Tim:** So you think, you know how long it's going to take and then you get into it and it's a lot longer, but his main argument is. These idea of sprints of like, how much can you get done within a two week sprint or whatever your sprint cycle is really just a bludgeoning tool to beat down on developers when they don't meet that.

[00:18:42] **Tim:** And that is so counterproductive because they didn't lie to you. They just didn't, they didn't know. And so, you know, you guys can read the, I posted in our Discord channel here as well, but,

[00:18:54] **Adam:** we'll definitely put the full text of his post in the show notes.

[00:18:58] **Tim:** but I think it's a,

[00:18:59] **Carol:** become a Patreon and you can get access just saying.

[00:19:03] **Tim:** So, I mean, I agree with him. I think that the idea of sprints as a form of accountability is bad. I do think at some level you have to give people an idea of all right, what are we going to get done in these two weeks? Right. I don't, when I've worked on sprints, it's always, yeah.

[00:19:22] **Tim:** I've never been in a sprint where they're like, if you don't get this done, there's repercussions. It's like, all right, we didn't get this done. Why didn't we get this done? All right. Well, we just move it to the next sprint. Right. but I mean, so where is the balance of delivering something on time, whatever that means, versus, what do you have to do to motivate developers versus,how does management do their job while developers do their job at the optimal level on both sides?

[00:19:48] **Adam:** very multifaceted. Right. There's a lot of different angles to look at this by there's the accountability, there's motivation, there's, goals and time management estimation. There's a lot of things to this.

[00:20:04] **Adam:** AndI think I agree with a lot of what howl is saying here, but, I, so I guess my, my, purview, no,

[00:20:11] **Carol:** Use that word again. Go ahead,

[00:20:12] **Tim:** Your,

[00:20:13] **Adam:** no, my, the way I was thinking about it when we were having this discussion earlier was just that, I agree that the accountability thing is wrong.

[00:20:19] **Carol:** Like in my organization, yes, we set deadlines and goals and stuff, but like, if you miss the deadline by a day, then you were like 99% there. You're, I'm not going to punish you for getting 99% of your goal done. And what is the punishment?

[00:20:32] **Adam:** I mean, flogging of course,

[00:20:34] **Carol:** Yeah, you get to wear the hat. I don't know. Like I've never been

[00:20:38] **Adam:** Yeah. I mean,

[00:20:39] **Carol:** There may be financial consequences to the company, but as a developer, I've personally never been like your punish

[00:20:45] **Adam:** I

[00:20:46] **Carol:** for not delivering.

[00:20:47] **Adam:** so

[00:20:48] **Tim:** Hm.

[00:20:49] **Adam:** we have this, this straw man that we can take down here. So, the person who is on the other side of this argument from hell, right. Who's saying we need to hold developers accountable. I think that what they're saying is like, if your developers, consistently don't meet their deadlines and their goals from their sprints, then that might be grounds for a demotion or termination or whatever.

[00:21:09] **Adam:** Right. Like some sort of

[00:21:12] **Carol:** See, and I think if you constantly have your developers not meeting their goals, then when they tell you a day, you go out a week to it. Because as a manager, they're not going to get it done in a day. So rather than saying, oh, you're trying to give me a good estimate because you think you can, I realistically know that you and this team can't do that.

[00:21:31] **Carol:** So I'm going to add a week to

[00:21:32] **Carol:** what you say. And ifif it's early, guess what? Everyone's really happy and you got it done in a day.

[00:21:39] **Tim:** No, no,

[00:21:39] **Carol:** a week, we're great.

[00:21:41] **Tim:** no. He's happy if you're, if you're done early they're like, why did you sandbag? Right? why did you

[00:21:46] **Carol:** when people tell me that when people, like, why are you sandbagging my quotes? You mean the sandbag, this it needs, I need a week. And now, you need that a week to whatever I just told you. So go have your two weeks now I get it. I get annoyed with this estimating thing. I get,

[00:22:00] **Adam:** I was thinking.

[00:22:01] **Carol:** about this too.

[00:22:02] **Carol:** Okay.

[00:22:02] **Carol:** Yeah.

[00:22:03] **Adam:** we're developers, we're not estimator. Right? Like we have a sense that the there's so many hidden corners in a project. Right? So like when somebody asks me to write a feature, my brain instantly is like writing code in my head. Right. Like, I'm seeing the path that I'm going to be implementing like instantly, but what my brain doesn't show me is, oh, you have to write the tests and you have to write documentation and you have to,you, forgot about, reports and you forgot about, the API implications of all this and,

[00:22:31] **Carol:** Maybe it's an after hours post there's time to support it. There's lots of things that go into development. That's not just riding your

[00:22:38] **Adam:** And those are the things that we're not thinking of when we make these bad estimates. I think.

[00:22:44] **Tim:** I think so he kind of gets to his conclusion at the end here. And I completely agree with him. He says, I told him, he talks about what should be his philosophy of management when it comes to managing developers. He says, I told him it was really quite simple. Give developers what they need and protect them from upper management.

[00:23:03] **Tim:** Amen. Yes, for sure.

[00:23:04] **Carol:** preach

[00:23:05] **Tim:** preachthat's that's me throwing that in there. CEOs don't produce software. Let me repeat that. CEOs don't produce software CTOs don't product managers. Don't when upper management tries tricks like sprints to force the developers into deadlines as if such a thing could be done by Fiat.

[00:23:25] **Tim:** They effectively tell their developers. We neither trust nor respect.

[00:23:29] **Adam:** Yeah, I think yes, when you're trying to be super rigid about it. And oh, I thought of this earlier and I wanted to fit it in before we get too far away from the topic. Another potential, consequence of not of like consistently not meeting your deadlines would be like, sort of bump you down the list for promotions.

[00:23:46] **Adam:** Right. Maybe not a demotion or being fired, but like, Hey, you need to get better at this

[00:23:50] **Adam:** before

[00:23:50] **Tim:** a write up.

[00:23:52] **Adam:** Yeah.

[00:23:54] **Carol:** I'm sorry if you've write me up for being late on the delivery, I'm pretty much going to quit anyway.

[00:24:00] **Tim:** Yeah.

[00:24:00] **Carol:** Like, I'm going to take the time that it needs to do it. Right. But the difference is that I'm going to communicate with you along the way. So if I told you it was going to take a day and I'm four hours into it, and I'm nowhere close, you're going to know at that four hour mark, that we underestimated this, that we can not deliver this.

[00:24:17] **Carol:** So do you want me to keep working on it or do you want to go to the customer and say, Hey, it's going to be late. Do you want to prioritize something else? Like you have to be open about what's going on. I can understand, if I'm not communicating that you're upset by it not being delivered on time, but if I'm telling you, we're not going to be able to do it and to it, there should be no punishment on my side.

[00:24:36] **Carol:** And if so, I'll go somewhere else. I'm hardcore about that.

[00:24:41] **Tim:** What drives me nuts is so you have project managers or, people in management who aren't writing a line of code whatsoever probably have never written a line of code. And they come to the developers and say, all right, so this needs to be done by X date. And you're like, well, where did you get that number?

[00:24:58] **Tim:** how did you arrive at that number? I mean, did you just pull that out of the air? Well, the customer needs it by then. Great.

[00:25:06] **Carol:** You shouldn't have told them we could do it.

[00:25:07] **Tim:** Right.

[00:25:08] **Carol:** not my fault.

[00:25:09] **Tim:** You do your job. You manage customer expectations. That is your job. As a project manager, you manage the project and manage the customer, but you can't magically write code in that short period of time because someone said that you had to

[00:25:24] **Ben:** it's one thing, if a customer needs it. It's another thing when you ask, where did this date come from? And they're like, well, there's going to be a marketing event around this.

[00:25:33] **Ben:** And you're like, well, maybe you should wait till

[00:25:35] **Carol:** so you played in it

[00:25:36] **Ben:** you start marketing it. Call me crazy.

[00:25:38] **Carol:** Yeah. Call you crazy.

[00:25:41] **Tim:** Hey crazy.

[00:25:42] **Carol:** Hey, crazy.

[00:25:43] **Tim:** But I don't know how to solve this nut, right? this is kind of a tough one.

[00:25:47] **Carol:** Yeah. It's definitely hard.

## [00:25:49] Shortcuts And Techinical Debt

[00:25:49] **Adam:** to come back to this idea of doing it right. A couple of you guys have said, it takes a certain amount of time to do it right. And like we talked about writing tests and the documentation and considering all the things. and that is where I want to put just the slightest amount of pushback on our total agreement with how here,as a really small business, one of the things that's constantly going through my mind as we're working on things is should I be doing this?

[00:26:12] **Adam:** Like, I'm thinking of a, that's in an office space, like, is this good for the company? Um,like what we like to do as developers is like, you're saying, do it right. Like we want to go full on like, clean code and, write all the tests and,use all the patterns. Right. That sort of thing.

[00:26:32] **Adam:** But it. There's a little bit of time pressure. You might be more inclined to put in a little hack that can save you 20 hours of work by putting in 15 lines of garbage code.

[00:26:44] **Tim:** dirty Cod.

[00:26:46] **Adam:** And that's good enough for like, like launch day and then you can come back and you can refactor and add those extra 20 hours of work later.

[00:26:52] **Adam:** if that is good enough, then that is literally good enough, right? Like, so you gotta be on the lookout for those. And I mean, what that isis it's technical debt, right? So you're intentionally taking on,this debt potentially harmful thing with the understanding that it gives you a short-term benefit.

[00:27:10] **Tim:** Right, but that is there actually that understanding that's my challenge on that. So you have a project manager who you initially say, look, I need three weeks for this. And he's like, look, we don't have that time. He or she says, we don't have that time. You're like, all right, look, I can do it dirty and quick.

[00:27:24] **Tim:** And I probably get it done in five days. He's like, all right, do that. Now you just trained that project manager that anytime you say three weeks, you can cut it down to five days. And so this technical debt builds because developers, rightly or wrongly. They in general don't people pretty well.

[00:27:40] **Tim:** they avoid conflict. some don't some really love conflict. I've got one that works for me. He loves conflict, but, in general, they're like, look, I just want to get it done and move on. I don't want to argue relentlessly on this. And so if you have that pattern of continually just saying, I'm just going to keep doing it dirty.

[00:27:57] **Tim:** Well, now you've just built this huge stack of technical debt that you know is insurmountable and no one can now you're bringing in tiger teams to fix everything and rewrite everything. And yeah. So I get what you're saying on that, Adam, but it's like that if you have a PM who understands that says, look, we can do this in the timeframe you want, but afterward we need to schedule actually scheduled time for the three weeks.

[00:28:26] **Tim:** We need to do this right.

[00:28:27] **Carol:** And commit to it and let it go through because that's not what typically happens. Usually you say, I need the time. Well, when you finish this, there's a new project. There's a new deadline, there's a new delivery. And now your tiny team that you have, like Adam's supporting this now is now having to do with having to deal with a new deadline and support this technical debt that you put in to cut the deadline up front

[00:28:50] **Tim:** And how do you explain that to the customer? Like, so you just released a new feature, right? That you cheated your way into, and you're like, okay, in our next sprint, we're going to add, two weeks to make this better. They're like, well, it works. They don't understand it. So they're like, this is just wasted time.

[00:29:06] **Tim:** You're just, you're just wasting time and resources on this project. And I mean, that's really hard to explain to a person that like, look, yeah, it works. But honestly it's not pretty.

[00:29:17] **Carol:** it's own work. Great.

[00:29:19] **Adam:** I think my perspective is a little bit skewed because my team is reasonably healthy about this stuff, right? Like we don't get those arcane. Like you will have it done by this date for no reason at all. deadlines. it is genuinely starts from a place of how long should it take to complete this feature.

[00:29:37] **Adam:** And, I don't think, I think we get, we developers get too comfortable with kind of making a guess. Personally. I feel like I do better estimations when I take the time and think, okay, I need to break my feature down into all of its smaller constituent parts and think about all the implications of those.

[00:29:55] **Adam:** And some of those get broken down into smaller parts. And how long do I really need to write that one part? And then you add them all up at the end. And I find, I get a much better estimate from that. And of course then I like, add another 50% or something like that for tests and documentation and API.

[00:30:11] **Tim:** Yeah, I do think there is benefit in braking. Much bigger task into as small as possibly can because there's room to basically add wiggle on. if you have like five things you're like, and you estimated at a certain time, they're like, okay, you know why those five things take that long, but if you have a hundred things that I go, okay, that's a

[00:30:32] **Tim:** lot, right? Yeah. That's a whole lot you're doing

[00:30:34] **Carol:** Clearly we now see it

[00:30:36] **Carol:** Right.

[00:30:37] **Tim:** Right. But I mean, that's a lot of just administrative work. I mean, that's just, again, that's trying to hold people accountable, and then beat them. So I mean, my philosophy, I totally agree with how, I mean, I totally agree with what he's saying. I don't think that the whole idea of doing sprints should ever be a way to punish developers for

[00:30:55] **Tim:** not getting stuff. The idea of a sprint is all right, look, let's just scope this. Let's just say, we're going to deliver something in two weeks. And here's what we aim to do. But the customer and project manager and everyone has to understand this might not be a hundred percent done. So even within that sprint that you're doing, there needs to be an order of priority.

[00:31:15] **Tim:** What is the most important out of all this? Right? So what's the stuff that really needs to be first and get that, try to work on getting that done. And if you know the lower priority things don't get done, then you just move them to the next sprint. And there's no punishment. There's no, write-ups, there's no, you failed.

[00:31:33] **Tim:** the idea of a sprint is trying to build a bounded box of work that you work on. And if you don't get to all of it, you just move things that didn't get done into the next one and build that next box of work. It's just moving the ball forward rather than saying, is it a passer.

[00:31:47] **Adam:** II completely agree with the whole concept of like sprints. Shouldn't be a tool for. Deciding who gets promoted and who doesn't, or, like whatever sort of consequences. But I think that the sort of the inverse of that for me is that in some ways, time, pressure is good, right? It encourages it too much.

[00:32:08] **Adam:** Time. Pressure can be bad, but a good amount of time pressure can be healthy for the business and for the product like this whole, my triumph about not writing the feature that was born out of, not only are we trying to meet an arbitrary deadline set by the customer, not necessarily arbitrary, like they, they want to run a giving campaign and we're trying to build a feature that can support them through that campaign.

[00:32:28] **Adam:** And, not, I only did. They just like draw a line in the sand and say, okay, this is when we're running our campaign and we need you to have it ready for that. about, at the very beginning of this week, they had a meeting and they called in, some of our people and they basically said, okay, we're changing the rules, moving the goalposts.

[00:32:43] **Adam:** and now you have more work to do in less time to do it. And, and we're have told them all along, we're going to do our best to try and help you out here. But, you're by creating a moving target, you're making it that much harder for us to accomplish the goal.

[00:32:55] **Adam:** And we're not going to be at all upset if we miss it, although we're trying really hard to hit it. And one of the things that is helping us do that is where can we cut fat? Right? what absolutely has to work at launch and what can we put off? And by, by deciding, oh, we can modify the database records directly to create the relationship and the data that doesn't have an admin interface, then, not having to build the UI to do that.

[00:33:19] **Adam:** That's going to save us probably a week or two of like two or three people's time.

[00:33:22] **Ben:** the idea of de scoping a release is one of the most underutilized management techniques that I see. And I think

[00:33:32] **Carol:** Explain that I don't know what de scoping and

[00:33:34] **Ben:** kind of, kind of what Adam's talking about, where you have a deadline and what you try to figure out is what you can fit into the deadline. Not necessarily. How long is it going to take to build this entire thing?

[00:33:46] **Ben:** so you sort of work kind of inverse. You don't get a set of features and then have to ship it on a certain date. You have a date that you want to ship stuff, and then you D scope the set of features to figure out what makes sense to ship during that period. And,

[00:34:01] **Tim:** I, again, people

[00:34:03] **Ben:** oh, well, and then I, and

[00:34:05] **Adam:** But you can change it over time as we close, or you can go, okay. We're definitely not going to have time for that. So you prioritize upfront the thing. Yeah. Upfront think about these are the things that absolutely must be included the critical path. And as long as you get all of those done, then everything else after that can be just a priority list.

[00:34:24] **Adam:** And, as long as you're working top priority to lowest priority, whatever you don't get done, it gets cut.

[00:34:29] **Carol:** So that's a problem too, because you don't always have staff to handle all your top priority. So you need things in there that your other teammates can be working on. If you don't have the skill set for it. So that's a whole nother topic, but yeah, you can't always have the same person doing those top five items that are critical.

[00:34:45] **Carol:** You may need to spread out some work.

## [00:34:47] Pushing Back

[00:34:47] **Ben:** I think one issue. And unfortunately this falls squarely on the shoulders of engineers. I don't think most engineers are good at pushing back against anything.

[00:34:59] **Carol:** No, absolutely not.

[00:35:01] **Ben:** they like, tough love, like they need to learn how to do that. Because if you never pushed back against anything, you just get into this toxic cycle. Over promising and under delivering. And then as much as Tim, as he was reading from house thing was saying that the role of a manager is to protect you from upper management. everybody is optimistic about what can get done. And at some point the engineers are responsible for doing the work, which means they're ultimately the most responsible for pushing back.

[00:35:34] **Carol:** I have had that hard conversation with engineers and with managers, why did you tell him that we could do this? Like, why did you tell the manager that we could achieve this? I need to know. And the answer is they were standing here and they wouldn't quit asking when we could do it. So I just said yes.

[00:35:50] **Carol:** So they would leave. And I'm like that doesn't work because now you've committed to it. Now I have to go stand in front of someone and go, we can't do this. Don't speak to engineers again. If you're going to be pushy, like go away, like you're just causing a bigger problem by doing.

[00:36:06] **Ben:** We've talked about this. I'm almost certain on a previous episode, but, the guys over at base camp have this concept of appetite where they, instead of thinking about when they're going to release something, they ask the company how much the appetite we have for working on this. Meaning like how much time and effort do we really want to put into this?

[00:36:26] **Ben:** Because it's easy for a product designer to look at something and feel like I need to this a hundred percent. Otherwise it's not going to be useful, but if you ask them how much time they want to put into it, and they're only comfortable saying, I feel, I want the company to dedicate a month of time to this.

[00:36:43] **Ben:** Then at least it gives you this. Now we can get on the same plane about what we're talking about, because you say you only want to put a month into it, and I'm telling you that what you want would take four months to work. Well, now we have to find a compromise because I can't make it fit into a month and you don't want to go longer than a month.

[00:37:00] **Ben:** So now let's start to have the tough conversation about what can we fit in the appetite of work you want to dedicate to this?

[00:37:08] **Tim:** Yeah. I mean, so kind of the business model that I work in is if you're billing time and materials, I see my time is such an important factor in this because every hour spent is an hour being built. A lot of the stuff I work on, cause it's financials, it tends to be transactional base. So it's like I'm building something that in return is going to generate a transaction and I would get the money from the transaction.

[00:37:33] **Tim:** It has nothing to do with how long it takes to build. In fact, typically there's no upfront professional services costs at the beginning. I would rather lose money at the beginning of the relationship, as long as I can keep you for the next five to 10 years and make money every single day in a, in recurring and on transactional basis.

[00:37:52] **Tim:** So what I tend to do is rather than worrying about how long something takes, I'm like, what is the minimum you need to achieve the goal you're trying to get to, right. give me the MVP. We're talking about that earlier, right? The MVP, what is the MVP that you need to get this done? And don't, don't throw on the bells and whistles and the absolute minimum and we'll shoot for that.

[00:38:14] **Tim:** And however long that takes. But at the end of it, it's going to be what you need to get done now that we call that our day one. Right? So that's our day one release day one. What do you need the absolute minimum to achieve whatever goal business goal you have. All right. And then day two is like, all right, now that we've achieved your base minimum.

[00:38:35] **Tim:** What do we do to make the experience better? What are the things you'd really like to have that are beyond the base minimum? And then we have a day three. It was just kind of like the pie in this guy, wishlist that lot of times you never even get to. And so attacking it from, look, we can't tell you how long it's going to take, but we can tell you that when it's done, it will be a good customer experience.

[00:38:57] **Tim:** Even if it's minimal. Even if it doesn't do everything you want to do, what it does, it will do well, it will execute and it won't fail. And. That is sort of a better conversation that, that I can have with customers, because they can agree with that. It's like, look, if you hold us to a deadline, we were at least something and it's not going to make you look good.

[00:39:18] **Tim:** your name's going to be on this and it's going to break. It's going to error. It's going to fail because we didn't have enough time to do it the way we needed to be done. So let's get it to a good state that everyone can be proud of that your customers will have a good experience with. And then we say it's released.

[00:39:35] **Tim:** So that's kind of how we attack those kinds of problems.

[00:39:39] **Carol:** All right. I'm going to put on my therapist, Carol glasses and hat for a moment. You all three just said the same thing, different ways.

[00:39:47] **Tim:** Right.

[00:39:48] **Carol:** Yeah. I just want to make sure you understand that like, and then you were like shaking your head no, to something Ben said, but then you just said it a different way. But the same thing, like we're going to Sam, we're going to box in this thing of time.

[00:40:02] **Carol:** We're going to say, we can only get these things done, which is to you your day one items. This is what we're going to get done. Everything else is going to have to go to a day two, which is now our next set of what we can get done.

[00:40:13] **Tim:** Right. But he was

[00:40:14] **Carol:** all at once.

[00:40:15] **Tim:** but he was working toward a date. Right? So

[00:40:17] **Carol:** are too, you have a day one release.

[00:40:19] **Carol:** This is what we're doing on day one,

[00:40:21] **Tim:** no. Day one is no I'm working toward, here's what the features will be when it's done. There is no deadline. That's the difference. So, so Ben was saying, you scope it and say, here's what we can get done by December 1st.

[00:40:36] **Tim:** I'm saying there is no December. First you tell me what the MVP is. Yeah. You tell me what the MVP is and we will get it done, but I'm not telling you what day that's going to happen.

[00:40:47] **Carol:** didn't you also just say, if you release it early, then you're going to look bad. So then you let them do it or you

[00:40:52] **Tim:** I was talking about, I was talking about whenever you, when you actually estimate and give a date,

[00:40:56] **Carol:** okay. Okay. That's you know, following. All right. Therapist's hat off, back to the us now. Yeah,

[00:41:00] **Carol:** we're good.

[00:41:01] **Tim:** I mean, there's a slight, I get what you're saying that there's some similarities, but it's a slight difference. Ben was saying, if you're working towards a date, I'm saying you don't work toward a date.

[00:41:08] **Tim:** You say what needs to be done? What are the absolute minimum features? And you get to those features and however long it takes.

[00:41:15] **Carol:** where you go.

[00:41:15] **Ben:** I think though,

[00:41:17] **Carol:** I'm on your side,

[00:41:17] **Ben:** all of us are talking about iteration really, and being able to see large things and understand how to work towards them in steps instead of these big bang releases.

[00:41:28] **Tim:** Yeah. The old waterfall methodology. I mean that's how did anybody ever

[00:41:33] **Tim:** think that

[00:41:33] **Adam:** It makes sense from a planning perspective, it's just, you can't use it for planning time just in planning sequence.

## [00:41:44] &quot;Work Will Expand To Fit The Time Allocated&quot;

[00:41:44] **Ben:** Yo, can I go ran for two seconds?

[00:41:46] **Adam:** All right.

[00:41:47] **Tim:** do it.

[00:41:47] **Ben:** one thing that drives me crazy is when a manager drops, the phrase work will expand to fit the time, allocated

[00:41:59] **Ben:** this idea that, oh, if I give a developer a month to do this job, then of course they'll take a month because why wouldn't they, I feel like there's something just terribly insulting about that.

[00:42:10] **Ben:** Like, we're so bad at our jobs that we don't know how to manage our time. And I, I think part of it is that there's this stereotype that, because developers love to code so much that, they'll spend a month automating something that you could do manually in 10 minutes, or I, all this like crazy stereotypical nerdy developer stuff, but like, that's not the people I know.

[00:42:36] **Ben:** That's not the people I work with. Like everybody has too much to do all the time. They're scrambling to get stuff off their plates so they can get to the next thing, which is probably overdue as we're discussing already. Like, nobody that I know is just sitting around, trying to fill up time with code and it drives me bonkers.

[00:42:54] **Ben:** When I hear managers talk like that. it's so dismissive of how people

[00:42:57] **Tim:** Yeah. It's the idea that people are inherently lazy and slackers and we'll do the absolute minimum. And for the most part, I don't see that most developers are that way. I mean, share them some bad apples out there, but they get found out pretty quick. And how actually talked about that. So he's like, if you're, if you want to do something you already want to do, what is the sense behind holding you accountable, eat this ice cream and I'll need to see status reports of how much you've eaten, accompanied by proof that you're actually eating it to make sure you just don't dispose of the ice cream.

[00:43:29] **Tim:** And it's kind of what you're saying. It's like, we want to produce good code. I mean, as, as best as we possibly can. And we will take the amount of time it needs to do that. The fact that they say, well, yeah, the level of effort will expand the time. Given is just a factor that shows that no one ever gives you enough time to work on something that needs to be done correctly.

[00:43:53] **Tim:** All right. Did you do all the tests? did you,did you code it clean? Did you re factor at least once? I mean, no, because you never give us enough time.

[00:44:00] **Adam:** there's definitely an element of truth to that, for sure.

## [00:44:03] Rethinking Sprints

[00:44:03] **Adam:** So I think that we've pretty thoroughly, destroyed this idea of sprints as a tool to hold developers accountable and enforce consequences, whatever those may be. But I'd like to maybe pivot the discussion a little bit to what is a more healthy approach to sprints in particular.

[00:44:21] **Adam:** Right. So I don't think that we're saying sprints are a bad thing, but that is a bad way, a bad, outcome to be using sprints to, to reach. Right. So what is the actual healthy reason to use?

[00:44:35] **Ben:** I like them as a ceremony that it's sort of a, opportunity to look at what's being done. And reevaluate, whether you're working on the right things, how much more time we want to put into stuff? Is, are there any, did we come across any unknowns that now need to be communicated at a broader level of the organization?

[00:44:53] **Ben:** So I like that there's a cadence to having the conversation about what's being worked on what's on the backlog and priorities, but beyond it being just a ceremony, I haven't personally used it for mine.

[00:45:07] **Tim:** I think so if you have a project manager or a scrum master or whoever, whatever the title is, who's worth their salt. What they're doing in that is they're setting a bounding box on a bucket of work. Right. And they're saying, all right, we got two weeks. Here's what we're trying to get done. Do you guys think.

[00:45:24] **Tim:** It's reasonable that it can be done. And everyone has a say, right? As we mentioned, everyone's bad at estimating. And so there inevitably are going to be wrong either over or under. and so, but they're, if you're they're good, they're going to go back to the customer and say, look, we think we can get this amount done.

[00:45:40] **Tim:** Chances are, it's probably we're estimating wrong. And so throughout this entire sprint, I'm going to be continually grooming the sprint and taking stuff out that may be lost. And that is not a failure. That is not anyone being lazy. This is just the nature of

[00:45:56] **Carol:** That's what it

[00:45:56] **Tim:** how things it is.

[00:45:58] **Tim:** People uncover people uncover a problem that is more difficult than they thought. And so it needs more time to be done. Right. And so I think sprint is a tool because developers don't care. You just tell him to work on some of their work on it. They

[00:46:13] **Carol:** Most of the time.

[00:46:14] **Tim:** Most of it, but it's like the sprint is a tool for the project manager to set expectations for the customer.

[00:46:20] **Tim:** And so if they just say, all right, we're going to do these 50 things. And no matter what is going to be done, they're not doing their job. Their job is to say, look, we're doing these 50 things we're trying, but they're constantly communicating through, say, look, we're going to have to cut these five things out because we discovered this and setting that expectation that's how it is not just pushing it upstream to the customer or wherever the stakeholder is and not pushing it down the developers as if they did something wrong in estimating something that honestly is not a hundred percent estimatable to begin with.

[00:46:55] **Adam:** It's interesting. So the way that Ben was describing sprints as ceremony and, deciding what's in and what's out and what we're going to push off makes me feel like what my team does is daily sprints. but I'll say that, but we don't use them as a tool for, managing customer expectations, right?

[00:47:15] **Adam:** This is all internal to our team. Like we're doing daily sprints to just keep each other abreast of what's going on in our work and to help pull our heads. We have a morning meeting every morning, we call it our standup, but it's not really a standup. and we just real quick go through the stuff and then like, get everybody on the same page.

[00:47:36] **Adam:** And then we'll kind of break off into, breakout rooms or whatever to discuss bigger topics that need additional input. and. I the, I think the reason that we don't need to use sprints as a customer expectation management tool is because we only have one person doing that job. And he does a really good job of setting those expectations without, without that sprint tool, I guess, I think my, impression of the expectations that he's setting is it'll be done when it's done and we're going to, we're aiming for roughly here and if it's not there, then it's not there and we're going to give you something that we're proud of.

[00:48:11] **Tim:** right.

[00:48:12] **Carol:** the other thing I like about sprints is grouping like work together. So we can see that these efforts are going on. So if we have multiple that are touching the same area, we can go, Hey, you, five developers on the team are kind of siloed off for two weeks working on this little area. So everyone knows what's going on.

[00:48:29] **Carol:** And then our SQA team knows what's about to come down the track. So they don't start testing one. And then there's really four more with it. So, it's kind of all together and they can just hold it all at once and release it all together as like one group of work, as opposed to them having to retest the same piece of the system over and over and over again, it gives them the ability to kind of group work together into a single.

[00:48:52] **Ben:** I'll throw out a hot take, which is that if you're having long discussions about how long the optimal Springs should be, you're probably doing it wrong.

[00:49:03] **Carol:** Doing it all wrong.

[00:49:05] **Ben:** my take. I just feel like you're focusing on the wrong thing somehow. I can't articulate it any better than that, but the length of your sprint should not make or break your product development.

[00:49:17] **Ben:** I can't imagine how it would. And if you spend a lot of time thinking about it, I feel like that's time you could have spent building a

[00:49:24] **Carol:** like imagine a month long sprint, like I can't

[00:49:29] **Carol:** see that being

[00:49:29] **Ben:** I'm saying like,

[00:49:30] **Carol:** Like two weeks is a

[00:49:32] **Ben:** if you're going to argue between one week and two weeks, then I feel like,

[00:49:36] **Carol:** You got other stuff. You've got nothing to do in your job every day. So go find something else to work on, please.

[00:49:43] **Carol:** of course. I don't like linting so, Oh.

[00:49:45] **Ben:** we all have our things

[00:49:46] **Carol:** There then

[00:49:48] **Adam:** I'm going to make you, we're going to make you put a quarter in a jar every time you bring that up.

[00:49:53] **Ben:** well, but linting, I mean, to some degree, it's like this belief that you should be standardizing on something like, oh, every like every team in the company should be running a two weeks. Because we need to have standardization. Just like what? Why? Just try that. Sorry. Okay. I'm done.

[00:50:12] **Carol:** Well, I struggle with it too. Is it really a sprint? If we're doing continuous deployments, like we deploy four or five times a day, is it really a sprint? Because it's so I'm doing like hourly sprints, I guess. I don't know, like we've released when the work's done. It all goes out. The only thing we use the, yeah, we continuously deploy literally all day long.

[00:50:32] **Carol:** We have like, we had 700 and something deployments last year and we have a lot of holidays and we don't release on weekends or Fridays or usually early

[00:50:41] **Adam:** Yeah. That's like three or four a day on average.

[00:50:43] **Carol:** Yeah, we have, it just goes out as it's done, we don't stop anything. so the only thing we use sprint dates for is when the actual system is going to be making a change and we need to train customers on new workflows.

[00:50:56] **Carol:** Then we're like, Hey, this Thursday, you need to know that this is changing as you wanted. So prepare 500 users for this, because they're about to see something different.

[00:51:06] **Tim:** So, I mean, I just want to say, I'm going to like message how that we've talked about

[00:51:11] **Tim:** this. And so maybe he'll have some feedback on this, but, yeah, I appreciate his posts and he's got a a lot of

[00:51:16] **Carol:** I agree. Yeah.

[00:51:17] **Tim:** there's a lot of things I agree with him on. So it's just, how do you

[00:51:21] **Carol:** Okay.

[00:51:22] **Tim:** everyone buy in on this kind of thing?

[00:51:24] **Tim:** Because I think lazy project managers are just like, well, the customer said it needs to be done by here. So we're just gonna, beatings will continue until morale improves.

## [00:51:32] Micromanagement

[00:51:32] **Adam:** I'm surprised. I didn't think of this earlier, this whole situation, this hypothetical situation, that the person that was talking to how created, like they want to hold developers accountable reminds me of like a story where you hear about the guy who owns or manages the movie theater and he's not onsite, but he's at home watching all the security cameras and they'll like call and yell at the employees if they're standing around too much.

[00:51:54] **Adam:** Like, if there's a, if there, if the problem is that your employees know this movie theater thing is way off topic, I guess. But if they're not busy, then you're not doing your job for getting enough people into the movie theater. Right. Like,

[00:52:04] **Carol:** Yup. You should have had your roadmap planned already and knew what was coming in the pipeline

[00:52:09] **Adam:** right. Yeah. So like the, I, I don't think I'm disagreeing with anything we've said, but like, if this person is so focused on holding developers accountable, then they're, it's their expectations that are wrong, right? Like, yes, we need to be accountable for our work, but deadlines is not the tool.

[00:52:28] **Carol:** I will say there are places and industries where micromanagers are successful and do well. And if you are over 16 year olds working at a movie theater, you need to micromanage. If you are over software engineers, you should not be a micromanager because you're just going to piss everybody off. And you're not gonna have people on your team that support you anymore.

[00:52:55] **Carol:** Like you can't be in that role and BMI be a micromanager. It doesn't work. So stay off the security cameras, if you are managing me because I've got my stuff.

[00:53:04] **Tim:** Yeah, for sure.

## [00:53:07] Patreon

[00:53:07] **Adam:** Okay. Well, it sounds like we're done. Okay. Well then this episode of Working Code is brought to you by two months, sprints and listeners like you. if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/working code. To thank our patrons for their support. They all get an invite to our Discord server, where we hang out and chat about the podcast and work stuff and life stuff, and how homes, Facebook posts.

[00:53:30] **Adam:** And we have other perks available like early access to our new episodes and the after show. And of course, we need to think our top patrons, Peter and Monte. Thank you guys so much for your support.

[00:53:40] **Tim:** Thanks

## [00:53:40] Thanks For Listening!

[00:53:40] **Adam:** if paying for podcasts, isn't your thing. No worries. We appreciate you taking the time to listen and there's some freeways that you can help us out too.

[00:53:46] **Adam:** You can share our show with your friends and your coworkers, or you can leave us a rating and review on apple podcasts or wherever you get your podcasts. we would love to answer your questions. So if you've got any or topics, suggestions, reach out to us on Twitter or Instagram @WorkingCodePod, or you can leave us a message on your old, that thing in your pocket that you use to doom scroll at night, when you should be sleeping, it's actually also a phone, a telephone, and you can put, you can punch numbers in it and then talk to people or even leave messages.

[00:54:15] **Adam:** And we have one of those

[00:54:16] **Tim:** Why would you want to do that?

[00:54:17] **Carol:** Or you can extend your car's warranty.

[00:54:20] **Adam:** You can yell at telemarketers. it was, we have one of those numbers. It's 512-253-2633 that's 5 1 2, 2 5, 3 code. If you want to leave us a message, we'll catch you next week. And until then,

[00:54:30] **Tim:** Remember guys, your heart matters. Even your project managers who set deadlines for no good reason.

[00:54:35]

[00:54:55]

## [00:54:55] Bloopers

[00:54:55] **Adam:** Okay. Oh, wait. That's I was going to say the wrong number, cause I didn't update it in the document. Here we go. And that's not the right date either. I guess if it was August

[00:55:03] **Carol:** Did you wear a slacker, Adam? You need to find some motivation to do this

[00:55:07] **Ben:** weren't.

[00:55:07] **Adam:** 1st.

[00:55:08] **Tim:** you weren't saying the data

[00:55:09] **Adam:** I'm not, but I like to know what it is.

[00:55:11] **Carol:** Well, you didn't spell September, right? Spit.

[00:55:14] **Adam:** We're doing this new thing

[00:55:16] **Carol:** Yeah. New months.

[00:55:18] **Adam:** October.

[00:55:20] **Carol:** are temporary.

[00:55:21] **Tim:** that's me, Carol.

[00:55:22] **Tim:** Welcome back.

[00:55:23] **Carol:** Yeah. Woo. Great vacation time. I've had a blast. first what's a Bailey wick,

[00:55:28] **Adam:** I had to go look it up too.

[00:55:31] **Tim:** It's I think it's a scam. I dunno. Maybe it's an English goddess thing is my grandfather always

[00:55:35] **Adam:** a person's specific area of interest, skill or authority like your field.

[00:55:41] **Tim:** What's the etymology of that.

[00:55:43] **Adam:** Huh?

[00:55:44] **Ben:** I like to use the word

[00:55:45] **Carol:** What's

[00:55:45] **Ben:** purview.

[00:55:46] **Carol:** Okay.

[00:55:47] **Tim:** well,

[00:55:48] **Adam:** that been?

[00:55:49] **Carol:** Y'all be using big

[00:55:50] **Ben:** Sometimes I like to throw out the word purview.

[00:55:52] **Adam:** No. Yeah.

[00:55:53] **Carol:** I love the purview

[00:55:54] **Adam:** like your area of responsibility to us is slightly different.

[00:55:57] **Ben:** I probably don't use it correctly, but no one knows what it means, so

[00:56:00] **Ben:** it doesn't matter.

[00:56:01] **Carol:** is kind of like what's in your vision. It's like what's in what you see? What is in your purview? Yeah. Hm. Okay. Anyways, I learned a new word tonight. That's a triumph.

[00:56:10] **Tim:** Yeah. Okay. So, so, so it's old English, ballywick district of a bailiff jurisdiction of a Royal officer or undersheriff

[00:56:19] **Adam:** so, I mean, in a way Carol's right. Cause like it's your or purview, right? it's the area you can see. Right. It's your area of your responsibility physically like geographically.

[00:56:30] **Tim:** yeah, one's natural or proper sphere of influence, so,

[00:56:34] **Ben:** I was saying that I will, sometimes someone will ask me a question and I'll be, and I'll say that it's above my head pay grade, but then,

[00:56:40] **Ben:** then it always makes me, I feel not like I'm shirking responsibility, but, for some reason that makes me feel more like I'm passing the buck than anything else.

[00:56:47] **Ben:** I don't know why.

[00:56:48] **Adam:** This is just like one,

[00:56:49] **Carol:** I know.

[00:56:49] **Adam:** colloquialism after another short game passing the

[00:56:52] **Tim:** Yeah. Or, or, is not my wheelhouse.

[00:56:56] **Carol:** wheelhouse. That wasn't him. That was a good one. Actually it gets you out of it without sounding like a jackass.

[00:57:02] **Tim:** Above my pay grade. It's kinda like they don't pay me enough to deal with that problem.

[00:57:06] **Carol:** That's kind of a

[00:57:07] **Ben:** Yeah, yeah, yeah.

[00:57:08] **Tim:** like, like I go further up the chain to those _(quack)_.

[00:57:10] **Carol:** What'd you mentioned on Tim

[00:57:13] **Tim:** Some beef jerky.

[00:57:14] **Ben:** I love jerky.

[00:57:15] **Carol:** Yummy. Oh, I love jerky too.

[00:57:17] **Tim:** About a dehydrator just to make it

[00:57:19] **Adam:** anybody you need a break or anything,

[00:57:21] **Ben:** It's like when you hear about the, that was it like, it was that NASA pilot. Drove down from like New York, New York to Florida or something with a, with a

[00:57:30] **Ben:** diaper on well, part of you is like, yeah, she's bat _(quack)_ crazy. But then part of me is like, but is she also kind of a genius? Like

[00:57:39] **Adam:** No,

[00:57:39] **Ben:** how much time could I be saving by wearing a diaper?

[00:57:42] **Adam:** no, it doesn't take that long to pull over and go to the bathroom.

[00:57:46] **Carol:** Well, you're not a female.

[00:57:47] **Tim:** Yeah. Do you know what old people tastes like? Ben

[00:57:51] **Adam:** Okay. Oh God.
