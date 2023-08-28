---
title: "067: We Have Feelings On Logging"
description: "The crew talks about different categories of logging, why some logging is required for regulatory purposes, how you can replace certain logs with telemetry and metrics, and why you should absolutely never ever email yourself errors..."
date: 2022-03-23
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/e5076582-aebb-484f-802b-4d3a0d57b1d5"></script><div class="redcirclePlayer-e5076582-aebb-484f-802b-4d3a0d57b1d5"></div>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Under the right circumstances, application and error logs can be magical. They can shed light on how a system is behaving - or misbehaving; and, they can provide a path forward in an emergency situation. But, logs do come at a cost. Not only is there an actual dollars-and-cents cost to aggregating and storing logs, having _too many_ logs can end-up reducing the signal-to-noise ratio which can make it _harder_ to debug a running application.

This week on the show, the crew talks about different categories of logging, why some logging is required for regulatory purposes, how you can replace certain logs with telemetry and metrics, and why you should absolutely never ever email yourself errors... except for when you should; because it's easy; and because we never learn from our mistakes.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/067-we-have-feelings-on-logging.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** So I don't know if that, it just like, it blew my mind how many tracing type things like, oh, request, starting grabbing message from the queue received message from the queue about to process message from the queue passing message off the handler successfully returned message. Right. it's just like, what's the point? Like what, I don't know where those are ever coming valuable. It was very frustrating to see this being happening and it's especially irritating because it took my entire week.

[00:00:26] **Adam:** So you feel better now that you've got that off your chest?

[00:00:31] **Ben:** you. Thank you.

## [00:00:51] Intro

[00:00:51] **Adam:** Okay, here we go. It is show number 67 and on today's show, we're going to be talking about feelings on logging cause we have them. But first as usual, we're going to start with our triumphs and fails. And we're going to start with our resident feelings. Have her been the Dell Ben what's going on, man.

## [00:01:08] Ben's Fail

[00:01:08] **Ben:** feelings, I'm starting us off for the failure. And, so during the COVID period, I don't know if this is related to COVID necessarily, but during this just general past number of months and years,

[00:01:21] **Ben:** I have

[00:01:21] **Ben:** been feeling less healthy. And,my clothing tells me that and just kind of the way I feel when I'm sitting down tells me that I'm like adjusting my pant wastes a lot. And,I knew I was gaining some weight, but I didn't really think too much about it. and today this morning I went to order my first ever weightlifting belt off of Amazon. because I've been having some weird, lower abdominal pain, which I think is like maybe pre hernia ask. And yeah, I figured maybe having a weightlifting belt will allow me. don't keep that under control whether or not that's true, regardless. So anyway, I went to Amazon, looked up one of their weight belts just found like the Amazon, the one that they recommend as the ones they haven't stock. I'm not very picky. And I had to measure my waist in order to get the sizing of the belt.

[00:02:08] **Ben:** Right. And in my mind, I've had a 36 inch waist for years and, to measure it, I was like, oh no,

[00:02:16] **Carol:** Oh,

[00:02:17] **Ben:** that fit? So, uh, I want to talk numbers, but, let's say it's not great. And,

[00:02:25] **Adam:** of

[00:02:26] **Ben:** it was, it was, and to be clear, it went up, it didn't go down in case there was any, uh, and, that did not leave me feeling great.

[00:02:34] **Tim:** I feel you, bro. I figure I've been tracking my weight, but it's like, there's some clothes I haven't worn for two years, like particularly like dress clothes and things like that. Just haven't gone to any like formal events or anything like that. And I put some on the other day, I'm like, okay, Wow.

[00:02:49] **Tim:** This is really really tight

[00:02:52] **Ben:** Yo.

[00:02:53] **Tim:** because I've been so sedentary, but I'm working from home now. I hardly ever go anywhere.

[00:02:57] **Tim:** I don't move much. So it's like, I haven't gained weight, but it's like my shape around my belly

[00:03:03] **Tim:** and good.

[00:03:03] **Carol:** It's changed. Yeah, it had the pageant and I was in my closet. Oh God. When did these zipper stop working? Like what's wrong with these zippers? I think that rusty or something,

[00:03:15] **Tim:** It must be it's the rust. It's the rust. Is

[00:03:17] **Carol:** that's the first.

[00:03:20] **Ben:** Oh man. Yeah. it's just, it's not good. I gotta install some sort of austerity plan where I, my problem. So. I'm not an unhealthy eater. Like the stuff that I eat, most, I eat a lot of fruits and vegetables and nuts, and I have some pretzels and stuff, but like, it's not like I'm snacking on candy and cakes and whatnot. I just have no self control or portion control, so all grades, but I'm grazing, like every time I go into the kitchen to make tea and I drink tea all day long, it's like a little handful of this, a little handful of that. And like, everything is in quantities of handfuls because like, I don't know, I'm just reaching into a container. So,

