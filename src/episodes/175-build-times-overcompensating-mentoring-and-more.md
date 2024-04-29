---
title: "175: Build Times, Overcompensating, Mentoring and More"
description: "On today's show, we cover a variety of topics. Ben talks about overcompensation at work. Carol talks about how her current task got away from her. Tim talks about the generation smoking ban going into effect in England. And Adam talks about the challenges of mentoring junior developers."
date: 2024-04-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/175-build-times-overcompensating-mentoring-and-more/id1544142288?i=1000653465744"></iframe>

On today's show, we cover a variety of topics. Ben talks about overcompensation at work; and, how we often swing way too hard in one direction as the first signs of a challenge. Carol talks about how her current task got away from her; and, how she suddenly founder herself creating a Pull Request with 84 files in it. Tim talks about the generation smoking ban going into effect in England. And Adam talks about the challenges of mentoring junior developers; and, how hard it is to have enough "right sized" tasks ready for them to work on.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/175-build-times-overcompensating-mentoring-and-more.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** if you told me my build process takes 90 minutes before it even starts, or just like the linting process before, I'd be like, there is something wrong with that, right?

[00:00:07] **Adam:** Like, clearly,

[00:00:08] **Ben:** I'd be like, how can we delete most of this code immediately?

[00:00:11] **Adam:** yeah, right? Like, I need

[00:00:14] **Tim:** No, Ben, you'd be like, linting's a waste of time. Let's

[00:00:16] **Ben:** Well, that's why we can delete it.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go, it is show number 175, and on today's show, we don't even know what we're gonna talk about, actually we do.

[00:00:45] **Adam:** We, we each have some stuff we wanna bring up, but, you know, we're just gonna have a conversation and see where it goes.

[00:00:49] **Carol:** You gotta stick around to find the title.

[00:00:51] **Adam:** that's right, yeah, we don't know what to call the show yet, so that's, that's why I introduced it that way, so we'll figure it out. but first, as usual, we will start with our triumphs and fails.

[00:01:00] **Adam:** Looks like it is Ben's turn to go first, so what do you got going on, my friend?

## [00:01:03] Ben's Fail

[00:01:03] **Ben:** This is going to be a soft fail, but, I had a thought this morning or yesterday morning that, what if I don't ever get to use Lucy CFML again? And that made me really sad. And I'll always have ColdFusion in my life. Cause my personal stuff runs on a VPS that's powered by Adobe ColdFusion. And for the most part, Adobe ColdFusion and Lucy CFML are highly overlapping in their feature set.

[00:01:28] **Ben:** but they're not exactly the same. And I have. Heretofore really enjoyed using Adobe ColdFusion in my personal life and Lucy CFML in my professional life. And it occurred to me that there's, you know, a non zero chance that when my current employment ends, I may never get to work with Lucy CFML again, because I'm not a server manager.

[00:01:53] **Ben:** And the idea of paying for another server and learning how to manage my own server is just to be able to use, the open source ColdFusion engine. I don't know. That's a, that's a lot more than I have time for in terms of learning and willingness to put in effort. And I don't know, it just kind of, kind of made me sad.

[00:02:11] **Ben:** I have really been, I've been really loving Lucy.

[00:02:15] **Tim:** Aw, it'll be okay.

[00:02:17] **Ben:** Yeah. I don't know. It's a, it's a, Lucy also seems like it's gotten a little quiet. You know, I, I pay attention to the, to the Lucy development forum and it just seems a little, a little quiet lately, and I don't know if that's,

[00:02:31] **Tim:** Maybe they fixed all the issues. There's no problems. It's perfect. Mishka, Mishka has completed his masterpiece.

[00:02:40] **Ben:** So anyway, that's me, ColdFusion forever, but maybe not Lucy forever.

[00:02:44] **Adam:** You need a ColdFusion tattoo.

[00:02:46] **Carol:** Yeah.

[00:02:47] **Ben:** any tattoos.

[00:02:49] **Adam:** Well, that would be, I mean, duh, like, if anybody's gonna have a ColdFusion tattoo, it would be you. I know people have ColdFusion

[00:02:56] **Ben:** Yeah, yeah, for sure.

[00:02:57] **Adam:** And if you were going to have a tattoo, obviously it would be a ColdFusion tattoo. So like, it all makes sense.

[00:03:02] **Ben:** The universe is, pointing me in a direction. We'll get there. Anyway, that's

[00:03:07] **Tim:** or it could be Lucy and you could say, you know, once it dies, you just say, well, it's my dog,

[00:03:11] **Carol:** Just spelt wrong.

[00:03:12] **Tim:** just spelt wrong.

[00:03:13] **Ben:** So that's me.

[00:03:16] **Adam:** quick change of subject.

[00:03:17] **Ben:** Carol, what do you got going on? Thanks.

## [00:03:19] Carol's Triumph

[00:03:19] **Carol:** All right, guys, I'm going to go with a big triumph. So this weekend we had ADT and AT&amp; T out to the house and they were installing all of the things that they install and multiple times they look at my husband and ask him questions about our technology and about what stack we're going to be using. And my husband looks and points at me.

[00:03:39] **Carol:** And I start rambling off like, Oh, right now we're just putting in like the Nighthawk mesh system because I don't want to like install the Ubiquiti when I only have a few hours here. Like, I'm going to come back and do that later. And he's like, Oh, you're doing mesh. I'm like, yeah, we're going to do mesh.

[00:03:53] **Carol:** He's like, do you know how to disable the wifi on this router? I'm like, yes, I know how to disable the wifi on this router. I was like, I've got it all covered. And, the AT&amp; T guy later was like, what do you do? Like. Like, what do you do? Like for a living type thing. And I'm like, Oh, I'm a software engineer.

[00:04:09] **Carol:** He's like, Oh, this makes sense. He was taking pictures of my ubiquity, like hardware to figure out what he wants to put in his house and I was answering questions about it. So it was nice to have tech people in my house working that thought my tech knowledge was impressive, even though they did look for my husband, like look at my husband to get answers first, but I'm never offended by that.

[00:04:29] **Carol:** Yeah.

[00:04:30] **Ben:** Yo, I'll tell you, I was never really tuned into things like that before, and then my wife mentioned it to me, that we'll go into a store, and she'll be talking to the clerk, and whenever the clerk responds to her questions, he'll look at me, and I, again, I never thought about it until she mentioned it, she's like, oh, it's so irritating, like, why can't they just respect me?

[00:04:53] **Ben:** And my wife manages the house and so she deals with all the contractors who come in to do the plumbing and, and, you know, HVAC maintenance and stuff. And so she'll meet them when they come to the house. And she'll be talking to them. And then I walk into the room and then all they do is talk to me.

[00:05:08] **Ben:** And I want to be like, bro, don't talk to me. I don't know what's going on. I'm not dealing with you. Talk to my wife. And

[00:05:14] **Tim:** It's her house. I just live

[00:05:15] **Ben:** yeah, I know. I'm so tuned into it now. It's, it's like really egregious.

[00:05:19] **Adam:** Mm

[00:05:20] **Carol:** It is crazy. When we were at my in laws, for like our break between getting here and leaving Georgia, the pool guy came out and I was explaining to him that the pool was not working, that one of the valves is not putting water out and it's circulating where it shouldn't be, and there's a problem.

[00:05:37] **Carol:** And he's just like, oh, okay, I'll go look at it. And he came back and knocked on the door and was like, I'm so sorry. Just didn't believe you. It didn't think you knew what you were talking about. Clearly you do. And I'll listen to you. He goes, there's absolutely a problem and I see what's going on and you were exactly right.

[00:05:52] **Carol:** So even called my father in law and apologized to my father in law for kind of blowing me off because I was right and knew what I was talking about. And he was like, yeah, he's like, she's our personal IT person for everything. You should listen to her.

[00:06:06] **Tim:** Even not, even like non IT, my, my wife won't go to change the oil at like Jiffy Lube or whatever, because every time, every single time she goes, the guys they're working on, they want to take her and show her like, so here's where the windshield fluid goes and they're showing her all these and she's like, And they never, never, ever done that to me.

[00:06:23] **Tim:** One, they just want to keep talking to her cause she's pretty.

