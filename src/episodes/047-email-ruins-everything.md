---
title: "047: Email Ruins Everything"
description: This week on the show, the crew talks about different communication styles, Inbox zero, email as a delivery mechanism, and the not-so-surprising surprising way that Zoom calls can supercharge our ability to get stuff done!
date: 2021-11-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/gb/podcast/047-email-ruins-everything/id1544142288?i=1000540612610"></iframe>

With an increasing amount of work being performed within a distributed or hybrid team model, there's a push to move more and more communication into an asynchronous workflow. Whether through email or collaborative document editing, there's a growing perception that collaboration becomes more efficient when each person can participate in their own time. But, is this really true? Or, are we fooling ourselves into thinking that the cost of "homework", "email fatigue", and extended delivery timelines are outweighed by one's ability to go "heads down" at work? This week on the show, the crew talks about different communication styles, Inbox zero, email as a delivery mechanism, and the not-so-surprising surprising way that Zoom calls can supercharge our ability to get stuff done!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/047-email-ruins-everything.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** that's amazing. So then now I appreciate your like approach towards email's a lot better,

[00:00:05] **Tim:** Yeah.

[00:00:05] **Tim:** I'm trying to protect the developers. I want the developers to be in the perfect condition where they can just focus on what they're doing and not worry about all the other stuff, you know, I'll inform them what's going on afterward any of the week. We sort of have a debrief and say, all right, here's what's going on.

[00:00:20] **Tim:** And they're completely surprised that there was all this thrash and churn, right? All this, you know, all this terrible stuff going on. That's like, don't worry. We handled it. You don't have to worry about it. Here's what you work on next week.

[00:00:31] **Adam:** The recording of Steve Vollmer going developers, developers,

[00:00:35] **Adam:** developers,

[00:00:36] **Adam:** developers,

[00:00:37] **Tim:** For sure.

## [00:00:55] Intro

[00:00:55] **Adam:** Okay. Here we go. It is show number 47. And on today's show, we're going to talk about how communication can just destroy your flow state. but first as usual, we're going to start with our triumphs and fails. And Ben, it's your turn to go first, man. What's going on?

## [00:01:09] Ben's Triumph

[00:01:09] **Ben:** And I'm going to switch it up from the last few weeks. I'm going to kick it off with a triumph. And that is that I released something at work and it was exciting. And, I think I've talked about this in the past that I've been very cautious about being loud about the things that I released because of the kind of political climate at work.

[00:01:28] **Ben:** And, you know, I don't want to, I don't want to pop my head up and let it be, reprimanded for maybe stepping outside of my purview. but I've been slowly and. Quietly releasing things over the last few weeks and nothing bad has happened. So I'm now just kind of throwing caution to the wind and, I'm loudly and triumphantly releasing things in our slack channel.

[00:01:52] **Ben:** And, and I'm really trying to celebrate the little victories with those releases and the, and the user experience improvements, which I, I hope they bring to the customers. And, I'm going back to the idea that if, if people can see me joyous and see me celebrate, then it will, it will give them permission to do the same.

[00:02:08] **Ben:** So

[00:02:09] **Tim:** We have that feature flag.

[00:02:10] **Carol:** I like this.

[00:02:11] **Ben:** It's right.

[00:02:12] **Carol:** So is this like your own roadmap? You've created that you're working on, like, I'm just going to achieve these things and this is what I want to do and I'm happy doing it. Or are these things that like the business knows are being done?

[00:02:22] **Ben:** a, you know, it's not a hand wavy stuff here. there are things that I've wanted to do for a long time in the application that have never, we've never really prioritized time to. There's stuff where I've been talking to a customer and they'll mention something like, oh, wouldn't it be nice if you know, XYZ happened?

[00:02:39] **Ben:** Or this has been always a point of friction for us. So I write those things down and then I let them percolate in the back of my mind. And I, and I, you know, iterate on them mentally. And then I get to a point where like, oh, I can start to see it in my head. And I want to put it into the application. And, you know, I'm, I'm picking things that feel like they're media enough to have a substantial value add for the customer, but not so large in scope that I don't feel like I'll ever get it done in my team, which is a very, very small team inside of a much larger company.

[00:03:10] **Ben:** So it's, it's,I'm excited, but

[00:03:12] **Carol:** sounds like great wins.

[00:03:14] **Ben:** it is great winds, but there's always, it's weird. I don't know if anyone else feels this, but every time I have some sort of victory, there's always like a little bit of a postpartum depression where it's like, you birthed this beautiful thing until.

[00:03:28] **Ben:** And I dunno if it's like, you're coming down from the high of all that, but there's this, this like right after you release something before you really even get any feedback, you get this, I get this little mellow where I'm, it's like, I'm almost sad that the adventure is over.

[00:03:43] **Tim:** kids have left the nest,

[00:03:45] **Carol:** Oh, no, no, I get, I get panic. I get that. Oh, shoot. Is this going to work now? It's in production. What did we not catch? Like what differed between the two environments and

[00:03:57] **Ben:** totally understand that feeling for sure.

[00:03:59] **Carol:** yeah.

[00:04:00] **Adam:** Then you were such an IFP,

[00:04:02] **Ben:** what's an infe.

[00:04:04] **Adam:** like the Myers-Briggs personality type

[00:04:06] **Carol:** Oh, we should talk about that one

[00:04:08] **Tim:** Introverted, intuitive feeling.

[00:04:13] **Adam:** I forget the P perceptive.

[00:04:14] **Adam:** yeah,

[00:04:14] **Ben:** Oh yeah, that sounds good. I like that. I, I relate to those words.

[00:04:18] **Carol:** very fitting

[00:04:20] **Adam:** then, so the exact opposite in those four categories would be STJ extroverted.

[00:04:24] **Tim:** it's just funny. I alternate between those two,

[00:04:26] **Carol:** Really?

[00:04:27] **Ben:** I

[00:04:27] **Tim:** depending on the day.

[00:04:29] **Ben:** like when you all talk about, I don't know what this scale is, but sometimes you'll talk about chaotic evil and

[00:04:35] **Adam:** Oh, yeah.

[00:04:35] **Adam:** Yeah. The alignment chart.

[00:04:37] **Tim:** does this, the, dragons?

[00:04:39] **Ben:** oh, is that what that's from? I like that that's that sounds fun. Someone, I think Adam, one time referred to somebody as, as like chaotic neutral.

[00:04:47] **Adam:** Chaotic. Good. Yeah. I referred to Adam Cameron, is that yeah,

[00:04:51] **Tim:** yeah, Pretty much, pretty much. Whenever I play a role playing, I'm always chaotic, neutral. I just love messing stuff up

[00:04:58] **Adam:** just for the.

[00:04:59] **Tim:** just for the laws. I don't really have an agenda.

[00:05:03] **Carol:** troll.

[00:05:03] **Ben:** all right. Well,Tim throwing it over to you. What do you got going on this week?

## [00:05:06] Tim's Triumph

[00:05:06] **Tim:** so I'm going to take a page out of your book, my brother,

[00:05:09] **Ben:** Noise.

[00:05:10] **Tim:** go for a triumph. So, you know, we, I went to Vegas a couple of weeks ago and we had a really nice, and we spent a load of money at a trade show. I mean, more than we ever spent before we had a beer garden. And I mean, it was packed. People were just coming, you know, you give out free beer and people are going to show up.

[00:05:28] **Adam:** Especially in Vegas.

[00:05:29] **Tim:** Yeah, for sure. As the only place you could have got beer on the, on the expo floor. So we were very popular, area, but I mean, at the same time, it's like we were engaging people. We're talking to people and just telling them what we're doing and this, the product we're really we're featuring is a product that, I started as a skunkworks about three, four years ago, maybe even five, honestly.

