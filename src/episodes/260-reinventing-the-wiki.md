---
title: "260: Reinventing the Wiki"
description: "This week is about patterns for co-maintaining a personal wiki with an AI agent, and where its job ends and yours begins."
date: 2026-05-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/260-reinventing-the-wiki/id1544142288?i=1000769266931"></iframe>

What's the point of a personal wiki when AI agents have already read the entire internet? This week is about patterns for co-maintaining a personal wiki with an AI agent, and where its job ends and yours begins.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Karpathy's LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/260-reinventing-the-wiki.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Tim:** I feel like I- I'm experiencing, LLM amnesia ' cause I can't remember what I've done from day to day

[00:00:05] **Ben:** I was just literally telling my wife that this morning.

[00:00:08] I said, "I in in the morning, literally have no idea what I worked on yesterday."

[00:00:13] **Tim:** Exactly.

[00:00:14] **Ben:** And

[00:00:14] **Tim:** to ask Claude, " Search your memory and tell me what I worked on yesterday

[00:00:17]

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go. It is show number 260, and on today's show, imagine my face here real big in the thumbnail, red arrow pointing my f- both my hands pointing at Reinventing Wikis. what we're gonna talk about. Clickbait here. but first, as usual, we'll start with our triumphs and fails. Once again, it's just the guys.

[00:00:55] Carol is almost done moving halfway across the country.

[00:00:58] **Ben:** close

[00:00:59] **Adam:** she should, be with us next week, hopefully, so

[00:01:01] **Tim:** She's just like a couple hours away from me now. Maybe we'll go see her in Savannah

[00:01:05] **Adam:** Yeah. Well, so I guess, like, we should say it kind of hinges on her getting her stuff back, right? Like

[00:01:10] **Tim:** It's

[00:01:10] always a-- Oh, for her it's always a risk.

[00:01:13] **Adam:** So, Tim, I'm gonna come to you first. What do you got going on, my

## [00:01:15] Tim's Triumph: Automating Team Goals

[00:01:15] **Adam:** friend?

[00:01:16] **Tim:** So I'm going with a Triumph. I've been building... So I've inherited a whole bunch of new employees. I got a whole lot more direct reports. I was kinda chilling, you know, after we kinda wou-wound down the payment stuff and kinda moved that off a little bit, and I only had, like, three direct reports, and that was kinda nice.

[00:01:30] You know, just kept like one of the guys. Now I got a whole bunch more people, which I, I mean, that's fine. It, it's fine.building dashboards to... I'm trying to automate goals, right? So, you know, every corporation of any certain size has these goals and these K-KPIs and these metrics. They're supposed to be SMART goals, right? But it's like I don't, feel like I, m-maybe someone else in the company has, but I don't feel like I've ever really done it well. It's always been very much seat-of-the-pants, kinda like, "So your air, you know, your, your bug-to-ratio is, you but there's no way to measure exactly how many bug defects a person's introduced. And it's like, "Well, I feel like you did a good job. I haven't heard anybody complain, so let's give you an A on that." And, I mean, it's just kind of demotivating when you, like, s- go through all this work and so hard to s- these goals, but you don't ever create tools to measure it. so, of with AI, I'm so much easier now to be able to look at our Jira instances, Microsoft instances, all the MCPs that we have available to us now to build a really slick-looking, dashboard. And it's, been working on it three days. I'm still not done. I'm getting close to being done. Right now I'm running Impeccable on it. as we record, Impeccable's running and, making it look all pretty.

[00:02:49] **Ben:** Oh, that's that website you talked about last time, right?

[00:02:51] **Tim:** Impeccable. Yeah, it's, it's, it's absolutely fantastic. It just does such a good job of just giving an even though it's like it's just a local internal website that no one is gonna see, just to scroll the mouse over and, like, things kinda jiggle and you're like, "Oh, I know where my mouse is," right? like that's stuff that I would never, ever would've bothered with. But yeah. So at the end of this, I'm hoping that I'll have a dashboard that, you know, people can look at every day, every week, they can immediately see where are they at on their goals and

[00:03:21] **Adam:** Sure

[00:03:21] **Tim:** so that when they get into the re- you know, we do the review, I have confidence, they have confidence, they know I know exactly they are. And you can click and detail everything to say, "All right, well, my, this one's not green. Why is it not green?" And it'll tell you exactly why. It's like, you know, a sprint with, you know, 10 tickets. Y-Your aim was to close at least 80% of them, and you only closed 50%. So either you need to make these tickets smaller or find a way to get them done,

[00:03:51] **Adam:** Are you worried about running into Goodhart's law?

[00:03:54] Like, you know, when a measure becomes a target, it ceases to be a good measure

[00:03:58] **Tim:** No, because this measure was given to all of us. well, I didn't come up with this measure, so I'm going with,

[00:04:03] tell me what you measure and I will tell you how I act. if you have, ridiculous measures, don't, complain when I act ridiculous. I'm very much

[00:04:11] **Adam:** Something like that, yeah

[00:04:14] **Tim:** Yeah, so I mean, that, that... I mean, we've been given from on high, "Here's what we're measuring you by."

[00:04:17] I'm like, "Okay, I am building a tool that will measure exactly that, and if people wanna gamify the system, I am absolutely fine with that

[00:04:25] **Adam:** Okay. So just to clarify, it sounds like you're building the dashboard, but you didn't pick the metrics. So it's just,

[00:04:31] **Tim:** no

[00:04:31] **Adam:** yeah, you're just building observability for the things that you're being judged on so that, and, and that you're supposed to judge other people on. So

[00:04:38] **Tim:** exactly. So I,

[00:04:40] **Adam:** Yeah,

[00:04:40] **Tim:** fact, I, the, the page actually has, so it has my goals as I'm a director, so it's like

[00:04:45] **Adam:** Mm-hmm.

[00:04:45] **Tim:** director-level goals, so everyone my teams know here's Tim's goals, and they see everyone else's goals, and they're all pretty much the same across the board for, for individual contributors. And so they see all their goals, and they see each other's goals, so there's no surprise. We get into the, you know, quarterly review and you're like, you know, we had one-on-ones, you know, every day, every week this year, and, you know, I told you, you need to start closing these tickets either faster or size them correctly so you can close

[00:05:12] **Adam:** Yeah

[00:05:12] **Tim:** faster. not a surprise. So

[00:05:16] **Adam:** Maybe that's something, a topic we should revisit, like just h- not hacking around Goodhart's law, but just like different ways to measure success while keeping that in mind, right?

[00:05:28] **Tim:** that, but it's like, I'll be honest, I think the measurements that we're given, honestly, even if you gamify them, you're still gonna be doing the right things to get where we want to

[00:05:39] **Adam:** I don't know, man. Like, if the, if the measure is... Like, I, I'm gonna use this because it was the example you gave, but it, i- if the measure is, you know, you were supposed to close at least 80% of the tickets for every sprint, then they're-- the gamification is they're just gonna make the tickets so small that they're, they can close 80% on day one of the sprint, and then, you know, maybe work's not getting done at a satisfactory level, but they're meeting their goals

[00:06:02] **Tim:** but then you have other goals that say you need to estimate it properly. And so it's like you can't say, "I'm gonna have, you know, 50 tickets that are gonna only take, you know, hours in a 40-hour week." the sprint. We have to-- There's other goals that say estimation, where if you say you're gonna fit this much in, it should take that long.

[00:06:24] **Adam:** Gotcha

[00:06:25] **Tim:** one goal that you say you gamify one, you, you might

[00:06:29] **Adam:** Right

[00:06:32] **Tim:** a topic here, but we're not talking about that today. So

[00:06:34] **Adam:** Yeah, yeah, yeah

[00:06:35] **Tim:** will, I will, I will get off that. I, I wanna do a personal triumph. I did put together my Blackstone grill that I got for anniversary, and it's fantastic.

[00:06:41] I love the thing. It's new favorite toy.

[00:06:44] **Adam:** Congrats