[00:06:25] **Carol:** She's very pretty. Yeah.

[00:06:28] **Tim:** two, they're like, oh, this dumb woman doesn't know where a spark plug is. So I'm going to, I'm going to impress her with my knowledge. And I go and they're like, okay, it's done. See you, bud. Bye.

[00:06:36] **Carol:** huh.

[00:06:37] **Tim:** I feel sorry for you ladies. It's, it's gotta be hard.

[00:06:40] **Ben:** Yo.

[00:06:41] **Carol:** I've just started ignoring it. And I will say younger generation, I don't see that. Like what you were talking about, Ben. So like if we're at Home Depot and I'm asking someone a question, like if it's, you know, someone my age or younger, they make eye contact with me. They answer me. But if it's one of the older guys, usually in their, I'm a retired some service guy hat, you know, working at Home Depot, they're always looking at Steve to answer him, or they're trying to ask him more questions about what's going on.

[00:07:07] **Carol:** And I'm sure he's just going, look, she drugged me in here. I didn't even want to come. I don't know what's happening. Just talk to her. I'm going to go play with our dog. Y'all fix this.

[00:07:17] **Ben:** that's good to say. That's good to hear that the generational gap is maybe part of the cause.

[00:07:22] **Adam:** And give it a few years and then you'll have the, these, you know, younger millennials and the Zoomers and everybody, filling in the workforce and then they won't be making eye contact, but it'll, it'll be for a different reason. Put

[00:07:34] **Carol:** All right. Well, that's me. What about you, Tim?

## [00:07:36] Tim's Triumph

[00:07:36] **Tim:** All right. I got a huge win here. This is major, major, major news. Stop what you're doing. Write this day down. Cause this is big

[00:07:45] **Carol:** Okay. What is it?

[00:07:47] **Tim:** I'll tell you, get ready. So today on my YouTube channel, which only has like five videos, I created, finally created my own 24 hour white screen video

[00:07:59] **Carol:** With no ads?

[00:08:00] **Tim:** with no ads.

[00:08:01] **Carol:** With no ads.

[00:08:03] **Ben:** Revolutionary.

[00:08:05] **Tim:** It's revolutionary. So if you, if I haven't mentioned this before, I tend to have like a white screen. YouTube channel up and there's the one that has like 65 million views. It's ridiculous. And I've been using it for years and I use it just to like, so that I can walk away from my computer and my computer doesn't shut down and lock up, you know, I want to keep an eye on my emails and, keep the computer from going to sleep.

[00:08:26] **Tim:** So that's what I, I just play that video. And as long as the video is running, it won't go to sleep or lock. And recently that channel. Started paying ads, so I have to sit through ads and sometimes like in the middle of it, it's like I'm doing something all of a sudden. Wireshark! It scares the heck out of me.

[00:08:48] **Tim:** So I'm like, you know what? It shouldn't be tonight. So it took about 20 minutes a day. Created it, put it up. I'll put a link in the channel so you guys can subscribe to it. I know you want

[00:08:56] **Ben:** Is it,

[00:08:57] **Carol:** want to watch

[00:08:57] **Tim:** Definitely want to watch this. It's no, it's not 4k.

[00:09:01] **Ben:** Oh,

[00:09:02] **Tim:** Search for Timothy Cunningham, 24 hour white screen.

[00:09:06] **Tim:** You won't be able to tell the difference if it's 4k or not.

[00:09:08] **Ben:** I'm joking. Does it have any sound? Is there like a,

[00:09:11] **Tim:** There's no sound.

[00:09:12] **Ben:** ASMR hum kind of a,

[00:09:13] **Tim:** no, no,

[00:09:14] **Ben:** all right. Fair enough. Fair enough. Fair enough.

[00:09:16] **Carol:** At like the three hour mark, you should just throw in like a goat sound or something and scare the out of everyone listening.

[00:09:23] **Tim:** then in lesser news, we had a new product go live today.

[00:09:28] **Ben:** Ah, congratulations,

[00:09:29] **Carol:** What's the news, eh? Okay. Okay.

[00:09:31] **Tim:** mean, nothing's bigger than the 24 hour white screen. Come on.

[00:09:34] **Carol:** You know.

[00:09:34] **Adam:** mean, I attended the premiere, but I couldn't make it all the way through the video.

[00:09:38] **Tim:** Yeah. Yeah. It's a real commitment to get through it. But, yeah, so we've been working on our product that, allows a company that like say they have like regular people that So you're a company and you have regular vendors that you're paying. So it could be lawyers, particularly insurance companies, could be lawyers, body shops, housing contractors, roofers and stuff like that.

[00:09:59] **Tim:** And so we've created basically an onboarding system where they can invite all their vendors to say, would you like to get paid immediately? And you know, not have to process a check. And so they can come on onboard themselves. And then anytime there's bills that they want to pay those vendors that automatically, you know, they have like 15 or 20.

[00:10:18] **Tim:** checks or payments that they want to do, consolidates them into one payment, pushes it out to them, notifies them, gives them a report of everything that they're paying and you know what makes up that deposit. And they just, you know, vendors just sit there and do their The money shows up in their account.

[00:10:33] **Tim:** So,

[00:10:33] **Ben:** Blair,

[00:10:35] **Carol:** Nice.

[00:10:36] **Adam:** Sounds like a good product.

[00:10:39] **Tim:** just gonna get that first customer on it. So

[00:10:43] **Carol:** Do you take money? Like, can the product take money from the customer? The

[00:10:48] **Tim:** we don't, to pay the typically, no, we do have a separate product that does that. so if they wanted to, they can make them aware of that and they can pay them. So that's me. Huge news. So excited.

[00:11:02] **Carol:** Great job.

[00:11:03] **Tim:** Thanks. How about you, Adam?

## [00:11:04] Adam's Fail

[00:11:04] **Adam:** I'm gonna go with a fail. and patrons will know what this is because it affects them. I still haven't sent out the stickers that I promised, from the end of the year, the end of 2023, for, for people that were signed up to our Patreon by then.

[00:11:19] **Adam:** and that's entirely my fault. I have the list of names. the stickers are ready to go. I just haven't been able to get around to it. And so part of the reason I'm bringing this up now is because by mentioning it on the show, now I'm committing myself to getting it done. And I have increased the humiliation factor if I don't manage to get it done by next week.

[00:11:38] **Adam:** So, thank you for holding me accountable, right? That's, that's what we're doing here.

[00:11:42] **Ben:** very nice way to, admit your, your sticker shortcomings,

[00:11:48] **Adam:** you know, of course, barring what in the business world we call an act of God, you know, something outside my control, but you know, short of that, I'll get it done this week.

[00:11:55] **Carol:** Anything we can help with?

[00:11:57] **Adam:** Can you do it for me?

[00:11:58] **Carol:** They sent them to me and I'll do them for you.

[00:12:01] **Adam:** I'll figure it out. you know, honestly, it's probably just as much work to, to send you the list of everything as it is to just get it done. So cool. All right. Well then, why don't we start our conversation off, with Ben, what have you got going on,

## [00:12:15] Overcompensating

[00:12:15] **Ben:** I was thinking recently about overcompensation and the reason that that was top of mind is we upgraded our MySQL database at work from a rather old 5. 7 something or other. To, 8. 0. 32.

[00:12:31] **Adam:** familiar with this. Yes.

[00:12:32] **Ben:** Yeah. And, and, you know, when you make a fairly large jump in database versions, although to be fair, I don't think there was anything in between 5, 7, and 8.

[00:12:41] **Ben:** they're breaking changes. And for the most part, those breaking changes are really. Not common, you know, it's, it's, like the, the database, they do a pretty good job of making sure that they're not like redefining what select means. Uh,but there are little things that change and we got bit by one of those.

[00:13:00] **Ben:** And it was one query in the entire application had a column called grouping. And in MySQL 8, grouping is a built in function.

[00:13:11] **Carol:** Oh no.

[00:13:12] **Ben:** so it, that one query started throwing an error saying something that like grouping isn't like an undefined reference. Yeah, it's a reserve word, something like that. Now that goes away if you just put back ticks around grouping so that it knows that it's not a built in reference.