[00:05:50] **Tim:** and now it passed hands. I, you know, I moved roles, so I didn't have it for a while. Now I have it back and just generate excitement for it. Now we're getting. RFPs request for proposals of people just saying, Hey, we heard about you do this solving a very big industry problem. That's, you know, paying claims people that, you know, maybe it's a mortgagee check.

[00:06:13] **Tim:** You know, sometimes you get a check. If you have a claim on your insurance, they, they send you a check and, it's you and Wells Fargo. Right. So how do you solve that problem? How can you do that digitally rather than just, you know, physically waiting two to three weeks while you try to figure this out?

[00:06:26] **Tim:** so yeah, it's been, I mean, getting tons of response from that and just, it's super exciting to really see a product that you just saw as a, you know, an idea years ago and just worked. And it went through a lot of ups and downs of getting it adopted and it was a skunkworks. So I really technically, I shouldn't have been working on it.

[00:06:46] **Tim:** I built a prototype. And showed it off and you know, that I didn't get in trouble for it, but it was kinda at the same time, like, well, you know, why you're you working on this? Well, I'm working on this because I think this is the next big thing. And now there's huge interest in it. and it kind of reinforces the fact that I was right in my gut instinct that this is going to be industry thing going on.

[00:07:07] **Tim:** And it just, just, I mean, it's so exhilarating to see, at the same time we took a long time to, try to build this right. Those we really could have, we could have been the first honestly, if, if, if we had done it, if I was given full resources to do it, but we weren't. Political reasons in internal reasons, whatever.

[00:07:26] **Tim:** I mean, there's people ahead of us. So, but now we're getting these RFPs. I can act in talking to competitors and I can see where our gaps are and we're not that far off. So there's things where I'm like, all right, I didn't read even realize this was a use case. And these RFPs come in and they tell you exactly what they're expecting, which is great because now I know, okay, we need to build this and we're not far off and it's not going to be hard to get there.

[00:07:49] **Tim:** So just super excited. I just, it just makes me energize when you can build something that solves a real world problem that affects people and, you can actually fulfill it. So it's super happy about that.

[00:08:00] **Carol:** That's awesome.

[00:08:02] **Ben:** Yeah, very cool.

[00:08:03] **Carol:** Yeah.

[00:08:04] **Carol:** you and Ben kind of go together on your triumphs there.

[00:08:07] **Tim:** Yeah. Well, he released the thing I've been working on this thing five years, man, five years. That's a lot. It's been a, it's been a journey, dude.

[00:08:16] **Ben:** No, that's so exciting. And, and I think what it also proves, and we've harped on this a whole bunch of times that the whole concept of never let great be the enemy of good that if you, if you waste all of your mental cycles, thinking about how you're going to create the perfect product, then you just, you never get there.

[00:08:34] **Ben:** And sometimes you got to just put something together, put it out there, have people look at it so they can tell you what it is that you're missing, or they can have suggestions about what would be nice to have. And then you can really iterate. And I I've been leaning just so heavily into that. The last, I want to say like year or two, and it's been really just such a huge value add for my ability to produce stuff at work.

[00:08:56] **Ben:** sometimes I don't even see the solution in my head. I'll have only a vague idea of what I'm even trying to do. Like I can see the direction I want to go in and I literally have to write code that puts data on the screen so that I can start calling. So that I can be like, okay, this isn't going to work.

[00:09:13] **Ben:** Or like, I was going to have some sort of filtering here and that doesn't make any sense or it's a terrible user experience. And just by getting stuff on the screen, that's junkie, you can finally see what the right path forward is. And I don't know, there's, there's just so much value in the momentum of moving forward.

[00:09:28] **Tim:** You're so Right. I mean, I learned so much just from talking to people and just saying, they're like, oh, it does your, your pro I explain what the product does. And then they ask a question and I realized the question is actually a need. Right. So there's, there's some issue that it's like, what, so what if you're, what if you're sending the claim?

[00:09:43] **Tim:** So it's a claim, but there's an attorney involved and the attorney's actually going to be the one to distribute the funds, which I didn't know

[00:09:49] **Tim:** was a thing I didn't think about. Right. So as soon as that comes up, it's like, I come back and like, I talked to our team and they're like, no, no, we can definitely do that.

[00:09:57] **Tim:** I mean, we're not doing it now, but it's not, it's not hard to do. So it's like, and then, like I said, the RFP like uncovers all the other wishlist items. That people have that we didn't know about. So it's super exciting to find that style, find that stuff out, which you don't, when you're first just kind of baking an idea in by yourself.

[00:10:15] **Tim:** You don't have,

[00:10:17] **Adam:** That process that you were describing Ben about sort of iterating to find the, the feature or the product when you don't really know what it is yet. I was, as you were describing that I was thinking, you know, that wouldn't really fit a TDD.

[00:10:32] **Ben:** When you were saying that, I was just thinking that.

[00:10:36] **Adam:** Like, I think for TDD to work, you really have to know what it is that you're building

[00:10:41] **Adam:** upfront.

[00:10:41] **Carol:** you gotta know your solution.

[00:10:43] **Tim:** I think when you're green Greenfield, just kind of building a prototype, you don't TDD, you just, you just build something and see, see it work. And then you, when you build the

[00:10:52] **Adam:** So. All right. Well, let's, let's, we'll put it on the list to we'll find a TDD expert, somebody who wants to come on and talk with us about it. And we'll, we'll come back to this because that's something I would love to talk about. And I feel like we could talk about that easily for hours.

[00:11:05] **Tim:** Alright, so that's me, Carol. What up?

## [00:11:08] Carol's Triumph

[00:11:08] **Carol:** Yo, I'm going to be the third triumph this week. I'm not. Yeah, yeah. Right. So nothing technical,

[00:11:16] **Adam:** pressure on me.

[00:11:17] **Carol:** I am a Spartan now. And if you don't know what that is. Yeah. Yeah. So we competed this weekend.

[00:11:23] **Adam:** people down holes or.

[00:11:24] **Carol:** yeah. Hardcore total bad-ass yeah.

[00:11:27] **Adam:** She didn't get the reference.

[00:11:29] **Carol:** oh, I guess I was this a movie thing. Oh

[00:11:31] **Tim:** three, it's a 300 movie reference.

[00:11:34] **Carol:** Okay. Yep. Nope. Sorry. Didn't get that.

[00:11:37] **Carol:** Okay. So there's this race you can do. So we did the 10 K version, which is called a super, so we did the super version of it at 10 K 29 obstacles of this 29. I mean, it had some help from two guys I was with, but 23 of the obstacles I was able to complete. So two of them, I did the penalty for and a couple, I just, I couldn't even manage the penalty.

[00:11:57] **Carol:** I was burnt.

[00:11:58] **Tim:** So what kind of obstacles we talking about here?

[00:12:01] **Carol:** Yeah. Like mud crawls, rope climbs, monkey bars, sandbag carries lots of stuff. Barbara crawls. it's hard. If, if you could see

[00:12:12] **Tim:** Like bootcamp?

[00:12:14] **Carol:** you would know. Yeah. The guys I was

[00:12:15] **Adam:** Oh yeah. Look at that, Bruce.

[00:12:17] **Carol:** you see these bruises. Yeah.

[00:12:18] **Ben:** geez.

[00:12:19] **Carol:** Yeah. The guys I was with are army and they're like, you know, most of this stuff we aren't even allowed to do.

[00:12:24] **Tim:** Wow.

[00:12:25] **Adam:** So you, you mentioned penalties, what's that about?

[00:12:28] **Carol:** Yeah. So if you don't do it, you have to do 30 burpees or you have to, or you

[00:12:32] **Adam:** you don't do what? Like, there were a particular challenge.

[00:12:35] **Carol:** Yeah. Look, if you can't, if you can't do the obstacle, the penalty for it to, to keep going is 30 burpees or it's penalty laps. So a couple of the opt to two of them have penalty laps in place of, burpees.

