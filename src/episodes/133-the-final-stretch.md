---
title: "133: The Final Stretch"
description: "Inspired by the GitHub Guide: Finish Your Projects, we wanted to talk about why finishing a project is always such a slog; and, how we can keep the momentum moving forward in order to get our projects over the finish-line."
date: 2023-06-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/133-the-final-stretch/id1544142288?i=1000618612490"></iframe>

Starting a new project is always exciting: there's so much potential, so many visions of grandeur. _Completing a project_, on the other hand, is always a challenge. In the engineering world, we often joke that the _last 90%_ of a project takes just as much time as the _first 90%_ of a project. Inspired by the [GitHub Guide: Finish Your Projects][github-guide], we wanted to talk about why finishing a project is always such a slog; and, how we can keep the momentum moving forward in order to get our projects over the finish-line.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[github-guide]: https://github.com/readme/guides/finish-your-projects
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/133-the-final-stretch.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** feel like for most things you could always do more, right? There's no such thing as

[00:00:04] **Adam:** really done. You know, you can always add features, you can always fix bugs, you can always polish, and you know

[00:00:10] **Tim:** Yeah, there's no finished software that's only released software. Right. So,

[00:00:15] **Carol:** if it were finished, it wouldn't take 10 people to maintain it.

[00:00:19] **Tim:** for sure,

[00:00:19] **Carol:** Yeah.

## [00:00:39] Intro

[00:00:39] **Adam:** Okay, here we go. It is show number 133 and we have once again everybody on the show, which don't get used to it cuz it's not gonna happen next week.

[00:00:48] **Tim:** so it's that time of year guys.

[00:00:50] **Carol:** hey. Is.

[00:00:51] **Adam:** Yep. But you know, we just gotta keep on keeping on, keep on trucking.

[00:00:55] **Adam:** Tonight we're gonna talk about finishing projects, which can be difficult at times. I know we can all relate to that. we are also gonna do a quick recap on where we're at in the book club. As always, you are still welcome to come join us in the book club. We're reading The Phoenix Project, a wonderful book about DevOps stuff.

[00:01:11] **Adam:** Told us a narrative story. It's a lot of fun. Everybody's really enjoying it. but as usual, we will start with our triumphs and fails. And Tim, it is your turn to go first.

## [00:01:20] Tim's Triumph

[00:01:20] **Tim:** Oh, hey. Okay. so I got a triumph, although I'm gonna start with a real personal triumph. My in-laws are gone. Finally,

[00:01:29] **Carol:** Yay.

[00:01:29] **Tim:** know, they say about, about fish and, and visiting relatives. They, yeah, they, they're here for three weeks and they had covid like for the first 12 days. So they're gone. They, they left, they got home safe.

[00:01:40] **Tim:** We did have a nice final like last week when everyone was healthy and. and they did their shopping. They loved to do, get all the cheap American stuff and take it, take it back home. So they did all their shopping at Ross and, you know,

[00:01:54] **Carol:** Home goods.

[00:01:55] **Tim:** Goods and all the outlet stores. so yeah, they're gone.

[00:01:59] **Tim:** They're safe. Great. We had a nice time. but the other trip is, so I've been, you know, just trying to stay relevant and learning about some new stuff. you know, and I really don't wanna learn new programming languages unless it's like work related and I need to, but something fun. so I've been, I've been messing around with, large language models, and, ai, generative art, generative videos, things like that. just cuz you know, it seems like it's all the, the rage that everyone's doing right now, there's tons of resources out there to, to learn about how they work and, and to just mess around and generate some stuff.

[00:02:32] **Tim:** So I've been, been doing that and it's, it's pretty cool. I put on the, our Discord on our, podcast adjacent channel. there's an article about how to create, take a QR code to create a QR code that goes to workingcode.dev. And then you can put some, you upload the QR code and then you also upload it to like this program called Control Net, which basically it, it, looks for the outline of things, so it will take.

[00:03:01] **Tim:** QR outline, and then you can put in sort of any generative prompt you want, like, you know, samurai sword painting of, you know, Japanese painting and it'll build the image around the QR code to try to kind of hide the QR code, but still make it viable.

[00:03:18] **Carol:** Cool.

[00:03:19] **Ben:** Sounds cool.

[00:03:20] **Tim:** And, yeah, it's, it's pretty interesting and it really creates some interesting looking artwork.

[00:03:24] **Tim:** It's not always a great QR code. Like, so I would generate 10, maybe two of them would work on my phone and I uploaded some of them and some of our, you know, folks in Discord are like, yeah, works on my phone. Doesn't work on mine. So it's kind of hit or miss, but it looks cool.

[00:03:40] **Adam:** I wonder if there's a way that you could do, I mean, I'm, I, I know the way that the magic eye images can be generated. You like, just tell it, here's a picture of it and generate me a magic eye image. That's the thing where you have to like, sort of cross your eyes or look through the image and you see it.

[00:03:54] **Adam:** I mean, obviously a human looking at that is gonna go, oh great, it's a QR code. That's boring. Cause I can't, I can't read QR codes, but I wonder if there's some way to like, put it in there and then like, you know, I don't know if you would need multiple cameras looking at it in order to like generate the QR code that then could be read out.

[00:04:13] **Adam:** Like, how cool would that be as like a part of a puzzle, a scavenger hunt or something? That would be so cool. Like, you know, you'd see this image and, and you're like, okay, well lemme try treating it like a magic eye thing. And you look at it in this QR code, you're like, great. Now what?

[00:04:28] **Tim:** Some of the QR codes, it generates, like, you can't really tell at first that it's a QR code, which is pretty cool cuz you just, there's maybe like a block up in the up upper corner, some blocks, you know, the kind of blocking up there, cuz that's, they usually, there's four blocks that the camera uses in an anchor to figure out what the, what the, the data is on the inside.

[00:04:48] **Tim:** So it's pretty, it was pretty interesting. But just really trying to, I, I really wanna learn more about not just, you know, taking someone else's tool and just creating stuff. I really wanna learn how they work. So that's what I've been working on.

[00:05:01] **Ben:** Let me ask you a question though, cuz I, I don't know anything about this stuff really. And when I see people posting photos of stuff, it feels like the trend is that all of those photos are very, I don't wanna say hyper stylized, but they're like very saturated, very rich colors. Like a lot of them are kind of like comic book ask, does it seem like the generative art is better in the not quite photorealistic realm, or is that just the things that people are dabbling with?

[00:05:32] **Tim:** I think it's just what they're, what they're posting, you know? because you have different, um, call 'em checkpoint files. So, so basically it's, they've trained. They've trained the, the language model to like be specifically good at one particular style of art. So the one I was messing with was called a ghost mixer, and it's really good at, generating sort of, Japanese, manga, manga inspired kind of stuff, stuff like that.

[00:06:00] **Tim:** It's really good at that ghost in the shell kind of machine, you know. But I, I was with another one, I forget the name of it, but it was super putter realistic, and I put in the prompt of, Henry Caval in a tuxedo

