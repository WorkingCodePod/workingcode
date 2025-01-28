---
title: "037: Brian Klaas Talks Cloud"
description: 'Brian Klaas (@Brian_Klaas) is a Senior Technology Officer and instructor at the Johns Hopkins Bloomberg School of Public Health; he runs a team that builds a Learning Management System (LMS) running on a hybrid cloud; he''s been using and extolling the value of Amazon Web Services since 2009; and, he''s a well known and respected speaker and leader within the ColdFusion community. According to him, the overarching value that AWS provides is the outsourcing of "undifferentiated heavy lifting": AWS builds the infrastructure that you don''t want to, allowing your team to focus on your own business-critical product-lines.'
date: 2021-08-25
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/037-brian-klaas-talks-cloud/id1544142288?i=1000533080737"></iframe>

As we alluded to in [Episode 20: Carol Needs a Consult][working-code-20], there are a lot of different products under the Amazon Web Services (AWS) umbrella. In fact, the number of products is somewhat mind-boggling. It can be overwhelming just figuring out where to start, let alone understanding which service is right for which job, how to configure that service, and how to get that service to integrate with all the other AWS services. Thankfully, we have Brian Klaas as a very special guest on today's episode.

[Brian Klaas][brian-klaas] ([@Brian_Klaas][brian-klaas-twitter]) is a Senior Technology Officer and instructor at the Johns Hopkins Bloomberg School of Public Health; he runs a team that builds a Learning Management System (LMS) running on a hybrid cloud; he's been using and extolling the value of Amazon Web Services since 2009; and, he's a well known and respected speaker and leader within the ColdFusion community. According to him, the overarching value that AWS provides is the outsourcing of "undifferentiated heavy lifting": AWS builds the infrastructure that you don't want to, allowing your team to focus on your own business-critical product-lines.

## Notes &amp; Links

