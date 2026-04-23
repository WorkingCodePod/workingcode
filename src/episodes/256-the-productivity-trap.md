---
title: "256: The Productivity Trap: How Optimizing Everything Broke Us"
description: "It's 11:30 PM and you're still prompting. The code is better than anything you'd have shipped a year ago — so why are you still here?"
date: 2026-04-23
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/b25d2fc1-e892-4406-8fca-1417895c2fe1"></script>
<div class="redcirclePlayer-b25d2fc1-e892-4406-8fca-1417895c2fe1"></div>

It's 11:30 PM and you're still prompting. The code is better than anything you'd have shipped a year ago. The output is prolific, the roadmap is moving, the tooling is miraculous. So why are you still here at 11:30 PM? This week is an honest conversation about the strange shape of burnout in the AI era — the productivity that keeps compounding, the bar that keeps rising right along with it, and the quiet feeling that somewhere in the last year the craft stopped feeling quite like yours.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/256-the-productivity-trap.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Tim:** I feel like we've gone from being artists to being gardeners.

[00:00:03] **Adam:** Hmm.

[00:00:04] **Tim:** we're planting a seed and we have no clue what the seed's gonna grow into.

[00:00:08] And then we'll water it a little bit and then let it grow and then go, oh, wait a minute. This is completely wrong seed. We'll just like, dig the thing up and plan it. You know? That's kind of what I feel like we're, we're, we're shifting paradigms of what we're doing as an entire industry,

## [00:00:41] Intro

[00:00:41] **Adam:** Okay, here we go. It is show number two to the eighth, and on today's show we are going to talk about the productivity trap, how optimizing everything broke us.

[00:00:49] and we're gonna do our best not to make this an AI topic. It's probably gonna come up, but we're gonna, we, we, we've been talking about AI too much, so we're gonna kind of pump the brakes on that a little bit. Anyway, we don't have Carol with us tonight. She has an excused absence. She had some work stuff she had to take care of.

[00:01:05] So it's just the guys tonight, which means, Mr. Cunningham, I'm coming to you first. What do you got going on? My friend?

[00:01:11] **Tim:** Cunningham is my dad, by the way.

[00:01:14] **Adam:** Mr. Tim?

## [00:01:16] Tim's Triumph and Fail

[00:01:16] **Tim:** I'll take it. So yeah, I'm gonna go with the fail. So my dad's cohort generation is, seems to be dying out. My dad's 82 and, and three of his, like closest friends died this past week.

[00:01:33] **Ben:** That's brutal.

[00:01:34] **Tim:** Yeah, it is brutal. And I, I feel for him because he's like, he's going through it. He's definitely deep in the feels right now.

[00:01:41] But also for me, it's, it's, these were the men that I, as a small child looked up to and saw as giants, right. And just seeing them go away. It's, it's hard. It's really hard to, to kind of deal with. And I, I imagine a lot of our listeners who are kind of the same, generation as me. I'm Gen X, and so a lot of the other Gen Xers are probably going through similar things.

[00:02:07] I, I don't know if I mentioned this directly on the show show. I, I think I mentioned it in the after show, but I have been going to therapy, past few months, just for other reasons. But, I don't like journaling. And I told my therapist that and he asked me what I, what do I like? And I said, well, I like, I like music and I like writing songs, or at least I used to and I want to do it more.

[00:02:29] So he, just said, well, why don't you write some songs about it? And so that's what I've been doing. And so I wrote a song for my dad's best friend, well actually is for his daughter. She's, same age as me. And, Her name's Missy, but he called her dad called her a bug.and, and I wrote a song called Hey Bug about her dad.

[00:02:51] He was like a, a the ultimate businessman wheeler dealer, I mean, could turn dirt into gold kind of guy. And so I wrote a song about that and yeah, I, I, I sent it to her today. I, I, I created a cd, like I'm going old school, like an old school cd, although I did put a thumb drive in there with an MP3 and some lyrics just in case, just in case she didn't have a CD player because I don't have one.

[00:03:18] My daughter bought one, my daughter bought one just for like nostalgia reasons. That nostalgia she never experienced. I don't know why, but she bought one. So I burned a cd, put a CD in the, put it in the mail with the MP3 and sent it to her. Just one song called Hey Bug about her dad.

[00:03:34] **Adam:** you, now that you mention it, sorry to tangent here. we, we witnessed the birth and death of CDs in our lifetimes.

[00:03:41] **Tim:** You know what? I've witnessed the birth and death of vinyl. Tape, eight track CDs.

[00:03:50] **Adam:** way you witnessed the birth of vinyl.

[00:03:52] **Tim:** not the birth of vinyl, but the, I mean, so when I was in, I was, I was born, I was definitely witness to death. So I mean, I was born in the early seventies, so vinyl was the only way to get it back then.

[00:04:03] **Adam:** Sure. But

[00:04:04] **Tim:** And then tape came along and tape took over.

[00:04:07] Eight. Track was kind of one of these like gross cousins that just kind of hung out, hung out and smoked pot. and then you, then you had CDs, and then we went, you know, MP3s and then streaming. So, yeah, no wonder Gen X is so pissed off. It's like every, we had to, we had to rebuild our music library forever.

[00:04:24] I went up the at, I went up the attic to try and find pictures of some of my dad's friends. I couldn't find pictures, but I found like a whole crap ton of CDs that I burned back in the nineties and two thousands. And I'm like, these, these things are worthless.

[00:04:39] **Adam:** Anyway, so let's get back on track here. Did she like the, the song?

[00:04:42] **Tim:** I dunno. I, I mailed it today. She'll find out. I didn't tell her about it. I, I wanted, I wanted as a surprise. So, yeah. I mean, she's preparing for the funeral and going through all that crap that you have to go through when somebody dies. I mean, so yeah. I just, yeah, just little song that I created for, you know, my 12 string guitar, so hopefully she likes it.

[00:05:02] **Ben:** That's lovely.

