---
title: "138: Ben Goes Streaking"
description: "As Ben builds-out Dig Deep Fitness, he wants to include an 'Activity Streak' indicator. As such, he turns to his brilliant Working Code co-hosts for their sagely advice."
date: 2023-08-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/138-ben-goes-streaking/id1544142288?i=1000623163520"></iframe>

As Ben builds-out [Dig Deep Fitness][dig-deep-fitness], he wants to include an "Activity Streak" indicator as a way for people to feel good about the consistent effort that they've been putting into their workouts. "Streaks", however, are bucketed by "day"; and, said "day" is specific to the user's current timezone experience. Historically, Ben has stored all of his application dates in UTC time; but, he senses that this won't be appropriate for "Activity Streak" tracking. As such, he turns to his brilliant Working Code co-hosts for their sagely advice.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[dig-deep-fitness]: https://www.digdeepfitness.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/138-ben-goes-streaking.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** What if you do your workout, but you forget to log it until tomorrow?

[00:00:03] **Ben:** So a tough one. That's a tough one. Okay. Well, yes. I don't know. I don't know. That's, that's a user error.

## [00:00:33] Intro

[00:00:33] **Adam:** Okay, here we go. It is show number 138 and on today's show, Ben's going streaking, or so I

[00:00:38] **Carol:** Close your eyes.

[00:00:40] **Adam:** we'll find out what that means in a little bit, but first, as usual, we will start with our triumphs and fails.

## [00:00:44] Adam's Triumph

[00:00:44] **Adam:** It looks like it is my turn to go first, and I am going to start us off strong with a triumph. My triumph is, oh yeah, yeah, this is a good one. All of our secrets, like API keys and AWS access keys and all that, all of our secrets have now officially been moved out of config and into 1Password and they get injected into the containers as needed at container start. How badass is that?

[00:01:11] **Carol:** So sexy. Great job. You started working on this a while back, didn't you?

[00:01:17] **Adam:** It's been one of the like little, so many things had to like get done and line up to make that happen. Right. So the last thing that had to happen, before I could do this was we had, so we have a wrapper around Redis, right?

[00:01:31] **Adam:** So we have Redis available to our apps, and then we have a module that is just like, I would like a copy of the, the Redis, Utility or like a Redis connection, please. And here's the customer and the environment that I want it configured for, right? So like, you know, working code university QA, right?

[00:01:48] **Adam:** And you get back a connected Redis instance and you can just use it, right? and we made that relatively naively. using an embedded copy of our configuration module, which just was like a module that had nothing but config and like a function that you could call to get config by like the, the key name.

[00:02:10] **Adam:** Right. So like a. b. c. g or whatever, right. You would give it that and it would give you that setting back. and it was embedded. So anytime that we had to make a config change, Say, for example, if we brought on a new customer, then we'd have to update the config module and publish a new version of that.

[00:02:26] **Adam:** And then we'd have to update the wrapper to use the new version of the config and publish a new version of that. And then all of the various applications that use that Redis module have to be updated to use the new version of the Redis module. And so that just was like a nightmare of tediousness. And so a bunch of things had to happen.

[00:02:46] **Adam:** And the short version of the story is now we have all of them upgraded to a newer, slightly different version of our Redis wrapper that pulls config at runtime from an HTTP service that's only available inside of our VPC. and that way... All that has to happen to like onboard a new customer is publish the updated config to this, web service.

[00:03:06] **Adam:** And then the existing modules, you just say, okay, I'm looking for Bob's University in production and it, and it returns that connection. It just works. Yeah, huge, huge weight off my back. you know, it's one of those things where like, you know, you start out, it's an early stage startup. You're like, well, I know I'm not supposed to put this one API key that we have into config, but like, we don't have a better solution, better place to put it yet.

[00:03:31] **Adam:** We'll just start it there and then all of a sudden, it's been 10 years, you have like 400

[00:03:37] **Carol:** All these keys.

[00:03:38] **Adam:** in config. You're like, oh man, and So,

[00:03:43] **Carol:** Even, uh, not even with startups, you know, I think we've done it in, you know, very old existing applications. We've seen that lay around. So

[00:03:53] **Adam:** but I mean, in a lot of ways, I espouse that attitude toward development, right? Like do, do the fast thing, do the easy thing until you know that the project is going to have a long life and then do the right thing,

[00:04:05] **Carol:** yeah.

[00:04:06] **Adam:** right? Like don't, don't burn 10 hours building something that you could have done in a half an hour if you don't know that the product is going to be a success

[00:04:14] **Carol:** If

[00:04:14] **Adam:** need

[00:04:15] **Adam:** to 10 years.

[00:04:17] **Carol:** Yeah, that's fair.

[00:04:19] **Ben:** Let me ask you a question here about environment variables. I go back and forth on this and I don't know if my perspective is just too colored by the constraints. of our platform at work, or if there's something to it. So let me paint a picture here. The platform team has,

[00:04:36] **Carol:** Heh heh heh. Heh

[00:04:37] **Ben:** happy little cloud, the platform team has provided an interface for engineers to go in and create new environment variables.

[00:04:46] **Ben:** So you can go in and you say, for this service, I want to create an environment variable with this name and it prefixes the name of the service to it automatically. You can give it this value. And once you hit save, You can never see that value again, so you have to know what it is, if you need to reference it, but you know, most of the time you don't need to reference it, that's the whole point, is that you reference the variable, you don't have to reference the value.

[00:05:09] **Ben:** Now, in, I want to say like 98% of cases, that value never changes, or, or it doesn't really have cause to change, you know, it's a, it's an API endpoint, it's an API key, it's, It's a port for an SMTP server, that kind of stuff. but sometimes you do have to rotate keys. You have to rotate certificates.

[00:05:32] **Adam:** I'm all too familiar.

[00:05:33] **Ben:** Yes, exactly.

[00:05:34] **Ben:** Now, because the platform at work literally doesn't allow us to change values. You can only create new values. That's it. I don't even think you'd go and delete environment variables. Now that's not necessarily a business decision that was made. It was a, someone had to build something to allow engineers to, to start storing environment variables.

[00:05:55] **Ben:** We'll build 25% of it. And the, you know, the U and the D and the R of crud kind of got kicked down the road. So as a by product of this constraint, when it comes to rotating values, It was never an option for me to say, okay, when it's time to rotate, I'll go in and I'll update this environment variable and then everything will be honky dory.

[00:06:17] **Ben:** Literally, I'll have to create a new variable with like, you know, API key V2 or like API key July 24th. And then in my application code, I have to say when I say API key, what I actually mean is API key. The July 24th, right? And what that forces you to do is think about the environment variables as immutable, essentially. And I've kind of grown to really like that perspective, but I don't know if I've just kind of Stockholm syndrome myself, where Because I can't change values, I've convinced myself that that's a nice way to do it. Or if there is actually something to it,

[00:07:00] **Adam:** Very interesting thought until you said that you kind of liked it. I was like, yeah, I could see why, you know. You're, you're experiencing growing pains with that or whatever, but maybe like if I spent some time with it, I might find some value in it. Maybe it has like good effects for deployments and rolling back and that sort of thing.

[00:07:20] **Ben:** yeah, you can definitely roll

[00:07:22] **Carol:** yeah, your old still exists. You don't have anything out there that wouldn't work. Yeah.