[00:13:29] **Ben:** And I thought that, okay, the sane response to that is I will go in and fix that one query. And then be done with it and I can go back to the rest of my work. The, in my opinion, insane response to that would be, okay, we have to stop what we're doing and go and update all queries so that all column names are now backticked and all new queries created going forward are surrounded by backticks.

[00:13:56] **Ben:** And,

[00:13:56] **Adam:** Ugh.

[00:13:57] **Ben:** I mean, we didn't do that, but that would be crazy. And it's, and it's easy to think of teams doing that. And I started to think about where else do we. Overcompensate, you know, Oh, my, my SQL is performing a little slow on this one query. You know what? Let me add a document database to our technology stack to overcompensate for that one problem.

[00:14:17] **Ben:** Or, you know, we're having some, I don't know, like one little issue here, like a bug popped up. Okay. Let's now implement a massive QA process so that things like this never get through. Or I don't know, like I, my, my brain just started to spin out and think about all these things that we do to overcompensate.

[00:14:35] **Ben:** And I, and I think there's like a, almost an unhealthy fear of breaking things sometimes. and I, and I know that we have sort of a love hate relationship in our tech, in our tech industry about move fast and break things. And that sort of fell out of vogue and now we want everything to be rock solid.

[00:14:52] **Ben:** And I, I want my software to be rock solid, but. I also,

[00:14:56] **Adam:** break nothing.

[00:14:56] **Ben:** yeah, I also feel like we have to accept the fact that there are going to be bugs and instead of being afraid of it, just kind of get on with our lives and, and deal with it as best we can. I don't know. This was just top of mind. There's not like a question in here that I'm just, it's just something I've been thinking about.

[00:15:15] **Adam:** so, I like the fact that you brought up the move fast and break things stuff, because that was my mantra for a long time. It was like, you know what, screw it. We're just, I'm, I'm getting stuff done. It may not be perfect, but we'll find the bugs in production. Then we'll fix them. Right. and like, Hey, and, and I'll get it done.

[00:15:29] **Adam:** I'll get that done fast too. And I'll get that done fast too. Right. We'll just, it'll just like always moving forward. Mm hmm. as fast as I possibly can. And I think something that really helped change my perspective on that. I hope I have a much healthier perspective on that now, but something that really helped was I built some, so I have this like engineering dashboard, I think I might've mentioned it before, where we like monitor outbound email and, you know, keep an eye on stuff that's, Important for the engineering team to sort of be proactive about, right?

[00:15:56] **Ben:** this part of the dead man's snitch stuff?

[00:15:58] **Adam:** Oh, that's one of the things, right? Like we have snitches on stuff we have, you know, like we have a, so our ticketing, like our support ticket system is home rolled and it's like built into the application and, and, and it's all single tenant installation. So right now, without any outside help, you would have to like go log into 13 different,you know, customer instances to, to find out what are the open tickets and all that.

[00:16:20] **Adam:** It's kind of a pain in the neck. So I like built an API resource where we can aggregate all the tickets and have one view of all the tickets. And then in there, it's like, okay. I have a, a way to filter it show, so it only shows tickets that nobody from our company has replied to yet. That's like, you know, for SLA reasons, right?

[00:16:39] **Adam:** So you have a rule or you have a SLA where you say we have to reply to all tickets within, you know, two business days or based on priority, right? If it's a priority nine or higher, we'll respond within four business hours or whatever, right? and so having that sort of stuff in there has been really helpful, but so I built this dashboard and then something I added to it more recently was, graphs of interesting things that are numeric, right?

[00:17:02] **Adam:** So like the number of credit card charges per day for the last 30 days. And the number of dollars per day that we've collected for the past 30 days. And number of dollars, by like, not by feature, but we call it by module, right? So we've got like an online giving module where you can make a donation to your alma mater, or we've got the membership.

[00:17:21] **Adam:** You can buy a membership to your alumni association, or you can, have your profile to show up in the directory, or you can register for an event, right? These are all modules. And seeing, just like seeing the number of dollars that we're collecting in this one module, right? Like, so I'm just going to make up a number because I don't want to give away private company information or whatever, but just, let's just say like on a daily basis, we're collecting 200, 000 out of this one module.

[00:17:47] **Adam:** I was like, wait a minute. So 200, 000, 24 hours, you know, that's, that's a lot of money lost per, per 10 minutes of downtime. So I'm like, okay, that really changed my, the way I think about at least that module. Right. And then it kind of colors the rest of, the application for me a little bit. Like stability becomes very important after you are no longer that scrappy young startup trying to get your second customer.

[00:18:11] **Adam:** Right.

[00:18:13] **Ben:** yeah, sure. Anytime you're taking money, you know, it's just a different feeling.

[00:18:18] **Adam:** And, and especially when you were taking money on behalf of somebody else, right? Like we're not collecting what, the money that we earn comes from our contracts with our customers. The money that we collect on our website goes all straight to our customers. We are just like, kind of, we're technically not even in the middle for like PCI specific reasons, but like we're facilitating, we're helping them make it happen.

[00:18:38] **Adam:** And so every dollar that we prevent being collected is like a dollar out of somebody else's pocket. And

[00:18:46] **Ben:** Yeah, yeah, yeah,

[00:18:46] **Adam:** that hurts.

[00:18:47] **Ben:** one other thing I was thinking of in terms of this overcompensation, and I don't have children, so I'm talking only from what I've heard and I'm sure anyone else here can chime in. With

[00:18:58] **Carol:** We can help you.

[00:18:58] **Ben:** boots on the ground experience. I've, I've been told that part of the problem with kids these days is, is, is like, we don't let them fail enough.

[00:19:10] **Ben:** You know, kids used to just roam around the neighborhood in packs and take the subway when they were 10 years old. And we weren't worried about them being kidnapped and molested and. You're breaking bones. And when they did get hurt, you know, then they dealt with it and, and they evolved and they learned how to do things and how to not do things.

[00:19:32] **Adam:** Or they were molested and

[00:19:34] **Ben:** yeah, yeah, exactly. And life goes on. No, but,

[00:19:38] **Adam:** Oh man.

[00:19:38] **Ben:** no, I'm joking. I'm joking. Um, but you know, the reality is I think that parents today, again, from what I've heard, this is not from my own personal experience, but, you know, They aren't kind of given that same amount of latitude to experiment and to fail and to learn.

[00:19:55] **Ben:** And that made me think about the overcompensation. And all this comes from a place of love, right? We want our kids to have the best experience. We want them to be protected. We want them to be healthy and feel safe. And in doing so, and you know, in putting rubber mats down on our playgrounds, we, we kind of remove some of that real life.

[00:20:16] **Ben:** Experience that kids used to get, I think maybe more often. and, and this again, made me think about software and how much we learn when we break things and when we, you know, do a boo boo and we launched something to production that didn't work out, you know, those are the things that I remember and I commit those to memory.

[00:20:36] **Ben:** And I think to myself, Oh, I definitely have to never do that again. Cause that sucked. And it was painful and people were angry at me and I disappointed the customers. And there's like a huge value in that. And I think if you're, if you're on a, you know, bowling on a bumper lane, yeah, maybe you get more pins, but are you, are you becoming a better bowler?

[00:20:55] **Adam:** Hmm. I like that analogy.

[00:20:58] **Ben:** Anyway, again, there's no questions here. This is just the stuff that's been bouncing around in my head.

[00:21:04] **Adam:** And, and the bumper, it's funny, the bumper bowling thing was what put me over the edge. And, and it just reinforced the thing you said earlier, but it didn't click with that. So like, you know, as a parent, letting your kids fail, Company or as an engineering manager team sort of thing, you have to let people make mistakes so that they can then learn from those mistakes.

[00:21:22] **Adam:** And yeah,

[00:21:24] **Tim:** I mean, I get what you're saying, but at the same time, it's like, there's some known bad practices in our industry, right? It's like, yeah, with a kid, you know, you want them to learn sometimes having to learn the hard ways. The The, the only way they're going to learn. but it's like in our industry, there's some known bad things to do and bad practices, like, you know, not writing tests or

[00:21:50] **Adam:** just to name one at

[00:21:51] **Tim:** just a name off the top of the cap,

