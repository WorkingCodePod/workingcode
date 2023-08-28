---
title: "115: Self-Care For Developers"
description: "We thought it would be nice to reflect on how we've all changed during the pandemic; and, share the little things that we do in order to keep our wits about us."
date: 2023-02-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/115-self-care-for-developers/id1544142288?i=1000601089781"></iframe>

After drinking close to 12 Mountain Dews in a single day, Adam started to wonder if — just maybe — he was using caffeine as a way to self-medicate. Upon discussing this with his doctor, Adam was diagnosed with ADHD (Attention-Deficit / Hyperactivity Disorder) - a condition _very common_ in the world of programming (a fact that we inspect on the show). In light of these findings, we thought it would be nice to reflect on how we've all changed during the pandemic; and, share the little things that we do in order to keep our wits about us.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/115-self-care-for-developers.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** How often do you have trouble listening to someone even when they're speaking directly to you, like your mind is somewhere else?

[00:00:06] **Ben:** I think I'm

[00:00:07] **Ben:** I'm usually

[00:00:08] **Tim:** what'd you say?

## [00:00:29] Intro

[00:00:29] **Adam:** okay, here we go. It is show number one 15, and on today's show we're gonna talk about self-care, uh, when you're working in the tech industry. And, I think we have a few interesting things to say about that. But, as usual, first we'll start with our triumphs and fails. And Tim, why don't you go first?

## [00:00:47] Tim's Failure

[00:00:47] **Tim:** well, you know, I have a really good run of triumphs lately, so I think it's only fair, you know, just so I don't make you guys look bad,

[00:00:55] **Adam:** of Averages, right?

[00:00:57] **Tim:** uh,that I'm going with a fail. so my fail this week is that I just cannot grok AWS lamb. I've tried, I spent a significant portion of the day yesterday trying to figure out how to do a specific, I can do the hello world examples and all those kind of simple things.

[00:01:15] **Tim:** That's, that's not a problem. and it's spent a lot of time today. So my use case that I'm trying to do is we have a really old FTP server. We're trying to get rid of it and we don't really want to do it ourselves cause we don't like opening those ports up to the world and things like that. So, Amazon, has something called AWS Transfer Family,

[00:01:37] **Ben:** Transfer family.

[00:01:38] **Tim:** transfer family.

[00:01:39] **Tim:** It, it is not Witness protection program where they transfer you to a, to a little Illinois town and hide your name. it is basically, they call it a, you know, a, it's a hosted FTP provider. And so I. Initially went through, did the sftp, got that figured out. I mean, the hardest thing with, I find with AWS is figuring out the roles and the I am permissions.

[00:02:03] **Tim:** But once I got past that for this stuff, I was very easily able to set up a SFTP server. but it doesn't use just a basic username and password. It, you have to send a, a public key. And I know that this is, I'm, I'm setting this up for some of our customers so they can go grab automated reports, basically some spreadsheets and c CSV files.

[00:02:22] **Tim:** And I know that some of them, they're just so far behind the curve that there's no way they're gonna be able to, you know, you know, understand how to use a public key and pass that in and grab it. and so there is an option for FTPs s which is basically you're using your SSL certifi. To do the encryption.

[00:02:43] **Tim:** It's just basic. It's just ftp, normal ftp, but it's encrypted using the, the certificate. But to do that, you have to use, either, you have to set up a, a active directory server on, AWS or you can use a custom identity service. And one of them is using a Lambda. And the Lambda seem like the least expensive because, you know, Lambdas only charge you when they run.

[00:03:08] **Tim:** But spending the whole day trying to figure out sample scripts, tutorials, I just like, I could not figure it out at all. And so I just gave up and said my, my final solution was if a customer can't figure out how to use a public key to do S F T P, then my answer to them is, you set up your own FTP server and I will send you the file.

[00:03:29] **Ben:** Yeah. It's like the easier way to do it.

[00:03:32] **Tim:** But I felt stupid

[00:03:35] **Adam:** the, there's, there's a bunch of different things, right? You could, you guys could have a shared S3 bucket that you both have separate keys for, and you could write the file in, they could read it out, and there's a bunch of

[00:03:45] **Tim:** Trust me. If they can't figure out ftp, they're not gonna figure out S3.

[00:03:49] **Ben:** well, a a lot of FTP clients have S3, support,

[00:03:55] **Tim:** Yeah.

[00:03:55] **Ben:** you can,

[00:03:56] **Adam:** it or are they just

[00:03:57] **Tim:** They're automating it. So that's, that's the thing, right? So they're gonna have to have someone go in and change their code. They're not grabbing, I mean, they're not grabbing like, you know, wins, s e p and Down or Cyber Duck or like that and doing that. I mean, that's pretty straightforward. They're, they're automatic, automatically comes down.

[00:04:14] **Tim:** I just know they're, and I know because we've run into this before, they're like, huh, we don't know how to do this. And

[00:04:19] **Adam:** yeah. Oh my God. I have a client, I don't wanna name names, but one of our customers, They're, they use Oracle as their , they use Nope, that's not it. They're not, they're not actually one of our customers for, for this product that I'm talking about. they use Oracle as their primary database for their, their stuff.

[00:04:37] **Adam:** And the guy, like they have a really small, it's a small school, they have a very small IT department and the guy who works on the integrations with us just doesn't really know anything other than the database. So, you know, we're like, okay, you know, hit the API and we'll generate a file and then you can download the file, and, and import that into your database.

[00:04:58] **Adam:** Cuz that's, that's the easy version of the, you know, like at first we were hit the API and we'll send you back the j s o data of, of what you're interested in. And he's like, how do I do that from Oracle

[00:05:08] **Tim:** The only thing he is is Oracle.

[00:05:11] **Adam:** And, and so what we came up with was like, okay, we'll we'll give you a url. You hit that.

[00:05:17] **Adam:** Well actually I think what we're doing now is, We just run it daily and like it's, it's a batch export and we write a new file to S3 for him every day.

[00:05:25] **Tim:** Mm-hmm.

[00:05:25] **Adam:** he's got a job on Oracle that will connect to S3 and download the data and import it into their database or whatever. And it's just like, this is why we can't have nice

[00:05:34] **Tim:** Mm-hmm. , have you told about our Lord and Savior PostgresSQL.

[00:05:38] **Adam:** so yeah. No, I feel your pain. I feel your pain.

[00:05:45] **Tim:** But I mean, in good news, I kind of follow up on something I talked about in previous episode. you know, I was talking about the, my SMS work, workaround that I was working on where, I was getting blocked by, prohibited by ca like 40. 7% of like a thousand SMS decisions were getting stopped for prohibited by carrier.

[00:06:05] **Tim:** So finally got everything worked around and today I was checking the numbers and it's like, so I sent over 1200 SMS from one client all in one big burst. and then I repeatedly went through the ones that got blocked. It was like 70 something got blocked. And then by the end of the day, once I got 'em all sounded like five got blocked, and that's an acceptable number.

[00:06:26] **Tim:** So very happy that my little, my little cheat code worked out. So

[00:06:30] **Adam:** to spreading it around a couple of different phone numbers.

[00:06:33] **Tim:** yeah, about 15 phone numbers. Yeah, so

[00:06:36] **Ben:** we had a complaint actually just this morning from Twilio that, someone was using our two-factor authentication workflow to spam phone numbers. So, so like you would go in, I think they would be, they were signing up for an account, and then as part of the setup process, they had to set up to a, to a factor authentication.

[00:06:55] **Ben:** And you can put in, you know, any phone number and then they send you a confirmation code, then you verify that it's your phone number. And this one user was just put in like all kinds of people's phone

[00:07:05] **Ben:** numbers. Which, which like, I don't, yeah. because all it does is send them a six digit code. You're like, what's the point?

[00:07:13] **Ben:** Is it, is it literally just malicious? Like, it's not even like you're trying to take advantage of somebody, you're just trying to spend our Twilio money or something. And

[00:07:21] **Adam:** well, yeah, I was gonna say maybe they're, maybe they have a grudge against you guys and it's trying to just burn through your Twilio budget.

[00:07:27] **Ben:** it's such a, and, and, and like the volume wasn't high enough where it was some bot that was doing it, or maybe it was a bot, but it wasn't like, it was like a couple of thousand messages, but it wasn't like hundreds of thousands of messages or something. I don't know. People are just, they're just, ah, the worst.

[00:07:46] **Tim:** Whenever I wanted a good laugh, I'd go through my logs and look through cuz this is an automated message that we're sending. Basically we're saying, Hey, your policy's about to, your insurance, policy's about to cancel, make a payment. And they will like write back like they think a human being actually sent them and be like, they'd be like, Hey, so, I lost my job on Thursday and I don't get paid.