[00:07:26] **Adam:** But you're, I mean, if you think, okay, the,

[00:07:29] **Ben:** it kind of, to some degree mirrors the way a lot of third party libraries or third party services, I should say, allow you to provision tokens. If I go into Twilio, for example, you can't just change an API key. You have to provision a new API

[00:07:45] **Carol:** You gotta get a new one,

[00:07:46] **Ben:** And then you get that in place. And then once that in place, you go and you de provision the previous

[00:07:51] **Tim:** Expire. Yeah.

[00:07:52] **Carol:** Mm hmm.

[00:07:53] **Ben:** So in a sense, the immutability of the constraints of our platform, which again, we're just arbitrary. I think do feel a little bit like they jive nicely with how third parties tend to express their API keys.

[00:08:07] **Adam:** I think you should reach out inside your organization and see if there's anybody else that feels the same way or if people like, what is the general sentiment amongst the engineering department?

[00:08:18] **Adam:** Do they go ahead,

[00:08:19] **Ben:** it's very interesting because we actually just had a, uh, we have a, uh, enterprises can log into our application using SSO, which stands for single sign on and part of the single sign on dance, and I'm, I'm sure I'll get some details wrong here, is that the identity provider, so let's say that Acme Corporation wants to use SSO, they'll have an identity provider, possibly in house, possibly hosted by Okta, possibly hosted by Microsoft, something like that, They'll post a signed payload into our application and it's signed using some sort of a certificate.

[00:08:58] **Ben:** I don't know if it's an SSL certificate or if it's just like a general, I don't know that much about this kind of stuff. So

[00:09:04] **Adam:** it's signed and encrypted.

[00:09:05] **Ben:** right, on our end, then we have to have a certificate that allows us to decrypt their payload so that we can verify it. And essentially we have to agree on what those certificates and that signing mechanism is and the signing algorithm so forth.

[00:09:19] **Ben:** As a standard, we have to rotate. Those certificates every one to two years. I think we're, I think we're doing it on a two year basis right now. I don't know. This was also, this was like all part of the SOC compliance negotiations, I think too. So getting back to the conversation here about rotating keys, we just had to rotate our, our, our signing key and that signing key is provided via an environment variable.

[00:09:46] **Ben:** And on the cutoff date for the expiration of the certificate, the engineer who's working on it literally had to open up a platform ticket, like a JIRA ticket to have the, one of the SREs, the site reliability engineers go in to production and change the value stored in the environment variable. So definitely we have people who are thinking about it in terms of.

[00:10:12] **Ben:** You can update values and updating values would make our lives easier. But on the flip side to that, going back to the embracing and leaning into immutability, if you were to just version the keys, then you wouldn't have had to open up a platform ticket.

[00:10:28] **Adam:** It's, yeah, I mean, it's a very double edged sword, right? It cuts both ways. On one hand, you do get that immutability and the rollback ability. On the other hand, like the direct opposite of that, or the corollary, as I guess, as we should say, is engineer people with big brains, right? is,

[00:10:43] **Tim:** Grog no like big brains.

[00:10:45] **Adam:** you got the reference. Good job. is, that they're going to pile up over time, right? Especially if it's going to, like, you would hate me right now if, if you were consuming my API because we just instituted policy. Where we are rolling our customers, access keys that we give them for S3 access, every quarter.

[00:11:04] **Adam:** So four times a year, we, we give them a 10 day, grace period for the old one. So we, we, on Amazon, an account can have two access keys. And so they've got their old one. It's still good. And on approximately day 90, give or take, because years are not evenly divisible by 90. they. A new one gets created and now both keys will work and then 10 days later The old key gets deactivated and during that 10 day window We're expecting and this is it's like the let's just say like january 10th and january 20th, right?

[00:11:38] **Adam:** So january 10th, you get a new key january 20th Your old key gets deactivated and you're supposed to know because it's january but somewhere between january 10th and 20th, I need to go in and either manually rotate my keys or write a Automation because we make it available through our api to get the updated key and update our stuff locally.

[00:11:59] **Adam:** So when you do the automation, it's great because keys are rotating constantly. And, you know, I guess warm fuzzies for security keys changing, right? But then if you're, if you're using environment variables and if you're using immutable environment variables, to make those available to your application, that would get ugly fast.

[00:12:20] **Adam:** I wouldn't, you know, I honestly wonder if there's some limit. To the number of environment variables that you can have or that

[00:12:27] **Ben:** Yeah. I have no idea. It sounds, I, I haven't used a windows computer in a number of years, but I always remember people throwing out the term registry, like registry would cause a

[00:12:37] **Adam:** I have nightmares.

[00:12:38] **Ben:** some reason.

[00:12:39] **Tim:**

[00:12:39] **Ben:** The other issue that we've run into is rotating environment variables. Is when two teams have to agree on an, on the value of an environment variable. So if I have to call, if I have to make an API call from one service to another, oftentimes the team that owns the target service that I'm calling, they'll have a signing key, much the same way that we just talked about the SSO.

[00:13:04] **Ben:** And if we have to rotate those keys, they want to, they want to just like agree on a universal. They're like, Oh, here's, there's some global bag of environment variables that all the services have access to. And I'm like, I don't want to use your global environment variable. Like that's, I hate the idea of me being able to change a variable for my service and it accidentally.

[00:13:26] **Ben:** Changing the value in someone else's service. I, I would much prefer each service to have its own set of environment variables. And coincidentally, some of those have to line up, but I tend to lose that fight.

[00:13:39] **Tim:** I'd ask though in practice. So it's like, you know, I have these keys that I get from Twilio and from Plivo and different providers. I've never had them tell me to get new ones. They've never forced me to.

[00:13:51] **Ben:** Yeah. Yeah. I don't, I don't think it's, it's, it's like, I mean, I probably shouldn't say certain things in a recording, but, but it'd be like if a developer, you know, accidentally pushed a key somewhere where it shouldn't have been, and

[00:14:04] **Carol:** Yeah, then you're gonna have to rotate, it's

[00:14:06] **Tim:** So you think you're, you think, yeah, typically it's like I can request a new one, but it's like, as long as I know it's not compromised, I'm just going to keep using that same key.

[00:14:14] **Ben:** percent. We've had some issues where. there was like a library that was used as part of our continuous integration builds, had a security scare, and then there was no way for us, I think, to know whether or not anything had happened. So we had literally had to rotate every single key that we owned.

[00:14:33] **Adam:** Mm hmm. Yeah, so, alright. On the subject of putting keys in environment variables, you might like to hear this, Ben. so for SOC 2, for, there's like a requirement to do vulnerability scanning of your code. And so we turned on a product called, I think it's Amazon Inspector is what they call it. It's just a module within AWS.

[00:14:56] **Adam:** and I think it's, I mean, it's relatively inexpensive. It's not that bad. It's worth turning on. and they scan your code for known CVEs, that sort of thing. But I also noticed that it complained. That we had, environment variables with AWS access keys in them. Because, you know, we were new to AWS when we started doing this stuff.

[00:15:17] **Adam:** We just were like, okay, we'll figure out how to give, you know, this lambda function access to do this thing. Let's create a user account. You know, let's give it access and, and we'll just give it an access key and use that access key to do the thing. You know, use the SDK.

[00:15:31] **Carol:** best you can

[00:15:32] **Adam:** Right, you just make it work. And,

