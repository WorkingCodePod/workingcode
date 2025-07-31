---
title: "226: To Sync or Not To Sync?"
description: "Sparked by an exploration of a competitor's API approach, the team share their thoughts on handling long-running tasks efficiently."
date: 2025-07-31
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/5476764c-9865-46a3-a279-0b0f82c6f7fb"></script><div class="redcirclePlayer-5476764c-9865-46a3-a279-0b0f82c6f7fb"></div>

In this week's episode, Adam, asks the question: To sync or not to sync? Sparked by an exploration of a competitor's API approach, the team share their thoughts on handling long-running tasks efficiently.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/226-to-sync-or-not-to-sync.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** you know, my gut reaction was like, ew, you get, you have to download a file for every API response and then parse that file.

[00:00:06] **Adam:** But then at the same time, I kind of had this thought like, maybe that's kind of a, a insightful approach because so many of, the use cases are gonna be get an API response and then dump it into a, an A CSV or an XLSX for the end user to have their data.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go. It is show number 226, and on today's show, we are going to be discussing to sync or not to sync. And I'm not gonna,

[00:00:52] **Tim:** question.

[00:00:53] **Adam:** I'm not gonna give you any more clues about that yet. You're just gonna have to stick in, tune in, turn on, tune out,

[00:01:00] **Tim:** Drop out, whatever.

[00:01:02] **Adam:** and you'll, you'll figure it out anyway, Carol's, unfortunately not able to be with us tonight, so it's just the boys again.

## [00:01:08] Ben's Fail: Dog Troubles

[00:01:08] **Adam:** Ben, I'm gonna come to you first. What's going on, my man?

[00:01:10] **Ben:** I'm gonna start us off with a little bit of failure, which is just that my dog is straight up killing me, which is morbid because she's the one that's dying,

[00:01:21] **Tim:** That is a little odd.

[00:01:22] **Ben:** but she is going out like three, four times a night sometimes. She's just urinating on herself all

[00:01:30] **Adam:** she on

[00:01:30] **Ben:** the house. Yes. I think she's on prednisone.

[00:01:34] **Ben:** She's definitely on a ster steroid. I think it is. Prednisone actually.

[00:01:37] **Adam:** do that. They make, it makes them. Our, our Lucy, who has also got cancer and was briefly on prednisone, she was having to go to the bathroom a lot and a couple of times like had no idea that she just peed herself, laying down on the couch or whatever.

[00:01:50] **Ben:** that's, we have, we have peepee proof blankets on like every sitting surface and bed surface, but then she'll just be laying on the floor and she gets up and there's just a puddle.

[00:02:02] **Adam:** Mm-hmm.

[00:02:03] **Ben:** we are, we're trying to affix a diaper to her, but she's got this tiny little butt and no tail and it just, it's constant, it's a constant battle.

[00:02:11] **Adam:** Yeah.

[00:02:11] **Tim:** Well look at it this way. This is a preview of your seventies, so.

[00:02:16] **Ben:** At least I can wear suspenders,

[00:02:18] **Tim:** Yeah. Getting up and peeing every two hours.

[00:02:21] **Ben:** but it's tough. It's just tough being in this in-between place where I, I feel like mentally she's still very much there. I do think she's a little dopey sometimes.Um. as usual or,

[00:02:33] **Ben:** No, there is times when, when she just looks like she's wandering around in a weird way. but she's happy. And when people come to the house, she gets very excited.

[00:02:43] **Ben:** But it's, it is just exhausting. And, uh,

[00:02:46] **Adam:** Yeah.

[00:02:47] **Ben:** it's, I I don't have, I don't have a lot of stamina. I'm, I'm finding

[00:02:50] **Adam:** Yeah. Can relate. Yeah. So because of our dog needing to go to the bathroom every couple of hours when she was on the steroids, we started keeping her in our bedroom overnight. We're usually like a, no dogs in the bedroom, not in the bed overnight sort of thing. They're, they're in their crates, but, because

[00:03:07] **Tim:** Have you had, have you had to clean the crane out a couple times? Change that rule, didn't you?

[00:03:11] **Adam:** no, it was, it's more just like, my, my wife is already a light sleeper, which is why we don't allow the dogs in the room. But then she wants to, now she wants to be woken up when the dog needs to go

[00:03:21] **Ben:** hmm.

[00:03:21] **Adam:** So, and then for a couple of, maybe for a week now, she hasn't really had any issues and has been able to hold her pee overnight and everything, which is great.

[00:03:30] **Adam:** But we still had her in the room, just I guess, because we feel bad, you know, we're trying to make the most of the, what life she has left. And, but man, two nights ago she just got so a bee in her bonnet about something and started barking. She like, walked over to my side of the bed, just barked

[00:03:44] **Ben:** in the middle of the night.

[00:03:45] **Tim:** She's like, wake up. We're gonna be murdered in our beds.

[00:03:48] **Adam:** 11 o'clock and midnight and, and like, just several times.

[00:03:53] **Adam:** and eventually I was like, I've had enough. You're gonna your crate, come on, let's go. And took her downstairs and put her in her crate.

[00:03:58] **Ben:** Dogs.

[00:03:58] **Adam:** I, I did, you know, I did take it as a signal like maybe she needs to go out. So I took her out on the leash and she just went out and stood in the grass and like stared at the woods behind her house.

[00:04:07] **Adam:** I think she thinks something's out there.

[00:04:10] **Ben:** I know that. Move.

[00:04:11] **Adam:** Yeah. So

[00:04:14] **Ben:** so that's me. I'll keep you all updated. Tim, what do you got going on?

[00:04:18] **Adam:** updated.

[00:04:19] **Tim:** Updated. Updated. Yeah.

## [00:04:21] Tim's Triumph: Weekend Getaway

[00:04:34] **Tim:** So I'm going with a triumph. I, I wish it were like a work related triumph. I like to keep this things kind of work related, but it's like, you know, sometimes it's like work, work is just copacetic, it's, you know, it's turning along, it's fine. Nothing, no big whoop, but personally it's like, I don't know, since 2020 we don't really just kind of, my wife and I just got outta the habit of like getting away from the weekend.

[00:04:41] **Tim:** Right. It's just like we became much more homebodies and trying to get outta that. And a few months ago she sent me an email, the Atlanta Falcons sent her something and they're like, it's like they have free,

[00:04:54] **Adam:** Are you trying out for the Falcons?

[00:04:56] **Tim:** yeah, yeah. Try not to. I'm gonna be a kicker. A 54-year-old kicker. No. they, they like went on my wife's permission first 'cause, you know, but anyway.

[00:05:04] **Tim:** No, they, they, they have like open training day, so you could actually go to their training camp, which is northeast side of Atlanta. A little, little town called Flowery Branch, Georgia, which is a cute little town. Only about 6,000 people there. But the 5,000 people showed up to the training day on Saturday and it was really cool.

[00:05:21] **Tim:** It was free. They had food trucks. It was like a party man. It was like they had DJs and they were selling merch and you could just, we sat on the ground on a hill, behind the goal, one of the goalposts. And just, it was nice and nice and shady. 'cause it was like, started at nine 30 and I ended around 1130 and we were far enough up the hill that the sun wasn't hitting us until right before it ended.

