---
title: "157: Dead Man's Snitch Deep Dive with Adam Cameron"
description: "This week, friend of the show Adam Cameron joins Adam in diving deep and answering some questions about Dead Man's Snitch, a product that offers a solution for task health alerts."
date: 2023-12-13
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/7ac6cacf-9221-457a-9003-d42d0d8417a3"></script><div class="redcirclePlayer-7ac6cacf-9221-457a-9003-d42d0d8417a3"></div>

This week, friend of the show Adam Cameron joins Adam in diving deep and answering some questions about Dead Man's Snitch, a product that offers a solution for task health alerts.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/157-dead-mans-snitch-deep-dive-with-adam-cameron.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** so this is a piece of software. It's modeled after the concept of a Deadman's Switch.

[00:00:03] **Adam:** you know, you configure a variety of snitches, You tell it what schedule you expect to, to run your job in,and then, should the job go missing, then it can do a variety of different things to let us know, right?

## [00:00:17] Intro

[00:00:17] **Adam:** Okay. It is show number 157. And on today's show, it's going to be the Adam and Adam show. I have with me, patron, friend of the show. And, bloody good chap, Adam Cameron.

[00:00:48] **Adam:** Say hello, Adam.

[00:00:50] **Adam Cameron:** Hi Adam.

[00:00:52] **Adam Cameron:** That actually worked.

[00:00:53] **Adam:** yeah, Adam Cameron, I don't know if I said your last name previously, you know, you've been around, a stalwart, of the, the

[00:00:59] **Adam:** ColdFusion CFML community for a very long time. and, just a good guy. So we've been hanging out a lot together, and we're going to talk about Dead Man's Snitch on today's show.

[00:01:11] **Adam:** We'll, we'll, we'll get in to that stuff more later, but, as usual, we would like to start with our triumphs and fails. I assume you brought one with you, Adam.

[00:01:19] **Adam Cameron:** Kind of one, yeah.

## [00:01:22] Adam Cameron's Triumph/Fail

[00:01:22] **Adam Cameron:** Okay, yeah. This is a stupid thing. I've been quite, quite a late starter with Docker. I've only been using it for about three years because when I was looking for a job with it, everything was Dockerised, so I had to teach myself. Which is fine, and now I'm kind of the Docker person at work.

[00:01:37] **Adam Cameron:** And it took me three years to find out that the entry point instruction at the end of the dockerfile runs after the container start. I just assumed everything in the dockerfile was to do with building the image and it just

[00:01:50] **Adam Cameron:** never occurred to me that I had that in to run stuff after the container was running. Like doing npm install or in my case composer install and stuff like that to set up the PHP dependencies after we start. And I just thought how am I this stupid? Um. Basically, and coupled with that, so I'm calling this a fail by the way, I don't know whether I've mentioned that before, and coupled with that I finally twigged like how a PHP container works, because you know containers usually have to have some sort of program running to keep the container from just finishing as soon as you start.

[00:02:25] **Adam Cameron:** We use Docker Composer and Docker runs pretty much the same thing as well, and it didn't occur to me until I was looking into this that the reason why a PHP, because PHP is just an EXE, you know, it's just you run it when you want to run it, it's not like ColdFusion. That PHP has a thing called PHP FPM, which is the service that runs in the background listening to requests coming from Port 9000 or whatever. It seems quite late in the piece for me to learn this thing that's incredibly fundamental to me to make my job. Maybe a triumphant that I found that out now?

[00:02:59] **Adam:** you managed to make it work this long without, without that. So I just want to make sure I'm understanding you were not clear that the, it's that last line that is what is keeping the container alive.

[00:03:12] **Adam Cameron:** well, yeah, that was it. how this cropped up is I'm foolishly, I volunteered to get our new node application, dockerized, our frontend application started on, we are shifting away from, uh, ion or Lucy from doing all that stuff and we've got a React application instead. So we've got a frontend developer starting to do all that, but he doesn't know anything about Docker.

[00:03:31] **Adam Cameron:** So similar to me in that regard, I guess we just found out. but I was dockerizing the stuff and the, I. Created a node container, but it was just exiting every time it started

[00:03:43] **Adam Cameron:** and that got me looking into the entry point thing and then I did some more reading and went, how did I not know this? And I redockerized our PHP containers as well to do the composer install part after it starts up.

[00:04:00] **Adam Cameron:** When I added the entry point instruction in, suddenly the PHP container just started shutting down straight away and again. yeah, looking into it further, the last thing in the underlying PHP image is an entry point run PHP FDM which just sits there in the background and listening. So I finally tweaked how all that stuff works as well. So it's a good learning experience. Which I guess is a win in itself, but it was the key thing was I assumed everything of the docker file was to do with building the image and it wasn't until you got to either the docker run command with all the parameters you give it or the docker compose file with

[00:04:38] **Adam Cameron:** similar parameters and and that stuff was applied to the container and that's not true

[00:04:44] **Adam:** yeah, I mean, it's pretty amazing how far we can get in this industry with just a little copy and paste. Like you don't really have to understand everything. Don't really have to read the docs. You can, you can

[00:04:54] **Adam:** get pretty far.

[00:04:55] **Adam Cameron:** yeah yeah well I mean we've we've got this business that make however many millions of quid for the boss every year running on this stuff that I didn't understand you Cool. We'll worry depending on how you look at it.

[00:05:09] **Adam:** Yeah. You know, little column A, little column B.

[00:05:11] **Adam Cameron:** Yeah. Yeah. So that's me. Adam, over to you, I believe is what we normally say.

[00:05:17] **Adam:** Yeah. As usual.

## [00:05:20] Adam's Triumph

[00:05:20] **Adam:** so, I am gonna go with, I'm gonna call it a triumph. It's been a rough couple of days for me, I thought I would pick something very specific to what we're gonna talk about today, and so, I mentioned on a previous show that, we switched things up about, like, the way that we're storing the configuration of our snitches, And using the service and its API as sort of the database of our snitch

[00:05:45] **Adam Cameron:** yeah, I can recall you saying that.

[00:05:46] **Adam:** Yeah, and, and sort of, in a way, you could say we're kind of looking up the snitch ID real time in order to check into it. And we'll get into what that means in more depth here soon. But, I made some mistakes when I wrote the code that, that made all of that work. And, and, you know, typical developer mistakes, stupid mistakes like, So the, the way that we find a snitch to check into is, you know, it says, okay, this is the job that's running.

[00:06:12] **Adam:** It's running job XYZ, for customer PDQ. and so I need what, I need the snitch ID for that. And it goes and looks it up and if it's not found, it creates it and it, okay. Well, okay. So I need to create a snitch with customer. So there's, there's tags, right? So it creates it. Creates a snitch and it tags it.

[00:06:31] **Adam:** Okay. It's for this job and for this customer so that when we need to go find it later.

[00:06:36] **Adam Cameron:** And by tag, you mean just like metadata type, any,

[00:06:39] **Adam:** yeah, yeah,

[00:06:40] **Adam Cameron:** you can attach to it, like a label in JIRA for arguments,

[00:06:42] **Adam:** yeah, exactly. Just like, you know, a lot of people tag their blog posts or whatever. Um,yep. And so, the thing that I shot myself in the foot with was I was creating them with whatever the case, uppercase, lowercase, was of the customer name, as it came in for the request.

[00:06:58] **Adam:** And then when I was specifically looking them up, I was doing a U case. Cause I was thinking, you know, you know, when we. are implementing things in, in a text in, or a case insensitive way. Usually you go, okay, everything is uppercase or everything is lowercase on both sides of the equation, and then we could just do an equal.

[00:07:16] **Adam:** and I, that's how I was thinking when I wrote the code to do the lookup, but that's not how I was thinking when I wrote the code to do the create. And so, not last night, as we're recording this, but the night before, I got woken up. Like four times an hour. it was a rough night. not, not every hour overnight, somehow it managed to like give me three or four straight hours of, of no interruptions.

[00:07:38] **Adam:** but it was, it was a very rough night because. of two mistakes, the, the text case one and then another one that I, it was using an in memory cache of the Snitch configuration. And I just, it didn't even occur to me that we, we very recently switched to this server that's running this being, multiple instances, like a load balanced cluster.

[00:07:58] **Adam:** And so, each instance had its own in memory cache and would go, okay, I don't recognize this Snitch that you're asking for, let me go create it. And it would create it and check into it, and that's fine. And then, you know, the next time that the job runs, maybe it hits the other server, and says, Oh, I don't know what this snitch is that you're trying to run.

