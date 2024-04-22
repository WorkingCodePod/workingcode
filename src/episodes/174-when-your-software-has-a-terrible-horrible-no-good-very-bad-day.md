---
title: "174: When Your Software Has a Terrible, Horrible, No Good, Very Bad Day"
description: "On today's show, we talk about incidents and outages at work."
date: 2024-04-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/174-when-your-software-has-a-terrible-horrible-no/id1544142288?i=1000652720254"></iframe>

On today's show, we talk about incidents and outages at work. Incidents are a fact of life. If you depend on a file system or a database or a third party vendor, at some point, something will break and your service will be degraded. Customers freak out (rightly so); and, it becomes a cross-team effort to try and find the problem, fix it, and effectively communicate updates back to your customers. There's no right way to do this. But, one could argue that there are definitely wrong ways to do this.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/174-when-your-software-has-a-terrible-horrible-no-good-very-bad-day.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** for me, I never really had reservations about when we, like when I, when it was clear that I did not know what I needed to know to fix a problem. And I was the one on calls like, okay, well, I have to escalate, right? That's, that's my job is to be here so that somebody else could, not have to deal with this, you know, and if it's 80 percent of the things I am able to deal with and the other 20%, I'm not, you know, like, you know, if one of those 20 percent problems comes up, then I escalate.

[00:00:22] **Ben:** Oh, I see you have a very healthy outlook on life and that's pretty commendable.

[00:00:26] **Adam:** try,

[00:00:28] **Tim:** Mr. I got it all figured out.

## [00:00:50] Intro

[00:00:50] **Adam:** Okay, here we go. It is show number 174. And on today's show, we are going to talk about when your software has a terrible, horrible, no good, very bad day. I did it. First try.

[00:01:02] **Ben:** Uh

[00:01:02] **Ben:** That was a mouthful.

[00:01:03] **Adam:** Yeah. but first as usual, we'll start with our triumphs and fails. We'll get the whole crew back, but as it happens, I'm going to go first.

## [00:01:11] Adam's Fail

[00:01:11] **Adam:** So, I've got a little bit of a fail for us and my fail is that my fingy hurts.

[00:01:17] **Carol:** Oh, no.

[00:01:18] **Adam:** I got a splinter two weeks ago in my thumb, just like handling some, some construction lumber at Home Depot. And, you know, I, yeah, I tried to pull out as much of it as I could and everything. And I thought I got it all out.

[00:01:28] **Adam:** And a couple of days ago it started to get like a little bit inflamed or whatever. It's like, oh, that's, that's no good. And, over the weekend it just got real bad.

[00:01:37] **Tim:** they cut it off.

[00:01:39] **Adam:** No, but you can, I mean, even at

[00:01:41] **Carol:** Oh, it's all red.

[00:01:43] **Adam:** it's all red and then like, there's like a sort of a white spot in the middle.

[00:01:48] **Adam:** So I thought maybe there was like a little puss pocket in there. And so I like tried to pop it with a needle from my wife's sewing kit and that wasn't

[00:01:55] **Carol:** it worse.

[00:01:57] **Adam:** and, and I took my pocket knife and I made sure it was nice and sharp and clean. And I tried to sort of like slice in through the side.

[00:02:03] **Tim:** Hmm.

[00:02:03] **Carol:** Oh,

[00:02:04] **Adam:** see if I could just, I mean, honestly, it hurts a lot.

[00:02:06] **Adam:** Just, it feels just like, you know, when you like hit your thumb with a hammer or something and it like gets, starts to be like throbby from the pressure and the inflammation in there. I can't quite feel my, my heartbeat in my thumb, but it's just constantly sort of at that dull roar throb.

[00:02:20] **Carol:** man.

[00:02:21] **Adam:** And so I was like, I just want to try to relieve some pressure, right?

[00:02:25] **Adam:** That's what I was trying to slice it open for. Well, that didn't work. and so I went in to my doctor's office and saw, you know, asked them to see if they could get it straightened out. and the doctor actually explained to me that like, there's kind of two possibilities with a situation like this. A, yes, you could have like a little pocket of pus.

[00:02:42] **Adam:** And so like popping it would allow the pressure to relieve or whatever. and. He thinks in my case, instead of a pocket of puff, it's like spongy.

[00:02:50] **Carol:** Mm hmm.

[00:02:51] **Adam:** the infected material is like spongy. and so, you know, even because I did get a needle in there, but like, even that just didn't relieve any pressure.

[00:03:00] **Adam:** So

[00:03:00] **Ben:** But so is it, is it infected though? I mean, is that why it's spongy?

[00:03:04] **Adam:** Yeah. And so I, I think just because of like where it is on my thumb, it's like on the inside edge, where like if you kind of just like put all your fingers and your thumb together so you have like a flat hand. It's like right where my thumb touches the last spot where my thumb touches the knuckle of my palm.

[00:03:20] **Adam:** Um,and, I think this like, you're kind of like a calloused material. Cause like I've dropped my phone a couple of times today. Like every time I try to open a bottle or anything like that, it's just like super tight and painful. I'm like trying to like, you know, I was opening my toothpaste with like the wrong finger this morning because it just hurt.

[00:03:38] **Adam:** so I think that's kind of like calloused material cause it's a high traffic spot for me. and so. I think the, the calloused material being infected is why it's like spongy. So they gave me antibiotics, and he picked out as much as he could with, you know, sharp doctor forceps. and hopefully that'll make you feel better.

[00:03:56] **Adam:** But in the meantime, you know, you, you know how you can like feel temperature differences of like different parts of your body. Like, especially for me, I touch it to my lips. I can feel the difference between a finger and this thumb. It's super hot. And

[00:04:08] **Carol:** Oh, it has fever. Yeah.

[00:04:09] **Adam:** Yeah. My thumb is a fever. Yeah.

[00:04:11] **Carol:** It's crazy, but like spots that are infected can have fever to them. So that's awful.

[00:04:15] **Tim:** hope you,

[00:04:16] **Carol:** It makes me think of like when you have one of those ulcers, like in your lip, like there's nothing to pop. It's just like, like a little round spot. That's just like that.

[00:04:25] **Adam:** Yeah. A canker

[00:04:26] **Carol:** spongy.

[00:04:27] **Carol:** Yeah. Yeah. So painful.

[00:04:30] **Tim:** well, I hope you get to keep your thumb. Hmm. Mm

