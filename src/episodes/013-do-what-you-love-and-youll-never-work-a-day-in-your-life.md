---
title: "013: Do What You Love and You'll Never Work a Day In Your Life"
description: "This week, the crew talks about the privilege of being able to choose work that we truly enjoy. Not everyone has this opportunity; and, even when we do, loving your job doesn't always make it feel any less like work."
date: 2021-03-10
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/013-do-what-you-love-and-youll-never-work-a-day-in-your-life/id1544142288?i=1000512391275"></iframe>

A friend of Ben's once said, _"If you hate your job, you'll spend 5-7ths of your life waiting for the weekend."_ This is a dark way to think about existence. And, to address the flip-side of that coin, [Mingo Hagen][mingo-hagen] suggested that we talk about the phrase, _"Do what you love and you'll never work a day in your life."_ This is a significantly more optimistic view on the human experience; but, does it hold up to scrutiny?

This week, the crew talks about the **privilege** of being able to choose work that we truly enjoy. Not everyone has this opportunity; and, even when we do, loving your job doesn't always make it feel _any less like work_. In fact, as Tim illustrates with some scripture, the challenge and hardship of work can be what makes it lovable and fulfilling:

> Enter in by the narrow gate; for wide is the gate and broad is the way that leads to destruction, and many are those who enter in by it. - [**Matthew 7:13**][matthew]

Bringing a different sort of _scripture_ to the conversation, Ben shares one of his favorite poems, "Our Deepest Fear":

> Our deepest fear is not that we are inadequate. Our deepest fear is that we are powerful beyond measure. It is our light, not our darkness that most frightens us. We ask ourselves, Who am I to be brilliant, gorgeous, talented, fabulous? Actually, who are you not to be? You are a child of God. Your playing small does not serve the world. There is nothing enlightened about shrinking so that other people won't feel insecure around you. We are all meant to shine, as children do. We were born to make manifest the glory of God that is within us. It's not just in some of us; it's in everyone. And as we let our own light shine, we unconsciously give other people permission to do the same. As we are liberated from our own fear, our presence automatically liberates others. - [**Marianne Williamson**][marianne-williamson]

The conversation examined the "do what you love" concept from a variety of different levels, with each host coming at it from a different angle. What becomes very clear is that the quote means different things to different people. But, the one thing we think we can all agree on: _don't commit to work estimates that you don't believe in!_ Doing so will only make you your own worst enemy.

### Triumphs &amp; Failures

-  **Adam's Failure** - he spent many person-hours trying to reduce the size of a Docker container image. And, while he eventually reduced it quite a bit (mostly by moving to Alpine Linux), he wasted far too much time on what turned out to be a _simple little typo_ in his `make` file. The most frustrating part of all of this is that he _just assumed_ that the line-in-question _could not possibly_ be the issue; so, he kept debugging the lines around it without addressing the actual problem.

-  **Ben's Triumph** - he and a co-worker, Jackie Ewald, were recently called-out as the embodiment of "customer empathy" at work because they built a custom feature for one of their clients. What made this so rewarding is the fact that they **did not ask for permission** to build this feature; and, it was a feature that they almost-certainly _would not have been allowed_ to build had they asked for permission.

   Ben likes to keep this quote from Stephen Gates - the former Head Design Evangelist at InVision - on hand during all ideation meetings:

   > ".... for most companies, right now, because of the way their processes are—because of how afraid they are of so many things—the innovation that they need will probably not be authorized.... When I look back at all the work that was innovative, it was only innovative in hindsight—it almost got me fired on the way there."

-  **Carol's Triumph** - She's loving life in Lake Tahoe! Woot woot! Rock on with your bad self!

-  **Tim's Triumph** - as a manager, he usually finds himself in a constant state of "meeting". However, he recently blocked-off **7-hours of heads-down time** on his calendar so that he would not be interrupted; and, the amount of work that he was able to get done was refreshingly preposterous. He even received a compliment from one of his clients who thanked him profusely, at the end of the day, for everything he was able to complete!

   > **ASIDE**: Managers, consider this story when it comes to scheduling meetings for your engineers! We need focus time to get our work done!

### Notes &amp; Links

-  [Mingo Hagen][mingo-hagen] - listener who suggested the topic.
-  [Matthew 7:13][matthew] - _Enter ye in at the strait gate_...
-  [Marianne Williamson][marianne-williamson] - author of the poem, Our Deepest Fear.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[marianne-williamson]: https://en.wikiquote.org/wiki/Marianne_Williamson
[matthew]: https://en.wikipedia.org/wiki/Matthew_7:13
[mingo-hagen]: https://mingo.nl/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/013-do-what-you-love-and-youll-never-work-a-day-in-your-life.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** I know we're recording, but, but Ben, I just got to say up front before we get into it. It's been a privilege just getting to know you. I mean, I've kind of known you, but just knowing you, like, like talking to you every week has just really been awesome.

[00:00:12] **Ben:** This has been so much fun for me. I can't even tell you guys.

[00:00:15] **Tim:** I mean, I just feel, I feel closer to you guys, even if, you know, you're not going to get rich off this or famous, but it's like, I feel like it's, it's touched me personally. It's made me better just knowing you people. I love it.

[00:00:29] **Adam:** I wish I could say the same, Tim. Thank you, Adam.

[00:00:33] **Tim:** I didn't expect that. I'm a taker, not a giver.

[00:00:53] **Adam:** Okay, here we go. It is show number 13 for March the 10th. And on today's show, we're going to do a topic from a listener's suggestion. Mingo, I believe your last name is Hagen. Hagen? Uh, ask that we talk about the, the phrase, do what you love and you'll never work a day in your life. That sounded interesting to us, so we're going to take a look at that.

