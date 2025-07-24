---
title: "224: Skin in the Game"
description: "In this week's podcast, the whole team is back to delve into the concept of 'skin in the game'."
date: 2025-07-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/224-skin-in-the-game/id1544142288?i=1000717686752"></iframe>

To be a good producer you have to be a good consumer. In this week's podcast, the whole team is back to delve into the concept of 'skin in the game' in product development and how consuming your own product, known as "dogfooding", and empathizing with users can influence the development process.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/2224-skin-in-the-game.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** cause skin of the game can mean different things to different people. Right? So skin of the game could be money.you know, for me, early my career, skin of the game was not getting yelled at by the customer. Right.

[00:00:12] **Tim:** You know, that was my skin of the game. So.

## [00:00:34] Intro

[00:00:34] **Carol:** Okay, here we go. It's show number 224. And on today's show we are going to talk about ai. No, just kidding. Um,Dear

[00:00:40] **Tim:** not ai,

[00:00:42] **Adam:** And on today's show, we're gonna talk about having skin in the game.

[00:00:44] **Tim:** and we don't mean only fans.

[00:00:47] **Adam:** well, you know, honestly, once you understand what this topic is about, I think Tim, you're, you're gonna be wrong there. I think that,

[00:00:56] **Tim:** I like being wrong.

[00:00:57] **Adam:** Okay. Anyway, uh, but first as usual, before I explain what any of that meant, uh, we're gonna go with our triumphs and fails.

[00:01:04] **Adam:** Tim, it's been a jumble. We've had a couple of two people episodes, but why don't we just have you go first, my friend.

## [00:01:09] Tim's Fail

[00:01:09] **Tim:** Yeah, man, today, today's was terrible. Tuesday today was a big bag of suck.

[00:01:17] **Ben:** Oh no.

[00:01:18] **Tim:** It was, it was a rough day. It was a rough, rough day. So we use Sendgrid for all of our email send outs, and we don't send a whole lot of emails. So we're like, we buy the $89 a month, uh, a hundred thousand emails a month tier. Right.

[00:01:35] **Tim:** And we never go past that.

[00:01:37] **Adam:** Mm-hmm.

[00:01:37] **Tim:** Well, Monday morning somehow 750,000 emails left using our credentials.

[00:01:46] **Adam:** Uh

[00:01:46] **Carol:** uh oh.

[00:01:47] **Tim:** And they were, and they were all about, uh, some sort of Bitcoin ledger

[00:01:51] **Ben:** Oh no, Tim.

[00:01:53] **Tim:** Yeah. Yeah. Now, fortunately, fortunately, Sendgrid caught on and they stopped it after it'd already sent seven 50,000. But it did bounce them all.

[00:02:04] **Tim:** Oh, no.

[00:02:05] **Tim:** but I do not know how our credentials got out into the wild. I, I I, so we had a similar thing happen with a w or AWS S3 buckets, and AWS had a, a leak, and we believe that's where that happened. And Twilio, who owns Plivo or not Twilio, who owns SendGrid, had a leak last year as well. And I think that's what happened. 'cause the only ones, the only keys that were existing were the ones that existed last year. None of the ones that have been created since that time, since that leak got hit.

[00:02:38] **Tim:** Of course, SendGrid doesn't admit to any of that. They, they just sent this long email saying, we've disabled your account. We take account, security very strongly, and, and you need to do these 50 things and we, you've gotta do an RCA to explain to us what you'd done to fix it. Well, I'm like, I don't think we did anything to, to jeopardize it.

[00:02:57] **Tim:** And the first one, I think you need to send me an RCA, but they're not gonna do that. So I don't wanna talk about ai. But ai I told this all to GPT, it generated me a very nice PDF that explained it and I uploaded it as evidence. But we did go through, you rotated all our keys, deleted the old ones, created new ones.

[00:03:14] **Tim:** Of course, we have to go through and find all the systems. Where are these at? So the whole morning, I'm quarter, I'm quarterbacking, you know, I got everyone in a group call and we were texting you in a create spreadsheet, and we finally get everything buttoned down around noon. And of course they're not gonna give us, you know, we went from paying $89 a month to now this month we have to pay like 750 bucks or something like that.

[00:03:34] **Tim:** which I mean, it's not a huge amount of money, but, you know, it still is annoying.as immediately when we get done with that, our pa our biggest payment provider went down.

[00:03:44] **Ben:** Oh

[00:03:44] **Tim:** Now they blamed it on an upstream off network. Right? So there's nothing I can do about that other than like, I generated an email that says, Hey, there's what's going on?

[00:03:53] **Tim:** No, ETA. Of course, when you say no, ETA, no one believes you. They just keep emailing you. Is it fixed yet? Is it fixed yet? When's it gonna be fixed? I told you there's no ETAI have no control. All I, all I do is send an email and wait for someone to

[00:04:04] **Adam:** said that was, that was today. That

[00:04:06] **Tim:** that was Yeah. This afternoon. Yeah. For about, so for about three and a half hours, we didn't get any payment processing volume come through.

[00:04:12] **Tim:** They all just died.'cause nothing would authorize, and I don't, IS.

[00:04:18] **Ben:** with payment stuff, you can't just queue it up and process it later. 'cause all these tokens and stuff

[00:04:23] **Tim:** right? Yeah. Yeah. Because we don't store the card information and you don't wanna do that because when a person, what's the natural human thing to do? You go through your payment, right? It says, yeah, you hit, you go, oh, my payment didn't go through. They either like, get a different card out or just retry the same card.

[00:04:37] **Tim:** So they may have tried three or four times, you don't wanna process that. Now they're, you know, and they're paying for home insurance or whatever. It's like a thousand dollars. So you do, you know, spend four or $5,000 on your card. You don't want that. So, yeah. And so finally, you know, later in the afternoon, he came back around and we emailed everyone, and then the inevitable question went, what was wrong?

[00:04:57] **Tim:** Well, I don't know. My payment provider doesn't know. And they're trying to get the information from the, from the, from the upstream off network who may or may not tell them. So. On top of that, my boss, she is traveling today, and so I have to take all, she runs the, the, the Silver V, silver Vine Company. I, I run Pay Cloud, but I assist her running Silver Vine and she's out.

[00:05:19] **Tim:** So when she's out, I have to take all her calls too. So I'm on the phone all day long with customers and developers and groups. We're doing our security reviews while all this time I'm sitting here trying to fix things and get stuff working. It was a stressful day, bad day, bad day.

