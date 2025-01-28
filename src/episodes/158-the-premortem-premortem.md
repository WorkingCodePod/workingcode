---
title: "158: The Premortem Premortem"
description: "What's better than premortems? Premortems for your premortems. This week Carol and Ben talk about potential problems and solutions for Carol's upcoming pre-mortem session."
date: 2023-12-20
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/158-the-premortem-premortem/id1544142288?i=1000639203269"></iframe>

In [episode 154][working-code-154], we discussed the concept of a project premortem. That discussion inspired Carol to schedule her own premortem for a new 2-year project that her company is about to undertake. Given the fact that her team's work won't be sharable for at least 18-months, she's wants to make sure that her premortem is as effective as it can be. As such, we're going to have ourselves a little _premortem_ premortem discussion on the show.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-154]: https://workingcode.dev/episodes/154-what-could-go-wrong-premortems-and-log-levels/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/158-the-premortem-premortem.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** People can bring up lots of negative points, but tell me why they're actually negative to what we're trying to accomplish right now.

[00:00:07] **Ben:** Yeah. I think that'll help refocus people on things that are objectively problematic, as opposed to just very subjective. We chose the wrong programming language, or, you know, we used, spaces instead of tabs or something. Yeah,

## [00:00:23] Intro

[00:00:23] **Carol:** Alright, well, welcome to Working Code episode 158, and tonight we're going to talk more about pre mortems. but first, let's go to triumphs and fails, and being that only two of us are here,

## [00:00:56] Carol's Triumph

[00:00:56] **Carol:** I'm going to kick us off because, you know, I feel like the winner today. So I'm going to throw in a big giant triumph.

[00:01:03] **Carol:** you guys know, I've been working on kind of, as I've mentioned a few times, this chatbot project at work, and there's not a real clear, understanding of how we need to develop it to make it. Meet standards for the government, right? So I finally can say, I understand private endpoints enough that I was in the call with Microsoft and our CIO and all of the Azure smart people with networking that they thought I understood DNS and.

[00:01:36] **Carol:** I understood, like, private networks, so it made me feel good. They were like, there's no way you just got here. Like, you picked up all this stuff so quick, and you sound like an expert in how we set things up. And all I did was ask questions like, you know, does this make sense? Does this not make sense? Like, shouldn't we be able to turn that off?

[00:01:53] **Carol:** And this new way would work without your settings to work around things. And it just made me feel good that I am Stepping outside what I consider to be a developer hat, and this has nothing to do with code. This is understanding the infrastructure around, privatizing our endpoints so that they're secure.

[00:02:12] **Carol:** And, yeah, it, it made me feel good. I'm going to call it a big ol win.

[00:02:16] **Ben:** Nice. I feel like asking questions in meetings is a superpower. It, I feel like it definitely sets you apart from other people.

[00:02:24] **Carol:** Yeah.

[00:02:25] **Ben:** there's so many people who are so, I think afraid either of being judged or, or feeling like they don't know what to say or don't know what to ask, or they feel like they're going to look stupid or something, but it's, as someone on the other side of that, I feel like people who ask questions, it's always appreciated.

[00:02:43] **Carol:** It is, right? And I like to do something that my husband's taught me and I usually start with, oh, man, yeah, that's a great question. And here's what I know, or like, here's what I figured out or here's what I've read. Like, do you see the same thing? Like, your question that you're asking is completely valid and I hear it and.

[00:03:00] **Carol:** Here's why either I went this way or didn't, you know, go this way. But I will say with asking questions, someone said something in the call along the lines of, have you looked at the slash API slash token, version of AzureBot? Because we think that's what you need to be using. And I was like, oh yeah, great point.

[00:03:21] **Carol:** we absolutely will be going that route, but we're not there yet. We're just trying to get to where our connections can talk to each other, even though I'm excited. Exposing a token in the quiet. It's just in development. Nobody can get to it. Like it's really fine. and then I hover over the guy's name and it's like.

[00:03:37] **Carol:** Director of Azure, I was like, it's director of cloud services. And I was like, Oh,

[00:03:43] **Ben:** That's awesome.

[00:03:45] **Carol:** Maybe

[00:03:46] **Carol:** I should look at names before I answer.

[00:03:48] **Ben:** there must be all kinds of constraints for government work about where things can be hosted. Yeah. Yeah.

[00:03:53] **Carol:** Oh, tons, tons. So much so that if you, pull up a lot of Azure documentation, it'll say like, okay, you're going to go to this path, like, you know, azureweb. com or net or whatever, unless you're government and here's your domain and how it usually is laid out because we do host things completely private from anything else and the way they do it, the way they talk to each other, so a lot of their documentation is laid out to explain how to do it for the government, which is nice.

[00:04:25] **Ben:** Oh, nice. So, so Azure is kind of on an allow list of services that you can use to store data. And

[00:04:32] **Carol:** Azure's about the only thing I'm allowed to use in the cloud. I mean, just being honest, we have like on prem options, but we're not allowed to build our on prem anymore than it already exists because we have some directives that are we're going cloud and Azure is the way forward for us as of now.

[00:04:51] **Ben:** nice at work, we had at one point explored this idea of getting something called FedRAMP and I couldn't tell you what that stands for, but it's like a special certification that says you're the infrastructure that you use for your service is. okay for government use and you kind of get under this, yeah, you get under this FedRAMP umbrella and it sort of opens up a whole lot of other doors, but we never ended up doing it.

[00:05:17] **Carol:** so with that, I know with your software, one of your competitors is Figma, right? So, Figma, just as of recently, was on a list of tools that we are now allowed to utilize for

[00:05:31] **Carol:** designing and things. So, it, it takes a lot to get there, to get to where you're an approved software vendor, because first someone has to request it, unless they request it, then it has to go through a vetting process, then they have to get approved by the government to be, like, allowed to be on their computers and stuff.