[00:15:33] **Ben:** mean, none of this sounds wrong, so I feel like, uh,I shouldn't be the one to organize any of that

[00:15:37] **Adam:** Well, Apparently, it doesn't like that, right? And I don't know if there's some hard and fast rule about not having secrets in environment variables. Because I feel like that's what we've been told for years as sort of like a best practice, right? Like, you don't want them in your code, don't hard code them, put them in as environment variables.

[00:15:53] **Ben:** Are they just trying to sell you like a Amazon's key service or something?

[00:15:57] **Adam:** I don't know, maybe. But, the thought going through my head is like maybe environment variables are fine for like a development machine. And maybe that's why we hear it so much. But maybe they're not so good for production.

[00:16:09] **Ben:** well, I mean, I think we talked about this or I mentioned it on a couple of episodes ago that our security team, they, they want to move some stuff to, I think they're calling it EKS, Elastic Key Service or something, or I don't know what it stands for.

[00:16:23] **Tim:** Like a, you know, like a secret provider

[00:16:25] **Ben:** yeah. And, and the, I think the whole idea behind it is exactly that somehow everything ends up in environment variables anyway, but it has something to do with how they're actually delivered to the machine.

[00:16:37] **Ben:** I

[00:16:38] **Adam:** Sure. Yeah. I mean, maybe the problem with the way that we were doing it is that as environment variables, like for our Lambda functions, for example, the name and value of the, the. Environment variable are both there in plain text, so you would be able to see this is the access key and this is the secret as somebody who has access to the console and to view our lambda functions, right?

[00:16:59] **Carol:** Huh? Hehe.

[00:17:00] **Adam:** Maybe that was more of the problem than the fact that they were there. But regardless, because of those alerts, I did learn how to do it the right way or the quote unquote right way. And I'll, I'll share that knowledge with you now. Basically, what they would tell you to do is create a role instead of a user account.

[00:17:18] **Adam:** Give that role, whatever permissions you would have given to the user account, right? So you need this Lambda function to be able to access S3. and you can, you know, tighten that down to just a specific bucket or, you know, whatever credentials or whatever restrictions you want to put on it. And then you can change the execution role of that Lambda function.

[00:17:35] **Adam:** And I've done this for Lambda. I've done it for. ECS containers, a couple of other things. So that seems to be at least a more preferred way to go about it. And then the nice thing about that is like, for example, in the Lambda, right? You don't have to give any credentials to the SDK. You just say, I want to use the SDK to access S3 and go do the thing.

[00:17:58] **Adam:** Right. And then it goes, okay, well, the. role that you are executing as has access to S3. So go ahead and you don't have to worry about key rotation or anything like that.

[00:18:08] **Ben:** That is pretty cool. I mean, it's, it's way more than I understand about AWS,

[00:18:13] **Adam:** pretty

[00:18:13] **Ben:** very cool.

[00:18:14] **Tim:** way more than I wanted to know.

[00:18:17] **Adam:** And here we are 20 minutes into the podcast. So, why don't we move on to the second triumphant

[00:18:22] **Carol:** Oh my goodness.

[00:18:23] **Adam:** Ben, how are you, man?

## [00:18:25] Ben's Triumph

[00:18:25] **Ben:** I will also go with the triumph, which is that I am continuing to make incremental progress on my Dig Deep Fitness app, which is, you know, I think the most effort I've put into anything outside of work in quite a while and not effort in terms of total hours, because it's really not, I'm just trickling, you know, two hours in the morning, an hour on the weekend, something like that.

[00:18:48] **Ben:** which is in terms of consistency and, and actually really trying to improve it. so I'm, I'm pretty pleased with that. It's a double edged sword though, as I continue to focus on Dig Deep Fitness, I am not focusing at all on writing on my blog or exploring new technology stuff. Like I, ColdFusion 2023 and not 2021, but, just not a priority right now, which.

[00:19:17] **Ben:** You know, I expressed this on a previous

[00:19:18] **Adam:** You don't want those Java islands

[00:19:21] **Ben:** Yeah, yeah, yeah, exactly. I want to be playing with that stuff. It sounds interesting. But, but I don't know, you know, there's only so many hours in the day, but I'm going to call it a triumph. So I think part of the triumph is leaning into the not having enough hours in the day and just accepting that and not freaking out.

[00:19:40] **Adam:** mean, what you're implementing, there's some, there's probably a name for this in like psychology or, or something, but, or philosophy, but like, basically there's only, like you said, there's only so many hours in a day and you are giving your attention to the thing that interests you the most. And so, yeah, there are other things, there's a million things I could list that I would love to be doing, but I have to decide what my priorities are and spend my time accordingly.

[00:20:02] **Adam:** So

[00:20:03] **Ben:** but feeling good about it. Pretty excited. I've been using it and it's fun. So, Triumph.

[00:20:09] **Adam:** cool,

[00:20:09] **Ben:** that's me. Carol. What do you got going on?

## [00:20:12] Carol's Triumph

[00:20:12] **Carol:** I'm going to go with a big, giant win for me. So I finally have my address changed with the post office. And why this is a win is because I started this process in April. And since then I've submitted three requests after like the change of address online to get it done. So finally I went to the post office to figure out what happened.

[00:20:34] **Carol:** Well, it turns out in April, they made a major update to their software. And everyone who submitted a change of address within the three day window of them getting this new software. Or this changed their software, their requests went into the ether, they just disappeared. And if you submitted any requests after it said duplicate, because it knew you had one, it just didn't know the state of it.

[00:20:59] **Carol:** So it would never process anything. So I went to the post office and. I had no idea the post office has like meeting rooms in the back of it. So they pulled me back to this meeting room and I sat there for an hour going through like the process to try to get my address changed only for them to then explain like how software engineers are so terrible and how they shouldn't be allowed to write this code and how they destroyed everything that they've been working for.

[00:21:27] **Carol:** And yeah. I was like, Oh man, it's like, I'm not going to tell you what I do for a living right now. Cause you know, technically I'm not employed, so I'm not going to say anything. That's not me. I didn't do that to you. So it was just interesting to see like the consequences of some of our actions. Cause typically I'm on the other side, just going on through it.

[00:21:47] **Carol:** I don't see the. The actual like headache that it causes to a company or to their users, or like now their new workflow, they have these massive posters sitting behind their desks that says resolve. Well, no, it's probably some of those two, but it had, they had these posters behind their desks that say like, resolve all change of.

[00:22:08] **Carol:** Of address concerns within 36 hours. And it has like four bullet points of why this is important because of this. Like they've had to put out publication, they've had to train people on how to get it done. So they have a special, IT help desk that they send all the emails to, to get it done. So today I got four envelopes in the mail, all confirming my change of address for everyone I had ever submitted.

[00:22:33] **Carol:** So it's kind of crazy too, because I told Steve, I was like, Oh wow, it got here just in time to do it again. So I was like, I have no idea what's going to happen when like, now my mail needs to forward to forward again. And yeah, we'll figure it out. But it was just interesting. So I'm gonna call it a win and it's done.

[00:22:51] **Carol:** But engineers suck, you guys. Just saying. We're not that great.

[00:22:55] **Tim:** what version of ColdFusion is USPS running?

[00:22:59] **Adam:** Four.

[00:23:02] **Tim:** MX, the best of them all.

[00:23:05] **Carol:** When that's me, what about you, Sam? What do you have?