[00:08:08] **Tim:** I'm a new one. I mean, they're writing a whole book about their life. I'm like, seriously, you really think someone's gonna reply to this?

[00:08:16] **Ben:** Oh man.

[00:08:18] **Tim:** I need to, I need

[00:08:18] **Tim:** to hook up chat G b T to it and just have a, a whole conversation with them.

[00:08:24] **Ben:** go back to the Lambda stuff for a second and, and feeling dumb about it. I, I don't know anything about Lambda, but I was in a call the other day at work and one of the guys on the call very, very bright guy. He's part. Kind of the platform team where he is kinda like an honorary member, the platform team, he does a lot of foundational work on our systems.

[00:08:45] **Ben:** And, someone asked him like, oh, what kind of stuff should I put in Lambda? And he was just flat out nothing. Don't put anything in Lambda. He's like, you'll regret it eventually. Just build a service that we can manage. And I don't know what that is based on other than he's a Yeah, he's a very bright guy and he's very typically very measured in his responses.

[00:09:06] **Ben:** So when he says something like that, I sort of stand up and, and listen.

[00:09:10] **Tim:** Yeah. I mean, then on the other hand, Brian Kloss, who we had on the show, you know, who's an aw w s genius, he, he's all about that. He's like, yeah, I'll just code it in Lambda. You know, you only get charged when it runs. So,

[00:09:21] **Adam:** We have dozens of Lambdas and I love them.

[00:09:24] **Tim:** in what? Aw. W s.

[00:09:26] **Adam:** Yeah.

[00:09:26] **Tim:** See, Adam can figure out. Now I really feel stupid

[00:09:30] **Adam:** Hey, what are you trying to say here?

[00:09:32] **Tim:** Oh, nothing. Nothing, nothing. Sorry.

[00:09:34] **Ben:** Oh.

[00:09:35] **Tim:** Well, that's me, Ben, how about you? After I insulted

[00:09:37] **Adam:** I was gonna, I was gonna offer to help you, but now not anymore, man.

## [00:09:43] Ben's Triumph

[00:09:43] **Ben:** I'm gonna go with a triumph and it's, it's still, it's something particularly special. But, I've spent the week scanning our S3 bucket looking for objects that shouldn't be there. as, as I've mentioned, I think in previous episodes, we've had a large cost cutting initiative happening at work, trying to find e c two instances that we can spin down test databases that no one's using anymore.

[00:10:04] **Ben:** All this, all these things that, you know, for better or worse, at one point when you're a venture-backed company, people just stop caring about where they're throwing money sometimes and they're just like, grow, grow, grow, grow. That's all we care about.

[00:10:17] **Adam:** did you meet the Avengers?

[00:10:20] **Ben:** wait, what?

[00:10:21] **Adam:** The Avengers backed your company.

[00:10:28] **Ben:** So, I've been tasked with looking through our S3 bucket and, and scanning it, trying to find, objects that don't have corresponding records in our database since pretty much every object that lives in our S3 buckets is referenced by some sort of database record. but it's, it's an interesting thing because what I wanna do is find objects that shouldn't be there.

[00:10:47] **Ben:** So I can't start at the database and say, Hey, show me all the things that shouldn't be there, because the database has no record of those. So I have to literally go key by key and say, what format is this key in? And figure out what type of entity it corresponds to in the database. And then parse out maybe like the database identifier or else, however else we're doing the COR correlation, and then go to the database and look for that thing.

[00:11:12] **Ben:** And if it's not supposed to be there, I need to, I'm logging it right now. I'm not actually deleting anything. But, I dunno. It's just been a lot of fun.

[00:11:19] **Adam:** It sounds like an interesting challenge, and I can't help but throw, an idea at you

[00:11:25] **Ben:** Yeah, please.

[00:11:26] **Adam:** you, so I think you could potentially go the other direction. I think you could start at the database and say, like, it, it entirely depends on how you use your data to generate the S3 key name

[00:11:37] **Ben:** let, let's say, there's a lot of primary keys that map to objects.

[00:11:40] **Adam:** Sure.

[00:11:40] **Adam:** But like, you know, if, if you, if you've, if it's just the primary key, but then there's like, depending on what table it in, it might, it might be in other buckets or whatever. but in theory, if you could look at the database and know, okay, this file should exist, then you could take, you know, that's just a string.

[00:11:56] **Adam:** And so you could generate a list of all of those strings and throw them into a Redis set. Right.

[00:12:04] **Ben:** Hmm.

[00:12:04] **Adam:** And then you can do the same thing on S3, get a list of all the keys and throw them into a Redis set.

[00:12:10] **Ben:** Well, it's getting the list of all the keys is, is. Part of the challenge, just cuz there's, we have, so we have like, like four petabytes of data, which that's a number so big. I don't even understand what it means. It's just all smoke and mirrors to me.

[00:12:26] **Adam:** yeah.

[00:12:27] **Ben:** But yeah, so, so part of the problem is that, I, I, I look at S3 like it's a directory structure because you can format it like it's a directory structure.

[00:12:37] **Ben:** It's like all objects of this type have this same key prefix and all objects of this type have this same key prefix. And it looks like you're drilling down through directories. But my understanding is that's all just a facade. It's just a giant key value pair where the key is the entire path to the object you're trying to reference.

[00:12:54] **Ben:** And they just, they, you know, make it look like you actually have directories. So to scan essentially the, the listing of objects, you tell Amazon, start with this key prefix and then give me the next thousand keys. And you can't. I don't have a good idea of how that could be parallelized because every worker essentially needs to pick up where the last worker left off.

[00:13:21] **Ben:** So if you have anything running in parallel, it's like chaos trying to figure out where you should pick up next. So

[00:13:27] **Adam:** Yeah, you would ha, you would wanna break it down into partitions. Right? So like each folder, you know, it would sort of just be its own process. And that process would be responsible for

[00:13:37] **Ben:** yeah, so that's,

[00:13:38] **Adam:** data. Yeah,

[00:13:39] **Ben:** that's more or less how I have it. I have, a bunch of key prefixes that roughly map to different database tables, roughly, cuz like, you know, it's a 10 year old application. Every table's slightly different logic. and I can run those in parallel, but they're all running, essentially single-threaded, looking at the, at the, at the keys in order. But there's, I mean, I have, we have hundreds of millions of records that we need to validate, or I should say we have hundreds of millions of objects in, I think we do, we have a trillion objects. I dunno. We have like some, like, again, just like a stupid amount of data just sitting there. And I'm sure that a lot of it can be deleted.

[00:14:18] **Ben:** So now it's just trying to narrow it down.

[00:14:20] **Adam:** So, as a cautionary tale, if your company is, walking down the same path that Invision did, you need to set up a, a automatic cleanup policy. Like if it, it doesn't get its timestamp updated within, you know, a year, then it gets deleted or something. Or you move it to, to, glacier or something. Or at least it costs.

[00:14:40] **Ben:** Yeah. It's, I mean, and that's, that is, that's like such an ongoing discussion at work because the idea of this tiered pricing storage gets so fuzzy when all of a sudden you could have a user that hasn't logged in in seven years. and then they could just log in and start looking at their stuff and we'd either have to lock them out and then maybe they'd have to go through an unlocking period where like, okay, I need to get back into my account.

[00:15:08] **Ben:** Okay, we need up to 12 hours to unlock your account so that everything comes out of glacier. Cuz I think Glacier is like four to eight hours of, of recent restoration time, something like that. So it's, it's one of those, it's like you wanna be able to snap your fingers and just make it happen. But so many of these things become both an engineering and a product question.

[00:15:28] **Ben:** And, and that usually, that's usually a dead end for us cuz for for whatever reason, solutions that require two departments almost never happen.

[00:15:37] **Adam:** yeah. It's easier to just keep throwing money into the fire.

[00:15:40] **Tim:** You can't confirm

[00:15:42] **Ben:** So anyway, that's just been a lot of fun. It, it just, it's been a nice, almost like a mental break cuz it's a very different type of work than I've been doing lately. So I've been having a lot of fun.

[00:15:52] **Adam:** Well, before you pass the mic, I wanted to ask you here, it's been several weeks since we've talked about your, final project on the legacy platform. I think the last time we talked about it, you were saying that,

[00:16:03] **Ben:** So this is the final, final project, apparently uh,final v2. PSD

[00:16:11] **Adam:** I was gonna say, you know, you, you said that was, you were gonna miss your deadline by a couple of days, which was a good thing because you had estimated it a lot farther than you,