[00:03:58] **Tim:** but, yeah.

[00:03:59] **Carol:** Good

[00:03:59] **Carol:** luck.

[00:04:00] **Tim:** And this is with me fasting like three and a half days a week. Not eating anything other than just water.

[00:04:06] **Tim:** And it's still,

[00:04:07] **Tim:** so I need some exercise

[00:04:09] **Tim:** is

[00:04:10] **Adam:** impressive, man.

[00:04:11] **Tim:** is, basically what it boils down to. I need some exercise,

[00:04:13] **Carol:** move.

[00:04:14] **Ben:** I gotta get out. And, it's funny. Cause Yana on Facebook, I'd posted this on Facebook about how devastating it was and this woman Yana was like, haven't your genes been telling you that you're gaining weight? I was like, I work from home. I've been in, I've been in pajamas for eight years.

[00:04:29] **Tim:** right?

[00:04:30] **Tim:** Genes. What are

[00:04:31] **Carol:** I've switched to joggers.

[00:04:33] **Ben:** So anyway, that's how I'm kicking it off. Adam, what do you got going on?

## [00:04:37] Adam's Triumph

[00:04:37] **Adam:** I'm going to go with the triumph this week. I kicked my boss out of our get hub org.

[00:04:42] **Carol:** Oh boy.

[00:04:44] **Adam:** Yeah.it's not a scandal. It's not a scandalous as it sounds. so he. He's a bit of a workaholic. That's my phrasing of it. But the, he's a founder of a small business. So as they tend to do, they burn the candle at all seven ends so that they can keep the company afloat or whatever, or that they feel that, the need to do that, I guess, from back when it was just them.

[00:05:07] **Adam:** and so he decided he was going to take a couple of days off to spend time with his family. one of his kids is having a birthday and, probably two or three hours before the Workday would have typically began on his first of two consecutive days off he's in our team Discord sending me private messages about things for work.

[00:05:26] **Adam:** And I was like, you're supposed to be off. And you're on before work. This is not like, okay. Yes, these are valid things, but they could have waited,no big deal. But, go and your time off. And he's like, okay. Okay. And then he went and like sent me more, things that were clearly work and I'm like, get out of here, I'm going to kick you out.

[00:05:45] **Adam:** And then I, he did disappear, but, I kicked him out of the GitHub org anyway, just to like, make that clear. and then like five, 10 minutes later, we just get one Discord message in the general channel. I saw that,

[00:05:59] **Tim:** that's

[00:06:00] **Adam:** but you know, I'm like, I feel like I have a reasonably good, relationship with work when it's time for me to walk away for the day or to take my weekends off. I do, I've talked a lot about being on call and cause that's every third week for me, it's pretty frequent. And I don't get called every night that I'm on call or even every week that I'm on call, but, I feel like.

[00:06:23] **Adam:** it's an important part of mental health and longevity and your job is stepping away when it's time to step away. So

[00:06:31] **Ben:** Yup.

[00:06:31] **Adam:** feeling like I had the ability and the relationship with him to be able to do that, kick him out and I'll let him back in when he's officially back. I feel like at the same time it was like doing him a favor and I really enjoyed it, so

[00:06:44] **Ben:** I was listening to a podcast the other day about, I think it was the stories about people who had went from engineering into management, and they were talking about mentors that they've had along the way. And this one guy was saying that one of the best mentors that he had would come over to his desk at the close of the day and tell him, you have to get.

[00:07:02] **Adam:** yeah.

[00:07:03] **Ben:** if he argued to be like, Nope, you can it on tomorrow, you have to go home. And he said, it was really helpful for him to start setting boundaries between what is work and what is not work

[00:07:12] **Tim:** Yup. Healthy boundaries is what it's all. So, I guess that's it for me. Hey Tim, what do you got going on?

## [00:07:19] Tim's Fail

[00:07:19] **Tim:** So, you know what? I've been on a tear here. I've had a lot of triumphs week after week. Uh,

[00:07:24] **Ben:** humble

[00:07:24] **Ben:**

[00:07:24] **Adam:** Not to toot my own horn.

[00:07:26] **Tim:** all good things must come to an end. My friends. Yeah. So this, I got a failure. just had no motivation this week. I just, I don't know what it is. I just, just have no drive to do anything.

[00:07:36] **Tim:** It's like, I'm actively avoiding work and I know it, it's like, if there's not a fire, I'm not going to jump on it. Right. I mean, I'm doing stuff I'm contributing, but it's at the same time, it's like, okay, Yeah, I know I'll get out of it. I think, I don't know. I'm I try to stay away from the news, but the whole stuff about Ukraine has really got me in a funk, with Russia and Ukraine and just it's just really is messing with my head. so yeah, I dunno. I know I'll get out of it, springtime here in Georgia. Everything's blooming, although we're about to have the 20 degree weather here over the weekend, but, yeah, once it gets springtime, we usually a lot more motivated. Just, I don't know, the more sunlight and everything, but yeah,haven't been the right frame of mind this week, so

