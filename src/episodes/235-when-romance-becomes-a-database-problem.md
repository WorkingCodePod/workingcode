---
title: "235: When Romance Becomes a Database Problem with Sean Corfield"
description: "How do you keep millions of people safe on 40 different dating sites while simultaneously figuring out what drives them to buy memberships? Sean Corfield joins to discuss observing user behavior at scale—from detecting devastating romance scams to managing 700GB databases."
date: 2025-10-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/235-when-romance-becomes-a-database-problem-with/id1544142288?i=1000733145889"></iframe>

How do you keep millions of people safe on 40 different dating sites while simultaneously figuring out what drives them to buy memberships? Sean Corfield joins Adam and Ben to discuss the surprisingly complex engineering and business challenges of observing user behavior at massive scale. 

Sean runs us through fraud detection and prevention (including devastating "pig butchering" romance scams), database architecture at enormous scale (700GB databases with 250M+ row tables), custom domain-specific languages for writing business rules without touching SQL, real-time scoring systems with hundreds of rules, zero-downtime deployments and schema migrations, and the constant cat-and-mouse game between scammers and detection systems.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/235-when-romance-becomes-a-database-problem.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Sean:** So that's why under the hood, it's all one big database, because technically if everyone opts in, you can see all of the members.

[00:00:08] **Adam:** So you've got a table with hundreds of millions of rows in it, and you want to, you wanna search over that table for some behavior that may or may not have happened for a variety or for all users or whatever. But how do you do that in a performant way, right?

## [00:00:41] Intro

[00:00:42] **Adam:** and on today's show we're gonna talk about observing user behavior. Tim is still on vacation. Carol couldn't make it tonight, but subbing in for our two usual friends. We have, Mr. Sean Corfield, friend of the show. Welcome back, Sean

[00:00:54] **Sean:** Hello, folks.

[00:00:55] **Adam:** and myself, and Mr. Ben Del, as usual. Hey, Ben.

[00:01:00] **Ben:** Howdy, Sean, great to have you here. when I said to Adam, Hey, we should get Sean on to talk about this stuff. I said, it'll probably be hard to coordinate though 'cause I'm pretty sure he lives in the uk. And Adam was like, what are you talking about? I was like, yeah, it's gonna be hard to line up the hours.

[00:01:16] **Ben:** And he was like, he lives in the us.

[00:01:19] **Adam:** Yeah, he did just move, but not, not

[00:01:22] **Sean:** Yeah,

[00:01:22] **Sean:** I

[00:01:23] **Adam:** to or from the uk.

[00:01:24] **Sean:** I, I, I've been in the US for 26 years.

[00:01:27] **Ben:** I, know, I, I, you know, once he said it, I was like, yeah, where did I get that from? I know you worked, you were in California for a while, right? Didn't you run the

[00:01:35] **Sean:** Yeah. Just right up. Yeah. Ran, the Bay Area called Fusion User Group for years. and worked at Macromedia and Adobe and

[00:01:46] **Sean:** So,

[00:01:46] **Sean:** yeah. And you would've run into me at conferences all over the us

[00:01:50] **Ben:** so, you know, as I'm getting older, the facts, the facts are getting more fluid.

[00:01:56] **Adam:** You know, you know, Ben, they say the memory is the second thing to go.Uh, he is not gonna fall for it. Alright, well, but first as usual, let's start with our triumphs and fails.

## [00:02:06] Adam's Triumph

[00:02:06] **Adam:** I'm gonna go with triumph today. Quick easy one. I got to write some spelt code today and that just makes me happy.

[00:02:11] **Sean:** some what code?

[00:02:12] **Adam:** Spelt

[00:02:14] **Sean:** Oh, right. That JS library thing.

[00:02:17] **Adam:** yes. My favorite.

[00:02:19] **Ben:** Is, is spelt five, like an official release thing or, okay. I didn't know if

[00:02:24] **Adam:** Spell five has been out for a while, maybe even a year at this point. I'm not entirely sure. and they're, they've got some other interesting stuff coming down the pipe. I think we're gonna be seeing another release here, not imminently, but soon.

[00:02:37] **Ben:** I was, watching the documentary that just got made about Evan U and the V team and, and Rich Harris who created spelt. He's, he's featured in it and I just love listening to him talk. He, he's very measured and feels like he's very thoughtful in all of his responses. And I, I dunno, I just enjoy it.

[00:02:58] **Adam:** That happens when they give you multiple takes and you get to like, really think about, in advance about what you wanna say. But he is, he is a very, well-spoken presenter, like his conference talks. I always love them. They're really good. So, like I said, quick, easy one for me. That's what I got going on.

[00:03:14] **Adam:** How about you, Ben?

## [00:03:15] Ben's Triumph

[00:03:15] **Ben:** I will also go with a mostly quick, easy triumph, which is that over the weekend the misses was in the city. So I had the house to myself, and I took that as an opportunity to move off of my host tech VPS onto my ex by VPS. and it, it took, I don't know, probably took like eight or nine hours to get it all done because it's just tedious moving databases around and, and like FTPing files down to my server and then FTPing, then back up to the new VPS.

[00:03:46] **Ben:** and you know, I'm sure there's much smarter ways to do it, but I was also learning about IISA little bit, it's all managed hosting. As, as you know, I'll complain to Sean and Adam Cameron very often. I just, I'm not a server guy, so a lot of it is me tripping over the, why did all of my requests just stop working?

[00:04:03] **Ben:** Oh, apparently you can't block Jakarta, even though that's what the server lockdown guide said to do, because I don't know something about web service connectors and I don't even know what that does. So, I got it done and I was pretty excited about it. And, I was moving from a coal vision 2021 server to a 2025 server.

[00:04:22] **Ben:** And there's a bunch of stuff, not a bunch. There are some things that I've used historically that are not compatible with 2025 and, this is like the other half of my triumph here, was that I was able to reg X fix all of those things mostly, removing H TM L edit or no? Yeah. What was, well, the old ones, like H TM L edit format,

[00:04:42] **Adam:** yeah, for like in code for HTML type

[00:04:44] **Ben:** yeah.

[00:04:45] **Ben:** Completely dropped. Now it's in code for HTML. Also, I don't quite understand this one. I'm sure there's reasons, but the CF header tag has dropped support for status text.

[00:04:57] **Adam:** Oh, really?

[00:04:58] **Ben:** yeah. It used to be you could pass in status code and status text, which I've been doing forever. And now the page won't even compile, template won't compile if you have status text in the, in one of the calls.

[00:05:09] **Adam:** Is this a C, F or Lucy?

[00:05:11] **Ben:** a CF 2025. And, anyway, I just, RegX to me feels like a gift that keeps on giving. I learned it when I was in my mid twenties and I swear it comes up every single day in my work. And,I just love it. And, you know, in the age of ai, and I know that you don't want me to mention ai, but people always talk about, oh, what's so great about AI is that it can do your regexes for you.

[00:05:37] **Ben:** And I'm always like, no, learn your regexes. It's so good.

[00:05:43] **Adam:** Don't take away the fun part. Let make, make AI read the RegX and tell me what the heck this RegX does. Not the fun part of writing the RegX and figuring that out.

[00:05:53] **Ben:** now I, I know that I often get a bad reputation for not testing my code, but, I will have, you know, that I did deploy it to production and then I hit F five and when the page didn't load, I'm like, oh, there must be a bug. Yeah. Fully tested now. anyway, that's me. Sean, what do you got going on?

## [00:06:13] Sean's Fail

[00:06:13] **Sean:** I'm gonna go with fail because, I have had my first experience with Android Studio today,

[00:06:19] **Adam:** Okay.

[00:06:19] **Ben:** Okay.

[00:06:20] **Sean:** and it has not been going well. nothing. It's, it's now got Gemini AI built into it

[00:06:26] **Sean:** or some sort of

[00:06:27] **Sean:** AI

[00:06:28] **Ben:** halfway done.

[00:06:29] **Sean:** and, you know, I was like, oh, you can, you can help me navigate my way around this. No.

[00:06:36] **Sean:** 'cause it keeps suggesting things that are just plain wrong.so I have not yet managed to get it to build anything without errors. I haven't even managed to get it to upgrade the gradle part without errors. and you know, it's, I'm glad the day is at an end and I'm not going to be frustrated by it for any more hours today, but I can look forward to going back to it tomorrow and being frustrated by it all day long tomorrow.

[00:07:02] **Sean:** I'm sure. So, and this, this is all about trying to debug an issue in one of our Android apps where I just need to figure out how to get visibility into something that is happening inside the app. So my thought was, oh, I'll install Android studio. We've done.

[00:07:18] **Sean:** it all with, expo command line before, I'll install Android studio.

[00:07:23] **Sean:** Great. It's got an emulator. I can run it in an emulator, I can debug it there. No, so far none of that's working. And I think it's probably compounded by the fact that.I'm on Windows and I use WSL,

[00:07:37] **Sean:** so all of my dev work, including all of the expo command line stuff to build the React native apps and run jest and do all the testing on the front end app.

[00:07:48] **Sean:** All of that happens on WSL. And I started by installing Android Studio for Windows. And unlike VS code Android Studio doesn't seem very good at figuring out how to get at stuff on, WSL and run things on WSL. So then I decided, you know what, they have a Linux version, I'll install that on WSL and it installed and, and it's, I still haven't gotten anywhere with it.