[00:12:48] **Adam:** but if you can't like, if you're too exhausted and you can't do the burpees or the labs, then you're just done.

[00:12:51] **Carol:** I was too spent. Yeah. I was like, I give up, I'm still going to say I finished, but I totally didn't do the last two obstacles and did not do the burpees for them.

[00:13:01] **Carol:** I'm still, I still, I still have the metal. Yeah. I know for people who compete, who are like, you know, honest with themselves, they do the burpees. Yeah. So I'm, I'm happy with it.

[00:13:12] **Carol:** Yeah. And push myself hard. Thank

[00:13:14] **Adam:** I, I, yeah, I, the word

[00:13:16] **Tim:** I lost 2000 calories just listening to It So

[00:13:20] **Carol:** It was hard. I totally napped after I was dying.

[00:13:23] **Adam:** Your, your commitment to your fitness is inspirational.

[00:13:26] **Tim:** for sure. yeah. I'm just, I'm a slob.

[00:13:29] **Carol:** gotta be.

[00:13:30] **Adam:** I got that dad bod

[00:13:32] **Tim:** Right.

[00:13:34] **Carol:** All right. What about you, Adam? Can you hold it together for us and make us winners? Oh no,

[00:13:41] **Adam:** ring the bell. It's four triumphs.

[00:13:42] **Tim:** whew.

[00:13:44] **Carol:** Um,Winner, winner chicken dinner.

## [00:13:47] Adam's Triumph

[00:13:47] **Adam:** so this week I have been writing lots of tests or writing lots of tests. And, even though I haven't been doing great at my, self, commitment to try and read the TDD book, like one chapter a day. I. And I'm feeling very motivated to get back to it. so I'm just like, I'm happy. This is a good thing for me.

[00:14:04] **Adam:** I'm in a good place with testing. I'm struggling. Right. I feel like every time that I start to feel confident that I know like, okay, I finally cracked the nut. I understand how to mock anything now. I then hit a wall and I'm stuck for like an entire day on something stupid again. And of course I'm stuck on something again today, but, writing tests and I'm getting through it and I'll figure it out.

[00:14:26] **Adam:** And I'm just happy that I'm,pushing through making testing part of my life.

[00:14:31] **Tim:** I still want to pair program with you and want you to do it. Cause you know, testing, I still struggle with it a lot. So.

[00:14:38] **Adam:** Well, you got time tomorrow.

[00:14:40] **Tim:** Sure. I actually know I'm doing a stretch. I'm doing a stretch session on pretty much All day, but next week I got time.

[00:14:46] **Adam:** Alright. We'll find some time.

[00:14:48] **Tim:** Right.

[00:14:48] **Adam:** Cool.

[00:14:49] **Carol:** Fun.

[00:14:49] **Tim:** also, man.

[00:14:50] **Ben:** Yeah,

[00:14:51] **Carol:** we're all winners and I am so happy right now.

[00:14:54] **Tim:** Right. Let's just, let's just in the show right now. I mean, it's not going to be any better than this. Just Stop it

[00:15:00] **Carol:** it done.

[00:15:02] **Adam:** All right. Sorry, your heart matters. That's it. That's all you

[00:15:04] **Adam:** get.

[00:15:05] **Carol:** it. Goodbye silos.

[00:15:08] **Adam:** All we're going to do is talk about email anyway. So,

[00:15:10] **Tim:** Yeah.

## [00:15:12] Managing Messages While Working

[00:15:12] **Adam:** all right. So, all right. Here's, here's the topic thing, and this comes from, not, not shame, but like I get guff from some of my coworkers because I, my, my style of work is I get in, in the morning, I check my email. I get down to inbox zero. If I can or close if I can't get all the way there.

[00:15:30] **Adam:** And then very, probably that's the last time that I check my email during the day, unless I like need to send an email for some reason. Chances are good. That that's the last time that I look at my email until the following morning, and then I will start my work and I go really deep on whatever it is that I'm working on.

[00:15:47] **Adam:** And I get super focused and that's my day. and then, you know, somebody will send me a message in our team chat or something like that. And it'd be totally out of context for me. I'm sitting there scratching my head for five minutes going, what the heck is this about why don't I understand what this person is saying.

[00:16:02] **Adam:** I have to scroll up and look and see if I missed something what's going on. And it turns out that they sent me an email three hours ago and they just assumed that I had read it by now. like I know that there's there's flow. Right. And that's probably what's causing me to get in to get into this rut of missing emails, but also like, I feel a little bit better.

[00:16:23] **Ben:** emails, just a terrible form of communication. At least for me personally, I, it feels like such a chore there there's I get no joy out of email at all, because, you know, at this point in life, like 90% of it is spam, or even if it's not spam spam, it's like get hub,

[00:16:43] **Adam:** Yeah. Oh, yeah.

[00:16:45] **Ben:** alerts or all kinds of notifications or, yeah.

[00:16:49] **Ben:** and it's just, it feels like so much noise. I almost would rather be interrupted with a chat message just so that I can get it done and then get back to my

[00:17:00] **Adam:** Yeah.

[00:17:01] **Carol:** Like then, you know, it's real.

[00:17:03] **Carol:** Yeah.

[00:17:03] **Adam:** feel like there's just a couple of reasons that I would, you know, a couple of situations where I would prefer an email and that's like, one, if I need the record of it, because Chad is a femoral goes away or two, if I, if I absolutely have to see every single one of them. Right? So like for example, we get, every exception that happens in our app goes to our chat.

[00:17:23] **Adam:** We have a bug log and they all get logged there. And then as part of getting logged there, they get pushed into our chat. And that way we're aware when there's a bunch of errors happening and we can go like, okay, this is going nuts. Something's definitely up. And we can jump on that, but I don't feel beholden to read every report of every bug or anything like that.

[00:17:42] **Adam:** You know, they're, they're kind of ephemeral too, right. If one bug comes through and I don't look at it, no big deal,

[00:17:46] **Carol:** what about customer communication? So, I mean, your customers need to communicate. I don't want my customers directing, like my slack all day long. I would much, rather than email me and me. Just wait till I have a block to go respond to that.

[00:17:58] **Adam:** Yeah. And I mean, for me, that's tickets, right? So we, we have tickets built into our app and occasionally we'll get some emails. And this is another thing is like, we get email notifications of our tickets and have every comment on a ticket and all that stuff, because we prefer for them to be never miss any event.

[00:18:19] **Adam:** The problem is until one of our team members is assigned to the ticket. Every single one of us gets every single notification on every single ticket.

[00:18:28] **Carol:** No bueno,

[00:18:29] **Tim:** Oh joy.

[00:18:30] **Adam:** And

[00:18:31] **Carol:** no Glenn.

[00:18:33] **Adam:** but at the same time, like the alternative is maybe we rotate who gets all the ticket notifications and somebody has to assign all the tickets or something.

[00:18:40] **Adam:** That's kind of a crappy job too. So it's kind of a no win situation. I think with that.

[00:18:48] **Carol:** Yeah, but you also become like I'm deaf to it at some point, right? Like I, I see all of my emails pop up and it's like, oh, so-and-so commented on the PR. And it's on every single comment. It's not like you can group them together. I just start ignoring anything. That's about a PR because there's just so many of them, I just tune them out.

[00:19:08] **Carol:** I'm like, well, more PR comments. And some of them could be legit. See, then they do have to slack me for it. So I totally do get the, with bug logs and things. Whenever you are getting emails on those, they become non-important anymore because you just see it so much. And so often that you become numb.

[00:19:26] **Adam:** When the, yeah. When the signal to noise ratio is too out of whack, then it just all goes in the garbage can.

[00:19:31] **Carol:** Yup. Yup. Yup. Yup.

