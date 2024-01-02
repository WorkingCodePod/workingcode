---
title: "160: Design Systems and Coding Philosophy"
description: "Happy New Year! This week, we ease into 2024 with a variety of topics."
date: 2024-01-03
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/6f28d11f-7253-4b0c-a996-fb9f7968c71c"></script><div class="redcirclePlayer-6f28d11f-7253-4b0c-a996-fb9f7968c71c"></div>

Happy New Year! This week, we ease into 2024 with a variety of topics. Adam is building a new design system at work using Svelte and Tailwind CSS. Ben wonders if there's any way to create an "Overview Effect" in the world of programming. And Tim discusses a few philosophical fallacies in a work context: planning fallacy, overconfidence effect, automation bias, and plan continuation bias (aka, the sunk cost fallacy).

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/160-design-systems-and-coding-philosophy.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** I've literally, 'cause everything was just pixel width, like 1120 pixels and margin right. Of 30 pixels. Like I never,

[00:00:08] **Adam:** but

[00:00:08] **Tim:** sound, that doesn't sound mobile friendly at all.

[00:00:11] **Ben:** I, I.

[00:00:12] **Adam:** What the heck are you building?

[00:00:15] **Ben:** Look, if you would just be so kind as to load this in IE8, I think you'd have a wonderful viewing experience.

## [00:00:43] Intro

[00:00:43] **Adam:** Okay, here we go. It is show number 160, and on today's show we are going to do a little bit more of No Effort December.

[00:00:50] **Adam:** For us, it's still December. For you, it is January and onward. so, we're taking it easy on ourselves. A little, time off, I suppose, from, from effort. And, it's just the guys tonight. Carol wasn't able to be here, so it looks like it is my turn to start first with our triumphs and fails.

## [00:01:08] Adam's Failiumph

[00:01:08] **Adam:** So, I'm gonna start us off with a failiumph.

[00:01:10] **Adam:** so I worked this week. I mentioned last week on the show that I took that week off for my week of PTO around the holidays. and that was nice. I had a, I had a good week last week, but this week has been particularly rough. You know, I came back from a week off and I'm not complaining about this part, but it's just odd and different.

[00:01:32] **Adam:** You know, it's quiet around here, right? I feel like most of the customers are either on vacation themselves or, you know, they're trying to keep it low key sort of thing, end of the year. You know, they got bookkeeping and stuff to do. And there's something nice about it, but at the same time, like, I don't know, I just kind of miss the hustle and bustle of the day to day.

[00:01:54] **Adam:** And it feels like, it almost feels like I'm wasting my time, right? Like I'm definitely, I'm working my butt off. I've been working on this design system thing that I'll talk about later.

[00:02:01] **Ben:** I think for, for Steve's benefit, if he's listening, Adam was doing hard scare quotes there.

[00:02:07] **Adam:** Steve doesn't listen. That's okay. And, yeah, you know, it's just like, it's, it's different, you know, I, I don't, look, I'm not, I'm trying real hard not to jinx it here, right? There's still a couple of days left in the work year here, but it's, I just, I feel like I made a mistake taking my week last week and not this week, so I don't think I'll be doing that again.

[00:02:28] **Ben:** You know, I've gone back and forth on how I feel about this because I have many times. been the person who is at work during this part of the holiday season. And it's exactly like what you say that half the company is away, half the company is there, and the half that is there is basically not doing anything.

[00:02:48] **Ben:** Cause there's really not even enough people to. Get anything really meaningful done. Plus there's just like a low level of energy at the company and low level of motivation. And some years I didn't like it. Some years I'd be like, Oh, I can't believe this. Like, why does the company even bother just staying open?

[00:03:04] **Ben:** We're not actually doing anything. We should just take a stand, like a moral stand and just say, you know what? We're closing for everybody between, you know, this date and that date and call it a day. But then some years. I kind of liked it. It was like a, it was like this quiet time to myself where I wasn't with the family, but I also kind of wasn't working.

[00:03:23] **Ben:** And it was this, like, it was almost like a me time. And, and I kind of liked that, but I will say that this year I am off between the, Christmas and new years and, it's actually been quite nice. So,

[00:03:34] **Adam:** Oh, so you and Tim are both on vacation this week?

[00:03:37] **Tim:** Yeah, you're lucky we showed up, buddy.

[00:03:38]

## [00:03:40] Ben's Failiumph

[00:03:40] **Ben:** I'll, I'll go next and I'm going to go with a, failiumph, which is that, as I mentioned on the prior show. I've, you know, I got an early access version of my book out and I'm feeling like I'm making good progress. But as, as we joke about often on the show, the first half, or that was like the first 90 percent of the book takes just as much time as the second 90 percent of the book.

[00:04:01] **Ben:** And I feel like I'm definitely in that second 90 percent right now where. It's like the text is basically done, Adam Cameron's been reviewing it for me, which has been super helpful, but like, I don't really have a cover that I enjoy and some of the images don't really work well on Kindle for some reason, and I don't actually have my iPad with me at the moment, so I can't even be testing on the iPad, and I'm just feeling like It's that part of the publishing process.

[00:04:29] **Ben:** I assume we're having a publishing team would really come into play. I assume that an author who has a company working with them, like they don't even think about this stuff. They write the content and maybe have some input into the illustrations and then that's it. They just, then it becomes an assembly line of people who know how to package and market and polish and compile and collate and, and like the author would never have to worry about this again.

[00:04:54] **Ben:** But. There is no one else. So I'm feeling just like, Oh, I'm losing motivation fast, which is not great.

[00:05:00] **Adam:** you're, you're mostly right. I think the one thing that I understand to be different is that, especially with a, like, a first time author like yourself, or in my case with my book, myself, any publisher would pretty much expect you to have a marketing plan on your own. You know?

[00:05:18] **Ben:** It's interesting. So I think I've mentioned this before, but one of the book series that I really enjoy is A Book Apart and they have an application page where you can. Suggest ideas for books. And part of that is you have to submit a rough draft or, you know, partially rough draft and talk about why your book is different from the other books that are currently in the market.

[00:05:38] **Ben:** And one of the other things that they have is like, how would you go about marketing this book? And what is your plan for spreading the word? And I'm like, Oh, I thought that was your job. Like, why, why do I have to do that?

[00:05:49] **Tim:** Just been saying, I don't know if you've heard, but I'm a pretty

[00:05:52] **Adam:** kind of a big deal. I've

[00:05:55] **Tim:** I've got a blog.

[00:05:57] **Ben:** I'm just like, tag, you're it. Now you go.

[00:06:00] **Adam:** developers that follow me on Twitter.

[00:06:04] **Ben:** So I'm just, you know, one of the authors that I'm a huge fan of is Seth Godin. And he talks a lot about the minimum viable audience, like finding your people that you can commune with. And one of the things that he said that sort of inspired me to finally do the book. And he said, you know, your ideas are not going to be good enough for everybody, but they will be good enough for somebody.

[00:06:29] **Ben:** And like, those are the people that you're supposed to be reaching. and I totally forgot where I was going with that thought. Sorry,

[00:06:37] **Tim:** It's pretty deep though. I mean, yeah.

[00:06:39] **Ben:** oh, maybe I, I think he was, he's, he's also a big proponent of like, just make sure that you ship. Don't get hung up on the perfection of it. You know, kind of like the the just ship book. He says it, I think in a little bit more of an eloquent way, but he says, you know, merely ship, like, that's the whole point is you can't get hung up on all the details.

[00:06:58] **Ben:** You have to believe that the value you have to give is good enough for somebody and just commit to shipping. And I, and I feel like I'm in the phase where I really, really just got to double down on that concept and get something out the door because, I'm exhausted and I just want to get back to having a schedule, like not having, I wake up in the morning and it still feels, it still feels like I have this weight hanging above me and I just want to shed that and get back to some sense of normalcy. So.

