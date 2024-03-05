---
title: "167: Everyone Likes Their Own Brand"
description: "On today's show, we talk about our own personal brands; how they can help us; how they sometimes hurt us; and, how the goals of brand-building can change over time."
date: 2024-02-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/167-everyone-likes-their-own-brand/id1544142288?i=1000647378498"></iframe>

> The first duty in life is to assume a pose. What the second is, no one has yet discovered. - Oscar Wilde

You may never think about it or even be aware of it; but, you have a personal brand. A brand is not something you can opt into or out of. It simply exists. The only choice that you have is how you manage - or choose not to manage - your brand in relation to other people. On today's show, we talk about our own personal brands; how they can help us; how they sometimes hurt us; and, how the goals of brand-building can change over time.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/167-everyone-likes-their-own-brand.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** Right. So for you right now, for like me, when I hear Ben Nadel, I think Cold Fusion, I think, too many line breaks, lots of comments.

[00:00:09] **Adam:** Uh,

[00:00:09] **Tim:** this is me photos.

[00:00:10] **Ben:** Yeah.

[00:00:12] **Adam:** And, and I mean, videos of your dog humping stuff,

[00:00:16] **Ben:** Totes

## [00:00:37] Intro

[00:00:37] **Adam:** Okay. Here we go. It is show number 167 and on today's show, we're going to be talking about personal brands. Should you have one? What are the pros? What are the cons? Gonna get into that a little bit. but first as usual, we'll start with our tramps and fails. it's Tim's turn to go first, I think, Tim.

[00:00:52] **Adam:** but before, before we, I mean, she couldn't be here. Carol's not with us tonight. she's under the weather. So just setting expectations. Let's lower the bar here a little bit.

[00:01:01] **Tim:** It's not the same without Carol.

[00:01:03] **Adam:** Yeah.

## [00:01:04] Tim's Triumph

[00:01:04] **Tim:** so I got a triumph, you know, I talked, had a very emotional episode a few weeks ago. We're talking about my mom. Well, my mom's home now. She's out, out of the hospital after about three, three weeks. Thank you. And,yeah, so my mom is home from the hospital now, and she's doing personal therapy from home. She has someone coming every day to do physical therapy with her.

[00:01:25] **Tim:** But she's, I mean, she's getting along. She, you know, she can't do much. She can get up out of a chair and Get in bed and go to the bathroom, but that's things she definitely couldn't do three weeks ago. So, and, hopefully, hopefully she keep pumping iron and get, you know, real swollen and, you know,

[00:01:42] **Ben:** Nice.

[00:01:43] **Tim:** start bossing dad around.

[00:01:44] **Tim:** So

[00:01:45] **Adam:** Get, Ben to come down and be her, her trainer

[00:01:47] **Tim:** yeah, yeah. She'll, she'll train him.

[00:01:50] **Adam:** that

[00:01:50] **Ben:** I'm glad she's doing better.

[00:01:52] **Tim:** Thanks. so that's all about the personal front, but so at work the past. This past week, I've been working on,SRGS, which is Speech Recognition Grammar Specification. It's a WC3, it's the web specification. Basically, it's, it's for speech recognition, like when you call into a phone system and it, you

[00:02:12] **Adam:** I hate

[00:02:12] **Tim:** yeah, I hate those two.

[00:02:14] **Tim:** You know, we do a fair amount of Business through IVR is where we do drive payments through IVR. So we try to encourage people to get them because there's still a subset of people that really just, they want to call a phone number. They don't, you know, they don't want to download an app. They don't want to go to a website.

[00:02:29] **Tim:** They want to call a number knowing that if they get stuck, they can talk to a human. And, but I've always. Steered people away from doing speech recognition. And I'm like, if we can just do it through punching numbers, it's a lot more accurate and less frustrating. but we have a customer who's just dead set that at least the policy number, you know, cause this is for insurance.

[00:02:48] **Tim:** So, you know, we have letters in our policy number, so we want them to be able to say it like, okay, we've been working on that. And, you know, figuring it out. it's, it's XML based, which was yucky. Big thing is it's really hard to test. I can test the code, right? Code, code parses is that it's about all I can really do and it doesn't error, but it's like, I have to physically call into a phone number.

[00:03:12] **Tim:** So I have a Google voice number. Yeah. I have a Google voice number and I call in and I'm like, ABC123AJD459. No, that's wrong number.

[00:03:25] **Adam:** Sneeze, cough.

[00:03:26] **Tim:** Yeah. And then sometimes it's like, you'll, it will be perfect. You'll figure out what. Letters and numbers I'm saying without issue and then other times it comes back. It is so wrong I just I don't even know how it got so wrong and I don't know why what I've been reading is that the the compression algorithm that they use to send the The voice capture across the phone line is so lossy that that it's it's hard for these things to do But you know, I've been on some of these phone systems.

[00:03:55] **Tim:** They do. Okay But, you know, I'm having a wide range of, experience with this and I don't, I don't know why. So if anyone out there knows a better way to test a speech recognition grammar system, let me know. That, that'd be very, very grateful because I, I can't figure out a way to automate this.

[00:04:14] **Adam:** Sounds like a fun problem, except until you get to that point where you're like, okay, I've tried everything. It's still not good enough. And, and I don't have a choice. I have to find a way. And you're just banging your head against the wall for a while.

[00:04:26] **Tim:** Well, I'm having the customer send me all their policy numbers because they're like, you know, some start with the letter and some end with the letter. I just want to see all of their numbers. Just send me all the policy numbers and I'll figure out. Because even if it's helpful, like let's say the policy letters are C, D, and E.

[00:04:43] **Tim:** I can eliminate from the specification that you're expecting to see the letter A and B. And that's helpful because that increases what it does, it does a probability, it does a probability and says this letter is, it's probably 80%. I think that's, that's a B or, you know, 20 percent that it's a C. But if I eliminate that as an option, it goes, well, that has to be a B because there's, you know, there's no other option that's close to that.

[00:05:08] **Tim:** So I'm hoping that they have, you know, just a few letters and I can knock out a bunch of those letters. And. And a sort of, you can also do sort of a pattern match to say, expect a letter at the beginning and then some numbers and then, or a letter at the end or a letter in the middle. And it's always going to be one of these two letters.

[00:05:25] **Tim:** If I can do that, I can probably get it to a higher degree of probability. So we'll see.

[00:05:30] **Adam:** M as in Mancy.

[00:05:33] **Tim:** Yeah. So, and then I have to do it in Spanish too. So, and I don't speak Spanish, but, I was playing with that today and, you know, saying uno, dos, tres, I have to spell it out and tell it that it's Spanish and it, that did okay.

[00:05:46] **Tim:** So. But I'm not a native Spanish speaker, so I don't know how well it will do with someone with a very strong. I speak like a gringo.

