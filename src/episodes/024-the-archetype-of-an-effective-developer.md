---
title: "024: The Archetype of an Effective Developer"
description: "This week, the crew discusses which habits make - or break - the most effective developers."
date: 2021-05-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/024-the-archetype-of-an-effective-developer/id1544142288?i=1000523154127"></iframe>

We all love the Hollywood portrayal of the "brilliant programmer" who can step in and just crush it at a moment's notice. We've probably all fantasized about _being that programmer_. But, that's not how people work. And it's not how teams work. Highly effective developers don't just "crush it" - they cultivate good habits that they then apply consistently, day-in and day-out, for years. This week, the crew discusses which habits make - or break - the most effective developers.

## Triumphs &amp; Failures

- **Adam's Triumph** - After struggling to get several Java-based feature flag services configured correctly in ColdFusion (which is one layer of indirection above Java), Adam decided to pull the ultimate power move and created his own open-source, ColdFusion-based feature flag library: [Semaphore][semaphore]. While still in active development, it's already feeling very "feature complete". Pull-requests welcome!

- **Ben's Failure** - Without being able to point at anything in particular, this week kind of just kicked his butt. Without a Product Manager (PM) or an Engineering Manager (EM) on his team, he's felt as though noone is "protecting" him or his people. And, even though an EM may not have actually made a the week better, there's an emotional cost to feeling so exposed. One saving grace, however, is that he received a _stellar review_ from someone on the Customer Facing Team (CFT). So, he must be doing _something_ right.

- **Carol's Triumph** - She totally survived a mercury-based allergic reaction to something she ate! That which doesn't kill Carol only makes her bolder when it comes to that sweet, sweet shellfish.

- **Tim's Triumph** - He recently built a custom solution for one of his customers. However, he built it with clean boundaries and multi-tenancy in mind. Which means, now that he's successfully rolled-it-out to his first customer, he's ready to cash-in on that work by using the same solution as an upsell opportunity for his other customers. He's even gone back and refactored some of the architecture using the [Clean Code tips from our earlier book review][working-code-022].

## Notes &amp; Links

