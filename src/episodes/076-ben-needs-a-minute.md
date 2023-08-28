---
title: "076: Ben Needs A Minute"
description: "If Ben crushes it in the woods, and no one is there to see it, is he truly crushing it?"
date: 2022-05-25
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/076-ben-needs-a-minute/id1544142288?i=1000563776432"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

If Ben crushes it in the woods, and no one is there to see it, is he truly crushing it? Such are the philosophical questions that go through Ben's brain as he continues to pour his heart and soul into a legacy product that no one else at the company cares about. That is, except for the customers that still log into the legacy platform on a daily basis. Don't those customers deserve something? Ultimately, Ben just wants to hear that he's doing a good job.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/076-ben-needs-a-minute.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I don't know if anyone's ever heard of the concept of the, of love languages. That there's a famous book called the five love languages. I can't remember what pretty much any of them are, but, uh, like, like, like one is gifts. Yeah.

[00:00:12] **Ben:** Touch

[00:00:13] **Adam:** No gifts is not, oh. Gifts with a Twith a

[00:00:17] **Ben:** Oh

[00:00:17] **Ben:** yeah.

[00:00:18] **Carol:** Yes. Memes and guests are definitely a love language. You guys.

## [00:00:46] Intro

[00:00:46] **Adam:** Okay. Here we go. It is show number 76 and on today's show, Ben needs a minute. So we're going to give it to him. But first as usual, we'll start with our triumphs and fails. It's my turn to go first.

## [00:00:56] Adam's Triumph

[00:00:56] **Adam:** So I'm gonna start us off with a triumph. I, as I was discussing last week on the show, actually, decided to make some improvements to my open source library.

[00:01:04] **Adam:** Semafore for feature flags and CFML, and I'm done now. I have actually released, when we're recording this, I've released like a beta version of 1.0, which included include my changes. And it was super easy to make those changes because I had tests. So, Like four or five lines of code changed and I could make all those changes with high confidence that I haven't broken anything else because the tests all still pass.

[00:01:30] **Adam:** And I added new tests for the new functionality. So I'm happy about that.

[00:01:36] **Carol:** That's awesome

[00:01:37] **Adam:** it took me probably three or four times longer to write the blog post explaining what I was planning on doing and publish that on my blog than it did to make the code

[00:01:47] **Carol:** to do the actual work I love when it's like that. Like all this was great, easy to do. Now. The documentation part starts.

[00:01:55] **Ben:** Yeah. Yeah. Is there anything in the testing that, that like is a mock of a persistence layer or anything like that?

[00:02:03] **Adam:** Not have a persistence layer. So this library, just kind of throws that responsibility over the fence, the data persistence. It's the library, you instantiate it and you go, okay, here's your data. And then, it'll. Do the it's the rules, engine processing stuff. And so the, the data persistence and, crud of the rules is all entirely out of scope.

[00:02:27] **Ben:** Nice, nice.

[00:02:28] **Carol:** Yeah, it shouldn't care about the logic. It's just care that the functions work, that the core of making a rule work is there.

[00:02:34] **Adam:** Right? So for the test, it just creates an instance of the CFC and says, okay, here's all the flags. And now run some tests to verify different things about different scenarios.

[00:02:45] **Carol:** That's cool.

[00:02:46] **Ben:** Very cool. I see that Adam Cameron, is he building his own testing framework? Has anyone been following that conversation?

[00:02:52] **Adam:** haven't been following it closely, but I do know that he is. I think that,

[00:02:56] **Ben:** Was it just, is it just an exercise or is there something more in depth as far as need?

[00:03:02] **Adam:** yes,my impression, and again, I have not been following it closely, but my impression is that he was dissatisfied with some of the problems he was running into with other testing frameworks. And CFML, he has a pension for finding bugs, right. He starts a project and instantly finds bugs in Lucy and Adobe ColdFusion and whatever frameworks and libraries he's using.

[00:03:24] **Carol:** which is the kind of person I want on my team, by the

[00:03:27] **Adam:** Exactly fantastic at it. and, so I think that maybe partially inspired by that he was like, how hard can it be to write a testing library? So he's kind of like creating his own and he's TDD seeing the library itself. And I, from what I understand, he's now TDD in his blog articles. Like, he's like, okay, this is the next thing I want to write in the article.

[00:03:48] **Adam:** Let me write the code for it and make sure that it's passing the test. And then I can write that chunk of the article. yeah, I think he described it as like red, green refactor. Right.

[00:03:56] **Carol:** No

[00:03:57] **Adam:** Adding a step to

[00:03:59] **Ben:** like a bit of work, but interesting. Very interesting.

[00:04:03] **Adam:** the dude is a machine. He, yeah, I don't understand it. I don't get it. Well, I do understand it. I just am not at that place in my life anymore. I've moved to a new phase of life where when the Workday is over, I don't want to see a computer and I've gotten really good at disconnecting. Like I have my phone and, if I'm on call or if, if it escalates to me, then I'll get the notifications.

[00:04:25] **Adam:** And I don't mind dealing with that, but I don't use a computer for fun anymore.

[00:04:32] **Ben:** Yeah. I know what you

[00:04:33] **Adam:** aside, like, okay, I use a computer to control the CNC and my workshop, or to do the 3d printing stuff, but like, I'm not coding for fun anymore used to all the time, but.

[00:04:46] **Carol:** I have a question for you previously, you had written something to check your test coverage and that was in your CFML projects. Yeah.

[00:04:54] **Adam:** I love you. I love you, Carol, but, no.

[00:04:57] **Carol:** what was that?

[00:04:59] **Adam:** So I wrote a tool, to keep an eye on our application and see like, which actions in the application were succeeding, which are being used, which are not being used. And when they're being used, are they succeeding or erroring? What's the error rate? Like, and it was inspired by a test coverage tools?

[00:05:20] **Carol:** And I don't know why I thought a long time ago, like maybe a year ago you wrote something to figure out if you had test coverage.

[00:05:27] **Adam:** No, it wasn't. I mean, it was, I have done a lot of stuff with test coverage, but I didn't write the coverage tools. and yeah, so when we were migrating from Adobe ColdFusion to Lucy, I. So, I mean, it's basically hooks inside of our application framework that we use, like lifecycle hooks right before or after that sort of thing.

[00:05:47] **Adam:** and I hook into those two, I guess for lack of a better word instrument, the application and log, okay, this action was run and it was successful and it took this amount of time or an error was thrown or whatever, so that we have those statistics on an action by action basis throughout our application, which has been really useful and interesting data to have.

[00:06:10] **Adam:** But yeah, no, it's not, like I said, it's inspired by test coverage in terms of like being able to drill down into things and see where the hot areas are, but it's not at all about testing.

[00:06:21] **Carol:** Okay. That's what I'm looking at next is something to give me test coverage on our CFML projects.

[00:06:27] **Adam:** I wish you luck.

[00:06:28] **Carol:** yeah, it may be something that we have to do in house, but that's part of trying to find out where you're covered at. So we better do something.

[00:06:35] **Adam:** I mean, I don't know exactly how test coverage tools work. I've seen some in the past that gives me the impression that they like modify your source code and inject its own code, like on every other line, like between every line of your code to say, okay, it's like, when you're debugging, you can do okay.

[00:06:53] **Adam:** Console dot log, a console dot log B console, let's say, cause you want to see exactly how far it's getting through your thing. Well, it's my impression is that it's doing that to say, okay, this line was run. Then this line was running. Then this line was running because the coverage is not even tracking necessarily whether, code did well.

[00:07:11] **Adam:** It's just, this was executed in the course of running the tests. So you run the tests and it logs what was, and wasn't executed. I'm not aware of anything that currently does that for CFML. I think there, there used to be something, if I'm not mistaken built into fusion reactor, but, or maybe it was in, maybe it was in SI fusion or