[00:05:56] **Ben:** So is the entire call tree outlined in one giant XML document with like all the options that get spoken, or is this only for the inputs?

[00:06:07] **Tim:** You can do it that way with the giant XML. I don't do it that way because I like to break it up. So you can basically have a form post. So you have a large piece of XML that just kind of describes all the possible options you're going to do in that one sort of node. And then once you do, once it figures out.

[00:06:25] **Tim:** What you've said or what you've picked. I can basically do a form call to another page. So I have basically, I have sort of a, it's almost like a state machine. I have the state machine of the call and, with routes and events. And so each, each prompt is going to generate an event that it goes to. And that event's going to figure out what's the next step in the state.

[00:06:45] **Tim:** So,

[00:06:46] **Ben:** Very cool. It's totally random, just popped in my head, but there's some, some article or paper written, you know, like decades ago, GOTO considered harmless, harmful, and it occurs to me that like so much of what we do is actually just sort of glorified GOTO statements. I mean, even just a web page, you know, clicking on links, submitting forms, you're, you're really just doing giant GOTO calls, you know, hey, go from this page to that page or a state machine is go from this state to that state.

[00:07:12] **Ben:** It's. Doesn't seem so fundamentally different to me.

[00:07:16] **Tim:** Yeah. I mean, we were, we, before the show, we were watching the, landing on the moon. The, what are they

[00:07:21] **Adam:** I am one. Yeah.

[00:07:22] **Tim:** so it reminded me, I mean, it sounds like, sounds like what we do for work. So they, they did a first run around the moon and it has this system that's supposed to like scan the landing area and find out, you know, automatically figure out which the best area to do.

[00:07:37] **Tim:** And it sounds like it was certain areas it wasn't getting imaging from. And so it had sort of an incomplete. Map, so they're like, no, we're not going to land. So it had, they, the programmers had the time that it took for it to go back around the moon. So a couple, that's why it

[00:07:49] **Tim:** was a couple hours late. They did one extra orbit and they're sitting there programming by the seat of their pants and uploading a patch to go fix it, and they did, they fixed it.

[00:07:57] **Adam:** I was thinking about that when they were talking about it on the broadcast, they were like, You know, they, they sent a patch and I'm thinking, did they, what did they call it an over the air update? There's no air,

[00:08:07] **Tim:** Well, the first bit of it in the, in the atmosphere, there's some air and then it's not, and then, and then they land and they're like, well, we're not getting, we're not, they weren't getting communications and they

[00:08:17] **Adam:** It was a really weak signal.

[00:08:19] **Tim:** really. So, so basically the, the thing's programmed to, if it doesn't get a signal, if it can't sense a signal, it will reboot.

[00:08:26] **Tim:** All this, so they're basically turning it off and on again to, to fix it, which I'm like, okay, well, it's, it's rocket science, but it's not that much different from what we do.

[00:08:35] **Ben:** It's a classic

[00:08:36] **Tim:** harder. Anyway, that's me. How about you, Adam?

## [00:08:40] Adam's Triumph

[00:08:40] **Adam:** Oh, I'm going to go with a big old triumph this week. Um,so I've been talking for a couple of weeks now about our, the Drexel co-op that we're, participating in and the process, and it's still a little opaque to me. I don't really, have a, a full grasp of like what the algorithm is on, how it matches people or anything like that.

[00:08:57] **Adam:** But the good news is, you know, we, we went through the interview process. We kind of ranked the candidates in the order that we would prefer, like, you know, this is our number one pick, our number two pick. Et cetera. And, you know, we put that into the system and then the next day I went and looked and we got our top pick, we got number one.

[00:09:14] **Ben:** Nice.

[00:09:15] **Adam:** yeah. So we're, we're super excited. and I think I mentioned to you guys, I'm pretty sure it was on, on the podcast. the, there was one person that had a, like, they, they made their background in Zoom, the AlumniQ logo. That was the person that we ended up hiring. It had nothing to do with the background, except that, you know, it was just like a good indicator that, you know, this guy knows how to have fun, right?

[00:09:34] **Adam:** You know, he's like a, he's not taking himself too seriously. He's, you know, trying to be creative, whatever. there's a, there's maybe a little teeny tiny bit of like an it factor thing coming from that, but otherwise, you know, we still would have picked him, even without that, just based off of everything else, I guess is what I'm trying to say.

[00:09:49] **Adam:** Anyway, so we got him, I, I guess because he picked us as well, and,

[00:09:55] **Tim:** like, I already got the background. So

[00:09:58] **Adam:** And then also, it's just been a good week, same, not same anything, but, also this week, my, the Svelte design system that I've been working on for like forever, just sort of between things, is finally done to the point where I stopped, Giving new versions as like dash beta dot some number and now it's version 0.

[00:10:16] **Adam:** 0. 1. and I'm actually starting to use it. Like I, we have an internal dashboard and I'm using it for that.

[00:10:24] **Ben:** Very

[00:10:24] **Adam:** kind of say it's in production, in production for an internal only tool.

[00:10:29] **Ben:** Heck yeah. I, I actually, I'll wait to my triumph and then I'll, I'll ask you

[00:10:33] **Adam:** Okay. So I'm super excited about it. it's just been, it's been a pretty baller week.

[00:10:38] **Tim:** when does this person start?

[00:10:42] **Adam:** April. Early April. I mean, I have a conversation with them on Monday to sort out details like first day, last day, a couple of other things, but,

[00:10:49] **Tim:** Cause that's when the semester probably ends because that's when Max gets out of college in April.

[00:10:55] **Adam:** that could be, yeah, I believe the, the official like way they describe this term for the co op is spring slash summer.

[00:11:04] **Adam:** So

[00:11:04] **Tim:** Yeah.

[00:11:05] **Adam:** I didn't, I did find more information on the way that this co op program runs. So it is a. There's, there's two different ways that they do it. You can either do a four year degree program and you take one co op in that, or you can do the same, you still get the same four year degree, but it takes you five years.

[00:11:23] **Adam:** You do the same number of like credit hours, but the, they're kind of interleaved more between three co ops. So you do three co ops that way. And I really love that, that idea. Like just seems, sounds like the perfect way to do college for our industry. Right? Like. Learn some fundamentals, then go get a, an entry level job, and kind of like start to mix.

[00:11:41] **Adam:** Here's some classroom work, here's some real work, here's some classroom work, here's some real work.

[00:11:45] **Ben:** so much sense.

[00:11:47] **Tim:** And do you. You obviously have to pay them, right? It's not an unpaid, I think, I think we covered

[00:11:52] **Adam:** to, you don't have to, but they, one of the nice things is, Drexel provides you, some statistical information on based on major, right? So like we were looking specifically at computer science and software engineering majors, those are two different Drexel, majors. And they say, okay, for, for this major, they give you like, percentile breakdowns, right?