[00:21:53] **Ben:** just randomly.

[00:21:54] **Tim:** not writing tests, right.

[00:21:55] **Tim:** Not having a stable deployment scripts or a pipe, you know, continuous integration pipeline, things like that. So do you really want to learn? A lesson that everyone else has already figured out. Just get the feels.

[00:22:10] **Ben:** I mean,

[00:22:11] **Adam:** I don't know that it's about the feels, but it's about developing that muscle, right? It's some, some lessons you learn better by being the one to have failed than trying to follow in somebody else's footsteps who says, oh, here's the safe path.

[00:22:27] **Tim:** I

[00:22:28] **Carol:** I think it depends. Like, I don't want someone writing data that should be encrypted, like, just as plain text, right? Like, there's no way that's okay. Like, our company is going to fail if this happens. There's going to be big problems. So maybe there's a, sometimes you can say yes, but I'm kind of more with Tim.

[00:22:46] **Carol:** Like, if we've already figured it out. Yeah.

[00:22:49] **Tim:** mean, what's, what's the point of going to school and learning about these things or having a company policy about these things, if you're just going to say, well, everyone needs to learn through their own mistakes. It's just like, no, people are still going to make mistakes no matter what. And they'll learn from those, but the known things that like the big things, those aren't the ones you should be learning on.

[00:23:11] **Tim:** Those are the ones you should be following procedure.

[00:23:12] **Adam:** Well, sure. Yeah. I mean, for anything that's like regulatory compliance, right? Like encrypting passwords and all that stuff. Like for sure, anything that could get the business in significant trouble, this is the way we do it. And we have three people looking over your shoulder at code review time to make sure that it's the right way.

[00:23:30] **Adam:** Sure. But like, and maybe Ben, you can, you'll have to answer whether or not this is right, but the impression that I got was. You know, as I'm, helping, you know, junior to mid level developers on my team. you know, maybe as we're pairing, I see a problem that they're going to run into, but I, instead of telling them in advance, Oh, you know, you, you spelled this wrong variable name or whatever, like let them do it.

[00:23:56] **Adam:** that might not be a great example,

[00:23:58] **Carol:** IDE fixes that for you.

[00:24:00] **Ben:** So I was listening to an episode of,the Go, was it GoTime? Yeah. The GoTime podcast, part of the ChangeLog series. And this guy was talking about one of the things that he likes to do in Go is that I think this was Go. Every if statement has an else statement. Yeah. Meaning that he always, yeah, that was exactly my reaction.

[00:24:23] **Ben:** And his, his rationale with that, it makes it very clear. It's either going to happen this way or it's going to happen a different way. And I don't agree with that rationale, but that was his rationale. And I have to imagine that that was developed because at one point, maybe he had a guard statement that had an early return or, you know, did something where, Oh, that didn't quite work out.

[00:24:46] **Ben:** And I'm obviously putting words in someone else's mouth here. And his overcompensation for that one issue was to say, okay, now all if statements must have else statements such that we never have this bug again. Or even people who say like. A function should only ever have a single return statement. I think like that's lunacy.

[00:25:05] **Ben:** That's crazy. Like that, that is unnecessarily complicating code.

[00:25:09] **Adam:** And, and if I'm not mistaken, that's one of the things in clean code. So that's one of those things where we're

[00:25:13] **Ben:** But that's lunacy.

[00:25:14] **Adam:** we, we have to say, okay, you know, maybe this was, good advice at some point in history based on the context of the time, but it's no longer like accepted wisdom.

[00:25:24] **Ben:** Yeah. And I'll tell you, I think I've come, I don't think I've complained about this per se, but I, I had a manager years ago who I wanted to refactor some SQL queries. And I said, Hey, sometimes these queries run for, for like 10, 15 minutes. I mean, it's completely unacceptable. The user's already left the screen.

[00:25:42] **Ben:** You know, they're just running in the background at this point, taking up CPU on the database. I said, I want to refactor these queries so that it, it reduces the load on the database. And he said, well, how much impact is that going to have on the user experience? I was like, I don't know, some, it's going to help the database.

[00:26:00] **Ben:** And he's like, yeah, but how often does it actually do this? And I was like, I don't know, you know, for most users, probably never because of the volume of data that they have. And I said, for some users, probably more, but not always. And he was like, well, what's the business case for fixing? And I really struggled to come up with a business case.

[00:26:21] **Ben:** Not like, like I couldn't give a number. I just like, I w it's dirty. It's not great all the time. And I'd like to fix it. And at the time I was really irritated that he was pushing back against me wanting to fix this, but I kinda. You know, looking at it through this overcompensation lens, like, yeah, it's going to suck sometimes for a handful of people, but is that worth fixing it?

[00:26:44] **Ben:** And I'm, and I'm not saying that it was the right decision, but I get it. I think I much more understand it now when I think about. Trying to be okay with stuff just being suboptimal. Sometimes if it's not suboptimal, let's say the majority of the time.

[00:26:59] **Adam:** And yeah, I mean, only you can speak to this or, I mean, of the four of us, only you can speak to this, but like maybe something that was unsaid there was like, Yeah, it's rare that it happens and it's a rare number of people that can trigger it, but if it's affecting the database, right? If it's, if it's bogging down the CPU on the database, that is affecting every user during

[00:27:19] **Ben:** Right, right, right.

[00:27:21] **Adam:** it's running.

[00:27:21] **Ben:** Yeah. It's, it was tough because databases are also so powerful. Anyway.

[00:27:28] **Adam:** too, is like, what is, what is an hour or two of your time worth to fix it? And, and how much is it going to cost to just throw a little bit more money at the, at the database to make it a little bit stronger?

[00:27:39] **Ben:** So anyway, I don't want to, I know we have other people here, so

[00:27:42] **Adam:** No, Bogart the show,

[00:27:43] **Ben:** I've been, I've been thinking about the overcompensation and I think, you know, we probably do it. A lot more than we think about. and I'm, I'm trying to be mindful about not throwing the baby out with the bath water and just fixing in a micro,

[00:28:00] **Adam:** why you don't have kids?

[00:28:02] **Tim:** hmm. Mm hmm.

[00:28:03] **Ben:** one weird trick and I have no kids.

[00:28:07] **Carol:** so anyway, that's me. Well, can I add one thing, Ben? So at ClearCapital, I worked for this great architect who would catch me all the time because I would be, you know, looking at these bugs that would come in and they would be one off bugs and I would be so determined to find a root cause. I'd be writing these massive queries, putting everything together.

[00:28:28] **Carol:** One single time did it ever happen, so I don't have any trends, I have no way to verify it's still happening or ever happened before, but I'm convinced that I need to like, spend days working on just digging through data to find out what caused it. And finally he would come in and go, hey. You know, one off, we're going to correct that one column that is off by two pennies or two dollars, and we're going to move on, and you're going to flag it, and if you see this occur again, save your queries, and we'll run them again, and we'll start coming back to it.

[00:29:03] **Carol:** Not once did I ever have to open up one of those queries again. They were always one off things, but I really appreciated that he could step in and go, all right, Carol. You went too far. You've looked too hard. This is one off, move on. Let it be a one off thing and admit sometimes we can't find a root cause.

[00:29:20] **Carol:** We're not always going to find a root cause.

[00:29:23] **Adam:** so that's a totally pragmatic and reasonable response, but I, I just, it made, it immediately made me think of, God, I can't remember the details right now, but remember we just had that case where the guy who works for Microsoft on Postgres discovered this like major vulnerability,

[00:29:40] **Ben:** Oh yeah. And the S and like

[00:29:42] **Adam:** and, and the, And the reason he started digging was because he saw slightly elevated CPU for a few seconds during a test suite run.

[00:29:51] **Adam:** Like, the world needs those people too.

[00:29:54] **Ben:** Yo, absolutely.

[00:29:56] **Adam:** Honestly, I think Microsoft is one of the companies that should be funding that kind of

[00:30:01] **Carol:** Yeah, I agree.

[00:30:02] **Adam:** they've got the money, they should be spending it on that. But The world needs that type of work too, for sure.