[00:08:15] **Tim:** that's all I have to say about that.

[00:08:17] **Ben:** Yeah.

[00:08:17] **Ben:** Those weeks are the

[00:08:18] **Ben:** worst.

[00:08:18] **Adam:** Well, I hope you feel better soon.

[00:08:20] **Tim:** Thanks. How about you, Carol?

## [00:08:21] Carol's Emergency

[00:08:21] **Carol:** So things were going pretty good. You told about a minute ago,

[00:08:28] **Adam:** Oh no. What happened?

[00:08:29] **Carol:** we have a production release. That's my code that just broke. So I have to jump off and support that.

[00:08:38] **Tim:** real time live. You were about to say how great it is to be great

[00:08:41] **Carol:** Yeah, it was literally about talking about how good things are going, but we had something just happened and I need to jump off because I have to go figure out what the heck is happening.

[00:08:49] **Ben:** No worries. Good luck

[00:08:52] **Tim:** Yeah.

[00:08:53] **Adam:** Good

[00:08:53] **Carol:** guys.

[00:08:53] **Tim:** is real life here for programmers, right?

[00:08:55] **Tim:** This

[00:08:55] **Carol:** do together. Yeah. All right. Bye guys.

[00:08:59] **Ben:** later.

[00:09:00] **Adam:** Yeah.

[00:09:01] **Ben:** We need a, we need to add them sad. Trombone alert music.

[00:09:06] **Adam:** I do I have it? Do I have it?

[00:09:08] **Adam:**

## [00:09:08] Audible

[00:09:08] **Ben:** Hello, my smart friends. If you're anything like me, you're either at your desk programming or you're on the go with a busy schedule. It can be hard to carve out time to catch up on your latest books or maybe revisit some of your old favorites. Luckily there's audible.com, which allows you to listen to just about any book, whether you're walking the dog, getting swollen, the gym, or just hiding from your kids.

[00:09:34] **Ben:** And today we've got a special offer just for you. Head on over to workingcode.dev/audible, and pick up a free credit for your first auditory advance. okay. So gentlemen, feelings on logging.

[00:09:47] **Tim:** well, I'm feeling that I'm hoping that Carol has some really good logging so that she can figure out what's going on with her bad deploy.

## [00:09:55] Excessive Logging

[00:09:55] **Ben:** So, if I can set the stage here, maybe for part of this conversation,

[00:09:59] **Ben:** earlier this week, one of the guys, this guy, Brett, from our platform engineering. He drops his message in our main engineering channel and says, all right, we need to kick off this as initiative, cross team, organization wide initiative to reduce the volume of logs that we generate because we generate an insight.

[00:10:18] **Ben:** We generate like three terabytes of logs a day.

[00:10:22] **Adam:** Holy

[00:10:22] **Ben:** and yeah, and it's not like we're some massive multi conglomerate global enterprise. Like we do one thing and we have users, but it's not like we shouldn't be generating terabytes of logs.

[00:10:35] **Ben:** So we have several times gone over our logging limit for the, the log service that we subscribed to. Yeah. It's bananas,

[00:10:45] **Adam:** what's your retention policy like on your logs?

[00:10:47] **Adam:** I'm sure there's some

[00:10:48] **Ben:** 30 days.

[00:10:50] **Ben:** Yeah.

[00:10:52] **Ben:** Yeah. It's crazy. Crazy. if you look at the logs part of, part of the problem with having so many logs is that debugging an issue, like what Carol's about to face you look in the logs and it's the signal to noise ratio is just bananas because it's not that we're logging errors.

[00:11:07] **Ben:** it's like the load balancers are logging every request that comes in. So it's like all the URLs. And then the big issue is that there's a lot of kind of info level and tracing and debugging logs that have been turned on in production for a long time. People just never turn them off anyway. So, the rainbow team, which is my team, we're responsible for a lot of legacy services that nobody knows anything about anymore. Half of them are nodes, some of their men Golang, and, I've been spending my whole week going into those various services and trying to turn off the logging. the tricky thing is, so a lot of times you can just set an environment. That will affect the level of logging that's allowed to go through. I think we as Bunyan in a lot of places, it's a very popular node logging service. but it's like, they're not configured properly because of the, how old the code is. And we had like wrapped it and things and you can't really build these services.

[00:11:57] **Ben:** Like you can't update a lot of these. I shouldn't even be saying this, but like, you can't even update half these node modules

[00:12:02] **Ben:** because then the builds completely break and you can't like the containers won't build anymore. So you have to be very, like very, discreet in terms of how you update the code.