## [00:23:08] Tim's Failure

[00:23:08] **Tim:** Well, unlike you guys who all have these shiny triumphs.

[00:23:13] **Carol:** Winners!

[00:23:14] **Tim:** Winner winners. I'm going with the fail.

[00:23:16] **Carol:** Oh

[00:23:16] **Ben:** Hahahahahahah

[00:23:17] **Carol:** bum, bum, bum. That was really good. You should fill more often.

[00:23:24] **Tim:** thank you. yeah. So security updates take a really long time to schedule. so. Our few remaining ColdFusion servers that we have in our payment. It's like, Adobe came out with some recent, very critical, like some day zero. I think it's like two or three of

[00:23:42] **Ben:** in a row, I think.

[00:23:43] **Tim:** three in a row, right? Really, really like high impact ones, right?

[00:23:49] **Tim:** If it were me, I'd be like, let's, let's upgrade them tonight. One, we have SLA. So I have to like give 24 hour notice to all of our customers that will be down for the, hopefully just a few minutes that you have to restart the services to run them. And then two, it's like, I can't actually do them because, you know, that's in the PCI environment.

[00:24:09] **Tim:** You have to have the infrastructure team do it. So it's like, you have to have different people do it. Like everyone wants to like validate the codes running. So it's like something that just like, we really need to get this done. It's like, it's going to be weeks where we can actually get the security updates, put in there.

[00:24:24] **Adam:** And then you never, you know, you try your best at, you know, you run some tests. we could help you, like, convince them to get it going. Right? So just tell us what your URLs are

[00:24:34] **Adam:** that are going to

[00:24:34] **Carol:** sounds like you're vulnerable!

[00:24:36] **Adam:** And then, uh, you know, sorry, it's common knowledge now. We're going to

[00:24:41] **Tim:** Yeah, it'll become, you know, escalate to an actual let's do it now in the middle of the day problem, right? Once, once the script kiddies start hitting it. So, fortunately a lot of these aren't even public facing, so that's, that's somewhat

[00:24:52] **Carol:** a win. Yeah.

[00:24:53] **Tim:** but it's like still you want to get them taken care of. So yeah, it just, it just frustrates me the level of bureaucracy. I'd have to go through to get these things that are like, you know, if you just take care of it now, it won't be a problem. But it's like, if you wait two to three weeks, it could become a problem because you don't know

[00:25:10] **Carol:** You

[00:25:10] **Tim:** targeting you.

[00:25:11] **Carol:** sounds like you need a change advisory board

[00:25:14] **Tim:** No.

[00:25:16] **Carol:** this to a higher level.

[00:25:18] **Tim:** Yeah. I've read that book. Sounds terrible. So yeah, just, just a little frustrated there that we just can't and just frustrated. It's like, why didn't they roll it into one big update?

[00:25:29] **Carol:** Why three?

[00:25:30] **Adam:** Yeah. Was it? You said there was three, was it all on the same day, or did they

[00:25:34] **Tim:** No, multiple days. Yeah. It was like, but they were like within days of each other. So one came out last week and then like the next day another one came out and then a couple days after that, a third one came out.

[00:25:43] **Ben:** I feel like I read, and maybe this is not true, so forgive me if this is inaccurate, but I think that the, one of the patches ended up being incomplete, or what didn't cover everything that they thought it was going to cover, so I think one of the subsequent patches was to fix a missing fix from the previous

[00:26:00] **Tim:** So they, they, they released too early basically,

[00:26:04] **Carol:** They didn't test their fix.

[00:26:06] **Tim:** I don't know. So it's just, it's just frustrating.

[00:26:09] **Carol:** That is, I hate that for you. you can get it done soon. I mean, it'll probably be done before this airs. So you're

[00:26:14] **Tim:** Yeah, no, it, it, it will be, it will be, but it's just like, and, and the most really sucks is that the previous week, you know, before any of this happened that we knew this was coming, we're trying to do a firewall update to come up to a new physical firewall, and, we scheduled two hours for that. On a Sunday morning to do it like we were down for normally we're never down we were down for like an hour and just the firewall just did not work so we had to roll everything back and go back to it and but fortunately you know because we had like notified the customers and they were expecting it but now it's like now we have to do firewall change and this critical update changes at the same time and I don't like changing multiple things at once because you never know what screwed up what right?

[00:26:57] **Carol:** I like my single points of failure. Like I know what caused it to stop responding. Not was it this or was it that? Was it this or was it that?

[00:27:05] **Tim:** Anyway,

[00:27:06] **Adam:** Alright Ben, pop that shirt off.

[00:27:08] **Tim:** streak,

[00:27:09] **Carol:** Bound chicken? Wow.

[00:27:10] **Ben:** I

[00:27:12] **Tim:** the Tank, Frank the Tank.

[00:27:14] **Adam:** We're going streaking!

[00:27:17] **Ben:** Woo! Carol, that's an old school reference.

[00:27:19] **Tim:** Yeah.

[00:27:20] **Adam:** Which is a movie.

[00:27:21] **Tim:** Will Ferrell.

[00:27:22] **Carol:** OK,

[00:27:23] **Ben:** and Luke Wilson.

[00:27:25] **Carol:** so when he's when he's an old school reference, I was waiting for him to say a movie title like, you

[00:27:30] **Adam:** Right, which

[00:27:30] **Adam:** is

[00:27:30] **Carol:** back in the day. I was like, Oh, don't leave me hanging, Ben. I

[00:27:35] **Ben:** You're my boy, Blue!

[00:27:36] **Tim:** movie, Will Ferrell was like the CEO of, of the Barbie company.

[00:27:41] **Adam:** haven't

[00:27:41] **Ben:** I

[00:27:41] **Carol:** not saw the Barbie movie.

[00:27:43] **Adam:** It's supposed to be really

[00:27:44] **Carol:** never see the Barbie movie.

[00:27:46] **Tim:** What? My wife and daughter went to see it. They loved it.

[00:27:48] **Ben:** Yeah,

[00:27:48] **Adam:** I mean, I've heard good things. I've heard it's supposed to be really good. It's not just like, you know, some, you know, whatever, money

[00:27:55] **Carol:** legally blonde

[00:27:56] **Adam:** a real story, sort of thing.

[00:27:59] **Tim:** Anyway. What's the streaking we're talking about? Is, is Ben going to, I

[00:28:03] **Ben:** kind of streaking. all clothing will remain

[00:28:05] **Ben:** fully, uh, clothed.

## [00:28:07] Representing Streaks in Data

[00:28:07] **Ben:** what I was referring to in a, in a chat that Adam and I were having offline was in regard to a streak of activity. So you do something for several days in a row and it's considered a streak,

[00:28:21] **Tim:** A behavioral streak

[00:28:22] **Ben:** behavioral streak.

[00:28:23] **Ben:** Right? Exactly.

[00:28:24] **Carol:** for example,

[00:28:25] **Carol:** Adam, flosses his teeth

[00:28:27] **Adam:** every day. Don't

[00:28:28] **Carol:** every day now.

[00:28:29] **Ben:** you go. Absolutely. And,

[00:28:31] **Tim:** forgotten to floss for the past 15 years.

[00:28:33] **Carol:** There you go.