[00:08:17] **Adam:** So it goes and creates a duplicate of it and then checks into it. And so, and the funny thing is we're, we're very deep into the process of growing and evolving the way that we're using the system. It's a little bit of a naive implementation still right now. We get, Alarms, on call alarms for every snitch that fails and then again when it starts to resume.

[00:08:38] **Adam:** So, I was getting alarms for all of these duplicates being created and, and the first time they get checked into, it's like, hey, congratulations, your snitch just checked in, which is great, fine. And then, you know, 15 minutes or an hour later or whatever, it fails to check into that one. And it's the same, you know, I've got four duplicates of the same, job.

[00:08:56] **Adam:** So each of those four is kind of constantly like, Missing or or now checking in again or whatever because of the the caching thing and then some of them I was like, I couldn't figure out how to get it to stop overnight I was just kind of like the things that were failing I knew was not a big deal so I was able to just like silence the alarm and try to go back to sleep, but it did keep me keep waking me up and it was very annoying.

[00:09:20] **Adam Cameron:** So, yesterday, at work, I made it, like, my the only thing I needed to accomplish for the day was to make this not happen again overnight. And so the triumph here is that I actually got a good night's sleep last night. That's triumph in anyone's books, mate. for whatever reason.

[00:09:35] **Adam:** yeah, you know, as much as my body will let me, now that I'm an old person. But, uh yeah. So, I, I managed to fix the problems. The, the text casing and the, in memory caching. Fixed those two things, and

[00:09:47] **Adam:** I want to come back to the text case thing later. I've been writing some notes as you've been talking. Already? Wow.

[00:09:53] **Adam Cameron:** yeah,

[00:09:53] **Adam:** Cool. so, then, let's just get right into it. Let's talk about Deadman Snitch. why don't I give, like, a, just a very quick, uh I mean, this is gonna sound like a sales pitch, but we're just, you know, talking about interesting software, right? Um, so,

[00:10:05] **Adam:** I'm just gonna

[00:10:05] **Adam Cameron:** you to sound as enthusiastic about this is, being is about feature flags. So, that's the level you need to picture that

[00:10:12] **Adam:** Okay, okay.

[00:10:13] **Adam Cameron:** Mm-Hmm,

## [00:10:14] Dead Man's Snitch Overview

[00:10:14] **Adam:** so yeah, for anybody who's not familiar, who hasn't been listening or paying close enough attention, this is a piece of software used to monitor things that happen on a schedule, not things that you're sitting there triggering, in real time, right? I'm not at the desk running a job and wanting to know if this thing failed.

[00:10:30] **Adam:** I'm sleeping and I want to be woken up. If, if it fails because it's that important, that sort of thing. so this is a piece of software. It's modeled after the concept of a Deadman's Switch. S W I T C H. this particular implementation service is called Deadman's Snitch. S N I T C H. and it's basically, a very simple service on the surface.

[00:10:53] **Adam:** you know, you configure a variety of snitches, which you just have like one snitch per job effectively. You tell it what schedule you expect to, to run your job in, and then if it stops checking in for any reason. So, so, and a check in is, okay, my job is running, and sort of like the last thing it does before it shuts down is it sends just an HTTP request to this service to say, okay, hey, I'm here, I did my thing, consider me alive, right? and then, should the job go missing, then it can do a variety of different things to let us know, right? It can just send an email, it's got integrations with other services. So we have it set up to integrate with our Ops Genie, which is an Atlassian product, for, for on call alarms, that sort of thing. And there's a, you know, there's a variety of ways we can do that. Like I said before, ours is currently pretty naive. all snitches are being alarmed. We have a plan for how we're going to change that. but,

[00:11:51] **Adam Cameron:** and

[00:11:51] **Adam:** way it's currently configured.

[00:11:53] **Adam:** that text in the middle of the night level for everything purely because you're still easing and this is new technology for you guys as well. we've been using it for years, but, but, you know, initially when we started setting it up, we were only using it for things that were mission critical. So it just made sense. And, you know, to be fair, you know, it's not often that things are failing and, and, sending alarms. So even if it is a.

[00:12:21] **Adam:** Something that can be ignored. If it happens once a month that it wakes somebody up and you go, Oh, okay. That one, I know I can ignore. Then you can just go back to bed and it's not that big of a deal. If it's happening every night, that's, that's much more of a problem. so, and then, further complicating things is, we have, we are in the process of moving toward a multi tenant architecture.

[00:12:43] **Adam:** So right now, you know, everything is. Deployed as effectively single tenant, we're, we're, you know, migrating in that direction, but, so there's 13 customers who all have 13 copy, or each has its own copy of every one of these jobs. And so, if there's, say, you know, a syntax error got deployed today, and the job is going to fail because of that when it runs overnight.

[00:13:06] **Adam:** Then it's going to fail 13 times and that's particularly annoying, right? So that's one of the things that will be changing in the future is, the jobs themselves will become multi tenant, right? And it will be one job that just runs and it handles all customers. And so even if it does fail, it'll fail one time, we'll get one alarm.

[00:13:23] **Adam Cameron:** I know. Yeah, that makes perfect sense and I would presume you're not locked out. So having done that, there might be some alarms that are. Use or tenant specific or the frequency or something tenant specific and you can still accommodate that sort of granularity

[00:13:40] **Adam:** We do have a couple. We try very hard not to do anything that is going to make our lives more difficult as we move toward multi tenant. you know, we do, like, the occasional third party service that we have to integrate with, and, and pull data from, or that sort of things. But, for the most part, we try to keep things pretty cookie cutter, but from customer to customer, that way.

[00:14:04] **Adam:** Yeah, and I guess it depends on the nature of what you're doing as to whether it even makes sense to have tenant specific things that it'll either be right or it'll be wrong across the whole piece of

[00:14:12] **Adam Cameron:** software. I'm not used to multi tenant software, so it

[00:14:15] **Adam:** Yeah, it gets, it gets very interesting very fast when you have, like, one of the difficult things about our industry is that we are working with universities and they are deeply entrenched with, whatever payment gateway that they use, like, as a campus. Right. So the, as a, as an organization, a gigantic, multi million dollar organization, they have an established relationship with some gateway, whether it's BlackBaud, Elevon, you know, authorized on that, whatever.

[00:14:44] **Adam:** And so there was, if we were like, okay, we use Stripe and you have to use Stripe to go with us, then I don't think we would have any customers and we would have gone out of business 10 years ago. Like we don't have a choice, but to integrate with all of the gateways. And so we use a service for that. That sort of, does the abstraction of gateways, for us, which is very nice.

[00:15:05] **Adam:** The one downside is that they don't have support for, and this is probably not their fault, but they don't support, like, Braintree. I think that there's Discussion of them adding it soon. Anyway, this service is called Spreedly. S P R E E D L Y, if anybody wants to look it up. You know, that's, to me, I always get annoyed when somebody discusses something on a podcast.

[00:15:22] **Adam:** I'm like, oh, that sounds great. Can I please have access to this thing? You know, I want to go patronize this service too. And they don't say what it is, or they don't tell you how to find it. So there you go.

[00:15:32] **Adam Cameron:** And good on you for spelling it out too, because depending on what one's accent sounds like, words can sound quite different, as we've

[00:15:38] **Adam Cameron:** already discussed beforehand.

[00:15:41] **Adam:** Uh, anyway, so, that's kind of the elevator pitch for Deadman's Snitch as a product, as a service, right? So, you configure Snitches, you have your scheduled jobs that run and check into Snitches, and instead of getting an email that the job ran, and now you can, you know, Be happy, you know, go about your day knowing that the job ran overnight.

[00:16:03] **Adam:** Instead of like expecting 30 of those emails in the morning and then having to notice when, hey, wait a minute, I only got 29 of the 30 emails that I was expecting. It kind of flips it around the other way and says, hey, wait a minute, this one went missing. and you can either get that by email or you can get a

[00:16:17] **Adam Cameron:** That

[00:16:18] **Adam:** wake me up alarm.

[00:16:19] **Adam Cameron:** very clarifying way of describing the service. I knew what you were talking about, but I hadn't thought of it in terms like that, because it

[00:16:28] **Adam Cameron:** fits into, we need to do something like this now shortly, which is why I've got the interest in talking to you about it. but that's a good way of looking at it, that it's the Detecting the negatives rather than leaving it to the user to count the positives, which will always get lost in there.