[00:05:47] **Carol:** It's a giant process, so people don't request often.

[00:05:51] **Ben:** Yeah. And I feel like there was some sort of a sponsorship angle. Like you had to, you couldn't just apply. You sort of had to be recommended by someone else who's also in the program, something like that.

[00:06:01] **Carol:** Yeah, usually you have to be under another contract. Like you'd be like, I gotta be under a prime contract to get access to it. There's a whole lot of stuff I don't understand and I don't even want to understand and I just let it go. But yeah, to get access is interesting. Anyways, that's me. I'm gonna go with a win.

[00:06:17] **Carol:** What do you got, Ben? My only other friend tonight. Oh no.

## [00:06:21] Ben's Fail

[00:06:21] **Ben:** going to go with a fail and, I was not on the last couple of episodes. And that was because I got a really severe head cold. I don't know if my body just forgot how to fight disease having sort of been quarantining for the last three years, but I just got hit with this head cold and it knocked me on my butt and I don't remember ever having a cold this bad.

[00:06:45] **Ben:** And it just, my face was just. Leaking mucus. I mean, it was so disgusting. My upper lip was just constantly damp. I mean, it was really gross. And, usually when I get sick, if I have a head cold, my sleeping isn't really impacted. I'm usually just congested, but I can fall asleep and breathe through my mouth.

[00:07:06] **Ben:** This, I was just, I had so much. What do they call it? Post nasal drip? I was waking up like, oh, I was waking up like five, six times a night, just all of a sudden choking on something. And, and, oh, it was just awful. And that happened for a couple of days in a row and just destroyed me. and you can even hear now, I'm, I'm today, today I'm on week two.

[00:07:27] **Ben:** Yeah, I'm two weeks out from when I first got symptoms. And, I'm still congested. I mean, I'm, you know, a world better than I was a week ago, let alone even just four or five days ago. but I just have this last little bit of congestion. I can't seem to kick yet. It's really, it's really irritating me.

[00:07:45] **Carol:** So I really think that you're kind of onto something there that. Like, I feel the same way whenever I get sick, it, it takes me out a lot harder than it used to. And I always like in the back of my head, I go, is it because I'm not exposing myself to any germs? Like I work at home, I play with the dog, I work out at home, I run in the neighborhood.

[00:08:06] **Carol:** There's no people around me. You know, I don't hang out with people often. We don't even go to restaurants. We cook all the time. So the minute something gets me, my body's like. What is this thing and how am I gonna handle it?

[00:08:20] **Ben:** Oh, and, and, I'm, I'm 99 percent sure that it was Thanksgiving. Cause that's the largest crowd I've really been in, in quite a while. And there were some sick kids

[00:08:30] **Carol:** we're their little kids.

[00:08:32] **Ben:** yes, there were three little kids. One of them had this wet cough just like all night, so I'm

[00:08:42] **Carol:** probably like, it's allergies.

[00:08:47] **Ben:** So I'm I'm excited to be feeling much better and sleeping through the night I just feel like I lost like an entire week of focus and work

[00:08:57] **Ben:** and Yeah. Yeah.

[00:09:00] **Carol:** fun. Yeah, I just, my supervisor and I just had that conversation. He picked up something over Thanksgiving from one of his kids or one of his siblings, children, and. The recovery time for us isn't what it used to be. Like, even when I'm better, it takes, you know, 24 hours of still living in a fog to even feel better.

[00:09:19] **Carol:** Like it's just, as we get older, things just don't recover like they

[00:09:23] **Carol:** used

[00:09:23] **Ben:** just everything slows down.

[00:09:25] **Carol:** Yeah. It just slows down anyways. All right. You want to get into the show? Cause I really could, you know, I could, I could really talk for a bit, I guess, and would like to be heard for a minute.

## [00:09:36] Carol's Worries About Pre-Mortems

[00:09:36] **Carol:** So, uh,yeah, a few episodes ago, you talked about premortems and I had read about them and kind of like had an idea of what they were and thought, you know, some really great things about them.

[00:09:48] **Carol:** So in my on site a few weeks back, I decided to schedule my first premortem.

[00:09:54] **Ben:** Oh, nice.

[00:09:55] **Carol:** Yeah, yeah, it sounds great. And if you don't know, like, what a premortem is, it's basically, my understanding, and correct me if I'm wrong, is where you go into a project and you're like, hey, Let's all come together and figure out everything that could go wrong before we start it, rather than doing a postmortem, which doesn't really help us with our current projects.

[00:10:13] **Carol:** You know, postmortems are great because they give you the opportunity to review what's went wrong, what's went good, but it doesn't help you with what you're doing right now. So, So we've decided to come together and, have our first ever pre mortem because no one has heard of a pre mortem until I brought it up.

[00:10:31] **Carol:** So thanks podcasts for that. And they listened to the episode. So double wins, right? Yeah. So, however, I feel like people are really good at being negative and I'm worried that this is going to. This is gonna turn into me turning around and just scheduling a post mortem to talk about why the pre mortem failed.

[00:11:00] **Ben:** Well, so what do you mean that the pre mortem failed? Expand on that.

[00:11:03] **Carol:** Okay, so it hasn't failed yet because the pre mortem is actually tomorrow. However, The questions that are already being, like, directed at me and the questions I've solved appear to be leading us down a very dark path of, and, you know, it's probably not fair to say, like, it's a dark path. It's just, I think negative.

[00:11:23] **Carol:** I'm almost always the cup is half empty instead of half full kind of person. So when someone's asking, like, hey, once this process is done, who's going to own it? My brain is like, who cares who owns it? Let's write it in a way that we all understand it and anyone can maintain it. Like, that's what makes sense to me.

