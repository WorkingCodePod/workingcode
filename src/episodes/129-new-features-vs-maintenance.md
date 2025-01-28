---
title: "129: New Features vs Maintenance"
description: "On today's show, we talk about the tension between Engineering, Product, and Design and how we might work to mitigate it."
date: 2023-05-31
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/129-new-features-vs-maintenance/id1544142288?i=1000615141759"></iframe>

When Engineering, Product, and Design (EPD) come together to create the first version of a given piece of software, it feels like everyone is on the same page and has the same priorities. But, once that initial implementation ships to users, the Product and Design departments tend to move on, leaving engineers to maintain the software. This creates an uncomfortable tension between the existing user experience (UX) and the underlying technical details. On today's show, we talk about that EPD tension and how we might work to mitigate it.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/129-new-features-vs-maintenance.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** One thing that always surprises me when you talk about matters of scale is it's, you would think that it would sort of be a linear progression, right? but that's usually not how it works

[00:00:08] **Carol:** what happens.

[00:00:09] **Tim:** No, it's usually It just is like, alright, you're chugging along, chugging along, and all of a sudden it's like that one extra request that breaks the camels back and like hockey sticks up, right?

[00:00:19] **Tim:** It just shoots up and it's like, oh, it's not, it went from being okay, slightly sluggish on occasion to just being unusable

[00:00:26] **Carol:** Yeah,

## [00:00:46] Intro

[00:00:46] **Carol:** All right guys, it's episode 1 29 and on today's episode we're gonna talk about the Great Divide Donez product versus supporting the product, and where does that fall? So, as you can tell, since I am bringing us in, that means Adam is not here. He is out today on some very fancy board meeting, but hopefully he'll be back next week and not too burn out to join us.

[00:01:09] **Carol:** So let's kick it off. like normal with our triumphant bells. And this week starting us out is a bin. What you got for us man?

## [00:01:16] Ben's Failure

[00:01:16] **Ben:** Unfortunately, I'm gonna kick us off with a little bit of a failure here. I've been feeling just very generally, ma. across the board, both professionally and personally. And, I think as a side effect of that madness, I'm, I'm having trouble launching into a new project. I think I had mentioned on one of the previous episodes that I'm interested in building little fitness tracking app for myself if, for no one else.

[00:01:40] **Ben:** And, I have it in my head and I just can't seem to pull the trigger on moving forward with it. you know, I had done a couple of months of research on some on Hot Wire as a potential foundation for building the front end, and I'm, I'm kind of cold on that. So now I wanna go back to using Angular and even, even with that decision having been made, I'm, I'm just struggling to put code on paper, so to speak, and to start moving forward.

[00:02:07] **Ben:** I think part of it is that the. I think I was holding it in my mind that these technical hurdles were the thing holding me back. And now that I have a technical plan in mind, what I'm realizing is that, oh, I probably also need a design and something sort of layout to the application, and then I'm gonna be using it on my phone.

[00:02:28] **Ben:** So does it need to have a mobile layout, you know, responsive layout that looks good on mobile and on desktop, even if I probably almost will never use it on desktop, and it's like suddenly. You know, you, you have this vision of something that could be built, and then there's the reality of all of the things that go into a project that you don't necessarily think about.

[00:02:47] **Ben:** And, and that's kind of hit me and I'm having trouble getting past that realization. So,

[00:02:53] **Carol:** But it's a true problem to think about though, and that's where my brain goes is the, the app I use for the gym is J Fit and it's great on my phone, but I think I tried using the website one time and it was not even usable. It was only developed to be used on a phone. So when I'm talking about wanting to build out a plan, I wanna be on my monitor and I wanna have my plan on one side, another plan on the right, and I wanna pick and choose and build my daily routine in so, I needed to work on both.

[00:03:23] **Carol:** And so far I've not been able to find an app that does that. So I think you're right to try to solve that because from what I've researched, there's not a good solve for it yet in the market. So,

