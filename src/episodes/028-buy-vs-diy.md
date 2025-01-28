---
title: "028: Buy vs. DIY"
description: 'Engineers love to build things. Materializing an abstract concept into the form of a working piece of software is one of the most thrilling experiences available on planet earth. As such, we engineers often favor building new software over buying existing solutions. However, doing so takes time and energy; and, incurs a potentially-large opportunity cost for the business. It can be difficult to know if such a trade-off is worthwhile for the business in the long-run. This week, the crew examines the "build vs. buy" dilemma; and, reflects on their own general tendencies.'
date: 2021-06-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/028-buy-vs-diy/id1544142288?i=1000526601692"></iframe>

Engineers love to build things. Materializing an abstract concept into the form of a working piece of software is one of the _most thrilling experiences available on planet earth_. As such, we engineers often favor building new software over buying existing solutions. However, doing so takes time and energy; and, incurs a potentially-large opportunity cost for the business. It can be difficult to know if such a trade-off is worthwhile for the business in the long-run. This week, the crew examines the "build vs. buy" dilemma; and, reflects on their own general tendencies.

## Notes &amp; Links

- [Kent Beck: Test Driven Development By Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530) - a book that teaches programmers by example, so they can painlessly and dramatically increase the quality of their work.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/028-buy-vs-diy.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** They were, they were like taking the date, converting it to the user's time zone, and then converting it back to UTC to get the underlying milliseconds. And I was like, you, you just don't understand how dates work.

[00:00:11] **Adam:** I mean, to be fair, dates in every language are terrible. And date math is awful. See this area of my forehead that doesn't have hair on it anymore.

[00:00:23] **Adam:** I call that date and that one, I don't even know where that one's from.

[00:00:45] **Adam:** Okay, here we go. It is show number 28 for June the 23rd. And our topic today is going to be buy versus DIY. When you should build versus when you should buy. Uh, but as usual, we're going to start with our triumphs and fails and it looks like it is Ben's turn to go first. So Ben, what's going on, man?

[00:01:02] **Ben:** I'm going to kick it off with the triumph.

[00:01:04] **Ben:** Uh, so 2021 was supposed to be the year where I started to delve into design systems and I did not really do that for the first quarter of the year. I did play around a lot with a ColdFusion custom tag DSL for email generation, which was kind of like a design system in its own right, but very small and focused.

[00:01:29] **Ben:** But I have recently started to try and build a small design system for my work in AngularJS on a legacy platform at work. And, um, I had been building up simple components like inputs, text areas, buttons. In a standalone little proof of concept and I have in the last, I'd say two weeks, maybe less, started to pull those into the application and actually use them to build some larger interfaces.

[00:01:57] **Ben:** And, uh, you know, you immediately start to see all the reasons why there's huge professional design systems, because there's a lot of weird details about. How things interplay and how do you encapsulate stuff, but still expose properties that need to be set. And, but I, I'm, I'm excited that I'm finally starting to kind of wrap my head around how a design system might work, at least at a very small level.

[00:02:19] **Ben:** And, uh, I don't know, I'm excited. You know, eventually I'll move to something. More professional in the future, probably not in this project, but in future projects. But, uh, I think, uh, you know, I'm starting to get that footing, that, uh, that base understanding of how they work and what problems they solve. So

[00:02:35] **Adam:** I'm excited.

[00:02:36] **Adam:** That's cool. That's

[00:02:37] **Ben:** really cool. Yeah. How about

[00:02:39] **Adam:** you, Adam? What do you got going on? Um, so I've been trying to, I don't know, for lack of a better word, push myself down the pit of success with TDD lately. Um, I had kind of built up a lot of momentum last week with testing and trying to do TDD. And, you know, we talked.

[00:02:54] **Adam:** previously about, uh, you know, the trials and tribulations I was suffering there. Um, so this week I bought and have here with me the test driven development. Uh, by example book by Kent Beck, um, which is sort of like the TDD Bible, if I understand correctly. Um, and it's actually not a huge book. It's a, it's actually a little bit smaller than Clean Code was.

[00:03:16] **Adam:** Um, so I'm gonna try to read that. You guys know I kind of hate reading tech books, but, uh, I'm gonna give it a go, see if I can. Make myself do better at it. Uh, and I'm just excited about the prospects of doing better and becoming a better programmer.

[00:03:33] **Tim:** awesome. Very cool. When you feel comfortable, I just want to like pair program with you one day and just watch over your shoulder to see how you're doing it because I can't

[00:03:41] **Adam:** be how not to do it.

[00:03:44] **Adam:** Well,

[00:03:45] **Tim:** I mean, you're struggling. I, if I went to like someone who's like really good at it, but I'm afraid I would ask like such a stupid question that. Yeah, you know what I mean?

[00:03:52] **Adam:** We could fail together. I mean, uh, long term, I intend to continue publishing stuff on my blog about this journey of TDD that I'm on.

[00:04:00] **Adam:** And I, you know, last week I, or last couple of weeks, I've had some good momentum of my writing. And this week, I mean, it's, we're recording this on Thursday evening. I haven't written anything on my blog all week. I was starting to feel kind of bad about that. And then I realized, like, while I haven't written anything testing related or otherwise this week, I have been still kind of consuming things, blog posts and videos.

[00:04:19] **Adam:** And I was thinking maybe I would like. Throw together a post of like, you know, sort of links to and, and discussion around some of this testing media I've been consuming.

[00:04:30] **Carol:** Yeah, that would be really helpful because I'm on YouTube, like looking up things for jest. I'm like, I just want to like, listen to something while I'm doing other things.

[00:04:38] **Carol:** So I just pick up on keywords. I'm like, just play something. I don't want to sit and read it right now, but I just want to in the background. So when I'm thinking, I'm like, oh, I heard that. Let me go think