[00:07:26] **Adam:** I'm sorry, what is the weight in

[00:07:28] **Ben:** Ugh, that I have to finish this book.

[00:07:29] **Adam:** Oh, okay. Yeah.

[00:07:31] **Ben:** Like, I just need it to be done and off my shoulders. So, yeah. Fail ium. That's me. Tim, what do you got going on?

[00:07:37] **Tim:**

## [00:07:37] Tim's Triumph

[00:07:37] **Tim:** a couple of things. So I'm off this week.

[00:07:39] **Ben:** Noice.

[00:07:40] **Tim:** So yeah, so we're, actually it was off. since Christmas Eve is on a weekend, we took Christmas Eve off on Friday and I don't really go back until, January 2nd. So, yeah, it's about 11 straight days of time off, which is awesome.

[00:07:52] **Tim:** so enjoying that, took the kids, took the whole family up to Atlanta to see a King Tut exhibit that was in town, which was pretty cool. Got to see King Tut's, tomb and then like all the stuff that was, that was just absolutely incredible to hear this kid, he's an 18 year old Pharaoh when he, he was, when he died and it's like, And he was like, basically a nobody in Egyptian history and just the huge amount of treasures and stuff and all the craftsmanship and work that went into, you know, creating his burial site.

[00:08:25] **Tim:** I can't even imagine someone like what Ramses had, right? So it's one of the really good pharaohs, the big pharaohs, right? So much gold and so much, there's all this stuff and just, but it just amazes me that I'm like, his throne was there and I'm going around to the backside to see like some of the wear and tear is like rubbed against the wall.

[00:08:45] **Tim:** You know, it was like an actual person, like 3000 years ago was sitting in this chair and now it's being shown in a warehouse in Doraville, Georgia.

[00:08:53] **Ben:** is cool, though.

[00:08:54] **Tim:** It's crazy. So that was that. And then, today, my triumph is I survived today. So my, my. Daughter, Lily, she's 18 and she, she had a really nice, pirate costume that, that she had made last this year.

[00:09:09] **Tim:** And so she had a pirate party. So it was about a dozen teenage girls that all showed up in pirate costumes. And, the pirate themed snacks, they had, uh,

[00:09:19] **Adam:** Did you cater it?

[00:09:20] **Tim:** no, I didn't cater, she did. So, so, like, croissants, and then they put like a little toothpick with eyeballs on them to make them look like crabs.

[00:09:28] **Tim:** And then like, little hot dogs that they kind of sliced up, you know, and splayed them out, so they look like when they cook, they kind of curled up, so they look like,octopus, and Swedish fish, and, yeah, so, yeah, a pirate themed, you know, treasure chest with, you know, You know, chocolate coins. And then they watched a couple of, Pirates of the Caribbean, movies.

[00:09:46] **Tim:** And then they went outside and had a, a sword fight, which was interesting. Bunch of teenage girls yelling, fight, fight, fight, fight, fight with little plastic sabers and dressed up as pirates. So like, it

[00:09:59] **Ben:** let me ask you a question, because you're in Georgia, which I assume is just hot all year round. I don't quite know what the temperature is like, but I assume

[00:10:06] **Tim:** was in the sixties today.

[00:10:07] **Ben:** Yeah, so I'm in the Northeast. I'm, I'm in New York. and It's like disturbingly warm. Yesterday I was out in my t shirt briefly. I think it was like 54 degrees or something.

[00:10:20] **Ben:** And it was, it was, yesterday was December 27th. And it's just like, it's weirding me out. And, and, and I mean, obviously climate change is a huge hot topic.

[00:10:30] **Tim:** Yeah. And plus it's an El Nino year, so the weather is really

[00:10:33] **Ben:** Yeah. Is it weird down in Georgia? Like, is it, is it, does December feel different for you than usual? Or is it just like hot as usual?

[00:10:40] **Tim:** I mean, it's like, so it's going to get down to 32 tonight, but then it'll be back up in like the high sixties tomorrow. So yeah, it's, it's, it's like this really wide. Swings. So it's like, yeah, we, no one in Georgia thinks, Oh, I have a white Christmas. No, that has never happened. I don't think in, in my lifetime, at least.

[00:11:02] **Tim:** So, but yeah, so I survived the, the pirate party of the girls of all left. I was afraid they'd be screaming while we were trying to record. So

[00:11:10] **Adam:** Were you just like hiding in your office the whole

[00:11:12] **Tim:** yes, I was, my son, Max was hiding in his computer room. He didn't lock the door. He's like, he didn't want any part because he's goes like from my daughter is the oldest dresser, like between the ages of 14 and 18, the median age, about 15 and a half.

[00:11:28] **Adam:** And there's a year or two between your son and your daughter

[00:11:31] **Tim:** yeah, he's 20. So yeah, he, he was just like hiding out and plus he's not, he's not a people person. So anyway, but yeah, I'm glad she did it. She, she got the, some social interactions. So yeah,

[00:11:45] **Adam:**

## [00:11:45] Patreon Stickers

[00:11:45] **Adam:** before we move on to whatever the topic is going to be for today, A couple of quick announcements. I think I mentioned on the show not too long ago that we were goofing around with AI, trying to generate some art. as potential stickers, podcast stickers. And where we landed is we have a couple of designs that we came up with that were particularly, what's the right word here, amused by. And, we've decided to, put out a set of patron only stickers. So if you, want a special working code sticker, you can get that by becoming a patron of the show, and when you do sign up to become a patron, make sure that you put in your shipping address. If you are already a patron, make sure that you go into Patreon, and, I had to recently change our configuration to request your shipping address, so you definitely have not provided your shipping address to us.

[00:12:36] **Adam:** Unless you saw me discussing it on the Discord and checked in on that since that, within the last day or two of us recording this on the 27th, 28th, sorry. anyway, so Patreon, put in your shipping address and you can get stickers from us. And so we have three sticker designs and so the idea is going to be basically you'll get a number of stickers based on your tier, right?

[00:13:00] **Adam:** So our entry tier patrons will get one sticker. We have three tiers, and so second tier will get two stickers, third tier will get all three stickers. and nobody outside of the four of us has seen these designs.

[00:13:10] **Tim:** I will give you guys one hit. So one of the prompts that I put in. is what if a tech podcast and a duck had a baby?

[00:13:23] **Adam:** you just,

[00:13:24] **Tim:** And it came out with a really interesting,result that, that Adam picked and said he'd like. So

[00:13:28] **Adam:** oh yeah. So, you know, we'll figure it out. Maybe that'll be like the middle tier. anyway, so yeah, stickers, if you're interested, you gotta join in our Patreon. I don't have the date in, we haven't decided what the date is gonna be for cutoff. time is an arbitrary construct. You know, I've heard of some, podcasts trying to do something like this, like at the end of the year, something like that.

[00:13:47] **Adam:** We're definitely not gonna hit the end of the year. I mean, you may not even hear this until the beginning of 2024. So, you know, time is arbitrary. We'll, it'll happen soon. Maybe if we're lucky, we'll be on our game more and do something like this earlier next year. But for the time being, if you're interested, become a patron, make sure that you give us your shipping address and maybe next week I will have a, a cutoff date for you. Stickers.

[00:14:11] **Ben:** Very exciting, very official, we're like an official podcast now.

[00:14:15] **Adam:** you'll be supporting a small business and when you do it too, my, my niece is going to print the stickers for us and perhaps do this, the shipping. I don't know. We'll see. I might just have her give them all to me.

[00:14:25] **Tim:** Nepo baby,

[00:14:26] **Adam:** nepotism makes the world go round, doesn't it?

[00:14:28] **Tim:** for sure.

[00:14:29] **Adam:** Okay, well, where do we want to start? we all have kind of some things in here in the list, that we could discuss.

[00:14:35] **Ben:** Why don't you kick it off?

