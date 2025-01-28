---
title: "097: Expectations Of Professional Software Engineers"
description: "This week on the show, the crew reviews Mike Acton's talk, 'Everyone Watching This Is Fired', by way of Adam Johnson's article, 'Expectations of Professional Software Engineers'."
date: 2022-10-19
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/097-expectations-of-professional-software-engineers/id1544142288?i=1000583154886"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew reviews [Mike Acton's talk, "Everyone Watching This Is Fired"][mike-acton], by way of [Adam Johnson's article, Expectations of Professional Software Engineers][adam-johnson]. This talk outlines 50 characteristics - both technical and non-technical - that go into making you and your team fit for building products and dealing with customers. Some of these line-items makes us feel seen while others leave us feeling attacked. Listen to find out which ones are which!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-johnson]: https://adamj.eu/tech/2022/06/17/mike-actons-expectations-of-professional-software-engineers/
[mike-acton]: https://www.youtube.com/watch?v=cV5HArLYajE
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/097-expectations-of-professional-software-engineers.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** Number 40. I feel I can schedule my own time. Well, you're an adult person. Just use a calendar.

## [00:00:06] Intro

[00:00:06] **Adam:** Okay, here we go. It is show number 97, and on today's show we're gonna talk about expectations of professional software engineers, which maybe, I don't know how, trendy this is right now, but, Tim sent us this article called Expectation of Professional Software Engineers, and, uh, we thought we would have a, a go at discussing it.

[00:00:43] **Adam:** so, we're gonna get into that. Carol couldn't be with us tonight. Something came up with her at work at the last minute. So just the boys tonight. but as usual, we're gonna start with our triumph and fails.

## [00:00:51] Adam's Triumph

[00:00:51] **Adam:** Looks like it's my turn to go first, so I'm gonna start us off strong on a triumph. I didn't want to come to the podcast.

[00:00:58] **Adam:** I didn't want to eat dinner today because I spent the vast majority of my day working on spelt code and it's so much fun. I just didn't wanna put it. It was that kind of day, like, Don't leave me alone. Don't bother me. Don't, I'm not gonna check my email. I'm not gonna do, There was no Twitter, there was no Facebook.

[00:01:14] **Adam:** It was just like going deep in the code and having a great time. And, and that

[00:01:19] **Tim:** So that's why you're late to recording tonight, wasn't it

[00:01:23] **Adam:** and then, I guess, I'll throw this out there as well. I didn't know it at the time, but, last week when Ben and I recorded, I was starting to come down with strep throat. So if I was sounding particularly gravelly or terrible on the recording, Sorry about that.

[00:01:36] **Adam:** I thought you'd just taken up smoking

[00:01:40] **Adam:** don't tell my mom. yep. So, that's it for me.

[00:01:43] **Adam:** How

[00:01:43] **Tim:** So, I mean, so what, what's so great about

[00:01:46] **Tim:** selt?

[00:01:47] **Adam:** Oh. What's so great about

[00:01:48] **Tim:** What are you loving about it?

[00:01:49] **Adam:** so the thing that I love about spelt is that the way that you organize your components just makes perfect sense to me. I've, for the last year or so, I've kind of like been. On the side of CSS in js makes sense, right?

[00:02:04] **Adam:** So you write like react components and have some sort of CSS solution baked into your components instead of having separate CSS files. and there's a couple of different solutions for that, and it's kind of a polarizing, topic really. You know, people tend to either love it or hate it. And I came down on the side of love it because for me, I wanna open a single file and look, okay, here's everything I need, need to know about my component.

[00:02:26] **Adam:** There's the, the logic about it, the dumb structure, right? The HTML and the styling all in one place. And, the, so CSS and JS with like something like React or View, that felt like a, a step in the right direction to me, felt, seems like it's the exact same, you know, you're moving in the same direction.

[00:02:47] **Adam:** Just going further. so sel, if I can summarize it quickly, is basically, It compiles the code that you write. So it's, it's, it doesn't have to be pure JavaScript, or anything like that. It actually kind of looks like an HTML file, right? You've got a script block at the top, you write some JavaScript in there.

[00:03:03] **Adam:** You've got what looks like HTML in the middle with a little bit of, just a tiny bit of dsl, mixed in. And then you've got a style block at the bottom and you just write components this way. And the, the thing that I love about this the most is that when you delete a component, cuz you no longer need it, it takes the style with it, it takes the JavaScript with it, right?

[00:03:23] **Adam:** You don't have to go trick track down, all this ancillary stuff and is it safe to delete this? I don't know, maybe let's try it and see if anything breaks. so yeah, it, it just makes perfect sense to me. And then the, the, because felt is compiled, it can be a very te language and then it, kind of adds it, The compiler adds in all the complexity that you have to kind of do manually when you're doing something like.

[00:03:45] **Adam:** So modern versions of React, you have to use hooks, right? So you've got these use effect and use state and use ref and all these other hooks and they're very complex things to think about. And with spelt, it's not really that complex at all.

[00:04:00] **Ben:** I'm not gonna go on a, on a React rant for a second, but,I think when I think about spelt and I started to play around a little bit with spelt, they have a really cool, like step by step interactive tutorial where

[00:04:10] **Ben:** it's like you're, they have little, almost like a code pen, kind of, here's the thing you do on the top, and then here's the output on the bottom.

[00:04:17] **Ben:** I started to work through that. It seems interesting, but, but I, I think, I don't yet have my head wrapped around at all If this is more user facing, more likely I'm sprinkling. JavaScript into something that might otherwise be a relatively flat experience, or is this something that you would really build into, say like an administrative backend that's more of like a single page application feel?

[00:04:42] **Adam:** spelt itself, was written originally by a guy who worked at the New York Times to create little, like interactive, demos of the concepts from the articles. Yeah, yeah, exactly. Islands. And right, so you're thinking, you know, a newspaper article, it's mostly text, right? And then there's little bits of interactivity throughout or whatever.

[00:05:01] **Adam:** and so that was where Felt was born. and more recently, they have also created spelt kit, which is like, it's sort of like the next JS version of spelt or, or spelt answer to Next js. So it's the full Stack frameworks spelt itself, with client side only, and then spelt Kit allows you to do server side rendering and the full stack.

[00:05:24] **Ben:** Gotcha. Yeah, it's definitely something I wanna play around with. Everyone who uses it seems to love, it seems worth an investigation.

[00:05:31] **Adam:** Absolutely. And so you mentioned the islands. It's funny. that's kind of the, so that's the name of the branch that I've been working in is spelt Islands. so we have this one feature that's been just like this thorn in our side for a while because it was one of the first things that we implemented.

[00:05:49] **Adam:** And it's extremely complex and it's very dense. There's a lot of information packed into this one little feature. It's extremely heavily cashed because there's a crap load of data that gets like, brought down. So we have like, basically we have a view in our monolith that spits out, several megabytes of JSON data.

[00:06:09] **Adam:** and then we, you know, put in all the caching headers and, all kinds of extra. We go, we jump through a whole bunch of hoops to make sure that you're gonna have to download that as infrequently as possible. And then also that when we need to, we can force the cash to clear, And it is just such a thorn in our side because there are sometimes that we want it to clear quickly and sometimes that we don't.

[00:06:29] **Adam:** and also, you know, your first hit to that page takes forever because you have to download megs and megs of, json data to be able to load this interface. and so we're making it, this, this basically, I'm replacing a whole, it's crazy when I say it is all this data, all this interactivity is baked into one little modal.

[00:06:48] **Adam:** you know, it's got, and there's like tabs down the side of the modal, and then, you know, inside of each tab you can

[00:06:54] **Ben:** I feel like

[00:06:55] **Ben:** we've all built something like that.

[00:06:56] **Adam:** oh, yeah, yeah, dozens. Like inside of each tab there's a select and, and each, and that select can have like dozens or, you know, maybe 20, 30 options in it. And then when you select one of those things in the dropdown, then that changes everything else inside the, the what's left visible of the mole.

[00:07:12] **Adam:** it's very complex and, and, yeah, so. Right. For disruption. And, and so I'm, I'm writing spelt and it's, and it's crazy because this, this monolith is written at Bootstrap and like common JS bundles and J Query and I am jumping through a few hoops here to basically create a diiv inside that model. And I'm recreating the all the modal contents, using selt.

[00:07:39] **Adam:** It's a little weird to like selt then create bootstrap stuff. And, it, it feels wrong, but at the same time, like it's working. So

[00:07:46] **Ben:** Very cool. All right, so if I can just go on like a really. React ran for a second

[00:07:52] **Adam:** you

[00:07:53] **Tim:** This ain't about React. we're

[00:07:54] **Tim:** talking, we're talking.

[00:07:55] **Adam:** you wouldn't.

[00:07:56] **Ben:** no, no, no. I, I said I wouldn't for a moment. , I, I, So, I'm, I'm sure many of you have heard of a Asani. He's a

[00:08:04] **Ben:** a Google developer. he's, he's very well known and he and, this woman, Lydia Haley, released this patterns.dev, which I think is, I don't know if it's part of Google.

[00:08:15] **Ben:** Cause they, I think Google has a bunch of dev sites. Anyway, they have a, basically what amounts to a learning design patterns, but in the context of React. and, and it's a pretty significantly in depth book. It's like 430 pages or something. It's, it's intense and it's, it's free though. So that's pretty amazing.

[00:08:35] **Ben:** and so I, I, I to say that I read it is like in the loosest sense of the word, I think I read maybe like the first a hundred pages and then skim the rest. And, and mostly the skimming was because I just, I don't do react, so it didn't, like, I didn't wanna spend too much time on it. But I'll tell you man, when he starts to talk about hooks, this is, So you brought up hooks.

[00:08:58] **Ben:** That's the only reason that popped into my head. So it brings up hooks and he is talking about, oh, before, before functional components and before hooks, we had class based components in React. And you had all these like, Component will mount, component will Unmount, or did Mount, I don't know the names.

