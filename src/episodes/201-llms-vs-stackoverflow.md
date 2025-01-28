---
title: "201: LLMs vs StackOverflow"
description: "The crew returns to dive into a thought-provoking discussion on the impact of Large Language Models (LLMs) like ChatGPT on technical communities such as Stack Overflow."
date: 2025-01-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/201-llms-vs-stackoverflow/id1544142288?i=1000684106661"></iframe>

We're back! and in this episode of the Working Code Podcast, the crew returns to dive into a thought-provoking discussion on the impact of Large Language Models (LLMs) like ChatGPT on technical communities such as Stack Overflow.

They explore how LLMs are changing workflows, the ethical considerations of using AI for coding assistance, and personal experiences with these tools.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/201-llms-vs-stackoverflow.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** hello? Hello? Is this thing on?

[00:00:02] **Ben:** Are we here?

[00:00:03] **Carol:** you. Yeah, yeah, I can hear

[00:00:04] **Adam:** oh, okay. How do we do this? We're, we're making a podcast. Okay, cool.

## [00:00:30] Intro

[00:00:30] **Adam:** So, hi everybody. welcome to Working Code Podcast. how do we do this again? Okay, cool. So,

[00:00:35] **Carol:** Season two! You gotta start with season two! Come on!

[00:00:40] **Adam:** We're so back.

[00:00:41] **Carol:** Clearly we're aligned.

[00:00:43] **Adam:** That's right. everybody's back. welcome back, Carol, Ben, Tim, say hi.

[00:00:48] **Ben:** Happy new year.

[00:00:49] **Carol:** Hi!

[00:00:50] **Adam:** All right. we're going to get into it tonight's show. We're going to talk about, LLMs versus Stack Overflow. I saw a recent report that, like Stack Overflow released some statistics about their, I guess their traffic or their usage or something recently. And since I think it was 2022, their question volume is down something like 70%, which is crazy.

[00:01:11] **Adam:** Which made me think like, okay, I think that the biggest thing taking away from that is probably like chat GPT, right? So we're going to get into that a little bit and start to discuss how we, how our personal workflows have changed and how we see happening and what's, what's going on there anyway. but first as usual, like we did in season one, we're going to start with our triumphs and fails.

[00:01:32] **Adam:** Carol, you would be next up in line according to the document that doesn't exist.

[00:01:38] **Carol:** Woo! Yep, I'll kick us off. so to introduce myself, I'm Carol. I don't know how we want to do this, you guys. Like, how do we say our names? Like, should we do it or not?

[00:01:46] **Adam:** uh, you

[00:01:46] **Ben:** you nailed your

[00:01:47] **Carol:** a thing? Okay. I'm Carol, the brains behind these guys. There you go.

## [00:01:53] Carol's Triumph

[00:01:53] **Carol:** I'm going to kick us off with a try. I'm starting 2025 very energized and ready to just knock some big tech goals out of the park.

[00:02:01] **Carol:** One of my things I need to achieve over the next year is just kind of proving that we are secure and that we have a healthy application. And that's kind of hard to prove on paper. Like, yes, we're secure. These scans say that, but what have we done to actually validate that these scans have meanings? And then what does it look like to be healthy?

[00:02:21] **Carol:** Is it really just Response time? Is it uptime? I don't think it's just that. I think to be healthy you also have to have like a nice user base and you have to have a good understanding of your users needs. So I'm really excited that that's been put on my plate for the next year is that I get to invest some of my time into making sure that we are showing that we're healthy and that we have a secure system.

[00:02:44] **Carol:** Yeah, I'm energized.

[00:02:46] **Ben:** Heck yeah. Welcome back.

[00:02:48] **Carol:** yeah. What about you, Timmy? What you got going on?

## [00:02:51] Tim's Triumph

[00:02:51] **Tim:** I, I mean, honestly, I need to remember how to work again. I mean, I was off so much during our break. It's like, I barely, I don't think I really worked a full week the entire time. There's a whole lot of, a PTO that we had to take off due to change in our, our, our, how we accrue our PT, not our, how we accrue it, but they cap it at a certain amount and I had a whole lot.

[00:03:10] **Tim:** So I had to make sure I used all that up.

[00:03:12] **Adam:** you don't have rollover minutes.

[00:03:14] **Tim:** We do have rollover, but it's like, you know, it used to be like extremely high rollover and then, and now it's like 80 hours a year, they cap it up, it's like, I get like 200 and something a year. So it's like, yeah, I guess, I guess they're forcing me to take time off, which, you know, that's a good thing.

[00:03:30] **Tim:** I should, I should use my time, but, yeah, so I, I'm forgetting how to actually work and then I got sick and then, you know, But I'm feeling better now. But so my triumph is not work related, not even tech related. Well, maybe slightly tech related. have you guys seen the new AirPod 2 commercial?

[00:03:50] **Carol:** there's a

[00:03:50] **Tim:** The one, it's a commercial.

[00:03:52] **Tim:** So there's this, this, this, this thing, they're called advertisements. They're sometimes you see them on websites, TV, things like that. But there's this, advertisement for the new AirPod 2 or the guy who, you know, he, he doesn't hear very well. I guess he has like. He's not old, but he's got like bad hearing and his daughter's playing the guitar and he puts the new AirPod 2s in his ear.

[00:04:15] **Tim:** And it goes from being more to her playing the guitar. Our house is a very, very, very fine house. And I was like, Oh, that's sweet. And my wife is like, you should probably get those. I'm like, what? I'm like, yeah. So I do, I had hearing tests. I have very minor hearing loss. It's not really bad, but it's like, I guess it's just that exact. portion of the wavelength of voice that my wife has so that I never can hear what she's saying.

[00:04:46] **Adam:** It's definitely not selective at all.

[00:04:49] **Tim:** No, no, it's, it's definitely, it's definitely a condition. And, and I, I, last year I'd gotten some actual like hearing aids, but they're like 5, 000. Insurance doesn't pay for

[00:04:59] **Carol:** What? They don't?

[00:05:01] **Tim:** No, insurance does not pay for hearing aids at

[00:05:03] **Carol:** Oh, wow. That's so sad.

[00:05:06] **Tim:** so it's like, it's extremely expensive. And if they weren't, they were, I wore them for a month before I took them back.

[00:05:12] **Tim:** I'm like, they're, they're okay, but they're not great.Um, 5,

[00:05:17] **Tim:** right, exactly. And so like the AirPod 2s are like 180 bucks, right? So I got some, and they're, they're actually super fantastic. They really are. It has a little hearing test on it. Just like you, when you go to the doctor, you hear the beeps and you just press the iPhone and says, yeah, I heard that.

