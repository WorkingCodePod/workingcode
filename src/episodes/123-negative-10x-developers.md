---
title: "123: Negative 10x Developers"
description: "On today's episode, we go hard in the other direction, talking about the much less mythical -10x engineer."
date: 2023-04-19
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/123-negative-10x-developers/id1544142288?i=1000609617166"></iframe>

In episode 58, we weighed-in on [whether or not 10x engineers actually exist][working-code-58]. On today's episode, we go _hard_ in the other direction, talking about the _much less mythical_ **-10x engineer**: those engineers that seem to actively work in opposition to the greater good, holding unnecessary meetings and flooding the team with a massive amount of documentation. This discussion was directly inspired by the post, [How to be a -10x engineer][taylor-town].

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[taylor-town]: https://taylor.town/-10x
[working-code]: https://workingcode.dev/
[working-code-58]: https://workingcode.dev/episodes/058-do-10x-developers-exist/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/123-negative-10x-developers.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** Prevent 10 negative one X engineers from getting fired. Don't rock boats. Don't leave a paper. Trail of failures. Vouch for bad

[00:00:07] **Carol:** gosh. The worst. The worst. The no paper trail gets you every time.

## [00:00:31] Intro

[00:00:31] **Carol:** All right. It's episode 1 23 of Working Code, and tonight we're gonna talk about negative 10 x developers. Often we talk about best practices, let's talk about those not so best practices. But as always, we're gonna start with our Triumph and Fellows. I will pass it over to.

## [00:00:50] Tim's Failure

[00:00:50] **Tim:** So I'm gonna start out with a fail. Sorry. Sorry. so, you know, you get excited, you get a new customer. They sign the con, they love the demo, they love your prototype, and then you, you start getting the technical conversations after they sign a contract and then you realize they run all their stuff on WordPress. I'm like, really WordPress? I mean, you guys are a pretty big company. Why is everything on WordPress and you gotta create plugins to, to run our stuff? This is crazy. They're, they're, they're asking, I sent 'em documentation. They, they don't, and the company itself's not doing it. They have like some outside firm doing it and I thought, okay, well it's an outside firm.

[00:01:27] **Tim:** Maybe they're, you know, pretty savvy. And so I just started warning em, say, look, you know, because we're dealing with credit card data, we have to be very PCI compliant. And so there's a limited number of ciphers that we're allowed to use for the, for our SSL certificate. So we turn a lot of ciphers that sometimes people just leave on, we turn them off cuz they're insecure or they.

[00:01:45] **Tim:** And the developer replied, I don't understand anything you just said.

[00:01:50] **Carol:** Oh no. Oh no. That's not good.

[00:01:55] **Tim:** I'm like, he's like, yeah, we just write plugins and, and, and put 'em in WordPress and, and, you know, hopefully it connects. I'm like, okay, okay. That's how this, this implementation's gonna go. This is gonna be a long one.

[00:02:10] **Carol:** no.

[00:02:11] **Tim:** Okay.

[00:02:12] **Carol:** So they're doing the credit card payments through their WordPress site and they're creating their own plugin for it, or they have in the past, and now you need to integrate with that word site that, so that WordPress site.

[00:02:24] **Tim:** Yeah, so, so basically they'll take our, we have a little JavaScript widget that you stick on any HTL page and injects our code to take the credit card data and all the code. It's kinda like an eye frame sort of, goes through our PCI compliant servers. So they just gotta drop. I just, they just gotta drop that in there.

[00:02:41] **Tim:** It's kinda how Stripe does that very similarly. and so yeah, they gotta do that, but it's like anytime I've dealt with people that are working on WordPress, they're you. They're like, oh, can you give us your WordPress plugin? Which we don't have. I mean, it's not really our target audience, but hopefully these guys, they're supposed to be experts at doing WordPress, so hopefully they'll figure it out.

[00:02:59] **Tim:** But

[00:03:00] **Carol:** Hey, maybe you'll get a, a WordPress like marketplace app or something from this. Yeah.

[00:03:07] **Tim:** That'd be cool. So that's me. Now, Adam would normally go next, but he's out. he's on vacation. Yeah.

[00:03:13] **Carol:** I heard he is getting lost in some giant canyon somewhere out west. Oh,

[00:03:17] **Tim:** Oh yeah. That, that, that big ditch out in,

[00:03:20] **Carol:** yeah.

[00:03:22] **Tim:** So how about you?

## [00:03:24] Ben's Failure

[00:03:24] **Ben:** I'm gonna go with a failure as well, and I had a very petty emotional day. And I'll caveat this with saying that this is a hundred percent non-logical, emotional, all about me, not about anyone else. And, a a peer of mine got promoted today. And, got promoted to a higher level in or in the organization than I am, and, he a thousand percent deserves it.

[00:03:53] **Ben:** He's probably one of the best engineers I've ever worked with, just like an all around superstar. Everybody loves him. Everybody has a huge respect for him. He's super enthusiastic. He's like such a a, a team lead and just like, I wish nothing but great things for him and he totally, totally deserved. But seeing it and seeing him get promoted, I felt like shined a light on all of the differences between us.

[00:04:23] **Ben:** And I have sometimes described him as having all of my strengths and none of my weaknesses. And so when I see him move up in the organization, it, it, it underscores how much my weaknesses hold me back in terms of career growth here at the. And so I just had a pretty like, down in the dumps day thinking about that.

[00:04:48] **Ben:** But, I'm gonna get over it. It's, it's, it's just an emotional hurdle and I'll be fine. But it was just kind of a, it was a crummy day. So