[00:03:32] **Ben:** Yeah, and I think it's the, the, just the grandness of it. That, is holding me back. And when I come up across this problem at work, meaning some large effort that I have to put into play, usually I approach that by just taking it and breaking it down into a lot of smaller problems. And then just doing the work and moving things across the con bond board and, and step-by-step making progress and.

[00:03:58] **Ben:** Maybe like that's just what I need to do. I, I think part of it is I'm so used to working in a project management system like Jira. Like I think I need to make a Trello board

[00:04:07] **Carol:** Trello. Trello, yes. Yeah,

[00:04:09] **Ben:** that I can, I can treat it like it's an actual thing and not just,

[00:04:13] **Carol:** absolutely.

[00:04:14] **Ben:** yeah, I have to get over this idea that I'm gonna build it in a weekend and it's gonna be done cuz that's just not how it's gonna work.

[00:04:19] **Carol:** So, If you're looking for suggestions, look at Asana too, because with all of my contracting stuff that I've been doing, asana's been great for me. So with Asana I can create different workspaces. I'm like, okay, this is my personal life kind of goals, and I can have the same kind of feel that I have with Jira, but not, and it's slightly different than Trello.

[00:04:39] **Carol:** Like take a look at the sauna. You might like using that instead of Trello to manage it, but it gives you the ability to move things in swim lanes and gives you the right feel for what we do on day-to-day.

[00:04:49] **Ben:** Nice. All right. Yeah, I'll take a look. I. Think I'm, I'm pretty sure I've seen them advertised on YouTube and, and the radio and stuff.

[00:04:56] **Carol:** I have the free account and it's working great. Still. I haven't had a need to upgrade, but yeah, for me also the, , the thought of like picking up a new project is that starting point.

[00:05:06] **Carol:** It's very scary, like picking out technology, picking out where I start always intimidates me. I do a lot better when I go into a project that's already established and they say, Here's problem X, Y, and Z. Go solve it. And I'm like, heck yeah, that's my game. Let's go play this. But when it's like, pick out what, Zach, we wanna put this on, I'm like, oh God, I'm gonna end up in analysis paralysis, because I never stop looking for other alternatives.

[00:05:32] **Ben:** Yo fo Joe.

[00:05:34] **Carol:** Well, good luck, man.

[00:05:36] **Ben:** Thank you. Thank you. So that's me. Carol, what about you?

## [00:05:39] Carol's Failure

[00:05:39] **Carol:** All right guys. I've been talking about it for, you know, going on four months now. You know, I've been doing some contract stuff and been, you know, doing things here and there, but I throwing in the towel a little. I have accepted a full-time job. Yeah, thanks. Thanks. Working for big old Uncle Sam for a minute, so I'm gonna take a government job for a bit.

[00:06:00] **Carol:** The stability is definitely needed. The thought of not knowing what's next was getting to my brain a little. So gonna, you know, take a job, do some work, and still have lots of time on the side to keep my stuff going and to keep building that up. And they know going into it that this is only, like an interim for me.

[00:06:17] **Carol:** Like I just wanna do this while I get everything else going. And they said they'll take whatever time they can get from me because it's people I've worked with in the past. So gonna go that route and then, just see what's next after it. But gonna be working 40 hours for the big old government for a bit and then, you know, some free time still building my stuff.

[00:06:36] **Carol:** So excited to see where it lands. And I'll keep you guys posted.

[00:06:40] **Ben:** Is there a particular branch of government or department that I mean, you don't have to say anything if you don't want to, but I'm curious.

[00:06:47] **Carol:** Yeah, it's o p M, it's the, the personnel side of, of the government. So it's Office of Personnel Management.

[00:06:54] **Ben:** I dunno what that is, but it sounds, sounds very peopley.

[00:06:57] **Carol:** It's basically how the government handles HR and how they handle hiring people, onboarding people, paying, yeah. Lots of training stuff. So,