[00:12:12] **Ben:** So I just went through and started commenting out things. Cause that was like how I could affect how much logging was done without actually adding or updating dependencies. And it was just like a hundreds of info level logs and tracing logs. And I'm just like, what are you people doing? Like, why do you need to understand every little bounce through every method? It's it just seems bananas to me. I have found historically that a lot of logging is need when you're fundamentally misunderstanding how our error handling should work. And if you just handle your errors and like log your errors, then you get in your stack traces where you are in an application and you don't need to be tracing everything all over the place. So I don't know if that, it just like, it blew my mind how many tracing type things like, oh, request, starting grabbing message from the queue received message from the queue about to process message from the queue passing message off the handler successfully returned message. Right. it's just like, what's the point? Like what, I don't know where those are ever coming valuable. It was very frustrating to see this being happening and it's especially irritating because it took my entire week.

[00:13:21] **Adam:** So you feel better now that you've got that off your chest?

[00:13:26] **Ben:** you. Thank you.

## [00:13:27] Debug Module

[00:13:27] **Adam:** So we use a node module called debug, originally from the same guy that started, express TJ Holloway check. but he has since moved on to other things. And so now there's like a small set of contributors. I think it's actually probably a large set of contributors that maintain that project.

[00:13:42] **Adam:** But anyway,

[00:13:43] **Adam:** one of the things that I really like about it, which there's many, but one of the really nice things that applies here is,you create an instance of this debug module and you can create different debugs streams. So you can have like an error stream and an info stream and a VRBO stream and whatever.

[00:13:58] **Adam:** and you turn them on and off for actually outputting their logs by changing an environment for. So you can deploy the code with all of those logging statements in it. And then based on whatever your environment variables are, determines how much logs get spit out. So you can affect the logging level by just changing an environment.

[00:14:18] **Adam:** Variable.

[00:14:18] **Ben:** and I think the debug module, you can do some interesting things where you can turn on like certain prefixes for modules. I think

[00:14:28] **Ben:** this is the debug one. So you can say like, I want to turn on debugging, but only in the HTTP module or something like that. And there's some sort of like prefixing

[00:14:37] **Adam:** Yeah. So, the way that we're still figuring out the best way to standardize it across all of our apps and services and tools. But, basically when you create a stream, you give it a name, right? So you could just call it info and then if you, have your environment variable named debug and whatever the value of that variable is it's, it's expecting a comma delimited list of streams to enable.

[00:15:00] **Adam:** So if you say debug equals info, then your info stream gets printed to standard out. and you can do wild. So you could do like info colon star. And so if you have info across, eight different modules, so you can have, info X info, colon Y and Foucault and Z, if our, your X, Y, and Z projects, and.

[00:15:19] **Adam:** That way you can say, okay, well I want all the info level logging or whatever. And so one thing that's really interesting using a node stack where,there's a lot of community modules being used, for example, express makes heavy use of debug and it's got a lot of tracing level stuff, configured in there.

[00:15:35] **Adam:** So if you just say debug equals star and you run an app, it's like two or three terabytes of log data, right? Like, it's a ridiculous amount, but it can be useful. and I found that particularly useful, like during development, too, especially when I'm, passing around like very large chunks of data and sort of massaging it and changing the shape of that data over time To be able to turn on verbose and see that,that the object looks like what I'm expecting it to look like for the next step that I'm about to run.

[00:16:04] **Adam:** But then, in production you just don't turn on verbose unless there's an error. And you're like, well, how is that happening?

[00:16:10] **Ben:** it's interesting. I wonder if, to some degree, our various experiences with languages shaped the way that we think about logging,

[00:16:17] **Ben:** because I grew up in ColdFusion and this is probably not true, but when I was young, It's not like there was an output stream that I knew of ColdFusion was running and you either output an arrow to the screen, or it was just gone.

[00:16:34] **Ben:** You didn't know where it went. Right. I mean, and I'm sure that again, their standard out and standard error, I know this now as a more mature developer, but when I was younger, I

[00:16:41] **Ben:** didn't know

[00:16:41] **Ben:** about things

[00:16:42] **Adam:** Yeah. And then the application log and the system log and.

[00:16:44] **Ben:** Right, right. So, and there was no step debugger or anything. So, you talk to ColdFusion developers and they swear by dumping a board, something goes wrong, you dumped to the screen, then you bought the request so you can see what happens. and I wonder if that has kind of made the, given such precedence to the error itself that I don't often now think about. Just dribbling information to an output stream, because that was like, that was never a, a muscle that I developed when I was, I don't want to say kid when I was just a young man. now in the age of Kubernetes and Docker, where everything goes to standard out, like now I'm thinking more about that, but it's still, to me is more about logs as a mean to aggregate errors across containers. Not so much as a way to just output stream information. But, I dunno,and I noticed, at least I work here, the offenders primarily feel like they're the no JS servers. And I don't know if that's because the stack traces and node have maybe historically not been great or something ColdFusion, you always something explodes and you got, you have a stack trace. It's like 50 items long showing you where everything happened. and I think maybe in no, that has not always been. As dependable or not as robust, or could just be the way that people are logging errors. I'm not really sure,