[00:04:46] **Adam:** about it.

[00:04:48] **Ben:** My, uh, my, uh, latest background YouTube watching is this guy, Max King. He's a massage therapist and I just like to listen to him massage people in the background.

[00:05:01] **Adam:** It sounds really weird. It does sound really weird. Very

[00:05:04] **Ben:** creepy. But he, it's, he talks about what he's doing while he's doing it. So he's talking about the different muscles and now he's doing active release technique and he's doing, you know, like opening up the quadratus lumborum and he's working on the spina recti and, and it's, it's, he's got this very, uh, kind of ASMR type voice.

[00:05:22] **Ben:** And, uh, I find it very soothing to listen to.

[00:05:25] **Adam:** Okay. One.

[00:05:29] **Carol:** Not

[00:05:30] **Adam:** judging you. No judgment here. Yeah. I find it amusing. I'm not judging, but I'm, I'm amused.

[00:05:37] **Ben:** Well, you haven't heard it.

[00:05:40] **Adam:** How about you, Tim? What's going on in your life? Well,

[00:05:43] **Tim:** you know, last week, that big, massive fail that I was talking about, all those rogue microservices that were running around, acting weirdly, I finally killed them all.

[00:05:56] **Tim:** You reintegrated

[00:05:57] **Adam:** them into the monolith? No,

[00:05:59] **Tim:** I didn't. I didn't reintegrate. They don't really belong in a monolith. I don't really have a monolith to put them in. They're kind of, it's a standalone thing. I just rewrote it as not a bunch of whole bunch of services that really didn't need to be a whole bunch of services in the first

[00:06:10] **Adam:** place.

[00:06:11] **Adam:** I don't follow. If they're not services... What are they now? And they're not a monolith.

[00:06:15] **Tim:** I mean, I don't, I think the term monolith has a certain connotation. It's a very small, it's

[00:06:19] **Adam:** three pages. You're

[00:06:20] **Carol:** thinking of like a big application. This is just like an API endpoint.

[00:06:24] **Adam:** Yeah, I created

[00:06:25] **Tim:** three API endpoints and then a page to call them on a scheduled job.

[00:06:29] **Tim:** Okay. So, and it was like playing whack a mole, I mean, you'd take, I'd stop one service and all of a sudden the email service would just kick off and go, Hey, this and this is happening. Why isn't this? Oh, that service doesn't need to be there. So, eventually I just, I just went and stopped the database that it was running on.

[00:06:49] **Tim:** Because you said

[00:06:49] **Carol:** it was all running async, right? So, you didn't know

[00:06:51] **Adam:** really where. Yeah, it was all async.

[00:06:53] **Tim:** It was using Scala actor systems, um, and Scala is a great language, but just, it was not. It was not designed for the way it was, the way it was built was not designed for what it was doing. So, yeah, I'm happy with that.

[00:07:10] **Tim:** That's going to take a lot of headaches out of my life. Yay!

[00:07:13] **Carol:** What about you, Carol? I'm going with a tryout, too. Um, it was about, I think it's been about eight weeks now. Uh, we had the episode where I was like, we're starting this new project, you know, you guys have heard me talk about it multiple times, like as, as it's been progressing, uh, we're in production.

[00:07:28] **Carol:** Nice. So I'm, I'm really, really excited. Um, now we just basically are going to be making some additions and actually, um, let's see. How do I say it? So like this is the phase one of it that just went out. So we're getting in all the data, we're looking at it, we're getting... My customer is actually my business.

[00:07:48] **Carol:** So I work internal. So I write things that my company uses. To basically do everything that they, that they do, right? So my customer is the business. So I'm just going to be working with the business over the next couple of weeks to make sure that what we're doing is actually helping them and that it's causing our customers, which is their customers, to remain happy or be happier.

[00:08:08] **Carol:** So. Hopefully by mid July, I'll be completely off the project and we'll just be doing minor tweaks here and there. But we ended up with a web form that basically is like, hey, come to us if we can't help you. We have the autoresponder to give them back immediate feedback so we can give them information and then, you know, like, the web form can be used to address anything if we respond and it wasn't helpful enough.

[00:08:34] **Carol:** So, it's exciting.

[00:08:37] **Ben:** Is it, is it all Amazon

[00:08:39] **Adam:** services?

[00:08:39] **Carol:** Yeah. Everything's in AWS.

[00:08:41] **Adam:** Yep.

[00:08:41] **Ben:** Very cool. Yo, four triumphs. Yeah.

[00:08:44] **Carol:** Hey, we are winners. Wow. Has that happened?

[00:08:46] **Adam:** Awesome. I think it might have happened once in the past. Cool. Well, uh, our topic today was buy versus DIY and Tim, you suggested that. So why don't you, uh, get the discussion going?

[00:08:58] **Tim:** Okay. Sure. So, I mean, the basic question is. There's different philosophies on building software where you go out, some people just they buy different software that does a lot of things, kind of glue them together with some custom code and that's their product. That's one extreme. Other people build a hundred percent.

[00:09:20] **Tim:** Everything, right? From, from soup to nuts, everything. And there might be good reasons for that. I know that some government projects, they have a very limited set of vendors that maybe they can work with. So there might be some cool project out there you can use, but they can't use it. Um, so, but for most people, there is always a discussion that has to be made of, all right, we need to build product X that does these five things.

[00:09:46] **Tim:** Do you build all five of those things or do you first do a market research analysis and say, all right, are what software out there already does these five things? How much should they cost? Things like that. So that's kind of what I was thinking about, but that's have that conversation of, you know, at what point do you say, you know what, we're not going to build this, we're just going to buy it.