[00:06:15] **Carol:** Who's Henry Cabell.

[00:06:16] **Tim:** Superman.

[00:06:17] **Carol:** Oh, okay.

[00:06:18] **Tim:** Superman,

[00:06:19] **Adam:** Not the original, not my

[00:06:20] **Tim:** the original, the, the, the, the latest Superman, the, the guy from Witcher.

[00:06:24] **Tim:** And he was also in, mission Impossible. And it created, it looked like an actual, actual photograph of him. You, you couldn't tell it was not a photograph.

[00:06:32] **Ben:** Gotcha. Okay. So it, it's, it's just what it's been trained on. I gotcha.

[00:06:35] **Tim:** so if you put like hyper real in the, the, the prompt Hyperrealistic, you know, ak, even like the name of the camera that you, you want it to use, it will generate that.

[00:06:46] **Carol:** Oh, that's cool.

[00:06:48] **Tim:** pretty amazing,

[00:06:49] **Carol:** Yeah,

[00:06:50] **Adam:** Maybe this is a good time to mention that. If Ben sounds like he's losing his voice, he's not actually doing that. he is just like recovering from allergies or something and sounds a little off, but,

[00:06:59] **Ben:** Yes. Recovering from some sort of allergic reaction to something

[00:07:03] **Tim:** the Great Canada Fire of 2023.

[00:07:06] **Carol:** who knows?

[00:07:06] **Tim:** So that's me. How about you, Adam?

## [00:07:08] Adam's Failiumph

[00:07:08] **Adam:** oh, I guess I'm gonna go with a, I was originally gonna call it a triumph, but now I'm gonna call it a fum, which is that, I am done with my work travel for this season. You know, normally we, you know, I get sent out to a couple of different, reunions, university or college reunions, each fall and sometimes spring and other times of the year whenever they happen to have them.

[00:07:29] **Adam:** which can be a lot of work, long hours, difficult and, and sometimes annoying and boring. But one of the nice things about that, and the reason that this is a fum for not a triumph is that, for that part of my job, I am being flown to parts unknown of the country or just random parts of the country.

[00:07:47] **Adam:** and it's often not a problem for me to just pack my skydiving stuff and find a drop zone near where I'm working and schedule my flight home like a day later so I have an extra day to go skydiving. And, so that it's, that's why it's bad is cause now I don't have that opportunity to get free travel to a, a drop zone I've never di been to before.

[00:08:05] **Ben:** And the airlines have no issue with you boarding a plane, wearing a parachute.

[00:08:11] **Carol:** Uh, I can see how that would be. Uh,through security. You're fine.

[00:08:16] **Adam:** so basically, t s a has approved, like they've put out a statement on their website. You are allowed to travel with a sport parachute. You can, you can check it, but I wouldn't recommend it. cuz it, you know, they'll go through your bags sometimes, right? If they don't,

[00:08:29] **Ben:** Right, right.

[00:08:30] **Adam:** weird on the x-ray or whatever and they don't know what they're looking at, they'll go through it.

[00:08:33] **Adam:** And there have been stories of people who get their bag back and it's been like slashed open with a knife

[00:08:40] **Carol:** Oh, no.

[00:08:41] **Adam:** it just like, destroys like $10,000 worth of equipment. and so like I will never check a parachute. I always wear it through security as my, like my, my personal item or my

[00:08:52] **Carol:** You carry on.

[00:08:53] **Adam:** Yeah.

[00:08:54] **Adam:** And I, I have a special bag that I put it in that makes it look very much like a backpack. it's a backpack with like special handles on it and stuff, but, so it's kind of like steampunk, you know, weird looking backpack. But, you know, then I have to put it through the X-ray machine. When I go through t s a, and I carry for this purpose, you know, they're gonna, it's got metal in it.

[00:09:11] **Adam:** They're gonna see it when they x-ray it. So I carry a card with me, that shows what all of the metal parts, like this is what a, an X-rayed sports skydiving parachute container looks like, and this is what you should expect, and these are what the metal parts are for and, and all of that. And so, you know, I, I put it through the machine.

[00:09:29] **Adam:** I say, by the way, there's a parachute going through there. Here's the a card that explains it all to you. Here's a copy of the page on the TSA website that says I'm allowed to do this and that I printed off. And, and they're like, okay, that's fine. I give 'em the stuff, I go through the scanner, and usually they just like swab it for explosive residue or whatever just to be safe.

[00:09:47] **Adam:** And they send me on my way, knock on wood, I'm over here knocking on my own head. Uh, it's never been a problem.So,

[00:09:52] **Ben:** Nice.

[00:09:52] **Carol:** that's

[00:09:53] **Tim:** the plus, on the plus side of the plane starts to go down. You, you've got your own parachute

[00:09:57] **Carol:** Yeah, you're prepared.

[00:09:58] **Tim:** can you just open the door please? I'm just off by

[00:10:01] **Adam:** I I'll get it. It's ok.

[00:10:02] **Carol:** Yeah.

[00:10:03] **Tim:** I'll send help.

[00:10:04] **Adam:** I'll get out here.

[00:10:05] **Carol:** Mm-hmm.

[00:10:07] **Adam:** You need like a, one of those like cords that you pull on on the bus when you're like, this is my stop. Cool. So that's it for me. how about you, Ben?

## [00:10:14] Ben's Failure

[00:10:14] **Ben:** I'm gonna go with the failure, which is that I am struggling to be enthusiastic about multiple things at the same time. And not that I am not enthusiastic, but that being enthusiastic is causing a challenge. And I think about, years past when something like Adobe ColdFusion would've released a new version, I, I would've literally stopped everything that I'm doing and spent like the next week worth of free time looking at the new features, playing with them, writing about them, posting them on my blog.

[00:10:48] **Ben:** And I, I feel like I just, I don't know how people do multiple things. Adobe Codefusion has recently released 2023. I have not looked at it yet. Lucy, C F M L has released 5.4 and six Beta. I've been working on my Dig Deep Fitness app. I'm still excited about maintaining and improving my blog, and I'm excited about the stuff that I'm doing at work.

[00:11:12] **Ben:** And, and it's just all too much. I, I don't know how to,

[00:11:15] **Carol:** sounds like a lot,

[00:11:16] **Ben:** I, I don't know how to get all of that in there. And it, it clearly, I can't get all of it in there, but I wish I could get all of it in there. And I just, it makes me a little bit angry at those people who will sometimes talk about like, all the things that they do in their life and, and I don't understand how they have time for it.

[00:11:34] **Ben:** And then they have kids too. And like, I don't even have kids. And, and I still

[00:11:38] **Adam:** that are like getting up at 4:00 AM so that they can work out and work for three hours before their kids get up and like, screw

[00:11:44] **Carol:** It was a hard, it was a hard life to live for a while. Yeah.

[00:11:48] **Ben:** Yeah. So I don't know. I, I'm just, I'm feeling pressed for time to explore all the things that I would like to explore.