[00:11:41] **Carol:** Like, let's all come to a decision on what we're gonna do. Instead, the questions are like, who's gonna own this after it's done? And I'm like, oh. I feel like we're gonna get into a little battle of, some semantics here. And then I also feel like I'm very new, you know, I've only been here since the end of September and this is all riding on what feels like my shoulder.

[00:12:01] **Carol:** So I know it's not on my shoulders. It's on all of the architects to come together and make decisions, but. If nobody makes a decision at some point, I have to keep moving forward and I'm going to have to own this. And then I am the one owning it forever. And if it doesn't go well, that scares me a little, but I don't know how to put that into a pre mortem to where I can ask the question.

[00:12:24] **Ben:** Well, I think, I don't want you to put too much pressure on yourself. For the premortem, I think the goal of the premortem, the way I understand it is you want to surface ideas, or I should say maybe surface concerns that people have that may not have been surfaced without this approach to the conversation.

[00:12:44] **Ben:** So I think if people feel freedom to bring stuff up that, that might be challenging or, you know, hopefully not too negative, but, you know, accepts the fact that something might go wrong with the project, I think the premortem at that point, is a win in that you're synthesizing these ideas that might require some further investigation.

[00:13:05] **Ben:** So I, I don't want you to feel like you necessarily have to solve all the problems on the spot. I think it's more about information collecting and then you deal with it after that.

[00:13:16] **Carol:** And see, you and I are on the same page because that's how I'm going into it. Like I, we've created a retro board basically inside my sprint board. That's like, Hey, okay. Give me everything unsorted is what we've done. Like, just give me everything you can think of. And then we're going to go with what's a low priority, what's a medium.

[00:13:34] **Carol:** And then we want to pick our top 10. I just want to take away 10 things that I can go figure out, or I can get in the right hands of the right people to figure out, and then we can decide if. These are no go, like something could be a no go for this project that says we need to halt and reevaluate because the way we're going isn't going to be supported, right?

[00:13:57] **Carol:** Or we say, okay, we've covered these 10. Now we loop back over the list and go, okay, are we good to start development? Are we good to start working? Or do we need to evaluate 10 more? Like, are these high risk items going to stop development? But I feel like it's going to come into just like a nitpick kind of thing, and it's going to turn into arguments and

[00:14:18] **Ben:** I think

[00:14:18] **Carol:** I'm kind

[00:14:19] **Ben:** a

[00:14:20] **Carol:** about it.

[00:14:21] **Carol:** Yeah,

[00:14:22] **Ben:** I think probably it's always important. And I, you know, as I said on the previous episode, I've done one of these and I don't think it actually went very well, so there's only so much experience here that I have to speak from, but I

[00:14:35] **Carol:** sure.

[00:14:36] **Ben:** probably one of the important things is to always come back to the idea of why the thing that's being brought up.

[00:14:43] **Ben:** Could be a problem. You know, if someone says like, Hey, we go over our timeline or we go over our budget or, or we don't know which team is going to own this longterm. And you're like, okay, but why would that be a problem? Like, how would that

[00:14:56] **Carol:** good, good, good, Ben. Yeah. Yeah.

[00:14:58] **Carol:** That's a good way to approach it. Cause I hadn't thought of that. Like. People can bring up lots of negative points, but tell me why they're actually negative to what we're trying to accomplish right now.

## [00:15:09] Language Decisions

[00:15:09] **Ben:** Yeah. I think that'll help refocus people on things that are maybe objectively problematic, as opposed to just very subjective. We chose the wrong programming language, or, you know, we used, spaces instead of tabs or something. Yeah,

[00:15:29] **Carol:** the language thing is on my list because when they did the rewrite, our project that I am supporting is mostly in VB. So it's Visual Basic, right? So it's a dotnet language, you know, kind of easy to understand, but there was a push to go to C# fully and the decision.

[00:15:46] **Carol:** You know, I'm going to air quote this because I wasn't here for it was apparently that not enough of the developers. Writing the,application knew C#, where the majority already knew VB, so leave it on VB. So I'm pushing almost like putting my foot down and saying, there's no way this is going to be a VB, like done.

[00:16:10] **Carol:** It's X, like we're killing it and people are going to have to learn. Right. And I feel like now enough engineers know other languages that it's going to be. That's not even going to be a point, but it is on there that even though we're pushing for a new language and I'm pushing for a new language, the pushback is going to come from somewhere else that says it doesn't make sense for our, our structure to change the language.

[00:16:34] **Carol:** And that's going to be interesting.

[00:16:37] **Ben:** that's a really tough one. And as someone who has been a longtime member of the CodeFusion community, you can imagine that I've faced that type

[00:16:44] **Carol:** CFM at rocks!

[00:16:46] **Ben:** many times where people want to rewrite in Node or Go or some other language, and you have to decide what makes sense for the team. That's definitely a tricky problem because it's, it's not just about what's good for the team.

[00:17:00] **Ben:** It's also what's good for long term maintenance. It's what's good for

[00:17:04] **Carol:** For performance.

[00:17:05] **Ben:** and performance. And, and yeah, that's a, I hate that. Honestly. I hate that's like the worst question of them all.

## [00:17:14] Architectural Decisions

[00:17:14] **Carol:** Yeah, there's a lot that's going to go into it. Oh, you think that's the worst? How about this one I have myself? So, there's a push to go cloud. So, maybe I should step back. we have this big monolith application, and my goal is to take out the oldest part and turn it into a like micro service or like some type of mini service that can hopefully hold its own database and can execute, you know, its own code outside of what's happening in the system.

[00:17:42] **Carol:** So we don't have latency because what they're seeing is each request just keeps stacking, stacking, stacking. So when you have someone trying to do 40 creation or 40, 000 creations at a time, they just have to wait forever. So. my job is to take this very old part, move it to Azure, hopefully break it off to be it's own service, with it's own like connections to these other, you know, entities for connecting like some details about what you would be doing and then have his own database as well.