[00:16:19] **Ben:** yeah. Six weeks out.

[00:16:21] **Adam:** do. so I just wanted to check in, like, what, what's going on?

[00:16:24] **Ben:** yeah, I appreciate the check-in. so that is kind of a, in a holding pattern right now because the, the technical parts are done and now it, it's more of a process and legal question about, because it's about data deletions. So it's, it's, are there any policies that we're, we need to adhere to? Are there communications that need to be sent out?

[00:16:44] **Ben:** What expectations are there from the customer? And that stuff just takes a long time.

[00:16:50] **Adam:** Is that because the legacy platform is actually being shuttered or, are they just separate efforts?

[00:16:56] **Ben:** It's, I don't even know if I could answer. I mean, I don't even know why. I thought we, we basically had the go ahead for all this. I think there's just so many people working on so many different things that, that they all just like, it. It's like whack-a-mole with information. You try to get information, someone gives you a little bit of information and they pop down and go back to their old stuff and you gotta get more information.

[00:17:18] **Ben:** And it's, it's, I, I don't know. It's, we're, you know, after our, reduction in force, I keep to say that cause it sounds so much more diplomatic. we just, we have not enough people doing way too much stuff and so it's, it's a little bit hard to keep everybody above.

[00:17:35] **Adam:** gotcha.

[00:17:36] **Ben:** So, yeah, so the S3 scanning now is, is become my main focus.

[00:17:40] **Ben:** Then I'll go back to the data deletion stuff afterwards.

[00:17:44] **Adam:** Is it the S3 scanning also for data

[00:17:46] **Ben:** It's also data deletion. Yeah, yeah, yeah, yeah. I guess

[00:17:49] **Tim:** doing reconnaissance now, you'll, you'll take your your troop action once you got the reconnaissance done.

[00:17:54] **Ben:** yeah, yeah, yeah. Exactly. Exactly. All right. So that's me.

[00:17:58] **Adam:** this is the final, final thing. So after that, you'll be doing something on the new platform,

[00:18:03] **Ben:** That's what, that's what people tell me. That's what people tell me. I've been invited to a couple of, standups on other teams, you know, chumming the water, getting, uh, it's so interesting, right? So, sorry, if I could just side quest for a second. I have talked, many, many episodes ago. I have very strong feelings about what I think a pull request life cycle should be.

[00:18:25] **Ben:** I think pool requests should be created and then, closed out in a very, very quick succession. on, on my team, the Rainbow team, which is basically just me now. And, and basically one other honorary guy who's kind enough to stick around and do my pool reviews.

[00:18:40] **Ben:** My pool

[00:18:40] **Tim:** one and a half

[00:18:41] **Ben:** Yeah.Yeah.we, when we have a pull request ready to go, we pop in a slack and we adhere the channel.

[00:18:49] **Ben:** Like there's no sense of this is the guy doing pull requests this week. Everybody is on pull request duty all the time. and I've been now added to a couple of other team channels and that's not how they do it. And, uh, I feel like that's gonna be a problem.

[00:19:06] **Adam:** We have a culture difference.

[00:19:08] **Ben:** that's gonna be like, of all the adjustments that's gonna, I think be the, the toughest adjustment is that, that cadence of I'm done with my coat, get into production. Go, go, go, go.

[00:19:18] **Adam:** Yeah.

[00:19:19] **Ben:** We'll see. Maybe they're doing that, but it's more behind the scenes instead of publicly in the team channel.

[00:19:24] **Adam:** Gotcha.

[00:19:26] **Ben:** So, okay, that's me.

[00:19:28] **Ben:** Triumph

[00:19:29] **Adam:** officially over

[00:19:30] **Ben:** Officially. Officially End of Triumph, and I'm passing it over to Adam. How are you doing buddy?

[00:19:35] **Adam:** Triumph. Final. Final v2.

[00:19:39] **Tim:** Hey.

## [00:19:42] Adam's Triumph

[00:19:42] **Adam:** All right. So I also am going with the triumph this week. I'm gonna say it's a triumph, I guess. Through, it's, so it kind of happened to me a little bit, and then I saw it happening and I just decided to pile on, right? So through that set of circumstances, I ended up having several doctor's appointments This week I have more, we're recording on Thursday.

[00:20:01] **Adam:** I have another one tomorrow. and some of those doctor appointments were resulted in referrals to yet more doctors who, I won't say this week, but, you know, whatever. and so actually, you know, this is another one of our great for radio moments, but, my co-host will notice that I am not drinking a Mountain Dew

[00:20:15] **Ben:** What is that? A, is that a Pepsi Clear

[00:20:19] **Adam:** I remember I missed Pepsi Clear. That was such a good beverage. I was so mad when they got

[00:20:24] **Tim:** Is that a zma?

[00:20:27] **Adam:** this is, this is the main ingredient in, in Mountain Dew.

[00:20:31] **Tim:** Yeah. Oh.

[00:20:33] **Tim:** Dih Dihydrate.

[00:20:36] **Adam:** dihydro, dihydrogen monoxide.

[00:20:39] **Tim:** There you go.

[00:20:40] **Adam:** yes. so, where do I wanna start? So, the, I, I, I mentioned the, the water thing.

[00:20:44] **Adam:** I have long battled my addiction with caffeine and with Mountain Dew. and I, I've known for a long time. When I say a long time, I guess what I really mean is like five-ish years that I have h d it was never diagnosed. It was just sort of like, you know, it became obvious to me once I learned by having two kids with h d and having to go through their diagnosing process.

[00:21:09] **Adam:** it became obvious to me that I have h d as well and have for my entire life. And, and then a lot of things started to like click into place, right? Like using the caffeine to control my ADHD so that I can focus, so that I can deal with stress, that sort of thing. and so I've had this contentious relationship with it for a very long time, and, There was a day not long ago where, I drank most of a 12 pack of Mountain Dews in one day, like 10 in a single day.

[00:21:36] **Adam:** and like I've always known, okay, a lot is a lot and, and don't push it too far, but that was sort of a like, holy crap. you know, I didn't feel too bad about it when, when I was having like six in a day when a 12 pack lasts me two days. Like, okay, that's, you know, that's a lot, but it's not like crazy.

[00:21:53] **Adam:** And when I drank almost an entire 12 pack in one day, I was like, okay, this is getting out of hand. and so I decided at that point, like, okay, I need to do something about this. And then like the next day I was like, wait a minute. You know, I, the reason, I'm sure there's, there's a, a habitual and addiction related reason, component as well, but the underlying reason is I'm using this to deal with, chemical imbalance in my brain.

[00:22:15] **Adam:** And so let me talk to my doctor about my ADHD and see if I can get medication to. Treat my ADHD or, you know, whatever it's gonna be. If I can treat my h d in whatever way makes sense, then maybe it'll become easier for me to kick the habit of drinking way too much soda. So I did, I talked to her about that.

[00:22:35] **Adam:** and when I told her, that I almost drank an entire 12 pack of Mountain Dew in one day, she just about fell out of her chair, Um, and I was like, do you need cpr, ? the, yeah. So she, she instantly agreed like, okay, that's definitely too much. That's like dangerous levels, of caffeine, let alone you, I mean, I drink diet so there's no sugar, but still like, I'm sure that there's all kinds of other negative effects when you're drinking at that scale.

[00:23:04] **Adam:** it's a problem of scale now. and so, you know, we did the questionnaire. It's clear that I have adhd. I wasn't surprised about that. and we, we did tried a couple, or we discussed a couple of different options and, and, she put me on a medication, which I took the first one this morning. and so I've been trying to cut back today, just see how it goes, right?

[00:23:21] **Adam:** Like I'm, I'm trying to drink it because I feel like I need it, not because of the habit or, you know, that sort of thing. and I, I don't have a, a. I didn't think to, to track it until like three quarters of the way through the day. So I don't have the exact number, but I would guess that I've got about four in me today,

[00:23:39] **Ben:** All right. Significant depletion.

[00:23:42] **Adam:** I'll, I will admit I have one on my desk. It's not open here. It's a, you know,

[00:23:46] **Tim:** This is, they're taunting you. It's taunting you.

[00:23:48] **Adam:** Yeah. but, you know, it's just, it's just there in case I needed to get through the podcast and talking to you, dweebs, um, So, yeah, that, I've got that going on, right. So I saw my primary care doctor same day.

[00:24:01] **Adam:** I saw my gastroenterologist to follow up on a colonoscopy I had recently, for my I B D. I have my appointment tomorrow is with my rheumatologist. it just so happens that I have an appointment tomorrow, as like a regular checkup, but I also have an issue that I need to bring up with him while I'm.