[00:11:57] **Adam:** One of the things that you mentioned in your list of things that you are, trying to be excited about, that you are excited to be, that you're finding you're struggling to juggle all of that excitement is, what you're doing at work. And I assume that what that was a reference to is your office hours stuff.

[00:12:10] **Ben:** Yeah. The office hour stuff I'm excited about. I've had some good conversations with a few people. Oh, I've only talked to a handful of people. I ended up, I don't know if I talked about this last time, but I ended up also posting a link where people could just reach out and schedule a one-on-one if there was stuff that they didn't necessarily feel comfortable talking about in a group setting.

[00:12:29] **Carol:** yeah. How's that

[00:12:29] **Adam:** We talked about the idea of doing that.

[00:12:31] **Ben:** Yeah, so I did it in like literally 20 minutes after I posted it. Someone scheduled a meeting and I, at first I was like, oh, did I just open up Pandora's box? But th they were the only one who scheduled a one-on-one. But it was a great, it was a great call. And,

[00:12:44] **Carol:** yeah.

[00:12:45] **Ben:** I feel like I now have a list of things that I know are troubling people and feature requests that they'd like to see.

[00:12:53] **Ben:** And, you know, when I don't have a product team behind me and a customer success team behind me doing research like this, this is the best that I can do. And I'm excited to have things that have a material impact or seemingly will have a material impact on the customers. So I'm, I'm pretty excited about that. So, all to say there's just not enough hours in the day. I go through, I go through phases where I feel that more and less, but right now I'm feeling that very much in the more category. So it's, it's frustrating.

[00:13:22] **Carol:** Well, hope it turns around for you.

[00:13:24] **Ben:** But as my father used to say, better to be busy than bored. So I, I guess that's true.

[00:13:30] **Carol:** Yeah, I like that saying. I've never thought about it, but that, that's absolutely accurate.

[00:13:36]

[00:13:38] **Ben:** anyways, that's what I got going on. Carol, what about you? Take us home.

## [00:13:42] Carol's Failure

[00:13:42] **Carol:** Oh gosh, guys, I'm gonna round this out with a big, giant failure. this week has been a nightmare. We got everything moved into our pod. Like, you know, you see the commercials, you get a pod sent to your house, you load everything into it, they deliver it to your house, right? We had it all scheduled except they delivered it to the wrong city.

[00:14:07] **Adam:** Oh no.

[00:14:08] **Carol:** To the wrong city, and then,

[00:14:10] **Adam:** Like delivered it to Paris, France instead of Paris, Texas type thing.

[00:14:15] **Tim:** Columbus, Ohio instead of Columbus, Georgia.

[00:14:17] **Carol:** pretty much that. They're like, we'll be there in 30 minutes. I'm like, oh, wow. That was really quick. Cool. I'm like, you're not here. They call, they're like, we're here. I'm like, you're not at my house. They're like, can you confirm the street address? So I do. They're like, can you confirm the city?

[00:14:32] **Carol:** And I say it, and they're like, uhoh.

[00:14:35] **Adam:** Oh, no.

[00:14:36] **Carol:** Yeah. To which they had to take it back to their shipping facility, hold it, figure out what went wrong. They came back to me and was like, oh, this is your fault. You did something wrong. So here's another thousand dollars bill for you to go pay to get it delivered to the correct city.

[00:14:52] **Carol:** To which I then had to pull up my security camera footage to show, like I told you, the right city, you got it wrong. It's on you. Oh, and by the way, we leave tomorrow for Disney for a week vacation with our family. And everything we need for Disney is in this pod. So they're having to not only like pay the extra shipping as up, they're handling it all.

[00:15:16] **Carol:** They're fixing it, but they're also having to like replace our, our essentials that we need. Like my running shoes are in there, my 10 shoes, my clothes are in there. the things that we need for this trip are in there. So just trying to figure out what all we're missing. And I'm not figuring it out until I pack it in a suitcase to only realize I don't even have our suitcases because they're also in the pod.

[00:15:36] **Carol:** So I'm just, I'm stressing out a little. My husband just keeps reminding me we can put our clothes in backpacks. But yeah, so I'm a little annoyed and on edge tonight, but tomorrow will be a new day and our stuff will be here in three weeks now. So yeah, it was supposed to be here three days ago.

[00:15:56] **Tim:** So how many miles off are they?

[00:15:58] **Carol:** Oh, they sent it back to the city.

[00:15:59] **Carol:** It originated from,

[00:16:01] **Tim:** Oh my God. Like you don't know where you're, yeah. They try to blame that on you.

[00:16:06] **Carol:** Yeah. Yep.

[00:16:07] **Ben:** you, you mentioned pulling something up on a security camera. How, what, where, where was this, what was it? Were you like giving them in the address at your front door or something?

[00:16:17] **Carol:** Alright. So I have teenagers and we have lots of doors in our house. So as I was raising my boys, I just put nest cameras in my house that captured in the house to capture all the exit doors. So there's one in my kitchen. So we just happened to place the order sitting at the bar on speaker so you can hear me and see me giving the address to the guy.

[00:16:39] **Carol:** He confirms it gives me the quote and we confirm everything, place the order, we're good to go. So I pulled up the footage. I'm like, here you go. Here's me starting the call. Here's 20 minutes of a phone call with your pods representative, showing that I did nothing wrong. This is on you.

[00:16:55] **Tim:** Wow. Well, good thing you had that.

[00:16:57] **Ben:** Yeah, for real.

[00:16:58] **Tim:** just

[00:16:58] **Carol:** Yeah, absolutely. Yeah. They're like, Hey, this is your own fault. You did it wrong. So I was like, no, we didn't. So

[00:17:04] **Tim:** I knew where I was going. I didn't want you to take it to the same town I live in.

[00:17:07] **Carol:** there's no way. Right?

[00:17:09] **Ben:** I'm surprised I didn't send you a confirmation email or something like,

[00:17:12] **Carol:** oh, yeah. So that's the funny part. Ben, you, you sign in and you just signed the contract. Well, because I verbally agreed to everything. I didn't even read the contract. I just said, accept the contract had the wrong address.

[00:17:26] **Ben:** Ah, gotcha, gotcha.

[00:17:27] **Carol:** So had I actually read it,

[00:17:29] **Tim:** you verbally gave 'em the right stuff. They

[00:17:31] **Carol:** they, they fingered it in wrong. Yeah. So since they typed it in wrong, it's on them.

[00:17:35] **Carol:** So they're giving us the, they're fixing it all. But yeah, I definitely signed the contract that said the wrong address, because I didn't even check it. I saw a street name and went on.

[00:17:44] **Ben:** yeah. Makes sense

[00:17:45] **Carol:** So

[00:17:46] **Adam:** contracts?

[00:17:47] **Carol:** right here's my blood. Take it.

[00:17:50] **Adam:** Ain't

[00:17:50] **Carol:** Prick. Myrick my finger. We're good. So yeah, I'm moving socks. I'm over it and I really hate that in on August 29th we do it all over again, so this is gonna be an interesting few months for us.