[00:05:43] **Tim:** So that was cool. And they had autograph sessions, but there was so many people for autographs. I didn't, I didn't even bother trying. I wanted to get de Jean Robinson's autograph, but it was pretty cool watching, watching the training and watch how it goes. I just frustrated that, you know, Kirk Cousins looked really, really good. He's our backup quarterback for the Falcons, you know, who's one of the highest paid QBs in the, in the league. But yet he's the backup. 'cause he really screwed up last year, but he was looking, he was looking fantastic. I'm like, oh, that's the last thing we need as a quarterback artist. But it was fun, it was nice to get away with my wife and just the two of us.

[00:06:16] **Tim:** And we went to, the town is on Lake Lanier, so Lake Lanier in Atlanta is, it's this manmade lake that they basically flooded this area. And there's all these stories about the ghosts of the graves of the people that were, you know, covered in water and how it's haunted if you ever, there was an episode of Atlanta with Donald Glover that was all, all about Lake Linear and it being haunted, which is pretty funny.

[00:06:40] **Tim:** but, but yeah, we went to the, this little tiki bar, which is right on the water and they had a, a live band. It was pretty cool. So it's just nice to hang out with my wife without the kids and have a weekend together and, and then come back and then we're absolutely. Exhausted for the next two days, so

[00:06:57] **Adam:** Yeah. Need a vacation when you get back from your vacation.

[00:07:00] **Tim:** exactly.

[00:07:02] **Tim:** The, the heat here doesn't help. It's like 105 heat index right now. So it's, it's, it's brutal here. I know it's brutal all over the states right now. There's this huge heat dome right now, but just, it's so brutal here. It's, it's terrible.

[00:07:15] **Ben:** I know when you were saying you were doing stuff outside, I was actually kind of surprised.

[00:07:19] **Tim:** Yeah, it wasn't bad in the shade in, in the morning, but yeah.

[00:07:22] **Ben:** what it is, man. That sun, it's so freaking intense. There's a good chunk of the year in the Northeast at least. Where if you are standing in the shadow of something, it can be downright chilly. And then you take two steps over into the sun and it's, you just feel like you're baking all of a sudden.

[00:07:38] **Tim:** Yeah. What was that, what was that movie with, VIN Diesel where it was in the dark? What

[00:07:44] **Ben:** Oh yeah. It was ridic Chronicles of ridic. They gotta go to

[00:07:48] **Tim:** That, that planet where the sun, the sun comes out, like just fries everyone if you're in the sun. That's kind of how Georgia is right now. If you're not, if you're not not in the shade, you're gonna just completely disintegrate.

[00:07:59] **Ben:** Well, this is my thing. I, I don't understand. Okay. I'm not a sun person. I know that there are people who just love being in the sun. I have to be outside because of the dog. Like, that's mostly why I'm outside. so if I go eat at a restaurant, it's always has to be a restaurant with a patio. 'cause the dog is with us and it.

[00:08:17] **Ben:** Blows my mind that not every single outdoor patio either has full umbrella coverage or some sort of area tarp. I just don't know who can sit out like that. It's mind bog.

[00:08:31] **Tim:** Or, or the people like growing up when I was growing up, like people would like rub Crisco on their chest and go lay out in the sun, like, oh my

[00:08:38] **Adam:** a mirror to, to put more sun on your face. Yeah.

[00:08:42] **Tim:** These people, they're, they're, they're crispy, fried now on their chest, so it's like,but anyway, that, it was, it was fun. It was, it was nice to have a getaway weekend that was of nothing particular, just to do, go do something fun.

[00:08:53] **Tim:** And it was fun. So,

[00:08:54] **Adam:** Cool. Good

[00:08:55] **Tim:** and, and the kids didn't die, so

[00:08:57] **Ben:** Nice bonus.

[00:08:58] **Adam:** triumph.

[00:08:59] **Tim:** double try. How about you, Adam?

[00:09:01] **Adam:** I

## [00:09:01] Adam's Triumph: Backups

[00:09:03] **Adam:** am also gonna go with a triumph. this is going to be the little bit of a throwback to something we've talked about on the show before. I am now backing up my laptop, which woo, sounds like not that big of a triumph. Let tell you, I had, I looked because it's a, it's a whole kind of process you have to go through to, to, I use Backblaze for my backups.

[00:09:21] **Adam:** It's a cloud backup service.and I, I had previously been backing up my laptop and then went a couple of years without, and, and so to transfer the license to the new machine, I had to, Go through this process. And so when you do that, you can see how old your backups are and they give you a chance to like download whatever from the backups before you delete it sort of thing.

[00:09:42] **Adam:** So my, my previous backups were 1300 days old. and, and changed, I don't know the exact number off the top of my head, but, that's like three and a half years that I went without backing up my laptop. I'm just very grateful that nothing bad happened in the meantime. and I think honestly the, the big thing was like, I think I got a new computer and I wasn't, you know, I was like too afraid to delete the backups from the previous computer.

[00:10:08] **Adam:** 'cause like, oh, what if I need something that's on there? Right? And I didn't have the storage space to like, download all that whole backup and keep it around and still have room to, to work on my computer. So a lot has changed since then. I have a NAS now. and also I, I kind of had this realization that like, it's been three and a half years and I haven't needed to download anything from that.

[00:10:28] **Adam:** If there's anything in there that, is actually of value, like. I wouldn't know anymore anyway,

[00:10:34] **Tim:** Nowhere to find it now.

[00:10:35] **Adam:** yeah, I just yolo deleted it. Like, okay, well, statute of limitations on that backup is up, it's gone. And I get to declare backup bankruptcy and start over with my new machine. So that's nice. Backing up now, just a little peace of mind.

[00:10:50] **Tim:** So is it expensive to pack up to the cloud?

[00:10:53] **Adam:** I don't recall the, the amount, it's, I, we went with that place because it's pretty cheap.

[00:10:58] **Ben:** I also feel like that's the only one I ever hear anyone talk about.

[00:11:02] **Adam:** yeah, it's, it's pretty popular. I remember it being relatively inexpensive and I just, I haven't thought about it because we've been paying for it for years and years and years. We've been on there for probably 15 years.

[00:11:12] **Tim:** Oh, wow.

[00:11:13] **Adam:** and you know, we use it for my wife's machine and now I'm starting to think, like, I wonder if there's a way where I can get another license and have it back up my nas.

[00:11:21] **Adam:** but I don't know. We'll, that's something to look into. Is on raid five anyway, so, you know, it's got like a single disc can fail. I think even two discs could fail and it would be able to

[00:11:31] **Tim:** five. Yeah.

[00:11:32] **Ben:** Yeah. So, I think I

[00:11:34] **Adam:** may be slow, but it could recover.

[00:11:36] **Ben:** I feel like I recently heard someone talking about a service that they use where. You, you're backing up remotely, but it's to a friend's computer. You kind of create this friend network and then everybody backs up to each other's computers kind of a thing.

[00:11:49] **Adam:** that is an interesting idea. But what it means is that all, all of your friends have to have a ton of extra storage space to hold your backups. It's kind of like, I don't know,

[00:11:58] **Ben:** I, you

[00:11:58] **Adam:** sounds interesting, but I don't think it's that practical. Mm-hmm.

[00:12:01] **Ben:** one thing that drives me crazy is we have a Dropbox family plan. And so I have, like, what I used to use a documents folder for is basically now my Dropbox folder and people are always like, oh, you can't depend on Dropbox as a backup mechanism. And I don't know, I feel like that's a cop out.

