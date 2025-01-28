---
title: "130: Book Club - The Phoenix Project"
description: "On today's show, we have our first book club discussion about 'The Phoenix Project: A Novel About IT, DevOps, and Helping Your Business Win' by authors Gene Kim, Kevin Behr, and George Spafford."
date: 2023-06-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/130-book-club-the-phoenix-project/id1544142288?i=1000615997951"></iframe>

On today's show, we have our first book club discussion about [The Phoenix Project: A Novel About IT, DevOps, and Helping Your Business Win][phoenix-project] by authors Gene Kim, Kevin Behr, and George Spafford. We review chapters 3-6 and talk about how Adam's recent compliance work has given him a fresh perspective on the 190-page spreadsheet of vulnerabilities portrayed in the book. It's interesting how a security team can have a deeply collaborative relationship with a company that feels, at least for some, to be purely adversarial.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[phoenix-project]: https://itrevolution.com/product/the-phoenix-project/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/130-book-club-the-phoenix-project.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** That was the other thing, is like they, they said, There's a checkbox in the form for this is an emergency change, and everybody was just always checking that because it took three weeks to get an answer if they didn't. And then so somebody's like, well, maybe we need this as a extremely urgent, or, or a, a very emerg, whatever it was.

[00:00:15] **Adam:** You know, like

## [00:00:35] Intro

[00:00:35] **Adam:** here we go. It is show number 130 and I'm back and I got rid of the Scallywags. and, and Carol couldn't be with us tonight. I think it's Tim's turn to have a, a leaking kitchen. That's all the information that I have. And I, if I'm not mistaken, Carol is just, very busy right now between her new job and, the move and all that that entails.

[00:00:57] **Adam:** So, got myself, Adam, and Ben tonight and, uh, we're just gonna make it happen. on tonight's show, we're gonna talk about, the book that we've been reading, our book club a little bit, give you a chance to catch up. And we are going to tie that into the compliance work that I have been doing at work.

[00:01:17] **Adam:** compliance is a, a big part of the book as well, which was not really intentional when I suggested that we read this, but, kinda worked out nicely. So we'll dig into that a little bit, So I guess as usual, we will start with our tramps and fails. since our friends, Tim and Carol are not with us tonight, I will go ahead and go first.

## [00:01:35] Adam's Failure

[00:01:35] **Adam:** I'm gonna start us off with a fail. so I've been mentioning how we wanted to hire some junior developers and, you know, kind of mentor them up through instead of only ever hiring senior developers and how we were interested in working with a, a local college on that.

[00:01:49] **Adam:** So we're near Philadelphia and it's. When I brought this to my ceo, he was like, oh, actually, Drexel has a great co-op program that does this pretty, pretty regularly. I think they're pretty well known for their co-op program, which is, you know, kind of like you get school credit and you also get to work experience and kinda just work together like that.

[00:02:09] **Adam:** and we looked into it and we just missed the cutoff window. So like we have to wait till the entire next semester before we can participate in that. I think it's either the next semester or, or maybe next year. So I don't know. We'll figure it out, but, it sucks that we kind of missed the window on that one.

[00:02:25] **Ben:** I've never heard that phrase, co-op program in relation to a. So like internship. So I, I don't know what the, relationship would be there.

[00:02:32] **Adam:** I, I don't know the language if maybe it's specific wording for specific, you know, ways it's implemented or whatever. I did an internship when I was in college and, We, we didn't have like a co-op program or anything.

[00:02:44] **Ben:** I mean, that's, it's awesome that you're really actually taking steps to look into this. And it wasn't just a momentary, wouldn't it be nice if.

[00:02:52] **Adam:** Yeah. Yeah. When I brought it to Steve, my, my boss and semi business partners, we have a very, ambiguous relationship around that part. But anyway, I brought it to him and I was like, you know, I, I think I would be really interested in doing this. You know, kind of, sort of moving in into more of a mentoring and managing role.

[00:03:14] **Adam:** and, and you know, bringing on some junior developers and like spending a, a specified portion of my week, like pair programming and mentoring with them and then doing other stuff the rest of the week. And he was like, hell yeah, that sounds perfect, so let's do it.

[00:03:29] **Ben:** It's so awesome.

[00:03:30] **Adam:** Which, which was great, but then it became real and I was like, okay, well now what?

[00:03:35] **Adam:** How do we do that? That's not something you can, where do you put the semicolons in that statement? Right? Like, this is all new to me.

[00:03:44] **Ben:** I will, you know, it sounds like. We could lean on Tim for some advice. He's, he seems to have run things like this, so maybe he can,

[00:03:52] **Adam:** If only he were here

[00:03:53] **Ben:** if only he were not dealing with stuff

[00:03:56] **Adam:** and, and he, he doesn't even listen to this podcast, so it's not like he's gonna hear us complaining about his absence.

[00:04:02] **Ben:** so do you think you'd have to get people, equipment? I mean, that's, so what's the barrier to entry?

[00:04:09] **Adam:** I, I have no idea. you know, I, I mean, I, I gotta imagine that kids enrolled in a computer science program at school are gonna be, you know, they're gonna have some equipment that they can use and, and our stuff. Can run anywhere, right? You just need a, a pretty basic code editor, like Visual Studio codes blind.

[00:04:26] **Adam:** If you're a glutton for punishment, you could use notepad.

[00:04:29] **Ben:** So it, it, I mean, you talk about compliance. Is there anything in the compliance mandate. It talks about who owns the machine on which the work is done, or is that simply contractual stuff?

[00:04:43] **Adam:** There's policies on policies on policies, my friend,

[00:04:46] **Ben:** So is it o, is it, is it okay for for a student to own a laptop and then do work for your

[00:04:51] **Adam:** have a bring your own device, policy,

[00:04:54] **Ben:** Ah, lovely.

[00:04:56] **Adam:** So it talks about like, you know, what's, what's allowed, what's supported, you know, ownership of, of the, the hardware. And,and I, I don't think that B Y O D policy covers like, okay, if you use our machine on your own time, what happens with that?

[00:05:12] **Adam:** But like, you know, that's in one of the policies.

[00:05:15] **Ben:** I love the idea of being able to bring your own device, especially in this industry where it's full of people who aren't just clocking in and clocking out, but. Have bleed over of interests into hobbies that relate to work or relate to work adjacent things. The idea that there's ever contention around whose machine you should be using for what, it just feels like unnecessary complexity and

[00:05:42] **Adam:** like predatory

[00:05:43] **Ben:** It's weird.

[00:05:44] **Adam:** it, I can only ever see it as predatory. Like why in, in what universe does it make sense for a company to own something I made on my free time? Because I happen to use the computer that they bought for me to do my, my business work, my nine to five job on. but I happen to use it at, you know, three in the morning on Saturday,

[00:06:03] **Ben:** Right.

[00:06:04] **Adam:** on my own thing.

[00:06:05] **Adam:** That doesn't, that doesn't compute for me. like that just seems like, oh, there's some gray area here, so the company's gonna take advantage of that. And just be like, Nope, that's ours now.