[00:18:15] **Carol:** So then when we're talking about like Azure, so we've went past the, if we don't know what language we're going to be in, what about, is this going to be like an app service? Or is this going to be like an Azure function that's running? Like, where are we going with it? Like, how is this actually going to execute when we're in the cloud?

[00:18:35] **Carol:** Are we talking always going? Some type of app? Are we talking something that gets hit and spins up and can, you know? Hopefully span out as needed with hits to it, like calls to it. But that's my second question. Like, is it an app service? Is it an Azure function? I don't want to decide this. Like, I don't want to be the final decision.

[00:18:55] **Carol:** I want all the other architects. There's five more of us to make this decision together. And if it falls on my shoulders, I'm probably just going to sit and cry.

[00:19:06] **Ben:** I always come back to. Local development. And then maybe this is my, lack of maybe more modern technology experience. But I always think to myself, what, what technology choices are going to make it easier to develop locally and which are going to make it really complicated to, to execute locally and, and this, I'm not an anti cloud native kind of person.

[00:19:33] **Ben:** I just, I don't have that much experience with it, but I know things like. Developing Lambda functions, which I assume is the equivalent of an Azure function.

[00:19:41] **Carol:** Same. Yep. Yep. Same.

[00:19:43] **Ben:** it's, I can't just run that locally. Now I have to have something that sort of mocks out the entire Azure stack so that I can then mock out whatever runs the Azure functions.

[00:19:54] **Ben:** And now it's like, is that a hundred percent compatible with the way it actually runs in production? And can I get a good understanding of the performances and the workflows? Is it worth the. What if I just had a, you know, a Docker service that ran and I call it a day and it works really well and I can really understand it quite easily.

[00:20:13] **Ben:** I'm not saying one of those is right and wrong. I'm just saying that that's, that's definitely the kind of stuff I would think about.

[00:20:19] **Carol:** Yeah. And that's exactly where I am. Like on my list of things, I have Docker question mark. Like, is there an opportunity to use it? I can't remember the last time I've done ground up development to where like I

[00:20:31] **Carol:** had to pick like what database were using, you know, an app service versus an Azure function.

[00:20:37] **Carol:** Like, how are these things going to work? Are we going to do a multi tenant database? Are we going to now merge into a single tenant database? There's a lot that goes into this, and there's things that, a lot of it I don't even know what to ask, because I don't know yet, like I'm still trying to figure this out, but there are people who do know, and I hope that in the pre mortem, tomorrow, they bring up their questions,

[00:20:58] **Ben:** Yeah,

[00:20:59] **Carol:** so,

[00:21:00] **Ben:** I, it is, it's going from zero to one is so hard and then going from one to 100 feels like you're solving different set of problems. Like you're already working on a known, on a known foundation at that point.

[00:21:15] **Carol:** Yeah, I, I think like my vision of this project is my happy place is once there are a few very solid decisions made, you know, like what type of service this is going to be, what language we're going to do, and then once we define what exactly is the process that we're moving, because, you know, if you have a auto policy and auto policy hasn't insured, Well, they have, like, mailing information, they have vehicles, you know, they can have accidents, like, where do your bound, like, where do the boundaries live at?

[00:21:48] **Carol:** So, I feel like once I have the boundary of what my process is, and where I can end that boundary and start connecting back to the system in other places, then I'll feel a lot better because then I can start, like, farming at work. And then I'll understand what my team needs to look like. But right now I'm being asked, like, how many engineers do you think you're going to need?

[00:22:10] **Carol:** Like, what kind of resources do you need? And I'm like, okay. I'm like, I need a data scientist because this is going to be all new data, right? And a whole new structure, possibly. And they need to help with reporting. I'm like, I need a couple BAs. I need a scrum master. I need, I don't know, let's just say four engineers because you're asking me to pull numbers out of a hat that I don't know because I don't even know what it looks like yet.

[00:22:33] **Carol:** So I feel like once. Once we have like those solid starting points, everything else is probably going to flow. It's not going to be smooth. It's going to hurt at times, but it'll keep moving. It'll at least keep moving.

## [00:22:45] Timeline Constraints

[00:22:45] **Ben:** do you have a sense of the timeline? Timeline is not the right word. How long does your boss want to allow you to work on this? Do you have a sense of that?

[00:22:57] **Carol:** Yeah, that's actually a really good question. That's one that's been posed by lots of teams and lots of people about what this is. So, ultimately we got a contract to do some work and, the contract is for two years. It's a two year contract

[00:23:10] **Carol:** to get it done.

[00:23:11] **Ben:** it's a meaty contract.

[00:23:12] **Carol:** And here is the kicker of how we're trying to handle it, is that my team is going to be doing the very large, cumbersome efforts of the long term goals.

[00:23:23] **Carol:** The other teams have some very small wins that they can get in, in their current sprints, and while we're working on this, that'll also help with said contract. So, you know, they'll be improving things along the lines, and I'll make sure that it gets implemented over if it's still an issue on our side.

[00:23:40] **Carol:** But, they're not gonna see anything I'm working on, I would say, for 18 months. Like, that's just my ballpark guess. Yeah.

[00:23:48] **Ben:** Yeah. That's intense. I've never worked on anything that has that kind of a. Time horizon. That's like a whole different way of thinking about the world. Oh

[00:24:01] **Carol:** so different that one of my questions is how do I deploy this to a test environment? Because I can't have this deployed in our standard tests, like dev test staging production kind of environment, because developers can't be developing against this new way of reacting with this part of the system because it's not going into production for a year and a half.

[00:24:22] **Carol:** So how are we going to handle getting this into any type of testing that makes sense?

