---
title: "204: Relaying Requirements"
description: "In this week's episode, the full crew is back to discuss the complexities translating user requirements to developers and the importance of clear communication to avoid wasted efforts."
date: 2025-02-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/204-relaying-requirements/id1544142288?i=1000689607557"></iframe>

In this week's episode, the full crew is back to discuss the complexities translating user requirements to developers and the importance of clear communication to avoid wasted efforts.

The conversation also touches upon the roles of project managers and developers, emphasizing the significance of a clearly defined problem statement and well-structured processes to ensure efficient project execution.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/204-relaying-requirements.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** whenever you're talking about an integration with another, like. Partner or another software like it's always so much better to like have a first call that says like we want to do this thing with this thing and let's just magically make it happen. The 2nd call should be whoever agreed to what that integration was going to look like between the other software and that company.

[00:00:21] **Carol:** And your tech people to hear what they're trying to deliver to them. And until you can talk to that company and you can read their docs and you have communication, you're going at it blind and you're just going to waste time and get burned out. Like you need communication up front.

[00:00:36] **Tim:** you're a hundred percent spot on

## [00:00:57] Intro

[00:00:57] **Adam:** Okay. Here we go to show number 204. And on today's show, we're going to talk about collecting the requirements from the users and taking them to the developers because I have people skills.

[00:01:10] **Ben:** What exactly would you say you do here?

[00:01:15] **Adam:** but first, as usual, we'll start with our triumphs and fails. Looks like it's Ben's turn to go first. We have the whole gang back together again. It's good to see all your faces.

[00:01:24] **Tim:** Welcome back, Carol.

[00:01:25] **Carol:** Hey, thanks, guys.

[00:01:26] **Adam:** but Ben, why don't you get us started?

## [00:01:29] Ben's Triumph

[00:01:29] **Ben:** sure. I'm going to kick us off with a triumph, and that is that I have recently in the last couple of weeks been just working on a little side project, and I am taking as an opportunity to question.

[00:01:41] **Ben:** Everything about how I work, but basically any kind of pattern that I have in place. I'm taking a moment to just check in with myself and ask, is this actually adding value to the way I'm building this application? Or is this just noise that is being carried through because of the momentum of how I've done things in the past?

[00:02:03] **Ben:** So as an example, just to make this more concrete, I have historically at the top of all of my SQL statements. Put a little debug comment with the essentially file path, not quite a file path, like they, the dot delimited object path to the component that contains that SQL. And the reason that I've done that historically is because we had a lot of people working in the application and people write all kinds of crazy ass SQL stuff and I look at the.

[00:02:30] **Ben:** Slow logs in the query. And I run into some query that's taken 17 seconds to run. And it's really helpful to have a little statement that it says, this is the file that this comes from. So I'm not poking through, you know, hundreds of different gateways. So I stopped and I asked myself, does this even make any sense?

[00:02:47] **Ben:** Like, when's the last time I actually got value out of this? And what I realized is that there's two different types of SQL components. There's, there's the kind of CRUD create, read, update, delete components that do nothing, but kind of insert, update, delete records. And then there's the more esoteric. I need to run this report and it joins these nine tables and it does these aggregates and has these window functions.

[00:03:08] **Ben:** And what I realized is that I was treating all of these, like they were the same degree of danger, so to speak.

[00:03:15] **Adam:** hmm.

[00:03:15] **Ben:** And I realized that for my CRUD type. Components. I don't, I don't need to debug those. Those are all based purely on indexes. They basically only look up a single record or delete a single record, or maybe a handful of records that are all based on a secondary key.

[00:03:29] **Ben:** Really, I only need those kind of debug statements in these crazy ass report queries, because those are going to be the ones that actually have the chance of showing up legitimately in a slope query log. So I just went through and I took out all of those comments. and again, it's, that's just one little example, but I've been just trying to step back and evaluate the reasons that I'm doing stuff.

[00:03:50] **Ben:** And what I'm finding is that the more I evaluate, the more I can actually take out of the code and reduce the noise and reduce the repetition and. I'm just really enjoying that. I'm really feeling good about the simplification of some of my strategies.

[00:04:04] **Adam:** And does this also tie in with some of the stuff you've been talking about on Discord lately?

[00:04:09] **Ben:** absolutely. All those things are me trying to understand. I mean, some of that is me trying to develop a new pattern, and that's why I have some of those like, I don't like the way I'm doing it, but I also don't know the way I'd like to do it. I just know that something doesn't feel quite right.but, but yes, that is all part of this question, everything and continue to move forward, but then question again and move forward and question

[00:04:32] **Adam:** Yeah. And I was thinking about that. I, I think if you take everything out of context, like if you just, if you don't think about our preexisting relationship and we know each other and we talk and you just look at the conversation that we had in discord, it's like, I came down kind of hard on you.

[00:04:47] **Tim:** Yeah, you did.

[00:04:49] **Adam:** this is just rearranging deck chairs on the Titanic, Ben. You're a terrible person, Ben.

[00:04:53] **Tim:** You're just navel gazing. Pupa. Yeah. Pupa.

[00:04:57] **Adam:** you know, like, I think the action that you're talking about doing is kind of navel gazing, but it's worth doing every once in a while. And I think that just the, the way that you talk about it and the way that you think about it, I think maybe you linger on the navel gazing a little bit longer than, than I would.

[00:05:16] **Adam:** Right. But there's nothing wrong with, like, I'm not saying that the amount of navel gazing that I do is the right amount. It's just the amount that I do. Right.

[00:05:23] **Ben:** also, you know, to be just to give it a little bit more context, more color. I am, this is a little side project that I'm working on. It's experimental. And this to me feels like it's the right time to make those kinds of questions.

[00:05:37] **Adam:** sure. Yeah. Yeah.

[00:05:38] **Ben:** Josh Ford was just saying, and as you were saying in the chat as well, like, what's the point?

[00:05:43] **Ben:** You know, you have patterns. If you're in an existing application, it has existing idioms, existing patterns, like there's no point to do questioning of how are we doing stuff for the most part. Cause a lot of it is just, you have a pattern. It behooves the team that you just continue on with that pattern so that nobody gets confused.

[00:06:01] **Ben:** They open a file and they're like, Whoa, what was this guy thinking? You know? But this is the. The kind of the nascent stage, the, the pupil, pupil, pupil,

[00:06:11] **Adam:** people is correct, but it's not P U P I L. It's like P well,