[00:06:14] **Ben:** Yeah. And it's like my computer here, it's, it's murky. I've bought this computer. And I had to sort of get permission to use it. And the guy who runs the security was okay with it because I have to install all the security software. So, so technically there's stuff on this computer that the IT department at work could, if they had to remote wipe this computer, even though, you know, 80% of the things that are on this computer are actually mine and not having anything to do with work.

[00:06:43] **Adam:** Yep.

[00:06:43] **Ben:** but like I'm okay with that. I, you know, they're not gonna do that. What's mdm?

[00:06:48] **Adam:** mobile Device Management.

[00:06:50] **Ben:** Hmm. Yeah. Yeah. So then there's antivirus stuff that I've had to install and, and things of that nature. Like find my MAC is mandated hardware and yeah, full disc encryption is mandated, all that kind of stuff. And they have some sort of a, like a thing that monitors the state of the computer to make sure all of that stuff is in place.

[00:07:09] **Ben:** And if, and if it's not, you know, I get alerts, they get alerts, et cetera.

[00:07:12] **Adam:** Yep. Yeah, no, the, that's part of compliance too, is like, you have to be able to prove that, you know, the, the, the necessary people have full disc encryption on, and that they're running antivirus scans and you know, this and that. And so, one, the, the, it's not the only reason to install MDM software, but like by installing MDM software, it allows you to query that and, and control it, at the, at the corporate level.

[00:07:38] **Adam:** And you can just get a, you can print out a report that says, look here now a hundred percent of our developers have full disc encryption on and all that. And so that you can submit that as your evidence for the particular compliance requirements.

[00:07:50] **Ben:** That's awesome. All right, so, so nothing, nothing from a compliance standpoint is ultimately at odds with the idea of having college students work on your stuff. You know, as long as the right permissions are in

[00:08:01] **Adam:** Yeah. Yeah, that's the whole compliance is all about, just making sure that you have done the due diligence to keep your systems secure and your financials, you know, legit.

[00:08:13] **Ben:** Sounds good. so, so is your plan now to wait for next semester, or is there some other avenue you want to explore?

[00:08:20] **Adam:** I, I think personally my plan is to keep my head down, trying to get my work done, my compliance stuff that I'll talk about. But, you know, as free time makes itself available cause I got, this is event season for us too. Right. So, today is Monday. I'm leaving, early Wednesday morning to head up to Princeton, New Jersey to work at an event for Princeton University.

[00:08:43] **Adam:** And I'll be there through the weekend and we will be working 9:00 AM to midnight every day. But, yeah, but it's a lot of like, hurry up and wait, right? So it's like, you know, a lot of stuff to do first thing in the morning and then there's like two hours of kind of dead time until lunch and then, you know, have lunch and then maybe a little bit more work, and then an hour of dead time and then a little bit more work and two hours of dead time and then a big rush from like 6:00 PM to midnight or whatever. So yeah, like when I have that downtime, I'll, I'll maybe try to use some of it to look into other options, other intern internship options. Maybe the co-op thing is something we can look into for the future, but maybe a little more informal. Just like somebody needs an internship as a requirement. It doesn't have to be a for credit sort of thing.

[00:09:29] **Adam:** Cause I feel like that's what I did in school. I.

[00:09:32] **Ben:** There was a, there's that Girls Who Code program, which I think is a national program. I wonder if there's some sort of in in roads you could have there that could be

[00:09:40] **Adam:** Yeah, that's a good thing to look into. I should, I should write that down.

[00:09:44] **Ben:** Cause I think they're everywhere.

[00:09:45] **Adam:** Yeah, for sure. Hey, me, when you're listening to this later, write that down. So that's it for me. I guess, Ben, how about you?

## [00:09:53] Ben's Triumph

[00:09:53] **Ben:** I'm gonna even us out here with a triumph, which is that I, I've talked recently about my lifelong desire to build a fitness application of some sort. And I have taken the very first smallest of baby steps to actually move that into a reality, which in the ultimate irony of all things, developer, is I deleted the previous fitness app that I had built, and so that I can now build a, a newer shinier one.

[00:10:21] **Ben:** but the, the previous fitness app that I had, I had, it, it was deactivated. No one's even been able to log into it in years. And, I was inspired by, in part, I finally read the, just ship book by Amy Hoy, which you had recommended probably like a year ago or something. And, it, it was interesting.

[00:10:42] **Ben:** I mean, it was, it's a, it's a very quick read. I read it in, you know, an hour and a half. I think I skimmed part of it too.

[00:10:48] **Adam:** It's a pretty short book.

[00:10:49] **Ben:** yeah, it's, it's a pretty short book, but, she definitely drives home the, just start, just do something. I didn't agree with everything that she said in the book, but the idea of starting small.

[00:11:01] **Ben:** Doing things incrementally, it really resonated with me and how I approach work. And I want to take all of those same philosophies and, and apply them to building, you know, a little, side hustle project as well. I don't, I don't intend to ever make money off of this. At least that's not my initial plan.

[00:11:17] **Ben:** But, I'm not gonna close that door if that's an opportunity, perhaps down the road.

[00:11:21] **Adam:** Yeah. You're just not actively pursuing it. It's,

[00:11:23] **Ben:** Yeah. Yeah.

[00:11:24] **Adam:** in the universe.

[00:11:25] **Ben:** I, it it's hard to, you know, what I want to build is just something where I can track my workouts and it's hard to know what people would even want to pay for, especially, cause I think most fitness apps, when you go on app stores are, are they free? I don't even know, I don't do any market research.

[00:11:39] **Ben:** I have no interest in doing market research.

[00:11:42] **Adam:** Well, that, that's a little, antithetical to, the whole philosophy that Amy teaches, but I don't know if that was really covered in that book. I think that book was more just like, get out of your own way. Start

[00:11:52] **Ben:** Yeah, so, so that's something that she talks in the book that I didn't quite understand. So I think she kept talking about the, this term sales safari, I believe. And then I subscribe to her, she and, and her partner Alex, I think is his name. They do a Stacking the Bricks podcast. which I, I cherry picked like, I dunno, eight or 10 episodes to listen to that.

[00:12:12] **Ben:** It's, it's actually pretty interesting. I'm gonna keep listening to it and they go more into depth about it. But it w it, it did seem very different from a lot of, a lot of advice where she seemed to talk about finding a market first and then building a product. Whereas I think a lot of people build a product or at least have an idea for a product and then figure out the market fit.

[00:12:34] **Ben:** I think she was saying that that's, In most cases doomed to fail because you didn't, you didn't, you don't have the right thing to begin with,

[00:12:42] **Ben:** which,

[00:12:43] **Adam:** It's like the classic, you know, programmer, ah, screw this. I'm just gonna go start my own thing and make my own money. And you know, a year later you come crawling back, please take me back.

[00:12:54] **Ben:** it's so tough because I'm so driven by the idea of scratching my own itch. And it's hard to, it's hard to wanna build a product simply because someone else needs it and not because it solves some problem that I have. And I mean, maybe that's just a narrow minded view of the world. I mean, it, it, it certainly is, right?