[00:08:16] **Adam:** Sounds like a good time to end it. End the day and crack a beer.

[00:08:20] **Sean:** Yeah, absolutely.

## [00:08:21] Mobile Development Strategy

[00:08:21] **Ben:** Let me ask you about the Android stuff. I'm just curious because I know with Android, or I guess I should say mobile development in general, there's sort of three camps that you can live in. You can go full native, I'm building stuff with all the Android, SDK, you can go the sort of like react script where you're writing it in a third party thing, like React, and it compiles down to Android.

[00:08:45] **Ben:** And then there's the lightest touch, which is, it's all just a thin wrapper around web views, and it's all HTL and CSS under the hood. What, what strategy do you take?

[00:08:55] **Sean:** We, we actually do have, a full React app, which is our web app, and then we have a React native sort of shell that sits around the outside. And we use that to build Android and iOS versions.

[00:09:07] **Sean:** And so the React native app is the part that handles all of the native interactions with billing, you know, Google Play or Apple App Store purchases, and camera stuff and, and things like that.

[00:09:23] **Sean:** but most of the logic is on the web app. And then there's one particular piece that's going wrong is an integration between the React native part on the Shell and the web app. And everything's working fine up until the React native Shell. And Of course.

[00:09:39] **Sean:** that's the piece I don't have visibility into.

[00:09:42] **Sean:** 'cause if it was in the web version, I'd just pull up a browser and debug it in the browser.

[00:09:47] **Ben:** Right? We get so spoiled by all the browser developer tools,

[00:09:50] **Sean:** Yeah.

[00:09:51] **Ben:** they're so good. Oh man, I, I'm just saying this out loud to myself. Not really to you guys, but the web view stuff, obviously that's been a long time proponent on the mobile side and on the desktop side. There's a, there's a product called Tauri, I don't know

[00:10:09] **Adam:** Yeah, that that's close enough I think.

[00:10:12] **Ben:** And, and they use the same kind of idea where they're using the OS specific web views and just doing a thin wrapper around it, which we've been able to do with Electron forever. But Electron embeds an entire, I guess, chromium runtime in

[00:10:29] **Adam:** like that. Yeah,

[00:10:31] **Ben:** the, apparently the, the Tari version, because it's using the native OS web view, it's like you can compile apps that are only like 180 K instead of, you know, three gigabyte kind of stuff.

[00:10:44] **Ben:** and I'm saying that out loud 'cause I've been dying to try it for years, not just deaf and carved out time.

[00:10:50] **Adam:** that's on the list of things that I'll probably never get to.

[00:10:53] **Ben:** That just sounds so cool.

[00:10:55] **Adam:** All right. Well, why don't we move into our main topic for the day, but before we do, Ben, are you ready to come out of the naughty corner yet?

[00:11:01] **Ben:** I dunno what I did

## [00:11:02] AWS DNS Outage Discussion

[00:11:02] **Adam:** Ben, you don't know what you did. I'll tell you what you did last week on the after show, you said, and I quote, taking down production is a rite of passage, and it's just something that we, and that is end quote.

[00:11:16] **Adam:** And, and it's just something that we have to kind of, you know, let happen and, and be okay with from time to time. Right. And then what happened yesterday, Ben, as we're recording this,

[00:11:26] **Ben:** do. Do you, does anyone know what happened? I haven't had a chance to look

[00:11:29] **Adam:** DNS happened. I, yeah, they haven't, as far as I've seen, they haven't released. So AWS went down right? A AWS region. US East one went down, and took like half the internet down with it because that's the way it works. and it was, from what I've seen so far, somebody made some changes to something. it affected DNS took out Dynamo db.

[00:11:51] **Adam:** And then Dynamo O DB is like the backbone of how they run most of the other services. And so it just started cascading and taking out other AWS services because they couldn't do their work to support, you know, our work as, as AWS users. So yeah, that was a fun day.

[00:12:07] **Ben:** Well, it'll be especially interesting because I think someone in the Discord chat was or maybe Sean was saying this, or Adam or Brian when I said, it must be so hard to calculate downtime, and this was before AWS. And someone said, oh, AWS actually has a policy where they can't say things are down because they invoke SLAs, and suddenly they have to start paying customers for missed time or something.

[00:12:33] **Ben:** I wonder how this kind of gets reported. It was just very, funny timing.

[00:12:37] **Adam:** There is like tension there, right? Like there's, you know, management pressure to just kinda sweep it under the rug, like fix it real quick and nobody probably noticed and you're fine. Right? And then. Me as the, the technology person, I'm like, no, this is, this is the moment for full transparency and like, let's post an announcement that things are broken and that, yeah, not, not this particular incident 'cause it wasn't our fault, but you know what I mean?

[00:12:59] **Adam:** Like, when, when that sort of thing happens.

[00:13:01] **Ben:** Well, I'm sorry.

[00:13:03] **Adam:** as you should be, sir. Alright, well with that out of the way, let's talk about observing user behavior. So Sean, do you want to tell us why you are a particularly, good and interesting person to talk to about this?

## [00:13:17] Observing User Behavior

[00:13:17] **Sean:** Well, I work for an online dating company, and so we run about 40 dating sites.

[00:13:25] **Adam:** 40. Wow. I figured it was like three to five 40 is

[00:13:28] **Sean:** no, it, it, it's close to 40. we have over 20 different Android apps,

[00:13:34] **Ben:** Holy

[00:13:34] **Sean:** and a bunch of iOS apps as well. so not every site has an Android app, but, You know, it's just the, the big popular ones. But that means that we have a lot of consumers, end users as our customers.

[00:13:49] **Sean:** and so we, we are interacting with the general public, and the general public are interacting with each other through the dating app, matching and sending each other messages and, and so on.and so how our members behave is extremely important to us for multiple reasons. One is we want it to be a safe space for dating.

[00:14:11] **Sean:** And so people who are abusive, or who cheat by trying to, you know, get their contact details straight away to the other person to get them off the app so that there's no tracking. Those sort of things are very important. Obviously, scammers love dating sites because they think that they can tempt people to send them money, which unfortunately is often true.

[00:14:34] **Sean:** so we're very interested in making sure bad actors don't get into the system, or if they get in, we figure that out pretty quickly and get them out. And then the other thing that's very interesting to us is what keeps a member engaged? Why do they buy memberships? Why do they renew their memberships?

[00:14:55] **Sean:** What sort of interactions do they have to have, with other members to keep them coming back? So, you know, we track it from both sides. Essentially. We are looking for behavior that looks suspicious, and then we're looking for behavior that's good, that leads to us getting money essentially.

[00:15:15] **Adam:** Right.

[00:15:16] **Sean:** and so we do, we have all sorts of scoring ideas, about, you know, your profile of the changes you're making.

[00:15:24] **Sean:** you know, we can, we've learned to detect scammers fairly well through that sort of stuff. and then we also have historical tracks of member behavior so that we can either in aggregate or even on a single user basis, look at the set of interactions they've had. Have they been liked by other members?

[00:15:43] **Sean:** Have they exchanged messages with other members? Have they made connections on the site? at what point do they buy a membership? do they create an account very interactive for a day or two, and then just go away? What causes them to go away? So that means that we collect huge amounts of data. we, we basically log.

[00:16:04] **Sean:** Everything that we

## [00:16:05] Detecting Scammers and Maintaining Safety

[00:16:12] **Sean:** can, think of, we log every action a user takes. We log every interaction between users. we run a scoring algorithm of member profiles, at login, and then a certain point past login to look at what sort of changes they've made to their profile.

[00:16:22] **Ben:** Can I, can I jump in and ask one question? So you're saying that you run, this parent corporation runs like 35 or 40 different dating sites.

[00:16:33] **Ben:** How, how isolated can you try different things? Like when you turn on a feature, is it turned on in every customer or

[00:16:42] **Sean:** Oh,

[00:16:42] **Sean:** right.

[00:16:43] **Ben:** have a freemium, like an app that runs it with a freemium business model versus an app that's like a credit card on day one, but a seven day trial kind of a thing?

[00:16:52] **Sean:** Yeah, we, all of our sites are data driven, so pretty much everything about every site is entirely data driven. And we have, an admin consult that member services use so we can tweak the behavior of each site individually. our feature flag system is also per site so that we can turn features on and off per site.

[00:17:16] **Sean:** and that same feature flag system also affects the front end. So if we flip a feature flag, the front end and the back end pick up, that change immediately and the behavior of the app will change.and then we have designed A DSL.that's kind of English like, but is very, customized to our domain that allows business to create English like rules.

[00:17:43] **Sean:** that we then turn into either database queries, elastic search queries, or, a predicate that we can apply to, an individual member. So for example, if we want to run a test of, what sort of trial memberships lead to purchases afterwards, we can segment that in all sorts of ways. we could do it off whether the user ID is odd or even, for example, we can do it about whether the member is male or female, which country they're in, how long they've been registered on the site, have they ever bought a membership before?

[00:18:19] **Sean:** Have we ever given them a trial membership before? Have they uploaded photos? and we can construct, you know, and, and all logic for all of that.we can check whether they've cheated in one of the various ways we consider cheating or abuse or anything like that. So we can build. English like rules that, really allow a, a huge amount of dynamic segmentation.

