---
title: "205: Lessons Learned Along the Way"
description: "In this week's episode, the team discusses various software development topics and how their opinions on these subjects have evolved over time."
date: 2025-02-13
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/ba019e35-efe9-40e2-b499-ca52f6d93dcb"></script><div class="redcirclePlayer-ba019e35-efe9-40e2-b499-ca52f6d93dcb"></div>

In this week's episode, the team discusses various software development topics and how their opinions on these subjects have evolved over time. Key topics include the benefits and challenges of testing, the balance between microservices and monoliths, the role of static typing in code, and the practicality of semver versus other versioning strategies.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/205-lessons-learned-along-the-way.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** And I have some ideas on like how I would. Change the code to make that easier to write tests for and that sort of thing. But I, I'm very much still on that journey and I just don't want to give somebody misinformation about, you know, like where I am now and then have that change in a year.

[00:00:16] **Ben:** and I think, and I think

[00:00:20] **Carol:** in of bad advice.

## [00:00:22] Intro

[00:00:22] **Adam:** Okay. Here we go. It is show number 205. And on today's show, we're going to talk about software topics. Things have changed our minds over the years. Maybe some things that haven't changed our minds or how we've grown. Of course, this is, if you haven't seen it, this is inspired by an article that's been making the rounds lately by, I believe somebody whose name is Chris Kyle.

[00:01:03] **Adam:** but this is a, you know, it's in the zeitgeist and, and a lot of it I think is really interesting and important to talk about. So we're going to go around the horn and talk about what we, what we've learned, what we've changed, what we're, curmudgeonly clinging on to. Got the whole gang here today, and it looks like, oh, but before I say that, I say, but first we'll start with our triumphs and fails.

[00:01:24] **Adam:** Carol, it's your turn to go first. What's going on?

## [00:01:27] Carol's Triumph

[00:01:27] **Carol:** well, since I can't really talk about work very much, my Triumphs and Fails are all going to have to be just personal, like, life stuff. so I'm going to go with Giant Triumph right now, and I'm going to let you guys know that we're taking a trip this weekend for Valentine's Day, and we're just going to get out of town,

[00:01:42] **Tim:** All of us,

[00:01:43] **Carol:** needed.

[00:01:44] **Carol:** Yeah, you want to come with? You

[00:01:45] **Tim:** we're all going.

[00:01:46] **Carol:** Yeah.

[00:01:47] **Adam:** Did you spring for the six person hot tub?

[00:01:51] **Carol:** mean, we have the executive lounge at Hilton, so I think you can just get free drinks with us. Yeah, yeah, that's enough. Yeah, we're going to head up to Fort Collins, Colorado and go visit the area. And it's a place my husband used to live at. Or lived at for a while, I think I'll look at the campus there and just do some, some touring for the weekend, but some definite, like.

[00:02:11] **Carol:** Relaxing and getting away from the stress of what's in our house right now, which is where I work, so need to get away.

[00:02:18] **Ben:** Is Fort Collins a high altitude location, or is it lower down?

[00:02:23] **Carol:** It is high, but I don't know how much higher it is than what I currently am or what I was in Arizona.

[00:02:29] **Adam:** I've been led to believe that everything in Colorado is very high all the

[00:02:32] **Carol:** Mm

[00:02:32] **Ben:** Absolutely.

[00:02:33] **Adam:** not the truth?

[00:02:34] **Carol:** Not me, I won't be. Heh heh heh. Heh heh heh.

[00:02:41] **Tim:** Oh, altitude. Okay.

[00:02:43] **Carol:** Alright, that's me. What about you, Tim? What do you have?

## [00:02:46] Tim's Triumph

[00:02:46] **Tim:** I'm going to go with the triumph too. And this is, this is work related. So I just, I just love seeing that when you have a nice small team that it can move quickly, you can get some real big wins pretty easy without a whole lot of friction. So, you know, we had a client call last week and they're, And I guess they're working with a small team to basically we went from having no API for them to be able to, pull information and to make payments, you know, for them and post them in their system of record from having nothing to basically, we basically have the first level working with nice UX and design and, be able to shift gears real fast, you know, like, I was working on it yesterday and then I ran into, I realized that the flow of this, the flow of this whole process wasn't going to work without a complete UI overhaul and I'm not a UI person.

[00:03:40] **Tim:** So I sent it over, you know, I do have a person on my team, they, they're very, very good at it. Sent it over to her. she was off that afternoon, but she got it. My note the next morning came in, you know, when I woke up and she likes to work really early when I woke up, she's like, here it is. I pulled, pull it down, looked at it, tested it locally.

[00:03:57] **Tim:** I mean, yep, this looks great.

[00:03:59] **Carol:** Oh, wow.

[00:03:59] **Tim:** then I put in all the bits and pieces that make it, you know, pull information down, do the calculations, redisplay the screens, post the payment, error handling, all that stuff. And pretty much got it wrapped up today as a little thing's going to tighten up tomorrow. But it's just nice when you go from zero to almost done.

[00:04:20] **Tim:** In pretty much a very, you know, 48, 72 hour timeframe,

[00:04:24] **Ben:** Crazy. What a pray tell is the magical technology you're using to make this happen so fast. Let us learn.

[00:04:31] **Tim:** it's, it's something that, that, you know, maybe you've heard of it. It's called cold fusion.

[00:04:37] **Ben:** what I hear. That is a rapid application development

[00:04:41] **Tim:** They Rhea Rhea, they used to call it. Yeah. Yeah. Rapid. Yes. Very, very rapid and rich. And yeah, it's delicious type. You know, it's, it's boring, but you know, that's one opinion. I've, it hasn't changed over the years.

[00:04:55] **Tim:** Boring works,

[00:04:56] **Ben:** boring is good.

[00:04:57] **Tim:** Yep. So anyway, that's, that's my, my win. That feels good. always nice when you move the ball forward. So how about you, Adam?

## [00:05:05] Adam's Triumph

[00:05:05] **Adam:** in a roundabout way, mine is also going to be about work, but very roundabout.my, I'm going to go with a triumph. My triumph is that I took a shower today. Um,and, and it's about work. Yeah, I, I mean, I work from home and, and, it's not a, it's not a big deal if I don't take a shower because nobody, we don't have smell o vision.

[00:05:27] **Adam:** we don't pay for that upgrade on our team chat. but, no, so I got some vaccines yesterday. I got a,pneumonia and my very first shingles vaccine. normally, I think they don't give that to you until you're like 50 or something, but because I'm immunosuppressed, they were like, ah, you can have it.

[00:05:41] **Adam:** and me, I'm like, you got some more science in a syringe, please inject that into me.

[00:05:46] **Ben:** Absolutely.

[00:05:47] **Adam:** my doctor was like, I'm just so happy that you are as like in love with vaccines as I am. I'm like, oh yeah, give it to me, give it all. Anyway, and so I got those two shots yesterday. And man, did they knock me. I don't know which one it is, but it just knocked me down My I got him early in the morning and then by the end of the day both of my shoulders were like on fire sore and then I woke up this morning with a fever and just It took me like an hour to realize that I had a fever.

[00:06:17] **Adam:** I just felt like Achy, lethargic, just like I was stuck in glue but also hot and, and my brain wasn't working and it was just awful. And then finally I was like, wait a minute. I think I have a fever. And so I took some Tylenol and slept for like an hour, and then I called outta work . And and then I went back to sleep for most of the day.

[00:06:38] **Adam:** So, but I did get up at one point and take a shower, and that is my triumph. I, I try to find the positive in things right. I took the day off. I, I, but I did some self care. I, I, you know, slept to try and get rid of this thing, and I managed to not stink it up all day.

[00:06:54] **Tim:** Cool.

[00:06:56] **Adam:** The, the little things, right?

[00:06:58] **Tim:** Yeah.