[00:24:28] **Ben:** man. It's like building a bridge. Like that's the kind of timeline you're on,

[00:24:32] **Carol:** Yeah, it, it, it feels that way.

[00:24:36] **Ben:** man.

[00:24:37] **Carol:** However,

[00:24:38] **Ben:** I just don't know. I just don't know how I'd even approach that. I mean, okay. So if I can just stream of consciousness for a second, I like to work small. Generally, that's just like rule of thumb, wherever possible work small. So I would try to approach something like this with. Is there a way in which we can start circling areas of functionality that can be built cohesively, not necessarily as an independent service or anything, but something where you can, if you think about like inputs and outputs, like what's the largest boundary that I can put where I can map inputs to outputs and then I have something to develop against and I can say whether or not it's right or wrong.

[00:25:21] **Ben:** And then she's like, try and find as many of those as possible and start breaking them up. I don't know. And that's, this just sounds very big.

[00:25:28] **Carol:** it's huge and that's actually one of the conversations I have with, he's my supervisor and he's the guy that ultimately goes and fights for me. Right? So I don't have to fight for myself anymore. Like, he's doing a great job fighting for what I need, you know, is always there to defend the needs of the tech, which is great.

[00:25:43] **Carol:** But that's one of the conversations I had. I was like, one of my big concerns is that it makes more sense. Like right now, where I am in this very moment is that it makes more sense to. Break off very small parts of this process and get them in a way that 3 or 4 years down the road, we could then start migrating over into these actual services.

[00:26:06] **Carol:** But right now, we don't have the middle layer to actually break it out. Right? So, even though I, I say, this is my policy, or this is my body of work that I need to touch. There's no middle layer to make it efficient. It's still going to be slow because it's going to have to still deal with the application to get all of this information.

[00:26:24] **Carol:** So I need to start breaking out those smaller things 1st and get them. kind of arranged in a way that we can talk to each other. Then take the big 1 and say, okay, now, let's get all those connected. Get them in their own database. And now we're good to go. And he told me today, he was like, I'm willing to go fight for that.

[00:26:42] **Carol:** If that's what we decide, right. If that's what makes sense, he goes, we just gotta be making progress forward. Whatever that looks like for you.

[00:26:50] **Ben:** Interesting.

## [00:26:51] Depending on Miracles

[00:26:51] **Ben:** I was listening to an interview a couple of weeks ago with, a guy, I can't remember what podcast it was. I think it was the Hard Fork podcast from the New York Times, and they were interviewing this guy who had founded a company that is making artificial meat, and not like Beyond Burger, like they're actually taking meat cells, beef cells, and they're growing them in these large bioreactor, these giant vats of, of liquid. And there's, there's a number of companies out there that are trying to do this. And the guy that was being interviewed, someone at the interview asked him, you know, why is it that we thought this was going to be so easy? You know, 15 years ago, everyone was so excited about synthesized meat. And here we are 15 years later and to produce a single hamburger patty is like 20, 000.

[00:27:42] **Ben:** You're like, what went wrong? And his response was interesting. He was saying that all these other companies. We're depending on having, on, on solving several different miracles in the whole workflow. And he said, what's important for a company is really to only have one miracle that they're trying to depend on.

[00:28:03] **Ben:** And don't try to, he's like, don't try to improve on anything else. Like make sure that one miracle is solved and then assume that everything else is going to be status quo. And, I, you know, I don't know enough about the meat synthesis industry, but, I, I wonder as an interesting perspective, is there anything there that you can take away in terms of a two year timeline?

[00:28:29] **Ben:** Is there one miracle that you can identify that is the thing that might be the most valuable to attack first or to be like the proof of concept, like, let's make sure that we get this part of the project proven in order to know that the next two years are even going to

[00:28:46] **Carol:** Oh, yeah, 100%. And that is dead on to the conversations I've been having. And it's not about growing our own hamburger patties or chicken livers. It's, it's about what is doable and I need a very clear, this is what defines success.

[00:29:04] **Carol:** So like the thing I've been pushing for is like, give me, what do you define as success? Like, what do I need to do first? And it can't be, Oh, create this whole new relationship, create all these new interfaces. Like I need to know a single, what is the win that I'm going to like, say this is successful.

[00:29:23] **Carol:** And the very first win is that we can go from uploading, say, you know, a hundred. Like, inputs at a time or 100 requests at a time. So, if we need to do 40, 000 in 1 click, we need the ability to add 40, 000 records and the process just flow correctly downstream. And I'm like, okay, so that's the 1st thing I'm tackling is the ability to have, All of the, like, course, like, tasks that are associated with it run correctly as well, but for the large bulk insert to be able to work. Efficiently, and so that the user doesn't sit and wait 45 minutes for. 100 and 100, 100.

[00:30:05] **Ben:** I mean, it sounds like I, I deal with this kind of problem also, and I. I'm always in sort of panic mode where I'm thinking to myself, how can I get this work done as fast as possible

[00:30:17] **Ben:** because it's not a

[00:30:17] **Ben:** priority for the company, you know?

[00:30:19] **Ben:** And, so my stuff tends to be super janky, but know, if I had more time to go back and solve it better, definitely there would be some sort of a separation between the work has been accepted.

[00:30:33] **Ben:** Versus the work has been completed to separate acceptance from actual processing. Now you have to store that state somewhere and you have to store whatever inputs are being uploaded somewhere so that they can be processed at a later date, it's definitely a much more complicated workflow,

[00:30:49] **Carol:** Yeah, because I already have to take our existing state machine and port it over and make sure that everything that's happening in that state machine happens in these new states as well. So there's a lot, a lot that's going to happen on the backend. But I mean, my upfront thought is that I take this load off of the database immediately because the way it's running currently is like, Oh.

