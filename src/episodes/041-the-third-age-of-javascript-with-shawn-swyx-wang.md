---
title: "041: The Third Age of JavaScript, with Shawn @swyx Wang"
description: "Shawn Wang - known as @swyx online - is a financial investor turned software engineer and journalist. With a passion for history and a knack for 'trend spotting', Shawn uses a keen analytical sense, honed through years of financial due diligence, in order to organize the world of web development into a series of epochs, each with its own theme. He's recently codified these observations in a blog post titled, The Third Age of JavaScript. Today, we're thrilled to have Shawn as a guest on our podcast to discuss the past, present, and future state of JavaScript as well as the world of developer ergonomics and the magical possibilities of effortless platform management."
date: 2021-09-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/041-the-third-age-of-javascript-with-shawn-swyx-wang/id1544142288?i=1000536263438"></iframe>

[Shawn Wang][shawn-wang] - known as "swyx" online - is a financial investor turned software engineer and journalist. With a passion for history and a knack for "trend spotting", Shawn uses a keen analytical sense, honed through years of financial due diligence, in order to organize the world of web development into a series of epochs, each with its own theme. He's recently codified these observations in a blog post titled, [The Third Age of JavaScript][third-age]. Today, we're thrilled to have Shawn as a guest on our podcast to discuss the past, present, and future state of JavaScript as well as the world of developer ergonomics and the magical possibilities of effortless platform management.

## Notes &amp; Links

