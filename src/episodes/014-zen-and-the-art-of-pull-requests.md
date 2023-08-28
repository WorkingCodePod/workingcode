---
title: "014: Zen and the Art of Pull Requests"
description: "This week, the crew meets to discuss Ben's approach to Pull Requests, reaching consensus on some concepts and pushing-back strongly on others."
date: 2021-03-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/014-zen-and-the-art-of-pull-requests/id1544142288?i=1000513408055"></iframe>

Ben has _"feelings"_ about many aspects of web application development. And, after working with [git][git] and [GitHub][github] for the last 10-years, he's formed a lot of _strong opinions_ - oftentimes _strongly held_ - about how Pull Requests (PRs) should be created and managed within a team context. For example:

> **Code completed** is more important than **code being written**. As such, if an open PR sits around for more than an hour, your team has _failed_ to review said PR in a timely manner.

And:

> If a PR takes **more than 15-minutes** to review, the PR is too large. The author of said PR has failed to decompose the problem into smaller, independently-deployable changes.

As you can imagine, Ben's "PR Commandments" don't work for every one or every team. This week, the crew meets to discuss his approach to Pull Requests, reaching consensus on some concepts and pushing-back strongly on others. And, of course, this is totally fine - every team has its own set of constraints that have bearing on how that team operates. Your mileage my vary!

Plus, we find out that Carol can be bribed with tacos... sweet, sweet tacos!

### Triumphs &amp; Failures

-  **Adam's Triumph** - He just had his **9-year work anniversary** at [AlumnIQ][alumniq]! And, as he reflects on the last 9-years, he's amazed to realize that he never wanted to quit. Every day seems to be a stream of challenges; which is exactly what makes the work _so invigorating_! When he thinks back to prior jobs that _he has quit_, they were always boring jobs building "forms over data" type products. He's looking forward to the next 9-years!

-  **Ben's Triumph** - He gets a little nostalgic this week, recalling a thought he had 15-years ago about how amazing it would be to create a software system that worked like the human body, with cells that acted independently and communicated via hormones. At the time, he dismissed the thought as being crazy; but, fast-forward to today, it turns out that his instincts were _actually spot-on_. Though, instead of hormones, we have event-streams, message queues, and pub-sub mechanism; and, instead of cells, we have distributed, independently-scalable systems that are kept up-to-date through "eventually consistent" communications!

-  **Carol's Triumph** - Her team has moved all thirteen of their pending-work branches into testing. This is the culmination of weeks of hard work. And, to top it off, she's proud of the fact that she was able to buckle-down and maintain a high standard of quality for her coding all the way to the very end! No cutting corners for this engineer!

-  **Tim's Triumph** - He was required to participate in a coaching and mentoring workshop at his company. And, though he was initially frustrated about having to put pressing-work-matters on hold, once the workshop started, he found it be quite helpful. And, he was even able to find the solution to a problem he's been wrestling with for some time! It turns out that if you open yourself up to opportunities in front of you, you never know what you're gonna find!

### Notes &amp; Links

-  [git][git] - the most popular source-control system on planet earth.
-  [GitHub][github] - a very popular source-control solution, built on git.
-  [BitBucket][bitbucket] - another popular source-control solution from Atlassian.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[alumniq]: https://www.alumniq.com/ "Better Software for Stronger Engagement"
[bitbucket]: https://bitbucket.org/
[git]: https://git-scm.com/
[github]: https://github.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/014-zen-and-the-art-of-pull-requests.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** Up until recently, I thought pull requests only came from your, your uncle. He wanted you to pull his finger.

[00:00:06] **Adam:** Pull my finger!

[00:00:07] **Tim:** No, don't do it!

[00:00:25] **Adam:** Okay, here we go. It is show number 14 for March the 17th. And on today's show, we're going to be talking about Zen and the art of pull requests. But before we get there, as always, let's do our triumphs and fails. And Carol, welcome back this week. Yay! So we're going to start with you.

[00:00:42] **Carol:** Yeah, well, I'm glad to be back, kind of.

[00:00:44] **Carol:** You know, like after you've been on vacation, you just have so much to recover from though. So I spent two days just trying to get back on my feet. Like, my body hurt from skiing and from being in the snow and from moving so much. And then I had so many emails and stuff to catch up on. But

[00:01:00] **Adam:** yeah. Don't say you need a

[00:01:01] **Tim:** vacation from

[00:01:02] **Adam:** your vacation.

[00:01:03] **Carol:** I do. I shouldn't. So I really probably shouldn't have flown home on Sunday. That's what I should have flown home like Saturday and then had Sunday to just do laundry and crap anyway. So, uh, triumph and failure. So I'm gonna go with a triumph this week. Um, I know a couple weeks ago I'd mentioned that we started the big Effort with Two Design Buddies and, you know, it's a pretty hefty project.

[00:01:24] **Carol:** Well, this week we got the final and last of the 13 branches out to testing. So, it's just, it's good to see that done. And I will say taking a vacation at the end of it has been huge, too, because I was so tired of looking at the same code over and over again. That the last 2 sets of changes and they're kind of repetitive.

[00:01:48] **Carol:** You just have to kind of keep doing it over and over. Um, but the last 2 sets, I got sloppy with and was just like done. I think it's done. It looks done. I don't want to look at it anymore. So, then when I came back with fresh eyes, I was like, all right, let me get it right this time. I'm not actually going to submit it that way.

[00:02:06] **Carol:** So I wrapped up those final two and put them in pull requests and they're out the door and testing. So four of the 13 are out in production and the rest are in QA testing. So yay, yay.

[00:02:15] **Adam:** That's awesome. But you said 13 branches and this was only something you were working on for like two or three weeks, right?

[00:02:20] **Adam:** Uh, I've

[00:02:20] **Carol:** been on it. It's been about four weeks total.

[00:02:24] **Adam:** Wow, still, in a month, 13 branches, just seems like a lot. Maybe that's just a difference in the way that we work.

[00:02:31] **Carol:** Well, the way that we did it was breaking out each set of changes into its own branch. So, the first one was the big base layer change. So, this has the big service in it, this has all of the model changes, and was kind of like the core that everything else will need in it to move forward.

[00:02:48] **Carol:** But then we wrap three with it to go into production. So four of the branches went to production. Then we put main back into all the remaining branches and got them up and testing. So, then, yeah, now they can be released individually, um, just throughout the day, whenever they're ready to go, or they can be wrapped together.

[00:03:06] **Carol:** And if they hate one, then the ones after it aren't held up by it. Yeah, getting

[00:03:10] **Adam:** done. Putting a bow on that project. Yeah. Yeah,

[00:03:13] **Carol:** getting done with that. Moving on to now the analytics. The analytics side of it. And then I'm done with it. Yeah, that's me. Woo hoo. What about you, Tim?

[00:03:23] **Tim:** Well, so I'll say it's a win.

[00:03:25] **Tim:** Um, one thing I love about our company is we get these trainings from time to time. You don't even know about, I got signed up for it. They call it an impact coaching training. And basically it's where the company as a whole is trying to get better at coaching people, mentoring people, taking, um, the next level of leaders and helping lift them up and to get better.

[00:03:47] **Tim:** And so they put me on this. Now I wasn't happy because it's like, I'm really busy and now I've got to take like four hours and one hour sessions, broke it up into four sessions that I got to take out over several weeks. But actually when I, when I did it and went through the about coaching people, mentoring people.

[00:04:04] **Tim:** I really learned a lot from it and what was nice is that you got to do it with people that weren't necessarily in, we're, we're a huge conglomeration of many different companies and so it wasn't necessarily people that I work with day to day and we got to talk about issues that we're working on and we did our coaching, mentoring, training by actually talking about real issues that we have kind of going on in our life and we would take turns being the, the coach, being the, the per, the coachee and then also just an observer.

[00:04:30] **Tim:** And then giving feedback on it and actually going through the exercise, which I thought would be stupid and pointless at first, turned out to be helpful because going through it and the person that I'm talking to my issue about knows nothing about what I do, nothing about my organization, but using the tips and techniques they were talking about, reflective listening and just asking questions a certain way.

[00:04:53] **Tim:** Gave me a solution to a problem that I've been battling with and, and avoiding for a while. And I immediately, while I was still on the training, kind of took a little action and got result out of it later that, that turned out to be good. So I was glad of that, that, you know, sometimes you get these trainings and people want you to, you know, bull crap that really isn't going to help me, but.

[00:05:14] **Tim:** You know, kind of go with it sometimes. And sometimes I actually learned something from it, and I, and I did. Um, and also I've been better at delegating. I'm pretty awful at delegating. I like to not, because I don't necessarily trust other people's work. It's just I like to know how things work. It's just the way I am.

[00:05:30] **Tim:** I feel I have to know how to do something before I ask someone else to do something. And I've gotten into a space now where I'm asking people to do work on a field that I don't know, a level of detail. I, I couldn't do it myself. If I asked him to do it and that always makes me uncomfortable, but, you know, obviously I can't know everything and it's impossible and me being that way will slow things down.

[00:05:53] **Tim:** So being able to delegate and seeing good results coming back, this is both from an internal employee where he's got a skill set that I totally don't have and I'm delegating it to him and he's, he's getting it done and I'm reviewing it and then I know he's getting it done and that makes me very Happy, but also we have an offshore team that, um, they've done amazing work and seeing what they're doing.

[00:06:13] **Tim:** And I know very little about what they're doing, but I, I can understand what they're supposed to do and they're getting it done. And so I could see the benefits of doing more delegation so that I can focus on my priorities. I'm happy that I'm learning those things even, you know, as late in the game as it might be for

[00:06:30] **Carol:** me.

[00:06:30] **Carol:** I was about to say, the delegating side is something that I've struggled with. Forever, because I feel like I'm the seagulls in Nemo, and I'm going, mine, mine, mine, mine, mine, mine, like, this is mine, like, I want to, yeah, I want to know, like, everything, and it's, it's not that I want to be, I don't want my name on it.

