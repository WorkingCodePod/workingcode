---
title: "030: Carol's Consult Catch-Up Conversation"
description: "Ten weeks ago, in episode 20, Carol described a problem at work in which her customers were using Support Tickets as a means to look-up information in lieu of logging into the customer dashboard. This email-based workflow has been putting a large burden on the Support staff. And, Carol wanted to brainstorm on ways in which she could improve the overall situation and the efficiency of her team. Today, we circle back with Carol to see how it's going. Which is to say, to see just how hard Carol is crushing it!"
date: 2021-07-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/030-carols-consult-catch-up-conversation/id1544142288?i=1000528111182"></iframe>

Ten weeks ago, in [Episode 20][working-code-20], Carol described a problem at work in which her customers were using Support Tickets as a means to look-up information in lieu of logging into the customer dashboard. This email-based workflow has been putting a large burden on the Support staff. And, Carol wanted to brainstorm on ways in which she could improve the overall situation and the efficiency of her team. Today, we circle back with Carol to see how it's going. Which is to say, to see just how hard **Carol is crushing it**!

It's amazing to see how much Carol has accomplished in just a few months. Topics include natural language processing, AWS SAM, AWS Lambda, AWS S3, AWS SNS, AWS EventBridge, AWS CloudWatcher, AWS Parameter Store, Sumo Logic, _and much more_! It's kind of mind-boggling to see it all coming together so quickly.

## Notes &amp; Links

