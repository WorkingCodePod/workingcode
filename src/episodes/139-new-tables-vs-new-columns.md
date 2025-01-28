---
title: "139: New Tables vs New Columns"
description: "This week on the show, the crew discusses the benefits and complexities of adding new tables vs new columns to a database."
date: 2023-08-09
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/139-new-tables-vs-new-columns/id1544142288?i=1000623913858"></iframe>

Early on in his career, Ben's default behavior was to add _new database columns_ to any _existing table_ that felt "similar enough" in nature. After years of evolving an application, however, this has lead to relatively wide tables with only a loose sense of cohesion. More recently in his career, Ben has started to err on the side of creating _new tables_ in order to house _new columns_. While this approach adds complexity in some ways, it also reduces complexity in other ways and creates a more clearly defined data model. Or, so he hopes.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/139-new-tables-vs-new-columns.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** kind of the, the philosophy that I take right now is that storage is cheap. And if I have rows. Leftover in a table that shouldn't be there. It's not the end of the world, but , when everything is in one table and you can delete one row

[00:00:12] **Ben:** that is really nice.

[00:00:13] **Ben:** it is about trade offs for sure.

[00:00:16] **Adam:** So once again, you know, I made a bad assumption and I put my foot in my mouth and you're not as crazy as you seem at the face value, Ben, you

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go. It is show number 139 and on today's show we're gonna get narrow minded. We're gonna bring it in real tight

[00:00:52] **Carol:** Sounds awful.

[00:00:55] **Adam:** But first as usual before we tell you what that is We are going to start with our triumphs and fails and Ben, it's your turn to go first.

## [00:01:02] Ben's Failure

[00:01:02] **Ben:** All right, I'm gonna kick us off with a failure, which is that, uh, this is not official, but the rumor mill is churning at work and it looks like we're gonna have some rifts, some reduction in force coming down the pipe, in next month. and this follows a, we had a very huge rift last July, so about a year ago.

[00:01:22] **Carol:** Then we had another smaller riff in February, and I think an even smaller riff after that. And the, the rumors are that this riffs gonna be. And, we're already understaffed. So I don't know, I don't know where you go from that. so scary.

[00:01:37] **Ben:** yeah, it's weird. I don't know how I feel about it. I mean, obviously I feel like poo, right?

[00:01:42] **Ben:** And that's why this is a failure here, but, It is what it is, we'll see. I'll have more to report when the poo hits the fan. So I'm just, I'm just exhausted. It's weighing on me, I think. And I think it's weighing on me more than I realize, because I'm just, I just feel beat up. Yesterday, I got into bed at like 4pm and just started watching TV, which was great.

[00:02:03] **Adam:** Mm

[00:02:06] **Ben:** But I just had nothing left in me, but I don't want my entire update to be a failure. So I did want to share one thing that I listened to yesterday, which I thought was very interesting. One of the podcasts listen to is. net rocks. They've been going for like. 25 years

[00:02:21] **Carol:** Forever. Yeah.

[00:02:22] **Ben:** number of podcasts and they interviewed this woman, Layla Porter.

[00:02:26] **Ben:** She's the dev advocate at VMware and their whole topic was about modular monoliths. And the reason that I found this discussion very interesting is because oftentimes I think in the technology world, we will hear something and we will develop in our own heads a concept of what that thing is. And then someone years later, maybe explains to you and you're like, Oh, the thing that was in my head was not at all what I thought it was a big example of this.

[00:02:56] **Ben:** We talked about many episodes ago, the idea of singletons. A singleton in programming is something that can only be one instance, like you have no choice. And for years I always thought that I used singletons, quote unquote, in my code fusion because I would instantiate components and then cache them in memory.

[00:03:15] **Ben:** Turns out that's not a singleton, that's just a single instance of something that I've chosen to cache, which is a very different

[00:03:21] **Adam:** It's like Singleton as a pattern instead of as a native construct.

[00:03:27] **Ben:** So in this interview with Layla Porter, they were talking about modular monoliths. And so the thing that I had developed in my head as a concept is this idea of modularity in a monolith, or specifically, what does modularity mean in relation to the phrase modular monolith? Because when I had developed this mental model for what that means, it was always kind of.

[00:03:49] **Ben:** Domain models like, Oh, I have, I'd have a module for users and I'd have a module for accounts and I'd have a module for projects and I'd have a module for payments, something like that. Cause I don't, you know, it was just me taking an idea and molding it into something that sounded modular, but not having any actual education about it.

[00:04:09] **Ben:** So she's talking about modularity and she says, so what makes the most sense in terms of modules? And she, then she says, I think the most obvious one is anything that has to In real time, even within the user request. So in her mind, modularity was more about synchronicity versus asynchronicity that everything that has to be synchronous.

[00:04:33] **Ben:** Is in the same module and that everything that can be asynchronous might be in a variety of other modules, like sending emails, sending invoices, things that don't have to respond within the span of the request. And that was just so radically different than what I thought of as modularity. And I think hers makes so much more sense that that's when they talked about microservices versus monoliths. And that you can still have a clean quote unquote clean monolith by keeping it modular. I was just making up in my mind what modularity meant in that respect, but. It wasn't based on anything meaningful and the idea that asynchronicity versus synchronicity as a way to, I think, indicate where the seams are in the application makes, I think, just way more sense and was just fascinating.

[00:05:21] **Ben:** So I want to plug a modular monolith episode on dotnet rocks.

[00:05:26] **Tim:** Is it, is it safe to say that your previous mental model for modularity was more based off sort of like a business domain, like you said, payments is all one thing and, you know, you know, it's sort of like a business function, that's a module rather than actually what the code is doing.

[00:05:44] **Ben:** Yeah, I think so. And, and, you know, to underscore that that wasn't based on any kind of reasoning. It was just me trying to find a way to think about code and, and, and. Boundaries, but not boundaries that had functional sense to them. Like they had business sense, but not necessarily maybe architectural. So they didn't have any architectural sense.

[00:06:06] **Ben:** And she was looking at it from an architectural standpoint, not a business standpoint. And I just liked it. I thought it was groovy.

[00:06:14] **Adam:** It's an interesting idea. I wonder, like, I'm just thinking about it in the context of my application. I think that if we were to try to do something like that it would be like one module is 99% of the code base and then you have one or two others that fill in that gap. It doesn't feel like a good system if One of the end buckets holds the vast majority of the application.

[00:06:38] **Adam:** Like what it, I don't know. It feels like an anti pattern to me or,

[00:06:42] **Ben:** well, you know, I think I would say that as an industry, and this is what they talk about on the show as well, that. We really swung hard as an industry into microservices and didn't really think very deeply about how things should be split up. And then we ended up painting ourselves into all kinds of difficult corners because we took essentially a monolith and broke it up and now we have a distributed monolith and all these things are making calls to each other because they, you know, service A needs data from service B in order to generate the response to the user.