[00:24:16] **Adam:** So I have an autoimmune disease. That's why I see him. And my last injection that I gave myself didn't really seem to help. So, I think that there's a possibility we're gonna be changing my drug, which could line up nicely. Like there's a, there's a couple of medications that my gastroenterologist would like, would've liked to try me on, but they wouldn't, it would be like two, different medications in the same category.

[00:24:38] **Adam:** You can't have two. and so, you know, I'm gonna kind of try to sort of bring those two teams together and see if we can kill two birds with one stone sort of thing. what else went going on this week? So I had, about, I think I mentioned last week or, or the week before that my eyes have been bothering me.

[00:24:52] **Adam:** and so I went out and did an eye exam and I do need glasses. it's like, Smallest possible prescription in both, categories, right? So they, they gave me a quarter diopter for focusing and a quarter of whatever they call it for a, an astigmatism, no cataracts or anything like that. But, and, and so I'm waiting for my glasses to come in and there was a point today that, I, I don't know what happened, but my screens started to get kind of fuzzy in the middle of the day today.

[00:25:21] **Adam:** So I turned my screen resolution down. I was like, you know, turning up the tech size and the browser is one thing, but, you know, then all of the, the chrome around the windows, everything, all, all the native stuff stays small, right? It's only turning up browser contents when you increase the font size.

[00:25:37] **Adam:** So I had to turn down my resolution, which was a little weird, but made it through and things are better now. I think it was just like a temporary thing. anyway, so I've got that going on. what else is on my list here? I think the only other thing is whatever

[00:25:49] **Tim:** Gosh, I talk to my grandparents. Geez,

[00:25:53] **Adam:** Yeah. And I'm only 40. God. Yeah. So, but yeah, you know, I, I'm also a heavy procrastinator, right? So, like I mentioned, I do these at-home injections for my autoimmune disease, right? And so, because I do at-home injections, I have sharps containers at home to put the needles in when I'm done with them.

[00:26:14] **Adam:** Well, I, I've kind of bounced around trying to find a medication that's gonna work for me for a long time that's also effective and whatever. And all of these different medications that you try, you know, it's like you can only get it through one company. So, and it's by mail. So they send you the thing and you get set up on their program and they're like, okay, we're gonna send you a sharps container to put your needles in.

[00:26:33] **Adam:** And then, you know, when you, when it's full, you know, you, we'll send you another one and you can send the, the full one back in the, the box that we ship your empty one in. That sounds great, except if you have to switch medications before it's full, then you, you don't get that opportunity. And everybody has a different size sharps container.

[00:26:53] **Adam:** And so now as a result of this, I have like six full sharps containers on the floor in my bathroom.

[00:26:59] **Tim:** Sounds like an OSHA violation.

[00:27:01] **Adam:** it does. and so I've been trying to figure out what I'm gonna do with that. I, I think the plan is I'm gonna call, my local fire department and be like, here's the situation. Somebody told me that I could call you and, and you might be able to help me out.

[00:27:13] **Adam:** Like if you can't take it off my hands, maybe you can tell me who can, sort of the situation.

[00:27:18] **Ben:** That's a good idea.

[00:27:19] **Adam:** that's been on my to-do list for like six months. And I just, you know, it's, it's not on fire, so I haven't been able to get to it yet. That's kind of the way my brain.

[00:27:28] **Ben:** Well, I have to say, well, two things. One, I very much had that same, how much water do you drink conversation? the very first gym I joined as an adult, I, I got a free fitness evaluation and we did like a little nutritional thing and, and I remember them asking how much water I drank, and I was like, well, I drank a lot of diet Coke.

[00:27:46] **Ben:** And they were like, yeah, okay. But like, how much other water do you drink? I drink a lot of Diet Coke, They were like, yeah, but like, when you're not drinking Diet Coke, what do you drink? I'm like, yeah, diet Coke. Pretty much in between the servings of Diet Coke. And he was not excited about that. but, but I, but I wanted to say that, I think the friction of talking to an individual on a phone in order to make an appointment is like far and away the biggest hurdle for me when it comes to keeping my physician related appointments in check.

[00:28:22] **Ben:** I, I almost wish I had a, like, like a Medical Pal or someone like, like when I was a kid, my mom just made all my appointments for me. She just told me when it was time to go, and I went and it wasn't so bad. The idea of having to talk to someone to schedule an appointment is so painful that I wish someone could just do that part for me and then I would stay on top of everything.

[00:28:41] **Adam:** Oh, I love, so there's certain things like when I get blood work regularly for different reasons or whatever, like you can make those appointments online. I love it.

[00:28:48] **Ben:** Oh, it's the best.

[00:28:49] **Adam:** occasional doctor will allow you to make appointments online or, I've had, I had a therapist in the past who would like to schedule over text.

[00:28:56] **Adam:** That was great too.

[00:28:57] **Ben:** Nice. one problem though is what I have discovered, even with the doctors who allow appointments to be made online, you go and you pick the doctor, and then you pick the time and, and it'd be like, oh, their first appointments in seven weeks. And then if you call up the office and ask for an appointment, they're like, oh yeah, how about this Friday?

[00:29:15] **Ben:** So there's, there's some like disconnect between what they have online and what they actually have available. And I don't know if that's a, a technology gap or if it's intentional to sort of space out and leave room for, for people who have maybe more urgent matters. I don't know.

[00:29:30] **Adam:** I gotta get these doctors on Calendly.

[00:29:34] **Tim:** So it sounds like, we almost have a topic here about like self-care

[00:29:37] **Adam:** Imagine that.

[00:29:39] **Tim:** huh?

[00:29:40] **Adam:** What a coincidence.

[00:29:41] **Tim:** What a coincidence.

## [00:29:43] Two Truths And A lie Deadline

[00:29:43] **Adam:** before we get into that, I guess a brief programming note. so last week we ended the episode with, a game of two truths and a lie. And one of the things that we neglected to mention as part of that was the deadline for when you need to get your answers in.

[00:29:56] **Adam:** and so we've decided, that you're gonna have to get your answers submitted by 7:00 PM US Eastern on February the 23rd, which is the day after this episode becomes available. Because we will be recording on the 23rd at 7:00 PM US Eastern . So we need your answers by then so that we can, figure out who won, declared our, champions of truth and send you your, what did I say, horsefly testicles or peppercorns?

[00:30:25] **Adam:** Peppercorns.

[00:30:26] **Tim:** off the, off the merch door.

[00:30:27] **Adam:** A fistful of mayonnaise

[00:30:31] **Ben:** That sounds

[00:30:32] **Tim:** That's a different, that's a different show.

[00:30:33] **Adam:** anyway, yeah, so get your, the, in the show notes. I'll make sure it ends up in the show notes for this episode as well. in the show notes for this, for this and the previous episode on our website, you know, find it somewhere. There's a, a link to the, it's a Google form where you could submit your, your answers and, get those in. We will declare a winner, I guess. Cool. So, self care for developers.

## [00:30:56] ADHD

[00:30:56] **Tim:** So I, I, I wanna ask this to you, Adam. it, it seems to me there is a disproportionate number of people with a D H D in, like the programming skills. I dunno why that is. You agree? Yeah. I, it seems like there's a lot, I mean, most, there's a lot of people at our, at our company, That, you know, are on ADHD medicines?

[00:31:20] **Tim:** Um,

[00:31:21] **Adam:** bet I can explain why, if that would be helpful.

[00:31:24] **Tim:** well, I I don't really care about the why right now. We can talk about that later. What, what I wanna know is, is so how did you, you talked about like, you discovered it when you were like diagnosed with your kids. What is it? Because sometimes I think maybe I am

[00:31:40] **Adam:** Sure. So, yeah, like when I was growing up, there was no such thing as adhd. We were just bad kids, right? Like, Our parents would get mad at us because we, we wouldn't focus on what they wanted us to focus on. they, you know, they called us like hyperactive sometimes. like, because if you, if you are fidgety and you can't stop moving, like my, one of my kids.

[00:32:04] **Adam:** so there's, there's two different types of adhd. There is, impulse control, and there is, oh, of course now that I'm on the spot, I can't think of it. Is it, so the impulse control and, and hyperactivity sort of go together, and then there's like, focus. So, I, I, I'm doing my best . I'm married to a therapist.

[00:32:21] **Tim:** I know a lot about this, but I'm not an expert. Sorry. I just want your