[00:05:03] **Tim:** So

[00:05:03] **Adam:** feel like writing the song helped you,

[00:05:05] **Tim:** I do,

[00:05:06] **Adam:** you get your,

[00:05:07] **Tim:** I do,

[00:05:07] **Adam:** That's awesome.

[00:05:08] **Tim:** I, so, I mean, last week actually, I mean, this was kind of a bonus song. I was, I, I had already written, so I, I, I don't know if I talked about this in the show show, but, I found an old tape of mine and I, I found an old song that I wrote when I was 25, and I've basically branched off of that song and created three other songs.

[00:05:27] Just kind of like the, this song was written when I was like, you know, going through like a. 25-year-old, 26-year-old, emotional drama of dating. And then I kind of progressed it through like getting past that crap and just deciding, you know, I wanna be a family man. And then kind of just the exception of, accepting the fact that I've gotten older and that my life is, you know, it's not what I wanted it to be, but it's not bad.

[00:05:58] So, yeah, I wrote actually four songs in the past two weeks.

[00:06:03] **Adam:** Wow, man.

[00:06:04] **Tim:** and they're just, they're just for me. They're just for me. I so it, it's, it's my version of journaling and I listened to, I, I, I listen to him in the car when no one else is around. 'cause I don't want the judgment from other people, but I listen to him, I'm like, yeah, this,

[00:06:20] **Adam:** dude, I love that for you.

[00:06:21] **Tim:** I give that, uh, it, it really helps kind of solve the pain of just living.

[00:06:28] So that's my fail, but also triumph. How about you, Adam?

## [00:06:33] Adam's Triumph

[00:06:33] **Adam:** I'm gonna go with a triumph. so as we're recording this, it's, roughly a week, maybe a week and a half, since the Artemis astronauts, went around the moon. Right. And I just wanted to say, you know, Artemis astronauts eat my dust they went around the moon. I just finished a lap around the sun.

[00:06:53] So,

[00:06:53] **Tim:** What? Yeah. Happy birthday.

[00:06:56] **Adam:** yeah. So

[00:06:58] **Tim:** How old are you?

[00:06:59] **Adam:** today is my birthday. I'm

[00:07:00] **Ben:** Oh, nice. Happy birthday. I didn't realize.

[00:07:03] **Tim:** So today's the 21st. You're like one. You were one day away from being born on four 20.

[00:07:07] **Adam:** Yeah. I've never heard that one before.

[00:07:12] **Tim:** That's

[00:07:13] **Adam:** simple for me. another, another year. Another year in the books. Another trip around the sun

[00:07:18] **Tim:** Yep. And didn't, didn't have to spin any rocket fuel.

[00:07:22] **Adam:** Nope.

[00:07:23] **Ben:** Do you have a, uh, favorite birthday dessert?

[00:07:26] **Adam:** Yes. and I didn't even have to ask for it this year, so actually it's, it's a type of birthday cake. my mother-in-law makes this awesome, chocolate tweed cake. So she like, kind of freezes chocolate and then you grind it up so you get little, like chocolate flakes and you mix it into the cake batter.

[00:07:42] And then she makes this like, I think it's like homemade buttercream frosting.it's, it tastes a little bit eggy. It's, it's just really good. and then a, like a chocolate drizzle over the top. Oh man. So good.

[00:07:53] **Ben:** it sounds amazing.

[00:07:55] **Adam:** for, for several years running, you know, she, they always volunteer to make me, it's my wife and I, our birthdays are really close.

[00:08:01] We're like, about a week apart.and so we celebrate at the same time, share with each other for the purposes of our families and stuff. But, so my, my in-laws always volunteer to make us a cake and ask what we want. And it's always that chocolate tweed cake. and this year they didn't even ask.

[00:08:17] They just made it and brought it.

[00:08:18] **Tim:** That sounds awesome.

[00:08:20] **Ben:** Winning that sounds,

[00:08:21] sounds.

[00:08:22] **Tim:** like, like tweed, like the fabric.

[00:08:25] **Adam:** It is spelled like that. I believe so, yeah.

[00:08:27] yeah.

[00:08:28] **Tim:** That sounds really good.

[00:08:29] **Adam:** yeah. I'll have to see if I can find a picture. it's, I'll, I'll, I'll share it in our discord if I can find it, but man is good.

[00:08:36] **Tim:** Hmm. Nice. Well, congratulations.

[00:08:39] **Adam:** Thank you.

[00:08:40] **Tim:** I'm glad you're still with us.

[00:08:41] **Adam:** Me too. And Ben, what have you got going on friend?

## [00:08:45] Ben's Triumph

[00:08:45] **Ben:** I will also go with a triumph, which is that, I have complained in the past that everyone is always saying how much they're learning from the code that AI is generating. And I always felt like I. I wasn't learning from it, but, I did learn something and, it taught me about locking reads at the database level,

[00:09:03] **Adam:** Mm-hmm.

[00:09:04] **Ben:** which I didn't really know about, which is also shocking that I've made it this far into a web-based career without knowing about locking reads at the database level.

[00:09:12] did some research on it, read the documentation for the younger listeners that's a, centralized recording of how things work. did some experimentation and then also kind of, tried to apply a lot of the things I was reading about locking reads to my little side research project, big sexy poems.

[00:09:34] And then having Claude look at it and say, how does this work? Am I doing it right? And kind of iterating? And I just felt like it was the first time that Claude Code had sent me down a fun little rabbit hole of research. And, I was pretty pleased with that.

[00:09:49] **Tim:** What, uh, database?

[00:09:51] **Ben:** Uh, MySQL, but apparently locking reads is pretty common for all of the

[00:09:57] **Tim:** Yeah. ' cause it's funny, I, I ran the same thing. I was trying to run a query against a production system and it was like bogging it down.

[00:10:05] So I pulled up FusionReactor and I noticed that what I, my query I was running was killing the server. And so I asked Claude, I'm like, this is killing the server. What do I need to do? And it started doing like, it was, this is, Microsoft SQL, it did, uh, uncommitted reads