[00:09:11] **Ben:** I'm not a React developer here. And, and I'm so used to lifecycle hooks, lifecycle methods like framework one on the ColdFusion side. We can have before and after and, and all that kind of stuff. And then obviously Angular is very heavy on classes and, and life cycle methods there as well. So then he compares, he's like, Oh, this is the 150 lines it would take to do this in a class based component.

[00:09:37] **Ben:** And here's like the 12 lines. It would take. To do it with hooks. But I'll tell you, man, looking at hooks, if you don't have a really strong grasp of what hooks does, it's like line of magic that feeds into next line of magic, which is dependency on the next line of magic. And then suddenly everything just renders.

[00:09:54] **Ben:** And it's like, it's like I couldn't even point to the code and be like, this is where the logic is happening. Like, I don't even know where the logic is happening. It's, I, I, I sometimes think that the people who are so deep in that world

[00:10:07] **Ben:** forget how magical that stuff is. And, and they, I don't know if I'm just so unfamiliar with it that it seems so crazy, not crazy, so foreign and so unintuitive, but, I dunno, you just get so mired in, in, in how things work that maybe I think you forget a little bit that it's not so obvious to everyone else.

[00:10:28] **Adam:** I'm gonna have to search through my YouTube history here. There's a, great, conference talk that I saw where a guy basically re implements react from scratch, by writing what looks like it should be a React app, but not importing React, and then like creating his own version of React that satisfies the requirements of being able to run the app.

[00:10:47] **Adam:** And so, and so basically he kind of describes some of some hooks like state and I think, it might might just be you state, but there some of the hooks, From first principles, right? So like, okay, we, we've got this, you state thing here, how we make it, do what we wanna do. And by going through and implementing it, you kinda see why it has the restrictions that it does.

[00:11:08] **Adam:** Like you can't use it inside of an if statement, it has to be in the root

[00:11:11] **Ben:** Right, right,

[00:11:12] **Adam:** component or

[00:11:13] **Ben:** It's just super, it's super interesting. I don't quite get it, but people love it. Although, I'll tell you, and again, this is not just a hit on react, I'm just, I watch from the outside,

[00:11:24] **Ben:** but it does seem like there's been this now. Divergence where the React community appears to be losing people. Like there, there are people now, from what I see, again, this is basically just from listening to podcasts. So

[00:11:40] **Ben:** I'm very

[00:11:40] **Tim:** they going to spelt?

[00:11:42] **Ben:** I, a lot of people are going to spell, a lot of people are going to view, I think there, there are a lot of people who are like, it, it, it's now taken me, you know, hundreds of lines of code to solve problems that react introduced in the first place that I could have just solved, like in a much more straightforward way using something else.

[00:11:59] **Ben:** And it's, it's almost like react, become its own

[00:12:02] **Ben:** reason for being. I'm,

[00:12:03] **Adam:** say. I mean, it's not like Angular doesn't have the

[00:12:07] **Ben:** no, I'm hundred percent. I'm just saying, I think, I think people are, I think the, the shininess of React appears to be starting to wear off a little bit.

[00:12:17] **Adam:** Yeah. So I found the talk, it's called Deconstructing React by Tejas Kumar. and I, I. We'll put a link to it in the show notes.

[00:12:26] **Tim:** Cool.

[00:12:27] **Ben:** Done. I'm done with my rant,

[00:12:29] **Adam:** rant over.

[00:12:30] **Tim:** That's good. Your time for try and prevail.

[00:12:32] **Adam:** yeah. What do you got going on?

## [00:12:34] Ben's Double Fail

[00:12:34] **Tim:** I I'm go double here.Oh no.

[00:12:37] **Ben:** Yeah.

[00:12:38] **Tim:** Boom, boom, boom.

[00:12:39] **Tim:** boom.

[00:12:47] **Ben:** sound so morbid. I just been feeling like I'm running out of time just with everything in my life. With work, with physical health, with, with my dog. I just like everything. I feel like, I just feel like I don't have enough time to do things. I don't have enough time to, I don't know, I can't even articulate it.

[00:13:12] **Ben:** It just, it just feels like I'm running out of time

[00:13:15] **Tim:** Is it that you're super busy or do you just, you just feel like things are coming to an end in general?

[00:13:22] **Ben:** I think, the end of the legacy platform at work is probably a huge part of it, and that makes it feel, that just exacerbates every other anxiety that I have. so there's the ending of the, of of that. There's, there's just, I've been having some, a lot of knee pain and some shoulder pain and some wrist pain.

[00:13:39] **Ben:** I feel like, I feel like my body's falling apart a little bit and I, I just, I watch my emails just ama and I can't seem to motivate to reply to anybody and, and, and follow through on things. And then we know we moved to a house, a new house in July and, and it's just like, I can't motivate to do anything here.

[00:14:00] **Ben:** Like I, I know I have to fix some things and, and start to organize and figure out, you know, if we wanna do anything around the house, like any improvements and, and just like everything, I, I feel so overwhelmed and I don't know how to, I don't know how to move forward. I almost feel like I need to just take out a giant whiteboard and write down all the things that give me this anxiety and just start picking one at a time and trying to do something about it.

[00:14:27] **Ben:** Cause right now it's just, it's just swirling around in my head and I don't know how to, It just feels, it feels overwhelming and I don't know how to deal with it effectively.

[00:14:36] **Tim:** Didn't buddy, it sounds like you're depressed.

[00:14:38] **Ben:** I, I

[00:14:38] **Ben:** do feel depressed sometimes. Yeah. I, I, it does, it does feel like depression sometimes, for sure. But then I have really good days sometimes,

[00:14:47] **Ben:** But that's, yeah.

[00:14:50] **Adam:** for anybody else, I mean also for your benefit if it helps, but for anybody else that's listening that might feel the same way, start by going to your primary care doctor, and explain the situation. They'll probably do a, like a questionnaire with you to, it's like a depression assessment sort of thing.

[00:15:05] **Ben:** Just a bunch of simple questions. You rate how often you feel that way. and then based on like the total score, they may or may not, you know, prescribe you antidepressants and they may recommend that you see a therapist. I

[00:15:18] **Ben:** actually have a physical coming up

[00:15:19] **Adam:** Yeah. I, I'm on antidepressants and I have done therapy and both have helped me tremendously and I hate the stigma associated with it, and I'm not afraid to, to tell people like, it's so helpful.

[00:15:33] **Tim:** I mean, if you can get it covered by your insurance and you can or can afford it, therapy is a wonderful thing. I mean, it can help, even if you don't maybe even need medication, just be able to talk to someone who's a professional to kind of help you unpackcuz everything you said there was, was emotional based, right?

[00:15:50] **Tim:** It

[00:15:50] **Tim:** was all coming from place of emotion. it, they'll help you sort out, you know, what is just fear and emotion and what is actually factual based and then you can attack the actual problem rather than just feeling the feeling. It really helps. So,

[00:16:06] **Ben:** Uh, I'll

[00:16:07] **Tim:** got a physical coming up. Definitely take Adam's advice there.

[00:16:10] **Ben:** my, my wife's been trying to find a therapist. She's been, she's seen therapists on and off for years, and, and she said it's been really, really challenging to find people. Like, she'll find a place locally and she'll go talk to them and they say they're not accepting new patients

[00:16:24] **Tim:** There's a huge shortage right now.

[00:16:28] **Ben:** one failure. And the other failure,

[00:16:31] **Tim:** one?

[00:16:32] **Ben:** double whammy, which in a way feeds into this one only because I, I, get so frustrated. So there are things that I do on a day to day basis at work that I feel really confident about and, and I feel like I'm continuing to get better in a lot of ways.

[00:16:49] **Ben:** And I'm, I'm psyched about that. Pretty, pretty stoked. But there are things that just continue to feel challenging and I never, I don't, There are, there are a lot of things at work that I just don't feel like I'm getting better at, and every time I go to work on them, I don't know. I, I feel like I'm just solving the problem slightly differently in a new way each time because nothing feels right.

[00:17:10] **Ben:** and I hate that. I, I, I hate the fact that certain things just elude me. It, it. It feels like there's just some mental block. I'm, I'm not, I don't know how to get past, like I'm working right now on, on cascading deletes

[00:17:24] **Adam:** In the database.

[00:17:25] **Ben:** data, yes, but not at the database level. Meaning the thing that I'm working on right now is, is deleting an entire user from the system and the user owns a bunch of things and those things are containers for lots of other things.

[00:17:40] **Ben:** And all those things can be individually deleted by the user themselves. So there's all kinds of different ways that a deletion of a thing can happen, or I should say that that's how our system is built and, and figuring out how to then initiate a delete from the, the next level up so that all those other things become deleted.

[00:18:01] **Ben:** And it happens in a performer way, meaning not just like the user doesn't click and see a spinner for three minutes while I'm, you know, busy deleting tens of thousands of, of various cascading records. and I, I don't know, like I just, I've, you know, been deleting data for 20 years and, and it still feels like every time I go to do something other than a basic crud level, like I'm deleting this one record, it's like I just, I don't have a strategy and it, and it really bothers me and it, it makes me feel like not a dufu, right?

[00:18:33] **Ben:** I mean, it's a complex problem, but I just, I get very frustrated that, I don't have a plan and I'm just throwing stuff at the wall and seeing what sticks.

[00:18:43] **Adam:** Sounds like the type of thing that would be tempting to hunt for a general solution, but it's probably not worth finding a general solution for, Right? Unless you're talking about, you know, something that's gonna go literally 30, 40, you know, layers deep, right? User deletes this, deletes that, that 40 times, unless it's like that, you know, you're probably better off just, okay, what needs to be deleted when I delete a user and hard code those things in and, you know, do that however far down the, the stack of turtles that you have to go.

[00:19:17] **Adam:** and.

[00:19:19] **Ben:** that's, that's more or less the strategy that I'm taking. but this is where, so we had talked a little bit on, on the pre-show about technical debt. And this is where,