[00:07:35] **Carol:** One of those tools.

[00:07:36] **Adam:** yeah, maybe.

[00:07:38] **Ben:** I mean, I dunno how this even works in the JavaScript side. I would think that, you're wiring your application together. Although I guess the test coverage is not based on the running application, it's based on the unit tests and that kind of stuff. So I guess there's more opportunity for the testing framework to wrap around the things that you're actually calling. So, so in that case, maybe on a ColdFusion perspective, you could wrap all the components and not do the line by line, but you can certainly with an on missing method, proxy, every single function call and see which ones are called kind of a thing. And then you couldn't say like this line was called, but you could say like none of these functions were

[00:08:15] **Carol:** Right. Nothing on there executed. Yeah.

[00:08:18] **Adam:** Yeah. I, to be fair, I don't know how it works for JavaScript either. It's all a black magic to me. I would

[00:08:25] **Carol:** it just happens.

[00:08:27] **Adam:** some time and dig into a library that does that like look at the code ingest, but, and who has the time?

[00:08:33] **Carol:** Not and to do our real jobs.

[00:08:35] **Ben:** Yeah. Do you ever sometimes, an open source library will do something interesting and I'm like, oh, you know what? I bet that would be really useful. Let me look at how it's done. And then you go to the GitHub repository for it. And it's like a thousand files. And like each files, like it's like 1500 lines of code.

[00:08:52] **Ben:** You're like, I'm never going to

[00:08:53] **Carol:** I can't figure it out. Yeah. Yeah.

[00:08:56] **Ben:** let alone find the one thing that I thought would be interesting to know about.

[00:09:00] **Adam:** the thing that drives me nuts in those situations is. I'm like, okay, this is a really small library and I really want to add this feature or fix this bug or whatever. And I go dig into the code and it is way too clever for its own. Good. And like, it's a, it uses all this indirection and abstraction and it's like totally unreadable because I'm coming into it completely blank, no history with this code.

[00:09:27] **Adam:** It's so it makes it like opaque, impossible to read. And I'm just like, Nope, I give up, sorry I was going to contribute, but you made it too difficult. So for me in this like later stage of my career as I'm, reaching my elderly phase of my career here. Yeah. I've come to appreciate the fact that clever code is bad.

[00:09:50] **Ben:** A thousand percent. Yeah.

[00:09:52] **Carol:** I needed to be readable like neat. I need to be able to read it and I need to just kind of be able to follow it pretty easily, or I lose interest very quickly.

[00:10:01] **Adam:** Yeah.

[00:10:02] **Ben:** We have a whole suite of node JS services. And this is not a knock on node. This is just the lifespan of our company, the node services where a sort of post ColdFusion Priego and they're this sort of no man's land of architecture. And every time I have to go into one of the node services to update it, I'm just like, oh my God, F you F like, why did you put that together?

[00:10:25] **Ben:** Like, there's like so much layers of indirection and passing objects to other objects that then inject properties into that other object and pass it back. And you're just like, it's impossible. You really have to it's like, you can't come in and just karate chop a fix. You have to like embed in this project to understand how it works and work on it for weeks before you feel comfortable with even just understanding the control flow or request, it's just.

[00:10:50] **Ben:** It's just crazy.

[00:10:52] **Adam:** I totally understand what you're saying though. Like it's totally possible and easy to write bad code in any language

[00:10:57] **Ben:** Yeah, yeah, yeah. Yeah. And again, like that's not a knock on note at all. It's, it's like, it feels like someone from like a Java background where there's a lot of interesting patterns came into note and I was like, I'll just apply the same kind of thing, but like, didn't have any of the interesting, like dependency, injection frameworks that also come with Java.

[00:11:16] **Ben:** So they were at hand wiring. I dunno, it's just bananas and it makes me so angry every single time.

[00:11:20] **Adam:** And the anger never goes away.

[00:11:24] **Carol:** It's okay. Ben, I wish I could hug you.

[00:11:27] **Adam:** Well, don't worry. You'll get an opportunity for some catharsis here in a minute. so Tim couldn't be with us tonight. He, one of his kids is getting yet another

[00:11:34] **Carol:** Another one. Oh my goodness. These good kids of his, so

[00:11:39] **Adam:** got to go sell and making the rest of us look bad as parents here. so,

[00:11:43] **Carol:** take much.

[00:11:44] **Adam:** yeah. Oh God. Hey, what are you trying to say?

[00:11:47] **Carol:** No boys are going to be boys. You do the best you can.

[00:11:51] **Adam:** That's true. All right, well, so, Carol, how about you?

## [00:11:54] Carol's Triumphs

[00:11:54] **Carol:** Well, I will, jump on the celebration wagon with Tim, I suppose. And I'm going to actually go with, to triumph. So Peyton is, I know I got to take on his spot. Peyton's my youngest. He is starting his senior year of high school next year. And he is dual enrolling in college. So he'll be doing college classes and taking high school classes at the same time.

[00:12:16] **Carol:** It's very common here. A lot of kids do it. they take their core classes that they need to take for high school over at one of the technical colleges and they just transfer into their college. like classes, right? So it's super common for them to do it. Anyways. He's been working on this for five weeks now, five weeks of back and forth with counselors and asking people to send things and saying, we sent your transcripts, but the schools never got it.

[00:12:42] **Carol:** Submitting his application. They're not getting it. He literally has been walking around with a printed copy of his admission application in his backpack because he knows he's going to have to keep handing it to people because he's just getting ignored. He's a 17 year old boy and they have a lot going through and they're just kind of pushing him to the background and to the back-burner.

[00:13:02] **Carol:** And they're like, oh, we'll get to you. We'll get to you. Everything is due tomorrow. If this is a finalize tomorrow, he doesn't get a spot. And he says to take all of his classes on campus, which isn't going to work for him because he's also taking independent study. He's taking an AP physics two class because he has decided he wants to get a degree in physics.

[00:13:20] **Carol:** So yay. Super excited about that. I'm really proud of him. but today we, in the middle of being sick and everything from, I got boosted. So I got my booster yesterday, but of course it made me run a fever. So that's my first dry up. I have all three of my COVID shots now, but I've been sick all day, in the middle of being sick.

[00:13:38] **Carol:** My second trip happened, which is we went over to the school and I, fell on my mom shorts and, got it all taken care of. So he's enrolled. In all of his classes, he's admitted everything's through and we're good to go. So then I called the school and got all of his independent studies approved and now that's over at the board office.

[00:13:56] **Carol:** So I just have to call tomorrow and get that done. So he went from going, I'm just going to handle all of this to, oh my God. I'm so glad you finally jumped in because this is overwhelming. So I was proud that he gave it his best shot at it, but they, the adults that are working with him, weren't taking him seriously.

[00:14:13] **Carol:** So I had to jump in. So it was just nice to see the effort he put in and to finally get it resolved though. So, yay. I'm a good mom.

[00:14:20] **Adam:** Mom's superpowers.

[00:14:22] **Carol:** super powers. Who, when we were walking in the school, we have this silly, like saying apparently it's from a movie. I don't know movies. So don't ask me what movie it's from, but it's a. praise Dell, raise hell or like raise hell praise Dell. Like for Dale Earnhardt. Right? So when we were walking, yeah. When we were walking to school, I was like, praise Dell, raise, hell had pingos please don't raise hell mom. I was like, I won't raise it. Dale Earnhardt, the NASCAR driver that died.

[00:14:50] **Ben:** or maybe it's from, what was the welfare shake and bake

[00:14:54] **Carol:** I said Talladega nights and everybody tells me that's always wrong. It's not brutality and night. So when I find out what it's from, I'll tell you guys

[00:15:01] **Ben:** that's the only racing movie I know.