[00:06:47] **Carol:** I just want the knowledge of all of it. I want to know how it all worked, how it impacted everything. But as I've gotten older, I have realized that sometimes it's okay to just hand that one off and know that at the end of it, you'll get the understanding. You didn't have to be involved with every step along the way and it's okay to just learn at the end and not be involved so much.

[00:07:09] **Adam:** Yeah. Yeah.

[00:07:09] **Tim:** That's, uh, the same way. It's, it's, it's not that, like I said, I don't, it's not that I don't trust people to get stuff done. I know I, my, I come from the viewpoint that I think most people really want to do good work. Yeah. And if they don't do good work, it's because they don't know how, or they're not empowered, they're not given the tools to do so.

[00:07:24] **Tim:** But at the same time, it's like, if I see something really cool, I want to take it apart. I want to know how it works. Yep. I, I, you know, I get that thrill from, from breaking the puzzle apart. And I'm not able to do that when I delegate, right? I have to leave that joy to someone else. And I get jealous.

[00:07:37] **Carol:** Yep.

[00:07:38] **Carol:** You have to go work on your spreadsheets and do some number things and someone else tears it apart. I mean, I'm still,

[00:07:44] **Tim:** I'm coding out of the stuff. It's just, we got so many things going on. I can't, you know, it's like, I can't have my finger in all of it. I just gotta set stuff up on autopilot for other folks and just make sure they do it.

[00:07:53] **Tim:** So. That's good.

[00:07:56] **Ben:** That's me. What about you, man, buddy? So this week I have a triumph, but it's, it's more of a nostalgic triumph than it is anything else. And, uh, I was thinking back to, I don't know, maybe 15 years ago. And when I was really starting to learn more about computer science and about designing applications, but.

[00:08:13] **Ben:** But still really living in a world where everything that I was building was fairly simple. And I was thinking about how you could build things that were more complex. And I had always been fascinated all my life with how amazing the human body is. And, and the systems that work in the human body and just how clever they are and, and resilient.

[00:08:31] **Ben:** And I remember thinking at one point, like, Oh, imagine if you could build an application that worked like a human system where you have these disconnected parts like cells and they're communicating through hormones and you have, uh, neurons and, and you have the neuroreceptors and, and things were, you know, not necessarily having to all happen at the same time.

[00:08:51] **Ben:** And body was always sort of catching up with itself and it was regenerating and handling errors and so on and so forth. And I was like, this, the human body is so beautiful as a system. And I remember at the time thinking like, Oh, you could never build a computer system like that. I mean, that's absurd, the complexity.

[00:09:06] **Ben:** And now jump forward like 15 years and I'm thinking about, you know, things like Kafka and event streams and eventual consistency and horizontally scaled systems that have redundancy. And I'm like, Oh, wait, I was like actually kind of on point with how I was thinking about complex systems, but I didn't even, I didn't have the, the, the wherewithal to understand that how you would even translate that into a technical setting.

[00:09:32] **Ben:** So my triumph is more that I, I had a good instinct for something years ago, even though I dismissed it. And I'm just, I'm kind of proud of the fact that my mind could even go there given the fact that I had never even built a system like that.

[00:09:44] **Carol:** And the systems weren't there then either. So it wasn't like you were dreaming on someone else's dream then.

[00:09:49] **Carol:** You were. Absolutely thinking in your own thought

[00:09:52] **Adam:** about it.

[00:09:53] **Tim:** I do think it's cool though, that the comparison between programming and organic organisms, because I mean, you think about it all. Life runs off of a code of DNA. DNA is really just coding. AGCTs, I mean, it's, it's just, it's a combination of codes in a helix pattern.

[00:10:12] **Tim:** And every living thing is based off that. That one code set is the operating system that everything from slime mold to bacteria, to monkeys, to whales, to humans, all of us are running on that same code set. And that's just fascinating to

[00:10:27] **Ben:** me. It is fascinating. How about you, Adam, what do you got going on this week?

[00:10:31] **Adam:** Uh, well, this week I have a triumph. Uh, earlier this week, just a couple of days ago, actually, uh, was my nine year anniversary working for AlumniQ. Happy anniversary! Thank you. This was the longest I'd ever worked for any single company when it was my four year anniversary. So I've been here for a long damn time.

[00:10:49] **Adam:** I've been at this company for more than half of my marriage, and it's just... The thing I think that amazes me the most about it is that I haven't gotten the itch to leave. There have been times when I've been frustrated, but almost every time I've ever quit a job, it's because it's been boring. And you know, like you get, I finally work into that rut of like, I'm just making forms, right?

[00:11:08] **Adam:** Write some crud data into the database and write some reports back out and you just do that over and over ad nauseum. Yep. And this job has finally been just nonstop challenge. You know, previous jobs, there's always been time to slack off and, you know, you worry about looking busy. And this job, I am legitimately busy from five minutes before I get to my desk every morning until I'm able to drag myself away from my desk in the afternoon.

[00:11:33] **Adam:** And it's fun and it's challenging and there's some interesting technical problems and it's just, it's been a wonderful ride and I'm really looking forward to the next 10 years.

[00:11:43] **Carol:** Congratulations. It's a healthy busy, right? You'd say it's like a healthy level of... Yeah, like

[00:11:48] **Adam:** 90% of the time.

[00:11:51] **Carol:** Well, there are those times when you're so busy that you just can't do anything else.

[00:11:54] **Carol:** And after repeating that over and over again, you need some time to slack off a little, learn something and sit back and relax and enjoy what you're doing. Well, congratulations,

[00:12:03] **Adam:** man. Thank you. Yeah, that is

[00:12:05] **Ben:** awesome. Something you said reminded me of my father, who he passed away like 10 years ago or something, not to do with dates.

[00:12:12] **Ben:** But I remember when I was a kid, we got into this pickup truck that we had. It was an old pickup truck that we didn't really use very much. And I remember we got in and we had to turn the windshield wipers on and the rubber blade on the windshield wiper just like ripped off. And I remember asking my dad, why would it break?

[00:12:28] **Ben:** We never used the car. And he looked at me and he said, in life, things suffer more from disuse than they do from overuse. And just this idea of only wanting to quit jobs because they're boring and not wanting to quit when you're almost overtaxed. I think what he said sort of makes sense in a lot of different contexts.

[00:12:44] **Adam:** Absolutely. Yeah, I guess it depends on what you're getting out of the job. And what you find

[00:12:48] **Tim:** rewarding is I had, so I've been doing interviews this week, not. For me for a job, but I'm interviewing, uh, hiring a salesperson to sell our product. And one of them asked me an interesting question. He asked me, how do you reward your people?

[00:13:01] **Tim:** And my immediate answer was, I reward them with what they value. And so let me explain that. I said, if you offered me more money, It would not motivate me. No. As long as I'm making a decent wage, I'm happy. What makes me happy, what grinds my gears and gets me out of bed in the morning is a challenge.

[00:13:17] **Tim:** Something exciting, something new, something, you know, I want to build stuff. Right. If you say, Tim, you can make 10, 000 more if you do this, this, and this, I'll be like, keep your 10, 000. I'm not interested because what you just offered me is boring. Now, This person was most definitely, I mean, he's a sales guy.

[00:13:31] **Tim:** He was motivated by money. I said, I'm going to assume you're motivated by money. So what I'm going to do is I'm going to find out what it is that you're looking to get, and I'll reward you with that. And if it's, you know, a commission schedule that's going to make you work harder, then I'm going to do that.

[00:13:45] **Tim:** I said, but if that's not what motivates you, I'm going to find what it is. I'm going to offer you that. Tacos. So, I mean, I think what, what Ben was saying, you know, it's like you suffer more from disuse than overuse. Right. If what motivates you in your life is not being used enough in your work, you're going to want to quit.

[00:14:03] **Tim:** They could say, well, we're offering you more money. Well, no, I don't want to do forms every day for more money. I'm going to find something more interesting. So I'm very proud of you and happy that you're excelling in what you're doing and loving it. Thanks, dad.

[00:14:15] **Carol:** And the tacos was for real, by the way. Like, I miss

[00:14:18] **Adam:** that.

[00:14:19] **Adam:** Just not fish tacos, right? No, I'm

[00:14:21] **Carol:** allergic to fish. And dear God, Adam. That's

[00:14:23] **Adam:** why I said that. That's gross. Sorry, just as

[00:14:25] **Ben:** a quick aside, I didn't know that fish tacos were a real thing. And my, my wife was always talking about fish tacos when we first got together. And she's like, Oh yeah, you know, we'd go to this place, they make good fish tacos.

[00:14:37] **Ben:** Or she would talk about, I don't know, she, she brought it up a bunch of times. I never seen her eat one. And then we were at a restaurant and she finally ordered a fish taco and I was blown away. I was like, wait a minute. Have you not been joking all this time? I just assume fish taco is like, it sounds so gross to

[00:14:55] **Tim:** me.

[00:14:55] **Tim:** So I want to hear Carol's taco. Like what's the taco draw

[00:14:58] **Adam:** here for you? Oh yeah.

[00:14:59] **Carol:** So when I was at Silvervine every Thursday or, well, I think it was Wednesdays or Thursdays, either myself. Scotty, Daniel, or David would go by and buy bags of tacos from the local taco place, the Tacos de Mar. I do remember that.

[00:15:13] **Carol:** Those things are valuable to me, like the, the, the family connection you get knowing that on Thursday, someone's gonna have a taco on your desk for you, and in a couple Thursdays, you're gonna put tacos on everybody's desk, like, because you love the people you're with. That's not, I wouldn't walk away for 10, 000.

[00:15:29] **Carol:** Like that's not even close to that. I want those connections with people.

[00:15:32] **Adam:** That's cool. All right. Well, I guess let's move into our topic. So today we're gonna talk about pull requests and we, we almost called this episode, Ben's pull request commandments,

[00:15:42] **Carol:** the holy grail of pull requests.

[00:15:45] **Adam:** He

[00:15:45] **Ben:** has them written on stone tablets.