[00:19:27] **Tim:** There's no pre-show just to be, This is just before we started recording. Just so you know, your patrons aren't missing out or anything. There's no pre-show subscription

[00:19:35] **Ben:** There's no double secret pre-show

[00:19:37] **Tim:** Yeah. Sorry.

[00:19:38] **Tim:** first rule pre-show. You don't talk about pre-show.

[00:19:42] **Ben:** And this is, it's one of those things where if you could build it all from scratch, then maybe it would work, right? But there's so much crush that's been built into the system over the years

[00:19:54] **Ben:** that you're like, Oh, I'll just call this method because it's doing a lot of the delete that I'm worried about.

[00:19:59] **Ben:** And then you look in that method and it has all kinds of weird logic that's you're like, Oh, that shouldn't be here. That's unrelated. Or it's like only peripheral related in certain edge cases. Like that should really be somewhere else and orchestrated somehow. But

[00:20:12] **Ben:** I,

[00:20:12] **Tim:** Has

[00:20:13] **Tim:** definitely a tech debt.

[00:20:14] **Ben:** yeah, yeah, yeah. So, so that's, that's my, that's my second failure.

[00:20:17] **Ben:** Just that there are things that continue to be hard. No matter how many times I try to solve that problem, I just never come up with something that feels like, ah, this was the right way. Finally, I figured it out. Just continues to be hard every time. So anyway. Tim, what about you? Welcome back, Tim

## [00:20:35] Tim's Triumph

[00:20:35] **Tim:** Well, hey. Hey. Thanks. Good to be back. Yeah. So sorry to after that emotional outpouring to come up back with a triumph here. I

[00:20:43] **Tim:** feel bad

[00:20:43] **Adam:** we're gonna do a, a turt sandwich here.

[00:20:46] **Tim:** right? Yeah. Got tar sandwich. But yeah, so this is my first show back after, 10 days in London and it was fantastic. got, was there for London for work. We have a, a leadership conference for our, you know, our parent company, Polaris, which, so there's like 1200 people.

[00:21:04] **Tim:** We had a entire hotel and you know, London, and, we call it the quadrants. So, basically it's like they're just getting people together to network and like best practices as far as companies go, but got flew in a little early so I could visit my family. So I've got some family that live. In England, but most of them are not in London anymore.

[00:21:24] **Tim:** So a cousin got to hang out with him, haven't seen him in 20 something years and gave him a bunch of hot sauces. We did our own little hot ones challenge at the pub at Wetherspoons. People were like watching us. Yeah, I, I blew his taste buds out and then, and then also got to meet Adam Cameron. No, of course I've met him before and over here, but, you know, he came, came down to visit me.

[00:21:46] **Tim:** Our, our, my number one, our number one hater here on the show,

[00:21:49] **Tim:** although we got along so well. I don't know if we still qualify as haters anymore cuz he's really a, a lovely, lovely guy. Just had a

[00:21:56] **Tim:** really good time chat with

[00:21:57] **Adam:** did did you eat after midnight with him or get him wet?

[00:22:03] **Tim:** I don't know if I got 'em wet, but we definitely ate before midnight. So But no,

[00:22:09] **Tim:** we had a nice time,

[00:22:10] **Ben:** picturing Carol having no idea what that was a reference to.

[00:22:13] **Tim:** you know Exactly. Carol's like, I don't get

[00:22:15] **Ben:** Why would you get him? We.

[00:22:19] **Tim:** No, but that, that was that. So that was super fun. But, yeah, one thing I find odd, so this, this is a, so our valis is part of Constellation Software, which is a huge company that all they do is they buy software companies. And so vertical software companies, these are companies that are not anything you would ever hear of.

[00:22:36] **Tim:** These are, we sell to businesses and we like help run their business. And, it's like there was very little topics that dealt with code quality, which bothered me. There's a whole lot of like, you know, how to get your, your, all these, we have all these ratios, you know, your core ratio, your, your ebida, your ebida B, how to get all, you know, it's all, it's a whole lot of like moving numbers around to try to like get to your numbers.

[00:23:02] **Tim:** But it's like at the end of the day, we're all software companies. If you have good software, it should be much easier to sell good software and to make money off good software. so. Little surprised that there wasn't more content along that regards. They do probably have, I know they have other conferences that deal directly with that.

[00:23:18] **Tim:** but yeah, I just, I think at a software company, you really should, number one job should be delivery good software. Not, not budgeting

[00:23:27] **Adam:** do, do you get the opportunity, I don't know like how you personally fit into the org structure there, but like do, would you have the opportunity to put your thumb on the scale and suggest, or, or even volunteer some software craftsmanship level content for like next

[00:23:43] **Tim:** Yeah. And probably in the future I will record cuz they do like sort of a call for, you know, what do you wanna talk about?

[00:23:48] **Tim:** And, and you get to, to moderate on it. So yeah, next year it, you know, if I, if I go, I will probably suggest some of those things that gotta, you know, just encourage that. Best practices behavior of, you know, are you guys even testing?

[00:24:04] **Tim:** I mean some of these companies are writing really old languages. You know, their, their, their job is to try to squeeze as much money out of it as they can. They much rather, you just squeeze much money out of the current product you have. And then if you need a new product, cuz it's failing, it was like in cold ball or something, we'll just go buy another company that's newer.

[00:24:22] **Tim:** Right. And put 'em under you and yeah, I mean that's sort of the strategy, right? We'll just buy another, another company that's doing it better and then, then there you go. So it's a very different

[00:24:33] **Tim:** mindset.

[00:24:35] **Adam:** that was not where I expected that to go at all. You were talking about like, okay, well when it starts to die, that then you, that then you take on the rewrite or something, and then

[00:24:42] **Tim:** No, you don't take, Yeah, they hate rewrites. I mean that's, that's still the mantra. They're like, just keep putting lipstick on a pig as long as it's making money. And then if, if it stops making money, we'll just, we'll just spend them, you know, we'll spend a few million dollars and buy another, a company that's, you know, doing it right, doing it better than you, and then make it part of your portfolio and just move all your customers to them.

[00:25:01] **Tim:** It's a very different

[00:25:02] **Tim:** kind of gig. It's, it's interesting when you have huge amounts of capital to play with, what the, your mindset's like, Oh, well, why should we spend like the next two years trying to write something? Well, we'll just, we'll just buy something that's already doing it. Just buy another company.

[00:25:17] **Tim:** I mean, they recently bought a company down in South Africa, who they're projecting the next couple years will be 1.4 billion in net revenue.

[00:25:27] **Ben:** Dang

[00:25:28] **Tim:** So, and that's just a slice of a tiny part of the company that, that they're part of that makes it up. So it's very different level. So I, I guess maybe that's kind why they focus on that.

[00:25:39] **Tim:** But at the end of the day, I'm, I'm just like, we're all software companies. Let's, let's, let's make good software. It's not gonna hurt.

[00:25:48] **Adam:** Yeah.

[00:25:49] **Tim:** They're not gonna hurt the bottom line. ,

[00:25:51] **Adam:** and I mean, you know, taking good care of the software that you got now will make it last longer.

[00:25:56] **Tim:** yeah, there were several tracks on technical debt, which we were thinking about talking about tonight. But, there were some good tracks on technical debt. and we, we've been building these best practices, playbooks, and I've talked about, how to build an honest roadmap. In the earlier show,

[00:26:08] **Tim:** we we presented our roadmap, paper, to the group and got, got good results.

[00:26:13] **Tim:** and a lot of the paper was talking about putting technical debt as part of your software roadmap, of making sure that 20% of your, your roadmap is like dealing with technical debt. So I felt that was good that we, you know, kept that in front of people.

[00:26:28] **Ben:** Very cool. How many people go to this conference? Just for my

[00:26:31] **Tim:** There was, 1200 people.

[00:26:33] **Ben:** Oh, that's pretty sizable.

[00:26:35] **Tim:** Yeah. Yeah.

[00:26:36] **Tim:** So it's pretty good size from all over the world. I mean, people from Australia, people from South America, people from Africa, I mean, pretty much every continent except Antarctica was represented. So,

## [00:26:48] I Can Articulate The Problem

[00:26:48] **Adam:** Cool. So our topic today, expectations of professional software engineers. Tim, you sent this link to us and you seem to have probably had the best read of it, amongst the three of us. So where do you wanna go with this?

[00:27:02] **Tim:** Yeah, so I just wanna kind of preface this. This is not like best coding practices. This is sort of about being a professional software engineer. So it's like coding is just a tiny part of that. It's about how to be good at your job overall, beyond just the, the chops of, you know, writing good tests, writing good code, things like that.

[00:27:22] **Tim:** And the, the article, is Adam Johnson, but he is referring to a talk given by Mike Acton. So Mike Acton is, from a, a video game development background. most of this is applicable to what we do. but just gotta realize he's coming from a video game background and when he starts talking about platforms and those sort of things, hardware considerations, that's the world he's coming from there. But I just, I thought it was interesting cuz It's a bunch of those, it's like 50 I statements, so I can do this, or I have confirmed, or I can explain, 50 things that, that you should be able to positively say that you do. And so the first few are really a whole lot about, articulating the problem and understanding the issue that that's being worked on.

[00:28:09] **Tim:** So like for instance, number one, I can articulate precisely what problem I am trying to resolve, right? And that seems pretty simple, but I mean, how many times, you know, sometimes maybe it's just some sort of bug

[00:28:22] **Tim:** and you're just trying to make the bug go away, but you really don't have a good grasp of, what is the issue I'm trying to solve?

[00:28:28] **Tim:** We kinda get stuck in the weeds. What's the goal? and is there an alternative path?

[00:28:33] **Adam:** See? Yeah, I, I like this one. I think I would also, maybe a slightly different perspective would be like, I'm not just implementing whatever spec was handed to me. Like I understand

[00:28:43] **Tim:** Right. Yeah.