[00:31:10] **Carol:** You know, insert, insert, insert, insert, insert. And I'm going to definitely throw that on a queue and let it process and then just send the user notification back. However they choose. It says, Hey, all your requests got done. Like go get them. Have fun.

[00:31:27] **Ben:** Right. It's like you have to upload. I mean, what I see other companies do. So one of the things that we're working on right now is we have to send out all these emails and. As a pre step to sending out the emails, we have to validate that the emails aren't spam or aren't, won't hard bounce because the service that we use to send out emails, you can't go above a certain bounce rate.

[00:31:51] **Ben:** Otherwise they'll shut your, they'll shut your account down because it's going to hurt their delivery, you know, reputation. So we have to run all of these email addresses through these email validation vendors. And it's, it's, it's kind of like what you're saying, I have to upload a file and the file might contain a million email addresses in it.

[00:32:11] **Ben:** And they just give you a token. They're like, here's the job and, you know, check back in 24 hours to see how it's going. And then eventually you get to download the results, but it's definitely not a instantaneous action.

[00:32:23] **Carol:** Yeah. See the, the difference is that, my, what I'm going to call my customer is technically my customer's customer, but whatever. My customer, doesn't want the results tomorrow. They want it in like 60 seconds.

[00:32:37] **Ben:** Hmm. Yeah.

[00:32:40] **Carol:** there's all about, I mean, and then I kind of had the thought to you with that. I'm like, okay, do I give you partial?

[00:32:45] **Carol:** I'm like, okay. Cool. Some have uploaded. Do you want to start working on them? If so here, if not, we're still working, so feel free to continue ahead with these if you really want to. Otherwise just chill and wait, you know, I'm going to hopefully write it well enough that you're only, you know. You know, delayed a few minutes, not the long time you work early.

[00:33:07] **Ben:** Well, that's tough too, because now you're talking almost about the burstable processing power.

[00:33:14] **Carol:** Oh boy. Yep.

[00:33:16] **Ben:** and that now, you know, like to say, Hey, I want that in my life. That implies certain technological choices,

[00:33:26] **Carol:** It sure does.

[00:33:27] **Ben:** then have all other kinds of knock on effects, right? You know, the like Azure functions, Amazon Lambda functions, the whole selling point there is you can go from zero to a 3000 or whatever the max is.

[00:33:40] **Carol:** Super quick. Yep.

[00:33:42] **Ben:** You know, close to instantaneously.

[00:33:45] **Carol:** Yeah. I have, I have been looking at the difference between scaling up and scaling out and what happens between app services and Azure functions when you need to scale out quickly, meaning that, you know, you have a bunch of requests and now you need to scale out. You're like, I think that's out.

[00:34:01] **Carol:** Believe me, I

[00:34:02] **Carol:** think it's Out Yeah, so you want to scale out, and then you want to scale back down when you don't need it anymore. So. And ultimately, I think we're going to need the ability to scale out when it ramps up and scale back down when we don't need it.

[00:34:17] **Ben:** but then, you know, you run into all these other little details, like what, what happens when you have a thousand functions running in parallel and they all have to talk to the database and now you have a thousand concurrent connections to the database, database won't love that. So then you have to worry about pooling or, or limiting.

[00:34:35] **Ben:** Yeah.

[00:34:36] **Carol:** we also have to think about the fact that we run a multi tenant database. So then does each tenant get their own app service to handle these functions or however it works, right? So that depending on the needs of one, does it scale for everybody? And suddenly everybody just shares in the joy of having the, the like growth out?

[00:34:55] **Carol:** Or is it? Buy my tenet, like The thoughts I'm having to put into this are thoughts I didn't know I would ever be thinking. I, I, I'm enjoying it, but it's definitely making me, go into this pre mortem way different than I would have six months ago or a year ago. And I'm getting to face new challenges that excite me and definitely motivate me.

[00:35:20] **Carol:** So that's a good thing.

[00:35:21] **Ben:** Yeah. It's so fascinating. That's, you know, I exist primarily in a monolithic application context.

[00:35:29] **Carol:** Yeah.

[00:35:29] **Ben:** So, so much of this stuff is just philosophical and academic, but it's so fascinating to think about.

[00:35:36] **Carol:** Well, I'm going to have a lot coming at you guys for the next two years or four, depending on how it goes.

[00:35:44] **Ben:** one of the things, so we did use some Lambda functions at work and, I think one of the big mistakes that we made was we, built too much understanding into the functions so that they became very tightly coupled to other areas of the architecture. For, for example, like if they had to upload to an S3 bucket.

[00:36:09] **Ben:** There was like all, like each Lambda function knew where it was supposed to upload to, and in retrospect, what I really wish had happened was, say for that, as a very specific example, if they had to pull a message off of a message queue, that part of that message was, and when you're done processing, send it to this S3 bucket so that the function itself didn't have to know that kind of information.

[00:36:34] **Carol:** Yeah.

[00:36:35] **Ben:** I think that would have ultimately made our code, much easier to not so much maintain, but it would have been easier to change because it would just, it was just too tightly coupled and then you couldn't change anything because it just felt like it would break at any moment.

[00:36:51] **Carol:** Yeah. It kind of feels fragile. Yeah.

[00:36:54] **Ben:** Yeah.

[00:36:55] **Carol:** I, I remember working in like step functions when I was doing like the AWS work before, and I was really into how everything kind of steps through the process. So it feels like you can take your functions and say, okay, I'm done. Now there's another step after, right?

[00:37:10] **Carol:** There's these, all these things that can happen that you can keep triggering after the process. So it doesn't feel like everything has to execute inside one. Yeah. Like big application or one big file, even like it can, it can be broken out into lots of steps and then it also, I enjoy like having the logs of it didn't fail and one, two, three, it's felt like in the, the, like create the S3 file or whatever, I

