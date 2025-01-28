---
title: "084: The Architectural Support Team with Jason Henriksen"
description: "We interview Jason Henriksen who works alongside Carol as a Software Architect at Clear Capital."
date: 2022-07-20
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/084-the-architectural-support-team-with-jason-henriksen/id1544142288?i=1000570573619"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, we interview [Jason Henriksen][jason-henriksen] who works alongside Carol as a Software Architect at Clear Capital. According to Jason, every engineer does some degree of _architecture_, whether they know it or not. In fact, there's a lot of overlap between what Jason does and what your average web developer does. Which is why he calls his team the "Architecture Support" team. Their goal isn't to hand down edicts and pass out proclamations. Instead, Jason's goal is to build bridges between teams, help identify common pain points, propagate best practices, and lovingly guide the company in the right _technical_ direction.

Also, special thanks to Tim for _only asking great questions_!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[jason-henriksen]: https://www.linkedin.com/in/jason-henriksen-60b5b22/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/084-the-architectural-support-team-with-jason-henriksen.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Jason Henrikson:** I mean, we provide, Cross product ownership, especially of, the little pieces and services that aren't owned by anybody else.

[00:00:07] **Carol:** Oh,

[00:00:09] **Jason Henrikson:** you guys have all seen this, like here's a critical piece of business functionality.

[00:00:13] **Jason Henrikson:** Nobody remaining at the company has any idea how it works.

[00:00:16] **Carol:** yeah.

[00:00:17] **Ben:** Oh, too close, too close to home.

## [00:00:39] Intro

[00:00:39] **Carol:** All right, here we go. Guys. It's show number 84. And today we have a guest with us, Jason, from Clear Capital. One of my coworkers is gonna talk with us about how an architect works, but first as always, we're gonna get going with some triumphs and fails, and I'm gonna kick us off with a big, giant triumph.

## [00:00:58] Carol's Big Giant Triumph

[00:00:58] **Carol:** I've been out for like, you know,ever actually three weeks. Yeah. You hadn't know this

[00:01:02] **Adam:** We didn't

[00:01:03] **Tim:** Nah, didn't notice

[00:01:04] **Carol:** I kind of got married it

[00:01:07] **Ben:** Congratulations.

[00:01:09] **Carol:** is so great. I'm so happy. Our honeymoon was amazing. I needed some downtime. He needed a break from work. He works a crazy job and it's super stressful and just has a lot going on. So we needed to rest.

[00:01:21] **Carol:** So it was nice to just be in a hotel room and watch Netflix and go eat breakfast and watch more Netflix and then walk around on the beach and take a nap with no stress. It was just, it was the best I need the honeymoon more often or just vacation. I don't

[00:01:35] **Tim:** you go.

[00:01:38] **Ben:** exciting.

[00:01:38] **Tim:** That's awesome. Yeah. I saw lots of

[00:01:42] **Carol:** Yeah, we did. And the wedding went good. So everything's great. Yay. So triumphs for me. what about you, Adam? What you got going. Have,

## [00:01:50] Adam's Triumph

[00:01:50] **Adam:** Well, I guess I'm gonna go with a triumph. this is probably the source of my sounding a little bit off this week. I am currently on a camping trip with my family. We took an extra long weekend. And just get away for a while and we're camping about five minute drive from a place called Clyde peelings rep to land.

[00:02:08] **Adam:** It's just this big, like reptile zoo. and one of my kids has been it's like my kid found the place and he is been begging us for years to take him here. and it's like just far enough away that it's not really a good day trip thing. So we finally found a campground that's nearby and that's the point of the weekend is to just spend a bunch of time.

[00:02:25] **Adam:** satisfy him.

[00:02:26] **Carol:** so have you been yet?

[00:02:27] **Adam:** no, we just arrived this afternoon. Set up camp, had dinner, the family's off at the pool and I'm here with you. Lovely people.

[00:02:37] **Tim:** reptile pavilion. That sounds like my worst nightmare.

[00:02:42] **Carol:** ask you something. When you camp, do you do like a camper or like a popup thing or do you pull out the tents and make the kids start a fire?

[00:02:49] **Adam:** we have, I've I have look, listen, I'm an Eagle scout. I have done my,I've paid my dues in terms of sleeping on the ground.

[00:02:56] **Carol:** but have your

[00:02:57] **Carol:** kids. That's

[00:02:58] **Adam:** no, and I tried to get them into Scouts and we did it for several years and it wasn't their thing. So we, regretfully allowed them to quit either way. so no, I, I no longer sleep on the ground.

[00:03:08] **Adam:** we have a small pop-up camper. and so it's easy to tow behind my truck and, take it all over the place. So we try to take it out many times a year.

[00:03:18] **Carol:** what I wanna do in a few years. Sounds great.

[00:03:20] **Tim:** good. I hope you guys have a great time.

[00:03:21] **Adam:** thanks. We're working on it. I don't have the document up, cuz I'm just on my phone here, but I'm gonna guess, so Ben, I'm gonna throw it over to you. How about you man?

## [00:03:27] Ben's Triumph

[00:03:27] **Ben:** Yeah, absolutely. I'm gonna go with a triumph, which is that, I've been living in spa world spa as in single page application world for the last like decade. And, sometimes you get so mired in that world, you forget that you can just post data back to the server with a regular form post. yeah, it's crazy.

[00:03:48] **Ben:** and I started to build some forms with actual form post back to the server, and I feel like I was doing some pretty clever stuff. and I, the triumph is just sort of the remembering that there are simple ways to do things sometimes that are very effective and you don't need to boil the ocean all the time to get work done.

[00:04:06] **Ben:** So, I know I just felt,like a return to my roots a little bit. And

[00:04:11] **Adam:** I don't wanna throw shade, but isn't that the new framework called remix, it's just, they, it's a web server.

[00:04:17] **Ben:** it's so funny too, because there are all these podcasts lately about. Spas versus multipage applications, MPAs. And then at some point they go multipage applications, the way we've always done it, but, you know, just has a fancy new, modern term to it.

[00:04:32] **Tim:** That's all you need to get something popular, just give it a better term.