-  [AWS Lambda](https://aws.amazon.com/lambda/)
-  [AWS S3](https://aws.amazon.com/s3/)
-  [AWS SNS](https://aws.amazon.com/sns/)
-  [AWS EventBridge](https://aws.amazon.com/eventbridge/)
-  [AWS CloudWatch](https://aws.amazon.com/cloudwatch/)
-  [AWS Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)
-  [AWS SAM](https://docs.aws.amazon.com/serverless-application-model/index.html)
-  [Sumo Logic](https://www.sumologic.com/)
-  [Jest](https://jestjs.io/)
-  [Kent C. Dodds: Testing JavaScript](https://testingjavascript.com/)
-  [Netlify](https://www.netlify.com/)
-  [JWT](https://jwt.io/)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-20]: https://workingcode.dev/episodes/020-carol-needs-a-consult/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/030-carols-consult-catch-up-conversation.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Yeah, email is just the root of all evil.

[00:00:03] **Carol:** And our email is a big giant. They call it the Plinko board. It's literally what they call it in the back end. That's

[00:00:10] **Adam:** actually a really good metaphor.

[00:00:30] **Adam:** Okay, it is show number 30 for July the 7th and on today's show, we're going to follow up with Carol on episode number 20. She needed a consult and today we're going to find out how things have gone in the last 10 weeks. It's been exactly 10 weeks. So, uh, let's find out what's going on. But first, as usual, we're going to do our triumphs and fails and Ben, it's your turn to go first.

[00:00:48] **Adam:** What do you got? I

[00:00:49] **Ben:** did a thing. What? Congratulations. Yay! I have, uh... I gave a presentation yesterday at the Adobe ColdFusion Developer Conference. That's right. And I was stressed out for basically the last month preparing for it. I give a presentation about once every seven years. So like, uh, the cicadas, it was my time.

[00:01:11] **Ben:** And, uh, I think it, I think it went well. I was, I was pretty pleased. My, my huge fear was that I was going to be done in like 15 minutes and then have another 45 minutes of asking people if they have questions. But I ended up going longer than I thought I would. And then had to sort of skim across a few slides at the end.

[00:01:29] **Ben:** But, uh, overall I didn't stumble too much and I don't think I forgot a lot of things that I wanted to say. So I'm, I was pretty pleased. I'm, I'm going hard triumphed this week. They were, they recorded it, right? Yeah, I think, uh, I think it'll all be available. Um, I don't know when, after the conference, I couldn't even, you couldn't access even the ones that had been recorded already yet, but, uh, I think soon.

[00:01:52] **Ben:** So I will send links around if anybody ever wants to watch it, but, uh, yeah.

[00:01:57] **Carol:** Yeah. Send

[00:01:57] **Ben:** them out. Just spreading the love of Future Flags. Great job. How about you, Adam? What do

[00:02:02] **Adam:** you got? I have a triumph this week as the four, the three of you can see over my shoulder here, that's a stack of my books. Those have finally come in the mail, printed complete.

[00:02:13] **Adam:** It's not a full tree, but so I'm going to be starting the process, finishing the process, I don't know, something. I'm going to be continuing the process of. Finalizing those pre orders, collecting the monies, getting them signed and shipped out. And I'm really excited about that. It'd be cool to have that.

[00:02:31] **Adam:** In the world, like it's in my house. It's, you know, it's, it's a real thing, but nobody else has it yet. I'm excited to get it out there.

[00:02:38] **Carol:** You should send it to us first.

[00:02:42] **Adam:** All right. All right. I can do that. That's exciting though, man. Yeah, that's awesome. Thank you. What's it called? Um, it is called Rest Assured, a pragmatic approach to API design.

[00:02:57] **Adam:** You don't know the title. It's been a long time since I've really had to think about that. I know it's rest assured. And the rest of it was like, I'm pretty sure that's what

[00:03:05] **Ben:** it is. Oh, Taffy got a mention in Charlie Earhart's presentation as one of the, uh, ColdFusion frameworks of note. Nice,

[00:03:13] **Adam:** sweet, flexing those muscles.

[00:03:16] **Adam:** I also started going back to the gym this week, double tramp, now that I'm fully vaccinated and it's been a little while. I'm like, all right, I guess I'm ready for this.

[00:03:25] **Carol:** Was it intimidating for you being around all the people?

[00:03:28] **Adam:** Um, fortunately at my gym, uh, there's not a whole lot of people that go as early as I do.

[00:03:32] **Adam:** I usually go at like in the six o'clock hour. Yeah. In the morning. Oh, dang. Yeah. I mean, I'm, I've got young kids. I've got to get them up for day camp now and school. During the school year. So I'm already up and I've got an hour or two to kill before work anyway. So I might as well go get my workout done.

[00:03:48] **Adam:** So yeah, that hasn't been too bad. All right. Well, that's me. So, uh, Tim, what do you got going on this week? Uh, I got a

[00:03:55] **Tim:** fail. Yeah. Yeah. I mean, it's not really my fault. Well, it is. Okay. It is my fault. I picked it. I was trying to be good. Right. We're so we're having a mid year stretch session. Down in Orlando, all the executors are getting together, going down to Orlando and just spending three days in a rented house, you know, just, just, you know, putting things together and just figuring out how we're going to meet our goals.

[00:04:16] **Tim:** But I chose, I've only flown Delta my entire life. I live in Atlanta. Delta is a hub there. That's the headquarters. Like everything's Delta. I'm like, Oh, you know what? I'm going to save a few bucks. And it wasn't much. It was like maybe 50 bucks. I'm gonna fly Frontier. And a friend of mine, she's, she works for Frontier and I never Flown Frontier and she plays, we play d and d every week together and I'm like, I'm gonna fly Frontier.

[00:04:38] **Tim:** Worse mistake of my life. Oh yeah, yeah. So lemme tell you something I, I. does not let me go to Walmart anymore for fear that I may commit manslaughter. Um, when I lived in different part, different town, I would only go to Walmart at like five or six AM because it was empty. Otherwise, yeah, otherwise, yeah, I, I'm not a people person.

[00:05:06] **Tim:** Amen to that.

[00:05:08] **Adam:** But even less so now after the last year of seclusion. Yeah, for

[00:05:12] **Tim:** sure. And stupid people, poops me over the edge. And I found out that Frontier, as a company, the planes were clean, the service was good, the staff was fantastic and polite and very efficient, but their clientele is completely different clientele from Delta.

[00:05:30] **Adam:** Just saying,

[00:05:33] **Tim:** uh, I, I had to really use a lot of self control to make sure I didn't get punched many, many, many, many times.

[00:05:44] **Tim:** So Frontier, you guys got a good thing going, you know, you, you got, you, you're servicing a sector of, uh, folks that, you know, need to get around, but I don't need to be on your planes.

[00:05:56] **Carol:** I will stick to Delta with

[00:05:58] **Adam:** you. Yeah, for your sake and mine, Delta. Yep. So you said you were trying to save some money. Was that for you?

[00:06:03] **Adam:** Or were you like saving your personal money? Or was it company money? No, no. It

[00:06:05] **Tim:** was company money even. That's a stupid thing. And so I get to this strat session. I tell them my flu frontier and they're like, well, Tim, out of everyone in this group, your number's the best. You could have splurged a little bit more value, tell me.

[00:06:18] **Tim:** I was trying to be good. Yeah. I was just trying to be good, set a good example, you know, be a good leader. Don't splurge. And what, what kills me is I didn't realize that these low cost airlines, I'm sure most of them do this, but that so Frontier, I didn't realize that you can't have a carry on bag without paying for it.

[00:06:35] **Tim:** So I check in the day before and they're like, Oh, you want to carry on bag? So I have a big backpack, which was too big to put under the chair. So now I'm paying an extra 50 bucks. So by the time you added up all the extra, I could have flown Delta for the exact same cost. So, shame on me. I'm not falling for that again.

[00:06:52] **Tim:** Nope. Lesson learned. No, so on the, so yeah, it's an hour on the way out. It's an, it was an hour, you know, to go from Atlanta's short flight on the way back. Orlando's weather is so bad in the summertime. It's like, so I was supposed to get home at midnight. I got home at

[00:07:08] **Adam:** 4:00 AM Oof. Oof. Oh man. Yeah, it was rough.

[00:07:12] **Carol:** Yarr.

[00:07:12] **Tim:** Was your flight just delayed? Yeah, it was delayed, because the weather was bad. I mean, it's not frontier's fault. I don't blame them for that, but it's like, they just have, they won't let them take off in a storm. So there was, it was storming. So it's like, so yeah. So. It's rough. Never again. What about

[00:07:27] **Adam:** you, Carol?

[00:07:28] **Carol:** I'm going to go with the Triumph. I found an extension for VS Code that I am in love with and that has changed my life. Um, it is Spellchecker. It spellchecks everything. If you camel case anything, it checks each individual word in the camel case. Yeah. Yeah. So if I like var something out and I'm like, you know, Text number, like I don't even, I can't think of a, of a name of anything at the moment.

[00:07:56] **Carol:** It will check each piece of the word that I called it, so that is awesome. Yeah, I put a link to it, so

[00:08:02] **Adam:** I'm sharing that with some of my coworkers

[00:08:04] **Carol:** names. Nice. Yeah. , it is the best. And um, so whenever I run it, it basically will just throw up little errors like on the. And you can right click on it and just do view problem and it'll give you the spelling options for you, or you can be like, add to, um, dictionary.

[00:08:24] **Adam:** Very cool. I got to check

[00:08:25] **Tim:** that out because the word disbursement comes up a lot in our variables and I can never spell it

[00:08:31] **Adam:** correctly. You should have like a snippet for it. I know, right? Spell checker. All right. So, uh, but I guess before we move into today's topic, I have a couple of things I want to just throw out there real quick for the good of the order.

[00:08:43] **Adam:** This was also true last week, but since I wasn't here last week, which we'll talk about next, and you guys didn't mention it, I heard, I listened to the show you guys recorded last week. We have an editor now. So a huge, huge, huge thank you to everybody that's donating on Patreon because you are now saving me four ish.

[00:09:03] **Adam:** Thank you. Yes. Yes. Thank you so much of time editing and we're now letting, uh, uh, letting somebody else do that and we're happy to be paying him for that. Heck yeah. And he's doing a good job. Couldn't have done it without you guys. Nope. I think his first episode editing with us was episode number 27. So.

[00:09:21] **Adam:** Um, if I remember correctly, so, yeah. Yeah. Even,

[00:09:24] **Tim:** even nicely cut the cat story from the after show last week. He did.

[00:09:28] **Adam:** He cut that. Yeah. Very nice. Yeah. And he beeped it out. Yeah, he beeped out and I was like, good job. Good job, Matt. Yeah. Cool. And so the other thing I wanted to mention was you guys did a great job without me last week, so thank you for, for giving me that confidence that when it comes up, I know I can take a week off.

[00:09:44] **Carol:** Aw, shucks. Thanks, Dad.

[00:09:46] **Adam:** Carol, Carol was

[00:09:47] **Tim:** a good Adam. She, Carol was a great Adam.

[00:09:49] **Carol:** She's a little nervous. I totally, I totally understand how you flub everything now.

[00:09:55] **Adam:** Cause

[00:09:58] **Carol:** I'm like, I'm like, I need to close my eyes and say all this from memory. Cause I think I would do better if I didn't read it.

[00:10:03] **Adam:** Sometimes it feels that way.

[00:10:04] **Adam:** Yep. All right. Well, let's move on. Uh, episode number 20, 10 weeks ago, Carol needed a consult. We talked about your project and. You've told us a couple of times since then that things are going well. So, what's going

[00:10:16] **Carol:** on? Well, first, I can't believe it's been 10 weeks. Like, that's a long, long time to be on a project.

[00:10:22] **Carol:** And you know, we're still working on stuff with it. Just a recap, if you didn't know what's going on with it, the project was a OKR that was set by the directors of our company. And it was to reduce the touch points on customer communication within like emails, so that our customer service team has the ability to do more customer related work and doesn't spend so much time in an inbox responding to emails that could easily be sent automatically.

[00:10:53] **Carol:** So, I've been working with three other engineers on it, and my part of it was everything related to the Gmail side of the house. So it was getting the emails, creating authorization, parsing it all, sending it over for our natural language processor to actually... Parse through for our natural language processor to do its thing.

[00:11:15] **Carol:** It's comprehend through AWS and then, um, another engineer doing that piece. And then we have the matching side that goes and finds the matches to our system then. So once it parses out like an address, then we go find, does that address exist in our system? And then we had the web form that we're directing the traffic to.

[00:11:33] **Carol:** Um, so hoping that eventually the customer service team will. Be able to reap the rewards by having the clients go directly to the web form, as opposed to using email to communicate. So that's kind of the big picture. Sounds about like everything? I think

[00:11:51] **Adam:** so.

[00:11:52] **Ben:** What does the natural language processing part of it do?

[00:11:56] **Carol:** Yeah, so I send through the body of the message and it goes over it and it finds identifiers. So it'll pull out addresses, it'll pull out names. It basically pulls out anything from it that it feels can be an entity that can be matched to something. So it'll find loan numbers, it'll just send through like an entity and it's.

[00:12:16] **Carol:** other because it doesn't know what that number represents. But then we take that number and we're like, is this a loan number? Is this a tracker number? Is this an order number? And we match it to everything. Where you start having issues is if you go five digits, because that's a zip code, right? So then suddenly.

[00:12:33] **Carol:** If you're at five, you're like, is that a zip code? Does it match the zip code? Does it match the loan number? So you try to say, you

[00:12:38] **Adam:** know, So the use case

[00:12:39] **Tim:** here, trying to refresh my memory, was that people are just emailing a bank, right? And they're in free form. There's no, there's no, and they're, and you're trying to figure out from the context of the email, what it is they're asking for and responding in an intelligent manner.

[00:12:55] **Carol:** Yep. So they're like, Hey, we want to know the status of this. And rather than having a customer service team that we pay, go look it up. We know the status in the system, we just need to automatically respond. And if that's not what you want, here's a web form that you can then be more precise. Is that the word?

[00:13:13] **Carol:** More, more, um, exact on what you're looking for. We'll find a new word for it. So it has options like, Oh, we're sorry if we didn't get this right. Tell us more about what you're looking for. And then we'll try to redirect back with better information. And hopefully, since that response is quicker, because it's taking a couple hours for customer service to get back to someone, if they get that response quicker, go to the web form, get another response back quicker.

[00:13:38] **Carol:** Then they'll stop emailing , hopefully.

[00:13:42] **Adam:** As far as

[00:13:42] **Ben:** the language processor, just curious about this, do you have to tell it what types of data to expect, or do you just send it, you know, on a bridge data and it just sends you back some sort of

[00:13:55] **Carol:** structure? Yep. We haven't given it a whole lot of, like, we haven't did a lot of training on it, and I don't know that we're necessarily going to, at this point, we're actually looking at another one called Malice.

[00:14:07] **Carol:** And I have to go look up the name of it to tell you exactly what this, but it's basically meant for, for doing the processing on actual email communication. So it has already been trained to go through and pull out email bodies and find those actual entities in it. But no, we just send through straight data and it just says, okay, it looks like this and sends it back.

[00:14:30] **Adam:** But do you tell it what to expect at all?

[00:14:33] **Carol:** We haven't told. I, well, I should probably go back and look at everything he's written, but that's another engineer doing that side of it. But I don't think we've done a lot of mapping. I mean, we've told it certain things to avoid, but that's it.

[00:14:46] **Adam:** Okay.

[00:14:48] **Tim:** So I imagine Amazon probably has like a library of, if it's this many characters and it's following this, it's probably a phone number.

[00:14:56] **Tim:** If it's this, it's probably a zip code. If it's this, it's probably a loan

[00:14:59] **Carol:** number. Yeah, and you will get the same information in multiple blocks. So say if you get a number through and it has a pound sign in front of it, um, you'll get the number without the pound sign, you'll get the number with the pound sign.

[00:15:11] **Carol:** So you can figure out which one is like accurate for what you're trying to find.

[00:15:15] **Adam:** And when it provides you some chunk of information like that number or whatever, does it also provide some metadata? Like, I think this might be a credit card number. I think this might be an address.

[00:15:24] **Carol:** Yeah. It'll tell us like address.

[00:15:25] **Carol:** It'll tell us name, person, company. I should probably look up a list of them, but yeah, it does have some and then the rest are just other. So if it sends through that number and it's not five digits, like it would be like. Uh, and then they'll send it through with pound sign with other. This

[00:15:40] **Tim:** isn't like a probability score, like we're 84% certain that this is, yeah.

[00:15:44] **Tim:** Okay. And then you can kind of

[00:15:45] **Carol:** base. Yes, it does do that. So when it sends through a phone number, it's like we're 97% sure this is actually a phone number.

[00:15:52] **Adam:** Yeah. I've played

[00:15:53] **Tim:** with those kind of natural language processing kind of things before. It's pretty, pretty interesting. It just never had a really good use case, but it sounds like you guys are

[00:16:00] **Adam:** using it pretty

[00:16:01] **Carol:** well.

[00:16:02] **Carol:** Yeah, um, Eric is the developer working on that, who worked with us. Eric Reeves, the one that we worked with. Yeah. He worked with us at Silvervine. Yeah, yeah, yeah. He was super excited because he did his master's at Georgia Tech and he did a lot of machine learning when he was working on that. So he was stoked to get his hands back in there.

[00:16:22] **Carol:** And then he was like, man, it's just kind of automated though. Right. Like the connections more work than the... Actual work. That's funny. So, yeah. So from the show, we had discussed some areas that I was struggling with and just kind of didn't have my head around. And one of those was just the infrastructure side of using AWS.

[00:16:45] **Carol:** So, I have been super pleased with just how everything works. Once I figured out, um, the feature branching strategy that we use, and figured out how to get back into develop and how to get back into main, it's so easy to just branch and deploy and everything just runs itself. It, there's no real difference between our normal workflow and how you work when you're working in an, Like a SAMstack, it's all pretty much the same and my hesitation for that is gone.

[00:17:14] **Carol:** So I'm super, super like stoked about that piece. That's awesome.

[00:17:17] **Adam:** So you said you're doing like SAMstack, right? So that would be serverless application model. Yeah. So you're doing serverless functions. You had mentioned before, there's a whole bunch of different, like sort of new to you technologies that you're learning for this, right?

[00:17:31] **Carol:** Yeah. LAMPAS, S3. EventBridge, um, I wrote a CloudWatch timer to basically go through and kick off functions, um, on a schedule. So like we go grab the inbox every five minutes, and then we're using SNS, which is the messaging, I think that's right. And then we're storing keys in the parameter store. So rather than having anything coded in like a template or in like an environment.

[00:17:58] **Carol:** Variable page, it's actually stored in keys and the parameter store. So like, that's where I'm holding a lot of my auth. So then when someone comes in behind me, they don't ever see the auth. They just see that it's a parameter in the store, like in, in the stack.

[00:18:14] **Ben:** Are you then using something like SAM local for the.

[00:18:17] **Ben:** Local development, how does that work?

[00:18:19] **Carol:** Yeah, so we just, um, I don't know all of the tools that are involved with it. Cause basically I just run, uh, like npm run build and then I do a deploy to it. And once it deploys, I just do a npm run and say I'm local and it just builds it all. I do have to be connected to.

[00:18:39] **Carol:** AWS still, like if I network down, then my local stack won't run because I'm dependent on some endpoints just for logging and stuff. Um, and then my S3 obviously can't save if I'm not on a network. But yeah, we're just building with that command. I don't know what that command does. I would have to go actually open package.

[00:18:57] **Carol:** json and see what that command does.

[00:18:59] **Adam:** That's pretty cool. And you, uh, I know in our recent conversations in the, the 10 weeks since that episode, you've mentioned some other things that you're learning for this project too, like you mentioned TypeScript and Jest. Yeah. Some other things.

[00:19:13] **Carol:** Jest is kind of a little crazy.

[00:19:16] **Carol:** I'm learning it. I've written tests around everything I'm doing, but I'm having trouble mocking out some of the connection pieces. So I'm still trying to figure that out because the first thing I did was like, okay, I want to turn the network off because I don't actually want you authenticating. And I don't want you to actually.

[00:19:35] **Carol:** You like, I just want you to mock this JWT my JSON Web Token. I just want you to come back as validated. That's all I care about. And just yes, it's validated. But then once I have that, I don't fully understand how to use that yet to actually test the, like, the create message or to do like send email. And I think it's just going to be more of if this is called, then we're good.

[00:19:58] **Carol:** Like, it should be a, like, is called once or is... I don't even remember all of the stuff. But yeah, it's not so much validating actual data back. It's just going to be the if it actually got hit. And then also, you know, a lot of authorization side work that's been fun and challenging in itself just because we aren't authenticating.

[00:20:21] **Carol:** Directly to Gmail, we're authenticating through, um, a G2, uh, Google Cloud platform. Uh, we created, uh, I did create a service account on a project and then we had to put an app in the app store. So then that service account is authenticated to that app and then that app has users defined to it. So even though that service user has domain wide access, only the users that we've.

[00:20:46] **Carol:** Put into that account, actually have access to the app. So then that prevents anyone from maliciously trying to, you know, get to my email or get to someone else's email using our application. It, it basically another step there. So our GCP team actually has to add a user inbox to the app in order for it to, to be authenticated.

[00:21:07] **Adam:** Cool. Well, if you want to learn more about jest and mocking in particular, and how to like use mocking to your advantage, I can recommend from a course that I've spent my own personal money on, and I would recommend to anybody who's wanting to learn this stuff, testingjavascript. com. Yes. It's, it's not cheap, but it's very worth what you spend on it.

[00:21:29] **Adam:** And he has a whole like module in there for just mocking in general. Nice. It doesn't teach you every little facet of mocking, but it gives you a really solid foundation. Yeah.

[00:21:38] **Carol:** Yeah. Cause that's been

[00:21:39] **Adam:** my struggle. That's the one you said is Kent. Yeah. Kent C. Dodds.

[00:21:43] **Carol:** I'll look it up. Thanks. Cool. Yeah. So I know you guys had some great suggestions from the show.

[00:21:48] **Carol:** I had jotted down a few of them. I don't know if y'all want to talk about them. Sure. So one of the things that Tim has just did was to get away from email. , right. You know, like,

[00:21:59] **Adam:** just get the problem away. Just, uh, , get

[00:22:01] **Carol:** away, get away. And that is the ultimate goal. And that's what we're trying to do, is to get them out of email and get them more trained to do the web form.

[00:22:09] **Carol:** So that's where we're hoping that this actually takes us. Um, we are gonna be capturing data to actually see, um, how much the web forms use and where people stop in the process so we can figure out how to tweak that and make it better too. Yeah.

[00:22:22] **Adam:** Email is just the root of all evil.

[00:22:25] **Carol:** And our email is a big giant.

[00:22:27] **Carol:** They call it the Plinko board is literally what they call it in the

[00:22:33] **Adam:** back. That's actually a really good metaphor.

[00:22:35] **Carol:** And sometimes emails will actually drop in multiple inboxes because they aren't sent to these customer. Teams, they're sent to, you know, customer service at our company. And then from customer service, you then, you know, depending on who you're coming from or, you know, what the domain is, then it gets routed into very specific user group to very specific customer service groups.

[00:23:00] **Carol:** And sometimes those filters don't work, right? So then two teams will be working on the same request. So that's, we're hoping to alleviate some of that too.

[00:23:09] **Adam:** So is this

[00:23:10] **Ben:** actually rolled out?

[00:23:12] **Carol:** Yeah, so what we've done is we have implemented all of the pulling of the inboxes to actually run the NLP on it and have it do our matching.

[00:23:24] **Carol:** So we're getting percentages of matching just kind of as what does this actually look like? Because our customer service team said, you know, we think we can, you know, cut 40% and we're like, well, where did that number come from? Cause. How do you know 40%? Just it's a random number out of the air at this point.

[00:23:39] **Carol:** Right. So what we've done instead of. Rolling out full, like, just send an email and let it all be done. We actually used one of the suggestions that, let's see, someone suggested it. It was Adam. Leaving it as a draft? Yeah, yeah, yeah. Yeah, I think it was Adam. We had talked about just creating a draft response and that's what we've actually done is we are creating the draft, giving it a label that says, you know, auto replied.

[00:24:08] **Carol:** And then I take that label and go look for anything in the sent box that has that label as a number to compare to what we sent over as we're going to send this. And then if they don't send it, then we know our matching was wrong and the customer service team didn't use it. That's awesome. So then they get a chance to put their eyes on it and they're able to give us feedback to go, yeah, this is actually working or man, this is way off.

[00:24:32] **Carol:** And maybe we should just auto respond to everything with here's a link to a web form. Go try again. We're not really going to do that, but sometimes it feels good to just want that.

[00:24:42] **Ben:** That's a really great solution because I, I think when people approach problems, sometimes It's all or nothing. Like, how do I automate this a hundred percent from the beginning?

[00:24:52] **Ben:** And there's no intermediary step that they can see as a value add, but essentially queuing up your support staff with all the information that they need ready to go, and then kind of just having them be that final mile to the delivery. Uh, that's, I think that's super, super clever.

[00:25:08] **Adam:** It's a lot of, uh, is it emotional IQ or something, Ben?

[00:25:13] **Adam:** I think it was you that brought it up. It was either in last week's up show when I wasn't on. Or, or recently, at least, the idea of meeting your customers where they are. Yes. Um, you know, that's, that's a huge thing here. That's what you're doing.

[00:25:25] **Carol:** Yeah. And with that, some of the emails that we have matched on that we think should be status requests, we feel like our customers would be very mad if they got a status request.

[00:25:37] **Carol:** We archive their message and they had to go reply to it again and say, I don't want the status. I want something else. And rather than having that kind of disconnect up front, we thought the draft would be the best way to go so that, you know, there's some human interaction still in this learning phase.

[00:25:56] **Carol:** Because that's what we're calling this is the learning phase of it. Human in the loop. Human in the loop. Gotta be there. What is

[00:26:02] **Adam:** something else that, uh, that we had suggested and maybe you considered?

[00:26:07] **Carol:** Oh, so we did talk about Postmark. Um, you guys had suggested using it and ultimately we decided to not go that route because everywhere that we store our, you, our.

[00:26:19] **Carol:** Data has to be approved by our clients. So that basically put us at another layer of where the data would be written and we would have to get buy in. And the last time we tried to get like Bank of America to approve something, it took like a year. So rather than doing that, we just keep storing where we're at.

[00:26:37] **Carol:** I'm like, I'm not even allowed to store the... Email information in Google Cloud Platform. Like I can't do any storage on that side. That application can't run over there. That's why it's all over on AWS side, because that's where the approval is. Even though they use Gmail, it still would be a new approval process.

[00:26:57] **Carol:** So it's just interesting, kind of the. Agreed upon contracts and stuff that prevent you from doing things that, you know, certain times because I did read Postmark and it seemed like they basically would process the entire email for me and have it ready. And it would have taken a lot of work out. Yeah.

[00:27:13] **Adam:** They basically would act as your, your inbound mail server. It would be SMTP, whatever. And, uh, and instead of Checking that through an email protocol, you just get like a rest webhook. So what, what

[00:27:25] **Tim:** governance

[00:27:25] **Adam:** prevents you from doing that?

[00:27:27] **Carol:** Um, our agreement with our customers. Oh, it's just a contract thing.

[00:27:31] **Carol:** Yeah. Anywhere that we put their data, they have to agree to. So it took us, uh, you know, I wasn't here when all this happened, but it took a while to even get them to allow us to write to S three buckets. Is that a

[00:27:43] **Tim:** banking thing or just a company

[00:27:45] **Carol:** thing, or It's probably a company thing. I can't tell you for sure.

[00:27:48] **Carol:** Okay. Sometimes I just say, yep and move on. And that's one of those already and move ons. Oh. Tim had mentioned something along the lines of hopefully that the solution would train the clients to stop using the email, and I know we kind of already touched on that. Yeah. But that really is where we're headed.

[00:28:08] **Carol:** Like, you know, We've let them do bad things for a long time. So this is our retraining the kid to ride the bike again or something so that, you know, we can interact with them better and more efficiently.

[00:28:22] **Adam:** It's tricky to have those conversations and not be like patronizing. But really, if you're, if you're being completely honest, there's benefits for everybody, right?

[00:28:30] **Adam:** They get their answers faster and. They don't have to write emails and you guys don't have to read emails and yeah, it's just a safe

[00:28:39] **Carol:** time. It's all around. So once we do get the data in and once we get better, um, information on the usage of the web form, we had talked about text communication and giving the users, the op, the clients, the option to text us just a little bit of information.

[00:28:55] **Carol:** And once we have their number saved and have that communication ready, it would actually make the process easier too. So after we find out that the adoption rate of the web form and this whole new workflow, then that's a process that we're talking about implementing if we need to, if we feel that there's there's room to grow it.

[00:29:13] **Carol:** So thanks Google. Oh, I did get into a big challenge that totally Mess me up. When you use Gmail's API to respond to an email, when you do like message create or draft create or message, message send or draft send, it doesn't include the original email body. It only, yeah, you have to go rebuild all of that back.

[00:29:42] **Carol:** So I had to spend time rebuilding it so that it looked. Correct. When it was formatted and I didn't want to have a lot of overhead. So that, that was a little bit of a challenge. And when you're Googling that the problem's been solved, but. Not in a really concise way. So I think I'm going to write something up and post it.

[00:30:02] **Ben:** What's the, uh, what's the goal of including the, the previous body? Cause I, cause I feel like when I use Gmail, they're jumping through a lot of hoops to hide that entire structure for you so that you only see your message. And then all the other messages threaded. What is, if you don't have the original body, what, what functionality do

[00:30:22] **Carol:** you lose?

[00:30:22] **Carol:** Because to say you, I respond to your email and I just say, yes, here it is. Well, if you deleted your email, you don't know what, yes, here it is relates to. You have no other context other than what I put in mine. So it still shows in that condensed form and it still shows correctly in the inbox. But if you don't have the thread in your inbox, it still gets you the full context of it.

[00:30:46] **Carol:** So you can scroll down and be like, what is this even about?

[00:30:49] **Adam:** Yeah, Ben, check your privilege.

[00:30:55] **Ben:** Good point. Good

[00:30:55] **Adam:** point. Uh, yeah, like Carol kind of got to it at the end there, but I was thinking like, yeah, also if you were not originally part of the conversation, if there's been five or six back and forth and then you get forwarded a copy of the message, having that whole history

[00:31:08] **Carol:** there I was like, man, who's really going to need this?

[00:31:10] **Carol:** And then I was like, I would need this because I delete emails all the time. So I'm like, I don't need it. So get rid of it. So if someone responds to it, I'm like. I would know what it was in relationship to. She's getting emails

[00:31:20] **Adam:** as yes. Yes. Well,

[00:31:22] **Ben:** it's funny. I'm, I'm, I'm so used to using Gmail and interacting with other people who use some flavor of Gmail that I completely forget that emails include the whole history with every single email.

[00:31:35] **Ben:** And then every now and then you'll get a, someone will forward you something from Outlook or something, and it'll be like 18 indented emails. And you're like, what? Stonehenge are you coming from? Yep,

[00:31:47] **Carol:** yep, yep. So then the last thing is Sumo. I've, uh... Yeah, what is Sumo? Oh, it's log aggregation. So it's where all of my production level logs, it's like all my logs exist there, but for our, um, AWS permissions for the role, I have to assume the only thing I actually can see on the production stack is the S3 bucket, but I can't see any contents of the file.

[00:32:10] **Carol:** I can just, I can only log in and see the, So I can see the data going in, but I can't do anything with it. So I actually have to use, um, Sumo to go in and see the logs for when my event bridge timers are actually running and when my schedules are triggering and look for any, any like errors in there. So that's been

[00:32:28] **Adam:** interesting.

[00:32:29] **Ben:** And is Sumo, is that an AWS service or that's a different

[00:32:33] **Carol:** service? I don't actually know who hosts it. It's just called Sumo Logic.

[00:32:37] **Adam:** Yeah, I don't think it's an AWS thing. I was thinking that it sounded an awful lot like what I use CloudWatch for. One of the things I use CloudWatch

[00:32:43] **Carol:** for. Yeah, it just consumes our CloudWatch logs and gives us a nice pretty dashboard for it.

[00:32:50] **Carol:** Have

[00:32:50] **Ben:** you had trouble getting any logs out of the various Amazon services that you're using? Or does Sumo pretty much just take care of it? And I ask because at work we use Lambda functions for some things. And I don't know if it's just the way we have things configured, and I don't know if this is true necessarily anymore, but we've for a long time had a lot of trouble getting logs out of Lambda functions into our log aggregation.

[00:33:17] **Ben:** I don't know if that's gotten better.

[00:33:18] **Carol:** I haven't seen any issues with it, but that doesn't mean that they don't exist. So yeah, um. I did find that in my Lambda logs, if I wanted to see what was going on, I went back and added, because basically I throw an error, um, if there's an error going on and I do an error response, because it's, you know, going to come back as an error.

[00:33:42] **Carol:** But I found that if I just do a console log, it's way easier to find it in the logs than waiting for the error response to happen. So I feel like the worst developer ever, because now throughout all of my like little functions, Console. log, console. log, console. log. And then, you know, my gut instinct is like, remove the console.

[00:33:58] **Carol:** logs. I don't need them, but I'm like, I really need this to write to logs while I'm in the learning phase of this still. So,

[00:34:05] **Adam:** then maybe I'll plug here a module. You're in JavaScript, right?

[00:34:09] **Carol:** Yeah, yeah. TypeScript JavaScript,

[00:34:11] **Adam:** yeah. There's a module that I love, and you can get it on NPM. It's called Debug. And basically, the way that it's sold is, there's a couple of benefits from it.

[00:34:20] **Adam:** One is that, I guess, console. log is Blocking, is that the right word? Mm hmm. Yes. And the way that this works is not, so your app doesn't get hung up, you know, printing some huge object or whatever. Nice. Serializing it for display. And also by default, nothing gets printed, but then, so you create different debug streams so you can have like an info of verbose, a debug, an error or whatever stream, and you turn them on with environment variables.

[00:34:49] **Adam:** So, so right. So you have a Lambda function and if you need to debug it, cause something's going on, you just go in and you edit the environment variables and turn on debug. And then your logs now have. That stream in, in the output as if it was console log. Nice. And it's got the, I think it has the, the debugs or the, the stream name Prefixed.

[00:35:11] **Carol:** Cool. I have it open right now. That's cool. I'll have to check it out. Thank you.

[00:35:14] **Adam:** You're quite welcome. I love that one. I use it all the time.

[00:35:17] **Ben:** So as you've started to look into these Amazon web services, Have you been inspired to think about how these new technologies could be used elsewhere in your business?

[00:35:27] **Carol:** Maybe not in the big picture of the business, but yes, um, we are pulling off of our CF app that I was hired to work on and we're going to be breaking that out into, you know, new language, new technology, and just learning the AWS side of it has like inspired me personally to just put everything there.

[00:35:47] **Carol:** It's just so easy. I'm like, if we could just put the services up there, then, you know, it's off CF and, and TypeScript or Endnode, whatever we're going to put it in. And it's just running. So. If you

[00:36:01] **Adam:** do decide to put personal stuff up there, just be careful. Cause it's also really easy to like turn on a thousand dollars a month worth of stuff and not realize it's going on until you get that

[00:36:10] **Carol:** bill.

[00:36:11] **Carol:** Yeah. You can set limits. If nobody knows that you can say, Hey, alert me and shut it down. Yeah. So.

[00:36:18] **Adam:** I was,

[00:36:18] **Ben:** uh, I had referenced in a previous episode what Adam was saying that, uh, meeting customers where they are. And that was said by this guy, Corey Quinn, who helps people understand how they use Amazon Web Services and helps them with their billing and optimization and stuff.

[00:36:32] **Ben:** And one of the points that he made is that if you're a small individual. Your bill goes from $9 a month to $400 a month. You notice that really fast. Mm-hmm. , he's like, but if you're a huge company and you're spending $3 million a month on infrastructure and suddenly that's 315,000, or like, you know, like 3 million and a hundred thousand.

[00:36:55] **Ben:** Right. You're like, nobody will notice that. Yeah. And suddenly you have these companies who have these massive overdone overages, but like they're paying for a ton of stuff. They don't need to, but it's so much money. Yeah. That nobody, it doesn't even trigger any

[00:37:05] **Carol:** alerts. So when I've been doing all my testing, I've been like, can I run all of this?

[00:37:11] **Carol:** Is this okay? They're like, just test it. Stop asking. Leave us alone. I'm like, okay, we're about to process thousands of emails through, you know, the natural language processor. That's

[00:37:24] **Adam:** kind of expensive. It probably has like a really generous free tier too though,

[00:37:26] **Carol:** doesn't it? Uh, I don't think so. No? I don't know that we get anything for free.

[00:37:32] **Carol:** Oh, maybe

[00:37:32] **Adam:** cause you have some sort of corporate account? You're using Comprehend? Yeah, Comprehend.

[00:37:37] **Ben:** Tim, you said you use Polly, right? Does that have a free tier?

[00:37:40] **Tim:** Uh, yeah, it does. It does. I mean, it's, it's, it's pretty low, but yeah, you can, you can play around with it and in Polly and not have to get charged for it, but yeah, once you get over a certain

[00:37:50] **Adam:** level, they start charging.

[00:37:51] **Adam:** So Comprehend does have a free tier and I, I imagine it does. It's like a million invocations or, uh, you know, 10, 000 minutes or something like that a month, a thousand minutes a month or something. And it's just, it automatically comes off your bill. So if you spend less than that in time, then you don't get charged for Lambda at all that month.

[00:38:14] **Adam:** They do that for most of their services.

[00:38:16] **Carol:** I should go learn more about the billing side of

[00:38:18] **Adam:** it. Yeah. I mean,

[00:38:19] **Tim:** Polly's like 4 per 1 million characters of speech. So 1 million characters is a lot. That's pretty

[00:38:24] **Ben:** good. Yeah. Have we talked about Netlify on this show at

[00:38:27] **Adam:** all? I think it's come up, but man, I love Netlify.

[00:38:30] **Adam:** And I have to say, the website, like the best website, workingcode. dev is on Netlify. What? Nice.

[00:38:39] **Ben:** They have, so one of the features that Netlify offers are functions. Which I think is kind of just a lightweight abstraction over AWS Lambda function. That's my understanding. But it's so cool because you basically, in your repository, you just have a functions folder and then the individual files in that folder automatically get deployed as Lambda functions.

[00:39:00] **Ben:** You don't have to worry about it at all. It's

[00:39:03] **Adam:** so clever. I've seen that used for some really interesting stuff. I think that, for example, I think that Wes Boss did something where he used that to like proxy. a request to get his latest Instagram posts and stories to include in the footer of his website because he didn't want his keys, his API keys to be visible, but that's like a statically generated site.

[00:39:25] **Adam:** So the function like does it and I don't know if he calls it a build time or whatever, but then so his, his latest stuff gets included in the footer. And that's very cool.

[00:39:34] **Ben:** I played around with it just once. Um, and I, like you're saying, you can have environment variables that you have in your build process or, or I shouldn't say build process, but they can be exposed to the lambdas.

[00:39:46] **Ben:** And, uh, I was using it to proxy uploads to S3. So the site, the static site could post through the, it wasn't posting through the Lambda, it was calling the Lambda function to get a pre signed URL. And then the, then the browser was using that URL to upload to, uh,

[00:40:02] **Adam:** to S3. I've done that. So you can do, yeah, you can have S3 uploads that go directly from the browser to S3.

[00:40:09] **Adam:** Without going through your server and then you can optionally even have it sort of redirect after the upload to a page on your site with like, um, information in the, in the post body or in the URL to say, okay, the file was uploaded. Here's the name and here's some other attributes so that you can store.

[00:40:26] **Adam:** I've done that in some places. It's

[00:40:28] **Ben:** nice. Netlify is just cool. And I think they have a whole bunch of stuff. I feel, I feel so behind. This is what happens to me with a lot of services is I'll discover something and I'll be like, Oh, this is so cool. It has one feature. And then I'll look up like four years later and I'm only still using that one feature.

[00:40:45] **Ben:** And now they have like a huge suite of products that they offer. And I didn't even realize that they had evolved so fast.

[00:40:50] **Adam:** And just

[00:40:50] **Carol:** scrolling through the site, they have so much.

[00:40:52] **Adam:** On Netlify. Oh, I love Netlify. It's badass. They good. And, and you know what, if they wanted to sponsor us, call me. I would absolutely hawk your stuff, wear your socks.

[00:41:06] **Ben:** Netlify is definitely one of those services that I feel guilty not paying for because they have such a generous free tier. And like, normally I wouldn't care because it's just one of those things you dabble with occasionally, but they just make it so easy to deploy stuff out of a repository. You're like, uh, I don't, I don't feel good not paying for this.

[00:41:23] **Adam:** No, I mean our, the website, the, the Working code website is up there. The website for my book is up there. I've got a couple of like, uh, you know, other websites up there. Nice. Alright. Is there anything

[00:41:35] **Carol:** else? That's about it. The project's

[00:41:38] **Ben:** good. I do have one question. You, you mentioned, uh, in the, in your, in your document here, JWTs Jots.

[00:41:44] **Ben:** Yeah. And off, where, where are Jots

[00:41:46] **Carol:** coming into play? Okay, so we have a service account tied to our G C P app, our, and. I use the Google authentication to create the JWT for the service account. And then once I have that JWT, that's how I authorize that service account to then go pull those emails for all those customer service accounts.

[00:42:08] **Carol:** So it's the, the, the authentication for the app. And then you to get to Gmail because Gmail requires you to authenticate if you're a user with, um, that two factor authentication where you have to actually click yes, I'm giving you access to it. And we don't want our customer service team to have that decision, that decision on them.

[00:42:31] **Carol:** That's on our company. So we use, I use the service account to create that. Hmm.

[00:42:37] **Ben:** And is that something you provision once and then that gets stored somewhere or is that provisioned?

[00:42:42] **Carol:** Over and over again. So I just create it. And rather than doing refresh or anything, we just go pull it again. And since it's using private key to generate it, then it's just always the same.

[00:42:52] **Adam:** So I wanted to ask you about this. What's, what is your opinion of using a JWT, uh, as an authentication mechanism for an API or however you're using it, if it's for SDK or whatever, because. I've never actually used one like in production. I've just kind of read about them and gone, ew, and decided not to go that way.

[00:43:12] **Adam:** Um, so like, I'm curious, how do you feel about

[00:43:15] **Carol:** them? I don't know that I feel strongly either way. Ultimately I'm using the, like I installed the package for Gmail through NPM. So it gives you the option of, you know, OAuth. To, you know, a couple of things that they have and JWT client is one of them. So I don't have the option of creating a I don't have the option to create any other type of authentication for the service account to have access to the app for it to have, I have to use a JWT.

[00:43:47] **Carol:** So if I didn't have to use the JWT, the JSON Web Token, I would go another route just because it's easier to implement. Okay.

[00:43:56] **Adam:** So, You're fine with it because you have to, but you wouldn't choose it if you had another

[00:44:00] **Carol:** choice. Yeah. Yeah. If any other client was available, then that's what I would have used.

[00:44:05] **Adam:** That's kind of how I feel too.

[00:44:07] **Carol:** They're not terrible. I mean, they're secure. It's not a problem. They're totally fine. It's just...

[00:44:12] **Adam:** Are you refreshing them often? Yeah.

[00:44:14] **Carol:** With

[00:44:15] **Adam:** every hit. Okay. So you're getting a fresh one every time.

[00:44:18] **Carol:** There's no reason to keep it.

[00:44:22] **Adam:** It's

[00:44:22] **Ben:** definitely one of those things that I think when they became very popular like five, six years ago, I think people maybe started to use them for things that weren't necessary for like, Oh, I don't have to have cookies anymore. So I'll just use Jots instead of cookies. And then you realize like cookies was just super easy and not problematic.

[00:44:44] **Ben:** But I do see it used as like service to service calls a lot.

[00:44:49] **Adam:** The thing that I have seen and used it for where I found it actually useful is to just do like, I want somebody to bounce off of my authentication service and I will provide something that says, this is the person that they're saying they are, you know, like, like me being an SSO provider to somebody else.

[00:45:07] **Adam:** Right. Not for an API, but just be like, Ben, this is Ben. Here's his rules and I'm, uh, signing this response or whatever to, to verify that

[00:45:20] **Carol:** that's the truth. And that, I mean, that's exactly what we're doing. As we're doing, it's a service to service. At the end of the day, it's application to application. It's not...

[00:45:28] **Carol:** and user agreement. So

[00:45:30] **Adam:** I did it for, uh, so we have a tiny little JavaScript app that we use for onsite check-in at small events like, you know, at the gate, at a football game for the v i p room, box seats or whatever. Vip, right? Mm-hmm. , yeah, Or at, uh, uh, like a, a happy hour at a bar where you're only expecting, you know, 12 people to show up or whatever, but.

[00:45:52] **Adam:** Uh, in order to sign into that application, basically our requirements were, uh, you know, the person has to be a user of our core application. Um, and have a certain role. And so what I did was they, they get to the app and then when they click on the login button, it redirects them to our normal application to a special URL, right?

[00:46:10] **Adam:** Like a deep link, right? So then, oh, you're not logged in. So I show you the login page. And then after you log in, it redirects you to the thing which says, okay, you want. Yeah. I

[00:46:20] **Carol:** hate saying it, I say

[00:46:24] **Adam:** JWTs. I've always said JWT. Uh, so you want a JWT and you want me to send you, send it back to this URL. And so it sends it back to my JavaScript app for the check in and that's how it's okay.

[00:46:34] **Adam:** You're this person and. Yeah. So, yeah, I just realized, I realized, I

[00:46:38] **Tim:** realized I don't have a whole lot to say. I'm so tired from getting in at 4 a. m. this

[00:46:42] **Adam:** morning. I did all

[00:46:43] **Carol:** the talking this time.

[00:46:44] **Adam:** That's good. Cool. Carry the show. Yep. Thanks, Carol. All right. So, uh, if you like what we're doing here, you might want to consider supporting us on Patreon.

[00:46:52] **Adam:** You can find us there at patreon.com/WorkingCodePod and new this week, actually new last week, but you guys didn't mention it. So I'm going to give them a mention this week. Bill, welcome aboard. Thanks for joining the crew. And, uh, glad to have you on. Welcome aboard. Heck yeah. Every patron gets an invite to our Discord server.

[00:47:07] **Adam:** So Bill, make sure you are on Discord. I don't recall seeing you there, but maybe you're there. Um, and, uh, we have other perks available like early access to new episodes and the after show. And, uh, our top tier on Patreon is for people who want to pay a little bit extra and to repay the favor. We thank them by name or shout out something in their honor.

[00:47:24] **Adam:** Uh, this week we still have two top patrons. So thank you to Peter and to Monte. And hey, if Patreon isn't your thing, then thanks for listening anyway. We appreciate having you here with us. You could share the show with your friends and co workers because, let's be honest, almost nobody searches podcast directory, so we really need your word of mouth referrals to keep growing.

[00:47:41] **Adam:** And you can also leave us a rating and a review on iTunes or wherever you get your podcasts so that maybe one day we'll rank first when you search for the name of our podcast. Please send us your questions and your topic Suggestions on Twitter or Instagram at WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week, and until then...

[00:48:05] **Tim:** Remember guys, your heart, it really matters.
