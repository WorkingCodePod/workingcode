---
title: "188: Yeeting Changes to Production - Code Reviews"
description: "In this week's episode, Tim returns to the podcast for a discussion on code reviews."
date: 2024-07-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/188-yeeting-changes-to-production-code-reviews/id1544142288?i=1000663308623"></iframe>

In this week's episode, Tim returns to the podcast for a discussion on code reviews, touching on the importance of providing constructive feedback, tailoring reviews based on the developer's experience level, and discussing the merits and drawbacks of tools like GitHub.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/188-yeeting-changes-to-production-code-reviews.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** I'm just like, let me just do my PR. I don't, I don't want to, I don't want to have to conform to your notion of what a PR should look like.

[00:00:07] **Tim:** Ben, you have a military haircut, but you're a complete hippie.

[00:00:11] **Ben:** I'm like, come on, man. But I,

[00:00:15] **Tim:** me do my thing, man. You don't, don't, don't, don't kill my buzz.

[00:00:18] **Ben:** think

[00:00:19] **Tim:** Harsh my mellow.

[00:00:20] **Ben:** So

[00:00:21] **Adam:** learned it from you, Dad.

## [00:00:23] Intro

[00:00:43] **Adam:** here we go. It is show number 188 and on today's show, got the whole crew back together. Welcome back, everybody.

[00:00:48] **Ben:** what? I

[00:00:57] **Adam:** we have a new and interesting, sort of, perspective to bring to this a little bit. we'll talk about code reviews, but first, as usual, we'll start with our triumphs and fails.

[00:01:06] **Adam:** and I think Tim, you were released recently on the show, so why don't we have you go first.

## [00:01:11] Tim's Triumph

[00:01:11] **Tim:** it's, it's been like over a month since I've been on the show. And the reason for that is my triumph is that, yeah, I just got back from Ireland. Had a fantastic trip. I was, got there, was there for a month. Got to hang out with my father in law and mother in law who gave, my mother in law gave me COVID. But okay, we're not, we're not going to hold a grudge.

[00:01:29] **Tim:** The only times I've ever had COVID, she brought me. So. Thanks. Thanks. Thanks mom in law. but yeah, we had a nice, nice time getting to see cousins and uncles and aunts and family that we haven't seen for very, very, like one cousin we haven't seen for 23 years. So really awesome. A lot of good food. A lot of good, actually the food wasn't that great.

[00:01:48] **Tim:** Food was okay. The beer was awesome, but yeah.

[00:01:50] **Adam:** And taking your kids to the pubs.

[00:01:52] **Tim:** Yeah, that was, yeah, that was, that was lots of fun. And I guess you saw some of the pictures. Yeah. Taken Max and Lily. So, Lily's. She's about to turn 19. And so she, she got to try alcohol really for the first time that I'm aware of. but I'm pretty sure she's actually never.

[00:02:07] **Tim:** So they broke her in on like, it was like late one evening. We just watched like the European cup match and they're like, Hey, let's have some whiskey. Let's admire. And they gave her like a, like a little taste of whiskey. And she was like, yeah, she wasn't having it. It was like, that's gross. But the only thing she likes, she kind of like cider.

[00:02:24] **Tim:** She's like, it's kind of like bad apple juice.

[00:02:27] **Carol:** Yeah.

[00:02:29] **Tim:** But it's really good. but then she, my son though, he's like, he was really like putting them away. So like, like,

[00:02:38] **Adam:** Wasn't his first rodeo.

[00:02:40] **Tim:** yeah, it wasn't not his. Yeah. He had some back in Barcelona a couple of years back, so. Yeah, that was, that was fun. The kids enjoyed it. It was nice.

[00:02:47] **Tim:** They really enjoyed, we live in a rural area, so them hanging out in like a city where they could walk to the grocery store and my daughter thought it was really cool. She could walk to the coffee shop and go get a coffee and

[00:02:58] **Carol:** Oh, yeah.

[00:02:59] **Tim:** yeah, she thought that that was, yeah, they really enjoyed that.

[00:03:02] **Tim:** So it's, it's, it's very hard not to just sell everything and pick up and move to Belfast.

[00:03:07] **Carol:** Yeah.

[00:03:11] **Ben:** I had been under the impression that the quote unquote troubles between the, that's like the, what is the, doing the Protestants and the Catholics. I thought that was just all said and done with when some sort of treaty was signed, I don't know, decades ago.

[00:03:25] **Ben:** And, we had went to Dublin, last year and we were talking to a tour guide and he was like, Oh no, it is definitely not over. He's like, there's, Light piece, but he's like at night, they still lock gates and they still shut down parts of the city. I had no idea that was still actually happening.

[00:03:43] **Tim:** Yeah, I don't want to take too long of this, but I did not know. So in Belfast, they have this thing that they call it the orange parade and we happened to be there for it. It was like. The 19th of June. I don't know. July was two weeks. Friday before last, from this show. so what they do, like the English, there's like areas of, of Belfast where they have like a, an English Union Jack flag everywhere, like every single block.

[00:04:06] **Tim:** They paint the streets red, white, and blue. There's pictures of the Kings everywhere. So, you know, you're in a, in a, in a English Protestant area, right? They make it extremely abundantly clear who they're for, but on this one day, they all dress in orange. It has something to do with like William, the orange, the conqueror, whatever.

[00:04:24] **Tim:** Some battle that happened a really, really long time ago. The British will march around and like go into. Catholics will kind of like the, the Irish pro Irish pro Catholic, they'll kind of like lay down in the streets and block it. And, and the English will build these, they'll get like hundreds of pallets of like, you know, wooden pallets and put them into like a big tower and like, put the Irish flag up there and they'll put like pictures of, politicians.

[00:04:51] **Tim:** There was an election while we were there on July 4th.

[00:04:53] **Ben:** feel like I don't like where the story is

[00:04:54] **Tim:** Yeah. So they would put all these posters of Irish politicians and they would burn these like in the middle of the night. Yeah. They would like burn everything. And so they, and they're marching around in the Catholic neighborhoods going, yeah, we own your country.

[00:05:06] **Tim:** And I thought, wow, this is not like the English that I thought. They were just really polite and didn't want to offend anybody. They were like, it was, it reminded me of like civil war reenactors, you know, with their kind of pro South kind of bigotry, it was, it was ridiculous. And they do

[00:05:21] **Ben:** is

[00:05:21] **Tim:** single year.

[00:05:22] **Tim:** Yeah.

[00:05:22] **Ben:** That is

[00:05:23] **Adam:** That's bananas.

[00:05:25] **Tim:** We could see like all the, like from our, Airbnb that we stayed at. It was like on a top of a hill. There's like this, Belfast is kind of like in this little valley and there's like this small mountain range going around it and we were like kind of at the top of it and we could just see the whole city just burning these huge pyres of, of, it was nuts.

[00:05:45] **Tim:** It was absolutely nuts.

[00:05:46] **Ben:** Crazy.

[00:05:47] **Tim:** But anyway, that was me. Glad to be back. Glad to be back on the show. I missed you guys. And, yeah. How about you,

[00:05:53] **Adam:** missed you as well, Tim.

## [00:05:54] Adam's Triumph

[00:05:54] **Adam:** so, I'm not, I'm not sure. You tell me if this is a triumph or a fail. So, I mentioned on the last show that, I would, well, I don't know if I did. I, I know I teased it for the after show. I said, Whiskey 7 at Niagara Falls. So I guess maybe I'll just spill that out. so, went skydiving at Niagara Falls over the weekend.

[00:06:14] **Adam:** That's not my triumph or fail necessarily. that was,

[00:06:16] **Tim:** all the time.

[00:06:17] **Adam:** Yeah, yeah, it was, it was a good trip. you know, the, Whiskey 7 was the, the, it, the call sign or something of this, of the plane that, there was like one special plane. I did a novelty jump, just one jump out of this plane. It's a old, C 47. It was the lead plane on the second wave on D Day.

[00:06:35] **Adam:** Dropping paratroopers in. Yeah, it's pretty cool.

[00:06:37] **Tim:** Very cool.

[00:06:38] **Adam:** gigantic plane. And it was pretty cool. I posted some pictures on my Facebook and stuff. Anyway, so I had this trip planned. I've had it planned for months and then, and I was supposed to leave, Wednesday night. Yeah, Wednesday night is when I was gonna leave, go spend the night with my buddy.

