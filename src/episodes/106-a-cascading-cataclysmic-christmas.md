---
title: "106: A Cascading Cataclysmic Christmas"
description: "This week, we continue to lean into 'No Effort December', talking about a hodgepodge of both tech and non-tech topics."
date: 2022-12-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/106-a-cascading-cataclysmic-christmas/id1544142288?i=1000590858050"></iframe>

This week, we continue to lean into "No Effort December", talking about a hodgepodge of both tech and non-tech topics. Since we're heading into Christmas, we start off talking about how challenging it is to buy gifts, especially for the _grown-ass_ adults in our lives. We also share some of our favorite Christmas movies; and, the movies which have absolutely nothing to do with Christmas, but which we love to watch in the winter anyway. We also dig into some modern CSS advances; including our fear that CSS selectors will quickly become more like Regular Expressions: fun to write but impossible to read!

Links discussed in this episode:

-  [Super Useful CSS Resources](https://dev.to/lissy93/super-useful-css-resources-1ba3)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/106-a-cascading-cataclysmic-christmas.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** CSS to me has always felt relatively, not static, but it, it evolved in ways that felt very easy to slowly roll into the way I approach c css. And it seems now like there's a lot of stuff that is, is fundamentally changing the way CSS works and it's just making me nervous. One that I'm gonna fall behind, but also two. I, I, I'm a little nervous that people are just gonna be too clever sometimes.

## [00:00:48] Intro

[00:00:48] **Adam:** Okay, here we go. It is show number 106 and on today's show we are gonna figure out what today's show is about right along with you cuz it is still no effort. December, but first as usual, we're gonna start with our tramps and fails. And Ben coming to you first. What's going on buddy?

## [00:01:04] Ben's Triumph

[00:01:04] **Ben:** I am gonna go with a triumph, which is that, I had mentioned last episode that I was, made no progress on my 2022 New Years resolution to build something containerized. But my triumph this week is that I have actually started to think about starting a new thing,

[00:01:20] **Adam:** Mm-hmm.

[00:01:21] **Ben:** and it, it's like a triumph, but it's also a little bit of a failure because what I realized is I, I don't start new things very often.

[00:01:28] **Ben:** Like I'll do lots of little demos here and there, but as far as starting a new site or a new application, I feel like I do that like once a decade. everything else is just maintenance, maintenance, maintenance. So the act of starting something new is really not a gesture that I have built in. And on top of that, so much technology has changed since I last started a really big project.

[00:01:54] **Ben:** and the, the things that have advanced really far are a lot of the, the front end stuff and all the compiling and, and the componentization of everything and the modules. And, I of course wanna build my back end in ColdFusion, and I don't even know how to mix those two things together very well. So it's gonna be an uphill, Hmm, I don't wanna say battle, but it's gonna definitely be a, a, a learning journey, trying to figure out how to take my, what I think is actually quite a rather old mental model for how you put an application together and, and sort of shoehorn it into more modern practices. And it's tough because I think so much of modern web development today that I hear getting discussed is JavaScript on the front end and JavaScript on the back end. And so a lot of things just sort of fit together really nicely because it's, it's sort of this, Universal technology, and I'm not doing that.

[00:02:50] **Ben:** So I, I don't know how much there is that I can learn from other people at the finer points of getting everything fit together. But, I dunno, I'm excited, but I'm nervous and I'm, I'm, I'm feeling a little intimidated, but, I'm excited.

[00:03:05] **Adam:** I, I saw you posting about this on Facebook, and I saw, like, you posted a screenshot of like, how you're organizing your code. and it, it had a Docker file in there. I was like, wait, is he doing it?

[00:03:14] **Ben:** well, so I'm, I'm not gonna, so ultimately when I ship to production, it's gonna be not container containerized, but locally it'll be containerized.

[00:03:23] **Adam:** That's okay. That's a, that's a good first step.

[00:03:25] **Ben:** yeah, I think it'll be pretty good. Although it's so funny, you know, everything is just more complicated than I always expect it to be. So I, I know that,certbot and Let's encrypt have quote unquote made getting SSL certificates super.

[00:03:40] **Adam:** Mm-hmm.

[00:03:40] **Ben:** but then I start to read about it and how do I do that? And it, and it's like there's all these different steps you would have to run through to get it to work. And like even that still seems really complicated if you have to do it. Services like Netlify that provision the SSL certificate for you behind the scenes.

[00:03:56] **Ben:** I mean, that's obviously magical and fantastic, but even like the moment you have to do it by yourself. It, it's a, it's this weird catch 22 where you can't have an SS an SSL site running until you have the certificate, but you have to have a site running in order for a certbot to be able to say, Hey, this is a valid site that I own.

[00:04:16] **Ben:** That it can though go in, like check to make sure it really exists so that there's all this stuff. You have to, from what I was reading at least, it's like you have to get the site running on port 81st so that you can then get the SSL certificate, which you can then install, which then you have to restart your, your web application server so that you can get the SSL certificate to power.

[00:04:36] **Ben:** What is it? 4 22 where, I can't remember

[00:04:39] **Adam:** Oh 4 33. No, uh, 43.

[00:04:42] **Ben:** 43

[00:04:43] **Adam:** Yeah. Wow.

[00:04:45] **Adam:** It's been so long since I've had to

[00:04:46] **Tim:** You were right the first time. It's, it's three digits. 4 43.

[00:04:50] **Ben:** whatever it does behind the scenes.

[00:04:52] **Adam:** It's, it's been so long since I've had to think of that. That's

[00:04:54] **Ben:** right? Yeah. But it's just, I don't know. It's one of those things where I thought it was gonna be a lot easier, and then you start to do it, and maybe I'm just not looking in the right places, or maybe I'm not reading the right articles, but it still just seems more complicated than I would like it to be.

[00:05:09] **Tim:** I, I would say though, once you have it set up, renewing it, cuz we, I know at work we have scripts that just go through and renew it whenever it needs to be renewed and just kinda like hands off, so,

[00:05:23] **Ben:** Yeah. It, it, it does seem, once you get it up and running, keeping it going seems pretty reasonable. Although it, it sounds like you still have to restart. Engine X or Apache or Iiss so that it picks up the new certificate, but, you know,

[00:05:39] **Adam:** only every couple of weeks. When When

[00:05:41] **Ben:** I think, yeah, I think it's like three months or something.

[00:05:43] **Ben:** It'll, it'll last for, or 90

[00:05:45] **Ben:** days I think it lasts

[00:05:45] **Tim:** the most, yeah, I think, I think it's the, the.

[00:05:48] **Adam:** Yeah, you can. You can set the. Yeah, like Tim was saying, you can set the renewal as far out as like three months, but I think they, they recommend every two weeks or something like that.

[00:05:57] **Ben:** Oh really?

[00:05:58] **Adam:** Yeah. I was using it for a, a client site that I had for a while and it actually worked out kind of nice for me because I was doing reverse proxying with engine X.

[00:06:07] **Adam:** So I was running engine X on the server and I was running docker on the server and so I could restart the, the app by like spinning up a second docker container and moving the proxy over to the other container and bring down the, the first one. And then, the, the, since there was basically nothing in the engine X container, it would restart in like half a second or less.

[00:06:27] **Adam:** Right. So basically zero downtime as far as anybody's concerned, cuz I wasn't doing anything, you know, no web sockets or anything that need the connection to stay

[00:06:36] **Adam:** open

[00:06:36] **Ben:** right, right. Yeah, that's really great. I have given up, I think on the idea of running it in Lucy, I, I, I really, really would've loved to run in Lucy. It's, it's a great language. I, I

[00:06:46] **Adam:** gonna go to the Smith Project or

[00:06:48] **Ben:** Well, no, I, I'll

[00:06:49] **Adam:** Dragon

[00:06:51] **Ben:** I'll be on on Adobe ColdFusion. So my v p s is a managed V ps and, and they manage Adobe codefusion.

[00:06:58] **Ben:** when they, when I upgraded to ColdFusion 2021, I asked if they would do Lucy CFML, and they said they could theoretically do it, but their ability to support it would not be nearly as good. So I was like, the whole point of having to manage VPs is so that they do a lot of stuff that I don't have to know about.

[00:07:16] **Adam:** I guess you won't have access to Tag Islands

[00:07:18] **Ben:** I know, that's the thing. It's killing me the most. Oh my God. Oh, oh, right in the heart there. Adam Anyway, so that's me. I'm excited about that. Tim,

[00:07:31] **Ben:** what? Yeah, yeah, yeah. I'm gonna, I'm gonna have some fun, I think, or at least I hope I have fun. what about you? What do you got going on?

## [00:07:38] Tim's Triumph

[00:07:38] **Tim:** So I mean, it's only been what, a couple days since we recorded, so there's not like a whole lot's happened. So I'll just talk about the most exciting thing that happened to me today, which has been ongoing. We. I think I mentioned this before, the credit card industry pushed through some price increases that really, really hurt our bottom line.

[00:07:53] **Tim:** this isn't code related, but it's like, it does affect the business. So, been pushing through price increases to our customers so that, you know, we can keep the lights on and keep everybody paid and have one particular customer that's like sizable customer. They tend to be a little bit difficult, particularly when it comes to the money.

[00:08:08] **Tim:** but worked with him finally today, he said. Yep. And it's got the price increased through and it's gonna be a huge impact in our company for next year. It just really unlocks a whole lot of things that I was afraid that we're gonna have to cut back on some stuff. So, really, really . In fact, I, I just saw him listen, I, I appreciate this.

[00:08:29] **Tim:** I said if I didn. These things through. I don't know if I'd, you know, you'd be talking to me next year, so it wasn't quite that bad. But, you know, I wanted to make him feel appreciated. I was like, I, I appreciate you. So anyway, so that made me super happy today. I, I almost couldn't, that was like late afternoon.

[00:08:48] **Tim:** I couldn't finish work. I was like, I gotta go walk around the house and shout and dance and

[00:08:53] **Adam:** Right.

[00:08:54] **Tim:** shake the tambourine.

[00:08:55] **Adam:** I've had enough success for one day.

[00:08:57] **Tim:** Yeah. Yeah. Just, just stop now. I'm ahead,

[00:09:00] **Ben:** I know on one of the previous episodes you had talked about paying for the privilege of having customers for the, for the customers who aren't ready for any price increases, and they eventually outgrow what they're even paying for your services. But hopefully far and few, few and far.

[00:09:16] **Tim:** Yeah. And, and honestly, these are, they are one of those, they, they've been with us for. Oh my god, probably 15 years. Right? And so, and that's the trouble with some of these long term customers is they're, they just get used to the status quo and it's like you don't wanna mess with them. And so, and you're afraid to give 'em price increases, but then it's like, you wait too long and then it's like, wow, they're really underpaying.

[00:09:40] **Tim:** Like you, we've got, they're getting like so much more than our other customers and they're, that are paying so much more. It's, it's really not fair. And so, yeah, we, we gotta be a little bit more diligent about just paying attention to, because everything goes up every year, right? I mean, that's what the whole cost colo cost of living increases is, is, is everything.

[00:10:02] **Tim:** Everything goes up every year. So if you're not constantly looking at your prices and, and pushing them and trying to get more, then you're actually making less money. So actually I'm looking for ways next year to come up with some sort of, Mechanism to have a built in contractual, you know, a percentage price increase that, you know, every

[00:10:24] **Adam:** Mm-hmm.

[00:10:25] **Tim:** three to 4%,

[00:10:26] **Adam:** just so the customers know what to expect.

[00:10:28] **Tim:** Yeah, yeah. So that's, yeah, because that's the hard part. It's like, you know, in order to increase people's prices, you have, we typically have to do a, a new contract, and they, they have the power, they just don't sign it. That's status quo. The only thing you have to do is say, well, we're shutting it down if you don't pay that.

[00:10:43] **Tim:** It feels terrible to say that it's like a bully. But, so if you already have that built in, then yeah. You, you, you don't have to have that friction,

[00:10:53] **Ben:** I, I know I've mentioned this podcast like a thousand times on, on our podcast, but I really enjoy The Rework Podcast by the guys at Base Camp. And maybe like two or three episodes ago, they were talking about how they used to run a product called Campfire, which I think was a chat program. and D h H was saying that Twitter was their biggest client of the chat program, and they were running the numbers and they used like 95% of the resources that were allocated for the application.

[00:11:22] **Ben:** And, and apparently the 37 Signal guys at the time were, were losing a bunch of money on it for and, and, they , said Twitter was only paying like $5,000 a year for the service. Yeah. And so they finally, to, to your point, like they didn't wanna say anything cuz it's such a big client, it's, you know, notoriety.

[00:11:39] **Ben:** And they finally went and said, Hey, we just, we can't afford to do this. And I don't remember what the number was, but they were like, we need to charge you $200,000 a year. And Twitter was like, yeah, okay.

[00:11:49] **Tim:** No problem. Yeah. Yeah. And that, that, that's sort of the, the philosophy that our, our parent company that, that owns us preaches is like, you know, It's hard. Yeah, you're scared to do it, but it's better to, to do it and get it over with than you. Maybe you'll lose some customers, but there are probably customers that are out the door anyway, so go ahead and do it cuz if you don't stay healthy as a company, you're not gonna be able to support them and then they'll start complaining, you know, that you're not doing what you, you said you can do cuz you don't have enough resources.

[00:12:22] **Adam:** And a customer that's just barely able to afford paying for your service is probably also super annoying with their support requests. And, you know, it's, it's always the customer that's paying like the, it's not even considering how much they're paying you. And they're, they're paying you the most, like the highest margin and they have no support requests whatsoever.

[00:12:39] **Adam:** They're just totally happy and you're like, I need more customers.

[00:12:42] **Tim:** Yep, for sure. Well, Carol's not here. She's got some personal stuff going on tonight. We're recording twice this week, so it made it a little hard to schedule, but, how about you, Adam? What you got?

## [00:12:52] Adam's Triumph

[00:12:52] **Adam:** Yeah. well I'm, I'm gonna call it a mini triumph that we're now officially back on schedule. I didn't wanna go to meta here, but, you know, we've been behind schedule with our recording for a couple of weeks, so I was initially thinking my triumph was gonna be, I, I've successfully herded the cats and we are now back to recording on schedule.

[00:13:08] **Adam:** but you know, like, let's just put that aside. so earlier this week I was feeling, a little burnout and just tired of, some crisis stuff going on at work and, being frustrated that I wasn't having enough time to actually like, do the work, part of work. It was just crisis management. and, but as of like yesterday morning and midday, most of that is behind us and spent all day today like. I don't wanna, I don't wanna shock anybody, but I spent all day today doing work that I had been planning on doing instead of just reacting to things that happened

[00:13:38] **Ben:** What is this madness?

[00:13:39] **Adam:** Right. And, and, and that felt pretty good. So, I'm happy about that. I was working back on my spelt island project, which is, close enough to Dunn that I've kind of pushed it up to QA for most of our customers.

[00:13:51] **Adam:** And,

[00:13:52] **Ben:** This is that modal window you you've been talking about. Yeah.

[00:13:56] **Adam:** I'm excited about it. you know, it's like 95% there. I just got like some edge cases I gotta figure out. And, you know, the best way to find whatever's still broken is to put it in front of customers. Especially, we have a couple of customers that are really good about, using QA heavily and like, they use it as a training environment for their staff.

[00:14:14] **Adam:** And so when something's wrong, they tend to find it pretty quick. And so it's, that's nice. Like it's, it's like, it's almost like having QA testers, right? Except they're just. friendly customers that, that understand that, you know, this is the QA environment, stuff can break. And, and we appreciate their help finding that.

[00:14:31] **Adam:** So yeah, you know, I'm, I'm calling that a triumph. I'm back doing, I'm back to doing the work part of my job instead of the firefighting part of my job.

[00:14:41] **Tim:** Which is also part of your job.

[00:14:42] **Adam:** yeah. Yeah, yeah. It, it's not the part of my job that I enjoy the most, but it's there.

## [00:14:47] Gift Giving

[00:14:47] **Adam:** So. Cool. All right, well, moving on to our note topic, topic. this episode is coming out the week of Christmas, so if you are one that celebrates Christmas, I guess we will try to do something somewhat relevant for you here.

[00:15:00] **Adam:** Christmas stuff. What do you guys got? How are you, how are you guys at, giving gifts?

[00:15:05] **Ben:** Terrible. Terrible.

[00:15:08] **Adam:** Is this, just an understanding between you and your wife? Do you guys

[00:15:10] **Ben:** This is, she is the most lenient.

[00:15:13] **Adam:** you this year?

[00:15:14] **Adam:** And, and she just buys it and says, Hey, look, this is, this is what you bought me.

[00:15:17] **Ben:** I, I ask Carrie if there's anything she wants. and, and this year she's had a lot of,Unfortunate stuff going on in her life with her, with her extended family. So she's super burned out. We're, we're basically gonna have like an unc Christmas, Christmas, I asked her already if, if there's anything in particular she wants and she like, doesn't even want anything.

[00:15:37] **Ben:** so like, that doesn't help me cause I feel like I should get something. but I, I just have no instinct at all for gift giving whatsoever nothing. I, I don't, I'm not, I'm not a big, I'm not a big gift receiver. Like, I don't, I, I just, I don't know. I'm terrible at it. I feel

[00:15:54] **Adam:** Are you the type of person that, like, when you want something, you just save your money for it and then go get it?

[00:15:58] **Ben:** Yeah.

[00:15:59] **Adam:** Like you don't, you don't have a wishlist. You just, you have things that you buy for yourself.

[00:16:03] **Ben:** I'm, I'm like, I just don't, I have a computer. , it's like I don't need a lot of stuff. Most of the stuff I get is for the dog.

[00:16:14] **Adam:** So, my wife is kind of similar, so my wife, grew up very not materialistic. and so she's incredibly difficult to shop for, for Christmas and birthday and stuff, to the point where her parents email me like, Hey, do you have any ideas for Something we can get for her? And I'm like, , I'm supposed to be asking you.

[00:16:37] **Adam:** yeah. And, and so I try, I try really hard to pay attention throughout the year and like if she mentions something that she wants, I'll, I'll either buy it or I'll write it down or whatever. and you know, like maybe in the 15 years that we've been married, maybe like four or five times have actually managed to come up with a really good gift that way.

[00:16:55] **Adam:** And all the rest of the time it's. , are you human? Do you actually have desires or

[00:17:03] **Ben:** I, I, I was better about that early on in, in our relationship about paying attention and, and mental notes. And I don't, I don't know if it's just a laziness thing or it, it's, I don't know, I've just gotten much worse at it. But I do remember, when we, so I'm not one of those, I didn't like secretly pick out a, an engagement ring.

[00:17:24] **Ben:** Like we went to the store and she basically tried on a bunch of stuff and she said, this is the one. And I remember it was really funny cuz we're at the counter and this guy Thomas, who, who managed the store, was helping us with the rings and we find the one. And and he was like, oh, so when you guys get engaged, and I'm like, I, I think it just happened.

[00:17:40] **Ben:** Like, wasn't that it

[00:17:45] **Tim:** That's funny.

[00:17:46] **Adam:** And also we've had a, like the last, I don't know, four months or so, have been really stressful for both of us, at home. And so we were on a dog walk just before I came in and we started this recording. and we were talking about, you know, how she has like basically nothing under Christmas wishlist.

[00:18:04] **Adam:** And, and she was apologizing for that. She was like, I, I've been, trying to think of things to put on there. And just like the, the work of trying to come up with things to put on my wishlist was more stressful than trying to find things for other people. She was just like, I don't know, whatever. I don't care.

[00:18:20] **Adam:** it's like, thanks. That's gonna make it real easy for me.

[00:18:23] **Tim:** How, how do you do your list?

[00:18:24] **Adam:** I, we both just have Amazon wishlist now. I, I have several am I'll, I'll just say upfront, I am greedy, and materialistic and, uh, I, I have a plenty of items on my wishlist that. Most of the people that know me, that have no reason to buy me anything, could get me something and probably not satisfy the entire corpus of my wishlists.

[00:18:44] **Adam:** and I, I, I admit that that's, that's not the best personality trait, but I'm being honest. Right.

[00:18:49] **Adam:** so I have, a couple of Amazon wishlists and she has her own Amazon wishlist and the kids have theirs. And, they do one, that's one thing that's nice is, if you want something that's not on Amazon, they do have like a leave a note sort of thing.

[00:19:00] **Adam:** So you can like just drop in a URL or something. Now you can't then go purchase it on Amazon through your Amazon card or whatever, but you can copy and paste the link out. So that's kind of.

[00:19:12] **Ben:** when I was a kid, I, I have a big immediate family. I have, I'm one of five children. And and I have cousins, but when I was a kid, especially we, we, we didn't have like a close relationship with our extended family. And the idea of getting presents for people outside the immediate family is so far into me.

[00:19:32] **Ben:** And, but my, my wife's family, her whole extended family is very close and she's always talking about how she has to get presents for her cousins. I'm like, for your cousins? What? ? I'm like, first of all, they're grown ass people. , they get their own stuff. And like, I'm like, cousins, really? Or maybe it's her nieces and nephews.

[00:19:52] **Ben:** I don't know. Whatever it is, I'm, I'm just like, I'm like, they got their own family with their own gifts. Like, you don't gotta get involved with that. And she's like, yeah, you do. But that's just, it's so far into me.

[00:20:03] **Adam:** Where I, I felt a little, I still feel a little grinchy about it, but like, I don't know, somewhere around 10 years ago, give or take three years, kids were real young. We were getting real frustrated with trying to buy gifts for my sister-in-law and her, so my wife's sister and her husband, and, and like my brothers and stuff.

[00:20:25] **Adam:** And so we just kind of sent out this email, like, you know, look, we're, we're young. We have young kids. We don't have a whole lot of money. So we would only be spending like 30 bucks a person anyway. That would be our budget. And so like, how about we just agree not to exchange gifts among this group of people, right?

[00:20:41] **Adam:** Like, the ex brothers and sisters. Right. and you know, we, we'll still buy for your kids if you wanna buy for our kids. That's great. Thank you. but we're just, you know, you keep your money. That's our gift from us, and we'll keep our money. That's our gift from you and that's fine. And, I felt awful about sending it, but honestly it's been kind of nice.

[00:20:58] **Adam:** It's been kind of like,

[00:20:59] **Ben:** A hundred

[00:21:00] **Adam:** you know, helps reduce the stress

[00:21:03] **Ben:** I remember my, my wife was like, oh, we gotta get something for your. You're a nephew because he just went off to college and I'm like, no, he's in college. Like he's an adult now. He doesn't need gifts anymore from us. From his extended family.

[00:21:18] **Adam:** Right. He gets a card.

[00:21:19] **Ben:** Yeah.

[00:21:23] **Adam:** So, Tim, I know you're, you don't celebrate Christmas, but, you can still answer the question, how are you as a gift giver?

[00:21:29] **Tim:** Yes. Yeah, yeah. I don't, we don't really do the Christmas thing. so our big thing every year is our anniversary. So it's, kids, kids get us presents, we get them presents. Everybody gives presents. And we kind of do the same thing. You do the Amazon w wishlist, I, they hate buying presents for me cuz I'm kind of like, if I want something, I just go buy it.

[00:21:49] **Adam:** Mm-hmm.

[00:21:52] **Tim:** But, yeah, it's not too bad. They, they make it easy. They, they do put a lot of stuff on their wishlist. And also when we go to Dragoncon, a lot of times we see a huge amount of like, really nerdy stuff and I could see what they want. My kids are very fr kids are very frugal, so it's like, I could see they really, really want it, but they're like, no, I don't want

[00:22:10] **Adam:** you're taking notes.

[00:22:12] **Tim:** they never ask us to buy them anything. So like, this, this, this year my daughter saw, there was this booth at Dragoncon that had like, book binding, like custom book binding. They'll take like They'll take your favorite novel and like bind it and like to make it look real leather and like, sometimes like locks and keys and cages.

[00:22:31] **Adam:** And it's like, and like her favorite author is Brandon Sanderson. The, um,Miss Born.

[00:22:37] **Tim:** yeah, the Miss Born, but her favorite novel is like Oath Springer. And so, We're gonna get her like a bound copy of that,

[00:22:44] **Tim:** like in with leather and like some glowing bits and stuff. So really like a look, like a ancient tome of magic or something that pulls off.

[00:22:52] **Tim:** So yeah, so yeah, we do that. We'd rather like get like one or two like really special things and just a whole bunch of TKIs and stuff.

[00:23:03] **Tim:** So am I a good gift giver? I don't know, but we try to try to pay attention to what they want.

[00:23:09] **Adam:** I, I have a giant stocking and it's not because I bought it for myself, but you know, like a Christmas stocking. and my, when I was a baby, my. I wanna say it was my grandmother. My mom would know for sure somebody made it for me. Right? It was a gift to my mom for me when I was like a year old or two years old, something like that.

[00:23:29] **Adam:** And it, at the time, it was as big as, if not bigger than me. I'm talking, the stocking is like three feet long. Okay. And it, and you could fit like a small dog in it, and so it always stresses my wife out about like, what to put in it. And I'm like, just fill it with chocolate. That's like, literally, that would be amazing, right?

[00:23:46] **Adam:** Just put $20 worth of like Reese cups and, and candy bars and stuff in there. And I'll be good. And she always finds little, you know, little things. She'll go to Harbor Freight and buy some cheap tools for me or whatever, but.

## [00:24:00] Engagement Rings

[00:24:00] **Tim:** so Ben was talking about the engagement ring thing. So it, it is funny when, when, so my aunt, my, my dad's sister is a, is a jeweler. and, they used to have a, a jewelry store in town, but they, they don't just buy you, they actually make the jewelry. Right. So she would, so when I was getting the ring for my, for my wife and also had another friend, he actually worked in Atlanta at the, at the diamond. And so he, took me to the diamond market. I got to pick, I basically paid wholesale for the diamond, and uh,I got one. It was like, not the perfect, like, you know, they'd talk about the seas. It was, it was a little bit yellow, but you really couldn't tell, you

[00:24:40] **Adam:** Yeah. Was that cut? Clarity, color?

[00:24:42] **Tim:** Yeah. And there was, there was a little fracture on the inside, but still it's like, it was a big diamond, but, you know, I couldn't really afford like, the top quality, but it's like, it, it was big, right?

[00:24:52] **Tim:** So you could see it from across the room and go, wow, it's a big diamond. And then if you, and then you look up closer, you're like, oh, okay. Yeah. All right,

[00:25:01] **Tim:** But anyway, so I, so I took, so I took this raw diamond and I took it to my aunt. And so in order to fit it, she needed my wife. So it's like, I, I took my, my fiance, soon-to-be fiance to, To the jewelry store.

[00:25:14] **Tim:** And she's like, what? I'm like, oh, we're just gonna go see my Aunt Kathy. And so you go see Aunt Kathy and Aunt Kathy's like, she says, hand me your, close your eyes and hand me your hand. So she, that's your hand. She fits her and gets it all figured out. She's all right, good. Nike leave. And then she sets the diamond, then she gives it to me later.

[00:25:31] **Tim:** So then I per, I didn't propose for another three months.

[00:25:35] **Ben:** Keep her on the edge of her seat.

[00:25:36] **Ben:** I

[00:25:37] **Tim:** There you go.

[00:25:39] **Adam:** I, that reminded me that when I was, young, I, I don't recall if this was. when I was dating Megan, my wife, or if it was with the previous girlfriend, but, I was given the opportunity and I passed on it to buy an obnoxiously large, but also quite flawed diamond from a guy who was engaged and gave it to his girlfriend.

[00:25:58] **Adam:** and they ended up breaking up or whatever. But the, it was very clearly like, I don't care about color or quality or, or, you know, clarity, any of that. It was just like, I need the biggest diamond you can afford. Right? I want it to be as big as my fist on my ring. Right? And, and, it wasn't quite that big, but you, you get the point and, and I looked at this thing and that you, like, you didn't have to like bring it up to your eye to see the flaws that were like going through the center of it, right?

[00:26:25] **Adam:** You could just hold it in your hand, a foot or two away from your face and see 'em, and you're like, yeah, thanks, but I'll

[00:26:31] **Tim:** did you break your ring?

[00:26:34] **Adam:** right? did you drop this or.

[00:26:38] **Tim:** Yeah.

[00:26:38] **Ben:** When I was a kid, I, I don't know how long cubic SAR has been around, you know, the artificial diamonds. but I remember when I was a kid, my dad either discovered that that was a thing or maybe it had just come out, I don't remember. And he went and he bought my mom this fake diamond ring. It was like huge.

[00:26:56] **Ben:** It was a, it was a huge diamond ring, but it wasn't, it wasn't so huge that it was like clearly fake. And he was so excited and he came home and he, and he gave it to her and she was like, what are you nuts? She's like, I'm not gonna wear this thing on the subway, like someone's gonna cut my hand off thinking that it's a real diamond

[00:27:16] **Tim:** It's funny

[00:27:17] **Ben:** What

## [00:27:17] Christmas Movies

[00:27:17] **Adam:** So how about css?

[00:27:23] **Tim:** Well first, hold on. smooth transition there, bro.

[00:27:25] **Ben:** what about Christmas movies? Y'all have Christmas movies that you get excited for?

[00:27:29] **Adam:** we, we go through the, the classics every year. We always watch the Peanuts one. a a a new favorite for me, it's become sort of a classic in our house is, Arthur Christmas.

[00:27:38] **Ben:** I don't know

[00:27:39] **Adam:** seen that one. It's really good, really cute movie, and it really is like, about the spirit of Christmas and a giving and, and making other people feel good and stuff.

[00:27:47] **Adam:** And, I would, I would strongly recommend that one So animated.

[00:27:50] **Ben:** I'll look it up.

[00:27:51] **Adam:** Yeah.

[00:27:51] **Tim:** So, so my favorite, even though I don't celebrate my favorite, is a Christmas story, which I'll say Die Hard is a Christmas movie,

[00:27:59] **Tim:** but a Christmas story is not a Christmas movie. It is a family movie set at Christmas, which is really, I love, I love that You'll your eye out. But also they just did the, they actually did several sequels, but they did a new, new one with Ralphie grown up.

[00:28:13] **Tim:** It's

[00:28:14] **Ben:** Christmas movie. Christmas movie or something.

[00:28:16] **Adam:** a Christmas story. Christmas.

[00:28:18] **Tim:** Christmas story. Christmas. Yeah. And it was really, I got really emotional watching

[00:28:21] **Adam:** Oh yeah, I haven't seen

[00:28:23] **Tim:** got, so I got all the nostalgia watching that it was,it's not super great, but it's, it was, it was endearing.

[00:28:28] **Ben:** yeah.

[00:28:29] **Adam:** I'm planning on watching that one with the kids here soon. we always go through the, the sixties classics too. You know, the, the stop motion and, I dunno if it's claymation or whatever, but the, like the Rudolph,

[00:28:38] **Ben:** Yeah. My wife loves that one.

[00:28:39] **Adam:** yeah.

[00:28:40] **Tim:** My favorite bit about the, the a Christmas story, what was it called? A Christmas?

[00:28:46] **Adam:** A Christmas story. Christmas.

[00:28:47] **Tim:** A Christmas story. Christmas was that so grown up, Ralphie really like idolizes his, how his dad like pulled off Christmas for his family and, but when you watch the original movie, you as a parent now you realize. That couple was just failing hard.

[00:29:01] **Tim:** They were just, they, they had no, they were clueless. They had no idea what they were doing as parents, and I can so relate to that. It's just like my kids, like, you guys are the best parents ever. We love you. And I'm like, dude, I have no clue what I'm doing here.

[00:29:13] **Adam:** Yeah.

[00:29:15] **Tim:** I'm just happy. You guys are good kids.

[00:29:17] **Adam:** Yeah.

[00:29:18] **Ben:** I'm a huge fan of when Harry Met Sally, and it's not really a Christmas movie, but it ends on, new Year's Eve, so I, I classified as a Christmas movie

[00:29:28] **Tim:** a winter.

[00:29:29] **Ben:** yeah, it, it's a just a fantastic, and, and to me at least, it holds up really well. I mean, I think it's from the eighties and, and, it, it feels very timeless.

[00:29:39] **Ben:** I'm a huge Nora Efron fan. She's the one who wrote it. She also wrote Sleepless in Seattle and, being Julia or whatever. she's written a, a number of really popular movies and, I, I just love that one. I also, and I, and I know that this is not a Christmas movie, it's the wrong holiday altogether, but I've been really craving, Groundhog Day lately,

[00:29:57] **Tim:** I, I love that

[00:29:58] **Ben:** it's so good.

[00:29:58] **Ben:** And I haven't seen it in like 15 years.

[00:30:01] **Tim:** It's one of those, if I, if I flip through TV and I see ground hug, I have to watch it. I just, I'd love it.

[00:30:07] **Adam:** all you have to do is wait for Groundhog Day to come on or to, to come around on the calendar and then turn onto tbs. They run it on a continuous

[00:30:13] **Ben:** Oh, they do? Oh man, I'm, I, I I, I, to me, and, and again, I know it's not a Christmas movie, but it's a holiday movie and I really wanna, I really wanna get that in there this time.

[00:30:22] **Adam:** It's great. I, I just watched that this year with my kids for the first time, and they really enjoyed it.

[00:30:26] **Ben:** do a classic Bill Murray,

## [00:30:28] CSS Updates

[00:30:28] **Tim:** So how about that css?

[00:30:30] **Ben:** how about that? C s s Yo c s. It's just making me nervous. It, it, it, it seems to be moving very fast lately. a lot of podcasts been talking about all the, the new hotness, the color stuff, the, the layering, the CSS grid, which I know is not super new, but it's, it's still, like I, I I still had to support I 11 for a long time, so I couldn't even touch it.

[00:30:56] **Ben:** but, I don't know. CSS to me has always felt relatively, not static, but it, it evolved in ways that felt very easy to slowly roll into the way I approach c css. And it seems now like there's a lot of stuff that is, is fundamentally changing the way CSS works and it's just making me nervous. One that I'm gonna fall behind, but also two. I, I, I'm a little nervous that people are just gonna be too clever sometimes. Like, the, what, what's the one, what's the big one that's come out just recently? Has, or is or no has where you can sit, you can like style things based on other things that are inside of it,

[00:31:40] **Adam:** Mm-hmm.

[00:31:40] **Ben:** and, and people are like freaking out about how great this is gonna be.

[00:31:43] **Ben:** And then I look at some of these selectors and the selectors are bananas and I'm, and it just, it makes me really nervous that people are gonna start creating this really, really complicated CSS, like almost for the sake of having it all in CSS and not having to worry about the markup at

[00:31:59] **Adam:** it, I feel like it's gonna, I think you're right. I feel like it's gonna turn into rejects where it's like you can only write it, you can't read it.

[00:32:05] **Ben:** Yo.

[00:32:06] **Adam:** And, and you know what? Honestly, my opinion, maybe this is a hot take, I don't know, but my opinion is it's not necessary. Like if you're in a situation where you can't solve it without a selector like that, the problem isn't that CSS is lacking.

[00:32:21] **Adam:** The problem is that your application is poorly organized. Right? And, you know, if it's perhaps something like Scoped CSS would be better, right? Like, I, I really am excited for Scope CSS to land one day, but in the meantime, I'm, I'm happy to have it in spell.

[00:32:39] **Ben:** Yeah. Yeah, exactly.

[00:32:42] **Adam:** I have to do is have a, like, it's so great.

[00:32:43] **Adam:** I was working, I, I tweeted something this morning. you know, I was, I, something made me think about, how, you know, as we go through our. We are, you can only put your attention on one thing at a time. So your, your working memory is a stack, right? Stuff gets pushed in and you can pop it out when it's done.

[00:32:59] **Adam:** And, and in theory, you know, it's a, it's a well organized, well executed stack. Something new comes in that has to take priority. You push that onto the stack when it's done, you pop it off and you go back to the last thing you were working on. and so I, I threw together a quick like felt rep. They have, it's kinda like a code pen or whatever, right?

[00:33:15] **Adam:** but it's, it's got spelt built in. so I threw together a quick rep of like, you know, just a quick visual representation of a stack and you can push stuff on and pop stuff off and it, and it shows you the history of what you did to it. And I was like, I'm gonna use this to kind of track my, my work today.

[00:33:29] **Adam:** and it was so much, it was, it was kind of like to the point where I was kind of laughing about it to myself that like to style, to like to style the different components in it. I'm like, oh, okay, here's my selector diviv. because there's only one diviv in this component, So I'm just like the Diviv gets this.

[00:33:48] **Adam:** Oh, it's got a span in it. Okay. Span that gets the this style and it was so nice.

[00:33:55] **Ben:** Yeah, totally. And it's almost like in my mind, the CSS and the markup are just forever coupled. They're, they're the, they're doing the same stuff. They're, or like, you know, they're two sides of the same coin kind of thing. And so I would much rather have a class name somewhere in my component that is a hook essentially for styling, instead of having to worry to say like, do this diviv with this style, unless it has an image in it, than do it with this style, unless that image is also a link than like, do this style.

[00:34:27] **Ben:** I'm like, no, I'd rather just have my angular conditionally apply a class based on some condition. And then my CSS is gonna be super easy to read because it's class name, class name, class name, class name. It's not, it's not element, element, element, element, element kind of a thing. And. It seems to me like some of these really advanced selectors are almost gonna make the code much more brittle, because if you're basing stuff on a class name, you can nudge the dom elements around a little bit, and the class names are the same, and it just continues to work.

[00:34:58] **Ben:** But if you have all these complex selectors and dependencies, then you move the dom around and suddenly your selectors don't match anymore, and now your whole thing breaks and you're like, what? What just happened?

[00:35:09] **Adam:** yeah, that's the, that's funny that you mentioned that that's exactly like the advice that you get about, in browser testing these days. Right. So I, I know this is not, a topic that you'll be up on Ben . Um,but, you know, you, you, you'll use something like Cypress or whatever to, to control the browser to do testing and they, you know, they say don't look for the diviv with ID disk that has an input.

[00:35:31] **Adam:** Right. You know, you're looking for the input that has this placeholder text cuz. You wanna type in that field or whatever. And that way when you restructure the page, the that input is still gonna have that placeholder text. And it doesn't matter what Diviv id, it's in, the user isn't looking for the diviv with the id, you know, XYZ with an input in it.

[00:35:49] **Adam:** They're looking for, this is a field that's asking for this information. So, so test like your user is looking at the application, like what, like they're thinking when they look at the application. and, and I think that the exact same thing applies to styling, just like you were talking about.

[00:36:02] **Ben:** Well, and it's so interesting cause I was actually having a, along the same lines of what you were just saying, I was having a conversation with someone at work where every now and then you'll see somebody or a, a library or, or an organization implement something in a way that's so obvious that you feel stupid that it didn't occur to you.

[00:36:22] **Ben:** And I, I remember it wasn't a testing library, it was like, It was like a, like a call out library. I dunno if you ever, like, you sign into an app and all of a sudden the screen goes gray and there's like a little popup like, oh, check out this new thing that we added. Like kind of something like that. And I had implemented things like that historically.

[00:36:41] **Ben:** And it was that same kind of thing where you wanna point to this button and show a tool tip, but this button's inside a div, which is only shown sometimes and you know, et cetera. And then it's working and then all of a sudden the marketing team is freaking out cause it's not showing anymore. And, and you're like, what's going on?

[00:36:56] **Ben:** That's, oh, because you changed the class because that class didn't mean anything anymore. Anyway, so we use this library one time where their implementation instructions, where you just go and you put completely arbitrary class names that have nothing to do with the style whatsoever. It's like you just put in the Joe Bob tool tip hook class on that element.

[00:37:15] **Ben:** And no matter where you move it, we'll be able to find it. And I'm like, oh my God, that's so obvious. Like, why did that never occur to me to make it have nothing? It, it's like, It never even occurred to me in my early career that you could add class names that did nothing but provide hooks, like class names to me, always had to be about style.

[00:37:34] **Ben:** So if you already had class names about style, those were the things you had to use and ah, just, ugh, can't believe it. So easy.

[00:37:42] **Tim:** Well, I have like zero CSX experience. If

[00:37:47] **Tim:** I, I don't work, I don't work on the front end. If I, if I am, you're in trouble. Cuz everything I, everything I create looks like But I, I did, so I, you know, I was just kind of researching. We do have some on our team. She's really, really good at, styling things and just in a magician at making stuff look good.

[00:38:06] **Tim:** But I, I saw an article and I'll put, we can put it in the show notes. and I put it actually in our Discord chat. If you guys wanna take a look at it, so it's 70 handpicked web-based tools, which are actually useful for CSS. They'll generate pure, pure CSS without the need for any JS or external libraries.

[00:38:23] **Tim:** And some of the stuff they're doing is like crazy magic, and

[00:38:27] **Ben:** Oh, I'll have to take

[00:38:28] **Adam:** is the, oh, this is the super useful CSS resources.

[00:38:31] **Tim:** yeah. Yeah, it, I mean, they're doing, you know, property generators, animations, backgrounds, color tools, topography, you know, CSS loaders, doing layouts, you know, infor gathering information. Just really cool stuff. And it's complete magic to me. Absolutely magic to me. I don't, it's scares me because it's like, you know, you, you put that stuff in a project and if you're like, if I have to go work on it, I'll just go like, hack numbers and see what changes , and sometimes nothing changes.

[00:39:01] **Tim:** Then I'm like, why Nothing change . I don't know what's going on here.

[00:39:04] **Ben:** Well, I mean talk, talk about hacking numbers. That that's the thing where, where I run into the disconnect sometimes. So one of the first really new CSS things that dropped. Like the beginning of this year was all the new color functions. So I'm used to thinking in rgb, red, green, blue, and Alpha. And then I guess like H s L, what is it, like Hughes saturation and lightness?

[00:39:28] **Ben:** Like there's a, a couple of different color functions and people are raving about like, oh, this is such a more natural way to think about colors. And I'm like a natural way to think about colors. Like literally I open the little color palette and I just start moving my mouse around till it doesn't look like garbage.

[00:39:44] **Ben:** Like, that's how I think about colors. It's not like there's a, a science that I'm dying to tap into. So I feel very, I feel very left out when people are freaking out about these colors because like they're clearly operating on a completely different level of how they think about design that I, it doesn't even, I don't even have a mental model for what they're doing.

[00:40:03] **Tim:** Yeah. I'm not even in the, I'm, I'm not, I'm not even in the same planet.

[00:40:07] **Ben:** Yeah. Yeah.

[00:40:07] **Tim:** like much less the same room

[00:40:11] **Adam:** Copy url. Go to Team Chat. Hey guys, check out this new website I found

[00:40:17] **Tim:** That's what I did. So I, I went, I went, I went straight, I went straight to our, our, our, woman who does our, our front ends. I'm like, Hey, check this out. She's sent out. She's like, oh, this is good stuff. I'm like, like, yeah. She also was like, I think I mentioned before, I, you were raving about selt and she started playing around with selt.

[00:40:32] **Tim:** She really likes it so,

[00:40:33] **Adam:** So, okay. this morning I saw Rich Harris, the creator has felt, just tweeted the six, the number six emoji, and it's a reply to a tweet that he had yesterday, that was the seven emoji. So he's obviously counting something down. I'm thinking next Wednesday is gonna be spelt 1.0.

[00:40:53] **Ben:** Oh, right. Cause that's still been in beta officially. That, that, that's the thing that's like the, like the high level bundler and all that stuff.

[00:41:01] **Adam:** It's, it's like the next Js first felt

[00:41:04] **Ben:** Gotcha. Yeah.

[00:41:06] **Adam:** sort of, you know, it is probably the closest thing to compare it to. and, and it's, it's been in release candidate phase for a couple of weeks now, but it's.

[00:41:14] **Ben:** That's exciting.

[00:41:15] **Adam:** happening.

[00:41:17] **Ben:** It's happening.

## [00:41:19] Tailwind CSS

[00:41:19] **Ben:** All right, so you have a note here about Tailwind making you a better css.

[00:41:22] **Adam:** Yeah. So, one of the things that I kind of put on my list of like, I should mess with it this year to, to see what the hype is about. see if I, like, it was Tailwind and I've spent a good amount of time over the last couple of months. I would say it's four to six months. Just like any opportunity I had that was a Greenfield or, you know, it was being sort of rewritten or whatever, I would see if I could include tailwind

[00:41:47] **Adam:** in that.

[00:41:47] **Adam:** Um, and I've, I've found it fun to use. The, the thing that I like about it is it's not just like, you know, bootstrap gives you these six colors that go together or whatever. You got your danger button, your info button, your warning, whatever, that, it's like hundreds of colors that are designed to work well together.

[00:42:04] **Adam:** And, it, it really is. A huge leg up on creating a design design system. And it's a much better default design system than, you know, something like Bootstrap outta the box anyway. but then you've got like all these, everything is, is like, it kind of scales up. I don't know if it's exponentially, but you know, it, things grow at the same rate.

[00:42:22] **Adam:** So you've got like, a, a number system, right? So if you say like padding, you've got padding, zero padding, one, or I don't think it's one. I don't think there's one, but there's a two, there's four, there's eight, and it goes up and up and up. And these are, these are not like eight pixels, that's just like number eight in the design system, cuz you can control what those values are.

[00:42:44] **Adam:** and it, the, it is basically the way that it's designed is that as you're thinking about which one you need for your, for the whatever use case you're on, You just guess. And then like, worst case scenario, because of the way that you're thinking about the spacing that you need, you're probably only off by one if you're off at all.

[00:43:03] **Adam:** Right? So if you guessed eight and, and you're, and you want it smaller, then you go to four if you, and you know, if you want it bigger than it might be 10 or 12 or whatever, but, you know, you're, you're really close. Wow. Voice crack. You're really close in the ballpark there. Yeah.

[00:43:17] **Adam:** I've been really enjoying it.

[00:43:18] **Adam:** And, and, it's funny because like, things that seemed way too complex to me, like I, I tried really hard to learn Flexbox when I came out, and it's just like, it doesn't, it doesn't, it's not clicking for me. I'm not really getting it. And I just waited for a little while until we got CSS Grid and that made a lot more, sense to me.

[00:43:34] **Adam:** And so for, you know, maybe a year now, CSS Grid has sort of been my default. You know, like I, 10 years ago I would've done this in a table, so now I'm gonna do C Ss grid. Well, I've been watching a lot of,tailwind content, like, you know, training videos on egghead and stuff, and they show how to do stuff using Flexbox, but using Tailwind classes.

[00:43:54] **Adam:** And so like, okay, this the, by simplifying the Flexbox concepts down into just a couple of class names that you have to know how to apply, that has made how Flexbox works, understandable to me. And then when I need to do something, it's like, okay, well this would be the Tailwind class. I don't have tailwind available to me in this case, but I can just go look up what that Tailwind class does. Right. And so now I, I'm able to work with Flexbox. I don't, I won't say that it's clicked for me completely yet, but I get it now.

[00:44:23] **Ben:** Yeah, I have, I have trouble wrapping my head around the value add of tailwind and I to, you know, full caveat here, I have not looked into it. but where I do, when you talk about it, the thing that does make the most sense to me is all of the layout related stuff. Meaning the, the flex box, the margins, the paddings, like the things that are around, the things that are the components.

[00:44:48] **Adam:** Mm-hmm.

[00:44:50] **Ben:** But as far as the componentry, and I know Tailwind has a way to say, well, if all of your buttons are gonna look like this, you can make a thing that encapsulates all of those things. And I always look at that. I'm like, yeah. Isn't that just like a component though? Like I don't need tailwind to do that.

[00:45:04] **Ben:** But the idea of not having to write the flex box classes all the time and having to write the margin bottom or margin top all the time like that I get like that I can connect with emotionally.

[00:45:16] **Adam:** Mm-hmm. And, here, let me throw this out there. And that might help you too. So, talking about like design systems, right? So you might have like a brand color, right? The official purple for Invision or whatever it's gonna be, right? And so you, when you do your tailwind config, you can say, this is the brand purple, right?

[00:45:30] **Adam:** Or, you know, if you have a dozen brand colors or whatever. But this is, you know, this is our brand. And you just define that in your tailwind config as a color name and what the, the heck's value, or I think you could do HSL and all those things too. But, and then when you are, applying colors to things like text color, background color, I don't know where else, nothing immediately comes to mind, but like you can then have, that color available to you by name, right?

[00:45:55] **Adam:** So then you go, okay, this, I'm designing a button and I want it to have the purple, the brand purple background, so it's button, you know, BG dash brand or BG dash brand dash purple or whatever. And then what's great about that is that like then in, you know, in five years when they're like, okay, well we're going to transition to a new purple, so we're gonna want to change the, the design over the next six weeks.

[00:46:16] **Adam:** One shade of purple at a time, right? You just go update the config file with the new hex

[00:46:22] **Adam:** and, and redeploy and the whole thing just goes out.

[00:46:24] **Ben:** It's so funny cuz I was actually just today editing some code that was pretty old and it, it's using less CSS, which is a pre-processor for, for those listening. And the code referenced a variable called like enterprise blue and then, but the design is all pink. So they just, they took the variable called blue and changed the hex and now it's the thing.

[00:46:47] **Ben:** So it, it's a css. Custom properties slash CSS variables is also something I really wanna start to embrace a lot more.

[00:46:57] **Adam:** Yeah. The, the CSS custom properties. I've done some and they're, they can be frustrating to work with,

[00:47:03] **Ben:** yeah, sure.

[00:47:04] **Adam:** because like you have to handle the case where it isn't defined or you have to have the case where it is defined and then you can override them in certain con or you can override them, but it only applies in certain contexts

[00:47:15] **Ben:** Yeah, yeah. Cuz it follows the cascade and the

[00:47:18] **Adam:** yeah. And, and that's super useful. But it's also like sometimes, Just want to change something. Right. I just, I just want to override it. Can you just let me override it and, and it's really frustrating to get it to do what you wanted to do, but yeah, I would encourage you, I don't know if you have any, like, if you have egghead, subscription available to you through work or anything, I would encourage you to check out Tailwind through there cuz there's a lot of really good content on that.

[00:47:40] **Adam:** Actually, one of the creators of Tailwind, Adam Wain, has a couple of really good videos on again, so really good stuff. Yeah.

[00:47:49] **Ben:** Let's go back to something Tim's interested in.

[00:47:51] **Adam:** is Tim sleeping on the job

[00:47:54] **Adam:** Hi, uh, you guys Yeah. Talking about Christmas and css. Yeah. Yeah. So I saw a cool tool. website?

## [00:48:02] Location Based Google Trends

[00:48:02] **Tim:** I saw a cool thing that Google came out with, and it is basically in the United States only you can put in your zip code and it will tell you what is trending in your area.

[00:48:14] **Adam:** Oh yeah,

[00:48:15] **Tim:** And so, yeah. So

[00:48:16] **Tim:** what I'd

[00:48:17] **Adam:** search results.

[00:48:18] **Tim:** Yeah, trending search results, so what people are searching for in your area over 20, 21, 22.

[00:48:24] **Tim:** So I'd like everyone put their zip code in there and we'll see. We'll kind of read out and we'll kind of get a feel for what's going on in your, in your, hometowns.

[00:48:34] **Adam:** Okay.

[00:48:34] **Ben:** and it seems to pick the, the biggest metropolitan area near you. So I'm, I got New York, New York, but I'm about two and a half hours away from New York.

[00:48:43] **Tim:** Yeah. We'll put the link in. We'll put the link in the show notes for those who wanna try it themselves.

[00:48:49] **Adam:** so,

[00:48:49] **Tim:** yeah.

[00:48:50] **Tim:** same thing,

[00:48:50] **Adam:** an hour outside of Philadelphia and it got Philadelphia for me, so.

[00:48:53] **Adam:** Well, that's

[00:48:54] **Adam:** all right. We'll go with it.

[00:48:55] **Tim:** I'm 30 minutes from Macon, Georgia,

[00:48:57] **Adam:** Okay, I'll go first. So, so the first thing that comes up for me for Philadelphia says, of the two places that had pickleball as a top trending near me search, the Philadelphia area searched for it the most. Hmm.

[00:49:10] **Ben:** Hmm. Pickleball. Pickleball is, I, I don't know quite what it is. I've, it's been described to me as imagine if you could be shrunk down and put on a ping pong table. but I, I have, I have yet to play it? I don't, I've barely yet to see it. Actually.

[00:49:22] **Adam:** Is that the one that has the like, like a little mini trampoline down in, in the middle of a group of like four people or something?

[00:49:28] **Tim:** I don't think it has

[00:49:29] **Tim:** anything to do with trampolines.

[00:49:31] **Adam:** Hmm.

[00:49:31] **Tim:** I, I've seen it, it, it, hold on,

[00:49:34] **Ben:** I got, I got a New York, New York area, searched for Serena Williams more than anywhere else in the country.

[00:49:42] **Tim:** Serena, so why, why do, why would New York,

[00:49:45] **Ben:** I

[00:49:45] **Tim:** I

[00:49:45] **Tim:** guess, tennis,

[00:49:46] **Ben:** I guess, but I don't, I don't, I don't know if something special happened.

[00:49:51] **Tim:** Well, you guys got cool ones. Mine is the Mac, the , the Macon, Georgia area was the only place in the US that had, Lian in its top trending near me searches.

[00:50:02] **Ben:** what is a electrician?

[00:50:04] **Tim:** I had to Google it myself. A Lian is so when some people go to get their hairs hair braided, so

[00:50:11] **Ben:** Oh, oh, oh. Like, like hair

[00:50:13] **Tim:** or they get, they get yeah.

[00:50:14] **Tim:** Hair locks. So they get dreads or we, you know,

[00:50:17] **Ben:** I gotcha. Gotcha, gotcha. Gotcha.

[00:50:18] **Tim:** yeah, yeah. So

[00:50:22] **Ben:** Well, New York was one of two places that had rainbow mantis shrimp as its top trending animal this year.

[00:50:30] **Tim:** Rainbow man

[00:50:31] **Ben:** I don't even know what that is.

[00:50:33] **Tim:** I don't either.

[00:50:34] **Adam:** I wanted to .I, my next thing was also about the top turning animal. And, but I wanted to overrule it and say that, hitchBOT should have been our top turning animal.

[00:50:44] **Tim:** What is

[00:50:45] **Adam:** hitchBOT was that, somebody, it wasn't a real robot. It was just like somebody like, you know, if you were nine years old and you were trying to make a robot, you would just like bungee cord, took a bungee cord together, a bunch of stuff that looked like it was parts of a human reg, you know, like these flexible dryer hoses as arms and like a laundry basket for a chest, right?

[00:51:03] **Adam:** Like somebody built something vaguely human shaped. Called it hitchBOT and like put a note on it. And they started it in like, you know, somewhere outside of Seattle or something up in Canada, somewhere over that way on the west coast. And they were just like, we're trying to hitchhike all the way across the country.

[00:51:18] **Adam:** Right. And so, like, if you're going that way, pick it up, take it, and it, and it made it like all the way to outside of Philadelphia and then it got destroyed.

[00:51:28] **Tim:** but what was the animal?

[00:51:29] **Adam:** Oh. it says a palace Cat. P a l l a s was the Philadelphia area's top trending animal this

[00:51:36] **Tim:** See, so if you click it, it'll tell you what that is.

[00:51:39] **Adam:** Oh, okay. Yeah. We, I think we have one of these in our, in our zoo.

[00:51:44] **Ben:** Oh, that's cool looking. It's like a, looks like a bobcat sort of a thing.

[00:51:47] **Adam:** Yeah. But it, it's kinda like Bobcat and Grumpy Cat had a

[00:51:52] **Ben:** Yeah.

[00:51:55] **Tim:** Yeah. So mine is the Macon area had vampire bat

[00:52:00] **Ben:** Ooh,

[00:52:00] **Tim:** as this top trending animal and it is the only place in the US with it in the top spot. Same thing for the yeah, the, the,

[00:52:07] **Ben:** the

[00:52:07] **Tim:** Lian.

[00:52:08] **Tim:** Yeah. With very specific needs in Macon, Georgia. You, you, you need to get some braids and you know about damn vampire bats cuz they're coming to get you

[00:52:17] **Ben:** Well, New York searched for disco more than anywhere else in the country.

[00:52:23] **Tim:** disco. Wow. Yeah.

[00:52:25] **Ben:** That's

[00:52:25] **Ben:** hilarious.

[00:52:27] **Adam:** Philadelphia area had cowboy caviar as its top trending recipe.

[00:52:33] **Ben:** Oh my God.

[00:52:35] **Adam:** What the hell is cowboy caviar?

[00:52:38] **Tim:** Macon, Georgia was one of only four places that had bakeries at the top. Trending near me, along with Cheyenne, Wyoming, Eureka, California. Yuma, Arizona. Yeah. I don't think we, I don't think Macon fits in with those places. Macon is making, has said like a murder every day for the past 12 days.

[00:52:59] **Ben:** Oh God. Oh man.

[00:53:02] **Tim:** And then, chicken piccata was its top trending recipe.

[00:53:05] **Ben:** We had something called Green Goddess Salad. I don't know anything in the salad genre.

[00:53:10] **Tim:** I it doesn't surprise me. don't seem like a veg guy.

[00:53:16] **Adam:** Oh, this is, this is interesting. If you scroll down far enough, it's like one of the last couple of things. It shows you the top 10 trending near me, searches in

[00:53:24] **Adam:** your

[00:53:25] **Adam:** region. So , I'll just, I'm not gonna give all of them, but like plasma donation near me.

[00:53:31] **Tim:** That's number four for us.

[00:53:33] **Ben:** Really

[00:53:33] **Adam:** here.

[00:53:34] **Tim:** Oh, wow.

[00:53:35] **Adam:** yeah,

[00:53:36] **Ben:** Ev, every single thing for me is either installation or repair of various appliances.

[00:53:42] **Tim:** Everything's breaking

[00:53:43] **Adam:** Okay, so then I got like pickleball, carnivals, recreational dispensary near me, then remote jobs, concerts, and food pantry. Man, this is depressing.

[00:53:58] **Tim:** yeah, yeah. Lochtian near me home. Covid tests, cheap gas junkyard near me. and passport photos is number one for some reason, I guess. People trying to get outta Macon.

[00:54:09] **Adam:** I'm far, far away.

[00:54:11] **Tim:** Far, far away. Let's just, let's do it for Carol. She's not here, but let, let's, I'll do it for

[00:54:16] **Tim:** Carol. See what she's, I, I, I mean I know she lives in Columbus, Georgia now,

[00:54:21] **Adam:** It's almost not fair. She's not here to defend it.

[00:54:23] **Tim:** Yeah. Well, I've been to Columbus. number one, it's top trending result. Pet friendly hotels,

[00:54:30] **Ben:** Huh,

[00:54:31] **Adam:** Big pet town.

[00:54:32] **Tim:** tr top trending. Well, I imagine they have a lot of military folks in Columbus, so it's like they're looking if they're, they're leaving, they have to have a place or they're, they're visiting family. They gotta have someplace to bring their dogs.

[00:54:45] **Tim:** mute Mun jack deer. The heck is a mutt jack deer. Okay. It's the of deer is the

[00:54:53] **Adam:** Like m u n.

[00:54:55] **Tim:** Yep. rodeo was a top trending of the two places in the country that had rodeo, I guess as a rodeo near Columbus. Red beans and rice top trending recipe. Rap was the top music. And let's see, let's look at their top

[00:55:10] **Ben:** Oh yeah, rap was New York's top music. Also

[00:55:13] **Tim:** staffing agencies. Cheap gas near me, prom, dress near me, hook a lounge near me. Rodeo, oral surgeon and flower shops.

[00:55:23] **Ben:** This, I, I can't get over how much repair New York needs you guys have like, no repair. I literally, it's like all repair

[00:55:31] **Tim:** No, we're just trying to donate our plasmas to get money,

[00:55:35] **Tim:** apparently and to get our hair done.

## [00:55:40] Asteroid Simulator

[00:55:40] **Ben:** All right. Have we put in a no enough, no effort. December into the show.

[00:55:47] **Tim:** I got, I got

[00:55:48] **Ben:** you get one

[00:55:48] **Tim:** I got, I got, this is this really quick. This just won't take long. So if you wanna see what would happen if a, asteroid hit your town, let's, uh,

[00:55:59] **Adam:** Hmm.

[00:55:59] **Tim:** neil.fun. Asteroid launcher. We'll put the link in the, the show notes so you can put in your address or your zip code. And for some reason it starts with New York, so I don't know what that

[00:56:10] **Tim:** has going on there, but, so you can select an implant.

[00:56:13] **Adam:** Oh, cool. You can choose your impact angle speed and the diameter and what type of asteroid it is.

[00:56:19] **Tim:** Mm-hmm. how big it is. Yep.

[00:56:20] **Adam:** I'm just a, a golden one. A gold asteroid.

[00:56:24] **Tim:** Ooh.

[00:56:24] **Adam:** gonna smush.

[00:56:25] **Tim:** Yeah. Mine's gonna be, carbon.

[00:56:27] **Adam:** Well, hang on. I'm, I'm definitely gonna blow up New Jersey, so they're, I'm not gonna use a gold one.

[00:56:34] **Adam:** We'll do a 66 degree angle.

[00:56:36] **Tim:** put,

[00:56:37] **Tim:** Macon.

[00:56:38] **Adam:** Boom. That's pretty.

[00:56:41] **Adam:** So I got a 15, 1,500 foot diameter carbon asteroid. I'm going at 38,000 miles an hour at 45 degree angle launch asteroid. It's gonna make a 3.2 mile wide crater. 13,000 people are gonna die. It's 1,586 feet deep. That's weak, buddy. I, I, I crushed your crater

[00:57:03] **Tim:** you crush your crater

[00:57:04] **Adam:** I killed an estimated 810,000 people. Crater is 0.65 miles deep.

[00:57:12] **Tim:** Ooh.

[00:57:12] **Adam:** 48 miles wide.

[00:57:14] **Tim:** Is that because it's gold?

[00:57:16] **Adam:** No, I was, I did an iron crater or

[00:57:18] **Adam:** iron

[00:57:18] **Tim:** okay. Iron.

[00:57:19] **Adam:** comet or whatever it was,

[00:57:21] **Ben:** That's pretty.

[00:57:22] **Tim:** this size happens once every 47,000 years and it'll make a fireball 5.1 mi 5.1 miles wide and kill an Es. Kill an estimated 133,000 people.

[00:57:36] **Ben:** Oh my goodness.

[00:57:37] **Adam:** I got a, the Fireball, so I hit New Jersey like Southern New Jersey, just kind of across the river from Philadelphia. and the Fireball stretches out to Columbus, Ohio, down to like Charlotte, North Carolina.

[00:57:53] **Tim:** Yeah, people 19 miles from the impact their clothes would catch on

[00:57:57] **Ben:** oh my God.

[00:57:57] **Tim:** And then the shockwave. So 56,000 people will die from the shockwave

[00:58:03] **Adam:** Oh my

[00:58:04] **Tim:** within 34 miles will collapse. Homes within 48 miles will collapse.

[00:58:08] **Adam:** And he won within 309 miles would likely receive lung damage.

[00:58:12] **Tim:** and then the wind, 92,000 people would die from the wind blast.

[00:58:16] **Ben:** Oh.

[00:58:18] **Adam:** I got 24.

[00:58:20] **Tim:** Whoa.

[00:58:21] **Tim:** Holy

[00:58:21] **Adam:** your asteroid is weak friend

[00:58:23] **Tim:** You're, wow. You've op

[00:58:26] **Adam:** we're doing asteroid tear now.

[00:58:29] **Tim:** Yeah. Goodness. That's scary. Yeah. So just a little fun if you know, you know, you're feeling cataclysmic and one

[00:58:38] **Adam:** Somebody gets on your nerves, you really wanna drop an asteroid on 'em, see how precise you can drop it on their head and, and,

[00:58:44] **Adam:** uh, only blow up their neighborhood

[00:58:46] **Tim:** out, ex-girlfriend out in San Francisco. Just, you know, see what happens. we had so much fun. I don't know if we even needed to do an after.

[00:58:54] **Adam:** Well, it is no effort. December, if you guys wanna call it no after show, then that's, we could do that.

[00:58:59] **Ben:** I'm fine to get to bed.

[00:59:01] **Tim:** Yep.

## [00:59:02] Patreon

[00:59:02] **Adam:** All right. this episode of Working Code is brought to you by CSS apparently, new stuff happening, and listeners like you, if you're enjoying the show and you wanna make sure that we can continue putting more of whatever this is out into the universe than you should consider supporting us on Patreon, our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:59:22] **Adam:** Special thanks of course to our top patrons, Monte, Sean and Giancarlo. if you'd like to help us out, you can go to patreon.com/WorkingCodePod. We actually have a new patron to thank this week. So thanks for coming aboard, Steve Kirk,

[00:59:33] **Ben:** Thank you very much.

## [00:59:34] Thanks For Listening!

[00:59:34] **Adam:** and homework this week. you know what, we talked about AI last week and, and I thought it was kind of funny.

[00:59:41] **Tim:** one of the, the, sort of aftershocks, let's use a, a. Asteroid term here, one of the aftershocks of like ChatGPT and all this AI stuff going around was that, you know, we saw, stack Overflow Band using ChatGPT to create, answers for, for their questions. And, you know, it, it occurred to me not only do we not want to ban people, leaving us a five star review with a ChatGPT generated review content, I would say I'll go further and I'll say I encourage it. So leave us your AI generated review. It's gotta be five stars to, to qualify and uh,In fact, actually, I, I generated one. Would you like to hear

[01:00:22] **Tim:** it?

[01:00:22] **Adam:** I would love to hear it.

[01:00:24] **Tim:** Yes. So the prompt was on ChatGPT write a Five Star podcast review about the podcast working code dev and the host Adam, Ben Carroll, and Tim. And it says, I've been listening to workingcode.dev for months now, and I can honestly say that the podcast has been a huge help to my development career.

[01:00:42] **Tim:** The host, Adam, Ben, Carol, and Tim are incredibly knowledgeable and always provide a great perspective on the topics they discuss. They're always friendly and engaging, and their conversations are always thought-provoking and interesting.

[01:00:56] **Adam:** that's how you know

[01:00:56] **Tim:** recommend I highly recommend this podcast to anyone interested in learning more about coding and web development.

[01:01:04] **Tim:** Five stars all the way

[01:01:06] **Adam:** All right.

[01:01:07] **Ben:** I'm blown away by all this AI stuff coming out lately. It's just kinda nuts.

[01:01:12] **Tim:** Yep, for

[01:01:13] **Adam:** I saw a video. I don't, I mean, we're, we're like 90 point percent through the.

[01:01:17] **Tim:** dismount.

[01:01:17] **Adam:** Uh, 90% of the way through the dismount here, and I don't want to like get the show going again, but I saw a video today of a guy who asked it to convert a PHP and jQuery, webpage to use like react and type script and tailwind, and it did it.

[01:01:31] **Adam:** And then he was like, now add, yeah. And then he's like, now add all zero for authentication. And it did it.

[01:01:37] **Ben:** Oh no. You shut your face.

[01:01:39] **Adam:** I I, hey, look, I I don't expect that code to be a hundred percent like perfect le you won't change it. But that saved you like hours of work, right? Like you just gotta go through and be like, okay, this, okay, I would change this, I would change that, but, and hey, look, I'm sure there's limitations, right?

[01:01:54] **Adam:** You can't just throw it at your million line code base and say, here, convert my thing to type script and react and, and it'll do it. But

[01:02:00] **Tim:** Anyway, five star reviews, AI generated user workingcode.dev approved.

[01:02:06] **Adam:** Yep. And, so if you wanna leave us a review, you can go to, Working code.dev/review and that'll take you to the right place to leave a review in your locality. that's it. So, that's it for us this week. We'll catch you next week and until then,

[01:02:18] **Tim:** Remember, your heart matters. It's the best gift we could ever receive. Well, besides Paton donations. But yeah, still, still good