[00:06:44] **Ben:** before, before, we get off it though, I just wanted to say thing that I feel like, because we're talking about tickets, that I've heard a number of people say lately, which is again, one of these things that I just don't connect with at all. People will say something to the effect of, "In the age of AI, do we even need tickets anymore?

[00:07:01] Like, what's the point of having tickets?" And I'm like, "What do you... How do you track anything you do?"

[00:07:08] **Adam:** Right

[00:07:09] **Ben:** Like, what? What does that even mean?

[00:07:11] **Tim:** I, think your, I think your AI should create their own tickets and estimate them and close them, and you measure that

[00:07:17] **Adam:** Yeah. It's just an ignorant comment. Like people who tell you like, "Oh, I work by myself, so I don't need to use version control."

[00:07:22] **Ben:** Right.

[00:07:23] **Tim:** Mm-hmm.

[00:07:24] **Adam:** then you just don't understand the point

[00:07:26] **Tim:** Exactly. that's me, Adam

## [00:07:28] Adam's Triumph: Migrating Off the CFML Monolith

[00:07:28] **Tim:** Butchko, man

[00:07:30] **Adam:** Well, I'm also gonna go with the Triumph.

[00:07:31] **Tim:** What?

[00:07:32] **Adam:** yeah. So,

[00:07:33] **Ben:** yeah

[00:07:34] **Adam:** over the years, we have slowly migrated things away from our CFML monolith when they became problematic, right? You know, as we sign more customers, and we have more users, and the, the different servers would just struggle to keep up with background jobs a- and getting those done while also leaving resources available for end users.

[00:07:58] when we would run into situations like that, we would usually migrate that background job off to be a Lambda function or, you know... That, that tends to be where 99% of them ended up. Occasionally, we'd architect something slightly differently. But, we had one remaining, and that was our online directory.

[00:08:16] So we use Elasticsearch to be able to... You know, it's like you go to your alma mater's website, and you say, "I wanna search for other people that graduated the same as m- same year as me that, also have a software engineering degree that live within 50 miles of this ZIP code," right? Something like that.

[00:08:30] Like, maybe I wanna get together with some people or something.

[00:08:32] **Tim:** Are you, are you doxing them? What's going on?

[00:08:36] **Adam:** well, I mean, you know, it's like, you know, maybe I have a job opportunity. I'm looking for people who went to my school that have the same degree that live close enough that I'd hire them

[00:08:44] **Ben:** a small dog puppy playgroup

[00:08:48] **Adam:** Yeah, you know, anything like that.

[00:08:50] **Tim:** I

[00:08:51] **Adam:** so y- but you know what I'm talking about, like, a, just a directory. A- and it's all, it's all above board, right? It's, it's opt-in, and you choose how much information you wanna share and all that. Anyway,

[00:09:01] the difficulty is that they have so much data that we have to, comb through to, to get it done, that it just takes-- We-- It, like, runs on a, on a counter, right? It's a cron job, and it runs, like, every 15 minutes all day long for every customer, and they're staggered, so they're not all running at the exact same time.

[00:09:17] But it's, they're all basically running all day long with a minute or two break between each one.and that was the last remaining job, background job that was running on CFML. And, you know, as we have spun up more customers, it just becomes more and more problematic. And so finally, I've got that, moved off of CFML onto our new TypeScript SvelteKit stack.

[00:09:40] and it has... I mean, today was the day I went to production, but so far, it has been fantastic, right? It's been faster. It's smarter, right? So, like, while I was in the process of migrating it, I was able to add some additional intelligent stuff to it. Like, for example, I added backpressure. So we're generating a file of NDJSON, new line delimited JSON, where we're sending all these updates up to Elasticsearch.

[00:10:04] and right now our bottleneck is Elasticsearch itself, like, consuming these files.

[00:10:10] **Ben:** Yeah.

[00:10:10] **Adam:** Yeah, the ingestion of these files. and so what I have it... a- and I've tried, you know, I tried multiple different approaches, and basically it came down to Only ever single threading the ingestion, right? I tried parallelizing the ingestion, and it just couldn't keep up, and that very quickly spun out of control and, and everything broke down.

[00:10:32] So single upload at a time, and then I ha- I also built it so there's a single queued file at a time, right? So as soon as that one upload is done, then there's always gonna be a file waiting. But then once there's a file in the process of uploading and a file queued, then it stops. Like, it just waits until the queue is empty because that queued file is now uploading.

[00:10:55] Now the queue is empty, and now it can go generate the next file. and that helps keep the CPU down on the app server and whatever. but yeah, so it's smarter, it's more memory efficient. and the, the last two things are things that would be particularly difficult on our CFML setup. one is that it has access to the database read replica, right?

[00:11:15] So we're using MySQL clustered, and there's a read node and a write node. And because of the way CFML data sources work, we just only ever had the, the write node hooked up as a data source because, you know, the trouble you'd have to go through to get a, a write query versus a read query connection would be too much to worry about.

[00:11:37] and so we only ever used the write, node from CFML.but now on TypeScript, it's just, it's easier to get a connection for either one. and then, what was the last thing? Oh, it runs detached from the triggering HTTP request, right? So coming from the CFML world, you, you make an HTTP request to trigger this job to run, and then it takes sometimes, like, 10 minutes to run, and that request is just sitting there spinning and spinning and spinning, waiting 10 minutes to get its, like, two character okay response.

[00:12:09] and now it triggers, you know, it's using Node, its promises, and it just triggers this promise to go run off in the background, doesn't wait for it, and then returns a status reply. And it's smart. It's using locking and all that kind of stuff to, like, prevent concurrent runs when we only want one at a time, that sort of thing.

[00:12:28] But like I said, today is launch day, and we had launched at midday, and so far so good, knocking on wood over here.

[00:12:34] **Ben:** sorry if you mentioned this earlier and I missed it, but the, process to generate the NDJSON files that's in-house but is Elasticsearch, is that an Amazon-hosted service or that's like an on an EC2 instance?

[00:12:48] **Adam:** So the files being generated to upload to Elasticsearch are on the app servers, writing to the temp folder on the app server. And then the Elasticsearch instance is Amazon hosted, ES. I guess they call theirs, like, OpenSearch now, but we actually started before they forked off their own OpenSearch.

[00:13:08] so I think that...

[00:13:08] **Ben:** that drama

[00:13:10] **Adam:** Yeah. It's just like everything else, Redis and MySQL and everything else. They, they fork their own version of it for sometimes good reasons, sometimes less good reasons. but yeah. So it, it's, you know, it's still all within our, AWS VPC. It never, like, leaves our little subnet, but, it's separate physical instances

[00:13:30] **Ben:** I remember,

[00:13:31] when I used to do a lot of work for law firms way back in the day, we were using the CF index tag, which I don't even know what that was using under the hood. S- Solr?

[00:13:41] **Adam:** Yeah, Apache Solr and then Lucene later

[00:13:43] **Tim:** Mm-hmm.

[00:13:44] **Ben:** but the, the thing that we always ran into was the lawyering stuff was always this mishmash of data types.

[00:13:51] Like half of it, I'd say like 70% of it was all database driven. It was, you know, like profiles and, and cases. then there was like 30% was just random pages on the website that we still had to get into the index, and then PDF documents we had to feed into the index, and that was always such the frustrating part. I had always wished that there was some sort of just... Like I think you, I think Google used to, I don't know if they sell this anymore, but they used to sell a search indexing box that you could just host in your own rack, and I think it would just kind of spider your site the way that the Google bot would spider, and then you could use that.

[00:14:28] And I was like, "Oh, that's the dream." I think they were like stupid expensive

[00:14:33] **Adam:** Yeah. I, I worked at w- at least one shop that had that, and yes, to all of the above. It was stupid expensive, it was stupid simple to set up, and yeah. And it worked just like Google

[00:14:45] **Ben:** Well, very cool

[00:14:46] **Adam:** So that's what I got going on. How about you,

## [00:14:47] Ben's Triumph: A Headphone-Free Weekend

[00:14:47] **Adam:** Ben?