[00:12:22] **Ben:** That's like saying, oh, don't depend on your bank for keeping your money. I'm like, but that's the bank's business.

[00:12:28] **Adam:** Yeah,

[00:12:30] **Ben:** I feel like if I can't depend on a business for doing their business, then what's the point?

[00:12:33] **Tim:** As long as it's not a Google service that they'll just kill, like they just killed, like they just killed all the shortening links that they had for decades.

[00:12:40] **Adam:** yeah, the, the bank is also insured up to a hundred grand, so,

[00:12:46] **Ben:** No, I think it's to 250.

[00:12:48] **Tim:** Two

[00:12:48] **Adam:** is it okay. It shows you how much I pay attention.

[00:12:52] **Ben:** Well, I only know that from the movies because they're always talking about it. Like when people come into Rob Banks, they always talk about it.

[00:12:59] **Tim:** I, I only know that 'cause we have to tell our customers that like, yeah, if you got more than 250, you're gonna have to spread your money across some accounts.

[00:13:06] **Ben:** Nice.

[00:13:07] **Adam:** So that's it for me. Easy win. Not, not so me, I guess. It was kind of easy, but, low stakes.

## [00:13:14] Main Topic: To Sync or Not to Sync

[00:13:15] **Adam:** Anyway, so let's move on to our topic for the day to sync or not to sync. and this has nothing to do with backups, but that, that was a nice little tie in there. basically, my company, we have been doing some oppo research a little bit on, on some of our competition, and we found something curious about the API of one of our competitors, and it gave me this idea for a topic, to, to talk about, for lack of a better word, let's call it the user interface of the API or like the way it's structured, the way it, the way you work with it, right?

[00:13:42] **Adam:** So you might be thinking if you're, if you're a fan of rest and if you've read a certain. API design book, you might be thinking to yourself like, what, what could you possibly mean? Like there's only really one more or less standard way to do it, right? You, you make a request, you get a response, it's got the data in it.

[00:14:00] **Adam:** Maybe it took a couple seconds to look that response up or whatever, but you know, you got it back synchronously.this, when we got into the API docs for this competitor, every single request that you can make to their API, you just get like a request ID back and that. So what's that? What this is implying to me is they're queuing your request and then they might have a fleet of auto-scaling, API servers that, handle those requests from the queue.

[00:14:27] **Adam:** and the way it works is you make your request, you get a request ID back, and then you're supposed to start polling a, a different API resource for the result. Like, here's my request id, is my result ready yet? And it might say no. And then so you wait a up. 10th of a second or something, and you, poll again, right?

[00:14:45] **Adam:** Until you just keep polling until you get your response. And then the response has like a, a status and a URL to download a file of the results, which is kind of bizarre to me. so that, and that's basically the, the, the inspiration for this. I know there's other things we can get into as well, but like that being the inspiration is just, I have some thoughts on that as well.

[00:15:11] **Adam:** Like there's, there's some interesting and good things about that design, but there's also, it's like, why, why would you do that?

[00:15:19] **Ben:** Well, I know one of the things when at at Envision, we were always trying to figure out ways, or I shouldn't say always at the end, we were trying to figure out ways to cut costs, and one of the things that kept coming up was this idea of can we move from Amazon S3, which is primarily a synchronous API.

[00:15:37] **Ben:** You get the request and response in the same breath versus something like Amazon's glacier. Which is a very, I think it's like tape backups behind the scene or something very slow. And if you want to get data out of glacier, it's that same kind of thing. You have to request it, and then they give you a request token, and then you just basically have to keep asking glacier, Hey, is my backup available yet?

[00:16:03] **Ben:** Is my backup available yet?

[00:16:05] **Adam:** Hmm. I didn't, I wasn't aware of that.

[00:16:07] **Ben:** that's my understanding at least we never actually did it because it would radically transform the way we would even think about storage.

[00:16:14] **Adam:** right.

[00:16:15] **Ben:** And you really have to, it becomes like a turtles all the way down

[00:16:18] **Adam:** Yeah. Yeah. I, I, I agree. So, I mean, I guess my, I, if you want, I can throw out my, my kind of hot takes on this design, so, okay. So you have like on, on the first hand. It's great because it, you know, I'm assuming that my, my assumption is correct that, it allows them to queue requests and they can handle those with without, like DDoSing, their API servers, right?

[00:16:44] **Adam:** It doesn't matter how many requests come in, they just get queued, they get a response I, or request ID back. And API servers are fine, right? And then you'll get your response. When you get your response. Maybe normal response times are 200 milliseconds and when they get flooded, maybe it goes down to two seconds or 10 seconds or two minutes, but eventually you get your response, right?

[00:17:03] **Adam:** so in that regard, I think it's clever, right? It's a good way to decouple request volume from ability to, to process that. And you just end up with some lag in there if you get swarmed.so I like that about it, but it's very, it seems backwards, right? Like. Here. The thing, the, the immediate response I have is like if your, if the application software that, like the application server layer that you're using to accept the API request and then queue the request or, or handle, you know, the, the data look up, whatever it is, is so bad at waiting for the io. Then maybe the, that layer, that application server is your problem, right? Like not to, not to, you know, always beat on the same drum, but node is really good at. Fire off an async request and it, it takes basically zero memory and, and zero CPU time until you get a response.

[00:18:11] **Adam:** Right? So you can have hundreds or thousands of async requests coming in that are just pooled and sitting there waiting for their response to come back in. And then you just, when they're, when it, when the function, you know, you've got an async function, a promise comes back, then it sends the, the result back to the customer.

[00:18:30] **Adam:** And I mean, I guess if you, if you were getting to the point where occasionally you're getting to these like two minute, three minute response times, then maybe queuing it makes more sense. I don't know that I would have it work the same way polling. 'cause then you're inviting somebody to abuse the polling for a

[00:18:46] **Tim:** Right. Yeah, that's what I was gonna say. What I don't like about that, I mean, I like the idea of an async request. 'cause I, so that's how our SMS provider, we use Plivo, for our SMS provider. And that's somewhat how it works. It's slightly different and it's, if I were doing something similar, it's how I would do it.

[00:19:03] **Tim:** So you send the SMS request and they just basically immediately come back. With an okay. And then you have a, a reference number that refer, refer refers to that. But then you also use, within the same payload, you've submitted a, a callback page. So whenever it's done, it sends you, it sends you the callback.

[00:19:24] **Adam:** Like a web hook,

[00:19:25] **Tim:** yeah, it's like a, like a webhook. Yeah. So, so it, you know, that whenever, that SMS is delivered or anything happens, you know, 'cause SMS will, or, and we also do this for SendGrid as well, you know, it'll say that the email was, was processed, the email was delivered, the email was clicked, the email was opened, or it bounced, right?

[00:19:44] **Tim:** All those are callback hooks that, that you can have. And so you just processes tho those there. I mean, putting the, the onus on the API user to come up with a polling service just seems a little heavy handed to me.

[00:20:00] **Adam:** Right. To me that sounds like you should have just done that in your app. Like if you really needed to use the queuing thing and you couldn't just like await a promise, then your API layer should be doing that polling. That way you control how much you're, you're hitting the, the, the wherever you're looking for the results, right?