[00:28:34] **Ben:** that's, that's its own kind of streak. I, you know, I think a lot of us are familiar with GitHub, GitHub. I. If you go to your profile on GitHub, you get the little, 52 weeks worth of green boxes where they have the months across the top. And then, I think the days of the week across the, the, the vertical and you can

[00:28:53] **Ben:** get various.

[00:28:54] **Adam:** by 7 grid, yeah.

[00:28:55] **Ben:** Yeah, you get various shades of green, depending on how many commits you made. I think I don't exactly know the algorithm, but it's a, it's one of those things that is a, can be a motivational tool because people like to see their own streaks that like to feel good about their own commitment to activity.

[00:29:12] **Ben:** And it occurred to me that in Dig Deep Fitness, my ColdFusion fitness tracker, it would be fun to have some sort of a. I don't know if I want to be a streak concept, but it would be nice to see some sort of a visual rendering of how often I've been working out. Am I doing something three times a week?

[00:29:32] **Ben:** Am I doing it every day? People don't necessarily need to work out every day or even want to work out every day. So I'm a little bit on the fence about how streaky oriented it should be. But here's the thing, I started to write some code for this and it occurred to me that, I don't know if I even know how I would store this data.

[00:29:54] **Ben:** So historically, data in terms of dates seemed like a solved problem. Everybody just stores everything in UTC universally. It was a universal time coordinate. and then you figure out what to do later, whether you

[00:30:11] **Carol:** clock. Oh, man. I

[00:30:14] **Ben:** whether you leave it in UTC or you translate it to a user's relative time zone, you store the date and the time in UTC, and then you worry about doing stuff later.

[00:30:23] **Ben:** Streak is different though, because. you're storing day specific thing. So, okay, let me back up for a second. Sorry. Old Ben would have just stored actual dates for everything like full date times and then old Ben would have done on the fly. Let me just do some group by date of this thing so I could on the fly strip out times and new Ben is thinking to himself, Hey, I'm building this thing from scratch.

[00:30:52] **Ben:** Why don't I try to build it the right way? So instead of doing all this on the fly aggregation, I actually want to have a data table that represents streaks. So the way I am doing it now, which, you know, is like a day old at this point is I have a user ID column and a date column and it doesn't have a time because I figured I want to, the streak makes sense at the day level, right?

[00:31:16] **Ben:** I had something for July 24th. I had something for July 23rd. I had something for July 19th. I skipped a couple of days in there. But then I, I kind of started to worry that that doesn't make any sense because days who is that day too? And then how do I make sure that I have the right days or the right time zones?

[00:31:36] **Ben:** If there's no time, that was the whole point of UTC is that you have the date and the time, so you can translate it. But if I have just the date, I don't know. I started to, feel really not confident about my implementation. That is what I'm saying. Makes sense.

[00:31:51] **Carol:** think it does. Like, okay, so I get concerned with the 24 hour clock, right? So I went to the gym at 8 a. m. If I don't go to the gym tomorrow until 5, did I just lose my streak because it's technically been more than 24 hours, like more than one day? Not matter since it's a day to day compare. So as long as I went Monday and I went any time on Tuesday, I'm still good.

[00:32:14] **Carol:** And was that your thought with not

[00:32:16] **Ben:** that's a perfect example, because if I'm storing dates in UTC and you work out, let's say you work out at 8 a. m., which we'll call is Monday, and then let's say you do a jog at 10 p. m. at night. 10 p. m. at night, Monday, is actually Tuesday in UTC, right? They, they've already crossed over into the next day.

[00:32:39] **Ben:** So now, does that, if I'm storing everything in UTC, is that, do those both workouts count towards your Monday streak, or does it become Monday and Tuesday? And that's where I'm, I'm realizing that I don't

[00:32:50] **Tim:** But that, I mean, if you're the user, that doesn't reflect the reality. You're like, I didn't do anything on Tuesday, right?

[00:32:56] **Carol:** Which is then when you need locale to user information, you need to know their locality to know what time they're actually in, right? To know the true date.

[00:33:05] **Ben:** Exactly. And, and, but then, so then when I store it, and then I'm like, well, maybe I don't even use a date value. Would it be crazy to just have. A string, like a year, year, year, year, month, month, day, day, kind of a string. But then I'm like, how is that really any different than just storing

[00:33:23] **Carol:** Just storing the date. Yeah.

[00:33:25] **Ben:** a time?

[00:33:26] **Tim:** And making it harder to

[00:33:27] **Carol:** Yeah, exactly.

[00:33:29] **Adam:** I think you're on the right track with dropping the time. Time doesn't matter. All that matters is the user's subjective day, right? To me, when I did this workout, it was Tuesday. So I'm recording it as my check mark for Tuesday. Now, here's, we started having this conversation before the podcast, my brain immediately went to like, I bet you there's some cool optimizations that you could do with, you know, like doing aggregation and updating it when, when there's new data.

[00:33:57] **Adam:** And so all your aggregations are already up to date,

[00:34:00] **Ben:** Right. I see. That's what it is. I don't want to do stuff on the fly. I wanted to have a, like a calculated table.

[00:34:06] **Adam:** Okay, let me throw a wrench in those

[00:34:08] **Ben:** Yeah. Yeah. Yeah.

## [00:34:10] Backfilling

[00:34:10] **Adam:** What if you do your workout, but you forget to log it until tomorrow?

[00:34:14] **Ben:** So a tough one. That's a tough one. Okay. Well, yes. I don't know. I don't know. That's, that's a user error.

[00:34:24] **Adam:** Okay, but that doesn't, I would be upset with my app if it wouldn't let me go. Okay, but yeah, actually I did work out yesterday.

[00:34:31] **Ben:** Okay,

[00:34:32] **Tim:** I worked so hard, my arms couldn't pick up the phone to put it in. That's

[00:34:36] **Carol:** Or you didn't have network activity, you know, like you didn't have access to the internet.

[00:34:40] **Ben:** so, okay, this dovetails with another topic, which I, I had never heard about this before, but I don't know if anyone's familiar with the changelog series of podcasts there. Okay. So they have a whole bunch of things like JS party and, go time and changelog news, et cetera. I'm pretty sure I was listening to an episode of changelog news last week and they were talking about streaks and specifically they're referring to an article.

[00:35:05] **Ben:** And the article is called Streak Redemption by this guy, Lucas Mathias Mathias. And the, the premise of the article is, is that streaks are a powerful motivator until you fail your streak, until you break your streak. And then they can be completely demoralizing. You're like, Oh, I was, I did something for 134 days in a row and then I forgot to do it on the 135th day.

[00:35:31] **Ben:** Why should I even start again? Like it's going to take

[00:35:33] **Carol:** why you, your streak should earn you treat days, but go ahead.

[00:35:36] **Ben:** So his take on it was that systems should have a way for people to redeem themselves and to essentially backfill. Parts of their of their streak. So I thought that's something that I could do where you could have a streak redemption option Where let's say instead of just working out Maybe you went for you know a long walk or you took your dog for a walk Or you did a little bit of cardio something like a little extra you could say, yeah I know I missed my workout yesterday, but I did 15 minutes on the bike today Let me count that as a redemption towards yesterday and you can do some sort of back filling I know

[00:36:08] **Ben:** that

[00:36:08] **Adam:** only if you're paying for premium.

[00:36:12] **Ben:** That's right.

[00:36:12] **Ben:** You got to, you got to pay up to feel better about