[00:10:05] **Tim:** Or you just say, you know what, let's just build it.

[00:10:08] **Adam:** So this kind of goes back to like our last episode where we were talking about passwords. So identity management might be something you would consider buying versus building your own.

[00:10:18] **Carol:** Yeah. So you're talking about your end result product. You're not talking about, oh, we need a way to track customers.

[00:10:28] **Carol:** So, we're going to write our own, um, ticketing system in house versus buying JIRA or you mean, that, I mean,

[00:10:34] **Adam:** that actually is a good example. A lot of companies do that.

[00:10:37] Yeah.

[00:10:37] **Tim:** Yeah. I know early on in our company, we built our own tracking system.

[00:10:40] **Adam:** I

[00:10:40] **Carol:** think Adam said that they had

[00:10:42] **Adam:** written one too, at one point.

[00:10:43] **Adam:** We still

[00:10:43] **Tim:** use it. And, and then eventually we just said, you know, let's just. You know, go to Atlassian and, and use Jira. Mm-hmm. So, so I mean that, I think that's a good example of, of if you're a company, how do you decide are you gonna build this thing and, and are you gonna buy it? Now, in our case, we didn't make any money off.

[00:11:01] **Tim:** That's not something we sold. Right. Building that thing ourselves. Yeah. Um, so I mean, there was a lot of cost involved in that, and that's sort of one what, that's sort of one of the pros and cons I see with, with buy versus build when it comes to cost. Um, you can spend a lot of time and money building your own stuff.

[00:11:19] **Tim:** But then again, you can also spend a lot of time and money buying someone else's stuff. I agree.

[00:11:23] **Carol:** Implementation isn't always the easiest.

[00:11:26] **Adam:** Yeah, I'm kind of realizing here if I'm, if I'm not mistaken, we kind of have the, the three different company modes that I can think of represented here. So my company is bootstrapped.

[00:11:38] **Adam:** We haven't had any outside funding, but we're still really small. We have a very small, tight budget, Carol and Tim, you guys both work in sort of a large company, corporate environment, a well established company. And then if I'm not mistaken, Ben Invision is, um, VC funded, right? Correct. So, I mean, that's, that's sort of three different.

[00:11:57] **Adam:** Perspectives on how you would make these decisions, I think.

[00:12:01] **Ben:** Yeah, we're actually having a lot of build versus buy conversations internally right now. Um, and in a previous episode, I had, I think I had mentioned that, uh, some of our future facing teams had built their own WebSocket implementations and, uh, they're discovering now that, you know, pulling Socket.

[00:12:20] **Ben:** io into a node application doesn't necessarily hammer out all the details of what it takes to manage a large scale. WebSocket implementation. So now we're trying to figure out what third party service would probably want to defer all of the WebSocket management over to. I think right now we're looking between Pusher and Abley.

[00:12:40] **Ben:** Um, but we're also having discussions about, uh, identity management, like Adam said in the previous episode. And then there's also discussions about things like whether or not we want to host a service versus have a managed service somewhere else, which is. Kind of another nuance to, uh, build versus buy, meaning like hosting your own database versus using Amazon RDS,

[00:13:00] **Adam:** something to that effect.

[00:13:01] **Adam:** Yeah, that

[00:13:01] **Carol:** is something Tim and I worked with previously was having a lot of on prem stuff, things that are on premise. Like we have our own data center, you know, we're hosting everything. So where I'm at now at Clear Capital, we have a big push for getting everything off prem, so it's all cloud. So we're trying to get out of the managing those.

[00:13:22] **Carol:** Environments and getting that over to like AWS, GCP, that type of stuff. We're

[00:13:28] **Tim:** going to be hybrid cloud. It's the new buzzword. Hybrid cloud, best of both worlds and the worst.

[00:13:34] **Adam:** I think that, um, you know, no matter which of our company types that you're in, you're going to end up having the discussion, right?

[00:13:41] **Adam:** There's always going to be some constraints that you're trying to meet or whatever, you know, there's the, the decision is going to be different depending on what the. Price of the tool is versus how long it would take you to build it and all that. But, um, I think it's possible that we would have like three different sort of, maybe even potentially four different sort of default postures.

[00:14:02] **Adam:** Um, you know, like you're still going to consider it and make a decision, but you're going to have... Uh, a natural bias based on your recent experience to either, you know, assume you're going to start here and then maybe the discussion will change the position. I'm curious what everybody's is.

[00:14:20] **Carol:** So, for this project that I just wrapped up or that we're wrapping up, um, when we first got kind of pulled into it.

[00:14:26] **Carol:** I spent two days doing nothing but Googling for software that already accomplishes at least half or more of what they're trying to accomplish on these OKRs. Wow. Because I was like, if there is already a product that can handle all the autoresponder, that can organize customer requests easier, that can make everything more streamlined, even if it only does half of what, um, we're looking for in the subset of work, That's still half that's already been vetted out and proven that I don't have to now vet out and prove.

[00:14:58] **Carol:** Yeah. So that was kind of my first go to was I want to go see if there is a product out there. A, can I adapt something that they're doing? Or should we just go straight to that product? And ultimately, it came into we'll use some of the good benefits of what we've looked at or like what I had found, but we're going to write it still in

[00:15:19] **Adam:** house.

[00:15:20] **Adam:** Tim, do you guys, do you feel like you guys are basically the same?

[00:15:23] **Tim:** Um, yeah, I mean, so we've gone through the arc early in our companies. We built everything, right? We, we had to, you know, we were single owned by a small group of private investors. Wasn't venture, it wasn't VC capital money. And so basically.