[00:28:45] **Ben:** I would go so far though as to say that sometimes, maybe a lot of the time it's unclear. I don't even know if I'm solving a problem, meaning I, I, I have an inkling that something is wrong and I have an inkling that I can do something to help alleviate that possible point of friction. But I, and I don't really know, and I don't have a, a hoard of users that I can just ask and I don't want go to the product people cause they'll just shoot me down.

[00:29:14] **Ben:** So, a lot of

[00:29:17] **Adam:** Is, is this the point where we admit that Ben is actually a machine learning algorithm or.

[00:29:26] **Ben:** but literally I will. I'm like, I, I, for me, it's always weighing the, potential value against the potential level of effort. So if I can look at something and say, Hey, I can, I can code something that might attack this problem in a couple of hours. I, to some degree, like, I almost don't even care if it's gonna add value because it's, it's such a low risk.

[00:29:48] **Ben:** So sometimes I'll build something and I can't even really clearly articulate what value it's gonna have, and I just wanna put it out there and see if anyone starts to use it. And then sometimes you build something and you start to play around with it, and, and just having it on the screen in front of you kind of seeds, new ideas, and then you can start to solve different problems based on that.

[00:30:10] **Ben:** So I, I don't know if that's a great use of time per se, but, but definitely there are, there are moments not infrequently where I'm, I'm solving a problem that I can't articulate, but I'm not against that makes

[00:30:24] **Adam:** Yeah, I think what you're describing sounds like a creative exercise, right? Not so much like a, a bug squashing, but just like a, there might be room for improvement here, a better tool or, or something useful, but we don't exactly know what it is yet until we

[00:30:39] **Ben:** Right, exactly.

[00:30:41] **Tim:** Yeah, I, I can't tell you how many times, like I start working on a problem, and at the beginning I have it kind of clear in my head, Here's the problem I'm trying to solve. And then I start getting caught in these code corners, and then I start my, my shift goes to fixing those problems. And then I wind up in the rabbit hole and I realized that I, and I back out and go, Wait, wait, wait.

[00:31:00] **Tim:** This really isn't solving the problem I'm dealing with right here. I'm just, I'm just trying to overcome this hurdle here. This hurdle really maybe has nothing to do with the actual problem I'm dealing with, and I gotta back out, cut a bunch of code out and then, you know, attack the actual problem I'm trying to solve and love.

[00:31:18] **Tim:** So, if you're dealing with customer support, let's say that, you know, people. And this happens tons of times. People will say, Oh, I'm getting this problem whenever I do this, this happens. Or like, All right. So, and then they will try to suggest a solution, right? So can, like, tons of times I'll get, we'll get customer support tickets.

[00:31:35] **Tim:** Like, can you make this, do this? And you gotta back 'em. Say all wait, wait, what are you trying to solve here? What's the actual problem? What are you trying to do? And then when you find out what they're actually trying to do, you're like, No, no. There's a completely different way we need to go about this than, than, than doing what you're asking to do.

[00:31:51] **Ben:** Yeah. Yeah, that, although that I have, in my experience, I could say that that is occasionally taken to the extreme. where I've been very, almost, I almost refuse to give users what they're asking for to the point where we don't solve the problem at all. And I could've just given them the thing that they were asking for and they would've been happy.

[00:32:16] **Ben:** But it's like I was so against that, that we ended up not doing anything. so I, I agree with you in the vast majority of cases, but I think there are times when sometimes users just just want the thing that they want and, and there's, there's no placating them.

[00:32:32]

## [00:32:32] I Have Articulated The Problem

[00:32:32] **Tim:** And I think there's the communication. So the second one is about I've, I have articulated precisely what problem I'm trying to solve. And so if you're on a team, this is particularly useful. So like at our standup, a lot of times, I'll ask, you know, people, what are, you know, what are you working on getting these roadblock?

[00:32:49] **Tim:** Things like that. And they'll talk about kind of what they're doing and the strategies they're trying to do to implement something. But I think sometimes it's good to just, you know, say, All right, so you, you're doing X, Y, Z using this methodology. You know, what is it again, we're trying to solve? And it, sometimes I sound a little stupid in the standup cuz it's like, I obviously should know what they're working on,

[00:33:13] **Tim:** But it's like, alright, so what is it you here you're trying to solve? and you're like, okay, so we're trying to do dual factor authentication kind of thing. All right. So does that really align with the strategies you have in place?

[00:33:25] **Adam:** Yeah, I like how the first couple on this list are like, I can articulate precisely what the problem is. I have. I can, I've confirmed that somebody else can articulate it. It's all about like knowing the problem and communicating well amongst the team. I

[00:33:39] **Adam:** think

## [00:33:40] How Much Is The Problem Worth Solving

[00:33:40] **Tim:** And number number five is big. It's like I can articulate how much my problem is worth solving,

[00:33:45] **Adam:** mm-hmm.

[00:33:46] **Tim:** Lot, lot of times, sometimes we just kind of get hung up on a pet peeve and, and this, Mike Agne says, If you say it's it's worth as long as it takes, he's not gonna have any nice words for you.

[00:33:57] **Tim:** So, I mean, you have to say, what is the maximum amount of effort and time and effort we're gonna do with this problem? Sometimes, sometimes you gotta cut it off and say, All right, if I'm gonna spend this much time try to solve this problem, and this problem may be affects, like less than a percent of of users maybe need to rethink your, your actions. That that's not an effective use of time.

[00:34:22] **Ben:** It's hard sometimes though when you're dealing with something more like technical debt where you, you can say that the way that the application or an area of the code is written right now is hard to maintain and it's hard to build new features. But then to ask for time from your product managers, Hey, can I take two weeks, a month or whatever to refactor this area of code?

[00:34:45] **Ben:** And they say, Okay, well, what's that gonna get us? I never know how to answer that question. I can tell them that it'll be easier to make changes in the future, but I don't, I can't, I can't promise them that I, I can't guarantee a value. I can guarantee that it's, it's gonna, I don't know what I can guarantee.

[00:35:04] **Ben:** That's, that's the most frustrating part for me sometimes.

[00:35:07] **Adam:** I feel like I saw something recently that was discussing technical debt and it, it dove into the metaphor of like, borrowing money from a bank. I, I have no idea where I saw this. My best guess is an article on lead dev. but, I, I kind of want to go dig that up because I'm sure that there's something in there that could help you crystallize some thought.

[00:35:32] **Ben:** Hmm.

[00:35:32] **Adam:** man, I wish I could remember.

[00:35:33] **Ben:** It'd be easier to articulate if there was a big thing that was being prevented. From the technical debt, like, Oh, I'd love to build feature xyz, but I can't because it's so complicated right now.

[00:35:45] **Ben:** Cuz then at least you could look to feature XYZ and say, Here's the value that we think this will have and let's remove the blockers.

[00:35:51] **Ben:** But if there's just this general sense, everything in this area of the code is just hard to work on just period and, and you might not have anything that you're supposed to be working on in there, but you know that things might come up in the future or just by refactoring the code. Again, there's a sort of evolutionary creative process where while I'm refactoring it, I might generate new ideas as I'm putting the code together.

[00:36:16] **Ben:** It's tough. There's,

[00:36:17] **Ben:** there's

[00:36:18] **Ben:** a lot of fuzziness when it comes to value add

[00:36:20] **Adam:** So who among us doesn't have that one file or that one function? That, or that one feature? Nobody wants to touch. Right? Like everybody's scared of it because if they, if they put their fingers in there, then the, the, you know, it's just gonna fall apart and everybody's gonna be mad at them. I think if, like, if you had the opportunity to refactor that and improve it, then that's, and, and like, if you can guarantee, like, okay, well it's not gonna, My goal is to, to not change the functionality of the feature at all, but I wanna make it so that nobody's scared to

[00:36:55] **Adam:** fix bugs that are in it.

[00:36:57] **Adam:** Like that would be awesome. I don't know how you state that value in, in like a business way. Hmm.

[00:37:04] **Ben:** It's so hard.

## [00:37:05] I Can Articulate Unknowns in Risk Associated With My Problem

[00:37:05] **Tim:** Here's one that, I mean, this is probably for me the hardest. number nine, I can clearly articulate unknowns in risk associated with my current problem. So the reason that's hard is if I can articulate it, obviously it's not unknown to me

[00:37:20] **Adam:** Well, there's, there's, there's known knowns, there's known unknowns, and there's unknown unknowns. It's the

[00:37:26] **Tim:** yeah, the known unknowns. Yeah. Okay. Yeah, I can agree with that. But yeah, there's some parts of it's like, how come you didn't know that? It's like, because it didn't happen when I

[00:37:37] **Tim:** was testing it out and Right. But yeah, I mean, so there might be some black boxes and things that you don't really fully know how those black boxes that you're talking to react, that I can, you know, say are unknowns.

[00:37:50] **Tim:** They're known unknowns. But yeah, there's no way to know every unknown.

[00:37:56] **Adam:** I agree. And also I think that, you know, the point of this one is to encourage us to take a minute, take a breath, think about the problem. You know, take the time to go, Okay, well what could be an unknown here? Cause I, I don't know about you, but personally, I, when I'm attacking a problem, I get the problem, I understand the problem, and I immediately, my brain just wants to go, Okay, like, here's the code, here's the fix, write it, go fingers.

[00:38:27] **Adam:** Just have to keep up with brain. and I think that this, this point, this list item is about, you know, when we're talking about, expectations of professional software engineers, you know that, I think that expectation is that you have the patience and the discipline to think deeply about the problem.

[00:38:44] **Adam:** I guess for a bigger problem that's worth thinking deeply about, right? Like, if there's a typo, you don't even have to think deeply about that. But, know, take the, have the discipline and the patients to think deeply about the problem before you try to attack it, because, you know, doing that might help you come up with a better solution, might identify the unknowns that are going to change the way you approach the problem, or, or stop you from doing it all together.

[00:39:07] **Adam:** Right? Like you figure out that we can't do this because we're missing this or whatever,