[00:16:43] **Adam Cameron:** And I don't want to get dirty emails. I don't want to get one email, but you know,

[00:16:47] **Adam:** Yeah. absolutely not. And I mean, it, it's funny the way it landed on my radar. it was originally, a product created by somebody local to me here near Philadelphia. and it's just like a, you know, a startup type of person in Philadelphia created it. And it, you know, I just had it in the back of my mind.

[00:17:06] **Adam:** I was aware of it. And then when we had a need for it, I was like, hey, actually, I know exactly what we need. We started using it and then later he sold the business off. So it's not the same guy anymore, but it's still a great product at a great price. So

[00:17:17] **Adam Cameron:** you're still invested locally, which is really good.

[00:17:20] **Adam:** So that's, the elevator pitch on the service itself. Did you have specific questions or certain place you wanted to start?

[00:17:27] **Adam Cameron:** No, I just the one thing that I find really interesting in this is that it reminds me of LaunchDarkly in that, not that it does anything similar, but left to my own devices. And me being a dev, I'd go we need something like this and I'd open up a file and start writing angle brackets cf this that and the other thing and

[00:17:48] **Adam Cameron:** then start trying to solve it myself and indeed at work we've we've kind of done that in our platform but we're migrating to javascript at the moment and I don't want to reinvent the wheel so I didn't even know anything like this existed so I am now glad that it's not something my devs need to write for me.

[00:18:07] **Adam Cameron:** We can

[00:18:07] **Adam Cameron:** live with something like this. you Which is, which is really good, and it's important, I think, for people to consider using stuff that's already been written, rather than writing it yourself. It's less fun, but it's more efficient, and

[00:18:19] **Adam Cameron:** it's more professional to reuse something that's already been done.

[00:18:23] **Adam:** Yeah, for sure. you know, it, it's easy. It's when you come across a problem like this, that's so well defined, it's easy to get sucked into the trap of like, Oh, I, I could do that. That's not a problem. And you know, then, then you're, but the, the things that I think we fall into the trap is, is like, we're not thinking about, okay, well, but for this to actually be valuable, it has to be, you know, I'm using finger quotes here, highly available so that it doesn't go down because one, one region of AWS went down or something

[00:18:49] **Adam:** like that. You know, I need to make sure that it's going to be there because this is a mission critical piece of infrastructure here.

[00:18:56] **Adam Cameron:** Yeah, and even not at that level though, I mean, I'm thinking for our operation, we're running on one server in a data center in Manchester or something like that. and this deals with the entire UK and Ireland, but we don't have this global spread, sort of thing. But that's the complexity. It's like, oh, I can write something, I can send an email,when something tallies up and they go, ah, but in the middle of the night, the email's no good, mate.

[00:19:17] **Adam Cameron:** Oh, okay, so now I've got to integrate with a text gateway. And there might be some others that go, oh no, we actually need to put something into Elk or something like that. And, and if you start writing it yourself, it sounds really easy when you start, but it's

[00:19:27] **Adam Cameron:** very, very quickly, it's super complicated.

[00:19:29] **Adam Cameron:** And these guys have done it all for you already, so.

[00:19:32] **Adam:** yeah, and

[00:19:33] **Adam Cameron:** What's the pricing like Is that something that we ought to discuss here or make sense too?

[00:19:39] **Adam:** yeah, we can mention it. Let me pull up their plans page here. So, actually, they,yeah,

[00:19:43] **Adam Cameron:** else can see these numbers.

[00:19:44] **Adam:** I, I'm pretty sure, yeah, so they, they even have a free plan, so if you just, like, want to try it out, you can try, try it out for free for an unlimited amount of time, you get one snitch, like it's one job to check into, and, and then it goes up from there, so, if you want three snitches, it's 5 a month, 100 snitches is 20 a month, 300 snitches for 49 a month, and then, like I mentioned on the show, I don't, I don't know what the, the numbers are off the top of my head, but we recently got to the point where we're like, okay, well, we know for a fact that we now need to create more than 300 snitches.

[00:20:18] **Adam:** and so, we are now on the, if you need more, call us price tier.

[00:20:24] **Adam Cameron:** yeah. But I mean, like I personally wouldn't want to be stocking up 50 bucks a month for anything to do with IT, but for a company that's nothing,

[00:20:32] **Adam:** Exactly. Yeah. 50 a month. And that, I mean, 50 a month covers you for 300 jobs. And so if you've got 300 background jobs running, you can afford 50. You better be able to afford 50 a month.

[00:20:44] **Adam Cameron:** indeed.

[00:20:45] **Adam:** Mission critical stuff. Absolutely.

## [00:20:47] How Does it Work?

[00:20:47] **Adam Cameron:** so how does all this stuff work from, you

[00:20:50] **Adam:** So I mentioned, yeah, I mentioned it's a, it's a webhook, right? So when you, we'll come, let's circle back to the API aspect.

[00:20:58] **Adam:** Well, let's just start with like what they call click, click ops, right? So you sign into the platform. there's a big new snitch button. You click that and you give it a name. you can give it some tags, taxonomy type stuff, you can give it an email address that you want to send to should, it fail to check in. There's a notes field if you care to do that, and then there's two other sort of important things. So it's got a type, which is just a simple, they call it heartbeat. so, Probably the, the, it's where everybody's, it's what everybody's expecting, right? It's the, the basic, you know, my job runs once an hour.

[00:21:33] **Adam:** I want the, the thing to run once an hour. and then the, the, the part where that becomes a little bit, frustrating or difficult is, how do you know when the job is actually late, right? So if, if the job is scheduled to run once an hour, then really, you know, if it, if it checks in at noon and then you're expecting A check in to happen between 12 and 1.

[00:21:57] **Adam:** Well, really, should you wait until 1? Should you wait until 1. 05? Because, you know, if the check in that happened at noon is because the job was triggered to run at noon, it's not that it takes an hour to run. It's that that's when it was roughly triggered, and

[00:22:12] **Adam:** maybe it took a minute, right? And so then the 1 o'clock one is for, the job that's triggered to run at 1 o'clock.

[00:22:18] **Adam:** So maybe it's 1. 05. Maybe it's 1. 07. Maybe it's 1. 15. It depends on how long the job is going to take. So, my understanding is, and this is a little bit outdated since the last time I read their docs, maybe it's Maybe it's changed, but I don't think so. This basic, they call it heartbeat type, is it waits an entire extra duration, right?

[00:22:35] **Adam:** So if the job is set to, expect a check in once an hour and it checks in at noon, the one o'clock goes missing at two o'clock is when they will send the alarm up. and that's, that doesn't sound terrible for something that you're expecting to run like on an hourly basis, but when you're expecting, a, a daily job or even, you know, like a weekly job.

[00:22:56] **Adam:** then you, you, certainly don't want to want it to wait a whole extra week, right? and that's why they offer what they call a smart, type, which is it kind of learns what to expect. the, the difference being with the, the more basic ones, you have a lot more tightly grouped, range. I guess, is that the right wording?

[00:23:15] **Adam:** so with the, the basic, you can go from my job runs once a minute, two minutes, three minutes, five, ten, fifteen, twenty, thirty. Hour on up to like a month. If you choose smart, the minimum that you can choose is one hour. But the smart thing is it figures out where in that hour it can expect the job to check in.

[00:23:36] **Adam:** And then it notifies you. There's some sort of intelligence baked into here. And so it notifies you sooner after it has gone missing.

[00:23:45] **Adam Cameron:** Going back to that drop down on the heartbeat one that you're showing

[00:23:50] **Adam Cameron:** before. That got you right when you got the values before one minute, two minutes. So what you're saying, if I set my heartbeat to be three minutes, I'll get an alert at six minutes. That was the wrong number for New Zealand, wasn't it?

[00:24:03] **Adam Cameron:** Six, the number after five. Sorry. No,

[00:24:08] **Adam:** That wasn't intentional at all, was it

[00:24:10] **Adam Cameron:** it actually wasn't.

[00:24:11] **Adam:** yes. So if you, if you have a job that runs every three minutes, basically, I, the way that I think about it is that, job would fail twice or it would have the opportunity to fail twice before I would be notified with a, with a basic heartbeat. which is still really good.

[00:24:27] **Adam:** You know, how many times in our careers have we had a job go missing for a month or two months and you're like, Oh, that's not good.