[00:15:41] **Tim:** We had to eat all our own dog food and that included building. We couldn't, if someone said, you know, spend 10, 000 to get this project management tool, we would have fell over dead. You know, we're like, no, we'll just, we'll just build it with sweat equity. Uh, and, but now sort of the default is, all right. So, what can we use to do this?

[00:15:57] **Tim:** I'll give you an example. For years, my default on every, like sending emails was, well, we got a mail server. Let's just send these emails. That's great when the email server works or if the emails get delivered. So, I thought sometimes these emails just disappear and you don't know why, particularly once we get bought out by another company and now it's going through another layer of corporate filtering.

[00:16:19] **Tim:** And it's like, I have no idea why you aren't getting your emails. So now I'd like, you know what? It's not expensive. It's pretty cheap. And I can track it. So SendGrid, you're getting all my emails from now on. It doesn't rewrite it. Uh, and I will say one thing I learned in that this isn't necessarily directly related to the pros and cons.

[00:16:38] **Tim:** This is sort of a code building thing. I wish I told my younger self to not write the emails in such a way that it was so dependent on it being a CF mail tag. I should have abstracted out that layer a little bit so that I could have more easily replaced SYNGRID with the CF mail tag that was there, right?

[00:16:59] **Tim:** So we're sending mail through just the native tools that are inside the language, but now I've got to go change all that. Had I, you know, abstracted that out to another layer, I could have a lot more easily

[00:17:11] **Adam:** replaced all that. Yeah. So for anybody that wasn't picking up on that, If you had had like a mail service and a single, you know, send email function in that, that would have the CFMail tag in it and you were calling that all over your application, then switching to SendGrid would have been as simple as updating that one function.

[00:17:27] **Adam:** Yeah,

[00:17:27] **Tim:** just change that one function and now make sure you're, the same thing's coming in that was before and the same thing comes out, you know, whatever it takes and the steps in between in those functions or whatever. But, uh, yeah, it's, it's. And SynGrid, you know, allows me to see the clicks. I can see if it got delivered.

[00:17:43] **Tim:** I can see where it stopped. So that's

[00:17:45] **Adam:** great. Having, having hand rolled a lot of that. There's no way

[00:17:51] **Tim:** I could have hand rolled all that. I mean, maybe I could, but I mean, just think of if I wanted to build my own SynGrid to solve a problem I was having with, with undelivered emails, how much time and money, and that's not my, that's not my area of expertise.

[00:18:05] **Tim:** So I'm so glad that. Back in the day, and that day, by the way, was a Wednesday, um, back in the day, you know, the pricing model for most software was, you know, they wanted a big amount of money up front and maybe you paid like a licensing fee or like a maintenance subscription per year, which was small.

[00:18:23] **Tim:** Well, now it's flipped. A lot of things are just on a per use or subscription basis, which is great because the barrier to entry as far as finances go is a lot lower.

[00:18:33] **Adam:** And kind of going back to what Carol was saying about spending two days Googling for stuff like, I can't imagine having that much runway available to me to, to spend two days looking for something that's, that can, uh, you know, mostly solve my project like that.

[00:18:46] **Adam:** That just doesn't compute for me.

[00:18:48] **Carol:** I don't take it for granted. Definitely. Cause I have come from places where I didn't have that availability and the research was all on my own after dinner, sitting on the couch, trying to fit it in. So to have that given to me, it's definitely. A luxury I enjoy.

[00:19:04] **Adam:** One of the

[00:19:04] **Ben:** nice things about building something.

[00:19:07] **Ben:** is that you can see what it's doing. Whereas when you buy something, oftentimes you have either no access to it or very limited access to it, or it's just terribly complicated and figuring out how it works is, is, is a very difficult. And, and if you go down to the micro level of build versus buy, you kind of get into the package level where I could build a is valid email function, or I could NPM install an is valid email.

[00:19:41] **Ben:** And I tend to err on the side of building small things. The smaller something is, the more I tend to just want to build it because then I own it and I know how it works and I can open up the source file and it doesn't have to typically be as robust. And in fact, like generally when you're building something yourself, it doesn't have to be as robust as the thing that you're buying because the thing that you're buying has to cater to more people, has to cater to more types of solutions.

[00:20:09] **Ben:** So there is a, there is a focus you can get with building something.

[00:20:13] **Tim:** But the anti argument to what you just said is that because they had to make it robust, therefore it's going to be more robust than yours. Yeah,

[00:20:20] **Adam:** I was kind of thinking about that too. So the, you brought up an interesting point, Ben. So there's build and buy, and then there's open source and you're kind of buying it from open source.

[00:20:29] **Adam:** You're using somebody else's thing. And I tend to agree with you, I think, in terms of like, if something is simple enough, like just build it yourself. If it would take me longer to find the right module on NPM and verify that it doesn't have a bunch of malicious dependencies and that sort of thing than to build it myself, then yeah, I'm just going to build it myself.

[00:20:47] **Adam:** But at the same time, sort of the other side of that coin is the, is valid email is a bit of an... Like an extreme simple example, but for something that's slightly more complex than that, I might, I might tend to err on the side of using the open source solution, especially if it's free, like, you know, NPM module, uh, because.

[00:21:09] **Adam:** And especially if I find one that has lots of tests, then I know it's probably going to be better tested than I would do. Right? Like, especially, you know, my, my longstanding habits of not testing very much or, or very well. Um, so that would make me feel better knowing it had, you know, if I, especially if I could see the tests and, and see how thorough they are.

[00:21:32] **Adam:** There's something to be said for that. Yeah. So, what do you think your posture is, your default posture at InVision, do you guys tend to buy unless you feel like you are confident you can build it better, cheaper, faster?