[00:30:09] **Tim:** Yep, I heard him on NPR, they were interviewing him and they, it's been said that the world, the world owes him beers for life.

[00:30:16] **Adam:** he should get like, like a ring or something, right? That just like, if you see him out at a bar, you have to buy him a beer.

[00:30:23] **Tim:** I saved the internet.

[00:30:24] **Ben:** yo. Okay. Sorry.

## [00:30:25] Unused Dashboards and Reports

[00:30:25] **Ben:** Just one more overcompensation thing for a second. It work.

[00:30:29] **Adam:** I mean,

[00:30:31] **Ben:** some point someone in leadership said every single service has to have a metrics dashboard associated with it, like as a rule, we have to have dashboards for everything. Which is fine when you have 300 engineers. We have six engineers, or four engineers now, and we've been trying to reduce costs and part of the costs that we incur are the custom, the number of metrics that we deploy into Datadog.

[00:30:58] **Ben:** And now you go and say, Hey, I'd like to remove this one metric. And Datadog says, are you sure you want to do that? Because it's being referenced in 719 dashboards. And if you remove it, all of those dashboards will break. And you're like, it's like, who, why do we have 700 dashboards? That's ridiculous. And it just feels like someone said that that was a rule at some point.

[00:31:23] **Ben:** And then we did it. And now everyone else has to suffer. Anyway. Okay. That's done. I got it off my chest. I'm good. I'm good now.

[00:31:31] **Carol:** was gonna say, I love the features that come in that go, oh, and we need to be able to report on it. Okay. Who needs the report on it? And they tell you one user needs to report. And like three months later that user quits. So your email and your report is just going to nobody ever. It's still being ran, but nobody's getting it.

[00:31:50] **Carol:** Nobody's monitoring it and nobody's doing anything with it. I'm like, Sometimes you want to report, but they should have like end of life. It should say, okay, we want to report on it for six months and then kill it. So I don't have to worry about it ever again.

[00:32:02] **Adam:** It should have a dead man switch on

[00:32:03] **Carol:** Yes,

[00:32:04] **Ben:** just thinking that.

[00:32:06] **Adam:** You, you have to go in every week and press the button. Like I still want this report.

[00:32:10] **Carol:** I was, kill the code.

[00:32:12] **Ben:** that's not crazy, honestly. I mean,

[00:32:15] **Adam:** I mean, I, I just, I emailed a customer today to say like, Hey, we've been generating these files for you. Do you still use them? Like we're, we're, this is a customer who is not technically sophisticated enough to use our API. So I wrote a job that uses our API to gather data. On a daily basis and write files to S3 so that he can then download those files and consume them in whatever automated automations he's got.

[00:32:42] **Adam:** And I have no idea how long, but like, we've been doing this for days. You know, we've been doing this daily for years and I emailed him today. I was like, Hey, are you still using this? And he said, Oh no, no, we don't use that anymore. Nice

[00:32:56] **Ben:** close to home. We had the same exact thing. We had a background process that was generating a report and it was, it was, it had custom FTP code. It was uploading this file to this person's FTP site. And we reached out to them and you're like, Hey, are you guys still using this? And they said, Oh no, the guy who needed that hasn't worked here in three years. Who's next?

[00:33:18] **Adam:** We're professionals.

[00:33:19] **Carol:** can go next.

## [00:33:22] Breaking Down a Large Commit

[00:33:22] **Carol:** So I've been working a lot at work, you know, that thing you do to get paid and it's been going pretty good. Yeah. So however, I've been working on this feature, which is. I wrote the initial story for, and if you listen to the podcast, you know I hate writing stories, so the story might just say, technical story, go add message consumer. That's literally it. Of course there's a lot more to it. So I finally hit the point where I'm ready to move on to my next phase of work, but I need to get a PR out. And I might've changed like 86 files and there might be like four different full processes, plus just cleanup code. So I have made my code so big, I can't send it for PR.

[00:34:06] **Carol:** I can't in any good conscience, send this over to another engineer and say, can you review this and expect them to actually understand it? So today I started breaking it out into smaller branches. and started writing smaller stories. Well, I started Breaking the Code out and I wrote one story and the story is just to change a misspelling I found because someone didn't spell successfully correctly in two spots.

[00:34:34] **Tim:** That's a hard word to spell.

[00:34:36] **Carol:** It's hard, right?

[00:34:36] **Ben:** lot of double letters.

[00:34:37] **Carol:** Yeah. Yeah. There's an extra E in there that's not supposed to be in there. And my browser kept, or my ID kept yelling at me. So I fixed it. So I broke that one out. And now I'm just down to like 78 files to still go through and build out stories for. And I am very overwhelmed. I just want to send it all up there.

[00:34:57] **Ben:** To interject, you're, you're, you're essentially retrofitting stories into the work. So you're, you had one story that became too big, but now you're actually creating new stories to account for smaller chunks of that.

[00:35:11] **Carol:** yeah, plus it really needs to be testable by my BAs and me just giving them a story I wrote myself that says add a message consumer, they're not going to have any idea what this means, even though like we've walked through the process and they understand what I'm doing, they understand what's going to be happening, they still need testable stories, I need to send it over to compliance, I need to send something to security, to the ISOs, so there's several different.

[00:35:35] **Carol:** Things that need to be added. And I was so like looking forward to just being done with this and moving on to the next step, but I've definitely backed myself into a little corner and I'm going to have to clean up a mess now. Oh,

[00:35:48] **Adam:** wonder if there's a way. I mean, so you said you've got all these changes. Were you making like commits in a branch as you were going, or is it like you made all these changes and that's one commit?

[00:36:00] **Carol:** no, there's like 42 commits total, but some of them are just merging main back in and just getting back up to date. So, I mean, some of those could be ignored, but they're not in any, like logical pattern. It was like, Oh, okay. I'm leaving on Friday. Commit, cause I don't want to risk my laptop dying. So. Now I have it there.

[00:36:21] **Adam:** So it's just a point in time commit, not so much a logical

[00:36:24] **Carol:** No, it's not like this is how we approve. This is how we create data. Like this is all my tests I've added. Cause there's also all the tests added to it and, you know, knowing whether it's coming from a message consumer versus coming from the system, there had to be some flags added to different files and adding new Git package versions, which I had to change a few times because I kept changing my data type cause I didn't know how I wanted it.

[00:36:48] **Carol:** So. There's no good way to just cherry pick commit somewhere

[00:36:53] **Adam:** That would be nice, but

[00:36:54] **Carol:** yeah. And I used to use this tool called Beyond Compare and it was great because I love it. Right. So I could have two branches. I would basically put my repo in one branch and then I would add the repo, sorry, in one folder and I would add the repo to another folder and I would just check out whichever branch I'm working on.

[00:37:11] **Carol:** And then like my main and another, then I would just do the compares and I would Push file over one at a time. I can't do that now. I'm not allowed to use that tool. So I'm having to do a compare in Visual Studio and then open the file and go put the changes in, save commits, and then do new branches. So it's very manual.

[00:37:30] **Carol:** It'll be good when it's done, cause it is getting my eyes on it again. And it'll be smaller PRs and in a way that people can actually understand what they're looking at and will hopefully give me true feedback and not just open it and go. We'll find out in production, you know, we'll figure out then if it works or not. So

[00:37:48] **Ben:** you, do you have a, QA team? I can't remember.

[00:37:51] **Carol:** yeah, we have our, so we have our own BAs and testers on our

[00:37:55] **Ben:** What is a BA?

[00:37:56] **Carol:** a business analyst, so they actually help write the stories up front, but because we spun this new team up, I just wrote my own story and said, this is what I'm going to work on and no one stopped me. So it's just where we went and no one really built stories out for it.

[00:38:12] **Ben:** I do have a question about it and anyone can speak to this, because I've never really had a formal QA team. When you're taking a large piece of work and you're breaking it up into smaller tasks, some of those tasks like literally can't be tested by a QA engineer because there's not, there's not like a user facing component.

[00:38:32] **Ben:** Or, or, you know, it's not complete, you know, maybe I'm getting this in place because the next thing that I deploy is going to consume it. Is, is it up generally to the engineer to say this requires a QA phase or, or I can bypass it, or is that usually something it's like the QA people actually have to sign off on that, not the engineer.