[00:20:19] **Adam:** So you're not, you're not DDoSing that thing.like I, I get the need to queue and, and scale out, but it just seems kind of shortsighted to me.

## [00:20:31] Handling Large Files

[00:20:31] **Adam:** Now, I will say, you know, we, we sim we just Like You, Tim, have a service where our customers will, push us,some data to us, like make an API request. We expect that sometimes those requests will take like 15 minutes, right?

[00:20:45] **Adam:** Sometimes those requests are, here's the name of a file that I put on S3 for you. I want you to import this as a database table, right? And so, you know, if it's a huge file, we're talking sometimes like 10, 15 megs or, or for the really big ones, even like a gig or two. And this is like a zip file of, a table that's got 200 rows or 200 columns wide, you know, 500,000 rows.

[00:21:09] **Adam:** it takes more than a few seconds to process that. Right now. We have to download it, we have to validate that it's the right structure, and then we have to import the data and run some post-processing on that. It takes time. So, that particular API resource, has two different notification methods on it.

[00:21:25] **Adam:** It's got like email for those that are not necessarily technically inclined. So you can just get an email that says, here's the status of your job. This was the request id, it completed successfully. Or it had these validation errors, or it had this runtime error or whatever. Or you can get a webhook notification.

[00:21:42] **Adam:** You, you know, in your API request, you include a URL to hit. So if you want to have it specific to that file, right, you include a grid in that URL or whatever to, to, give that data back to you. That's fine. You just give us the URL, we're gonna send a post to that URL and this is the payload we're gonna send.

[00:21:58] **Adam:** This will be the shape of it. You know, it might be an array of error messages in this key and whatever, but, and that's been working out great for us. Now we only have a handful of customers that are actually proficient enough to use that. But, where it gets used, it's really, it's, it's gratifying to see it used well.

[00:22:17] **Tim:** Yeah, it's, it's funny you brought this topic up 'cause today we were talking about that we have A-A-P-D-F service where it's gener a sister company that is consuming PDFs that we output and they actually physically print them. And some of these insurance companies, it's taking like five, six hours for them to. Generate the, PDF packages that need to be generated. And a lot of that is 'cause, I mean, we're generating it in cold fusion and it's, you know, it's not using any sort of asynchronous and it's blocking and the resources get used up and it starts, it starts to really slow down. cer only a certain number of threads that you wind up being able to, to use while you're generating PDFs.

[00:23:00] **Tim:** But I was like, if we could put this to an asynchronous service and then use a different library to generate the PDFs and you just queue it up and then at the end of it, it calls back a endpoint and sends you all the files or something, that'd be useful. So it's, that's, it's funny you brought this up 'cause it's very top of mind for me today trying to figure out how to do this.

[00:23:20] **Ben:** The PDF stuff was actually a real issue for us at Envision because when the application was very small and we had such a small number of users, and the documents that they were creating were relatively small, they could generate PDFs on the fly and they'd be done, you know, in five seconds. But then as the system started to grow and people started to create, it wasn't a prototype with three pages.

[00:23:44] **Ben:** It was a prototype with 175 pages and, and those now need to become A PDF. Suddenly we were running into actual timeout requests and, and because we were in a horizontally scaled application, we had our ColdFusion server. Then in front of it, there was an Nginx server, and then in front of that, there was like a Kubernetes.

[00:24:05] **Ben:** Load balancer. And then in front of that there was an Amazon elastic load balancer or something. And then in front of that was CloudFlare. And if someone had to make a request through all of these layers to generate that PDF, it's like any single one of those layers could at one point say, Hey, you've run for too long.

[00:24:24] **Ben:** We're just gonna cancel this request. And the thing is, is that by the time we had gotten to that, like we had sort of so much application, UI and experience around how it works synchronously that to convert to an asynchronous workflow just was, was more effort than anyone actually wanted to put into it. ' cause it is definitely, you really have to change the way you think about application design when you introduce asynchronicity to it.

[00:24:51] **Tim:** For sure.

[00:24:53] **Ben:** And it's not easy. Oh my God, if I can go tangent for two seconds. When microservices were like peak. Like it wasn't even peak hype yet. It was. It was like people had just started talking about microservices and there was this buzz about how exciting this could be.

[00:25:07] **Ben:** I was remember watching this presentation, I think maybe it was from the go-to conference. And this guy was saying how great this is. It's so easy and powerful. Take for example, this idea that someone's checking out at a car rental place. And so you put in your request to get a car rental, and then one service admits an event into your event stream that a, that a quote has been requested.

[00:25:32] **Ben:** And then you have a quote calculation microservice listening on that. And it receives that event and it looks at the customer data and it looks at the prior history, and it looks at the deals and tries to come up with a quote. And then it emits like a quote calculated event back onto the event stream.

[00:25:48] **Ben:** And then your original event that's been stopped, like blocked and is waiting is like now waiting for other events to come back in that same request. And they're like, and if it takes too long, you know, if it takes more than two or 300 milliseconds, you can just have a default to a, like a fixed quote. I'm like, none of this sounds easy.

[00:26:05] **Ben:** What are you talking about? This sounds awful. So anyway, I, you know, I guess it's all perspective as.

[00:26:14] **Adam:** Yeah, for sure.

## [00:26:15] Meeting the User Where They Are

[00:26:16] **Adam:** So, back on the main thread here. another thing that I found kind of interesting about this, this particular API when we were doing this OPO research was, you know, it says you get a,

[00:26:27] **Tim:** say apo, you mean opposition research, right?

[00:26:29] **Adam:** yes. Yeah. I, I forget where I picked that OPO research term up

[00:26:33] **Tim:** It's astan. It's a standard term.

[00:26:35] **Adam:** yeah, I'm just Oh, you're, you're, you're asking me for the benefit of the listener.

[00:26:39] **Adam:** I see. Uh,yeah, so the, you know, you get the status and the download, URL once the, the, the response is generated, right? So it then it requires a third step where you now you have to make a request to download the file assuming that the status was successful.and I don't know offhand, I haven't dug in far enough yet, but I don't know if you're getting JSON or X ml back like you would from a traditional web API or if they're giving back like a CSV or an Excel file.

[00:27:10] **Adam:** Right. This industry that we're in, the, the colleges man, the, and I'm sure most other industries too, the, the non-techie people, the non, the non nerds, they live in Excel. Right? and they don't appreciate the value of the automation that you can get with JSON or XML. But, so, you know, my gut reaction was like, ew, you get, you have to download a file for every API response and then parse that file.

[00:27:36] **Adam:** But then at the same time, I kind of had this thought like, maybe that's kind of a, a insightful approach because so many of, the use cases are gonna be get an API response and then dump it into a, an A CSV or an XLSX for the end user to have their data. Right? Like, that's probably, I don't know, maybe 40% of, the, the integrations that we're doing, like the API requests that we get are. To generate some, like a, a file output for the end user. we do have a lot of other integrations that we encourage a lot of, automation, right? So the, especially the accounting stuff, right? We're doing event registration and online giving are sort of our two biggest lines of business. And that's a lot of real time data to, to chew through and to like batch it up daily or even like every, every half day, into Excel files that somebody then has to deal with would be a terrible process.