[00:05:40] **Ben:** day. That sounds awful. Do you have a, um, one of those like public status pages that, that you're, do you have a support team? I, I.

[00:05:49] **Tim:** You look at, no, I'm kidding. No, we, we do, we do. we don't have a status. That's, you know, we really don't. That's, we should have one of those things, but at the end of the day, it's like,

[00:05:57] **Carol:** so helpful.

[00:05:59] **Tim:** It is helpful, but they also just call you and email you anyway going, Hey, I noticed your, I noticed your status page says this is down.

[00:06:06] **Tim:** Do you know? No, I don't know. I'm sorry. These things are, and, and then so one customer who's not even like, he's, they're a customer who's like on their way out. Like they've, they've already signed with another provider and they're moving everything off, but they're still somewhat with us. They send this like cheeky little email, Hey, do you guys ever like give refunds for all the hardship that you caused whenever you like, blah, blah, blah.

[00:06:29] **Tim:** And, and I didn't, I didn't even reply. I didn't even reply 'cause I was too hot at that time. I was too angry at the time.

[00:06:35] **Ben:** good for you.

[00:06:36] **Tim:** And, and my, my reply was like, when you guys screw up someone's insurance and don't pay a claim correctly, do you ever make up for it? I don't think so. I know you don't. I know you

[00:06:46] **Adam:** your whole business model.

[00:06:47] **Tim:** your whole business model, your whole business model is not to pay at people out whenever some stuff goes bad, even though that's what they're paying for. And then to kick me in the teeth. It is the hottest day of the year right now. I know I said that last time. It's even hotter. It was like 103 yesterday and, and 80% humidity.

[00:07:04] **Tim:** And of course the air is out again after less than four weeks of getting it fixed last time, it's out again. So,

[00:07:13] **Ben:** That is a terrible day, sir.

[00:07:14] **Tim:** it is a terrible, terrible Tuesday.

[00:07:17] **Carol:** Thank goodness you're not living in the Groundhog movie.

[00:07:20] **Tim:** Right?

[00:07:20] **Carol:** Yeah.

[00:07:21] **Tim:** Yeah. I don't wanna repeat this day over and over again. So that was me. Adam, please give us a triumph.

## [00:07:28] Adam's Triumphs and Fails

[00:07:28] **Adam:** Uh, well, I'll tell you what, I'll, I'll compromise. I'll give you a triumph that turns into a fail, that turns into a triumph that turns into a fail. Is that

[00:07:34] **Tim:** Ooh, a journey, baby. It's a journey.

[00:07:38] **Ben:** Take us on this

[00:07:39] **Adam:** So, so last week I talked about, I, I don't remember if this was my triumph or fail or if this was just something I mentioned earlier in the show, but I talked about, you know, the American guy just wants to buy his way out of every problem.

[00:07:50] **Adam:** And I was talking about some gym, gym equipment that I really was salivating over. And I finally decided to pull the trigger and buy it. Um, I, I spent a bunch of money. Basically the, the triumph is, I'm excited, you know, I bought a new piece of equipment, when I bought it, I, I bought it on Amazon and the, the estimated delivery, I think it was on Wednesday, it was either Tuesday or Wednesday when I bought it

[00:08:11] **Ben:** Oh wow. Because it's probably like a 300 pound piece of equipment or

[00:08:15] **Adam:** Uh, I believe the total is close to 600.

[00:08:18] **Ben:** Oh my goodness.

[00:08:19] **Carol:** Sounds like our stuff. Yeah.

[00:08:21] **Adam:** So, I I, I'm pretty sure I bought it on Tuesday or Thursday, and the estimated delivery was Wednesday or Thursday of this week. So basically like tomorrow or the day after, as we're recording, was the estimated delivery, which is fine because I wasn't gonna be, I bought it on, let's just say I bought it on Wednesday last week, Thursday last week my family went on a vacation.

[00:08:41] **Adam:** Uh, we, we drove three hours away to go to the beach and hang out for the weekend long weekend. Which is great. And I was like, okay, cool. No problem. We won't be here for the weekend anyway. That'll make it easier for me to not, constantly watch the tracking and be like, come on, get here early, whatever.

[00:08:54] **Adam:** Right. and then here comes the first fail, as like, I think as we're waking up the next morning, Thursday morning, no, Friday morning I get an email. Your package is out for delivery. I'm like, you sons of like thank you Amazon for shipping it fast, but also you jerks like,

[00:09:15] **Ben:** Oh, that's, that's lame.

[00:09:17] **Adam:** yeah. So, and this is an expensive 600 ish pound, package.

[00:09:22] **Adam:** Now I knew it was coming in like separate packages, which was like three packages, but still heavy, big, bulky stuff arriving. And I'm gone for like the next three or four days. and I, you know, it could be weather. I didn't want it stolen any of that stuff. So I'm like. Kind of, I mean, I knew what I was gonna do, but I was, I was frustrated.

[00:09:40] **Adam:** Not

[00:09:40] **Tim:** It's gonna take some effort to steal a 600 pound piece of equipment, unless it's Ben, he just be. It up

[00:09:45] **Adam:** yeah.

[00:09:46] **Carol:** With his

[00:09:46] **Ben:** No, these things are, these things are so unwieldy when they come.

[00:09:49] **Carol:** Mm-hmm.

[00:09:50] **Adam:** Yeah. So I texted my neighbor, thank, fortunately, my next door neighbor, we have a pretty good relationship. And I was like, look, I, I'm really sorry to do this to you. It's coming earlier than they said it would. It's gonna be heavy, it's gonna be big and bulky. But fortunately because it's heavy and big and bulky, probably what's gonna happen is the FedEx truck is just gonna back up into my driveway and drop it right in front of the garage.

[00:10:07] **Adam:** Here's the code to my garage. You could just put the go, put the door up, drag it inside the door, and shut the door. That would be amazing. And he's like, yeah, sure, no problem. And, and he did that. So that was, there we go. Now we're back to triumph. Right. My neighbor was awesome. Did me this favor, brought it into my garage.

[00:10:21] **Adam:** Yeah. I didn't have to worry about it while I was gone. So the fail is, that was, you know, he brought it into my garage, I think it was Friday.

[00:10:27] **Tim:** and then Rob you.

[00:10:31] **Adam:** and I can't, I can't figure out where he lives to go get my stuff back. And, so it, it, it is, it was three boxes. I'm pretty sure each one of them was over a hundred, 150 pounds.

[00:10:41] **Adam:** So we're, we're up in the neighborhood of 500 to 600 pounds total. All of them big and bulky. So I had to get my wife to help me carry 'em down in the basement and doing all this. Man, it is a lot of work to put a piece of gym equipment like this