[00:05:32] **Tim:** I heard that. And it tailors that sound to amplify that section you can't really hear. And, they've been great. I've been, it's actually shocked, shocks me because like my laptop, I didn't realize how extremely loud it was until I put these things in my ear. I'm surprised you guys can't hear right now.

[00:05:50] **Tim:** It's super loud. I need a new laptop, but yeah, they're great. I'm super happy with them.

[00:05:55] **Adam:** you're talking about like the fan,

[00:05:57] **Tim:** the fan on my laptop. Yeah. Yeah. Yeah.

[00:05:59] **Carol:** We've all been there.

[00:06:01] **Tim:** Yeah, it's super loud. I was like, I didn't realize it's that loud. My wife's like, yeah, we can't, you know, we have to close your door because the fan's too loud on your laptop.

[00:06:09] **Tim:** and then what's really cool, it's like, they're better actually than the hearing aids I had before because you can like just press the stem of the, of the, the iPod, the AirPods,

[00:06:19] **Carol:** AirPods,

[00:06:19] **Tim:** and it goes, it'll go into like, you can switch the mode between transparency, which is where you hear everything, it amplifies everything, or to like, sound cancellation.

[00:06:30] **Tim:** And so it's like, you turn that on and it's like, all of a sudden, all the fan noise, all the background noise goes, it's gone, but it's smart enough. If you start talking, if you say something, you know, I can cough. I can do whatever. It doesn't kick in. But if I say something out loud, a word, it knows that I'm speaking and it turns off.

[00:06:49] **Tim:** For a little bit, that, that sound cancellation. So then it's like, I will walk into the kitchen and like the washing machines going and the, you know, oven's going and all that's noise. I don't hear any of that. And then I'll say something to my wife and it'll kick off and I hear all that noise, but then I can also hear my wife's voice and things like that.

[00:07:06] **Tim:** So yeah, I mean, they're, I, 180 bucks for probably some of the best hearing aids I've ever had. Happy beats 5, 000 bucks.

[00:07:16] **Adam:** That's awesome, man.

[00:07:17] **Carol:** Yeah, we have them too, and the only thing I don't like is when I'm watching a video like Netflix on my phone and I start talking to Steve, it doesn't pause the video. It just turns Netflix all the way down, and I have to hit the back button to hear what I missed because it doesn't go, Hey, okay, let me pause this while you're having.

[00:07:36] **Carol:** The conversation, because I think it's called conversation awareness or something. yeah, so that's the only frustrating part. But yeah, I got mine and Steve tried them and he has hearing loss from guns, just from being in rooms and shooting guns, like for the army. Right. And, he loves them. He loves the transparency mode because the same thing.

[00:07:53] **Carol:** Like you guys were saying, like, he's able to then hear what I'm saying better and I don't have to yell. But now he's like, whoa, don't yell. I'm like, wait, I'm not like, this is just normal. Or he'll say, don't get so whiny.

[00:08:07] **Adam:** That's just because you're whiny, Carol.

[00:08:08] **Carol:** I am sometimes. I

[00:08:11] **Tim:** So, I mean, that's a small triumph, but it's like, Hey, that's, it's a proving quality of my life. So I'm happy with that

[00:08:19] **Carol:** mean, there's something to be said for tech and where it's going and just medical advances, period. So small, small things can make big changes in someone's life.

[00:08:28] **Adam:** Tech, it seems like, you know, nine out of 10 things, advancements in tech ultimately make life worse, at least for, for a significant, for more people than they help. Right. Maybe they, I should put it that way. but it's, it's real nice. Like what you're talking about, the, the medical devices, like the AirPod Pros using them as hearing aids.

[00:08:46] **Adam:** Like that's, that's just a win win. Like there's really, the only people that's hurting is the bottom line of the people that manufacture expensive hearing aids.

[00:08:53] **Tim:** Yeah. And I don't mind the fact that, you know, I'll put them in. It's like, you look like a stockbroker or something with them in your ears, but it's like, I don't mind that they're big. I, you know, they're, everyone at least knows what they are. Right. So there's, they don't, they don't think. hopefully they don't think ill of me for

[00:09:11] **Adam:** You look a little elitist. You don't look like a weirdo,

[00:09:14] **Tim:** Yeah, there you go. Yeah, right. Yeah. Yeah.

[00:09:16] **Adam:** uh, I also have AirPods pros, not, not the twos. I have the original pros. and like you said, the noise cancellation is amazing. Wearing them on a plane is great. You can still hear that there's an engine out there, but it's far better than not having them on.

[00:09:31] **Carol:** The can's

[00:09:32] **Adam:** noise cancellation. Yeah. It's, it's incredible for being an. Earbud, right? Like all before the AirPods Pros, my awareness of noise cancellation was always the around ear headphones.

[00:09:46] **Ben:** you'll hear something totally, as an aside, but it was funny. So I was on a plane back in September when I went out to a, CF summit. And the plane from Atlanta to Las Vegas was a really modern plane. Like it looked like it had just come off the assembly line. And I remember while we were in the air, I was actually kind of irritated that the sound dampening of the plane itself was working so well, because I'm so used to being on a plane and not being able to hear anybody.

[00:10:15] **Ben:** And suddenly I could hear everybody's conversation. And I was like, Oh, this is awful. Why can't they bring back?

[00:10:22] **Adam:** in a different spot than you normally do? Like, if you're behind the wings, then you get a little bit more engine noise versus

[00:10:27] **Ben:** yeah, yeah. I guess I was closer to the front of the plane. And so maybe I was, it was, but just, I don't know, it was funny. It's like, Oh, the modern convenience of, of better wall construction.

[00:10:38] **Ben:** But now I have to hear you all.

[00:10:41] **Tim:** So anyway, that, that's my little, little triumph, small as it is, but yeah, I'll take it. How about you, Adam? Adam Tuttle,

## [00:10:49] Adam's Triumph

[00:10:49] **Adam:** My name is Adam and I have a Triumph. can you, can you tell we're, we're trying out a new thing where, we're saying our names at the beginning of the show? Cause that was something people have, talked about. Anyway, My triumph is that I got a performance review at work and, you know, A, that's just triumph on its own.

[00:11:04] **Adam:** Maybe that that's a triumph for Steve that he actually did a performance review for me. and it took, compliance and regulators and auditing to actually get, I think if I'm not mistaken, I think this was my third performance review in the, in March. I will have completed my 13th year with the company.

[00:11:22] **Adam:** I think that's probably good, right? I think if I was being a screw up, then I would be getting negative performance reviews, but no news is good news sort of thing.

[00:11:32] **Tim:** a pip.

[00:11:33] **Adam:** Yeah. Yeah. Be put on a pip. so yeah, I got a performance review. It was good. And, and it was. Inspired slash required by all of the compliance stuff that we've been doing and compliance is going well.