[00:28:37] **Adam:** So we, you know, we encourage them to like, you know, daily or, or however often they wanna do it, like hit our API start here. This is where you get the list of like, transactions that's happened or event registrations, whatever, and here's how you spider out and, and handle all of that.but like I said.

[00:28:52] **Adam:** There's a lot of use cases where what they really want at the end of the day is just like an Excel file that they can go stare at and like, oh, what if I sort it this way? What if I filter down to this? Right? They want, they want to do kind of bi business intelligence stuff with it, which I can appreciate.

[00:29:09] **Adam:** and so there's an element of like, are they just meeting the users where they are? Right. Are they saving the users a step by doing that? I, I don't know if that's truly the case, but it's an interesting question to explore. And I mean, I will say for our API, any of the responses that we return that are what I'll call flat, like all of our responses are JSO by default.

[00:29:31] **Adam:** But if, if that response is an array of objects with no, like sub objects, then we offer, the ability to get that back as a CSV, right? You still get the exact same data, but instead of a, an array of JSON objects, you just get a CSV file

[00:29:47] **Ben:** I think that makes sense because it's also, even if you don't live in Excel, I mean. A lot of people have some experience with Google spreadsheets, and you can just upload a CSV directly into a spreadsheet, which has been pretty helpful. If you don't have, I mean, windows is really the best place to do Excel.

[00:30:06] **Ben:** what, what's the, the one on Macs, like numbers or

[00:30:09] **Adam:** Yeah, it's called numbers.

[00:30:11] **Ben:** Or, you know, it's comparatively awful.

[00:30:13] **Adam:** it is. It's fine if everyone that you ever have to work with is also using like the same version of numbers,

[00:30:21] **Ben:** It just, the whole experience of it feels like they, it feels like the people who built it never used a spreadsheet

[00:30:29] **Adam:** yeah.

[00:30:30] **Ben:** and not like I'm a power spreadsheet user. I just like, when I go to Excel or when I go to Google spreadsheets, I'm like, Hmm, this is a spreadsheet application. And then when I open up numbers, I'm like, Hmm, these, this is not a spreadsheet application.

[00:30:42] **Tim:** I'm sorry, what is numbers? I've

[00:30:44] **Ben:** Numbers is, is the Mac equivalent, like it comes with the computer? I think it's the Mac equivalent of the spreadsheet

[00:30:51] **Adam:** F Excel. Yeah.

[00:30:52] **Tim:** So let some graphics designers try to design a

[00:30:55] **Ben:** It, it feels very much like that. Yes.

[00:30:58] **Adam:** is like we have to have a spreadsheet app go make one. Okay. Done.

[00:31:02] **Ben:** It's like every spreadsheet application in the world, you open it up and you immediately get a, a full screen of cells and numbers. You open it up and it's like, it's like a Word document full of cells. It's just really weird. I don't understand they built it this way,

[00:31:19] **Adam:** Yeah. I get, honestly, I think the only time I ever see numbers files anymore is like when somebody created it from their iPad. Right. And then they like email it to them or email it to me or whatever. But

[00:31:31] **Ben:** or like if I accidentally double click on an Excel file, like not meaning to, and then numbers opens up.

[00:31:38] **Adam:** Oh man. my turn for a tangent. I cannot stand the, the, this is the year of our Lord, 2025 and a, an obscene amount of people still double click on links on the internet.

[00:31:55] **Tim:** I know. It's so,

[00:31:58] **Adam:** the is wrong with you?

[00:32:01] **Ben:** Oh my goodness.

[00:32:04] **Tim:** yeah, and it, it is not just old people either. I've seen my kids do it. I'm like, what are you doing? Stop that.

[00:32:11] **Adam:** man, that no excuse for that. Your kids just lost a point in my book.

[00:32:15] **Tim:** I know. They, they, they deserved it. I, I totally chewed them out. I'm like, why? Why are you double clicking there? Because it didn't open. I'm like, you gave it like, not even like two thirds of a second before you clicked it again.

[00:32:26] **Ben:**

## [00:32:26] Complex Queries

[00:32:26] **Ben:** if I can go. Kind of more towards the user for a second in terms of asynchronicity. here's something that I grapple with and I haven't quite taken the leap. So to paint it in, in an alumni queue context for, for metaphor here, for analogy, whatever the right word would be. Imagine that you wanted to get a list of universities, and then in that list of universities, you wanna also get the number of donations that have been made this year.

[00:32:54] **Ben:** And in that same row, the total amount that's been donated, and maybe also like the top donor in that particular university. You know, kind of, kind of like a, like a little sprinkling of business intelligence mixed into your kind of generic search results.

[00:33:08] **Adam:** Okay.

[00:33:09] **Ben:** And like the, the kind of idea ish way to do that is to have all of those numbers be pre-calculated.

[00:33:18] **Ben:** On some ongoing basis. Like every night we run a calculation and it, and it builds all these stats so that when I pull that table back, I just joined this like alumni stats table and I Bingo. Bingo. It's, it's ready to go.

[00:33:31] **Adam:** Yeah. We do that with, the thing that generates the most stats for us is, mail, right? Just 'cause we send so much email. And so we do have processes that run like every hour, and it looks like the, at the last four or five hours of, of stuff that's come in. So there's a lot of overlap intentionally so

[00:33:50] **Ben:** it like rolls up kind of

[00:33:52] **Adam:** Yeah.

[00:33:52] **Adam:** Yeah. We call it roll up stats, right? so that if for whatever reason that hour the job failed, the, the job server was rebooting and we missed that job for some reason, or, or whatever, the next, you know, we've got like four more chances to cover that hour. So we. Know that we're not missing any stats from that hour, but

[00:34:10] **Ben:** So, so that's like the smart way to do it. A hundred percent. That's the ideal way to do it. The dumb way to do it, which full disclosure is typically the way that I do it, which is, is like I get the list of, of a, of universities and then in the select query I then have a bunch of subqueries that say and get me, you know, select some of of donations for this university and select count of donations from this university and like select top one of donors order by amount, descending limit one kind of a thing, right?

[00:34:42] **Ben:** And so. Essentially, what is I, conceptually one query to get the data is actually like an n plus one query behind the scenes. So that's awful. But you know, the thing is, is when you're designing a ui, it never starts that way. You know, you start with, and then Steve says, Hey Adam, it'd be actually kind of great to see the number of of mails that went out in the last hour and go, oh, okay, no problem.

[00:35:07] **Ben:** And he's like, Hey, you know what? Also, I just got off the phone with, a university and they'd like to see this and that. Right? So it, it kind of, it, it, the, I I hear economists use the term accrete, like all of the requirements get accreted over time and, and, and this application builds up anyway. The, the one thing that I've never tried, but I've always been curious, would be to render the initial page with the super fast query, like just the list of universities, and then make an asynchronous request, tying it back into the discussion here, from the browser.

[00:35:41] **Ben:** Back to the server and say, Hey, here's the current page results I'm looking at. It's got these 35 universities listed now go get me the stats for these. So it's like you get all the benefits of that super fast page load, but you don't necessarily have to be so smart about it. And then you can come and, and like maybe there's like a little gray skeleton thing in, in a couple of the columns saying, I feel like I've seen that be done in a couple of places and I've always wanted to try it and I've, I've just never done it.

[00:36:12] **Adam:** Yeah. You have to, it's, it's like thinking about, above the fold content on a page, but in a little bit more of a dynamic visual way. Right. It's not just what's above the fold, literally, but what