[00:04:36] **Ben:** exactly. So I don't know. I just felt good about that, but, triumph for me. How about you, Tim? What do you got going on

## [00:04:43] Tim's Triumph

[00:04:43] **Tim:** Well, this is my short week. We get two days off or fourth. So I was off Monday, Tuesday. So this is only my second day back to work, but, I could really get used to a three day work week. I think let's make this happen. I've been pretty productive the past two days. And, yeah, got a lot done, felt rush VE maybe I just needed time off.

[00:05:00] **Tim:** Cause I didn't, I just the microphone, maybe I just needed the time off cuz I got a lot more done past two days than I normally do In the four days, it would normally be so feeling good about that. but yeah, that's me

[00:05:12] **Carol:** I will say, typically, like, whenever you take a few days off, you're like, oh, when I go back, I've got so much to do. But when your whole company shut down for the two days, then there's nobody else working. So you get to just relax and know that coming back in. There's no two days to catch up on.

[00:05:25] **Carol:** So that's great.

[00:05:25] **Tim:** yeah. that is a nice feeling. And it's like Tuesday, I was kind of walking around the house, going all right. I feel like I should be doing something. So actually when I got in Wednesday morning, I'm like, oh good. I finally got something to do. Cause I like it. Wasn't gonna go anywhere. I really didn't have any big projects I was working on.

[00:05:40] **Tim:** So I was like, I'm like Tuesday evening. You're like, yeah, I can't wait to go back to work tomorrow.

[00:05:45] **Carol:** Yeah. So Steve's been on leave since the day before the wedding. So he doesn't go back to work until Monday and yesterday he hit his point. He cleaned the entire house. It's just up fixing things, putting things in walls, like just doing any project he can, he's like, I'm bored. I need to go back to work.

[00:06:03] **Carol:** I think this is too much.

[00:06:04] **Tim:** his paternal instinct. He's nesting.

[00:06:06] **Carol:** he's nasty. All right. So wait,

[00:06:09] **Tim:** That's awesome.

[00:06:11] **Carol:** we just have four triumphs,

[00:06:12] **Carol:** so that's really good.

[00:06:14] **Carol:** So Jason, no pressure or anything.

[00:06:16] **Carol:**

[00:06:16] **Carol:** Bring us home.

## [00:06:16] Jason's Triumph

[00:06:16] **Jason Henrikson:** I think I will. I'm gonna come in with a triumph as well A hundred percent flawless victory. No, I actually, I reached out and, made some connections with people. I actually saw a person face to face today. It was kind of a strange event. People do actually exist outside of computer screens. I wasn't really sure anymore, but it's true. And, so there's another whole section of my company that, I've just started to work with.

[00:06:47] **Jason Henrikson:** And, as an architect, you come in there and there's a title and people are like, oh God, here comes this dude. That's gonna tell me what I'm supposed to do. He's got mess. they're horrible people. Nobody wants to talk to those guys, architects, consultants, they're coming in and they're just messing everything up.

[00:07:02] **Jason Henrikson:** So it's always really gratifying when you go into someone and you can convince them that you actually can contribute and that you respect what they're doing and that you're supporting them, not just coming in and saying, well, everything you're doing is wrong because it. Probably is that way for a reason.

[00:07:16] **Jason Henrikson:** And, and it really helps when you can build that relationship. So had a hugely successful lunch today in person with a dude that I'm gonna work with pretty closely for the next year and a half. And it went tremendously well. So, so there's my try.

[00:07:30] **Carol:** Yay.

[00:07:32] **Ben:** And that's pretty amazing that you assume that things are the way they are for reasons, which it's a lot more credit than I think a lot of people will give an existing situation. So kudos to you on that.

[00:07:44] **Jason Henrikson:** Well, thank you. I think it's a, I think it's a well known fact that programmers of all stripes, they love to write and they hate to read and almost never has a programmer walked into a piece of code and said, oh, I love this. it's just, it's not in our nature.

## [00:07:59] What Is A Software Architect?

[00:07:59] **Carol:** So with that, I think it's a good transition point. Jason, you're on the show today and we're gonna talk about architecting and about your team and just about how you handle things throughout the company. So do you wanna kind of go over what you do? Like what your day to day looks like or go over what your title is first?

[00:08:16] **Jason Henrikson:** Yeah, absolutely. So, I'm Jason Hendrickson, I'm a senior architect with Clear Capital. And really what that means is that you, we have to kind of go through and say, Hey, what's going on? And from a technical direction, what are we needing to do? product managers can say, we need a product that does this so that we can make money, but it's much more difficult for especially non-technical managers to understand why we need to make various technical changes.

[00:08:44] **Jason Henrikson:** as engineers, we know that if we don't make certain changes or perform certain maintenance, there's risk that things will fall. Where there's risk that projects will take 10 times longer than they need to, because we've gotta shave a bunch of yaks before we can make a sweater. So keeping an eye on these kinds of things is really an architect's job to come in and say, we're gonna herd the cats all in the same direction, but more importantly, we're gonna make it.

[00:09:08] **Jason Henrikson:** So the cats want to go in that direction. Not that they're being forced to on pain of a severe talking to, or disciplinary action. I think that as an architect, for me, at least it's really important to convince people that they want to do a thing, as opposed to say, thou shouts do a thing because the grand PBA in the, ivory tower said so, so yeah, how's that for an introduction?

[00:09:31] **Carol:** That's a good introduction. Yeah. I like.

[00:09:33] **Tim:** I can step back a little bit and say, so, the role of architect, how is that different from the other roles on the team where you have, just a programmer or, what do we call a system analyst, things like that. How's the architect role different from those and where do they overlap?

[00:09:49] **Jason Henrikson:** Well, I'm glad you said that about the overlap, because I think there's a huge amount of overlap. I would say that every engineer on the team does some level of architecture. And in fact, my team is not just called, the architecture team. We specifically named ourselves the architectural support team. And I think that's key. Our job is not to come in and do your designs for you. Our job is not to come in and say, you have to use these tools because we think it's best. Our job is to come in and support your architecture by saying, Hey, here are some opportunities that you might take advantage of.