[00:04:32] **Adam:** Me too. I hope so too. I appreciate the thought.

[00:04:36] **Ben:** Yeah. Is

[00:04:36] **Adam:** Thoughts and prayers, right?

[00:04:37] **Ben:** affecting your ability to type? So my right thumb, the only thing it really does is hit the space bar.

[00:04:44] **Adam:** it's my left thumb. and yeah, fortunately it's on the opposite side, right? So you hit the, I hit the space where it's like the opposite, the outside of my thumb and this is on the inside.

[00:04:52] **Ben:** So it's

[00:04:53] **Carol:** you got lucky. Yeah.

[00:04:55] **Ben:** Man.

[00:04:55] **Adam:** That's me. My fingy hurts. How about you, Ben?

## [00:05:00] Ben's Fail

[00:05:00] **Ben:** I'm going to go with a fail, which is that apparently I'm not spending enough time learning about AI.

[00:05:08] **Carol:** What?

[00:05:08] **Ben:** Uh,yeah, apparently that's like what you got to do these days. The, the hype train is definitely in full effect and, every podcast I listen to, it sounds like people are just talking about how it's going to revolutionize everything.

[00:05:20] **Ben:** but, but one thing that I do here and would, is that you really have to sit down and Actively try to learn how to use things like chatGPT effectively, and maybe even try to use them, kind of how you would learn regular software practices by actually building something. You can't just do a little of this and a little of that every now and then and expect to, you To get better at it.

[00:05:44] **Ben:** Apparently you actually have to attack it, you know, yeah, with some sort of destination in mind. And, and that is not how I've been using it. I've been using it kind of like a, like an alternative to Google searching. And, and I mean, this is just one perspective, obviously of, of, of many perspectives, but when I use it as a Google search substitute, I find that it almost always falls short. It gets me very excited at first. I'm like, Oh my God, this is so amazing. Like it just gave me the answer. And then I try it and it's wrong, like every single time. And not only is it wrong, but it's, it's like fundamentally wrong. Like it'll, it'll say like, Oh, just use this, you know, inject this header into your response.

[00:06:28] **Ben:** And then I Google for that header and there's zero references to that header anywhere on the web. So it just completely made that up or. It'll get stuck in these loops where it'll give me a solution and I say, actually, that solution doesn't work. It's giving me this error. Says, oh yeah, you know, I'm so sorry.

[00:06:42] **Ben:** I'm so apologetic about that. Let me try this. And then you do that and it's a different error and you say, well, this version doesn't work. And I say, okay, let me try something else. And they just go back to the previous solution and they just kind of bounce back and forth between two failing solutions.

[00:06:54] **Adam:** I've never had that one.

[00:06:55] **Ben:** Oh yeah. And I don't know, I think it's. the part that gets me frustrated is that I use the free version when I just have an open AI account that I signed up for free. And it's, I guess that's chat GPT 3. 5, I think. And whenever I complain about it publicly, people are like, Oh, 3. 5 is terrible. What you have to do is use the paid version and get, I guess that's chat GPT 4.

[00:07:18] **Ben:** But that just seems crazy. Like, why would I pay for something that is clearly failing me in the free version? Like that's, that's not how freemium models

[00:07:26] **Carol:** no,

[00:07:28] **Ben:** right?

[00:07:28] **Carol:** it needs to be good, and I want the best, right?

[00:07:31] **Ben:** right, exactly. Like, like pull me in with the free version and then get me excited to pay. Right now, I feel like I have to pay to extract any value because, because honestly, I'm just not finding it.

[00:07:44] **Ben:** Very valuable. But I, again, maybe I just don't quite know how to use it or I haven't learned how to effectively have it think through problems for me. I don't know. So that's,

[00:07:57] **Adam:** yeah, what you're talking about there, like having to learn how to prompt it. Well, I've heard referred to as prompt engineering,

[00:08:04] **Tim:** hmm.

[00:08:05] **Adam:** which I forget where I saw this. I really wish I could remember. I want to say I might've heard it on Svelte Radio, which is another podcast. but that's just kind of a guess, that.

[00:08:15] **Adam:** The whole concept of prompt engineering is kind of an anti pattern and that we hope that, you know, we can continue to improve the engineering of the AI stuff. So that, like you were talking about, Ben, you just kind of like throw it a question and not only does it figure out the answer to what you asked, but it like tries to figure out sort of the best form of the question itself and then answers that. but yeah, right, yeah, right now you have to like, sort of give it a lot of context to go with your question to get a good answer.

[00:08:42] **Ben:** right. And I think that's kind of where I start to get frustrated because what I end up having to do oftentimes is just. Read the manual for whatever I'm trying to ask it to help me with. Like, you know, at the best, it kind of points me in the right direction in that it'll tell me that something exists. And then, then I can go to the actual documentation for that thing and learn how it actually works and not the delusions that ChatGBD thinks is how it works. So there is that sort of pointing me in a direction, but. I mean, at that point, I feel like I could have basically done a Google search or oftentimes if I'm looking for something specific, I can go directly to MDN, you know, Mozilla Developer Network.

[00:09:26] **Ben:** I can go directly to the MySQL docs. I can go directly to the ColdFusion docs. Like, most of the time I know kind of in the ballpark where I'm trying to be. I just don't necessarily know how to get there. And, and I'm just, I, it has, I'm, I'm not super impressed. Like I'm, that's not true. I'm super impressed that it works at all.

[00:09:48] **Ben:** That's kind of amazing, but it just doesn't really wow me with the

[00:09:52] **Carol:** it's not good enough for ya,

[00:09:54] **Ben:** Yeah.

[00:09:55] **Tim:** We're totally, we're totally in the hype phase right now with AI, right? Everybody's saying it's, it's going to do this, going to do that. No one really knows right now how much it's going to be a part of our life 10 years from now.

[00:10:07] **Carol:** it's gonna change our world, Tim, just wait and see, just

[00:10:10] **Tim:** it, but how much, right?

[00:10:12] **Carol:** mean, it already is, it's writing our code for us, if you have, You know, Copilot installed, which I think I mentioned that a couple episodes ago, you know, we were in our all hands and our CIO is mandating that it is, well, mandating means mandatory.

[00:10:28] **Carol:** So obviously it's mandatory for everyone to take a class on how to prompt AI for information because otherwise it's pointless. Like you said, it doesn't give you the right information, the right answer, if you don't understand how to ask the question correctly.