[00:15:03] **Carol:** anyway, so yeah, T wins. I have all three of my COVID shots. I procrastinated and the third one, and then I feel like a super good mom, because I finally got that resolved and he's picked a degree for college.

[00:15:15] **Carol:** So I'm super excited to see what his, college career looks like going forward. Physics is going to be interesting.

[00:15:24] **Ben:** There was a kid in my high school class who took an AP to physics

[00:15:28] **Carol:** That's what he's taking it.

[00:15:29] **Ben:** he was the only person in it. It was, I think it was just him and the professor.

[00:15:33] **Carol:** So that's what they're doing with Peyton is, but I think Peyton has convinced a couple of his friends to take the class with him, but they're still going to be physically sitting in the classroom with the physics teacher while he's teaching AP physics one. And they will be doing independent study over on their side.

[00:15:51] **Carol:** And they'll just be able to ask him general questions. He's not going to be doing any teaching with them. He'll just be there for when he's not doing work with the other class. He can answer questions for them, but it's fully self-taught so that'd be hard. Yep. That's me. What about you, Ben? What you got.

## [00:16:06] Ben's Triumph

[00:16:06] **Ben:** to go with the triumph, which is that in previous episodes, I had talked about my big goal for 2022 was going to be taking some piece of Lucy CFML code and containerizing it, and then deploying it as an image somewhere, whether it's like a digital lotion or Amazon web services, something, I just want to, I use containers at work, but I don't really know how they move from a build system to a production system.

[00:16:33] **Ben:** So I want to, I wanted to do that. but I couldn't fail what to do that with, like what the topic would be. Cause I didn't want to pick something that was too complex, that it was too daunting and I didn't want to pick something that was not interesting at all. so I think I finally came up with something that is fairly simple, but we'll have just enough complexity that I think will make it interesting and like just enough work, real world problem solving that it might be something I actually use in the long run.

[00:17:00] **Carol:** And are you going to tell us what this is? Okay. Okay. Okay. Okay.

[00:17:04] **Ben:** going to be totally anticlimactic though. But a real world issue that I have is Christmas will roll around and, we live in an apartment complex and we tend to tip the super during Christmas. And then like, my wife will tip her hairdresser during Christmas and every now and then there's like one or two people we need to tip for something or other.

[00:17:22] **Ben:** And we can never remember what we tip people. So I want to build an app. That's literally just like a tipping journal so that, 12 months later, when you need to tip someone again, you can look back and say, oh, last year, I gave the hairdresser $40 or, whatever it is. And, and I think that's pretty simple, right?

[00:17:40] **Ben:** Some sort of logging, or maybe it doesn't even have to be a login. Maybe it could be some sort of a, like a magic link. Adam, I think alluded to this in the last episode about those passwordless logins, it could be something like that. And then it's, maybe a user table and a tip history table, something like that.

[00:17:54] **Ben:** Super. Almost no JavaScript, probably just very light CSS, but enough where I can wrap it up in a container and deploy it somewhere. And,and I went so far as to buy a domain name, which is super, yeah, it's super, super hard to find my name. It has not taken these

[00:18:08] **Carol:** It's so hard.

[00:18:10] **Adam:** there is the domain name, just the tip.

[00:18:13] **Ben:** so just the tip was taken.

[00:18:16] **Carol:** Of course it was.

[00:18:17] **Ben:** Just the tips was taken tips, tips.com was taken tips, tips, tips, tips was taken. All these things were like, show me your tips.com was taken like all these things. so what I went with was, so the tips is actually a TLD at top level domain these days. Apparently I went through a giant list of them. and I went with sticky.tips, sticky in that it's a

[00:18:38] **Carol:** Yeah. Stay around. Yeah.

[00:18:39] **Ben:** It seems short. Funky enough to make it interesting. and it's actually the first domain name that I've ever purchased through CloudFlare. All of my domains

[00:18:48] **Carol:** Flare is great. Yeah.

[00:18:50] **Ben:** Yeah. I've been playing around with CloudFlare as a CDN, but apparently there as a registrar there, their mission statement is that they only sell their domain names at cost.

[00:19:00] **Ben:** Like it's not something that they want to make a profit, they're just providing the service. And so I think it was like 15 bucks or something for the DOD tips, domain name, which

[00:19:09] **Carol:** It's not bad.

[00:19:10] **Ben:** feel like it's not bad, but I think a.com domain name these days is like $8 or something.

[00:19:14] **Carol:** Yeah. You start out like 7 99.

[00:19:17] **Ben:** yeah.

[00:19:17] **Adam:** I have no idea why the different TLDs are different prices. That's like a whole, it feels very like, Supply and demand, man.

[00:19:26] **Ben:** I don't know, it feels very like a mobster ish

[00:19:29] **Adam:** Look, if you could have gotten, if you could've gotten, like adjust the.tips, do you think that you would have paid 20 bucks for that?

[00:19:36] **Carol:** Yes, I would have, we would have bought that for you after

[00:19:40] **Ben:** it's shocking though. It's shocking, but not shocking. How many things it'll say, oh, this domain names are already taken and then you go to it and it's just a parked page on GoDaddy or somewhere it's like

[00:19:50] **Carol:** doing anything with it yet.

[00:19:51] **Ben:** of all domains are just parked pages,

[00:19:54] **Carol:** Like at least redirected to porn or something, make it interesting for clicking on the link. Oh

[00:19:59] **Ben:** it useful.

[00:20:00] **Ben:** Uh, so anyway, I

[00:20:02] **Carol:** I don't care.

[00:20:04] **Ben:** what is a may June, so we're in the fifth month. So I have S I have seven months to turn my 20, 20 goal into something that approaches a thing. And I feel like I can do that. I'm feeling confident.

[00:20:16] **Ben:** I just need to now carve out the time to actually start it.

[00:20:19] **Carol:** and you'll have it ready for when you need to start tipping your Christmas tips.

[00:20:22] **Ben:** There you go. There you go.

[00:20:24] **Adam:** Maybe

[00:20:25] **Carol:** Maybe we'll

[00:20:25] **Adam:** you'll get there. You'll get there. It'll be a hard-coded file. It'll just be a text file on the domain and it'll be like, here's what you did for tips. Last year, you can

[00:20:36] **Carol:** That's

[00:20:37] **Adam:** the text file and deploy it. And it just pushes that text file up in a Docker container.

[00:20:42] **Carol:** It's a star. It's a star.

[00:20:44] **Ben:** It's so tough though, because I think about it and technically I have all the tools already that I could build this without even dealing with containers and containerization. Right. Cause I could deploy a static site, like an angular site to Netlify and not have to worry about the building can come directly out of GitHub.

[00:21:02] **Ben:** And then I can use something like Firebase as free tier to, to store it all on the giant Jason document. And like, I could make it like, it's so simple that I could make that happen probably with very little effort. I have to remember that I'm doing this as a learning opportunity. Like, I'm choosing the harder path because I wanna, I want to learn the harder thing.

[00:21:24] **Carol:** Right. There are steps you want to know now

[00:21:26] **Ben:** Yeah.

[00:21:28] **Ben:** But I'm super excited to be in a place where the idea of building a container or building an image and then deploying it as a container to somewhere. I want that to be something that feels not second nature, but doesn't feel like a black box.

[00:21:44] **Carol:** Yeah. At least there's an understanding of it. Yeah.

[00:21:47] **Ben:** yeah. And if I could get that, I feel like it would be a very good investment of my time.

[00:21:51] **Carol:** Well, I'm glad we're all winners this week. Yay.

[00:21:55] **Adam:** And you know

[00:21:56] **Carol:** Tim a winner.

[00:21:57] **Adam:** I haven't, registered any domains through CloudFlare, but I like, as soon as they open it up that you could transfer in your domains. I moved everything over that I could,