[00:01:11] **Adam:** Thanks for the topic, by the way. Yes, thank you. And before we do that, as always, we're going to do our triumphs and fails, and I'm going to fill in for Carol here. She, as she mentioned last week, she's not in this week. She is AFK. Snowboarding in Lake Tahoe with her son, and that is definitely a triumph.

[00:01:27] **Tim:** I've seen, I've seen the pictures. I'm so jealous.

[00:01:31] **Adam:** Super jelly. Uh, so who wants to go next?

[00:01:33] **Tim:** I'm gonna be like you guys in the past and struggle to say if this is a triumph or a fail. The failure part is that I have been so slammed the past week. I constantly spend every single day trying to do a set amount of work and I'm constantly interrupted with meeting requests, with training requests, with, uh, HR requests.

[00:01:56] **Tim:** Just so many things that just keep coming in at me that today I actually scheduled, so I put on my calendar. I'm like, if I do not schedule at least five hours of coding, I am not going to get what I need to get done. So I scheduled today from, um, 5 a. m. until... 12 PM, 12 noon, lunchtime till noon. So 5 AM till noon.

[00:02:23] **Tim:** I put a meeting there, a big long meeting, that the only thing it said was code like the wind.

[00:02:33] **Tim:** And I, so that way no one could just jump in my, cause like people constantly jump in my calendar. They constantly, like I have like, we're trying to hire some people and I'm having to do interviews, so HR is constantly putting these people. In my calendar and in these other meetings that just are total injects and I'm not, don't get me wrong.

[00:02:54] **Tim:** The meetings are important. A lot of the things that if I don't have the meeting with them, my goals will fail. So I'm, none of this stuff is not pushing my, my personal agenda forward. It is, but there's the stuff I've got to get done on my own outside of what I have to help other people get done. And so I, I, I put that on my calendar today and I did it.

[00:03:21] **Tim:** I did it. I didn't look at my email.

[00:03:23] **Adam:** Wow. I didn't take a call. No Twitter. I

[00:03:25] didn't,

[00:03:26] **Tim:** I didn't, I, I didn't look at our discord. Sorry, patrons. I didn't look at our discord at all. Sorry. I'll look at it, you know, later. But, yeah, and I got so much done. In fact, actually, what made me really, really happy, and this is a triumph for me, is the customer that I'm really, they're, they're sort of our beta launch, uh, supporter on this, this, this project.

[00:03:50] **Tim:** She sent me an email today at 6pm, my time, to say, Thank you so much for all the work you got done today. Oh, nice. And that made me feel so good because, yeah, because I did. It's like, and the stuff I wasn't doing wasn't hard. It was just, it needed attention to detail. And I, I can't, I've learned this about myself.

[00:04:14] **Tim:** I cannot pay attention to detail when there's constant injects. I fail. Wouldn't I have so many injects? So yeah, I'm, I'm proud of myself today. I, I coded like the wind today.

[00:04:28] **Ben:** One thing that would be interesting to talk about sometime is something called the Pomodoro technique, which is where people work for set periods of time, like 20 minutes, and then they take a five minute break or a 10 minute break or something.

[00:04:42] **Ben:** And I've never worked like that, but people who use it swear by it. But I listened to you talk about heads down and productivity. And that's how I feel a lot is that if I'm heads down, if I'm in the zone, feeling the flow, I don't want to stop every 20 minutes and, you know, it's probably terrible for my wrists and my eyesight, but I don't know, sometimes I feel like.

[00:05:05] **Ben:** Incremental working and then breaks disrupt me more than they help me, but the topic for another show that made me think.

[00:05:12] **Tim:** Yeah, I definitely would bring that topic up because I, I, I'm with your gut feeling that 20 minutes for me, it's like, I'm, I'm just getting good at 20 minutes. So it's like, I need several hours.

[00:05:24] **Adam:** Not to turn this into the Pomodoro show, but I agree. I think that the. The Pomodoro Technique, I've played with it in the past and I think that it works best if your work more closely resembles turning a crank than unpacking some giant concept in your mind and then using that context to, you know, build on that and do something interesting.

[00:05:46] **Adam:** Yeah,

[00:05:46] **Tim:** I barely understood the problem in 20 minutes. So, how

[00:05:52] **Ben:** about you Ben? So I have a triumph this week and it actually dovetails a bit with the topic of the show. And, uh, right now work, we're in the middle of what we're calling Sync Week, which is a week long. In normal times, this would be an actual in-person event where the whole company would get together because we're an entirely remote company.

[00:06:14] **Ben:** So, uh, usually we call it i r L in real life, but this year we're calling it Sync Week. It's all virtual. It's been themed the amazing race and, you know, team activities based on, on the show. But, uh, uh, in the keynote. I was super pumped up to be called out with my coworker, Jackie Ewald. We were recognized as embodying the customer empathy principle at work for the stuff that we've done.

[00:06:44] **Ben:** And so obviously super exciting to be recognized for that. But the reason I think it dovetails with work is because we were specifically called out for having built a feature for a customer. That we almost certainly weren't allowed to build at the time. Uh, I, we were on a call with a customer. I can't, I won't give their name, but we're on a call with a customer.

[00:07:10] **Ben:** Customer pays us a ton of money and they were expressing a certain degree of friction that they were having with the software. And I was listening to this and I thought to myself, what you're saying is super simple, like literally something that I could build in three hours. And I didn't ask for permission.