## [00:14:36] Designing a Design System

[00:14:36] **Adam:** Okay, I'll, I'll start. So, I mentioned earlier that I've been working on a design system for my company, and I, you know, the, the general concept that I'm trying to start here is design systems are hard. Like, You know, I've got many years of using, you know, Bootstrap and jQuery UI, that sort of thing. uh, is it under my belt? Is that how you say it? I don't know, whatever. I've got many years of experience of using these things. and, you know, I think I got to the point where I was starting to sort of take it for granted.

[00:15:07] **Adam:** And now, you know, trying to work on my own. It's, it's surprisingly difficult. I don't know if difficult is necessarily the right word. It's just, there's a lot to it, right? You know, it's given me a new respect for the stuff that you'll find in Bootstrap or Foundation or any of these other systems, you know, not only does it have to all like sort of work and look decently in isolation, but then you have to be able to sort of snap together the Lego bricks and come up with something decent, and the thing that.

[00:15:39] **Adam:** It's interesting for me as I'm trying to do this in a way that is going to vastly improve our accessibility scores, improve our like client side validation. and all kinds of, just like, we have so much room for improvement because we've just sort of been like hand rolling, HTML using Bootstrap for the longest time.

[00:15:59] **Adam:** There's no, like, reusable components about it, right? It's all just sort of like, Oh, we did something similar over here on this page, so we'll just go copy and paste and modify, and

[00:16:10] **Ben:** I can interject for a second Because I have also, built a very small design system at work and I did, it was hard at first to not think of, try to think upfront about all the things that I wanted. And when there were things where, even if it was something really silly, like I just didn't know what to call this thing that I was starting to build on a particular page.

[00:16:34] **Ben:** I love the idea of, of like allowing something to show up two or three times before it becomes a quote unquote pattern. So that I can see like, Oh yeah, like, Oh, it should be so obvious that I'm going to have a tabbed interface at some point, but maybe I won't. So I'll build tabs, like I'll hand roll tabbed interface on one page and then I'll hand roll tabbed interface on the second page.

[00:16:55] **Ben:** And then like by the third page, I'm like, all right, now I see the way I want to use tabs. Sometimes I have like numbers. Sometimes I have an icon. Sometimes it's just a label. Now I can get a sense of what the constraints are and now I'll make a tabbed interface widget. And then go back and essentially clean up those previous three pages.

[00:17:13] **Ben:** That, that felt like it was an easier pill to swallow than trying to boil the ocean up front.

[00:17:19] **Adam:** Sure. Yeah, I think I have a little bit more insight to start here, just because we, the goal will ultimately be to replace our existing system. So, like, I know the UI, I know, well, for starters, you know, I have to do all the form fields, right? So you have to have an input and a text area and radio buttons and check boxes and, you know, labels and all that stuff.

[00:17:39] **Adam:** and then, like you were saying, you know, you're going to have tabs, you're going to have modals, you're going to have a sheet, like the, the thing that like slides in from the edge,like extra details or whatever you're going to have, you know, a bunch of these things that like are kind of table stakes for the way that we've been designing our pages for a long time.

[00:17:57] **Adam:** So I don't want to get into a situation where I'm like, okay, well, it's close enough to, to start trying it out. And then like 10 minutes into starting to try to use it for an application, I'm like, okay, here's three components that I need to go create.

[00:18:10] **Ben:** You're right. Exactly.

[00:18:11] **Adam:** So, yeah, like, it's, you're right, there's, you shouldn't try to boil the ocean up front, but also, in the position that I find myself, I feel like there's some obvious stuff that needs to be done.

[00:18:23] **Adam:** And I, I feel like I've got most of the hard stuff done, and now it's just, kind of like you with your book, right? Like, I've done the first 90 percent and now it's just the, the polish,

[00:18:31] **Ben:** The last 90 percent of publish. I, the, at work, we actually, I think Bootstrap is part of our application, but it's a version of Bootstrap from like 2013 and, oh man, they made some.

[00:18:46] **Adam:** know the version number?

[00:18:47] **Ben:** I have no idea what the version number is, but they just made some super, super frustrating assumptions about how things were going to be used.

[00:18:54] **Ben:** Like as you know, it's like a predates Flexbox and CSN grid. So there are things like all labels have a bottom margin and I'm like, F you. Why, why would you have made that assumption? And like all buttons have a bottom margin. And I'm just like, Oh my God, this goes. So when I'm writing my CSS. I'll have the Flexbox stuff and then I'll have margin zero.

[00:19:19] **Ben:** And then I have a CSS comment. That's like overriding terrible defaults in base stylesheet. I'm just like,

[00:19:26] **Ben:** Oh,

[00:19:27] **Adam:** Yeah. I mean, that's one nice thing that I really like about the way that I'm doing these components. So like, when I would run into that problem, it would be easy to override it. So, I'm, I'm doing my components all with Svelte and then I'm using Tailwind. And there's some pretty awesome, sort of like Tailwind adjacent libraries.

[00:19:45] **Adam:** There's a, I think it's called Tailwind Merge. which allows you to, you just give it, like, you pass sequential, it's a variadic function, right? So, an arbitrary number of arguments, and you just pass it a set of strings, and those strings contain a collection of Tailwind classes. And basically, it just is building up the collection of Tailwind classes that you're going to apply, but then whenever there's conflicts, it's last in win.

[00:20:11] **Adam:** So, if you have, like, bgRed 500, and then bgBlue 500. Or 1100 or whatever. I don't think there's 1100. 900. because you set bgBlue 900 after red, the red one just gets removed from the collection of classes. and so, and I don't, you know, I haven't looked at the logic, but it's gotta be crazy. Like, there's so much, adjacency and overlap in those classes.

[00:20:33] **Adam:** I bet it's interesting to look inside that library. And then there's another one, for creating variants, right? So you have like a success button and a danger button and an info button and a brand color button and all these other things, right? and there, it's a way to like, make it easy to create variants of components and say like, okay, the, the success variant has like this background color, this foreground color, this border color, this like hover state, all this other stuff.

[00:21:04] **Adam:** So, and to do it cleanly, like before I found that I was trying to do it manually and it was a nightmare, so I'm very happy to have found that. But, to get back to your original point, yes, especially now that we have Flexbox and Grid, nothing, pretty much nothing should have margin, on it at all.

[00:21:23] **Adam:** And then, even further, I am trying as much as possible to avoid padding. Like, in a couple of places where, like You know, you're only ever like a card and a card title and a card body and a card footer, right? Like the title body and footer can have some padding and and then the contents just float inside there That's just going to make it look nice.

[00:21:43] **Adam:** But yeah

[00:21:46] **Ben:** stuff I find it, like that is my biggest blind spot. I think currently when it comes to design system thinking, which is, I just don't understand where I'm supposed to define the margins and what I mean by that is. Let's say I have a page title and when that page title is say, like in the base layer of the website, it's supposed to have, you know, bottom margin of 30 pixels.

[00:22:13] **Ben:** But then if you open up a modal window and the title in the modal window is actually only supposed to have like a margin of 15 pixels, like, I don't know. I don't know how to differentiate between those two margins in a way where I'm not just like littering the HTML with lots of

[00:22:29] **Adam:** So

[00:22:30] **Ben:** variation.

[00:22:31] **Adam:** I think this is a fairly common, relatively new thought, but, the way I've been approaching this is I have specific components that all they do is space things out. Like I have a, it's called a column component. And so you, you put things inside of a column and it's a div and it's a like CSS grid and with a grid gap, and it's set to only have one column.

[00:22:54] **Adam:** And so it will evenly space things out. And so, so then you, so then nothing has margin and then the, the spacing stays consistent. And if there's only one thing in the grid, then there's no margin around anything.