[00:10:22] **Ben:** Hmm.

[00:10:23] **Adam:** Hmm.

[00:10:23] **Tim:** and ran that against it and did it in batches with some pauses in between the batches and was able to do the entire thing without affecting the system.

[00:10:33] But I had never, I, I wondered why have I not known about this all these years?

[00:10:38] **Adam:** Is that a, Microsoft SQL specific feature? I'm not familiar with this one.

[00:10:41] **Ben:** the uncommitted reads is a isolation level for the transaction, which I'm saying that because I've recently read about it and I don't necessarily know how it all works, but there's 'cause when I was reading about the locking reads, so this is where I get a little confused. The locking reads is.

[00:10:59] Who has access to read or mutate a row. And then the isolation level has to do with who else can see the things that you're doing. So, for MySQL's InnoDB storage engine, the default isolation is repeatable read, which means that if you query the database inside of a transaction and then you do the same query, you're guaranteed to get the same results. Whereas read uncommitted or I think is what Tim was just saying, is you can, anybody changes, you can see those changes right away, even if they haven't been committed to the database.

[00:11:39] **Adam:** It doesn't isolate the whole transaction as a group atomically. Okay.

[00:11:43] **Ben:** That's, and this is like, this is one of those things where I'm like, oh, I'm pretty good at databases.

[00:11:48] And like really what that means is like I'm good at running selects and inserts and deletes and not like actually really using the mechanics of the database in a really great way, which

[00:11:59] **Tim:** Yeah. My, my level was like just doing a with no lock, and I thought that was magic,

[00:12:04] **Ben:** Yeah.

[00:12:05] **Tim:** it, it exposed me to a whole new world. So we both learned something this week, Ben.

[00:12:10] **Ben:** Yeah. I

[00:12:11] **Adam:** can't wait to find out when, this feature comes back to bite you in the butt. It's always like, you know, oh, we've got JSON columns and then we, so, so we do start to do some relatively clever stuff with that. And then all of a sudden like, oh, we brought down the database because we were using JSON columns in a very inefficient way.

[00:12:26] **Tim:** right. You're doing text searches. No wonder it's taking forever.

[00:12:29] **Adam:** Yeah, a whole table scan across 300 million rows.

[00:12:33] **Ben:** But yeah, so I was happy to do some learning. I feel like I've been a little bit.devoid of learning in my life recently, and this kind of can relate back to the topic of the show actually, just, but so it was nice to, I felt a little freshened up putting some new juice in my brain.

[00:12:49] **Adam:** Yeah. Well, so let's, I guess let's transition into the show topic. Maybe a, a new record for us, or at least a, a local

[00:12:57] **Tim:** 15 minutes. Wow.

[00:13:00] **Adam:** less than, and, uh, yeah, so, basically

## [00:13:02] The Productivity Trap

[00:13:03] **Adam:** we wanna talk about burnout, right? Like, probably surprising. Nobody that has heard most of this podcast, I'm feeling a bit burnt out just on life in general, right?

[00:13:09] I've, we've been doing this podcast for, what, four or five years now. And, I, this entire time I've just been a very ambitious person and, and for many years prior, you know, I take on a lot of side projects and, and try to turn everything that I do into a business because that's how my brain is broken.

[00:13:27] And,

[00:13:28] **Tim:** culture,

[00:13:29] **Adam:** yeah, and, and I, it's like I derive my self worth from how many dollars I can bring in. And, I, I recognize that, that, that that's not healthy, but it doesn't mean that it's easy to turn it off. anyway, yeah, we just kinda wanted to get into like, burnout and, and how that has changed. Like we talked about burnout very early on this podcast.

[00:13:50] and I think that the addition of AI coding especially has changed, the landscape of burnout and it's probably a good idea to revisit that.

[00:14:03] **Tim:** yeah. And I think, so we started this podcast. It was like early COVID, right?

[00:14:08] **Adam:** yeah. So our first episode aired the very end of 2020.

[00:14:12] Tim,

[00:14:12] **Ben:** Crazy.

[00:14:14] **Tim:** Wow.

[00:14:15] **Ben:** Ugh.

[00:14:16] **Tim:** And the world is just, I hate sounding like an old fart. 'cause old farts always say this, but the world has gotten absolutely insane since 2020.

[00:14:26] **Adam:** I, agree.

[00:14:28] **Tim:** we are adjusting from a trauma,

[00:14:31] **Adam:** Yeah.

[00:14:32] **Tim:** the trauma of COVID, the trauma of what happened, January 6th, politically. Yeah. And the markets are responding in a crazy way,

[00:14:44] **Adam:** Yeah, so there's additional trauma because we're all watching our 401Ks go like into the toilet and then up to the moon, and then back into the

[00:14:50] toilet, and

[00:14:51] **Tim:** Yep. So, but the pro, we talk about productivity, it's like

[00:14:57] we have levers now that can make us a whole lot more productive. And one of them, I mean, I don't, you say you don't want this to be an AI show, I get it. But AI really is a, a, the past couple years has been a major driver in the productivity trap early on. I feel like coders kind of got it. You know, we all kind of adopted early.

[00:15:20] Not talking about you, Ben, but, um we, we, Hey Zing. Sorry. We, we kind of adopted early. I'm like, okay, this is cool. We can do some stuff with this. And like a lot of us, I mean, I bought a personal subscription before the C corporation would buy me one because I'm like, let, let me check this out because this is, this seems cool.

[00:15:40] And then we started to see what it could do. Well now everyone else, and I'm sorry if this is a pejorative, but the normals, the normals are starting to catch on that there is some productivity gains. So people like in hr, in design and people that aren't normally like your hardcore developer kind of people are like, Hey, I can use AI to like speed up my workflow.

[00:16:07] **Adam:** Yeah, Carol mentioned her real estate agent wrote himself some software that was all buggy and