[00:15:46] **Ben:** I have some feelings about stuff. I mean, if that's, you know, we're on episode 13, 14, 14. Did you sleep through 14. I was, you know, in the, in the bag. And, uh, uh, I have some feelings about some things and pull requests happens to be one of those things that I have a lot of feelings about, and it's only, I think from having worked with a variety of teams and having been building pull requests for the last 10

[00:16:08] **Adam:** years.

[00:16:09] **Adam:** So before we get into the details of feelings on pull requests, maybe we should start with what is a pull request for people who haven't had the pleasure of using GitHub, because I'm sure that there's plenty of them out there. Pull my

[00:16:19] **Tim:** finger

[00:16:20] **Carol:** and find out. Insert fart sounds.

[00:16:26] **Ben:** So the way Git works is that you have multiple branches of work with one primary branch and the primary branch is typically the thing that's in production.

[00:16:35] **Ben:** At least that's the way we work where I am. And a pull request is essentially a, I don't know, I don't know how to describe it. Yeah, yeah. Someone take a stab at this. Yeah.

[00:16:43] **Carol:** So the way that I view a pull request is kind of the opposite of what the word is. So when I think of a pull request, it's pushing my code up, ready to go in.

[00:16:53] **Carol:** So it's saying, Hey, I have came off of production or wherever we started from, and I've done this work and now wherever my starting point was, usually, wherever my starting point was, I'm ready to put my work back into it. So I'm doing a pull request to push my code into the production branch, if that's what we want to call it.

[00:17:13] **Carol:** But it's the stepping point before it actually goes in to go through the checks that are in place for the team I'm on. Whether that's a code review or that's build reviews, like, whatever we have going on with it. It's that point to say, okay, we need some, some people to go sign off and say, this pull request is ready to go in.

[00:17:32] **Carol:** And then once it is, it merges in. So I've always, like, been like, why do we call it a pull request if I'm going to push my code up? Like. It shouldn't be called pull, but anyways, that's just my little sidebar

[00:17:43] **Adam:** thing. So prior to GitHub and not unique to Git, when you would make changes, you know, work in a branch or whatever in Git parlance, we'll just stick with that.

[00:17:51] **Adam:** So if I'm over in my fork and I make some changes and I commit those to my branch, when I want them to end up in your fork or the production server's fork, then what you do is you generate a patch file and it basically is like the output of Git diff. Okay. in a file with so it's got some context it's got your changes and that way you can apply that patch and it makes those same modifications in a predictable deterministic way to the same files and prior to there being like github you would email those patch files around and say okay here's my changes you can apply them locally and see what i've done and you you would have this email thread back and forth where you might have a discussion you might do a digital code review sort of thing and so pull requests I think started as a way to give a web UI to that process.

[00:18:33] **Adam:** So instead of exchanging all those patch files over email, you would push your patch up to github and there would be a page where you can view the diff. You can have comments and you can comment on specific lines of code. And over time it has grown and there's things like you're talking about the tests running or whatever other processes.

[00:18:52] **Adam:** happening sort of in line all and it kind of streamlines a bunch of different things all into one location. And it, for me, the sort of killer feature of pull requests and the reason we started using them in the first place was to have that central place for code reviews. Yep. Yeah. I could kind

[00:19:07] **Tim:** of distill it down to a phrase.

[00:19:08] **Tim:** I call them, I, I think of them as curated merges. So you have someone who is in charge of curating the repository and you have all these other people who are saying do this, do this, do this and each pull request. Someone curates those and through some process decides, yes, this is, this is worthy of coming into the fold.

[00:19:25] **Tim:** This one needs a little work. This one is completely out. That's the simplest way I think of it. It's really just a merge, ultimately. You're taking a change of code and putting it on another code set. But someone is in the middle. Or some processes in the middle that decides, does this deserve to be in here?

[00:19:40] **Tim:** Has it passed the proof that it belongs here? Because these are used by open source projects. These are used by internal projects. These are used by a lot of people.

[00:19:48] **Ben:** So. One thing that's interesting hearing you guys talk about Git and pull requests and Adam talking about mailing patches around. When I think about Git, I'm thinking about Git and GitHub.

[00:19:59] **Ben:** Um, I, I don't think about Git on its own, other than the low level, how do I change branches and merge things and rebase and stuff? But my entire way to consume Git is both locally and with GitHub. I don't think I have a Git workflow that works without GitHub. And I think that's a good preface for this conversation, because everything I'm about to say is from the perspective of Git plus GitHub.

[00:20:22] **Ben:** I have no idea how... All of this would translate if you were working with something other than Git and GitHub, so your mileage may

[00:20:29] **Carol:** vary. Yeah, I was going to say, we use Bitbucket. So I still use everything I know from Git, GitHub, Git Terminal, like I use all my terminal command line is everything I know from Git still.

[00:20:40] **Carol:** Just my interface with Bitbucket is slightly different. Um, it's not as pretty as GitHub, but I still have those same thoughts with how I function in the GitHub world, just on Bitbucket. Yeah, if you're

[00:20:51] **Adam:** using

[00:20:51] **Tim:** some online central repository of one source of truth for your GitHub repository, your mileage is going to be the same.

[00:20:59] **Tim:** I doubt anyone originally get, yes, it was completely distributed. You didn't have to have a central point. Um, people could all have their repositories and they could, like Adam was saying, you could send stuff between each other. And merge them. But what has become the de facto standard is you subscribe to a service like Atlassian or GitHub and you use that service, uh, so it's no longer truly fully distributed because if GitHub goes down, you're not going to work

[00:21:26] **Adam:** that day, right?

[00:21:28] **Adam:** Snow day. That does remind me of another detail though, which is that, like you were saying, there's, it's, before there was GitHub, there was just Git, and people had their own clones of a repository, and that is where the pull request comes from. So, so with Git, you can have multiple, what they call, remotes.

[00:21:46] **Adam:** So instead of having like a central, um, GitHub, You would just, you know, the four of us would all have our local Git repo, and you could set up a remote alias. So I could have one named Tim, one named Carol, one named Ben. And then you can pull from somebody else's, like I can pull from Ben's main into my main, or from Carol's feature branch into my main, or to...

[00:22:07] **Adam:** To my feature branch, whatever, so you can pull from them to you. And I think that that is where pull request comes from. So you're saying, okay, this code is done and it's in my local. Here's all the details you need to know if you want to pull it into yours, which is in the de facto case, the central hub.

[00:22:22] **Tim:** These are back at Linus Torvalds days, early Linux. So,

[00:22:26] **Adam:** Ben, how are we all doing them wrong?

[00:22:30] **Ben:** This is no one's doing it wrong. So it's actually, and that's a very interesting note talking about how I am both very strongly opinionated about certain things, but then at the same time, I try not to force that opinion.

[00:22:42] **Ben:** On anybody Strong

[00:22:43] **Adam:** opinions weekly held.

[00:22:44] **Ben:** Right? Right. So going back to conversations from previous episodes where I always feel very strongly about syntax, but I don't use a linter or a common formatter because my feelings are my feelings with pull requests. I have very strong feelings about pull requests, but at the same time, we don't have like a change control board or a GitHub whole request template.

[00:23:04] **Ben:** 'cause like my feelings are not necessarily your feelings. And again, your mileage may vary, et cetera, et cetera. All right. So my preparation for this show is I just started writing down a list and I had it in Trello and I just kept adding to it as things popped into my head throughout the day. So we'll go through the list, I guess, one item at a time.

[00:23:20] **Ben:** These are in no particular order.

[00:23:22] **Carol:** How many items are there? What are we talking about? Scroll,

[00:23:26] **Adam:** scroll, scroll, scroll, scroll. Maybe

[00:23:27] **Carol:** we should put them in order.

[00:23:30] **Ben:** It's too complicated. All right. So let's just kick it off. Let's just one time kick it. Do it. All right. Number one, always look at your diff in more than one context, meaning look at it on your command line.

[00:23:42] **Ben:** Look at it in a GitHub pull request context. Look at it in two. Different, unique formatting. Cause this is like going back to when you used to write papers in school and your teacher would be like, print it out and then read it on paper because reading it back on the computer is not the same. Your brain's not processing things the same way it is, is when you print it out and you read it back on paper.

[00:24:01] **Ben:** And I look at a pull request the same way. If I do git diff on the command line. I'm thinking about the code changes in one way, and then if I push it up to GitHub and I create a pull request, I then go and I look at that same diff on GitHub, and that allows me to look at it in a different context and allows my brain to catch different things, like typos or things that I suddenly realized, oh, I should change this code around, things that I didn't necessarily see in the command line.

[00:24:23] **Ben:** So. Wow. I

[00:24:24] **Tim:** did not see this one coming. Oh, I've got a lot.

[00:24:29] **Ben:** Buckle in, Tim. Buckle up,

[00:24:31] boys.

[00:24:32] **Adam:** It's a

[00:24:32] **Ben:** bumpy ride. And, and I, I guess, and I don't know if there's any way to not look at it in more than one context. I will say that having interacted with some people, I think there are those that will create the PR and just throw it over the fence and not actually review their own PR.

[00:24:49] **Ben:** And I think you're leaving money on the table when you do that. Tim's raising

[00:24:53] **Adam:** his hand.

[00:24:54] **Carol:** Yeah, I'm with you, Ben. I use Sourcetree. That's my favorite. That's my go to. So I start in Sourcetree and then I push my branch up and then I go to start the pull request in Bitbucket. So I don't do it in any code editor.

[00:25:06] **Carol:** I actually go to the Bitbucket UI, I go to the interface and I, um, start my pull request there and I read it again. And my big thing that I usually catch on my own is that I'll have tabs and space errors, and all of a sudden, it, I can see where I copied a line up from something, and now mine's tabs, and the rest of the file is spaces, and I have to make the decision on do I go change mine or tab the whole damn file over.

[00:25:32] **Carol:** I'm like, I'm gonna do one, and then undo, and let it just check it all in, and like, oh, then everyone's gonna see this whole file change for one line, and then go back in and put the spaces