[00:18:03] **Adam:** probably some combination of all of the above.

## [00:18:05] Logs For Remediation

[00:18:05] **Tim:** so, so for me, it's like, I mean, logging errors is great. because there is sort of an immediate fix, right? An error comes, it's logged. It's, you're alerted to that. There's an error. And then you can usually go fix it pretty quick. For me, it's the, it wasn't really an error. It was an unexpected result in particularly like in my ecosphere, what we're dealing with, we have multiple API APIs are all talking to each other, right?

[00:18:27] **Tim:** So one API is relying on another API for something else. And I ha I basically have to log every response, every call, every response when I got back, because historically they're like, well, why did, why did this payment not go through on this date right here on this thing? And so the only way to find that is if you have a log that says, this thing did this call at this time and here was a result. And so, I mean, unfortunately we don't have terabytes of that stuff going on per day. But, I mean, it'd be nice if it were, but, yeah. I mean, those call outs and those responses backs are extremely important and now I can get rid of them and, in, 30 days or whatever, but yeah, I mean, you have to have that in my opinion.

[00:19:13] **Ben:** Well, I think also that's an interesting, I want to say clarification on logging as an application requirement versus logging as a debugging method,

[00:19:24] **Ben:** it sounds like you're not debugging the application per se. You have a requirement that requests have to be logged, that they can be evaluated, should a payment method be disputed payment not work properly. which I think is categorically different than someone just saying, I made an API call and I'm just gonna log it because why not? Because I needed to do it locally and development. And I might as well just leave it in the code when I ship it to production. Cause who cares kind of.

[00:19:51] **Adam:** I mean, so one thing I will say in favor of those things that like, okay, this method is starting, that type of log statement, the only time I've ever found those to be truly useful is when,the process crashes or times out and you have to go. But where and why? Like, especially if you're in the middle of something like, adding accounting rows to the database and you're in a, you've got money partially allocated, you need to know exactly where it stopped.

[00:20:17] **Adam:** Otherwise you have to go trace through data that could be changing as you're,digging through the data to retrace those steps and make sure all the accounting stuff got properly written. And I've done that. And as it, as a nightmare,

## [00:20:32] Performance Checks

[00:20:32] **Tim:** Yeah. I mean, and those are also helpful for performance checks, right? So a lot of times you have something that performs quite well and your local or your development environments, because you have a small dataset, you move it to production, doesn't perform as well, because you have much bigger data set to work with having those kinds of things where this started here, this ended here can help you figure out which processes is taking long. Right. But that's not something you should have on forever.

[00:20:58] **Adam:** No. So actually that's a really good point. I have a remember many moons ago. One of the things we were talking about here on the show was, a tool that I wrote that kind of acted a little bit like a code coverage tool to be able to detect which of the actions in our application were completing successfully or throwing errors and like how many errors and stuff.

[00:21:23] **Tim:** right.

[00:21:23] **Adam:** that's still running and it's running in production and we haven't looked at the data in a while, but I would be really curious to go look at it because we're still logging successes and failures. And one of the reasons we haven't looked at it is because we wanted to give it a chance to collect a bunch of data and see like, what are the problem actions?

[00:21:39] **Adam:** Is it like a certain report that's always failing

[00:21:41] **Adam:** or something. So that'll be interesting. I'll have to go back and look at that.

## [00:21:44] Logging Vs Metrics

[00:21:44] **Ben:** So one of the ongoing conversations that we have at work is logging versus metrics. So Brett, the guy who launched this initiative to reduce logging costs is, one of his constant,

[00:21:59] **Adam:** Ballywick.

[00:22:01] **Ben:** Yeah. One of his constant Bailey wakes is that, that most logging can be replaced with recording metrics. So instead of saying, Hey, this request started and Hey, this request ended, you should log some sort of a metric that's maybe tagged with the name of the method or the request. And then you can aggregate those metrics and you can see here, none of these air it out, but then suddenly there was a spike in ones that were associated with the failures. And then you can use alerting in your monitoring to, to draw attention instead of trying to comb through logs manually. and as I was doing this log volume reduction, it was actually pretty funny because it turned out that one of the largest defendant. Of logs was in this one node service that started spewing,address, not found errors as it was trying to log metrics.

[00:22:47] **Ben:** But for some reason, the data, the UDP datagram connection, like couldn't bind to a particular port and it was just spewing errors. Every time you went to log metrics and it was locking like gigabytes of errors an hour, which it was just very ironic because the whole point of what it was doing was to try and do exactly the thing he was talking about.

[00:23:07] **Adam:** Yeah.

[00:23:08] **Ben:** it's, I go back and forth on, on things like open telemetry,

[00:23:13] **Ben:** which which like allows you, I don't really understand open telemetry very well, but my understanding is you can use request IDs to trace, call durations across. cost stacks and across services. but half of the logging that I do is like, I don't know what to expect.