[00:07:16] **Ben:** So is this sense that. We, we took the worst of all possible scenarios and put it into production where if you isolated it more on synchronicity versus asynchronicity, you would co locate all of the things that really tightly depended on each other, and then you would break out or could theoretically in the future, break out things that were not so tightly coupled. So I, I a hundred percent understand what you're saying, but I. I almost feel like that gut feeling that it was wrong to have all those things together as part of why microservices kind of exploded out of control as well. I mean, I love monoliths. So again, like, like I, like I was talking about on the book club stuff, you know, and confirmation bias, I hear what I want to hear when I hear something that makes me feel like, oh, I could be right about something anyway.

[00:08:10] **Adam:** That's the human condition, Ben.

[00:08:12] **Ben:** That's the human condition. I'm good at it. anyway, so that's me.

[00:08:17] **Ben:** failure and a little triumph there in terms of value add. But, Carol, what do you got going on?

## [00:08:22] Carol's Triumph

[00:08:22] **Carol:** I'm going to take us to a nice triumph. So tomorrow I'm getting my new tattoo and my son is at, my oldest son is actually on his way here now. It's about three and a half hour drive for him to get here. So he's on his way. So in the morning we go to 11 to get our new tattoos, which are our mother son tattoos that we've been talking about since he was like 16 and I am super excited to get it.

[00:08:46] **Carol:** So I have to show you guys when it's done, but I've always wanted to get a bird cage that was empty. On somewhere on me and then he was going to get the bird on him. So, you know, yeah, it's a symbolize, you know, setting your kid free kind of thing. Like I've done my thing now, my nest is empty and he's off in the world.

[00:09:04] **Carol:** So he's getting a raven on his forearm and I'm getting a cherry blossom branch on my. Arm, across my bicep and, it's going to have the birdcage in it. So super excited to get that going. And then the next win is I have decided that while Steve's in school, I'm going to up my home lab scale. So whenever I left our last house, I just packed up all my, unify.

[00:09:31] **Carol:** Hardware, and I didn't install it here because he already had all of his networking stuff set up. So why go change it if we're only going to be here 60 days, but I've already went and unpacked the raspberry pi. So I have the pi already. I've wrapped up all my cables. Everything is good to go. So I'm going to take his old gaming PC because we got him a new PC for Christmas, my husband.

[00:09:54] **Carol:** So I'm going to take his gaming PC and turn it into like our media server so that I can stop Paying for cloud storage of our cameras and stuff and have it all store locally. And i'm going to get a new switch and i'm just i'm super excited to be working on home lab stuff because that's That's like my itch like I enjoy just tinkering with little things like that

[00:10:14] **Ben:** So Carol, I know what home lab means, but I don't think Tim does. Could you, could you explain it to him? What does, what does that phrase mean?

[00:10:22] **Carol:** So a home lab is pretty much anything that you do for yourself to like, make your house more techie. So for me, you know, Steve was like, Hey, we've really get no wifi in the bedroom. Can you fix that? And I was like, yep, on it. I'm going to put a new access point closer to the bedroom so that he can have, you know, internet when he's laying in bed or whatever.

[00:10:44] **Carol:** you know, putting our thermostats on something internal,

[00:10:47] **Carol:** I'm not going to deal with our Roomba, but it's anything you do in your house to automate and to make it yours. So I've seen people deploy code in their house and do all kinds of stuff. I'm not going that far yet, but definitely we'll have a nice interface. I've, I plan on creating a nice interface where Steve can just like access from his phone and, you know, control everything that is part of our, like home ecosystem.

[00:11:10] **Carol:** Very cool. I think Tim appreciates that explanation.

[00:11:13] **Tim:** Thank you. Thank you so much.

[00:11:15] **Carol:** I think Tim might do some home lab things. Yeah, I'm pretty sure.

[00:11:22] **Tim:** Yeah.

[00:11:22] **Adam:** it's very nice of you to help him, fill in the gaps in his knowledge. Your

[00:11:25] **Carol:** I mean, he just didn't know that's what he was doing, but what kind of home lab stuff do you do?

[00:11:30] **Tim:** Mostly entertainment stuff. So we have a Plex media server. So we store all the movies and digitize stuff and put it on there so you can get TV and movies all through Plex. I really like that.

[00:11:43] **Carol:** Yeah, I was hoping to, I was hoping to rip all of our, DVDs that we have so that we don't have to keep moving them from place to place and just have a digital storage of them.

[00:11:54] **Tim:** That's pretty cool. And then, I missed her. I didn't, I kind of dropped that. There's a smart assistant. That's kind of like Alexa or other one, but it's called Mycroft. So that, yeah, you can talk, talk to it and it'll look stuff up for you, but I never got too far with that.

[00:12:11] **Carol:** Yeah, so I'm excited to get in on that while Steve's doing classwork and stuff. I got it all set to the side so it can go with us in the shipping and not get lost in transit. But that's me. What about you, Tim?

## [00:12:23] Tim's Failure

[00:12:23] **Tim:** Well, I've got a nice juicy fail actually too.

[00:12:26] **Carol:** oh.

[00:12:26] **Tim:** Yeah. So last week I was talking about the security updates. We finally got, you know, these, ColdFusion had like three updates in a row that came out and they were pretty. high visibility. I think one was even like a zero day kind of thing. So got that launched on Sunday and the actual security patch work fine.

[00:12:46] **Tim:** But some reason these were windows machines and it, broke like the default page. So, you know if you don't put in, you know default dot whatever dot cfm or whatever it it was not It was coming back with a 404 or actually it was a 500 error for some reason

[00:13:02] **Carol:** Oh, that's not fun.

[00:13:04] **Tim:** And so but it's like I don't know how many people actually only do that and I found out pretty quick.

[00:13:09] **Tim:** but yeah, and I don't know why it broke that and we we ran like the the web server config stuff and it didn't seem to do anything. I just had to go in and manually like add some default pages and IIS to different folders. So that was kind of annoying. I don't know. I don't like it when you don't, because it didn't, when we did this in development, it worked fine.

[00:13:30] **Carol:** No, no issues. Did the, did those servers have the IIS configs already in place though?

[00:13:35] **Tim:** they were the same configs. Yeah.

[00:13:37] **Carol:** configs? Yeah.

[00:13:39] **Tim:** yeah, I don't know if that's just frustrating, but yeah, that wasn't a huge deal, but just annoying and one thing that was the most annoying though. So I, I would work on some code and I don't know, I wasn't paying attention. I was working locally, probably spent a day and a half on, on something, a new feature, and then just got distracted and didn't never really deployed it to anywhere and didn't even push it up to GitHub and somehow I lost all that.

[00:14:06] **Carol:** Oh no!

[00:14:08] **Tim:** Because I'm generating a, a banking file. So I generated a banking file, send it to someone. I mean, can you send it to the bank for testing? They got tested. So I know I did it. I know I did the work, right? I have a file that says so. so I spent about three, four hours trying to find it anywhere, everywhere.

[00:14:23] **Tim:** It was nowhere in Git.