[00:18:02] **Ben:** man.

[00:18:03] **Tim:** Time to downsize. Just get rid of everything.

[00:18:05] **Carol:** We already did. We got rid of so much stuff. Yeah. Yeah. That's me guys.

[00:18:11] **Adam:** All right. Well, sorry for your troubles that, that sucks about not having all your stuff for the next three weeks, but

[00:18:16] **Carol:** Oh yeah.

[00:18:18] **Adam:** congrats on getting a bunch of free stuff, I guess

[00:18:20] **Carol:** Yeah. I got

[00:18:21] **Adam:** now after you got rid of a bunch of stuff.

[00:18:22] **Carol:** Yeah,

## [00:18:23] Book Club

[00:18:23] **Adam:** Okay, well, I guess let's, do a quick recap of where we're at with the book club. so I, if I'm not mistaken, we read up through chapter 16.

[00:18:31] **Adam:** How are you guys liking the book so far?

[00:18:33] **Ben:** Yeah, really, really good. It you know, I mentioned this in one of the previous episodes though, that the first time I've read this book, cuz this is the second time I'm going through, I just had a very different perspective. I think at the time I read the book, the first pass. We were very heavily steeped in the, we're moving all, everything to microservices and everything is a distributed world and, and event buses and message cues.

[00:19:00] **Ben:** And so when I read this book the first time, it, it felt very much in alignment with all of that kinds of stuff. And since then I've focused so much at work on actually distributing a lot of stuff and like merging services back together and realizing the beauty of having a lot of things co-located. And now as they're talking about these massively distributed systems in this book, it feels like I'm having a very different reaction

[00:19:30] **Carol:** Yeah. Every

[00:19:31] **Ben:** all of it.

[00:19:31] **Ben:** Yeah.

[00:19:32] **Carol:** Yeah, I'm with you. I'm with you. Cuz this is my third time going through it. And you know, the first two times was just kind of in, in an engineering role and the, this third time, you know, I understand the management side of stuff. So just seeing things from different points of view is making me appreciate different areas of the book that I never even caught on the previous reads.

[00:19:53] **Carol:** So I, I'm glad we picked this.

[00:19:55] **Adam:** yeah, absolutely. Your, whatever your current circumstances are for work, definitely colors the way that you read the book and how it, how it hits for you. the, the whole compliance thing for me is, very different than the first two times that I read this book.

[00:20:08] **Carol:** Yeah. Once you've been through that, you're like, oh God,

[00:20:11] **Adam:** Yeah.

[00:20:11] **Carol:** I feel, I feel for the security guy. The first time I read it, I hated him. Right. Hated him with a passion. Was like, this guy is just screwing my world every way around. Every other read through, I'm like, my heart breaks for you. Cause I know what your fight, like I, I know what you're having to go through.

[00:20:26] **Adam:** Yeah, well one of the earlier book clubs, we had a conversation about like, who you picture in your head. Like for me, I have a habit of like putting, cuz I'm, I'm listening to an audiobook or if I'm reading the book, I have a habit of like kind of picturing it like a movie. And I try to like reuse a character that I'm familiar with.

[00:20:43] **Adam:** So for me, the security guy, John looks like Hank from Breaking Bad. And that's what we talked about that one time at, at book club. but more recently I've realized that for me in my head, the CEO Steve looks like, Fred Waterford from The Handmaid's Tale. I don't know why, but that's just like, that's what my brain has slotted in there.

[00:21:02] **Ben:** funny.

[00:21:04] **Adam:** yeah.

[00:21:04] **Ben:** You, you have in the notes here, the c e o, employing the Steve Jobs and basically just like demanding that everything get done. And then that was such a point of, angst for me in, in reading this. So just to recap for people who, who haven't read the book, basically everything is on fire and, there, the point of sales systems are down in the, in the, stores

[00:21:27] **Carol:** Yep.

[00:21:28] **Ben:** know, they've been working on it for like three days straight.

[00:21:31] **Ben:** So the head of it goes home to spend some time with his wife and kid, and the boss calls up and is like, why aren't you at work? Like, why isn't everybody at work working on this right now? And he says, oh, you know, well I have, we have a plan. We're executing the plan. I trust the people who are there. And the boss just like blows up at him and he's like, get your lazy to the office.

[00:21:53] **Ben:** Get your lazy people to the office and work on it until it's done. And it was, I, it just, it was like I had P T S d I, I remember being on a call years ago and, my boss at the time was so angry at everybody and people were exhausted. I think they were just like, it was the same kind of thing. We're just like, lots of stuff wasn't going right.

[00:22:14] **Ben:** And he said, he's like, look, everyone on this call, if you're not working 70, 70 hours a week, you are working at the wrong company right now. And I just wanna be like, f you, like flip a table. And it just like, it just hit really home. I'm, I'm, I'm so tired of, of these executives thinking that they can just demand excellence and demand superhuman ability.

[00:22:39] **Ben:** Yeah. And.

[00:22:40] **Carol:** Yeah.

[00:22:41] **Ben:** Ah, drives

[00:22:42] **Tim:** Not even demand excellence. I, I like the, what it says here, the reality distortion field.

[00:22:47] **Adam:** Yeah.

[00:22:48] **Tim:** You're, you're, you're, yeah. I mean that it guy probably went into work, you know, if he, I don't know. I don't remember. Did he go into work or not? But if you go in, it's like not everyone can work all at the same time.

[00:22:59] **Tim:** The reason he went home is because, you know what? They don't really need me. Right. It's not urgent. It's like I'm just gonna go in and stand around. What, how's that? More efficient just to make your ego feel better that it's all hands on deck, that you can get on a call with someone and go, yep, we got everyone working on it.

[00:23:13] **Tim:** Yeah, cuz I'm, I'm the big alpha male and I'm making everybody work. Make me feel better. That's just

[00:23:18] **Adam:** So, he tries to, yeah, he tries to explain all of that to the ceo, Steve. and, and Steve's like, I don't care. I want everybody there. And so Bill, the main character basically tells him like, look, if that's the way you want it done, then you do it. and you can expect my resignation in the morning.

[00:23:34] **Adam:** And then he hangs up on him. And that's like,

[00:23:36] **Adam:** I think there's a, a, I think there's like a paragraph or something after that, but that's basically the end of chapter 16 where we left off. So that was a, a very interesting place to end the, the section for the book club.

[00:23:46] **Tim:** Cliffhanger.

[00:23:48] **Adam:** Yeah. Good. Good stopping point.

[00:23:50] **Carol:** So when, when Ben was talking about having some P T S D from this, right? I'm like, you, Adam. I listened to this book so early on, like in the first couple chapters, I was listening to it on my drive back and forth when we were handling, like, moving and stuff. And at one point I am white knuckling the steering wheel because I am getting so angry that this guy is just demanding so much from this guy and it is bringing back flashbacks of my previous like career.

