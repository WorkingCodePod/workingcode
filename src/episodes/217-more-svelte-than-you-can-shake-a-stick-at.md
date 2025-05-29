---
title: "217: More Svelte Than You Can Shake a Stick At"
description: "In this week's episode, Adam puts the spotlight on Svelte, and takes us on a deep dive."
date: 2025-05-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/217-more-svelte-than-you-can-shake-a-stick-at/id1544142288?i=1000708570477"></iframe>

In this week's episode, Adam puts the spotlight on Svelte, and takes us on a deep dive of Svelte features, latest developments and some of his own applications of Svelte in recent projects.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/217-more-svelte-than-you-can-shake-a-stick-at.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** I got to start over, build my app with the latest svelte kit, the latest svelte, and I'm doing Postgres, how do I do a sign of the cross here?

[00:00:07] **Ben:** Now Tim needs to go get his new underwear.

[00:00:10] **Adam:** yeah.

[00:00:11] **Tim:** Yes. Postgres baby.

[00:00:13] **Adam:** How you talking?

[00:00:14] **Adam:** yeah.

[00:00:15] **Tim:** Can I side Quest for a half hour now? so

## [00:00:19] Intro

[00:00:39] **Adam:** With more svelte stuff than you can shake a stick at. It is show number 217. And on today's show we're gonna talk about se s Svelte stuff, uh, surprise, surprise, but first as usual, we'll start with our triumphs and fails. but it is my turn to go first, but before I do that, I will go ahead and mention, unfortunately, Carol's not able to join us.

[00:00:55] **Adam:** She got stuck at work today. So just the boys tonight.and I'm gonna kick us off with a two-parter, a fail and a fail young, I guess.

## [00:01:03] Adam's Fail and Failiumph

[00:01:03] **Adam:** so this last weekend as we're recording was Mother's Day. my wife had a pretty good Mother's Day by all accounts. and we have a, we have a family Discord, right?

[00:01:12] **Adam:** We have a Discord server that is just like myself, my brothers, and then, you know, like their wives and my mom is on it. That's basically it.andthat morning, Sunday morning, I, you know, everybody sent around the Happy Mother's Day messages on there, but my fail is, that was the only Happy Mother's Day I sent to my mom.

[00:01:30] **Adam:** I meant to call her later in the day, but I just got distracted and did not call and say Happy Mother's Day. And that's like, I think that's the first time I've ever not physically spoken Happy Mother's Day to my mom. So.

[00:01:40] **Tim:** Ooh, you're gonna hear about

[00:01:42] **Ben:** Yo, you're embracing the new social media lifestyle, right? It's like, I drop a happy birthday on Facebook and I call it a day.

[00:01:50] **Adam:** That honestly, that would be a better place to get ahold of her. She's like terminally on Facebook, as old ladies tend to do, and which is probably how you cornered the old lady market, Ben.

[00:02:01] **Ben:** We all need a niche.

[00:02:03] **Adam:** Yeah.so I feel bad about that. I mean, it's not like she's gonna hear this, she, this, I think this is the one thing that I've done with my life that is far too nerdy for her. Like she's always been the one that like hangs around and, and, you know, reads my blog or whatever and, and, would send me emails about stuff.

[00:02:19] **Adam:** And, and this is the thing where she's like, okay, well clearly this is too far off the deep end for me. She doesn't get it. So she doesn't listen to the podcast. But

[00:02:26] **Tim:** She called me and said, it's because I'm, I'm, I'm on it. And she just really takes issue with things I say

[00:02:32] **Adam:** you, well, you wanted a hater back in the day

[00:02:34] **Tim:** I did. I wanted to hate her. And, but it's like I can't reach her. I haven't been able to convert her. I, I converted outta Cameron. But your mom man, she's like, Tim, Tim, as long as you're on the show, I am not listening to that crap that comes out your mouth. And I'm like, my mom said the same thing. So you're in good company.

[00:02:51] **Adam:** All right. Well then, my fum, you know, we've been talking a little bit lately about, jump run, my app I've been working on, on the side, and it's actually getting used. I've got something like 60 I think, or 70, active users in there now. yeah. And so here's the thing. all the old people, you know, the, the guys that are 60, 70 years old that are, are getting kind of, sort of forced to use the app, they're like, the password has to be a minimum of 15 characters.

[00:03:17] **Adam:** What the Like, that is the only, yeah,

[00:03:22] **Tim:** 15 characters. What do you do to these guys?

[00:03:25] **Adam:** That is the only like strength password, strength requirement that I put in. And, and they're like 15 characters. I can't believe that. And I'm like, you're lucky it's not more.

[00:03:34] **Tim:** Just just tell 'em to use a phrase. Suggest like a phrase, right? Like the old horse jumps off the bridge. I mean, that's easy to remember. And it's more than 15.

[00:03:43] **Adam:** that's what I do.

[00:03:44] **Tim:** Yeah.

[00:03:45] **Adam:** So, and, but, and like, it's a, it's a failure because, you know, as I have to listen to these guys go, seriously, 15 characters, I can't just use like, you know, this one word,

[00:03:54] **Tim:** Love 69. No, you can't buddy. You used that. You used used that on everything since 1997.

[00:04:00] **Adam:** right. and, and, but it, the, the reason it's a fail mfin, not just a fail, is that I'm, I'm forcing these old dudes to have some sort of password security. So,

[00:04:11] **Ben:** There you go. dragging them. Kicking and grieving.

[00:04:14] **Tim:** Yeah.

[00:04:14] **Adam:** yeah. So that's what I got going on. How about you, Ben?

## [00:04:18] Ben's Triumph

[00:04:18] **Ben:** I'm gonna go with a triumph, which is that I have been continuing to dig into HTMX, which is a very lightweight front end

[00:04:26] **Adam:** You haven't, you haven't reached the bottom of that pool yet. It feels like there shouldn't be that deep of a topic.

[00:04:31] **Ben:** It's, well, it's so interesting and this is what's so, if, if I could touch on one of my pet peeves for a moment, I, I feel like there is in our industry this sense that,

[00:04:39] **Tim:** Well, he hasn't even started his, his thing. And he is already,

[00:04:42] **Ben:** this is a segment adjacent

[00:04:44] **Tim:** He's side questing.

[00:04:45] **Ben:** there.

[00:04:46] **Ben:** I feel like there's a lot of dismissal of the difficulty in learning things, and there's this sense that, oh, you know, there's just syntactic differences between languages and frameworks and like, yeah, they all have their own little caveats, but basically if you know one framework, you can learn another one, no problem.

[00:05:02] **Tim:** And, I feel like that's just never really true. It's like maybe there's flavors of truth there, but there are so many little intricacies and design decisions. And peccadillos, if I can quote, Goodwill hunting, Ooh,

[00:05:18] **Ben:** for each particular framework or library and the, it's just, you know, you start to pull that thread and, and you just start asking more questions and you realize that those questions don't have super clear answers and you gotta dig into that.

[00:05:30] **Ben:** Anyway, my triumph is that I'm, I'm, this is like, this is the first like real new, new thing that I've had to learn in a while, I think. And I'm, I'm, I'm enjoying the process of it and I'm enjoying the fact that I'm enjoying it. Meaning that I'm, I'm liking that learning feels good almost just for the sake of learning, which I know is maybe a not the best reason to be learning all the time, but there, there is some work applicability here, so I don't think it's gonna be completely wasted.

[00:06:00] **Ben:** And I, and I would like to use H-T-M-X-I think maybe in some of my personal stuff, but I dunno, I'm just enjoying the process of learning.

[00:06:07] **Adam:** The brain is a muscle. You know, you, you don't stop working out your biceps because you don't have a reason to have big bicep muscles. You just, you know, you keep, keep exercising it so that, that one day when you do need to lift an a car off an old lady,

[00:06:19] **Ben:** There you go.

[00:06:20] **Adam:** can deadlift that car man.

[00:06:23] **Ben:** And it's, so,

[00:06:23] **Adam:** yet another old lady in your fan club.

[00:06:25] **Ben:** it's also so, so interesting to think meta about learning in the context of ai because obviously I can't speak for a lot of people, but I do hear some people on interviews say that the more that they learn, the more that they use ai, the less they feel like they're able to think very deeply and very critically about things.