[00:25:41] **Adam:** in. If you had whitespace characters on, you would have caught it in the first place.

[00:25:46] **Carol:** Actually, I so.

[00:25:47] **Adam:** It's the bees pajamas.

[00:25:51] **Adam:** I'm seeing

[00:25:51] **Tim:** that. I get, so I get what Carol said. What I don't get is the, and you have to explain this to me, Ben, the value of looking at the command line git

[00:25:59] **Carol:** diff. I can't use command line git

[00:26:02] **Ben:** diff. I'm not saying, sorry. I'm not saying you have to look at it on the command line. I'm saying just look at it in two different contexts.

[00:26:07] **Ben:** The command line happens to be the one where I look at it first, because I just happen to use the command line to do my git branching and my git diffs and that stuff. Yeah, I do

[00:26:15] **Tim:** too, but the diff never really looks like anything to me readable. Right. It looks great to me on GitHub, but doesn't look great to me on command line.

[00:26:24] **Carol:** I need it pretty in visual for

[00:26:26] **Adam:** me. Yeah, me

[00:26:27] **Ben:** too. I, a hundred percent. I don't, I would say that I consume the PR much more effectively in GitHub, but there is a gesture for me in being able to like, um, a git diff dash dash stat, which, which we'll just list out the files and then doing the full git diff and then be able to just like quickly hit the space bar to run through it.

[00:26:45] **Ben:** It's almost like it gives me a. An emotional bird's eye view. I don't know. I can't explain it. I, I, as I'm saying is I think just being able to see your PR in two different contexts, I think it's just getting your brain to work in two different

[00:26:58] **Tim:** ways. So give me an example of something you found using git diff on the command line that you said, all right, I need to change this before I push this up and look at it in GitHub.

[00:27:08] **Tim:** Well, I

[00:27:09] **Ben:** mean, it's hard, it's hard to compare to your approach only because it's a little bit... I'm

[00:27:13] **Tim:** not asking about my approach. I'm asking what you have done.

[00:27:15] **Ben:** No, no. What I'm saying is that the things that I would catch on the command line are probably also the things that you would catch in GitHub. So I'm not saying that it's allowing me to catch something that I wouldn't catch on GitHub.

[00:27:26] **Ben:** I'm just saying that it's a different perspective on the same thing, which I think

[00:27:29] **Adam:** has a value. What I'm hearing is that by looking through different lenses at the same thing, it kind of forces your brain to switch modes and you see things differently. You might catch things in one context that you're not going to see in the other.

[00:27:45] **Adam:** Right.

[00:27:45] **Ben:** It's because it's the experience is completely different. If you think I'm going from my Sublime Text, which has beautiful syntax highlighting and color coding, and then I go get diff on the terminal and suddenly it's Just red and green on black background. And that's showing me a different texture, if you will, of the diff.

[00:28:03] **Ben:** And then I pushed it up to GitHub and now it's back to a beautiful syntax, but now it's a side by side comparison as opposed to, for example, a stacked comparison that you get in the, in the terminal. So it's just, you just catch something different. I think you just, you just think about things differently, just momentarily.

[00:28:18] **Ben:** I'm not saying that I spend even minutes looking at the terminal. I mostly do just a quick once over. A quick cursory glance. Yeah. To make sure that. There's nothing crazy that just pops out to me, and then I push to GitHub, I go to GitHub, I create the PR, and then I review the PR there.

[00:28:33] **Tim:** I'm trying to think what value that would have for me.

[00:28:36] **Tim:** The only one would be if I were concerned about what I put in GitHub, because once, once it leaves your local, right, that's up there. If you need to change something, you got to fix it there, and people can see that you fixed it. So if I were concerned about that, which I'm not,

[00:28:50] **Carol:** I'll tell you straight away.

[00:28:51] **Carol:** I'll have 10 commits in one day,

[00:28:52] **Ben:** it's fine. Yeah, I'm a dash, dash force all day.

[00:28:56] **Carol:** See, we can't force anymore. Damn it.

[00:28:58] **Ben:** No.

[00:29:01] **Tim:** So, so I, I would say based on what you said, unless you can make a better argument, I don't, I don't see any value doing it. That, that first one. That's fair. That's fair. I'm going to catch it, I'm going to catch it in GitHub or Bitbucket or whatever I'm working in.

[00:29:14] **Tim:** So doing that extra step of doing the stat and then the diff, I'm like, I'll catch it later. I don't need to do that extra step. I think that's fair.

[00:29:22] **Carol:** And to me, I feel like I always do two checks because I don't push my branch until I've reviewed it. So I look at everything, I go through my, what I have. And then I make sure that the correct code is staged.

[00:29:37] **Carol:** And then I commit, put my nice, pretty message in there. And then I push and I do the second compare. I feel like most people do two compares always, and maybe don't even realize you do it. But the stage

[00:29:47] **Tim:** isn't, I'm sorry to interrupt you, but the stage isn't comparing the code changes. It's comparing

[00:29:52] **Adam:** the files.

[00:29:53] **Carol:** In Sourcetree, it does, because when I click on it, it gives me the diff view at the bottom right hand corner. It says, okay, here's what it was before, here's what it was after. I can stage by honks, I can stage by just lines, and I can discard. I mess up by constantly turning off whitespace, um, show whitespace, because I don't want to see it all, like, just garbled in there.

[00:30:14] **Carol:** I only want to see my real changes. And that's when I forget to undo it, and I push it up, and now my changes that would have fixed the whitespace issues aren't in there. So, it's another commit.

[00:30:24] **Ben:** Alright, let's carry on then, because there's a number of these. Two!

[00:30:28] **Tim:** We spent a lot of time on

[00:30:29] **Adam:** one. Trim that one down, Adam.

[00:30:31] **Adam:** Oh yeah, I will. I'll cut out everything Tim said.

[00:30:34] **Ben:** Don't! Alright, the second one I think is, should be short and obvious. Let's see. Oh man. But always look at the comments that people left before you merge your PR in. What do you mean? Yeah. Like if, you know, you create the PR, you have someone review it, that person can leave comments on the PR.

[00:30:52] **Ben:** Oh, and, and, uh, at least on GitHub, I, I, I don't know, but yeah. And the reason I think that's worth calling out is because not every comment blocks the approval of a PR. So just because your PR gets the thumbs up doesn't mean that there are things that might need further

[00:31:09] **Adam:** consideration, right? You can leave a comment and then also approve in the

[00:31:12] **Ben:** same action.

[00:31:13] **Ben:** And then there are a lot of, let's say, stylistic differences that you might have with the author of the PR where you might leave a comment and say, Hey, Did you consider this? Or, hey, you're using a really old style of coding or, hey, did you know that there's a built in function that does the same thing that you just did here?

[00:31:27] **Carol:** Right. Like what you wrote so good, but there may be a better solution or better.

[00:31:32] **Ben:** What you wrote is not going to break, so good for you, but you might want to consider changing it, and if you don't, I don't care. And maybe you want to do it in a subsequent PR because that's just not a priority right now, that's fine.

[00:31:43] **Ben:** But just because a PR is approved doesn't mean that there aren't comments worth reviewing.

[00:31:47] **Tim:** Yeah, in our PR comments, so because we're dealing with the credit card data, everything has to be, we have to review the OWASP top 10 every time on everything we're changing to make sure that it's not breaking the OWASP.

[00:31:58] **Tim:** So that is the place where we put those comments. Typically, Everyone's going to say I passed it all, but you still got to look at it because auditors are going to look at it. Then you have to also look at the code. Yeah, definitely. I agree with that a hundred percent.

[00:32:09] **Ben:** All right. We're off to a better start.

[00:32:11] **Ben:** Good job. Just start with that one. All right. Number three, this is probably going to be more team dependent, but the way my team works is what is in the main branch should match or is about to match what's in production, meaning you never merge into the main branch, something that's going to sit in a local development environment.

[00:32:30] **Ben:** Or in GitHub for some period of time that is not minutes in length so that you can always be confident that what is in production matches what's in the main branch when you have to understand why a production system is behaving a certain way, right? You don't want to have to go look and deploy logs to see what Git hash had been.

[00:32:48] **Ben:** Release to production. Oh, I see what you're saying. Your main branch should be the evidence of what's in production. Do people do

[00:32:55] **Adam:** that? Yeah. Um, yeah, no, I, I completely agree. And I think the way that we work that enforces that is merging is part of the deploy process, right? Like we do the code review and everything's happy.

[00:33:06] **Adam:** And then the moment that we're ready to deploy, that's when it gets merged. Right.

[00:33:10] **Carol:** Our, our merge into main is what pushes it to the server. So I didn't realize that. I mean, I guess you could have main sitting there without it being like, without it being released to the actual server physically.

[00:33:22] **Adam:** Yeah. Yeah.

[00:33:23] **Adam:** If you don't have that automation. I forgot that's a thing. Ouch.

[00:33:26] **Ben:** And then sort of dovetailing with that is this idea that I think some teams will build up a number of commits in main with the intent that we're going to deploy a bunch of commits together. And that's, I don't understand that personally, but that I think is a strategy that some teams have.

[00:33:41] **Adam:** I see it as the approach that you kind of have to use if your deploy process takes a while, right? If it takes you an hour to do a deploy for whatever reason. Then you don't want to do that nine times a day. You want to do that, you know, maybe twice a day. So I mean,

[00:33:55] **Carol:** I guess I could see if we're talking a day's worth of buildup, like everyone's getting all their stuff in for maybe over a day process because like you said, it takes a while.

[00:34:03] **Carol:** But I think outside of, I would say a day, you shouldn't be, it shouldn't be off that far. Like I can't imagine trying to debug something and not knowing what's on my server. I

[00:34:12] **Adam:** agree.

[00:34:13] **Ben:** All right. Next one, which I think sort of dovetails with this one as well, is that no one should deploy your code, but you, meaning that you're the only one who understands the changes that you've made, which means that you're the one who has the instinct.