[00:06:59] **Carol:** So, the, um, when the cobit vaccine was kind of still coming out, it was probably the 1st year of it. We went to eat with one of our friends who had just gotten it and her arm was hurting so bad and we did the thing where you stick a penny to it and if the penny sticks to it, like, you know, like it was the original, like COVID vaccine.

[00:07:16] **Carol:** So yeah, sure enough, we stuck the penny to her arm and it just stuck to it and didn't move where the injection was. She's

[00:07:22] **Adam:** that 5G chip.

[00:07:24] **Carol:** she's like, they're watching me.

[00:07:29] **Tim:** You talk about science in, in a, in a needle. I was watching, I think it was last night. There's this YouTube show called SciShow

[00:07:36] **Adam:** Yeah.

[00:07:37] **Tim:** with Hank Green.

[00:07:38] **Adam:** hmm. I'm familiar.

[00:07:40] **Tim:** and, he, he was talking about just what they do, these poop injections. Where they take someone else's poop and they like give you an enema with it,

[00:07:49] **Ben:** Fecal transplant.

[00:07:50] **Tim:** fecal transplant.

[00:07:51] **Tim:** And it's like cures like IBS and liver disease and allergies. It's like ridiculous amount of things that they, they believe that this stuff cures and there's some scientific evidence, but it hasn't been fully studied. Otherwise you'd be seeing poop pills at your, at your local Walgreens and shoving them up your butt.

[00:08:10] **Tim:** But, yeah, that, that's, that's the latest science, I guess the going on the poop track.

[00:08:15] **Ben:** It is so fascinating. I, I forget what I was listening to. I want to say maybe it was a science versus episode, which is a very funny podcast, by the way. and they were saying that so much of the emerging science, About human health is this balance between the gut biome and the rest of your body. And that's what my understanding is.

[00:08:35] **Ben:** That's what the fecal transplant is about. It's about getting that that biome back into a healthy place, but they were saying on the show that it seems to have so many positive. Outcomes despite the fact there's not so much research. Why don't we have enough research? And it was like, no one really wants to talk about poop.

[00:08:52] **Tim:** And there's no, and there's no money to be made, honestly. It's like, it's, there's no drug to patent. He just, it's a process of collecting healthy people's poo and putting them into capsules and then popping them in. You're either swallowing them or doing it the other way.

[00:09:08] **Carol:** It's going to be the next like blood plasma donation place where you get paid to come do it.

[00:09:14] **Adam:** The brown cross.

[00:09:15] **Tim:** Yeah. The brown cross. That's

[00:09:22] **Adam:** All right, and on that note, why don't I throw it over to you, Ben? What do you got going on?

## [00:09:26] Ben's Triumph

[00:09:26] **Ben:** going to go with a triumph. last time I had talked about how I've been working on this little side project for funsies. And, I've just been trying to question a lot of the things that I've done historically. And there are a lot of things that I've done historically that have worked, but I think lacked. Any kind of an elegance or any kind of a clean abstraction. And one of the things that I've never been happy about in any of my implementations is kind of, permissions model. Who can access this thing? Who can do what to this thing? And, I've just been playing around with different ideas and I've been having these very long conversations with chat.

[00:10:05] **Ben:** GPT. What do you think about this approach? What do you think about that approach? This is too complex as their way to simplify as their way to unify. and I feel like I'm slowly getting to something that feels like I'm going to be pleased with it and that it's not going to necessarily lock me into a corner that I don't want to be in and also is not too complicated.

[00:10:29] **Ben:** you know, that opinion could very well change two days after I start to implement it. I could be like, Oh, this is total crap. I can't believe I thought this was elegant two days ago, but, I'm just, I don't know. I've been just having so much fun. Questioning things and and playing around with little ideas and it's funny, I think I've mentioned this before that this is kind of where I'm finding the sweet spot of of AI to be or these kind of philosophical conversations because when I ask it to do.

[00:11:00] **Ben:** Actual implementation of stuff. I don't know. I just don't love it. And I mean, probably part of that is just me pushing against that idea of having it write code for me. So this feels like the safe way to, to leverage what it can do without having to feel like I'm no longer writing code. but it's also. It, it does, it, it just feels like a really fancy rubber duck to me. Like, I really feel like I'm just throwing ideas at it and seeing what it'll say and just letting that prompt a new idea in my head. And I think I would get that same exact feedback if I were just talking to someone else about my ideas.

[00:11:37] **Ben:** But I think the niceness is the, the on demand nature of it, that I don't have to jump on a call with someone and say, Hey, can we talk through some idea?I can just open up a new chat and do that. Am I saying that it's as good as talking to a human? Absolutely not,

[00:11:51] **Carol:** But something

[00:11:52] **Ben:** but it's something. Yeah.

[00:11:53] **Adam:** I forget where I saw this, but it was that, ChatGPT has started to show up as a citation in some scientific research. like, you know, a paper written by so and so and so and so et al or whatever. but they'll like, they'll list, large language model, whatever, I guess if it helped them write the paper or something, or if they used it in their research.

[00:12:15] **Adam:** and it was making me wonder just, just now when you were talking about, you know, the way that you use it. I wonder if we're ever going to get to the point where we have to like put, when we make a commit to the source code repository, is it going to be like, this was committed by Ben and chat GPT.

[00:12:30] **Carol:** Yeah. It's almost like, uh,The co author

[00:12:33] **Ben:** like it needs its own get user. And so you ask it to generate some code and it kind of does an intermediary commit, and then you can go through and change it. So you can say like, here's the stuff that chat GPT wrote. And here's the stuff that you wrote.

[00:12:46] **Adam:** I think that would be very interesting. Like if you took an application and you came back like five years later and you saw like, which of the lines were authored by chat GPT that are still there and which ones like maybe got replaced.

[00:12:57] **Tim:** So if you pair program, do you put the other person's name in the commit?

[00:13:01] **Adam:** I mean, I haven't done programming in a really long time, but no, we didn't when I was doing it.

[00:13:06] **Carol:** so we do sometimes actually, but it's usually when you're working on the same branch and then the PR will have all the commits in it. So, when you squash it, it has every author. So, at the bottom of the squashed PR, it'll say co authored by. This person coauthored by this person, as long as they have commits on it, actual commits on their name,

## [00:13:26] Squashing

[00:13:26] **Adam:** we, can we sidebar very quickly on squashing? I feel like that's a, that's a controversial topic,

[00:13:32] **Carol:** it's a hot, it's a

[00:13:33] **Adam:** for, and I mean, honestly, it leads right into today's model or topic too, because, I, it's something that I've changed my mind on over the years. I, I, I originally was like, no, no, no, you squashing is bad because you're losing.

[00:13:51] **Adam:** The granularity of the history, right? Each, I guess, before we get into that, does somebody want to explain what squashing is? Mm

[00:14:00] **Carol:** and make one commit so that it looks like one change instead of seeing all the changes individually.

[00:14:05] **Ben:** Sorry, just to add some more color there though, because so many, so many, when, when people are anti squashing and they want to merge something in to develop or master or main or whatever you're using, and you look at their commit history. There are usually feels like dozens of commits that are like, Oh, finally got it working.

[00:14:26] **Ben:** And then the one before that is like, what the F and then the one before that is, Oh, I see where it's going

[00:14:31] **Adam:** I don't know why this is working.

[00:14:32] **Ben:** right. And like the one before that is just checking it in for the weekend, you know, it's like, and it's, and it's this like literal stream stream of consciousness of the developer

[00:14:40] **Adam:** And for sure, ever since we started doing squashing, Let's change the way I commit to, right? Like, so I think I want to come back and circle back to the definition. So the way I think about it, and I'm sure that there's more than one way to do it or one more more than one way to use squashing, but the way that we do it tends to be, you branch off of main working on your feature, your bug fix, whatever it might take you four or five, 50 commits.

