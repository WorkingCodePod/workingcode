---
title: "032: What Comes After Senior Developer?"
description: 'This week, the crew talks about the career path of web developers; how some positions allow you to be a "force multiplier" and have a bigger impact; and, how dopamine affects your sense of work satisfaction.'
date: 2021-07-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/032-what-comes-after-senior-developer/id1544142288?i=1000529572722"></iframe>

The world of web development is still a nascent industry. According to Robert "Uncle Bob" Martin, the number of programmers roughly doubles every 5-years. Which means that most of the developers that you interact with are relatively new and relatively young. It's not often that you look around and see developers in their 40s, 50s, and beyond; because, frankly, the web - _as we know it_ - isn't even that old.

Because of the ongoing evolution of our field, it can be unclear as to what a web developer's professional journey _can_ or _should_ look like. A lot of engineers seem to end up in management; but, for those of us that want to continue coding, what comes after Senior Developer? And, is climbing that technical ladder even something that you want to do?

This week, the crew talks about the career path of web developers; how some positions allow you to be a "force multiplier" and have a bigger impact; and, how dopamine affects your sense of work satisfaction.

## Notes &amp; Links

-  [Sarah Drasner: Engineering Management for the Rest of Us](https://www.engmanagement.dev/)
-  [David J. Schwartz Ph.D.: The Magic of Thinking Big](https://www.audible.com/pd/The-Magic-of-Thinking-Big-Audiobook/B002V1BMPI)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/032-what-comes-after-senior-developer.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** So, you're doing the unit testing. You're doing everything that uncle Bob Martin says that you should do, right. That, and that, that is your role as a leader, as a software engineer, to take those best practices and discuss, how do we implement them?

[00:00:14] **Tim:** Because best practices are great. Right. But it's, it's a

[00:00:17] **Tim:** goal.

[00:00:20] **Carol:** I mean kind of, you could, you could.

## [00:00:24] Intro

[00:00:24] **Adam:** It is show number 32 for July the 21st and on today's show, we're going to be talking about what comes after senior developer, when you're ready to move up, where do you go? And, what are the trade trade-offs there? But as usual, we're going to start with our triumphs and fails and it looks like Tim, it's your turn to go first.

## [00:00:54] Tim's Triumph

[00:00:54] **Tim:** All right. Well, I got gotta, guess it's kind of a triumph, so I've talked about it before, so we have a. We basically ship all of our data. We have a database that we write to, and we have a database that we read from for reporting purposes. And so we have a transformation service that takes all of our data from our, MySQL database and sends it up to a PostgresSQL database on AWS.

[00:01:22] **Tim:** And then it builds some materialized views. But recently the data has gotten so big over the years that it wasn't finishing in time. Cause there's was like some processes that kick off in the early morning and the materialized views weren't done by the end. So it was causing a lot of headaches.

[00:01:40] **Tim:** So basically had to re refactor all that stuff. But yeah, it what I had been doing was just building a materialized view for everything. For, I had one view for today. So today's stuff because I can refresh that concurrently very quickly. And then one thing for everything prior to today, prior to day one just wasn't it was just taking too long to build.

[00:02:01] **Tim:** So I broke it up into everything from today, everything from this year, and then everything from the prior years of this year. And so the prior years from this year, I don't ever have to, well, I don't have to rebuild, but once a year, which, it takes about 16 hours to build that one. Because um, it's all the indexes and things were bitten on it, but yeah, after a couple of days of doing that refactored at all, now it's running great.

[00:02:27] **Tim:** So was

[00:02:29] **Carol:** is 60 hours the new time, or did you cut that down?

[00:02:34] **Tim:** No. Well, I mean, 16 hours is about what it takes for For doing it the way I'm doing it now, where it's everything from a prior year. But I only have to do that once a year. That the one that runs for that's doing this year, it takes about 15 minutes to build the entire materialized view. So it does that kicks that off at midnight, says, give me everything from yesterday and this year and builds up materialized view.

[00:02:58] **Tim:** But main thing is it runs super fast because it's materialized view in Postgres

[00:03:03] **Carol:** Cool.

[00:03:03] **Carol:** Cool.

[00:03:04] **Adam:** how you can tell when a another developer is using Postgres?

[00:03:10] **Tim:** Just wait,

[00:03:10] **Adam:** Yeah. You don't have to worry about it. They'll let you.

[00:03:14] **Carol:** Okay,

[00:03:15] **Tim:** I don't get that. I'll get the elitists over there. That it's just another database for me. Some developer chose it and it. works fine.

[00:03:22] **Carol:** You just landed with it.

[00:03:24] **Tim:** now I didn't pick it. Yeah. Just dealing with it. But as I said, I think I said another show it the way it deals with dates is really weird. I don't know why it's so weird, but.

[00:03:33] **Ben:** Using, I don't know if you want to call it a materialized view in the PostGrest sense, but in general, just the idea of using some sort of a de normalized set of data that is catered to some set of reports. I feel like that's the promised land that I've never quite been able to get to. We have a primary databases and read replicas and we'll do a lot of reporting on the replicas, but the replicas are just an exact structural match of the primary database, just on smaller weaker machines.

[00:04:03] **Ben:** And I feel like we've never really been really able to leverage the idea of having a true report oriented structure of data. I want that. I want that bad.

[00:04:15] **Tim:** It is pretty nice because it's like, you don't have to do, I don't ever have to do any joins when I'm curing those materials you use, everything's just flat. And so there's no joins everything you need. Is there, you don't have to go looking for that. Where's that field that I need. It's,

[00:04:29] **Ben:** Are the materialized views, is that just for internal employees at your company or are these customer facing in some ways?

[00:04:36] **Tim:** No, it feeds our, some of our API APIs that do reporting. So yeah, it customers and internal people use it as well. But the best thing about it is just how incredibly fast it runs. That's me. How about you,

## [00:04:48] Carol's Triumph

[00:04:48] **Carol:** Okay, so update, I still have three bird eggs. They're doing good. No cats have gotten to, or anything. The mom did fly out of the birdhouse today and scared me pretty bad. Cause I wasn't expecting a bird to be in the bird house. I mean, I don't know what I expected to be there, but I was hoping it was just three eggs anyways.

[00:05:05] **Carol:** So that's three eggs. And then I'm going to go with the big triumphs that I talked a few weeks back about being selected and getting into the Peachtree road race and I finished.

[00:05:16] **Ben:** Heck.

[00:05:17] **Carol:** I have on my race shirt today. And not that not that everyone can see it. It has a big, giant peach on it. So, you know, when you text someone

[00:05:25] **Tim:** It looks like a

[00:05:26] **Carol:** you know what it means?

[00:05:28] **Carol:** So when I was in my call today, one of my coworkers was like, oh, is that your shirt from the racist? But as the weekend, I was like, yeah, it is. And it's not a, but it's a peach, that's a peach, I'm a Georgia peach, not the Georgia, but so yeah, I did pretty well. I finished in an hour, five 15, so did a 10 K had a lot of fun, got really hot, but loved it.

[00:05:50] **Carol:** So when they do it again, so that's a triumph. Yay. About.

## [00:05:56] Ben's Failure

[00:05:56] **Ben:** I'm gonna go with a failure. I think when I look back on my career, some of the things that I regret the most are having a bad feeling about something and then not pushing back hard enough against the people who want to do that bad thing. And the bad thing is almost always introducing some new technology or paradigm shift in the way we're doing something.

[00:06:18] **Ben:** And it's top of mind for me, because I've been trying to refactor a little bit in our legacy angular JS application, and years ago, some of the engineers decided that angular JS wasn't fast enough. So they pulled in react. So now we have react components being rendered inside parts of our angular JS application.

[00:06:41] **Ben:** And for those of you who don't know, react from angular from Adam they have completely different paradigms and the way they do change detection and how events are propagated. And they're just two completely different frameworks and having to manage life cycles across both of these is such a headache.

[00:07:00] **Ben:** And the problem is the stuff that exists in react is now sitting there in the application for the most part rotting, because nobody wants to touch it. And the stuff that's an angular is updated very regularly. And not that it's terribly good, but it's at least updated. And it just makes me I never wanted to pull react in when it was pulling the time, it was claimed to be pulled in for performance reasons, which I think is almost always a little bit of a red herring.

[00:07:26] **Ben:** And it it's an a, and I'm not trying to hate on react if it was just a react application would be great if it was just an angular JS application, it'd be great. It was the fact that these two were merged together, but it's not just this one time. Even just like yesterday, I saw PR come across my desk and I left a comment.

[00:07:47] **Ben:** I was like, I don't think that's a great idea. And the person was like, no, it's going to be fine. I was just like, okay. I, you know, I have this mentality where it's not that it's not my problem because it's still my application, but it's like, oh, you're making this decision. So you'll be around to maintain it.

[00:08:04] **Ben:** The problem is that that ends up not being true most of the time in the long run. So the things that I didn't push back against thinking that other people would be there to maintain it. Most of those people are no longer there

[00:08:16] **Carol:** And now you're maintaining it.

[00:08:18] **Ben:** and now I'm maintaining it. It's super frustrating. Anyway, Adam, what do you have going on?

[00:08:27] **Adam:** Well, how do I want to say this? I am an unabashed react fan boy. And I agree with you, like, if the code is 99% angular and that 1% react and nobody wants to work on the rack. That's that sucks, man. I'm sorry.

[00:08:39] **Ben:** Yeah.

## [00:08:41] Adam's Triumph

[00:08:41] **Adam:** I'm going to go with a triumph this week. I have a weird thing, but it's super neat and kind of mind-bending and just cool and fun.

[00:08:50] **Adam:** So, we've been working on this feature flags thing at work, and the, I think, I don't think this made it onto the show at all recently, but one of the things that we were trying to figure out is how we were going to store the data long-term cause we have a whole bunch of customer databases, but this data is cross customer, right?

[00:09:07] **Adam:** So we have feature flags that be able to turn on and off for specific customers and specific environments, that sort of thing. It's sort of another abstraction layer on top of the customer layer. And we don't have a central database for stuff like that.

[00:09:22] **Adam:** So I was trying to figure out what can I do to store that data? And this is not the first time we've done. This is actually the second time. But I'm making a few changes to the way we're doing it, but basically the application runs and on start-up it reads the data for our feature flags from just a flat text Jason file.

[00:09:41] **Adam:** And that's the feature flags that it serves via the API. And then let's just say, somebody goes into the admin and modifies a feature flag. What that does is it updates that file in place in the application as is running on like a far gate service on AWS. So it updates that file locally so that any future requests to the API, get that updated flight.

[00:10:03] **Adam:** But then it also clones a copy of the repository of itself locally modifies that file and sends a pull request to the repository with that updated file , and then what happens is when we go and we will review that change and merge it, and then there's like, we have a one button auto deploy to push up a new revision of the Docker container and redeploy the application with that new revision

[00:10:30] **Carol:** So it's still getting a human interaction with the confirm merge.

[00:10:34] **Adam:** Yeah. Human in the loop twice, actually. Right. So somebody has changed the feature flag and then we have a pull request which requires a code review and push button deploy. So it's like three sort of touch points there.

[00:10:45] **Carol:** Okay. That's cool, dude.

[00:10:47] **Adam:** Yeah.

[00:10:48] **Ben:** It does. This is this for all feature flags or just feature flags that were be customer specific or

[00:10:55] **Adam:** would be all of our feature flags.

[00:10:56] **Ben:** gotcha. Gotcha. Very interesting. I would never have thought

[00:11:00] **Adam:** It's like the old thing that the snake eating its own tail sort of thing.

[00:11:05] **Ben:** something like this would never have occurred to me. There's certain just, I'm not a very outside the box thinker. I'm definitely a, here are the tools that I have. How do I make that work?

[00:11:16] **Adam:** Yeah. We deal with a lot of configuration as data. And one of the things that I've come to love having and work very hard to never lose is w what's the revision history, the ability to roll back and the audit tracking that you get, like with they get repo of something. Right? So it's one thing to just have a table full of settings and be able to modify them that works great.

[00:11:39] **Adam:** But then you lose all of the ability to know who changed. What, when, what was it before to quickly roll back? And so that was sort of is what was going through our heads when we were trying to decide how to store.

[00:11:55] **Ben:** Very interesting.

[00:11:56] **Adam:** Why can't we just put it in yet? So, cause we were initially kind of thinking maybe we'll just throw it on S3 or something.

[00:12:02] **Adam:** And I know as three has some

[00:12:05] **Tim:** Self-modifying code is going to become Skynet eventually.

[00:12:08] **Adam:** hopefully not, I'll put in if Skynet then processed out exit one. So that's me, I guess that's everybody cool. So I guess a quick programming note, get it programming. We're recording this during whatever tropical storm or hurricane or whatever it is now, Elsa.

[00:12:30] **Carol:** Elsa.

[00:12:31] **Adam:** And so

[00:12:33] **Tim:** Let it

[00:12:33] **Carol:** let

[00:12:34] **Adam:** in the sticks and, and there's yeah, there's a good chance that you'll hear some storm noise in the background from some of us.

[00:12:42] **Adam:** So that's, what's

[00:12:43] **Carol:** It's already past us. Woo.

[00:12:45] **Tim:** Yeah, we

[00:12:46] **Tim:** had

[00:12:46] **Carol:** we got to like 2:00 AM this morning

[00:12:49] **Adam:** Yeah, lucky you. And there's a decent chance I'm going to lose power at some point. So that's just a, how it goes out here in the middle of the woods.

[00:12:58] **Carol:** in the sticks.

## [00:12:59] What's After Senior Developer?

[00:12:59] **Adam:** Yep. All right. So, moving on up, you know, when you get to be a senior developer and you've been there for several years and you feel like you're do a promotion, what happens next?

[00:13:10] **Tim:** Yeah. So, I mean, it's an interesting topic. I have noticed, and I'm talking over a long arc here. I'm not talking about just, come in as a entry-level programmer and then, the progression I'm talking about the longterm. So you're with the company for a while. A person has shows, promise and skills.

[00:13:29] **Tim:** It seems what tends to happen is that an engineer over the lifetime of their career, the push is that if you want to progress that the upper levels of things is management and management is dealing with. Less with building things and writing code and software and more with managing people.

[00:13:53] **Tim:** And I just wondering why is there a way to promote engineers that allows them to stay close to the code? I know that, at some level, if to be a manager, you have to deal with people, right? So if you're basically, if you're not a person who deals with people, they're probably not even going to offer you that anyway.

[00:14:09] **Tim:** But if you are, it's like I come from this from a personal perspective. Cause it's like throughout my career that I'm constantly trying to, they're trying to push me away from the code and more toward dealing with, budgeting and spreadsheets and hiring and firing and that sort of stuff.

[00:14:29] **Tim:** Yeah. And it just it's like, I don't enjoy, I like building things. And so I'm trying to figure out, how do we get to a place where you can continue to advance where you don't have to become someone who is so detached from the code base and from what the actual software is that, you feel useless when it comes to looking at stuff.

[00:14:49] **Tim:** So I don't know. That's what I struggle with that I suggested this topic while we're talking about it, because I don't know the answer, but I have ideas.

[00:14:57] **Adam:** So had a quick conversation before we started recording. And some of the things that, the words that were bandied about were like principal architect and what was the other one staff architect? Yeah. Or even like principal or staff developer, whatever. While you were talking, I was trying to think of like what's the difference between a senior developer and like a staff developer or principal developer.

[00:15:20] **Adam:** And what occurred to me, I think is that that's like a team leader, That's sort of a middle management type position. Your role is to do whatever you can to be a force multiplier for people on your team. In every way that's not directly like code related, right.

[00:15:39] **Adam:** So helping them get out of office politics issues or get around, get the support they need from another department, stuff like that. I'm wondering if maybe that's sort of the role of that staffer or principal level person, but from the technical perspective, right? So instead of directly contributing to the product, if you're working on a product or the service or whatever, maybe that's when you move up into like, all day everyday, you're focusing on customizing the framework that you guys use or building little tools to make life as a developer on the team, easier.

[00:16:20] **Ben:** I think that's true where I work. We have staff and principal engineers, and, the higher you go up the harder, the problems you're supposed to be addressing. And I think hard in this context is, is the term you used was force multiplier. And I think the hard problems are the ones that pertain to the most number of teams and can have the largest impact on the most number of engineers.

[00:16:47] **Ben:** And, I mean, full disclosure, I am also a principal engineer and I don't know, do any of that, which also gives me like a tremendous amount of imposter syndrome. I was just told one day that I'm a principal engineer and I was like, okay. So I'm just going to continue to do all the things that I already do.

[00:17:06] **Ben:** Yeah, at least rings. True. What you're saying over at Invision for sure.

[00:17:13] **Tim:** I mean, so you're talking about principal engineers. So what about the role of CTO?

[00:17:18] **Adam:** I guess. I, you know, I think in my opinion, as somebody who technically is CTO, but at a five person company that role is going to vary tremendously depending on the size of the company and what the company does. Right. A CTO for Walmart is going to be a vastly different job than me. And, I'm a CTO, that's also an IC, right.

[00:17:40] **Adam:** I I'm an individual contributor. Right. I'm writing 99% of my time. I'm writing code, you know, the rest is like meetings to facilitate writing code. So I don't know. Does that answer your question?

[00:17:53] **Tim:** Yeah, I kind of, but you've been, a CTO?

[00:17:58] **Ben:** I was formerly a CTO and, uh, yeah I just don't know how to do it. I'm not, I'm an individual contributor through and through cut me and I bleed code. I don't, I don't know what it means to organize teams and have a vision of where you want something to go and have a roadmap that gets you to that vision.

[00:18:18] **Ben:** I'm very much a shortsighted thinker, but like I said in the triumphs and fails, like I am a, here's the tools that I have, what's the most that I can do with it. I don't have the muscle for thinking, how do I build new tools? What if I use totally different kinds of tools? Like, that's just not a mindset that I have and I've never focused on trying to improve that.

[00:18:43] **Ben:** So for me, the closer that I can get to the code, the better.

[00:18:47] **Adam:** Yeah,

[00:18:47] **Ben:** Now the problem though, is that I also want to have an impact and I want that impact to also be largely customer driven. I mean, I want to have contact with the customers and I want to be able to build things that the customers want. And it's hard sometimes to get all of those desires to kind of coalesce into a proper

[00:19:07] **Adam:** that's a very small intersection on your Venn diagram. Yeah.

[00:19:09] **Ben:** yeah, yeah, exactly.

[00:19:12] **Carol:** Yeah. So for me, I started as an intern and then just joined the team and then became a team lead. So it went from writing code and figuring out what I was doing to being on a team, to then being over a team. And it was a lot of, not necessarily managing people, but expectations of trying to say what we can and actually can't deliver.

[00:19:35] **Carol:** And it was being the voice of reason when people under you don't have the ability to necessarily say where they can get with something. So it was being able to kind of look at that picture and go, while you say, you can get this done in the week, I've seen how you work. Realistically, we should put two weeks on this.

[00:19:54] **Carol:** Now we're not up against a wall and we have. Made the customer mad and you're not under all this stress because you don't even know. So it is, getting those kind of roadblocks out of the way when they do happen. But it's also being able to communicate where your team can actually go and being able to be the voice of reason when it's needed.

[00:20:11] **Adam:** Right. I really like this topic because I'm kind of at that stage in my career where I'm starting to think about this stuff. And honestly, I think I could be happy going in either direction. Ben was saying with the imposter syndrome stuff, like there's, there are days and they're not all that infrequent that I.

[00:20:35] **Adam:** Look at the new technology that's going around and I'm just like, get me out of here. You know, I'll do whatever it takes. I'll manage people. If I can just not have to keep up with these kids out of college right now. Right. Like they know all these things and they're saying words, I don't even know what that means to like, how do I Google that?

[00:20:52] **Carol:** Yeah.

[00:20:54] **Adam:** And so, so I'm in, that's not the only reason, you know, I think I think I might've mentioned in the past, just like I've grown up a lot. My wife is a therapist and I feel like

[00:21:06] **Carol:** She's made you better.

[00:21:08] **Adam:** has but I've been going to therapy myself, not through her and through whatever. Well, you know, I've had an imperfect life and I'm trying to do better for that, through the therapy.

[00:21:20] **Adam:** And I've learned a lot and I've become a better person. And I feel like my emotional intelligence has leveled up a couple of levels just within the last like five years. And

[00:21:29] **Tim:** Hm.

[00:21:30] **Adam:** I, in that regard, I see that possibility of helping a team of people or something like that. And, I see that as a very possibly fruitful path forward for me.

[00:21:42] **Adam:** But at the same time, when I think about the code that I like to work on, it's the stuff, it's the automations,

[00:21:48] **Carol:** Yeah.

[00:21:49] **Adam:** the stuff that's going to really impress my teammates, because it's going to make their jobs easier sort of thing. And that's like what I'm thinking about with that whole principle engineers sort of thing.

[00:21:59] **Adam:** And so like both appealed to me and I don't know which to really pursue.

[00:22:05] **Ben:** Yeah.

[00:22:05] **Carol:** that's one of the things I thought about when we were talking about this topic was that as I get older, I find myself feeling like, I don't think as quick as kids coming on now, right. The youngsters, they just like whip out things. And they're just thinking through, and I'm like, going, hold on, wait a second.

[00:22:22] **Carol:** I need two more cups of coffee to even comprehend the sentence you just said. So I leaned like, just a minute, right. Then we'll come back to this. So I feel like at some point we become better as almost being like the librarians of the system, right. Or of like what we're doing. And we go to, instead of necessarily being the top person, writing all the code.

[00:22:42] **Carol:** You know, making sure the functionality is in place for everything that people coming on. Don't know. So again, it's putting things in front of the people on your team to make sure they have what they need to keep moving forward and the things they're not going to have when they come on, it's going to be you now spending more time sharing knowledge than writing code.

[00:23:00] **Carol:** So you're going to have to give up some of your time to keep the company growing and keep your team growing. You're going to have to step out of code at some point, not a hundred percent, but a little bit so that you can, or I would say even probably half your time to keep people on your team moving forward, you have to share the knowledge.

[00:23:20] **Tim:** That's a good point. Yeah. I mean, and that does seem to be, I mean, just because you have more experience where you're at you, you eventually become a guide and in some sort of way,

[00:23:30] **Carol:** that's a compliment to me. Like I take that.

[00:23:36] **Tim:** I kind of would step back a little bit and say, so what, what makes people want to be promoted in the first place? Right? So one money, right? Obviously if you're going to make more money, right. The them dollars. Right. But beyond that, I don't, for me, money has never really been the big motivating factor.

[00:23:55] **Tim:** It's it's I think been kind of hit on it is feeling like you're making an impact on the product. And that you are making sure that the course that the company is going on is one that is, is thought out and not just reactive. And so, one thing I kind of envisioned that I want, I don't want to be a general manager of, of a company where really my only job is to administrate, layers of bureaucracy below me.

[00:24:26] **Carol:** No.

[00:24:26] **Tim:** Is not fun. I've seen that job and I don't really want to do that. But what I do feel passionate about is the product, right? Building the product roadmap, talking to customers like Ben was saying, knowing what the customer's issues are building things that solve the problems that they have and Nessus, and not necessarily I can't, build it all uh, is a team of people that are building these things, but making sure that when it is being built, it is being built with best

[00:24:57] **Tim:** practices. So, you're doing the unit testing. You're doing everything that uncle Bob Martin says that you should do, right. That, and that, that is your role as a leader, as a software engineer, to take those best practices and discuss, how do we implement them?

[00:25:13] **Tim:** Because best practices are great. Right. But it's, it's a

[00:25:16] **Tim:** goal.

[00:25:18] **Carol:** I mean kind of, you could, you could.

[00:25:23] **Tim:** but, how you implement them is varied. Right? So, someone has to make that decision. And I think that's where years of experience trumps the wide-eyed youngsters coming in that just, have great ideas, but not necessarily real-world experience.

[00:25:41] **Tim:** So whatever that role is, I don't know what role I just described, product owner or CTO. I don't know what you call that. That's sort of where I would like to see people grow into if they have the bent for, and some people, honestly, they don't necessarily want promotion. They just like, you know what?

[00:26:00] **Tim:** Just give it. Year over year, partially, you know, cost of living increases and I'll keep doing what I'm doing. And that is absolutely fine. You need people like that on a team because not everyone can constantly ladder a climb. If you do that, you just your organization is going to sustain that unless it's growing ridiculously

[00:26:18] **Adam:** Yeah, no, no team needs 12 principal architects and one intern.

[00:26:24] **Tim:** Yeah. Yeah,

## [00:26:25] The Money

[00:26:25] **Ben:** You know, it's funny though, that you say that money is not necessarily your primary motivator and I'm the same way. And when the pandemic. Invision has been a remote first company since day one for the past eight years. But then when the pandemic came about some of the really large tech companies like Facebook and Google started to be much more remote friendly.

[00:26:49] **Ben:** If not remote first, I think a lot of Facebook people can just now work remote indefinitely. And we definitely lost some engineers to these big companies and in their exit interviews, they were saying, we're leaving because we just want more money. And remember hearing that and pushing back against that idea.

[00:27:07] **Ben:** And I'm like, no, that can't be right. Like, there's gotta be some cultural problem here. Like they're not feeling autonomous enough or they're not feeling empowered enough. And they were like, no, they just want more money. It's just like, I couldn't connect with that.

[00:27:21] **Tim:** but that is the easy answer though, , but sometimes it, that's the easy answer to give, but there's also something else, right. That they're not telling you in the exit

[00:27:31] **Carol:** Or, I mean,

[00:27:32] **Tim:** And then some

[00:27:32] **Carol:** it may be about the dollar, like really, if you are, if I see a job where people work out, that I know, and they're telling me that my quality of life is going to be about the same as where I'm at now, I'm going to face the same struggles I'm going to, have the kind of day to day. It's not going to be much different from what I'm doing now, but we'll throw on 30 grand.

[00:27:52] **Carol:** So what you're making right now, I mean, it is about, I mean, it's just dollars. And to me, I mean, I didn't my, when I left where I was at recently, it really honestly was a, a new tech stack. I was really excited about that and dollars that's that was it.

[00:28:10] **Tim:** You ever see that there was another reason?

[00:28:12] **Carol:** even if I was going to not a new tech stack, the dollars would have still been

[00:28:17] **Adam:** Yeah.

[00:28:17] **Tim:** Yeah.

[00:28:18] **Ben:** I was going to say and to be clear, I'm not diminishing that money is a very powerful motivator and that it gets you a lot of stuff. I,

[00:28:26] **Carol:** I'm sorry.

[00:28:28] **Ben:** I was just surprised that that was what people were stating as the reason that they were leaving. It didn't occur to me that that would be such a driving force.

[00:28:36] **Adam:** So I like, I totally agree with everything we've just said, but I think that the way I think about it as a little bit different. So the one thing that you can't change is the amount of time that you have,

[00:28:49] **Adam:** right? you.

[00:28:50] **Adam:** can't add more hours to the day. You can't, for the most part, you can't affect how long the work week is.

[00:28:56] **Adam:** You can change your employer to try and go to somewhere that has a four day workweek or something like that. But your controls on time are extremely limited. So what I like to optimize for is. A way, whatever I can do to make the most of my time. And, that means something different to everybody.

[00:29:12] **Adam:** The way I spend my weekends with my family, my current employer, we have not unlimited PTO, but know, I don't even know how to describe it. Just sort of like, keep your, keep the best interests of the company in mind, PTO. I'm taking a week off next week and I took some time, not that long ago and whatever.

[00:29:34] **Adam:** But yeah, I mean, so I optimize for time, but I think that having more money can help you make better use of your time. Like we were talking earlier today, Ben, about how nice it would be to have a personal. If you're getting paid 30 grand a year extra for no reason, all of a sudden you have a bit done, basically a, a lateral shift in technology.

[00:29:56] **Adam:** Right. Are you not going to consider like, Hmm, maybe I can get a personal assistant now, right.

[00:30:02] **Ben:** good point.

[00:30:03] **Carol:** someone's going to come clean my shoes now. Yeah. This one's getting cleaned up.

[00:30:08] **Adam:** Okay.

[00:30:08] **Ben:** No, but that's a really good point. I mean, I live very comfortably. I will admit that. So I think money doesn't remove pain from my life right now. And there was a point in my life when I was younger. When I, it was very clear that all of a sudden my life, I had more money than I had time and time became the very limiting factor and it like refocused everything.

[00:30:29] **Carol:** It does.

[00:30:30] **Carol:** Yep.

[00:30:31] **Adam:** That's there, there's like an inflection point early on in your career. Like when you were young,

[00:30:35] **Carol:** Oh

[00:30:36] **Adam:** you're high school, early college, or even first few years out of that college, it's like, all you have is time. nobody's, dying to beating down your door to pay you tons of money. You have you know, maybe you're not married or, or whatever, that sort of stage of your life.

[00:30:53] **Adam:** So you've got free time and like, I'm thinking about like open source work and that sort of thing, like you have of all this time, and maybe you can use the time to make money and then you hit this inflection point where it goes the other way. And now you want to use your money to make time.

[00:31:10] **Ben:** Totally. Oh

[00:31:13] **Ben:** man.

[00:31:13] **Carol:** Mind blown right now.

[00:31:16] **Ben:** I will, I will have my inbox open and I'll see unread emails and I'll sit there and I'll have a little conversation with myself and say like, just read it, just read it and reply. You can do this, you can do it even just one. I'm like, this is an important email. You should open it and you should read it.

[00:31:32] **Ben:** And then I'm like, no, I don't have time. I've got other stuff to do. And I just, I it's like my whole being refuses to prioritize. Anything, but like a very slim select few activities. It's very uh, it's very limiting. I'll admit that,

[00:31:49] **Carol:** I did something very bad with my email, Ben, I I really don't like replying to emails either, and I don't think I'm as bad as you are, but I just, I don't like seeing them there either. So I went into my settings a week ago and gave myself like five different inboxes and they each only show five messages. Yeah. Yeah. So now I'll send you a screenshot of it. So now it only looks like I have a couple unread messages.

[00:32:16] **Ben:** there you go.

[00:32:17] **Tim:** That's not solving the

[00:32:18] **Carol:** you know, I think that's a win because I'm not so stressed out when I opened email now it's nice.

[00:32:25] **Tim:** Yeah.

## [00:32:27] Managing vs Being on the Front Lines

[00:32:27] **Ben:** One thing that I would I'd bring up in, I didn't come up with this. This is something that I've heard a bunch of other people discuss when they talk about promotions and it's this idea. Most people don't get promoted as much as they get recognized for doing the work that they're already doing. So you never jumped from, junior engineer to senior engineer.

[00:32:48] **Ben:** You take on the work of a senior engineer, and then at one point your manager says, oh, Hey, you're a senior engineer now because you've been doing all this senior engineer work. And I think it's, if you shift from engineering to management, that's probably a different,

[00:33:02] **Adam:** Yeah,

[00:33:03] **Ben:** there.

[00:33:04] **Tim:** But that's how they get you to like, can you make sure, you need to budget this and you need to do that. It's like, oh no, I'm doing all this is general manager stuff. This is CEO and stuff. I don't want to do this. And they're like, oh, you're already doing it anyway. Yeah. But I hate it.

[00:33:20] **Ben:** I think a lot of it comes down to where you get your dopamine hits from. So if I build a solution and that solution works. Or better choice of words. If I build a solution and that solution adds value to the customers, that's like where I get my high. And I'm like, how do I keep doing that day after day?

[00:33:40] **Ben:** And as a manager, you're not building the solution that adds value to our customers. You're building the team, that's building the solution that adds customers. And if you can get the dopamine hit from building the team, then that's great. Oh, more power to you. I don't want to say it's like a self-centered thing, but like, I don't get so much joy out of seeing this is going to sound terrible.

[00:34:05] **Ben:** I don't get joy out of seeing other people succeed.

[00:34:10] **Adam:** You're right. It

[00:34:11] **Carol:** then that sounds awful. Ben.

[00:34:13] **Ben:** That w and what I mean is like, I want to be there on the front line. Like I can't, I don't get joy out of standing behind watching other people do the work.

[00:34:21] **Adam:** You want to stand shoulder to shoulder and help them

[00:34:23] **Carol:** there you go.

[00:34:25] **Carol:** Maybe. Or he just wants all the credit. I don't know.

[00:34:27] **Tim:** Yeah. And now that you say that out loud, it's like, yeah, I get like this stupid materialized view that I worked on it. I got so much joy when I finally figured out I. Basically I had these three different materialized views and I put them together into a, just a regular view so that it would be a combined view and it was running really, really slow.

[00:34:49] **Tim:** If anytime I, I would try to do a, a limit and do a sort and I couldn't figure it out. It took me two, three hours. I finally figured out and fixed it. And I was so happy figuring that out.

[00:35:02] **Ben:** And to be clear, there's no one right way,

[00:35:05] **Carol:** Oh, no,

[00:35:05] **Ben:** in the same way that Tim wants to eat something that has like a million squabbles or I don't know what the term is.

[00:35:12] **Adam:** And then after it, he'll swap, he'll wash it down with a SCOBY.

[00:35:14] **Ben:** Right.

[00:35:16] **Tim:** Yeah.

[00:35:16] **Ben:** So, so like, I get a high off of building things, very low level. I had an engineering manager return strong, and when he should have been company, he was like, I came here to ship product. Like he didn't want to build the things he wanted to build the team that built the product and like, that's how he got his high.

[00:35:33] **Ben:** And that's totally great. It's, we're just not all built the same.

[00:35:37] **Carol:** And I feel like most engineers, aren't going to end up on that path. And I think with this conversation, it's okay to say, Hey, look, I don't want to go into management. I don't want to be the person handling all of this stuff. I want to keep going in technology. And force your way into it, make sure that when you're promoted, you're still doing the thing you love.

[00:35:56] **Carol:** Don't take a job that are promotion. That's going to put you into a position that you hate. Like make sure it's something you love, find that job. And if it's not there, make it a new job.

[00:36:05] **Tim:** Yeah. And so I think, I mean, it's kind of going to boil down to that. You either, if you are a person in charge and has people under you in direct reports, or, if you're an employee, there needs to be a conversation at some point to say, what does success in my career look like for the future?

[00:36:24] **Tim:** It needs to be that conversation because there are people will tend to assume that what it is they want is what you want out of a job. And that's not always true. You need to have that conversation. And I've done that, with people that I work with and, people that, that report to me, I'm like, what is it.

[00:36:43] **Tim:** That gets you going, what makes you happy? Some of them are customer service people and they just really enjoy interacting with people. Great. I mean, so what does success look like? And you got to have that conversation. And you know, and I've had that conversation with, people I report to is I've I told him, I said, look I'm not looking to be a CEO or general manager.

[00:37:03] **Tim:** I always want to have my hands on the product, and I know I can't build everything by myself. I'd love to if I could, but I, I can't,

[00:37:11] **Tim:** uh, needed to, right. You're not bad, but I need a team, but I definitely need to continue to be in it. But the thing that scares me is that in most companies and it's true in our company.

[00:37:23] **Tim:** So at some point, our, and we'll, we'll be split off. It'll be a separate business unit inside of our parent company. And there will have to be a general manager. And, but basically that general manager has the power to fire me. Now I could hire this general manager. I could select that person. And then at some point they could decide they don't need me.

[00:37:43] **Tim:** And I don't like that at all.

[00:37:45] **Ben:** No.

[00:37:46] **Tim:** so there's that fear that I need to have that power so that someone above

[00:37:52] **Carol:** man. You're in a

[00:37:52] **Carol:** catch.

[00:37:54] **Tim:** right. But in the grand scheme of things, someone

[00:37:56] **Tim:** above you can always fire you. So

[00:37:59] **Ben:** Yeah.

## [00:38:00] Moving Between Roles

[00:38:00] **Ben:** Remember listening to a podcast. This was maybe two years ago and I can't remember which one it was. And I can't remember who was being interviewed. I think it was someone who worked at Google. And, this woman was saying that she bounces back and forth between engineering and management every two years, that should do two years of management, two years of engineering, two years of management, because she feels like, you know, I think she liked to get back into the engineering to kind of refresh the, on the ground skills.

[00:38:26] **Ben:** And then she liked to bounce back into management so that she could do more team-building and force multiplication.

[00:38:32] **Adam:** And be curious to see what kind of stuff she was doing as an engineer during those years, because I feel like if I were to step away for two years and try to come back, I would be so long.

[00:38:41] **Ben:** yeah, I agree.

[00:38:42] **Carol:** Well, I mean, I wonder if she fully steps away or if it's like kind of what I had done more, I'm like, okay, I'm half and half, like spending half the time doing customer roadmapping and engagement things. And then half the time still writing some of the codes. So I'm not fully out of it, so I can still help, but I went, so I kind of went through the phases of really enjoying it.

[00:39:07] **Carol:** I'm just writing code to really enjoying the team to then going back to like managing the team and being over teams to, to going back to it. I really just like being on the team again. I like it just like, I get to make decisions on where we're taking the product. I still get to, to have a lot of input and everything, but I don't have to with budgets and I don't have to hire, I don't have to fire.

[00:39:30] **Carol:** Like we did this like peer review this year. So for our career conversations, it was like, Hey, here's a list of everyone on your team. Give us feedback on them, like, go review your own teammates. Like to me, that's better than any manager review that I've ever gotten to have my team give me those reviews.

[00:39:48] **Carol:** So I think I'm back to the point in my career where I really just like being on the team. I don't, I don't want to be over people.

## [00:39:56] Keeping up with your Growth

[00:39:56] **Adam:** So if I could take us back to, I don't remember who said it, but we were talking previously about promotions and like title versus money.

[00:40:06] **Adam:** And, And some, I just had a couple of thoughts around all of that, that I wanted to throw out there.

[00:40:11] **Adam:** So, the whole point of promotions and a pay increase and the title I think is, there's, I'm sure there's a lot of aspects to it, but like a it's to recognize you for continuing to grow in your career, be it's to give you an incentive to stick around. Right. And see, I think it's also.

[00:40:35] **Adam:** Did I do like a B2C, whatever.

[00:40:38] **Tim:** Sure it

[00:40:39] **Adam:** then it's to keep it interesting for you, right? To keep challenging you. And I think that as long as you're getting what you need out of the job, and that includes enough money, and whatever's important to you, whether it's challenge or recognition or a title, you know, everybody's different, everybody's motivated by different things.

[00:40:59] **Adam:** If you're getting what you need then there's no reason not to stay where you are. Right. Like you don't need to quit your job just because you haven't gotten a promotion in five years. But if you haven't gotten a pay raise in five years and you're you feel like you're falling behind you know, your peers and whatever, you know, you're struggling to make ends meet then.

[00:41:18] **Adam:** Yeah. I think it's time to look for a new job, but sort of the same. Or the other side of the same coin is like, none of those things are necessarily required. And so like, okay, maybe they're on a really small team. There's no room for a principal engineer sort of thing. But as long as you're getting enough money and the right kind of recognition on your team then it's fine.

[00:41:41] **Adam:** And you may be perfectly happy at the other side of this coin though, is if there's no room for you to get a promotion, but you feel like you deserve something, then that's a totally legitimate reason to leave

[00:41:53] **Adam:** and go get another job somewhere

[00:41:55] **Adam:** else. Like, just because my company hasn't grown at a rate that can support me leveling up doesn't mean I haven't leveled up.

[00:42:04] **Carol:** I agree.

## [00:42:05] The Peter Principle

[00:42:05] **Tim:** No, I would say that the double-edged sword though, of promotion is the Peter principle.

[00:42:14] **Carol:** I don't know what the Peter principle.

[00:42:17] **Tim:** So the Peter principle is it's a concept by a guy, wrote a book called the Peter principle, where basically that says that people in a hierarchy, which most businesses tend to be a hierarchy. They tend to rise to their maximum level of incompetence. So they keep getting promoted until they reach a point where they fail and actually

[00:42:38] **Tim:** had someone, either they stay there or they get knocked back down or, they, they go to another company.

[00:42:46] **Tim:** Yeah, and I actually had someone that was much way higher up in the organization. Just basically call out that I had reached my, my uh, Peter

[00:42:54] **Tim:** principle.

[00:42:56] **Adam:** That's

[00:42:57] **Tim:** Yeah. I was not too, not too particularly happy with him at that point. Cause yeah, I was just going through a lot, my personal life at that time. And so my life was, my life had gone to crap.

[00:43:06] **Tim:** And so what had nothing to do with my competence, it had to do with just my concentration at that point. But but yeah it's just like wanting to constantly be promoted if you're a person who feels that that's what you are gauging your success as be careful because eventually just going to reach a point where they're going to continue to promote you to a point where they put you in a job that you have absolutely no right to be in and you're right.

[00:43:35] **Tim:** And it's going to be humiliating and hopefully you recover from it. I did,

[00:43:39] **Carol:** Yeah.

[00:43:41] **Tim:** I did. And I'm much happier now. And I, and now I know my strengths or weaknesses, and that's why I've, I've made the decision. Look, I am not going to be a CEO / GGGM. That is not where my strengths lie.

[00:43:53] **Tim:** I know where my strengths lie. I know how to build stuff. I know how to help a team build stuff. And I know how to talk to customers to get what they need out of it and deliver that to them. And that's what I want to do.

[00:44:08] **Ben:** Yeah, it's funny. So at work. Peer reviews. So I think we do in biannually where you have to review several other people and then they review you not necessarily the same

[00:44:19] **Carol:** You love it.

[00:44:20] **Ben:** And, and I had to review my, my director. And I said, in my review, I was like, you need to not worry so much about my career because he's definitely a, like, what's your growth path look like?

[00:44:32] **Ben:** What does your career look like? You know, how do we keep you moving forward? And I, I, in my view, I'm just like, I got customers, those customers have problems today. They're gonna have problems tomorrow. They're gonna have problems the day after that, like I got things to do. You don't have to worry so much.

[00:44:49] **Carol:** When I run out of the things, I will let you know.

[00:44:51] **Ben:** Yeah. But I think it's, it's that sort of, I get my high out of helping the customers very directly. And like, because he's not there doing that with me, I don't think he necessarily understands how rewarding that.

[00:45:05] **Ben:** And so he constantly wants me on this other path. I think.

[00:45:08] **Carol:** I had someone ask what my five-year plan was at my last job. And I was like, we're kind of struggling to get through month to month right now. Like we are having a really hard time roadmapping customer needs month, month. So I'm not really for sure why we're even talking about my five-year plan because we need to focus on what's happening in the moment right now.

[00:45:28] **Carol:** So.

## [00:45:30] Book Recommendations

[00:45:30] **Adam:** So this is totally unprompted not sponsored, whatever. There's just this there's a woman who wrote a book on this topic. It's called engineering management for the rest of us. I haven't read the book, but I, she, because it's not out yet, I intend to read it. She says that a lot of the stuff that's in it has been posted on her blog and I've been following her blog for a long time.

[00:45:51] **Adam:** Her name is Sarah. And if anybody's interested in the book is called engineering management for the rest of us. And the website is E N G management.dev. It looks really good. And like I said, I've read, I've been reading her blog.

[00:46:03] **Carol:** I just subscribed.

[00:46:05] **Adam:** I've been reading her blog for a long time. And she has been an engineering manager at Netflix and she's just a really smart person and she seems to be, have a really high emotional intelligence and do good work.

[00:46:18] **Adam:** So, I'm really looking forward to this book when it does come out.

[00:46:23] **Tim:** Good.

[00:46:26] **Ben:** Yeah, I know the name. I know she either is on podcasts or she's written books, but I definitely know her just having

[00:46:31] **Ben:** trouble.

[00:46:32] **Adam:** she's also a staff writer for CSS tricks.

[00:46:34] **Adam:** So you

[00:46:35] **Ben:** that's might be it.

[00:46:36] **Carol:** Yeah.

[00:46:38] **Ben:** If I can plug a book,

[00:46:40] **Adam:** Yeah.

[00:46:40] **Ben:** this is a book that Clark Valberg recommended to me, like 15 years ago, it's called the magic of thinking big by David Schwartz.

[00:46:49] **Ben:** And it's the cheesiest. I listened to it on audio and it sounds like it was recorded in the sixties. And like you're listening to the actual cassette playback, like that's the audio quality and it's all about kind of career growth and taking on larger responsibilities. But there's just something magical about it.

[00:47:07] **Ben:** The magic of thinking big, highly

[00:47:09] **Ben:** recommended,

[00:47:11] **Adam:** I don't know where I just, I remember seeing this book cover like earlier today, I was, I was looking for new books to read for this camping trip. I'm getting ready to go on.

[00:47:19] **Carol:** Or steel

[00:47:20] **Adam:** cover

[00:47:21] **Ben:** uh, with the audio, the audio, you got to do the audio. Cause it's, it's all about the guys intonations and it's just fantastic.

[00:47:28] **Adam:** I was thinking that we should see if Sarah Drasner wants to come on and talk about engineering management uh, when maybe when the book is ready to come out or

[00:47:35] **Carol:** Yeah, that'd be great. Is that notify?

[00:47:40] **Adam:** send her an invite.

[00:47:42] **Tim:** from one published author to another.

[00:47:44] **Adam:** Well,

[00:47:45] **Tim:** Got your

[00:47:45] **Tim:** book.

[00:47:46] **Carol:** it

[00:47:46] **Carol:** I got, no, I got my Monday and so I reading it.

[00:47:49] **Tim:** got mine

[00:47:50] **Adam:** Did you read the inscription when I signed it?

[00:47:52] **Tim:** I did your heart matters. Thank you.

## [00:47:58] Patreon

[00:47:58] **Adam:** Cool. All right. Well, I guess then we're done. So let me do this thing. So like I said, we've never taken any money from any companies to say nice things about them or books or anything else. And we'd prefer to keep it that way. And we can only keep doing that because of the support of generous listeners.

[00:48:14] **Adam:** Like you, if you like what we're creating here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. In addition to the warm feeling, you get in your heart for helping us create something positive in the world. We also offer perks for our patrons. They all get an invite to our Discord server, where we hang out and chat about the podcast and work stuff and life stuff.

[00:48:34] **Adam:** And we have other perks available like early access to new episodes and our after show. Every week we thank our top patrons. And since this week is part of every week, we're sending out a huge thank you to Peter and Monte.

## [00:48:45] Thanks for Listening

[00:48:45] **Adam:** And Hey, if Patreon, isn't your thing then. Thanks for listening. Anyway, we really appreciate having you here with us. You could share the show with your friends and coworkers because let's be honest, almost nobody searches podcast directories. So we really need your word of mouth referrals to keep growing.

[00:49:00] **Adam:** And you can also leave us a rating and review on iTunes or wherever you get your podcasts. So that maybe one day we'll ring first, when you searched for the name of our podcast. Please send us your questions and show topics and suggestions on Twitter and Instagram @WorkingCodePod, or you can leave us a message on the phone at 512-253-2633 that's 512-253-CODE.

[00:49:21] **Adam:** We'll catch you next week. And until then,

[00:49:23] **Tim:** Your heart matters, guys,
