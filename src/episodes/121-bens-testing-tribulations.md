---
title: "121: Ben's Testing Tribulations"
description: "We decided to dig into the topic of 'what to test' more closely."
date: 2023-04-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/121-bens-testing-tribulations/id1544142288?i=1000607512535"></iframe>

Ben was recently tasked with removing an old feature from one of his services. As he did this, he kept breaking tests that were tightly coupled to the rendering of user interface (UI). In his mind, these tests were unnecessarily "brittle" and appeared to be testing the underlying front-end framework more so than the underlying business logic. When he brought this up in the [podcast's Discord server][working-code-discord], people disagreed. As such, we decided to dig into the topic of "what to test" more closely.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/121-bens-testing-tribulations.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** first off, hold up. Ben is doing some testing at.

[00:00:03] **Ben:** to be clear, , that's, that is overstating it heavily.

[00:00:08] **Adam:** I didn't say Ben was writing.

[00:00:10] **Tim:** Oh, okay.

[00:00:11] **Ben:** I am. if anything I'm deleting tests

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go. It is show number 1 21. And on today's show we are going to, I guess once again revisit testing.

[00:00:42] **Tim:** What

[00:00:43] **Adam:** Ben had some, testing stuff he wanted to talk about, and I am not one to let a dead horse go unbeaten.

[00:00:49] **Adam:** So we will once again be talking about testing. but first as usual, we'll start with our triumphs and fails. And since this is not the first time that we have talked about testing on the show, I was just a little curious about things that had gone on. And I wanna say we're gonna have to make it a policy.

[00:01:04] **Adam:** Like once something happens, once it's just a thing that happens when it happens twice, it's a pattern. When it becomes a third time, you're, you're verging on policy at this point. Right? So I went back and I looked, and it was episode nine that we talked about testing originally. And then we had, Scott Straus on about half the podcast ago, if you guys can believe that.

[00:01:24] **Carol:** Wow.

[00:01:25] **Adam:** Yeah, that was, it was episode 65. We're doing 1 21 tonight.

[00:01:29] **Carol:** Oh man.

[00:01:30] **Adam:** yeah. And we talked about t d d with Scott. and now we're, we're, and on both of those episodes, Ben went first and it's Ben's turn to go first tonight. So anytime we talk about testing. Ben, you're first.

## [00:01:44] Ben's Triumph

[00:01:44] **Ben:** All right, well then I'm gonna kick us off with a trium. and, I've been talking about the hot wire framework over the last couple of episodes.

[00:01:51] **Adam:** What's this? I haven't heard of it.

[00:01:53] **Ben:** it's,

[00:01:54] **Adam:** Is it part of the legacy?

[00:01:56] **Ben:** so it's a, it's a framework, it's a front end framework from the guys over at Base Camp. And, I've been digging into it sort of just in an isolated kind of, proof of concept way.

[00:02:05] **Ben:** a couple of days ago, maybe a week ago, I started applying Hotwire to my ColdFusion blog. And, I've just about got it all working. I've hit a lot of road bumps along the way. There's some really interesting edge cases that you don't think about. As an example, part of how Hotwire works is that the Turbo drive aspect of it creates a long running process, basically holds your page open, and then performs navigations via the fetch api instead of doing full page refresh.

[00:02:37] **Ben:** which is fine most of the time. However, I have a lot of links to really old demos that I've put together that are, you know, from a decade ago. And Turbo Drive will happily load those right into the same long-running context. But the problem is, if those aren't Hotwire compatible, so to speak, they'll end up loading style sheets and other JavaScript libraries.

[00:03:00] **Ben:** And those just stick around in memory because they weren't built to be hot wire compatible. So you have to find ways to work around that. And I'm, I'm slowly getting there. And then there's issues with layouts. I have multiple layouts for the blog, and that was problematic. And I have multiple CSS sheets and that was problematic.

[00:03:15] **Ben:** So I've been hitting these hurdles and then fixing them one at a time. But, I think I've just about got something that, that's working. And a, as we discussed in a previous episode, it's really not gonna affect the initial page load, which is really what the primary means of operating a blog is. So users probably won't have any tangible difference in their experience, but.

[00:03:36] **Ben:** I'll know, I'll know that their life is better.

[00:03:38] **Carol:** You'll know. That's all that matters.

[00:03:40] **Ben:** and I'm pretty excited about that.

[00:03:42] **Adam:** That's pretty cool, man. So if you, let's say you identify a link in an old article to one of these demos that you don't want to. Load using hot wire. Is there, like, do you put an extra attribute on the link to say, don't load this via hot

[00:03:54] **Ben:** So you could do that. you can say Data turbo equals false and Turbo Drive will just ignore it. But I have links that are embedded within data-driven content, you know, content coming outta the database. So I don't wanna have to necessarily update those on the fly or update them in the database. So the approach that I've taken is that when Turbo Drive goes to intercept a link action, it actually triggers a, an event called Turbo Click, and you have the opportunity to call prevent default on that.

[00:04:23] **Ben:** And if you prevent default, then it basically goes hands off and just lets the browser, you know, the, the default behavior for the browser take over. , that's what I've done to, to solve that problem.

[00:04:34] **Adam:** So you just look at the url and if it's like in the demo folder, you're like, no,

[00:04:38] **Ben:** yeah. That's exactly it. They're all, like, every demo I have is inside of a resources folder, so anytime you link to a resources base link, I just, I, I ignore it and let the browser do its thing.

[00:04:50] **Adam:** Cool, cool.

[00:04:51] **Ben:** But yeah. Anyway, so I'm excited about that and, I'm sure I'll have more to report on that next week. But,

[00:04:56] **Adam:** as

[00:04:56] **Carol:** Yeah. I, I am loving the weekly update. It's like, great. Yeah.

[00:05:00] **Tim:** Hey, but we did miss an update, or maybe I just missed it, how you're, deleting files on S3

[00:05:07] **Adam:** oh

[00:05:07] **Adam:** yeah. What

[00:05:08] **Carol:** oh yeah,

[00:05:08] **Adam:** on?

[00:05:09] **Ben:** so I, I, there was one, there was one massive prefix, this prototypes, a p i two prefix. it finally finished scanning, I think on Tuesday of this week. and it, it found I think about 591 terabytes of data that should have been deleted over the years

[00:05:28] **Adam:** That'll save you $7.

[00:05:30] **Ben:** Yeah, apparently it,one of my coworkers, this guy Jonathan Wilson, he's been doing a deep, deep, extensively deep dive into S3 and all the different storage options, and there's monitoring costs and different tiering and even glacier.

[00:05:44] **Ben:** Now there's an instant access glacier, which I didn't realize. Yeah, that's a, it's a relatively new, it's, it's, so, it's, oh man. He gave a presentation about all this stuff on Wednesday, yesterday, and it was really, really good. It's so crazy. There's all these calculations you have to do. So for the Instant Access Glacier, it's like a third, the cost of standard S3 storage and it's instant access, but it costs three times as much to access it.

[00:06:11] **Ben:** So it's like you have to do all these calculations for how. , what percentage of our data is gonna be there and how often is it gonna get used? And is the three times cost of access worth the third, the price of long-term storage and, and like all the different tiers have these funky calculations you have to do, but

[00:06:30] **Tim:** So, so it's good for stuff that you want to store, but you don't access it that often.

[00:06:34] **Ben:** yeah, yeah, yeah. Absolutely.

[00:06:36] **Carol:** But when you do, it's there quickly now.

[00:06:38] **Tim:** yeah.

[00:06:38] **Ben:** Yeah, it's nuts.

[00:06:40] **Carol:** Yeah.

[00:06:41] **Tim:** what, what does Amazon just say? We don't want you to know how much it's gonna cost. That mean, that's basically what it boils down to. Yeah.

[00:06:45] **Carol:** it does. I feel like the solution is just turning on and we'll send you a bill

[00:06:51] **Tim:** Exactly.

[00:06:52] **Ben:** Oh, man. All right. Anyway, that's me. Carol, what do you got going on?

## [00:06:56] Carol's Triumphs

[00:06:56] **Carol:** Okay guys, I'm going to be winning enough for all of us tonight, so if any of you are failing, I have it all covered. So I got like three things here that are worth sharing. Number one, we've been dieting in the house and working out more, and I found a cookie recipe that I could eat that tastes freaking amazing.

[00:07:14] **Carol:** That's just peanut butter, Splenda, and an egg, and it doesn't sound good, but it's the best peanut butter cookies I've ever had, and it's diet approved. So great.

[00:07:23] **Adam:** When you say it's diet approved, are we talking like, like a, is it like a gluten thing you're avoiding or is it just calories or, or what?

[00:07:30] **Carol:** actually, I signed up for Noom. My husband signed up for it, so I said, sure, if you're doing it, I'm bored currently in my life, so I'll do it with you. So I'm doing Noom with him and it just encourages you to eat healthier. So making smarter decisions. And it tracks like how many, you know, vegetables you have versus what lean you have versus what unhealthy things you have,

[00:07:50] **Ben:** you blow into?

[00:07:51] **Carol:** no, that's Lumen.

[00:07:53] **Carol:** We also have one of those which we don't use either cause that that only works if you are in ketosis. So it tells you like if your body's in ketosis, which actually isn't really great for you. So I'm not gonna do that. I'm just gonna try to eat more vegetables. But, so the peanut butter that I'm using is like healthier and stuff.

[00:08:09] **Carol:** It's low fat and not so bad for me. And the cookies are delicious,

[00:08:13] **Adam:** I love peanut butter.

[00:08:14] **Carol:** oh, I'm, I'm addicted. It's so good.

[00:08:17] **Adam:** Peanut butter is the only correct type of Eminem for the record.

[00:08:19] **Carol:** uh,I'll send, I'll send you the recipe if you want it, and you can give it a try.

[00:08:25] **Adam:** definitely

[00:08:25] **Carol:** the second thing is Instagram for me is loaded full of a d d posts and golden doodles because that's where our dog is.

[00:08:33] **Carol:** That's, that's all we get,

[00:08:34] **Carol:** right?

[00:08:35] **Tim:** that's where you live. A d d, the lane, the cross section of a D. D and golden doodles.

[00:08:40] **Carol:** Yeah. Well I found this, this post that was about planners for people with A D H D and I went on to their site and was looking and because they're in early startup phases, a lot of their, the ones I wanted were free. They're like, just sign up, make an order, and they'll send you the planner for free and you print it at home.

[00:09:01] **Carol:** Oh my gosh. Change my life. Like I track everything like by the hour showing what I'm doing. Where previously Steve would come home and he'd be like, what you been doing today? And I'm like, I don't know, just around the house bouncing on things. Couldn't tell you. I did a whole bunch of stuff, but none of it makes sense cuz you know, it's just back and forth.

[00:09:17] **Carol:** Well now I just kind of jot down, so it has like little hourly blocks. So I can look back and actually go, what did I get accomplished today? And every time I get off task, I jot it down so I know to get back on task so I can go, okay, here are my distractions. These are the things I need to work on. And it has been amazing.

[00:09:36] **Carol:** And, I put a, the link to it in the, the show notes so that anyone can go grab it.

[00:09:42] **Tim:** Does it come with thumbtacks and a bunch of red string and you like have to,

[00:09:47] **Carol:** No, it's not, not that cool. It's just a get a pen, write it down, you're good to go. No hard work.

[00:09:53] **Ben:** Yo. You know what it reminds me of though, a bunch of episodes ago, I think it was Adam was talking about the, the thing of dots where you can print out 90 years of your life and you can check out

[00:10:03] **Adam:** life calendar.

[00:10:04] **Ben:** at a time or something. I almost feel like you, you would be, you would help. Yeah, you would enjoy a 24 hour version of that where it's like 10 minute blocks and you could scribble in what you do at 10 minute increments.

[00:10:17] **Carol:** I would be so happy doing that. Yeah.

[00:10:20] **Adam:** You know? Set an, set yourself an alarm to wake up every 10 minutes overnight and write down slept.

[00:10:25] **Carol:** Was sleeping until my alarm went off . So, yeah, the planner's really cold, but the big news is, is I applied for my L L C,

[00:10:35] **Carol:** so that should be approved tomorrow or by Monday, hopefully. And I will officially be, you know, one step closer to having my company going. So

[00:10:45] **Adam:** have like a cool company name?

[00:10:47] **Carol:** I think it's really cool.

[00:10:49] **Carol:** You guys can let me

[00:10:50] **Adam:** Is it Carol Hamilton, llc.

[00:10:52] **Carol:** that's not my name anymore, Adam. I

[00:10:54] **Adam:** Oh, that, you're right. I'm sorry. I just deadnamed you.

[00:10:57] **Carol:** I know, I see this. actually I decided to use concept Workspace,

[00:11:03] **Carol:** so that's what I'm gonna be called. Yeah. I feel like it's a good place for engineering consulting on management planning. It's literally just whatever you can bring at, we'll make a concept for it and we'll figure out how to make it go right.

[00:11:16] **Carol:** Like, We'll, we'll make it happen. So yeah, I'm super excited about it.

[00:11:21] **Ben:** Is this gonna be in Delaware? Is that, isn't that where like everyone does all their things?

[00:11:25] **Carol:** it is. So I did not do Delaware. I did Washington just because it's where we have a state of residency already and because we move all over the place, I didn't really understand it all, so legal Zoom said Washington was fine, so I picked Washington

[00:11:42] **Ben:** Nice.

[00:11:43] **Carol:** Yeah,

[00:11:43] **Adam:** Delaware is like tax friendly for like startups, so

[00:11:47] **Carol:** And it's also friendly for employers versus employees, so.

[00:11:51] **Tim:** it, and it's friendly. I think you, there's less rules about the AR in the, OR articles of incorporation about like the number of people you have to have.

[00:11:59] **Carol:** Yeah, you're bored. All of that stuff. It changes state by state, so it's one of the more friendly for,

[00:12:05] **Carol:** for

[00:12:06] **Tim:** I think I, I have one. I don't really use it. I just renew it, in Delaware, but that's, I'm the only person on the board, so

[00:12:13] **Carol:** sole proprietor.

[00:12:14] **Tim:** Yeah.

[00:12:14] **Carol:** Yeah.

[00:12:16] **Adam:** it's concept testicles.

[00:12:18] **Tim:** Yeah.

[00:12:19] **Carol:** Yeah.

[00:12:20] **Tim:** Yeah, sole, sole proprietors. That way I don't have to have a secretary and a, all those other positions, you know? So

[00:12:27] **Carol:** You can own it and manage it. Yep.

[00:12:29] **Tim:** yeah,

[00:12:30] **Carol:** Yeah, that's me. I'm winning you guys.

[00:12:33] **Adam:** Congrats. That's

[00:12:34] **Carol:** Thanks. what about you, Tim? What's you got going on

## [00:12:37] Tim's Triumph

[00:12:37] **Tim:** it's a, it's a mini triumph. It's not huge, but, so, you know, I, I hate design work. I'm not really good at it, but we had a request come in customer, they're changed all their branding and they wanted to do it, and everyone else was busy on other stuff. I'm like, well, I'll take a hack at it. And is it, it was in our, one of our scallop projects.

[00:12:54] **Tim:** Fortunately, the scallop project was really nicely laid out as far as, you know, changing design and, yeah. So I was able to take their, their, their style sheets, another style sheets there. what do you call that?

[00:13:05] **Carol:** like a mock up.

[00:13:06] **Tim:** No, they, they have like the corporate colors and the c.

[00:13:08] **Ben:** system.

[00:13:09] **Adam:** no, style.

[00:13:10] **Tim:** Style guide. Yeah. They're style guide. They're style guide. Take their fonts and everything and, and, and, and yeah, about three or four hours I got it. Got it. Looking good. And send it to 'em. And I missed, I had one typo that they said I fixed that and it was done. But, but yeah, usually I hate, I hate doing any sort of design work, but particularly if it's like not a, I'm not working with a, a person whose job is designed.

[00:13:33] **Tim:** If it's just like a person was like, they don't really know what they want. They're like, oh, kind of make it look like this. And then, then it's like hours of tweaking little tiny things. But she had everything all kind of, pretty much laid out, made it look similar and got it. You know, and she's like, perfect.

[00:13:46] **Tim:** So, got it all done within a few hours.

[00:13:49] **Carol:** Yeah. I will, I'll never forget the email chain I had about turning, banner blue.

[00:13:54] **Tim:** Hmm.

[00:13:55] **Carol:** Just blue, right?

[00:13:56] **Tim:** Yeah.

[00:13:57] **Carol:** That's not the right blue. It needs to be darker. Can you tell me what? Just make it darker. That's not the right blue.

[00:14:03] **Adam:** Oh my God.

[00:14:04] **Tim:** gave me the hex code. She gave me the hex code.

[00:14:07] **Adam:** Can you make it a happier blue?

[00:14:09] **Tim:** Yeah,

[00:14:11] **Ben:** Have you guys, has anyone seen anything about Adobe Firefly that came out this week?

[00:14:16] **Tim:** yeah. I signed up for that.

[00:14:17] **Ben:** Oh my God, I watched some of the demo videos. It looks bananas. I

[00:14:22] **Tim:** Generative ai.

[00:14:23] **Ben:** yeah, but you know, with Adobe Flare on top of it,

[00:14:27] **Tim:** Yeah, and, and from what I understand, they're, they're a lot better at doing like letters and fonts and stuff, cuz I know a lot of the generative ai, when it produces words, it's like

[00:14:36] **Ben:** garbled

[00:14:37] **Tim:** gar it garbled. Yeah.

[00:14:38] **Adam:** Looks like a capcha

[00:14:40] **Tim:** Yeah. Capture.

[00:14:42] **Adam:** because that's what it knows. Letters looks like.

[00:14:44] **Tim:** Exactly. I'm a robot, that's all I see. , oh, I, I do have a, a failure. It's not really my failure, but I was scared to death you guys.

[00:14:53] **Tim:** So Friday my daughter got home from school and she got some library books that she wanted to take. So she went down to little town just south of us called Perry. After she dropped 'em off, her and her mom decided to go get a cup of coffee at a local, local coffee shop. And she, got, got a brownie and the brownie didn't have any nuts on it on top, but she put into it.

[00:15:11] **Tim:** And then two bites, she started swelling up and they're like, what's, they're like, what's in this brownie? Because it wasn't like Raptor, they was like a homemade brownie that they were selling. It was because it was, they were making it,was that called, carb friendly? You know, there's no carbs in it.

[00:15:25] **Tim:** They made it with pecan.

[00:15:27] **Adam:** Mm.

[00:15:28] **Carol:** She's allergic to put.

[00:15:29] **Tim:** She's allergic to. She's allergic to tree nuts. Yeah. So her lips swell up, her eyes swell

[00:15:34] **Ben:** oh.

[00:15:35] **Tim:** They, they, they took her to like a local med, med stop and they had her in there and they were giving her stuff. It wasn't going down. They're like, we're we're gonna call an ambulance. We might have, they might have to intubate.

[00:15:44] **Tim:** So they, they call an ambulance, they take her to the hospital. They didn't have to intubate,

[00:15:49] **Tim:** you know, they got her on some, some breathing treatments and stuff and finally went down. But man, first I was scared to death cuz it's like my wife calls me, she's like, we were wondering if she was still allergic.

[00:15:58] **Tim:** Well, she is And, but then when I find out, they're like, thinking about intubating. I'm like, oh my God. So then after I was scared and then it, when I news she was fine. I'm like, now I was mad. I'm like, all right, yeah, these guys are paying those medical bills. They should have, you know.

[00:16:15] **Carol:** so it was at, it was at like a public place. It wasn't like a little

[00:16:18] **Tim:** No, no. It was a little, little coffee

[00:16:20] **Tim:** shop. Yeah.

[00:16:20] **Tim:** little little coffee shop there on the square down there in Perry. And, they had no, no signage, no nothing. Just said brownie.

[00:16:25] **Carol:** Yeah.

[00:16:26] **Tim:** 99 cents.

[00:16:27] **Carol:** Oh, and who puts pecans in brownies without putting 'em on top? Right. Like usually you put nuts on top. If it has any nuts in it, you don't make it out of nut flour.

[00:16:36] **Tim:** Well, well, they were trying to make it gluten friendly. Right.

[00:16:39] **Carol:** Oh

[00:16:40] **Tim:** I mean, with gluten you get a bad stomach and I'm sure it's painful, but with nuts

[00:16:44] **Tim:** you could die.

[00:16:45] **Ben:** Yeah,

[00:16:46] **Adam:** Yeah. Does, does your, wife or daughter carry like an EpiPen or anything like that?

[00:16:50] **Tim:** They do now they, they're the EpiPen and expired,

[00:16:53] **Tim:** so

[00:16:54] **Adam:** Hmm.

[00:16:55] **Carol:** yeah. I just had to call my bcm, cuz I realized mine expired in 2020 .

[00:16:59] **Carol:** I was like, I might need a new one.

[00:17:01] **Tim:** yeah, they're only good for two years, so,

[00:17:03] **Carol:** I am so sorry. I'm glad she's okay. She is okay. Fully,

[00:17:06] **Tim:** Oh, yeah, she's, she's fully okay. She's fully okay. They, she had to take Benadryl like every four hours for four days and take steroids and

[00:17:12] **Tim:** stuff,

[00:17:13] **Ben:** Oh.

[00:17:14] **Carol:** Set. A little side note to help her, add some tums to it or some, like any type of, antacid with it.

[00:17:22] **Carol:** And it'll also help break it down faster as well. It helps with the reactions when you're having a reaction. If you take Benadryl and, like Pepcid I think is what it is. Any an acid, it helps stop the reaction. Clicker.

[00:17:34] **Tim:** Okay. Good to know. Good to know. Come coming from a pro there

[00:17:39] **Carol:** yeah. I know my thanks.

[00:17:42] **Tim:** Anyway, so that's, that's me. Little, little triumph and a, and a big scary fail. So

[00:17:46] **Adam:** Whew.

[00:17:48] **Tim:** how about you, Adam?

## [00:17:49] Adam's Failure

[00:17:49] **Adam:** Well, I will not allow for triumph to stand. I, it's been a week, right? I, I can, I could pick something triumphant from this week, but I choose to pick a fail, and that is, today, I, I spent almost my entire day working on compliance work. I, I was updating policy, so I, I talked previously about all the SOC two work we're doing.

[00:18:09] **Adam:** Yeah, no, this is probably, I mean, the, the whole SOC two process is definitely gonna take us through the end of the calendar year, if not longer, because it's a, well, it's a, it's a, you know, you get your ducks in a row, and then the, the point of the SOC two, type two that we're doing is that, okay, like you're doing a, an audit over time you are proving that you can remain compliant for a certain amount of time.

[00:18:30] **Adam:** So you have to get compliant and then you have to stay compliant. And that's what. Getting audited on. and so a, a big chunk of that will be staying compliant. But, so we initially, when I was doing the, the policy work for, our, our policies for SOC two, you know, I was thinking that the P C I clauses in the templates that they gave us, I didn't need to really concern myself with those because we were only doing SOC two at the time.

[00:18:55] **Adam:** You know, we, we did PCI separately, so I was like, okay, whatever. Doesn't matter. So I completely excluded all the PCI paragraphs, and no big deal. Well now we're doing PCI through the same tool, with the same, auditing vendor and everything. So it's just easier to kind of get it all in one place, all done at the same.

[00:19:13] **Adam:** So I had to go through all of the policies and, and add back in all those paragraphs that I missed. And of course, like they have, the, you know, there's, their templates have been updated a little bit, so they're tweaking the language, adding things that could be better or whatever. And so I have to go through each of these policies and look at like a diff basically, and and compare and say, okay, well this was something that changed on purpose because I, you know, I want it to fit our business model better, or this is something that is totally new, so I need to copy that in.

[00:19:38] **Adam:** Or now this is a PCI thing, so I have to copy that in and it's just, I am done looking at documents on my computer for the rest of the night. At least I'm so tired of this crap. brain is mush.

[00:19:51] **Ben:** Yo, I can't believe you've been doing it for so long, and, and with at least the face that you present us with is, is rather cheery and upbeat. I feel like I'd get through these days and just be like a guy from Clerks where I'm like, I'm not even supposed to be here today.

[00:20:10] **Adam:** It's a, it's a lot of hurry up and wait, right? So like, I, there are, I'm, I'm spending a lot of time as not the roadblock, but being blocked. So it's like, okay, I gotta do as much as I can about this thing, and then, okay, I need an answer to a question, so I have to wait or have a meeting, talk to different vendors to get pricing and this and that.

[00:20:27] **Adam:** And it's all, it's all hurry up and wait. So,

[00:20:30] **Tim:** Good thing is once you have all your documents and all your procedures in place, I mean, next year will be a whole lot easier unless there's like a dramatic shift in the way you're doing things.

[00:20:39] **Tim:** yeah, the first year's the hardest and then kind of on cruise control from there, as long as you stay, compliant and, and obey your policies. Every year we gotta go through those documents and, and mark any changes that we make or just say, nothing has changed, and put your date, name, date, and go move on

[00:20:56] **Carol:** Sign, resubmit.

[00:20:57] **Tim:** yep.

[00:20:58] **Adam:** yep. Yep. So that's it. like I said, some good things happened this week too, but, I cannot abide four triumphs. So

[00:21:06] **Carol:** Well, I don't care. My cookie recipe was enough wins for all of us.

[00:21:10] **Tim:** It's true. It's true.

## [00:21:12] Ben on Tests at his Work

[00:21:12] **Adam:** Alright, so, we were talking in Discord earlier today, us and the patrons about, some testing stuff that Ben's been going through at work. And we decided to turn it into a show topic, which is why we're talking about testing for the third time

[00:21:26] **Tim:** first off, hold up. Ben is doing some testing at.

[00:21:30] **Ben:** to be clear, , that's, that is overstating it heavily.

[00:21:34] **Adam:** I didn't say Ben was writing.

[00:21:36] **Tim:** Oh, okay.

[00:21:37] **Ben:** I am. if anything I'm deleting tests

[00:21:42] **Tim:** Okay. I thought I stepped into a Bazaro world version here. Okay.

[00:21:47] **Ben:** so

[00:21:47] **Carol:** on the haters.

[00:21:48] **Ben:** this, all, this started because at work we have a certain type of data point that is being deprecated within the. And, so I've, a bunch of teams are working on removing it from a bunch of different services and code bases. And, I'm, I've been given the task of doing it for this one particular service.

[00:22:08] **Ben:** So I'm going through and I'm trying to delete all references to this type of data. And as I'm doing this, one, I don't have any of the code actually running locally. essentially I do all the work locally and then I just push it up to our continuous integration environment. I will push it up to code ship, and then code ship runs all the tests, which is really, really slow.

[00:22:29] **Ben:** It takes like a, a solid 10 to 15 minutes for the tests to run, which boggles my mind because that seems insane that anyone's gonna wait 15 minutes for a test run. But,

[00:22:40] **Tim:** Coffee break.

[00:22:42] **Ben:** You know, it's actually funny cuz the, the, the classic comic of the guys sword fighting in the hallway. You know, what do you do? And, oh, we're waiting for stuff to compile. That's, this is like the first time in my life I've ever actually felt that pain.

[00:22:54] **Tim:** Mm-hmm.

[00:22:54] **Ben:** it now. So what ended up happening was I'm removing this data from some of the interfaces.

[00:23:01] **Ben:** And this is to be clear, the repository that I'm working in right now is, is really a front end repository that latches onto a bunch of backend APIs

[00:23:10] **Adam:** and you said this is like the, the, some of the oldest part of the new, system or what

[00:23:15] **Ben:** It's the new platform, but it's like the, some of the oldest stuff in the new platform.

[00:23:20] **Tim:** So it's the legacy of the new. So you're still on the Legacy team,

[00:23:23] **Ben:** Exactly. you know, baby steps towards modern modernity. and it's actually written in VJs, which nothing else in our entire platform is written, but just the service is written in VJs. so anyway, I started deleting stuff.

[00:23:36] **Ben:** these references and I'd pushed up to code ship and these tests would start failing, which I'm like, how are tests failing? All I'm doing is removing stuff. It boggles my mind. And, you know, caveat, of course, I have very little testing experience here, and there were a lot of tests where it was checking to see if navigational elements were being listed properly or like a, a, a bulleted list or, or, or like a bunch of buttons in a row and would have code, like make sure that the button in position three is for this type of data and make sure the button in position four is for this type of data and make sure that, you know, these six things show up in the navigation list.

[00:24:15] **Ben:** And, it just boggled my mind that people are actually testing that kind of stuff. So what, what happened in the Discord chat was me basically ranting about how ridiculous these tests. and then everybody else, instead of high fiving me and telling me how cool I am, pushed back and said, no, actually, that's exactly what tests are supposed to do.

[00:24:36] **Ben:** They're supposed to stop and make you think about why you're, you're breaking stuff. so I thought it'd maybe be interesting to dig a little bit deeper into the what of testing. Like what, what is actually worth testing, because none of the stuff that I was breaking felt like it was worth testing in the first place.

[00:24:57] **Tim:** Before we get into that, I do wanna ask you, you kind of breeze through it. You're not running locally. Is that a reason for that? Do other people run it locally or you just couldn't be

[00:25:06] **Ben:** I just couldn't be bothered.

[00:25:08] **Ben:** I,

[00:25:08] **Tim:** buddy.

[00:25:09] **Ben:** I just figured deleting code

[00:25:11] **Tim:** Well, there's your problem right there.

[00:25:13] **Ben:** easy,

[00:25:14] **Adam:** Honestly, I think it's great that when you deleted some codes, some tests started to fail. Like that means that the, the code coverage was, I mean, we're gonna, I'm sure, talk about code coverage, but the, you know, and how that's not necessarily the thing that you should be reaching for, but, it means that there was a lot of test coverage for the things that were there,

[00:25:31] **Ben:** So, so here's, so I've been thinking about this since we talked about it in the Discord and thinking about how does it make sense to attack this topic? And two things pop to my mind. One is this concept of brittleness that I, I don't know if I can define what this means, but I have historically been told that if tests are very brittle, meaning they break very often because of what you do, that there's probably a problem there.

[00:26:00] **Ben:** I don't know what that is. Let's put a pin in that for a second. The other thing that pops to my mind is this concept in testing. And again, Caveat, very little hands on experience here, that you don't test the libraries. Meaning if I'm gonna pull jQuery into my projects, I don't need to test that jQuery works because the jQuery team tests to make sure jQuery works.

[00:26:22] **Ben:** Or if I'm gonna pull Angular in, I don't need to test that Angular works. The Angular team does that quite extensively. So when it comes to testing, UI rendering, and I think this is part of where I get very like, oh, this seems useless, is that so much of what is being tested is essentially the framework itself, like the the UI framework.

[00:26:48] **Ben:** Because if you think about how a UI framework works, it's taking the state that you give it, like, here's my data model and it's translating it into a UI with probably a bunch of ifs and iterations and conditional class assignments, stuff like that. So, To me, if I have an array of data and I want to turn that array of data into buttons or links on the page to test that those links are actually there, it's really testing to make sure that the framework is properly translating your data into UI elements.

[00:27:25] **Ben:** And to me, that feels very much like a don't test the library faux pa.

[00:27:30] **Adam:** Mm-hmm.

[00:27:30] **Ben:** So those, so those are the two things, the brittleness and the don't test the library.

[00:27:34] **Adam:** So which one do you wanna double click on first? You, you used the, we gotta put a pin in, so I gotta, I'm, I'm doubling down on crappy business metaphors here. Manager speak.

## [00:27:44] Test Brittlenesss

[00:27:44] **Ben:** let's, let's, let's talk about brittleness first because I think I can, I can imagine a world in which tests have to be brittle because they are truly testing very low level things, and those low level chains can't change without breaking. but I have to imagine that there are cases where things just are brittle because the deaths aren't properly scaled with the thing being tested, scaled, like in and out kind of a thing.

[00:28:11] **Adam:** I think there's a lot of different reasons that you would consider it a test or like a suite of tests to be brittle. I think it might be easiest to start by saying like, what is something that's guaranteed to not be brittle? And for me, the first thing that comes to mind is like a pure function, right?

[00:28:25] **Adam:** So you've got a function, you call it, you give it some inputs and it returns an output. And if you give it the same input, if you give it one and seven, you're always gonna get eight back because it's an ad function, right? There's no side effects, there's no outside context that affects what happens on the inside.

[00:28:40] **Adam:** That's what makes it a pure function, right? And so you write tests for that, and it doesn't matter what you do to do the sum that's happening inside that function, whether you choose to convert them to binary and do binary edition or to just use the math library built into the programming language or whatever.

[00:28:58] **Adam:** you know, it doesn't matter what the implementation looks like. The the test is still going to pass if you give it one and seven and it returns eight, right? and so that is, I think for me, the definition of not brittle. You can change what's going on inside the implementation and the tests still pass as long as the interface, is still, the same.

[00:29:17] **Adam:** Did I say that right? Yeah, I think

[00:29:19] **Ben:** l let me throw this at you because A, as much as I am, I hate to say anti-testing, but let's say testing agnostic. Uh, I, I actually, there was a brief period in my career where I was on a team where I was required to write tests and, uh, And when I first started doing it, what I found was that I was writing, let's say I had to pull data out of a database or let's call this say some sort of data persistence repository object.

[00:29:47] **Ben:** And I had to pull data out. My initial test when I first started writing tests, I would get that thing out of the data and I would say, okay, does this field match this value? Does this field match this value? Does this field match this value? And like one, it was hella tedious because now I'm like basically checking that all the columns come back from the database.

[00:30:08] **Ben:** And what I ended up doing after a while was just checking a, like the primary key, like I asked for object with ID seven, does the thing that comes back have ID seven in it? And like I don't care about any of the other fields because I'm asking for a record, essentially. It better have all the fields if the database is functioning properly, like I shouldn't have to test that.

[00:30:29] **Adam:** what you're talking about is testing the library, except in this case, the library is the MySQL or whatever, instead of jQuery,

[00:30:35] **Ben:** Well, right, right. Exactly. So I, I, I started to, I don't wanna say short circuit my test, but it was like, I found the, the thing that I, I wanna say that I found the thing that I cared about, but I, I guess that's the, that's the pivot of the whole conversation is what it is. What is it that we actually care about in the test.

[00:30:52] **Ben:** And I think maybe that's where I just, I don't see the same value that a lot of other people are clearly seeing. Feels like. so I dunno, the brittleness to me, like order, the order of things feels like you shouldn't have to test that. Like, let's say on day one, I want this tab to be position one and like this navigational tab, you position two.

[00:31:13] **Ben:** If, if like the product team comes and says, Hey, actually we wanna start emphasizing tab two, can we move that to tab one? I feel like if I move that to tab one and test break, like that's crazy.

[00:31:24] **Adam:** a hundred percent agree.

[00:31:25] **Ben:** okay, all right. So I'm not that crazy

[00:31:27] **Adam:** you are pretty close to that crazy so yes, I think I wanna take a, a very short step back here. So we talked about, you know, when you first started testing, you were like grabbing a row from the database and, and asserting that the, you've got all of the elements of the database.

[00:31:44] **Adam:** because that was easy for you to understand how to test, even though that wasn't maybe necessarily a useful

[00:31:49] **Adam:** thing

[00:31:50] **Ben:** I thought that's how you had to test. Like, I thought that was the point

[00:31:53] **Adam:** That was the night. Yeah. Right. When I was a child, I did childish things. Right. and, and so what you're describing, like te asserting that the, the tab named, you know, settings is in position seven.

[00:32:07] **Adam:** That's a dumb thing to test. Nobody needs to test that. Just like, you don't need to test that. The, the value in the name column for primary key 42 is, uh, Ford prefix, right? Like it's, it's dumb. That's, that's not something you should be testing, but, what is useful and what those same steps that you would take to test position of tab or whatever, like asserting that something is in the UI can be useful in a longer form test.

[00:32:34] **Adam:** Right. There's different types of tests, right? You've got your unit tests, integration tests, end-to-end tests, and, and other things as well. and if you think about it as like, maybe an integration test where you say, okay, I need to be able to click on a tab and that's gonna expose some information in that tab, and I need to be able to, I, you know, I'm expecting there to be a form in that tab, and if I fill out that form and press the button, I'm expecting a modal to pop up.

[00:32:56] **Adam:** And in that modal, I expect this to be there. right? And so you're expecting a series of things to happen and if, you know, it, it doesn't matter what order the tabs are in, right? You click the tab with a certain name. You fill out the form, you hit the button based on what the button label is, and the modal pops up and, and it says, okay, your, your record has been saved or whatever.

[00:33:14] **Adam:** Right? and so that's what you do. You say click the tab, fill out the form, and you're doing assertions along the way. Uh,assert that the form exists, maybe a, you know, a, an input type of name or whatever, or, type of Id not, ID you wouldn't do. Id, label, sorry, with like a, with a label of name, and, you know, fill out the form.

[00:33:30] **Adam:** You're expecting a button with a certain label to be there. You click the button, you expect the modal to pop up after a few seconds and it should say success or, or error. And even if there's error, then you wanna, you know, make the test fail or something. But, so that's, I think that's a more useful approach to UI testing.

[00:33:45] **Adam:** Right. Cuz you're, you are testing that a workflow that you expect to continue to work continues to work versus Yeah. Is the tab or the tabs in the right order That's, that's asinine.

[00:33:59] **Ben:** It does. But I will say it felt like even people were pushing back against that in the chat and, and their perspective was that they didn't want a particular piece of data to be removed from the page

[00:34:13] **Adam:** I, yeah. And I

[00:34:14] **Ben:** being called into question.

[00:34:16] **Adam:** I was part of that conversation as well. And I think that's a slightly different thing than the tabs. Right. So we were talking, I think you said something about like a dropdown and there was an option that was static in the dropdown.

[00:34:26] **Ben:** Well, the, there were, so the, I'm, I'm saying that I'm removing a particular type of data, and let's just say that there are five types of data and that gets translated into a tabbed interface.

[00:34:38] **Ben:** And so I essentially wanted to remove one of those tabs. And so the system was saying like, Hey, there's supposed to be a tab in there for that data type, and I, I

[00:34:49] **Adam:** Okay. So, so let me, let me throw this at you. as an enterprise organization, you have an expectation to keep your systems decently documented, right? And so you have to do your best to keep the application and the documentation in sync. And so if you're gonna

[00:35:06] **Tim:** Unless you're Amazon, then you don't care.

[00:35:10] **Adam:** if you're gonna delete a data type and it's gonna affect the UI like that, then you need to make the same changes in the documentation, right? Just, just delete that part of the documentation as well. and you may not think to do that unless you have a test that says, oh, hey, you know, this thing exists.

[00:35:23] **Adam:** And if this test fails, starts failing you because we have decided to remove this data type, then we need to go remove that from the documentation as well. It, so in that case, I think tests can be useful as reminders that other things need to happen that are dependent on the way that the application currently exists.

## [00:35:41] Snapshot Tests

[00:35:41] **Ben:** Yeah, I mean, yeah, I could see the value add in that. one of the other things that I had to contend with was the tests. Not, not all of the components in this front end had this, but a, a large number of them had snapshot testing. I'm, I'm not really familiar. Yeah. I'm not super familiar with this. What I gather from what I see and what I've heard on other podcasts is you take the, the, the component will render, like you render it to a string, and then you store that string output as an H T M L file, and you keep that in your, like you persist that along with all of your other components and you store it as a snapshot.

[00:36:20] **Ben:** And then as part of the unit test you can say, Hey, when the component renders, does the output match the previous snapshot? And if it doesn't, it'll fail the test. And I mean, to me that feels like the ultimate brittle, because like you could add, you could add anything to an end, a front end for completely unrelated reasons and to, to have it fail a unit test because like suddenly, There's a, like an Aria label or something, or a, some people you could add CSS classes that do nothing but allow like third party libraries to hook into your do.

[00:36:57] **Ben:** Having nothing to do with the component itself. I could just, I don't

[00:37:00] **Adam:** Well, hang on, hang on, hang on again. Again.

[00:37:01] **Ben:** Okay. Okay, okay,

[00:37:02] **Adam:** You're, you're talking about, okay, you wanna add a CSS class that allows a third party library to hook into your dom? What you've just said is you added a new feature and, and now you need to cover that in your test.

[00:37:14] **Ben:** why do I go

[00:37:14] **Ben:** to test

[00:37:15] **Carol:** snapshot, right?

[00:37:16] **Adam:** Right? So here's the thing. You're absolutely right.

[00:37:18] **Adam:** That snap, okay. I need to, I need to, to disclaim this here. I don't currently use snapshot tests, never have. I've, I've toyed with them to understand them, but never have, I don't think I have a good use case for them. That's why I don't use them. And I'm also just not doing a ton of testing yet, even though I'm fully on the testing is good bandwagon.

[00:37:35] **Adam:** anyway, I think snapshot tests are intentionally brittle because you're supposed to be running your tests locally and, and you're supposed to be the one that's going, okay, I'm, I'm changing the way this component works. I'm expecting the, the output of my changes to affect the snapshots, right? And so I change, I change the code.

[00:37:53] **Adam:** I look at the, the output on the html, and I say this is correct. And that, that based on that knowledge, I can say, okay, the, it's okay to update the snapshot based on what just happened, and it'll save the new snapshot or whatever. And so it's just part of the development cycle for that developer where they can be helpful is I'm, I've, I've got my snapshots for my components, you've got your snapshots for your components, and.

[00:38:16] **Adam:** I'm making my changes and I'm only expecting to change things in my components. But it just so happened that you imported some like, you know, modal component from my thing. And I made a, a small CSS change to allow a third party library to hook into my mobile modal. And now your snapshot is gonna yell at me because, when, when I run my tests or when I run the full test suite, because, I'm expecting my thing to change, but you weren't expecting it to change in, in the test for your, you know, components or whatever.

[00:38:43] **Adam:** And so, it, it helps prevent regressions outside, you know, where you're, where you're currently changing things, right? So when you've got this like network effect of like, reuse going on and you can make a change in one place and, and you completely forgot that it could change something way the heck over there, it can save you from that.

[00:39:02] **Carol:** And the good thing is, is if you. Get it right and it did need to change. It's super easy to regenerate those snapshots for future tests. And it's not a big manual thing, it's just regenerate 'em pretty much.

[00:39:15] **Adam:** I'm, I'm really sorry. I feel like I'm kind of, bogarting the mic here. I'm gonna try to like listen more and talk less and let you guys other, other, let the rest of you, yell at Ben for a little while.

[00:39:24] **Carol:** Well can I, can I circle back to the brittle test part with the data? Right. So one of the issues I ran in at my previous job was there were tests that ran based off of actual data rose. So the first thing it did, let's say go hit the database, get me all the information for ID number, you know, 999, well since the last, you know, production refresh.

[00:39:50] **Carol:** Because what we would do is production would come down to non-production environment. So you could test with actual production data, just wipe so that it's. Well, during that time there was an archive process that happened. So now Records 999 no longer exist. So what I had been doing was I was going in and mocking all of those.

[00:40:10] **Carol:** I'm like, okay, we really don't need any of this data from the database. There's no reason to connect to it. And my opinion is that if you are hitting the database, it's no longer a unit test. Now I'm testing data in the database, which is like an integration kind of test. And the unit test doesn't matter because if the data's not there, it's all gonna fail.

[00:40:29] **Carol:** So I feel like that is one of the big brittle tests that I face with not understanding, with people, not understanding how to actually test the function without getting true.

[00:40:42] **Ben:** So let, let me just say that that actually hits home for a lot of the stuff that I've been doing the last couple of days because I, I, I swear like 50% of the code in this front end repository is all fixtures. And I don't know if fixtures is like an official term or whatnot, but it's all like these mock data structures that represent what would've come back from an api.

[00:41:05] **Ben:** And, because I'm removing data, a particular data point, I'm removing that data point from all these different fixtures as well. I mean, not, it balloons the size of the pr, which also makes me angry, but that's, you know, much less of an issue.

[00:41:17] **Carol:** Been like small prs. If you didn't know that

[00:41:20] **Ben:** yeah, I love, I love me some small vrs, but, so it'll, it'll do this exactly to what you're saying, where there were tests that started to.

[00:41:29] **Ben:** Because I removed one data point out of five data points and there were tests that said, Hey, I'm gonna make this call and I should get five unique data points back. And I'm like, really? You're testing the types of data you're getting back. Like that's not your business. The the a p i that's providing that data, that's their business.

[00:41:48] **Ben:** You shouldn't have to test that. Like you should just depend on it working properly.

[00:41:52] **Carol:** to me that throws two red flags. One, either the code was written poorly, so the test had to cover the scenario where it does need to check the type of data cuz the method or function wasn't actually doing that or the test was written poorly. And when you went into those test files, was it actually using that data anywhere with what was being tested?

[00:42:12] **Carol:** Or was it just creating it and never touching it again? Because if it was actually using it, then you should need to fix those tests and figure out if you have a code problem.

[00:42:22] **Ben:** I mean, I will be a hundred percent honest. And saying that when I looked at these test files, I found them very hard to decipher personally. A a a lot of that I'm sure is experiential. Like I'm just not familiar with these testing frameworks.

[00:42:37] **Carol:** What is the testing framework? Are you, you're looking at

[00:42:40] **Ben:** I don't even know it had a, to Adam, Adam Cameron asked about it in the chat and, and they're all in the like, it, blah, blah, blah, blah, blah, does blah, blah, blah, kind of a terminology, but I don't, I think, I think a lot of frameworks

[00:42:53] **Carol:** they do. Yeah.

[00:42:54] **Adam:** a common pattern.

[00:42:55] **Carol:** Yeah.

[00:42:57] **Ben:** so it, it was just hard for me to understand. Plus a lot of, there was a lot of objects spreading and, and like,

[00:43:05] **Adam:** Are you not, super, fluent in the latest JavaScript Synt.

[00:43:10] **Ben:** I. I understand the syntax. I am one who often errors on the side of verbose white space adorning code. So when there's like lots of objects spreading and and tight lines, I find it hard to read,

[00:43:28] **Tim:** Yeah,

[00:43:29] **Ben:** but.

[00:43:30] **Tim:** what? What I don't get is the fact that the database is part of it. Maybe it's just cuz the way we do our testing. Kinda like, I guess kinda what's sim, similar to what Carol was saying, we build, you know, a json structure to represent the data and it's, it's static, right? We, the, the data that we're feeding the test are static because we know there's certain types that we want.

[00:43:54] **Tim:** We're not actually going to a database and pulling it because, you know, a database is inherently dynamic and changes. I don't want, I don't want the underlying data that I'm feeding into my test to change. I want to know that if I send a Noel that it's gonna fail. You know? That it shouldn't be No. And that if it's in this information, it should pass.

[00:44:14] **Tim:** So, I, I don't, I just, I don't get that. You're using the database for

[00:44:18] **Carol:** Because, let's be honest, how often do you change a data type after the column's gone into production?

[00:44:26] **Ben:** Yeah.

[00:44:26] **Tim:** I, I changed one today.

[00:44:28] **Ben:** Shut up Tim

[00:44:30] **Carol:** it's very rare, right? So

[00:44:32] **Tim:** It is rare.

[00:44:33] **Carol:** it's more likely that you add a new column with the new data type you need, you convert over and then that's just gone. Or it's, you know, left there for ar Yeah, or it's just left there for an archive type process to see what it looked like before the conversion.

[00:44:49] **Carol:** So I don't, I don't see a point in checking data types when it's like a database row

## [00:44:56] Not Testing the Library

[00:44:56] **Ben:** All right, so, so let me get a little crazier here and, and, and go back to this idea of,

[00:45:02] **Carol:** It's possible you guys.

[00:45:04] **Ben:** of not testing the library. And if you think about how a lot of the modern front end frameworks work, there's state, and then there's the H T M L that get rent that's rendered because of that state.

[00:45:19] **Adam:** you're talking about declarative ui.

[00:45:21] **Ben:** Yeah, like I'm taking an array of values and I'm translating it into list items in a unordered list, or I'm taking, you know, this, state and I'm translating into a an H one tag. This is like, you gotta squint pretty hard to understand what I'm saying here, but I can understand testing the state of the application.

[00:45:43] **Ben:** Like I have an array of, dogs and I, and I call the add dog method and it adds a new name to that array. I can then understand, okay, let me make sure that that array now has, you know, n plus one items and it wears previously. Had an to then also want to turn around and say, okay, and does the rendered html also reflect the name of that new dog?

[00:46:10] **Ben:** I feel like that's, of course, that's what's gonna happen assuming you have the HTML for it. Like if I have a repeater and the repeater is bound to that array, anytime I add something to that array, it's

[00:46:23] **Adam:** You just said it yourself, you just said it yourself. If you have the, the code that does it, you're testing to assert that the code is properly hooked

[00:46:30] **Ben:** who is gonna take out the html?

[00:46:33] **Adam:** Some, some jerk holes are gonna drive by and delete stuff.

[00:46:37] **Tim:** I, I would say, I mean, maybe I'm wrong here, but I mean, this seems a little bit like, too much internal knowledge on the test.

[00:46:44] **Adam:** Hmm. So

[00:46:46] **Tim:** To me,

[00:46:47] **Tim:** to me, a test should, should, should, should sort of test a black box, right? I put, put something in, and here's what I expect to come out. That step in the middle where you're checking to see if there's n plus one on the array.

[00:46:58] **Tim:** I don't care.

[00:46:58] **Tim:** about what, what I care about is what's the name of the dog. So that, that first step mental step is useless. Check, check what the HTML is. You're using internal knowledge. Well, I should have an array now.

[00:47:09] **Adam:** So, I wanna, I wanna kind of maybe reframe around a different, Say you're building a, a calculator like on, on a webpage, right? You're, you've got, a visual calculator like that calculator app and an iPhone, right? So you've got number buttons and a, you know, plus minus, divide, clear, all that, right? And you've got a display of digits.

[00:47:28] **Adam:** So you're, you, what you need to do is make sure that the calculator works. You need to have tests that prove that the calculator is functioning. And the point of UI tests is not to prove that the logic of the the UI code works. The point or the way that you should be thinking about these tests is, as a user, I wanna be able to press three plus five, enter and see eight, right?

[00:47:54] **Adam:** So you, you write a test that presses three, then presses, plus then presses five, then presses enter

[00:47:58] **Carol:** and, you expect that

[00:48:00] **Adam:** and assert that eight is in the, the display, right? And so that involves a bunch of UI interactions. and yeah, I, again, I think it would be asinine to say, assert that the seven key exists, not just because we're not touching the seven key in this, thing, but because, that's just like a, that, that's sort of a primitive of the ui.

[00:48:18] **Carol:** You just assume that it's there. Right. This is where a snapshot test would be good.

[00:48:24] **Ben:** No, no, sorry,

[00:48:26] **Carol:** It would never

[00:48:27] **Ben:** But, but this, this is,

[00:48:28] **Adam:** Oh, oh yeah. Of the, of like the, the boot up

[00:48:31] **Adam:** ui, right? Yeah. Yeah.

[00:48:32] **Adam:** You've got all your different numbers and everything. Yeah, I agree.

[00:48:35] **Ben:** but I think about, and, and this is very particular to how maybe I approach development for UI stuff. I will oftentimes, if I have, you know, I'm trying not to use framework specific code, terminology. So if I have a, let's call it a code behind and then a, a rendering for that code behind, I will oftentimes, when I'm building out a.

[00:48:56] **Ben:** Just get all the logic in the code behind first and like I won't have any real CSS applied to the front end. Like it'll just be the minimal amount of, of HTL markup that I need to give me buttons that I can click to call back to the code to make sure that the code's actually doing the thing that it's supposed to be doing.

[00:49:16] **Ben:** So I can imagine getting to a feature complete, but not a good user experience state within the application and want to test that and then not care at all how the H T M L evolves. You know, once I put on my design hat and I'm like, oh, I need this to be a, a flex box, some rounded corners, and I need to have this, should,

[00:49:38] **Adam:** You care that the buttons are still there, that when you click on the buttons in a certain sequence, you get a certain

[00:49:43] **Carol:** happen.

[00:49:44] **Adam:** Yeah.

[00:49:44] **Ben:** I don't, I don't

[00:49:45] **Tim:** Otherwise the, otherwise the program doesn't work.

[00:49:48] **Carol:** what what did you, wait, can I go back? What did you call it? You said front end and what else

[00:49:53] **Adam:** Oh, a code behind it.

[00:49:54] **Adam:** It's a, it's a

[00:49:55] **Adam:** uh, like a C sharp

[00:49:57] **Carol:** term

[00:49:58] **Ben:** No, I'm trying, I'm trying not to say like,

[00:50:01] **Carol:** backend?

[00:50:02] **Ben:** angular controller or something like

[00:50:04] **Carol:** like, I, I don't know what it

[00:50:05] **Adam:** It's a, it's a term that I'm familiar with from like back in, like the c sharp.net days. Yeah. So you've got your, like, you've got like, so think of it like, something that, that the four of us are all gonna speak the same language on would be like ColdFusion, right? So you have your CFM template, that's, that's just a bunch of HTML logic with some, some CFML, you know, ifs and, and loops and whatever to, to format the html.

[00:50:27] **Adam:** And then you've got like a CFC that does all the data, massaging, pulling from the database, whatever. And it feeds all the data into the cfm. The CFC is the code behind that Ben is talking about. It's, it's all, it's all, it's all logic, no display. And the, the, the rest of it is the display and hopefully minimal to no logic

[00:50:48] **Adam:** or display only

[00:50:49] **Ben:** Yeah, sorry, I'm trying not to get people attached to a particular framework as they're

[00:50:53] **Ben:** thinking about it.

[00:50:55] **Carol:** Yeah, I get it. I just didn't understand

[00:50:57] **Ben:** Yeah.

[00:50:57] **Ben:** But so Adam, the fact that you bring up ColdFusion, which

[00:51:01] **Ben:** is obviously awesome. No

[00:51:03] **Adam:** It.

[00:51:04] **Carol:** now that

[00:51:04] **Carol:** you mentioned

## [00:51:05] Testing UI

[00:51:05] **Ben:** it does, it does beg the question that the conversation so far has been at least initiated by the context of front end testing.

[00:51:14] **Ben:** And I'm wondering, there are applications that we can write where there's the front end. There is front end, but the front end's not dynamic. You know, to what you're saying, we could have a ColdFusion controller that just does CFS and CF loops and outputs static h well, not static, but it outputs html.

[00:51:30] **Ben:** That doesn't change once it hits the client.

[00:51:32] **Adam:** right?

[00:51:33] **Ben:** and I'm

[00:51:33] **Adam:** Like the days before modern JavaScript. Yeah. Go ahead.

[00:51:36] **Ben:** exactly. And, and I'm wondering, in those days did people test the output generated by their cfml or is that,

[00:51:44] **Ben:** is that more

[00:51:44] **Adam:** of Selenium ide?

[00:51:45] **Carol:** Yes. I was about to say Selenium did that very slow. Yeah.

[00:51:50] **Adam:** Yeah. It was basically like you've seen like maybe Cyprus now. There's a bunch of

[00:51:54] **Ben:** yeah, I've heard of Cypress.

[00:51:56] **Adam:** so yeah, it, it's just a little thing that. , like kind of drives the browser for you. You can kind of think of it as like a robot that's sitting at the browser clicking and waiting for

[00:52:04] **Carol:** Actual clicks.

[00:52:05] **Adam:** and and looking for things.

[00:52:06] **Adam:** Yeah. And it's like, it's literally like interacting with your browser and you can watch it. It's automating, interacting with the

[00:52:12] **Ben:** And you can, like, can't you like record the clicks that you do and then have 'em

[00:52:15] **Carol:** That's what you have to do. That's actually what you have to do as you record it. Yeah. It's very slow.

[00:52:20] **Ben:** I, I know of those,

[00:52:22] **Ben:** but I, I've only really seen them discussed in the context of single page applications. But maybe that's just because like everybody's building single page applications these days.

[00:52:31] **Ben:** But so, so, so not to get too sidetracked there, I, I'm wondering if people feeling the need to test the generated H T M L, is that something that has always existed or is that something that is more prevalent with rich client side applications?

[00:52:50] **Adam:** I think that it's impossible to answer your question, but because I think that. Maturity of, the profession of developing websites has, sort of paralleled the tooling, right? So I'm sure that the, in the beginning, people who came from, you know, cobalt or, or whatever, more structured programming environments where they were familiar with doing a lot of testing, if they started working on the web, they were like, well, how do I do tests?

[00:53:16] **Adam:** Well, you, you just look at the code like, okay, well fine. If that's the only way that I can do it, then that's what I have to do, right?

[00:53:22] **Tim:** F

[00:53:22] **Adam:** email. Yeah. , view source, that's your testing framework. and so

[00:53:27] **Ben:** Sorry.

[00:53:27] **Tim:** There wasn't a lot of testing and dream weaver back in the day.

[00:53:31] **Adam:** front page, anyway, so like, I don't know, I've kind of lost the thread in my mind here, but I think that in general, people's skills around testing have kind of, or I'll, I'll say the broader. Communities skills in testing have kind of paralleled the tooling that's available. And so as the tooling gets better, then the community gets better and it kind of, seesaws back and forth. So, before we close out, we're, we're running a

[00:53:57] **Ben:** yeah, yeah. We're, I'm

[00:53:58] **Ben:** good.

[00:53:59] **Adam:** on time here.

[00:54:00] **Ben:** What I heard from this is that I've been right about everything

[00:54:02] **Adam:** uh, you've

[00:54:04] **Ben:** continue to

[00:54:04] **Tim:** I was just,

[00:54:05] **Carol:** Yes.

[00:54:05] **Ben:** to operate under such assumptions.

[00:54:08] **Tim:** Plus keep, keep in mind we're looking at through your lens and your lens is very, very biased. I'm pretty, I'm pretty sure if we talked to your teammates, they would like give us an earful right now.

[00:54:18] **Carol:** Um,all of our tests.

## [00:54:22] Flaky Tests

[00:54:22] **Adam:** So we talked about brittle tests. We talked about a bunch of different things. I, we only barely touched on mocking, and that's kind of a whole separate conversation. But something that I, I think I wanna be careful to point out here is that there's other problems too. So, like, the one that stands out for me is flaky tests, which it sounds like maybe should.

[00:54:40] **Adam:** lumped in with brittle tests, but for me, they're separate. So I consider a test flaky if it passes sometimes and fails sometimes with, you know, and all you do is like rerun the tests, right? If sometimes it passes. Sometimes I had tests like that, that would occasionally let, let's just be real here.

[00:54:58] **Adam:** It would occasionally pass, and most of the time it would fail because the, like, it was trying to build a docker container with some CFML code in it and then run our tests against our app. And one of the steps in the docker container build was like hitting some apt get. you know, install some dependencies for Linux thing and whatever it was trying to do, like maybe three or three and a half times outta five, it would fail to do that.

[00:55:22] **Adam:** And so the container build step would fail, and so the tests would fail. So like, you know, you, every time you're pushing, up to your branch on GitHub, the, the tests are running and like three outta five times it's failing. And you're like, but I know it's fine. At that point, the tests become completely pointless because nobody's, it's all, it just becomes noise and nobody's gonna care anymore.

[00:55:41] **Adam:** So nobody looks at the tests. And so then when the tests start failing because the code's actually broken, then, then you're screwed because you didn't know it, even though you had the tests there to tell you.

[00:55:49] **Carol:** Yeah. Another

[00:55:50] **Carol:** exam, another example of a flaky test is a lot easier to understand than docker containers is. imagine the test runs and the very first thing it does is gets the date right now, and then it does a date compare at the end. But the clock's rolled over at midnight or the clock's rolled over one minute.

[00:56:07] **Carol:** And depending on what your date compare is, it'll fail. But when you run it again, it catches it within the same seconds. And yeah, we had lots of those. I'm like, fix them. This is so easy.

[00:56:17] **Tim:** Hmm.

[00:56:18] **Adam:** And, and to your point earlier, Ben, like one of the first things you said was that the tests take, you know, 10, 15 minutes to run and that, that, that was bananas to you. And I, I agree. You know, the, the faster the tests run, the more likely people are to use them and to contribute to them and to, to look to them. I, I I agree that 10 minutes is probably too long, but I have heard plenty of stories of tests that like take 10 hours or 30 hours to run. I mean it when your tests take more than 24 hours to run that is, that's I think where you're officially in bananas territory. That's where you cross the line from, from Gonzo into bananas, , and.

[00:56:58] **Ben:** and I, I wonder if the slowness is in somehow a byproduct of the fact that the UI stuff is being tested. I think maybe Tim a moment ago said tick, and I don't know if this is what he was referring to, but there are, there are a lot of things I think where you have to set up the state.

[00:57:14] **Ben:** and then you have to either wait for like the next tick of the clock for all the data to be reconciled with the H T M L. And you know, if you're doing that in one place, it's instantaneous. But if you're doing that over hundreds of tests, you know, that actually can start to, to to, to add up, I guess.

[00:57:29] **Tim:** I was talking about the ColdFusion CF tick, where you just count the ticks between the clock rather than worrying. The Datelines between midnight and whatever,

[00:57:37] **Ben:** gotcha. Gotcha.

[00:57:38] **Adam:** is that only available in Tag Islands?

[00:57:43] **Tim:** yo, don't even get me started on that weird tag on and stuff that.

[00:57:47] **Ben:** Yo, I'm sorry. I like. CF query to me will forever be the most amazing thing ever invented. And I swear I look at people's code reviews at work and they're using these ORMs to programmatically piece together SQL statements. And it's like half of the code is the SQL and then the other half of the code is like all the noise from calling the different methods that make the SQL statement.

[00:58:14] **Ben:** And I'm just like, people

[00:58:17] **Adam:** So

[00:58:17] **Ben:** like we already solved this problem in CF Query. I don't know why everyone's making it so much harder.

[00:58:22] **Adam:** I think you can be right about the second half without being right about the first half, and I think that's the case here.

[00:58:32] **Ben:** Good times. Anyway, I appreciate, I appreciate you. Let me dive into tests again. It will forever be

[00:58:38] **Tim:** We're just happy you're putting your toe back in. Let's say, you know, talk to your team. You know, find someone like can mentor you.

[00:58:46] **Adam:** And we'll do it again in another 60 something episodes.

[00:58:48] **Ben:** There you

[00:58:49] **Tim:** Yep.

[00:58:50] **Tim:** And you'll be the first

[00:58:52] **Carol:** maybe consider running your code locally.

[00:58:55] **Tim:** Yes, for sure. Figure that out. That's what it's meant to do.

[00:58:59] **Adam:** Alright, well I guess that's, gonna do it for us tonight. We are about to go record our after show tonight on the after show. We're gonna talk about G P T four. There's a new version of it out. and apparently we're gonna talk. Did it pass a capture? Maybe sort of. I don't know if anybody else has heard this.

[00:59:13] **Adam:** I, there was a, a podcast that one of our listeners suggested that I listened to and I did, and a lot of interesting stuff in there. And, I think Tim, it was, you added this on here. So who is working only three hours in five months? Is it you? It you, Tim, we're gonna find

[00:59:26] **Tim:** I wish. I wish

[00:59:27] **Tim:** we'll

[00:59:27] **Tim:** find out.

## [00:59:28] Patreon

[00:59:28] **Adam:** but first, as always,

[00:59:30] **Tim:** . This episode of Working Code was brought to you by asinine tests. you know, gotta make sure that that tab is in the right location. And listeners like you, if you're enjoying on the show and you wanna make sure that we can keep putting more of whatever this was out into the universe, then you should consider supporting us on Patreon.

[00:59:43] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks of course to our top patrons, Monte and Giancarlo. If you wanna help us out, you can go to patreon.com/WorkingCodePod

## [00:59:57] Thanks For Listening!

[00:59:57] **Adam:** your homework this week. Obviously we're having lots of great discussions on Discord and you don't wanna miss out on that.

[01:00:02] **Adam:** So you wanna go to workingcode.dev/discord. It's just like Slack only better workingcode.dev/discord.

[01:00:11] **Tim:** It's developer therapy guys.

[01:00:13] **Adam:** Oh, it really is. It's great. Great place to spend the day. Well, that's gonna do it for us this week. We'll catch you next week and until then.

[01:00:19] **Tim:** Remember, your heart matters. Even your tests are a little bit flaky. It's okay. Your heart matters.