[00:19:34] **Tim:** Yeah. I don't know. So I'm, I'm a inbox Hawk, right? So I'm sitting there. The first thing I do in the morning is just get to the inbox and I will not do open a lot of code or do anything until I get to inbox zero, if possible. Sometimes, sometimes there's a few things you have to delay, but I will at least flat out flag them as important and then mark them as, as read.

[00:19:57] **Tim:** and then we'll get to the flag things later in the day, but it's like, I still, I don't know. I had this need, this need to be able to, to be the first person to answer something.

[00:20:09] **Carol:** Oh

[00:20:09] **Tim:** Right. I

[00:20:11] **Carol:** the total opposite.

[00:20:14] **Tim:** I want to be the first to answer. I want to set the tone, right? I I don't,

[00:20:17] **Adam:** Wait. I got a question for you, Tim. Have you ever participated in like online forums?

[00:20:23] **Tim:** yeah.

[00:20:23] **Adam:** Yeah. Are you the, is your personality the one that has to reply to every thread,

[00:20:29] **Tim:** No.

[00:20:30] **Tim:** not every thread, not everything. I mean, if a thread? where I may be mentioned in, or I've commented on before. Yes. But No. they're not every thread. Just the

[00:20:41] **Tim:** threads I'm interested in.

[00:20:41] **Adam:** that was me. Like when I played world of Warcraft, I joined the Guild and we had a Guild forum and I replied to every threat and I read ever replied to every thread and eventually they were like, okay, we gotta make this guy moderator. So he'll shut up. him busy.

[00:20:56] **Tim:** No, it's, I don't know. I want people, I particularly, if it's customers, right. So I get a lot of customer contact and I want to make sure that they know that whatever it is is being worked on. so. it's, so sometimes my replies aren't even necessarily informative. It's just, Hey, got it. Appreciate it. Thank you.

[00:21:17] **Tim:** We're working on it and we'll get back to you. But if I, if I'm not constantly on. Right then that's

[00:21:24] **Tim:** I feel I'm feeling fallen down.

[00:21:27] **Adam:** How much of that though, do you think is a self perpetuating problem, right? So you, it sounds like you get a bunch of emails from people and because you are so good about responding quickly, maybe they you've sort of trained them to

[00:21:41] **Adam:** expect that

[00:21:42] **Adam:** from

[00:21:42] **Carol:** Yes, you

[00:21:43] **Tim:** Definitely. Yeah, definitely. For sure. Yeah. I'll I'll get lots. I get lots of emails going, appreciate the quick response. And I realized, damn it. I probably responded too quickly if they're saying they appreciate it. I probably could have. waited an hour before I responded, but it's like, I'll get it.

[00:21:58] **Tim:** And it's like within 30 seconds, I'm responding.

[00:22:02] **Carol:** No, no, I get the email and if multiple people are on it, I will hold the email. Unlike, let me just see if someone else wants to take this on, because if so, I'm going to skip it. I've got other things to do.

[00:22:15] **Tim:** I guess maybe I'm just so arrogant. I want to be the first respond is like, I don't want anyone else on this email chain to respond because I want to set the tone for this.

[00:22:24] **Carol:** Yeah,

[00:22:25] **Adam:** sometimes that's appropriate, right? Sometimes, you know, best how this situation should be handled and you should set that tone or whatever, but it doesn't have to be everyone.

[00:22:34] **Tim:** I mean, I guess kind of in my silo, I'm in charge, right? So w w what I'm doing, I'm into, I want them to see that the person in charge has acknowledged it. And even if, even, I'm not saying I'm going to deal with it, I've, I'm telling other people, Hey, take care of this. And so I want them to see that. So I don't know if it's a Personality, flaw, I get it. I don't work on

[00:22:56] **Adam:** Personality, flaw, likes email.

[00:23:00] **Tim:** I hate email.

[00:23:01] **Tim:** actually. I really, really hate it so bad,

[00:23:04] **Carol:** but

[00:23:04] **Carol:** that's why you try to keep it gone. Like that's why

[00:23:06] **Tim:** Yeah, I want to get rehab. That's why, so I want to get rid of it, but I mean, to your point, Adam, it's like, that's why when I get flow, there's some, actually there are some days where, you know, the emails I'm at inbox zero and I'm not getting anything that's relevant in my box.

[00:23:22] **Tim:** And, I get to flow. I'm like, wow, this is great. I should do this more often.

## [00:23:26] Do Not Disturb

[00:23:26] **Carol:** So I put my laptop on, do not disturb. And then I also put my phone on, do not serve. I'm like no notifications anywhere. Like I don't want my watch vibrating. I don't want my phone vibrating. The only thing that comes through or the people who I've set as important and that those are my kids. That's it.

[00:23:41] **Carol:** Let's just be real. My kids come through and nobody else. That way I can just focus on what I'm doing because when I context switch, neither one of you get good attention at that point. Like I'm either halfway into one conversation while I'm thinking about what I really want to be writing, or I am, you know, writing something terrible because I'm also trying to figure out this problem that was just presented to me.

[00:24:02] **Carol:** So context switching is not good for me. I do not do well with context.

[00:24:09] **Ben:** I don't get disturbed by the little dings and slack. This is, this is a pain point that I think a lot of people have that for some reason. However, my ear brain system is wired together. Doesn't seem to affect me. I'm a way back in the day, when we were using AOL instant messenger.

[00:24:25] **Ben:** there was a setting you could go into, I was on a windows computer, so it used to be on windows, computer.

[00:24:29] **Ben:** If you got a message, then the little bar at the bottom of the screen would start playing.

[00:24:33] **Carol:** Yeah.

[00:24:34] **Ben:** was a setting and you could tell it how many times to blink after you received a new message before it would stop blinking. And I would go in and I'd set mine to a thousand because people in the office would be freaking out.

[00:24:46] **Ben:** They'd be like, dude, do you not see that? I messaged you? And I looked down and at the bottom of my screen, there's like four different blinking bars. And it's like, I get so tunnel visioned into the work that I'm doing, that I don't even see or hear things a lot of time. and, and I've, it's because of that, the idea of being interrupted by a chat message is never a pain that I could relate to.

[00:25:09] **Ben:** I know that there are people on my team who will put slack into do not disturb mode. And I think it mutes all the sounds. Yeah. And I'm, and I'm like but I think I, I think it's literally just because I don't hear the things the way that other people.

[00:25:23] **Carol:** so the reason why I like doing that is because if you come to message me now, when you start to message me, it says, Hey, she's in, do not disturb. Are you sure you want to send this right now? If so, hit send, then she'll get it. It'll also pop up. But are you sure? Otherwise, why don't you just type it and hold it a little while because she's trying to focus on something

[00:25:40] **Adam:** or send an email

[00:25:41] **Carol:** know yeah.

[00:25:42] **Carol:** Or yes, in an email do not send me an email,

[00:25:45] **Adam:** I'm going to write a script that sends you an email, like every hour.

[00:25:48] **Carol:** I'm just going to add them is spam. Yes.

[00:25:53] **Adam:** Yeah. I mean, that was probably already true anyway, so

[00:25:55] **Carol:** The do not disturb is great. Cause then people trying to ask me silly questions. No, to hold off just a minute, like let's wait till after lunch and then ask those questions because you know, I'm trying to actually work and

[00:26:06] **Tim:** Does that work though in

[00:26:08] **Carol:** It does. It does. I think it does because it's, I don't get as much noise.

[00:26:14] **Tim:** because I've been on do not disturb all day long with a 9:00 AM to 5:00 PM meeting. And I got tons of messages all day long and no

[00:26:21] **Carol:** because Tim, you respond to

[00:26:24] **Tim:** I, yeah, I do. It's

[00:26:25] **Carol:** to your own fault. We're blaming you for this behavior