## [00:18:43] Scoring Behaviors and Engagement Metrics

[00:18:43] **Adam:** When you say cheat, are you talking about like romantically cheating? Relationship

[00:18:47] **Sean:** sorry. When, when I talk about cheat, we're talking about people, breaking the terms of service, which is, you know, don't post profanity, don't harass people, don't post your contact numbers because it's safer if you stay on the app in a moderated environment rather than, you know, if you, if the scammer gives you a phone number and you call them, they've probably got your phone number now,

[00:19:11] **Adam:** Right,

[00:19:11] **Adam:** Yeah.

[00:19:12] **Sean:** you know, and you don't want that.

[00:19:13] **Sean:** So, you know, we look for contact details in profiles and it uploaded images. 'cause that's one of the other things scammers do. They upload images with their contact details in,

[00:19:26] **Sean:** and it can be a phone number or it can be like a telegram username or something like that. and so. That's part of our machinery that we can actually detect scammers with queries that say, oh, you know, have we detected that their photograph is used elsewhere on the web?

[00:19:44] **Sean:** If they've uploaded a celebrity

[00:19:46] **Adam:** Oh wow.

[00:19:47] **Sean:** have they uploaded a photograph that's got text that looks like contact information?

[00:19:52] **Adam:** This is very sophisticated.

[00:19:54] **Sean:** yeah. It's, it's stuff we built over the years. I mean, the, the first version of the dating site was launched about 20 some years ago.and I've been there 15 now.and we've done several sort of rebuilds of the entire platform and learned a lot over the years.

[00:20:14] **Ben:** I I, know that we've often talked in the Discord chat about microservices, and it feels like that's such a perfect use case for things like that. You know, having to run all kinds of processing on an image after it's been uploaded.

[00:20:27] **Sean:** Mm-hmm.

[00:20:28] **Ben:** you don't wanna block a request and be like, lemme check with Google to see if this has been run anywhere yet.

[00:20:34] **Sean:** Right. And we actually have, we do, we use a lot of queuing.

[00:20:37] **Ben:** Yeah, I imagine.

[00:20:38] **Sean:** so we will have a lot of queues mostly in the database. and then we'll have processes that will claim an item off the queue process it put results back on another queue and something else picks those up. So, I mean, our entire system, we have a, a huge MySQL database.

[00:20:56] **Sean:** and we have many tables that have over a hundred million rows and several tables that have over 250 million rows.

[00:21:05] **Adam:** Wow.

[00:21:05] **Sean:** Amazingly MySQLs still pretty good at querying a lot of those things. but that data we, we massage into, an XML document and post to, Elasticsearch.

[00:21:17] **Adam:** Okay.

[00:21:18] **Sean:** and that is, that's a background process that runs continuously, that looks for changes in profiles.

[00:21:25] **Sean:** And every time it sees a change, profil, it creates one of these XML packets, posts it off to elastic search, and then. Our matching queries between members are all done via elastic search because we're not doing, you know, direct database queries, we are doing fuzzy matches. That elastic search lets us use.

[00:21:45] **Sean:** So we've got that sort of process going on. and then anything that's uploaded photos, those also go into a queue. We'll do some very, very basic manipulation on them when they're uploaded. but then they're put in a queue and we have a photo queue process and it pulls photos out of the queue and it sends them off to a service called Imager, which looks for text and not safe for work content.

[00:22:09] **Sean:** and

[00:22:10] **Adam:** Hot dog. Not hot dog.

[00:22:13] **Sean:** and so we, we also get it to estimate ages and gender and race so that, you know, if, if. Ben were to put up a photo, and you know, it was some young black woman, our algorithm would go, well, we are pretty certain this is a black female and you are not a black female, so you know, we're gonna flag that.

[00:22:39] **Sean:** so we do a lot of that. we, we also look, we send it off to Google to see if it can do a web search and find the images elsewhere. and that process automatically partitions photos into, yep, these look good, these look sketchy, and we're not sure about these. And then our moderation team can go through those separate queues and just sanity check and go.

[00:23:02] **Sean:** Yep. the photo queue machinery. Got it right. these are good photos, these are bad ones. And we'll go through the, the little bit of manual work in the middle and deal with those. And then in addition to that, we have fairly recently added. Google Gemini slash what are we on now? Two pro I think, to analyze all of the profile changes to look for, any sort of, you know, bad language, sexual harassment, violent language, contact details.

[00:23:35] **Sean:** And it can do that across all the different languages. 'cause that's the other thing, our sites are in about 14 different languages,

[00:23:40] **Adam:** Wow.

[00:23:41] **Ben:** Oh my

[00:23:41] **Sean:** including Arabic. So you've got right to left as well as regular left to right languages. and members can change the site dynamically. They can be logged in and just say, well, you know, I'd rather see the site in Spanish.

[00:23:54] **Sean:** And so the whole site will change to Spanish. So whatever we do with text and images also has to be, sort of processed through the lens of multiple languages.

[00:24:06] **Ben:** just bonkers.when you say that you're having AI analyze it,

[00:24:12] **Sean:** Mm-hmm.

[00:24:13] **Ben:** this a user facing thing? I mean, will someone go to submit a form and they get a message that says, okay, this is

[00:24:19] **Sean:** this is this is all in the background? Um, as they make changes to their profile, we put all those changes in a queue, not surprisingly. and then we send them off to Gemini with a bunch of custom instructions to say, you know, given our rules on our sites, is this allowable or not?

[00:24:38] **Adam:** Right.

[00:24:39] **Sean:** it's the same sort of thing where we get these changes to profiles Look good.

[00:24:44] **Sean:** Member services can just go, oh yeah, that's fine. and, you know, bulk approved, or These all look bad and they'll bulk disapprove, or, we don't know about these. that gap is pretty small with the ai. the image analysis has a bigger gap in the middle for the, the manual stuff. And of course we then track all of this as, oh, this member's been uploading a lot of contact information.

[00:25:08] **Sean:** They must be a scammer, we'll, you know, flag them for member services to, to look at in more detail.

[00:25:15] **Adam:** So I really kind of have so far two like lines of questioning I want to explore with you. you talked about scoring behaviors and just the, the sheer number of potential things that you could, you know, look for and assign a score to, and use that as just even insight into making other decisions what do you do for the tech stack for that?

## [00:25:36] Domain-Specific Languages for Business Logic

[00:25:36] **Adam:** I mean, that's, you're not just creating a table that's like, here's an, an event or, you know, like a, I don't even know what, like what do you do?

[00:25:43] **Sean:** Well, I've mentioned the DSL, and that allows the business people to create English like rules, which we then compile down to sql, predicate functions or elastic search. And the way we do it for predicate functions is because we're all closure on the back end. we essentially have an interpreter that turns the English DSL into an A STA syntax tree, and then it turns that into actual dynamic functions on the fly.

[00:26:13] **Sean:** So it will return a live function.

[00:26:18] **Ben:** Crazy.

[00:26:19] **Sean:** it's like functions, returning functions. So you can do it in cf, but it's just not something people do a lot of in cf. but it's really common enclosure to have functions returning functions.

[00:26:30] **Adam:** So.

[00:26:30] **Ben:** I know. I, I know Sean, you're a big fan of New Relic and I knew New Relic

[00:26:36] **Sean:** Oh yeah.

[00:26:37] **Ben:** their neral, which is

[00:26:39] **Sean:** Yes.

[00:26:40] **Sean:** New Relic query language,

[00:26:41] **Ben:** is that when you're talk, so for younger listeners, who aren't as wise as we are, DSL stands for domain specific language. And it's basically my, I'll, I'll, I'll mangle this, but it's like a way to create a more human friendly phrase for something that is a representation of something more complex under the hood.

[00:27:03] **Sean:** Yes. And so, for example, in our English like query language, we might have a query that says mail and has photos and has no free trial and registered 10 to 30.

[00:27:17] **Ben:** Right. And you're saying that builds some giant sequel statement that's joining a bunch of

[00:27:21] **Sean:** that that'll build sql. It'll build elastic search queries and it'll build, a function predicate on the fly. and then you can, with the predicate, you can give it a member's profile data, which we've read from the database and augmented and just say, does this rule apply to this member?

[00:27:40] **Ben:** Crazy.

[00:27:41] **Adam:** the scoring stuff, it sounds like it's happening on the fly, like just as part of day-to-day business, not an ongoing, like I, it's not that you assign a score to a behavior that I've done in the past. Like when it happens and then you look at it later, you're, I'm interested now, so I'm gonna go generate scores for all these things now.

## [00:27:59] Real-time Scoring and Profile Analysis

[00:27:59] **Sean:** Right? So on a per member basis, we will generate a score on the fly.

[00:28:04] **Adam:** Gotcha.

[00:28:04] **Sean:** and one of the things we found with scammers was that they tend to register. With something that looks fairly reasonable and then often, very quickly change their profile to something that is essentially catfishing. particularly if they find that they're getting suspended just after login. 'cause scammers are pretty smart. They realize, oh, you know, I logged in with this profile and immediately got suspended. Okay, I'll log in and create a new profile, ah, that got suspended. I'll try again. Ah, that didn't get suspended. Okay, now I'm in. Now I'll change my profile to the bad thing and (quack) suspended me again.