[00:23:28] **Ben:** And sometimes I just need to log an error because it's unexpected and like no amount, like it's one thing to see that, that,there's an uptake in errors, but it's another thing to not even know where that was coming from. And I like to look in the logs for errors, because I don't know where they're going to come from. I'm not articulating a thought there very well, but it's hard for me to think about a world where logging doesn't exist, that blogging gets replaced by something more

[00:23:54] **Ben:** high-level.

[00:23:55] **Tim:** For sure. I mean, I'll say this, when you talk about metrics, typically in my mind metrics, I segregate them out from logging, right?

[00:24:04] **Tim:** So metrics are things that I want to track. There are events that take place that they want to track. And so I usually put those in the database. So those are, someone took this action and it's important to me because I may want to run a report on it or I may want to charge them for it. And so those are like database actions. I don't put them in the log because I mean, the logs are messy.

[00:24:28] **Tim:** They're always messy. So stick that in a database and up the counter, this person sent a text message. They send an email, they made a payment, whatever. and so metrics for me had never tend to go in the law.

[00:24:41] **Adam:** Yeah, we're the same way. So we have a table for auditing. Actually we have two one for like admin side and a separate one for public facing like the unwashed masses. it gets a separate audit table and they're different in the way that they're architected. But one of the things that's the same between them is we just have this.

[00:25:00] **Adam:** I think it's either a, just a regular, MySQL text, or maybe it's like a medium text field, but at the intention is it's just a Jason blob. And one of the things we throw in there consistently is all the metrics that we've recorded during that record. So we do measure a lot of things. We don't measure everything.

[00:25:16] **Adam:** but w especially if we think that something might become a problem in the future, we like to throw metrics on it in advance, or once something is starting to become a problem. we know somewhere in this request, there's a problem. So we'll just start to go in and instrument. every section and wherever we can break it down into possible heavy lifts, we instrument those things.

[00:25:32] **Adam:** And then all those metrics get automatically aggregated and thrown into that blob that goes into the audit log. And every request gets at least one audit log. and so that goes into the table for that part of the application. But then, I mean, that brings up a really good point that the, When people say logging, we've already covered like four or five possible categories of things you might log, right?

[00:25:54] **Adam:** Like metrics, error, cataloging, just log statements. Like I'm doing a thing. Here's the ideas that I care about and like auditing actions so that you have the receipts. When somebody says I didn't update that ticket, you can go back. Well, actually you updated it at this time. Now using this browser, and this was your IP address.

[00:26:15] **Ben:** Yeah, it's funny. sometimes you just get into these semantic arguments with people. So there's this ongoing logging versus telemetry conversation at work. And I don't know much about telemetry. So my tool of choice is obviously logging and people will say, well, I don't use it. I don't even have to use log-in because I use telemetry and I know how all the requests happen and I'm like,

[00:26:36] **Tim:** What do you mean by elementary? I know.

[00:26:38] **Ben:** there's like specifications about how you track, requests as they come into analysis. I think open telemetry is like a specification

[00:26:48] **Tim:** Okay.

[00:26:49] **Ben:** and then I I'm I'm talking above my pay grade here, so,

[00:26:52] **Tim:** totally don't know either. So.

[00:26:54] **Adam:** I think telemetry is just a word that means like measuring the performance of different things, kind of.

[00:26:59] **Ben:** yeah. And then open telemetry, I think has a specification about how you it's like a standard data form. about what kinds of things you track across services? So people will talk about how they don't use log-in at all, because they use telemetry and I'm like, well, what do you do when an error comes in?

[00:27:16] **Ben:** And they're like, well, I save it in the trace within the telemetry. And I'm like, so you log your errors. And they're like, no, I'm not logging. I'm using open telemetry or whatever. And I'm like, that's the same thing. Like you're recording errors that happen. Your tool just has a different name. Like, why are we arguing about this?

[00:27:34] **Adam:** An error by any other name?

[00:27:38] **Ben:** But it also makes me wonder now about this conversation that I was having with, the guy Brett, who was saying that all your logs should be replaced with metrics, not all, but most that when I think about logs, as we're talking about earlier in the episode, I think about errors. Like I'm not thinking about tracing and debugging logs because that's like a different gesture for me. So I'm wondering now, if part of what he's saying. The debug tracing info. Like all of those are under his logging umbrella, which to me then would make sense why you'd say, well, we can replace a lot of that with metrics. But when I think about only errors, I'm like, I would never replace only errors with metrics because only errors have all the error information that I need to debug. Whatever is going on, that a metrics not going to help me with like a metric will alert me that something is wrong, but it's not going to give me any information on what to do about it. And that's where the airline comes into place. I don't know. I love airlocks and this is crazy, but like, I'll just look through the error logs, kind of every couple of hours. And I kind of just get a sense of what errors I expect, because unfortunately are. Ongoing errors in the application that we haven't had time to fix, but you get a, it's like a, in the matrix, right.