[00:36:14] **Adam:** Get your little blue checkmark and you can do redemptions.

[00:36:17] **Ben:** You know, exactly. That's actually an interesting idea. but yeah, no, that's a great point about forgetting to mark something off.

[00:36:27] **Carol:** So the way like my fitness app works is I actually can select the day. So like I have a calendar view and I can select the day and say add workout and manually put it in there. So like I can select yesterday and say I spent 30 minutes on the, on the, you know, elliptical or I lifted weights for 30 minutes.

[00:36:47] **Carol:** And then I have my little green dot on the calendar again. But in the other app I was using, they had this concept of treat days. So if I, I set my goal, right? So my goal was to work out five days a week. So if I worked out five days, I earned a treat day, which meant next week I have a day. I can just say, activate my treat.

[00:37:07] **Carol:** And it still gives me the green dot, but there's nothing wrong. So it says, okay, Tuesday's your treat day. You earned that. So. Take a little break. It's fine. Don't don't feel bad about yourself that you didn't get a workout in the day You've been doing really good and you're not gonna it's not gonna look to you like you're a failure.

[00:37:24] **Ben:** I like that. Release the treat. Yeah, that's a cool idea. It never would have occurred to me to do something like that. That's, yeah. Yeah, that's very, that's the proactive version of what I would be doing reactively.

## [00:37:38] Adam's Solution

[00:37:38] **Adam:** So I want to ask you Ben, this project, is this just something that you want to do to have it and, and to get to work on it? Or are you interested in opportunities to use this as a lever to make yourself learn something new and interesting?

[00:37:54] **Ben:** I feel like this is a, I

[00:37:55] **Adam:** Oh, this

[00:37:56] **Adam:** is totally a

[00:37:57] **Ben:** you're, you're, you're,

[00:37:59] **Carol:** trick.

[00:37:59] **Ben:** don't like to learn anything, Adam. Learning is stupid.

[00:38:03] **Ben:** Uh, I do want to learn stuff. how might I be able to use this application to my advantage?

[00:38:09] **Adam:** Okay, so, you were talking about, you know, you always want your aggregations to be, up to date and, like, you don't want to have to recalculate them at display time, that sort of thing.

[00:38:21] **Ben:** Right. I wouldn't mind recalculating in the background if I had to, I just don't want to do it like users rendering this page. Let me run those calculations on the fly.

[00:38:29] **Adam:** Right. So... My thought is you record the the workout you ask the the whole thing is on the honor system anyway, right? There's no way there's no reason I couldn't log into DDF and just say yep I did my workout today and continue eating my jar of Snickers bars

[00:38:49] **Ben:** That's the only size worth having.

[00:38:51] **Carol:** Exercise

[00:38:53] **Adam:** The So my point is it's on the honor system to begin with right? So there's no reason you can't just get the the user's subjective date from whatever input device that, you know, if it's their web browser on their phone, or if it becomes a mobile app one day, whatever you can just say, what is today's date for wherever I am in the world?

[00:39:15] **Adam:** Whatever, right? Today is July 24th. and record that as part of the, the check in effectively, effectively is what it sounds like this is. Right. and so you record the date you record. Whatever detail you want to have in order to prove that it's or that you need to calculate the streak Right if it's one or zero or whatever, and then you Send a message into a queue, and this is where it gets fun to

[00:39:42] **Carol:** You want to learn

[00:39:44] **Adam:** Adam is ready for his aggregate his streak Aggregate details to be recalculated.

[00:39:49] **Adam:** So then you go and you're like, okay, what is my best streak ever? Right my current streak Whatever other stats that you're pulling And and do that and then you can that'll give you experience with like queues and dead letter queues and retries

[00:40:05] **Adam:** That would be pretty cool, actually. I mean, it would be overkill for the situation that I have, but. Everything lives on a single box anyway for me, right? You know, this is all just on a single VPS, my database and my application server side by side, physically, spiritually. You got some spare headroom for, to run a rabbit

[00:40:27] **Ben:** I, I think I do. I will. I mean, yeah, cause I don't, because this is just for funsies and, I don't want to start to actually add material costs. I think I would probably want to try something like RabbitMQ just because I can run it locally, I think. Right. Whereas. SQS, I mean, I'm pretty sure I have to start paying for it, although it probably has a

[00:40:47] **Carol:** do it some get some count you might not hit it soon, but you could Yeah,

[00:40:54] **Ben:** but I, I love this idea as as a

[00:40:58] **Adam:** Uh,

[00:40:58] **Ben:** opportunity.

[00:41:00] **Adam:** I think you would be fine. SQS free tier is a million requests a month.

[00:41:03] **Ben:** Yeah. Let's, let's worry about getting user number two first.

[00:41:08] **Carol:** I thought you were seeing different IPS.

[00:41:11] **Ben:** I think there are like two people who have tried the app.

[00:41:15] **Tim:** the link.

[00:41:16] **Ben:** I appreciate that, Tim.

[00:41:17] **Carol:** I went to the wrong site and then looked a lot at that guy.

[00:41:21] **Ben:** I, hey, you know what? I'll take it.

[00:41:24] **Carol:** Yeah I was like, Ooh, he has muscles.

## [00:41:28] User Experience

[00:41:28] **Ben:** So then the other thing that I've been thinking about is I do need to use someone's understanding of, if I have to have an app that understands time zone, I don't know if I want to record that in terms of the time zone itself because time zone just stuff is, it's complicated and there's so many time zones.

[00:41:45] **Ben:** I do know that if you're in a JavaScript context, or I should say specifically if you're in a browser context. You can get the number of minutes offset. So I might be in GMT plus five, but I'm really in whatever number of minutes. That is 60 times five

[00:42:07] **Adam:** We don't want to dive into the time zone hole, my friend.

[00:42:11] **Ben:** right? So what I think what I could be comfortable with is having the user as part of their form submission, I could write to a hidden field and say, this user is at plus 300 minutes off of UTC.

[00:42:25] **Ben:** Okay. And then because everything on the server is in UTC, I could use that to figure out what, what day they're in. Maybe, I don't know. No,

[00:42:35] **Tim:** what if they're on vacation in Japan

[00:42:37] **Carol:** I mean, you still would want to log that to their, it's going to be their Tuesday workout. So they're still going to want that click for their Tuesday

[00:42:44] **Ben:** Ultimately, I still have to get their correct day bucketing and I

[00:42:49] **Adam:** Yeah. I mean, if you wanted to do that to figure out how to default the day field, but like, yeah, I mean, ultimately what I would like to see as a user of the application is, you know, The, the date that it's being logged against as a, as a suggestion and allow me to overwrite it. I

[00:43:05] **Ben:** I see what you're saying. What you're saying is that the user should essentially provide the date as part of the, so

[00:43:14] **Carol:** Submit.

[00:43:15] **Ben:** yeah. Okay. I see what you're saying.

[00:43:17] **Tim:** and particularly like let's say they forgot to record it again, right? So that's like yesterday Don't force them to choose now as the default

[00:43:24] **Adam:** it heavily depends on the way that the application works, right? Like if it, if the whole thing is like it guides you through the workout, that's a little harder to do.

[00:43:33] **Ben:** I mean, so the way it works right now is you get into the app and you say start workout and then you choose a location like I'm working at home, I'm working out at Planet Fitness, I'm working out at Equinox and then it jumps you into the workout essentially and you can select your exercises and behind the scenes when you say start workout and then you choose the location where you enter new location.