[00:36:22] **Ben:** what are the important columns and what are the nice to have columns in this data grid?

[00:36:28] **Adam:** Right. And also like, in a way, it, it helps if you can run that async request in a way that's like, okay, this one request is gonna fill in the whole

[00:36:37] **Ben:** Right, right. 'cause you don't want to do an n plus one query from the client back to the browser. Now, you know, like the one thing to do it when you're already in the database, it's another to do it from the browser.

[00:36:48] **Adam:** Right. And so in case that wasn't clear for the listeners, if you've got, you generate a page using the minimal query and you've got 500 rows in that table, and now you've got three other rows that you're trying to load dynamically. You don't wanna have to have 500 times three async requests running up to the browser.

[00:37:05] **Adam:** You want maybe three, maybe two, maybe one async request that's gonna get all of that data to fill in, the rest of those, whatever grid

[00:37:13] **Ben:** right. Exactly. It's like if you could, if you had a, a spel ruin representing that data grid.

[00:37:20] **Tim:** You know, you just waving red meat in front of him. Now

[00:37:22] **Ben:** and then if you could, if you could go back to the data to the server and say, Hey, get me these three columns and then just merge it into that run. I don't know if I'm using the right terms here. And

[00:37:33] **Adam:** You're not, but it's okay. I'm enjoying it

[00:37:35] **Ben:** okay, this, these sub data points have now become available and I will just update that data grid.

[00:37:41] **Tim:** so, You, you, you got me going here. he triggered him.

[00:37:44] **Adam:** we have a, a internal tool for our team. We call it our engineering dashboard. And it has something kind of similar to that. So you had mentioned like, you know, okay, if I wanna, load this sort of summary data across all of these universities, right? But our customers have individual api.

[00:38:02] **Adam:** We don't have like one API that covers all universities. We have, if we have 15 customers, then we have 15 different APIs that we would have to hit.and, so in order to make life suck a little less, when you're trying to like view summary data across the entire ecosystem of all of our customers, like what is the current status of all outbound mail right in the queue across all end customers.

[00:38:26] **Adam:** That's kind of a pain in the butt to do without something like what you're talking about this like across all summary. So I have an app that, This engineering dashboard, it can dynamically look up what is the current list of customers, and then from there it fans out the like kind of n plus one query where it's like, okay, I need to hit each of their APIs to get the current list of mail in the queue.

[00:38:45] **Adam:** And, and each of them, as the data comes back, kind of fills in this data structure that's available. And so when I make a request to that page in our engineering dashboard to say, what is the current status of the mail? I get an instant ish response, right? Like less than a hundred milliseconds, but it may not be complete or it might be slightly outdated for this one customer or whatever.

[00:39:06] **Adam:** and it shows me like the, the, the load times and the last, loaded timestamp, for each of those customers, right? So I can see, oh, this particular school, their API's running slow. I should go look at that. or it's 10 minutes behind. I should go look at that. and, and that's really nice. But yeah, so that like that's sort of thing is just something to be mindful of when you're developing these.

[00:39:28] **Ben:** Okay. So something you said there also made me think about Asynchronicity on the, I dunno if the asynchronicity is not quite the right term. It's more like parallel requests. So let's say it's, you're rendering this dashboard and you have to get all this data, you could, I'm, I'm just using this as a harness for the conversation here.

[00:39:50] **Ben:** Let's say you have 15 universities, you need to get data for them. So you could, on the server side, in the span of a single request, say, get me these 15 universities for the top level. And then you could do, like a, an asynchronous for each, which I, I think is the thing we can do these days in JavaScript.

[00:40:10] **Adam:** I think you're thinking a four in, but yeah.

[00:40:11] **Ben:** well, you, you could do like a, like a map onto a set of promises too, right? Like, I'm gonna take this array and I'm gonna map it, and then each iteration is actually gonna launch an asynchronous request to get the more rich data for this university. The, the, the struggle that I've always had with that kind of an approach.

[00:40:29] **Ben:** Which is kind of fetching data in parallel as opposed to in se in series, like, which is more of a cult fusion, you know, like, I'm gonna get the user, then I'm gonna get the project, then I'm gonna get all the comments, then I'm gonna get all the, you know, such and such. Is it if one or two of those requests fails, whether it's because there's a timeout or you know, the, the API is down

[00:40:52] **Adam:** Swamp gas

[00:40:53] **Ben:** Yeah. Like, you as the developer now have to make a judgment call. Does the whole request fail or do I return 13 universities and, and two of them have error responses? and it's like, there's no, there's no obvious answer. There's no, like, this is the one way to do it.

[00:41:13] **Adam:** Yeah. I, I don't know. It's been a long time since I've paid any close attention to new advancements in the C FM L language, but. Something that I've really, a tool that I've made a lot of use of off my tool belt in JavaScript is instead of promise at all, promise at all, settled, which, you know, basically if you're using Promise not all, and you've got 30 promises in there and one of them rejects, then immediately the whole thing rejects and you get none of the data.

[00:41:42] **Ben:** Right. You get, you basically get the first error that becomes an error.

[00:41:45] **Adam:** right?all settled, takes your, the response that you get from the promise and kind of wraps it in an object and says, was it successful? Yes or no? And then this is what you got back, either the rejection or the the result data. and so you still get, like with the promise that all settled, you're kind of guaranteed a quote unquote successful resolution to that promise of the all settled.

[00:42:07] **Adam:** And then you just have to handle on an individual basis of the promises that were in that, collection.so if you, in, like you said, if that one times out or if you're cosmic bit shifting swamp gas, so, then you can handle that and you can, you can, it's a lot easier I think, to kind of approach it from that higher level and say, okay, the, you know, we're, we're loading these chunks of data and they're gonna go into these places in some data structure.

[00:42:34] **Adam:** And then when I'm rendering the view based off of that data structure, then I can say, well, this data wasn't able to load, or whatever. You know,

## [00:42:42] Complexities of Asynchronous Work

[00:42:42] **Ben:** Okay, so this, this is an interesting thing because I think this is also part of the complexity of asynchronous work. When you're dealing in a synchronous world and everything either

[00:42:53] **Adam:** hang on, I wanna stop you when you're dealing in a synchronous world. Right. Okay.

[00:42:57] **Ben:** with an synchronous world,

[00:42:59] **Adam:** Okay.

[00:43:00] **Ben:** everything either works or it doesn't work. So when you're thinking about how to design a product, you really only have two modes of thinking. You have the happy path and the sad path. And if you're working with a designer, you know, obviously they're gonna design the happy path.

[00:43:17] **Ben:** That's basically their job.and, and you know, a good designer will also give you a sad path or, you know, some concept that you can

[00:43:25] **Adam:** Concepts of a plan of a sad

[00:43:27] **Ben:** Yeah, yeah, exactly. Is in cleans.but when you deal with this asynchronous kind of data fetching where some things can break and some things can succeed, you're in this kind of murky world where it's no longer just an engineering question because everything becomes a trade off.

[00:43:46] **Ben:** How do I want to handle this? Is it more important that this succeeds or is it more important that we can deliver something? And then if we can only deliver something, do we have to give the user a notification that it didn't work? We have to give them the option to retry everything, or retry just those things and like.