[00:12:13] **Adam:** So like 50 percent or more make this much or more 75 percent or more make this much or more 95 percent or more make this much or more. Right. And so. They, and it's like dollars per hour or whatever. And so, and they do say you don't have to pay them. And I guess if the job is awesome enough, like if you're like, you get to be the guy who reboots the moon lander.

[00:12:34] **Adam:** And maybe you don't, you don't pay for that, but, if, yeah, I don't know. I mean, so we, we paid or we, we offered what we thought was a pretty competitive salary, like we were pretty darn near the high end of that, competitive salary, you know, information that they gave us. And that's based off of, I think last year or maybe two years ago, salaries for the.

[00:12:56] **Tim:** Okay.

[00:12:58] **Adam:** Super excited. and now, you know, now it's real, right? Like now I have to start, actually putting real focused effort into, brushing up on my mentoring skills and thinking about like, how am I going to be a manager of a person? And, you know, we're going to be doing onboarding and funnily enough, and all this other stuff.

[00:13:16] **Adam:** So, getting real, but I'm here for it.

[00:13:19] **Ben:** Very exciting.

[00:13:20] **Adam:** Yeah, man. So that's it for me. How about you, Ben?

## [00:13:24] Ben's Triumph

[00:13:24] **Ben:** also going to go with a triumph. I'll round us out here with triumphs.

[00:13:27] **Tim:** Look at us.

[00:13:28] **Ben:** I've, I've done some learning. I've done some, stepping outside the box, trying some new tech. my strategy has been to go onto Udemy, which is an online educational system. And, I got, I got and watched courses for Alpine JS, which is a front end, like a small front end library, HTMX, which is a, kind of a over the wire dynamic websites thing, like trying, trying to create a, responsive application without having to do so much JavaScript.

[00:13:58] **Ben:** And, and then I did a course on, Svelte JS, Let's call it the complete guide to Svelte. js, which was actually a pretty tremendous course. It was really good. Maximilian, Schwartz and something. I can't remember off the top of my head. Svelte. js is actually very interesting. there's some stuff about it that seems really nice and some stuff about it that Rubs me the wrong way, but you know, to each their own. I'll tell you, coming from Angular, and this is, I think,interesting to talk about in the context of a design system, one of the things that I always appreciated about Angular was that the component, the kind of the root component object. Our element is actually an element. Like if you, if you import a,magic menu and then you render magic menu and you look at the source of the rendered page, you get a magic menu element.

[00:14:51] **Ben:** It's not like magic menu component doesn't randomly generate a div with some other rando class on it. Like you actually get an element with that, tag name. And that was definitely. One of my stumbling points. So I'm starting to dig into Svelte because you import a class, it's not really a class, it's like you, you import this magical Svelte component and you render it and what you get as an output.

[00:15:16] **Ben:** Is whatever that component wants to render. It has nothing to do with what that element is kind of called on the, on the consuming side, which became a problem when I wanted to say, add margin bottom to an element, realizing that I don't actually have an element to attach a margin bottom to, and then when I go to pass a class into it, Svelte complains that there is no prop called class because I didn't expose a called class on the, on the component itself.

[00:15:45] **Ben:** And then you'd have to do that. And then, I don't know, it just, it felt very strange to have this layer of abstraction between the thing you're importing and the thing that actually gets rendered and, I'm curious to understand a little bit more about how that, works with a design system. Cause people must have to attach classes and, and, you know, on the fly, CSS styles to, to a design, design system.

[00:16:10] **Ben:** Widget. How, how do you go, how are you implementing something like that?

[00:16:13] **Adam:** I would love to dig into that, but that is a totally

[00:16:15] **Ben:** Yeah. Okay.

[00:16:16] **Adam:** sir. So, I sent you a link here in our private Discord channel that we have. The secret one. That we're not going to mention on the show. is that the, that's, okay. I'm sorry to tell you, I think this might be somewhat outdated.

[00:16:32] **Ben:** yeah, yeah. I think it's like two years old or something.

[00:16:34] **Adam:** Yeah, it says last updated November 2023, and it mentions Sapper, which was like

[00:16:40] **Ben:** Right. That's what

[00:16:41] **Adam:** thrown away and rewritten from scratch.

[00:16:43] **Adam:** Yeah, well, they were just like, Sapper has too much technical debt. We want to go a totally different direction. They just literally threw it away and started from scratch.

[00:16:49] **Ben:** Yeah. It's interesting, you know, as I'm, as I'm starting to explore other front end, back end technology strategies. What I'm trying hard to do, which seems like it's actually a bit of an uphill battle here, is find a modern front end framework that is somewhat back end agnostic. It seems like especially the JavaScript based ones are all very heavily tied to a specific back end implementation, whether it's SvelteKit or, or Next or, uh,

[00:17:23] **Adam:** is going. You have, you have a, a, you have a pet favorite backend that you just want to keep.

[00:17:29] **Ben:** have something that, you know, it's like, I have something I'm already paying for. I want to, I want to keep not paying more than I have to for as long as possible.

[00:17:38] **Adam:** I think you could get more resources for less money by, by changing that out to something else. But that's just my opinion,

[00:17:44] **Ben:** but, but, you know, and it's not just about, it's not just about the particular technology that I happen to like, but there are so many backend technologies. Whether it's PHP or Ruby and Java and

[00:17:56] **Adam:** yeah, and I'm glad that we're kind of, kind of going around on this. So you had mentioned HTMX and I wanted to ask you, I know you have done some exploration into like Hotwire. and so now that you've been learning a little bit about HTMX, I have not touched HTMX, and when I, like, read a little bit about it, or when I see other people talk about it, it reminds me of Hotwire.

[00:18:15] **Adam:** So can you contrast them? How are they different?

[00:18:19] **Ben:** So they're very much in line with each other. I would say HTMX is almost like a subset of what Hotwire is trying to do. Hotwire is a. It's like four different things coming together at the same time, like a, like Captain Planet style, you know, our, our powers combined. Yeah. And so Hotwire is Turbo.

[00:18:44] **Ben:** Turbo is an evolution. I think of something called TurboLynx and HTMX is, is most closely aligned with. Um,but then there's Hotwire also has Stimulus, which is the kind of JavaScript attaching JavaScript behaviors to the, to the browser, you know, the DOM. And so I think in HTMX, people will often use Alpine JS as their sort of stimulus alternative.

[00:19:09] **Ben:** and then there's some other stuff there's,

[00:19:10] **Adam:** Wait a minute, hang on. You're using words that I'm not familiar with. So when you say stimulus alternative, does that mean Does that mean that like, you, you have to have something in addition to HTMX? You can't just use HTMX

[00:19:22] **Ben:** no, no, you can. The, so fundamentally HTMX says, I want to make this network request. And I want to take the response of that network request and put it in the page in some way. And often times that is, instead of doing a full page refresh, let me take that response and just Repopulate this one div or this one table or this one select box, or like, let me take this part of the response and put it over here and another part of the response and put it over there.