[00:24:16] **Carol:** So I'm like, okay, we're going to Spotify right now because I'm gonna crash or I'm gonna yell at someone because I'm getting up upset about this book. I'm like, take a break, step away. Come back to it.

[00:24:28] **Adam:** it is pretty infuriating.

[00:24:30] **Carol:** it is, it makes me so mad.

[00:24:33] **Ben:** Yo. As a quick side note, something that I've always wanted, Because I listen to a lot of audio books and a lot of podcasts and the, to contrast that when I used to read actual textual books, I would always underline stuff I would, or, or if I was like on the Kindle, I would usually highlight things. And one thing that I've always wanted from an audio based experience is some button that I could hit in the interface that would immediately start recording like 15 seconds before that time.

[00:25:04] **Ben:** And because like they'll start to say something, I'm like, oh, I wanna remember this and I wish I could just hit record, hold my thumb down for the next like 30 seconds and release it and, and then get like audio clip notes.

[00:25:14] **Adam:** Yeah, that would be great.

[00:25:15] **Ben:** How is that? That feels like that's such a need. I can't believe I've never seen that

[00:25:19] **Adam:** audio highlights. Yeah.

[00:25:20] **Ben:** Yeah. Audio highlights. That's perfect name for it.

[00:25:24] **Tim:** Oh, so, Jeff Bezos, if you're listening, we got a new feature for, for Audible. Audible Blair.

[00:25:31] **Adam:** Oh, we have his ear. We'll, we'll get on that.

[00:25:33] **Tim:** Okay.

[00:25:34] **Carol:** He listens.

[00:25:36] **Tim:** speak. We're going back to failures. I, I meant to bring this up. So what day was it? Tuesday. So AWS Lambdas went down

[00:25:45] **Adam:** Oh yeah.

[00:25:46] **Tim:** from like two 30 till, I think around 5 36,

[00:25:50] **Carol:** Oh,

[00:25:50] **Tim:** um, in the Eastern region. And so, yeah, one of our payment processors, the one we've had a whole lot of problems with lately, they were trying to get away from, like, all of a sudden they're down again.

[00:25:59] **Tim:** We're like, oh my God, these, these morons are down again. And you know, and it turns out it was, I mean, it was, it was that, and I tried to, yeah, not, not, not necessarily. Yeah. It wasn't strictly their fault. And they're like, oh, it's, we're we're affected by the AWS instance. So I'm like, okay, so I'm gonna log into my aws.

[00:26:17] **Tim:** I tried to log into AWS just to see what was going on. I couldn't even log in. I got a 5 0 4 gateway error. Like, okay, I guess it's legit.

[00:26:26] **Ben:** Yeah, US East is our, is our region, and we lost all of our, image processing for a couple of hours.

[00:26:33] **Tim:** Yeah. Yeah. It was, that was a, it was a mess. Yeah. Everything came back. I guess they were using the Lambda for like, Tokenization service cuz they would like take the card information and then it would come back. And then when you try to do, do a sale, it'd be like, oh, account data missing. We, they're like, we, you gave us this card number we totally forgot.

[00:26:50] **Tim:** We don't know. Have no clue what, what card number you're talking about. So, yep. No credit card processing for three hours there that day.

[00:26:57] **Adam:** Sounds like, you know, going multi-region to have high availability would've been one of the things on the, that last, you know, checklist of their. Their application that, that they really should have finished but didn't

## [00:27:08] Finishing the Project

[00:27:08] **Tim:** speaking of which, let's talk about that, that the finish finishing the project, right? So I, I think all of us have, you have a new product that you're trying to release. You know, it's not gonna be, you know, you know, it's not gonna be completely feature full. It's maybe it's an MVP type product, but that, that last bit, the first bit is really super fun to work on, right?

[00:27:30] **Tim:** You're, you're building, you're architecting, you're figuring out, you know, how to solve these problems. That's super fun. these errors come in, they're weird errors, and you're trying to figure them out and, you know, then you get better error handling and things like that. But that last 10% is really, really hard.

[00:27:46] **Tim:** And I think, not necessarily because it's always technically hard, I just think it's not that interesting sometimes.

[00:27:52] **Carol:** Burnout.

[00:27:54] **Tim:** Yeah.

[00:27:54] **Carol:** You're done with it? Yeah.

[00:27:56] **Tim:** Yeah. And it also, it's like the problems you're solving for the last, everything, all the fun stuff's been done, and now it's just kind of like, you know, covering the nail holes, patching the walls, you know, doing the, the little stuff that has to be done to, to, to, to ship it.

[00:28:10] **Tim:** But it's like,

[00:28:11] **Adam:** You start to realize your mistakes are like, oh, these, these, Columns or not columns. These is like fields in our API responses are inconsistently named, but there's already people consuming them, so it would be a pain in the butt to version it and, and fix that.

[00:28:25] **Tim:** Yeah. Yeah. And so, yeah, you have this really huge productivity stage that you're working on, but that last bit where it just, it's stuff that has to get done to get it out the door. It's really, really hard. And it's sort of a mental block about getting it finished. And then a lot of times people will think, oh, that project almost done.

[00:28:44] **Tim:** So resources start getting pulled off, right? Oh, start working on the next new thing. Of course, everyone wants to go work on the new fund

[00:28:51] **Carol:** Oh yeah.

[00:28:52] **Tim:** and then you're, you'll, and then you got this team left over that's this, that, that, you know, they're like, oh, I guess we're left stuck holding. But some of the things that you have to finish at the end can be super important to the success of the project.

[00:29:06] **Carol:** Yeah, sometimes those require like an architect to, to make some decisions on what's going on because you don't find some of the problems until that last 10% and you're like, Hey, I know you've moved on to something else, but we got an issue you gotta come back to

[00:29:19] **Tim:** Yeah.

[00:29:21] **Tim:** Yeah.

[00:29:21] **Ben:** Well, I, we've talked about this many times before, which is that I am a huge proponent of building things incrementally, and, and I do think that building things incrementally actually ultimately aids in being more successful at finishing the overall project. And part of that, and maybe this is controversial here, part of that is that you can also discover that there are areas of the application or feature that you don't have to finish.

[00:29:50] **Ben:** Because if, if, you know, you start out with this grand idea of what something should be and the product team has designed all these various screens and states and interactions and workflows. And if you can start to build something incrementally and, and, and I think this is actually quite key, put analytical information into the usage of it and you get that into customer's hands.

[00:30:14] **Ben:** You might have a screen that is not feature complete and you have analytics on it and you see users don't even really engage with that screen at all. And then you're like, well there were all these other aspects of it that I was gonna build on that screen. But if like three people are going to it a day, maybe it's not worth the, the effort to put it in and maybe I'm gonna defer that to a future quarter, maybe never do it at all.

[00:30:36] **Ben:** And focus more on the areas that do seem to be getting traction do seem to be getting, engagement from the users. So I think building small and incremental also keeps up that enthusiasm and that focus.