[00:26:29] **Tim:** man. Carol,

[00:26:30] **Adam:** Don't blame the victim, Carol GS

[00:26:33] **Ben:** I'll tell you if I'm in a meeting, if I'm in a meeting and I can respond, I definitely do feel a pressure to, if I don't respond with a meaningful message, I will often respond to someone and say, I'm in a call.

[00:26:45] **Carol:** right? Yeah, I do that

[00:26:47] **Carol:** too.

[00:26:48] **Adam:** like slacker,

[00:26:49] **Ben:** yeah, yeah. A big, because I do feel like, especially in a remote working environment where you don't have the, that sort of, you know, the co-location sense you get in a physical office. Sending a text message into the void and not hearing anything back is it is quite disconcerting in a, in a way that's totally not, rational. And so I do feel a lot of pressure to just ping back and be like, Hey, I'm busy right now, but give me 20 minutes.

[00:27:17] **Carol:** The problem is, is if I respond now, it's gone out in my life. It has a red dot on it, and I'm not going to remember to go back to that

[00:27:24] **Adam:** you can mark it as unread.

[00:27:26] **Carol:** in slack.

[00:27:27] **Adam:** Yeah, you're right. Click on it. Or there's I guess, dots on the side. It's been a while since I've been in slack. I'm we're Discord now, but

[00:27:33] **Carol:** No

[00:27:34] **Ben:** you can also do,I think Ault, if you do all and click on a message, I think it marks it as unread

[00:27:39] **Carol:** got to do this. Okay.

[00:27:40] **Ben:** what? I have a windows keyboard on a

[00:27:42] **Adam:** or here you go. Take the Ben approach and just do shift escape.

[00:27:47] **Carol:** With the

[00:27:47] **Adam:** That's mark everything red everywhere in all channels.

[00:27:52] **Ben:** Can I, can I take the conversation in a slightly different.

[00:27:56] **Adam:** Yeah.

## [00:27:57] Asynchronous Messaging Vs Just Get On A Call

[00:27:57] **Ben:** One thing that drives me crazy. And I, and I'm, and I'm, I don't know if this is crazy or not, but, at work we do a lot of these RFCs is request for comment requests for feedback, where it becomes this sort of a mob approach to organizing data into a document where someone will outline, like, here's the thing I want to do and here's option a and option B an option C.

[00:28:21] **Ben:** And then everybody goes and reads it and they leave comments and they leave suggestions and they highlight stuff. And, it drives me nuts because

[00:28:29] **Adam:** Do you want to trade

[00:28:30] **Adam:** jobs? I'm super jealous. I've tried to do that. And like, I'm the only person on my team that likes that level of communication. And everybody else is just like crickets chirping.

[00:28:40] **Ben:** So it's not that I don't like the communication. What I don't like is the, is the distribution of responsibility for collecting the infant. I what I would prefer. I, it feels like it gives me a chore. Like, don't give me a chore. I want to help you think through stuff, but I don't want you to give me work to do.

[00:28:59] **Ben:** And almost what I would prefer is instead of us all reading this document asynchronously in our own time, I'd rather us all. Just jump on a call, talk about the thing that we're trying to figure out, and then have the one person who is putting the document together, then transcribe or take down the notes that he or she feels is relevant to the conversation, because it seems like asynchronous communication. There's so much opportunity for misunderstanding and subjective interpretation and, and just time-wasting. I think I would almost rather everyone get on a call. Let's just bang this thing out quick. And then the one person who needs to know this information has it, and then they can record it in a way that's most meaning.

[00:29:44] **Adam:** Yeah. And I could see if you have 20 people that are going to participate in the RFC and you know, it might get edited over the course of two days. You know, the first person that comes to, to read it and write on it is going to miss everything that comes after them. If they don't go back and check on it all the time.

[00:30:00] **Ben:** And then also then it becomes a whole nother source of noise in email because now that you've commented on document, now you get an email for every other person who comments or likes that document.

[00:30:10] **Tim:** Yeah.

[00:30:11] **Tim:** I, it's funny you bring that up, Ben, because like, so today I'm in a meeting, I was not supposed to be checking email or talking to people, obviously I was, but, from 9:00 AM to 5:00 PM. So something starts off as an email from a customer to go to a subset of people, just basically say, Hey, there's this issue?

[00:30:31] **Tim:** And then. you know, we respond to that and then my basic response was, Hey, I'm sorry. I'm in talent reviews all day. I can't deal with this. I'll talk to you tomorrow. But then, then that becomes a, some project manager, who basically. Didn't really seem to fully read the whole email since an email to me and someone else who wasn't on the initial chain.

[00:30:53] **Tim:** And now they're like, Hey, what's going on with this? And I'm like, I don't know. And then, and then eventually we now, then it moves to, it moves from email, from customer to email internally to now there's slack messages with again, the wrong group of people. But including me to say, Hey, there's this problem with these payments what's going on with this?

[00:31:13] **Tim:** And so I'm like, all right, well, we had a break at, during this 9:00 AM to 5:00 PM meeting that we had all day long. I'm like, all right, fine. We're doing, we're doing a voice call right now. Everyone get on this voice call right now, we're talking to this out and just put an end to this nonsense. And that, that's what it took.

[00:31:30] **Tim:** And that's like, I, that just drives me nuts. Cause sometimes, you know, email is good for one thing Chaska for another, but sometimes the only thing you can do is get everyone on the exact same time in a synchronous call. And solve it in real time. And what's crazy is after all day long of dealing with this at the end of the day, we get on one call meat, we solve it in like five minutes,

[00:31:53] **Carol:** Yep.

[00:31:53] **Ben:** Yeah, totally.

[00:31:54] **Carol:** agree.

[00:31:56] **Ben:** Also the nice thing about getting on a call is things have a things feel like they have a more definite deadline when you are driving something with asynchronous communication. You have to give so much latitude for people's time to respond. So you're like, I'm going to, you know, here's Thursday, October 21st.

[00:32:16] **Ben:** let's give everyone until October 28th to read this and leave comments. And you're like, now I've lost an entire week because you need to give people time to read this. How about let's schedule a call for everybody tomorrow. And if people can't make it like that sucks for them. I'm sorry. Like we're going to make a

[00:32:32] **Carol:** maybe we don't need so many people to make this decision, then

[00:32:35] **Carol:** it's fine.

[00:32:36] **Tim:** I mean, so, so in my example, I knew from the beginning seeing the actual, so in my mind, I'm like, all right, I know that really these five people need to be involved in this. The myself, I'm a fast responder. This lady, she's a very fast responder. I know she'll re, but these other three people, these three guys, they're not gonna respond to all.

[00:32:57] **Tim:** Unless you get them in a call, right? I just know that that you, you can, you can email them. You can slack them, you can Discord them, you can team them. It doesn't matter. They're going, nor it until you just basically get ahold of them and say, listen, you need to get on this call. Right. And, and sure enough, once we got it, like I said, once we got those people all in real time, synchronous communication, it finally got solved.

[00:33:20] **Tim:** We could have spent a week on this. Had we done it synchronously. And now there's some things synchronous is fine.

[00:33:26] **Tim:** but I mean, certain things like when there's a whole lot of people involved and it's a problem where it's not very well defined. You just guess like, guys, let's just stop it. Let's just get on a call and sort this thing out.

[00:33:38] **Tim:** It won't take long.

[00:33:40] **Ben:** Yeah, I need to go on a quick side rant,

[00:33:43] **Ben:** which is that,

[00:33:45] **Ben:** oh,

[00:33:46] **Carol:** I have the authority now to grant things. Don't listen to Adam.

[00:33:49] **Carol:** I totally do

[00:33:51] **Tim:** We need rain. We need a rent. We need rent music,

[00:33:54] **Carol:** Yeah.