[00:38:52] **Carol:** So our QA people, for us, our QA people do sign off on it. but I just skip a step and I say, Hey, there is nothing for you to test. However, you are so responsible for testing that I didn't break anything else. So they still run their suite of tests. So they do everything that they normally do and they make sure how it worked yesterday, it still works today with my code in place.

[00:39:12] **Carol:** And then they approve it.

[00:39:13] **Ben:** That's funny. I mean, not to, not to circle back to the overcompensation, but like if an engineer says, Hey, I didn't touch anything that actually touches anything. You don't have to worry about this. And they're like, well, it's going to go through QA anyway.

[00:39:25] **Carol:** Yeah, so,

[00:39:26] **Tim:** know how many times people have said, Oh, I didn't really change anything big. Nothing's going to break. And then it turns out the thing that broke it was that. I've seen that so many times.

[00:39:34] **Carol:** yes. I just made the column name plural, nothing to test.

[00:39:40] **Tim:** I'll, I'll do a get blame on it. I'll message them. I'm like, did you post this? Did this code just go? They're like, yeah, but it, you know, it doesn't really do anything. It's kind of self isolated. I'm like, no, no, it's not.

[00:39:49] **Adam:** You see how we're down now?

[00:39:51] **Tim:** Yeah, exactly.

[00:39:53] **Carol:** Yeah,

[00:39:54] **Adam:** Yeah. Oh man. And so I wish I had some advice for you. It sounds like you don't have any good options.

[00:40:00] **Carol:** meh, I just, it's a lesson learned, right?

[00:40:04] **Tim:** You made your bed.

[00:40:05] **Carol:** I gotta clean it up now.

[00:40:07] **Tim:** Yeah, sleep in it.

## [00:40:08] Smoke Breaks and Build Times

[00:40:08] **Tim:** I'll go and I'm going to lead off with kind of a news item that is slightly related. This is kind of a weird thought, but anyway. So today I saw that in England they're doing a generational smoking ban. Did you hear about

[00:40:22] **Ben:** Explain.

[00:40:24] **Carol:** I don't

[00:40:24] **Tim:** So what they're doing right now, the legal age is 18 to buy tobacco products.

[00:40:28] **Tim:** So every year they're going to add another year to the smoking age.

[00:40:33] **Adam:** I

[00:40:33] **Tim:** Until it gets up to like, you know, 100.

[00:40:36] **Adam:** Right.

[00:40:36] **Tim:** So basically Pete,

[00:40:37] **Adam:** if, you're under 18 now, you will never be able to buy

[00:40:39] **Tim:** right. If you're born, I think, I forget what year it was, but, yeah, if you're under 18 now, you'll never be able to buy tobacco products. And if you're smoking now, that's fine, you know, cause you can keep buying them.

[00:40:50] **Tim:** The age keep going up and your age doesn't go down. It goes up too. So, you know, so that, yeah, right. I'm Benjamin Buttoning. and I say that to say that, you know, smoking used to kind of be. The, you know, you're working, you just want to take a break. Oh, I'm going to take a smoke break. Right. And

[00:41:06] **Carol:** They used to be called that, yeah.

[00:41:08] **Tim:** yeah, I'm going to take a smoke break.

[00:41:09] **Tim:** They go smoke. And even at our office down here, we had a, a group of people that really liked to smoke. And we had a smoking gazebo and they'd go out there and smoke in the gazebo. And a lot of times if you like had to find, like, I really need to talk to someone like where, oh, they're out there. So I'd go in the gazebo and bug them,

[00:41:28] **Carol:** Side side note, how many times should they catch that gazebo on fire? Heh

[00:41:32] **Tim:** I think just

[00:41:34] **Carol:** heh heh

[00:41:34] **Carol:** heh

[00:41:35] **Adam:** And is it now the vaping gazebo? Um,

[00:41:40] **Tim:** You know, in one way, you know, smoking is obviously bad for you, but it's nice to take a break from work and to have an excuse. And last week I was working on our Scala projects and there's tons of microservices in it and I have a script that like spins them up, you know, and it just takes, you Sometimes 10 to 15 minutes to get everything up and running.

[00:42:01] **Tim:** When I compile, right? If I make a change, I've got to compile. It recompiles everything. It could be five minutes or, you know, if it's just for one service, but I have to do all services, it could take like 15 minutes. And I'm like, well, I don't really want to do anything else right now. My emails are answered.

[00:42:17] **Tim:** I'll take a break. I'm like, is, is code compile like the new excuse for a break?

[00:42:22] **Carol:** If your compiler's bad, yes. Heh heh heh

[00:42:25] **Adam:** or, or if you're using stuff that just takes forever to compile. Yeah. I mean, I have, I have, I do something similar, right? You know, I have a Docker containers and we have, you know, whatever it is, like 15 Docker containers that if you're doing all of the little things, if you're testing all of the little things at once, you know, you might need all 15 Docker containers in your local development environment, and it may have been months since the last time that you rebuilt them.

[00:42:46] **Adam:** So you need to just like, you know what? I need everything. Just blow it all away. Start from scratch. and build everything for me. And that, yeah, that can take 15, 20 minutes. And it's like, I could go do something else. I could start on another task, but then I'm probably going to be, you know, elbows deep in that one and completely forget that I was over here doing this.

[00:43:05] **Adam:** And this is actually more important. So it's, it's like better for the, the important project for me to just take a five minute break and come back. You know, like go to the bathroom, get a drink, walk around the house, walk a lap around the house to, to get some blood pumping and come back. And you know what?

[00:43:20] **Adam:** I, I don't actually ever think of it as a smoke break anymore and I don't smoke. but I have no qualms about saying I'm taking a smoke break, right? Like, back in the day when I was, when I had coworkers and worked in an office and people would take smoke breaks, I'd be like, okay, well, I'm taking my smoke break now and I would just go walk around the parking lot or whatever, and if they get a smoke break, I should get a smoke break, right?

[00:43:43] **Adam:** Even if I'm not

[00:43:43] **Tim:** And that's one thing that bothered me at work. Well, you know, when we were in the office, like they'd be out there and they'd get talking and they're out there smoking for six, seven minutes, 10 minutes or whatever. And it's like, I haven't got out of this chair in five hours, right? I'm getting out of this chair, the same feeling like, yeah, if they get a smoke break, I'm going to, you know, take a walk around, you know, play some foosball. So,

[00:44:04] **Adam:** Yeah, for sure. Pick weeds out of my garden or

[00:44:07] **Tim:** Yeah, I'll do that now.

[00:44:08] **Tim:** I'd get up, you know, go check the pool, go check the plants, water a few plants, whatever, look at the bird feeder, kiss on my wife, you know.

[00:44:17] **Adam:** I like to come over and kiss your wife too. Yeah.

[00:44:19] **Tim:** you, no, no.

[00:44:23] **Ben:** That's too many states away. Come

[00:44:25] **Adam:** Yeah. That's a long drive to go for a kiss.

[00:44:27] **Tim:** Yeah. Yeah.

[00:44:28] **Ben:** I was listening to a podcast the other day. I don't remember which one it was. And they were talking about compile times for Shopify. That Shopify has a pre deployment linting process that takes something like 90 minutes to

[00:44:43] **Carol:** It's nuts,

[00:44:43] **Tim:** Whoa.

[00:44:44] **Ben:** have to, they, they compensate by, by breaking it up and spreading it across like 40 different servers or something.

[00:44:51] **Adam:** That sounds very familiar.

[00:44:52] **Ben:** That's bonkers. I have just

[00:44:54] **Tim:** a long smoke

[00:44:55] **Ben:** for that kind of stuff.

[00:44:56] **Carol:** when I was here before, cause I worked where I'm at now as a contractor before I came here as a fed, the laptops we had were really bad, so I knew whenever I needed to compile code on my local, it was just go ahead and take a lunch cause it was just gonna bog down everything.

[00:45:10] **Carol:** Like I couldn't check email, like nothing else would run on my computer, like while this was happening. Now they're a lot better and now our projects are a lot smaller. Oh, we still have. 50 projects in the main, the main project though. So, but it does not take 15 minutes to build. It's very quick. Yeah.

