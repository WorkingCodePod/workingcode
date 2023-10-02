---
title: "146: Resiliency is Hard"
description: "On today's show, we talk about the complex systems that we've built personally; and, how we attempt to keep them online in the face of uncertainty."
date: 2023-09-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/146-resiliency-is-hard/id1544142288?i=1000629373959"></iframe>

The products that we build can become quite complex and involve many interconnected parts. Due to this complexity, and to the properties of the natural world, these products _will_ begin to fail in new and exciting ways. There's really no way to stop a system from failing; but, we can build systems that are _more resilient_ to failure. That said, this is oftentimes much more challenging than we expect. On today's show, we talk about the complex systems that we've built personally; and, how we attempt to keep them online in the face of uncertainty.

As a funny aside on the topic of complexity, checkout Tom Scott's video: [The Problem with Time &amp; Timezones][tom-scott].

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[tom-scott]: https://www.youtube.com/watch?v=-5wpm-gesOY
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/146-resiliency-is-hard.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** Resiliency is hard.

[00:00:01] **Ben:** Yeah. Resiliency is hard.

[00:00:03] **Adam:** You just don't know what decisions you're making today that are going to come back in five years and make you regret not taking that career as a ice cream truck driver.

## [00:00:14] Intro

[00:00:14] **Adam:** Okay, here we go. It is show number 146, and on today's show is just myself and Ben. Good to see you again. and let's see, Carol is, you know, doing moving stuff, trying to get her life back, into something resembling normal, and Tim is sick, so he's not able to join us tonight. so just the two of us, and on tonight's show we are going to be discussing how resiliency is hard, building res building a system for resiliency.

[00:01:01] **Adam:** So Ben said something about that. He said it seemed like he had some stuff he wanted to talk about. So

[00:01:06] **Ben:** I got some stuff on my mind.

[00:01:07] **Adam:** yeah. And you know what? And it's gonna, it's gonna dovetail to use a term from multiple parts of my life. Nicely with my, triumph or fail today. So with that, let's start with our triumphs and fails.

[00:01:20] **Adam:** And Ben, what do you got?

## [00:01:21] Ben's Triumph

[00:01:21] **Ben:** my triumph is going to be that I have been writing. I've mentioned this on previous podcasts. I'm intending to try and write a small technical book and, I've actually been putting action to those thoughts and I've been waking up and I've been doing that and, and putting pen to paper. I'm still, I think, in the trying to make it look too good out of the gate. I feel like I need to be much better about just barfing my thoughts onto the page and then worrying about the, the polish later. So I'm, I'm still trying to find my flow. I've, I've never written anything in quite this long form format.

[00:02:02] **Adam:** I've read your blog. That's lie.

[00:02:04] **Ben:** I, you know, I've been, I've been blogging for a long time, but it's, it's always so much more focused and this is,

[00:02:09] **Adam:** never more, never less than like 5, 000 words.

[00:02:14] **Ben:** so this is a, a somewhat familiar, but also very, very new experience for me, but I've been doing it and I'm, I'm

[00:02:22] **Adam:** That's

[00:02:22] **Ben:** excited. I'm excited. I feel like I'm putting, putting one foot forward.

[00:02:26] **Adam:** Yeah, I'm, I'm pumped for you.

[00:02:28] **Ben:** You know, I know that you have published a book, so I think, you know, not to tease out the, the after show here, but we might talk about in the after show.

[00:02:34] **Ben:** I'd love to maybe pick your brain about some of the book stuff. Cause I, I feel very unsure about how I want to navigate the waters of publishing and, and, and there's a lot of questions.

[00:02:45] **Adam:** Sounds like a great after show topic. So yeah, let's, let's plan on that. Um, Well, I'm super pumped for you, man.

[00:02:51] **Ben:** Yeah. Thank you. thank you. That's me. How about

[00:02:53] **Adam:** you?

[00:02:53] **Adam:** Been, I've been trying to keep up, reading with, the bits that you've been posting on the website. Do you want to mention the, the, the website and what

[00:03:00] **Ben:** Oh, sure. So, you know, I, I've always been so, I love the fact that people like Wes Bos, they come out with a product and then they have a website that's exactly that product, like, learncssflexbox.com. I don't remember exactly what he has, but anyway, so I have this book. It's about feature flags and I check the domain FeatureFlagsBook, and it was available, so I bought it. And, uh, so if you go to FeatureFlagsBook.com, I'm sort of working out in public currently, and I have a couple of rough, to call them chapters is maybe a little bit of an overstatement. I've been calling them sections. Chapters feels way too formal.

[00:03:36] **Ben:** But I am sort of, I have an outline of the book, a working outline. This is all very rough draft and, and I've been putting some stuff together. And, I don't, so yeah, check it out. you can leave your email address so far I have done nothing with those email addresses, but I assume I will let people know when, there's more to be had, but,

[00:03:52] **Adam:** Are they going on to like a convert kit list

[00:03:56] **Ben:** are literally getting written to a dot TXT file on the server.

[00:04:01] **Adam:** Nice. Hey, that's something, man.

[00:04:03] **Ben:** Yo, yeah, exactly, exactly. So anyway, that's me.

[00:04:08] **Adam:** That's, I mean, honestly, that's the, that's the level of keep it super simple instead of keep it simple stupid, that you need to be taking with the whole book, right? Like, not just the... The, the tech behind it,

[00:04:20] **Ben:** I, I agree. You know, I'd, uh,I think the first three paragraphs of the book took I'd say two days to write and that's crazy. And then, but then it was like day three, I think I got four paragraphs done and then I started to pick up a little bit of steam, but I'm still in that. I mean, I've been doing this a week, right?

[00:04:39] **Ben:** So it's, it's not, I don't have a ton to show for it yet, but I have something.

[00:04:44] **Adam:** yeah, yeah. Anyway, let's, let's save,

[00:04:46] **Ben:** Yeah, yeah, yeah. Save it for the after show. What about

[00:04:49] **Adam:** I'm, I'm proud of you, but, yeah, let's move on.

## [00:04:50] Adam's Failure

[00:04:50] **Adam:** So, I have a fail this week, uh, and it's actually a fail from today. So,

[00:04:56] **Ben:** So fresh.

[00:04:58] **Adam:** and it's not, I mean, the truth is it's not a hundred percent from today. I made a change yesterday toward the end of the day.

[00:05:05] **Adam:** Like, let's just say 3 PM. So I don't know if that's it exactly, but close enough. And, I left it out there as a pull request, and now, what is the opposite of in my defense? In my, uh, in my prosecution, I did click the button to set that PR up for auto merge. I don't know if you know, GitHub has this as a feature now.

[00:05:25] **Adam:** Like, you know, how you can have like, tests that automatically run, and you can require reviews and stuff. Right, and some of these things can take a while, so instead of, like, making you asynchronously, like, check on it a couple times, see, do I have my reviews, have the tests run, is everything in mergeable shape, okay, now I can press the button to merge it, they now have, like, a thing where if you enable it for the repository, I think, it's probably a repository setting, but it is enabled for us, You can click a button called enable auto merge, and so then once you have all of the requirements satisfied, right, it's the up to date with the base branch, you're passing your tests, you've got reviews, you know, whatever the, if you're, if you require like commits are signed, et cetera, et cetera, et cetera. Once all of those requirements are met, it will automatically merge. And I did click that, that button, which for us, for production deploys, does not deploy the code. You know, I, that's something I've flirted with the idea of like auto deploy when you merge domain, but at the moment we are keeping a human in that loop

[00:06:27] **Ben:** I respect that.

[00:06:28] **Adam:** yeah, I mean, it's.

[00:06:30] **Adam:** Part of the reasoning is that, you know, what if we want to merge five pull requests and just deploy them all at once, right? Like, and they actually have a new feature for that called deploy trains or merge,

[00:06:41] **Ben:** merge. I have not heard of the, I've not heard of a

[00:06:43] **Adam:** I don't think it's deploy trains, but they're all, they all mean the same

[00:06:46] **Ben:** Yeah, yeah, yeah.

