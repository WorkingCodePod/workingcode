---
title: "017: Premature Optimization"
description: This week, the crew talks about "premature optimization". As Ben explained it to his wife, this is when you "solve problems that you don't have yet". But, what kind of problems are we talking about? Missing features? Missing methodologies? Missing performance characteristics?
date: 2021-04-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/017-premature-optimization/id1544142288?i=1000516124831"></iframe>

This week, the crew talks about "premature optimization". As Ben explained it to his wife, this is when you _"solve problems that you don't have yet"_. But, what kind of problems are we talking about? Missing features? Missing methodologies? Missing performance characteristics? It seems that every aspect of the development life-cycle offers up potential pitfalls in which we may chase "perfection" needlessly when all we really needed was something that was "good enough." In the best case scenario, premature optimization is a waste of time. But, in the worst case scenario, premature optimization can kill a project before it ever gets off the ground.

### Triumphs &amp; Failures

- **Adam's Triumph** - For a long time, he and his team have been correcting a recurring data corruption issue by manually opening a record in their administrative user interface (UI) and then re-saving that record. It's easy to do; but it's tedious and frustrating. After recently completing some of his high-priority work, however, Adam was _finally_ able to locate and _fix the underlying cause_ (a race condition between two asynchronous API calls). This removed a small point of friction; but, it had an outside effect on the team morale!

- **Ben's Triumph** - After feeling gut-punched over the poor performance of his HTML Email DSL (Domain Specific Language) when running inside of a Docker container, he deployed a sanity-check experiment to production and found that ColdFusion custom tags ran _68-times faster_ in production when compared to his local development environment. This completely removed his fear of using ColdFusion custom tags to generate HTML emails; and meant that it was totally _game on_!

- **Carol's N/A** - Unfortunately, Carol was out sick. Feel better Carol! We miss you and we hope you feel better soon!

- **Tim's Triumph** - He's been working hard to find common ground with his customers during the ideation phase of Product development. And although he sometimes feels like a marriage counselor, he knows that the best way to achieve success is to include and consult with his customers, even if he suspects that the final outcome will be the same. Ultimately, customers just want to _feel heard_; and to feel like their needs are being addressed in some form or fashion.

### Notes &amp; Links