[00:07:26] **Ben:** I discussed it with Jack, who is the customer success manager on the call. And I said, let's just do this. Let's just do this for them. We can put it behind a feature flag. We'll turn it on just for them. And if it causes an issue down the road. We'll address the issue then, but for now it's worthwhile for the type of customer they are.

[00:07:44] **Ben:** So literally spent like, uh, three, four hours building this thing, deployed it just for them behind a feature flag. They were super excited. And now, months later, getting recognized. For building this as an example of customer empathy, just feels like vindication for the feelings that I were having at the time that I don't care.

[00:08:07] **Ben:** I, I a hundred percent know that if I had asked a manager, can I build this for this customer? I would have absolutely been turned down. I would have been told that we can't do this. Uh, we're going to break with the, there's a whole lot of political stuff going on behind the scenes, but it definitely would have been rejected.

[00:08:23] **Ben:** Isn't there always? Always. And, um, And I wanted to read a quote from Stephen Gates, who is our former head of design evangelism at, uh, at work. Uh, he just left, I think, a couple of weeks ago. But I kept a quote from him at the top of my team's ideation document. And this is what he said. For most companies right now, because of the way their processes are, because of how afraid they are of so many things, the innovation they need will probably not be authorized.

[00:08:55] **Ben:** When I look back at all the work that was innovative, it was only innovative in hindsight. It almost got me fired on the way there. And it's just. Having had his quote at the top of all of our design ideation meetings and now being recognized for something that I almost certainly didn't have permission to build in the first place, it just feels like extra layers of rewarding.

[00:09:20] **Ben:** So it was a pretty, pretty huge triumph for me.

[00:09:24] **Adam:** I award you two Attaboys. Yeah.

[00:09:28] **Tim:** You know, here's a topic that we could possibly go into at another time. We talked about it a little bit before the show, we were talking about Elon Musk. I mean, one of his things, he said there's too many... MBA graduates leading companies.

[00:09:46] **Tim:** And I think that's sort of, you know, it's, it's your, it's your people that know that technology that are engineers, they're the ones who are going to take the risk because they see the potential. You, you, you give that to an MBA. They're like, no, no, we can't do that. And it's the natural conservatism of, of not taking the risk.

[00:10:08] **Tim:** But yet you take the risk and you think, oh, I could get fired for this. And yet you get. And applause because afterwards the payoff is, is huge. So yeah, I would love to dive into that at some point.

[00:10:21] **Ben:** The phrase that always pops into my head when I talk to people who don't share my mindset is FUD, fear, uncertainty, doubt.

[00:10:29] **Ben:** And I feel that the higher up in the organization you go. The more you think about fear, uncertainty, doubt, and, and I feel like the lower down in the organization that you go, the more you focus on the opportunity costs of not doing something. And maybe it's because your outlook is more nearsighted.

[00:10:50] **Ben:** Because you're not thinking about the, the trajectory of an entire organization. So you look at a particular thing and you think, uh, this is crazy not to do, like, how could I not do this? Whereas the higher up you go, maybe you have to

[00:11:06] **Tim:** de risk. The higher up you go, the less detail you have, right? So, I mean, you see things, you don't, you see things, but from broader perspective, but you don't see things at a detailed level when you're at the lower level, you.

[00:11:19] **Tim:** Completely understand how this one thing, although small, can become huge. You don't see that further up. You just see a baseline number that says, Oh, you know, it's a 1%. It's not that big of a deal. And, but you realize that 1% is, could very shortly become 20%, 30% of a problem.

[00:11:41] **Ben:** 100%. That too. 100% agreed. How about you, Adam?

[00:11:47] **Ben:** What's going on in your life?

[00:11:49] **Adam:** So I have a failure this week. Um, Today, I spent several hours, not just of my own time, but somebody else's time as well. We were pairing on this. And, uh, we were debugging, uh, a Docker build. We were trying to basically take a Docker container that we were building that the final production image was about a gig.

[00:12:08] **Adam:** And just see what we could do to make it smaller. And, Um, a small triumphant silver lining to this cloud is we did get it to just over 100 megs, so huge reduction in size, which would be nice cost savings in our ECR storage and it should, in theory, make deploys go faster. Um, but it took several hours, I want to say three to four hours of two people's time to figure this out.

[00:12:37] **Adam:** Because I was seeing intermittent success and intermittent failure, and of course, you know, I tried very hard at first to approach it methodically and change one thing at a time and, okay, have confidence in that one change before I move on to the next, and So I was changing a Node. js Docker container and changing it from the the basic Node.

[00:13:04] **Adam:** lts container to like Node. 14. lts on Alpine Linux, which is a where a big portion of that size savings comes from. But then other things that I was doing, so we use a makefile as part of the multi stage build to do tests as part of the build, and in that makefile I was monkeying around with some things and...

[00:13:28] **Adam:** I had put a line in the makefile that I would, you know, kind of drop in and take out at random as I was working on debugging this stuff. And it was, uh, the line was echo period with no space between the two, which if you're from, if you're familiar with Windows batch script programming that prints out a blank line.

[00:13:48] **Adam:** And for some reason, and I know that you have the echo command on Unix systems. And so for some reason I had it in my head that you could do the same thing in my computer is a Mac. So I just thought it'd be the same. And it worked fine for me locally on my Mac, but I guess it doesn't work in Ubuntu. So, um, my builds were failing at that line, and I didn't notice it because it, the whole point of having that echo there was the command before that, um, was not ending with a new line, and so I was just trying to get the next thing down onto the next line, and I was seeing that it failed at that line above it, and In the output, and I was getting hung up on the fact that the line above it was failing, and ultimately, a stupid echo is what was killing my build for three hours today.