[00:45:28] **Adam:** Yeah. I mean, I, I'm not at all dissing on Shopify. I'm sure that they have a ton of amazing engineers and there's a reason that their build process is what it is, but to me, not knowing any more than what we've already discussed. If, you know, if you told me my build process takes 90 minutes before it even starts, or just like the linting process before, I'd be like, there is something wrong with that, right?

[00:45:49] **Adam:** Like, clearly,

[00:45:51] **Ben:** I'd be like, how can we delete most of this code immediately?

[00:45:54] **Adam:** yeah, right? Like, I need

[00:45:56] **Tim:** No, Ben, you'd be like, linting's a waste of time. Let's

[00:45:59] **Ben:** Well, that's why we can delete it.

[00:46:03] **Adam:** need deploys to be like 10 minutes at the most, right? Like two minutes would be better, but, and that's from like the time that I push to the time that it's running in production. That would be awesome. And that way, like, It does give you a little bit more freedom, right? Like if you can keep the build times fast, then you can, be slightly more cavalier with, you know, okay.

[00:46:23] **Adam:** Looks good in the code review, right? Like clearly you're not trying to rip the company off. You're not trying to take a fraction of a penny of every transaction and put it in your own account, right?

[00:46:32] **Tim:** Superman three.

[00:46:34] **Adam:** And, and, and so like, okay, you know, your intentions are good. The code, I don't see any obvious problems in the code.

[00:46:42] **Adam:** Let's just push it to production and see what happens. Isn't it a worst case? Then we, it costs us five or 10 minutes of downtime while we're, pushing a fix. Yeah, I don't know.

[00:46:51] **Ben:** I think, I, I mean, this is narrow minded thinking, I assume, but I, I feel like people just get really used to having a lot of friction when they work and that just, it's like a boiling the frog problem.

[00:47:05] **Carol:** What do you mean?

[00:47:06] **Ben:** it's like the stuff that people are comfortable with sometimes is kind of shocking to me.

[00:47:13] **Carol:** Like a 90 minute build. Like you shouldn't be comfortable

[00:47:15] **Ben:** but it's like that probably happened because it happened really gradually and slowly.

[00:47:20] **Ben:** And by the time it gets to such an outrageous timeline, you're just sort of used to doing things that way.

[00:47:26] **Adam:** right. don't, you don't know that it could be any better. So you just accept it or like you were hired and it's like, okay, well, you know, our builds take half a day, so we do deploys once a day,

[00:47:36] **Ben:** You know, I was so irritated one time at work. So the monolith, occasionally, occasionally I get irritated. So the monolith at work, ColdFusion, JVM, you know, beastly machines. And people are always like, Oh, it's so slow. Deployments take forever. And then they started building new services and Node and Golang.

[00:47:55] **Ben:** And I remember working with one of the teams at one point and they were deploying Go services and the deployments took longer than the cold fusion deployments. And I was like, what is going wrong with you people? Like this is nuts. You, I thought that was the dream is that your deployments would be like a 30 second deployment.

[00:48:13] **Ben:** And now you're waiting around 15 minutes for your deployment. I just, I don't know. Yeah,

[00:48:21] **Adam:** Honestly, like, it's funny because. That's one of the things that really frustrated me, you know, with, with ColdFusion CFML is the startup time, right? You know, you, you say, okay, start the ColdFusion server and it's five minutes before it's ready. even on like a really well powered developer laptop, maybe not five minutes, but you get my point.

[00:48:38] **Adam:** versus, you know, you say node index. js and now it's ready, right? Like, and to go from that stark comparison, but then you're like, okay, so in order to get my node app ready to run in production, I have to put it in a Docker container and we have to do this and that. And, and, you know, we have to run npm install inside the Docker container.

[00:49:00] **Adam:** And, like, all the little, little things, it's like death by a thousand paper cuts, and then you, you end up with the same build time. And it's, it kills me, because it's like, but the app is so fast!

[00:49:11] **Ben:** I forgot how we got here.

[00:49:13] **Adam:** I don't know.

## [00:49:14] Mentoring

[00:49:14] **Adam:** So maybe I'll just go with my thing. so,

[00:49:16] **Tim:** I've done with my smoke break.

[00:49:19] **Adam:** Welcome back. so the thing that I wanted to talk about was mentoring, right? So I've mentioned on the show, I hired this new co op. He's a student at a local university in Philadelphia. he's a very smart kid. and, things are overall going really well.

[00:49:35] **Adam:** Like I said, he's very smart. He's got great JavaScript fundamentals. he works pretty fast. What I'm finding difficult is, I find myself working sort of in two modes with him. I either find myself having to, like, sort of pair program with him to help him learn something that he's just, like, never seen before.

[00:49:52] **Adam:** you know, he needs a lot of, kind of, hand holding to get off the ground. Otherwise, it's like, okay, well, here, read the CF Whack, and now you know ColdFusion. Well, that's a lot to ask of somebody, right? And so we're doing pair programming, which is intensive on my time. I can't really multitask because I have to be paying attention to what he's doing and helping him figure stuff out, which is fine.

[00:50:12] **Adam:** That's what I signed up for. But then, he's so good at the stuff that he doesn't need my help with, right? So either I'm pair programming with him or he's doing async work. And the stuff that he can do async is so good at it that I can't stay ahead of him. I'm constantly, I'm constantly like, okay, I need you to slow down for five minutes.

[00:50:33] **Adam:** Go take a 10 minute break so that I can come up with some more tasks for you. Because, I don't know. It's just, it's frustrating and it's hard to figure out.

[00:50:42] **Carol:** Is this why you bought us chairs to put together, Tim?

[00:50:46] **Tim:** exactly. I mentioned that when you weren't here, like, not like Adam. Now, you know why we had to put chairs together.

[00:50:53] **Carol:** And they only gave us like three computers to share. So you had to take turns like working through problems or you had to go sit with someone else, but you couldn't be like full on dedicated to what you were working on. Cause I didn't really think about that. There probably wasn't the resources around to help someone all day long.

[00:51:09] **Carol:** Like they had their work to do too.

[00:51:11] **Adam:** You put together these 10 chairs, but you only get one Allen wrench.

[00:51:14] **Carol:** Yeah. And you need three smoke breaks.

[00:51:16] **Ben:** true. Pointing people to a, how do I learn a new thing resource was really challenging. Yeah.

[00:51:29] **Adam:** I can either take a bunch of time and write down everything. I can imagine that he would need to know with like links to various other repositories, like specific lines of code on GitHub, you know, documentation for this and that, or I can spend the time pairing with him.

[00:51:43] **Adam:** And obviously there's gotta be something in the middle, right? I need to find that like juicy middle ground to, to. Feel like I'm able to help him learn and get going, but also have time where I can get my own work done.

[00:51:57] **Carol:** Well, this kind of goes back to what Ben said, like, is it worth letting him flail a little? Like, let him just Google for a few hours and figure it out and say, you know, from, for these four hour window, I'm really like working on something else. So just do some research, see what you can find out, and then come to me with a list of like very direct questions.

[00:52:19] **Adam:** yeah. And I think maybe part of the reason that I haven't been doing that is that most of his questions, not all of them, but most of them end up being very specific to like our code, our

[00:52:30] **Carol:** Oh, that's harder, right? Yeah.

[00:52:32] **Adam:** do I, how do I know which snitch belongs to this function or whatever, right? Like, Although it is occurring to me now, maybe I could ask my other coworkers that are sort of at my similar tech level, if I can kind of pass him around, right?

[00:52:47] **Carol:** Oh, that would be great. Yeah.

[00:52:48] **Adam:** know, like I will set his tasks and I'll just say like, okay, when you're working on this one, Chad can help you. When you're working on this one, Adam can help you, whatever. But that would

[00:52:59] **Carol:** Yeah. I, I don't think people understand the dedication it takes to bring on someone, with very little knowledge of how the tech world works just in the day to day operation. I mean, explaining pull requests to someone who doesn't really know that. They may understand some language they've learned in school.

[00:53:16] **Carol:** They may have some tech background, but teaching them your application. They're not going to learn that in school. The internet's not really going to help them with that. You have a bunch of homegrown things. So it's not like he could just Google even those. So the bringing someone in very new is hard.