[00:06:53] **Adam:** And then early in the morning we'd get up and, and, car or, yeah. Carpool, yeah, share. I would ride with him up to Niagara Falls. And, Tuesday night. we had really bad storms roll through, and, we lost power. Which is not that uncommon in my area, but they usually get it fixed within a couple of hours, no big deal.

[00:07:11] **Adam:** Well, so Wednesday night rolls around, we still don't have power, it's been more than 24 hours, it's like time for me to leave. We've had our generator running so that we can keep the fridge cold and, that sort of stuff. Keep the phones charged.

[00:07:24] **Tim:** Your Mountain Dew.

[00:07:26] **Adam:** Nobody wants a warm Mountain Dew. you know, so just got to keep the phones charged so that the kids don't, burn the house down.

[00:07:31] **Adam:** And keep the fridge cold so that the food doesn't spoil. Those were the priorities. And we have a gas range so we could still cook and everything. Anyway, so it came time for me to leave and I was like, you know, if I knew the power would be back on in another two hours, three hours, I would stick around and I would just go over to his house later, but there's, you know, I could stick around for another six hours and it wouldn't, you know, if it didn't come on, then I'm just kind of like wasting my time.

[00:07:56] **Adam:** I felt really bad because, you know, not to, you know, do like, you know, Traditional gender roles thing or something. But like, you know, my wife does a lot of the inside the house stuff and she asks me to do a lot of the outside of the house stuff, right.

[00:08:10] **Tim:** Although she cuts the grass, apparently.

[00:08:11] **Adam:** Well, she does that for me every once in a while when. She's, she's a very strong, independent woman. That's one of the things that I love about her, right? Like she, she doesn't ask for help, almost never asks for help. And, and so like when she was kind of stressing over me leaving because she'd not, she doesn't know how to run the generator, she doesn't know how to like turn it off and fill it with gas and get it started again, it's not that hard.

[00:08:33] **Adam:** And there's a sticker on it that shows you all the steps and everything, but she's never done it before and you know, that sort of thing. So I was feeling a little bad about leaving her. And I believe it was like 8 or 10 a. m. the next morning after I left that they got power back. But so they, we were out at, we were without power for like 36 hours and I just abandoned my wife to go on a skydiving trip in the middle of it.

[00:08:54] **Adam:** I felt a little bad about that, but it was a good trip. So.

[00:08:57] **Ben:** Call to

[00:08:57] **Tim:** guys think? I call it failure.

[00:09:00] **Adam:** Is it a fail because I abandoned her or is it a triumph because she's a strong, independent woman and she made it work?

[00:09:04] **Ben:** You set her up to learn something new and exciting.

[00:09:07] **Adam:** Yeah. The last, like the last tank refills that we had to do on the generator before I left. Like I didn't touch it at all. I took her out and I just stood there as emotional support and like back up. and, and she did it on her own, just so that, you know, increase her comfort level with it.

[00:09:21] **Tim:** Okay.

[00:09:24] **Adam:** Yeah. I don't know. That's just a sort of top of mind for me right now.

## [00:09:29] Tim's Fail

[00:09:29] **Tim:** And speaking of power failures, I will, I will throw this as a failure because, you know, I've been gone a long time. So I have a lot of triumphs and fails built up. So while I was, while I was gone, I forget, it's probably like two weeks ago. So the, it's been super hot here in Georgia. I mean, murder at like a hundred, it was 108 when we

[00:09:47] **Carol:** Oh, wow. Yeah.

[00:09:48] **Tim:** on our, you know, the official term, I don't know where they get this official, official temperatures. They'd be like 90s. It says 96 in the news. And I go look at the thermometer on the back of my house and it's 108. It's always like five degrees hotter than whatever they say it is. But anyway, it's like the power kept going out at work.

[00:10:06] **Tim:** And most of the time that we have a, you know, a very good UPS and extremely good, like we have a big giant generator that's natural gas fed, but one of the times that it went out, the UPS didn't catch it.

[00:10:17] **Carol:** Oh, no.

[00:10:19] **Tim:** And everything, our entire hosting center that we, cause we do all our own on prem hosting, it all went out.

[00:10:25] **Tim:** So

[00:10:26] **Ben:** man.

[00:10:27] **Tim:** business, my business was dead for about nine hours and I'm on a different time zone. And so, I'm sitting there trying to, you know, they want to make sure that that's, you know, when you're one of the leaders, you got to be

[00:10:41] **Carol:** Right? Yeah.

[00:10:42] **Tim:** Even though, even though I'm not, I can't do anything, right? I can't do anything, but you got to be visible.

[00:10:46] **Tim:** And so, I'm there, it's like, I was up until like 4 a. m. in Ireland, just making sure, I was waiting to the last customer and last process and last serve. Everything was up and running, verified it was going, and I'm like, oh, okay.

[00:10:59] **Ben:** that's

[00:10:59] **Tim:** I can go to bed now. And the next day I was just trashed for the next two days.

[00:11:03] **Tim:** But yeah, that

[00:11:04] **Carol:** That's awful.

[00:11:06] **Adam:** Way to Bogart my triumph or fail. I'm taking all my, my, emotional support here. No, it's cool.

[00:11:12] **Tim:** To make you feel better, I will Bogart bins and carols too.

[00:11:17] **Adam:** Fair enough. All right. So Ben, what do you got that, Tim's going to Bogart?

## [00:11:21] Ben's Fail

[00:11:21] **Ben:** I'm gonna do some technology stuff here, not like I've Now like you nerds who hang out with people.yeah, I'm going to go with a light failure, which is I've been trying to dabble in more, less framework oriented client side code, whether it's just native JavaScript or it's stimulus coming out of Basecamp or it's the Alpine JS stuff.

[00:11:45] **Ben:** and I just feel like I keep hitting the edges of the usefulness of it. I really want to buy into this world that there's this. Almost like a virtue to not having a framework that there's a virtue to doing quote unquote vanilla JavaScript and keeping things simple and native to the web platform. And I, and I do believe that there is something there that is really nice, but I just keep finding myself thinking this would just have been much easier with a framework like Angular or Svelte or Vue or whatever.

[00:12:19] **Ben:** And I don't know, I'm, I'm, I feel like I'm tired of fighting against it.

[00:12:24] **Adam:** Well, look, I mean, I just went and picked up a quarter pipe, a skate ramp for my kid, you know, we went and bought him one at his request and I had, in order to do that, I had to take the cover off the back of my truck and it's got this like quarter inch bolt to do that, right? It would be really. difficult and pointless to try to remove that bolt with a hammer. You know, you need the socket wrench.

[00:12:47] **Ben:** yeah, I exactly. And I think maybe part of my problem is that I'm, I'm just trying to use these, like, I'm trying to lean into the web platform in places where maybe that's not right. Not that it wasn't designed to go, but it's just, things get too complicated. Meaning like, if I'm just working on my blog and it's really just a totally public site, you know, I'm going to eat the cost of some of the complexity of the code.

[00:13:16] **Ben:** Because I don't want to have to have this convoluted build system or do some sort of like server side rendering with node applications, you know, like, like I wouldn't want to try and start rendering react components on the server in order to get a lot of the spa like functionality for something like blog, like I'd rather just have not as elegant CSS and not as elegant, HTML architecture.

[00:13:38] **Ben:** And, and have it more simplified. But the moment I'm going to have more complex interactions and be in something like more of a single page application environment, I don't know, I'm just feeling like I'm, I'm swimming upstream if I'm trying not to embrace the, the spa framework lifestyle.

[00:13:56] **Adam:** Yeah. I mean, I get what you're just saying that there, wow. That was a very, poorly constructed sentence, but we're keeping it. I get what you're saying. The, you know, there, there is definitely some value in not whipping out the framework for a page that doesn't need it. Right. If like, that's kind of what I was getting at with the, the hammer for the Bolt thing, like the right tool for the job, right?

[00:14:18] **Adam:** So like, if it's, if it's just a little thing and it, yeah, okay. So you want some interactivity in a particular blog post and you want some, you know, random or not dynamic, you know, example thing, interactive thing, you know, throw in some JavaScript, but that doesn't mean you need Angular or React or whatever to, to do that.