[00:21:47] **Ben:** Oh man, I think we're all over the place. I think we build a lot of stuff internally and we buy a lot of stuff and, uh, at one point, oh my God, it's embarrassing to admit.

[00:21:58] **Ben:** I think they, they, one year, a couple of years ago they did an audit of how many third party services we use. And it was like. Over 300, which boggles my mind. I didn't know they're worth 300 services you could pay for, but it's just, you know, between all the marketing stuff and the contact management stuff and the business intelligence stuff.

[00:22:20] **Ben:** I mean, I'm just making

[00:22:21] **Adam:** up terms. But then you get your Jira and you know, that may include like Trello gold or something.

[00:22:27] **Ben:** It just, it boggles my mind. I, I was actually just reflecting on this the other day in terms of my own mentality and I, and I don't know where the line is there. There's definitely things that I love to build.

[00:22:39] **Ben:** And then there are things that I have absolutely no interest in building at all. And I, and it's almost just like some gut reaction to whether or not I think I'm even capable of building it. I think when I know that I'm not capable of building it, I have no interest in even trying to build it, where I get into trouble.

[00:22:58] **Ben:** It's when I look at something and I think to myself, yeah, I could do that. And, uh, and I don't sort of sanity check that, uh, that emotion. And then I tend to, to build when maybe I should have.

[00:23:10] **Tim:** Adam, you kind of brought up an interesting point. I didn't really think of that angle about, about open source.

[00:23:15] **Tim:** Where does that fall, right? Is that, is that bill? Does that buy? It's a little, it's not really both. I mean, you're building it, right? Cause you have to take it, you have to build it, but you're not actually. You're consuming it, so you're buying it, but the price is free, but the thing, even with paid software, this is, this is one of the cons of paid software.

[00:23:37] **Tim:** What happens if that, the open source project stops being maintained? Well, at least with that, you can download it and you've got the code and you can become the maintainer yourself. So that's, that's good. But if it's, if you bought it and it goes end of life or it just, they stopped doing the service, you know, now what do you do?

[00:23:55] **Tim:** Well, now you've got to find another solution or. Build it yourself. So you're back to where you were before. So, I mean, that is a con of mine. The companies go out of business. They get a few years back. I started writing a project, and I was, I had selected a vendor for a certain thing. It was had to do with telecoms and something I couldn't do.

[00:24:15] **Tim:** Right. And so had a relationship with them, worked with them for about six months, and then they got bought out by Twilio. And then all of a sudden, that's, no, no, I'm sorry, take that back. It wasn't Twilio, it was Cisco. And Cisco was not taking this and selling it as a product. They were just consuming it for the technology for themselves.

[00:24:36] **Tim:** And they were not, so basically, so they shut down. They're like, we're sorry, we can't do business with you anymore. We're part of

[00:24:42] **Adam:** Cisco. It's like the opposite of an acquihire.

[00:24:44] **Tim:** Yeah, they just bought it. They just bought it for the IP. And so I had to, I had to find another service to replace that. So that is one con.

[00:24:53] **Tim:** They can, they may not always be there or, you know, they might go out of business.

[00:24:58] **Adam:** Well, I guess to round it out here, speaking for, I hesitate to call my company a startup, but we kind of are. We're like a bootstrap startup, you know, just no outside funding. And I, I think our default position is we're sort of 50 50.

[00:25:13] **Adam:** If it's a obvious, like primitive piece of the web. So we're talking like a database, the ability to send email. Stuff like that. Um, we tend to outsource those things. So we're using like Amazon RDS and we use Twilio for text messaging. We use Mailgun for sending email and, you know, a bunch of other things.

[00:25:33] **Adam:** But short of that, um, we run on a pretty tight budget. And so our sort of default posture is if it's not like a commodity service, like email, that sort of thing, then. We tend to at least build first and, you know, get something that's good enough. Like do, do the MVP product of that service and just ride that into, into the ground until it's so terrible we can't do it any longer.

[00:26:01] **Adam:** And then we'll upgrade and transition over to some, you know, switch our, in probably another five years, we'll switch our tickets internal to our product into Jira or, or, you know, Zendesk or who knows what, but it's going to be because. Everybody hates working with our current ticket system and the customers hate it.

[00:26:18] **Adam:** And you know, it's time, right? We were going to extract as much value out of those hours that we put into building it before we, before we switch over to something else.

[00:26:28] **Ben:** I think there is something very significant to be said though, about when you build something, you can create that MVP style approach because, uh, you know, software is evolutionary.

[00:26:42] **Ben:** And you don't necessarily know what you need. And even if you do research and you try a product, you run into situations where maybe it didn't work, or maybe it just does way more than you needed it to. And then it becomes a question of whether it's worth the cost, but being able to experiment in your own code space with your own abilities, I don't know, other than the joy of doing it because we're engineers and we love to build stuff, I think there's, I think there really is a value to being able to.

[00:27:18] **Carol:** I think you weigh out the cost of that initial purchase and determine if you want to battle through writing it yourself.

[00:27:25] **Tim:** But I mean, I think you need to make that search first, right? If your first gut instinct is hand on keyboard, let's build this, you know, first go out and say, all right, what's out there?

[00:27:36] **Tim:** And that's kind of what I do. I, first thing I do is, is there an open source project that does this? Yeah.

[00:27:41] **Adam:** Yeah. Okay. Like someone else has to have had this problem.

[00:27:43] **Tim:** It solves this issue. If not, all right. I found some, but I'm not too thrilled with them. Are there companies that do this and what's their cost?

[00:27:52] **Tim:** And then afterward you sit down and you make the decision, right? How long do I think it would take this for us to build? Is that worth the time? Can we be building something else that will make, you know, that's more effective use of our time? And money and resources then, and it'll use like that. So it's just a calculation you have, I think everyone should do.