[00:14:49] **Ben:** I will also close us out with the third triumph of the day here. And, yeah, I... My triumph is, is not tech-related at all really, although I guess, I guess it's tech adjacent in a way. typically, when I'm out about, or even when I'm up walking around the house or I'm brushing my teeth or anything, I have my headphones in, and I'm probably listening to some sort of a podcast. I just like having an onslaught of information going into my head. I think half of it is I just like to be distracted so that the voices don't get so crazy,

[00:15:23] **Adam:** Mm-hmm.

[00:15:24] **Ben:** the other half is, like, I actually just wanna have my finger on the pulse a little bit. You know, if someone mentions something, part of me gets very excited if I at least kinda know what they're talking about.and Saturday and Sunday here were really, really beautiful days. Like, it got up into the 80s, but it was... Which is kinda hot for me, but it also had a beautiful breeze, and it was just lovely out, and I ended up going for a long walk with no headphones, and it was, like, the most relaxed I have felt, I think, since I can remember.

[00:15:56] **Tim:** Hmm.

[00:15:56] **Ben:** and I think that my attempt to constantly distract myself almost ruined my ability to just relax, and, what I wanna try to do now is

[00:16:09] **Tim:** Mushrooms

[00:16:10] **Ben:** well, yes, andI would like to try to make my weekends a headphone-free period when I'm out of the house. When I'm out of the house. If I'm home and I'm doing stuff at, at the house, that's fine, headphones on.if I'm in the car, I feel like maybe I can continue to listen. But if I'm just, like, out on the weekends taking a walk, wanna use that as an opportunity to connect back with the surroundings. you know, no holds barred during the week.

[00:16:42] **Tim:** Touch grass

[00:16:43] **Ben:** exactly. I wanna touch grass more. I wanna...

[00:16:46] **Adam:** With your ears?

[00:16:48] **Ben:** With my whole body.

[00:16:50] **Tim:** yeah

[00:16:50] **Adam:** Sir, it's not that kind of an establishment

[00:16:54] **Tim:** Please don't let

[00:16:54] **Ben:** know

[00:16:55] **Tim:** u- let this unlock something in me

[00:16:58] **Ben:** It was just really weird. So, okay, on, on Saturday and Sunday I did the exact same walk. There's this bridge that goes across the Hudson River here called Walkway Over the Hudson. It's in Poughkeepsie, and it's like a one-mile bridge that's... Yeah, I think it used to be a, a, a trail, or like a, a railway, and they converted it into a walking path, I don't know, like 20 years ago or something. And Saturday I did it, and typically when I'm on the bridge, I just listen to my music, 'cause there's people around and it's too distracting to listen to a podcast 'cause I'm just looking at stuff, so I'm not really paying attention. But Saturday I did it with music and I, and I love it. I'm, you know, bopping around, I'm smiling, I'm, you know, giving trigger fingers at people and like, you know, d- doing fun dad stuff.and then on Sunday I, decided to do it without headphones, and at first I was like, "Oh, this is so ridiculously quiet." And like 30 seconds later, it just felt wonderful, and, continued to be wonderful the entire, walk. And I kept thinking, I'm like, "Any moment I'm gonna get bored," and I just never got bored. And I like... Even if I didn't have anything going on in my head, like if I was just staring off at some seagull floating in the breeze, I loved it. It was great

[00:18:06] **Tim:** That is so cool. I mean, it's, it's, it's really hard these days just to be in the moment

[00:18:11] **Ben:** Yeah.

[00:18:11] **Adam:** I, I, I'm right there with you, Ben. I, I feel like I have, I don't know if it's a dopamine addiction or just, an attention addiction or something. Like, I need to have my attention on, s- like, focused on something. I can't just let my mind wander and be in the silence. Every now and then I will, you know, like, maybe if I'm, if my ears are tired from constant podcasts and, and books and stuff, then I'll like, you know, do a car ride in, like, literal silence, just road noise.

[00:18:41] But short of that... And, I mean, like, when I go on walks with my wife or stuff, we'll...

[00:18:45] **Ben:** Yeah

[00:18:46] **Adam:** I'm obviously not, but

[00:18:48] **Tim:** It's, it's funny. So think this like and everything comes back to AI these days. Our corporate like parent, like the big, big parent is pushing down through HR program to talk about AI burnout, which is funny 'cause at the same time they are pushing us extremely hard to use AI, but at the same time it's like recognizing it's...

[00:19:11] And, and I get it. It's like I've talked to different people in our organization, and even like in their personal life, they're like using AI all the time, and, and I know I do too. like if I f- I feel guilty if I'm not burning tokens. I think I mentioned that before.

[00:19:26] **Adam:** Yeah

[00:19:26] **Tim:** If I'm not burning tokens and I haven't hit the wall, I'm like, "I cannot let those tokens go to waste."

[00:19:32] And yeah, it's, Yeah, so good for you, Ben, for, for disconnecting. And I,

[00:19:36] **Ben:** What?

[00:19:39] **Tim:** and, you should too

[00:19:41] **Ben:** It's funny too because,

[00:19:42] o- on Sunday, I, I walk across the bridge and then I walk back. So I, I think it's, like, roughly a mile each way. And there was a moment on the way back, I'm, like, halfway across the bridge, and the sun is kind of on my back, which is, you know, better than it being in my face for me personally, and all of a sudden there's this beautiful breeze.

[00:20:00] And I was... I thought to myself, like, "This is a perfect moment." And then I thought to myself, "I need to tell someone about this." And I, like, I literally started to type a text message in my family chat, and

[00:20:12] **Tim:** Oh.

[00:20:13] **Ben:** doing? Just, like, enjoy it."

[00:20:15] **Tim:** Yeah.

[00:20:16] **Adam:** Yeah

[00:20:16] **Tim:** Yeah.

[00:20:16] **Ben:** Just be in the moment. You don't have to tell anyone that you're having a perfect moment.

[00:20:20] Just have the perfect moment

[00:20:23] **Tim:** It's like that scene in Project Hail Mary where he's like in the stream of the the ship and it's like

[00:20:29] **Adam:** Mm.

[00:20:29] **Tim:** all the red, and he's like... Rocky's like, "What are you doing?" "I'm having a moment."

[00:20:33] **Ben:** Yeah. Exactly. It was a maze

[00:20:38] **Tim:** Amaze amaze

[00:20:40] **Ben:** Three triumphs, bros Pretty exciting. And let's, I, I say we give Carol an honorary triumph for moving across country.

[00:20:48] **Adam:** Pending getting her stuff

[00:20:49] **Ben:** pending

[00:20:51] **Tim:** Pending, yeah. At least she's near the ocean, so. Savannah's beautiful. If you've ne- if you guys have never been to Savannah, it is one of the most beautiful cities in America. It feels European. It's very cool

[00:21:05] **Ben:** I feel like maybe that's where there's a, there's a... Me and my wife were really big into home renovation reality shows for a while, and I feel like small town...

[00:21:13] **Tim:** Georgia

[00:21:14] **Ben:** I think Savannah might have one or two specifically

[00:21:18] **Tim:** it's a, it's a beaut- it was, it was, it's the first planned city in the United States. So Oglethorpe, they came over. It's, it's everything's in squares, planned gardens and parks all everywhere,

[00:21:28] **Ben:** Oh, nice

[00:21:29] **Tim:** It's really, really, really nice. Nothing, nothing else like it in Georgia. So if you guys wanna visit a really cool place, go see Savannah. And the, the Spanish moss hanging off the trees along the sides of the

[00:21:40] **Ben:** Oh, that's cool

[00:21:41] **Tim:** very, very cool. If you saw, what, Midnight in the Garden of Good and Evil, that movie, it was all based in Savannah. Filmed in Savannah too.

[00:21:48] we talking about?

## [00:21:49] Reinventing the Wiki: The LLM Wiki Pattern

[00:21:49] **Adam:** Uh, well, so we were gonna talk about reinventing the wiki, and, I kinda wanted Ben to, to kinda intro this. You-- It was your original idea to talk about this, so, like, let's give you

