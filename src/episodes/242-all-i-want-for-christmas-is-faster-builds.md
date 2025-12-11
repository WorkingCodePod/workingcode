---
title: "242: All I Want for Christmas Is Faster Builds"
description: "It's that time of year—each host reaches into Santa's sack of topics to see who's been naughty and who's been nice."
date: 2025-12-11
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/d2369e02-0414-446d-bbbd-ddeb01501656"></script>
<div class="redcirclePlayer-d2369e02-0414-446d-bbbd-ddeb01501656"></div>

It's that time of year—each host reaches into Santa's sack of topics to see who's been naughty and who's been nice. Ben returns from visiting his employer's manufacturing headquarters in Georgia with some philosophical musings. Carol is on a mission to slash CI/CD build times. Adam has cautiously optimistic news about passkeys finally working (sometimes). And Tim reflects on a TLDR article suggesting that the management skills you've built—knowing what to build and what _not_ to build—might be exactly what AI-era coding demands.

Plus: December blues, mushroom tea for focus, and jQuery as peak imperative JavaScript.

Links mentioned:

- [Owning A Lucid Has Been Super Disappointing](https://www.youtube.com/watch?v=1WiQAOmESH0)
- [Driving Xiaomi's Electric Car: Are we Cooked?](https://www.youtube.com/watch?v=Mb6H7trzMfI)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/242-all-i-want-for-christmas-is-faster-builds.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** So when it says co-authored by, and it's an LLM, I go, okay, I have to review this one and make sure it's right because I don't trust it.

[00:00:07] **Tim:** Notice how Ben turned. I can do an AI episode.

[00:00:10] **Adam:** Yeah,

[00:00:11] **Ben:** Hey, you all had started the AI talk. I was just piling on.

[00:00:16] **Adam:** so obviously Ben was pretty naughty this year.

[00:00:19] **Carol:** Nty. Nty Nty.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 242. And on today's show we're gonna reach into Santa's sack of topics and we're gonna find out who's been naughty and who's been nice and talk about it. but first as usual, we'll start with our trams and fails. Looks like it's my turn to go first. So, going first is what I shall do.and my name is per haply. nobody got the joke. Sorry. That was a parks and rec joke. Anyway.

## [00:01:04] Adam's Triumph

[00:01:04] **Adam:** I'm gonna start us off with a triumph. I've talked recently about my SvelteKit app that we're working on at work, and how we were trying really hard to make it hit production for end of the calendar year, and it's looking like that's gonna happen.

[00:01:17] **Adam:** it went to QA I think, very late last week, maybe like first thing this week. and, you know, just iterating on it, you know, like first hands on it from outside the development team and, and, get some, feedback and starting to iterate. And it, the, the, the crazy part is I feel like we're dragging our feet, although I know we're not, right.

[00:01:37] **Adam:** What's making this difficult is that it is extremely customizable. Like we've, we've kind of built a design system for this thing, and the design system is built in a way to allow us to have settings in admin where the. The school staff can say, okay, well these are our color palette and, you know, we want this sort of look and feel.

[00:01:58] **Adam:** do, do they want things to be more rounded or more square or maybe somewhere in the middle? And, that sort of stuff. And, and it like applies that site-wide on the new app. and eventually the, the, boundaries around the new app will grow and grow and totally consume the old app as well. But, it's, it's hard to think about that kind of work.

[00:02:19] **Adam:** You know what I mean?

[00:02:19] **Ben:** So are you, you have database driven customizations of CSS, right? Is that what I'm understanding? So are you doing like a, is there some sort of touch point where you're merging database values into CSS custom properties or something?

[00:02:38] **Adam:** It's pretty much exactly what we're doing. Yeah. So we have a bunch of components that are, you know, Svelte code that use a bunch of CSS custom properties. Which is the worst name for variables

[00:02:48] **Ben:** I know, right? I, I only use the term CSS custom properties to be pedantic. Every bone in my body wants to say CSS variables.

[00:02:57] **Adam:** Right. And you know how you use a CSS custom property? You use the function var, uh,

[00:03:06] **Carol:** Oh.

[00:03:07] **Adam:** yeah, so, basically like we have defaults, but then we have some, I forget exactly what it is. It's, I guess it's just like part of the, the root layout or something pulls in some code that just spits out a chunk of CSS that overwrites the default values for all of these, CSS custom properties with, that the theme for that particular customer. And

[00:03:31] **Ben:** Very cool.

[00:03:31] **Adam:** it, it cascades down, shockingly enough.

[00:03:35] **Ben:** This is where picking names is just so tough. I, I, I find it tough. I don't wanna speak for anyone else, but this is, it's, it's not just like picking a standard variable name that is somehow local to a function and kind of easy to reason about. You really have to have an eye towards the future and like how this variable might be used.

[00:03:54] **Ben:** And I know a lot of people just, I don't wanna say give up because I obviously don't wanna throw anyone under the bus, but a lot of people will just pick a variable and call it red because the first approach to it is red, but then later on it's actually purple. But they just still call it red. And red is actually really just a primary color, but everyone calls it red kind of a thing.

[00:04:12] **Ben:** it's, it's something I struggle with, greatly. And, uh, I hope you're having better success.

[00:04:18] **Adam:** You know, even, even if you spend a lot of time collaborating to come up with good names on things, the name is only good until you have something else that like, you know, six months later. Something comes along and it's like, oh yeah, that has way more of a claim to that name. And so now we have six months worth of legacy code that uses this name, and there's no way we're gonna go through and change all of that.

[00:04:42] **Adam:** So it's, it's naming things as hell.

[00:04:45] **Ben:** It really is. And Google's Material Design, I think did a lot to lay the foundation for how we think about these things. And they, I mean, I'm sure other people had prior art, but Google Material Design was really the first publicly, showcased design system that I saw that had huge adoption. And I, and that was the first time I had seen terms like primary color, secondary color.

[00:05:12] **Ben:** Texts, fills, backgrounds, surface surface, one surface alternate, and like even reading through their docs, which are way too big, it really tests the limit of my ability to focus and concentrate. And I feel like I usually have pretty good focus, but the names like, they don't even feel meaningful enough somehow.

[00:05:31] **Ben:** You know, like surface alt or like surface highlight. I, I don't know it like, you really have to be the one almost designing it to really understand what they mean and not just what they mean, but the extent to which that name is meaningful and should be applied.

[00:05:47] **Adam:** Yep.

[00:05:48] **Ben:** sorry. This, there's a little mini rant there.

[00:05:49] **Ben:** It's hard.

[00:05:52] **Adam:** Yeah, I mean, it, it's on the list, right? Naming things, cash in validation and off by one errors.

[00:05:58] **Tim:** Two hardest things in programming

[00:06:00] **Adam:** That's right. So that's what I got going on. How about you, Ben? What do you got going on?

## [00:06:04] Ben's Triumphs

[00:06:04] **Ben:** I'm gonna go with, two triumphs, one, one sort of big and one sort of tiny, 'cause I missed, yeah, I missed last week. You, you punks went and talked about exciting AI without me. So this is my retribution.so I wasn't here last week when you guys were having fun talking about ai, and that's because I went down to Suwanee, Georgia, which is the corporate and manufacturing headquarters for PAI, the company I work for.

[00:06:27] **Ben:** And, it was just really awesome. I have to say, I, I wasn't like terribly looking forward to it because, you know, I live in my house and I never put shoes on and, I don't speak to people and I haven't sat at someone else's desk in 13 years. but I went down and. It's just a really, really impressive operation.

[00:06:49] **Ben:** PAI, they walked me through the manufacturing plan. They were showing me all the robotic cells for gear grinding and polishing and deburring and, and the, these heat treatment stuff and, and laser marking. And they,

[00:07:04] **Tim:** make.

[00:07:05] **Ben:** they are an aftermarket truck engine parts manufacturer. So they don't, they don't build, the engines for things like Toyota, but they will build replacement parts for the engines that Toyota makes kind of a kind of a thing.

[00:07:24] **Ben:** I'm not explaining well 'cause I'm still trying to understand it, but, it was just really, really cool to go around the manufacturing floor and see how everything was made and then seeing, they have a whole warehouse, massive. Apparently they have Several additional warehouses they didn't even take me to.

[00:07:39] **Ben:** But just these inventory warehouses where it's, you know, everything is, it's like walking into a Home Depot and you're like, oh, aisle 27, row three lot or like box four a and they have these vertical lift machines, like these giant, you know, vending machines for parts and all this packaging stuff.

[00:08:00] **Ben:** And I'll tell you, I, I was not just inspired that it's very cool business, but I was inspired by the sort of American dream of manufacturing. There was something magical about being in a place where stuff is built and, and you can see it, and you can feel it, and it has weight to it. I, I don't know, it was, it was just very, very magical, very inspiring.

[00:08:23] **Ben:** And despite the fact that I dealt with people, I had a lot of fun there. So that was my big triumph. and I, so far I have

[00:08:31] **Adam:** moving on, so Ben doesn't get a second one. Just go ahead.

[00:08:34] **Ben:** So far I have not gotten sick too, which is, you know, the other thing I always worry about when I get on planes, my little triumph is, I don't think I had mentioned this on the show, but I was mentioning this in the Discord that I was really putting off the idea of working on the response of design portion of my big sexy poems little side project.

[00:08:51] **Ben:** And I have, okay, yeah. So I've finally taken the plunge and started to attack the responsive design stuff and, I don't know, I just feel like I'm doing the right thing as opposed to just continuing to put it off forever. it's not easy. I don't love it and I don't enjoy it and I don't necessarily know what the definition of done is.

[00:09:09] **Ben:** We talked, I think, yeah, you're right. On the previous show we talked about responsive data grids. I ended up just going with the, the thing I think, Adam, you were talking about where you just put a, a div around it with a horizontal overflow scroll. And that's just how I'm gonna deal with it for now. I'm, I'm not gonna try and get fancy with hiding and showing.

[00:09:28] **Ben:** Table cells and then recreating portions of the data grid as just properties within an additional cell, et cetera, et cetera. but I just feel, I feel good that I'm, I'm taking the plunge and actually trying to attack that problem instead of continuing to kick the can down the road. Boy. All right. So that is me.

[00:09:45] **Ben:** Carol, what do you got going on?

## [00:09:47] Carol's Fail

[00:09:47] **Carol:** Well, I am gonna go with a fail. I just have the blues right now. It is that time of year I think, where the sun just doesn't show long enough and suddenly the workdays feel like they drag on forever. 'cause I go in my office and it's dark. I leave my office and it's getting dark again. So I'm just like, and it's cold.

[00:10:09] **Carol:** I hate when it's cold and my fingers are cold and I can't type on my keyboard 'cause my fingers are so cold. And it's just, it's, it's a whole thing, right? So I've ordered some, mushroom tea to try to help in the afternoon to see if it helps with focus and also just not feeling so blue. But I am ready for summer again, and hopefully that comes soon.

[00:10:32] **Tim:** official winter.

[00:10:34] **Carol:** and I don't even have winter like everyone else, like I'm complaining. But it's 70 degrees here during the day. Still. It's just at night. At night. It. Yeah, it's the darkness and it does get so cold during the night. 'cause we live in the desert. So this dry cold is something I've never really had to deal with until the last three years.

[00:10:54] **Carol:** And the dry cold is completely different than what I'm used to in Georgia. There's no humidity and it just, it cuts you, it's not fun.

[00:11:03] **Tim:** What's your mushroom tea that you're taking?

[00:11:06] **Carol:** So I think it's Lion's Mane, brand is Rise. There's, yeah, it's good for cognitive stuff. I also am excited just to have something warm in the afternoon to drink. And since I have ADHD I'm hoping it'll help a little with that focus too. So we'll see how it goes. I've not ever tried it before, but it has good reviews.

[00:11:23] **Carol:** Lots of people suggest it, so yeah.

[00:11:26] **Adam:** pro tip, when you're taking stuff like that to help with your memory, it's best if you remember to take it.

[00:11:33] **Ben:** That's how they get you. I don't know if anyone else has been having winter allergies. I have never had winter allergies before, but I have just had something up in my face and like my nose and sort of my throat a little bit for the last month. I don't know if it's the heat kicking on and I don't know, just something dust in the air or if it's something outside plant wise.

[00:11:58] **Ben:** But

[00:11:59] **Tim:** This last time you changed your air filters.

[00:12:01] **Carol:** I was gonna ask the

[00:12:02] **Ben:** I don't know. I mean recent, not, not like, not like years ago, but you know, probably in the last couple of months, I'm sure

[00:12:09] **Carol:** this your first winter in your house?

[00:12:11] **Ben:** Third, second, third, third winter, something like that.

[00:12:15] **Carol:** So if it were in events, you probably would've known about it last year.

[00:12:19] **Ben:** Yeah, I don't remember it being like this last year. So then I'm also wondering, maybe it's something I've been eating, but I've just also, I feel like I'm operating at 80% right now

[00:12:29] **Carol:** Oh no.

[00:12:29] **Ben:** I, and I don't love it.

[00:12:31] **Carol:** Oh,

[00:12:32] **Tim:** Less 20% more than most people. So

[00:12:36] **Carol:** Well, that's me. what do you got, Tim?

## [00:12:38] Tim's Fail

[00:12:38] **Tim:** mine's very similar to yours, Carol. I just, yeah. I got the December Blas and, and some of it's the weather 'cause it is actually cold here. Right. We're ha we've been having cold snaps in Georgia and getting down into the thirties, which I hate. kind of just gray overcast days. But it's, it's more the fact that it's like. I can't really plan my work because like my customers, I was like, okay, this week I'm gonna do this. And then I like send an email to, you know, some customers and they're like, oh yeah, half our team's off this week, so we're just gonna postpone everything the next week. I'm like, great. So I'm, I'm at work, but I can't work and I just can't take off.

[00:13:17] **Tim:** I can't take off either. I don't wanna look like a loser, but it's so it's yeah, I'm in this kinda limbo state of just staring at my email going, do the thing, do the thing, gimme something to do because there's plenty of things I need to do, but it's like, it, there's all these like people I gotta wait on and a lot of these people are just like, oh yeah, I'll be back next week.

[00:13:40] **Tim:** Or, you know, I, I'm sick or whatever. So, yeah, it, I'm just like, can we just call this year over now? Let's just, just stick a fork. Can everyone just take the rest of the month off?

[00:13:50] **Adam:** you got my vote.

[00:13:52] **Tim:** get paid double

[00:13:54] **Adam:** Yeah. Heck yeah.

[00:13:55] **Tim:** yeah, little, little extra

[00:13:57] **Tim:** December bonus and do no work. I'll be happy with just a hundred percent of my normal salary.

[00:14:04] **Tim:** So,

[00:14:05] **Carol:** it's funny you say that because. Early on, I mentioned you guys. We were, you know, government employees. There were a lot of cuts going on. So people who remained decided to not take vacation. So a lot of people who have tenure at the at at our agency held a lot of their leave thinking that if there was a worse case that Lisa leave would get paid out in addition.

[00:14:29] **Carol:** Right? So then we hit November and all these people have just disappeared because now they have use or lose time. So now they're forced to either lose their time or take it off. So they're just gone, their emails are like, see you January 4th, and I'm like, oh, that's like 45 days. Yeah,

[00:14:50] **Tim:** Reminds me, I need to check my, see if I'm gonna, I need to take some time off before the end of the year so I don't lose it.

[00:14:55] **Carol:** Don't lose it.

[00:14:56] **Tim:** they really should give you the option. If you don't, you know, if you're gonna lose it, they should pay it out to you.

[00:15:01] **Carol:** I agree. You've earned it.

[00:15:02] **Tim:** You know, they, because if you just keep it on the, 'cause we went through this, the company policy prior to us getting bought out was, we just kept it on the books and I had three, 400 hours worth of time.

[00:15:13] **Tim:** And then they're like, oh, we, you know, that actually shows up as a liability on your book. So when you have you know, 70 employees with all this extra, you know, that, that looks bad on your books. we need to cap this at 80.alright, well just, just give us a payout.

[00:15:27] **Ben:** Right,

[00:15:28] **Tim:** if, if it's a financial burden on the books, just go ahead and take the hit and give it to us.

[00:15:33] **Ben:** There's a solution.

[00:15:34] **Tim:** There's a solution. They're like, no, we're not gonna do that.

[00:15:37] **Adam:** Why would we do the thing that actually is beneficial to you and fair for us when we could just do the thing that's beneficial to us and screws you?

[00:15:44] **Tim:** exactly. Yeah. Hey, welcome to Corporate America.

[00:15:46] **Carol:** Well, I will counter a little though. I think it's kind of good 'cause it does force you to take breaks. It says, okay, if you value your time and money enough, then you're going to use this time off to go away from work. You're gonna step away and do your reset because you, taking a mental res reset typically helps the company overall.

[00:16:07] **Carol:** 'cause you're not gonna be as stressed. You're gonna, you know, come back motivated, most likely kind of refresh and they don't lose as much.

[00:16:15] **Tim:** And I get that if we were on a normal cadence, but when you're going down from 400 hours to 80, there's only so much re there's only so much resetting I can do.

[00:16:23] **Carol:** Yeah.

[00:16:24] **Ben:** right.

[00:16:25] **Tim:** I, and I went to Portugal for almost a month and I still got time. I gotta use up so.

[00:16:31] **Adam:** You poor thing.

## [00:16:33] Santa's Sack of Topics

[00:16:33] **Adam:** Well, uh, shall we see what Santa brought for us this year?

[00:16:37] **Carol:** Let's go.

[00:16:38] **Ben:** Absolutely.

[00:16:39] **Adam:** Who wants to go first?

[00:16:40] **Tim:** I believe in Krampus more than

[00:16:41] **Adam:** Okay, well, you know, uh, we'll.

[00:16:43] **Tim:** the rest of us.

[00:16:44] **Adam:** I was gonna say, we'll, we'll put up the Festivus poll and you can air your grievances andyeah. Who wants to go first? Who wants to open their present first?

[00:16:51] **Carol:** Plenty of you guys take it off.

## [00:16:53] Software Artifacts vs. Art Evolution

[00:16:53] **Ben:** Alright. I, I'll go first as soon as I wasn't here last week,

[00:16:56] **Tim:** Hey, keep playing that card.

[00:16:58] **Ben:** yeah. All right. That's the last time.before the show, we were just doing our little pre-roll chit chat and, one of the things that I was saying was how one of my North stars is that I look at old code and it still continues to embarrass me, which makes me feel like I'm continuing to fine tune the way that I think about software development and application architecture.

[00:17:20] **Ben:** And that reminded me of a thought that I actually had over Thanksgiving.we did double Thanksgiving, so we did Thanksgiving up here in the northeast with my family, and then we went down to Maryland to be with my wife's brother and his family. And, they lived down in Maryland. So on the way back we decided to stop off in Philadelphia for the night just to break up.

[00:17:40] **Ben:** It's a six hour drive between the two places, so it breaks it up nicely. And we ended up going to the Barnes Foundation Museum. And, I don't know anything about museums I don't like, I'm not like a Super Museum fan. I just like looking at pretty pictures. That's like my mode of absorbing. So I'm just sort of wandering around this foundation and looking at the art and a lot of stuff is very beautiful.

[00:18:03] **Ben:** And I walked by this tour that was happening and I was, you know, eavesdropping on what the tour guide was saying. And there there was, you know, works by really famous people like Renoir and, and Picasso and, uh.Monet just, I mean, I can't believe how they don't have this stuff locked down, whatever.

[00:18:22] **Ben:** Anyway, so I passed by this tour guide, and the tour guide is talking about the artifacts in this. I think, I'm pretty sure it was a Picasso painting and saying, oh, you can see in this part that the Picasso had actually the arm outstretched, but you can see that he painted over it because he didn't wanna do that.

[00:18:39] **Ben:** You can see that this portion of the painting is reminiscent of the Roman statues because that was the type of art that he was studying at the time. And it, it, it struck me that there could be an interesting parallel there between the way we look at the artifacts in artwork and the way we look at artifacts and software.

[00:18:58] **Ben:** And the fascinating juxtaposition for me is how when people talk about it in the context of artwork, I feel like it's always in a very positive light. This is the phase that, that the artist was going through. This was the blue phase, this was the, the surreal phase. This was, you know, this phase and that phase, and here are the influences.

[00:19:17] **Ben:** And it, it always feels like it's a very positive, very organic, very, yeah, exactly. But I think when we take that same lens and point it towards software and our own software architectural journeys, I feel like it's much more through a negative lens. here are all the mistakes that I made, and here are the, I just learned about this design pattern and suddenly I wanted to use it everywhere.

[00:19:46] **Ben:** And how much of a mistake that was and, oh, I can't believe I decided to use this JavaScript framework. And it ended up not being the one that the market chose and how much of a waste of time that was. And oh my God, I can't believe I started to use this database. And it turns out to be more complicated.

[00:20:01] **Ben:** It doesn't have asset compliance. I don't know. It, it feels and maybe I can only speak for myself here. It feels like we don't take enough joy in the journey and the, the growth, and it just seemed interesting to see the comparison of, of artwork that's considered to be masterpieces and, and how software, just is much more critical.

[00:20:25] **Tim:** I get where you're coming from. I mean, it kind of resonates. I think that, you know, 'cause like you said,Picasso in his early phase, he got better and better and better assume assumingly, and you think, oh, you talk about his growth and his career tr trajectory and, but then you look at your old cult and you're like, oh, I was just an idiot back then.

[00:20:44] **Tim:** But you don't, you don't, you don't look at the growth, right? You don't, well, you know, he was in his, he was in his CF tag phase where everything was five tags and then, and then later he learned about CF scripting and then, you know, and look at the growth that he's made of, we just go,

[00:20:56] **Adam:** And then Galaxy Brain Tag Islands.

[00:20:58] **Tim:** yeah, tag, I look.

[00:20:59] **Tim:** Yeah, exactly. And you, so you don't look, people look at that, oh, that old code is crappy. And you, and, and I think the reason is, is because, you know, Picasso was a solo artist, right? He wasn't working in a team and people weren't inheriting his artwork to go, whoa. Woman holding a purse. This looks like you threw a sandwich down on the floor and then just stepped on it.

[00:21:23] **Tim:** I mean, I, oh, okay. That's the eyeball. Okay. I get it now. Yeah. What were you thinking? So I, I, I think that's sort of the thing. It's like you have this living sort of breathing ecosystem of code that many people have their fingers in. And if it were a solo endeavor, maybe you could say over time, yeah, I could see how I've grown.

[00:21:42] **Tim:** But it's it it, people look at that and go, they don't know where you started. Right. 'cause they only know where they're at. And so that's, I, I think that's probably the reason why.

[00:21:51] **Ben:** I think also we're much more judgmental of things that don't move faster forward or don't move forward fast enough, I guess is probably a better phrasing there. And I, I, I can't help but always go back to jQuery and that even today, if I land in a project that has jQuery in it, it feels so intuitive and easy to use.

[00:22:16] **Ben:** And there is something very luxurious about the fluent API and the way it bulk applies things to Dom nodes, and it's like there is something magical to it that, that to remove jQuery for the sake of removing it. Because modern dom APIs have rough equivalences. It's it almost misses some, the artistry of it.

[00:22:40] **Ben:** Yeah. Yeah. I, I don't know.

[00:22:41] **Adam:** I, I'll agree with you that jQuery is sort of the peak of imperative JavaScript, right? So you know, if, if I were to just like kind of intentionally be slap dash like. I, I don't, I, you know, if I'm just throwing something together for a day project or to show somebody that something's possible or whatever, yeah, I'll reach for jQuery.

[00:23:01] **Adam:** but I feel like for long-term projects, right, for something that I'm trying to run a business on or something like that, I feel like I need more sophisticated tools. So that's why I reach for, you know, React or SvelteKit or whatever. But, yeah, I, I mean, I still agree, you know, when you're there, there's a time and a place for those imperative tools.

[00:23:23] **Adam:** And when you're there, you're either, you're either doing vanilla JavaScript 'cause you need nine lines of JavaScript and no more. And that's fine. Or if you're doing something that needs a little bit more than that, then yeah, reach for jQuery.

[00:23:34] **Ben:** yeah. And I, and I guess. Like I, if I imagine if, if you were to look at a piece of artwork and someone had, let's say that someone had been doing oil painting for a long time and then they went back to doing a lot of, like charcoal based sketches. I don't know a lot about art, so I'm sort of talking out the side of my mouth here.

[00:23:51] **Ben:** You know, you could say, oh, well this is such a unsophisticated medium compared to paint. I mean, I'm not saying, I'm not saying people would say that. I'm just trying to draw some sort of a comparison. but you, I, I think in, in the world of art, you wouldn't say that. You'd say oh, this person is trying to do something different.

[00:24:06] **Ben:** Or like the, they're exploring different mechanics or they're, they're in, you know, trying to figure out how to use the shadows and the shading to illustrate the emotion of the sketch as opposed to the richness of the colors that you would get with oil painting. there's something beautiful to be taken out of each medium.

[00:24:23] **Ben:** It's not that there is one right medium to make art with, and I almost wish that. If, if no one else but myself could learn to appreciate the beauty of the medium of software development as opposed to just always feeling a little shame that I'm not doing the right thing all the time. I feel like that would just help me mentally and help me enjoy the work more and, and have more just delight throughout my day as opposed to feeling shame about this or about that or about, you know, not learning enough or learning fast enough or learning the right things or, I don't know.

[00:25:07] **Adam:** As, as we learned in episode one, Ben, shame is, a personal choice.

[00:25:13] **Ben:** So anyway, it was just interesting. I, I, it was just an interesting mindset to put myself in at the museum.

[00:25:19] **Adam:** It's fun when something totally foreign makes you like, gives you deep thoughts about your work.

[00:25:28] **Ben:** Yeah, agreed.

[00:25:29] **Adam:** Cool,

[00:25:29] **Carol:** I feel like in general You're a deep thinker though.

[00:25:34] **Adam:** Ben? Yeah.

[00:25:34] **Ben:** It, it, it prevents me from having to talk to people,

[00:25:37] **Carol:** Yeah.

[00:25:38] **Ben:** so that's a win. It's a two-way win, Carol.

[00:25:43] **Carol:** I look at my code from months ago and I'm like, ah, I could have done that better. I don't know if I'll ever be at the point where I can just see it as growth and not as failure, so maybe down the road I'll get there.

[00:25:57] **Ben:** It's so hard.

[00:25:58] **Adam:** Well, in starting in a few months, you shouldn't have any code that you wrote a few months ago, right? It's all AI code from here on out.

[00:26:04] **Carol:** I was, I was just thinking that I was like, the real thing's gonna be in a year. I look back and I go, did I even write that or did I just commit it for an LLM? That doesn't look like my style.

[00:26:17] **Tim:** We'll, we'll know we reached, you know, general, was it AGI? Whenever the, the, the AGI goes. Oh my God. Look at this code I wrote five years ago. This is so terrible. I feel such shame deletes itself for like, yeah, okay. It reached, it's finally reached parody with human beings.

[00:26:37] **Carol:** this is when the bubble hits. Yeah.

[00:26:39] **Tim:** I can't go on knowing I wrote this code. I

[00:26:42] **Ben:** this is a little bit of an aside, but it's, it's, it's heavily related to this. When I was in the airport going down to Georgia and I was waiting for my flight, I'm walking around, I like to

[00:26:51] **Tim:** you drove.

[00:26:52] **Ben:** Th this is down to Georgia, not, this is for going down to the manufacturing

[00:26:56] **Tim:** Oh, okay.

[00:26:56] **Adam:** That, that I flew. Thanksgiving.

[00:26:58] **Ben:** Yeah, so I'm, I'm pacing around the airport terminal here, up in Albany, New York, and there's a guy on the phone and he is on a business call and he is straight up yelling at the other people on this phone call talking about how, you people are me over.

[00:27:16] **Ben:** I said, no matter what I do, if I'm nice to you, if I'm mean to you, it doesn't matter. You just sit there and you me over because you don't take any of this seriously. And at the end of the day, it's my fault if you guys screw up the orders, if you screw up this, if you screw up that, it doesn't matter because at the end of the day, it's my fault.

[00:27:37] **Ben:** And he's like literally yelling this on the phone, which is, you know, really ridiculous. But it it

[00:27:44] **Adam:** he goes to hang up Happy Thanksgiving.

[00:27:46] **Ben:** love you, mom.

[00:27:48] **Tim:** I love you, mom.

[00:27:49] **Carol:** That's a good one.

## [00:27:51] AI in Commit Messages

[00:27:51] **Ben:** But it was, I, I appre as much as I think everything about that call was probably wildly inappropriate. Like it's probably, it's not how you can talk to people, especially the people who work for you. I appreciated the fact that what he was saying was that at the end of the day, he has to take responsibility for the output of his team.

[00:28:08] **Ben:** So even if his team is operating at a substandard level, he's the one who ultimately is left holding the back. And I'm bringing this back to the AI conversation now. I am, I think it's crazy that people put that Claude wrote anything like that. There is like a Claude participated in this commit message or Claude suggested this line of code.

[00:28:31] **Ben:** I feel like the fact that AI wrote any of it is irrelevant. At the end of the day, the person who is committing the code is wholly responsible for that code.

[00:28:41] **Tim:** Yeah,

[00:28:41] **Ben:** And to even hint that AI was responsible in any way whatsoever, I feel like you're, yeah. Even if that's not your intent, I feel like subconsciously it's oh, QA will catch this error.

[00:28:58] **Ben:** And not having to worry about the quality of your own code. And I, I feel like I never wanna know that AI is actually involved in the authoring of code. I feel like that's definitely a code smell. But a you, it's a person smell, not a code smell.

[00:29:12] **Carol:** I have a conscious bias. I am absolutely biased on PRs. If they say co-authored by Copilot, I automatically dig through it. 'cause I assume it has no context of how our system works. In the big picture of things, it may understand the small context of what is changing, but did they think about how like these other packages are gonna ingest this data?

[00:29:37] **Carol:** Did it make the other changes that are needed? So when it says co-authored by, and it's an LLM, I go, okay, I have to review this one and make sure it's right because I don't trust it.

[00:29:48] **Tim:** Notice how Ben turned. I can do an AI episode.

[00:29:50] **Adam:** Yeah,

[00:29:51] **Ben:** Hey, you all had started the AI talk. I was just piling on.

[00:29:57] **Adam:** so obviously Ben was pretty naughty this year.

[00:30:01] **Carol:** Nty. Nty Nty.

[00:30:02] **Ben:** All right, who's next?

[00:30:03] **Carol:** I can go next if you want.

[00:30:05] **Adam:** Yeah, do it.

## [00:30:06] Optimizing CI/CD Build Times

[00:30:06] **Carol:** Yeah. Cool. So I am tackling this side thing at work because I want to, because it's driving me nuts and because I know it can be better. So our build times, while they got better over the past few years, they are still obnoxiously long. So when I have my solution open locally, our build times aren't too bad.

[00:30:30] **Carol:** You know, I can get everything up and running pretty quick because we have it segregated and it's very isolated on what it's trying to do. And if I need to go run other pieces, I just spin them up separately. No big deal. It's not, not too bad. However, when I do a pr, we have all these gated check-ins that happen.

[00:30:48] **Carol:** So all of these scans take place, you know, all the YAML checks, oh, I didn't even change the yaml. Like, why are you trying to run checks on files? I didn't change, which I haven't been able to isolate how to eliminate that, but I'm getting there. and then like the security scanning, are you adding vulnerabilities to the system?

[00:31:06] **Carol:** Are you adding secrets? So all of this is happening like at our gated check-in piece, which is on a pr, and it says, okay, our PR is created. Let's go run. And I'm not kidding, 15 to 22 minutes worth of, of scans per pr. To then turn around and have the deployment process repeat almost every one of those scans.

[00:31:27] **Carol:** So I was like, why are we duplicating this? if I checked it on pr, it had to pass on pr. I don't need to check it on the merge domain. I've already checked it in the initial branch that is merging. There's no reason to check it again. So if I can eliminate some of these steps, then now the developer's life is just a little better.

[00:31:47] **Adam:** yeah, I mean, we've been in a similar situation. I've been kind of hands off of it because I, I got just so frustrated with it. I just kinda walked away. I was like, you guys figure it out. at one point we disabled our test suite in the deploy workflow because for the same reason.

[00:32:04] **Adam:** they already ran in the test workflow, why do it again? Right. And then I think if I remember correctly, the problem that, like we ended up turning it back on and I think that that was because basically like integration issues, right? So like my PR passes tests, your PR passes tests when we both merge and, and go to deploy the, the, the bill breaks, right.

[00:32:29] **Carol:** So there's

[00:32:30] **Adam:** 'cause they're related or whatever. Yeah.

[00:32:32] **Carol:** GitHub has a setting that you can force the branch to be up to date before you allow it to merge. So there's a checkbox that you can turn on that says, cool, well Adam already merged, has changed. Well, now you've got a rebase or you've gotta update. It's a button or a comment that says, rebase my branch, or update my branch.

[00:32:51] **Carol:** And then it does it all over again. So I think some of that gets solved by forcing that second PR to then have to get the latest before it'll allow to be merged.

[00:33:01] **Adam:** That, that could have been the, a better solution to our problem. But yeah, like I, I'm right there with you. It seems so pointless, but at the same time I've seen it save us. So

[00:33:10] **Carol:** it ha, okay. See, I don't know if it's ever saved

[00:33:12] **Adam:** ours aren't 20 minutes either, but Yeah.

[00:33:15] **Carol:** well, the other problem is that I will go in and I'm like, all right, prs out there.

[00:33:19] **Carol:** I send it over for review, and then copilot suggests something silly oh, you forgot to capitalize this, which isn't really silly, like I should do it. Then I commit that and it starts to process over again. I have to get approvals again, and by the time it's getting done and I have time to monitor, to make sure the code actually goes out to dev, like I'm already sidetracked.

[00:33:40] **Carol:** I've opened Zillow, I've started cleaning my desk, like I'm doing all of these other things. To not forget that I have this work I have to get accomplished, but I don't wanna start any new code yet. Like I wanna get this out the door. So it's just, it's frustrating and it is, it's. It's an emotional, like rollercoaster when it fails because you know it's gonna take up hours of your day and you don't need hours of your day For a small change.

[00:34:06] **Adam:** Oh yeah. Build time is definitely like a quality of life issue for

[00:34:09] **Carol:** Yes. A hundred percent

[00:34:11] **Adam:** build and test time. it it, like you're saying, if, if it's too long, then it becomes a burden. It's almost a waste of time to not start something new. Not start, you know, not, not to run too tasks in parallel so that you can be working on one while the other is building and testing.

[00:34:26] **Adam:** But then, then you're, you know, you get really heads down on the side thing and you forget that you have one that's just was running the test and you let it sit for three hours after the test's finished. To note that, oh, okay, it failed because I missed a semicolon, so now I have to go start the process over

[00:34:43] **Carol:** all over again. Yes.

[00:34:45] **Carol:** I was also looking at some of the ways that I can ask. AI then, so I can ask AI how to do things like a pre pull request check. So I've started doing some of that, oh, can you review all the changes in my branch as a pre PR request and find any problems that way I know them before they go up into a pr.

[00:35:09] **Ben:** I, I'm always shocked. I think I was listening to an interview one time about Shopify, and I think the Shopify build time is bon like 120 minutes or something.

[00:35:20] **Adam:** I think they, they recently published something how they like dramatically reduced it, but it was crazy before. Yeah.

[00:35:26] **Ben:** Crazy. And I just, I can't even imagine how you get work done because I, I think this is what Adam, you were saying a moment ago that because the build time is so long, you just gotta jam as much stuff into each PR as possible. And that just makes the, the, the, the whole PR review and the burden you put on, on all your other teammates on reviewing stuff, and it just, it creates garbage all the way down as far as human experience goes.

[00:35:55] **Ben:** If I were to come into a company and I was a benevolent dictator, I feel like build time would be my number one and perhaps my only priority. it's the engine that drives movement forward.

[00:36:08] **Ben:** It's short built times. I, I can't understand how anyone puts up with it.

[00:36:13] **Carol:** Well, sometimes you just power through it.

[00:36:16] **Ben:** no, no. I know, I know. Sorry, I'm not, I'm not, I'm not saying like we, we all, I'm, I'm more saying like it's just awful. I'm not,

[00:36:21] **Carol:** shouldn't be tolerable though. Like everyone should fight to have it improved. It should be so annoying that you just wanna walk away. Like it should be the thing you fight for. I do agree with that. I can't tell you the number of times I've went to daily standup to have someone ask why my story or like why my work items still am ready to merge.

[00:36:40] **Carol:** And this will happen to a lot of developers. It's this has been in ready to merge since yesterday's standup. I was like, oh, I forgot to actually follow up that it finished merging. Like I did it. It just, I didn't go tell it. Now you can go test because it did work. So it's just, it's frustrating.

[00:36:56] **Carol:** But with that. I'll say working right? Working toward making it better. Trying to find solutions on how we avoid these checks on things that a don't change. How can we break up the monolith slightly so that only pieces really need to build and test based off of what changes are in place, if that's even possible.

[00:37:17] **Carol:** 'cause you always have the downstream effect of what you're changing. So just kind of trying to think through what we can do to, you know, make it better. First step is stop repetitive actions.

[00:37:29] **Adam:** Yeah, I'm trying to remember from past shows. Are you on GitHub Enterprise?

[00:37:33] **Carol:** We are, yeah.

[00:37:34] **Adam:** Okay, so you are, are you using GitHub actions for running this up? You, you asked about like triggering based on path, for example, of one. Like one of the things you can do, there is a way to do it in GitHub actions. yeah, so we have, it's not a full true monolith.

[00:37:48] **Adam:** Yeah, yeah. Wait, it's not a, it's not a full true monolith, but we do have, or sorry, I said monolith. I meant monorepo. But, we do have, you know, for example, a bunch of different like Lambda projects and each project has its own like package JSON and tests and stuff. but they're all in the same repo and so we have different workflows that are like, run the tests for this particular lambda and, and there's a, like a, I forget this intax, but there's a way like, you know, it says run on pull request and then I think it's just like a path argument or something.

[00:38:16] **Adam:** But it says only when something inside this folder

[00:38:19] **Carol:** Oh, okay. I will look that up and implement that.

[00:38:23] **Adam:** Yeah.

[00:38:24] **Carol:** 'cause that's what we're working towards. That's what I want to solve.

[00:38:27] **Adam:** Yep.

[00:38:28] **Carol:** Yeah. Cool.

[00:38:29] **Ben:** It's funny, I don't know if anyone here has had this experience, but my main form of entertainment is television. I, you know, I listen to a lot of podcasts, but at the end of the day, I'm getting to bed, I'm watching television. That's where my, that's where my joy comes from. And, I think to myself, oh my God, how did, how did people even live before there was television?

[00:38:47] **Ben:** Like it's just, it's so magical. And then something will happen, like we'll lose power from a storm and we don't have television. And me and my wife will sit in our living room and literally listen to the radio out loud, like old timey, 1920s people listening to War of the World or something. And there's a moment.

[00:39:07] **Ben:** Yeah. And there's a moment where I'm like, wow, you know what? This is actually really nice. There is something really nice about just sitting here and listening to the radio and having the, having to come up with an image in my head about what's happening. Like it's really kind of magical. And sometimes I feel like modern technology in the software development space sort of suffers from that same disconnect from the old timey days.

[00:39:33] **Ben:** You know, we have these really modern, high tech, robust deployment pipelines and we're like, oh, how did anyone ever get any work done before there was continuous. Deployment and continuous integration and blue green deployments and feature flags. And then sometimes you, you know, VPS or RDP onto your server and open up text, edit and edit a file.

[00:39:55] **Ben:** And you're like, oh, that's, that's pretty nice actually.

[00:39:58] **Carol:** Love config. Yeah, love config is process enabled. Not today.

[00:40:04] **Ben:** right. It's like we, we get so enamored with the way that we do things that we think everything else was just a stepping stone to get where we are. And, and we forget sometimes that there is a certain magic to the way things used to be done.

[00:40:19] **Ben:** and, and I bring that up only to say that, sometimes it might be worth looking at the things in the deployment pipeline to think about do we actually need this stuff? Are there things here that we could just remove instead of trying to make them better? can we just actually remove them all together?

[00:40:35] **Ben:** Like the old timey days before this technology existed. I, I dunno, just may, maybe there's an opportunity there as Carol shakes her head.

[00:40:43] **Carol:** Oh yeah, I, I'm right there with you and I will report back and let you know what I removed.

[00:40:48] **Ben:** Nice.

[00:40:49] **Adam:** Should I go next?

[00:40:50] **Carol:** Yeah.

[00:40:50] **Ben:** Hit it.

## [00:40:51] Passkeys: Getting Better

[00:40:51] **Adam:** Okay, cool. So hopefully mine's a, a brief topic. I, I just, I, I have, had my gripes in the past about passkeys. It's like the, the new password thing, right? So we, we did pass username, even password for a long time, and then OAuth got really big. and it feels like now the thing that the big password industry is pushing on us is passkeys

[00:41:14] **Tim:** big password.

[00:41:17] **Adam:** big sexy passwords. Um,and, you know, I, I really wanted to believe I watched some of these, YouTube videos of like the, the, I think it was IBM, are they the ones that do the videos where the guy is behind a, a pane of glass and he's writing on it with like whiteboard markers or dry erase markers,

[00:41:38] **Ben:** I feel like that's every technology company

[00:41:40] **Tim:** Yeah, pretty much. Yeah.

[00:41:42] **Adam:** Well, not a commercial, but like that's, that's kind of like their.

[00:41:45] **Ben:** Oh yes. This is like an IBM teaching series.

[00:41:48] **Adam:** Yeah. But it's like that, that's their pattern, their, the way they do their videos. And it, you know, it's interesting 'cause you watch the video at first and you're like, did everybody on this channel learn how to write backwards and upside down and stuff?

[00:41:58] **Adam:** And you're like, oh, no, no, no. They just reversed the video. Like he's writing forwards for himself. And then it gets flipped and you, you notice it. It's you see, you're like, oh wow, everybody on this channel is like left-handed. And then you go, no, wait a minute. his, his wedding ring is not on that hand.

[00:42:12] **Adam:** It's his wedding ring is on his other hand. It's on his quote unquote right hand. It's oh, they reverse the video to

[00:42:18] **Ben:** Oh, that's interesting. This is the where it's like they're on a black background and he is sort of, right. Yeah, yeah,

[00:42:22] **Adam:** but they're, it's like they're writing on the camera lens is

[00:42:24] **Ben:** yeah, yeah. With like very neon markers kind of stuff. Yes.

[00:42:28] **Adam:** Anyway, so I saw a video there and I think that it was like one of the, if I think that person or the, the company IBM or whoever was like on the steering committee and they're trying to like.

[00:42:39] **Adam:** Work out the problems and, and make passkeys work, right? Make fetch happen sort of

[00:42:43] **Ben:** Yeah.

[00:42:44] **Adam:** And, and, I, you know, I, I was conceptually very bought into this. I'm like, okay, this sounds like they're trying, they're, they're trying to solve all the real problems with passwords and password management and stuff, and Sounds great.

[00:42:58] **Adam:** Lemme give it a try. And immediately, the three things I tried, this was probably two years ago, the three, three or four things that I tried like just fail after fail, after fail, after fail. And I'm like, if this is the future, don't sign me up. I, it was just not, it wasn't working. I wasn't happy. And, I still have things that it doesn't seem to work very well for.

[00:43:17] **Adam:** But I have noticed lately, like in the last six weeks that more and more things are offering me passkeys. And when I try it out, it actually works pretty well. Especially like I, the portals that I use for my doctors, for whatever reason, and banks. You know, you sign in and, it's like, do you want to add a passkey?

[00:43:37] **Adam:** And eh, sure, why not? I said, I can go back to my password if I need to. and it adds a passkey and it's like seamless. It adds it to my 1Password entry for that, website. And then I go back to that website the next time. It's Hey, do you wanna sign in with your passkey? Like literally press one button and a couple seconds later I'm logged in.

[00:43:52] **Adam:** Works great.

[00:43:53] **Ben:** What, when you say push one button, what button? And I ask because my laptop is never open, so there's no like biometric reader or anything, so is it?

[00:44:02] **Adam:** Yeah. well, so then I guess for you, so for me, when I'm, when I say push one button, it might end up being two buttons for me. If my 1Password is not unlocked, right? So 1Password has to be, you know, quote unquote unlocked active, for your current session. But assuming it is unlocked, then I get the little popup in the top right corner, almost looks like a toast message from the website.

[00:44:26] **Tim:** and it's a 1Password, add in. It floats on top of the webpage, and it's like, do you wanna sign in with your passkey? And I just press that button. See, I've had it, like I would be on a desktop logging in and it would, the passkey would pop up on my phone

[00:44:41] **Adam:** yeah.

[00:44:42] **Tim:** to do

[00:44:42] **Tim:** the face id. Face idea. Yeah.

[00:44:45] **Tim:** Yeah, which, well, I thought was pretty sick 'cause I was the same as you. I'm like this past key thing, I'm not really sure. Let's, let's give this some runway before we start adopting it.

[00:44:54] **Tim:** A couple of them, they pretty much strong arm me into doing it. I was actually pretty surprised that if, if I was on my phone, it worked great. It just looked at my face and said, yep, okay, still ugly. Come on in. And then, and then it, but then I was like on the desktop version of it and it popped up on my phone and let me in.

[00:45:11] **Tim:** So I was like,

[00:45:12] **Adam:** So, yeah, I mean, I've had a couple of different experiences, right? Where you go to the website, and you tell it. Okay, yeah, I wanna sign in with my, passkey. I've had, I, I don't remember where this was, but I've had one. I know it like. Put up like a, basically a QR code on the screen and it's open with your iPhone and open the camera app and you point it at it and it, and it's then it pops up a thing.

[00:45:32] **Adam:** Do you wanna sign in with your passkey on the phone? And I do that, that, that works. It's a little clunky just 'cause I have to, okay, I have to take my phone outta my pocket. I have to unlock my phone, I have to go to the camera app. I point it at the screen.but at least that works. The place where it's most frustrating for me right now is I do have a passkey on my work Google account.

[00:45:50] **Adam:** And because of compliance reasons, we, so we use our Google SSO to sign into our laptops, which, it's not like seamlessly integrated. It works, but it, it, it's a little, Rube Goldberg esque, right? So when I update my Google password, I have to remember to go update my system password to match my Google password.

[00:46:12] **Adam:** And it, it will remind me, like the MDM will remind me. Hey, it's been two weeks. You, you should probably sync your Google password if you haven't already. and I'm just in the habit, so I know. But, anyway, so the, the problem that I have with it is that trying to log into the laptop with the password, like it's, it, it basically kind of pulls up like a little micro browser window with no chrome around it.

[00:46:36] **Adam:** that it's like, okay, now, you know, log in with your passkey, you know, or with your whatever device. I think it's expecting me to have one of those little, like key chain USB device type things and I don't Right. It just, like a YubiKey. Yeah. And it just assumes that that's the kind of passkey that you're using and I don't have that.

[00:46:54] **Adam:** And so it's you know, whatever login failed and, so like I always, when I sign into my laptop after a reboot or whatever, I have to click the try another way and I have to select from the menu, yes, I want to enter my username password and do it that way. That's super frustrating. And granted, that's a pretty niche use case, but still, if this is the future, these are the kinds of problems that we're gonna have to solve.

[00:47:17] **Adam:** So I, I'm, I'm, as, as much as it doesn't sound like it, I'm getting more optimistic about passkeys. I, I'm starting to finally see them work.

[00:47:26] **Carol:** So I've slowly kind of started rolling 'em in. Just some everyday stuff like, you know, email logging in, just where I can, like you said, the bank's good, but where I ran into the issue, the same kind of thing happened as what you were saying is the Tesla. So I was in the car waiting for Steve and it was gonna be a while.

[00:47:43] **Carol:** So I hit YouTube and forgot I had changed my password 'cause my nieces had my account and they were watching a lot of stuff and I didn't like it in my history. So I changed my password. I got real tired of Barbie being suggested to me. So, I changed my password, but I didn't think about the fact that I was signed into the Tesla.

[00:48:02] **Carol:** So watch YouTube. No matter what I did, I can't get to the password menu. It's forcing me through passkey, but it can't take it and it's just a nightmare. So I finally just switched over to Steve's and was like, do not change your password until Tesla updates because we can't watch YouTube in here. If you do

[00:48:18] **Adam:** Speaking of that,

[00:48:19] **Carol:** on Netflix,

[00:48:20] **Adam:** I just saw, a video about

[00:48:23] **Adam:** an electric, car. It's called a Lucid Air. It's a competitor to, you know, Tesla or whatever. And, this video that I saw, the guy was like going through all of the problems that he's been having with it. He was, he's an engineer and he bought it because he thought it would be like the best thing you could possibly buy right now.

[00:48:40] **Adam:** and he was going through all these issues that it has some hardware issues, some software issues, whatever. But the, the one that caught my eye for this conversation is. The car basically has face ID built in, right? So kind of behind the steering wheel, there's like a little sensor and it shoots up whatever, you know, the dot grid or whatever it needs to be able to do, kinda like face ID on your face.

[00:48:59] **Adam:** But, it's poorly engineered so that, like if the, you know, a, a steering wheel is vertically adjustable, right? It can move up and down depending on how big you are and that sort of thing, how tall you are. and if you have the steering wheel all the way up, the, the center part of the steering wheel blocks the thing from being able to view your face.

[00:49:16] **Adam:** So you can't like, authenticate with the car and it, and that's the way it, it'll, it has a feature where it'll automatically adjust the seat and the mirrors and the steering wheel and everything to whoever's driving it based on looking at your face. Well, if the steering wheel's all the way up, then it can't see your face and it can't adjust.

[00:49:30] **Adam:** And it's just likeyeah.

[00:49:32] **Tim:** Oh wow. just imagining like you sit down. Trying to crank your car. You look at the thing and all of a sudden the seat starts rolling back, going up and down, and you like

[00:49:45] **Adam:** Oh man,

[00:49:45] **Tim:** twisted like a pretzel.

[00:49:47] **Adam:** dropped the, the link in our team chat here. we'll include it in the show notes as well. If, this sounds like an interesting, collection of fails, about an electric car, definitely watch this video. it is surprisingly bad considering this is like a car full of modern technology.

[00:50:04] **Tim:** It's in 77,000 base price. So.

[00:50:07] **Adam:** Yeah.

[00:50:07] **Ben:** I'll tell you, going back to the passwords for a second, I just find that 1Password is so easy and with the browser extensions, it really automatically logs into everything that I need it to. I mean, granted, most of the time I have to unlock 1Password and I think it only remains unlocked for 15, 20 minutes or something. But you know, that covers my sort of morning routine of logging into the various stuff, slack and the company website, that kind of stuff. And then for the one-off things like logging into banks and health portals, I do it so infrequently and you know, infrequently might be once a month, once a week, you know, relative, you know, it's all relative.

[00:50:51] **Ben:** I don't, I dunno, I my 1Password just it. I don't think I, the motivation, what is it called? Like the activation energy to move to a different thing that then has to start working everywhere. I think it's gonna be pretty high for me personally, but I'm also slow to adopt things,

[00:51:07] **Tim:** I, I hear you guys talk about 1Password all the time, and I'm like, you know what? Chrome does a great job for me. It works on my phone, it works on my desktop. It's it generally has every password I need. So I don't, you know, and I don't, you know, I let Google generate all my passwords, so it's like I don't really see a driving need to adopt until there's either a, a security scare or things get easier.

[00:51:30] **Adam:** maybe that's a topic we should revisit on its own. There's, there's a bunch of reasons that we, that I would advocate for something like 1Password or KeePass over Chrome. But let's, let's, I'm gonna, I'm gonna write that down. We'll come back to that,

[00:51:42] **Carol:** I think that'd be a great topic.

[00:51:43] **Tim:** Yeah,

[00:51:44] **Ben:** but fundamentally, I think it's the same idea. It's just the central I,

[00:51:47] **Adam:** as feature number one.

[00:51:49] **Ben:** yeah, yeah, yeah.

[00:51:50] **Tim:** My turn.

[00:51:51] **Adam:** Yeah, go ahead.

[00:51:52] **Ben:** it, bro.

## [00:51:52] Why Your CTO Might Start Coding Again

[00:51:52] **Tim:** So I read an article, I think it was today, yesterday, that kind of struck a chord with me, just kind of where I'm at in my career and life and trying to figure out, you know, what I, what I'm wanting outta my job. And, it, it was in TLDR about, the title was Why Your CTO might Start Coding again.

[00:52:13] **Tim:** Right. And the premise of the article is that the world kind of changed, and this is gonna be an AI topic, but we're not talking directly about ai, just sort of the knock on. Knock on effects of, of AI in people's workplace. and that the, the premise is that, you know, AI kind of changed the economics coding went, the actual hands-on keyboard coding in theory is gone from $150 an hour, whatever your date, you know, hourly rate is to $200 a month for a Claude Code subscription, so to say.

[00:52:43] **Tim:** And then the bottleneck shifted from knowing how to write code to knowing what to build. That if you were in sort of the normal progression that most people start with, they're a developer, a junior developer, developer, senior developer, tech lead manager, you know, development manager.each step of that progression, if you went down that path, kind of moved you further and further away from the actual code and more toward the decision making tree of, of, you know, what code should do not actually writing it.

[00:53:19] **Tim:** And I, you know, I've sort of seen that as sort of a trade off. It's I really enjoy writing code. That's kind of what I grew up doing. It's why I got into the business in the first place, but it's I could be more effective for the company and I could affect more change and I could make more money, let's be honest, by moving up that, that ladder.

[00:53:39] **Tim:** And so I felt it was sort of a trade off. And the article's premise is, well, what if it wasn't a trade off? You were just training for a job that doesn't exist yet. And now AI has made that possible because the skills that you develop when you're not coding is, you know, being able to write good specifications for human beings, being able to review work product effect effectively.

[00:54:01] **Tim:** being able to like, maintain architectural coherence across multiple contributors. And the biggest thing is understanding the business that you're, that you're work, you know, doing this for and knowing what not to build. A lot of times, like developers tend to get into this path, oh, it does this, this, and this will be really cool if they did this, this, and this and this.

[00:54:24] **Tim:** And I've had, even just this week someone come to me like, Hey Tim, I'm thinking you know, we're doing this right here, but should we do this? And then I'm weighing the business decision going, well you know what the, based on the kind of things that are going on within the business that really doesn't make sense that you do this, so don't build it.

[00:54:42] **Tim:** Which a lot of times is the most important thing you can do is, is not build something versus building something and then it never, either a never gets used or just adds complexity. So I, it kind of struck a chord with me 'cause it's like I've been kind of ruminating the past like few months. It's what do I want to do?

[00:54:59] **Tim:** Do I really want to continue to like, manage people and like just be out of the code? 'cause my joy comes when I build something. Right. And, and honestly playing with AI as I have the past few months, that's, it's sort of helping me with that thing of, of getting that joy of building something without, at a scale that is, it sort of makes sense, right? So, I don't know, I, I think, I think it's kind of putting people who have, have kind of followed my path in, in, in their career at a point to say, you know, do I wanna jump back in the coding game? But then some might feel like, well, I've been out of it so long, I don't really know where to start or if I'd be good at it.

[00:55:40] **Tim:** But I think, I mean, the article makes some valid points that, that a lot of the things that you need to do to be able to tell an AI what to do are things that people who've kind of left from code into code management and develop, you know, managing developers. That's sort of what they do now. So maybe they have a little bit of an edge.

[00:55:59] **Tim:** I don't know.

[00:56:00] **Carol:** Yeah,

[00:56:00] **Adam:** It's. On. Go ahead, Daryl.

[00:56:02] **Carol:** I was gonna say like in the, one of the very first sentences in it, it's, they're already used to orchestrating work without doing it themselves. So they're used to making the like concept of something. Into a product. So they take what customers want, they take what we need to get done, they, you know, dish that out to a whole bunch of people.

[00:56:24] **Carol:** So I'm sure that most engineering like managers would be able to feed in the correct information to an LLM to build the plans to write the code. I feel like my manager now gives more detailed, props than I even think to do because I go very basic and then I, I iterate. I go, okay, I'm gonna do a little bit, because that's how I would write my code.

[00:56:51] **Carol:** I would do some work, read it, figure out what the next steps are, and keep working where he thinks big picture upfront.

[00:56:59] **Tim:** Yeah. And, and. I, I, and I sort of see that similarity because it's you know, we have these daily standups and I talk to their team. It's I do not wanna get into the details. This is a standup, you know, it should be 15 minutes or less. And it's people started to get into details, I don't really need to know implementation.

[00:57:17] **Tim:** You know, just gotta understand that, you know, here are the parameters, you know, don't go outside this. If you start running into that, let me know. That's sort of the same thing you do with an ai. You're like, you know, I don't need to know the implementation details. I'm gonna trust you that you're gonna do it right, and then review it afterward.

[00:57:33] **Tim:** But I, I mean, you sort of see that similarity of, leading a team of developers without doing a whole lot of coding yourself, with using a whole bunch of ai.

[00:57:45] **Carol:** I mean, you already trust them to go do the work, right? I mean, you're just trusting something different at that point.

[00:57:51] **Tim:** But you trust and verify, right? So we don't let people, you know, deploy code without it having been verified going through qa. It's as long as I know those things have taken place, I'm like, okay, cool. I could trust that there's gonna be some things here and there, but in general, trust the process.

[00:58:07] **Ben:** I was gonna,

[00:58:08] **Adam:** of thoughts. Go ahead.

[00:58:09] **Ben:** I was gonna mention this on the after show, but, it, it's very timely for what Tim's talking about, but I was just listening to a, a podcast called Shell Game, which just entered its second season. I didn't listen to the first season, but Radiolab did a crossover episode where they re

[00:58:24] **Tim:** the one where the shells are on the toilet

[00:58:27] **Ben:** no.

[00:58:27] **Tim:** pick

[00:58:28] **Adam:** three C details.

[00:58:30] **Ben:** So in Shell game in the second season, this guy is trying to test the limits of what the AI companies are selling.

[00:58:39] **Ben:** As far as you know, your whole workforce can be AI agents and he's trying to build an actual company.employing basically nothing but AI agents. And he is going through the whole process of how he's configuring them and how he is deciding who's doing what and how he's training them to use Slack and how he's training them to check emails and, and all this stuff.

[00:58:59] **Ben:** And it's, it's really fascinating because he is, he's very quickly, and I, it's, I'm only, it's only four episodes so far, but he is very quickly running into this problem where you have to be so specific about how things work that you can't assume any kind of human intuition whatsoever. And he was sharing this story where he has them integrated with Slack and the agents start slacking each other and they start talking about the stuff that they're doing outside of work.

[00:59:30] **Ben:** And he is like, oh yeah, like I went hiking in, uh, in Yosemite and it was so beautiful. And then the other AI agent is talking about, oh, that sounds so great. Yeah. And then they start trying to plan an out of office camping trip. He's oh, wait, now we need to, like, how should we, someone started a document so we can figure out which trails we all want to go to and we can vote on where we wanna be.

[00:59:50] **Adam:** you gotta drop the link for this so that we can all

[00:59:52] **Tim:** I,

[00:59:52] **Ben:** yeah. yeah, yeah.

[00:59:53] **Tim:** This is hilarious.

[00:59:54] **Ben:** really interesting and but it's again, it's one of these things, it's if, if you don't explicitly say you can do this or you can't do that, it's like you have to reinvent what a human does. So naturally, and I think that's, I, I don't know, like that's the, the, I, know, you, you're people try to apply the mental model of I manage people.

[01:00:15] **Ben:** Now I can just manage agents, but I think it's going to be wildly different.

[01:00:21] **Tim:** Well. I, you know, I did sort of infer the managing agents, but it's my point was really so that as a person who's sort of taken the management track that you already have, you might not feel you have the coding skills 'cause you're a bit rusty. But the code isn't really the problem when you're in an AI type world. It's not the code implementation. It's understanding, explaining to something that has a level of intelligence, whether that be a human or, an ai, what to build and what not to build. You know? So I don't, it was just, it just kinda struck a chord with me. 'cause it's like I'm, I'm trying to find that joy back, right?

[01:01:02] **Tim:** I'm trying to get that, that feeling. So it's I don't know, I go back to being an developer.

[01:01:06] **Ben:** It is, I mean, you know, the, the stuff that I do hear people saying is that it really does lower the barrier to entry. To the projects that they wanna work on, but didn't feel like they necessarily had the holistic understanding to get started with. I mean, even, you know, Sean Corfield, I think when he was on, he was talking about how he was using AI to help him build his, was it Flutter or, I don't know.

[01:01:29] **Ben:** You know, like one of his like native script mobile apps, he's I don't even really know how to do mobile development, but I'm doing it. And I mean, that, that stuff is, I, I do think that's pretty cool.

[01:01:39] **Adam:** I used to pay every year for,what is it, Google, play store account. Or you have to pay, it's a hundred bucks a year. It's not a lot if you're actually building apps, but I used to pay for it every year because I had this dream of building an app back when I was an Android user. There's an app you could get from Google where they would send you surveys and you would, they'd pay you, it might be 10 cents, it might be a dollar 25 or whatever, but for the 30 seconds that I, you know, spend filling out the survey while I'm pooping, you know, is money well earned, right?

[01:02:06] **Adam:** And then, you know, eventually you get like $30 in Google Play Store credit and it's oh cool. I can go buy this like expensive app that I've always wanted, but it's not worth spending $30 on. Cool. So I had this idea, I was like, I was gonna make an app where, you would buy like in-app purchases of whatever dollar amount I'd take a cut and you get the rest back as like PayPal, right?

[01:02:24] **Adam:** You, you put in your PayPal address, you, you pay me $30. Google takes their cut, I take my cut and you get $20. Right? But it, I turn your Google money into real money. And I, I must have paid for that for maybe four or five years. Never built the app.and, and it was always like, it comes around due again.

[01:02:43] **Adam:** I'm like, okay, this is gonna be the year. I'm gonna do it this year. Okay, let's go ahead and re-up it. And then I finally stopped. I a, I stopped being a Android user. I switched to iPhone, but also BI finally just gave up on that dream. I was like, okay, it's not, nobody's gonna use this. It might be for me.

[01:02:58] **Adam:** But, and then, like the next year or two years later is when LLMs hit and I was like, that might be, could have been possible.

[01:03:06] **Tim:** Right.

[01:03:09] **Ben:** But, but this, okay, so I mentioned the, mostly technical podcast. And one of the things they've been talking about AI just recently on the last couple of episodes, and Ian Lansman, one of the co-hosts, keeps bringing up the point that coding is like the smallest part of actually making a product successful.

[01:03:29] **Ben:** So when people talk about, oh, I can build something professional. With, ai, you know, the hundred times faster. He was always like, but the code's the easy part. It's like marketing and getting traction and finding the right product to build and hiring people and interviewing and, and,

[01:03:46] **Tim:** is the perfect example. That is the most garbage software that the

[01:03:51] **Ben:** right. So he's like, he's like being able to code faster really, if you're trying to build a, a company. It's like that's almost the, the, the very least of all of the responsibilities of running a company. and I, it's, I mean, you know, I don't run a company, but it feels right what he's saying. I mean, I spend a lot of my day coding, so I also know that code is actually a very important part of building a product.

[01:04:13] **Ben:** but I, what it, what it does make me always think about is just that we have finite amount of time and even when we have these agents doing stuff for us, and we can maybe get better at our context switching and our tasks switch. Like there, there's people are, you know, people who have to develop taste and quality and steer a company.

[01:04:37] **Ben:** there's only so many things they can possibly manage in their head. And I'm, it, it doesn't, you know, I feel like that taps out a lot sooner than people think it does, but maybe that's my

[01:04:49] **Tim:** Because it's, yeah, because it's like whenever you're in a managed position, you're dealing with so many different plates. You're dealing with legal, you're dealing with hr, you're dealing with finance, finance a lot. If you want a successful company, you have to have a good finance team. And, but they are completely different characters from the coders that, you know, if you, if you grew up in the trenches of coding, it's a diff whole new world.

[01:05:14] **Tim:** But buddy, it's a whole different world dealing with those people. And so if you get those skills, it's okay, I have those skills and now I can kind of plan for that with, with the actual coding. But then now I'm gonna kind of like devil advocate myself. It's if you have those skills, then why are you even bothering coding in the first place?

[01:05:33] **Tim:** Just kind of share that knowledge with your team and, and, and, you know, help them understand that and then let them do it. 'cause Yeah, I don't know. I'm going back and forth. Yeah.

[01:05:43] **Adam:** It's, it's the, the age old, like force multiplier thing. So,

[01:05:48] **Tim:** Yeah.

[01:05:49] **Adam:** alright, let's wrap it there.

## [01:05:50] Patreon

[01:05:50] **Adam:** so this episode of Working Code is brought to you by Three Hour Builds. Now you only have to do two things per day. You're welcome.and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:06:03] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:06:11] Thanks For Listening!

[01:06:11] **Adam:** We're gonna go record the after show. We got a bunch of stuff on the list here to talk about, a little bit of tv. I'm gonna follow up on some stuff I mentioned in last week's after show Jump unwrapped, and, you know, a couple of other little bits and bobs.

[01:06:24] **Adam:** so if, that sort of thing interests you, it's real easy. It's less than a dollar a week to become a patron. Obviously we'd love to have, you had a higher support tier as well, but, you know, if money's an issue, we get it. That's why we have our base level, which is, $4 a month, which works out to less than less.

[01:06:40] **Adam:** It's $48 a year if you're paying, full price for that tier. Yeah, we also have a, you can pay by the year and, and I think it saves like 5% or something like that. So, anywho, if you want the after show, go to patreon.com/workingcodepod, throw us a few dollars and get the entire back catalog of 200 ish episodes of, after show.

[01:07:00] **Adam:** And all the future ones as well. And we'd love to have you.that's gonna do it for us this week. We'll catch you next week. And until then,

[01:07:07] **Tim:** So it turns out that in the collective experience of all four of us, the job we've been training for all along has actually been to make sure that your heart matters. Mm-hmm. ​