[00:14:24] **Ben:** no, man.

[00:14:25] **Tim:** I think I had done it local, and then I, for some reason, decided to rebuild my Git repository.

[00:14:30] **Carol:** Hmm.

[00:14:32] **Tim:** I didn't stash it. So yeah, that's just stupid. So I rewrote, I spent today rewriting all that today and I was quite upset with myself, but

[00:14:42] **Carol:** The whole time. Just like err.

[00:14:44] **Tim:** yeah, it's just worse. You know, it's like, you're like, how long do I spend looking for this versus actually just redoing it?

[00:14:50] **Adam:** And the whole time you're rewriting it, you're like, this isn't as good as the first time.

[00:14:54] **Tim:** No, actually it's better. No, I was like, actually, you know what? This is a lot better. I'm probably glad I rewrote it.

[00:15:00] **Carol:** It's funny. Yeah. I've had that happen before where I'll go to stash something and I will like, it'll be a new file. So it's never been added to index yet. So I'll stash it, but the new file doesn't get stashed. And then I just always clear out all my changes. I'm like, okay, just go. And I'm like, Oh no, the new file, it didn't stash it.

[00:15:16] **Carol:** Oh no.

[00:15:17] **Tim:** Yeah. Yeah. That's, that was pretty frustrating. Anyway, that's me. How about you, Adam?

## [00:15:23] Adam's Triumph

[00:15:23] **Adam:** Well, I'm going to run this out with a triumph. So we're two and two. and my triumph is that, for my company, click ops is on the way out and Terraform is on the way in. And that's real exciting.

[00:15:35] **Carol:** What is ClickOps? ClickOps. ClickOps.

[00:15:37] **Adam:** so click ops, if you remember when we had Brian Rinaldi. No, not Brian Reynaldi, the other Brian, Brian Kloss on the show.

[00:15:43] **Adam:** he talked to us a lot about, AWS, services and, and managing that. And he introduced me to the term ClickOps. And that is when you're managing your infrastructure by going into the AWS console or the GCP console or the Azure console, whatever it is, and using your mouse to click on things and typing in server names and that sort of thing to, to manage your infrastructure, create new services, or create new instances of servers and databases, whatever. And Terraform is a tool that, can manage that for you, like in infrastructure as code. So you, you have like configuration files that say, okay, I need. You know, this is the type of database and I need three instances of them or whatever and That sort of thing and then it can generate that and if you wire it up correctly It gets the host names of each of those and you can stick those in route 53 and then you can have you know dedicated host name aliases in your route 53 route table that Then you can map into other services so they know how to get to it.

[00:16:40] **Adam:** That sort of thing. Pretty neat. and I mean, we're still very early days in this, like we've done the, there's a, I don't know if it's a plug in or what. fortunately for me, I was able to just sort of like plant the seed of this idea. Like, hey, we should try out Terraform. I hear it's really easy to generate code from your existing infrastructure.

[00:16:56] **Adam:** And then it just kind of like, Picks up where you left off and you don't have to start from scratch and rebuild everything and then I came back after the weekend He's like, yeah, I kind of mostly got it figured out. I'm like awesome So that's kind of where we're at right now Like it generates stuff but then there's like bits and pieces in that that are hard coded and you have to kind of extract that out and make it Pull the the like IDs of the surfers and that sort of thing into a configuration file or something like that and then put in a token It can get streamed in sort of thing, or secrets or what, you know, environment variables, that sort of thing.

[00:17:29] **Adam:** I'm super, super, super excited about all this. we, for compliance reasons, you know, we've been trying to get way more diligent about, managing... Not even managing, but just like, documenting infrastructure changes. Like with ClickOps, you really don't have much of a, of an audit log at all. With, if you turn it on, there's a tool called CloudTrail, which is like audits everything that you do in AWS, but it's.

[00:17:55] **Adam:** Just like everything else in AWS, it's, it's, overwhelming if you don't know what you're doing. and so, this at least will, you know, it'll give us the config and then in theory, should we ever need to, you know, if Amazon's like, sorry, we're closing up shop. See ya. And then we needed to go to Azure GCP or whatever.

[00:18:13] **Adam:** In theory, we could just kind of flip that bit in the, in our root config and say, okay, we're going to be on GCP now and here, and it goes and builds all our infrastructure. So that would be cool. And like what Tim was saying with the, the default page not being configured, right? So if you were using something like Terraform and you used that to build your, to deploy the change, like the new version of the application server and it broke the default page not being available or whatever, like that's the type of thing that you would catch in QA because you're building your environment from code every time.

[00:18:46] **Adam:** And then, you're like, okay, well, we need to fix that. So you go back and you add that config and now you test it in QA again, QA again. And, and all's good. And then you can go to production.

[00:18:56] **Ben:** it does, it does sound really cool.

[00:18:59] **Tim:** Terraform is that, like platform agnostic?

[00:19:01] **Adam:** It is, it's from a company called HashiCorp, not sponsored. but, yeah.

[00:19:05] **Carol:** call us.

[00:19:06]

[00:19:07] **Adam:** I, I don't know what they're

[00:19:09] **Ben:** Docker, right?

[00:19:10] **Adam:** no,

[00:19:11] **Tim:** No?

[00:19:12] **Adam:** no,

[00:19:13] **Carol:** I don't think so. Douglas

[00:19:14] **Adam:** I'm trying, I, I, Moby, I think Docker was the original name of the company and then they like split it. And then it's like, They're, they're like enterprise y thing is Moby, or that's the name of the company now. And then there's like, Docker is the product.

[00:19:28] **Ben:** Gotcha.

[00:19:30] **Adam:** They're, they're...

[00:19:30] **Carol:** much going on, it's hard to keep

[00:19:32] **Adam:** Yeah, early days of containers were, were pretty wild.

[00:19:34] **Adam:** It's possible that like, maybe HashiCorp had some sort of Docker competitor, or maybe

[00:19:39] **Ben:** I think they

[00:19:40] **Ben:** did Docker swarm, maybe.

[00:19:41] **Adam:** Okay. Yeah, I don't know. I don't know about that.

[00:19:44] **Ben:** what I'm talking about.

[00:19:45] **Adam:** Yeah, but, yeah, super exciting.

[00:19:49] **Ben:** I would be curious for another time, perhaps I'd like to understand more about how your company figures out what to work on, because I know you're a relatively small company. And you do a bunch of wild stuff, whether it's, you know, moving to CLI based one password key management to nightly data dumps from your database to key rotation to all, you know, like, I feel like you're always working on rather interesting stuff.

[00:20:18] **Ben:** And then, you know, I'm going to do, do a little side John, take six months and do SOC compliance work. I'm, I'm, I'm, I'm curious to know how much feature development happens or is, is AlumnIQ, like feature stable. And now you guys are focusing more on hardening the product and making it scalable and more maintainable.

[00:20:36] **Ben:** And

[00:20:37] **Adam:** Yeah, it's definitely maybe it would be a good idea to, like maybe have Steve on or something in