[00:44:02] **Ben:** None of those, I think, are things that an engineer historically has felt gung-ho. I have the answer for this. I, I mean, there's a lot of us, myself included, who have a lot of strong opinions about stuff, but it, it becomes one of those things because we're in this sort of asynchronous, murky world now, it really, we have to come together to figure out how to build this thing in a way that has a nice user experience.

[00:44:28] **Ben:** And that is part of the complexity. It's not just the technical aspects, it's the holistic, what does this even mean downstream to the user kind of aspects

[00:44:39] **Adam:** Yeah.

[00:44:39] **Tim:** So I'll, I'll kind of flip this on its head a little bit. So I had a. Conversation with one of, people that for the past, like five, six years have been consuming an API that I wrote, for them.it, it's based off of Taffy that IO that

[00:44:53] **Ben:** toy?

[00:44:54] **Tim:** I call it, I call it

[00:44:55] **Adam:** Toffee. Yeah,

[00:44:56] **Ben:** Oh yeah. You mentioned.

[00:44:57] **Tim:** I call it toffee.

[00:44:59] **Tim:** 'cause it is sticky. It's like, it basically we have, it basically grabs data from all of our customers so that we can do payments related stuff for them. But so we were having sort of a design discussion with them and they were pointing out that, you know, 'cause what I did was I made very early on, I didn't want, I didn't want any one end point to be, to take very long.

[00:45:21] **Tim:** It should just have a very specific purpose. You pass it may one parameter, maybe two that are readily known. It's not like some obscure ID that you have to know or some or something. And, and it gives you back. An atomic bit of data. So it's inherently gonna be fast. It's just not grabbing, it's not doing huge joins or anything.it's one or two of them do a little bit more complex stuff and they do take a little bit of time, and it's some of them, because it's ColdFusion and I'm talking to different servers that are different levels of optimized and I have a direct data source connection to them, and I don't have full control over how well optimized database is.

[00:46:01] **Tim:** Some of them do take a little bit at a time, but what they did their salt work around for it was they asynchronously, they know like there's only like maybe 15 endpoints that they're going to typically call. And so as soon as they have the key data, they can base off of one bit of data, do a call, and then do the other 14 calls and queue those up asynchronously.

[00:46:24] **Tim:** And that by time the individual, you know, who's logged into the system. It's starting to actually do stuff. By the time that has happened in the background, all of that stuff is loaded up. So I'll look at like the, at the trace logs and the fusion reactor and I'll see they'll come in, they'll do the initial call and boom, it fires off all these requests they're taken.

[00:46:47] **Tim:** I mean between, you know, half a millisecond, you know, 500 milliseconds or some of them in like four or five seconds. And if you total it all up, it's like that's a lot of time. 'cause there's like 15 of them. But they're all happening simultaneously. So the user experience is not bad because they, not me, they are handling asynchronously and they have pretty much all the data they need to do whatever it is they do and, and I know they're kind of caching some of that on the backend as well so we don't have to meet making calls.

[00:47:14] **Tim:** So I just trying to flip that around that, that's sort of a different way to handle the problem. But that does put a lot on the API consumer being savvy enough to do that.

## [00:47:25] Prefetching

[00:47:25] **Ben:** Well, I think that's, I've, I've heard that technique used for search results where when someone loads a page of search results. The browser will, you know, through the client side, JavaScript will immediately make the request for the next page results, so that by the time the person goes to hit next, it's basically the data's already been loaded.

[00:47:47] **Adam:** Yeah, I mean, you know what's coming, in felt, there's a, a way where you like, I think it's on by default, but like as your mouse is moving toward a link on the page, if.

[00:48:00] **Ben:** right, right, right.

[00:48:01] **Adam:** If, that link would take you to like another screen in the application, it preloads the JavaScript and the data that it needs in order to render that so that if you do click on that link, it will immediately load it with the data it already has on hand.

[00:48:15] **Adam:** Or at least, at the very least, you know, you're, you're already in the middle of requesting it by the time that click comes.

[00:48:21] **Ben:** Well, the crazy thing too is I, I'll hear people talk about how these things are implemented, and they'll say things that I would never even think of. They'll say, well. That, that prefetching of the content. It turns out that if you do it on mouse down and not click, that most people take somewhere between 100 and 200 milliseconds to actually perform the full click.

[00:48:42] **Ben:** So it gives you, you know, another 100, 200 milliseconds to preload the data. I'm just like,

[00:48:47] **Tim:** Yeah, I'm

[00:48:48] **Ben:** so there's people who are just thinking on a different level. That's awesome.

[00:48:51] **Tim:** they're thinking on a different scale 'cause they have to Right.

[00:48:55] **Ben:** Oh,

[00:48:55] **Adam:** it's great when that sort of stuff gets built into your tools. So I don't even have to think about it. It's just built into felt. It's

[00:49:00] **Ben:** so just talk about thinking on a different scale. This is, I was listening, I don't know if it was, it was

[00:49:07] **Adam:** Somebody else's podcast.

[00:49:08] **Ben:** lab, something like that. And talking about asynchronous.

## [00:49:12] Asynchronous Energy Use

[00:49:13] **Ben:** This is, this is fascinating. this was Google Gemini, I think they were talking about, and

[00:49:16] **Adam:** Oh, damn it.

[00:49:18] **Ben:** what?

[00:49:19] **Adam:** We made it this, we made

[00:49:20] **Tim:** ai.

[00:49:20] **Adam:** 50 minutes into the show

[00:49:21] **Ben:** no, no, no. It's, it's, this is not about the AI itself though. I, I'll just say that they have what I think a lot of other products have this sort of deep research will to go off and do like, you know, 10, 20, 30 minutes of research and then give you a response.

[00:49:37] **Adam:** Mm-hmm.

[00:49:37] **Ben:** But apparently you can opt in to having them run that later in the day, like late at night, and they'll charge you less money for it.

[00:49:45] **Ben:** Like, they'll charge you fewer tokens or something because electricity is cheaper at night. So, I mean, just a fascinating use of an asynchronous workflow. If you're willing to put up with the latency, we'll cut you a deal because, you know, talk about way, way downstream, the cost of electricity is cheaper at 2:00 AM than it is at, 11:00 AM.

[00:50:05] **Adam:** yeah, I mean the, this is very extreme and I don't know anybody that does this personally, but I know of people who capitalize on that same thing. The fact that electricity is cheaper at night. They, use their house as like a thermal battery, right? So they overnight, they program their thermostat to take the house down to like 60 degrees or, or 55 degrees cool it for the day, and then they don't run their AC all day long, right?

[00:50:29] **Adam:** And so it just gets slowly hotter all day. And at the end of the day, maybe it's 80 degrees inside or whatever, but, yeah. So they're, they're,

[00:50:36] **Tim:** We, we actually do that. So we have, our house was owned by a guy who owned a, a, a stone and tile company. So everything is covered in marble and granite and tile. so it holds, it holds heat and cold, actually extremely well. So at night we just crank that thing down as fast as it'll go to low as it will go.

[00:50:55] **Tim:** You gotta wear a quilt while you're sleeping and it's outside, outside. It's 92 degrees inside, it's like 61. Okay.

[00:51:03] **Ben:** That's awesome.

[00:51:05] **Tim:** And then you just turn it, you just turn it up, right? And, and then during the day that, that cool, that, you know, it's, it takes longer for it to heat up.