[00:32:24] **Adam:** yeah. Yeah. So. A lot of people think d h D means you can't focus on anything, which is close enough to get you wrong. But, but, but not, right. Right. So, people will say things like, my kid can sit and play video games for four hours, so he can't have d h and that is like the exact wrong thing.

[00:32:48] **Adam:** The, the thing about focus is, it has to be like ADHD people, adhd, P ADHD brains can focus only on things that are novel, interesting, urgent or important, right? and so if it's not one of those things, if it's not important to me or if it's not new and exciting, or if it's not on fire, then I, it just kind of gets automatically put on the back burner of my brain.

[00:33:13] **Adam:** And meanwhile, I've. Steam, you know, this, the winter sale is going on and, and I'm getting games that are on sale or whatever, right? Like, whatever, whatever is interesting to me in that moment, I'm gonna sit and I'm gonna focus on that. So, the, the, well, whatever, I'm trying not to answer the first question, question, which is why, so many people are drawn to this, but maybe, maybe they two go together.

[00:33:34] **Adam:** So, I think that there's a disproportionate number of people with ADHD who are drawn to

[00:33:38] **Tim:** So you only wanna answer this question because it's interesting to you, the the question I didn't ask.

[00:33:43] **Adam:** Well, well played, sir.

[00:33:45] **Tim:** Wow. Okay.

[00:33:46] **Adam:** It, it it is occupying a lot of my brain space right

[00:33:48] **Tim:** Okay. All right. Get that outta your system.

[00:33:50] **Adam:** Sure. the, I think that the, a disproportionate number of people are represented, with ADHD in the programming communities because, one of the characteristics is when something is interesting to you, Um, novel, exciting.

[00:34:06] **Adam:** Then you lock in on it. And like, who among us? I'm sure that there are some people, but I would say that if you went to any developer conference and asked, you know, raise your hand if you've ever forgotten to eat dinner because you were so wrapped up in a programming thing that you were working on a side project, a thing for work, whatever.

[00:34:24] **Adam:** And you know, you look up and all of a sudden six hours have gone by it, it's 1230 at night, you forgot to eat dinner, you have to go to the bathroom really bad. And it's all just because you were so excited about what you were working on. Right? Like, that is a classic sign of A D H D And I think that it's because the, the work is interesting and, and it, it meshes well with what ADHD brains are good at

[00:34:50] **Ben:** Hmm, I

[00:34:50] **Tim:** And if you're write bad code, things are constantly on fire. So,

[00:34:55] **Ben:** Well, and it's constantly novel too, because you're always coming up with better solutions to things and, and being able to rework or rethink the way things work. So it's, it's like there's always a next level, a next boss to beat, so to

[00:35:07] **Adam:** Absolutely. Yeah. So what was the, the question that I didn't answer?

[00:35:11] **Tim:** so how do you, what are the id? So if I were a person who was sitting and thinking, you know, do I have it? Maybe I have it. People, you know, my son the other day goes, I think you got undiagnosed A D H D . And I'm like, really? No one's ever told me that before. So, I mean, What do you look for? just maybe see, hey, maybe I need to go talk

[00:35:34] **Adam:** yeah, I, I'm sure it's easy to Google. There's a questionnaire and it's only like six or seven questions that you can ask yourself, and it's like, you know, how, how true is this statement about you on a scale from like never to constantly, right. and the questions on there are like, how much do you fidget, like with your hands or feet?

[00:35:50] **Adam:** Are you the type of person that just cannot stop, bouncing your foot on the floor or, or fidgeting with crap off of your desk in your hands? I have a, I have that to a small degree. or, are you a heavy procrastinator, right? Do you feel like you just can't stop procrastinating? That's what I was talking about.

[00:36:05] **Adam:** Like, you just can't focus on things because they're not urgent, right? Like, I, I struggled a lot with procrastination in school, because it wasn't urgent and it wasn't interesting, right? Like, who cares about reading Cser, not me, apparently. so yeah. the, so yeah, I would say if anybody thinks that they might have adhd, Google it.

[00:36:25] **Ben:** Google like an ADHD questionnaire, and, and you ask yourself the questions and based on, you know, you do your best to answer honestly. And based on where your answers fall, it'll tell you, you do or don't, show likelihood for it. And I would make sure you Google for the adult questionnaire. we do this right now,

[00:36:43] **Tim:** I'm, I'm looking at one right now.

[00:36:45] **Adam:** I'm gonna, okay. Well you've, you've got it up in front of you. You ask

[00:36:47] **Adam:** the questions and we'll All answer

[00:36:49] **Tim:** Yeah. All right. Let's see how long this is. It's pretty long, actually.

[00:36:54] **Tim:** Well,

[00:36:54] **Adam:** The one

[00:36:54] **Tim:** probably like twen 2020 questions.

[00:36:57] **Adam:** well,

[00:36:57] **Tim:** All right.

[00:36:58] **Ben:** Just we'll get a flavor, we'll get a flavor.

[00:37:00] **Tim:** how often do you have difficulty sustaining your attention while doing something for work school? A hobby or fun activity, eg. Remaining focused during lectures, lengthy reading or conversations? Never, rarely, sometimes, or,

[00:37:13] **Ben:** I, I, for me, I think if I'm alone, rarely, my concentration is very good. If, if like my wife is around, that's much more challenging.

[00:37:23] **Tim:** I'd say rarely.

[00:37:24] **Adam:** Okay. My, for me that's like a, sometimes to always, like, when I'm trying to read something or if I'm trying to pay attention in a meeting, I sometimes something will

[00:37:33] **Ben:** Ah, well, okay.

[00:37:35] **Adam:** catches my eye, you know, I'm like, squirrel. and, and, and I, I, I catch myself four or five times a meeting, thinking about a tangent, and I'm, I go, wait a minute.

[00:37:47] **Adam:** I just missed three sentences because I was, I was paying attention and that caused me to have a thought. And I'm like, I'm trying to expand on those ideas and see where that leads because it could be useful information, but in the meantime, I'm missing things. So I have to like consciously redirect myself to go back and pay attention to the meeting.

[00:38:04] **Tim:** Okay.

[00:38:05] **Tim:** How often do you avoid, dislike or reluctant to engage in tasks that require sustained mental effort or thought?

[00:38:11] **Adam:** So, yeah. Do you avoid things that, will require you to think deeply?

[00:38:15] **Tim:** Yeah, sometimes.

[00:38:17] **Ben:** Yeah, some sometimes, but I think for me that's more about how interesting is it. If it's interesting, I can do it. If it's not interesting, then I'm, ugh.

[00:38:25] **Adam:** Mm-hmm.

[00:38:25] **Tim:** Yeah.

[00:38:26] **Tim:** How often do you have trouble listening to someone even when they're speaking directly to you, like your mind is somewhere else?

[00:38:33] **Ben:** I think I'm

[00:38:34] **Ben:** I'm usually

[00:38:34] **Tim:** what'd you say? I rarely, I, yeah, that's rarely for

[00:38:40] **Ben:** my kryptonite though is if we're in a meeting and someone. For lack of a better phrase, is it like slips into marketing speak and they're just talking about, there's just, I, I don't even know what they're talking about, but they're using a lot of marketing lingo. I cannot pay attention if I'm staring at them and like watching their mouth move.

[00:39:01] **Ben:** I, I still can't pay attention. It's just, I just can't do it.

[00:39:05] **Tim:** how often do you forget to do something you do all the time, such as missing an appointment or paying a bill?

[00:39:12] **Ben:** That's like my, that's my superpower is, is consistency.

[00:39:16] **Adam:** See, I wouldn't remember to get outta bed if I didn't have my calendar to remind me.

[00:39:20] **Tim:** Wow.

[00:39:22] **Adam:** I have, I'm pulling up my alarms on my phone cause I have many alarms throughout the day.

[00:39:27] **Adam:** So,

[00:39:28] **Tim:** Wow.

[00:39:29] **Tim:** I have one to, to get up in the morning. That's it.

[00:39:32] **Ben:** I have, I have alarms. Well, I mean, some of 'em are recurring things and like, not for my own benefit, right? Like, so I have one in the evening to remind my kids to take their meds. I have one to remind me to take the PO or for the podcast when we record. I see. I put those in my to-do app, and then it's like a recurring to-do

[00:39:47] **Adam:** it, well, so, but the thing is, I need the alarm because I need it to be like, I need it to

[00:39:52] **Adam:** be to, to come get me.

[00:39:55] **Adam:** Right? I don't, I don't, with it in my to-do app, I might not think to look at it at the appropriate moment. Like if I look at my to-do app 20 minutes before the meeting, that might not be good enough. So,