[00:06:47] **Ben:** Like their instinct is now to go to the AI and ask it questions before it is to just sit there and stare off into space and think about the problem, you know, on hard mode for a little bit. and what I'm finding is that I. I, I think I'm trying to still spend time in that hard mode where I'm not just going to the ai, I do go to chat GBT to ask it questions if I feel like I'm not finding a good answer.

[00:07:13] **Ben:** And, I don't know if it's just the confluence of technologies that I tend to lean towards, but AI just doesn't feel like it gives me good answers for this kind of stuff. but I, I'm, I'm enjoying just sitting there and stewing in the problems a little bit. So I'm gonna consider that a success, a triumph if you'll

[00:07:30] **Adam:** I will.

[00:07:30] **Tim:** So you're, so, you're, so you're just sitting in it, stewing in it,

[00:07:33] **Ben:** stewing sitting in my own juices.

[00:07:35] **Tim:** Yeah, I got code swamp butt.

[00:07:38] **Ben:** Swamp body, my friend.all right, well, Carol would be next, but, as Adam alluded to, Carol is stuck at work, enjoying the new efficiencies of the government. And, uh, so I will kick it over to Tim. Tim, what do you got going on?

## [00:07:56] Tim's Triumph

[00:07:56] **Tim:** I mean, I'm going for a triumph. It's, it's, it's pretty uneventful. My life is not too terribly stressful. But this week, so normally every year we have like the big, like corporate thing and that we go to, and this year they kind of are doing an experiment. It's run by a different group of people and it's, anyway, I was like,I'm really not interested in going, I don't really care to go.

[00:08:18] **Tim:** It's in Costa Rica. I couldn't get direct flight. I'm like, yeah,

[00:08:22] **Adam:** feels like you just got back from, what was it, Cancun?

[00:08:25] **Tim:** it was, yeah, it was, it was Mexico. It was, yeah, Cancun, but that was, yeah, so that was like November, but they moved it to like May. Which is my wedding. And like there's graduations, there's a whole bunch of stuff going on in May. So already I was like, eh, I dunno if I really want to go.

[00:08:40] **Tim:** And then I heard that we're try experimenting with a new format, which I do love about this, this, this conglomeration of companies that we're part of. They do, they do like to experiment on stuff. They're like, you know, this is working okay, but maybe we can make it better. And sometimes it is. And then they're like, no, that didn't work at all.

[00:08:57] **Tim:** Let's never do that again. which is cool. I mean, I, I, I, I admire the, the pluck, but yeah.so there's a whole bunch of folks missing from the company and I'm filling in, so I'm basically, he, they're like, yeah. So if anything goes wrong, all of leadership is gone. So call Tim.

[00:09:15] **Ben:** nice.

[00:09:16] **Tim:** Yeah. But it's, it's been pretty good.

[00:09:18] **Tim:** I'm sitting in a lot of meetings that I normally don't sit in on, but what I do, I, I think the thing I. My mission in life is to make meetings nice and tight and done. I, I like to chair. I like to chair. I hate it when you get to a meeting. It's like the person who's supposedly, like, it's their meeting right there.

[00:09:38] **Tim:** Yeah. Always has to be one person who's kind of leading the thing. And those people that just kind of let a whole bunch of, I, I love talking, I love joking, but I don't like doing it at meetings. I wanna get in, get out, get done. Right. Yeah. I, I'm not a chatty Kathy. During meetings, I will crack a joke just to stop someone from going on a rant.

[00:09:56] **Tim:** That's the only time I'll, I'll be funny, but I do that defensively to protect the meeting. 'cause it's like, listen, you are really going off on a rant here. we got 30 minutes for this thing and I can tell it's gonna take you 15 minutes to get this your butt. So

[00:10:12] **Ben:** Classic butt crawl.

[00:10:14] **Tim:** Yeah. Oh, those butt crawls. Yeah. Just stewing it.

[00:10:18] **Tim:** So, yeah, I, I, I've been, I've been coming on meetings and been just like, people start like going off on tangents, you know, and I, I shut 'em down. I'm like, all right, we, that sounds like another meeting to me. Or maybe you can send an email after this, but yeah, we're, we're staying on target here.so hopefully, hopefully the, the, the people won't come back and go, yeah, don't ever let Tim do that again.

[00:10:41] **Tim:** 'cause that was awful. But at the end of it, I'm like, I gave you 15 minutes of your life back, guys. So go, go work.

[00:10:49] **Adam:** it's, it's win-win for you, man. Either you're, you're doing a good job managing the meetings or

[00:10:54] **Tim:** I don't do it again.

[00:10:55] **Adam:** yeah. Or everybody hates it and they never ask you to do this again.

[00:10:58] **Tim:** I don't care. I don't care.

[00:11:00] **Ben:** are you done interviewing people? I know you said you were trying to meet everybody at this, kind of new department you're working in.

[00:11:06] **Tim:** Yeah, I'm still, I still got a few more stragglers. It, it's, it's funny, it's like I'm really okay with like the new people that I don't really know. 'cause I really do want to get to know them. It's the people that I've known a long time and I really wanna talk to them too. But at the same time, it's like I know the axes that they want to grind, and it's like, and so I have to be like, in a really kind of specific mindset where I go, all right, I'm gonna, I've known you like 15 years.

[00:11:33] **Tim:** I kind of know I have, I have a prejudice about what I think you're gonna say when I ask you these questions. So I have to be in the right frame of mind where I, I, I'm feeling very generous of spirit, which is, which is which. I'm, let's be fair, it's, I'm not always in that mode every day. So it's usually a Friday or, you know, you know, Friday four 30, I've already cracked a beer.

[00:11:57] **Tim:** And I'm like, yeah, I'll give 'em a call. Let's see what they got to say. So yeah, I'm working on it. I'll, I'll wrap 'em up soon.

## [00:12:04] Podcast Overload

[00:12:04] **Ben:** Nice.if I could take a quick moment and just mention one more triumph that I had this week, which was that I declared podcast bankruptcy. I have like 97 podcast episodes in my queue going back. And it's not just that they were all recent. It's like it's going back like a year and a half or something.

[00:12:23] **Ben:** I'm just like, I'm never listening to these.

[00:12:25] **Adam:** Dude, I think I listened to 90 EP 90 podcast episodes in the last like three weeks.

[00:12:31] **Ben:** Well, that's the thing is I listened to a lot of episodes, but it's just, it's a fire hose of content and I cannot keep up. So I, I just went through and I, I think I maybe kept two or three that seemed like, okay, I didn't even know that these were in the mix. But I, I wanna find a way to be better about processing that, that cue not, not better about processing.

[00:12:53] **Ben:** I sort of want to, what's the, like if it's not a hell no or no, if it's not

[00:12:58] **Adam:** it's not a, if it's not a hell yes, then it's a no. It's hell, yes or no.

[00:13:01] **Ben:** I wanna be better when I see a podcast comes in

[00:13:04] **Tim:** Marie Kondo, that stuff come

[00:13:06] **Ben:** yeah. And it doesn't immediately tickle me. Even if I can't, let's do it right now. If I, if it doesn't, if I'm not like, oh, that sounds good. I feel like I just wanna delete it.

[00:13:13] **Adam:** Mm-hmm.

[00:13:14] **Ben:** 'cause otherwise they just pile up and then things get lost and I feel crappy about it. And.

[00:13:20] **Adam:** That's how I've been. I, I do that, but it's, I allow myself to get a couple minutes into the episode first. Right. So, like, one that I've been listening to a lot lately is called Decoder. It's from the Verge. the, the editor in Chief of the Verge, his podcast and he has a lot of like CEOs on to talk about business stuff and.

[00:13:36] **Adam:** Just interesting people in the tech space. and I would say at least 80% of the episodes are actually really, truly interesting to me. So I listen to 'em, but then the rest, it's like, okay, you know, maybe 50 50 on whether I'm gonna get five minutes in it and go, yeah, don't care, delete. Or, or actually, okay, I'll, I'll, I'll leave this on in the background.

[00:13:56] **Adam:** You know,

[00:13:56] **Ben:** Yeah, I

[00:13:59] **Adam:** and I've, I've gotten better too at being a little bit more ruthless about like, okay, well my podcast backlog is starting to pile up again, so let me look at actually what I'm, I'm allowing to auto queue and do I really want this in there?