[00:21:58] **Ben:** Sure. So last week I went to an in-person meetup, which was very exciting, the two guys speaking, they were sort of co-speaking together. it wasn't about anything, like, really articulated. It was basically they love AI, they use OpenClaw, they use agents to do a lot of stuff, and they were walking us through how they use an... I think it was like a VM instance to run the OpenClaw stuff in a really isolated environment, and how they were running it through Telegram and all this stuff. And so they're just, you know, talking about all this AI stuff, and then, like, the last five minutes, one of the guys was, "Oh, and one of the things I wanted to show you was I use this..." I think he called it an LLM wiki, and it was some pattern where I think it was Obsidian. I guess it's like a note-taking app historically. He, he uses a AI agent to manage this wiki that he's building. I think it was lo- I don't know if it was locally on his computer or it's on Git- I think maybe it's posted to GitHub, I can't remember. it creates this sort of interconnected set of pages. I mean, that's what a wiki is. And it, he may have called it his second brain. You know, I've heard people use that phrase before. But it was like any idea that he has about things he's read or researched or, like, he'll take, like, a YouTube transcript or he'll ask the agent to go grab this transcript from this YouTube link and integrate it into the wiki and I, I, I don't know.

[00:23:33] So it was interesting, but my thought was like, isn't that just what the World Wide Web is? Like,

[00:23:39] **Tim:** Great

[00:23:40] **Ben:** if, if you're, if you have AI agents that have been, number crunching the entire web into this trillion-parameter weighted model, what... I didn't understand the, the why you would then have your own wiki to do that kind of stuff. I will say, full disclosure, I'm just, like, not a big note-taking person historically. I have a pad of paper that I scratch some notes on sometimes, and I have a, board I occasionally throw a sentence or a link into if it's something I want to remember for later. But, like, that's it.

[00:24:13] That's the extent of my note-taking. So foreign to me. And when I mentioned it in Discord, Adam

[00:24:20] **Adam:** Mm-hmm. Mm. Yes, feelings, definitely.

[00:24:25] **Tim:** All right,

[00:24:25] **Adam:** I,

[00:24:25] **Tim:** Okay

[00:24:26] **Adam:** did you, did you say specifically who these two people were? 'Cause you, you'd thrown out the name Karpathy earlier. I don't know if that was

[00:24:32] **Ben:** mentioned that it was based on an idea that Andrej Karpathy, Kar- Ka- I don't know however you pronounce it. The

[00:24:38] **Adam:** Yeah

[00:24:38] **Ben:** coined the term vibe coding,

[00:24:40] **Adam:** Right

[00:24:44] **Ben:** then he went to xAI, and I think he just went to work at Anthropic, like yesterday or something.

[00:24:50] **Adam:** Oh, really? Okay

[00:24:51] **Ben:** I don't know. I honestly know very little about him other than what other people mention, but he's kind of a big wig in the AI world and keeps coming up with these ideas that seem to get a lot of traction

[00:25:02] **Adam:** for me, this all started with a GitHub gist, right? And we'll, we'll link it in the show notes. It's a, I guess, pretty widely known gist at this point. It's very long. It's got a lot of comments on it.and it's just about, you know, I mean, the title of it is LLM Wiki.

[00:25:17] and i-it's, it... So the line under that says, "A pattern for building personal knowledge bases using LLMs." And when I read that, that clicked for me, and there were two things that I wanted to do with that, like, immediately. And one of them I'm actually already doing, and the other I've kind of started writing some notes, but the, the, the second one for me is so intensely personal that I will never connect it to or give access to that data to a, an internet connected

## [00:25:45] A Private Offline Diary With a Local LLM

[00:25:45] **Adam:** model, right?

[00:25:46] So the... And I'll just get that one out of the way 'cause that's gonna be easier to discuss, which is, I wanna have, like, a personal diary, but it's like my medical symptoms and the medications that I'm taking and when things change, right? Like, well, okay, today my doctor changed me from this dosage to this dosage.

[00:26:01] That way I can in a month go, "Oh, I feel like this medication might have had this effect." Like, when did it switch and, and did that line up with my, my symptoms that I've been describing? That sort of thing, right? Or, you know, maybe it's, mental health stuff, or maybe it's when I bought my car or, you know, whatever personal details.

[00:26:17] But I, I wanna have it in local files and be able to like search it and sort of cross-link at query time, not at writing time, using a local LLM to do that. Does that make sense?

[00:26:30] **Ben:** That makes a tremendous amount of sense. I mean,

[00:26:33] **Adam:** Yeah

[00:26:33] **Ben:** if I can relate to it in the most ridiculous way,

[00:26:36] **Adam:** Mm-hmm.

[00:26:37] **Ben:** our dog had a very sensitive stomach, and so she was just like constantly and seemingly randomly getting diarrhea.

[00:26:46] **Adam:** Yeah

[00:26:46] **Ben:** So I had always wanted to have some sort of a food journal for her where I could say, "Oh, we ended up giving her sweet potato on Tuesday, and then she had diarrhea on Thursday.

[00:26:55] So maybe it was the sweet potato, but maybe it was the sweet potato plus whatever we gave her on Wednesday."

[00:27:00] **Adam:** Right.

[00:27:00] **Ben:** Yeah,

[00:27:00] **Adam:** Now, okay, so perfect. That's a, that's a great example except just swap out the dog for yourself and, like, would you wanna give that information to OpenAI, right? No, not at all,

[00:27:10] **Tim:** OpenAI is like, "Adam, Adam really poops a lot. What's going on?"

[00:27:14] **Adam:** That's just, public domain knowledge. It was trained on that. But, yeah, so that's, that's my, like, my local model usage thing is like I, I, I just kinda wanna have a diary and be able to point the thing at it and say like, you know, "Find information about this topic," you know, "What's the, what's the through line here?"

[00:27:34] **Tim:** t-technical

[00:27:35] quest. So w- I mean, what are you using for your local LLM?

[00:27:39] **Adam:** Nothing yet. So that, th- I have just barely started the, like, diary files, right? I'm just writing markdown files and they're, the file names are the date, right? So I'm just, like, one file per day, and it's like a, a stream of consciousness, like

[00:27:52] **Tim:** I'm actually running a local LLM to do the Showbot. I'm like, I could actually just shift it not... Obviously I'm not, my Showbot's not gonna tell you, tell you about my

[00:28:02] **Adam:** So before we started before-- I'm just gonna walk right past that. I'm

[00:28:07] **Tim:** You're not gonna, gonna... No, that's okay

[00:28:09] **Adam:** Just, before we started recording, y- we were talking and, and you guys pointed out I have a laptop sitting on the couch in my office here. it's still in the box. I haven't even un-unboxed it yet, So I'm recording this on my M1 MacBook Pro, And the one in the box there is an M5, like max, the, the top-end spec, like 128 gigs of RAM, the, the top-end CPU, all that. that was one of the things that I had in mind when I picked that one out, was like, "Okay, this is gonna be the opportunity to test the performance of local LLMs, completely disconnected from the internet."

[00:28:43] **Tim:** And, like, m-making it that way, making it completely disconnected kind of makes me feel a little bit better about the idea of using s- one of these maybe open-weight Chinese-sourced models like a Qwen or whatever. Qwen's

[00:28:57] **Adam:** so

[00:28:58] **Tim:** That's what

[00:28:58] **Adam:** yeah. So

[00:28:59] **Tim:** think I'm using that

[00:29:00] **Adam:** it's something I'm looking forward to experimenting with, but, it's just, the bo- the, the...

[00:29:04] This is a brand-new laptop, and it's been sitting on my couch for a week because I... it's just not a good time for me to be switching machines, so

[00:29:12] **Tim:** your new EV, so

[00:29:14] **Adam:** driving and, and dealing with work, and we just got a lot of stuff going on. So not a good time. so but that's coming. but then the other usage that I actually am using it for,I, I would say Obsidian is not required.