[00:14:37] **Adam:** But then, you know, if you are building like a big multi page application with login and all kinds of other stuff, like, yeah, sure. A single page app framework, makes sense there.

[00:14:50] **Ben:** That's how I'm feeling. And I, and the only reason I'm calling it a failure is because I feel like I couldn't make it work in a, in a way that felt satisfying. Like, so, so there's this kind of, I think, what's called a healthy tension between the user experience and the developer experience. And I think sometimes the, the heavy frameworks come under fire because while they err on the side of a great developer experience, sometimes maybe that's at the cost, the argument is that maybe that's at the cost of the user experience.

[00:15:19] **Ben:** and I think I just don't always know where that line needs to be drawn. And I

[00:15:24] **Adam:** That's a, that's a actually a really good idea for a show.

[00:15:27] **Ben:** Yeah, I, I, I, you know, cause even, even if you're dealing with something that is a SPA experience, there are probably SPA adjacent pages that don't need to be SPA like, whether it's the, you know, forgot my password page or the terms of service and privacy policy pages.

[00:15:43] **Ben:** Like those don't need to be SPA technologies, but then you run into a problem. You're like, well, if I'm not rendering them with SPA technologies, then how do I know that my design system type considerations are taken into account? Right? Am I using the right font? And is the line heights the correct, and is the button colors?

[00:16:01] **Ben:** Correct. And now do I have to have two different build systems? One for like more staticky pages and one for more spa pages. And I just, I don't have a good strategy for that. And, and it's frustrating not having a good strategy and it's frustrating, not necessarily knowing how to find the right strategy.

[00:16:19] **Adam:** mean, you've mentioned a couple of different frameworks that you're familiar with. I know you were an Angular person for a very long time and, the, you mentioned something earlier. I can't remember him.

[00:16:32] **Ben:** mentioned Svelte. I threw Svelte in there for you.

[00:16:35] **Adam:** Earlier

[00:16:35] **Ben:** Did I not? Did I

[00:16:36] **Adam:** this

[00:16:36] **Tim:** don't, don't, don't wave the red meat in front of him by saying svelte.

[00:16:41] **Adam:** What I was going to say is I know for a fact, a couple of these, more widely adopted frameworks, like I'll start with Next. js, right? That's a React thing. and I believe SvelteKit does this as well. Where you can, like, annotate a page and say, like, this is static, right? There's not going to be any dynamic behavior on this page.

[00:17:00] **Adam:** And so it kind of, like, optimizes that page. Like, yes, it's still going to use your same If you have a button on there, it'll use your button component so it's consistent. But, you know, it optimizes that page for being static. So it'll load faster than typical Client side rendered pages and that sort of thing.

[00:17:14] **Adam:** I

[00:17:16] **Ben:** I, I did not know that, but that makes sense. The, the thing, so the thing that kills me, and I don't wanna make this about my problems,

[00:17:23] **Carol:** That's Tim's job.

[00:17:23] **Ben:** that kills me is I

[00:17:25] **Tim:** That's right.

[00:17:26] **Ben:** I have a Windows VPS for some, for personal as a personal playground. And so I just have a strong aversion to anything. That requires me to have a specific server side technology to gain a feature.

[00:17:42] **Ben:** Meaning like if I wanted to use any particular database that could just work anywhere, right? If I wanted to have a, I could have a locally installed MySQL or I could have a RDS on Amazon MySQL. You know, I don't have to have a particular server side technology to do that. But the moment

[00:17:57] **Tim:** ColdFusion.

[00:17:58] **Ben:** well, but even cold fusion, I mean, that could run anywhere, but, but, but I guess, but that's my point.

[00:18:02] **Ben:** It's like. I like writing in ColdFusion. And the second that someone says, Oh, your whole life would just be better and easier if you just switched to technology X, Y, Z, I feel like I want to just say no on principle, because I feel like it shouldn't be the world that I have to live in.

[00:18:21] **Tim:** Is this principle just called stubbornness?

[00:18:23] **Ben:** No, it's not a stubbornness.

[00:18:25] **Ben:** It's like a, it's like a lock. And I just don't want to be locked into a particular server side technology.

[00:18:30] **Adam:** mean, yeah, you're, you're locking yourself in, buddy.

[00:18:33] **Ben:** Okay. that's me. I don't want,

[00:18:38] **Tim:** I'm looking forward to 2025, Ben, when he's like on the job market and

[00:18:44] **Ben:** let's not even think about that

[00:18:45] **Carol:** stress him out, Sam, jeez.

[00:18:48] **Tim:** sorry, I'm sure he's got enough stress on his own, sorry,

[00:18:51] **Ben:** All

[00:18:51] **Adam:** So glad you're back.

[00:18:53] **Tim:** a month.

[00:18:56] **Ben:** Carol. Why don't you take us home here?

## [00:18:58] Carol's Triumph

[00:18:58] **Carol:** Yeah, well, I'm going to go in with a triumph. last week I had the flu and I am recovering pretty well. I lived several days just in the fog and in my bed and after not really able to do much work, but my new team did amazing. And while I was gone, they kept code moving. They were able to ask questions to the right people.

[00:19:18] **Carol:** So just having jumped into this project that I've been on for months, it was nice to see that if I step away for a week, they kind of keep going. So I think that's a huge triumph for my team this week and just that feeling better is good, always. Oh yeah.

[00:19:37] **Tim:** I might get fired.

[00:19:38] **Carol:** Suddenly they realize they don't need you, Tim.

[00:19:41] **Tim:** They don't hate me. My salary's gone.

[00:19:45] **Ben:** Well, that's cool, Carol.

[00:19:47] **Tim:** So I, sorry I have the flu. It's funny this year. Like the COVID was not that bad. Honestly, it was not that bad. It was like three, four days. It wasn't really, but the flu this year seems ridiculously

[00:19:59] **Carol:** It was awful. And to get it in July, like who catches the flu in July? Apparently everybody does around me. That's what the doctor said anyways. Plus flu and COVID are going around.

[00:20:10] **Adam:** I feel like we have a responsibility to say COVID's not that bad if you've been vaccinated.

[00:20:14] **Tim:** Or if you already had it. Yeah, I'm naturally vaccinated. But so are you, are you, you're in Texas now, right, Carol? Okay.

[00:20:22] **Adam:** You really missed that much, Tim? Geez, how long were you gone?

[00:20:25] **Tim:** I remember she was, I think she was just about to move when I

[00:20:28] **Carol:** Yeah, I think, I think the last time we recorded was my first episode here and you and I just talked about moving and you were going on vacation and we did like a five minute podcast.

[00:20:37] **Tim:** Yeah, I was checked out. I was, I was already on

[00:20:40] **Carol:** I hadn't checked back in yet.

[00:20:43] **Tim:** Gotcha.

[00:20:44] **Adam:** Well,

[00:20:44] **Tim:** review some code.

[00:20:45] **Adam:** yeah, well, speaking of, of, rough timings and, and just barely being able to put a show together, I feel like we should acknowledge this episode is probably going to land late. and that's just, you know, it's that time of year, right? It's, we're all busy. We're all getting stuff done.

[00:20:58] **Adam:** We got work. We got lives going on and vacation, which is totally justifiable. Excused absence. but, you know, life is life and we're a little late. Sorry, but, here we are now.

## [00:21:08] Code Reviews

[00:21:08] **Adam:** Okay, cool. Let's talk about code reviews. so this was my idea for a topic and I thought of it because, you know, for, I've been at this company for like 12, 13 years now and, the entire time, like we started as like just a couple of very experienced, longtime software engineers and the first several hires were just like us, like very experienced, longtime software engineers.

[00:21:32] **Adam:** So it's like a all seniors company for the longest time. And now that we've hired our, our co op, who is basically a junior developer, still in college, not even fresh out of college. it, it kind of put this new set of glasses in front of me at code review time. Right. Like, uh,yeah. And, and like, it kind of made me realize like, oh, okay.

[00:21:52] **Adam:** I, I review code differently now for these people than I did at previous jobs. Right. and. I feel like there's something there, right? Like you review code, not just based on the code, but also based on like, what do I know about this person? And I want to get into that. And I've been holding onto this cause I knew it would be a better discussion with all four of us.

[00:22:13] **Tim:** well, let's first, first thing you said, code review. I remember when I first started the company I I've been at since 1999.