[00:28:44] **Sean:** so this is why we run the scoring algorithm, you know, when you finish registering and then a certain while afterwards. and why we use AI to look at all your profile changes. because even if you start off with a profile that looks good and you get past the first set of barriers, and then you try and change it to something that you can do catfishing from, We want to trap that as well.

[00:29:07] **Adam:** Right, and I mean, I, I have to imagine you've got things that you can query against or, or you know, whatever your DSL is hitting, but it's like looking at past behaviors, right? So like, has ever sent address. Message or has sent more than a hundred direct messages. Right?

[00:29:22] **Sean:** Right?

[00:29:23] **Sean:**

[00:29:23] **Adam:** and so I'm just trying to think through like the data model for that, right?

## [00:29:26] Data Architecture and Scale

[00:29:26] **Adam:** So you've got probably some collection of events, right? You a user and an event and maybe some other metadata or whatever, but like especially across 40 different properties, that has gotta be a ridiculous amount of data.

[00:29:40] **Sean:** it is. Yeah. I mean, we, we have an enormous MySQL database.

[00:29:45] **Adam:** and, and so are these event tables, like the things that are, the tables that you referenced that were like hundreds of millions of rows?

[00:29:52] **Sean:** Yeah. I mean, we sort of refer to 'em as log tables, but they really are event tables. so, you know, we record every action.And we record a lot of changes so that we, because the database, obviously with a profile, you want it to be the latest version. Um, that means you have to record a lot of the changes.

[00:30:12] **Sean:** And there's key fields we record all changes to, and other fields we're like, well, that's not so interesting in terms of change. but one of the things that, that is appealing to us, although we haven't gone this way, is, immutable bitemporal databases,

[00:30:26] **Adam:** Okay. You lost me. Atemporal.

[00:30:28] **Sean:** right? Yeah. and so in an immutable database, when you do an update or a delete, you don't actually lose the old data.

[00:30:38] **Sean:** So what happens is you get,

[00:30:39] **Sean:** an updated version of the record, or the record ceases to exist past a certain time, and then the temporality comes in from the fact that you can say, you know, at this date and time.

[00:30:52] **Adam:** hmm.

[00:30:53] **Sean:** What did the world look like? and with Byt temporality you can also say, given this time period and this information, what else can we find out from this period so we can find out whether two members were on the site at the same time.

[00:31:13] **Sean:** we could look at all interactions on a particular hour of a particular day in the past, and things like that.

[00:31:20] **Ben:** That's crazy. I've never heard of a database working like that. I mean, I've heard of, of, you know, like a pen only kind of strategies, but I've never, I've never heard anyone describe it in terms of temporality. I don't know what the

[00:31:31] **Sean:** Mm-hmm. And it's, the idea is that there's, there's a time when the information became available and was recorded system time, and then there's a time when that information was valid to and from.

[00:31:45] **Ben:** Interesting.

[00:31:45] **Sean:** so, you know, a good example is insurance policies. You know, your insurance policy is valid from say, the 1st of November this year to the end of March. But the insurance company, you are paid. So the insurance company has all that. So the system time about that information is perhaps last week when it was filed. And so then if during that period if you say, oh, you know, I'm going to have to change my insurance because I bought a different car, they will be able to say, well, this information came to us on this date and this is the effective date of the change. And those are two separate things. So you can say, what do we know and when did we know it?

[00:32:32] **Adam:** And you, so this by temporal stuff, is this like something you've kind of built on top of the MySQL stuff or is this a, a custom database or,

[00:32:39] **Sean:** this is something that we would. If we were building it from scratch today, we would go with a Bitemporal database

[00:32:46] **Sean:** because it allows us to ask and answer a lot of questions that you don't have to think about in advance. The problem with doing it in a regular SQL database is you kind of have to think about it in advance and go, oh yeah, we're gonna want to track when all of these things happen.

[00:33:04] **Sean:** and an immutable bitemporal database allows you to essentially punt on that and then go back in afterwards and go, okay, when did this change happen? What do we know about this change? What do we know about this day when we saw, you know, this massive spike in revenue, for example? and so for any sort of data that you are interested in tracking change over time and keeping all historical records, those sort of databases, just take care of that out of the box.

[00:33:35] **Sean:** You don't have to build anything. I mean, you can do temporal queries with a lot of databases. you know, if you go off and look up, temporal queries, you'll see SQL Server, Postgres. these all have ways of having columns with date and time that you have and then, querying things and you can say, you know, well run this query as if the system time were three weeks ago.

[00:34:00] **Adam:** Oh, interesting.

[00:34:01] **Sean:** but it's, it's having to add a lot of columns in and you've still, under the hood got a mutable database where when you do an update, you've got to be careful that what you are really doing is adding a new record and modifying those date times to say, well, the previous version is no longer valid now, and here's the new version.

[00:34:21] **Sean:** And it started to be valid when I did that update. So there's a lot of machinery to make it happen. whereas. Atomic XTDB, and there's probably others out there. They take care of this automatically, that when you do an update behind the scenes, it knows well as of this time now, that data is no longer valid.

[00:34:41] **Sean:** That's there and here's the new valid data.

[00:34:44] **Ben:** Very cool. As a, as a quick aside, I know in MySQL, and I don't know if other databases have this, but in MySQL there's a setting you can turn on that will prevent you from running queries that are unfiltered. So like there's no, there's no opportunity to say like update, you know, status to inactive without a wear C clause.

[00:35:04] **Sean:** Right?

[00:35:04] **Ben:** So it gets rid at least that small

[00:35:08] **Sean:** yeah.

[00:35:08] **Ben:** nightmares.

[00:35:10] **Sean:** Although it's still pretty easy to have a wear C clause

[00:35:12] **Sean:** that affects a lot more rows than you want. And you know when you run some manual update, 'cause you're doing some housekeeping on the database and you run an update and it says, you know. 10,400 rows updated, and you're like, oh,

[00:35:28] **Adam:** Oh no.

[00:35:29] **Sean:** no, that should have been 14 rows.

[00:35:31] **Sean:** What did I do?

[00:35:32] **Adam:** Yeah.

[00:35:33] **Sean:** so yeah, And that, there have been times, you know, yes, I've done that.

[00:35:37] **Sean:** Um, yeah.

## [00:35:39] Immutable and Bitemporal Databases

[00:35:39] **Sean:** so that's, yeah. This is, this is what's nice about the immutable data. You never lose your old data. You can always roll back. You can always pull back old versions.

[00:35:48] **Adam:** cost of probably a lot more storage space.

[00:35:51] **Sean:** Yeah. But storage is free.

[00:35:52] **Adam:** Yeah. Effectively. Yeah.

[00:35:54] **Sean:** yeah, I mean, our database is, let's see, I think our data drive, we recently updated the partition to, I wanna say 700 gig.

[00:36:08] **Ben:** pretty

[00:36:08] **Adam:** not that big, and that covers all, all 40 ish properties.

[00:36:12] **Sean:** Yeah, I mean, they're all in one database.

[00:36:15] **Sean:** the reason for that, in fact, is that we have related sites so that there will be three or four sites that actually will share members because they're, they're just essentially different names for the same property. like Perfect Date grwhich is one of our Greek dating sites and eligible greeks.com, which is another Greek dating site.

[00:36:36] **Sean:** And they have the same pool of members underneath.

[00:36:39] **Ben:** Oh,

[00:36:39] **Sean:** Um, you can log in, you can create accounts on either of them, and you will be able to search across 'em. But then we also have the idea of a world singles site where you can opt in to people in other groups being able to see you. So if you created a, a site on eligible Greeks, you can opt in and say, okay, you know, I want to search all the world's members on your sites. And then anyone else who's opted into it or has logged in and and create an account on world singles.com, they will see everyone across all sites. So that's why under the hood, it's all one big database, because technically if everyone opts in, you can see all of the members.

[00:37:23] **Adam:** So I mean, I, I, I gotta keep coming back to the tech here. So you've got a table with hundreds of millions of rows in it, and you want to, you wanna search over that table for some behavior that may or may not have happened for a variety or for all users or whatever. But how do you do that in a performant way, right?

[00:37:40] **Adam:** I have a table with 3 million rows in it, and if I want to just like, query out a batch of, of, you know, 5,000 records to, to set aside in another queue to work on that can. Sometimes be, slow and painful.

[00:37:52] **Sean:** Yeah, I mean, you, you have to go into this with some idea of indices on some of the things you're gonna be querying on. So our basic assumption is yes, you are going to be querying by member id, or you are going to be querying by time.

[00:38:07] **Adam:** Mm-hmm.

[00:38:08] **Sean:** And so we generally have indices on those. and then if we decide later, oh, we actually need to query on this other thing, we will either add an index, which MySQL will at least do in the background.

[00:38:22] **Sean:** So, you know, yay. or. We'll figure out how to do it in chunks and do the efficient chunked data, and then query across that in memory. and when you get to these sort of volumes of data, there are times where it's actually much faster to do a simple query in SQL and then do the complicated filtering in memory.

[00:38:46] **Adam:** oh, okay.

[00:38:48] **Adam:** You mean in like application memory?

