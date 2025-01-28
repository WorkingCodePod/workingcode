---
title: "005: Monoliths vs. Microservices"
description: This week, the crew talks about their own mistakes, feelings of fraud, insecurities, and how Impostor Syndrome manifests in their own careers.
date: 2021-01-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/005-monolith-vs-microservices/id1544142288?i=1000505212666"></iframe>

Monoliths are bad! Microservices are good! These are the "obvious" truths that many engineers hold close to heart. So, why is it that [Ben](https://www.bennadel.com/) has been slowly [merging some of his Microservices back into his Monolith](https://www.bennadel.com/blog/3944-why-ive-been-merging-microservices-back-into-the-monolith-at-invision.htm)? It turns out that a Monolith - _like a Microservice_ - is a valid architectural choice that carries its own set of pros and cons. And, for him, his team, and their particular set of skills, the Monolith is proving to contain the right set of trade-offs.

This week, the crew talks about Ben's journey; why [InVision](https://www.invisionapp.com/) started using Microservices in the first place; and, what made him realize that it was time to start pulling services back into the core Monolith. There are no hard truths here - only thoughtful, context-aware considerations.

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Triumph:** He took the week off! He's usually not that good about taking time off; so, taking a whole week off between Christmas and New Year's was actually quite relaxing.
- **Ben's Triumph:** He managed to stay production at work during the "deployment freeze" that takes place during the holidays! This meant creating lots of small, parallel git branches tied up in a bow, ready and waiting for the 2021 deployments to begin.
- **Carol's Triumph:** She stayed up until 3am writing Unit Tests! She doesn't often work in an environment that does much testing; so, this was a new and thrilling experience. Who knew that one could be so _happy_ thinking about the _unhappy path_!
- **Tim's Triumph:** He also took the week off (his company always takes Christmas week off)! But, he's not used to taking so much time off; and, he started to get bored by Thursday (such a classic engineer).

## Notes & Links

- [GitHub "Draft" pull-requests](https://github.blog/2019-02-14-introducing-draft-pull-requests/) - it's just like a regular Pull Request (PR); but, it's intended to be a "work in progress" (WIP).
- [Silento](https://www.youtube.com/watch?v=vjW8wmF5VWc) -Watch Me (Whip/Nae Nae) - official music video.
- [Archer](https://www.fxnetworks.com/shows/archer) -a wonderfully raunchy animated series about spies (for adults). _Sploosh!_
- [Microservices](https://martinfowler.com/articles/microservices.html) - an architectural choice, write-up by Martin Fowler
- [Monolithic application](https://en.wikipedia.org/wiki/Monolithic_application) - an architectural choice.
- [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law) - how organizational structure relates to programming structure:
  > Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.
- Single-Tenant architecture - configuration in which one customer shares no resources with another customer.
- Multi-Tenant - configuration in which many customers share the same set of resources (such as all existing in the same database).
- [Single Page Application (SPA)](https://en.wikipedia.org/wiki/Single-page_application) - a common front-end application architecture in which the front-end dynamically re-renders the UI based on data-fetches.
- Distributed Monolith / Microlith - an architectural anti-pattern in which you combine the worst properties of both monoliths and microservices while reaping none / few of the rewards.
- [ColdFusion / Lucee CFML](https://www.lucee.org/) - a modern web programming language for dynamic server-side rendering.
- [Mark Richards - The Rise and Fall of Microservices](https://learning.oreilly.com/videos/oreilly-software-architecture/9781492050728/9781492050728-video328505) - presentation from O'Reilly Software Architecture Conference 2019.
- [Sam Newman - Building Microservices](https://samnewman.io/books/building_microservices/) - the canonical book on Microservices.
- [Sam Newman - Monolith To Microservices: Evolutionary Patterns To Transform Your Monolith](https://samnewman.io/books/monolith-to-microservices/) - Sam's follow-up book to Building Microservices - it should be required reading.
- [Simon Brown - Modular Monoliths](http://www.codingthearchitecture.com/presentations/devnexus2016-modular-monoliths) - presentation from DevNexus 2016 that famously had the slide:
- If you can't build a well-structured monolith, what makes you think microservices is the answer?
- [Amazon AWS Lambda](https://aws.amazon.com/lambda/) - serverless compute services.
- [Amazon AWS Fault-Injection Simulator](https://aws.amazon.com/fis/) - aka, Chaos Monkey as a Service.
- [Amazon Cloudwatch](https://docs.aws.amazon.com/cloudwatch) - a reliable, scalable, and flexible monitoring solution.
- [Kevin Conway](https://github.com/kevinconway) - Principal engineer at InVision and a strong proponent for microservices.
- [Chris Richardson](https://microservices.io/) - he was doing Microservices before there were Microservices. He's the maintainer of microservices.io.
- [Hype Cycle](https://www.gartner.com/en/research/methodologies/gartner-hype-cycle) - from the "Peak of Inflated Expectations" to the "Trough of Disillusionment" and every emotion in between, this is how the technology world experiences new technology.
- [Reactive Manifesto](https://www.reactivemanifesto.org/) - an approach to building robust applications.
- [Lagom Reactive Microservices framework](https://www.lagomframework.com/) - an opinionated microservices framework.

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/005-monoliths-vs-microservices.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:13] **Adam:** All right, here we go. It's show number five for January the 13th of 2021. Oddly enough today on the show, we're going to talk about. Monoliths versus microservices. And why Ben hates microservices on Ben.

[00:00:28] **Adam:** Yes, but first as always triumphs and fails. I'm going to go first because I have a feeling that I'm going to claim as my triumph might be kind of a popular triumph this week. So I want to be first so that you guys steal it from me and not me stealing it from you. So my triumph this week is I took the week off.

[00:00:48] **Adam:** This is currently, as we're recording the week between Christmas and new year's Eve. I don't often take long vacations. Usually I'll take a day here and a day there to make long weekends. But I find these really long weeks to be very relaxing and restorative. And it's just good mental reset. Good way to start the year.

[00:01:06] **Adam:** That's my triumph. I took the week off.

[00:01:07] **Ben:** Very nice. Bully for you. All right,

[00:01:11] **Adam:** uh, Tim, what do you got this week? A triumph or a fail? Well, mine's the

[00:01:15] **Tim:** same one. I also took a week off. Our company gives us every Christmas week off, which is nice. But, uh, being off is hard. I was getting bored by around Thursday going, you know, I'm tired of being at home.

[00:01:30] **Carol:** So are you on two weeks of vacation or a week off?

[00:01:34] **Tim:** Uh, no, we just Christmas week. And then I'm taking PTO today and we're off tomorrow for New Year's. Nice, nice, nice.

[00:01:41] **Adam:** What about you, Carol?

[00:01:43] **Carol:** I have a triumph. Um, so I've never really written a lot of unit tests. Like I've dabbled in it, but as far as actually writing testable code and writing unit tests, it's not something I've done.

[00:01:53] **Carol:** Like I've not been in an environment where that was something that was required. The last night I stayed up till like almost three o'clock writing unit tests because I was having so much fun writing just the scenarios out for everything and seeing like where there were defects and getting super happy that just by thinking through scenarios, you can identify defects.

[00:02:12] **Carol:** And you can find ways to like, solve the problem without even realizing that there could be a problem. So my triumph is that, yay, I love unit tests and I had a lot of fun

[00:02:21] **Ben:** writing

[00:02:22] **Adam:** them. Very nice. They are fun. They're fun when they're working. Yeah.

[00:02:27] **Carol:** And that was the thing that happened last night is I kept screwing myself up.

[00:02:30] **Carol:** So I was like, okay, time to walk away. Cause I'm going to need a test to test my tests now because I'm writing way too late. I suspect

[00:02:38] **Ben:** that one of the nice things about unit tests is that it gets you to think about the unhappy paths within software. Whereas I think people who write code just to write code, obviously code for the happy path, because that's how they know it's working.

[00:02:51] **Ben:** But then a lot of people forget. To do the unhappy path

[00:02:55] **Carol:** testing. Oh, yeah, it's fun. I really, really love it. I genuinely love it. Like, I am so giddy

[00:03:01] **Adam:** doing this. Nice. Well, hopefully you got some sleep. So Ben, what do you got a triumph or a fail this

[00:03:07] **Ben:** week? Uh, I'm going to call it a triumph because, uh, I was at work, but half my team was out.

[00:03:13] **Ben:** I find that when half the team is out, basically everyone is off, but some people are still there making sure the system's up and running, but during the kind of pre Christmas, I think we're going from December 24th to like January 2nd, we're having a deployment freeze. So even if you're at work, you're not allowed to deploy simply because.

[00:03:33] **Ben:** You know, stuff can go wrong and then people might have to get paid and rollbacks sometimes fail that kind of stuff.

[00:03:38] **Adam:** Nobody wants to have to deal with that on vacation.

[00:03:41] **Ben:** Yeah, a hundred percent. So it's more just courteous to the rest of the team for the deployment freeze. But I've been here and I can't work on big things because at this point in my life, I don't understand how to work on big things without deploying them incrementally.

[00:03:53] **Ben:** So I worked on a ton of really small things and I have them all in various Git branches. So it was sort of a masterclass in figuring out how to name branches that I remember what they're for later. And then when I then go to deploy them next week, I'm going to have to remember how to get all the branches back in the right order and be rebasing on master to make sure that things don't get merged in weird.

[00:04:20] **Ben:** And I don't know, it was very mentally challenging trying to move a bunch of little things forward in parallel. Because I didn't want to base all the different branches off of each other, because then I'd have to really be serious about how I merge them back in. So I have a bunch of different branches that are branched off of the main branch, which means that all the changes that I made in The different branches aren't represented in all the other branches.

[00:04:44] **Ben:** So there's going to be a lot of merge conflicts when I bring it back. So it'll be very interesting to see how that plays out. But I feel, uh, I felt good about getting as much done as I could get done without being able to deploy.

[00:04:56] **Adam:** Do you guys use GitHub or something else? GitHub. Okay, cool. Are you familiar with the draft pull requests?

[00:05:04] **Ben:** I know that that came out, I think a couple of months ago. Yeah. So

[00:05:08] **Adam:** when you're creating a pull request, you can mark it as a draft so that nobody will accidentally approve it and merge it. So basically it keeps a little bit of control in the creator's hands. So you can say like this exists so that we have a place to talk about it and a record of, okay, this branch is for this discussion, but the person who creates the pull request has to mark it as ready for review before you can actually merge it in and finish it off.

[00:05:32] **Ben:** Interesting. I think it's normally what I would put WIP in the description for. Yeah. Work

[00:05:36] **Adam:** in progress. Yeah,

[00:05:38] **Ben:** exactly. Cool.

[00:05:40] **Tim:** Watch bin whip.

[00:05:42] **Ben:** Watch bin nay nay.

[00:05:46] **Tim:** Watch bin nay nay.

[00:05:48] **Ben:** Oh my God.

[00:05:54] **Ben:** There's your stinger right there.

[00:05:56] **Adam:** Yes. Yeah. I don't know if you guys watch Archer. It's a cartoon for adults. It's very much for adults, but there's an episode where they're kind of working with a person who's I think very heavily based on Gordon Ramsay. You know, he's just very ostentatious and loud and kind of a jerk, uh, and he's a chef.

[00:06:11] **Adam:** And one of the things that he says over and over in that episode is bumper. I guess that's a thing in TV, like going to, uh, commercials or whatever.

[00:06:20] **Ben:** Love that show. Are we seriously not doing phrasing anymore?

[00:06:26] **Adam:** Carol has this confused look on her face. I have

[00:06:28] **Carol:** no idea

[00:06:29] **Adam:** what you're talking about. You've got so much TV homework from this podcast already. I don't know if we can give you more. I

[00:06:36] **Carol:** just laugh and pretend and hope no one notices.

[00:06:42] **Adam:** We notice Carol. We always notice. Okay. Move on to our main topic. Yeah. So Ben, why do you hate microservices?

[00:06:51] **Carol:** You're a bully.

[00:06:54] **Ben:** Uh, I wouldn't, I wouldn't say that I hate microservices. Uh, Microservices are a architectural choice that comes with pros and cons, right? And the pros and cons depend on what your team and company is capable of in a particular point in time. And, um, the team that I'm on. Before

[00:07:16] **Tim:** we get into that, let's define what is a microservice.

[00:07:18] **Tim:** Some people might not know, right?

[00:07:20] **Ben:** That's the 64, 000 question. I would, uh, I would say that defining a microservice is very challenging, which I think is part of why microservices themselves are very challenging. Because my understanding is microservices are a cohesive set of functionality that addresses some business concern and they're packaged in a separate deployable system.

[00:07:48] **Ben:** So

[00:07:49] **Adam:** I'm going to translate that to English for you. So basically when you write an application in the monolith style, you have one application and it does everything. A microservice is when you break a piece out of that application and it's like a function or it could be a couple of functions that work together.

[00:08:03] **Adam:** It's a bit of code that can kind of stand on its own. And it does like one job, one thing. And it does that one thing really well. And sort of, I guess the primary benefit that I see espoused for these things is that if that one thing falls over, it doesn't take down the rest of the

[00:08:17] **Carol:** app with it. And typically you would also see that that service encapsulates its data too.

[00:08:23] **Carol:** So you would have to access that service in order to access that data. So you would have a completely separate. Correct.

[00:08:29] **Tim:** Well, Wikipedia agrees with you, Ben. It says there is no single definition for microservices. A consensus view has evolved over time in the industry. So Wikipedia doesn't even know.

[00:08:39] **Ben:** Right. And that's where, in my opinion, which I will heavy caveat here is very hands off, very theoretical, very what I think after reading books about microservices. I think that's where people. So, what happens when people tend to stumble is that they don't quite understand what the microservice is supposed to do.

[00:08:59] **Ben:** So, they don't quite understand what they're supposed to put in it. Right? So, when Adam says it's supposed to do one thing and one thing really well, what does one thing mean? Is one thing... A operation is one thing, a business concern, right? Is one thing, a bounded context around a business domain. And I think there's no clear answer there, which is why there's a lot of variation in what it means to be a

[00:09:24] **Adam:** microservice.

[00:09:24] **Adam:** Yeah, that's a good point. And maybe that's a good spot to mention that, like the whole reason that we're having this conversation and the reason that I framed it as Ben being anti microservices is because this is all based off of a post that Ben, you wrote on your blog. What about a week ago talking about pulling some microservices back into your company's monolith.

[00:09:45] **Ben:** Right. So to just kind of give the bird's eye view of what that post was about. I work on a team at Invision and over time. The team that I'm on has shrunk in size in terms of number of people, but has grown in terms of the number of services that our team is responsible for. And that's because years ago when microservices were the thing du jour, , uh, our architectural team decided to start slicing out parts of our monolithic application into their own microservices.

[00:10:16] **Ben:** And in my opinion, half of the decisions were, I just want to try the new shiny tech. And half of the decisions were, we have a lot of people on the team, and we have one deployment target, and it's just a lot of people getting in line to push code to production. So, uh, our early microservices implementations were more about solving people problems than they were about solving technical problems.

[00:10:40] **Ben:** We had to divvy up work in a way where we could deploy in parallel instead of getting queued up to deploy. Um, but as the size of my team has shrunk, What we're seeing is that the same team is now having to touch multiple microservices to accomplish similar overlapping sets of tasks. And having to do that in separate services and worry about different dependencies and versioning and just general complexity.

[00:11:07] **Ben:** It's no longer worth the cost of all of the independent scalability, independent deployability. So we've been slowly merging some of those services back into the monolith. So that our now small team can more easily manage the landscape of functionality without having to worry about the added complexity of the microservices architecture.

[00:11:28] **Ben:** And that's not to say that we don't use microservices anymore. Other teams are whole hog into microservices. This is a decision that we made for our team and our set of responsibilities.

[00:11:41] **Tim:** I guess that really is the hard part in defining a microservice architecture is how big the microservice needs to be, right?

[00:11:47] **Tim:** Your blog talks about this, but the word micro is apropos of nothing. Micro makes people think everything has to be a little small, tiny service. Right sized is really the better term. It's a right sized service. Too small actually is less efficient because you're going to have a lot of network talk because basically you're building a service that talks over the network and you have a lot of crosstalk going on and just too small, it just doesn't make sense.

[00:12:10] **Tim:** So figuring out that boundary, if you draw the wrong place, it's going to create more work than it is going to solve problems. Right?

[00:12:18] **Ben:** And I tried to find the presentation that I saw this in and unfortunately I can't find it, but there was one presentation that I watched a couple of months ago where they were talking about how people love to embrace the concept of microservices because of the whole independent scalability.

[00:12:32] **Ben:** But they were saying that that's just one of the many factors that should go into whether you break code apart versus keeping it together. And the independent scalability was like the one of five choices that meant break the code apart. And the other four characteristics were, no, we should actually keep that code together.

[00:12:50] **Ben:** Things like team size and things that change usually in lockstep should be kept together. And his take on the whole microservices hype cycle. was that when they first started to become popular, everyone was looking at just that one factor and completely ignoring all the other things that would otherwise indicate that you should keep code together.

[00:13:13] **Ben:** And, uh, you know, just speaking to what is the right thing for a service to do. It's not only is it difficult to define what a microservice is, but it's difficult to define what one thing is, as we mentioned earlier.

[00:13:25] **Adam:** You talked a little bit about right sized services, and I get the sense that that's based on Conway's law, which is what you talked about in the blog posts.

[00:13:33] **Adam:** Um, do you want to talk a little bit about how you feel like Conway's law applies to your team and your product and the decisions that you're making now? Sure. So,

[00:13:44] **Ben:** uh, Conway's law, and I'll paraphrase here, cause I don't remember. I have it

[00:13:48] **Adam:** in front of me if you want me to read it. Sure. Go for it. Okay. So it says any organization that designs a system defined broadly will produce a design whose structure is a copy of the organization's communication structure.

[00:14:01] **Adam:** And then it says this law is often illustrated with a compiler example. If you have four groups working on a compiler, you'll get a four pass compiler.

[00:14:09] **Ben:** Right. So the architecture of the system essentially begins to mirror the teams that are working on that system, meaning that the architecture is optimized for the teams and not necessarily optimized for the overall performance and structure of the system.

[00:14:23] **Ben:** And I want to tangent for one second and say that one of the things you'll often hear Not just in the technology industry, but in many industries is the phrase the right tool for the job. I love that. And one of the, I think, most mentally freeing addendums that I heard to that in recent years was that it's not just the right tool for the job.

[00:14:43] **Ben:** It's the right tool for the job for the team with their skills in that moment of time. And when you take that into consideration, I think it starts to influence how you think about optimization. Yeah. And coming back to the post, we optimized towards a monolithic architecture, because that is what my team's particular skillset and resource availability happens to be in this period of time.

[00:15:12] **Ben:** That

[00:15:13] **Adam:** was the original design or that's what you're saying you're going to now?

[00:15:15] **Ben:** I'm saying that's what we're going to now as we begin to merge some of the microservices back into the monolith, because we're taking into account team size. Team skill, prioritization of feature development versus platform scalability, and all these things.

[00:15:30] **Ben:** And we've decided that what we want to optimize for is essentially team throughput, as opposed to some of the other things like maybe service durability, that kind of optimization. So by,

[00:15:42] **Adam:** by bringing everything back into the monolith, I don't know what, how you decide what is and what isn't going to be merged back into the monolith.

[00:15:50] **Adam:** That's what I'm curious

[00:15:51] **Ben:** about. So some of it on our end has to do with infrastructure costs. So microservices as a. Abstraction have no cost if you're not working on that. Meaning if you, let's say you create a Lambda service or some node based service, and it's just running and you don't have to update it from a maintenance standpoint, it's free because you get to focus on other work.

[00:16:14] **Ben:** And this microservice over here just gets to run and not require attention. But in the real world, that microservice is running on something that costs money. And in our particular platform, we have both multi tenant and single tenant environments. And our microservices have to be duplicated for all of our single tenant environments.

[00:16:36] **Ben:** So we have hundreds of single tenant environments, which means that the microservice in a multi tenant environment, which may just be sitting there humming along in the background, Now has to have several hundred instances running in single tenants. And then for redundancy purposes, you know, some multiple of those hundreds of instances.

[00:16:54] **Ben:** So what is maybe otherwise a low cost suddenly becomes a much higher cost in terms of dollars and cents, if not in terms of man hours and effort. So we've microservices back into the monolith because they won. Don't have any scaling requirements, meaning it's not like we're doing heavy CPU processing and that's why we split it out.

[00:17:17] **Ben:** We can easily tuck it back into the monolith without having any performance overhead. And then we get to slice out all of the infrastructure costs associated with that

[00:17:26] **Adam:** microservice. So. Man, I'd love to be able to sit and pick your brain about multi tenant stuff. Cause that's something that my company is kind of going through now too, but yeah, we'll put it on the list, but specifically to this situation, you talked about how you have code that is fine in a multi tenant environment, but then you have also.

[00:17:47] **Adam:** Separate from that, single tenant environments that need to run the same code. And that is part of the reasoning why you're merging that back into the monolith. I guess my question is, if you've got a multi tenant version of that code, why do you need the single tenant, why can't the single tenant environment use the multi tenant resources?

[00:18:03] **Adam:** Uh,

[00:18:04] **Ben:** contractual obligations, essentially I thought it might be part of the single tenant contracting is separation on

[00:18:10] **Adam:** prem or basically government cloud sort of thing. They

[00:18:13] **Ben:** want that what they're paying for is that enhanced security and that enhanced isolation. So it's, yeah, it's, it's more contractual than it is anything else, but other monolith.

[00:18:25] **Ben:** We're essentially just errors in judgment back in the day. The biggest error in judgment, in my opinion, was that people looked at front end code, the JavaScript, CSS, HTML, and said, Oh, the front end code all calls the backend code, but we should be able to deploy that separately. So let's just start slicing off all the JavaScript parts and put that in its own repository.

[00:18:48] **Ben:** And then we'll leave the API and the monolith. And that's honestly, since day one has caused nothing but friction, because when you think about how you want to break code apart, one of the factors that you should be taking into account is things that change together. And the reality is when you have client side code for a SPA single page application, and you have an API that feeds data for that SPA.

[00:19:11] **Ben:** Well, those tend to change together. I'm going to change an API call. And now I have to change the JavaScript that consumes that API call and manifests it into a template. So what we ended up having to do all the time. Was change the API, then check out the repository for the front end code, then change the front end code and make sure you're deploying them in the right order so that you don't accidentally deploy the front end code before the API code's available.

[00:19:35] **Ben:** And we realized that we're doing this over and over again, and it would be so much easier if they were literally next to each other on the server. So that's a smell

[00:19:41] **Tim:** test, right? If you're having to deploy things in tandem all the time, you obviously treat the boundaries wrong somewhere. And in fact, actually researching this topic beforehand, I learned a new anti pattern, I hadn't come across this one before, the Microlith.

[00:19:56] **Ben:** Microlith. The

[00:19:56] **Adam:** Microlith.

[00:19:57] **Carol:** I haven't heard of that. I don't know

[00:19:58] **Tim:** what that is. The Microlith, basically you create a microservice that's actually acting like a monolith where everything just depends on everything else, which means when you took your monolith and decomposed it, you didn't draw the boundaries correctly.

[00:20:11] **Tim:** So now you basically have spaghetti code in a microservice. There are a bunch of microservices, all of them need each other, all of them are intertangled. And so you're not getting the benefit of a microservice, a right sized service, because the boundaries weren't drawn correctly. I

[00:20:28] **Ben:** think this is also sometimes referred to as a distributed model.

[00:20:32] **Carol:** It just sounds painful.

[00:20:34] **Ben:** So a monolith is an architectural decision, just like a microservices architecture. And every architecture has pros and cons, and people often forget that the monolith has a bunch of pros associated with it, even though it has some cons. So it's not monolith is always bad. That was just the pervasive mentality for people who want to try microservices.

[00:20:56] **Ben:** Monoliths was just bad the same way that people sometimes see ColdFusion code and they're like, Oh, ColdFusion is bad. So we obviously have to rewrite this in Node or Golang or something to that effect. And, um, I watched this presentation by Mark Richards, part of the O'Reilly software architecture conference, and.

[00:21:12] **Ben:** He was saying that the reason that microservices go so poorly sometimes is because people didn't address business concerns. Yep. They were addressing technology issues and that they realized at the end that those technology issues weren't actually addressing business concerns because microservices aren't a goal.

[00:21:30] **Ben:** So Sam Newman talks about this in his Monolith to Microservices book. Which is a fantastic book. I think that should be required reading. Monolith to Microservices, Evolutionary Patterns to Transform Your Monolith. And he talks about the fact that microservices are not a goal. You shouldn't sit down and just want to have microservices.

[00:21:50] **Ben:** Those microservices should be addressing problems and those problems should speak to business concerns. And if you're not doing that. Then you're going to end up like my team did a little bit in a world of hurt where you incur a lot of the costs, but you're not getting a lot of the benefits. Right.

[00:22:05] **Adam:** Yeah.

[00:22:05] **Adam:** We started out with a monolith as well. And, um, I think instead of saying that we break things off for business reasons, most of the time, what we have done is when we hit a performance bottleneck, that would be for technical reasons, but still, um, you know, the business wants that to be online too.

[00:22:23] **Ben:** Right.

[00:22:23] **Ben:** Right. And I think, you know, availability of your application is a business concern for sure. True. If I could go back years and do everything over again, and I mentioned this in the blog post. What I would have done is focus completely on CPU bound and memory bound processes. So things like thumbnail generation, PDF generation, perhaps zip archive generation, PDF processing, things of that nature where I can have a single operation actually take a bunch of resources out of the computer such that it might slow down everyone else's request.

[00:23:00] **Ben:** If we did nothing but isolate those things. I think we would have gotten much more value out of our initial microservices efforts.

[00:23:08] **Tim:** So take the bad actors, the things that are perhaps killing performance in your CPU, spin them off as a service so that they can be on their own machine, their own hardware, their own thread, their own memory.

[00:23:18] **Tim:** You think you would have got more bang for the buck out of that?

[00:23:21] **Ben:** I think we would have been solving... A bigger problem. The actual problem. Yeah. Yeah. We would have been solving the things that were actually causing us pain. Yeah. 100%. Yeah. And

[00:23:29] **Tim:** I think a lot of times, I'm not saying this is the case in your organization, but a lot of times people that are in a monolith that is behaving badly, because if you have a monolith and it's running great, no one ever worries about it.

[00:23:39] **Tim:** But whenever it starts to get problems because it's so big, no one really knows how to attack the beast and how to solve the problem. And then someone, typically it's someone who really doesn't know the monolith very well, comes in and says, well, we just need to rewrite this whole thing from scratch. You know, here's your problem.

[00:23:56] **Tim:** It was a day one problem where you guys just made a bad decision and now it's totally screwed. And we've got to go back and rewrite it from the ground up. And let's do it as microservices. Cause that's the cool thing. All

[00:24:05] **Ben:** the cool kids are doing it. Right. I'll find this for the show notes. I can't remember who did this, but there was a presentation and the slide in this presentation, I think has become a little infamous where it said something to the effect of you couldn't build your monolith correctly.

[00:24:18] **Ben:** What makes you think you could build your microservices correctly? And I think it's so on point. It's accurate. So accurate because you can take a monolith and internally you can build it using modular patterns. Where you have clean separations of concerns and clean boundaries and, and teams can focus on different areas and you don't necessarily get the big ball of mud, the spaghetti that Tim's talking about, and if you can do that within a monolith, then maybe you don't even need the microservices.

[00:24:46] **Ben:** But if you couldn't do it in a monolith, what on earth makes you think you're going to figure out the right boundaries for a

[00:24:51] **Adam:** microservice? That makes sense. Yeah. I mean, adding microservices adds a lot of other overhead. You have to manage the microservices. You have to deploy them separately. You have to test them separately.

[00:25:00] **Adam:** Yeah. Good luck

[00:25:01] **Carol:** testing them. Et cetera.

[00:25:02] **Ben:** Yeah. Inter service communication. Yeah. Well, I

[00:25:06] **Tim:** mean, I've I've worked on both sides. In the company that I worked at, I did work on a monolith, same monolith that Carol used to work on when she was at our company. And there was definitely struggles there. People are always breaking things because it's so big and you don't realize where it's, you know, one area affects another area.

[00:25:22] **Tim:** And like Ben was talking about, you got some processes like a PDF generation, which bogs the whole system down because it sucks all the memory and resources. And it's on the same machine. So that's bad. But then we have a payments that deals with financial services and it was written from the ground up in Scala Play as a microservice architecture.

[00:25:42] **Tim:** And it was, the boundaries were drawn correctly. There's, there's maybe only like five microservices, but there's really only one I ever have to touch. The rest of them just work. That tells you it was done right. If you have services, they're doing the job they're designed to do. The other services don't really need to know how those services work and they just consume it and they all work together.

[00:26:03] **Tim:** Then, you know, it was drawn correctly. So I've seen the pain of both of them and also the benefit of both of them. So like you said, it's what will fit your organization. I was reading when we were studying for this, that, you know, apparently Amazon there, there's microservices. They try to map it one to one to a team of three to 10 engineers.

[00:26:23] **Tim:** You

[00:26:23] **Adam:** studied for this? I know.

[00:26:24] **Carol:** I was like, Ben just talked about not preparing.

[00:26:31] **Tim:** Well, I mean, Ben wrote a whole blog article. I didn't want to hit this just to be the hour of Ben talking.

[00:26:36] **Adam:** So

[00:26:37] **Carol:** what are you talking about? This is amazing. Well,

[00:26:39] **Ben:** and, and, and to be fair, again, I want to caveat here. I'm not. Anti microservices. I don't personally have a tremendous amount of hands on experience with them because I work primarily in the monolith, but even our team, we do have some node services and some lambda functions.

[00:26:56] **Ben:** That we basically never have to touch because someone wrote them and they did one thing, as Adam says, and they just work like we almost never have to touch them until Amazon stops supporting a node version for Lambda, which is a fun little experience because some node service suddenly stops working and then it goes down and then you can't deploy.

[00:27:17] **Ben:** More of them because they're like, Oh yeah, by the way, we don't support node version 0. 10 anymore. So your land doesn't come back online because it has some dependency that didn't work in newer nodes. Right. And that's an interesting case in point, because here's something that even ran very smooth on its own.

[00:27:33] **Ben:** And you don't think about the cost of that, but then you realize, well, what about security patches? And will this version of Uh, Ubuntu or whatever it runs on has to be upgraded, or this version of Node. js is no longer supported by whatever functions as a service provider you're using. And now, suddenly, the thing that you didn't have to touch, which means your team doesn't necessarily know really how it works, well, now you have to go in and update your package JSON dependencies, or you have to go, uh, install a new version of an image processor because the old one has a security vulnerability, and now that's another thing you have to test and you have to maintain.

[00:28:08] **Ben:** And there's just all these. Little hidden costs that add up over time that you didn't necessarily take into account when you thought to yourself, Oh, wouldn't it be great if I could just split this off from the monolith?

[00:28:19] **Tim:** Yeah. I mean, that is another complexity related anti pattern called the flying blind.

[00:28:23] **Tim:** Software is already kind of mysterious already because it tends to somewhat be a black box. But if you have all these microservices, let's say we have five of them. Like I said earlier, I only touch one of them. If something happens in one of the others, I don't necessarily know that that's the bad actor if I don't have sufficient logging, if I don't have sufficient monitoring.

[00:28:41] **Tim:** So all of a sudden I have an issue coming up and I'm flying blind because I don't have some alert that pops up that says this microservice has been working for the past five years that you've never touched. Something has happened to it. You know, version change or dependency change. And so there's a level of complexity there that I don't know where to look because maybe I didn't have enough monitoring there, enough logging.

[00:29:02] **Tim:** I ran into that. Uh, so definitely you've got to take that into consideration when you're building a microservices to have. Very robust logging, very robust monitoring for those

[00:29:12] **Adam:** cases. I don't know if I dreamed this or if it actually is something that's going to be available, but I feel like I have seen somewhere that Amazon was going to be providing as part of like AWS, the, uh, chaos monkey, like as a service, basically you give it access to all your stuff and occasionally it will just turn something off.

[00:29:33] **Adam:** And so the idea being that, I guess this is based on the Netflix, uh, they had something, I don't know if it was just a principle that they used or if they...

[00:29:42] **Ben:** No, I think it's an actual service they have. It's a real service.

[00:29:45] **Adam:** Yeah, yeah, it was an actual thing and it would like just turn stuff off randomly, change permissions on something.

[00:29:49] **Adam:** I've actually got a

[00:29:50] **Tim:** Chaos Monkey t shirt that Ryan Enklam from Netflix gave me. It's a great t shirt. Every time I wear it, it's on

[00:29:55] **Adam:** the brakes. Maybe you shouldn't wear it.

[00:29:59] **Carol:** Let's leave that in

[00:30:00] **Adam:** the closet.

[00:30:01] **Tim:** There's days I pull it out and go, no, it's Friday. I don't want anything to break today. I've got

[00:30:05] **Adam:** to put this t shirt away.

[00:30:06] **Adam:** Nice. But yeah, the, the idea, just the like, okay, like you're saying, sometimes it'll run fine for five years without ever needing any sort of maintenance, but by having things artificially break, you can stay on top of, okay, well maybe, maybe we should upgrade because yes, uh, you know, it's still functional, but we are three node versions behind.

[00:30:26] **Adam:** Maybe we should go ahead and, and upgrade or something like that.

[00:30:29] **Ben:** And even to Tim's point about the logging, I'm not a platform person, but I think even today getting logs and metrics out of a Lambda function is still quite challenging. I talk about flying blind. Um, I can tell you for sure that some of our old Lambda functions were essentially flying blind, and if they appear to stop working, because some sort of user facing portion of it doesn't work, we have to go to our platform team and be like...

[00:30:56] **Ben:** Can someone look at some CloudWatch logs or whatever it is that you guys do? Cause I have no idea why this is breaking. It just doesn't seem to be working. Oh, interesting.

[00:31:03] **Adam:** So that was my first thought was like, okay, well, yeah, there's, there's CloudWatch logs. Yeah, getting the logs from Lambda to something external to AWS, I could see being maybe difficult or problematic, but we've kind of centralized on CloudWatch.

[00:31:17] **Adam:** So when we have like, even if it's like a Windows EC2 box, we're pushing the logs from that to CloudWatch. So the CloudWatch is the first place that we look for logs. Um, and Lambda does report memory usage and runtime. I don't know if it reports, uh, CPU usage or not, but, uh, yeah, there's logs there.

[00:31:37] **Ben:** It was interesting.

[00:31:38] **Ben:** So after I'd written that post, I was having a discussion internally at Invision with this guy, Kevin Conway, who's on our architecture team, who no relation to Conway's law, Conway. I had posited

[00:31:51] **Ben:** in the, in the blog post that Conway's law can be helpful because. You optimize for your team structure. So you essentially optimize for your team's responsibility as opposing to optimizing for the services themselves. And he looked at that as an anti pattern. And when we got into a little bit more of a conversation about it, one thing that he was saying is that he's worked on teams where they've managed.

[00:32:12] **Ben:** 20, 30 services, and it's all been very effective. But when we were digging deeper into the details of that, what he was saying was that it works really effectively if all the services are basically built on the same constructs, right? So the logging libraries are all the same and they're written in the same language and they have the same linters and they all use the same general application architecture, right?

[00:32:32] **Ben:** And I'm like, yeah, well. As you begin to squint harder at what you're saying, that's basically a monolith. Like, oh, I took all the code and it's built the same way with the same login and the same technologies. I'm like, yeah, if you just broaden your boundaries, that's exactly what I'm doing by merging the microservices back into the monolith.

[00:32:50] **Ben:** Whereas with the microservices that we were working with, we had huge variants. We had some were in Node, some were in Golang, some were in Lucy CFML, ColdFusion technology. Some are on various different versions of Node. I was talking about the Lambda service earlier that was actually on a version of Node that was no longer even supported.

[00:33:09] **Ben:** So it's hard to make a comparison between a team that manages 30 services that are all written with the exact same libraries and languages and technologies and strategies to the team that has to manage just a handful of services. And all of those services are written in completely different technologies using completely different architectural patterns.

[00:33:30] **Ben:** Right. There's so much variance in what you can do. That it's, it's hard to say, well, it worked here. Why isn't it working over here for these people? Another

[00:33:39] **Tim:** challenge, if you do build a team around microservices or right side services type framework, you can run into the, another anti pattern is herding cats.

[00:33:50] **Tim:** And so if you have all these independent teams, if there's no governance. Over those teams, they're, you know, they're going to kind of be off on their own doing things on their own. And if it's not coordinated with the rest of the organization that can lead to to an amount of, um, disjointedness, all of a sudden you have a microservice and it breaks the pattern or contract with another service.

[00:34:13] **Tim:** And now you created a problem for the other team. So there really needs to be some sort of governance involved. Management has to be involved. Uh, at some point to decide, you know, how these things move forward. Otherwise. It's herding cats.

[00:34:27] **Adam:** That's like, it sounds to me like the job of a product manager.

[00:34:30] **Tim:** Yeah. Well, it depends. I mean, if you consider the product, the service, then each product manager only cares about the service.

[00:34:36] **Ben:** It's like sort of

[00:34:36] **Adam:** a, I guess it depends on the size of your product too. Right. Yeah.

[00:34:40] **Tim:** So who's the owner of the, of the organizational vision?

[00:34:44] **Carol:** To me, that's more of your, um, like director of engineering type role.

[00:34:47] **Carol:** Like that's where you would want to have your hands on all of it.

[00:34:50] **Adam:** When

[00:34:51] **Tim:** you have these independent services, it tends to, it doesn't have to be this way, but it tends to be each team has to be a full stack team because you've got to be able to continuously deploy. You've got to, you have a lot more concerns and in a monolith, you can just have a team that handles things on behalf of other people, because it's all sort of the same pattern.

[00:35:09] **Tim:** It's the same thing and it's, it's a known process from start

[00:35:12] **Carol:** to finish, you know, exactly how it's working. Like, you know, the steps to get there to get it done. And when you're talking about different ways of doing it, then you have no idea what the other other team was doing. So you can't just jump in and go work on it usually.

[00:35:25] **Carol:** Well,

[00:35:26] **Ben:** and I think, um, people who are higher up in the organization, part of their job is to have that long term vision. So microservices, everything, everything has pros and cons, and there's always a tension between what makes the most sense now and what makes the most sense in the future. So even going back to the right tool for the, for the job, which we talked about earlier, you know, you could have a team.

[00:35:53] **Ben:** That wants to implement a microservices architecture. And their argument is, well, if we use Erlang for this particular service, it would have, you know, super high throughput and concurrency. I don't program in Erlang, so I'm hoping I'm not making this up. And, and for them, that makes total sense, but then hopefully there's someone else in the organization at the higher level who says, okay, but what happens when everyone on that team gets hit by a bus?

[00:36:17] **Ben:** Like, do we have Erlang people at this company that are not working on that service? Can that service run on its own? How long would it take to hire up to replace those people? So it's, there's this tension between scalability, the right tool for the job, technology decisions, and how do we actually make sure that we can.

[00:36:34] **Ben:** Put human resources behind the things that we're actually building and maintain them over time. And, and those things I think are often in conflict.

[00:36:40] **Adam:** Sounds like a good way to hold your company hostage. I built this thing and I'm the only one that knows how it works. And now you're going to start paying me three times what you're already paying.

[00:36:50] **Adam:** Keep

[00:36:50] **Tim:** the

[00:36:50] **Carol:** buses away from me. And I wrote it in Cobalt. I've just been like listening. Like this has been a really good absorb kind of conversation for me. But I listened to several things that Chris Richardson had talked about and he basically is, I mean, he was doing microservices before microservices for microservices.

[00:37:09] **Carol:** Right? So, he basically was working on this pattern and didn't realize that that's where it was going to lead. So, he has a lot of really good resources. It's microservices. io. If you want to go take a look at anything, but basically he's up front, like you're probably trying to solve the wrong problem. And you need to stop thinking about your deployments.

[00:37:31] **Carol:** You need to stop thinking about a lot of things and figure out what your problem is that you're trying to solve and make sure that you're actually on the right problem, which is what you were saying, you know, commonly happens.

[00:37:42] **Ben:** Well, I mean, it's so fascinating because. These people, Chris Richardson, Sam Newman, a bunch of other people who are well known in the microservices world, when microservices were sort of peaking in their hype cycle, it was always microservices are amazing.

[00:37:57] **Ben:** We should do these things. And now if you talk to those same people and by talk to, I mean, listen to them on podcasts or read articles, talk to them. Shoulder up with them at what they'll say. And I think, you know, almost a direct quote from Sam Newman, who wrote the building microservices book, like 10 years ago, he says, when people come to him today and ask, should we build microservices?

[00:38:21] **Ben:** He says, no. Don't do it, like don't do it until you really are in pain and then do it for the right reasons.

[00:38:28] **Carol:** Right. Make sure it's for the reasons that make

[00:38:29] **Tim:** sense. Yeah. I mean, everyone likes to think that they're going to, their, their, their software is going to become hugely popular and you're going to have that problem of exponential growth, but you know, building for that right now doesn't necessarily make sense.

[00:38:41] **Tim:** Yeah. Wait till you have that problem. I mean, be smart about how you build things, but don't assume that you're going to have that issue because you might not. But that being said, if you are interested, I think there's, there's a couple other things folks should look at is one is the, the Reactive Manifesto, um, ReactiveManifesto.

[00:39:01] **Tim:** org, which is kind of goes somewhat hand in hand with, with microservices. Reactive is when you hit that peak and you're building a service that doesn't fail, uh, where reactive systems are responsive, resilient, elastic, and message driven. So take a look at that if you haven't, most people have probably seen it.

[00:39:19] **Tim:** Um, and then I talked about this before, uh, the Logum Framework, so LogumFramework. com. Um, is a, it's a reactive microservices in Java, Escala. Um, which is, if you want to see how it's very opinionated framework, so. They don't give you a lot of leeway. So if you want to see how, a way to do it, I'm not saying to use it, but if you want to see a way to build reactive services, Logum has some good documentation on, on how they do it and how they think it should be done.

[00:39:48] **Tim:** And so at least if you are looking to move to microservices, you can get a feel for what a well thought out, robust, mature system looks like. I like it. Well said. That's just my opinion. Your

[00:40:01] **Ben:** mileage may vary. Well, and I think that's the, the challenging thing, not just with microservices, but with any sufficiently complex concept is how do you see it in a way that is both consumable, but then also meaningful?

[00:40:17] **Ben:** And you see this a lot of times with things like object oriented programming, where you look at an object oriented programming example. And you're like, that's ridiculously complicated and doesn't really seem to add value. And then they're like, well, it wouldn't necessarily add value in this particular context, but you have to think about a much more complicated system.

[00:40:34] **Ben:** And it's like, you almost have to get to the point where you can already understand it in order to understand why it's valuable. It's hard to get something that's isolated. That's both meaningful and, and. And also human friendly as well. Okay. Are we done? Let's call it. I think so. All right. Why not? Yeah.

[00:40:55] **Ben:** It's new year's Eve, right? It's 11am somewhere. New year's Eve.

[00:40:58] **Adam:** It's not new year's eve for our listeners. So, uh, but, uh, no, thank you everybody for listening. We're aiming today for a slightly shorter episode. So let us know what you think. Do you like the shorter episode or do you want us to go back to a full hour?

[00:41:11] **Adam:** You can hit us up on Twitter or on Instagram. We're @WorkingCodePod or hit us up individually. All of our profiles are linked from the show notes. But again, thanks everybody for listening. If you wouldn't mind, share it with a friend. So one of the things that we've been trying to do is for each new episode, we Uh, post a new post on Twitter and on Instagram with a short video with a chunk of the show, um, to make it real easy to share that and, um, maybe a highlight, that sort of thing to help, uh, you know, explain to people why they might want to listen.

[00:41:48] **Adam:** Um, so, you know, share it with a friend, rate us on Apple podcasts or wherever you're getting your podcasts. That also helps a lot. Um, and then I guess the last thing is if you have any topic suggestions, something you'd like to hear us discuss, then... Hit us up with those too. Noice. And I, so I guess that's it.

[00:42:04] **Adam:** Thanks for listening, everybody. Peace. We cannot steal peace from syntax. I'll think of something. Okay. I'll wait for you to think of something.