[00:22:21] **Adam:** Mm hmm.

[00:22:22] **Tim:** So one of the guys, his name was Tommy. he was one of the co founders and he would, he was really old school. He would print out all the code and review it with a

[00:22:32] **Adam:** bar paper.

[00:22:33] **Tim:** Yeah, on Greenbar, yeah, dot matrix paper, print it all out, and review it and go through, and then he would come into your office with the paper, and show it to you, and suggest it with his notes, and questions, and suggestions, and I was like, you know, that's, that's, I just really aged myself. Everyone knows I'm old.

[00:22:50] **Tim:** Nevermind. Yeah. That, that's,

[00:22:52] **Adam:** I learned how to debug that way in high school, you know? yeah, yeah. So you, you print it out and then you like kind of mentally walk through. You're like, okay, this, you have a, like a little variable. You draw like a X equals and that with a box up in the corner and you're stepping through the code in your mind and you're filling in the box with a pencil, as it changes, so you can like mentally keep track of what variable values are and stuff.

[00:23:14] **Carol:** think I could do that. Like, I don't know how I could code now without breakpoints and watches. Like the fact that I can just watch a value and know what it's doing and know how it got there and step through my code or step backwards. Like I'm good. I don't need paper.

[00:23:29] **Tim:** Yeah. I mean, that, that's kind of where I was going at. It's just how incredibly cool, like, this, just the tooling around code reviews has gotten. So eventually, originally there was no. None, right? It's like you, you printed it out or you just looked at a screen or you did a, a, a, a WinDiff or some sort of, you know, WinMerge kind of thing to look at the changes that were done and go, okay, they changed this to this, why'd they do that?

[00:23:51] **Tim:** But now you've got so many tools that they can use to do code reviews. It's, it's, it makes it a lot, it's harder to excuse yourself to say, we shouldn't do code reviews.

## [00:24:03] PR Comments

[00:24:03] **Ben:** Let me ask a, a mechanical question before we get too much into the philosophical stuff. And this is something that I feel like I must be in the minority here, because GitHub changed the way that they do something in a very drastic way, and it rubbed me the wrong way. But I'm assuming if they made this change, I'm in the minority.

[00:24:22] **Ben:** And it used to be that on GitHub, if you were looking at a pull request and you left a comment, the comment would immediately become a comment on the pull request. And then at some point they, they moved to this. Like pending comment model where you could kind of build up a bunch of comments to leave and then commit your review.

[00:24:41] **Ben:** And then suddenly all of those comments would become public to the, to the pull request author. And it drives me bonkers. I'm like, when I leave a comment, you should know about it right away. I think part of my hope is by the time I'm done with this PR, you've maybe already fixed the issue in the first comment.

[00:24:59] **Ben:** And I can only assume again that I'm in the minority here because GitHub probably listened to a bunch of people and they were all like, this is an amazing way to change the product. So I want, Carol, it sounds like you love the whole concept of the pending

[00:25:13] **Carol:** Yeah, I do not like the immediate save because there's been many times I go add a comment and I scroll down a little bit and understand a little more of what's going on. Like, okay, now it makes sense. I don't even think my comment was valid. Like, I want to go change the wording here because now I see what's happening further down and I understand why you did this, but here's my suggestion.

[00:25:33] **Carol:** And then on the flip side, if I am the one that has that PR out, I get very annoyed when my inbox just goes ding, ding, ding, ding because Ben's leaving me like a hundred comments on I forgot to do spaces or I didn't capitalize something. I'm like, I just want one thing that says, okay. It's ready now, go check it out.

[00:25:54] **Tim:** Plus his unread queue is like, what, 2000 now, Ben?

[00:25:59] **Adam:** So, okay, a couple of things to touch on here. I, I do like the, you know, build up a queue of

[00:26:05] **Ben:** Okay. So I'm the weirdo. I get

[00:26:07] **Carol:** duh.

[00:26:08] **Adam:** but that's, that's very heavily colored by the way that we do code reviews at my company. And I feel like that's another conversation we could have about, I think it was Ben you shared with me, like something about continuous integration, and continuous delivery and like, shortening the, the loop on that, trying to like get stuff, smaller pull requests and, and, and make stuff not sit in a review queue for a long time.

[00:26:34] **Adam:** Like that's a whole topic onto itself. But, and I think that in that sort of a paradigm, you know, where you're trying to keep the, the, the loop tight. The, the immediate comment is totally valuable and that would be my preference. I do want to point out that there, there are just two buttons right next to each other, there's a button that says add single comment and there's a button that says start a review.

[00:26:56] **Adam:** Now the start a review button is green and it looks like the primary action button,

[00:27:00] **Ben:** Well, I think it is, I think it is the primary action button that if you do command enter, I think it starts the review. It doesn't submit the comment. And maybe that's if they just, maybe if they switch the command enter shortcut, my whole world would change. And then

[00:27:15] **Adam:** tab four times and then

[00:27:17] **Tim:** Are you, are you, are you can relearn?

[00:27:19] **Ben:** But just to, to speak to Carol's thing about how you leave a comment and then you read 20 lines of code and you realize your comment doesn't make sense or, or now you understand what the confusion was, I've definitely run into that situation and I'll just leave a subsequent comment that says, Oh, okay. I see what you were doing.

[00:27:34] **Ben:** I,

[00:27:35] **Tim:** you already made me angry with your first comment. Like, idiot,

[00:27:38] **Carol:** code before you leave comments, come on!

[00:27:40] **Tim:** idiot. Just look further down.

[00:27:43] **Carol:** Oh

[00:27:44] **Ben:** right. All right.

[00:27:45] **Adam:** starting to feel like the hate on

[00:27:46] **Carol:** no, never, never.

[00:27:48] **Tim:** because I'm, that's cause I'm back.

[00:27:51] **Adam:** Mm

## [00:27:51] Knowing Who You Are Reviewing

[00:27:51] **Tim:** I'm his counter foil. So you were talking about like the person, like, so when, like, so when someone that you know, have known a long time, you kind of, because as you, as you Grow in a company, kind of get to know people. You kind of know where their blind spots are, right?

[00:28:06] **Adam:** Yeah, that's a good way to put it.

[00:28:09] **Tim:** You get to know them as individuals. Like, you know, they tend to miss this kind of thing. It's just, we all do. Mine is misspelling. Everyone knows when on a code review. Look what, look, look what Tim spelled. There is invariably spelled wrong. You know, the, the I, the E thing always screws me up. I'll always like drop a letter from the end of something, you know.

[00:28:28] **Tim:** Just, just drop the end of the letter, like what, I, my fingers got tired, like, yeah, you know what I'm talking about. I just skipped that last letter. Who needs it? and then, and then other folks, and then there's some people who are just, just so pedantic on stuff, and it's like, I know you're pedantic and you really get off on, on finding this kind of stuff, so I'm not gonna worry about it.

[00:28:50] **Tim:** I'm just gonna let you catch it, because I know you will.

[00:28:53] **Adam:** Is that like going into a sales meeting with like two pitches and the one of them is intentionally bad to make them pick the other one? Like you're, you're intentionally leaving something in the code for this person to find so they don't like, dig

[00:29:03] **Tim:** I don't think it's intentional, but it's like, you know, I'll go through something. I'm like, should I go review all the spelling line by line? Nah, Bonnie will get it. She hates, she, Bonnie, Bonnie hates misspellings. I like with a passion.

[00:29:15] **Ben:** But you are touching on something very interesting here in terms of pedantics, which is the, I don't agree with something in this code, but the code isn't invalid, meaning the logic is correct and the application will run. So the question then becomes, do I, Comment and wait for them to respond? Or do I comment and approve the PR and leave it up to them as to whether or not that's something that they want to take into consideration before moving forward?

[00:29:46] **Adam:** I'll do that.

[00:29:47] **Ben:** Yeah, I feel like that's the, that's the player move is to err on the side of approval as often as

[00:29:53] **Carol:** I do it with certain people. Some people I know, they're always gonna make the decision I don't want them to make, so I'm gonna not approve it yet. Like, I want you to really think about it before you just ignore my message and move on.

[00:30:07] **Tim:** Yeah, sometimes, sometimes you're in the mode of like, this is a learning moment for them. Let's see how they take it. Or maybe it's like, sometimes it's, there's just two ways to look at things, right? They're both equally valid ways to do things. And you just say, Hey, when you were doing this, did you think about doing it maybe this way or following this pattern.