[00:10:43] **Ben:** And I'll tell you, I know I've mentioned Ezra Klein's podcast several times before. He's a New York Times journalist and his podcast is continually one of my favorite podcasts, and he just had a recent episode about AI and his appre, not apprehensions, but his, he has frustrations like I do that It's interesting, but it hasn't wowed him over.

[00:11:03] **Ben:** And he has not, he has not figured out how to make it part of his daily life as a journalist. And one of the concerns that he brought up was that so much of the interesting thinking happens in that deep thinking about a problem. And if you go to one of these large language models and say, how do I do this, or help me think about this problem, anchors you to the solution that the large language model comes up with.

[00:11:30] **Ben:** And it's sort of, Prevents you from, from rabbit holing in your mind on the problem more so than if you were just sitting and staring off into space and thinking deeply. And I definitely relate to that. I definitely feel like I know that if I don't know something very well, and I asked Chat GPT how to do it, I'm going to just follow whatever thread Chat GPT lays out for me.

[00:11:54] **Ben:** That I'm, I'm definitely going to lose the instinct to say, does that even make sense? Should I think about a bunch of different options? And maybe that's part of the, the, the prompt engineering that maybe you have to then go back to chat to be able to say, that's interesting, but like, what are 10 other approaches to this?

[00:12:11] **Ben:** You know, you hear things, people say things like that. Maybe that's just

[00:12:14] **Tim:** It'll give you nine

[00:12:15] **Ben:** Yeah.

[00:12:16] **Tim:** or 11.

[00:12:18] **Ben:** And it's, I'm just, I'm struggling and I'm, I'm frustrated because it feels like it's one of those things where it's going to slow me down a lot at first, maybe to try and get better at it before it makes me actually more productive.

[00:12:32] **Tim:** Sorry, buddy.

[00:12:33] **Adam:** Yeah. I agree with you. Like I often feel like I would have been faster for me to just Google it, even though. And it's not even, it's maybe like a third or less of the time that I think, you know, let me ask AI for this. AI can probably figure it out. And even then, you know, more than 50 percent of the time it ends up being, I could have gotten to this answer faster if I just Googled it myself.

[00:12:58] **Carol:** Yeah. But then should you just respond and be like, you're wrong and close the session so that it, it learns that what I did was bad? Like, how do you fix it?

[00:13:08] **Adam:** Go sit in the corner.

[00:13:09] **Carol:** Yeah.

[00:13:10] **Tim:** I'll tell you one thing it is good for though.

[00:13:13] **Adam:** Go ahead.

[00:13:14] **Carol:** Keep going. Don't tell me what's

[00:13:16] **Ben:** to know.

[00:13:19] **Tim:** So creating crazy images. So someone in our D&amp; D group was talking about what if, what if a giraffe was a centaur? And so I drop it in the chat here. that's what, that's what, uh, being created for me.

[00:13:32] **Ben:** Yo, I'm telling you, the image stuff does seem like the most fascinating.

[00:13:37] **Adam:** Yeah.

[00:13:38] **Carol:** It is literally a giraffe with a centaur and abs.

[00:13:42] **Tim:** Yep. Human abs and arms. Yep.

[00:13:44] **Ben:** Love it.

[00:13:45] **Carol:** bizarre.

[00:13:47] **Ben:** All right. So that's me. I'm going to get there. Carol, what do you got going on?

## [00:13:52] Carol's Triumph

[00:13:52] **Carol:** Yeah. Well, you guys are losers for failing. Not really. I still love you, but I'm going to go with a triumph. I typically don't play a lot of games, but I have recently become very addicted to Satisfactory, which is just a game where you build like factory type processes. And my son saw the other day that I was playing on Steam and he, Immediately sent me a link on, YouTube where a guy is comp is, like comparing software engineering to games like Sati or like Factoria and Satisfactory.

[00:14:27] **Carol:** And I realized that I think the reason why I love this game so much is because when I first started it, I built all of the spaghetti, like, mingled together problems of everything was just trying to feed into its own, like, little spot. And then I. And put like all my iron together and all my copper together and all my steel together.

[00:14:49] **Carol:** And now you can follow these very cool paths to get there. And it's so much like, Engineering and software engineering and how we break out division of, like what we're trying to accomplish, that it makes sense why I enjoy playing this game. And I didn't even realize it until my son told me that he's like, mom, it's just how your brain is.

[00:15:09] **Carol:** It doesn't surprise me that you have 110 hours in this game. I was like, holy crap. I've been playing it a little too much.

[00:15:18] **Ben:** That's very cool. I, I don't play a lot of games, but when I was younger, I used to play a lot of games and I always loved the, the sim games, you know, like SimCity, SimTower. And it was that, there was something so fascinating about having to build stuff and then having it run algorithms against what you were building.

[00:15:35] **Carol:** something I, I remember when James was little playing rollercoaster tycoon, I think it was, and that was like the hotness for me was building rollercoasters. I don't know why, but maybe it's the same thing. Just enjoying watching the process and seeing what physics can do with things.

[00:15:52] **Adam:** Yeah.

[00:15:53] **Tim:** Have you seen these infinite combination games?

[00:15:56] **Carol:** No.

[00:15:57] **Ben:** what is that?

[00:15:58] **Tim:** So, so Infinite Craft, it's a game, you start out with earth, earth, wind, fire, and water, and you start combining them, and you can pretty much combine them in almost infinite number of things, and it'll start creating things like Arnold Schwarzenegger and, and then you combine that with a robot and it's Terminator and, and they have like competitions where they'll give you a set of like 10 words and people will compete to see who can get, those words, you know, the fastest.

[00:16:27] **Tim:** and then sometimes you'll tell you if you create something that's never been created before.

[00:16:31] **Carol:** Oh, that's cool.

[00:16:32] **Tim:** Yeah. So it, it's, it's, it's a good time waster, but it's pretty interesting.

[00:16:38] **Carol:** Well, that's me. Tim, what do you got? Bring us home.

## [00:16:41] Tim's Triumphs

[00:16:41] **Tim:** So I could say a fail because now I'm feeling better, but everyone else in my house is sick.

[00:16:47] **Carol:** Oh, no.