[00:28:12] **Tim:** Um, and there's no right or wrong answer. It totally depends on, on your core competencies. Totally depends on, you know, how much budget you have. There's so many limiting factors, uh, that, that come into play

[00:28:23] **Adam:** here. Yeah. I was going to say core competencies as well. That's, uh, something that we've been discussing a lot internally, like the ticket thing, like we recognize that.

[00:28:34] **Adam:** Uh, having a ticketing system and maintaining the features of that ticketing system is not our core competency. That's not what we're selling, uh, but it's necessary for us to get our work done. So we need something that's just good enough for as long as possible. And then when it's not good enough anymore, then we'll start paying for it.

[00:28:51] **Adam:** Um,

[00:28:52] **Ben:** you can also abandon stuff that you're building, which, which you maybe can't necessarily do as easily if you're already paying someone else to, to build it for you or, you know, to host it for you just because contracts get involved and, you know, it's some cost savings, you know, maybe you open up a two year contract or something and you get into a couple of months of it and you're like, ah, this isn't really doing what we want.

[00:29:13] **Ben:** Yeah,

[00:29:14] **Tim:** that's true. What one great pro by building software is that, you know, if you have a feature that you absolutely need. You can do it, right? You can prioritize that. You can build that yourself. You might not necessarily get that same response from whatever vendor you've gone with or whatever open source project you've gone with.

[00:29:31] **Tim:** They're like, yeah, it's a great thing, but you know what? That might be on our 2023 roadmap. Um, okay. Although I will say that one of my, I was quite surprised there, there, there are another. And they, they use Amazon Polly to create the voices for this, uh, integrated voice system that we have. And I really wanted, they only have like two default Spanish voices and they're not really that great.

[00:29:59] **Tim:** And so I'm like, Amazon Polly has a whole bunch of them. And so I sent him an email. I'm like, Hey, why don't you guys have these different Spanish accents from, from Amazon? I mean, how hard is that to put in? And I'm like, Oh, okay, we'll look into it. And then two weeks later they put it in. It was in their product.

[00:30:14] **Tim:** I was like, that's awesome. Thank you. So, so, but that is totally outside the norm. That the only reason I can bring that story up is because I've never had a company, you know, that's, you know, it's worth millions and millions and I put in a request and they're like, yeah, we'll do that. When I'm paying just a monthly subscription fee, most of them are like, most of them close my ticket and say it's resolved.

[00:30:37] **Adam:** They haven't done a damn thing. Or don't reply at all. No,

[00:30:40] **Tim:** they reply. They ought to reply to her. Yeah. We'll, we'll get to it. Thank you for your input. And then it's like two weeks later, they just close it with no comment. If I could have an old man moment. Yeah, do it.

[00:30:49] **Adam:** Do it. Do it. Do it. Do we need a jingle for this?

[00:30:51] **Adam:** Ben's old man moment every week.

[00:30:53] **Ben:** One thing that gets under my skin. It's when I see people install modules for something that is almost practically supported by the language you're already using, plus like one tiny little thing, like, I mean, an example that pops to mind that's made up, but, uh, so there's base 64 encoding and.

[00:31:14] **Ben:** I think all languages have some sort of Base64 encoding, decoding. And then there's a, uh, a format. I don't know if this is a de facto, uh, an official format or this is just a de facto format, but there's something called Base64 URL, which is a URL safe version of Base64, which is Base64. And then you replace out like two of the special characters in the Base64 character set.

[00:31:39] **Ben:** And I, and I feel like if I was in a project and I saw someone NPM installed, A base 64 URL module. I would think to myself, that's literally base 64 and two replace calls. Like the fact that you installed that makes me feel like, I don't know. I don't even, it's just like a weird emotion that I have. It's like this.

[00:32:01] **Ben:** It's almost like a laziness, like you didn't, no, there's like, there's times where it's it's whether it's like it, it demonstrates that the person didn't think about it at all, or they don't understand the language that they're using. Maybe a more real example is I came across something in our code base the other day where someone had installed a library.

[00:32:26] **Ben:** That converted a JavaScript date value to a UTC value to get the millisecond timestamp. And I thought to myself, but dates are already millisecond UTC timestamps. They were, they were like taking the date, converting it to the user's time zone, and then converting it back to UTC to get the underlying milliseconds.

[00:32:48] **Ben:** And I was like, you, you just don't understand how dates

[00:32:51] **Adam:** work. I mean, to be fair, dates in every language are terrible. And date math is awful. Yes, yes, yes. See this area of my forehead that doesn't have hair on it anymore? I called that date and that one, I don't even know where that one's from.

[00:33:14] **Tim:** I broke him.

[00:33:25] **Tim:** Good job. You broke

[00:33:25] **Adam:** him.

[00:33:29] **Ben:** I'm good. Are you? So, I don't know where that emotion comes from, but, um, I don't know, sometimes I feel people just go, some, I, I get bothered, I think when the default gesture is just to search NPMJS, is that the site? Sometimes I wish people would do a little bit more building and a little less buying when it comes to NPM modules, but I don't know if that's just like me sitting up on my ivory tower or.

[00:33:58] **Adam:** I understand that emotion, and I think that my version of it is that I am in favor of using tiny modules that simplify things, but I want to see them implemented without any dependencies, if possible. Right? What grinds my gears, if we're getting into that, is, uh, you know, you install, you know, something that's, you know, 2base64 or whatever, and it's got 43 dependencies, and it's 7 meg download.

[00:34:26] **Adam:** I would like to see that. No ,

[00:34:30] **Ben:** yo. A hundred percent. I, I get so bothered when I go to a, a GitHub repository for a, a file that's like three lines of code and then you go into it and it's like 47 files with all kinds of 16 pages of documentation, dinging and editor configs and read mes and, and tests and.