[00:30:50] **Adam:** I mean, it, it. Cuts both ways, right? So maybe the reason that people aren't engaging with that feature is because it isn't complete, right? They're waiting for the thing that they need out of it. But yeah, you only you will know, or maybe only they will know if, if that's the case.

[00:31:05] **Tim:** Yeah, so I think there's two parts to it. So the last, the last bits are just really a slog, right? It's just work and there's no way. To get around the work and, and we're, I'm reading our, it's a GitHub article that, we, we'll link, to it. There's a lot of the points that they're making there, but that's one of the things they say that there's no tricks to getting around the work.

[00:31:25] **Tim:** You just gotta get through the work. So it's not sexy, it's not fun, it's just stuff that, you know, that has to be done. So this thing can launch, and you gotta find a way to trick your brain if you're a person who is dopamine driven, you know, and has to feel the, the power of, you know, doing some cool or something slick.

[00:31:43] **Tim:** you know, and a checklist is like the bane of your existence for, you know, just let's just make sure that, okay, do we have this feature done? Yes. Okay. Does it do this? Yeah, I mean that you hate that. You gotta find a way to trick your brain to handle that, to just get through that slogs, that work.

[00:31:58] **Adam:** I think you're, you're absolutely right about it being a brain thing, right? So there's this phrase that, I know it's not, it's not, I'm not the only one that's ever heard this, but it's like you do the first 90% of the work and then all that's left is the last 90% of the work. And that's because your brain takes that last 10% and just goes, this is just as much of work and just as annoying as the first 90%.

## [00:32:18] Fear of Finishing

[00:32:18] **Tim:** Yeah. And then it's, it talks, talk about the fear of finishing. So I think it takes courage and, and I've done this before, so I, you know, have a, a, a pet project that I've been working on for maybe better part of a year, and it's ready to go, but it's like there's these little things. All of a sudden I come up with these reasons to start changing and tinkering and

[00:32:38] **Carol:** Oh yeah.

[00:32:40] **Carol:** I, I th I think we've all done that, right? Like you hit the end of the project and you're like, oh God, I'm about to release this thing out into the world. Everyone is about to see what I've done. If it fails, my name's all over it. Number one, like, everyone's gonna know how terrible I did. And even if it's great, I just have this fear that's huge fear that this project is going to land on its face.

[00:33:02] **Carol:** So at the end of it, I start looking for any way I can maximize like opti, or I can like optimize earlier, right? So I can be like, okay, let's go ahead and plan for this. And I start telling the customer, but we didn't think about this, but we didn't think about that. We need to figure out this because there's this huge fear of releasing it and something going wrong.

[00:33:21] **Carol:** And it scares me every time. There's not been a time I've had a project go out. At the end of it, I kind of just poop my pants a little and go, I don't know if I want this out. Right? I'm like, oh God. Oh God. Everyone's gonna see it. Right? And even. I would say 90% of the time, like what I've released has been fine.

[00:33:40] **Carol:** It's been, there's not been an issue, but there hasn't been a single time something didn't release big that I wasn't like shivering going, what's gonna happen?

[00:33:49] **Tim:** Mm-hmm.

[00:33:50] **Ben:** Well, it's funny, like you only have to do this a couple of times where you build something or people at your company, not necessarily, you build something and it's really cool and you release it and no one cares. And, and it's not because it's not a cool feature and it's not because it's not well done, it's because just people have a way that they're doing their work.

[00:34:10] **Ben:** And just because you build something great doesn't mean that they're suddenly gonna change the way that they do something. And it's, it, it sets you back a little bit emotionally, but at the same time, it also. Gives you this perspective that not, you know, not everything is critical. Like you can actually get away with a lot because there's so much momentum in a product that getting people to change their habits or change the way that they're gonna do something like that actually takes time and you, you have that time to learn and adapt as people are, are trickling in.

[00:34:45] **Tim:** Yeah.

[00:34:46] **Adam:** The other thing that comes to mind for me is that like I'm sure that there are is a class of products that you could be working on where this is not true, but I feel like for most things you could always do more, right? There's no such thing as

[00:34:58] **Adam:** really done. You know, you can always add features, you can always fix bugs, you can always polish, and you know

[00:35:05] **Tim:** Yeah, there's no finished software that's only released software. Right. So,

[00:35:11] **Carol:** if it were finished, it wouldn't take 10 people to maintain it.

[00:35:15] **Tim:** for sure,

[00:35:15] **Carol:** Yeah.

[00:35:17] **Ben:** One of the things that they say in the article that hit home for me was the guy was saying that he'll, he'll pick a song and put it on repeat for hours on end, and I am totally guilty of that. I will play the same song forever if I can find a song that's like the right amount of stimulus but not distraction, it just like, it kind of dampens the noise in the back of my head and allows me to focus.

[00:35:42] **Carol:** I am. So with you there, we were, putting a pi, we were taking a pilot from three states and putting it into a new state. And I was like, I don't even know what this pilot is because you guys created the pilot before I was here, so I'm gonna have to learn what this pilot program is, right? So I'm putting it in and for, you know, weeks straight, all I'd listened to was Hamilton.

[00:36:02] **Carol:** I was, I had the Hamilton soundtrack memorized because it gave me just enough simul like simulation that I could keep going with coding, but not so much that ever got distracted. So that is like, And critical for me and, and so many times, but Hamilton was the last one I remember, and it was moving the pilot to Idaho.

[00:36:22] **Carol:** I was like, okay, let's get this pilot program in Idaho.

[00:36:27] **Adam:** for me, it's, there's a, a, a metal cover of Africa by Toto that I really like. and and then like after the song, there's a, like, yeah, all on the same track. There's like another sort of like mini just riff or a, a jam. It's a co, it's a collaboration between a couple of different artists and there's just this little, little jam session at the end of it.

[00:36:45] **Adam:** And so I'll play that one song on repeat, that one track and sort of two songs over and over and over. And it's just, like you said, it's just, it's hype up and, and I know it so well that like, it's not distracting to sing along or anything like that. Yeah.

[00:36:58] **Ben:** I really like the, the last in the mohegans theme, cuz it has this, it has this like,

[00:37:03] **Adam:** soundtracks are good for this

[00:37:05] **Ben:** yeah, it's like a haunting, kind of a celly violin string instrument. And it builds and there's some percussion and, you know, like Drummonds and, and you know, but in my mind I can see the scene where they're either running up the hill after the, the Damsel in distress.

[00:37:19] **Ben:** It's a, it's a classic movie. I don't. Carol, it might be before your time. I don't know.

[00:37:23] **Carol:** Yeah, I don't even, I don't know what you're talking about.

[00:37:26] **Ben:** Oh, it's early. I mean, I don't know about early, early, but it's,

[00:37:29] **Tim:** Daniel Day Lewis,

[00:37:30] **Ben:** Lewis. Yeah.

## [00:37:31] Tweaking and Tinkering