[00:15:04] **Adam:** And then when you're ready to merge that back into main. All of those commits in your branch just get squashed together. It combines the diff so as if you were able to fix the problem in one commit. And that's just the one commit that gets merged back into the repo. So you do lose the other 49 commits in that branch.

[00:15:22] **Adam:** The commit messages. But you don't actually lose any of the result of that branch. If that makes sense.

[00:15:29] **Carol:** Well, you don't lose the result of the branch, but you lose the ability to undo a singular commit. So you can't roll back like three commits where you realize you did it wrong. You have to make a new commit to change the, to change the code now.

[00:15:44] **Adam:** Yep. Very good point.

[00:15:46] **Ben:** You could argue that what I'm about to say shouldn't be part of the same PR process, you know, PR is something very specific to GitHub. Right. So that's not necessarily something that I can paint with a broad brush here. But, if I'm doing code and I see, oh, this file has a lot of, you know, Just formatting issues or something, or like someone accidentally pasted a lot of code that had spaces and that most of the file has tabs, and I just want to fix that so that I can now go and edit it with normal formatting.

[00:16:15] **Ben:** I will try to fix the spacing and then make that a commit and then fix the code. And that way, even if it's in the same PR, I can link people on a GitHub interface. I don't know how other apps do this, but in GitHub, you can link even within a PR to a series of commits within that PR. And I'll say, look, like, just look at this one commit.

[00:16:37] **Ben:** This other one just fixed a bunch of white space.

[00:16:39] **Adam:** You can also just turn off whitespace differences in the diff view, but, so I, I'd mentioned that it changed the way, that I will write my commit messages. And basically it kind of gets to what you were saying, Ben. I think it was Ben that was like, you know, I'm just checking this in for the weekend so I don't lose it.

[00:16:56] **Adam:** If my house burns down before I come back in on Monday sort of thing. And to me, what it's done is all of those intermediary commits. The commit message has become less precious. It's not something I have to waste time getting just right. Right, for a long time I was like, not, not to the extent of like conventional commits, if you've ever heard that, where it has like a very strict You might have a specific emoji to indicate this was a bug fix, or a new feature, or chore work, or whatever.

[00:17:23] **Adam:** And then you put in a certain module in parentheses, and a colon, and a space, and like, a 50 characters or less description, and then you have to have like a blank line after that, and then like a more thorough description. And that's, that is a very nice way if you have the Discipline to do it and the time to do it because then you could do things like automatically generate a changelog and your release notes and that sort of stuff, which is if you're doing releases, like if you're releasing a open source package and you those sorts of things that changelog and all that is conceived as a or not conceived perceived as a useful output.

[00:18:03] **Adam:** Then, that sort of thing I think can be a really good use of time. but for me, when I am just saying like, Oh, I'm halfway through this payment gateway change. Normally, prior to this opinion switch for me, I would be like, I can't commit this because it's not a logical change, right? This isn't, an atom of, of a complete thought that has could be, I guess my thought before this was.

[00:18:27] **Adam:** Every commit had to be something that like could compile and pass tests and stuff all in its own little bubble. And now I kind of think of like, that's what the purpose of the branch is. The branch, by the time that it gets merged has to be complete and, and thorough or whatever, and that final commit message of, of the merge happening should be disciplined and well written and all that clean stuff.

[00:18:51] **Adam:** But if you look at one of my branches now, you're going to find like 12, commits that just like WIP. Right. Because it's just, I know it's, it's going to be gone by the time the branch gets merged because we squash now. And, and like, I'm not going to be looking at that commit message in the next week to go, Oh, what was I thinking when I did this?

[00:19:13] **Adam:** Cause I'm actively working on it.

[00:19:16] **Tim:** So I've never really used the squash functions. Let me ask you, is that something you do? So you create a branch off main, you do all your work, do a bunch of commits. Is that something you have to do on that branch before you merge it? Or can you, at the time of merging that branch into the main, do a squash at that point?

[00:19:34] **Tim:** Because I always forget.

[00:19:36] **Adam:** it's an argument to the merge command if you're doing it manually. and yeah, I mean, like if you do it, if you're using GitHub or I would imagine GitLab and other. Competitors probably have a setting you can turn on per repo. That's what it is in GitHub is you can have a per repo setting, say. We squash our branches when we merge them.

[00:19:54] **Adam:** You

[00:19:56] **Ben:** You

[00:19:56] **Carol:** So there's 2

[00:19:57] **Ben:** oh, go ahead.

[00:19:58] **Carol:** that was gonna say there's 2 things like 1 is the merge itself into the, the upstream branch is the squash commit, or you could do a rebase on itself. And then at that point, you would rewrite however, many commits back into 1. so then if you need your branch to set out there with just the 1 commit, it could be pushed with just 1 commit.

[00:20:19] **Adam:** know, I love rebase in concept, but I feel like at least 50 percent of the time it just falls flat on its

[00:20:26] **Carol:** not fun, right? Yeah. Yeah.

[00:20:29] **Ben:** There's other, I don't know what the technical term for it is, but there is some operation you can do where you can like check out the code changes, but not the app, like none of the actual commits,

[00:20:42] **Carol:** Oh, yeah.

[00:20:43] **Ben:** like replay, replay all of these commits as if I had just typed it without committing any of it.

[00:20:50] **Ben:** And it's almost like creating a raw Delta between your branch and another branch. And then you'd have, you know, get ad dot and then commit it kind of a thing. I don't remember.

[00:21:01] **Adam:** a shallow clone? Is that what you're thinking of?

[00:21:04] **Carol:** No, I'm thinking that they like get merge or get rebase dash dash no commit where it just does everything, but it doesn't actually commit it. So everything shows in your

[00:21:14] **Ben:** part

[00:21:14] **Carol:** state changes.

[00:21:16] **Ben:** It's like, you know, we develop our patterns of the way we do stuff and get is

[00:21:20] **Carol:** all mindset and the worst part is like, I don't know about you guys, but I have so many aliases saved that are like, I don't, I never type checkout anymore.

[00:21:29] **Carol:** It's just get CO and I know that's checkout. So when I'm helping someone, I'm like, Oh, wait. Let me just send you my aliases so you can learn, like, while we're doing this, because I don't even know what the shortcuts are anymore. I just do them, like, by memory.

[00:21:44] **Adam:** Or like if you're pairing with somebody aliases, it's, oh, it's awful.

[00:21:50] **Carol:** Yeah.

[00:21:50] **Ben:** yeah, definitely squashing. I'm a huge fan. The other, the other reason that I really like it is because if you have a bunch of commits, someone, someone call me out if this is not correct, but I believe if you have a bunch of commits in your branch. And then you merge into your main branch, the log itself kind of weaves, all of the commits together based on time.

[00:22:14] **Ben:** So if you then do a get log, I think a sane person would say, Oh, well, of course the first 10 things in the get log should be all the stuff that I just merged, but it's not because it's, it's like by time order. So it might be the first one's yours and then four from some other developer. And then the fifth one is yours.

[00:22:33] **Ben:** And you're like, what? That doesn't make any sense, but it's.

[00:22:36] **Adam:** So. I think you're right, but it's the, it's weird. So you got to look at it as the, like the, the source tree, or I'm sorry, I said the name of the application that I have a lot of experience with, but what I meant was the like guitar hero view of the commit log, right? So you've got all the different colored lines coming down and where they branch off and remerge and stuff, and there's dots in them and, like it does show them in that order, but then.

[00:23:00] **Adam:** Like the, the line continues with no dots sometimes, right? That just means that like this commit chronologically happened between these other two commits on your branch, right? If you're, if there's a continuation of the line without a dot in it.yeah, it is, it is very confusing. I agree with you, but at the same time, like it, would anything else be any better?

[00:23:19] **Adam:** I don't know.

[00:23:20] **Carol:** Yeah. Squash it.

## [00:23:22] Semantic Versioning