[00:51:12] **Adam:** Mm-hmm.

[00:51:13] **Tim:** like you're storing the cold

[00:51:15] **Ben:** Well, I was

[00:51:16] **Tim:** seem to work as well with the heat though, I, I guess we're not as well insulated as we should be, but yeah, the heat doesn't, the winter time, it doesn't seem to hold heat very well.

[00:51:26] **Ben:** I was listening to another podcast,

[00:51:29] **Adam:** Of course you were.

[00:51:30] **Ben:** I think this was the, reckless podcast, which I think has now become the ABOARD podcast. I, I don't know if they were making it joke or if they were referring to something that there was a town somewhere where people were spending so much money doing crypto mining, that it was, it was pulling so much electricity off the grid that it became more tenable for the town to just pay these people to not do bitcoin mining.

[00:51:57] **Ben:** So that they could, that they would take less electricity. It somehow worked out better for the town. I don't know if this is a true story or, or again, like if someone was just making a joke, but I thought it was pretty funny.

[00:52:07] **Adam:** That sounds apocryphal, but that would be hilarious if it was true.

[00:52:11] **Tim:** Yeah, I think that they would just cut off their electricity.

[00:52:14] **Ben:** Oh man. Tabs.

[00:52:17] **Tim:** Well, that's all I have to say about that.

[00:52:19] **Adam:** Well, so before we, before we wrap it up, I just want to kind of circle back. Can you guys think of any other possible solutions to this, like kind of scaling your API problem, right? So you've got like traditional response and maybe that becomes a problem. We've, we talked a little bit about web hooks. I, I would wonder, so back in the day, I'm, I'm making myself sound really old here, but, J-S-O-N-P, are you familiar guys?

[00:52:43] **Adam:** Are you guys familiar with this? Yeah. So JSON p was like a solution to the CORS problem, right? You can't from ben nadel.com, you can't make an API request to, you know, AdamTuttle.codes, right?because of cross origin resource issues. and so JP was a way around that basically you'd make that same API request, but then you just add like, JP equals and then some function name on the end of the URL.

[00:53:10] **Adam:** And it, the response, it kind of formatted it as a script that you would embed in your page and it would just, okay, here's the data you requested, and it would pass it as an argument to the function that you named. So then you just have to have some global function on the page that's waiting for that response and it handles that data.

[00:53:26] **Adam:** Right. And I wonder if there's a, a similar approach to be had, but like instead of JP, because that was to solve CORS. And we're not talking about CORS, but like I wonder if there's a similar approach to be had for like webhooks or some other mechanism for, returning API results.

[00:53:45] **Ben:** I mean we've, I wouldn't say that I've used this to return the results per se, more about letting people know that something happened, but we'll use web sockets. Where we emit an event on the server to a web socket system, and then the web socket system goes and tells a whole bunch of other connected people that that happened.you know, but it could just be the one person who did the thing is the person is the browser that's sitting there listening for that event.

[00:54:14] **Adam:** Yeah. I mean the, the 99.99% users of our API, it's coming from external systems, right? So we're, I'm not talking about API requests made from a single page app to, to get data for the app. It's more external systems integrating with us to get data or send us data sort of thing. But I, I kind of hear what you're saying.

[00:54:36] **Ben:** Here's something that I, I have to admit that I've never really understood. So I, I, at a very high level, I understand HTTP is a protocol that we use to make requests from one server to another. For most of my life, it was like HT P 1.0 and then 1.1 or something, and then HTP two came out and it was some sort of multiplexing request and response in the same connection.

[00:55:04] **Ben:** And I think we have a HTTP three now, and I don't even quite understand what that is. but maybe this is because I'm a cold fusion person, and cold fusion is typically sitting behind something else like an NGINX or an IIS or an Apache. I, I don't quite understand how these complex multiplexing keep alive connections interact in a cold fusion world.

[00:55:33] **Ben:** Like I don't even know if that works in a cold fusion world or if that's more like a closer to the metal. Like I have a Golang server or a, a node server where Node is itself, the web server. never understood it.

[00:55:47] **Adam:** I mean, you've got your ear to the ground. Well, my understanding is http three is just starting to see its first like broad ish, implementations. I think it's in like a new.net, thing as of like June. So just like a month to a month and a half ago.

[00:56:04] **Ben:** Oh, wow. I must have just heard it in passing

[00:56:06] **Tim:** clued in, buddy

[00:56:08] **Adam:** Something you heard on, on a one of a million other podcasts.

[00:56:11] **Ben:** but, but you talked about how Node can easily handle like 10,000 concurrent requests. And it's not because Node is doing 10,000 concurrent processings, it's because some handful of those are actually getting, well, it's like one per core is actually getting processed at a time and then, and then it's kind of, scissoring, not, scissoring is not the right word.

[00:56:34] **Ben:** It's like, it's like zippering back and

[00:56:35] **Adam:** not that kind of podcast spend.

[00:56:38] **Ben:** Like it's ping ponging back and forth between all these queued up requests, you know, allocating some, some processing time. but I don't know how that translates to a world where you have a, an application server behind a web server. Like is, I don't know. I just don't, I just, I don't have network chops to even begin to understand the implications of something like this. You know, because, like, 'cause, 'cause I, IS could maybe own or have 10,000 requests open, but that doesn't necessarily mean that it's passing those 10,000 requests directly to the underlying site. I don't know. I don't know. Anyway,

[00:57:18] **Ben:** Yeah. we'll have,

[00:57:19] **Adam:** so well to, to, to, to riff on that just a little bit. I mean, that. That, async io, right? Just like,do you call that two words or We'll, we'll call that, that one phrase. that is, that was like the thesis of Node, right? It's like you can write JavaScript in any environment and it's the, the thing it excels at is async io.

[00:57:39] **Adam:** So if you wanna go talk to a database or read a file or hit an API make a make a FTP request, whatever.it excels at being able to do a lot of that efficiently. So, I think it would be well suited for a use case like this.

## [00:57:53] Patreon

[00:57:53] **Adam:** Alright, I think we've said all we have to say, so this is the part where I say this episode working code is brought to you by the Circle of Hell designated for internet double clickers.

[00:58:03] **Tim:** Burn.

[00:58:04] **Adam:** like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:58:17] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:58:21] Thanks For Listening!

[00:58:21] **Adam:** we're gonna go record the after show. and my only tease for the after show tonight is that I am going to whinge about PCI. It is a tech thing. I'm gonna, I'm gonna complain, as I do, so that if, if you, that's the sort of thing that interests you, you wanna hear me complain about tech stuff, then you gotta become a patron of the show so that you can get the after show, get early access to new episodes, and you get some special access in our discord.

[00:58:48] **Adam:** so

[00:58:48] **Tim:** stuff too.

[00:58:49] **Adam:** yeah. Hey, So, if you want access to that stuff and more, you can go to patreon.com/workingCodePod, become a patron of the show. We'd love to have you.and I mentioned our Discord, so I'll just throw this out there as well. If you wanna join our Discord, it's free and open to the public. you can go to workingcode.dev/discord Alright, that's gonna do it for us this week. We'll catch you next week and until then,

[00:59:12] **Tim:** Hey, look, asynchronously, synchronously. Doesn't matter. Regardless, your heart matters.