[00:06:47] **Adam:** I think GitLab has a similar feature, but either way, where you can say, okay, I'm going to group all these PRs, merge them all as one and And it, like, it does things where it like, this is not at all what we're talking about. We're, we're way off on a tangent here. But it, like, it runs the tests for them, or it runs the repository tests for, that are applicable based on the changes.

[00:07:06] **Adam:** and it can like tell you which one, like when it, when it adds it to the group, which one is broken or breaks the build so that like, You don't end up in a situation where you're like, okay, I have 10 PRs I want to merge together and I merged them all into one branch and now the tests fail and it's like, great, which one broke it?

[00:07:24] **Adam:** Right? I think that this thing can kind of, sort of, bisect that, that set of changes and tell you, okay, this is the PR that breaks it. Anyway, So that's why we don't have a human, or that's why we do have a human in the loop for our prod deploys. All that to say, it was not automatically deployed yesterday.

[00:07:41] **Adam:** It's not like I like, you know, made this change and then threw a match over my shoulder and left punched out at the end of the day. Right. but it did get merged and then somebody else later in the day, who's in another time zone west of here, right? So it was still business hours for him after I was done working for the day.

[00:07:58] **Adam:** He made changes and he merged and deployed his changes. Which now included mine.

[00:08:05] **Ben:** Brought yours up for the ride.

[00:08:07] **Adam:** Sure. And so that is probably my, the, the crux of my failure is that I, I merged it when it wasn't, I wasn't ready for it to go to main. Like the code I thought was in good enough shape to go to main, but I wasn't there to, you know, parent it all the way through deploy and, and, uh, success.

[00:08:23] **Adam:** And we had tested this in QA, but it wasn't. you know, maximally regression tested in all of the places and that turns out to have been necessary because my code went to production and things started breaking, and it's funny because it's like it only, it only affected certain things in certain ways.

[00:08:44] **Adam:** Basically, It was a JavaScript change and it resulted in, you know how like old school JavaScript, if you like had some invalid JavaScript syntax or a, or a, a runtime error,

[00:08:56] **Adam:** None of the JavaScript below that on the page would run, right? You've got your script tag and it's all just in there in the page

[00:09:02] **Ben:** It's like the interpreter just breaks and stops interpreting.

[00:09:04] **Adam:** right, and so none of the JavaScript below that executes. That's basically what was happening. You know, we've got my thing over here, which is not a super consequential thing.

[00:09:13] **Adam:** It's the phone number input field. and then as a result of my thing being broken, now we are accepting event registrations without payments because we're not getting, because the JavaScript that triggers the modal to collect the payment isn't working. And so then it's off to the server, empty payment token and purchases of memberships and...

[00:09:38] **Adam:** Like, I don't know. I want to say 10 different places and they're not all payment related, but it was like, just things just started breaking and breaking and breaking. And, a call was made and I was not aware of this, but a call was made last night that like this, it's okay. It's just event registration.

[00:09:55] **Adam:** We have tooling in place to, to, recognize and reconcile these later. You can say like, okay, you know, send them a bill and they can go online and pay it, they don't have to re register or anything like that sort of thing. So it, it was decided last night not to pull me out of bed or anything to, to deal with this, but then this morning I get in and there's like 40 plus event registrations that are all borked because of this and you know, a whole boatload of tickets that people will put in and this isn't working and that's not working and it's just, it's a terrible way to start the day and between that and a totally different issue that I, that was sort of dropped out of my plate.

[00:10:35] **Adam:** Simultaneously, I guess we'll say, I spent my entire day today just fighting these fires, dealing with the tickets, doing like, I think we probably did 15 to 20 production releases today, like, okay, this one's fixed, push it out, right? So that at least in small increments, the site is getting better instead of trying to fix it all in one big,

[00:10:56] **Ben:** So it wasn't just one type of error. It was, it was a number of different types of error just in random places.

[00:11:04] **Adam:** This is, okay, this is why I said it dovetails nicely with building resiliency. So, this, maybe let's use this as sort of transition to get into the main topic of the show here. So I mentioned this was the phone number input. You may have seen phone number inputs across the web where like it's a text box where you type in your phone number and it's got like a little flag dropdown in the left side of that input.

[00:11:27] **Adam:** That is a, that is all based on a library that Google made open source many years ago called, lib phone number. for, for phone number validation. It even says like, okay, if you choose, UK right, it has to, it, it, it knows what the phone number formats are there. So like, if it's only, if you choose a country where it's like only expecting six digits after the country code, then it won't let you, Like it marks it as invalid if you have seven or five or whatever, right?

[00:11:57] **Adam:** So it, it knows the formats and it knows what is considered a valid number. And even to the point where you can't put in like US with the area code of 555, it knows that that's not a valid area code. it's a very useful library and that's why we used it. The problem was that we were using a version from 2015, and We started this all started because of a different ticket.

[00:12:19] **Adam:** We got a ticket that somebody was trying to use area code 332 and was not able to. Now, being that you live in New York, you might know what 332 has been, do you?

[00:12:29] **Ben:** No idea.

[00:12:29] **Adam:** okay, so it's a, come to find out, relatively new area code, in Manhattan.

[00:12:36] **Ben:** Oh, really?

[00:12:37] **Adam:** yeah, I guess the population has been going up there enough, or new phone numbers or whatever, that they needed more, so they added a new area code.

[00:12:44] **Adam:** And so we got a ticket, somebody's like, I can't enter my, my phone number with 332, they tell me it's invalid, so we looked into it, okay, so, That, that area code was added in 2017. So, okay, that explains why it's not in our validation. And so we need to upgrade. So we upgrade from like version nine, something to like version 18, something.

[00:13:03] **Adam:** Skipped a whole bunch in here. and the, when I, when we integrated this into our code, I did write sort of a wrapper around it for like instantiating it on the page and interacting with the, the library itself. but there have been some changes over time, right? Like, so that, that first phone number input that we have, we don't necessarily capture the data the same way anymore, right?

[00:13:31] **Adam:** So back in 2015, we thought, and it seemed like the best idea at the time, you know, to capture the country code, the, the exchange, country code, area code, exchange, and,

[00:13:42] **Ben:** I didn't even know the technical terms for these things.

[00:13:45] **Adam:** Yeah, yeah, so country code is like the plus one when you're talking USA.

[00:13:47] **Ben:** That's the one I

[00:13:48] **Adam:** Area code, you know, exchange is the first three in your 10 digit number.

[00:13:54] **Adam:** I'm sorry. No, in

[00:13:55] **Ben:** The second three.

[00:13:56] **Adam:** second three in your 10 digit number. Then the last four is called your extension.

[00:14:00] **Ben:** Look, sorry, quick aside for a second. So you, I live in, in, in New York, the metropolitan, well, I used to live in the, in the metropolitan area, the greater metropolitan area. And we've been using a 10 digit telephone since, want to say since I was like 11. Like we just, there was just too many people forever.

[00:14:19] **Ben:** and I don't know how it is around the Philadelphia area. I assume it's similar. Like no one uses local phone numbers anymore.

[00:14:25] **Adam:** Yeah. I mean, I've been using, I mean, I, we haven't been in Philadelphia since, or we've been in, we moved into the Philly area in two thousand and probably eight, yeah, 2007, 2008. but even, you know, like you probably when I was 10 to 13, we started using 10 digit

[00:14:45] **Ben:** I, so I just assumed when that happened, that that was a, that was a national choice that we said as a, as a people, we have too many people, everyone's going to use a 10 digit phone number. And I didn't realize if you fly to a more rural area or you're watching a, you know, a movie that takes place somewhere like in the middle of the country, they still use local phone numbers.

[00:15:07] **Ben:** Cause there's just not that many people to necessitate everyone having the 10 digit and that, that blew my mind. Right.

[00:15:13] **Adam:** Yeah, I am very curious how that works. There's gotta be some sort of like, method to the madness of like, okay, this is what a country code should be. Like, these are the available country codes and these are the available area codes so that there's no confusion when you start punching in on, you know, old school phone, that's not a, like an iPhone, but like a, not quite a rotary, but like, you know, buttons, you know, when you start typing three, three, two, how does it know that that's an area code and not a country code?