[00:23:10] **Ben:** See, this is where, so I read, Brad Frost, I think is his name, has a book called Atomic Design. And I think he was very early in the design systems thinking industry. And he breaks up the thinking into four parts and sounds like, you know what I'm talking about, so maybe you can refine my thinking here.

[00:23:27] **Ben:** He's got Adam, which is like a button. And then he has

[00:23:31] **Adam:** A T O M.

[00:23:32] **Ben:** a mo is it a

[00:23:34] **Adam:** Atom, like atoms, molecules.

[00:23:36] **Tim:** Not Adam Tuttle.

[00:23:37] **Adam:** Right, right, right. A T O M, not A D A M. Mm

[00:23:41] **Ben:** So then I think he has molecule, which would be like a search input with a search button as a reusable thing. And then there's something in between. That's like a little bit beefier. And then I think the biggest thing, or maybe the organism is like a collection of molecules. And then I think he has a, a layout and it's, and I never quite understood, you know, it's easy to think about a button because it feels very tangible and I can pipe attributes into it and, and a molecule feels like, okay, I could see a search input plus a button being used in a bunch of places or like text plus an icon used in a bunch of places.

[00:24:15] **Ben:** But then we started talking about layouts. I just, I couldn't visualize it and I didn't have any experience to back it up, but maybe that's, is that kind of what you're talking about? Like. This column spacer is really a kind of a layout component that then organizes all of the little tinier molecules and atoms inside of it.

[00:24:35] **Ben:** Does that sound crazy? Yeah,

[00:24:36] **Adam:** that's how I'm thinking about it.

[00:24:37] **Ben:** yeah.

[00:24:39] **Adam:** Yeah, so, I, I think it was an interview with Brad Frost that I had heard where he basically said like margin on things is, in today's world, granted, you know, I'm not, this is not throwing shade at old versions of Bootstrap or whatever, but in today's world, margin is kind of an anti pattern, right?

[00:24:55] **Ben:** Like you just kind of shouldn't need it for the most part. do get a little frustrated though, because sometimes I'll see, I don't, I don't know, is CSS reset, is that still a thing in our industry? You know, so for people listening who are maybe younger, CSS reset was this concept that all the browsers sort of had little different quirks in the way they rendered stuff.

[00:25:13] **Ben:** So people would have, here's every single HTML element available. And then they would say like margin zero, padding zero, font size, a hundred percent and, and, and which was fine in a lot of cases, but then it came to lists and I'm like, you just took all of my margin off of lists. I'm like, that doesn't feel like good default

[00:25:30] **Adam:** Well, so is it still a thing? Absolutely. because browsers still have Varying default visual presentation of things. So, just having a reset in place, gets you to start from a consistent place across all browsers. Now what reset you choose to use, kind of defines what kind of experience you're going to have with it.

[00:25:51] **Adam:** I've been leaning heavily into Tailwind, and Tailwind comes with its own reset.

[00:25:57] **Ben:** Oh, they have a reset. Okay. The

[00:25:59] **Adam:** and it does some frustrating things, like you're talking about, like, not only, is the, like, margin padding removed from list, but like, the little disk icon bullet before the list items is gone, and the numbers on an ordered list are gone, and like, it's really, like, it basically turns everything into just, like, inline plain text,

[00:26:21] **Ben:** Interesting.

[00:26:22] **Adam:** and you kind of got to build it up from there. It's not that much to it. I mean, we're talking, like, Maybe 20 things that you gotta define in your CSS to get back to a good, solid, and then it would be consistent, base.

[00:26:35] **Ben:** thing in the CSS world that I feel like I completely sidestepped and never understood what it was really used for, and I think is now no longer a thing, are grid systems. I don't know if everyone, there was like a 960 grid system and everything was like 20 pixels of grid and then 10 pixels of margin just repeated like 12 times.

[00:26:54] **Ben:** And to this day, I'm not even quite sure what problems that was trying to solve. And I think maybe it was part of bootstrap. I don't even know, but I'd never used it and it seems to be gone. So like,

[00:27:06] **Adam:** had a grid system built in. It wasn't exactly the same as the 960 grid. But like, you, you, I'm sure that if you've worked with Bootstrap at all, you're familiar with like their column medium for, you know, you have, you have

[00:27:18] **Ben:** you know, I have seen that in code. I have never written that myself. I literally don't know. Is it just widths or was there something more to it?

[00:27:26] **Adam:** How? This is a bigger hole. We need to dig into this. How?

[00:27:32] **Adam:** How have you made it this

[00:27:33] **Tim:** I hate CSS, and even I know that,

[00:27:35] **Adam:** How have

[00:27:35] **Adam:** you made

[00:27:36] **Ben:** had

[00:27:36] **Adam:** working on a website that uses Bootstrap and you don't understand their columns?

[00:27:40] **Ben:** I, I've literally, 'cause everything was just pixel width, like 1120 pixels and margin right. Of 30 pixels. Like I never,

[00:27:48] **Adam:** but

[00:27:48] **Tim:** sound, that doesn't sound mobile friendly at all.

[00:27:51] **Ben:** I, I.

[00:27:53] **Adam:** What the heck are you building?

[00:27:56] **Tim:** A monolith, apparently.

[00:27:58] **Ben:** Look, if you would just be so kind as to load this in IE8, I think you'd have a wonderful viewing experience.

[00:28:06] **Adam:** And the little animated gif at the top of the page tells me that, right? Best viewed in IE8.

[00:28:11] **Tim:** Yep. Using marquee at the top.

[00:28:14] **Ben:** It's the best. So design systems. Yeah. I'm excited to see where you go with this.

[00:28:19] **Adam:** Yeah, it probably is not something, I don't know, maybe we'll see how it goes after, after it gets a little bit of use internally. It might be something we would consider open sourcing, but I mean, I'm building heavily. It's funny, I, I, I'm on probably like version three or so of, my, my approach to this.

[00:28:36] **Adam:** I started out like, I'll just, you know, build it myself, Svelte components and Tailwind, and I'll just do everything manually, and then, I was reminded of stuff like Headless UI, which is a website slash project from the same people that make Tailwind. It's just like a collection of, components designed with Tailwind to provide the like accessibility, look and feel, sort of primitives.

[00:29:03] **Adam:** And then you can tweak the, you know, the colors, the spacing, the fonts, all that stuff. to make it look like it belongs on your website, but then hopefully the, the idea is that you get, accessible, controls sort of by default by, you just copy and paste and modify. so I started down that path and then I found out about this library called Melt, M E L T, UI, which is a collection of, components.

[00:29:31] **Adam:** It's a component library, it's for Svelte, and it's kind of the same idea but like expanded, right? It's all headless components and you get things like tabs and you know, an input or a radio group or modal or whatever. And they're headless and that sort of thing. and that's great. And I started down that path.

[00:29:50] **Adam:** It's like, okay, you know, I'm not that far down. I'll, I'll set this aside and, and try out MELT. See how that goes. And I liked it a lot. and then, you know, a week into that, I'm like, You know, doing more research. How do I make this do behave the way that I want? Where's this? Where's that? And I'm, I discovered a project called, ShadCN.

[00:30:08] **Adam:** That's how I've been pronouncing it in my head. So you may have heard of, Radix or Radix, in the React world, which is a collection of like headless components. And if I'm not mistaken, Radix, Radix is like, you go to the website and you can just copy and paste their components. There's nothing to install.

[00:30:24] **Adam:** You can't install it. it's like copy and paste. And somebody, decided to do a similar thing. It's like they took that concept, the radix, radix, copy and paste concept, and they, and the like headless components that provide accessibility stuff context. And mashed the two together. And that was Sha I think.

[00:30:47] **Adam:** Oh, and, and they also made it like, instead of copy and paste, there's like a command line and you can say, okay, I want to add the popover component to my library. And it already, like, you've given it just a tiny bit of config and it says, okay, this is where I'm gonna add new components. And you just say, okay, add the, add the popover.