[00:14:35] **Adam:** And I just, it was so frustrating. I've lost enough hair as it is, and you know, you have a day like that where you're yanking your hair out, and it turns out to be... You know, in so many cases, it's like a missing semicolon or whatever, something stupid like that. And ultimately, what it came down to was a bad assumption.

[00:14:51] **Adam:** You know, I had just assumed that this line was, um, foolproof. No way this could possibly be the problem. And so I was dropping it in and taking it out and dropping it in and taking it out and, uh, rough day. I got

[00:15:03] **Tim:** some ignorant questions for you because you used some terms there I'm not familiar with. So, what is Alpine Linux?

[00:15:09] **Adam:** My understanding of it is, it is a extremely stripped down version of Linux to the point where it, it doesn't have bash, it has what is called ASH, I think, um, which is comparable to bash, but it's different. I'm guessing it's, it's, it's much, they take the B off. It's much lighter. They saved that bite. Um, but it's much lighter weight.

[00:15:33] **Adam:** It doesn't have SSH. It doesn't have git. It doesn't have curl.

[00:15:36] **Tim:** More

[00:15:36] **Ben:** importantly, so it's, It doesn't have nano. Yeah, or vi. Is the editor... Nano is the best thing ever. It's the only editor I know how to use on the command line. Me too, me too. I refuse

[00:15:46] **Tim:** to use vi.

[00:15:48] **Adam:** Vi, I can't stand it. Technically it's vim. I just want to make sure that we're clear with that bit.

[00:15:52] **Adam:** It's called vim, but the command is vi. I don't know why. Actually.

[00:15:58] **Tim:** And what is a

[00:15:59] **Adam:** megfile? Megfile. Makefile. Oh, make. Sorry if my pronunciation was poor there. Make. Yeah, I thought you said make. Oh yeah, I probably

[00:16:07] **Tim:** did. Makefile. I know what a makefile is. Okay.

[00:16:11] **Ben:** Did you, uh, have you played around with The multistage builds.

[00:16:15] **Ben:** You were talking about that on an earlier

[00:16:17] **Adam:** episode. Yep. Yep. We're doing that. And that was another way that we saved a bunch of space. So, um, this is a Node. js application. And, um, one of the ways that we saved a bunch of space was to do, uh, so in our package. json for this particular application, we're using private modules that are just, uh, loaded over a git URL.

[00:16:37] **Adam:** So we don't have, like, npm private modules or anything like that. We just, uh, have the, the git URLs. Set up correctly in our, in our package json so it can go and pull them from there and keep them as a private repo. Um, but the downside of that is you have to have GI on the machine where you're doing like the N P M install, which is not a problem in 99% of cases.

[00:16:58] **Adam:** But then when we switch to Alpine Linux, It doesn't have Git installed, and I tried, like, okay, well, what happens if I just install Git? Well, apparently, it costs 90 megs to install Git, which is ridiculous, but whatever, that's the truth. Um, so, what I ended up doing, ultimately, was... To move the npm install up into the multistage build, the build layer, container, whatever you want to call it.

[00:17:24] **Adam:** Um, and then after we're down in the final container, I will copy the node modules folder from the build container.

[00:17:32] **Ben:** Nice. Yeah, the multistage build stuff is fascinating. It is. Groovy.

[00:17:37] **Adam:** Cool. So, what do we think about the phrase, do what you love and you'll never work a day in your life? Oh, I've got

[00:17:44] **Tim:** thoughts on that.

[00:17:45] **Tim:** Hit

[00:17:45] **Adam:** it. Yeah, go for it, Tim. No, no, no, no, no, just let's... If somebody, let's, let's play devil's advocate here. Maybe there's somebody out there that doesn't truly understand what the phrase is trying to say. And I think, I'll, I'll take a stab at it. I think what it's trying to say is, if you love what you do, then you will enjoy your work so much that it won't feel like work.

[00:18:08] **Adam:** And you'll enjoy your career and you will never be miserable about the idea of going to work. That sounds right.

[00:18:16] **Tim:** Close. Yeah, I guess.

[00:18:19] **Adam:** Well, if I'm not right, Tim, then correct me.

[00:18:22] **Tim:** So do what you love and you'll never work a day in your life. So that if you choose something that you really, really are passionate about, then every day you will be passionate about what you do.

[00:18:38] **Tim:** And at some degree I can agree with that, but I have huge. Huge problems with that statement on so many levels.

[00:18:50] **Ben:** Yeah, I think, I mean, I've talked about how violently passionate I am about my work sometimes, but I've had panic attacks. I've had

[00:19:02] **Ben:** times when I can't imagine getting up in the morning to go to work.

[00:19:06] **Ben:** I've had really, really dark times, but I absolutely love what I do. And I think the underlying issue that maybe you're feeling here, Tim, is that work is always work. And, and the things that you're passionate about are still work. And that's why you hear people say things like, I don't want to turn my hobby into a work because then it won't be fun anymore.

[00:19:31] **Ben:** Because the reality is, is that when it's something that you're doing as a career, it's hard. It's always hard. If it weren't hard, I don't think it would be interesting personally, but there's going to be days where it's not fun and you just have to muscle through with the idea that it's going to get you somewhere.

[00:19:50] **Ben:** And, uh, and you have to be able to hold that, that love and almost that pain sometimes in the same thought and understand that you're doing the right thing.

[00:20:01] **Tim:** So, so I'm going to challenge the first statement about do what you love. I agree. Everyone should be able to do what they love, but not everyone can do what they love.

[00:20:15] **Tim:** People have to live. I mean, ultimately what you do for your career, your life, your work, a lot of it depends on your position in life. Some people cannot do what they love. There's a certain