[00:33:54] **Ben:** I get the

[00:33:55] **Ben:** Rand grant.

[00:33:56] **Tim:** Hm.

[00:33:58] **Ben:** I used to be in the, I used to be in this a weekly call and they would record the call in zoom, which is great. If anyone wants to go and watch it later, but then they would also pick someone on a rotating basis to record meeting notes for the call. And it made me so angry, so angry.

[00:34:19] **Ben:** I can't even, I'm like getting angry thinking about it. And I brought it up one time and I'm like, if people can't make the call, why don't they just watch the recording?

[00:34:28] **Ben:** And people were like, well, they could watch the recording, but it would be much faster for them to be able to look at the notes and be able to, you know, search the text for what happened.

[00:34:36] **Ben:** I'm like, so you're paying me an hour to take notes at my salary. Like, that's ridiculous. That's a terrible waste of time

[00:34:45] **Tim:** because they couldn't be asked to show up.

[00:34:47] **Carol:** Yeah.

[00:34:48] **Ben:** Like, yeah, you can't make the call. So now I have to make it as convenient as possible for you. Oh my God made me so angry.

[00:34:54] **Carol:** not just that with our mindset to things, we're not going to just put out our quick jotted down notes, we're going to spend an hour after the call and making them actually legible and making sure someone can do something with it. So it's not an hour of time. It's a couple hours of time.

[00:35:07] **Ben:** So, and, and, and I don't know, I'm not, I'm not one of those people who can think and type at the same time. So if I'm writing down what people are saying, I'm basically not listening to them. it's just like, the conduit through which it's flowing into text format, but I've got no idea what people are actually saying.

[00:35:23] **Ben:** So it's like, not only do I waste an hour of my time taking notes, I waste an hour, basically not participating in the meeting.

[00:35:30] **Carol:** You miss it as well. Yeah. Yeah. You guys have heard me say how much I hate like entering in my own JIRA tickets. Right? My solution to this would be, I would screenshot the link to said zoom call and be like, here are your notes. Go listen by Carol

[00:35:46] **Adam:** not even copy and paste, just

[00:35:48] **Carol:** Nope. You get a screenshot of the link

[00:35:50] **Adam:** So you have to transcribe it

[00:35:52] **Adam:** into your Euro bar.

## [00:35:53] Historical Documentation

[00:35:53] **Carol:** Yes. I hate, I hate documenting stuff like that. I'll document my code. I'm good with that. I'll write that technical documents. That's fine. But no, note taking.

[00:36:04] **Ben:** generally speaking, how important, if we could be honest, how important do you think technical and historical documentation is? And I'm not saying, you know, if you're going to have an open source project and it needs to be documented so people can use it. That's something very

[00:36:20] **Carol:** Totally different. We're talking the application I write, which is

[00:36:24] **Adam:** You're talking to

[00:36:24] **Adam:** internal docs.

[00:36:26] **Ben:** yeah,

[00:36:26] **Ben:** Like Carol's working on an inbox processing thing and she decides to go with Google cloud app and not Amazon and like let's document. The reason that decision was made, how important is that? Because we do a ton of that documentation at work, and I never look at any.

[00:36:44] **Carol:** I don't look at it. I don't go look at the documentation for why the decision was made. I will look at the documentation for how the process works. So say we're talking about how data's coming into the system, what we do with it, and then how we integrate with another partner. I will read that documentation.

[00:37:02] **Carol:** I will reprocess documentation all day long, but I don't care about why it became, I don't care about how it started. I don't care about the cost. Like just let me know what the process is and that's where I'm going to get. So I don't document the other stuff. I can document my process all day long.

[00:37:18] **Carol:** Yeah.

[00:37:19] **Adam:** If I feel like there's notes that I need to leave behind for somebody that might be working on this project after me, that don't fit in as like code comments, they don't have an obvious place to go. Then I'll throw in like a, read me dot markdown file in the, in that folder and the root of the repo or whatever.

[00:37:35] **Adam:** and we do have like a company Wiki. Sort of things over like things that come up often or like onboarding, that's all sort of,

[00:37:46] **Carol:** Sure.

[00:37:47] **Ben:** to Carol's point like anything that's about process. I feel like that's probably cause that has to be kept up to date in order for it to be helpful. And when people use it and it's not helpful, there's a, there's an initiative to, to keep it up to date. But there's, there's so much stuff that we document at work that I, it feels very academic.

[00:38:09] **Ben:** Like let's document this so that in two years from now someone will, if someone feels like, why didn't we use Postgres instead of MySQL, then, then there's a document somewhere that says, Hey, here's why we decided to use MySQL.

[00:38:23] **Adam:** it's a whole document. It's not just like

[00:38:25] **Adam:** two sentences.

[00:38:26] **Tim:** it's.

[00:38:27] **Tim:** a bunch of excuses. That's all

[00:38:28] **Ben:** it's it's a whole document and some architecture diagram,

[00:38:31] **Adam:** Oh man.

[00:38:32] **Ben:** and it's like, it's really great that people do it.

[00:38:35] **Ben:** I just,

[00:38:36] **Ben:** I,

[00:38:37] **Carol:** beneficial. Then my

[00:38:39] **Ben:** and maybe it's just my role at work is just not that it just doesn't deal with that kind of

[00:38:44] **Adam:** I mean, the the positives there is, it saves you from, you know, five or 10 years from now. Somebody's going to question that decision. And one possible outcome of questioning that decision is putting in a crap load of time and effort to change the minds and, you know, implement the other solution that you chose not to do the first time through and realize too late that they have not wasted their time because of a, B and C that are outlined in that document.

[00:39:16] **Adam:** That didn't exist because you didn't write it.

[00:39:18] **Tim:** Yeah.

[00:39:20] **Ben:** So I would counterpoint. The passage of time, I think necessarily changes the context of decisions. So you might document why you decided to go with MySQL 5.5, six years ago,

[00:39:38] **Ben:** and now someone

[00:39:39] **Tim:** And now why you're wrong now? Not using Postgres?

[00:39:42] **Carol:** Yeah.

[00:39:43] **Ben:** no and you know, and now someone might join the company or have a director level position or something and want to change databases. And their, their considerations are possibly significantly different, even though it's the same technology

[00:39:56] **Ben:** because of, yeah, because of advances that have been made or different database, you know, Tim's always talking about cockroach DB that, you know, that didn't exist a decade ago when maybe the decision was made.

[00:40:07] **Ben:** And, I don't know much about cockroach DB. That's not an endorsement, but I'm just saying that it feels like the historical nature of, of the document in some ways makes it less about. No, not that it makes it less, it makes it, it's almost like there's nothing in Trinsic really

[00:40:28] **Adam:** So what you, what you're saying is the stuff you're working on is not important enough to end up in history books. So don't write history books about it.

[00:40:38] **Carol:** Maybe,

[00:40:38] **Ben:** what I'm saying.

[00:40:39] **Carol:** well, no, no, The way I take it is if I'm re-evaluating something in five years, I've really shouldn't look at most of the evaluation process from five years ago. I should be looking at what it applies to right now and how it impacts what we're doing today and where we're going, because what, what, what was five years ago is not now, Adam?

[00:41:00] **Carol:** It's not now.

[00:41:01] **Adam:** I'm going to.

[00:41:02] **Tim:** know. I think, I think there's some benefit and con I think there's some benefit in context, right? It's like, they're like, all right, Because I mean, constantly developers looking, go, why in the world who is doing this way? Well, if you look at it, if there's an, if there's an article that says, here's why we chose it, they're like, all Right. they can get off it.

[00:41:19] **Tim:** So box, and now it's like, you don't argue the past. You argue

[00:41:23] **Carol:** the future.

[00:41:24] **Adam:** So

[00:41:25] **Carol:** is what I'm saying you