[00:15:38] **Adam:** Like, how does it know when to start? The request for the call versus,

[00:15:43] **Ben:** Yeah.

[00:15:44] **Adam:** know, I'm not, I'm, I am or am not done typing. I don't know. Anyway, so, suffice it to say, there were some splinters of the wrapper, and, you know, data being collected in different ways, and it was just a mess, and it was a pain in the neck to fix, and I think it Knock on wood here.

[00:16:04] **Adam:** I don't know if you can hear that, knockin on my head. that, we're done. Hopefully they're all fixed now. So, and, and, the, one of the other issues was a, we, there was a security update for Lucy, not too long ago, a couple of weeks ago, and we applied that, and then we are affected by a regression that was in that release.

[00:16:24] **Adam:** which causes serialized JSON to spit out invalid JSON for certain types of CFCs. And, I mean, this one didn't affect us, but queries do. Like, if you, if you serialize a query object, it can, in certain cases, it can spit out invalid JSON, which is like a whole bunch of commas in a row, right? That's not valid JSON.

[00:16:46] **Adam:** and, yeah, like, on the one hand, Do your job and do it right, like serialized JSON is something they should have well tested. On the other hand, the reason it bit us is because we're serializing a CFC instance of a custom CFC that I wrote. You may or may not remember this, Ben, MomentCFC that I wrote like forever ago.

[00:17:07] **Adam:** like inspired by, yeah, yeah, inspired by Moment js. Uh,not a, not a direct port, but... Very heavily inspired for date manipulation and time zone,adjustments and stuff. Anyway, and we were unwise enough to at one point just go, I wonder if you can serialize these and what do you get out of it? And it gave us something useful.

[00:17:31] **Adam:** It, you know, it was originally serializing to some sort of like a structure with specific keys. I don't know if they were the private variables of the CFC or whatever. But it's not doing that anymore. Actually, it is kind of doing that, but it's throwing in a whole bunch of extra commas, which is making it invalid JSON.

[00:17:47] **Adam:** And it's like, if we had been smart enough to just say, you know, format it this way and shove it in a string and put it in this object, then it probably, when it's an object and then structure, you know, it probably would have been fine and we wouldn't have been bitten. We were lazy and we just tried to serialize a bunch of these CFCs and now this. Resiliency is hard.

[00:18:08] **Ben:** Yeah. Resiliency is hard.

[00:18:11] **Adam:** You just don't know what decisions you're making today that are going to come back in five years and make you regret not taking that career as a ice cream truck driver.

[00:18:22] **Ben:** Oh, well, I'm, I'm glad that you got through your issue. we actually had a very similar plugin, not, it didn't have all of the validation that it sounds like yours had, we just had a dropdown, which was actually a jQuery plugin, just to show you how old some of that code is. It was a jQuery plugin, and I think all it did, it used emojis for the flags.

[00:18:45] **Ben:** And then you would pick the US and it would just auto populate plus one into the text field. That was it. I don't think it did any validation. I don't think it stopped you. but I actually just recently was able to remove it from the application entirely when we stopped using Twilio because of all of that, SMS, toll, whatever we called it, you know, the fraud stuff that we were dealing with. So, I, I, I enjoyed ripping it out, but, I'm happy to hear that you kept yours in and fixed it.

[00:19:14] **Adam:** Oh yeah, I mean, at this point we can't get rid of it because they're, it would be a nightmare to try and we do have international customers, right? We've got, people giving us Canadian phone numbers and French phone numbers and stuff and we... have to be able to capture those in a way that is understandable, right?

[00:19:33] **Adam:** It makes sense enough to the code that we can pass it on to our customers. and we could just make it a plain text field, but then, you know, how do we validate that other than is empty or is not empty, right? How am I to say that putting a Q in the middle of your phone number is or is not valid? I don't know.

[00:19:51] **Adam:** I don't, that's why there's this whole... Library.

[00:19:53] **Ben:** KLJ5, they always do in the movies.

[00:19:58] **Adam:** so yeah, I mean, like it's one of those moments where like, I want to stand on the shoulders of the giants, you know, that, that Google open source library. It's awesome. It's legit. but it's one of those things where you kind of have to stay on top of it, or you're going to end up with zip code, not zip codes, area codes that, say they're invalid, but they're not.

[00:20:15] **Adam:** Mm hmm.

[00:20:16] **Ben:** feel your pain.

## [00:20:18] Human in the Loop

[00:20:18] **Ben:** But so speaking of resiliency, you, one of the things that you talked about here, which I think is very relevant is this idea that having a human in the loop. Now you talked about it in terms of pull requests and whether or not an auto merge then automatically rolls into a deployment. And it's nice to have someone in the loop.

[00:20:38] **Ben:** To, to review that logic, or I should say maybe more to review the timing to be on hand, should something go wrong. And I like that. I'm, I, I think that there's a certain level of sophistication that a company has to have, where they really have true automation. You really have to have a lot of stuff buttoned up, both in the movement of things forward, and then also the automatic rollbacks and, and reverts should a.

[00:21:09] **Ben:** Problem B detected and detected with such sufficiency that it triggers some alarm that then triggers a rollback. And I, you know, I think as an industry, sorry, I'm, I'm like already going off on a, on a rando tangent here. You know, I, I, I feel like that's really, really hard to do. And as an industry, we often, I think, get a little hand wavy about how challenging that is.

[00:21:32] **Ben:** And that's just something that we should all strive for. I don't, I don't think it is something that, that we can all feasibly strive for. I, I think at least. From what I've seen building that level of sophistication is, it's like you need really deep thinkers with a huge amount of experience and an understanding of monitoring and metrics and standard deviations and understanding spikes and windows of evaluation.

[00:22:04] **Ben:** I mean, that's not, that's not something that people just pick up randomly. Unless they're, they're forced to anyway, I, I don't know where I was going with that thought other than to say, I like having a human in the loop because things break and they break for really unexpected reasons. And in order for resiliency to be built into a system, you have to, at least on some level, be able to think through all the ways that something can break and then understand the implications of the choices about how you remediate those issues or automatically react to those issues. And that's just really, really hard. At work, I've been dealing with sending emails. Now, you've sent out a lot of emails in your life. So I'm, I'm actually very curious to, to hear maybe more about how you've dealt with some of this stuff.

## [00:22:56] Ben's Email System

[00:22:56] **Ben:** So just to paint a little bit of backstory here. We have to email, like, I'd say roughly 4 million people at work. These are 10 years worth of users. Essentially, we have to let people know about a, I'll call it a change to our terms of service. And for reasons we have to let everybody who's ever given us there are an email, let them know that this is happening.

[00:23:19] **Ben:** And, I didn't know that I deal with transactional emails. You sign up, I send you a welcome email. You leave a comment. I send a comment email. I've never dealt with, with what Postmark refers to as broadcast emails or these marketing emails. And, so the idea of having to send that volume of email, I have no prior art here in terms of my experience. I know that there are companies that are built to do just this. And every time that there is a company that will do this for you, I have to assume it's because it's actually pretty complicated and requires a lot of work. and apparently it can also sometimes be very expensive. So the company went and got some price quotes about how much is it going to cost to send 4 million emails?

[00:24:05] **Ben:** Apparently it costs enough that they did not want to pay for that. And they came to me and they said, can you build this for us? And I said, that's a bad idea. And they said, okay, but can you build it for us anyway? And I said, that's a really bad idea. I said, I don't have any experience with this. You want to do it fast.

[00:24:27] **Ben:** Like they did, you know, I said, I was, so I go to Postmark and Postmark has their best practices as well as their kind of service level agreements. And they say, you can't send more than 50, 000 emails an hour. They're like, that's just. It's a problem if you do that, we will stop you if you try to do it. And so my project manager at the time was looking and doing some number crunching and they're like, well, that's going to take us quite a while to send out 4 million emails and I'm like 50, 000 an hour.

[00:24:58] **Ben:** That would take a couple of days. Maybe like, that's not a lot of time. I don't know what you guys are talking about.