[00:10:23] **Jason Henrikson:** Here are some pitfalls that other teams have seen. I really consider my team to be responsible for building bridges between the teams to facilitate best practices between them. So I can come into a team like the one that I'm talking to today and say, all right, you guys are doing a bunch of data and analytics work on a critical service, but that team didn't have the context to realize that we have a, we have an absolutely unbreakable SLA with an external client to the tune of, if we break our SLA, it costs us at least $20,000 a day until it's fixed. So without that context, it's pretty hard for them to know what they have to do. And of course, nobody, had any way of telling them. So as an architect, I, well, yeah, I mean, how are they supposed to know? So as an architect, it's kind of our job to, to have a higher level view of all of the different pieces.

[00:11:17] **Jason Henrikson:** and it's interesting because I find that QA often has a broad view of different pieces. There are a lot of times where you'll say to somebody, oh, Hey, I didn't know, work like that. But the QA guy did so. Exactly.

[00:11:28] **Carol:** RQA people are the first people I go to. I'm like this isn't working. I don't understand it. I'm like guys, anybody have an answer and I can guarantee you

[00:11:37] **Jason Henrikson:** exactly.

[00:11:38] **Ben:** sometimes I feel like the only people in the company that I can trust are the people on the support team. It's like the product team tells you what they want the product to look like. And the sales team tells you how they're selling the product, but it's the support people who know what the customers are actually feeling and experiencing and where their pain points are and where their desires are.

[00:11:57] **Ben:** And just they're such a wonderful source of truth.

[00:11:59] **Jason Henrikson:** it's really true. the people that are closest down to the. the weeds, as you might say, are the ones that really know what's up.

[00:12:06] **Carol:** as part of your role, do you find teams that are trying to re-engineer something that's already been solved by another team and kind of prevent that from happening? Or would that be on the individual teams to just kind of know what's going on within the company?

[00:12:20] **Jason Henrikson:** Well, I mean the individual teams often don't have any visibility into what the other teams are doing. So absolutely. One of the things we try to do is find areas where there are pieces of, potential reuse, potential, two people going, trying to accomplish the same goal, but doing it in different directions.

[00:12:37] **Jason Henrikson:** we actually see that we have a group that does integration testing and we have to kind of review with them what the unit tests do to make sure that their separate testing isn't replicating unit tests. Cuz that can be frustrating sometimes. definitely, looking for areas where there are repeated issues.

[00:12:55] **Jason Henrikson:** And trying to get those into a centralized service. it's a big part of the gig. Absolutely. Kind of that overarching. Well, Hey, we have this a good example. I've been at a company where we have no less than four different ways of implementing business rules. How many do you need? Well, every programmer wants to build one, so

[00:13:16] **Carol:** I like my way, the best. Okay. Let me have it.

[00:13:21] **Carol:** it'll take me longer to understand your way and add what I need. Then it would take me just to build it myself, Been there.

## [00:13:28] When Is An Architect Involved?

[00:13:28] **Tim:** So let me ask then, since you are architecture support, which kind of surprised me, right? I have saw it as like what you said you don't do the sort of top down driven. Here's the architecture, everyone conform. how do you, or how do other people know when architecture support needs to get involved?

[00:13:45] **Jason Henrikson:** That's a great question. Usually we come in towards the beginning of a project sometimes even before, we've decided if we're going to do a project or not. And sometimes we come in because something isn't quite going. Right. I've spent a lot of my career as a consultant and we used to have this kind of motto that nobody calls a consultant when everything smells like roses,

[00:14:05] **Tim:** for

[00:14:05] **Jason Henrikson:** usually there's yeah.

[00:14:07] **Jason Henrikson:** There's some kind of, there's some kind of impedance, so there's some kind of a concern and then we'll come in and say, Hey guys, what are we doing? How is it going? Another thing that we do with our team is all of our architects. Spend half of their time embedded in a team.

[00:14:22] **Carol:** cool.

[00:14:23] **Ben:** That's

[00:14:24] **Jason Henrikson:** it's the only way to really know what's going on. So, like you said, with the support guy, he's the one that really sees what the customers are doing. If your architect isn't down in the weeds, helping do the coding, they only kind of know what's going on. And so that allows us to really have a good visibility.

[00:14:42] **Jason Henrikson:** So when the architect's on the team, I mean, are they just a contributor considered for that halftime? They're not like in charge, but if they do see something that they think is architectural concern, they raise a flag.

[00:14:53] **Jason Henrikson:** that's exactly right. we commit, we act as regular engineers. Really. The only difference is that the architect has the court architect team to go back to and consult with and say, Hey, these guys are doing this and those guys are doing that. Oh really? Cuz these guys over here are doing a whole different thing.

[00:15:10] **Jason Henrikson:** And then can kind of build those bridges to get people to talk. And then generally the architects have a little bit more of a involvement with the management. A big part of the architecture is helping to convince the upper management of the decisions that need to be made, you know, say, Hey, we've done this analysis.

[00:15:27] **Jason Henrikson:** We've written a write up we've broken it all down. And here's why we think this particular service is worth buying or that particular technology is worth avoiding. Does that make sense?

[00:15:38] **Carol:** It does. So like if the engineering team comes up with a solution and you go through it and you're like, yeah, that's cool. Like, you'll go to bat with like the executives and be like, Hey, like we've looked at this, we've looked at how it impacts the company. And we think this is a good decision. So

[00:15:52] **Jason Henrikson:** Exactly. Another thing the architects end up doing is something that many engineers often hate to do, and that's talking to people. Yeah, you guys on this call. I mean, I think you guys are all past that, but there, there are a lot of people that I'm even having a guy right now that I have to convince him that he wants to join the team because he's nervous about having to do the presentations and the writeups that are a part of the job.

[00:16:18] **Jason Henrikson:** a lot of engineers would really rather not do that. So

[00:16:23] **Carol:** pretty.

[00:16:26] **Adam:** I'm kind of struggling to get a concrete picture in my head of exactly what the job of architect is for that halftime, that you're not a, an individual contributor to the best of my understanding so far, it sounds like. the job is to, have a broad awareness of what's going on across the company so that you can see where people are kind of, reimplementing the same things and push them to talk to each other.