[00:38:49] **Sean:** in the application Yeah. And in the logic. and, and that's just partly because, I mean, some of the things that we would build as queries, no matter how you index them, are just gonna be slow.and we've had situations where we've had, queries that are doing some aggregate calculation and, you know, you run them across, you want to get, for example, a dashboard that gives you, all of the, the moderation information that.

[00:39:16] **Sean:** Totals for all of the sites so you can do a grid. and so that's a lot of, aggregation across a lot of profiles.

## [00:39:26] Querying at Scale and Application-Level Filtering

[00:39:32] **Sean:** I mean, thousands and thousands of new profiles every day. So if you are doing that across a month, in a table that's existed for 20 years, you've got huge amounts of data to pull that out of.

[00:39:39] **Sean:** and so what we found quite often is that if you can do a simple query to pull like the, the top level number across and then in parallel in code drill down onto those, and I know it's the n plus one that they tell you not to do, but if your queries are simple enough, sometimes that n plus one query and then a bit of, application logic is going to be an order of magnitude faster than trying to do the whole thing with one query and joins an aggregate operations in sql.

[00:40:11] **Ben:** Well. So I know, sometimes you give me grief in the chat about like, you know, when you have a hammer, everything is a nail. and some of that though is more of a permissions access kind of a thing. So I have worked at a company, when I was at Envision. I, I could connect to the read replica database or I could run cold fusion in production.

[00:40:37] **Ben:** Those are my two options. And, if I tried to do anything in cold fusion in production, engine X would eventually just terminate my request. So I had to have something that would run in under like 60 seconds. If I connected directly to the database, I could run for longer. But I think something configured on the SQL server would only allow the connection to be like five minutes.

[00:40:58] **Ben:** So my whole world was like, it either had to run in 60 seconds or five minutes, so I had to do a lot of these like weird gymnastics. Kind of like what you're talking about, where I would deploy something to production and it would walk over the table like a million rows at a time and it would store into a separate table, just like A-J-S-O-N blob of, of kind of an intermediary aggregation.

[00:41:21] **Ben:** Then once that was done, I could then run a query on that table, which, you know, now had a hundred thousand rows instead of 10 million rows or

[00:41:29] **Sean:** Oh yeah, yeah, yeah. And I mean, you know, that that's definitely also been the case with us where we've found that some of the queries we want to run just aren't tenable to do them in real time, across the vast amounts of data. and so we, at one point we had some particular event that we were just logging.

[00:41:48] **Sean:** We were just logging the event, so you had the time it happened, the type of the event and some auxiliary data. And it got to the point where that just became too slow to query when we were trying to build aggregates for graphs. And so he said, you know what? We could aggregate this on a daily basis.by essentially truncating the date time down to the, the date, and then doing an atomic update, and count in an aggregate table so it record exists.

[00:42:18] **Sean:** You add one to the count. If it doesn't, you insert it with a count of one.and when we did that sort of stuff, we would always do it in a backward compatible way so that the queries would look at the aggregate tables first, and if the data wasn't there, they'd then do the slow query against the main part.

[00:42:37] **Sean:** and then they would kick off a backfill of the aggregation. And so whenever we'd made big schema changes like that, we've always tried to do it in a way that a, we can deploy the schema change, live as part of the deployment. So all of our SQL migrations are run as part of automated deployment.and we can do that while the legacy code's running.

[00:42:59] **Sean:** So we. Make sure that it's a compatible with legacy code and that B, when we deploy the new code, it's going to start searching the new tables we created or the new columns we created, and fall back to the old data and start back filling it. So yeah, every schema change. You have to think through that when you are dealing with so much data.

[00:43:24] **Sean:** Uh

## [00:43:24] Zero-Downtime Deployments and Schema Migrations

[00:43:24] **Ben:** think that's so powerful though, because Okay. You know, in, in the olden days, we used to be able to take a site down, and I'm sure you know, some sites still do this, take a site down, it's gonna be in maintenance mode from, you know, Saturday at 11:00 PM to Sunday 2:00 AM right? And, and, and then it's carte blanche.

[00:43:42] **Ben:** You do whatever you need to do to get the work done, but once you have to meet a certain level of availability. You really do have to start thinking in these phased approaches and not just in the phase rollout, but then, something went wrong. How do we roll that back in a way that suddenly the business logic can't handle the data that's in the database?

[00:44:01] **Ben:** And I feel like once you start thinking about stuff like that, it, it affects you see how it it in it improves the way you think about like every aspect of application development, you know, from your, from your Android mobile apps. And you know, we have people using 17 different versions of the Android mobile app.

[00:44:19] **Ben:** Right. And, and the APIs have to be backwards compatible. And how do you end of life certain properties? I dunno. I think it's so fascinating to think about this stuff.

[00:44:28] **Sean:** Oh yeah, absolutely. And I mean, feature flags are a big help with this because you can, you know, keep deploying the code behind a feature flag. and you know, on your staging environment you have the flag one way, and in production you have it. The other, or in our case, you know, might, we might have it on in one site and off in all the others.

[00:44:45] **Sean:** and it doesn't interfere with your deployments. So you can incrementally build your feature, you can test it incrementally, and then once you are happy with it. You will turn it on in production.and you know, this is also why we've tried to be very careful not to need, to roll back schema changes because that does complicate

[00:45:07] **Sean:** things.you know, if you are going to roll back the schema change, you've got to roll back the code first because you now need to get the code back to the old format code that's not expecting the schema change you just did. And, then you can roll back the schema change, but you've also gotta figure out, well, what happened to all the data that was being collected in the time that we had that out there before we decided to roll back?

[00:45:32] **Sean:** What are we gonna do with that?

[00:45:34] **Ben:** it, it's such a fascinating thing to think about deployments because not only do you have to think about this forward and backwards concept, but I'm, I'm assuming that you're using some sort of a rolling deploy where, you know, you're not, you're not deploying 90 servers all on a blink of an eye.

[00:45:52] **Ben:** I mean, I don't know how many surveys you have, but you might have,you know, an Android phone. It's making an API request and in the middle of a deployment it hits one server that's running a previous version of the code and in the next API request it

[00:46:05] **Sean:** Goes to another server.

[00:46:06] **Sean:** That's

[00:46:06] **Ben:** a server that's running newer code.

[00:46:08] **Sean:** absolutely. That absolutely happens. I mean, we actually have server to server communication happening as well, so, you know, a service running on one server will make a request, and then maybe the next time it makes that request, the server that it hit last time is down because it's having a deployment done.

[00:46:28] **Sean:** And so pretty much everything we do in terms of that, we always have to have retries. 'cause it's like, oh, we've got a 5 0 2 from the gateway, the service is down, we'll retry in, you know, 30 milliseconds, a hundred milliseconds, whatever.and it's why we also use queuing a lot because we try to avoid direct coupling between processes and it's really a case of what from the user's point of view needs to happen instantaneously.

[00:46:55] **Sean:** versus, you know, what can we do in background and, and how does it, what does it matter to the user if it's 30 seconds out of date, for example, things like that.

## [00:47:07] Primary Key Strategies

[00:47:07] **Ben:** Can we, can we get a quick hot take on primary keys? Are you, an an auto inter incrementing big integer? Or are you a, a uid, goid, qid kind of guy?

[00:47:19] **Sean:** It depends. it depends on what we think the lifespan of the data's going to be. we definitely have tables where we knew upfront that the auto incrementing, ID just wasn't gonna cut it. And so we went with, UIDs.

[00:47:33] **Ben:** Gotcha.

[00:47:34] **Sean:** and then we have a bunch of tables where, you know, yes, it's gonna be just fine with an auto incrementing id.

[00:47:40] **Sean:** even if we wrap around the end of the table because we're the, for data that we're gonna prune beyond a certain date or that we're going to be, relocating from table to table, which is the other thing that we've done sometimes. so you'll have some housekeeping process running that's back filling another table.

[00:48:02] **Sean:** With the data you want to keep outta the first table, and then at some point it catches up and it's like, okay, I've got all the data I need, you know, now let's start deleting that old data and cutting over the process to talk to the new table.

[00:48:16] **Ben:** I'll tell you primary keys is like my died in the wall. Old man yells at cloud, like I I I can academically, someone could gimme, here's 10 reasons why you should never use auto incrementing fields, and I will agree with every single thing you say. And then I feel like I'm still gonna use auto incrementing IDs.

[00:48:37] **Ben:** I dunno, I just love them. But certainly, you know, for certain tables I can totally understand it, but it's, it's

[00:48:44] **Ben:** like

[00:48:45] **Sean:** Yeah,

[00:48:45] **Sean:** and I mean, we've, we've certainly had situations where we've had, we had one table where we did want to keep everything and we had an auto increment. I, ID primary key on it and we ran off the end

[00:48:58] **Ben:** Yeah. Yeah, I've been

[00:48:59] **Ben:** there. I, I was there, Thanksgiving morning

[00:49:02] **Adam:** Oh.

[00:49:02] **Ben:** happened to us.

[00:49:03] **Sean:** Yep. And you know, suddenly you've got a production down because you, you, as far as the process is concerned, it ran outta space. it ran out of index space and, you know, we've had to very creatively come up with something that we switch from auto in, auto increment over to UIDs. And again, it's this, well, we're talking to two tables.