[00:24:35] **Adam Cameron:** Yeah. Yeah.

[00:24:36] **Adam:** but yeah, so then there's the, the smart type, which, like I said, is a minimum of an hour. and then that one also goes up to monthly.

[00:24:42] **Adam Cameron:** Okay, and the way that, say you set that for an hour, right, and it will gather some metrics, I guess, initially, and hone its accuracy, so if it, it'll see a task running at 1pm, 2pm, 3. 04pm,

[00:24:56] **Adam Cameron:** 3. 59pm, and it's going to go, okay, there's kind of a delta for about five minutes on this stuff, so I'll, if the next one doesn't run by 15 should we say,

[00:25:05] **Adam Cameron:** then it will go okay yeah that's outside that delta of five minutes that I've become accustomed to then that's probably a problem I'll send them a ping.

[00:25:12] **Adam:** Yeah, basically, and you know, not everything, this is not an alerting service. I just want to make that clear for the listener. this is not something, this is not the thing that gets me out of bed in the middle of the night. This is the thing that knows that I should be, that, that, you know, the job has gone missing.

[00:25:25] **Adam:** And then we have, we have an integration with our Ops Genie,

[00:25:29] **Adam Cameron:** ah and that's,

[00:25:29] **Adam Cameron:** when you were saying there were the webhooks before it sends a webhook to Opsgenie and Opsgenie does the

[00:25:36] **Adam:** right.

[00:25:36] **Adam Cameron:** messaging. Sorry I don't know

[00:25:37] **Adam:** yeah, so I, I have a I have the OpsGenie app on my phone and I have it set up so that even if my phone isn't do not disturb and silent and all that, it can, it has access through settings on the phone to like turn on sounds and, and ignore the do not disturb and place this really loud, annoying gong sound at like full volume because I need it to wake me up.

[00:25:58] **Adam Cameron:** I need something that's going to like wake me up without, giving my wife a heart attack. So that's kind of what we've settled on. yeah.

[00:26:06] **Adam Cameron:** no fair enough, gotcha. See that's, that's good that you mentioned that because I thought This was the thing that was doing the alert messaging as well.

[00:26:14] **Adam Cameron:** just from, you know, the quick discussion we had in

[00:26:16] **Adam:** Sure. Yeah. I'm trying to find an example. So there's a, a pretty neat thing that I've noticed. I wish I could remember which one of these jobs. Okay. Yeah, here we go. So, let me see if I can describe this audibly for the listener. So I've pulled up one of my snitches and we're looking at the, the activity of check ins.

[00:26:36] **Adam:** and the, so it shows this particular job is set. It's a smart.

[00:26:43] **Adam:** snitch, with an interval of a day, so it expects the job to run once a day. so we've got it, and it shows me what the webhook is. There's a URL that we just, you know, make a GET request to that URL. and it says, okay, thanks for letting me know the job is running.

[00:26:58] **Adam:** and then on the right side of the screen, I've got, it shows like a list of days. and it shows a checkmark with a timestamp of when the, when the job checked in. And so we can see, you know, so down here at the bottom of the list, They're all, you know, just like 12 noon, basically, which I think is even, it's like noon UTC.

[00:27:17] **Adam:** and, the checkbox is like, centered in that, in that,

[00:27:21] **Adam Cameron:** hmm. Yeah, I was wondering what

[00:27:22] **Adam Cameron:** that

[00:27:22] **Adam:** Div, right? So just picture a div, it's like a, a line with, brackets on either side of it, I guess you would say. And it's pretty much, pretty much centered in there at 12 o'clock. And you'll see, you know, even though the check ins are, as we move up into more recent days, even at, even though we see the, timestamp are still right there, noon or 1201, the check mark is moving closer to the right edge of that And what I'm taking that to mean is that This is showing that it's expecting, so I think this most recent one, it looks like it's, you know, maybe 15 minutes behind or something like that.

[00:27:58] **Adam:** it's, I think it's what it's showing here is that if this 12 o'clock check in were to go missing, it would notify us probably by 12. 15, 12. 30, something like that. Even though it's a, it's only a day job, it's, it has detected the pattern of like, we are right here at 12 o'clock checking in.

[00:28:18] **Adam Cameron:** I see. Yeah, yeah.

[00:28:19] **Adam:** And, and so it recognizes like, okay, there's a little bit of room for variation.

[00:28:23] **Adam:** Let's not be too, too hyper vigilant about like, well, it's 1201 and the job hasn't checked in yet, let's give it a minute to breathe. But even though this is a once a day job, it's going to notify me very soon after if it

[00:28:35] **Adam Cameron:** I guess an important thing in the visualization here that you and I can see and the others obviously can't is, there's about a week and a half's worth of matrix there. Back down maybe between nine. it's going. Yeah, OK, well, if I don't get one by November 30, then I go, well, I better tell him, I suppose.

[00:28:50] **Adam Cameron:** And as we go up to more recent ones, it goes, maybe it's not just the next day. Maybe I'll, if it doesn't happen by 11, by, 11. 15pm, maybe I'll trigger him. And then the next day's one is actually maybe 9. 45pm I should be telling him. And it's getting more confident about, it's learning, in a primitive sort of way.

[00:29:13] **Adam Cameron:** or when it should start panicking.

[00:29:14] **Adam:** Yeah. It's, it's slowly tightening the window in which it's expecting

[00:29:18] **Adam:** that

[00:29:18] **Adam Cameron:** better way of describing it.

[00:29:19] **Adam:** Yeah.

[00:29:20] **Adam:** It, it only just occurred to me as I was, about to say it to you. So, I'm not,amazing at

[00:29:26] **Adam Cameron:** It's good when you're describing something to someone, you, you learn a lot more about it yourself. Because you,

[00:29:31] **Adam Cameron:** you have to actually think about it rather than just go, ah, yeah, I kind of know what that stuff is.

[00:29:35] **Adam:** So while we've got this one snitch open, I can show you, it's got like these three tabs here across the top. It's got Activity, Setup, and Settings. Alright, Settings is the thing that you, we saw, it's a form, that we filled out when we were creating this snitch, with just all of the choices that were in there.

[00:29:49] **Adam:** and then the, so that just leaves the Setup tab. And so this is basically, a whole bunch of different options for like cut and paste of how to implement this, right? So the big thing at the box, at the top, is it just gives you a big like easy copy and paste. Here's the URL. Send a GET request to this URL and your snitch will have been checked in.

[00:30:06] **Adam Cameron:** Cool. And that's got like, it's sort of GUID on the end of it, but it's

[00:30:09] **Adam Cameron:** some sort of short hash, like a, like, like a hash from GitHub, kind of length type thing.

[00:30:14] **Adam Cameron:** So, you know, unique

[00:30:15] **Adam:** It's like a 10 or 12 character, like a SHA type deal. Yep. And, and so, you know, we've got that and then it shows like curl examples, you know, how to do stuff from the command line. Different approaches for different things. And then along the left here, you know, so that's just HTTP basics, you know, so that's, that's applicable to anyone, but then if they've got, okay, well, you know, if you happen to be a Ruby user, here's the Ruby gem, here's how you install it.

[00:30:38] **Adam:** Here's how you use it. There's Python. You can check in via email.

[00:30:43] **Adam Cameron:** that they don't list ColdFusion down there, Adam.

[00:30:45] **Adam:** Yeah. I mean, can you imagine? Why? then I, they have, a field agent, which I think is just like a, it's a, an app like this, the way that they're using it here. It looks like it's a, An application you can install on the command line. So instead of doing curl, you

[00:31:01] **Adam:** just call their program and pass it some arguments and it'll, it'll do the thing.

[00:31:07] **Adam Cameron:** Oh yes, the DMS, oh yeah, DMS, of course, DMS. So, what Adam's showing me is, is the equivalent of something you type into Bash or something like that. So it's like DMS, dash S and then the, hash or whatever it is, and a path to a shell script to run. So that kind of makes, you can install that locally as an agent on the operating system.

[00:31:30] **Adam Cameron:** Okay.

[00:31:31] **Adam:** Right, yeah, so if you're using cron or something, then this would be like the copy, this would be the command that you would drop into cron and say like, it looks like the way that, if I'm looking at this correctly, it looks like they say, you know, you call this command and you pass it a shell script or whatever as one of the arguments and it'll run the shell script and then after it completes, then it will check into the snitch for you.