[00:14:11] **Ben:** That's, that's where I'm struggling right now. And, and the one that I think needs to go to the chopping block, unfortunately. 'cause I just don't listen to it. I don't make the time to listen to it. Is this American Life Working Code? Is this American Life? Every time I listen to a, this American Life episode, I remember how great a podcast it is, but it's just so tangential to anything that I feel like I'm doing in my life.

[00:14:38] **Ben:** Like it's just storytelling at this

[00:14:40] **Adam:** it's a fabulous gateway drug for getting into the, the hobby of listening to podcasts. But then once you like niche down and you're really into the podcast that you're into, it's like, eh, the production value is through the

[00:14:52] **Ben:** is so good, but that's a great phrase. You put niching down, like that's, that's what it is. I feel like I've found my sort of funnel of things that I wanna queue up, and I love this American life, but I just don't make time for it. And it's like, ha, like half the things that I had to clear out of the queue were this American life, unfortunately.

[00:15:10] **Tim:** at this point, as long as they've been on, I think they've pretty much chronicled like 98% of white, white life and culture. There's not, there's not a whole lot more that, you know, you can tell about the struggles of a deli operator in, in Hoboken that you know.

[00:15:26] **Ben:** Oh, kills me though. All right. Sorry. That's, I didn't mean to, I just Svelte good about, about pulling the trigger on that.

[00:15:33] **Adam:** Yeah, I mean, I, I, every now and then I'll hear, you know, I'll find a reference to something. Right. So there, i I, the last podcast I remember removing from my like subscribed podcast is the Amy Poer podcast. I think it's called A Good or a Good Hang with Amy Poer. And basically it's just, she's a famous person.

[00:15:50] **Adam:** She has other famous people come on and they have conversations. And the, the, the sort of kick for it is that, like before the person, so before Paul Rudd came on the show, she had a quick conversation with John Ham from Mad Men. And she, and I guess, you know, the three of them are all mutual friends, but Ham and Rudd are good friends.

[00:16:07] **Adam:** And so she's like, gimme some dirt on Rudd that I should ask him about. Tell me where the, the good stories are.and so like the, you know, every, I think I, I got myself hooked on that one. 'cause there was a, some, I saw a video clip of her interview with Jack Black, which was really interesting. So I went and I listened to that episode.

[00:16:21] **Adam:** I was like, yeah, I could, I could use more of this subscribed. And then like three episodes later, I'm like, eh.

[00:16:27] **Ben:** I.

[00:16:27] **Tim:** it fe it feels like every celebrity now has a podcast. If they're not like, actively like working like Conan, he has a podcast. He just got the, the Twain Prize. Recently I watched that, on Netflix. It's like every celebrity now has a podcast, and I don't, I don't know how they compete with us. I, it's just like, I feel bad for them. I

[00:16:48] **Adam:** They have to follow this

[00:16:49] **Tim:** mean, they have to follow this. I mean, I'd even try so.

[00:16:53] **Ben:** I do like the fact that my wife listens to, I don't, she, so she has a whole set of podcasts that she likes to

[00:16:58] **Adam:** doxing. Your wife here.

[00:16:59] **Ben:** but then, but then she does have podcasts that I think overlap in, interest but aren't podcasts that I listen to. But then, so we'll listen to them together sometimes in the car.

[00:17:10] **Ben:** And I like that amount of exposure. So like, one of the ones that she likes to listen to is smartlist, speaking of celebrities, which is, uh, um,oh God, say it again.

[00:17:21] **Tim:** Ferris? Tim Ferris.

[00:17:22] **Ben:** No, no. Smartless. It's, John, Jason Bateman,

[00:17:26] **Adam:** Oh

[00:17:27] **Tim:** oh yeah, yeah.

[00:17:28] **Ben:** the guy from Will and Grace, and then the other guy

[00:17:30] **Adam:** And Will Anette.

[00:17:31] **Ben:** Fam, uh, yeah. Will Ornette.

[00:17:32] **Ben:** Thank you. and it's like, it's really funny and I really enjoy listening to it, but I could never listen to it on my own. Like it would

[00:17:38] **Tim:** it's entertaining. It's not very educational.

[00:17:41] **Ben:** Yeah. I'd be bored almost immediately, except when I listen to it with, with my wife and it's, you know, it's fun and we can joke about

[00:17:47] **Adam:** Mm-hmm. Yeah. Like if you're going on a long car ride and you need something to

[00:17:50] **Ben:** Yeah, yeah, yeah,

[00:17:51] **Adam:** Alright, well, with enough discussing other people's podcasts outta, are we done with that?

[00:17:55] **Ben:** yeah, yeah. Let's do

[00:17:56] **Tim:** I mean, I mean they, they should, they should be paying us for

[00:17:59] **Adam:** Yeah. Right. Not sponsored

[00:18:01] **Tim:** not, not, not sponsor, but you're welcome, smartless.

[00:18:03] **Ben:** That's right. We're just paying it back for all the times they've plugged us, you know.

[00:18:06] **Tim:** Yeah, exactly.

[00:18:07] **Adam:** A little reciprocal.

[00:18:09] **Tim:** Yeah. Little reciprocal tariff. Little reciprocal anti tariff there.

[00:18:14] **Adam:** Oh God. Oh, okay.

## [00:18:15] Diving into Svelte

[00:18:18] **Tim:** And on that note Svelte stuff, let's talk about veYeah. I'm out

[00:18:19] **Tim:** yeah, uh, pardon me. I have to go put on clean underwear. you're white on underwear

[00:18:24] **Adam:** so, these guys were asking me like, you know, what's new? And s Svelte stuff and I, there is some new stuff, you know, we're not really a, a topical news show, but there's some new stuff coming up and, and it made me realize, like we've really never kind of dove into what makes Svelte different than other things like React.

[00:18:40] **Adam:** And so, yeah. I, that's a weird like, turn of

[00:18:44] **Tim:** dove, divin,

[00:18:45] **Adam:** yeah. So, I thought, I thought it would be a good opportunity to just like, a little bit, not, not super technical, but a little bit, let's talk about the differentiators between just like, let's say Svelte and react and, What makes me choose Svelte, and then, you know, where things are at, what's coming, what's new and exciting.

[00:19:03] **Ben:** So, Can we, can we, before you dive into the, the meat, the nut meat of

[00:19:09] **Adam:** I have divin Go ahead.

[00:19:12] **Ben:** can we just get some, uh, some, let's like anal analogous words that people might think of. So, and maybe I'll try to say this to you and you tell me if I'm right or

[00:19:22] **Adam:** you guys are the, the peanut gallery and the devil's advocate here help, help the listener out

[00:19:26] **Ben:** so Svelte is to react

[00:19:30] **Adam:** uhhuh,

[00:19:31] **Ben:** at, like, Svelte kit is to next js.

[00:19:36] **Adam:** correct? Yeah. So svelte is a library that you can use to manipulate browser ui. Okay. Just like React svelte Kit is an additional layer or library you can compose with that. That adds basically file-based routing and some other niceties for doing a full stack application.

[00:20:00] **Ben:** And so like next, JS svelte was a standalone client side library for years before svelte kit came out.

[00:20:12] **Adam:** you said like next JS Svelte is a

[00:20:15] **Ben:** Oh, sorry, sorry. Like, like, so like, like React, so svelte and react were basically were, were primarily client side for years. And then they both have now evolved to have server side components. Not components in the component sense, but components in in aspect

[00:20:30] **Adam:** a full stack framework. Yeah.

[00:20:32] **Tim:** see, even, even that was educational for me. I I had no clue.

[00:20:35] **Ben:** There you

[00:20:35] **Adam:** just 'cause you don't listen to me when I talk

[00:20:37] **Tim:** I, yeah, I glazed over when you talked about Sveltel.

[00:20:41] **Ben:** And I've heard the term rro.

[00:20:45] **Adam:** Uhhuh.

[00:20:45] **Ben:** and I know that there are a lot of frameworks that are talking about signals and would ruin be like a signal equivalence.

[00:20:51] **Adam:** Yes. So ROEs is sveltes implementation of signals.

[00:20:56] **Ben:** Okay. And that was new with Svelteled

[00:20:58] **Adam:** of concept and ROEs is the implementation.

[00:21:02] **Ben:** All right. Cool. All right. Now everybody has our mental models for the, the,