[00:49:27] **Sean:** So now the new code writes to this table with these IDs. And when you're querying, you look in both tables and now you backfill the items you found and Yeah. Yeah. It's, there's, there's a lot of entertaining stuff goes on in that when you're dealing with that volume of data.

[00:49:43] **Ben:** Oh man,

[00:49:44] **Adam:** So I want actually kinda wanna go back to something you had said pretty early on in this conversation. So you were talking about all the different things that you do.scoring behaviors and stuff. And one of the things you mentioned was, kind of getting, an idea of what the users of the website want, right?

## [00:50:00] The Underground City Tool

[00:50:00] **Adam:** The, the people that are signing up for these dating sites and what makes them come back, what makes them buy memberships, that sort of thing. Is that at all different from the work of, you know, inspecting user behavior for, you know, scamming or other

[00:50:16] **Sean:** Yeah, the the way that a lot of the user behavior, the good user behavior gets figured out. we have a standalone process called Underground City, which is a ColdFusion, app. In fact, it's running on Lucy. and it's built and maintained by one of the business team and. They connect to the, the secondary database read only so they can, they can tank the performance of the secondary, running awful queries.

[00:50:47] **Sean:** But what they do is they, they explore the space. And so one of the things that they can do if they find, oh, you know, this, this looks like an interesting interaction between these members, let's drill down into the individual member. and they have a graphic display that shows that user's, events in different colors as like a, a snake.

[00:51:10] **Sean:** So they can see the distance in time between certain events. and so they can visually look at patterns and so they can see, Oh, this person had a purchase event after. A bunch of these interaction events. Let's see if anyone else does that. Oh yeah, this looks like a fairly common pattern. So if we can encourage these interactions, we are more likely to get people buying memberships.

[00:51:38] **Sean:** What can we do to encourage this? And then you have to brainstorm around, well, how do you guide people to do these things that you want them to do without making it look like you are putting a cash register in front of them and saying, give us your money.

[00:51:53] **Adam:** Right.

[00:51:54] **Sean:** So, you know, we, we try and come up with creative ways to figure out, oh, well, what will encourage member to come back to the site if they get an email from us?

[00:52:05] **Sean:** and so one of the things we, we did was we figured out, oh, if you've made connections with people and those people have uploaded photos. I bet we could get you back to the site if we sent you an email with the latest photos uploaded by the people you have a connection

[00:52:24] **Adam:** Mm-hmm.

[00:52:25] **Sean:** 'cause it'll encourage you to go back to that person that you've already got a connection with and say, Hey, saw you uploaded this new photo.

[00:52:33] **Sean:** You look great at that outfit. Now it turned out that the actual logic behind that was really hard because we're running across, you know, millions of users, looking at all of the connections they've got. And of course, one person might have a connection with 50 other members. And so we're then saying, okay, now we need to find all of the recently uploaded photos for those members.

[00:52:57] **Sean:** And C, which of those photos were uploaded since person A last came on the site and looked at that member? In other words, their photos that person hasn't seen.

[00:53:06] **Adam:** Yeah.

[00:53:07] **Ben:** just, just to put the, the, like a lens on the scale there. It's easy when you're thinking about a specific user like, Adam hasn't logged in in two weeks. What can we do to bring Adam back? But it's a very different problem when you're like, what of the 200 million user records do we have are relevant for this?

[00:53:28] **Ben:** You know, talk about an n plus one query. You know, that's that, that I don't, I don't even know how to solve stuff like that.

[00:53:34] **Sean:** yeah. And, and, and making that work, efficiently can sometimes be very hard. so I mean, sometimes we will just delegate to some new background process and say, okay, you know, scour through all of the profiles who've been active in the last six months, but haven't logged in for a month, and you know, that we can find pretty easy.

[00:53:57] **Sean:** That's a fairly straight query. And then you have to go in and say, okay, and now for each of those. Find their connections and for each of those connections, see if they've uploaded photos since this date. And then, you know, it was like, okay, well they've uploaded six photos, we don't want to send six photos in the email.

[00:54:17] **Sean:** Are we gonna send the most recent photo? Are we gonna send the oldest photo? you know, things like, that.

[00:54:22] **Sean:** we might look at, you know, what does our image analysis say about the photo? This will probably be a more attractive photo to them than this one, for example.so yeah, sometimes, we'll, we'll have a go at doing it the brute force way just because yep, let's just test if this is even feasible.

[00:54:39] **Sean:** And it doesn't matter if it's slow. And then you go, yeah, this works. Okay, now we need to optimize it. And this kind of goes back to underground city that I was talking about. That's where the business team can experiment and run all sorts of nasty queries and. Then sometimes they'll go, Hey, we got a real good insight.

[00:54:59] **Sean:** We want to implement this in the main system.but the way we're doing it is really inefficient, so you'll have to figure out a way to make it happen efficiently. And that's when sometimes we'll go, okay, now we need a process that's gonna do the aggregation in batches. So that's another continuous process we'll throw up on one of the servers.

[00:55:19] **Sean:** And now we're able to run this fast query across the aggregate data.

## [00:55:23] Data Teams and Business Intelligence

[00:55:23] **Ben:** Now I, I know that like, I feel like 10 years ago, maybe not quite that long ago, data scientists were like the hot thing. Everybody wanted data scientists. Everyone was hiring these PhDs in mathematics. When you say business team, is that like part business intelligence, part data science? What, like what's that team look like?

[00:55:44] **Sean:** They, they are full on business people. They, I mean, they either are interacting with customers or they are coming up with the features or the long-term goals of business. They, they're not data scientists.

[00:55:55] **Ben:** it. Very holistic team.

[00:55:56] **Sean:** yeah. And so they have enough tooling available to them that they can run pretty much any query they can imagine.

[00:56:04] **Sean:** when they find things that are interesting to them, they will then essentially throw it over the fences into a ticket that we have to implement on the, the main system in a fast, efficient, and well-maintained manner.

[00:56:17] **Ben:** just the, the, the ability to find those patterns to me has always seemed like magic.

[00:56:23] **Sean:** yeah, and I mean, and there are also things that have gone the other way. I mean, we actually had quite a, a complicated graphic engine built into, the admin console. That was doing a lot of these ad hoc queries. and the business team said, well, there's these extra things we need and these extra things.

[00:56:40] **Sean:** We want a query on this, we want a query on that. And so we said, well do it in underground City, an experiment, figure out what you need and when you have something specific you want the front end or the the main system to do, let us know. And in the end, we completely retired the graphing engine because they were able to get everything they wanted in the underground city, even if the queries were really slow.

[00:57:07] **Sean:** And then they were able to elaborate on that. So, you know, we have gone both ways. and every now and then I'll go into the, the Underground City stuff and I mean, it's full of visual displays of all sorts of data. and some of the pages take many minutes to come up.

[00:57:24] **Ben:** Okay, so I've, I'm gonna throw out some phrases that I don't even know what these mean, but I've heard things like data lake, data warehouse, star schema. which I understand these are all techniques for making data accessible. It, it sounds like you guys just have really beastie read replicas.

[00:57:47] **Sean:** Yeah, yeah. Our, our database, the physical servers, well, they're actually virtual servers, so our database is actually run on virtual servers,

[00:57:55] **Sean:** uh, which I was amazed that the data center could actually make that work at the scale we needed. but yeah, I mean, they are, they are monstrously large servers, with huge SSDs.

[00:58:06] **Sean:** and so they are, I forget how many CPUs they've got and how many gigs of ram, but they're, they're big, big servers.

## [00:58:17] Simplicity vs. Complex Analytics Systems

[00:58:17] **Sean:** Um.

[00:58:18] **Ben:** so great though. You know, I'm, I am always a fan of keeping things as simple as possible for as long as possible, and that, that you don't have to introduce this whole. Analytics warehousing, data mining thing that you can get work done with more or less the tools that you're familiar with. I mean,

[00:58:37] **Sean:** yeah, and, and we looked at it. I mean, we, we've looked at, offloading data to S3 and we've looked at Redshift and stuff like that. for a while we were using MongoDB for a whole bunch of data, on the grounds that, you know, the types of queries we wanted suited it. and in the end we just realized that it was gonna cost us so much more to maintain all these multiple systems.

[00:59:01] **Sean:** And if we could make it all work off sql, MySQL, it would ultimately be cheaper and fast enough.

[00:59:08] **Ben:** Well, I remember, so we had Brian class as a guest, I don't know, like three years ago it feels like at this point. And he was talking about all of the AWS services that they use and or, or not even just that they use, but just some of the really interesting things. And I think he talked about offloading data to S3 and then being able to query it almost like it's relational data table using, I think it was a Athena maybe.

[00:59:33] **Ben:** And I was like, oh my God, that's so crazy. I can't even believe that works. He's like, yeah. So you go in and you start your query. And then you check back occasionally to see when it's done and maybe it's six or 12 hours later it has data and I'm like, oh, okay.

[00:59:45] **Sean:** Yeah.

[00:59:46] **Ben:** I'm like, alright. So it's not quite as magical as I thought it was gonna be.

[00:59:50] **Sean:** yeah. In fact, that's, that's one of the interesting things about XTDB, which is built by a company in the uk

[00:59:56] **Ben:** I'm sorry, what is XTDB.