- [Shawn Wang: The Third Age of JavaScript][third-age]
- [Shawn Wang: The Self Provisioning Runtime](https://www.swyx.io/self-provisioning-runtime/)
- [Shawn Wang: Temporal.io][temporal]
- [John Resig: jQuery](https://jquery.com/)
- [Douglas Crockford: JSON](https://www.json.org/)
- [analytics.usa.gov](https://analytics.usa.gov/)
- [JavaScript (ES) Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
- [Evan Wallace: esbuild](https://github.com/evanw/esbuild)
- [SWC](https://swc.rs/)
- [Parcel](https://parceljs.org/)
- [Benedict Evans: Platforms, bundling and kill zones](https://www.ben-evans.com/benedictevans/2020/12/21/google-bundling-and-kill-zones)
- [Base Rate Fallacy](https://en.wikipedia.org/wiki/Base_rate_fallacy)
- [Rogers Curve of Adoption: Diffusion of Innovations](https://en.wikipedia.org/wiki/Diffusion_of_innovations)
- [Crossing the Chasm: Marketing and Selling High-Tech Products to Mainstream Customers](https://www.amazon.com/Crossing-Chasm-Marketing-High-Tech-Mainstream/dp/0060517123)
- [Svelte](https://svelte.dev/)
- [Svelte Society](https://sveltesociety.dev/)
- [Webpack](https://webpack.js.org/)
- [Pulumi](https://www.pulumi.com/)
- [AWS Cloud Development Kit](https://aws.amazon.com/cdk/)
- [Serverless.com](https://www.serverless.com/)
- [Begin.com](https://begin.com/)
- [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)
- [Chris Richardson: Microservices.io](https://microservices.io/)
- [The Burning Monk: Choreography vs Orchestration in the land of serverless](https://theburningmonk.com/2020/08/choreography-vs-orchestration-in-the-land-of-serverless/)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[shawn-wang]: https://www.swyx.io/
[temporal]: https://temporal.io/
[third-age]: https://www.swyx.io/js-third-age/
[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/041-the-third-age-of-javascript-with-shawn-swyx-wang.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** So, the third age of JavaScript, did you coin that term or did you build on somebody?

[00:00:03] **Adam:** Else's cool.

[00:00:05] **Swyx:** I did. I went on a run one day and I was like, yo, there's something going on? There's something in the water in Jeddah and JavaScript land. And I looked around for different analogies for it. And it came up with this term and it stuck.

[00:00:17] **Ben:** Okay,

[00:00:17] **Adam:** can see why.

[00:00:18] **Ben:** can you.

[00:00:19] **Carol:** makes sense.

[00:00:19] **Tim:** don't even know what a means, but it's like, I'm like, I want to know.

[00:00:23] **Adam:** Yeah,

[00:00:24] **Swyx:** Yeah. And they accidentally, it was very good title game. I didn't really think about it that way. I mostly was just making observations. so, let me explain the thesis in, in, in brief so that people can follow along. so the thesis is that every roughly 10 years or so, there's a changing of the guard in JavaScript and the thematic investments are that when you step back in the long arc of history, Changes over that course of 10 years, actually has certain, very identifiable themes to it.

## [00:01:07] Intro

[00:01:07] **Adam:** Hey everybody, it is show number 41. and on today's show, we have a, another special guest today we have joining us, Mr. Sean, Swinks Wang. does that pronounce all that right? Sean.

[00:01:15] **Swyx:** Yes, sir.

[00:01:16] **Adam:** All right. Excellent. And do you prefer that we call you Sean or six or?

[00:01:21] **Swyx:** I actually do both. It's very confusing to

[00:01:24] **Adam:** Yeah.

[00:01:25] **Swyx:** but I've had, I just had switched since I was 13. it's my English and Chinese initials also make, reduces the chance of conflicts. and my previous company, there was an, another Shaun with the exact same spelling. So I just want basics.

[00:01:36] **Adam:** That works cool. And, so Shawn is joining us today to talk about, the third age of JavaScript. And so I think I'm really excited to find out what that means and open that can of worms. but as usual, we're going to start with our triumphs and fails. And today it's my turn to go first. So I'm going to start with a trial.

## [00:01:50] Adam's Triumph

[00:01:50] **Adam:** so at work today, we deleted our first feature flag, not the first feature flag that we created, but this is the first one that we've deleted because the feature has now become permanent and went well. And we got to remove like 150 lines of code. That was the original implementation. Just felt good.

[00:02:06] **Adam:** I'm happy about that.

[00:02:07] **Carol:** Yay.

[00:02:08] **Tim:** your Semaphore project. You built

[00:02:10] **Adam:** It is. Yeah.

[00:02:11] **Swyx:** Okay.

[00:02:12] **Carol:** Cool. Cool.

[00:02:13] **Ben:** exciting feature flags, man, it's gonna, you're gonna, you're gonna become addicted.

[00:02:18] **Adam:** Changing, changing the game, the paradigm here.

[00:02:21] **Carol:** I have now transitioned from getting LinkedIn information about LaunchDarkly to now I get emails promoting them. So apparently, my ads are all about LaunchDarkly right now, so I'm getting it all over the place. Thanks Ben.

[00:02:35] **Tim:** Thanks, bye.

[00:02:36] **Ben:** You're welcome.

[00:02:37] **Adam:** Yeah. So mine simple today. I feel like I usually drone on and on. I figured I'd keep it simple. So that's me. Ben, what do you got going on?

## [00:02:43] Ben's Triumph

[00:02:43] **Ben:** So in past episodes, I've talked about how at work. I do things very quietly and I try to fly under the radar because of political reasons. but on Friday I made a demo video. When I put it into our, one of our slack channels, we have this product TV channel, which is where we post demos of features that we've released.

[00:03:02] **Ben:** And, I gathered the courage to make a demo of something I had. I put it out there and I sort of put it under the guise of embracing this whole MIP, this minimum informal product movement that we're doing at work, which is like even pre MVP to get user feedback. It's I had never heard it before, apparently someone at the company coined it.

[00:03:24] **Ben:** like MVP of concept, right? Not even MVP of implementation, just

[00:03:30] **Ben:** but like, I'm sort of just using that as cover to basically say, Hey company, this is so exciting that we're doing all this iteration and moving fast and getting user feedback. And in the spirit of that, here's something I built and I'd love some feedback on it. So I figure if anyone calls me out for doing it, then I can be like, well, that seems very counter-cultural at this point, based on a lot of the other stuff we've been talking about.

[00:03:54] **Ben:** So, but, I haven't gotten in trouble yet, so I'm going to consider that a pretty good trial.

[00:04:00] **Carol:** Ask for forgiveness, not permission.

[00:04:02] **Tim:** There you go.

[00:04:05] **Ben:** How about you, Tim? When you got going on?

[00:04:07] **Ben:** So, I mean, the week's been kind of short. We had labor day weekend, just recently. And we went and saw Hamilton, which was awesome. Yeah.

[00:04:14] **Tim:** nice to be able to get a dig, we're supposed to go see it during COVID, but you know, they rescheduled. Actually cope is even worse right now, but we're vaccinated. So whatever.

[00:04:22] **Tim:** but as far as like a work triumph, I'm getting more comfortable with Scala and particularly testing scholar. And that kind of helps that I've got other people working on it with me now. So, just, yeah, working with the stack that I've kind of inherited. and yeah, just feel more comfortable with it actually being able to do some real good stuff with Scala.

[00:04:39] **Tim:** I've always been impressed with the language itself. Just I don't have opportunity to work on it. So having worked on the scholar play from work for the past week and actually having stuff compile actually feels really pretty good.

[00:04:52] **Carol:** So you were already supporting a scholar project though, right? You're just now actually getting to develop and learn whether as opposed to just

[00:04:59] **Tim:** well, I mean, so I mean, a lot of the stuff I was doing was just like changing some views and

[00:05:03] **Carol:** Yeah. Small

[00:05:04] **Tim:** Yeah. Small changes. But now we've got into some pretty actual, like architectural type changes

[00:05:09] **Carol:** So you're getting the code code.

[00:05:11] **Tim:** Yeah. Yeah,

[00:05:11] **Carol:** Yeah.

[00:05:12] **Tim:** So that's pretty cool.

[00:05:13] **Carol:** Yeah. That's awesome.

[00:05:14] **Tim:** feeling good about it. I mean, in any new language you can put on your belt and start to feel confident about is,is good, so

[00:05:20] **Carol:** goes great when you actually understand it, when you're learning it. That helps. Yeah.

[00:05:24] **Tim:** for sure. It's been a lot of a trial and fail, but it's been worth it. So I put the time in, so that's me. How about you Carol? And doing testing? Yeah. Testing the scholar. So, yeah, so it's so much easier to test Scala than it is to test ColdFusion. In my opinion, I maybe it's just because the testing framework is already there and it runs extremely fast compared to what ColdFusion and Lucy does, but yeah.

[00:05:47] **Tim:** So just being able to run those tests has been, it has been a, I feel like a real developer now. I mean, it's only been what, 20, 25 years. So

[00:06:00] **Carol:** You're

[00:06:00] **Tim:** that was your Carol.

[00:06:01] **Carol:** job.

## [00:06:01] Carol's Failure

[00:06:01] **Carol:** I guess I'm going to break up the street here. I'm going to go with a failure. Yeah. I'm sorry guys. No full triumphs this week. So I've been sick and kind of just recovering from not feeling so great. And I am really tired of people talking to me. I am just so over this,

[00:06:16] **Adam:** Well, you're in the right place.

[00:06:18] **Carol:** I, I like go look at slack and then I just close it.

[00:06:21] **Carol:** I don't even respond to anything and that's terrible because I'm a remote engineer. I really should be responding. And then I opened like Gmail and I'm like, oh, I have 50 emails. I need to go respond to you. Like, why are people asking me questions? I just don't feel good. I don't want to work. Like, but I really want to work.

[00:06:36] **Carol:** Cause I don't want to lay in bed either, but I just don't I'm not peopling very well right now. And it's not good for me. So.

[00:06:45] **Tim:** His whole career and he's fine.

[00:06:47] **Ben:** I actually on a Facebook, someone had just posted this meme. It was this angry looking cat. And the caption was, I don't even like the people I like. And I was like, yeah, that sums it up.

[00:06:57] **Carol:** am feeling that right now. I'm totally on board with that meme. Yeah.

[00:07:02] **Tim:** you're just not feeling well. You got, you get past that. That's not you normally

[00:07:06] **Carol:** no, normally I do pretty well, but it's just exhausting. So I'm just ignoring people and I'm sure someone's going to get mad at me eventually, but

[00:07:14] **Tim:** now.

[00:07:14] **Carol:** we'll see.

[00:07:15] **Swyx:** is there a way, so first of all, I think that it's very healthy to recognize it. is there a way that you can sort of shake yourself up, like some kind of, procedure, or I don't know, the word is escaping me, but just like a thing that you can always do in

[00:07:27] **Carol:** So actually I was feeling it like this whole week. So today I got up, I took a shower, I put on makeup and I brushed my hair and I was like, I'm going to actually put on like, not gym clothes. I was like, maybe if I make myself feel like I'm going to get up and do something, then I'll feel more like connected to people in a way.

[00:07:47] **Carol:** And maybe for like the first couple hours, it was good. But then I'm like, Nope, I'm over it again. Close slack. Again. I put the little, I did this time put the little sick emoji on my status so people know why I'm not responding so quickly. Yeah.

[00:08:02] **Tim:** my little routine when I try to get out of it is just to make my bed. Most of the, I don't care. I'm not a bed maker normally, but it's like, if I'm like, you know what, I don't feel any structure or purpose right now. I'll make my bed. I

[00:08:15] **Carol:** That's so easy.

[00:08:16] **Tim:** don't know if you can see right now, it's behind me.

[00:08:17] **Tim:** I actually made my bed. So

[00:08:19] **Carol:** That's a simple one.

[00:08:22] **Swyx:** Yeah,

[00:08:22] **Adam:** I usually either go on a walk. I live on a circle, so I'll walk around the circle once or twice, or I'll switch my desk. Like if I'm been sitting I'll stand or if I've been standing, I'll set

[00:08:30] **Carol:** I did do that today. Several times. I'm back to sitting again, but yeah, I think it's just cause I'm sick mostly.

[00:08:36] **Tim:** yeah, you'll be, you'll get over it.

[00:08:38] **Carol:** Yeah,

[00:08:39] **Adam:** Great audio. Thanks. Thanks for that girl.

[00:08:41] **Swyx:** do you, can I do a, like a combined try a

[00:08:43] **Carol:** yeah. Sean,

[00:08:44] **Ben:** no rules.

[00:08:45] **Carol:** yeah.

## [00:08:46] Swyx's Triumph and Failure

[00:08:46] **Swyx:** It's the same, it's the same thing, but there's a wind and there's a field. So the wind is that I'm here in Croatia right now, calling to you from, I guess Southeast Europe because of a blog post that I made called the third age of JavaScript.

[00:08:59] **Swyx:** that became a talk and I've given it a three times on, I think, three different continents

[00:09:05] **Carol:** that's cool.

[00:09:05] **Swyx:** And, but this is the first one. That's an in-person conference, they really set you up in Europe, all expenses paid and stuff like that. the fail is that I got common, the common cold. it was so nice to meet people in person, but you know how it conferences like diseases go around.

[00:09:21] **Swyx:** it seems like every speaker, cause I just met some of them, came down with the same goals.

[00:09:24] **Tim:** No.

[00:09:25] **Swyx:** it's a bit norming in a sense it's like comforting to know like, okay. if things are back to normal, even the bad stuff is also back to

[00:09:31] **Carol:** Like I can catch a cold. Yeah. That's

[00:09:33] **Carol:** funny.

[00:09:34] **Tim:** Hope you're feeling better.

[00:09:35] **Carol:** Yeah.

[00:09:35] **Swyx:** a little bit, especially, I guess when in like a social setting, I love talking to people. So this is just, heartwarming

[00:09:42] **Carol:** can't wait to

[00:09:42] **Carol:** be back in person conferences. Like that is just so exciting to me. I know. I just said I don't like talking to people, but that's right now, typically I'd love talking to people. I miss conferences.

[00:09:52] **Tim:** Where else have you given the talk?

[00:09:54] **Swyx:** global scope Australia. and then, I think one of the us conferences, I don't even remember which, which is a bit embarrassing because, I should have more, care or I don't know, like a mental space where the conferences that do invite me to speak, but, I mean, I just have other things going on in my life.

[00:10:11] **Tim:** but when it's virtual, it's kind of hard to, it's kind of hard to place it, right? It's like you just happened at your desk somewhere.

[00:10:18] **Swyx:** I know. Yeah.

[00:10:18] **Ben:** I was just gonna say. Croatia is beautiful and is becoming like a big tourist destination. I didn't know if you being there, it lives up to the hype.

[00:10:27] **Swyx:** it definitely does. So it's an S the, this conference is the info BIP shift conference. is it's in its 10th year of running and it was in this tiny city called Zadar. It's like, not even the top one or two cities of Croatia. So I expected it to be like a honestly kinda crappy small town. and then we went to the city and it looks like.

[00:10:46] **Swyx:** Um,the city center, like the, the liveliness of like all the people there and the restaurants and like the music and, yeah. It's, I mean, it just wowed me again of like how beautiful old

[00:10:56] **Ben:** Yeah.

[00:10:57] **Swyx:** can be. and, yeah, I mean, yeah,it's a really nice place to go for, I guess, a getaway, we're at a resort.

[00:11:02] **Swyx:** So I guess that's also a very nice thing because you have like swim out pools, right into the sea with the mountains in the background is very, very scenic.

[00:11:10] **Tim:** All right. We need to get at this conference. We

[00:11:12] **Carol:** Yeah, how can we get the invite

[00:11:13] **Tim:** How can, how can we need to figure out how to get to talk there.

[00:11:16] **Adam:** I'm going to start my blog

[00:11:17] **Adam:** post for the fourth age of JavaScript right

[00:11:19] **Tim:** here you go. And I'll do the fifth.

[00:11:21] **Swyx:** You know what you do though. So conferences are always keen on promoting the next conference, right? Like that's, they need to get butts in seats for the next events. so next year, you could be like the live panel podcast, and then they could use that as collateral for like the next thing.

[00:11:36] **Swyx:** and I've seen that in quite a few American conferences, but it doesn't seem to have arrived on European conferences yet.

[00:11:42] **Tim:** Good. good

[00:11:42] **Carol:** goes Smith.

[00:11:43] **Adam:** Yeah. Right.

[00:11:44] **Tim:** do it, man.

[00:11:45] **Tim:** Coratia 20,

[00:11:47] **Adam:** We'll work on that.

[00:11:48] **Carol:** 2020. You are bad at calendars

[00:11:51] **Tim:** no. Yeah. I'm going back in time and stop and Corona. I don't calendar you don't people. I don't calendar.

[00:12:00] **Carol:** calendar. Well, there you go.

## [00:12:01] Who Is Swyx?

[00:12:01] **Tim:** All right. Who is this dude? Who is this guy?

[00:12:08] **Adam:** on the, well, I mean, he's obviously he's a big guy, right? Like he's a, he's got so many cuts speaking gigs. He forgets where he's been

[00:12:14] **Tim:** I know, right. I mean, so just give us a little background. I mean, just for our listeners who don't know you, we obviously know who you are in your fantastic and awesome. but you know, for our listeners who don't know those couple, let them know who you are.

[00:12:26] **Adam:** the two or three.

[00:12:27] **Tim:** Yeah.

[00:12:28] **Swyx:** Yeah. the quick sort of two minute version is that I'm Sean, I'm from Singapore, born and raised, went over to the U S to study finance. Then that was my first career, from, since I was ever, since I was in high school, was captivated by the world of finance. I thought people who had money controlled, everything They kind of do.

[00:12:43] **Swyx:** But, um,and I spent, my, six years working in the finance industry, working my way up to the hedge fund that I really wanted to work at. And then finding out that I did, wasn't a fit. I didn't like it. it was both stressful and I wasn't that great at it. so, realized. I think technology is eating the world of software's eating the world and I wanted to be a part of that.

[00:13:01] **Swyx:** I wanted to create stuff instead of just invest in stuff. so that's what really got me interested in coding. I switched careers at the age of 30 and,did the boot camp and everything, rose up kind of as a software engineer through to Sigma and then developer relations at Netlify AWS. And now I'm head of developer,now head of developer experience@tempo.io.

[00:13:22] **Swyx:** so that's the quick sort of career summary. and then as a side project, they started blogging in 2018, mostly because I felt very bored at work. And I think at work, when you start out, you basically only get the mentors that you have at work. Right. And it's kind of luck of the draw. They could be good, they could be bad.

[00:13:38] **Swyx:** but when you engage them, Broader tech sphere, you get to pick your own mentors, externally. and that really accelerated my career as particularly just in getting involved in New York tech scene and getting, starting to blog in the react ecosystem. So I got, pretty friendly with like all the reactor core team members.

[00:13:55] **Swyx:** I started giving a lot of talks and my first big talk was at react rally, which is like the premier react conference. And, then things snowball from there once you're well known as the speaker, people start inviting you because you're a known quantity. You're you like? You're at least going to draw some people and you're going to probably be.

[00:14:12] **Swyx:** Give a good talk. So I try to do that for my conference organizers as much as possible. So they keep asking me back. but I don't want to be a full-time influencer because I think that's also a very dark path that a lot of people are on. so I, China want to, have the day job and do that work, but then also try to extract lessons from it and share it because Richard, a lot of people don't do so.

[00:14:32] **Swyx:** that's a lot of what my blogging and my speaking is

[00:14:35] **Carol:** I like the approach.

[00:14:36] **Tim:** thank you.

[00:14:37] **Carol:** Yeah.

[00:14:38] **Ben:** Do you watch a billions by any chance?

[00:14:40] **Carol:** Billions is the best.

[00:14:42] **Swyx:** the first couple of seasons. it got a bit too real for me, so

[00:14:45] **Ben:** cause there's a lot of finance, but then especially in the later seasons, there's a lot more technology

[00:14:49] **Carol:** yeah, they mix the two. Yeah.

[00:14:52] **Ben:** it seems like it might be right up your alley, but you already watch.

[00:14:56] **Tim:** I do. I do appreciate that. What you just said about, just not wanting just to be an influencer or maybe an evangelist, because I think a lot of people get in that role, sorry, Ray Camden. But th they kind of, they only like kind of dove on the top of things, right? It's not like they don't, they only get the, as very shallow pool that they play in that it's just dealing with, like hello worlds and some simple cases.

[00:15:18] **Tim:** And, if you're a person who really loves technology,you may want to go a little bit deeper, so

[00:15:25] **Swyx:** I have complicated feelings about this because at the end of the day, they will just numerically always be a lot more beginners than there are, intermediates and events. And, it's never a bad thing to want to help more beginners get started. I think it's just personally for me intellectually, not that fulfilling to essentially be stuck in tutorial hell.

[00:15:43] **Swyx:** but where I just like write like hello world or like, beginner demos again and again, and I wanted to go deep and I wanted to, learn how to manage people. I wanted to, learn how to help technologies cross the chasm, which is also another phrase that I really love. so yeah, there's all sorts of paths and they're all fine.

[00:16:00] **Swyx:** like I think the sort of intro path and the sort of influencer path is a decent living and I will never begrudge anyone their livelihood. So yeah, that's just a personal.

[00:16:11] **Tim:** All right. So now we know who this dude is, Adam.

## [00:16:14] The Third Age Of Javascript

[00:16:14] **Adam:** Sorry. I tend to jump the gun like that. yeah. So, the third age of JavaScript, did you coin that term or did you build on somebody?

[00:16:20] **Adam:** Else's cool.

[00:16:21] **Swyx:** I did. I went on a run one day and I was like, yo, there's something going on? There's something in the water in Jeddah and JavaScript land. And I looked around for different analogies for it. And it came up with this term and it stuck.

[00:16:33] **Ben:** Okay,

[00:16:33] **Adam:** can see why.

[00:16:34] **Ben:** can you.

[00:16:35] **Carol:** makes sense.

[00:16:36] **Tim:** don't even know what a means, but it's like, I'm like, I want to know.

[00:16:39] **Adam:** Yeah,

[00:16:41] **Swyx:** Yeah. And they accidentally, it was very good title game. I didn't really think about it that way. I mostly was just making observations. so, let me explain the thesis in, in, in brief so that people can follow along. so the thesis is that every roughly 10 years or so, there's a changing of the guard in JavaScript and the thematic investments are that when you step back in the long arc of history, Changes over that course of 10 years, actually has certain, very identifiable themes to it.

[00:17:09] **Swyx:** so the first age was, sort of in between 1997 to 2007, 2008, where the language was essentially standardized from ESY and all the way to years five and year six. from the second age Jewish, started in 2009, all the way to 2019, in 2009 was kind of the miraculous year. So in the exact same year, common JS,was born.

[00:17:28] **Swyx:** No JS was born, Chrome was born, NPM was born. and I'm probably forgetting a couple others, but,very foundational technologies that we still use today, was all born in 2009. And the rest of the 10 years was just kind of exploring the implications of those technologies and building the user land ecosystem around the finalized language.

[00:17:46] **Swyx:** and so that now that's sort of has run its course, and we were starting to see emergence of people, rebuilding things and innovating things, right. When the pandemic struck a lot of, people sort of took a pause and then they really furiously went to work on

[00:17:59] **Carol:** Absolutely.

[00:18:00] **Swyx:** and you could see all these, you see all these projects coming out of the woodwork for like, and you're like, okay, I'm just overwhelmed.

[00:18:07] **Swyx:** What is all this? So what the third day of JavaScript is a theory is a hypothesis. We're still living in it. So I don't know what it is. Right. But it's a hypothesis that there are common themes do this. It's a framework for organizing news that comes in and yeah, people are really liking it for the descriptive nature of like, okay, where does this new tool or this new project fit within what I'm going to use in 10 years?

[00:18:29] **Swyx:** Right? let's make those investments with a clear goal of understanding what is, what's what we really want to change and improve.

[00:18:37] **Carol:** So you said you started when you were 30 in your thirties, early thirties is when you entered. Okay. So when, like where in the sphere of this, did you jump in, like, where was your, at what point did you get in.

[00:18:49] **Tim:** You trying to figure out how old he is.

[00:18:51] **Adam:** yeah.

[00:18:51] **Carol:** no. We're trying to figure out how you all you are.

[00:18:53] **Carol:** I'm 36. So I was in college, at the beginning of what you're considering the second age, like, I was taking classes, I finished in 2010, so I, everything I know is based off of known, based off of angular and based off of react. And that's my starting point. So I was just curious of where your start was and

[00:19:13] **Tim:** Mine was Pearl

[00:19:15] **Adam:** Okay.

[00:19:18] **Swyx:** Well,when people ask me how many people ask me, how many years of experience I have, like my response is that, I learned a Lego Mindstorms when I was 12. I started basic when I was 14, I started, Excel when I was 16 and then VBA and then Python in high school, and then finally JavaScript.

[00:19:33] **Swyx:** But neither, and none of those times until I was 30, did I have the title of software

[00:19:37] **Carol:** Gotcha. So you

[00:19:38] **Carol:** had the

[00:19:39] **Swyx:** when did I, how many years of experience? Exactly.

[00:19:42] **Tim:** his origin story.

[00:19:43] **Carol:** Your origin.

[00:19:45] **Swyx:** But I mean, as you can't be sort of our age, like, millennials sort of thirties and HMIS that,

[00:19:51] **Tim:** I'm gen X I'm strictly gen I'm 50 years old. I'm strictly gen X.

[00:19:56] **Adam:** Sorry. Tim's our

[00:19:57] **Adam:** token old guy.

[00:19:58] **Swyx:** our age, our

[00:19:59] **Swyx:** age and up right.

[00:20:00] **Carol:** go.

[00:20:00] **Carol:** There you

[00:20:00] **Carol:** go.

## [00:20:01] The Near Death Of Javascript

[00:20:01] **Swyx:** You notice flash and action script, you noticed silver light. You notice all these competing standards. and we S we, we really didn't know it at the time, but we were experiencing the near-death of JavaScript, right? Like everyone working to their own proprietary implementation, you have to download this Java extension or this flashes extension in your browser for the thing to even work.

[00:20:20] **Swyx:** so it really had a near death experience. And honestly, the only thing that saved it, actually I can trace it down to an exact moment in 2008 in Oslo, when the maintainers for the ECMAScript 3.1 spec and the maintenance ECMAScript four, which were they're kind of deadlocked for five years, they came in the same room and agreed on what ECMAScript five was going to be.

[00:20:41] **Swyx:** and that was the sort of healing moment for JavaScript that enabled 2009 where everything else, kicked off. So like, it could just have gone a very different path.

[00:20:50] **Tim:** I

[00:20:50] **Adam:** sounds very

[00:20:50] **Tim:** it being an open standard really helped. Right. So I mean, when I was programming back in the nineties, BB script was our go-to right. We were like, oh, Microsoft, it's going to rule the world forever. And you know, they're always going to support it. And so we backed BB scripts much to our chagrin.

[00:21:06] **Tim:** And, then later I had to rewrite everything in Java. But I think the fact that it is open is probably the best thing. You don't want. The, these walled gardens that when it starts losing money or just loses popularity, it's gone.

[00:21:19] **Swyx:** Yeah, well, it's still complicated, right? it's not exactly open right now. TC 39 is a large body, where corporations buy seats and decide the future jobs. Good for you. How happy are you with that? they decide on a yearly cadence, incrementally feature by feature, instead of having a holistic view of how everything fits together.

[00:21:37] **Swyx:** How happy are you with that? there's a significant debate on the process, by which millions of developers are affected and the people who make the calls are like sitting in a room somewhere.

[00:21:47] **Tim:** But it means someone has to make the decisions. Right? I mean,

[00:21:49] **Adam:** yeah, We didn't elect them, Tim

[00:21:51] **Tim:** well, we did know. Well, maybe you didn't. I got an invite to the elections, but the elders of the internet called me.

[00:21:59] **Adam:** Right.

[00:22:00] **Ben:** in one of the, I think it was in the second age of JavaScript. You talk about, I think you mentioned Douglas Crockford and the good parts of JS book. but I forget sometimes that Crockford, I believe introduced the world to the concept of Jason JavaScript object notation, and like how revolutionary that was and how like the that's like, just like the impact that's had, like John Resig introduced jQuery and the world changes forever.

[00:22:27] **Ben:** And like Douglas Crockford introduces Jason and the world changes.

[00:22:33] **Tim:** The world turns upside down.

[00:22:35] **Swyx:** I think it's humbling at, probably for each of these guys, like when they did it at the time, it didn't seem like that big of a deal probably was one of many projects that could have worked, could not have worked and, for whatever factor or reason they managed to catch on, and are probably a lot of other contributors that contributed to their popularity as well.

[00:22:52] **Swyx:** So I try not to hero worship too much and, for these people, just cause they were just trying stuff out and there's happened to work. Whereas there are a lot of other, probably equally smart ideas that just didn't work out for some or some other reason.

[00:23:03] **Ben:** well, one thing that's really interesting is I went to see, I think it was Gotham JS conference, maybe like a decade ago. And Douglas Crockford was giving a talk and he was talking about this new type system. He was trying to develop and sell people on. And he was joking that a lot of times in the world of computer science, you have to essentially wait for the old guard.

[00:23:26] **Ben:** Before new ideas become really popular, but it feels like in the last 5, 6, 7 years, like that's no longer true, good ideas bubble up. And then they become super popular and then they evolve and then they get torn down and the new things replaced them, but it definitely feels like there isn't this, you have to wait for the old guard to die anymore.

[00:23:45] **Ben:** New things are happening all the time, which is exciting, but it's also exhausting.

## [00:23:51] Javascript Fatigue &amp; Consolidating Layers

[00:23:51] **Adam:** So that kind of, segues nicely into something that I wanted to bring up too. Was that, so what you were just talking about there, Ben reminds me of the buzzword. Yeah. JavaScript fatigue. That was going around a lot, a couple of years ago. And I feel like it's led up a little bit. And I think that might be one of the symptoms that, Sean was referring to in that for the third age was to like, collapsing layers.

[00:24:13] **Adam:** Right. So things are getting easier because the tools are taking over more responsibility for us. Right.

[00:24:20] **Swyx:** Yeah, it's a, it's about consolidation because we've worked out the main functionalities of the tool chains that we need. so now it's about like that's combined them, so we're not doing duplicate work. It's faster. It's simpler at its core. And, yeah, I think the end result is less JavaScript fatigue.

[00:24:35] **Swyx:** there are trade offs. There's always trade-offs. So I'll give you one, which is that, these tools are much more complex internally, so they require a lot more development. So actually every single tool that I mentioned in my post on the 30th of JavaScript is now a VC-backed. Right. So the business model changed.

[00:24:52] **Swyx:** It's no longer a volunteers working in source that kind of like hacking and stuff on weekends. there's a pavement to internship, because it requires a lot more upfront development costs. but what is that going to give us in terms of the business model of the tools that we use? Right. So are we going to see ads?

[00:25:06] **Swyx:** Are we going to pay subscription membership like that? Maybe that's fine, but this is a very untested ground that we're entering right now.

## [00:25:14] The Death Of IE 11

[00:25:14] **Adam:** So, what would there, are there any other, characteristics of the third age besides collapsing layers?

[00:25:22] **Swyx:** Yeah. so I go into a couple. So the first is they're the two main categories and then, one of them is,has two more subcategories. So the first one is the death of I E 11, which is a huge generational thing. Right. And,and the rise of IES modules, which, they're kind of tied at the hip.

[00:25:38] **Swyx:** they're not exactly the same. I mean, they're not the same thing, but, the tighter, the hip, because you can't have you as much as take off until 11 is dead. and I think this is the year, so the primary, a lot of companies that have dropped it from Microsoft, with themselves, dropping, 11 to like LinkedIn to Twitter, all this in the past year, since they started tracking this.

[00:25:55] **Swyx:** and every single framework, like view angular and,it's felt in, I not sure about react actually, but yeah, they've all at least announced plans or they're introducing plans and WordPress, which is obviously like 30% of the internet has also announced that they're dropping, 11 support.

[00:26:10] **Swyx:** The main thing like, oh, these are incremental. They're like individual projects, individual companies. The main metric that I'm really looking at is the U S government dropping IE 11, when that goes, everything else goes right. So. What point at which do they do that? So you can go to analytics.gov or something like that.

[00:26:28] **Swyx:** I don't actually know the precise URL, but there's a web analytics publicly for the, browser stats of people visiting us government websites and their policy is that you have to be above, if for a browser share of both 2%, it has to be supported by the us government. in November of 20,November last year, this number is the 3.6% of people visiting U S government websites on nine 11.

[00:26:50] **Swyx:** This is now dropped to

[00:26:51] **Ben:** Yeah.

[00:26:52] **Swyx:** So it's under the 2% mark has been dropping like a few zero point something every month. and at some point this year, I think the U S government is going to announce that they're dropping, 11 support. So once that goes, a lot of enterprises will just go like, alright.

[00:27:05] **Swyx:** Yep. we no longer have an excuse. everyone's moved over now and it's even okay for the us government to not

[00:27:10] **Swyx:** support it. Um, and I think that that really does.

[00:27:12] **Tim:** And, I E 11 is at 1.4.

[00:27:15] **Ben:** Oh, man,

[00:27:16] **Swyx:** Oh, geez.

[00:27:17] **Ben:** I can't wait to not

[00:27:18] **Swyx:** Yeah, it's really dropping fast. yeah, partially I think, there's a reason to this. Why so fast so soon because it hovered at this sort of four-ish percent mark for a long time. what the reason really is edge is the miss Microsoft being the heroes here, introducing 11 support in edge, meaning that you can upgrade your machine safely and still use your 11 applications without rewriting it.

[00:27:38] **Swyx:** and this actually solves the enterprise use case. Like if you're like, I work at a big hole, we don't have the fancy, machines that you guys have. We don't have the budget to change any of the applications and the, all the CMI 11. You can now run it on modern machines of Microsoft edge in 11 compatibility modes.

[00:27:55] **Swyx:** So Microsoft did a lot of work to kill their own.

[00:27:58] **Adam:** let's pour one out for the engineers that have to maintain that.

[00:28:03] **Ben:** Okay.

## [00:28:03] The Rise Of ES Modules

[00:28:03] **Swyx:** so that's the first section. The first section is the rise of you as much. So what does that enable? Right. Like it enables new tools that Viets in, snowpack in, a lot of light lighter packages. Like just this. Elimination of the need to transpile because every browser now is evergreen. that actually makes for a lot less JavaScript shifts over the wire.

[00:28:19] **Swyx:** and that makes it a faster internet. So we were all pro

[00:28:22] **Swyx:** that, yes, modules themselves, like they can only improve user experience. They also improve developer experience. Right. And that's what we're seeing with IES build and and all these new build tools that just assume you as modules, they don't assume, CJs.

[00:28:36] **Swyx:** and so, yeah, even so the node side and the abroad in the clients, sorry, node side and the client side are both moving to as modules. And I think that's a very fundamental thing. what's ironic here I'll note for the historians is that there's actually some debate as to whether this year's modules were even necessary. Uh, have we just spent a few years, wrestling with different module formats only to find out that actually it wasn't a big Duetto. So Devin gov it who maintains parcel one of the big three bundlers actually argues that common geos is fine. We could have stuck with it and he writes a

[00:29:08] **Tim:** Because that's what node

[00:29:09] **Tim:** JS uses. Right.

[00:29:10] **Swyx:** yes.

[00:29:11] **Swyx:** yeah,just as a convention, as a quirk of history, like no one really sat down and designed this thing. So when just came up with like a unifying format for all the pre-existing module formats, and that became common JS. but then we were like, let's standardize it and use this completely different syntax.

[00:29:25] **Swyx:** And that's a lot of tool chain churn and pain for an comparatively, not that much improvement. So it's a very hot take. but I like it because it comes from someone who is so credible, who understands deeply what it means to write a bundler into code split and all that. And he's saying that we didn't need the modules, Cool.

[00:29:41] **Swyx:** yeah, historical note done. and then, so moving on to like the second part, which is kind of the more interesting part of the second age of JavaScript, which is, oh, sorry. The third is your Johnson, which is the,collapsing layers and then the polyglot tooling. Right? So we talked about co collapsing layers in the sense that, my favorite thing about the collapsing is Adam is a historical fact about word processor.

[00:30:02] **Swyx:** So in like the seventies and eighties, we're processing software used to come sort of, with, with a single mandate, which is like you type stuff in text showed up on screen. If you wanted to do a page counts, if you wanted to do a landscape layout, if you wanted to do all the other things that you see in the options menu, in real word processor, these were plugins.

[00:30:24] **Swyx:** These are separately bot is a separately installed and maintained. Yeah. So there's a fantastic post by Benedict Evans. That kind of goes into this, because it's very relevant to. Does, what does a job and does that definition of that job evolve over time? So when, when a new piece of software first comes out, it does one thing and that's great.

[00:30:43] **Swyx:** And then you use a whole plug-in ecosystem to fill out the gaps that users need, but eventually the definition changes itself. And we started just expecting a standard set of plugins or features in every piece of software that you use of that category. So his argument was actually about, platforms.

[00:31:01] **Swyx:** So, like. Is competitive. What is competitive? Like when the iPhone launches a native feature that used to be developed as third party? Is that anti-competitive well, maybe not right,

[00:31:14] **Carol:** Okay.

[00:31:15] **Swyx:** because like, there's just enough people that need it, that maybe it should just be built into the platform. So similarly, I think the argument here is that, we used to have this Unix philosophy in JavaScript.

[00:31:23] **Swyx:** Right? One, one thing does one thing. Well, but, I think the definition of the thing of the job to be done is changing, in a sense that we now require linting we now require for, for

[00:31:33] **Carol:** Oh, Ben.

[00:31:34] **Adam:** He said the magic word.

[00:31:37] **Swyx:** what Linton.

[00:31:38] **Tim:** Lynching. Yeah,

[00:31:40] **Ben:** I hate,

[00:31:41] **Swyx:** Yeah.

[00:31:41] **Tim:** linting

[00:31:42] **Ben:** hate Lindsay, but.

[00:31:43] **Tim:** okay.

[00:31:44] **Swyx:**

[00:31:44] **Swyx:** well, I mean, I'm a fan, but yeah,it's all installed together, right? So that you don't have to reach for a separate tool. and the use the same EST, which acts actually on a fundamental basis, much more efficient, you're not parsing and validating and then working at different, like these are this, the reason why,you're building your bootcamps as low as because these, all these tools don't have any knowledge of each other and they don't work together.

[00:32:05] **Swyx:** They're not in the same, AST pass. and, you have to configure them. So you have like 20 different config files

[00:32:10] **Carol:** All floating

[00:32:11] **Swyx:** get your insulin, to work together with your text scripts and all that. so it's very common and this will go away because we're the definition of what the basic tooling requires for any development environment is changing to a more comprehensive definition.

[00:32:25] **Swyx:** Yeah. So the that's the death of Unix philosophy.

## [00:32:28] Polyglot Tooling

[00:32:28] **Swyx:** And then the final bit, before I drag on too much is the bit about polyglot tooling, which is also another development. Not very user-facing, but you'll see it in the speed. so people are using essentially saying like every JS tool needs to be written in JS so that JS people can contribute back to their tool.

[00:32:43] **Swyx:** they're finding that's actually not so true because

[00:32:45] **Swyx:** people don't really

[00:32:46] **Carol:** That's going away. Yeah. We're seeing that.

[00:32:49] **Swyx:** Yeah. So at the core of every tool, should be written in a systems language because that's a very hot path that friends that gets runs run millions of times a day. and no one in the GSM world really touches that stuff anyway. So we should really try to optimize it for speed rather than for contributions, which are. so people are switching tools in the core over to go and rest. we'll see which one wins essentially, but maybe it doesn't matter. It just matters what the maintainers are most comfortable with. because anytime you have a systems core and scripting showers is what I call this theory. that's kind of the best of both worlds because, users care most about the plugins and the interfaces that they can write, to extend the tool that they're using.

[00:33:27] **Swyx:** Whereas the core of it just needs to be fast and reliable.

[00:33:31] **Carol:** Yep. That's the key.

[00:33:32] **Adam:** yeah, I see a relationship here between the tools moving away from being written in JavaScript to the relationship, to, the companies now that are building these tools, being venture funded. Right? So like they can pay somebody to work there and I'm of two minds about it. I, it makes it harder for me to, to contribute if it's something I wanted to do, right?

[00:33:57] **Adam:** Like there are certain scenarios where I would be willing to, go up and write a feature for react. If it's something I really wanted. But if all of a sudden react was written in rust, I'd be like, well, sorry, I don't have time to do that. Right. I'll have so many, a night and weekend hours available.

[00:34:14] **Carol:** Okay.

[00:34:15] **Ben:** Okay.

[00:34:16] **Swyx:** There's trade-offs right. nobody's saying this is a pure win. but I'm, I am kind of predicting that this is what we see in early on. So far, one or two years into the thirties of JavaScript is going to be the overwhelming theme for the rest of the, that period. And this period will come to an end as well.

[00:34:33] **Swyx:** So a part of my humbleness, I guess, is that is saying that we don't know what's happens in the distant future. We don't know how long JavaScript itself is going to live. So I always inject a mention of like, we will, we might be thrashing about for these next 10 years, only to find that the next wave comes and, the tooling changes again, the languages that we use change again, and we have to be prepared for that.

[00:34:55] **Swyx:** but I don't necessarily mean. I don't necessarily think that means that we sit back and ignore all of it, because it's just fascinating how much people are trying to improve, development and the way we deliver experiences to users. it's

[00:35:06] **Tim:** Okay.

[00:35:07] **Ben:** Well, even just in the last few years, I think about Webpack and it feels like two or three years ago. People were looking at Webpack like this is a solved problem. We have this really difficult compiling problem and the web PAC people solved it. And now it's not a problem. And now a lot of people are saying like, oh, Webpack who even uses Webpack anymore.

[00:35:28] **Ben:** That feels so outdated. Like everyone should be using Veet. And these other more advanced builders that are more specialized. I don't even know what the differences are, but I mean, to go from such an extreme that this is a solved problem too, who even still uses that just in the span of like, it feels like two years is kind of crazy.

[00:35:47] **Swyx:** Eric or imagination. So limited by what we see around us. And a lot of us don't spend a lot of time thinking about what else could be, but certain individuals do. So Evan Wallace of who's actually CTO of Figma, wrote he has billed as a proof of existence. that could be a tool that would, there could be way faster than Webpack.

[00:36:04] **Swyx:** Cause he was just annoyed at Webpack internally within Figma. So he wrote it. he showed that you could do it a hundred times faster. you could bundle a hundred times faster to Webpack and then it was after racist, right? Everyone is now seeing like you kind of broke the four minute mile and now everyone's trying to do the same thing.

[00:36:20] **Swyx:** So, this, these things come in spirits because of certain individuals were brave enough and crazy enough to actually try, throwing away the existing tooling where it solved, for them it's not good enough

[00:36:29] **Tim:** Went back was an MVP, right? It was just an MVP.

[00:36:32] **Swyx:** It was, and he didn't actually intend to maintain it and build into a thing.

[00:36:35] **Swyx:** He was like proof of existence now that you lot, no, this, no, this thing exists. we don't need the rest of you. go build out the rest of it. but I think he enjoyed playing with it so much that it developed into a fully maintained project, which is great for all of us.

[00:36:46] **Swyx:** Cause he's amazing. but also it's interesting that it might not win because, next year, which is kind of the predominant framework of our time, or meta framework over time, next years did not pick yes. Build. when they dropped a Webpack, they went to SWC instead, which is the Bunbury compiler built-in rust.

[00:37:02] **Swyx:** so for them, whatever technical trade-offs, it's not about languages. It's more about design choices way. for whatever reason, SWC was better, but all of this was just kicked off by this sense that we could have something better. And I think, yes, build was a very, critical moment in that journey.

## [00:37:18] Analysing Trends Through History

[00:37:18] **Tim:** So, so Sean slash , I want to ask you, so don't take this. I'm not being condescending compared to me. You're young guy. I lived through the seventies, eighties, nineties of computers. You seem to have a real depth of history about like the past, which I don't normally see in younger people that haven't lived through it.

[00:37:41] **Tim:** Right. So how did you get to that? you have a rich wealth of knowledge about how we got to where we are and what was in the past and what it became. How did you, I mean, explain to me how that happened since you were like in finance during all that time.

[00:37:57] **Swyx:** Yeah, well, this is a lot of how finance research has done. So I'm kind of, applying a lot of the things I learned in finance, to my approach, to coming up in the tech world. Right. you do your background research, you do your due diligence on the history of things. You understand the trends and you try to predict where that takes you to going forward.

[00:38:14] **Swyx:** so part of something I do and I advise people is to follow the graph, right? who like when you start to learn that the world, as it is today, who made those things and, what were the situations in which they made it? What did they replace and what, and those people, they probably have moved on to the next thing, by the time that you came around to it, what are they working on?

[00:38:32] **Swyx:** and so, and then followed that graph to like, who do they follow and who inspires them? And once you build this graph of prime movers in your industry, you have a pretty strong knowledge of like, the driving forces behind everything. So, I do this, all of this partially because I'm a history nerd.

[00:38:47] **Swyx:** I do love trying to explain the world as it is today, but more importantly, it's a framework under which I can actually think about what I want to dedicate my own time to, because I want to make an impact as well. Right. So, understanding how people have done it in the past at least gives some format.

[00:39:03] **Swyx:** There's this. Problem with this, it's called the narrative fallacy, which is a Jeff Bazell term for it, which is when you try to explain things in the past, everything seems to fit so neatly together. It's like, oh yeah, of course he had a one line explanation for 10 years of work. but like it's never that need, right.

[00:39:19] **Swyx:** So I do, I'm always looking out for narrative violations where, the common sense or the common trope is one way. And then the truth is slightly different doors, a little bit uglier. And I love those

[00:39:30] **Tim:**

[00:39:30] **Tim:** I just find that really fascinating. So you're applying the idea of finance, where you're watching, where the money goes. Who's investing in what's growing, where they come from to the idea of computer programming and the, I mean, that just super fascinating. I've not. Yeah, I'm gonna have to digest this. This is gonna take me a minute.

[00:39:50] **Swyx:** I want to be clear, like it's not intentional. It's just like my

[00:39:53] **Adam:** It's your

[00:39:53] **Tim:** But I mean, that, that way of analysis is not one I've ever kind of thought of, so yeah.

[00:40:00] **Swyx:** so I have a podcast. I kinda listen to the culture chat money, where they go into sort of stock analysis. And, when they start, when you start talking about a stock, they don't stop. They don't talk about it as it is today. They talk about the origin story. It talk about what the key, the who to keep key players were like the strategies that they did in order to get to where they are today.

[00:40:17] **Swyx:** Because a lot of that is continuing destiny is a lot of that is culture. And, yeah, just having a deep understanding of how these things start, I guess really gives you a better information than just being buffeted about by news and data points and like benchmarks and, things that are very momentary in time.

[00:40:33] **Swyx:** The things that don't change are the long running trends in

[00:40:36] **Tim:** Hmm.

[00:40:37] **Tim:** Yeah. Mind blown that's okay.

## [00:40:40] Can Tooling Rely On Funding?

[00:40:40] **Adam:** here's a question you might be kind of uniquely poised to answer as somebody who comes from a finance background, who has a lot of experience in tech and who thinks deeply about both. we hear a lot about there being a bubble in the tech company funding. What do you think when we started talking about all these companies, that the tooling being now backed by companies, if there is a bubble and it were to pop and the floor drops out from these companies, what's going to happen to the JavaScript ecosystem. And what do you think the likelihood of that is?

[00:41:11] **Swyx:** I mean, the what's fantastic about the JavaScript ecosystem. Is it got by on so little funding anyway, right. We know how that's the default mode. We know how to live. That's fine. it's the rest of the economy that was going to be in trouble. it's like right now, as for us, it would just, these are this, just play money.

[00:41:27] **Swyx:** Like the monster that went in into these companies, it's like in the low single digit millions of dollars, that's not systemic. that's fine. so I would not be worried about that. I think having, by the way, another skill in finance is understanding base rates, understanding that, some things have much smaller impact than other things, just because you have a sense of the proportions of what normal looks like.

[00:41:49] **Swyx:** And base rate fallacy is very common in the sense of cognitive bias. And when you adjust for that kind of thing, you start to have a sense of like what news matters and what news is just, is more secondary to a third derivative of what's going to happen.

[00:42:04] **Adam:** Okay.

[00:42:06] **Tim:** I'm going to pretend I understood that. Okay.

[00:42:09] **Swyx:** No it's know like, okay. So Adam is talking about funding in, coming, VC funding coming through JavaScript tool tooling, whereas where it used to be open source. This is a second derivative change in a sense of like, it's an Excel, it's a directional change or acceleration rather than an ongoing trends.

[00:42:27] **Swyx:** we're only seeing, limited examples right

[00:42:30] **Tim:** above the baseline.

[00:42:31] **Swyx:** exactly. Oh, there you go. There you go. Yeah. I just, there's a picture in my head right now, which I can't really communicate over, over audio, but you got it.

[00:42:39] **Tim:** So it's a spike of my baseline. It's abnormal, but that's fine. we'll get whatever utility we can out of that. And then, we'll go back to baseline and there's more investment later. We'll take

[00:42:49] **Swyx:** Yeah. Yeah. More and more of these does change the baseline, right? It does. but you also have to just take it with a grain of salt because a secondary of this, which is we noisier than the first derivatives. And first of all, it is derivatives. And so, that's kind of how I think about all these things like,what is a zero, zero of derivative?

[00:43:06] **Swyx:** It's like the very first principles of like how many developers are out there, roughly for you at 50 million, what percent of them are using JavaScript about 11 million, like have your base facts down and understand the total addressable market. and then you start to have some measure of like, okay, when 10,000 people respond to a survey, that sounds like a big number, but it's tiny compared to the entire universe when 6 million people visit hacker news every single day, That's that sounds like a big number.

[00:43:31] **Swyx:** That's hacker news is really influential, but there's also 34 million developers who do not visit. How could you use every day? Right? Like it gives you a sense of what the baseline is before you go into the first and second degree of Dave's, which are noisier because he changed more often. These things don't

[00:43:46] **Tim:**

[00:43:46] **Tim:** I visited when Carol links to it.

[00:43:49] **Carol:** It's my morning read. I'm usually on the hacker news.

## [00:43:53] Participation vs Making Bets

[00:43:53] **Ben:** Yeah. So, so it sounds like we have a per Gnostic. what's the word? Prognosticator.

[00:44:00] **Tim:** prognosticator. Yeah. Thank you. Sounds like we have a prognosticator here on the show. Kind of look in your crystal ball here in say who in the next five, six years you think are the winners and losers when it comes to the game that you're looking at?

[00:44:17] **Carol:** Oh man. The

[00:44:18] **Swyx:** What game,

[00:44:18] **Swyx:** what game?

[00:44:19] **Carol:** Okay.

[00:44:20] **Tim:** The JavaScript, the programming game. I mean, you're talking about, the third age, right? So who's going down. Who's coming up.

[00:44:25] **Swyx:** so I do not identify as a predominant prognosticator. I said, I often say that if I was good at forecasting, I would still be in

[00:44:33] **Carol:** Oh yeah.

[00:44:35] **Swyx:** So what I do is I'm a journalist, I'm a journalist. I write the first draft of history, right. I try to say, what's going on now? trends, spotting is what someone called it.

[00:44:45] **Swyx:** and,I may be wrong and,I don't particularly have, I don't try to put the confidence intervals around what I project. I don't try to pick winners. I just say like, this is what's happening now. And this is how it fits in the overall frame of what's going on. and that's about as much as I. Put out publicly, obviously in practice, I do have to bet myself on things. so, I do think that, either yes, builder SWC is a really great, bill to option that seems to be, gaining a lot of traction. and then the layers on top of that, like Vieten,spelled kits are also very interesting as well.

[00:45:16] **Swyx:** And, and we'll see how this all plays out because, these kinds of things are more conditional. Like, the only thing that takes to invalidate my views is something comes along tomorrow that just like is better than every metric. And then that's not a very foundation stable foundation to, to build your beliefs on.

[00:45:31] **Swyx:** So you want to build your beliefs on long-term trends, which you think are always going to work. And then you filter the news based on those, understanding, based on those principles. So I try not to pick winners

[00:45:42] **Swyx:** essentially.

[00:45:43] **Ben:** Yeah, well,

[00:45:43] **Adam:** I mean, I guess the theory is that with collapsing layers, the, every man, and every woman doesn't need to necessarily concern themselves with the Pika and the snowpack and this felt, and the, all of those tools, if we pick the right meta framework like next or whatever, that's going to configure all that for us.

[00:46:01] **Adam:** Right.

[00:46:03] **Swyx:** I guess, but there's still be enough layers where you do need to make a choice in every layer. so that only gets you so far, basically that the classic layers philosophy, there's a lot of layers.

[00:46:14] **Swyx:** yeah. So, let me see. maybe this will be more helpful. What I actually care about more is activism.

[00:46:19] **Swyx:** So what turned me off about an investing was that I was just kind of sitting there placing my bets, at the casino table. And maybe they worked out, maybe they didn't, but like, I didn't really have a role to play in that. I was just kind of a parasite, just kind of sitting there and just trying to profit off of other people's work.

[00:46:35] **Swyx:** Where do you want it to get really good is you want to help these companies or these projects when you want to be a player in the stage, in, in the history, right? You want to have been there. You want to have been an active agent in that change. and so if you can make change happen, you can profit a lot financially, but then also more importantly have an impact in the industry.

[00:46:54] **Tim:** So that's kind of what I'm thinking about these days. so I mean, that's a very grand statement that I just made, I don't know what that means in practice though.

[00:47:04] **Swyx:** So help people cross the chasm, right? So there's a, this is called the Rogers curve of adoption where it's kind of like a bell curve. when a new technology comes along, there's like the, kind of the hobbyist kind of true believer types who don't need documentation, who don't need any support.

[00:47:17] **Swyx:** they just believe in this idea so much that they're just in it. And then there's an early adopters who are like, okay, there's a bit of stuff here. There's a bit of proof of concept. I'm going to try it out because I have some budgets or some time to try something new. And then there's early majority, late majority.

[00:47:31] **Swyx:** And then the stragglers, right, who make up the rest of the population. Those people don't adopt anything until they see, well thought out documentation, conferences, books, jobs, functioning job market. There's a certain segment of the world. And this makes sense for the majority of technologies that you do, but new technologies will never come along if not for the early adopters in the enthusiast.

[00:47:52] **Swyx:** Right? So the idea of crossing the chasm. By the way, this is a title of a book that, that also is of the same name that you should read, is that there's a huge gap between the early adopters and the early majority, right? The early adopters don't need kind of don't need as much handholding as the early majority.

[00:48:07] **Swyx:** And there's huge gap in between. So I've kind of dedicated my own career to helping technologies and companies cross the chasm, to fill in the gaps around developer experience, documentation, community. So anything that, that sorts of. Things over the hump, essentially.

[00:48:22] **Tim:** Okay.

[00:48:23] **Swyx:** So, so yeah, I'm kind of doing that.

[00:48:24] **Swyx:** I initially started out doing that with react and TypeScript and,I essentially wrote their community react in sex with docs. And then, I pivoted my focus to spelt, and I'm working on this wild society now, that I started it two years ago. It's now reached over 10,000 members.

[00:48:38] **Swyx:** and we were working on our fourth conference. so

[00:48:41] **Tim:** Okay.

[00:48:41] **Swyx:** I do, I think Scott was going to take over the world, probably not, but I'm just getting incrementally better at making impact. and I think that's more way more interesting than just sitting in a chair somewhere and just pontificating on who's going to win.

[00:48:54] **Swyx:** Right. Anyone can do that. any sort of anyone can be right or wrong. Doesn't matter, not fulfilling, be it be an agent in that

[00:49:01] **Tim:** So capitalist, Tim has to ask, how do you make money off of that?

[00:49:05] **Swyx:** Well, you do it with the companies that you adopt. All right. So, I work@temporal.io. Now I left a very high paying job at Amazon to work harder for less money at this startup. And the only reason that makes any economic sense is that I really believe this thing is going to cross the chasm and I want to help it. And I have equity in that. So that makes a lot of sense, right. if I do this well, it's probably a one or $2 million a year job. if I do it poorly, then I, I'm not going to go poor, but, there is some skin in the game.

[00:49:32] **Swyx:** there's some skin in the game for me and that's good. I think people should actively push themselves towards more skin in the game, rather than just sitting on the sidelines and pontificating on the great people and like, who's going to win. And like, you can hear that all day long. it doesn't really is not good use of life.

[00:49:47] **Swyx:** I don't think.

[00:49:48] **Tim:** this guy, man is inspiring me, man.

[00:49:50] **Ben:** were you just on a podcast talking about spelled society?

[00:49:53] **Swyx:** I do a fair amount of podcasts,

[00:49:55] **Ben:** I dunno. I think I just randomly subscribed to a podcast earlier today and someone was talking about smell society and they were joking, but joking about how like the top hat needs to be in the logo and very fancy sounding.

[00:50:06] **Swyx:** oh yeah. Yeah. So you're talking of a web

[00:50:07] **Ben:** yeah. Web brush. That's the one. So that was

[00:50:10] **Ben:** that

[00:50:10] **Swyx:** there, there are two, two other co-founders. No, that's Kevin

[00:50:15] **Ben:** gotcha. Gotcha. Gotcha.

[00:50:16] **Swyx:** so the three co-founders as our society. So he's the conference guy for us.

[00:50:19] **Tim:** Spilled society sound like something Andy Warhol would have started.

[00:50:22] **Swyx:** It just sounds, I like alliteration. and it's, it sounded more interesting than small community. So I just kinda went with that. And now everything starts about this.

[00:50:31] **Carol:** Yeah.

[00:50:32] **Swyx:** Like all conferences felt summit,

[00:50:33] **Tim:** glittery.

[00:50:34] **Swyx:** just kind of keep it rolling.

## [00:50:35] New Trends And Legacy Code

[00:50:35] **Ben:** One thing that I think maybe is worth mentioning is that when new things get introduced, however, it's not like the entire universe suddenly shifts and everyone's using the new thing, it's almost like Schrodinger's cat. If I understand that theory, it's like when something new gets introduced, the universe splits and now there's a new universe where everyone's using the new thing.

[00:50:57] **Ben:** And there's an old universe where everyone is continuing to use the old thing, because there's all these legacy applications that continue to exist. And just because some new compiler comes out, it doesn't mean that the, hundreds of thousands of Webpack based projects suddenly go away. And I wonder if there's a downside to things moving so rapidly. It becomes difficult to attract talent and to maintain projects that are using older technologies. I mean, not a month goes by where someone doesn't say to me like, oh, how do you even find ColdFusion developers? I mean, how far are we away from being like, how do you even attract Webpack developers that can work on my project that I started four years ago?

[00:51:37] **Ben:** It seems like there is a we're like you're dancing on the edge a little bit when stuff moves so quickly, I think there can be maybe some drawbacks.

[00:51:45] **Swyx:** Yeah.

[00:51:46] **Tim:** No.

[00:51:47] **Swyx:** Yeah, I, there's definitely a sense of that. I guess when, people, the U S governments, there was stuff in COBOL and they're trying desperately to find cobalt developers. Right. the state of New Jersey was like

[00:51:55] **Ben:** Yeah. Yeah.

[00:51:56] **Swyx:** looking for anyone and everyone who does cobalt.

[00:51:59] **Swyx:** I think, again, this, let's be clear about the scale at which we're talking about here, right? These innovations, maybe they'll, they'll come and go in, in the span of a year. And it's a real toss up as to whether or not they have staying power. but Webpack has been around for about 10 years now.

[00:52:13] **Swyx:** Yeah, we'll probably be around for another 10 years. Right? So like, this is called the Lindy effect, right? Like where the probability of something that's, continuing to exist is, directly proportionately correlated with how long has

[00:52:24] **Swyx:** already existed. so you try to base on that and, understand.

[00:52:27] **Swyx:** Yeah. I mean, we talk a lot about tech, a new technology. It's very easy for people to get excitable, but new technology. But the definition part of the definition of senior developer is understanding how to merge that in together with legacy, right? Because there's just always going to be a mathematically larger amount of legacy software than there is new software.

[00:52:45] **Swyx:** so it was actually a lot of the often a lot of the junior developers who were always talking about these new names because they don't have any baggage and that's fantastic. And you shouldn't, we should,encourage that energy, because this is like kind of the lifeblood of what is to come.

[00:52:57] **Swyx:** but when you're talking about maintaining serious software that users use and businesses depend on, you have to understand how to integrate it. with legacy tech and to migrate when some migrated and when to just stick with it. I think it's an art. I don't necessarily know of a better way myself.

[00:53:11] **Swyx:** we kind of kicked off this conversation with a discussion of feature flags and that seems to be the overwhelming way that people manage legacy and manage migrations.

[00:53:20] **Ben:** Feature flags. I got so excited, so I've been writing for a long time and the code that actually powers my blog, it's disgusting and it's old and gross and it's embarrassing. And I would never want anyone to ever actually look at it. And every now and then I get enthused and I'm like, oh, you know what?

[00:53:36] **Ben:** I should try and rebuild parts of it using one of these fancy new compilers. And I remember maybe like a year or two ago, I started to look at, parcel and I was like, maybe I can get parceled to, to compile my JavaScript and CSS, but it's like in order to even buy into the parcel approach, You have to have a bunch of assumptions in place.

[00:53:55] **Ben:** Like you have to build a point at an index file that parcel can parse in order to follow things. And I'm like, I don't have like a plain index file. I have a server side rendered template. That's actually like a composite of a lot of different other templates. And like, there's nothing to point at. So it's like, I can have it compile a JavaScript file, but then like, I would have to manually go in and copy hash based file names around to make sure that things are unique.

[00:54:20] **Ben:** And it's one of those.

[00:54:21] **Swyx:** So I'm not sure how true that is. Usually a parcel is designed as a graph. You should be able to point it at a simple JS file and it should start

[00:54:29] **Ben:** no. So I can do that, but then in order for it to create a unique file name, right? So it like caches the content and then it puts the hash in the. But then I'd have to go and take that file name and manually copy and paste it into something else or have it right to a file that I would then have to build tooling around to.

[00:54:47] **Ben:** And I'm not complaining. It was more like I was so excited to use the shiny new thing. And then I realized that it's not always so simple to take the shiny new thing and wedge it into the old crufty pile of mud that I've been working on for

[00:55:00] **Ben:** a decade and a

[00:55:00] **Carol:** Yeah. And it's not just plug and play.

[00:55:02] **Ben:** Yeah, yeah, yeah, exactly.

[00:55:05] **Swyx:** And that's a necessary cost of dropping all these assumptions. that's why I tend to talk about things in terms of assumptions, the optimal solution, what is best, tends to change when the assumptions change. So I focus on the assumptions of,each module is going away as I 11 going away, JS the Unix philosophy, going away, JS 4g as developers going away, and when you drop those assumptions, new problems come along and we're going to have to solve those.

[00:55:28] **Swyx:** so, yeah, I try not to be a, an mitigated champion. Like I think a lot of people, when they, when you promote an idea, they only say that the pros, I think that's very intellectually dishonest. so we should be pretty open about like, yeah, there are costs and sometimes these costs outweigh the benefits and you should just not do anything.

[00:55:42] **Swyx:** and that's completely fine. Yeah. So I tried to make clear that every time

[00:55:47] **Ben:** Yeah.

## [00:55:47] Infrastructure As Code

[00:55:47] **Swyx:** I have a couple of other, so things that didn't make the cut

[00:55:50] **Adam:** Oh, yes, please. I was going to ask

[00:55:51] **Adam:** that.

[00:55:52] **Carol:** please.

[00:55:53] **Tim:** go ahead.

[00:55:55] **Carol:** This is the exciting part.

[00:55:56] **Swyx:** Ooh. so, the integration of language and infrastructure, so I don't know, who here has, mess around with like the dev ops stack, essentially. Pilou me or AWS CDK. essentially. So, just kind of walk backwards since some of you are shaking your heads.

[00:56:10] **Swyx:** Yeah. So, so when you provision infrastructure on public clouds, you used to have to write all this. You just have to click around, right? Like, like, on digital ocean, you'd like, be like, give me this $5 box or whatever. And then on, AWS are easy to use, just like, give me like this size of box.

[00:56:23] **Swyx:** And that's where I run it. but when you start managing fleets of machines that just gets unscalable, click ops gets unscalable. So we start developing infrastructure as code, which for them, for, AWS means cloud formation, which is a declarative template of just like here's everything. I'm just going to give it to you as a spin things up as needed spin things down is not needed.

[00:56:40] **Swyx:** and that's fantastic. That becomes thousands and thousands of lines long. and so we're, the state of things have the state of play has come to is, were now using programming languages to generate cloud formation, to deploy onto these cloud, to these things. So, that's where, AWS CDK and come along, to really give you some power in expressing these things and building reusable functions and,doing all, doing a lot of, expressive power in your infrastructure provisioning.

[00:57:05] **Swyx:** The problem is then you have to connect that up to your application that you wrote in whatever language, let's just say JavaScript. So it turns out that I can write my, AWS provisioning infrastructure in TypeScript. I can write my server code in. Okay. Right. My appetites groups, but all these things don't naturally talk together.

[00:57:22] **Swyx:** and, actually I don't really want to do it. Do any of that infrastructure provisioning stuff? I just want to use it. Right. So what's the situation in which I can just send you my app and you figure out what it needs. You figured out the databases, you forgot the, I dunno, the authentication, the,the queuing mechanisms and the, all that other stuff that, that, that may possibly be.

[00:57:43] **Swyx:** so that's the sort of holy grail of just write business logic. so this is a blog post that I recently wrote called the self-provisioning runtime, where, essentially you write the app, and you'd sort of declared the resources that they use within the app as a, you, as you sort of use the app and there's no other configuration, there's no other deployments.

[00:57:58] **Swyx:** and that saves like a third of your code and you just ship it to, to the platform and it just runs everything else. so people are working on this serverless. there's a company called serverless.com, which is very confusing because it overlaps with the serverless movement, which is a, not a company specific thing, but they just bought the domain name and they won SEO.

[00:58:15] **Swyx:** Hm.

[00:58:16] **Swyx:** but, they're moving, they're building server, this cloud, which is essentially like a w two, just to store things through a database, you require it in an NPM module, right. And so that there's just like, is it fundamentally simpler way? So it's an integration of language with infrastructure. and you're going to see more of those.

[00:58:31] **Swyx:** I have like four or five different examples. A couple of startup founders are also working on similar things. but it's very new and probably you're not going to see this rollout for another two or three years, but it's on the radar that people are working on

[00:58:44] **Ben:** That's good.

[00:58:44] **Swyx:** theirs. so any comments on that?

[00:58:46] **Ben:** Well, I think earlier in the call, when you talked about the four minute mile as an analogy, For people not understanding that something's possible. And then someone demonstrates it and then like a whole bunch of people want to pile on to me, what you're talking about. There feels very much in that same genre where if you said like, oh, provision databases by requiring an NPM module, I'd be like, that's crazy talk. But then someone will do it. And suddenly it's a proven idea and a whole new world opens up. So from my very limited point of view, it sounds completely nuts, but I know that there's like brilliant people who are thinking about that in a much more in-depth way. And I'm excited because Alice but excited that's even a possibility

[00:59:30] **Swyx:** Yeah, you can try it now, by the way, with begin. so begin.com is a sort of serverless platform, that deploys on AWS. and yeah, you stand up a dynamo DB database by saying required, begin/data.

[00:59:42] **Swyx:** Is it, um,

[00:59:44] **Carol:** Yeah.

[00:59:45] **Swyx:** it cannot get any simpler, right?

[00:59:47] **Ben:** As a quick aside, I listened to an interview with the guy who founded begin and he was talking about how they create a free tier for all of their databases. And they do it by, it was like this massive dynamo DB table where they actually apply user permissions on like individual rows within the dynamo DB table.

[01:00:07] **Ben:** So like their entire free tier I think is a single table that they break up into individual users. I didn't really understand what he was saying, but it sounded very cool.

[01:00:17] **Swyx:** Uh, so that would be DB has a primary key and in sort of a secondary index system that makes that pretty straightforward to implement. I think a lot of serverless apps that are, multi-tenant do this exact same exact architecture and in down with UV makes it super cheap. so he's able to offer it free.

[01:00:34] **Swyx:** It's free for

[01:00:35] **Swyx:** everybody.

[01:00:35] **Swyx:** he's one of the smartest founders I've ever met. So I do have to disclaim that I invested in the company just cause like, I, I don't know, like, I don't know where this goes, but,the smart guy, so I'm sure he'll figure it out.

[01:00:46] **Swyx:** Um,

[01:00:48] **Adam:**

## [01:00:48] Temporal.io

[01:00:48] **Adam:** I was just gonna say, we've been going for a little over an hour now. and we want to be respectful of your time and, let's say something fun to talk about for the after show. So, do you, is there anything that you want to say before we end the shows or anything, do you want to tell us about temporal or,this is your minute man.

[01:01:03] **Swyx:** yeah. Okay. All right. let's try to like, make some noise for my employer. no, I mean, I left. I was on, because I do believe in this thing. I spent the past few years being an advocate for the serverless movement, and that's the serverless movement is a very strong friend or JavaScript in such very strong friend of front end developers.

[01:01:19] **Swyx:** Right? Because it's so much easier to deploy your own business logic on the server. the problem comes when you're trying to do anything substantial and by substantial, I mean, long running, because all serverless functions, have a natural limit of three seconds and it can be extended up to 15.

[01:01:33] **Swyx:** Minutes if you want to, but you probably don't want to do that. You will probably want to dispatch things to a task. You, and then have that pull off, into workers and stuff like that. And that is an essentially completely unanswered question in the serverless and the JAMstack and,finance space, right?

[01:01:47] **Swyx:** How do you do long winning tasks and winning tasks are more frequent than you think? so, anything from like processing a video file to waiting for a few preconditions to be fulfilled before you proceed to the next task. so this is for example, what Uber does with driver onboarding, right?

[01:02:04] **Swyx:** when you onboard as a, as an Uber driver, you have to fulfill like 10 or 15 different requirements and all those things have to be true before you're approved as a Uber driver. How do you model that? Right? You have to. Pull together, a scheduler, a database, a little state machine, a queuing system.

[01:02:19] **Swyx:** It's got a scale. You gotta be able to test it and you gotta be able to migrate. schema is it's all a very messy business and that's the state of the industry as it is today. temporal is a way to simplify that by writing code, workflows. And these are a fundamentally new unit, in the same way that search is a new is a new sort of custom job that you would never write on your own.

[01:02:37] **Swyx:** You would just outsource it to a search engine, an analytics tool as a custom database that you will outsource to an analytics tool. So, a new category of software is called, workflows, which specifically handle long running tasks and help you test them migrate and deploy. So, yeah,

[01:02:53] **Tim:** cool.

## [01:02:53] Choreography vs Orchestration

[01:02:53] **Ben:** I was, speaking of temporal.io. I was reading Chris Richardson's book. He runs microservices.io and, he talks about choreography versus, oh my God. Orchestration. Thank you.

[01:03:11] **Ben:** and I think he was so, my understanding is that choreography is like this thing executes, and then it knows to call the next thing.

[01:03:18] **Ben:** And then that thing knows to call the next thing. Like each kind of each thing knows what to do next, but there's no overall sense of what to do. and orchestration is like, no, there's going to be one thing that kind of manages all the other individual parts. And I was, he said that. The choreography is the way to go because it simplifies the individual units and is more scalable, et cetera, et cetera.

[01:03:39] **Ben:** And that was listening to a podcast the other day. And someone was saying that, yeah, choreography is great. Well, you have like three things to do. Maybe he's like, but the second things get really complicated. And you're talking about how Uber, you have like 18 preconditions that you have to deal with. It was like, you need something that no, like you need something that has state that you can debug and you can look at it.

[01:04:00] **Ben:** And it knows when to call things and knows how to cue stuff. He's like to, if you rely on choreography, it's like, you'll go mad trying to understand how a system works and why it's not working at any particular moment. anyway, sorry, that just popped into my head just cause,

[01:04:15] **Swyx:** No that's so you pitched orchestration perfectly. it's not a clear, super set you're making out to be like, orchestration is always better than choreography it's not, and there's a, there's really good posts. who is, the burning monk on Twitter, where he goes into when you should use choreography versus orchestration.

[01:04:31] **Swyx:** and, basically the TLDR and I'll save you. The read is, that within a bounded context, you want to do choreography because they all sort of are tightly bound, coupled pieces. But between, by the context between systems between jobs, you once orchestration. So it's not an either, or you can submit sometimes use a mix, especially if you're doing a bunch of serverless things or microservice

[01:04:52] **Ben:** I think that makes sense. and I hate to,

[01:04:56] **Tim:** I feel like at the end of the day, oh God, this is gonna sound terrible. Like at the end of the day, you sort of have to build systems assuming that a lot of developers are not that intelligent. And that sounds terrible. And I don't mean it how it sounds, but. You, can't not everyone who works in an engineering team are going to be, staff level, super architecture.

[01:05:20] **Ben:** Yeah. Yeah. Like you need to be able to build systems that can be used and worked on by a whole range of people. And sometimes you, like, you need to make the less elegant choice sometimes because it's the easier choice to understand and maintain.

[01:05:34] **Tim:** Hey bill.

[01:05:35] **Swyx:** Right?

[01:05:37] **Ben:** Yeah.

[01:05:39] **Swyx:** I think so. I mean, so, I think, I'm not sure who said this, but you know, if you code whenever you code, at one level, when, if you have to debug that code, you have, it kind of requires like two times that mental capacity. So if you code at the limits of your mental capacity, then when it comes time to debug,

[01:05:56] **Swyx:** you're completely screwed.

[01:05:57] **Swyx:** So

[01:05:58] **Ben:** I love that one.

[01:05:59] **Swyx:** I really liked that phrasing. I don't know who said it and I should probably go hunt it down. Cause,I like to give

[01:06:04] **Tim:** Sounds like uncle Bob. said everything.

[01:06:07] **Swyx:** Yeah. He said everything. He probably stole it from somewhere else too. so yeah, but, just to kind of loop it back. I have a blog post on white and portal and there are three fundamental opinions. Orchestration is the first one. second is event sourcing and third is workflows as code.

[01:06:22] **Swyx:** So, I kind of lead you through the pain points. And if you share the agreement with the conclusions, then you're eventually going to build Tim portal, whether or not you use it.

[01:06:32] **Tim:** The temporal is a language surface,

[01:06:35] **Tim:** a framework. now.

[01:06:36] **Swyx:** It's a framework. It's a,

[01:06:37] **Tim:** Thanks for coming.

[01:06:38] **Carol:** You're awesome.

[01:06:39] **Tim:** it was very, very engaging. My brain is full.

[01:06:44] **Swyx:** I'm trying my best to give you good audio. No, I know. I know we're podcasters is

[01:06:48] **Adam:** and you're doing all this at midnight for you, so you're on your game here, man.

[01:06:51] **Ben:** And he has a cold though.

[01:06:52] **Tim:** Yeah,

[01:06:53] **Carol:** Cole.

[01:06:53] **Swyx:** I love technology I'm yeah, I hope it shines through. And I love talking about it with people who are equally interested in your you're giving me all the positive feedback that I needed to keep going.

[01:07:01] **Carol:** You're doing amazing. Keep up the hard work.

## [01:07:04] Patreon

[01:07:04] **Adam:** So thank you so much for coming on the show. and I guess then, this is the part where I say, that this episode of Working Code was brought to you by all the JavaScript frameworks that you can't even. and listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod, to thank our patrons for their support.

[01:07:23] **Adam:** They all get an invite to our Discord server, where we hang out and chat about the podcast and work and life and all kinds of fun stuff.

[01:07:29] **Tim:** And how much Adam Cameron.

[01:07:31] **Adam:** or this week doesn't, he's redirecting that at me apparently. and we have other perks available, like early access to our new episodes and our after show that we're going to go record with John here momentarily.

[01:07:41] **Adam:** and of course we need to thank our top patrons, Monte and Peter. Thank you guys so much for your support.

## [01:07:45] Thanks For Listening!

[01:07:45] **Adam:** if paying for podcasts is interesting. No worries. We appreciate you taking the time to listen, and there are some freeways that you can help us out too. You can share the show with your friends and your coworkers, or you can leave us a rating and a review on apple podcasts or wherever you get your podcast. so please send us your questions and show topics on Twitter or Instagram @WorkingCodePod. Or leave us a message at 512-253-2633 that's 512-253-CODE. We'll catch you next week and until then,

[01:08:10] **Tim:** Remember guys, your heart. It matters unless you're creating new JavaScript platforms.

[01:08:15] **Tim:** Okay.