[00:21:05] **Adam:** Well, there was one thing I wanted to point out. So you had talked about how like for years and years react and svelte were client side libraries and then you have to add a versel or, or not Versal,next JS or svelte kit. I just wanna acknowledge before there was Svelte kit, there was a similar project by the same people called Sapper.

[00:21:24] **Adam:** So you had svelte and sapper and that was, Sapper was the original full stack framework for doing full stack svelte apps, apps. They just kind of, they, they were working on it, working on it, working on it. And they got deep enough to the point where they were like, we really wanna re just like, throw it away and start over and, and re-architect this from the ground up to be better in all these, like, implement all these lessons we've learned.

[00:21:48] **Adam:** And so they were like, instead of like making Sapper 3.0, we're just gonna throw it away and start on something new. And that became s Svelte kit. So,it's the spiritual 3.0 to Sapper, I think. But

[00:21:59] **Ben:** Gotcha

[00:22:00] **Adam:** so Okay. Vocabulary established. Any other,

[00:22:04] **Ben:** established. Check.

## [00:22:05] Routing

[00:22:05] **Adam:** 'cool. So, a big thing, okay, this is also true for next js.

[00:22:12] **Adam:** So for people that are doing React and next js, a, a big thing that you get from these full stack applications is the router, right? So most, usually these days it's file-based routing, right? So you have folders, and in those folders you put files and you can put other folders and deeply nest them, whatever.

[00:22:27] **Adam:** But that determines what the URL is going to be. Right. So you put, you create a folder called fu and a folder called bar, and then a file called bjs or whatever, and that, that might give you fu slash bar slash b as your react or your, your next Js path in, in Sveltel kit. It's a little different. and you know, they, there's, it was a very, what is the word that I'm looking for?

[00:22:52] **Adam:** heated discussion, like the kind of a, a mercurial people had a mercurial response. Either people either tended to love it or hate it, but this is the way that Svelte kid does it. Every part of the URL is in, is set up by folder names. And then, so if you're, if you want that same, you know, slash f slash far slash f bar Boz, then you have to have that, that Boz also has to be a folder.

[00:23:17] **Adam:** And then in the Boz folder you create a plus page dot Svelte. That, that that a file that's plus page do svelte is like, okay, that's a, that's saying this is the leaf node of that URL, right? You're, you're building up sort of a tree there.and you don't get a page in the URL, it's just, you know, fu bar B.and then so you've got plus page dot svelte, that's the view.

[00:23:38] **Adam:** And then you can do like plus page server js or Ds, and that gives you a server side only executing, data loading function. So when you, when you hit that URL, if there's a plus page, do server do ts, I'll just say, 'cause that's what I do. then the, you can kind of think of it like a code behind from like a vis,C plus plus or C what is itp.net?

[00:24:02] **Adam:** That's the what I'm thinking of, like. You hit the url, if there's a plus page server ts, it'll run that on the server side. Whatever data gets returned is available. Then to render the view, it renders the view server side, sends it down to the client and hydrates that all on client side.in addition to that, you can have a plus page ts, so it doesn't have the dot server in the file name and that is similarly, it can be like a data loading and or UI logic, file where you can have, you know, all logic, no, no view, of the code.

[00:24:35] **Adam:** andI don't use that one a ton, but that's there. So you've got those three files, right? And then you can also have like a plus layout ts. Similarly, you can have a layout ts and layout Svelte that like wrap everything in that folder.

[00:24:48] **Ben:** Okay.

[00:24:49] **Adam:** and then so the, this is where it gets interesting. so svelte kit really makes it easy to.

[00:24:54] **Adam:** Have type safety when you go from the server to the client. That was always something that bugged me when I was doing next JS and React. Now granted, I will say I stopped doing next JS like five plus years ago. I think it's hard to believe it's been that long, but I'm pretty sure that's roughly accurate.

[00:25:11] **Adam:** and so there's a very good chance that they've fixed this problem since then. But, it's the spate uses dynamically generated types. Like you run the dev server and it like generates these sort of ghost files that don't really exist, but the dev mode thinks it does exist, whatever that have types in it based off of what you're returning from your load function.

[00:25:30] **Adam:** And then in the client you get all the TypeScript hints, like know you type data dot and it's got like, this is what your load function is returning so you can easily, do all that stuff. You get, so you get type safe server to client data transfer, which is pretty neat.and you don't have to do, you can, but you don't have to do like, The a validation framework, you don't have to use like a Zod to validate the data you get on the, on the client side. Just nice.

[00:25:53] **Ben:** I know you had talked about using svelte at AlumniQ to get some modals implemented. Did you ever get svelte kit at at AlumniQ, or this was all client side stuff?

[00:26:04] **Adam:** yeah, so that, that app you're talking about with the modal, that was only svelte, and I believe that was during the Sapper days or maybe very early svelte kit. And it was just like svelte KIT was available, but it was kind of beta and they were like, yeah, you probably shouldn't use this in production yet.

[00:26:19] **Adam:** So, and also, yeah, well also, like, it just wouldn't jive with, you know, we've got this gigantic CFML monolith and I'm not gonna just, okay, now we need to spin up this other container just to run this one little modal on one page. You know? So, I made it work with just Svelte, which was fine. It, it works well and it's still still kicking.

[00:26:41] **Adam:** and it, it still does its job just well. and, to answer the question though, I do have a svelte kit application in production at work. It is an internal application. It's our engineering team dashboard, right? So every now and then I'll share screenshots of like, charts and you see like a sort of a very dark blue background and, charts or whatever.

[00:27:00] **Adam:** And that's, that's from my engineering dashboards where we can monitor, you know, mail volume and, and transaction volume and tickets and outgoing mail status and stuff. So, that application, it, it's been nice because it was a good way to kind of kick the tires and, get, you know, my head around stuff like I've built a few little teeny tiny things was Svelte up until that point, but really never got the opportunity to build something significant with it.

[00:27:27] **Adam:** It's, it's one thing to be exposed to a new tool and be like, Hey, we should rebuild everything in this. And then it's a totally other thing to actually get your feet wet and actually like start to understand this is where it gets hard, this is what's, what makes it difficult as compared to, you know, c fm l or whatever other thing that we're doing.

[00:27:45] **Adam:** and so it's been a

[00:27:46] **Ben:** difficult compared to CFML.

[00:27:50] **Adam:** you can believe that. so, you know, I, it, it's been a good opportunity to do that. And, I think early on in that process I was very gung-ho, like, okay, cool. Now I know and I need to know, I started building like our own little, component library, right. just like we right now, like, just like you mentioned last week, you're doing bootstrap and, and all that stuff for your.

[00:28:10] **Adam:** Your new job. our application is so old that it, it was, created when Bootstrap, I believe three was the new hotness. Um,so, so quite old. And we still use Bootstrap three. and, so it's got some growing pains or whatever, but one of the things about that is that, you know, we've got the CSS for these various components or whatever, but it's not super consistent from form to form, right?

[00:28:35] **Adam:** You might have, you might choose to do a, a two,you know, if you're doing your column widths for like the label and then the text input, right? You might do two and not, or whatever. It's 12. So you might do two and 10 or then three and nine on different pages or whatever. So you're just getting a slightly inconsistent experience.

[00:28:52] **Adam:** Or you might do labels to the side or above or whatever. And so these are the kinds of challenges that I was really trying to dive into with that component library is like. Let's build the, the atoms and the molecules to have a very consistent experience. And then if and when we find accessibility bugs or whatever, it's like we fixed it in one place and boom, it's fixed across the entire application.

[00:29:12] **Adam:** That was the idea. we, we've still not really completely dn doven into that pond, but it's there, kind of waiting for us. And, it, it's funny 'cause the, the more I work on jump run, so Okay. Setting all of that aside now, I more recently, like, two to three months ago, I started this jump run project.

[00:29:33] **Adam:** So I, I get a fresh, clean sheet, right? I'm on all the latest versions of everything.and it's different, right? The, the engineering dashboard was originally written in svelte four, which did not have ruins, right? It was the. You're, if people are familiar with Svelte pre-run, basically it's like, you know, let X and then down in your page you just do bin on on an input.