[00:20:43] **Ben:** Yeah, yeah, yeah,

[00:20:43] **Adam:** Have that conversation with them. I just to give you the five second version, like it, it definitely feels like there's a spectrum, right? You're either, you know, one end you're like a hundred percent feature work.

[00:20:52] **Adam:** The other end, you're like absolutely no new features, bug fixes only. And, and whatever security and, you know, optimization, efficiency, cost cutting, whatever. and we are, you know, kind of working our way from the beginning, as I said them of that spectrum toward the other end, but we're still pretty close to the beginning side, so I would say we.

[00:21:12] **Adam:** You know, still may, maybe like 70 ish percent sort of feature work. but then, you know, we're kind of taking the foot off the gas a little bit there.

[00:21:21] **Ben:** sounds like you guys get a lot of stuff done for the size of your team.

[00:21:25] **Adam:** We try to, yeah. You know, it's very much like a move fast and, and just get it done. And then we'll worry about getting it right after that. Like when, when we can come up for air. All right, cool.

## [00:21:37] Book Club Recap

[00:21:37] **Adam:** Well, that's it for me then. why don't we, before we move on to today's topic, let's do our book club recap. earlier today we met with, what was it?

[00:21:47] **Adam:** I guess the total number of people on the call was 11. All four of us were there. So quick, some quick math. That's a, what, seven other people were there. and it was, it was a good conversation. anybody want to jump in? What were your guys thoughts about it?

[00:21:59] **Carol:** I really enjoyed it. I enjoyed hearing how, you know, one of our patrons was able to relate his day to day operations with, you know, like continuous integration with the challenges that they were facing in the book and how they actually move to that. So it was just nice to hear that some of the.

[00:22:18] **Carol:** The good is used in other companies, because like, I think one thing Tim had brought up, like, okay, you read the book, but then how many people actually see a change? So it's good to hear when people do make changes.

[00:22:30] **Adam:** Yeah, for sure. I feel like, it's been a pretty common thing, theme among people that I talked to that like somebody will read the book and be gung ho and excited about it and want to do some or all of what's in there and then they share it with their company or with their team. And maybe a few people will read it, maybe a percentage of the people that read it are okay to buy in and then it just doesn't go anywhere like people.

[00:22:54] **Adam:** It seems like there's this lack of enthusiasm for, taking a professional and evolutionary approach to, the way that we work, not just the work that we're doing, but the way that we work.

[00:23:08] **Carol:** And I feel like a majority of people don't feel like that they are in spots to make those changes. So why try? You know, only one person sits at the top and if you can't change that person's mind, you sometimes feel like it's too much of a burden and too much of a headache to try. So just work through the madness and get through your day.

[00:23:28] **Adam:** sure. So then, the other thing that kind of stood out to me, this is what, my third or fourth reading of this book, something like that, so it was, as I was reading it, it was more and more obvious earlier and earlier in the book that this is, Agile propaganda. I mean, it's good Agile propaganda, but it's Agile propaganda.

[00:23:43] **Adam:** Let's be honest, Agile development, I guess is need to be clear about that. Capital A Agile because they're doing things like, you know, Kanban and, work in process limiting. And,

[00:23:55] **Carol:** Change control.

[00:23:57] **Adam:** yeah, I don't know that's unique to Agile, but yeah, stuff like that. What were we saying, Ben?

[00:24:01] **Ben:** I just, I just said whip.

[00:24:05] **Adam:** With the H,

[00:24:06] **Ben:** Yeah.

[00:24:06] **Adam:** So, you know, you got to kind of come into it with your eyes open, right? This is agile, agile propaganda. And that doesn't necessarily mean that it's going to be bad, but you have to know that going, or I think it helps to know that going in. And, you know, if you already know that you're not going to do agile, I don't think that necessarily, it means that, you're not going to get anything out of the book.

[00:24:28] **Adam:** I think there's other lessons to be learned, but, I think that the, at the end of the day, this. Is ultimately, I think, a sales and marketing effort for other agile content, right? Like the, the guy who wrote this book also wrote another book called the DevOps Handbook. And it's all about like, you know, how

[00:24:49] **Carol:** Co authored it.

[00:24:51] **Ben:** Oh, is that true? Cause they, they talk about writing that book at the end of this book. I thought that was just made up. Oh, that's hilarious.

[00:25:00] **Adam:** Yeah. And that's the funny thing. Like, as I was reading it, I'm like, is he trying to imply that like, this is sort of a story that happened to him and that's why he wrote that book? Or is he just like, you know, this is the tie in and this is how I can like. Maybe people will go search Amazon for that book and see if it exists because I mentioned in this one sort of thing.

[00:25:18] **Adam:** I don't know. but yeah, I mean, it's a, it's a good book. You can learn stuff from it. Obviously the, you know, they kind of go through the, the problems that Agile solves. Like they, they make up this company that has problems and sort of try to naturally introduce Agile concepts and how they, and have those things solve their problems.

[00:25:41] **Adam:** but there's other lessons to be learned too, right? So like, the one, this lesson, I think kind of really fully crystallized for me as we were having that conversation, in our book club this afternoon, which is like something, it's multiple pieces from discussions we've had on the podcast way back about like, When we first started talking about feature flags and, something Ben said during the, conversation this afternoon about like, when things start to go wrong, when you start to have a whole bunch of problems, I know, Ben, I don't, well, I don't remember exactly what you were referring to, but like, maybe is it bugs in production or something?

[00:26:16] **Ben:** Well, in the, in the book, they were talking about how. When things start to go wrong, the instinct is to slow down and put more process in place. And Eric and others were saying that that's the opposite, that you're actually starting to work faster and deploy more often, and that will reduce the number of bugs and issues that you have in production.

[00:26:38] **Adam:** Right. And that's counterintuitive. Like, you, you know, I think if you hear that, when I heard that. I was just like, well, but we're already working as fast as we can. And

[00:26:47] **Ben:** Right, right.

[00:26:48] **Adam:** we're pushing these things out and we have problems. So how is trying to go even faster and get the same amount of work done in less time going to help at all?

[00:26:56] **Adam:** And I think what the, the light bulb moment that I had was it was, yes, it's go faster, but it's go faster by breaking it into smaller deployable chunks. And that is much easier through use of something like feature flags, which is kind of tie in to. The discussion like when we first brought up feature flags in the podcast and you were talking about oh, yeah, you know, I just deploy the the smallest like a what was it? I don't remember exactly how you put it But you know, it's like a couple of hours of work or something and just deploy that and i'm like How is that useful? Why you know, why bother? instead of like, you know doing a nine week project and putting that behind a feature flag and then deploying it all at once.

[00:27:36] **Adam:** Like I get that, I think a little bit better now, like by putting it out in a feature flag, you can expose a few people to it selectively and, and kind of work out the kinks as you go. Instead of like, okay, here is this baby that I've been forming for the last nine months. Tell me everything that's wrong with it so I can go cry myself to sleep.