[00:23:22] **Ben:** so if we could, if, if we can just tangent on something else that like, wouldn't anything else be worse? I know it seems like in the last couple of years, people have hated on the idea of semantic versioning and semantic versioning for listeners is where the version of a product is usually like major version dot minor version dot patch.

[00:23:41] **Ben:** And then sometimes there's a fourth one. And, and it has to do with how backwards compatible something is like going from major version two to major version three, you can expect a lot of stuff in the software possibly to be breaking if you try to upgrade. I'm not saying that that's, that's not the aim, but like you, you have to expect some of that to happen,

[00:24:01] **Adam:** the rule is if you make any breaking changes, there's even one breaking change, you're supposed to increment the major version.

[00:24:06] **Ben:** right? Which is not

[00:24:07] **Adam:** And then the others get reset to zero. Well, actually,

[00:24:11] **Ben:** and so sorry, sir, not, not to cut you off, but like, but, but that's my point is that so many things can actually constitute a breaking change, like so many more than people even have the common sense to think about

[00:24:26] **Adam:** you're absolutely right.

[00:24:27] **Ben:** that holding people to this reality makes no sense.

[00:24:31] **Ben:** And at the same time, there's no version of this that's better. Like,

[00:24:36] **Adam:** disagree with the last part.

[00:24:37] **Ben:** Oh, okay. Changed my mind.

[00:24:39] **Adam:** Okay, cool. So there's this thing that's been going around is called, so what you were talking about a semver or semantic versioning, there's, a proposal for something called Epic Semver, but it's E P O C H not E P I C. Okay. Epoch.And basically, so the root of the idea is think about it.

[00:24:58] **Adam:** Instead of there's three numbers, there'll be four, right? So, and the problem is that as humans, we think of that first number as like, oh, it's the new version of Microsoft office. A whole bunch of stuff is going to be

[00:25:09] **Ben:** My license upgrade time.

[00:25:11] **Adam:** we're in reality, right? You know, I just did a release that, that, you know, we, deleted a method that's been deprecated for 10 years and that's a breaking change.

[00:25:20] **Adam:** But even though it means like basically zero for anybody that, you know, only started using the program within or the whatever the dependency within the last five years, you know, if it means zero for them and they're seeing a major version, that's a kind of disconnect in your brain, right? And so, the thought, the, the, the original concept for Epic SemVer is that you would add a new number at the beginning.

[00:25:45] **Adam:** So it would go like Epic major, minor patch. Okay.the, and the, the Epic number is for like marketing purposes, right? So you've got your new version of Microsoft office. This is like a thing that we are doing marketing around. We're promoting it. It's a thing. Like we want you to think of this as the new version.

[00:26:03] **Adam:** Right? And then you still got major, which is like, there's been breaking changes, minor patch. and the problem with that is that there is no, it would break everything. Like, all of npm, and I'm sure pip, and maven, and like all of these things I'm sure have, tried centralize or standardize on semver.

[00:26:26] **Adam:** I, I imagine that's what other package managers do. Npm is really the only one that I'm in on any regular basis. and they assume it's like hard coded in there, there's going to be three numbers. And so if you just start showing up as like, now I've, I've got a new fourth number, I don't know if it would even work or if it would break stuff because now there's four sections instead of three.

[00:26:46] **Adam:** Aside from that, now you're just changing the rules and like the, the like tilde versus caret at the beginning. Like, what does all that mean? All that stuff. So the, the sort of compromise proposal is you take your epic number and you multiply it by like a hundred or a thousand, something like that. So basically you're just padding it out with a bunch of zeros on the right and then you add that to your major, right?

[00:27:08] **Adam:** So, if you're your major, it might be version 76 because you've done a bunch of breaking changes, but it, but your epic number, let's just call it like version two. So you're at like version 2076,

[00:27:20] **Ben:** Ah, sounds like the perfect use case for the left pad module.

[00:27:25] **Adam:** If only there was a module,

[00:27:28] **Carol:** I

[00:27:30] **Ben:** I mean, it's, I like it, but I think again, it's still this idea. So if I can tangent on tangent for a second. The other, the other thing that drives me crazy is the, is when people define their package, JSON files, which for listeners who aren't familiar with Node, it's like the manifest of things you're supposed to install as vendor dependencies.

[00:27:51] **Ben:** There's a notation where you can do, and I don't know what it is offhand, but it's like, if you use the tilde, it can use. Let's say minor updates automatically. And if you use the, the upy deal, I don't know, I can't remember what

[00:28:04] **Adam:** carrot,

[00:28:04] **Ben:** Carrot. it can use like only patch updates or something, but this always drives me crazy.

[00:28:10] **Ben:** I'm like, you should just, everything should just be locked down to a version. You should like nothing automatic should ever

[00:28:15] **Adam:** can do that. You just,

[00:28:17] **Ben:** No, no, I know. I know. But like, I don't know why that the, I don't know. I don't understand why that's the default when you, you know, NPM install dash dash save, like, why is that the default?

[00:28:27] **Adam:** I mean, I can't, I can't presume to speak for Isaac Schluter who wrote NPM and all that. But my understanding is that when you're running an NPM install, it's a reasonable thing to assume you might want, Oh, like you shouldn't have to go check and find out that a dependency of a dependency of a dependency.

[00:28:45] **Adam:** Has a patch update that just fixes a tiny little bug, right? Like you shouldn't have to care about that. so it just, if it's quote unquote compatible, which is B the major version is the same, then just install whatever the latest compatible version is that, and that, you know, there's a lot of problems, right?

[00:29:04] **Adam:** There are people that don't give a crap about semver and they just, you know, use version numbers, however they feel like it should be. There's people that

[00:29:12] **Ben:** five based version numbers

[00:29:13] **Adam:** there's, there's people that. Do whatever the heck they want. They, you know, maybe they don't know any better. There's people that, yeah, I mean, there's, there's people that know better and try to follow semver and, and promise to follow semver, but don't realize they've made a breaking change and then, and you can't

[00:29:29] **Ben:** that see that to me feels like the most tractable approach is like, you're just doing your best, but let's not, let's not pretend that this is foolproof. And I think if everyone could just

[00:29:40] **Adam:** you can't retract a version number, like you can, you can issue a, a, an updated, you know, fix whatever. So if you. If it should have been 4. 0, but you accidentally released it as 3. 9 or whatever, you can release a 4. 1 that fixes the problem that you introduced in 4. 0, whatever, but it's a whole thing.

[00:29:58] **Ben:** So what else? We never really introduced the topic or we never transitioned, but we're definitely into the show at this

[00:30:03] **Adam:** I, I tried, I tried, eh,

[00:30:05] **Carol:** think you did okay.

[00:30:06] **Tim:** Things, things we changed our mind on or opinions we picked up along the way. I've, I've got one. So,

[00:30:12] **Adam:** go for it, mm

## [00:30:13] Reducing Complexity

[00:30:13] **Tim:** so early in my career, you know, I'm working on really someone else's software that I really didn't understand. And I thought it was just because I wasn't smart enough and I didn't have enough experience.

[00:30:24] **Tim:** I didn't know enough about the industry that we were writing for. And over years, I eventually kind of started figuring stuff out just through, honestly, through a lot of trial and error, because there wasn't really any documentation. And eventually I. Began to understand the complexity and sort of became somewhat of a, a swamp guide and managing that, that complexity.

[00:30:47] **Tim:** And I thought that was a good thing, right? Because people would come to me, they'd ask me questions. I'm like, Oh yeah, I've, I've, here, let me explain. And, you know, I'd say how I wrote this, I wrote this article here, here's a, go read this, this kind of explains what's going on. And I took pride in that. And that was actually not a good behavior

[00:31:07] **Carol:** Why? Like, why was that not good?

[00:31:09] **Tim:** because complexity itself, it was the problem, right? Understanding it's not, not really understanding is yes, a challenge, but what I should have been doing was reducing the complexity

[00:31:20] **Tim:** of the problem. And going in and saying, okay, I understand, I understand why we're doing this this way. I understand how we got here, right?