[00:25:03] **Adam:** That's 833 a minute. Yeah. I mean, we're, we're sending 3, 400 a minute when we have large sends to go.

[00:25:09] **Ben:** Yeah. So I, I, I'm, I'm, I'm just painting the backstory here. It's, it's, I'll get to a point, probably not, but I say, well, So they say, we really need you to do this because we're not going to pay for it. And these have to go out. And I said, okay, I will get you the, what I lovingly refer to as the dollar store architecture of email sending.

[00:25:28] **Ben:** I said, manage your expectations because it's not going to be great because you're getting what you're paying for, essentially. I mean, I was trying to be very clear about this. So I didn't know how to build it, honestly. And most of my experience revolves around loading up a webpage. Hitting a submit button and then performing an action and even background tasks.

[00:25:54] **Ben:** I don't have tons of experience with, and usually background tasks are more about for me doing like one thing. On a scheduled basis, like, you know, recalculating a number or checking to see if there are any overdue payments that need to be flagged, that kind of thing. It's not, how do I churn through 4 million things? So I started to build it. I figured if I could just build one piece at a time, then maybe something would come out at the end. So what I did was I built a text box that you could dump a bunch of emails into. And you hit submit and it will then loop over those and it sort of queues them up one at a time and then sends them out.

[00:26:38] **Ben:** And that was just to make sure that, if someone like double submitted the form or something crashed in between, I would have some record of something that had happened and I would try to make sure not to send the same email twice. So

[00:26:51] **Adam:** So, I'm sorry to interrupt.

[00:26:52] **Ben:** yeah, please. I'm just rambling really.

[00:26:55] **Adam:** so I, I want to, there's so many things. question the first,

[00:26:59] **Ben:** Yeah. Yeah. Yeah. Dive right in here because I'm, I, I'm

[00:27:03] **Adam:** you know, you tell me whatever backstory is relevant. However, it might be useful for me, for my listening. If you tell me, give me some idea of where we're heading by saying like, okay, this is the challenge that I'm having. This is where I'm stuck. And, and this is how I got to where I am. And so like that, I can kind of listen for those clues along the way.

[00:27:23] **Ben:** Okay. So I will, I will, I will hand wave over the journey here and just say that it became more and more complex as it went along because we kept finding challenging parts of it that needed to be dealt with. And ultimately what we ended up having to do was break this thing into like three different phases where we have to get the emails into the system and we don't even know if they're good yet.

[00:27:50] **Ben:** like they might not even be properly formatted. They might not pertain to accounts that are still active because these emails are coming from a separate system that it's coming from the data data science department. Yeah, exactly. So we don't even know if they're the right people. So we had to get into the system.

[00:28:05] **Ben:** Then those 4 million emails have to be validated against the production database, the application database. Then.

[00:28:14] **Adam:** meaning

[00:28:15] **Ben:** Like making sure that, yeah, like making sure that they're an account and, and that, there was some other criteria that we had to add because it was like, we have emails for customers, but then we have emails for people who aren't really customers, but who interact with the system by way of their customers, kind of a thing.

[00:28:32] **Ben:** it's weird. So we had to end up removing a bunch of people. And then, we ended up having to make call API calls out to this system called NeverBounce. It's a SaaS product where you basically give it an email and it says that email will probably work or that email is a, is a, a temporary email domain.

[00:28:50] **Ben:** You know, you get like a valid email for 30 minutes kind of a thing, or this is a domain that's set up to catch any email address. It won't even respond. So we had to make calls out to that. So then we get all these validated emails and then that then gets. Like queued up into another phase of all the people that need to be sent.

[00:29:08] **Ben:** And then essentially we're processing over all of those and sending them. But at the same time, we can't send more than 50, 000 an hour. So we have to have a background task that essentially only gathers a certain amount over a certain period of time and sends them out. And it's like any part of this could break for random reasons.

[00:29:29] **Ben:** You know, just to give you one example, halfway through our validation process. The Never Bounce API just started rejecting all of our calls because our API usage looked quote, unquote, suspicious.

[00:29:44] **Adam:** How dare you use the service you're paying for?

[00:29:48] **Ben:** And it's something we're paying for. That's the craziest part. Anyway, we, we get to the end here and it's, and it's truly a spectacular dollar store version of anything that resembly that resembles a resilient system. But I just. I imagine that trying to make a system like this resilient would, would require thinking about all of the places in this weird workflow that could break.

[00:30:11] **Ben:** And it's not just what could break, it's what do you do about it? You know, if, if there's a system

[00:30:16] **Adam:** it in a self recoverable state?

[00:30:18] **Ben:** well, and, and that, and how did you know, like when to retry? So, so Neverbounce just starts rejecting all of our requests. Am I just going to start trying the same email over and over and over again?

[00:30:31] **Ben:** Or does it trip and say, well, this email has given me. 403 forbidden response 15 times in a row. So I'm going to stop and then move on to the next email or, but I I'd have to, like, I didn't even know that NeverBounce would ever reject our emails. So I would have never even thought to have coded that into the system in any kind of an intelligent way, all to say so many things can go wrong.

[00:30:56] **Ben:** I don't know. I feel like I just don't even know how to build a resilience system.

[00:31:00] **Adam:** So, okay. State machines, which is a big hand wavy way to say, like, build a resilience system. yeah, I mean, we send a buttload of email and our system that sends this buttload of email is extremely complex and has a lot of stuff built into it so that like, okay, well, if, if the process were to die at this point, how is it going to recover, right?

## [00:31:26] Adam's Email System

[00:31:26] **Ben:** Can, can we just, I just want to back up for a second and I want to get a sense of you've, you've, you've been at AlumniQ for over a decade. Over what period of time would you say that you have been building and honing and perfecting this email system? Like, is this something that you built in three months and it's, and it's hard and then it's great?

[00:31:47] **Ben:** Or it's like, we've been tweaking it and, and updating it over six years?

[00:31:54] **Adam:** The short version is, I have a meeting all day tomorrow to brainstorm with two of my colleagues about reinventing this thing from the ground up because it's not good enough.

[00:32:03] **Ben:** Oh, perfect.

[00:32:05] **Adam:** Literally, my entire day tomorrow is blocked off to have this meeting. so... We implemented my design ethos of design naively.

[00:32:14] **Adam:** Version one was CFMail going into the spool folder, like literally writing a file for each email and letting the CFMailer handle it, and using SMTP. And relatively quickly, we learned that that just wasn't going to cut it on throughput. And So then we learned, okay, like SMTP as an approach is, well, a, the spooler is just slow and in the standard edition of CFML or of of Adobe ColdFusion, which we were on at the time, you're single-threaded, like that's one of the, the feature blocks between standard Edition and enterprise is, you know, you're, you, it throttles down the, the rate at which you can send email. so we pretty quickly moved over to using Mailgun, not, not sponsored, obviously, but, we've been relatively happy with them. pricing wise, they're, you know, at least as good as, if not better than, most of the other competition. Actually, we landed there after, what's the one, I think they're owned by MailChimp now, Mandrill.

[00:33:20] **Adam:** They, they used to be called Mandrill, and I think they got bought out by MailChimp. anyway, we were using them and when they got bought out by MailChimp and, and pricing information seemed to indicate we would be, giving up all four extremities in order to keep, in order to keep sending email, we started shopping around and that's when we switched to Mailgun.

[00:33:36] **Adam:** Anyway, and Mailgun supports SMTP and, HTTP API calls and the API is just significantly faster. You can send SMTP, like they give you an SMTP server and you can, you

[00:33:47] **Ben:** Yeah, that's, that's what we're still using. We use Postmark and Postmark like, like that also has an API, but then SMTP basically for backwards compatibility.

[00:33:58] **Adam:** you, especially if you ever try to exceed that, 50, 000 an hour, was it? Yeah. Because that's 833 a minute or something like that. that you're very quickly going to find out that SMTP is just not going to work for that unless you like, you know, get multi threaded, you know, like,