[00:13:16] **Ben:** I mean, people build products all the time for itches that they do not have themselves personally and, uh, can be very successful at it. But, you know, I think if you're doing it as a. As a job. That makes sense. You know, you, but if you're just gonna do something as a small side hustle, I don't know. I feel like I'd only want to do something that scratches my own niche.

[00:13:35] **Adam:** Yeah. I, it there's, I think that there is a, a middle ground where there is both, and that's where the magic happens, right? So like, you know, you can, you can just scratch your own itch and as you personally just said a minute ago, like, maybe it turns into nothing, right? Maybe nobody ever wants to pay for it.

[00:13:50] **Adam:** Maybe it's just, it's just a you thing, and that there's nothing wrong with that at all. But if you wanted to turn it into a business, then building the thing that you want may turn out to be something that nobody else on the planet

[00:14:01] **Adam:** wants, even if they know it's available. Right.

[00:14:03] **Ben:** So, so,

[00:14:05] **Adam:** well, so let me finish real quick.

[00:14:07] **Adam:** So, Amy and Alex teach a course that's called 30 by 500, not sponsored. and I've just been sort of floating out here in the, in the ecosystem, very aware of their stuff and, and all the, you know, gobbling up all the little tidbits of free content that they give away. cause it seems very valuable.

[00:14:24] **Adam:** But, I have not taken the course and I did read the book and, and, you know, I've bought a couple of their little info products, but, it, it very much seems like from the outside looking in, my interpretation of what I've heard is that you identify a group of people that you would enjoy serving, right?

[00:14:44] **Adam:** So if you are a, a amazing React developer, And you happen to find a place where a lot of people talk about React stuff, and you hang out there and you've already been, especially if you've already been hanging out there and you're part of that community, and then you see, you know, if you can, if you can detect a trend of people doing the whole like, shut up and take my money thing, like, that is a, that's a sign, especially if, you know, they're all doing it for the same thing.

[00:15:09] **Adam:** Like, we have this problem. Like that is a sign. And if you go, yeah, I, I know how to do that and I can, I can do that and you can pay me for that, then that's sort of like the, the, my totally uneducated guess of, what sales Safari is about. It's like finding those, they call 'em watering holes where those people who do the thing, the, the people that are in the audience that you wanna serve, where do they hang out and, and talk to each other and complain about their problems with the thing that they like doing, whether it's knitting or, or whatever.

[00:15:37] **Adam:** Right. And, you know, kind of be a fly on the wall there, identify their problems, and, and then.

[00:15:45] **Ben:** Well, so, so let me interject because as you're saying this, what I'm realizing is I think maybe this weird baggage that I'm bringing to the conversation. So when I, when I think building something for a need that you don't have personally, My first reaction is, okay, I'm gonna be showing up to a job I don't like.

[00:16:06] **Ben:** I'm gonna be building a product I don't believe in because someone told me to build it. And like, clearly I'm bringing my own to that perspective. And when you talk about finding a group of people that you would take joy in helping, I'm like, oh yeah, that's like, that's actually the real me, uh, when I think about dealing with customers at work, that that was, I didn't always understand what they were asking for.

[00:16:29] **Ben:** I didn't always relate to the things that they wanted, but I was so excited to get on calls and talk to these people and hear about their pain points and think about, oh yeah, I could fix that. I could, that's a, that's just a database query. Like literally the thing that is driving you crazy will take me half an hour to build.

[00:16:43] **Ben:** I can do that for you. And, and man, I feel like such a jerk now that, that my first reaction was, oh, I don't wanna build something for other people. Cause, but I, but I do think, honestly, if I, if I can be super transparent, I feel like that is a byproduct. Of how, of how distant I've become from my own customers at work, and that's, that's something I need to fix.

[00:17:05] **Adam:** Yeah. And I, I, I don't think that it's even a hundred percent that, right? So I think that there's this stereotype of, you know, software people going off and just like, oh, I've got an amazing idea. I'm gonna go build it. And you spend six months and, and you're life savings, trying to build it, and then it crashes and burns and now you're destitute and you have to become a whatever.

[00:17:28] **Adam:** I don't wanna say any particular job cause I'm, I'm just gonna sound like a jerk, right? So whatever a job you don't want. and then, and, and her. Philosophy is sort of the antithesis of that. Like, find a problem that you already know how to solve and, and actually like, it's funny how things like overlap too, cuz you've got, like, you've probably heard the, the phrase content marketing, right?

[00:17:50] **Adam:** Where you're just like, you're giving a lot of value away for free in order to sort of build your personal brand and build trust with your audience. And then after some point Intuit, you provide some sort of paid product and you can kind of like, you know, continue to build that trust and that relationship.

[00:18:08] **Adam:** Now they're, you're paying for a premium product from you and they find out that they love your teaching style and you know, you're, you're just kind of, growing that snowball bigger as it rolls down the hill or whatever, whatever metaphor you like. And it's so tough because I feel like there's a lot of traps and pitfalls along that path where you can kinda get sucked into like, not the, the.

[00:18:33] **Adam:** Methodology that they teach, right? It's not just like, give away 10 tips and then make a free, make a paid product, right? Like it's a, you're, you're, I think their approach, again, totally uneducated, haven't taken the course, but my, my understanding is you, you build a relationship with the people, right? You become part of the community and you become known in the community as somebody who's giving away your knowledge.

[00:18:56] **Adam:** And then, and then it's like, okay, well here's a big thing that I can do, and because it's a big thing, I can charge for it or whatever, so,

[00:19:05] **Ben:** Yeah, it, it, it's making more sense as we're talking about it actually. it's tough because I, I want to build this thing for myself, but I am excited at the idea that someone else might find value in it. But it's hard. Like I don't wanna get sucked down the rabbit hole of now building something for someone else before I've built anything.

[00:19:24] **Ben:** It's like, I want, I want that MVP to be the thing that makes me the happiest so that I'll keep doing it and then figure out, okay, now where's the value add that I can, I can allow, that I can add that other people will find perhaps more enjoyable that maybe I don't necessarily understand, but, but, other people might find helpful,

[00:19:45] **Ben:** I don't

[00:19:45] **Adam:** I mean, I think honestly, the first thing that comes to mind for me, if, if you wanted to do that market research that you're resistant to do is, go on the app store, look up fitness apps and read their reviews. Right? So many people are gonna be in there complaining

[00:19:55] **Ben:** Oh, that's an interesting idea.

[00:19:58] **Adam:** Yeah. Like, I love this feature, but this sucks about it, or whatever.

[00:20:02] **Ben:** Hmm, hmm. Delightful. Delightful idea.

[00:20:07] **Adam:** Yeah.

## [00:20:08] Going Live and Talking to Customers

[00:20:08] **Ben:** Let me, let me throw something totally at random now, like taking a, taking a side tangent here, but, but in the idea of becoming closer to customers. So, as I mentioned just previously in this conversation, I have felt very distant from my customers for a long time now.