- [Semaphore][semaphore] - A minimalist Feature Flag engine for CFML apps.
- [Taffy](https://github.com/atuttle/Taffy) - A low friction, extremely simple way to build REST-ful end-points in your CFML apps.
- [FW/1](http://framework-one.github.io/) - A family of small, lightweight, convention-over-configuration frameworks, primarily for CFML apps.
- [Oh My Zsh](https://ohmyz.sh/) - A delightful, open source, community-driven framework for managing your Zsh configuration.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[semaphore]: https://adamtuttle.codes/blog/2021/introducing-semaphore/
[working-code]: https://workingcode.dev/
[working-code-022]: https://workingcode.dev/episodes/022-book-club-1-clean-code-by-uncle-bob-martin-pt1/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/024-the-archetype-of-an-effective-developer.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I feel like I've been on too much of a streak of triumphs, but I don't really have a fail in mind. You're

[00:00:05] **Tim:** a legend. You eat triumphs for breakfast.

[00:00:09] **Adam:** My fail is I haven't had a fail in a while. That's

[00:00:13] **Tim:** like the job interview question where they say, you know, What's your, um, biggest weakness? What's your biggest weakness?

[00:00:19] **Tim:** And it's always some BS, like, I just care too much, or I don't know when to stop working.

[00:00:25] **Ben:** I'm probably too much of a perfectionist.

[00:00:41] **Adam:** It is show number 24 for May the 26th. And on today's show, we're going to talk about the archetype of an effective developer. And as usual, we're going to start with our triumphs and fails, and I'm going to fill in here real quick. Carol couldn't be with us tonight. She had an allergic reaction to something and she's at the hospital, so hopefully she's doing well.

[00:00:58] **Adam:** Get

[00:00:58] **Tim:** well, Carol. Worried about

[00:00:59] **Adam:** you. Feel better soon. So, without Carol, I guess, Ben, it's your turn to go first. I just, yeah, she always seems to miss her turn to go first. Just busy snowboarding or sick. She can go first next week. Yeah. All right, Ben, what do you got?

[00:01:14] **Ben:** Uh, I'm gonna kick it off with a failure, which is just that this week has been a little overwhelming.

[00:01:22] **Ben:** Work's just been really tough and I don't know if I could point my finger at anything in particular other than just I feel like I'm being pulled in a bunch of different directions. Like, there's a lot of high priority emergency tasks and since I don't have a manager, I feel like there's no one protecting me.

[00:01:39] **Ben:** And I don't know if a manager would protect me, but sometimes it's nice to know that there's someone who you could maybe just... Call on and be like, Hey, you just need to help me figure out how to debounce some of this work or something, but I don't have any of those people right now. So kind of on my own, trying to figure out how to best prioritize things and how to best cut corners where I can cut corners.

[00:01:59] **Ben:** And I don't know, it's, it's just been a little bit of an overwhelming week. That's a, that's a bummer. Tomorrow's Friday.

[00:02:05] **Adam:** That's cool. Yay.

[00:02:08] **Ben:** And you know what the crazy part is, in the midst of this week, I got, um, a random piece of feedback from someone on our customer facing team that was like super, super positive and was like, Hey, you know, like Ben is so great with the customers and, and, and like, he's really effective at solving problems.

[00:02:25] **Ben:** And like, there was like this really glowing review from someone on a totally different team, which I think helped me get through this week. But this week has just been overall

[00:02:34] **Tim:** crushing.

[00:02:35] **Adam:** When you say it like that, it sounds pretty bad. Crushing. You know what, Ben? In life,

[00:02:40] **Tim:** sometimes you're the football and sometimes you're the kicker.

[00:02:43] **Tim:** Today, you're the football.

[00:02:46] **Ben:** What

[00:02:46] **Tim:** about you, Adam? What do you got

[00:02:47] **Adam:** going

[00:02:47] **Tim:** on?

[00:02:48] **Adam:** Um, well, I got a triumph, which I feel a little bit bad for. I feel like I've had way too many triumphs in a row here, but I'm just, I'm on, I'm riding high and I'm just going to keep, yeah, I'm just going to keep winning. All I do is win, win, win.

[00:02:59] **Adam:** Um, and I also, I'm going to start this by just apologizing. You know, I'm going to try to mute it as much as I can when I'm not speaking, but there may be some that sneak in while I'm speaking. Um, we are in the middle of replacing our floors in our house and my wife is downstairs ripping up our laundry room floor right now.

[00:03:15] **Adam:** So there may be some bangs and Who knows what sneaking through apologize for that. Um, anyway, my, my triumph. Um, so I had, we've talked, I think, in the past about, uh, my frustration trying to Get either Flagsmith or Split. io running in my company's application. I don't remember if that was on the main show or if that was on the after show, but I know we've talked about it.

[00:03:39] **Adam:** Frustration with things like, you know, this application runs on CFML and so that's on top of Java and there's a lot of stuff that I find when I'm trying to use something that's for Java. Like technically, it should be possible, but there's, you know, when you're, when you're running another abstraction layer, there's missing documentation is what it feels like.

[00:04:00] **Tim:** You're talking

[00:04:01] **Adam:** about feature flags, right? Yes. Yeah. So that's what Split. io and Flagsmith are. Feature flag services, paid services. Anyway, so I had burned a couple of hours here and there of my free time trying to get this thing on its feet to see if I could get it into a state where I could show this off to my team and be like, look, let's do this.

[00:04:20] **Adam:** I've already done the initial work. Let's put it in our project and see how well it can help us. And I got enough frustrated with it that I just had sort of a fudge it, darn it all to heck moment, and I decided I'm just gonna roll my own. I was so fed up with the problems that I just figured by the time I get this working, I could have rolled my own anyway, and then it would work the way I want.

[00:04:43] **Adam:** So I'm gonna do the the thing you're not supposed to do and just roll my own, start from scratch. Uh, and see where it goes, and I'm having a lot of fun with it, at least, and it's given me an opportunity to do some TDD and to play with some tools I haven't played with before, some CFML test, uh, mocking and code coverage and that sort of stuff, and I'm playing with the GitHub Actions and, um, automating the tests on pull requests, and it's, it's been fun and exciting to start something new, and I'm excited at the prospect of being able to have feature flags in my app soon, so.

[00:05:18] **Adam:** Heck yeah.

[00:05:20] **Tim:** How open source is this going to be?

[00:05:22] **Adam:** It's already on GitHub. It's not in a useful state at the moment, but you know, what it has in it right now is basically the initial implementation of a rules engine. So there's like a, basically a domain specific language, a DSL for defining rules as data.

[00:05:41] **Adam:** Rules being like the selection criteria for a segment of users for your audience, uh, for your, for your flags. I mean, and some functions that allow you to pass in like a struct that identifies the user and the flag name, and it'll tell you whether or not the user.

[00:06:02] **Adam:** And, uh, oh, man, I gotta, I gotta do a shout out here. So, uh, a friend of the show, Adam Cameron, and I were chatting about... Frit, you mean our hater. Hater of the show. Uh, we were talking about a particular... feature. I showed him the code and, uh, he was, he pointed out something in it. I, you know, I had done the, all right, I got to rewind here a little bit.

[00:06:24] **Adam:** So when we talked about on the feature flags episode, we talked about how you can target a percentage of your users. And I was, I was dying to know how that was done. And we eventually boiled it down to is effectively you get, you know, some input that identifies your user and that gets Like, let's just call it hashed down to something like a CRC, a checksum, numeric value, like something between zero and one, and that lets you say, okay, is this person above the percentage or below it?

[00:06:51] **Adam:** And so that's how you decide whether or not they're included. So that was one of the things that I implemented already in the rules engine. Um, and the way that I did it was, I put a comment next to it, like, does this make any sense at all, whatever, I don't know if this is safe, I don't know if this is the right way, whatever, but this is what I did, and so in order to take that user object and convert it into a number between 0 and 1, what I did was I serialized And then I MD5 hash it, and then I extract all of the letters out of the MD5 hash, leaving only the digits behind.

[00:07:24] **Adam:** And then I plop a zero dot in front of it. Which is ridiculous. Absolutely, you know. Upfront with that, but so he questioned that and he's like, he sent me the link to the CRC Wikipedia page and we were chatting and we went back and forth about this and I was kind of complaining about how certain CFML platforms that shall go unnamed their serialized JSON function.

[00:07:52] **Adam:** is not necessarily deterministic when it serializes a structure. Sometimes the keys will be in one order, sometimes they'll be in another order. And I was complaining because that makes the process of getting from a primitive structure data type to a numeric In a deterministic way, right? If you get an object with key A, value 1, you want that to always be converted to the exact same number every time.

[00:08:19] **Adam:** For consistency's sake, right? You don't want the flag to be on for this request, and then when you refresh the page, the flag is off, right? So, consistent experience. So I was talking with him about this problem and we went back and forth about it for a little while and eventually what it came down to was he was like, Serialize the JSON and then take that string and sort all the characters in it.

[00:08:40] **Adam:** Because what, I don't need the actual JSON, I just need to convert it from a primitive... Complex data type to a string so that I can take that string and hash it, right, because hash expects a string as input. So I just need something in the middle that's going to be deterministic. So by sorting it, it doesn't matter what the order of the keys are in the JSON, the characters are always going to be the same, they'll just be in a different order.

[00:09:02] **Adam:** Sorting it puts them in a deterministic order. And there you go, you've got a deterministic, I, I

[00:09:08] **Tim:** hate the fact that I have to give my hater compliments on saying that it's an excellent

[00:09:14] **Adam:** lateral thinking. I told him that was evil genius, like chaotic good, right? That was so just perfect. I loved it. So I put his face in the readme, like this was his idea.

[00:09:27] **Adam:** This was awesome. Well, is it popular as our. feature flag

[00:09:31] **Tim:** episode was. I think maybe you should just shout out, you know, what the, the GitHub. Yeah, sure. So that maybe some want to contribute to this. Cause it's, I think a lot of people are thinking about it right

[00:09:40] **Adam:** now. Awesome. Well, uh, so it's github.com/atuttle.

[00:09:44] **Adam:** That's A T U T T L E. slash semaphore, S E M A P H O R E. Uh, which is a system of sending messages by holding, uh, flags in your arms, and, and it's like, it's like Morse code that you can do with your, with hands and your, yeah. Oh. Yeah, and on

[00:10:01] **Tim:** the, if you're on a ship, you, you signal another ship with semaphore.

[00:10:03] **Tim:** Right,

[00:10:04] **Adam:** or if you're ever at the beach and you see the lifeguards, like, waving flags at each other, that's what they're doing. Oh, I thought you were just having a parade. Anyway, so yeah, that's my triumph. And now that I've taken up, like, ten minutes, All right. Show's over. Good show. Oh, that's awesome. Your heart matters.

[00:10:19] **Adam:** Um, but, uh, yeah, I'm having a lot of fun and that's all I have to say. So Tim, what about you? I'm going to go with

[00:10:27] **Tim:** the triumph. I had a fail last week, so, you know, I'm not a winner like you, Adam.

[00:10:32] **Adam:** We can't all be. We can't all be constant winners,

[00:10:35] **Tim:** uh, but no, I, I, I feel like I'm really reaping the benefits of.

[00:10:40] **Tim:** What I feel, it's a bit vain because I wrote it all, but it's a, it's of a well built multi tenant system. Nice. I got to give you some credit for it, Adam, because I built it, uh, when I say systems, it's systems. So I, I built. Uh, an API that talks to disparate data sources that are somewhat similar but very different in actual implementation, create a unified API for it, uh, that pulls data from So you're like,

[00:11:09] **Adam:** you're like federating APIs?

[00:11:10] **Adam:** Yeah. Yeah, I'm federating.

[00:11:12] **Tim:** Well, they're not even APIs. I'm actually talking directly to data sources. Oh, okay. Awesome. Um, because they don't have an API. That's the problem. Mm hmm. They didn't have one, and it's a bunch of different systems that are all slightly different. They should be the same but they're not because they're not multi tenant so I'm just talking directly to their data sources and I'm taking all that, federating that data and then presenting a unified API for it for multiple different tenants.

[00:11:37] **Tim:** So that, that I had done years ago and recently I built this new thing which is just a, a way to present data via IVR response and, and also web portals and stuff and so I've been working, you know, as I mentioned earlier my, one of my triumphs was I finally got that launched, it went well. Well, this week what I've been doing is like, I want to take this same new thing that I've done and I've done it in a multi tenant way and I want to make sure that I can, I want to sell this to all the other people, right?

[00:12:06] **Tim:** And so today in about a couple, two hours, I just, you know, went through a few things and found a few things where I realized that had I done it the way Uncle Bob told me to do it, I wouldn't have had any problem at all. I had way too, some procedures that were way too big. I didn't break things down into separate functions.

[00:12:25] **Tim:** Because in a multi tenant system, which I basically do is, you know, if, if a system, you know, let's say it has a way it calculates its balance, system A calculates a balance this way, B, C, and D all calculate a balance that way, E is slightly different. Well, you just extend the base, overwrite that one function.

[00:12:47] **Tim:** Problem is I didn't make my functions atomic enough. There's not small enough, so. I've been refactoring a lot of that this week to please Uncle Bob. Nice. But, but, uh, yeah, so within a couple hours, I have a very complex system working on a totally different tenant and returning and it passed all my tests.

[00:13:10] **Tim:** I have functional tests that I can run. I can run all those tests. I'm like, all right, cool. So my next thing is I'm going to go to that customer and say, I've got a new product for you here. Um, it's already live. It's already, you know, you can go ahead and use it if you wish, and we'll start billing you. So that's, that makes me super happy.

[00:13:29] **Tim:** Last week, I honestly felt like a loser last week. I was like really questioning if I even should be a developer. Oh, we all have those days.

[00:13:37] **Adam:** You

[00:13:37] **Ben:** know, you were, you were sitting back and just like enjoying the data and dealing with the customers who are satisfied. That

[00:13:43] **Tim:** was, that was, that was like two weeks ago.

[00:13:45] **Tim:** That was two weeks ago?

[00:13:46] **Adam:** Two weeks ago. Last week

[00:13:47] **Tim:** I totally, yeah, I totally just thought I should quit. Now this week, it's, yeah, I think maybe I'm bipolar. I don't know. Um, I'm not, but yeah, yeah, so it's like, it's just massively satisfying to see you build a multi tenant system and you actually start using it.

[00:14:06] **Tim:** And like, it works. And I knew it, I knew it would, because I'd done the same thing with the first system and like changes with that are very trivial. If there's some customization in a new client. It's a very trivial to change it. Um, and the other thing I had to do was versioning and I'd be interested to see how you're doing Semaphore because I was actually thinking today, I'm like, I could do feature flags with my, my versioning system.

[00:14:32] **Tim:** Cause all I'd have to do is just base the version off the existing version and just add a flag feature to it. So yeah, we'll have to have a chat offline about that. Definitely, I would definitely like to see what you're doing.

[00:14:43] **Adam:** So Tim, I have to tell you, every time now I am on the phone and the phone talks to me, like not a person, but the, you know, a computer talks to me through the phone, f k Tim.

[00:14:53] **Adam:** Thank you. I have to cut that out. I'll just bleep it. Yeah. Like just, what did we decide to call it? It's like infuriating voice robot or something. Yeah, exactly. Oh, I hate them so much.

[00:15:05] **Tim:** Yeah, I hate them too. But a lot of people, a lot of people use them. I mean. Exactly.

[00:15:11] **Adam:** I'm curious about your multi tenant thing because we are, um, moving in that direction, right?

[00:15:15] **Adam:** I told you before we started. Not at all multi tenant and we're trying to migrate our code base to be multi tenant. You talked about how you had sort of a base class or an original implementation and then you kind of used polymorphism to change that one function or whatever for this one customer or the tenant.

[00:15:36] **Adam:** And I'm curious, is your multi tenant system one, like one repository per customer?

[00:15:42] **Tim:** Okay, so then. No, no, it's one

[00:15:43] **Adam:** repository per the system. Okay. All customers work off that same thing. So how does that work where like, how do you have code, code customizations for one tenant that don't affect another if it's all like using the same code?

[00:15:59] **Adam:** So it's a bit convention based. So I have a,

[00:16:02] **Tim:** I basically have a default class. And so whenever it calls, so in your, your, uh, Taffy API, when Taffy. has a resource. So the resource basically goes and looks, I have some, I have another folder I call components. Whenever it tries to, um, to call the resource, it will say, uh, is, is there a folder with this name and this CFC in it, right?

[00:16:27] **Tim:** This CFC function. If there's not, it just goes, uses the default. So it will overwrite those. So it's basically overwriting. So then I can extend Um, so like say for instance, I have customer B, it has no customizations for that particular function. Well, I just don't put anything in that folder. Uh, and then I, above that I have another layer, which is version.

[00:16:51] **Tim:** So I, you know, in the URL, that is all based off the DNS name. So you have customer A, you know, API. com, customer B. So

[00:16:58] **Adam:** the host name, yeah. Yeah, it looks at the host

[00:17:00] **Tim:** name and figures out, all right, you're using this tenant. So it gives you. It will try to look for that tenant's name in the folders. If it doesn't find it, it falls back to default.

[00:17:09] **Tim:** And it's also in the URL, uh, you'll have version numbers. So V1, V1,

[00:17:15] **Adam:** 1, V1,

[00:17:15] **Tim:** 2. V1,

[00:17:16] **Adam:** 2, final, Tim. Final, final, final, really final.

[00:17:22] **Tim:** So that way, if you want to, you know, launch a new version and perhaps some people will adopt it and some tenants won't, you don't break what was in the prior.

[00:17:33] **Adam:** I'm getting lots of ideas over here.

[00:17:35] **Adam:** It works, it works extremely well. So, we use Framework 1, and I'm just sitting here thinking, like, when you started talking about choosing a different CFC, but, you know, with a, like a tenant ID or something in the file name, based on the, the current tenant in the request, if it exists, and if not, defaulting back to the other one.

[00:17:52] **Adam:** That, that made a lot of sense, but my, where my brain went. immediately was, well, what about views? What am I going to do when I need to have a custom view? And it's easy enough, I think, to use polymorphism and write sort of a wrapper for the framework that does the same sort of thing for, for view names, right?

[00:18:09] **Adam:** Look for a view custom for this tenant. But I guess where I'm kind of struggling is like, how am I going to, it would be nice if I didn't have to duplicate all of that view logic. Right. In,

[00:18:21] **Ben:** in framework one, I believe. Uh, views can be like Russian doll nesting, where you can have a view. And then I think you can essentially give every view parent view, which is typically a layout, but I think you can actually just have.

[00:18:36] **Ben:** I think you can just like queue up views and then it'll just sort of like roll up into each other,

[00:18:41] **Adam:** maybe. Also look into that. I know, so there is layouts. We use those for layout type things already. And, and you can also do partials, right? So there's like a view function. And so within a view, you can call the view function, which I think is probably what you're talking about, like queuing up other views.

[00:18:55] **Adam:** But they've, it's, it's almost like a, like an include is the way it works out. Um, wherever you drop in that view function, it renders that thing, which might be.

[00:19:06] **Tim:** I don't know how to help you there because none of the, I never write any view layer stuff. It's all

[00:19:11] **Ben:** just JSON payloads here and there. It's

[00:19:13] **Adam:** just like, yeah, here's your JSON, sir.

[00:19:15] **Adam:** Man, that's, that's my dream. Get out of the view business entirely. Yeah, I mean, totally

[00:19:19] **Tim:** in the API business. All

[00:19:21] **Adam:** right, sounds like we're done with that. Let's move on and talk about the archetype of an effective developer. What does that mean? Yeah, so I mean, I

[00:19:29] **Tim:** suggested this topic because I think coming off the last show, we talked about clean code, right?

[00:19:34] **Tim:** And that was extremely eye opening and clean and being a clean coder, if you can get there, I think all of us, I think it's a progression. All of us are working toward that. But even if you were the best clean coder in the world, if you don't have good habits, an archetype basically is a series of habits, a way of working.

[00:19:56] **Tim:** A mode of working. You don't have good habits as a person, as a developer, as a worker. Um, the best coder in the world isn't going to be as effective as someone who has really good habits. And so that's kind of what I was thinking is, you know, what's the commonality? The very successful people who are good at coding, a lot of them have very similar characteristics in the way they work and the things they choose to do.

[00:20:31] **Adam:** So do you want to start us off, Tim? Uh,

[00:20:33] **Tim:** sure. So this one, actually, I'm going to, we have them on order, we have a little, little thing here, that little outline that we're following. I'm going to jump. Yeah, go ahead. Which I think is, I think it might sound silly at first, but if you really think about it, it's kind of important and that's learn touch typing.

[00:20:50] **Tim:** Okay. Right? I mean, you spend all your time. Typing. Yep. And so if you don't know how to type quickly and touch typing is, you know, no one can convince me that hunting and pecking mm-hmm. with, with one, you know, two fingers is faster than, and I, I'll be honest, I wasn't that good of a touch typer. I took, you know, we, we called it, uh, it was, it was typing back then.

[00:21:14] **Tim:** It's keyboarding nowadays. Mm-hmm. But yeah, back that it was typing on actual typewriters. I wasn't that very good, but I've gotten extremely good, you know, since I've been doing this for a living

[00:21:25] **Adam:** now. Do you work in the typing pool or something? No, no.

[00:21:30] **Tim:** I mean, as a programmer, I just learned to improve my typing so that, you know, I never, if you're looking down at your keyboard to type, you're really hindering yourself because you should be looking at the code.

[00:21:40] **Adam:** Yeah. I have to look down occasionally like, oh, which. Number has that symbol that I need or, you know.

[00:21:47] **Ben:** Sometimes I'll type the wrong key like nine times in a row where I'm trying to find it and finally I have to look and I'm like, Oh, where the heck is that backslash?

[00:21:55] **Adam:** I find the thing I do

[00:21:56] **Tim:** the worst, and it's usually on passwords cause I can't see it as a type, is I don't, I will shift too early.

[00:22:03] **Tim:** My shifts are too fast, so I will uppercase something that shouldn't be uppercase and my password fails. Cause you know, you usually have to have a special character and mine tends to be. You know, uh, like one of, one of the ones above the number symbols. And so I have to shift to get it. And it's like, I will shift way too early.

[00:22:21] **Tim:** So just too

[00:22:22] **Ben:** fast. I know as developers, we spend a lot of time, I think in, in deep thought and we're thinking about problems and how things should be wired together, but every now and then I'll be. in a situation where I just see it in my head and literally the limiting factor is how fast I can get it from my head onto paper, so to speak.

[00:22:44] **Ben:** And, and that's the ability to just type that out and just let it flow. I think actually on an earlier episode, Tim, you talked about flow is like you're in the middle of a river and it just has to flow through you. And like, there are those moments where you're like, I have this program in my head. It just needs to get into this file.

[00:22:59] **Ben:** And I just need to type.

[00:23:02] **Tim:** Oh, yeah.

[00:23:02] **Adam:** My kids sometimes are like, you don't do anything, dad. You just sit at the computer all day. Why, why can't we have unlimited screen time? I'm like, well, I know it looks like my job is to sit here and stare at the screen and to type, but my job is to use my brain. Yeah. Yeah.

[00:23:18] **Tim:** There's nothing more exhausting than a day of coding, like really good hmm.

[00:23:26] **Adam:** You're out of spoons.

[00:23:29] **Ben:** And, and kind of on the same line as touch typing, and maybe this is not even related enough, but tab completion on the command line is, is like such a power up sort of move. Understanding how tab completion works, uh, can be just a huge efficiency gain.

[00:23:48] **Adam:** Yeah. I mean, from there, we should probably just pivot right into use the command line, right?

[00:23:51] **Adam:** So if you have the choice between using, uh, a GUI, a graphical user interface, or a command line, so for example, like git, right? Most of us probably have a git GUI installed. No. No, you don't? Wow, that's impressive. I still have one. You know, what I use mine for is when I go too long without committing and I need to go through and like...

[00:24:12] **Adam:** I'm kind of picky about my commits, right. I want... I never just like commit all, like whatever, like catch up. As my commit message, you know, I want, this is a logical commit, you know, the things that I'm committing together make sense together. Um, that way if I need to revert one commit or something, it makes sense when I'm reverting.

[00:24:29] **Adam:** And so I'm, I will go through my, I use a source tree. And, uh, I'll go through that and pick out the different lines that I want to stage and then I'll, you know, put together the stage and I'll do my, uh, command line stuff,

[00:24:42] **Tim:** uh, to commit and push. Yeah, I mean, Ben, you're totally right. You know, using the tab powerups, I, I, I guess maybe because I learned programming back in the basic days, that command line to me just feels like home.

[00:24:57] **Tim:** Yeah. I mean,

[00:24:57] **Adam:** Well, anything that lets you use the keyboard rather than the mouse, I think is going to be a, uh, a series of. Like a million fraction of a second speed improvements and productivity improvements, right? You're not gonna have to reach over for the mouse and drag it across the screen.

[00:25:12] **Ben:** I would say I'm not even particularly good at the command line.

[00:25:16] **Ben:** Like I'm, I don't know how to program in Bash or anything. You know, the number of commands that I understand, I could probably count on two hands. Um, just understanding tab completion and one of the, uh, super awesome things is the dash. Mm-hmm. the dash will let you jump back and forth between things. So like if you do CD dash, it'll jump to the previous Yeah.

[00:25:38] **Ben:** Where you were before. Uh, thing. Yep. And get checkout will do the same thing. Mm-hmm. So you could do get checkout Dash or get Rebase dash. Uh, I don't know if Freebase works. But, uh, that, I don't know. There's like just a handful of things that I have found that are super helpful. Yeah. Yo,

[00:25:53] **Adam:** up arrow for show.

[00:25:54] **Adam:** So, okay. I have to, I feel like I have to shout out ZShell and OhMyZSH. It's just, it's basically a package of like a whole bunch of different productivity tools that improve your command line. And then, um, it comes with a ton of different plugins. And, you know, if you're into that sort of thing, the customization, it's got like themes as well.

[00:26:14] **Adam:** So you can kind of make your CLI look how you want. But it's got. Great in great GI integration. So for example, when I'm sitting there typing on the command line, Git and Docker and just about everything else, if I type the command correctly, then the, the, that first keyword like Docker or Git or whatever turns bright green.

[00:26:32] **Adam:** If I mistype it right, if I type D c o k e R or something, then it turns bright red. So I go, oh, okay. Catch it for me. Right? So I like go back and fix that before I even try to submit it. And then it's got tab completion for the different commands. So I can like, uh, your git branch names, it'll auto complete those for you.

[00:26:47] **Adam:** Um, it's,

[00:26:49] **Tim:** it's like,

[00:26:49] **Adam:** it's awesome. It, it's fantastic. I

[00:26:52] **Tim:** mean, I'm on Windows, so I use PowerShell. I use PowerShell a lot. And, you know, in my home folder, cause when I type, when I click my PowerShell icon, it basically goes to my. See users, you know, Tim Cunningham, I have so many PS files. And so I just, but I know how they're, I named them well, so I can just type a few characters, tab, get to the, to the, uh, the thing I want.

[00:27:17] **Tim:** So I, I mean, I command line, I script everything that I have to do. Um, and the biggest thing, Windows subsystem for Linux is, was a game changer for me. I'm sure it was. I'm, I'm very, I'm very, I love using Linux and so being able to drop down to Linux and do stuff and using all the grep and all the tail stuff that, that, that, you know, they have that Windows doesn't have is just fantastic.

[00:27:43] **Tim:** So yeah, use the command line. It's so much faster. I

[00:27:46] **Adam:** think that's like 80% of what makes a Mac so appealing to a developer. It's basically Unix. Yeah, it's a flavor of Unix.

[00:27:56] **Ben:** Ironically, I don't like aliases for some reason, and I think it's purely emotional. I enjoy typing stuff out as much as I want to

[00:28:06] **Adam:** be fast.

[00:28:07] **Adam:** So this is the prettier argument all over again, isn't it?

[00:28:11] **Tim:** You see the pattern here, buddy?

[00:28:13] **Ben:** I don't know what it is. I know a lot of people have things like GC for git commit or GCM and stuff like that. I like typing git commit and git checkout dash b and git rebase master and that stuff. And, and I think, I think it's 100% emotional.

[00:28:31] **Ben:** And I think the emotion is part of me is afraid if I use an alias, I will forget

[00:28:36] **Tim:** what the alias stands for. You know, I can actually agree with you on that bit. I think part of it is, so for many years there, I was sort of the git evangelist. You know, I spoke at tons of conferences about git. And aliasing things, I was afraid I would start speaking in a language that people could, so I pride myself on, you know, remembering and memorizing pretty much most of the Git commands that are out there and using them.

[00:29:00] **Tim:** So yeah, I don't, I don't have any aliases at all for Git. I do it all by At the base. Command

[00:29:06] **Adam:** lines. Noise. Yeah. Well, I kind of pivoted us into command line. What do you think we should talk about next, Ben? I

[00:29:12] **Ben:** feel so the next two on the list to share your code publicly as much as possible and write. To me, these are both learning in public.

[00:29:21] **Ben:** Yes. And I love the idea of learning in public. And I think it's. There's a freedom that comes with that. The freedom to get feedback from other people, a freedom to be able to make mistakes and not feel bad about it. Like you, you have to, you have to embrace that if you're going to learn in public. I think it just generally prepares you to write code more iteratively and I don't know, there's, there's a power to it.

[00:29:50] **Ben:** I can't maybe articulate very well.

[00:29:53] **Tim:** I think, Ben, you are the poster child for that. I mean, honestly. I mean, you have had, how long, when did you start your blog? How long have you had that blog? 2006, I think. Yeah. I mean, that's, That's a long term relationship right there. It's a hobby. I

[00:30:08] **Adam:** would say it's more than that, dude.

[00:30:09] **Adam:** I'll tell

[00:30:10] **Ben:** you. So one thing that I do is, uh, in Chrome, I'm sure you can do this in other browsers. You can go and you can set up your own search engines for the, for the unified bar or whatever they call the search bar. Yep. Where you can type in a prefix and then it'll kick into a search engine and then pipe whatever you're typing into another search engine.

[00:30:29] **Ben:** So I will actually go and use the prefix Ben To point to my sites that does, you know, site colon benandale. com. So I, I, I search my own site all the time because I'm like, Oh, I know I wrote about this, you know, some years ago. I can't remember what it is. Let me do, you know, uh, Ben, uh, scroll window to top.

[00:30:47] **Ben:** And, you know, there's the articles that I wrote about scrolling to the top of JavaScript across different browsers, something like that. And, uh, like I have one for MDN, actually, I think MDN might come out of the box installed in Chrome. I can't remember. So, you know, you can do like. MDN, Node, AppendChild, and it'll take you to the proper Mozilla developer network page.

[00:31:07] **Ben:** So learning in public and writing, it changes the way you think about learning and it also helps you build up this repository, uh, philosophically speaking. Yeah. Of, of code and, and learnings that you can then refer back to because there's only so much you can hold in your brain at one time. Oh yeah. It's, it's like an index.

[00:31:28] **Ben:** Like, I, I remember that I wrote about something, but I don't necessarily remember what it was, but I just knowing the fact that I did write something now allows me to go look it up. And, and sort of pull that into my

[00:31:38] **Adam:** work in memory. Oh, yeah. We've all had that experience of like you go to search something on Google and you land on like a Stack Overflow question that you answered or that you asked or your own blog post or something.

[00:31:49] **Adam:** Yeah. Yeah. I'm so, I

[00:31:52] **Tim:** mean, I'll admit I do envy you Ben that you do that because I, for a while there, I tried really hard. I had a blog of my own, I worked really hard on it and it just, it just went by the wayside. But it was when I had it and it was running, it was super helpful for the exact same reasons you said.

[00:32:06] **Tim:** You could say people would come to me at work and say, Hey, I got this problem. Like, I'll just send them a link. Here's my blog post on it. Right. Or sometimes I would have the problem and I would Google it. And like you said, that would be the top hit on. So yeah, I need to get back into it. Yeah. Learning in public, doing open source.

[00:32:24] **Tim:** Right. And if you can't blog, maybe some people... Just have a fear of putting it out there. Yeah. Please journal, keep a journal of, of, of what you're doing. Yeah, you can have a private blog. I like the fact that Ben basically combined two points into one that Learned in Public actually does cover both those.

[00:32:39] **Tim:** Yeah.

[00:32:40] **Adam:** Yeah. I mean, I've been nowhere near as prolific of a writer as Ben, but I would say even at the minuscule comparative rate that I write on my blog, I found it incredibly helpful. Um, it, it's helped me. Sharpen my own communication skills, you know, becoming a better writer has made me better at sending emails and having discussions with people, helps me organize my thoughts.

[00:33:03] **Tim:** But you do, you commit, try to commit to a lot of open source projects and create some, I mean.

[00:33:08] **Adam:** Yeah, I have had a few that have, uh, actually been worth maintaining. You know, I, of all, I probably have over a hundred, uh, repositories on my GitHub and I think that maybe like. Three or four of them get updated on any given year and, you know, one or two get regular updates.

[00:33:27] **Adam:** You know, of course I have private repositories for work, but, um, yeah,

[00:33:30] **Tim:** but I mean, e even if you're not updating 'em, and like some of them, I mean, they keep on giving, right. I, I know you're, your taffy.io is you, you don't update that often, but Yeah,

[00:33:40] **Adam:** like it, it's pretty stable. That's one of the ones that I would say gets updated a couple of times a year, you know, little things.

[00:33:46] **Adam:** And then, you know, like right now, this project I just started last night, I'm obviously putting a lot of commits into that one. Open sourcing code, I think, is a very interesting thing to somebody who's never done it before. It takes a certain amount of vulnerability, I guess. Yeah, yeah. It's not just letting your co workers look at your code for a code review.

[00:34:08] **Adam:** This is like, it's almost like a, uh, you're declaring to the world, this is something I am proud of. Which may not necessarily be true, but what is it? It's Cunningham's law, too. Like, thank you, Tim. You're welcome. Asking a question is not necessarily going to get you the answer, but if you post the wrong answer and kind of pose it as if it were the right answer.

[00:34:30] **Adam:** You're more likely to get somebody to give you some feedback. And so just open sourcing something and saying like, Here, I've been playing with this and you know, whatever. It's surprising how often that you'll get, you know, people file issues. Like they tried it and they had an issue with it or something.

[00:34:46] **Adam:** Or suggest different ways

[00:34:48] **Tim:** to do it.

[00:34:48] **Adam:** That you didn't even think of. Yeah.

[00:34:51] **Ben:** I'll tell you one thing that I'm fascinated by lately is, is I've heard more people talk about open source projects that are, uh, they'll accept issues, but they won't accept pull requests.

[00:35:02] **Adam:** I don't, that baffles me. I'm,

[00:35:05] **Ben:** I, I think there's a lot of stress involved with the idea around having to accept other people's code into your project.

[00:35:14] **Ben:** I think a lot of people feel more comfortable as like a, Benevolent dictator for life, who will also accept feedback, not,

[00:35:24] **Adam:** like, not code. So, I, I totally understand the mindset. I don't agree with it. Something that kind of opened my mind a lot to the way that I have handled my open source projects in more recent years is when I found out, or when I heard about the way that the Node.

[00:35:41] **Adam:** js project does theirs. If you If you submit a pull request for any non trivial change to the code base of Node. js, they give you commit access. And the idea being like, it's Git, right? If you do something malicious or dumb, we can just roll it back. And, and by doing that, by giving you that access and sort of like opening you, opening their arms and welcoming you to the community and be like, come on, come join us.

[00:36:06] **Adam:** This is, you know, welcome to the club. Um, it kind of, encourages people more to feel ownership and to feel like they have a stake in what's going on here and to motivate them. And I like that a lot. Like, that's why when, I think it was Dan Switzer asked me about my, that one open source project I mentioned a couple of weeks ago that I passed off to him.

[00:36:26] **Adam:** He asked me, he's like, for some change or something. And I was like, you know what? You know, I haven't touched this in years. Do you want it? You can have it. It's all yours. He didn't even, I barely gave him time to say yes. I was like, okay, I already sent it. Your

[00:36:39] **Ben:** baby now. I mean, I totally understand. I think, uh, I think there are a lot of projects.

[00:36:45] **Ben:** There's a tremendous number of projects that have a value add from a lot of people contributing to them. No question. But I do think there are some people and I might count myself under that. I don't do a lot of open source, to be honest, who I love constraints. And, and constraints to me feel a little bit like freedoms.

[00:37:05] **Ben:** And if I can draw a hard boundary around the ownership of code. It's almost like the way you all love things like prettier and various lintings. It's like those allow you to, you, they, they allow you to not have to have that tough conversation. And I think if you can draw a boundary around the code and say, I'm the only person who will ever write to this code.

[00:37:29] **Ben:** It's like, now I don't have to have the conversation with someone about like, oh, well, you submitted a PR. I'm sorry. I'm like, I'm never going to accept your PR. Uh, like, like there's just a read me, like, go look at the read me. I don't accept PRs. If you have feedback, I'm happy to hear your feedback, but I may never use it.

[00:37:44] **Ben:** And I just feel like it's one of those, like, it's not a difficult conversation anymore. It's almost like I can't help it. Like I can't allow your code into this repository. Look, there's a read me. It says, I don't accept code pools. And I think it's just a, it's a personality type.

[00:37:57] **Adam:** Yeah, it reminds me of having to let somebody else take over a part of my project that I wrote.

[00:38:05] **Adam:** Like I, you know, thousands of lines of code that are all mine, right? And then I'm busy doing something else. And so somebody else has to take it over and like add new features and refactor this and do that. And it makes me

[00:38:16] **Ben:** uncomfortable just to

[00:38:17] **Adam:** hear you say it hurts, right? But the more you do it, the more you get comfortable with it and the more you kind of realize, okay, like I wouldn't have done it that way, but it's fine.

[00:38:26] **Adam:** Um, it's. Fine. It's fine. There was good reason

[00:38:32] **Tim:** at the time. Time's not now, but there was good reason at the time. Yeah.

[00:38:37] **Adam:** All right, let's move on. We're kind of getting stuck here. So, uh, again, kind of going back to, uh, the command line and touch typing, like learn the keyboard shortcuts, I think is a, a million tiny moments saved is it, you know, it adds up and Just makes you, you know, let's just say it buys you an extra 10 minutes every day, you know?

[00:38:55] **Ben:** Yo, command, well, on the Mac, it's command tab, I think. I don't know, the one that like allows you to toggle between windows. I get confused because I'm on a Windows keyboard on a Mac.

[00:39:06] **Adam:** It's command tab on Mac, it's alt tab on Windows.

[00:39:09] **Ben:** So there's command tab to go from application to application and then there's command tilde to go between windows within an application.

[00:39:16] **Adam:** And then it's command alt left and right to go between tabs in the same application? Yeah, I think so.

[00:39:22] **Ben:** Although, see, like a lot of these things, I do them with my fingers and I don't necessarily remember what they are so I have to look

[00:39:27] **Tim:** when you say that. Muscle memory. Yeah, same for the, like I have multiple monitors.

[00:39:32] **Tim:** I think most people do. So, you know, on windows using, you know, Alt Shift and the arrow keys, you can grab a window and just shift it all around. Nothing worse than having to stop, grab your mouse, grab a window, try to slide it over somewhere, just being able to within a second. Pop that window to another screen to get it out of your way so you can look at something else is super effective.

[00:39:52] **Adam:** Yeah, that's not built into macOS, but there are apps you can get to do that. And I

[00:39:56] **Ben:** think even within your IDE, your text editor, I use constantly like bubbling a line of text up and down or copying duplicates of a particular text token

[00:40:06] **Adam:** or shifting boxes. I have one that says delete the current line. It's for me, it's Alt D.

[00:40:13] **Ben:** Yeah, for me, is it? I think it might be command L and sublime. I think it's select the line. I think command D, I think you're right. It's maybe the delete.

[00:40:20] **Tim:** Yeah. I mean, so we don't have to go through all the keyboard shortcuts, but I mean,

[00:40:24] **Adam:** if you

[00:40:25] **Tim:** want to be, you know, take the time, read the documentation on whatever OS you're on or whatever tool you're using and figure out how to do things from the keyboard, because that's just going to make things faster rather than just dragging stuff around with a mouse.

[00:40:40] **Tim:** Mouse is great, but. Honestly, you There's it's muscle memory when you're using the keyboard and you don't even have to, once you learn it, you never have to think about it again. There's nothing

[00:40:55] **Ben:** more painful than watching someone else use the edit menu for copy and paste.

[00:41:04] **Adam:** I'm not sure if that is better or worse than watching them right click on the tag, like highlight it with the mouse and then right click.

[00:41:15] **Adam:** What if they double click the right button? Yeah. So along the same lines of like productivity things, you know, I've, I've mentioned many times over the last few weeks, like using GitHub actions to automate running tests and stuff. Like for me, I'm the type of person I will automate just about anything. If, if, if it can be automated, I want it to be automated because then it's something I can just like do one quick keyboard command or if it can happen automatically without me doing any interaction.

[00:41:46] **Adam:** Even better. And I figured like the more of those I add up over time, like there's that XKCD comic. It's like, is it worth the time? And it's a chart. Are you guys familiar with this one? I think so. Um, it's a chart and it's like how much time does automation save you versus, uh, how long does it take to do the automation?

[00:42:05] **Adam:** And it kind of fills in and shows you like whether or not it's worth it based on how much time it saves you over, you know, and how often it happens, right? So it takes you five minutes to automate it and it happens a hundred times. a year or whatever, then this is when you recover the automation time. I don't even worry about that.

[00:42:23] **Tim:** I'm the guy who has automated rebuilding my laptop from destruction. I have a script sitting in a gist on GitHub that I can run and rebuild my laptop and put it exactly where I want it to be. Honestly, probably maybe every four or five years I'm gonna get a new laptop, but I'm glad to have it. Yeah.

[00:42:44] **Ben:** I'm terrible about automating stuff.

[00:42:45] **Ben:** I, I mean, I'm, I finally hooked up Time Machine to do automated backups of my computer and that was only like four months ago. And it's like the, and that's like the only thing I have automated. I don't know. I mean, you know, at work we have, We have CodeShip. I can never remember which thing is continuous integration and which is continuous delivery.

[00:43:05] **Ben:** We have people who set up that stuff. So I don't even know how that works, but just even like in my local environment, environment, I'm terrible. I'm brute force most of the time. I wish I wasn't necessarily. I just, it's, it's, it's for whatever reason, it's not the, I don't take time to do it.

[00:43:25] **Tim:** So, I mean, automate, I think that's pretty obvious.

[00:43:28] **Tim:** I think probably the next archetype. Or a habit of an effect developer would be, you know, getting involved in the community. Um, so whatever language it is, whatever tools it is you're using, making connections with people in community, going to conferences, speaking at conferences, you know, starting projects with people in that, that you tend to see the people who really excel, they're the ones that are doing that.

[00:43:53] **Tim:** Now, true, maybe you see them because they're out there, but you know, obviously putting themselves out there. was a leap of faith that helped them get to a level, um, that helped them accelerate. I know that was for me personally. There was many, many years where I was just coding and coding and back in 2010, I'm like, you know, I probably want to, I want to go to a conference.

[00:44:15] **Tim:** I'm tired of talking to the same people here in the cubicles next to me who give me the same answers all the time. There's got to be people who are doing things a bit differently. And then I went to my first conference and I was like, Oh my God. Yeah. Wow, these people are, are, they're in the trenches that I'm in and they're solving the problems I'm facing right now and they're doing it so much smarter than I would have done it or the way other people would have done it.

[00:44:39] **Tim:** They're awesome. To me, they were like gods. And then a few years later, like now I'm at conferences giving talks and I'm, I, you know, I'd realized they weren't gods and I'm not one now, but. They're just people who are at different points in their journey. So definitely get involved and get out there and, and, and, you know, get involved with the community of the language or.

[00:45:03] **Adam:** Yeah, for real, as much time as you can afford to. Uh, to spend on attending community events, even if they're virtual events, there's plenty of virtual meetups for just about every language. I would say they're, they're pretty much invaluable. Um, you know, not everything is going to be gold, but even if the topic of the, the meetup that you're going to isn't all of that.

[00:45:23] **Adam:** interesting to you. Hopefully, you know, you'll meet somebody interesting there, you know, make a friend, uh, be inspired by something you see. Like, I remember, um, some of the first, some of the earliest meetups that I went to were like, uh, user group meetings. Seeing people do crazy stuff with keyboard shortcuts, like line bubbling, right?

[00:45:43] **Adam:** That's where I kind of like got hooked on all the, the crazy keyboard shortcuts was seeing other people do it. And there was actually, uh, a guy, he... had this tool that he turned on while he was doing his presentation and it showed all of his keystrokes on screen. So like you saw him do something, you know, move a line up or down or whatever.

[00:45:59] **Adam:** And you could see what keys he was using to do that. And you know, some of them were custom, but most of them were like built in. So you could see, Oh, he used these three modifier keys in this letter to, to do that. That's cool. That was awesome.

[00:46:11] **Ben:** There's also a sense of connection with the community. And, and, and I, you know, given this last year with the pandemic and people not seeing each other, I, when I reflect on.

[00:46:23] **Ben:** In past episodes, I've talked about how I've been feeling very disconnected from the community and from learning. And, and, but what I have is this sort of momentum of years past that I, that I lean on and, and a lot of how I feel connected to the community is from events from years ago. And, and I think it sticks with you.

[00:46:42] **Ben:** And, and, you know, it's like when you go on a vacation and you remember that vacation for years. I'd like, that's how I think you think about conferences and meetups. Like I remember. Presentations that I saw on people that I talked to in dinners that I had, and, and it sticks, just sticks with you and makes you feel like you're part of something, which is really nice, for real.

[00:47:01] **Tim:** And it also kind of feels like a safety net, right? So you, you, you go to a conference and you find maybe a, a speaker or just a person you're talking to at the, at dinner or at the bar or, you know, sitting, you know, sitting next to it in the hallway, in the hallway. And you find out they're really passionate about X, right?

[00:47:19] **Tim:** And so you kind of tuck that away in your head and then you go back to work and about a year later, you have a problem with X. You're like, Oh, I know what, I need to talk to Ben. Ben knows about X, right? And so you just send him a message or a tweet or whatever. And, and then Ben's like, Oh yeah, so and so and so and so and so and so.

[00:47:38] **Tim:** Okay, cool.

[00:47:39] **Adam:** He sends you the link to his blog

[00:47:40] **Tim:** post. Right,

[00:47:41] **Adam:** exactly. And

[00:47:42] **Tim:** you just now I have, you know, I, I know I don't know everything. But I know that in the community, most everything that can be done probably has been done. And if it hasn't, then there's people in there who can fix it. And so you just kind of feel a level of security that when it gets bad, I know I've got people behind me that care about the same things I do that can back me up and help me get out of this hole.

[00:48:09] **Tim:** That's a good feeling.

[00:48:12] **Adam:** All right. So the next one in here is BTshaped and Tim wrote next to it. WTF is this? So it's actually something we've discussed on the podcast in the past. A T shaped developer is somebody that is a sort of a jack of many trades and a master of one. Right? So you, you have a broad experience that's shallow and you go real deep on some focused area.

[00:48:38] **Adam:** That makes sense. Like a capital T. Mm hmm. And I think that that In my opinion, is not, not necessary to be an effective developer, but it definitely has a lot of advantages, you know, being specialized like that can be, can come in really handy if you happen to get, if the thing that you specialize in, it becomes in high demand, then, then that can be really good for your career.

[00:49:03] **Adam:** Yeah, I'm tossing that one around my head.

[00:49:05] **Tim:** I've got to, cause I didn't know what that meant, T shaped. I

[00:49:08] **Ben:** think the nice thing about being T shaped is that it opens up a lot of doors for you in terms of your own development. Yeah. If you're, if you're very narrowly focused in a particular area, then you can crush it in that area, but then the second you have to coordinate some other part of the development process, now you really have to lean on other people.

[00:49:30] **Ben:** Whereas I find when I'm, I think of myself as a T shaped developer and, and that allows me to take a lot more proof of concept work farther because I can do a little bit of the database and I can do a little bit of the backend. I can do a little bit of the front end and I can deploy stuff. And I kind of know about, uh, you know, operational readiness and observability.

[00:49:49] **Ben:** Like I'm not really great at any of those things, but like, I know enough to take something that was just an idea in my head. And

[00:49:57] **Tim:** deploy

[00:49:58] **Adam:** it. Right. I'm not a master of CSS, but I can, I can make something that doesn't look like vomit from

[00:50:04] **Ben:** 1998. Right. And so I think you, there are, you see, you can see more possibilities in front of you because you know that there's a path

[00:50:13] **Adam:** forward.

[00:50:13] **Adam:** Right. Versus the guy who like, Oh, he's like, I don't do front end. All I do is server side. Right. Uh, I don't do CSS. I don't do JavaScript. I'm just a, I'm a SQL guy.

[00:50:24] **Ben:** Yeah. So I just think it affords you

[00:50:26] **Adam:** more opportunity.

[00:50:28] **Tim:** Absolutely. And I think being T shaped, even if you can't do it all, I think it's important to know at least some of it so that you can ask good questions and communicate well with those who are going to do it.

[00:50:41] **Tim:** So if you're a big team, you might not be the person who's going to be doing the Doing some of the database transformations, but if you understand it and you understand what you, you know, what you are an expert in, you can say, look, I know you're the expert in this, but here's some things you might, you know, here's some points that you might want to be aware of that this, this, and this could be stumbling blocks.

[00:51:04] **Tim:** And, you know, you know, I, I expect this to come out of, out of this from that. So, yeah, I.

[00:51:11] **Adam:** Like you said, it helps you know enough to ask intelligent questions.

[00:51:16] **Ben:** And Tim said on a previous episode that having a broad spectrum of information sort of lets you know when someone's BSing you. Exactly. You know, when you're like, hey, can you add a log statement here?

[00:51:29] **Ben:** And they're like, oh, that'll take a couple of weeks. You're like, uh, I know how to

[00:51:32] **Adam:** add a log statement. Trust me. I've had some infrastructure

[00:51:36] **Tim:** guys try to. Tell me that, Oh, well, I can't do that because the PGP won't die. I'm like, uh, it doesn't really work that way.

[00:51:44] **Adam:** Doesn't the PGP, you know,

[00:51:47] **Tim:** always reflect it's like, Oh, okay.

[00:51:49] **Tim:** Well, uh, what I meant was, okay, thank

[00:51:52] **Adam:** you. All right. Who wants to pick the next one? I'll go

[00:51:54] **Ben:** disconnect sometimes. Step away from the keyboard. I think it's important to disconnect from the computer. But only in so much as it is actually important to you. I don't think there's this, there's this standard.

[00:52:11] **Ben:** People talk about work life balance, and I think it's this sort of imaginary goal that they feel like they need to fit into in order to achieve proper happiness and productivity. But There is no one thing that is work life balance. If, if you work at a computer all day and then your hobby is also working at a computer, like that's totally fine.

[00:52:34] **Ben:** If your hobby is, you know, gaming or your hobby is woodwork or your hobby is hiking, like. None of those are better than the other ones. You, you just have to find the thing that allows your brain and hopefully your body to think and move in a different way. And I think that creates balance. Yeah.

[00:52:50] **Adam:** I think if it helps you de stress to put aside the work and work on your open source project, then by all means do that.

[00:52:57] **Adam:** Like if it, and if it gives you energy to do that, then that's what you should be doing. Yeah, totally.

[00:53:03] **Tim:** I think, you know, working from home during this pandemic, you know, I know several of you have worked from home. before, but this is really the first experience for me. Disconnecting. I've, I've found that I've worked more hours because I'm at home.

[00:53:20] **Tim:** Yeah. But I found that during that time, sometimes I just realize I need to just stop. I'm like spinning my wheels. I'm like, all right, I'm going to go outside. And my hobby, my physical hobby, what I use is gardening. So I go outside, I have a vegetable garden. I've got very large vegetable garden, herbs and all sorts of weird fruits and vegetables.

[00:53:40] **Tim:** And so sometimes I would just be like, you know what? I need 15 minutes right now. It's a, you know, some people smoke. I go garden. I will go outside for 15 minutes and I will go pull some weeds. For 15, it's brainless, it's mindless, but I find that doing that kind of clears, resets my brain, allows me actually to problem solve better because honestly, my subconscious is, is working on the issue while I'm pulling weeds.

[00:54:05] **Tim:** I'm not really actually thinking about anything and I'll find that I'll come back in and I'll be like, all right, I'm much more productive after 15 minute, go pick some weeds, you know, throw them out, get rid of it, put some mulch down, come back inside. Uh, yeah, so I totally agree with that, just, whatever, and that's my thing, right?

[00:54:24] **Tim:** Whatever you find to stress relieve at some kind of a mile a nit ing. Jumping out of airplanes. Jumping out of airplanes might take a little longer than 15 minutes, but yeah, whatever it is. Yeah, disconnect, step away from the keyboard, clear your mind, let your subconscious work on it. Totes. But kind of connected, but different is, is avoiding distractions.

[00:54:46] **Tim:** So sometimes I do this, I will schedule and because I'm, I'm not truly a full time developer. I'm a developer slash manager slash director, uh, executive, right? So I'm on the executive team. So I have, Uh, competing responsibilities. What I love to do is code. I'll be honest. I hate all that other stuff. I do that because I can and I make more money doing that, but it's not what I love to do.

[00:55:15] **Tim:** And that's why I tell them up front, like, you know, if you start trying to push me where I'm a hundred percent management, I am not going to take that job. That's not what I'm into. I do, but I do like kind of the split. When you're in that role of people managing and things like that, you get a lot of distractions.

[00:55:35] **Tim:** So I will set aside on my calendar periods of four hour blocks where all I'm going to do is code. I will turn off everything. I won't look at email. I turn off Slack. I turn off Discord. Sorry guys. That's, that's you guys. Uh, I turn off everything and I don't do anything but code for those four hours. And sometimes, honestly, I don't get a lot of code done because I'm thinking about it too much, but knowing that I have that four hours of time where I'm not taking meetings, I'm not answering emails, I'm not looking at my team's chat, um, is extremely helpful.

[00:56:12] **Tim:** So being able to have focused time, I think is, is definitely Uh, something that people that want to be effective should do and should plan for and should schedule. Yeah.

[00:56:25] **Adam:** This, this whole disconnect and step away from the keyboard idea was one that I added to the list. And another part of it that I had in mind when I wrote that was like, when I walk away from my desk at the end of the day, I have developed this habit of being difficult to reach.

[00:56:40] **Adam:** Not impossible, but difficult. Like I don't check our work chat. I don't check my work email. If my teammates really need to get in touch with me, they can call me or they can put in, uh, an alert in our OpsGenie. And even if I'm not the one that's on call, it'll, eventually it'll escalate to me. And so like, I'm not unreachable, but I make it a point to be difficult to reach so that, uh, I can focus my thoughts and my time on my family or on a hobby or something.

[00:57:09] **Adam:** And I, I think that. The reason that I do that is because I have a strongly held belief that nothing is worse for your productivity than being burned out from constantly working and constantly, like if you, even if you're only sitting on the couch answering emails while you're watching TV at night with your spouse, That is working, right?

[00:57:30] **Adam:** Your, your brain is at least 40% into that. And so you, you never stop working at that point. Except when you're sleeping. That is also not family time. Right. Exactly. You're, you're doing a poor job of working and you're doing a poor job of being with your family. So just like pick a lane really.

[00:57:47] **Tim:** Exactly.

[00:57:48] **Tim:** Pick a lane for sure.

[00:57:49] **Adam:** But, uh, yeah. So like, I feel like it, it, it can be tough, especially if you've been like a workaholic for a long time. And I was. to, to step away and make it difficult to get in touch with you. But ultimately I feel like it makes me way more productive. Like, okay, so now I'm, I'm giving up those, let's call it four or five hours where I, where I was doing 30 to 40% effort work.

[00:58:16] **Adam:** But I feel like I'm more than double productive what I would be if I was still available for email and chat and stuff in the evenings.

[00:58:24] **Ben:** Also I think when you constrain the amount of time you're allowed to work, it forces you to be more focused because you know you don't have that wiggle room. I think, and this is going to sound crazy, but a big part of how I stay focused is I just have too much stuff to do.

[00:58:43] **Ben:** And like, I know that every moment where I step away from the thing that I'm supposed to be doing, it's just delaying something else. Yeah. So like, I don't want to, I don't know, like it's part of it too, is like I have, I have my work work and then I have my self directed work, which is still work, but it's like the stuff I want to do as opposed to the stuff I have to do.

[00:59:04] **Ben:** So because I have these almost two competing priorities in my head that are both work, I want to cruise through the stuff that I have to do so that I can get to the stuff that I want to do. And, and because I'm like overloaded, it forces me to actually just get through it as fast as possible. Yep. Like not cut corners, but like

[00:59:23] **Adam:** stay focused.

[00:59:24] **Adam:** Oh yeah, for sure. I haven't really spent much time on Facebook in years, right? Facebook, Reddit, none of it. Just like, I'm, So busy with work. Like you said, we've got just so much stuff going on and I have, I, I try to be really disciplined about doing the stuff that I have to do and it's important to do for work before I do things that are things I want to do.

[00:59:47] **Adam:** I think that that drives me to stay focused so that I have some, I have some me time at the end of the day or at the end of the week.

[00:59:53] **Ben:** Also, pro tip that I do, which, uh, I don't know, this probably makes me sound like a terrible person, but my wife is sort of the liaison between me and everyone outside of our family.

[01:00:06] **Ben:** So like she does all the, she sets up all vacation stuff and like she deals even with my family and like setting up plans. So she'll be like, Hey, did you see the text from your mom earlier? I'm like, no, like you have to tell me that that happened.

[01:00:23] **Adam:** Oh, Ben. Well, all right, let's move on to the next one. We only have a few more left here.

[01:00:29] **Tim:** Yeah. So communication, I don't know if this is a stereotype and if I'm going to get raked over the coals for saying this, but I think the typical idea of a programmer is somewhat of a, a very analytical. somewhat introverted person, uh, who doesn't

[01:00:49] **Adam:** communicate.

[01:00:49] **Adam:** Yeah. Yeah. Good with computers, not with people. Exactly.

[01:00:53] **Tim:** And now, I mean, I'll say that is not me. I know I'm, I mean, I like to communicate with people. I'm, I'm one of those, I feel I personally, I'm one of those ambiverts. I, I, I enjoy talking to people, but it does take something out of, um, communication regardless of what your personality style is.

[01:01:13] **Tim:** If you want to be effective, you have to learn to communicate. And communication is extremely important because you might have all the answers in the world, but if you can't explain to another person why those answers matter, they don't care and they won't be on board with you. And, and they could be in a position where to make the fact that you can't implement your best ideas in the world.

[01:01:37] **Tim:** So learning how to explain your viewpoint and why what you say matters. And your heart matters. Is extremely important. I mean, Uncle Bob said it right. Like, we have to fight for the code. We have to fight for the code to keep it clean. And if you can't explain why, other than just, you know, throwing invectives and ad hominem attacks, that's not going to win you into battles.

[01:02:03] **Tim:** You have to be explained, why do we need to do it this way? Why should it take this long? And why is it that important? And if you can't do that, it's going to be extremely hard.

[01:02:13] **Ben:** You know, and flip side to that, become very comfortable saying you don't understand something. That opens up like a whole new world of communication.

[01:02:23] **Ben:** When you feel comfortable getting into a meeting and saying, I don't understand why it works this way, or I don't understand how that works, or can we please walk through this? I just, I just don't get it. That opens up everything.

[01:02:35] **Adam:** This also makes me think, I occasionally get into what I like to call healthy arguments at work.

[01:02:40] **Adam:** Especially with. our founder. Um, he and I have known each other for like 10 plus years now and we have a pretty good relationship, like a lot of trust and respect there. And so even if things were to get heated between us, I think at the end of the day, we know it's all for the right reasons and we're willing to let that go.

[01:02:58] **Adam:** But I guess what I mean by like healthy arguments, is that what I called it? The idea is to like argue for like, I mean, argue in the sense of debate, right? So like argue for what you believe in and have a reason for it, but do it entirely without ego, right? Like this is, I'm arguing because I think that this is what is best for the product and I'm willing to be convinced otherwise, but this is what I believe and this is why I believe it.

[01:03:27] **Adam:** And, and if you disagree, then please come over here and convince me. Yo,

[01:03:30] **Ben:** throwback to being T shaped and then this is going to sound terrible, but A nice benefit of being T shaped is if you're in one of these arguments with someone and they're like, I don't think we should do it that way. You can be like, okay, but I'm going to do it that way.

[01:03:44] **Ben:** And I have like all the skills ready to go. And, and, and, and I'm not, not to say that you're going to just like bulldoze over someone who has an opposing opinion, but being T shaped allows you to. Show them what you were thinking instead of just being able to talk it through, because sometimes people just don't understand what you're saying until they see it.

[01:04:06] **Ben:** And also sometimes you don't understand what you're saying until you see it and then maybe you realize it was a good idea or you're like, Oh, no, okay, that that was a bad idea. I didn't think about these edge cases until I went to

[01:04:16] **Adam:** write. Yeah, makes me think of, um, you know, so much of our communication, especially now during the pandemic, everybody's remote.

[01:04:22] **Adam:** You know, we default to text based communication, right? Email for some people, but probably a lot of companies are moving to Slack and Discord and whatever else. Oh, Microsoft memes. Tim. Yeah. Um, but it's easy to get, I think, like emotional because you feel like you're not being understood. And it's the, I like to think of it as it's not as high fidelity a conversation in team chat because you can't type as fast as you can speak and as you can think and you can, you can start to feel like you're getting outrun and that's why you're, you're losing there.

[01:04:53] **Adam:** And when I start to feel that way, I'm like, let's jump on a video chat here so that we can have that conversation. I can. Hear the tone of your voice and see your face. And that's going to help diffuse the situation. And we can just talk about what's best for the product.

[01:05:06] **Ben:** I wish I was better about that.

[01:05:08] **Ben:** There was a time in my life where I was good at that and I have regressed and it's been years since I've regressed. And I, and I would like to be much better at that.

[01:05:16] **Tim:** Yeah, that's, I mean, that is crucial what you just said, Adam. It's like so many times in the past few months where I start like sending an email or doing a chat with someone and it's going back and forth and it's like, you know what?

[01:05:31] **Tim:** Can we just, let's just, you got time right now? Can I call you right now and, you know, hit a Teams chat or send an invite, whatever, for the next, you know, the next 15 minutes and what you can... Discuss in 10 minutes over a call or, you know, a video chat is so much more productive than 20 iterative emails that go back and forth and context get lost.

[01:05:54] **Adam:** And you just get more and more annoyed that they know that the emails keep piling up. Yep. Right.

[01:05:58] **Tim:** And yeah, and you're getting, you're getting mad at them because they're not understanding. You're like, this person's an idiot. I told them like five chains back ago that this. If you had a conversation, it would have been clear.

[01:06:10] **Tim:** So yeah, high fidelity conversations is extremely important. And when we go back to the office, don't just, you know, send them a chat or, you know, walk over there, talk to them, right?

[01:06:19] **Adam:** Yeah. Knowing when to jump into those hi fi conversations is important.

[01:06:23] **Tim:** Yeah. Yeah,

[01:06:25] **Ben:** sure. And I, I can only speak for myself here, but I know that when I am writing texts with someone, my mindset is definitely in the vein of how can I process this fast and get it done?

[01:06:38] **Ben:** Like someone sends me a message, like how fast can I type back and get back to the thing that I was doing before, which I think is a different gesture emotionally than let's get on a call where I'm actually purposefully committing time and not just trying to figure out how fast I can process this, uh, distraction, if you will.

[01:06:56] **Tim:** And I think another misconception about communication is about speaking well. Communication, you know, God gave us two ears and one mouth so we should listen twice as much as we talk. Really learning how to listen is, is a skill that people that are effective have. They, they don't hear what's just said.

[01:07:17] **Tim:** What was that? But also what's not said, what was not said. I took some sales training classes years back and they, one of the, uh, is Hyman Miller, the sales conceptual, uh, and strategic selling concepts. And one was, they talked about the golden pause where you, you ask a person a question and they give them an answer and your immediate response is to jump on that and talk back.

[01:07:41] **Tim:** But the golden pause is when they, when someone gives you an answer, don't respond quickly. Wait, because nine times out of 10, what happens is. They will give you more information. They will, they will say something else beyond because their brain gave you the knee jerk response and then their analytical mind started processing and realized there was actually more information and they give you that more and usually that more information that the thing that after your awkward pause gave you was actually more valuable and more insightful than what you would have got had you just jumped in to feel the silence.

[01:08:18] **Tim:** Uh, you never would have got that because, you know, they've switched to receiving mode rather than sending mode. So listen well and when someone gives you an answer, pause and wait to see if there's anything more because those last little drips out of the faucet are

[01:08:35] **Adam:** usually the best. We only have a couple left here.

[01:08:38] **Adam:** Let's see if we can get through those real quick because we've been going for a little while here. Um, I feel attacked, Tim. Yeah. Okay. Okay. So I, I, I

[01:08:47] **Tim:** mentioned that we should talk about always have an agenda for meetings. Now, when I say agenda, I don't mean, you know, some sort of written down, established, although that is best.

[01:08:56] **Tim:** If you can, in a meeting, invite, put in there, here's the things I want to address. That is extremely helpful. I, I, I like to have it when people invite me to a meeting. A lot of times if, if, particularly if it's someone above me in the food chain, says, Hey, Tim, I need to meet with you. My, and they don't tell me what it's about.

[01:09:15] **Tim:** My thing is, can I see the agenda? Great. And so kind of have that same empathy toward other people of having at least a broad agenda about what's going to be discussed. But more along the lines is what is your agenda to get out of the meeting, right? What is it you need? Yeah. If you're going to take the time to have a meeting, and sometimes these meetings, it's just the nature of things.

[01:09:42] **Tim:** You maybe want to have a one on one, one person, but then they're like, Oh, I need to bring so and so in, so and so in. And when you start getting over, you know, two people in one meeting, it becomes a thing. Yeah. Right? It just becomes a thing. So you need to know what you want to get out of that meeting and have an agenda, at least on your own.

[01:10:02] **Tim:** But if you can publish that and put that out among all parties, that really speeds things up. Now, tell me, why do you feel attacked

[01:10:10] **Adam:** about that? Because the agendas for our podcasts are always like, intro, big blank area, outro.

[01:10:17] **Tim:** I don't consider this a, this is not a meeting. This is a conversation among friends, right?

[01:10:20] **Tim:** Sure. This is...

[01:10:22] **Adam:** So,

[01:10:22] **Ben:** one thing that I heard recently discussed, I think this was on Seth Godin's... Podcast Akimbo, he was saying that when we used to meet in person all the time, there was so much overhead to getting people together. in a conference room that you felt like you had take up the allotted time. Oh, yeah.

[01:10:40] **Ben:** And he was saying now that meetings are essentially frictionless, you can send someone a Zoom link or a Hangout link or Microsoft Teams link. I assume they have their version. Yeah. That it's so easy to do that, that you shouldn't feel the pressure anymore to take up the half hour or the hour on the calendar.

[01:10:59] **Ben:** If you schedule an hour calendar meeting with someone and you get in and you make a decision in five minutes, Like, end the meeting. Mm. And, and he was saying like, people are so not ready to do that because they're so used to taking the time that like they end up discussing a whole lot of stuff that isn't even necessary just because they feel like they have to be there for the hour they booked or the half hour they

[01:11:20] **Tim:** booked.

[01:11:21] **Tim:** That's, uh, it's funny you bring that because I've had seven meetings today.

[01:11:28] **Tim:** All of them were scheduled, all of them were scheduled for 30 minutes and none of them lasted 30 minutes.

[01:11:34] **Adam:** They were longer or shorter? They were shorter.

[01:11:36] **Tim:** They were all shorter.

[01:11:37] **Adam:** We, we, we got to

[01:11:38] **Tim:** the, and, and, and so actually four of them were planned meetings that were on my calendar prior in the week. The rest of them were ones like, I mean, I've been doing that a lot.

[01:11:50] **Tim:** I was a customer or a vendor. There'll be an issue and I'm like, Hey, you available at three? Can we just hop on and talk? And they're like, yeah, sure. We, and so it's like an impromptu, you know, sometimes it's like within 15 minutes, I'm like, are you going to be on 15 minutes? I'll just send you an invite.

[01:12:08] **Tim:** We'll, we'll chat and we'll chat for 10 minutes and hop off. And it's, you know,

[01:12:13] **Adam:** I'm going to start scheduling meetings for like seven minutes. No, I'm dead serious. I'm like, you know, let's, let's try to make this a thing, right? Like schedule a short meeting and do your best to stick to it. I have two questions.

[01:12:24] **Adam:** Here's my two questions going into it. And we're having a meeting because I know it's not just going to be a quick email on. Two questions, two answers. There's going to be a little back and forth and discussion. Why is it that way? Sort of thing, but like, yeah, let's do it. We're going to get on promptly.

[01:12:37] **Adam:** We're going to have our, our quick questions, answers, discussion. Okay. Thanks. We're done.

[01:12:44] **Tim:** Yeah. I mean, I had a very tricky discussion with a vendor today that we had scheduled one hour and I thought for sure it would take an hour and we were done 37 minutes and we're like, well, I guess we're done. So, And what's nice is it still shows up on my team's calendar as a full, I'm in

[01:13:02] **Adam:** their meetings.

[01:13:02] **Adam:** You can go garden. So that's extra free time. I can go garden

[01:13:05] **Tim:** or work on some code or something.

[01:13:07] **Ben:** Would you rather have four back to back meetings or four meetings that were each spread out by like

[01:13:15] **Adam:** half an hour? It depends on are they related or are they totally unrelated? I would rather

[01:13:21] **Tim:** have them back to back.

[01:13:22] **Tim:** I mean, because if I have like a 30 minute gap, I'm like, what am I going to do in those 30 minutes? Right? It's like, I'm just going to sit there waiting for that next meeting. I'd rather just do back to back to back. And then if I get some extra time because it ends early, that's gravy. But... Yeah, scheduling an extra 30 minutes in between to me is just ridiculous.

[01:13:41] **Tim:** I'd rather have it

[01:13:42] **Adam:** back. I'm totally fine having four seven minute meetings in a row.

[01:13:48] **Adam:** All right, let's round this out. Okay. Yeah. So I think it was Tim you wrote this one, but I want to take a stab at it. So you wrote here, you understand what the business needs. And I think that what you're trying to say here is ultimately what we're doing when we write our code is we are earning money for our business by providing value to our customers.

[01:14:06] **Adam:** And if you're not doing that thing, either directly or indirectly, then it's not worth doing. And sometimes there's like edge cases where it's like, we think that this can, uh, improve productivity or performance or something. And that in a very indirect way increases the bottom line. But at the end of the day, if you're not doing something for the benefit of the business, probably shouldn't be done.

[01:14:29] **Tim:** Right. And I, I wouldn't, I wouldn't narrow it to the point where what the business needs is, is profit, right? Because there are... I know very profitable companies that have really bad software. Um, what the business needs is good software, what the business needs is people with integrity, what the business needs.

[01:14:47] **Tim:** It is to serve their customers. That is true.

[01:14:51] **Adam:** Right. So.

[01:14:52] **Tim:** Very true. So if you don't know what your customers need, you don't know what your business needs.

[01:14:56] **Adam:** And if you look at it the right way, sometimes what the business needs is a healthy culture, right? You need people that don't feel overworked.

[01:15:03] **Tim:** And a lot, you know, a lot of times we write, we don't write software for the company we work for.

[01:15:07] **Tim:** I mean, I write, what I do is I write software for my company. But it's for another company to buy, right? So you really have to understand their business. And so I think probably one of the most formative things I've ever done, uh, earlier in my career was actually go visit those businesses. And I know everyone can't do that as developers, but you know, we do have a program.

[01:15:31] **Tim:** We do try to do that. Even junior people, we try to send them to a location to go see, here's the stuff you're writing every day. Here's how it's actually being used in the field. Here's what people are doing. Here's And when, so when you see, you know, how it's made their life better in some cases, and then there's some cases where something that maybe you worked on that is really causing them extra work and you didn't even realize that, you know, you could probably change this with maybe a little bit of effort and really make their life a lot easier.

[01:16:01] **Tim:** That's very transformative to understand. Like this is, you know, I'm not creating fake fairy tales here. This is real stuff being used by real people that has a real effect on their life. And when you get that, You come back with a different viewpoint of, of how can I make this easier for them. And that's what I mean by understanding what the business needs.

[01:16:22] **Tim:** Okay, I like it. I

[01:16:25] **Adam:** think both of these last two here are yours. The very last one, I think, I think it's a good one that we have last. Uh, but, uh, so what's this other one? So

[01:16:35] **Tim:** using best tools. So I, you know, whatever tools can make your job easier, get them, right? So the best IDE, I mean, I'm not, this is not a plug for them and there's probably better ones out there, but I love MySQL editor.

[01:16:49] **Tim:** I use AquaData SQL editor. It has so many cool tools and functions and editing tool and I couldn't live without it. I've just, I know it so well, like the back of my hand and I'm so much in data all the time. So I couldn't live without that tool and whatever IDE you use, use the best one that works for you and know it well.

[01:17:11] **Tim:** The best chair for coding, my son, it was our anniversary last weekend and my son bought me this cool uh, Purple, you know, they make mattresses, but this is like a seat cushion. So I have a cheap IKEA chair. I don't have like a gaming chair like you do. And they're at them. I'm jealous,

[01:17:27] **Adam:** but this chair is awful.

[01:17:28] **Adam:** It's a breaking apart. It's just a staples. Yeah. It's a staples chair from forever ago. And

[01:17:33] **Tim:** I, I had one of those. Mine has no headrest or anything, but yeah, he gave me this cushion. It's like make so much my life so much better. But yeah. So get the best, get the best tools for your job.

[01:17:42] **Ben:** You know, learning tools, that's something that I always regret not having done more of.

[01:17:48] **Ben:** Every time I learn something new about one of the tools I use, I think to myself, why didn't I learn this five years ago? Why did it take me this long to find some really interesting aspect of this tool that ends up being super helpful?

[01:17:59] **Tim:** Yep. And sometimes it's not even necessarily getting a new tool, it's using the tool better, right?

[01:18:06] **Tim:** So like, I mean, I love to cook. That's, I'm a... Just within the last year, I learned to sharpen knives, right? So I would buy these really cool knives and, Oh, these are awesome. And they would be awesome for like six months. I'm like, Oh, this is crap because I didn't know how to sharpen a knife. So I bought a whetstone and I watched tons of videos and now I have, now I only need two knives.

[01:18:27] **Tim:** I have a cleaver and I have a Japanese long knife. And I will just sharpen that once a week and that I can cut anything. So it's like. Get the best tools, use the best tools, understand how to use your tools, and your life is going to be so much easier.

[01:18:45] **Adam:** All right. Well, let's round it out. Read books. Read books.

[01:18:49] **Adam:** Listen to podcasts. Mostly this one.

[01:18:53] **Tim:** Taking information, right? Yeah. Yeah, mostly. Yeah. I think that's a good one to end on because, you know, we just did the, uh, clean code and that's kind of what got me thinking about these best habits, right? So, you know. Taking information about what you do. Um, and a lot of times it might seem repetitive.

[01:19:12] **Tim:** Like, well, I just read a book. I just read Clean Code, but there's other books that have different perspectives. And even he kind of said, you know, the whole dojo mentality. You become an expert in that dojo. Well, that doesn't necessarily mean you're an expert at fighting. You're just a really good expert in that, that, that teacher's philosophy.

[01:19:31] **Tim:** So, you know, Clean Code is a great book, but. You know, and a lot of stuff that he's going to say is going to overlap with other books, but you're definitely going to be able to take in best practices from others. So don't stop learning.

[01:19:43] **Adam:** Oh, that's a great way to put it too. That's exactly where I was going.

[01:19:45] **Adam:** So my wife is a. mental health therapist. And in her industry, in order to keep your license, you have to do a certain number of continuing education credits every year. We don't have anything like that. And in our industry now, not everybody has to go to school and get like certified as a developer, but there are so many opportunities to continue growing, to continue learning, whether it's new tools or like reading a relatively old book like this.

[01:20:12] **Adam:** You know, and I feel like this clean code came at a perfect time for me in my career. Maybe, you know, perfect window, whatever. Anytime five years ago to the next five years probably would have been great. Just, I've gotten a little complacent in the, that like sweating the small stuff type thing. And this was a great reminder to take pride in the work that I'm putting out.

[01:20:35] **Adam:** And I think we talked about it before, defending it, right? Standing up for what the code needs.

[01:20:41] **Tim:** And I would say don't limit yourself to books that are just strictly about, you know, whatever language it is you learn, whatever, you know, methodology you're doing in development, Agile or Scrum or Chemistry.

[01:20:54] **Tim:** Find things that are, that are related, but kind of adjacent because a lot of the geniuses in the world are people that took aspects of some other discipline of science or art or music and brought that in and infused it with. The thing that they were, they felt more comfortable with. So taking things that are adjacent and merging it kind of becomes this sort of genius of fusion.

[01:21:22] **Tim:** So learning those sort of things, like, you know, that's why I've. Earlier we talked about our goals for the year. I mean, you know, mine is kind of like cryptocurrency and smart contracts and things like that. That doesn't have a whole lot to do with what I do, but it is adjacent. And so I may never use any of that stuff, but it may inform and inspire some things that I'm doing now to help me become more creative in what I'm doing that I wouldn't have done had I just strictly stayed blinders onto the thing I'm focused on.

[01:21:54] **Ben:** Yeah, totally. There's so much more cross pollination than I think people realize.

[01:21:59] **Adam:** Alright, if you like what we're doing here, you might want to consider supporting us on Patreon. We're working on building up enough monthly income to pay an editor, which is a day that I will probably put on my calendar and celebrate every year when it finally arrives.

[01:22:11] **Adam:** We've got a bunch of people already contributing toward that goal. So from me personally, thank you. If you can't support us financially, but you want to help out, the best thing you can do is to help spread the word about the podcast. The more people that there are listening, then the more people that could potentially kick in to help us out with a few bucks every month.

[01:22:29] **Adam:** Um, so if you think we've earned it, you can find us at patreon.com/workingcodeod. Every patron gets an invite to our discord server, which is where we hang out and where we do fun stuff like have our game night. Recently, I'm wearing the t shirt patrons from the, from the Jackbox games. We have other perks available like early access to new episodes and our after show that we're getting ready to record.

[01:22:52] **Tim:** After show, pew pew pew.

[01:22:54] **Adam:** It's an inside joke, don't let them know. Oh, sorry. Our top tier on Patreon is for people who pay a little bit extra just to help us out out of the goodness of their hearts and so we want to say a special thank you to Peter and to Monte. You guys rock. And to everyone else that just listens to the show, thanks for listening.

[01:23:08] **Adam:** We love just having listeners and so you guys matter too. We really appreciate it. Please share the show with your friends and co workers because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:23:23] **Adam:** Send us your questions and topic suggestions on Twitter or Instagram at WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. Yeah, seriously,

[01:23:35] **Tim:** leave us a message, guys. We got one message so far and it was awesome. So someone call in. That's my challenge for the week. Call in, leave us a message, even if it's just to say hi.

[01:23:44] **Adam:** Come on, man. Somebody listens to an hour of us blabbering to give them homework? All right, we'll catch you next week. And until then, Your heart matters.

[01:24:14] **Adam:** Like you said, asking, helping,

[01:24:18] **Tim:** Because those last little drips out of the faucet are usually the

[01:24:21] **Adam:** best. That sounded like a pee reference.

[01:24:27] **Tim:** I'm a man of certain age. Pee becomes important. The last little drips.

[01:24:32] **Adam:** I have young children and both of them boys and they're like, dad, how do I, I had to teach my son how to not like pee his pants after he done, after he goes to the bathroom. Pinch it off. Sorry, son. There's always going to be two drops in there.

[01:24:46] **Adam:** There you go. Here's how you prevent that.