[00:53:33] **Carol:** And I think that's why a lot of companies lean toward bringing in senior level people because it's easier to teach them a specific application when they already know how to write code. And they already know how to be an engineer and a developer. All they have to do is now teach them their company.

[00:53:48] **Carol:** Which is bad. It's bad for our people coming out of school, but that's kind of just what I've seen.

[00:53:54] **Adam:** Yeah. And, and I mean, honestly, that was a big part of the reason that we decided to go down this path of Getting a co op from the university because we knew it would be hard and we knew we would have to figure this out. So, but what it will do is after we do figure it out, it'll give us sort of a pipeline of new talent to hire, right?

[00:54:13] **Adam:** You know, we, we kind of got to the point where it's like, okay, well, we've hired all of, Our friends that are senior developers that are available. so now what, right? Now, now who can we hire? And

[00:54:24] **Carol:** coming on the market soon, I hear. Wink, wink, nudge, nudge.

[00:54:28] **Adam:** Dibs, and, yeah. So, so, you know, we have to develop our own, you know, like a farm team, basically. And so basically what this is, is like, yes, you know, we're helping out the community. We're helping out with the training for the school, this particular person that we hired. That's great, but one of the things, one of the benefits that my company is getting out of this experience is that we are learning how to hire somebody who is at the skill level of, I am still enrolled in college.

[00:54:59] **Adam:** for learning this stuff and helping them get the, the real world skills. Like they have fantastic fundamentals. I mean, this guy knows TypeScript, he knows JavaScript. you know, ask him recursion stuff or, you know, anything technical like that. He's got it.

[00:55:14] **Ben:** Well,

[00:55:15] **Adam:** when you like, drop him into the application and say, I need you to do this.

[00:55:18] **Adam:** He's like, uh, uh, I think I can figure that out.

[00:55:22] **Ben:** is there a way that maybe you could, Take some of the things that need to be done and Isolate them in a way that he's not working on the app directly, but he's sort of exploring solution space. And then maybe he can do that on his own. And then, then the pairing with him would be, okay, now how do we take the idea that you created and integrate it into the app?

[00:55:47] **Ben:** I'm, I'm, I don't have anything. You know, if he had to do some sort of a, like data transformation, like JSON file and say, consume this JSON file and help with this other thing, or. You know, in the future, this will be an S3 object, but for now, it's a file on your local file system.

[00:56:03] **Adam:** I think, yes. My initial gut reaction was like, you know, the amount of work that that would take to, to make that possible.

[00:56:10] **Carol:** build that up, yeah. Yeah.

[00:56:13] **Adam:** like, Extract out a, a task from the application, let them work on it, and then put it back into the application is kind of what they ask. But I mean, so for example, something that is sort of like on the, hopefully he'll be able to get to this at some point, list of ideas is, you know, we have a WYSIWYG editor for emails, right?

[00:56:35] **Adam:** And it's not our editor. actually, you know, let me change that. So, something that happens is we have our in built support ticket system and, people struggle with, attaching screenshots. You and I know you can just hit print screen and, and, like use a million

[00:56:54] **Carol:** Oh, yeah,

[00:56:54] **Adam:** to

[00:56:55] **Carol:** all

[00:56:55] **Adam:** that as an image file.

[00:56:56] **Carol:** Adam? Tell us how to do it.

[00:56:58] **Adam:** Well, it depends on your system, right? So on Mac, you can do command shift three or command shift four and, and save it as a file on your desktop. No problem. on Windows you use like, what is it? A snip, snipping tool, something like that. I don't know.

[00:57:09] **Carol:** Yeah. That's the only way I can make it work is if I use Snipping Tool. So I have it pinned to my startup menu.

[00:57:16] **Adam:** let me tell you the number of times that I have received a support ticket with a Word doc attached and a screenshot in the Word doc. It just makes my blood boil because then the, the image has been like, I don't even, it's like blurry and crappy and you can't really make out what it is in there, you can't like.

[00:57:33] **Adam:** Expand the image and for whatever reason, it just loses clarity. I don't know why, but I don't know. It's awful. So one of the things that we want to do, the like, you know how, when you're on GitHub and you're leaving a comment, you can just paste an image in, right? You take a quick screenshot and you just paste it and they recognize what you're doing, they upload the file up to wherever it's probably on S3 or something.

[00:57:55] **Adam:** And then they drop in a link all within like a second of you hitting command V. that is totally doable. With today's technology in a browser with like just JavaScript basically. and I, we've never done it, but it's like, that would be so awesome if we had that functionality in like 20 different places in our application.

[00:58:13] **Adam:** So now that I'm thinking, based on what you said, Ben, I'm thinking like, okay, I need to give him the spec of like how that works and say like, figure out how to do this, right? I'll give you, some examples of how you can take an image. And S3 and get the URL back. Cause that's, that's a solved problem. I don't need you to figure that part out.

[00:58:32] **Adam:** What I need you to figure out is how do we go from somebody pastes an image into a text area to upload that image and get the URL back for it. Yeah. Okay. I like this.

[00:58:42] **Ben:** But that's good, because, you know, he'll struggle in a good way. You know, there's gonna be a lot of holes in his understanding. And he'll have to figure that out.

[00:58:49] **Adam:** Yeah. And, and I like the idea. I really like the idea of, like a, a project that we expect to take a while. Now, honestly, this guy, I would, I would expect him to like finish it in like a week where, where me, I'd be, I would be planning to spend a month on it, you know? I dunno, maybe, maybe I would do it in a week and he would do it in a day, but you get the point.

[00:59:07] **Adam:** I

[00:59:07] **Ben:** Alright.

[00:59:09] **Adam:** think that's all I got about that. I'm, I appreciate you guys input. The, it definitely gives me some things to, honestly, what I need is time to process what we've been talking about and, and get ahead of him with some of this stuff, although I feel like I might have bought myself that I kind of like just spent my entire day today, just like typing up, okay, do this and then do this and then do is how you test this and this is all that.

[00:59:30] **Adam:** I

[00:59:31] **Carol:** Well, kudos to you and your company for bringing on interns and

[00:59:35] **Ben:** Yeah, absolutely.

[00:59:36] **Carol:** think that's huge for our market and for our, our careers and our peoples.

[00:59:43] **Adam:** agree, but I will also be the first to admit that it is not entirely unselfish, right? We're, we're doing it too because it's, it's good for our company. So,

[00:59:51] **Tim:** It's that, that, that's a win win

[00:59:53] **Adam:** yeah, man.

[00:59:55] **Tim:** and actually, um, company you used to work at, Carol, they're, they're starting back the intern program.

[01:00:00] **Carol:** yay. That's great to hear it. They have some, some good like schools in the area to help market from. So

## [01:00:07] Patreon

[01:00:07] **Adam:** alright, well, it sounds like we're done, so I'm just gonna, I'm gonna cut it off there. this episode of Working Code was brought to you by truck nuts, and other forms of overcompensation, and listeners like you. If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:00:24] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them, and I promise your stickers are coming. By the time you hear this, they will be ordered. I don't know

[01:00:37] **Tim:** We haven't even ordered them.

[01:00:39] **Adam:** Well, I don't know if it's gonna be like a, a, print and, you know, I'll just have it print and deliver all, like, you know what I mean?

[01:00:46] **Adam:** Like, not Don't go through me, yeah, I don't know the words. Words are hard, but yeah, something like that. Like a they never touched my hand sort of situation. Anyway, they're coming. I promise. special thanks to our top patrons, Monte and Giancarlo. You guys rock. we're gonna go record our after show.

## [01:01:01] Thanks For Listening!

[01:01:01] **Adam:** Look, Carol's playing with a Rubik's Cube, and I have questions. So, we're, that's definitely bound to come up on the show, on the after show. if you would like to hear the after show, you can go to patreon.com/workingcodepod, all of our patrons at every support level, get the after show and we appreciate each and every one of you.

[01:01:21] **Adam:** That's going to do it for us this week. We'll catch you next week. And until then,

[01:01:24] **Tim:** remember your heart matters, even if you feel you're overcompensating for something,