[00:31:52] **Adam:** And so you just copy and paste that into your cron tab as the, the command that you want it to run. And it does both for you in one go. And you don't have to like change the code of the job itself.

[00:32:03] **Adam Cameron:** of the sort of usage docs right there

[00:32:06] **Adam:** Yeah,

[00:32:06] **Adam Cameron:** in the application.

[00:32:07] **Adam:** So if we take a second and zoom back out a little bit, I've gone to the like the main screen of what I see when I log in here. I know it's got a list of all my snitches and at the top it shows there are 20 snitches pending. So that's like 20 snitches that have been created and have not yet been checked into.

[00:32:23] **Adam:** Shows that one snitch is missing. So I've got

[00:32:25] **Adam:** this one

[00:32:25] **Adam Cameron:** the definition of checked into in that content?

[00:32:28] **Adam:** So, really what it means is that it has received that HTTP request with that, that hash that we saw.

[00:32:36] **Adam:** Um, right. And so you create the job and then you could just let it sit there and never do

[00:32:41] **Adam:** anything with it. And that's, that's the state that these are in. Right.

[00:32:45] **Adam:** and then this next one is missing, this like sort of blue question

[00:32:50] **Adam Cameron:** Yeah. Right. That correlates across the other side of the table. Okay.

[00:32:54] **Adam:** yep. And so you can see, you know, this job. If I open it up, has had a couple of successful check ins, but then for whatever reason, today has not checked in yet. and so, I need to go investigate that. Probably as soon as we're done on this call, I'll go dig into that. but it's not a mission critical thing and hasn't been sending me alarms, which has

[00:33:13] **Adam Cameron:** Right. And that's one that's been set up for an hourly. That's why you've got in that sort of activity log thing on the right hand side, there's an entry every hour going, um, hello.

[00:33:21] **Adam:** Yep. Yeah. Yeah. So the windows that it lists here are like 19.

[00:33:26] **Adam Cameron:** Okay.

[00:33:27] **Adam:** So we talked about pending, missing, and then it's got paused. So you can say, you know, I've got a snitch and it, the job is broken and it's not mission critical. So I'm just going to let it sit there while I'm doing something more important for right now.

[00:33:38] **Adam:** But I don't want the alarms to keep coming. So you can just pause the snitch and say like, go, go into dormant mode. And one of the very nice things about it is that it will automatically unpause If and when it is next checked into. So the job starts working again,

[00:33:52] **Adam Cameron:** Oh, okay.

[00:33:54] **Adam:** you know, goes back into active mode and, and does its job.

[00:33:58] **Adam:** Which is very nice.

[00:33:59] **Adam Cameron:** It's kinda like, it's okay if you don't hear from this one, but back to business as usual. Once you do, start

[00:34:05] **Adam:** yes, exactly. So then I've got, it shows a 248 healthy right now.

[00:34:11] **Adam Cameron:** Okay.It also goes to show that from, from the, the UI here, there's a little green circle and they've tried to fit in 248,

[00:34:18] **Adam:**

[00:34:18] **Adam:** yeah, you know, the, I don't think that they have too many customers that have 300, you know, three, three digit snitches. Or if they do, maybe they just don't care because

[00:34:28] **Adam:** it's fine. Right?

[00:34:29] **Adam Cameron:** Yeah,

[00:34:29] **Adam:** Right. Yeah, exactly. So. and then along the, the side of the page here, we've got like a list of all of our tags and it shows, you know, the same status, indicators along them.

[00:34:41] **Adam:** So you can see, okay, you know, for this particular customer, I've got 18 that are healthy, one that's paused, two that are pending.

[00:34:46] **Adam Cameron:** okay, right, yep, yep,

[00:34:48] **Adam Cameron:** okay.

[00:34:49] **Adam:** And so you can just go,

[00:34:51] **Adam Cameron:** At the top of the list, if you click on the, each of those icons, there's a filter on them, so if you click on, on the, on the, go back the list, sorry everyone,

[00:35:01] **Adam Cameron:** um, if you click there, does it, does it filter, does it filter on, on those, so you can only, for argument's sake, only see the paused ones,

[00:35:09] **Adam Cameron:** or only see the

[00:35:11] **Adam:** which is a little unfortunate, but one nice thing is it does sort by that. So

[00:35:16] **Adam:** the, the, the missing one is right there at the top of the list, because that's going to be the most important than your pending ones, because obviously you created them for some reason and they haven't checked in yet.

[00:35:24] **Adam:** So that's kind of important. Then under that you have all your, all your active ones and down at the very bottom of the list is where all the paused ones show up. So. It doesn't have filtering, but I do feel like there's a little bit of thoughtfulness there, so

[00:35:35] **Adam:** that's fine. And then, in for each tag, you can click on a tag and it'll show you just the snitches for that particular tag.

[00:35:43] **Adam Cameron:** Okay, so you've got a list of what looks like various colleges, down the side there, and so each of those will on the, I'm just thinking about your multi tenanted thing, they've got different numbers of switches, is this, rather than all having the same number, is this just because this is all, it's not multi tenanted yet, so

[00:36:02] **Adam Cameron:** some of them don't have some of them, or,

[00:36:04] **Adam:** yeah, so, each school could opt into a variety of different modules. Like, so we have One of our, one of our less popular modules is our online, Alumni association, membership organization. And so you can like pay to be a member of your alma mater's alumni membership.

[00:36:23] **Adam:** Alumni association. Wow, man, I cannot think today. It's my day off.

[00:36:27] **Adam:** Um,

[00:36:28] **Adam Cameron:** he was your idea to do it today.

[00:36:32] **Adam:** And, so For the schools that have that module, they will have some additional jobs that are specific to that module. So that's why the numbers are not the same school to school. Yeah.

[00:36:42] **Adam Cameron:** Yeah. Make it makes perfect sense. Sorry.

[00:36:44] **Adam:** And so, as we start to move toward talking about the API, I think this is a good time to mention. So I think that we are in a little sense here overloading what the tags are intended for, right?

[00:36:54] **Adam:** So like when you're just creating these with ClickOps, you know, it makes sense to tag things and try to group them in a way, where you might want to be like, okay, like show me all of the membership. You know, so I can see, you know, who, who has things that might not be working or whatever for membership, that sort of thing.

[00:37:12] **Adam:** for the automation that I built with using the API, I needed some way to be able to uniquely identify Uh, snitch without knowing its ID, right? So I get a request saying I need to check into the job, right? I'm the membership, payment collecting job, and I need to just notify you that I've completed.

[00:37:33] **Adam:** Well, I don't want the job to have to know, okay, well, I'm for school ABC. So that's this SHA and I, or I'm for school XYZ. So that's this SHA. I just wanted to say, Hey. Go, I ran the job, and here's the school name, right? And then, so I built this thing that stands in the middle there, and says, okay, it accepts membership payment job for this school, and then it uses the API to go look up what is the snitch for the membership payment job for this school, returns that to the job, which then sends the, the check in, the HTTP request.

[00:38:06] **Adam:** and so to make that work. Basically, we're, we just use their API to cache locally a list of all of our snitches. so we cache a list of all of their snitches. And then, I need to find a way to, I could have just done it with like very specific syntax in the snitch name, right?

[00:38:26] **Adam:** Like, you know, customer colon, job name, colon, something, who knows.

[00:38:30] **Adam Cameron:** but then you're just moving the metadata into the name and, and s getting that a bit.

[00:38:34] **Adam Cameron:** So

[00:38:35] **Adam:** could have, yeah, but since they have tags, I was like, okay, well, let's, let's try that. So, all the job, snitches here, you know, they have a tag that is, like, you know, a specific prefix and then the job name, right? So the prefix just tells me like, this is, this is a job tag. It might as well just say job colon here.

[00:38:53] **Adam:** Adam's showing me a list of tags, against one of his clients. And, and some of them are like, . That's what you call your company, isn't it?

[00:38:59] **Adam Cameron:** and another one, email marketing and another one. the name of the institution. And then there's one that's all letters and underscores and stuff like that, and those are the ones that you're talking about, your job specific ones, yeah.

[00:39:10] **Adam:** Yeah, so, and, you know, the one you said, it's the name of the institution. This is one I had to go through and clean up because there were a lot of them in here that had, you know, mixed case, right? Like only the first letter was uppercased or all lowercase or all uppercase, whatever. So I, I recently had, fortunately they have the API, so it made it very easy to like, okay, find everything that's, that has one of this tag.