[00:11:45] **Adam:** So that's sort of double dipping as I usually do on my triumphs here. and I'm sure I'll, I'll get more into that at a later date. I don't want to take up too much time on that, but I'm just happy I got a performance review. It went really well. I came out of it like really motivated and excited and it's really, I think going to change the way that I work here over the coming years.

[00:12:06] **Adam:** So I'm excited about that.

[00:12:07] **Carol:** Oh, that's awesome. Yeah, there's something about spending some time at a job and then finding that thing that kind of re motivates you a little bit. And if it's a performance plan, like if it's something just showing you what you've done well or like how you've benefited the company or how you can improve to help improve the company, those are all like great things to have as an employee.

[00:12:27] **Adam:** Yeah. The, the process of doing a performance review and the way that we did it was like a double blind sort of thing. Like Steve wrote up a, basically like a, a list of questions to answer, you know, it's like, you know, how have you been demonstrating leadership over the last year or whatever, that sort of thing.

[00:12:43] **Adam:** and it's probably like 10 or 15 questions. And we both, like, wrote it up about me. And then I sent mine to him and he sent his to me at the same time. We took, like, an afternoon to read it and digest the other things. And then we had a meeting to discuss, see, like, where we aligned and where we were different and stuff.

[00:12:59] **Adam:** And so it was good to see, like, an honest, picture of, you know, what he thought about me and how, you know, my, my goals and my interests in terms of, like, what I want to do for the rest of my career. Are pretty well aligned with what he wanted from me. So it's exciting.

[00:13:18] **Carol:** That's exciting and that's awesome.

[00:13:19] **Adam:** Thanks.

[00:13:20] **Tim:** so we started doing something this year. They're self evaluations, which I honestly, I kind of mixed on. So it's this big, long thing where it's like, talks about, you know, expert domain, leadership, communication, conflict. I mean, it's all these things and you're supposed to say, if you meet or exceed or don't meet, or so you, you judge yourself first and then, your, your manager gets it and then they supposed to go over it with you and tell you, you know, Where you align or where you don't align.

[00:13:52] **Tim:** And it's like, I had, so I had to do that for all my reports. And it's like, fortunately everyone on the team sort of has the same thing. Cause like, I think pretty much everyone put. Meet like, yeah, we, we, you know, we do our job. We, we meet that. Or if it's like something that they just felt like, yeah, it's not even within my job description.

[00:14:10] **Tim:** They just put, you know, NA, which is fine. and so we were all on the same page with that. Cause I'm like, I'm not going to sit there and say I exceed at something. And then you're like, no, you really don't. You just think you do. I'd much rather say I meet it, right? Cause you know, I meet it.

[00:14:27] **Tim:** So, and if, if you want to say I exceed it, I'm like, okay, I won't disagree with you there.

[00:14:31] **Adam:** I do think that the self evaluation is an interesting tool from the manager's perspective. It's like.

[00:14:37] **Tim:** It puts the onus on me.

[00:14:38] **Adam:** Yeah, it, it, it, I want to, I mean, I have zero direct reports right now, but as a manager, I would want to know not only like my interpretation of how your work compares to our expectations of your work, but how do you feel about, like, do you feel like you're doing an excellent job or just like barely skating by or what?

[00:14:58] **Adam:** And, and if we don't align, then that's, you know, that's a interesting and useful bit of information, right? Then that's a, we need to adjust either our expectations of you or your expectations of what your job is.

[00:15:10] **Tim:** Or you just didn't even understand what the skill that you thought you were great or like, you know, cus, cus, like, customer centric or something, you know, it's like, well, when have you ever talked to a customer? Well. I don't talk to customers, but I make sure that the, you know, the customer has what they need when I build this feature.

[00:15:26] **Tim:** I'm like, okay, I can see that's a valid point. So it's like, there's a lot of, even though it's like, they're supposed to be, to try to narrowly, you know, define what the skill is. It's like, there's different lenses to look at it through. So.

[00:15:38] **Adam:** for

[00:15:38] **Carol:** Can I throw one thing into what you said, Tim? So you said that you just put the like, the middle row, right? The meets expectations and I've been on both sides, right? So I've had to do the evaluations on employees and I've been the one doing my own evaluation and I go the opposite. I go, I'm going to put a letter above middle row for everything and even the top for something.

[00:16:00] **Carol:** And if you want to challenge me on it, fine. Like say I don't do it, I'll accept it. But if you're cool with me just looking like a rock star on paper, then that's better for me in the long run. So I'm like, all right, that's just now on my record and it looks like I'm a rock star. So I'm going to try to get away with it.

[00:16:17] **Tim:** I, I get that. And that's probably because we're at different points in our journey. I'm at the point where I don't want to go any higher.

[00:16:22] **Carol:** Oh, that's

[00:16:23] **Tim:** don't, please do not, do not, do not promote me to any more stuff. I don't,

[00:16:28] **Carol:** Yeah, that's true, that's

[00:16:29] **Tim:** You know, I'm good because it's like, you get high enough. It's like, eventually it's like, if something fails, it's like, they're only going to blame one person.

[00:16:36] **Adam:** Right.

[00:16:37] **Tim:** And I don't want to, I don't want to have my neck on that block. So it's like, let's dial it back a bit. I'm fine where I am. Thank you.

[00:16:44] **Adam:** Keep your neck off that chopping block.

[00:16:46] **Ben:** We used to an evaluation tool at work one time. I don't remember what it was, but it was. One of these things, I think they're called Likert scales, where it's basically a strongly agree,

[00:16:56] **Carol:** Yeah.

[00:16:57] **Ben:** neutral, strongly or disagree, strongly disagree. And it was all these things for other people on the team. And I had to review this one guy and he was just like a, he's a pretty exceptional person.

[00:17:09] **Ben:** And I just went down, I put fives or, you know, like strongly agree with like all the skills and the form would not let me submit it. They were like, you're not allowed to submit with fives across the board. You have to be more critical than that. And I had to go back and tweak some.

[00:17:24] **Adam:** I mean, at face value, that's kind of shocking. But then if you think about it, like,

[00:17:29] **Ben:** I

[00:17:29] **Adam:** Probably the majority of people that would submit that. It would be like the lazy, like, I don't care. I'm just going to give

[00:17:35] **Carol:** All fives.

[00:17:37] **Adam:** Yeah.

[00:17:37] **Ben:** The thing is, it's like, the problem is that there's so, it feels like there's so much judgment, even if you say neutral on something where it's. It's the same idea where when you meet expectations somehow feels like an insult, even though it's like you did what exactly the job described, but you're like, Oh, all I do is meet expectations.