[00:20:23] **Ben:** It used to be when the company was small, when we didn't really have a support team, when we hadn't even heard of the term customer success. Engineers would get on calls with people and we would have, we, you know, we would do screen shares and we would debug, why is the app not working for you? Let's figure it out.

[00:20:38] **Ben:** And that's an error that is years behind us right now. I haven't directly talked to a customer months, I don't know, six months, eight months. And that was only me listening on a call, someone else talking to a customer. So I've been feeling the need to remedy that situation and I have this crazy idea and, and I'm gonna throw it out there and you can feel free to give me raw, transparent feedback.

[00:21:04] **Adam:** You're wrong, and this is why.

[00:21:07] **Ben:** So here's my, here's my thought, in the, let me caveat this immediately by saying I work on the legacy platform at work. No one else cares. No one else cares about the legacy platform. So I feel like I have a lot of latitude to experiment and to ask for permission or no, to ask for forgiveness, not for permission.

[00:21:25] **Ben:** Okay, here's my, here's my thought. What if in the global navigation I had a little office hours link and you click the office hours and it says something like, you know, Friday from 11:00 AM Eastern to 1:00 PM Eastern. And you know, the language here is not right, but the engineer who maintains this system will be available for any questions you want to talk about.

[00:21:50] **Ben:** And it's just a, it's a link to a Zoom. And at Friday, at 11:00 AM I show up. And I click like a little feature flag, it says like, on air, and then like the, maybe the office hours turns red or something. You know, kind of like a, like on air at a radio station. And just hang out and see if any customers show up and wanna talk about the app.

[00:22:08] **Ben:** I, I assume a lot of people who show up will be angry and like, I'm prepared for that. You know, that's, that's why they're showing up. but I'm like, I'm just thirsting, I'm thirsting to talk to people who wanna talk about the product. Is that a crazy idea?

[00:22:22] **Adam:** not at all. I do think the very first thing that I thought of as you started to get into the details there was you gotta be careful how much you open the kimono.

[00:22:29] **Ben:** I know, I

[00:22:31] **Adam:** so you specifically use language like the engineer that, that maintains this, which

[00:22:36] **Ben:** The only one who cares

[00:22:38] **Adam:** Yeah. Yeah. Some, some people will definitely read that and go, there is only one person working on this product.

[00:22:43] **Adam:** Like,

[00:22:44] **Ben:** Yeah. Yeah. I, it would have to be more

[00:22:46] **Adam:** royal we and that sort of thing. and you know, just, just, just because you are the only one that ever shows up from the company at these office hours to, to talk to the customers doesn't mean that there's not more people. Right.

[00:22:59] **Ben:** I take the, I take the requirements from the customers to the engineers. I'm good with people.

[00:23:09] **Adam:** I think that, that sounds fun. I would, and that's, it's, that's more of a, a sort of a delicate tightrope that you have to walk there because like, if you just kind of show up online one day and people have to be in the app and notice it to see it, like you're, you're not gonna see much uptick at first.

[00:23:27] **Adam:** And I feel like for me, that would be demoralizing,

[00:23:30] **Ben:** Yeah, yeah, yeah. I,

[00:23:31] **Adam:** Like if you just, if you just go, I wanna play with live, I'm, I'm speaking from personal experience here. I wanna, I wanna see what live streaming is all about. So you just like, jump on a live thing, you tweet, I'm Live now, and, and you go like, I'm gonna work on a coding thing.

[00:23:43] **Adam:** And you're like, there's nobody there watching you, so you can't talk to anybody. So then when somebody does pop in, you're like in the middle of thinking about something and you're like, not in a, you're not talkative. Right. So there you're, it's just somebody like looking over your shoulder at your screen while you're working on something and, and it doesn't work that way.

[00:24:00] **Adam:** Right. Like in order for it to actually, I think be what I would consider successful if I were doing it, I would want to advertise it a little bit in advance. I dunno if you have like announcements or anything sort of built into your,

[00:24:13] **Ben:** Right. So

[00:24:15] **Ben:** here's where it gets weird, right? Because I feel like if I, I hate to even say this in a place where anyone could ever hear it. I feel like if I went and I asked the company and said, Hey, would you guys mind if I did this? I would not get permission for it. So I sort of feel like I have to get something in place. Such that like a customer sees it. Like, I'm not even saying get to the first office hours, but I'm saying like, it has to be in the app doing something before anyone knows about it. Otherwise, I, I don't think I'll be able to get it off the ground. But to your point, I think what I wanna, I think what I can do is I put the office hours link in the nav all the time, so it's gonna show up.

[00:24:56] **Ben:** Maybe it has a little gray.next to it, and that gray dot can turn red, you know, when we're on air kind of a thing. it shows up all the time. Anyone can click on it. Anytime they get taken to a, an interstitial page, an interstitial page says the, the next office hours is scheduled for, you know, maybe it's like a week and a half from whatever the day is.

[00:25:13] **Ben:** So that way people can dribble in the clicks, the attention. They can see, oh, what is this? Let me make a mental note of that. Maybe, or maybe I could, you know, I'm talking mvp. I don't even e even the idea of like, you know, send me an email when this is, when this is live. Like that's more infrastructure and effort that I think I'm ready to put into it yet, but,

[00:25:33] **Ben:** I, I think having the link there all the time, but then only having it activated on air, flashy, whatever, you know, beeping at the, at the time of, of it, of it live.

[00:25:42] **Ben:** I feel like, I feel like that's something we could work with.

[00:25:45] **Adam:** Yeah. I mean, who's gonna review this poll requester. Are they not gonna rat you out?

[00:25:51] **Ben:** I, I got people, I got people, so, yeah. It's a, well, and, and, and you know, you talked about, I think this is in the, the JFS book as they, as they start to call it, I think this is in the book. I don't think this is one of the podcasts, but they were, she talks about it in the book that they had one product that they went to release and it fell completely flat.

[00:26:15] **Ben:** And, they had done a bunch of products before and they had all been very successful and they didn't quite understand why this one suddenly fell flat when everything, like they did it by the numbers and for whatever reason, this one didn't feel like it was working. And they, what she realized was that there was, to your point, no lead up at all.

[00:26:32] **Ben:** They were like, Hey, product, here's the page, here's the, here's the buy now button, have at it. And when she talked about the products that had been successful, it was the, we announced months ahead of time that this was gonna happen. And then we released some, some like teaser. And then weeks before we emailed our group of people saying, oh, this is so exciting.

[00:26:52] **Ben:** And then more teaser and then like tweets and, and email campaigns, everything up to, and including the product deployment itself. And so they took that failed product release and they redid it having changed nothing about the product at all, but just, just implemented this drip campaign and they went to bananas.

[00:27:10] **Ben:** And so, yeah, it's all about framing. The, the, the pipeline into the product itself.

[00:27:17] **Adam:** for sure.

[00:27:18] **Ben:** It's fun talking about product stuff.

[00:27:20] **Adam:** Absolutely.

[00:27:22] **Ben:** I don't get to talk about it enough at work. I, I'm all, all just like on bug fixes and infrastructure problems right