[00:34:48] **Ben:** And I don't know, I just, I feel like if you had just written those three lines of code yourself, you wouldn't need those 47 other files. You done gripe it now?

[00:34:57] **Tim:** Yeah,

[00:34:57] **Adam:** I'm good. Gears all around. So

[00:34:59] **Carol:** something that, um, Tim said multiple, you know, comments earlier, I've jotted down a note. He was talking about, um, you know, do what you're good at.

[00:35:11] **Carol:** So, you know, if your team's not good at building this, then I think it's a good idea to source that out, you know, to use what you're good at. But the other thing is to consider is that if you are building it, um, think about building to buy. And I know he kind of said that too, which if he had written it correctly, that, you know, it would have been a lot easier to pull that out.

[00:35:33] **Carol:** So if you do build that and you go small with it, build it with the thought that you could at some point replace this with some enterprise level, you know, product that's going to do a lot more for you and it's going to be easy for you to then switch out, which then saves you money when you're trying to, you know, convert over.

[00:35:51] **Adam:** The same is also true. If you buy one thing, you know, if you, if you make a custom wrapper for it, you know, whatever that is appropriate in your language, the way to implement that, but then. Again, if you just, if you decide, if they shut down or for whatever reason, you decide to switch to a new service, then you've got to change it in one place and that place is reused.

[00:36:11] **Tim:** I think another pro and con. So, you know, I talked about, I'm glad that we've gone to a software as a service thing, but all that really means is we've shifted the upfront costs to a long term cost and those long term costs can add up. Right? So, be rest assured. The service you're using, they are making a profit off of you.

[00:36:31] **Tim:** They're doing what you possibly could do for a profit and then charging you for it. And that's okay. I mean, that can be okay, but got to realize that at scale can add up. So it just totally depends on where you're at and as a company and what you're doing. Um, at some point, bigger companies realize, well, we're using the service.

[00:36:53] **Tim:** I'm not saying I'm a bigger company. I'm just imagining, um, that You know, we're, we're paying this much for the service. We really, you know, if we just, we have all these resources, let's just throw, you know, a team at it and, and just take this out and we'll save. You know, 200 million over the next 10 years by not paying this one service that, so that is a pro and a con that upfront costs are lower, but the long term costs could be a lot higher.

[00:37:21] **Tim:** Well said.

[00:37:22] **Ben:** Has anyone had any, uh, terrible experiences with buying stuff? Just out of curiosity.

[00:37:27] **Tim:** I have. I just try to remember where they are. I block them out. PTSD kicking.

[00:37:33] **Ben:** We've had a lot of effort that has gone into migrating from one payment service to another paid service. And that's like, we'll go with one vendor who does XYZ.

[00:37:48] **Ben:** And then two years later, you know, maybe our usage has gone up and they're become now cost prohibitive. And now we have to move to a same type of vendor doing the same thing, but maybe at a more attractive price point. And it's shocking sometimes how much work it is. To rejigger the application to do exactly the same thing, but with someone's slightly different API or, or, you know, they're using a library versus some sort of sidecar model and a Docker container or something.

[00:38:18] **Ben:** I don't know. It's like, just, it's, it's, uh, we've had a, we've lost, I would say months in aggregate of time going between vendors who do the same thing.

[00:38:29] **Tim:** Ooh, I've got one, Carol. You'll know this one. Do it. We can't name any names here, but, um, yeah. So, I mean, sometimes when you, your company kind of is like strapped for resources, like everyone is just.

[00:38:43] **Tim:** And you really don't have a lot of extra space to build on. Sometimes building partnerships, which is really just a fancy term for having a vendor, um, that you, that you, you know, present to your customer as a partner. Um, so we, we had a, a need with, um, dynamic document generation that was beyond what our normal system did.

[00:39:07] **Tim:** And so yeah, Carol's eyes just lit up. She just knows who I'm talking about now. So I, I found this, this company, they're a great company. I really, I still stay in touch with these people. I'm actually friends with them on Facebook. They're fantastic folks and their software is amazing and it's expensive.

[00:39:23] **Tim:** Um, but you know, we presented this to one of our customers and like, we need it. Absolutely need it. Absolutely need it. Right. So put it in their system. And I don't actually even know if they still, do they still use it? You know, Carol?

[00:39:35] **Carol:** Yeah, they still use that, and it is a pain in the ass for everybody. You talking about being hated?

[00:39:43] **Carol:** Ugh.

[00:39:46] **Adam:** Okay, well,

[00:39:47] **Tim:** it was impressive software, but I guess the implementation of it wasn't as

[00:39:50] **Adam:** good as the demo. Yeah,

[00:39:52] **Carol:** every time we would deploy any, so, um, the way that they test and stuff is they have a cycle server. And basically it lets them change the clock. So you're talking about our customer or not? Our customer, that customer at the time.

[00:40:07] **Carol:** So every time they would run the clock up, every license of that would expire, which would cause everything to crash and there was no way around it. So then every time they're trying to test what would happen, like when policies renewed or when, you know, these things happen in the future and they're trying to test it.

[00:40:25] **Carol:** Nothing in the system would work because they couldn't allow us to move forward at all. So it was just a nightmare testing anything. So they ended up having to spin this off on its own server, then we had to rip code out so that it would never know about it because we didn't have feature flags. Okay, Ben?

[00:40:41] **Carol:** We So we had to rip the code out so that now there's basically two branches running. One to test future like cycle things and one to test, you know, not.

[00:40:53] **Adam:** Yeah.