[00:29:54] **Adam:** You do bind to X bind value equals x. When you update the input, the the X value updates and anything that else is displaying x gets updated automatically and stuff. It's, that's nice. But it had some drawbacks in terms of like the compiler, right? It made it difficult for them to efficiently understand like how to build the application.

## [00:30:15] Signals and Reactivity

[00:30:15] **Adam:** And, it basically they were, they Svelte kind of hamstrung by it, which is where signals came in.I don't really wanna dive too much into, I mean, I feel like I've been talking a lot.so basically, you know, like, it, it, at first glance it looks a lot like, use, the, like react hooks, right? You've got your like used state used effect.

[00:30:32] **Adam:** There's a, there's a state ruin, there's an effect ruin. They visually looks similar, but they behave. Kind of differently in, in a lot of ways. But that's basically the idea is instead of making assumptions about what needs to be reactive, the, the ruins just allow you to like do stuff and market as reactive.

[00:30:51] **Adam:** You can kind of think of it as like annotations and say, this needs to be reactive. And anywhere it gets used, it's the compiler is now aware of that,

[00:30:58] **Ben:** But this is still all client side stuff. Runes don't really, there's no real meaning for run on a server set. Right.

[00:31:04] **Adam:** Correct. Yeah. The, I mean, your server side is very, what's

[00:31:08] **Ben:** data out of the database and

[00:31:10] **Adam:** Yeah, it's a, it's like a pure function, right? You've got some, you look up some data, you execute the function, you get your output, and that's what it is. It's not gonna change a bunch of times on, on the server side, on, so

[00:31:21] **Tim:** So, so is is Svelte kit, how's that compare to like node js? Right, so node js is the server side

[00:31:29] **Adam:** it is, yeah. So server, so node is just the server language, right? The node. You can't run Node client side, you run your client side JavaScript in the browser,

[00:31:41] **Ben:** you need Node to run svelte kit,

[00:31:44] **Adam:** correct? Well, it can be, yeah. Yeah. It's gotta be, it's gotta be JavaScript runtime, which could be node, could be bun, could be Dino, could be

[00:31:50] **Tim:** Okay, because I, I thought there was some connection there between the two. So you do, so you can run node js server side with svelte kit.

[00:32:00] **Adam:** Yes.

[00:32:00] **Tim:** Okay.

## [00:32:01] Starting From Scratch with Svelte

[00:32:01] **Adam:** So, I got to jump run. I got to start over, build my app with the latest velt kit, the latest svelte, and I'm doing Postgres, how do I do a sign of the cross here?

[00:32:12] **Ben:** Now Tim needs to go get his new underwear.

[00:32:15] **Adam:** yeah.

[00:32:15] **Tim:** Yes. Postgres baby.

[00:32:18] **Adam:** How you talking?

[00:32:19] **Adam:** yeah.

[00:32:20] **Tim:** Can I side Quest for a half hour now?

[00:32:23] **Adam:** so I dare you to try,So it's, it's been fun. It has a couple of times kind of bitten me because I've had to like go back and work on the old application and now I've like overwritten all that part of my, my brain space that had this Svelte floor knowledge was Svelte five. I'm like, oh wait, how does this work again?

[00:32:40] **Adam:** How do I, how do I do dynamic data stuff? Oh yeah, okay, I have to go find that old docs and stuff.but for the most part it's been good. There's one thing, this is not, I guess this, this, I do believe this is from the latest version of Svelte kit. so there's a, there's a really neat thing. So I talked about the, the loader functions, right?

[00:32:59] **Adam:** So you've got your plus page dots Svelte, that's your view, template basically. And then you've got your like page server, or I'm sorry, page server Ts and page Ts, and those can return data and that data then becomes available to the view, in your view. It's also, you can think of it as like a JSX file, right?

[00:33:18] **Adam:** It's, it's, it looks a lot like HTML, but it's really kind of JavaScript under the hood. So you can do some scripting in there, and so you can import, a JavaScript function. There's invalidate and then there's invalidate all, for all intents and purposes, they're the same for this, for what I'm talking about now.

[00:33:34] **Adam:** and basically you do, if you call the invalidate all function, it just tells Svelte kit, like, okay, that data that you got from the load function, re-execute the load function and give me a new copy of the data, which is super handy, right? Instead of having to make, if you've got a, a table of data and you've got some other stuff on the page, it's all updated or it's all, based on data from the database.

[00:33:55] **Adam:** You just make one quick function call instead of having to make four different fetches and wait for them to come back and, and loop over stuff and, and push it back down into your data. It, you just call it invalidate all. Svelte can says, okay, well I'm gonna rerun your load function. Here's the, the updated data and everything that's reactive, based on that data is gonna get updated, which is super handy.

[00:34:14] **Adam:** The downside

[00:34:15] **Ben:** be clear, you're making a. A browser client side or svelte is you're making a function call on the browser and Svel has some mechanics that it kind of bakes into the page that says I'm gonna make a, now like a fetch call back to the server to get this data.

[00:34:30] **Adam:** Right.

## [00:34:30] SvelteKit's Compilation and Reactivity

[00:34:30] **Adam:** So the other thing, okay, this is something I don't think I got into before. The other thing, the other big difference between let's say svelte and React is Svelte is compiled away, right? So when you run a Svelte application, I don't think that there's any, or if there is any, it's this tiny amount of quote unquote Svelte kit code that comes down with my application, right?

[00:34:50] **Adam:** the compiler runs at build time and it just makes my app and, and bakes in the smarts of, okay, well you updated this variable, so now we have to go re-render these things. But that's not. That's like built into the, it's almost like hard coding the application based on the logic that

[00:35:04] **Ben:** Like svelte is adding stuff, but then the kind of svelte compiler is no longer there.

[00:35:10] **Adam:** right? Yeah. It doesn't have to reevaluate what do I need to do in this moment because of exchange. It just knows, okay, exchange. So I have to go do PD and Q, right? and that part gets hard coded into the application.so you've got these load functions, and this is, I think this is an interesting way to, break this up, right?

[00:35:26] **Adam:** I talked about you've got plus page, server Ts and page Ts page do server ts because it has that server thing in there. You can do server side stuff. Like you can import a query function that will pull data out of your Postgres database.you can't do that from the plus page ts because it's running client side.

[00:35:43] **Adam:** You can't make that database connection from the client to your database. But what you can do is like maybe make an API request so you can reach third party APIs or you can call your own APIs that are backed up by page or by server side, running functions, that sort of thing.and so you can invalidate either of those, right?

[00:36:01] **Adam:** So if I call invalidate all and I happen to have a page ts that called, you know, makes a fetch to get data from some API, then it's gonna rerun that and gimme the updated data. Or if I happen to have a page server ts that was pulling data from Postgres, it's gonna repu that data from the database and send it down, which is nice.

[00:36:19] **Adam:** The problem that I've run into with Jump Run, that's, I guess I should say, it's got,a fix is supposedly forthcoming, but you know, these views that I'm loading have a ton of data on them and a lot of it I know is not going to change, right? So, I. As the day progresses, the number of aircraft that the drop zone owns is not going to change.

[00:36:39] **Adam:** Right. The and, and the details of those aircraft, they, they're not gonna suddenly have an extra seat on the aircraft. There's only 14 seat belts, there's only 14 seat belts, right? sort of thing. And so some of the, I would say a good half or so of the data that I'm loading to render this page is like, I know for a fact I don't care for it to update, but the rest of it I'm updating frequently, like to the point where I'm, I'm using web socket service so that when data is changed on the server, I'm pushing a message to all the connected clients saying the data has updated, pull the latest.

[00:37:14] **Adam:** And so then it's making requests to get the latest, you know, status of all the

[00:37:17] **Tim:** So, so is there no way to say Don't refresh these on the refresh? All

[00:37:21] **Adam:** So that's, yeah, that's where it's at. Is that, that's what's frustrating me is like, it's. It's currently kind of an all or nothing thing. Now I could, I could swap over into like a manual mode and like write all my own API functions and, and write, you know, fetch calls to get those things individually.

[00:37:38] **Adam:** and, and it's like they, they gave us this super easy path. you know, you just write a, a query, you return the result to your load function, you return that data to the view, boom, super easy, nice straight line. But if you

[00:37:52] **Tim:** but the assumption is that everything's gonna change every single time. If it doesn't, then you're just wasting