[00:17:58] **Carol:** It just feels gross. Yeah.

[00:18:00] **Ben:** So it feels weird to like, I almost want to, I always just wish there were fewer options anyway.

[00:18:07] **Adam:** well, yeah, cool. So the, that's my triumph. Ben, what do you got going on and who are you?

[00:18:11] **Ben:** Ben, longtime listener, longtime caller.

## [00:18:15] Ben's Triumph

[00:18:15] **Ben:** I am gonna round out our triumphs here with a fourth triumph, nothing to do with technology, but I am at an age now where I'm going to see a dermatologist on an annual basis for, you know, checkups like I do a normal doctor, and, I'm like the only person at this dermatology waiting room that is under the age of, you know, Ninety, I want to say.

[00:18:38] **Ben:** So I am, I am just like the hot middle aged stud and, the two receptionists there, there, there's a check in receptionist and a checkout receptionist, and they're both elderly women. And, they're just so sweet to me. I went to one and I walk up and she just goes, You just have the most wonderful smile, just a wonderful smile.

[00:18:58] **Ben:** And then, I'm checking out and the woman at the checkout says, you know, I could just immediately tell from your face that you are a good man. And I'm like, you know what? I'm going to take it. This is a win for me.

[00:19:11] **Adam:** Don't check my browser history.

[00:19:14] **Ben:** Don't dig too deep here, people. Superficial is what we're going after. But, I don't know. It's very nice. Sometimes I've walked down the street and. You know, I'm very introverted, so when I'm out in public, it's my opportunity to try and practice my peopling skills, so I do try to kind of make some eye contact with people, especially if we're dog people and they have a dog and I have a dog, or if I'm in a store, you know, cashiers and that kind of stuff.

[00:19:42] **Ben:** And, I don't know, as of late, I just feel like people are trying to avoid me, and I'm sure it's all in my head, or if it's people are just becoming less social because of the state of the world and post pandemic, et cetera, et cetera. So, it was just very validating for me to have people react so nicely.

[00:20:01] **Ben:** And so it was, it was very nice.

[00:20:03] **Tim:** Been pulling all the grannies.

[00:20:05] **Ben:** Yo, I had, I, when I was in college, one of the stores that was in the Boston area was this one called Urban Outfitters. I don't know if it's a national

[00:20:14] **Carol:** It's still a store,

[00:20:16] **Ben:** Is it? Okay. Yeah. So they, they had a lot of funky t shirts. That was a big part of what they did. They had a huge t shirt section and they had this one, it was like this beet red shirt and it just said sweet potato on it and I would

[00:20:29] **Adam:** about this

[00:20:29] **Ben:** Do we? Okay. Yeah. And this, this, this, just collected grannies by force and it was pretty great.

[00:20:39] **Tim:** Yeah, that shirt's the unofficial fifth member of the show.

[00:20:44] **Ben:** So triumphs for all of us. Very exciting and very exciting to be back with you guys.

[00:20:49] **Tim:** Yeah, it was good.

[00:20:50] **Adam:** before we move on to have a couple of questions.

[00:20:52] **Ben:** Yes.

[00:20:53] **Adam:** so Carol, how's your golf game?

[00:20:55] **Carol:** Oh man, golf's getting good. I mean, it's so good that we bought new grips for our clubs. We're about to put new grips on it. and when we get back from these next two trips, we're going to start some lessons, but we've been playing every Saturday. So hitting lots, lots and lots of balls. Yeah, I'm getting better.

[00:21:11] **Carol:** I make solid contact. I can hit my driver. Well, I can hit most of my irons. I'm okay with a sand wedge. I can't make contact with a hybrid, a three wood. Or some other club that sits beside my driver. I don't even take the case, the cover off of it. So I don't know what it is, but yeah, most of my clubs I can make solid contact and can aim pretty well with.

[00:21:32] **Carol:** Steve is just athletic and is great at everything he does. So he's just amazing and he's getting frustrated cause it goes slightly left and I'm getting frustrated cause I swung and didn't even hit the ball, you know? So that's kind of the different level of doing great, but yeah, really good. Thanks for asking.

[00:21:49] **Adam:** You're welcome. Yeah. So, I'm the guy, I went back and listened to episode 200 to see like what we said we were going to do over the break.

[00:21:57] **Ben:** I have zero recollection

[00:21:58] **Ben:** that

[00:21:59] **Carol:** can't remember at all. Yeah.

[00:22:01] **Adam:** And, Tim, you were, you were going to go be a co host on the Joe Rogan podcast. I guess that didn't work out for you.

[00:22:07] **Tim:** Yeah, it didn't work out for me. We got, yeah, very, very much political differences there. So, I believe in facts. So,

[00:22:19] **Adam:** Oh That's I don't even want to get into that. Let's just move right past that. Anyway, so

[00:22:26] **Tim:** I mean, but if we could start a beef with this show that I think it'd be great for ratings.

[00:22:29] **Adam:** yeah, you know what I would I would absolutely welcome Joe Rogan on us on his

[00:22:34] **Carol:** Please do. Yeah.

[00:22:37] **Tim:** if you're gonna ask me about mine, yeah, I've, I've determined that trying to print a Iron Man costume for my son,

[00:22:44] **Ben:** right.

[00:22:45] **Tim:** I could probably just buy a, I could probably just buy him a car instead.

[00:22:48] **Carol:** Yeah.

[00:22:49] **Tim:** After I figured it all out and then I talked to him about it, he's like, yeah, I'm not that into him. Like, okay, I'm not doing it then.

[00:22:55] **Tim:** I'm there's no way I'm not. But he's there. Yeah. You gotta be hot and I'm like, oh, come on, man. All right. Fine. If you're not into it, I'm not doing it. So, and yeah, I'll just buy you a car instead or something.

[00:23:08] **Carol:** Yeah. 'cause that's a lot of like material and just time and redo over and over.

[00:23:13] **Tim:** mind the time, but yeah, just, I imagine I could probably get it. I did the math. I'm like, wow, this is a lot more expensive than you think doing it yourself is cheaper. No, I know a Filipino guy. in the Philippines who like will do the whole thing for like 2, 000 and just ship it to you.

[00:23:32] **Carol:** Wow.

[00:23:33]

## [00:23:33] LLMs vs StackOverflow

[00:23:33] **Adam:** All right. Well, then I guess that brings us to today's main topic, which is LLMs versus Stack Overflowso I guess i'll just start by saying like me personally. for years now I have Not been posting many questions on Stack Overflow. I would say like, On average, maybe every other year, I would go to post a question on Stack Overflow and the process of like typing it out and rubber ducking it to that text area because I know how pedantic and like, well, but did you do this?