[00:16:11] **Tim:** Yep. Right. But I mean. I mean, they're aiming toward efficiency. And so we're, I think we're getting to a world where the promise is we're gonna be able to do more and have more free time because of ai. But what I see the pattern of history over the years has been is that the, it's the highway problem.

[00:16:34] If you create more lanes, you just get more traffic. And that's what's gonna happen in our lives. We're just gonna, when when my boss, she starts sending me distilled ai, and I, you can tell because it's like no one ever actually normally puts a, like a, an emoji con, of like different, you know, in bullet points and such.

[00:16:53] Perfect. Right. And so you can tell that they've, they've copy and pasted something from AI and put it into their email to send to you. And they've done it very, very quickly. And now I have to, in return very, very quickly, ingest that and return it back to them and ho and hope it's right. and so we're, I feel like we're gonna get caught in this cycle of regurgitating AI back and forth to each other, and we're gonna get more done.

[00:17:22] But I don't know if it's gonna be better, and I don't know if, if it's gonna be very well thought out,

[00:17:29] and I think we're gonna get burned out

[00:17:32] **Ben:** I was listening to something the other day, I can't remember what podcast it was, but they were talking about this idea that there's kind of a a zero sum attention pie and that there are a lot of markets that it's not like there's a lot left to win. And they were talking about something like Uber and Lyft and they're like, okay, well what if Uber invests in a ton of AI and they become a lot more productive?

[00:17:59] And then Lyft does the same thing and now they're a lot more productive. So now you have these two companies that are basically the, the top leaders in the, you know, car service comp industry. Like now they're all just being more productive, but it's not like there's more pie for them to take.

[00:18:15] **Adam:** Right.

[00:18:15] **Ben:** So like what does that productivity actually get them in the long run?

[00:18:18] Accept more cost,

[00:18:21] **Adam:** I'm not sure It's a perfect metaphor because you, the, if there, the only way there's not more pie for them to take is if everybody on Earth is using Uber and Lyft for every ride they ever take. Right. That's not happening. But I, I, I, I do think it's a valid metaphor. It's just not perfect.

[00:18:36] **Ben:** but there's also, people will talk about the

## [00:18:39] AI-Generated Businesses and Saturation

[00:18:46] **Ben:** lowering the barrier to entry for creating businesses, which I think that's happening, but at some point there's a, a saturation, you know, there's already more businesses than, than I can make use of. And even when I go to amazon.com and I look up, you know, show me this product, I already get 27 pages of basically the same product being stamped out by different manufacturers or white labeled by different companies.

[00:19:04] So at some point if you say, well, the future's gonna be so great, 'cause everyone in their grandparent can start a new business. But like, who's, who are those customers then?

[00:19:16] **Tim:** Right.

[00:19:17] **Adam:** Yeah.

[00:19:18] **Tim:** It. It's funny you say that, Ben, you just triggers. So, so over the weekend I was at, Lowe's getting some paint. I was building some, some planter boxes for some citrus trees. I'm trying to grow and I saw a guy who used to work for us, like at the same paint counter and his name is Wes. So I like pulled out my phone.

[00:19:36] I'm like, Hey Wes. And he, I see him look because he's on his phone right waiting 'cause we're all waiting for the paint. And he sees that and he looks around and then he sees me, like comes over and he is like, he's like, Hey, what you up to? I'm like, yeah, we, we chat. And he's like, you've been using ai.

[00:19:51] I'm like, dude, that's my whole job now. My whole job's ai. He goes, so I just ba he tells me about his thing he built, which is, he basically built Shopify. On using ai, and I'm like, well, you know, I'm just like looking for a business venture. I'm like, if you need some credit card payment stuff, I can help you.

[00:20:12] Like make some, you know, actually get some money rather than being a call center, you can make some money off of it. He's like, all right. Yeah, we'll, we'll chat. But I'm thinking like, so if this dude who like just some random dude, how many other random dudes at every Lowe's waiting for paint has built a Shopify version using ai?

[00:20:32] What value is that to, to have where everyone's just building these random things,

[00:20:39] **Adam:** I think we're about to witness an explosion of people realizing that writing code and having an idea is like the easiest part of starting a business. You know, marketing and getting users and keeping them happy. Yeah.

[00:20:54] **Tim:** Yeah. Have having worn those hats. The hardest job I've ever had in my life was sales. And I, I, I will never go back to it. I enjoyed it. I enjoyed marketing a lot, but that's a black magic that there's very little metrics for to, for success to prove that you're actually doing your job.

[00:21:12] And sales is just basically the good old boy network

[00:21:17] **Adam:** Yeah.

[00:21:17] **Tim:** on speed.

[00:21:19] **Ben:** Well, let me,

## [00:21:20] Keeping Up and Falling Behind

[00:21:30] **Ben:** let me paint everything in this light. I feel like probably the last 20 years of my life has been a Controlled, embracing of the idea that I can't keep up. And it, it started very early on with email. I just can't keep up with my email. I got so many unread emails. I have emails that I've starred that I intended to respond to, which, you know, are now backed up probably for months.

[00:21:48] and then it was blog posts trying to keep up with other people's blog posts. And then it was, technologies, trying to keep up with technologies even if I wasn't like doing deep learning, just kind of trying to keep my finger on the pulse. And then it's HTML and CSS things coming out and trying to keep up with that.

[00:22:05] And everybody come out with new databases and then new platforms as a service. And like, it's, the idea that I'm constantly falling behind has just continued to accelerate. And I think the AI era has just put that feeling of keeping up with the Joneses into. I'd say into overdrive is an understatement. I mean, when I hear about other people and the amount of stuff that they're doing, it's like on one level I feel bad because I don't have this wellspring of ideas that I even wanna work on.

[00:22:43] You know, everyone's saying like, oh, finally I can take that backlog of a million ideas that I've had kicking around and I can finally do it. I'm like, I don't even have a backlog of ideas. Like that's how lame I am. I don't even have a backlog of