[00:41:26] **Adam:** I I'm going to disagree, but, and I'm going to, I'm going to disagree with the caveat that I think that the documentation should exist, but I think it should be limited to like two paragraphs of like three or four sentences,

[00:41:40] **Carol:** Perfect. I agree.

[00:41:42] **Carol:** I agree. I

[00:41:43] **Adam:** we had to make a decision. These were our constraints and this was the reason that we went with that we went to

[00:41:49] **Ben:** Oh my God. I'll have

[00:41:50] **Carol:** get on. Yeah, I'll take, I'll

[00:41:52] **Carol:** take some of that.

[00:41:53] **Tim:** So going back to your kind of original premise, Adam, you, you.

[00:41:55] **Tim:** you.

[00:41:56] **Adam:** sucks.

[00:41:57] **Tim:** No, it wasn't, it was, it was, it was the flow state versus contextual rights. So being, you know, the, the benefit of being in a flow state, which, you know, developers, you know, have gotten into that, you know, the value of just losing track of time and just, just,

[00:42:12] **Tim:** you know, doing, uh, doing the beautiful, the beautiful mind thing.

[00:42:15] **Tim:** I sort of feel because I'm a developer who has, who basically leads other developers. I feel my job is to protect them so that even though I rarely get into that position, when I, and when I do it's, it's, it's a beautiful thing, but it's like, I feel my job is to protect the others so that they. Be in that state more.

[00:42:37] **Tim:** Right. So I'm that, that is really the reason why I am the forefront of blocking the emails answering quickly so that my people can be in that position to be best suited, to get into that flow state. And that, that's what I pride myself on that they don't have to worry about injects and, constantly, you know, requests.

[00:42:59] **Tim:** Right. I want them to be, I want them to be almost to the point where they're like, should I be doing something else? No, no, you keep doing what you're doing. You know, keep, keep staying on that, finish that. Don't worry about it. Anything else? Don't don't and because you know, you have to have people doing that.

[00:43:16] **Carol:** Absolutely. And I would, that's really good. Yeah. So I was going to say that's amazing. So then now I appreciate your like approach towards email's a lot better,

[00:43:24] **Tim:** Yeah.

[00:43:25] **Tim:** I'm trying to protect the developers. I want the developers to be in the perfect condition where they can just focus on what they're doing and not worry about all the other stuff, you know, I'll inform them what's going on afterward any of the week. We sort of have a debrief and say, all right, here's what's going on.

[00:43:39] **Tim:** And they're completely surprised that there was all this thrash and churn, right? All this, you know, all this terrible stuff going on. That's like, don't worry. We handled it. You don't have to worry about it. Here's what you work on next week.

[00:43:53] **Adam:** The recording of Steve Vollmer going developers, developers,

[00:43:56] **Adam:** developers,

[00:43:57] **Adam:** developers,

[00:43:58] **Tim:** For sure. I think Tim said this on a previous episode, but he was saying, one of you said that good managers manage down and up.

[00:44:11] **Ben:** And

[00:44:12] **Adam:** Um, I think that might've been Carol, but.

[00:44:15] **Ben:** somebody said it

[00:44:16] **Tim:** Yeah, somebody said it.

[00:44:18] **Carol:** Yeah. We, uh, We, all agree with it. Yes.

[00:44:20] **Ben:** Yeah. Yeah.

## [00:44:21] Communication Styles

[00:44:21] **Ben:** If I can go in slightly different direction, again, more about communication styles and maybe thinking speeds. one thing that I have been challenged with in the past is that I'm not a super dynamic thinker.

[00:44:35] **Ben:** I'm like the, I'm like a slow marinating thought person. I kind of have to let stuff sit in my head for a little while and, and chew it over. And if I get into a real time conversation with someone who's a very quick thinker and it's very strong with their feelings and strong with their emotions. I find it very challenging to have a productive conversation.

[00:44:57] **Ben:** Cause I feel like I'm constantly getting steamrolled and I can't, I don't have enough time to, to be able to justify some of my thoughts if I, if I can't think them think through them deeply enough. And if I have to communicate with someone like that, that is actually a time where I actually will like to do something over slack or over email.

[00:45:18] **Ben:** Cause I feel like it gives me the control and I can, and I can control the cadence of the conversation and I can step back and, and have time. So there is, there is at least for me at times, a sort of survival mechanism that an asynchronous communication allows me to have.

[00:45:34] **Tim:** Yeah.

[00:45:35] **Tim:** I get those a lot of times when I'm dealing with a superior, I do want to do it in a, text version where I'm either email or chat. So I have time to think about what I'm saying to a superior, right.

[00:45:47] **Ben:** Yeah.

[00:45:48] **Tim:** Because yeah. You say it over the phone or whatever, and you're like, oops, I probably shouldn't say that.

[00:45:55] **Carol:** Yeah. It's something about typing it and rereading it right. And going okay. Does that make sense? Cause I'm kind of, I'm the opposite of Ben. I tend to go very fast and I go, Hey, okay. Here's what it is. Here's what I'm thinking. What do you think? Tell me what you think right now. And I'm trying to not be pushy, but I'm just very quick.

[00:46:11] **Carol:** And that's where, you know, most of my team is like, Give me a second. Let me process everything. You've just said, let me think about you, what you just said, and I will get right back to you. Okay.

[00:46:23] **Tim:** yeah.

[00:46:24] **Adam:** I sound a lot smarter in written communication than I do in

[00:46:28] **Tim:** Well, it, so it's funny. So because of my need to like type things fast and just get information out quickly. So I had, she was my, I was reporting to her, but it's like, you know, we're just, isn't, it's not like we were having conversations about different issues. And I would, I mean, I have terrible spelling. I mean, my Mead's got, Stroh's just are probably the worst spellers in the world, Scott and love you, buddy. but Yeah. so, and then one of our performance reviews, she's like, you know, in your communications on slack, you, you know, many times you have misspellings and things, you know, grammar. And I'm like, in my mind, when you're talking on slack, that's like a conversation that's informal.

[00:47:10] **Tim:** And she's like, no, you know, we use this for, uses for like, you know, That as a programmer, whatever level you were at the time that you should be, you know, expressing yourself more clearly. I'm like, but I got the information across the fact that I spelled the word wrong, or, you know it didn't have an, a prosperous place.

[00:47:28] **Tim:** I don't really think that.

[00:47:30] **Tim:** Yeah. That's I didn't really, I didn't really get that.

[00:47:33] **Tim:** so,

[00:47:33] **Adam:** That's unrealistic expectations. I think it's such an informal communication mechanism that,

[00:47:39] **Ben:** it's all a gifs and emojis. Anyway, most

[00:47:42] **Carol:** Yep.

[00:47:43] **Tim:** For sure.

## [00:47:43] Managing Documents In Meetings

[00:47:43] **Ben:** All right, I'm going to take it in one more direction. Apologize. This whole, the whole communication style. It's just so much stuff is popping into my head. one thing that has historically really bothered me is when someone calls a meeting and in the meeting invite, they say, Hey, can you all please read this document before the meeting?

[00:48:01] **Ben:** Cause I'm like, no, thank you, please don't give me chores. And what we've started to do at work is we have a meeting and then on the call, everybody will go off audio and video and we'll take the first 10, 15 minutes of the call. And everybody reads the document that we're about to discuss. And I freaking love that because it means that all my efforts are still time boxed into the scheduled call.

[00:48:29] **Ben:** I don't have to prepare for it. I don't even have to know what the meeting's about and you know, full transparency, half the meetings I go into. I don't know what I'm even going into. And it's all just works out and I, and I've been loving that approach.

[00:48:43] **Tim:** like Sydney, you a meeting with homework,

[00:48:45] **Ben:** Yes.

[00:48:46] **Ben:** Don't give me