[00:24:03] **Adam:** And did you do that? Did you do that? So I know that those are going to be the immediate questions. And so I try to get ahead of them and answer them in the And usually by going through the process of trying to ask the question well, I figure out the answer. Even then, I'm only doing that like every other year.

[00:24:20] **Adam:** And I think that it's a, it's a reflection on the type of work that I'm doing, right? It's, I'm facing challenges that are maybe not necessarily coding related, right? I'm like doing scaling stuff or infrastructure stuff, which is a little bit different than how do I do this with code? And so a lot of the stuff that I look for ends up taking me To server fault or, or whatever.

[00:24:42] **Adam:** And then, I think me personally, especially over like the last, six months, I've really started to embrace asking chat GPT stuff. Like for example, I'll just throw one out there. we continue to be hit with, credit card fraud attacks. I, as I brought up on the, on the past on the show, we had one start on New Year's day and.

[00:25:05] **Tim:** It took us, it took us like a good four or five days to finally like Make enough changes and get it locked down enough that the person finally was like, okay, I'll move off to somewhere else that's a little easier to deal with or whatever. they like charging the card to see if it was a good card?

[00:25:20] **Adam:** yeah, so this is what it looks like is we are getting a lot of attempted donations, which, hey, sounds great, but then you realize like, wait a minute, these are fraudulent and they're going to need to be refunded. And, Meanwhile, you know, let's say, so actually,we use CAPTCHA on our giving form and we try to, we prefer the reCAPTCHA v2 invisible mode, because like for 90 percent or whatever, like the majority of legitimate users, Never see anything except they might see, they might notice the little reCAPTCHA logo down in the corner of the screen that's like, it's there and it's doing its thing.

[00:25:54] **Adam:** And then if you look a little fishy, or if it's just can't figure out whether or not you're human, then you'll get the, you know, click all the pictures of the bicycle or whatever, right?and through this, we finally, got smart enough to like, you know, think about how would we try to circumvent our own protections, right?

[00:26:11] **Adam:** Like, try to attack yourself. And because of the, that. angle of thinking, we, ended up finding two different services where you can pay for a person at a screen in another country to answer CAPTCHAs at like, as an API. I don't, I don't, and it's not expensive either. It's like 20 bucks for a thousand or something like that, or it might even be like eight bucks for a thousand.

[00:26:34] **Carol:** Wow.

[00:26:36] **Adam:** and it's not just reCAPTCHA, it's like maybe 10 different CAPTCHA, you know, Cloudflare and Amazon and. All the, you know, and Google's recapture and all this. And, and yeah, it's a person at a keyboard that's just sitting there doing the work. And, you know, they're getting paid for their work. And meanwhile, people are doing credit card fraud.

[00:26:55] **Adam:** Anyway, why did I get into credit card fraud?

[00:26:57] **Ben:** Did you solve it?

[00:26:58] **Adam:** Oh, oh, oh, yeah, we, we did do that. we did, you know, it's,

[00:27:02] **Carol:** Stack overflow.

[00:27:04] **Adam:** let me talk.we did finally get this current carding attack pretty much behind us, I think. You know, knock on wood here, but, one of the things like when, you know, you're always, we're always kind of searching for like signals.

[00:27:17] **Adam:** How can we determine that this looks suspicious? Right. And there's some things it's like, okay, if it's just like 10 characters and there's no vowels in like the email address or in the name, right. That it's all consonants. That's. Pretty unlikely to be a person's actual name, right? Like that, it's kind of just a gibberish thing, right?

[00:27:36] **Adam:** And there's, so some, you start to notice these patterns, right? Like, or first name. And then first name with three numbers after it.co as the, as the email address. Something like that. Anyway, one of the signals that we decided was actually pretty relevant is the, the rapidity of. of attempted transactions, right?

[00:27:55] **Adam:** So if we're getting our typical,you know, gifts per minute or something, let's just call it that, or let's say gifts per 10 minutes might be three for a average customer. and so when that jumps up to 15, that's a, that's a pretty good indicator that something fishy is going on, or they're having a really good day.

[00:28:14] **Adam:** Either way, we should be aware that, That's happening. Right. So, I, and our first crack at it was like, okay, well, you know, just do select some information group by a 10 minute period or whatever and get the counts and it just, it smelled off to me. I was like, there's, this can't be the best, most efficient way to look for this type of signal.

[00:28:37] **Adam:** And so I was just like, I didn't even, you know, I've gotten to the GPT are really lazy, I'm like, oh, you know, minutes between records, how, you know, like,

[00:28:48] **Carol:** Oh, I know the feeling. Mm

[00:28:50] **Adam:** and it's just like it figures out what I want and then it, and then it, gave me two different ideas to try and I haven't tried them, but I'm like, yes, this just looking at them and how it like, Describes the approaches that it's taking.

[00:29:00] **Adam:** Like, okay, that's, that's what I kind of knew in the back of my mind was going to be possible. So I, I took that information and I passed it off to one of my coworkers who was already going to be the one to work on that. It's like, here's some extra stuff. You might want to consider these, but it's just like, yeah, that, that felt good.

[00:29:15] **Adam:** And it took a minute to type that out and get the response. I'm like, it's just, just as sad as it is to say, like, I don't know. I kind of am of two minds about using LLMs for this type of stuff. It's based on, I guess I don't like it because it's trained on quote unquote public data, but then it's like, it's kind of taking the credit for other people's work, right?

[00:29:40] **Adam:** and, and that just gives me the ick a little bit, but as the person consuming it, it, it's nice. It saves me time.

[00:29:49] **Ben:** I thought about it the other day, almost in the terms of the shop local movement, like I can buy a book from Amazon, or I can buy a book from the local bookseller in town. And I, and to me, the LLMs are kind of like that. It's like, yeah, I could go to the big name store and use the LLM, or I could go to someone's website and look at an article they wrote.

[00:30:10] **Ben:** That feels to me like shopping local, like I'm still giving them the love for the effort that they put in. But. I mean, certainly, I've been using ChatGPT.

[00:30:20]

## [00:30:20] Detecting Fraud at Adam's Work

[00:30:20] **Tim:** About your issue though, did they actually charge the card? Did they actually do a transaction or they

[00:30:24] **Adam:** We're going back to

[00:30:25] **Carol:** We're going back

[00:30:26] **Carol:** Yeah. Yeah. Um,Oh, no, no, no, it's Tim's money brain, you know?

[00:30:31] **Adam:** Yeah, it is. And so I'll, I'll actually, I have some really interesting stats to share too. So, I mentioned we use reCAPTCHA and so we have some data on, you know, how many of those were successful and failed and stuff. So, I'll just say like for one particular day, we saw about 14, 000 rejections from reCAPTCHA.