[00:34:30] **Ben:** For what graphs, you should look at what metrics you might wanna look at, what type of errors might start showing up in the logs. Now you could argue that a lot of this is maybe automated, but Right. I, I think that, I just think that you, the author of the code is the best positioned person to understand the possible effects of code hitting production, and they should be the ones doing the deploy.

[00:34:50] **Carol:** Can I say no to that? Big no. Sure. Yeah. Yeah. So I would disagree because I feel like people, too many hands in the pot is a bad idea too. You're going to have too many people deciding on changes that shouldn't be there. I feel like the best solution is that you, like what we do where I'm at now, we get in, um, a Slack thread.

[00:35:08] **Carol:** Everyone whose code's going up, we deploy each package. When your package goes out, you check it, make sure things are good, and then you move on. I physically never push a button. I can't put anything into our main branch. I can't push, I can't do, so I mean, the release does it, we check it, and we're good to go.

[00:35:25] **Carol:** But as far as having the authority to actually put code in, I think that's a bad idea. So, okay,

[00:35:31] **Ben:** let me rephrase that, because I think we're fundamentally saying the same thing, I'm expressing it. Okay. I'm expressing it in a way that our team uses, but what I mean is the person who authored the code should be present and actively engaged with the deployment.

[00:35:46] **Ben:** Yes, I agree

[00:35:47] **Carol:** with

[00:35:47] **Adam:** that. Yeah, you do the validation. You're the only

[00:35:50] **Carol:** one that's going to know if you broke the merge, like if the code didn't merge right, because it may auto merge perfectly fine, but yet it made changes that were not part of what you were expecting to change.

[00:36:02] **Ben:** Right, like, I guess what I'm arguing against is this idea, one, that you would put something in main and just walk away.

[00:36:09] **Ben:** And then maybe someone else happens to deploy it later. But even on a similar note, Carol doesn't merge something into main and then goes to Tim and says, Hey, Tim, I gotta run out to a doctor's appointment. Can you deploy this for me? Like, no, Carolee, you can deploy when you're back from the doctor's appointment.

[00:36:24] **Ben:** Like, you should be there for the

[00:36:26] **Tim:** deployment. So let me give you an opposite. Okay. So PCI, which credit cards, you know, we have to follow PCI compliance. The person who writes the code. Cannot be the same person who deploys the code, cannot be the same person who reviews the code.

[00:36:41] **Ben:** Really? I mean, I, the review I get, but I'm surprised about the deployment.

[00:36:45] **Ben:** The review,

[00:36:46] **Tim:** yeah, so it has to be a separate entity that deploys the code. Fascinating. So that is absolutely a non starter for me. So we, we have to build our things in such a way that, so what I will, what we will do is I will merge it into main. I will locally build it. To make sure it compiles correctly.

[00:37:05] **Tim:** This is a Scala thing, so it's a compiled code. And then I run my test to make sure it works. And then the other entity, which is our infrastructure team, they have to deploy it separately. And that's just for separation of concerns so that you don't have a person, a bad actor who is introducing code to steal credit card information, and then they review it and approve it, and then they deploy it.

[00:37:25] **Tim:** So I absolutely cannot do that. So we have to build our entire pipeline around that assumption that the person who's writing the code doesn't deploy it. The only thing we can do is because everything is load balanced, is we can deploy it to a node. I can individually check each node and do a smoke test to make sure that everything works.

[00:37:41] **Tim:** I know what could possibly break based off what was being deployed. Check that and then say, okay, put that in rotation. And then we go through all the nodes and update all those so that there's zero downtime.

[00:37:50] **Carol:** So they couldn't even do their own smoke testing. Who the person who wrote the code. No, the

[00:37:55] **Adam:** person who wrote the

[00:37:55] **Tim:** code can do the smoke testing.

[00:37:57] **Tim:** See, to

[00:37:57] **Carol:** me, that, that validates kind of what Ben's saying. Like, to me, that's enough. Like, I've validated that what went in is good, even though I didn't push a button.

[00:38:05] **Tim:** But he's using the word deploy. So deploy to me means that you are the one who is putting the code in production. And that is, that as a separate concern that

[00:38:13] **Ben:** I can't do.

[00:38:14] **Ben:** Yeah. And I think cause where I work, that is when we talk about deployments, it is actually someone hitting a button. So there's, we don't have examples where I am of a group of people being engaged in a deploy that's being led by one person. But I think that's the intent of that feels the same. Okay.

[00:38:30] **Adam:** Yeah. I think what you proposed, Tim, agrees with when Ben rephrased after Carol's feedback, say everybody's names. Uh, yeah, he was saying, you know, the developer is actively engaged in the process of validating the deploy. Right. Validating, but

[00:38:44] **Tim:** not deploying it.

[00:38:46] **Adam:** That's fair. It depends on, yeah, your, your different requirements, but I don't even have access

[00:38:50] **Tim:** to production environment because of the, if I'm the one working on the code,

[00:38:54] **Adam:** but that is specific to your industry, right?

[00:38:56] **Adam:** So that doesn't necessarily mean that that should, by definition, be true for everybody

[00:39:00] **Carol:** all the time. True. Yeah. I feel like we should throw the caveat in there that I'm FinTech too. So like the whole finance market is us too. So a lot of those same regulations are interesting. And why I can't touch things.

[00:39:11] **Ben:** I think for our SOC compliance, we have to have someone else review the code. And I think that's kind of the extent of the deployment requirements. Other than people just not having general access to production. All right. I think the next two might be a little bit more controversial. Code completed is more important than code being written, which means that if you have an open PR on your team, someone should make it a priority to review that PR because that is completed code, ready to be deployed, ready to add value to a user, which means that.

[00:39:46] **Ben:** If a PR sits around open for, I'm just going to throw out an arbitrary number, more than an hour, your team has failed to review that PR.

[00:39:55] **Tim:** So explain to me what completed means to you in your world.

[00:39:58] **Ben:** Theoretically

[00:39:58] **Adam:** ready to be deployed.

[00:40:00] **Carol:** Yeah, I mean a pull request only goes up when it's ready to be merged into main.

[00:40:03] **Carol:** So I only put the pull request out when my code's done, it's ready for testing. Which for us is actually not necessarily into production, it's when we hand it over to QA for testing. But I don't hand my code over to QA until the pull request gets approved. I wait because sometimes people come back and are like, Hey, what'd you think about that?

[00:40:21] **Carol:** And I don't want to waste QA's time testing.

[00:40:23] **Ben:** And, and, and I guess one thing to clarify too, is that a pull request can act as a good foundation for a conversation with other people, which means that if you, if you push up a PR and the basis of that PR is, Hey, I'd like to review this with you to get some feedback.

[00:40:40] **Ben:** That I think is a different gesture than, Hey, I have a pull request. That's ready to go. I need someone to review it. Right. That's code

[00:40:47] **Adam:** complete. Right. So, to comment on your original assertion that a pull request, some arbitrary number, but a very small number, like if it's been sitting there for one hour, that's too long, I can imagine a context in which that makes sense to have just as sort of a general guideline for the team, but I can also imagine a context because I work in a context where I don't think that is a good fit for our team.

[00:41:07] **Adam:** You know, my whole company, including non developers, is five people. And on any given day, the three full time developers and one part time developer might all four of us be working on different high priority projects. And so, the context switching involved in stopping what you're doing to review somebody else's code.

[00:41:26] **Adam:** is maybe too high a price to pay because the feature could wait until tomorrow to be deployed. And so if I finish my day by reviewing your pull request and you finish your day by reviewing mine, then we have two features that are ready to deploy at the beginning of the day tomorrow that cost nothing essentially in context switching because neither of us was trying to go back to anything when

[00:41:45] **Ben:** we're done.

[00:41:46] **Ben:** That's interesting. I, I would, I would say that in my experience, people have trouble moving on from a pull request that is done. Meaning, if I have a pull request or my teammate has a pull request that's completed, there's almost an emotional break. Yep. Where they can't now go work on something else.

[00:42:09] **Ben:** Cause they're like, but I got this code and it's done and it needs to be deployed. So it's like, they, they mentally can't let go of that and then open their minds up to working on something else. Yeah, you have to,

[00:42:22] **Adam:** when you do that, you unload that information, that context from RAM and it becomes harder to come back and, and put yourself back in that state of mind when somebody does have feedback.

[00:42:32] **Adam:** I get that.

[00:42:33] **Tim:** Could I ask you to define where is it expected to be deployed? Is it to like a development staging server or production? Uh, I

[00:42:41] **Ben:** mean, in my team's context, we only need PRs for production. We can deploy to staging without PRs.

[00:42:47] **Tim:** Okay. Well, that's a little different because we do pull requests to like, like a staging.

[00:42:52] **Tim:** So they, cause we need that early review for OAuth 10 kind of thing. Launching to production really is just taking everything that we have and merging it into the main branch. So we're reviewing everything that's going in the lower branches. So it's not the immediacy that is needed. Some stuff can pile up in our context of it's not going to production anytime soon.

[00:43:12] **Tim:** So let's, they can pile up and plus, you know, like Adam said, it's a smaller team for us as well. It's like, I could be in a meeting for an hour, so I'm not going to get to your, your pull request that hour. Um, I'll get to it, but yeah. But I

[00:43:24] **Adam:** think that there's a, a kernel of truth to what Ben is saying is that you don't want to just let something die on the vine either, right?

[00:43:31] **Adam:** Yeah, I, I agree with that.

[00:43:33] **Carol:** Yeah, definitely. I think you should have a, a set limit. I just don't think an hour or even a day would work for us. But like Tim said, what we do, and I think I mentioned it already, is that we, we put the branch up and our QA team actually checks out our branch on a server, on a sandbox, and that's what they test with.

[00:43:51] **Carol:** So mine's not going into production. And if it is something like we had a bug today that did need to go to production today, well in Slack, it's all tied together. So when the pull request went up. I just clicked the nudge button. There's a nudge button? There's a nudge button. I have a nudge button in our Slack channel.