[00:34:17] **Ben:** Well, so if I can just quick aside, right. So that's, that's what, what I had to do. I mean, thankfully, we use Lucy and Lucy CFML and, and ColdFusion has, Adobe ColdFusion has this as well, where you can take an array and you can iterate over the array. And, and for the each or map, and you can give it some additional arguments to the iteration.

[00:34:38] **Ben:** It, you can tell it true, it's second argument, which says run this iteration in parallel threads. And then the third argument is how many threads you want it to, to use. so that's what I was doing. I was grabbing like 200 emails out of the queue and I'm calling it a queue in quotes, air quotes here on the podcast, because it's a database table.

[00:34:57] **Ben:** I, I, again, dollar store. Architecture here. So I grabbed 200 emails. I would iterate over them in parallel threads, and then I'd be sending out the, using CFMail with, and, and one of the things you can do, I know you can do this in Lucy. I don't know if Adobe ColdFusion has this, where you can say async equals false.

[00:35:18] **Ben:** And essentially it doesn't spool it. It, it sits in blocks until it does something. I don't know what the something is.

[00:35:25] **Adam:** Yeah.

[00:35:26] **Ben:** So if, if the spooling fails, it'll throw an error instead of just dying quietly in the background. But yeah, I had to start doing it in parallel threads in order to, to get it to work fast enough.

[00:35:38] **Adam:** So, let me just kind of see if I can rattle off the, the

[00:35:42] **Ben:** Yeah. We're just going to meander here.

[00:35:44] **Adam:** yeah, yeah. So the, the primary problems that we had to overcome, to be able to send even at the meager 3, 400 a minute that we can do. Well, now I say that we self limit to 3, 400 a minute because if we don't, then our, then Mailgun's going to get mad at us.

[00:36:01] **Adam:** Like that's what we're contractually allowed to send. We are, we, we finally have the ability. To do that last mile much faster than 3, 400 a minute. Like in theory, we could go maybe three or four or five times faster than that. by removing the governor that, that limits us there and then allowing more parallelization.

[00:36:23] **Adam:** That's a big word. more, more Lambda threads running in. concurrently to, to grab a batch of emails and send them. but I, I specifically called it the last mile there because it's everything up to that last mile that is an absolute bear for us. And the, the biggest problem, so our system, and, and this is one of the things that I was kind of like listening for.

[00:36:43] **Adam:** So it doesn't sound like you need to do much in terms of culling the list that you get. You get a list of email addresses, You're going to send them to NeverBounce and find out if, if you should even bother trying and then you're going to compare them against your user table or whatever and say, okay, we should or shouldn't.

[00:37:03] **Adam:** Send to them based on whether or not they're a user. You don't have to worry about unsubscribes. You don't have to worry about, you know, are they registered for this event? Like we've got probably 50 different criteria that

[00:37:14] **Ben:** right, right, right.

[00:37:16] **Adam:** and so the process of going, here's a pile of email addresses from that to here are the email addresses that we actually want to send to in this occasion.

[00:37:28] **Adam:** It takes a ridiculous amount of time for us. Now, granted, that's only for the couple of customers that we have that have a ton of data in the database. So maybe that's part of what's choking it. It's just trying to, you know, you're, you're trying to work on 300, 000 rows in a table that has 3 million rows.

[00:37:46] **Adam:** These doesn't, these don't sound like the numbers that should be choking MySQL to me, but maybe that's, you know, maybe we've reached problem, territory with that. and, so whittling that list down tends to be a problem for us. For these, like, if you, if we start out with a list of 300 to 400, 000 people, and then we're expecting that to be somewhere in the neighborhood of 250 to 300, 000 total, at the end, there's a lot of work that goes into removing people from that list, and deduplicating on various things.

[00:38:17] **Adam:** Anyway, that part is what we struggle with the most. And then once we get there. We have a fairly resilient system to, build up the queue, render the emails that we're going to send, have them ready to go, some self healing stuff if parts fall over during that process. This is all, like, from that point on, from the, from the point of the finalized list of email addresses that we need to send to, that's an inflection point in the architecture for us.

[00:38:45] **Adam:** So, up to that point, it's all... In the CFML application, just doing stuff. And at that point we write all those email addresses to a table. and then we make a SNS call to trigger a Lambda that will go through and start the, the cloud, like a high resiliency, very complicated system. Right? We, we write files to SN, to S3 for each email we're going to be sending.

[00:39:13] **Adam:** And that, that file has the rendered subject. a text only version and an HTML version of the message. And when I

[00:39:21] **Ben:** good on you for having a text only version. That's like, in and of itself, a level of complexity.

[00:39:26] **Adam:** yeah. And when I say rendered, I mean, any of those three bodies of text could have tokens in them that are, are unique to the person, receiving the message or other things. and so they, they, they go from token to rendered. So we write a, we write files to S3, which then triggers, and that's the, the raw unrendered file that triggers a lambda for per file to render that file.

[00:39:53] **Adam:** And then we encode information about, okay, this is for this customer in this environment using this message ID, and this is the list member ID, right? So like I'm sending to the all alumni list. And there's got, let's just say it's got like a GUID as the list member ID, right, the primary key on that column, on that table.

[00:40:16] **Adam:** all of those bits of data get encoded in the file name, just as like, okay, this, then underscore, then this, then underscore, then this, then underscore, right? dot, dot txt or whatever. so then we parse the file name, tells us like what database we need to connect to, you know, where to go find information about who we're rendering for, et cetera, et cetera.

[00:40:35] **Adam:** The text file has all the contents of the, the, the, what you need to start with in order to render it. We look up the data,

[00:40:43] **Ben:** You doing this from the Lambda function?

[00:40:45] **Adam:** Yeah, so this is a, separate life, right? The initial lambda, just like, here's the email addresses, write the files, right? Do that as fast as possible, right?

[00:40:53] **Adam:** 300, 000 files to S3. Then we

[00:40:55] **Ben:** So, so sorry. Just, okay, keep going. No, keep going. Keep going.

[00:40:58] **Adam:** Okay. So then we have a trigger, right? When we write files to a specific bucket or location in a bucket on S3, that triggers lambda. a separate lambda function. And that function gets an event that has, okay, here's the filename that you need to work with. So it goes and reads that file from S3, based on the filename, knows where to connect to the database and what data to get, pulls that data from the database, in memory, updates the contents of that file, and then writes it out to a separate location in a separate S3 bucket and deletes the original.

[00:41:29] **Adam:** Right, so we've gone from sort of an empty husk, or we call it a stub. Message to a rendered message. And then in the process of each of these steps, right? Like the, the first one that is just creating files, with the, the same static unrendered message content. in addition to doing that, it's also by way of Redis, updating the database to say, okay, I've written the file for these.

[00:41:54] **Adam:** these email addresses, these list member records from the queue, right? And so you can't, we were, we got to a point where we were pounding the table, trying to update, you know, one row at a time or, or 50 at a time, that we were writing. So what we did instead was now we write those to a, a set in Redis.

[00:42:12] **Adam:** And then we have a job that runs once a minute, looks at that set and says, okay, give me everything in the set. And I'm just going to do a single update to the database. If where ID is in these IDs. SetStatus equal, you know, StubWritten or whatever, and then delete those from the set on Redis. And Redis is really good at that.

[00:42:30] **Adam:** It's nice and fast, and you're doing a single

[00:42:32] **Ben:** Now, Redis is not resilient by default, so if Redis crashes you're, that's gone. But,

[00:42:39] **Adam:** Correct. However,

[00:42:40] **Ben:** you can set it to, to have right. To disc, I believe.

[00:42:44] **Adam:** you can, but for us this process is idempotent,

[00:42:47] **Ben:** Gotcha. So you could try it again.

[00:42:48] **Adam:** rerun it and it's no harm, no foul, because if it sees in the database that the file was written, then it skips it. If it doesn't... It writes it anyway. so yeah, at, at each step of the, of along the way you have to leave breadcrumbs so that you can kind of resume from where you left off instead of starting from scratch, because then you're gonna waste a lot of time and resources when things do inevitably fall over.

[00:43:10] **Adam:** So we've got Lambdas running in concurrent,concurrently, that's the word I was looking for, to, render all these things and write them out to a new S3 bucket, and update the database again to say, okay, now render is complete. Again, via a Redis like set, and a and a separate background job and delete the original file.