[00:30:49] **Adam:** So that's like, they couldn't even get past the CAPTCHA to submit the form. We saw Another 3, 600 or so that were rejected by the payment gateway. So the, it was just like invalid credit card data basically. and then there were approximately 50 that were successfully charged. So those 50 will have to be refunded.

[00:31:11] **Adam:** and you might have to, about of those 50, I would say maybe 30 to 40, had like legitimate email addresses. And the question is like. Well, I know for a fact that some of those people saw that email and open it. Cause you know, you get, event webhooks back from our emails. Right. So, I can see, okay, this person received the email, it was delivered.

[00:31:32] **Adam:** They opened it 12 times and then they marked us as spam. Like, I have a pretty good picture of what's going through this person's mind right now. They're like, I didn't make a gift. This is definitely spam. And they mark it as spam. It's like, we're going to have to, not us, but like our customers, unfortunately, you're going to have to like reach out to the person and say, like.

[00:31:50] **Adam:** I'm sorry that this happened. You might want to check on your credit card information. you know, we're going to be refunding the gift. Would you mind not marking this, you know, undo the spam thing just to, make sure that you continue to get our emails sort of thing.

[00:32:04] **Tim:** Yeah, the reason I ask is because we had, over the holidays, we had the same carding attack that one of our customers faced. And what we wound up doing was turning on, because they were just run the card, trying to do a sale, like they're doing a dollar. And I'm sure they just take whatever they, whatever the dollar is, and they go take that card somewhere else and say, okay, this is because they bought, basically they bought a whole bunch of card numbers.

[00:32:27] **Tim:** They're trying to figure out which ones are good. we turned on, address verification system. So a VS, so if you don't supply the correct zip code, then it's not gonna, it's not gonna charge the card. And so it doesn't really give them any information. So turning that on actually in this case, really helped 'cause chances of them getting the correct zip code.

[00:32:48] **Tim:** 'cause typically that's not in the information they were buying, they were using, they were charging the, they had the card number expiration, I guess the CBV and they were putting the same person's name and same address for everything.

[00:32:59] **Adam:** Yeah.

[00:33:01] **Tim:** so once we turn on AVS where they had to put in a zip code or it would decline, it wouldn't even try to charge a card.

[00:33:07] **Tim:** It would just, when they tried to enter it, it would say, no, this is wrong. Drop

[00:33:11] **Adam:** I think that some stolen credit card data sets like includes the name that goes in the card. And then because of all the other data leaks that happen in the world, like it's probably not that hard to go, okay, here's a Tim Cunningham. Let me try, you know, let me see if I can find an address for you, right?

[00:33:28] **Adam:** All I need is your zip code for the CVV or, or not for the CVV, but their AVS. yeah, so we, we do have AVS on, another thing that I think we're going to give ourselves the option of, is like, it'll be off most of the time, but like, if that signal says, Hey, wait a minute, gift volume is way up. We might be able to turn on, cause if it looks like we're being hit with a carding attack, we might be able to turn on a thing that'll do.

[00:33:51] **Adam:** Like an email based MFA before your gift is actually charged, right? So you give us your, fill out the gift form, all of that. And then at that last step, like when you hit submit payment, it's actually going to make a quick round trip to say, do I need to do an MFA first? And if it does, it'd say, okay, pops up a text box and says, we just sent you an email, enter the code there.

[00:34:13] **Adam:** and then when you do, then it submits the payment. So at the very least, you'd have to have an email address that, That, you have access to. And then if, then you have to, if you still want to try to like, continue and you're willing to do that, then you have to have either all of your gifts go to the same email address, which makes it easier to track them down and, and mark them as fraud and refund them and everything, or you have to have a bunch of different email addresses to, to send, to, to try with, and,You're probably, if that's your approach, you're probably going to use that same email address over and over until you get a successful charge.

[00:34:52] **Adam:** that gives you something else you can track.

[00:34:54] **Carol:** Yep.

[00:34:55] **Adam:** Then, then you've got 40 failed gifts and one successful, all to the same email address. That's just another useful signal.

[00:35:01] **Ben:** And just for the listener's benefit, Adam is indeed saying GIFTS with a T and not

[00:35:07] **Adam:** Oh, yeah, no, no. you won't hear me say, the, the animated image format with a, with a J sound. I, one of my love, love languages is sending and receiving GIFs.

[00:35:19] **Tim:** Yeah. Yeah. Yeah.

[00:35:21] **Adam:** this case I am saying gifts.

## [00:35:26] Outsourcing Payments

[00:35:26] **Ben:** So I know with payment processors or payment gateways, I don't know what the right terminology is here. You often have two options. One option is you can embed. Payment intake into your own application, or you can shuttle people to a, like, I'm sure Stripe has a hosted version of a payment page, and I'm sure Braintree has a hosted version of PayPal, I'm sure has a hosted version.

[00:35:50] **Ben:** I wonder if you use a hosted version, which obviously comes with branding trade offs and workflow trade offs. Does something like this get handled, I don't want to say better, but is it, do you think that like, this is their whole job is figuring this stuff out? Do you think they have more mechanisms in place, or do you think this kind of an issue?

[00:36:11] **Ben:** It's just going to be an issue regardless.

[00:36:14] **Adam:** That is a very loaded question and I can tell you there are multiple angles that I want to answer it from. so

[00:36:21] **Ben:** If only you had a

[00:36:21] **Adam:** at your, yeah, yeah. To, to answer your question directly. I do think that if we were to kind of switch to, okay, when you click pay now, it like, you know, Redirects you over to, you know, a Braintree hosted page where they have the credit card form, they do it.

[00:36:38] **Adam:** And they're then at that point, they're the ones responsible for all the fraud detection, all of that. It totally takes that burden off of our shoulders. however, like you said, there's a, there's going to be some branding challenges there, all of that. And. I don't know how true this is, like I haven't actually seen a scientific study, but the sort of the gut feeling in the circles that I run in for this type of work, for the payment collection stuff, is that the on page experience where you don't have that branding change, people believe that it converts a little better.

[00:37:12] **Ben:** I would, I would believe it. I would believe it.

[00:37:14] **Adam:** Yeah.

[00:37:15] **Tim:** Me too.

[00:37:15] **Adam:** say when Adam said the, the groups like he runs with, with the payment processing things, all I could see is like Adam at a biker bar in like a leather jacket

[00:37:24] **Adam:** yeah, yeah,

[00:37:25] **Carol:** talking about, yeah, like, I know payments, ask me.

[00:37:30] **Carol:** Yeah, on my, on my denim jacket on the back, it's just a giant patch. Ask me about my payment solution.And so I'm the opposite from what you guys just said. For me, if I'm on the site and anything looks slightly suspicious, if I go to make a payment and they direct me to like another, like truly trustable source, like, Oh, you're going to go to PayPal to pay this, or I'm very obvious, like on some other, other interface, I'm like, I feel safer now.