[00:37:57] **Adam:** Right. So if I've got, if when you combine all the data on the page, if there's like 20 to 40 queries that are running and I know I only really wanna rerun like three of those.

[00:38:07] **Adam:** Your SOL you gotta, yeah, I could either, I can eject out into a manual mode and build an API resource that'll only pull that data and update that data, which I might do one day if it becomes a problem. In the meantime, I'm just like, you know what, let it go. I can reload everything. That's fine. I might, I, I've

[00:38:24] **Tim:** Yeah, I mean right now you're probably, right now you're probably working with a very small data set, so it's not very expensive to do. But yeah, eventually I, I've done that before where you're like, I'm just gonna refresh everything. And then like two years later, like, oh, it's probably taking a little long to load this page.

[00:38:40] **Tim:** Let's, let's find a different strategy for reload.

## [00:38:43] Mobile Device Constraints

[00:38:43] **Ben:** well, here's something that just occurred to me, which is a, a unique problem that you might be facing because you're dealing with people who might have mobile devices. So if I have a spa single page application, and it's been running on a desktop browser, Chrome, Firefox, safari Edge, what have you, I feel like that page could live for weeks and, and it's not an issue.

[00:39:06] **Ben:** But I know from personal experience when I'm on my phone and I have a browser page that's been open for a long time, every now and then I'll go to it and it'll just have like unloaded

[00:39:16] **Adam:** Mm-hmm.

[00:39:16] **Ben:** or like, I'll go to it and it'll completely refresh and, and do stuff. when you're poking around in a svelte application, I, I guess with svelte kit and the whole routing situation, it you, I guess you have to, you have to build it in such a way that if it just randomly refreshes, like you're gonna kind of be brought back to the right state. Does that, does that question make sense? Like, because someone might have an iPad with jump run on it, it, it's like slightly different constraints than if you're on a desktop.

[00:39:49] **Adam:** So,

[00:39:49] **Ben:** constraints is not the right word, but like

[00:39:52] **Adam:** Yeah, yeah. I think I, I think I kind of am picking up what you're putting down, and I don't think that that necessarily applies to jump on itself. So it sounds like you're asking if you're two steps into a five step process, is it going to remember where you were or are you gonna get kicked back to step one?

[00:40:11] **Ben:** Like, is Safari just gonna say, Hey, there's too many tabs running in this browser. I'm just gonna like unload this one until the user comes back kind of a thing.

[00:40:19] **Adam:** so no, I don't think Svelte kit has anything to save you from that. you could do it manually. You could, you know, push partial state to local storage and maintain it that way. the,

[00:40:31] **Ben:** I guess I, I don't have a great mental model for what the pa, the page based routing gives you, or not that, not what it gives you, but like how that then dovetails with things that are slightly more dynamic in nature.

[00:40:44] **Adam:** Yeah, this is, it's funny because this conversation is making me wish that I could open source, jump, run 'cause it's such interesting code to work on, but I'm trying to make a little bit of money from this and, and like, I don't want, yeah. So, yeah, I don't know. I will say I don't think that that particular problem is something I need to worry about on this particular application.

[00:41:04] **Adam:** There are a couple things where it's like, okay, it opens a modal and you you have to fill out four or five little fields and then you submit it and it updates whatever in place. It's, it's,

[00:41:12] **Ben:** Is is a modal window, something that's Svelte? Is, is that, is that kind of a, a first class citizen. Citizen in svelte kit.

[00:41:21] **Adam:** so no, you, I mean, it's basically when once you reach the layer of H-T-M-L-C-S-S, it has zero on offer. You, you are welcome to do whatever you like for H Tm L and CSS, but it doesn't do anything for you there. It's strictly JavaScript. now, I mean, and a lot of the, the whole svelte community and ecosystem is very much embracing the use the platform thing, right?

[00:41:45] **Adam:** So like the, the newer dialogue elements and, and all of that, they, that's where everybody would be pointing you to.you may have heard of a library called ShadCN. From the React world, and it's, it's very popular. It's basically a collection of components, but it's not a library you install. It's basically like, go copy and paste it and now you own a copy of this in your repo, and that way you know it's never gonna change out from underneath of you.

[00:42:11] **Adam:** And if you, you know, if it's been two years and you're like, oh, there's these accessibility issues, or Oh, there's, you know, it's a little wonky in this way, you can go look, oh, there's a new version of it, cool. And copy that, that one new component in and, you know, fix whatever's different about it that might not jive with your app and now you're, you're good to go.

[00:42:27] **Adam:** There is a, I guess I'll call it a port of Shad CN first Svelte it's called of all things shad CNS Svelte.

[00:42:35] **Tim:** So creative.

[00:42:36] **Adam:** yeah. and so I'm using that and it's, it's very much, you know, like I said, use the platform, and A lot of, it's not a one for one copy of ShadCN, but it's very much in the spirit of ShadCN, and very customizable.

[00:42:51] **Adam:** And then, you know, it's built on tailwind and I like tailwind anyway, so just, it all kind of jives together that way.

[00:42:58] **Ben:** I'll tell you. So I played around a little bit with Svelte, I don't know, like a year ago.

[00:43:03] **Adam:** mm-hmm.

[00:43:04] **Ben:** I don't even know if version five had been released yet. I don't quite recall. But, I think one of the things that I griped about to you on the show was that, I didn't like the fact that when you import a component and then go to use it. The tag, so to speak, that you're using to output The Sveltel component is not necessarily the tag that renders to the browser. Like if I output an icon tag under the hood, it might be an I tag or it might be an SVG, or it might be something with a font awesome icon or something like there's no, there's no like direct port of the thing I used in my svelte code to the thing that actually gets rendered.

[00:43:44] **Ben:** You know, svelte might short circuit that component and nothing gets output. And my complaint about why that gets complicated is because of what happens. If I want to add a style attribute, then like there's no inherent way to do that. So you sort of have to say, okay, well then I can pass a style prop and then the, when this style component, when this component renders, it knows to merge like my inner styles with the styles that get appended kind of a thing.

[00:44:09] **Ben:** and I'm going somewhere with this thought. Which is to say that at work we, we use the, we've been using the WHEELS framework, so it's a cold fusion framework and they have a lot of mechanics around abstracted rendering of little partials on the page. Whether it's a, like a file that you include, it kind of gets wrapped in a function or like all these, like little helpers and stuff.

[00:44:35] **Ben:** Anyway, it boils down to the fact that there's also that problem there that I'm calling a function, but I, it's like if I wanna, if I'm calling a function that outputs a diviv under the hood, there's no inherent way for me to say, Hey, this diviv should also have this class unless I actually build that into the thing that's rendering the diviv to accept a class and know how to merge it and so on.

[00:44:55] **Ben:** And, this is a very long-winded way of me saying that I still don't like that. I don't hate it as much as I did before, like now that I've kind of used it for a while and having to deal with if I need to accept a class and a style attribute to, to kind of prop drill down to the underlying thing. Like, okay, I'm okay with that.

[00:45:14] **Ben:** Like I don't love it, but I don't hate it.

[00:45:16] **Adam:** Yeah, I mean, prop drilling is a, is a different problem and there are, you know, decently well-known and, and acceptable solutions to that using context stuff. But yeah, I, I, you kind of lost me at the beginning about like, you know, you tell it to put in an I tag and you don't get the I tag or you don't get your icon whatever,

[00:45:35] **Ben:** I'm saying like, like you could do a, you know, like less than like greater, or, sorry, like a uppercase I icon as the thing I'm importing. But then that doesn't mean that you're getting an icon HTML tag. You might be getting an

[00:45:50] **Adam:** Well, it's whatever's implemented inside of that

[00:45:52] **Ben:** Right, right. That's what I'm saying is that there's this layer of abstraction.

[00:45:55] **Ben:** So you don't like what you see is not necessarily what you get. Which it was in sharp contrast to something like a, like a web component where you invoke the web component literally by using the tag that it is. It's not like something that renders something else.and that, that just takes a, I think that it, it, it's a weird thing to get used to,

[00:46:17] **Adam:** Yeah. I'll give you that.

[00:46:19] **Ben:** but having, well, I said like having now spent some time in the cold fusion world dealing with some abstractions that are more akin to that.

[00:46:26] **Tim:** you been in the coefficient

[00:46:27] **Ben:** I, I've been dabbling. I've been dabbling