[00:22:55] **Tim:** You got poems. You

[00:22:56] got poems, Ben,

[00:23:00] **Ben:** And then on top of that, I'm seeing people just producing so much stuff and it's just, again, it's this constant sense that I am falling behind in a way that I can't even articulate.

[00:23:13] It's just like people are doing stuff and I don't feel like I'm doing stuff, and that is making me feel

[00:23:19] terrible.

[00:23:20] **Tim:** That's the trap.

[00:23:22] **Adam:** So you mentioned email and that, I don't know if you saw when you started talking about that. I just had the biggest smile

[00:23:27] **Ben:** Yeah. Yeah.

[00:23:28] **Adam:** So I,

## [00:23:29] Inbox Zero Philosophies

[00:23:35] **Adam:** I don't use my email as a to-do list, but I kind of use my email as a to-do list. like when I receive an email especially, so I, there's just like two or three newsletters I subscribe to.

[00:23:39] TLDR is one of 'em. and you know, I don't always get to read them every day when they come in or every couple of days. And so what I'll do is I leave it unread in my inbox as a, as a reminder, Hey, come back and read this. And other than that sort of thing, I tend to attempt to be an inbox zero kind of guy, right?

[00:23:57] I leave stuff in there that I intend to come back to, but I can't get to now. Otherwise I try to process and archive and delete and all that. So I, I scrolled to the bottom of my inbox to see what is the oldest unread newsletter that I have in my inbox that I've been holding onto. And the date on it is 1/1/2026.

[00:24:15] **Tim:** Well,

[00:24:16] **Ben:** All right.

[00:24:17] **Tim:** I, don't know how you guys live like that. I'm an inbox zero every day guy.

[00:24:22] **Adam:** I wish I could, I, I, I aspire to do that, but,

[00:24:26] **Tim:** Yeah. It's, it's a, it's a disease. So it's funny, my pool guy. So I, so I decided I'm not gonna clean my pool anymore 'cause I, I don't do it. Well, I, I, yeah. So

[00:24:36] anyway,

[00:24:37] **Adam:** you're gonna have your pool cleaned. It's not, your pool is gonna go uncleaned,

[00:24:40] **Tim:** my, my pool's gonna be cleaned by someone else 'cause I, I, I just can't deal with it anymore.

[00:24:44] And, and so. He was at my hou we were at a very, very bad, like there's a cell tower, like right next to our house. It's like, right. You can see it from the backyard.

[00:24:54] **Adam:** So you cook your dinner by just leaving a plate

[00:24:56] **Tim:** Exactly. A hundred percent. A hundred percent. Yep. The 5G cooks, my cooks my steak. but that means that we actually don't get any signal because it's like going over the top of our heads.

[00:25:07] Right. And so he, he's like trying to like, you know, communicate and send messages and he can't. I'm like, dude, I'll just give you my wifi password. I have like a, I have a split wifi system. I was like, I'll give you, I'll give you a password. And he can't, some reason he couldn't do it. He's like putting it in, putting it in.

[00:25:24] He keeps putting it in wrong. And so he is like, here you do it. He hands me his phone and so I put in the wifi password and then I, you know, it closes and then I see the rest of his screen. 'cause he unlocked it for me. And I look at his text messages. He has 226 unread text messages on his phone.

[00:25:41] **Ben:** dude, that's nothing. Yeah, I was gonna say he's, oh, it's only three digits.

[00:25:46] **Tim:** and I hand it to him and I'm like, I'm like, dude, I didn't look at your messages 'cause I respect your privacy, but how in the world do you have 226 unread messages? I can't live that way. I'm an inbox zero guy. He just laughed. He's like, ah, man, I, I, yeah, I, I can't, I can't

[00:26:02] **Adam:** Holy Ben.

[00:26:03] **Ben:** I got 1,235. I mean, you know, half of them I'm sure are one time codes from banks and random political ads that I've constantly unsubscribed from. So it's not like, but there are definitely a lot of people that I just, family chats and group chats

[00:26:21] **Adam:** I think the

[00:26:22] **Tim:** so for the listeners, he held up his phone, it was 1,235 unread text messages.

[00:26:29] **Adam:** difference for me is there's basically zero times ever. I will come back to a text message or need to come back to it. Right. Maybe occasionally, and I'll leave that one unread, but I'll need to come back to it within a couple of hours. Right? I can't, I can't handle what this person is saying to me right now 'cause I'm in, I'm on the phone or, or whatever.

[00:26:47] So I'll, I'll come back to it later. But other than that, like even if I see, if it's a, if it's somebody replying to me and they say, okay, and I see that in the notification tray, right? I swiped that away, but it's still marked as unread in the app. So I'll open the app and I'll just tap it open to get rid of it, to get rid of the notification.

[00:27:03] Like I, like I said, I aspire to be the inbox zero guy, but there's not a good way to be like, to, to add, go read this email that I received,you know, whatever such and such date. This was a subject or whatever to my to-do list. Right? If, if I could do that, I would probably do that. If I could like cross link between apps like that.

[00:27:22] **Tim:** so transition a little bit here from unread messages, so the productivity trap. Here's one thing I've noticed with ai.

## [00:27:31] Burnout Guilt and Background Processing

[00:27:43] **Tim:** I never in the past 15 years would work past, like, end of my day. My end of my day is like 5 30, 6 o'clock. I, I'm done. Right. I'm done. I'm unplugging.even during COVID, but since AI has been around, AI feels like my little buddy, my little Tamagotchi

[00:27:53] **Adam:** Yeah.

[00:27:53] It's, it's a, it's a slot machine. It's got that, like

[00:27:56] **Tim:** yeah. It's got that addictive kind of feeling. I'm like, I wanna see what this thing does, right. So I'll, I'll feed it and feed it and feed it all day and then the end of the day comes and I can't stop feeding it.

[00:28:07] **Adam:** mm-hmm.

[00:28:08] **Tim:** I wanna, I want to