[00:37:59] **Carol:** This makes me much more like happy to make this payment. Cause now I know you're not handling my data.

[00:38:05] **Adam:** I agree with you. And I, I just, that's the thing is it's like, we are tech people. We understand the risks and the challenges of doing it on our own site versus going to the professionally hosted, like payments is all we do people. the other thing that I wanted to point out too, is you may not know it, but if I told you, like, if I, if I took you to,an e commerce store that uses Shopify and you go through their checkout process, you're Then you would go, Oh, that looks like the checkout process of a hundred other stores that I've used, right?

[00:38:36] **Adam:** Cause it, it's all their store, but then it just takes you to a page that this is very clearly the exact same template. and I, I have a feeling that that's kind of what Shopify is doing. It's like they're doing the, the, it's probably for PCI compliance as well to like segment there. Here's your store versus here's the payment page.

[00:38:57] **Adam:** So that only the payment servers and stuff have to be better protected.yeah, but, and also I imagine it probably has a little bit of that, like warm, cozy feeling like Carol was talking about, so I will say since I'm on, on my soapbox already, I fricking hate the shop app.

[00:39:17] **Carol:** It's so bad.

[00:39:19] **Ben:** What

[00:39:19] **Adam:** buy something from somebody who has, I'm getting there.

[00:39:22] **Adam:** You buy something from somebody

[00:39:24] **Carol:** Geez, Ben, come on.

[00:39:26] **Adam:** who uses Shopify, right? They have their online store. They use Shopify. You buy something from them and it's like to track your, your package, download the shop app. They won't just give you the freaking tracking number. You have to like download the shop app

[00:39:38] **Tim:** Which one's access to your email?

[00:39:40] **Carol:** Yeah.

[00:39:42] **Adam:** And, and you don't have to give it access to your email, but like, they're like, oh yeah, if you just give us access to your email, then we'll read all of your emails. And when you get confirmation emails from our stores, we'll automatically add your packages to be tracked, which is,

[00:39:56] **Ben:** Well, that sounds

[00:39:57] **Ben:** sounds roundabout.

[00:39:58] **Carol:** Sketchy.

[00:39:59] **Ben:** Your, your Dust Bunny 3D printed vent covers, is that, do you sell that through Shopify or that's through Etsy?

[00:40:08] **Adam:** I sell that stuff through Etsy. Vent sawdust, my

[00:40:11] **Ben:** Yeah. Sawdust. Sawdust.

[00:40:13] **Adam:** dust bunny vent covers.

[00:40:15] **Carol:** I was like, well, where are we going with this?

[00:40:18] **Adam:** I had no clue what you were talking about for a second. I was like, is there, is there dust flying around behind me? Like,

[00:40:22] **Ben:** Yo, quick aside, because we were talking about payment gateways and I mentioned Braintree on Netflix. There is a documentary about the guy who created Braintree. Braintree. But it has nothing to do with Braintree, he's this bio longevity lifehacker guy who's like

[00:40:39] **Ben:** trying to reverse his aging. We watched it the other night, it's very bizarre.

[00:40:44] **Carol:** Yeah.

[00:40:45] **Adam:** I think I might've been hearing a bit about him. Just like there's, there's the whole like longevity kick that's been going around like social media and YouTube and stuff lately, but,

[00:40:52] **Carol:** Millionaires with the ability and time to just do what they want.

[00:40:57] **Tim:** Right.

[00:40:57] **Adam:** their houses burn down just like everybody else's in

[00:41:00] **Ben:** Oh my gosh. Yeah.

[00:41:01] **Carol:** That's so

[00:41:02] **Tim:** on out there

[00:41:02] **Carol:** Yeah.

[00:41:03] **Ben:** is, this is just for context, people listening. This is being recorded the day after there was three massive wildfires in the LA metropolitan area

[00:41:12] **Ben:** in California.

[00:41:13] **Carol:** They're still there. Yeah. They're not, um,

## [00:41:16] LLMs

[00:41:16] **Tim:** So on the topic of LLMs and AI and that's where I

[00:41:19] **Carol:** Oh yeah. That's where we started.

[00:41:22] **Ben:** What are we doing here?

[00:41:23] **Tim:** I know. Right. So I was looking at Axios article today and people, you know, my son is like finishing up his computer science degree and it's like, so there's a bunch of people that are saying, you know, like, CS grads might honestly be cooked right now because they're looking at the new.

[00:41:39] **Tim:** 03, I think it is, model for ChatBee. And like, it has like, like a very high degree of understanding of mathematics, like a, like a college level mathematics. So they're saying that these, these, these new models can do, which that, I mean, that more than anything is amazing to me that I can reason on mathematics.

[00:41:59] **Tim:** and then other people are like, yeah, but you know, there's still going to be new things that need to be built. So don't worry about it. So it's like. I don't, do I go to StackOverflow much? No. Do I even ask GPT? Occasionally. It's kind of a rubber, a good rubber duck in my opinion.

[00:42:18] **Ben:** Well, but here's, sorry, go

[00:42:20] **Tim:** that's about it.

[00:42:21] **Tim:** But that's about it. But it's like, you know, this concern that, that these, New graduates aren't going to have a role to fill coming out of school because you just use chat GPT. It's kind of scary.

## [00:42:35] Dunning Kruger Effect

[00:42:35] **Ben:** It is scary, but I don't know how much I buy it. And here's the thing. I'm sure we've talked about this on the show before, but there's this sort of cognitive bias. Where when you know a lot about a particular, domain, you don't trust other people who talk about that domain because you have so much deep knowledge.

[00:42:55] **Ben:** So they say something you're like, oh, that's totally BS what you're saying. But the second you hear someone talk about something that's outside your domain of expertise, You implicitly trust them. There's no doubt because who are you to question it, but you forget how many times people talk about the things you're knowledgeable about and it's awful.

[00:43:11] **Ben:** And that's, that's kind of the lens that I look at some of this LLM stuff where. When I'm asking it questions about how I should be implementing work that is involved in something I'm actually quite knowledgeable about, it's very clear to me where the reasoning is off, or I just don't like the way that they did something and I can do something else.

[00:43:32] **Ben:** They're using an old strategy and I can use a newer strategy that makes more sense. But the moment I start asking it questions about things I don't really know, It feels like I have, I have no idea how to validate any of this stuff and I'll start, I'll go like the, like, like I was having a conversation with, with ChatGPT about accessibility on websites and, you know, like, what should I be concerned about?