[00:06:17] **Ben:** like there's an L

[00:06:17] **Adam:** pupil phase. Yeah, yeah,

[00:06:19] **Ben:** Yeah. It's the little, the little maggoty phase of the, uh,

[00:06:22] **Carol:** that sounds awful.

[00:06:23] **Adam:** there's some A's in there

[00:06:25] **Ben:** yeah. Like this is the right time to do the questioning so that I can lay down the patterns that feel like they're going to make sense over a longer period of time.

[00:06:33] **Adam:** Yeah, absolutely. The, I think that my comments were also very colored by the fact that like not more than 99 percent of the. Development work that I'm doing is on, you know, Brownfield application, you know, patterns are established stuff is not set in stone, but pretty darn close. And, and like, that's just not the way that you approach that sort of thing.

[00:06:52] **Adam:** And so it's, it's hard for me to

[00:06:54] **Ben:** I think that's why I'm so excited about it too. It's like, cause like, Oh, like, like you. I, I, my whole life has been Brownfield applications for the most part. So this is like this exciting moment. Someone just. you know, I've unleashed myself onto a little side project and I'm having at it.

[00:07:13] **Tim:** The only issue. Not even the issue. It's just kind of a flavor I took. You kept talking about your feelings. Doesn't feel right. You know, the folders here, the doesn't. And I'm like, if you base that on feelings. Feelings are going to change, right?

[00:07:26] **Ben:** Yeah, that's

[00:07:26] **Tim:** and that's from experience, right? I'm like, I was like, you know what?

[00:07:29] **Tim:** This doesn't feel right. I need to set my folders up and name things this certain way. Cause we talked a lot about last week about naming and if you're doing it just strictly off feelings. And then six months later, you're like, Oh, that doesn't feel good anymore. Right. And it's, but it, it doesn't really matter at that point.

[00:07:46] **Tim:** Right. Your feelings be damned. You made a decision. If you keep changing it, then your feelings are gonna be like, Oh, look at this. It looks like this way, one way here. And this way it's inconsistent. Now I feel really bad. So that was the only thing you kept talking about your feelings about it. But now that you've explained sort of the problem, I get where you're coming from.

[00:08:07] **Ben:** Well, it's like, uh, in severance when they just have to stare at the numbers and they're like, we're like, look for the scary numbers. That's what I'm doing right now. I'm just looking for the scary patterns. I'm like, what's the. What's my tum tum telling me?

[00:08:19] **Adam:** even in brownfield development, there's opportunities for reorganization, right? So like we had a private node module that for years we used and it was like a, you would install this node module and then it would give you access to various config settings that were shared across different parts of the application.

[00:08:39] **Adam:** And over the years it got to a point where it was like, we, we just decided it would be better to make it a service that you like, make an API call to, to load that config from, and it's just like a, it's a API, a web, I don't know, I guess you could call it a rest API, but it just only runs inside of our production environment.

[00:08:57] **Adam:** Like it's all inside the firewall. You can't get to it from outside and everything. And, but it was the same code base. And so it had all these like. Bones of how things will be organized and compiled to be best used for both client side and server side apps where it was being installed and it's likeso like about a month ago, I just had enough of it and I was just like, you know what, I'm done.

[00:09:21] **Adam:** Like this, I'm going to cut off this vestigial tail and, and we're going to reorganize this repo. And it, it took me like all day to, to reorganize this one repository, but it's so much nicer and like, just so much less junk in the root folder now.

[00:09:35] **Ben:** Yo, and look, a day sounds like a long time, but in the grand scheme of things, it's nice to put it in perspective that nothing we really do is that set in stone. And if we want to refactor where things are, you know, even if we don't have some fancy jet brains integrated functionality, where I can just be like refactor to new component, or, you know, I'm just making up terms there, but.

[00:09:58] **Ben:** Like, you know, you could do an extended find and replace, and that gets you like 80 percent of the way there, and you gotta finagle some other stuff manually, but, you know, you just put some time aside, and anything is possible. All the clean up is possible. Anyway, I don't want to take up all of the time with my Meandering ramblings,

[00:10:18] **Adam:** triumph, the podcast,

[00:10:21] **Ben:** Corner.

[00:10:22] **Ben:** I will pass it over to Carol. Carol, how's, how's things in your world?

[00:10:26] **Carol:** Oh, my God, do you really want to know we won't we won't go too deep into it.

## [00:10:31] Carol's Triumph

[00:10:31] **Carol:** I'm going to go with a giant triumph and that's just that I haven't been fired yet.

[00:10:36] **Ben:** Nice. Congratulations.

[00:10:38] **Adam:** you like to, would you like to add some context for why that's a triumph?

[00:10:41] **Carol:** Yeah, yeah, yet being like the key term here. So if you're following the news at all, there's a lot going on with federal employees right now and the civil service and people working and there's just a lot of uncertainty and unknowns about like, what our future looks like. As civil servants and as federal employees.

[00:11:03] **Carol:** So part of my problem is like I'm remote. I'm a military spouse like going back to the office and a forced return to office mandate doesn't really fit my family. And if I have to choose between living with my husband and moving to an office, that's a plane ride away. I'm going to choose my husband, you know, like that's going to be what I do.

[00:11:24] **Carol:** but it's just, it's unsettling most days to just not know, like what direction we're going, and not having answers. So the yeah, it's because I feel like if I just assume it's going to happen and then I'm not so shocked when it does and I'm just ready to move on. Yeah.

[00:11:43] **Tim:** for, for context, if listeners don't know you work for OPM, which until actually this, like last week, I didn't realize it was a government. I didn't work for the government. I didn't realize it was like a government agency as big as it was the office of personnel management, which is. I mean, I was listening to NPR and they were talking about that.

[00:12:02] **Tim:** I mean, people right now are outside the OPM building protesting Elon Musk and his minions, like seemingly,

[00:12:10] **Carol:** So great.

[00:12:11] **Tim:** I don't know. Carol's not there. No, no, no, no. She's not there. She

[00:12:15] **Adam:** I was saying they're protesting Carol.

[00:12:16] **Carol:** know.

[00:12:18] **Tim:** at protesting like this. It seems like a hostile takeover of the civil service by, by, you know, the, the doge department.

[00:12:25] **Tim:** So, I mean, it's gotta be, I can't imagine how scary it is to work there right now.