- [Go Time: Episode 172](https://changelog.com/gotime/172) - An interview with Bill Kennedy discussing best practices around the design of Go software.
- [Meme: Science vs Engineering](https://imgur.com/gallery/KkUB0dL) - A meme that pits the elegance of science against the brute-force pragmatism of engineering.
- [Sandi Metz: The Wrong Abstraction](https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction) - a blog post in which the cost of a little duplication is compared to the cost of the wrong abstraction.
- [Rule of Three](<https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)>) - a code refactoring rule-of-thumb that states an abstraction should be created only on the third time duplicate code is needed.
- [Kent C. Dodds: AHA Programming](https://kentcdodds.com/blog/aha-programming) - DRY vs. WET vs. AHA - several different rules-of-thumb for refactoring code.
- [Adam Tuttle: Errors Are Best When Emailed... Said Nobody Ever](https://adamtuttle.codes/blog/2013/errors-are-best-when-emailed-said-nobody-ever/) - a presentation on how to effectively monitor errors within your web application.
- [MongoDB is Web Scale](https://www.youtube.com/watch?v=b2F-DItXtZs) - a meme poking fun at the web scale fanatics that showed up after Document Databases were first introduced.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/017-premature-optimization.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Seriously, iTunes, why are you not showing my, oh, there it is. Okay. Hey, we are now second in the iTunes directory. If you search for the name of our podcast, instead of like seven.

[00:00:26] **Adam:** Okay, here we go. It is show number 16 for April the 7th, and on today's show, we're going to talk about premature optimization. Before that, we're going to do our triumphs and fails as usual. Unfortunately, Carol is sick and won't be joining us this evening. Aw, hope you get better, Carol. Yep, feel better. Um, so instead, Ben, I'm going to start with you this week.

[00:00:44] **Adam:** What do you got? Yeah,

[00:00:45] **Ben:** and I'm going to kick it off with a triumph. Last week, I had a failure, which was essentially that, uh, I was feeling pretty down and exhausted because of the time change, but I was also doubly feeling down because I've been having some performance issues with my, uh, ColdFusion Custom Tag DSL.

[00:01:01] **Ben:** Uh, where once I had moved to inside of a Docker container, it started to run really, really, really slow. Like, when I ran it outside of Docker. A page that executed in like 15, 20 milliseconds a second, uh, which is just kind of bananas. Um, so I had started to go down this rabbit hole of creating some sort of a two pass system where one pass would actually compile it down into another file of ColdFusion code and then the second pass would just execute that ColdFusion code that didn't have any custom tags in it.

[00:01:34] **Ben:** Mm hmm. Uh, and that just started to feel like a mess and was starting to be very confusing and I think lost a lot of the elegance that, that ColdFusion custom tags were bringing to the, to the experience. So, rather than go down that rabbit hole too far, I actually just created a very simple sample page where I executed custom tags thousands of times in a single request and I deployed that to production and I tried running it in production and it was...

[00:01:59] **Ben:** Stupid fast. Um, the thing that was taking over a second to execute in my Docker container, uh, was like 12 milliseconds once it hit production. And I think there was one where I executed 10, 000 ColdFusion custom tags in a single request. And even that only took something like 120 milliseconds in production, whereas locally it was taking, I think, over 12 seconds, sometimes 15 seconds.

[00:02:24] **Ben:** Yeah. So it's interesting to go back to the, uh, one of our earlier episodes where someone was talking about how much do you actually need to know about DevOps? I don't know if this was a listener suggestion. It was a listener

[00:02:37] **Adam:** question, I think. Oh,

[00:02:38] **Ben:** yeah. I remember that. And one of the things that we were saying was that even though you don't necessarily need to know how all the low level platform stuff works, Understanding that there are these quirks because you're on an abstracted platform system can really help at least sanity check the, what you're seeing.

[00:02:57] **Ben:** So because I knew that Docker file IO was really poor, even though it doesn't necessarily relate to what I was doing on a day to day basis, I knew enough to want to run a test in production before I went too far down the rabbit hole. So, uh, I'm feeling pretty good about that. Again, I'm feeling like I can abandon that whole two pass concept.

[00:03:14] **Ben:** I can go back to just the. ColdFusion custom tags. And, and I feel like now that elegance, uh, is intact.

[00:03:22] **Tim:** So, yeah, I saw you posted about that on, I think, believe it was Facebook and one of our friends who work at Google was like, Oh yeah, that's a known issue on Macs. Yeah. Yeah.

[00:03:31] **Ben:** Yeah. Elliot.

[00:03:33] **Tim:** Uh,

[00:03:34] **Adam:** so two questions.

[00:03:35] **Adam:** Yep. Um, one, does your production environment also run inside of Docker?

[00:03:40] **Ben:** So here's where I start to get really fuzzy. It is containerized. I don't know if that means docker. Sure. It's kubernetes. I don't know if kubernetes, I don't know if kubernetes and docker both run the same types of containers. I know that, I know that containerization.

[00:03:58] **Ben:** And

[00:03:59] **Adam:** we're officially out of my depth.

[00:04:00] **Ben:** Yeah, I was going to say like on, on, on Linux machines, like containerization is a native thing I think, right? Like you get

[00:04:06] **Adam:** that isolation. There's kernel level containerization stuff.

[00:04:12] **Ben:** Right, and I think once we, once the code hits production, I think it's running more like that.

[00:04:18] **Ben:** Okay. But I'm way out of my,

[00:04:21] **Adam:** my, my zone here. You have the luxury of having people that understand that better than you. Yes, absolutely. So then my other question is, do you think it's possible that like in your dev container, you have the template cache disabled and template cache enabled in production?

[00:04:36] **Ben:** I, I tried experimenting with a template cache that didn't seem to, the issue is that the.

[00:04:42] **Ben:** The way I was using ColdFusion Custom Tags, which is with the CFImport tag, the way Lucy is implementing the CFImport tag, it's actually checking to see if the file exists every time I go to use the tag. So, because I'm using the Custom Tags to create a DSL, Every paragraph tag, every title tag, every div tag, each of those is implemented as a custom tag.

[00:05:05] **Ben:** Right. So if you have 20, yeah, if you have 20 paragraphs in an email, I mean, really the big one is tables, right? If you have like 400 TD tags in an email, that's 400 file IO checks, which in production apparently is fairly negligible. Right. Um, but in, in Docker on Mac, it was just

[00:05:25] **Adam:** terrible. Well, congratulations.

[00:05:29] **Ben:** Yeah. So that turned around. I'm still tired this week, but, uh, overall triumphant feeling. Nice. Um, how about

[00:05:36] **Tim:** you, Adam?

[00:05:36] **Adam:** What do you got going on? I mentioned last week before I pivoted to the triumph of my book, uh, being in my hands that I had some failures going on that I was planning on talking about and I, it's the same thing that I'm going to talk about today, but it's since turned into a triumph.

[00:05:52] **Adam:** So the, the failure was that we've had this bug that's been in production in our environments for months now, and like a certain user can always hit it and most of our users never hit it. And the fix is annoying, but simple. Like you just open the record in admin and save it again and everything is fine type of thing.

[00:06:16] **Adam:** And it's like, when it goes wrong, like this, this user does whatever it is they're doing that causes the problem consistently. Um, and then, you know, we don't really know about it until a scheduled job runs. And then when that scheduled job runs, everything blows up. And so we have to, we get all these notifications and we have to go.

[00:06:35] **Adam:** Go in there, open the record, save it, rerun the schedule job and everything is fine. And so I've been wanting to come deal with this for months now because something I've been focusing on for, I hesitate to say the last year, but maybe, maybe it's been a year long now, um, that I've been kind of focusing on this concept of toil.

[00:06:55] **Adam:** Um, so there's this great Google white paper about reducing toil is from, um, Google site reliability engineers and about how like. Toil is just this work that makes you kind of hate your job because it's, you're not doing anything productive. You're just like getting the crud out of the way so that you can do your job like this thing.

[00:07:14] **Adam:** Right. And so this has been something that has happened sometimes every day, sometimes multiple times in a day. And so it just bugs my entire team. And finally, I was able to get the urgent and important things cleared off my desk so that I could spend some time looking at this. And I. And it took me about half the day to understand the problem and then, you know, another couple of hours to fix it.

[00:07:38] **Adam:** And man, it just, everybody on the team is so relieved to have it fixed. Like, uh, my boss was like, please let me buy you a beer. Uh, so that, that's my triumph is just like that sense of relief from having a super annoying

[00:07:54] **Ben:** bug fixed. Did it end up being like a one line code change you just had to

[00:07:59] **Adam:** locate? Um, not one line, but really close to that.

[00:08:02] **Adam:** So basically what it was is there, it's a really complicated form for like generating email, right? So you've got the email content, you've got when you want to schedule it, you've got all this like metadata about it. It's got a name and a subject and you can have like, like a hundred different other things about it, right?

[00:08:18] **Adam:** And how do I want to explain this? There's multiple ways to submit this form. And If you submit it in one way, sometimes it'll go, Oh, but you might also need to do this. It'll pop up a little modal and say, Do you want to do this now? It's an optional step. And when it does that, it recognizes that there's like two things going on, and it like cancels the submit from the button that you pushed.

[00:08:38] **Adam:** And the modal has a couple of buttons in it, and those are submit buttons as well. And so what was happening is that the button that you pushed Actually does sort of an async parsing of some data in JSON and spits out some HTML and that's like the message body. And basically we created a race condition and what would happen is if you click the save button and that popped up the modal and the modal only pops up under certain conditions.

[00:09:03] **Adam:** And then you click the submit button in the modal before the HTML rendering that was happening finished and updated a hidden form field. Then the value in the hidden form field that gets submitted because you hit the submit button on the form before it was updated has sort of like bad data in it that would cause this stuff to blow up.

[00:09:22] **Adam:** So it was a race condition and the fix was effectively to just move some code to happen after the save instead of like popping up that modal before the save. Nice.

[00:09:31] **Ben:** Yeah. Race conditions are always fun to track down. What's the, uh, is it, is it the Heisenberg uncertainty principle where observing, observing things changes their outcomes?

[00:09:41] **Ben:** I feel like the race conditions such that's the, how the race condition works. It's like the second you start putting in. Break points in code or, or, or logging stuff out. Sometimes it'll slow the code down enough so that the race condition never has a problem.

[00:09:55] **Adam:** Yeah. It's like when you ask your boss or, uh, you know, a more senior developer to come look over your shoulder at this problem and that makes it go away, you're like, grr.

[00:10:04] **Adam:** Schrodinger's code. There you go. Yeah. All right, Tim, what do you got this week?

[00:10:09] **Tim:** So I'm going to do a triumph this week. So. I'm at the tail end. Now, last week I talked about, you know, I said everything's coming together. This isn't that project. That project's a lot more sexy than this one. But this is um, a project that, I mean, honestly was kind of a skunkworks on my part, because I thought it needed to be done, and I had no permission whatsoever to build it, and yet I went ahead and built it, and then...

[00:10:33] **Tim:** All of a sudden, there was a need for it and it was mostly built. So, but my triumph is finding common ground with customers. So, a lot of times in order to justify the existence of a project, you have to justify that it can make income. And if you can get, you know, initial signatory person or company to get on board with it, to, To bring in the income, then you have proof that it's going to be a viable, profitable venture.

[00:11:00] **Tim:** And I just feel today, we had our meeting today. Actually, it was Monday. We had another one today, but we had a meeting Monday. Basically, they're like, all right, everything's great. Let's go live. Let's, let's, let's do this. Let's, you know, let's launch it. We're excited. And looking back at how much goodwill and common ground I had to find with the customers, uh, and the, the, they're not really the product owner, I would kind of consider myself the product owner because this isn't something I'm building just for them, this is something I'm building for lots of people, but they're like the signatory, right?

[00:11:33] **Tim:** The initial launching, um, interest. And so you definitely have to, you know, Have a lot of meetings with them and get goodwill with them and just, I mean, having the conversation, a lot of times we had meetings where I'm like, honestly, there's nothing technical to discuss here. Like I wrote the stories, the stories work, just, you know, let's just go through and approve it.

[00:11:53] **Tim:** But having the meeting and talking through, I feel a lot of times I'm a marriage counselor for other companies. Does that make sense? Yeah. We get on a call and they start talking about a problem that they have and they feel that my solution is going to solve it, they're just not sure how that would look and they talk and they talk and they talk.

[00:12:14] **Tim:** And I feel like I'm facilitating between, and they'll bring, you know, sometimes it'd be six, seven people from that other company and me and, you know, maybe a project manager and a QA person. And, um, I feel like I'm facilitating that conversation of explaining, all right, so you're saying that if we do this, this would be the effect.

[00:12:33] **Tim:** Well, really, ultimately, what does that mean to the end user and finding that common ground? A lot of times I feel like I just want to have the answer. I just want to say, look, here it is. It's perfect. Accept it. But I realized that human nature is not that way. If they don't feel they are a part of the process of coming to the conclusion, even if ultimately my conclusion was ultimately what they came up with, if they're not part of that discovery process, then they're not going to buy into it.

[00:12:59] **Tim:** And so it's not a technical issue I'm talking about here, but just, it just opened my eyes, the fact that you really need to find common ground with the customers, that you're both trying to solve the problem. And not focusing on how the problem is being solved, but what is the problem being solved, what is the effect of the problem, and explaining the re and sometimes, you know, they come up with ideas that would solve the problem, but I explain from a technical point of view how that's not feasible.

[00:13:24] **Tim:** What surprised me the most is that they're like, okay, they totally backed down. I thought they would fight me on it, and they didn't. So, yeah, so I think that's my triumph, just my unders my discovery of just find common ground with your customer, make them part of the discovery process. And you can kind of smooth over some of the technical challenges and conflict that might come sometimes from just trying to be a little more distant from just setting up all your stories and saying, here's what needs to be done.

[00:13:52] **Tim:** Here's the, here's the events. Those might not necessarily capture in their minds what needs to be done for their company.

[00:13:59] **Ben:** What's interesting because I'm an engineer. And between me and the customers is our CFT, our customer facing team. And so we will typically interface with the customers through them as the intermediary.

[00:14:13] **Ben:** And the piece of feedback that I get Back so often is thank you so much. The customer really felt heard by the changes that you put in place. And there's this just a tremendous amount of value that comes out of listening to a customer voice, their concerns slash desires slash needs. And then even if you can't build that thing for them, them knowing that you heard them out and considered it, it's, it's, it's a, it buys you a lot of emotional

[00:14:44] **Tim:** capital.

[00:14:46] **Tim:** Emotional capital, I think that's a, that's an excellent term for that because there's some things that they, they came to us with and we're working with multiple systems that we're dealing with and I, I get why you want that. I seriously do. But something that's outside my system control is not able to do that.

[00:15:02] **Tim:** So can we, like, move that from a launch Day issue to a day to type issue where and they're like, okay, once once they understood that they're like, they didn't feel like we were just pushing back because we didn't want to do it and spend the hours. We're like, we don't want to do it because. There's a whole lot of other stuff behind the scenes you don't understand that need to take place and are going to affect you in other ways other than just this one problem you're trying to solve.

[00:15:31] **Tim:** So yeah, emotional capital is definitely a good term there, Ben.

[00:15:37] **Ben:** And at work, people use this phrase that I've been really enjoying, which is fast follow. When you can't commit to something for initial release, then you just be like, but it'll be a fast follow. Somehow that feels like it's definitely going to get done.

[00:15:51] **Ben:** Just not quite now. Yeah.

[00:15:56] **Tim:** And that's important. I mean, I explained to them from a, from a financial viewpoint from our side, how software tends to, I don't know if every company is this way, but how we recognize revenue is that you really, no matter how much money you're putting in or getting back, you really can't recognize revenue until something is.

[00:16:15] **Tim:** is in production. And so getting the MVP, the, the minimal viable product in production live and, and earning is extremely important to a software company like us. And so explaining that and saying that, you know, I know you want all these things. That's awesome. Let's just get these, these subset first and then we'll follow on.

[00:16:39] **Tim:** Um, I think the issue is sometimes customers are like, well, what, what motivation do you have to get those other things done? Right, and if you built up emotional capital. They feel you're invested in it. And, you know, even though you're getting revenue from some degree, uh, initially there's, there's, they, they feel that you are invested in getting the rest of it done.

[00:17:03] **Ben:** I was just listening today to the GoTime podcast, and I think it was an interview with this guy named Bill Kennedy. I'm probably messing up the name there, but he said something on it that I hadn't heard before, but kind of hit me in the feels in a certain way, which something you were saying there, Tim, reminded me.

[00:17:20] **Ben:** Which was that any code that hasn't been deployed is technical debt. That the only time something becomes valuable is when it hits production and starts getting used by, by customers, which I don't even know if I could tell you a hundred percent what that means, but like, I feel what it means, if that makes sense.

[00:17:38] **Ben:** Like I, I, I understand what he's saying at a gut level. I don't know if I could explain. in

[00:17:45] **Adam:** words. I don't think I fully understand it, but it definitely feels like there's some truth to that. Yeah,

[00:17:50] **Ben:** yeah, exactly. It's truthy. Yeah, it's heavily truthy.

[00:17:54] **Adam:** All right, so I guess, uh, today we're going to talk about premature optimization.

[00:17:58] **Adam:** Um, I did have sort of a specific, uh, instance, I guess, in mind that made me think of this topic, but of course we can take this wherever we want to go with it. When my

[00:18:08] **Ben:** wife was asking me what we were going to talk about tonight, I said premature optimization. She was like, what's that? I had to stop and think about how I would explain it to someone who doesn't solve engineering problems.

[00:18:19] **Ben:** And I, and I summed it up as solving problems that you don't have yet.

[00:18:22] **Tim:** Or as Rachel from Friends would say, it's not that common. Doesn't happen to every code base. And yes, it is a big deal.

[00:18:31] **Ben:** Well, when I was thinking about the show, I have in my mind, this worst case scenario for me in terms of premature optimization, which is that. It prevented me from actually building something. So forever, I've wanted to build some sort of a fitness tracking application, you know, where you go in and you include your, you track your weights and your reps and your exercises, that kind of stuff.

[00:18:55] **Ben:** And I've literally, I've had this in my head since probably year 2000. I remember I was in school and I wanted to do it actually as my final school project. And I didn't end up doing it, but I had a notebook and I had all these, uh, diagrams of what I wanted my forms to look like and how I wanted to lay out the pages and track the information.

[00:19:17] **Ben:** And then I graduated from school and I got my first job and I kept wanting to do this as sort of a little side hustle and I started to write the code. And then I started to learn about object oriented programming, and I was like, oh, I'm definitely going to need to use object oriented programming to build this application.

[00:19:34] **Ben:** So I put all the development on hold, and I started to learn about object oriented programming. And that was, you know, a good 15 years ago. I still don't know object oriented programming very well, and I never built this fitness application because I didn't just sit down and do it. I kept thinking, well, there's got to be a better way to even get it done.

[00:19:56] **Ben:** And that mindset that I had to build this perfect application stopped me from building any application whatsoever. And now I am 15 years later, and I still have nothing to show for it. And, you know, I'll probably go to my deathbed with this being one of my, uh, regrets. I never built this stupid.

[00:20:16] **Adam:** Yeah, that reminds me of the phrase, or maybe it's an aphorism.

[00:20:19] **Adam:** I don't know. Um, perfect is the enemy of done. Yeah. Or good. Or is the enemy of good. Yeah. Yeah. A hundred percent.

[00:20:28] **Tim:** So, I mean, I, I kind of was coming from this from a different perspective as far as, um, when Adam, your example kind of seemed to me, seemed to me to be adding features before they're needed. Mm hmm.

[00:20:43] **Tim:** Um, and Ben's was sort of like. methodologies, um, I sort of think of premature optimization as being worrying about efficiencies in the wrong places at the wrong times, like a bubble sort versus some other type of sort, you know, doing, trying to figure out something where on a scale, right? I'm thinking more scale issues where it works, you know, something, something works fine when you have a hundred thousand users, but when you have a million users, it doesn't work, right?

[00:21:17] **Tim:** And so worrying about that million user issue before you ever have a million users and may never have a million users. Yep. That to me seems to be more of the idea of what premature optimization is. I don't know if I'm right or wrong. That's my take on it.

[00:21:35] **Adam:** I think you're right, but also that there are a lot of different, uh, what's the word that I'm looking for here?

[00:21:42] **Adam:** Like there's a lot of different disciplines where Uh, you can prematurely optimize, like, so the, the one that I'm thinking of is preparing for a huge amount of users, kind of like you were talking about, not necessarily with, um, algorithms and code efficiency, but with, like, hardware and, and automatically scaling production environments and all this stuff, like, there are some ways to do it that are relatively recent, um, creations, like the, there's been some serverless frameworks that make things real easy to, like, It's efficient with one user and easy to create and then it scales up really nicely, but that is a relatively recent creation and in years not so long gone by, it was, I think it was one of those problems that is interesting and so it attracts people because they want to work on something interesting, not because they have a problem to solve.

[00:22:32] **Adam:** Have you ever

[00:22:32] **Ben:** seen, there's a meme that was going around for a little while where it was computer scientist versus computer engineer and the computer scientist, it was this cup and it had two dinner forks and they were sort of perfectly balanced and leaning on the side of the cup. And on the computer engineer side, it was just the two forks were duct taped to the side of the cup.

[00:22:54] **Ben:** I've seen that. I think about that one because to your point about user scale and Sometimes you, you're, it's shocking how much you can get done if you don't care so much about elegance. Right. Sometimes just getting dirty and doing the thing that you know maybe will even be thrown away and embracing the idea that it will be thrown away is, is super powerful.

[00:23:19] **Adam:** Yeah, like, uh, write code for it to be deleted, I think is something I've heard some people say. Like, okay, this is my first attempt at it and I'm going to write it in a way that when we, when it's time to improve on this, you know, it's all in one place. It's, it's written in a way that makes it easy to strip this chunk out, throw it away and rewrite it with something better.

[00:23:40] **Adam:** I know

[00:23:41] **Tim:** when I first started the, the company I'm at now, 20 years ago. We had a lead engineer who was, he was very set on how much, so he had a data type, you know, so you created a SQL table, and he had very strong opinions on using a bit versus a tiny int, and all the different, and he was like, well, it won't scale, it won't scale, right, if you create a VARCHAR, you know, you do a VARCHAR, our text field is not going to scale, and he worried so much about that, and in 20 years, I have never Run across an issue where that has been the problem for the program.

[00:24:20] **Tim:** Right. And he, I mean early, I, I, I believed him. I totally believed him. I'm like, Oh my God, I cannot, I have to use a tiny int on this. If I use anything other than a tiny int, it's going to be the end of the world. And it has never been the end of the world because I use a tiny int versus a VARCHAR3. Right.

[00:24:38] **Tim:** Or what. So, Yeah, that was definite premature optimization because it was trying to solve a problem that didn't exist at that time, doesn't exist now, and probably never will, and if it did exist at that time, because we would have scaled, you know, back in 1999 to a huge, you know, thing that the technology couldn't deal with, but it's like, Every problem that we've, we've come at is, you know, it's like you, you do some code optimization, but honestly, Moore's law is being in effect.

[00:25:14] **Tim:** You just, sometimes you just keep throwing hardware at it. You either get better, better servers, more memory, or you scale horizontally. If you can, if you design that way and the, the code inefficiencies can be covered at

[00:25:28] **Adam:** the time. So that makes me think of two things. And I want to say them both because I'm sure I will forget one of them if I start with the other.

[00:25:36] **Adam:** Um, A, the whole concept of like, web scale. And then B, uh, so your whole like database example made me think of like, okay, so premature optimization, a good example of that would be putting an index on every single column, right? Like we don't, we don't know what we're going to be searching on. We don't know where we're going to need indexes, so let's just put an index on every column.

[00:25:56] **Adam:** Wow. And that idea, right? Yeah, exactly. It's a bad idea. Not only does it have a cost of you, the time it takes you to do that, but then every time you update a row or insert a row. You know, I just gotta go and update all of those indexes, and then you're not using them all, and whatever. You guys get it.

[00:26:12] **Adam:** Obviously that's a bad idea. So that would be the premature optimization. Whereas the opposite of that would be start with like almost no indexes, right? Start with the hobby stuff. I mean, you, you get an index for free on your primary key and then, you know, like whatever, if you're going to be searching based on name or something, then put, put an index on name.

[00:26:30] **Adam:** Um, and then wait for slow queries to happen and find things that you can improve to make those queries run faster. So, that's, I guess, sort of a thought that I have on premature optimization and appropriate optimization with databases. The web scale thing, so... I don't know how long ago it was, but you know, that was like the, the buzzword, right?

[00:26:48] **Adam:** Everything had to be web scale. And uh, I, to me that means you have to be prepared to become the next Facebook, the next Twitter, whatever, and have hundreds of millions of daily active users that Do you? But that's the thing, right? So when you think about it though, do you remember the fail whale? Oh yeah.

[00:27:10] **Adam:** Yeah. So, Twitter. Exactly. Twitter. So, for those that don't know, Twitter, um, you know. Early on in its life and for a long time, um, had a, their error screen was a whale like being lifted out of the water by a bunch of little birds. And it was called, it was affectionately named the Fail Whale. And you saw that screen when their infrastructure fell over and you had to like wait for the team to go in there and fix whatever problem, reboot whatever servers were being a pain in the butt.

[00:27:35] **Adam:** The checker's guide to the galaxy. Yeah, yeah. So really what that was, was they hadn't yet optimized that part of their application, whatever was being broken at the moment. You know, they wrote just enough to get that working and then they waited for stuff to break and they improved the processes and I can't tell you the last time that I saw Twitter go down if it wasn't like half of the internet is down because S3 is offline or and you know what even some of those times more recently when S3 or some of those core backbone internet services EC2 is having Twitter's still been online these days.

[00:28:12] **Adam:** And I think that, I don't want to say that Twitter didn't do any premature optimization, but I think that it's pretty clear that there was a time when Twitter wasn't quote unquote web scale and, or, you know, in some aspects of it, and now they've improved. And I think that that is what we should all aim to be, right?

[00:28:32] **Adam:** We, we should write an application, make it useful, get people to use it, experience growing pains, and then deal with those growing pains. I think the issue

[00:28:43] **Tim:** is that we are, humans are very bad at figuring out what is going to be the unknown problem because it's an unknown problem. We can optimize things we know about, but depending on what we're writing, that may not be the issue that we have for the use case that we're dealing with.

[00:29:02] **Tim:** So, do best practices, but don't get so caught up in trying to worry about, You know, a billion users, if it's not, you know, worry about that when you start getting close to that.

[00:29:15] **Adam:** Yeah, but I think the things that I would say are important to get right from day one. are security? Mm hmm. Error handling. Yeah, yeah, yeah.

[00:29:27] **Adam:** Even then, like, you can have sort of a minimum acceptable level of error handling, and you can improve on it over time. Just make sure you log it. Yeah, yeah. Log from day one. What else? Like, what can you not afford to screw up? I think payment collection product, I think product

[00:29:45] **Tim:** feedback, right? So finding out if your users are actually using the features that you have and if they're working well for them, some sort of quality metric to say, here's how.

[00:29:57] **Tim:** The product is being perceived because, I mean, there's a very small subset of people that ever report a problem to you.

[00:30:04] **Adam:** So I agree, but I think that that is something that doesn't, for me personally, clear the bar of Has to be absolutely perfect from day one, right? Like, yes, you want to have some user feedback mechanisms and you want to have visibility into what the application is being used, what parts of the application are breaking, but it's okay if it's not, if it's got rough edges to start, then, you know, as it gets used more and more, you improve it.

[00:30:34] **Adam:** And to be fair, product

[00:30:35] **Tim:** feedback could be a person got an error here, right? Yeah. So like Vin was saying, you know, logging error problems and trying to fully under, being able to replicate an error rather than like, okay, an error happened. I'm, I can't recreate it. I don't have no idea how to fix it.

[00:30:52] **Tim:** Hopefully it will happen again, or someone will report it and give me a screenshot, you know.

[00:30:58] **Adam:** I can't tell you how many companies I've worked for, applications that I've worked on that. I was just totally oblivious of what was going on in the application at any given time. And the company that I work for now, the application that I had the luxury of designing my way, I was developer number one on it.

[00:31:19] **Adam:** Um, from the ground up. And we have so much visibility into what's going on in this system. Every single exception that gets thrown is logged and the important ones get pushed in front of us into our team chat. And we have... Pre emptive notifications, like alarms go off when the CPU is getting high for an extended duration, or database, uh, CPU is high, or query times are starting to climb, that sort of thing, and it makes me just...

[00:31:51] **Adam:** Not ashamed, that's not the right word, but it just makes me so aware of how naive I was for so long in this industry. You know, I was just throwing code into a dark room, like, this should work, and then waiting for an email to say it's broken.

[00:32:10] **Ben:** I used to, back in the day. Email myself errors. Oh yeah. And then every now and then something, not catastrophic, but something pretty terrible would happen on the site.

[00:32:20] **Ben:** And I'd get so many emails that my email would basically become unusable. Or if I was sending them through, uh, an email vendor, the vendor would just shut us down and be like, Hey, you're spamming, you're, you're spamming us. Can you please fix whatever it is? And then let us know. And we'll turn your system

[00:32:35] **Adam:** back on.

[00:32:36] **Adam:** Nice. I worked on a team that, uh, you know, had like a rotating on call. And, um, instead of having like a central error logging database or anything like that, like you said, they were all sent to email. And so the solution was we had an email account that we all shared the login info to, and you would like sign into this email account when it was your week to be on call and just look at the tens of thousands of unread messages in this mailbox to get like auto sorted into different folders and outlook.

[00:33:04] **Adam:** And you're like, how is this helpful again?

[00:33:10] **Ben:** It's crazy.

[00:33:12] **Adam:** So also, this reminds me, I don't know if you were there, there was a presentation I gave at CFObjective some year. I remember. About, uh, BugLog. And if I remember correctly, the title of my presentation was Errors are best when emailed... said nobody ever.

[00:33:31] **Tim:** I remember that one. I was on the steering committee on that conference. Nice. It was a good talk too. Thank you.

[00:33:39] **Ben:** Going back to what Tim was talking about earlier about... deferring problems. One nice thing that you get when you do that is you discover that some problems actually never need to be solved. Yes.

[00:33:51] **Ben:** And so essentially when you're solving problems before they need to be solved, you're paying for stuff you don't need to pay for in terms of time and, and people, people hours and whatnot.

[00:34:03] **Tim:** We have an acronym for that. It's called

[00:34:04] **Adam:** IPIGA. Please explain.

[00:34:07] **Tim:** Ignore problem. It goes away. Nice.

[00:34:11] **Adam:** I like that.

[00:34:13] **Tim:** And sometimes it does, honestly.

[00:34:16] **Ben:** In, uh, in some interview I was listening to with Uncle Bob Martin, uh, he was talking about, I think it was some sort of wiki he was building or something. I can't remember, but I remember he was saying that on the outset of the project, they were trying to figure out what database they wanted to use and they couldn't figure it out.

[00:34:33] **Ben:** So they just created, uh, like a file IO abstraction, like a data storage abstraction. And at first they were just writing stuff to files and then they were building the application. This was fine. They were like, Oh, we should really figure out what database we're going to use. They're like, ah, we've got more important stuff to be working on.

[00:34:49] **Ben:** And eventually they got to the end of the project and they realized that they had been using this data storage abstraction that was just writing stuff to physical files. And they were like, Oh, you know what? This is actually totally fine. We don't, we don't, we don't need a database.

[00:35:02] **Adam:** It's like the very first static site generator.

[00:35:04] **Adam:** Yeah,

[00:35:06] **Ben:** that's funny. So yeah, you just keep kicking the can down the road where you can. And, uh, and sometimes magic happens.

[00:35:12] **Adam:** Absolutely. I mean, I think it

[00:35:14] **Tim:** really is deciding where your energies are best spent, right? And sometimes. If we're afraid, if we have a fear of committing, we, we just, we want to work on the, the edge problems or the future problems that, that we worry about.

[00:35:36] **Tim:** But aren't 100% sure that are going to happen. We worry about those as an excuse to

[00:35:41] **Adam:** getting stuff done. Like as a way to look busy or to feel busy because maybe because you and I think you said this in a previous episode because you're intimidated by or, you know, for whatever reason procrastinating on something else that you should be working on.

[00:35:56] **Adam:** But you're either more interested in or for whatever reason you're just trying to not work on that. So you work on something else that's... Yeah, it's avoidance sometimes, right? So it's

[00:36:07] **Tim:** like, you know, this isn't perfect so I'm going to avoid it. But really that's not the issue. The issue is like you don't have confidence that you can build what you said you can build.

[00:36:17] **Tim:** And so build something good enough and don't worry about Being perfect because none of it is, it never will be. And it will always continue to grow.

[00:36:30] **Ben:** I was just listening yesterday to a Seth Godin podcast. He has a really great podcast called Akimbo and the latest episode, he talks about perfect versus perfection.

[00:36:42] **Ben:** And how something can be perfect for what it needs to be, which is fine. But then this idea of perfection, constantly needing to find perfection is exactly what you're talking about, where you're sort of, you're, you're doing stuff so that you don't have to do other stuff, thinking that you have to solve an infinite number of problems before providing value

[00:37:02] **Tim:** to people.

[00:37:03] **Tim:** Yeah. Cause I mean, perfect could just mean complete, right? I mean, it. It's perfect for what you need at the time. It's not perfection in that it's everything you need at the time.

[00:37:12] **Adam:** If I'm understanding this correctly, perfect is a description that you give something after it's done to say like, this was everything that it, that it turned out I needed.

[00:37:22] **Adam:** Whereas perfection is an ideal that you chase and you probably will never get there. Yeah, I think

[00:37:28] **Ben:** that's right. One of the ones that I always come back to because I'm, I'm still trying to mental it out is, uh, document databases. So I've been a relational database person since I began my career. That was the thing that people use.

[00:37:45] **Ben:** That's what I learned. And that's what I'm much better at. I'm with you, bro. Yeah. And, and when things like MongoDB and CouchDB first came out, I mean, WebScale, WebScale became a meme, basically. At that time, every, you know, all databases had to be web scale. And, uh, to this day, I still just use and really enjoy a relational database.

[00:38:08] **Ben:** And we do have some document databases, but even the document database stuff that we do today feels to me less enjoyable than a relational database, because it doesn't have a lot of the predictability of seeing a hard schema that I get in a relational database. And even when they talk, I mean, talk about premature optimization, when, uh, the canonical example with a document database is, well, what happens if someone purchases something and then you need to have a purchase order and needs to have line items in it, and those can't refer back to the old product, and so in a document database, you would just store the purchase order plus all of the items all in like one giant document.

[00:38:47] **Ben:** I was thinking to myself, I would just create new tables. Like I took a database modeling class in school. I understand how to model things out. It's almost like there's this weird fear of having to create tables and people optimize for not having to create tables by creating a schema that can be changed arbitrarily.

[00:39:11] **Adam:** That kind of reminds me of some optimizations that we've been doing in the last few months. That are basically denormalization, right? So when you talk about normalizing a database, you're like, okay, there's only one, uh, record with us and with an ID number, a unique ID says, this is the widget and anytime you're going to refer to the widget, you give, you put the ID of the widget in your other record and you're referring back to it.

[00:39:36] **Adam:** And so many places in our code, we started out with things very normalized, you know, like event registrations, this and that, and you sign up for all your activities, and the event can have activities, activities can have sections, and activities and sections can all have options, and different prices, and blah, blah, blah, blah, blah.

[00:39:55] **Adam:** And when you go to do reporting. It gets to be a real pain because you've got to go 12 levels deep on all this stuff. Whereas if at the time that the registration is no longer likely to change, which is like when they've paid for it. You capture the current state of things and you, you know, all the prices that you're rolling up into, like the registration total, for example, and you store that on the registration, then you don't have to go look that up every time you want to display it.

[00:40:23] **Adam:** Yeah. Every time you wanna sum across all registrations. So we've been doing a lot of that denormalization to improve performance lately, and it's been, that's an easy win, right?

[00:40:35] **Tim:** Yeah. We, I mean we, we do the exact same thing. It's like, so for all the transactional stuff for, for financial. Things, it's all very normalized, very quick for reporting, it's all immediately shipped out to somewhere else and flattened and denormalized.

[00:40:51] **Tim:** And so, but again, we're using relational data, we're not using document storage on that, we're using PostgreSQL and you know, so I'm with you, but I do struggle to find the true value of a, of a document store, you know, like MongoDB. And it's probably just because That's not the background. I'm with you on the background that I came from that I fully understand T SQL.

[00:41:17] **Tim:** Right. Right. I know what that means, but, you know, a document stored just sounds like. I'm storing like text and PDFs or something. I know that's not the way it

[00:41:28] **Adam:** is, but. I'm not a heavy user. We don't have any that we're currently using in production, although we, well, unless you count Elasticsearch, I'm not sure.

[00:41:36] **Adam:** Short of that, you know, we occasionally just go, you know, is this the thing? You know, we'll be discussing some engineering challenge and we'll go, is this when we're supposed to start using a document database? Is this the problem that it solves? And we kick it around for a while and we go. I mean, no, maybe, I mean, maybe yes, maybe can help, but also we have a ton of relational database experience right here on our team, and we can solve this problem with relational databases, but the thing that I think might end up becoming a use case that we would try a document database for or NoSQL would be Like a distributed system where you want that eventual consistency, but the individual consistency within a shard or wherever you're going to call it, like a region is fine on the short term.

[00:42:30] **Adam:** Um, that might be what pushes us over the edge.

[00:42:34] **Tim:** And so I would just cheat and say that's where I would use CockroachDB. Where it's, it's basically the best of both

[00:42:40] **Adam:** worlds. So my understanding of CockroachDB is that it's, it's like you can treat it almost like a document database, but it's... Still relational, right?

[00:42:50] **Adam:** Yeah. And isn't it, wasn't, is that also the premise that was true for RethinkDB?

[00:42:56] **Tim:** I don't know about Rethink. I know that this was based off of Spanner, which was Google, Google's version of it. And then the guys from, from Google started their own open source company called CockroachDB. Gotcha. But yeah, that, that premise, you have multiple shards.

[00:43:10] **Tim:** It's eventually consistent. It. But it is ACID and it's T SQL. It uses the Postgres wire protocol. So it, to me, that just seems to be the best of all worlds for, for my team.

[00:43:23] **Ben:** This is a total tangent for a second, but I was listening to an interview, I don't know, maybe a year and a half ago with this guy who's, he's a consultant and he comes in and he helps companies figure out how to use document databases properly.

[00:43:36] **Ben:** Um, I think he was originally... I don't know if he was part of the Mongo core team or he was part of the core team that implemented Mongo supported Amazon. Something where he's got a ton of Mongo experience. Anyway, he was, he brought up two things that I thought were really funny. One was that people always talk about big data, like they have big data problems because they have a terabyte of data.

[00:43:59] **Ben:** He was just like, Oh, that's adorable. Like, that's not, that's not what big data is like, like you gotta be like petabytes of data before you have to have big data problems. And as one of the sort of sub examples that I have of that, where he was talking about how people like having, uh, document databases because they can scale horizontally and you can shard them, and, uh, he said he had this one client that he was consulting with, and they needed to rebalance their shards.

[00:44:26] **Ben:** And he was like, yeah, so we kicked off the rebalancing in January and we expect it to be done around June. Whoa. Yeah. Just cause like, that's the amount of data that they have to move around to rebalance their shards. I'm like, yeah, that's so that's like orders of magnitude. It's many orders of magnitude beyond what I would have even considered a big data problem.

[00:44:46] **Ben:** It's crazy. Wow. I don't even know where I got onto that. Just document databases. Yeah. Fun times.

[00:44:54] **Adam:** Well, while we're off topic here, I don't think this is true anymore. But there was a time when MongoDB was kind of well known for like, just losing people's data. And, you know, you'd commit something and it was like, meh, it might get saved.

[00:45:08] **Adam:** It might not. And so people had, uh, like MongoDB coffee mugs and would like drill a hole in the bottom.

[00:45:16] **Tim:** I'm sure they fixed that by now.

[00:45:23] **Ben:** Oh, God. I, I, maybe, maybe one thing worth bringing up is that sometimes premature optimization can get in the way of actual research and development. Um, and by that, I mean, sometimes, you know, you need to create a bad solution just to get a sense of what the landscape of a problem looks like.

[00:45:44] **Ben:** For sure. And if you start trying to over optimize early in the research, it's, you... It's like you're creating stumbling blocks for yourself and you, you may never end up actually doing the research on the thing you wanted to do the research on.

[00:46:01] **Tim:** Yeah, I would say, so when it comes to this topic of premature optimization, the first step is get something working, right?

[00:46:11] **Tim:** And then every programmer should be refactoring things. So you're going to create it the first time, refactor it to where you're following what you know to be best practices. If you get to the point where you start thinking about issues that really aren't on the immediate horizon, and by immediate I mean not just today, but the next few years.

[00:46:36] **Tim:** Stop. Don't worry about that now. Postpone that and work on other things. Work on other features of the app that will make your software more usable for the user. Because ultimately, if you're optimizing something for something that no one ever uses, it's a waste of time. Build something someone will use and when the usage starts to become difficult, optimize then.

[00:47:04] **Tim:** That's my

[00:47:05] **Adam:** summary. Yeah, I mean, it kind of goes back to that sort of agile manifesto or mantra of like, make it work, then make it right, then make it fast. And

[00:47:17] **Ben:** also, uh, one thing could be worth talking about is abstractions, which I think an abstraction is in some form of a premature optimization, or it can be a premature optimization.

[00:47:28] **Ben:** Sandy Matz in the Ruby world has a saying that's something like. A little bit of duplication is better than the wrong abstraction. Cause when you try to create an abstraction that handles a lot of situations, if you do that too early, you're probably not going to create the right abstraction and everything becomes challenging when you go to use it.

[00:47:47] **Ben:** And, and I think I've heard the expression something along the lines of like. 1, 2, 3, refactor, which is this idea of you write something once, that's fine, you find you write that same thing in a second place, you're getting a sense that it's getting reused, if you write that thing in a third place, now you know that it's, it's probably something that can be factored out into some sort of abstraction, but don't on execution 1 think, how can I make this into a reusable form factor?

[00:48:18] **Ben:** Actually get it written and duplicated in a number of places so that you can suss out what it's actually going to look like and how it's actually going to perform and be consumed. And then once you have the evidence that something should become an abstraction, then you can go about creating that abstraction.

[00:48:34] **Ben:** But if you try to do that too early, it's, it's almost

[00:48:37] **Tim:** certainly not going to work out well. And to be fair, I've done all of them. I've done all of

[00:48:44] **Adam:** them. There's a blog post that I'm looking for from Kent C. Dodds, and it's about, it's kind of along the same lines of that, um, 123 refactor, and it's, uh, Ah, here it is.

[00:48:56] **Adam:** AHA Programming. So you've got, again, I, uh, so obviously I can't take credit for this. This is Ken C. Dodds, and we'll link to the post in the, um, show notes, but so he starts off by describing dry, right? Don't repeat yourself. Then sort of as a competitor, I don't know what to call it, you know, an alternative take instead of dry would be wet, which is write everything twice.

[00:49:26] **Adam:** Um, and he says that that's a little, it's still a little too dogmatic and, um, prescriptive. And so his take is, aha, like, aha, I just had an idea. A H A. Um, and his is avoid hasty abstractions. So I think You know, ties in nicely to what you were saying. Prefer... Oh, and his blog post even refers back to Sandy Metz.

[00:49:50] **Adam:** Prefer duplication over the wrong abstraction. Look at that. What a small world we live in. It's a circle. Yeah,

[00:49:59] **Ben:** I'll tell you that's the thing I love about listening to podcasts that involve programming languages that I don't use. You just get these little tidbits of perspective and exposure to other ideas that you don't necessarily get in your own community.

[00:50:16] **Adam:** I mean, I can't even keep up with the podcasts that I want to listen to that are all relevant to my own personal interests. I don't know how you have time for

[00:50:23] **Ben:** it. It's, I mean, I, I just scratched

[00:50:25] **Adam:** the surface, I think. Yeah. I mean, I'm, I subscribe to a whole bunch of different podcasts that are like, there's, I have multiple categories, right?

[00:50:32] **Adam:** I have the, like, this goes to the top of the list, my queue when new episodes come out, and these go to the bottom of the queue when new episodes come out. And then if it doesn't, like, if it's, if it's not one of those two, then I'm just going to unsubscribe. I don't even listen to ours.

[00:50:49] **Adam:** I would say me neither, but mine is only true because, uh, I'm, I'm tired of it by the time I'm done editing it, right? I've listened to it five, 10 times. So then it's time for me to thank our Patreon supporters. So we've got a bunch of people supporting us on Patreon and we really appreciate their support.

[00:51:04] **Adam:** If you think you've earned, if you think you've earned it, if you think we've earned it, then please consider supporting us on Patreon. You can find us there at patreon.com/WorkingCodePod. We have a bunch of different support tiers with different perks, like a lifetime invite to our Discord server, early access to new episodes, and the after show where we keep the mics running for another 10 to 15 minutes after the show ends.

[00:51:24] **Adam:** It

[00:51:24] **Ben:** gets crazy!

[00:51:27] **Adam:** We also have what we call our top tier on Patreon for people who want to pay a little bit extra and in exchange they get what we call a sponsored shoutout. So this week's sponsored shoutout is going to go to GirlsWhoCode again this week. Um, we thought that maybe since, uh, as we're recording this, it's middle of March.

[00:51:43] **Adam:** And we just recently had, I think it was International Women's Day earlier this month. So we're gonna stay focused on the female persuasion for the time being. So GirlsWhoCode, wonderful organization if you can help them out. Maybe some money, some pizza, some equipment, some time. That's a good place to, to, uh, throw your support.

[00:52:02] **Adam:** Girls rock. So, uh, thank you to our patrons and everyone else that just listens to the show. Thank you for listening. So don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[00:52:18] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod. We'll catch you next week. And until then, your heart matters.

[00:52:47] **TTS:** When we were talking about web scale, did you guys ever see those? I don't know if you'd call it a meme. But kind of when MongoDB came out, people started making these short little animated, it was like you could type in dialogue and it would do this little animated characters for you. And it was all about web scale.

[00:53:06] **TTS:** Everybody knows that relational databases don't scale because they use joins and write to disk. Scalability is a complicated topic and it's hard to make a general statement like that. Relational databases weren't built for web scale. MongoDB handles web scale. You turn it on and it scales right up. It may surprise you that there are a handful of high profile websites still using relational databases and in particular MySQL. Relational databases have impotence mismatch. I think you mean impedance. MySQL is slow as a dog. MongoDB will run circles around MySQL because MongoDB is web scale.