[00:19:50] **Ben:** So it's kind of slicing and dicing HTTP responses. it's, it's very heavily focused just on that workflow on the, I'm making a request to the server and I'm getting response. On top of that, if you want to then start to make the front end a little bit more interactive, that is not, you know, HTTP based, you'd have to sprinkle in JavaScript and in the Hotwire world, that sprinkling of JavaScript is typically done with Stimulus.

[00:20:18] **Adam:** hmm.

[00:20:19] **Ben:** And in the HTMX world, it sounds like just from what I've seen, you know, hearsay, anecdotally that, that the sprinkling of JavaScript is often done with AlpineJS.

[00:20:30] **Adam:** Right.

[00:20:31] **Ben:** another, JavaScript framework.

[00:20:33] **Adam:** I see. So HTMX is not so much, an interactivity re rendering thing as it is just like, jQuery. load, effectively.

[00:20:42] **Ben:** yeah, I, I mean, I, you know, I'm, I'm, I'm, I don't want to talk out of turn here based on my understanding, but it's like a very, very fancy version of jQuery load. Yeah.

[00:20:51] **Adam:** Sure. And then if you wanted to do something a little more sophisticated, like a single page app in a little div or whatever, then you could Drop in a little Angular app or a React app or

[00:21:02] **Ben:** Yeah. Yeah. Yeah, exactly. And it seems that AlpineJS, which is again, just a, yet another JavaScript library framework is, is, is, is what that community seems to really like. Yeah,

[00:21:14] **Adam:** I always thought of Alpine as like As the, the sort of baseline, like if you wanted to do, we talked previously about like islands architecture, right? I have, I have a 90 percent static application and then it's just got this one interactive thing in it. and so you might use Alpine for that.

[00:21:31] **Adam:** Cause it gives you like a nice static web server, plus a way to easily drop in just a little node app or whatever, or a whatever react or, whatever app in that div,

[00:21:42] **Ben:** exactly. I mean, my understanding of Alpine is fairly limited still, but it's basically you say, Hey, any DOM element that has this data attribute, it gets bound to this, AlpineJS class more or less. I mean, it's not really a class. It's like just a reactive object, fancy object, and then you can do things, but it has some cool stuff.

[00:22:04] **Ben:** Like it has some templating and repeaters and, it's interesting.

[00:22:09] **Tim:** Would you, would you call HTMX a, a micro framework?

[00:22:13] **Ben:** I guess so. It's very.

[00:22:15] **Adam:** doesn't matter.

[00:22:18] **Ben:** It's, it, it's very focused in what it's trying to do. And I think it is very, it doesn't have a lot of opinions about how you want to do anything else. So I, I think it is fairly micro in that respect.

[00:22:32] **Tim:** because I was reading the other day about one called, HTMZ,

[00:22:36] **Adam:** I heard about this.

[00:22:37] **Tim:** Which is,I think it was on, TLDR. It's a minimalist, HTML framework. That's just, it looks, I mean, it looks stupid simple, doing stuff that I used to have to do with jQuery. I'm like, Oh, that's pretty cool. But I mean, I didn't do anything other than look at it.

[00:22:52] **Ben:** My, the, one of the things that I'm finding frustrating in my exploration is I, I keep wanting to better understand how to more holistically. Think about CSS organization and how do I get reusable things and, and how do I best annotate my HTML to use those CSS classes effectively? And it just seems like over and over again, people, people sort of sidestep that problem by just using Tailwind.

[00:23:21] **Ben:** It's like, yeah, yeah, we just use Tailwind. So we don't have to deal with that. And I'm like, ah, I feel like that's not really an answer. That's like, then I could just keep that. That's as good as me saying, I'll just keep doing what I'm doing today. And, and having something maybe more robust. No, I, I don't have, there's not a, a dis, a dunk on, on Tailwind.

[00:23:42] **Ben:** I've never used Tailwind other than to say, if I'm going to have a lot of. CSS classes in my markup, like I could just have regular classes in my markup and I don't think it would be fundamentally all that different. You know, as opposed to something like Svelte, where I have a style block and it's inside my component and it has automatically scoped my component.

[00:24:04] **Ben:** Like it's, it's really the automatic scoping. Like, how do you get automatic scoping without having like a ground up? I have to believe in this one particular framework and maybe you just can't, maybe that's the, maybe that's the problem is you just, there isn't like a nice halfway point,

[00:24:21] **Adam:** Well, yeah, I mean, it depends a lot on your stack, right? So We talked about, you know, where I, I, the very first thing that I put into a production with Svelte was like, I built the,like a modal dialogue that has a lot of complex functionality built into it. and that, I built that with Svelte and then it is injected into an application that is heavily, you know, server side, you know, like post back style for the NET folks.

[00:24:49] **Adam:** you know, submit the page, form posts and you get a page back and then we sort of try to make that page. Fairly dynamic using a lot of jQuery, right? and then I took that page and, okay, here's a modal window. Here's this felt app that you run in that modal window. And you're right that it's a, it's a little bit of a mind, messer to try and use polite words here.

[00:25:12] **Adam:** Um. It, it, the, you're, you kind of like have to draw a box using the outside, you know, whatever the, the baseline application is using for styling, like, okay, here's my rectangle. And inside that rectangle, it's felt it's going to take over and it's, it is weird.

[00:25:29] **Ben:** It is very cool though, that there isn't really a Svelte app. So, so much as there is just, here's a component. I'm going to treat this as my quote unquote root component. And I want you to target this div on the page. And if you want to target multiple divs with multiple root elements, we don't care. Like that's, that's totally fine.

[00:25:48] **Ben:** And that, and that is kind of cool. Cause I can definitely see you being able to baby step an application into a more robust architecture by just. Targeting almost more of the, of the rendered page with Svelte elements.

[00:26:04] **Adam:** hmm. It would lend itself well to like a strangler pattern type of approach of trying to. Now, I mean, think about how, too, this is all, Svelte itself is born out of the New York Times, right, so it was created by Rich Harris, who worked at the New York Times at the time, and he was making interactive animations and stuff to, to show off, you know, like the Olympics, you know, the, the swimming, you'd see little animations of people swimming and it would be like, to scale or whatever, right, you'd see like, The swimmer's going across the pool and it would, you know what I'm talking about,

[00:26:38] **Ben:** Yeah. Yeah.

[00:26:39] **Adam:** wouldn't just be like a random animation. It would be like, okay, lane four is, you know, is Michael Phelps or whoever. and he's got the right amount of lead.

[00:26:48] **Ben:** It's like uh, yeah.

[00:26:50] **Adam:** it's all based on real data. And, and yeah, I mean, it's, it's just an animation dropped into the middle of a news article. Like you don't want to take over the whole page.