[00:22:06] **Carol:** All mine moved

[00:22:06] **Ben:** Oh, to CloudFlare.

[00:22:08] **Carol:** Yeah.

[00:22:08] **Ben:** Oh, no.

[00:22:09] **Adam:** Yeah, they announced that they were going to be opening for registration eventually, but then they were like, but in the meantime, you can just transfer everybody in all of your domains and that they support, there's still a few TLDs that they don't support.

[00:22:19] **Adam:** and, yeah, especially because a, their tools don't suck be the company is not awful, like certain GoDaddy other companies. and see, they sell them to you at cost. So like, it's, there's no reason, no good reason not to move it over there as far as I can tell. Except I guess the one thing that I don't like about it is they're like, they're so good right now that everybody's just flocking to them and it's going to become this like single point of failure for the internet.

[00:22:44] **Carol:** So not that we're sponsored by them because that would be great if we were, but also their documentation's really good. So if you start setting up something, a new project and you don't know how to do it, there's so much documentation out there that walks you through everything. You need to do everything like you need to know with, all your settings and just like certificates, all that stuff is out there and laid out pretty easy to read. So,

[00:23:05] **Ben:** Very cool.

[00:23:06] **Adam:** CloudFlare hit us up.

[00:23:08] **Carol:** yeah, we'll talk better about.

[00:23:10] **Ben:** we actually, we use CloudFlare as our CDN at work and we came under a DDoSs attack for the first time that I know of maybe like a month and a half ago. And it's funny because,we're looking at the CloudFlare dashboard and you can see like, it goes from like X number of requests a minute to all of a sudden it's like 8 million requests a minute.

[00:23:31] **Ben:** Yeah. And we're like, what's going on? And we're trying to look at the IPS to see if we can add some sort of ID blocking and some someone finally put like two or three IPS under some, a block list and all of a sudden the traffic totally. And we're like, oh man, this is so great. And then finally someone was like, Hey, those IPS are actually our own internal IPS.

[00:23:50] **Ben:** We actually, but it turned it. So we were like, where are we DDoSing ourselves that we didn't realize it. But it turns out that, CloudFlare had like kicked in some automatic DDoSs protection, like just at the same time. So we thought we had fixed it, but actually CloudFlare had fixed it for

[00:24:06] **Carol:** Oh.

[00:24:07] **Ben:** was really nice.

[00:24:08] **Carol:** Oh, that's awesome. Yeah, they have really good protection up front and you can turn on the settings. They're like, oh, when you're getting hit, what do you want your users to see? And you can configure all that so that it doesn't look so bad to your front end users. They're not just stuck there on a page of nothing responding.

[00:24:24] **Ben:** Yeah, it's interesting. I, so I've only experienced CloudFlare from a CDN standpoint, and now this first domain being purchased. And so I have my, I put my blog behind the CDN and it's just, it's just a blind path through it. Doesn't do anything. It doesn't even catch this. Yeah. the HTML pages or anything,

[00:24:42] **Adam:** So you're on a

[00:24:42] **Adam:** great class.

[00:24:43] **Ben:** is that what that's called?

[00:24:44] **Adam:** If you go into your DNS settings in CloudFlare, you can like, if there's a little cloud icon and if it's gray, then they're just a pass through. But you orange cloud, if you click on it and make it orange, then you get like CloudFlare features.

[00:24:58] **Ben:** Ah, all

[00:24:59] **Carol:** all the alerts and stuff.

[00:25:00] **Ben:** Yeah. See, I'm still learning, but every month I get a email from them then just as like, how much bandwidth did they serve? And it'll say something like, oh, we stopped 146 malicious attacks. And you're like, oh,

[00:25:13] **Carol:** Yeah, glad you were there,

[00:25:14] **Ben:** was, yeah. I didn't know that was going on.

[00:25:16] **Carol:** You like virtual high-fives. Thank you.

[00:25:18] **Ben:** Yeah, absolutely.

[00:25:20] **Ben:** So yeah, good times triumphs trumps all around.

[00:25:24] **Adam:** Thank you.

## [00:25:25] &quot;Love Languages&quot;

[00:25:25] **Adam:** All right, Ben, what grinds your gears?

[00:25:28] **Carol:** just take a minute and talk to us, buddy.

[00:25:30] **Ben:** yeah, so I feel like I've been trying to crush it hard lately at work. And, I made this joke. I thought it was last episode of the previous episode, but like if I crush it in the woods that no, one's there to see

[00:25:42] **Adam:** Yeah.

[00:25:43] **Ben:** I actually crushing it? Yeah. And so we have this, like showcase channel in slack where when people release product features, they'll make a little demo video and a little blurb about what it's doing and I'll drop it in this channel.

[00:25:56] **Ben:** And, and I do that too. And of course I'm the only one doing it from V6. Everyone else is doing it from the new platform. I'm on the legacy platform, V6. And, and it's just like, It's crickets. I'll make a little demo video. And I say like, here's the use case and I drop it in there and I write, this is how much a ARR annual recurring revenue is attached to all of the tickets that have been filed.

[00:26:19] **Ben:** And that's a super loose number. I mean, that's nothing that you could, but it's basically like all the customers who have filed tickets around this thing, this is the amount of money they are paying us, not for that ticket specifically, but this is the amount of money that customer's worth. so we'll say like, oh, this had a, a 500,000 or a million dollars of ARR attached to this one issue and I'm super excited about it.

[00:26:40] **Ben:** And then it's like, like maybe a few people maybe will give me like a thumbs up or a little like party parrot emoji, but no one even drops a comment and it's like, Hey, that's cool. Or, oh, awesome. To remove friction from our users lives. And it's really kind of demoralizing. and. But more than that, it's gotten me to think about it.

[00:27:01] **Ben:** I don't know if anyone's ever heard of the concept of the, of love languages. That there's a famous book called the five love languages. I can't remember what pretty much any of them are, but, uh, like, like, like one is gifts. Yeah.

[00:27:13] **Ben:** Touch

[00:27:14] **Adam:** No gifts is not, oh. Gifts with a T with a

[00:27:18] **Ben:** Oh

[00:27:18] **Ben:** yeah.

[00:27:19] **Carol:** Yes. Memes and guests are definitely a love language. You guys.

[00:27:34] **Ben:** Yeah. Oh, that's so good. That's so good.

[00:27:37] **Adam:** Yeah, I will. I have on occasion said that gifts with no tea is my love language.

[00:27:46] **Ben:** I was thinking about my love language and I'm definitely a compliments person. Gifts don't really mean anything to

[00:27:53] **Adam:** So that would be what words of affirmation.

[00:27:54] **Carol:** Where's the

[00:27:55] **Ben:** Yeah, yeah, yeah,yeah. Words of affirmation. And I think that's like, that's why this is so demoralizing for me is I just want someone to come in and say, Hey man, you did a good job way to go.

[00:28:08] **Ben:** and

[00:28:09] **Carol:** And that's not too much to ask for. It's.

[00:28:13] **Ben:** oh, what? It's interesting. So, so not to just meander all over the place here, but then I was thinking about Carol and now she's stepping into more of a managerial position. and I know we've talked about like personality tests, in previous episodes. and I wonder if the concept of love languages or something to that effect goes into how you think about managing.

[00:28:36] **Ben:** The people that are under you, because there are some people like me who want to hear compliments, and then maybe there's some people who really want to be promoted. And that's how they feel like they're being acknowledged or there's some people who want bonuses and like that's how they feel that they're being acknowledged.

[00:28:50] **Ben:** I mean, I don't, it feels like there's not a one size fits all on a, there's a lot of just stream of consciousness here. But,

## [00:28:56] Managament And Communication Preferences