[00:39:14] **Ben:** I find, I know a lot of people don't like creating tickets for their work, or, I know Carol has talked about taking screenshots of conversations to put them in tickets.

[00:39:24] **Ben:** I, I find that I will sit down and I'll just write out the ticket titles and I'll, I'll write, like, I'll create like 20 tickets in a row, and I don't put any descriptions in them at all.

[00:39:34] **Ben:** It's just, it's just like the one in Jira. So in Jira, maybe to be more specifically, there's a title for the card and then there's a description. And a lot of times what I wanna do, I'll just put in the title as a little sentence. And just the act, to your point of sitting down and sort of closing my eyes and thinking about the steps that I want to take it, it makes the entire problem seem so much more approachable.

[00:39:59] **Ben:** You know, on the onset it feels overwhelming. Like, Oh, there's so much work we're gonna have to get done. And then by the time you've written out just the, you know, the one liners for 25 different tickets, you're like, Oh, all right. I see the path forward. We got this

[00:40:13] **Adam:** Hyundai p

## [00:40:18] I Can't Make Up The Time Without Talking To Someone

[00:40:18] **Tim:** But here's one that I a hundred percent agree with. I have not thought or said I can just make up the time without immediately talking to someone. So the situation, the context here is, you got something to do on Friday. It's Wednesday, and someone drops a new task in your lap, you know, that's complete, a complete total inject, and you think, Oh, I can just make up the time this says, you know, stop right now.

[00:40:42] **Tim:** Talk to your product, talk to your product manager and help manage the timing and risk because you're like, Oh, I can just, I wasn't expecting this, but it's new thing. I'm gonna just do it. I'll make it up later. you probably won't.

[00:40:53] **Ben:** Yeah, well, sort of dovetailing with this, there's been a lot of talk on podcasts that I've been listening to lately about, stigmatizing hero culture. And, and this actually goes back a little bit to the, the Phoenix Project, which was a, an audio book that we talked about like a year ago. And how historically we celebrate the people.

[00:41:12] **Ben:** They're like, Oh, so and so worked all night to get everything done. You're like, Oh, what was so amazing? Like, what a, what a, you know, coding ninja. And they're like, No, that's terrible. We shouldn't, we shouldn't ever celebrate anything like that. That should be frowned upon. And if someone has to work all night to get something done, then we should figure out how to not make that ever happen again.

[00:41:31] **Ben:** And, it was funny cuz I was just listening to a podcast the day where they were talking about that. And literally I came in the next morning and I saw in Slack that someone had been up all night trying to solve a problem that had, occurred at like eight o'clock that night. And they were working all night trying to figure it out.

[00:41:48] **Ben:** And then in the, in the all hands meeting that day, they were celebrating this guy. And they're like, Oh. So like, oh, he is really, you know, took one for the team and he was up all night working to, to make things happen. And I was like,

[00:42:00] **Tim:** Hmm.

[00:42:00] **Ben:** like, we're just, we're just trying to make up the time.

[00:42:04] **Tim:** But is that sort of like a live outage kind of thing?

[00:42:09] **Ben:** So that's the thing that bothered me the most about it, is that it wasn't, it, if it couldn't have been solved and the guy went to sleep, life would've went on. Like it wasn't, it's not like we weren't accepting payments or anything like that. Like it was an unnecessary all nighter from, from what I could see.

[00:42:28] **Ben:** And, you know, I think it's, it's, it's, it's hard , it's so hard to not celebrate hero culture and also not sound like you're telling someone that they did the wrong thing. Like it's, it's, I, we appreciate that he did it. I wish that he had chosen not to do it. Kind of a, it's hard to word that. Well, I know if I lose any sleep at all, I'm devastated. So even the idea of working. And to the evening, I'm like, Ugh, it's

[00:42:59] **Tim:** I mean, you didn't even wanna do these podcasts until the in

[00:43:02] **Tim:** the evening. You ready for bed?

[00:43:05] **Ben:** exactly.

[00:43:05] **Tim:**

## [00:43:05] Will You Know When You Have Achieved The Thing You Need To Do

[00:43:05] **Tim:** let's see. So here's another one. Number 12, I can articulate what the test for completion of my current problem is. Now it says test. It doesn't mean like, TDD is basically saying, How do you know when to stop? How do you know when you've achieved? What you've needed to do. And, I mean, I think that one will probably be pretty easy for most people.

[00:43:26] **Tim:** It's like, all right, does it work? Does it return the right thing? Does it pass all the tests? But maybe in the video game, video game world, it's a little different.

[00:43:34] **Adam:** It's funny, when before we started this, I noticed that the word test only appears right there where you just said it. I can articulate with the test for completion of my current problem is. I found it interesting that automated testing doesn't appear on this list considering some of the discussions that we've had on the podcast and in our Discord about how, automated testing in some people's opinion is table stakes for being a professional web developer.

[00:44:01] **Adam:** just, I, I found it interesting

[00:44:03] **Tim:** Yeah.

[00:44:05] **Ben:** Well, I think also what's interesting about this one is that I think it can vary wi widely what is considered to have solved the problem. Meaning these days, because I have so little time on the legacy platform left, I go into everything with a, with the mantra that it's not enough. But not enough is better than nothing.

[00:44:28] **Ben:** And that's very different mindset than someone who's coming in thinking that they have to deliver a highly polished product. And we're both looking at the context, thinking to ourselves, you know what? This is solving the problem, but we're just our, our level of entry, I think our barrier to entry and what that's on, what is on what a solution is, is very different.

[00:44:49] **Ben:** So it, I, I guess like as long as you can articulate it in your context, then, then it's good. But it does, I think it is gonna be very different from situation to situation.

[00:44:59] **Tim:** Yeah, for sure.

## [00:45:01] Is It Falsifiable?

[00:45:01] **Tim:** Now this one I don't understand, so maybe you guys can help me cuz it sounds really like super nerdy and smart. I can articulate the hypothesis related to my problem and how I could falsify it. So if a hypothesis cannot be proven wrong, there's no knowledge to be gained. As Carl Popp showed, Science only works through falsification.

[00:45:21] **Tim:** I have no idea what that means. Way over my.

[00:45:25] **Ben:** To me, this feels like a data question. So at work it, I, I feel like the people who pose hypothesis based stuff at work are, are the data people, and they're, they're looking at funnels and conversions and they're like, If we can get someone to engage, More with this feature, then they're gonna be more likely to be using this feature over the next seven days and they're gonna pull more people into the conversation and there's gonna be some sort of there, there's like this downstream effect to what they're doing.

[00:45:54] **Ben:** So a lot of the stuff they do can be falsified, I think just by looking at the data. Like they say this is the outcome that we're expecting in terms of the numbers, and then you look at the numbers and either the numbers are there or they're not there.

[00:46:07] **Adam:** Right. But at the same time, I think what this is saying is like, if the hypothesis isn't like, let's just use the word crisp, if the hypothesis isn't crisp enough, then it won't be possible to prove it false. And so there's nothing, It it like it, it's almost like it means nothing. Right. Like if the hypothesis is like shade of blue A is better than shade of blue B at getting conversions and like you just can't, If a conversion is, you know, three or four steps away and you can't prove that one, that that's the only factor that changed, that affected them, then then the shade of blue test is you know, not proving what it's trying to prove.

[00:46:52] **Adam:** If that makes sense.

[00:46:54] **Ben:** Well, I think also if you change more than one thing at a

[00:46:59] **Ben:** time, it's hard to tell which thing actually made the difference or if

[00:47:03] **Ben:** they work together to make the difference, that that kind of stuff is challenging.

[00:47:07] **Adam:** Yeah, I was thinking that's exactly where I started thinking and when I stopped talking, isolating variables.

[00:47:14] **Tim:** Yeah, I've seen that. Yeah. Cause there's sometimes we, you know, there's a problem. We deploy a fix, we don't deploy two at the same time. We deploy one to see if and if that one fails, and, you know, you learn something from that, so you deploy the second one. but also it could be like, you know, the hypothesis is that I, you know, I think that by moving this to a certain place, you know, the top right corner where the eye tends to go, I'm gonna get, you know, 20% more up clicks, you know, because of that.

[00:47:44] **Tim:** So you, you move that there, it has to, there has to be a pass or a fail there, right? It can't, it can't be kind of a gray area. It's.

[00:47:50] **Tim:** Yeah.

[00:47:51] **Ben:** It. It's also hard sometimes, and this kind of goes back to being able to articulate the problem that you're trying to solve.

[00:47:58] **Ben:** Sometimes I see at work they'll be saying, Hey, we need more people to try feature A, so we're gonna add this button. Over here that says, try feature A, and then they're like, And then we'll just look at how many people click on that.

[00:48:12] **Ben:** I'm like, But that didn't, that doesn't tell you anything about whether or not people wanna use feature A or if they're gonna come back and use feature A, or if it's, if it's adding value to their day, like you just added a new button that wasn't there before and you wanna see how many people click it.

[00:48:27] **Ben:** Like that's not, there's no problem being solved. So it's, it's

[00:48:31] **Ben:** hard to sometimes bring it back to a, a business proposition too.

## [00:48:37] I Have Watched An Actual User Of My System

[00:48:37] **Tim:** I'm gonna jump a little bit. So this one I have sat and watched an actual user of my system.

[00:48:43] **Tim:** Has anybody ever actually done that?

[00:48:45] **Adam:** yes and no, right? Like, not, not, professional user testing, but I have. well actually, you know, I'm, I'm thinking about my current job, but at previous jobs, and again, not professional user testing, but very hands off, like sort of second degree away. Like, we write the software, we turn it over to somebody else, and they then, implement it and, and have users use it.

[00:49:08] **Adam:** one of my previous jobs we wrote quote unquote simulations and serious games, and, for teaching business concepts, right? So like OPEC or stock market or prisoners dilemma type stuff. so I'm not talking like video games, just like text based sort of web things. And and then we would turn those over to professors at the business school and let them use them with their students.