[00:26:59] **Adam:** You just want that one little island of interactivity.

[00:27:04] **Ben:** Although I'll tell you, it's just one of those things where it's just, you, you learn it one way and then you don't necessarily know that there's a different approach. So in this complete Svelte JS guide that I took on Udemy, he was talking about how in order to make complex objects and arrays reactive.

[00:27:22] **Ben:** You have to jump through all the hoops that you do in React where you don't just push and pop things from arrays. You have to, you have to like spread arrays into other arrays and then add new items or move new items. And it's just, it was getting very complex. And then I was watching this interview with Rich Harris, and he's talking about his philosophies to Svelte and, and how, why he's excited about Svelte 5, which I guess is coming out soon.

[00:27:47] **Ben:** And one of the things he was talking about was how. The assignment operator is what triggers Svelte's reactivity and he brings up, oh yeah, objects and arrays can't be classically reactive with their push and, and, and pop because there's not an, there's not an assignment. He's like, so what a lot of people will do in their code is they'll do the non reactive push and pop and stuff.

[00:28:11] **Ben:** And then below that, they'll just set object equal to object. Like to do is equal to to do is. And he says, all that's there is to tell Svelte, Hey, I just overwrote this variable. Please re render it. And I'm like, Oh, that's so much easier than what they were doing in this course. That's all I had to know.

[00:28:28] **Ben:** It's just a hack I have to get around.

[00:28:30] **Adam:** I'm super excited for Svelte 5 and Runes. I don't know how much you've learned about that stuff, but

[00:28:34] **Ben:** I looked up runes like two hours before this podcast. So I don't know that much about it. I

[00:28:42] **Adam:** Like, it's a real short, like maybe 10 15 minute video. Easy to watch on like 1. And it's, you know, it's got some humor, you know, easy watch and, and informative, but also it's going to get you hyped for how it's felt. It's going to get even better.

[00:28:56] **Ben:** mean, so I, I skimmed one article that, that talked about a number of the runes and, I don't even know if I could tell you what a rune was only, only to say that I get, I get a little, like my Spidey sense tingles a little bit whenever I see having to wrap objects inside of other stuff in order to make things happen.

[00:29:14] **Ben:** And the only reason that gets up my, my hackles a little bit is, It's cause in AngularJS and the Angular and even Angular, I feel like is going down this path as well, where they're doing signals to, to make reactive state. AngularJS was such a simple mental model where basically you just did whatever you want and then Angular said, Hey, we'll just reconcile that with the DOM every time.

[00:29:38] **Ben:** And, and it had limitations, definitely. And if you're working with a lot of data, which, you know, you could argue is maybe not a great UX anyway, it had some performance issues. But it was just so easy to reason about because there was no magic. The magic was brute force. Like that's what made it so exciting.

[00:29:57] **Ben:** And, and I, and I just get a little apprehensive that stuff is becoming too clever and with that cleverness, we're starting to have to take on a lot of syntactic, not, cruft is not the right word, but like more ceremony.

[00:30:12] **Adam:** I hear you. I think, well, so that it sounds like the video that you're, you described that you watched was, it was an interview. He talked about how he's excited for Svelte 5. So I'm pretty sure I know which one you're talking about. and

[00:30:23] **Ben:** was long. It

[00:30:24] **Adam:** in that

[00:30:24] **Ben:** hour and a half long.

[00:30:25] **Adam:** Yeah. Yeah. And in that interview though, he, he mentions that they looked at like something like 50 different, possible implementations of like what eventually became ruins.

[00:30:35] **Adam:** And they just like tried a bunch of different things and threw it out because they were like, this isn't good enough. We don't like it. You know, it just doesn't feel right. And when they landed on the implementation that they're gonna go with, they were like, okay, this is, this is the one.

[00:30:48] **Ben:** It is really cool. I mean, you know, like the fact that you just export a variable and it becomes a prop that you can assign. I mean, that's so simple and clean and, oh, it's going away. Oh,

[00:31:00] **Adam:** It's gonna be different. It's gonna be different. Svelte

[00:31:03] **Ben:** I mean, it was just in terms of how do you, how do you make something that is easy enough to reason about and also very clever and, and, but then on the flip side of that.

[00:31:13] **Ben:** I, I built some, building something in Svelte, just kind of a simple, let me learn about Svelte. And at one point I had to, I'm like, how do I know if a property binding has changed, like the, the thing that's getting passed and changing, I started to Google for it. And like, there's no one way to do it.

[00:31:28] **Ben:** People are like, oh, you can just create a reactive block, you know, the dollar sign, colon, and just. Do open curly brace, close curly brace and everything inside that will get rerun whenever it has to. I'm like, Oh, that's weird. That's not really what I'm trying to do. So it starts to feel very like this works coincidentally.

[00:31:48] **Adam:** an incoming prop value changed or

[00:31:50] **Ben:** Yeah. Yeah. Like, I mean, I think even, so Angular, you know, I'm coming from an Angular background. So Angular has a, basically an on changes lifecycle hook. And I think custom elements have like an attribute value changed kind of a hook. You know, react has, like props will change or something.

[00:32:06] **Ben:** I, I, I don't do react very much,

[00:32:08] **Adam:** Oh, yeah, yeah, yeah, yeah, yeah. I know what you're talking about. It's been a while.

[00:32:11] **Ben:** yeah, so Svelte it felt very much like Svelte was like, nah.

[00:32:15] **Adam:** Component will receive props, that

[00:32:17] **Ben:** Yeah, yeah, yeah. Spelts, like, put it in a reactive statement and you'll learn about it eventually.

[00:32:23] **Adam:** Oh, okay. we are

[00:32:25] **Ben:** Yeah, yeah, yeah. Yeah.

[00:32:27] **Adam:** I blame you, man. You mentioned Svelte.

[00:32:29] **Ben:** sorry, sorry, Tim. I know Tim, has not had a lot of Svelte, insight here.

## [00:32:34] Personal Brands

[00:32:34] **Adam:** Okay. Well, let's, let's move on to our topic for the day. personal brands. and I think as the, the person with the largest X following on the podcast, we're going to have to defer to you, Ben. no, I mean, let's, let's, let's break that down a little bit actually. So, you know, you've been writing your blog for a million years.

[00:32:53] **Adam:** you have been sharing content consistently on your blog and on Twitter for Twitter X, whatever, for forever. and, and, you know, when you do that, when you are that consistent about it, I think, you know, most people would agree that the numbers are probably, unless you're terrible at it, the numbers are going to go up.

[00:33:12] **Adam:** Whether, you know, just how fast they're going to hockey stick up is, Is a function of how good you are at it and how lucky you get, I guess. But,

[00:33:18] **Adam:** Well, if can, if I can just jump in for a second and, and I know. go ahead.