[00:43:57] **Ben:** How do I associate form labels with form fields? You know, what, when should I worry about ARIA roles? How do I worry about keyboard accessibility? Like that kind of stuff. And it, you know, talks super confidently about how it's supposed to be organized. And like, all I can do is accept it, or I can go and like read a whole book about accessibility and start doing hours of research on the web.

[00:44:20] **Ben:** And at that point, I feel like I might as well just have done that. So I don't know, I don't know how to balance the, the fine tuning of something I already know versus the kind of blind acceptance of something I have no idea about.

[00:44:34] **Adam:** Or you can use SvelteKit and it'll give you warnings in the compiler. Boom! Did

[00:44:39] **Carol:** You

[00:44:39] **Ben:** Right off the

[00:44:41] **Ben:** bat, episode 2. 1.

[00:44:43] **Adam:** it!

[00:44:45] **Carol:** So kind of to add to, to what Ben and Tim both said a little bit, like, I think that the ability for someone to come out of school and be able to catch up might be slightly harder because it's easier for someone who's experienced like us to take the information from, for me, it's Copilot, we use Copilot.

[00:45:05] **Carol:** So it's easier for me to take the information from Copilot and kind of decipher like what I know based off what it's telling me and how to make That answer be correct for what I'm trying to accomplish. Someone coming out of school is going to have a hard time just taking that and having a truth of, like you were saying, just trusting that it's real, but that's not actually going to work.

[00:45:26] **Carol:** So I think you're going to, I personally think you're going to see more value in experienced engineers and their ability to use these tools than, than new people coming out of school, being able to use the tools, because you need to experience the experience to understand like what you're doing with it.

[00:45:43] **Tim:** yeah. That's a good point. So my issue with some, the thing I like about StackOverflow and answer sites like that is Cunningham's law, right? Good old, my good old uncle Ward Cunningham. So it's like, even some of the wrong answers I learned something from. Yeah. Right? So those times that it's, it's not the answer to the original poster's question, but actually it might be somewhat related to mine because the search term hit it.

[00:46:09] **Tim:** Right? And so that it could be tangentially could get me going. The most important is like when someone posts something very confidently and says, this is the answer and all of you other guys can suck eggs. And then there's, there's, there's five responses underneath where people are going, no, here's why you're wrong.

[00:46:26] **Carol:** Right. Here's a documentation.

[00:46:27] **Tim:** Yeah, exactly. Right. And that's, that's Cunningham's law. The best way to get an answer on the internet is not to ask the question, but to post the wrong answer. And then people are very quick to tell you the wrong answer. You don't get that with ChatGPT or the, these, these smart agents. So maybe what we need is you need like multiple agents, right?

[00:46:45] **Tim:** And so you ChatGPT will, will, will give you an answer. Then you You ask Llama, tell me how chat GPT is wrong. And then Llama jumps in and goes, whoa, whoa, wait a minute. Did you think about this? And you know, maybe then we'll actually get a real good answer. We need Cunningham's law for AI.

[00:47:02] **Ben:** one thing that I think is really cool about Stack Overflow, and I only ever get to Stack Overflow through Googling for something, and it lands me on a Stack Overflow thread, but these threads last years. So I'll land on a thread where someone posted the original question in 2012. And it was, you know, how do I get this jQuery plugin to work?

[00:47:22] **Carol:** ColdFusion. Yeah.

[00:47:25] **Ben:** And then you scroll down and it's like 2016, someone says, oh, you don't need jQuery to do this anymore. Now there's a browser, API. And then someone's like, oh, but it doesn't work in Firefox or Safari yet. And then you're scrolling down and it's like 2022 and you're like, oh, this has been available in all the browsers for the last three years.

[00:47:41] **Ben:** And it's like, you can, you get this sort of condensed. Evolutionary understanding of how a feature has evolved. And I find that super fascinating, especially when I'm still doing something that's in like the, uh, 2018 era. And I'm like, oh, now people have come back and said, oh, in 2024, it's actually an easier way to do this now.

[00:48:01] **Ben:** And I just learned something by scrolling through this thread, looking at the evolving answers. I think that's, ah, just, it's in, it's cool. Right place, right time kind of a thing. Plus also, if the LLMs are all trained off of public data and we stop using public sites to generate new data, like don't the LLMs just slowly get worse and worse?

[00:48:23] **Tim:** That's the poison pill theory.

[00:48:24] **Carol:** Yeah.

[00:48:25] **Ben:** plus we need to connect with people.

[00:48:27] **Adam:** Well, it'll be interesting to see how it all shakes out. All right, let's let's wrap it up there. so my dudes and my dudette, it has been so good to see your faces and to hear your voices again. I'm super glad we're back.

[00:48:39] **Carol:** fabulous.

[00:48:41] **Ben:** Triumphant return.

[00:48:43] **Adam:** Yeah! And I look forward to seeing you again next week.

## [00:48:46] Patreon

[00:48:46] **Adam:** this episode of Working Code is brought to you by having the face of a good man and listeners like you. If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs. We could not do this every week without them.

[00:49:06] **Adam:** Special thanks, of course, to our top patrons, Monte and Giancarlo. Thank all of our patrons for continuing to support us through our little hiatus there. I'm gonna beat Tim to it, just say your heart matters. Your heart matters the most! we're not done, I'm not done with the outro here, I'm just saying like this is a little, an extra, this is an extra heart matters.

[00:49:27] **Adam:** Um,sorry Tim, I didn't mean to give you a heart attack, your heart matters too Tim,

[00:49:31] **Tim:** Stole my line.

## [00:49:33] Thanks For Listening!

[00:49:33] **Adam:** We are going to go record our after show. We have a couple of things in our, document that doesn't exist that I'm going to tease for you here. we're gonna talk about one of my kids is coming up on a birthday. And so I got his birthday wishes at dinner tonight. He asked for a trip to Mars and an iPhone 19 Pro Max. that's where we talk a little bit about that. And, somebody, I'm not going to say who, wrote down avoiding Ben on the sidewalk. So, we'll, I guess we'll see what that means and get into that. If you want to help us out and, and hear stories like that and more, you can, go support us on Patreon. Go to patreon.com/workingcodepod. Throw us a few dollars and we'll throw you a few extra minutes of episode every week.

[00:50:18] **Adam:** We'd love to have you on board. You can always join our discord. It's totally free and open to the public. Go to workingcode.dev/discord. Come get welcomed with a welcome to the party pal gif. and, and, and hang out with cool like minded people like yourself. That's gonna do it for us this week.

[00:50:33] **Adam:** We'll catch you next week. And until then

[00:50:36] **Tim:** So, your performance review is in and your heart matters.

[00:50:45] **Ben:** Ah, lovely.

[00:50:46] **Carol:** Nice.

[00:50:47] **Adam:** done. Nicely done.