[00:27:28] **Adam:** I, I do think that your office hours thing could work. I did. Taffy office hours way back in the day. And I only ever did like, maybe two of them. It was just like, you know,

[00:27:37] **Ben:** That's cool though.

[00:27:38] **Adam:** I, I'm gonna jump, it was a Google meet. This was like maybe fairly soon after Google Meet was, released. Like, yeah, I'm, I'm gonna jump on a thing and we'll just, I want to talk to Taffy users, see what they're up to, see what they're, you know, if they're interested in new features or, or you know, should we rewrite it to all BCF script or, or whatever.

[00:27:56] **Adam:** and yeah, and that

[00:27:58] **Ben:** and and cf, CF script, what does that stand for?

[00:28:01] **Adam:** I don't know, coffee, coffee script. and the I think that it fizzled out because there was no direction, right? It was just like, the doors open, you can come in to talk to me about whatever you want. And people that were, you know, maybe frequent users of the, of the framework or people that, were just excited about community.

[00:28:22] **Ben:** Yeah,

[00:28:23] **Ben:** Showed up and we talked for a little bit, and then it did not, oh, I, you know, I think I also did it around like Taffy's birthday, the anniversary of its release. but that does make me think like I should show up with some, some pre-canned questions if, if people don't know what to talk about, I need, I need prompts. What do you hate most about the product? What, you know,

[00:28:42] **Adam:** If you were king for a day

[00:28:44] **Ben:** yeah. Yeah, exactly.

[00:28:45] **Adam:** what would you change? Yeah, absolutely.

[00:28:47] **Ben:** always like the idea of pushing a button. Like if you had a button that you could push that did something magical, what would that do?

[00:28:53] **Adam:** Yeah. That's a good question.

[00:28:55] **Ben:** All right. Yeah. This is great. This is great. I'm excited

[00:28:58] **Adam:** what repetitive tasks do you do that could maybe be automated? Save you, you know, how much time a week would that save you? Right.

[00:29:06] **Ben:** Yeah. Got the, the machinery firing. I like it. I like it.

[00:29:10] **Adam:** Good. Good. Cool. Well then maybe we switch gears and talk about.

## [00:29:14] Book Club

[00:29:14] **Adam:** Book club and, and

[00:29:15] **Adam:** compliance. Those two, my two favorite things. yeah. So, last week you guys did the show without me, and you talked about the book club a little bit in the after show. and, I slapped your hand for it afterwards

[00:29:29] **Ben:** Yeah. There was some misunderstanding

[00:29:30] **Adam:** Yeah, it's all right.

[00:29:31] **Adam:** The book club is for everybody. so if you're listening to this, you are invited to join us in our book club. So basically we're reading the Phoenix Project. It's a book about DevOps stuff. It's for a manufacturing company, and it's basically like, let's learn, you know, best practices about, running an IT organization, right?

[00:29:49] **Adam:** Like, how do we handle technical debt? How do we, how do we fix the fact that the world is crumbling around us, right? Like payroll's broken and the sand goes down and all these other problems are, are cropping up, like sometimes multiple problems in a single day. And also, by the way, at the same time, we've got this project that we've been trying to like rewrite our whole.

[00:30:09] **Adam:** our whole product from scratch and it's two years late and a million dollars over budget, and we've already promised the market analyst that it's gonna be coming out this quarter. You know, like, and so how do you balance all of that and, and still manage to get, get to success? That's what this book is about.

[00:30:24] **Adam:** And instead of just saying like, this is what continuous integration is, and this is what DevOps is, and this, you know, instead of just like giving you a list of things and like job responsibilities, it's told as a narrative story. So you meet characters and they have certain jobs and they have certain challenges they have to face.

[00:30:40] **Adam:** And there's people that are, potentially like sabotaging things and, and the, we're only a couple of chapters in, but the, the CEO seems maybe a little bit, like his head's not in the game or something. Right. so yeah, if, if you're interested in, in following along with that, you need to do two things.

[00:30:56] **Adam:** You need to give yourself a copy of the book. It's called The Phoenix Project. and I forget the subtitle, but it's something about DevOps. And then you need to join our Discord, which you can go to workingcode.dev/discord. Join our Discord. it's free and open to the public, and it's like Slack, but it's just more for communities rather than companies.

[00:31:15] **Adam:** and then, there's a channel in our Discord where we talk about the, the book. and we read, so far we've been doing three chapters a week. We just, so today was our second meeting, so we are six chapters in today. When I say that is Monday, May 22nd, we meet on Mondays at 5:00 PM US Eastern, and talk about the book for about an hour, and then we move on with our day.

[00:31:35] **Adam:** and so, chapters a week. So by the time that you hear this, So patrons will hear this probably just barely in time for the book club meeting. That'll happen on May the 29th.

[00:31:46] **Adam:** and then it'll go public in time for people who are early listeners to new episodes to, to arrive for,the meeting on May, June 5th. wait a minute. No, I'm sorry. I'm, I'm, we moved our, our recording day and I'm, I'm, I'm off. So, patrons will, we would hear this in time for the June 5th thing, I believe.

[00:32:07] **Adam:** Maybe. I don't know. I'm all, I'm all sort of twisted, but anyway, drop into our Discord and we'll get you straight there. Right. We'll tell you what chapters you need to read up to. The chapters are pretty short, so it's not a big ask. Yeah. That's available as an audiobook if you like, that you can listen while you're driving or showering like me.

[00:32:23] **Adam:** and then, yeah, and it's fun. We talk about, how it relates to our, our jobs and our experiences. We got a guy that's been coming in meetings that day. He's a college student. He's got a little bit of experience doing projects with people, and it's been a lot of fun. People talking, talking about the book and the challenges and how we would solve those problems.

[00:32:42] **Adam:** And so, I guess the, the, the way we kind of wanted to tie it in this week was that,

[00:32:46] **Adam:** So a big thing that happened, in the, the chapters for this week, four, five, and six, was, uh, they got their internal, compliance audit results.

[00:32:56] **Adam:** and so there was this big meeting and they hand this dude like a stack, like a, probably like a, a 15 pound stack of paper. It's like, okay, here's, here's all the things that are wrong and we need you to have them fixed a, a week from Monday. Can you do that?

[00:33:10] **Ben:** Yeah, they did. They, they explain it. It's like a, a printed out Excel sheet

[00:33:14] **Adam:** Yeah. Which,

[00:33:15] **Ben:** pages long or something.

[00:33:16] **Adam:** yeah. And, and you know, at one point when they, when they said that, he said it was like 20 rows per page at eight point type. And I'm like, obviously you've never seen a printed out spreadsheet. That was my first reaction. I was like, at eight point type, you could fit 150 rows on whether we're talking landscape or portrait.

[00:33:33] **Adam:** But then I was like, you know what though? I've seen the way that business people use spreadsheets and we're not talking a single line of text. Right. Like that, that column, column D is gonna be like, every row is gonna have 40 lines of text in it anyway, so yeah, they, and, and they go through a little bit of, in, in this meeting where he gets all these audit findings.