[00:12:31] **Carol:** Yeah. It's kind of crazy. Like not even talking about doge in general, just if you read through fed news or you're looking at people's comments, like they blame us at like my agency for the things that are happening, but in reality, like OPM, the office of personal management, like our job is to kind of almost handle the HR side of things for the government.

[00:12:53] **Carol:** Right. It's. Executive order comes down our agency then provides the guidelines to the other agencies on how to follow these EOs. Like, we have to follow them to like, we're not exempt from the return to office. So, what we're putting out causes us to lose very talented people to, like, it's not just us, but then when you read the post, it's like, oh, is the evil actor in all of this.

[00:13:19] **Carol:** And all we're doing is doing exactly what we're supposed to do, which is follow the law and. Do what the president tells us to do and, you know, do the best we can. So there's definitely a lot going on. I mean, I feel like with every presidential trend, like a transition, you have someone from the other side that's not happy.

[00:13:39] **Carol:** And there's always going to be those kinds of like protests that happen initially that they're fighting something, but I feel like there are more now. and maybe they're more visible to me because I'm seeing them as federal employees are participating in them. Right. Like they're actually standing outside their agencies complaining and they're like protesting what's happening and it kind of just cuts me a little more.

[00:14:01] **Carol:** No,

[00:14:02] **Tim:** don't think this is,

[00:14:03] **Carol:** this has been a different one.

[00:14:04] **Tim:** yeah, this is like, no one's ever heard of OPM

[00:14:09] **Carol:** Unless they listen to our podcast.

[00:14:10] **Tim:** Exactly. Let's say they are. Yeah.

[00:14:12] **Adam:** I mean, if you're a, if you're like a big West Wing fan, you'll know what OPM is. But

[00:14:16] **Tim:** Yeah. Well, I'm glad you haven't been fired

[00:14:19] **Carol:** Thanks.

[00:14:20] **Tim:** and I hope things calm the hell down that, you know, they just, everything chills out a little bit

[00:14:26] **Carol:** Across the board. Right. Like, my heart just hurts for so many people right now that are going through this time and just doesn't. We don't have answers. People don't have answers and that's all you want is just to know. You just want to know.

[00:14:40] **Ben:** on a, on an Elon Musk related note for a second, did I, I saw some headline that is he canceling the Cybertruck?

[00:14:47] **Carol:** Oh,

[00:14:48] **Adam:** I

[00:14:48] **Ben:** that a thing?

[00:14:49] **Carol:** so that's interesting because I saw someone post something that the value of the Cybertruck is now like 00 cents and I didn't really go back and reference like what they were talking about, but I wonder if that's related.

[00:15:02] **Ben:** think they. I think they're canceling or yeah, I think they're no longer doing production of it or something. Anyway, sorry.

[00:15:08] **Tim:** it's not a good looking car.

[00:15:11] **Carol:** I know it's so ugly. Yeah, it's so she like cut.

[00:15:15] **Tim:** bought it.

[00:15:16] **Carol:** No,

[00:15:17] **Tim:** a few around town, like, I appreciate you guys buying that so I know who to stay away from.

[00:15:23] **Carol:** do you remember several years ago when the Hummer came out and people bought them and then we're like, oh, we can't drive them because we can't afford the 2 mile, like, per gallon gas thing that it gets. Right? So then you just stop seeing them. I feel like that's how cyber trucks are going to be. It's just going to be this random 1 off.

[00:15:40] **Carol:** You're stuck with it and someone's going to have it, but they're not going to be a mass. Yeah.

[00:15:45] **Adam:** mean, to be fair, at least it's not a PT cruiser.

[00:15:48] **Carol:** Oh, man.

[00:15:49] **Tim:** or, an Aztec.

[00:15:51] **Adam:** Oh yeah, Pontiac Aztec, eh?

[00:15:53] **Carol:** Oh yeah, those got a bad rep, big time.

[00:15:56] **Adam:** We are way off the

[00:15:58] **Tim:** Oh,

[00:15:58] **Carol:** I have a job, yay!

[00:15:59] **Tim:** Yay.

[00:16:00] **Adam:** Good job and and honestly a double triumph because that's a great perspective to bring to it

[00:16:05] **Carol:** yeah, did the best. Yeah. But anyways, what about you, Tim? What you got going on?

## [00:16:10] Tim's Triumph

[00:16:10] **Tim:** Well, I got a Triumph. Yay! We gave somebody else a job. Um,so, those, those of you who didn't see it on Discord, we, I talked about this earlier this week, but, starting Monday, we hired, the son of Scott Strohs, so if you, if you're a CF person who's around any length of time, you probably have heard of Scott Strohs.

[00:16:30] **Tim:** You know, regular public speaker and

[00:16:34] **Adam:** friend of the pod

[00:16:36] **Tim:** of the pod.

[00:16:36] **Ben:** He's, he's also a podcast host himself these days. He, there is,

[00:16:41] **Tim:** before called CF hour

[00:16:43] **Ben:** so there is a MySQL podcast now called Sakeela Speaks, I think is what it's

[00:16:49] **Tim:** And he has a huge cause now that's his job, right? So he's a, he, he's a developer advocate for, for MySQL. But anyway, so his son, finished his four years. He's got his, he's working on his master's, his son, Scott actually contacted me and said, Hey, my son's looking for a job.

[00:17:04] **Tim:** Can you help, you know, help me out? I'm like, sure. All I did was recommend him. I mean, and, but his son obviously very much impressed everybody. And, so yeah, he started on, on, on Monday and he get, I told him, I said, you know, if you see my name next to some cold fusion code, just remember it was many years ago. And I was doing what I thought was best at the time

[00:17:26] **Carol:** was following my feelings.

[00:17:28] **Tim:** I was following my feelings and I was probably stole 20 percent of it from Ben Nadell's dog blog.

[00:17:34] **Ben:** Just remember to respect your elders.

[00:17:35] **Tim:** exactly. And I got you hired. So, yeah, so he started. So that's pretty cool. It's, it's, kind of interesting to see the next generation.

[00:17:43] **Tim:** My son will be graduating. Probably in the next six to eight months. So hopefully I can find it. Maybe Scott owes me now. Maybe my son go work for my sequel

[00:17:53] **Carol:** that would be cool. Yeah.

[00:17:56] **Tim:** So, yeah, that's my try up it but yeah, he's super happy super excited. He's got a lot of enthusiasm I just can't wait for the world to beat him down,