[00:40:06] **Tim:** often do you lose or misplace or damage something that's necessary in order to get things done, eg. Your phone, eyeglasses, paperwork, wallet, keys, et cetera.

[00:40:15] **Ben:** Never.

[00:40:16] **Adam:** me, not so much that, except I think that this, what this one is getting at is like a little bit of clumsiness, right? And, I do. You know, I'm a computer guy, but at the same time, I also like to work with my hands, like I do the woodworking. I've, I've considered myself a handy person and I have my wood shop and, I am constantly hurting my hands.

[00:40:37] **Adam:** Like,

[00:40:38] **Adam:** you know, I'm just a little, just a tiniest, little bit careless y you know, turning or whatever. And so like I swing my hands into things or knock things over or hurt my hands. not like on a, a spinning saw blade, but, you know, just like bumping into stuff. Yeah. And occasionally, like I will back into something.

[00:40:53] **Adam:** I'm also a tall and wide person, so I, I take up a lot of space.

[00:40:58] **Tim:** So, I mean, my eyeglasses, I put 'em down and I cannot find them. But that's because I can't see, to find my glasses

[00:41:05] **Adam:** What about when they're on top of your head?

[00:41:06] **Tim:** and be, and because, and because I have bifocals now, it's like, I ha I take it, I don't even, I'm, I'm gonna get my eyes checked and I'm not gonna get bifocals again cuz they're absolutely worthless.

[00:41:16] **Tim:** I never actually use the bifocal function at the bottom cuz it's like uncomfortable to like point your head in the direction to look at it. I always wind up just taking them off and setting them down. That's why I lose them. So I'm just getting regular glasses next time. It's not worth the extra money.

[00:41:29] **Ben:** I don't, I don't know if this is a generational thing, but I cannot relate to people who don't know where their phone is. My phone is in my pocket

[00:41:38] **Tim:** Oh. I always know where my phone

[00:41:39] **Tim:** is.

[00:41:40] **Ben:** when people don't have their phone on them or it's ringing and they don't know where it is, I'm like, what? What world are you living in? Where you don't know where your phone is?

[00:41:49] **Ben:** Like how do you randomly look up celebrity net worths? Come on.

[00:41:56] **Tim:** How, how often do you have difficulty waiting your turn such as waiting in line?

[00:42:00] **Adam:** No, for me not, not really. I mean, I might have struggled with that one as a kid, but out outgrown the, the problem or something.

[00:42:07] **Tim:** I, I can't Self-checkout drives me nuts because I sit there and watch

[00:42:12] **Adam:** Oh yeah.

[00:42:13] **Tim:** try. I mean, it's like, this should not be taking you so long. How in the, because like

[00:42:19] **Adam:** That's a very type A

[00:42:20] **Tim:** check, you look at this, this self checkout, and you make a bet, you're like, this person only has a certain amount.

[00:42:26] **Tim:** They don't look like they're gonna be u using multiple forms of payment. and they look relatively intelligent enough to like scan stuff correctly. And then you get behind them and they are complete moron

[00:42:37] **Ben:** Yo,

[00:42:38] **Tim:** And I'm like, oh my God, I'm dying here. That just drives me. And maybe that's adhd, but maybe it's just I'm just a terrible person and I hate people.

[00:42:47] **Ben:** There's nothing wrong with hating people.

[00:42:49] **Adam:** I feel like the most of the places that I go to that have self checkout either don't have the volume where it's a problem where you have to wait in line. Or if they do have a line they use like the English system where it's one line for all of the registers and you just take the next available

[00:43:02] **Ben:** You queue

[00:43:03] **Tim:** Hmm.

[00:43:04] **Ben:** Oh, the, the thing that drives me crazy though is that a lot of checkouts will have a 12 items or less sign posted, and there, is inevitably that person who just has their entire shopping cart and just doesn't want to deal with people.

[00:43:20] **Tim:** how often do you feel like you're on the go? Acting as if you're driven by a motor, EG. You're unable to be, or uncomfortable being still for an extended period of time, such as in a restaurant or a

[00:43:30] **Adam:** Yeah. So that's the thing where I was talking about where you bounce your foot

[00:43:33] **Adam:** or. Playing with crap off your desk. so one of my kids has this real bad, like, I, I challenged him at dinner tonight to not say or make mouth noises for two minutes. And this was difficult for him,

[00:43:46] **Ben:** mouth noises.

[00:43:48] **Adam:** like laughing

[00:43:49] **Ben:** Yeah. Yeah, I know what you mean.

[00:43:51] **Adam:** whatever, like trying to, to make a point, making noises that aren't words or whatever.

[00:43:57] **Adam:** I was like, just like, just be silent for two minutes. Can you do that?

[00:44:02] **Tim:** How often do you feel restless? Like you wanna get out and do something

[00:44:05] **Adam:** Eh, for me I would say that's a, sometimes

[00:44:07] **Tim:** sometimes

[00:44:08] **Tim:** How often do you fidget or tap your hands, feet, or squirm in your seat?

[00:44:11] **Adam:** constantly, I, I'm constantly worried that the noises of the things that I'm playing with at my desk here while we record the podcast are gonna come through.

[00:44:20] **Tim:** Wow. Okay. Well, I, I, I think, okay. I feel better now. I don't think I have it.

[00:44:27] **Tim:** I'm, I'm, just, I'm just a jerk.

[00:44:29] **Ben:** do you have problems sitting through a movie?

[00:44:32] **Adam:** Me. not if it's a good movie,

[00:44:34] **Adam:** like there, I'm trying to think of one that I've turned off. Nothing's

[00:44:39] **Ben:** I don't think there's anything wrong with turning off a bad movie.

[00:44:41] **Adam:** yeah.

[00:44:42] **Ben:** But like my dad, my dad could not sit through a movie.

[00:44:45] **Adam:** yeah, no, my mom is the same way. she just doesn't have the patience to sit and watch a whole movie. And I like movies.

[00:44:52] **Ben:** I love movies so much.

[00:44:55] **Tim:** Well, that was interesting.

[00:44:56] **Adam:** So what, what about you makes your kid think that you might have.

[00:45:01] **Tim:** so we were doing, I was, I was, we were both in a meeting together and we had like responsibility for like, it was a Zoom meeting and we were like hosting the Zoom meeting. And while I was doing, I had to just constantly be messing, to be honest, I was just bored with the meeting. The, the meeting didn't really have, Content that I found exciting.

[00:45:21] **Tim:** So I was finding stuff to do on, we're both at computers, so like, I'm at a computer, let me mess around. And he's like, yeah, I do you have undiagnosed A D H D? Like, I don't, I don't think so. I just wish the speaker was more exciting.

[00:45:33] **Adam:** Hmm. Okay. So it wasn't that the window was organized wrong,

[00:45:39] **Tim:** no, I was installing, I was doing stuff that needed to be done on the computer. I'm like, well if, if I'm not, you know, entertained by what's going on now, let me just go ahead and do some necessary maintenance on this computer here.

## [00:45:49] Toxic Productivity

[00:45:49] **Adam:** You know, I think it, I think that in some cases productivity can be a disease.

[00:45:58] **Ben:** Hmm.

[00:45:59] **Adam:** Right? Like, I feel like we are so trained to try and squeeze value out of every second that we're awake, that it's, it feels wrong to take five minutes to do nothing.

[00:46:12] **Ben:** Yo, I, I do feel compelled to listen to podcasts. Kind of along those lines though, I, if I'm say out walking the dog, I, I can't. Just be with the dog and listening to the sounds of the birds and the trees. I feel like, oh, this is 20 minutes. I could be learning something new about technology or listening to the news or something.

[00:46:37] **Ben:** I feel like I'm, I'm missing that opportunity, and I, and I don't like that. I don't hate it, but I don't love it either.

[00:46:44] **Adam:** Yeah. Every now and then, I, I'm with you. I, I consume a lot of media through my ears, right? So, very rarely I will listen to a YouTube video without watching it like so. This week, I've been getting into Agile materials and so I listened to the Scrum guide and it's not like I, I searched Audible, I have an Audible membership, and I was like, well, maybe it's on there.

[00:47:03] **Adam:** I don't, I had no idea that how short it was. It is very short. It's like, you know, five pages or something like that. so I was like, well, you know, maybe somebody read it on YouTube or something like that. I did, I just Googled, or I searched for the scrum guide on YouTube and, and there was like, somebody just sat there and like read it as if it was an audiobook and there were comments under it that was like, as a blind developer, thank you so much.