[00:43:27] **Adam:** and, and eventually at the end of this like train of things that are happening, you've got a bunch of files sitting on S3, a bunch of database records that know, okay, I represent a file that exists on S3 somewhere. and here's an email address that I'm gonna send to. And then, it's all just sitting there.

[00:43:42] **Adam:** And we try, we, we begin all of that about four hours prior to the desired send time. if, if that much time exists, right? Sometimes they're like, I need to send to these 300, 000 people now. And so you're like, okay, well, I'll do my best. But, you know, if they plan it in advance, which we very much encourage them to do, then we try to, to get ahead of the game there.

[00:44:02] **Adam:** but then, you know, the, the clock strikes noon or whatever, right? And they need to send this email. And so we have a separate. We have like a container that's running in the cloud and it's just, you know, on a schedule. I think it's like every 30 seconds or something like that. It's just saying, is there anything waiting to be sent at now or prior, right?

[00:44:22] **Adam:** Anything that's overdue for sending, which might, it might only be overdue by a millisecond, but it's overdue. and if it, if there is, then it splits it up into batches, triggers more Lambda functions to run, passes off those batches to Lambda. And those lambda functions, send the email to Mailgun over the API and,

[00:44:41] **Ben:** That's, that's the system that does the governing to say like,

[00:44:45] **Adam:** the, the one that's doing the batching there, yes.

[00:44:47] **Adam:** Yeah, so, that's, that one gets really complicated, you know. As the Lambdas are running, because a Lambda can only, I think now it's like 15 minutes max, but when we originally wrote this system, the limit was something like five minutes. And so we, we do small batches. I think we're doing batches of like 6, 000, maybe it's 600, emails at a time.

[00:45:10] **Adam:** And so a Lambda gets handed a batch and it says, go send these, as fast as you can, and then check in with me. And there's a web socket between the Lambda and the Lambda. We call it the conductor, right? It's like standing in front of the orchestra, conducting a bunch of these things. And at that check in, the conductor is going, Okay, well, I know I have five lambdas running.

[00:45:31] **Adam:** And I can tell based on what they're telling me that during the last calendar minute, right? Between the time that the clock says 1034 and 1035, we sent 3, 200 emails. And I know the limit is 3, 400 based on my configuration. And I, I'm forgetting details, it's been a long time. It looks at

[00:45:51] **Ben:** There's, there's a lot of details here.

[00:45:53] **Adam:** the standard deviation of the time to send a batch, and it says, A, do I have time to send another batch before this lambda is going to be shut down?

[00:46:04] **Adam:** Right, like we, we tell them when they get close enough to the forced shutdown time, we just say, okay, go kill yourself and we'll start up a new one. And so we, we use math to do, do, is there enough time for this lambda to, to send more before it's gonna be killed anyway? If not, then just die. even if there is time in the, in the Lambda's lifetime and assuming there's more work to do, do we have more headroom in this calendar minute?

[00:46:31] **Adam:** Right? and if not, then okay, then just. Shut yourself down. Actually, there's a, there is a sleep. Like, it'll say, okay, if there's enough time, if you're early enough in the life cycle, sleep for 15 seconds and come back.

[00:46:42] **Ben:** Now what's the, what's the benefit of doing that as opposed to just having the conductor spin up another Lambda when it needs to, is it just the, the cold start time,

[00:46:54] **Adam:** Cold start is not really a concern here because they're returning through those,

[00:46:58] **Ben:** It's happening in the

[00:46:58] **Adam:** so fast. So there's, there's gonna be a hot one available. but it's a good question. I, and I think that there might, I might not be including all the thought that goes into it. It might be like, are we, are we close enough to the end of the calendar minute?

[00:47:14] **Adam:** Yeah, it's worth waiting versus, you know, if we, if we already hit the calendar minute limit and there's still 45 seconds left this minute, then just shut down. Right.

[00:47:25] **Ben:** just, it's just bonkers.

## [00:47:26] The Diminishing Returns of Resiliency

[00:47:26] **Ben:** I mean, just to think about all this stuff that can go wrong. I mean, my system is complicated for me. And your system sounds much more complicated, but also, I mean, also very clean in, in how you sort of have these pieces sectioned off and quarantined and,

[00:47:44] **Adam:** Hold on. This is 10 years of,

[00:47:46] **Ben:** yeah, yeah. Right. So, you know, just as a comparison there in timelines.

[00:47:50] **Ben:** When they came and said, Hey, can we build this? I said, I've never built anything like this. I think it's a terrible idea. It might take me three months to build. And they said, can you do it in less than a month? I said, I said, we can have a discussion about which parts of this you don't think are essential.

[00:48:09] **Ben:** We can cut those out. And then at what point they were like, is there any way we can get it down to a week? So it was so nuts, but you know, I'm, I'm, I'm.

[00:48:21] **Adam:** Pay for a service.

[00:48:23] **Ben:** I know, right? So I'm looking at your system and I mean, there's just so many moving parts. I mean, there's so many moving parts in my system and it's significantly less complicated, or I should say it's significantly less robust. That's for sure. You know, Mailgun could turn around and just say no for whatever reason, right?

[00:48:41] **Ben:** They could say, we're having a degraded experience. We can't be sending emails or we've detected suspicious activities. So we've suspended your account. So that could just stop working or for whatever reason, like. Lambdas might stop working. I don't know. Redis could go down. I don't know. There could be some sort of deadlock in the database that's preventing database queries from working or they're timing out.

[00:49:05] **Ben:** S3, I didn't know that this can happen, but you can send so much traffic to S3, or at least you can increase traffic so quickly that it will start giving you these responses that are like, I'm spinning up. So, S3 can do like an ungodly amount of traffic, but it's dynamic. It will apparently, I think per bucket I was reading about this, it'll dynamically spin up what it needs to under the hood in order to handle basically all the traffic that you can throw at it, but it'll give you errors occasionally saying.

[00:49:38] **Ben:** We're expanding to accommodate this. Please try again. So like, that can fail, you know, I don't know your file names that you're generating with the UUIDs and the various indicators, like that's probably, probably pretty locked down. But you never know if, if like any of that contains user generated, generated information.

[00:49:57] **Ben:** You know, suddenly someone puts a Russian character in that you didn't expect. And now like something doesn't encode properly on disk. It's

[00:50:04] **Adam:** talked about it. We talked about emojis. That was a huge thing

[00:50:08] **Ben:** everything can go wrong. And, and, and I just trying to account for all of that. It can only be a journey of failing over and over and over again. And then at each one of those failures, trying to figure out how to best fix it in the future. I don't think you can plan for this stuff. It's, it's. It's like when they talk about the, the nines of availability, right? Four nines of availability, five nines of availability and how each one of those nines is significantly more expensive than the one before it. And at what point does the cost outweigh the stability that it offers?

[00:50:47] **Adam:** Yeah. I don't, I don't remember where I first heard that, but that's a really good, you know,

[00:50:51] **Ben:** right. So like you can build a resilient system, but at some point, like it's going to be so expensive to build it. To be truly resilient.

[00:51:00] **Adam:** and you know, to your point, you know, like I said, we're, we're 10 years into evolving this system, probably longer than that. And I said, I have this meeting tomorrow to reimagine, you know, like take all the lessons we've learned, throw all of the current technology, technology decisions aside.

[00:51:19] **Adam:** We're starting from scratch in theory, on a whiteboard. how would we do this if we were starting over right now? What are the things that we would do differently? Like, the technology has changed so much. Like, when we originally wrote this, MySQL didn't have support for common table expressions, CTEs.

[00:51:35] **Adam:** And now we do,

[00:51:35] **Ben:** right. Yeah. In

[00:51:36] **Adam:** right? So that

[00:51:37] **Ben:** something.

[00:51:38] **Adam:** potentially could have a major impact on, on query performance and like decisions to do one way versus another. Mailgun, I mentioned, is our email provider. They actually provide... They have a feature where they do that sort of like last mile piece for you. And I believe it's the same price.