[00:31:28] **Tim:** It was a, it was a pathway paved with good intentions, but it led to hell. and so let's fix this. That's what I should have been doing. Instead, I just kind of just was quite happy to sit there and my, my expertise and to dole out wisdom. And, that was, that wasn't a good thing. So I'm trying to We're trying to be better trying to like, if, yeah, once I understand complexity and like why we got here, all right, let's, let's unwind this and make this so that it is easier to understand for, for going forward.

[00:31:59] **Tim:** Because otherwise everyone else is just have to follow that same path. It's just a waste of time.

[00:32:05] **Carol:** Yeah. I, I think that's a good one that a lot of people probably have picked up if they're 10 plus years into doing it, right? Those early on, they haven't had the chance to realize that the complex solution that's in place isn't necessarily the best solution because they're still trying to, you know, like you said, figure out what the software is.

[00:32:24] **Carol:** They're trying to figure out like how they even like be an employee at this point. So they have a lot to learn and they just have to go learn.

[00:32:33] **Adam:** think simplicity is having a bit of a renaissance these days, right? Like, people are appreciating more and more that simple and easy are different things, and simplicity It's something you have to work for. It's not simple because you wrote it quickly. It's simple because it's easy to understand, and quick to understand, and it just does what it needs to do.

[00:32:55] **Ben:** Well, it's funny. So in the, in the, discord chat, I was ran, not ranting, but, you know, I was going off on some tangent about how I'm struggling, I'm struggling with some sort of pattern I'm trying to create my code and you had posted a bell curve. Of kind of a, the journeyman's journey, or, you know, the, the engineer's journey, where it was the novice and the intermediate and the expert, and you could definitely go simplicity to overly built and then back down to simplicity.

[00:33:22] **Ben:** And I was thinking about that for quite a bit after you had posted it, because I was thinking about how often that happens with so many things. I like, I almost. I'm embarrassed that we don't teach that more. You know, I think we, it's like so much of how we teach people is on the assumption. You want to do the more complex thing.

[00:33:46] **Ben:** So let me show you how to do the more complex thing. And I feel like everything that we teach should start out with everything I'm about to teach you. Chances are, you're probably not going to need it, or like, you're not going to need this in most cases. Like almost, I almost feel like we should start defaulting to the complexity being the edge case.

[00:34:04] **Ben:** Not, not ever the norm. Because so much of the strife, it seems like companies suffer from are the, I saw Netflix do it this way, or I saw Amazon do it this way, or I saw Google do it this way. And I just assumed that's how real companies work. And like, those are very much the edge cases.

## [00:34:22] Multi-Tenancy

[00:34:22] **Adam:** I've got one. this is, I guess, not so much something that I have changed my mind on, but it was a lesson that I learned the hard way that I want to share, and this is like, one of my missions in life is to spread this message. And that is, I guess if I could try to simplify it as much as possible here, like if there is even the slightest chance that an application should be multi tenant, figure that out as soon as possible.

[00:34:45] **Adam:** And, and, and cross that chasm from one to two, as early as possible, just plan on it and make, make it the thing that you devote your first thousand hours on the project to, because circling back and migrating from single tenant to multi tenant after you have 20 customers is a freaking nightmare.

[00:35:06] **Carol:** Yeah. And keep fighting the fight when people are like, Oh, we should go back to single tenant because you're going to have the use case where you really wish you had multi tenant again.

[00:35:16] **Adam:** Oh, man, our code base for years was littered with like, okay, well, here's an exception for this customer. And here's an exception for this customer. That was the worst.

[00:35:24] **Carol:** Tenants are the best.

[00:35:26] **Ben:** I'm fascinated by the whole SQLite kind of re emergence in the last couple of years. SQLite has been around forever, but it's definitely been very popular amongst the podcast.genre of discussions and yeah, yeah, exactly the media elite. and one of the fascinating things about it is it's so cheap and inexpensive to create SQLite databases because they're just text files or, you know, they're just flat files and you can, uh, but, and, and the idea there was a multi tenant system is you could, in theory, create a separate SQLite database for each tenant so that your application.

[00:36:11] **Ben:** Kind of hacks as if we're multi tenant, but then only opens up and writes to tenant specific database files, which it's one of those things where it's such an iceberg. Like it feels like, Oh, that's so elegant. It's so simple, simplistic, but then how do you actually get that to work? In a way that doesn't mandate that you have some sort of database as a service vendoring and then all kinds of magic that has to happen.

[00:36:38] **Ben:** And like what happens if you accidentally associate the wrong database with the incoming request? I mean, it just sounds it's like at some point going back to this idea of simplicity, like, wouldn't it just be more simple to have a customer ID column in every table? And then it's just like you solve the problem.

[00:36:54] **Adam:** Indeed, sir.

## [00:36:56] ORMs

[00:36:56] **Ben:** If I could go with one, I have hated on ORMs, object relational mappings or mappers forever. And

[00:37:04] **Adam:** hmm.

[00:37:05] **Ben:** still hate them a lot, but I think the reason, okay. So I think. So much of my hatred came from an all or nothing mindset. When I first learned about ORMs, I don't know if this was an assumption on my end or if this was how it was described to me, but it was described to me as the ORM is the way you get data out of the database.

[00:37:29] **Ben:** There was no, there was no nuance to it. And so I'm like, Oh, it's going to be so complicated. All these, you got to define all your table properties and your CF properties inside of components. And then it's this crazy SQL where it's like half object access, half SQL syntax. I mean, just nuts. And, and then I was,

[00:37:48] **Adam:** you don't think in hql, I,

[00:37:52] **Ben:** to an interview. I mean, this has got to be four years ago, maybe five years ago. And, this woman on the podcast was saying that ORMs are really, really fantastic. If you use them for a very specific small part of your application, which is basically just the create, read, update, delete access on the tables.

[00:38:11] **Ben:** She's like, if you're not going to do anything but that it's actually really nice because like literally that's the only thing that that SQL is doing more or less. And I think if I had had that mindset where I could draw this tight boundary. Around just very simple record based access and said, okay, this is where the ORM is going to work.

[00:38:31] **Ben:** And then every part out everything else on the app and all the complex reporting, all of the, you know, get me this list of users and calculate these aggregates and get these other things. Like if that was just going to be raw SQL and not shoehorned into ORMs. I just feel like my relationship with ORMs will be very, very different.

[00:38:49] **Tim:** it.

[00:38:54] **Adam:** I have an application with tons of ORM in it. We, we did use it poorly, you know, in ways that you're talking about initially. And we're working on growing out of that and replacing it with a lot of SQL. ORM to me feels like there it's, it's something that. It feels like there should be promise there.

[00:39:11] **Adam:** It feels like it should be the promised land where like, Oh, you just add a column to your code and you do a database migration and it appears in the, in the database and, and like it. But the, I've, I've never had a truly great experience with ORM. I have had a couple of like nice things, like where tests would fail because of a database changes didn't go out or something like that.

[00:39:33] **Adam:** But the number of times that has bitten me to the point where I'm like, you know, working 14, 20 hour days or, wishing I could go back in time and tell my past self, like, dude, it's not worth it. far outnumbers, far outnumbers the times that ORM has actually saved me time and stress.

[00:39:51] **Carol:** Agree. And then trying to track back, like I'm looking through our query log in the database, trying to figure out where this came from and you can't just go search for it in code because it doesn't exist. It's like a link created statement. And then the whole, if I never see another sync migration in my life, I will be happy.

[00:40:10] **Carol:** Like I could die a happy person knowing I never had to see another sync migration just because things get out of whack and it is a nightmare to manage. So like part of what I want to do going forward is try to get us away from entity first and code first migrations and start moving toward more sort of procedures and more actual just straight SQL that you can find for what we do.

[00:40:31] **Carol:** We don't have business logic in our database or anything though. It's all application driven.