[00:28:56] **Carol:**

[00:28:56] **Carol:** would that one, that's something I'm facing right now? I have one-on-ones with all my people and I'm like, Hey. I need to better understand how I communicate with you. Like, how do I effectively communicate with you? Because is it, you want to just share jokes every day? And we'll just randomly like, just how's your morning, what you have for breakfast?

[00:29:15] **Carol:** Like, do you want those type of conversations or do you want me to just reach out once a week, twice a week? Like, I'm trying to gauge how these people respond to me better. And I have a very big, like, I have a very wide audience there on, on how I communicate with these people. One of my leads is like, I'm probably not going to tell you when things are going wrong because I just hold it in.

[00:29:35] **Carol:** And I was in your spot before, and I got really tired of everyone throwing everything on my plate. So I'm probably just going to keep things to myself. So it's probably a good idea. If you just reach out to. Every other week and asked me if there's anything that I need to know about, and then I'll tell you, he's like, but I'm going to hold it to myself because I don't want to tax you with something that may or may not be an issue because it could work itself out.

[00:29:58] **Carol:** He's like, so you just need to reach out. And then other people are like, yeah, let's just say hi every day. Cause I just like saying hi to you every day. So you do have to figure out how people communicate. Like that's the first step of all of this is if I can't communicate with my team, then I'm not going to be able to do a good job in any of this.

[00:30:15] **Carol:** I'm not going to be able to make them promotable. I'm not gonna be able to build plans for them on their growth. I have to first figure out how I talk to you in a way that makes you comfortable. And that gets the job done.

[00:30:25] **Ben:** Oh, it's so hard. I mean, to me it's so hard, especially cause I'm very introverted. So the idea of like building a database in my head of how people want to interact, that feels,

[00:30:35] **Carol:** I love it.

[00:30:37] **Carol:** I love it.

[00:30:38] **Adam:** That's why there's spreadsheets.

[00:30:40] **Carol:** Yeah.

[00:30:40] **Adam:** yeah, absolutely. a Trello board because we have so many different customers and, it's like, I need to, talk to any individual person from any individual customer, maybe like four times a year that I need to like reach out and, Reason to do to reach out to them. And so I can't keep all these people straight.

[00:30:56] **Adam:** So I created a Trello board where it's like, okay, each list is a school. And then each card is a person. And if I can find a headshot, I'll put it in there so I can recognize them. And I put like notes in the cards like, okay, this is, this person really likes us and has talked to us about other customer or has talked about us to other people like potential customers, like talking us up.

[00:31:15] **Adam:** I've marked them as like, alumni champion. And, or if, if they're big grudging users, they don't, they only use us because they have to, then I want to know that too. It's like my ownown little CRM, but it's just a Trello board.

## [00:31:27] Personal CRM

[00:31:27] **Ben:** Yeah, I have literally thought of that in the past and thought to myself, this alone would make a really cool product. I don't know what it would be. I mean, cause you could, a lot of this stuff you could do in just a Trello board or, just like a notes app, but that feels like there's something there's a juicy need there in terms of wanting to offline store, all this information.

[00:31:47] **Ben:** That could be interesting. Even just like with your spouse or your significant other you're out at the mall or something and someone remarks like, oh. Pretty bracelet. And then you want to make like a mental note of like, oh, they've mentioned this bracelet. So maybe when some special occasion happens, I can remember that, but I won't remember that because I'd have to write it down.

[00:32:05] **Ben:** I've been barely remembered yesterday.

[00:32:07] **Adam:** Yup.

[00:32:07] **Carol:** what notes are for Ben?

[00:32:09] **Carol:** Open your

[00:32:10] **Carol:** phone

[00:32:10] **Adam:** immediately. You buy it immediately and you keep it at the bottom of your socks.

[00:32:14] **Carol:** You're like, oh, it's pretty. Go get some ice cream.

[00:32:19] **Ben:** no, but I think there's, I think Adam's tapping into something that I think would be useful to a lot of people and probably in a way that they don't even realize would be helpful to them.

[00:32:28] **Adam:** My problem is I would just forget that I had it available to be in. I would never use it

[00:32:32] **Carol:** Yeah. That's what I do with a

[00:32:33] **Carol:** lot of apps. Yeah. I'm like, oh, this is a great tool for organizing like my thoughts while then I never use it again. Or this is a great tool for organizing my contacts with people. Well, then I never use it again. And I go back to just regular contacts and notes on my phone.

[00:32:47] **Carol:** Cause that's what I'm kind of just used to doing.

[00:32:51] **Adam:** There's got to be a good domain name for this.

[00:32:54] **Ben:** I wonder if it's one of those things that could really benefit from prompting. Imagine that, at 8:30 AM every morning, you just

[00:33:01] **Adam:** I can see from your phone GPS location that you're Neal or near a Kay jewelers.

[00:33:06] **Carol:** did you remember your wife wants this bracelet?

[00:33:09] **Ben:** no, no, no, no. I mean a prompting, like if every morning it said, Hey, did anything interesting happen? Whereas like, I don't know what the wording would be. Like, did anything interesting happen to anyone? write it down now. Cause you'll never remember it. And then you can like, oh yeah, you know,Carol just had a, she's on a board for what'd you say you run a board

[00:33:27] **Carol:** band the band, the

[00:33:28] **Carol:** high

[00:33:28] **Carol:** school

[00:33:29] **Ben:** a board for bed. Like I would not remember that.

[00:33:32] **Carol:** Well, don't remember that. Cause I just handed my position over, so it's gone. Let that go.

[00:33:40] **Adam:** And that'll be the one that he remembers

[00:33:41] **Carol:** Yeah. Why don't you the vice president of something somewhere.

## [00:33:46] Other Sources Of Recognition

[00:33:46] **Ben:** Yeah. It's just been, it's I've been feeling so isolated and lonely at work. And I think so much of it is because I just need someone to give me a compliment, like throw me a compliment every now and then.

[00:33:56] **Ben:** So I know that I'm doing a good job. Like I know that I'm doing a good job intellectually, but it's like intellectually is only half the battle. I need a gratuitous.

[00:34:06] **Carol:** Do you have a suggestion box at work because of, so I think I'm going to write to your suggestion box and tell them to compliment you. It's hurting my feelings that you guys are not giving Ben his correct attaboys because he deserves his attaboys. He's doing a good job.

[00:34:24] **Adam:** As a user.

[00:34:30] **Adam:** I dunno. So that's where I'm at. Well, Ben, you are doing.

[00:34:34] **Carol:** I think you're doing a great job.

[00:34:36] **Ben:** I appreciate that. I think the guys on my team who are sort of just, honorarily still on my team, they don't actually do any of the work on my team. they'll tell me that what I'm doing is interesting or fun or cool or whatever, but it's like, I need someone from outside of my bubble to say it, to get that, that like public acknowledged.

[00:34:55] **Carol:** Well, if you want, you're already making the little snippets and have the information, just post them in our amigo channel. We'll at least give you the feedback that says we're proud of you.

[00:35:05] **Adam:** I mean, we do have a triumphs channel frame, some fails post them in there.

[00:35:10] **Carol:** And if it's not public, you could just tell us and we'll say we're proud,

[00:35:13] **Ben:** I mean, it's pretty much all public and then it goes into the product.

[00:35:18] **Adam:** So I almost feel like there might be a little bit of a weird, organizational hierarchy thing to this. Like, I mean, a you're on a team by yourself. So it's, nobody is as aware of it as they would be if they were working with you. But also you were very early into the company. I don't know where you sit in the org chart, but I feel like there's probably not that many people above you that would like make it their own priority to pay attention to what you're producing and,give you that attention.

[00:35:48] **Ben:** yeah.