[00:31:04] **Adam:** component, and it adds it to, adds a folder to your code and then you can modify it however you want. yeah, and, and then, so there was a, a port of ShadCN, which was for React. A port of that to Svelte stuff. So, right now I'm, I'm on the ShadCN Svelte, train, and I'm really loving it.

[00:31:22] **Tim:** I have to feel like the problem you're trying to solve, I'm pretty sure you don't think someone's already solved this problem.

[00:31:28] **Adam:** Well, that's what I'm trying to do, is I'm, so that's, that's kind of where I've ended up, Tim. the, the components. like the logic, the, the accessibility stuff is all built in. And so when, like the, the thing that I've been working on. So today I was doing like form field stuff. you know, I, I ran the CLI and said, okay, give me the input and the text area and the radio group and all of these things.

[00:31:52] **Adam:** And, and it spits out a little folder with some Svelte components in it. And then I go in and I say, okay, well, but this is the way I want my form fields to look, right? I want them to have a consistent, background color that fits into our theme, right? So I'm really just kind of theming the components that it spits out, and then, you know, little bits and bobs, adding some padding here or trying to, reduce boilerplate by abstracting multiple things away down into one smaller, easier to use component sort of thing.

[00:32:21] **Tim:** So you're not trying to write this from scratch. You're taking other stuff and frankensteining it together and something that makes sense to you.

[00:32:27] **Adam:** Yeah. And, and that's what, you know, that's pretty much the journey that I had to go on, right? Like when I started, I was trying to build it from scratch. And then as like, as I was building it and looking for like, Oh, how, how would I want to do this? Right. How do I build a accessible modal and with Tailwind and Svelte?

[00:32:44] **Adam:** Doing some Googling. And then it's like, okay, well, that's when I landed on the Melt UI website for their Svelte component for, Modal made with Tailwind. And it's like, oh wait, you know, they're already doing this for me. Like, I should be doing that. And then you just, I've repeated that process a couple of times and landed here where I am.

[00:33:01] **Adam:** And fortunately, I do think that I'm kind of at the end of that road. Like I've reached the point now where the project that I'm using is not 100 percent done. The, for example, toast messages, the little things that pop up in the corner of the screen. I saw him work in, the guy who's running the ShadCN Svelte, project.

[00:33:18] **Adam:** He did a live stream today. I didn't really watch it, but I was aware of it. And, he was working on the, the toast component for his library. So, you know, it's not a hundred percent done, but, you know, it's actively being developed. And, so I don't, you know, I don't think that there's another one of these steps in front of me.

[00:33:36] **Adam:** I think I've hit the end of that, chain of like, oh, I should be doing it this way.

[00:33:41] **Tim:** Gotcha.

[00:33:42] **Ben:** One of the things that I struggled with when I was doing my little toy design system at work in, in Legacy Angular was initially trying to create. All of the design system in the same mechanics. And what I mean by that is there's some stuff that's sufficiently complex where you actually wanna wrap it up inside of a component and then pass attributes into that component.

[00:34:10] **Ben:** But then there's some stuff that's just stupid simple. Like I have a, a strong tag, you know, like a bold tag and like I just want to give it a slight variation. And like, I don't want to componentize that. That can just be a CSS class that is provided by the design system. I've definitely seen people go like hard pendulum all the way to one side where You're actually, there's like a text item component that then you pass in a variation to so that it outputs a strong tag.

[00:34:39] **Ben:** And I'm just like, does that really need to be a component? Cause it feels like that was just some simple text. And like, obviously everyone has to have their own discussion inside their head about whether one way is more right or less right, or has a better trade off or, you know, whatever. But that, that was a tough conversation for me to have with myself was just accepting the idea that not everything in this.

[00:35:00] **Ben:** Design system boundary has to be a component that sometimes it can be a component when it's complex and sometimes it can just be a CSS class when it's simple. And that ended up actually being very freeing for me.

[00:35:12]

[00:35:12] **Ben:** I've, I've often wanted to look into, so there's another podcast. I think it's just called CSS podcast

[00:35:19] **Adam:** on us?

[00:35:20] **Ben:** constantly, with Una Kravitz and Adam Argyle from, I think they're both from Google maybe. And Adam

[00:35:28] **Tim:** Lenny Kravitz?

[00:35:30] **Ben:** she's actually very musically talented, having nothing to do with CSS, but, he has this project called Open Props.

[00:35:37] **Ben:** And it's like a huge collection of CSS custom properties that are intended, I think, to help drive design systems. I have not personally looked into this, but it might be something. You would be curious to see.

[00:35:51] **Adam:** I will pull the link out of our show notes and go take a look at it when, when you post those.

[00:35:55] **Adam:** All right, well we've been on design systems here for a while and why don't we, switch gears.

## [00:35:59] Overview Effect

[00:35:59] **Ben:** Yeah, sure. I'll, I'll go, if you don't mind there, Tim. so I, as I mentioned on the previous podcast, I think that at the end of the year, yet another podcast dotnet rocks, they do an end of the year sort of science and tech roundup, they do like a really deep dive and anyway, they just released their deep dive today.

[00:36:17] **Ben:** I have not listened to it, but it's, it's all about space and. It got me thinking, just in passing, about something called the overview effect, which, as I understand it, is this reframing of one's reality, that once they're in space, and they see this little blue orb, which is Earth, it completely just Thanks.

[00:36:39] **Ben:** Shifts their perspective on humanity and coexistence and borders. And, and, it just opens the heart. I, I think this is like a, kind of what people talk about after they've taken, LSD, right. And just like, it's like, yeah, yeah. And it's just like, and now I just see people differently and my mind is, is forever changed.

[00:36:58] **Ben:** Anyway, in the programming world, we tend to form these tight knit communities and sometimes for better or worse, these communities can become. Maybe too tight knit, maybe too echoey chambered, and we lose sense of the larger programming world. And I just was curious to, as a, as a thought experiment, is there a way that we could somehow create an overview effect for the world of software development?

[00:37:27] **Ben:** and I think back to this visualization that I saw of Jeff Bezos's Wealth. I don't know if anyone's ever seen this. It's a side scrolling webpage.

[00:37:35] **Adam:** Mm,

[00:37:35] **Ben:** And it's like one pixel of width represents like a hundred dollars or a thousand dollars or something. And so you just keep scrolling, right? And it's like, here's how much the average American makes.

[00:37:47] **Ben:** And like, here's how much a house costs on average. And you just keep scrolling, right? And it's like, here's the GDP of the Netherlands and, and you keep scrolling right, and it's just forever until you finally get to the end of the earth. And it's Jeff Bezos wealth in pixels. And it just really puts it in perspective.

[00:38:04] **Ben:** And I thought, what if you could take something. Like that and, and map out software, like, like a, like a tag cloud of how many lines of code in existence map to different technologies, or like what amount of revenue has been generated by a particular technology, or, I mean, I'm just, you know, shooting from the hip, but something where you could say. You know, people freak out like, Oh, everyone should be using, Redux. And then you're like, okay, how does Redux fit into the history of software? And you pull up the giant map and it's like, you know, here's this massive IBM over here, and then here's Apache. And then like,

[00:38:42] **Tim:** COLBOL is hands down the winner.

[00:38:45] **Ben:** you know, and it's like, and here's this one pixel on the bottom right, that it's Redux and you're like, Oh, okay. Maybe that's not the most amazing thing that's ever been invented. And I don't know, I just think it would be a very fun visualization that would help people have perspective in a world that doesn't have a lot of perspective.

[00:39:02] **Tim:** I mean, you'd have to figure out what you're measuring. You said lines of code. I mean, that's, is that a good measure? Money, you know, profit generated.

[00:39:11] **Ben:** I think it'd be fun to do it different facets because you could like lines of code, you could do things like lines of code that had been written consuming a technology versus lines of code. is the technology, you know, you could go, so not to pick on Redux or anything, but like Redux. It was like 30 lines of code or something.