[00:40:36] **Ben:** well, a couple of episodes ago, maybe five or six episodes ago. I don't really remember. Adam was talking about how, a lot of his, this Adam here, cat, cat herder extraordinaire, that a lot of his data access objects are sort of like. They inherit from, they inherit from some base gateway and you just say like, here's the table and these are the column names and these are the types.

[00:41:00] **Ben:** And, and I've been on team SQL forever. Like I said, and in these little side projects that I'm been playing with, where I'm questioning a lot of my patterns and I'm trying to simplify stuff, like I'm basically getting to a point where my data access objects, like my, again, just this tight boundary, just this crud stuff. It's, I literally copy paste into a new, into a new file. And I find, replace the table name, and then I just change whatever columns need to be changed. And I'm like, Oh, damn it. Like this could literally just be a set of properties where I say, this is the auto incrementing key. And like, these are the types of these columns.

[00:41:38] **Ben:** And like these three out of these five can be updated. And literally I could just generate that, you know, those methods or, or, or whatever, you know, they can be generically named enough. and it just, it just, it's, I'm feeling, I'm feeling like I've probably copy paste modified. More than I've had to, and I love copy, paste, modify.

[00:41:56] **Ben:** Don't get me wrong. It's one of the best tools.

## [00:42:00] Monolith, Monorepo, Microservices

[00:42:00] **Carol:** Alright, I got one. Can I go? I used to think microservices were the Like they were everything you needed to do. And I've realized over the years that the developer experience is way more important than breaking every service out. So you should probably keep your core application together. So your developers can just work and things can just happen.

[00:42:23] **Carol:** When I have to go open up a repo to go find this, to then find where it goes in this other repo. Like, how is it being used here? Like, that's not fun. That's not how I want to spend my day. Like I enjoy my monolith now and I don't want microservices in my life.

[00:42:39] **Ben:** yo.

[00:42:39] **Tim:** Amen.

[00:42:41] **Adam:** hard to agree, although you know what it makes me think of is I'm drawing a comparison between the monolith versus microservices to mono repo and I guess separate repos for different related applications or services or whatever. And again, it feels like Monteripo, there's a, there's a, an element of perfection or something to it, right?

[00:43:03] **Adam:** There's, there's something about it feels like this is on the right path. There's, there's something based in factual betterness to it. but it doesn't feel like a solved problem yet. And I'm really excited for five, 10 years from now when like the, the challenges have been figured out. and, and we can, it'll just be like, oh yeah.

[00:43:25] **Adam:** Like how right now. 99 percent of people, I'm guessing, are, are using Git because like SVN and CVS, were terrible and they were the best crappy thing that we had at the time. But now that we have Git, like, why would you go back and use SVN? and so I'm kind of hoping that like we, we have another you know, evolution in the way that we use these tools and they, we land on something and it's like, Oh yeah.

[00:43:52] **Adam:** Why would you do anything other than a monorepo this way?

[00:43:57] **Ben:** Oh, it's so when microservices first started to get discussed, I had, I had built this mental model that a microservice is a thing that I could either build or buy, and the reason that I thought that was because the first time we ever considered using microservices at work was for image processing. And, basically for thumbnailing of larger images.

[00:44:20] **Ben:** And that was kind of the first big as a service, kind of a thing that it felt like content delivery networks were going to offer. Like suddenly you could just point your CDN at this image and add some property, you know, some query strings. And suddenly it's thumbnailed and it's, and it's monochromed and it's cropped.

[00:44:38] **Ben:** And it's like the face has been centered and it was like, oh yeah, I could either build that myself or I could buy it from this platform. And, and so that was like, Oh, microservices are the things that I either choose to build or buy. And, and, you know, people who quote unquote knew a lot more than me, like, Oh, that's so narrow minded.

[00:44:56] **Ben:** Like there's all kinds of crazy, you know, you could do hundreds of different things and data enrichment and all this stuff and monitoring and learning and just all this jazz. And I was like, yeah, my, my mental model for it is probably vastly. Too simple and fast forward, like six or seven years now. And I'm definitely back to the, yeah, like the stuff I should carve out is the stuff I either want to build or buy like the email sending.

[00:45:20] **Ben:** I could either build it myself or I could pay postmark or like queue management. I could either build it myself or I could use simple queue service. Like anything that is like core business, the business logic. I don't know. I just want it to be next to everything else that does core businessy business logic.

[00:45:37] **Carol:** I'm with ya.

[00:45:38] **Adam:** That's interesting to me because that's not at all how we have a bunch, I mean, we have probably 40 or 50 Lambda functions that we've extracted out of our monolith and we have a dozen or two dozen Fargate containers, for different purposes. So we, we're no. you know, what is the word I'm looking for?

[00:45:55] **Adam:** We've used microservices

[00:45:56] **Ben:** Yeah. Yeah.

[00:45:58] **Adam:** Maybe you just got good boundaries.

[00:46:00] **Adam:** well, the way that we tend to think about it, it's like it belongs in a monolith until it doesn't. And what it, when it doesn't belong in the monolith is when it generally either performance or, like a conflict of resources, right? So like if, If we want the application to be durable when this like chunk of it, the, the image generation or whatever, like if that, if that image generation could, fail, right.

[00:46:24] **Adam:** If it could throw an exception and take down the monolith, that's not acceptable. Right. And so we would pull it out for that reason. Or if, if it's just being used so much that like 90 percent of the application server's resources are being used for image generation, then, and it's slowing down the rest of the application, then like, let's pull it off on its own thing so that we can scale that according to demand without having to scale the rest of the application accordingly.

[00:46:49] **Ben:** Okay. So, so let me refine my explanation then because I think when I say build it or buy it, I think part of what that implies in my head, and this is the unspoken part. Is that the communication to that service happens through kind of dumb pipes, meaning I can, I could post data to this thing and then maybe it can web hook data back to me, but where I feel like we fell down, at least I can only talk about my own experience here, but where I felt like we fell down is when we tried to get fancy and we would post data to some microservice and then microservice would then have to spend a lot of.

[00:47:29] **Ben:** API calls back into our system to get more information about the thing that it's supposed to do. And I feel like if we had been just dumber about how those things communicate and said, instead of you asking us for it, let me just give you a whole payload. Like, okay. Like, like, like let's say we wanted to have a service that did invoice generation as PDFs. I wouldn't want that service to then have to call back into my business logic to say, well, let me get the customer data and the invoice information and the line items. I'd be like, no, let me just give you an HTML document. And your only purpose is to generate a PDF out of that HTML, and you don't actually care that it's an invoice, like that kind of a thing.

[00:48:09] **Ben:** Like I wish we had done that stupider dumb pipes kind of a situation.

[00:48:14] **Adam:** We have a Lambda called HTML to PDF.

[00:48:16] **Ben:** God, that's see, see, you found the right boundaries. And, but, but, but again, like going back to the build versus buy, if there was an Amazon service called HTML to PDF, like you could have just opted to buy that instead of build it.

[00:48:29] **Adam:** yep, and there would have been a free tier like their first million PDFs a month or free and yeah Yeah, for sure.

[00:48:36] **Ben:** Who else got one?

## [00:48:37] Types

[00:48:37] **Adam:** I got one so Partially because of the career path that I took for a long time. I was against strongly typed languages. I came up Initially out of college. I my first couple of jobs were working on like mainframe code and that wasn't strongly typed. and then, I, from there, I guess I kind of went more into web dev stuff and mostly with cold fusion, which is dynamically typed, duct typed.

[00:49:03] **Adam:** and I think largely because of the people that were trying to sell me cold fusion licenses, I, I believed what they were saying. Oh, you know, dynamic typing is better sort of thing. And over the years, I think I've changed my opinion that not only is static typing good for me, but it's a fantastic tool for sharing a workload across a team with a diverse, skill levels, right?