[00:07:07] **Carol:** It's also what got hacked a few years ago, just letting you know that.

[00:07:14] **Ben:** is will they be doing any ColdFusion, just outta curiosity? I know.

[00:07:18] **Carol:** nope. they have some ColdFusion stuff, but it's not what I'll be working on. I'll be working on, type scripts. I'm trying to react. I'll be working on, View and there was one more that they're trying to go to. I don't remember what it is off the top of my head, so that's gonna be kind of my focus for a while. So, yeah.

[00:07:35] **Ben:** Very exciting.

[00:07:37] **Carol:** Yeah. Yes.

[00:07:37] **Tim:** cool. Well, good luck.

[00:07:39] **Carol:** Thank you. Thank you. Yep. I'll let you guys know when I officially, officially start, cuz I told them I was going on vacation to Disney the end of June, and I'd needed a little time to get through graduation and moving first. So, yeah.

[00:07:50] **Ben:** Yeah.

[00:07:51] **Carol:** Cool. All right. Let's see. What about you? 10?

## [00:07:54] Tim's Failure

[00:07:54] **Tim:** Well, it looks like all three of us have failures today. This is, yeah. We're just, we're just, we're just riding the FA struggle bus. So my, my failure and mine's not a big failure, it's just my brain hurts. I just got you

[00:08:07] **Carol:** Oh man.

[00:08:07] **Tim:** my, my brain was just hurting today. I was trying, I was just struggling just to, to even put thoughts together today, just where I, it was a long weekend.

[00:08:16] **Tim:** We've been doing some home projects, putting down new flooring and, you know, into the years it was all this stuff going on with the school for the kids

[00:08:23] **Carol:** Oh, I was about to be like end of the year. It's July, June,

[00:08:26] **Tim:** Yeah. End of the school year. Yeah. Yeah. Yeah.

[00:08:28] **Carol:** Don't listen to my calendar time.

[00:08:31] **Tim:** We got, we got my in-laws coming from Ireland in a couple, you know, less than 10 days. So it's like so much stuff just going on. So it's just, yeah, my brain just hurt. So, yeah, I don't, don't really have any exciting to say other than just, yeah, I, I'm, I'm, I'm surprised I'm even here on this, this podcast today cuz I don't know how much I'll be able to offer cause my braid is just not in gear.

[00:08:55] **Carol:** Yeah, my husband tends to text me like how stressed out he is at work or something. I'm like, man, dude, adulting. It sucks, right? Like these things we have to do as adults. No one prepared me for what it costs to put in new floors for your house when you're leaving, or replacing carpet that your puppy decided to chew up during the podcast because you get in the crater one night like, Adulting.

[00:09:17] **Carol:** Oh my God.

[00:09:20] **Tim:** Yeah,

[00:09:21] **Carol:** Well, I hope your brain gets better soon.

[00:09:25] **Tim:** Thanks.

[00:09:28] **Carol:** All. So we roll into the.

[00:09:31] **Ben:** Let's do it.

## [00:09:32] New Features vs Maintenance

[00:09:32] **Carol:** So I think we're going to talk about, product versus support once a product is delivered. So this being said, because one of our, Patreons, asked about something that Ben mentioned on episode 1 26 where he talked about delivery versus supporting the product. Meaning that the idea that product and engineering come up with an idea of what the product should look like and what we're gonna deliver.

[00:09:55] **Carol:** But once it hits the shelves and people start using it, Usage falls back on the shoulders of engineering. So you wanna dive into that, Ben?

[00:10:05] **Ben:** This is something that, having been maintaining a product for 10 plus years now there's, you get past the honeymoon phase of product development, right in the, in the beginning. Everyone's on the same page. We have a vision for what the product is gonna be. We have a vision for how the product is gonna be used.

[00:10:23] **Ben:** We've talked to some customers, they're on board, we've shown them some prototypes. They like what's going on, and then we build it. And of course, because there are budgetary and marketing deadlines, we build it, you know, in the style that gets it done, not necessarily in the best practices across the board.