[00:39:31] **Ben:** Right. And then you could look at something like a, like a Postgres driver for Java and like, what is it

[00:39:36] **Ben:** like, like, yeah, like, what is it like 25, 000 lines of code and just to like give you this general sense of how things exist in the world next to everything else. I feel like it would be fascinating. And I, and I, and I think, I mean, I'm just as guilty. Of this as anyone as to looking inwardly to my own echo chamber of technological decisions and choices. And I'm always, so this is one of the reasons that I love to listen to podcasts for technologies that I don't use at all. Like I don't use. net. I, I mean, I've used C sharp like 20 years ago and I have not used it since.

[00:40:16] **Ben:** And if you only lived on Twitter, it feels like you would believe that the entire world runs on JavaScript. And that everything else is dead. And then you hear that, Oh yeah, there was a NET conference, in Spain and there were 15, 000 people in attendance. I'm just making this up. You're like, Oh like maybe Twitter is not where I should be getting my information about what's hot. and, and we lose those, we lose those bigger picture views.

[00:40:43] **Tim:** It's called X, by the way.

[00:40:45] **Adam:** You gotta do, Tim, you gotta do this. You gotta push the glasses up the

[00:40:51] **Tim:** X.

[00:40:52] **Ben:** Anyway, I just think that would be really fun thing to see.

[00:40:55] **Adam:** Yeah, I mean, obviously you're, you've got a data problem, right? Even if somebody wanted to play with this, like you guys were talking about, you know, you got to decide what you're going to measure and visualize. And I don't think that any sort of centralized data exists. So really what you've just, created for yourself as a research problem,

[00:41:13] **Ben:** Right. Yeah, yeah.

[00:41:14] **Adam:** have fun with that.

[00:41:15] **Ben:** Well, but people,

[00:41:17] **Adam:** done, but,

[00:41:18] **Ben:** people do attempt to look at this from different viewpoints. So, so GitHub, for example, you can probably get some sort of relative lines of code in GitHub. I know you can get it at the individual project level. I assume they can do some sort of more macro and then I think people will scrape.

[00:41:34] **Ben:** Web page archive and look at which libraries are installed in different websites or something like that. You know, they, when, when people joke, like 70 percent of the web still actually runs on jQuery or something, they like that information has gotten from, from somewhere, I'm not saying that this is the answer, I'm just saying there are very clever people and I believe in them.

[00:41:52] **Adam:** Yeah, I mean, I, I think that at the heart of what you're talking about is just this, the, the desire to help people get a, a better sense of the importance of the things that they feel hung up on, right? And I think that that's a, a very, noble goal. And I think that, were it possible, and I don't think that it is reasonably possible, like, sure, is it possible?

[00:42:18] **Adam:** Absolutely, somebody could figure out how to do it and do it, but I feel like that's gonna be one of those things that's like, My life's work is making this visualization, right? Versus, like, should is it something anybody should take on? Is it actually going to, be that transformative where where that person will be super glad that they did?

[00:42:36] **Adam:** I I wouldn't bet my money on it.

[00:42:38] **Ben:** No, if it were easy somehow to have it, it would be great.

[00:42:42] **Adam:** And that's exactly what I'm saying. So I think that it's a, it's an interesting thought experiment around a noble goal. And I think that, right. So, to apply the entrepreneurship startup mentality to it, like, okay, if that's, if that's the goal, that's the thing that the problem that you're trying to solve, like what's the skateboard version, right?

[00:43:01] **Adam:** If that's the, if that's the, the Ferrari of the, the, the solution, what's the skateboard version of the solution?

[00:43:09] **Ben:** Yeah, I feel like the skateboard version would be using every publicly available package manager, do something like NPN and Maven and apt and apt get and pip and like all of these things. Like, I don't know how many package managers there are out there or whether or not they're for every language. I assume every language more or less has a package manager at this point.

[00:43:33] **Ben:** Like, could you do something just with that?

[00:43:36] **Adam:** Only the good languages have package managers, Ben.

[00:43:40] **Tim:** I mean, I, I do know, so Stack Overflow, they do an annual thing where they do kind of the state of the developer kind of thing. Have you seen that? And like, for instance, like I'm looking at 2022, they did, it's a survey. So it's like, they're not going out and like scraping data, but people are doing a survey and like, what's the most popular technology?

[00:44:02] **Tim:** I mean, JavaScript, 65%,

[00:44:04] **Adam:** hang on. So we have to talk about sampling bias here. So this is going to be, what's the most popular technology among people who struggle to get their work done?

[00:44:10] **Tim:** exactly right. They're doing Javas, JavaScript, HTML SQL, Python, and TypeScript. Right. So, yes, so yeah.

[00:44:18] **Adam:** I can't, I can't find it. There was a, I mean, you talked about comparing package managers. There was a website that I'd seen where you could see like a number of packages, number, I think it might've had lines of code and like, you know, count of versions or whatever. And it would go across package managers, so you could compare npm, and pip, and maven, all these other things, but I can't find it now.

[00:44:41] **Ben:** so the overview effect. That's a fascinating idea.

[00:44:45] **Adam:** when you brought that up, the overview effect, the very first thing that came to my mind, and I just want to throw this out there because it's fun, so if anybody is one of today's lucky 10, 000 who doesn't know about this, there's a photo, a very famous photo of Earth from, I want to say it's Voyager 1, might have been Voyager 2.

[00:45:01] **Adam:** and they call it the pale blue dot, right? If you just go to Google and search for pale blue, pale blue dot images, you'll see a photo from space. It's a very grainy photo and it just looks like this big open, blackish field, and there's like a sunbeam going across the image. And in the middle of the sunbeam, it's like, you know, four pixels or something like that of a pale blue dot.

[00:45:22] **Adam:** and you know, that's, that's, you know, even further, right? The overview effect, I think that you're talking about is like. What was reported by astronauts like when they were on the moon looking back at the earth or that sort of thing Where you can kind of put up your hand and cover the entire world And this is like you can kind of like hold up, the tip of a pencil and at eyes At

[00:45:41] **Tim:** was Voyager one

[00:45:42] **Adam:** cover the whole world.

[00:45:43] **Ben:** I think that was the first photo of Earth taken from space. I feel like I heard that. I could be wrong.

[00:45:49] **Adam:** I yeah, I don't know. but then further there's a wonderful quote I think we talked last week maybe

[00:45:55] **Ben:** Carl Sagan.

[00:45:56] **Adam:** about cosmos. Yeah, and so Carl Sagan sort of One of my, my favorite scientists. Rest in peace. he has a wonderful quote to go along with the Pale Blue Dot. I'm not going to read it because it's, it's relatively long, but you should Google it and we'll have a link to it in the show notes.

[00:46:10] **Adam:** It's smooshing

[00:46:13] **Ben:** Yeah, I know. I'll definitely take a look. I know very little about him.

## [00:46:17] Coding Philosophy

[00:46:17] **Tim:** So it's interesting, you, you talk about the overview effect. 'cause I mean that's sort of a, a philosophical take on, on looking at coding and software. That's was sort of where my mind was going. As, as I get older, it's like I'm less interested in learning about new coding things. and more interesting, more sort of philosophy.

[00:46:36] **Tim:** I do read a lot of philosophy, myself. I don't know why I'm drawn to that, but I, but I am. and particularly today I was looking at, like fallacies, but thinking about how it applies to not only software development, also just sort of the, the lifecycle of software. So for instance, we have the planning fallacy. The planning fallacy is a tendency for people to underestimate the time it'll take for them to complete a given task.

[00:47:03] **Ben:** Well, I'm familiar with this. I'll take two of those.