[00:27:58] **Adam:** Right.

[00:28:00] **Ben:** And actually it ties in a little bit to our triumphs and fails earlier when I was talking about how we have these concepts in our head and we then hear other people describe similar things or things that we think should be similar but end up being quite dissimilar and. When you were just saying, well, we're already moving as fast as we can.

[00:28:20] **Ben:** How does moving faster help? I think it's also helpful to remember that I think a lot of us are, or an increasing number of us are in the practice of deploying more often, but places like parts unlimited from the book, they were not deploying more often. They were deploying, you know, every two weeks or however, however long it was.

[00:28:40] **Ben:** And they had

[00:28:41] **Adam:** that frequently.

[00:28:41] **Ben:** yeah, they had these. They have these huge massive, you know, we've been working a quarter to get ready for this deploy kind of a thing. So when they say we have to work smaller and faster, you know, you have to take it from their perspective as well.

[00:28:55] **Adam:** Oh, true. Very true. Okay. I mean, any final thoughts on the content of the book

[00:29:00] **Ben:** I, I enjoyed it. I, you know, I like, like you, I've read it a couple of times now. And, I, I mentioned this in a previous episode, it, how, how I think about the book and what I take away from the book is heavily colored by what I'm going through personally at work. And it was just very interesting.

[00:29:17] **Ben:** I was much more aware of that going through the book this time and, it colored it very interestingly.

[00:29:22] **Adam:** Yeah. And actually that reminds me of something that, only hit me this time, this read through that I talked about in book club today that I wanted to bring up here, which was, in the, in the story, the company going through this is a manufacturing company. They produce auto parts. And so it Is important for their business, but that is not their end product, right?

[00:29:43] **Adam:** They're not producing software. They're producing software so that they can manage their hardware production. And, as a result. The compliance section of the book to bring this back to my world. you know, they just kind of at the end of it, just kind of like hand wave away, like 90% of the whole compliance story and just say like, Oh, the, you know, there's controls in the other side of the business to, take care of these concerns, right?

[00:30:09] **Adam:** So the finance department is looking for fraud and whatever else sorts of things. And, you know. I did a quick straw poll of the, when we had people on for a book club and nobody, not a single person raised their hand and said that they work at a company that produces something other than software. And so, for me, that was a, it was a little bit of a, for lack of a better word, I'll just say a plot hole.

[00:30:32] **Adam:** Like it was just too easily waved away. Like, oh yeah, they'll, they'll take care of it. and I think it was ultimately they were trying to make a point and they made that point that like, you know, only work on the stuff that actually matters. You know, don't be redundant. It was, it was frustrating to me because I, and I think it, it, it reflects, maybe not an attitude, but like a positioning in time that is becoming, increasingly not irrelevant, but, uncommon or you know what I mean?

[00:31:02] **Adam:** Like the more and more company, more and more developers are working for companies that are producing something other than, or that are, I'm sorry, that are only producing software. So compliance. It's going to be more and more important and not less and less important for people.

[00:31:19] **Ben:** I think about that too, when I listen to people like Uncle Bob Martin, where he talks about how you should author code and how important it is to have safe code that's open to extension, but closed to modification. But I have to take it with the perspective that he came up in a world where he was writing software to chips.

[00:31:41] **Ben:** That were being burned onto motherboards that were being sent out into the world. And he didn't have an option to update those, or if he did, he couldn't necessarily change it in a way that, you know, if I deploy something and it breaks, I can just roll it back or I can quickly roll forward with a, with a hot fix and like, yes, all of the same principles apply to some degree, but they don't all have the same kind of.

[00:32:06] **Ben:** Criticality that they maybe did at one point,

[00:32:11] **Adam:** Yeah, when you're writing for the web is a lot different than like writing operating systems or embedded systems for

[00:32:17] **Ben:** or even just like shipping out a CD with the software on it.

[00:32:22] **Adam:** Okay, cool So that's kind of book club. I guess a couple of format notes on book club going forward We did a little polling of people there I think in the future when we do book clubs We will do like every two weeks instead of every week make it a little bit less of a commitment to try and show up Covering larger sections of the book instead of like three chapters.

[00:32:41] **Adam:** Maybe we'll do ten chapters or something like that People seem to like having a recap during the show, which is why we did one tonight, and why we will keep that, facet of the book club. And then, that's about it.

## [00:32:54] Ben is Narrow Minded

[00:32:54] **Adam:** so, okay, moving on. Ben is narrow minded.

[00:32:59] **Ben:** True. Cool, cool, cool, cool, cool, cool, cool, cool.

[00:33:02] **Tim:** Good show. I

[00:33:04] **Ben:** so we wanted to talk about database tables and I had, I think maybe mentioned in the previous episode

[00:33:10] **Adam:** He did. I was wondering if, I'm not sure if it was in the episode proper, or if it was in the after show that it came up.

[00:33:16] **Ben:** maybe that may have been in the Discord chat also.

[00:33:19] **Adam:** It came up in Discord, and that's why we decided to like make it, go ahead and make it this episode, and not like some future episode.

[00:33:25] **Ben:** I think the thing that triggered it was I was talking about tracking time zones for a user and how

[00:33:31] **Carol:** yes, yes. Mm hmm.

[00:33:33] **Ben:** old Ben instinct would have been to say, I already have this user table, I might as well just go ahead and add a time zone offset column to this user table, but that new Ben. Was no, I actually want to have a table that's dedicated to perhaps location user time zone, something to that effect and and as a broader concept, I'm trying to lean into the idea of having more tables that are narrower in scope than having fewer tables.

[00:34:02] **Ben:** That are larger in scope and this transformation in my perspective on data modeling is, is let's call relatively recent, maybe in the last five or six years, and it started at work when we had a user table and we were tracking, I think it was, we were tracking two things. One was the user's IP address and the date that they last made a request to the application.

[00:34:31] **Ben:** So I think it was actually the last request date. That was the most problematic here. So if you could imagine that we had a single user table and the columns are growing over time, and at some point we had last request at column and every time the user makes a request to the database or to the application, we update that database with that database column with the current date time.

[00:34:53] **Ben:** And when the volume of the application was small and the number of users was relatively small, it was an innocuous amount of IO on the database. As the application itself became more robust and functionality and we were triggering more parallel requests and there was more users and there was just more inputs and outputs and network requests happening.

[00:35:14] **Ben:** What we found was that having to update this last request at column in parallel with requesting it for a lot of places that we were rendering that information or using it to color online offline status, that we were getting a lot of lock in contention around these rows. And that was, we solved that at the, at the time by just updating that column less often.

[00:35:39] **Ben:** Instead of updating it every time the user requested first, we're like, well, if the last request was within 60 seconds, then don't bother updating it. That 60 seconds became three minutes and then five minutes and then 10 minutes. And we kept increasing that latency because we were continuing to see problematic locking around these user records. And. What I started to think about was that does that information, should that information be in the user table and I didn't explore it more deeply in terms of those particular records, because that would have been kind of a nightmare to change at that point. But as I started to think about new database tables going forward, I kept thinking about how can I slice this off into its own thing rather than trying to fold it into something that exists.