[00:43:56] **Ben:** It creates the workout, and then it also adds an entry to your workout streak. So it's doing that recording on the fly, when you start the workout. But that's, essentially I'm selecting the date behind the scenes, but that could easily be replaced with someone selecting a date explicitly.

[00:44:15] **Tim:** you could uncouple the actual workout from the actual recording of the workout So you're walking them through the workout and then at the end do you want to save this and the save button has a date As a as a date that you choose in a location

[00:44:29] **Ben:** Yeah,

[00:44:30] **Ben:** that's true.

[00:44:31] **Adam:** Tim, you brought up like, you know, what if you're on vacation in Japan? You know, you're, you might cross the international date line and like totally lose a day for, through no fault of your own. But then like you're going to gain a day on your way back, right? Or something the other way around.

[00:44:45] **Ben:** Uh,

[00:44:45] **Tim:** they love this app so much They're they're doing it globe around the globe, dude

[00:44:50] **Adam:** Yeah. What were we saying before about premature optimization?

[00:44:53] **Tim:** Exactly. I just say decouple like the actual workout steps from the saving of the time when you did it. The recording versus the, it sounds like you're doing at the beginning, you're like, I'm working out. I'm starting my workout.

[00:45:06] **Tim:** Here's where I started it. Here's the date. That's gospel. And then you store it. Welcome to the steps of the workout. And then at the end, when they let, when they choose to save, let me save my workout, then let them choose what the day is

[00:45:21] **Ben:** yeah, that's fine. I don't know if I feel like starting the workouts. Yeah, starting the workouts a pretty strong indicator of activity. I think, I mean, you know, to Adam's point, you're on the honor system. You could start a workout and do nothing inside of it. And I would technically have recorded you as having a streak entry.

[00:45:42] **Tim:** True. Yep. But they could put the, I guess they could put the date there, right?

[00:45:46] **Ben:** yeah, yeah, yeah. I think so. I think the idea of entering a date. I'd like to have a way to do that. I don't think it necessarily needs to be the primary workflow because I think in the majority of cases. Someone's going in, they're doing the workout, because also remember that the main, mode of exercising in this app is resistance training.

[00:46:11] **Ben:** So I'm picking up a barbell, I'm picking up a dumbbell, and the reason that that's the main gesture is because it records the weights and it tells you what it was previously and then you can try to do as good or better this time. So you, there is a, there is a sense that you will be actively engaging with the app as part of the workout in order for the app to actually be providing value.

[00:46:32] **Carol:** Can I get you to add just a single button for cardio?

[00:46:36] **Ben:** Yes, a hundred percent. I just don't know anything about cardio. So I don't know what's interesting to record. That's the, that's like,

[00:46:43] **Carol:** I just need cardio and I can either select like elliptical, treadmill, rowing, like there's a few. And then, I need distance and time.

[00:46:52] **Ben:** I think that's

[00:46:52] **Carol:** Some people track calories. I don't track calories. I just check track distance and time.

[00:46:57] **Ben:** all right. Hey, I'm down to clown. I can, I can put something in there because the, the, the data that stores the workout, it's not necessarily tied to resistance training, the resistance training exercises are. Included as part of the workout, like a sub data point off the workout, but there's nothing where there's nothing that ties the workout to a specific type of workout.

[00:47:21] **Ben:** So it should be easy enough, but yes. So something like that though, I could definitely see you forgot to do it while you're on the bike, but then later on, you're like, Oh, I did half an hour on the bike, I should record that. That makes a lot more sense. Okay. But just going back to the streak stuff for a second.

[00:47:38] **Ben:** I mean,

[00:47:39] **Carol:** Oh yeah. I think we've kind of, you know, veered off a few times,

[00:47:43] **Ben:** that is our, modus operandi. make sense then?

## [00:47:47] Storing Dates

[00:47:47] **Ben:** Okay. So we're okay with storing date as a, but what is that date? Is that date? That's the

[00:47:53] **Ben:** date in the user's

[00:47:54] **Ben:** time zone. Okay.

[00:47:55] **Adam:** It's whatever day the user feels like it is.

[00:47:58] **Ben:** Okay. Okay. Yeah. I think that's, I think that's definitely where I need to go. The idea of

[00:48:03] **Carol:** but I think, I think defaulting it to what the browser date is, is fine. Yeah.

[00:48:11] **Ben:** agreed, agreed. Okay. Okay. This is, this is literally going to be the first time in like 10 years where I've wanted to store a date that is not in UTC time. And I think it's just been really trippy for me to think about it.

[00:48:26] **Adam:** Yeah, I've done it a couple of times and you're right. It's like, wait a minute, this doesn't feel right. This is unnatural.

[00:48:31] **Ben:** It's, it's already the, the worst part was for years, years, we had servers at work that weren't actually in UTC. They were on Eastern time, I think, or they were on like Chicago time. I forget what time they were in. So we would store everything in UTC, but we're constantly in ColdFusion parlance doing the date convert.

[00:48:51] **Ben:** Local to UTC to get it into the database. And then sometimes people forget to convert it back. I think to local on the way out before they did date math, like there was, there was, there was life just gets easier when everything on the server is actually running in UTC.

[00:49:07] **Carol:** Oh yeah.

[00:49:08] **Ben:** Much less to think about, but then you think to yourself, sorry, this is total tangential for a second, but it's like, do I want to assume that the server is running in UTC and stop doing the date conferred between local and UTC when I have to do certain things Or do I just lean into the, well, of course the server's running in UTC, that's the only sane operation, and I'm not going to worry about converting dates at the server level.

[00:49:35] **Adam:** Is your server also hosting the database? Or is that on a

[00:49:39] **Ben:** At work, no, but in my personal world, yes.

[00:49:42] **Adam:** DDF.

[00:49:44] **Ben:** Yes, Dig Deep, Dig Deep Fitness, everything's on one box, but at work we have RDS and then various containers.

[00:49:51] **Adam:** My personal preference, and take that for what it's worth, is a database server, without a question, should be running on UTC.

[00:50:00] **Adam:** It

[00:50:01] **Ben:** I'm almost certain that would be yes.

[00:50:03] **Adam:** And, as a byproduct, as a personal policy, not that I Enforce this elsewhere, but it's personally, I never, if I want the current time, date and time, whatever, I never insert the current date and time as believed by any code.

[00:50:21] **Adam:** It is always using the like current underscore timestamp keyword in MySQL.

[00:50:26] **Ben:** Oh, interesting. I've definitely used that when running queries, like running reports and stuff, but I've never used it as a way to actually persist data. Hmm. Interesting.

[00:50:41] **Adam:** Now, I don't know how that you could, again, we're, we're kind of at odds here, right? So that you could run that through a date format and pass it into a date only field. and you could do

[00:50:51] **Ben:** you could use it.

[00:50:52] **Adam:** on it.

[00:50:53] **Ben:** I mean, you, if you have a date only field in the database, you can throw basically anything at it and it'll just store the date part. This is my, is my understanding.

[00:51:02] **Adam:** and if you wanted to, you could do time zone conversions on it. MySQL has good functions for that. But again, I think going back to what we were talking about earlier, what matters is what the user thinks this workout day is. So it doesn't, it doesn't matter what the current timestamp is. It matters what the user thinks.