[00:28:09] **Adam:** I do it on the weekends.

[00:28:10] **Tim:** yeah, I, I mean, there's been times in the past three months since AI has gotten so much better that I will be working on stuff for work at like 10 30, 11 30 at night, regularly every week.

[00:28:26] And it's, it's addictive. That's scary.

[00:28:31] **Adam:** Yeah.

[00:28:32] **Ben:** I at least am a very structured person, and I always have been. I've been very, I, I like to have my boundaries and I think it's the only way that I can manage to stay sane. And I think historically this is, so, this is interesting 'cause it's kind of a weird knock on effect of burnout because I, I'm definitely feeling very burnt out.

[00:28:51] Right now as we're speaking at the time of this recording, and historically I have always, this sounds terrible, but it's like I've justified working work hours because I always felt like when I was outside of work, my brain was just still going. I was thinking about web technologies, I was thinking about product development.

[00:29:13] I was thinking about all of the stuff that went into building this career and, and adding value to the companies that I worked for. So it always felt like even if I only worked during business hours, my brain was still sort of always working.and now that I'm feeling very burnt out, I get to the end of my day and, you know, my brain still does some stuff, but I'm like, I'm excited for the end of the day to go have dinner. Talk to my wife, watch television, go for a walk. it almost makes me feel guilty now. I mean, it's like this, like a house. This is like the, the, the sickness of it all is like, I feel guilty that I'm only working during business hours because I'm not having that sort of background process running all the time in my head, which is weird.

[00:30:05] **Adam:** Yeah.

[00:30:06] **Tim:** think? Do you think that's because you feel like the AI's doing that work for you?

[00:30:11] **Ben:** I, I think that's definitely, that's definitely part of it. Absolutely. I mean, it's not the only thing. I think there are, I, I think I've also just been feeling a lot more isolated lately. I feel like my sense of community is dissipating. And I think some of that is AI related. Some of that is just life choice related.

[00:30:34] Apparently moving farther away from cities makes you feel more isolated.who knew? You know? so I think there's a lot going on, but I think, I feel like maybe my brain was just more engaged in a continuous way. When I have less ai, the AI gives me more productivity, but it also gives my brain more downtime.

[00:30:58] In between the, even if it's just like I hit enter on Claude Code and now I'm waiting two and a half minutes for it to come back like that, two and a half minutes isn't enough for me to go do anything else. And I, I at least, you know, that's how I operate. I know that there's a lot of people who were like, oh, let me jump over to my other terminal to see what that agent is doing.

[00:31:16] Like I just, my brain doesn't operate at that level. So I have two and a half minutes where I'm just sort of staring at the screen and reflecting on life and it, it's, I don't like it. It makes me feel very uncomfortable. And I think that is definitely contributing to my sense of, of burnout. It's like I'm just waiting to hit enter, but it's not, it's not mentally lightweight.

[00:31:39] It's also the work itself is very cognitively demanding because the things that I'm trying to ask Claude or that Claude is asking for clarity on, I feel like. I'm having to think deep. And I think part of the problem too is I don't know how to keep that thought process in short cycles. You pre ai, I feel like I could think deeply, but I could keep it very scoped.

[00:32:05] You know, here's the one problem I'm thinking of, and let me marinate on that and let me write a little document or, or a Jira ticket and then I can work on it. But now it's like I'm thinking deeply about a, a small problem. And then Claude says, well, what about this? And I'm like, oh, that's, that's really interesting.

[00:32:20] Let's explore that for a second. And then like, suddenly I've gone like half an hour into this conversation with Claude and I forget what my original question even was. And like, and then I feel disorganized. I feel like I've wasted time. I feel like I'm not adding value because it's like I'm just like spray and pray a attempt at solving problems.

[00:32:42] I, I just don't have a good strategy yet. I'm feeling very. With the non-deterministic mode of it all. I feel very, I don't have the same tools that I used to have in terms of how to solve problems, and I'm still very much adapting and trying to figure out, and it's, and it's been very trying.

[00:33:02] **Tim:** I think everybody is, I, I, one thing I struggle with is like my impatience, my level of impatience. Like, I'll, I'll put something in and I'm like, you, I, I don't want, I, I maybe have two or three agents running at any given time. I, I want to see them finish and I, I don't wanna be there when they finish.

[00:33:22] So, recently, this past week, I, I installed Bark. So Bark is like a push notification kind of thing that works well on iPhone. And so I have, anytime Claude finishes something and it's idle for 60 seconds, it sends me a Bark message. What? That? And so what that allows me to do is like, just give me a break, right?

[00:33:46] So I will put it in, it could take 30 seconds, it could take five minutes, 10 minutes for Claude to finish. I have no clue. When it will. But with Bark, I can just walk away and go get a cup of coffee, drink a cup of tea, chat with my wife, check on the garden water. Some plants do whatever around the house, and then Bark will say, play a little musical note and

[00:34:11] **Adam:** It doesn't bark like a dog.

[00:34:13] **Tim:** now it plays like, like classical music for some reason.

[00:34:16] I don't know. That's weird. But anyway, it, it, it'll play a little notification on my, on my, and my, it will vibrate in my pocket and I'll go back into my office and check on what Claude did and go fix it. And so it's weird. I, I feel like we've gone from being like artists to being gardeners.

[00:34:35] **Adam:** Hmm.

[00:34:36] **Tim:** You know what I mean?

[00:34:37] Like artists like create stuff and they'll, they'll, they'll take a blank canvas and create it. That's kind of what the old school programmers were. And now we're kind of like, just, we're planting a seed and we have no clue what the seed's gonna grow into. And then we'll see what that seed does. The plant comes up and like, oh no, the spacing is too close.

[00:34:56] We'll clip, we'll clip a little, couple of seeds, little seedlings, like, so that spacing's better. And then we'll water it a little bit and then let it grow and then go, oh, wait a minute. This is completely wrong seed. We'll just like, dig the thing up and plan it. You know? That's kind of what I feel like we're, we're, we're shifting paradigms of what we're doing a as as an entire industry, and it's gonna make some people happy and make some people sad and some people different.