[00:33:54] **Adam:** You know, like he's got some of his other managers in there with him and they talk about how like, some of this stuff is, not worth considering. Like yes, technically it's some sort of, you know, minor security issue. there's a insecure cookie setting on one particular server. versus like you've got, the, another one that they brought up was like the, people have the ability to push changes to production without any approval, and no one would know that anything changed, right?

[00:34:20] **Adam:** Like, these are two very different. Levels of security issues. And man, when I read that, my, my like bells were going off in my head, like, this is so relatable. Who among us has not run N P M audit and laughed at the like 70 prototype pollution critical security vulnerability things. I'm like, really? So because somebody put their custom method on the array class, that's a critical security vulnerability.

[00:34:48] **Adam:** Or like, I mean, I get it. If, if you get the perfect storm of, of bad things happening, then bad stuff can ha or like, right, somebody could take over your server or whatever. But it does require that perfect storm versus, okay, you've got a SQL injection vulnerability or you've got, you know, whatever else going on. You look

## [00:35:10] The Security Team

[00:35:10] **Ben:** One thing, one thing that I find interesting in the book, and I, and I guess every company is different, but I, in the book, the security team always feels very much at odds with everybody else. Like they're coming in and ruining the party. And, and I will say maybe this is a testament to the culture that we have or maybe the culture that I have diluted myself into believing that we have, which is that the security team, we view them as, as like really having our back.

[00:35:37] **Ben:** And when they come in with a, with, with an pen test findings or things that are, you know, low, medium, high criticality, you know, we jump on them and I, and I, and I, you know, this is probably just me. This is probably not everybody. Like, I'm excited to jump on those things cuz it's, it, it's kind of like what I was talking about where I thirst for communication with the customers.

[00:35:58] **Ben:** When the security team comes to you with issues, it's like, now the security team is your customer. You're like, what? I can solve your problem. This is exciting. I, I maybe this is crazy. I love dropping what I'm doing and I almost feel like the security team gives me the permission to do that. That, oh, I was working on a product thing.

[00:36:15] **Ben:** Oh, sorry. Security has vulnerabilities that they need to take care of. Yeah. I'm totally okay to drop everything that I'm doing and go deal with them and, I don't know. I enjoy it. I enjoy it except for token rotation. That's awful. All the time.

[00:36:29] **Adam:** Yeah. The, so you're, you're absolutely right that in the book, it's, it's feeling very much that the goals of the security team are like orthogonal to the goals of the development and operations teams, and they're just like constantly butting heads. And I've been on, I, I feel like I've been in places where that is representative of my experience, but I've also seen it done well.

[00:36:54] **Adam:** And like you were talking about, like, I don't know that I, okay, here's, here's the other thing. it, I would relate this very much to working out. It is so much easier to stay healthy and stay fit than it is to let yourself go and, you know, find yourself, oh, I'm now, I'm 40 pounds overweight. I have, I barely walk anymore.

[00:37:13] **Adam:** I, you know, my doctors tell me I'm at risk for heart disease and now I have to get up and, and start working out. Right? Like, that is such a heavier ask.

[00:37:22] **Ben:** Well that that, that's a good point cuz at

[00:37:25] **Ben:** the, the picture that they paint in the book is like, imagine a scenario where everyone has made every wrong decision they can possibly make about everything that, that, that's like what it, that's, that feels like the, the hellscape that he has been dropped into as the new, VP of technology or whatever his role is.

[00:37:44] **Adam:** Yeah. Oh yeah. Like chapter one is like, he gets unwillingly promoted to VP of, of IT or something like that. And then, and it's just like, I, I think it's pro, it's probably at least the first four chapters, it's just like, Every day is at least one, if not two new like critical fires the world.

[00:38:02] **Adam:** It's an existential crisis. And, and it's like not only do you have to finish, you have to follow up and finish on, the, the problems from yesterday. But now you've got these new fires and also you've got the, the long-term goals. And man, so the first time I read this, I feel like I took a pretty naive, cuz we've talked about this book on the podcast before, kind of just like lightly like, oh, I read it and I really enjoyed this sort of thing.

[00:38:25] **Adam:** But, first time I read this, I was very naive view of the security guy, because of like the, the way he flies off the handle talking about it's my job to keep them outta jumpsuits and,

[00:38:37] **Ben:** Mm-hmm.

[00:38:38] **Adam:** that the orange jumpsuits from if you go to jail, and all that. And you know, now having some security compliance experience under my belt.

[00:38:47] **Adam:** I get where he is coming from and, and I think that, you know, I think it's a character choice. I think that. What we're supposed to take away from his approach to dealing with this stuff is not just that he has an appreciation for how important it is that he's been worn down by not being taken seriously by the rest of the company.

## [00:39:07] People Over Process

[00:39:07] **Ben:** Yeah, I can definitely believe that. It, it, the, the one phrase that keeps coming to my mind when I'm reading this or when I'm listening to it, is from the Agile Manifesto, which is people over process.

[00:39:20] **Adam:** Mm-hmm.

[00:39:21] **Ben:** that's, you know, one of the things in the, in the

[00:39:22] **Ben:** manifesto, I believe, and it, it feels, at least at the onset of this book, that it is very much a pendulum swinging the other way, which

[00:39:32] **Adam:** Mm.

[00:39:33] **Ben:** Let's get processes in place so that we can fix all the people problems.

[00:39:38] **Ben:** And on one hand, that feels like moving in the wrong direction, but on the other hand, it's almost like, like wartime triage, like everyone is bleeding to death. You just need to stop the bleeding and then maybe get back to a better place. So I almost feel like the, what feels to me like extreme process that they all want to put into place is to just stop everything from dying.

[00:40:06] **Ben:** And then not necessarily that this is the perfect solution, but it is the one that maybe keeps us alive.

[00:40:12] **Adam:** Yeah. Yeah. When we got together for the book club earlier, something we spent a good amount of time talking about was the, how they sort of tried to reboot their, their change advisory board, is that what the acronym stands for? The

[00:40:24] **Ben:** Yeah, the cab. Yeah.

[00:40:26] **Adam:** It's changed something board. and, you know, they have this like piece of software.

[00:40:31] **Adam:** They, they send a bunch of people to IT, training it t i l, which I, it's like IT infrastructure something.

[00:40:39] **Ben:** Something. Yeah.

[00:40:40] **Adam:** and, and you know, they, so they spent a bunch of money to send a bunch of people to training, give up a whole bunch of time, spend a bunch of time and money on custom software to manage their cab.

[00:40:49] **Adam:** And, and everybody hates using it because it's too, it's too much work to, to, you know, even for a tiny little change. And it's not flexible enough. And then they come in with index cards and a calendar drawn on a whiteboard. And that's, we're, that's kind of where we leave off right at the end of chapter six is seems like they're starting to get their, get to a process that might work for them.

[00:41:11] **Adam:** and the thing that I loved about that, you know, now on my, I believe this is my second read through it might be my third, is that. The thing, the thing that is amazing about the index card approach is that it is infinitely flexible. The only constraint is it has to fit on an index card. Right? So if the, if the prescribed way that you fill out the index card, you know, like it's supposed to be a one line sentence about what it is you're changing plus like when you wanna do it and what'll be affected or whatever.