[00:37:35] **Ben:** well, failure is a whole other can of worms because if someone's uploading something that has, you know, 40, 000 inputs, you know, what happens when it gets to 23, 000 and something goes wrong, like, is

[00:37:48] **Ben:** that. Do you have a partial response? Do they have to restart over? Do they have to re upload?

[00:37:54] **Carol:** almost feels like you need like a safe spot, right? Like a, like a safe entry, like, okay, we got three fourths away. You're going to have to go back and do a fourth or something, you know, like, I don't know, but it's going to be some figuring out. I will say logs, right? I know we're kind of off the topic a little, but today I was in a call going through like the, the chatbot stuff.

[00:38:15] **Carol:** And I was in AWS and we had turned on analytics and it was like, Oh, do you want to turn on app insight? I was like, yes, I need app insight. Cause I don't know why this isn't connecting in the next step up. Cause we'd went through development. Now we're into tests and suddenly it's not connecting. Guess what you can't find in App Insights.

[00:38:35] **Carol:** Anything! It's so terrible. It's the worst. I couldn't even find any, anything related to my code to the point where I did something I probably shouldn't have and I clicked the create a whole new app insight like, like thing. I don't even know what it's called, right? So like now there's this test app insight where everything's supposed to exist and now there's also the chatbot test app insight.

[00:39:00] **Carol:** So I can find my stuff now.

[00:39:03] **Ben:** Nice. Nice. That's the first step in debugging,

[00:39:06] **Carol:** Oh my gosh. Logs are not fun. They're not fun when you can't make sense of them and they're just all together.

[00:39:14] **Ben:** Yeah, I really enjoyed the, episode we had. I think it was two, two episodes ago when we're talking about log levels.

[00:39:20] **Carol:** That was this one.

[00:39:21] **Ben:** yeah, yeah.

[00:39:22] **Carol:** this was with 154. They were together. It was, postmortems and

[00:39:25] **Ben:** That's right.

[00:39:26] **Ben:** That's

[00:39:26] **Carol:** yeah. Yeah.

[00:39:27] **Ben:** Yeah, nailed it.

[00:39:28] **Carol:** Sorry. Go ahead.

[00:39:29] **Ben:** No, no. It was just so interesting because, I don't mean this in a diminishing way, but it's so fascinating to listen to Adam talk about his architecture because he does a lot of very advanced stuff, and, and, and is very adventurous in his solutioning.

[00:39:45] **Ben:** And it was just interesting to hear him talk about his frustrations with logging. Cause I always think about logging. As like a day one thing, like that's, you know, it's like you put your try catches in and you log in and then you figure out your business logic afterwards. And it was just fascinating to hear him like, his logging strategy feels like it is less advanced than almost anything else that he has going on, which is just almost inverted a

[00:40:12] **Carol:** for him.

[00:40:13] **Ben:** Yeah, exactly.

[00:40:16] **Carol:** Yeah.

[00:40:17] **Ben:** is in and of itself, just always fascinating. You know, you have this mental model of people based on the things that you see and, and you know, you let your own imposter syndrome kick in and you assume everyone else has like all their together. And then you, you see these little things and you're like, Oh, we're all just people and we're all just really trying our best and we make a lot of mistakes and it's, I don't know.

[00:40:39] **Ben:** It's always a. I find those conversations very grounding, I should say, or they offer perspective and a commonality.

[00:40:49] **Carol:** It reminds us that we're all related, right? And kind

[00:40:52] **Carol:** of working through our own struggles. Adam, Adam is like a whole nother beast, right? And part of me feels very lucky over the next two years that I get all of this free like consult work from you guys to just like talk to you what I like to talk to you like what I'm dealing with.

[00:41:09] **Carol:** And Adam's just going to be like, Oh, day one, ground up. Here's where we're going to start. This is what you should be doing. Like, have you thought of this? Yeah.

[00:41:18] **Ben:** absolutely.

[00:41:19] **Carol:** pay for questions.

[00:41:22] **Ben:** no,

## [00:41:22] New Paradigms

[00:41:22] **Ben:** I'm super excited to hear. You, report back on your progress, you know, whatever, whatever bits you're allowed to, I'm sure there's going to be

[00:41:29] **Carol:** Oh, yeah.

[00:41:30] **Ben:** talk about, but

[00:41:31] **Carol:** Yeah, I mean, there's little things, right? But the overall is easy enough to talk about cause we're all dealing with it. a lot of companies are making the move from on prem to cloud and it's not a say that tech has, it's something that's been pushed down to them. This isn't something we push for.

[00:41:46] **Carol:** This is something that got pushed to us. It said funding now goes to cloud and get on board kind of thing, which is, I mean, it's not a bad thing. I mean, if, if on cloud is where we're going for the future, then that's what we should be doing. Right. So we just get to learn and we get to try new things.

[00:42:03] **Ben:** yeah. I, I mean, I was, you know, I'm such a laggard when it comes to new technology. I'm, I'm very much a, here's my old boring technology and how can I use that to solve the problems? But it is just funny, you know, you see progress being made. But every, it's, it's, it feels very much like a two steps forward, one step back in terms of solutioning versus complexity.

[00:42:28] **Ben:** So it's, you know, we have all these CDNs, content delivery networks, which are globally positioned to be near people. And then they say, Oh, wouldn't it be great if we could just start executing your code at the, the pop locations, the points of presence? And you're like, Oh, that's so great. Cause now, you know, the request doesn't have to travel halfway around the world in order to process, your request, but then you're like, yeah, but then what about the database?

[00:42:51] **Ben:** Like they still have to go back to the database and now you're going from the pop locations back to, you know, US East one or, or West or whatever. And then you're like, Oh, okay, well now we need a whole nother database technology solution in order to bring the data itself closer, but then also have replication of data and