[00:51:57] **Adam:** So,

[00:51:58] **Ben:** say the last mile, you're talking about the governing, like the rate limiting stuff.

[00:52:02] **Adam:** me say, let me tell you, and there might be, they may have like maximum,chunk size or whatever, like, maximum number of email addresses per request or something like that, but they do have a way, and I don't have the details, sorry, we haven't gone down this road yet, but, they do have a way where you can say, here are some email addresses, And per email address, here's a token and a value, and a token and a value, and a token value.

[00:52:27] **Adam:** When you find that token in the content, replace it with the value,

[00:52:30] **Ben:** Okay.

[00:52:31] **Adam:** And then here's the raw template that applies to all of the email addresses. So, like, a lot of what I just talked about, that whole render and prepare system, they just do that for

[00:52:42] **Ben:** Right. You would have like a template. This is like what Microsoft for years, they call this a mail merge where you'd have some sort of a template and then you just give it a file and it merges it together,

[00:52:53] **Adam:** yeah, yeah, it's pretty similar.

[00:52:54] **Ben:** something like that.

[00:52:56] **Adam:** Yeah, so, I mean, it is very much what I talked about, like, you know, so, we. Part of the system that it would be replacing for us is, we have figured out the list of email addresses that need to be sent to. From that, we can look up the data for each relevant token in the unrendered message content.

[00:53:17] **Adam:** And then we take that unrendered message content, we render it, and it's ready to send. Mailgun has an API where you could say, Here's an un, like you, you say, here's the unrendered message content and here are the recipients and the recipients is like an array of objects and the, you know, email address, first name is Bob, last name is Jones and, you know, employer is IBM or whatever, right?

[00:53:39] **Adam:** And the, when the first name, last name and employer tokens are found in the body. As it's trying to turn through these and send them, it replaces it for you. So that's all that, that whole like render piece is done. And the, as far as I know, they're much faster about it than we are able to be on our end in terms of like going from, lists of email addresses to rendered and ready to send, I don't know what their actual throughput speed is, but it sounds like it's a hell of a lot faster than what we're able to do.

[00:54:12] **Adam:** And so. part of what we, what is limiting us to 3, 400 a minute is that's the like API request limit, and we are sending one email per API request. And that same API request could send a whole batch. Of these, using this mechanism I'm telling you

[00:54:29] **Ben:** Yo, thank goodness in my exploration. And maybe this is because we're using SMTP. That it, it, it did not appear that there was a limit to how many SMTP

[00:54:41] **Adam:** Just the, the limitation of SMTP

[00:54:43] **Ben:** Yeah, yeah, yeah. But there was certainly, I think, a limit for the number of API calls we could have made. 'cause I had looked at, so, so Postmark does have a batch mail endpoint. Again, it was just, to some degree, because I knew that I couldn't send out more than a certain amount per hour. I was in some sense leaning on the latency of the approach to govern. My, so, so how I ended up dealing with the, the up to 50, 000 an hour and no more was I had a scheduled task, a ColdFusion scheduled task that runs in the background.

[00:55:19] **Ben:** It runs every five minutes and every five minutes it gets the next, I think like five or 6, 000 emails off the queue. And just by fact that it runs every five minutes and it gets a finite number of things. If it can send all of those in five minutes and it won't try it again for another five minutes, I'll know that within the hour I won't exceed that 50,000.

[00:55:42] **Ben:** And if it's too slow, then like, whatever, I'm, I'm not gonna exceed it. You know, that that's more of a business problem, that it is an API problem at that point. And, so yeah. So I was a little bit leaning on the fact that it wasn't a well architected system to control the throughput.

[00:55:58] **Adam:** Natural, uh, throttling.

[00:56:00] **Ben:** right. . It's like, uh

[00:56:02] **Adam:** So, maybe you already thought about this or whatever. I, I do have a lesson that is, particularly well crystallized in my memory about how to generate batches performantly against the database. So, I'll, let me offer this advice to you or anybody else who might be listening and trying to, to do something like this.

[00:56:19] **Adam:** So, You know, potentially you have a table with a crap load of records in it and you only want to select a subset of them and only the ones that, have not been sent and you want to mark them as, like, now belonging to a batch so that the next time the function runs it doesn't give you the same ones over again, right?

[00:56:35] **Adam:** So, generally, my approach is predetermine whatever your batch ID is going to be like. So, let's just say it's a GUID. So, you have a variable containing a GUID, and you're set, you basically, you run an update. You say, okay, update the table, set the batch ID to this one, where the batch ID is currently blank, with a limit of whatever, you know, of...

[00:56:58] **Adam:** However many we want to do for this job, a thousand or whatever. and then follow that up with another query that says, okay, now give me everything that's in that batch. So you do two queries, both relatively quick,

[00:57:09] **Ben:** Sure,

[00:57:09] **Adam:** that, that, that batch ID column has an index on it. And, and because of the limit on the update, that one happened pretty quick.

[00:57:16] **Adam:** It's just the first however many thousand rows that I could find that didn't have,

[00:57:21] **Ben:** this is what you're saying. So, I always knew you could do a limit on a select. I did not know that you could do limits on updates and deletes until I was reading up on this very problem that how do you essentially chunk something?

[00:57:36] **Adam:** mm hmm.

[00:57:36] **Ben:** essentially I was reading articles about how do you use a database?

[00:57:40] **Ben:** Like it's a message queue. And that was kind of what it was. It's like, here's all the things I'm going to claim for my worker. And then my worker will go back and pull all those out of the database. Yeah, it's pretty cool. But you know, it's just talking about resiliency again. So one of the things I had a queue table and then I have a, I had a delivery table.

[00:57:59] **Ben:** So these are two different tables in the, in the MySQL database. And if you think about the order of operations, I pull an email address out of the queue table. I send the email and then I have to move that record from the queue table into the delivery table. So I have to add a delivery record and I have to delete a queue record and it's.

[00:58:20] **Ben:** On the topic of resiliency, it's like, which order, which table should be affected first? You know, if I insert into the delivery table and then the system crashes before I can delete it from the. Queue table. Then the next time it runs, the queue will be, you know, the email will be queued up again and sent.

[00:58:39] **Ben:** So that user can get two emails, but I will always have a record of it having taken place. If the order of operations was first, I delete it from the queue and then I insert it into the delivery, but it dies in between that the user will only get one email because it's been removed from the queue, but I have no record that this ever happened.

[00:58:59] **Ben:** And I'm like, which one of those? Is worse. And, and that's not, it's not a clear cut problem.

[00:59:05] **Adam:** And in both of those cases, you have to account for, I don't know if it actually did send or not. Like the process died. The process died, but did it die before or after the send took place?

[00:59:18] **Ben:** Yeah. So it's, I mean, and that's, and that's a one. Minor interaction in a overall flow that is itself very complicated and, and could break at any moment. And that's just,

[00:59:31] **Adam:** Yeah. And so my, my advice in that case is state machine. Yeah. That's a, that there's a state for somewhere between needs to send and sent. And if it, if it stays in that state for too long, or if the process dies and you have stuff in that state, then you need to go check on the things that are in that state.

[00:59:48] **Adam:** And you have to have, either there's an API where you can say, has this email been sent? Or you have a human. Go look.

[00:59:58] **Ben:** well, that's the nice thing too, is that as you're building this stuff up, I mean, I don't know how Mailgun works, but I assume it's, I assume there's some sort of a dashboard where you can log in and actually look at some record of emails that have been sent.

[01:00:09] **Adam:** Yes.

[01:00:12] **Ben:** So that's one of the nice things is that as you're building systems like this, there's going to be bugs.

[01:00:16] **Ben:** Things are just going to break for unknown reasons. You're going to be figuring it out as you go. And sometimes you do need that human reconciliation. You're like, something went wrong in this batch. I'm not quite sure what, I'm not quite sure how many of these things went out successfully, and I literally have to log into my SMTP SaaS product and look to see what's there and maybe try to reconcile the two somehow.

[01:00:38] **Adam:** Have you seen the pretty famous Tom Scott video about time zones? Which we'll of course have to link in the show notes