[00:04:57] **Carol:** Aw. That's just heartbreaking. Like I hate that for you,

[00:05:01] **Ben:** It, it, it's tough because like, I don't want to do a lot of comparisons. Like I don't want to just be comparing myself to others all the time.

[00:05:09] **Carol:** but we do. We're human. I mean, we do at times.

[00:05:12] **Ben:** And because of where I am in the company and the fact that I work on the legacy stuff and a lot of people don't even understand why we're putting any effort into the legacy stuff, I feel like I'm in a position where I constantly have to explain, not explain.

[00:05:25] **Ben:** I have to justify the work that I do and to see other people then get promoted. It, it, I dunno. It just, it makes me feel poopy and.

[00:05:35] **Tim:** Yeah.

[00:05:36] **Ben:** But again, it's in a completely petty emotional way, having nothing to do with anyone else just to do with me, so.

[00:05:42] **Carol:** No, I get it. Like, with all of this contract work, I've been trying to get kicked off, right? I feel like every single day I'm validating myself to someone who has no idea what I do, and it's to non-technical people who need technical help and trying to get validation. It sucks because when you're on the team that validates you all the time, it's great cuz you can write some code and they're happy with you, they know what it's doing.

[00:06:07] **Carol:** But when you're trying to write code and explain it to non-technical people who just want everything to work right, and you're trying to be like, well it's not gonna work. Right? Cuz it wasn't done right up front and I can't fix it in three hours, you know?

[00:06:21] **Ben:** Yeah,

[00:06:22] **Carol:** constantly like just struggling to find validation.

[00:06:24] **Carol:** So the puppy's giving me a lot of self-love right now.

[00:06:29] **Ben:** yo dogs are

[00:06:30] **Ben:** the best.

[00:06:31] **Tim:** we don't deserve dogs. Hey, Ben. I, I mean, I, I, I get how you're feeling, but I mean, a life lesson is that comparing ourselves to others is. It's, a worthless exercise. In fact, it's a damaging exercise,

[00:06:45] **Carol:** it is.

[00:06:46] **Tim:** it's actually really bad for you. Regardless if you're comparing yourself to someone going, oh, I'm so much better than them.

[00:06:51] **Tim:** You know, I'm this, this, and this. Or if you're comparing yourself, oh, I'm, you know, this person's so much better than me. This, this, and this. We tend to just take, you know, our best or worst qualities and compare them. You know, the opposite on them, right? If, if you're depressed, you, you know, you're taking your, your worst qualities, comparing it to their best. It's pointless. You don't know their journey, you know yours, right? You know, you can list all the reasons why you're where you're, where you're at, right? You know your journey. Like, well, you know, I was really comfortable and I really enjoyed working on a legacy platform, and I was good at it and no one else was doing it.

[00:07:23] **Tim:** So, you know, a hundred reasons. You can say why you are where you're at. You don't know those reasons for that person, right? Even if they're, even if you're close to them, you don't know their reasons, right? So,

[00:07:33] **Ben:** it, it's funny because like probably at my darkest moment where I was like really going down an emotional rabbit hole, at one point I was like, you know what? Maybe I could spend less time judging myself. And more time being disappointed in other people. Like,

[00:07:47] **Carol:** No.

[00:07:49] **Ben:** like what I mean is, is is I oftentimes, I, I, I feel very angsty about letting other people down, but then I give other people so much more benefit of the doubt.

[00:08:01] **Ben:** At least I like to think I do. But I'm like, you know what? Maybe some of that benefit could just be taken away and be like, yo, I'm pretty disappointed that this person is not doing the job that I think they should be doing. And then I, and like the only reason I go down that really dark hole is cuz then like, I, I can feel less bad about myself.

[00:08:18] **Ben:** But again, like I said, that, that was at like eight o'clock this morning. So I've had a all day to process it and I, I'm feeling much better now.

[00:08:26] **Carol:** Good.

[00:08:27] **Tim:** that's good because at the end of the day, the only only thing you can control is yourself, right? You can only control. That's all you can do is you can control your actions. So

[00:08:34] **Tim:** if

[00:08:35] **Carol:** I agree.

[00:08:36] **Tim:** take those feelings and use 'em for fu fuel to say, you know what? I gotta get it better at X, Y, and Z.

[00:08:41] **Tim:** And that's on me, has nothing to do with the other guy. I just, and I need to get better at these three things. I'm gonna start working on that.

[00:08:47] **Ben:** Hundred percent. So that's me. Carol, what do you got going on?

## [00:08:52] Carol's Triumph

[00:08:52] **Carol:** Well, you guys had failures and I was gonna call mine a failure, but I'm gonna call it a triumph just because we can't all be failures, right? I ain't got nothing going on. We had some family emergencies happen this week, and I decided, That, you know what? It's okay if I don't like finish this class that I'm in right now, that I can actually work on family things.

[00:09:13] **Carol:** And today, look, I cleaned the pool cause it really needed to get cleaned, but I literally have nothing going on and I'm happy that I can just sit back and go, I ain't got nothing going on. And that's okay. So no triumphs, no failures. It's just good. You know, the family stuff all worked out. Mom's okay.

[00:09:32] **Carol:** So yeah, that's.

[00:09:35] **Ben:** Yeah, sometimes you just need time like that.

[00:09:37] **Carol:** I agree, and I'm at the end of it because now everything's ramping up in my life. So I think this is my last free week too. So yeah, it's all gonna get hectic real soon.

[00:09:49] **Ben:** When you say last free week, do you mean you have contracting work that's gonna