[00:16:48] **Tim:** both the kids and my wife are sick and my wife's been sick a whole week. So, this thing that, whatever this nastiness is, seems to last at least two weeks. But, luck will go with that. A few, several weeks ago, so. I mentioned that I had a problem in my IVR where you had to say, say the letters in a policy and it just wasn't working. Right.

[00:17:10] **Carol:** Oh,

[00:17:11] **Tim:** So after being sick two weeks and not really working on the problem at all yesterday, I kind of sat down and said, let me attack this again. And I attacked it again. And then like within 10 minutes, I figured it out and fixed it.

[00:17:23] **Adam:** Nice.

[00:17:24] **Carol:** wow.

[00:17:25] **Tim:** And it turns out. To be the, a bad mistake I made in the beginning. You know how much I hate ORM, right? I just, I despise ORM. Well, I was doing a little logger. I was creating a logger for this, this software. And I'm like, let me just use ORM for this. It's tiny. It's not a big deal. And, yeah, so ORM was breaking, but it wasn't sending me, it wasn't sending me an error report because my error reporter in ColdFusion and Lucy, the error response from ORM, from an ORM error is completely different from a regular error. And so I was expecting to see a certain thing in the error to send that report. Well, it didn't exist. So it was breaking my error reporter. So I'm like, why? There's no error. Why are they saying there's an error? There's no error. And no matter where I on the, you know, was debugging where it was, the logging was kind of taking place in the guts of the program.

[00:18:16] **Tim:** I never thought to look there. So what turned out was I had a field that I was logging and, you know, the thing I was logging was too long. It was just.

[00:18:26] **Adam:** Mmm.

[00:18:26] **Carol:** Oh, no. I

[00:18:30] **Tim:** characters in the database and it was, you know, this thing I was logging was 26. So, so yeah, I found where that was.

[00:18:41] **Tim:** I kind of cleaned up the data a little bit, fixed my, fixed my, error reporter and then extended the database field for that column

[00:18:48] **Carol:** was gonna say, I was gonna say, did you extend the column or like confirm that whatever you were putting in it didn't max out? But you said you, you

[00:18:56] **Tim:** Yeah. and then I'm, yeah, but I fixed my, fixed my logger and then also make sure that, when I was inserting something that I'm checking to make sure it's, Not beyond the column length. Well, that felt good to fix that. Cause I was feeling really stupid. I'm like, man,

[00:19:12] **Adam:** I mean, I'm,

[00:19:12] **Carol:** that was really stupid, Tim.

[00:19:14] **Tim:** I know. Right.

[00:19:15] **Adam:** I'm really glad you fixed it because I've lost so much sleep since you told me that you were having people like read off one number or letter of

[00:19:23] **Tim:** Did you say blah?

[00:19:24] **Adam:** Yeah.

[00:19:25] **Carol:** say A? A.

[00:19:28] **Adam:** Oh my God. Well, I mean, who among us has not had a similar, Like so obvious in retrospect, stupid mistake that you spend so much time trying to, to sort out. I had one of those today, in fact.

[00:19:44] **Tim:** Okay.

[00:19:45] **Carol:** I'm rubbing my eyebrows as you say it, cause I know. Yeah.

[00:19:49] **Tim:** Well, it's just, we have these assumptions sometimes. Like, well, it can't be this, you know? Right. You know, something's wrong. It's, it's obviously the, the VoIP company's problem. Cause I put a ticket in into them and they're like, Nope, we don't, we don't, we don't see. So,

[00:20:04] **Ben:** It's funny that you say it can't be this because that is often my reaction when I'm fixing a very clear bug in the application code, like I'll have misspelled a variable name. And when I noticed that it's misspelled, I think to myself, well, that can't be the problem, but I'll fix it anyway. And then of course it's the problem, but I don't, I don't know why my initial reaction is that, that a misspelled variable name shouldn't be a problem.

[00:20:26] **Ben:** Like that's crazy.

[00:20:28] **Carol:** So often. Yeah.

[00:20:29] **Ben:** on the topic of, of debugging and, and logging, I was listening, I think this was maybe one of the change log, podcasts over the weekend and they mentioned something called Hiram's law. Has anyone heard this?

[00:20:40] **Adam:** I feel like I know the name, but I can't think of what it is.

[00:20:42] **Ben:** It says, it's with a, with a sufficient number of users of an API, it does not matter what you promise in the contract, all observable behaviors of your system will be depended on by somebody. And it ties into this concept of a breaking change and versioning of APIs. And you think, well, if my API was documented to only do X, Y, and Z, then making this small tweak isn't a breaking change because that's not part of the contract.

[00:21:09] **Ben:** If someone noticed that your API did something. Then eventually with a sufficiently large number of users, someone will actually depend upon that functionality. And when you change it, even if it's undocumented, it will break someone's code or maybe more to the point, it'll break someone's integration tests.

[00:21:26] **Adam:** But if it's undocumented and they rely on it, then they deserve what they get.

[00:21:33] **Carol:** So mean, Adam.

[00:21:36] **Adam:** They just, I mean, obviously there's a relevant XKCD for everything, but the, the, do you know which one fits here?

[00:21:42] **Ben:** don't think so.

[00:21:43] **Adam:** It, I'll have to find it and I'll put it in the show notes, but the, Like the, it's like a changelog and comments on a text editor in the, you know, the author's like, Oh, I fixed this bug.

[00:21:55] **Adam:** And then there's a comment that the bug is like, you know, when you hold down the space bar, the, the CPU temperature goes up, right? Like it just like, And, and, you know, somebody is like, oh yeah, I programmed my Emacs to, you know, respond to a 0. 4 degree increase in CPU temperature as this key command. Like,

[00:22:17] **Ben:** Yeah, for real. Oh, good times.

[00:22:21] **Adam:** so yeah, I'll, I'll have to look that up and put it in show notes.

## [00:22:24] When Your Software Has a Terrible, Horrible, No Good, Very Bad Day

[00:22:24] **Adam:** Well, sounds like we should move on to our topic for the day. Tim, would you like to, to lead us off on that?

[00:22:32] **Tim:** yeah. So we talk about when our software has a terrible, horrible, no good, very bad day. And, you know, decades I've been doing this. There's been, there's been several of those that kind of stick out in my mind where, you know, just everything kind of crashes. things come to a standstill, there's some serious, serious issue, whether that be hardware related, network related, software related, or maybe the worst one is when it's a service provider that you depend on and they're having a bad day and therefore your day just got worse, several of those being in the credit card industry, but I mean, I just kind of want to talk about how you get through those days.