[00:37:31] **Tim:** Yeah, I, I will admit, so there's, there's sometimes, like I get, I have gotten stuck in that tweaking tinkering mode where like, oh, let me, let me swap this library out for this one cuz this one's really better. And it came out, you know, I didn't really know about it when we started and you, you eventually like, reach this point where you really can't tweak anymore conscientious, you know, with a, with a clean conscience, you realize, okay, I'm just, I'm just creating work cuz I'm nervous.

[00:37:58] **Tim:** And then there's like some sections like, you know, I really don't feel good about this, but. I'll wait till the error comes in. I'll wait. I'll wait till the errors start popping because I know, I know that will motivate me to fix it and also will motivate maybe the organization to make that a higher priority.

[00:38:12] **Tim:** It's terrible, you know, you want to be able to say, oh yeah, I, it's code. I'm, I'm a hundred percent behind it. I know there's, it's good quality, but it's like, sometimes it's like, you know what, there's a couple, there's a couple goblins in that basement and we're just gonna have, let, let people find them and, and they'll have to slay them, you know, help me slay them when we get to them.

[00:38:33] **Tim:** Cause, you know, otherwise I'm never gonna release this. I've done that a couple times and I'm not proud of it.

[00:38:40] **Carol:** I think we all have to an extent.

[00:38:43] **Ben:** So one of the things that I've taken to doing in my software is I have a centralized component in the, on the backend where you give it, an error that's been thrown by the system. And this centralized component will take that error, look at it, and then return a user-friendly error message. So essentially it looks at the type and it has to translate it into the appropriate HTP status code and a message to return.

[00:39:08] **Ben:** which is, that's manual translation. I actually have to put all those cases in. and at the end it's basically a giant switch statement when you look at the error dot type and I'm doing a bunch of stuff and then the default case returns a 500 error by default. But then it also logs a message to say the application through this error, but nothing caught it and translated it properly.

[00:39:29] **Ben:** And to your point, like I won't put in translations for everything. I'll just sort of like, you know, the ones that are

[00:39:36] **Tim:** often are we gonna get

[00:39:37] **Ben:** Yeah, yeah, yeah, exactly.

[00:39:38] **Tim:** We'll wait till it happens and we'll figure out what should say.

[00:39:41] **Ben:** so I'll just watch the logs to see how often it says this error was not translated properly. And I'll go from there.

[00:39:47] **Tim:** I've definitely done that.

[00:39:50] **Ben:** So one thing that I've been feeling, and I I I mentioned this right before the show, is that when it comes to finishing, and maybe when it comes more specifically to the, to the minimum viable product mindset, I almost feel like I've been airing too hard on the MVP end of the spectrum, where I think I'm releasing stuff maybe too early and like too broken and too feature incomplete.

[00:40:18] **Ben:** with, with this, you know, faith that it'll be okay and I'll be able to iterate and improve it with enough time. But I don't know. I feel like I'm getting too cocky. Like as, as an example, I'm working on this thing at work right now where, you can apply tags to a document so that later on you could search for things by tag.

[00:40:39] **Ben:** and I released the ability to add tags to a document. There is no ability to delete tags or to rename tags. Like you can remove a tag from a document, but then you have a list of tags somewhere that you can't alter. And I'm like, I probably shouldn't have released that yet, but you know what? It's gonna be a fast follow, it's gonna get there.

[00:41:00] **Ben:** But like, so what? So what if people have tags and they don't want, or they rename, they can't rename something like, I don't know, maybe, maybe it's okay, but maybe it's also not, maybe I'm getting too sloppy.

[00:41:10] **Carol:** I would be furious because I misspell everything. On the first go, every word I type is misspelled. So the fact that I would have like four tags on there and only the fourth one would be spelled correctly, I would be so mad at you right now.

[00:41:26] **Ben:** I know. See, this is what makes me nervous. But I, I also, you know, my perspective is I'm, I'm on this legacy system at work. I feel like every day is a borrowed day at this point. And

[00:41:37] **Carol:** Aw.

[00:41:38] **Ben:** I, I don't have. I don't have time to worry as much as I probably should, so that's how I'm validating it. But, uh

[00:41:46] **Adam:** we've talked in the past about like code review process and stuff and, and you know, what you guys were talking about, like the spelling issues. I think every, almost every team has the one person, at least one person who struggles with spelling or, or maybe it's the typing part of it, like spelling.

[00:42:02] **Adam:** They get, they know the spelling, but they're just typing too fast and not paying enough attention. Whatever it is. I feel like we, we get to know each other, right? Everybody kind of knows who the person on the team is that's gonna most likely be the one with the spelling mistakes, I

[00:42:13] **Carol:** Her name is Carol. Yes. Yeah,

[00:42:16] **Adam:** And, and, yeah.

[00:42:17] **Adam:** So like that's one of the things that like, you know, we look for in code review for that person, right? And like, mine is probably, my bad habit is probably like copy modify mistakes, right? Like I'm copying, pasting the same thing in a couple of places and forgetting to update the part of it that needs to be updated.

[00:42:33] **Adam:** So if you see the same code, it's probably not supposed to be the same.

[00:42:37] **Carol:** Yeah.

## [00:42:38] Code Review

[00:42:38] **Ben:** You know, I almost just, cause you talked about pull requests for a second, so I almost put this into the engineering channel today at work. A I I, I had a, I poit something and then I wanted to suggest something. My posit was that of all prs, and this is just a rough number, don't actually need any critical review, that 90% of prs are someone, I wrote some code.

[00:43:04] **Ben:** I'm very willing to take full responsibility for this code, but someone else needs to approve it because we have compliance stuff and I, you know, we have to check a box that says someone else looked at this. I said, 10% of prs probably do need feedback. And the person. Putting the PR out there probably knows that and can make that judgment, Hey, I'd really like some feedback on this. That was my po. What I wanted to suggest was, Hey, can we just create a Slack channel that is like rubber stamp prs? And the ones that I'm fully willing to take responsibility for, I'm gonna put 'em in there and just, I want someone to rubber stamp them. And I said, we could even make it fun. Like we could give out a bonus at the end of every month for the engineer that rubber stamped like the most prs, you know, during the

[00:43:50] **Adam:** about a bonus, but

[00:43:51] **Tim:** like

[00:43:52] **Carol:** Here's your Starbucks gift card,

[00:43:53] **Ben:** But like, ju, just to underscore from the company standpoint, like yes, we understand that this is a process driven system and we're just trying to get around it.

[00:44:02] **Adam:** Well, yeah, I mean that's, that that calls back directly to stuff that is in the book that we've been reading, the Phoenix Project. Right. That's. That is, what do they call that? Like, not routine changes, but like, there's a name for it I thought.

[00:44:14] **Ben:** this is one of the four types of work.

[00:44:16] **Adam:** no, I mean it was, I think it, I think it probably was under the umbrella of changes, but like when they were, when they were looking at the index cards and deciding like, which ones do we actually need to discuss?

[00:44:27] **Adam:** And then there was a

[00:44:27] **Ben:** Oh, right, right,

[00:44:28] **Carol:** Oh yeah.