[00:47:23] **Adam:** And I, I was like, that's awesome. And, and I was able to just, you know, hit play and put the, put my phone in my pocket and do other stuff and it's like, cool. Now I know a little bit more about Agile. and you know, I've listened to a lot of audiobooks and podcasts and stuff on. On dog walks and driving and in the shower, and it hurts me.

[00:47:44] **Adam:** Like, it's great that I get to consume all this information. I, I feel like it helps me be productive, right? Like I, I'm accomplishing more things that I actually want to do than I would be able to if I wasn't doing them in the shower and driving, et

[00:47:58] **Adam:** cetera. I'm, I'm further accomplishing more by listening at, you know, 1.52 x sometimes 2.5 x.

[00:48:05] **Adam:** How you do that? I, I,

[00:48:06] **Adam:** just have to train yourself. You start by listening at like 1.2 and, and then when that sounds, so what you do actually, pro tip, if you want to get into speed listening,

[00:48:16] **Adam:** crank it up a little bit at a time. When I say at a time, like, listen to it for 10 seconds. If you can still understand what they're saying, crank it up more.

[00:48:23] **Adam:** If you can still understand, crank it up more. So go to 1.3, 1.5, 1.8, whatever, until you can't understand it, and then go down by like two steps. , right. And then listen to that for like 10 minutes and then crank it up, start cranking it up again. A until you can't understand, and you'll find you'll be able to get faster.

[00:48:41] **Adam:** You'll be able to listen to it faster because your brain develops like a, a familiarity with the voice or whatever it is that you're listening to. And so, you, you develop this skill of being able to listen to it faster and faster. And now if I try to go and listen to an episode of Syntax on one X, it sounds like they're drunk

[00:48:59] **Ben:** It's so painful. It's so painful.

[00:49:03] **Tim:**

## [00:49:03] Excercise

[00:49:03] **Tim:** All right. So I mean, so we talked about a h What are some other things that is we need to do as developers? I mean, as people for self-care?

[00:49:12] **Adam:** So the two things that stand out to me that are obvious are we sit in a chair, for

[00:49:18] **Adam:** a, a ridiculously unhealthy amount of time. So trying to switch between standing, walking, sitting, would be healthy. So I have a standing a, a sit stand, adjustable desk, which I really like. and then taking care of your eyes, right?

[00:49:30] **Adam:** So taking opportunities to relax and sit in a dark room with your eyes closed, or go for a walk and look, look at things that are far away, is supposed to be good for your eyes. And then, you know, stay on top of your eye exams and, and get corrective lenses if you need them.

[00:49:45] **Tim:** Yeah, I mean, one thing I've been doing lately just because I've realized since, you know, working from home, since the start of the pandemic, it's like I really have not had a lot of movement. is to put my, wireless earphones in Bluetooth on my phone and if there's a, a meeting cuz like people, like lightly, no one ever turns their camera on.

[00:50:04] **Tim:** So I put my phone in my back pocket, I joined my teams meeting, have my wireless headphones in, and then I pace the house. I just, I just pace while the meeting's going on. And that's, I do have a fair amount of means from time to time, so that that kind of helps me get up and get around rather than just sitting in a chair all the time.

[00:50:21] **Adam:** That's a really good idea.

[00:50:22] **Ben:** I was just watching a video review of a desk bike, so I, I'm sure everyone's seen desk treadmills for standing desks, but this guy had

[00:50:31] **Adam:** a, keyboard.

[00:50:32] **Ben:** it's, it's like if you could take a bike and sort of cut it in half, And only have the seat and the pedals. It was, it was kind of like that. And it was on

[00:50:41] **Ben:** wheels? Well it was, it was stationary and, but it was on wheels and so it had like chair wheels on the bottom so you could roll it in and out from under the desk. I don't think I wanna walk cause I have flat feet and walk it as oftentimes. Like

[00:50:55] **Adam:** it, it's made to go under a desk, so it's like a recumbent bike.

[00:50:58] **Ben:** No, it's a seated bike, but you'd have to have a desk That raises up a bit, you know, cuz you're a little bit elevated.

[00:51:03] **Ben:** But I'm curious to try something like that. Like just a slow

[00:51:07] **Adam:** good things about like the treadmill under the desk.

[00:51:11] **Ben:** My thing is I, I would still kind of like the idea of being able to type and I can't imagine that I could walk and type at the same time.

[00:51:19] **Adam:** it sounds like something you would have to work at. Yeah.

[00:51:21] **Ben:** Yeah.

[00:51:22] **Tim:** Yeah. And after I have a doctor's visit coming up to make sure that everything with my recent surgery is okay, but I'm gonna get back to, going on the, so I have a standup at 11, which I schedule for an hour, but it's only usually 10 minutes and getting on the treadmill for 30 minutes. So 30 minutes a day.

[00:51:40] **Tim:** I have just some high, impact. exercise, you know, is for a person my age is very helpful. cuz it's like, I'm not overweight, but my, you know, it's, I've gotten a lot softer in the middle , so I keep having to buy bigger belts and I don't like that. So, yeah, hopefully that can, I can get back to that, that, that little little exercise every day would be helpful.

[00:52:02] **Tim:** And then I go get a shower. So,

[00:52:04] **Ben:** It's the social aspect of it. For me that always feels like the, the highest barrier to entry, meaning that like, Between work and dealing with the dog and being married and having set meal times. It's like there's, if I wanted to carve out just another half hour in the day for me to just do some stationary biking, I'm sure I could do it, but that it feels like then I'd have to

[00:52:34] **Adam:** you're

[00:52:34] **Ben:** run it.

[00:52:34] **Ben:** Run it by somebody. Yeah, exactly.

[00:52:37] **Tim:** Yeah.

[00:52:37] **Adam:** Well, yeah. I mean, that's, oh man, Ben don't have kids. Uh,when, when you have kids, it's like opening a new chapter in your life where your life is no longer about what you want It

[00:52:51] **Adam:** is,

[00:52:52] **Ben:** so I, I mentioned in the tribes and fails that I have been recently added to some standups on other teams and, one, two teams are just about to merge and so they had a, a standup and everyone was going around doing introductions and the guy running it was like, why don't everybody go around, talk about where they live and what kind of hobbies they.

[00:53:11] **Ben:** And two different people on the call. Were like, I had a baby eight months ago, so I don't have any hobbies anymore.

[00:53:17] **Adam:** Yeah.

[00:53:20] **Tim:** My life is feeding this thing and wiping its butt.

[00:53:23] **Adam:** And I try to sleep when it's asleep

[00:53:26] **Tim:** Exactly. Hey, trust me, when they get teenagers, you know, hopefully it, it, it's usually for us it's a lot better. It gets, it gets better.

[00:53:37] **Adam:** Yeah. But that first 20 years

[00:53:39] **Tim:** Yeah, for sure.

[00:53:40] **Adam:** it's technically only like, you know, maybe 15 years till they become,

[00:53:45] **Adam:** you know, 12 to 15 years depending on the kid, till they become like, you know, fun to hang out with

[00:53:51] **Tim:** Yeah.

[00:53:51] **Adam:** and you're not doing what they want to do. but it feels like 20 or 30 years sometimes.

[00:53:58] **Tim:** and, and I would say so, you know,

## [00:54:00] Social

[00:54:00] **Tim:** I think many of our listeners there working remotely as well. And, and I'm struggling with this now. I really don't have a good answer. I do not spend a whole lot of time with people other than people in my house

[00:54:12] **Ben:** Yo, I'm feeling that

[00:54:13] **Tim:** and you guys, right? So this podcast is like you guys and then all, so everyone else is physically, I don't spend a lot of time with anybody other than my, my immediate family virtually, like, like you guys.

[00:54:26] **Tim:** And we have our, you know, you know, role playing group on Tuesday. But other than that, it's like I don't get a whole lot of other people time.

[00:54:34] **Ben:** yo and I recently moved away from a city center, or I, I was at least closer to a city center, and I have moved farther into the country. And every now and then I'll go to meetup.com and be like, where's the closest web development meetup or any kind of technology meetup? And it's like, closest thing is two and a half hours away, and you're like,

[00:54:54] **Tim:** Yeah.

[00:54:55] **Ben:** Killing me. I gotta, I gotta find another social group of people. I have like nothing in common with

[00:55:01] **Adam:** Start doing like hot yoga and you'll be the, the one guy there or something.

[00:55:06] **Tim:** but what's funny, it's like I don't really even know if I want to, it's like if I can get, if I can get away with not leaving the house for, and, and this is not me, I don't know, I guess the pandemic, like just, it made staying at home like a virtue and now I'm just keep holding onto that