[00:09:52] **Carol:** Yep. Yeah, actually I have work I'm starting on, so, I've already started a little bit, a few little things here and there. Nothing big. Just, like Tim mentioned, there are people who have their sites running on WordPress and have no idea how to use them. And when they're friends of yours and their companies say, Hey, can you just teach us how to modify these things?

[00:10:14] **Carol:** You're like, sure, here's my. Give me three hours and I'll show you how to do this yourself. So, you know, little things like that have been fun to work on cuz it gives me, interaction with a whole different set of clientele cuz they're not looking for you to code something for them. They're just wanting to understand how they get their Instagram posts to show up in their feed.

[00:10:33] **Carol:** And, you know, I'm like, Here's the plugin for it. Here's how you use it. So it's just a little research and then, you know, showing 'em how to do it and then answering some questions, you know, for a few days if they have any, just because they are friends. But yeah. And then next week I actually start writing big code for some bigger projects.

[00:10:51] **Carol:** So excited about that. Yep. I, I'm getting to do type script and react, so I'm super excited about that. I don't have any CF on my plate at the moment, but if CF falls onto my plate, that'll be okay.

[00:11:05] **Tim:** And I'll, I'll play Adam. It should be spelt.

[00:11:11] **Carol:** Spelt ain't paying me though. So react, reacts gonna pay the bills. Alright. React

[00:11:16] **Tim:** There you go.

[00:11:18] **Carol:** anyways.

[00:11:19] **Ben:** Very cool. That's exciting.

[00:11:21] **Carol:** So, you guys ready to roll? Show.

[00:11:23] **Ben:** Let's.

[00:11:24] **Carol:** Let's do it.

## [00:11:26] Negative 10x Developers

[00:11:26] **Carol:** So Tim, you posted in Discord about, a post you had read about negative to next developers, and you suggested that we talk about this. So you wanna kick it off and, and get it going.

[00:11:37] **Carol:** Cool.

[00:11:38] **Tim:** So, you know, if you heard about, you know, 10 x engineers, which they're probably mythical, but they're, there's these entities that when you add them to a team, they multi, they're a force factor of, you know, times 10, that everything gets more efficient, that they're super efficient, the entire team gets better cuz they're bringing best practices and things like that. Rather not, they exist or not. I don't know. In fact, that's the first sentence of this is, this was from an article or a blog post from someone called Taylor Town and he says 10 X engineers may be mythical, but negative 10 X engineers exist.

[00:12:14] **Carol:** yeah.

[00:12:15] **Tim:** So to become a 10 x engineer, you just simply, you know, you and your team have to waste 400 engineering hours per. And, and then he lists, I don't know how many, there's a whole bunch of strategies here that when you read them, you're like, oh yeah, we kind of do that. Yeah. That's, that's not good. I dunno if we waste 400 hours, but we, we definitely, definitely have this habit. So I, I thought it'd be fun if we could count it.

[00:12:38] **Tim:** We don't have to go through these one by one, but we just, just, Randomly pick one out. That, that, that resonates with us. because sometimes, you know, you can tell people best practices and it's hard to imagine, and if you're not doing them how that looks like, but when it's a bad practice, you probably pretty much can imagine exactly what that's like because you've done it at some point.

## [00:12:57] Holding Coworkers Hostage

[00:12:57] **Carol:** So, I, I can give you one that I saw in here that stood out. So one of the ones that they call out is Hold 10 engineers hostage. In a technical discussion, what's the worst part is when the discussion is going nowhere for, say you wanna decide if you wanna edit your PDFs with Adobe, or if you wanna, you know, build something yourself.

[00:13:17] **Carol:** And everyone on the team says, let's just use a product that already works for editing our PDFs and one person. Won't give in. So then that one person holds everyone hostage to discuss why we should write our own tool to, to handle something that the market's already created. We know nothing about form development and when it comes to the big grand scheme of thing, right?

[00:13:40] **Carol:** Like that's not what our software is intended to do. So why would we ever wanna try to build PDF editing like into our own software when we could just plug in something and pay for it. However, we could sit at a table and discuss. Four hours. On hours. On hours and still come up with no solution because one person won't give in.

[00:14:00] **Ben:** Yo.

[00:14:01] **Carol:** Oh.

[00:14:01] **Ben:** a hundred percent I The worst for that is, is when you get to the end of the meeting as well, and they're like, well, let's go and do some research and then we'll convene again to review the research. You're just like, oh my God, or that you. Or this, this ties into another one, which is the um,

[00:14:20] **Tim:** Before you jump to that one, I, I get on this one. So it it, it makes the point. So encourage them to pursue elegance over pragmatism, which you, you get these people with their very entrenched ideas that they, oh, you know, this is the most elegant way to do this. You know, are we gonna use this library, not that library, cuz it's, you know, it's much better and you know, at the end of the day, is it gonna get done?

[00:14:43] **Carol:** Yeah.

[00:14:44] **Tim:** Is it gonna get done? You gotta be

[00:14:45] **Carol:** can be achieved? Yeah.

[00:14:47] **Tim:** And then make sure that no one has the authority to make the decision at the end of the, you know, you can have this, you know, you can, yes, you can have this conversation, technical discussion, but at the end of the day, someone's gotta put, you know, be in charge and put their foot down and say, all right, we've talked about this for two hours.

[00:15:02] **Tim:** We really haven't come to any good decision. I'm just calling it we're doing X and everyone's just gotta move on. And, you know, disagree, but, you know, commit.