[00:18:06] **Carol:** I just, I can't help but feel really old when you say this, like the fact that our friends, kids are now being employed by the companies we've worked or worked with as like what we started out as I'm like, where's that retirement button? Right. Like, am I

[00:18:24] **Tim:** I'm, I'm closer to it than you are, but yeah, you talk about that. So I, I, I remember, I think Scott's son was so back in 2010, the very last CF United, which was a cold fusion conference that was big and popular for many years. But the very last one, it was at a really nice resort in somewhere outside of Washington, DC, great place.

[00:18:44] **Tim:** I took my family, took my kids. A lot of guys brought their kids. I know. Ray Camden brought his I think Scott brought his so our kids were all playing together in the pool little bitty guys at the Time and now they're getting you know, their very first jobs out of college. So yeah Yeah, it did make me feel very very old and he calls me sir, and I'm like stop that stop it.

[00:19:07] **Tim:** Stop it right now So that's me.

[00:19:12] **Adam:** Call me skibbity Tim.

[00:19:13] **Tim:** Yeah. Yeah, skibbity toilet Tim. All right. How about you Adam?

## [00:19:19] Adam's Triumph

[00:19:19] **Adam:** Oh, well, I guess I'm gonna have to round it off nice and even with four triumphs. I am very happy to report that for calendar calendar year 2024 My company has already completed our PCI, SAQ, AOC, ROC, all of that, for thanks very, very much in large part to, the auditing firm that we've been working with.

[00:19:42] **Tim:** They've been much better. And not only have we completed PCI, but SOC 2 is like just around the corner. And I'm talking within a couple of weeks, we should have it completed. That's a huge lift

[00:19:53] **Adam:** it is, considering it took us like. Eight months or six months last year to get the previous calendar years one done. It's just, Oh, it's going to be a huge weight off my shoulders.

[00:20:04] **Adam:** I'm so happy. You know, part of it is the auditing company. They're just much better, better organized, and they stick to the schedule that we laid out in advance. Part of it is I came into this. Process with a lot more experience now, so I was better prepared to provide them what they needed and we had some had policies in place.

[00:20:22] **Adam:** So it didn't take me as long to get the policies updated for the new year. And, you know, there's tons of little things, but they all add up. it's just I'm I'm very much looking forward to, like. Going into March, knowing that we're already, we have our compliance for 2024 completed and we're already on the path to have like, well, you know, it's a treadmill, right?

[00:20:42] **Adam:** It's like, we've just become content creators for accountants basically. and, so now instead of, creating a new YouTube video every week, we have to like stay on top of PCI requirements and SOC 2 requirements. so that's it. pretty easy, but, just very.happy about that

[00:20:59] **Ben:** Very

[00:21:00] **Carol:** I guess, I guess with the current status, then, we won't be getting like weekly updates on PCI changes for the next year of podcast recordings. You hope to cut that down a lot.

[00:21:11] **Adam:** Yeah, yeah so actually you know when I made my list of goals for this year's like The normal stuff you would expect to see and then one of the the items on the list was just like a a stress free No change year of compliance like we are compliant and we shall remain compliant Like there's there's checkpoints you have to hit along the way and i've got those like on my calendar and on my checklist I've got things that are going to send me Notification emails and stuff to say like, Hey, it's time to go run this report or do this.

[00:21:38] **Adam:** Like, just it's stupid. There's so many requirements that are like, you have to look at this document that you previously wrote and make sure that it's still okay. As is right. We have a, we have a document that is a matrix of staff access, right? So these are the applications that we use. And these are our staff that we add in a new staff.

[00:21:57] **Adam:** Did we terminate anybody? Did we add or remove any applications? And then the, the values of that matrix are like, who has what access to what application? Is it all still correct? Which 99 percent of the time it is. And it's good. Like, I'm not complaining. It's good to have it, but to be forced to do it like four times a year, even though my company is seven people and

[00:22:18] **Tim:** a lot of turnover. Yeah.

[00:22:19] **Adam:** right.

[00:22:20] **Adam:** And it's like, okay, yeah, check done. But it's just annoying to, Have to stay on top of that.

[00:22:28] **Tim:** Which, which version of PCI were you? Was it 4.0? The new one,

[00:22:32] **Adam:** yeah, so we did three, five or no. yeah, we, we did four. Oh, for, for this, for calendar 2024, there are a bunch of requirements that don't actually, they remain quote unquote best practices for now. And then it's like March 31st or something. They become required. so we're, we're, we're In good shape to be ahead of the ball or ahead of the game for all that stuff.

[00:22:56] **Ben:** Yo, as a, as a quick aside, having nothing to do with anything you just said, other than, other than you said, calendar year 2024, Young people will not remember this, but people of our age might remember that there was a movie called Braveheart, which came out, I think, like 25 or 30 years ago

[00:23:13] **Adam:** Speaking of being old, go ahead.

[00:23:16] **Ben:** So in that movie, in like the last battle scene,Mel Gibson, he's doing a little voiceover and he says something like in the year of our Lord. Whenever it was 724, like, you know, Scotsman stormed the whatever. And they fought like warrior poets. They fought like Scotsman. They won their freedom. And I thought the phrase in the year of our Lord was just some dramatic thing that he was using.

[00:23:36] **Ben:** And literally every time I've ever heard anyone else say that, I thought that they were referencing Braveheart and literally like two months ago. I was just, it struck me that I didn't know what AD stands for in, you know, it's like, you know, 2024 AD literally AD means in the year of our Lord. I didn't know that.

[00:23:58] **Ben:** So

[00:23:59] **Tim:** I know. Domini

[00:24:00] **Ben:** I just, you know, things you, you thought were based on movies are actually based on something totally unrelated.

[00:24:06] **Carol:** Yeah, this reminds me of the time that you learned fish tacos were a real

[00:24:11] **Ben:** Yes. Or

[00:24:17] **Carol:** Yes. Yeah.

[00:24:24] **Ben:** Life is about living and we're learning as we go.

[00:24:28] **Tim:** You, you keep living it, buddy.

[00:24:30] **Carol:** And sharing with us.

## [00:24:32] Communicating Requirements

[00:24:32] **Adam:** Yeah. So, alright, that brings us around to our topic for the day, basically, as I mentioned at the top of the show, we're talking about collecting the requirements from the customers and taking them to the developers because the developers can't talk to the customers. Obviously, they don't have people skills.

[00:24:46] **Adam:** We have people skills. I don't, Carol, have you been getting the reference?

[00:24:52] **Carol:** No, I just fake laugh.