[00:55:23] **Ben:** Well, this is, this is what I say to my wife all the time is I'd be like, I want to be the kind of person who wants to do that stuff. And it's, that's like that weird, difference between the image I have of me and the actual me. And there's, there's a conflict.

[00:55:38] **Tim:** It, it was funny. That was me. I was the guy who like, create, you know, we had a meetup group, like a, we'd do monthly meetings and programming stuff and I would create groups like, and they bring people in. But now it's like, I can't be bothered. I don't I don't know what's changed. It, it's the pandemic. It's just changed my mindset about like creating opportunities to socialize.

[00:56:05] **Tim:** It's, it's become, it's given me, I don't know if it's gave me an excuse to say, no, we're not, I don't wanna do that cuz it's not safe. I, I, I don't really know. I want get back to being that person, but I don't know how to get there.

[00:56:16] **Adam:** Yeah, I, I've been working from home for 10 years and change, actually, it'll be 11 years in less than a month. and yeah, that I struggled for the first several years, like just constant cabin fever. I would go out and, I, like noon was great because all the, the places near my house that were, receptive to having somebody come in and work there for the day were bars.

[00:56:41] **Adam:** And so you can't get in before noon. Right. Or you could go to like McDonald's, but it's cold and the wifi sucks and Right. So we don't have like a Starbucks near me or anything. That's how far out in the country I live. so, the, the closest something like that would be like a Panera that's like 30 minutes drive from my house, so it's just not worth it anyway.

[00:56:57] **Adam:** So I would, you know, work half a day from home and then I would, like, at lunchtime I would pick up and move and I would grab lunch on my way and, and work the rest of the day from a bar or something just to the change of scenery. Having people moving around me, you know, just felt better. And after a while, I don't know if it was when the, our business really took off or whatever.

[00:57:16] **Adam:** I just, something about being busy and like, it was just easier to stay home.

[00:57:22] **Adam:** Right.

[00:57:23] **Adam:** but I, I totally get you on the needing something social. and I would say if anybody is struggling with that hobbies, right? So find, find a hobby. That's a social hobby for me that tends to be skydiving. You know, I try to go e every couple of weeks, and I go and I hang out with a bunch of people and.

[00:57:40] **Adam:** there are things about it that are not particularly covid safe. Now we're all vaccinated and we try to, you know, wear masks and do the right thing. But, at the end of the day, we're taking five people and cramming them into a sardine can and throwing it into the air, right? Like, you're, you're gonna be in close quarters.

[00:57:54] **Tim:** You're just gonna have to, certain amount of trust. And, and part of that is trust in your vaccine. Part of it is trust in your fellow humans. anyway, that was a more political than I meant it to be. Sorry. I don't think it.

[00:58:04] **Adam:** okay. yeah, but hobbies I think are crucial. If you're feeling, you know, socially depressed, like you're not, there's a part that's missing because now that you're not going to the office or whatever, then that, to me, that seems like the, the choice.

[00:58:17] **Adam:** And, and it could be like my wife, volunteers at a local animal rescue and she goes in and, you know, like walks dogs and helps take care of 'em, groom 'em, or whatever. and it's just like once a week for like a couple of hours. And there like a, she loves dogs, so it's great, you know, she, that alone would be worth it to her.

[00:58:37] **Adam:** But then like there's a whole bunch of people there that like, that's the only way she knows them. And so it's just this other little social group

[00:58:44] **Ben:** W when we moved out here to the country, I thought that the dog was gonna be my, my social lifeline and there was a dog park. And so we started taking the dog to the park on the weekends, Saturday and Sunday morning. And nothing against these people, but it was all, it was all like retirees and, and they were terribly nice, but just like I wanted, I was hoping to meet a somewhat younger crowd.

[00:59:08] **Adam:** right.

[00:59:09] **Adam:** Somebody you would wanna hang out with on the weekends.

[00:59:11] **Ben:** Yeah. Yeah. You know, someone that might be beyond the, the, the fence of the dog bark.

[00:59:16] **Adam:** Okay. Well, anything else we wanna squeeze in here before we wrap?

## [00:59:19] Structure

[00:59:19] **Ben:** we've, I've talked about this before on previous episodes, but I live and die by structure, and it's very important for me that I start work at the same time every day and that I end work at the same time every day. And I don't have incidents in the middle of the night and or not. I Lunch is flexible for me in terms of when it is because of various meetings.

[00:59:42] **Ben:** If I do it at 11, it's fine. If I do it at two, it's fine. I don't really care. But I take a full hour lunch and there are days sometimes when I'm actually really excited about the work that I'm doing and I'm tempted to not take lunch. And then I remind myself that I have to do it. And every time I step away from the desk, it feels great.

[01:00:02] **Ben:** And, so that's, I I have to have structure. I can't not.

[01:00:06] **Adam:** So, this is a call back to something we talked about a little earlier. I mean, also, yes, structure. that's the only way I got through school. I got really good grades, thanks to my mom who put in some good systems for me to, be able to focus and be organized and turn in the assignments that I did rather than just like leave them in the bottom of my backpack.

[01:00:23] **Adam:** the, but we talked about consuming a lot of content, listening to it on one and a half, two speed, whatever. the problem with that, I've noticed that you probably have noticed too as a listener of this podcast, is that my brain and my mouth are always going way faster than most people. Are ready to hear

[01:00:40] **Adam:** And so I, I consciously have to slow myself down and choose to speak slower, and it's very difficult for me to do. So I apologize. And I thank you for putting up with me,

[01:00:52] **Tim:** I, I think you do better than me because I, I was listening to, I just did it. Right now. I tend to stammer sometimes, right? I'll stop back up. Yeah. I'm like, I'll listen to myself like, is that really what I sound like? And at my son's stammers and like, it annoys me and then I listen to myself. I'm like, oh my God, he got it from

[01:01:09] **Adam:** Yeah.

[01:01:11] **Adam:** I learned it from

[01:01:12] **Adam:** you.

[01:01:13] **Tim:** my son is a car. He, my son is a six foot four carbon copy of me,

[01:01:17] **Adam:** Yep. Yep. well, I guess we're gonna go record our after show. let's see, before we do that, we have a, a brief small whatever announcement. So we actually know what we're gonna do next week as of this recording.

[01:01:30] **Tim:** Right, rather than waiting 30 seconds before the show

[01:01:32] **Adam:** We figured we could tease it. we're gonna have a guest next week.

[01:01:35] **Adam:** Some of you might know him. Brian Ranaldi will be joining us to talk about, developer conferences, what's going on in, in that industry. So he's deeply ingrained in, running and attending and speaking at developer conferences. And, he wrote an interesting article about it, and so we thought we'd have him on and have a talk about it.

[01:01:52] **Ben:** We may also discuss some codefusion. He is a longtime codefusion developer. Just throwing that out there.

[01:01:57] **Tim:** and

[01:01:58] **Ben:** Yes.

[01:01:59] **Tim:** Flex, is dead.

[01:02:00] **Adam:** cool.

## [01:02:01] Patreon

[01:02:01] **Adam:** So,

[01:02:01] **Adam:** this episode of Working Code was brought to you by Adderall and listeners like you

[01:02:07] **Tim:** Consult your doctor if you need to have

[01:02:08] **Adam:** Uh,well actually it's apparently, it's really hard to get, I'm not on Adderall because, there's shortages and stuff, and she was like, it'll, it's not worth the headache right now. Just try this other thing. So,

[01:02:17] **Adam:** anyway. I am not even gonna touch that one. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this was out into the universe, then you should consider supporting us on Patreon.

[01:02:30] **Adam:** Patrons cover our recording and editing costs, and we couldn't do this every week without them. Thank you all so much. Special thanks of course, to our top patrons, Monte and Giancarlo. You guys rock. If you wanna help us out, you can go to patreon.com/WorkingCodePod

## [01:02:45] Thanks For Listening!

[01:02:45] **Adam:** your homework this week. We want you to come join us in Discord, go to workingcode.dev/discord. A great way to network, great way to meet other like-minded people who wanna have a social aspect about their life that's not just staying home and talking to the people that they live with.

[01:03:01] **Tim:** I, it's funny you say that. I heard someone on our Discord channel describe to one of their coworkers that workingcode.dev Discord was like, developer support group.

[01:03:12] **Adam:** Yep.

[01:03:12] **Adam:** Absolutely. That was, that was one of the ways I was thinking about the podcast itself, before, before we started it, so, yeah. Yeah. I'm glad that it's become that. so that's gonna do it for us this week. We'll catch you next week and until then,

[01:03:25] **Tim:** Remember, your heart matters even if you can't remember what you did. 10 seconds.

[01:03:29] **Ben:** Squirrel