[00:33:23] **Ben:** so I, you know, I do think of myself as having a brand for sure, but I think if I can just take a step back, I think everyone has a brand. The question isn't, do you have a brand? It's how much do you care about that brand? it's like, it's like when people say, not making a choice is making a choice.

[00:33:43] **Ben:** Like you have, everyone's making it. Yeah. And, and, and the, the reason I think it's maybe important to think about for a second is I can't tell you how many times I have tried to look someone up online, you know, like I'll meet someone, or, or like I'll have a physician and I want to look them up online and it's just like.

[00:34:04] **Ben:** It's just a black hole. It's just nothing. And you're like, how does this person not exist in the digital world in any way whatsoever? And you know, that, that's, that is a brand you've chosen to some degree that that is your representation in the world. And that's totally legitimate. I'm not, I'm not pooping on that.

[00:34:24] **Ben:** I'm just saying that we all have a brand and it's not just about Twitter and, and Twitch and, and TikTok. It's just how we interface with the world.

## [00:34:37] Reputation

[00:34:37] **Tim:** I mean, before we had called it brand, you know, we had professional reputation,

[00:34:42] **Ben:** Yeah, absolutely.

[00:34:44] **Tim:** everyone has a reputation, good or bad, everyone has a reputation. maybe reputation is for not being very well known. I mean, that's, that's, that's fair, but I'll say, I'm going to talk about your early days, Ben, when I first met you. Yeah, Kinky Solutions is what your blog was called. And, and, was that really, I mean, was that sort of, was that sort of persona you were trying to put out there? Cause when I met you, I totally, and I've said this before, like early in the days of the podcast, I'm like, I expected you to be this muscular and you were, but like rough, tough, beer, swilling, womanizing.

[00:35:22] **Tim:** You know, Code Bro, just complete jock. And just because that, that you're, you're, you're, you know, some of your examples were a little bit sexist and, and then I met you and you're like the most retiring, sweet, shy guy who's just, you know, scared, scared of everything. And, but just super, super nice teddy bear.

[00:35:43] **Tim:** You just wanted to give him a hug and I'm like, you know, was that, was, was that like, that was, you were trying to project or just.

[00:35:49] **Ben:** I don't think I was ever trying to project anything. It was more like I was just trying to have fun. And, and I, I was, my intention was never to have fun at anyone else's expense. It, it came across that way and that's very unfortunate. And I've moved away from that

[00:36:06] **Tim:** Yep.

[00:36:07] **Ben:** persona, if you will. Yeah. And I've,

[00:36:09] **Adam:** Yeah, yeah. It was naive and we're all naive for, in various ways,

[00:36:14] **Ben:** oh man, I look back just at decisions I've made in my life and I feel like I didn't start making good decisions until I was easily in my thirties. there, like, there's just so many things I look back. And, and shake my head and be like, Oh, what a, what is just a poor decision to have made at that time.

[00:36:32] **Ben:** And the crazy thing is, is I do think like I'm actually one of the good ones, you know, like there are people who make much worse decisions that I have, and I feel shame for a lot of the things that I've, I've, you know, past I've gone down. but yeah, I think I just, I loved programming and I still love programming.

[00:36:48] **Ben:** And it just added a little spice to it. I mean, it's not the right word, but like, I would just, I was, I was so enamored with programming and sharing and talking about programming. And it, and it, you know, and I was a young, man and it just sort of like, it was like a, you know, a two way win, how do I include other things that I think are fun and exciting?

[00:37:11] **Adam:** So I think for better or worse that You know, a person's personal brand is what people think of in general, like as a rule of thumb when they hear your name. Right. So for you right now, for like me, when I hear Ben Nadel, I think Cold Fusion, I think, too many line breaks, lots of comments.

[00:37:31] **Adam:** Uh,

[00:37:32] **Tim:** this is me photos.

[00:37:33] **Ben:** Yeah.

[00:37:35] **Adam:** And, and I mean, videos of your dog humping stuff,

[00:37:39] **Ben:** Totes

[00:37:41] **Adam:** and, never ending content, right? Like it's, it's like, there's always something every week it feels like from you, whether, whether it's tips on Twitter or blog posts or this podcast or whatever, like it's, you are always doing something and I admire that about you. But like. That's just what I think of, right?

[00:38:00] **Adam:** And so I think for me, that, that is what a personal brand is, right? And just like for Tim, I think that, the way that Tim has branded himself or, or been branded one, one way or the other, is he's the guy that looks like Doctor Who or, or used to show up to conferences dressed up in a, in a suit.

[00:38:18] **Tim:** And that, that was intentional, right? You go to a nerd conference and everyone's, you know, just wearing their sweatshirts and everything. And like, I'm like, if I go in a suit, I'm going to stand, it's like people, they might not even talk to me, but like, who's the dude in the suit? Particularly when I was speaking, I always wore, sometimes I would get casual, you know, later in the evening, but whenever I was speaking at conferences, I always wore a suit and it got a lot of attention.

[00:38:41] **Tim:** And so that was, is that who I am in real life? No,

[00:38:45] **Adam:** Was that like a piece of advice you took from Half Baked?

[00:38:47] **Tim:** I don't, I never watched Half

[00:38:48] **Adam:** you know, wow, you should. It's a stoner movie. Dave Chappelle. Pretty good stuff. Anyway,

[00:38:55] **Tim:** but I mean, yeah, my, you know, my family, we did cosplay and I had a really nice Doctor Who suit, before I, my belly got too big and I couldn't fit in it anymore. so I, I started wearing it. Some people don't even know who Doctor Who was and they're like, oh, it's a cool suit. Interesting. Brown suit with bright blue pinstripes.

[00:39:10] **Tim:** Okay. But, I was memorable and that was kind of the main thing I wanted to do is just, just to be memorable and, I guess it worked. I don't really care about that anymore. As, as I've gotten older, it's like, I don't care. I really don't.

[00:39:24] **Adam:** it's funny. I, I spent years not, I won't, not even close to obsessing about my personal brand, but it was just a thing that I was like aware of, right? You know, I was super proud for, this was back in the days of like when I, my blog was called Fusion Grokker and I was all about cold fusion. So, you know, a long, long time ago.

[00:39:44] **Adam:** and. you know, I was super proud of the fact that, like, when you Googled Adam Tuttle, I was, like, the first five results on Google or something like that. It was, like, my LinkedIn, my blog, my Twitter, you know, a bunch of other stuff, whatever. and now I think if you Google it, I might be on the first page.

[00:39:58] **Adam:** And I think that has a lot to do with the fact that I have I'm just at a different place in life now, right? Like,

[00:40:05] **Ben:** you got kids.

[00:40:06] **Adam:** for me, then yeah, and that has been a big part of it, but I think that My, it has a lot to do with my career, right? Like at that point in my career, I was looking for upward movement. I, and my current point, I'm looking for stability, right?

