---
title: "155: Software We're Thankful For"
description: "Coming out of the Thanksgiving holiday (and still recovering from our food comas), we wanted to have some fun today and talk about all of the software that we're thankful to have in our lives."
date: 2023-11-29
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/105aba05-8940-4a54-865c-d1e018cfd8a4"></script><div class="redcirclePlayer-105aba05-8940-4a54-865c-d1e018cfd8a4"></div>

Coming out of the Thanksgiving holiday (and still recovering from our food comas), we wanted to have some fun today and talk about all of the software that we're thankful to have in our lives. These aren't sponsors of the show (yet); but, we love them so much that we wanted to share them with the rest of the world. Topics include [Dead Man's Snitch](https://deadmanssnitch.com/), [Overcast podcast player](https://overcast.fm/), [git](https://git-scm.com/) source control, [GitHub](https://github.com/), [Snagit](https://www.techsmith.com/screen-capture.html) and [Skitch](https://evernote.com/products/skitch) screen capture tools, [1Password](https://1password.com/) for password management, [PlexTV](https://www.plex.tv/) for media management, video chat, IDEs and code editors, and basically everything that enhances the day-to-day lives of us developers.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/155-software-were-thankful-for.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** I'm a huge fan of podcasts. I listened to loads of podcasts on 2x speed and I am a huge fan.

[00:00:06] **Adam:** my brother, 2x

[00:00:07] **Ben:** Yeah. Oh, you gots to, you can't be listening to people talk like they're drunk on their 1x speed.

[00:00:14] **Tim:** So you listen to people that sound like they're on meth. This is what you're saying.

## [00:00:39] Intro

[00:00:39] **Adam:** Okay, here we go. It is show number 155 and on today's show we're going to talk about software that we are thankful for because we are nothing if not late to the party. This is, we're recording this on November 27th and it was just Thanksgiving and so we're in the mood to be thankful. So we're going to talk about software that we're thankful for. But first, as usual, we'll start with our triumphs and fails. And it looks like it's my turn to go first.

## [00:01:00] Adam's Triumph - Dead Man's Snitch

[00:01:00] **Adam:** you know what, I'm gonna, I'm gonna tie the two together. So there's a piece of software that I'm really thankful for. It's called Deadman Snitch. I've mentioned it on the show before.

[00:01:09] **Adam:** And, we can talk more about what that is. But basically, my triumph here is that, my, talking to my team, you know, we, we hit this point where we have so many snitches. We, we've actually, for Deadman Snitch. My company has reached the point where we're on the, if you need more than that, call us plan, you know, like on the pricing page, it's like, okay, there's this price and this price and this price.

[00:01:31] **Adam:** And if you need more than that, call us and we'll work something out. So I did, and, that that's where we are. so that's how many snitches we're using. And,

[00:01:38] **Ben:** can you, can you just back up for a second? And when you say that you have a lot of snitches, these are, like, health checks for your software?

[00:01:47] **Adam:** No I'm not gonna do that. Yeah, sure. so we've talked about this not too, long ago. The, this is, so it's called Deadman's Snitch. S N I T C H. but it is conceptually sort of a software implementation of the concept of a Deadman's Switch with a W instead of an N. Which is, you, you press the button down and and that, like, arms it, and then if you ever let go of the button, then it activates, right?

[00:02:17] **Adam:** So you could use it. So, I used a pretty,I don't know, gory, analogy previously when we talked about this, and then I was talking with one of our patrons about it, and he reminded me that, I think maybe the Deadman's Switch, God, I gotta be careful with that W and the N, but I think that the Deadman's Switch was originally invented For train, is it engineers?

[00:02:38] **Adam:** The guys who stand or guys and gals who stand up at the front and, and, you know, make the train run, right? They're the ones, pulling the levers and blowing the whistle and whatever, you know, make the, the train move. And like, if the idea was, if they ever take their foot off of this pedal, then the train would stop because something bad has happened, right?

[00:02:57] **Adam:** so that's kind of the same idea with your software, right? So you've got scheduled jobs, right? You've got a scheduled job that it's, it's. It's the reason it exists is to bill your customers, right? It sends them invoices. And if it stops doing its job, then that's a big freaking deal. And you need to know that.

[00:03:12] **Ben:** But how are you... Okay, go ahead. Oh,

[00:03:15] **Adam:** yeah, yeah. So the way that it works is, every time that the job runs, you send, an HTTP request or a webhook to deadman snitch and they just record it. and, and

[00:03:26] **Ben:** they don't have to have, like, hooks into your software. You're pushing to them that something's happened. Okay.

[00:03:33] **Adam:** right. So if you, if you stop checking in, if you fail to check in, then it would, send you a notification in one of the many ways that it's possible to do so.

[00:03:44] **Ben:** I wonder if you could... Not to, not to throw a snitch here under the bus. but I know that you have talked before about using CloudWatch, is it

[00:03:53] **Adam:** Mm

[00:03:53] **Ben:** for logging? I wonder if CloudWatch would have some sort of similar type of an alert where instead of sending an HTTP request to the snitch product, you could log a particular message and then have CloudWatch say, Hey, if I haven't seen this message n number of times in the last hour, something might be wrong.

[00:04:13] **Ben:** And let me. Send an alert. I'm just shooting from the hip here. I have no idea how CloudWatch works.

[00:04:19] **Adam:** I gotta imagine something like that could be accomplished. at this point, it would have to save us a ridiculous amount of money

[00:04:26] **Ben:** Right, right. Like you already have a solution.

[00:04:29] **Adam:** Right. And we, not only do we have this solution, we have other, like, things integrated with it, right? Like, it integrates with our team chat, it integrates with our on call, and so, like, it would be kind of a big effort to switch it to something else, especially, like, at that ground level that you're building other stuff on top of. And it's not that expensive, all things considered. I think we're paying, like, 90 a year or something

[00:04:53] **Ben:** Oh, that's, that's a rounding error as they

[00:04:55] **Adam:** it might be 90 a month, but still, like, not that bad. Yeah, anyway, so, my triumph, getting back to that from five minutes ago, is, that, you know, we're doing so many of these snitches now, in large part because we have not made it to multi tenant yet and we have a bunch of customers and so we have End jobs, times, end customers, and it just becomes this explosion of jobs.

[00:05:19] **Adam:** and, so we have so many snitches, and it was becoming way too tedious to manage the configuration of like, okay, when this job for this customer runs, it needs to use this snitch ID to, in the webhook, to say, okay, I'm, I ran. and so, you know, we, We had a meeting about it and we, discussed the options available to us. And it was one of those things where like, we felt like we were right there. And then I'm so glad that we just kind of like kept talking it out for a couple more minutes, because then we came up with the best solution, which is we shouldn't manage that config at all.

[00:05:48] **Adam:** They have an API, they have a database, they're storing the configuration for us. We should just use like tags in their system and use the API to create and, and look up the snitches that we need. So like, you know, the job runs and it says, okay, I'm, you know, working code university and the, the mail stubbing job has run, I need to snitch for it and it says, okay, well, I don't have a snitch configured for working code university for, for mail stub.

[00:06:15] **Adam:** So let me go create one. I have to look up what the config for mail stubbing is, create a snitch using that because, okay, so that's another thing I didn't mention earlier, the snitches, you know, different types of jobs run on different schedules, right? So you might have something that runs once a minute, you might have something that runs once an hour, you might have something that runs four times a day, you know, three days a week, whatever.

[00:06:35] **Adam:** So you can have different schedules and configurations of your snitches. So, this thing, when you go to check in, it... Pulls up the config, creates the snitch if needed, and then checks into it. And then the next time that you try to check into that snitch, it'll already be created. It'll look it up and just check into it.

[00:06:52] **Adam:** and this is going to be so helpful for us. So this all started because we realized that we were like way behind on creating new snitches. like we just had dozens of jobs that didn't have snitches that were like kind of becoming a problem because things would break and we'd be like, how did we not know that that job was...

[00:07:11] **Adam:** Not running, like, you know, don't we have snitches for that? And like, oh, well, actually no. So we did this big audit of all of our jobs, created a spreadsheet because business runs on spreadsheets. And we were like, we identified something like 170 jobs that didn't have snitches. Like, oh my God, this is going to be such a nightmare to create them all.

[00:07:30] **Adam:** You know, it doesn't, it doesn't seem so bad when you're adding them like two, three at a time. But when you're adding like 170 in one go, like this is, there's got to be a better way. So, that's when we came up with this approach to, like, let Deadman's Niche API be the source of truth. and it also means that, like, yes, there's a little bit of work, and the Triumph has been working on it, and the code is pretty much ready to ship at this point.

[00:07:52] **Tim:** We're waiting for GivingTuesday to come and go before we take the risk of rocking the boat by doing a big deploy like this. so it's Tuesday, a big donation day for you,

[00:08:01] **Adam:** Yeah, so, today is Monday the 27th, you know, shortly after Black Friday. Today's Cyber Monday. And then Tuesday following that is like national sort of day of giving, right? You had your day of thanks, you've had your couple of days of commerce, and now it's the day of giving.

[00:08:16] **Tim:** whatever's left over.

[00:08:17] **Adam:** yeah, you know, if you got any table scraps, push them over this way.

[00:08:21] **Adam:** it's a, it's a pretty big, broad light. You know, I hadn't really heard of it until I started working in this industry. But, apparently giving Tuesday is a big thing that a lot of people are aware of.

[00:08:29] **Tim:** I know NPR always reminds me about it every time of year, but how

[00:08:34] **Adam:** and so we're, we're just trying not to rock the boat. you know, we don't want to mess something up right at, right. As our customers are trying to raise a whole bunch of money. so, anyway, after this code that I've been working on gets deployed, like all of these jobs can start checking in, create their own snitches.

[00:08:50] **Adam:** And as we add new jobs in the future, the only thing that we have to do is add the config for the snitches. The snitches will add themselves. It's going to be so awesome.

[00:08:58] **Tim:** many of them get stitches?

[00:09:01] **Adam:** All snitches get stitches, didn't you know?

[00:09:03] **Tim:** just checking,

[00:09:04] **Ben:** That's pretty cool. So if, just so that I understand, essentially you have. In your application code, you put in calls to the snitch program, even when the configuration doesn't exist. And then essentially the snitch program is kind of tracking 404s on requests. And then you basically go and post fill those.

[00:09:26] **Adam:** Yeah, I mean, if you guys want maybe another episode or something, we can dig into, like, how it's actually implemented for me. but for the most part, yeah, you know, we pull from the API. We say, you know, give me my list of snitches. Is the one that I'm looking for in there through various criteria? And if not, then I need to create it.

[00:09:45] **Adam:** I don't currently have the concept of like a default configuration. So like, if you try to check into the, you know, Ben needs to feed Lucy for the 117th time today job,

[00:09:56] **Ben:** So

[00:09:59] **Adam:** then, and there's no configuration found for that one, then right now, what it would do is just throw an error. to essentially to get the developer's attention to say, Hey, wait a minute, you tried to snitch.

[00:10:09] **Adam:** There is no snitch config. So, you know what? You need to do something about this. Either remove the attempt to snitch or add the configuration. But, I do kind of think maybe having a default of like, you just expect, just expect it once a day might be the way to go.

[00:10:24] **Ben:** Yeah. Then at least you could get a really

[00:10:25] **Tim:** the, what's the website for this product?

[00:10:29] **Ben:** dead mans snitch.com and, and you know, of course I think we should just go ahead and say this upfront, not sponsored for any of the things we're gonna mention today. Always available though.

[00:10:42] **Adam:** yeah, please, I will shill for almost anybody.

[00:10:48] **Ben:** Let me ask another question, because I know that you do make heavy use of AWS Lambda functions for some of your, your processing power. Um,and, you know, when you make an HTTP call to an external service, there is usually some degree of hiccuping in latency, you know, where 99 percent of the time it takes 30 milliseconds.

[00:11:11] **Ben:** And then every now and then it'll take 17 seconds. do you have any sense in Lambda? If, UDP communication works, like where you, you initiate the request, but you don't actually care for the response in a ColdFusion application, I'll do that sometimes if I'm say like logging a metric and I don't really care if it fails, you know, one out of every thousand times, but where you have a Lambda where it executes for the duration of the function and then maybe disappears.

[00:11:41] **Ben:** I don't know if that then messes up the idea of kind of this background request that

[00:11:46] **Adam:** So, it's a very interesting thought. I mean, do I know? No, I do not know that. I am almost certain that Node, which is the runtime that we're using on Lambda, can make UDP requests. So that should work. The thing that we're making requests to is a service that we created, right? So it's not the Lambda directly hitting Deadman Snitch.

[00:12:09] **Adam:** It's hitting a centralized service for us that manages like a local cache of the snitching, and it has the snitch config, and it, it translates from, I'm trying to check into this Lambda job for this customer. Here's the webhook URL. So it does that, that conversion, that lookup, and then, it converts it to that and then sends that back to the Lambda in this case. And, then Lambda sends that web request. And it, so I know that it is possible to, exit a Lambda. Before certain things are done, like you can exit a Lambda with a, database connection still connected.

[00:12:44] **Adam:** And I think in theory, you know, so say you're in a high concurrency moment, right, you're, you're handling a lot of requests with Lambda. It's not just like a one invocation and then go to sleep for five minutes. And then another one, this is like a 2000 requests queued up and so like handle one, shut down, handle one, shut down.

[00:13:04] **Adam:** in theory, you are. Shutting down, but you're leaving that database connection connected. And when it, when that Lambda virtual machine gets reused, like the, I think they call it a warm copy or whatever. and it's still connected in there. So potentially you could. Maybe make that HTTP request and just not wait for the response.

[00:13:28] **Adam:** I'm not sure how that would work.

[00:13:30] **Ben:** All right. All right.

[00:13:32] **Tim:** So, we're kind of wedging

[00:13:35] **Adam:** all over the place.

[00:13:36] **Tim:** and no, we're just kind of wedging this in with, with, with your thankful and I appreciate you bringing this up. So, it talks, I'm looking at the website. Actually I put in dead man's switch instead of snitch at first, which actually was a URL and it's basically you put in your information and it, I guess it pings you.

[00:13:53] **Adam:** And if you don't respond in a certain amount of time, it alerts people that you're dead, physically dead, as a human being. So I'm like, this is the worst website ever. I don't even, where's the API docs? told you, you gotta be careful.

[00:14:06] **Tim:** yeah, but so I found Deadman's Snitch. so I have a job that sends out tons and tons of SMS. And basically what I do is I let it run for two hours. And I assume it's going to fail the first time because it's like, the time's out or whatever. With this, could that check that and then just rerun it?

[00:14:22] **Adam:** No, it would not do the rerunning part for you. It's just, it will notify you that it failed to check in

[00:14:28] **Tim:** Okay, well, I've already

[00:14:29] **Adam:** you can have,

[00:14:29] **Tim:** does that, yeah.

[00:14:30] **Adam:** you can have it do email or you can have it send to your Slack team or your Discord or SMS or to push notification on in the app on your phone or, you know, a dozen other things.

[00:14:44] **Ben:** Very cool.

[00:14:46] **Adam:** All right, now that we're 15 minutes into this episode, I'm gonna throw it over to you, Ben. What, what's your triumph or fail?

## [00:14:52] Ben's Triumph - Feature Flags Book Early Access

[00:14:52] **Ben:** I'm going to go with a triumph, a pretty big triumph for me, which is that this morning, which is Cyber Monday, I released an early access version of my book on feature flags. Um,it's yeah, I've been, I it's, I've been working on this for just shy of three months. I think maybe I started on. September 6th or something like that.

[00:15:14] **Ben:** so just shy of three months and putting quite a significant amount of time into it. the early access is just a PDF and it's essentially the way I've been authoring the book is I have a book. md, md stands for markdown, I have a book. md file that I've been authoring directly in. And it's in source control.

[00:15:34] **Ben:** And then I take that, I parse it with Flexmark, which is a Java based, thank you for the graffiti there, Flexmark, which is a Java based markdown to HTML parser. And then I run that through Jsoup, which is a Java based HTML to document object model parser. And then I Add some links and generate a table of contents and I output it to the page.

[00:16:03] **Ben:** So essentially I take this bookmark down file and I turn it into a web page and the early access version is literally me just. In Chrome, doing Command P and then printing the output to a PDF and, you know, removing the headers and footers and adjusting the margins. And yeah, it's, it's

[00:16:22] **Tim:** artisanal, it's an artisanal book.

[00:16:24] **Ben:** an artisanal book.

[00:16:26] **Ben:** Exactly. Exactly. And as long as I never change the settings on my printed PDF, then I can consistently generate it. Um,I, I do have plans to. aspirational plan to try and turn this now into an EPUB, which is, Apple's official use and, uh, Mobi, which is, is it again?

[00:16:45] **Adam:** no, okay. I don't know. EPUB is, is open source. It's not

[00:16:49] **Ben:** Yeah, yeah, yeah. Sorry. I didn't mean it was Apple. I meant, I meant Apple Books, the.

[00:16:54] **Adam:** Okay. Yeah. That's what Apple Books expects. Yeah.

[00:16:56] **Ben:** they prefer EPUB and then Amazon's Kindle, they prefer a Mobi or PDF. And, so apparently there's some giant open source library called Pandoc, which can convert between a bajillion different formats and it can take HTML or Markdown and convert it into EPUB and PDFs and Mobis.

[00:17:18] **Ben:** I just have to figure that out. And, and at that point. I then also want to clean up some of the page breaking and where figures, like images. Get placed so that they don't create these giant empty gaps and pages. and you know, that's all something I intend to do. But as of today, I have officially launched an early access version of the book.

[00:17:37] **Ben:** It's available on Gumroad, which is the, service that Adam had recommended to me and, and so far that's been a pretty easy service to use and, sold some books, so I'm pretty excited about that.

[00:17:49] **Adam:** Heck yeah, man. I got that email while I was, you know, after the dog walk this morning before the oldest left for school. And I was like, gotta, gotta get it done before I gotta do the thing for

[00:17:59] **Ben:** Adam Tuttle was my very first purchase.

[00:18:02] **Tim:** Aw,

[00:18:02] **Ben:** that was very, that was very nice of him.

[00:18:05] **Adam:** I just happened to be sitting on my phone, like, playing Spider Solitaire, waiting for the, you know, I had three minutes left until the kid needed to, you know, be brought down for the school bus, and so, like, you know, doing that, like, get the, the push notification for the email, from Ben Nadell, I'm like, I wonder what that's about, I look at it, and it's, you know, Feature Flags book something, I'm like, click, and, it's like, heck yeah, bye, bye now.

[00:18:26] **Adam:** I bought it on my phone, and then I was like, wait a minute, there's a down, I don't want to download it on my phone, because then if. I wonder if like the download button would only works once or whatever. It's like, I don't want to have to like try to figure out how to get it off. No, it, I don't think it works that way.

[00:18:38] **Adam:** It does not work that way, but I was worried about it working that way. And it's like, I don't want to have to figure out how to get the PDF from my phone to the computer. I'm sure, you know, I'm sure it's not that hard, but I was just like, it'll be easier. If I just wait. And download it on my computer. So

[00:18:54] **Ben:** So I'm, I'm thrilled about that. so my, my wife, when I told my wife that I had published it today, then she went and actually started to read some of it for the first time. And, she came in like an hour later and she said, I think it's really good, but

[00:19:07] **Tim:** mm

[00:19:08] **Ben:** use bold and italics text like. All over the place.

[00:19:12] **Ben:** Like you have to chill. And, uh, I, I think that is a by product of when I write is basically the way that I write is I write a couple of sentences and then I read those sentences back to myself out loud. just that's, that's historically how I write. Which, you know, is probably

[00:19:29] **Adam:** out loud, flapping your

[00:19:30] **Ben:** yes, yes, my, my meat part's in the wind.

[00:19:34] **Ben:** which is definitely why my attempt to apply the just ship mentality, did not actually happen. and I'm much slower of a writer than I had hoped I would be anyway. So I read, I skimmed back over the book and I'm like, Oh my God, she's right. I, I italicized like every other word in the book. So I quickly went through and I removed all of the italics and bolding or, you know, like 98 percent of all the italics and the bolding. And I generated my PDF via Chrome's print to PDF artisanally, and I re uploaded it to Gumroad. And then I sent out another email. So you might actually get a second email that

[00:20:09] **Adam:** I saw it.

[00:20:10] **Ben:** that says, if you don't, I think, I think a phrase is like, if you'd like a less aggressively formatted version of the book, you can download it again.

[00:20:19] **Tim:** She's like, Ben, you need to calm down, this is a Wendy's.

[00:20:25] **Adam:** Did she just like get Taylor Swift to come over and sing? You need to calm down.

[00:20:28] **Tim:** Mm hmm.

[00:20:30] **Ben:** so anyway, I'm super excited about that. I'm super excited to just get back to blogging. I feel like my blog has been a ghost town for the last three months, other than thankfully, the Wednesday posting of the working code pod, updates. So

[00:20:47] **Tim:** shows it. Do you guys subscribe to Pete Freitags? He has like a weekly newsletter. See it break. Yeah. It's so it's always Ben and the gang. It looks like on working code. Like, okay, it's, it's Adam's podcast, but all right.

[00:21:01] **Adam:** Hey, I'll

[00:21:02] **Tim:** Ben's, it's Ben's blog, but we'll take the free publicity.

[00:21:05] **Tim:** That's right. It's not like the web, the podcast has its own website that you could, Yeah, true.

[00:21:10] **Adam:** Link to.

[00:21:11] **Ben:** it was a good time. Good time. that's me. Carol is traveling. It looks like not with us today. So I'm going to kick it over to Tim to take us home. Tim, what do you got going on?

## [00:21:20] Tim's Triumph

[00:21:20] **Tim:** Oh, I guess all three of us have a triumph, which is, you know, pretty good for having been off. I guess, I guess when you've been off most of the last week, it's, you know, less room for fail. So. There's that. yeah, so it's first day back at work after a long three day, three day off, you know, for Thanksgiving.

[00:21:38] **Tim:** and, but I, I managed to, so we have, an early version, Scala version of our, our payment. API that, I think as of the beginning of the year, there was only one customer that was using it and they're a really slow customer. We didn't want to kill it, you know, and make them so eventually they got around to updating their stuff to use the new API, got that moved over.

[00:22:04] **Tim:** and, so today I, we. We just turned it off just to make sure no one else was using it. We did, we did look at our, we did look at our logs, our Nginx logs and all the other logs to see what requests were coming in. And the only thing that was coming in is some of our internal reports that we, that we wrote that was calling this old API.

[00:22:23] **Tim:** So basically I wrote, a replacement report for that, that gets all the same, exact same data, returns the exact same format. You know, all the same getters, when you do the get call, to do it, replace that. And that took about four hours today, but I was testing it out, all the tests seemed to work. So we'll see tomorrow.

[00:22:43] **Tim:** And it's not super mission critical. Some people can't get their reports for a couple hours to borrow. Why fix stuff? That's not a big issue, but it's nice to finally turn an old machine off. particularly one that's in the PCI environment because any, you know, every machine and service that you add to your PCI stack is just a new surface area for, it's a vector for attack.

[00:23:03] **Tim:** So the more we can turn off, the better.

[00:23:06] **Adam:** That's like the best code ever is the code you didn't write.

[00:23:10] **Tim:** Or the code that doesn't run anymore. It's not accessible. So,

[00:23:13] **Adam:** delete it.

[00:23:14] **Tim:** yep. So basically deleted a whole service today. So pretty confident that it should be okay. We'll find out if it's a failure next week or next episode. but we'll see. Yeah, that was me.

[00:23:25] **Ben:** At work, we use the phrase scream test to indicate that we don't know if anyone is still using something. So we'll just turn it off and see who starts screaming. And then, and then

[00:23:36] **Tim:** do the exact same thing. I mean, we did check the logs and the, look at the only requests that were coming were all this daily report report that we have, that was it. So there was no payments coming through. There was no. Refunds or transactions. So we're like pretty confident that no one else is using it.

[00:23:53] **Tim:** So if they are, they're doing it maybe once or twice a year and what we don't want them as a customer. So

[00:23:59] **Ben:** We've had issues in the past, and this is something that I didn't even know was possible. But we use Kubernetes to deploy a lot of our containers to production. And Kubernetes can just completely lose track of a running container sometimes. And I think it has to do with rolling deployments or something, but every now and then we would have a service that we're trying to shut down and we see traffic continuing to come into it.

[00:24:26] **Ben:** We're like, where the hell is this traffic coming from? And someone on the platform team, you know, has to go into some low level APIs and start listing out things in our network and then they'll just find a container that's just running that, that none of our other systems knew about. And it just happens to have all the.

[00:24:42] **Ben:** You know, it was running on an old version of code, which is also terrifying by the way. But it's, you know, just running out there in the void, making API calls to, other pods, because that's what it would do, say, as part of a worker process or something. And just Kubernetes had no idea it was there anymore. It's terrible. It's weird.

[00:25:01] **Tim:** seems like a problem.

[00:25:03] **Ben:** Yeah, I think so.

[00:25:05] **Adam:** It's fine.

[00:25:06] **Tim:** That's all

[00:25:07] **Ben:** care of itself naturally. Eventually.

[00:25:10] **Tim:** Dead man's

[00:25:11] **Adam:** else's problem. So, let's get into the software that we're thankful for. We've already mentioned a couple of things here, but, maybe we should just sort of like go round robin, just throw something out and, and, you know, if we want to dig into one of those, or if we just want to go, yeah, that, that, it sounds good.

[00:25:25] **Adam:** I agree. Then, we can move fast and quickly too. It doesn't have to be a whole discussion for each one. So, who wants to go first? I already went first. I already went first. I said Dead Man's Snitch, so now somebody else go.

[00:25:37] **Tim:** You go Ben.

[00:25:38] **Ben:** go second.

## [00:25:38] Overcast

[00:25:38] **Ben:** I'm a huge fan of podcasts. I listened to loads of podcasts on 2x speed and I am a huge fan.

[00:25:46] **Adam:** my brother, my two ex

[00:25:47] **Ben:** Yeah. Oh, you gots to, you can't be listening to people talk like they're drunk on their one X speed. the pot, so for years and years, I just use the default.

[00:25:59] **Tim:** So you listen to people that sound like they're on meth. This is what you're saying. They're tweaking hard.

[00:26:05] **Adam:** Well, we were talking about this in the podcast discord today about like, if it's something that I'm trying to like learn from and concentrate on and be like, okay, yeah, that makes sense. Or like, if it's, I'm trying to like, you know, grow as I listen to this, then I cannot go above like 1. 8. That's sort of the max, but like.

[00:26:22] **Adam:** If it's just for entertainment, like if I'm listening to a fiction audiobook or if I'm watching a YouTube video that like, you know, I'm not trying to follow along, I'm not trying to learn something from it, it's just entertainment value, man, I can get up to like 4x sometimes.

[00:26:33] **Tim:** What? It's

[00:26:34] **Adam:** yeah,

[00:26:35] **Ben:** Nice. So, so along those lines, when I first started listening to podcasts for years, I just use whatever the native one on the Apple iOS was, which I think, I think it was just called Apple

[00:26:45] **Adam:** terrible. It's just called terrible. You find the ugliest icon and you open it up and it just yells at you.

[00:26:52] **Ben:** I'm so slow to switch things, but I was listening to a podcast one day and someone said, Oh, you should check out. Overcast. It's a, it's a podcast, a podcasting app. And their selling point was that it has this, dynamic speed mode, where you can say, put it on 2x, but then you turn on this dynamic speed, and it will automatically trim.

[00:27:14] **Ben:** Dead space in the podcast, so it'll be 2x, but it'll still get through, like, it's sometimes going 2. 1x or 2. 2x because it'll just skip over empty space. Your, your, the voices are not crazy, but the overall duration of the podcast is much shorter. Anyway, that, that was the selling point, so I tried Overcast and it's just, it's a really, really great app.

[00:27:35] **Ben:** It's very solid. It has a bunch of. Cool configurations about different speeds for different podcasts. And you can put podcasts into different types of playlists and you can say automatically download new episodes when they're there, how many episodes you should keep around. It's, it's just become,

[00:27:52] **Adam:** Yeah. I mean, these are all table stakes, features for any podcast app that doesn't suck.

[00:27:58] **Ben:** Well, I'm on podcast app number two right now. So it's, it's way better than the one I had before. So

[00:28:04] **Tim:** new world.

## [00:28:05] PocketCasts

[00:28:05] **Adam:** I'm going to have to add, I didn't have a pocket casts on my, on my list of, of apps, but I'm adding it because of exactly what you're talking about. So I'm holding up the screen so these guys can see my stats here and,

[00:28:17] **Ben:** days,

[00:28:17] **Adam:** yeah. So I, I've been listening, I've got 70 days and 20 hours of listen time.

[00:28:22] **Adam:** Now that I, I believe that is like, you know, as recorded, right? If you were listening at 1x. So, less than that total. But, by skipping, right? Hitting the like forward 30 second button or something like that to get past ads and that sort of thing, I've saved almost, just shy of 13 hours. By using variable speed, I, I'm just shy of 24 days saved.

[00:28:44] **Ben:** Oh my goodness.

[00:28:44] **Adam:** the, the trim silence thing you're talking about where like, you know, if there's just a long pause, it just cuts it and doesn't count that toward like, The, the, the speed change, it's saved three days and 18 hours auto skipping. So like, you know, some, some podcasts have, you know, a, a two minute intro and it's just like the same recording every single time that they never mix it up.

[00:29:05] **Adam:** There's never like, you know, it's not, it's not a discussion thing. It's just like, we play this clip and then we have our show and then we play this clip as we exit. I have that automatically trimmed off. So it's just like, it starts. And, and they're already in a discussion. I've saved three hours and 52 minutes from that.

[00:29:21] **Adam:** So total savings.

[00:29:22] **Ben:** that adds up.

[00:29:23] **Adam:** Oh yeah, yeah, yeah. So, that's crazy. Okay, sorry, go ahead.

[00:29:29] **Ben:** No, overcast. Yeah. Overcast. Hit it. It's great.

## [00:29:33] Git

[00:29:33] **Tim:** All right, I'll do one and mine's going to be super basic. I am so appreciative. I'm thankful for Git source control because I lived back in the day before source control was really available to the masses and I'm telling you guys, the things I've seen.

[00:29:53] **Adam:** Back in the days of VisualSourceSafe, or

[00:29:56] **Tim:** oh my god.

[00:29:57] **Adam:** was back, back, final, final, final, final for

[00:30:02] **Tim:** version, Tim's version, Bob's version, Carol's version. Yeah, get source control. It's just so, it's, I still, I don't understand how it works. I'm just glad that it does, because it's like, There's times when I thought I lost code and I didn't lose code. And sometimes I have lost code, but, but, you know, it keeps it safe.

[00:30:23] **Tim:** It's simple as learning it. I don't know why it was so hard the first time I was trying to wrap my head around it. If I couldn't get the mental model of how it worked, I think I had some bad habits

[00:30:33] **Adam:** Yeah, too much experience with subversion.

[00:30:36] **Tim:** Right.

[00:30:36] **Adam:** It kind of turns your brain inside out when you try to switch to git.

[00:30:40] **Tim:** And, you know, we would like have bad, you know, constantly having merge conflicts and branches that were.

[00:30:46] **Tim:** Bad. And, but now it's just like, it's so simple. It's like, I don't even use like fancy, you know, it's like maybe five commands. I use just, just make sure that, you know, if you're, sometimes you're working in different repos, just make sure you're, you're, you're pushing them up and pulling them down regularly.

[00:31:02] **Adam:** You're a, you're a 5 commander?

[00:31:03] **Tim:** Yeah. Five, five. Yeah. But with git, that's a good thing

[00:31:08] **Ben:** So,

[00:31:09] **Tim:** because, because you're having to get esoteric with the git, the git bash line. You, you, that's because you messed something up bad. You got to figure it out

[00:31:16] **Ben:** I think if we could just extend this though, I think GitHub has done just worlds of wonder for the development process on top of Git. I didn't even realize for years that the concept of a pull request was something that GitHub had invented. That was not part of what Git actually did. They just used to send around like patch, patch

[00:31:38] **Tim:** Patch files. Yeah,

[00:31:40] **Ben:** something insane like that.

[00:31:41] **Ben:** I can't even imagine a world like that.

[00:31:43] **Adam:** Yeah, and it's funny because, like, I don't know, I don't understand how they got to the name of a pull request, really. I mean, I guess it's, it's there if you dig hard enough for it, but, like, if you think about the way that you would share code prior to that, right, you would make your changes in your branch, you'd create a patch, and you would, like, email it and be like, Alright, here's my changes, please, you know, review this, and then...

[00:32:05] **Adam:** I guess, I guess at that point if you did like the code and you didn't have to request any changes or anything, you could like add a remote, now again we're talking about git here, not subversion or anything like that, but you sort of add a remote and you could pull from that remote and merge it into your main branch, so maybe that's where They came up with the name pull request, but like, to me, it always seemed like such a push action, so it always kind of felt interesting and backwards that they ended up calling it pull requests, but it's worked.

[00:32:38] **Tim:** I, I mean, the whole idea of a centralized thing, like GitHub kind of breaks the paradigm of, of, you know, source control being, you know, distributed and, you know, there's no, no, there's no one, you know, place of truth. But honestly, at the end of the day, it makes everything so much easier when you have that.

[00:32:54] **Tim:** So it's like, as long as it gets up and it usually, you know, it's been down a few times, but, you know, it's a, just make it a holiday

[00:33:01] **Adam:** I mean, you're, you're not wrong to make it a holiday. The, so our approach, so we use, GitHub Actions pretty heavily as our CICD stack. And in large part because of what you're describing, right? Where like, you know, GitHub can go down. Stuff breaks sometimes, you know, maybe Amazon is down or whatever.

[00:33:18] **Adam:** And like, we, in an effort to make it so that we can still be as productive as possible. at the end of the day, All of our GitHub. CI, workflows, they just call makefilescripts. So we have makefiles that do the thing, right? It's a build the container, push it to ECR, trigger a deploy on ECS, whatever.

[00:33:38] **Adam:** But that's all done in makefilescripts. And then the, the workflow just like check out the code, find the makefile, run the make command. It's basically what it does.

[00:33:49] **Tim:** Ours is kind of similar to that. Yeah, we're, we're just pulling it from the latest branch, but if I had locally the latest branch, I could just, in our scripts, we, we, it's, forget what we use it in Scala, but anyway, it's basically doing, it's pulling down the latest code from, from GitHub and then. That builds the packages and then puts it up on the server.

[00:34:08] **Tim:** Comment that out and just say, you know what? Use my local I have local changes and then push it up. So yeah, there would be a workaround for that. Usually not down long. We'll just wait, have a beer,

[00:34:18] **Adam:** Yeah.

[00:34:21] **Tim:** take a lunch. That's me. Get source control. I'm very thankful for, for source

## [00:34:25] Video Chat (FaceTime, Discord etc.)

[00:34:25] **Adam:** I guess it's my turn to go then, and I'm going to go with video chat and I'm just calling it video chat. You know, if you want to call it FaceTime or the one that I use the most right now is Discord because that's where my team chat is. before that it was Slack. before that we used Google Meet.

[00:34:39] **Adam:** And I think that, the, the reason that I am so thankful for these things is because really this is what empowers at least my team and my company to be fully remote. Like we don't even have an office. There is no return to office. I'm already in my office. and I don't think it would be possible without video chat.

[00:34:57] **Adam:** And, and this is like, totally open technology. Somebody could have made a lot of money off of this, probably. But they decided to just share it with the world. And I'm so thankful for that.

[00:35:07] **Tim:** Is it open?

[00:35:08] **Tim:** RCS, is great. RCS is the, the thing that... Apple is only mostly in implementing in iMessage. talking about RCS. I mean, like Discord. I know they, there's, you can pay

[00:35:22] **Adam:** oh yeah, I mean, Discord, Discord itself is, but the, the underlying technology for doing video chat, like Google Meet, right, is, it's just built on web technology. Like anybody can go build a web video chat platform.

[00:35:35] **Tim:** Gotcha.

[00:35:36] **Ben:** will plus one video, video conferencing. It's, it's been pretty amazing. We use Zoom very heavily at work. and it's just been just the, and anything that makes it seamless and effortless to get into a call is really great. And I think all of the different products have really made it kind of just a one button click.

[00:35:54] **Ben:** Let's do this kind of a thing.

[00:35:56] **Tim:** A hundred percent. We're using video chat right now to record this on Riverside. fm.

[00:36:02] **Ben:** Pro show.

[00:36:05] **Adam:** Cool. So, Ben, I guess that's your turn.

## [00:36:08] Snagit

[00:36:08] **Ben:** Yeah, I'll go with a, kind of along the same lines of. I use a product called Snagit, which is part of the TechSmith suite of products. It's just a screenshotting tool and video, like little quick video recording tools. and I know that there's a million different screenshotting tools where you just take a screenshot and you can drag it into Discord or drag it into Slack or drag it into email.

[00:36:30] **Ben:** But I've been using Snagit for a really long time and it's just really great. It has a bunch of additional tools like being able to highlight text and annotate things and you can crop images and drag new images onto existing images. And, you know, I'm, I'm sure nothing in there is particularly revolutionary to this little genre of tools, but Snagit has just been my, my go to and, it's been awesome.

[00:36:55] **Adam:** Yeah, big plus one from me. I use, what is it called? Skitch, which originally

[00:37:00] **Ben:** Yeah. Sketch.

[00:37:01] **Adam:** And they got bought out, I think by Evernote. And then it just kind of like mostly died, but you can still, you can still use it. It's just not like, I think originally it had like a, you could take a screenshot and annotate it, whatever.

[00:37:14] **Adam:** And then there was a button where you could like push it up to the cloud and you could just share that URL with somebody. And that part is gone. So now I just like, I take my screenshot, I annotate it. And then I just copy it to the clipboard and paste it.

[00:37:25] **Ben:** yo, I used to be a big Skitch user and I remember one of the things that really sold yeah, really sold me on it was I always thought that their arrows were just perfectly stylized.

[00:37:36] **Adam:** yes,

[00:37:37] **Ben:** just a line with a, with a little cap at the end. It was like a fun, chunky arrow.

[00:37:43] **Adam:** I, I give anybody on my team who like creates documentation with screenshots and it looks like a toddler came by with a crayon and drew an

[00:37:50] **Ben:** Yo,

[00:37:52] **Adam:** Like, I just give them so much I'm like, there are better tools. We are better than this. Do better, be better. It still

[00:38:00] **Ben:** for real, they're, they're chunky arrows were just the right blend of playful and professional and well done. And I think Skitch was just a really fantastic product. I don't even remember. Why we stopped using it at work. Maybe it just got replaced by Snagit at some point, or there was a support, I don't know, a licensing issue.

[00:38:20] **Ben:** Who knows, but it was a fantastic product for sure. Oh, sketch.

[00:38:28] **Tim:** Getting nostalgic over there.

[00:38:29] **Ben:** Yeah. Big time. What about you, Tim? What's next for you?

## [00:38:32] CICD

[00:38:32] **Tim:** So, building off my last one on source control is just, being able to do automated CI, CD, continue some. Improving continuous delivery. so we use, for most of our new projects that we're using, of course, we use GitHub for the code. We use JIRA for, you know, the ticket management and the task tracking, and then the Azure DevOps pipeline.

[00:38:57] **Tim:** So, which has a plug in for JIRA. You can go through, you know, we have a strict approval process for anything that has to be reviewed for PCI reasons, and then, you know, you just. I mean, I remember the days what it took to deploy things, like it was moving, physically moving files. And now you just click a button, yeah, that's just seeing how hard the code deployment used to be into what it is now with just this. Easily documentable, easily replace, you know, reproducible, easily rollbackable type of system.

[00:39:36] **Tim:** It's just, it's amazing. I love it. We, we, we saved so many hours, there were times where it's like in the early, early days, but before we had good source control where, you know, we would wait to off hours to deploy code because, you know, you have to manually put files out there. And so if you don't get all the files up at the exact same time, which was impossible, or if they, you know, cause there's conflicts or something, or with the bad source control that we used to have, things could break.

[00:40:03] **Tim:** Cause. You know, you, you got 59 outta your 62 pages deployed, but others, others aren't there. It just was a mess. And now it's just like, click, click.

[00:40:13] **Ben:** Well, and, and it's even crazier than that nowadays where, you can get things like, Netlify where they'll take a GitHub branch and they'll give you Subdomain, like a preview subdomain, just of your branch. And then it gets even crazier than that, because I think, I don't know if it's planet scale, there's some company or some set of companies where they have databases now as a service, and they will do the same kind of thing where if you want to run a migration, they will give you like an on the fly.

[00:40:44] **Ben:** Like, I don't even quite understand how it works. Like if you like an on the fly, new snapshot of the database with the new structural change without having to have actually copied all the data somehow using some sort of, I don't know, copy on read magic or something, and then you can use that to test your migration changes in, in other preview environments.

[00:41:05] **Ben:** It's just, it's just really bananas the way we're moving forward as an industry in terms of deployments.

[00:41:12] **Tim:** And the, and these things, you know, it's like people doing it now like to kind of take it for granted. Oh yeah, of course. That's the way to do it. It's like, guys, you didn't realize how , how, how rich you have it

[00:41:23] **Ben:** Well, and I still feel, I don't know if. I think at the very beginning of our podcast, like our, of the working code series of podcasts, I had said my goal during one of the years was I wanted to get something built into a container and then deployed using CI CD because at work we had people who built that and I can leverage it, but I didn't build it.

[00:41:44] **Ben:** And, to this day, the actual wiring up and orchestrating of all that stuff is still kind of a black box to me. I don't quite know how any of it works and I'm sure that's just, if I do it once, it'll make sense, but it. It still seems super,exciting and foreign and mysterious to me.

[00:42:02] **Ben:** 44

[00:42:02] **Adam:** Okay, cool. So, I'm, I'm gonna, oh, there's so many good things. So many things to be thankful for. I'm gonna throw out a couple of like rapid fire ones and then give a real one.

[00:42:11] **Adam:** How about that? Google Calendar and Gmail. Like. revolutionized the way I use the internet between these two things. Like, you know, calendars existed before that. you know, Outlook, honorable mention from back in the day, but, Google Calendar and Gmail really, like, made being an internet person possible, like a digital native, right?

[00:42:32] **Adam:** and I know a certain somebody is going to give me an earful for that. He just switched from Outlook to, Not Outlook, I guess. Well, I'll talk to them about it later. Anyway. so those are my honorable mentions, or my rapid fire ones.

## [00:42:46] 1Password

[00:42:46] **Adam:** But the real one here is 1Password.

[00:42:48] **Ben:** Mm one password's.

[00:42:49] **Adam:** for 1Password. you know, A, it has significantly upped my personal security game.

[00:42:56] **Adam:** It's made... being organized about security and secret sharing in a good way, amongst my team at work. Like, A, possible, but also B, like, well organized and well done. So happy and so thankful for that and it's at a reasonable price, and if you didn't know, if you're, if you get team, a team license for 1Password, everybody on the team gets a free family license.

[00:43:21] **Ben:** Oh, I didn't know that. That's awesome.

[00:43:24] **Adam:** that's fantastic. That way, like, you know, you're, you're at work, you have to use this thing for security stuff. Okay, fine. But like, now you know it and you can take what you've learned from using it at work, you know, expand it out to your family. So like, because of that, you know, we have it for our family.

[00:43:39] **Adam:** I've got my wife and kids on it. I've got my mom on it because you get a certain number of seats. And so I was able to share it with her.

[00:43:46] **Ben:** One of the best things that I've come to love about 1Password is that it can do the one time password aspects of a two factor authentication, which if anyone has ever had the Google Authenticator app or some other on your phone two factor authentication approach. when you update your phone's operating system, or I guess, I guess more, if you transfer to a new phone, it doesn't transfer over the one time password configurations.

[00:44:13] **Ben:** I guess that's a security consideration. I don't quite understand why. And once you have that in one password, you never have to worry about that again.

[00:44:20] **Adam:** Yeah. I, I, I 100 percent agree with you in terms of convenience there. before I discovered that in 1Password, I was doing, I was using an alternative app called Authy. I think it's from the people who make Twilio.

[00:44:32] **Ben:** Okay.

[00:44:33] **Adam:** and the nice thing with that one is it's, you know, it's external, like it, it stores your tokens, I guess, that it needs to build the time based, one time passwords, in the cloud.

[00:44:44] **Ben:** Ah,

[00:44:45] **Adam:** You get a new phone, you sign into the app and it says, okay, here's your tokens. And it's got them all, you know, your config saved and it would restore that. That was nice. But again, having to get out your phone is a pain in the butt. Now it's also kind of the whole point, which is why I feel just the tiniest little bit bad about using 1Password because it's like the password and the one time password.

[00:45:09] **Adam:** Are in the same place. If you get access to one, you now have

[00:45:13] **Ben:** get access to the other.

[00:45:14] **Adam:** Kinda defeats the point. But it's so convenient.

[00:45:18] **Ben:** convenient. I mean, your computer is still technically like the second factor, right? I think? Is that how? I, I'm, I'm always a little bit fuzzy

[00:45:28] **Tim:** I got your laptop. Although, you know, sometimes on dual, dual, they need a phone number. I just have a Google number. So I'm just in my browser anyway. So

[00:45:36] **Adam:** yeah. Yeah, it'll go to Google Voice, which pops up in a window on my computer.

[00:45:40] **Tim:** exactly. So it's a little dirty. I do feel a little dirty about that, but I don't use it for anything

[00:45:46] **Adam:** Well, I mean,

[00:45:47] **Tim:** business related.

[00:45:48] **Adam:** like, something like 80 percent of adults in the United States use an iPhone, and so if 70 percent of them have a Mac, you know, that's a significant chunk of the country. Just has iMessage.

[00:46:02] **Tim:** Oh yeah. I forgot about that. Yeah.

[00:46:04] **Adam:** like a significant chunk of the country has iMessage. I said, I did it again.

[00:46:07] **Adam:** Message, message up on your laptop and it just pops up right there anyway. So,

[00:46:12] **Tim:** Yeah, I totally forgot about that. I don't use Mac. So, all right,

## [00:46:16] Plex

[00:46:16] **Tim:** I'll go. so I'm going to do two that are non work related.

[00:46:20] **Adam:** okay.

[00:46:21] **Tim:** one is Plex.

[00:46:23] **Adam:** LovePlex.

[00:46:24] **Tim:** Yeah. Plex, Plex is so, you know, most of you probably know what Plex is, but it was originally, X, XBMC. It was basically a way for people to have like a, like a big screen experience, hook their Xbox up to a big screen and gave you menus and everything.

[00:46:40] **Tim:** Kind of like the smart TVs we have today. but it's just for Xbox. And that is. You know, Xbox kind of, that kind of became passe. Now, Plex is just, it's just a, that you can download for your Fire TV or put it on a PC, pretty much any.

[00:46:55] **Adam:** You can get it on an Apple TV. Yeah.

[00:46:58] **Tim:** and it just manages all your media. So if you've got music, if you've got movies, you know, that you've have legally copied and created a file for, which all of mine are,

[00:47:08] **Adam:** Organize all of your Linux ISOs.

[00:47:10] **Tim:** exactly a hundred percent, and you know, if they will download like the, the graphic art for the TV show or the movie, whatever, you can show you the Rotten Tomatoes score.

[00:47:19] **Tim:** it's just, yeah, it's just amazing. It's like, it's so easy. You just put the right file on the right. Folder, just, you know, the TV name, Doctor Who 2005, put the files in there and it automatically scrapes that and says, Oh, you got new episodes and you can just, yeah. So if I have a huge like, multi terabyte array of just, you know, video,

[00:47:38] **Adam:** Mm hmm.

[00:47:39] **Tim:** tons of movies, and then it will organize it for you and keep track of what you watched, what you haven't watched.

[00:47:45] **Tim:** You can Yeah, it's just cool. I love Plex. You get, you can watch it remotely. If you're, if your upload is good enough, you can log in and you know, you're on the road, you can watch all your media, keep up with all your media. and so that, that's really pretty amazing.

[00:48:01] **Adam:** Yeah, so when I found that out, I started, anytime I have to travel for work, I bring an HDMI cable with me so that I can plug my laptop into the TV in the hotel room and I can just like control it on my laptop and then basically casting up onto the TV in there, my own stuff. Yeah, it's great.

[00:48:16] **Tim:** it's not great for live TV. I, we, we, I tried something where we had a, an aerial antenna and I had this plug in that we tried to add that as a source and it didn't really work and. Where we live, we're down kind of in a hole. So we don't really get aerial TV anyway, but I just get a YouTube TV and that fixed that.

[00:48:34] **Tim:** So,

## [00:48:35] Roll20.net

[00:48:35] **Tim:** and then Roll20. net.

[00:48:38] **Adam:** So you play a lot of D&amp; D online, huh?

[00:48:40] **Tim:** yeah, we do play a lot of role playing games and, and just not even, you know, role playing like Pathfinder and those sort of role playing games and other just. Other games, particularly like the start of the pandemic just played a lot on Roll20, so it has automatic write still, it's, it's like almost programming in a, in a way, if you want, it can be as simple or as complex as you want.

[00:48:58] **Tim:** It's like, it's basically a shared game board. It has video chat, chat, like we have, you know, on other platforms, but you can play games, roll dice. Play cards, move pieces and all that sort of stuff. So it's super, it has like, you can build different campaigns and has access to any sort of, a lot of different source material books.

[00:49:20] **Tim:** So it kind of makes it simple. If you know, if you have, different, features that your character class has, you can just drag them and drop them onto your character. Now you have that item or you have that, that ability. So. Those, those are great for gaming.

[00:49:34] **Adam:** And is that like a, that's like a premium thing you pay extra to get access to all the materials and stuff that's in there?

[00:49:40] **Tim:** Yeah, you do. But only, so if you're the, so you can, you can buy a premium. I have a premium, I think it's like 99 a year. The people that you invite don't have to buy all the same things. So if you get a whole bunch of rule books, those rule books can be in your game. Everyone that's in your game, they. They don't have to pay anything.

[00:49:58] **Tim:** It can be, there's a free, they can use the free version. And so they have access to all those rule books. It's like going over to someone's house. They have all the rule books. You can sit there and read them and create your characters and do all that sort of stuff. they don't have to pay for it. So that's pretty cool.

[00:50:11] **Adam:** That makes sense. okay. Well, we're, we're pretty much running out of time here. Do we want to throw in the last couple before we go?

## [00:50:18] VSCode, Copilot

[00:50:18] **Adam:** I got one that I can't, I can't leave without saying, and that is like a copilot and then as an extension of that VS code, right? So like, Hey, I love, I love working in VS code, but I also loved working in Sublime Text.

[00:50:28] **Adam:** So, you know, it just was like,

[00:50:30] **Ben:** Plus one for sublime text.

[00:50:33] **Adam:** Of course you're still on the old one, Ben. Yeah, yeah. So, like, I kind of just go where the ecosystem is, right? So, like, when Sublime, kind of stagnated and everybody moved over to VS Code, like, that's where all the new extensions are being built.

[00:50:47] **Adam:** That's where all the new functionality is. Like, that's kind of where I went, and it's great. And then, of course, Copilot just makes that an amazing experience. I know you can get Copilot even in, like, Vim, for example. But,

[00:50:57] **Tim:** you can never get out of them once you've opened it.

[00:51:00] **Adam:** I know how to exit Vim. That's why I'm a senior developer.

[00:51:03] **Tim:** I Google it every time.

## [00:51:06] Chrome Dev Tools

[00:51:06] **Ben:** Well, along the lines of development tools, I just want to say that. Chrome's developer tools continue to be just like world class. I have them open constantly and they just feel so much better than any of the other browsers. When I open Safari's dev tools, I don't even have to poke around. I immediately know they're terrible.

[00:51:27] **Ben:** Their iconography is terrible. Their spacing is terrible. Their margins and padding on their tooling is terrible. Like everything about the tool visually is awful. Chrome dev tool is just. I don't know, they knocked it out of the park and continued to evolve on it very rapidly. It's just very

[00:51:42] **Adam:** there's... So many people that like swear by Safari and I just don't understand it like are they broken or am I broken?

[00:51:50] **Ben:** Definitely, that's what I'm saying, it's like... You know, you know how you can open up a webpage and immediately you get a gut reaction. You're like, this webpage is awful. I can't trust this product. When I open Safari's DevTools, that's my immediate reaction. Every, everything about the design is awful.

[00:52:06] **Adam:** the browser Chrome itself. Like I open it up and it reminds me of like the 2002 era iPad that was like skeuomorphic design everything looks like it's a leather and got stitches and like brushed metal like just

[00:52:20] **Ben:** Agreed.

[00:52:22] **Adam:** just Yeah, and then also it's the new IE6, so.

[00:52:26] **Tim:** For sure.

## [00:52:27] Patreon

[00:52:27] **Adam:** Alright, well then this episode of Working Code is brought to you by IE 6, the, the hot new browser that everybody's gonna be switching to next month. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing and transcription costs, and we couldn't do this every week without them.

[00:52:48] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:52:52] Thanks For Listening!

[00:52:52] **Adam:** we are getting ready to go record our after show, which is one of the perks that we have for our patrons. and it looks like Tim has a topic he wants to discuss. something about the university system and he have failed his son.

[00:53:05] **Adam:** So, oh, sounds like the, the, the coattails are about to be yeeted out from underneath of you there, Tim.

[00:53:11] **Tim:** alright,

[00:53:11] **Adam:** But, hang on, hang on, hold it in. Two, two more minutes and we'll be in the

[00:53:15] **Tim:** alright, alright,

[00:53:16] **Adam:** So if you, if you want to hear, yeah, if you want to hear that and more, then you can go to patreon.com/workingcodepod, become a patron of the show.

[00:53:25] **Adam:** That's gonna do it for us this week. We'll catch you next week and until then,

[00:53:28] **Tim:** Remember everyone, your heart matters, and we are thankful for you. Our listeners.

[00:53:33] **Adam:** Tim, I am thankful for you because you always remember to, to do the, the, that, like, you express the feelings I would have if I had feelings.

[00:53:44] **Tim:** So why don't we make a good team?