[00:49:29] **Adam:** And occasionally we got the opportunity to sit in on the class and watch these things happen and see how the students interacted with it and see them learn. I think was part of the, the goal of that exercise. But also, you know, Get the opportunity to see firsthand how the tool helps them reach that learning outcome and, and try to see if we can do a better job of reaching that learning.

[00:49:53] **Ben:** Yeah, that's.

[00:49:54] **Tim:** Yeah. Yeah. So I mean, I will say this is one good thing. So the parent company or part of one of our previous quadrants that we did, they, part of the assignment was they told us to go visit our top two customers. And see how they use our system, actually just go in their office. And we did that. So we went in their office and we actually sat down with like different levels of users, cuz they're all different users, you know, how are you actually using our software?

[00:50:21] **Tim:** And it, I mean it was enlightening. It was like

[00:50:24] **Tim:** we saw people doing these kind of workarounds that were like, why are you doing it that way? They would go, Well if I, if I don't do it this way, then XYZ happens. Like, okay. And it was, it was, I mean it was expensive exercise , but, cause we had like a big group of people there going to this, but we did actually learn something.

[00:50:43] **Tim:** And then also at the same time, you know, they wanted us to like say, find some other business problem that wasn't like part of our software. Like what are they doing in their office that's unrelated to your software that maybe we could build some software to sell to them. So, but, but actually, actually watching a person sit down and click and type and see what they do is, was quite enlightening.

[00:51:04] **Tim:** So

[00:51:06] **Tim:** I don't know if that's a must do, but.

[00:51:08] **Ben:** I find a lot of the time, so I very rarely actually get to see users use our system. The only time I really get to see it is either when I've been asked to join a support call cuz a customer's having a problem and we need to get a bunch of people on the call to see if we can figure it out.

[00:51:23] **Ben:** Or occasionally the, customer facing team, they'll. Snippets of their conversation with their customers to share internally. And it's, I, I love it. I, I really wish it was something that I could weave more into my weekly routine somehow. I don't know what that would look like, but it's, it's, I, I almost don't even care what the users are talking about.

[00:51:45] **Ben:** I just want to hear them talk about the system in any way that they want to, whether it's good things or bad things. They, they'll just say the most random stuff and it'll spark an idea and then the idea becomes a feature later on. And, and you would've never thought to do that cuz you didn't realize that that was a problem someone was having. So that's, it's so that, that's like the, the biggest missing part in my professional career is getting more face time with users. Which is weird to say cuz I don't like dealing with people, but I, I do wish I could somehow not deal with people, but then also deal with more customers.

[00:52:21] **Adam:** Gonna be a fly on the wall.

[00:52:23] **Ben:** It, it is crazy though, you talking about the, the workarounds that users come up with.

[00:52:28] **Ben:** I, it's, it's, almost, it's mind boggling some of the things that they'll come up with and be like, Oh yeah, this, I was trying to generate this Excel document, but it wasn't working. But I found out that if I, like went to the print preview and then I copied the print preview over to Microsoft TextPad, and then I exported that as an, as a rich text document file, and then I could import that into Google Sheets and then export it as an Excel file.

[00:52:53] **Ben:** You're like,

[00:52:54] **Tim:** what?

[00:52:57] **Ben:** you're, But that's,

[00:53:00] **Tim:** Geez.

## [00:53:02] I Know How To Debug Live Builds

[00:53:02] **Tim:** All right. How about this one? I know specifically how I can and will debug live release builds of my work when they fail

[00:53:10] **Adam:** number is that?

[00:53:10] **Ben:** Hmm.

[00:53:11] **Tim:** 30.

[00:53:12] **Adam:** yeah, you know, just remote desktop to prod and edit the code. You know, ftp. And, just, you know, edit and save.

[00:53:21] **Tim:** Send an email. Yeah, email with, with this bug context.

[00:53:26] **Tim:** I I do think that's the big, because cause a lot of times, like your, your production builds might be, you know, somewhat slightly different from your development. It's the whole works on my machine thing. Right? So how are you gonna deal with that?

[00:53:39] **Tim:** Whenever production is like airing, but it works every single place else. How can you, how do, how do you, how do you deal with that?

[00:53:46] **Adam:** Right. So what logs are you gonna look at? You have some sort of a debugger live Shell look at in there.

[00:53:53] **Tim:** Yep. Cause if you don't know how to do that, it's like someone has to do that cuz it's gonna happen.

## [00:54:00] I Know What Hardware My Software Will Be Running On

[00:54:00] **Adam:** wanna, I wanna go back a couple here on the list. number 26, I can articulate the finite set of hardware I'm designing my solution to work for. So, in our context, web development, what I think this means is screen resolution, not only on the desktop, but also on like phones and tablets. I had, a bug come in today that, basically somebody did something dumb in our app, and it, they did it because, A, we didn't stop them from doing it, but b, the place where we were warning them, that they were doing it was just off screen.

[00:54:30] **Adam:** It was like below the fold. and, you know, so the, the solution was easy. It was move the warning up above the fold and, and add some extra valid. you know, it's just because I have a, a gigantic, like 34 inch monitor that I do my development on, and, you know, I, I forgot that, you know, you gotta resize the window and, and treat yourself like somebody with a 24 inch tiny little monitor running 10 24 by 7 68.

[00:54:57] **Adam:** God, do you remember when that seemed like it was so huge?

[00:55:00] **Ben:** yo, Well, and what was before that? It was like six 40 by four 80.

[00:55:05] **Adam:** Yep.

[00:55:06] **Ben:** Oh man. That's crazy. If you, if you ever, if you ever put that, you like, open up a graphics program and draw a rectangle that's six 40 by four 80, it's, it's like a comically small.

[00:55:18] **Ben:** It's like the size of your watch face.

[00:55:20] **Adam:** Yeah. I mean, yeah. I mean, a, a iPhone, the original, like iPhone, the width of the screen is three 20, so that's half of the 40.

[00:55:30] **Ben:** That's crazy. Oh, man. Yeah. We've had customers who literally couldn't figure out how to submit a form because the submit button just happened to be right below the fold

[00:55:41] **Ben:** of the

[00:55:42] **Adam:** God.

[00:55:43] **Ben:** You're like, Ah, that's a hard one to solve.

[00:55:47] **Adam:** scroll down.

[00:55:49] **Ben:** but the, the, so the related one on, 28th there recently profiled the performance of the system. I think any, anything performance related, that's where I start to get really fuzzy on having a plan. Like, my plan is usually, it either breaks the system or it doesn't. And like anything that falls in the dozen category is sort of like good enough for now.

[00:56:10] **Ben:** But I don't have, I don't have good strategies.

[00:56:14] **Tim:** Yeah. One good strategy that I don't have is like, so you have a lot of these tables and doing these joins and when the data set is kind of small,

[00:56:21] **Tim:** no problem. All of a sudden the data set starts to expand and all like, Oh, wait a minute. We really need some better indexes on this

[00:56:27] **Tim:** thing to, to make this run better.

[00:56:30] **Tim:** So that's bit me in the butt

[00:56:33] **Tim:** a few times in life.

[00:56:34] **Adam:** but that's also, you could look at it as a good thing, right? It's not, you didn't prematurely optimize, right? Like, it's one thing if you are, if you don't have enough data in your development environment to or in qa, if that's where you wanna do it, to, to find these problems before they hit production.

[00:56:50] **Adam:** And then a problem happens like as soon as you release that is unfortunate and hopefully preventable. But like, you know, if you build a new feature and it doesn't have the index and, and whatever performance tuning it needs in order to scale well, when in five years that it finally has enough data that it's a problem.

[00:57:11] **Adam:** I call that a win. I call that not,

[00:57:14] **Ben:** yeah.

[00:57:15] **Ben:** Although, I'll say something at work, and I don't know if this is just like a insecurity about database performance, but I, I, I see this time and time again where developer will have a feature and they've, they've added a new table to the database and the data's starting to grow. and and they'll start to get slow query alerts or the CPU on the database will go high and they'll look some, they'll look somewhere at what's happening and they're like, Oh, this table, there's a full table scan because we're looking up by user id, but there's no index on user id. And then they're like, All right, well now we need to come up with strategy for adding the index in a preview environment and then load testing it to make sure it's right. I'm always like, You don't have to load test it. You're doing a full table scan. Now.

[00:58:01] **Ben:** Anything less than a full table scan is good.

[00:58:04] **Ben:** Like just add the index. You don't have to worry

[00:58:06] **Ben:** about it. I don't know, maybe I fly too fast and loose.

[00:58:12] **Tim:** Yeah. Well, that's just my default mode. So like, don't, don't fix it till, don't fix it until, until you know that's a problem. But when monitoring, you kinda get ahead of that. When you start seeing things that are, that we're taking milliseconds before, now they're taking seconds. You're like,

[00:58:26] **Tim:** you, you need to take a look at that.

## [00:58:28] Never Say Future-proof

[00:58:28] **Tim:** I'm gonna jump down to 38. I like this one. I never used, oh no, 39. I never used the phrase future proof when referring to my.

[00:58:36] **Ben:** Yo.

[00:58:37] **Tim:** Future proofing is 100% of fools errand

[00:58:40] **Ben:** Oh, yeah. Oh, I feel,

[00:58:44] **Ben:** yeah, I, No, no, like I feel, I feel attacked, but, this, this is a struggle. I think this is a struggle. it's hard to, it takes a tremendous amount of discipline, in my experience to start down the path of problem solving and not see all the things that might happen one day and, and feel like you, and feel like you can ignore them for now.

[00:59:06] **Ben:** I, I'm, I'm getting better at that, but it is still very hard to do, and, and I feel like every time I, I approach a new problem, I have to, I have to put myself in that mindset.

[00:59:18] **Tim:** Yeah. I mean, the caveat of that is, is it's saying that you can't pre solve problems you have no information of. But if you have some information that leads you to believe that there's gonna be a problem, I don't see that as, as future proofing. Right. That's. It's a tendency, it's a trend, but it's like you're trying to solve a problem that's not even happening right now.