[00:23:10] **Tim:** How you survive those. And then also what do you tell your customers,

[00:23:14] **Carol:** And what do you tell your wife when you get home and you can't talk to her?

[00:23:17] **Tim:** right?

[00:23:19] **Carol:** My brain's off. I'm sorry.

[00:23:21] **Tim:** You know, well, typically she just doesn't see me for several days. Cause I'm like, you know, hiding at work and sleep, sleeping at the office. And, you know, it's like, I'll, I'll see you when I see you.

[00:23:34] **Ben:** one, one thing just right off the bat, when you talked about what do you tell your customers? they're, they're sort of the way I see it. There are two large, distinct groups of problems. One is a security problem and one is like everything else. And, and

[00:23:51] **Adam:** Well, then there's three, security, privacy, and everything else.

[00:23:55] **Ben:** sure, sure, sure.

[00:23:56] **Ben:** And I paint with a very broad brush and I'm sure Adam might be able to speak to this more clearly than I am. But I know that a lot of companies have actual. I don't know, regulatory is not the right word, but compliance things where when there is a security related incident, there's actual protocols about how fast customers need to be, let into the circle of trust, so to speak.

[00:24:18] **Ben:** And then on the other half, but it's not security related or whatever else we're going to talk about here. I think it's, there's, there's a, you know, up to the discretion of the company, but, but I just, you know, there's very, there's I see there's like very two distinct types of things going wrong.

[00:24:33] **Tim:** I'm talking, I'm not necessarily talking about where you've gotten hacked or something like that. And I'm just talking about more sort of, there's a, there's somewhere in your stacks of failure, right? And it's, it's not. Because of some outside bad actors that have gotten in. This is just, you know,

[00:24:48] **Carol:** the days, days your application keeps running out of memory and you don't know

[00:24:51] **Tim:** right.

[00:24:52] **Tim:** Right.

[00:24:53] **Carol:** like, nobody else can click okay because it's not doing anything.

[00:24:57]

## [00:24:57] Communicating to Customers

[00:24:57] **Tim:** I'll tell you what the guy, the biggest thing I struggle with, particularly when you're a smaller company, I'm thinking of our early days before we got bought by Constellation Software. Um, you know, you've got typically when you're a smaller company, young company, you have very close relationships with your customers.

[00:25:16] **Tim:** Typically, particularly when it's, you know, Like we're a business to business software, we're not dealing with the general public, we're dealing with a company, an insurance company or that's, you know, taking payments or running their software. So they're not able to do any work because your software isn't working and they want constant updates.

[00:25:33] **Tim:** Right? But at the same time, it's like you can't be on the phone with them all the time talking about the problem because you got to be working with your team to get it fixed. And so finding that balance of, of, communication with the customer and communicating to them what's going on, what steps are being taken versus actually doing your job and getting things running again.

[00:25:55] **Adam:** So. in our incident response plan, which we had to put together for SOC 2 reasons, I think the way I described it is that we have a, a designated person during any significant incident that, that person's primary job is to handle communication. If there are questions coming in, that person is the one to field those questions and that person is also responsible for, posting updates on a regular Timely basis, right?

[00:26:26] **Adam:** If that, it depends on what's going on, right? If there's a, like a big real time thing, then you might want updates every 15 minutes, or, you know, if it's just something that, you know, is going to take half a day or whatever longer to fix. Then you might post updates once an hour or something, but whatever it is, like that, that's sort of like becomes their role in supporting that the incident.

[00:26:48] **Adam:** And then, if they have bandwidth leftover, they might be able to help debug or whatever, but I think setting, you know, what is the word that I'm trying to think of identifying and assigning one person to be the communication manager for the incident is helpful for that specifically.

[00:27:04] **Tim:** yeah, they're the gatekeeper, right?

[00:27:06] **Carol:** when you're a small company, you may not have two extra hands to go put on that communication. You may need the only five engineers you have available to fix it, working on it.

[00:27:18] **Adam:** Well, I think I disagree. And I think that the reason is that by, by having one person who is responsible for the communication and saying like, you know, Steve is going to handle all of the communication, then the other four people or whoever, you know, like you said, if you're only five people, then everybody else automatically knows I don't have to worry about any incoming emails.

[00:27:38] **Adam:** I don't have to worry about posting updates. I'm a hundred percent on fixing this issue. And then that person, if they have any time between communication can help out as well.

[00:27:47] **Tim:** then, I mean, someone's going to have to communicate to the communicator what to communicate, right? So, I mean, that takes time.

[00:27:53] **Carol:** circle.

[00:27:54] **Adam:** So what you do there and what we do in that type of situation is we have like a war room, right? We have a video chat channel, if it's a Google Meet or in a Slack room or whatever. and so you can have that rapid high fidelity conversation. Okay. Here's the status of things, blah, blah, blah, blah, blah. And then that person goes offline and types it up nicely, to post as a new announcement or whatever.

[00:28:16] **Tim:** Run it through chat GPT to make sure it sounds professional.

[00:28:21] **Ben:** I have such extreme

## [00:28:24] Escalating Problems

[00:28:24] **Ben:** anxiety if I am ever the person who has to page people.

[00:28:29] **Carol:** Yeah.

[00:28:29] **Adam:** Mm.

[00:28:30] **Ben:** it's like a real life anxiety dream where there's, it's like that meme. It's like the, the guy who's at the control panel and he's sweating in one, right. And then like the next panel, it's him trying to hit a button. And that button for me is like page the, the on call site reliability engineer, the SRE.

[00:28:48] **Ben:** I, I feel like I can't do it. I can't be the person who has to page another human being. I don't know why I have this extreme anxiety about it, but I would rather anyone else in the world hit that button.

[00:29:00] **Adam:** Yeah, I get it. You don't want to, like, disturb somebody on their time off. Especially, like, the the closest the closer you are to, like, 1am, or 2am, like, that that makes it even worse. Like, I don't mind paging somebody at 9 o'clock at night, but at 2am, that's like that's a big ask. There's gotta be a a real good reason for that.

[00:29:20] **Ben:** And then the worst part is when. There's no one around at that particular time who really is in a position to make that call. You know, it's like the, the people. I mean, you know, I'm only here talking from my own experience. Other companies may operate differently, but it's like, you know, the peons are the ones who are getting paged in the middle of the night.