[00:24:53] **Ben:** Oh no, Carol.

[00:24:56] **Adam:** Office space. Um, one.

[00:25:00] **Ben:** Yes.

[00:25:00] **Tim:** got it. You got it.

[00:25:03] **Adam:** okay. Anyway. Tim, you, you kind of brought this to us. You, you have, some particular troubles you're going through.

[00:25:09] **Tim:** Yeah. So, I mean, am. to day work, we have a very small team, so it's like, the requirements is usually I'm just like, a customer wants to do this, I, I put a title on a ticket, tell, you know, the few people that I'm working with, like, hey, here's what they want to do, you know, here's some specs, and if they have a question, if you have a question, call me, right?

[00:25:29] **Tim:** So that's, that's pretty straightforward, but I've been consulting with a much larger company that's part of our, our, our Family portfolio and trying to figure out just where the slowdown is, right? They have a huge bucket of work, right? They have lots of customers, huge bucket of work. And their problem is just getting it done, right?

[00:25:49] **Tim:** Just getting that, those that work through the funnel as fast as possible. And, you know, it's just not happening. And so the natural reaction is to blame the developers, right? They're well, they're just coding too slow.but as I get into it, I don't think that's the case, right? Because, you know, they have a process where, because you want your developers working on develop, you know, building code, you try, I guess you try to specialize, right?

[00:26:16] **Tim:** So you have, so you have coders who code, you have architects who kind of, you know, design like a bigger solution. But, you know, if you're not really doing something new or transformative, you just, you know, bypass them and people work within the. Sphere that they're already working in. But then you have this thing where a customer says, Hey, we bought this product, right?

[00:26:37] **Tim:** And we need to talk to your product in the middle. And so make that happen. The customer doesn't know, right? They're, they're an insurance company in this case. They don't know anything about software, how it works. They're like, yeah, these guys say that you should be able to tie it to them and we'll pay you to make that happen.

[00:26:54] **Tim:** That's all they care about. And so you put some, you attach, you have a GR ticket, you attach a bunch of specs and everything, and I'm looking at this, it's like, so like these project managers, it's the title that they're, they're using, they look at that and They're not typically very technical people, right?

[00:27:12] **Tim:** They're a little bit technical, but they don't really understand coding. And so they look at these specs, and then, you know, how much of deciding what work needs to be done to get this done should they give to the developers before the developers take it over? And what I see happening is, like, they spend all this time trying to get all these requirements.

[00:27:36] **Tim:** Right. And they give it to developers and it doesn't make any sense. It doesn't make any sense. And now the developers confuse and now they're having to reread everything that was done. Like, like this one, the product that. This company bought basically is like a communication tool that, you know, it's a website and people can log in and get documents and do self service and be notified.

[00:28:00] **Tim:** They can sign up for for SMS messages. So when something happens on, you know, on their policy, they get a little message, right? Comes out to them. And so I'm looking at these requirements. And it's somehow turned into internally, we need to build an SMS engine to notify people sitting in SMS costs. What would you say?

[00:28:21] **Carol:** I said, oh, geez.

[00:28:22] **Tim:** Yeah. Oh, geez. Yeah. I mean, to send an SMS is it costs money. It's not a lot, but when you're getting into, like, the tens, hundreds of thousands, it adds up. And so I'm like. Wait, wait, wait, hold up. Why do you, why do you think that you need to send the message? What says this message needs to be sent? By whom? haven't stopped to ask that question. I'm like, this other company is charging thousands and thousands of dollars a month to build this thing that sends the message for them. You want to do it? I'm pretty sure if you do that, they will take that bet and, you know, let you foot the bill. So I, I don't understand, and my mind is like, well, let's just cut the, let's just cut those PMs out.

[00:29:05] **Tim:** Let's just get rid of them. They're obviously not doing their job. But then again, I don't want my developers spending all this time talking to customers. Cause one, I mean, some developers are good. Like my team is pretty good. It's a small team. We're pretty good at talking to the customer, getting, understanding what they want.

[00:29:21] **Tim:** But not all of them are. Some are, some aren't. So, I'm trying to figure out the balance here of how much should your developers be talking to customers to get requirements to understand what to do versus having an interface in between that does that for you. And how do you make that role successful?

[00:29:42] **Ben:** Hmm.

[00:29:43] **Adam:** So a clarifying question, and then maybe a, a, a dig deeper question. you said you were doing some consulting. Obviously this is within the same larger parent organization. It's not like you're, it's not a side hustle. It's within your company or whatever. you say you, do you mean you personally or like your team, the you and

[00:30:03] **Tim:** me, me personally, me

[00:30:04] **Adam:** Okay. So when you were talking

[00:30:05] **Tim:** that dealing with people that don't directly report to me, but I've been told to do whatever. I said, I'm kind of like Elon Musk coming

[00:30:13] **Adam:** Yeah

[00:30:13] **Tim:** to OPM.

[00:30:14] **Carol:** mm.

[00:30:15] **Adam:** Are you are you doging this

[00:30:16] **Tim:** I'm doging this guy. Yeah, I'm doging them.

[00:30:18] **Carol:** ha. Ha ha

[00:30:19] **Adam:** so Okay, but so the developers that you're talking about, you know, you're saying like my developers whatever but like the the company developers Are are there so do you have any sense of what their skill level is? Like are they senior developers or the juniors are they somewhere

[00:30:36] **Tim:** it's a mix. So, I mean, it's, it's not, it's a team of usually three to four people. Right. So, so some of them are very senior and they're the, typically the ones that will reach out to me and go, I don't, I don't understand what we're supposed to do here. The other guys. Or girls will just kind of spin their wheels and like, well, I'll still build this click, click, click, click.

[00:30:55] **Adam:** Yeah. So, and that's, that's, that's exactly what I was thinking about. It's like, you know, I think of a junior developer is like somebody you can hand them a spec and the spec says, you know, build a form that does this, build a service that sends this email or whatever, and they go do it. And whereas the senior developer, it's like, you know, we need to get across the water.

[00:31:14] **Adam:** I don't care if you're, if you build a bridge or a tunnel or a boat or a helicopter, we just need to get across the water and you figure out the best way to do it. and, or, or, you know, a slingshot or a trebuchet, I just got to get those in there. and, it sounds like the, the project managers that are there, like need to be thinking more like the, the senior developer mindset, right?