[00:30:26] **Tim:** I noticed you did this here and this seems kind of inconsistent to what you did prior. Is there a specific reason for that as asking? I tend to ask more questions than make bold statements, right? Because I, I feel that, you know, most people who have been doing this and have a modicum of integrity, if you just ask the question, you're going to get a good answer.

[00:30:49] **Tim:** Cause sometimes it's just, they didn't think about it.

## [00:30:51] Copy Pasting

[00:30:51] **Ben:** You know, one thing that drives me crazy and I think this is, you know, just my lack of patience sometimes. is I'll be working on code and literally my implementation is I go to a function, I copy it, I paste it below, I change the name, I change some logic. It's like, it's kind of the same as the function above, but it has to do something special.

[00:31:13] **Ben:** And then someone in a pull request review will start being like, well, why did you, you know, format your function signature this way? Or like, we usually do this thing. I want to be like, bro, I literally copy pasted code that's already there. This is not what this PR is about. Oh,

[00:31:31] **Carol:** I copy old ones and put them in and they're like, we don't really do it this way anymore. I'm like, well, you should get rid of the old ones. Cause that's where I found it.

[00:31:39] **Ben:** yeah. Right. Like don't make your problem. My problem. Side

[00:31:43] **Tim:** know. Copying and pasting code just sounds like a problem to begin with to me. Honestly, it's a red

[00:31:47] **Ben:** code is awesome. I copy paste

[00:31:49] **Carol:** I do it with tests a lot, just because I don't want to set everything up. I'm like, oh, you've already got like 10 of the mocks I need. So I'm just going to copy this one and use it as my kind of like base for getting going. I don't have to question anything.

[00:32:02] **Tim:** guess so. All right, I guess we're done.

[00:32:05] **Adam:** on the subject of copying and pasting, that just made me think of, it's not a pull request that I have, but it's like a, an issue to go back. And replace a bunch of our, yeah, Excel sheet, spreadsheet, generation code. You know, we, we have this way that we figured out how to do it that is reasonably performant, and not a terrible developer experience.

[00:32:23] **Adam:** And that's been copy pasted a dozen times. and, and, you know, people kind of add little niceties here and there and.I finally just got fed up with it. And I was like, you know, we're already using a confusion component to do the heavy lifting here. It would not be that hard to like add a function to that.

[00:32:40] **Adam:** That's like, here's the query. Give me back a spreadsheet. Right. And it does all those same things. And you could even have like a callback to do like a per row, you know, whatever, if you want to, if you want to hook in somehow, and so I did that and now I have this issue to like, just go back and change all of the existing spreadsheet generation code to use that so that the next time that somebody goes to copy paste it, they find the good code, no matter, yeah, yeah, yeah, no matter where they look, they find the good code and they copy paste that,

[00:33:08] **Ben:** Yo, I had the same exact thing. I created a cold fusion component. I think I call it something like. CSV serializer. And literally it just took a, you know, double array, like array of arrays and generated the CSV string. And I've created that. And then I had to go and replace it like 16 different places.

[00:33:27] **Ben:** Cause I'm like, Oh, I just can't not have this everywhere at this point. a different PR of course.

## [00:33:34] Security

[00:33:34] **Tim:** So one, one thing we do, this is part of our code because we're working in the credit card industry environment, to satisfy the PCI auditors. We have in our JIRA, part of our code review before anything's released to production, is we go through the OWASP top 10.

[00:33:53] **Ben:** Hmm.

[00:33:55] **Tim:** in practice, you know, I'll tell you the dirty secret.

[00:33:57] **Tim:** Most of the time people just go,

[00:33:59] **Carol:** Yeah, yeah, yeah.

[00:34:00] **Adam:** check, check, check,

[00:34:00] **Tim:** check, check, check. It's a checklist on every single one because during the audit, the auditor, they want to see, all right, who, who wrote the code, who reviewed the code, what was part of the review, and then who deployed the code. And those have to be all different people, which is tough because we have a small team.

[00:34:17] **Tim:** But, Yeah, so we do the OWASP top 10, but it is, I mean, you, it is good to at least stop when you're reviewing the code to see. You know, at least think about those things. So like, you know, is there a chance for injection here or cryptographic failures or server side request forgery? But you know, a lot, sometimes it's just like, I just changed the wording on a view.

[00:34:40] **Ben:** Yeah,

[00:34:41] **Tim:** check, check, check, check, check, check, check. There's absolutely no chance that's going to be bad. But when you're dealing with like right now, we're completely rewriting our, we're moving everything from Scala over to, to C sharp for ASP. net. And so that's, there's a lot there that we got to review.

[00:34:57] **Tim:** Yeah. If you think finding ColdFusion developers is hard, try finding some Scala developers. That's yeah. That's yeah. But yeah, C Sharp folks, there's plenty of those. So, but yeah, you're everywhere. You're everywhere with your blue screen of death if you're running CrowdStrike. But anyway, we'll talk about it in the after show.

[00:35:17] **Ben:** for, so, so you mentioned something that made me think of something else. You talk about always hitting the OAS top 10. And as a quick aside for listeners who may not be familiar with oasp, but I, I can never remember what it stands for. It's like open web application security project, maybe. I don't think that's quite right.

[00:35:34] **Ben:** And the top

[00:35:35] **Adam:** at least

[00:35:35] **Carol:** close. You're so close.

[00:35:36] **Ben:** Yeah, yeah, yeah. Is I, yeah. and, and the top 10 is the top 10 vulnerabilities that often get introduced into code. That's what.

[00:35:45] **Tim:** Yeah, so they, they kind of do a review every year of like, what were the security failures for that year and say, all right, here's the top 10 and like 2017, there's a whole bunch of them that were there and then there's like 2021, there's some new ones. Insecure Design was a new one, Software Data Integrity Failures, and then Server side Request Forgery was a new one in 2021.

[00:36:08] **Tim:** So I don't know what the CrowdStrike one would be. I was trying to figure that out, but insecure design, maybe.

[00:36:13] **Ben:** When you mentioned the top 10, it made me think of something, which is that the notion of a checklist for here's the stuff that we do when it comes to a PR. And again, this is just me being weird. I think for reasons that are 100 percent subjective and me just dealing with my own stuff. I can't stand the notion of a pull request template.

[00:36:35] **Ben:** And I don't know if this exists in all version control products, but in GitHub, at least you can create like a dot GitHub folder and you can put a template in there so that anytime someone goes to create a new pull request, it'll auto populate with this template where it's usually like, you know, make sure you mention your ticket number and make sure you've included reproduction steps and make sure you.

[00:36:56] **Ben:** Have already deployed your database migration scripts if they have to be migrated. And I get like, I don't know why it just rubs me the wrong way. I'm just like, let me just do my PR. I don't, I don't want to, I don't want to have to conform to your notion of what a PR should look like.

[00:37:11] **Tim:** Ben, you have a military haircut, but you're a complete hippie.

[00:37:15] **Ben:** I'm like, come on, man. But I,

[00:37:19] **Tim:** me do my thing, man. You don't, don't, don't, don't kill my buzz.

[00:37:22] **Ben:** think

[00:37:23] **Tim:** Harsh my mellow.

[00:37:24] **Ben:** So

[00:37:25] **Adam:** learned it from you, Dad.

[00:37:27] **Ben:** so much of stuff like that to me exists for the reason that, medical advertisements say, you know, if you're allergic to Allegra, don't take Allegra. You're like, well, yeah, of course,

[00:37:38] **Tim:** How do you know? How do you, do you take a like or a,

[00:37:40] **Ben:** but you know, someone did and they were allergic and had a bad reaction. And now we have perpetuity. And I feel like pull request templates are often like that. Somebody, you know, five years ago forgot to deploy a database script first and then production crashed. And now forever, we have to remind people to do that in the pull request template. And I, and I think that's the part that rubs me the wrong way.

[00:38:02] **Ben:** It's just like constant paying for other people's mistakes.

[00:38:06] **Tim:** I get that because what happens is what, I mean, let's be honest with our OWASP checklist, we're only doing that to satisfy the auditors, it's like, I mean, we're seriously that that's, I mean, In our natural progression of having learned to do the job, we realize you just, there's things you just don't do.