[00:29:41] **Ben:** It's not like the CTO is not the guy getting paged in the middle of the night. He, you know, and he could ultimately decide who has to get on a call and who doesn't, so it's like, we're all kind of like shifty eyed looking at each other. Like, do we have to page someone? Is this an incident? I mean, I got paged automatically from the software, but do I have to get other people involved?

[00:29:57] **Ben:** This feels weird.

[00:29:59] **Adam:** well, honestly, I mean, maybe I can give you a little bit of perspective that'll help, Ben. you're, I think you're right that, you know, as the saying goes, rolls downhill, right? So, it tends to be the people at the bottom of the totem pole who have the least access and the least experience who carry the brunt of the hours of on call.

[00:30:18] **Adam:** Or at least it can feel that way when you're down there. but, for me, I never really had reservations about when we, like when I, when it was clear that I did not know what I needed to know to fix a problem. And I was the one on calls like, okay, well, I have to escalate, right? That's, that's my job is to be here so that somebody else could, not have to deal with this, you know, and if it's 80 percent of the things I am able to deal with and the other 20%, I'm not, you know, like, you know, if one of those 20 percent problems comes up, then I escalate.

[00:30:46] **Ben:** Oh, I see you have a very healthy outlook on life and that's pretty commendable.

[00:30:50] **Adam:** try,

[00:30:51] **Tim:** Mr. I got it all figured out.

[00:30:53] **Adam:** except my thingy

## [00:30:57] Rushing Troubleshooting

[00:30:57] **Tim:** one thing that's bit me in the past is I'm a person who believes in quick responses at the, I want to be the, you know, I just want to get it out there first. Right. That sometimes can bite you in the butt. So it's like, how many times have you been like troubleshooting an issue and you think you found the root cause and maybe because of tiredness or, you know, Whatever, it was just wishful thinking and the thing you thought it was really just had nothing to do with what the actual issue was.

[00:31:26] **Tim:** And so you, you communicate to everyone, Oh, here's the thing. We found it. You know, we should be able to clean this up in the next 10 minutes. After you send that out and then like people are like, well, you said 10 minutes and it's still, it's another hour. Like, yeah, well, that really wasn't the issue. And now they're like, do you even know what you're doing?

[00:31:41] **Tim:** Are you, are you clueless? Are you a bunch of idiots? So

[00:31:46] **Carol:** The times that Yeah, the times that I've been like looking at a problem, not even like in an emergency situation, but I'll be looking at a problem and I will end up down a whole nother rabbit hole. And I'm going, why am I even looking at this value right now? Like, what brought me to watch this?

[00:32:03] **Carol:** Like, I don't care about this value. Why did I just right click and say, watch this? I don't. I don't need to know what this was doing. Let me go back and figure out where I started. And usually like I redirect myself, but when it's in crisis mode, it's hard to get redirected for me too. Cause then I'm like, Oh, I have to be on the right track.

[00:32:20] **Carol:** I have to be on the right track. Like I clearly can't be wrong. And then usually I am wrong the direction a few times before I get it right.

[00:32:29] **Tim:** you get that little dopamine hit of, Oh, this is it. This is it. I finally found it. Right. And you just, so your brain's like, I can't let this go. And they're like, no, no, no, no, that it has nothing to do with what you're doing.

[00:32:39] **Carol:** And in the back of my head, I'm going, well, I found another problem, so that's okay too.

[00:32:44] **Adam:** yeah, I mean, I would say, we've all been there, you know, we've all gotten burned by, thinking we have the right fix and it's not. And so we communicated that it'll be fixed shortly and it's not fixed shortly. so I think, you know, that's just one of those rites of passage, right? Everybody has to burn themselves a few times that way to, to build up the calluses, so that you slow roll your, your communication on that part, right?

[00:33:07] **Adam:** So, you know, I think at that moment, you just say, you know, we have some leads we're, we're going to continue to investigate. And once you have, you know, passing tests or, you know, whatever it is that gives you high confidence that you're actually got the fix. Then you go, okay, you know, we were testing a fix and you roll it out and you see what happened.

[00:33:24] **Ben:** Well, it's funny. So we have this one SRE, this guy, Pablo Fredrickson

[00:33:31] **Carol:** What's an SRE?

[00:33:32] **Ben:** a site reliability engineer platform guy, and, uh, yeah, DevOps and, his SRE, Default reaction to all incidents was rollback. Like it didn't matter if it was in an unrelated service that has nothing to do with the thing that seems to be broken.

[00:33:49] **Ben:** He was like, did you deploy recently? Roll it back immediately. And everyone else on the team was always like, hold on. I I'm looking through the logs. I'm trying to figure out. He was like, I don't care. Roll back, whatever change you just made, roll it back, even if it doesn't seem relevant. And I'll tell you, like.

[00:34:05] **Ben:** Like 80 percent of the time he was right that it was definitely the last deployment and now is not the time to debug. Just roll it back and remediate the issue. But there is something so alluring about it's on fire and I can look through the logs and I can look at CloudWatch and I can look at the metrics and I can hone into where it's going wrong.

[00:34:23] **Ben:** And, it's a, it's a, I mean, depending on how you see it, it's a balancing act between the customer experience and, and actually not wasting time with. Fixing the wrong thing.

## [00:34:35] Incident Reports

[00:34:35] **Tim:** Our post action incident report, I'll be, I'd say, so I've been the victim of many of times where, you know, services that I depend on were interrupted. Therefore, you know, my service was down and that happened yesterday for like 45 minutes on one of our, one of our payment processes back in processors that we use.

[00:34:56] **Tim:** And knowing this company, it's like, I, you know, I needed an incident report. They will never give me one. I will never, I think out of the 15 years we've been with them. We've got one, and that's because that incident lasted weeks.

[00:35:12] **Adam:** Hmm. That's pretty bad.

[00:35:15] **Carol:** Yeah.

[00:35:16] **Tim:** And their incident report was basically, Oh, we were moving things to AWS Cloud and it didn't really go very well. It was basically what they said.

[00:35:24] **Adam:** Wow. That's pretty bad.

[00:35:25] **Carol:** communicate that? And why do you, so why do you have to remain with the service? Is it the