[00:59:59] **Sean:** that's, it's, it's the bitemporal immutable

[01:00:01] **Sean:** database. It's one of the, those that I was talking about, they just called XTDB. I can't why they called it that, possibly because the company's name is Juxt, JUXT. So

[01:00:11] **Sean:** XTDB makes sense there.

[01:00:13] **Adam:** maybe XD is like a common, shortening of bitemporal or something.

[01:00:17] **Sean:** but that in its sort of production setup uses S3 as, storage, sort of flight for the slow storage for everything. and it uses Apache Arrow for the file format. and then it figures out what data you need hot and basically indexes and caches that in memory on the nodes. So every now and then you'll hit a query that it has to go to S3 and, and, you know, go through all these arrow files.

[01:00:48] **Sean:** But for the most part, a lot of the, the data queries you are doing, will stay hot in memory. and so it's actually surprisingly fast, but it's capable of doing very elaborate queries slowly as well. So you don't need two databases for it, which is where I was really going with this. And it's, again, came back to the point that we ended up using MySQL for quote everything.

[01:01:14] **Sean:** because, you know, you, you can run both types of queries out of, you can do the data way, warehousing queries that are gonna take time and then you can keep all of your transactional stuff running very, very fast for the member facing apps.

[01:01:29] **Ben:** I have always been fascinated by read replicas because like you're saying, you can destroy a read replica and it doesn't really impact much. but in my experience, read replicas have always been an exact replica of the primary database. Just, you know, 60 milliseconds later kind of a

[01:01:49] **Ben:** thing. I, I have.

## [01:01:51] Database Indexing and Replication Lag

[01:01:51] **Ben:** Heard that you can have read replicas that actually have not different structures per se, not like, not different schemas, but totally different indexes so that you can make the read replica more friendly for certain types of queries. But I've never learned anything about that. I don't quite understand how it works, but it seems like a fascinating idea.

[01:02:12] **Sean:** I, I don't know enough about databases to have much of an opinion on that.

[01:02:17] **Ben:** Me neither. I'm an auto increment guy.

[01:02:21] **Sean:** I remember standing up at one of the coal fusion conferences when I was talking about something to do with databases, and I admitted to everyone that I had only written my first join in SQL a few years prior to giving that talk at a conference. because I just didn't touch databases. I just didn't touch SQL for most of my career.

[01:02:43] **Sean:** Other people dealt with the database. I dealt with business logic.

[01:02:48] **Ben:** I literally remember I was working, for a company called Recycle Bank that had a rewards-based recycling program. And we were having admin pages that were taking like 20, 30 seconds to come up just to render. And I was like, and I, I remember going to the CTO at the time and being like, I just read about this thing called database indexes that might help our performance here.

[01:03:10] **Ben:** And it was one of those like light bulb, you know, change the rest of your life moments where you put the index in and the query that took 30 seconds is instantaneous,

[01:03:20] **Sean:** mm-hmm.

[01:03:22] **Ben:** bonkers.

[01:03:23] **Sean:** Well, it's also the indexes. If you've got complete replication between a primary and secondary, sometimes your indexes can slow replication down because the index will get applied for the changes coming across in replication. and we had a situation like that where our replication lag just kept increasing.

[01:03:41] **Sean:** and we were actually seeing replication fail, because the insertions were timing out and we engaged a database specialist company and they took a little while and eventually figured out, oh, if you take this index off, replication will be much, much faster and this other index will give you enough coverage to not, impact the performance of your queries on the primary.

[01:04:09] **Sean:** And I was like, oh, I'd never heard of having to take indices away from a database to speed it up. So that's something else to

[01:04:17] **Ben:** that is fascinating. I know because you, because a lot of times you're like, why can't I just index every column? You're

[01:04:23] **Sean:** Yeah. And that's the

[01:04:24] **Ben:** that's a lot to maintain.

[01:04:25] **Sean:** Yeah.

[01:04:26] **Sean:** because then your insertion is doing a huge amount of work. 'cause it's forcing all the indices to be rebuilt, to be rebuilt.

[01:04:31] **Adam:** Yeah. Well, I think for me, the most, the, the biggest and most obvious lesson I'm taking away from this episode is, with MySQL. Most of the time you can probably just throw money at performance issues, right? Like just, just add more CPUs, just add more ram

[01:04:46] **Sean:**

[01:04:46] **Sean:** and, write better queries. But still, like, And if you, if you're all on virtualized equipment, a lot of the time you can just expand the amount of RAM available or the disc or the CPUs without downtime.

[01:04:58] **Adam:** Yeah.

[01:04:59] **Sean:** 'cause when we've expanded the disc on our databases recently, that was done by a configuration in the, the virtual system, and suddenly the databases had a hundred gig more disk.

[01:05:13] **Sean:** You know, we've had situations where they've added CPUs without having to take anything down. The system's gone from like 16 CPUs to 24 CPUs.

## [01:05:22] Virtualization and Infrastructure

[01:05:22] **Adam:** Yep. What a time to be alive.

[01:05:24] **Sean:** Yeah, it's the, the virtualization. I was quite skeptical about it when our data center folks started talking about virtualizing everything.and one of the things that they recently did with us, which was very impressive, they moved us from one physical data center to another.

[01:05:40] **Sean:** And because it was all virtualized, essentially what they did was they shut down the virtual machines, shipped them over their network and powered them up on the new

[01:05:51] **Ben:** Crazy.

[01:05:51] **Sean:** servers. And So we didn't have to do anything. None of the networking infrastructure changed. None of the IP addresses changed, none of the routing, nothing.

[01:06:00] **Sean:** They just essentially shut everything down, shipped it all across, powered it all back up, and we just had a different firewall to, to log in through to get at everything. And

[01:06:11] **Ben:** So cool.

[01:06:12] **Adam:** Alright.

## [01:06:13] Pig Butchering and Romance Scams

[01:06:13] **Ben:** Well, well, okay. Before, before, I know we're at the top of the hour here. I, I, I can't not say the phrase pig butchering, but the, so, so as Adam alluded to at the top of the show, one of the things that I was interested in was the scam and detecting malicious actors. And just, just to put some scale on it, and I'm sure I'm gonna butcher these numbers, no pun intended, that, that I was listening to an interview

[01:06:38] **Ben:** Two days ago, and they were estimating that of all of the financial crimes that happened globally. Something like 15% of them are these catfishing pig butchering. Like, it, it, it, it represents a tremendous, like in the hundreds of billions of dollars annually, kind of, of, of an issue. and the two that, that I've heard talked about are catfishing, which I think is less malicious and more sad and lonely, which is you just pretend to be someone else, right?

[01:07:11] **Ben:** Every, no one, what, what's, what's the joke like on the internet? No one knows you're a dog or something like that, right? And then there's pig butchering, which is when you using a catfishing profile, befriend, try to romanticize, try to get someone to fall in love with you over many months.

[01:07:29] **Sean:** Mm-hmm. Oh, yeah.

[01:07:30] **Ben:** gain their trust, gain their affection, and then approach them with a, oh, you know, I've got some great news.

[01:07:36] **Ben:** I just made a bunch of money on this crypto investment. And slowly get people to invest in your fund or, you know, in your kind of thing. And it's, you're not taking people for like hundreds or thousands of dollars. Like you're literally, people are losing hundreds of thousands of dollars and, it's, it's just a tremendous amount of, of malicious activity.

[01:07:59] **Ben:** And I, I just imagine trying to find and prevent that, it's gotta be challenging and

[01:08:06] **Sean:** yeah, it, and it, and it's fun because, our member services team are the people who see anything that gets past the existing safeguards. And so they will be the ones who will say, okay, we need to be able to spot this behavior, or this sort of interaction, how can we do it? And they've gradually learned over time, oh, okay, well here are some things we can do.

[01:08:29] **Sean:** So the scoring system I talk about is a whole bunch of rules that are actually written in closure code, but it's still very readable. and so we have a scoring file that has hundreds of positive and negative rules that are literally just functions, anonymous functions, and. Pretty much any aspect of a member's profile or their membership history, can be queried in that.

[01:08:59] **Sean:** And so there's, there's a lot of things that member services will say, well, you know, we found that people say they're from this area, and are using these patterns in their email addresses. And they're usually making themselves out to be, you know, a blonde woman in her forties, who comes from one of these ethnic groups.

[01:09:24] **Sean:** And so we'll come up with the rules that score that at say, you know, minus 75 or minus 300. Or if it's something that we think, you know, good people are gonna get caught in a rule and we can identify, oh, if they say these things on their profile, we'll give them positive score. And we can check things like, you know, does the IP geolocate where they say they are, are they claiming to be from a suspicious, family roots history for where they say they're going to be on this particular site?

[01:09:58] **Sean:** So there's combinations of, well, if you're on an Albanian site and you know, you say you are Spanish and you're in this part of the world, you're probably a scammer as it turns out, because, you know, we've seen this pattern before. so it's, it's a constant cat and mouse game.

[01:10:16] **Ben:** Right. And, and just, and just for the listener's benefit, you know, when, when you talked earlier about running image analysis and looking for contact details, it, it, it's easy for someone to not be thinking too deeply about this and say, oh, this is just part of the attention economy and they want to keep people on their site.