[00:16:50] **Adam:** Is there more to it than that?

[00:16:51] **Jason Henrikson:** Definitely. Although I'm glad you mentioned what you just said, because that is a really big part of it. It takes a lot of time to, to collect that information from the various teams to build them up to the point where they trust you to share that with you. But another big part of it. In fact, I have a presentation where we kind of say, what is the architecture team responsible for?

[00:17:11] **Jason Henrikson:** And, let me just bring it up. And I'll read you a couple of little bits off of it. I mean, we provide, Cross product ownership, especially of, the little pieces and services that aren't owned by anybody else.

[00:17:22] **Carol:** Oh,

[00:17:24] **Jason Henrikson:** you guys have all seen this, like here's a critical piece of business functionality.

[00:17:28] **Jason Henrikson:** Nobody remaining at the company has any idea how it works.

[00:17:31] **Carol:** yeah.

[00:17:32] **Ben:** Oh, too close, too close to

[00:17:34] **Ben:** home.

[00:17:35] **Jason Henrikson:** we had a thing where a customer exited and somebody had to be responsible for exporting all of their data onto CDs and making certain that we kept none of it. Architects got that. the metaphor I like to use is we are both the, a team and the janitorial staff. if nobody else can help we come in, if nobody else wants anything to do with it, we come in.

## [00:17:59] The Architect Team

[00:17:59] **Ben:** team?

[00:18:00] **Jason Henrikson:** we're aiming for a team of six out of, Development staff, what would you say about 150 developer

[00:18:06] **Carol:** Yeah,

[00:18:07] **Carol:** probably.

[00:18:07] **Jason Henrikson:** so,not that large, but you know, I think six people will be enough and then we're gonna see how we're growing from there.

[00:18:14] **Jason Henrikson:** In fact, we're formalizing this team in the past, the architects were really kind of more free floaters that moved from team to team, helping out as necessary kind of your wandering samurai saying, Hey, there's a need over here. We're gonna send in that guy, cuz he's not deliberately or automatically connected to a team, but by formalizing it, it really helps us to kind of say, okay, here is a resource.

[00:18:36] **Jason Henrikson:** They've got responsibility for the shared services. They've got responsibility for shared needs. So when the upper management says, Hey, I need to write up on how we could do this potential business opportunity. We don't know if it's feasible. We need somebody to help without an architecture team. Some random engineer gets pulled off of their team.

[00:18:56] **Jason Henrikson:** It distracts them from their main job. Now often you'll find an engineer who wants to do that. And those are the people that generally gravitate towards the architecture team. And, sometimes we end up putting together a tiger team where we say, Hey, the architect, isn't the guy who knows everything about this, but there's a subject matter expert over there.

[00:19:14] **Jason Henrikson:** So the managers say, Hey Jason, who is the guy that knows about this thing? I say, aha, I know who that guy is. Let's go find him, get the right people together in a room and we can build out this analysis for you. And then the other aspect of it is more of the DevOpsy side of it. We're kind of responsible for making sure that we have, high availability, security, scalability, all of the, kind of the abilities.

[00:19:37] **Jason Henrikson:** It's helpful to have a cross team view because what works in one team might have really helped another team, but they didn't know to do it. A good example of this is a little bit of logging consistency. Across many teams so that our DevOps guys can build dashboards for site reliability engineer.

[00:19:56] **Jason Henrikson:** Just as an example,

## [00:19:57] Architect Team Reporting Lines

[00:19:57] **Tim:** For sure. So, so let me ask you in your organization, who does the architect team report to and how do they metrics success or failure for the architect team?

[00:20:11] **Jason Henrikson:** that's a great question.

[00:20:12] **Tim:** I only ask

[00:20:15] **Carol:** Go ahead. Go ahead,

[00:20:16] **Carol:** Pat Pat yourself on the back there, Tim, you got it.

[00:20:20] **Jason Henrikson:** excellent. So, so I report to our director of engineering and the other architects on the team will report to me, our company does these, OKRs. So we have yearly goals for the company. And so we, as architects are responsible for making sure that the teams are moving towards those goals. We also have our own JIRA board where we say, here are tasks.

[00:20:43] **Jason Henrikson:** I had a J board task saying, Hey, we're gonna change the way we do our sprints. And it was my job to first build consensus. So we got together a team of guys from all the different teams that would be affected, brought them together, had probably 10 hours worth of meetings about these changes to our process.

[00:21:02] **Jason Henrikson:** And then it fell on me to give presentations to each team about what the change was, why we were doing it, how we built consensus and these kinds of things. So a lot of it was in this case, not even a physical artifact or a digital artifact, but just getting everybody on the same page. And when that was done, that ticket was moved into the done call.

[00:21:24] **Ben:** and then Carol's team is like, we're good with how we do it. Thank

[00:21:29] **Carol:** A good point. And that's a good part of it is that the structure doesn't quite fit what we're doing on our side. So we are not on that path yet, and we're not looking to move into a sprint model yet. So we keep doing it, how we're doing it, cuz it made sense for us to not change.

## [00:21:45] OKRs And Metrics

[00:21:45] **Tim:** So you talked about your OKRs, which means objective key results. So give kind it, it was building trust in O OKR or, I mean, can you kind of gimme more concrete example of what an O OKR for an architect team would be?

[00:21:59] **Jason Henrikson:** Well, we're trying to support the business OKRs, but if you want the specific architecture team for me there, it comes back to you. You're, I'm sure familiar with the, the five pillars that AWS likes to talk about. the operational excellence, the security, reliability, the performance and efficiency, and then the cost optimization.

[00:22:20] **Jason Henrikson:** So I, I do run ops meetings.

[00:22:24] **Jason Henrikson:** that we are trying to look at these build metrics around them. And we're pretty nascent in this. Honestly, we'd like to be a lot better where we have dashboards for each team showing us how we're doing on these metrics and showing how they trend. But even that is while it's a key part of it, the smooth functioning of the team is the main thing that, that my boss is looking for me to build out to ensure that we're trending in the right direction on all these tasks.