[00:59:37] **Tim:** That's premature optimization. Right. And we've talked about it before.

[00:59:40] **Ben:** This, this got me, this bit me in the,

[00:59:43] **Adam:** Focus.

[00:59:43] **Ben:** I'm trying to think of how to articulate this. Well, I was gonna say, I, I wasn't gonna say bit me in the, but Cause I almost didn't make it that far. And that's the thing is, so I wanted to build at one point an audit log. We've talked about auditing stuff before

[00:59:56] **Ben:** and,

[00:59:56] **Ben:** and I've never really built an audit log in my life.

[00:59:59] **Ben:** And, I, I was thinking, I'm like, Oh, maybe I could just have some sort of table that's. This user did the a thing, here's the thing that they did, and like, here's a text area column that's like any other metadata that I might wanna include with it. And, it just felt so sloppy . And, and I went to the architecture team here and I was like, This doesn't feel right.

[01:00:18] **Ben:** Like, can you guys gimme some advice on how you might wanna track things? And then of course, they immediately went down the, you shouldn't be using a database table for this. You should be using some sort of like, text-based document service or, or some other kind of document store, data store that's more scalable.

[01:00:35] **Ben:** And then like, I was like, Oh, well now you want me to do multiple layers of things that I've never done before. That's not, I don't wanna solve multiple problems. It's that I ended up just not building it at all. And, and it, and I, and I think back to that and I'm like, I was so nervous about not being able to solve, like I was afraid that I would build this audit table.

[01:00:55] **Ben:** And then people would need to access it in a way that I hadn't anticipated, and I wouldn't know how to deal with that because maybe I hadn't stored the data that they needed, or I hadn't stored some reference that they needed. Or you couldn't look up the references past enough or something, or sort them by da.

[01:01:08] **Ben:** I don't know. Like I just had so much anxiety about it, about problems that I didn't know what they were, and then I ended up just not building it at all. And that it doesn't feel like a win. Like it feels like a better solution would've been to build something. anyway, I'll

[01:01:23] **Ben:** I'll

[01:01:26] **Adam:** Uh, it just, I, I forget, what the name of the department was or the people that you, the team that you took your concerns to, but, when you were describing, Yeah. Yeah. So when you described their response, my first thought was like, so you took it to like early stage stack overflow basically. That was the response you got back was like, Oh, you need to be doing X, Y, and Z Shouldn't use J

[01:01:47] **Ben:** Yeah.

[01:01:47] **Adam:** that.

[01:01:48] **Ben:** You should put that in some sort of a, an elk stack with a cabana open text searching. I'm like, bro, I, I already got a database. I use the database I already have

[01:01:58] **Adam:** Mm-hmm.

## [01:01:59] I Can Schedule My Time

[01:01:59] **Tim:** Number 40. I feel I can schedule my own time. Well, you're an adult person. Just use a calendar.

[01:02:07] **Ben:** growing ass man.

[01:02:09] **Tim:** Exactly. I, I'll tell you. So it's like I've gotten away. When we first started recording, I talked about how I had my checklist. I have a notepad I used to keep by my desk here. I don't, I got rid of that. I, I don't use checklist anymore. Everything, because checklist doesn't necessarily relate to time. So it's like, if I'm in a meeting, and like I say, all right, the action item is I owe you this, this, and this.

[01:02:30] **Tim:** I, I immediately go to my calendar. I block out 30 minutes, 15 minutes, whatever, how long I think it's gonna take, put it on my calendar for some time in the future. And then when I wake up in the morning, I look at my calendar, I'm like, There's my time. There's what I'm working on and other people. Will not schedule me during then because they can, they can see my calendar and say I'm blocked out.

[01:02:50] **Tim:** So it's like my calendar has, you know, sometimes it has some white space, but it's, you know, I'm, I'm blocking out that time cuz otherwise I'm not gonna get it done if I'm just working on a checklist. It's like, that's sort of making me feel good. Like, you know, I, I check something off, but it's like, if I know this is the time I'm working on this, I'm doing that, I get stuff done.

[01:03:11] **Adam:** I feel incredibly privileged that the vast majority of my schedule is wide open. Like we have a standing meeting every day, and that can go from like five minutes to an hour, depending on what needs to be discussed. But it's like, other than that, I don't typically have any meetings in a week. And, and, you know, every, like, every month I might have three or four meetings to add beyond that, that one other meeting.

[01:03:39] **Adam:** And so like, I kind of want to block off. Okay. You know, let's just say like from noon to, to end of day is my deep work time every day.

[01:03:50] **Adam:** But,

[01:03:50] **Adam:** The, the times that stuff comes up is so random, right? Like there are, you know, maybe two, three times a week it's like, okay, I need you to drop everything and work on this.

[01:04:02] **Tim:** that's ideal. I mean, that's, I mean, you're living the dream

[01:04:04] **Adam:** Yeah. like I said, I feel privileged, but at the same time, like I I, and I wish I could choose what time of day. I'm just going to say like, no, I'm not doing anything but my, my deep projects. Because I think as we, since we are such a small team, like we have no choice but to be more nimble and willing to, to jump around.

[01:04:25] **Ben:** Yeah.

[01:04:25] **Tim:** mean, I wear a whole bunch of different hats, so it's like, like, alright, I'm putting on my, we're doing price increases hat, so I need to like schedule that out so I can do that and I need to talk to Legal hat and then I'm gonna do some, you know, someone has a new feature and I really kind of wanna work on that feature.

[01:04:40] **Tim:** So I'm gonna schedule, here's my coding period time there. So that's, this past year that's kind of been transf transformational for me is like, I'm using my calendar rather than a checklist so that I can just make sure I got the time. And if I run outta space, I'm like, No, I can't. It's gotta move.

[01:04:57] **Ben:** solid move. I'm, I'm, I don't, I don't think my time is as open as Adams, but I don't, I don't have very many meetings. I have maybe like two meetings a day. and I feel, I feel like I actually use my time very well at work. I think that's, that to me feels one of, like one of my superpowers. the irony is, is that, Good as I am managing my time at work, I'm completely catastrophically the opposite personally.

[01:05:24] **Ben:** and I, and I think the difference is, is that so much of my time management personally involves other people. And like, that's my cryp tonight. The time management that I have to do at work is like, here's all the things I need to do, mostly in isolation. And that feels so easy to do. the moment I have to return an email or make a doctor's appointment or respond to a text message, I'm like, I'm like, No, I'd rather just go crawl into a hole for the next couple of hours.

[01:05:52] **Tim:** Oh

[01:05:53] **Adam:** You need to like start taking speed or something.

[01:05:58] **Tim:** children. We do not recommend this.

[01:06:02] **Adam:** It gets

[01:06:02] **Ben:** You can't see, Can't see Tim winking, No

## [01:06:07] Not Wasting Other Peoples Time

[01:06:07] **Tim:** right. one. I'm passionate about this. I, I'm vigilant about not wasting other people's time.

[01:06:13] **Ben:** Yo.

[01:06:14] **Tim:** And for instance, don't waste, don't, don't ask a question that you could Google.

[01:06:18] **Tim:** So I've kicked people, I mean, I got in trouble for this, but I kicked someone, someone came to my office to ask me a question.

[01:06:24] **Tim:** I'm like, Did you Google it? And she's like, No. I'm like, Then get out. Come back. When you Google it and then someone's like, They made a company policy. Don't ask too many questions. Like what? No, that was not the point.

[01:06:39] **Tim:** That was not the point. But at the same time, don't waste your time if you're struggled for hours.

[01:06:46] **Tim:** Right? If you struggle, if you Googled it and then you still can't figure it out, you struggle. You know, Go ask someone for help. But it's like, gotta find that balance there. Cuz

[01:06:53] **Adam:** man.

[01:06:54] **Tim:** people ask that questions. They didn't even Google just annoy me.

[01:06:57] **Adam:** You're, you're dead on. And it's funny, the, like, all the things you just said that talking about like, you know, don't ask immediately spend, you know, a reasonable amount of time trying to figure it out for yourself, Google, and just try, stare at it, read docs, whatever. Right. But then, you know, also at the same time, like don't sit on it for a week because you can't figure it out.

[01:07:19] **Adam:** Like if you, a couple of hours, if you can't figure it out and you know somebody knows the answer, then yes, interrupt them. The, I have, I think back when my company was three people, like before we hired our third person, I put together a Trello board that was like our onboarding documentation. It's like, okay, here's all the information for payroll and here's this and here's that.

[01:07:39] **Adam:** And also like, just sort of like engineering team principles. And that was one of them, like, you know, don't respect the flow state of other people

[01:07:48] **Adam:** and.

[01:07:49] **Ben:** So when I, when I, had my very first internship in college, they were walking me around the first day and they were introducing me to people and they, and they pointed over to this guy, He was at his desk and he had his headphones on, and they're like, That's so and so, when he has his headphones on, you're not allowed to talk to him.

[01:08:08] **Ben:** he is, you know, like in deep. And my gut reaction at the time was like, Oh, so this guy's a jerk. , and now, but like now maybe I feel bad. Maybe that's not the reaction I should have had. Maybe I should have respected people's times. But it just felt so weird. You're like, Oh, what do you get to be in your special cone of silence?

[01:08:25] **Ben:** Like, that's not how people work. But

[01:08:28] **Tim:** I, I will say on the, on the flip side, so I did ask someone a question one time. I sent 'em a, a message, I don't remember what it was, Slack or whatever, and they sent me a, let me Google that for you. And I, I, I mean, seriously, my blood was, I got to like murderous like levels of anger. And I was like, How dare you condescend to me?

[01:08:51] **Tim:** You, And then I had to like serenity. Now I. And I'm like, Dude, you cannot throw stones here cuz you've done this to people over and over again in your lifetime. So I could see how things kind of feel if you're on the receiving end of like, did you Google it? Like, But yeah, just seriously, just just Google it first before you go ask a question cuz like Stack overflow normally has the answer for you.