[00:31:36] **Adam:** Where they're, they should be the ones to say like, okay, well, we need some sort of requirements from the customer, right? You want us to accomplish what? Give us a goal. Right. You want to see this data over here, or you want to see, you know, have this action trigger this action, what, and then, you know, their job, the project managers and the senior developers work together to then either break it down into smaller chunks that the juniors can handle, and then maybe leave a few things for the bigger, the, the senior people or something, but, yeah.

[00:32:07] **Carol:** Yeah, like for, for me, the thing that I love about my team right now is the customer comes to our product owners, right? And our project, our

[00:32:16] **Tim:** Custom. Can you repeat that customer? What?

## [00:32:18] Tell Me the Problem Not the Solution

[00:32:18] **Carol:** our customers come to the product owner and the product manager for what they need. Right? And what they've gotten really good at doing is saying, we don't want you to solve our problems.

[00:32:29] **Carol:** We want you to tell us what's going on. Like, what issue are you having? What are you looking to get? Like, what do you need? And then I'll take that back. I'll come up with, like, a PowerPoint to explain to a few developers. Like, this is the problem statement. Like, this is what the customer's wanting, they have a thought on maybe using like this software to do it or this tool or this interconnection for how they're going to get the data, but you need a spike that says, can we use this data?

[00:33:01] **Carol:** Can we even interconnect with them? Right? And then if there is no, like partner solution there, and it's just make a feature, then it's okay. Now, you go solution this right? And then let's all get back together and talk about how you're going to solve the customers like need. It's not come to us with a solution.

[00:33:19] **Carol:** It's come to us with a problem. Come to us with something that you would like, and then let us solve it for you. And then your developers end up in the conversation very early instead of non technical people, making technical decisions without the influence of the people writing the code.

[00:33:36] **Tim:** Yeah, yeah.

[00:33:38] **Adam:** You.

[00:33:39] **Tim:** that. Trying to figure out because the ones that examples I've seen, I don't think they understand what the problem is. Right. What are you trying to solve? They're like, they start with, well, what work do I need to do? It's like, oh, SMS, well, let me go build an SMS thing. No, no, no, that's not, that's not the real problem.

[00:33:59] **Carol:** Yeah.

[00:34:00] **Tim:** So figure out the problem first. I just don't know who does that, right? Is it a team of people?

[00:34:09] **Adam:** well, it sounds like it, it sounds like the project got thrown over the fence. You know, the, the customer was like, here, we did a thing. We want to pay you to, to connect the dots or add the glue or whatever.

[00:34:19] **Carol:** and those are never fun to be thrown into, you know,

[00:34:22] **Carol:** like the, after the contract sign, go figure it out.

[00:34:26] **Tim:** Well, right now there's no contract yet. We're just trying to do a statement of work, right? So we're trying to build a statement of work and they can't even wrap their minds around what is actually. What work actually needs to be done?

[00:34:36] **Adam:** Well, I mean, somebody who is capable of having this conversation that we're having right now needs to go in there and, and have that conversation with the customer, like, don't bring me solutions, bring me problems, right? Don't tell me connect these two things. Tell me, what are you trying to accomplish?

[00:34:50] **Tim:** I, I'm getting the feeling that I'm going to have to wind up being that person at this point.

[00:34:55] **Carol:** possible, but use it as a chance to mentor your product. You have a product owner or a product manager, which 1 is that that you're working with

[00:35:03] **Tim:** Yeah.

[00:35:04] **Carol:** 1. Okay. Whoever it is taking this opportunity to mentor to be like, look. In the future, here's how we should deliver this, right? Like, we need to come to the team with a problem statement.

[00:35:14] **Carol:** And if you don't understand the product, like the problem statement here, or you don't understand the ask, how can you expect someone to code something that you can't even explain to me?

[00:35:23] **Tim:** Yeah. And I think you actually make a, I think a point that might be missing in this organization is that they, so they're very customer based. So you have a team that works with for a customer, right? And so there is no. Product owner in the middle. And maybe that's what we're missing. The person in the middle who basically says, all right, you're wanting to make this change.

[00:35:45] **Tim:** You it's got to come to the product owner first. And the product owner who should understand the whole scope of everything, the big picture, then gives that because the PM is just like, Oh, the customer wants to do this. We can build this. We got to give this number of billable hours so we can, you know, we can make our money this quarter.

[00:36:01] **Tim:** So yeah. And then they just like get some specs and then throw it over to the developers. And there was like, I don't know what you're telling me to do here. I don't really understand this. So maybe that's the step we're missing of a product owner who just says, you know, okay, I appreciate what you brought me, but let's.

[00:36:18] **Tim:** Let me, let us think about how to solve that first, even before we get, because, because I think they're jumping to the statement of work too fast. Right. Even before understanding what the problem is. Sometimes it might not even be a problem. Sometimes it's like, you know, the product already does that.

[00:36:34] **Carol:** And it almost sounds like one thing you said was like, Oh, we have to get billable hours. Right. So it almost sounds like they're jumping the gun on trying to commit to work just to get it in through like, Oh, this quarter's numbers, right. Or this month numbers, instead of trying to forecast a little better with these products, enhancements will be what we deliver, which will then add this much value, right?

[00:36:55] **Carol:** You're trying to commit to like right now's money, not three months down the road's money, which is also a big stressor for developers.

[00:37:04] **Ben:** I don't know if this would be feasible at all, but I know at work, one thing that the sales associates did and the customer success advocate people did was occasionally they would just record the phone calls. Like, like a, like they record the video audio calls and then they would post them somewhere or they would. In an hour and a half call, they might post three, two minute segments that say like this part really, you know, homes in on what the problem statement is and like where the friction is, maybe something like that. Something that just has more richness and depth than, than a document or a ticket could just shed some color on what is trying to be done, but you know, not everyone necessarily wants to have their calls recorded.

[00:37:51] **Ben:** So that could be an

[00:37:52] **Carol:** that's true.

[00:37:53] **Ben:** could up,

[00:37:55] **Tim:** But if you could take a transcript and then have AI kind of distill it

[00:37:58] **Adam:** my God.

[00:38:00] **Ben:** could upload it to a Google notebook and they could make a podcast about it and then you could, have all of your developers listen to it.

[00:38:06] **Tim:** Quick aside, I took last week's episode transcript and just, and just scraped it off workingcode. dev and I threw it into notebook to make a podcast.

[00:38:15] **Adam:** Was it better?

[00:38:16] **Tim:** No,

[00:38:18] **Carol:** I