[00:46:30] **Tim:** dabbling.

[00:46:32] **Ben:** and, you know, I'm, I'm, I'm, it's growing on me.

[00:46:35] **Tim:** Yeah. Maybe you should write about it a little bit.

## [00:46:39] Updates

[00:46:39] **Adam:** So I remembered the other thing I wanted to get into a little bit. So, you know, I, I mentioned that, this is my, my biggest frustration, the whole like invalidate all thing. it is a known frustration. I won't even say it's a own issue, right? It's not that it's not working correctly, it's just that it's kind of, I guess people are starting to outgrow it and, so they're looking for.

[00:46:59] **Adam:** Some improvements, some, some better experience. and it's, I, according to the svelte, you know, issue tracker, it's slated, I think, to be fixed in svelte three, which is a little frustrating for me because they're, they've been working on Svelte two svelte, or I'm sorry, svelte kit two. it's, and which is not out yet.

[00:47:16] **Adam:** So, that means I have to wait two major versions to get this fixed, which is frustrating. but there are other things coming and I think that might be part of why they pushed it off to three. So there's, there's a, I guess it's a, a branch Is this, I think it's a Svelte, I haven't touched it, I've only just started to read about it, but there's a, a branch, like a beta branch of, I think it's Svelte available.

[00:47:41] **Adam:** It might be of Svelte kit. It's the, the Async branch. And basically this is sort of sveltes answer to react suspense and loading data from within your component. So if you've seen any react code where you've got like a compo, you're in the client side component, and then it's like, you know, a weight, SQL and then it's like back ticks and, and it's got some sql and you're like, holy crap, you could do that from a React component.

[00:48:03] **Adam:** It looks very dangerous. It's actually not dangerous because of the way that the template

[00:48:07] **Ben:** running on the server.

[00:48:09] **Adam:** Yeah, well that, but also it's, it, you know, you, it could be, you know, it's a, it's a weight SQL back ticks and then a, a SQL string. And you might have like interpolated variables in there, right? Dollar

[00:48:19] **Tim:** looks like injection code.

[00:48:20] **Adam:** Right. It looks like this is ex, this is excess waiting to happen. But because it's a template string, the way template strings work where it like extracts those ar those, interpolations out as arguments and then the, the sequel with placeholders is the first argument. Yeah. So it, it makes those safe, but it's, it's terrifying to look at the first couple times you

[00:48:38] **Tim:** I bet. What, why are we putting this? Why are we putting SQL statements in our code? What's going on?

[00:48:44] **Adam:** on the login form. It's got, you're like, holy sh Nike's.

[00:48:47] **Tim:** tables.

[00:48:48] **Ben:** I'll tell you, so Angular and I haven't really been keeping up with Angular in the last, I don't know, six months to a year. I think they're on version 19, but, but around like version 12 or 13, I think they. They just like put a stake in the ground and said, okay, all of the libraries that we use to make this ecosystem are now gonna be the same number.

[00:49:11] **Ben:** So instead of having like the Angular CLI being on version five to power Angular version 12, it's like everything's like Angular CLI is now on version 19 as is the framework, as is the material library. And it, it just made so much more sense. Like even if they just have to arbitrarily increment the value to keep them all in, in, in alignment, it's, it's just, it's, it's makes it so much easier to think about, oh, I'm on, I'm on svelte five so I use this Svelte Kit five and I use all the other version five libraries.

[00:49:43] **Adam:** Yep. Yeah, I'll give you that. so I, I just wanna say like, 'cause Async Svelte, you know, it's got, it's their, their sort of version of like a react suspense with, you know, you can do, boundaries with a pending state that's kind of like a suspense component sort of thing. And you can load data from within components, which, if you've got some way to invalidate just that data, maybe that'll solve my problem.

[00:50:07] **Adam:** And if this, it, it, it's entirely possible that this async thing could land as like svelte kit 1.1, you know, and so maybe I won't have to wait two major versions, but, And so I, I'm just, I'm, I'm eagerly I'm sitting over here like, just kinda leaning over the edge of my desk.

[00:50:22] **Adam:** Like, come on, release it, do it, do it.

[00:50:25] **Tim:** that's great.

[00:50:27] **Ben:** I feel like Adam's beard has gotten to a point now where he is like a significantly different looking person.

[00:50:33] **Tim:** He is right. It's good looking. He is, he's a good

[00:50:37] **Ben:** It's like it's, it's like you're no longer Adam growing a beard. You're Adam with a beard,

[00:50:42] **Tim:** Mm-hmm. But I, but I was like, I think the first time I met you, you had like a ponytail.

[00:50:48] **Tim:** Yeah,

[00:50:48] **Adam:** I probably did. Yeah.

[00:50:49] **Tim:** did you have a beard then?

[00:50:51] **Adam:** yeah, while I had my long hair, I did have the, just the chin goatee.

[00:50:54] **Tim:** The chin thing? Yeah. Yeah. The, yeah. When we, I did my beer tasting in my room up in

[00:50:59] **Ben:** I don't remember you with long hair. That's funny.

[00:51:02] **Adam:** yeah. That's okay. It was, it was not a good look for me, so

[00:51:04] **Tim:** Well, yeah, I mean, yeah. You look good now, buddy. I'd love, I'll, I'll, I'll, I'll lean on the positive. Yeah.

[00:51:10] **Ben:** There you go.

[00:51:11] **Adam:** tell my wife that,

[00:51:13] **Tim:** You don't like it?

[00:51:14] **Adam:** she's on the fence.

[00:51:15] **Tim:** Yeah, I love it. Yeah. I'm just jealous 'cause I can't grow facial hair at all. So

[00:51:21] **Ben:** I can grow good facial hair down under my neck.

[00:51:24] **Adam:** Yeah.

[00:51:24] **Tim:** beard. A neck beard. Yeah. Great. Awesome.

[00:51:29] **Adam:** not mine is much like thicker and, and more consistent down there, but I've got the, you know, I've got,

[00:51:33] **Tim:** I, I can't, I can't even grow a neck beard. I get like one or two hairs there, like every, every year or so, I just get Michelle's like, you got a, what, what is that? I'm like, oh, it's a giant hair, like three feet long off my neck. And she pulls it and you know, that's it for the next two years.

[00:51:49] **Ben:** My goodness. Good times.

[00:51:51] **Tim:** Good times.

[00:51:52] **Ben:** She.

[00:51:53] **Adam:** Yeah, we

[00:51:54] **Adam:** can do,

[00:51:54] **Tim:** think so. I, I think it's a natural state to stop there when, you know, we're like, we got so bored with, with the Svelte kit. We're like, let's talk about facial hair. No, actually, you know, I, no, I'm sorry. I, I was, this actually was very enlightening for me because it's like, it's svelte kit is not.

[00:52:10] **Tim:** I did send someone on my team like, Hey, go check this out. You know, someone, he's like, thinks this is really awesome, and she spent like two weeks trying to figure it out and she's like, yeah, I don't get it. I'm like, okay. but I mean, now that you kind of explained it. I, I think honestly, once they do the async loading data things, I might actually might take a look at it after that point.

[00:52:33] **Tim:** 'cause that does sound interesting to me.

[00:52:35] **Adam:** Yeah. I'll, I'll, I'll be sure to bring it up here on the show.

[00:52:38] **Tim:** I'm sure

[00:52:38] **Ben:** Ask you, sorry, one more Sveltel question. Just 'cause I'm, so you have these sort of code behinds that run on the server and then you have the kind of client side aspect of it.

[00:52:48] **Adam:** Mm-hmm.

## [00:52:49] SvelteKit's Layout and Component Structure

[00:52:49] **Ben:** If you wanted to have layouts, so like, let, let, let's imagine, let's imagine that you have two layouts, that you have one layout that is, here's the header at the top and here's the footer on the bottom, and then maybe you have a nested layout where it's like a one column layout or a two column layout with a sidebar.

[00:53:05] **Adam:** Mm-hmm.

[00:53:06] **Ben:** Does that nesting of layouts, is that a client side concern or is that a server side concern? Or it could be a little this, a little of

[00:53:17] **Adam:** It's, I guess you would call it a server side concern. So it, it ends up being kind of part of the folder structure, right? So the way that it works is that you've got your layout Sveltel and optional layout server ts, or layout ts for client side stuff that it can do. and based on where it is in the folder structure, everything in the current folder with the layout and everything in child folders of that folder.