[00:10:42] **Ben:** And I think that that makes sense in most cases because you don't necessarily have a sense that you've proven the product, right? You want to build the product, get it into people's hands so that they can tell you whether or not it's a product market fit. So you get that version one out into the wild and everybody's excited.

[00:11:00] **Ben:** The users like it, product team likes that. Everyone else is liking it. And then the product team moves on and they start developing a roadmap. New features, evolutions of existing features, and the user base grows and people continue to use the product. More people continue to use the product, they continue to use it in different ways and use it to solve different problems.

[00:11:19] **Ben:** And suddenly the. I don't wanna call it the MVP or the proof of concept, but let's just call it the version one of your software isn't necessarily holding up the way it used to, given the volume of data, the volume of requests, et cetera. And what we find, at least where I work, that solving those nascent problems of performance tends to fall on the shoulders of the engineers.

[00:11:46] **Ben:** The engineers have to use the current interface for the application as the source of truth, and then kind of below the surface try to fix whatever performance problems might be appearing. and that's, that's very challenging because you, that's a, it's a lot of constraints to have to live with. And I think ideally what should happen is that just as we did with version one of the product, we're.

[00:12:12] **Ben:** Product and engineering and design all come together to build something when we have to address performance issues. I feel like we need that, that co-location of minds. Again, we need product design and engineering to come together again to say, okay, now that we see how people are using the product, how can we evolve it in a way that is a good combination of performance and developer experience and user experience?

[00:12:34] **Ben:** And we just almost, I almost never see that happen.

[00:12:38] **Carol:** Great point. Good show. No, I mean accurate, right? Like it happens all the time. Like we see things get delivered. I always think of like what my son said, like all through high school. He was like, Hey, mom, seas get degrees, right, like seas get degrees. That that's all that matters is. I got it out there, it passed, and we're good to go now move on the next thing.

[00:12:59] **Carol:** And so often product is already allocated to working on the next new thing. But they don't have time. They don't have something built into their schedule that says, oh, by the way, we're releasing this and every week for the next six weeks. Like, you need to block off a week to go back into what you created and make sure the team's actually able to use it.

[00:13:19] **Carol:** Instead, they're on to something else and now you're just stuck dealing with it. And it's, that's a challenge everywhere. I've been like, that's, that's nothing that's changing from what I've saw, Tim.

[00:13:32] **Tim:** No, no, definitely. I mean, and then you. Struggle with the is is, you know, is what you're trying to do. Is that a feature request or is that really, are you fixing a bug? Right, so maintenance, typically they say maintenance shouldn't be delivering new features, but sometimes it's like you've got an incomplete feature or a buggy feature, and really the only way to fix it, it.

[00:13:56] **Tim:** Is to expand the feature, right? And then products like their butt hurt. Cuz they're like, well you guys shouldn't be, you know, changing the design of the product. but, you know, you're, you're not really, I mean, it is just, it seems to be the only sensible way to fix it, otherwise it's completely broken. So you got that struggle.

[00:14:15] **Tim:** and then products like, well we don't have to, you know, that's not on our roadmap, right? They've already moved on to something else. I, I do think product teams should. Scheduling 20% of their time for technical debt. And you could sort of say that, that these. Bug slash quasi features or technical debt that really needs to get done and have them work.

[00:14:37] **Tim:** You know, they don't have to do it all, but work with you on fixing the solution because, you know, a person in maintenance or support, they might not solve the problem a way that, like a system architect who designed it from the beginning would suggest, right? They just want to squash the bug, whereas, Whereas an architect might say, well, you know, there's that change you can make on the structural side of the code that could actually solve not only this, but other issues that you might be running into.

[00:15:04] **Tim:** But without that conversation, it just, you, you're slapping band-aids on, on the, on a problem constantly. And that's, and then that's how you get into huge amounts of technical debt because the band-aids just compile.