[00:15:11] **Ben:** Oh man. Then what is the saying that you had said before that I fell madly in love with, but clearly didn't fall back in love with it because I forgot it. But to like, to commit to something like, even though you don't really like, like the idea, but once you're sold, you're like, all right, I'm gonna do that and I'm gonna put my all into it because I've been heard and what Tim was saying. Uh,disagree and commit, I think is what the, the phrase is.

[00:15:34] **Carol:** No, there was another term you had before. I will remember it and post it.

[00:15:38] **Tim:** I think it's strongly.

[00:15:41] **Carol:** Loosely held

[00:15:43] **Ben:** opinions loosely held.

[00:15:44] **Carol:** That's it. Yeah. That

[00:15:45] **Ben:** as, as I've said, I have strong opinions strongly held. But, but,the other one that I really enjoyed here in the list, add 400 hours of communication overhead, meetings, rec calendars to inconspicuously, waste others' time, write lengthy messages and documents, and share as widely as possible. Welcome all opinions and aim for engagement. This like hits so close to home and I think dovetails with the idea of holding people hostage. So we, we, we do this at. My place of employ where people will put together these giant documents and circulate them, and I'll open a document and if it has a ton of stuff in it, I'm, I'm just like, immediately, nope. And close it down. I'm like, it's already gotten past the point where I feel, engaged with the, with the process.

[00:16:35] **Ben:** I, I like to be in that really early, like, idea formulation. If you've already written down a hundred, like a ton of stuff, I, I feel like you already know what you wanna do. You don't need my feedback.

[00:16:45] **Tim:** Yeah.

[00:16:46] **Ben:** You should get feedback in that fledgling, like, I have a seed of an idea. Let's talk it out for a couple minutes, and then you just move forward.

[00:16:53] **Ben:** I don't wanna iterate over someone's, you know, magnum opus on how they wanna put something together.

[00:17:01] **Tim:** I think a lot of that. They do that, it's almost passive aggressive, right? You send this huge document, this huge document, like, you know, so we want feedback on this. You know, here's how we think it, you know, they're acting like it's, you know, not already decided. Right? But if you spent a week writing, you know, like you said, a magnum opus, they're ready to go with it.

[00:17:20] **Carol:** You already know what you want. Yeah.

[00:17:21] **Tim:** What they're, what they're really doing is they're covering their butts so that it's like when, when, when things go bad, they're like, we had your opportunity to give your input and you didn't say anything, so you're, you, you're also part of the problem that, that this failed. Right? So it's like, oh, just awful.

[00:17:37] **Ben:** There, there's, there's a quote from Mike Tyson, which I'm sure you've heard or some form of it, which is everybody has a plan to like, get punched in the mouth like the, you know, the other, the other version is like, everyone has a, like all, what is it? No plan. Survives first contact with the enemy, I think is another popular variation.

[00:17:57] **Ben:** But that's, that's how I always feel when people do all of this work upfront, is that no matter how deeply you think about something, to me, it always falls apart or at least becomes highly unstable the moment you start to build it. Because you, you find all these little points and corners of the application that you didn't Yeah, exactly.

[00:18:17] **Ben:** And you're like, oh, we gotta rethink some of this. So you gotta just start. And, and go from there.

[00:18:24] **Carol:** Yep. Iterative development is like the best thing to do. Get what you can out and then just iterate on it until you like what you have.

## [00:18:33] Irrelevant Meetings

[00:18:33] **Tim:** And, and talk about meetings, like what I've noticed, it seems like the bigger the organization, a lot of times we have or, you know, meetings with other organizations. If it's a small, smaller company, you know, you have maybe one, two people on the Zoom call or the me, you know, the teams call or whatever you're using.

[00:18:49] **Tim:** But really big organization, I swear that there's a, like a biweekly call that I'm on with this really large company and there's, from their side, 10, 12 people on the call, and I'm pretty sure only two of them have ever spoken besides, besides the initial, hi, my name is, and this is my role, and I'm like, what are these people doing on the call?

[00:19:11] **Tim:** If they have no input, what, and they're, I'm pretty sure they're not paying that close attention. Just record the thing in transcript and send it to 'em later if there's something they need to know, you, you wasting just dollars of dollars of people's time, of all these expensive bodies just sitting on a call where they say absolutely nothing, contribute.

[00:19:27] **Tim:** Nothing.

[00:19:29] **Carol:** It's not like there's action items after that they need to go task on. Right. This is literally just them being there to be in the meeting. That's awful. That's terrible.

[00:19:38] **Tim:** Ty, typically the people we're call talking, they're the only ones getting the action items,

[00:19:42] **Carol:** Oh yeah. I would be, if I was one of the other people,

[00:19:46] **Tim:** I don't even remember why. You know, it's like these five people are, are on the call. I don't remember what they do or why they're even interested talking about it, so it's ridiculous.

[00:19:57] **Ben:** Every now and then I'll get on a call with a bunch of people and they're talking about all of the really complicated stuff that they're working on. And I'm sitting there quietly like, am I supposed to be working on this stuff? Because like no one assign any of this to me.

[00:20:14] **Carol:** why am I here?

[00:20:15] **Ben:** I know I feel very out of place all of a sudden.

[00:20:18] **Tim:** All right. Let me pick one.

[00:20:20] **Carol:** Okay.

## [00:20:21] Worthless Documentation

[00:20:21] **Tim:** Right. Worthless documentation. Explain code and private messages. Write wikis that nobody uses.

[00:20:31] **Carol:** Oh, that's so real. Like a, you're wasting your time writing it and then it's never gonna be maintained. So when that one person does find the documentation that you wrote, it's so out that they're lost on what they're trying to accomplish now.