[00:10:53] **Carol:** Sure is.

[00:10:54] **Adam:** some of the reviews, the people were like, oh yeah, I got it done in about 90 minutes.

[00:10:57] **Adam:** And maybe that's possible if you just like, if you're just kind of winging it. Me, I, I'm not the type of person that usually like, is crazy about reading the instructions, but with something this big and this expensive, like I did open all the boxes, which was a chore looking for the manual. 'cause I was like, okay, well you gotta do, you gotta do the inventory all the parts, make sure you're not missing any screws or bolts or anything like that.

[00:11:17] **Adam:** 'cause you don't, you don't wanna get three quarters of the way through assembly and find out you're missing some crucial piece. So I did the full inventory of everything before I sent it back or, or before I started assembling it. And, fortunately everything was there. So I'm, uh, I mean, this is spread out across, I think, three or four different days now.

[00:11:36] **Adam:** I'm about two hours-ish of time invested in, assembling this thing. And I, I mean, it's barely vertical. Like, I've got a bunch of different pieces of, of square tube bolted together and it, but it lays flat on the floor. It hasn't even like started to ascend yet. and so I'm, it's just, it's taking time.

[00:11:53] **Ben:** So basically my approach, since I don't really have a whole lot of other time to work on this, is like, instead of my leg day workouts, I'm doing leg day build a workout machine. Nice.

[00:12:05] **Adam:** yeah, my, my basement is in shambles. It's covered with boxes and plastic wrapping and cardboard and, uh, like it's littered with just pieces of this machine all spread out.

[00:12:14] **Adam:** I had to go buy two new horse stall mats from Tractor Supply to put a nice rubber footing

[00:12:21] **Ben:** Oh, how, how are those? Because I've heard that those are really great because they're not squishy, but they're protect the, the floor. But I've, I've also heard that they, the, uh, not, what is it? Not aate, what's the, um, yes. That the offgassing can be pretty intense.

[00:12:36] **Adam:** yeah, I mean the, I have three that I bought when I first got my squat rack, and I would say they did off gas for maybe a week. And it was a, it wasn't, I wouldn't describe it as intense, but it was like bordering on unpleasant,

[00:12:47] **Ben:** Okay. But it, But it, but it, passes,

[00:12:50] **Adam:** it was tolerable. Yeah. And then, you know, a week or two later it was gone.

[00:12:53] **Adam:** And these new ones, I, they smell a little bit like rubber, but it hasn't been like bad and I'm sure that that too will pass. So,

[00:13:00] **Ben:** you know,

[00:13:01] **Carol:** if it's different if they're exposed to like direct sunlight versus in your basement.

[00:13:05] **Adam:** yeah, I don't know. They were, when I went to pick 'em up today, they were like sitting out in front of the store on a pallet, just like a couple of chains wrapped around them so that you couldn't, because these things too are heavy, man. They're not a hundred pounds, but they gotta be close. It's four foot by six foot of like inch thick rubber.

[00:13:19] **Adam:** So,

[00:13:20] **Ben:** The other challenging thing about fitness equipment in my experience is it's not like, like Ikea furniture where it's almost impossible to put things in the wrong way. Fitness equipment. It's just a lot of these square tubes with, with random holes drilled into the sides and it's very easy to put something in the wrong way and not realize till you have like four pieces that now need to connect, you're like, ah, hold on the wrong side.

[00:13:47] **Carol:** when we assembled our rack, I had no idea that it could go backwards until we tried putting it together and it no longer fit and we had to disassemble everything. And Steve was furious. So we stopped that night and tried again the next day.

[00:14:00] **Adam:** yep.

[00:14:01] **Carol:** Yeah. He's like, I'm reading the instructions this time.

[00:14:03] **Carol:** I'm like, someone should have, 'cause I did it. Mm-hmm.

[00:14:07] **Adam:** old age, I'm starting to become an instruction reader.

[00:14:10] **Carol:** Yeah.

[00:14:10] **Ben:** yeah. You have to, like, I double check where the holes are and I'm like holding the, the, the instruction pamphlet in one hand and the piece in the other hand, I'm like back and forth, back and forth. I'm like, is that the right hole? Is

[00:14:23] **Adam:** yeah. Do I have it facing the right direction? Right. I like, I can just see myself putting on something backwards and then, and then not realizing until two days later and having to like disassemble half the machine. So that's my rollercoaster of a triumph and fail and triumph and fail. What do you got going on, Ben?

[00:14:40] **Tim:** I'm exhausted. That was a journey.

[00:14:42] **Adam:** Yeah,

[00:14:43] **Carol:** I think we just call it there guys.

[00:14:44] **Tim:** we're done. That's, that's enough drama for one day.

## [00:14:48] Ben's Fail

[00:14:48] **Ben:** Uh, well, I'll go with a, with a small fail on a similar topic, which is just that I have not worked out in like two weeks and it's, it's, I just feel dumpy and awful. And it's just a lot of things have come up during the week. I think, like Adam, I work out sort of during my lunch break, but

[00:15:07] **Carol:** that.

[00:15:07] **Ben:** if I have personal things that come up like a, like a, I have to make a call to the accountant or something, or I have to deal with my family or like, we've taken the dog to the vet a bunch of times recently, which I can talk about that in the after show.

[00:15:21] **Ben:** it's like, then I can't take two lunch breaks.so I just, and then I've, it's, so that's been

[00:15:28] **Carol:** It spirals.

[00:15:29] **Ben:** Yeah, it is. And then at some point you're just, even when you do have a day where nothing's interrupting you, you just, I'm like, oh, I just gotta get out of this damn house for a minute and go walk around.

[00:15:40] **Ben:** I feel you, Ben. I, I have not worked out since 1989.

[00:15:45] **Ben:** One of these days, it's gonna catch up with you,

[00:15:47] **Carol:** Mm-hmm.

[00:15:47] **Adam:** I knew that was coming.

[00:15:49] **Ben:** as a, as a, as a small triumph to even out this small fail. I, I was using chat GPT over the last couple of

[00:15:58] **Carol:** No ai. No AI

[00:15:59] **Ben:** no, no, no, this is, but this, this is, you know, minor, minor. Um,it, it was getting just a bunch of stuff wrong about custom tags, cold fusion, custom tags, like fundamentally wrong about just the mechanics of it.

[00:16:12] **Adam:** Get the hint, Ben.

[00:16:13] **Carol:** Stop writing. Cold fusion.