[00:15:17] **Carol:** Yeah, the, the bandaid analogy is exactly what I thought of is that if you don't have your product team coming in, you're gonna have your maintenance and support team basically banding, you know, the bleeding at the moment that it happens without really thinking back to, oh, like maybe I shouldn't have stored this this way, and maybe I should have stored it a different way.

[00:15:34] **Carol:** Or maybe these should be linked slightly different where someone coming in is just gonna throw in like, You know, it's gonna sound stupid, but let me just put an index and make it a little faster or something. When in reality that data shouldn't be linked together. So getting your architects back in, getting your product team back in, like you said, that 20%, like if a product team knew that 20% of their time was allocated to a, a quote maintenance window to support what they designed, maybe they would also think through problems that they're solving a little better to upfront than just kind of coming up with ideas and handing it off to the next person to support.

## [00:16:12] Scaling

[00:16:12] **Ben:** I think also part of the issue is that. At some point, the problems that you have to start solving are problems of scale. And problems of scale are one, I think problems that a lot of people don't have a lot of experience solving. You know, we joke about, oh, that's a good problem to have, but the reality is it's a, it's a good problem to have because it might be a sign that the business is doing well, but it doesn't mean that it's a enjoyable problem to have.

[00:16:38] **Tim:** Right, or to try to fix.

[00:16:40] **Carol:** Yeah.

[00:16:41] **Ben:** so it's, I think it's one that it's, it's a type of problem that a lot of people, myself, very much included, don't have a tremendous amount of experience with, and they're just not problems that are very easy to solve. And. And, it's tough in the early stages of a product when it feels like you can just crank stuff out because you're taking shortcuts and the application logic is relatively simple and the volume is relatively small.

[00:17:06] **Ben:** And you, you get the sense that, well, we can just keep doing that, but doing it in different ways. But once you hit a scale problem, you can't just rip it out. I mean, you gotta, you gotta really rethink the way things are architected and the way data is flowing and it's. It's just, it's like suddenly something has to slow down and the product team is not ready for that.

[00:17:26] **Tim:** Mm-hmm.

[00:17:27] **Carol:** Yeah. Cause I feel like if you hit an issue with scale, the people designing it aren't gonna create a better solution. Second go around. Like in reality, like if I create a pro, if I create an application and it can't scale, what are the chances that I can fix the scaling issue? Because I thought what I created was solid.

[00:17:45] **Carol:** My team thought what we created was solid. So if scaling is really the issue, then I need someone else to come look at this because what I did didn't work. And clearly I don't know how to scale this so someone else needs to come help me because I'm gonna just break it a second. Go around like maybe I'll get you up, you know, a hundred more requests or you know, a thousand more requests.

[00:18:05] **Carol:** But then we're gonna need to scale again and someone better needs to be like on this helping me cuz I didn't do a good job.

[00:18:12] **Tim:** Hmm. One thing that always surprises me when you talk about matters of scale is it's, you would think that it would sort of be a linear progression, right? You know, you add 20% more requests and you know things are gonna get 20% slower, but that's usually not how it works

[00:18:28] **Carol:** what happens.

[00:18:29] **Tim:** No, it's usually yes. It just is like, alright, you're chugging along, chugging along, and all of a sudden it's like that one extra request that breaks the camels back and like hockey sticks up, right?

[00:18:40] **Tim:** It just shoots up and it's like, oh, it's not, it went from being okay, slightly sluggish on occasion to just being unusable

[00:18:47] **Carol:** Yeah,

[00:18:48] **Tim:** and there's snow in between.

[00:18:50] **Carol:** yeah, like we, I think Tim and I had saw this before when we were talking about just, like an application being able to print documents, right? So it went from, okay, we can print them to where if one more thing kicks off the print, suddenly you're at 98% C P U usage and there's no memory left on the machine and you don't know why one more caused the problem, but.