[00:20:48] **Tim:** Yeah.

[00:20:50] **Ben:** Un

[00:20:51] **Tim:** documentation is good, but it's like if, if, if it's not anywhere anyone's ever gonna be able to see

[00:20:55] **Carol:** No.

[00:20:57] **Ben:** It's interesting because when I write for myself, I, I have a very, pros approach. Like I write, like I'm talking to someone, but then when I read technical documentation internally and people write like that, I'm like, oh dude, just keep it bullet points. Like I don't wanna, I don't wanna know. It's like when you go to the recipe sites and they tell you like, oh, I was walking, you know, on the coast in

[00:21:23] **Carol:** scroll, scroll,

[00:21:24] **Ben:** Yeah, yeah,

[00:21:25] **Carol:** Yeah.

[00:21:25] **Ben:** Yo, there's so much background inform. And complexity in some of these documentations. And I, I think by, that's a, in part, a byproduct of the complexity of the services and some of these services just like way too complicated and have all these state diagrams. I, I don't know, I, if it takes a lot to explain how a service works, I feel like it's doing too much or something, or it's com too complicated. It doesn't.

[00:21:51] **Carol:** yeah, I was gonna say, I like to create 400 hours of busy work. you know, this says ask your team to perform tasks that resembles work, like common examples or presentation diagram, ticket management, just, just pointless rituals. We had gotten really, really good at a previous job about, any new implementation that you added to the system.

[00:22:11] **Carol:** You needed to create a plant, u m L for. Which is just a diagram of how the whole process works, which is all fine until you realize not everyone understands how to write the code for plant U M L, which is you write it and you store it in your code base, like it's actual code. And if you don't understand how to write it, now that person's having to go learn Plant U M L to just put a box on piece of paper when.

[00:22:38] **Carol:** Like a Confluence page that just says what it was doing would've been sufficient for what you were trying to accomplish. So I'm like, sometimes you don't have to code out the entire process. It's okay to skip the plant. U m L. Just put it in a Confluence page. It's, it's fine. Don't waste 40 hours trying to learn plant u m L to put an arrow to a box.

[00:22:57] **Carol:** That's okay.

[00:22:59] **Tim:** I feel bad for the people. I mean there's, I see some people working jobs where pretty much their only job is to just deal with the ticketing system.

[00:23:09] **Carol:** Yeah,

[00:23:09] **Tim:** don't mean like in a technical way, I mean just managing tickets,

[00:23:12] **Carol:** it's awful.

[00:23:13] **Tim:** That's just it, that I don't, you know, I, I guess if you're a big enough company, you gotta do it.

[00:23:18] **Tim:** But it's like sometimes people get so, Hung up about where the ticket is and what's, you know, the status is. And it's like, at the end of the day, is the work getting done? Can we, can, you know, it's like, oh, it hasn't gone through this step. Well, maybe not. Everything needs to go through that step. Well, how do I test this?

[00:23:36] **Tim:** Well, you know, can, you know, that's particularly with us. It's like lot of stuff that we do. It's like, it's not. Testable, you know, to prove that it's gonna work in live, but you have a higher degree of confidence it's going to, right? So they're like, well, we need to make sure that I'm like, no you don't.

[00:23:52] **Tim:** They're like, no, you don't. Well, how's it gonna get tested? I tested it. It works. You can't do that with everything. I mean, you do need to be doing testing, but it's like some people just, they get so anal retentive about the flow of the ticket. The ticket's just there to drive the work, but, The whole focus is about, you know, making sure the ticket is nice and clean. That's just, that's a, that's busy work.

[00:24:20] **Carol:** Yeah. I, I, I think Ben inside with that, cuz I think recently he was trying to just add a new swim lane to the ticketing system and got his hand slapped.

[00:24:30] **Ben:** I still have. So they added, they added a column on our con bond board called, blocked. And I have like 10 tickets in it that are blocked simply because the person who's managing the board doesn't have the right permissions to add a new status. I wanna, I have these 10 tickets and I want to cancel them, but I can't move them to cancel because there is no canceled status and I don't wanna delete them because the fact that they're being canceled has meaning.

[00:24:57] **Carol:** Do you have, do you have the option to mark them done but like with a fixed resolution as will not resolve, or not an actual problem, which would kind of do the same thing?

[00:25:09] **Ben:** You know, that's a good question. I'm, I'm not sure, I also am only just realizing recently how different everybody's con bond boards at work are. I thought, I thought Jira was like, basically all the boards were the same except like different statuses and different swim lanes and stuff, but, There's lots of variation.

[00:25:27] **Ben:** I didn't quite realize how intense it was.

[00:25:30] **Carol:** I think most companies strive to keep things uniform, but teams like to work independently and like to follow their processes. So things aren't gonna always be exactly the same, but typically you would find that most, most boards have the same swim lanes, like the same status of where the ticket could be in.

[00:25:48] **Carol:** but yet it would just have different options for like, you know, do you do sprint work or do you not do sprint? Do you do fix? Do you do releases? Like those type of things would differ. So if your teams have substantially different swim lanes, that's interesting. Cause that would mean whenever you try moving to do work for another team, you're gonna be very confused on your day-to-day work life.

[00:26:09] **Tim:** Yeah,

[00:26:09] **Carol:** be like, where is my block status? You don't get one on this team.

[00:26:14] **Tim:** We, we've been using our, our our kind of like one of the parent companies, JIRA instance. And they, they, I mean it works really well for them. but doesn't really, hasn't really worked well for us cuz, We're typically not answering to customers, right? We're building a product and it's not like a customer's driving, so sprints don't really make sense for us.