[00:16:15] **Tim:** like a, like a typical cold fusion developer.

[00:16:18] **Carol:** Oh, well that

[00:16:20] **Ben:** I, I asked, I said, look, I'm not asking for an apology, but I am curious as to why you're making fundamental mistakes about the mechanics of custom tags, considering that this was all very clearly documented. On the co vision documentation. And it gave me, actually, and this is the triumph, is that it just gave me a very, I thought, well thought through coherent answer as to why it gets these things wrong.

[00:16:43] **Ben:** And it was basically like, it doesn't really use the documentation the way a person would use the documentation the way it said it is, like, uh, it makes all of these analogies in its

[00:16:55] **Adam:** Sprain.

[00:16:56] **Adam:** yeah. I was gonna say, I was gonna say head, but you know, we always,Anthropomorphize.

[00:17:00] **Ben:** thank you. That's exactly what I was trying to

[00:17:02] **Carol:** Is such big words.

[00:17:04] **Ben:** So it was, it was saying that it was trying to equate the CF module tag as a concept of modularity to the JavaScript modular system,

[00:17:13] **Carol:** Mm.

[00:17:13] **Ben:** which is totally different in how it works. And then it would try to sort of fill in the gaps in the mis the misalignment in feature set. And it just sort of takes guesses and makes a lot of mistakes.

[00:17:25] **Ben:** And like it was very upfront about that. It was like, look, it's not documentation, it's. Me just sort of guessing based on patterns.

[00:17:33] **Tim:** So you're here to, could generate like an LLMs txt for cold fusion stuff. Like I wouldn't need it or use it, but,

[00:17:40] **Tim:** so you heard it here first guys, ColdFusion makes no sense. Not even a super intelligent AI can figure it out.

[00:17:47] **Ben:** Well, I mean, that's the interesting thing. You know, so Adam's saying he's at an age now where he just likes to read instruction manuals because you get better results.

[00:17:55] **Ben:** I don't know if I included the word

[00:17:56] **Ben:** like,

[00:17:57] **Carol:** uh.You

[00:17:59] **Ben:** you know, they, they talk about, about these things operating like junior developers. But I think that's one of the advantages of being a human is you can just sit down and go through documentation and the, and the, the large language models don't really do that.

[00:18:14] **Ben:** Like, that's not even the way they would start to approach the problem it seems.

[00:18:18] **Carol:** Yeah.

[00:18:19] **Tim:** Of course it could have been a hallucinating, why it was wrong, because it makes no sense to me. If it could scrape the doc, the manual, it should know the manual.

[00:18:28] **Ben:** Right. That's right. And, and, and I think, I think why I'm categorizing this as a triumph is that I get so angry at chat, GPT and the triumph is that it's very clear to me why I get angry because it's like, it, it's so different than the anthropomorphization that I have in my head. Anyway, Carol, bring us home.

[00:18:49] **Ben:** What do you got?

## [00:18:50] Carol's Fail and Triumph

[00:18:50] **Carol:** Yeah, I'm gonna go with a failure first. I was out last week because of work, so I missed my opportunity to go first on triumph and failures. Now I have to wait four weeks. So, yeah. Uh, and then work is, um, work's being a challenge right now. Um, I feel like I'm doing my best to gracefully fail, but I'm finding myself just stuck a lot.

[00:19:11] **Carol:** And when I mean stuck, there are areas of the system, I don't know, I never knew I never touched, but now the people that supported it are gone. So when I get a message from support that says, this tenant has a failure on this acronym that I've never heard of before, I have to figure out acronym. I have to figure out new application, new process, how it's working, and then start digging through logs.

[00:19:35] **Carol:** So it's just kind of been a struggle lately. I will say the graceful part for me is that I look for every opportunity to make it better. so like for example, today I'm digging through some logs and I find that the application was written a really long time ago. This piece of it was, and whoever created some of it didn't understand log types.

[00:19:55] **Carol:** So. The error logs are all of like your trace logs. So I am digging through error logs, justifying certs, were read, certificates were found, thumbprints match, and I'm going, why are all of these errors? Like, why are these errors? So I'm digging through thinking there are problems only to find out that someone just didn't handle logging correctly.

[00:20:19] **Carol:** So I am going behind and I've already put in a PR or I have to code up for a PR in the morning to get those fixed. So when it fails again, the next person who has to look at this won't spend so much time tracing down the errors. This should have just been debug or trace or information, not something you put into an error log.

[00:20:37] **Ben:** Yo, this, this hits so close to home, because this was such a huge issue for us when I was working at Envision. I don't know who had started this pattern, but especially on the teams that were building node JS services. Oh my

[00:20:53] **Adam:** the finger at JavaScript

[00:20:54] **Ben:** I, I've, it's like every single function that could be invoked had a, a trace at the beginning that said like, such and such function about to start.

[00:21:05] **Ben:** And then at the end, such and such function about to end. And it was just gigabytes upon gigabytes of logs coming out of these things because no one had ever changed the environment variable to be nont trace. Or even if they did like it didn't actually read the right variable. Oh my God. Ah,

[00:21:23] **Adam:** that's, yeah, that's.

[00:21:25] **Ben:** awful.

[00:21:26] **Carol:** is so slow, nothing's reading, and you don't know why, and you go find out. It's 'cause of these trace logs that are still being created. Yeah.

[00:21:32] **Ben:** Oh man. Oh man. And then the, the most infuriating thing is that we would have some applications where people would have this bonkers amount of tracing, actively spewing logs, and you spend. Hours trying to trace down a bug despite all of this logging and you finally locate it and it's in some try-catch and in the catch.

[00:21:55] **Ben:** There's no logging whatsoever. And you son of a beaver.

[00:22:01] **Carol:** that

[00:22:01] **Ben:** Oh,

[00:22:03] **Tim:** Son of a beaver.

[00:22:04] **Carol:** I was even like digging through things that could have possibly been errors. Like, 'cause I didn't know, didn't know what was errors and what should have been like just information at this point. And so many of them are logging the exact same thing that I don't know which piece it called from, because it just says like, the message is send failed.

[00:22:23] **Carol:** I'm like, well, where did it come from? Like every one of these are called like doing the exact same log. So even if I wanted to go find it, I wouldn't know which piece of it actually executed unless I had a stack trace. And most of them didn't have Stack Trace because guess what? There were no errors.

[00:22:38] **Ben:** oh my God. I'm having so much PTSD right now

[00:22:41] **Carol:** know. I,