[00:28:51] **Ben:** When he's staring at the screen with just the little, the glyphs coming down and he's like, I don't even, I don't even see any more, like I just look over there and it's, I see this and that and whatnot like that.

[00:29:01] **Ben:** Yeah,

[00:29:01] **Ben:** yeah.

[00:29:02] **Adam:** which to be fair, I'm quoting from the movie. I'm

[00:29:06] **Ben:** Yes. The coding for the movie. exactly. exactly.so that's what it is. Like I see all these arrows coming through and you develop sort of a, not a sense, but it's like, there's a shape to it. And then when you see a different shape, come in, you're like, whoa, that's weird that shouldn't be there.

[00:29:19] **Ben:** Like, why is that happening? And then that gives you, or it gives me something to dig into a little bit more. And then typically it turns out to be some sort of malicious thing. If someone's trying to scan the system, that kind of stuff.

## [00:29:30] Log Consolidation &amp; Emailing Errors

[00:29:30] **Tim:** Yeah. I mean, so there's two things that, that I want to modernize. I haven't yet to my shame. So, you have a microservice system with, different services running. So typically we're just logging it's Linux system where we're logging to just, file, multiple, multiple nodes right now just. But, so if there's an airy get-go research, you basically have to go log into both in grip and try to find it don't have any log consolidation. I actually think I talked about this, that was a goal of mine to do. Haven't done it yet. Cause you know what? It's like two times a year I ever have to go in there to try to figure it out.

[00:30:10] **Tim:** So it's like, eh, it's not worth the effort. I'm waiting until that becomes an actual possible issue. But yeah. So having a central place to look at the logs from all your instances that are running for the same thing, I know how to do it. I just don't really feel like doing it

[00:30:27] **Adam:** Yeah.

[00:30:28] **Tim:** until it becomes an actual problem. And then the other thing is like, the delivery of like error, logs. And so. Adam, you're going to hate me for this because I know you, have you given talks on this about email airing, sending email errors in email? No, it's just that there's an error and you send an email, but that's what I do. I just it's like the most immediate thing.

[00:30:51] **Tim:** I'm like, oh, this is an error

[00:30:52] **Tim:** there. I can go fix it in like 50 seconds.

[00:30:55] **Adam:** that's where we all start. But the problem, I mean, I'll just do the two minute version of the talk, right? Like the problem is it goes to whose email either it goes to one person's email and then that person could potentially be out on vacation or out sick or whatever. And then nobody knows there's errors or it goes to everybody's email and everybody is burdened with trying to decide, well, oh, Tim we'll take care of it.

[00:31:17] **Adam:** Or has Tim taken care of it? Should I take care of it?

[00:31:20] **Adam:** Now we have to have a conversation. Let's have a meeting so that we can just like, Burden there versus, other systems, you can have like an error logging database. You can like whatever, Reagan or there's all these paid services for it, or there's even open-source products, which is what we use.

[00:31:38] **Adam:** and not only does it have sort of a, an error log or a log dedicated to your errors as they come in and you can do things with that, like have alerts when a certain one goes over a certain threshold, or you can ignore certain types of errors, that sort of thing. but then it's like you were talking about not being able to find them in the noise.

[00:31:58] **Adam:** One of you was mentioning, like, there's, you've got a ton of log statements and you have to like dig through there for the errors. It can be hard to find that needle in the haystack. so yeah, I mean, I think I will ever be grudge to anybody for being earlier on the trail than me. Right. Like we all start.

[00:32:13] **Adam:** emailing ourselves our errors because that's, what's easy and that's what the tool makes easy for us. but, I think when I was a child, I did childish things. Right.

[00:32:23] **Tim:** Right. Well,

[00:32:23] **Tim:** but also it's like, it's not overwhelming me. Right. If

[00:32:26] **Tim:** it got to the point where

[00:32:27] **Tim:** it's like, it's overwhelming, I'll be like, okay, I need a different solution. It's like, I can deal with this.

[00:32:33] **Tim:** I don't want to put the effort in to go that next level of complexity to, addthose things to the system.

[00:32:38] **Tim:** So.

[00:32:40] **Ben:** I also, so I started using a roll bar to record areas on my personal site. but I also still email myself the errors. cause it's usually not a high volume, but I have had times where something will go wrong. Like a, the database will suddenly become, you can't communicate with the database and I'll get so many emails that a postmark, which is what I use as my SMTP server.

[00:33:01] **Ben:** They'll just stop sending emails,

[00:33:03] **Ben:** which you know, is fine for the errors. But if people leave a comment on my site and the emails don't go out, like that's like now the functionality of the site is broken. It's not just that my emails got overwhelmed. other things stop working, which is an unfortunate side effect.

## [00:33:15] CloudWatch

