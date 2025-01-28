---
title: "020: Carol Needs a Consult"
description: This week, the crew meets to commiserate with Carol on the complexity of email management; and, to help her brainstorm on ways that she might use AWS - and other service providers - to increase Support efficiency while also providing more customer value.
date: 2021-04-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/020-carol-needs-a-consult/id1544142288?i=1000518995897"></iframe>

At Carol's company, Support emails are sorted, labeled, and processed using a manual - _and very expensive_ - workflow that won't be able to scale with the increasing demand. As such, Carol is looking to build a robust auto-reply system on Amazon Web Services (AWS) using machine learning (ML). At least, that's the long-term goal. In the near-term, she'd be thrilled just to get more users to log into the existing web-portal instead of using email as their primary means of communicating with Support.

But, where to begin? This week, the crew meets to commiserate with Carol on the complexity of email management; and, to help her brainstorm on ways that she might use AWS - and other service providers - to increase Support efficiency while also providing more customer value.

**Pro-tip from Carol**: Did you know that GMail ignores _dots_ in the email username? That means that `foobarbaz@gmail.com` and `foo.bar.baz@gmail.com` are _the same address_. Carol uses this to her advantage by signing-up for services using different email variations which she can then use for filtering in the future.

This week's sponsored shout-out is **[TechGirlz][tech-girlz]**, whose mission it is to inspire middle school girls to explore the possibilities of technology to empower their future careers through the creation of free, fun, interactive TechShopz led by industry professionals, leaders, and students.

And finally, don't forget that we are going to have our first book club episode on May 12th for [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). Feel free to read-up and follow along!

### Triumphs &amp; Failures

- **Adam's Triumph** - He just transfered ownership of an old open-source project to fellow ColdFusion enthusiast, [Dan Switzer][dan-switzer]. This project hasn't been touched in about 5-years; and, Adam is thrilled to have the project continue to live-on and remain useful under Dan's watchful eye.

- **Ben's Triumph** - In an attempt to be more agile and bias towards action, he had an idea on Tuesday, implemented it on Wednesday, and then deployed it on Thursday. He cut out all of the "analysis paralysis", over-engineering, and hand-wringing that often accompanies product design. And gosh-darn-it, people are already using it and _getting value out of it_! It feels like a victory.

- **Carol's Triumph** - After using a Windows computer for most of her career, she recently switched over to using a Mac for development. The Mac is nice; but, when she has to switch back to her Windows computer briefly, the key-combinations feel all janky. To remedy this, she remapped her Windows' modifier keys to work like her Mac's modifier keys. She now has a seamless experience no matter which operating system she's on.

- **Tim's Triumph** - After deploying a brand new product, he half expected a lot of bug reports to start rolling in. But, _nope!_ It's been surprisingly smooth sailing. As such, he finds himself just watching the analytics and seeing those sweet, sweet payments get processed appropriately. He was even able to leverage those analytics to drive a 10% increase in conversions through targeted improvements for certain cohorts.

### Notes &amp; Links