[00:47:10] **Tim:** yeah, so I mean, I got a developer as I, as I kind of learned the developers that are, that are working with me, it's like, I can get a gauge of, you know, sort of their level of optimism.

[00:47:19] **Tim:** I get that done pretty quick, probably, probably take two weeks. And in my head, I'm like, all right, I'm going to set a timer for. Six weeks and check in with him because I, because I know by that point, he'll probably be close to being done. And then at that point, he's like completely, you know, it's like apologizing.

[00:47:36] **Tim:** I'm sorry. I said, I'm like, you know, it's, it's okay. I seem very forgiving, but honestly, in my head, I'm like, yeah, you have a planning fallacy problem. you, you, you always underestimate how long it's going to take. So, but, and that's just human nature.

[00:47:49] **Ben:** Have you, I was just watching a movie over the holiday here. I think it's called The Holdovers with Paul Giamatti. I think it takes place in like the seventies. He's, he's. Taking care of, some boarding school kids. Anyway, for Christmas, he gives out copies of it's, like Caesar's meditations or

[00:48:08] **Tim:** No, it's Marcus Aurelius

[00:48:09] **Ben:** Marcus Aurelius has, have you read that? Is that, is that

[00:48:12] **Tim:** I have, I have read that multiple times. I actually, we talked about it one time on the show. It's, it's, I highly, highly

[00:48:18] **Ben:** Do they have an audio book version? You think should I,

[00:48:20] **Tim:** do. They do. And there's, there's another book that they've talked about on the show. I'll find it later. But yeah, there's a, there's a behavioral psychiatrist who kind of goes through Marcus Aurelius meditations kind of explains how it ties in to behavioral therapy and Stoic, because Marcus Aurelius was a Stoic, right?

[00:48:40] **Tim:** So if you watched, Gladiator, it was based off of Marcus Aurelius. Marcus Aurelius was the, was the older emperor who's dying. And that's, he was a true, that was a real emperor. He was very much a Stoic philosopher. And his son, Commodus, who was played by Joaquin Phoenix, was a complete. Animal, amoral, just terrible human being.

[00:49:01] **Tim:** and that's all, I mean, that part is true. Obviously, the whole story isn't true, but, yeah. Meditation is extremely, extremely good book.

[00:49:09] **Ben:** I got to check that out.

[00:49:11] **Tim:** And it's short. It's relatively short. And what's interesting, it was not, he didn't write it to release it. It was sort of his own personal diary about his struggles and about his life and about how, you know, things he was thankful for, things he was working on, how he's trying to be, following the stoicism way of life.

[00:49:29] **Tim:** and I think people really get stoicism kind of backwards. I think it's all about self denial. It's not. It's really not. It,

[00:49:36] **Adam:** in the curves, right? Not allowing yourself the super excitement and not allowing yourself the super depression.

[00:49:42] **Tim:** Yep. So, you know, they, they, they weren't against like, drinking and, you know, but it's like, if you, if you get drunk to the point tomorrow, you feel terrible for most of the day, then what's the net benefit there? It's like drink just enough to feel good. And that's, that's perfectly fine. But if you drink, you know, it's all about just drinking in excess, then the negative effects are going to ruin you.

[00:50:02] **Tim:** And like, the biggest thing is don't. Concern yourself with things you can't control. Control what you can, deal with, deal with what you can control, and then don't worry about the rest because worry is just killing yourself. So anyway, so philosophy, another one is the overconfidence effect. That's a tendency to

[00:50:22] **Adam:** Yeah, I don't have that one.

[00:50:24] **Tim:** excessive confidence in one's own answers to questions.

[00:50:28] **Tim:** For example, certain types of questions, answers people rate as they're, they're 99 percent certain they're chosen, chosen thing or whatever the, you know, they're, they're, however they're going about solving a problem is 99 percent certain that it's right. And it turns out it's 40%. Wrong, most of the time.

[00:50:49] **Tim:** So I think, I think we see that a lot too. And like choosing a technology, choosing, you know, the, what was I looking for? The pattern,

[00:50:58] **Ben:** Design patterns.

[00:50:59] **Tim:** This design pattern to go with, you know, right. So we're like absolutely certain, Oh yeah, this is totally the observer, you know, pattern that we need to do here.

[00:51:06] **Tim:** And it's like, you know, get like mostly done with it. You realize that probably wasn't the best pattern to choose.

[00:51:13] **Adam:** 60 percent of the time it works every time.

[00:51:15] **Tim:** Exactly. and then automation bias. So this is, this is another, bias that people have. It's the tendency to depend excessively on automated systems, which can lead to erroneous automated information overriding correct decisions.

[00:51:28] **Adam:** What do you mean by that?

[00:51:29] **Tim:** So you, you automate something, you create a system, right? To track something or to do something. And there's information that comes out of that automated system, right?

[00:51:41] **Adam:** Mm hmm.

[00:51:43] **Tim:** You're basing all of your information off the what the feedback you get from an automated system. But the automated system is not measuring the correct thing.

[00:51:51] **Tim:** It's going to lead to incorrect decisions.

[00:51:55] **Adam:** So it's, you're just talking about like a flaw in the automation itself, not necessarily,

[00:51:59] **Tim:** Right. It's just depending on the automated system. So, and it, it doesn't also 100 percent apply to

[00:52:07] **Adam:** so it sounds like it's saying it's important to keep a human in the loop.

[00:52:10] **Tim:** right. And it can happen in organizations, right? So you have an automated system of commissions. So you're going to incentivize people based off of. How much they do X, all you're really doing is making sure they do X.

[00:52:23] **Tim:** Doesn't necessarily mean that that's the commission is to drive a goal. The goal is to make the business successful, right?

[00:52:31] **Adam:** right,

[00:52:33] **Tim:** If X is not perfectly aligned with making the business successful, you're measuring that and going, Oh, we're doing great, but really overall business is failing because you're measuring the wrong thing and basing off this automated system of, of getting that information.

[00:52:46] **Adam:** Yeah, we've talked a little bit about that in the past, like, uh, you know, as soon as you start measuring something, it ceases to become a useful measure, basically.

[00:52:55] **Tim:** Mm hmm.

## [00:52:57] Podcast Listening Speed

[00:52:57] **Ben:** Let me ask Adam a question, kind of an aside here, but I know Adam's part of the 2X club. Podcast listening speeds.

[00:53:05] **Ben:** if you were going to listen to a book like Meditations by Marcus Aurelius, which is not just a book about information, but is like a meta analysis about thinking, would you listen at 2x speed?

[00:53:19] **Ben:** Or would you want to slow down for a book like that?

[00:53:21] **Adam:** probably not. So, one of the things that affects how fast I choose to listen to something is familiarity with the speakers, the way they think, the sound of their voice, right? So, when I'm listening to a podcast, even if, like, even if it's one I listen to all the time, like, Syntax, right? I've listened to hundreds of episodes of that.

[00:53:44] **Adam:** And so, if it's just the two of them, I can listen at 2, 2. 5. If I'm not really paying super close attention, I could probably go up to 3x on a lot of their episodes. but if they have a guest on, and that guest has an accent that I'm not super familiar with, or, you know, like, like somebody with a really particularly thick accent, even if it's like Scottish or

[00:54:03] **Ben:** Yeah. Yeah.

[00:54:04] **Adam:** Like, not that it's difficult for me to understand, but it's just hearing through the accent can be difficult.

[00:54:09] **Adam:** Um, and, and likewise, if I'm really trying to learn, from something. Like if I'm, if I feel like I, there is a lot of value in me paying super close attention, then I will slow it down. I, I don't know that I could do 1.

[00:54:26] **Adam:** 0, but I might do, you know, 5, to just, cause I feel like most people, especially if you're talking about like somebody reading an audio book, there's a lot of slow, intentional

[00:54:39] **Ben:** of cadence work

[00:54:40] **Adam:** sentence. Yeah. And I'm like, yeah, I don't have time for that. Just give me the words.