[00:44:29] **Adam:** know, on the card, they've got the right signatures or whatever. So they don't, they don't need to be discussed and scheduled. It's like, whatever, you know, it's such a simple routine change whenever you wanna do it. Go

[00:44:38] **Carol:** Mm-hmm.

[00:44:39] **Ben:** Alright. Well, I mean,

[00:44:41] **Adam:** I mean, let me, let me jump in here on this too.

[00:44:43] **Adam:** We, we don't have a specific Slack channel for it, but we do have a concept that we just have among the team that we call, we, we don't, we've called it a blind stamp instead of a rubber stamp. Like we're explicitly calling out the fact that I'm not even looking at this, I have blind stamped your pr.

[00:44:58] **Adam:** Right. and it's for the exact same reason, right? Like, you know, or I'll, I'll post a PR and I'll say like, this can take a blind stamp. Right.

[00:45:06] **Ben:** because like the reality is, and. I mean, I don't think this makes me lazy. I think this is just the reality of building software and not every screen is a thousand percent unique and special. I have a lot of screens that I build that are literally like copying a previous screen, pasting it, gutting most of it, and then changing the bits that actually have to be changed.

[00:45:28] **Ben:** And like, I don't really need someone to review that.

[00:45:32] **Carol:** But I, but I have to trust that you tested it right? Because a lot of people

[00:45:36] **Carol:** gut

[00:45:37] **Ben:** loaded it in the browser and I clicked around.

[00:45:40] **Carol:** but not every engineer does that, right?

[00:45:42] **Adam:** but that's, that's, that's the whole concept of the, but that's the whole concept of the blind stamp. He's saying, I'm, I take responsibility if it breaks, it's my fault, not yours, the reviewer. And like, I mean, so let.

[00:45:53] **Tim:** that's always the case with reviewers. It's never the reviewer's

[00:45:55] **Ben:** right, right, right.

[00:45:56] **Ben:** But

[00:45:56] **Carol:** that's kind of normal.

[00:45:58] **Adam:** Well, but like how, how many of us have never had, a bug where you, like you ship some jQuery code and your selector is a class selector when you meant an ID selector? And so the bug fix is literally changing a.to a pound sign. Like,

[00:46:12] **Carol:** Right.

[00:46:12] **Tim:** Yeah.

[00:46:13] **Adam:** do, does that really need thorough review and like deploy a QA and smoke test there and

[00:46:18] **Ben:** Right, right, right. All right, well, you know what, so I didn't actually, I, I typed this all out at work, but I didn't actually hit return to send it into the, into the channel. Cause I'm like, oh, people are just gonna think I'm a jerk.

[00:46:30] **Carol:** No, I think it's smart.

[00:46:31] **Ben:** it sounds like maybe I'm not a jerk and I wonder if

[00:46:33] **Adam:** a way of saving time for people.

[00:46:35] **Carol:** Yep.

[00:46:36] **Ben:** all, maybe this is something people would actually be down by, down with.

[00:46:39] **Ben:** Cause I find at work so I use this phrase, and I don't know how accurate it is, but I use this phrase that we will often use process to solve people problems. And sometimes like, I just want people to do their thing and like, we don't have to have a whole process around trying to protect people from people or whatever.

[00:47:01] **Tim:** If, if, if you create a process to protect everyone from the idiots, you're gonna treat everyone in your company like an

[00:47:06] **Carol:** agree. That's accurate, Tim. Yeah.

[00:47:09] **Adam:** you have to have

[00:47:10] **Tim:** Fix, fix, fix the idiots. Fix the idiots. And then your process doesn't have to be so stupid.

[00:47:16] **Carol:** Sounds like we've all fought this fight before.

[00:47:19] **Tim:** Yeah.

[00:47:20] **Ben:** the, so total side tangent there for a second, but, you, you reminded me years ago when I was at the, I used to be on the board at work and I was at a board meeting and they were talking about how to build up this company and one of the investors said, said something like, you have to org, you have to build a business assuming that everyone who works for you as an idiot.

[00:47:42] **Ben:** Because like at some point someone will be in that role and they're not gonna know what they're doing, and the business has to be resilient. Which,

[00:47:50] **Tim:** well, yeah, I mean, that's different from, I mean, that's building a business, not the processes. Right.

[00:47:55] **Ben:** Yeah. But I'm just saying it's like,

[00:47:56] **Tim:** for when the idiot nephew takes over.

[00:47:58] **Carol:** yeah.

[00:47:59] **Tim:** Yeah. Make the company run so well that he can, like, play golf every day and it'll still run itself. That's, that's, that's different from

[00:48:07] **Carol:** Rubber stepping a pr.

[00:48:09] **Tim:** yeah.

[00:48:09] **Tim:** Yeah.

[00:48:10] **Carol:** Yeah. Silly thing when you said, I was on the board, like I used to be on the board before my immediate thought was walking in a break room and seeing your face like on the pinup board, you know, like where they have the OSHA guidelines, like I don't know why that was the first thing that went through my head was Ben's face was on the board.

[00:48:27] **Carol:** So

[00:48:28] **Tim:** Have you seen this developer? If so, if so, if so, call 5

[00:48:33] **Carol:** reward.

[00:48:35] **Adam:** I, I just can't not picture Ben as a, as a pinup like tattoo now, like a pinup girl. But,

[00:48:43] **Tim:** yeah,

[00:48:43] **Carol:** Sorry to put you guys there.

[00:48:46] **Adam:** Ben, you need to smile more, bud. I need to, I need to objectify you a little bit more here.

[00:48:51] **Carol:** It's the raspy boys. I'm

[00:48:53] **Tim:** yeah, it is. Yeah.

[00:48:54] **Ben:** I got, I'm working my deme more angle.

[00:48:56] **Tim:** Yeah, yeah, yeah. Yeah.

## [00:48:58] Patreon

[00:48:58] **Adam:** All right, well, I guess this is the spot where I tell you that this episode of Working Code is brought to you by your CEO's reality distortion field. Just put out the fire and get your projects done ahead of schedule. That's what we pay you for. Just do it listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon or patrons.

[00:49:18] **Adam:** Cover our recording and editing costs. And we couldn't do this every week without them. So special thanks to our top patrons, Monte and Giancarlo,

## [00:49:25] Thanks For Listening

[00:49:25] **Adam:** and actually. I'm just gonna break in from the script here to point out that, Patreon added a free trial feature and I went ahead and I enabled it for us.

[00:49:33] **Adam:** So if you wanna see what it's like to be a patron, get that little gold roll attached to your Discord account and listen to the after show feed.

[00:49:43] **Ben:** Yeah.

[00:49:44] **Adam:** for free. I think it's like a two week trial, if I'm not mistaken. Either way, check it out. patreon.com/WorkingCodePod. And that's gonna do it for us this week.

[00:49:53] **Adam:** We'll catch next week and until then,

[00:49:55] **Tim:** Remember, your heart matters even if you're the idiot that makes us create idiot proof processes.