[00:19:10] **Carol:** We were running fine until that one hit, and you know, there is no gradual increase to the problem. It was just there and then dead.

[00:19:19] **Tim:** Yeah,

[00:19:19] **Carol:** Yeah.

[00:19:21] **Tim:** I've seen that with data, with data structures. You know, you, you don't, you know, like, oh, we'll never need an index on that. And then, and, and then all of a sudden it's like, you know, this query is like taking really long time. It's, it's slowing everything dead, dead locking stuff. You're like, oh, you popping index on there now.

[00:19:37] **Tim:** Okay, now it's better. But it wasn't gradual. It just went from, yeah, from okay to just garbage.

[00:19:45] **Ben:** Well, I, a couple years ago I used to work with this, database. We had a database manager named Brad Brewer. And, he was super great guy and he was wor, he was always very hands on with me trying to get me to learn more about data structures and how databases work. And I was on this kick of looking at our slow query logs and, and said, oh, you know, this query.

[00:20:05] **Ben:** It has a suboptimal index. I can throw an index on there to make it a little bit better. Or, you know, this query is whatever. I, I kept chasing the query log and at one point he pulled me aside and he said, Hey, you know, query optimization is a good thing, but the way you're aggressively fixing things in a slow query log, he, it can actually be problematic because what you're doing is essentially taking all the slack out of the rope that.

[00:20:32] **Ben:** Adding better indexes and refactoring queries. It's like your wiggle room. And what you're doing right now is you're essentially hiding the larger problem, which is that the system is not architected well and you're squeezing as much power out of the database as possible. And what's gonna happen is at some point you're gonna run out of things you can squeeze, and what you're gonna be left with is a poorly performing application and you've already solved all the easy things.

[00:20:56] **Ben:** It's like,

[00:20:57] **Carol:** Oh

[00:20:57] **Carol:** dang.

[00:20:58] **Ben:** is re-architect it now before it's too late.

[00:21:02] **Ben:** And,

[00:21:02] **Ben:** I did not listen, but it was a, it was a good point in retrospect, I think that he was making,

[00:21:08] **Tim:** Yeah. Building a glass cannon, right?

[00:21:10] **Carol:** Yeah.

[00:21:13] **Tim:** Super powerful but fragile.

[00:21:14] **Carol:** Yeah. Holy

[00:21:16] **Ben:** but it's, it's just so tough. And then sometimes as an engineer, I want to go back to the product team and I wanna, I want to build a, a worse user experience that will lead to a better technical outcome. and, and one of the examples that always pops to mind for this is that at work we have a system that allows people to create types of documents and there's four or five different types of documents.

[00:21:40] **Ben:** And these documents all live in different systems. And as a user, you log in and you see your list of documents, and it's a single unified list. and in order to pageant through a unified list, That's composed of four or five different types of things. You either have to have a, a single system that manifests all that data into a single place, or you literally have to go to five different systems on the fly and then try to pull all that data back and then try to pageant through it.

[00:22:09] **Ben:** And, and that can be really bad for performance. So I, I'm always trying to push the product team to break things out into different types. Like, oh, let a user see, you know, a list of this type of document or if a different tab you have a different type of document, a third tab for a third type of document.

[00:22:24] **Ben:** And literally I only want them to do that, not because I think it's a good user experience, it's definitely not a good user experience, but I know that technically I can make that a good experience from a performance standpoint.

[00:22:35] **Tim:** You can make it, perform it.

[00:22:36] **Ben:** Yeah, you only have to deal with one system at a time like that.

[00:22:40] **Ben:** I know how to do that. I know how to build indexes for, and database structures for, but I don't know how to do it all from the same place. And yeah, it's just, there's no easy way to do that. We, we actually, so we had a team at work that built that unified system that brought it all together and it, it, it took them months and months and it, and even on top of that, they still had to make a lot of concessions about the performance. Aspects of it, just brutal.

## [00:23:07] Relationship Between Product and Support Teams