[00:35:29] **Tim:** We don't, I mean, Not, it's We have multiple servers, they're one of, they're one of many that we use, and it seems like every year or so, I was looking at my text message because I've got the phone number of the, the, the vice president of operations over there and,

[00:35:45] **Adam:** back in February of last year, the exact same issue happened and it happened again yesterday. And it's like, I've never got an answer from February why it happened. You know, that time it was about two hours and this time it was like 35, 40 minutes. it even had like direct phone numbers to some of their developers and they've been trained not to tell me.

[00:36:02] **Tim:** So,

[00:36:04] **Carol:** Don't respond to me.

[00:36:06] **Tim:** yeah, exactly. So just very annoying, but we, we do try to do incident reports. I mean, so we send one out and said, you know, ours was pretty simple and said this third service part, you know, provider that we use for this. Had an outage. They've not told us why that was the reason we were down.

[00:36:25] **Carol:** So have,

[00:36:26] **Ben:** when you say you send it out, are you saying internally to the company or externally to customers? Gotcha.

[00:36:32] **Carol:** and then none of your customers have questioned why you continue to use this third party service?

[00:36:38] **Tim:** Well, they know why, because they're like, you know, if you sign up with a different, with this other, you know, but that requires work on their part. So they don't do it.

[00:36:45] **Carol:** Okay.

[00:36:47] **Adam:** so I like that you went to the incident report because I have another thing that I wanted to talk about that would help in preparing the incident report, but it's also useful for other reasons. So something, that I mandated in our incident response plan is Somebody needs to be, writing down just like a log of everything that we discuss and everything that we, make changes for.

[00:37:10] **Adam:** Like if we're, if we're trying to troubleshoot the problem and we're like, okay, well maybe, maybe it's DNS and we, you know, refresh the DNS cache or whatever. you know, we, we, so we timestamp it, right? So, and this is for us, it tends to be the person who's doing the communication with the customers during the times that they're not communicating with the customers they're available to.

[00:37:27] **Adam:** Be doing the logging, right? So they'll write down like, okay, if the incident started at five o'clock, then, you know, at five 30, Adam refreshed the DNS cache, right. And, and just like little simple things, just enough for us to remember the sequence of events and, and so that we don't forget the steps that were taken.

[00:37:45] **Adam:** Because what you don't want to happen is. You know, you get this resolved and then it happens again later, two months later, and you try to remember

[00:37:53] **Tim:** What do we do? But what all we do to get.

[00:37:55] **Adam:** so remember, and that way too, you know, okay, this is what I did in this order so that if something goes like even worse or something else comes up, you can go like, oh, okay, that's because of this one thing that we tried.

[00:38:06] **Adam:** Well, that, that thing that we tried didn't fix the, the incident, but obviously it caused something else. So now we can go undo the thing that we tried. So, and I've had on multiple occasions, that log come in super useful for providing an incident report later for being able to like, just take a look, looking at the log of everything that happened and then.

[00:38:28] **Adam:** Organizing those thoughts, you know, there's a lot that you leave out in the incident report, but at least then you have a full clear picture of everything that happened.

[00:38:36] **Carol:** Is there a title that you give that person? Like, the scribe or the historian or, I mean like, how do you,

[00:38:42] **Adam:** for me, yeah, I mean, I think in our documentation, we call it the incident commander, but, you know, that's, it doesn't, it's, it's whatever,

[00:38:51] **Carol:** No, I, I do better if I have like a thought, like a role to go to, like a process, rather than just thinking hypothetically about it.

[00:39:00] **Ben:** One thing that I have found to be completely invaluable during this incident remediation stuff is anytime you're looking at a metrics dashboard or even a, like a CloudWatch logs search results. Take a screenshot. The there's like being able to find the right logs or the right metrics with the right filtering in the, in the future, especially depending on, on log retention and like metric granularity, retention, screenshot, screenshot, screenshot, put it into the, into the war room chat.

[00:39:36] **Ben:** And that way, not only do you have the timeline that Adam's talking about, you have this correlation of, and here's what the graph looked like at that time. And here's what the log entries looked like at that time. And it's this.

[00:39:46] **Adam:** mean,

[00:39:47] **Ben:** Etched in stone.

[00:39:48] **Adam:** our log we do in a Notion doc, so you can just drop the screenshots right in there. And in addition, so like, if you're running SQL queries to like check on the status of things, I say, You know, our, our instructions say, you know, those, those, whatever SQL queries you're running, we have to have in the log.

[00:40:02] **Carol:** Oh, that's cool.

[00:40:03] **Ben:** player.

[00:40:04] **Tim:** is cool.

[00:40:04] **Carol:** Yeah, in our README, so we use App Insight and we put a lot of our queries in our README. It's like, oh, you want to know how to go find these in the logs? Here's some, like, queries to help you find it. And it makes it a lot easier for you.

[00:40:18] **Ben:** Although, so we had to do, back, back when we were like having incidents constantly and learning how to run the platform and the company more effectively was like our top priority. We would create these runbooks and the runbooks were like, like, you will shoot yourself in the foot and something will go wrong.

[00:40:40] **Ben:** And then here's typically how we deal with it. And it's like, here are links to the dashboards that we typically use. And here are links to the log queries that we typically use. And that's one of those things that I think in theory makes a ton of sense. But then. When a system operates pretty well and you haven't had to deal with it for a while, and all of a sudden there's an incident and you go to the, that runbook and you click on the link and you're like, Oh, that log service doesn't actually, we don't actually use that log service anymore.

[00:41:09] **Ben:** You know, and like, Oh, that metrics dashboard, we don't actually pay for that metric service anymore. We moved over to something else. And I don't know, I don't know how you keep stuff like that up to date. Part of me wishes that. You just didn't do it in the first place, but I know that's not good protocol necessarily.

[00:41:26] **Carol:** You do what I did and you go to work for the government and nothing's ever allowed to change. So you don't have to worry about it. What you used 20 years ago is still valid today.

[00:41:36] **Ben:** Oh, yeah.

[00:41:37] **Tim:** But they told you to use chat GPT.

[00:41:39] **Carol:** Not yet. It's not approved yet. I have to take my training first. Yeah.

## [00:41:44] Calling It

[00:41:44] **Ben:** The other thing, and I know we've talked about this on, on previous episodes, but at some point you're, you're working on debugging an incident and let's, you know, even if it's like eight o'clock at night, that sucks, but whatever, everyone's still mostly awake and then it's nine o'clock and that's 10 o'clock and then it's midnight.