[00:36:29] **Ben:** And I think that that has a number of benefits. One is that the number of records can sort of scale independently, meaning not every record has to have an associated set of values with it. So, you know, we talk about last request set date, that makes sense, that every user might have a last request set date, but not every user might have a billing address.

[00:36:58] **Ben:** So I think it would make sense to have a billing address table, not necessarily billing address columns on the user table because you might have a million users and only 10,000 billing addresses. So why fill up all that space? And then other advantages or other things I started to think about were this concept of, I call them archive tables.

[00:37:17] **Ben:** That's just the term I made up. I don't think that's an industry term in any way. But we used to have a lot of started at, ended at date stamps in records. So you could say, Hey, this user was a member of this organization from this date to this date. So we would often look to see what's their active membership by give me all the records where the user ID is this and the organization ID is this and the ended at is no, but now the problem is over time, you just get more and more cruft in that table.

[00:37:47] **Ben:** So what I started to do was instead of having. A memberships table, I would have an active memberships table and an archive memberships table so that instead of when a membership ends and having an ended at date, I would literally move that record from the active table into the archive table and the archive table could have more columns like the ended at date so we could store stuff like this and it just feels like the data continues to make more sense and continues to be more, specific and what it's trying to, Portray within the domain, and by breaking off these smaller More focused models, you can have them evolve my, I'm not, I'm not getting my right words here, but

[00:38:35] **Adam:** are hard.

[00:38:36] **Ben:** words are hard.

[00:38:36] **Ben:** We've talked about this recently. but it just, it just feels like there's, there's an immediate upfront cost. Oh, I got to create more tables. I probably have to have some additional data access layers. Like it's just. There's some more mechanism. there's more mechanics that has to be put in place, but ultimately I'm finding in the long run that there's more value to having smaller, more focused tables, but there was a, there was a lot of words.

[00:39:01] **Ben:** I kind of just puked this idea into your ear holes.

[00:39:04] **Tim:** isn't that the whole point of a relational database to have like very small, narrow.

[00:39:11] **Ben:** there, there's a, varieties of Bacchus normal form, right? Or wait, is BNF, is that all of the denormalization or is that just like one level? No, that's like all of them, right?

[00:39:23] **Adam:** I don't remember. I, you know, to be honest, I'm, I'm a little on the, I'm a little surprised that you actually know that that level of, of knowledge

[00:39:33] **Ben:** I took, I took one database course in college.

[00:39:36] **Adam:** Was it, was it relational calculus?

[00:39:39] **Ben:** No, no. It's, it was database relational databases.

## [00:39:42] New Tables vs New Columns

[00:39:42] **Adam:** Okay. Yeah, I took a relational calculus course and I was gonna reference a few things from that, but that was all based on the way that you were talking about this last episode just like saying, you know, old Ben, or sorry, new Ben would Want to put the time zone out in a separate table. And I'm like, no, don't do that.

[00:40:01] **Adam:** Yeah, so, okay, a couple of things. I love that this comes from a place of problem solving. It's not premature optimization. It is, we had a problem, there was database contention, and we tried to find a way to solve it. And I think that that is the purest approach to changes, right? It's either generating, it's one of three things.

[00:40:28] **Adam:** You're trying something new, you are fixing a problem, or you're doing to do right, right. Exactly.

[00:40:34] **Adam:** and so I like that this came from that. The, the other thing that I misunderstood you last episode was like, it sounded like you were just like, okay, well, you know, time zone is kind of its own thing. We'll just put it out in a separate table.

[00:40:46] **Adam:** And I'm like, well, but everybody has a time zone. and

[00:40:50] **Ben:** be clear, splitting off timezone may not make sense. It, it was, it, you know.

[00:40:55] **Adam:** So when you use the example of an address earlier, and I think that that makes a lot more sense, right? Like not everybody's going to have a business address. And so you can save yourself some storage space and, you know, some computational time. That's the other side of that coin, right? So for example, one of the reasons that I wouldn't like time zone out in its own table is, you know, you don't want to get into a situation where just to look up some basic user information, you have to do 30 joins,

[00:41:20] **Ben:** Yeah. No, this is, this is also very true. So another thing, you know, you, the way you think about programming just continues to evolve over time and. Earlier Ben, and I'm not saying that this is wrong, I'm just saying that I'm trying to think about things differently. Earlier Ben was all about how do I join 16 different tables to get the information that I need.

[00:41:45] **Ben:** And I'm trying to worry less about how do I do everything in a single query and I'm, and I'm getting more into the, what are the more simple queries that I can write as long as I'm not creating n plus one problems where I, you know, I get a, I have n products and then I have to. Make an additional request to get additional data about those products.

[00:42:10] **Ben:** As long as I'm not falling into that trap, I'm, I am becoming more comfortable with the idea of this could have been one large query, but it can also be three much smaller, much more straightforward queries. And I, and I want to try that more. And I'm not saying that's better. I'm only saying that I'm playing around with what the trade offs are between complexity and performance.

[00:42:39] **Adam:** That's what it is. There's, there's trade offs, right? So simpler organization, simpler querying, versus storage space. And well, there's other things too. I think we've talked about it in the past on the show. Like, I have hit a limit at one point in MySQL where. It wasn't that we ran out of allowable columns, but you can only have so many indexes on a table,

[00:43:02] **Carol:** Ooh.

[00:43:03] **Adam:** or it may not even be the index count, but like the

[00:43:07] **Ben:** It was like the number of characters you were indexing.

[00:43:09] **Adam:** right.

[00:43:10] **Adam:** Yeah. It's like some limit on the number of bytes per row that can be

[00:43:14] **Ben:** Right.

[00:43:15] **Adam:** Ridiculous. and so because of that, and we needed to have multiple indexes, we ended up with like a, a and a B table and they're both considered sort of like the root table, but we just need to have them separated so we can have extra indexes to search through this data.

[00:43:29] **Adam:** And we can, as needed, join them back together with the same ID.

[00:43:33] **Carol:** That doesn't sound messy at all.

[00:43:36] **Adam:** I hate it, but it's like the, the least bad solution that we've found.

[00:43:41] **Carol:** I just imagine training someone and being like, their primary table is underscore A and underscore B. No,

[00:43:48] **Ben:** Well, that, the, that's one of the things that I do find problematic with trying to split tables up into smaller tables is that you, it becomes, inserting data is usually not a problem. If I'm going to insert data and it needs to be spread across a couple of tables, that's easy peasy. The thing that becomes problematic or point of friction is, okay, now I need to delete a row from table A.

[00:44:15] **Ben:** And technically the corresponding row should also be deleted from table B, but I'm like, Oh, now I do, I, I probably have to update this in a couple of different places and, or like, or do I have to come up with a way to have some sort of background task that is reconciling the differences between table A and B so that if there's rows in table B that don't have the corresponding rows in table A, they have to be cleaned up.