[00:23:07] **Tim:** I think the pushback you're gonna get is. Not necessarily a technical pushback. I mean, people can agree in principle, but it's just in practice. You know, product's, job is to create new products because it generates more revenue, right? You, you, you can't say, oh, we're just gonna be static for the next two years and not build anything new.

[00:23:27] **Tim:** So, so product is always getting pushed to add new features, add new stuff, add new sources of revenue, and there's just not a whole lot of revenue available in, you know, going back and, and fixing. You know, little things here and there, in a way that, a way that's good for the entire project. So yeah, we, you wind up with the support team and, and I ran a support team for a long time.

[00:23:52] **Tim:** It, it was kind of disheartening, right? It's like product would just throw something over the walls as fast as they could and there's a whole bunch of problems in it. And they're like, well, you guys just clean it up. And it, we kind of felt like the janitors of the company, right? It's like, you, you guys could build this better, but you're so pressed for time.

[00:24:09] **Tim:** You just, you just. Toss it over to us and then we gotta clean up. And a lot of times it was the same stuff over and over again. It's like similar problems that's like, this is a known thing. Don't send us this until until, and it doesn't, cuz you know they're moving on to something else cuz there's another contract was signed.

[00:24:26] **Carol:** Yeah, they have deadlines. If they can't. Pass either, cuz there's usually financial penalties when you do. And for me as an engineer on the other side that wasn't doing the support and maintenance, I would get frustrated when I would hear from someone else, just from chatter down the road that what I did didn't work in the way.

[00:24:45] **Carol:** And I didn't know that because like you said, I just keep doing it over and over again because I think what I've, created's good and this method worked and someone else fixed it behind me without telling me, and I didn't know what I was doing was wrong. So it, it took away my opportunity to learn and do better because we just brushed it under the rug.

[00:25:05] **Carol:** So there's a, there's a learning to both sides that's beneficial when you go back to product and say, This didn't work, this didn't happen. This was a problem. Let's talk about it. Let's re-engineer it so that it's fixed in what we're doing now and going forward. You don't do it again. Because like I said, I didn't know.

[00:25:24] **Carol:** I didn't know what I was sending. Tim's team was broken, cuz Tim's team fix it every time, you know?

[00:25:30] **Tim:** Yeah. And I think, yeah, just, it's just a lack of communication between teams, right? And that, that, that tends to be art. Like everyone's got their own priorities and everyone's busy. So it's like, unless you have some sort of ceremony or process where those information can get transferred, it's just gonna continue to be a problem.

[00:25:48] **Tim:** So

[00:25:49] **Tim:** I, I'm just happy now. I have a small team. We

[00:25:50] **Tim:** all just talk to each other every day, and there's no, there's no problem.

[00:25:53] **Carol:** All the days. That's why it's true, like postmortem's good when anything goes wrong. So you have something going wrong. You're like, okay, let's do a postmortem on it. And let's say everyone, whoever touched this needs to be involved with it, so they know why it went wrong. But that doesn't typically happen.

[00:26:08] **Carol:** Typically, we do the sprint, we release it, we move on, and then when the po the, the course, listen to me when the postmortem happens, if there is a problem. It's like your top level people, maybe a team lead, but that doesn't ever get spread back to the rest of the team or to the people who actually wrote it

[00:26:25] **Tim:** I should, but

[00:26:26] **Carol:** should, but it doesn't.

[00:26:28] **Carol:** It ends there because they're working on something else already, so, yeah.

## [00:26:34] Releasing Quick

[00:26:34] **Ben:** I will say though, that I, I, I also don't wanna make it seem like I want to build better solutions from the GetGo. I, I think that there is, I think when we build a good enough solution on day one, I do think that's the right approach.

[00:26:49] **Carol:** Yeah, I agree.

[00:26:50] **Ben:** You don't wanna over-optimize and over-engineer stuff.

[00:26:54] **Carol:** Yep.