[00:44:07] **Carol:** It's part of JIRA. I think it's JIRA or Bitbucket, one of the two. I can tell you in a minute, but yeah, it just nudges everybody on it. All right,

[00:44:15] **Ben:** next one. And again, this one might be more team dependent. And again, I'll caveat all of this with saying that this is how I feel my particular team works well and everybody's mileage may vary.

[00:44:25] **Ben:** So next one. Pull requests are not the responsibility of an on call engineer or a hero engineer, but they're the responsibility of all members on the team. And whoever can get to the PR first, or whoever is, let's say, has the particular skill set for reviewing a PR, that that's their responsibility. I know some teams operate on this rotation, where it's like, Joe's doing all the PRs this week, and then Steve's doing all the PRs next week.

[00:44:49] **Ben:** Like, no, everyone's doing the PRs all the time. Yeah, I've never

[00:44:53] **Carol:** been on a team like that where you took rotation. Ours is skillset, number one, and availability. So, and there's two people on the team. One of them have to approve everything for just sign off. So the lead and the engine, the director of engineering.

[00:45:07] **Carol:** So one of them have to be on sign off. But other than that, we go based off of who knows the area I'm changing the best. I'll put three or four people on it. And then I add a couple people who I think don't have light load, like heavy loads, and then once I have three sign off, off it goes.

[00:45:21] **Adam:** All right. Yeah.

[00:45:22] **Adam:** I

[00:45:22] **Tim:** mean, I mean, sometimes the review might be not my area, right? Yeah, I agree there. Maybe, maybe at so and so should look

[00:45:28] **Ben:** at this, right? And, all right, not all these are controversial.

[00:45:30] **Carol:** Awesome. I, I agree.

[00:45:31] **Adam:** Yeah. Nope, I

[00:45:32] **Tim:** totally agree.

[00:45:33] **Adam:** How about you, Adam? Can you repeat the question? , , not that I wasn't listening, but I, when you started talking on, and I went down this rabbit hole, and I've forgotten the original question,

[00:45:44] **Ben:** I, I just, that the PR is the responsibility of the team, not of any on-call engineer,

[00:45:49] **Adam:** for example.

[00:45:50] **Adam:** Okay. Yeah, I mean, I agree. It's tough to translate a lot of this to us because we're a smaller company. And I mean, I've worked on bigger teams before, but that was the last job I had was gosh, almost 10 years ago. Trying to remember if we were on Git or if that was all subversion.

[00:46:04] **Tim:** If I can repeat what I think Bit is saying is like, sometimes there's a designated person.

[00:46:09] **Tim:** It's their job PR, right? Rather than the team. Right. Yeah. And so in that case, that person reviewing it, they might not know anything about it. So they're just rubber stamping it. So really you need to have everyone involved on it. Even if some of them might not, you know, so even on a small team, you might have some people who only know a certain section of the code.

[00:46:27] **Tim:** They see a PR and realize, this isn't my wheelhouse. And they defer to the other person. But if they're the one on call, they're the only one who can approve it. And they're like, well, it looks good to me. I don't see syntax errors. I don't see, you know, XSS, you know, injection code. Here's fine. Stamp it.

[00:46:42] **Tim:** Let's go. Yeah. I think that's what you're saying, Ben. Yep. Yep. I think so.

[00:46:46] **Ben:** All right. Kudos. I totally agree with that. All right. This one, this next one seems strange, but something I've actually run into before. Never review a PR until you're actually asked to review a PR. I know that sounds crazy, but if you think about there are all kinds of integrations that people have where new PRs show up in Slack channels or you get alerts from them or something.

[00:47:06] **Ben:** People use. PRs for different reasons. Like we're talking almost at the top of the show, I like to review things in different contexts. And one of those contexts is the PR you're talking about. You might push a PR and you find changes and then you need to go back and make changes and you're pushing the PRs again.

[00:47:20] **Ben:** Um, the PR is not a meaningful piece of work until someone goes to you and asks you to review it. Which if I can then add one more addendum to that, I think GitHub recently added this ability to mark PRs as being in draft mode, which to me, I'm like, that solves no problems because it was in draft until I asked you to review it.

[00:47:41] **Adam:** So I was actually thinking about draft mode when you were talking about the, when you would want to create a pull request for the purpose of having a discussion with somebody to show them your code and get their feedback. I think that would be a good use case for the draft mode so that somebody doesn't come along and say, Oh, okay, I'll, you know, I have some time now.

[00:47:57] **Adam:** Uh, I'll go ahead and review this.

[00:47:59] **Ben:** I hear you. That sounds almost more like miscommunication happened. But,

[00:48:02] **Tim:** I mean, draft mode sort of says, Yeah, I know it's not fully complete yet. I still want some feedback. I don't fully expect you to pull this into that, but I get your, I mean, that's sort of an ambivalent state.

[00:48:12] **Tim:** It's not really a pull request. It's sort of a, hey, look at this request. It's still a draft, which if I'm not paying attention to my white space, that's probably what

[00:48:19] **Adam:** I'm

[00:48:19] **Carol:** doing. Our, um, kind of common agreed upon thing is once the pull request goes up, if there's no reviewers on it, then, you know, it's sitting there because people are just having conversation.

[00:48:30] **Carol:** So, if there is a reviewer on it, then sure, like, if we've added 3 or 4 people on it, then it's open and ready to go. But if it's just created, but there's no reviewers yet, then I'm having a conversation on the side, and someone's pulling my branch, and we're going to make some changes together, or we're just going to talk it through.

[00:48:45] **Carol:** Once reviewers go on it, we're

[00:48:46] **Adam:** good to go. So when you say reviewers on it, do you mean an assignment of a reviewer? Or, okay, so you're not talking about the completed review? No, no, no. I'm

[00:48:53] **Carol:** talking about the pull request went up and I hit the create button and now it shows sitting there and people can approve it, but there are physically zero reviewers on.

[00:49:04] **Carol:** I can still decline it at that point, or I can just go hit the edit button and add reviewers once I know that I'm ready to go with it. So you use

[00:49:10] **Adam:** that, uh, in GitHub, it's request review. I don't know what it is in Bitbucket, but specifically sort of send this to somebody, notify Tim, I'd like you to review this, please.

[00:49:19] **Carol:** Yeah, I only push it up once I'm having a conversation with someone, so I just grab the URL. Post it in Slack. Go to this link. You

[00:49:26] **Adam:** said that earlier in a different, uh, one of Ben's commandments about not pushing until you, like, you're ready for review. And the thought went through my mind at that moment, and it just reminded me that I push almost every time I commit.

[00:49:36] **Adam:** Hmm. Because I, I, I view that as an insurance policy. Oh yeah. So, If my house were to get hit by a nuclear bomb between commits, like, somebody's gonna have the access to my branch there, right? Like...

[00:49:48] **Carol:** And see, I'll push my branch, but I don't push to the pull request. Mm hmm. Right. Like, I don't put in pull request early.

[00:49:54] **Carol:** Yeah, I

[00:49:54] **Adam:** don't create a pull request, but yeah, I push my branch up.

[00:49:57] **Carol:** Well, sometimes I actually don't. I take that back. Undo what I just said. I don't push that often.

[00:50:02] **Adam:** I

[00:50:02] **Ben:** push all the time. All right, this next one is not going to be true 100% of the time, but I think it should be true more often than it is false.

[00:50:10] **Ben:** Your PRs should be small. I feel like if it takes someone more than 15 minutes to review a PR, you have way too much stuff in it. You have not decomposed your problem into smaller problems. Effectively. Wrong.

[00:50:25] **Adam:** So I'm going to have to disagree. I think the, I think that I can understand why you'd say that because you have the feature flag ability to like deploy codes, you know, make a pull request and deploy code and have it be literally dark, right?

[00:50:38] **Adam:** Like not reachable and the rest of the world that doesn't have that privilege. You know, when we deploy a new feature, that feature is going out and it's, if it's not reachable, it's executable, right? Like you might not have a URL hooked up to that service method or whatever, but it's, it's there and it's hot.

[00:50:53] **Adam:** And I think as the author of many enormous pull requests, uh, you know, there, sometimes there's just no getting around it. Like, you know, you're, you're adding this whole. I was starting to say, like, you know, you're adding a whole module and it's got a whole bunch of different features and I get that, like, maybe the argument against where I was going is that, okay, well, maybe you should be deploying more often so that you have, okay, just the home page of that module is visible and then you deploy another feature later that's, you know, the The reports view and another, another deploy for each individual report as you, as you work on them sort of thing.

[00:51:26] **Ben:** But the feature flag, I mean, you are right that my team operates heavily with feature flags and it does change the calculus, if you will, of when things can go out. I will say, I

[00:51:35] **Adam:** wish that I could agree. If I had a reasonable expectation that no pull request review will 15 minutes. Then I would be much more inclined to agree with the idea that pull requests should be reviewed more or less immediately.

[00:51:49] **Ben:** Ah, that's interesting. Okay. That makes sense. I love

[00:51:52] **Tim:** that. I think that because the pull requests that we're doing aren't associated with production, ours are typically smaller. They can be big, to be honest, but they're typically smaller. Because they're reviewed before they're going to production. So there's, it's more a unit of work kind of review rather than it is an entire feature review.

[00:52:10] **Tim:** Does that make

[00:52:11] **Adam:** sense? Yeah,

[00:52:12] **Carol:** I think so. So like each one of your like smaller sets of work is its own branch or something? Yes, I guess. That's where I struggle is I end up with one branch that's containing like. You know, all this big work we were doing, like the core logic is in the base branch. So then I can't do a pull request on each commit, I don't think.

[00:52:30] **Carol:** So it's hard to break out sometimes the big features if you don't have like, you know, the functionality that you were talking about with releasing smaller subsets of work.

[00:52:38] **Ben:** Yeah, I think that's, that's, it's, you guys are making a good point. I think because my team has the ability to deploy things that aren't necessarily activated per se, it can change the way that things are done.