[00:29:27] Obsidian is a fine interface if you want to be hands-on in the markdown files. Like, if you want to build a set of interconnected markdown files, Obsidian is a nice UI for browsing and writing those files

[00:29:41] **Ben:** And just half for my understanding and half for the listener's understanding, Obsidian is a note-taking app, it is powered, like, exclusively by markdown files on your local computer. Is that the idea?

[00:29:56] **Adam:** I think so. I'd say that's a fairly accurate representation

[00:30:00] **Ben:** As opposed to something like Notion, where Notion is a note-taking app, but I think it's, know,

[00:30:05] **Adam:** Notion is pretty much cloud only. Yeah

[00:30:06] **Tim:** more than that 'cause it, it doesn't it kinda like interconnect data nodes of, of things? 'Cause my son used it. He's on a, like a... He's a moderator on, an art dojo where they do these. They have... Everyone creates their own, like, anime characters, and they do their own drawings, and they have battles, and he's, like, become the historian

[00:30:26] **Ben:** That's cool

[00:30:27] **Tim:** he can build this, like, interconnected web. He showed it to me. It was actually really pretty amazing. It was more than note-taking. It was

[00:30:33] **Adam:** It, yeah,

[00:30:33] **Tim:** it was sh-

[00:30:34] **Adam:** there's a pretty healthy ecosystem of plugins for it, and you can do a lot of stuff. There's like to-do systems built on top of it and database stuff

[00:30:42] **Tim:** this is almost like, I, I can

[00:30:44] never say this word, Graphle, Graph... What's

[00:30:46] **Adam:** GraphQL.

[00:30:48] **Tim:** thank you. I can

[00:30:49] **Adam:** It's just the word graph and two letters after it. GraphQL

[00:30:53] **Ben:** by markdown files more or less, which

[00:30:56] **Adam:** Yes.

[00:30:56] **Ben:** of LLMs essentially

[00:30:58] **Adam:** Mm-hmm. Yeah, and I imagine it probably has some sort of, like, internal indexing, like database indexing, where it, like, you know, stores metadata about your files, in its own little local probably SQLite database or whatever. But that's it.

[00:31:12] At, at its core, it's a, it's a UI on top of a pile of Markdown files with some s- some sugar sprinkled on

## [00:31:18] Ingesting Support Tickets Into a Product Wiki

[00:31:18] **Adam:** top.

[00:31:19] **Ben:** So what are you using it for?

[00:31:21] **Adam:** like I said, the, the first line of that Gist is, "A pattern for building personal knowledge bases using LLM." So what I have done is I, I used this Gist, and I fed it into an LLM, and I said, "I wanna build a tool that's basically like my own internal documentation for our products." so it's, it's like the documentation, except it's only meant for me to, A, write to it, and B, query it using an LLM.

[00:31:49] I want it to be e-eventually sort of automated, but right now it's just kind of a manual step that I take between I receive a ticket and I reply to a ticket. And I'd like to get to the point where, you know, I receive a ticket, and that's automatically forwarded to the LLM that then says, "Can I answer this based on the information that I already have?

[00:32:09] and if so, here's the answer." And I can look at that answer and go, "Okay, yeah, that r- that helps me remember that yes, that is in fact how things work," and I can just copy and paste that answer, maybe modify it so it sounds like it's coming from me instead of an LLM, and then reply to the ticket, right?

[00:32:24] And a lot of times there's knowledge that we use in res- replying to tickets that is not something we would post on our documentation, right? like, sometimes it's just too inane. I got a ticket today that a lady was asking like, A, why do I have to log into the app every day?"

[00:32:40] And then, "B, why did I get a password expired today?" A-and the answers were, "Your session time's out after an hour, that's why you have to log in every day, and your password, quote-unquote, expired today because you actually haven't been logging into our system for more than 90 days. You've been logging into other things and thinking that counts as logging into us, and so your, your, you, you didn't get password expired, you got...

[00:33:04] Your p- your account was deactivated because of 90 days of inactivity."

[00:33:08] That kind of information is useful to be able to automatically generate, but it's not something we would just post in the public facing documentation. And even if it was there, the likelihood of the users reading that and paying attention to it and remembering it is basically zero.

[00:33:21] So hopefully you can see like that's an example of a good reason t-to be able to automate that sort of information lookup.I don't have anything like crawling the code to document stuff about the app, but one thing that I do have is at this moment, very elaborate, but I'm slowly over time making it less elaborate and more sort of like streamlined automated, where I'm going through the history of all of our support tickets and ingesting those into the wiki.

[00:33:49] So it's, it's going through the thousands upon thousands of support tickets that we've already answered and closed in our history

[00:33:55] **Ben:** Oh,

[00:33:55] **Adam:** says, "Okay, Did this turn out to be like a data issue and something that I can skip or ignore," right? Like if this was, oh yeah, the data was wrong, or oh yeah, they just needed me to flip this switch on your account.

[00:34:06] Like that's not something that needs to be documented, right? So we call all of that out from the knowledge base. This is not a question that can an- can be answered. This is like a, "Please do this." "Okay, I've done it." Right? We don't need to worry about any of that. Granting you a role, that sort of thing.and then what's left is like, okay, is this a, a clear this was the question, this was the answer, and if it's able to do that, then it documents it, and it gives citations, right?

[00:34:30] It like links to the original ticket, in case we ever wanna go, "Okay, well, where did this answer come from and, and who gave it?" sort of thing.

[00:34:38] **Ben:** So let, let me just in- interject for a second

[00:34:40] **Adam:** yeah

[00:34:41] **Ben:** like building this, but it is actually something that could be useful at a team level. You know, you... I could... It, it's not hard to imagine a, a scenario where an in- a different team member is, like, on ticket support day, like, on different days of the week,

[00:34:57] **Adam:** Yeah

[00:34:57] **Ben:** everybody might have to have access to something like this. Is there a way that you can build this that is maybe not distributed is the right word, but, like, the stuff that you put in it is stuff that your teammates can see and vice versa?

[00:35:12] **Adam:** Oh yeah, absolutely. I mean, all you would have to do is, make the... I mean, again, it's just a pile of markdown files that the LLM can then go search. Right, yeah, make it a Git repository and then, like, have a s- have a cron job on everybody's machine that does a Git pull once a day or something, you know?

## [00:35:28] RAG, Context Windows, and Fuzzy Retrieval

[00:35:28] **Adam:** and

[00:35:30] **Ben:** Well, it's interesting too. Sorry, I don't mean to... I'm just letting my mind wander as you're talking here.

[00:35:34] **Tim:** topic? So

[00:35:36] **Ben:** Well, so, so when Tim was talking about making his, chatbot thing for the Discord, he was talking about how it had to run in, in kind of separate phases, where one is it-- I'm gonna

[00:35:48] **Tim:** RAG

[00:35:49] **Ben:** But yeah, like it had to create a vector embedding to say, "This is the thing I'm looking up." then like it did a light query into something just to like find it, and then it was... Then it would like read in the more meaty content to get the like into the context window so it could give you like actual meaningful results.when you're building this LLM wiki, eventually it's more information that can fit in the context window. You can't just be like, "Hey, read the entire wiki, and then I'm gonna ask you questions."

[00:36:19] **Adam:** Right

[00:36:19] **Tim:** RAG is for, right? The RAG does a search first and gives you enough answer to the search, and then the,

[00:36:25] **Ben:** Right. Well, that's, that's where I'm going. I wanna

[00:36:27] **Tim:** feeds the LLM.

[00:36:29] **Adam:** Mm-hmm.

[00:36:29] **Tim:** So it's basically generating a prompt for the LLM, and the LLM, you know, finds more context and gives you a better answer. That's g- that's kinda how that chatbot works, is like someone puts in a question about a show, the RAG looks up the very basic boring facts, it feeds that to the LLM, then the LLM expands on it

[00:36:47] **Adam:** Do you wanna define what RAG means or, or the acronym?

[00:36:51] **Tim:** forget

[00:36:52] **Adam:** Retrieval augmented generation.

[00:36:54] **Tim:** Thank you