- [AWS Lambda](https://aws.amazon.com/lambda/) - Serverless compute resources that scale automatically.
- [AWS SNS](https://aws.amazon.com/sns/) - Simple Notification Service, a fully-managed messaging service.
- [AWS SQS](https://aws.amazon.com/sqs/) - Simple Queue Service, a fully-managed message queue service.
- [AWS Polly](https://aws.amazon.com/polly/) - A robust text-to-speech service that offers realistic, life-like sound.
- [Postmark](https://postmarkapp.com/) - An industry leading email delivery and inbound processing service.
- [`say`](https://ss64.com/osx/say.html) - A text-to-speech synthesis program that ships with MacOS.
- [Seth Bling: Machine Learning for Video Games](https://www.youtube.com/watch?v=qv6UVOQ0F44) - An example of a computer that learns to play Super Mario.
- [Google: Natural Language](https://cloud.google.com/natural-language) - A service helps you derive insights from unstructured text.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[dan-switzer]: https://www.linkedin.com/in/dswitzer/
[tech-girlz]: https://www.techgirlz.org/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/020-carol-needs-a-consult.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:20] **Adam:** Okay, here we go. It is show number 20 for April the 28th, and on today's show, Carol needs a consult. So we're gonna talk to Carol about some stuff she's been working on. And needs some help

[00:00:30] **Carol:** figuring it out. Got a little itch over here, you know. Yeah.

[00:00:34] **Adam:** But first, uh, as usual, we'll do our triumphs and fails.

[00:00:37] **Adam:** And as luck would have it, today's Carol's turn to go first.

[00:00:41] **Carol:** Man, I got the best triumph ever. So I have been using Windows my entire life. Like that's all I've ever used until October when I switched to a Mac. So if you switch between keyboards, you probably have the same muscle memory that I have that.

[00:00:59] **Carol:** Command C, Command A, like all of your commands that you do for normal typing to select your code, to cut things and paste things, it's two different fingers, right? So on a Windows, it's your pinky. You got your, your, uh, is it? Yeah, now I don't even remember. I should look it up. Yeah, it's the pinky. And on Mac, it's my index finger.

[00:01:21] **Carol:** Well, anytime I use my Windows laptop to code the next day. I spend numerous, I spend so much time hitting the wrong button just because my muscle memory kicks right back in. It's like, it takes two days to get back on it. So I did some, uh, some Googling and found a web archive to an old Windows resource toolkit.

[00:01:48] **Carol:** I grabbed it, I installed it on my Windows laptop, and it has the Um, the remap tool in it. So I remapped my control and alt on my windows. So now I no longer have that problem. Anyone else who uses my laptop is going to be pissed. And be like, why can't I copy and paste? I

[00:02:13] **Ben:** actually use a Windows, Microsoft scope.

[00:02:17] **Ben:** keyboard with my Mac. Cause it's ergonomic. I need an ergonomic keyboard cause my

[00:02:21] **Adam:** wrists Those are good, yeah. That's the one where it's like your hands are sort of tilted outwards. And more sideways than straight up and down. It's ever

[00:02:29] **Ben:** so slightly. Yeah. But so I use the Windows key as the, I guess the command key on the Mac.

[00:02:35] **Ben:** It's very confusing to talk about how I type cause I don't actually know what the actual Mac keys are. Uh

[00:02:41] **Adam:** huh. But, um. You've just

[00:02:43] **Carol:** programmed into it. Does it program to it? Like, is there something in there you can do with the, like with

[00:02:48] **Adam:** the no idea. it just works. You can go into the Mac settings and say, you can say, okay, I want to set the button for the command button.

[00:02:56] **Adam:** And then you just push the button on the keyboard and that's what it maps to. It doesn't really matter.

[00:02:58] **Carol:** He's going the opposite way. See, Windows isn't that nice. Windows is like, no. So I had to find an old program to do it. So.

[00:03:08] **Adam:** I know your pain. I, I, uh, this machine that I'm on, DualBoot, uh, between Windows and Mac.

[00:03:13] **Adam:** I only ever go into Windows to play games with my kids, but I know the pain. Yeah,

[00:03:17] **Tim:** that, that remap, that remap key is all I, I know we used to, uh. Back years ago, like probably 10 years before you, you came on at our company, Carol, we, we would like put, put it on people's computer and remap all their

[00:03:33] **Tim:** keys. And then you just hear cursing

[00:03:34] **Adam:** coming out of the next office. They're like, what's going on?

[00:03:40] **Carol:** Yeah. Well, I have a link to it if anyone wants it, I can get it out there to you. Nice. That's me. All right, Tim, what you got going on?

[00:03:50] **Adam:** So

[00:03:51] **Tim:** last week I talked about how we launched that, uh, my new product that we have and it, you know, it finally went live.

[00:03:58] **Tim:** We had a cut over a period where it was, stuff was transitioning over to it and it's been fully live. And anytime you go live with something, you know, there's always a fear that, you know, something uncaught it's going to be happen. It's just going to fall over in its face, but it was so smooth. We just, just perfectly smooth.

[00:04:14] **Tim:** I'm just sitting there watching the users use it and looking at the data streams and, and, and tweaking some, you know, down, down to the little thing. I see people come in and I see how they're acting. I'm like, well, that seems a little odd. Let me fix this. And then immediately get the feedback that, oh, this change, you know, made users, you know, they would jump out of the process at this point.

[00:04:32] **Tim:** Now they're going through the process. And yeah, so yeah, I'm just feeding on that data stream, that lovely, lovely data and just, uh, loving it. So yeah, I'm very. I'm always skeptical every time we launch something new because it's like the chances for it failing is so high. Uh, but this went really well. I, and I a hundred percent credit the success of this to the business user of the client.

[00:04:57] **Tim:** We had a very good, the team that, it wasn't even a team, they had, they had a team and then they just brought one, one lady on who she was, they took the other lady off. And as soon as she came on, Customer and she was extremely good at testing and very good at finding she knew her system and how it worked and she could find all the edge cases to test using.

[00:05:19] **Tim:** Our software. So yeah, if it wasn't for her, the thing, I'm sure we would have ran into a lot of crap. My week would have been complete in misery. But yeah, it was quiet. I had pretty much blocked everything out. And in thoughts that, yeah, the thoughts that I was going to be, you know, playing triage this week, but nope.

[00:05:37] **Carol:** You're like sitting there playing chess at your desk. This is a nice

[00:05:39] **Tim:** week. I'm just sitting there looking at the data going. Yep. Okay. They made a payment. They made a payment. Yep. Okay. They made a payment. Oh, they didn't make a payment. Why is that? Okay. I think we probably should change that. So yeah,

[00:05:48] **Adam:** very happy.

[00:05:49] **Carol:** That's

[00:05:49] **Ben:** awesome. Watching data analytics, I have not done this historically. And since we lost our project manager on our team, I've sort of stepped in as the guy who checks some of the metrics and it's, it's addictive. It's like, it's like a slot machine. Essentially you throw some code into production and then you just start watching to see if anybody touches it.

[00:06:10] **Ben:** And there's almost, it's almost crazy rewarding now to make a tweak in production, not announce it. And then find people discovering it on their own and you start to see those numbers go up. You're just like, Oh, this is crazy.

[00:06:27] **Tim:** Yeah. I ran into that. There was, so I noticed watching this that, so we have two versions, the English version of Spanish version of the, of the program and the Spanish speakers tended to dump out of the process before they made a payment.

[00:06:41] **Tim:** at a certain point and it had something to do with it. They were policy numbers and they kept putting in, they were only supposed to put eight digits of their policy number. They were putting 10 and the program wasn't handling that. So I'm like, all right, they're giving me 10. Let me just look at the first eight.

[00:06:56] **Tim:** Yeah. So immediately put that in and immediately it went from like 20% of Spanish speakers dumping out at that point to 90% of them getting through. Sweet. Uh, so I was super pleased. You're right, you get a dopamine hit, right? Totally. Yeah, you totally get a dopamine hit when you see something like that and you see it coming through.

[00:07:16] **Tim:** So yeah. Nice. How about you, Ben?

[00:07:18] **Ben:** What you got? I'm gonna go with the triumph. I've been trying to focus on being more agile. I don't know if agile is the right word. I was, I've been watching the Sopranos TV show for the first time, even though I know it's like a 20 year old series. And, uh, they have this quote in the show a couple of episodes ago that the, uh, I think it was that indecision is worse than the wrong decision or the wrong decision is better than indecision.

[00:07:43] **Ben:** I can't remember what it was. And I've been thinking about that and going over in my mind and I'm, I'm trying to embrace that more where instead of putting off making decisions, I'm just going to go with a decent decision and see if it pays off. And if it doesn't pay off, then. Hopefully it wasn't too waste, too much of a, of a waste, but if it, uh, it works out, I feel like that's victory.

[00:08:05] **Ben:** And, uh, you know, embracing the idea that wringing my hands and making too many decision trees and weighing too many pros and cons, uh, may be detrimental in the longterm, especially for things that are, uh, are what they would call an Amazon two way doors, where if I go through it and it turns out to be a bad decision, then we can just walk back out the door and it's a no harm, no foul.

[00:08:28] **Ben:** So. I had an idea on Tuesday, like Tuesday morning or something, and then I started to work on it Tuesday afternoon. Wednesday, spent all day working on it, and then, uh, I finished it earlier this afternoon. I just did it. Nice! It felt really good. Go do it. And I didn't know all the details going into it. I had a vague idea, and then as I started to put it on paper, so to speak.

[00:08:53] **Ben:** The idea became more formalized and then the details presented themselves and they were polished and I don't know, I'm just very excited about the

[00:09:01] **Carol:** progress. It's nice to have that freedom to be able to just kind of move around and and work on it that you're not in such a like time crunch all the time that you can't really just play and try because playing and trying is the fun part.

[00:09:16] **Tim:** I feel you and I, Ben, are kind of opposites in that regard. I'm very much the, let's just make a decision. You know, let's not worry about if it's too right or too wrong. And that's, and that's, you know, to be honest, that's bit me in the butt a few times in my life. Uh, I'd rather just make a decision quickly and go forward.

[00:09:36] **Tim:** I think that works good for things that are perhaps low risk. You know, there's, there's certain things, you know, that big decisions, you really got to meditate on and think about and mull over and, and introspect on it. Some, some, yeah, I think you just got to kind of gauge what kind of decision is this. If it's a two way door, like you said, I've never heard that phrase, but that's awesome.

[00:09:57] **Tim:** I'm stealing that.

[00:09:58] **Ben:** You're stealing it from Amazon, not from me.

[00:10:01] **Adam:** You heard it here first. If I stole from Ben, I

[00:10:03] **Tim:** stole twice. So, yeah, I mean, if it's a two way door, then, yeah, don't, don't wring your hands too much about it. Just make a, make a decision that, that feels right, and then, yeah. Walk

[00:10:12] **Adam:** back out, like you said.

[00:10:13] **Adam:** Walk back out,

[00:10:13] **Tim:** yeah. It's awesome. Proud of you. Thank

[00:10:16] **Ben:** you. Thank you. It's very exciting. What about you, Adam? What do you

[00:10:19] **Adam:** got? Well, uh, I'm gonna have a triumph, which, uh, if, correct me if I'm wrong, I think this might be our first episode where all four of us have a triumph.

[00:10:27] **Carol:** We are winners.

[00:10:29] **Adam:** It's been a good week.

[00:10:30] **Adam:** Yeah. Um, I guess there might've been, uh, I'll probably cut this out. There might've been, uh, a week when like Carol was out sick or something and the three of us had triumphs, but that's still not

[00:10:39] **Carol:** four triumphs. That's a failure. I was sick.

[00:10:41] **Adam:** That's a failure. Well, or, or the week you were on PTO. I don't know.

[00:10:43] **Adam:** Whatever. Anyway. So my triumph this week is I transferred ownership of an old open source project to somebody else. Somebody hit me up on Twitter and said, Hey, would you mind if I submitted a pull request? And I, this is a project I haven't touched in multiple years, maybe over five years. Um, and I, I had already marked the repository in GitHub as read only.

[00:11:05] **Adam:** And I, you know, I was never intending to go back to it. And so I just replied to him, this is a person I know, right? We've talked on Twitter before. Um, I just replied like, do you want it? I'll, I'll just transfer ownership to you. And he's like, sure. So I did. I gave him the GitHub project and I added him as a Committer in N P M.

[00:11:23] **Adam:** I haven't removed myself on N P M yet, just because if there's any issues, I wanna be able to help him sort it out. Right. But that, that's a huge win for me. Like it's code that I wrote that is not a hundred percent dead. Somebody else is using it and finding it useful. That's wonderful. Somebody wants say yeah.

[00:11:36] **Adam:** Yeah. Mm-hmm. and, uh, and I don't have to worry about it.

[00:11:38] **Carol:** You might have outlived it, but the code did not outlive you.

[00:11:42] **Adam:** Who did you give it to? Dan Switzer. So what it is, is, um, it's a command line utility that integrates with MX unit, the old C fml mm-hmm. Testing framework. And it adds like a watch functionality to it.

[00:11:57] **Adam:** So more recent, um, testing frameworks that are c l I based, like say jest, um, they have a watch mode. You, you, you start, you write your test, you start the test runner and then as you're write, developing your code, when you save things, the tests run and let you know how you're doing with the code you just wrote.

[00:12:14] **Adam:** And MX unit is old enough that it just didn't have that sort of functionality baked in. It also, it does have like a A C L I output, I think. Maybe? I don't know. But, uh, like I said, I haven't touched this in five years. So my memory is pretty thin. But I just made a very thin wrapper. I added some code to have it be able to spit out the list of tests, and then did some file system monitoring, and run the test suite, and print it out in the console, and run in not, not necessarily a loop, but you know what I mean?

[00:12:43] **Adam:** Like watch mode. And yeah, so somebody found it useful. Still using it. So more power to them.

[00:12:49] **Ben:** I'm a, I'm a huge fan of Dan. Me and Dan go way back, actually. He was, uh. Sort of my brother in arms when it came to a library called XStandard, which was a, uh, an active X component that was a WYSIWYG editor in, uh, in IE.

[00:13:04] **Ben:** And I actually just got an email from XStandard like a month ago that they're shutting down the company because they realized that active X components are not the future.

[00:13:16] **Adam:** They just, they just realized that? They just got the memo? In the last days. Yeah. Dan's a long time

[00:13:24] **Ben:** fan of the

[00:13:25] **Tim:** ColdFusion. We have one like that called Meedco, which is a printing tool for, for IE.

[00:13:29] **Tim:** Yeah, I,

[00:13:29] **Ben:** I actually up until about three years ago, I've been on a Mac for about a decade now. And up until about three years ago, I still had a virtual machine for Windows that I would boot up just to use XStandard to, uh, to write my blog. But before I moved over to Markdown,

[00:13:48] **Adam:** finally.

[00:13:49] **Carol:** The commitment to it.

[00:13:50] **Adam:** Okay. So before we move on. Uh, we have a couple things I guess we should remind you about. Uh, we mentioned a couple episodes back, I don't think we mentioned this last week, that we are doing, we're preparing for our first, uh, Working Code Book Club. How are you guys doing on that? You want the truth? The truth shall set you free.

[00:14:09] **Adam:** I haven't started reading yet. I've did the first three chapters. I've, I've been gathering my materials, right? So I think I mentioned before that I got the book from my local library. I've been talking to some of our listeners in, in different places about it. And it turns out that, um, if you have a Safari book subscription, there's actually, they made it into like this video series.

[00:14:27] **Adam:** It's like kind of. TV episodes sort of thing. So I'm seeing about getting access to that because I'm lazy, right? If I can watch videos instead of reading a book or if I can listen to that, if I can't watch videos, then I'll listen to the audio book. If I can't find the audio book, then I'll get the eyeball book and use my

[00:14:43] **Carol:** eyeballs.

[00:14:44] **Carol:** I contacted my librarian and they were like, oh yeah, oh no, it's actually lost. It shows in stock, but it's lost. It's flagged as missing. And there's only one coffee in the whole state of Georgia.

[00:14:56] **Adam:** Well, yeah, to get mine, I had to have it shipped in from, I think it was from out of state, if I remember correctly, it came from New Jersey, but I have, I have the book from my library and I'm working my way through it, or I will be working my way through it soon.

[00:15:09] **Adam:** If I can get onto Safari Books and watch the, the videos, I would, uh, love to see how that compares to the book and to your guys experience of reading the book, too. Well, I'm listening to it.

[00:15:19] **Carol:** I'm listening to it, too.

[00:15:21] **Adam:** But I also have a PDF copy

[00:15:23] **Carol:** of it as well. I printed out the work stuff and put it in a binder.

[00:15:28] **Carol:** I three hole punched it and everything. Wow.

[00:15:30] **Adam:** Yeah,

[00:15:31] **Tim:** yeah. Gold

[00:15:32] **Adam:** star for you.

[00:15:32] **Carol:** Yeah. I'm liking

[00:15:35] **Adam:** it so far. It's

[00:15:35] **Tim:** highly opinionated, that's for sure. They don't pull any

[00:15:38] **Adam:** punches on this. Oh, I'm looking forward to it. Alright, and then the other thing we wanted to remind you of is we have a hotline where you can call in and leave us a message, and so we just want to make sure we get that number out there that's going to be 512 253 2633.

[00:15:54] **Adam:** That's 512 That's 512 253 C O D E. Um, and we actually do have a message that we just received from good friend Nathan Strutz. It's a nice long message, but we're actually going to hold on to that, and we're going to play that for you in our upcoming listener questions episode, or hey, if we're throwing out options, uh, record a voice memo and email it to us, too.

[00:16:16] **Adam:** Okay, um, so Carol, uh, what's going on? You said you needed

[00:16:19] **Carol:** some help. Yeah, I mean, I figure while I have you guys for, you know, an hour every week, I could just totally steal that as free consult time, right?

[00:16:28] **Adam:** Yeah, captive audience. Yeah, yeah, yeah, yeah. Yeah, we'll bill you.

[00:16:31] **Carol:** Yeah, free, right? I like those numbers.

[00:16:35] **Adam:** I'll double your pay for this week. Still

[00:16:39] **Carol:** nothing. Still nothing. Still free. Still free. Alright so I got added to a really cool project at work. Um, it's a company wide, um, OKR that we are trying to measure. So, what is happening is right now our emails come into our customer service team. And they have to touch every email.

[00:17:01] **Carol:** They have to respond and a lot of them could, could ultimately be handled by just an auto response that says, here's the status. And this is from customer service, you know, telling us that they think easily 40% of their communication. Thank you, Jen. It's just giving someone a status and it's, you know, when is this going to be done?

[00:17:20] **Carol:** When is it going to be delivered? Where is this at? Where we have it in the system, customer service physically logs in, looks at the status, types it in an email, hits send, and then paste it into a communication log. So if we could reduce that, then we reduce costs for customer service and they can actually perform more.

[00:17:41] **Carol:** Like customer related tasks to improve, you know, the quality of, you know, the communication with customers. So we have a few ideas of what we want to do, but everything is going to be in AWS, which is outside of anything I've really ever worked with before. So we're talking about, you know, putting it on S3 and building a SAM stack, and we're going to use Comprehend for the natural language processing side of it.

[00:18:08] **Carol:** And then talking about the S&amp; S, so all the services and messages are going to go through AWS. And all of this is just like... You know, my happy face is on because I love learning new things and I am just taking notes on everything. I'm watching videos. I, I literally have four Chrome windows open and each one of them probably have 20 tabs and I'm so scared something's going to happen and they're going to close and I'm going to have to reopen everything because I just keep, I keep researching and I keep looking at things.

[00:18:37] **Carol:** So what I wanted to kind of talk through tonight was ideas for an auto response. So the thought is to automatically respond with a status, not giving out any information that couldn't basically be, I want to say publicly released, so we don't want to release anything that's sensitive. So to just say, yeah, it's currently in process and we see no delay.

[00:18:59] **Carol:** Like it is being worked and what you were told is accurate. Nothing has changed with that. Or there is a delay. So, if you want more information, like, we can provide you that or reach out to us and we can communicate. Usually, that is enough information to, to get what we need. So, that's the first thing is just figuring out how to get customer service out of their Gmail box.

[00:19:20] **Carol:** And in the system working. So we want them doing everything in the system ultimately. We don't want them in Gmail looking through everything that they're doing. So that's the, the goal out of Gmail and the system. And then me having to learn AWS. So I figured if we could talk through. Some of the things that I don't understand with AWS, just with the whole serverless stack itself, and just understanding, you know, how the heck do you deploy to a non server?

[00:19:48] **Carol:** Like, I, like, I get it. I get the NPN run and, or is it run and deploy, I think. Anyways, I know it's going to put it up there, but it's just mind blowing to me that there's nothing there, that it's not really a thing. I don't know, it's just, I kind of just wanted to talk through it with you guys about ideas on how to do the.

[00:20:07] **Carol:** Other reply, and then also about the technology we had time.

[00:20:12] **Ben:** Well, just one point of clarity. When you say people are emailing your support. Yep. Are they replying to an email? Are they hitting compose and starting a brand new email? How do emails even get into the support inbox?

[00:20:27] **Carol:** Okay, so we have one customer support, um, email address.

[00:20:31] **Carol:** And all of everything is routed in. So depending on who the customer comes from, um, our customers are usually followed by a company email address, right? So like for the example we used before, like edu. So we have, you know, some some very, it's very clear based off the signature emails where a lot of these are coming from.

[00:20:51] **Carol:** So then it gets filtered into other email addresses, which then those customer support teams, then they see it in their inbox. And then those customer support teams log in and they label the emails as the user that's taking it. So if Ben looked in and he was going to take these four emails, he just adds his name as a label to the email and he's like, okay, I'm going to go respond to these.

[00:21:12] **Carol:** And they manually respond to every

[00:21:15] **Adam:** email. Okay, so it sounds like there's one customer support email address, there's rules in that account that look at the sender address. And automatically forward on to different departments, you could call them or whatever, different, um, customer managers or something like that.

[00:21:31] **Adam:** Yeah. Um, and, and then those people handle it and there's teams there and they sort of claim them. They have

[00:21:36] **Carol:** access to it. Yeah. It's all through, configured on the Google side.

[00:21:39] **Adam:** Right. Now, I don't want to, I'm trying not to, like, be that person that's just like, you're doing it wrong, but...

[00:21:46] **Carol:** Oh, we know, we know we're doing it wrong, that's why we're changing

[00:21:49] **Adam:** it.

[00:21:50] **Adam:** I'm just, I have questions that I want to, it'll help inform the way that I respond other ways, so... Okay, okay. It sounds like you have a system that they could go look this up in, but they're being lazy? Is

[00:22:01] **Carol:** that true? Yeah, so... They believe, they think that probably half of the users that email don't even know they're logged into the system because everything they get is just automatically sent back and forth and they can respond via email, text, and just says, yes, I confirm, and then everything just happens.

[00:22:21] **Carol:** So it's not often that they actually have to go into the system to find out this information.

[00:22:25] **Adam:** It's almost like email is one of the ways, the primary ways that they communicate with the

[00:22:29] **Carol:** system. Yeah. And we have trained them bad to allow them to do this. And now we've realized the expense of having to have so many people and so many hands responding to all these emails.

[00:22:40] **Carol:** How

[00:22:40] **Adam:** tied are you to the

[00:22:42] **Tim:** Email workflow.

[00:22:43] **Adam:** You said texting.

[00:22:44] **Carol:** We're not tied to the email workflow. We are tied to it as the system is going to send it to the customer and to our vendor type role people. That's fine. We're good with that. We don't want customer service to have to always be using emails to communicate.

[00:22:59] **Carol:** We want to ultimately drive the users to a web form that says here, here are some options for types of questions. From that, we then can generate more appropriate responses and just log it in the system and have. A lot less touch. So the first step is just, you know, one type that we're going to try to do, which is the status, you know, for all the status requests, we're going to try to just tell you, here's your status.

[00:23:25] **Adam:** And,

[00:23:25] **Tim:** and how tech savvy, I don't know your user base, how tech savvy

[00:23:29] **Carol:** are they? They're usually pretty tech savvy. These are people who are doing, using our software in houses and doing appraisals. So they're out with their iPads, with their phones, scanning everything, putting everything into the system. And then it's, you know, the people processing all that data that's asking

[00:23:48] **Ben:** the questions.

[00:23:49] **Ben:** Okay. Can a user have more than one support ticket open at a

[00:23:53] **Carol:** time? Yes. Yeah, because they can have 10, 000 addresses signed to them at one time because we're talking the customer could be reaching out, which is who owns all of the orders. It could be the middleman who's doing the service on the single address could have the ticket out for that property.

[00:24:12] **Carol:** So, there could also be multiple support tickets out for 1 single

[00:24:16] order.

[00:24:17] **Adam:** Okay, I think I understand the problem. I mean, I don't want to spend the entire hour talking about why you're why you want to do this. Anybody else need any more set up questions? No, I think I think

[00:24:29] **Tim:** I got a pretty good idea of the of the issue.

[00:24:31] **Tim:** Okay. I mean, I My thing would be get them away from email because email is not, uh, interactive, you know, and I'm thinking, you know, like web form, like you said, or something where you could just enter in the, the, there's some sort of, I guess, ticket number or case number, I don't know what you call it, uh, that they can

[00:24:49] **Adam:** look

[00:24:50] **Carol:** at the some type of identifier to it, yeah.

[00:24:53] **Adam:** So

[00:24:53] **Tim:** it's, so it's. Or, or like even like texting, you know, like, like having some sort of, uh, where they can text a number and put it in the, you know, and ask them questions. Oh, that's a really good

[00:25:02] **Adam:** idea. Yeah. SMS is a definite possibility through like something like Twilio.

[00:25:08] **Tim:** Twilio, Plivo, uh, Amazon, if you're using, are you using Amazon, they have texting features as well.

[00:25:13] **Tim:** Yeah.

[00:25:14] **Adam:** So, um, before we get into technology stuff, one thing is you said something that kind of piqued my interest, which was that you are starting with this, um, status use case and um, hopefully it'll go well and you can expand on it from there. And I was thinking you could even take a small bite of that right so whatever you come up with whatever the plan is going to be the first implementation and I'll just throw this out there as you should but you know whatever you're not beholden to any of this think about um implement it but the the output of that implementation is this is what we would do if you turned it on right it becomes like a reporting tool for you to see how well you've implemented the natural language processing and like if you turned it on you What percentage of the messages would it catch and maybe like have it report, this was the message that we received and this is what we would have sent back and and a human can come back and match it up and go, okay, we got like a 98%.

[00:26:11] **Adam:** Accuracy, this is probably pretty safe to turn

[00:26:13] **Carol:** it on, sort of thing. Yeah, what we had thought about with that was, um, for the first kind of cut of it is apply a label to the email. That says, you know, was auto replied or instead of was for this, it would say can auto reply. So then as the user, this is before we actually start auto replying.

[00:26:32] **Carol:** So as the users are actually doing it, they can either choose to leave the label on, so we can go pull all of those threads and see what has the label and has been archived, and we can then have them add another label that says no, or, you know, something that, that, that contradicts that, that says you actually couldn't have, and you thought you could have, and that's not what it was, so then it does give us the ability to see Um, there is a measurable there, I guess I'm trying to say, if we were to do something like that without actually having to, um, interact with anyone yet, so we're not sending out bad information.

[00:27:07] **Adam:** Sounds good. Something I recently

[00:27:09] **Ben:** learned is that if an email client sends an auto responding email, like so and so is out on vacation or out of the office, there's a special header, an SMTP header that they include that will indicate that the email was from an auto responder. Which is great because if you turn on auto responding on your end and some user starts auto responding to your auto response, it's good to have a way to Turtles all the way down.

[00:27:33] **Ben:** Yeah, yeah. It's good to have a way to not respond to certain

[00:27:36] **Adam:** types of stuff. I've

[00:27:36] **Carol:** seen that, yeah, I've seen that happen in ticketing systems with like helpdesks and stuff.

[00:27:42] **Tim:** Yeah, I think probably because my last project, my mind went straight to, you know, some sort of voice phone number or text messaging system because that, that's kind of what I, what I did for this recent thing is people can text a phone number, put their particulars in to identify themselves and then get a status of something immediately.

[00:28:02] **Carol:** I really like the idea of text. I think most of our users would just. You know, because you could even embed it in the response in the email, just click the link and it does that whole pop up your text. And now it's just right there for them. They don't have to fill out anything extra. They just put in, you know, the identifier that we're asking for, because we couldn't auto respond to it to say, hey, we couldn't really get what you were looking for out of this email.

[00:28:26] **Carol:** Can you just give us some more information? And when you text that, then we're like, oh, well, here's your status. There

[00:28:31] **Adam:** you go.

[00:28:31] **Tim:** And, and maybe if, maybe if you, I don't know if you already have like a, a database with their phone number, you could, you could even like identify, you know, when they text, you get the, the phone number that's coming from.

[00:28:42] **Tim:** So you could say, are you, are you calling about. Are you, you know, are you interested in this? You know, and then immediately, um, you know, that way they don't have to enter stuff that you, you know, their phone number.

[00:28:52] **Carol:** We don't, it's not a one to one, so I can't think of a single user that would be interacting with us that has one order in the system because you're talking about doing property appraisals and inspections.

[00:29:03] **Carol:** So you go to 10 houses a day, you go to 10 locations. Right.

[00:29:09] **Adam:** What about, so you said that there's a good chunk, I think you said like 40% ish of the users don't even know that they have an account, right? Is it accurate to say that 100% of users do have an account, whether or not they know about it?

[00:29:25] **Carol:** Yes.

[00:29:25] **Carol:** Everybody has to have an account set up in order to have their license added, in order to be validated that they actually can use the system. But then at that point, they just upload through other systems because sometimes we're just endpoints. And

[00:29:39] **Adam:** then is there a one to one relationship between those user accounts and the email addresses that they're emailing you from?

[00:29:46] **Adam:** Yes. Yep. Okay. So you could theoretically tie back from email address to user account and in your response, you could say, by the way, you know, you could send whatever you're going to send at the top and then underneath that say, by the way, you could have saved yourself the waiting for the response. Just check the status here.

[00:30:02] **Adam:** Here's the URL, here's your username, and here's the forgot password link if you forgot your password. Oh, I like

[00:30:07] **Carol:** that too. Yeah.

[00:30:09] **Adam:** Yeah, I mean,

[00:30:10] **Tim:** ultimately, it sounds like a training, like training the user. Yeah. They've just, they're using email because that's the experience,

[00:30:15] **Carol:** right? Yep, and that's been the thing, it's that we know we've introduced it.

[00:30:18] **Carol:** We know that we caused this to happen because we've handheld them, and this is how we've taught them to get responses. So we want them to see a faster response with an auto response, or a faster response with a web form. Or if, you know, we can get the text part set up, we want to see that be the faster response.

[00:30:35] **Carol:** So they then migrate toward the faster solution. Instead of the slower, which is contacting. Yeah.

[00:30:41] **Adam:** Yeah. And I don't know how. Uh, willing you guys are to have multiple solutions to the same problem, but like, if you can train them to just thinking about what's easiest for them from like an iPad phone situation and also keeps, uh, touches on your side of the, of the process to a minimum.

[00:30:59] **Adam:** If you can convince them to log in and provide their phone number, then you could set up a solution where they can text you, text like, you know, a short code, a five digit number, and say like, status, and then address, or whatever case ID number sort of thing. Um, and you could process that, and okay, okay, you're asking for status, and here's the case number, and then you can reply back with that.

[00:31:21] **Carol:** That is, that's probably my favorite idea of all of this so far, like, and we, like, we've been brainstorming a lot this week, like, One of the things I did today was spent my morning creating the plant UML for all of it so that I have it all mocked out, showing kind of how it's going to interact with AWS and show, or I say AWS, but with everything in AWS and including, you know, the hit to Google's, um, mail app and then back to our system, that stuff.

[00:31:48] **Carol:** I mean, we've, we've put holes in everything we've designed and had to figure out how to get around those holes. Then I had to come up with solutions. So I can't believe none of us thought about a texting solution. Everyone went straight to a web form.

[00:32:05] **Adam:** Well, web form, I think ultimately

[00:32:06] **Tim:** is probably the best thing, right?

[00:32:07] **Tim:** I mean, that's pretty easy. Um,

[00:32:11] **Carol:** I just can't believe none of us thought. They all text .

[00:32:15] **Adam:** Yeah. So,

[00:32:17] **Tim:** I mean, let me ask you, so you, you talk about, uh, S three and a w s and sort of some, perhaps some concern or some excitement about, about doing that. Um, what's, what's the concern with using that other than the fact that maybe you haven't been that exposed

[00:32:32] **Adam:** to it?

[00:32:32] **Carol:** That that is my only concern is that I don't know it. Um, so getting signed in today and, you know, we have a, um, a template that you download from our repo that we've created. That's just like a basic S3 build. Um, so it has like the YAML file in it. You just go through and change a few things and now you have your own.

[00:32:53] **Carol:** Um, is it called an S3 bucket? Am I getting these things right? I have my own S3 bucket up there. And, um, I'm still not understanding how my code connects to it yet, because if we all have our own buckets, how do we all work out of the same branch, but yeah, I'm working locally and it's my own code. How does it get merged in?

[00:33:15] **Carol:** That piece I still have to figure out because my head cannot wrap around that concept yet. So

[00:33:20] **Adam:** there's, uh, one of the problems with AWS is that there's a million ways to do everything. Right. Right. Um, and so it, it's tough to say exactly what that template was going to do. It sounds to me kind of like a, sort of like a cloud formation.

[00:33:36] **Adam:** It is cloud formation. Okay. Um, I have never used cloud formation, but I, I know enough to get myself in trouble. And so basically, I mean, I guess let's break it down a little bit. It's right, S3 is just like storage space that you, that you can integrate with the AWS security model, right? And it's in, and it's in the cloud, right?

[00:33:55] **Adam:** And then buckets are like a map drive, right? And so you can share them, you can share credentials so that you and I both have access to the same bucket, or I can have a private one, you can have a private one, or that sort of thing. Okay. Um, and you can make them world public. Readable sort of thing, right?

[00:34:12] **Adam:** So like, when you upload a picture to Twitter, um, that gets written to an S3 bucket, and that, I don't, I don't think that the entire S3 bucket is readable, but. You can have an object that they call just a file in that bucket set to be public and then you give it the URL and you can read it out of there.

[00:34:29] **Adam:** Okay. Um, so that's S3. Lambda, as you mentioned, it's kind of a funky because, you know, people call it serverless and all this and it's just somebody else's computer, right? Right. It's

[00:34:40] **Carol:** not here.

[00:34:40] **Adam:** Yeah. The easiest way I've found to learn Lambda or to understand how it works At the basic level is to think I take my code and I write a zip, I zip it all up.

[00:34:51] **Adam:** And then you can literally go into the Lambda interface in the console. Wow, that was a lot of stuttering. You can literally go into the Lambda interface in the AWS console and create a function and set the metadata about it, the permissions and what it has access to. And. Whatever memory and CPU usage and stuff and then upload a zip file of your code and that's what runs and then so I guess the next thing that you need to understand is, um, you specify the language, right?

[00:35:17] **Adam:** So you can run Python or Node or whatever.

[00:35:20] **Carol:** Yeah, we'll be in Node and TypeScript.

[00:35:22] **Adam:** Awesome. Um, and then, so you, uh, you give it like a file name, and then that file name has to export an object with, uh, a function named, you can name it whatever, but the, sort of the default is handler, right? So you have index.

[00:35:36] **Adam:** js, and that exports an object containing a function named handler, and then, so you configure your lambda function to say, run index. handler. Oh,

[00:35:43] **Carol:** okay, so I saw this in our, like, in our sample setup, and our, like, guide for how to get it going, because we have this in the guide in our build. So, like, how to get going with it.

[00:35:53] **Carol:** Okay, that makes sense. I was wondering what that was relating to.

[00:35:57] **Adam:** So, and I, you, you talked about how is your team going to be able to do this? And that's, it's an interesting challenge because like I said, there's a million ways to do everything. And I don't know the first thing about how CloudFormation does it, but the way that my team does it is that zip code process.

[00:36:13] **Adam:** We just have our code checked out locally, and then we have a makefile. That, uh, that, you know, it runs the test, it does whatever it needs to do, and then we create a zip file and we call the AWS CLI command to upload that zip file to that lambda function. And that's how we deploy our

[00:36:31] **Carol:** code changes. I know that we're using GitFlow.

[00:36:35] **Carol:** That's about all I know. Okay.

[00:36:37] **Adam:** That's just kind of like a set of rules for how you're going to use Git, if I remember correctly.

[00:36:42] **Carol:** That's the only thing I know. And that's where I was like, this doesn't make sense to me because my head goes around check out code, not have it run locally and then figure out how to put it back together with two other developers, so.

[00:36:56] **Carol:** I gotta figure it out. I'm sure there's some, like, easy solution to it, but my head so far cannot wrap around how it's gonna happen yet. Right. So, yeah. So, I know the Lambda, so the level so far is the Lambda will have the node code on it, if I'm getting it right. The node code on it is actually gonna be handling the communication to, um, to the, the Gmail app to actually get messages and pull them back in and then to send updates to it for labeling.

[00:37:27] **Carol:** Um, and then we will send to a, um, this is a plan, obviously, we're going to send to a, a, um, to a message, so we're going to send a notification out with SNS, and then our system will then get a notification that says they go process this, and then we'll send back, and then we'll do the work on another lambda that'll basically go through and process.

[00:37:47] **Carol:** Now we have found matches, and we're going to autorespond.

[00:37:51] **Adam:** So do you get enough? Email volume that it just makes sense to have that processor, the one that's kind of slurping up all the emails and deciding what to do with them running, like, as a scheduled job every five minutes sort of thing.

[00:38:04] **Carol:** That's what, that's what we're looking at.

[00:38:05] **Carol:** That's what we think. We have a lot of unknowns, so we don't really know yet because. This is outside of what me and the other two engineers that are working on it have done. Um, we're super excited to be working on it and that, you know, we're being given the freedom to go learn it and do it. Um, but we don't know those statistics yet, so we don't know what the stats look like.

[00:38:27] **Carol:** Someone asked me, um, because I wrote a Google Apps script a couple of years ago that runs every hour on my own inbox. And it labels every email I have by domain, so that it basically, if I go into my own email and I click the Amazon label, it gives me every email from Amazon. So I showed that to one of the developers and I was like, hey, this is kind of like what we're doing.

[00:38:52] **Carol:** And like, dude, can, you know, can the Google Apps Script scale? I was like. Don't know. I was like, I'm going to have to go research that because I've only ever used that functionality on my own personal email. I don't, I have no idea what that would look like at our company level. And I don't even know like what type of inbox we're going to be looking at yet.

[00:39:11] **Carol:** So right now we're thinking every five minutes. One

[00:39:13] **Ben:** of the things that we use at work, and I don't know if this would be applicable, but I'm going to share it just because it might be an interesting perspective. Yeah. We use a service called Postmark. Okay. And Postmark is essentially, it's an. It's an, it's almost like an email interface to an API.

[00:39:34] **Ben:** So you send messages to Postmark and Postmark turns around and essentially parses all of the data and then posts it to a webhook. And then you can post to its API and it'll turn around and send out email messages. So you can, instead of, um, instead of having an inbox somewhere that you have to periodically scrape, You can treat SMTP almost like it's just a, like an if this then that style service, and then it turns around and hits your web service to, and you can process that data any way you'd like.

[00:40:11] **Adam:** Yes, I've used Postmark as well. Love it. Great service. It's, it's really awesome. I'll have to look it up. It's a great way to take, um, inbound email. And make it usable and not suck. So like, um.

[00:40:27] **Carol:** That was one of our, that's one of our

[00:40:28] **Adam:** concerns. Yeah, uh, I forget if it was my, must have been my origin story where we talked about that app that I wrote that parsed a whole bunch of different emails.

[00:40:37] **Adam:** Yeah, yeah. I will never, ever forget the pain of just parsing emails sent by different systems. It was awful. Postmark takes all that pain

[00:40:47] **Carol:** away. Yeah. Cause one of the things that we can match on is obviously a location address. So then we're going, well, everybody's signature block has their address in it.

[00:40:59] **Carol:** So we're almost always going to have an address that we're going to have to check against. That's not going to be Valix, it's not going to match an order, but then that's two addresses that's coming back. If we had a way to strip the signature block out up front, I don't know if Postmark can do that or not, but.

[00:41:15] **Carol:** I mean, it sounds like if it can break it apart. Not really. No. Probably not. Never mind. You're gonna get the whole... It's

[00:41:19] **Adam:** still stuck with it. You're basically just gonna get the whole body of the message as like one big text field in a JSON...

[00:41:25] **Carol:** That's, that's what you get with the... Envelope. Gmail app. I mean, with the Gmail, yeah, app too.

[00:41:30] **Adam:** Okay. There are

[00:41:32] **Ben:** certain patterns, though, that people use for signatures a lot. Not, not, not consistently, but like... Two or three dashes followed by a space typically is like a pre signature indicator. So you start to play around with a lot of these rules. Like anytime you see, uh, you know, written from my iPhone, like that's the beginning of a, of an auto responding kind of signature.

[00:41:58] **Ben:** There's all these women. Do people still use those? It's really complicated.

[00:42:01] **Carol:** I haven't seen one of those

[00:42:02] **Adam:** in forever.

[00:42:04] **Ben:** But one thing that I did want to add, and again, I don't know how applicable this is, but it is something that we use with Postmark that's been super helpful for us. Um, they use, they call them mailbox hashes.

[00:42:17] **Ben:** I don't know if that's just a term they used or if that's an industry term, but essentially when you have an email address that say like support at Acme. com, you can typically put something after support, but before the at sign with a plus, you can do like support plus. Case1234 at Acme. com and all of those emails will go to the support inbox and then typically whatever service is receiving those can parse the reply to address and take the plus case1234 out of the email address and then use that programmatically to associate the email with some other, you know, referential data.

[00:42:56] **Adam:** Yeah, that's how Gmail plus address filtering works too. Yeah, that

[00:43:01] **Ben:** revolutionized the way I, I did testing because suddenly I didn't have to have different email addresses. Yes. I just have Ben plus John Doe and whatever and Ben plus Sarah.

[00:43:12] **Adam:** I, I often wonder how many of the nefarious gray area owner email senders are just going, Oh, this is a Gmail address.

[00:43:21] **Adam:** Okay. Strip out anything between the plus and the at. Well,

[00:43:25] **Carol:** not just that, did you know that with Gmail, so like typically I'm like carol. hamilton, you know, did you know the dots and underscores don't matter? You can put them anywhere in your, in your, um, in your name and it'll still come through. So when I do need to create, yeah.

[00:43:40] **Carol:** So like, if I need to like put something in, I know that's going to go to spam, I always do C. underscore, and I do the rest of my email address, and I have a filter that's set to set everything to C underscore, A R O L, to go straight to spam.

[00:43:55] **Adam:** That is

[00:43:56] **Tim:** brilliant. I did

[00:43:57] **Adam:** not know that. Yeah, I used to put in like a dot between every letter just to annoy people.

[00:44:03] **Carol:** Yeah, I like C dot A dot, I forgot how to spell the rest, but whatever.

[00:44:09] **Adam:** So we're consulting with you, but you just taught me something. That's awesome. Yeah,

[00:44:11] **Carol:** look at that. So I'm super excited about using Comprehend. I don't know if you guys have worked with any natural, um, language processors or not. No. But.

[00:44:23] **Carol:** That's some powerful stuff. So we just put some like test data in there and it's like this is, it tells you nouns, verbs, it tells you like the usage to it. Um, it'll find non words. So we're hoping to use some of the non words as identifiers to like, um, like say a loan number or to like, um, an account number maybe.

[00:44:46] **Carol:** So, and then you can set patterns and you can teach it. So like we're going to upload it. 50 examples of different things that we use as the ID and it'll start learning from that and they'll be able to give us like the, uh, scores on how confident it is with everything. Google's does the same thing. I can't remember what it's called.

[00:45:05] **Carol:** I think it's called, I think it's called Natural Language Processor. I don't know, just Google's. So there's a lot of them out there, but it's, I'm excited to be learning that piece of it. Even though it doesn't sound like there's a whole ton to learn, it's just going to be implementing it and watching it grow.

[00:45:21] **Carol:** And then adding some rules and then adding keyword filtering so that we can actually get things back.

[00:45:27] **Adam:** NLP is

[00:45:28] **Tim:** a very cool, I mean, I've never had an opportunity to work on it, but uh, it looks, it looks

[00:45:33] **Carol:** pretty interesting. Yeah, to anyone who wants to try it, um, I'll put a link in to Google's because if you scroll about halfway down the page, they actually have a, a little like interface that you just paste some text into.

[00:45:46] **Carol:** And it'll show you how it breaks it apart. So it'll show you how it came up with the nouns, a verb usage. It'll tell you like what type of, um, IDs it was able to put in there to it. So if it was able to say this was an address, or if they thought this was a phone number, it'll show you how it came up with those keywords to it.

[00:46:07] **Carol:** If you haven't worked with it. Pretty nifty.

[00:46:12] **Ben:** All the machine learning stuff feels like magic to

[00:46:14] **Carol:** me. It is magic. I mean, it has to be magic.

[00:46:19] **Adam:** It, yeah, it's super powerful, but it's also just a little bit scary, right? Like, so we just finished up an election year and machine learning had so much of an effect on our lives for the last two plus years, right?

[00:46:32] **Adam:** Like the, the algorithm for Facebook feed, you're at your homepage or whatever there. And for all the stuff that shows up in your Google news and everything you see on YouTube, that all goes through this machine learning. And the problem with that is Nobody can tell you how it works, right? They give you like, here's all the data and here's the desired outcome.

[00:46:52] **Adam:** Figure it out. And it does, it just tries over and over. It's like, okay, this is trending in the right direction, trending in the wrong direction. And they just train it and it does stuff. And... Like I said it's super powerful and super scary. I just don't

[00:47:04] **Ben:** understand how you feed something a lot of data and it starts making better decisions.

[00:47:09] **Ben:** Like I don't understand

[00:47:10] **Adam:** how it makes that leap. I think I have a good example for this. The first time I really understood what machine learning was doing, I watched a video where a guy used machine learning to have it beat the first world or the first whatever map whatever of uh the original Super Mario's Super Mario Brothers game right so he gave it all right you can wait a certain amount of time before jumping or you can do the the dash button you can you have all the directions that you can hit and it's like these are all your inputs your goal is to make it to the finish gate right to not die this is how you tell when you die this is you know whatever and I imagine there was probably possible for it to Tell like your score, right, from getting coins or whatever, but so And what he did was, as the video progresses, you see all of the runs, right?

[00:48:01] **Adam:** So the game plays and maybe the first time it just walks to the right until it falls down that pit early down in the level, right? No, it's a turtle or a thing, a mushroom. Yeah, yeah. Something. But, you know, you walk to the right and you die. Okay, well, I have to do something before I die there. So, like, it's going to make a decision at that point.

[00:48:18] **Adam:** And it just chooses, it tries every different combination and it's like, okay, well, this is the best one from there. I was able to get the best outcome from there. And so it just keeps. Iterating on that loop. How can I improve from last time? It's kind of how I program. Yeah.

[00:48:35] **Carol:** He's like backspace, refresh, backspace, refresh.

[00:48:38] **Carol:** Yeah. That's probably the best analogy. Like I've been able to like wrap my head around so far with it. Like that's a, something that I can easily see in my head as you're explaining it. So.

[00:48:48] **Adam:** Yeah, it was years ago that I saw it, but I'll see if I can find something that's similar. It's got to be out there.

[00:48:54] **Ben:** This is a total non sequitur, but it just popped into my head because of thinking about this recursive sort of machine learning. But if anyone's listening that didn't know this, in your JavaScript, you can just put in the term debugger. And then when you run your page, your code will freeze on that line and you can go into your dev tools and see the entire call stack of how you got there.

[00:49:16] **Ben:** And that's just hugely helpful sometimes when you don't understand why code is executing.

[00:49:21] **Carol:** Yeah, because it actually stops it. Yeah. So in Chrome, I don't know what I've done, but in Chrome, whenever I, and maybe it's normal now, whenever I reload the page, if I don't have DevTools open, the debugger doesn't stop anything.

[00:49:35] **Carol:** If I have DevTools open, it actually will pause it, and I can like, have the option to step through it, step over it. And I can like, kind of go through it that way. I'm not for sure if I screwed

[00:49:44] **Ben:** something up. No, I think that's, I think a lot of things don't happen if the

[00:49:49] **Carol:** tools aren't open. Okay. So first open your DevTools, then reload the page.

[00:49:55] **Adam:** So I don't know.

[00:49:55] **Tim:** Have we, have we, are we, have we fully consulted with you? I mean, have you been helpful

[00:49:59] **Carol:** at all? Yeah, I mean, you've given me some good ideas and a better understanding of kind of the AWS side that I didn't really understand. Basically, when I think of things in AWS, I treat them as I would if I were interacting with an API, right?

[00:50:14] **Carol:** So I'm going to be sending something over and getting something back. Um, I'm not so much concerned with how it's configured because I mean, my team knows how to do that. Like they've got other, we've got other applications running. We have a whole DevOps team that's responsible for that. I want to learn more, but I'm not going to be super stressed out by, man, I log in and I look at that console window and I'm like, there are so many options for everything.

[00:50:38] **Carol:** What the heck do I choose? Like, how do I allocate resources? And they're like, don't worry about it. We already put in the file for you. Just build it. I'm like, y'all are so mellow about this. And I'm like, So that piece I'm not going to stress about, but I, I think as I learn more, I will, I will like to see how it changes my view on it.

[00:50:57] **Carol:** Like, am I still going to treat it as I do just working with an API? Am I going to be like, here's where I'm sending it to? This is what's coming back. Am I going to change my view on it as I start working more with the services themselves? We'll see. And then I'm excited to be writing some TypeScript. I haven't done that before.

[00:51:15] **Tim:** The only thing I'll find with Amazon is They change things so often. It feels like they really are constantly changing, which is good. I guess they're, you know, they're staying ahead, but it's like, you will find, like, you'll find a use case that, all right, I need to figure out this problem. You'll Google it.

[00:51:30] **Tim:** You'll find an article from two years ago, and it absolutely does not look anything like what it looks like now, and you're like, I

[00:51:37] **Adam:** Options have moved. Yeah,

[00:51:39] **Tim:** options have moved, stuff's in a different order, naming has changed, you know, screen's completely different, uh, so yeah, so that's the only thing I warn you on is don't, don't find some resource that's, that's a couple years old and think, okay, I figured this problem out.

[00:51:54] **Tim:** It's, you know, sometimes just gonna, and their, their documentation is, is lengthy. But

[00:52:01] **Adam:** confusing.

[00:52:01] **Carol:** Yeah. That was one thing I did read. I was like, this just sent me in like a circle and I don't understand, like, it didn't get me any closer. It's frustrating.

[00:52:10] **Adam:** It's very enterprising. Yeah. Yeah. It's, it's,

[00:52:12] **Tim:** yeah, it's very frustrating.

[00:52:13] **Tim:** Cause it's like, you're like, okay, you're explaining this to me, but I don't even understand the context where you're talking about this from. Because like, like Adam said, there's, there's a hundred different ways to do the same thing. So depending on the context you're coming from, it's like, it may not make any sense to you.

[00:52:25] **Tim:** To do

[00:52:25] **Carol:** it that way. Yeah. Yeah. With what they're representing. So one thing you said was, you know, the timeline on, you know, how it's not relevant anymore. I didn't know until, I don't know, probably a couple years ago that when you're searching in Google, you can actually go up to the right and go to settings and you can say only show me search results like for the last six months.

[00:52:47] **Carol:** So when I'm looking for library posts, I'm looking for things that are updated, I constantly change that setting to be like, let me start with relevant. Questions about this and then work my way backwards because I don't want to post that's for a version of a library that, you know, is four versions ago from 2016 that isn't even what I'm using.

[00:53:07] **Carol:** So.

[00:53:08] **Adam:** Well, if it makes you feel any better, I was today years old when I learned that.

[00:53:14] **Carol:** You just found it out. You also can do the, is it verbatim? Like you'd be like, I want this. Don't give me anything. I want

[00:53:21] **Adam:** this. Yeah. I'll, I'll wrap stuff in quotes and use plus and minus all the time, but. I guess maybe, um, I use, I try to use DuckDuckGo instead of Google as much as possible now. Let me see if they have that same option.

[00:53:35] **Adam:** One thing that

[00:53:37] **Ben:** I don't know a whole lot about Amazon because that's usually handled by a lot of our platform people. But one thing that does seem really cool is like, I think everything integrates with their queuing system. So like, this event happens, you can automatically put it in a queue. And like, you get a message from SNS, you can put that in a queue.

[00:53:57] **Ben:** And like, you get something from their data stores and you put that in a queue. Like everything just seems to completely seamlessly integrate with the simple queue service. And

[00:54:08] **Carol:** see, I'm super excited about that because then my failures, I don't have to stress so much about. Because if a service is down, like say, you know, if our endpoint is down or if we're having network issues.

[00:54:20] **Carol:** My messages sit there waiting, right? So I'm not having to go, oh man, go handle all these errors. It's just going to retry it so many times. So I'm excited

[00:54:29] **Adam:** about that. Yeah, it's, it's so daunting. You know, like Carol was saying, you log into the console and you're immediately smashed in the face with You know, 40 of their most recently, uh, released, uh, whatever services.

[00:54:45] **Adam:** I'm like, I

[00:54:45] **Carol:** don't even know some of these, like, I haven't even

[00:54:47] **Adam:** heard of them. I've been using

[00:54:50] **Tim:** Amazon Polly a lot recently for this last project I was doing, which is natural language, speech synthesis, it just, which is amazing what they're doing now with the speech. You can, you can modify it if you want to create a Darth Vader sounding voice, you know, you just type and it will create.

[00:55:08] **Tim:** Yeah, just, just absolutely amazing with what they're doing now with, with speech

[00:55:12] **Ben:** synthesis. Just a fun thing about speech. If you're on a Mac, if you go to the terminal, they have the say command and you can just do say and whatever. And the terminal will just speak using their voiceover narration stuff.

[00:55:29] **Ben:** Holy moly. Which is fun. It's like, it's like when you're a kid and, uh, and someone has one of those electronic dictionaries and you just try to get it to say dirty words out loud.

[00:55:43] **Carol:** And now when I hear my MacBook curse.

[00:55:46] **Adam:** Which for

[00:55:46] **Tim:** you, babe, would be like, darn it.

[00:55:50] **Ben:** Dang.

[00:55:50] **Adam:** So wholesome. Darn it. Oh, this, this

[00:55:53] **Tim:** might be a short show, actually.

[00:55:55] **Adam:** We're at about an hour now. Nice. You know, that's short for us. And I

[00:56:04] **Carol:** update with, you know, some routes we take. And as I run into failures, I'm sure that'll be my failure for, you know, the next few episodes.

[00:56:15] **Carol:** This did not work.

[00:56:17] **Ben:** You discovered a way not to do it.

[00:56:19] **Adam:** Yes. That's right. Okay. Well, it sounds like we're done. So, uh, before we head out of here, let's, uh, remind everybody about our Patreon. So we do have a whole bunch of people supporting us on Patreon and we want to say thank you to all of them. We really appreciate their support.

[00:56:35] **Adam:** If you think we've earned it, please consider supporting us over on Patreon. You can find us there at patreon.com/WorkingCodePod. We have different support tiers with different perks like a lifetime invite to our discord server, early access to new episodes, and the after show where we keep the mics running for another 10 to 15 minutes after the show ends.

[00:56:52] **Adam:** And we get crazy! We also have what we call our top tier on Patreon for people who want to pay a little bit extra. And in exchange they get what we call a sponsored shoutout. And this week's sponsored shoutout is going to go to TechGirlz with a Z.

[00:57:07] **Adam:** techgirlz.org. And to everyone that just listens to the show, thank you for listening. Don't forget to share the show with a friend because there's no better support than a word of mouth referral to help the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[00:57:21] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. Uh, we'll catch you next week. And until then, your heart matters.

[00:57:55] **Carol:** You have a long tongue.

[00:57:57] **Adam:** I was just thinking that Gene Simmons over there. Geez.

[00:58:01] **Ben:** Got a

[00:58:01] **Adam:** short stubby tongue. Oh my god. Alright, alright. We're doing this, right? Like, ahhh. No. We aren't doing it. It comes in handy. For cleaning spoons, right? Exactly. Yeah.

[00:58:13] **Tim:** Aiding the ice cream. Lollipops.