[00:52:50] **Ben:** Which is why we need an episode on that. Oh my God, please. So ready. I'm ready. 24 hours a day, I'm ready. So ready. This is just sort of a asterisk here on this statement as well, is that if you have a large sweeping change that isn't necessarily functional feature related, I would try to always do that as a completely separate deploy.

[00:53:08] **Ben:** Meaning you're upgrading a framework or Adam's talked about. I'm coming into a project. I need to apply prettier to this project. That's never had it before. Like you're doing that as its own deploy. Sure. That makes sense. And like, you're not doing that plus feature work in the same PR. No, no, no, no.

[00:53:23] **Adam:** Yeah, that's evil.

[00:53:24] **Adam:** All right. Can I jump in and throw out one of my own here that I just thought of? Oh, please. So if you're working on, like say, a feature branch, and while you're working on that, you kind of come up with this, either maybe you're fixing a problem, or you come up with some other separate feature, but that secondary idea that, and this has happened to me many times, like I'm working on a feature and I come up with this other thing that I need to do, and that My, the feature that I'm working on, my project can benefit from and so often it's so tempting to just sort of slip it in with that feature that I'm working on and then for whatever reason like maybe that project has to go on a back burner because something urgent came up or something like that and then all of a sudden you find yourself like needing that feature elsewhere and so I guess the thesis of my commandment that I'm adding here is that in that situation you have to have the diligence to set your branch aside And go off and create another branch for this separate feature so that it can be reviewed and deployed separately and so that then you could rebase or merge it into your feature branch as well if you need to make use of it there.

[00:54:23] **Adam:** Yep.

[00:54:24] **Ben:** One thousand percent. Agree.

[00:54:25] **Adam:** Yeah, that's a good point. Have you guys all been bitten by that as well? Oh yeah,

[00:54:28] **Ben:** definitely. Yeah, definitely. And I would add that I think another expression of that. is that sometimes I will start a feature that I think is a manageable sized feature, and then I realize it's actually much bigger than I thought of, and I will then see if I can stop and be like, well, actually, I can do this smaller part as its own thing, deploy that, and then be able to come back and do this other thing.

[00:54:51] **Ben:** And I know that sounds like a feature flag type thing, but here's a very, very recent non feature flag thing is we used to use a service called Optimizely, which allowed us to run, I guess, sort of AB style testing in their application. We stopped using it a couple of years ago, but there was still a lot of code left in the application that used.

[00:55:10] **Ben:** It was a sort of a dynamically injected JavaScript file and there was a lot of code that would check to see if this object existed and do certain things. So I had created a ticket to just remove all of the Optimizely code. And as I started to get into it, I realized that there were huge experiments like over here for signups and then over here for onboarding and over here for tours within the application.

[00:55:32] **Ben:** And as I started to see the breadth of this thing unfold, I was like, no, this is not one ticket anymore. And then I'd be like, all right, I'm going to set this aside. I'm going to rebranch off of the main thing. And I'm going to say, okay, this is just removing the optimizely onboarding experiment. I'd get that.

[00:55:47] **Ben:** Then I'd rebase my original branch or I'd go back to main and I'd say, okay, now this is just the experiment for the in app tours. And I would deploy that so I could start to deploy. The removing of optimizely incrementally once I realized it was a lot larger than I thought it was going to be.

[00:56:02] **Tim:** Yeah, because I mean, you have to look at it from the viewpoint of the reviewer, right?

[00:56:05] **Tim:** So if you're, if it's related to a particular feature or ticket that you have and you're doing all this other stuff that seems unrelated, they're like, what are you doing? What, what, what am I reviewing here? I don't understand the parameters that you're trying to fulfill here. I don't know how, what this code line here has to do anything.

[00:56:22] **Tim:** with this feature or ticket that you're working. So you're helping them out by not going rogue and saying, Oh, while I'm here, I'm going to do this, right? You say, no, I have the discipline. I'm going to stop, make another ticket, do another of that. Just do this work here if I can. So that way when they review it, they're not, they're not having to slack you and say, so you're working on this.

[00:56:40] **Tim:** Why did you delete all this stuff over here? Totally. I don't get it. What's your purpose? Particularly when you're dealing with financial systems, you're like, your intention was this. Why are you doing X and

[00:56:49] **Ben:** Y? I, I can't tell you how many times I'll see a PR where someone's working on a feature and then as part of that feature, they also go and like change the favicon that was included in a bunch of pages and they're like, Oh yeah, well, I just, I, I keep forgetting to do that.

[00:57:01] **Ben:** I'm like, well, then do that as its own thing. Don't open a ticket. Yeah, don't make me review three different things in one PR. I will

[00:57:09] **Tim:** say as an aside though, sometimes it's hard when you're working on, trying to work on multiple things and you're on a commit and you're like, oh, I'll just change this here too.

[00:57:15] **Tim:** It's like, oh crap, I just really combined a couple things on this. Um, I don't know how to undo this. I'm just going to push it up and put a comment and say, you know, I explained why I did it, right? I mean, sometimes it's really hard when you're context switching between. Between issues, to put everything in the right committ.

[00:57:31] **Tim:** We're not perfect. So, I get that it's not a

[00:57:33] **Adam:** perfect world. Yeah, I mean like sometimes adding a feature requires a slight page redesign. Right. And so then you have the question of like, okay, well now do I do a pull request first to make the page redesign to support the feature that I will be adding next time?

[00:57:46] **Adam:** Or do I add the feature in a way that kind of looks ugly and is shoehorned into the current design, and then come back and do the redesign later? Or do I just do

[00:57:53] **Ben:** it all at once? I think, to me, and this is just an opinion, that feels cohesive enough to me. I'm talking about things where like, someone will be redesigning the login page, but then also changing the JVM settings.

[00:58:06] **Ben:** And you're like, well, That's totally

[00:58:08] **Carol:** unrelated. Yeah, because then I'm sitting there researching, trying to figure out why you made that change, and why I don't understand how what you changed, like, relates to the login. And I feel like an idiot. I will

[00:58:19] **Ben:** say that sometimes having a PR that is explicitly a collection of small changes, I think that's okay.

[00:58:26] **Ben:** Like, you get to the end of the week, and you have a bunch of little tickets that were sitting around, and you're like, Each of these tickets is four lines of code. I'm just going to knock them all out together. And then the PR is a collection of small changes.

[00:58:37] **Carol:** So that doesn't, yes, it's pretty, like I could see it happening, but that doesn't work so well when you need to hand all four off to QA for testing.

[00:58:45] **Carol:** And now one's approved, three hasn't even made it to a QA yet. That one's ready to release and you have to tell them, no, it can't go because now I'm holding three other working items in there with it. So you definitely have to make sure you're balancing what can go out to. Yeah. Yeah. No,

[00:58:59] **Ben:** that's a great point about QA.

[00:59:01] **Carol:** So, we all agree you should be doing code review and pull requests. All right. Even if you're not doing what's technically a pull request, you should at least be doing code reviews, like, before you move code into production.

[00:59:11] **Adam:** Yeah, absolutely. I agree it is necessary. I will also admit that as a, an administrator on our GitHub account, I have for certain repos, the ability to bypass the, uh, review requirement.

[00:59:25] **Adam:** And in a pinch, I will use it. I get a review if at all possible, but you know, if it's the middle of the night and I'm fixing a bug and you know, it's a one line thing is semicolon got forgotten somewhere. Like I'm not going to wake somebody up to get a code review. And I'm adding a semicolon where there was one obviously missing.

[00:59:40] **Adam:** I'm just going to do it. Or I'm not sure whether or not I want to admit this. I was going to say, you know, sometimes I'll just remote desktop onto the server and change it right there. It's not even in the repo.

[00:59:53] **Tim:** You just get conflicts.

[00:59:54] **Ben:** Um, how about this? How about if I just read the last few and then any discussion that's worth having, we can have, yeah, let's do it.

[01:00:00] **Ben:** All right. You should clean up your PR before you have it reviewed, meaning that if you have a bunch of crap still working on it, or this isn't working, or trying something new, your commit log should not be an expression of the development process, it should be an expression of the evolution of the application, and commits like Crap, it's still not working.

[01:00:22] **Ben:** That doesn't express the evolution of the application. That's just noise that went through your process locally. So I'm a huge fan of squashing or rebasing, however you do that kind of stuff.

[01:00:33] **Adam:** I need to get better at that because I would tend to agree with you, but I have many commits verified to my name, uh, that are like FML or...

[01:00:43] **Ben:** And to be clear, I do have those locally. They just, that's not what ends up in the PR.

[01:00:48] **Carol:** I try my best not to, but sometimes when I squash or when I do make those changes, all of a sudden I end up with something bad happening and I lose my code. So then I'm like, hell no. You get my commits, nobody cares. We don't look at commit history anyways, really.

[01:01:03] **Carol:** Yeah.

[01:01:03] **Adam:** If I was going to push back on this sentiment at all, it would be that the commit messages are there for the benefit of the developers, not the product or the management team or anything. And so like, I agree with you in sentiment, but I think that it's not a critical path. Type thing. I

[01:01:19] **Tim:** mean, ultimately it's the final diff

[01:01:20] **Ben:** that matters.

[01:01:21] **Ben:** All right. Where possible and applicable, always include a screenshot or a GIF of UI changes. Don't ever expect someone to pull your code down and actually run it. That if there's a big visual change, you should have a representation of that in the PR. I like that. I

[01:01:35] **Adam:** just don't do it. I do it instead of a gif.

[01:01:37] **Adam:** I will often include a short video and then for anything that is not like worthy of rubber stamp, you know, not that we do rubber stamps, but you know, if it's at all complex, I will push it to one of our QA servers and, and I'll just be like, this is where you can go test it. You've fancy. So you don't have to do the work of, of, uh, merging yourself and, and all that and be like, I've done the work for you and here's U R L with a, a sample record where that has the problem that is fixing or whatever, and you can go see it for yourself.

[01:02:03] **Adam:** That's actually really good. I like that. Yeah. I