[00:44:39] **Ben:** And kind of the, the philosophy that I take right now is that storage is cheap. And if I have rows. Leftover in a table that shouldn't be there. It's not the end of the world, but the, you know, when everything is in one table and you can delete one row and it deletes all of the things relevant for that record.

[00:44:59] **Ben:** That is really nice. So again, it, it is about trade offs for sure.

[00:45:05] **Adam:** So once again, you know, I made a bad assumption and I put my foot in my mouth and you're not as crazy as you seem at the face value, Ben, you

[00:45:15] **Ben:** You know, the other nice thing is that. It's easier sometimes from a performance standpoint, it is just easier to create a new table than it is to modify an existing table. If you have a table that has a hundred million records in it, and like most of the values in a column are going to be null or some form of empty by, you know, on day one, you're like, I, you know what, I'm just gonna create a new table and that'll be immediately available.

[00:45:44] **Ben:** And I don't have to migrate anything

[00:45:46] **Carol:** Yep.

[00:45:48] **Ben:** and that can be pretty nice, especially if you, you know,

## [00:45:51] Number or String Enums

[00:45:51] **Carol:** So, a question. You mentioned like the billing address, mailing address, those type of things. Are you a fan of making a type on the table that says what that? What that address relates to. So like type one means that it's the mailing address. Type two means it's the business address. Or do you store business as a column versus mailing as a column versus home addresses as columns, or do you type them?

[00:46:17] **Ben:** I think my default approach is to have a. Kind of a property lookup table where I have a type ID of some sort and

[00:46:30] **Ben:** Yeah.

[00:46:30] **Ben:** and I don't even necessarily query that table, but I make sure that it's there should I need to join to it and use a like one of the values as a label, but a lot of the times when I have a table like that, I will also have a representation of it in the application logic.

[00:46:48] **Ben:** You know, I can say like this.

[00:46:50] **Adam:** it repeated as an

[00:46:51] **Ben:** types. yeah,

[00:46:52] **Carol:** Yeah, I had an architect, previously look at some code that I had submitted, right? And I did the whole numeric types and he questioned me on why would you do a numeric type when string storage is so low when you're talking about, you know, a five letter word, like, why would I want to go look up a one, two, three, four, five, when you could just put mailing and the cost isn't that much more.

[00:47:18] **Carol:** So. Just where available use the string instead of the numeric for it.

[00:47:24] **Adam:** That's an interesting argument. Yeah. I mean,

[00:47:26] **Tim:** It's, it's definitely more readable,

[00:47:28] **Carol:** is. Yeah.

[00:47:29] **Tim:** Than having a bunch of magic numbers that you got to go

[00:47:31] **Adam:** are we talking about a table that has, you know, 2,000 records in it or a table that has, you know, 2 trillion records in it? Because that's going to be a big total storage difference, even though it's, you know, 4 bytes per. Per record difference, that's going to add up a lot.

[00:47:47] **Ben:** Well, this is always where the, the feebleness of my human brain comes in, where I can throw around phrases like storage is cheap, but I don't actually know what that means, you know, from a practical dollars and cents, does storage is cheap mean that this costs pennies per year, or does it mean it costs, you know, 1,000 a month for an enterprise company?

[00:48:10] **Ben:** That's different depending on, on, on how you think about data storage, I guess.

[00:48:15] **Adam:** Yeah. And I mean, I'm certainly no expert on the topic, but this, this whole thing with like, you know, store the number versus, mailing or business or whatever, I, I'm kind of having just memories are saying this. So it's, it's kind of like a trained gut instinct, but I don't remember the, the, the root information.

[00:48:33] **Adam:** I feel like, indexes are going to be faster if you're operating on integers than on strings, especially longer strings, but if you had like, You know, a three character string that might be fine versus a 25 character string again, trade offs, right? Know your data, know your, your, business model. These are things that have to come into play every time.

## [00:48:57] Naming Join Tables

[00:48:57] **Ben:** The one other thing that I think about with databases, and this is a relatively recent perspective for me, is that early Ben used to love the idea of What I'll call a join table and for those who aren't familiar with this concept, you have two entities in the database or in your application. I have a people entity and I have a parks entity and I want to know which users like to go to which parks and I'll have a user park join table that just basically has a user ID and a park ID column so that I can figure out the associations between the two.

[00:49:33] **Ben:** And I've, I've. Tried to develop a disdain for this. And what I want to do is figure out what that join table actually is. And the hardest part of it is just giving it a word. That describes it a name and I, I want to try to take those join tables and I want to elevate them up into something that I can point at and say, this is that thing.

[00:49:58] **Ben:** So instead of having going back to this user and parks join table, I want to have a table that's like park preferences or favorite parks or something that I can draw a border around and say, I can meaningfully talk about this with English words instead of just saying user park join.

[00:50:17] **Ben:** I feel like this is a graph databases type of problem, right? Is that you're got park nodes and people nodes. And then what do they call the connection between them? Like relationships or, or I don't know, I forget, but it's like nodes and the lines in the circles, but, Paths, axes, vertices. I don't know. But Yes, I know what you're talking about.

[00:50:37] **Carol:** I've seen it with user and a user underscore user permission table. So it would be like, you go look up your user, then you have to go look up every permission that's assigned to that user and the user underscore user permission table, and I'm like, Oh, like, I'm glad I at least can read the name of this to kind of understand what it's doing.

[00:50:58] **Carol:** But then I'm like, Okay, now we have four other permission tables, and where do I go look this up at, because it's not clear on which table we actually joined with, because there's no table called just user permission in the database.

[00:51:10] **Adam:** Well, that's, that's a design problem. I, I, I love, I love these as you're calling them join tables and, and I have, I mean, it's not a written style guide or anything like that, but I, I do personally enforce this in our stuff is if you have one of these join tables, it is, you know, it's like a person ID and park ID, right?

[00:51:29] **Adam:** And you've got a person table, you've got a park table. and the, the join table would be called person underscore park,

[00:51:36] **Carol:** Yeah, I probably would end up with like a person underscore recreation area. Like join, I'm like, where does this even go? Like, I think as long as it's named well, it's good, right? Like, as long as I can read, know where it's going. But when I have so many options, I'm like, this doesn't make sense anymore. And every time I spend time trying to figure out where it went.

[00:51:54] **Carol:** So,

[00:51:56] **Ben:** Yeah, and to be clear, I am not poopooing on a joined table. I have loads of joined tables.

[00:52:01] **Carol:** yeah, they they do great when you need them. Yeah.

[00:52:04] **Ben:** yeah, I, I'm only challenging myself to see if I can come up with a name for that thing. Because what I find is that if I can come up with a name for that thing, then I actually discover That there is more information that I want to store about it than I at first thought. And that's, that's really the thought exercise there is. is how do I discover more about the thing that I'm trying to, to model in the database. It kind of, one of the ways that I like to think about it is that on a join table, you would typically have a compound primary key. So that you have, you don't just have user ID as the key or park ID as the key. The primary key for the table is both user ID and park ID. And this enforces uniqueness constraints on the table and does all kinds of good stuff.