[00:35:49] **Carol:** But it's going into the channel with all the other engineers work, right? Like it's going in where everyone else is posting there. So if you're setting at a higher tier, typically people under that two year, like push to give that the best feedback, because they want recognition from someone above. So I feel like that's not really totally right.

[00:36:10] **Ben:** It's interesting too, because now, eh, what does it, Gandhi said, be the change you want to see in the world? I think that was

[00:36:16] **Adam:** Yeah,

[00:36:17] **Carol:** Yeah.

[00:36:17] **Ben:** And so

[00:36:18] **Ben:** now

[00:36:18] **Ben:** I'm like being the compliments I want to receive. So every time other people post things, I try to drop in and be like, oh, this looks so great. Or like, oh, this is going to really improve the user experience.

[00:36:29] **Ben:** Like, oh, it's looking so clean right now. And it's like, I'm trying to put the compliments out there hoping that they will come back kind of like efficient board.

[00:36:37] **Carol:** I think that's a great approach. Do you have a manager over you?

[00:36:41] **Ben:** No

[00:36:42] **Carol:** You don't have like anyone who like handles your time off or anyone who handles when you have like people issues, you

[00:36:49] **Ben:** I mean, technically I report to the SVP of engineering. Who's basically the CTO, our CTO left, and this guy is now basically the CTO. Yeah. So I don't report to him in any kind of ongoing basis, but, like my, performance reviews will be with him and, and that kind of stuff. But

[00:37:07] **Carol:** So there's not.

[00:37:08] **Ben:** it's

[00:37:09] **Carol:** On like a weekly basis checking in and being like, Hey, how's it going? Oh

[00:37:14] **Ben:** to have that. I used to have that, but not anymore. none of the legacy platform, those people have all left

[00:37:19] **Adam:** Just, do it to a mirror, like ask yourself how.

## [00:37:25] Assurance From Analytics

[00:37:25] **Ben:** Ah, I mean, one of the, one of the things that is sort of a stand-in is a analytics. So when I build a feature, then plug it into, we use amplitude. I'm a little unclear if amplitude is, I don't know if we send it to amplitude sends it to other places. Anyway, I eventually data gets into amplitude and it graphs it.

[00:37:46] **Ben:** And so every time I build a new feature, I attach amplitude metrics to it. And then I can start to see usage trickling from the users. And like, that's super rewarding because now I feel like people are actually using this and they're hopefully getting value out of it. and I assume, if there's like an initial spike of interaction and then it completely drops off, I'm like, okay, this was just a dud.

[00:38:08] **Ben:** And I'll be super honest about some of the stuff that I build is not great. And it doesn't add compelling value in, whatever. Like you just got to throw a lot of stuff against the wall and see what sticks.

[00:38:19] **Carol:** don't know till you try it.

[00:38:20] **Ben:** Yeah. I mean, I can tell you that a lot of stuff that even as a company, we thought were going to be great, ended up not being great.

[00:38:26] **Ben:** And then stuff that we didn't think was going to be a big deal, ended up being a big deal. Like you just don't know until it's on the page and people are clicking through it and they're either feeling it or they're not feeling it. so yeah, so if I attach the metrics and I can see the metrics continue to be used over time, then it, for me, that's like a compliment of sorts and that's very rewarding and I can see people using it and I feel that, and that's really, that's been very helpful for me. Yeah. So

[00:38:53] **Adam:**

## [00:38:53] Legacy Platform Woes

[00:38:53] **Ben:** it's working on the legacy platform is particularly challenging too, because I think, I don't know if this is true, but I imagine that because the things that I'm building are for the legacy platform, I think people are hesitant to compliment it because it's not the focus of the company.

[00:39:12] **Carol:** Uh,

[00:39:13] **Ben:** feel like by people, especially people higher up in the organization complimenting anything that I do really it, I think it might send not the wrong message. I don't know. I don't know.

[00:39:24] **Carol:** there's an

[00:39:24] **Carol:** unknown for them. Yeah.

[00:39:27] **Adam:** I'm sure there's a feeling of like any investment in the legacy platform. And I'm not saying this like to be mean to you or anything, but like there's a, there's an aspect of throwing money, throwing that money away, right? Like the, you already know you're going to be shutting it down. So it's got a limited lifetime

[00:39:41] **Carol:** But if the, but to me, like if I'm looking at this new release of something on there, my assumption is that the company really thought that this application and the legacy platform should be turned off. There wouldn't be any engineers working on it. So clearly there's a need for this to still may be maintained.

[00:39:57] **Carol:** So someone has to do the job and Ben's doing it. So that's not a bad thing,

[00:40:03] **Ben:** And there's still use, I mean, there's still users on it. That's the thing that keeps me waking up every morning and coming here and trying to crush it at a hundred percent is that there are literally people logging in and still using the legacy platform and like they deserve stuff.

[00:40:18] **Ben:** I dunno what that stuff is, but they definitely deserve it.

[00:40:22] **Carol:** If there were another ones, if it sticks,

[00:40:24] **Ben:** and

[00:40:24] **Carol:** what they deserve.

[00:40:26] **Ben:** and I was in a, I was in one of the support channels the other day. I troll a lot of the support channels looking for inspiration. And, one of the guys was saying, oh, the administrators and some of our teams. We're spending a lot of time doing this one thing that really shouldn't be hard in the system at all.

[00:40:43] **Ben:** And I was like, bro, why did you not tell me about this? And he was like, I just found out about it. I know it's crazy how much time they're spending. and I don't want to go into the details, but I'm like, I can build this. I can literally build this in like an hour to

[00:40:56] **Ben:** fix

[00:40:56] **Ben:** this, to remove that problem.

[00:40:57] **Ben:** So I learned about it on, was like a Tuesday and Wednesday. I had a solution in production. It's not, it wasn't a lot of work and I'm not tooting my own horn here was just like, I just needed to know that it was a problem so that I could build the solution. And I went back and said, Aw, can you please tell your clients that I built this?

[00:41:15] **Ben:** And the guy is like, so heartbreaking. He was like, well, I don't want to tell them that you built this because they're scheduled to move over to the new platform in 17 days. And he's like, yeah, he's like, and I don't know if they will appreciate. Having the solve for them, and then immediately going to a new platform where they essentially get this pain again, because

[00:41:37] **Carol:** Oh, it's not solved over there. Yeah. Okay. That I understand what you're fixing it and then they're going off of it. That piece I do get, but the, the holding it and they got it and you fixed it and now they don't even know you fixed it. That's socks.

[00:41:50] **Ben:** I know that was like, I was like sad, Panda.

[00:41:53] **Carol:** Yeah. I am definitely learning from this. I'm going to make sure as we're transitioning off our legacy to the new app, that our people do not feel this way at all, that they are reminded that their work is valuable and that somebody like our view on this, as somebody has to maintain the legacy system until everybody's off of it.

[00:42:12] **Carol:** And someone may feel like they're held behind because they're stuck on the legacy. Like, we're not for sure who's going to be doing that yet. So we still have to figure out who actually stays back on legacy. Like that's a whole big thing to you. We're going to have to figure out, and I'm going to just do my best to make sure that they know that their job is valued and the work that they're producing matters and that they matter to the company. I don't want anyone to feel like you're feeling.

## [00:42:35] Pros An Cons Of Working On Legacy

[00:42:35] **Ben:** well, and I think there is a kind of a magical part to being on the legacy platform, which is that there's just less people care, which opens up a lot of opportunities. There's a lot of constraints that I have. Like, I can't create new data really, because if I create a new data, like new types of data, then that becomes a whole conversion problem because then they have to figure out how to get that data to the new system.

[00:42:59] **Ben:** So I'm very limited to really just improving the user experience instead of in creating new features. but within those constraints, At least the way I look at it, it's like a no holds barred. It's just have edit, try anything that crosses your mind. And if it works. If it doesn't work, it doesn't work.

