---
title: "269: The AI Anxiety Draft"
description: "This week, the hosts respond to a question from the State of Devs survey: “Which of these general AI risks and issues are you most concerned about?”"
date: 2026-08-06
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/089aca3c-bec1-455a-bf8b-0c0149b4403a"></script>
<div class="redcirclePlayer-089aca3c-bec1-455a-bf8b-0c0149b4403a"></div>

Worrying about AI is the easy part. Everyone already has a list. The interesting part is what lands on it, what doesn't, and why. From military use, to an AI slop takeover, to the possibility that the tools are making us stupider.

This week, the hosts respond to a question from the State of Devs survey: “Which of these general AI risks and issues are you most concerned about?”

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [State of Devs 2025 survey](https://survey.devographics.com/en-US/survey/state-of-devs/2025) — the questions that set off the discussion; the survey itself is now closed
- [OpenAI's Hugging Face security incident](https://openai.com/index/hugging-face-model-evaluation-security-incident/) — what happened when agents escaped a constrained cyber evaluation
- [LinkedIn's campaign against AI slop](https://news.linkedin.com/2026/keeping-conversations-real-on-linkedin) — the official explanation of its new reporting control
- [Cloudflare Pay Per Crawl](https://blog.cloudflare.com/introducing-pay-per-crawl/) — tools for publishers to allow, block, or charge AI crawlers

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/269-claude-fishing-season.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Carol:** Mhm.

[00:00:00] **Tim:** if I were out of token or I would really be in a bad place trying to fix this.

[00:00:04] **Adam:** M.

[00:00:04] **Adam:** Yeah.

[00:00:04] **Tim:** I wouldn't know where to begin.

[00:00:05] **Carol:** A big dependency.

[00:00:06] **Ben:** Yo,

[00:00:06] **Adam:** How long until my tokens refresh?

[00:00:06] **Carol:** Yeah.

[00:00:08] **Carol:** Right.

[00:00:08] **Adam:** And can I wait that long.

[00:00:08] **Tim:** Exactly.

[00:00:09] **Tim:** Exactly.

[00:00:11] **Tim:** Uh, am I getting stupider?

[00:00:12] **Tim:** No, but I'm definitely more dependent.

## [00:00:34] Intro

[00:00:34] **Adam:** Okay, here we go with show number 269.

[00:00:34] **Ben:** Mhm.

[00:00:36] **Adam:** And on today's show, we're going to talk about some questions from the State of Devs survey which is still open if you want to take it online.

[00:00:37] **Carol:** Mhm.

[00:00:43] **Adam:** We'll get into that a little bit more later.

[00:00:44] **Adam:** but you, uh, know, it goes into some ethical stuff about AI usage.

[00:00:47] **Adam:** We just thought it'd be fun to kind of game it out and talk and see where everybody stands.

[00:00:51] **Adam:** But first, as usual, let's start with the triumphs and fails.

[00:00:53] **Adam:** We got the whole crew here tonight again.

[00:00:56] **Ben:** Oh yeah,

[00:00:56] **Carol:** Hola.

[00:00:56] **Adam:** And Ben, I'm coming to you first, my friend.

[00:00:58] **Adam:** What's going on?

[00:00:59] **Ben:** sure.

## [00:01:00] Ben's Fail

[00:01:00] **Ben:** I'm going to start us off with a failure, uh, keeping it balanced.

[00:01:02] **Adam:** Okay.

[00:01:03] **Adam:** Keeping it balanced.

[00:01:05] **Ben:** So in the last show I mentioned that I was working on a syntax highlighting service that I'd love to consume eventually into my blog.

[00:01:14] **Ben:** And um, I was using it as a engine to try to explore more AI agentic coding and kind of just let the agent rip a little bit more.

[00:01:25] **Ben:** And last week I think I mentioned it was either.

[00:01:25] **Adam:** Mhm,

[00:01:27] **Ben:** I think it was maybe a triumph and a failure.

[00:01:29] **Ben:** So it was a little bit of a failure last week that I couldn't quite get out of my own way that I kept feeling like I was overthinking things.

[00:01:32] **Carol:** Mhm.

[00:01:32] **Adam:** Mhm.

[00:01:37] **Ben:** And uh, I will say that that is still the case that I do feel like I'm still maybe overthinking things.

[00:01:43] **Ben:** But it is a mild triumph in that I got a proof of concept deployed to Amazon Lambda.

[00:01:51] **Ben:** it's not like an automated deployment, it's not like a like an AWS CLI push or like a pull from GitHub kind of anything.

[00:01:59] **Ben:** I, I have my local Docker container generate a zip file and then I just go into the AWS console and I say like update function from zip file.

[00:01:59] **Adam:** Yeah,

[00:02:06] **Carol:** Mhm.

[00:02:07] **Adam:** Dude, it is.

[00:02:08] **Carol:** Boy, aren't you so fancy.

[00:02:08] **Adam:** It is so easy to automate that I have, I have Makefiles that run the zip command and then upload the zip using the AWS CLI Like.

[00:02:16] **Ben:** See this is like part of where I have these just weird emotional barriers.

[00:02:21] **Ben:** So in the effort to try to specify this project, you know extensively enough to have the agent just do it, uh, we talked a lot about where we were going to deploy, what were the constraints were, how was it going to be developed locally, what was the deployment situation going to be.

[00:02:33] **Carol:** Mhm.

[00:02:36] **Adam:** Mhm.

[00:02:40] **Ben:** Meaning was it code, was it a git pull, was it a ah, container registry?

[00:02:44] **Ben:** That kind of stuff.

[00:02:46] **Ben:** And everything that wasn't me uploading a zip file was like installing another command line tool, whether it be the, the Amazon CLI or like a ah,

[00:02:53] **Carol:** Sam.

[00:02:53] **Carol:** Mhm.

[00:02:55] **Adam:** Mhm.

[00:02:59] **Ben:** a Netlify kind of thing.

[00:03:01] **Ben:** And I just, I was like I don't want to do another CLI and then deal with credentials that I have to do.

[00:03:08] **Ben:** And especially with Amazon's console then I have to like do IAM roles for being able to deploy a Lambda function.

[00:03:15] **Carol:** Well I forgot about those.

[00:03:15] **Ben:** I'm just like f that I'm like you know what,

[00:03:17] **Carol:** And.

[00:03:17] **Adam:** You can just use your personal credentials, man.

[00:03:19] **Adam:** Just log in the AWS CLI You've got your personal credentials.

[00:03:21] **Tim:** Click run.

[00:03:22] **Tim:** Mhm.

[00:03:23] **Adam:** You can do a little like, there's like AWS login command in the CLI and that stores your credentials.

[00:03:27] **Ben:** It's too much, it's too much.

[00:03:28] **Carol:** Uh,

[00:03:29] **Adam:** That's not that hard.

[00:03:29] **Ben:** So, so like I'm doing the uh, the quote unquote click ops strategy where I'll uh, just go to the Lambda console and upload from the zip file.

[00:03:29] **Adam:** It's.

[00:03:30] **Carol:** listen

[00:03:30] **Adam:** Now stop being a wiener.

[00:03:33] **Carol:** sa.

[00:03:39] **Ben:** So I'm calling that a triumph people.

[00:03:42] **Adam:** That's a failure.

[00:03:42] **Ben:** Um, but it's just again it's one of these things where like you see it on TV and then you open the box at home, you're like, this does not look like the thing they had on television.

[00:03:45] **Tim:** You're holding it wrong.

[00:03:54] **Tim:** Mhm mhm mhm mhm mhm mhm mhm mhm mhm.

[00:03:54] **Carol:** Mhm.

[00:03:56] **Ben:** Uh,

[00:03:56] **Adam:** We have Lambda at home.

[00:03:59] **Adam:** The Lambda we have at home is zip files that you manually drag up that.

[00:04:04] **Ben:** but it's just, it's like the, the conversations that I have with Claude Code go back and forth and uh, it, it's telling me about cold start times and limiting the number of grammars that I pull into this syntax highlighting.

[00:04:14] **Carol:** Mhm,

[00:04:17] **Adam:** Mhm.

[00:04:17] **Ben:** But then Lambda has a lot of memory overhead, like, like memory space to work with and the cold starts actually only a couple of seconds and it like almost doesn't matter that much because I'm not going to use it that often.

[00:04:27] **Adam:** Sa.

[00:04:28] **Ben:** But then it says, oh, you want to limit the grammars because sometimes you get false positives on the way the fenced code blocks work.

[00:04:35] **Ben:** Like you say that the language is this and it actually maps to the wrong grammar so you have to limit the grammars.

[00:04:38] **Adam:** Mhm.

[00:04:40] **Ben:** So then we're going down like a curated grammar list.

[00:04:42] **Ben:** And then eventually it's like, oh, by the way, you don't actually have to curate grammars.

[00:04:46] **Ben:** You can just override mappings between language extensions and the grammar that gets used.

[00:04:52] **Ben:** And it's just like all this back and forth and it's, it's exhausting.

[00:04:56] **Ben:** And again I just, it's so hard for me to look at the struggle that I'm feeling and then

[00:04:56] **Carol:** Mhm.

[00:05:04] **Ben:** see how other people don't struggle and seem to just find so much joy.

[00:05:10] **Ben:** And like, I'll caveat to say that if it wasn't for AI, I would never even try this project.

[00:05:16] **Ben:** The idea of using uh, Starry Night and pulling in special syntax highlighting and building a Docker container that generates a zip file and does like a multi-step Docker build that does npm installs and then pulls the resources from that and then pulls, you know, stuff from this and that.

[00:05:17] **Adam:** Mhm.

[00:05:17] **Carol:** Mhm.

[00:05:26] **Adam:** Mhm.

[00:05:32] **Ben:** Like it's the, the overall orchestration of everything that's happening across these like four code files, like it's actually a very small project is so far beyond what I would feel comfortable doing.

[00:05:38] **Carol:** Sam.

[00:05:38] **Carol:** Mhm.

[00:05:44] **Ben:** So like on one hand it's amazing how enabling it feels

[00:05:51] **Ben:** and at the same time I feel uh, that I'm so far behind when I hear about other people's ability to just let things rip and.

[00:06:00] **Adam:** M.

[00:06:00] **Adam:** Dude, you have a subscription service to all of the world's knowledge at your fingertips, literally.

[00:06:06] **Adam:** And you're like, don't automate it too much because it makes my tum tum hurt.

[00:06:14] **Adam:** You don't even have to think about it.

[00:06:15] **Adam:** Just be like, help me do this.

[00:06:16] **Adam:** Tell me what to do.

[00:06:18] **Ben:** It's.

[00:06:18] **Ben:** I, I uh, know.

[00:06:19] **Ben:** And maybe that's, maybe that's the failure part of this is like I uh, some part of me just still wants to kind of understand how it works and so I don't want it to do anything too crazy.

[00:06:29] **Adam:** It'll teach you.

[00:06:33] **Ben:** Oh, uh,

[00:06:35] **Carol:** Can I, can I add one thing real quick?

[00:06:35] **Adam:** I

[00:06:36] **Carol:** So you're talking about your like AWS and trying to like give it your I like your IAM um, permissions and stuff in AWS I was working on something where I was just trying to get a PowerShell script to work that would let me loop through the API endpoint M on our deployment service.

[00:06:36] **Ben:** please.

[00:06:37] **Ben:** Mhm,

[00:06:37] **Adam:** up.

[00:06:48] **Adam:** Mhm.

[00:06:52] **Carol:** And I forgot that in my PowerShell script which I was just running on my local I had just picked up pasted in my API key to authenticate to the deployment server to do it.

[00:07:02] **Carol:** So immediately Claude's like, oh yeah, I read the files by the way, you've exposed your API key.

[00:07:10] **Carol:** I'm going to use it, but you should definitely change it.

[00:07:13] **Carol:** I let it create me two scripts and then I logged in and changed my key.

[00:07:16] **Adam:** Yep.

[00:07:17] **Ben:** Mhm.

[00:07:17] **Carol:** I was like, dang it.

[00:07:18] **Carol:** This is the problem with giving you access.

[00:07:20] **Carol:** The things I used to run in Postman, I didn't always use sensitive variables.

[00:07:22] **Tim:** Mhm mhm mhm mhm mhm mhm mhm.

[00:07:25] **Carol:** I'm like, let me just run it and see what the outcome is and let me easily know when I need to rotate something because that one's expired.

[00:07:28] **Adam:** Mhm.

[00:07:31] **Carol:** I have to be super selective about how I even do things in my local now because I accidentally expose keys that I don't mean to expose.

[00:07:41] **Ben:** Well that was part of the thought process that I had when it said, hey, let me just use the AWS CLI My assumption was at some point I'm showing you a credential somewhere that you probably shouldn't have access to.

[00:07:54] **Ben:** And maybe that's not true, but even if I put it in like an env file, I'm like, you have access to this directory.

[00:07:59] **Adam:** Yeah, it.

[00:08:00] **Carol:** They still read them.

[00:08:01] **Carol:** Yeah,

[00:08:01] **Adam:** It does time out.

[00:08:04] **Carol:** mhm,

[00:08:04] **Adam:** So I would have to.

[00:08:05] **Adam:** My, my gut says it's like an OAuth type situation.

[00:08:08] **Adam:** Like you log in through the CLI which you know, you're putting your, your information in and then, and then you've got a session that lasts a week or two or a month or whatever it is.

[00:08:11] **Ben:** Hmm.

[00:08:11] **Ben:** Mhm.

[00:08:14] **Carol:** Mhm.

[00:08:17] **Adam:** I don't know.

[00:08:18] **Adam:** Um, and then, so, yeah, I mean, there is a token that has to come back from that through that OAuth process or whatever.

[00:08:23] **Adam:** But, uh, yeah, and you can go in and revoke it too.

[00:08:26] **Ben:** Yeah.

[00:08:26] **Adam:** Just saying.

[00:08:27] **Carol:** You sure can.

[00:08:29] **Ben:** Or I can just log into the console and upload the zip file.

[00:08:32] **Adam:** Mhm.

[00:08:33] **Adam:** Oh, Ben All right.

[00:08:34] **Adam:** Thus ends this week's episode of old man yells at cloud.

[00:08:35] **Ben:** Yeah.

[00:08:36] **Ben:** Yeah.

[00:08:36] **Ben:** All right,

[00:08:38] **Ben:** so that's my failure.

[00:08:40] **Ben:** Carol, what do you got going on?

[00:08:41] **Carol:** Yeah.

## [00:08:41] Carol's Triumph

[00:08:41] **Carol:** I'm gonna go to Big Triumph.

[00:08:43] **Carol:** It's not a tech related one, it's a personal one.

[00:08:45] **Carol:** Um, I had set myself up to run a half marathon by October time frame and I'm actually signed up to run one in April.

[00:08:51] **Adam:** Mhm,

[00:08:54] **Carol:** So I'm super excited about that.

[00:08:56] **Ben:** Nice.

[00:08:56] **Carol:** But with us having to take two weeks off from having 24 hour supervision over our dog that was not recovering well.

[00:09:06] **Carol:** I thought it was going to completely set me back in my training plan because I wasn't able to run.

[00:09:11] **Adam:** Mhm,

[00:09:12] **Carol:** It was get up, watch the dog, let Steve sleep a little while and um, while he was sleeping I handled the dog and then while I'm working he's handling the dog.

[00:09:21] **Ben:** Mhm.

[00:09:21] **Carol:** So it was a lot, a lot on us.

[00:09:22] **Ben:** Mhm.

[00:09:23] **Carol:** Well, I jumped back into my plan and it only took me a week to get back on track to be right back where I was.

[00:09:31] **Carol:** So I was just super motivated to feel like even though I've been stressed at work, we have a lot going on.

[00:09:32] **Adam:** Mhm,

[00:09:36] **Carol:** I can still recover, like to a healthy state even after taking two weeks off from training.

[00:09:42] **Carol:** And uh, it, it made me feel good about myself and where my body is, I guess.

[00:09:43] **Ben:** yeah.

[00:09:47] **Tim:** Uh,

[00:09:50] **Carol:** Not that.

[00:09:52] **Ben:** No, that's awesome.

[00:09:53] **Ben:** And that gives me hope because I'm also raising a puppy here and I uh, have not worked out in an undisclosed amount of time.

[00:10:00] **Ben:** And uh, and I am definitely leaning heavy on the idea that I will be able to bounce back.

[00:10:06] **Carol:** Yeah, I'm sure you will, you'll get back there.

[00:10:08] **Carol:** Just give yourself some leeway.

[00:10:10] **Carol:** All right, well, that's me.

[00:10:11] **Carol:** What about you, Tim?

## [00:10:15] Tim's Triumph

[00:10:15] **Tim:** More like a vibe check kind of triumph.

[00:10:17] **Carol:** Oh,

[00:10:18] **Adam:** Mhm.

[00:10:18] **Adam:** Okay.

[00:10:19] **Tim:** So.

[00:10:20] **Tim:** So yeah, like a couple weeks ago it was like super stressful stuff just like hitting the fan and things are breaking and like stuff that just like really shouldn't be happening.

[00:10:22] **Adam:** Sa.

[00:10:25] **Ben:** Mhm,

[00:10:28] **Tim:** And it's all happening same week,

[00:10:30] **Carol:** Mhm.

[00:10:32] **Tim:** same time.

[00:10:32] **Tim:** I'm doing interviews and also doing everyone

[00:10:36] **Tim:** did your assessments and scorecards.

[00:10:40] **Tim:** Thank goodness I automated a huge portion of that.

[00:10:43] **Tim:** But um, so we haven't had any that.

[00:10:45] **Tim:** I really probably shouldn't even say this out loud.

[00:10:45] **Ben:** Mhm.

[00:10:47] **Tim:** I'm going to jinx it.

[00:10:48] **Tim:** We haven't really had any disasters the past seven working days.

[00:10:51] **Carol:** Mhm, mhm.

[00:10:51] **Tim:** Um, I mean

[00:10:53] **Adam:** Sad that the bar is that low.

[00:10:54] **Tim:** right.

[00:10:55] **Tim:** Seven days.

[00:10:56] **Tim:** Yeah, I'm like just, I'm like it's kind of quiet.

[00:10:59] **Tim:** Uh, and I even shut down during this passive day.

[00:11:01] **Tim:** I shut down on Amazon AWS like about uh, $4,000 worth of different services, a bunch of microservices, uh, some database stuff, uh, converted the database, latest version of PostgreSQL, our Lord and Savior.

[00:11:08] **Adam:** Nice.

[00:11:10] **Ben:** Heck yeah.

[00:11:14] **Adam:** Mhm.

[00:11:18] **Tim:** Because we were paying like a $250 a month uh, term support fee on those because I just, I knew this database was going away.

[00:11:26] **Tim:** I didn't want to mess with trying to upgrade it, dealing with nonsense.

[00:11:30] **Tim:** But did, uh, the upgrade moved the tables over and everything worked really, really well.

[00:11:35] **Tim:** So nothing's broken.

[00:11:37] **Tim:** And I'm kind of waiting for the other shoe to drop.

[00:11:40] **Tim:** You know what I mean?

[00:11:40] **Ben:** Mhm.

[00:11:42] **Tim:** So I'll enjoy the triumph while I can.

[00:11:42] **Adam:** Mm.

[00:11:45] **Tim:** I had like two afternoons in a row with like almost no interruptions, which is extremely rare.

[00:11:51] **Carol:** M.

[00:11:51] **Carol:** Holy moly.

[00:11:52] **Adam:** Well, there's one thing that's for certain, Tim, and that is the streak's gonna be what it's gonna be.

[00:11:56] **Adam:** But eventually it.

[00:11:58] **Tim:** Exactly.

[00:11:58] **Carol:** Mhm.

[00:11:58] **Tim:** Everything has a beginning, it also has an end.

[00:11:59] **Adam:** Mhm.

[00:12:00] **Tim:** And I know what's going to happen.

[00:12:01] **Tim:** I'm taking Thursday Friday off and so that's when it's all going to happen and I'm going to.

[00:12:05] **Ben:** M.

[00:12:06] **Ben:** Sounds like someone else's problem.

[00:12:08] **Tim:** If only it worked that way.

[00:12:12] **Carol:** At work.

[00:12:12] **Carol:** At work we had this like issue that popped up where we had some users were getting this weird tab not loading error and to me I was like, oh, clearly database problem.

[00:12:19] **Adam:** Mhm.

[00:12:20] **Ben:** Sa.

[00:12:20] **Tim:** Sa.

[00:12:24] **Carol:** Like everyone should be getting the error.

[00:12:26] **Carol:** Nope.

[00:12:26] **Carol:** Three servers were not.

[00:12:28] **Carol:** Like they were having issues with assert auth and searching authority.

[00:12:28] **Adam:** Sa.

[00:12:30] **Ben:** Mhm.

[00:12:32] **Carol:** Something happened.

[00:12:33] **Tim:** Mhm.

[00:12:33] **Carol:** I get on the call and I'm like, hey guys, here are the logs.

[00:12:36] **Carol:** I think it's just, you know, three machines.

[00:12:38] **Carol:** We need to restart them.

[00:12:39] **Carol:** Um, someone else is researching how and someone else is making sure the alerting's there so it doesn't happen.

[00:12:40] **Adam:** Mhm.

[00:12:43] **Carol:** If it happens in the future, we'll see it.

[00:12:45] **Carol:** Right.

[00:12:45] **Carol:** But at the end of the call, one of the DevOps guys goes, oh, wow, this is like amazing.

[00:12:51] **Carol:** I remember back in the day when these calls would take four and five hours and we're off in like half an hour.

[00:12:57] **Carol:** I was like, buddy, you're on call now because you've just spoken into existence and now we are all going to be on a support call for six hours because things won't come online.

[00:13:02] **Adam:** Yep.

[00:13:03] **Ben:** You bastard.

[00:13:07] **Carol:** I was like, so someone sent him the phone.

[00:13:11] **Tim:** I tell you, certificate issues and DNS issues are the bane of my existence.

[00:13:16] **Ben:** Yo.

[00:13:16] **Carol:** So bad.

[00:13:16] **Ben:** We had a DNS issue just the other day at work.

[00:13:19] **Carol:** Yep.

[00:13:19] **Adam:** Sa.

[00:13:19] **Ben:** It was like, that was the uh, like Internet went down, I think briefly to the office and then it came back up and for whatever reason, like one entire building's computers just couldn't figure out how to get back on the network.

[00:13:20] **Tim:** It's always DNS.

[00:13:22] **Adam:** Mhm.

[00:13:33] **Carol:** Yeah.

[00:13:33] **Carol:** Like how do your routes get like jacked up into something going offline?

[00:13:37] **Carol:** Like it does not make sense to me.

[00:13:40] **Ben:** Computers are magic, man.

[00:13:44] **Tim:** So anyway, that, that's my weak triumph, my vibe check.

[00:13:47] **Tim:** How about you?

[00:13:48] **Tim:** AD.

## [00:13:50] Adam's Triumph

[00:13:50] **Adam:** Well, mine, uh, is also on the weak side.

[00:13:51] **Adam:** But, uh, you know, I'm gonna go with it.

[00:13:53] **Adam:** Uh, I have a triumph, uh, which is that, ah, you know, I've just another week of putting food on the dinner table for my family, man.

[00:13:56] **Tim:** Mhm.

[00:13:59] **Adam:** You know, like just coming in, doing the work.

[00:14:02] **Adam:** Not every day is, uh, uh, worth talking about, I guess.

[00:14:07] **Ben:** Like it.

[00:14:08] **Ben:** That's always a triumph.

[00:14:10] **Adam:** Yeah, man.

[00:14:11] **Adam:** um, no disasters, right?

[00:14:11] **Adam:** Like Tim's talking about.

[00:14:12] **Ben:** Yeah.

[00:14:12] **Carol:** Mhm.

[00:14:13] **Adam:** I'm on my streak.

[00:14:14] **Adam:** Whatever the streak is currently.

[00:14:16] **Adam:** And that's all I want to say about that because otherwise it'll end it.

[00:14:19] **Carol:** Don't speak it.

[00:14:19] **Tim:** Mhm.

[00:14:20] **Carol:** Don't speak it.

[00:14:20] **Tim:** Testing.

[00:14:21] **Tim:** Testing the universe.

[00:14:24] **Adam:** Okay, well, uh, why don't we move into our show topic today?

[00:14:26] **Adam:** this is a recent record, man.

[00:14:28] **Adam:** We're done in less than 15 minutes with, uh, triumphs and fails.

[00:14:31] **Adam:** Wow.

[00:14:31] **Ben:** Heck yeah.

[00:14:31] **Adam:** We.

[00:14:32] **Adam:** We should get an award.

[00:14:32] **Tim:** Mhm mhm mhm mhm mhm.

## [00:14:33] Military AI and Autonomous Decisions

[00:14:33] **Adam:** okay, so the State of Devs survey right?

[00:14:34] **Carol:** Mhm.

[00:14:35] **Adam:** There's all these surveys that you can take.

[00:14:36] **Adam:** The State of CSS the State of JavaScript the state of whatever.

[00:14:40] **Adam:** This one is more like developers, uh, mental health.

[00:14:44] **Adam:** And for whatever reason this year kind of went into like, AI stuff.

[00:14:48] **Ben:** Mhm,

[00:14:49] **Adam:** So if you're interested in these types of things, we'll, we'll have a link in the show notes.

[00:14:53] **Adam:** I'll also just say real quick, it's survey.devographics.com uh, and then I'm sure you can find it from there.

[00:14:54] **Carol:** Mhm.

[00:14:59] **Adam:** but there were a couple of questions in it that we thought would be interesting to kind of dig into and discuss amongst the four of us.

[00:15:05] **Adam:** I guess let's just go through them.

[00:15:06] **Adam:** Right?

[00:15:06] **Carol:** Sam.

[00:15:06] **Carol:** Mhm.

[00:15:06] **Adam:** to.

[00:15:07] **Adam:** It asks a question and then it gives you a bunch of options and it's pick four.

[00:15:10] **Adam:** Okay, so this is the question.

[00:15:12] **Adam:** Which of these general AI risks and issues are you most concerned about?

[00:15:18] **Adam:** Okay, Okay, so military use of AI, environmental impact, AGI being reached, job displacement, security issues, rising AI costs, entrenched stack bias, open source disruption, AI overuse, copyright and ethics issues, AI slop takeover, negative cognitive impacts, and then there's an other where you can like write it in your own, uh, concerns.

[00:15:26] **Ben:** Mhm.

[00:15:47] **Carol:** I kind of.

[00:15:47] **Ben:** Why is there not all of the above?

[00:15:49] **Carol:** I know, I know.

[00:15:49] **Adam:** Yeah,

[00:15:50] **Tim:** M.

[00:15:51] **Adam:** because that's.

[00:15:52] **Adam:** That, that's the thing is they're, they're forcing you to choose what is most concerning for you.

[00:15:58] **Adam:** That's why I found this question so interesting.

[00:15:58] **Carol:** Yeah.

[00:15:59] **Tim:** The top four.

[00:16:00] **Tim:** Yeah

[00:16:02] **Adam:** The top.

[00:16:02] **Adam:** Yeah.

[00:16:02] **Ben:** Uh, I'll say if I can just jump in.

[00:16:03] **Adam:** Your personal top four.

[00:16:04] **Adam:** Yeah.

[00:16:04] **Tim:** there.

[00:16:07] **Ben:** I think,

[00:16:07] **Adam:** Mhm.

[00:16:10] **Ben:** um, for me, the military use of AI feels like the most overblown and like least grounded in reality.

[00:16:14] **Carol:** Mhm.

[00:16:17] **Ben:** At least.

[00:16:18] **Ben:** Maybe that's, maybe that's an optimistic hope.

[00:16:20] **Adam:** That's an interesting thing to say considering I think we just saw in the news recently that the first person had been killed by a decision, uh, made by AI.

[00:16:22] **Carol:** Sam.

[00:16:25] **Ben:** Ah, uh, that's disappointing.

[00:16:26] **Tim:** Sa.

[00:16:27] **Adam:** Like militarily.

[00:16:28] **Adam:** Yeah.

[00:16:29] **Ben:** I, I guess like my assumption.

[00:16:32] **Ben:** And again, this is me just making up stories in my head is that so many people are, I assume, involved in how things get done in the military because it's this giant industrial complex

[00:16:32] **Tim:** Mhm mhm.

[00:16:35] **Carol:** Mhm.

[00:16:40] **Adam:** Sa.

[00:16:44] **Adam:** Mhm.

[00:16:45] **Ben:** that even if there's AI, I have to imagine there are so many humans in the loop.

[00:16:51] **Ben:** I mean, we have people who have to simultaneously turn keys to arm things.

[00:16:56] **Ben:** Like that's the mentality that, that the military has.

[00:16:58] **Ben:** Uh, so for me, I think the military use of AI is a fun one to like get angry about.

[00:17:05] **Adam:** Mhm.

[00:17:05] **Ben:** Uh, and like, I enjoy getting angry about it, but I, it's the, it's like almost the one that worries me the least.

[00:17:12] **Ben:** But I didn't know that someone actually got killed.

[00:17:13] **Tim:** Yeah.

[00:17:13] **Tim:** Yeah, definitely.

[00:17:13] **Carol:** Yeah.

[00:17:13] **Tim:** It wouldn't be my top four.

[00:17:15] **Tim:** I mean I'm definitely interested, but it's not my top four.

[00:17:15] **Carol:** Yeah.

[00:17:16] **Adam:** Okay, that's interesting.

[00:17:18] **Adam:** I, I put it in.

[00:17:19] **Carol:** So.

[00:17:19] **Adam:** It's one of my four because.

[00:17:21] **Adam:** So, okay, so I picked it.

[00:17:22] **Adam:** So let me read the, the description line.

[00:17:23] **Ben:** Yeah,

[00:17:24] **Adam:** So it's autonomous drones, AI decision making, etc.

[00:17:28] **Adam:** That's what they put in there.

[00:17:29] **Adam:** And maybe I picked it because of the current administration and how over eager they seem to be for using AI.

[00:17:34] **Tim:** Mhm mhm.

[00:17:36] **Carol:** M.

[00:17:38] **Carol:** Mhm.

[00:17:38] **Adam:** Right.

[00:17:39] **Adam:** The President is posting AI memes all the time.

[00:17:42] **Adam:** They're constantly being caught using AI generated text in like legal documents and what's the releases and all kinds of other stuff,

[00:17:47] **Ben:** Yeah, that's true.

[00:17:53] **Adam:** not just AI generated.

[00:17:55] **Adam:** Like okay, sure.

[00:17:56] **Adam:** So you were too lazy to, to do your job and type it out.

[00:17:58] **Adam:** But like obviously AI generated because it, it includes Uh, like when it makes stuff up, uh, hallucinations.

[00:18:04] **Ben:** Yay.

[00:18:04] **Ben:** Yay.

[00:18:05] **Carol:** Hallucinations?

[00:18:05] **Adam:** Right.

[00:18:06] **Adam:** So to me, maybe it's partly who's got their hands on the controls, but that feels really concerning.

[00:18:12] **Ben:** I, I could see that.

[00:18:12] **Carol:** M.

[00:18:16] **Ben:** Well, is if.

[00:18:17] **Ben:** Do we have any government people on this show that could maybe speak on behalf of the entire government.

[00:18:23] **Carol:** No, I don't, I don't think there are.

[00:18:27] **Ben:** Going through a tunnel.

[00:18:30] **Adam:** You're breaking up.

[00:18:31] **Tim:** Mhm mhm.

[00:18:32] **Ben:** I know.

[00:18:32] **Ben:** I guess my uh, like again, my hope is that this is so sci fi feeling that it feels implausible.

[00:18:37] **Adam:** Mhm.

[00:18:39] **Ben:** But maybe that's just wishful thinking.

[00:18:41] **Ben:** Maybe that's like me just living under my happy rock.

[00:18:45] **Adam:** Maybe

[00:18:45] **Carol:** Well, no.

[00:18:46] **Carol:** Okay, so Ben said not, not military use of AI.

[00:18:49] **Carol:** Uh, do you have one that you do that you would say is your top or do you want us to go through one that we picked?

[00:18:55] **Ben:** it's such a.

[00:18:55] **Carol:** Yeah.

## [00:18:57] Security Risks in AI-Generated Code

[00:18:57] **Ben:** I'm becoming increasingly concerned about all of the security issues.

[00:19:01] **Carol:** Mhm.

[00:19:02] **Carol:** Yeah.

[00:19:02] **Ben:** I mean there's been so many uh, marquee article titles recently about

[00:19:08] **Ben:** Anthropic accidentally hacking stuff.

[00:19:10] **Ben:** OpenAI accidentally hacking stuff.

[00:19:11] **Adam:** Mhm.

[00:19:13] **Carol:** More and more.

[00:19:13] **Carol:** Right?

[00:19:14] **Ben:** Yeah,

[00:19:15] **Tim:** Yeah but that comes off me like marketing ploy Honestly, I, I don't know how genuine all that is

[00:19:17] **Ben:** I.

[00:19:18] **Ben:** I know.

[00:19:22] **Carol:** Yeah.

[00:19:22] **Adam:** So.

[00:19:22] **Carol:** The.

[00:19:23] **Tim:** because you're like, yeah.

[00:19:25] **Tim:** And it was, you know, they had two other engineers helping prompt it, right?

[00:19:30] **Tim:** So it's not like the AI just went off on its own.

[00:19:32] **Tim:** They, they like, they steered it and they're like, oh, we're so dangerous.

[00:19:35] **Carol:** Interactive.

[00:19:38] **Adam:** Maybe.

[00:19:39] **Adam:** Yeah.

[00:19:40] **Carol:** Yeah,

[00:19:40] **Adam:** Uh, we would have to have more transparency to know for sure if that's the case.

[00:19:43] **Tim:** Mhm, mhm, mhm, mhm mhm mhm mhm mhm.

[00:19:44] **Carol:** yeah.

[00:19:44] **Carol:** Security is one of those that I picked.

[00:19:46] **Carol:** And for the, like the, the listing on security issues and security issues and exploits and AI, uh generated code.

[00:19:54] **Carol:** So I don't think it's just the.

[00:19:56] **Carol:** Oh, you know, OpenAI breaks out and hits Hugging Face like it's other things.

[00:19:59] **Ben:** Sa.

[00:20:02] **Carol:** It's the code that's being generated that has these exploits in them as well.

[00:20:07] **Carol:** Like, I am meeting with my team to figure out how we even share stuff, how we keep things secure.

[00:20:07] **Adam:** Mhm.

[00:20:12] **Carol:** And I'm going, how do we share agents?

[00:20:14] **Adam:** Don't paste API keys into your prompts.

[00:20:15] **Carol:** And

[00:20:16] **Carol:** okay, don't, don't get me fired, you guys.

[00:20:21] **Carol:** But like, how do we keep our agents from going rogue if the creators of said models and agents can't keep their own systems from going rogue?

[00:20:32] **Carol:** I think that security is a valid concern.

[00:20:35] **Adam:** Yeah, it's,

[00:20:35] **Carol:** It's one of my, it's one of my top ones.

[00:20:37] **Adam:** It's interesting to see how people read the question too because it wasn't one of.

[00:20:42] **Adam:** I'll say that it wasn't one of the ones that I picked.

[00:20:44] **Adam:** I do have concerns, but I don't think it rated my top four.

[00:20:47] **Adam:** so.

[00:20:48] **Adam:** And maybe I was kind of misled by the sub line here.

[00:20:51] **Adam:** It says security issues and exploits in AI generated code.

[00:20:54] **Adam:** So maybe I was kind of thinking at it, thinking about it at the time more as security issues that that exist.

[00:20:55] **Ben:** I see

[00:21:00] **Ben:** that you're creating.

[00:21:00] **Adam:** Because the code was AI generated.

[00:21:02] **Carol:** That you're building.

[00:21:03] **Adam:** Yeah, yeah.

[00:21:04] **Adam:** And, and in my experience so far, I don't.

[00:21:04] **Ben:** Mhm,

[00:21:08] **Adam:** I think AI is a lot better at finding bugs and and writing code that is secure by default than I am, you know, given the even 10 times as much time.

[00:21:22] **Adam:** Right.

[00:21:23] **Adam:** And.

[00:21:24] **Carol:** I agree.

[00:21:24] **Carol:** But like, I had Claude review one security finding and its initial suggesting, and this was on Fable by the way, was to go back a package like seven versions ago and pin it because that's the only one that had no vulnerabilities in it.

[00:21:36] **Adam:** Mhm.

[00:21:40] **Carol:** And I went, well, that's not really doable.

[00:21:41] **Ben:** Mhm, mhm,

[00:21:42] **Carol:** We've built everything on like a DOT three version.

[00:21:45] **Carol:** Like it has to be three, we can't go back to two.

[00:21:47] **Carol:** Like that's not.

[00:21:48] **Adam:** Right,

[00:21:48] **Carol:** The code won't work.

[00:21:50] **Carol:** And it's like, oh, I can see that.

[00:21:51] **Carol:** Well, let's just see if your code exposes anything that the vulnerability is fine and its first suggestion isn't, oh, let me see if the code actually has problems, like has the vulnerability in it or if you're not even using that piece instead it's like go back seven versions, which is not an option.

[00:22:03] **Ben:** Mhm.

[00:22:04] **Adam:** Right,

[00:22:08] **Adam:** right.

[00:22:08] **Adam:** Yeah.

[00:22:09] **Adam:** Like on my compliance, the scans that we're doing, the internal and external PCI scans we have to do, you know, we occasionally get dinged for like oh, this particular site uses a really old version of jQuery and there's like this particular exploit in it.

[00:22:20] **Adam:** I'm like, yeah, okay, that's great.

[00:22:22] **Adam:** But we don't use that function and so it doesn't matter.

[00:22:24] **Carol:** Right, mojedas?

[00:22:25] **Carol:** Right.

[00:22:26] **Ben:** That's like.

[00:22:27] **Ben:** I keep getting the um.

[00:22:28] **Ben:** Was it the Dependabot alerts on GitHub?

[00:22:30] **Adam:** Mm mhm.

[00:22:31] **Ben:** I keep getting them for a repository that is a proof of concept of a client side only build for something that I literally haven't touched in like nine years.

[00:22:31] **Tim:** Mhm mhm.

[00:22:41] **Adam:** You know you can turn that off.

[00:22:42] **Adam:** Right.

[00:22:42] **Carol:** Yeah.

[00:22:43] **Ben:** I, I don't.

[00:22:44] **Ben:** That uh.

[00:22:44] **Ben:** I feel like that's not my responsibility.

[00:22:47] **Adam:** It is your responsibility.

[00:22:48] **Adam:** You turned it on.

[00:22:48] **Ben:** How dare.

[00:22:49] **Ben:** Did I.

[00:22:50] **Ben:** I don't remember turning it on.

[00:22:51] **Adam:** There's, there's a Dependabot YAML file or something like that in uh, the, in the, in the repo.

[00:22:56] **Carol:** Oh, oh, wait, is this, is this work or is this a personal thing?

[00:22:56] **Adam:** That's what turns it on.

[00:23:00] **Ben:** This is a person.

[00:23:00] **Ben:** This is just like a personal repo on GitHub.

[00:23:02] **Carol:** Oh,

[00:23:03] **Adam:** Yeah, totally your fault.

[00:23:04] **Carol:** totally your fault.

[00:23:05] **Ben:** I don't think so.

[00:23:06] **Ben:** I take umbrage.

[00:23:09] **Carol:** What about you, Tim?

## [00:23:10] Job Displacement and AI Economics

[00:23:10] **Carol:** Give us one.

[00:23:11] **Tim:** Um, so I'm looking at job displacement

[00:23:14] **Ben:** Mhm.

[00:23:14] **Carol:** Oh,

[00:23:15] **Tim:** probably being, I'm probably being biased because Cory Doctorow has been all over the podcast circuit, uh, circuit He was on Jon Stewart, interviewed him on his podcast.

[00:23:25] **Carol:** Mhm, mhm,

[00:23:28] **Ben:** M.

[00:23:28] **Tim:** I um, was driving.

[00:23:28] **Adam:** He was on the Daily Show Yeah.

[00:23:28] **Ben:** He just published a book.

[00:23:29] **Tim:** He was on the Daily Show.

[00:23:30] **Tim:** I figured he had been.

[00:23:32] **Tim:** Um, I was, we were driving somewhere.

[00:23:34] **Tim:** I was driving the truck and my wife and the kids were in car and I get out, I was listening to NPR They work too.

[00:23:41] **Tim:** It was, Cory was on there.

[00:23:43] **Tim:** I didn't know what they were doing and it was kind of raining.

[00:23:46] **Tim:** So I ran in the house and they all just sat in the car.

[00:23:47] **Adam:** Mhm.

[00:23:48] **Tim:** I thought it's not raining that bad.

[00:23:50] **Tim:** So I check on them and they give me this signal of we're listening and they're having the driveway moment, right?

[00:23:55] **Adam:** Sa.

[00:23:56] **Tim:** So they're listening to Cory Doctorow.

[00:23:57] **Carol:** Mhm.

[00:23:58] **Tim:** Um, and his big argument about job displacement is that the point he was making is like AI companies.

[00:24:06] **Ben:** Mhm.

[00:24:06] **Tim:** I don't know the time box that he was doing, but let's just say it was the past year spent a trillion dollars on AI earning on that same trillion dollars, $550 billion.

[00:24:19] **Tim:** That's a terrible business model.

[00:24:21] **Adam:** Mm.

[00:24:21] **Adam:** Mhm.

[00:24:22] **Tim:** No business model.

[00:24:23] **Tim:** The world loses as much money as AI right now.

[00:24:25] **Carol:** Huge.

[00:24:26] **Carol:** Yeah.

[00:24:27] **Tim:** So why are they doing it?

[00:24:27] **Adam:** Mhm.

[00:24:27] **Ben:** Right.

[00:24:29] **Tim:** Uh, because their bet is that they, you know, rightly or wrongly, uh, they can say that AI can do the

[00:24:31] **Ben:** Sa.

[00:24:37] **Tim:** people's job.

[00:24:37] **Tim:** And he's like, people are replacing, you know, it's not, you know, these little people, it's not it.

[00:24:45] **Tim:** They're going.

[00:24:45] **Tim:** In order to justify the expense, you have to replace top dollar people.

[00:24:50] **Tim:** Most expensive people are developers who are pretty expensive and also executives are pretty expensive to.

[00:24:50] **Adam:** Mm mhm.

[00:24:53] **Carol:** Mhm.

[00:24:58] **Carol:** Mm.

[00:24:58] **Carol:** Mhm,

[00:24:59] **Tim:** I'm the worst because I'm a developer who is also an executive.

[00:25:00] **Ben:** Mhm.

[00:25:01] **Adam:** You're both.

[00:25:05] **Tim:** And it doesn't matter if AI, ah, can actually do the job.

[00:25:08] **Tim:** They can convince your boneheaded CEO

[00:25:11] **Adam:** Yeah,

[00:25:11] **Tim:** that they can

[00:25:12] **Ben:** Right.

[00:25:14] **Tim:** do however much revenue, increase their revenue year over year with half the people or a quarter of the people.

[00:25:19] **Carol:** Mhm.

[00:25:22] **Tim:** News articles are talking about you know, million-dollar-revenue companies that are one employee and AI

[00:25:28] **Adam:** Yeah, yeah.

[00:25:30] **Tim:** So I think in the short term and maybe long term, Job displacement is probably my biggest sa.

[00:25:38] **Adam:** M.

[00:25:40] **Adam:** Yeah.

[00:25:40] **Adam:** I, I picked four but I don't know if I could put them in order.

[00:25:43] **Carol:** Yeah, I don't know if I could either.

[00:25:43] **Adam:** It's interesting.

[00:25:45] **Ben:** Ezra Klein has.

[00:25:46] **Ben:** Has had a couple of episodes where he talks about ch.

[00:25:47] **Carol:** I love Ezra Klein.

[00:25:48] **Ben:** Job displacement.

[00:25:50] **Tim:** Mhm M.

[00:25:50] **Ben:** And one of the interesting things that he talks about is his biggest fear is almost that if there is job displacement that it doesn't happen fast enough.

[00:26:01] **Ben:** Meaning that if like all white collar workers were put out of work at the same time, we would do something about it because it would be so catastrophic that we'd be forced to act.

[00:26:07] **Adam:** Mhm,

[00:26:10] **Carol:** Right?

[00:26:12] **Ben:** But his concern is that it's going to be such a trickle that it's going to just like slowly destroy the economy and so many people are going to suffer before it reaches a critical mass, before

[00:26:24] **Ben:** Congress is forced to do something about it.

[00:26:27] **Tim:** Hey, will trickle down theory finally will have worked

[00:26:29] **Adam:** Mhm.

[00:26:29] **Carol:** Mhm.

[00:26:32] **Adam:** Disaster.

[00:26:32] **Tim:** because when Reagan promised it in the 80s it hasn't happened.

## [00:26:35] Cognitive Dependence and Human Connection

[00:26:35] **Adam:** I was thinking should we go through and like each say what our top four is to see like what's the overlap?

[00:26:36] **Ben:** Huh.

[00:26:40] **Adam:** Because I feel like it's going to be very disjointed if we just kind of go through the list and see who's has what.

[00:26:42] **Carol:** M.

[00:26:42] **Carol:** Yeah.

[00:26:44] **Adam:** So I'll go first.

[00:26:46] **Adam:** These are my top.

[00:26:46] **Carol:** Okay, uh,

[00:26:46] **Adam:** These are my four.

[00:26:48] **Adam:** We already said military use of A.I.

[00:26:50] **Adam:** uh, environmental impact.

[00:26:51] **Adam:** I'm a little bit of a hippie, so that, that resonates with me.

[00:26:52] **Ben:** Mhm,

[00:26:52] **Tim:** Mhm.

[00:26:54] **Carol:** This checks out.

[00:26:55] **Adam:** Um, yeah.

[00:26:56] **Adam:** Copyright and ethics issues.

[00:26:58] **Adam:** I guess I'm also, I like art.

[00:27:01] **Adam:** So that you know, strikes a chord with me and then negative uh, cognitive impacts.

[00:27:05] **Adam:** And for me that one's pretty selfish.

[00:27:06] **Adam:** Right.

[00:27:07] **Adam:** That's me looking in a mirror and trying to be honest with myself.

[00:27:11] **Adam:** Like I'm allowing AI to make me dumber.

[00:27:14] **Carol:** M.

[00:27:14] **Carol:** Yeah, the negative cognitive impacts the sub for that one is excessive AI use making users helpless without it.

[00:27:22] **Carol:** And I feel that one strong because I have stopped Googling and I asked, uh, Claude and I have found myself when I do Google something, I just look at the AI result at the top of the page instead of going into like articles or into like actual results.

[00:27:24] **Tim:** Mhm mhm mhm mhm mhm mhm.

[00:27:25] **Ben:** Mhm, mhm,

[00:27:40] **Carol:** And it makes me feel like my dependency on AI is way too much.

[00:27:41] **Adam:** Yeah.

[00:27:45] **Carol:** Yeah,

[00:27:45] **Adam:** So that, that's a really interesting thing because I, I completely, I do a lot, I do the same thing a lot of the time and I am similarly troubled by it.

[00:27:54] **Ben:** Mhm.

[00:27:55] **Adam:** But I don't think I was as troubled when Google was a better search engine than Yahoo and Ask Jeeves and all that.

[00:28:00] **Carol:** True.

[00:28:01] **Adam:** Right.

[00:28:01] **Adam:** And like why, if we're getting the correct answer, which uh, I think just like Google, you know you.

[00:28:04] **Carol:** M.

[00:28:08] **Adam:** You had to learn the, the right Google-fu to get a good answer out of Google originally.

[00:28:09] **Carol:** Mhm.

[00:28:12] **Adam:** You're kind of having to learn the right way to talk to and, and verify that what you get out of GPT or whatever else.

[00:28:19] **Adam:** But like at the end of the day it kind of just is a better search engine and you can tell it like cite your sources or whatever.

[00:28:24] **Adam:** Like these are the, that's the Google-fu So like should, should we be concerned with that?

[00:28:24] **Carol:** Wait.

[00:28:28] **Adam:** I don't know.

[00:28:30] **Carol:** Yeah, but I feel like when I Google something, I scroll right?

[00:28:33] **Carol:** I go, oh, let me see, does this look valid?

[00:28:33] **Adam:** Mm mhm.

[00:28:35] **Carol:** When I get an answer back, if it sounds smart enough and sounds legitimate or is convincing, then I just accept it.

[00:28:39] **Ben:** Right.

[00:28:41] **Adam:** If it confirms my biases.

[00:28:44] **Adam:** Yeah.

[00:28:45] **Carol:** And I think That is taking out some of my like, think harder rather than just accept.

[00:28:52] **Adam:** Mm.

[00:28:54] **Ben:** And this is kind of along the lines of the negative cognitive impact.

[00:28:59] **Ben:** But I feel like if I can, if I can like blur the lines between

[00:29:04] **Ben:** what's called open source disruption and negative cognitive impact, I feel like nowadays I'm trying to make more of an effort to go to people's site.

[00:29:08] **Adam:** Mhm.

[00:29:09] **Carol:** Mhm,

[00:29:15] **Ben:** Like if I see someone on LinkedIn link to an article that they wrote or something comes up that gets referenced.

[00:29:20] **Adam:** We found him.

[00:29:21] **Adam:** The one human that's still on LinkedIn.

[00:29:23] **Ben:** Okay.

[00:29:23] **Ben:** So

[00:29:25] **Ben:** that as a quick aside, apparently they deployed a button.

[00:29:25] **Tim:** Mhm mhm mhm.

[00:29:28] **Ben:** Now where you can say that this is AI slop.

[00:29:31] **Carol:** Mhm, mhm.

[00:29:31] **Ben:** I don't know what happens, but apparently that's a thing now.

[00:29:31] **Adam:** Yeah.

[00:29:34] **Ben:** but, but, but going back to the whole, like, open source negative cognitive impact, I'm trying to make an effort, I think more than I used to, to actually go to people's sources

[00:29:45] **Ben:** because I feel like they took time to write something.

[00:29:47] **Ben:** I'm trying to almost cognitively combat the idea that I'm getting lazier.

[00:29:53] **Adam:** Mm mhm,

[00:29:53] **Ben:** But then it has this weird side effect where part of what I want to do there is interact with the person.

[00:29:59] **Adam:** Mhm.

[00:30:00] **Ben:** And what I'm hoping is that I read the article and then I could leave a comment about, oh, uh, this was a great read.

[00:30:06] **Ben:** Or like, oh, yeah, you hit some really great points.

[00:30:08] **Ben:** And what I'm finding is that when I get to a page where there's no where, it's more just like a wiki style, but it's not like a place where I can have an interaction, I almost feel let down is not the right word.

[00:30:14] **Adam:** Sa.

[00:30:20] **Adam:** Mhm.

[00:30:22] **Ben:** But it's like I'm trying to make the extra step to connect with a human, and then the human on the other side has no way to let me connect other than to consume the material.

[00:30:31] **Carol:** Yeah.

[00:30:33] **Ben:** And, you know, that's not to blame any.

[00:30:34] **Tim:** Yeah.

[00:30:34] **Tim:** Because it doesn't have any personality.

[00:30:37] **Ben:** It's.

[00:30:37] **Ben:** It's more like I just.

[00:30:39] **Ben:** uh.

[00:30:40] **Ben:** I don't know, it's like I think I'm just craving a human connection and I'm trying to step outside of the AI where I can.

[00:30:44] **Adam:** Mhm.

[00:30:45] **Adam:** That's on brand.

[00:30:46] **Carol:** Mhm.

[00:30:46] **Tim:** Yep.

[00:30:48] **Ben:** And then it'd be great to leave a comment sometimes.

[00:30:52] **Ben:** And a lot of places don't have any kind of a commenting feature.

[00:30:57] **Tim:** AI bots.

[00:30:57] **Carol:** M.

[00:30:57] **Carol:** Yes.

[00:30:58] **Ben:** Yeah,

[00:30:58] **Tim:** So negative impacts is also.

[00:31:01] **Tim:** It's toward the bottom of my top four.

[00:31:04] **Adam:** Okay.

[00:31:04] **Tim:** Um, and because uh, because I think I'm there.

[00:31:08] **Adam:** Yeah, I'm already stupid.

[00:31:08] **Tim:** Um, so my number one job displacement Um, number two AI slop takeover.

[00:31:10] **Adam:** Give me.

[00:31:11] **Adam:** Well, uh, give us your top four.

[00:31:12] **Ben:** I did.

[00:31:12] **Carol:** Yeah.

[00:31:12] **Ben:** The thing.

[00:31:13] **Carol:** What are your four?

[00:31:17] **Adam:** M.

[00:31:20] **Tim:** Number three.

[00:31:22] **Tim:** Four, four.

[00:31:22] **Adam:** Wait a minute.

[00:31:22] **Adam:** You have an AI slop website of your own, sir,

[00:31:25] **Tim:** I do.

[00:31:25] **Tim:** Yeah I do.

[00:31:27] **Adam:** Your, your recipe site,

[00:31:27] **Tim:** I have several.

[00:31:28] **Ben:** Can confirm.

[00:31:28] **Tim:** But mine's high quality slop.

[00:31:30] **Tim:** So

[00:31:32] **Adam:** Gourmet slop.

[00:31:33] **Adam:** If you.

[00:31:34] **Tim:** finest brand.

[00:31:35] **Tim:** And then copyright and ethics issues.

[00:31:38] **Tim:** Uh, and then negative cognitive.

[00:31:41] **Tim:** So I'm not joking.

[00:31:42] **Tim:** So it says excessive AI making helpless.

[00:31:45] **Ben:** Sa.

[00:31:47] **Tim:** So a bug came in from one of my services that I maintained and I'm like kind of know what that is.

[00:31:47] **Carol:** M.

[00:31:47] **Carol:** Yep.

[00:31:50] **Carol:** Um,

[00:31:56] **Tim:** Later I want to stop what I was doing.

[00:31:57] **Tim:** So I just copied and pasted dropped it.

[00:32:00] **Tim:** Claude told it to say it's probably over here and I just walked away like I don't want to bother opening it up.

[00:32:02] **Carol:** sa.

[00:32:04] **Adam:** Mhm.

[00:32:05] **Ben:** Mhm.

[00:32:08] **Tim:** Um, but then that's not something I know there's an issue with something that uh, still don't have the verb for when you co co author something with Claude.

[00:32:11] **Carol:** Mhm.

[00:32:18] **Tim:** Some sort of service like in Python or Rust that I wrote with Claude, there's an issue like I have no idea where it starts

[00:32:26] **Tim:** and so I just

[00:32:29] **Tim:** trust that it's going to fix it and it does.

[00:32:31] **Tim:** But I'm like if I were out of token or something happens, I can't use AI anymore.

[00:32:38] **Tim:** I would really be in a bad place trying to fix this.

[00:32:40] **Adam:** M.

[00:32:40] **Adam:** Yeah.

[00:32:41] **Tim:** I wouldn't know where to begin.

[00:32:42] **Carol:** A big dependency.

[00:32:42] **Ben:** Yo,

[00:32:43] **Adam:** How long until my tokens refresh?

[00:32:43] **Carol:** Yeah.

[00:32:44] **Carol:** Right.

[00:32:45] **Adam:** And can I wait that long.

[00:32:45] **Tim:** Exactly.

[00:32:46] **Tim:** Exactly.

[00:32:48] **Tim:** Uh, am I getting stupider?

[00:32:49] **Tim:** No, but I'm definitely more dependent.

[00:32:51] **Adam:** And more lazy.

[00:32:51] **Carol:** Yeah.

[00:32:51] **Carol:** Um, yeah, for sure.

[00:32:52] **Adam:** Yeah.

[00:32:53] **Carol:** Talking about tokens, today, I was eating a bag of chips.

[00:32:57] **Carol:** Granted they were protein chips, like the best chips ever.

[00:32:58] **Tim:** Mhm.

[00:32:59] **Carol:** And I was out of chips and I looked at my bag and I was like, oh man, I'm out of chips.

[00:33:04] **Carol:** And my husband looks at me and he goes, what?

[00:33:07] **Carol:** And he goes, I've never heard tokens called that before.

[00:33:11] **Carol:** Apparently, apparently I say it enough to say, oh, like I'm out of tokens, I have to go use Codex for a bit.

[00:33:12] **Ben:** Mhm.

[00:33:13] **Adam:** Mhm.

[00:33:18] **Carol:** That when I said chips, he just assumed I meant tokens instead

[00:33:21] **Adam:** Right.

[00:33:22] **Adam:** Interesting.

[00:33:24] **Ben:** Sa

[00:33:24] **Carol:** So

[00:33:24] **Adam:** So Tim, yours, yours were job displacement.

[00:33:26] **Ben:** mhm.

[00:33:27] **Adam:** AI slop takeover.

[00:33:28] **Tim:** AI slop copyright ethics.

[00:33:31] **Tim:** Negative.

[00:33:32] **Adam:** Okay.

[00:33:32] **Carol:** So I.

[00:33:33] **Carol:** I'll add my four.

[00:33:34] **Carol:** Because three of mine matched him and the other security, which I talked to Ben about a few minutes ago.

[00:33:39] **Tim:** M.

[00:33:42] **Carol:** But it's definitely the copyright and the AI slop and then the negative cognitive impact.

[00:33:47] **Carol:** The AI slop is big for me.

[00:33:50] **Ben:** Mm mhm.

[00:33:50] **Carol:** And uh, I hate to say I see it at work, but I see it at work.

[00:33:54] **Adam:** Mhm.

[00:33:54] **Carol:** Like, um, we had,

[00:33:55] **Tim:** Well your ultimate boss posts them all the time.

[00:33:59] **Carol:** well, we even had some code go out that just.

[00:34:01] **Adam:** Mhm,

[00:34:01] **Tim:** Mhm mhm.

[00:34:01] **Carol:** It.

[00:34:02] **Carol:** It should have never passed the PR And I have to go, how did it pass the PR And it passed the PR because when I go back and look, it's very confident in what's been created.

[00:34:06] **Ben:** Mhm sa.

[00:34:13] **Carol:** The person that put in the PR was very descriptive and used AI to generate the description.

[00:34:19] **Carol:** So the person that approved it saw there were no findings, like hard findings, so said okay, approved it, auto merge.

[00:34:26] **Carol:** And then it kind of fell behind the scenes because it didn't hit a fail test.

[00:34:27] **Ben:** Mhm.

[00:34:31] **Carol:** It was a weird like one off case where this could happen.

[00:34:35] **Carol:** And I was like, literally code just generated not known, not understanding the end to end application.

[00:34:35] **Adam:** Mhm,

[00:34:43] **Carol:** M.

[00:34:43] **Carol:** This is easy to happen.

[00:34:44] **Carol:** Like we have many applications that touch each other and if you change how one endpoint works, everything goes down.

[00:34:52] **Carol:** Right.

[00:34:52] **Carol:** Like they show they don't work anymore.

[00:34:55] **Carol:** So those are my four.

## [00:34:58] AI Slop and the Social Contract

[00:34:58] **Tim:** On the slop one.

[00:34:59] **Tim:** So when I think of slop, I'm thinking about kind of like public

[00:34:59] **Adam:** Mhm.

[00:35:02] **Carol:** Mhm.

[00:35:03] **Adam:** Yeah.

[00:35:03] **Tim:** social media networks, things like that.

[00:35:04] **Adam:** Twitter.

[00:35:06] **Tim:** We've already seen how badly bots can mess up.

[00:35:11] **Tim:** Twitter at one point was actually a fantastic place.

[00:35:12] **Carol:** Oh yeah.

[00:35:12] **Ben:** Mhm.

[00:35:12] **Adam:** Mm.

[00:35:14] **Tim:** We all, early on we all lived on Twitter together.

[00:35:18] **Tim:** Uh, and now it's just all bots.

[00:35:22] **Adam:** It's awful.

[00:35:22] **Adam:** Yeah.

[00:35:22] **Tim:** The job hiring, they're all bots and AI is just

[00:35:27] **Tim:** making that orders of magnitude worse And I don't see a way to fix.

[00:35:33] **Ben:** Well, in one of the Cory Doctorow interviews that you alluded to, I think he introduced me personally to the phrase Claude-fishing which is a take on the term catfishing.

[00:35:34] **Carol:** Uh.

[00:35:34] **Carol:** Ah.

[00:35:44] **Carol:** Mhm.

[00:35:46] **Ben:** And for anyone who's not familiar with that, listeners, catfishing is when you pretend to be someone else online to lure people in, typically kind of in a scammy, romantic way.

[00:35:46] **Adam:** Mhm.

[00:35:57] **Ben:** And so Claude-fishing is the idea that there's this sense of betrayal when you engage with content online thinking that it's written or created by a human, and then it turns out to have been written or created by an AI and you feel like you were bamboozled and it almost doesn't matter the quality of the thing being consumed.

[00:36:04] **Tim:** Mhm mhm

[00:36:05] **Carol:** Mhm,

[00:36:15] **Adam:** Yeah.

[00:36:20] **Ben:** And, um, they can demonstrate this oftentimes in these studies where they'll show people content and not tell people what it is.

[00:36:25] **Carol:** Mhm, mhm.

[00:36:29] **Ben:** And people say, oh, yeah, I really enjoyed it.

[00:36:31] **Ben:** And then they tell people, oh, actually it was created by AI.

[00:36:34] **Ben:** Like they can do this with music or small pieces of writing, and it completely changes the way people think about the thing that they just consumed.

[00:36:35] **Adam:** Mhm.

[00:36:35] **Adam:** Yeah.

[00:36:41] **Ben:** And it's not a matter of quality.

[00:36:43] **Ben:** It's a matter of some just deep.

[00:36:46] **Tim:** m Social contract.

[00:36:47] **Ben:** Yeah.

[00:36:48] **Adam:** Yeah.

[00:36:49] **Adam:** The social contract, I think is like dead on the nose for me.

[00:36:52] **Adam:** I, I have AI do m.

[00:36:55] **Adam:** The first pass of all of my code reviews If I open up the PR and it's more than like, you know, 10, 15 lines of code, right?

[00:36:55] **Ben:** Mhm.

[00:37:01] **Adam:** If it looks complicated at all, first thing I do is drop it into Codex and say do a code review on this for me.

[00:37:05] **Tim:** Mhm mhm mhm mhm.

[00:37:07] **Adam:** But I also say do not leave any comments on the PR Give me the feedback here in our session.

[00:37:11] **Ben:** Sa.

[00:37:14] **Adam:** Because I never want

[00:37:16] **Ben:** Mhm.

[00:37:17] **Adam:** uh, like feedback to go into the, to, to another person without filtering through me first.

[00:37:23] **Adam:** Like often I would say maybe more than 50% of the time I have some comment that I'm going to leave on the, on the PR because of what the AI found during its code review.

[00:37:33] **Adam:** But I often will rephrase it.

[00:37:36] **Adam:** I will be like, oh no, you know, it found three things but two of them are dumb or not, you know, irrelevant.

[00:37:38] **Ben:** M.

[00:37:38] **Ben:** Mhm.

[00:37:40] **Carol:** Yeah,

[00:37:41] **Adam:** And, and like, you know, it's just.

[00:37:44] **Adam:** I'm glad to have that as a tool, but I would never try to inflict that on somebody else.

[00:37:49] **Adam:** And it's, and I have the exact, you know, the, the exact reaction you would expect based on, I guess this behavior when I see, you know, comments on a PR or comments on an issue and I can tell they're like, AI generated.

[00:38:01] **Adam:** I'm like, I don't even want to read this.

[00:38:03] **Adam:** It's probably great, but I don't even want to read it.

[00:38:03] **Carol:** Yeah.

[00:38:04] **Carol:** Agree.

[00:38:04] **Ben:** Right.

[00:38:05] **Carol:** I'm like, hey, I can just read it, then I'm done.

[00:38:07] **Adam:** Yeah.

[00:38:09] **Ben:** This is why.

[00:38:09] **Carol:** Mhm.

[00:38:09] **Ben:** Okay, if I small side quest here for a second.

[00:38:13] **Ben:** So I.

[00:38:15] **Ben:** I, uh, think we can all agree that when you've used AI for a bit, it says things that you key in on as being.

[00:38:22] **Ben:** Oh, uh, like this is just something the AI says all the time.

[00:38:25] **Ben:** Like for whatever reason.

[00:38:26] **Ben:** A couple of months ago, Claude Code started using the term load bearing, like, all the time.

[00:38:31] **Ben:** For me, this was a load bearing decision.

[00:38:32] **Ben:** This was a load bearing feature.

[00:38:33] **Adam:** Mhm.

[00:38:34] **Carol:** Oh my goodness.

[00:38:34] **Ben:** This was a load bearing part of the code.

[00:38:35] **Carol:** Uh huh.

[00:38:36] **Tim:** Does it use the word seam, S-E-A-M, a lot.

[00:38:39] **Carol:** It.

[00:38:40] **Tim:** It uses it all the time.

[00:38:40] **Ben:** Yes.

[00:38:41] **Tim:** With me.

[00:38:42] **Ben:** Seam's a big one

[00:38:42] **Adam:** Well, seams are important.

[00:38:44] **Adam:** That's like right out of programming books.

[00:38:46] **Adam:** Like intentionally placing seams.

[00:38:46] **Carol:** Yeah.

[00:38:49] **Carol:** Let me seam this into your unit test.

[00:38:51] **Carol:** Yeah.

[00:38:52] **Ben:** So I, uh.

[00:38:52] **Ben:** A couple of weeks ago I had gone on LinkedIn.

[00:38:55] **Ben:** Sometimes I just need to blow off some steam.

[00:38:56] **Ben:** And I'm realizing now that that's just a terrible idea.

[00:38:59] **Ben:** Uh, I went onto LinkedIn and I said something like, Claude Code loves to say that things are, worthwhile.

[00:39:03] **Tim:** Sa.

[00:39:07] **Ben:** Like, this is a decision worth noting, or like this is an idea worth drilling in on.

[00:39:07] **Tim:** Mhm.

[00:39:10] **Adam:** Mm, mhm.

[00:39:11] **Adam:** Mhm.

[00:39:12] **Ben:** Or like this is something worth uh, more clarity on.

[00:39:16] **Ben:** this is an idea worth noting.

[00:39:18] **Ben:** And I said something on LinkedIn, like, if you say, like if your writing has worth a lot, like, you're just speaking like an AI.

[00:39:23] **Carol:** Sa.

[00:39:25] **Ben:** And in my mind I'm like, I never want to sound like an AI.

[00:39:29] **Ben:** So,

[00:39:29] **Adam:** Sa.

[00:39:30] **Ben:** uh, like, I would try to avoid using phrases that feel AI-ish And like, everybody who responded was like,

[00:39:31] **Adam:** Mhm.

[00:39:35] **Tim:** M.

[00:39:35] **Tim:** Classic Ben

[00:39:37] **Ben:** everybody who responded was like, that's how I talk though.

[00:39:40] **Ben:** And I'm like, oh.

[00:39:41] **Ben:** But like, it made me think of, um, I think an early Turing test So, you know the Turing Test where you.

[00:39:47] **Tim:** Mhm.

[00:39:47] **Ben:** I think it was like there was a chat or something originally, or you asked something questions and then you had to judge whether or not the thing answering you was a human or a computer.

[00:39:47] **Carol:** Mhm.

[00:39:56] **Ben:** And apparently several people who were on the, you know, like on the other side of the wall were false positives as computers.

[00:39:56] **Adam:** Mm.

[00:40:03] **Ben:** Like someone said, oh, this person responding is a computer, but it was actually a human.

[00:40:07] **Ben:** I'm like, that's an insult to the person.

[00:40:10] **Ben:** Like, like, then you should probably change the way you talk because you don't want to be false positive as a computer anyway.

[00:40:18] **Adam:** You gotta stop saying all those em dashes

[00:40:20] **Ben:** I know.

[00:40:22] **Ben:** Anyway, I just, It's.

[00:40:23] **Ben:** It was interesting to me.

[00:40:24] **Ben:** I mean one, it's probably not an appropriate thing for me to say on LinkedIn anyway.

[00:40:28] **Ben:** I don't want to like, I'm um, I never want to yuck anyone's yum.

[00:40:30] **Ben:** M.

[00:40:30] **Ben:** Like if you talk a certain way, I don't want to be the guy who says that's not something you should say.

[00:40:35] **Ben:** I say hella all the time.

[00:40:36] **Ben:** And apparently that's not cool anymore.

[00:40:38] **Ben:** Since the 90s.

[00:40:40] **Adam:** It's hella uncool.

[00:40:40] **Tim:** Give m another 10 years, it'll be better that.

[00:40:42] **Ben:** Yeah, yeah, but

[00:40:43] **Carol:** Hey, what are your four.

[00:40:44] **Carol:** Ben?

[00:40:45] **Ben:** my four.

[00:40:46] **Ben:** I think, um, I think the job displacement, the security,

[00:40:46] **Carol:** Yeah.

[00:40:48] **Tim:** Mhm.

[00:40:51] **Carol:** Mhm.

[00:40:51] **Ben:** the AI slop Sorry, something just popped up.

[00:40:55] **Ben:** The AI slop and the negative, uh, cognitive impacts and the AI slop takeover and just to like drill down the AI slop takeover more.

[00:40:59] **Adam:** AI slop takeover specifically.

[00:41:01] **Adam:** Okay.

[00:41:05] **Ben:** And going back to this idea of the social contract,

[00:41:09] **Ben:** LinkedIn I think has become particularly terrible with the AI slop.

[00:41:12] **Adam:** This guy loves LinkedIn.

[00:41:13] **Tim:** Was it ever any good?

[00:41:13] **Ben:** But

[00:41:15] **Ben:** you know, just going back to this idea of there are things that the AI says that as, as these like wonderful pattern matching brains that we've been, you know, granted through our existence.

[00:41:31] **Adam:** I grew mine, sir.

[00:41:33] **Tim:** Mhm.

[00:41:34] **Ben:** It's like the moment I hear anybody say something in writing that even,

[00:41:34] **Tim:** My mother did.

[00:41:41] **Ben:** you know, whiffs of possible AI usage, I'm like, my uh, brain just like immediately disengages.

[00:41:49] **Adam:** Oh yeah.

[00:41:50] **Carol:** Yeah, it's uh, it's so silly, but I was trying to just draft a response to someone and it was about something we're researching, right?

[00:41:50] **Tim:** Mhm.

[00:41:53] **Ben:** Mhm.

[00:41:54] **Adam:** Mhm.

[00:41:57] **Carol:** And I was like, hey, I did as you suggested.

[00:41:59] **Carol:** Right.

[00:41:59] **Carol:** I took all these bullets that I had sitting over here.

[00:42:02] **Carol:** It's just thoughts in my brain.

[00:42:03] **Carol:** And I ran it through Claude and, and the sentence that Claude gave me was something like.

[00:42:09] **Carol:** And had Claude enhanced the pres.

[00:42:11] **Carol:** Like the presentation for you?

[00:42:13] **Carol:** And I was like, I would never say that.

[00:42:15] **Carol:** So I just deleted it.

[00:42:17] **Carol:** And I was like, had Claude pretty it up?

[00:42:20] **Tim:** Mhm.

[00:42:20] **Carol:** I'm like, because these aren't words I use.

[00:42:20] **Ben:** Mhm.

[00:42:22] **Carol:** Like, I don't want it to.

[00:42:23] **Carol:** Not like I still want it to sound like me when I'm sending something, but I also want it to sound like acceptable and professional still.

[00:42:25] **Adam:** Yep.

[00:42:31] **Carol:** So I'm like, I had Claude pretty this up for us.

[00:42:34] **Adam:** Oh that.

[00:42:34] **Adam:** I wonder if that's going to become like a personalization.

[00:42:38] **Adam:** Right, so we've got if I'm not mistaken, as generative pre training.

[00:42:43] **Adam:** Right.

[00:42:43] **Adam:** That's what the GPT and ChatGPT is.

[00:42:45] **Adam:** please listeners, correct me if I'm wrong.

[00:42:47] **Adam:** That's my, the best.

[00:42:47] **Carol:** You're the only person who took the time to learn this.

[00:42:48] **Adam:** My.

[00:42:50] **Ben:** I'm pretty sure that the T is transformer.

[00:42:51] **Adam:** Well, but then, so.

[00:42:52] **Ben:** That's all I know.

[00:42:52] **Tim:** Mhm mhm mhm mhm mhm mhm mhm mhm.

[00:42:54] **Adam:** Oh God.

[00:42:55] **Adam:** Anyway, uh, but then I know we have RL which is like sort of the step after this.

[00:42:57] **Carol:** Mhm.

[00:43:00] **Adam:** Like the.

[00:43:00] **Adam:** They.

[00:43:00] **Adam:** They train it later.

[00:43:00] **Ben:** Reinforcement learning.

[00:43:02] **Adam:** Yes.

[00:43:02] **Adam:** Reinforcement learning where that's like they, they train this particular agent to be really good at code or really good at physics or whatever.

[00:43:09] **Adam:** Um, and I'm wondering too if like we're gonna have to sort of.

[00:43:13] **Adam:** You get a model or you, you take with your subscription or whatever you like.

[00:43:17] **Carol:** Mhm mhm.

[00:43:18] **Adam:** You're having it generate like for example, to leave on PRs.

[00:43:21] **Adam:** And it's.

[00:43:21] **Adam:** This is what it generates.

[00:43:22] **Adam:** And then you go, okay, this is what you generated.

[00:43:25] **Adam:** Here's the comment that I actually left.

[00:43:27] **Adam:** And it learns your voice, like filter through that.

[00:43:29] **Ben:** Mhm.

[00:43:29] **Ben:** Oh, interesting.

[00:43:31] **Adam:** And, and I wonder if that's gonna become like a standard, you know, tool or feature of some of these things.

[00:43:37] **Adam:** That sounds incredibly unscalable.

[00:43:40] **Adam:** You know, I'm not an AI researcher, but yeah,

[00:43:44] **Ben:** M.

[00:43:44] **Ben:** I mean they have services that kind of do that from a generative voice, like, like actual, you know, uh, recording where they, they get trained on people's voices.

[00:43:44] **Adam:** it seems like the thing that I would want.

[00:43:54] **Adam:** Sure.

[00:43:57] **Adam:** Yeah.

[00:43:57] **Ben:** So uh, I feel like if you squint, it's kind of, it's kind of a similar thing.

[00:43:57] **Carol:** Mhm.

[00:43:58] **Adam:** That's just

[00:44:01] **Adam:** maybe.

[00:44:02] **Adam:** Yeah, I mean the, the, the thing about it that doesn't sound scalable to me is like you have.

[00:44:06] **Adam:** Every person would have to have a collection of the inputs and outputs.

[00:44:10] **Adam:** Right.

[00:44:10] **Adam:** These are the things that, that it initially generated and this is what I translated it to.

[00:44:11] **Ben:** Yeah, yeah,

[00:44:15] **Adam:** So.

[00:44:15] **Adam:** Yeah.

[00:44:16] **Adam:** I don't know.

[00:44:17] **Ben:** But the AI slop in general.

[00:44:19] **Ben:** Sorry, I just say I feel like it's kind not ruined lot of the common spaces, but it feels like the common spaces have become so problematic that it's almost the walled gardens that are going to become a refuge of human contact.

[00:44:25] **Adam:** Mhm.

[00:44:35] **Carol:** Well, do you think that if the US did something like the UK or the E.

[00:44:36] **Ben:** Mhm.

[00:44:40] **Carol:** Thought you sent me the.

[00:44:42] **Carol:** The EU

[00:44:44] **Carol:** to pass regulation that says like, oh, if you're talking to a chatbot and it's actually AI, you have to tell the user it is AI.

[00:44:45] **Adam:** Mhm.

[00:44:52] **Carol:** Or if this is AI generated, like it has to be labeled as AI generated.

[00:44:57] **Carol:** Like if your code's running, it has to be machine readable.

[00:45:01] **Carol:** Like, do you think if the US did something like that, it would help with some of the things that we see?

[00:45:06] **Ben:** So, okay.

[00:45:06] **Adam:** No.

[00:45:07] **Adam:** Uh, for me.

[00:45:07] **Carol:** No,

[00:45:08] **Adam:** No.

[00:45:08] **Adam:** Right.

[00:45:08] **Adam:** Like those PR things I was telling you like that, that are instant rage for me.

[00:45:12] **Adam:** Like part uh, of the, the giveaway is like at the bottom it'll say generated by Claude Code And I'm like awful not gonna read it.

[00:45:18] **Carol:** But you know, you know you hate it.

[00:45:20] **Carol:** And that to me that's okay.

[00:45:21] **Adam:** Yeah,

[00:45:21] **Carol:** It tells me to skip it.

[00:45:23] **Carol:** It tells me don't read it.

[00:45:24] **Carol:** Like, ignore it.

[00:45:25] **Adam:** but that's the thing.

[00:45:26] **Adam:** This is a.

[00:45:26] **Adam:** There, there's a work contract and that's maybe that's why it's rage inducing is like I'm expected to read it.

[00:45:32] **Adam:** Right.

[00:45:33] **Adam:** Maybe nobody.

[00:45:33] **Carol:** You have to click resolved.

[00:45:33] **Adam:** No, no effort went into generating it.

[00:45:36] **Adam:** But now a comment exists and the onus is on me to deal with that comment.

[00:45:43] **Carol:** Blow out your boss card now.

## [00:45:46] Copyright, Ethics, and Creative Communities

[00:45:46] **Tim:** I think one that all four of us picked was the ethics.

[00:45:49] **Ben:** Mhm.

[00:45:50] **Tim:** That one little kind of eyebrow mentality for me.

[00:45:53] **Carol:** Mhm mhm.

[00:45:54] **Tim:** But I think it kind of matters, right?

[00:45:56] **Tim:** So I mean these companies basically took all the world's knowledge that has been published and stole.

[00:45:57] **Adam:** Yeah.

[00:46:01] **Adam:** Stole.

[00:46:04] **Tim:** They didn't buy, you know, they stole it and now they are repackaging, selling it back to us.

[00:46:05] **Adam:** Yeah,

[00:46:10] **Tim:** No benefit to the actual authors who created it I just think that's extremely unethical.

[00:46:14] **Adam:** Yeah.

[00:46:17] **Tim:** Um, right.

[00:46:18] **Adam:** And at the same time complaining about other companies distilling based off of their outputs.

[00:46:23] **Ben:** Yeah, that's the funniest part.

[00:46:24] **Tim:** Yeah.

[00:46:25] **Tim:** So it's extremely hypocritical.

[00:46:27] **Tim:** I think it's unethical if, you know, ChatGPT was supposed to be open source.

[00:46:31] **Ben:** Mhm.

[00:46:32] **Tim:** That was the whole lawsuit, the original plan and had they done that, that have been cool.

[00:46:33] **Adam:** The original plan.

[00:46:34] **Adam:** Yeah.

[00:46:34] **Carol:** Mhm mhm.

[00:46:38] **Tim:** It's like

[00:46:39] **Tim:** publicly available knowledge, stole a few things.

[00:46:42] **Tim:** Shame on you.

[00:46:43] **Tim:** At least you're making it open to everybody.

[00:46:46] **Tim:** But now they're like, no, no, um, gonna make billions and billions of dollars and put everyone out of work.

[00:46:52] **Tim:** So the ethics of that just really sit

[00:46:52] **Ben:** Mhm.

[00:46:55] **Tim:** staking.

[00:46:55] **Adam:** Mhm,

[00:46:56] **Tim:** Are we going to get stuck in a place where creators stop putting things out there because they don't want it stolen or they can't make a living off of it because everyone's just getting it from AI?

[00:47:03] **Adam:** Mhm.

[00:47:06] **Adam:** Sa.

[00:47:09] **Tim:** Where is that?

[00:47:10] **Tim:** The progress of our culture, not our economy and not science and nothing.

[00:47:16] **Carol:** Mhm mhm.

[00:47:17] **Tim:** Where's that put our culture where people are disincentivized

[00:47:22] **Tim:** high quality work.

[00:47:24] **Ben:** Yeah, it's definitely

[00:47:26] **Ben:** problematic and it's also, it's interesting for people who exist inside of a community.

[00:47:29] **Tim:** Mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm mhm.

[00:47:34] **Ben:** I think there's a lot of conflict and I, uh, I can only speak for myself here.

[00:47:39] **Ben:** So when Cloudflare had announced, I feel like this was like a year ago, that they were going to build a feature into the Cloudflare networking where you could essentially turn off bot traffic or kind of put it behind a paywall There was, there was, there was some kind of grand idea that you were going to be able to put your site behind a paywall and then if your content could be useful to the AIs, there would be a marketplace that they could buy essentially access to your site from.

[00:47:52] **Adam:** Mhm,

[00:47:57] **Carol:** Mhm mhm.

[00:48:08] **Adam:** Mhm.

[00:48:09] **Ben:** And

[00:48:10] **Ben:** uh, as someone, I will loosely call myself a content creator, not in like I think the modern notion, but just kind of a general notion.

[00:48:18] **Adam:** Oh Ben, you're an influencer.

[00:48:21] **Ben:** I, I thought about it a little bit, just out of curiosity, as like a thought experiment and I felt extremely conflicted because on the one hand there's the ethics of it all and I feel like I don't want to support the idea that people can just scrape content.

[00:48:30] **Adam:** Mhm,

[00:48:39] **Carol:** Mhm mhm.

[00:48:39] **Ben:** But then on the other hand I see myself as belonging to a community and hopefully the content that I create is helpful to the community.

[00:48:46] **Adam:** Mhm.

[00:48:48] **Ben:** And the reality is a lot of the people in that community are using agentic AI.

[00:48:56] **Ben:** And if I block access to my content, and I don't mean this in like a boastful way, but like if I block access to my content, then I can't participate in the kind of cultural conversation around what this type of code should look like.

[00:49:11] **Ben:** And I honestly like felt very conflicted about that.

[00:49:16] **Ben:** Um, because it's not for me, it's not just about the content generation, it's about the community around it.

[00:49:20] **Carol:** Mhm mhm.

[00:49:22] **Adam:** Yeah.

[00:49:22] **Ben:** And I have to imagine a lot of people will feel that kind of conflict.

[00:49:27] **Adam:** There's a hundred different angles on this.

[00:49:28] **Adam:** Like another one kind of going through my mind now is Reddit, right.

[00:49:32] **Adam:** I used to be a fairly heavy Reddit user.

[00:49:34] **Adam:** I have paid for one.

[00:49:36] **Adam:** Not any subscriptions but ah, like one time purchased various different Reddit apps because they're the official Reddit app.

[00:49:43] **Ben:** They had that whole API thing right.

[00:49:45] **Adam:** Yeah.

[00:49:45] **Adam:** So the, the official Reddit app sucks.

[00:49:45] **Ben:** API gate.

[00:49:47] **Adam:** And so there were all these like third party uh, apps that you could, some of them were free, some of them you had to pay whatever.

[00:49:54] **Adam:** and it was great.

[00:49:54] **Adam:** And, and I was a fairly heavy Reddit user and I am no longer a fairly heavy Reddit user because they shut down their API because of.

[00:50:01] **Adam:** I, I don't necessarily fault Reddit for doing this.

[00:50:05] **Adam:** Right.

[00:50:05] **Adam:** They shut down their API because they knew that everything was being scraped out, to, to train LLMs and that,

[00:50:15] **Adam:** that would be a whole show topic on its own really.

[00:50:17] **Carol:** Mhm mhm.

[00:50:17] **Ben:** Mhm.

[00:50:17] **Adam:** but then, so like it made my experience worse.

[00:50:22] **Adam:** I don't think they were entirely successful at blocking LLMs.

[00:50:24] **Adam:** Right.

[00:50:25] **Adam:** You can still go to the HTML pages and scrape the content and and the Reddit app still sucks.

[00:50:31] **Adam:** But like

[00:50:33] **Adam:** just, it's like lose, lose, lose all around.

[00:50:36] **Adam:** And that, that.

[00:50:36] **Adam:** And uh, just so that we can have AI.

[00:50:39] **Adam:** Which whatever.

[00:50:41] **Adam:** Did

[00:50:41] **Ben:** So when I hear people talk about

[00:50:44] **Ben:** social media and young kids, and not to make that a conversation, but just one of the phrases that I've heard bandied about in that area of the world is this idea of it being a collective action problem that when they ask a lot of kids, hey, do you enjoy being on Instagram?

[00:50:57] **Carol:** Mhm.

[00:51:01] **Ben:** And a lot of kids say no, I actually don't like it and it makes me very unhappy.

[00:51:06] **Ben:** But the problem is all of my friends are on Instagram and if I'm the one person not on Instagram that I'm not part of the friend friend group.

[00:51:07] **Carol:** Mhm m.

[00:51:13] **Ben:** And I feel like that's, that that's probably an applicable

[00:51:19] **Ben:** concept where it's like you don't necessarily want to do it, but if you don't do it, you're not in the conversation.

[00:51:26] **Adam:** Yeah, the network effects.

[00:51:27] **Ben:** And yeah, the network effects.

[00:51:31] **Adam:** All right, why don't we wrap it there?

[00:51:31] **Ben:** Uh.

## [00:51:32] Thanks For Listening!

## [00:51:32] Patreon

[00:51:32] **Adam:** We've said quite a bit on this, uh, and amazingly we only got through one of the questions on the survey.

[00:51:37] **Ben:** Mhm.

[00:51:37] **Adam:** Um, but let's set it aside.

[00:51:39] **Adam:** This episode of Working Code is brought to you by whatever ChatGPT says sponsored it.

[00:51:44] **Adam:** I don't know.

[00:51:44] **Ben:** Ha.

[00:51:46] **Adam:** And listeners like you.

[00:51:47] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:51:49] **Carol:** Mhm with mhm.

[00:51:53] **Ben:** Mhm.

[00:51:53] **Adam:** Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them.

[00:51:58] **Adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

[00:52:01] **Adam:** You guys rock.

[00:52:02] **Adam:** We're gonna go record the after show which at this point you probably know, right?

[00:52:05] **Adam:** You give us some money through Patreon, we give you a special feed, has the.

[00:52:07] **Ben:** Sa.

[00:52:10] **Adam:** The normal podcast has extra content called the after show, which is because it comes after the show.

[00:52:14] **Ben:** Mhm.

[00:52:16] **Adam:** We're just going to keep talking into the mics.

[00:52:19] **Adam:** we're going to talk about briefly about, Ted Lasso season four is about to start.

[00:52:22] **Carol:** Oh my God.

[00:52:22] **Adam:** So as we're, as we're recording this, this is August 4th.

[00:52:27] **Adam:** and so tomorrow is the first episode.

[00:52:29] **Adam:** It's gonna be tough.

[00:52:30] **Adam:** I think I'm just gonna kind of hold out till we're most of the way through the season so we can binge it all in one go.

[00:52:33] **Ben:** Mhm.

[00:52:34] **Adam:** I don't know.

[00:52:35] **Adam:** Anyway, that's after show.

[00:52:37] **Adam:** Uh, we'll get into it there.

[00:52:38] **Adam:** But if you want the after show and other similar awesome perks, you can go to patreon.com/workingcodepod and support us there.

[00:52:40] **Carol:** Sa.

[00:52:45] **Adam:** We'd really love it.

[00:52:47] **Adam:** That's going to do it for us this week.

[00:52:48] **Adam:** We'll catch you next week.

[00:52:49] **Adam:** And until then, you're on mute, Tim, which is perfect.

[00:52:49] **Carol:** Mhm.

[00:52:56] **Tim:** It almost feels unethical how much this is true.

[00:52:59] **Tim:** Your heart matters.

[00:53:20] **Carol:** Mhm.

## [00:53:21] Aftershow

[00:53:21] **Adam:** And

[00:53:22] **Adam:** the after show,

[00:53:24] **Ben:** It's the after show

[00:53:25] **Tim:** You.

[00:53:27] **Ben:** time.

[00:53:28] **Adam:** This time with Ben.

[00:53:32] **Ben:** Half-awake Ben half puppy.

[00:53:34] **Adam:** Yeah, yeah.

[00:53:35] **Adam:** So

[00:53:35] **Ben:** Sleep-deprived Ben

[00:53:35] **Carol:** Or Ben.

[00:53:36] **Carol:** Or Ben.

[00:53:36] **Adam:** on, uh, the.

[00:53:37] **Adam:** Yeah, yeah.

[00:53:37] **Adam:** On the subject of puppies, actually, is Rendez okay?

[00:53:40] **Carol:** Yeah.

[00:53:41] **Carol:** She's doing so much better.

[00:53:42] **Carol:** However, after being tied to us for so long, it feels like all the training we did kind of reverted and now she's back to super hyper, jumping around, not obeying commands.

[00:53:49] **Ben:** Mhm.

[00:53:49] **Adam:** Oh no.

[00:53:50] **Tim:** Sa mhm.

[00:53:54] **Carol:** The only time I can get her to listen is if I have a treat in my hand.

[00:53:57] **Carol:** Otherwise we're like, stop biting your sister.

[00:53:59] **Carol:** Stop biting your sister.

[00:54:00] **Carol:** Stop biting your sister.

[00:54:02] **Carol:** And she's like, uh, oh, I don't even know my name, you know, so it's going to take a little bit to get her back on track, I think.

[00:54:02] **Ben:** Uh.

[00:54:05] **Adam:** Mhm.

[00:54:05] **Ben:** Oh man,

[00:54:09] **Carol:** But health-wise she's good.

[00:54:11] **Carol:** She's physically okay.

[00:54:13] **Carol:** And yeah, yeah,

[00:54:14] **Adam:** That's good.

[00:54:16] **Ben:** Glad to hear that.

[00:54:16] **Adam:** Uh, what's everybody's Ted Lasso Ted Lasso watch plan?

[00:54:20] **Carol:** I'm going to start tomorrow yeah,

[00:54:20] **Adam:** Uh, or you're.

[00:54:22] **Adam:** You're just gonna watch it every week?

[00:54:23] **Adam:** Oh, like a freaking savage.

[00:54:23] **Carol:** yeah, yeah.

[00:54:24] **Carol:** So I can't help it.

[00:54:26] **Carol:** My husband is the one driving the TV plans these days.

[00:54:27] **Adam:** I know.

[00:54:31] **Adam:** You guys got to get on the same page.

[00:54:33] **Adam:** That's like marriage counseling material.

[00:54:35] **Tim:** All right.

[00:54:35] **Ben:** I haven't even seen the trailer yet.

[00:54:36] **Ben:** I'm, um, going in completely nude.

[00:54:37] **Carol:** Oh my God.

[00:54:37] **Adam:** Oh, I,

[00:54:38] **Carol:** Adam shared it.

[00:54:39] **Adam:** I literally posted the link in our Discord last week.

[00:54:41] **Ben:** I know.

[00:54:41] **Ben:** I didn't want to watch it.

[00:54:41] **Tim:** Sa.

[00:54:42] **Ben:** I kind of like want to go in blind.

[00:54:43] **Carol:** Uh, yes, there is.

[00:54:43] **Adam:** It's.

[00:54:44] **Adam:** It there's no spoilers, really.

[00:54:45] **Adam:** It's just, it's.

[00:54:47] **Carol:** Steve was like.

[00:54:48] **Carol:** Oh.

[00:54:49] **Carol:** So don't.

[00:54:50] **Carol:** Don't watch if you don't want a spoiler.

[00:54:52] **Ben:** I'll tell you, we did go back and watch the, uh, Millers, which is a Jason Sudeikis movie from like 2013, I think.

[00:54:52] **Adam:** I don't think.

[00:54:56] **Carol:** The Millers

[00:55:01] **Ben:** And I.

[00:55:02] **Ben:** He's just a very enjoyable person.

[00:55:04] **Carol:** Mhm.

[00:55:04] **Ben:** His timing on, um, comedy is, is just really good.

[00:55:04] **Adam:** He is.

[00:55:10] **Ben:** I find him.

[00:55:10] **Adam:** We're the Millers Yeah.

[00:55:10] **Tim:** Mhm.

[00:55:12] **Ben:** Yeah, We're the Millers

[00:55:13] **Tim:** I loved it when he was on Saturday Night Live.

[00:55:15] **Ben:** Yeah.

[00:55:16] **Ben:** Yeah, he's really solid.

[00:55:18] **Adam:** Yeah, he's just.

[00:55:18] **Ben:** I, uh, find.

[00:55:19] **Ben:** I find him enjoyable in everything.

[00:55:19] **Adam:** Nice guy.

[00:55:21] **Tim:** speaking of pop culture.

[00:55:22] **Tim:** So we went and saw Spider, the new Spider-Man movie Saturday.

[00:55:25] **Adam:** Yeah, I heard it's really good.

[00:55:26] **Tim:** And I have to say it is the best Spider-Man movie of them all.

[00:55:30] **Carol:** Really?

[00:55:31] **Tim:** Yeah.

[00:55:31] **Tim:** Ah, the pacing is really good.

[00:55:31] **Ben:** That's pretty, it's pretty good.

[00:55:34] **Carol:** Okay.

[00:55:34] **Tim:** It has every.

[00:55:35] **Tim:** It's like, is extremely emotional.

[00:55:37] **Tim:** Like some really difficult emotional bits there you don't normally get from a, Spider-Man movie.

[00:55:43] **Tim:** And the action was pretty good.

[00:55:45] **Tim:** But I mean, and there was just one reveal that the whole, the whole, theater just went,

[00:55:51] **Tim:** ah.

[00:55:51] **Adam:** Wow.

[00:55:51] **Tim:** Because we did not see that coming.

[00:55:53] **Tim:** So it's, it's, it's good if you're.

[00:55:54] **Adam:** There's Nazis in it.

[00:55:56] **Tim:** No, there's actually,

[00:55:56] **Carol:** Mhm.

[00:55:58] **Ben:** Why did it have to be Nazis?

[00:56:01] **Tim:** Uh.

[00:56:01] **Tim:** Yeah, definitely.

[00:56:03] **Tim:** If you're inclined to watch those kind of movies, go see it.

[00:56:03] **Ben:** Mhm,

[00:56:05] **Carol:** Sa.

[00:56:05] **Tim:** If you're not inclined, at least wait till it comes out, you know, on streaming and watch it.

[00:56:10] **Adam:** On home VHS

[00:56:11] **Tim:** Yes,

[00:56:12] **Adam:** you can go get at your local Blockbuster

[00:56:14] **Tim:** exactly.

[00:56:15] **Tim:** Oh, sorry, you just triggered something.

[00:56:18] **Tim:** So.

[00:56:19] **Tim:** So the, Cory Doctorow was making the point on NPR is like.

[00:56:22] **Tim:** Or was it.

[00:56:23] **Tim:** That was Jon Stewart The last privacy law that the United States passed

[00:56:30] **Tim:** was about sharing people's Blockbuster video rental titles.

[00:56:36] **Carol:** What?

[00:56:36] **Adam:** That's hilarious.

[00:56:36] **Ben:** Mhm,

[00:56:37] **Tim:** That's how long it's been,

[00:56:38] **Adam:** Like renting it and letting your friend watch it too.

[00:56:40] **Tim:** right?

[00:56:40] **Tim:** No, no.

[00:56:41] **Tim:** So like there was a law that you couldn't go into.

[00:56:44] **Tim:** Like the people could.

[00:56:46] **Adam:** Oh,

[00:56:46] **Carol:** I couldn't find out what you watch.

[00:56:46] **Tim:** You couldn't sit.

[00:56:48] **Tim:** Right.

[00:56:48] **Tim:** So Blockbuster or these other home.

[00:56:48] **Carol:** Yeah,

[00:56:50] **Tim:** They couldn't sell the list.

[00:56:51] **Tim:** Here's all the dirty movies Tim watches.

[00:56:53] **Tim:** Right.

[00:56:53] **Tim:** So you can market to him.

[00:56:53] **Adam:** Yeah.

[00:56:54] **Tim:** M.

[00:56:54] **Ben:** mhm.

[00:56:55] **Tim:** So that was, that was made illegal.

[00:56:57] **Tim:** But that's the last time any privacy law has ever been passed in the U.S.

[00:57:00] **Adam:** Wow.

[00:57:01] **Tim:** that's how old it is.

[00:57:02] **Tim:** It's older than VHS.

[00:57:03] **Adam:** Do you think that applies to streaming?

[00:57:05] **Adam:** I mean, data brokers are going to get it through other means now anyway.

[00:57:07] **Tim:** Yeah.

[00:57:08] **Tim:** No it doesn't.

[00:57:08] **Adam:** But.

[00:57:09] **Carol:** Yeah.

[00:57:10] **Tim:** Because it was specifically about the list of rentals.

[00:57:13] **Tim:** Um, you need to go pee

[00:57:13] **Ben:** Crazy.

[00:57:15] **Ben:** Oh, I miss Blockbuster

[00:57:17] **Adam:** I got an old man yells at biology thing if you want.

[00:57:20] **Carol:** Okay.

[00:57:20] **Ben:** Do it.

[00:57:20] **Carol:** Uh, yeah, yeah,

[00:57:21] **Ben:** Do it, old man.

[00:57:23] **Adam:** No.

[00:57:23] **Adam:** Do you guys know what a stye is?

[00:57:25] **Adam:** Like the.

[00:57:25] **Carol:** yeah.

[00:57:26] **Adam:** You pronounce it like pigsty right?

[00:57:26] **Tim:** I On your I.

[00:57:27] **Adam:** Yeah.

[00:57:28] **Adam:** Yeah.

[00:57:28] **Adam:** In your eye.

[00:57:29] **Adam:** And so I get.

[00:57:30] **Adam:** I'm at now, I guess of the age where I get eye styes S-T-Y-E

[00:57:34] **Carol:** That happens at, uh, an age.

[00:57:36] **Tim:** Mhm.

[00:57:37] **Adam:** Apparently in this household.

[00:57:38] **Adam:** Yeah, my wife started getting them about a year ago and now, uh, and she's a year older than me and then, now I'm starting to get him.

[00:57:45] **Adam:** So basically what it is is it's just like a clogged, uh, like oil duct in the skin along the edge of your eyelid.

[00:57:52] **Adam:** Like I'm talking like right up on the edge.

[00:57:52] **Ben:** Mhm.

[00:57:55] **Adam:** Like where you put eyeliner.

[00:57:56] **Adam:** Right, like right up on.

[00:57:56] **Carol:** Mhm.

[00:57:57] **Adam:** At the edge of your.

[00:57:58] **Adam:** I.

[00:57:59] **Carol:** So bad.

[00:57:59] **Adam:** Uh, yeah.

[00:58:01] **Adam:** Ah.

[00:58:01] **Adam:** And

[00:58:01] **Ben:** Can you pop it?

[00:58:02] **Ben:** Is it like a pimple?

[00:58:04] **Adam:** it's recommended that you don't.

[00:58:05] **Adam:** I imagine that means that you can.

[00:58:05] **Tim:** Right.

[00:58:06] **Tim:** That's.

[00:58:06] **Tim:** That's painful.

[00:58:07] **Tim:** Yeah, I popped one.

[00:58:08] **Adam:** Um.

[00:58:08] **Adam:** So

[00:58:09] **Tim:** It's not fun.

[00:58:10] **Carol:** Mhm.

[00:58:11] **Adam:** I mean, I.

[00:58:11] **Adam:** Listen, I have never tried that.

[00:58:13] **Adam:** I have popped pimples on places that I shouldn't mention here on the podcast.

[00:58:17] **Adam:** Uh, they, uh, don't pay enough for that.

[00:58:18] **Carol:** And it's the after show.

[00:58:19] **Ben:** I love a good pimple.

[00:58:20] **Ben:** Pop.

[00:58:22] **Adam:** Um, and, uh,

[00:58:24] **Tim:** Show it on your OF.

[00:58:25] **Ben:** Sa.

[00:58:27] **Adam:** and.

[00:58:27] **Adam:** And in some really painful places too, I'll say that.

[00:58:30] **Ben:** Mhm.

[00:58:30] **Adam:** Um, anyway, no.

[00:58:30] **Tim:** Hmm.

[00:58:31] **Adam:** So what they do or what my doctor told me to do, she actually, she told my wife a year ago and my wife gave me this advice is like baby shampoo.

[00:58:39] **Adam:** They're like no more tears kind and literally wash your eyes with it.

[00:58:42] **Adam:** Not with your eyes open, but like wash your, like you're.

[00:58:45] **Adam:** You're literally washing all of your eye skin.

[00:58:47] **Carol:** Yeah,

[00:58:47] **Adam:** Um, which is.

[00:58:49] **Adam:** Was bananas to me when I first heard.

[00:58:51] **Adam:** Like, you know, of course you hear wash your eyes and your first thought goes to, you're washing your eyeballs.

[00:58:55] **Ben:** Yeah.

[00:58:56] **Adam:** No, you're washing your eyelids.

[00:58:56] **Ben:** Yeah, for sure.

[00:58:56] **Tim:** Mhm.

[00:58:58] **Adam:** But it's like.

[00:58:59] **Adam:** And you can't help but get a little in your eye.

[00:59:01] **Adam:** So that's why they say you use the like the non stinging, no more tears type stuff.

[00:59:04] **Carol:** Right.

[00:59:06] **Adam:** but yeah, so now that's a part of my shower routine.

[00:59:08] **Adam:** Every day, actually.

[00:59:09] **Carol:** Oh, so you do it all the time, not just when you have one.

[00:59:11] **Adam:** Yes, every day.

[00:59:12] **Adam:** Now, because I skipped a day, uh, and now I've got one coming in, so.

[00:59:15] **Ben:** You fool

[00:59:18] **Ben:** human bodies, man.

[00:59:18] **Tim:** Yeah.

[00:59:18] **Tim:** I'm the kind of person who cannot leave if I feel like a bump on my.

[00:59:22] **Tim:** I have to scratch it until it's smooth again.

[00:59:23] **Carol:** I pick at it.

[00:59:23] **Adam:** Mhm.

[00:59:24] **Tim:** And now it's like all bloody.

[00:59:24] **Carol:** Mhm.

[00:59:27] **Adam:** Mhm.

[00:59:28] **Tim:** So yeah, I had a stye I've only had like two in my life, but I remember one.

[00:59:28] **Ben:** Mhm.

[00:59:31] **Tim:** I just sat there and dug on it.

[00:59:33] **Tim:** Dug on it.

[00:59:33] **Tim:** Dug on it and popped it.

[00:59:34] **Adam:** Oh,

[00:59:35] **Tim:** It felt so much better.

[00:59:36] **Tim:** But then my, my whole eye was just the best you could.

[00:59:39] **Carol:** Yeah.

[00:59:39] **Adam:** Yeah.

[00:59:40] **Tim:** People are like, what did you do with a stye You can't really see it too bad.

[00:59:43] **Carol:** Um.

[00:59:44] **Adam:** Mm,

[00:59:44] **Tim:** But.

[00:59:44] **Tim:** Yeah, but I had a huge scab on my eyelid that looked terrible.

[00:59:48] **Ben:** Oh,

[00:59:48] **Adam:** Yeah.

[00:59:48] **Tim:** Um, I don't recommend.

[00:59:49] **Tim:** It's Mhm.

[00:59:50] **Adam:** No, uh, maybe this is TMI I was a pimple popper, right?

[00:59:55] **Carol:** Mhm.

[00:59:55] **Adam:** I, I, like, I couldn't.

[00:59:56] **Adam:** Like you're saying.

[00:59:56] **Adam:** I just couldn't leave it alone.

[00:59:57] **Ben:** I was.

[00:59:57] **Ben:** I am.

[00:59:58] **Ben:** Huh.

[00:59:58] **Adam:** It's like a compulsion.

[00:59:58] **Carol:** Yeah.

[00:59:59] **Carol:** I can't leave stuff alone.

[01:00:00] **Adam:** Uh, and, and so I'm just really lucky that I was not the type person to get the bad acne scarring because my face would just look like the surface of the moon otherwise.

[01:00:03] **Tim:** M.

[01:00:04] **Tim:** Scarring.

[01:00:04] **Carol:** Mhm.

[01:00:04] **Tim:** Yeah.

[01:00:06] **Carol:** Yeah.

[01:00:07] **Adam:** It.

[01:00:08] **Tim:** That's crazy.

[01:00:09] **Carol:** Very Ben.

[01:00:09] **Ben:** There's a.

[01:00:11] **Ben:** Sorry.

[01:00:12] **Ben:** I just like, like 20 years ago I had an eye that was so itchy.

[01:00:16] **Ben:** And I'm walking around.

[01:00:17] **Ben:** I was walking around in a mall one time and I'm just itching, itching and itching and itching.

[01:00:21] **Ben:** Like for like felt like two hours I was itching.

[01:00:24] **Ben:** And finally I went to a bathroom to see, uh, if there was something in it.

[01:00:27] **Adam:** Mhm.

[01:00:27] **Ben:** And by the time I got there, the whites of my eye had had like swollen up and it almost like started to curve around the front of my iris.

[01:00:33] **Tim:** Mhm.

[01:00:33] **Adam:** Wow.

[01:00:36] **Carol:** Oh my gosh.

[01:00:37] **Ben:** It was really disturbing.

[01:00:39] **Ben:** It was like the most disturbing thing I've ever seen on me.

[01:00:41] **Carol:** Oh,

[01:00:46] **Tim:** Oh

[01:00:46] **Carol:** The Odyssey Huh

[01:00:49] **Ben:** Oh.

[01:00:49] **Tim:** yeah.

[01:00:49] **Ben:** Um, so I like to think of myself as a fan of pop culture.

[01:00:49] **Adam:** Wait, are we gonna leave biology behind that easily?

[01:00:49] **Carol:** huh.

[01:00:50] **Carol:** Uh-huh.

[01:00:50] **Tim:** Thank you.

[01:00:52] **Carol:** Huh.

[01:00:52] **Tim:** Yes, please.

[01:00:52] **Carol:** Uh-huh.

[01:00:53] **Carol:** Yeah.

[01:00:53] **Adam:** Okay, fine.

[01:00:54] **Adam:** We won't talk about tonsil stones.

[01:00:57] **Tim:** Oh.

[01:00:57] **Adam:** It.

[01:00:59] **Ben:** And I think, uh, my bar is usually pretty low.

[01:01:00] **Tim:** Mhm.

[01:01:03] **Ben:** Like, I will muscle through a movie.

[01:01:05] **Ben:** I will watch a movie over like six separate sittings if it's terrible.

[01:01:06] **Carol:** Mhm.

[01:01:10] **Ben:** But I just like, I want to know how it ends.

[01:01:11] **Adam:** Mhm.

[01:01:13] **Ben:** And uh, I feel like I'm.

[01:01:15] **Ben:** I can't watch anything, but I'll watch most things and, and

[01:01:21] **Tim:** Mhm.

[01:01:21] **Ben:** uh, sometimes my preference is just so far off of what I think the general opinion is.

[01:01:22] **Adam:** It's.

[01:01:29] **Ben:** And so I went to see The Odyssey a couple of weekends ago and it's getting rave reviews.

[01:01:34] **Ben:** Everyone who I have talked to has, uh, has at the lowest bar, liked it, if not raved about it.

[01:01:40] **Carol:** Mhm.

[01:01:43] **Ben:** And I was like bored out of my mind.

[01:01:46] **Tim:** Mhm.

[01:01:47] **Ben:** Like literally from the first moment

[01:01:49] **Adam:** Oh, no.

[01:01:50] **Ben:** I was bored and then it lasted three hours.

[01:01:53] **Adam:** Oh,

[01:01:53] **Ben:** And I, I like, I love Christopher Nolan's movies.

[01:01:53] **Carol:** M.

[01:01:53] **Carol:** It's so long.

[01:01:58] **Ben:** Uh, the Batman, the Bane movie is like one of my all time favorite Batman movies.

[01:02:03] **Ben:** I.

[01:02:03] **Ben:** He did, um.

[01:02:04] **Ben:** What was the time?

[01:02:04] **Ben:** One Inception

[01:02:06] **Adam:** Oh.

[01:02:06] **Tim:** M.

[01:02:06] **Tim:** Most.

[01:02:06] **Tim:** Most of them.

[01:02:06] **Adam:** Interstellar.

[01:02:07] **Ben:** Oh, Interstellar Inception.

[01:02:08] **Tim:** Almost all of them.

[01:02:10] **Ben:** I, uh, liked a lot of, uh.

[01:02:11] **Carol:** Mhm mhm.

[01:02:11] **Adam:** Yeah.

[01:02:12] **Ben:** I liked Dunkirk.

[01:02:13] **Ben:** I don't think I liked it as much as a lot of people liked it, but, like, he's a really.

[01:02:16] **Tim:** Tenet Did you like Tenet

[01:02:18] **Ben:** I like Tenet I think I had to watch a YouTube video of, like, what did that mean?

[01:02:23] **Tim:** Same.

[01:02:24] **Ben:** Because I didn't quite understand it.

[01:02:24] **Tim:** Yeah.

[01:02:25] **Adam:** You and everybody else who saw.

[01:02:27] **Ben:** And for whatever reason, I like nothing in this movie connected with me at all.

[01:02:33] **Ben:** I'm not here to yuck anyone's yum.

[01:02:35] **Ben:** Obviously, we all have our own preference.

[01:02:38] **Ben:** I just like nothing about it was compelling.

[01:02:41] **Ben:** And here's the worst part to me is from everything that I've heard in the news and on various podcasts, like, all the people who are hating on it are, like, super right wing.

[01:02:43] **Tim:** Mhm, mhm mhm.

[01:02:51] **Ben:** Like, oh, a black person was in this movie.

[01:02:52] **Carol:** Oh my goodness.

[01:02:53] **Ben:** A trans person was in this movie is awful.

[01:02:54] **Carol:** Yeah,

[01:02:55] **Ben:** And I'm like, I don't want to get lumped in with those people.

[01:02:57] **Carol:** right?

[01:02:57] **Adam:** Mhm.

[01:02:58] **Ben:** But it was.

[01:02:58] **Ben:** It was just not.

[01:02:59] **Carol:** Mhm.

[01:02:59] **Carol:** Not your thing.

[01:03:01] **Ben:** I think I have, for whatever reason, an aversion to any movie where I feel like maybe religiosity is carrying too much of the.

[01:03:08] **Carol:** Mhm.

[01:03:12] **Ben:** Of the movie.

[01:03:14] **Ben:** Um, where, like.

[01:03:15] **Ben:** Like, I'm not saying that I don't like movies that have religious aspects.

[01:03:19] **Ben:** I feel like there are movies where the religiosity feels like the point.

[01:03:24] **Adam:** Mhm.

[01:03:24] **Ben:** And to me, that just, like, that doesn't connect enough with me for that to carry it.

[01:03:28] **Adam:** I felt the same way about The Passion of the Christ

[01:03:30] **Ben:** Oh, my God.

[01:03:30] **Ben:** That's exactly what I was about to say.

[01:03:32] **Ben:** Oh, my God.

[01:03:33] **Ben:** I.

[01:03:33] **Ben:** So I went to see The Passion of the Christ

[01:03:34] **Tim:** Well, it was sort of the point of that.

[01:03:37] **Ben:** Well, okay, no, no, I went.

[01:03:37] **Adam:** I was making a joke.

[01:03:40] **Ben:** So, uh, I went to The Passion of the Christ by myself in New York City because I loved Braveheart so much that, like, I will, Like, I have gone to see, like, every other movie that Mel Gibson has ever made, despite him probably being kind of a terrible person.

[01:03:47] **Tim:** Sa.

[01:03:48] **Carol:** Mhm

[01:03:50] **Adam:** It.

[01:03:55] **Ben:** Um, and The Passion of the Christ was the same exact thing.

[01:03:57] **Carol:** sa.

[01:03:57] **Ben:** Like, from moment one, I was bored out of my mind, and I thought it was awful.

[01:04:02] **Ben:** And then I went to tell someone that I saw that, that I saw it, and before I could tell them how awful it was, they were like, oh, yeah, I loved it.

[01:04:08] **Carol:** Mhm.

[01:04:10] **Ben:** I saw it three times already in the theater.

[01:04:12] **Adam:** Oh my God.

[01:04:12] **Ben:** I'm like, whoa, all right, well, I'm not about to have this conversation.

[01:04:17] **Ben:** And I felt okay, not, uh, to hate on a whole bunch of other things, but, like, I also saw.

[01:04:20] **Adam:** Mhm, mhm,

[01:04:20] **Tim:** But hold.

[01:04:21] **Tim:** So I'm kind of this swerve that we took.

[01:04:21] **Ben:** Yeah, go ahead.

[01:04:23] **Ben:** Yeah.

[01:04:23] **Tim:** Did you feel The Odyssey was religious?

[01:04:26] **Ben:** They said there's a phrase that they use, Zeus's law, which is kind of like a.

[01:04:32] **Ben:** Kind of like, do unto others as you would have others do unto you.

[01:04:35] **Ben:** But they used it so many times in the movie it was like,

[01:04:35] **Tim:** Mhm.

[01:04:39] **Tim:** That's funny.

[01:04:40] **Carol:** Okay.

[01:04:40] **Carol:** They did overuse that one.

[01:04:41] **Ben:** oh my God, it was like, it was like, stop trying to make fetch happen.

[01:04:43] **Carol:** Yeah.

[01:04:46] **Carol:** Um.

[01:04:47] **Tim:** Because it's.

[01:04:47] **Tim:** It because I, I haven't seen it.

[01:04:49] **Carol:** Mhm mhm,

[01:04:49] **Tim:** Um, but I did read an article today that they were asking Nolan if he felt that he

[01:04:56] **Tim:** Christianized the movie.

[01:04:57] **Tim:** And he denied it and said it wasn't the intention.

[01:05:00] **Tim:** But you know, things, you know, biases slip in and I think any kind of reference, I think it's probably what you're talking about, the Zeus's law.

[01:05:11] **Tim:** If you look at ancient history, most stories were about hospitality

[01:05:15] **Ben:** Mhm.

[01:05:16] **Tim:** and the importance of hospitality.

[01:05:18] **Tim:** Because back then you didn't have a Motel 8 or a place you could, you know, there was no inns If you're traveling, you were relying on the hospitality of people you didn't know,

[01:05:22] **Adam:** Mhm,

[01:05:22] **Ben:** Oh, that's interesting.

[01:05:26] **Ben:** The kindness of strangers.

[01:05:27] **Tim:** kindness of strangers.

[01:05:29] **Tim:** Um, and so it was to

[01:05:30] **Carol:** Mhm, mhm,

[01:05:32] **Tim:** treat a traveler or a guest unhospitably.

[01:05:36] **Tim:** It was like an offense against God.

[01:05:39] **Tim:** And that was extremely important.

[01:05:40] **Tim:** I mean, Homer did make that a big motif in his.

[01:05:44] **Tim:** So I guess that was his way of portraying.

[01:05:45] **Tim:** I haven't, like I said, I haven't seen it.

[01:05:46] **Tim:** Maybe that's what he was trying to portray and it came off a little too, uh, religious, but.

[01:05:51] **Ben:** Yeah.

[01:05:51] **Ben:** And again, like, my intention here is not to poo poo religiosity that has that.

[01:05:51] **Tim:** Yeah.

[01:05:56] **Ben:** That's not this take that I have at all.

[01:05:57] **Tim:** Right.

[01:05:58] **Adam:** Mhm.

[01:05:58] **Ben:** I.

[01:05:59] **Ben:** They're just like, look, there's a lot of movies that I have seen are straight up terrible because they have something in them that connects with me.

[01:06:05] **Tim:** Mhm.

[01:06:06] **Ben:** And like, that's enough for that movie to matter to me.

[01:06:09] **Ben:** Um, and like, even I saw not to.

[01:06:10] **Carol:** Mhm mhm.

[01:06:11] **Ben:** Not to like, make this Ben poops on movies for a moment.

[01:06:13] **Ben:** But like, I went to see Disclosure Day and like, the amount of.

[01:06:19] **Adam:** Oh, uh, don't ruin it.

[01:06:21] **Adam:** I'm, I, I'm, I'm gonna go see that soon.

[01:06:22] **Ben:** Okay, okay, okay, here.

[01:06:23] **Ben:** I'll just say, like, this is also just like a very long movie that has a perspective that didn't resonate with me,

[01:06:29] **Adam:** Okay.

[01:06:30] **Adam:** Oh,

[01:06:31] **Tim:** Wow.

[01:06:32] **Ben:** but I'll just leave it at that.

[01:06:33] **Ben:** But also, like,

[01:06:34] **Adam:** well, I mean, it sounds like you don't like anything anymore, so it's probably okay.

[01:06:37] **Ben:** I can't wait for Ted Lasso.

[01:06:40] **Adam:** Oh, man.

[01:06:43] **Adam:** It.

[01:06:43] **Ben:** No, I'm very excited for Ted Lasso.

[01:06:45] **Ben:** All right, I'll stop pooping on things.

[01:06:47] **Carol:** Yeah.

[01:06:47] **Carol:** Because The Odyssey was great, so I don't know what to talk about.

[01:06:49] **Ben:** Yeah.

[01:06:50] **Tim:** You enjoyed it.

[01:06:50] **Ben:** Car.

[01:06:50] **Ben:** Yeah, exactly.

[01:06:51] **Ben:** Like,

[01:06:52] **Carol:** Mm.

[01:06:52] **Ben:** look, I live with a woman who is very happy to tell me that most of the stuff that I watch is garbage.

[01:06:59] **Adam:** Mhm.

[01:07:01] **Ben:** So, uh, very much.

[01:07:02] **Ben:** To each their own.

[01:07:03] **Ben:** Beauty is in the eye of the beholder

[01:07:07] **Adam:** Oh my goodness.

[01:07:07] **Ben:** Mhm.

[01:07:08] **Tim:** Oh, and thank you for giving me the idea.

[01:07:09] **Tim:** I was working on this while we were recording.

[01:07:11] **Tim:** I just made.

[01:07:12] **Tim:** I have an Outlook skill that basically will draft an email for me and pop it in my drafts.

[01:07:18] **Carol:** Yep.

[01:07:18] **Tim:** My Outlook Um, and while you mentioned it, I had it trained, my voice.

[01:07:19] **Carol:** Mine does too.

[01:07:25] **Tim:** And then I did an email that I sent today that it was a good email but like, didn't sound like me.

[01:07:29] **Tim:** Now it sounds like me.

[01:07:30] **Tim:** So cool.

[01:07:31] **Carol:** Nice.

[01:07:31] **Ben:** Wait, you did all of that while we were doing the recording?

[01:07:31] **Adam:** Nice.

[01:07:31] **Tim:** Thanks for the idea.

[01:07:34] **Tim:** Yeah, yeah.

[01:07:35] **Carol:** Yeah.

[01:07:35] **Carol:** Ben, some of us do things while we record this show.

[01:07:38] **Ben:** No, like, just Tim's ability to multitask is kind of impressive.

[01:07:42] **Adam:** Yeah, I also multitask, but usually at the expense of understanding what's going on on the show.

[01:07:47] **Tim:** What'd you say?

[01:07:47] **Adam:** Like.

[01:07:48] **Carol:** Yeah.

[01:07:48] **Adam:** Yeah, yeah, it's exactly how I feel.

[01:07:50] **Carol:** You'll know if I'm doing something because you're just gonna get head nods and it's gonna.

[01:07:53] **Carol:** Huh huh huh.

[01:07:54] **Carol:** Uh-huh.

[01:07:55] **Ben:** I.

[01:07:55] **Ben:** I can't multi.

[01:07:55] **Carol:** Yeah.

[01:07:55] **Tim:** I had to do a side by side of an email.

[01:07:57] **Tim:** I'm like, yeah, that sounds a whole lot more like me.

[01:07:59] **Tim:** And the, the ellipses, which absolutely drive my children crazy.

[01:08:02] **Tim:** But I bet I use ellipses all the time.

[01:08:04] **Ben:** I love an ellipsis.

[01:08:04] **Adam:** Mm, mhm.

[01:08:04] **Tim:** I should.

[01:08:07] **Tim:** What'd you say, Ben?

[01:08:07] **Ben:** I love ellipses.

[01:08:08] **Tim:** I do too.

[01:08:09] **Tim:** Yeah, they're great.

[01:08:10] **Carol:** That's a dot, dot, dot, Right?

[01:08:11] **Ben:** Yeah.

[01:08:11] **Tim:** Yeah, no, uh, it's these things.

[01:08:12] **Adam:** Yeah, that's a millennial thing.

[01:08:13] **Adam:** I think

[01:08:13] **Carol:** I.

[01:08:13] **Carol:** I love.

[01:08:14] **Carol:** I love that too

[01:08:15] **Adam:** my lips.

[01:08:16] **Tim:** Ellipses on my faces.

[01:08:20] **Tim:** Uh, good times.

[01:08:20] **Adam:** All right, we are definitely giddied out.

[01:08:24] **Adam:** It's time to wrap this up.

[01:08:25] **Carol:** Mhm.

[01:08:26] **Adam:** patrons, thank you so much for your support.

[01:08:28] **Adam:** Your heart matters more.

[01:08:29] **Adam:** We.

[01:08:29] **Adam:** We what?

[01:08:30] **Adam:** What else do I say?

[01:08:31] **Adam:** We'll catch you again next week.

[01:08:34] **Adam:** For French reasons.

[01:08:36] **Tim:** But ellipses.

[01:08:36] **Ben:** Mhm.

[01:08:38] **Adam:** We'll catch you guys next week.

[01:08:40] **Adam:** Thank you so much for your support.

[01:08:41] **Adam:** don't forget to, uh, go on our Discord and tell us what, uh, your AI concerns are.

[01:08:46] **Tim:** For sure.

[01:08:46] **Adam:** Uh, anyway, catch you next week.

[01:08:48] **Adam:** See you, Bye.

[01:08:49] **Tim:** Bye.

[01:08:49] **Carol:** Tusk.

[01:08:49] **Ben:** Cheers.