[00:38:18] **Tim:** no, it's, it, so it did shrink it down. It's only 17 minutes long, but it's basically the, the woman's, the woman's voice. She's like basically reviewing like summarize what, and the other guy's like, Oh, that's interesting.

[00:38:30] **Tim:** Yeah. That's, oh, that's great.

[00:38:32] **Ben:** Yo, can you put that MP3 somewhere for us?

[00:38:35] **Tim:** Yeah, I get poppy. I got it. The tab open now. I'll send it up after the

[00:38:38] **Ben:** amazing.

[00:38:39] **Tim:** It's hilarious. Well, and then Adam made a really good point that you'd put book

[00:38:44] **Ben:** Classic Adam.

[00:38:45] **Tim:** as a guy. I don't,

[00:38:46] **Adam:** So I want to make a really good point here and that is,

[00:38:50] **Carol:** Oh yeah, we're doing a show, aren't we? Okay,

[00:38:52] **Adam:** no, I, I do. I have a thing that I want to come back to. So we've talked about this in the past and I feel like maybe this is kind of what Carol was getting at with the mentoring thing. Like. I, I have this like, it's just a metaphor that works really good in my brain of like military, like objectives, right?

[00:39:07] **Adam:** So you get like a goal, a strategy and a tactic, right? So, and those are like in increasing order of like granularity, right? So the goal is like, we want to win this battle. The, the strategy might be, we need to take this hill and this hill. And then the tactics are, how are we going to take the hill? We have to flank somebody or we have to do a pincer maneuver or whatever.

[00:39:27] **Adam:** we're just, you know, YOLO,Leroy Jenkins in with some grenades. I don't know.

[00:39:32] **Carol:** Jimmy

[00:39:32] **Tim:** Uh,Lisa, I got my chicken

[00:39:35] **Adam:** right. But like, it sounds like somehow along the process, like between the customer and the people who are writing the SOW, they just kind of got all the way down into tactics without ever considering the goal and the strategy.

[00:39:49] **Adam:** And really like. They need to come into you with a goal and then like the, once the goal is well understood, then the project manager and a couple of senior developers can like put their heads together and break that down into some strategies. And then from there, like that's when you commit to the statement of work and the tactics can just be figured out during implementation.

[00:40:12] **Tim:** because I mean, ultimately I think the developers, I mean, they just, they just want to. Do the work, right,

[00:40:18] **Adam:** Yeah.

[00:40:20] **Tim:** they'll do the work, but it's like, if they have to spend more time trying to figure out what it is, so they receive like a work request statement of work and they're like, none of this makes any sense.

[00:40:32] **Tim:** And that's so disheartening, right? They're like, they're like, they really want to. And now they're like, okay, I can, and it's not a small document that's been produced here. So it's this, this huge document. And then they're trying to wade through it and none of it makes sense. They don't understand how, and now they're like, I just basically have to redo all this work that someone else did that really doesn't is no, no value to me.

[00:40:54] **Tim:** And I don't think that the person who built it, they just, they just didn't know. Right. They weren't. They weren't solving, they weren't trying to solve the problem. They were just trying to make sure that, you know, they covered all the bases and did the process. I know there's slightly tendential. So I saw a thing that, Steve Jobs said years and years ago, that companies like get successful.

[00:41:17] **Tim:** Like he talked about IBM that they, they become sort of outdated and lose innovation and focus because they believe that the reason they got successful was because of the process. So they, they grew, they had this process and IBM, you know, back in the day, we became like the biggest process company in the world, Steve Jobs said, it's not about the process, it's about the content.

[00:41:44] **Tim:** So you can have the best processes in the world. And that seems like what. I'm seeing here is that they built this really sophisticated process to try to, you know, bring in customer requests, build a statement of work and get it done. And they have a really good process. They've they, I mean, it's very detailed.

[00:42:03] **Tim:** They have charts and everything. It's fantastic. I have no process with my small team, right? It's like so small. It's like not even worth the time of doing that, but we get a lot done on our small team.and it's like the content at the end of the day is. The code and the value that is producing value for your customer.

[00:42:22] **Tim:** And so if you have this fantastic process, at the end of the day, it just spits out this tiny little bit of code and value to your customer, and then you charge them ridiculous amounts of money for it, because that whole process costs a lot of money. They're not going to be happy.

[00:42:38] **Carol:** no, why would they be? Yeah.

[00:42:41] **Carol:** I just have 1 thing. So you were talking about this as a, like, a very specific, like, use case. Right? So, it's the integration with another, another software.

[00:42:50] **Tim:** I'm talking about, uh, I'm giving you an, an. What's the word for I'm looking for, not an example,

[00:42:59] **Carol:** and

[00:42:59] **Tim:** anecdote that explains the overall issue that I've seen. Cause it's, I've seen several

## [00:43:05] Making Calls

[00:43:05] **Carol:** yeah, well, I was just going to say that whenever you're talking about an integration with another, like. Partner or another software like it's always so much better to like have a first call that says like we want to do this thing with this thing and let's just magically make it happen. The 2nd call should be whoever agreed to what that integration was going to look like between the other software and that company.

[00:43:29] **Carol:** And your tech people to hear what they're trying to deliver to them. And until you can talk to that company and you can read their docs and you have communication, you're going at it blind and you're just going to waste time and get burned out. Like you need communication up front.

[00:43:44] **Tim:** you're a hundred percent spot on because that's sort of the first I said, so, cause I know the other company that they're talking to, cause they're also a partner of ours. I'll make it. So did, did you have a meeting with so and so and they're like, no, I'm like, why not? I mean, I, I know these people pretty well.

[00:43:59] **Tim:** You can, we can hop on a call in 30 minutes. All this would have been cleared up and no one thought to do that.

[00:44:06] **Carol:** I think I know what you need to do. You just need to hire me when I get fired to do the job.

[00:44:10] **Tim:** Yes. Come on, Carol. We'll do it. We'll do it. Put the dream team back together. Yeah.

[00:44:18] **Ben:** one time, I'm sure we talked about this on the show, feels like years ago, but I had thought that there would be a significant value add if every customer facing call had one engineer on it. And I know that's a huge time sink, but I think you could have something very informal with someone says, Hey, I'm about to get on a call with a customer.

[00:44:40] **Ben:** Does anybody have any interest on jump and jumping on with me? And I think just having someone there to offer kind of a grounding in what is possible or what is completely unknown, and then could take that information and either help guide the conversation or help guide the conversation back on the engineering side, I think it would be hugely valuable.