[00:20:28] **Adam:** amount of privilege involved in

[00:20:29] **Tim:** being able to do that. There's a huge, I mean. Absolutely. There's a huge amount of privilege.

[00:20:34] **Tim:** I'm not going to sit here and say, I mean, the fact that my father was able to buy me a computer when I was a teenager, when he couldn't afford it. He did that, but he could do it because he was able to. And I've benefited from it. The fact that I was able to go to school to learn to do it is a privilege.

[00:20:52] **Tim:** And the fact that the, I mean, there was probably 10 years of my life where I just trying to use a bad word here. Um, I goofed off. I totally goofed off. I totally did. And I didn't starve. Nobody died. That is total privilege to be able to just goof off for several years of your life to just pursue something that you really want to do and not fail because I had a support system.

[00:21:25] **Tim:** So doing what you love is not an option for everybody.

[00:21:29] **Adam:** And there's another side to that coin as well is that there are a lot of jobs that Need to be done, whether or not somebody loves them. Like, there may not be, there may very well be, but I imagine it's not high on the desired career list to be a high school janitor, or, you know, whatever.

[00:21:53] **Adam:** But, uh, that's a very necessary job.

[00:21:56] **Tim:** Right. And those people that do that, I mean, if it wasn't their love, they're doing it because they have to, and they learn to love it. I mean, I've, I, you know, high school janitor actually in my middle school was probably one of the most influential people in my life because he was a cool dude.

[00:22:13] **Tim:** He was really was. He was, he chatted with me, we hung out and like. He didn't teach me any topics, but he turned, he, I was in middle school, I was the smallest. So I went from being the smallest kid in my class in middle school to being just normal height in high school. I was picked on relentlessly in middle school, but my, my middle school janitor was like my buddy.

[00:22:41] **Tim:** And it's like, did he love his job? I don't know, but I'm so glad he was there because he did so much more for me than just cleaning the floors. So, you know,

[00:22:56] **Ben:** I don't think I knew any of my janitors at

[00:22:58] **Tim:** school. My dad, I don't know what he would have loved to do, but I know that when we were young and struggling, he liked clean cars.

[00:23:09] **Tim:** He was a car washer. That's what he did for a living. He washed cars. And honestly, he loved it. He loved, my dad, he loves cleaning stuff, but he couldn't make enough money doing that. Um, and so he loved it. Was he working? Yeah, he was working, but he was enjoying what he was doing. But at the same time, he couldn't feed a family of four, you know, making below minimum wage being a car washer.

[00:23:36] **Tim:** So he, he learned chemistry and learned to make carwash soap. And became a business owner that turned into a, you know, a multi million dollar business. They later sold. I mean, so sometimes you have to do things you don't necessarily love. Yeah. And there's nothing wrong with that. And I, that's the thing that bothers me the most.

[00:24:01] **Tim:** I think that if people hear that phrase, that if they, they're not doing what they love, they feel, feel like they're a failure. Maybe you're not doing what you love right now. It doesn't mean that. You're not leading up to it. You can, you can eventually do what you love, or you can learn to love what you're doing,

[00:24:22] **Adam:** or you can love the fact that you're doing what is necessary to support yourself or to contribute to the economy or to do some work that just needs somebody to do it.

[00:24:32] **Adam:** And you spend your work time on work and then you have hobbies that you love in your free time and that's where you find personal satisfaction.

[00:24:41] **Tim:** Or the immigrant story where you're, you're, you know, you're doing what you have to so that your kids can have a better life. There, there's love in that.

[00:24:47] **Tim:** Absolutely. It might not be the work, but there's still love there. This is getting deep. This is real. I

[00:24:53] **Ben:** know. When I was preparing for this show and putting my thoughts together, I was thinking to myself, what can I, how, what advice can I give people so that they can get through times in their work when they're just frustrated or, or not enjoying it?

[00:25:07] **Ben:** Definitely, I did not come at it from a very The deep philosophical perspective that you're taking, I think. I

[00:25:16] **Tim:** think it's, yeah, I mean, that's the only way I can come at it, because I think it's bigger than that. I mean, you're talking about life goals. You're talking about love. Love is, love is life, right?

[00:25:26] **Tim:** So, yeah, I mean, do we all get frustrated? Everyone does, right? But it's like, what do you love in life? And that, that love sort of defines you.

[00:25:41] **Ben:** I guess when I heard the phrase, What strikes me about it is this idea that I think people equate not working with being easy. That this idea, if you do what you love, then it'll just be easy.

[00:25:54] **Ben:** And that's the part where I push back against. Just because you love something, it doesn't mean that it's going to be easy. It doesn't mean that it's necessarily going to come naturally all the time. That there is struggle and there's hardship and there are hurdles and there are ebbs and there are flows and there are peaks and valleys, but that's all part of the journey of doing something that you love, that there's not, it's the love that allows the drudgery of it to be easy, but it's still drudgery sometimes.

[00:26:28] **Ben:** I wanted to read a quote from this painter, Chuck Close. Uh, most people have heard, I think, part of the phrase, which is this inspiration is for amateurs. The rest of us just show up and get to work.

[00:26:41] **Adam:** I think you read this on a previous episode. Yeah. I did?

[00:26:44] **Ben:** Yeah. Oh, cut this. No, no, no. Don't cut

[00:26:46] **Tim:** it. Don't cut it.

[00:26:47] **Tim:** Don't cut it.

[00:26:49] **Ben:** This is why I have a terrible memory. That's right. I vaguely remember running out of breath reading it.

[00:26:56] **Tim:** It makes you breathless.