[00:26:32] **Tim:** we have stories and things like that, so we just, just this week actually moved off of their Jira onto our own because our team size is so small. We we're still at the, the free tier, so, Yeah. But yeah, we've been working on that this week of getting, getting it up and running, so it's, it's so much better just to be able to not worry about 10 different statuses.

[00:26:52] **Tim:** We, we got in work ready to test done.

[00:26:58] **Ben:** Well, and, and the idea of being in a sprint versus just moving. Across the board. That's definitely a point of contention for us at work because the managers seem to want sprints so they can plan out into the future. I don't know how well that

[00:27:12] **Carol:** Roadmapping. Yeah.

[00:27:14] **Ben:** and everyone, like all the engineers are just like, I just wanna move stuff across the board.

[00:27:18] **Ben:** Like sprints don't mean anything. When a ticket's done, I take the next ticket. It doesn't,

[00:27:22] **Carol:** And see, I think working in like a combine style like that where you don't have a sprint, where you just work works well as long as you keep your backlog groomed and you keep the priorities high and your engineers know to pick up, the top. Things in the backlog versus just picking up whatever they wanna go work on.

[00:27:40] **Carol:** So if product is like, Hey, we really need to get this initiative done, so it's number one in the backlog. The engineering team needs to know that the top five items are critical. And once those five are done, then you kind of can keep weeding out what you wanna work on. But what we found is if we didn't put things in like a sprint type format, Developers would just pick up whatever they wanted to work on.

[00:28:01] **Carol:** They didn't like the idea of being told, like, pick a priority. They liked, you know, as long as there was like 10 or 15 to choose from, then they were good doing that. So,

[00:28:12] **Tim:** You got one.

## [00:28:13] Pointless Tests

[00:28:13] **Ben:** I, I know Carol mentioned this one earlier, in, in regards to me, but the right pointless tests. It just, it feels like it's hit really home for me lately because I've been trying to change stuff at work and the slowest part for me seems to be fixing the tests that are breaking for reasons I don't quite understand.

[00:28:31] **Ben:** And they're, it's not that they're catching issues, it's like the tests are just written in a way that makes things hard to delete.

[00:28:39] **Tim:** Your whole job is to delete stuff,

[00:28:41] **Ben:** yeah. Yeah. My whole job was to delete stuff. I, I, I just have such a love hate relationship with Tess. I in,

[00:28:48] **Tim:** Really? I've never heard that before.

[00:28:52] **Ben:** part of me wonders if, hear me out here for a second, if, if Tess are meant to be guardrails against things that break, I almost wonder what would happen if you started out with no tests.

[00:29:07] **Ben:** And then just added tests as things broke, like a developer goes to change something and it, and it breaks in production, they're like, oh, okay. That was clearly a confusing thing. Let's write a test for it. Instead of trying to test the universe first and then let developers feel safe, I almost, I almost feel like it'd be much easier to, to not test anything until the thing has proven itself to need a.

[00:29:32] **Tim:** But you're, you're accepting the fact that it's okay to break in production. I mean,

[00:29:36] **Tim:** not everyone's le Yeah. Not everyone's level of comfort is to that point.

[00:29:41] **Ben:** yeah. It all depends on what type of work you're doing for sure. As well. Anyway, that's, that's what I've been thinking about a little bit there.

[00:29:50] **Tim:** Well, I like how it says mock function calls until no

[00:29:52] **Carol:** Oh gosh, right? Like what's the point of this test anymore? You're literally just mocking that. It would always be true. So it's always true. There you go.

[00:30:03] **Tim:** well, what's the point of testing that?

[00:30:05] **Ben:** I, I, I have found a lot of trouble with code coverage tests, or, or sorry, like constraints where you can't deploy your code unless your code has like 80% test coverage or something. I, I don't know. That seems to. That just seems to be a problem. I, I've never seen a team that is really happy with the way that's functioning.

[00:30:26] **Ben:** Even teams that are really protesting, I feel like they run into a, ugh, I just gotta write test for something that's never gonna break, so that the code coverage passes.

[00:30:36] **Carol:** Oh yeah. I mean, I'm not gonna say I did this because you. I don't do bad things often, but when, um, so whenever I was working on a type script project, you know, there was no like application, there was no interface that anyone would ever see. So I had some console logs that I would write out into the CloudWatch logs so that I would get a little more information in the log than having to dig through my admin side because I didn't have access to that in production.

[00:31:03] **Carol:** But what I did have access to was the CloudWatch logs. So I'm like, oh, I'll just throw a little console log here. Well, in order to get test coverage on all of that, I ultimately was just like Jess and I found a way that I could make sure that it returned back a console log message so that it always had a hundred percent test coverage.

[00:31:23] **Carol:** It thought the whole function was covered because enough of it was to get to it, and I was like, okay, it's deployable.

[00:31:33] **Tim:**

## [00:31:33] Creating Useless Tools

[00:31:33] **Tim:** Alright, here is my, here's, this is my absolute favorite one. All right. Yeah, so creating useless tools. So decide that existing solutions are quite what you need, and then write scripts that only one person understands if the script does something important.

[00:31:46] **Tim:** Avoid documentation.

[00:31:47] **Carol:** Yeah.

[00:31:50] **Tim:** So you got a little, you got a little handy dandy gadget tool that, you know, something goes wrong. You can just run this real quick and it fixes everything. yeah, keep that completely secret and then that way you're the only person who can run it. So that way you can be the hero. But if you're out, if you're out, no one knows how to do it. Cuz they, you know, there's no documentation. They don't even know about the script in some special folder on your local hard drive.