[00:22:49] **Jason Henrikson:** but I will say, and, you asked, kind of, you've got this half time, what goes into it? I had one of my engineers say to me, your architecture team is the kitchen sink project. And there's a lot of truth to that. everything that doesn't really fit into a specific team ends up with us.

[00:23:07] **Jason Henrikson:** And so what happens is that our delivery teams, our product teams go very deep into their product, into their technology, into their needs. Whereas the architect team goes very wide to make sure that everybody is moving kind of in the same direction and that. In general, all making good progress on our goals.

[00:23:23] **Jason Henrikson:** That was a very hand wavy question or answer. I

[00:23:28] **Carol:** And you didn't hit your

[00:23:29] **Tim:** We'llwe'll we'll pretend it did. yeah. It's just with OKRs at our company, they tend to have to be a lot more metrics related rather than, build trust, have things going well, they're very number driven. that's just the way we are. We are, but I mean, people do it all differently.

[00:23:46] **Jason Henrikson:** realistically, I think we would really like to get there. My team is really relatively new and I think that we are still building a lot of our operational competencies. We're at the point now where we know that we are very disparate in what our team's capabilities are. We have some teams that Excel in one area and another team that struggles in that area.

[00:24:06] **Jason Henrikson:** So we're trying to get more of a baseline and then it will become easier.

[00:24:10] **Tim:** right? Yeah. Once you have some baseline numbers, then you can say, all right, can we improve these let's aim to make, these logging errors, 10% less over the next quarter or that sort of thing, then you can have some metric numbers. So that's good. that's hard though.

[00:24:23] **Tim:** That first that's first thing of figuring out, all right, what do we measure? Because you show me the incentives. I'll show you the results, right?

[00:24:33] **Tim:** Yeah,

[00:24:33] **Jason Henrikson:** It's also tricky with our company, because we do have such a broad array of things that we're doing. And I'm sure this is true of many companies, but at Clear Capital engineering is really only about a third of the company. And we have a group that supports the other two thirds. We have a group that is building a mobile application.

[00:24:50] **Jason Henrikson:** We have a group that is doing all B2B data and analytics, and we have data teams that are doing, machine learning products,

[00:24:59] **Adam:** Thank

[00:24:59] **Jason Henrikson:** building shared metrics across all of those teams becomes a bit of a head scratcher sometimes. So then how do you present this to your management in a way that makes sense?

[00:25:08] **Jason Henrikson:** And we use a variety of tools, but we're definitely still getting started.

[00:25:12] **Tim:** Adam's very happy that you said machine learning and not AI

[00:25:17] **Tim:** is pet beef.

[00:25:18] **Jason Henrikson:** well, Adam, I did wanna tell you that one of our Lambdas recently became sentient and it's doing, appraisals. So that's what

[00:25:24] **Jason Henrikson:** we

[00:25:24] **Tim:** good. Yeah. Nice.

[00:25:25] **Adam:** But does it eat nuts?

[00:25:28] **Jason Henrikson:** No, no, sadly it does not.

[00:25:31] **Adam:** Okay.

[00:25:31] **Jason Henrikson:** he turned

## [00:25:33] When Does A Company Need An Architect Team?

[00:25:33] **Adam:** not at all, speaking from personal experience and mostly just trying to put myself in the shoes of some of our potential listeners who work for really small companies. maybe they have five, six people, mostly engineers, you know,the,

[00:25:45] **Ben:** very theoretical.

[00:25:46] **Adam:** exactly very hypothetical. the architecture role is really an interesting thing, but.

[00:25:50] **Adam:** I'm trying to wrap my head around. When does it make sense to start to split that out? Right? Like when you're, when the company is two, three people, kind of everybody does everything. And as the company grows, you start to specialize more. So I guess what I'm kind of asking is like, what other roles like traditional roles in a software company would have to be well established before you should start thinking about adding an architecture role to your team?

[00:26:16] **Adam:** Is there anything that makes sense to do.

[00:26:18] **Jason Henrikson:** Yep. And I think that's a great question. And realistically, I think that Clear Capital is really only now getting to the point where it's large enough, that this makes sense. We've been kind of on the cusp for a while now, but I'll give you,an answer by example. So we work with another very large company.

[00:26:40] **Jason Henrikson:** I don't wanna embarrass anybody, so I won't give any names, but let's just say they're very huge national company and we are dependent on their API. So they start giving us problems. We contact them and say, Hey dude, we absolutely have to have this API working. And one in a hundred times, you just fall on your face and it's only 1%, but it really is not acceptable for us.

[00:27:02] **Jason Henrikson:** What do we do? . And so we talked to their product owner who talked to another team, but the problem wasn't in their team and they didn't know who to talk to. So they found another team and that team didn't really know what to do. So then they tried to call the firewall guys, the firewall guys didn't have any understanding of the problem.

[00:27:18] **Jason Henrikson:** And so they spent literally weeks trying to find who owned a particular thing, because nobody knew how the entire system all worked together. There was no one person who could say this is how the pieces fit together. Each individual piece had a team that was very focused on it, but there was nobody who knew how the whole system operated together at a high level.

[00:27:45] **Jason Henrikson:** And so when your company is large enough that no one person can understand the entire operation, then an architect can come in and say, all right, I don't really understand how this particular service works at a deep level, but I understand it well enough that I can read the code that I. Intelligently comment on what it does and what it doesn't do, know who the correct people are and have a reasonable conversation about, yeah.

[00:28:10] **Jason Henrikson:** This might be a problem in there, or no, it's probably over here that you wanna look. So if your level of complexity is high enough that you can't have a small group understand the whole system, that's when you're starting to look at, okay. Do we need to have an overarching engineer who can tie those pieces together, especially for the managers.

[00:28:32] **Carol:** Yeah. When I started at Clear Capital, I didn't realize how many services inside the company my system talked to until I got pretty deep into it. And as, as I'm looking at these services that are owned by teams inside the company, there's several of them that have no owners and I'm going, but this is throwing an error back to me.

[00:28:53] **Carol:** And they're like, nobody works on it. And I'm like, oh, that's a problem. Right. I'm like someone has to work on it. They're like if you report it, you have to work on it.