[00:36:55] **Ben:** But I mean, ultimately that just means I'm taking some stuff and I'm jamming it into the context window,

[00:37:01] **Adam:** Yes and no. I mean, th- so think about it this way. Instead of I have to load the entire wiki into memory and then I'll be able to answer any question about it, it is, "Oh, Ben is asking about event registration, so let me do a quick grep across the entire wiki for the word event and the word registration," and any ti- any file that where both of those words appear is probably a high signal file for me to read.

[00:37:29] And a- anywhere, any file where only one of them appears may be relevant, but less so, and any word where, or any file where none of those words appear is probably not important to answer the question. And so it helps it

[00:37:41] **Ben:** This

[00:37:41] **Adam:** it down.

[00:37:42] **Ben:** feels like the most exciting part of AI, is its ability to, take really fuzzy English and produce

[00:37:50] **Adam:** Mm-hmm.

[00:37:50] **Ben:** a deterministic result, but like, I could imagine a world where I have a JSON payload or like a YAML file where it says like, "This directory is for human resources," and like tags with, you know, birthdays,

[00:38:06] **Adam:** Mm-hmm

[00:38:07] **Ben:** company holidays, vacation time, paid leave, maternity leave.

[00:38:11] And like, "This directory is for support tickets," and like tagged with, you know, XYZ.

[00:38:16] **Adam:** Yeah

[00:38:16] **Ben:** And you could have like, oh, someone asked this question, like someone typed into the little chat GUI, "Hey, when is the next company holiday?" And, and you, you know, run that against the YAML file and it says, "Oh, it's probably this entry."

[00:38:29] And then you can go and scan that directory or do whatever. And like that to me is like the most exciting thing, where it's like you can take something that has actual constraints, but that kind of last mile decision-making is really complicated and very fuzzy, and like the LLMs feel like they're really, really good at that kind of stuff.

[00:38:48] **Adam:** Mm-hmm.

[00:38:49] **Tim:** So I'm looking at the gist that you talked about. And, it's funny, I, I'm actually kind of doing this. I didn't think of it as a wiki, but for instance, so, for the LLMs, context is very important. So I have s- certain folders.

[00:39:04] They're not code folders. so particularly for like my team, where I'm managing my team, I have a, a, like a team folder, and they're named by... Each team has a certain name. So we like have a team called Layer. So I have a Layer team folder, and I put just documents in that folder, like email, like copies of emails, copies of copies of, messages that we, we shared on Teams.

[00:39:28] Just I have it, you know, and I have the AI go and grab it 'cause we have MCPs to go grab all that stuff. And it, it just lives there in that folder. And because it's in that folder, and I've told Claude what the context is for that folder and what each of those files are, I can go in there and just ask a question. Like, like, you know, "What is, what is so-and-so's top three priorities for this week?" And it just says, you know, "Tim should be working on X, Y, and Z." I'm like, "Okay, cool." Then, so our one-on-one's

[00:39:58] **Ben:** Hmm.

[00:39:59] **Tim:** how is one A, B, and C?" But I don't think of it as a wiki 'cause I don't generate like a page, but maybe I could. I don't know. Th- this is a interesting idea, but I feel like I'm already kind of doing this. Also like competitive analysis. So if you're like in sales and marketing, and you like build, they call them battle cards. You guys heard about this?

[00:40:17] **Adam:** Mm-mm.

[00:40:18] **Tim:** So battle cards is like you basically

[00:40:20] **Adam:** Pokemon?

[00:40:21] **Tim:** Yeah, exactly. It's so cool.

[00:40:23] Gotta catch them all. No. It's opposition research, basically. So

[00:40:26] **Adam:** Okay

[00:40:26] **Tim:** you see who are the people that you tend to run into when you're fighting over customers, and you build battle cards. And so, an ongoing process. You're like grabbing press releases, you're grabbing information. They update their website with a new thing, and you're constantly scraping that.

[00:40:43] So I have folders for that, and the LLM kinda does that and does c- competitive analysis, of like, you know, if you run into someone that's s- you know, go to a conference, and they say, "Oh, we're, we're thinking about going with X." And you're like, "Well, competitor X is good in this, this, and this, but here's the cons,

[00:41:02] **Ben:** Hmm.

[00:41:03] **Tim:** And you have that already.

[00:41:04] **Adam:** Yeah, so traditionally that would just be, knowledge stored in the head of your best personal or your best one or two salespeople, right?

[00:41:14] And, if they're not the ones that took the call or made that, that site visit, then they may not make the sale. But if the best s-salesperson was there, then they would.

[00:41:21] And so having that shared knowledge is extremely beneficial

[00:41:24] **Tim:** Yeah. Interesting. I just never thought of it in the context of a wiki,

[00:41:28] **Adam:** Right

[00:41:28] **Tim:** guess, but I guess it's kind of because I'm breaking everything up into separate folders, they really are kind of wikis

[00:41:35] **Adam:** Kind of, yeah. I mean, so I, I was, kind of staring off into space here for a little bit thinking like what, what makes a wiki, you know, in spirit is that anyone, quote-unquote, "can edit it," right? Like anybody, any of the users can edit it. And I think that that goes hand in hand with the, what we were talking about where you just put it in a Git repo to share it, right?

[00:41:57] Like I, I already have my product management wiki in a Git repo because I'm terrified of the LLM making changes that are gonna be destructive, right? Anyway, so,

[00:42:09] you know, the, the claude.md that I have in there is already like, you know, okay, after you've made changes, you have to make a commit with all of your changes included, right?

[00:42:17] Um- that from me or did I learn it from you? 'Cause I know I, I've been doing

[00:42:21] I learned it from you, Dad. I learned it from watching you

[00:42:28] **Tim:** Good callback

[00:42:30] **Adam:** yeah. I don't know. Who knows? But, yeah, so like, I,

## [00:42:33] Digital Gardening and Linting the Knowledge Base

[00:42:36] **Adam:** I find this to be an incredibly compelling use case for LLMs, probably because it's the lazy approach. But I think that, you know, like we talked about before, laziness can be a good thing, right? It, it leads us to do things that are simple and easy and

[00:42:52] **Ben:** Well, I think it's not lazy though, because I think everything requires work. And I think what you're gonna find or what I assume people will find, again, not really knowing that much about this topic, that it's really easy to start something, but then to continue to make it good over time is, is, you know, effort that you have to dribble in.

[00:43:13] You know, like, do you have to do something every week or every month, or do you have to come up with skills that refine it over time or, drop things that feel like they're just polluting the context window? Or I saw somebody mention something about, like, y- if you grab a, like a YouTube transcript and say, "Hey, summarize this YouTube transcript into the wiki," it makes a mistake in the summarization, then you're like kind of baking that mistake the model of the, of the wiki and, you know,

[00:43:40] **Tim:** Yeah

[00:43:41] **Ben:** then you gotta find that and you gotta remove it once you realize that's happening.

[00:43:44] You know, like it's gardening, you know? It's digital gardening. So it's

[00:43:48] **Adam:** Absolutely

[00:43:48] **Tim:** I'll give you a concrete example of what you're talking about. So, like, for our, my goal project for my, for my dashboard, So there's some changes I needed to Jira, our ticketing system, and there's a person who kind of gatekeeps that. So I sent it to her and I said, "You know, here's what I need," and she completely misunderstood what I wanted, and she started, like, inserting her own goals into my goals that were not given to me. And I just grabbed that email and put it into my, my folder that I use to build this goal project. All of a sudden I start seeing these goals. I'm like, "None of this was coming from above. Where'd this come from?" And they're like, "Oh, so and so, so and so mentioned it in this email." I'm like, "Okay. Yeah, that, that is completely wrong."

[00:44:35] And it was really hard to un- put the toothpaste back in the tube on that one. yeah, I had to go in and tell it to s- forget that, clean this up, stop... In fact, I, Impeccable just finished and I just see those, some of those goals came back. So I gotta go in and,

[00:44:48] **Ben:** You got your own goblin problem