[00:40:53] **Tim:** So I consider that a bad because I saw that as a partnership, but after going through that, we realized we really couldn't, I mean, there we could give it to one of our customers who paid and they paid for it.

[00:41:04] **Tim:** It wasn't, you know, our, it was our pain, but it wasn't our, our bill. Yeah. And, uh, yeah, so it's like. Yeah, I wish we hadn't, wish we hadn't bought it.

[00:41:14] **Adam:** I have a little bit of a relevant story. It's not exactly fitting the mold of the question that you asked, but it feels very close. So, um, we have a variety of customers and they have established relationships with different payment gateways.

[00:41:29] **Adam:** Uh, in order to be able to work with a variety of different payment gateways, we use a service called Spreedly that integrates with a bunch of them and then sort of aggregates it all into one API. So we call the Spreedly API and we say we want to use this gateway. And here's the information to charge the credit card.

[00:41:44] **Adam:** And, and it does all that for us. And, um, then we had a requirement come up to be able to do things like PayPal, Venmo, Apple Pay, Google Pay, that sort of stuff. And Spreedly doesn't support any of those, but then, um, Braintree does support those. And so it kind of fell on my plate to update our entire application and all the different modules that collect money to be able to.

[00:42:11] **Adam:** By configuration, switch between using Spreedly or Braintree, and that was a bit of a nightmare, but at the same time, I feel like if I had, um, like Tim was saying, if I had built that gateway thing into its own wrapper, we felt so safe because Spreedly is an aggregator, right? We, we didn't wrap that in A single point of, of interface because we felt, I guess, just safe that they would be able to do anything that we wanted.

[00:42:38] **Adam:** And then when this extra requirement came along, I ended up having to do all that same touch everything, uh, work. To be able to switch between gateways effectively because, uh, you know, one service provided stuff that the other didn't and we needed to be able to do that. And if I had done, uh, a wrapper around it, then I would have been able to handle that a lot easier.

[00:43:02] **Adam:** And that's kind of what I ended up doing is, is implementing that wrapper, as well as the... Uh, configuration to switch between them. I feel like payment

[00:43:11] **Ben:** stuff is especially sticky. We've had a couple of different payment processors and they're all just. different enough that I almost feel like having some sort of clean abstraction is

[00:43:25] **Tim:** like a, it's a pipe dream.

[00:43:26] **Tim:** Hey, hey, hey, hey, I'm a payment processor.

[00:43:30] **Adam:** I was like, see if you need a new one.

[00:43:33] **Ben:** Third time's the charm. Yeah. Right. Plus like, you know, you get all bank codes come back and different processors tell you different reasons why cards get rejected. And I feel like once you get payments working, It's like, you just sort of do that, like the Homer Bush, you know, disappear into the

[00:43:51] **Tim:** air.

[00:43:51] **Tim:** Don't touch it again. Please, please keep doing that. Become our customer and then keep doing that. So we round it out? Yeah, well, I would, I got one more pro and con. So I would say, so In, in marketing speak and sales speak, you talk about your competitive advantage, right? It's like, what is the thing you do that no one else does?

[00:44:10] **Tim:** And that is honestly one of the hardest things in the world to explain and to put into good words without being hyperbolic or just flat out lying. That's what

[00:44:20] **Adam:** you're talking about with core competencies, right? This is the product that we're selling. And it doesn't, well,

[00:44:26] **Tim:** your, your core competency can be the exact same thing as someone else's.

[00:44:30] **Tim:** There's no competitive advantage there. You're both doing the same thing. What do you do that no other company does that? That's like the thing in marketing everyone, like every marketer that we've ever hired or work with, the first thing she says to me, or he says to me is, what is your competitive advantage?

[00:44:45] **Tim:** And that's really a hard question because most people aren't doing completely unique things.

[00:44:51] **Adam:** Our website is blue.

[00:44:54] **Tim:** Right. Yeah, exactly. We're cheaper than the other guys. We're, we're nicer. People like us, we're really friendly. When, if you,

[00:45:03] **Adam:** when

[00:45:04] **Tim:** you have an error, we don't yell at you. Um, so. But if you're just using a bunch of off the shelf software that other companies can buy and gluing them together, you really don't have a lot of differentiators, or, you know, things that make you different.

[00:45:22] **Tim:** If you've built something that, that legitimately no one else does... You for a moment have lightning in a bottle and should sell that as hard as you can because eventually someone else is going to do it or someone else has already done it and just no one else knows about it. So that is a con of just pulling in a bunch of other software and gluing them together.

[00:45:45] **Adam:** All right, let's, uh, let's wrap it up then. So if you like what we're doing here, you might want to consider supporting us on Patreon. You can find us there at patreon.com/WorkingCodePod. Every patron gets an invite to our discord server and we have other perks available, like early access to new episodes when they come out and the after show, which is what we're going to go do as soon as we hang up on you guys.

[00:46:04] **Adam:** We're going to go spend another 10 to 15 minutes talking about something totally random and. Probably unrelated to the

[00:46:09] **Tim:** show and Ben will complain a bunch.

[00:46:14] **Adam:** Our top tier on Patreon is for people who want to pay a little bit extra and to repay the favor. We thank them by name or shout something out in their honor.

[00:46:21] **Adam:** And we have two top patrons right now. So thank you very much. So an extra special thank you goes out to Peter and to Monte. Thank you guys to everybody that just listens to the show. Thanks for listening. Please share the show with your friends and co workers because there's no better support than a word of mouth referral.

[00:46:36] **Adam:** Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts. Send us your questions and topic suggestions on Twitter or Instagram at @WorkingCodePod, or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until then, remember guys,

[00:46:55] **Tim:** your heart matters.

[00:46:56] **Tim:** And apparently according to some of our patrons, even the host hearts matter.