[01:10:33] **Ben:** But the reality is, when you keep people on your site, you have all of these mechanisms in place to protect people, and you don't want someone to meet and hey, you know, hit me up on Telegram or, or WhatsApp so that we can talk more privately. Like that's a huge red flag. And you're really protecting people, Mo, because most people don't know about this stuff.

[01:10:56] **Sean:** Right.

[01:10:56] **Sean:** You know, and if, if someone you start chatting with pretty much immediately says, oh, you know, here's my cell phone number, let's chat on the phone instead. Or let's text. There are people who are like, oh, okay, yeah, sure, we'll text. And as soon as they do that, we can't help them at that point 'cause they're no longer using our system.

[01:11:16] **Sean:** We are no longer able to monitor the messages that are going back and forth or the interactions. you know, and we may see, for example, that a profile is engaging with hundreds of other profiles. Sometimes that's just, you know, guys being clueless and liking hundreds of women and sending them the same Hi you, cute message.

[01:11:38] **Sean:** And which we literally will see, you know, we'll see a guy comes on and he'll send 400 women, hi, you cute

[01:11:45] **Sean:** in, you know, 15 minutes because he's just,

[01:11:47] **Adam:** cast the broadest net possible.

[01:11:49] **Sean:** but then there are other situations where we'll see, you know, this sort of development of, a chat history happening with lots of people at the same time.

[01:12:01] **Sean:** And so, you know, they're gradually trying to pull in dozens of people and that is suspicious. That's not just clueless, that's suspicious. So

[01:12:12] **Adam:** so I had some questions about the scoring stuff too. It didn't even occur to me until you mentioned like, okay, so we might give these ones a negative score. These guys, a positive score is the whole goal of the scoring system to be able to like, sum up some selection of events and, you know, given this query, if the, if the sum of the scores is positive than this and negative than this or over some threshold, is that the, the goal of scoring in the first place?

## [01:12:36] Scoring Rules and Automation

[01:12:36] **Sean:** Well, the scoring, for the most part it gives, the intent of the scoring is to give us, a, a figure that will fit in a range where we'll say, okay, if the score is in this range, we will automatically suspend the profile. If the score is in this range, we'll put it up in front of member services for manual review.

[01:12:56] **Sean:** If the score is in this range, we'll automatically approve the activity.

[01:13:00] **Adam:** Gotcha.

[01:13:01] **Sean:** So it's very much like we do with the image analysis to say, you know, well, can we tell this is a good image? Can we tell it's a bad image? We don't know with the text they're putting in their profile, is it good text? Is it bad text?

[01:13:15] **Sean:** We don't know. And we want to try and get the work, the manual work of the member services folks minimized by having as few false positives, as possible. So the scoring is, is one thing that we are constantly tweaking. and in fact for, for kind of humorous internal reasons, our scoring engine is a process called Frankie that has three E's at the end.

[01:13:41] **Sean:** and its logo is kind of like a little Frankenstein monster.

[01:13:44] **Adam:** Okay.

[01:13:45] **Sean:** and the Photo Q is known as Otto 'cause he's Otto photo, he's an auto photo ally analyzer. So, So we have Frankie Scoring and member services will create a triage ticket that has Frankie scoring adjustments, and I think we're up to about 34 or 35 in terms of triage tickets that they've sent through just for scoring changes.

[01:14:10] **Sean:** and each one will typically have, you know, three or four rules that they want to add or tweak. And I will usually, as soon as I see one of those, I'll move it over to the backend, JIRA board and it will get done and it'll be up on production in about an hour after that. And that will have gone through the full testing and CIN deployment to QA and then promotion to production.

[01:14:35] **Adam:** Well that kind of gets at something else I was thinking of too is, you know, you're trying to look out for people, you're trying to spot scammers and people who just have nefarious intent. are you doing any sort of like real time monitoring of chat history or that sort of thing? Like, 'cause you talked about kind of everything going through queues.

## [01:14:52] Real-time Monitoring and Queue Processing

[01:14:52] **Adam:** How do you keep up and, and try to get like, you know, real time, hey, maybe this person's a scammer, maybe you shouldn't be

[01:14:59] **Adam:** talking to them.

[01:15:00] **Sean:** it's a trade off. It's an interesting trade off because we want to obviously make timely decisions on things, so you don't want something sitting in a queue for a long time. and part of why we've automated stuff is to try and get approval time down as fast as possible so that if you are a good, well-intentioned person who's coming to the sites to date, you know, your profile changes, your photos will probably get approved in a few seconds.

[01:15:25] **Sean:** and. The stuff. And so we've geared the system that, anything that's considered good from scoring, screening, ai, whatever, those are all going to go into a queue that's front loaded. That member services will just look at the whole list and go, Yeah. they all look good. Click and, you know, 50 changes will get approved.

[01:15:46] **Sean:** or it'll just be automatically approved. And then there'll be a screen where member services can go in and retroactively go, oh no, that shouldn't have gotten through. And we'll yank it back. and then if the stuff that we think is bad, it's kind of less important for that to be reviewed in that we will already have curtailed some activity and potentially suspended members or deleted their photos or denied their profile changes.

[01:16:14] **Sean:** 'cause if they're trying to put contact details into their profile. That simply won't show up until it's been approved. And so if it sits in a queue where we think it's bad for a couple of days, that doesn't matter. But the good stuff we want done, obviously as fast as possible. So anything like this is always a trade off.

[01:16:31] **Sean:** And the more complicated the query, the more complicated the process, the longer it's gonna take. And so we will often try and find shortcuts or ways to say, well what, what can we do to mitigate damage while we are waiting for this to be analyzed? a lot of complicated

[01:16:49] **Adam:** It's a very interesting, sector of technology that you're working in there.

[01:16:54] **Sean:** that we've gradually been able to leverage AI for more and more. Parts of it has proven to be a very interesting learning curve.

[01:17:03] **Ben:** do you have any sense at all of whether or not users use AI to like, help refine their profile descriptions or anything like that? Is there any, I mean,

[01:17:14] **Sean:** I don't know.

[01:17:16] **Ben:** I'm always curious about that

[01:17:17] **Sean:** it, I think it's something users could certainly do on their own.

[01:17:21] **Ben:** Yeah, yeah.

[01:17:22] **Sean:** you know, if you want to make your bio really sound good and you are willing to use, you know, chat GPT or whatever

[01:17:31] **Adam:** Lots of M dashes.

[01:17:33] **Sean:** that's m Dashs

[01:17:33] **Ben:** You know, m dashes get such a bad rap. I, I love an M dash.

[01:17:38] **Sean:** I went to an English grammar school.

[01:17:39] **Sean:** I use M

[01:17:40] **Adam:** Yep, me too.

[01:17:41] **Ben:** I love M dashes. I love semicolons. Come on.

[01:17:44] **Sean:** but yeah,

[01:17:45] **Sean:** I mean, you know, the AI aspect of it, of course is also something helps scammers. So, you know, you, it's, it's an escalating battle. the scammers get smarter. We have to get smarter in the way we detect them. We have to get faster at it.

[01:18:00] **Ben:** Well there was.

[01:18:01] **Sean:** if, if we'll sometimes see that someone will have set up a way to create hundreds of new profiles.

[01:18:08] **Sean:** So instead of creating one profile and then trying to use that to go after people, they'll create hundreds of profiles. and try and automate that because, you know, after all, our system is based on an API. And you know, if you can figure out how to automate the API, you can do actions programmatically.

[01:18:26] **Sean:** So they're also speed traps built into our system. So if we see behavior happening too fast, it's like that's not a person.

[01:18:34] **Adam:** Yeah. I think, we gotta find a place to stop. That seems like a good place. As any, Sean, we could obviously talk to you forever. you've got a ton of great stories and, and, a lot of experience that we'd love to just drag out of you. But, I guess we'll have to wait till the next time we see you at a conference and drag it out of you over a beer.

[01:18:51] **Sean:** Absolutely. That'd be great.

[01:18:52] **Adam:** Well, thank you so much for coming on tonight.

## [01:18:54] Patreon

[01:18:54] **Sean:** All right, well then, this episode of Working Code is brought to you by Auto Incrementing Primary Keys and listeners like you. If you're enjoying a show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:19:06] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks as usual to our top patrons, Monte and Giancarlo, you guys rock.

## [01:19:14] Thanks For Listening!

[01:19:14] **Adam:** we're gonna try to convince Sean to stick around a little bit and talk to us a little bit more in the after show.

[01:19:18] **Adam:** I don't know what we're gonna talk about, but it's definitely gonna be off topic. It's definitely gonna be fun. You're definitely gonna wanna hear it. And if you wanna do that, you're gonna have to go to patreon.com/working code pod, throw a few dollars our way, and you'll get, early access to new episodes, all the after shows, all 200 plus episodes.

[01:19:33] **Adam:** Brian Klaus, by the way, that was episode 37. Good memory, Ben. long, long time ago, like 200 plus episodes

[01:19:39] **Adam:** ago.

[01:19:40] **Adam:** anyway, that's gonna do it for us this week. We'll catch you next week. And until then. You gotta unmute yourself, Ben.

[01:19:48] **Ben:** Uh,

[01:19:48] **Ben:** sorry I didn't even have anything clear. I just said, remember folks, your heart matters.