[00:44:50] **Adam:** I got, I gotta, I gotta pull those weeds out of this garden 'cause it's like you know, they're only supposed to have like three to five goals and all of a sudden there's six and seven. I'm like, "Where'd these come from?" UhSix, seven

[00:45:01] **Tim:** Six, seven.

[00:45:03] **Ben:** forgot about that

[00:45:04] **Adam:** So you do have to,pay attention to how this works and understand how it works, because like you were talking about, Ben, it is entirely possible to pollute the context too much. One of the things that I've had to do, because eventually, you know, you get enough tickets covering the same topic, I noticed that there was like a section at the bottom of the f- the...

[00:45:25] Each, you know, each page in the wiki had like a sources down at the bottom, and that was growing to the point, especially 'cause it's, you know, URLs to a bunch of tickets as, as each reference. it was growing to the point where it was more content in the document as sources than it was like the, the actual information.

[00:45:42] And I was like, "That's a waste of, you know, time and tokens reading that to, to answer questions." So

[00:45:46] **Ben:** Right

[00:45:49] **Adam:** like, JavaScript source map files, right? So like we have a, you have relationship between like this is the, part that is not relevant all the time, and this is the part that I want you to look at most of the time, right?

[00:46:02] The, the source code and the, and the compiled source code or whatever. And I was like, okay, well, let's, let's use that sort of concept and, and had it build like a sidecar. So I, I don't even remember what the file name is, but it's just like, it's, it's just like, you know, if it's eventregistration.md, then it's like eventregistration.sources.md or something like that, right?

[00:46:22] And, and so the... there's always, the two files there that, that stay paired and all the, that sort of background detail, the metadata goes in that sidecar file. It might just be called like .sidecar.markdown or whatever. But, and i- if you read that gist, one of the things in there is it talks about like running a lint occasionally.

[00:46:45] You just like... I think the way it's set up is the, like the claude.md says like, "Okay, if the user asks for lint, then do this," right? "Look for these types of problems in the dataset."

[00:46:56] **Tim:** Like contradiction between pages, stale claims.

[00:46:59] **Adam:** Yeah, that sort of thing. Um, low confidence, claims or statements in the, in the wiki. Like if, if it's, if it's a code smell for it being in the documentation, right? Like, if you're not highly confident in the statement, then maybe that's something that the user might wanna go back and further research.

[00:47:15] **Tim:** So, the lint thing is something I had been doing for a while, and I started to realize... Actually, I did it today. I realized that, this is the work one. I, I haven't actually done anything with LLMs with my personal one yet. You're waiting for your superpower

[00:47:29] **Adam:** yeah. Yeah. but I, I realized it's like I, I tell, I told it to lint, and then I was like, "You know, every time I do this, it writes code to, like, search through the, the wiki files in a certain way, right?

[00:47:41] I'm sure it's looking for certain keywords and using that to do whatever prompting. Like, I wonder if I could skip the part where I have the LLM write the code to then go look at the data, and if I just said, like, 'Here's a, a program you can use that spits out the relevant context for a linting session,' right?"

[00:47:59] so I said, you know, we... I, I had it run a lint, and then I was like, "That code you just wrote, is that something that we could make repeatable and, like, a reusable utility f- program?"

[00:48:10] **Tim:** too

[00:48:11] **Adam:** Yeah, yeah. And it was like, "Oh yeah, definitely." So it started to do it, and it started to write it in Python.

[00:48:16] **Tim:** Adam. You're so smart. Let's do it. I wanna

[00:48:18] **Adam:** It started, ugh.

[00:48:21] **Tim:** Thanks,

[00:48:21] **Adam:** It started... Damn it, Tim, shut

[00:48:24] **Tim:** Sorry.

[00:48:25] **Adam:** up. Uh, it started to write it in Python, and A, I don't like Python to begin with, but B, This whole, like, LLMs in general, one of the things that it has shown me is just how much faster Rust is for local stuff in particular, right? Like, yeah, I mean, it, it makes total sense if you think about it.

[00:48:45] Like, all these things that have gotten, like, 10X, 100X faster in the last couple of years, the, like, JavaScript build toolchains, ESBuild, and Vite, and all these things, like, most of them are using Rust under the hood or, or one of those other similar generation languages like Go.

[00:49:01] **Tim:** Like Rust SF, CFML? Yeah

[00:49:05] **Adam:** stepping right past that one as well. and,

## [00:49:08] Why Rust Beats Python for Local Tooling

[00:49:08] **Tim:** Sorry

[00:49:09] **Adam:** I, I was just...

[00:49:10] **Ben:** a

[00:49:10] **Adam:** so the tool for me was...

[00:49:12] **Ben:** like an executable? Gotcha

[00:49:14] **Adam:** Yep. The, the tool for me that was, like, really eye-opening was ripgrep. So if y- you probably know what grep is, right? It's searching across files, whatever. There's one, there's basically a re-implementation of grep, but written in Rust, and if you run them side by side, it is mind-blowing how fast it is.

[00:49:31] Like, if you searched for, you know, whatever word across a code base of maybe, like, 20,000 files or whatever, that grep could get done in a couple of seconds, a second, two, three, whatever, right? ripgrep, you're talking, like, maybe two-digit milliseconds to search...

[00:49:48] **Tim:** grep

[00:49:49] **Adam:** Yeah, R-I-P grep. Maybe, and honestly, maybe that's why it's, it's like, I'm, I'm coming for your lunch. I'm killing you, grep. I don't know why it's called ripgrep, but that's what it is. The command is RG, I believe. but just holy smokes, it's so much faster. And so I was like, okay, I, I don't know why I didn't put two and two together previously 'cause I knew that Rust was fast, but it's like, okay, if grep could be made that much faster and grep, I'm sure the original grep was written in C or, or something like that.

[00:50:17] Like, okay, then there's

[00:50:19] **Tim:** probably.

[00:50:21] **Adam:** stepping right past that as well.

[00:50:22] **Ben:** Hmm.

[00:50:23] **Adam:** Um, the... So i- it's worth considering for these utilities that you want to run really, really fast. So I was like, okay, well, cool. Let's l- you know, and I don't have to learn Rust. I can just be like, okay, no, don't, don't write it in Python, write it in Rust, and it did it, and I'm like, awesome.

[00:50:37] And it, it is. It's super fast. It's not, it's not like I have thousands of these files, but I probably have a couple hundred of these files, and it's more or less instant that I run the command and it spits out, "Here are the 40 things that I found that are low severity matches," or whatever. Yeah. So, I'm, I'm, I'm very happy with this system so far.

[00:50:57] **Tim:** It's a little, it's a little bit of, like, duct tape and bubblegum and, and Christmas ornaments being held together here. Like Project Hail Mary

[00:51:06] **Ben:** But I'll, I'll say, like, as, as you're talking about it, the, the thing that makes it make more sense in my mind is this idea of being able to lint it, and, and not even from a technical standpoint. But I think that was my mental hurdle when I heard them talk about it in the meetup, was that it

[00:51:24] **Adam:** Mm-hmm.

[00:51:24] **Ben:** very much when they were talking about it like this drawer of information they would just throw stuff into.

[00:51:30] And in my mind, a junk drawer just gets worse over time. It doesn't

[00:51:34] **Adam:** Yes

[00:51:35] **Ben:** But if you have a... a litmus test, and you can look at any one document and you can think, you know, in some sort of meaningful way, is this document making this wiki better or worse? And will it make it worse over time or better over time? at least is like you have a path forward in the way that you can see maintaining it. So when you're building a business system or you're building, know, a KPI system for the team you're managing, like at least you have a North Star. I think that was the idea, is like not having a North Star, like what is this wiki even for?

[00:52:09] **Adam:** Yeah

[00:52:10] **Ben:** I didn't quite... I couldn't get past

[00:52:13] **Adam:** And I, I do feel like my personal one that we've been talking about is a little more like that than it is like the product management one, right? It's, it's just, it's basically a way to like put my diary inside of an LLM and say, "What did I talk about on this day?" Or, "What days did I talk about this topic?"