[00:52:54] **Ben:** But I think to myself, what value could I get if it had an auto incrementing primary key, but then it also had a user ID and a park ID, would there be a value there? And what would that be? And if I can start to think about what that thing would be, then I can start to think about what other information I could access quickly by having A, a generic ID.

[00:53:16] **Ben:** Yeah.

[00:53:17] **Adam:** Yeah. I'm trying, I can't think of the concrete example, but I remember doing that. You know, I started out as a joint table, just like user, person ID and a park ID, and then it becomes like, you know, there's, it's a relationship between two entities and that relationship itself can have properties.

[00:53:31] **Adam:** Right, like, this is,

[00:53:32] **Ben:** is also an entity somehow.

[00:53:34] **Adam:** right, like, the relationship, the, the preference to go to that park can be retired, but you want to know that they used to like to go to that park, right, and so you have like a, a, an archive date on it or something, right, and, and in that case, yes, then you, then you kind of want to add like a surrogate key to that column, to that table, sorry,

[00:53:52] **Ben:** Yeah, and one of the most recent things that I've had to do at work is I've, we have documents at work, and I've created a way for people to apply tags. A tag just being an arbitrary label. You know, this is my beta tag or this is my Acme corporation tag. And then I can search for documents based on tags and,

[00:54:11] **Adam:** not a _(quack)_ show at all,

[00:54:13] **Carol:** 20,000 tags later.

[00:54:15] **Ben:** yeah, yeah. It would be, you know, a document, it's 1700 tags on it. Obviously the UI should handle that. but. It would have been very easy for me to just say, well, I have a document table and I have a tag table, so I should have a document tag join table. But then I'm like, well, maybe I want to record the user who put the tag in place and the date at which they put that tag in place.

[00:54:40] **Ben:** And now I have. A document ID and a tag ID and a created by user ID and a created at date. I'm like, this isn't really a join table anymore, but I just don't know what to call it.

[00:54:52] **Adam:** now you're talking about like audit information,

[00:54:55] **Ben:** Well, it, yeah, right. Well, all that information is, yeah, that can go off in a whole other direction, but I'm just saying when you, I ended up calling it a tagging.

[00:55:04] **Ben:** And you know, like, like graffiti art almost, right? I think that,

[00:55:08] **Adam:** It's like when you're eggs,

[00:55:10] **Ben:** yeah, so a user is tagging a document with a tag. And now that I can call it a tagging, it can conjure up. More rich information that then I might want to store additionally on the table. I'm not saying that I have that information at hand right now, but I'm just saying that it opens up the, it opens up the possibility to start thinking about the operation and the data in a different way.

[00:55:36] **Carol:** Yeah. But can, are tags shared between users?

[00:55:39] **Ben:** Well, that's okay. I mean, that's a whole other. So

[00:55:42] **Carol:** I mean, like, I was like, why would he need to know what user created it if the user only has their own tags?

[00:55:48] **Ben:** I mean, so I mean, as a quick aside, our system, it's such a. It's such a nightmare when it comes to how certain things interrelated, it's like this weird social web of of interconnected data, and it brings up some really interesting security problems. So let's just say, for example, that Adam and I are working together and I have a document and then I tag it with.

[00:56:14] **Ben:** let's

[00:56:14] **Carol:** Working code pod.

[00:56:16] **Ben:** I tag it with working code pod and and so let's now say that Adam starts up another document and he says, Oh, this relates to working code pod. So let me apply the working code pod tag, which I've already seen elsewhere now, unbeknownst to Adam. I go and I, talk to Chris Coyier, and I want to get on the, the Shop Talk Show podcast, and so I create a document, and I put a Shop Talk Show tag.

[00:56:42] **Ben:** Well, Adam and I have worked together, but do I want him to see that I have created a Shop Talk Show tag? Like, that feels... There's a security problem there that I'm I'm leaking data that Adam probably shouldn't see so now I have to only show Adams the tags that he's seen by way of the documents that we've collaborated on and then be like, Oh, I didn't store this right?

[00:57:04] **Ben:** This definitely should have been stored in a different way. Anyway, there's all kinds of weird complexity when you get into how people relate to. Data through other people. And

[00:57:13] **Carol:** It is.

[00:57:14] **Ben:** it's

[00:57:14] **Tim:** that sounds like that'd be solved more through like a different type of database.

[00:57:18] **Ben:** something went wrong.

[00:57:19] **Tim:** graphic, like a, like, like, like a graphing database.

[00:57:22] **Ben:** You know, sometimes you just have to move fast and break stuff, I think. And,

[00:57:26] **Tim:** I've heard that before.

[00:57:28] **Carol:** Couple times.

[00:57:29] **Adam:** Shall we wrap it up there?

[00:57:30] **Ben:** yeah, I, I don't have too much more to say on that. Other than, other than I, I, I like, I'll only say this to close out that. I like the idea of challenging myself to think about the data. Differently, because it gets me out of my comfort zone and, and, and forces me a little bit to explore some different ways of wiring stuff together.

[00:57:54] **Ben:** And I think that good things must come from that exploration.

[00:57:59] **Tim:** For sure.

[00:58:01] **Adam:** Good thoughts, Ben.

## [00:58:03] Patreon

[00:58:03] **Adam:** this is where I'm gonna let you know that this episode of Working Code is brought to you by Bacchus Normal Form, which has absolutely nothing to do with database normalization.

[00:58:09] **Ben:** no!

[00:58:11] **Adam:** It is instead a metastatic, I'm sorry, metasyntactic notation used to specify syntax of programming languages.

[00:58:19] **Ben:** Obviously.

[00:58:20] **Adam:** Obviously, as you do, but it's, it's brought to you by Back as Normal Forum and listeners like you. If you're enjoying the show and you want to make sure that we can keep putting out more of whatever this is into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:58:39] **Adam:** Special thanks to our top patrons, Monte and Giancarlo.

## [00:58:43] Thanks For Listening!

[00:58:43] **Adam:** we are about to go record our after show, which is one of the perks of becoming a patron of the show. you get to listen to us continue to ramble on about whatever's going on. Uh,last week I inadvertently destroyed Tim's memory of his, first time he kissed his wife.

[00:59:01] **Tim:** Sorry, Tim. That's all right. I think I'll survive. Trust me. I'm not, when I, when I think about that, I'm not thinking about you, buddy.

[00:59:08] **Adam:** good. I'm glad I'm glad I didn't ruin it forever. Maybe just for a couple of weeks Anyway, if you'd like to get a taste of that, you know, you can go to patreon.com/WorkingCodePod that's gonna do it for us this week. We'll catch you next week. And until then,

[00:59:23] **Tim:** Remember your heart matters. And so do your joint tables. I'm