[00:26:54] **Ben:** It's just that that only gets you so far and you have to go into it knowing that that'll only get you so far.

[00:27:01] **Carol:** Yeah,

[00:27:01] **Carol:** I truly enjoy releasing quick and releasing early, and checking the adaptability of something like, are the users going to use this? Is this something that makes sense? And once we see that it actually makes sense for a user, then let's adjust. Let's make it better. But until I get it out there and get it in their hands, it's just an idea and something that engineering and product think would be great.

[00:27:23] **Carol:** But you know what? Our users aren't engineers and they're not product people. They're users and they don't typically like what we like. So get it out, even if it's a little ugly, use it and then, you know, iterate on it. Iteration's big, so

[00:27:39] **Tim:** What's the, what's the quote? That there's only two groups of two. Two industries that call their people, users, drug dealers, and software engineers.

[00:27:49] **Carol:** I've never heard that, but that's amazing.

[00:27:55] **Ben:** I freaking love how easy. SQL makes things, I don't know if anyone ever thinks about this, but the, the SQL language as a means to pull data

[00:28:06] **Carol:** Oh, it's so pretty. Yeah.

[00:28:08] **Ben:** so freaking powerful and I think it really allows you to get that, I hate to call it an v mvp, that's collect an initial implementation.

[00:28:16] **Ben:** You get that initial implementation out the door, and you might have queries that are joining. Six, seven tables and you know, that's not gonna scale long term, but, oh man, it makes it so easy to, to build a product from, from scratch. I love it.

[00:28:31] **Carol:** I agree. I agree. I've always had really good experience using sql. When I went to Oracle, I'm like, how do people write these things? There's no top. How do I get the top 10 records? I have to do road number by? What the hell?

[00:28:47] **Tim:** Anytime people would come in like outta college and on their resume, a lot of times, you know, they'd take an IT class, they would have programming and they have different, almost, you know, a lot of times they would have NoSQL, no no database and, and I'd be like, you know, go back, take some SQL core. I mean, that'd be the best thing you do for your career is get, get some good, get some good SQL t SQL under your belt

[00:29:07] **Carol:** Yeah, I agree. Learn, learn that because if you learn SQL then you can adapt into any other like database language from it. Yeah.

[00:29:16] **Tim:** For sure. Well, I guess we've solved the product support divide. Just talk to each other more. Use 20, use 20% of your roadmap for, technical debt and, yeah. Good problem Solved.

[00:29:28] **Ben:** We're just kicking

[00:29:29] **Tim:** Good show guys.

[00:29:31] **Carol:** Well, now we know who the chatty one is. Adam. Yeah. Are we good to bring this home guys then?

[00:29:40] **Tim:** Hey, let's do it. We'll, we'll, we'll, we'll gift you, you listeners, a a, an extra 30 minutes of your time.

[00:29:45] **Carol:** I mean, unless you're a Patreon, then you get the after show and

[00:29:48] **Carol:** it's it's spicy. I hear.

## [00:29:53] Patreon

[00:29:53] **Carol:** So this episode of Working Code brought to you by the last request that broke the camel's back. And listeners like you, if you're enjoying this show and you wanna make sure we can keep putting whatever this is out into the universe, you should consider supporting us on Patreon.

[00:30:08] **Carol:** Our Patreons cover, our recording costs and editing costs. We can't do this without them. and we'd like to send out the special thank you to Monte and Giancarlo.

## [00:30:18] Thanks For Listening!

[00:30:18] **Carol:** So if you wanna help us out, why don't you hit us up at @WorkingCodePod. That's @WorkingCodePod on Twitter, Instagram. Send over your topics or your questions and we'd love to chat about them.

[00:30:32] **Carol:** You can also find us on workingcode.dev/discord and get in the chats with us. So that's it for this week. We'll catch you next week. Until then,

[00:30:42] **Tim:** Remember, your heart matters even if you optimize all the slow queries in your crappy app.