[00:51:20] **Ben:** I like this. I like this. I had not considered that at all. When I was trying to think about this, I'd never occurred to me that the user would want to enter a date, but it also never occurred to me that you want to enter the date for your workout yesterday

[00:51:33] **Adam:** you, yeah, have you ever done any streak tracking?

[00:51:36] **Ben:** no, I have not. So this is, this is all new territory.

[00:51:41] **Adam:** As, as a forgetful person. Yeah, for

[00:51:43] **Carol:** yeah, definitely.

[00:51:45] **Ben:** Alright, groovy. Well, this has been very helpful.

[00:51:48] **Carol:** Yeah, glad we could help.

## [00:51:49] Dev Database Changes

[00:51:49] **Ben:** I'm excited. I tell you, it's very, it's, there's something so freeing about having an application that no one is using, but it is still in quote unquote production, right? It's not just in my local development environment. And because it is, again, quote unquote, in production, but no one's using it, I feel so much. Lucy goosey about data. I'm like, Oh, tomorrow I'll just write a migration script that completely drops a table or truncates a table or creates a new column and then generates data for it based on an existing column. And when you have 16 records, it's totally not a big deal. If I was working in a database that had 300 million records, you can't just flippantly be like, Oh, let me just, decrease the VAR car in this or change it to a date time or something.

[00:52:34] **Ben:** So it's, I don't know. It's. It's very freeing in that It allows you to think about how data can be transformed and not data as a, an anchor keeping you in place. Like I, I get to lean into the idea that data can be changed and, and because of that, I don't have to, you know, do so much hand wringing about, oh, is this exactly the right data model? Maybe it's not, but who cares? Then I'll just change it tomorrow and I'll change it the day after that until it works. And then

[00:53:07] **Carol:** that's the fun part of building.

[00:53:08] **Ben:** yeah, exactly.

[00:53:10] **Ben:** You can, you feel like. You can make mistakes and it's okay. And I think that's such a healthy mindset to have. I think too often at work, we try to, you know, like think through to the nth degree, what something is going to be like, and we go round and round in circles and we have daisies about how something should be designed and what's the trade offs and what about performance.

[00:53:32] **Ben:** And is someone doing proper load testing on a database that has the production equivalent volume of records? And you, you know, it's a lot of times, I think that's just too much thinking. Just get something out there and see what happens. And if you gotta adjust, adjust.

[00:53:49] **Carol:** Yeah, to kind of talk about the data build, right? So I remember working previously at a job where I had added something to the database and it was just a column to a table and I wasn't really using it yet. So it was only in the dev databases and where we were, everyone ran their code locally, but you connected to a shared development environment.

[00:54:10] **Carol:** That way no one had to spin up a database on their own, have a local copy of it. You just use the shared. Because it also had the, the cleaned out data. So production data would come down, we'd strip out everything. And then you were able to use that day. Yeah. So it's really good for actual volume testing because the volume matches what's in production, but it's not gonna hurt anyone.

[00:54:31] **Carol:** If you send emails to everything, cause it's like test at test. com. So you're still okay. If you accidentally screw up. Anyway, so I remember adding a column and being like, Oh, I really don't think I'm going to use this. And then it come time to move it up to like the QA and staging environments. And I dropped that column out of dev.

[00:54:48] **Carol:** And all of a sudden the Slack channels blowing up because someone's like, what happened to this column? Why did we decide to get rid of it? And I was like, well. It was never really supposed to be there, so from then on, whenever I would make changes, I would make sure I created, like, my own table, and everywhere in the code, I would reference my version of that table to make sure it was solid, so no one accidentally started coding against development columns that weren't really ready and might not ever go into production.

[00:55:16] **Ben:** Yeah. Well, that's another thing that I've been trying to focus on in terms of building this new system is keeping my data's, my data tables narrow. It used to be if I had a user table, take, okay, so just take timezone for example. If I wanted to store the user's timezone, old Ben would have said, hey, I have a user table I'll just add a time zone column to that table because it's the user data and new Ben says to himself, no, the user table stuff you need to access on like every single request.

[00:55:50] **Ben:** And you don't necessarily need time zone on every single request. I'm not saying that's actually true, but that's why I'm forsaken discussion here. And so new Ben wants to actually create a new table for like user location preferences or something like that. And like that has time zone in it. And maybe I only read it occasionally.

[00:56:08] **Ben:** Maybe I only write to it once a year or, you know, whenever the user moves. And I'm, I'm much more enjoying this idea of keeping the data model numerous, but narrow. And I think that, I think that has a lot of benefits.

[00:56:23] **Adam:** We should talk more about that because at first blanch, I'm thinking, no, I don't like that. So let's save that for another show.

[00:56:29] **Ben:** Sure, sure.

[00:56:29] **Carol:** And see, I do like it, so this should be a good topic.

[00:56:33] **Ben:** Fight, fight.

## [00:56:35] Patreon

[00:56:35] **Adam:** All right. Well, I guess then, I should just let you know that this episode of Working Code is brought to you by user number two. Whose current workout streak is, uh, 300, I'm sorry, 3,000 days and counting. Gotta give credit where credit's due. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:56:55] **Adam:** Our patrons cover our recording and editing costs and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. We actually do have a new patron this week, which is somebody who's on a free trial. I just want to point that out. We Patreon,

[00:57:11] **Adam:** yeah, Patreon added free trials.

[00:57:13] **Adam:** It's a, I believe it's a 14 day free trial. so you have two weeks to go download our entire back catalog of, of aftershows and episodes. If you want to boost, boost our numbers by going back and redownloading those episodes, be my guest.

[00:57:24] **Ben:** Heck yeah.

[00:57:24] **Adam:** But, uh, yeah, free trial for two weeks. So, Madison Turner, thanks for joining and, hope you stick around.

## [00:57:31] Thanks For Listening!

[00:57:31] **Adam:** this week. Oh, so I guess I should go ahead and mention, for people who do, join our Patreon, they get a special podcast feed where they get, early access to new episodes and our after show the after show, we just keep the mics on and keep talking. we've got a couple of things to tease for tonight's after show.

[00:57:46] **Adam:** Is this, is this you Carol, the first one here?

[00:57:48] **Carol:** Yeah, yeah, that's me.

[00:57:50] **Adam:** Screw notebooks, take notes on cardstock, which is very interesting coming from you. You're a notebook person, so I'll be interested to hear what that is. And personally, I have a streak that I want to end and a streak that I want to begin.

[00:58:03] **Ben:** Oh, nice tie in.

[00:58:04] **Adam:** This would be a good, yeah, good, good tie in for this episode.

[00:58:07] **Adam:** So,

[00:58:08] **Tim:** Then how many of them are in your underwear?

[00:58:12] **Carol:** well, nevermind.

[00:58:15] **Adam:** I mean, I wear underwear every day. Is that a streak?

[00:58:19] **Tim:** Do you have streaks in your underwear?

[00:58:22] **Adam:** Ah, right. Moving right past that. if you'd like to help us out, you can go to patreon.com/WorkingCodePod. that's it for us this week. We'll catch you next week. And until then,

[00:58:31] **Tim:** Remember, your heart matters, whatever time zone you're in.

[00:58:34] **Adam:** or whatever time zone you believe you're in.

[00:58:35] **Tim:** Mmm, true.

[00:58:36] **Carol:** good one.