[00:22:42] **Ben:** because I can't tell you. Yeah, I can't tell you how many try-catch. Again in the node services and I don't know what it was about the node developers where there'd be a try-catch, the error is in the catch and then they would have a log, but then the log has just failed to perform operation, but they didn't actually log the error.

[00:23:03] **Carol:** Oh gosh. Yeah. That one hurts too.

[00:23:06] **Ben:** Oh my God. Yo. Okay, so I know we don't wanna talk about ai, but it just strikes me that Carol's story here feels so analogous to having AI generate code. If I can reframe what Carol said though, this is what I heard, is

[00:23:23] **Carol:** like marriage counseling right now, Ben. Okay. Let's talk. Repeat

[00:23:27] **Ben:** me reflect back to you what I think I heard.

[00:23:29] **Carol:** What did you hear me say?

[00:23:31] **Ben:** I believe what Carol said was, or what she implied was in areas of an application that she has actively worked on. Her ability to understand and debug it is greatly amplified when compared to a part of the application that she has never touched and doesn't fully understand how it works.

[00:23:49] **Ben:** And now debugging becomes greatly degraded. And like, how different is that from AI spitting out a bunch of code and it generates 15 files and you didn't write that, but now you are responsible for making sure that it runs properly?that feels like it's exactly the same thing to me. And, and I don't know, I, so I have, I had an analogy in my head the other day where if I, I'm a, I'm a big copy paste developer.

[00:24:15] **Ben:** If I, if I'm building a new feature that's kind of like an older feature, but different, I'll just

[00:24:20] **Ben:** copy the old feature.

[00:24:21] **Adam:** and.

[00:24:23] **Ben:** I'll just copy the old feature, paste it, and then modify. So just to, to make it concrete. If I have a file and has a thousand lines and I need to create a duplicate of it, that's slightly different.

[00:24:36] **Ben:** I'll copy that, a thousand lines, paste it and let's say change five lines of it. So the liability that I have of knowing

[00:24:43] **Tim:** Bob Weeps.

[00:24:45] **Ben:** the, the, the liability of that code is really the five lines that I changed because the fact that I copied it from an existing working part of the application means that the other 995 lines are more likely to work than not.

[00:24:58] **Ben:** But if instead of copy pasting, I say, Hey, ai, look at this other feature and make a new feature based on it, and it spits out a thousand lines. I feel like I have to double check all thousand lines, not just the five that it modified, because I have no idea what rande

[00:25:14] **Adam:** a reusable function that allows me to change this about it.

[00:25:18] **Ben:** yeah. So it's, it's, it's, having feelings.

[00:25:21] **Ben:** I just have a lot of feelings. Okay.

[00:25:23] **Adam:** You don't say,

[00:25:25] **Ben:** I've, Tim's been telling me that it's my fault, so.

[00:25:28] **Tim:** It. Oh. Oh. Thanks for, okay. He alright. You, you opened the door. I was not, I was not gonna bring it up on the podcast, but, okay. Audience. Audience. I. Pull back the curtain a little bit on the podcast here. Right? So every time when we try to schedule a podcast, Ben's like, can we do it at six 30? Let's let's have a short one.

[00:25:48] **Tim:** I'm down for a short one because, you know I'm tired. 'cause he likes to go to bed early. He's an old man. He goes to bed early. And, and so we had a small, very small sample size. So we had two weeks was only two people on the show first. Me and Adam. Right? And then Adam and Ben. Adam is the common denominator.

[00:26:04] **Tim:** Our show was a half hour. You and me

[00:26:05] **Ben:** the control group.

[00:26:07] **Adam:** yeah.

[00:26:08] **Tim:** He's the control group. Half hour. How long was your show, Ben? How long was your show?

[00:26:14] **Ben:** I think it was like an hour and 15 minutes.

[00:26:16] **Tim:** Hour and 15 minutes. So do not,

[00:26:18] **Adam:** the after show.

[00:26:19] **Tim:** so, so whenever you complain, our shows go too long and you wanna go to bed, understand you sir, are the problem.

[00:26:28] **Carol:** Hey,

[00:26:28] **Tim:** I love you, but you're the problems.

[00:26:30] **Carol:** Hey, Ben. I think you and Tim need to go to marriage counseling. Yeah.

[00:26:35] **Ben:** Tim, here's what I hear you saying.

[00:26:40] **Adam:** So, uh, as we were doing Carol's fail there, you have anything else to add, Carol?

[00:26:47] **Carol:** Oh no, no. I will gracefully fail. I will keep failing and we'll get to it one day.

[00:26:54] **Adam:** Okay, well then,

[00:26:56] **Tim:** on not the problem.

[00:26:57] **Carol:** Thank you.

[00:26:58] **Tim:** You're the solution.

[00:26:59] **Carol:** that. I try. I try to be a good solution.

[00:27:02] **Adam:** my daughter said it to her, I try not to be part of the problem. I try to be the whole problem.

[00:27:06] **Carol:** Oh, I love that.

[00:27:08] **Adam:** an

## [00:27:08] Main Topic: Skin in the Game

[00:27:16] **Adam:** yway, uh, skin in the game. That's our topic of discussion for today, uh, unless somebody side tangents us into ai. so basically, Ben, do you want to kind of like tell us what your, how what this, damn it words are hard.

[00:27:23] **Adam:** Ben, do you want to tell us kind of what made you think of this topic or, or why you wanted to discuss this?

[00:27:28] **Ben:** Yeah, absolutely. So one of the podcasts I listen to a lot, which I'm sure I've brought up many times, is the Ezra Klein podcast. He's a New York Times columnist and a book author. And I, I think just one of the sharpest minds that we have in, in journalism today. Just, just a brilliant on his off like, anyway, just brilliant guy.

[00:27:50] **Ben:** And the other day he was interviewing Chris Hayes, who I think is like an M-S-N-B-C news correspondent. Yeah.

[00:27:58] **Adam:** and also he has a podcast as well.

[00:28:01] **Ben:** Oh.

[00:28:02] **Adam:** called, why is this Happening?

[00:28:03] **Ben:** Oh, okay. I didn't know that. I should check that out. Um, so he, he also wrote a book recently, I think it's called The Sirens Call, and it's about the attention economy, basically how we're affected by social media. And, um, one of the things that they talked about on the show was for those who are not in the New York metropolitan area, there was a, uh, democratic mayoral primary just recently, and the kind of underdog, I guess you could call it, a guy named Ani.