[00:29:08] **Jason Henrikson:** So, Adam, you talk about a five person company at a company of that size. Every single one of you is an architect.

[00:29:14] **Carol:** absolutely. I think

[00:29:16] **Adam:** Yeah, that's kind of what I thought. Yeah. I just, I guess my, my, the overarching question going through my. And maybe you answered this when I totally didn't disconnect there, was, the O the potential other roles that need to be considered before you start to specialize off into architect and other things like what, if anything, what should come first

[00:29:37] **Jason Henrikson:** So, so there, there are a lot of roles that need to be in place. I mean, your engineers have to have product owners that they can trust. They have to have a method of doing QA. that might be automated. It might be QA staff engineers. Your data team might be necessary if you have complex data or it might be that your data can be managed and your databases can be managed by your engineers.

[00:30:02] **Jason Henrikson:** It's difficult to say, Dow must have these things before you cross the Rubicon, because there are so many variables in terms of how teams are built. It's really about, do you have so many disparate teams that team a doesn't know what team M is working on? And the management needs some way to say, Hey, how do these things interact?

[00:30:25] **Jason Henrikson:** I'll go back again to that example, where we had a team that didn't realize about an SLA, how are they supposed to know that somebody calls a service that service calls another service that service calls them. And so if they triple their response time, because they have added some new feature, some other guy on the other side of really on the other side of the state might not even be in the same building is gonna suddenly explode.

[00:30:50] **Jason Henrikson:** Those ripple effects become a bigger and bigger deal, especially as you have more and more teams and the communication becomes more and more difficult. If everybody can fit in a. You don't need somebody in that specific role, but if you can't fit everybody in the same building, probably somebody at least has to conceptually understand how the pieces fit together.

[00:31:12] **Tim:** you just build a monolith, right?

[00:31:16] **Jason Henrikson:** what could possibly go wrong. Exactly.

[00:31:18] **Tim:** tried and tested. Right.

[00:31:21] **Jason Henrikson:** no, it was actually really interesting when I first got to Clear Capital. It took months before I was even completely clear on what my part of the organization and it was because there was nobody responsible for saying like, these are all the pieces and here's how they fit together.

[00:31:39] **Ben:** I can assume you had a lot of conversations that started with you saying, Hey, can someone point me to the documentation for this? And people being like documentation for what ,, what are you talking about?

[00:31:50] **Jason Henrikson:** well, there's a, there's a Wiki that was last touched three years ago by a guy who doesn't work here anymore. How's. Carefully

## [00:31:59] How To Compromise On Solutions

[00:31:59] **Ben:** Oh, man. I, so as someone who has been both party to and witness to, I will kindly call over architecting solutions. How do you approach problem solving where there's a, there's the perfect solution that you can see in your head? And then there's the solution that maybe your engineering team is actually capable of.

[00:32:24] **Ben:** and I feel like you one way or the other is not perfect. You gotta meet in the middle. how do you compromise when you're talking about architecture?

[00:32:33] **Jason Henrikson:** carefully, is the best answer to that. one of the things that I've noticed is that, engineers continue to get stronger and stronger through their career. And then they'll find an idea that they're passionate about how it should be done. and I, myself am very much like this.

[00:32:50] **Jason Henrikson:** so as an architect, it's not always necessarily my job to say here's the perfect solution. It's my job to say, how do we get from the solution we have to the solution that we want. And that's often a whole different thing. I mean, it's easy to say, well, I've got this old system that works. I'm gonna build a new system that's way better.

[00:33:12] **Jason Henrikson:** And then we'll just all end mass jump from the old system to the new system and pray that nothing goes wrong. Absolutely not. this is one of the conversations I was having today is, if you're in a boat and you want a different boat, you can't just, break off the front half of the ship and replace it, cuz you'll sink.

[00:33:30] **Jason Henrikson:** know, it's,it's very much working on the ship while you're riding and it requires special care and that special care is often more important even than the desired future state. so, yeah, I spend a lot of my time thinking about migration plans, thinking about how do we get from the problem state to the solution state without ever being truly down.

[00:33:53] **Jason Henrikson:** I mean, you can take an outage if you have to, but if you're truly down as in it doesn't work for a big gap of time, then the whole plan gets thrown out the window and nothing happens. And you continue to sit there in, in the problem. In fact, a lot of times I think that managers don't start a project because they don't have a clear vision of how they're going to continue to operate while they get to the solution.

[00:34:16] **Carol:** That's a scary thought.

[00:34:17] **Ben:** Well, it's interesting too. I mean, you talk about migrating from one solution to another, and I think that's been for me personally, one of the biggest challenges when trying to embrace more robust, resilient, complex architectures is that I have trouble finding the incremental. It gets me there. It always feels like there's some sort of forcing function where I have to, turn the dial from three to nine before I actually start to get any value out of this thing.

[00:34:48] **Ben:** and it's very uncomfortable to do that. it'd be great to find little ways to, to tweak it here and tweak it there. And now it's a little bit more resilient. It's a little bit faster, but it's not an order of magnitude more complex or more interconnected or whatever you wanna call it.

[00:35:03] **Ben:** And that, to me just feels like the hardest part of architecture is finding that gradual path.

[00:35:10] **Jason Henrikson:** Yeah, I completely agree, but it's also really important, especially if you're going to sell the project to the management and that doesn't always mean sell that it's going to even be better. Sometimes it's sell that it's going to be safe, proving that you have truly mitigated the risk of a migration is a big part of whether or not a project is adopted,

[00:35:33] **Ben:** We've had situations where there'll be big architectural discussions may, maybe this is not necessarily strictly architectural, but there'll be big engineering discussions. And no one can come to any consensus about how we wanna do something. And then out of left field, the operations, like the COO will come in and say, Hey, this thing is way too expensive and you have a month to fix it because we're not renewing our contract with, some SAS provider.

[00:35:59] **Ben:** And suddenly it's like an all hands on deck. Everybody has to stop what they're doing. And we're not using this, performance monitoring tool. We're now using this other performance monitoring tool and has totally different kind of integration. And sometimes there's huge decisions that get made, for no engineering reason whatsoever.