[01:09:18] **Ben:** one thing that I'm very good at is switching context. I, I know historically a lot of programmers complain about context switching and like their whole mental map is destroyed and then takes 'em like 20 minutes to get back into flow. That, that's like not a point of friction that I've really ever felt.

[01:09:35] **Ben:** And I think maybe, again, we've talked about this before. I work on very small tasks, so I don't actually keep a lot of stuff in my head anyway. It's not a point of friction I've ever felt. And I'll tell you when I've worked with people and, and they'll be like, All right, I'm gonna go offline for four hours cause I gotta get heads down and get some work done.

[01:09:53] **Ben:** I've, I've always been. I don't know. It always rubs me the wrong way a little bit. And I know it's, it's not fair cuz a lot of people like that just happens to be something I'm, I think, unusually good at. And it's, it's, I hate the fact that I have trouble seeing it from other people's perspective, but the, I guess like, sorry, not to ramble, but like heads down as a, as like a don't interrupt me, I've, I I don't take that well.

[01:10:20] **Ben:** Like, I find, I find that strange and I hate that and I hate that I'm even saying that out loud. cuz I know a lot of people get a tremendous amount of value from going down, from going into a heads down mode, but it just seems

[01:10:32] **Tim:** Sorry.

[01:10:40] **Adam:** was that about? Being a grown ass man?

[01:10:50] **Tim:** moving on.

[01:10:51] **Ben:** on.

## [01:10:51] Constructive Feedback and Uncomfortable Conversations

[01:10:51] **Tim:** So there's like several here about constructive feedback and, not avoiding uncomfortable situations and conversations. Yeah. So I, I think I, yeah, those are hard. Those are really hard. So it's like you see something in the company that you're like, you know, this isn't good. I don't feel good about this.

[01:11:12] **Tim:** Or maybe this particular person, they're not performing and talking about it. I mean, I still don't know if I'm comfortable with that. I mean, sometimes I just wanna ignore it and say, Not my monkeys not my circus. but I mean, I, I get it.

[01:11:25] **Ben:** all of my biggest regrets at work are about not being more confrontational.

[01:11:30] **Tim:** Hmm.

[01:11:31] **Ben:** The, those are all the wrong choices that I made. That's so frustrating. I, I wish that was something I was, I'm so terrible. I'm such a, I'm a, a catastrophically, non-confrontational person.

[01:11:42] **Tim:** I mean, I am also to an extent, unless I'm, I feel I'm forced into it. Like, you know, people are like, What do you think's going on? Like, all right, I'm gonna tell you the truth, but it's like, if I'm not asked, I'm not volunteering cuz I don't wanna be the, fly in the ointment, right? Cuz those are hard things and a lot of times if you get labeled the difficult one, it can be hard on your, hard, on your career. But if they ask you that, you're like, Well, okay, I'm gonna tell you. But if you don't ask me, I'm not volunteering because I, I, I see the stuff going on here. I know this is all toxic. I, I recognize it and maybe, you know, maybe you don't see it, so,

[01:12:24] **Adam:**

[01:12:24] **Ben:** I was gonna say, I dunno if anyone ever has watched the show, Grey's Anatomy. I was a huge Grey's Anatomy fan. And, uh, there was this guy, Dr. DrRichard Weber, I think he was, he

[01:12:34] **Ben:** was like the chief of surgery, and I was always in such awe of him because he, he had these wonderful, warm relationships with everybody.

[01:12:44] **Ben:** But then at a, at a moment when he needed to do it, he could just flip a switch and he would go into chief in mode and he would just lay down the law and tell people what's up. And then he'd go right back to having these wonderful, warm relationships. And I know that it's TV drama,

[01:13:00] **Ben:** but I was always, I always looked at that and, and I wanted to have more of that in my life.

[01:13:04] **Ben:** Like I wish I could do.

[01:13:07] **Adam:** It sounds like the exact opposite of Dr. Cox from Scrubs.

[01:13:11] **Tim:** right? No, but I'll tell you, Ben, there are people, So there are people in our organization who are like that. They, the most empathetic people, they, they, you feel when you talk to them, they understand you, but at the same time, they can like turn

[01:13:28] **Tim:** and go into straight, Listen, you're messing up here. You need to get right.

[01:13:33] **Tim:** You know, and, but you don't feel attacked because you felt listened to before. So, you know, they're not

[01:13:39] **Tim:** attacking you. They're just, they're trying to help you get better. But that is a really, that's a really hard place to be in as far as a person. So,

[01:13:47] **Ben:** I know. And I wish I could, I wish I could better understand where it comes from. I always chalk it up to confidence. Like I don't have, I think the confidence to be strong and feel like I'm, I'm not damaging the relationship. And I, and I think I don't, I don't know. I. Again, I just wish I could figure it out.

[01:14:07] **Tim:** Hm.

[01:14:08] **Ben:** I can't, cra I can't crack that code.

[01:14:10] **Tim:** It's tough one.

## [01:14:11] Returning Value To The Commons

[01:14:11] **Tim:** Yeah. Let's, let's finish it up on 48.

[01:14:13] **Adam:** Okay, I like it. So I'll read it. I pursue opportunities to return value to the commons when appropriate. And so the context it gives here is all our work builds on top of the work of countless others. At some point, you'll have opportunities to give back to the community at large.

[01:14:26] **Adam:** For example, talking at meetups, making open source contributions, or even just discussing topics with your team to boost everyone's skills. you know, like making a podcast

[01:14:36] **Tim:** Yeah,

[01:14:37] **Ben:** Yeah,

[01:14:37] **Tim:** check.

[01:14:38] **Adam:** Exactly.

[01:14:38] **Tim:** on my calendar.

[01:14:41] **Ben:** I do love it at work when people, we use Confluence at work. It's like a wiki from Jira from Atlassian People will just write up things like, Oh, we had this hard problem to solve at work, and, and here's the thing that we came up with, and they'll write up a little confluence page and drop it in the engineering chat.

[01:14:56] **Ben:** I love that. That's been, I, I love to see people sharing that kind of stuff.

[01:14:59] **Tim:** Yeah. I, I think if you can like, take something in that you built and like if it's appropriate, make it open source project. That's fantastic. I mean, I know Adam, you, you built, you know, some open source projects and, and super helpful for me, so I super appreciate that. Or, and of course, yeah, we have this podcast, but just talking about, you know, just boosting people's skills and trying to get better at what we do as craftsman in this.

[01:15:25] **Adam:** and, trying to normalize the things that we all go through that maybe would've

[01:15:30] **Adam:** gone unsaid too.

[01:15:33] **Tim:** Yep, For sure. Yeah, so I mean, I think it's a good list. I mean, there's some things I'm like, I scratched my head at, but the, for the most part I'm like, you know, this is what if you want, if you are a new person, like coming in, like just outta college, and you think it's all about just like having skills and code, this really, this isn't code centric.

[01:15:54] **Tim:** This is about being a problem solver, about being a team player, about understanding what it is you're doing. And then honestly,

[01:16:02] **Tim:** in life, that's the hardest thing. And a good, I mean, understanding what's going on is probably the hardest thing in life. problems are so complex in life, so it's just being able to articulate the issue and understanding the issue and, knowing when to stop working on the stuff.

[01:16:21] **Tim:** This is, I mean, I think this is great. So,

[01:16:23] **Ben:** Yeah.

[01:16:25] **Adam:** Good.

## [01:16:26] Patreon

[01:16:26] **Adam:** All right. Well, this episode of Working Code is brought to you by being an adult person who uses a calendar and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe than you should consider supporting us on Patreon, our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[01:16:46] **Adam:** Special thanks of course to our top patrons, Monte, Sean, and I'm probably gonna butcher this, but that's okay cuz I said it, I was gonna butcher it in the, in the Patreon, description, G Carlo, Giancarlo, sorry, but also not sorry.

[01:17:00] **Ben:** Nailed it. Nailed it.

[01:17:01] **Adam:** Yeah. if you'd like to be one of those people that helps us out, you can go to patreon.com/WorkingCodePod and if you didn't p on it new this week.

[01:17:09] **Adam:** Giancarlo Giancarlo Carlo Gomez. thanks and, and, welcome aboard. New Top

## [01:17:14] Thanks For Listening!

[01:17:14] **Adam:** Patron. After show this week. Tim, you're gonna tell us a little bit about your London trip. I think

[01:17:22] **Tim:** Oh yeah. I'm gonna give you the low down on Adam Cameron for sure. Yeah. one hater,

[01:17:28] **Tim:** The truth will be out.

[01:17:30] **Adam:** All right. And I, if I'm not mistaken, this episode, comes out to the public on the 19th, I'm sorry. Yeah. Yeah. This episode comes out on the 19th, so you've got one week from the time that this episode releases to get your questions in before we record our 100th episode.

[01:17:47] **Ben:** crazy

[01:17:49] **Tim:** while we eat spicy

[01:17:50] **Tim:** wings.

[01:17:51] **Adam:** so we're doing a little bit of an a and a AMA and, and punishing ourselves with, extremely hot, spicy food.

[01:17:58] **Adam:** Uh, you can find the link to ask us a question on our website that's workingcode.dev. and that's all the homework I'll give you for today. Leave us a question. Working code.dev. And yeah. So, you can, find us on Working Code Pod at, Twitter or Instagram. You can join our Discord at workingcode.dev/discord.

[01:18:14] **Adam:** You can email us at WorkingCodePod@gmail.com. Send us a voicemail to the same email address that's gonna do it for us this week. We'll catch you next week. And until then,

[01:18:22] **Tim:** Remember, your heart matters, but mostly you, Adam Cameron, you beautiful, beautiful beer drinking curry, eating hot sauce taking lovely, lovely man.

[01:18:33] **Adam:** bear swell

[01:18:34] **Tim:** but you're still our number one hater.