[00:43:19] **Ben:** And, worst case scenario, the legacy platforms going away anyway. So they it's very, it's like in that respect, it's really exciting. it would just be more exciting if I got a compliment every now and then on some of the things I was doing.

[00:43:32] **Adam:** Low risk, low expectations.

[00:43:34] **Ben:** Yeah. Yeah, exactly. and this is how I pitch it internally at work, as well as that it's like free user research, meaning that if I build something and people like it, then congratulations, new platform. I just prove this feature for you. And now all you have to do is put it on your roadmap

[00:43:52] **Carol:** You already

[00:43:52] **Ben:** and yeah, exactly.

[00:43:54] **Ben:** it will be a winner.

## [00:43:55] The Cheese System

[00:43:55] **Ben:** So, yeah. but one of the other things. That,I've been thinking about just recently with all this stuff, is that going back to this idea that the one of the customer support people said, Hey, my clients are doing this thing and it's such a waste of their time. And I was like, oh, why did you not tell me this?

[00:44:13] **Ben:** It's really easy to fix? I'm sure a lot of this is because I don't have any managers, so there's not a good workflow pipeline for things that get to me. I, yeah, I do wonder, I wish there was a better way to bubble up what I consider a quick wins. Like how do you support and the support adjacent departments in the company need a way to like, get the little things like the little quick wins somehow mixed in with the larger roadmap

[00:44:44] **Adam:** Jeez.

[00:44:45] **Ben:** and

[00:44:45] **Carol:** Jeez.

[00:44:47] **Ben:** I'm intrigued. Tell me

[00:44:50] **Adam:** Say more. I mean, I'm sure that I brought it up on the podcast before, but, something that we did a lot early on was,we added a status to our ticket system called GS, right. So there

[00:45:00] **Carol:** Oh, yeah.

[00:45:01] **Carol:** Yeah. I remember you talking

[00:45:03] **Carol:** about

[00:45:03] **Adam:** deferred all that. And it's inspired by the west wing, the TV show. So if you haven't, if you've never seen it, then you really won't get the reference.

[00:45:10] **Adam:** But the short version is it's a day where any cause can get an audience at the white house. No, nothing is too small to be paid attention to. and so they call it the big block of cheese day. It's inspired by this whole interject something anyway. In the episode, the national association of cartographers once the, once the administration to like change the official map of the United States or the map that we push out, it was sort of, endorse not to change the land masses, but to use a different projection so that it more accurately represents, the sizes of countries or whatever.

[00:45:45] **Adam:** which is, not something that would ever come across, even anybody that worked in the white house desk, right. That just doesn't rise to that level. so we have that status in our ticketing system and it's like, anybody can feel free to. put anything in our ticketing system and when we triage it, we might go, okay, this is a valid request, but it does not rise to the level of attention right now.

[00:46:05] **Adam:** So we just mark it as GS. And then if you're ever in that situation where you're like, okay, I have two days and no projects. And I know in exactly two days I have to start a new, big thing. So I can't take on a big thing right now, so you can just go grab, okay. I, I'm looking at the cheese and I just go grab little things until I fill my time

[00:46:24] **Ben:** Absolutely.

[00:46:24] **Adam:** and it makes people happy.

[00:46:26] **Adam:** they never know when it's coming, but when they get it, it's a nice little gift.

[00:46:30] **Carol:** So we would have a hard time getting it into the backlog period because the things I imagined been talking about are like workflow issues. It's not Zendesk tickets. It's not like, oh, well there was a little bug here. It's just, oh, this process is very convoluted. And that takes me a long time to get my job done.

[00:46:46] **Carol:** And these steps are why. And my users like,

[00:46:49] **Ben:** I think both though.

[00:46:50] **Carol:** it'd be, it would be great, but I don't think our end users would ever put in a ticket for that. Like that would have to come in from a product complaint, which then has to be prioritized through the product mapping. And then that would come to us. So we get the little tasks that are like, oh, this doesn't look right.

[00:47:04] **Carol:** Or this doesn't work exactly the way, but the changing the workflow. And that's what I thought you were talking about earlier was it was a process that just took a long time. So you fix the process.

[00:47:14] **Ben:** I think one thing that would be helpful, and again, this is very specific to maybe our company is we do get a lot of tickets. for all kinds of stuff, feature requests and frictions and things that are breaking and things that we're working in and are now breaking, regressions.

[00:47:30] **Ben:** And it would almost be super helpful if like, even just once a month, an engineer sat down with someone for support and they just like rapid fire, went down all the tickets to be like, users say that they can no longer change their avatar. And you're like small effort or you're like users would like to log in with Google huge effort.

[00:47:51] **Ben:** You know, users would like to do this. You're like small effort, medium effort, small effort. And then just

[00:47:55] **Ben:** like,

[00:47:56] **Ben:** totally shooting from the hip categorize estimated level of efforts. And then, maybe a couple of days a month or something, or like the hero rotation or the, the on-call rotation, maybe some something where someone could say, let me just see if there were a whole bunch of things here that.

[00:48:12] **Ben:** Estimated, it doesn't necessarily work out that way, but estimated a small effort and see if I can just bang those out, having nothing to do with the feature roadmap at all.

[00:48:20] **Carol:** Yeah. Or you have your cheese items like Adam said.

[00:48:22] **Adam:** yeah. That's what I'm saying is like anything small would be cheese, Yeah. And I mean, I mean, what you're getting at here is that the people that, accept those requests or hear that those complaints don't necessarily know the engineering effort required to correct that. And that's a problem that we all have to learn how to solve.

[00:48:41] **Carol:** think that's all of our companies. Yeah.

[00:48:43] **Ben:** Yeah. This reminds me way back in the day, really early in my career, I was working at this company nylon technology and we sort of specialized in building legal, websites for legal. And every now and then you would get someone saying something's wrong on the site. And they'll send you a PDF where they literally took a screenshot of every page that had the error and like circled it and then scanned it into a PDF.

[00:49:08] **Ben:** I mean, like so much work. And the ended up saying, you have a PDF, it's like 200 pages long. And it was, and it's a mistake inside of a ColdFusion template.

[00:49:18] **Ben:** So it was just, it was the same exact error on every single page, but they didn't realize, yeah, they didn't realize that they'd have to not show you every single instance of it, but it's that kind of thing where, to them, it seems like a monumental effort.

[00:49:31] **Ben:** And then to person who understands how it's technically put together, like that's literally a 32nd fix and I should just do that. I should stop everything that I'm doing. The

[00:49:40] **Carol:** Just fix it real quick.

[00:49:42] **Ben:** and just, and

[00:49:43] **Carol:** Yeah.

[00:49:43] **Ben:** knock it out.

[00:49:44] **Carol:** Being that you put that much effort into creating this ticket for me. I need to just fix this for you.

## [00:49:49] Problems Solved By Git

[00:49:49] **Adam:** do you guys remember the days before get stash save?

[00:49:53] **Carol:** get stash save. I just always do get stash.

[00:49:56] **Adam:** that's a save as the default action. So if you just do get stash, it saves it in your sash. So yeah, I mean, back in the day, when you were like subversion or CVS or any of these guys, like if you were in the middle of a huge project and one of these requests that came in that would take 30 seconds to fix it, there was no good way to set aside everything that I'm currently working on.

[00:50:19] **Adam:** I don't, I'm not ready to commit it yet, but like just set it aside, change. My branch could do a thing, commit it, push it, come back, pop my stash. We are so privileged

[00:50:29] **Carol:** We are, we have no people have no idea. We used to work on something called front page extensions. Do you all know what that

[00:50:35] **Carol:** was? Oh, yeah.