[00:36:15] **Ben:** Just somebody came in and said, the wallet doesn't make sense anymore.

[00:36:19] **Jason Henrikson:** Yeah. Yep.

[00:36:21] **Jason Henrikson:** That's definitely true.

[00:36:22] **Tim:** then it's architecture's problem. And then the it's

[00:36:28] **Jason Henrikson:** But, paying attention to the wallet is definitely part of the, of my team's responsibility. Because a lot of times the engineers only kind of have a vague idea how much things cost.

[00:36:39] **Carol:** no idea.

[00:36:40] **Tim:** yeah.

[00:36:41] **Tim:** it seems low, cuz it's like a low per whatever fee, but you don't realize the scale you're operating at.

[00:36:46] **Jason Henrikson:** we once had to do an entire analysis of lames to say, okay, how many invocations per second do we have to be operating at before server less becomes more expensive than a Kubernetes cluster? And man, it can be really hard to figure that out with any kind of number that you can say with a straight face.

[00:37:08] **Jason Henrikson:** So, I mean, we spent, I wanna say a week and a half, just trying to figure out at what point does it make sense to switch over? Because there is a point, I mean, you definitely have a line. And if you're below the line, you save money. And if you're above the line, you lose money.

[00:37:24] **Tim:** Yeah.

[00:37:24] **Tim:** Cool.

[00:37:25] **Ben:** of the challenges that I've faced at work is we've had some very brilliant architecture people that are coming from backgrounds that are very different to how the current company operates. And I think they struggle to, to translate the way they're used to thinking about architecture into the new situation.

[00:37:48] **Ben:** And I've several times had conversations where they're talking about how microservices should be architected and coach should be generated, and everybody should be using like, similar services and all the services should be. Written in the same language. And then, you should be able to generate proto buff, and event CHES.

[00:38:08] **Ben:** And I'm like, yeah, that's great if that's where you're coming from. But I look at our services and we have a variety of different languages, a variety of different data, persistence mechanisms. we have like 14 different versions of node running across all of our services. We have Lambdas that you literally can't commit to because Amazon will no longer support the build of that version of node, you know, and it's,and it's hard to, it's hard to get them to come.

[00:38:34] **Ben:** It's hard to, sometimes it's hard to get them to meet the customer where they are so to speak and not think about architecture in the perfect world, but think about it in the dumpster fire. That is the reality that we're all living in right now. And.

[00:38:47] **Jason Henrikson:** And that is exactly why we're called an architectural support team, because it's very easy to get into that ivory tower, especially if you're coming from an academic background or if you're coming from a situation where you just assume that cost is no object and that time is instant and and you start to say, okay, that's where you want me to go.

[00:39:07] **Jason Henrikson:** All right, show me how to get from here to there. And then suddenly it becomes a, oh, well, we've gotta do this and this. Okay. How am I gonna do this? And this, it's very easy to fall in love with your own design.

[00:39:21] **Jason Henrikson:** It's,

[00:39:22] **Carol:** easy.

## [00:39:25] What Would You Change About The Architect Role

[00:39:25] **Tim:** let me ask you the magic wand question. So if you had a magic wand, you could change one thing about. Your role or about, other people's perception of your role, just wave that wand and it will go away and become perfect for you. What would that

[00:39:41] **Jason Henrikson:** I'm not gonna tell you that was a good question because you only ask good questions.

[00:39:44] **Tim:** be? That's a great question. Is Jason, let's get that straight.

[00:39:49] **Jason Henrikson:** Well, I think that if I could wave a truly magic wand, that magic wand would say that I will never commit an error. as an architect, you come with this title and people expect you to get it right. And so I always tried to lead with enough humility to say, Hey, this is where I think it's gonna get better, but we need to prototype it.

[00:40:09] **Jason Henrikson:** We need to prove it out. We need to make sure. That it really is better because it may well not be. I mean, I recently had a situation where I backed the wrong horse and everybody was surprised that the horse didn't perform in the way that it was supposed to, but it just didn't. And eventually we tracked down why and said, ah, look, it's a good thing.

[00:40:30] **Jason Henrikson:** We didn't commit a team of 20 guys to this for a year because in our prototyping we've found out that what all the marketing said and what all the initial analysis said, just didn't pan out. So yeah, I, I would love to be error free are free, but lacking that magic wand, I would say, check your assumptions early and often and welcome being wrong because then you learn something.

[00:41:02] **Carol:** will say typically when I go into a discussion, I think of it. I try to approach it as please poke holes in what I'm doing. Like, I am presenting this idea to you, and I want you to poke as many holes in it as you can, because I wanna see what I missed along the way, when you're coming into meetings with engineers or with the teams, do you approach it in the same way of, that you have this thought in your head, but you're okay with them poking holes and what you're trying to accomplish.

[00:41:29] **Jason Henrikson:** absolutely. I think that's, I think that's kind of the hallmark of the way a professional engineer thinks. and in fact, I'll go a little further. One of the things that I really enjoy about this job is sparring. And by sparring, I mean, we come into a room and we all bow and we all throw out our best ideas and we all cut each other's ideas apart.

[00:41:51] **Jason Henrikson:** And we say, that'll never work because of this and you're wrong because of that. And at the end, we bow again. Yeah, because our goal is not to be right. Our goal is to find the best solution.

[00:42:02] **Carol:** I love that.

[00:42:06] **Tim:** just wanna know don't any the dark horse that you back that, that failed, but I'm a hundred percent sure it was not PostgresSQL. Right?

[00:42:15] **Carol:** Postgres fan boy.

[00:42:20] **Tim:** in terms of weighing technology choices with technology

[00:42:25] **Jason Henrikson:** Nice.

## [00:42:27] Technology Choices And Support

[00:42:27] **Ben:** how do you do people, do you ever have to turn down ideas? That might be the best possible idea? The team that you have just, they're not that they're not the subject matter experts. Like, someone might wanna do Postgres, but you look at your ops team and they only know how to do MySQL.