- [ColdFusion](https://www.adobe.com/products/coldfusion-enterprise.html)
- [Azure Cloud Services](https://azure.microsoft.com/)
- [Google Cloud Services](https://cloud.google.com/)
- [Alibaba Cloud Services](https://us.alibabacloud.com/)
- [Amazon Web Services (AWS)](https://aws.amazon.com/)
- [AWS S3 (Simple Storage Service)](https://aws.amazon.com/s3/) and [Storage Classes](https://aws.amazon.com/s3/storage-classes/)
- [AWS Glacier](https://aws.amazon.com/s3/glacier/)
- [AWS SQS (Simple Queue Service)](https://aws.amazon.com/sqs/)
- [AWS SNS (Simple Notification Service)](https://aws.amazon.com/sns/)
- [AWS EventBridge](https://aws.amazon.com/eventbridge/)
- [AWS Fargate](https://aws.amazon.com/fargate/)
- [AWS ECS (Elastic Container Service)](https://aws.amazon.com/ecs/)
- [AWS EC2 (Elastic Compute Cloud)](https://aws.amazon.com/ec2/)
- [AWS Athena](https://aws.amazon.com/athena/)
- [AWS Kinesis](https://aws.amazon.com/kinesis/)
- [AWS Step Functions](https://aws.amazon.com/step-functions/)
- [AWS Glue](https://aws.amazon.com/glue/)
- [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
- [AWS Lambda Functions](https://aws.amazon.com/lambda/)
- [AWS VPC (Virtual Private Cloud)](https://aws.amazon.com/vpc/)
- [AWS DynamoDB](https://aws.amazon.com/dynamodb/)
- [AWS X-Ray](https://aws.amazon.com/xray/)
- [Principles of Chaos Engineering](https://principlesofchaos.org/)
- [Strangler Pattern](https://martinfowler.com/bliki/StranglerFigApplication.html)
- [A Cloud Guru](https://acloudguru.com/)
- [@killedbygoogle](https://twitter.com/killedbygoogle)
- [Certifications: The Good, The Bad & The Ugly](https://www.lastweekinaws.com/podcast/aws-morning-brief/certifications-the-good-the-bad-the-ugly/)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[brian-klaas]: https://www.linkedin.com/in/brianklaas/
[brian-klaas-twitter]: https://twitter.com/Brian_Klaas
[working-code]: https://workingcode.dev/
[working-code-20]: https://workingcode.dev/episodes/020-carol-needs-a-consult/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/037-brian-klaas-talks-cloud.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** Like earlier you had mentioned step functions and I don't exactly know what step functions are, but I assume if you weren't using step functions, you would have to do something.

[00:00:09] **Ben:** Cute choreography where you're taking like messages off of one cue and then putting them onto a next queue. But like that doesn't like, you're not in the business of building queue management. Right? So like, why build that when you could be concentrating on product development

[00:00:22] **Brian:** Absolutely.

[00:00:23] **Tim:** functions. There are functions that you love less than the functions you wrote.

[00:00:27] **Tim:** Step

[00:00:28] **Brian:** But right now, it is, it's one of the real benefits when you're using it. When you buy into AWS or GCP or Azure, use everything seriously use everything because that's where the real power lies tapping into not just one service, but services tapping into Abila services. And of course, AWS and GCP and Azure, happy to take all your money, right?

[00:00:46] **Brian:** Because these services cost money at the end of the day, but it gives you a set of options that you wouldn't otherwise have. And it just easier to write stuff. I

## [00:01:10] Intro

[00:01:10] **Adam:** It is show number 37 and on today's show, we have a special guest, joining us today. We have, we have,Brian Kloss on to talk to us about the cloud is

[00:01:19] **Tim:** you do.

[00:01:20] **Adam:** expert. So, get somebody smarter on you never want to be the smartest one in the room. So that's why we pulled Brian.

## [00:01:24] Adam's Triumph

[00:01:24] **Adam:** And, but as usual, we are gonna start with our triumphs and fails and it looks like it's my turn to go first. So I'm going to start with a triumph, which is that my recent experience writing a rule evaluation engine, AKA Semafore. If you guys have been listening to recent episodes, the feature flag engine that I wrote for CFML has come in really handy.

[00:01:43] **Adam:** this afternoon, on a task, I dropped onto my desk to help out with this project. And, it turned out what was needed from me was to write a rules engine and sort of like a DSL for, for doing that. And I burned through the whole thing in like one afternoon and, I'm really happy with, I wrote tests for it and everything, so, oh yeah.

[00:01:59] **Ben:** can you expand a little bit on what a rules engine?

[00:02:03] **Adam:** Yeah. So,

[00:02:04] **Adam:** basically let's see the feature that we're building is like, survey questions, but survey questions that you can drop in and different modules of the application, right? So you, maybe you have some sort of questions you want to add to an event registration or to an online giving form or to a membership sign up.

[00:02:19] **Adam:** And so we want a central they're all going to work basically the same way. So we want a centralized place to have them. And then we want to be able to apply different rules for whether or not to display any given question on that form. So, for a donation form, you might say, we'll only show this form.

[00:02:35] **Adam:** If the total gift amount is over a certain number of dollars, or if we're inside of a date range or if,the there's multiple giving forms. So if you're on a certain giving form, that sort of thing, like allow you to apply rules that are specific to that module. To this larger system. And so the DSL allows you to, create rules that are applicable to some random dynamic data that you'll be getting later applicable to the module where you're using it.

[00:03:00] **Adam:** and allow those to be evaluated. And it's not technically meta programming, but it feels like it should be called Metta programming. Right. it's very, very dynamic.

[00:03:08] **Ben:** Very cool.

[00:03:09] **Adam:** Yeah.

[00:03:11] **Tim:** I'll nod my head and pretend I understood that. So,

[00:03:13] **Adam:** Well, very much like ripping off the code that I wrote for feature flags, but I did start fresh.

[00:03:19] **Tim:** okay. You wrote tests that impresses me?

[00:03:22] **Adam:** 12 of them, but

[00:03:24] **Brian:** better than most of us.

[00:03:25] **Tim:** yes. That's 12 more than I wrote today.

[00:03:28] **Adam:** so that's me. What you got going on, Ben?

## [00:03:30] Ben's Triumph

[00:03:30] **Ben:** I'm going to go with triumph and that is that I did a vacation.

[00:03:33] **Adam:** I saw.

[00:03:34] **Ben:** was out, up in Vermont. I live in New York. I was up in Vermont from Saturday to Wednesday. And.

[00:03:40] **Tim:** Say hi to Bernie

[00:03:41] **Ben:** It was, it was beautiful. And, I basically just like zoned out a lot. I even had moments where I was sitting there staring off into space and I thought like, Hey, this would be a great opportunity to think about some work stuff.

[00:03:53] **Ben:** Like while I'm just peaceful and sitting here. And I couldn't even, I couldn't even hold a thought. I, it just like, it would go into my head and then all of a sudden it would be gone and I couldn't concentrate. And I just sort of leaned into that and just stared at the trees and the sky and the water.

[00:04:08] **Ben:** And it was, it was very peaceful. So I feel

[00:04:11] **Brian:** Did you completely unplug no work, email,

[00:04:13] **Ben:** I check my slack mostly for a second comradery. Like I just like to see people doing stuff. not very often, maybe like just a handful of times a day, like I'm not responding really. Or like, I'll go with a thumbs up or something like, like one of my teammates got promoted while I was gone.

[00:04:30] **Ben:** So I dropped the thumbs up. but mostly I don't check email or anything like that, really? so it was pretty, I, it was an effective vacation. I don't vacation very often, mostly because it doesn't occur to me. but so

[00:04:41] **Tim:** I was going to ask, are you normally a good relaxer when it comes to vacations?

[00:04:46] **Ben:** I don't know. I don't know. maybe not. I'm not sure. we, yeah, well, like when we vacation we're not like live by the beach type people, my wife who does all the planning, she's always like, go, go, go. And she has a bunch of stuff lined up. So we're like driving around a lot and seeing different places.

[00:05:03] **Ben:** And so there's not a whole lot of downtime, but when there is, that's when I just sort of stare off into space and I enjoy it, that's my, one of my favorite pastime staring off in the space.

[00:05:14] **Adam:** Yeah. I mean, Ben, you and I have both been working from home full-time for eight plus years now. I think a skill that I did not have when I first started doing that, that I have fortunately cultivated over the last eight years is the ability to really disconnect at the end of the Workday and on the weekends.

[00:05:29] **Adam:** Like that's my time. That's my family time. Yeah.

[00:05:33] **Ben:** Yeah, I definitely I've talked about this before. I have very strong boundaries around when I'm work working. my one Achilles heel is I do like to just monitor slack just to, I dunno, I just, for the heartbeat of it all, it, it doesn't feel like work like, cause I don't respond. It's more just think, I don't know.

[00:05:52] **Ben:** I it's probably, yeah,

[00:05:54] **Tim:** you're watching the

[00:05:54] **Ben:** it's probably a bad habit, but it doesn't stress me out. So anyway, Tim, what do you got going?

## [00:06:00] Tim's Triumph

[00:06:00] **Tim:** Well, I'm gonna, Hey, three triumphs in a row here. Here we go. 1, 2, 3, Adam, Ben may, hopefully Brian will have one. I'm going to take a triumph here today. So, I'd built a project and I responded now for reasons that I, at the failure that I had, that I didn't do due diligence, and I have to switch providers for a certain part of this.

[00:06:18] **Tim:** I'm having to refactor, but refactoring and changing the code to do new features is a whole lot easier when you wrote it clean in the first one.

[00:06:27] **Ben:** Good boundaries.

[00:06:28] **Tim:** So having good separations of concern, having good OB object models and everything. I mean, all I'm really doing is just changing. It's one part that was generating the XML.

[00:06:39] **Tim:** And I think I've talked about this before, but you know, I'm actually in the guts of it now, I got stuck a little bit, cause I was going through some personal issues and depression that I was talking about a few weeks ago, but got through all that Headspace junk and now I'm like plowing through it. I'm like, wow, this is really great when you can, everything is separate out and it's discrete parts and all I'm doing is changing this bit.

[00:07:00] **Tim:** It doesn't break everything, which is so unlike some of the code from, 15 years ago that I wrote that was like, you change one thing and everything falls apart. So it's like, yeah, writing clean code is really, really good.

[00:07:13] **Adam:** so you're telling me all those promises in the book actually do come true.

[00:07:18] **Tim:** Yeah. yeah, definitely. uncle Bob was right. I wish I had read him much earlier in my career would have saved me a lot of headaches. So that's my win.

[00:07:25] **Ben:** Nice.

[00:07:26] **Adam:** So that brings us to Brian. Brian, what do you got going

[00:07:29] **Tim:** our guest of honor

## [00:07:29] Brian's Triumph

[00:07:29] **Brian:** well, I have a, when not

[00:07:31] **Tim:** a row. What we are winners today, we are winners guys.

[00:07:35] **Brian:** this bizarre. so my win is that at long last, my oldest son's starts college a

[00:07:43] **Adam:** No way.

[00:07:43] **Ben:** cow.

[00:07:43] **Brian:** And I'm super happy about that because, it's in a very long road to hoe to get to this point. He is not the most academically inclined person.

[00:07:52] **Brian:** but one of the few silver linings the pandemic has brought, was a year away from school and working in a warehouse with, lots of other people, who didn't do anything after high school. And, he sort of come to realize that to have the life that he wants, he's going to need to go to college, whether he wants to or not.

[00:08:09] **Brian:** and there was a lot. Pushing and pulling and, not being truthful and honest about registering for classes and fun, things like that. And, it's all been settled and everything's registered in New York, his books, and he's all set up and turned in his immunization forms and has the move in date for the dorm.

[00:08:24] **Brian:** So I'm super excited because I know it's going to be really good for him in the long run. And we get our 19 year old out of the house, which is also a win.

[00:08:32] **Ben:** Is he, is he moving?

[00:08:33] **Tim:** Working in a warehouse. Good object lesson in

[00:08:36] **Brian:** yeah, absolutely. I mean, it was good for him and he loved the people that he worked with and had great relationships, but it really did give him a perspective on what he had and what he has to do to move forward in terms of the life that he wants to have as an adult.

[00:08:49] **Brian:** And I think that's, that was invaluable.

[00:08:52] **Tim:** it's great to have a great workplace experience, but we need to get the paycheck and go, wow. Okay.

[00:08:57] **Brian:** Right?

[00:08:58] **Tim:** can't have this, this and this and this. Maybe dad was right,

[00:09:03] **Brian:** Dad is never right. Dads are we are the meanest dads in the world and we're never right about anything. Believe you, me and my husband will tell you that

[00:09:13] **Tim:** Yeah.

[00:09:13] **Brian:** anytime you ask.

[00:09:14] **Tim:** It's the old mark Twain quote where, when he was 18, his father was the stupidest man in the world and he left home and came back to visit when he was 24 and realized how much my father had learned in those few years I was gone.

[00:09:27] **Brian:** Yeah. Yeah, exactly.

[00:09:28] **Ben:** far away or staying low?

[00:09:30] **Brian:** it's about an hour. So I live in Frederick, Maryland, which is a hour north of DC hour, west of Baltimore and the center of the state. And then he's going to shepherd university in Shepherdstown West Virginia, which is about another hour

[00:09:42] **Tim:** Almost seven.

[00:09:43] **Brian:** Yeah, just on the border of Maryland and West Virginia in that area.

[00:09:46] **Brian:** It's a beautiful little town. They have a great, nationally recognized theater festival every year. Like really good theater festival every year. and it's a good little school and he's going to be, I think, pretty happy there.

[00:09:54] **Ben:** very cool. Well, congratulations.

[00:09:56] **Brian:** Yeah. Very good. One down two to go.

[00:10:00] **Adam:** all boys? Okay,

[00:10:02] **Brian:** it's a house full of testosterone, five guys and a male dog.

[00:10:06] **Brian:** So

[00:10:07] **Tim:** Wow.

[00:10:08] **Adam:** yeah.

[00:10:09] **Brian:** the, our younger two went to camp, it was a struggle to not have our entire first floor smelled like feet and dirty socks. So since they've come back, it's like, take your shoes upstairs. Take your socks upstairs

[00:10:21] **Adam:** boys, they just get undressed as they walked down the hall.

[00:10:25] **Brian:** pretty much. Oh yeah. There's underwear here. Shorts there. It's great. Love it.

[00:10:30] **Tim:** Awesome. All right. You want to lead us

## [00:10:33] Brian's Introduction

[00:10:33] **Adam:** Yeah, sure. So, Brian, for those that don't know who you are, can you give us a little bit of a primer? Who are you? What's your background and how did you become a cloud guru of ninja?

[00:10:44] **Brian:** A cloud guru. I don't know about that. There's a whole like company that calls themselves now. so yeah. Yeah. They're actually, they have great

[00:10:49] **Tim:** not sponsored.

[00:10:51] **Brian:** you actually want to get up to speed really quickly, it was some great resources on AWS and other cloud providers. a cloud guru.com is a great, a service insight.

[00:10:59] **Brian:** Their trainings are excellent and they have this really kind of cool playground feature you can do. It's not inexpensive, but definitely worth it. I think. so a little bit about me, I guess, since you prompted. so I have worked for many years at Johns Hopkins university at the Bloomberg school of public health where I am the senior technology officer.

[00:11:17] **Brian:** Working primarily in the center for teaching and learning and it's our job to do, online learning stuff. And one of the things we do crazily enough is we have a learning management system, that we built and have maintained for many years. And in spite of the university going through various other learning management systems, they've stuck with ours at the school because they feel it's a superior experience and can do things that the other LMS has can because we control our own day.

[00:11:38] **Brian:** Rather than using a third-party tool. It sounds a little crazy, but, it is a differentiator for us. And what's great for me is that as the lead, I get to decide what happens and what does not. And, that's, I do that. And I also, have I have a faculty appointment there. I teach communication for health science professionals, which is very different right than my, web development inside.

[00:11:59] **Brian:** I lead a team of six developers, and, who developed this learning management system. But I also do all this communication stuff. And the two kind of go hand in hand because, if you're going to be an effective developer or you're going to be an effective leader or manager, certainly in tech, you have to communicate well.

[00:12:12] **Brian:** So it is the superpower of every great developer and every great manager and leader, certainly in technology is being able to communicate clearly and effectively about what you want and what you need and document these things and being able to write really well. These are all super important skills, to have anyways, The reason why I'm here today is because, I've been working with AWS for awhile.

[00:12:33] **Brian:** And, I think we first started using S3 simple storage service, back in 2009, maybe even 2008. I can't remember, is when we start using it. And I say to people, if I could go back in time and do everything all over again, I would've stayed with S3 and put everything there and never put anything anywhere else, because it's one of like, it's the eighth wonder of the world.

[00:12:53] **Brian:** It really is. It's an amazing, incredible piece of engineering and software and user experience and a whole bunch of other things. And. You all know me on this podcast? mostly through speaking in the CFML the ColdFusion, markup language, ColdFusion,lit community. I talk a lot at conferences, both inside and outside the CFL community.

[00:13:13] **Brian:** CFML community about AWS, because I love talking about it. It's super liberating and freeing for me as a developer because I still write code and it's super liberating and freeing for me as a manager who wants to have his team do better, provide innovative, interesting features and for them to grow as professionals.

[00:13:33] **Brian:** I think that's one of the most important jobs I have is making sure they grow as professionals, because as we all know, it's super easy to stagnate. It's super easy to look at your job as being like the same thing you did five years ago, or 10 years ago, you can get away with a lot of that. But if you don't grow, you'll never really do better for yourself.

[00:13:51] **Brian:** And for the people who are relying on you to grow, meaning your clients, the people that you work with, the people who fund you. so growth is super important to me. and AWS really lets me do that personally and professionally. And then I got to talk about it on forums like this, or at

[00:14:06] **Tim:** Which is why we asked you here.

[00:14:09] **Adam:** Okay.

## [00:14:09] Migrating To The Cloud

[00:14:09] **Ben:** You have, what can I just to tangent for a second on S3 story? So S3 was my first introduction to Amazon web services and we were in this crazy situation. We had a early days Invision. We have this network attached storage device. They had, I think like two terabytes of storage on it or something which, is mind boggling to me.

[00:14:31] **Ben:** And, but we were eating through it like crazy. And at one point the hosting provider that we're using came to us and said, Hey, you're running out of storage. we can provision a larger, like a 10 terabyte drive, but like you have to pay us. it was like $50,000 today for us to be able to even order it from the company that's going to provide it.

[00:14:50] **Adam:** Wow.

[00:14:52] **Ben:** And,and we were like, well that's,

[00:14:53] **Adam:** nice data you got. There'll be a shame if something happened to it.

[00:14:56] **Ben:** and, so we were like, oh, that's a tremendous amount of money. Let's see if we can move everything over to S3. And like, literally we were looking at our burn rate in terms of hard drive space, and we were going through something like it would have taken like 32 days estimated to eat through the rest of our hard drive space.

[00:15:14] **Ben:** So I started learning about S3 and, I started, I had this task that literally ran in a browser and it would grab like a thousand records at a time and then put them up to S3 and then grab the next thousand records. And I literally had it open on my desktop and it was just constantly refreshing. And I had that running straight for like 30 days.

[00:15:35] **Ben:** And it was, was like neck and neck to see if we could get all of the files off the drive. And,and the challenging part,

[00:15:45] **Tim:** It's a literal race

[00:15:46] **Ben:** craziest part was because we had to, we essentially had to dual write the files because we had to write all new files to S3 and to the local NASA network attached storage.

[00:15:56] **Ben:** And then we would continue to only read from the network storage. And then there was a flag that we would flip and then suddenly everything would start reading from S3. And I think we, we finally got the flag flip. the day before we would have run out of storage, it was like the most stressful time in my life, but it was also like, so exhilarating and S3 to Brian's earlier point.

[00:16:16] **Ben:** Like I'll never not put stuff in S3 going forward. Like it just it's magic. I don't, I, and maybe that, like, just to quickly, step into like another thought is like, one of the worries that I have with Amazon web services is like, it feels so magical. It feels like, oh, that's someone else's problem.

[00:16:36] **Ben:** They've solved that they're obviously much smarter than I am, but like, is that kind of a dangerous mindset to have

[00:16:43] **Brian:** No, I would say no. I mean, to jump in and say, answer that question, I would say no, let it be somebody else's problem. Undifferentiated heavy lifting is what Amazon says over and over again. Right? Why should it be your job to deal with network attacks, attach storage? Is that your area is that Invision's area of expertise?

[00:16:58] **Brian:** The answer is no, not at all. It's not my area of expertise, and,running compute instances, that's not my area of expertise or, Kubernetes clusters. Nobody wants to do that for real. Right. And nobody wants to do that. and letting somebody else take care of that and paying them.

[00:17:13] **Brian:** Sometimes not very much and sometimes a significant amount to do that, is in many ways I think is the value, right? if, why do you need people running database servers? And why do you need people running the network hardware and network interfaces and,X function, execution environments, whatever it is, you got to pay people to do that.

[00:17:30] **Brian:** And that's not helping your business be any better at helping in your case. people design and collaborate with

[00:17:37] **Brian:** one another. And so I think, in that

[00:17:38] **Adam:** did his homework.

[00:17:39] **Brian:** of

[00:17:40] **Ben:** Yeah,

[00:17:40] **Brian:** those kinds of things. Yeah.

[00:17:42] **Brian:** I'm speaking to AWS line there, but it also, I made sure for me, I think Ben, your experience, I mean, yeah, I definitely had those browser page, single page functions that like pull a thousand records at a time and do something with them or 5,000 records.

[00:17:53] **Brian:** I'm gonna have done plenty of migrations that way. I'm ashamed to say, but it's true. but that kind of pattern, the strangler pattern, right where you start, having everything in another service in AWS or Google compute or Google cloud or Azure. And then at one point start moving everything over to that, I think is a great way to get started.

[00:18:10] **Brian:** people always say well, but I've got to do everything at once in the answers there's no, you don't. Right. You can start moving stuff over. And then at some point flip the switch on. Everything using feature flags. Right. Which I know you're a huge fan of Ben and Adam was talking about earlier using feature flags to do that kind of work.

[00:18:25] **Brian:** I mean, you can slowly strangle, as I say, it's not the right, the nicest word, but it's a great way to get started with pretty low investment and pre low risk. And I think that's what I think people are just terrified. Like they think I have to move everything to the cloud and I'll tell you,our primary compute instances are still on our data center at the Bloomberg school of public health because of legal reasons.

[00:18:45] **Brian:** and because of other monetary and business reasons, we can't move them. So for

[00:18:50] **Tim:** It's a hybrid cloud.

[00:18:51] **Brian:** a hybrid cloud. Yeah. The worst part of the worst of all possible worlds. Um, but for me, what that lets me do is say, okay, what can we do? That's completely outside of this. And that's super freeing and liberating. Like I don't have to worry about someone saying, no, you can't put this in AWS because you have to run in the data center.

[00:19:06] **Brian:** Well, no, I can just run it in the cloud and that's that, and it's fine. And we can explore and play and grow and provide functionality. We wouldn't be able to otherwise while still maintaining that sort of core sort of data center activity, that we'll probably never be able to get rid of.

[00:19:21] **Adam:** Well said.

[00:19:24] **Brian:** Thanks.

[00:19:24] **Adam:** all the right buzzwords in there.

[00:19:26] **Ben:** Okay.

[00:19:27] **Brian:** did. I am very, very buzzword

[00:19:29] **Ben:** So S3 to me feels like a super low entry into Amazon web services, because I mean, even in the ColdFusion world, especially you can write a file. And the fact that you could write to a hard drive or you could write to S3 is almost like completely abstracted away. If you're not going to use something like the Amazon SDK, but like the next I want to use Amazon web services, to me feels like going from S3 to what do I use next?

[00:19:58] **Ben:** Like then it becomes a significant jump in complexity. Like it's not just a hand wavy over some sort of abstraction. Like now I have to actually start thinking about how to rearchitect or completely changed the way I think about architecting an application. what do you think is like the next natural ingress into Amazon web services?

[00:20:20] **Brian:** So, I think S3 can be the next natural ingress because you and I come from, all four of us at some point had been in a CFML background. Right. And the CFML engines make it real easy as Ben Joe said to say, point to S3 or point to a local file system. And it's all kind of abstracted away, but that's just reading and writing files.

[00:20:36] **Brian:** What we're missing are things like storage class.

[00:20:39] **Ben:** Okay.

[00:20:39] **Brian:** Right. So you don't want to, if your file is going to be in, infrequently used, you don't need, sub 10 millisecond response times on those files, put it in infrequent access. If you're not to me, if it's back of an archival, then put it in, one zone infrequent access, and that can save you a significant amount of money every single month, especially as you're moving on from gigabytes to terabytes or petabytes of data that you're storing inside of S3.

[00:21:02] **Brian:** And you can't do that with our ColdFusion engine. So the next step would be say, okay, let me see how I can use the, in our case, Java SDK, or the Python SDK, or the node SDK, whatever it is to write files at to a different storage class. So I can do that automatically and save myself money. Right? That's a, that's an easy sort of, or I think was sort of a logical next step because everyone wants to

[00:21:22] **Ben:** Just a point of clarity because Tim had mentioned glacier, but glacier is a different service and it's not quite storage classes. Right. You're talking about something slightly different.

[00:21:31] **Brian:** Right. It storage, but, it's not request response-based storage, it's asynchronous storage in the sense that it can take five minutes to get your file back or up to eight hours to get your file back. And that's not, people are like, oh, put it in glacier because it's super cheap. Well

[00:21:43] **Adam:** It's well named.

[00:21:44] **Brian:** never going to get the file, Yeah. You have to write a whole, like, ACR has workflow to get the file, but I do understand where you're coming from Ben. And so, S beyond.

[00:21:51] **Ben:** right.

[00:21:51] **Brian:** I think from an architectural perspective and starting to think in the cloud, think like the cloud, the next apps are things like simple queue service, simple notification service breaking apart, or even event bus or sorry, event bridge.

[00:22:03] **Brian:** That's, what's called a vent bridge. Thinking about how you break your application down into a series of steps as Tim was talking about earlier that are unique and isolated from one another, so that you can rewrite a small portion without affecting anything else. so you can use simple Q service to, say these things.

[00:22:19] **Brian:** These are all the things I need to process. Right. I have a hundred items I need to process. I need to make a hundred different PDFs. I'm just going to put them into simple Q service that have, a ColdFusion function or an, a Python or node function that pulls that back out. One at a time, it makes that PDF.

[00:22:31] **Brian:** For me, it's a pretty simple service to use. And it gets you thinking as the cloud in the cloud, right? Without about issues of, asynchronous processing and resiliency and failure, and what happens in modes of failure. And just thinking about that around events, right? Something happens and I respond to it because that's ultimately how the best of AWS really works and the best architectures in AWS really work.

[00:22:53] **Brian:** So I would encourage folks to look at simple queue service, simple notification service. They are different, they serve different purposes, but they're super powerful and a great way to start thinking of that. And they're easy to use. That's the other thing they're easy to use. They're not complex like far gate or elastic container service or the 17 different ways you can run containers on AWS.

[00:23:12] **Brian:** but they're simple and they're easy to approach and we'll help you really think differently about how you build your apps in a resilient and more cloud native.

[00:23:21] **Tim:** No offense guys, but this is the first time I've ever taken notes in our own show here. So I'm just writing

[00:23:25] **Ben:** Aye.

[00:23:26] **Brian:** up, ask you S

[00:23:28] **Tim:** Okay. Yeah. That's exactly what I wrote. You have.

[00:23:31] **Tim:** a camera in here? My room.

[00:23:33] **Brian:** yeah. You know, we're, so one of the things a project we're working right now is actually one of our last, really big data stores, which is about, only about seven and a half terabytes of data, is moving out of our data center into the cloud and we're rewriting the module and our learning management system that stores, most of that data and the developers are working on it are, this is their first real, like big, not like a simple Lambda function, or just working with S3 or queue that they pull messages off.

[00:23:57] **Brian:** This is like a full, complex workflow that combines, I think at this point it probably has about eight or nine different AWS services combined, making all of this stuff. and for them, even for them, they're like, okay, I gotta figure out what's the difference between SQS and SNS. And again, these are learning opportunities that really can transform the way you think about building applications.

[00:24:17] **Brian:** And for them it's been eyeopening and useful, and we've done a lot of talking back and forth about, well, what about this case? And what about, a lot about failures? Because if you're working with AWS, you gotta deal with failure stuff fails all the time. Right. Verna Vogels, the CTO. Sad and not these exact words, but basically everything fails all the time.

[00:24:33] **Brian:** And how do you deal with that? And the great thing about AWS is they do a lot to abstract away, some degree of failure for you, like with retries that are built into the SDKs, how magnificent and wonderful is that right. A call fails. And you don't have to worry about catching it right away because the SDK will retry it after, three or five or however many times you configure to do it.

[00:24:53] **Brian:** That's awesome. I don't have to worry. So talk about not worrying about things like, running servers or network infrastructure through some of these tools. You don't have to worry about things like retries and handling it. I mean, you have to figure it out sooner or later, things are to.

[00:25:04] **Brian:** Permanently at some point and you got to handle that. But, again, it's abstracting these things away and getting people to think differently about what they do. And I think that's really for me again, and I know I'm going to sound like a broken record with this, but I think it's one of the great powers of AWS.

[00:25:17] **Brian:** And one of the reasons why I really encourage all developers to think about how they might be able to use AWS or another cloud service, because it does make you a better developer, certainly a better architect, but certainly a better developer over time.

## [00:25:29] Cloud Services Comparison

[00:25:29] **Adam:** you kind of, gave me a nice little segue there. So the discussion so far has been very AWS heavy. And I know you said you guys use AWS, uh, Johns Hopkins. do you have any experience with any of the other Google cloud providers, Google, or Azure or anybody?

[00:25:42] **Brian:** a little bit with both Google and Azure, I haven't done Oracle, although I've heard actually good things about it. And, Alibaba, not at all. Even though we have lots of students, in our, in China,things we sit with AWS because I think it's where we are happiest. there's integrations has been with putting out in the CFML runtimes there.

[00:25:58] **Brian:** my issue is sometimes with, AWS has both its great strength and weaknesses, the number of services that are available, right. there's 270 some services now in AWS and it's crazy bonkers. Whereas Google has a lot less than that. and Azure has even less, fewer than that. I think the reason why I stick with AWS above all the others and I have dabbled some with Azure with like, Azure data services and cosmos database DB and with Google, with,their cloud run, environment to see sort of what that's like.

[00:26:25] **Brian:** with Google, it's always a question of, are they gonna.

[00:26:27] **Tim:** For sure.

[00:26:28] **Brian:** that's and I, and people joke about killed. I mean, there's a Twitter account killed by Google, right. but this is a serious issue, right? You're building something you're like, I don't want this service to suddenly disappear in two years because it was like, we don't want to do this anymore.

[00:26:40] **Brian:** We're getting out of this business and with Google and you never know. And I know they just announced some enterprise agreements to like, stick, you have things stick around longer. I still don't trust them. And Azure,people used to say are still some of them to say the cloud's not reliable.

[00:26:53] **Brian:** Stuff goes down. Will Azure goes down a whole lot more than either Google or AWS. AWS has had only two major outages in the last almost five years. One was an S3 outage and one was an outage related to Kenisa and streams. And that was an, a, it was one was a fat finger thing. And the other one was they tried to reboot too many instances at one time and didn't have resiliency there in terms of concurrency, in terms of the number of threads being spawned for the services as they rebooted it anyways, two major outage.

[00:27:23] **Brian:** In five years, Azure had like five outages last spring because of the pandemic and the sudden crush on Microsoft 365 services and teams and things like that. They just don't have the same scale and resiliency that AWS has. AWS

[00:27:40] **Tim:** Yeah, we got hit by that. Yeah. That

[00:27:42] **Brian:** And you could be a small shop. I mean, we only have, at any given time, we only have about 7,000 students who use our LMS.

[00:27:47] **Brian:** but I'll tell ya, even if I only had five students and one of them couldn't get on there, couldn't get access to their materials because AWS is down. It's like a huge crisis and everyone freaks out and it's not reliable. And why do we use these things? So, it, it does make a big difference for me.

[00:28:01] **Brian:** I understand, I think if I had started all over and I was a hundred percent, like let's say a net person, a window shop Azure makes a lot of sense because Microsoft and their traditional embrace and extend, sort of approach to things makes it really easy to work with Azure. if you're a end-to-end window shop and Microsoft shop, and I think there were some advantages there.

[00:28:19] **Brian:** I mean, I think it's kind of nice that cosmos DB can do a bunch of different things, not just, relation, it can be a relational store or an object store or key value stores. It's kind of interesting. but for me, AWS is where it's at, because there's always something new that I can play with and explore.

## [00:28:35] Deprecated Services

[00:28:35] **Tim:** We bring up deprecations, or just shutting things down. So just recently I got an email from ADA, but we have a lot of stuff in AWS, so anything we're all credit card and financial stuff. So we do host, we are hybrid as well, but it's actually is the, I can't afford PCI compliance in AWS. So we keep all the credit card stuff local, but anything else?

[00:28:57] **Tim:** And there's a lot that's not related directly to that is in AWS, but they recently sent him an email that says, Hey, we're shutting down. classic.

[00:29:06] **Ben:** that too.

[00:29:07] **Tim:** You got that email. And I'm like, I don't know if we're on it. They're like they said, we had an instance,

[00:29:13] **Tim:** but it

[00:29:13] **Brian:** which

[00:29:13] **Tim:** like org, but it was yeah.

[00:29:15] **Tim:** but which one?

[00:29:15] **Tim:** And it was in Oregon. I'm like, we always keep our stuff in north America, like Virginia what's.

[00:29:21] **Brian:** Yep.

[00:29:21] **Tim:** And so that is one fear I do have is like, sure. Today it seems like easy to VPC version is, that's where it's at. 10 years from now, it's like the thing about ATS is it's so magical. I never have to touch the stuff.

[00:29:34] **Tim:** And so my fear is like, what happens, five years from now, or 10 years from now, they're like, Hey, we're shutting down ECE to a VPC. and I'm like, oh crap. I'm 60 years old now. And

[00:29:47] **Brian:** Got to relearn

[00:29:48] **Tim:** I'm like, yeah, what do we do now, guys?

[00:29:50] **Brian:** it's a pretty unusual move on their part to be blonde. I mean, they just, this is not something they do on a regular basis and I think they're doing it because, they kind of feel that they have to for security purposes or for, some new service that they were using internally at AWS or some certification they need to get.

[00:30:06] **Brian:** Right. That's why they're doing it. And even what's happening is they're not really shutting down. Yes, they're shutting ECG classic down in the sense that you can't run an ECE two instance outside of a VPC or virtual private cloud anymore. but really what they're just going to do for those who don't take any direct action.

[00:30:20] **Brian:** My understanding is that they'll just put, you have a default PC in your account, virtual private cloud in your account. And they'll just eventually just move that ECQ instance into your default VPC. Now that may cause issues with networking and in ingress and egress and all those other good things.

[00:30:36] **Brian:** but you know, the instances aren't going away, they're just being migrated over into your own,personal, VPC. It's going to cause problems for people. And I think, we might even have some I'm like, why are we getting this notice? I don't think we have any in there, but we probably do.

[00:30:50] **Brian:** That's a great thing about AWS, right? The AWS bill is like, what is this 11 cents? I can never find that last 11 cents. Right? Cause it's some incense that somebody spun up

[00:30:58] **Tim:** I did find it and it was like some tea. It was like some old test container when we first started out and we ran it up just to, to test out Amazon and like, and we never use it for anything. It's not even, it's not even doing anything. So it's like, Okay. just, I finally found it and killed

[00:31:12] **Brian:** but that's gotta be somebody's job. somebody has to go through and look at all your resources and be like, why is this here? I did that like two weeks ago with my team. And, I shut off about $50 worth of stuff that we're getting charged for every month, 50 bucks, which is, 600 bucks a year, not a huge amount of money, but it's not in substantial $600 savings as a $600 savings right.

[00:31:31] **Brian:** A year. and it was because people had done test stuff and were trying things out and they just left it running and I'm like, no, kill your _(quack)_. That's what you're supposed to do. Kill it. Take it down. Yes.

[00:31:43] **Ben:** just turned something off to see what would break.

[00:31:45] **Brian:** no, I'm not, I don't live that

[00:31:48] **Tim:** Oh, I have,

[00:31:49] **Brian:** it's a great idea. And you should, like, everyone says, oh, you should do it. Right. chaos engineering. You want it to have fault injections. You want to do all this stuff that will break your stuff and to make sure it's super resilient. I don't wanna mess my stuff up.

[00:31:59] **Brian:** I'm still too much in the mindset. It's like cattle. I mean, Pat's not cattle, right? I'm still like, no, but I know what this does and I don't want to

[00:32:06] **Adam:** There are very few things that we don't turn off because we're a little bit worried that they're not going to come back up clean and then we're hosed for weeks or whatever, while we get that sorted.

[00:32:15] **Brian:** Absolutely. Absolutely. We do the same, like we do. we're doing more and more with like Kinesis and Kinesis, firehose and writing, data, temporary data, log data analytics, data to S3 using Kinesis firehose, which is a service that basically lets you just take like Jason objects and just keep pumping them as fast as you can into this Kinesis firehose stream.

[00:32:36] **Brian:** And then it writes it, transforms it and writes it into text files of varying size in an S3 simple storage service. It's super useful. It's great for long-term storage of data that. And sometimes do fun things like sit in a relational database when it really doesn't need to be there after a long period of time, we've all put logging data in relational databases, say it don't say you haven't, or auditing data, or we have, there are requirements that we have around students and how long we have to keep their data.

[00:33:00] **Brian:** it has to be, eight years in some places, 10 years and others. And we're past that point. We're like, let's get rid of this old data, but people still will, someday somebody will be like, oh, you know, that student was in my class in 2008. I need to know if blah, blah, blah. I'm like, okay, we just keep pumping that sort of old data after those points, through these Kinesis firehose streams into S3 where it's super cheap to store.

[00:33:19] **Brian:** and then if we really need it, there's this really awesome service called Athena, in Amazon that let you query text files, right? A query data stored in text files, which sounds kind of crazy, but it's amazing and powerful and a great way of storing all your data. It really in a sort of long-term way, inside of AWS, when you really don't need it inside your relational databases,

[00:33:39] **Ben:** How does something like, so, going from one extreme where I make a request to a server and an immediately response to something like Athena, which I assume is go query this like terabytes worth of object store. Does that just do they just say, all right, we'll just email you when this is done, because to sit here and stand.

[00:33:59] **Adam:** Okay.

[00:33:59] **Brian:** So there's a kind of briefly explain there's this sort of pattern that you see in a lot of AWS stuff, where it's not an immediate request response where it's an asynchronous call. Cause most of their stuff is asynchronous. and this is the case. If you ever use step functions, which is a, sort of workflow execution environment, that's super powerful that lets you tie together a whole bunch of AWS services.

[00:34:17] **Brian:** and I've talked about it and you can dive videos about it on YouTube and stuff anyways. so basically in those kinds of situations where you might have to scan terabytes worth of data, query that, you make a request and Amazon says, cool, Here's an ID, here's a token, right? We're going to put it into our internal queue and it'll run.

[00:34:33] **Brian:** And it usually runs pretty quickly. But if you're scanning five terabytes of data, it's not going to be instantaneous. Obviously just check back later and see if this job is done and you make another request saying, Hey, here's my token. Is this job done or not? Yes or no. And if it is, then it says, here's, with that rate yes.

[00:34:49] **Brian:** Response, you can say, okay, cool. Now give me the results from that. and that's the case, how, at the end it works and step functions, work, and another number of other services as well. So it's a, it's not request response. It's a little more involved than that, but it allows you to do crazy stuff like, run a select star on five terabytes worth of data and not worrying about, bringing the whole system down.

[00:35:09] **Ben:** Does it have

[00:35:10] **Brian:** Not that you would ever do that. I would never recommend select star for any reason, but

[00:35:14] **Ben:** does

[00:35:15] **Brian:** you can do it

[00:35:15] **Ben:** all of the objects that Craig queried in an Athena query, do they have to have a similar structure? Like how does,

[00:35:22] **Brian:** they do so it doesn't do, it's not fun. Things like joins. I mean you can kind of set up multiple tables in there. Craig started virtual tables, so it uses another tool called glue AWS glue, which is a sort of catch all crawler data engine thing, a schema, it's a schema generator really. And you say, okay, this, these objects are all going to have a user ID and email, column name, column type to just like a normal table would, and then it queries that, or it's crawls that it scans it and make sure that all the stuff is there.

[00:35:50] **Brian:** And if it doesn't exist, then it's gonna throw an error,

[00:35:52] **Brian:** right. Uh, for you. But that's pretty much what it does. is it sort of doing real time, sort of schemes, translation and, putting it all into memory somehow, I don't know what these huge memory things are that they have there inside of AWS. not just, gigabytes, but terabytes of data for these things, puts it into memory and then, winds up doing the querying on it.

[00:36:09] **Brian:** it's pretty remarkable. And again, All abstracted away. You don't have to worry about a thing.

[00:36:15] **Adam:** Yeah.

[00:36:15] **Brian:** It's like magic. It is you're right. Bed. And it's like magic. Yeah,

## [00:36:19] AWS Documentation Problems

[00:36:19] **Tim:** I'll tell you my biggest beef. All right. Let me just give let's lay down here.

[00:36:23] **Brian:** I got

[00:36:23] **Tim:** my biggest beef with them. You got BS. So their documentation, they got a lot of it, Right. But it's like, it is, they change. They change the screens. They change so much so fast that by time the doggy, you get this documentation, it doesn't match.

[00:36:38] **Tim:** You're following a simple tutorial. Right? It's even their stuff is not someone else's blog and you're following it along. And it's like, all right, look for this and do this. And it's like, it's not.

[00:36:48] **Brian:** Right.

[00:36:49] **Tim:** It's completely different and that it's not like, I've done it. I do this all the time. And I was like, why can we not sync this up?

[00:36:57] **Tim:** Can you not update your documentation at the same time you change all your damn screens.

[00:37:00] **Brian:** or just provide simple, clear examples of how to do things. I mean, I get it, their documentation is thorough. Right. for every function call, you get all the sort of, the properties that go in it, or, all the methods that are part of a service, or if they, like you can do, it'd be the ape, the SDK or the CLI or cloud formation, but, or sometimes in cloud formation.

[00:37:20] **Brian:** but there's just too much. And it, and I think that's, AWS's biggest problem right now is too much right. Service differentiation. What is the difference between ECS, EKS and far gate, right. What's the big difference between the three of those and yes, I'm sure, Adam, you probably know the difference between the three of them very well.

[00:37:37] **Brian:** but you know, explaining that to somebody who's getting started with this, or even someone who's relatively familiar with AWS who wants to move into container-based services, that's really hard and they keep adding, can you explain the difference between like the 17 different. What's there. They're a big machine learning thing.

[00:37:52] **Brian:** SageMaker right. SageMaker studio versus SageMaker pipeline versus SageMaker whatever. I mean, just go Google, AWS SageMaker and there's literally 17 different services or 20 different services there. and it's w what are these all for? So service differentiation is a problem. There's too much documentation.

[00:38:08] **Brian:** There's too many options. It's difficult to figure out what you're supposed to do. And I've had the same experience to him just trying to get started. And following people's blog posts that seemed clear and well-written, but things have changed, and those options are no longer supportive to the screens.

[00:38:21] **Brian:** If you're using the console, you can't follow along in those same ways. and that's a challenge, but if they really want to make developers happy, which they say they want to do, and they're customer obsessed, then coming up with simple, clear examples for the documentation. For all aspects of it is super important because otherwise we can't do the things that we want to do.

[00:38:39] **Brian:** it shouldn't take us a day to figure out how to hook up, an SQS queue to a Kinesis stream. It shouldn't take a full day to do that. It shouldn't anyways. I mean, it's not that hard, but, so the uninitiated it easily could because there's so many options and so many different knobs

[00:38:52] **Adam:** And you have to learn a whole language.

[00:38:53] **Brian:** but frustrating.

[00:38:54] **Brian:** Yeah. Yeah. It is. AWS has its own language. I mean, cloud formation is its own language really at the end of the day. Right? it's I mean, it's a DSL, but it's in a very real sense its own language and to the outsider, looking in it's super frustrating and really daunting.

[00:39:09] **Tim:** I kind of wish we had Carol. I mean, I know we're you, we invited you on because Carol is out this week, but,

[00:39:14] **Brian:** I'm your second

[00:39:15] **Tim:** but.

[00:39:15] **Brian:** then

[00:39:16] **Tim:** Well, I mean, she's,she's the original beetle. You're Pete best, but anyway,

[00:39:20] **Brian:** that works for me.

[00:39:22] **Tim:** but yeah, I mean, she had some issues with AWS and doing some stuff. She definitely would be picking your brain right

[00:39:27] **Brian:** Yeah. It's yeah, it can be super frustrating days lost to just trying to figure out how to make things, talk to each other or heaven forbid figuring out the IAM permissions, identity, access management permissions for things that's like, I get, I understand now why that's why there are companies where they have like a whole group whose only job is to work in.

[00:39:45] **Brian:** I am an, I am permissions because it is

[00:39:48] **Tim:** yeah. It's like, it's like black magic.

[00:39:49] **Brian:** is like, it is black magic. It

[00:39:51] **Tim:** yeah. Colin star, whatever. Just we're good.

[00:39:53] **Brian:** all the resources, all the people, all

[00:39:56] **Adam:** that is why you can't be PCI

[00:39:58] **Brian:** do that.

[00:40:00] **Tim:** Right.

## [00:40:03] Building In The AWS Console

[00:40:03] **Ben:** Well, one thing that, that when you talk about having to learn a different language, to make sure that everything talks effectively to each other, I think that's also one of the big cognitive steps is that when I'm developing application code and it's all right there in the application, I make a tweak and I deploy it and it just works.

[00:40:22] **Ben:** Like I didn't have to do anything else when I then start to consume Amazon services and then have Amazon services talk to each other and emit events and consume events. It's like, as a new person, I don't even know. Do I do that programmatically? is it quote, unquote, wrong to like actually just log into the console and manually set up a bunch of stuff and like provision tokens, and then put them into my application.

[00:40:45] **Ben:** Like that feels so dirty. Cause it doesn't feel reproducible. so like,

[00:40:49] **Brian:** but it works right. It works. It gets the things done in your app. And I think that's, again, one of the real challenges that AWS has, because Ben, I totally feel your pain. I mean, again, the sort of, the migrant, the big project we're working on right now, or one of the projects we're working on right now, again, the sort of workflows and the architecture diagrams for these things are huge with, like 50 or 60 icons. Yeah, on, on the screen for this one service, right? and people talk about this and experts who work in particularly the server hosts area and AWS will say, look, yeah, it looks daunting. It looks complicated. But you know, this, all this complexity was being hidden by your local app, your runtime, whether it was.net or ColdFusion or whatever it was, that was all hiding that from you.

[00:41:29] **Brian:** Right. You just have to deal with it in this very kind of like decentralized, fragmented kind of way. But the advantage in the long run, because you have things that are super resilient. And if you want to swap something out or add a new piece of code or functionality or an entirely new workflow, you just do it.

[00:41:46] **Brian:** You say, Oop, insert here. And it just does it, right. Or you could say, I'm going to subscribe now to this SNS topic. So instead of like three different services or three, three different functions going to listen to this SNS topic and execute code based on the data that comes in, I can add a fourth, I can drop one out.

[00:42:01] **Brian:** I can do whatever I want. The other things don't know. The other things don't care. And like Tim was saying, it makes for a really clean working environment in the long run to make sure that things are truly isolated, truly separate. And you're really thinking about resiliency as well as failure paths, as well as the happy path there. So it's just a different way of thinking. and I get it. I mean, we use cloud formation for some of our stuff, but not for everything. And a lot of times it's, in our dev account we build in the console and then we figure out how to make a nice cloud formation template out of it.

[00:42:32] **Brian:** And then we put that into production and even then sometimes it's like, it's just easier to, make changes in the console, which isn't always good. But again, you're like, I don't want to break stuff. I don't want to blow everything up and production and the console lets me

[00:42:44] **Adam:** You mentioned earlier, like the cattle versus pets thing. I like to think of those as like cattle, but we give them names, right? Like this is Betsy.

[00:42:51] **Brian:** exactly. Exactly.

[00:42:53] **Tim:** Betsy, all right. Well, you want to get into a user, patron questions.

## [00:42:57] Dangers and Benefits of Cloud Lock-In

[00:42:57] **Adam:** So, Brian asked, what are the dangers or benefits of quote unquote cloud lock-in. And do you think they're overblown? Is it maybe just a case of trading one set of problems for another

[00:43:08] **Brian:** Yes. Yes. And yes. yeah, so, vendor lock-in is always sort of the thing it's like, oh, I can't just use AWS. I've got to use AWS and Azure GCP because I don't want to be locked into one. No, now you have three sets of problems instead of one, seriously. the whole multi-cloud thing, the, the people that I listened to they're like just don't do it.

[00:43:25] **Brian:** It's a nightmare. And the more I've looked at it, I'm like, I wouldn't want to do that either as Tim was saying, it's hard enough to keep just what's an AWS. Now you're trying to keep, what's an AWS in your head and what's in Google in your head and what's an Azure in your head and they all do things differently.

[00:43:39] **Brian:** is there a, lock-in sure on a certain degree, but there's, lock-in when you choose to write in Python, when you choose to write a node, when you choose to use MySQL versus SQL server or heaven forbid, Oracle,there's,

[00:43:51] **Tim:** PostgreSQL.

[00:43:51] **Brian:** right. there's always a certain degree of lock-in there, right?

[00:43:54] **Brian:** I mean, how many people have actually moved, their databases. From, from MySQL to Postgres or Oracle to Postgres or whatever, Tim's raising his hand. He's saying to me it's not really common because it's really super difficult to do. And there's a of cost fallacy there, but there's also, it's like, no, this is not our, what we should be doing.

[00:44:12] **Brian:** There's not, unless there's an extraordinarily good reason to switch from one to the other, which there rarely is. I don't think it's not worth it. And for me, I'm like, look, yes, I'm not in a business where I have to worry about AWS being a competitor to me, I get why Walmart was like, okay, we need to get off AWS and move elsewhere.

[00:44:28] **Brian:** And our vendors should not be on AWS as well, because we don't want them looking at our traffic and our access patterns because AWS does that. They're really up front. They're like, Hey, look. We develop new services based on the traffic and access patterns and questions that our current customers ask us.

[00:44:42] **Brian:** So if we see lots of people doing, ML analysis on, customer interactions or purchases, then we're going to build a service around that to help abstract some of that for people. And we're going to use it ourselves. I mean, remember that pretty much everything that Amazon builds into AWS is a service that they use themselves or have used themselves first, whether it's look at it.

[00:45:03] **Brian:** For vision, whatever that is, that's the, it's a machine learning service to help find defects in products that are created in a factory. Right. I'm like, well, why does AWS do that? Well, think about the number of products that AWS actually makes themselves that they sell on. Right. it's Amazon selling products on Amazon.

[00:45:21] **Brian:** So they're doing that. They have the service and they're going to sell it to other industrial customers who build products. And they can like have a machine learning algorithm that sort of looks at the pictures and like, ah, there's a defect and that one pull it off the line. Right? So they, this is what they do.

[00:45:33] **Brian:** they eat their own dog food every single day of the year, which is not, can't always be said about Google. And can't always be said about Azure and the products and services that they provide, although Microsoft does a lot more dogfooding than Google does. so, I don't know I'm getting off topic there.

[00:45:47] **Brian:** Sorry. but lock-in no, I wouldn't worry about it too much. AWS is not going anywhere. Azure is not going anywhere. I wish I could say that Google cloud is not going anywhere, but, if it doesn't become prof profitable in a couple of years, I wouldn't be surprised if they say you have a 90 day time or 12 month timeline to get off Google cloud.

[00:46:05] **Brian:** Um, seriously,

[00:46:07] **Tim:** Yeah.I agree, totally agree with you bro. Because I mean, the things, like I said, we use a lot of AWS and the reason we continue to stay with it is because one, I mean, if you look at AWS is our Amazon's budget. Most of their money comes from AWS. I mean, amazon.com and all that it's they make some money, but not nearly as much, everything is funded by AWS.

[00:46:29] **Tim:** Right. So that's driving their profit. So they're going

[00:46:31] **Tim:** to

[00:46:31] **Adam:** pretty sure

[00:46:32] **Tim:** it. It's continually

[00:46:33] **Adam:** Bezos just use the profits from Amazon and AWS to take a four minute vacation in outer space. Yeah.

[00:46:39] **Tim:** yeah.

[00:46:39] **Tim:** But you know what? That's a drop, that's a drop in the bucket. It's a total drop in the bucket and they're going to, I just feel they're going to be around right there. they have a foothold in it and that's their money maker. So if they're making money off of it, they're going to keep it around.

[00:46:53] **Tim:** So if it's going to die, it's going to, because like some great new thing comes out of The blue and that hasn't happened yet. So don't worry. Don't premature

[00:47:01] **Adam:** thing that I worry about is all the other competitors dying off and then Amazon going, oh, we have a monopoly. Our price has just tripled.

[00:47:09] **Brian:** Yeah.

[00:47:10] **Tim:** Well, it kind of did have a monopoly for a good while. I mean, Azure, wasn't a thing for a while, Google. I mean, they're all pretty

[00:47:15] **Tim:** new compared to them,

[00:47:16] **Ben:** one thing that, prion early, you had talked about undifferentiated, heavy lifting, and I think part of the benefit of buying into a vendor whole hog is that you get to outsource some of the nitty gritty stuff that you would have had to deal with. Like earlier you had mentioned step functions and I don't exactly know what step functions are, but I assume if you weren't using step functions, you would have to do something.

[00:47:39] **Ben:** Cute choreography where you're taking like messages off of one cue and then putting them onto a next queue. But like that doesn't like, you're not in the business of building queue management. Right? So like, why build that when you could be concentrating on product development

[00:47:53] **Brian:** Absolutely.

[00:47:54] **Tim:** functions. There are functions that you love less than the functions you wrote.

[00:47:58] **Tim:** Step

[00:47:58] **Brian:** But right now, it is, it's one of the real benefits when you're using it. When you buy into AWS or GCP or Azure, use everything seriously use everything because that's where the real power lies tapping into not just one service, but services tapping into Abila services. And of course, AWS and GCP and Azure, happy to take all your money, right?

[00:48:16] **Brian:** Because these services cost money at the end of the day, but it gives you a set of options that you wouldn't otherwise have. And it just easier to write stuff.

[00:48:23] **Brian:** I mean, I, like I said earlier, we can't put our core compute instances in AWS, even though we have a situ instances, we have lots of compute running inside of AWS because of reasons from Hopkins. but, if we could do so much more, right. It would be even more freeing and liberating for us because there's a lot more that we could do that way.

[00:48:39] **Brian:** and I wish we could do that, so I don't worry. It isn't let lock. It doesn't keep me up at night and in cost increases, don't keep me up at night, Microsoft's not going to anywhere. So at the very least there's going to be Azure and AWS and probably Oracle and certainly Alibaba as well.

[00:48:52] **Brian:** Alibaba is not very well known here in the west, but they're huge, in an APAC region. And, they're not going anywhere either. So I think we're going to

[00:49:01] **Tim:** but you can't host any picture of Winnie

[00:49:02] **Brian:** No, you cannot. You

[00:49:05] **Adam:** Oh,

[00:49:06] **Brian:** is

[00:49:06] **Tim:** cause GP we'll shut it down.

[00:49:10] **Adam:** how do we move on from that?

[00:49:11] **Tim:** Sorry. I'm the disruptor in

[00:49:13] **Brian:** it's a perfectly legit question, right?

[00:49:15] **Brian:** It's a perfectly,if you have customers in China, you got to think about that stuff and who's going to see your data and,who will have control over

[00:49:21] **Adam:** Yeah. Censorship. Yep.

## [00:49:24] Fixing vs Starting Over

[00:49:24] **Adam:** So definitely not speaking from personal experience if, when you were new to the cloud. Yeah.

[00:49:33] **Adam:** For a

[00:49:34] **Adam:** friend of

[00:49:34] **Adam:** mine, if, if, when my friend was new to AWS, they set up a VPC and maybe didn't do the best job, locking it down and configuring everything to be secure and happy and, done well and done.

[00:49:48] **Adam:** Right. Would my friend be better off, starting from scratch with, what they've learned since then? Or should they try and fix the mess that they've made for themselves?

[00:50:01] **Brian:** That is an excellent question. and I feel for your friend, because, I'm doing this right now with, organism and control tower, which are two tools that lets you sort of define your accounts and put guardrails and centralized billing and all sorts of fun, things like that. Because like with many people I started out and I was like, oh yeah, AWS, cool, here's this one account.

[00:50:21] **Brian:** And when you do everything in this one account, terrible idea, like we've learned over the years and AWS has all the time, don't do it. It's a terrible idea. Meaning you'd have different accounts for different things and it can build that out. But managing five accounts, isn't so bad managing 25 accounts is _(quack)_ and managing 125 accounts is even worse.

[00:50:36] **Brian:** So, yeah, so I'm sort of in the same sort of boat right now. We're thinking about redoing that and, but migrating is never easy. Right. Migrating is never easy. And I think like with all things compute, there are trade offs to what you want and need to do. So I would ask the question to have your friend, are there significant and serious threats to, with the current configuration of your VPC?

[00:50:57] **Brian:** And if there are then yes, it's absolutely worth it to do it,

[00:51:01] **Adam:** To do which

[00:51:02] **Brian:** start with something fresh rebuild, do it the right way that time. Cause you've got to migrate all your easy two instances in there, move your elastic network, interfaces, all that stuff. and maybe that's not a terrible thing. Maybe it's, again, pretty straightforward and less of a, not don't look at too much downtime or anything like that.

[00:51:18] **Brian:** but if there aren't significant threats to the security of the data and the instances that are in there, it's the question of is that really worth your time is the hundred and 50 hours, 200 hours, whatever it's gonna take you to do this. And again, moving everything into a new VPC is not trivial at

[00:51:35] **Brian:** all.Um, is it.

[00:51:36] **Adam:** keeping everything running

[00:51:37] **Brian:** could you be doing with that time? Otherwise? So I wish I could have said yes, absolutely do it, but, no, I it's that for me, like, and the same thing with organizations, for me, it's been a long time and I've gotten to the point. Now we have enough people and enough accounts and I'm like, I need to do something better.

[00:51:51] **Brian:** because right now it's all in my head largely. Right. And that's a terrible place for stuff to be. I try to document some of this, but you know, you're talking about secrets and account management and, it's a bad place for all that stuff to live is in somebody's head. So I'm like, Nope, I need to finally bite the bullet and do it.

[00:52:06] **Brian:** even though it's going to take time and effort, and there's gonna be potential disruptions as a result, because in the long run, I'm not going to be in my job forever. I better not be, so it's good for me to do that. And before it gets even crazier and more difficult to

[00:52:17] **Adam:** Okay. will pass that information onto my friend. Thank you.

[00:52:20] **Brian:** please do.

[00:52:23] **Tim:** He'll be glad to hear it.

## [00:52:24] Certifications

[00:52:24] **Adam:** this was just a personal question from me and I know I haven't heard a whole lot about their certifications more recently, but, I know that they, at least at one point did offer certifications. You could become like a. ECE two certified or AWS certified that you knew all their stuff. Is that really worth getting, does it do anything beyond getting you past HR or,

[00:52:48] **Brian:** Depends on who you work for. Right. so there's a really good blog post. If you aren't familiar with Corey Quinn and his company, the doc bell group, they do, screaming in the cloud as this podcast last week. And AWS has his weekly newsletter or bi-weekly newsletter. It's awesome. bi-weekly or semi weekly.

[00:53:01] **Brian:** Cause it comes out twice a week. they did a blog post about certifications that I think is really great. And you should, everyone should take a look at it, because it gets it very much mirrors what I feel about it, which is. If your job is going to reward you for it, like you work for the federal government, you work for a large organizational corporation that rewards certifications do it right.

[00:53:21] **Brian:** Do it because it's going to be more money for you, in your weekly paycheck. So. Otherwise it in the rest of the tech world, it doesn't matter a whole lot. if you like getting into the private certification lounge at re-invent, then you need to do it right. It's important to some people having that private lounge and the good snacks they have in there.

[00:53:40] **Brian:** And that, you can eat Jeff bar and other mucky mucks at, AWS in the certification lounge. but beyond that, it doesn't offer a lot of real benefits. from my understand people that I talked to who work in AWS as well outside of my job and where I work, it doesn't make it by that much of a difference in hiring.

[00:53:56] **Brian:** If you don't have a big resume, if you can't say here's a project that I worked on and we use these services and we did all this in AWS and talk for a long time about that project in depth, in detail, a real-world project, then certification can help you sort of get your foot in the door with companies that are looking to hire, folks with AWS experience.

[00:54:11] **Brian:** but beyond those circumstances, it's not, I don't think it's that valuable. And maybe it's because I've never taken the exams, but I also feel like. don't need to write, cause I'm going to learn on my own. I'm going to develop this, that level of expertise on my own and I can take it through my workplace and to my colleagues.

[00:54:26] **Brian:** And I think that's, what's

[00:54:28] **Adam:** Yeah. I mean, to the previous point about the documentation going out of date almost before it goes, gets published. I was kind of wondering like, is that sort of the same thing with the certification? Right? Does the information change so fast that the certification is outdated when you get it?

[00:54:42] **Brian:** Well, the certification tests you on things that are more established, right? And it's not, you're not going to be certified on Lambda. You're not gonna be certified on step functions, although I'm sure they're developing a serverless architect certification, but even then most of those questions are going to be thinking about things like SQS and SNS that have been around for a long time or the basics of the functions.

[00:54:58] **Brian:** I mean, I guess you also, I mean, I've done some practice exams with AWS certifications. It's I'm like, well, maybe I'll do it. And sometimes they deal with real minutiae, real minutia of VPCs of easy two instances of billing of CloudWatch metrics and alarms. And it's like, I don't need to be tested on that.

[00:55:16] **Brian:** Right. That's not how I should be

[00:55:17] **Adam:** I can Google that.

[00:55:18] **Brian:** I want to build crap. Right. I can Google that. I can Google that if I really need to know. I mean, some of these are gotchas and there's a lot of little gotchas with AWS around service limits and retries and things like that. So you should be aware of it, but that's stuff you learn as you develop with the services themselves.

## [00:55:35] Finding AWS Expertise

[00:55:35] **Tim:** so let me ask you, you talked about hiring. So we are in the process of trying to hire someone to manage our AWS stuff. what are, as a person who hires other people that might be doing this? Give me a couple of golden questions, Right. A little nuggets here to drop on them, to figure out, if they know

[00:55:51] **Brian:** Right. So I think the best question to ask that I always like to ask is, tell me about a project that you were in charge of or a lead on. And what did you have to do? How did you implement it? What were some of the challenges and what would you do differently next time? And just let them go with that and ask followup questions based on those things.

[00:56:06] **Brian:** because you'll know pretty quickly, if you have any sort of familiarity. Reno, relatively passing familiarity with AWS and building a couple of small projects, whether or not they know what they're talking about, whether or not it was a sort of a real project, the level of complexity, the challenges they encountered was it, oh, we had to move all of our files and our image database up to S3.

[00:56:24] **Brian:** Well, cool. So what else did you do with it, right? it was it, I just literally FTP, a terabyte worth of files up there, or was it that you actually had to build a service and what did you about IAM permissions? And did you do anything with like, storage classes or AWS batch for processing those images?

[00:56:39] **Brian:** I mean, there's lots of opportunities for you to sort of ask sort of follow up questions in there to see really what was the depth of their experience. so I think by having them describe that project and what worked and what did, and in particular with the challenges where you really learn a lot about somebody's skill and experience with AWS, that can't be, sort of, faked by just dropping buzzwords,

[00:56:57] **Tim:** right.

[00:56:59] **Brian:** We did a, oh yeah.

[00:57:00] **Brian:** We had a SageMaker service that ran on elastic container service that talk to AWS batch and then did, four different

[00:57:07] **Brian:** sizes for each image. Okay.

[00:57:09] **Tim:** five,route 53 and

[00:57:11] **Brian:** Just drop more service names in there, but you could ask easily ask a follow-up question about any one of those and say, well, what was it like working with EKS?

[00:57:19] **Brian:** I mean, what were some of the challenges with EKS and running pods and stuff, being tasks, being killed and stuff. And if they can't come up with even like a good explanation of that, it's pretty clear that they don't really know what they're talking about.

## [00:57:29] Over-Application of Services

[00:57:29] **Ben:** along the lines of the complexity of Amazon web services and getting things to talk to each other, are there, I don't want to call it anti-patterns I, I think we've probably all had moments in our career where we read a book on programming patterns and then we over apply those patterns in our next, few months of work.

[00:57:48] **Ben:** do you ever see people like use dynamo DB when RDS like would have been overly sufficient and like, why go through the complexity of some totally new database model? Like, do you see things like where people just kind of go off the deep end because they're excited.

[00:58:04] **Brian:** Yeah. Yeah, absolutely. I think, it's really easy to do that, that, like with all things, and all you have is a hammer. It looks like a nail. Right. and AWS provides you with lots of different hammers and I've been certainly,guilty of this myself on more than one occasion.

[00:58:17] **Brian:** I'm like, oh yeah, SQS is the best thing ever. And we're gonna use it for all of our things and oh yeah. Well, it doesn't really work for this, but we're going to make it work because no, right. I can't use SQS for all of my asynchronous messaging. There's lots of other tools for that. Right. SNS has a very different set of requirements or different set of use cases, but that are overlapping.

[00:58:34] **Brian:** In some cases, sometimes a event bridge is something that I'm learning now and sort of getting involved in. it's easy to over apply a single service. I mean, just like you, just like a pattern, like you're saying there, bandits, I think it's very common for you to be comfortable with the service and then over apply that, in many different scenarios and dynamo, DB is awesome.

[00:58:50] **Brian:** Don't make it wrong. Dynamo is awesome. it's not awesome at everything, right? It's not good at,aggregations. It's not good if you don't know your access patterns, like it's awesome. If like here's the day that's going to come in and here's how it's going to come in. And here's what I need to query.

[00:59:02] **Brian:** And I'll never need to change that. Dynamo is totally awesome and people get bit all the time trying to do joints, right? In particular. They're like I come from a relational doc background. I'll just use dynamo DB and I'll have my user's table and my store table and my products table. And that's where all goes to hell in a hand basket really fast.

[00:59:20] **Brian:** it's just, it's learning to think in a different way, but then also, in the cloud native way, but then also not using one service for everything you might need to do. Although S3 is probably that service.

[00:59:34] **Ben:** well, do

[00:59:34] **Adam:** you

[00:59:34] **Adam:** heard it here.

## [00:59:36] Migrating Old Functionality vs Implementing New

[00:59:36] **Ben:** even just earlier, when we were talking about, Adam's friend with the VPC issue, do you, if I'm like, let's say I'm buying in, I'm excited. I want to try some Amazon web services stuff. Should I try to refactor an existing piece of functionality or do you think it'd be best to, I have something new I want to build, maybe it's part of an existing application, but a new feature and like, let me use the new feature as a way to experiment or I dunno.

[01:00:04] **Ben:** I dunno what the better move is.

[01:00:06] **Brian:** I don't know either, I'll give you the typical Hopkins answer. It depends. that's a typical answer. We give everyone for everything at Johns Hopkins. It depends. on the one hand, if it's a new feature then yeah, absolutely. It's Greenfield. You have all sorts of options and ideas. You can explore to see how things go if they work well.

[01:00:20] **Brian:** Or if they don't something that's known is much easier because you know, the business logic, you know, the rules, you don't have to figure them out as you go along and you can figure out, can I replicate this in the cloud? Or how does this need to be. In the cloud. and I talk a lot about serverless and I, haven't only, I've only mentioned that word, like once in this whole podcast so far, that's kind of shocking to me.

[01:00:39] **Brian:** cause I talk about it all the dang time. eh, that's a great way to get started, right? Is take a piece of functionality, put in a Lambda function, hook it up to an SQS queue or S3 or whatever else are there services, you might need to do this and you build a cloud-based function that requires no management, no cattle, no pets.

[01:00:56] **Brian:** It gets invoked as you need it. and it's wonderful. and for me, I think that's been for my team and myself, the easiest thing to do, like say, okay, By and large, we want to do things that are kind of similar to what we've done in the past, or there's really clearly defined business logic around this.

[01:01:11] **Brian:** one of our, I'll say one of our first big projects that we did in AWS in a purely serverless way was a video transcoding translating transcribing service. And we weren't doing that locally because we didn't have the compute or know how to do it, but we did it all serverless fully in AWS. And that was totally new functionality for us.

[01:01:28] **Brian:** And we use it every day and it cost us a good chunk of money because we use it super heavily for the work that we do. but it's totally worth it because I don't worry. I don't have to build a translation service. I don't have to build a transcription service. I don't have to build a video, transcoding service, all that stuff is there and I can piece it together and I did.

[01:01:44] **Brian:** And that was great. And that was all new functionality. The stuff that we're talking, I was talking about now, the project that we're currently working on, we have all the business logic. We have to figure out how to map that to AWS. And that's its own special challenge, right? Because we're building all these sort of flows and workflows and paths, and lots of little pieces of functionality that were, a series of, ColdFusion components and functions and ColdFusion components before.

[01:02:06] **Brian:** and that's good too, because it allows my team to say, ah, I know how this is supposed to work. How do I make this work inside of AWS? And they learn that way because there's less to figure out. I'm not figuring out all the business logic I'm node, the business logic. I just got to figure out the component pieces and how they fit together, the component services and how they fit together.

[01:02:24] **Brian:** So again, I think it depends there. though I would probably lean towards the, take something existing, figure out how to replicate it in the cloud, because that way you don't have to worry about the business logic side of things.

[01:02:34] **Ben:** That makes sense. Plus, if you, I mean, this is not a great example, but you can always send to both, almost like send to the old and to the new, and then once you're confident that the new results match the old results, you can start moving more traffic

[01:02:50] **Ben:** over.

[01:02:51] **Brian:** right.

[01:02:52] **Brian:** With feature

[01:02:53] **Brian:** flags.that's the strangler pattern at work right there. Right. You slowly strangled the amount of work that's going to be. Oh, it's the old service and push

[01:02:59] **Ben:** W

[01:02:59] **Brian:** And it's safe. It's safe. If something blows up, you still have the data in the old service.

## [01:03:04] Lambda Function Responsibilities

[01:03:04] **Ben:** One thing that I struggle with wrapping my head around. And it's because I don't really have a lot of experience with any of this stuff. We have teams at work who are much more forward-facing when it comes to the new technology. But, one thing that I'm always wondering about with Amazon Lambda is how dumb a function should be.

[01:03:22] **Ben:** Meaning, for example, let's say you have a Lambda function that pulls a file down from S3, does something to it, and then pushes it up somewhere, like almost in an ideal world. That Lambda function shouldn't even know where it's pulling from or where it's pushing from like part of the message that it receives should have, like, here's the S3 URL that you're pulling from.

[01:03:45] **Ben:** And here's the S3 URL that you're putting to. And like, you could run like a whole bunch of different services can now use you to do this thing. But I assume that then adds another level of complexity that now you have to pass data to that. And I dunno, like, what's your strategy? Like how closely coupled, I don't even know what the right terminology, like how tightly coupled should the Lambda function be to its contextual usage versus like how completely pure functioning should it be or.

[01:04:16] **Brian:** that's a great question. And I tend to err on the side of cohesion for the task, more than anything else, I don't believe in giant Lambda functions that do like, 17 different things based on the parameters that are passed into them. And I understand why people do that. because they haven't learned about step functions and haven't learned about, the fact that you can do like

[01:04:35] **Brian:** branching and workflows and there, it leave that to step functions, leave that to an external service or environment or another sort of controller function, although that's a bad idea.

[01:04:43] **Brian:** so I mean, in the example that you gave, where it's like pull a file, do some manipulation, put it back. I keep that. I think by and large, most of the time, I would say put that all in one function, unless that manipulation or transformation is really complicated. And in that case, you'll want to say, Well, it can also depends on the runtime because, if you are, you can't really use you can't pass file instances, like say across step function, steps in a step function workflow, which a lot of times what we use for orchestration, because it's really, I think the best available of the available options in AWS, or even if you have Lambda functions that are chained to one another, either by direct invocation, which is a terrible idea, don't ever do it or through destinations.

[01:05:20] **Brian:** so on success from one Lambda function, you'll invoke another function, which is perfectly fine and good. You can do that or talk to event bridge, send a message to event bridge, and they'll get picked up by another Lambda function. you still can't fi pass file instances in there. So at the end of the day, But again, this is kind of specific to files.

[01:05:35] **Brian:** you have to pull it into that function. You're going to have to read it back into that function, kind of, no matter what, and maybe that's a better option for a shared library than,a separate function. That's where you used again. and again, on the other hand,I think I tend to look at it more like tasks.

[01:05:47] **Brian:** So we do a lot of zipping files, inside of Lambda because we're doing stuff in S3. S3 is not a, it's not a, it's a, it's an object store. It's not a file system. So you can't like point for example, in ColdFusion, you can't point, you can't say CF zip, this directory, it doesn't work that way. Right. you actually have to like pull each of the files in.

[01:06:05] **Brian:** So, one by one, which is tedious and awful, but we can not just try to make that function more generic. Like here's a payload zip. Regardless of where those files are, as long as you have permission to do it, go ahead and do it. so I think it's more about shared libraries than trying to, in some ways then making really small functions, but the function should perform the task and absolutely no more than

[01:06:24] **Ben:**

[01:06:24] **Brian:** Does that make

[01:06:24] **Ben:** Yeah. Yeah. And I, and as you're articulating that, I think I also kind of come up with a different way to phrase the question a little bit. And I don't know if this adds any color, but like, imagine you had a team that came to you and said, Hey, we need to land a function. XYZ for a process that we're working on.

[01:06:39] **Ben:** Do you think a good default would then be to think, okay, you want to use it for that, but how can we think about this function that any team might want to use it to do something similar? Or should you just solve it for that team first and then not worry about it being generic

[01:06:55] **Brian:** Yeah, I solve it for that

[01:06:56] **Ben:** for that feed

[01:06:56] **Ben:** for

[01:06:57] **Brian:** be perfectly

[01:06:57] **Brian:**

[01:06:57] **Brian:** because again, for some of the stuff, the way, especially looking at sort of like event bridge or step functions, which are these sort of orchestration, environments that AWS provides for you. If you want to use them more and more, they're directly integrating with other services.

[01:07:10] **Brian:** So, two years ago, three years ago, two years ago, you had to write a Lambda function to insert a record into dynamo. Now you can just do it from within the step functions, workflow itself, right? You just say insert record. Here's the data I want to insert into this dynamo DB table and you're done.

[01:07:25] **Brian:** There's no more Lambda function even needed for that. So over time, you're going to see more of these kinds of direct service integrations. No code integrations is what some people call them. So you don't have to write separate functions for that. so for me, I'm like, for some things, it's going to be easy to abstract that away and to say, we don't need that function anymore.

[01:07:40] **Brian:** Right. But let's solve the problem now for these people. And if we see a repeated issue or repeated sort of requests, we can work on building something that's a little more abstract. my problem with a sort of abstract functions, a lot of times you want to try to do everything and don't do anything particularly well.

[01:07:53] **Ben:** Yeah.

[01:07:54] **Brian:** So I'm like solve for

[01:07:55] **Brian:** that problem.

[01:07:56] **Ben:** And I imagine the hardest part now that you have distributed systems is that there might be code there. And it's almost impossible to tell if anyone's even still using it. I mean, like you could see that a function is being invoked, but like, I can't tell you how many times, even in a simple application, you look at arguments for a method and you're like, is anyone even passing these arguments anymore?

[01:08:15] **Ben:** And you start through the hole and like you find out that everyone's just passing Noah because like the one person who needed it doesn't need it anymore. And now everyone's just passing.

[01:08:23] **Brian:** Oh yeah. And you don't have a single code monolithic code

[01:08:25] **Brian:** base, Right, To search through. I mean, you could like clone all, you're getting repos for the entire company and be like search for this, you know, and across all they get repose and hope you don't break things, but maybe that's chaos engineering.

[01:08:37] **Adam:** Ah, so I wanted to, I was trying to decide whether or not to do this, but I think it could be beneficial to the listener. So Ben, your original question there about, like writing a Lambda that reads a file from S3, maybe modifies it and writes it back to somewhere. I actually have a service that does specifically that.

[01:08:55] **Adam:** And the only thing that I really want to add to what you guys, I think everything you guys talked about was perfect, but to add to that, like, yes, and, You have to plan for failure, right? Like that Lambda could fail for myriad reasons. And

[01:09:08] **Brian:** Yeah.

[01:09:08] **Adam:** part of what we decided, like the boundaries of our Lambda was what's the recoverable case.

[01:09:15] **Adam:** Right? Can, where can we just rerun this Lambda with the exact same message and it'll just rerun

[01:09:21] **Ben:** Hm.

[01:09:22] **Adam:** that

[01:09:23] **Tim:** w what's that word? I didn't potent. I can

[01:09:25] **Brian:** I didn't potent yes. Super important. Yeah. Yeah. Adam, I totally feel you. We, all the time we have reads and writes that fail in the middle of, oh, here's 300 files. We're going to try and zip up. For example. And it fails to read one of them. So what do you do, right. Do you put that back in the queue?

[01:09:40] **Brian:** Are there other people waiting for that, and then you have to sort of retrial those things again, and that's where again, people try to do right. All this, especially in the serverless sort of distributed environment that serverless in particular. well, they'll try to write, all these tries and catches and it's like, look, use an orchestration engine, use that functions, or just send events, via event bridge, or SQS queues or whatever you're using so that you don't have to write, all of these, try success, failure, catch modes into your code and your functions.

[01:10:07] **Tim:** Then you got these giant functions that try to do all of this work when you should be using the native services, the native integrations, again, step functions is a big one. I hate to be harping on it, but it's great. to do this work for you, You tend to be

[01:10:19] **Adam:** just replaced serverless. What's that functions in

[01:10:21] **Brian:** exactly. I did. I did. Dang it.

[01:10:24] **Tim:** Yeah. it.

[01:10:24] **Tim:** seems like it.

## [01:10:25] Debugging

[01:10:25] **Tim:** So, so let me tell you what my, my, my biggest fear is like when you start separating out all these things into different concerns and that, but there are different services is kind of weird. A podcast about microservices and the struggles there is when things go wrong debugging, right?

[01:10:42] **Tim:** Where the issue is because you have so many places, you've separated everything out, they're all different services or different Lambda functions. There are step functions, how do you wrap your arms around figuring out when things go bad? Where is the

[01:10:54] **Brian:** Yeah.yes, that is a challenge. Absolutely. And there are companies that will take all of your money to help you solve that challenge. right. So two things that I try to encourage my team to do, because again, we don't certainly don't have unlimited funds anything, but, x-ray, and AWS is a great service,to say, run

[01:11:13] **Brian:** it, never heard

[01:11:13] **Brian:** of it. So it's their distributed tracing service, right? That lets you sit, take a look at our request and see, from start to finish, what that request was like, what did it do? Like what did this various surfaces of where it went through? Where were their slowdowns? Was it in dynamo? DB was an SQS. Like how long did each call or each component in the service sort of chain and the request chain actually take, and they do it down to by the millisecond.

[01:11:37] **Brian:** and you can, on a specific request you can log the DoubleClick and be like, oh look here, this one took, 736 milliseconds, but the biggest time was running this dynamo DB scan, query scan, right. Instead of a query, and that was 400 minutes. So x-ray can be very powerful. the problem with that is that it adds a lot of data to things like CloudWatch and you pay for that, as you go along.

[01:11:55] **Brian:** so you have to use those tools sparingly. And one of the nice things about x-ray is that it does the distributed tracing, basically you're kind of wrapping your Lambda function calls or API gateway requests inside of an, a larger x-ray calls saying, Hey, x-ray, you're going to trace this whole thing.

[01:12:10] **Brian:** And there's other companies out there. If you want something x-ray is nice. there are better and more thorough solutions through companies like, Lugo or dash bird or Datadog, even of course, but again, you're gonna be paying for it. So that's, that can be really helpful. The other thing to do is put, the Amazon request ID in everything you do in all of your logging, even in different Lambda functions, the it's the poor man's way to do this, but if you put it in all the requests you put in each of your Lambda functions, you can then search through using CloudWatch, right?

[01:12:38] **Brian:** And through the logging. Cause all the logging is done largely through or through CloudWatch, through Lambda functions, at least, do a query that looks for that request ID and that'll query all of your CloudWatch log streams. And you can say, oh, okay. here's the busing pieces. Here's the bits and pieces of where things went wrong.

[01:12:51] **Brian:** it's tedious. It's error prone, and it takes, yeah, it's tedious. Then the biggest thing, it's not fun. I mean, debugging a distributed environment, whether you're using, a Kubernetes cluster or a serverless stuff, and Lambda is painful, it is painful. you can't just like, do an abort and dump a bunch of stuff, in the middle of a request, it doesn't quite work that way.

[01:13:10] **Brian:** and so I think those are really the best tools to use in my experience without going to a third-party service, which we lovely. But again, that's not within our particular budget. X-ray definitely check it out and look at it. and service lens is there sort of like super set of x-ray where you say, okay, now we're gonna look at it.

[01:13:24] **Brian:** Like you define it a whole application and how stuff runs end to end. and you can sort of drill down and see where there are bottlenecks and slow requests and the number of errors and all that other stuff. It's definitely worth checking out inside of AWS.

[01:13:38] **Adam:** Okay.

[01:13:39] **Tim:** Alright, I'm

[01:13:40] **Brian:** Two more notes, AWS service lens.

[01:13:42] **Brian:** X-ray again, this is the challenge of AWS, right? Tim, you guys, how many times have you said in this podcast use a lot of AWS and you're like, what x-ray what the right service lens.

[01:13:50] **Tim:** Yeah, right? Yeah, no, exactly.

[01:13:52] **Brian:** because there again,

[01:13:54] **Tim:** I know CloudWatch, but I don't use it because it

[01:13:56] **Brian:** right? Yeah. Cloud watch is not cheap. Right. And so you got to like sample very small rates inside of x-ray.

[01:14:01] **Brian:** So you're not getting $5,000 bills a month from watching every single trace go through.

[01:14:07] **Adam:** CloudWatch pro tip, you can set a retention on every log. Is it log group, you can set retention. So for your QA servers, set it for, three days or something, production

[01:14:19] **Brian:** it because the default is forever and AWS will charge you for forever, which is great because they make money that way. But yeah, absolutely. You got it. And that's the other thing that no one talks about when you were developing AWS is you got to watch your money, like a Hawk.

[01:14:31] **Brian:** You really do, because it's so easy to let some service get out of control. And you're like, wait, why is my bill $5,000?

[01:14:37] **Ben:** Yeah.

[01:14:38] **Tim:** Yeah.

[01:14:39] **Tim:** I had a developer all of a sudden he's like, you know what? I need to turn this to an extra large service. I'm like, you went from micro to extra large without going intermediate. I mean, stop, roll

[01:14:49] **Brian:** Hey, Tim, be glad it was an exhale instead of like, an eight times or 16 times XL,

[01:14:52] **Brian:** right?

[01:14:53] **Adam:** Yeah.

[01:14:54] **Tim:** Yeah, for

[01:14:54] **Tim:** sure.

[01:14:55] **Adam:** Brian, you've been really generous with your time. We are way past an hour here.

[01:14:59] **Adam:** Um, but thank you so much for your time here. you've been a font of knowledge. Um,

[01:15:06] **Brian:** pleasure

[01:15:06] **Adam:** do you do any, consulting, like if anyone is jazzed up, yeah, like

[01:15:10] **Brian:** you, Ben. Yes. For everyone

[01:15:11] **Adam:** what about my

[01:15:12] **Brian:** Uh, sometimes you can hit me up on the Twitter. I'm always happy to try to answer some questions. I'm also like in the CFML slack where I try to answer questions one at a time, my life is so busy between, I have, I teach really year round now for Hopkins and I teach about. This year, I think 600 students, about in each terminate, super intensive and fun, but it's great. So between that and my children and my family and,

[01:15:35] **Ben:** Oh, so you don't need a fourth job.

[01:15:36] **Brian:** pays me,

[01:15:37] **Brian:** uh, and the dog can't forget the dog. I, yeah, I just don't have the, I wish I had more time to do consulting, but I'm always happy to kind of try and answer questions to the best of my,

[01:15:45] **Adam:** Cool.

[01:15:46] **Brian:** yeah.

[01:15:46] **Adam:** All right, well, we are gonna call it here. So, Brian, thank you again for your time. You said people can reach out to you on Twitter. What is your Twitter handle?

[01:15:54] **Brian:** it's at Brian underscore Kloss. That's my Twitter

[01:15:57] **Brian:** handle. K L a S at Brian underscore K L E.

[01:16:01] **Brian:** Yes. That's me.

[01:16:03] **Tim:** That's the

[01:16:04] **Brian:** Yes.

[01:16:04] **Brian:** exactly. Exactly.

## [01:16:07] Patreon

[01:16:07] **Adam:** All right. Well, this episode of Working Code is brought to you by AWS step functions and listeners like you,

[01:16:13] **Ben:** Okay.

[01:16:14] **Adam:** like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod to thank our patrons. For those support, we they'll get an invite to our Discord server, where we hang out and we chat about the podcasts, work stuff, life stuff, et cetera, et cetera.

[01:16:27] **Adam:** And we have other perks available like early access to new episodes and our after show. Of course, we need to thank our top patrons, Peter and Monte. Thank you guys so much for your support. If

## [01:16:37] Thanks For Listening!

[01:16:37] **Adam:** paying for podcasts. Isn't your thing. No worries. We appreciate you taking the time to listen, and there are some freeways that you can help us out too.

[01:16:42] **Adam:** You can share the show with your friends and coworkers, or you can leave us a rating and a review on iTunes or wherever you get your podcasts. Please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod, or leave us a message at 512-253-2633 that's 512-253-CODE.

[01:16:58] **Adam:** We'll catch you next week until.

[01:17:00] **Tim:** Your heart matters.