[00:42:02] **Tim:** awake, Ben at eight.

[00:42:03] **Ben:** Yeah, yeah, yeah. And then at some point you're looking around and you're like, none of us can make decisions here. Like none of us have position of power. We can say. F it, we're just gonna let this thing be broken overnight so that we can go get some sleep. And it's, it's really incumbent upon a person in a leadership role to step in and, and, and actively say, Hey guys and gals, it's 1am.

[00:42:29] **Ben:** We're not going to fix the problem at this point because our brains are fried. We're just going to eat the fact that from 1am to. 8am, the site is going to be continually broken and that's just the reality and we're going to regroup in the morning and when leaders are not willing to do that, I think that's, I think that's a real failure of leadership.

[00:42:50] **Adam:** Agreed.

[00:42:50] **Carol:** Completely agree. Like even though,

[00:42:53] **Adam:** agree.

[00:42:53] **Carol:** no, I

[00:42:54] **Adam:** No, just, just to be difficult and, and disagree with Carol, go ahead.

[00:42:57] **Tim:** Although I don't know if I could sleep,

[00:42:59] **Carol:** That's what I was about to say. Like when something like that has happened and I've walked away, I just come right back to it because I can't turn my brain off and I'm so freaked out that I've caused a problem or that my customers are suffering from this and they're losing money and.

[00:43:13] **Carol:** I just end up not being able to sleep, so I come at it, and then I probably do a worse job because I really should just be sleeping. But someone should step in and say, you're not allowed to look at this anymore.

[00:43:24] **Ben:** You just gotta slam those Advil PMs. Knock yourself out and then highly caffeinated in the morning.

## [00:43:32] Getting Back to Normality

[00:43:32] **Tim:** incident is fixed, you know, that's a great feeling when it's fixed and you, you know, you tell your customers what was wrong, how do you get back to getting back to normal life is, is kind of weird. After that, you know what I'm like? It's like,

[00:43:49] **Carol:** It's like that next day is just off. Like you're guaranteed to have like a fog from it all, and a feeling of it's about to happen again, and that like, the fight or flight kind of kicks in.

[00:44:03] **Tim:** Yeah. And. Admittedly, it's bad that it happened, but it is an adrenaline rush to go through that whole kind of experience. You know, you're constantly, like you said, fight or flight, Carol, and then you get back to like the normal stuff and you're kind of like, something's wrong.

[00:44:20] **Carol:** Mm hmm.

[00:44:20] **Tim:** It's too quiet. You're like the, the, the horror movies where, you know, everyone thinks they're safe and then pops up and starts, you know, so it takes a little while to adjust back to normal life.

[00:44:36] **Tim:** And that, that next day, I don't really know how much, how much productivity I get out of myself or the team. Cause they're all just kind of like just going back and looking and marveling at, you know, this thing that was like spiking, you know, like just checking the CPU and the memory logs go, Oh, look at that.

[00:44:51] **Tim:** It's so calm. So tranquil.

[00:44:54] **Adam:** I've done that. You know, you have like really rough weeks or everything is crappy. And then like the next week it's like, I have taken screenshots of just like normal CPU and memory usage and been like, ah, so nice.

[00:45:07] **Tim:** beautiful. Yeah. I hope, I hope none of our listeners have those kinds of days, but chances are, if you're in software, you're going to have them, they're going to happen.

## [00:45:16] Journaling

[00:45:16] **Adam:** Yeah. Oh, and one other thought that occurred to me before we close this out. I know we've talked in the past about like, sort of, at least me, I've talked about journaling, my way through my work week, right? Just like, so I don't forget the, the things that I've done or whatever. And I think that if you're going through a period where you've got a bunch of incidents, it can be really helpful to journal, you know, just about your workday, just to say like, you know, okay, on Tuesday, I spent four and a half hours dealing with this incident during the workday.

[00:45:42] **Adam:** And that's why I'm like an extra half day behind on my schedule for work, right? Like, and then if you've got three incidents during the week, like, you know, you're going to be significantly behind. And, and you want to be able to point back to that and say, well, this is why, right? It's not because I am bad at doing my job.

[00:46:00] **Adam:** It's because I had to set my job aside to deal with this other incident.

[00:46:04] **Ben:** 100 percent on that. That's management doesn't necessarily understand that.

[00:46:10] **Adam:** All right. Well, it seems like a good place to wrap it.

[00:46:12] **Adam:**

## [00:46:12] Patreon

[00:46:12] **Adam:** Okay. So this episode of Working Code is brought to you by being paged by the lowest person on the totem pole at 2am. gracious. They didn't want to, but they had to. and listeners like you, enjoying the show and you want to make sure we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:46:33] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:46:41] Thanks For Listening

[00:46:41] **Adam:** We are getting ready to go record our after show, which is where the outro will con will roll and those of you that are not patrons will listen to an objectively worse podcast.

[00:46:52] **Adam:** And those of you that are patrons will get to hear more of our delicious voices. And, tonight on the After Show, I'm gonna ask Tim, if he successfully stole that role from Tom Cruise in whatever movie he was, auditioning for. it's tough when you're up against Tom Cruise,

[00:47:09] **Tim:** It is, it is,

[00:47:10] **Adam:** we'll see, we'll see.

[00:47:11] **Adam:** And then, it looks like in the notes here, I'm not sure that's spelled correctly. Does that say deifying

[00:47:16] **Ben:** Yeah, do you fine?

[00:47:17] **Adam:** Okay. so apparently we're going to be talking about that in the after show. So if you want to find out what that's all about, you can support us by going to patreon.com/workingcodepod and become a supporter of the show.

[00:47:29] **Adam:** We'd love to have you. that's going to do it for us this week. We'll catch you next week. And until then,

[00:47:33] **Tim:** so in theme, in line with the show opening topic, but Ben's, you know, failure, I put into chat GPT to help me make, make, I was going to say, what I was going to say was remember. It doesn't take artificial intelligence to know that your heart matters. And here's what ChatGPT said. I should say instead, keep in mind, acknowledging the significance of your heart doesn't necessitate artificial intelligence.

[00:48:00] **Tim:** I think my job is safe.

[00:48:03] **Ben:** We can't replace you for the outro. That's crazy.