[00:38:25] **Tim:** but the auditors don't know who you are and your, your, your employees change constantly.

[00:38:32] **Carol:** They can,

[00:38:33] **Tim:** but they can't, from their, they can, right? From their viewpoint, it's a possibility that you have, because they don't audit your, your employees that hard, that, intensively. So, so you have a little checklist that says, yep, they at least thought about it.

[00:38:45] **Tim:** They saw it, their eyeballs saw it, and they clicked it. So

## [00:38:49] Mentoring

[00:38:49] **Adam:** So let's go back to, different types of code reviews for different people, right? So

[00:38:54] **Tim:** different strokes for different folks.

[00:38:56] **Tim:** that is a very inappropriate way to say what I said. It was a TV show.

[00:39:01] **Adam:** the, so again, this came up because we hired our, co op and so he's a junior developer. And so for him, when I do his code reviews, it's like a mentoring opportunity, right?

[00:39:11] **Carol:** I'm reading his code thinking. You know, what do I need to point out that he did really well? And what do I need to point out that there's room for improvement? And like, is he actually accomplishing what he's supposed to be accomplishing?no, that's a really great thing to call out. Like I've found throughout my career, whenever I am working with people who are learning and who are new to this, the best thing I can do on the PR is say, you did a great job here. Like, oh, what you did here is awesome. And there have been times when I wanted to throw a comment in there that was, you know, a little negative and instead I'll just go message them rather than making it Go across to everyone who now is on this PR to see that something was wrong.

[00:39:51] **Carol:** I just send a message, talk about it, give them a chance to learn, let them fix it, let them push it up, and then the rest of the team just assumes they caught this themselves. It didn't take a PR, but now they found it, and it gives them a little more credibility, and it also gives them the opportunity to learn without feeling like they've been embarrassed by it.

[00:40:09] **Tim:** You're a good person,

[00:40:10] **Carol:** I like teaching.

[00:40:12] **Adam:** sound surprised,

[00:40:13] **Tim:** That is, that is, no, no, I know she's a good person. I worked with her for years, but yeah, that, that's, I, I think. That's the one thing I don't like about code reviews is it feels like criticism and it's a very, you need, there's a skill in, he, he stopped being a patron, so I don't know if he listens anymore, but it, so Adam Cameron, sometimes a lot of times when he would like, like talk about stuff, a lot of times I felt he was being just critical and being a jerk. For many years, I had an issue with him and then I realized it's kind of who he was. And that was sort of his love language was like helping you get better. He really just wanted you to be better. but there's a skill in like being able to tell someone like, you know, there's something not right about your code and you need to, you need to take another look at it, without sounding like you're saying you're, you're bad at your job.

[00:41:06] **Tim:** And I think what you just said, Carol, is a great thing to say. You know, privately say, Hey, you might need to think about this. Try it this way. Here's how it could be better. Give them a chance to save face because all of us, we want to look good in front of our peers. so that's, that's a, that's a tricky balance of, of mentoring, but not sounding like a jerk.

[00:41:26] **Adam:** It's a, it's a skill you have to develop. I think that everybody's default, voice for writing is the same like voice or tone that they read with. Right. So Carol, you were talking about. you know, trying to bring criticisms to people privately, I would bet that, especially early in your career, you were, you were the type of person that really preferred those private, conversations when, when you were the

[00:41:49] **Carol:** early in my career, we didn't have code review. Let's be real here. I wrote what I want and we hoped it was right. I do. I do.

[00:41:59] **Adam:** point, right?

[00:42:00] **Tim:** You didn't have, you didn't have testing either.

[00:42:03] **Adam:** And I think that that, you know, just like you were saying with Adam, I think that his, it's not so much a love language, but you know, he reads with a, this person is trying to make my code better and make me better at my job. he kind of reads that intent into the words. And so I think that's why he writes that way.

[00:42:20] **Adam:** Right.

[00:42:21] **Tim:** I get that, but I'm the kind of person that's like, I want, I want affirmation for, I want an affirmation sandwich, right? Hey, you did really, really good. It works, really works well. That's awesome. Good job, Tim.

[00:42:33] **Adam:** But it's ugly as sin,

[00:42:34] **Tim:** but did you think about this and this and this, and there's probably a security flaw here. And this right here is probably.

[00:42:41] **Tim:** Probably pretty bad, but overall you did a, I want that sandwich. Give me that sandwich. That that's, that's my advice in giving like any sort of like constructive criticism, start with a good, with a, with a, an authentic compliment and praise, give them the criticism, give them the thing they need to work on and then end it with more, Praise.

[00:43:00] **Tim:** And that, that way that that little sandwich just goes down a whole lot easier than just like, dude, what the heck did you do on line 32? That is the stupidest thing I've ever seen. Are you crazy? That

[00:43:10] **Adam:** Well, but okay.

[00:43:12] **Tim:** right.

[00:43:13] **Adam:** It's not a, it's not a binary. It's not a coin where you either do the sandwich or the, the plate full of right? Like there's, you can be.

[00:43:22] **Tim:** ducks in that

[00:43:23] **Adam:** Yeah, you can be more direct and, so here's my, my issue, and I was gonna say, until you started with the second half of that, like, you know, just like the, the negative attitude one as the alternative to the sandwich, until, until you started that, I was gonna say, I disagree, right?

[00:43:40] **Adam:** And because I, I don't, I don't say, I don't want to say that I agree with the second one, but I do disagree with the first one. I think that, Everybody knows about that trick now, and so when it happens to me, I see right through it, and I'm like, this person is just trying

[00:43:54] **Tim:** Well, that's because that's because the, that's because the initial compliment is not sincere. It's like, Hey buddy, you did a really good job, but. Right. You, you gotta find something genuine and most people don't take that time to do that. They don't take the time to really say, Hey, you know what? You did this.

[00:44:09] **Tim:** And I never really thought about that. It's pretty cool. It's really awesome that are, you know, but some, you know, to be fair, sometimes people just do a crap job and you just got to call a crap sandwich with a crap sandwich, right? So, but, but yeah, if, if you can find something positive to

[00:44:24] **Adam:** I mean, yes, okay, just full stop, period, right there. If you can, find something positive to say. But I don't think that you need, personally, I don't think, I don't believe in the sandwich.

[00:44:33] **Tim:** okay. We agree to disagree. I've always been taught that I've always tried to do that. And when I don't do that, it goes badly. So.

[00:44:42] **Adam:** Anyway.

## [00:44:44] Breaking Up Large Commits

[00:44:44] **Ben:** I do think that there's a lot of credence to people make a joke about this and it's a, it's an entirely accurate joke that if you have a pull request that has one line of code in it, you'll get 10 pieces of feedback. And if you have a pull request that has a hundred files in it, you'll just get a thumbs up.

[00:45:01] **Ben:** You know, that's totally 100 percent accurate. and, and one of the few pushbacks that I have where I'm like, please change this before we review it. If I see a pull request that has too many things happening in it at one time, I'll, I'll ask people, I'm like, can you break this up into smaller PRs?

[00:45:21] **Carol:** Yeah. The answer's no, Ben. Review all 86 files. I'm sorry. I didn't make the application this big. It's not my fault.

[00:45:30] **Ben:** I'm not saying, I'm not saying that it's a, it's a, like

[00:45:34] **Tim:** you know how hard it is to fix those, those those commits?

[00:45:37] **Ben:** No, but sometimes it's not that it's one change that covers a lot of files. Some people will just fix like seven different bugs in one PR. And I'm like,

[00:45:45] **Carol:** a breakout. Yeah.

[00:45:46] **Ben:** let's, let's,

[00:45:47] **Tim:** Yeah. That's lazy. That's, that's lazy. Yeah. That, that's lazy commits,

[00:45:53] **Ben:** The one thing, in, in the Golang projects at work, they, include their vendor folder. That's like if in the node world, that's the node modules equivalent. And they'll include that in the commit itself. So you'll get these PRs and it'd be like

[00:46:09] **Carol:** Oh my goodness.

[00:46:09] **Ben:** 000 files changed. And which, fun fact, GitHub doesn't love rendering that.

[00:46:15] **Adam:** Yeah.