[00:49:31] **Adam:** So you're, if you have complex types, that, that are necessary for your application and like it gives the. Junior developer or somebody with a little bit less experience, some nice, like it's like bumper bowling, right? It kind of keeps them on the right path. Like if they're getting red squigglies, then something's not right.

[00:49:49] **Adam:** And they might not have otherwise knows otherwise known it.and I think that that is just a massive benefit of static typing that doesn't get talked about enough heads nodding.

[00:49:59] **Ben:** No,

[00:49:59] **Carol:** No, I, I love, I love type languages. Yeah.

[00:50:02] **Ben:** I, I like type languages, but if I could draw a parallel to type script itself, because JavaScript is basically, I guess it's, it's, what did you call, cold fusion? Dynamically typed.

[00:50:14] **Adam:** Dynamic type or, or duct typed.

[00:50:16] **Ben:** JavaScript is basically dynamically typed, for the most part. At least it's like the user facing bits are

[00:50:22] **Adam:** yes and no.

[00:50:23] **Ben:** it, it's, it's, I, I'll say that I can travel back and forth between JavaScript and ColdFusion, and I don't have to think too hard about the rules,

[00:50:32] **Adam:** Yeah. I mean, I, for all intents and purposes, JavaScript is dynamic, dynamically typed.

[00:50:35] **Ben:** Then TypeScript came out and TypeScript just caught like wildfire. And, and I was definitely on the TypeScript chain and I loved it. You know, Angular, modern Angular was built on top of TypeScript. And it, it just, again, felt like, I hate to say this, but I felt like quote unquote, like real programming, like just like a level of sophistication that this is what real engineers do.

[00:50:59] **Ben:** And this is, and this is how we build

[00:51:00] **Adam:** We're, we're writing and adhering to contracts.

[00:51:03] **Carol:** huh.

[00:51:04] **Ben:** And, what I noticed is that whenever I started an Angular app, obviously I used TypeScript and I really enjoyed it. And then whenever I started to build a little side project, I, I didn't reach for TypeScript, it was not, it was not my instinct to just reach for a strongly typed thing.

[00:51:19] **Ben:** And you could say, going back to this idea that it's great for a diverse team with a, with a diverse set of skills. And you're, if you're only going to write for yourself, it probably doesn't matter that much, but I just. When I'm, at least when I'm on my own, and that's what I'll, that's the only thing I can speak to, I don't find myself missing TypeScript.

[00:51:39] **Adam:** I totally understand where you're coming from. And I will say I've done the same thing sometimes. I think the, the solo project benefit of TypeScript is not so much while you're sitting there working on it. But when in three years you get an email, somebody's like, Oh, Hey, can you make this quick change?

[00:51:56] **Adam:** And you want to go just drop in, make the change, run the tests, make sure they pass, and you're done. Like, TypeScript can be super helpful,

[00:52:05] **Ben:** Yeah. Agreed.

[00:52:06] **Adam:** again, you're getting the red squiggles, and you're like, Oh, wait, what am I doing wrong here? This was supposed to be, you know, an integer, not a string or whatever.

[00:52:16] **Adam:** That's oversimplifying. Simply, why can't I not talk tonight? Maybe it's maybe the fever's coming back.

[00:52:22] **Tim:** You got shingles,

## [00:52:23] Agile

[00:52:23] **Ben:** I think it'd be interesting to, are there anything in the, in the managerial track, Like, , is there anything like, you know, obviously we had waterfall years and years ago and then we've gotten hard, hard into agile and then, I don't know. I sometimes feel like I'm not, I'm not pro waterfall in any way, but I'll be in a meeting where we do a lot of design thinking and I think to myself.

[00:52:45] **Ben:** Dang it. This is really nice. It's like, it's actually kind of nice to get a kind of a broader sense of what's going on before I just dive right into code.

[00:52:53] **Tim:** yeah, well, I mean, yeah, but when I think of waterfall, I think you have a big project, right? It's like, it's going to give you a year long project and you try to get all the requirements up front. That to me is waterfall. It's like, and that's impossible. But then again, Agile is just kind of like. it's like squirrel programming.

[00:53:14] **Tim:** Like we're only going to worry about for two weeks. Let's just get all the nuts in it before winter. And we're not going to worry about, you know, what the end result is. So I try, you know, I still try to strike a balance with between the two of, yeah, you gotta have a good vision for where you're going and where you're trying to end and the sort of a timeline you're trying to do that on the same time you can't. You can't drink it all in at once because it's going to constantly change. So you need a way to be able to, you know, set aside on the horizon, but also at the same time, be able to course correct along the way, even like for a sprint, I've seen this time and time again, you got a two week sprint and you have people who are trying to like, make sure they have all the requirements for the spread.

[00:53:56] **Tim:** Just, it's just two weeks and they can't get that right. You know, or they get it and they think they know it. And then the, you know, you release it to the customer after two weeks and like, Oh no, this, that's not what I meant at all. Did you notice on, on this page here, I mentioned this requirement and you, you know,

[00:54:12] **Adam:** I mean, not to be the agile defender or whatever, but like, that is the whole point of agiles, that you're putting it in front of them after two

[00:54:19] **Tim:** you're right. You're catching it earlier.

[00:54:20] **Carol:** hmm.

[00:54:21] **Adam:** Yeah, and, and, and again, you got to go back to the agile manifest one real quick. You got to go back to the agile manifesto and be like, it's agile, isn't scrum.

[00:54:30] **Adam:** It isn't XP. It isn't any of these things. It's just a relentless focus on what is good for the customer and what is going to produce the best product. The fastest.

[00:54:41] **Ben:** I was listening to an interview. This is, I don't know, four or five years ago. I think I actually mentioned this on the show a couple of years back that I was listening to an interview with one of the guys. Who was in the room where it happened, Hamilton callback, who, okay. who, who signed the animal agile manifesto.

[00:55:00] **Ben:** And he was saying on this interview that so much of it has just been misunderstood. I said, basically, if all you take from it is people over process, like that's basically, it's like, that's the important part.

[00:55:13] **Adam:** And yet everything, every discussion about Agile is process, process, process, process.

[00:55:18] **Ben:** I'll tell you. And maybe this is like a little bit embarrassing to admit. I don't understand the role of. Time based sprints. Like I just, I just don't get it. I don't know what, how it affects anything that has to do with project management and when people say, would you rather have a two week sprint or a four week sprint?

[00:55:37] **Ben:** I'm like, I don't know how that changes anything in my day to day life.

[00:55:43] **Carol:** Yeah. So for us, like it's important because we have to publicize everything that we're going to release. So we need to be able to push out the documentation, have all the read me's updated, have customer support trained. So they need to know like what's coming. So they have time to do all of their stuff.

[00:56:00] **Carol:** I mean, that's what happens when you're big enterprise and you are, you know, government, like we don't, we don't have the opportunity to just. Kind of keep going. We have to make sure everything's documented ready. So we have to know, like, this is 4 weeks. This is 4 weeks. This is 4 weeks.

[00:56:16] **Adam:** I see what you're saying, but at the same time, like the, the work is going to take however much time it takes to get done. And if you, if it fits in a four week sprint and you could just like leave it on the shelf for an extra week until you're ready to deploy it or whatever, then great. But if it doesn't, then what?

[00:56:32] **Tim:** I mean, what that happens, that happens all the time. Like you say, in these two weeks, we're going to try to get these 10 things done. You get nine of them done. The 10th one ain't going to happen. You, you do the release. You say, here's the nine things we got done. This is postponed to the next sprint. No big deal.

[00:56:47] **Tim:** But at least, at least it gives you a plan for what, what can we expect to see in the next two weeks? And particularly like if you're working with a customer, they want to know what should I expect?

[00:56:59] **Adam:** I, I, well, I guess what I was getting at is that you don't have to do. Sprints, you know, like time box sprints or whatever to share that knowledge with your customer in advance. Right. You can just say, okay, here are the five things that we're working on. We expect them to be done in a week, in three weeks, whatever.