[00:53:47] **Adam:** Get wrapped in that layout

[00:53:49] **Ben:** Gotcha. so

[00:53:50] **Ben:** it's, it's kind of like the, the, the gold fusion frameworks where it's like everything generates a body variable and then it kind of rolls back up and keeps in enveloping inside

[00:53:58] **Adam:** Yeah. Yeah. So every view, export or returns body, and then the layout takes it and embeds the body and returns itself as body. And if there's anything happen, be higher up in the tree, then it takes that body and embeds it as whatever and, and passes itself up as body. Right. Like,

[00:54:13] **Ben:** Yeah. Yeah. Okay. So, so the, the folders kind of work that way as well then.

[00:54:17] **Adam:** yeah. And, and I mean, I, there's like hours and hours and hours of stuff to talk about that I didn't get into here in terms of

[00:54:24] **Ben:** Alright, cool. Well, this, it's, it's fascinating. Yeah, go ahead,

[00:54:28] **Tim:** One of the things that you said though, that struck me because this I think might be a. Fundamental misunderstanding of what this product is. You said that it doesn't care about your HTML or CSS.

[00:54:42] **Adam:** Okay. So

[00:54:44] **Adam:** it,

[00:54:44] **Tim:** because you said there was a front end, front end, like a client side framework, but this isn't really a ui UX tool.

[00:54:52] **Adam:** It is, but it is a, it is a, the what S Svelte gives you is a great developer experience for dynamically changing your, your le your view. And it has zero opinions on how you should write your HTML and CSS. So if you wanna use Tailwind or if you don't, either way is fine, both integrate just fine. if you, you know, if you're doing O-O-C-S-S or if you're doing, what's the one them, you know, all of those are fine.

[00:55:21] **Adam:** if you want to. So here's something that's really nice that might actually help sell you on this, Tim. in, in Apelt component or the dots Svelte file, right? It's got, you're doing, it's a table, right? and, and, you've got your table of data up here, and then down at the bottom of that file, you could just put a style tag.

[00:55:37] **Adam:** And you put in your, your styles, but you don't have to be like, okay, well this is the, the accounts receivable table. you know, you don't have to name things carefully because if there's only one table in the component, then the style can just say table, right, or TR or td, like you don't it. The styles in that component only apply to the HTML in that component.

[00:55:58] **Adam:** So even if you've got 10 different components that each render tables, if they've got different style in that component, it only applies to the, the, the tables in that same file,

[00:56:08] **Tim:** okay. Yeah, because I, I like turned it over to one of our ui ux people and she was like, this really doesn't have anything to do with like styling the page. I'm like, okay. That's what she told me. I'm like,

[00:56:19] **Adam:** right? It doesn't give you tools to make better ui, it gives you tools to make, have a better developer or experience of building a dynamic

[00:56:28] **Tim:** right. So this is the dynamic part. Okay. Yeah. That, that's where I was missing it. 'cause I thought, I mean, 'cause React kind of really does deal with the actual screen itself. Right.

[00:56:38] **Adam:** Well, yeah, I mean, you still write the h TM L in your app and you, you know, you do, you can have like a little loop and you spit out your table rows or whatever, or your divs inside of Flexbox or what, you know, whatever you're doing. but, it's,

[00:56:50] **Tim:** gotta style them. You still gotta make the, okay.

[00:56:52] **Adam:** Well, and like I said, you know, we use, a lot of bootstrap and you can, you can just as easily, you know, include the bootstrap CSS and include bootstrap classes on the html you're rendering and there you're doing a bootstrap app with Svelte.

## [00:57:04] Scoped CSS

[00:57:04] **Ben:** But I will say, I think, and maybe I'm speaking out of turn here, but,

[00:57:08] **Tim:** That was your turn.

[00:57:09] **Ben:** no, no, speaking above my pay grade, I, I,

[00:57:12] **Tim:** I don't know, but you get

[00:57:13] **Ben:** fundamental differences between React and S Svelte was that it seemed like Svelte from day one. Baked in, scoped CSS to its concept of components and React did not have that.

[00:57:28] **Ben:** So there was a lot of discussion and a lot of competing approaches and a lot of hand wringing and going back and forth about how scoping CSS should work in the React ecosystem. 'cause it wasn't a first class citizen. So like what, like CSS and Js was sort of like the leader and then that got dropped for CSS layers.

[00:57:49] **Ben:** I, I don't, I don't really know that world so well, but I think maybe that's part of what you're picking up on a little bit.

[00:57:55] **Adam:** you, you had mentioned the scope CSS, and that's officially what it's called. I believe

[00:58:00] **Ben:** Yeah. So it's like svelte just had that from day one and React had to sort of back into an implementation that, that the community agreed upon.

[00:58:09] **Adam:** You know, I don't wanna, I don't wanna misrepresent. I believe that at least s Svelte kit had scoped CSS from day one. I don't know about Sapper. I never used sapper and components in svelte clients. I, I believe, svelte itself at least since version

[00:58:25] **Ben:** in, in the, in the multi, like the single file component, unless I'm getting confused with view, but I'm pretty sure svelte had this where it's like you have your style block at the top and your JavaScript block and your, your view block essentially.

[00:58:38] **Adam:** Mm-hmm.

[00:58:39] **Ben:** And I think that automatically, like you could just say scoped or something from

[00:58:43] **Adam:** Yeah. I'm, I, you know, I, I was not there at the beginning, but I

[00:58:47] **Ben:** was I, I'm making this up

[00:58:48] **Adam:** Yeah, yeah, yeah. I'm just saying, I, I started with Svelte three. I'm pretty sure they had Scope CSS there, so, you know, prior to that, maybe there's a good chance, 'cause Rich is a freaking genius. But,

[00:58:59] **Ben:** toy.

[00:59:00] **Tim:** Don't call the dog magic to me. I was there at the beginning.

[00:59:05] **Adam:** Yeah, I wish I knew the Bain quote better. I would, I would play along. But

[00:59:08] **Adam:** That wasn't Bain. That was, see,

[00:59:10] **Tim:** of the wardrobe.

[00:59:11] **Adam:** see, I, I don't, I don't even know that

[00:59:14] **Tim:** that was,

[00:59:14] **Adam:** I'm, I'm playing the part of Carol tonight

[00:59:16] **Tim:** that was a, that was asline to the, to the, to the, to the, white witch.

[00:59:21] **Tim:** something, something. I was born in it. I don't know, whatever. Yeah. Similar quote. Yeah, I get it.

[00:59:27] **Adam:** alright. W

## [00:59:28] Patreon

[00:59:28] **Adam:** ell then this episode of Working Code is brought to you by exercising your brain meat muscle and listeners like you.

[00:59:33] **Ben:** brother.

[00:59:34] **Adam:** Yeah, brother. If you're enjoying, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:59:43] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we could do this every week without them. Special thanks for our top patrons, Monte and Giancarlo. You guys rock.

## [00:59:51] Thanks For Listening!

[00:59:51] **Adam:** We're gonna go record the after show, which is our patrons get, their, their episodes will keep going for a little bit. We're gonna keep talking. I've got, I'm gonna talk about my eye again. I'm gonna talk about Mingo came over, hung out for a little bit.

[01:00:02] **Adam:** I, I got to meet.

[01:00:03] **Tim:** not

[01:00:03] **Tim:** Monty.

[01:00:05] **Adam:** I don't know why you would mention that.

[01:00:12] **Tim:** I just love them both so much.

[01:00:14] **Adam:** and,and apparently Tim has a meeting pet peeve. So

[01:00:18] **Tim:** Oh, I do. I, I, I've, I, I have, I have opinions on meetings.

[01:00:22] **Adam:** right? So if you wanna hear that stuff, what you gotta do is become a patron of the show. You go to patreon.com/workingcodepod, throw us a few bucks, we'll throw you a few extra minutes of episode every week.

[01:00:31] **Adam:** So that's, that's the trade. we greatly appreciate all of our patrons, and we would love to have you join that crew. that's gonna do it for us this week. We'll catch you next week, and until then,

[01:00:40] **Tim:** Remember, your heart matters. And if you're an old lady, your heart matters even more to Ben.

[01:00:47] **Ben:** Zing.