[00:26:57] **Adam:** So, uh, I think there's another angle on the second portion of this phrase, you'll never work a day in your life, that stands out to me. And that is, none of us that I'm aware of, certainly not me, do only the part of our job that we love.

[00:27:19] **Adam:** Right? So, if I take this thing as what it is, so do what you love and you'll never work a day in your life. Well, what I love about programming is choosing the thing I want to work on, following it. As into this state of being where I don't even realize it's been 11 hours since my last meal and you know, I haven't spoken to another human being in two days and uh, you know, I, I'm just deep down this rabbit hole of the project that I want to work on and then, you know, either I finish it or whatever and then I want to move on to the next thing and maybe I'll never finish it and maybe Whatever, but I don't have to write documentation for it, and I don't have to write tests for it if I don't want to, and I don't have to go to meetings about it, and I don't have to explain it to customers seven times, and I don't have to give it some weird name, and I don't have to do, uh, you know, budget forecasting or any of that part, but that's all necessary work when it is part of a business, which is what you're doing when you're, you know, working a job.

[00:28:29] **Adam:** And so I think that, that... All that stuff is kind of lurking in the shadows when you talk about like, do what you love. Maybe, maybe there are people who are fortunate enough to be able to work on the part that they love and then they can afford to hire enough people to be like, okay, you do the part I don't like.

[00:28:46] **Adam:** I think that that is the extreme minority.

[00:28:49] **Tim:** You hit on the head.

[00:28:50] **Ben:** One thing that I do, which relates to what you were just saying, is that I like to structure into my day, a period of time that is dedicated to doing what I want to do. It is dedicated to doing very self directed, very autonomous work. And for me, I like to do that during the morning.

[00:29:10] **Ben:** That's my most creative time of the day. And I feel like that's when I'm most free thinking and most able to color outside the lines if I need to. So for the first hour, hour and a half of every day, I draw a really hard circle around that time. And that's the time I do things that. People didn't ask me to do that's not on a roadmap or has not been allocated based on some sort of a timeline or, or whatever estimations that's, that's the time where I can pick and choose the things I want to do, whether it's a tiny support ticket that I saw come through, or it's a random idea that I had from using the application.

[00:29:48] **Ben:** I felt here's a part I can improve or maybe some R and D, but it's, it's a time where I know that I have it every morning. Regardless of what's going on at work, this is my sort of quiet time, my peaceful time. And no matter what's happening, I always have that to look forward to. So even if I know that the rest of the day is going to be kind of sucky and challenging and I'm going to have to work on stuff I don't want to work on, at least I know that I have tomorrow morning as a, as a respite from, from what's going on right now.

[00:30:20] **Adam:** I like that a lot. I'm going to try to adopt that in more ways than one. I'm going to do that with my work and I'm also going to try to do that with hobbies. It's

[00:30:29] **Tim:** kind of like what my triumph was today with scheduling out that time period from 5 a. m. till noon, where I said, I'm doing this. And that was, I so enjoyed that.

[00:30:41] **Tim:** Uh, just knowing that no matter what, it was a luxury, honestly, I'm going to be fair that that was a luxury because there were so many demands of my time, um, that are outside of what I want to do. That's what I wanted to do. So if you can do that. You know, any sort of fashion is going to be helpful. So again, me backing out to the higher perspective, I will say this on the opposite side, cause I totally poo pooed this, this kind of sentence, but you know, I've got a teenage son who is, and I remember this part, portion of my life when I was younger of, you know, what am I going to do with my life?

[00:31:27] **Tim:** And a lot of times you, you try things. And you think you like them and you really don't. And I think this sentence to do what you love and you'll never work a day in your life is good for the phase of your life where you're not really sure what it is you love. Because, you know, he, let's take my kid. He doesn't listen to the podcast.

[00:31:55] **Tim:** He's a fantastic artist. He's also very critically minded. He's good at programming and he, he's He's looking into, uh, doing animation, uh, cause he's a big anime nerd and wants to do animation. But the more he learns about it, you know, they realize how hard it is. He loves it, but there's no, it doesn't know if he wants to do it for his job, which I say at this point in his life at 16, 17, it's probably a moot point, but it's at least worth an exercise of going into.

[00:32:30] **Tim:** Well, see what it's like. Um, when you're at that phase in your life where you're trying to figure out what it is you want to do, definitely do the love test. Definitely do the love test. It's the same way with picking a mate. What do you mean by the love test? The love test is, so you're picking a, you're picking someone to spend the rest of your life with, right?

[00:32:55] **Tim:** The love test is you take the worst thing about them, the thing that annoys you the most and say, can I live with this for the rest of my life? And if you can. Ding, ding, ding. Winner, winner, chicken dinner. I mean, if, if, if you go into a job and can't take the worst of it, then don't start it and find something else.

[00:33:23] **Tim:** I mean, so, or if your love for it out outweighs your level of frustration with it, so, you know, you find someone, they're fantastic, they complete you, but they do this one thing that really annoys you and you're not sure you can live with it, but you know what, you can't live without it. Ding, ding, dinging.

[00:33:43] **Tim:** That's your love test. So I, I think this, this question is not one of those questions where you've already decided I'm a programmer, that's what I want to do. There's gonna be frustrations. Oh yeah.

[00:33:57] **Adam:** I don't think any job would be without

[00:33:59] **Tim:** frustrations. What, what fun would it be a job without frustrations?

[00:34:03] **Tim:** Yeah. Right. I mean, we, we complained about it, but honestly, it's what drives us to overcome them. So do what you love, but you know what? It's gonna be work. I