[01:02:05] **Tim:** like that. I might, I might adopt that. All right. Every

[01:02:07] **Ben:** PR should be associated with a ticketing system, whether that's JIRA for us or whatever ticketing system. I like the idea that everything links back to an external, I don't want to call it a source of truth, but an external indication of why this work has been done.

[01:02:22] **Ben:** And then you can depend on the JIRA system or the Basecamp URL or something to then provide further explanation as to why it's happening. But. I would say on the flip side to that, you should treat your PR message as if there is no external source of truth. That your JIRA system might not exist in two years.

[01:02:41] **Ben:** You may have moved on to Basecamp or someone's JIRA board may have been deleted accidentally. That your PR message should explain why you're doing the things that you're doing in the code.

[01:02:54] **Tim:** I look at the PR message as the, um, in internet speak, the TLDR. Yep. Right. The executive summary of what it is. But if you really want the dirty history, you go to the ticket, right?

[01:03:05] **Tim:** Because typically there's like comments from the developers, from QA, sometimes from customers, you can get the dirty history of why this thing happened the way it

[01:03:13] **Carol:** happened. I was going to say on. One recently I threw in one of the customer notes just because I knew that the PR was going to get not approved and there was going to be feedback from it because it went completely against what the original request was.

[01:03:27] **Carol:** And I was like, hey, but here's the conversation that says it's actually one day, not six days. So just know it's actually one day.

[01:03:34] **Adam:** I was originally going to say that I disagreed with this one because of the way that it's a blanket statement, right? You said every PR should have. An issue attached to it.

[01:03:42] **Adam:** And then you kind of rephrased and you said an external, would you say an external source of, source of truth? Truth or motivation or whatever. And that softened me on it because I was thinking, okay, well a lot of ours, you know, we will just link to the, we have a, a bug log, every exception gets logged. And so I'll link to those with maybe in a description of what the problem was and, and what I did to fix it sort of thing.

[01:04:03] **Adam:** Or we have a ticketing system in our product and we'll link to those. And then the only thing that that really left for me, Is like a new feature, new product, new module, whatever. And I mean, I guess at that point you could link to like the spec or you could transfer parts of the spec into a ticket. If you're going to create from that.

[01:04:20] **Adam:** I'm not sure. Yeah. Yeah. We have a story. Yeah, yeah, yeah. It depends on your workflow. We don't have a hard and fast workflow for new development of stuff. Sometimes it's in a Google Doc. Sometimes it's in a ticket. Sometimes it's in a spreadsheet because we're sharing that with a customer.

[01:04:35] **Ben:** And one thing that I would point out is that sometimes, for example, in the middle of an incident where you're doing emergency work, that you can always fill out your ticket later.

[01:04:44] **Ben:** Even if I have to deploy a hotfix in the middle of an incident, I'll create an empty ticket in JIRA, grab the ticket number, put it in the commit. So that later I can go into JIRA and say, we had an incident. I had to do a hotfix. Here's a link to the Slack message where this is being discussed in the incident channel.

[01:05:01] **Ben:** And then that way my PR almost retroactively points to something that's more meaningful. Right. I think that's a good idea.

[01:05:07] **Adam:** Yeah.

[01:05:07] **Tim:** Because, because yeah, the ticket itself is ongoing. It can, it can outlive the life of the, of the actual commit. Right. So if there's issues later, that ticket can

[01:05:15] **Ben:** document. Totes.

[01:05:17] **Ben:** All right. I think I only have like one or two left here. All right. This one, I don't know how to phrase this one exactly. The role of the PR reviewer is not to ensure the success of the code. That theoretically, unless you're sharing a PR specifically to get feedback and have a discussion, that you should be as confident in your code.

[01:05:36] **Ben:** Before someone looks at the PR as after they look at the PR, you don't ever want to think of your PR review as someone's going to catch the bug that you were worried might be in the code. That's not their responsibility. Their responsibility is to maybe catch red flags, to give you feedback on maybe architectural decisions, but you don't want them to be a safety valve essentially to the code that's about to go out.

[01:05:58] **Ben:** To be clear, they

[01:05:59] **Adam:** should, but you shouldn't be counting on it. Right. I

[01:06:02] **Ben:** think it's, it's too much. Um, Thank If a bug hits production, it's not because someone didn't catch your mistake, it's because you deployed a problem. I would agree with that. Alright, and last one. The names of your branches are meaningless.

[01:06:16] **Ben:** If you're spending time, like, trying to craft the perfect branch name, that's time wasted. No one looks at your branch name. If you want to put your ticket number in your branch name, that's up to you. But like literally no one is looking at your branch names. I would pick whatever is easiest for you to understand and shortest to

[01:06:33] **Carol:** type.

[01:06:33] **Carol:** But follow your team standard. Like we have to, there should be no standard. No, well, we do, we do because in JIRA on the right hand side, we have a branch section, and as long as you make the branch, that first part of your ticket number, which is like BP 12345. It'll always link on the right hand side. So I never have to go look.

[01:06:53] **Carol:** Oh, that's interesting. Same. If I go help someone, I pick up their work. I don't have to know what they named their branch. I just go to the branch section and click the branch and their branch is open.

[01:07:02] **Adam:** Yeah. So

[01:07:03] **Tim:** the naming convention is very important for, for us as well. So you have to have the ticket name because the ticketing system picks it up.

[01:07:10] **Tim:** It knows about, it knows about the commit when you commit it, because there's a connection between we use, um, we, we use JIRA and it's connected to the repo. So whenever you. Put that ticket name in it, it goes, this is part of it, and therefore it's in the ticket. See, I,

[01:07:24] **Ben:** I think that when we've integrated with ticketing systems, having the ticket number in the PR message, I think has historically been sufficient.

[01:07:33] **Ben:** I guess it, I, I think it might all, it obviously depends on the integration.

[01:07:35] **Carol:** Yeah, ours is all based off the branch and then any PR that opens against that branch is then associated to the ticket.

[01:07:41] **Adam:** I agree with your original sort of thesis was that. Like, if you're spending a bunch of time trying to think of what the perfect branch name is, that's wasted time.

[01:07:48] **Adam:** Don't do it. I

[01:07:49] **Ben:** think that's all of them. So I have, you know, just a handful of opinions about some stuff. It's not actually all of them, but I think it's the meaningful

[01:07:56] **Adam:** ones. Well, does anybody have anything else to talk about with pull requests and code reviews and stone

[01:08:01] **Tim:** tablets? No, I'm just, I'm just shocked that I had no idea we would go this long on this topic.

[01:08:08] **Tim:** Ben

[01:08:08] **Carol:** definitely had some feelings, huh?

[01:08:11] **Adam:** Strong opinions, weakly held. I think that's the key here. Okay, well, before we move on into Patreon, I told you guys earlier that we had our first iTunes review and I would like to read it to you now. Yay! What? A reviewer?

[01:08:27] **Tim:** Please be a hater. So

[01:08:27] **Adam:** excited. Please be a hater, come on.

[01:08:30] **Adam:** So this is by somebody named Jacob Fiff, if I'm reading that right. I apologize, the text size is kind of small and I can't make iTunes bigger. It looks like it's from Jacob Fiff. The title is super enjoyable and it says, I'm really enjoying this podcast. The format is great to listen to and it feels real as they talk about things that I can relate to having experienced.

[01:08:48] **Adam:** I'm always learning something new from listening, so thanks for your awesome insights and keep up the great work. And I'm going to click, uh, there's a little line under this that says, was this review helpful? I'm clicking yes.

[01:08:58] **Ben:** Yeah. Yes. That was awesome.

[01:09:00] **Adam:** Thank you,

[01:09:00] **Tim:** Jacob. You're not a hater, but I'll take

[01:09:02] **Adam:** it.

[01:09:04] **Ben:** Got the warm

[01:09:05] **Adam:** fuzzies. Thank you for the review. So, uh, if you guys think that we've earned it, please consider supporting us on Patreon. We have several people helping us keep the lights on in there, and we really appreciate their support. If that's something that you're interested in, you can find us at patreon.com/WorkingCodePod. There's perks available at different support tiers like an invite to our discord server, early access to new episodes, and our after show that we're getting ready to record. And basically what that is is we just keep the mics running for another 10 to 15 minutes and uh, sometimes we keep going on the same topic as the show, sometimes we talk about something totally random and different and sometimes secret.

[01:09:37] **Adam:** It gets crazy sometimes, yo. Our top tier on our Patreon is for people who want to pay a little bit extra for, I guess, little more than us saying their names on every episode in return. Like Monte Chan. Yeah, right now we only have one top supporter and his name is Monte Chan. So, Monte, thank you for your continued support.

[01:09:53] **Adam:** You beautiful legend. And for everybody else on Patreon and everybody that's, uh, not on Patreon and just listening, thank you. Thank you for listening. Thank you for everything. Without listeners, we'd just be four weirdos recording our conversations for no reason. Three weirdos. Yeah, I mean, we're still four weird weirdos, but we have a reason for recording our conversation.

[01:10:13] **Adam:** Anyway, on our way out here, don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts. Send us your topic suggestions on Twitter or Instagram at WorkingCodePod.

[01:10:29] **Adam:** We'll catch you next week. And until then, your heart matters.

[01:10:54] **Adam:** Okay. So before we move on, how many more of these you got? Cause it's, uh,

[01:11:00] **Tim:** it's almost 10. He isn't even yawning. He's happy.

[01:11:04] **Adam:** Did I not speak fluently? Is that why? Yeah. I'm going to cut all of that out. You're going to have like eight words.

[01:11:10] **Carol:** Yeah, can you just do it again, Tim? Start over. You look so sad.

[01:11:16] **Ben:** You know, it's funny.

[01:11:17] **Ben:** It's just, when I was listening to the last, the recording of the last episode, Adam at one point says something like, well, we didn't think we'd be talking for an hour, but we've already been talking for an hour. And I look at the clock and it was like 36 minutes into it.

[01:11:32] **Tim:** All my content, he cut all mine.