[00:28:33] **Ben:** I, I don't live in New York City, so these names aren't top of mind for me. he ended up winning the primary over Andrew Cuomo, who was the former governor of New York, and they were talking about it on the Ezra Klein POSCO podcast about why this guy did so well. And a huge part of why he did so well was his social media game was just really on point.

[00:28:52] **Ben:** He was in the streets. Talking to people as they're coming outta stores, as they're walking down the street asking them about what their problems are, what is the kind of stuff that they want to see fixed, you know, where their biggest pain points are. Really listening to people and not just talking at them, which is what I think a lot of people feel is what politicians do.

[00:29:12] **Ben:** And so the conversations steered towards the Democratic Congress and why Democrats just seem to be so terrible at producing social media. They, they called out a bunch of very specific examples of where a Democrat could have had a really compelling social media story. And the things that they come up with are just trash.

[00:29:35] **Ben:** And they're saying like, it boggles the mind because these people all have a lot of money and they could just hire people to help them think up and create and produce these videos, and they don't do it. And Chris Hayes in the interviews said that in order to be a good producer, you have to be a consumer. His point was that none of these Democrats are real consumers of social media. Like the average age of these people is like, you know, a thousand.

[00:30:03] **Adam:** 112.

[00:30:03] **Ben:** Yeah. And it was interesting to me because I was thinking about it from the lens of product development and I worked at a company where we, the, the product was rolled out of a consulting agency that I had worked at.

[00:30:19] **Ben:** So it was, it was us actually scratching our own itch. So we were solving a problem that we knew how to solve because it was a problem that we were experiencing directly. And this whole, you can't be a producer unless you're a consumer. Kind of, it underscored this question that I've had in my mind, which is that, can I build a successful product if it's not a, if it's not solving a pain point that I truly understand. So that's where this idea of having skin in the game is, can I, can I build something? Can one build something when they don't really have skin in the game when they're just sort of a hired gun? Can you have that sense, that horse sense, if you will, to borrow from What about Bob? To, to build something just truly successful.

[00:31:08] **Adam:** this is where we turn it into the OnlyFans discussion.in order to produce good OnlyFans, you have to be a consumer of OnlyFans. And that's what I keep telling my wife.

[00:31:20] **Tim:** Oh God. Oh God.

[00:31:22] **Adam:** I'm just kidding.no. So, I find that that concept of, or the, the nugget of the discussion here really interesting because I'm on the other side of that and that is one of my biggest struggles, right? So my company, uh, we make software for the people in the alumni relations department, primarily at colleges and universities.

[00:31:45] **Adam:** They're the ones that are trying to continuously, I hate the word engage, but engage with, their alumni and their community after they've graduated. Like, keep them involved with the school, keep them. Informed of what's going on, like new stuff around campus or programs or interesting lecturers that are coming by, whatever, try to keep them involved with the community so that they will feel compelled to support the community with money and, and whatever other stuff they might have to offer.

[00:32:15] **Adam:** and I did go to college, but I mean, the colleges that I went to had basically zero school spirit. I, I didn't get really like any, yeah. Like I, I went, I made the mistake of going to one of my college football games, and I swear to God there was, you could have counted the number of people from our school that were there on like two hands and, and half of 'em were my group.

[00:32:40] **Adam:** and, so like we didn't have that. I, I didn't get like, I mean I got like federal loans and a very small grant. It was like a thousand dollars, which is not really gonna cover much for. College, but I got a little grant, got some federal loans and, and that sort of thing. So I, I never, I didn't have the background, that Steve, our founder and CEO brought with him to starting this company.

[00:33:04] **Adam:** Right. He, he got, some sort of support scholarship, something through his school, and he, they kinda leveraged that into getting him involved as an alum. Uh, and so he was on their like alumni board and he saw the, the alumni board, like volunteers and the staff struggling with different software and he's, you know, as a software developer himself, he was a consultant at the time.

[00:33:26] **Adam:** He would see them struggling with this stuff and like, just, it, it hurt, right. You know, you could see it's like, I, I, there's a better world. I could make it happen. And so he decided to make it happen. So he has a lot of insight and, and just kind of general knowledge that is really hard to transfer over.

[00:33:44] **Adam:** You can't just like, oh, hey, welcome to the company here, let me brain dump. 20 years of volunteering in this industry into your head. And so it, what you're describing, being an outsider and trying to build a successful product, there is what I do every day and I have some limited successes. Really. I think honestly, what works best for me or what would work best for me is to have like a counterpart, like a, a, a a partner within the organization, right?

[00:34:14] **Ben:** Somebody who still works at the school, but like, for whatever reason, they, they wanna work with me and help them, help me build the best product for them.on their side.

[00:34:24] **Adam:** Yeah.

[00:34:25] **Ben:** Uh, so if I could add another podcast that I like to listen to is from

[00:34:31] **Adam:** is the podcast about other people's

[00:34:32] **Ben:** yeah.

[00:34:33] **Adam:** by

[00:34:33] **Carol:** Yeah. Yeah. Every, every episode.

[00:34:35] **Ben:** More podcast recommendations per podcast episode.is the Basecamp podcast with, uh, David Meyer Hanson and Jason Freed. And one of the things that Jason Freed has brought up a bunch of times on his podcast is, is that data that, that ultimately, at the end of the day, all leadership is making decisions based on their intuition.

[00:34:59] **Ben:** And that when you have data, really all that is, is more evidence to help guide your intuition. But ultimately, no one's making decisions based on the data. They're making it based on their intuitions, which may or may not be colored by the data. And I think if we can, let's just accept for, for a moment, for sake of discussion that that's true because I, I get it.

[00:35:20] **Ben:** I like my, like my tum I, that, that feels right. So if, if you, if you take that for truth. Then this idea that even if you were to wire every interaction into an Amplitude dashboard and you're seeing all of the buttons that people click and you're seeing all of the subject lines that convert the best, at the end of the day, all that is, is data.

[00:35:43] **Ben:** And if it's not feeding into a larger intuition machine, that is the, you know, your way of thinking about that particular product. Like the it is, it is, it's just limited in how far data alone can bring you. as, as much as I feel like, ah, you know, I love listening to customers and I like hearing those little things, those paint points that they talk about, I wonder in myself how much of hearing those little pain points and understanding and recognizing that they're actually interesting is actually them echoing something that connects in me that I can understand, but I can understand it because it's, it's something that I just get at an intuitive.

[00:36:27] **Adam:** Yeah, the, the challenging, the biggest challenge that I have, you know, I've got those people, I've got a, a handful of people that I think of that are like my champions within different universities, and the challenge with all of them is developing a shared vocabulary, right? Because they know what they need, they know what they want, they, they understand what frustrates them.