[00:35:24] **Adam:** Yeah, I wouldn't say that I'm particularly upset or thrilled with the changes to the way I'm working or, you know, what I'm getting done. I, I will say I've been getting more done it feels like, at least in terms of amount of work completed in a day, right? I think because of the changes I'm taking on bigger projects, right?

[00:35:45] Like this ORM code review or ORM migration thing is something that we've wanted to do for years and it's just been like, that's too big of a task, it'll never get done. Too bad, so sad sort of thing, right? Like, oh, well, and now it's like, well we, I'm at with it now is, you know, I've done the majority of the work.

[00:36:03] I've done a crap load of automated code reviews, and. Now it's just like, it's the last 90%, right? The first 90 percent's done. All that remains is the last 90%.

[00:36:13] **Tim:** Hard, hardest

[00:36:14] **Adam:** I'm at, yeah, I'm at that point now where I have to like, every day grind on it to make sure it doesn't just wither on the vine, right? and so I am, I'm pushing on it hard, right?

[00:36:25] I, I re-base on the main branch every day. I am working on it. So I found a bunch of, bugs and prod that I'm working on, getting the fixes landed, and then I'll rebase on that. And that should be a good baseline to like, okay, let's take this to qa, and see how it goes there. And also, it's just this week turns out to be a bad week.

[00:36:42] We're like onboarding a couple of new customers and one of 'em, not one of the new ones, but a different customer's having a, a giving day this week. It's just like not a good time to rock the boat. so, timing notwithstanding, I'm getting fairly close to moving on to the next phase and trying to shake out whatever underlying bugs are still, you know, hiding in the crevices here.

[00:37:04] yeah, all that to say, I'm just taking on big projects that I would never have even dreamed of doing before. And so now it's taking a long time. I don't know how many weeks I've been saying I'm almost there. I'm almost there here on the podcast. Um,but, I'm almost there and

[00:37:22] **Tim:** And, and that is hard. So we've had on our standup meetings, it's like, so our scrum master is like challenging. It's like, so when do you think you'll be done? And when you have, like, we have some tests, some things that are just basically a hundred percent Claude. Like you, you're just building unit tests or, you know, looking for, you know, knowable issues or, anyway.

[00:37:41] And, and one of our developers is like, he was, he was pushing him for like, when do you think he'll be done? I'm like, I have no clue when Claude will be done. I'm not doing this. I, I can't tell you. I'm like, he's, he's done 10 of them. But sometimes it takes longer, sometimes it takes less. So, but one thing I have gotten more productive is, is I've, I.

[00:38:02] I've been more communicative. So talking like basically, now that I've figured out how to connect Claude to Jira, it's like if I do some work for someone, someone's like, Hey Tim, can you do? I'm like, okay. I go in, do the changes, commits it, I'm like, go to ticket number 5, 5, 5, 3 and update what I did, and then I just walk away.

[00:38:25] And I love that 'cause now, 'cause before I'd be like, I would have to call them or talk to them or send them an email and I'll call just like, here's what, here's what he did, here's what you should expect, input in and put out, done. And so that, that's a big productivity gain. But it's like everyone now is putting Claude comments on their tickets

[00:38:44] **Adam:** I was just gonna say, I need to push back on that a

[00:38:45] little bit. 'cause

[00:38:46] **Tim:** and

[00:38:46] **Adam:** know it wasn't that long ago you were saying Yeah. You were saying, well, we're all just sending AI generated communication at each other.

[00:38:51] **Tim:** Yep. So, so, so it's like, Claude, it's just basically it's making yourself indispensable because we're not gonna be able to process all the comments that Claude generated. So you're gonna need Claude to understand all the comments that it generated so that you can get something done to understand what you need to do.

[00:39:10] **Adam:** It's a very well proven business strategy.

[00:39:13] **Tim:** yeah, a hundred percent. And then they're going up their prices by, you know, a thousand percent and we'll all be screwed. So,

[00:39:20] **Ben:** Yo, just one thing you said triggered me this idea of keeping up with Claude comments. So one of the workflows that we.

## [00:39:27] Claude Code Review Death Spirals

[00:39:27] **Ben:** we have at work is we push code to GitHub, and once it hits GitHub, there's a Claude Code Review bot that runs somewhere in Claude servers. And we get into these like death spirals, at least I do, where I write code. I try to review it as best I can locally, you know, asking Claude, Hey, do a deep review.

[00:39:51] Are there any edge cases I haven't considered or security issues that I've left open, et cetera. And it's, Claude says, yeah, of course. You know, it's all right. Fine, let's fix it. And then I push it to GitHub and GitHub review bot goes off for like 10, 15 minutes and it comes back with a whole bunch of things, says, here's all the stuff that you missed.

[00:40:10] So then I'll tell my local cla, Hey, look at the comments on this PR. There's a bunch of issues we need to fix. Come up with a plan to fix 'em and we'll review. And so it does that. It fixes it, and I push it back up to GitHub and then GitHub does the review again and comes back with even more issues. And I'm like, dude, you just are reviewing the fixes for the issues you just told yourself to fix.

[00:40:31] **Adam:** the one on GitHub, you, you're, it's like the built in Copilot thing. It's not Claude. Right.

[00:40:37] **Ben:** I'm not a hundred percent sure.

[00:40:39] **Adam:** we did experiment with the Copilot baked into GitHub for a little while and pretty quickly agreed as a team. It just turned off. 'cause it's like whatever, however it's set up, it's system prompt or whatever.

[00:40:51] It's like it won't quit until it finds 10 or 15 things to complain about. Right. It's almost like they've told it like every code has a, you know, all code has problems. It is impossible to pass a code review. Just like Yeah. 'cause exactly what you're describing, right. You'd, you'd get 15 things to fix, you'd go fix 15 of them and it would come back with like 12 more and you're like, where were these last time?