[00:32:11] **Carol:** Yep. Been there. Or what's even better is you have to share that folder with someone. When you decide to leave the company and you're like, Hey, I put all this in the Google Drive for you.

[00:32:24] **Tim:** Here's my secret Swiss army knife to fix stuff when it hits the fan.

[00:32:28] **Ben:** We had a database guy at work a couple years ago and he had wired up some metrics coming outta the database and putting them on some Datadog dashboards for me so that I could see things like how many slow queries were running per minute or, or like, you know, read, reads and updates and delete operations, that kind of stuff.

[00:32:47] **Ben:** And he left the company and like a year later, all of a sudden my stats stopped working. So I went to the data services team and I was like, My dashboard broke. I don't know what happened on your end. I don't know if something's wrong with the database. And, they had just been cleaning up some old e c two instances that they thought no one was using.

[00:33:05] **Ben:** And apparently the guy who had set it up for me did some like totally custom script that just ran on an e c two instance that nobody else knew about. And so when they were like, oh, no one's touched this computer in a year, it must not be in you. So they deleted it. And I was like, no.

[00:33:22] **Carol:** Baby come back.

[00:33:25] **Tim:** That's, that's my favorite. The infrastructure team. They're like, we don't really know. Is anyone using this? And they ask around. No one remembers. And they're like, let's just turn it off and see who yells.

[00:33:33] **Ben:** Yeah, the scream test. I've been, I've used the term scream test like every other day at work for the last couple of weeks because we're in

[00:33:40] **Carol:** a good one.

[00:33:40] **Ben:** yeah, it's great. We're in this huge cost cutting initiative and there's a lot of caution around turning things off because nobody knows what anything's really being used for.

[00:33:50] **Ben:** I'm like, just turn it off. Just do it. What's the

[00:33:53] **Tim:** You sound like Elon Musk. That's, that's what Elon did when he took over Twitter. He is like, just, just shut these services down. We don't, they, we don't need them. We don't need them. Fire everyone who works on that team.

[00:34:03] **Carol:** more food for you.

## [00:34:04] Tiger Teams

[00:34:04] **Carol:** So I don't see this one on here, but one thing that we've seen before is Tiger Teams. So like whenever you pull everyone together and you're like, we want the best of the best to work on just this initiative and you can't ask them questions and all they're gonna do is work on this one project. They get nothing done on the project, by the way, cuz you can't fix everything all at once with one team.

[00:34:28] **Carol:** Plus these people are probably so strong-headed that they're not gonna work well together anyways cuz they're gonna all. Have their own reason for why they did it wrong in the first place, because they probably were the ones that wrote it originally. And they're gonna spend more time defending their original actions than fixing the problem.

[00:34:45] **Carol:** And then you come a off this tiger team with nothing really solved, only to find your teams are so far behind that you can't get out of this hole either. So tiger teams are a terrible thing too.

[00:34:58] **Tim:** Yeah, I, I think it kind of, it's similar to trap 10 engineers in a fetal skunkworks project.

[00:35:03] **Carol:** Oh yeah, that would be it.

[00:35:05] **Tim:** Yeah, so get the bright engineers, waste their potential, undersell the difficulty of the project to management, oversell the project's usefulness, and until the management's almost complete, until they scrap it.

[00:35:15] **Carol:** There you go. That's exactly it. Yeah,

[00:35:18] **Tim:** Yep.

## [00:35:20] Not Valuing Estimates

[00:35:20] **Ben:** One of the things that we had some issues with at work is the product team would, Have an idea for a feature that they want to build, and then they would get an engineering team to come up with a super detailed estimate of how long it would take and like why it would take so long.

[00:35:36] **Ben:** And it would take the engineering team like days to do the research and come up with the stuff, only for the product team to turn around and be like, no, that's gonna take too long. We're not gonna do it. And they're like, we just wasted so many developer hours trying to come up with a, with an idea just so that you guys could shoot it down.

[00:35:51] **Ben:** And they were like, we don't wanna do estimates for you anymore. It's very painful and you don't seem to appreciate it.

[00:35:57] **Tim:** Yeah, for.

[00:35:59] **Carol:** Yeah, I've worked at a place before where we started charging the customers for estimates because they would turn down so many and we're like, okay, well if you're not gonna keep paying for these, then going forward you're gonna pay up front for us to do the estimate because you turn down so many.

[00:36:13] **Carol:** So make sure the work you want us to estimate for you is work you really actually want.

[00:36:19] **Tim:** Yeah,

[00:36:19] **Ben:** Totally.

[00:36:20] **Tim:** someone's got some crazy hair braid on it. You're like, Hey, could we do that? Oh, no, let's ask. It doesn't cost us anything.

[00:36:26] **Carol:** Yeah, it's free to ask the question

[00:36:28] **Tim:** Yeah. Yeah, exactly.

[00:36:30] **Carol:** 12 hours later.

[00:36:32] **Tim:** Yeah.

[00:36:33] **Ben:** Well, I, I think another thing that could be on this list is to never push back against product ideas. I, I can't tell you how many engineers will just go super deep on something because a product person asks them to do it, and the product people have no idea necessarily how things get implemented technically.

[00:36:52] **Ben:** So they don't have a, a, a system of measure for the hair brainedness of their. And the engineer has to learn how to push back and be like, whoa, are you sure? That's super complicated. Do you understand how how much work that's gonna be?

[00:37:08] **Tim:** Yeah.