[01:00:43] **Ben:** No, I don't,

[01:00:45] **Adam:** No, so it just goes on this like rant about a hypothetical, it's like why developers hate working on time zones or working with time zones. And it goes on this, you know, like, okay, so you build a product and it's got some sort of time thing in it.

[01:00:57] **Adam:** And then you're just like one request after another, after another to deal with certain time zones or certain features because of time thing. And it just, after this like five minute rant. He's like, and that is why nobody ever wants to work with time zones. I will make sure that we include the link for that in the show notes and I bring it up because I think that second place after worst possible thing to have to work on.

[01:01:23] **Adam:** I'm sorry, second place in the category of worst possible thing to have to work on after time zones is sending email.

[01:01:29] **Ben:** yo

[01:01:29] **Adam:** Especially bulk sending,

## [01:01:31] Microservices

[01:01:31] **Ben:** I'll tell you, so as an industry, this was, when did we as an industry start to fall in love with microservices? That was like six years ago. Five years

[01:01:42] **Adam:** really good question.

[01:01:43] **Ben:** I think it was

[01:01:44] **Adam:** feels like it may be before that, but it depends on your definition of like, fall in love with

[01:01:50] **Ben:** it felt like the industry hitting, hit a tipping point where suddenly everybody was talking about microservices. And then with the advent or the addition of microservices into our control flows, suddenly we're like, Oh, resiliency is a really hard problem. We've taken these monolithic applications and we've put all these network calls in between them.

[01:02:09] **Ben:** And that's a real problem. And then. Circuit breakers, the concept of circuit breakers became like a really hot topic. And this was one of those things where. just again, resiliency is so hard. I, I played around with circuit breakers because it on its face sounded like a good idea. I just couldn't get it to work right.

[01:02:31] **Ben:** And I never really understood the philosophical approach that would have made it work effectively. And it's like, suddenly I just have applications that are now breaking in different ways. Like nothing became more resilient. And this is not a knock on circuit breakers. this is a knock on my ability to get them to work.

[01:02:48] **Ben:** Well, it's like, at least when the database locks up and the whole system dies, like I get it, like, I understand why it happened, but when you have a circuit breaker, it's like something just stops working. You're like, I don't know why the circuit breaker opened. You're like, well, did you have the proper metrics being emitted from it?

[01:03:05] **Ben:** So you could see why it opened and like logging and just complexity upon complexity. And now things don't work.

[01:03:13] **Adam:** hmm. You've been mentioning this enough, do you want to maybe give a basic definition of what a circuit breaker is?

[01:03:18] **Ben:** Oh, sure. So a circuit breaker is essentially a, a piece of control flow. That is intended to, let's say, fail fast. So if you think about a series of systems that one calls another and one, then that one calls the next one, and if the upstream one. Stops working. So let's, let's say your database stops working and then the, API system that was reading from that database, it will stop working.

[01:03:47] **Ben:** And then the clients that were calling that API system, those stopped working. And then the browsers that were making requests to those clients, all of those requests stopped filling. So you get this cascading failures. And then if the, one of the systems comes back online, then all the things that Originally calling it, they start calling it again.

[01:04:07] **Ben:** And then you get this stampeding herd problem and the sudden influx of volume ends up breaking the system over again. So there's all these problems with having these interconnected systems. So you, you can put a circuit breaker in a bunch of these different pathways that will. Be more, graceful.

[01:04:25] **Ben:** Graceful is probably not the right word. It'll handle that though, those failure modes more effectively so that it will protect both the upstream and the downstream systems, it'll protect the upstream systems from things like the stampeding herd problem, and then it'll protect the downstream systems by failing fast.

[01:04:43] **Ben:** So if, if, if you've say made a hundred requests to the database. And the last hundred of them have failed. The circuit breaker will open up, meaning like a, like the circuit breaker in your house, it'll open up, the electricity will stop flowing, and then every subsequent call that you make will immediately fail without even touching the database because it knows it's not in a healthy state.

[01:05:03] **Adam:** Makes me think of like, sometimes I'll go to GitHub and I'll get a response, you know, I'm just trying to like open up my repository page or whatever, and I'll get a response that's like, you know, 900 milliseconds or something like that, some relatively short amount of time, and it's like, oh, sorry, we're failing the request timed out, and I'm like, what?

[01:05:20] **Adam:** That is your threshold? And I think that that's what's going on there, right? They're saying like, we've detected a pattern of something. So we are putting on the brakes. We're not letting as much traffic through. To even try against the database or whatever in this case. Yeah,

[01:05:34] **Ben:** yeah. Yeah, absolutely. I've, I've gotten the, they have like a rocking unicorn or something that's like, oh no,

[01:05:40] **Adam:** Oh, it has a name, I forget what it is. Anyway.

[01:05:44] **Ben:** but yeah, anyway, all to say that this is really hard stuff. I, I, you know, I'm a fairly experienced programmer. I've built some pretty large systems. I don't want to say that I've built some pretty robust systems because that could probably be called into question. I feel like you need people who are dedicated to thinking about these types of problems because there are people who just need to get work done.

[01:06:08] **Ben:** You have customers calling, they're having issues. You can't necessarily sit around all day thinking about the best way to attack resiliency problems. There needs to be. Specialized teams that I think help you architect this. It's not, it's not the, it's not the purview of the day to day engineer, the product engineer, who's.

[01:06:28] **Ben:** Who's just trying to get work done.

[01:06:31] **Adam:** I feel like I might have mentioned it long ago on the show, but, and I'm certainly not advocating for this as a healthy, good way to do things, but it's the truth of what happened. Early on when we were switching from the like CFMail with the spooler, To something we were trying to do, you know, complex, cloud, multi threaded, like all of this.

[01:06:54] **Adam:** When we were trying to actually try to do this well, we, I say we, myself, Steve, and the one other person that belonged to the company at the time, that was working for the company at the time, we got a couple of hotel rooms and we said, see you to the family for an entire weekend. And we just went, it was like a hotel in town, you know, we were just all local.

[01:07:14] **Adam:** We went to the hotel and we worked like 20 hours a day and we would just work and eat and then work and eat and work and eat, and then we would sleep for a few hours and get up and work and eat and work and eat and work and eat for like three days straight, and we learned a lot of lessons about like, you know, how you can screw yourself with, Sending too many requests, to Lambda.

[01:07:35] **Adam:** Oh, wait, there's a whole thing there. Anyway, we're already pretty late in the show here. So why don't we, why don't we wrap

[01:07:40] **Ben:** Yeah, yeah, yeah. Let's wrap it up.

## [01:07:42] Patreon

[01:07:42] **Adam:** Okay, cool. well then this episode of Working Code was brought to you by Adam's ice cream truck. I need you to patronize it so I don't have to keep doing this crap anymore. Come on and get some ice cream. and listeners like you, If you're enjoying the show and you want to make sure that we can keep putting more of stuff like this, more of this content out into the universe, then you should consider supporting us on Patreon.

[01:08:02] **Adam:** Our patrons cover our recording and editing costs, and we could not do this every week without them. Special thanks to our top patrons, Monty and Giancarlo.

## [01:08:11] Thanks For Listening

[01:08:11] **Adam:** I think, Ben, Ben, you don't look sleepy yet, so, we're gonna do an after show. and as we mentioned, we're going to talk about your book. I have questions about, what's going on at Invision.

[01:08:20] **Adam:** You mentioned like, we and, and, and company stuff. So I'm, you know, we're going to dig into that a little bit more. and then just another thing that, popped into my head. We'll see if, if time allows. I mean, this is already like a list that could go into a whole new show, but we'll try to do an abbreviated version.

[01:08:34] **Adam:** I've had thoughts about, and opinions about testing as part of deploys. So, That's what we're going to try to get through on the after show. And if you want to hear us attempt to get through that list, then you can go to patreon.com/workingcodepod become a patron of the show. that's it.

[01:08:49] **Adam:** Yeah, yeah, that's going to do it for us this week. We'll catch you next week. And until then,

[01:08:52] **Ben:** Remember folks, your heart matters.