[00:41:38] **Adam:** Like if the, if the prescribed format doesn't a hundred percent fit the type of change that you wanna make, then you could just tweak it right into a way that makes sense. All your, it's a tool for communicating and, and that's what the whole like software thing was supposed to be about too. The tool that they wouldn't use because it was, it got in their way.

[00:41:57] **Ben:** Well, and that it's interesting because in the scene when they're all in the room talking about entering data, the one guy's like, yeah, I can't enter it because the only option I have is this dropdown box that has a thousand things in it, and it doesn't have all the things that I need. So I literally can't move forward.

[00:42:14] **Ben:** And she says, well, of course it has to be a dropdown box. How else could we have referential integrity? And you know, they, yeah. Data, and yes, yes, yes. Data integrity. But then you look at something like the index card where, you know, there is no concepts of, of data integrity. Like, to your point, everything that is there is on, is on the index card.

[00:42:33] **Ben:** And it's almost like the index cards allow you to reset your perspective and realize that the tooling is supposed to work for you. Whereas they had tooling that they had to be constrained by instead of having it work for them kind of a thing. It's,

[00:42:48] **Adam:** The, the, yeah. Their old process was about generating reports, right? So that's why they needed data integrity, so they could say, okay, these were all the changes that affected this server, or these are all the servers that are being affected in the next week or whatever. Right? Like it was all driven by that output that they wanted and it got in the way of getting stuff done.

[00:43:06] **Adam:** That was the other thing, is like they, they said, you know, the. There's a checkbox in the form for this is an emergency change, and everybody was just always checking that because it took three weeks to get an answer if they didn't. And then so somebody's like, well, maybe we need this as a extremely urgent, or, or a, a very emerg, whatever it was.

[00:43:23] **Adam:** You know, like double emergency, double secret, emergency.

[00:43:27] **Ben:** Oh yeah. Oh. I used to work with a

[00:43:29] **Adam:** very relatable.

[00:43:31] **Ben:** we used to have a Microsoft Outlook, and every, every, every single email she would send to the company had a little red flag for urgent on it. Every single one,

[00:43:41] **Adam:** Top

[00:43:42] **Ben:** yeah, it's bananas.

[00:43:44] **Adam:** Yeah. Oh, that was another thing I, I don't remember exactly where, this came up in the book, but it was like, you know, I guess when they were, sorry, I don't remember where, where exactly this came up in the book, but they were talking about, I guess getting. A, getting a good overview of like, what is the status?

[00:44:01] **Adam:** Like we, you know, we have all these people and they're all doing projects, but we don't have a list of the projects. So like, talk to everybody and find out what they're doing. and oh crap. I lost my train of thought.

[00:44:10] **Ben:** When they're like, we've interviewed 200 people and we've discovered 197 projects. That kind of, that that, yeah.

[00:44:18] **Adam:** I don't know. There was something I was building toward, but it that my alarm going off really threw me.

[00:44:23] **Adam:** okay. It's not your fault.

[00:44:24] **Ben:** one thing that, that keeps coming back to my mind, and, and we've talked about this on the show I think several times now, which is this idea that people live in this world or they've created a world for themselves where you change something in one area and suddenly something seemingly unrelated blows up.

[00:44:43] **Ben:** And it feels like they're really suffering from that in a huge way. And, you know, it's a fictional company, obviously, in those fictional situations and it's, this is the worst case scenario. But I keep coming back to this idea that if, if every team has to know about every other team's changes all the time, that feels like something has gone terribly wrong in the dependence between the teams.

[00:45:07] **Ben:** And I dunno if that's an architectural problem or a complexity problem or something, but like that shouldn't be happening,

[00:45:13] **Adam:** Well, I mean, I think it, it should, but it shouldn't. Right? So the, the developers on your team don't need to know what's going on with the developers on a team, you know, up three layers in the org chart across by seven managers and then down three layers, right? You don't need to, you don't need to have that kind of detail into each other's daily, backlogs or whatever.

[00:45:33] **Adam:** But I think the point of the cab, is so that the, the, the managers of that org chart have a good understanding of what's going on in their department. And then when I go, oh, I wanna tokenize the social security number field in the, the HR tables, for compliance reasons, then the guy that manages payroll will go, well, hang on.

[00:45:58] **Adam:** We need, we need to make sure that that's not gonna mess up payroll runs. Right? Which is sort of the, the guise for what ended up happening in the first couple of chapters there. and. Yeah. It's about like funneling that information up in, in a very digestible, memorable way. Like Right. Ben is, Ben is adding office hours to the global nav, and then, you know, somebody else is adding things to Global Nav and we know we've got a limit of, of seven items in the global nav, and now we're talking about having an eighth one there because two people want to add one at the same time.

[00:46:31] **Adam:** Right. and yeah, so, that's, that's my read on, it's like, it's not about up over and down, it's about just up and the, the people up in the tree, their job is to see the, the collisions coming and, and prevent them.

[00:46:48] **Ben:** Yeah, and, and, and everything that people are doing in this book, they're doing it under duress. Everything is

[00:46:54] **Adam:** Yeah.

[00:46:55] **Ben:** everything. Is high priority as we discussed. And

[00:46:59] **Adam:** you ever known a Brent.

[00:47:01] **Ben:** I've ever known a Brent,

[00:47:03] **Adam:** To be clear for the listeners that Brent is a specific character in the book

[00:47:06] **Adam:** and he's the, he's the hero,

[00:47:08] **Ben:** yeah, he's the, what's the, what's the, what's the stone in an archway that like, holds it all together at the top?

[00:47:13] **Ben:** The keystone? Yeah. He's like the keystone of the company. Have I, I feel like, I think we have people on our platform, on our platform team where

[00:47:21] **Adam:** Mm-hmm.

[00:47:22] **Ben:** if they left it would be a problem.

[00:47:24] **Adam:** Yeah. Right.

[00:47:26] **Ben:** They, they know too much about how it all works under the hood.

[00:47:29] **Adam:** yeah, and, and it's funny because like in some organizations that's definitely true, but I think a lot of organizations feel that way when it's not necessarily true. Like somebody is filling that role as if they were the keystone, but that if they were to leave, then other people would be able to figure it out and.

[00:47:52] **Adam:** Honestly, you know, we've, we've talked about like the hero complex sort of thing on the podcast before, like yeah, it kind of makes you have some level of job security, but it's also, it limits you from moving up at all. And, and there, you know, there's all kinds of bad things about it. Single point of failure

[00:48:08] **Ben:** I know when I've gotten on vacation and the company continues to exist, like part of me is always a little sad.

[00:48:16] **Adam:** mm-hmm.

[00:48:17] **Ben:** Like, oh, they didn't actually need me to be at work this week. And that's, you know, great for them, but, you know, reality check for me,

[00:48:25] **Adam:** Yeah. But then you come back and you see that there's 70,000 emails waiting for you

[00:48:29] **Ben:** they screwed everything up.

[00:48:32] **Adam:** you committed what You didn't use feature flags. And what are all these tests?