[00:43:08] **Carol:** be replicated.

[00:43:09] **Carol:** Yep.

[00:43:10] **Ben:** and it's like, you know, we have all these exciting steps forward, but each step forward adds overhead and complexity that then you have to solve with new solutions that, I don't know, I, I get a little, weary sometimes of whether or not the, the pros outweigh the cons, but.

[00:43:29] **Carol:** Yeah.

[00:43:29] **Ben:** why I like to be slow.

[00:43:31] **Carol:** but see, that's also valid with what I'm doing right now, because I feel like a lot of what has been solved in the monolith are problems with, like, creation, problems with updates, problems that they've already faced. I'm about to just spin this off in a whole new way and probably have to re solve.

[00:43:51] **Carol:** Every single problem over again and hope I get it right. But in reality, what happens with development is we spin it off in this new way, and now we're going to spend the next several years figuring out how to get that part of it right to fix what we already had fixed before. So

[00:44:08] **Ben:** Yeah, absolutely. Well, we did, we did an episode, I mean, this was like a hundred episodes ago or something crazy where we're talking about how much, when we move to these more cloud and containerized types of programming paradigms, how much people actually know, have to know what goes on under the hood.

[00:44:27] **Ben:** You know, like, do you have to know about Kubernetes? Do you have to know about Docker? Do you have to know about orchestration? And. Like, no, but also yes, because if you're dealing with something that has a processing that takes place over maybe minutes and not, you know, seconds anymore, then it's like, well, are you operating on a processing compute that Is transient or, you know, do you need to know that this machine is going to stick around and that this network attached storage is going to stick around or block storage or whatever you call it?

[00:44:59] **Ben:** Or is it okay if Azure just takes your compute away at, you know, at any moment's notice? And then you have to talk to your ops people, like, do we need dedicated instances for this kind of compute and on demand instances for this other types of compute? And you're like, I never had to think about these problems before.

[00:45:14] **Ben:** We just had a server and that server was running and you never had to think about it. And it's just. I don't know.

[00:45:20] **Ben:** It's, it's exciting, but frustrating.

[00:45:22] **Carol:** I totally miss the days when I started with Tim as an, like as an intern. Where they still had front page extensions, and I had to check out the file. And if I went away too long, I would have an email or a message for someone asking me to check the file back in so they could make edits to it.

[00:45:41] **Ben:** Yeah. Well, do you

[00:45:42] **Carol:** Wasn't the life easier then? It's so much easier.

[00:45:46] **Ben:** do you, did you ever use Dreamweaver

[00:45:49] **Carol:** No, no. That was a little before me.

[00:45:52] **Ben:** So Dreamweaver had kind of similar concept where, you essentially Dreamweaver for those listening was basically, development environment slash code editor, but you would, you would back it onto things like an FTP.

[00:46:10] **Carol:** Yeah.

[00:46:10] **Ben:** server. So what it would do is you would open up a file and what it would actually do is it would FTP, it would generate a lock file. Like you opened up home. cfm and it would auto generate something like home. cfm. lock. And it would FTP that behind the scenes, unbeknownst to you, to the server, and then all the other developers that would get synced down to their Dreamweaver instance.

[00:46:34] **Ben:** And then when they went to open up. Home. cfm Dreamweaver would say, actually, you know, Carol has a lock on this file. You have to let Carol unlock it, before you can open it. And just, I mean, it's just so fascinating to think about that was. Before version control or, or, you know, it was outside of version control and it was using

[00:46:53] **Carol:** get. Yeah,

[00:46:55] **Ben:** it's crazy. I loved it. I mean, I hated it, but I loved it.

[00:46:58] **Carol:** No, front page extensions did the same thing. Yep. So, I know the pain. Anyways, are we at a stopping point?

[00:47:06] **Carol:** Yeah, I guess so. I'm, I'm excited for you to go to this premortem and then report back. I may just come back crying and say, 100%, I've scheduled a post mortem about why this pre mortem failed. Possible. Totally possible. Or, you know, like, I'm gonna use what you said. I'm gonna say, hey, yeah, sure, these are valid, but tell me why. Like, tell me why this is a valid, like, question or a valid concern for what we're trying to accomplish.

[00:47:34] **Carol:** Let's talk about the whys of it and not just go off on tangents, because that's going to be the key thing here.

[00:47:40] **Ben:** I think that's, that's going to be critical for sure.

[00:47:43] **Carol:** All right, well, cool. Thanks for your help tonight. I really appreciate it, Ben. I, hopefully tomorrow will, go a little easier for me now that I've had my free consult from you, my little therapy session.

## [00:47:54] Patreon

[00:47:54] **Carol:** Well, this episode of, Working Code was brought to you by growing your own meat listeners like you.

[00:48:01] **Carol:** If you're enjoying the show and want to make sure we keep putting out whatever this is into the universe, you should consider supporting us on Patreon. Our Patreons cover our recording costs, editing, and transcription costs. Man, they should probably get me some, like, English classes, too. And we couldn't do this each week without them.

[00:48:21] **Carol:** So a special thanks to our top Patreons, Monte and Giancarlo.

## [00:48:25] Thanks For Listening!

[00:48:25] **Carol:** So, Ben, you got anything for an after show tonight?

[00:48:27] **Ben:** I was not prepared.

[00:48:29] **Carol:** I wasn't either. I think, we're gonna skip the after show tonight, you guys. I got some reflecting to do on the, like, everything we talked about and getting ready for tomorrow so I could use the break. But, yeah, so this week's homework is going to be, tell a friend, just tell someone about us, let them know that we exist in the world and let them know to find us at workingcode.dev. So that's it for this week and we'll catch you next week until then.

[00:48:55] **Ben:** Remember folks, your heart matters.