[00:34:14] **Ben:** keep thinking of ways to make this more light hearted. It feels like, I feel like this conversation is very deep.

[00:34:22] **Tim:** Yeah.

[00:34:24] **Adam:** Well, I think that the saying itself is attempting to be very shallow.

[00:34:29] **Adam:** Like, it's attempting to sound deep without going deep. And maybe that's

[00:34:33] **Tim:** its downfall. To make it more deep, can I bring some Bible into it? I don't know,

[00:34:40] **Adam:** do we have room for the JPMs here, or?

[00:34:44] **Tim:** What's

[00:34:44] **Adam:** a JPM? Jesus is per minute.

[00:34:46] **Tim:** Ah. So, in Christianity, so, you know, Jesus once said that, uh, he recommended that people go into the narrow gate.

[00:34:57] **Tim:** So, he said go into the narrow gate because broad and spacious is the road leading off into destruction. And many are the people going through it. Whereas narrow is the gate and cramped is the road leading into life or success. And few are the ones finding it. And I think about that, that that's saying a lot, because I don't think what he's saying is that he's, what he's saying is that the way to do something correctly is so narrow and so focused that it's hard.

[00:35:26] **Tim:** The road leading into success is not easy. It's not, it's not made to be hard, it's just because it's such a narrow pinpoint that you have to work to get to it. And it's the same way with, with enjoying a career. It's like, it's hard because it's specific. If it were easy, anyone could hit it, and it wouldn't mean anything.

[00:35:53] **Tim:** It's the same with with with enjoying your your work. It's like you have to struggle to appreciate it not because Appreciation needs to be struggled for but because the struggle leads to success Success requires struggle. That's what I'm saying. There's so many that there's an infinite number of ways to do something badly There's a very limited number of ways to do something properly and you're only going to get A sense of fulfillment when you do something properly.

[00:36:25] **Ben:** Well, the thing that strikes a chord with me, when you say choosing the narrow gate, is I always like to say that I thrive in structure, meaning that I get up at the same time, seven days a week, I start work at exactly the same time. I have my dedicated autonomous work time. I end work at exactly the same time.

[00:36:46] **Ben:** I find that I can only be successful when I have a very rigid structure in which I can operate. Because that allows me the freedom, I think, to do the things I need to do when I need to do them. And because of that, I've never really been able to relate to people who talk about remote work. As this flex time, I can come in late when I need to come in late.

[00:37:13] **Ben:** I can stay late when I need to stay late. If I want to go have lunch with, you know, people for three hours on a Wednesday, I can do that. No part of that makes sense to me because I, I love working remotely, but I need to have that structure in order to do the things I need to do. And. Dead. You travel on the cramped road, brother.

[00:37:33] **Ben:** My wife is always like, Hey, maybe you should sleep in tomorrow. And I'm like, no. Why would I do that? Yeah. She's like, but you're really tired today. I'm like, yeah, that sucks. But I need to wake up at the same time tomorrow so that everything else falls into place. Because I don't know how to do my

[00:37:47] **Tim:** day.

[00:37:47] **Tim:** When my alarm goes off, I get up. Right. That's

[00:37:49] **Adam:** just, you have to. I... Can relate, but not for the same reasons, Ben. I, so I have young children, or I have had young children. They are starting to grow up now. My kids are now 10 and 12. It's, it's tough, they tend to not think of them as, you know, six and eight anymore.

[00:38:05] **Adam:** Um, but, uh, you know, when you are a parent of school aged children, you tend to... Have to work backwards, right? So, in order to, everything is based on catching the morning school bus, right? In order to be awake in time to have a healthy breakfast and be ready to go in time to catch the morning school bus, they have to go to bed at a certain time.

[00:38:27] **Adam:** In order to go to bed at a certain time, they have to have dinner at a certain time. They have to be done at a certain time with homework. You know, we have to, the whole day is structured around the schedule and. Like it or not, I live inside that box. And so I've learned to thrive in that as well. And I end up with a schedule very much like what you're describing, you know, get up at the same time every day.

[00:38:49] **Adam:** Mine is a little different because now with the pandemic and hybrid school, our schedules are different on different days, but it's a set routine. It's the same every week, whether or not it's the same every day. And At the same time, I feel like my personal batteries get recharged from those flexible moments.

[00:39:10] **Adam:** So, If I have a sick kid and I need to take him to the pediatrician or if they have a dentist appointment, I can take him to that. Or if I want to go have lunch with my, uh, my old boss, who I consider a mentor and a friend, um, you know, I do that and I might work a couple of extra hours that evening or maybe I won't, maybe I'll make it up, you know, I feel like I'm a little bit of a workaholic anyway, so I'm constantly sticking an extra half hour on the beginning of the morning because I have it available, right?

[00:39:36] **Adam:** You know, the kids are off to school and what else am I going to do? So I might as well just go get started early. And so I feel like I'm kind of walking a tightrope between those two worlds. The, I live in that structured box, but then I, there are maybe designated moments of freedom. If that makes sense.

[00:39:57] **Adam:** So you go through the narrow

[00:39:58] **Tim:** gate and then you kind of jig a little bit and then

[00:40:00] **Ben:** you come right back. I think that makes sense. Cause even within my structure. Sometimes I need to go for a walk or I'll take the dog out cause she has to go out or every now and then I just need to go lay down for just three minutes, five minutes.

[00:40:16] **Ben:** I just need to take the weight off of my legs and my spine for a minute and just zone out for a second. And that's just, you just need that sometimes. But, but for the most part. And it's, and it's subjective, right? It's a personal strategy for success. I find that I need that, that structure. My creativity is not hindered by structure.