[00:48:47] **Tim:** Don't give me homework.

[00:48:49] **Ben:** I'm a professional.

[00:48:50] **Adam:** It's, I, I don't know if this is where it originated, but for me, that style of meeting, I'm aware of it as like an Amazon style meeting. I think that kind

[00:48:58] **Ben:** I, I think so.

[00:48:59] **Adam:** Bezos pushed that on him or whatever, but yeah, I mean, and that's how we do a lot of our meetings too. And it works really well. Our ours tends to be like five minutes.

[00:49:08] **Adam:** It takes to read. It sounds like you guys write a lot more than we do just in general, a lot more words, but,and our style, instead of going off of video, we just mute our microphones. And then when you are ready to discuss you unmute, but that video might be better. That's a little more.

[00:49:27] **Tim:** we don't do it in that format per se, but if, if I've been called into a meeting where someone is attached, like a document, and so far, really the only the marketing piece. And our company have done that to us. I will say, can we just take the first, you know, five, 10 minutes and you go over the document, explain it to us.

[00:49:45] **Tim:** I, I mean, I'm not going to, I'm not going to start the meeting and I will refuse. I would just basically say, I'm not going to go. Someone will say, did you read the document I sent with the, with the meeting attachment? I'm like, no, I did not so loud. We take the first five minutes and we'll go over that.

[00:50:02] **Tim:** And then that just kind of kicks off the meeting anyway. It's like, yeah,

[00:50:07] **Tim:** don't, don't make me do homework.

[00:50:08] **Ben:** a hundred percent. And if I can double down on that for a second, one thing that will drive me crazy is, and maybe this is because I only have one monitor, so I have very limited screen real estate.

[00:50:18] **Tim:** You poor, poor, poor person.

[00:50:20] **Ben:** Trying to have a bunch of people review a document and have video chat open on the same time.

[00:50:28] **Ben:** It drives me nuts. I would much rather have the one person who's driving the meeting, share their screen so that we can see exactly where they are in the document and what they're looking at. And they can highlight text or they can, you know, draw annotations, whatever kind of tool you're using '

[00:50:43] **Tim:** cause otherwise like, what do you know you're talking about? I mean, show me what you're talking. I don't know where in the document. I'm sorry.

[00:50:49] **Carol:** it sounds like we're on the same page, but we're not.

[00:50:52] **Tim:** Yeah.

[00:50:53] **Ben:** And I know Adam's got like 12 monitors, but, but I, you know, with me, it's like, I'm either looking at your face. I'm looking at the document. I don't know how to do both. So it's a lot of all tabbing back and forth to get between the two experience.

[00:51:06] **Tim:** I mean, I mean, even if you have multiple documents, like they could be looking at a section of the document that you're not even looking at. You're like, I have no idea what you're talking about. And that was the day that was the 9:00 AM to 5:00 PM meeting today. We were like pulling up spreadsheets and looking at talent reviews and like, unfortunately they showed us what they were looking at so we could see what they're looking at.

[00:51:27] **Tim:** So I was like, okay, good. Otherwise we'd be like, I don't have no clue what you're talking about.

[00:51:31] **Ben:** Oh man.

[00:51:32] **Adam:** Are you all ranted out?

[00:51:34] **Ben:** I had no idea.

[00:51:35] **Ben:** that talking about communication was going to bubble up so many feelings.

[00:51:39] **Carol:** ah,

[00:51:40] **Carol:** listen, Ben it's it's all in context. Okay. It's all in context.

[00:51:45] **Adam:**

## [00:51:45] Patreon

[00:51:45] **Adam:** This episode of Working Code is brought to you by big email. If it didn't happen in email, it didn't happen. And listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon. And you could do that by going to patreon.com/WorkingCodePod for the unfamiliar Patriana as a way for you to kick in a few dollars a month to support the things you like.

[00:52:06] **Adam:** And it helps keep the lights on around here. the entry level tier starts at just $4 a month and all patrons get our after show and early access to new episodes as soon as they are ready. So they don't have to wait for the new episodes to release on Wednesday. They usually get them Tuesday at 11:58 PM because then I'm panicking that I didn't get them out earlier now, significantly earlier.

[00:52:30] **Adam:** Anyway, where was I? yes, we have to thank our top patrons, Monte and Peter. Thank you guys so much for your support. These guys have been helped us out a lot

## [00:52:37] Thanks For Listening!

[00:52:37] **Adam:** and if patronizing podcasts, isn't your thing. No worries. we appreciate that. You listen, If you enjoyed this episode, you should post about it on your social media, your word of mouth referrals help more than you might think it would also really help us out.

[00:52:48] **Adam:** If you could leave us a rating and review on apple pod. So please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod, or leave us a message at 512-253-2633 that's 512-253-CODE or, or, or you can join our Discord and share your ideas with us there. As we're recording, this has only been about a day and a half since we made our Discord public and we've already had a bunch of people join up.

[00:53:12] **Adam:** So welcome everybody and looking forward to meeting more of you guys and gals. And, if you didn't know, you can join us at workingcode.dev/discord. That's how you, where you go to join our Discord. by the time that you hear this, it's only a couple of weeks from our one-year anniversary. We're coming up on episode 52.

[00:53:27] **Adam:** so we want to know what do you guys want us to do for our one year Something kinda fund special? No, sorry. I don't have enough time to plan that we're not going to Vegas, but if you've got ideas, we want to hear them. So join us, our Discord and let us know there. Or you can tweet at us @WorkingCodePod. I think that's everything. So I guess we'll catch you next week. And until then,

[00:53:49] **Tim:** Hey guys, your heart matters. Even your inbox is not zero.

[00:53:53] **Adam:** I

## [00:54:12] Bloopers

[00:54:12] **Adam:** think that getting on a conference call like with correct audio and video and levels and everything being where you want them, that should be a new game on squid game.

[00:54:22] **Tim:** All right.

[00:54:24] **Ben:** I had brought up the, when Swift's was on, he had talked about the Rogers curve adoption. I find that a little fascinating, cause I'm such a laggard on like everything.

[00:54:33] **Adam:** Okay.

[00:54:34] **Ben:** I dunno if anyone's different, maybe it wouldn't be interesting if we're all the same.

[00:54:37] **Adam:** I think I'm different. I I'm,

[00:54:39] **Ben:** you seem to be an early adopter

[00:54:40] **Adam:** I'm an early adopter, I think like, I would like to be an early adopter, but I live in, like an early majority world, not in that world, but like, you know, I work in an early majority company. I am a material girl.

[00:54:58] **Adam:** Should I bring it home?

[00:55:00] **Ben:** Let's do it.

[00:55:01] **Carol:** Dad,

[00:55:03] **Adam:** All right. Oh God, you guys are making me cringe so hard.

[00:55:09] **Carol:** next time, leave your shirt on.

[00:55:12] **Ben:** I mean, I want to look to see how many emails I actually have work emails. I have, I have currently in my work.

[00:55:20] **Ben:** 5,082 unread messages.

[00:55:23] **Tim:** geez.

[00:55:24] **Carol:** boy.

[00:55:27] **Ben:** Wait, so that's worth 5,082. And my personal email has 29,661.

[00:55:35] **Adam:** Oh my god. Ben.

[00:55:36] **Ben:** I feel like I get 19 emails a day just from the democratic national party.

[00:55:43] **Carol:** Yeah, yeah, yeah. do too.

[00:55:46] **Adam:** You got to get better at those unsubscribes been.

[00:55:48] **Ben:** Oh, it's so, Joe Biden is constantly reaching out and

[00:55:52] **Ben:** pleading

[00:55:52] **Adam:** I am once again, reaching out to ask for your support.

[00:55:55] **Carol:** help me.

[00:55:59] **Adam:** That was a terrible Bernie impression. I'm sorry.