[00:54:44] **Tim:** So, I can't find it right now, but I did read something recently, it made me think of you. because I, I think you've mentioned on the show before that you have ADHD, right? So, the, the article I read basically said that ADHD people actually can listen to sped up audio and get full benefit out of it.

[00:55:01] **Ben:** Oh, interesting.

[00:55:03] **Tim:** And so I thought about this like, cause I'd never listened to anything.

[00:55:06] **Tim:** And I'd listen to everything at 1x and

[00:55:09] **Adam:** Yeah,

[00:55:09] **Tim:** everything at 1x.

[00:55:12] **Ben:** Oh my God.

[00:55:14] **Tim:** And Adam, you've made remarks like, I'm not going to listen to it at 1x. Like the person's talking, they're drunk.

[00:55:21] **Adam:** Yeah,

[00:55:21] **Ben:** God. So drunk. Oh

[00:55:25] **Tim:** So it made me think of you.

[00:55:28] **Adam:** we should do like drunk audiobooks. Like just get drunk and read a book into a microphone.

[00:55:35] **Tim:** I

[00:55:35] **Tim:** mean, that's kind of how I do this podcast. So I got, I got one last one philosophy,a bias, plan continuation bias.

[00:55:45] **Adam:** Okay.

## [00:55:45] Sunk Cost Fallacy

[00:55:45] **Tim:** And I think this is a big one, right? So plan continuation, it's a failure to recognize that the original plan of action is no longer appropriate for a changing situation where the situation is different than anticipated.

[00:55:57] **Ben:** If I can just interject with a, a different term, and I don't know if this is the same thing or, or just a different, different concept. Yeah. Sunk cost fallacy is typically what I would call that for other people.

[00:56:11] **Tim:** And that's true. I mean, so you come up, you have a big project, everyone says, all right, how are we going to attack this? You do the pre mortem on it, you do whatever, and you start working. And it's like, then the wheels just fall off the whole thing. And it's just not working out. And people are like, well, just keep doing what we're doing and it'll get better.

[00:56:29] **Tim:** Cause we planned this. Everyone agreed to it. When maybe that's not the best way to go. Maybe the best way to do is to stop, figure out, all right, why isn't this working? What do we need to change? Rather than just keep throwing, like you said, you know, sunk costs, keep throwing good money after bad, continue to fail.

[00:56:45] **Ben:** I was listening to a podcast. I can't remember which one it was. It's, it seems like it would be the hidden brain. This feels like a hidden brain topic where a guy rephrased that to help himself deal with it. And he talked about not in terms of things that he has spent time, effort, money, but instead he's given his future self a gift and that when that future self arrives, it's up to him, whether or not he wants to continue receiving that gift.

[00:57:15] **Ben:** and the, the example that he gave. That made it more concrete is that imagine that you bought tickets to go to the opera and it was the 300 tickets and you're on your way to the opera and you run into your friend and your friend said, Oh, I'm so glad I ran into you. I actually have Hamilton tickets.

[00:57:32] **Ben:** But I can't go. My wife just went into labor and I have these two Hamilton tickets and they're like, there's like a two year wait. Do you want these tickets? I'm literally on my way to the hospital. And you have to decide whether or not the fact that you've already spent 300 on opera tickets is more important than these, like.

[00:57:50] **Ben:** What he was painting as like priceless tickets to Hamilton. And he was saying that it's not that he spent 300 to get these opera tickets is that he gave his future self a gift. And now his friend is giving him a different gift and he's basically just choosing between two different gifts. And it's not this sense of obligation to his former self.

[00:58:10] **Ben:** It's just, he's enjoying this opportunity of selecting gifts and that's how he. Works through that, that bias effectively for himself, which I don't know. I just thought that was a very nice way to, to paint it.

[00:58:24] **Tim:** Yeah. I mean, that's called reframing, right? So that, that's when you, when you have sort of this cognitive dissonance that you sometimes just reframing it and looking at it from a different perspective. It helps you come to terms with it. Like, so like, Oh, the, this, you know, the steak is, is 80 percent protein.

[00:58:42] **Tim:** Yeah. But it's also 20 percent fat. So, I mean, it depends on how you frame that. It makes a big difference.

[00:58:48] **Adam:** I'm trying to think of, like, the, the way you were explaining it, Ben. I forget if you gave it a name or something, but, you know, sunk cost fallacy. I think for me, the, the immediate thing that it calls to mind is the way that Elon Musk runs SpaceX, right? So they, you know, there's a billion different examples you could pull.

[00:59:06] **Adam:** That's just the one that comes to mind immediately for me. And. You know, they might be halfway done building a rocket and they realize that there's a stupid mistake or a 15 percent performance improvement change they could make. And instead of finishing the rocket, they will just be like, okay, scrap it and start over and make the new one with the improvement because they're not, you know, they, it's clearly enough of an improvement that they're not going to continue making.

[00:59:35] **Adam:** And I'm trying to, like, map that into the whole, like, I gave myself a gift, and now I have a different gift, framework. And I'm, I'm struggling to see it. Do you think you can help me with that? Or should we just cut this whole?

[00:59:49] **Ben:** No, no, no. I mean, it's, it's interesting because I don't know. I mean, I'm, I'm just guessing here, but you know, it's, it's like you've given yourself the gift of 15 percent of a rocket and now, an alternate version of the future gives you a different gift of a more efficient rocket. I mean, I'm just, I'm just trying to use the same words, but inserting gift instead of cost.

[01:00:11] **Ben:** I don't know. I, I, this was just a personal strategy that this guy used. Yes.

[01:00:23] **Tim:** right? In the rocket example, you're giving, what's the cost of failure? I saw an interview. I think it was on 60 minutes. And it's probably been a while, but he was talking about when he's first starting SpaceX and, they had like four failed, I believe it was four failed launches and, you know, guy from NASA was like, yeah, NASA, we could not have gotten away with that.

[01:00:42] **Tim:** You know, four, we would not get away with four. And so they're doing a fifth launch and they, you know, pretty much, you know, he's knew that, you know, he's telling the interview, he's like, you know, what happens if the fifth one failed? He said, if the fifth one failed, we would have. Died, company would have died, right?

[01:00:58] **Adam:** That was the last of their money I had to work.

[01:00:59] **Tim:** that was it. And I mean, it was, it was this or nothing and it, and it worked. So it's like he, he gambled it all. So, I mean, but I don't think that's a continuation bias, a plan continuation bias, because they weren't doing the same plan over and over again. They were changing the plan every single

[01:01:15] **Tim:** time. And this one had a, in their estimation, had a higher perceived success rate than what the previous ones did.

[01:01:24] **Adam:** Yeah. I mean, it's, you guys are gonna say the same thing, right? you know, plain continuation bias is, resolved by not falling victim to some cost fallacy. Yeah.

## [01:01:35] Patreon

[01:01:35] **Adam:** Alright, well then, this episode of Working Code is brought to you by Earth. It's pale, and it's blue, and we all share it. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:01:48] **Adam:** Our patrons cover our recording and editing and transcription costs and we could not do this every week without them. Special thanks to our top patrons Monte and Giancarlo.

## [01:01:57] Thanks For Listening!

[01:01:57] **Adam:** I don't know what we're going to talk about on the after show, after show, after show, but I did just finish another book. and I thought it might be, well, it's almost like a, like a pick, right?

[01:02:08] **Adam:** And we don't do that on this podcast, but I wanted to share it. I found it fun and amusing and I'll drop the name in the after show. if you would like to find out what the after show is all about, you can go to patreon.com/workingcodepod. And if you become a patron of the show, then you, somewhat soon can expect some stickers in the mail. so that's going to do it for us this week. We'll catch you next week. And until then,

[01:02:30] **Tim:** Remember, it's not a confirmation bias. Your heart matters.
