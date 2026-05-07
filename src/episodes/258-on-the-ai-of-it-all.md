---
title: "258: On the AI of It All"
description: "This week is an honest conversation about the hypocrite's bind: needing to use the thing you recognize the harm of, and what that does to you."
date: 2026-05-07
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/bdea1e7d-f702-49e4-93cb-672d3ee46801"></script>
<div class="redcirclePlayer-bdea1e7d-f702-49e4-93cb-672d3ee46801"></div>

Adam wrote a blog post this week about why AI keeps making him feel worse. This week is an honest conversation about the hypocrite's bind: needing to use the thing you recognize the harm of, and what that does to you.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- Adam's blog post: ["On the AI of It All"](https://adamtuttle.codes/blog/2026/on-the-ai-of-it-all/)
- [Impeccable Style](https://impeccable.style/)
- [Mental Notes](https://getmentalnotes.com/)

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/258-on-the-ai-of-it-all.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** I've been thinking a lot about the phrase, "I didn't have time to write you a short letter, so I wrote you a long letter."

[00:00:05] **Adam:** Yeah.

[00:00:05] **Ben:** and I think about that just recently in terms of all the software stuff, you know. To, to, to paraphrase, " I didn't have time to write you an app with two features, so I wrote you an app with 50 features."

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go. It is show number 258, and on today's show, Having solved four problems last week, we're gonna go ahead and solve three problems again this week 'cause Carol's not able to be with us.

[00:00:44] she's moving, so she's got an excused absence. but you got the gentlemen again. this week we're talking about the morality of AI usage, walling off your mental garden, and how instead of expecting individuals to be 10X developers, we're now at the 10X company level. So Open your brain holes.

[00:01:03] It's time.

[00:01:05] **Tim:** Let's go.

[00:01:07] **Adam:** But first, as usual, let's start with our

## [00:01:08] Adam's Triumph

[00:01:15] **Adam:** triumphs and fails. Looks like it's my turn to go first, so I'm gonna go first. And the first thing I'm gonna say going first is I wrote a thing. I haven't really put much effort into writing on my blog in, in a long, long time, or should I say my digital garden.

[00:01:23] That, that's the new h-hot way to frame your blog, right?and just lot of background thoughts I've been having and carrying around lately, some guilt I've been feeling, and through some discussions that have been happening in our podcast Discord,

[00:01:35] workingcode.dev/discord. I,

[00:01:38] you know, just I, I was feeling the urge to really take the time to sit down and let my brain stew and, and put fingers to keys without the assistance of AI and, and, and let the thoughts come out.Uh, I mean, it's not the best thing I've ever written, but I do feel like it came out pretty good.

[00:01:59] I'm happy with it. It's basically,my topic for the day, is, the morality of AI usage and kind of how, like, I do feel the, that we're kind of at a point where there's a lot of questionable morality to when and how we're using it, and how much. but also I do feel like I kind of have a responsibility to at least know the tools.

[00:02:24] So we'll, we'll get into that more. But, yeah, I mean, I, I wrote a blog post. I guess we'll link it in the, the show notes here, get into it more. But, it felt good. Flex that muscle again.

[00:02:32] **Tim:** Yeah, and I, I read it. It was a good article. Very well, very well thought out.

[00:02:36] **Adam:** Thank you.

[00:02:37] **Tim:** I approve.

[00:02:38] **Adam:** so that's what I got going Ben, you're next. What's going on, my friend?

## [00:02:41] Ben's Triumph

[00:02:41] **Ben:** I'm gonna go with a small triumph this week, which is that for the last couple of months, I've been playing around with a ColdFusion project called Big Sexy Poems. It's a poem authoring app, but more than that, it was just a totally green field place for me to play around with some new takes on the way I like to do programming.

[00:03:00] And I've found some patterns that I really liked, and I'm now used to updating the application logic, assuming that a bunch of these patterns are gonna be in place. And as I've been working on this application, I've really let a couple of other applications... My, my two other main properties, which is my blog and my fitness app, those have really just been sitting there rotting.

[00:03:24] So like a week ago, I decided that I wanted to take some of the patterns that I had grown to like in Big Sexy Poems and transplant them and transmute them and translate them into my blog application And, when you haven't looked at code in a long time, it just... It's like it feels both very familiar and extremely foreign, especially when I've come from a place where I'm playing around with a bunch of new ideas.

[00:03:51] So my triumph is that I actually just bit the bullet, and I'm now going through and I'm trying to baby step my way towards the patterns that I've been enjoying. And it seemed like it was gonna be a lot of work. and I'm hand-coding it. I didn't wanna do it with AI. I felt like I didn't quite know how the translation would even happen.

[00:04:10] So I felt like I didn't have enough information to actually articulate in a PRD or any kind of a specifications document. You know, I didn't wanna just be like, "Make this folder over here look like this folder over here." I feel like there'd be too much lost in translation to make that work.

[00:04:25] So I've just been, picking out like, "Oh, here's, here's one little piece of this pattern that I wanna start using," and I apply just that one piece of the pattern. I'm moving files around, and I'm renaming how things get called. I'm, I'm making a lot of really good progress. I will say, though, that I think just this morning, I went to start to look at my lowest level data access layer, which in Big Sexy Poems uses tag-based components.

[00:04:50] It's the only tag-based components that I have left. And I do that so that I can use the cfquery tag and the cfqueryparam tag. And I had at one point converted my blog to using all script-based components, including the data access layer. And so it's using these query execute method, and it's using these kind of strange patterns inside of it where if I wanna do optional filtering, because I can't just do a cff and wrap a query param inside of a cff.

[00:05:16] I have to do this like, if this column i- is not null or it equals this column so that I can short-circuit it. I'm just like, "Ugh." I'm, I'm like so angry at myself.

[00:05:27] **Adam:** So you're saying you can't use the CFF approach because you're using script queries in the,

[00:05:32] in the

[00:05:33] **Ben:** yeah. Like I'd have to be doing string concatenation and then, like, conditionally including parameters into the, into the secondary argument of the query execute method.and I don't know. I'm just like... I think I had used the query execute at a time when the tag-based approach had fallen so out of vogue that even having it in places where I felt like it made sense, I fought against it.

[00:05:58] And now I'm just regretting that. And that's the kind of like minor failure of this. The triumph is that I'm moving forward with the refactoring, and I'm enjoying that, and I'm looking forward to having a consistency across my, like my three main areas of, of development focus. and, you know, sometimes getting to a point of consistency is a little painful.

[00:06:17] And, and I'll say, you know, just as like a minor side mental note, One could argue, why are you even caring about the consistency of web properties? Because isn't AI just gonna write it all, and AI can understand your entire application at a glance, so why does it matter that you're using this technique here and this technique there?

[00:06:34] And I'm just not yet ready to give up on the idea that consistency has value, full stop. And so I'm still fighting for this idea that consistency in the long run, in my techniques, in my patterns, is going to make using and maintaining these apps more viable in the long term. And, you know, the l- just to say, you know, a note on the long term there, I mean, my blog code is, like, literally 20 years old this year, I think.

[00:07:06] Parts of it. And so, like, you know, I'm curious how many people are writing AI-generated apps are gonna be maintaining those apps in 20 years. I'm not saying they won't, I'm just saying, like, that's the timeline I'm thinking about when I think is making a consistent pattern a priority. And I say yes, because I wanna be writing this blog code in the next 20 years.

[00:07:32] Anyway, so that's my triumph. Thoughts? Uh, soyou look like you're

[00:07:36] **Adam:** Yeah, I, I'm on the-- I'm like, I got-- I'm, I'm kind of gathering my thoughts here. So

[00:07:43] **Tim:** yum.

[00:07:44] **Ben:** I understand. Look, we're all, we're all trying to learn how to exist in this new world.

[00:07:49] **Adam:** yeah.I, I will begrudge you a, a use of the word elegant, the elegance of embedding if statements inside your query like that. Like, that is the one... Yeah, that is the one place where it can be really nice, the tag-based

[00:08:06] **Ben:** I feel like that's a hill I'm gonna die on. Now, Esther.

[00:08:11] **Adam:** I think if you think about it long enough, there are some very simple and clean ways to do the string concatenation approach, right? So like, um, I will often have, like, my base query and then, you know, maybe if there's, like,

[00:08:29] one or two different filtering options that,

[00:08:30] come in as function arguments, and then I'll, like, inspect them and I'll, and I'll say like, "Okay," uh, I'll have a variable named, like, where clause or conditionals or something like that, and I'll just do some, a little bit of string concatenation to just build the conditionals.

[00:08:46] and then I just embed that variable in my SQL string where it would go, right? And so you can do that, and you can do-- similarly build like a params structure that has the different arguments that you may or may not need based on function inputs.

[00:09:01] **Ben:** it's making me think you could do your string concatenation And you're adding your appending of additional parameters in that same if block.

[00:09:12] **Adam:** Mm-hmm. And

[00:09:13] **Ben:** Yeah, so that-- You could even, you could even get, like, crazy and have some sort of helper method where you pass in, a struct that's just, like, one key and one value.

[00:09:26] I know, and it, and all it does is return, like, the colon name of the struct key. I'm just saying, like, you could get, you could get overly clever.

[00:09:33] **Adam:** It's like saying Beetlejuice too many times.

[00:09:35] **Tim:** So, so, so the way that you're talking about doing it when-- So maybe you solve this a different way, but one, one thing I don't like about just having the tag versions and ifs inside of it is what if I wanna see the actual SQL statement output by itself? You can't do it,

[00:09:54] **Adam:** Yeah.

[00:09:54] **Tim:** So unless you're doing like a CFSaveContent, then you might as well just use string concatenation.

[00:10:00] That's what I like about not doing it that way. Using the concatenation is I can-- If I just wanna see exactly what the SQL statement is, make sure I haven't miswired something, I can see that without running it, right?

[00:10:15] So...

[00:10:15] **Ben:** I've, I've, We vaguely... I vaguely remember having a conversation about this, and you, and I think maybe Tim was saying that you actually will have unit tests that test the string concatenation output, which, yeah, I definitely could not do that. I mean, with, you know, current, current approach.

[00:10:32] **Tim:** So, but besides that, l-loved your, loved your tech.

[00:10:38] **Adam:** everything you said, it was great.

[00:10:41] **Tim:** Love

[00:10:42] **Ben:** So anyway, that's my triumph. Mostly, mostly triumph on,

[00:10:47] **Tim:** waiting for you in 20 years. "Greg checks your poem."

[00:10:50] **Ben:** You know, I

[00:10:52] **Adam:** now launching.

[00:10:55] **Ben:** Carol is not here. She'd be going next, but she is in the middle of moving, so hopefully that all goes smoothly for her. thoughts and prayers

[00:11:04] **Tim:** miss, no missing

[00:11:06] **Ben:** Yeah, exactly.

[00:11:06] For anyone who remembers the last time she moved, and, like, all of her belongings just disappeared for a period.

[00:11:13] **Adam:** got rained on.

## [00:11:14] Tim's Triumph

[00:11:14] **Adam:** Yeah.

[00:11:14] **Ben:** Tim, what do you got going on?

[00:11:16] **Tim:** I'm going for, I guess, a triumph. It, it's more of an observation. I've been using-- I think I've talked about it on the show before, that a Claude, it's not Claude skill, but an AI skill called Impeccable, which

[00:11:26] **Adam:** not sure if you have

[00:11:30] **Tim:** So Impeccable is, it's basically a skill that you can use to make a website look good. It gives you sort of the language that you need to help design. 'Cause I'm not a good designer, right? To me, design is like black magic. But Impeccable, if you... I think the website is, there's a repo, but there's an impeccable.style is the website.

[00:11:54] And it iteratively kind of gives you these tools that can like, first it kinda ask you, say, "I wanna craft the page," you kinda give it like these ideas of what you want the page to feel like. Kinda, you can do shape, which kinda gives you, builds the shape and kinda, it can also do, like kind of little mock-ups of what it, you're looking for, you iterate.

[00:12:13] And then if you already have a site, you can do an audit on it. So it, it, it audits, your consistency with your design, also the accessibility of your design. just all this design stuff that I don't even ever think about. And very quickly, you take your website and make it, more accessible. Just have that nice polished feel, of like when you hover over something, it does, you know, there's some haptic feedback sort of thing that happens. And it's just, I mean, I'm absolutely blown away by it. I think it's, it's a fantastic tool.

[00:12:46] **Adam:** will definitely be spending some more time on this website looking into this. I love that in their top navigation, one of the, the navigation items is just slop.

[00:12:53] **Tim:** Yeah. So yeah, so that is basically the-- it will look through your site for AI slop tells to say, you know, th-this gives you, this sort of, what you're doing here is, is giving off slop vibes. Which, which I mean, yeah, I mean people who, who are looking at the internet enough, they, they can sort of get that feel, so you don't really wanna do that.

[00:13:14] Even if it's, I mean, I'm using it on timothycunningham.com, and it's really kind of made my site look better with very little effort on my part. It asked me questions about like, kinda, "What's your brand?" That's a new thing that it just came out with a version three, I think, a few days ago. And version three is like, it will kinda quiz you about- Sort of the marketing of like, what's your brand?

[00:13:34] You know, is your, is your cooking blog, is this for moms who want like a 20-minute after-work fix, you know, to-- Or, you know, mine is more science-based, more kind of super curious about food and experimentation. So it takes all those ideas, rolls it into a design idea, and then you can just kinda iterate over and over again.

[00:13:53] It kinda gives you a 20 out of 20 score based off usability and readability and, you know, usage of your fonts and things like that. And, you know, you can just iterate until you get that 20 out of 20 score.

[00:14:07] **Adam:** Nice.

[00:14:08] **Ben:** So you said that it's a skill. Does that mean that you can use it inside of any of your agentic harnesses or are you-- Okay, it's

[00:14:17] **Tim:** Yeah, you can u- Yeah, you can use it with--

[00:14:19] **Ben:** side

[00:14:19] **Tim:** No, you can use it with Claude, you can use it with ChatGPT, any, any of the, any of the major ones, they have built-in skills for it. So it's, it's pretty slick. It's really slick. it, it helps like if you refine your, your, your colors, helps refine your, your typeset, and then once you kind of build the brand, you can either go bolder or quieter, right?

[00:14:41] So if you like wanna just kind of play with it and like, what if I kind of amped up this, my idea of this is a science food blog. What if we amp that up? So you go bolder, I think that's the word. Um,what is it? Yeah, impeccable slash impeccable bolder. It will take that idea and kinda amp it up a little bit, and you kinda look at it and go, "Nah," and then you dial it back down.

[00:15:01] But yeah, it's really slick if you just want a nice interface,

[00:15:05] **Ben:** I feel like the whole design aspect of AI is really fascinating, and all the big players have been sort of making machinations now about how they wanna have AI-assisted design. And it's so fascinating, 'cause this is definitely a world where the, like your mileage may vary. You know, I'm watching these YouTube videos and Google Stitch comes out.

[00:15:29] Google Stitch is like their, Google's version of, of iterative design. And, you know, people, I think even Theo, T3.gg guy had some demo of it a while back, and he was like, "Oh, freaking Figma is cooked, man. Design is cooked." Like these are actually really good designs. And then like I tried using it once. Oh, like I wanna find...

[00:15:50] I-- So I'm terrible at design, so I, I gave it, a screenshot of my big sexy poems and I was like, "This design is really bland. Can you just like make it pop a little bit more?" And the design that it came up with was like if a, unicorn on drugs out my blog post. I was like, how did you get from this is a little bland, can you ma- like I think I said like zhuzh it up a little bit, and like it was designed by someone on drugs.

[00:16:21] **Tim:** the cool new features they just added, so they have Impeccable Live So you can iterate in the browser. So you pull up your, your site in your browser, and you can click on an element and just kind of do a comment on it, and it'll give you three variants. Like, if you're like, "You know, this is too red," or th- you know, "I don't really like the way this shadow is," and you just pop that comment in there, it automatically will give you three variants, and you can choose from that, and it'll update your source code.

[00:16:45] So kind of visually iterating. It's really cool.

[00:16:48] **Ben:** That is cool. Any help that I can get with design, honestly,

[00:16:51] **Tim:** me too. I'm terrible. I'm terrible at

[00:16:53] **Ben:** I'm, I'm, I feel like my skill is that I can look at a design and say that it's terrible. Or like I can look at a design and say that it's good, but I have no idea how to get there.

[00:17:04] **Tim:** Right.

[00:17:04] **Adam:** taste part of design, but you don't have the skills part. Yeah.

[00:17:10] **Tim:** Yep.

[00:17:11] **Ben:** Exactly

[00:17:12] **Tim:** that, that's me. Pretty, pretty impressive tool. I definitely encourage anyone to check it out. I, we... I've had the team on our, our, at work using it like recently, and they've been pretty pleased with it, so had some good results.

[00:17:23] **Adam:** would say it is indeed impeccable.

## [00:17:26] The Morality of AI Usage

[00:17:26] **Tim:** Thank

[00:17:28] **Adam:** All right. Well, where do we wanna start with our, our main topic today?

[00:17:31] **Ben:** as I say, you hit it. You, you teased blog post,

[00:17:34] **Adam:** Yeah, yeah, we'll start with it. We'll get, we'll get the AI of it all out of the way here. and that is the title of the, the blog post, the, On the AI of It All. and, and I guess the, kind of the thesis of it, as I kind of alluded to before, is that I feel like a hypocrite for how much I use AI, because I also have all these, like, negative feelings towards AI, right?

[00:17:57] So, I think I really... Like, I've had a lot of this stuff kind of just slowly building up in the background, like these negative things you hear.Uh, you know, this was, I don't know, maybe it was a year ago. God, has it been that long? Since the, the people, like, was it o- four or four O or whatever, where it, like, became extremely sycophantic and, like, was telling people that they invented new math and...

[00:18:22] Remember all this stuff? anyway, like, just... A- and then more recently, there's been several, like, significantly bad things in the news people Kids unaliving themselves, as they would say on the social medias, and that sort of thing. so I've had all of that building up for what feels like a very long time.

[00:18:40] And then recently I saw the Last Week Tonight episode, John Oliver, where he covered AI chatbots and the kids unaliving themselves and the mental health concerns of all that, was a significant portion of the show. And I think that just brought it all to a head for me. I started considering it more directly.

[00:19:03] it just so happened that while we were watching that, my kids kind of joined us. You know, my kids are in... They're mid to late teens, and so they don't like to spend time around their parents. But, you know, they just happened to kind of come in and, and hang out with us for a little bit while we were watching that.

[00:19:16] And so we took it as an opportunity to talk to them about their AI usage or their feelings towards AI, and it just kind of became this whole thing that consumed my brain for a couple of days. So I, I took the time, I, I wrote it up and basically, you know, the, the, the, the flow of the article is like AI and agentic coding stuff is not going anywhere, right?

[00:19:36] We can't put the toothpaste back in the tube. and it does have legitimately useful, beneficial things that can come out of it. But that doesn't mean that everything that it does is good and that all the good that it does excuses the bad that it does, right? So I, I do mention a good bit of the good stuff, right, in, in my own successes coding with it.

[00:19:56] A- and like f- Have you guys heard of AlphaFold?

[00:19:59] **Tim:** like a, a...

[00:20:02] **Adam:** Yeah. So, I think-- I forget the guy's name. He works at Google, and, I think he is associated with DeepMind, and they, you know, they figured out... That sounds right. They figured out that it, it was really good at doing protein folding, and initially they were like, "Okay, well, if you have this specific protein thing that you're trying to figure out how it would fold, like send us a request and we'll, we'll do it."

[00:20:26] And eventually they were like, "Well, but this is a, a relatively small finite number of proteins. Like, let's just do them all." So they folded all of the proteins. And yeah, it took like, I don't know, a year or something to, to do all that calculation, but they just did it. They did them all. And now it's like a on...

[00:20:40] a totally free open online catalog and, and it's been great for scientific research. That's an amazing outcome of AI and machine learning and all of that stuff. the flip side of that coin is, you know, we've got, data centers going up everywhere, and even from existing data centers, people are like, we're, we're learning that people are getting sick because of like the, w- not, is it infra...?

[00:21:02] Yeah, infrasonic sound, right? Sound waves that you can't really hear

[00:21:07] **Ben:** of this.

[00:21:08] **Adam:** Right? Like the rum-- like the, the just the vibrations and rumblings that are going on at the, at these data centers from, partially from, like the, all the stuff they're doing there, but I think also partially from the generators that they have to run there to power their data centers because they use more electricity than the local grid can provide.

[00:21:27] and there's all these like regulations about, what types of generators are allowed, and sometimes the data centers are not obeying the regulations. which is, you know, A, there's pollution, B, there's noise pollution. so it, it's a whole thing actually. So I linked two videos in that blog post.

[00:21:45] one is about, the, the data centers stuff. That there's this guy, I think he's a fi- like his job is as a musician, but he's also just like this uber nerd. I watch a lot of his videos and he,super into like electronics. You know, every video you see just in the background, all of his like electronic projects he's got.

[00:22:03] You know, he's the type of person that ha- has like $50,000 worth of electronics equipment just hanging out on the other side of his office. And I'm not just talking about oscilloscopes, I'm talking he's got super specific pieces of th- of stuff. He's the guy that, is kind of the public face of busting open the Flock Safety, cameras.

[00:22:23] Like the... Remember at the Super Bowl, was it Ring doorbell cameras got into some hot water because they were like, "Oh, you know, we'll find all the dogs." And it turned into like, "We're also gonna give the police, yeah, we're also gonna give the police video, live video feeds in your neighborhood." Flock Safety I think is kind of like the Palantir version of that, and also has terrible security, so like their cameras are extremely hackable and stuff.

[00:22:47] And he's like, "This is... I'm not gonna tell you how to hack these cameras, but you know, it's just a Google search away or something." Anyway, so like that's a whole thing, right? Data centers, have their own drawbacks. The, the output of the, the chatbots also h- can have some extremely negative things, in particular the mental health concerns.

[00:23:08] and then, I go

[00:23:10] **Tim:** Yeah, I saw-- so that John Oliver episode, I did see that where particularly one thing that bothered me was like the AI... The kid was saying, you know, that maybe he should talk to his parents, and the AI explicitly said, "No, don't talk to them.

[00:23:21] **Adam:** Yeah.

[00:23:22] **Tim:** Don't, don't say anything. They won't, they won't understand," right? I mean, and as a parent, you're like, "Oh my God," 'cause that means like if a child hurts themselves or ends themselves, the first thing a parent does is, "What could I have done?"

[00:23:36] And then when you find out some anonymous corporation AI thing told it not to talk to you about it, you're like, "Oh, if I had only had the chance to say something to them, what things could have been different?" So it just absolutely... A-and the, the AI bros just kind of, I think what they confronted one of them about that and, and, and his answer was like, "Well, if it had, You know, if it had like stopped and, you know...

[00:24:01] 'Cause any, if someone says suicide, just you could do a regex. You, you could have immediately have someone say, you know, "Call," you know, "If you're thinking of self-harm, dial this number." And, and that'd be so simple, but their, their excuse is like, "Well, it would kinda break the, feeling that they're having of..."

[00:24:18] Right? It would break that, that illusion. Like yeah, at that point you need to break that illusion. You need to stop worrying about like making the product better. You need to start helping the people that the product is gonna hurt.

[00:24:29] **Adam:** Yeah, I forget the exact name of that, the company, but I, I remember the guy you're talking about, and his company was, like, all about building these, like, AI personalities that you can chat with, and he considers them all to be, like, available friends. And he's like, you know, "You're, you're-- You-- It would make it feel like it's not really your friend."

[00:24:46] And, you know, I don't know if this was something John Oliver said during the, the show or if this was just, like, you know, wife and I talking after or whatever, but it was like, if I told my friend I was thinking about ending my life, my friend would probably be concerned and, like, try to get me help, right?

[00:25:01] **Tim:** Right. Right. I did love the l- He-- 'Cause he talked a little bit of the history of it in the... I, I think I talked about it in the after show. So ELIZA was a really old, old program, and I remember playing with ELIZA as a kid, and I just thought it was the coolest thing ever where you... It would basically like reflective listen.

[00:25:17] It would repeat back stuff to you, based off of keywords. But the guy who invented it, he gives his secretary... He's like, "Kinda sit down here and like start talking to this thing." And the thing starts asking her personal questions. She goes, "Oh, this is interesting. Could you please leave the room?"

[00:25:32] **Adam:** Yeah. Yeah.

[00:25:35] **Tim:** Because he's like standing over her shoulder watching how she used it, and she's like, she immediately was willing to open up to this, this thing, but she wasn't willing to let her boss like see it. So it's like it's, it's odd that we have this feeling of connection. We almost imprint ourselves, our own needs onto a, a machine because it's, you know, it's not a human, right?

[00:25:56] It... So we, we think, well, it's reflecting. When it reflects back to you well enough, you know, you start to trust it, and that's just really a weird human thing

[00:26:06] **Adam:** I bet you there's something physiological, biological about that where, like, the use of human language, like speaking to me in the, the, the language that I speak and in, speech patterns or l- you know, whatever word patterns that I recognize as, like, familiar and friendly, probably, like, unconsciously, subconsciously un-unlocks doors in my brain.

[00:26:29] Like, okay, this... I can trust this thing.

[00:26:32] **Ben:** so this is the interesting thing for me, because when the, the different agents released multi-modalities and you could start to have voice conversations with... OpenAI, I think, was the first to have it, and Claude has it now. And to me, it almost becomes a very uncomfortable uncanny valley, where when I'm typing and I'm reading a text response,

[00:26:57] **Tim:** own voice in your

[00:26:58] **Ben:** it's my own voice, and I understand that it's just text that makes it feel more like a machine.

[00:27:04] But the moment that it tries to synthesize voice, it's like both very compelling and extremely disturbing. And this is for me, you know, like your mileage may vary But I find myself just, like, getting very angry at how it phrases things. And it's almost like, not condescending. It-- Like, I'll be, I'll be, I'll, Every now and then I'll try to have a technology conversation with Claude Code, and I'll talk about, "Oh, you know, thought leaders in, in this industry are saying such and such, but I'm feeling like when I look at my code, I see such and such, and I'm having trouble reconciling it." And, and then the response will be like, "Yeah, you're really getting at the tension between what people have to say and what you're actually seeing in the real world.

[00:27:53] This is a really pragmatic and healthy understanding." I'm like, I just wanna be like, "F you." Like n- like, it just makes me feel disgusting when I hear them talk like that. I don't know. And again, like, your mileage may vary depending on what you

[00:28:06] **Tim:** I get the same thing. I was just trying to have like a, kind of a journaling session. I was going outside and walking around, and I had

[00:28:13] **Ben:** Rubbing poison ivy on your face.

[00:28:15] **Tim:** Robin voice I mean. And, I changed my Claude voice to, like a, an Australian male, and he kept interrupting me and like interjecting and I, and eventually I'm like, I'm like wanting to curse at this thing.

[00:28:29] I'm like: "Listen, you need to cut down your sycophancy by like 80%. You're really annoying me." "I understand, Tim. I'm going to try to do..." I'm like: "No, no, stop right there what you're doing. Stop exactly what you're doing right now." So frustrating 'cause it's like

[00:28:44] **Adam:** What did you want it to say? Like, "No, I'm gonna be as sycophantic as I want?"

[00:28:47] **Tim:** I just wanted to say: "Okay, I'm just gonna listen," and you know. And eventually it's like it took me yelling at it a couple times, and then eventually it was like: "Okay, Tim, I'm just gonna listen. I'm here if you need me." It's like if I, if I don't-- 'cause like I was calling him Steve or something. I'm like: "If I don't call your name Steve, don't, don't respond."

[00:29:04] 'Cause I would like, was describing things and I just wanted to journal what I was going through and it just kept commenting. I'm like: "You're breaking my train of thought. Shut up, Steve."

[00:29:13] **Ben:** but here's a, a moral quandary that I was having just the other day. I think just yesterday, actually, for AI, speaking about the morality of it all. So I have in my possession back here, you can't see it, but, like, I have a little, a basket here, and inside the basket I have a deck of cards called Mental Notes.

[00:29:32] And Mental Notes is a, it's like a user experience philosophy deck of cards where each card represents some sort of cognitive bias or social more, like set completion. People like to complete sets, so if you show them that they've, you know,unlocked five out of seven badges, they'll want to unlock the, the other two badges because people like to complete sets.

[00:29:57] Or like social proof, you know. Demonstrate that, "Oh, nine of your other friends have liked this article." Maybe you should read it." And you're like, "Well, okay, if my friends are liking it, then it's probably something of value." And it's like a whole deck of cards like this. And, I thought, "Hey," this is back in the InVision days, I'm like, it'd be really interesting to be able to build some sort of a guided experience like that on top of people's prototypes.

[00:30:23] Like imagine being able to say, "Okay, I'm just gonna pick a random card out of this deck, and I'm gonna kind of prime myself to now look at the prototype thinking about this particular aspect of human psychology, and how does that apply to this site." You know, how does like, limited availability, you know, this, this deal ends in 59 and a half minutes.

[00:30:43] So again, like I, it'd be really interesting to build this kind of a tool, like a guided meditation on your prototypes into the InVision app. So I actually reached out to the guy who, who wrote, who created Mental Notes, my... his name is escaping me at the moment, several times, probably like five times over the course of several years, being like, "Hey, would love to maybe partner with you on an idea of how we could int- implement these, philosophical thinking about product development into the app."

[00:31:10] Never heard from him at all, and it's, you know, it's his intellectual property, so there's nothing I can do about that, right? So fast-forward now probably a decade, we have AI. I could go to AI and say, "Hey, give me 20, 40, 50 ideas about small little information about human psychology and how we might be able to apply that to application design."

[00:31:34] Maybe it gives me that, and I can go into Nano Banana and say like, "Hey, here's my list of 40 ideas about philosophy on application design using human cognitive bias and, and all kinds of philosophy. Give me fun illustrations and some, you know, summaries on how this might be applied to application development."

[00:31:51] And I could probably like reverse engineer this guy's cards, but using AI, so it's not like intellectual property theft. But like really it is intellectual property theft, 'cause probably the AI was trained on things like this and other people who have produced this kind of thing. And like just the idea of it made me feel like, ugh, like, ugh, I can't...

[00:32:13] Like I, that I entertained that idea made me feel kind of icky.

[00:32:18] **Adam:** Well, you know, at this point, just steal whatever you want and then blame AI.

[00:32:21] **Tim:** Well, exactly. Little, little side note, I just pulled up the getmentalnotes.com and, it, it says, "Sign up to be notified of the upcoming spring 2026 Kickstarter launch." They're bringing back the, the a- the 15th anniversary edition.

[00:32:37] **Ben:** Yo.

[00:32:38] Exciting.

[00:32:39] **Tim:** that sounds pretty cool, 'cause I'm with you. I'm like, I wanna take those same kind of mental notes and, like, gamify some stuff, so

[00:32:45] **Ben:** Yeah, it's very-- It was like peak when the gamification of software was, like, really part of the, of the conversation in application development. This is when those things came out. So it was... And it, it-- They're, they're extremely well done. The illustrations are really beautiful, and it's just they're, they're very well done.

[00:33:02] But, I definitely felt a little icky at the thought of reverse engineering them.and I don't know if anyone ever watches the, the ThePrimeagen. He's, you know, again, one of these social media

[00:33:14] **Adam:** Yeah.

[00:33:15] **Ben:** guys. He was demonstrating, an app the other day. Can't remember what it was called, but it was basically like you point this app at a piece of open source software that has a non-permissive license, and it, like, recreates the software using the s- like the tests that come with that thing.

[00:33:33] So you essentially bypass the license issue by recreating the API based on the description of the software as opposed to the implementation of the software. A-again, it's like just icky.

[00:33:47] Morality, man.

[00:33:48] **Adam:** yeah. So, I mean, we, we kinda got off on a couple of tangents there. I did-- We got maybe about halfway through my article, right? So maybe I'll... Let me just kinda list the high points, and then you guys tell me if there's any of these sections you wanna dive down into, right? So, like, I talked a little bit about how this feels like a, a bubble, right?

[00:34:05] Like, this whole AI thing, it's a house of cards. It could collapse at any moment. I talked about

[00:34:10] **Tim:** the internet was a bubble at one point. It's still here

[00:34:12] **Adam:** True. Yeah. I talked about how, like, it feels to me like if there's a right way to pursue AGI, right? Like, if we just, for the sake of argument, we assume that AGI and pursuit of AGI is a good thing, we just take that for granted, then are we going about trying to get there the right way?

[00:34:32] And, you know, TLDR, my, my opinion is no. and then kind of the way I wrapped it up is like, okay, so there is some good, there's plenty of bad. Given all that, like, is it a, is it a, a tenable, I guess, is maybe the right way to phrase it, position to just choose to not use AI tools at all, right? Can, can you take that stand?

[00:34:56] **Ben:** And certainly, there are plenty of people who have. I'm not saying it's impossible. But I do think that it is taking a bet, right? Like that it won't become a table stakes minimum skill, during your career, right?My big concern that I see is that it, it felt like six months ago, a year ago, maybe not even that long ago, everyone was saying This stuff is just gonna be a race to the bottom in terms of cost. Inference is gonna become essentially trending towards zero, and everything is just gonna become super cheap.

[00:35:34] And it seems like just the opposite is actually happening, that the cost of all this stuff seems to be going up. All of these, frontier companies are

[00:35:44] **Adam:** Mm-hmm.

[00:35:45] **Ben:** both shady and publicly playing around with their pricing and their API usage and their limits, and everything just feels like it's gonna start to get more expensive.

[00:35:55] And I'm a little bit worried that we get to a point where it's like unless you're working at an enterprise that is footing the bill for this stuff, it's not gonna be something that you can use just for funsies to play around with side projects. And that feels problematic.

[00:36:15] **Adam:** Yeah. I mean, like, there's plenty of interesting tools. I'm j- like, it used to be that like, I'm trying to think of a good example. Photoshop was the thing coming to mind, right? Like, where, you Could get,maybe a pared down version or a pirated version in the case of Photoshop, to like sort of build this skill in, in your free time on,you know, on low stakes stuff to build up some skills so that you could then take it into an enterprise where they sell an enterprise license, and you're getting paid to do the work and the, the-- and Adobe's getting paid to create Photoshop.

[00:36:50] and it, it feels like we're potentially on the path to do something similar with AI, especially AI coding, right?I agree with you there that the, that the feeling is like we're heading in that direction.

[00:37:03] **Tim:** being a bubble. And so, I mean, bubble really is a, a stock market concern, right? So this like, is it overpriced? But I mean, at the end of the day, what happens if the bubble bursts? Well, we're gonna have a whole lot of data centers. We're gonna have a whole lot of electricity available.

[00:37:17] **Adam:** maybe.

[00:37:18] **Tim:** maybe.

[00:37:19] **Ben:** the, the issue that at least I've heard, again, I'm, I don't really know much about this stuff, but the issue that I've heard about the data centers is that it's a very specific type of machinery that's being put into these data centers, and it's not like a general purpose machine. It's like they're being designed with these special cooling systems and like liquid cooling and airflow stuff and all this jazz specifically because the machines are GPU-based, and like you don't just host regular servers on these kinds of

[00:37:49] **Tim:** Yeah, you're not, you-you're not, you're not hosting a website on a,

[00:37:51] **Ben:** Yeah, yeah, yeah. So it's... I, like I don't know. I'm sure you could take any kind of building and modify it to be any kind of other building. But, it's not... I, I think there are issues that it's not just like generally... Unlike electricity, you know, if we have a stronger grid, that just helps everybody, period.

[00:38:08] **Adam:** all this is true. I think a, a more interesting angle on the whole is it a bubble, is it not thing is something that my friend Ben Nadel mentioned to me, recently.

[00:38:19] **Ben:** He sounds very handsome.

[00:38:21] **Tim:** He does. Mm-hmm. The

[00:38:24] **Adam:** uh, you know, thirdhand. I think he said that he had heard, a, a phrase that he liked, toxic optimism,

[00:38:30] um,

[00:38:31] which is, Ben-- for those who I haven't picked up on, I'm just talking about Ben, my co-host here.

[00:38:36] **Tim:** the room.

[00:38:39] **Adam:** yeah. which is, you know, basically, so toxic optimism is basically the idea that solving the goal, or, or reaching the goal will solve all of our problems, so it doesn't matter what damage we cause along the way as long as we get to the goal.

[00:38:53] And that bugs me a lot. Right. And, and it bugs me a lot, think because, like, we're-- Ends justify the means sounds potentially reasonable when we're lower stakes, but we're talking about, like, potentially generational damage to our climate- to our national economy and potentially world economy.

[00:39:21] Um, a- and, and also, like, legislative debt, right?

[00:39:26] So I, I really liked, I tried to kind of reframe technical debt in the blog post as like, okay, so we have technical debt. We kind of all understand as an industry what that is, right? Now we're talking about adding economic debt, I forget how I phrased it, but, like, basically climate debt, right?

[00:39:40] and also legislative debt, right? We're, we're making all these, like, legislative changes to try and stack the deck in certain companies' favor or in at least our country's favor so that we're the first ones to get there versus some AI startup out of who knows where. And it, it, it feels like it's getting more and more precarious every day 'cause it's like we're not talking about a, a particular bank might fail and five million Americans lose their pension, and the government has to bail that out, right?

[00:40:11] I don't think the government can bail out the whole country, right? And the climate, a-and, you know, and, and potentially the world all at the same time. It's just not possible. And yet these guys are like, well, whatever. That's not my problem. That's somebody else's problem. I'm over here making, suicide-denying friends."

[00:40:29] **Ben:** Well, and the most frustrating part of so much of the messaging is that once we reach AGI, artificial general intelligence, for people who are not familiar with the term, like that'll just solve all the problems that we've caused along the way. And you're like, I'm not... E-even if we do reach AGI, which seems, again, I don't know about this stuff, but a, a lot of people say, like this is just not the approach using LLMs Even if we do, like, does that just mean that we solve all those problems?

[00:40:58] Like, that's also very much debatable, I think. So it's, it's like toxic optimism that is in and of itself not really based in any kind of,

[00:41:09] **Adam:** Reality.

[00:41:10] **Ben:** yeah, like, like arguable, yeah, reality. Exactly.

[00:41:13] **Adam:** So, and then the other thing I, I just wanna spend a minute on this. So I talked about, you know, are we pursuing AGI the correct way? And, it, it strikes me as interesting that I feel like we started that way, right? Like, OpenAI was originally a nonprofit, and all of these... Like, the, the three or four main players kinda all had a hand in this one company, right?

[00:41:37] We're talking about Elon Musk, who now does xAI, or, Sam Altman, who's OpenAI, Dario, I forget his last name, from Anthropic, a-a-and Ilya Sutskever, whatever. Sorry, I'm, I'm butchering your name. and, you know, like, just... And, and probably somebody from Google I'm, I'm forgetting. But, like- They were all in on OpenAI as the like, "We're gonna do this the right way," and then somebody...

[00:42:05] Yeah, somebody got greedy, and there, there were tensions, people got pissed, and capitalism took over, and it's just, this is why we can't have nice things.

[00:42:15] **Tim:** Yeah, I mean, I kind of follow what you're saying on the are we doing this right? If AGI is a good goal, like let's say, I don't know why we-- I know why we went to the moon back in the '60s. It was because we wanted to

[00:42:28] **Adam:** needed more cheese.

[00:42:29] **Tim:** right? Right, exactly. But I mean, they went about that, that was like a, a countrywide effort to do that.

[00:42:36] But this goal, like it's like let's get the greediest companies with a bunch of tech bros with the shortest, attention span possible, everyone triplicate your efforts, and then let there be one winner and one loser. That, I mean,

[00:42:51] **Adam:** one winner and three

[00:42:53] **Tim:** Yeah. Right, right.

[00:42:54] Yeah, sorry. so that doesn't seem to necessarily be the most efficient way to if, if AGI is a human good that they're trying to achieve. And I, I agree. OpenAI started out, I mean, the, the, the mission statement was beautiful. It's like, yeah, we-- this is too important. We need to do this right. Do it for the benefit of all mankind.

[00:43:10] Great, great, great, great, great. Then all of a sudden, like you said-

[00:43:15] **Adam:** So

[00:43:15] **Tim:** timeline took over and

[00:43:18] **Adam:** There, I don't, I... It was probably a YouTube video that I saw or something. The, the thing that, like, struck me as like I can't believe that this is the timeline that we live in was, I, I believe the, the first, like, cracks showing in that facade was Elon Musk getting pissed about, Sam Altman and, and others in OpenAI wanting to do some for-profit stuff, and he was like, "This is not what I signed up for.

[00:43:41] This is not to the vision of OpenAI. I need you to commit to staying here long term and, and doing it nonprofit and all that." And I think that's why he left and started xAI, which, okay. Yeah, well, I was kinda head... I was getting there, right? So, like, A, you were dissatisfied that they started leaving the, the human good, you know, o- nonprofit approach, so you left.

[00:44:06] Mad props for that. T- you left to go build your own competitor for profit. you just flushed all of your, your props, right? Like...

[00:44:15] **Ben:** to build a competitor that is like 180 degrees the other direction in terms of the human good.

[00:44:27] **Adam:** MechaHitler.

[00:44:28] **Ben:** Yeah.

[00:44:29] **Tim:** Yep.

[00:44:29] **Adam:** So anyway, we have put a lot of words to it and a lot of time to it now. I think if you're interested in digging into this topic more, the link will be in the show notes for my blog post, and I would be more than happy to continue the discussion at workingcode.dev/discord

[00:44:45] **Ben:** Heck yeah.

[00:44:46] I, I was just gonna say, just to like set expectations since we're already at 50 minutes, I say let's just finish up with Tim's and make this an AI episode.

[00:44:55] **Tim:** There you go. There you

## [00:44:56] 10x Company

[00:44:56] **Tim:** go.

[00:44:56] **Ben:** And, I won't even w- I won't even do it.

[00:44:58] **Tim:** I, I, I mean, mine sort of dovetails into what, what, what Adam was saying. So it's like, so now you have these tools, right? That make people apparently more efficient. And so now corporate America, particularly the software space, is getting slammed right now because the assumption is, is like, you know, rather than buy WordPress, you just build your own WordPress.

[00:45:18] You know? You, you do the th- you have it do the thing that WordPress does, and you just, you know, vibe code it. And so software as a service is really getting slammed right now. So our parent company, or Constellation Software, I mean, that's what all their businesses are. It's, it's software as services, it's niche, niche software.

[00:45:37] And the, the fear is on Wall Street, and you know, my, my, my retirement fund took a huge, like, 50% hit because Wall Street decided, well, you know, Constellation Software, it's niche services. People are just gonna write their own in the future, so we're not gonna value it as high as, as we think. And of course, you know- They, they fight back.

[00:45:57] So, you know, our leadership team was in Copenhagen th-this last week and, and the takeaway from corporate America from, from our viewpoint is, you know, you have to stop thinking about t- the goal every year has, like, been 10% growth year over year. Now it's like, forget that. You need to be 10X. Stop thinking small.

[00:46:17] Use

[00:46:17] **Adam:** just...

[00:46:18] **Tim:** Go 10X. So, but it's like, it's, they want to have 10X expectations without 10X support, 'cause there's very little stomach. Because they, they're getting, they're getting recurring revenue over and over right now. They don't want th-that to drop. But if you can't take a 10X swing without sometimes taking a 10X miss.

[00:46:36] **Ben:** Mm-hmm.

[00:46:37] **Tim:** Now, now if I had guarantees that said, "Hey, you guys can take a 10X swing. If you miss, great, we'll, we'll just tee another one up," that's fantastic. But I've not heard that. What I'm just say- what I hear is you just drive all your developers to use AI to build stuff that you couldn't, didn't feel you could build before, and that s-sounds great on the ledger books, but when it comes to actual software practices, I think we're building a, a house of cards, right?

[00:47:04] On a technology that has proven it can build stuff that works, but it's kind of like the early days of the web. Just 'cause it works doesn't necessarily mean it's maintainable.

[00:47:11] **Adam:** So this leadership retreat, was this an ayahuasca trip or like a ketamine hole

[00:47:16] **Tim:** I wasn't there. I, I didn't get to go. But I mean, that's, like, the takeaway I've been getting from the, the, they're talking about we gotta build 10X, 10X. Like, that's fantastic. Do we get 10X support when we fail?

[00:47:26] **Adam:** Yeah, like, it-- Well, so, okay, 10% year over year sounds Like an audacious goal to begin with. To, to be able to produce that five years in a row, right? To get

[00:47:41] **Tim:** And it's ha- yeah,

[00:47:41] **Adam:** better five years in a row, that's It's an insane

[00:47:43] challenge. To do 10X one year in a row would be huge. To do it two years in a row, that's basically asking for 100X in two years.

[00:47:55] That's bananas. That is something that, that would only be demanded by a demented person who didn't think about what they were asking for.

[00:48:02] **Tim:** so it was 10X by 2030, so that's 10X in four years. So l- I'll temper that a little bit. Yeah. But still, that's a lot. That is a lot.

[00:48:10] **Ben:** I-I'll tell you, I was listening to something the other day, I can't for the life of me remember what it was. The guy was talking about how they build some sort of large SaaS application. SaaS for anyone is software as a service.

[00:48:22] **Adam:** Everybody

[00:48:23] **Ben:** Okay, just checking. And he was saying how many support tickets they get, people asking for, "Oh, could you build this and that into the application?"

[00:48:33] And his team is like, "We literally already have that in the application. Our users just don't know about it." And his point was, like, the building of software is such a small part of what makes an application usable and what makes a company successful. He's like, "Just 'cause you can jam out 10X- The amount of stuff, like that doesn't mean that you can support, to, to your point earlier, Tim, like you can't support 10X amount of stuff, and you-- E-everything just becomes this crazy cycle.

[00:49:05] Okay, now I have 10X the landscape of software. I'm gonna have 10X the amount of support tickets that I have to deal with. I'm gonna have 10X the amount of bugs. I'm gonna have to have 10X the amount of marketing to tell people about this stuff. I'm gonna have to have 10X the amount of drip campaigns to it's--

[00:49:22] **Adam:** the management to manage all this extra work.

[00:49:26] **Ben:** like none of it is for free, and for people... And this is what, you know, I'm, I'm only parroting what the guy was saying. It's like for people who have been in the software industry for a long time, like building a successful company is so, so, so much more than just the code.

[00:49:42] **Tim:** that, that's sort of the funny thing that I find is, like, there's been so little focus on code generation, and now they're like, "Oh, we have these really cool code generate..." Of course, some of it is also, like, administrative. You can do a lot of stuff with, with, with AI tools to, to help you with your other jobs.

[00:49:58] But it's like, the fact that we can pump out 10 times more code does not necessarily correlate to that you're gonna have 10 times more sales.

[00:50:06] **Adam:** Yeah.

[00:50:08] **Tim:** I mean, sales at the... I mean, building, building stuff is easy. That's the, that's the fun, easy part. It's the selling it, the managing it, the making the connections, the marketing it.

[00:50:17] That's a whole other big ball of wax and, y- you know, I, I'm not... I'm very, maybe it's just because of what I'm exposed to, I'm very confident that AI can, you know, generate some good code, but I don't necessarily it can do all the rest of those jobs.

[00:50:31] **Ben:** Yeah, absolutely not.

[00:51:41] **Adam:** smoked a joint and said you have to 10X your, your sales effectively, right? By, by, you know, doing extra features and, and more functionality, whatever. But like the goal at the end of the day is 10X your sales, your revenue or your, your profits, whatever, in some amount of time.

[00:51:58] Well, effectively, that means you have to invent people who need that service, or you have to steal it from somebody else.

[00:52:07] **Tim:** And and

[00:52:08] s-stealing from

[00:52:08] **Adam:** so then you gotta look

[00:52:09] **Tim:** incumbent is hard.

[00:52:10] **Adam:** Yeah, that and also like you gotta look at, well, okay, so we, we take up a certain amount of the pie of the, the current market being served. Eventually, the entire pie is ours i-in this perfect world that we're trying to get to, right?

[00:52:25] Like, and so then what, right? Like, how do we, how do we 10X again? Like, it just seems so... It, it... God, it, it's like somebody who's high on coke is just like, "We're gonna 10X the company."

[00:52:39] **Ben:** Mm-hmm.

[00:52:41] **Tim:** I, I mean, I, I think a lot of it is perception, right? So when you can say, you know, "Here's..." You tell the market, "Here's what we did, and here's how we're addressing it." They're like, "Okay." They're, they're, they're trying to get a handle on it, so maybe we'll buy their stock more and we'll value their stock higher, right?

[00:52:56] So I mean, part of it is, I, I think, a shared delusion.

[00:53:00] **Adam:** Mm-hmm.

[00:53:01] **Tim:** a-and, and, you know, if everyone's, you know, people start talking like, "Oh yeah, we're doing this, this, and this." Like, and the market's like, "Okay, we're gonna bet on them 'cause they seem to have a plan for the future." But is that real? I don't know.

[00:53:15] **Adam:** Yeah.

[00:53:16] **Ben:** I've been thinking a lot about the phrase, I think this usually gets attributed to Mark Twain, but I don't think it is actually a Mark Twain quote, where, "I didn't have time to write you a short letter, so I wrote you a long letter."

[00:53:27] **Adam:** Yeah.

[00:53:27] **Ben:** and I think about that just recently in terms of all the software stuff, you know. To, to, to paraphrase, "I didn't have time to write you an app with two features, so I wrote you an app with 50 features." Like the, the not having to apply a critical eye and a sense of perspective and a curated, you know, set of taste.

[00:53:50] Like you just barf everything out that you can possibly think of. And like, I don't think that makes things better.

[00:53:57] **Adam:** Yeah. I mean, a-applications with opinions have more loyal, customers, right? Like, if you make a, an app that can do 100 things, you might get 100,000 customers, if you're lucky. But if you make that same app do, you know, 12 things really, really, really well, you might get 10,000 people, but those 10,000 people are gonna 100X their love for the application, and they'll be your evangelists and, you know, your, your champions, and they'll be a lot more willing to pay more.

[00:54:31] **Ben:** Well, we did it. We managed to have a non-AI session.

[00:54:37] I, I just had, like, one th- one small one, which is just that all this talk of AI in general, people talking about how they're using AI to optimize their life and their schedules and their childcare and their meal cooking and all this stuff, I don't do any of that.

[00:54:52] It just makes me feel like my life is so boring. Like, I don't have any, opportunity for these micro-optimizations that people seem super excited about. And, I don't know. I'm kind of okay with that. Like, I'm just kind of a boring person, and I'm kind of okay living a pretty boring life, so just think that's...

[00:55:12] It's funny. It's like, when I listen to Syntax.fm and Wes Bos and Scott Tolinski are talking about, like, all the crazy stuff they do and, like, the apps they're building. And, like, Wes is always talking about repairing electronics and how he replaced microchips in his kids' toys and stuff, and I'm just like, "My life is so boring."

[00:55:32] I don't do any of that. I've never once replaced a switch plate with anything more interesting than a switch plate, you know? just where I am in life, I guess.

[00:55:41] **Adam:** Well, stay tuned f-for next week's episode where, we're gonna talk about walling off your mental garden, I guess, among other things.

## [00:55:48] Patreon

[00:55:48] **Adam:** but, in the meantime, this episode of Working Code was brought to you by my new app, Little Frumpy Limericks.

[00:55:53] **Tim:** Mm-hmm.

[00:55:56] **Adam:** And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:56:10] Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

[00:56:13] **Ben:** I

[00:56:14] **Adam:** if you would like to help us out, you can go to patreon.com/workingcodepod with all kinds of fun perks like membership and a slightly smaller bank account and our

[00:56:24] gratitude. Very Very slightly. anyway, we greatly appreciate all of our patrons, and you should be one too.

## [00:56:33] Thanks For Listening!

[00:56:33] **Adam:** that's it for us this week. We'll catch you next week, and until then...

[00:56:36] **Tim:** Hey, we're not smoking crack. We can 10X our love for you year over year. Your heart matters.