[00:40:40] **Ben:** I think my creativity is facilitated by structure and having that safe space within which I feel like I can be

[00:40:47] **Tim:** creative. Do what you love. Yeah, man. If you've got the privilege to do it, do it.

[00:40:52] **Adam:** Yeah, but don't expect that it'll never feel like work. Yeah.

[00:40:56] **Tim:** Will you work a day in your life? Yeah, you're going to work, but you know what?

[00:41:00] **Tim:** You're going to enjoy it more than doing something you don't love. So, uh, who was it that recommended this? Yeah, Mingo,

[00:41:06] **Adam:** Mingo, thank you so much for the topic. I, I didn't think that we would be able to talk about this for about an hour, but, uh, here we are. It's been an hour, geez. Here we

[00:41:14] **Tim:** are. Yeah. Coming up on an hour.

[00:41:15] **Tim:** It's, it's definitely, it's, uh, it's a perspective builder.

[00:41:21] **Ben:** If I could give one piece of advice that makes life more enjoyable, don't overcommit to estimates you don't believe in. That's like the worst possible thing you can do as an engineer, is knowing that something will take three months, saying you can get it done in a month, and then spending two months trying to explain why you're...

[00:41:45] **Ben:** A month overdue on your

[00:41:46] **Tim:** work. I feel personally attacked by that comment because I do that every time because I want to get it done. I'm like, I, I love this idea so much. I know if I just care about it and love it and kiss it so much, I will get it done in a month, no matter the fact that I really can't, I mean, I started something back in September and I'm like, yeah, this would be done by December.

[00:42:08] **Tim:** And like, here's it's March and I'm berating a customer cause I'm blaming them for my. My failures, but I know it's me.

[00:42:16] **Ben:** I read one time that one of the worst things managers can say to people is, I just need you to work harder for a little while because it paints this picture that most of the time people aren't working hard and it's incredibly demoralizing.

[00:42:33] **Adam:** Okay.

[00:42:34] **Ben:** Are we done here? I do want to end with a poem that I love.

[00:42:41] **Adam:** First spit take of the show. If I can read scripture, you can read

[00:42:46] **Ben:** the poem. This one actually, it mentions God in it, so I feel like we're tit for tat. Okay,

[00:42:50] **Tim:** here

[00:42:50] **Ben:** we go. Alright, this is Marianne Williamson's poem, Our Deepest Fear. Our deepest fear is not that we are inadequate.

[00:43:00] **Ben:** Our deepest fear is that we are powerful beyond measure. It is our light, not our darkness, that most frightens us. We ask ourselves, who am I to be brilliant, gorgeous, talented, fabulous? Actually, who are you not to be? You are a child of God. Your playing small does not serve the world. There is nothing enlightened about shrinking so that people won't feel insecure around you.

[00:43:25] **Ben:** We are all meant to shine, as children do. We were born to make manifest the glory of God that is within us. It is not just in some of us, it is in everyone. And as we let our own light shine, we unconsciously give other people permission to do the same. As we are liberated from our own fear, our presence automatically liberates others.

[00:43:51] **Ben:** I love this poem and, and I think, I think it connects to the topic because when you love what you do to a certain degree, it gives you the freedom. To truly express yourself and to do the things that you feel need to be done because you can let go of some of the fear that you might have otherwise. And, and as you do that, and people see you doing that, you, you allow other people to feel that same love in the work that they do because they see it's possible in others.

[00:44:26] **Ben:** So I love

[00:44:28] **Tim:** that poem. Your heart matters.

[00:44:32] **Ben:** You know, What used to drive me crazy would be kids in high school who would spend forever... Talking about whether nothingness was something. I'm just like, oh, I'm so deep, man. You're all artists. And this is what you like. This is not, not to say that they're all artists, but they were

[00:44:49] **Tim:** all like, A programmer would just say, do you guys know what null is?

[00:44:53] **Tim:** Just shut up. It's null. Oh man. So thank you guys. Thanks for listening. Um, apparently we have a Patron and apparently people like us enough to actually give us money. That's absolutely fantastic. Monte Chan. You're a legend. Thank you so much for donating to keep the lights on so that we can keep doing what we're doing.

[00:45:15] **Tim:** If anyone else wants to join Monte with his bold charge into supporting us at patreon.com/WorkingCodePod, send us some money. You don't have to, but if you want to. We won't turn it away. Yeah, definitely. We love you for it. If you really enjoyed this podcast, give us a rate on whatever you're listening on.

[00:45:36] **Tim:** And give us a review. Some places give a review, so that would be awesome. And thanks for listening. Anything

[00:45:42] **Adam:** else, Adam? If people have topic suggestions, how should they send them to

[00:45:45] **Tim:** us? That is a good question. I do

[00:45:47] **Adam:** not know that. They can send them to us on Twitter or Instagram, @WorkingCodePod. Okay.

[00:45:52] **Adam:** Well, I guess we'll catch you guys next week. And until then, your heart matters.

[00:46:16] **Adam:** I've been looking through some random Satanist quotes.

[00:46:24] **Tim:** I mean, it's what I'm going to talk about my, my triumphant fans like. My triumph is,

[00:46:27] **Adam:** well, I mean, your hair is still on point. That's your triumph.

[00:46:33] **Tim:** You know, it's not as good. Last week it was, I was really proud of it. Now it's like, you know what? I need to, it looks

[00:46:38] **Adam:** like it's a little more back and then instead of to the side today, you know, I've got to cover up the bald spot.

[00:46:43] **Adam:** I have

[00:46:43] **Tim:** some conditioner in there to try to It sucks. I'm too

[00:46:49] **Tim:** vain to get old.