[00:45:02] **Ben:** Yeah.

[00:45:10] **Tim:** me and my customer care person will take an initial call with the customer. They're like, you know, we have an initiative. Here's what we're thinking of doing. And we'll just sort of get all the business reasons of what's going on.

[00:45:21] **Tim:** And then I'm like, and if they get technical, I'm like, no, this isn't the purpose of this call. You know, so, so and so, I mean, I would understand it, but so and so she's on the call and she didn't want to understand it. So let's, we'll, we'll, we'll delay that for another call. And then I'll bring the technical people on and they will have that call.

[00:45:36] **Tim:** And, and, you know, and I'll just kind of very much give the cliff notes of it and won't let the customer do it. I'll say they're wanting to do this as I understand the, the problem that they're trying to solve. It's this, this, and this. Did I get that right customer? And they go, yes. Okay, cool. So technical person, cause they usually have their nerd on the call.

[00:45:55] **Tim:** And, like, so what are the challenges that you, what are the obstacles you see doing that? Or what's the format and then, and they don't tend to be long calls. We'll usually schedule 30 minutes. We're done in 15. Most of the time. And, yeah, I 100 percent agree that I don't, I don't think that's a time suck.

[00:46:11] **Tim:** As long as you're doing your meetings well. Yes. And it sounds like you are Tim.

[00:46:14] **Tim:** Yeah. As long as you're, yeah, as long as you're doing a meeting as well, and talking about one, I, I do not like meetings that talk about multiple things. Now I know if you have a long history with a customer, sometimes it turns into a counseling session, a marriage, I call them, I call them, yeah, a marriage counseling session. I've been on calls with customers that we've had for many, many years and they're, they're dysfunctional and we don't say a word and the customer just talks to themselves. To figure out at the end of it, they're like, yeah, well, I guess we really didn't get back to you on this because we, you know, we need to, we really need to figure it out.

[00:46:44] **Tim:** I'm like, okay, bye. That was a waste of time. but yeah, if you can get in a call to with the customer and get it done quick, then you can get to the problem.

[00:46:54] **Carol:** this all assumes you have developers that are capable of talking to other humans though, so let's just be clear there.

[00:47:00] **Carol:** Not all of us have that

[00:47:01] **Tim:** well, right. And that's why I think you need another person. That's why you have the other person on the call. Typically. So I have one particular developer. I love him dearly, but he is the most blunt. Just matter of fact, he's gotten better in his older age, but yeah, he just would just say the hardest truth in the hardest way and I'm on that call and I know him and when he starts getting there, I'm like, well, okay, I'll stop him and just kind of wind it back. Yeah, I think you kind of need that, that mixture, unless you have the developers that are kind of that mix of like, like you, Carol, on your, I

[00:47:35] **Carol:** or Ben

[00:47:36] **Tim:** our

[00:47:36] **Tim:** Ben, yeah,

[00:47:37] **Ben:** but it's also it's. You have to learn. I mean, not everybody goes into, you know, when I go and I run an errand for me, it's practice. How can I talk to the cashier? How can I talk to the sales associate? You know, like I'm practicing my little people skills. You gotta do the same thing at work. You know, you get on a call, you ask all the wrong questions the first couple of times, then you get a sense of, of just how you're supposed to carry yourself, how you're supposed to interact with people.

[00:48:03] **Ben:** It's all a learning process and you can't learn unless you, unless you do it.

[00:48:07] **Tim:** Yeah,

[00:48:09] **Ben:** was, I just heard a really great quote. Ah, hold on, hold on, it's going to come to me. It was like, someone, someone fill me in here. It's like, it was like good judgment comes from bad experiences and bad experiences come from poor judgment or something like that.

[00:48:22] **Adam:** Something like that. Yeah. I feel like I've heard that before.

[00:48:25] **Ben:** like, you have to,

[00:48:26] **Adam:** Yeah,

[00:48:26] **Ben:** you have to do stupid stuff in order to learn how to not do stupid stuff.

[00:48:32] **Tim:** yeah, I look back at, you know, some of the stuff I did when I was in my mid twenties, thirties, early thirties and like, well, how did I ever get away with that and not get shot?

[00:48:41] **Ben:** Right? Oh.

[00:48:44] **Tim:** well, I think this has been helpful. I mean, I, I think you guys have, made some, some good points that opened my eyes. So I appreciate it.

[00:48:52] **Adam:** You're welcome. Anytime.

[00:48:55] **Tim:** Send me your bill.

[00:48:56] **Adam:** Yeah, invoices in the mail.

## [00:48:59] Patreon

[00:48:59] **Adam:** All right. Well then this episode of working code is brought to you by TPS reports Actually, I don't did you did you get the memo? There was a memo that we sent out We're putting new cover sheets on all the TPS reports now. I'll have them send you another copy of the memo And listeners like you if you're enjoying the show and you want to make sure that we can keep putting more of whatever this Is out into the universe then you should consider supporting us on patreon Our patrons cover our recording editing and transcription costs and we couldn't do this every week without them special Thanks to our top patrons Monte and

## [00:49:26] Thanks For Listening!

[00:49:26] **Adam:** We're getting ready to go record our after show and if you would like to Find out more about what that is. I mean, basically it's just outro is going to play we're going to keep talking one of the things that i'm know i'm going to bring up is My oldest is driving now, which is a very strange experience to give the car keys to the teenager and sit on the other side of the car, but we'll get it in the after show, just stuff like that, right?

[00:49:46] **Adam:** Sometimes it's personal, sometimes it's more of the technical stuff, but, you know, we just keep chatter going until we feel like we're done. and then we give that away to the patrons. If they're, if that's something that you're interested in, you patreon.com/workingcodepod. And, send us a few dollars a month and we will reciprocate with a few extra minutes of audio per week.

[00:50:06] **Adam:** I would love it if you would come join our discord, you can go to workingcode.dev/discord. I'll take it to all the right places. leave us a review. I know it's been a while since we've mentioned that we should probably get back on that train. You can go to workingcode.dev/review, and it will take you to.

[00:50:20] **Adam:** Apple podcasts in your region, if it still works, I believe. and you'll be able to leave a review there. We would greatly appreciate that.and I guess that's it that'll do it for us this week. We'll catch you next week and until then

[00:50:34] **Tim:** No matter what you say you actually do here, your heart matters.