[00:40:21] **Adam:** I like where I am. And as long as my job continues to get better, continue to be challenging and, and, you know, that sort of thing, then, then I am not interested in moving. And, I think that because I don't have an interest in moving, I don't have an interest, I have no vested interest in being,

[00:40:39] **Tim:** Cultivating this

[00:40:39] **Adam:** known, yeah.

## [00:40:41] Serving Your Brand

[00:40:41] **Ben:** are tough because You, you formulate a brand or you, you know, conspire to have a brand. And then in, in some ways you become a subservient to that brand. And that brand begins instead of you thinking, what can I do to help my brand? You start to think about what do I have to do to keep my brand? And I definitely feel that way.

[00:41:08] **Ben:** and not in a bad way, but it's, so, so I talked about Svelte. I mean, I took the Svelte course. I built a little thing in Svelte to help me learn about it. And I couldn't leave it at that. I could have built this thing. No one can ever know about it and life would go on and I can move on to other stuff.

[00:41:26] **Ben:** But I feel compelled to write about it and post about it. And, and part of that is because. I know that doing that will help cement it in my mind. Like it's not, there is still part of me that is virtuous and, and doing something just for the love of it. But there is absolutely a hundred percent a part of me that thinks I need to write about this so that I can begin to at least cultivate the spark of a, Oh, Ben knows some stuff about Svelte in the public persona.

[00:41:59] **Ben:** And, it's, it's, you know, I don't know if that's the best use of my time, but I feel compelled to do that.

[00:42:05] **Tim:** That's a good way to learn. I mean, to teach is to learn twice, they say. So,

[00:42:09] **Ben:** Oh, I like that. I haven't heard that one before. I

[00:42:10] **Tim:** you know what When

[00:42:12] **Ben:** Classy.

[00:42:13] **Tim:** you're learning for yourself, it's one thing, but when you're learning to try to explain to someone else, it's a completely different thing. I think that's why you're so, able to talk about, you guys are sitting there talking about Svelte and I was like, it was way over my head.

[00:42:25] **Tim:** It was like, I was like, I don't even know how they're remembering these terms, but you know,

## [00:42:30] Push vs Pull

[00:42:30] **Ben:** Well, so here's one thing that I've been thinking about recently, because I run a blog and a blog is very much a, you come to me, I don't go to you kind of a thing. You know, like I'm, I'm, I'm writing it for myself. And, and when I say for myself, that is as much for my own learning as it is for the building up of my personal brand, but it is for me.

[00:42:52] **Ben:** At the end of the day, nowadays there's become this growing movement towards newsletters and sub stack. And, and, and that is very much a, like I am now pushing out to you. I write stuff and you subscribe and, or pay for it. Now it's, it's not just a personal brand. It's a product. And, and

[00:43:12] **Tim:** it's, it's almost like the blog is like someone. You know, walking up to your house, knocking on the door and you're like, yeah, come on in, but, but a newsletter is like, you showed up at their place going here, take

[00:43:21] **Ben:** yeah, yeah. Have you heard, have you heard the good news? and I don't know. I, and I, part of me has a, An insecurity about that, you know, there is a safety in having people come to you because you can always say, well, it doesn't matter if people don't like what I'm writing because I'm writing for me predominantly and people who like it will come and, and people who don't like it will, you know, they'll ignore me.

[00:43:44] **Ben:** And that's fine. And there's a very, there's a safety in that. But the second that you're now pushing information to people purposefully, I feel like you have to start chasing, chasing those clicks. You know, I can't write an article if, you know, I'm just trying to put myself in the sub stack mind space.

[00:44:00] **Ben:** I can't write an article because it just happens to be something I, I, I happened upon. And I thought it was very interesting. Let me write this up. Like you have to now start to take your audience into account and that's a very, it's a bold move. Oh

[00:44:13] **Tim:** a financial move. I mean, there is money to be made for having that subscription list.

[00:44:17] **Ben:** no, a hundred percent. And I'm not, I'm not, I'm not saying that it's bad to have a sub stack or, or a paid subscription or newsletter in general. I'm, I'm just saying, it's a, you, you have, you have explicitly moved out of the personal brand arena and you've stepped into the product arena and

[00:44:36] **Adam:** right. Personality as a product. Or, not personality, but like, my output is a product that you are.

[00:44:41] **Ben:** that's just a very different mindset. You know, if I'm. Right when I was writing my book and I didn't have much blogging to do for like three months. If you're doing that for yourself, it's not a problem. But if you have people who are paying you to write and release a weekly newsletter, you can't just disappear off the face of the earth for three months.

[00:45:00] **Ben:** That's, that's just not a thing. I assume. I don't, I don't actually subscribe to anything. Brand stuff.

## [00:45:06] Marketing

[00:45:06] **Adam:** strikes me that we haven't mentioned, I guess it, somebody mentioned it a minute or two ago, and that's when you think of it, marketing. you know, marketing is a word that comes to mind pretty quickly when you start talking about the word branding, or a brand. But I think we're hesitant to talk about personal branding as marketing ourselves, but really that's what it is, right?

[00:45:24] **Adam:** Like, you know, I was doing yeah. Okay. Yeah. Okay. So you're you're thinking about suits like that's that makes you memorable, right? But, doesn't necessarily get you an in somewhere, right? Like that that just that's awareness.

[00:45:41] **Tim:** I mean, I think, I think if people who are influencers, they definitely, they're marketing a hundred percent. They might not be anything like what they're, what they're, what they say or do. It's all an act. It's all completely fake. But you know, I think for most technical people, we're pushing information and knowledge and, I think there's a little less of the marketing side of it.

[00:46:01] **Adam:** but I think that it's a useful If you, if you are interested in, like, if you're, if you're hungry, if you're trying to get a better job, if you're trying to find that upward mobility, like think about that, right? Like you market yourself, you know, by improving your community's awareness of you and what you have to offer, you are building a personal brand and that brand itself can help you get a better job.

[00:46:28] **Adam:** Like for me, I'll, I'll give a very concrete example. I spent. Years and years blogging about ColdFusion stuff, I for a while became, somehow people started calling me the king of MangoBlog because I released like 20 different plugins for MangoBlog because I, I was like, hey, cool, a new CFML blogging engine.

[00:46:45] **Adam:** That's not blog CFC. Sorry, Ray. I was like, let me, let me check this out. It's cool. It's different. So I did, and it's like, okay, well, it'd be nice if it had this. So I wrote a plugin that did that. I had a really good plugin system. So I was like, plugin that does this. Let me write a plugin that does that.

[00:46:58] **Adam:** And I just started releasing new plugins and I had like 20 of them. And so people started calling me the King of Mangablog. And I was

[00:47:03] **Tim:** Wow. I've not thought of mango blogging in a long time. Holy smokes.