[00:36:46] **Adam:** And getting them to communicate that to me in a way that makes sense to me about what I can do to make their life better, right? Like, if we could just establish that vocabulary and have those conversations, then I could build the things that make your life better and, uh, you know, make you more productive.

[00:37:02] **Adam:** Get your organization more money, then that's success. But that's, that's, that's the hard part.

[00:37:09] **Carol:** So like these are all great for if you're talking about people who work for a small company or for a software that they actually can invest in. So say like they can have stocks and if the company does well, then their money investment improves, right? So they can have skin in the game. So what do you do for people like me who my skin in the game is like providing a service for the, like people who are trying to hire other like federal employees.

[00:37:39] **Carol:** Like my only skin in the game is does the application work. Like I don't really have anything I can invest, I don't have anything I can get out of it. It's just cannot do a good job.

[00:37:49] **Ben:** Does Tim have something to say?

[00:37:51] **Tim:** I do. That's, that is an excellent question, Carol. 'cause I was thinking of the same thing. 'cause skin of the game can mean different things to different people. Right? So skin of the game could be money.you know, for me, early my career, skin of the game was not getting yelled at by the customer. Right.

[00:38:08] **Tim:** You know, that was my skin of the game. So. I, I think you need to figure out what is your stake in, in the game and the game being, we're developing a software that solves a problem, you know, what are you looking to get out of it? And I'm sure you remember, Carol, when you worked over here with, with Constellation, one of the things they said is that you need to really have not just your managers and your, your directors and everything, go visit customers, but have developers go and have them actually watch how your product is being utilized within the organization to see what those people's daily struggles are and that sort, that sort of builds an empathetic skin in the game.

[00:38:48] **Tim:** Now, to your point, I don't know, as a government entity, you can like, Hey, I'm gonna go OPM, we're gonna go see how we're, yeah. Okay. Yeah. Oh good. Well, I mean, so that sort of builds skin in the game because whenever, I mean. Hopefully, unless you're a complete sociopath, you have a, a bit of empathy, right? And you go see how people are using your product and you just, you see things that say that tell you like, oh, I never realized how my lack of delivering this product feature or doing it in such this way has created so much friction in this person's life.

[00:39:20] **Tim:** I wanna make it better for them. And then when they, you see the results of that, hopefully for you, that's some skin in the game.

[00:39:27] **Carol:** I was gonna say, like my personal thing is my name, right? Like I want people to always say like, if you've worked with me, like I've done the best I could for you, and that that's my skin in the game. Like I want to have the reputation that that shows I foster like ownership of the application.

[00:39:42] **Carol:** Even though I don't own it, I can't make the ultimate decision. I can just push for the right decisions, and I just want people to always know I've done my best. Like that's my skin, you know?

## [00:39:51] Eating Your Own Dog Food

[00:39:51] **Adam:** I think we've kind of. Straight away from the core concept here, which is because of the phrasing, right? So we said skin in the game. But I think really what it comes back to is you, in order to be a good producer, you have to be a consumer. And which in, in our industry, you might have to say, or you might hear people say, you have to eat your own dog food, right?

[00:40:09] **Adam:** You have to know how it tastes so that you can tweak how it tastes. 'cause you're making it right. If you use your own API so that you can make the API better sort of thing. So, Carol, to go back to answer your question from my perspective of, of, uh, you know, what would make good, producer, consumer skin in the game for you, you are occasionally, somebody who hires people.

[00:40:34] **Adam:** You and you, I imagine have used tools to go through that process. And so that's what you should be thinking about, right? Using those tools,

[00:40:43] **Carol:** yeah.

[00:40:43] **Adam:** you're building tools for hiring. So you gotta think about using tools for hiring

[00:40:47] **Carol:** True. I mean, I definitely have went through that in the past.

[00:40:50] **Adam:** yeah. So for me, like I can't, I could just call people and say, Hey, gimme money, but that's, uh, that's not gonna help me build better software.

[00:40:59] **Adam:** So, yeah.

[00:41:01] **Tim:** For me, for, so like for the pay cloud hat that I wear. I pay for things online all the time, and I realize what frustrates me, right? I'm a consumer of that experience. And so when I see that our stuff isn't doing that, I'm like, okay, we need to fix that. The other one's harder. It's like, you know, I, and maybe change insurance every four years.

[00:41:21] **Ben:** right.

[00:41:21] **Tim:** I, you know, everyone's slightly different. And, and Geico's different from travelers. I just called an agent and said, Hey, gimme a quote. And then an agent says, okay, here's your policy, and then Geico, I do it online. but yeah, I don't really have a whole lot of opportunity to, to be a consumer of that process.

[00:41:39] **Ben:** just to bring it back to social media for a second, I, I am a terrible social media con, producer and consumer. Like I basically use social media to just. Publish my

[00:41:51] **Tim:** Flog your

[00:41:51] **Ben:** Yeah, basically that's it. And, and it, it, it tracks because when I consume social media, I hate it. I don't like almost anything about it.

[00:42:03] **Ben:** And I will occasionally go down a rabbit hole for even two minutes where I go. I go, I'm flipping through my Facebook reels and I'll see these videos and I just don't understand why they're entertaining to people. And then I hate myself for having watched it.

[00:42:20] **Adam:** Because

[00:42:20] **Ben:** then I hate myself for going to the next one.

[00:42:23] **Ben:** 'cause I'm like, oh, maybe the next one won't be terrible. And then the

[00:42:26] **Tim:** feels that way.

[00:42:27] **Ben:** you, and then the problem is like, every 10th video is actually good. And then I just hate myself even more. Anyway, I so, like, there's nothing about it that I truly enjoy. Even the parts that I enjoy, I kind of hate. And I know because of that, I'll, I'll just, I'll never be good at making social media because none of that connects with me.

[00:42:46] **Adam:** Yeah.

## [00:42:47] User Studies

[00:42:47] **Adam:** So Carol, when we had, uh, I believe a coworker of yours on Thelma,

[00:42:52] **Carol:** Yeah. I love Thelma. Yes.

[00:42:54] **Ben:** Oh,

[00:42:54] **Adam:** I, I feel like when we had her on, we talked about doing, what was it, user studies or something like that. Right. I, I know she does UX stuff. and I feel like this, what we're describing is the problem to which the solution is user studies, right?

[00:43:10] **Ben:** Hmm.

[00:43:10] **Carol:** They do.

[00:43:11] **Adam:** you've seen