[00:39:29] **Adam:** Remove that tag and replace it with this tag that's like the same thing but all u-case or whatever. so that was nice to be able to clean that up, especially when you get into the point where you have 300 of these things. and then, so, so that's the two tags that we're currently, like, using for that automation is there's one that identifies the customer and one that identifies the, the job that's being run.

[00:39:49] **Adam Cameron:** Makes sense.

[00:39:50] **Adam:** and so I use that to look up what the snitch is, return that, and, and there you go, Bob's your uncle. And then, so they do have an API, if I could pull up their docs here. It's, it's pretty basic, like you can, You know, list all of your snitches, add a snitch, you can do updates, like I talked about.

[00:40:05] **Adam:** I modified the tags, that sort of thing. I'm sure that there's a lot of stuff in here that I'm not making use of, but, you know, it does what I need, which is great. And there's a node module for it too, which is handy. Takes most of the heavy lifting, I just like, here's my API key, and I'm calling the update method, or whatever.

[00:40:23] **Adam:** Like, it's not, it's not difficult.

[00:40:27] **Adam Cameron:** That looks easy enough.

[00:40:28] **Adam:** Yeah, for

[00:40:28] **Adam Cameron:** And they've got examples, and it was showing me the docs where they've got full examples there of what to run, explaining everything.

[00:40:35] **Adam:** Yeah, curl examples and, and all kinds of good stuff here. so I guess that's pretty much it about this particular service. Do you have any other questions I could answer for you?

## [00:40:43] Can You Add Functionality to Snitches?

[00:40:43] **Adam Cameron:** Oh yeah, one question I had is there. Is there any ability to build any more intelligence into the snitches? In an example, I just was thinking that could it have the intelligence like I've started this So,

[00:40:57] **Adam Cameron:** I'm running a job, right? We run a lot of scheduled tasks. I've started this job

[00:41:01] **Adam:** right. Like I

[00:41:01] **Adam:** started

[00:41:02] **Adam Cameron:** and then, yeah, and then there's no finish,and we don't care if it starts and stops, we don't care how long it takes, on the whole, but if we go, this one started, this one never stopped,

[00:41:12] **Adam:** Mm

[00:41:12] **Adam Cameron:** we probably want to hear about it before it gets around to its full cycle, because it might be, again, as you say, a weekly job, or any other sort of business rules?

[00:41:21] **Adam Cameron:** Can you give it like a lambda or something that it can run that comes back with a true or false based on some stuff? Send it or something like that?

[00:41:32] **Adam:** of

[00:41:32] **Adam Cameron:** okay. It's as simple as that. You basically just ping the URL

[00:41:36] **Adam Cameron:** and go take note of that and either tell me if you don't get another one of these within time, within two time periods, or work it out for yourself how often to get it.

[00:41:44] **Adam Cameron:** No, that's, that's, that's, that's cool.

[00:41:46] **Adam:** So, you know, there's different, ways to think about it, too. So, for example, I'll just throw out a couple of things that we've had to, to think about ourselves. one is, you know, sometimes you have scheduled jobs that run, say, every 15 minutes, except you've got this, database maintenance window where, like, it doesn't run

[00:42:01] **Adam:** overnight for these two hours or whatever, right?

[00:42:04] **Adam:** And so what we do to cover our bases in that type of situation is we'll just have a cron job that does nothing except. A check in as if it were the job running,

[00:42:13] **Adam Cameron:** Let's see if I can

[00:42:14] **Adam:** right? Fake it or, and, and, you know, that works, but it's a little bit messy. Cause now you've got that snitch set up in two different places. The approach that we're moving towards now

[00:42:25] **Adam Cameron:** You can have a switch adapter though,

[00:42:27] **Adam:** you could,

[00:42:28] **Adam Cameron:** all the code and you just call that. But yeah,

[00:42:30] **Adam Cameron:** I get your point though.

[00:42:30] **Adam:** So what we do now though, is, we build the maintenance window into the job itself. So the job knows, okay, if it's between this time and this time, I'm

[00:42:39] **Adam:** not supposed to actually do anything. And so the, the. The scheduler, the cron server that we have running can still call and execute the job. And then it says, okay, well, it's a maintenance window.

[00:42:48] **Adam:** So the only thing I'm going to do is check into the snitch.

[00:42:51] **Adam:** And then I'm going to shut down.

[00:42:52] **Adam Cameron:** We have had to deal with this situation just recently and that, I mean, we did it a different way. now I wish we'd had this conversation earlier because that sounds like a better way of doing it, to be honest. we've just got our, our, hosting provider, Reserves the right to shut everything down between 1 and 2

[00:43:08] **Adam Cameron:** a.

[00:43:08] **Adam Cameron:** m. every day, and we process 24 7, 23 7 as it turns out, and I've got them to call a curl that tells the application

[00:43:20] **Adam Cameron:** stop running the scheduled task for an hour, and then at the end of the maintenance window that goes, yeah, okay, you can start them all again, whereas we could have baked that into a task runner,

[00:43:30] **Adam Cameron:** I guess, but yeah, this is, in this window, just return true.

[00:43:33] **Adam Cameron:** send the snitch and return true. Yeah,

[00:43:36] **Adam:** So you're, you said that they reserve the right to shut down between one and two or 12 and one, whatever it is, but they don't necessarily always do that. And so then they, the, they're called, they're sending you a webhook to say, okay, we're actually going to do it because we have

[00:43:48] **Adam Cameron:** yeah, they don't, they don't shut them all down every night of the week. It's just, just on the nights of the week that they do need to do the maintenance because before we just let everything collapse in a heap and

[00:43:57] **Adam Cameron:** our tasks, the work that our tasks do is such that it doesn't matter. if it, it will, if it falls over whilst processing a record, it will back it out and go, yeah, I still need to do this one next time around.

[00:44:10] **Adam Cameron:** So it's pretty robust, but we do get a see if your email is going on this task failed, this task failed, this task failed, and we just know if the timestamp on the email is between one and two, just delete them all. Which is, you know, it was just annoying rather than an actual problem. But you know, problem people need to solve, so it's good to have options there to do it, I guess.

[00:44:29] **Adam Cameron:** the other question I had, and this is a random one that doesn't impact us, but just whilst you were showing me the, the delta and the learning part. Kind of, what about. I don't know if this is a real world thing. What about if you're sending a snitch too frequently? Like, you're supposed to get one of these an hour. If you're getting it more frequently than one an hour, is that actually a problem in itself?

[00:44:53] **Adam:** That's a really good question. I've never thought about that. I don't think that the, I mean, I know for a fact, if you check into a snitch more often than it's expecting, it's not a problem. you know, the, it's more of like a gone missing than a too

[00:45:05] **Adam Cameron:** Yeah, yeah, yeah, yeah. I mean, I don't have a situation that covers that. It just came up there.

## [00:45:10] How is a Snitch Window Defined?

[00:45:10] **Adam Cameron:** Another question comes up now. Let's say your snitch is, your process is due to run hourly on the hour. I If one runs at the half hour, is the next expected one on the hour, or is it a timer from when it last got one and goes, okay, well, I'm not expecting the next one until half past three now, rather than

[00:45:30] **Adam:** I don't know. That's, that's another very good question. I mean, my instinct says, yeah, I mean, The way that, you know, when we're looking at these ones that have checked in, when, when we're looking at that, that time window, you know, it, I feel like, I don't know how they decide what the start of that time window is.

[00:45:48] **Adam:** Now, I, I think the one that I pulled up here at random to show you ended up being one of the smart ones, because they're, all the check marks are toward the end of the window, but, yeah, I, I, I don't know. I, I think

[00:45:59] **Adam:** It would make sense for it to be a stopwatch starts now. Right. And the thing is, when you, when you configure one of these, you don't give it a time, a start time, right? You just say, this is a job that's going to run once an hour, or, or you configure the snitch to, maybe that's what it is. You're configuring it to say, I want it to check in at least once per hour.

[00:46:20] **Adam:** And, and I don't think that that means like a calendar hour or a clock hour, right? Between 12 and 1. It's just, I think if that first check in comes in at 12. 37, then the second one is going to expect by 1. 37.

[00:46:32] **Adam Cameron:** and that's the analogy of the dead man's switch thing as well, or the the dude in Lost, typing in the number, every 42 minutes or whatever it was, at the time it starts from when it happens and that's kind of the thing that you're looking for. Lost might be too long ago for

