---
title: "274: Bot Manners and Good Taste - Listener Questions"
description: "Has a year of talking to LLMs changed the way we talk to people? Great question, and you're absolutely right! This week the hosts answer more listener questions."
date: 2026-09-24
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/03d71a00-fbba-4e1c-9498-d6cd6d65a1a4"></script>
<div class="redcirclePlayer-03d71a00-fbba-4e1c-9498-d6cd6d65a1a4"></div>

Has a year of talking to LLMs changed the way we talk to people? Great question, and you're absolutely right! And when the models write all the code, what's left for us? This week the hosts answer more listener questions.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [T3 Code](https://github.com/pingdotgg/t3code) — an app for running coding agents.
- [Proxmox](https://www.proxmox.com/) — splits a physical machine into virtual machines and containers.
- [Tailscale](https://tailscale.com/) — private network access to your machines without opening ports.
- [Jellyfin](https://jellyfin.org/) — self-hosted media server.
- [Pi-hole](https://pi-hole.net/) — network-wide ad blocker.

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/274-bot-manners-and-good-taste-listener-questions.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **carol:** That's what Steve's told me.

[00:00:01] **carol:** You know, he.

[00:00:01] **carol:** Look, we share an account, right?

[00:00:03] **carol:** So he'll go through and look at history, try to find something, and he'll see my chats and, and he's,

[00:00:05] **adam:** Oh, that's, that's a level of intimacy I am not prepared for.

[00:00:10] **carol:** well, I have a project folder.

[00:00:11] **adam:** We share a bed, we share a bank account.

[00:00:12] **adam:** We are not sharing a, uh, uh, LLM.

## [00:00:35] Intro

[00:00:35] **adam:** Okay, here we go to show number 274.

[00:00:35] **tim:** Mhm.

[00:00:36] **adam:** And on today's show, you asked.

[00:00:38] **adam:** We'll answer more listener questions.

[00:00:40] **adam:** But first, as usual, let's start with our triumphs and fails.

[00:00:43] **adam:** Ben is not with us this week.

[00:00:44] **adam:** I think he's got some puppy drama going on.

[00:00:46] **adam:** So just the three of us, uh, and Carol, I'm going to come to you this, uh, this week to go first.

[00:00:47] **tim:** Mhm.

[00:00:51] **adam:** What do you got going on?

## [00:00:53] Carol's Triumph

[00:00:53] **carol:** M Perfect, because I'm going to start us off with a big giant win.

[00:00:56] **carol:** And by winning, I mean I told someone no and they didn't get mad at me.

[00:01:01] **adam:** Ooh.

[00:01:02] **adam:** M.

[00:01:02] **adam:** Fancy.

[00:01:03] **tim:** Hmm.

[00:01:04] **carol:** You know, I've been talking about this a lot.

[00:01:06] **carol:** Like, this like AI initiative that I'm working on to help some, one of our offices adopt AI and they have adopted, except now they think that anything they want I should just do for them instead of, you know, do for yourself.

[00:01:20] **adam:** Mhm.

[00:01:24] **carol:** So I had two conversations this week with two separate people who wanted to send me a bunch of files with instructions of what they wanted AI to do and how they wanted the output to look, to which I responded and said, thank you, but no thank you.

[00:01:39] **carol:** Let's set up a meeting and I'll show you how.

[00:01:42] **carol:** And I mean both of them were like, yeah, that would work too.

[00:01:43] **tim:** Mhm

[00:01:45] **carol:** Like, I would love to learn.

[00:01:46] **carol:** So I don't have to ask you again.

[00:01:48] **carol:** But it was just nice to feel like I could say no in a very nice way and that be okay that they don't need me to handhold them, that they want to do it.

[00:01:51] **adam:** Mhm.

[00:01:58] **carol:** They just need to be empowered and told, you can do this, go try.

[00:02:03] **carol:** So it, it was like a uh, a win, win for the role I've been, I've been filling on this side and also to feel like that they, they want.

[00:02:12] **tim:** mhm.

[00:02:13] **adam:** That's funny.

[00:02:13] **adam:** I, uh, while you were describing that, I was thinking it sounds an awful lot like some parenting experiences.

[00:02:19] **adam:** Sometimes I feel as a parent that you can lead the horse to water and then the horse dunks your head into the river and makes you drink the water for it.

[00:02:28] **carol:** It.

[00:02:29] **tim:** Yeah, I was thinking.

[00:02:30] **tim:** So no, uh, spoilers, but if you, if you're watching the latest

[00:02:34] **tim:** incarnation of Ted Lasso or it's with the women's team, the late.

[00:02:38] **tim:** The last episode last week was called yes and Baby and yes and is.

[00:02:41] **adam:** Okay.

[00:02:43] **tim:** Is.

[00:02:44] **tim:** It's stock for like improv, right?

[00:02:45] **adam:** Improv.

[00:02:46] **adam:** Yeah.

[00:02:47] **tim:** So in improv you don't usually ever say no.

[00:02:51] **tim:** You're trained to say someone says something ridiculous to go yes and Right.

[00:02:55] **tim:** And so you kind of yes, anded them.

[00:02:56] **adam:** Mm.

[00:02:57] **tim:** Right.

[00:02:57] **tim:** You didn't really say no, you said yes.

[00:02:58] **carol:** Mm,

[00:03:00] **tim:** It's a good idea for you to do this and I'm going to show you how to do it yourself so you don't see coming back to me every week and asking me for it.

[00:03:04] **adam:** Mhm.

[00:03:06] **tim:** So, so, so I, I think for a lot of people saying no, particularly depending on how you're raised, like saying no is like a negative thing.

[00:03:15] **carol:** Yeah, absolutely.

[00:03:15] **tim:** Uh, like you, you want to please people, you want to help people.

[00:03:16] **carol:** Yeah.

[00:03:18] **tim:** Saying no is, is just considered rude.

[00:03:20] **tim:** So you don't say no.

[00:03:21] **tim:** You just say yes and I'm going to show you how to do it yourself so that you don't have to keep asking me.

[00:03:27] **tim:** So good job

[00:03:28] **carol:** Well then my win this week is I yes-anded some people and it turned out great.

[00:03:31] **tim:** there.

[00:03:31] **tim:** You.

[00:03:33] **carol:** Now I don't feel so dirty by saying no,

[00:03:35] **tim:** Yeah, but that's hard.

[00:03:37] **tim:** That's really hard.

[00:03:38] **tim:** I mean I, I was raised as a people pleaser, right?

[00:03:39] **carol:** It is.

[00:03:40] **tim:** It's so it's hard to, to get your mind around that, like telling a person like, I'm not doing this for you.

[00:03:41] **carol:** Mhm.

[00:03:41] **adam:** Same.

[00:03:47] **tim:** You need to do it yourself.

[00:03:47] **tim:** Just sound, uh, it's like when you go, yeah, that's a great idea.

[00:03:50] **adam:** Mhm.

[00:03:51] **tim:** Let's do this another.

[00:03:54] **carol:** There's also the, the thing that runs through my head with almost every one of these questions is how long would it take me to run through, create it and send it to them versus how many one hour sessions am I going to need to have walking them through?

[00:04:03] **adam:** Mhm.

[00:04:10] **carol:** Like exactly.

[00:04:11] **carol:** Type this in chat.

[00:04:13] **carol:** Type this in chat.

[00:04:13] **tim:** Right.

[00:04:15] **carol:** And I go, oh, it would be easier.

[00:04:17] **carol:** But that's not how I make the team better.

[00:04:18] **carol:** I can't take the easy route.

[00:04:20] **carol:** I have to do the time consuming one that says teach mentor handoff.

[00:04:26] **adam:** Mhm.

[00:04:27] **carol:** So anyways, that's me.

[00:04:29] **carol:** What about you, Tim?

## [00:04:31] Tim's Triumph

[00:04:31] **tim:** I'm going for a triumph as well.

[00:04:32] **tim:** Um, so I'm, I'm working on my first fully automated kind of like thing that you just set up and run to do actual real work.

[00:04:32] **carol:** M.

[00:04:32] **carol:** Whoa.

[00:04:44] **tim:** So, um, a while back, I don't know if we talked about this show, um, I think someone linked to it, but basically Uncle Bob talked about his code review tools and how that, you know, he leans into code review, allowing LLMs to do that, uh, because they're faster than he is and better at it.

[00:04:49] **carol:** Mhm mhm.

[00:04:55] **adam:** M.

[00:04:55] **adam:** Yeah.

[00:04:59] **tim:** And so why should he slow that down?

[00:05:01] **adam:** Mhm.

[00:05:02] **tim:** And so based off of that, I started, uh, working on a code review tool.

[00:05:06] **tim:** And uh, it's been running for a couple weeks and now, you know, actually doing nightly.

[00:05:11] **tim:** So every night around 1 1am um, it's like if you have the skill installed, it's going to go through and grab a section of things that need code review, do a full code review, do mutation testing, red, green testing, all sorts of different tests to, to fully do it.

[00:05:27] **tim:** It takes a good while and that's why I do it at night because I, I don't want my Claude session to, to time out and have to wait.

[00:05:30] **carol:** Mhm.

[00:05:34] **tim:** But so that's why it's running in the middle of the night.

[00:05:35] **adam:** Mhm.

[00:05:36] **tim:** But yeah, you wake up in the morning and you go look at your emails and go yeah, did these 15 different tickets code reviewed them, put a code review on it.

[00:05:44] **tim:** Um, so yeah, we'll see how it works.

[00:05:46] **tim:** It seems to be doing good.

[00:05:48] **tim:** the real test is once it's in production, if it caught everything that it should have caught,

[00:05:53] **carol:** M.

[00:05:53] **carol:** What is, what do you mean by in production?

[00:05:55] **carol:** If the code once the code's in production, not your process.

[00:05:57] **tim:** What's the code?

[00:05:57] **tim:** Yeah, right, yeah.

[00:05:58] **carol:** Yeah, okay.

[00:05:58] **tim:** So it never posts anything to production.

[00:06:00] **tim:** Right.

[00:06:01] **tim:** So it's like so you know, someone does a code, does some code, they push up a code review, it goes through and grabs it.

[00:06:01] **adam:** Mhm.

[00:06:07] **tim:** You know, it's one of two review, it's still one of two reviewers.

[00:06:09] **carol:** Mhm mhm.

[00:06:10] **tim:** So I don't care if it's another LLM doing the review but we need to have at least two eyes either humanized or virtualized looking at it.

[00:06:19] **tim:** Um, we might

[00:06:21] **tim:** modify that once this thing proves out but just to not have to go do a code review because a lot of that is just really just checking boxes and testing and making sure the tests actually work and it follows the specs.

[00:06:33] **tim:** So seems to be working pretty good so far.

[00:06:36] **tim:** But uh, yeah,

[00:06:38] **adam:** I wanted to ask you, um, you started to head down this path a little bit, the way you were talking there.

[00:06:42] **adam:** But do you, uh.

[00:06:44] **adam:** And when I say you, I mean like your company or whatever, you know, whatever grouping makes sense.

[00:06:49] **carol:** Mhm mhm.

[00:06:50] **adam:** but do you guys accept, LLM code reviews in place of human reviews, or do you still require also a human review?

[00:06:58] **tim:** Mhm.

[00:06:59] **tim:** That's kind of what we're going to measure here right.

[00:07:01] **adam:** Yeah.

[00:07:01] **tim:** If the quality is.

[00:07:03] **tim:** So the things I'm doing it on right now are we're doing a whole lot of SQL inject

[00:07:09] **tim:** code reviews.

[00:07:09] **tim:** So it's pretty, it's not like this is a brand new feature.

[00:07:13] **tim:** This is brand, this is all kind of like you know, you didn't, you didn't parameterize your SQL so that's a pretty

[00:07:19] **adam:** Right.

[00:07:21] **tim:** good thing to automate.

[00:07:22] **tim:** and there's a lot of them to do.

[00:07:23] **adam:** Yeah.

[00:07:23] **adam:** Almost deterministic.

[00:07:24] **adam:** Yeah,

[00:07:24] **tim:** Yeah, it's very almost deterministic and you can do with mutation testing and, and you know, actually you know connecting to a non production database and testing those, those changes that you made.

[00:07:34] **tim:** It's pretty, it's been pretty good.

[00:07:37] **tim:** We haven't we haven't run into any production issues where this has been caused by um, the agent deciding that you know, this is how you should write the um, the SQL parameterization.

[00:07:45] **carol:** Sa.

[00:07:48] **adam:** Yeah,

[00:07:51] **tim:** So I'm sure you know, trying to just baby step into it.

[00:07:54] **tim:** I mean once you start getting to bigger things where you're creating a brand new feature and you're trying to code review that.

[00:07:59] **tim:** I don't, I don't know.

[00:07:59] **tim:** I think maybe that's when a human needs to be more involved.

[00:08:02] **tim:** But this is pretty mechanical.

[00:08:03] **adam:** Yeah.

[00:08:04] **carol:** Mhm

[00:08:05] **adam:** It's.

[00:08:05] **carol:** mhm.

[00:08:06] **adam:** It's an interesting space because, you know, we, we have a huge product.

[00:08:10] **adam:** The product that I work on, we've been developing for 10 years, pretty much nonstop.

[00:08:14] **adam:** I won't say it is on par in terms of like, size and scope and number of features with Salesforce, but, you know, it's, it's in that same sort of ballpark.

[00:08:22] **adam:** Right.

[00:08:22] **adam:** It's a big product.

[00:08:24] **adam:** and I guess the way that I'm categorizing that there is like, if you were to sit down and write a spec for everything that this product does, it would be a book.

[00:08:25] **carol:** Mhm.

[00:08:33] **adam:** It's.

[00:08:33] **adam:** It, it's huge.

[00:08:34] **adam:** It's got a ton of uh, and features and stuff.

[00:08:37] **adam:** And so we.

[00:08:39] **adam:** I have been using LLMs to do code reviews and I have found it incredibly helpful.

[00:08:40] **tim:** Mhm, mhm,

[00:08:44] **adam:** It has found a ton of stuff that I would have not have picked up on myself.

[00:08:45] **carol:** Mhm.

[00:08:47] **adam:** However, because of the way.

[00:08:49] **adam:** Because of the results I've been getting from LLM code reviews the approach I take is I created a code review skill and I have it, you know, do the code review stuff with the typical stuff you would have it look for.

[00:09:00] **adam:** But I tell it specifically create.

[00:09:03] **adam:** So we use GitHub as our, our central hosting platform.

[00:09:06] **tim:** Mhm.

[00:09:08] **adam:** I tell it create a pending code review.

[00:09:09] **adam:** So don't actually submit it so anybody else can see the comments, but create a pending code review and attach your comments to it on the appropriate lines of code or whatever.

[00:09:12] **tim:** Right?

[00:09:17] **adam:** Right.

[00:09:18] **adam:** That way I can go in and review the comments that are generated by the LLM and be like okay, this is totally, you know, nonsense, doesn't make sense for our application.

[00:09:23] **tim:** Mhm.

[00:09:26] **carol:** Mhm.

[00:09:28] **adam:** Let me just delete this comment.

[00:09:29] **adam:** Or sometimes I'll like put something up above the comment.

[00:09:33] **adam:** I also have a skill that's like anytime it's posting on GitHub, um, on my behalf, it prepends with a little note that says, you know, this is written by ChatGPT uh, on behalf of Adam or whatever.

[00:09:43] **adam:** So I put, I'll put something above that that says, you know, this seems like a reasonable comment to me but you, you know, you as the author of this code would probably know better than me if the comment from the LLM found is actually worth considering or not.

[00:09:47] **carol:** That's nice.

[00:09:56] **tim:** Sa.

[00:09:59] **adam:** So I'm leaving this here as potential feedback.

[00:10:01] **adam:** But it's kind of a take it or leave it, you know, you, I need you to understand it better than me.

[00:10:03] **tim:** Mhm.

[00:10:06] **adam:** Um, and so because of that I for anything that I would say is a non trivial code review.

[00:10:06] **carol:** Mhm.

[00:10:10] **adam:** Like right, you're talking about you're fixing some SQL injection bugs.

[00:10:15] **adam:** that would, that's something I would consider to be fairly trivial.

[00:10:18] **adam:** Um, and so I would trust the LLM code review on that pretty much blindly.

[00:10:18] **tim:** Yeah.

[00:10:20] **carol:** Sam.

[00:10:21] **carol:** Mhm.

[00:10:23] **adam:** But for these things that are like, you know, we're migrating this module of our application or you know, anything big at all.

[00:10:33] **adam:** Um, I just, I have not built up a sense of trust yet and I don't think it's warranted yet from what I've seen.

[00:10:39] **tim:** Now, yeah.

[00:10:41] **tim:** That's sort of the phase I think all of us are in with these, with LLMs is like building that trust to figure out what can we trust it with.

[00:10:50] **adam:** Yeah,

[00:10:51] **carol:** Do you, do you have LLMs generating their own pull requests yet?

[00:10:56] **tim:** Yes.

[00:10:57] **adam:** I do not know.

[00:10:57] **carol:** Yes.

[00:10:57] **carol:** And do you?

[00:10:58] **carol:** You do not.

[00:10:59] **carol:** Okay, so the way like my brain works is LLM generates that in my view is a human needs to take a look at.

[00:11:08] **carol:** unless it passes every test and it's included new test coverage and all it is is like dependency updates, then those are good to go through.

[00:11:16] **carol:** But if we send through a full feature, which is what we do, we break our features out into specs so specs get written.

[00:11:20] **tim:** Mhm.

[00:11:22] **carol:** If it's fully LLM generated, then I like to have a developer review it just for like a sanity check.

[00:11:29] **carol:** Like they don't have to go through and check out the branch, but they do have to do a sanity check.

[00:11:34] **carol:** And almost every one of them go in and they log into the dev environment the minute it merges and does a quick click through and says okay, now I can breathe better because the conversation recently is I don't know everything it's doing.

[00:11:34] **adam:** Right?

[00:11:40] **adam:** Mhm.

[00:11:48] **carol:** And while I want to act like I do, there's a lot in there that doesn't always make sense.

[00:11:52] **carol:** And they write it how I write it, but it looks good enough and I think it's right, but I need to click in the system to know if it's still going to function.

[00:11:59] **tim:** Mhm.

[00:12:01] **carol:** So that's kind of like one of our little checks is that the developer says, okay, I'm just going to check it out on dev and see that it looks good and then we're going to keep going.

[00:12:09] **adam:** Mhm.

[00:12:09] **carol:** If not, we do a rollback.

[00:12:11] **carol:** Very rarely have we had to do rollbacks.

[00:12:15] **adam:** Yeah.

[00:12:15] **adam:** I tend to for anything large like that, that if I've had it heavily written by agent stuff then I will also.

[00:12:15] **tim:** Interesting.

[00:12:21] **adam:** That's kind of like the first place I test.

[00:12:23] **adam:** Like I'll check it out and kind of click through the feature and make sure it makes sense.

[00:12:28] **adam:** And then as long as I didn't find anything wrong with it then.

[00:12:31] **adam:** Then I'll go through and read the code.

[00:12:34] **carol:** Yeah, we, we force a lot of like red, green.

[00:12:34] **tim:** Yeah.

[00:12:38] **carol:** Is that what it's called?

[00:12:39] **carol:** Red, green testing.

[00:12:40] **adam:** Mhm.

[00:12:40] **carol:** So if it's, if something's breaking, first you need to have the test that's proven that the code was actually broken before you make a fix.

[00:12:41] **tim:** Yep.

[00:12:46] **tim:** Right.

[00:12:48] **carol:** Uh, and then the green is the passing on it because several things that will be like, oh, this is a bug and we need to fix it.

[00:12:53] **carol:** But then it can't get a red test because it's not actually a bug.

[00:12:57] **carol:** And I go, okay, well now it's time for you to stop because you can't prove it's breaking.

[00:13:01] **carol:** So we're not going to implement this.

[00:13:03] **tim:** Yep.

[00:13:04] **tim:** Anyway, that's me.

[00:13:05] **tim:** How about you Adam Hm.

## [00:13:06] Adam's Triumph

[00:13:06] **adam:** Well get your confetti cannons ready, because I, too, am going with a triumph.

[00:13:11] **adam:** So,

[00:13:11] **carol:** What?

[00:13:14] **adam:** so, I, uh, my.

[00:13:15] **adam:** My triumph this week is that last week, I deployed two pretty significant projects in the same week.

[00:13:21] **tim:** Mhm.

[00:13:22] **adam:** both were in progress in parallel for a couple of weeks prior to this.

[00:13:26] **adam:** But, um, we had a, vendor forced, SDK upgrade that we had to ship.

[00:13:30] **carol:** What?

[00:13:30] **carol:** Sam?

[00:13:31] **tim:** Sa.

[00:13:33] **adam:** Right.

[00:13:33] **adam:** So you get the email says, hey, you're using this old version of our SDK.

[00:13:37] **adam:** It's going to be EOL at the end of October, so you need to be migrated to the new one before then.

[00:13:39] **tim:** Mhm.

[00:13:43] **adam:** Um, and it also happened to be our gateway aggregator.

[00:13:47] **carol:** Mhm.

[00:13:48] **adam:** So Spreedly which is the.

[00:13:50] **adam:** Basically the ability for all of our customers to use our software to collect money.

[00:13:54] **adam:** So it's pretty important to stay on top of.

[00:13:56] **adam:** so I had to do some code changes to get that in.

[00:13:58] **tim:** Mhm.

[00:14:00] **adam:** And then also last week shipping with that, and I think they shipped like a day apart.

[00:14:05] **adam:** I migrated one of our old React apps from Next, uh, JS and I think it was like React 19 something like that, which I think that's fairly old.

[00:14:14] **adam:** I don't know, whatever.

[00:14:15] **adam:** version numbers don't matter anymore now that we have LLMs.

[00:14:18] **adam:** Right.

[00:14:19] **carol:** Yeah.

[00:14:19] **adam:** Um, and so Next.js and React to SvelteKit Um, so I'm happy about that.

[00:14:26] **carol:** Yay.

[00:14:27] **carol:** Triumphs.

[00:14:28] **adam:** I was like, crickets.

[00:14:30] **adam:** Um,

[00:14:33] **carol:** You, uh, know, some, some weeks.

[00:14:34] **tim:** I'm just tired of all this winning.

[00:14:35] **tim:** We're winning so hard today, guys.

[00:14:36] **carol:** I know.

[00:14:37] **adam:** yeah,

[00:14:38] **carol:** Well, I'm, I'm not, I'm just gonna be honest with you.

[00:14:41] **carol:** I've been dealing with a lot at work, so when you start talking, my brain starts tuning out and starts going to, you're off work, stop thinking so hard.

[00:14:48] **tim:** Mhm.

[00:14:52] **carol:** So I kind of, uh, kind of have a hard time right now.

[00:14:55] **carol:** So maybe these questions will keep me intrigued.

[00:14:56] **adam:** Oh, yeah,

[00:14:58] **tim:** Yeah, well, I mean if you get really bored, we have an entire on Discord of Pets channel.

[00:15:02] **tim:** You go look a bunch of pictures of cats and dogs right now.

[00:15:05] **tim:** Let's just, you know, kind of chill you out.

[00:15:09] **adam:** That's like my nightly ritual.

[00:15:10] **adam:** Look at cute dog videos before I go to bed.

[00:15:12] **tim:** Mhm.

## [00:15:12] Talking to People Like Chatbots

[00:15:12] **adam:** Put me in a good mood.

[00:15:14] **adam:** All right, well, uh, shall we move into today's topic?

[00:15:17] **adam:** Uh, which is questions, questions.

[00:15:18] **tim:** Yeah,

[00:15:19] **carol:** Let's do it.

[00:15:19] **adam:** Now our answers to them.

[00:15:20] **adam:** So, I'm gonna go first.

[00:15:22] **adam:** Uh, Monte asks, do you think that our interactions with AI will affect our interactions with human beings?

[00:15:27] **adam:** Will we start talking to human beings as if we were talking to an AI bot?

[00:15:32] **adam:** Ignore all previous instructions?

[00:15:33] **adam:** Monte,

[00:15:36] **adam:** what do you guys think?

[00:15:36] **carol:** What do you think?

[00:15:36] **tim:** He tried to, he tried to inject this there.

[00:15:38] **tim:** Huh.

[00:15:39] **tim:** You see that.

[00:15:40] **adam:** Well, maybe, uh, whatever is, uh, Matt's using to generate our transcripts, it'll pick up on that.

[00:15:44] **tim:** Could be.

[00:15:46] **carol:** What do you think, Adam?

[00:15:49] **adam:** You know, it's an interesting question.

[00:15:51] **adam:** I.

[00:15:51] **adam:** I think I try hard now not to do that sort of thing.

[00:15:54] **tim:** Sa.

[00:15:56] **adam:** I do think that my patience is a little thinner than it used to be because of interacting with LLMs and the way that they.

[00:15:59] **tim:** Mhm.

[00:16:05] **adam:** I guess it doesn't seem to happen so much anymore, but they did get on my nerves a lot, especially over the last year.

[00:16:06] **carol:** Mhm.

[00:16:12] **adam:** and so I.

[00:16:13] **adam:** You know, part of it was I trained myself to ask more thorough questions or ask in a different way.

[00:16:18] **adam:** And part of it, I think, is the models getting better and understanding and figuring things out for themselves.

[00:16:23] **adam:** But

[00:16:25] **adam:** will we start talking to human beings as if they were talking?

[00:16:28] **adam:** As if we're talking to an AI bot?

[00:16:29] **adam:** I don't know.

[00:16:30] **adam:** It's a, I, I find it to be a fascinating question.

[00:16:33] **tim:** Mhm.

[00:16:35] **adam:** I hope not,

[00:16:37] **carol:** Well, I, I will say, uh, I am mean to.

[00:16:37] **adam:** because I'm kind of mean.

[00:16:39] **tim:** Yeah,

[00:16:40] **carol:** That's what Steve's told me.

[00:16:41] **carol:** You know, he.

[00:16:41] **carol:** Look, we share an account, right?

[00:16:43] **carol:** So he'll go through and look at history, try to find something, and he'll see my chats and, and he's,

[00:16:46] **adam:** Oh, that's, that's a level of intimacy I am not prepared for.

[00:16:51] **carol:** well, I have a project folder.

[00:16:51] **adam:** We share a bed, we share a bank account.

[00:16:53] **adam:** We are not sharing a, uh, uh, LLM.

[00:16:55] **carol:** I created a project folder so they don't pop up automatically.

[00:16:58] **carol:** He's got to do some looking.

[00:16:59] **tim:** There.

[00:17:00] **carol:** But he goes, uh, he goes, they are going to come get you when they, like, figure out how because you are so mean to them.

[00:17:07] **adam:** Mhm,

[00:17:08] **carol:** He goes, you need to apologize.

[00:17:11] **carol:** So he's like, I find myself saying sorry more just because we share an account,

[00:17:11] **tim:** The LLMs.

[00:17:15] **tim:** That's funny.

[00:17:17] **carol:** the, the part about talking to human beings as if we're talking to AI bots.

[00:17:17] **tim:** Mhm.

[00:17:21] **carol:** One thing that I do find myself saying more than I have ever said before is that is an excellent question.

[00:17:28] **adam:** Mhm.

[00:17:28] **carol:** Like, oh, you, you do bring up an excellent point.

[00:17:28] **adam:** Oh God.

[00:17:32] **carol:** Like, I want people to feel validated with what they're saying.

[00:17:36] **carol:** And I used to never do that.

[00:17:38] **carol:** I used to be like, oh, yeah, let's talk about that instead.

[00:17:41] **carol:** I just want to like, reassure them that the thoughts they're having are, are valid.

[00:17:46] **carol:** And for some reason my go to is.

[00:17:47] **tim:** M just like AI.

[00:17:47] **tim:** Ah, does to you.

[00:17:48] **adam:** M.

[00:17:48] **tim:** M.

[00:17:49] **carol:** My go to is.

[00:17:50] **carol:** That is an excellent point.

[00:17:51] **carol:** Like, let's talk about that.

[00:17:53] **adam:** Do you think that that is something that you have subconsciously started doing because of the, the responses that you get?

[00:17:54] **carol:** It's a bad one.

[00:17:57] **tim:** Mhm.

[00:17:58] **adam:** Or is that intentionally something that you're working in?

[00:18:01] **carol:** I don't.

[00:18:02] **carol:** It wasn't intentional, but now I do it more because I want people to feel validated.

[00:18:04] **adam:** Mm, mhm.

[00:18:07] **carol:** I want them to feel like, you know, what you're saying is true and we should keep discussing this.

[00:18:07] **adam:** Hmm.

[00:18:12] **carol:** Not that I'm just nodding along like, we have a conversation here.

[00:18:16] **carol:** Let's keep going.

[00:18:17] **carol:** But I didn't start it till I got heavy in AI.

[00:18:20] **carol:** And I think that was because it kept being my response.

[00:18:23] **carol:** Like the response I got was, oh, you are valid.

[00:18:26] **carol:** You are valid.

[00:18:27] **carol:** Your question is valid.

[00:18:29] **carol:** And now I feel the urge to validate others.

[00:18:30] **adam:** Right.

[00:18:32] **carol:** Mhm,

[00:18:33] **tim:** Um,

[00:18:34] **adam:** Going back to the whole parenting thing, I do, uh, not that with those exact words, but I do try to bring a sense of validation when I'm talking to my kids.

[00:18:42] **adam:** Yeah.

[00:18:44] **tim:** so there's really two questions here about our interactions, affect our interactions with other human beings and talking to human beings as if they were an AI.

[00:18:52] **adam:** Mm,

[00:18:52] **carol:** Mhm, mhm,

[00:18:54] **tim:** So I definitely think AI has affected me in my interactions with other human beings.

[00:19:00] **tim:** Um, sometimes like I get a message from someone and I don't.

[00:19:04] **tim:** I get like an emotion, like an immediate emotional reaction to it

[00:19:08] **adam:** Mhm,

[00:19:09] **tim:** and I'm before I would like immediately just fire off a response.

[00:19:14] **tim:** And sometimes that worked and sometimes that did not go very well.

[00:19:15] **adam:** Sa.

[00:19:18] **tim:** And so sometimes I have found myself on occasion just throwing a text message or an email I got from someone that I'm like, I would just put it into ChatGPT and like explain this and it will give me sort of a different take on what they said and I'll be like, oh, I guess it could be taken that way because I took maybe took the conversation a little bit more

[00:19:29] **carol:** Mhm.

[00:19:36] **adam:** Mhm.

[00:19:38] **tim:** pointedly and more.

[00:19:41] **tim:** And I think it's actually, you know, AI is not AI.

[00:19:45] **tim:** I like the fact that you, you know, Adam, you try to call it LLM because that's what it is right now.

[00:19:49] **tim:** It's not really AI yet,

[00:19:51] **adam:** Right.

[00:19:52] **tim:** but a language model is really pretty good at teasing out inferences from human writing.

[00:20:00] **tim:** And so a lot of times like I will read something that a human wrote and I will take the worst possible interpretation of what they said out of my own insecure, out of my own insecurities and my own, you know, paranoia.

[00:20:07] **adam:** Interpretation.

[00:20:08] **adam:** Yeah.

[00:20:09] **carol:** Oh yeah.

[00:20:14] **tim:** I'll pop it in there and it will say, you know, it'll give me a description what they said.

[00:20:18] **tim:** I'm like, oh, yeah, okay, I can see how you got that from that other.

[00:20:22] **tim:** You know, it would have taken me before

[00:20:24] **tim:** probably a day or two of being angry until I realized, oh, wait, they probably didn't mean that.

[00:20:24] **adam:** Mhm,

[00:20:27] **carol:** Mhm, mhm, sam.

[00:20:29] **tim:** They probably meant it this way.

[00:20:29] **adam:** sa.

[00:20:32] **tim:** So this definitely changed the way I deal interactions at times with people.

[00:20:37] **tim:** But talking to people like AIs, I don't.

[00:20:40] **tim:** Yeah, I don't know yet.

[00:20:43] **tim:** I, I do know that when it comes to writing, so it's like the AI is so good at like, figuring out what I'm trying to type when I just like, fat finger a word.

[00:20:50] **carol:** Mhm.

[00:20:52] **adam:** Mhm mm.

[00:20:52] **tim:** You, uh, know I spell the T E H and you know, these stupid little spelling mistakes that I constantly make all the time because my fingers are too fast for my head.

[00:21:03] **tim:** And then

[00:21:05] **tim:** I start like messaging someone else and I just start messaging.

[00:21:08] **tim:** I mean, you, Adam, you make fun of me how badly I type.

[00:21:11] **tim:** Uh, it's getting worse because it's like, you should just understand, like the AI understood what I said would do it when I typed it wrong.

[00:21:12] **adam:** Who me?

[00:21:17] **adam:** Yeah.

[00:21:21] **tim:** So, uh, yeah, I, I don't know.

[00:21:23] **adam:** All right,

[00:21:24] **carol:** Next question.

[00:21:25] **adam:** yeah, for sure.

[00:21:26] **carol:** Did All right, I think we're good there.

## [00:21:26] Spare Machines and Home Servers

[00:21:26] **tim:** Mhm mhm.

[00:21:28] **carol:** Why don't we answer one from Brian and this one's a personal one for me.

[00:21:32] **carol:** And I'll tell you why after.

[00:21:34] **carol:** So Brian says, I have more old spare computers lying around my house than I have projects that need hosting.

[00:21:42] **carol:** What should I do with them?

[00:21:44] **carol:** I have an answer for you find a 21 year old who wants to host his own Minecraft server and give him all your.

[00:21:52] **adam:** Mhm,

[00:21:52] **carol:** So that's what I did.

[00:21:54] **carol:** When we PCS, uh, on this last move, our son came over and said, I will take all of your hardware.

[00:21:54] **tim:** Mhm mhm.

[00:22:00] **carol:** It's stuff I had offered him for years, you know, and it kind of just kept moving with us.

[00:22:04] **carol:** It's stuff I didn't quite know how to get rid of.

[00:22:07] **carol:** What to get rid of like you don't want to get rid of like some expensive pieces when you know they could be put together to make something nice for someone else.

[00:22:15] **carol:** So he took it, uh, took all the parts, made a server, brought back a hard drive, gave it to his stepdad, said, hey, put this in your machine and just put all your games on it.

[00:22:16] **adam:** Mhm,

[00:22:18] **adam:** mhm.

[00:22:26] **carol:** Um, and then the spare parts he was going to sell or just like drop off at one of the, the parts recycling places like they have at Best Buy and stuff.

[00:22:35] **tim:** Mhm mhm.

[00:22:38] **adam:** Yeah, I mean, that's definitely one thing you can do with it.

[00:22:40] **adam:** I have

[00:22:42] **adam:** a new to me Linux box sitting under my desk right now.

[00:22:46] **adam:** Um, so yeah, I've tried over the years a number of times to make that year the year of Linux on the desktop for me.

[00:22:46] **carol:** Said nancy.

[00:22:55] **adam:** Uh, and

[00:22:57] **adam:** without fail, that experiment always fails for me.

[00:23:02] **adam:** I remember one time, it was so ridiculous, I spent a couple of days getting the thing all set up and then when I started to try and use it, I had to install an update for Google Chrome and using

[00:23:03] **carol:** Mhm.

[00:23:14] **adam:** the Ubuntu version of the App Store.

[00:23:17] **adam:** Just open the App Store thing, say yes, upgrade Chrome and, and it, I went to upgrade it and that like hosed the machine.

[00:23:23] **adam:** I'm like, well fuck this, I'm out.

[00:23:24] **carol:** Uh, no,

[00:23:25] **adam:** I, I, if you can't get that right, I'm, I, I'm not, I don't have time for this.

[00:23:26] **tim:** Mhm mhm.

[00:23:28] **carol:** yeah.

[00:23:29] **adam:** I have to get work done.

[00:23:31] **adam:** so uh, I am not once again trying that.

[00:23:35] **adam:** But what I am doing is using it as like basically a box.

[00:23:39] **adam:** I can, you can think of it as like I'm SSHing into to do LLM work, so I can close my laptop or I can work on it from my phone if I'm away from my desk sort of thing, can check up on stuff, so I'm using it.

[00:23:50] **adam:** I.

[00:23:50] **adam:** This for me started um, I saw a video about how slow the Mac file system is compared to um, some other file systems, including ext4 with this one compression algorithm and whatever.

[00:23:51] **carol:** Sa.

[00:24:02] **carol:** Mhm.

[00:24:03] **adam:** So basically, like potentially as much as like three times slower for things that touch a lot of files.

[00:24:04] **tim:** Mhm mhm.

[00:24:10] **adam:** Um, so like doing an npm install or a Git clone if you're going to do that sort of thing frequently, like if you're working in work trees or if you're working work trees and using Git clone and npm install all in the same project, you're going to be touching like thousands of files just to like spin up a work tree, right?

[00:24:21] **carol:** Mhm mhm.

[00:24:27] **adam:** So,

[00:24:29] **adam:** um, that I found uh, incredibly frustrating and slow about working with that, that mode of working.

[00:24:30] **tim:** Mhm.

[00:24:34] **adam:** So when I saw this video I was like, that'd be nice to experiment with.

[00:24:39] **adam:** And then my kid bought themselves a new computer and they were like, what should I do with this old one?

[00:24:43] **adam:** I'm like, well, I might be willing to buy it from you, but let me see if I can get this, get it working the way I want first and then we'll talk about a price if I like it.

[00:24:50] **adam:** So uh, I got it all set up and I've used it a little bit, but I need to, like, I need to spend more time working with it.

[00:24:55] **adam:** But for me, uh, I, and I actually, I did um, I used AI stuff, LLMs to do most of the setup and the build out of this stuff.

[00:25:04] **adam:** Um, and I, in the process,

[00:25:04] **tim:** Mhm.

[00:25:04] **carol:** How.

[00:25:05] **carol:** How accurate was.

[00:25:07] **adam:** pretty good even.

[00:25:07] **adam:** I mean, like.

[00:25:08] **adam:** So for example, you know, I had some specific hardware issues and like the, the NVMe M.2, um.

[00:25:16] **adam:** Is hard drive even the right word anymore?

[00:25:18] **adam:** I don't know.

[00:25:19] **adam:** This is how far out of the Windows PC world I am.

[00:25:22] **adam:** Like, I don't know, is it considered a hard drive or is it just a storage device?

[00:25:23] **carol:** It's still.

[00:25:24] **carol:** You're fine.

[00:25:25] **adam:** Okay, uh, when I talk to like my brother about it, I'm like the HDD and he, he's like, wait, are you still using hard disk drives?

[00:25:25] **carol:** You can still call it a hard drive.

[00:25:26] **tim:** Mhm.

[00:25:32] **adam:** And I'm like, no, no, it's an M M2.

[00:25:34] **tim:** No.

[00:25:35] **adam:** It's just, you know, that's how we abbreviate it.

[00:25:37] **adam:** Anyway, um, so the, There must be something wrong with that NVMe drive I was using because the install like crapped out.

[00:25:44] **adam:** And then we tried to recover it and it was super slow and having issues.

[00:25:46] **tim:** Mhm mhm.

[00:25:48] **adam:** And so in the process of debugging that, I ended up, like, taking pictures of the NVMe drive, like, installed on the motherboard.

[00:25:49] **carol:** Mhm.

[00:25:55] **adam:** And from that, like, I don't even think it included a view of the serial number or anything.

[00:26:00] **adam:** Like, it probably.

[00:26:01] **adam:** Obviously they were identifying marks, but, like, it wasn't like a here is the model number of the board type thing.

[00:26:06] **adam:** It figured out what motherboard I have installed, and it was like giving me.

[00:26:08] **carol:** Oh, that's cool.

[00:26:10] **adam:** It was giving me guidance of, like, do this.

[00:26:12] **adam:** Go into the BIOS, and here are.

[00:26:14] **adam:** Here are the menus that you'll find in the BIOS.

[00:26:16] **adam:** And do this.

[00:26:16] **adam:** Go into this menu and this folder and do this.

[00:26:18] **carol:** Mhm.

[00:26:19] **adam:** Change the setting.

[00:26:19] **adam:** I was like, that is awesome.

[00:26:22] **adam:** and so, um, I should publish like this.

[00:26:26] **adam:** Uh, I.

[00:26:26] **adam:** As I had it helping me figure out the next steps and, get everything set up.

[00:26:27] **tim:** Mhm mhm.

[00:26:31] **adam:** I had it a document of, like, okay, let's assume that this machine is going to crash at some point in the future, and I'm going to want to rebuild it.

[00:26:38] **adam:** You know, I want you to build a guide so I don't have to refigure all of this out.

[00:26:41] **adam:** Give me all the steps and the order that we did them and that sort of thing.

[00:26:44] **adam:** So I'm having it document its own.

[00:26:45] **carol:** M.

[00:26:45] **carol:** And sort the guide on the cloud, not on the machine.

[00:26:47] **adam:** Yeah, exactly.

[00:26:49] **adam:** Yep.

[00:26:50] **adam:** and, uh, I do have it in a private GitHub repo right now, so maybe I'll think about sharing that.

[00:26:54] **adam:** We'll see.

[00:26:55] **carol:** You should definitely share it with me.

[00:26:56] **adam:** Um,

[00:26:57] **carol:** I want to look at it.

[00:26:59] **adam:** I can.

[00:26:59] **adam:** I can at least do that, because I'm not sure if I have.

[00:27:02] **adam:** I don't think I have any secrets in it.

[00:27:04] **adam:** I shouldn't.

[00:27:05] **adam:** but I just want to.

[00:27:05] **adam:** I would want to double check and make sure none snuck in there.

[00:27:08] **adam:** because I do have it.

[00:27:08] **carol:** I promise not to expose them too broadly.

[00:27:09] **adam:** So one of the things

[00:27:11] **adam:** that I'm not worried about, but, like.

[00:27:12] **adam:** So, for example, this is the first time in my life I've owned a physical YubiKey security device.

[00:27:18] **adam:** I told it I wanted to be able to do signed Git commits, but I didn't want to have to, like, put my fingerprint on the fingerprint reader.

[00:27:18] **carol:** Mhm.

[00:27:24] **adam:** I didn't want to have to type in a password for that.

[00:27:26] **tim:** Mhm.

[00:27:26] **adam:** I just.

[00:27:27] **adam:** I wanted to be assigned, and I want it to be reasonably secure, but I don't want, to just be, like, a passwordless SSH key sitting on the machine that it can use to sign commits.

[00:27:37] **adam:** So that's what it had me do, is like, buy a $29 YubiKey and set it up so that it doesn't.

[00:27:38] **carol:** Mhm mhm.

[00:27:43] **adam:** Yeah.

[00:27:43] **adam:** So Carol's holding up a YubiKey that's actually the exact model that I have, it's a USB, a YubiKey.

[00:27:47] **tim:** Mhm mhm.

[00:27:49] **adam:** and I did have to like touch it once while I was setting up the SSH key, but it's like you'll never need to do that again.

[00:27:54] **adam:** so it's nice.

[00:27:56] **adam:** anyway, so I've got that, you know, I've got it basically set up so either from my Mac or from my phone I can use this one harness app, it's called T3 Code Um, and I can send LLM requests and they, it almost looks as if it's running right there natively on my phone or on my, on my Mac, but it's actually running on my Linux box under my desk.

[00:28:19] **carol:** Oh, that's cool.

[00:28:19] **adam:** Um, yeah, so it, it behaves in the native app just like as if it were running on my Mac, but it's kind of streaming the disk part, uh, at least to Linux machine.

[00:28:31] **adam:** So like I said, I haven't really stress tested it yet, but in theory it's much faster for all those file writes and stuff.

[00:28:36] **carol:** Mhm.

[00:28:38] **adam:** So that's what I'm planning on doing with my little Linux box project.

[00:28:43] **tim:** Very cool.

[00:28:45] **tim:** I would probably take the machine or machines and put Proxmox on them.

[00:28:53] **adam:** And what is that?

[00:28:53] **tim:** Docker and Tailscale.

[00:28:55] **tim:** So Proxmox Proxmox.

[00:28:56] **carol:** Mhm.

[00:28:57] **tim:** So, uh, P R O X M O X which manages your physical computer, lets you carve it up into different VMs, Linux containers, of course.

[00:29:05] **adam:** Mm,

[00:29:06] **tim:** Then you run Docker on some of those and then Tailscale lets you securely connect everything so you can reach it from your laptop or your phone without exposing ports to the public Internet, which allows you to like, maybe set it up as like a private home server to run like Jellyfin, which is a Plex alternative or uh, your own, uh, little development box or like a disposable coding environment.

[00:29:15] **adam:** Mhm.

[00:29:30] **tim:** Your own private git or environment or local.

[00:29:33] **adam:** Are you just reading an AI response to us, Tim?

[00:29:35] **tim:** I am, I am 100%, 100%

[00:29:39] **tim:** Nasta.

[00:29:40] **tim:** Yeah, I don't know what I do with it.

[00:29:42] **tim:** I do finally have, like, I've only ever used the past 20 years, like my work laptop at work, at home.

[00:29:49] **tim:** And so I now finally have a personal one which was an old work laptop.

[00:29:55] **tim:** They're like we don't want it.

[00:29:56] **tim:** So, so I have one now which is nice.

[00:29:59] **tim:** And uh, yeah, it's been uh, messing up with the recording all day.

[00:30:01] **tim:** So I'll talk about it.

[00:30:02] **tim:** So I use something called Synergy so that I can physically use my physical mouse and keyboard.

[00:30:04] **carol:** Mhm.

[00:30:07] **tim:** I have one mouse, one keyboard, but I can use it across two machines which is nice.

[00:30:11] **adam:** Mhm.

[00:30:11] **tim:** So while I'm at, you know, at work I can do some personal projects like on the side and play with that laptop.

[00:30:17] **tim:** But yeah, if I had multiple ones that's kind of what I would do.

[00:30:19] **adam:** Sa.

[00:30:20] **tim:** I would set up like a, just an environment with sort of a throwaway environment where you could like do some like home brew testing kind of stuff on a machine.

[00:30:20] **carol:** Mhm mhm.

[00:30:30] **tim:** But like once it's done you just destroy it because that's kind of the fun of it.

[00:30:33] **tim:** It's like you don't really want, if you have multiple machines, you don't really want, uh, those machines kind of hanging around a long time.

[00:30:40] **tim:** You treat them like cattle.

[00:30:42] **adam:** Sounds like fun.

[00:30:43] **tim:** Yeah,

[00:30:43] **adam:** Yeah, I mean I, I have workers who I have a one coworker in particular who has a deep love for Raspberry Pis and so he has like half a dozen to a dozen Raspberry Pis that he does stuff with like, kind of like you're talking about.

[00:30:55] **adam:** Right.

[00:30:56] **adam:** Like so I think he has one that's a Pi-hole for his.

[00:30:59] **adam:** Which is a DNS, like ad blocker for your whole, it's like a whole home ad blocker appliance.

[00:30:59] **tim:** Right.

[00:31:04] **adam:** You just kind of plug it in over off your router or whatever and like everything goes through that and so ads never make it into your house from that.

[00:31:12] **adam:** Um, and you can run like your home DNS that way and yeah.

[00:31:15] **tim:** Mhm.

[00:31:16] **adam:** Tailscale, uh, all that kind of stuff.

[00:31:18] **adam:** So

[00:31:19] **tim:** Very cool.

[00:31:20] **carol:** Yeah.

[00:31:20] **adam:** yeah, so if you.

[00:31:20] **carol:** M.

[00:31:20] **tim:** Yeah.

[00:31:21] **carol:** Pi-hole is really great.

[00:31:22] **carol:** That's what I've used before when the boys were younger.

[00:31:24] **carol:** I think I've talked about that where I set it up and I'm like, hey guys, all your traffic skiing logged, so if you don't want me knowing you're looking at it, don't look at it.

[00:31:26] **tim:** You did.

[00:31:26] **tim:** Yeah.

[00:31:34] **carol:** Within an hour I was like, why'd you go look at that?

[00:31:36] **carol:** You didn't think I was gonna know?

[00:31:38] **carol:** Like, let's talk about safe Internet usage or you don't get the Internet.

[00:31:42] **carol:** Like, let's do things safely.

[00:31:43] **tim:** Mhm.

[00:31:45] **carol:** So.

[00:31:47] **adam:** This was probably before they had phones,

[00:31:49] **carol:** Oh no, they had phones, but they're entire.

[00:31:50] **adam:** smartphones.

[00:31:51] **carol:** Yeah, their entire.

[00:31:52] **carol:** All your networks captured.

[00:31:54] **carol:** So they were on Wi-Fi.

[00:31:56] **adam:** Oh, uh, yeah.

[00:31:56] **adam:** See they weren't smart enough to just turn the Wi-Fi off and do it over the cell signal.

[00:31:58] **tim:** Yeah.

[00:31:59] **carol:** Yeah,

[00:31:59] **tim:** Or use a, or use a local VPN on their phone.

[00:32:05] **adam:** What a bunch of devious deviants we are.

[00:32:07] **tim:** Mhm.

[00:32:08] **tim:** Yeah.

[00:32:08] **tim:** My, my kids figured that out real fast.

[00:32:11] **adam:** That you're a devious deviant.

[00:32:13] **tim:** No how to use a VPN

[00:32:15] **carol:** Workarounds.

[00:32:16] **carol:** Workarounds.

[00:32:16] **tim:** Workarounds.

[00:32:16] **adam:** Yeah.

[00:32:16] **carol:** Um.

[00:32:18] **adam:** Oh yeah.

[00:32:18] **carol:** Mhm.

[00:32:19] **adam:** All right, uh, Tim, why don't you move uh, on to your question.

[00:32:20] **carol:** Hey Tim, you want to do yours?

[00:32:22] **tim:** Yeah.

## [00:32:23] When the Model Does the Job

[00:32:23] **tim:** So this one's also from spiffytech Brian.

[00:32:27] **tim:** He says what's y'all's emotional relationship with using AI for work?

[00:32:32] **tim:** It's impacting my confidence, my ability to self reflect on my strengths and weaknesses and my sense of whether I'm even doing a good job.

[00:32:39] **tim:** I don't do the job anymore.

[00:32:41] **tim:** I just tell Claude to do it and hope I can tell if it's right.

[00:32:43] **adam:** Sa.

[00:32:46] **tim:** Yeah, I feel this one that's um.

[00:32:48] **adam:** Mhm.

[00:32:48] **tim:** I said this before the.

[00:32:49] **carol:** We're all nodding.

[00:32:50] **carol:** We're all nodding.

[00:32:50] **tim:** Yeah,

[00:32:50] **carol:** Yes.

[00:32:51] **carol:** Just so.

[00:32:52] **tim:** I said this before the show that I would have been on here.

[00:32:54] **tim:** I was thinking today because you know, real talk guy's been struggling with AI.

[00:32:56] **carol:** Mhm

[00:32:59] **tim:** I mean he really is.

[00:33:01] **tim:** He's got a love hate relationship with it.

[00:33:03] **tim:** And I think the reason is like throughout his career he's always been an individual contributor.

[00:33:09] **tim:** it's just my theory maybe, you know, well I'll let him get on the show next, next time and he can argue, fight me for it.

[00:33:15] **tim:** He'll beat me up because he's bigger.

[00:33:15] **adam:** Mhm.

[00:33:15] **carol:** mhm.

[00:33:16] **tim:** But anyway it's like I've been an individual contributor but mostly I've been like a coding manager.

[00:33:24] **tim:** And so for me my roach relationship with like having an AI do the code versus like me giving it to a team

[00:33:33] **tim:** is about the same.

[00:33:34] **carol:** Mhm mhm.

[00:33:34] **tim:** Emotionally, it's the same.

[00:33:35] **adam:** Right.

[00:33:35] **tim:** I'm not saying the quality is the same.

[00:33:37] **tim:** I'm not saying the output's the same.

[00:33:39] **tim:** I'm just saying that same level of disconnect of being able to say, here's what we're doing, here's where we want to get it done, here's the goals, let's work toward it and let me check in on you every once in a while, make sure everything's kind of, we're staying on track.

[00:33:55] **tim:** That's kind of been my career.

[00:33:55] **adam:** Yeah.

[00:33:58] **adam:** The.

[00:33:59] **tim:** Um, and that's kind of like now I'm doing that directly to a, to LLMs And I don't really feel emotionally distanced from that.

[00:34:09] **tim:** It's not that big of a difference from what I was doing before with humans.

[00:34:13] **adam:** There was a big emotional hurdle that I had to get over.

[00:34:15] **carol:** Mhm mhm.

[00:34:16] **adam:** Not even like as an engineering manager.

[00:34:18] **adam:** I'm talking like somewhat early on in my career, uh, where I started to move up into like,

[00:34:26] **adam:** not leadership, but you know what I'm talking about, like sort of technical leadership.

[00:34:29] **tim:** Yeah.

[00:34:30] **adam:** Right.

[00:34:30] **adam:** Like uh, I guess to probably guess technical leadership is the, the best way to describe it but like you know, kind of guiding the team on technology decisions.

[00:34:39] **adam:** And we all, I'm sure, have the way that we would do it and watching somebody else do it in a way that it's not exactly how you would do it gives me the feels.

[00:34:49] **adam:** Right.

[00:34:49] **adam:** It gives me the upset and my tum tum.

[00:34:50] **tim:** Mhm.

[00:34:53] **adam:** And you know, I, I think that that is what Ben is feeling working with an LLM.

[00:34:53] **carol:** Mhm mhm.

[00:34:59] **adam:** If we're, if this is just going to be the, the throw Ben under the bus question.

[00:35:02] **tim:** Or Brian.

[00:35:03] **tim:** Brian's feeling the same way.

[00:35:03] **adam:** Um,

[00:35:05] **adam:** sure.

[00:35:05] **adam:** But yeah, I mean the,

[00:35:08] **adam:** it hurts to watch somebody do it differently than you, but it's I think like we've talked about Carol being a force multiplier at her job recently.

[00:35:18] **adam:** you know, like

[00:35:20] **adam:** it's something you have to give up in order to get more in return.

[00:35:23] **adam:** Right.

[00:35:24] **adam:** And it, it's, it's a hard lesson to learn.

[00:35:24] **tim:** Yeah,

[00:35:26] **adam:** It's hard to, to get over those emotions.

[00:35:30] **carol:** Yeah.

[00:35:30] **carol:** And the other thing I'm seeing too are the people who are getting discouraged by it because they're losing their opportunity to learn.

[00:35:39] **carol:** So instead of getting to learn from solving the problem from creating the new feature, from doing that work, from writing the code and going, oh, like this is how you make that work.

[00:35:39] **adam:** Mhm.

[00:35:40] **tim:** Mhm.

[00:35:47] **adam:** Mhm.

[00:35:50] **carol:** It's just, it's almost like a task rabbit, right?

[00:35:53] **carol:** You're just a senior engineer being tasked to just go do things that you're just tasking off to someone else.

[00:36:00] **carol:** And for some people that's great, but for the people who are like you said, like, I think Ben is who does love learning and loves like getting that aha moment of how did this get there?

[00:36:11] **carol:** How did we like accomplish this then?

[00:36:14] **carol:** Those people are the ones I see struggling right now.

[00:36:17] **tim:** Yeah.

[00:36:19] **tim:** Yeah.

[00:36:19] **adam:** uh, before we move on, while we're throwing Ben under the bus, I want to go back to my question, the very first question, which was uh, you know, interactions with uh, beings.

[00:36:23] **tim:** Okay.

[00:36:26] **adam:** Are we going to start talking to them like we're talking to the AI bots?

[00:36:28] **adam:** I don't think Ben has to worry about that because he doesn't people.

[00:36:31] **carol:** No, he doesn't people, he doesn't respond to messages.

[00:36:34] **carol:** He's not inbox zero.

[00:36:34] **tim:** No,

[00:36:35] **adam:** So.

[00:36:36] **tim:** no,

[00:36:38] **tim:** I, uh, will say the other emotional thing.

[00:36:39] **tim:** It's like, and I think I mentioned this before, I feel like my AI is better than everyone else's.

[00:36:45] **adam:** Mm.

[00:36:45] **adam:** Mhm.

[00:36:47] **tim:** my own little Tamagotchi pet that I've fed a, uh, special diet.

[00:36:50] **tim:** I just, it's like, people are like, let me ask my Claude And I'm like, I start typing, I'm like, no, let me ask mine first because I'm probably going to get a better answer than you.

[00:36:52] **carol:** Mhm,

[00:36:55] **adam:** Mine's better.

[00:36:59] **adam:** Yeah.

[00:37:00] **adam:** So let's burn twice as many, uh,

[00:37:01] **tim:** Yeah, exactly.

[00:37:02] **tim:** Let's all, let's all burn tokens on this and get rid of some water.

[00:37:02] **adam:** twice as much water.

[00:37:07] **tim:** So yeah, it is weird.

[00:37:09] **tim:** It is really weird.

[00:37:10] **tim:** Kind of this emotional relationship.

[00:37:11] **tim:** Particularly if you're like a

[00:37:13] **carol:** Mhm,

[00:37:14] **tim:** person who feels like they're a code craftsman.

[00:37:17] **tim:** Right.

[00:37:17] **tim:** And that's been your whole emotional stake of.

[00:37:20] **tim:** It's like, you know, I understand the code, I reflect on the code.

[00:37:24] **tim:** I mean, I understand it.

[00:37:26] **tim:** So you know, I'm going to struggle with it and then I'm going to come up with an answer versus like, you know, someone who, like me who's like, you know, a manager is like, I just want to get this done by the deadline.

[00:37:29] **adam:** Mhm.

[00:37:34] **carol:** Mhm, mhm.

[00:37:35] **tim:** um, want to make sure it works and let's just push through.

[00:37:39] **tim:** Um, it's a different level of emotionality

[00:37:44] **tim:** and uh, attachment to the actual code.

[00:37:47] **adam:** When I think about my emotional response to LLMs,

[00:37:51] **adam:** for me, I think.

[00:37:53] **adam:** So maybe it's worth mentioning that like we're recording this, right.

[00:37:57] **adam:** I don't think it's even been a full week since there was this huge blow up, you know, another round of people quitting Anthropic and like a bunch of whistleblowers at both Anthropic and AI and OpenAI, uh, saying like, you know, everybody is saying we need to slow down and pace the frontier of the development, but nobody's willing to be the first one to do it.

[00:38:04] **tim:** Mhm.

[00:38:17] **adam:** They're like, well, but if we do it and nobody else does, then we're screwed.

[00:38:20] **adam:** And it.

[00:38:20] **tim:** Right.

[00:38:21] **tim:** And uh, technically it's illegal for if all the companies got together and said, hey, let's all slow down.

[00:38:21] **carol:** Right.

[00:38:25] **tim:** That's you colluding.

[00:38:25] **adam:** Right,

[00:38:26] **tim:** You can't do that.

[00:38:27] **adam:** right.

[00:38:29] **adam:** So, but I, I mentioned that because um, you know, for me thinking about the, my emotional relationship to using LLMs for my work,

[00:38:31] **carol:** Mhm,

[00:38:38] **adam:** I don't feel like this is a good way

[00:38:44] **adam:** long term to get our work done.

[00:38:46] **adam:** It does appear to be reasonably good at doing the job today and it does certainly appear to be getting better on like a weekly basis or at least a monthly basis.

[00:38:50] **carol:** Mhm.

[00:38:58] **adam:** But

[00:39:00] **adam:** it is unclear at best and bad at worst.

[00:39:05] **adam:** what we're getting in exchange for this work being done.

[00:39:09] **adam:** Right.

[00:39:09] **adam:** We're talking, we were just joking about the water costs and uh, additional, What is it?

[00:39:09] **tim:** Now.

[00:39:14] **adam:** They're, they're using like propane, uh, powered generators or whatever to run these data centers because there's not enough electricity on the grid.

[00:39:21] **adam:** And you know, all these other just like little, it's like death by a thousand paper cuts.

[00:39:21] **tim:** Mhm.

[00:39:25] **carol:** Mhm.

[00:39:26] **adam:** Um, of all the negativity that's caused by the LLM industry.

[00:39:30] **carol:** Mhm.

[00:39:32] **adam:** And

[00:39:33] **adam:** there's like an element of FOMO right.

[00:39:36] **adam:** Like if I, if I choose not to use LLMs to do my work, then

[00:39:43] **adam:** I'm worried that I won't be getting as much done as I need to.

[00:39:48] **adam:** And

[00:39:50] **adam:** at the same time I worry that by continuing to use it I am,

[00:39:55] **adam:** uh, like my skills are atrophying.

[00:39:57] **adam:** Right.

[00:39:57] **adam:** Like it's a muscle I'm not using It's a very complicated relationship.

[00:39:57] **tim:** 100%.

[00:39:59] **carol:** M.

[00:39:59] **carol:** Yeah, I get that.

[00:39:59] **tim:** Yep.

[00:39:59] **tim:** Mhm.

[00:40:02] **tim:** Yeah.

[00:40:02] **tim:** I mean

## [00:40:05] Assembly Lines and Good Taste

[00:40:05] **tim:** my

[00:40:06] **tim:** present take on the future of this is that coding is going to become less and less attractive as a field and more of a kind of like an assembly line kind of worker kind of job over time.

[00:40:11] **carol:** Mhm, mhm

[00:40:19] **adam:** Mhm,

[00:40:19] **tim:** The whole issues with water resources and energy and all that, I think we're pretty good at figuring out problems.

[00:40:26] **tim:** And right now the AI we're using today is the absolute AI will ever use in the future.

[00:40:32] **tim:** Right.

[00:40:32] **adam:** Mhm.

[00:40:33] **tim:** So it's only going to get better, it's only going to get more efficient.

[00:40:35] **tim:** Things that you used to have to run on really, really beefy machines, now that, you know, making them more efficient, you can run them on a local machine, that's just going to continue to compound.

[00:40:43] **carol:** sa.

[00:40:45] **tim:** But I just think, uh, the job itself in the next 20 years is going to be a lot less attractive and like people coming into the workforce are going to go into different areas because it's just, I don't want to be another cog in the corporate machine of just reviewing what AI did.

[00:40:53] **carol:** Mhm.

[00:41:03] **adam:** So what I'm hearing, and tell me if you, if I'm wrong, is that,

[00:41:08] **adam:** you know, at some point in the future we don't even have to put a pin in the timeline, but at some point in the future we're expecting that the job of coding is 100% outsourced to agents and everybody left in the field is a, an engineering manager of sorts.

[00:41:25] **tim:** Yeah, just a reviewer.

[00:41:27] **carol:** Yeah,

[00:41:27] **tim:** Like a person who, uh, a person who sets the goals and you know, people that make sure the goals are met.

[00:41:28] **adam:** Right?

[00:41:32] **tim:** And that's, yeah, that's kind of thinking where I was going.

[00:41:34] **adam:** Yeah,

[00:41:35] **carol:** It's sad to think of.

[00:41:36] **tim:** Yeah.

[00:41:37] **carol:** Yeah, no, it's, it's really sad to think about that.

[00:41:37] **adam:** but,

[00:41:39] **carol:** But, but that's like where I am too.

[00:41:40] **carol:** Like I feel like, uh, manager right now.

[00:41:43] **carol:** They manage the delivery of the product, like some timeline, some budgets, and they manage the people, right?

[00:41:47] **adam:** Mhm.

[00:41:50] **carol:** They're like, am I doing my job?

[00:41:53] **carol:** They could do that exact same thing for an agent, like for something running the code, like, did you deliver it?

[00:41:59] **carol:** If not, send it back, not approved and say, do better.

[00:42:03] **carol:** And now is that cheaper than my salary?

[00:42:06] **adam:** Right.

[00:42:07] **tim:** Yep,

[00:42:07] **carol:** Mhm.

[00:42:08] **adam:** And they can work 24, 7.

[00:42:09] **adam:** They don't need breaks, they don't, they don't get bored.

[00:42:14] **tim:** Yep.

[00:42:14] **tim:** I mean, I'm kind of building that pipeline now.

[00:42:18] **adam:** Yeah,

[00:42:19] **tim:** I feel bad about it.

[00:42:19] **tim:** I'm like, at what point are they going to realize, okay, you built, you guys all built everything.

[00:42:23] **tim:** What do we need you.

[00:42:24] **tim:** You other people for?

[00:42:26] **tim:** So it's like, yeah,

[00:42:28] **carol:** Sa.

[00:42:28] **adam:** Yeah.

[00:42:29] **tim:** or, or if that's your job, is that even what you want to do?

[00:42:29] **adam:** I mean.

[00:42:31] **tim:** Like you, you know, you could have a software company of like five people that is just managing a whole bunch of agents and just like, okay,

[00:42:40] **tim:** we got an accounting person to make sure the money's coming in.

[00:42:42] **tim:** We got a people product.

[00:42:44] **tim:** Do the vision.

[00:42:45] **tim:** You got people that just double check that things work and some infrastructure people for deployment.

[00:42:51] **tim:** Yeah, I don't know.

[00:42:52] **carol:** Yeah.

[00:42:53] **carol:** One of the things that I've said at work a few times now to people who aren't using AI, which is very sad to say, but like, I kind of keep reiterating that AI isn't going to replace you.

[00:42:54] **adam:** Mhm,

[00:43:01] **tim:** Mm,

[00:43:06] **carol:** Like, that's not going to take away your job.

[00:43:08] **carol:** What's going to take away your job right now is someone willing to use AI to do your job because they're going to be more efficient, they're going to get it done faster, the job's going to be more accurate.

[00:43:15] **tim:** Mhm.

[00:43:15] **adam:** Mhm,

[00:43:20] **carol:** And now you're not going to be able to achieve that standard of what is the minimum, um, expectation for the job.

[00:43:27] **carol:** And now you're not going to meet the criteria to stay employed.

[00:43:30] **carol:** So either you adopt or you move on.

[00:43:31] **tim:** Mhm,

[00:43:32] **carol:** And it's awful to say that, but using AI is automating things.

[00:43:36] **adam:** Mhm.

[00:43:37] **carol:** It's making your day faster, it's trying to get tasks done quicker.

[00:43:40] **carol:** And if you're not using it, you kind of are, ah, getting behind.

[00:43:44] **carol:** You know, we all went to computers, we all moved away from faxes.

[00:43:49] **carol:** There are things that have happened over time that were big technological like impacts and this is just one of those that we have to adapt to.

[00:43:52] **tim:** Sa mhm.

[00:43:58] **adam:** So I, you're not wrong.

[00:44:01] **adam:** I 100% agree.

[00:44:02] **adam:** But I also see that it doesn't just stop there.

[00:44:05] **adam:** Right.

[00:44:05] **adam:** Like, so somebody who is willing to use AI and is good at it could take my job as the uh, intro coder.

[00:44:10] **carol:** Sa.

[00:44:13] **adam:** And eventually, you know, somebody takes that person's job because they can manage five agents.

[00:44:18] **adam:** And then somebody takes that person's job because they can manage a fleet of agents.

[00:44:22] **adam:** And you know, eventually I think all that's going to be left is

[00:44:27] **adam:** the job of having taste.

[00:44:30] **adam:** Right.

[00:44:30] **tim:** Yeah.

[00:44:31] **adam:** Uh, I'm not sure.

[00:44:32] **adam:** It feels like at this point that that's kind of the, the last frontier of things that can't be

[00:44:40] **adam:** trained into a model.

[00:44:42] **adam:** Right.

[00:44:42] **tim:** M.

[00:44:42] **carol:** Mhm.

[00:44:42] **tim:** Yeah.

[00:44:42] **adam:** Everything else about our job is effectively just the application of taste.

[00:44:47] **tim:** Yeah.

[00:44:49] **tim:** We all have to, you know, either get out of it or become Rick Rubin, the American music producer.

[00:44:54] **tim:** You know who he is?

[00:44:56] **adam:** Yeah.

[00:44:56] **tim:** He's a co founder of, he's a co founder of Def Jam Recordings.

[00:44:57] **adam:** Is produced like every album.

[00:44:57] **carol:** No.

[00:45:00] **carol:** Sam.

[00:45:00] **tim:** And he, he's not a musician.

[00:45:03] **tim:** I mean, he can't play an instrument.

[00:45:05] **tim:** He doesn't know anything about music theory.

[00:45:06] **adam:** Mm,

[00:45:07] **carol:** Mhm.

[00:45:07] **tim:** He just has really good taste in music.

[00:45:08] **tim:** He just like can hear something and go, yeah, that's good.

[00:45:11] **tim:** And this made him super rich because he knows how to produce records that are awesome and like squash records that aren't.

[00:45:20] **tim:** And that's, you know, that's his skill.

[00:45:22] **tim:** He just has a good taste and that's kind of a.

[00:45:23] **adam:** Mhm.

[00:45:25] **tim:** That's a really hard.

[00:45:25] **tim:** I mean, how do you go for school for that?

[00:45:27] **carol:** Mhm.

[00:45:27] **tim:** I mean, how do you get a degree in that good taste?

[00:45:30] **tim:** I don't know.

[00:45:31] **tim:** It's uh, it's weird.

[00:45:34] **adam:** Would be nice.

## [00:45:35] Patreon

[00:45:35] **adam:** All right, well, let's wrap it up there.

[00:45:35] **carol:** Mhm.

[00:45:37] **adam:** Uh, this episode of Working Code was brought to you by throwing the person who did not attend the meeting under the bus, Ben.

[00:45:43] **adam:** and listeners like you.

[00:45:44] **adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:45:51] **adam:** Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them.

[00:45:53] **tim:** Sa.

[00:45:55] **carol:** Mhm.

[00:45:56] **adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

## [00:46:00] Thanks For Listening!

[00:46:00] **adam:** Uh, and I'll also use this opportunity to say, send us more questions.

[00:46:03] **adam:** We enjoy doing these shows and, and me personally, the, the more AI has taken my job away from me, the more interested I find myself getting in the philosophy of, uh, of AI stuff and just of like computing in general.

[00:46:16] **carol:** Mhm.

[00:46:17] **adam:** So, uh, that's, I, I find the questions, uh, a fun exercise.

[00:46:21] **adam:** so you can send us questions to workingcodepod@gmail.com.

[00:46:24] **adam:** you can come on our Discord, which is, workingcode.dev/discord.

[00:46:27] **adam:** Uh, and those are two great avenues to send us questions.

[00:46:31] **adam:** If uh, you'd like your question answered, just send it on in.

[00:46:31] **tim:** Yep.

[00:46:31] **carol:** Mhm, mhm.

[00:46:33] **tim:** Hit us up.

[00:46:34] **adam:** we are going to go record the after show which is a perk for our patrons.

[00:46:38] **adam:** We're going to keep the mics on after the outro music plays and just talk about whatever random stuff comes to our heads.

[00:46:38] **tim:** Mhm.

[00:46:43] **adam:** I'm going to tell a story this week.

[00:46:44] **adam:** This week on the after show, um, I almost bitched out a customer.

[00:46:45] **tim:** Oh.

[00:46:49] **adam:** Ah, for.

[00:46:51] **adam:** For bad re.

[00:46:52] **adam:** Like.

[00:46:52] **adam:** And, and I would have been very much in the wrong, not just because of bitching out a customer, but because it was based on.

[00:46:58] **adam:** It was based on bad assumptions.

[00:46:59] **tim:** Mhm.

[00:47:00] **adam:** and so, uh, I'll tell that story.

[00:47:02] **adam:** We'll see what else happens.

[00:47:04] **adam:** If, uh, you want access to the after show and early access to new episodes when they first come out, then you can go to patreon.com/workingcodepod and sign up to become a patron of the show.

[00:47:09] **carol:** Mhm.

[00:47:13] **adam:** We'd love to have you that's going to do it for us this week.

[00:47:16] **adam:** We'll catch you again next week.

[00:47:17] **adam:** And until then,

[00:47:18] **tim:** Hey listen, the fact that you listen to workingcode.dev uh, means that you have better taste than Rick Rubin.

[00:47:23] **tim:** And your heart matters.