[00:33:15] **Adam:** Yeah. I mean, it's funny because we have all these things. Like I talked about my audit table and that's where we keep our metrics. and we have a separate error log and we have things like when you try to send an error to the error database, if it can't write to its database, but it received like the API is running, it received an error from you, but it can't write to its database.

[00:33:34] **Adam:** It'll email it to us. I've got all these things, but at the end of the day, we still write a lot of stuff to the, our log files, which for us on AWS ends up being CloudWatch. and we do that sort of as the last line of defense, like, yes, we sent this error to our bug database, but just in case we can't get it out of there.

[00:33:52] **Adam:** We're also just going to spit it out in the error log or in the application log. and one of my coworkers has started messing with CloudWatch, I guess, the tooling around, querying through CloudWatch logs has gotten a lot better recently and he's doing things like piping in our Apache access logs and is generating some really cool graphs and stuff from, from those logs.

[00:34:13] **Adam:** and also. He's like proving how useful it is to be able to like, oh, I can find that error. he can actually like queer query CloudWatch logs as if it was a database and it's

[00:34:24] **Adam:** surprisingly cool. so yeah, I mean, like, it's good to have all these tools, but at the same time, like logs as a last line of defense, if everything else were to go down, at least you'd have those logs.

[00:34:34] **Ben:** I think that's something to think about too. Eh, there are times when the application that we're running fails to bootstrap and by bootstrap, I mean, it's spinning up and all of the components are being instantiated, initialized and wired together. And oftentimes one of those components is some sort of a logging service that I'll catch errors and send them to the service. But if the application breaks really early then half the time that login service hasn't even been created yet. And you're suddenly in this sort of defunct state where I have an error object, I need to record it to the standard output stream, but I don't have any of the normal tools. And I'm so terrified of. Serializing something and trying to stuff it in the output stream. So I have, it's like nested levels of try catches where I'll try to turn to a string and then I'll catch that error. And then I assume like, well, maybe some of those fields didn't exist. Then I then start to iterate over and see like, is this actually a string?

[00:35:29] **Ben:** And if it's a string, I can pluck it out. And if it's not, maybe I can see realize it. But that's an a try-catch because there are things you just can't see realize for whatever reason. I don't quite understand, at least not in a simple way. And it's just, it gets really complicated when you don't have all of your tooling ready to go,

[00:35:43] **Adam:** And the other thing I wanted to say about us using CloudWatch so heavily, one of the really nice things about it is that like there's, everything gets its own log stream, right? So if I've got this Lambda function, then that Lambda function has its own, stream of log files. And, you can set a retention, like basically per log stream per application or per microservice.

[00:36:04] **Adam:** And so if we've got one Lambda function, that's like the QA version, we might have the log retention on that set to two days, just in case we forget something is there and we want to go back and get yesterdays. But, in production it might be 30 days or whatever, or if there's a service that, if it's financial data, we're going to keep that for like a year.

[00:36:21] **Ben:** That's pretty cool.

[00:36:22] **Ben:** We

[00:36:22] **Ben:** able to set the

[00:36:23] **Adam:** that way

[00:36:23] **Adam:** we don't have to, we don't have to actively manage our log storage and it just kind of prunes itself.

[00:36:32] **Ben:** That's really cool. Yeah. Cause, cause we use a service called Loggly and I'm by no means an expert in a tool, but I think the retention it's just across the board,

[00:36:41] **Ben:** I will say that in the world of microservices, uh, I have in the past had to develop against a service that I don't actually have running locally. And I will definitely put some try catches and some logs in place with code that I think is going to work. But with the understanding that once this has production, there's maybe definitely going to be something in there that breaks.

[00:37:05] **Ben:** And I just want to log the responses to understand what my assumptions were, how my socials were incorrect locally, which, you could argue, that's not why it's development, but sometimes you gotta.

## [00:37:16] Patreon

[00:37:16] **Adam:** All right. Well then this episode of Working Code is brought to you by the three terabytes of logs that Ben recorded during tonight's episode and listeners like you. If you like what we're doing here, you should consider supporting us on Patreon.

[00:37:27] **Adam:** You can do that by going to patreon.com/WorkingCodePod. We have a bunch of really great people that help us out over there, and we appreciate every single one of them. of course, special, thanks to our top agents Monte and. all of our patrons get early access to an ad-free version of new episodes and they get our after show.

## [00:37:44] Thanks For Listening!

[00:37:44] **Adam:** Do you have a question or a topic that you'd like to hear us discuss? There's a lot of ways to get it to us, like sending it to @WorkingCodePod on Twitter or Instagram, you can join our Discord at workingcode.dev/discord.

[00:37:54] **Adam:** You can email it to us@workingcodepodatgmail.com, or you can even record a voice memo on your phone and email that to us so we can play it on the show. that's going to do it for us this week. We'll catch you next week. And until then,

[00:38:05] **Tim:** Remember your heart matters. Even if you email your errors like me,

[00:38:12] **Adam:** but only. There's a time limit.