[00:47:08] **Adam:** it was fine, whatever. but like. You know, and, and, you know, I, I spent some time as a, an Adobe community professional, which I think is like, you know, Google Developer Expert or whatever. Like, there's just these company programs where they give you a free license to something in exchange for you giving them a bunch of your time to

[00:47:25] **Adam:** be a beta tester, basically.

[00:47:27] **Adam:** and as, as a sort of a, I guess I'll say indirect result of all of that. you know, because I was on Twitter talking about stuff a lot, and I was constantly writing on my blog. People were aware of me I ended up getting a job at the University of Pennsylvania because it was weird that I kind of heard this conversation kind of didn't, or it was like a conversation that I was like, I don't even know how to describe it, right?

[00:47:56] **Adam:** I got hired, and I was just like, it was a little small social circle of a couple of people, and they were like, you know, one of them was like, yeah, so we hired Adam, and, and so now there's no more ColdFusion developers in the area, like, they just, they knew that I was there, and that I was a ColdFusion expert, and, and I was local.

[00:48:13] **Adam:** Like, okay, snap him up, because he, you know, obviously can do this. And, and so like, that's the kind of situation you can put yourself in. And I mean, obviously if you're, if you're, drowning in people that have the same skills as you, then it's a little harder to stand out, but

[00:48:26] **Ben:** you know, this is circling back on that topic to something that I had mentioned before, which is how many times I've tried to look people up online and they just don't seem to exist anywhere and not to be judgy, but that's, yeah.

[00:48:41] **Adam:** Like, how many people, it's, it's becoming really popular now for people to be like, no, I don't have a Facebook account.

[00:48:46] **Ben:** That's fine. But, but if you, if you don't have a GitHub profile or a LinkedIn profile or something, something that just says you exist in this world, I don't, I don't know, it feels, it feels very weird to me. And it, and it could just be that you don't go by. You know, John Smith, you go by like CatBlaster5000, right?

[00:49:08] **Ben:** And it's just like, I didn't know to look that up because that's the name you've been using since AOL Instant Messenger. And that's, and you know, that's something, but it does seem there are so many ways to have a. Zero effort online presence, whether it's just like an about me site or, you know, it doesn't cost any money to have a LinkedIn profile or anything.

[00:49:30] **Ben:** It just feels weird to me when people seem to not exist online at all. It feels like a weird brand choice, you know, going back to the idea of personal brand,

[00:49:40] **Tim:** would imagine a lot of women who work in. Maybe

[00:49:43] **Ben:** can a hundred percent understand women not

[00:49:46] **Tim:** that's very, it's a little scary to put, you know, put all that information out there cause they get treated a whole lot different online than we

[00:49:52] **Ben:** Yeah, that's for sure.

[00:49:54] **Adam:** So, I mean, I think you, if you were looking for somebody who was going to help you disappear, like if you wanted to do like, you know, citizens, witness protection program, right? Like you just wanted to disappear, move to a different town, be a new person. You would want somebody who you couldn't find online, right? They're going to be the one that, that knows how to, to actually disappear you.

[00:50:17] **Tim:** Cousins yet to die in Amish town. Let's go.

## [00:50:19] Benefits of a Brand

[00:50:19] **Ben:** I think the reality is having a brand helps you, you know, assuming it's a good brand and not a tarnished brand. I think

[00:50:29] **Adam:** your, your brand is, you're that that

[00:50:32] **Ben:** Yeah.

[00:50:32] **Adam:** ruins all the forum posts.

[00:50:34] **Ben:** You know, I think it's just human nature that if you have a group of people to choose from, and you have a couple of people that you've never heard their name before, and one person where maybe all you've done is heard their name once. Human nature, I think is just going to be like, I'm going to go with this guy. I've heard his name before having, you know, and I think there's, there's something, there's something very real about that.

[00:50:59] **Tim:** the modern equivalent of it's, it's not what you know, but who you know. And so if they, you know, in this day and age where everyone has their own pulpit that they can preach from on X or a blog or Facebook, it's like, yeah, if you get known, they were like, I know the guy, I've read some of his stuff.

[00:51:15] **Tim:** He's really smart. I enjoyed that. You know, that's the same thing. They know you or they thinking they know you. So.

[00:51:19] **Ben:** Yeah. You get the, what is it called? The halo effect where if you do something good, then people just assume that that good stuff sort of transfers over into other things.

[00:51:29] **Tim:** Yeah. Oh, it's like when I had the, I had a short for a few years, I had a blog and I did a lot of writing about SQL server and deadlock, you know, I had several people, I think, I got a job, not a contract from the, the master's tournament for the PGA. To help them with some problems they're having.

[00:51:46] **Tim:** It's like, I probably, you know, what I learned, I learned from other people. I definitely was not the SQL expert, but I, I had a lot of experience with it. And so I, I was able to help them, but you know why they came to me. Well they found a blog and there's probably a lot more smarter people they could have talked to.

[00:52:03] **Tim:** But they chose me cause they read about it and believed it. So

[00:52:06] **Ben:** Absolutely. So maybe, maybe to close, just to say that you have a brand, period. That's not a choice. But the choice.

[00:52:14] **Adam:** to do with it is

[00:52:15] **Ben:** Yeah, exactly.

## [00:52:16] Patreon

[00:52:16] **Adam:** Alright, well then, this episode of Working Code was brought to you by Adam's Life Relocation Service. You've never heard of us, and that's how good we are. And listeners like you, if you're enjoying the show And you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:52:33] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock. I have no idea what we're going to talk about on the after show. Does anybody have a topic you wanted to cover?

[00:52:47] **Ben:** I've been hearing a couple of podcasts lately talk, make reference to some recent studies that copilot is actually problematic. Like they're finding that code maintenance is becoming harder and code duplication is becoming more prevalent. I don't know if anyone has.

[00:53:04] **Tim:** I've read the same

[00:53:05] **Ben:** I'd be curious to know a little bit more about that if anyone

[00:53:07] **Adam:** let's, we'll dive into that in the after show. And if you have no idea what we're talking about, after show is the outro is going to play, but for patrons, after the outro plays, we just keep talking. And sometimes it's five minutes, sometimes it's another half hour. And we just, you know, whatever's on our minds.

[00:53:24] **Adam:** Sometimes it's TV, sometimes it's more tech, you never know. but, the patrons of the show financially support us, help keep this, keep the lights on and the mics running, rolling. and if you want to do that, if you want to help us out, you can go to patreon.com/workingcodepod. And the after show is one of the perks that you get it.

[00:53:38] **Adam:** In addition to that, you get a special patron only channels on our discord and a couple of other things. so that's going to do it for us this week. We'll catch you next week. And until then,

[00:53:48] **Tim:** Remember, your heart matters, so keep loving your own brand,