[00:37:09] **Ben:** It's

[00:37:09] **Carol:** it sounds so easy up front.

[00:37:11] **Ben:** Yeah.

[00:37:13] **Tim:** Yeah. I mean, you think about a product like Twitter, it's like super easy, but yet to be able to scale. Not easy.

[00:37:19] **Carol:** No.

## [00:37:23] Hard to Debug Code

[00:37:23] **Tim:** The, the, the very last one at the bottom, really just this one hits me where I live. incur 400 hours of bug triage. So make unable programs and let's, let's be clear, early ColdFusion style of writing where you have like a bunch of, you know, CF sets and some queries at the top, and then a whole bunch of, you know, output codes and some loops in there at the

[00:37:45] **Carol:** Good luck buddy.

[00:37:47] **Tim:** I mean, the only way you debug that is like you just hit F five and start changing stuff until it works. Right. It doesn't throw any more CF errors, but yeah. You know, write spaghetti code, make everything sensitive to initial conditions. Yeah. Avoid pure functions. Yeah. That that was early C, you know, five tag, CFM L use dependencies liberally and say it works on my machine whenever possible.

[00:38:10] **Tim:** The old, it works on my machine. Oh my God. I heard, I've heard that so many times in my career. I don't know. It works on my machine. Yeah. My code's good.

[00:38:18] **Ben:** , when we first started working on our product a decade ago, we were on a really early version of framework one, which is a, ColdFusion framework and part of it is a DI one de yeah. Part of it is dependency injection one, which is just a, an inversion of control framework.

[00:38:34] **Ben:** And the version that we started with, you couldn't have circular dependencies, like you couldn't have component. Require component B, but then component B also require component A and then a version of d i one came out that fixed that because it, it delays all the stuff and you can wire things together.

[00:38:52] **Ben:** And I remember at the time I'm like, that seems like a really bad idea. Like we've had this constraint where you can't have things in a circular dependencies, and, and they fix that, and now we're leveraging that feature. I'm like, that doesn't sound right. I'm like, I feel like you're. Something is missing there.

[00:39:11] **Ben:** That should be orchestrating calls between those two things. Having calls go back and forth, back and forth. That's

[00:39:18] **Carol:** Does not seem healthy. Yeah,

[00:39:21] **Tim:** I'm pretty sure Sean will weigh in on that.

[00:39:25] **Carol:** please do.

[00:39:27] **Tim:** I just see so many of these.

[00:39:29] **Carol:** Yeah.

[00:39:29] **Ben:** these really ring true.

[00:39:31] **Tim:** Yeah. Hi, higher. 10 zero x engineers. It's just Deadweights. This is dead. They're just taking up space. They don't, they don't do anything.

[00:39:44] **Carol:** I mean, that can be said for leaving on the people too, right? Like how many times have you worked with Deb? Wait, who? No one would take the time to fire. Like it was easier to just push 'em to the side and hope that you make 'em mad enough that they leave instead of just taking on the ownership and being like, you suck.

[00:40:01] **Carol:** Get outta here. We're gonna find someone that doesn't.

[00:40:04] **Tim:** That's, that's the next and last one. Prevent 10 negative one X engineers from getting fired. Don't rock boats. Don't leave a paper. Trail of failures. Vouch for bad

[00:40:13] **Carol:** gosh. The worst. The worst. The no paper trail gets you every time.

[00:40:18] **Tim:** Yep. Just hope. Just hope they leave.

[00:40:20] **Carol:** This is a really good post. I'm really glad that it was written.

[00:40:25] **Tim:** Yeah. Like I said, I think it's easier to visualize these. Now the opposite is how do you, how do you do better? Don't do these things first, right? Stop, do, stop doing this. When you see yourself doing it, call yourself out on it and and say, all right, what should I be doing instead?

[00:40:39] **Carol:** Call your team out too.

[00:40:41] **Tim:** Yeah.

[00:40:42] **Tim:** for sure,

[00:40:42] **Ben:** Do we cover 'em all? Basically.

[00:40:44] **Carol:** Yeah, I think so.

[00:40:46] **Tim:** The link will be in the show notes.

[00:40:47] **Carol:** Wants you to go check it out. If you can't read the show note, it's Taylor slash negative TenX, so

[00:40:55] **Tim:** Yep.

[00:40:56] **Carol:** you should be able to find it. Yeah.

## [00:40:58] Patreon

[00:40:58] **Carol:** All right. So this episode Working Code is brought to you by No Jokes because Adam's on vacation, you guys and listeners like you. If you've enjoyed the show and you wanna make sure we can keep putting whatever this is onto the universe, you should consider supporting us on Patreon. Our Patreons help cover our recording costs and editing costs, and we couldn't do it, every week without them.

[00:41:19] **Carol:** Special thanks to Monte and Giancarlo. And this week we actually have a new Patreon too. oh man. I really hope I don't get your name wrong, but it's M R E J. I'm gonna go with Merge. So maybe

[00:41:36] **Ben:** Heck yeah. Welcome to the party.

[00:41:38] **Carol:** Yeah. Yeah. Thanks for supporting us. We appreciate it.

## [00:41:41] Thanks For Listening

[00:41:41] **Carol:** And for your homework this week, why don't you send us your topics or questions? You can find us @WorkingCodePod on Twitter, Instagram. You can also head over to workingcode.dev/discord and reach out there or you can email us at WorkingCodePod@gmail.com. So that's it for this week. We'll catch you next week until,

[00:42:02] **Tim:** Remember, your heart matters unless you're a negative 10 X developer. Your heart is dark and useless.