[00:52:30] Or, you know, "What, what could be causing this thing?"

## [00:52:33] LLM Amnesia: Forgetting What You Did Yesterday

[00:52:33] **Ben:** Yeah.

[00:52:34] **Tim:** I feel like I- I'm experiencing, LLM Claude amnesia 'cause I can't remember what I've done from day to day

[00:52:42] **Ben:** Oh my God, dude. I was just literally telling my wife that this morning.

[00:52:47] I said, "I in in the morning, literally have no idea what I worked on yesterday."

[00:52:53] **Tim:** Exactly.

[00:52:53] **Ben:** And

[00:52:53] **Tim:** to ask Claude, " Search your memory and tell me what I worked on yesterday," 'cause I can't. I serious- Because when you have... I have so many context windows open, it's like I don't know what I did. I did a lot of things. I know I worked all day long, but I can't tell you what I worked on. And Claude's like,

[00:53:10] **Ben:** for me

[00:53:10] **Tim:** did this, this, and this, and this, and this, and this."

[00:53:12] I'm like, "Okay, cool. Could you please log that so I have proof so I don't get fired?"

[00:53:17] **Ben:** I think for me, 'cause it's not like I have a lot of different tasks running. I'm, I'm, I'm still a very much a one-task guy and I'm, you know, one ticket at a time and I've got one terminal window open for Claude. I think for me it's like I spend so much time iterating with Claude on an idea and trying to refine the thing that it's about to work on or like trying to understand... You know, 'cause a lot of times I'll say, "Hey, I wanna do X, Y, and Z." And it'll say, "Okay, X, Y, and Z is fine, but have you considered M, N, O, P?" And I'm like, "Well, let's iterate over those 'cause I'm not sure that's even really relevant to this conversation." And we talk about L and then M and then N and then O and then P and I'm like, "This one, yeah, we should do this, but no, we shouldn't do that," or like, "Let's defer on this because it's not relevant." And it's like I spend so much time hand-wringing with Claude about the thing that we're gonna do actually end up just forgetting or like, like what cements in my mind is the pain of the conversation and not like the concreteness of the outcome.

[00:54:15] **Tim:** Yeah

[00:54:15] **Ben:** It's w- it's really weird

[00:54:17] **Tim:** It is weird. It is weird. And that's why it's like I, feel like it's replacing my brain, right? But going back to the LLM topic, so I'm reading the, the gist here, and I kind of agree with it. So it says, "The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means.

[00:54:38] The LLM's job is everything else." And everything else is bookkeeping, like updating cross-references, keeping summaries current, when new data contradicts old claims, et cetera, et cetera, et cetera. You can read the article yourself. Adam will put it in the show notes. And I get... Yeah, I get that. I mean, 'cause that is the hard part, right?

[00:54:57] Like, if you can find a way to automate that bookkeeping, then all you're really doing is doing the fun stuff, which is like finding new sources, pulling them in, grabbing them in. Like, "Oh, this looks cool. Let me throw it in the garden. Let me throw this in the garden." And this thing kind of goes in and tries to maintain it all.

[00:55:13] **Ben:** I know. If, okay, if I can tangent for two seconds, but it's, it's a relevant tangent.

[00:55:18] **Tim:** We've never stopped you with a tangent

[00:55:20] before

[00:55:20] **Ben:** uh, I'd say for a long time, I've always thought about there being sort of two types of people in the programming world. There are the people who really all they wanna do is build new stuff and try out new libraries and new frameworks and prototype ideas, they don't get any joy out of maintaining an application over the long term.

[00:55:45] **Tim:** Would you really

[00:55:46] **Ben:** Well, so that's what I'm saying is, like, I, I think then there are a lot of people who... Maybe not a lot of people. I think there's a good number of people who like the idea of inventing new stuff, but they like the idea of building a product over a long period of time and that is, is, that is a different kind of satisfying. And, um a long time, I, like, sorta ha- quietly hated on the people who only wanted to build new stuff 'cause I'm like, yeah, like, of course you only wanna eat ice cream for dinner. Like, that's what we all wanna do, but, like, that's not the real world. It's not

[00:56:23] **Adam:** And garlic bread

[00:56:24] **Ben:** Yeah, it's not just about eating ice cream.

[00:56:26] Sometimes you gotta eat your vegetables in order to live. But I've, like I've...

[00:56:32] **Tim:** they have a problem with commitment

[00:56:34] **Ben:** Well, so, but I've pulled back on it a little bit and as I'm thinking about all this AI stuff, and especially as I'm seeing people, like, really wanting to live on the bleeding edge and kind of, know, hacking the path in the jungle with the machetes, part of me is like, maybe we just do need people who, you know, are the extreme sports of programming and, like, they like doing this, and there's a chance they might die while they're doing it, and they're sponsored by Red Bull, and, like, that's the path they've chosen. And, like, but, you know, it's like I don't wanna hate on that anymore 'cause I feel like in

[00:57:07] **Adam:** So

[00:57:07] **Ben:** degrees it, it's, to some degree it's, like, a necessary craziness to help move the rest of us forward. I'm sorry. just

[00:57:15] **Adam:** am I gonna get like a Red Bull branded wrist rest or

[00:57:19] **Ben:** Yeah. I mean, like Adam is definitely farther on that end of the spectrum than I am for sure by, by, you know, gonna say a country mile, but I don't actually know what that phrase means.

[00:57:30] but I thi- I guess what I'm saying is like, I think it's one of these things like there's a synergistic relationship between these two personality types and I, and I don't think... I used to think that my way was better because it was the way I chose, but I think it's actually both are very valuable and, and

[00:57:46] **Adam:** It takes all types

[00:57:47] **Ben:** Yeah, I think like

[00:57:48] **Tim:** you.

[00:57:48] **Ben:** both need...

[00:57:49] **Tim:** You're growing.

[00:57:49] **Ben:** You can't, you can't have just one. You have to really have both to move everything forward.

[00:57:54] **Tim:** Their heart matters too

[00:57:55] **Adam:** Yeah. I, I'm sorry, I don't remember why I got onto that, but, Well, then that seems like a perfect place to wrap it up.

## [00:58:01] Patreon

[00:58:01] **Ben:** There

[00:58:02] we go.

[00:58:02] **Adam:** So this episode of Working Code was brought to you by touching grass with your whole body. I hope you don't have allergies. listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:58:18] Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. Actually, I gotta throw a shout-out to Giancarlo. he has been hitting me up lately. He and I think at least one of his daughters both went skydiving for the first time.

[00:58:36] **Ben:** Oh, nice

[00:58:36] **Adam:** yeah, he, he shared some of that in our Discord, and then he and I have been talking in, in DMs, and he's gone again since then, too. so, congrats, man. That's

## [00:58:44] Thanks For Listening!

[00:58:44] **Adam:** awesome.

[00:58:45] **Ben:** Very cool

[00:58:46] **Adam:** after show, we're gonna go record the after show. Tim has a YouTube video he wants to tell us about. I think it was a YouTube video, the psychology of Gen X men who love to cook.

[00:58:55] **Tim:** I'm so seen. seen

[00:58:58] **Adam:** The video's about you, yeah. and, and I, I actually kinda wanna continue a little bit of being on the bleeding edge discussion about LLM stuff and, and doing,some customization stuff. So there's a thing that I wanna talk about. So gonna get into that. if you would like to get access to the after show, it's real easy.

[00:59:14] You go to patreon.com/workingcodepod, throw a few dollars our way. We'll give you the special RSS link that gives you access to every episode of the podcast with, show attached, past, present, and future. and you get to listen to that. That's how that works.that's gonna do it for us this week.

[00:59:33] We'll catch you again next week. And until then

[00:59:36] **Tim:** Listeners, if we

[00:59:38] as a podcast were a wiki You listeners would be 100% our best attribution. heart matters.

## [01:00:07] Bloopers

[01:00:07] **Adam:** you know, that kind of information i-is useful to be able to, like, automatically generate And after show.