[00:46:50] **Adam:** That one I managed to, you're talking about the TV show

[00:46:52] **Adam:** Lost, right? So that I, I managed to, avoid the, the disappointment. The only episode of Lost I've ever seen, the only episode of Lost I've ever seen is the finale,

[00:47:03] **Adam Cameron:** Okay, well

[00:47:04] **Adam:** I had no idea what was going on. Okay, I had, I had no idea really what was going on, who the characters were, obviously, or anything.

[00:47:10] **Adam:** I was visiting a friend and he was watching the finale. I'm like, okay, sure, yeah, he was

[00:47:15] **Adam:** very disappointed. that's okay, tangents happen on this show, as you're familiar.

## [00:47:20] What Happens When a Snitch is Missing?

[00:47:20] **Adam Cameron:** so tell me now, so you, you don't post your, or you don't submit to your, you don't, don't send one, it then goes, right, I need to fire a web hook. or I need to do something. We've not looked at that side of things yet.

[00:47:34] **Adam Cameron:** Mm-Hmm.

[00:47:34] **Adam:** Okay. Yeah. Good question. So, when you're setting up a snitch, one of those fields, initially is you can give it an alert email and that's optional. You don't have to have anything at all. and so for record keeping purposes, we do have it sent to our help desk account just so that we have a list of all of the times that they, went missing and when they came back in, makes it easy to like have a log basically in my email.

[00:47:57] **Adam:** however, not on per snitch basis, but sort of like at the, at the top level. They have an integrations section, and so you can do webhooks, you can do, so they have, oh, this is, interesting to me. I haven't been in here in quite a long time. So, we've got one configured for Slack, which is interesting because we no longer use Slack as our team chat.

[00:48:19] **Adam:** Now we're on Discord. but it's still in there and I, I knew it was still going to there, but that's fine. And then I've got this, other icon as a, the, sort of the, Internet, community agreed upon symbol for a webhook. I've seen that on like Zapier, I've seen it on a bunch of different sites. It's like three dots, red and black, sort of

[00:48:36] **Adam Cameron:** Oh, you're looking, because you'd highlighted a, a good when you said that thought. Really

[00:48:39] **Adam Cameron:** what they settled on was. Four CF 7, 4, 3, 1 5.

[00:48:44] **Adam:** Yeah.

[00:48:45] **Adam Cameron:** And that's I shouldn't have said that. That's just

[00:48:47] **Adam:** That's okay, you'll, you'll get quacked. It's

[00:48:49] **Adam Cameron:** Oh yeah. Cool. Can't believe

[00:48:52] **Adam:** Yeah, but

[00:48:52] **Adam Cameron:** I did in almost an hour.

[00:48:55] **Adam:** that's a new record. So, yeah, it's just a

[00:48:58] **Adam:** random webhook, which I've got it hooked up to some service I was using, and I think that this is what is, so it's, you can see underneath it says all snitches, it's sending every snitch, which, ooh, I wonder if I could, like, tell it to not send alarms for when they return, well, like, when they start checking back in, re return to healthy status, I need to, oh, man, this would be so nice.

[00:49:18] **Adam:** so, as we've started to move towards this automation stuff, I've got some sort of planes in the air that I haven't landed yet. Like how am I planning to, separate things out so that like these jobs and these snitches are not mission critical. So don't alarm us. We still want the emails and it's going to send it to our chat.

[00:49:36] **Adam Cameron:** But, like, I can get that when I wake up in the morning. I don't need to be woken up in the middle of the night because an image resize failed. Like, screw you, that's not important. Well to some people find that. Mm-Hmm?

[00:49:47] **Adam:** and so, I, the, the approach that I have been thinking about so far has just been, to use email. So, like, OpsGenie has, an email to alarm gateway, right?

[00:49:58] **Adam:** So, within our OpsGenie configuration, our account there, you can set it up so that it creates an email address, and if you send that email, if you send an email to that address, it will create an alarm and send that out to your team according to your on call rules. and that was the plan going into this.

[00:50:13] **Adam:** I'd say, okay, for these alerts, let's just add, the on call email as, as one of the recipients of alerts for this particular thing because it's important. But it looks like, they support a way to, like, pick a tag, and only send, Alarms for snitches with that tag to this in particular integration.

[00:50:34] **Adam:** That, that

[00:50:34] **Adam:** looks

[00:50:35] **Adam:** interesting.

[00:50:36] **Adam:**

[00:50:36] **Adam:** so, and it shows you an example of what the, what type of web hook that they're going to send. and, and then, that's the, that right there, that's

[00:50:43] **Adam:** the URL that I set up.

[00:50:45] **Adam Cameron:** can send that JSON packet. You show me the notes field, which I presume is the notes field we discussed earlier on when you're setting up the stitch and you can.

[00:50:52] **Adam:** Yeah,

[00:50:53] **Adam:** exactly.

[00:50:53] **Adam Cameron:** sent along anyway.

[00:50:55] **Adam:** Right. So we have a couple that are configured and the notes are like, do not ignore, you know, like,

[00:51:01] **Adam Cameron:** Not like all the other alerts you ignore. This

[00:51:03] **Adam Cameron:** one, don't ignore please.

[00:51:05] **Adam:** the, it's. I mean, you're not wrong because, you know, there are so many snitches, you know, we're at this point where we've got a bunch because we want to have the awareness of when the jobs are failing and when they're not, but we do have, we're, we're just now kind of getting good about segregating important alarms versus critical alarms and, so we've, of the, let's just say 300 alarms that we have, maybe 20 of them I would put as critical and the rest are all just important enough that we need to know about them.

[00:51:35] **Adam:** and so we've got a couple, it's like, yes, if the, if you don't get this job fixed by the end of the day, we can recover it, but it becomes harder sort of situation. So if you can get it done the same day that it fails, then good.

[00:51:50] **Adam:** Um,

[00:51:51] **Adam Cameron:** they need to send in that JSON packet is like a An integer that represents a log level, for, for a degree of urgency. I mean, definitely shouldn't use a word like info or warning or anything like that, but I think the industry has agreed that we just use integers, for those things. So I'm having a go at Ben in your previous, in your previous episode where he went, numbers.

[00:52:13] **Adam:** yeah, the, the discord had a, a fun time chatting over that one.

[00:52:17] **Adam Cameron:** Okay.

[00:52:19] **Adam:** The numbers. Yeah. anyway, so, they've got integrations and what, what, sent me off on that tangent is it looks like they now have an OpsGenie, integration specifically that we're not currently using. So I will be looking into that.

[00:52:31] **Adam:** I've never heard of quad cast or vector. All metamized for that, but then again I don't do this sort of stuff for a living, I guess.

[00:52:40] **Adam:** yeah,

[00:52:40] **Adam Cameron:** Have you heard of all of those? Are they things? No? Okay, that's cool.

[00:52:43] **Adam:** No, I mean, so

[00:52:44] **Adam:** from this list,

[00:52:44] **Adam:** I've heard

[00:52:45] **Adam Cameron:** OpsGenie I've heard of.

[00:52:46] **Adam:** Yeah, obviously you need PagerDuty, Slack, and Webhooks, you know, that's like a DIY, approach. But, and then, so you, you can have multiple people, right? So like that's the, my teammates, and then billing, I don't know. Yeah, okay, so we are, we're paying 80 a month for 750 snitches, which is very, very affordable.

[00:53:08] **Adam Cameron:** yeah, yeah. It's a lot of helpful functionality there, so yeah.

[00:53:12] **Adam Cameron:** Yeah,

[00:53:13] **Adam:** Oh yeah, this, this made life so much better. I, I'm trying to remember what we did before we had this. I don't, I don't know that we did anything. you know what we did? Okay. So before we had Deadman Snitch, we had, we did have OpsGenie set up. And so what we would do is a couple of, you know, just those like super important jobs would be written with like a, sort of a global try catch around the entire job itself.

[00:53:40] **Adam:** Right. And if that catch fail, it caught an error, then it would directly send a message to OpsGenie. So there was, you know,

[00:53:46] **Adam Cameron:** think you've been looking at our code base, when you say this.

[00:53:50] **Adam:** yeah.