[00:43:12] **Carol:** They do.

[00:43:12] **Carol:** a lot of empathy mapping, so they do a lot of things with users to figure out what is going on, so we understand their problems. Yeah.

[00:43:19] **Adam:** Yeah. So like if you've seen Silicon Valley, it's like that room where it's like,

[00:43:22] **Ben:** That's the best.

[00:43:23] **Ben:** and Adam, Ben, Carol, Tim Mingo. Sean, Sean George, how does that make you feel? It makes you feel angry. Does it make anyone else feel angry? Carol? Tim. Ben, Adam.

[00:43:40] **Adam:** bingo. Sean. George. George. Yep.

[00:43:45] **Ben:** that's such a good series. so. I mean, I guess I, I just didn't wanna let that go unsaid, right? Like we're, we're kind of dancing around this being a problem and trying to be mindful of it in our work. And there is a quote unquote solution to this problem, although, you know, solutions come with their own problems, right?

[00:44:03] **Adam:** They cost, this one in particular, cost, money and time and organizational effort. And we don't all have that available. So we have to kind of find our own hacks around it.

[00:44:14] **Ben:** If, if I can just maybe closing, closing thoughts here for a second. I was talking to someone just recently, friend of the show, member of the Discord, and we were talking about job hunting and, and I said that one of the things that I hoped had served me well when I was doing my interviews was that.

[00:44:35] **Ben:** When people asked me what I wanted to do at the companies, I would always say, well, I don't wanna, I would love to start as an individual contributor so that I have time to ramp up and to understand the product and to understand the team culture before I, you know, maybe organically evolve into some sort of a leadership position.

[00:44:57] **Ben:** I said, because I've worked at companies where too often leadership changes. Someone new comes in, they have no context, they have no true connection with the product or with the mission. They make these huge changes, everything blows up, and then they leave.

[00:45:14] **Tim:** Yeah,

[00:45:14] **Ben:** And it's like they, they just had, they didn't, they had,

[00:45:17] **Adam:** equity?

[00:45:18] **Tim:** it's called, it's, it's called, it's called consultants.

[00:45:22] **Ben:** so that, that was, I mean, I think, you know, half of me saying that was just me grappling with my own imposter syndrome. but I think half of it is legitimately, that feels like. Just a, a true way that I look at the need to connect with something before I can feel like I have the best ability to, to make changes that are meaningful.

[00:45:46] **Carol:** It's funny you say that, 'cause today I actually had the conversation with someone about something we're trying to accomplish and toward the end of the conversation I just went, it really feels like you're pushing for change just because you want to make change.

[00:45:59] **Ben:** Mm-hmm.

[00:45:59] **Carol:** Not because you're coming at it with a, a big problem to solve.

[00:46:03] **Carol:** It's just that you wanna change things up and it's been the same for too long and you feel like doing this could, could make things better, but there's not really a big problem here. So come at me with a problem and then let's talk about the change.

[00:46:17] **Ben:** Yeah.

[00:46:18] **Tim:** Yeah, well said. Yeah. Awesome. Um, I was gonna say, Ben, you, you say imposter syndrome. I, what I see in you is a realistic modesty, right? Because it, because I don't believe if someone comes in and

[00:46:31] **Ben:** I will take it.

[00:46:31] **Tim:** I, I, if someone comes and in and says, yeah, I know, I, I know the problems you're dealing with. I got, you know, I could, I got the solution, I'm gonna fix it.

[00:46:39] **Tim:** I'm like, charlatan, complete charlatan. They are just covering, they're just covering their inequities with this big glaze of, of, of attitude. It's like, if someone comes in and says, look, I, I don't, I'm not gonna know everything outta the box and I don't, you know, I, I don't want to come back. You know, create a irre will fail.

[00:46:57] **Tim:** So, yeah, let me start small, keep my feet in, and then we'll then, we'll then, then we'll make it bigger things that, that's a legitimate thing to do.

[00:47:06] **Ben:** I think we started with Tim insulting me and I think we should end with Tim complimenting me.

[00:47:11] **Tim:** Oh,

[00:47:12] **Carol:** I think so. I think so. Close it out.

## [00:47:16] Patreon

[00:47:16] **Adam:** well then this episode of Working Code is brought to you by nine other podcasts

[00:47:20] **Tim:** that Ben listens to.

[00:47:23] **Adam:** and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:47:35] **Adam:** Special thanks for our top patrons, Monte and Giancarlo.

## [00:47:38] Thanks For Listening!

[00:47:49] **Adam:** Of course, as usual, we're going to go record the after show. If you're not sure what that is, that is we, the outro music plays. And then for the patrons, the show continues. We just keep blabbering on about stuff. usually stuff that's totally unrelated to what we talked about on the show, and usually stuff that is not even tech related.

[00:47:56] **Adam:** Uh, so on tonight's after show, here are some cliff notes. a a gift crime was committed.we're gonna talk about, uh, job market and rehiring. We've got, unfortunately, some sad dog news. And maybe if we have time, we're gonna talk about the book that Tim mentioned two weeks ago in the after show. So, if you'd like to find out more about what the after show is, get your early access to new episodes in the after show and get in on some perks on our Discord.

[00:48:25] **Adam:** You can go to patreon.com/workingcodepod, throw a few bucks our way, and we will send you all those other things back in return. And that includes back episodes, right? You can go all the way back to the very first episode of the after show. I don't know what episode of the podcast that included, but, uh, we didn't start it on day one.

[00:48:41] **Carol:** Oh.

[00:48:42] **Adam:** No, we didn't start it on, on episode one, but you know, whenever we introduced the Patreon, that's when we started doing the after show. And it, and you get all the back catalog of the after show as well. anyway, so if you, I mentioned patreon.com/working Code Pod. The other thing is our Discord workingcode.dev/discord will get you to the right place, come join our community.

[00:49:00] **Tim:** our discord has been popping off.

[00:49:02] **Adam:** It has, and not just in the, not just in the gift can, I cannot speak tonight. I corrected my, my impro improper pronunciation of gif. Uh, and that messed me up on the other word, not just in the gif channel. Anyway, that's gonna do it for us this week. We'll catch you next week, and until then,

[00:49:23] **Tim:** Listen, unlike Ben, you, you listeners are not part of the problem. Your heart matters.

[00:49:30] **Adam:** we've come full circle back to the

[00:49:32] **Ben:** That's right. It was a, uh, fail, triumph fail.

[00:49:35] **Tim:** Exactly. It's a journey. It's a journey.