[00:42:47] **Ben:** They only know how to do Oracle or something. You gotta say, no, we can't do Postgres. Even if it has a feature that would really solve this problem. It's just not something we can support long-term or do you let people experiment? How much, I guess, like how much wiggle room do you cut people.

[00:43:02] **Ben:** Hm.

[00:43:03] **Jason Henrikson:** So I think that I can be more effective if people are entirely behind the technology choice. I mean, I have strong opinions and I try to make them strong opinions loosely held. Now, if I know for a fact that a certain thing is going to cause provable problems, I will say, no, we really can't do it. And here's why, and all of the professional engineers will look at that and either say, you're wrong, your analysis is incorrect or they'll say, oh no, you're right.

[00:43:36] **Tim:** That won't work. And then they abandon a bad idea by themselves. What about the

[00:43:43] **Jason Henrikson:** that, that requires a different kind of solution that usually requires a management solution.

[00:43:48] **Carol:** We don't hire those kind of people.

[00:43:50] **Jason Henrikson:** But, but usually, I mean, people who really do want the best solution will come to the conclusion that yeah, this will work or this won't work.

[00:44:00] **Jason Henrikson:** But then to answer your question, absolutely. There are teams that work on things in a way that I wish they didn't, but I recognize that it's the way that they understand and that they can be the most productive with. And in those cases, usually what will happen is we'll say, okay, we're gonna continue to work with this.

[00:44:17] **Jason Henrikson:** If there is a clear benefit to another approach, then I will encourage people to experiment with that approach. And usually Wednesday, Tuesday, they kind of start migrating in that direction until one day there's an inflection point. And then. Technology that doesn't fit as well, suddenly vanishes. And I'm reluctant to mention any particular technology because

[00:44:40] **Carol:** can mention one it's okay. They won't

[00:44:42] **Carol:** get

[00:44:42] **Carol:** mad. Yeah.

[00:44:44] **Jason Henrikson:** well, let's just say that it used to be that we could only do our rules in R because all of the people we had that were doing the rules we're are experts.

[00:44:54] **Jason Henrikson:** And over time, all of those are experts are gone. And now we're like, why is all of this stuff in R nobody has how to do this.

[00:45:03] **Carol:** Sound the one person. Yeah.

[00:45:05] **Jason Henrikson:** progress. I figured that would be the least controversial of my opinions.

[00:45:09] **Carol:** all know we're dropping CF it's okay. They know we're getting rid of the CF.

[00:45:19] **Ben:** No, I guess you guys just tired of, uh,

[00:45:24] **Carol:** But that is like what he's talking about. That's where the team goes, Hey, we don't wanna support this anymore. And we think rolling off is the way we should go. And here's our plan for doing it. So we've started the process for mapping that out and actually getting a game plan going for what to do.

[00:45:39] **Carol:** And it's because we have the team that works on this. Application's buy-in to want to do it. They see that what we've written can be improved if we change a language

[00:45:50] **Jason Henrikson:** And that's a perfect example of what we were talking about earlier. Like if an architect came in a few years ago with a cricket bat and said, I'm gonna hit everybody, who's using ColdFusion until they start writing it in something else, they get massive resistance. But if they stand in a place where things are better and say, Hey guys, the water over here is really awesome.

[00:46:09] **Jason Henrikson:** And there's Palm trees, and this is all really good. Eventually the people who are doing cold food will say, Hey, you know what? I want some of the Palm trees in the ocean side over there and they'll move by themselves. I really think that an architect should be an influencer more than a,what's what's the, fascist form of influencer, you know, fascist, you know, the

[00:46:29] **Carol:** Think you said it

[00:46:32] **Carol:** well, that's all I've got for you, Jason. I really appreciate you being on the show tonight.

[00:46:36] **Tim:** it

[00:46:36] **Jason Henrikson:** I can't see how much

[00:46:37] **Jason Henrikson:** fun it is

[00:46:38] **Ben:** Yeah, thank

[00:46:38] **Tim:** very, very enlightening. Appreciate your perspective. And, yeah. Sounds like, you guys got some good stuff going on there, so

[00:46:44] **Carol:** yeah.

[00:46:45] **Tim:** for sharing.

[00:46:46] **Jason Henrikson:** Absolutely.

[00:46:47] **Carol:** Tim, do you wanna bring us home tonight?

[00:46:50] **Tim:** Sure I can bring us home.

## [00:46:52] Patreon

[00:46:52] **Tim:** This episode of Working Code was brought to you by the dumpster fire of a world that we're living in and listeners like you. If you're enjoying the show, you should consider supporting us on Patreon. It's the best way to keep the show running your donations cover the cost of recording and editing keeps all of our burps and me bumping the mic stand throughout the day, out of the recording.

[00:47:11] **Tim:** we couldn't do this every week without our pat patrons. So a very heartfelt thank you special. Thanks to our top pat patrons, Monte, and Gavin. And if you'd like to help us out on pat patron, check out pat patron.com/working code pod that's paton.com/working code pod. And we have two new ones this week.

[00:47:31] **Tim:** Welcome to Ken Wilson and Simon C Y M O N.

[00:47:35] **Carol:** Welcome.

[00:47:36] **Tim:** Thank you for supporting us. Appreciate it. So all patrons get early access to new episodes and the after show and the after show. We dunno what we're talking about, but we got a guest here. So what we promise not to be on our best behavior.

[00:47:48] **Carol:** honeymoon. Let's talk about my

[00:47:50] **Tim:** Oh boy, that's gonna get juicy.

[00:47:51] **Tim:** Okay.

[00:47:53] **Adam:** Keeping it R-rated.

[00:47:56] **Tim:** Might, might have to use a lot of quacks there. Uh,

## [00:47:59] Thanks For Listening!

[00:47:59] **Tim:** soif you can leave us a review at workingcode.dev/review, that really helps, boost our signal. And we appreciate that and you can send us topics, questions, and suggestions, either via Twitter on @WorkingCodePod on Twitter or Instagram, on our Discord, or you can email us at WorkingCodePod@gmail.com, and leave us a little voice memo there on the record it and send it to us.

[00:48:21] **Tim:** That's all for this week. We'll catch you next week. And until then

[00:48:24] **Carol:** heart matters, even the architects.