[00:50:37] **Carol:** that was nice. It was amazing. Someone would go on vacation and you would go to do work and you'd have to get like the help desk to unlock all the files because they didn't finish what they were working on.

[00:50:48] **Carol:** They were all still locked to them. Like, well, I just need to fix it. And I can't even get to the files cause they're all locked. So yeah,

[00:50:55] **Carol:** that was

[00:50:56] **Carol:** fun.

[00:50:56] **Ben:** do that. I think Dreamweaver had a mode where you could, instead of reading off the local file system, you could read off of an FTP drive, I think. And it would pull down the FTP file and then it would push up like a file

[00:51:10] **Ben:** name dot lock

[00:51:10] **Carol:** Yep. I'm pretty sure that's what front page extensions did.

[00:51:16] **Ben:** Oh man.

[00:51:17] **Carol:** those

[00:51:17] **Carol:** were the days.

[00:51:18] **Adam:** that we used that was similar to that. I can't remember the name of the program, but it was, yeah, it was like, One central repository and you get like, you get a lock on it. And yeah, that was always the problem. Somebody either they check it in and it doesn't release the lock.

[00:51:32] **Adam:** And so now it's just become this whole big thing

[00:51:34] **Adam:** or

[00:51:35] **Carol:** Or they're gone and

[00:51:36] **Carol:** yep.

[00:51:37] **Adam:** the days, those days are thankfully behind it.

[00:51:41] **Carol:** Oh yeah. Oh yeah. I feel bad for anyone. So working in that environment

[00:51:46] **Ben:** it is crazy. Just how much get and get hub or I think Carol or Tim uses bit bucket.

[00:51:53] **Carol:** please,

[00:51:53] **Ben:** sure they're all, I'm sure they're all, roughly the same,

[00:51:55] **Carol:** We still use get vicious instead of get hub. We use Bitbucket for it.

[00:51:59] **Ben:** it's like to say that it changed work. It's such an understatement. Like, unless you were in the before days, it's like, you don't even understand the degree to which things have changed.

[00:52:10] **Carol:** Yeah. I remember working with Tim to create our, like how we branch and how we release code and how we merge because nobody could get it. Right. And we kept rebasing onto branches and trying to figure out where the history of everything went. And I'm like, well, let's just stop rebasing. There you go. We're on the merge strategy fixed. So yeah.

[00:52:35] **Ben:** yeah. Those early days there would definitely be nightmares.

[00:52:37] **Ben:** People would get into these situations. They couldn't even tell you how they got there. It was like suddenly,suddenly the thing they were working on, which was like three files now had like 75 files that showed a difference. It's like they had somehow rebased on a,a, on a, yeah, like an old thing.

[00:52:55] **Ben:** And then they merged it back in because they panicked and you're like, no, we just have to delete everything you were working on. I'm

[00:53:02] **Carol:** Yeah. Sorry buddy.

[00:53:06] **Adam:** yeah.

[00:53:06] **Carol:** tell you how many times I've sat at someone's desk going. Okay. Let's go to get graphs. Let's start here and see if we can figure out where the lines go, because that's going to point us to kind of what you did. And if there are no lines, you rebased somewhere, so we'll figure it out.

[00:53:23] **Adam:** And the last year or two has gotten a lot better, but I can remember there was several years where it was like, my mantra was like, slow down, calm down. Don't panic because that's all

[00:53:33] **Carol:** And don't push whatever you do just don't push it, like hold your pushing. Nothing gets pushed.

[00:53:40] **Adam:** But fortunately now with GitHub, we have a branch protection on, so nobody can like push directly to main.

[00:53:44] **Adam:** They can always screw up their own feature branches, but,

[00:53:47] **Ben:** Right, right.

[00:53:48] **Ben:**

[00:53:48] **Carol:** That's good.

[00:53:49] **Adam:** yeah. And, but yeah, like, and like I said, it's gotten a lot better over recent years, but there was,a bunch of times where like people would do something by mistake and then they would try to fix it and that would just make things worse.

[00:53:59] **Adam:** And then they'd like merge main into their own branch. And now it's like, sorry, you have to start your whole feature over.

[00:54:07] **Carol:** Love it.

## [00:54:08] Loss Acceptance Side Rant

[00:54:08] **Ben:** a total tangent for a second. So I've I brought this up, I think months ago I bought these reusable ties for wires and

[00:54:16] **Adam:** I have those

[00:54:17] **Carol:** this is the

[00:54:17] **Ben:** yeah. So inside of the tie is I guess Adam called it like a sculpting wire

[00:54:23] **Adam:** Armature wire. Yeah.

[00:54:25] **Ben:** armatures. I said, yeah. So, and I said that I've been playing with it, like bending it back and forth.

[00:54:32] **Ben:** And for me it's a really interesting mental exercise because I know at some point it's going to break because, you can only bend metal back and forth so many times for breaks and it's been. living on the edge a little bit, playing with this wire, waiting for it to break, not yet breaking.

[00:54:46] **Ben:** And it, it literally just, no one can listening can hear this, but like it literally just broke and, uh, and life goes on and like, this is kind of actually an exciting moment because I was doing something that I know would fail at some point and it has failed. And it's like, I sort of leaned into the idea that was going to happen eventually.

[00:55:06] **Ben:** and it's almost like mental conditioning. They're like, yeah, you're okay with that. Be okay with that. You can replace this.

[00:55:13] **Carol:** And you caused it.

[00:55:15] **Ben:** yeah, I don't know. So there's a, I know I'm, if you're not the one here twisting and bending it and then waiting for it to break, maybe it makes no sense, but there's like a, it feels

[00:55:25] **Carol:** It's an expected outcome and you got that expected outcome. And finally, that's how I

[00:55:30] **Ben:** Yeah. Yeah. Yeah. It's like when you see martial arts people, and I dunno if this is just in the movies, but like martial arts, people would take like a wooden dabble and they're running it up and down on their shins by kind of desensitize their shins from being able

[00:55:43] **Carol:** do that.

[00:55:44] **Ben:** And that's what I feel like I'm doing, like, I'm sort of like trying to desensitize a fear by bending this little armature wire until it breaks.

[00:55:54] **Ben:** Okay. Anyway, side rant over, but was a

[00:55:56] **Carol:** that.

[00:55:57] **Ben:** for me

[00:55:58] **Adam:** Cool. All right.

## [00:55:59] Patreon

[00:55:59] **Adam:** Well then this episode of Working Code is brought to you by Ben CRM. For that time, your friend did that thing that you want to remember now available@crushingit.tips. And listeners like you, if you're enjoying the show, you should consider supporting us on Patreon. It's the best way to help keep this show running Patriot and donations cover the costs of editing and recording. And we couldn't do this every week without those things and without your help to pay for those things.

[00:56:23] **Adam:** So we really appreciate all the support that we can get. And of course, special, thanks to our top Patreon, Monte.

[00:56:28] **Adam:**

## [00:56:28] Thanks For Listening!

[00:56:28] **Adam:** So we're off to go record our after show and no tease this week. You're just going to have to listen and find out or become a patron so you can find out,what I'd like you to do. Please tell a friend about the podcast word of mouth. I think, goes the longest of all ways there's reviews and there's this and that.

[00:56:43] **Adam:** But, I think a word of mouth is probably the best possible thing that you can do. So tell your mom, tell your coworkers, tell, your mom's knitting circle. working code Beth podcast ever. We really appreciate it. send us your topics and questions @WorkingCodePod on Twitter or Instagram, you can join our Discord at workingcode.dev/discord.

[00:57:00] **Adam:** you could record a voice memo or even send a text, question to WorkingCodePod@gmail.com.

[00:57:07] **Adam:** that's going to do it for us this week. We'll catch you next week. And until then

[00:57:10] **Ben:** Remember folks, your heart matters.