[00:46:15] **Ben:** and it, and I'm like, bro, what did you do? And I'm like, oh, I updated a bunch of vendor files. It's actually only two lines of code that were changed in the main file. You can just ignore everything that's under slash vendor. And I'm like, oh, did you not have put that in a separate PR?

[00:46:31] **Tim:** right?

[00:46:32] **Adam:** One thing that I do like about the GitHub code review interface, they, they made some changes not too long ago where you can, like they added like a file browser on the left side, you can toggle it off and on, but in those situations, you can just sort of like collapse the whole vendor folder and there you go.

[00:46:47] **Adam:** There's the like one file left and you click on that and it takes you to it in the, in the view. It's nice.

[00:46:51] **Ben:** Yeah, that is true. They've made some really nice usability stuff. GitHub's a pretty solid product. I know, I know Carol used Bitbucket.

[00:46:59] **Carol:** don't know what I use right now. It's very confusing. We were on like TFS and now we're on something else. I don't even ask where it is. The code's there. It works. We're moving to GitHub Enterprise. However, right now it is definitely on prem doing something. So I've given up. I will tell you, we have a problem right now in our code review process, if you would like to hear that.

[00:47:21] **Carol:** Please do hit

## [00:47:22] Side Effects

[00:47:22] **Carol:** Yeah, so we have, this checkbox that says, you know, do you want to require that the work item be associated with the PR or is it optional? So we've migrated

[00:47:33] **Tim:** What's, what's the, wait, what's the word you

[00:47:35] **Carol:** optional. Yeah. Yeah. Sorry. I'm a little Southern still and congested. So. No,

[00:47:41] **Tim:** I thought you said off Shell. I'm like, what's

[00:47:43] **Carol:** It's required or optional. so we have it set to optional right now.

[00:47:47] **Carol:** So if you don't associate a work item, it just gives you a warning that says, are you sure you want to like a, like complete this, even though there's no work item associated to it? Well, we have a like transition from an on prem ADO to Azure DevOps ADO for all of our ticketing. However, none of that is currently linked to our repos.

[00:48:08] **Carol:** So you can't actually link a work item. So I found out yesterday that my developers and a few other have been going in and taking their work item from our current system. Going into the old system, creating a mirrored work item just to get rid of that link. So now our old ADO ticketing system has all of these orphan stories that no one's looking at, no one's doing anything with.

[00:48:35] **Carol:** They're just created so someone could get around a warning. So, I have a meeting later this week, so I'm going to probably get rid of that warning temporarily and get people to just put like a coffee and paste a link, a PR to a story until we actually transition to GitHub Enterprise, at which point then this becomes a non issue.

[00:48:52] **Carol:** But I was like, you're creating stories in the old ticketing system? Why?

[00:48:59] **Adam:** Yeah.

[00:49:01] **Ben:** It's just a perfect example, though, of how far users will learn to work around certain

[00:49:07] **Carol:** And never say anything. Yeah. Yeah.

[00:49:13] **Tim:** it's, it's an optional, optional, we're stuck in my head from you Carol, it's a cautionary tale. It's like, so there are organizations within our corporate umbrella that seem like to me, they spend more time worrying about getting the ticket right. I mean, days and days working on getting the ticket right and making sure that the ticket has like all, you know, the requirement requirements are good, but it's like, it's just this whole ticket grooming thing.

[00:49:46] **Tim:** They just keep grooming the ticket and the backlogs

[00:49:49] **Adam:** And it ends up being 20 minutes worth of dev work.

[00:49:52] **Tim:** instead of frigging working on the problem. I asked for, I asked for a text change on a, on a page and they're still grooming the backlog and the tickets. I'm like, are you serious? If this were me, I would have been done with this. Today. Today.

[00:50:05] **Carol:** we use the No, no, no. It's a good rant actually. We use the whole like MVP, right? So what is the, the least amount that we can do to get this out into production? So, you know, once we got there, we're like, okay, this can actually be broken up into like 10 phases. All you're going to get up front is a page that shows the data.

[00:50:24] **Carol:** Then you're going to get the option to edit it like on each row, and then we're going to give you like bulk actions. We're going to do the least amount and we're not going to groom it because we don't even know if you're going to use it when we put it in production, right? Like that's it.

[00:50:37] **Tim:** But where do we build the time? Where do we build the time, Carol? And the way we build the time for the meetings that we have to talk about where we build

[00:50:43] **Carol:** know about you guys. Yeah. Yeah.

## [00:50:49] Rubber Stamping

[00:50:49] **Adam:** how close do you guys come to a rubber stamp for PR code review

[00:50:53] **Carol:** What do you mean by a rubber stamp?

[00:50:55] **Tim:** Oh, me? I'm a hundred percent rubber stamp. No one expects me to review anything. Honestly,

[00:50:59] **Adam:** Well, yeah. So to answer your question, Carol, a rubber stamp is like, you know, barely look at it or, you know what I mean? Like, like just, like, like Tim was saying, nobody expects him to approve it. He's just, they're going to send it to him and he's going to say, read the title and say, yep, that sounds

[00:51:13] **Carol:** I would be heartbroken. Like it would actually make me very sad if I knew I was putting out PRs and that's what my teammates were doing, but they were just rubber stamping it.

[00:51:23] **Tim:** the rest of the rest of the people do it. Just, just not me.

[00:51:25] **Carol:** mean, I, I put time in,

[00:51:27] **Adam:** I mean, I guess what I'm getting at there, what I'm getting at there, like we talked about sort of the, the beginner end of the code review spectrum, and I'm getting, you know, more at like the opposite end of the spectrum here, right? So if I've got these same coworkers that I've been working with for more than 10 years, you know, we all know each other's skill level.

[00:51:45] **Adam:** We know each other's blind spots. We, the, the things that we tend to mess up. I have the guy on my team who misspells everything. And no, Tim, it's not you. And, you know, that sort of thing, but like, you know, I read their code differently, this is kind of like why this whole thing came up, right? I noticed just, I noticed myself reading their code differently.

[00:52:07] **Adam:** Like, I'm not looking for the mistakes in the same way that I look for them in the newbies code. And I feel like either that's wrong and I need to fix it. And I'm kind of like, you know, confessing here and trying to tease out from you guys is that. Is that a bad idea or it's the, it's like code review should be a spectrum and that's, you know, what the

[00:52:30] **Carol:** so like for me, I don't look for spelling errors because I assume if you spelled it bad once, you spelled it bad everywhere or it wouldn't work. So it's gonna probably run fine, even if you spelled it wrong. I don't really care about that. Even some of the syntax, like, you know, depending on how you do your if and you end it, right?

[00:52:48] **Carol:** Like just there are little things that I could go nitpick through. I'm more just read the functionality. Like, I want to understand, like, what you were trying to accomplish and how you accomplished it. I enjoy, like, reading PRs and going through code review and taking the time to learn more about my teammates and about, like, what our system is accomplishing and where the shortcomings were in it.

[00:53:09] **Carol:** So, again, I go back to, I would be upset if people weren't actually taking time to review my code and they were just rubber stamping it with, like, She's the architect. So clearly she knows what she's doing. Approve. I'm not going to challenge her. Like I, I want to have that feedback. So I provide that feedback in time.

[00:53:26] **Carol:** So I don't know that there's a right answer for everybody to just follow. And it's different on your comfortability and like your, your, how confident you are in the people you work with.

[00:53:38] **Tim:** I would. So I'm going to retract what I said. I'm, I'm not a rubber stamp. I do tend to, because a lot of things that are, they're small changes, but I would kind of say the, almost the converse of what you said, Adam, based off who the person, I don't really care who the person is doing it sometimes. Yeah. I get like, I've learned certain people's, you know, shortcomings and, and I know what to look for.

[00:54:01] **Tim:** At my position in the company, it's already been reviewed. A couple of times by the time it gets to me. What I'm looking to do is when I review something, my job is to make sure I'm protecting the company. Is there, is there a bad actor who's trying to steal credit card data? It's pretty much what I look at.

[00:54:20] **Tim:** I go, is there anything in here that it, that if an auditor looked at it would say, this is not good, or, or if a security expert looked at this would say, Hey, this is a problem that's focus I come to, so if I see it's just a And it's just like text changes, rubber stamp. But if it's like a little bit more involved and I don't understand why, you know, why are you doing this?