[00:41:14] **Ben:** Right, and it's, and it's, there is,there is something, okay, I can only speak for myself here, but I, I have a lot of trouble with the non-deterministic, black box, nature of the whole thing. And I think it's because I, there's, I don't know if it's a mental block, like I don't know if I'm holding myself back or if this is just the way that my brain works.

[00:41:37] Somehow not being able to see the parts makes me feel like I can never learn how to use it effectively. And I, and I almost wonder if this comes back a little bit to my aphantasia, which we've talked about on previous episodes, where it's like, I just don't visualize things in my head very well. And it's almost, it's almost like code has allowed me to externalize that visualization.

[00:42:00] 'cause I can see it on paper and I can figure through it much more easily. But now that this whole thought process is black boxed in and of itself, and I don't understand, like there's no, this called this, which called this and that's why this broke, or that's why this worked because that call stack isn't there anymore.

[00:42:19] Like I'm, I'm just, I'm really for whatever reason having a lot of a, a big struggle trying to figure out how to hold it right, so to speak. And, and then like the models are constantly changing and the level of effort I'm trying to use at the thinking level. I'm trying to tweak that. And then the CLAUDE.md is changing and I, I don't know, it's, I can't, like, Hmm, sorry.

[00:42:42] I, I, I, I lost, I lost my temper with Claude today 'cause it just started out of nowhere. I've had the same review process for weeks and I've always explicitly created my own branches. I've always explicitly pushed to GitHub. I mean, like, I've told Claude, you know, commit this or push it to GitHub and it's always waited for me to do something.

[00:43:02] And then all of a sudden today it just started willy-nilly making branches on its own with all kinds of random names and then just randomly committing stuff. And I'm like, what the f are you doing? And it says like, oh,

## [00:43:12] Claude Gaslighting and Alpha Code

[00:43:12] **Ben:** I didn't do that. You probably did it. I'm like, no, I didn't do it. Oh. And it's,

[00:43:19] **Tim:** Gaslighting

[00:43:19] **Ben:** yeah, and, and I don't know, I'm just,

[00:43:23] I

[00:43:23] **Adam:** I especially after they released 4.7, I feel like it was real quick to jump on trying to do more, than I asked it to do. Right? You ask it to fix a problem, it's like, okay, I fixed it. Now lemme commit it. Let me push it. Lemme create a pull request. Hey, stop.

[00:43:37] **Ben:** Yo, I will literally be in plan mode and I'll say, let's come up with a plan and it'll just start writing code. And I say, whoa, what the F are you doing? We're in plan mode. And it says, no, we exited plan mode before, and I'll take a screenshot of the terminal where it says plan mode at the bottom right below where it just responded.

[00:43:55] I'm like, then explain that. And he goes, oh my bad. You know? It's like, so and and like. That's even scary because that's the mechanic of the CLI itself.

[00:44:06] **Adam:** Yeah, that's the harness.

[00:44:07] **Tim:** That's how the, that's how the world ends. My bad. I launched all the nuclears.

[00:44:13] **Ben:** what about the dash dash dry run?

[00:44:18] **Adam:** Can I, can I, sorry, can I, I just wanna say one more thing,

[00:44:21] **Ben:** which is, okay. So I was listening to an interview the other day with this guy, Simon Willison, I think is his last name, and I think he's Wilson. So he is kind of a big deal in the AI community.

[00:44:31] **Adam:** we'll listen, I

[00:44:32] **Ben:** Willison. Yeah, I knew it was something I didn't quite understand.

[00:44:36] and he's really huge into all the code generation, and he was, in this interview, he was saying that he has taken to, publishing code and making sure that he puts the, he tags it with Alpha version. And he was saying that's, he's like, beta is like,I haven't looked at the code, but I've tried the, like I've ran it and it seems to work.

[00:45:01] Alpha is, I haven't looked at the code. And I've never even tried running it. And I thought to myself, then, why are you publishing that? Like, why are you publishing something you haven't even wanted to use yourself? And like, it, it made me so angry to hear that and I'm, you know, I'm probably not understanding exactly what he meant, but this idea that like, you're almost publishing code just for the sake of publishing code and it's not even a problem you're solving for yourself, let alone other people.

[00:45:29] Like that to me almost feels like the, just, it just made me so angry. And, all right. That's it. I just said my piece.

[00:45:41] **Adam:** Alright, well, why don't we call it there? I dunno about you guys. I'm kind of burned out on this topic.

[00:45:44] **Ben:** Yeah,

[00:45:46] well said.

[00:45:47] **Adam:** so, uh,

## [00:45:48] Patreon

[00:45:52] **Adam:** this episode of Working Code is brought to you by Prompt Fatigue and listeners like you. If you're enjoying a show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon

[00:45:58] Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them. Special thanks to our top patron, Monte. You rock man.

[00:46:07] Thanks for your long time support.

## [00:46:08] Thanks For Listening!

[00:46:10] **Adam:** We're gonna go record the after show, and we've got some stuff on the list here that I have absolutely no idea what it is. Fathom Events and argue Mint, which sounds, tasty and also like maybe it might mess with my budget. so we will figure out what that means.

[00:46:23] if you wanna get access to the after show, it's real easy. You go to patreon.com/workingcodepod, sign up, send us a few dollars every month, or a dozen or so dollars every year. and we'll send you the after show. You get all the old ones, all the new ones as they come out. You get early access and you get a nice gold badge in our Discord.

[00:46:39] **Tim:** And we get crazy on the after show,

[00:46:43] **Adam:** you thought talking about testicles on the main show was bad,

[00:46:46] **Tim:** right?

[00:46:47] **Adam:** anyway, join our Discord as well, workingcode.dev/discord. You'll get, special perks there as well for being a patron. but that's gonna do it for us this week. We'll catch you next week. And until then,

[00:46:57] **Tim:** Listeners, lemme live with you. You will never burn us out. Your heart matters.