[00:53:50] **Adam Cameron:** That's pretty much the approach that we've got at the moment and I'm, I'm looking at this, and actually one thing I was thinking about, you know how I, I, I jokingly said that you could use, if advanced such adapter, for this sort thing. so the implementation was only in the one place. thinking about it now, it'd be a sitter for, and this goes back to the conversation you guys had about logging before, where a, a pointer made on the discord, sorry, for the people that aren't patrons is, is logging is, is more than just sending messages.

[00:54:17] **Adam Cameron:** You could have a log writer. that sends your snitches so you just have a log entry like write log to the snitch log and the handler for that goes off and does the snitch stuff so from anyone looking at the code still just looks like a log entry to make sense it is writing to a log i'm doing your quotes here

[00:54:35] **Adam Cameron:** in a way it's just the log that's on deadman snitch rather than a file

## [00:54:40] What Can You Send With the Alert?

[00:54:40] **Adam:** Yeah, for sure. so I wanted to mention one other thing that I forgot I was going to say earlier. You had talked about like having it be sort of smart enough to know like a start and an end of a single snitch. It doesn't have support for that. I mean, if you're willing to sort of use two snitches per job or per job that you want to track start and end of, you know, you could have like a snitch for the start.

[00:55:01] **Adam:** It wouldn't really correlate between the two, but you would know, okay, like. The start happened and, and, you could like

[00:55:08] **Adam Cameron:** yeah here's a question what can you send with the request can you send metadata with the request

[00:55:13] **Adam Cameron:** Like,

[00:55:14] **Adam:** can send

[00:55:14] **Adam:** a

[00:55:15] **Adam Cameron:** instance, instance, so you can have a unique message,

[00:55:19] **Adam:** Well, so like I'm pulling up some of our code here to show

[00:55:22] **Adam:** you,

[00:55:23] **Adam:** the, when you send your, your HTTP request, right? So you send it with the snitch ID and then you can just do like, you know, m equals m for message. And then whatever, whatever message that you want to send. So in, in some of them, you know, it's like we sent a hundred thousand emails or whatever, that it's not super important the way that we use it.

[00:55:43] **Adam:** I don't know how that would be useful to other people necessarily.

[00:55:46] **Adam Cameron:** it could be a way that you could correlate the start and finish if you

[00:55:49] **Adam Cameron:** sent a job, a job GUID, or something in there, so you would have the message for the first one, message for the second one, I don't know what you'd do with it then after that.

[00:55:59] **Adam:** I mean, you said the way you were describing that job, I think you said it runs like weekly.

[00:56:03] **Adam Cameron:**

[00:56:03] **Adam Cameron:** as a, for instance, there was just an example of you wouldn't

[00:56:05] **Adam Cameron:** want to wait for a week to find out that that, or two weeks, that that didn't run. You want to know within an hour that it didn't

[00:56:11] **Adam Cameron:** run.

[00:56:11] **Adam:** hmm.

[00:56:12] **Adam Cameron:** aren't going to get their money. I'm not going to get my pay. so

[00:56:15] **Adam Cameron:** that's important to me, you know,

[00:56:16] **Adam:** Yep. And then, is it, how long does the job take to run in this hypothetical one you're talking about?

[00:56:22] **Adam Cameron:** three minutes.

[00:56:23] **Adam:** Okay. So, if you wanted to be tricky about it, something you could do is like, check into, have it set up to be like a half hour snitch, right? Give it a maximum of a half hour, and then, so you check into the snitch, and you pass the message of started, and here's the GUID or whatever, and then you could have it, Check in to say finished in the GWT.

[00:56:45] **Adam:** That's fine. And those will show up in that, like, when I showed you the activity log where the, with the check marks, that it'll show the message right there on that screen next to the check mark.

[00:56:52] **Adam Cameron:** Mm hmm. Okay.

[00:56:53] **Adam:** and then you could have it built into the job so that after it sends that finished, you can use the API to pause the snitch.

[00:57:01] **Adam:** So it'll

[00:57:02] **Adam:** pause.

[00:57:02] **Adam:** starts again, the next time it'll unpause.

[00:57:05] **Adam Cameron:** Yeah. Yeah. I can see how that would work. Yeah. And so you could use the APIs at all. Yeah. Yeah. Cool. Handy.

[00:57:12] **Adam:** random thought. we have, we already have like audit logging for our entire application, keeping the receipts of what users are doing and how stuff they're screwing up, so that we can have those receipts handy when they try to blame us for something that they broke or did something stupid with, but. so we, since we have that audit logging built into the system and handy already, we will often say, okay, I'm auditing the start of a job, audit the finish of the job, audit a particular particular order.

[00:57:42] **Adam:** step of the job. We do, for the ones that do some heavy lifting, lots of,cal like calculations in the database or, you

[00:57:48] **Adam:** know, selecting lots of records and we know they could be slow in certain scenarios or something, we will break it down into specific chunks and Track the metrics, the time that it took for each chunk of the job to run, like this step where I want you to select, select the rows that I'm interested in.

[00:58:05] **Adam:** You know, I want to know how long it took to do that. So I'll like, sort of gather all of these metrics as we're going through the, the process. And then in that finish, audit entry, I include the, all the time, the durations of all the different steps.

[00:58:21] **Adam Cameron:** That's fair enough, yeah, and maybe my idea was pushing that job onto the start and finish thing onto the wrong tool for the job anyway, and you're possibly quite right, that should be done more locally,

[00:58:35] **Adam:** Yeah, I don't know. I mean, there's, in this industry, there's a million ways to do any particular.

[00:58:41] **Adam:** Thing, right. So,

[00:58:43] **Adam Cameron:** thinking about it, do you want to know that something started and finished because not getting the snitch that it's finished would, by implication, you don't get it started, right? You care that it didn't run,

[00:58:59] **Adam:** right.

[00:59:00] **Adam Cameron:** so you don't need to go, this one started, this one finished, you just need to look for the absence of this one finished, and that does the job, and that's entirely what decrements, what

[00:59:10] **Adam Cameron:** Slitch does, so it's fine.

[00:59:11] **Adam Cameron:** Yeah,

[00:59:12] **Adam:** Yeah. So yeah, yeah. To, to, to restate, you're kind of just saying like, ignore the started thing. And then if, if the finished goes missing, then it goes missing and that's

[00:59:21] **Adam Cameron:** yeah, yeah, and the only reason we asked the question, I'm just thinking, okay, how can we use this? What sort of things can we do? It

[00:59:27] **Adam Cameron:** wasn't a reformed question, but we got better at it, so

[00:59:31] **Adam:** Well, we've been going for about an hour

[00:59:33] **Adam:** now. Uh, did you have any other, did you have any other questions that you wanted to get to before

[00:59:37] **Adam:** we

[00:59:38] **Adam Cameron:** that was a good intro. I, I, I, I like that. And it, it's been interesting and I, and I like the, our sysop, my sysop friend, Brenda, who a few of the people, listening Will, will know, said, why would you wanna use something like that when you could just use Ops Gen? But I, I think I was mis articulating what it was for.

[00:59:55] **Adam Cameron:** op Gen is the thing that does the alerting. This is the thing that informs Ops Genie, that there's an alert, to be done. So. So that's cool. so that was just an observation, not a question, actually. no, we've got, oh, we've got something to work on here.

[01:00:06] **Adam:** Excellent.

## [01:00:07] Patreon

[01:00:07] **Adam:** So, this episode of Working Code was brought to you by TimeZones, the thing that, meant that Adam and I had to get together and have this conversation on the weekend, instead of during the week, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:00:22] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons. Monte and Giancarlo, you guys rock.

## [01:00:31] Thanks For Listening!

[01:00:31] **Adam:** Adam and I are gonna go do an after show and I have no idea what to expect from that. That'll be fun.

[01:00:35] **Adam Cameron:** No, me neither, but we'll figure something out.

[01:00:37] **Adam:** we're, we're gonna talk about accents and Testing.

[01:00:40] **Adam:** Did I, did I do it okay?

[01:00:42] **Adam Cameron:** nailed it. It's like, it's like I'm hearing myself.

[01:00:47] **Adam:** And so if you would like to get that after show, you can go to patreon.com/workingcodepod. Become a patron of the show and you get access to the extended cut, I guess is what it is, and early access at that. Of every show.

[01:01:03] **Adam:** alright, well that's gonna do it for us this week. We'll catch you next week. And until then,

[01:01:06] **Adam Cameron:** Your heart matters, even if something, you really blindsided me with that, thank you very much.