[00:48:38] **Ben:** Oh, feature flag's so good.

[00:48:41] **Adam:** Sorry, I broke Ben. I sent 'em down a, down a hole here.

[00:48:46] **Ben:** What else can we tell? Anything else about the book?

[00:48:49] **Adam:** Yeah, I'm trying to think of other compliance stuff. So yeah, I mean my, my work with compliance has definitely given me an appreciation for what, I think his name is John, or is John the lead of the development group or is he the chief

[00:49:01] **Ben:** Wes is the, Wes is the,

[00:49:04] **Adam:** No, Wes is the, like one of the two. Wes and Patty are over like operations. Patty is the cab and Wes is like, I think my read on it is he's in charge of all the operations dudes

[00:49:15] **Ben:** yeah. Okay.

[00:49:16] **Adam:** and probably duets. yeah, I think, I wanna say John is in charge of the, the development team, but maybe not. Maybe John is whoever the CISO is the information security officer.

[00:49:29] **Adam:** I, I have empathy for him now, like it is hard work and, and it is a lot of times thankless work. I feel like I've been lucky that, that my company, they can see. How much the stuff that I've been working on sucks and they appreciate that I'm doing it so they don't have to. and that's from above end and my peers as well.

[00:49:51] **Adam:** and so like that's nice. I'm glad that, that they appreciate that I'm doing this and, and cuz like my code output has gone to basically zero for like, I don't know, maybe a month if not more. Now I, I've definitely done some stuff, but it's all been in service of compliance,

[00:50:05] **Ben:** Yeah. That's

[00:50:06] **Adam:** you know, we're doing key rotation stuff.

## [00:50:07] VS Code

[00:50:07] **Adam:** So I've been working on the key rotation software and all that, but like, pushing the product forward zero for well over a month. And, and that hurts a little bit, right? Like, so I got, I got my invite to the new, integrated co-pilot like chat feature in VS code,

[00:50:25] **Adam:** like the, the beta one. and for two reasons I haven't been bothered to install it yet.

[00:50:29] **Adam:** One is, I don't have time. I'm, I'm busy on compliance stuff. Like I'm not writing code really. and, and. The other is that it's the, you, you have to be using the, I think it's called insiders build of VS code. You have to like the beta channel,

[00:50:43] **Ben:** a bleeding edge

[00:50:44] **Ben:** build kind of a thing.

[00:50:45] **Adam:** Which, which is fine. And I, from what I hear, that there are like ways to sync it up with your stable release ones so that your extensions stay in sync, your settings stay in sync or

[00:50:56] **Ben:** Oh, cuz it's a different physical application.

[00:50:59] **Adam:** I think so.

[00:51:00] **Adam:** Yeah. And, but like, man, I, the idea I have so little time to write code right now as it is like the idea of the possibility of trying to sit down and write code when I've got a half hour and I wanna bang something out and my editor is like broken

[00:51:15] **Adam:** in some

[00:51:16] **Ben:** yep, yep, yep. Yep.

[00:51:17] **Adam:** That just sounds so demoralizing. So like, I would, I would absolutely love to get to play with this new co-pilot stuff, but I'm just, it's not the right time, you know?

[00:51:28] **Ben:** Yo, if I can quick tangent for a second on

[00:51:31] **Adam:** Absolutely not. We don't allow that on this podcast.

[00:51:34] **Ben:** This is, this is a tangent free zone. so I have been a sublime text user for years and years and years now. Absolutely love sublime text. And for the longest time everyone has said, oh, you should switch to Visual Studio Code. All of the key commands work.

[00:51:48] **Ben:** It's a very seamless transition, but it's a better editor. you know, their, their words not mine. Uh,so at work, we've started using this thing from Microsoft called Dev Containers, and essentially, I had never heard of this before, but it, but essentially we have all these microservices and we have enough to the point where it is challenging, if not impossible for an individual developer to actually run all of their microservices on their computer.

[00:52:14] **Ben:** So, This guy Chesley, brilliant guy. He essentially has these e c two instances that get provisioned to be the development con, to be the development environments. And then you spin up a dev container, which is, I guess the name of the product. I don't know what dev container is, the name of the library, maybe the framework.

[00:52:34] **Ben:** You spin up a dev container first particular microservice and it like reroutes traffic in the EC two instance to, to your container as opposed to the kind of the base image of the, of the service. Anyway, it it, it works really seamlessly in Visual Studio Code, so I've had to switch out a visual studio code to work on it and like none of my key commands from sublime text work, I feel like, I feel like I've forgotten how to type to the point where I actually will go back to sublime text.

[00:53:05] **Ben:** To do work, then push the work up to GitHub, then go into the Visual Studio Code and pull the work down from GitHub so that I don't actually have to do the typing in Visual Studio code. I, I don't, it, it just feels, it feels so different. It, it does. It's not like, it's not like a updated skin on the same product.

[00:53:24] **Ben:** It's a very, very different product.

[00:53:26] **Adam:** I wanna, I wanna do like a, a code editor escape room. Like, like, you know, everybody jokes about, you know, how do you quit vim? Or like, you know, how do you, how do you generate a, a truly random string? You sit a developer down in front of Vim and tell 'em to try and exit, right? Like, but like, there's gotta be, there's gotta be enough there that you can do.

[00:53:48] **Adam:** Like, you know, everybody hates so much about different ides. There's gotta be like a way to, that would be awesome. anyway, we've been going for, for quite a while now. why don't we call it there? And,

## [00:54:01] Patreon

[00:54:01] **Adam:** so in that case, this episode of Working Code was brought to you by prototype pollution, possibly the best kind of pollution,

[00:54:07] **Ben:** The most dangerous kind, according

[00:54:10] **Ben:** to your GitHub, depend about alerts.

[00:54:11] **Adam:** Yeah. Oh my God. Depend upon alerts. Yeah. Don't even get me started. If you're enjoying the show and you wanna make sure that we keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording costs and our editing costs, and we couldn't do this every week without them.

[00:54:28] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. Guys Rock. if you would like to help us out, you can go to patreon.com/WorkingCodePod and we will show our gratitude by allowing you to listen to more of our blathering, patrons. Get, a nice little, like special role in our Discord that people can see that you are patron.

[00:54:48] **Adam:** And you get early access to new episodes, and those episodes will have, additional time after the outro of our blathering on about sometimes technical, sometimes non-technical stuff. and so yeah, if you wanna help help us out and get some, hopefully, hopefully enjoyable bonus content in return, go to patriot.com/working code pod

## [00:55:09] Thanks For Listening!

[00:55:09] **Adam:** your homework this week.

[00:55:10] **Adam:** Come join us for book club, get yourself a copy of the book, come join our disc code workingcode.dev/discord, and look for the book club channel. And we would love to have you there and, and come join us Mondays at 5:00 PM US Eastern. that's gonna do it for us this week. We'll catch you next week.

[00:55:23] **Adam:** And until then, I doubt Ben has something planned here.

[00:55:26] **Ben:** I didn't everything planned, but I will say, your heart matters.