[00:57:16] **Adam:** and, we'll, we'll stay in communication with you, right? It can just be like a, a bulleted list, a sequence like this is first, then this is going to be next and this is going to be next and. There's no reason you have to use time boxing, I guess.

[00:57:30] **Ben:** It feels like something that is meaningful to the managerial layer, but I think mostly touches the engineering layer. And I think that's where the disconnect for me has always come from. It's like people ask, you know, do you want to have a chocolate or vanilla? It's both amazing. Yeah. Yes. Yes. To all of it. You're like, no, but I need to know how much I can order as much as you can, the most, the most chocolate and vanilla.

[00:57:57] **Adam:** The amount is yes. How much money you got? Any, any, any other things in this list, grabbing you guys attention?

## [00:58:06] Isolation in Testing

[00:58:06] **Adam:** I mean, for me, I've spent a lot of time over the last few years really digging in on testing and trying to get way better at that. And there's one on here. I mean, it's never been something that was, I never had to change my mind on it.

[00:58:18] **Adam:** It was something I realized early on. But it's just such an important thing, which is that, when you're talking about testing, isolation is everything. If you have to have to change the order that your tests run in, or if you run one test by itself, instead of as part of the test suite, and that affects the outcome of the tests, then you have bad tests.

[00:58:37] **Carol:** Yeah, completely agree. But I don't think that's something I've ever changed my opinion on.

[00:58:43] **Adam:** No, no. Same here. It's just like, again, it's just another like super important thing for somebody new to the industry to know.

[00:58:53] **Ben:** Well, and as someone who does basically no testing, no automated testing caveat, it is fascinating to watch the conversation in the greater community evolve over the years. And it kind of, to some degree follows the sort of bell curve of the, you know, the novice intermediate expert where it's, it's, It feels like it was like no testing and then it's test everything and mock out every service.

[00:59:18] **Ben:** And then now it's like, you probably don't have to unit test most things and just some good integration tests and you'll be good.

[00:59:25] **Adam:** Right. If money is changing hands, or if this is the thing that you're selling for your value, then these are the things that are important to test.

[00:59:33] **Ben:** I was so angry. Okay. So I was

[00:59:37] **Adam:** Have we struck a nerve, Ben?

[00:59:38] **Ben:** I was listening to an interview the other day. I wish I could remember what podcast it was. And they were saying that, I think this was the. Dave Farley's podcast. I can't remember what it's called. It's like the programming room or something. Anyway.

[00:59:51] **Ben:** I think they were saying that if,

[00:59:52] **Adam:** get a good look at a steak by sticking my head Wait, this is different, Farley. Sorry.

[01:00:02] **Carol:** You broke Ben.

[01:00:07] **Tim:** You broke

[01:00:07] **Adam:** I did it.

[01:00:08] **Ben:** Oh my God. I love that movie. Oh, for Carol's reference, that's Tommy boy.

[01:00:15] **Carol:** I was gonna guess Happy Gilmore.

[01:00:17] **Ben:** Types. Um,okay. Sorry. Sorry to get back on track there. I was listening to an interview and someone was saying that if something is hard to test, That is an indication that your code isn't well architected. I don't know. I feel like the fact that so much of an application involves taking data and putting it into an external resource, whether it be a file or a database or about API, I feel like that stuff is just inherently hard to test.

[01:00:45] **Ben:** And, and to say that the difficulty of testing that is an indication of poor architecture, I think either hand waves over a lot of unsaid things like, of course, you would mock out your database service, or of course, all of your business logic is built in pure functions and. Saving to a database happens at quote unquote, the edge of the application.

[01:01:10] **Ben:** Like there's a lot of stuff that's built in there that I think makes a lot of assumptions, but I, I, I, my S again, as someone who doesn't test. I would just assume that this is all very hard to test, period, and that that's not an indication that anything is wrong, per se.

[01:01:25] **Carol:** See, when I think of, is it hard to test? I'm thinking about a single block of code. Meaning, do I have so much logic in there that it takes 20 tests to get through it, and they all have different outcomes, and it's just very complex. Like, I want to break those out into very small pieces of work. That's just a single test can cover it like a happy bath and a not happy bath.

[01:01:47] **Adam:** to be, to be perfectly honest,

[01:01:50] **Ben:** I'll defer, yeah.

[01:01:51] **Adam:** to be perfectly honest, I just don't feel qualified to give like a, a good answer or like advice on this one, because I feel like I'm still on that journey, right? Like, I kind of have an idea of what, you know, hard to test code, like specifically what you're talking about, Ben, you're putting data in the database sort of thing.

[01:02:10] **Adam:** And like, why that can feel hard to test. And I have some ideas on like how I would. Change the code to make that easier to write tests for and that sort of thing. But I, I'm very much still on that journey and I just don't want to give somebody misinformation about, you know, like where I am now and then have that change in a year.

[01:02:28] **Ben:** and I think, and I think

[01:02:32] **Carol:** in of bad advice. Yeah,

[01:02:38] **Ben:** The fact that we have a mental model in our head, and we all have a sort of basic assumption that everyone else's mental model sort of lines up with ours, and it probably does in a lot of ways, and does not in maybe many more ways. So, case in point, when I think to myself, testing is inherently challenging and someone else thinks testing is inherently easy.

[01:03:01] **Ben:** If their version of testing should be inherently easy is I have to set up a special database in my CI CD server. And it has to have a set of like golden records that get loaded in at the start of tests. I'm like, Whoa, that's not easy. Like that whole thing you just said is very complicated just because it is a maybe established pattern.

[01:03:23] **Ben:** That's not easy. We're like, Oh, no problem. All you have to do is record the output of an API and then replay it back during your tests. I'm like, Whoa, that's not easy. That's really complicated. You probably had to build a, or pull in a special library that does just that kind of thing. Like that's not easy.

[01:03:39] **Ben:** And so it could just be the thing that I think is complicated is the thing that everyone else is like, Oh, that's just, that's just the way it's done. That's easy. And so it could just be a, a, the word for how you call things like nomenclature? Not nomenclature, terminology. I don't know. It could just be that we're just not on the same page about what words mean.

[01:04:02] **Tim:** But that's subject to change.

[01:04:06] **Adam:** There's a joke here about literally not meaning literally anymore, but I don't know.

[01:04:11] **Ben:** one of my favorite reaction gifts is Rob Lowe from Parks and Rec. Just go ahead. Literally.

[01:04:16] **Adam:** Yeah. All right. shall we wrap it there?

[01:04:19] **Ben:** Sure.

## [01:04:21] Patreon

[01:04:21] **Adam:** All right. Well, then this episode of Working Code is brought to you by the Brown Cross, available under a bridge near you. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this was out into the universe, then you should sink it, sink it, or I don't even know what I was going to say there.

[01:04:37] **Adam:** You should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks, as always, to our top patrons, Monte and G

## [01:04:47] Thanks For Listening!

[01:04:47] **Adam:** we're gonna go record the after show I gotta imagine we're gonna be talking about that owl show that that they had this weekend

[01:04:52] **Tim:** The superb owl?

[01:04:53] **Adam:** yeah the superb owl show, And I mean like, you know, the there's the dog thing, but they only do the owl

[01:05:00] **Ben:** Okay. Sorry. My luck totally went over my head.

[01:05:04] **Carol:** Yeah,

[01:05:06] **Adam:** yeah, there's a subreddit for everything. Don't worry about it. We'll get into it and i'm sure that there will be other stuff. So, if you want to find out more about the after show or just become a supporter of the show. We'll, we'll provide that to you. You can go to patreon.com/workingcodepod and learn more and throw us a few dollars every month.

[01:05:22] **Adam:** We greatly appreciate that. That's going to do it for us this week. We'll catch you next week. And until then,

[01:05:27] **Tim:** Remember your heart matters and the amount is yes.