[00:54:43] **Tim:** Also, like we can't call anything external that's not whitelisted. And that's just, sometimes our developers kind of forget that they're like, Oh, this works in development, but development isn't blocked from the outside world. So you can go grab, you can go grab a library externally. But when it goes to production, that's completely going to break.

[00:55:01] **Tim:** And that's bitten us in the butt in the past. So I look at that kind of stuff. I'm like, where are you pulling this JavaScript library from? Is it hosted on, you know, you have to pull the file down and host it on prem. Are you trying to grab it from a remote source? Cause that ain't going to work. It's going to completely break.

[00:55:16] **Tim:** So that's. Because of my role, I look at it a little differently as, as compared to some of our developers we're looking at. Are you following good patterns? Is this an anti pattern or is this the best way to do it? Is this the best practice or is it not? is this an OSOP10 violation or is it not? By the time it gets to me, I'm looking to protect the business.

[00:55:37] **Adam:** That's a different kind of review. That's less of a code review and more of a, like a security review.

[00:55:44] **Ben:** I, I, if I can just illustrate the extreme end of the spectrum at

[00:55:49] **Tim:** Love it.

[00:55:50] **Ben:** You know, shutting the company down. We have three engineers left managing two platforms and like 130 different repositories written in a variety of languages.we are on the 100 percent it is rubber stamped because we are just covering, you know, sock compliance at this

[00:56:08] **Tim:** What are they going to do? Put us out of business?

[00:56:10] **Ben:** and, you know, like, like the reality is the people who are here have to some degree opted in to wanting to see the company to the end. And for me, that is a certain degree of trust affordance. And like, if one of you was going to do something crazy, you know, like we'll, someone will let the criminal justice system figure that out.

[00:56:33] **Ben:** Like, that's not my

[00:56:34] **Tim:** Right. Exactly.

[00:56:37] **Carol:** that

[00:56:37] **Tim:** a very unique situation you're in Ben. I gotta admit that's, that's kind of crazy. It's kind of like, all right, we shut down the store, but we're still making a few

[00:56:45] **Ben:** Right. Yeah, exactly. Exactly.

[00:56:47] **Adam:** Yeah. I mean, you're, you're not going to have a SOC 2 audit next year, so you don't have to worry about, did you stay compliant with all those things? Right.

[00:56:55] **Tim:** Yeah. I dropped that doughnut on the floor, but you know what? It's still edible. So.

[00:56:59] **Ben:** But I do think that there is a spectrum. I think there has to be a spectrum.

[00:57:04] **Tim:** Hmm.

## [00:57:05] Running Code Locally

[00:57:05] **Ben:** You know, if I can illustrate it with something very concrete, The security team, when we had a lot more security oriented reviews, the people on the security team would oftentimes like to actually pull the code down and run it locally as part of their review. And I always thought that was more than needed to be done.

[00:57:27] **Ben:** But if I was just a regular engineer looking at another regular engineer's code, I would never pull their code down and try to run it locally. Like my review happens in the GitHub interface because my role as a reviewer isn't to catch bugs. My reviewer is to provide guidance where applicable, maybe by chance to catch something that's totally wrong.

[00:57:50] **Ben:** I can, I can, I can really.

[00:57:52] **Adam:** developer has a professional responsibility to make sure that their code is going to run before they put it in for code review.

[00:57:58] **Ben:** Right, right. But so I've seen like, as, as part of the nuance there, right. I can understand where the security people are coming from because they have a different goal, so to speak, like they don't want to open up a vulnerability, which is somewhat different than does this code look like it'll work and is the business logic kind of right.

[00:58:15] **Ben:** And I, so I, I wouldn't want to put in the level of effort that the security reviewers put in. If that helps kind of just add some color to the, how much work it's not unified. It's some people get more work, some people get less work. I don't know that maybe that wasn't the best example, but I

[00:58:34] **Carol:** pulled people's code in and ran it locally during a PR and use that as a chance to go, okay, I see this probably is going to fail over here. And rather than trying to put it in a big comment explaining how to do it, I will pull the branch down. I will run it locally, build the test scenario, send it all over and go, hey.

[00:58:54] **Carol:** Like, this is how you get to it. Here's how I found the problem. And this is what I think might be a solution. So I mean, I definitely have done that and I don't, I don't think it's a bad thing. I don't think that it's necessarily a tester's job to find every scenario. If I can see the fail up front and the PR.

[00:59:11] **Adam:** a clarifying question here, Carol. So I feel like this may be something that we've talked about in the past where like the, the best bug report is a failing test case, right? Like a pull request with a failing test case. Is that what you're saying you're doing for the, the, like a code review? If you see something that doesn't seem right, you'll run it and add a failing test to, to say like, here's a thing that

[00:59:32] **Carol:** oh no, not, not even that. I just pull it in and I go into the interface. I'm like, okay, let me go open up this application. Let me do this process on it. Then I send you how to do it. That way you have the understanding of the full process that you just touched. Cause you didn't know where you were going.

[00:59:46] **Carol:** And this is where we now need test coverage. Cause it obviously wouldn't have gotten caught. And this is how you can duplicate it. And I'm not so sure that like my BAs would catch that in testing.

[00:59:57] **Adam:** Fair enough. Fair enough. Yeah. I'll, I'll, I will do the same thing. I'll pull it down and try to run it. But for me, it's usually like, I want to make a comment. I want to say, I don't think this is the right way to do it. Or I, you know, I don't think this is doing what you think it's doing. But I'll, I'll run it locally to prove to myself that I'm right before I leave the comment.

[01:00:15] **Adam:** Because I don't want to

[01:00:16] **Carol:** I know, right?

[01:00:17] **Adam:** Well, actually, if you try

[01:00:18] **Carol:** Agree. Agree. So Ben's just wrong again.

[01:00:24] **Ben:** like if I, if I have a, if I have a thought that I want to run the code, usually I'll just leave a comment with a, have you considered what might happen if X, Y, Z, and then at least that gives them the opportunity to say, Oh yeah, don't worry about it. We've taken care of it here or something. Like I just.

[01:00:41] **Tim:** Can you run it locally, Ben? Are you just running it on the server?

[01:00:43] **Ben:** No, I don't run it at all. I just look in, I just look in the pull request.

[01:00:48] **Tim:** I'm sorry. I'm sorry, Ben.

[01:00:51] **Ben:** Oh, you guys.

[01:00:52] **Tim:** in production. Let's see what happens.

[01:00:55] **Ben:** I don't know. I, I, again, like the, the notion of wanting to pull down the code to me feels like I'm taking on too much responsibility for this interaction.

[01:01:06] **Carol:** guess that's where I feel like every error on my team is my responsibility. So I tend to spend a lot of time in there because I own a lot of when something goes wrong.

[01:01:17] **Tim:** someone like you were working at CrowdStrike.

[01:01:22] **Adam:** Alright, well then I guess, that seems like a good place to wrap it.

## [01:01:25] Patreon

[01:01:25] **Adam:** so this is the part where I say this episode of Working Code was brought to you by YOLO Stamping Code Reviews and Yeeting Changes Into Production.

[01:01:31] **Ben:** Do it live.

[01:01:33] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:01:40] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock!as has been mentioned several times, tonight, I think we're going to talk a little bit about CrowdStrike on the after show.

[01:01:53] **Adam:** So Who was affected and, don't, don't give it away. Who was affected and, and,

[01:01:58] **Tim:** I think they know. I think they know.

## [01:02:01] Thanks For Listening!

[01:02:01] **Adam:** but yeah, the after show. so if you do support us on Patreon, then, you know, the outro music plays and then we just keep talking, until you get sick of us and, and pick a different thing to play on your podcast player, this episode is just, infinity long, so. That's how that works. If you'd like to get that and you wanna help us out on Patreon, you can go to patreon.com/workingcodepod and you can send us as little as $4 a month. as much as you would like. You can always do a custom and send us a thousand dollars a month. We won't say no.join our Discord.

[01:02:31] **Adam:** We had a bunch of new people join our Discord recently. It continues to grow, and we'd be happy to have you go to workingcode.dev/discord. Always fun place to hang out. That's it for this week. We'll catch you next week. And until then,

[01:02:41] **Tim:** I get to say this again after a month. Yay. Remember your heart matters. Even if you keep hitting the edge of the spa like Ben.
