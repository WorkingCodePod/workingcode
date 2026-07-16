---
title: "267: Prove You Are Human"
description: "Tim is trying to hire remote developers, but the interviews have started to feel like one long CAPTCHA. This week the hosts discuss the state of remote developer interviews in the AI era."
date: 2026-07-16
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/a4117-0fd7-457b-91cb-4f75bb3c52bd"></script>
<div class="redcirclePlayer-a4117-0fd7-457b-91cb-4f75bb3c52bd"></div>

Tim is trying to hire remote developers, but the interviews have started to feel like one long CAPTCHA. Before he can decide who's right for the job, he has to figure out whether he's interviewing the candidate or ChatGPT. This week the hosts discuss the state of remote developer interviews in the AI era.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Mostly Technical #29: “Super Epic Crazy”](https://mostlytechnical.com/episodes/29-super-epic-crazy-with-adam-wathan) — the source of the cover-letter story about most applicants missing simple instructions
- [Roberto Serrano on AI fraud at Brown University](https://english.elpais.com/education/2026-06-28/ai-fraud-at-brown-university-academic-integrity-is-at-risk.html) — the course whose take-home exams triggered the in-class-final story

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/267-prove-you-are-human.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** I think the question that they asked me was like, tell me about a time in which, someone disagreed with you and then you changed their mind.

[00:00:07] **Ben:** And I was like, oh, bro, I don't think I've ever changed anyone's mind on anything.

[00:00:13] **Adam:** And did you get that job, Ben?

[00:00:15] **Ben:** No, I did not.

[00:00:37] **Adam:** Okay, here we go.

[00:00:38] **Adam:** It is show number 267.

[00:00:39] **Adam:** And on today's show we are going to talk about the value of strife.

[00:00:41] **Adam:** Or I mean, uh, the pitfalls of hiring remote developers.

[00:00:45] **Adam:** Sorry, it almost snuck in a third time.

[00:00:48] **Ben:** Third time's a charm.

[00:00:48] **Adam:** Uh,

[00:00:50] **Adam:** but first, as usual, we'll start with the triumphs and fails Carol's not able to be with us tonight.

[00:00:54] **Tim:** Did you just say just the gentleman and Tim?

[00:00:55] **Adam:** She's got some doggo issues going on.

[00:00:57] **Adam:** So.

[00:00:58] **Adam:** Just the gentleman.

[00:00:58] **Tim:** That sounds about right.

[00:00:59] **Adam:** And Tim, I'm going to come to you first.

[00:01:00] **Adam:** What's going on, my friend?

[00:01:01] **Tim:** Oh,

[00:01:04] **Tim:** punctuations.

[00:01:06] **Tim:** Punctuation is important.

[00:01:06] **Adam:** Just a gentleman.

[00:01:07] **Adam:** Just a gentleman, comma.

[00:01:08] **Adam:** And Tim, I'm coming to you first.

[00:01:11] **Adam:** Em Dash,

[00:01:14] **Adam:** let's delve into your uh, your triumph or fail here.

[00:01:14] **Tim:** Um,

## [00:01:17] Tim's Triumph

[00:01:17] **Tim:** yeah, so I'm gonna go with the.

[00:01:17] **Ben:** Mhm.

[00:01:19] **Tim:** Well, we'll see if it's a triumph.

[00:01:21] **Tim:** I don't know, I might be replacing myself here, but I've been working a past couple weeks on building an internal company skill for Claude That's basically an agentic loop where you just feed it a ticket and it does the intake of the ticket, looks for customer information, handles correspondence with the customers till it feels it has all the information it needs to work on the ticket and then Pete

[00:01:24] **Adam:** Hmm.

[00:01:43] **Ben:** M.

[00:01:44] **Ben:** It handles correspondence with the customers.

[00:01:46] **Tim:** and then handles, handles the.

[00:01:48] **Tim:** It basically ends up from beginning.

[00:01:50] **Tim:** I mean there is a little human action interaction there but at the end of it, after it does its full intake, it will be a full PR ready for review.

[00:01:54] **Adam:** Mhm.

[00:01:58] **Ben:** Mhm.

[00:01:59] **Adam:** So hang on.

[00:02:00] **Adam:** When you say it handles correspondence with the customers, is this like it's leaving comments on a Jira ticket?

[00:02:04] **Tim:** Yep.

[00:02:05] **Adam:** And what if the customer takes three days to reply?

[00:02:07] **Tim:** It just waits three days.

[00:02:10] **Adam:** So yeah, uh, I mean, how do you, how are you managing that?

[00:02:12] **Adam:** Like does it just every once a day or something check in on that ticket?

[00:02:16] **Tim:** It, it runs throughout the day.

[00:02:18] **Tim:** So it's idempotent.

[00:02:19] **Tim:** So it just, it just runs throughout the day and gets to sees where it, where it can move the ball along.

[00:02:19] **Ben:** Mhm,

[00:02:23] **Tim:** Basically treating Jira like a state machine.

[00:02:26] **Adam:** Okay.

[00:02:27] **Tim:** So I, I, I, I m manually tested.

[00:02:28] **Adam:** It's an interesting thought.

[00:02:30] **Tim:** So we had a developer who was out in his job where he manages one like one particular client and he was out.

[00:02:36] **Tim:** So I told him, I'm like, hey, while you're going, I'm going to be doing this experimenting with your customer.

[00:02:40] **Adam:** Mhm.

[00:02:42] **Tim:** And Um, so it post, and like it four post or these five of questions them got to PRs.

[00:02:44] **Tim:** their customer.

[00:02:45] **Tim:** And I haven't I heard was quite from the developer surprised if it the PRs ended are up any like quality But several tickets just got closed after the questions because the questions were good enough.

[00:02:52] **Tim:** The person was like, oh yeah, you're right, this, none of this makes any sense.

[00:02:54] **Tim:** I just closed this request.

[00:02:56] **Adam:** Nice.

[00:02:56] **Ben:** Mhm.

[00:03:01] **Tim:** um, the customer was like, wow, Tim's really asking a lot of good questions these days.

[00:03:08] **Adam:** The quality of the questions has gone way up.

[00:03:09] **Tim:** Oh yeah, it has.

[00:03:10] **Tim:** And the punctuation and grammar, what happened?

[00:03:15] **Adam:** Yeah, you got to put that in.

[00:03:15] **Tim:** So.

[00:03:16] **Adam:** Your, in your prompt is like, you know, every now and then misspell a word or skip a word.

[00:03:19] **Tim:** Yeah, yeah, yeah.

[00:03:22] **Tim:** Spelled the wrong so.

[00:03:24] **Tim:** But yeah, we'll see.

[00:03:26] **Tim:** I'm curious to kind of see how it goes.

[00:03:29] **Tim:** it's scary if it works, honestly.

[00:03:31] **Ben:** So I just, I'm a little bit curious about the,

[00:03:35] **Ben:** uh, path from customer requests to PR Meaning the degree, uh, of tension has always existed in product development where customers want stuff and you go to your product team and you're like, here's what customer wanted.

[00:03:48] **Ben:** And, and product team says, that's ridiculous.

[00:03:51] **Ben:** We're not putting that into the application.

[00:03:51] **Adam:** Mhm.

[00:03:54] **Ben:** Uh, like, how do you navigate that tension in this loop?

[00:03:54] **Tim:** So I'm not going to go Do a PR on like

[00:03:58] **Tim:** Oh, I haven't got there yet.

[00:03:59] **Ben:** Yeah,

[00:03:59] **Adam:** I.

[00:04:00] **Adam:** It was a.

[00:04:01] **Adam:** There's the first thing that came to my mind as well is like the customer is not always right when it comes to software.

[00:04:07] **Tim:** Right.

[00:04:08] **Tim:** Well, I mean a lot of these that we're dealing with, they're, they're bugs.

[00:04:10] **Tim:** Right.

[00:04:11] **Tim:** So that they're bug and something broke and they want to know why or they want to maybe make a slight change.

[00:04:11] **Adam:** Mhm.

[00:04:17] **Tim:** It does flag it.

[00:04:18] **Tim:** If this is a feature obvious feature request that it's like that's going to get flagged for architectural review.

[00:04:19] **Adam:** M.

[00:04:23] **Adam:** Okay.

[00:04:24] **Ben:** Gotcha.

[00:04:25] **Ben:** Okay.

[00:04:26] **Tim:** hey, fix everything in my system or you know, make it do 10 things it can't do now those aren't.

[00:04:33] **Tim:** We got to charge for that.

[00:04:35] **Adam:** Right.

[00:04:35] **Ben:** I'd love it if my teammates got Rickrolled when they clicked on this link.

[00:04:38] **Tim:** Exactly.

[00:04:40] **Tim:** Hey, let me do that for you.

[00:04:42] **Tim:** Which version of Rickroll would you like?

[00:04:43] **Adam:** What a great idea.

[00:04:44] **Tim:** What a great idea.

[00:04:46] **Ben:** uh, I'm curious about the infrastructure for it.

[00:04:48] **Ben:** Is this just running on your desktop or you have it on a VPS or what's the.

[00:04:52] **Tim:** It'd be running on the desktop of each developer who's, you know.

[00:04:55] **Ben:** Oh, interesting.

[00:04:57] **Ben:** Oh, so it's running in the voice of the developer it's running for.

[00:04:57] **Tim:** So.

[00:05:00] **Tim:** Right.

[00:05:00] **Tim:** Yeah.

[00:05:01] **Tim:** So there is there is there.

[00:05:01] **Ben:** I see.

[00:05:01] **Ben:** That's why they were like, Tim's making really good points.

[00:05:03] **Tim:** Yeah.

[00:05:04] **Tim:** So there, there's, there's per project rules and those per person rules.

[00:05:07] **Adam:** Mhm,

[00:05:08] **Tim:** Like so if you want to change your voice you can.

[00:05:08] **Ben:** Sa.

[00:05:10] **Tim:** There's a section for you to modify that skill locally.

[00:05:13] **Tim:** So but I mean it, the actual, what's cool is the actual process of coming up with code fix is like it's building red green tests.

[00:05:21] **Adam:** Mhm,

[00:05:21] **Ben:** M.

[00:05:22] **Ben:** Mhm.

[00:05:22] **Tim:** First everything's red and then it builds a test um, using TestBox and it builds the virtual environment.

[00:05:28] **Tim:** Builds the whole thing up and destroys it.

[00:05:31] **Tim:** creates feature branches for it.

[00:05:32] **Tim:** So I don't know.

[00:05:33] **Tim:** It's been two weeks of working on it.

[00:05:34] **Tim:** I just really interested to see how well it actually faces reality because it may fail.

[00:05:39] **Adam:** Mhm,

[00:05:41] **Ben:** This is a really interesting thing, because you say that you're developing a skill for the company and one of the things that I've heard people kind of dance around on various interviews in the last couple of months is this idea that it used to be that every developer sort of had their way of developing.

[00:05:44] **Tim:** Mhm.

[00:05:58] **Ben:** They could bring their own editors and they could bring their own.

[00:05:59] **Adam:** Mhm.

[00:06:00] **Ben:** You know how, this is how I run ColdFusion on my machine and this is how I compile my CSS.

[00:06:05] **Ben:** And then DevOps became a thing and then the DevOps teams were like, no, that's not actually how you do any of it.

[00:06:10] **Ben:** It all runs in containers now.

[00:06:12] **Ben:** You have no choice except like maybe some wiggle room and certain areas and like we give you the dashboards for all the metrics that you can plug into and like teams aren't reinventing their, you know, error rate detection kinds of stuff that's just like become standardized.

[00:06:13] **Tim:** Sa.

[00:06:20] **Adam:** Mhm.

[00:06:27] **Ben:** And I wonder, uh, how much of that kind of path is the AI skill type of stuff heading on like if, if Tim M.

[00:06:40] **Ben:** As an AI expert, as an AI native chap, uh, you know, is building skills for other people to use, then people don't necessarily have to know how those skills work.

[00:06:41] **Adam:** Mhm.

[00:06:41] **Tim:** So.

[00:06:43] **Tim:** Mhm.

[00:06:49] **Ben:** They just know how to invoke them.

[00:06:51] **Ben:** In the same way that I don't know how Kubernetes works, but I just know that if I deploy an image, it eventually becomes a running container somewhere.

[00:06:59] **Tim:** There's a question there.

[00:07:00] **Adam:** Mhm.

[00:07:00] **Tim:** But I mean that is the plan.

[00:07:01] **Tim:** That.

[00:07:01] **Tim:** But I just want a skill you put in and you type ticket intake and the ticket number and it does its thing.

[00:07:07] **Tim:** Mhm.

[00:07:08] **Ben:** Right.

[00:07:08] **Ben:** Well, I guess, I guess, you know, so much of the public conversation seems to be about skill development and you know, we've talked about Ben Pocock and, and all kinds of other people talking about skill development and iterating on, um, what skills are good and /grill-me and.

[00:07:24] **Adam:** Um, did you say Ben Pocock?

[00:07:24] **Ben:** And

[00:07:27] **Ben:** yes.

[00:07:27] **Ben:** Was that not his.

[00:07:28] **Ben:** That is not his name.

[00:07:29] **Adam:** His name is Matt Pocock.

[00:07:29] **Ben:** Matt.

[00:07:30] **Ben:** Matt.

[00:07:31] **Ben:** Sorry,

[00:07:33] **Ben:** I'm not good with names.

[00:07:33] **Adam:** Ascribing.

[00:07:34] **Adam:** Ascribing something to yourself.

[00:07:37] **Ben:** You know how much of that is like early days where we were still talking about uh, Chef and Puppet and, and like, does all that just go away eventually?

[00:07:43] **Tim:** Mhm.

[00:07:46] **Ben:** And there are a set of like, blessed standards for how we do this stuff and people don't have to worry about what's the right type of skill to get this type of work done.

[00:07:55] **Ben:** I uh, like, you know, it's not an answer here.

[00:07:57] **Ben:** I guess I'm just thinking out loud.

[00:07:58] **Tim:** I mean, yeah, I mean it's definitely all going to change the next six months.

[00:08:01] **Tim:** So anyway, so that's what I'm working on.

[00:08:04] **Tim:** I'll call it maybe a triumph.

[00:08:06] **Tim:** But how about you Adam?

## [00:08:07] Adam's Fail

[00:08:07] **Tim:** What you got?

[00:08:08] **Adam:** Um, I guess I'm going to call this a fail.

[00:08:10] **Adam:** so I think I mentioned previously that I have a trip plan to go up to Niagara Falls to go skydiving this weekend.

[00:08:14] **Tim:** Sa.

[00:08:17] **Adam:** And I've canceled that trip for myself at least.

[00:08:20] **Adam:** because of the weather.

[00:08:21] **Adam:** The, the forecast just looks horrendous up there for this weekend.

[00:08:24] **Ben:** Rain or heat.

[00:08:25] **Adam:** Yes.

[00:08:26] **Adam:** Um, and I mean if it was just heat, I would go anyway.

[00:08:27] **Tim:** Mhm.

[00:08:30] **Adam:** but the, it's the rain that's killing it.

[00:08:32] **Adam:** You can, you can jump in heat, you can't really jump in rain.

[00:08:32] **Ben:** Gotcha.

[00:08:35] **Adam:** Um, and it's a 6ish hour drive each way.

[00:08:38] **Adam:** And um, you know, so by canceling it, I skipped the hotel cost, I skipped the eating out for four or five days cost.

[00:08:45] **Adam:** And, and the jumping that I would be doing, I won't be doing.

[00:08:49] **Adam:** But so saving some money.

[00:08:51] **Adam:** But uh, I'm kind of sad that I'm Gonna miss my trip.

[00:08:53] **Adam:** So.

[00:08:54] **Tim:** We gonna jump into Niagara?

[00:08:56] **Tim:** Is that the.

[00:08:57] **Adam:** No.

[00:08:57] **Adam:** Um, but the.

[00:08:58] **Ben:** That'd be pretty cool.

[00:08:58] **Adam:** So what it is is you're really close to Niagara Falls and on the plane ride up to jump altitude, they have special permission to fly around the falls and you actually get to fly into Canadian airspace.

[00:09:07] **Tim:** Mhm.

[00:09:09] **Adam:** You kind of circle the falls, um, and then you go back over to the airport, which is just like a few miles away.

[00:09:15] **Tim:** Where do you jump?

[00:09:16] **Adam:** Over the airport?

[00:09:17] **Adam:** Uh, not, it's not like an international airport.

[00:09:17] **Tim:** Okay.

[00:09:19] **Adam:** It's just like, it's basically like a farm, you know, grass strip Runway sort of situation.

[00:09:21] **Tim:** Yeah,

[00:09:24] **Ben:** I don't think I've ever considered this in my entire life, but I figured you always needed permission to land at an airport, but do you need permission to fly into another country's airspace?

[00:09:35] **Adam:** Yes, absolutely.

[00:09:36] **Adam:** That's sovereign territory.

[00:09:37] **Ben:** Oh,

[00:09:39] **Tim:** It goes all the way up.

[00:09:39] **Ben:** I did not.

[00:09:40] **Tim:** Mhm.

[00:09:40] **Ben:** Yeah, I never thought about that.

[00:09:40] **Adam:** Yeah, yeah.

[00:09:41] **Adam:** So like, like, uh, you know, airlines, right?

[00:09:44] **Adam:** You take Delta and you're flying to Canada or if you were to fly to Russia from, I don't know, Ohio or something, they're going to go over Canada.

[00:09:49] **Tim:** Sa.

[00:09:51] **Adam:** So they have to have permission to go through Canada's airspace.

[00:09:55] **Ben:** Huh.

[00:09:56] **Ben:** Fascinating.

[00:09:57] **Ben:** I had no idea.

[00:09:57] **Adam:** Yeah.

[00:09:58] **Adam:** Yeah.

[00:09:59] **Ben:** Let me ask you a total random question here.

[00:10:01] **Ben:** So you said Niagara, uh, is six hours away.

[00:10:03] **Ben:** Niagara.

[00:10:04] **Adam:** Mm.

[00:10:04] **Adam:** Mhm.

[00:10:04] **Ben:** For me it's like, it's probably like seven hours from where I am.

[00:10:05] **Tim:** Mhm.

[00:10:07] **Adam:** Interesting.

[00:10:07] **Ben:** and I'm.

[00:10:08] **Ben:** I'm curious to get to uh, Ithaca because apparently the.

[00:10:11] **Adam:** Yeah, been there.

[00:10:12] **Ben:** Everyone says, you know, the gorges are beautiful and I keep getting ads.

[00:10:12] **Adam:** It's beautiful.

[00:10:14] **Adam:** Yeah.

[00:10:14] **Adam:** Ithaca is gorgeous.

[00:10:15] **Ben:** Yeah.

[00:10:15] **Adam:** Yeah.

[00:10:16] **Ben:** So Ithaca is about five hours away, I think for me, like five and a half.

[00:10:21] **Adam:** Yeah.

[00:10:21] **Ben:** And uh, five and a half is like beyond the.

[00:10:24] **Ben:** Hey, maybe we should try that this weekend.

[00:10:25] **Tim:** Mhm.

[00:10:26] **Ben:** And that becomes like a, uh.

[00:10:27] **Adam:** Mhm.

[00:10:28] **Ben:** Let's plan this out several months in advance.

[00:10:30] **Adam:** I don't know about months, but yeah,

[00:10:31] **Ben:** What.

[00:10:32] **Ben:** But like, like, you know, like it goes from casual to serious.

[00:10:35] **Adam:** sure, yeah.

[00:10:36] **Ben:** What's.

[00:10:36] **Ben:** What's your road time that kicks it from casual into serious?

[00:10:42] **Adam:** Me personally, probably like eight hours.

[00:10:45] **Adam:** Um,

[00:10:46] **Adam:** I'm, I, I am a fly by the seat of your pants, improvise kind of guy.

[00:10:47] **Ben:** M.

[00:10:48] **Ben:** Oh man,

[00:10:50] **Ben:** you're a be.

[00:10:52] **Adam:** My wife is not my wife.

[00:10:54] **Adam:** It's probably like three hours.

[00:10:56] **Adam:** Um,

[00:10:56] **Ben:** Yeah.

[00:10:56] **Tim:** I'm with you three hours.

[00:10:56] **Ben:** I feel like three hours is casual max.

[00:10:58] **Tim:** Yeah,

[00:10:59] **Ben:** Yeah.

[00:11:00] **Adam:** Nah man, you just, you're just out here living L-I-V-I-N

[00:11:06] **Tim:** That's young man thinking right there.

[00:11:07] **Adam:** That's right.

[00:11:09] **Ben:** That's awesome.

[00:11:09] **Adam:** You Just because you old doesn't mean you have to grow up.

[00:11:12] **Tim:** That's true.

[00:11:12] **Ben:** I was like,

[00:11:13] **Tim:** I know lots of people haven't grown up.

[00:11:15] **Adam:** So just me sitting at home wishing I was skydiving.

[00:11:19] **Adam:** And that's a, that I think that's the real fail is I was originally only planning to work on Tuesday.

[00:11:19] **Ben:** M.

[00:11:23] **Adam:** Thursday.

[00:11:23] **Adam:** I'm sorry, Wednesday.

[00:11:23] **Ben:** Mhm.

[00:11:24] **Adam:** Tuesday.

[00:11:25] **Adam:** Let me try that again.

[00:11:26] **Adam:** Tuesday, Wednesday this week.

[00:11:28] **Adam:** and I was gonna be leaving Thursday morning for the trip, because we just returned from our previous trip on Monday.

[00:11:33] **Adam:** and so I was only into work two, two days this week and now it's going to be four.

[00:11:37] **Adam:** So because I'm here, I might as well work, right?

[00:11:39] **Tim:** Sure.

[00:11:41] **Ben:** They get you.

[00:11:42] **Adam:** Yep.

[00:11:42] **Adam:** Anyway, so that's it for me.

## [00:11:43] Ben's Fail

[00:11:43] **Adam:** How about you, Ben?

[00:11:45] **Ben:** I'm going to go with a failure, which is that I did a clickbait on LinkedIn and I uh, regret it.

[00:11:51] **Ben:** uh, I've been.

[00:11:51] **Ben:** I've been mostly like.

[00:11:53] **Tim:** I didn't uh, clickbait

[00:11:55] **Ben:** I've been mostly not doing a lot of social media at all in, in quite a while, but I still try to at least slightly engage with LinkedIn.

[00:12:02] **Tim:** Mhm.

[00:12:05] **Ben:** Uh, mostly in like a contrarian way these days because.

[00:12:09] **Ben:** Good.

[00:12:09] **Adam:** Well, I just want to jump in and say so you said you did a clickbait.

[00:12:12] **Adam:** Are you talking about like a blog post that you linked on LinkedIn?

[00:12:15] **Ben:** More.

[00:12:15] **Ben:** More like a, uh, more like a clickbaity statement than a, than something I linked to.

[00:12:15] **Adam:** You gave it a clickbait title.

[00:12:21] **Adam:** Okay, so you're just kind of rage baiting, like getting people to engage, leave comments or likes or whatever.

[00:12:25] **Adam:** And.

[00:12:26] **Ben:** It's more.

[00:12:26] **Tim:** He started writing in CFML and then this happened.

[00:12:30] **Adam:** You won't believe number seven.

[00:12:32] **Ben:** Okay, so you know, like, like 90% of LinkedIn.

[00:12:35] **Ben:** I don't know if anyone ever looks at LinkedIn.

[00:12:36] **Ben:** But like 90% of LinkedIn is everybody just talking about how amazing AI is and posting AI generated photos and, and uh, uh, you know, I'm obviously filled with a lot of

[00:12:41] **Adam:** Yeah.

[00:12:47] **Tim:** Rage.

[00:12:48] **Ben:** pause and rage about some of the AI stuff.

[00:12:51] **Ben:** So I, I had posted something like that.

[00:12:53] **Ben:** I'm, I'm blown away by how many people just seem to assume at this point that AI will write better code than them.

[00:13:02] **Ben:** And know, I'm not saying that AI won't write faster code, it will absolutely write faster.

[00:13:03] **Tim:** Mhm.

[00:13:05] **Ben:** But I, I have heard many people on podcasts say I'm just going to ask the AI to do it because it will probably write better code than I will.

[00:13:10] **Adam:** Mhm,

[00:13:13] **Ben:** And that like, it just blows my mind because the way I look at it.

[00:13:17] **Ben:** And uh, many people quickly jumped in to tell me that this is actually not the case, that AI is like an average of everything it's ever seen.

[00:13:24] **Tim:** Mhm.

[00:13:24] **Ben:** And part of what the prompting does is like shifting the window on the average that you're seeing.

[00:13:31] **Ben:** And people just like went crazy and, and were telling me how wrong that was and like how great AI is.

[00:13:37] **Ben:** And like, I just didn't want to engage with any of it.

[00:13:40] **Ben:** And it, and it uh, like I just instantly regretted it the moment anybody responded.

[00:13:40] **Adam:** Mhm,

[00:13:46] **Ben:** And I don't know how people,

[00:13:46] **Adam:** M.

[00:13:46] **Adam:** See that's the feeling that I have as soon as I sign into LinkedIn.

[00:13:51] **Ben:** like, I just don't know how people live that lifestyle where they, they say stuff that's incendiary and get a lot of like people hating on it.

[00:13:59] **Ben:** I know early in the podcast Tim was all about the haters and, and eating that hate to grow and be powerful.

[00:14:05] **Tim:** Mhm.

[00:14:06] **Ben:** Um, but I don't know, I just found it super exhausting.

[00:14:09] **Ben:** Like every time I got a notification and it's not like it blew up or anything, I probably got like 30 comments, which is like way more than I've ever gotten.

[00:14:13] **Adam:** Mhm.

[00:14:18] **Ben:** And I don't know, I just hated it.

[00:14:19] **Ben:** I hated every moment of it.

[00:14:21] **Ben:** And uh, it makes me

[00:14:24] **Ben:** not want to,

[00:14:26] **Ben:** I don't participate in the conversation.

[00:14:26] **Tim:** Mhm.

[00:14:28] **Adam:** Yeah.

[00:14:29] **Adam:** This is going to Be my, old man yells at cloud moment.

[00:14:30] **Ben:** M.

[00:14:31] **Adam:** But uh, the thing that happens to me, used to happen to me that gave me the similar feelings was, whenever it was my birthday and going on Facebook, you get 30 people leaving posts or comments or sending you messages like,

[00:14:44] **Ben:** Yeah, yeah,

[00:14:46] **Tim:** Mhm.

[00:14:47] **Adam:** I don't care.

[00:14:48] **Adam:** Like, uh, I, I am the guy.

[00:14:49] **Ben:** Right.

[00:14:50] **Ben:** Mhm,

[00:14:51] **Adam:** So like a couple of years ago I would always, you know, oh, thank you, whatever, you know, it's nice to be thought of, Whatever.

[00:14:55] **Adam:** And then about a two, three years ago, I decided the amount of effort that you're putting into to remembering my birthday is that the amount of effort I'm gonna put into thanking you for remembering my birthday.

[00:15:06] **Adam:** So, uh, like there are people that I've, I wouldn't know it was their birthday if it wasn't for Facebook telling me.

[00:15:06] **Tim:** Mhm.

[00:15:13] **Adam:** But if it's somebody that I know and like I actually have a connection with, I'll like text them or call them and say, hey, Happy Birthday.

[00:15:20] **Adam:** I feel like at least that's a little bit more personal.

[00:15:22] **Adam:** It's not like, oh, hey, it's Ben's birthday.

[00:15:23] **Ben:** Right,

[00:15:24] **Adam:** Click here to say Happy Birthday.

[00:15:25] **Adam:** And it just sends you a message.

[00:15:26] **Adam:** I don't have to give it any effort whatsoever.

[00:15:27] **Tim:** Mhm.

[00:15:28] **Ben:** Right.

[00:15:28] **Adam:** Right.

[00:15:29] **Adam:** Like

[00:15:30] **Adam:** so, yeah.

[00:15:31] **Adam:** And then, I think this last year I finally had had enough.

[00:15:34] **Adam:** I just said, take my birthday out of Facebook.

[00:15:36] **Adam:** Nobody needs to know that anymore.

[00:15:39] **Ben:** The more we're in this crazy attention economy

[00:15:43] **Ben:** where there's just so many distractions, uh, having to put effort into anything that doesn't feel meaningful at this point just feels like

[00:15:49] **Adam:** Mm, mhm.

[00:15:51] **Adam:** Yeah.

[00:15:51] **Adam:** Okay, that's.

[00:15:52] **Adam:** That is such an interesting point.

[00:15:53] **Ben:** sa.

[00:15:54] **Adam:** That is exactly the type of interaction that so many of us finding our are finding ourselves in now with AI stuff.

[00:16:00] **Adam:** Right.

[00:16:01] **Tim:** Mhm.

[00:16:01] **Adam:** Somebody is trying to garner appreciation, gratitude, something with minimal effort.

[00:16:09] **Adam:** And the receiver of that has to deal with all of the effort.

[00:16:15] **Adam:** Right.

[00:16:15] **Adam:** So you are sending me an AI birthday Happy birthday thing and I have to deal with getting 70 of those because Facebook makes it so easy.

[00:16:25] **Adam:** And so now that's a burden on me because I had a birthday and it costs you 2 seconds to click the button.

[00:16:32] **Ben:** Mhm.

[00:16:32] **Adam:** I feel like that totally inverts what it should be.

[00:16:34] **Adam:** Right.

[00:16:35] **Adam:** Uh, and that's, that's where the frustration comes in.

[00:16:36] **Ben:** Yeah,

[00:16:39] **Tim:** See this is why in the Matrix movies the pinnacle of society was early

[00:16:46] **Tim:** 21st century pre super Internet days.

[00:16:49] **Adam:** Yeah.

[00:16:50] **Adam:** Flip phone.

[00:16:51] **Tim:** Flip phone days.

[00:16:51] **Ben:** Yeah,

[00:16:52] **Tim:** that's why we reached peak right there.

[00:16:54] **Tim:** It all went down after that.

[00:16:54] **Ben:** Yeah,

[00:16:56] **Ben:** right.

[00:16:57] **Ben:** The early 2000s, like the late 90s, early 2000s, that was just great.

[00:17:01] **Tim:** Yep.

[00:17:01] **Adam:** Yeah, man.

[00:17:03] **Ben:** Anyway, that's my failure.

[00:17:04] **Ben:** Uh, I'm gonna, I'm gonna do even less social media than I was before.

[00:17:08] **Adam:** Good.

[00:17:09] **Adam:** That's, that's how we make the world a better place.

[00:17:11] **Ben:** Yeah.

[00:17:11] **Adam:** One person at a time.

## [00:17:12] Hiring Remote Developers

[00:17:12] **Adam:** So let's talk about hiring.

[00:17:14] **Adam:** Tim, I know you've done some hiring recently, and as far as I know you're, you're hiring for at least partially remote, if not fully remote positions.

[00:17:14] **Tim:** Mhm.

[00:17:22] **Tim:** Yep.

[00:17:22] **Tim:** Yeah, they're all, they're all fully remote now.

[00:17:24] **Tim:** I mean I live 10 minutes from the office and I never go in.

[00:17:27] **Tim:** I'm fully remote.

[00:17:28] **Tim:** So yeah, we, we, we don't have the space in the office anymore for our total staff.

[00:17:33] **Tim:** So, yeah, we did two

[00:17:36] **Tim:** positions.

[00:17:36] **Ben:** Mhm.

[00:17:36] **Tim:** A junior, a developer position, and a senior.

[00:17:40] **Tim:** And I mean, I don't know if you guys experience this, but it's like the huge amount of applications you get is just ridiculous.

[00:17:48] **Tim:** We got over 2,200 for each.

[00:17:48] **Adam:** Yeah.

[00:17:51] **Adam:** Yeah.

[00:17:51] **Adam:** Once again, the power dynamic is like almost inverted, just in terms of the amount of work it takes to apply versus the amount of work it takes to deal with all the applications.

[00:17:56] **Ben:** Mhm,

[00:17:59] **Tim:** Yeah.

[00:18:00] **Tim:** So, I mean, it's like

[00:18:02] **Tim:** I, I see why, you know, people complain about, you know, using AI to do the intake, but unfortunately the AI problem is that people are also doing AI to submit the res.

[00:18:13] **Tim:** The resumes.

[00:18:13] **Adam:** Mhm.

[00:18:13] **Tim:** And some of them are very, very obvious.

[00:18:15] **Tim:** So we filter those out pretty quick.

[00:18:17] **Ben:** Mhm.

[00:18:17] **Tim:** and fortunately, you know, we do have an HR department.

[00:18:19] **Adam:** Mhm.

[00:18:19] **Tim:** It's not just me and other folks, so we have an HR department.

[00:18:23] **Tim:** They try to screen them as much as possible, have a actual phone interview where a human being picks up the phone and actually has a conversation with them before we'll even consider scheduling them.

[00:18:33] **Tim:** even with that, it's like, it such.

[00:18:37] **Tim:** It's just weird time, guys.

[00:18:39] **Tim:** So much, so much weird stuff is happening.

[00:18:39] **Ben:** M.

[00:18:39] **Ben:** Yeah,

[00:18:40] **Adam:** Yeah.

[00:18:41] **Tim:** Like you're these people who are obviously

[00:18:44] **Tim:** never heard of ColdFusion and it's in the app and they call it cloud fusion over and over again.

[00:18:51] **Tim:** Um,

[00:18:52] **Ben:** That's crazy.

[00:18:52] **Tim:** yeah,

[00:18:53] **Adam:** So that's a, that's an easy.

[00:18:54] **Adam:** Okay, thanks for your time.

[00:18:55] **Tim:** yeah, yeah, yeah, Very good.

[00:18:56] **Adam:** Click.

[00:18:57] **Ben:** Mhm.

[00:18:58] **Tim:** Um, but then they're, Then they're.

[00:19:00] **Tim:** But then there have been trends like, so I've read, and I think I'm experiencing this this time around because it's been a while since I hired that there are these

[00:19:10] **Tim:** countries, areas of the world where they have services that either,

[00:19:12] **Adam:** Mhm.

[00:19:12] **Ben:** Sa.

[00:19:16] **Tim:** you know, they will sell their service to, to someone like, you know, we'll help you get hired.

[00:19:18] **Ben:** Mhm.

[00:19:20] **Tim:** And they train.

[00:19:21] **Tim:** The people are very trained.

[00:19:22] **Tim:** Some of the people that are coming on these phone calls because.

[00:19:25] **Adam:** M Trained to interview well, right?

[00:19:26] **Tim:** Trained to interview well.

[00:19:28] **Tim:** Right.

[00:19:29] **Tim:** So they basically spit back to you your own verbiage on the job application.

[00:19:36] **Tim:** Right.

[00:19:37] **Tim:** So this one, she was, said she was like working for a local state college here in Georgia and doing research.

[00:19:39] **Ben:** Mhm,

[00:19:45] **Tim:** But then in describing how her job in the research position, it was talking about how they would service, uh, their clients and promote code within a certain window.

[00:19:57] **Tim:** It was exactly our wording about how we do our posting

[00:20:00] **Ben:** Mhm,

[00:20:01] **Adam:** Mhm.

[00:20:01] **Tim:** to promote, uh, code.

[00:20:03] **Tim:** And I'm like, so you're working at a college and the people you're dealing with are like research grads.

[00:20:10] **Tim:** Why do you call them your customers and clients and that you have to post code in their windows?

[00:20:17] **Tim:** How does, how does that work with a, with a, with the grad?

[00:20:20] **Tim:** And then there was some like, really fast talking kind of.

[00:20:20] **Adam:** Mhm.

[00:20:20] **Ben:** Mhm.

[00:20:24] **Tim:** And then again, regurgitating our own bullet points back to us.

[00:20:27] **Tim:** And you're like, uh, so it's.

[00:20:28] **Adam:** Right.

[00:20:30] **Tim:** It's really weird that you have to almost catch them up.

[00:20:32] **Tim:** And I hate this.

[00:20:33] **Tim:** I hate going into interview and feeling like I'm trying to play gotcha, right?

[00:20:37] **Adam:** Yeah.

[00:20:37] **Tim:** Because this is a very

[00:20:40] **Tim:** vulnerable, uh, moment for anyone, right?

[00:20:41] **Tim:** So Even if they're 100% sincere, hundred percent legit, maybe English isn't their first language.

[00:20:45] **Ben:** Right.

[00:20:45] **Ben:** They might be nervous.

[00:20:47] **Tim:** They're nervous, right?

[00:20:48] **Tim:** So you don't.

[00:20:49] **Tim:** I don't want to.

[00:20:50] **Tim:** I don't want to be.

[00:20:50] **Tim:** That guy's playing Gotcha.

[00:20:51] **Tim:** But then it's like at some point, I'm like,

[00:20:54] **Adam:** Mhm.

[00:20:54] **Tim:** so can you.

[00:20:56] **Tim:** So your supervisor, because she.

[00:20:59] **Tim:** One of the questions we ask to rate their supervisor, right?

[00:21:02] **Tim:** So like, your supervisor, you know, what would you rate them?

[00:21:04] **Tim:** And, oh, he was wonderful.

[00:21:06] **Tim:** Uh, 10 out of 10.

[00:21:07] **Tim:** Such a good, loving mentor, you know, Amazing.

[00:21:09] **Tim:** She glowing about him.

[00:21:11] **Adam:** Mm.

[00:21:11] **Tim:** About 10.

[00:21:11] **Tim:** So 10 minutes later, I asked, so your supervisor that you gave a 10 out of 10, what was his name?

[00:21:16] **Tim:** And there's a, and the eye, like the eye movement.

[00:21:19] **Tim:** You can, like, see them trying to go and figure out what should I say here?

[00:21:24] **Tim:** And then they.

[00:21:24] **Adam:** M.

[00:21:24] **Adam:** Right.

[00:21:24] **Tim:** And they just spit out a first name.

[00:21:26] **Tim:** Um, Jamal.

[00:21:27] **Tim:** Okay.

[00:21:28] **Tim:** All right, thank you.

[00:21:29] **Tim:** It's like, okay, you just made up a name on the spot right there.

[00:21:33] **Tim:** So it's.

[00:21:35] **Tim:** It's weird, man.

[00:21:37] **Ben:** It's super weird.

[00:21:37] **Adam:** So did you end up hiring for these two roles that you put out?

[00:21:40] **Tim:** We did.

[00:21:41] **Tim:** We did.

[00:21:41] **Tim:** One was actually a former employee.

[00:21:44] **Tim:** so he knew.

[00:21:44] **Adam:** At least you know, they're human.

[00:21:44] **Tim:** He.

[00:21:44] **Tim:** At least we know he's human.

[00:21:46] **Tim:** Uh, and then another was.

[00:21:48] **Tim:** Was someone that was a recommendation.

[00:21:51] **Tim:** So it's not that, uh.

[00:21:52] **Adam:** Yeah.

[00:21:52] **Adam:** Just goes to show, networking is still huge.

[00:21:53] **Tim:** Uh, yep, networking is still huge.

[00:21:56] **Tim:** But it's like, I felt bad.

[00:21:59] **Tim:** It's like were sitting through some of these interviews, were just so bad.

[00:21:59] **Ben:** Mhm.

[00:22:02] **Tim:** You could tell, like the one who just kept calling it cloud fusion.

[00:22:06] **Adam:** Mhm.

[00:22:07] **Tim:** But then I asked.

[00:22:10] **Tim:** It sounds like you have really good experience with cloud fusion.

[00:22:14] **Tim:** Can you tell me a little bit about the history of cloud fusion?

[00:22:17] **Tim:** And his eyeballs go straight up to the ceiling for like 10 seconds.

[00:22:21] **Tim:** And then he comes back down.

[00:22:22] **Tim:** He's like, yes, he was started by the Allaire brothers back in.

[00:22:27] **Tim:** And I'm like, okay, all right.

[00:22:28] **Ben:** M.

[00:22:28] **Ben:** That's how we all talk about ColdFusion for sure.

[00:22:32] **Tim:** I'm, uh, like, oh, I don't know where he got that from.

[00:22:34] **Tim:** If this is.

[00:22:35] **Tim:** If there's a screen on the ceiling or what.

[00:22:36] **Tim:** But yeah.

[00:22:38] **Tim:** And he kept calling it cloud fusion even after he remembered who the Allaire brothers were.

[00:22:42] **Adam:** Right.

[00:22:42] **Ben:** That's.

[00:22:43] **Ben:** That's wild.

[00:22:46] **Ben:** I am,

[00:22:46] **Adam:** Yeah.

[00:22:46] **Adam:** So, uh, go ahead, ben.

## [00:22:48] Hiring Through the Slop Avalanche

[00:22:48] **Ben:** I was just say I was listening to an episode just recently of

[00:22:52] **Tim:** Sa.

[00:22:52] **Tim:** Mhm,

[00:22:52] **Ben:** Mostly Technical Aaron Francis, Ian Landsman and Ian Landsman had just recently been hiring for his company.

[00:22:59] **Ben:** And he said that I, I think in the job application posting they had some specific things that they wanted to see in people's cover letters.

[00:23:08] **Ben:** And he said like 90% of the applications that he got didn't even fulfill like the simple requirements for what should be in your cover letter.

[00:23:13] **Tim:** Mhm,

[00:23:17] **Ben:** And he's like, he's like are like people just aren't even trying at all.

[00:23:17] **Adam:** Mm.

[00:23:17] **Adam:** Mhm.

[00:23:21] **Ben:** Like even for the minimum effort.

[00:23:24] **Ben:** And it just, it's wild.

[00:23:26] **Ben:** Uh,

[00:23:26] **Adam:** Yeah.

[00:23:26] **Adam:** You know, I think I'm gonna.

[00:23:27] **Adam:** If I.

[00:23:28] **Adam:** Not if, but when I do my next round of hiring, I think I'm gonna say like, I will, I will pay you for this personally.

[00:23:34] **Adam:** You have a budget of $10.

[00:23:36] **Adam:** I want you to go out and get a local newspaper.

[00:23:40] **Adam:** But I'm.

[00:23:40] **Adam:** I'm going to tell them this, like on the day of the interview or the day before, get a local newspaper so you can show it to me on video.

[00:23:47] **Adam:** like.

[00:23:47] **Ben:** I, I was just listening to something and it uh, was about education in AI and this one teacher said that they were including in their assignment some line about be sure to include this phrase in your, in your report.

[00:23:49] **Tim:** Mhm,

[00:24:02] **Ben:** And like you know, it was one of these things where I think it was probably like white text on a white background sort of a thing so that she could just immediately look to see if this was just copy pasted directly into uh, an AI for a prompt.

[00:24:06] **Tim:** Mhm.

[00:24:06] **Tim:** Yeah, yeah.

[00:24:15] **Ben:** And again like it's like it sucks that we have to call people out on kind of just being super lazy, but there's such a slop avalanche.

[00:24:22] **Adam:** Yeah.

[00:24:24] **Ben:** You almost have to find a way.

[00:24:25] **Tim:** Well, I.

[00:24:26] **Tim:** I push back on the.

[00:24:27] **Tim:** On the lazy.

[00:24:28] **Tim:** These people were very well trained.

[00:24:30] **Tim:** They were very well trained.

[00:24:31] **Tim:** I mean, I respect.

[00:24:32] **Adam:** M.

[00:24:32] **Adam:** There's different kinds.

[00:24:33] **Ben:** Mhm.

[00:24:33] **Adam:** Yeah.

[00:24:33] **Tim:** I respect the hustle because like they so obviously didn't understand what we do or the like, like one she claimed to have worked for basically a competitor of ours for two years, uh, in like property and casualty insurance.

[00:24:40] **Ben:** Sa.

[00:24:47] **Tim:** And at the very end wasn't me, someone else, one of the other interviewers like oh, by the way, so what?

[00:24:48] **Ben:** Mhm.

[00:24:53] **Tim:** Because we were hooked at this point, we're like this person's amazing.

[00:24:56] **Tim:** What lines of businesses did the comp.

[00:24:59] **Tim:** You know, the insurance company you work for, right?

[00:25:02] **Tim:** And she couldn't say.

[00:25:03] **Tim:** She's like, oh, well we, the, the, the uh, the, the office side of the.

[00:25:04] **Adam:** Mhm.

[00:25:08] **Tim:** They handled all the business side and we just handled the back end.

[00:25:13] **Tim:** They were like, so you don't know.

[00:25:14] **Ben:** You don't even know what you're offering insurance for.

[00:25:16] **Tim:** So you work for an insurance company.

[00:25:17] **Tim:** You couldn't even tell from the table names that it was like auto insurance or homeowner's insurance or life insurance or medical insurance.

[00:25:24] **Tim:** I mean I would think there'd be some clue somewhere in the code what you'.

[00:25:28] **Ben:** There's got to be a whole industry now about AI being used to filter through all of the AI onslaught.

[00:25:35] **Ben:** Right?

[00:25:35] **Ben:** That's got to be a thing.

[00:25:36] **Tim:** I mean we use, we actually do use AI already to score them, right?

[00:25:37] **Adam:** Oh yeah.

[00:25:39] **Tim:** So the AI is pretty good at picking out like even, like even the ones we did interview.

[00:25:39] **Ben:** Gotcha.

[00:25:44] **Tim:** Like some of them like very

[00:25:45] **Ben:** Mhm.

[00:25:47] **Tim:** obviously flagged out.

[00:25:48] **Tim:** Like the terminology they're using is basically your own job applications being spit back to you.

[00:25:55] **Adam:** Yeah.

[00:25:55] **Adam:** Mhm.

[00:25:55] **Tim:** So here's what you need to drill on.

[00:25:56] **Tim:** And we did, we got through it.

[00:25:59] **Tim:** But it's like, I mean I respect the hustle.

[00:26:01] **Tim:** It's like for some, I uh, mean if the, I don't know where these people are, maybe they're, they all say they're in America, but maybe they're not.

[00:26:06] **Ben:** Mhm.

[00:26:08] **Tim:** And if, you know, they could get a job for even a couple months at an American wage, I imagine it would be huge for them and their families.

[00:26:15] **Tim:** I, I don't, I'm not mad at them.

[00:26:17] **Tim:** Um, it's just really, really a waste of my time.

[00:26:20] **Adam:** Mhm.

## [00:26:22] Will Fraud Push Work Back to Offices?

[00:26:22] **Adam:** Yeah.

[00:26:23] **Adam:** And you know, honestly, I.

[00:26:24] **Adam:** It makes me wonder if we just.

[00:26:26] **Ben:** Mhm.

[00:26:26] **Adam:** This, the hiring issue itself and the way that it's becoming harder and harder to tell when somebody is trying to, for lack of a better word, I'll say scam you.

[00:26:35] **Adam:** Right.

[00:26:35] **Tim:** Yeah.

[00:26:35] **Adam:** they're trying to game the system

[00:26:38] **Adam:** and not abide by

[00:26:40] **Adam:** what I'll call the rules.

[00:26:42] **Adam:** Right.

[00:26:42] **Adam:** You know, we're like, we're only supposed to hire American citizens.

[00:26:45] **Adam:** Right.

[00:26:45] **Tim:** Okay.

[00:26:45] **Adam:** You have to do extra paperwork and extra stuff to hire abroad.

[00:26:45] **Tim:** Mhm.

[00:26:49] **Adam:** Um, and like there was, I remember a time when, you know, we got flack for that.

[00:26:53] **Adam:** Like, sorry, we can only hire American citizens.

[00:26:55] **Adam:** And people were like, well, but I'm in Germany or whatever.

[00:26:57] **Adam:** And I'm like, yeah, I know that sucks.

[00:26:58] **Adam:** I'm sorry.

[00:26:59] **Adam:** And now you've got these people that are like, oh, yeah, I'm based in Georgia.

[00:27:02] **Adam:** Maybe they are in Georgia, just not in Georgia, United States.

[00:27:05] **Ben:** Mhm mhm.

[00:27:06] **Adam:** Um, but uh, wondering if because of all this, we might see more of a push to go back toward, offices and like in person work just because it's easier to, it's easier to check that box.

[00:27:20] **Adam:** Like this is a person who is actually physically

[00:27:23] **Tim:** Mhm.

[00:27:24] **Adam:** hireable.

[00:27:24] **Adam:** Right.

[00:27:25] **Adam:** Like, we can get in trouble if we hire somebody, uh, internationally and, and we're not supposed.

[00:27:28] **Ben:** Yeah,

[00:27:31] **Ben:** It's uh, so tough because I feel like at this point so many people have built their lives around being able to be remote and then to go back on that, it's like it's a very non trivial thing I think for a lot of people.

[00:27:32] **Tim:** It.

[00:27:34] **Tim:** Mhm.

[00:27:46] **Ben:** Because if you're working remote at this point, you know, you might not be in a metropolitan hub, you know can speak for self here where you know, if I had to go into an office it would not be easy to do.

[00:27:47] **Adam:** To.

[00:27:52] **Adam:** Mm,

[00:27:55] **Tim:** Yeah.

[00:27:59] **Adam:** Yeah.

[00:27:59] **Tim:** And, and then on the business side it's like so a lot of companies, they've downsized office space, right?

[00:28:04] **Tim:** They're getting out of the landlord business or you know, the office management business.

[00:28:07] **Adam:** Mhm.

[00:28:08] **Tim:** And they, you know, either go.

[00:28:11] **Tim:** We have a very small footprint now, and hope that once we get all our hosted stuff to the cloud, then we'll shut that office down.

[00:28:19] **Tim:** So it's like

[00:28:20] **Tim:** there's trade offs, right?

[00:28:22] **Tim:** I, I don't.

[00:28:22] **Ben:** Yeah.

[00:28:23] **Tim:** But it could be a pendulum kind of thing.

[00:28:24] **Tim:** I, I think a lot of the

[00:28:28] **Tim:** generation coming out of colleges now, they're like, like, you know what I've been Remote all my life.

[00:28:33] **Tim:** I would kind of like to know what it's like to.

[00:28:36] **Ben:** Yo, I miss being in an office sometimes.

[00:28:36] **Tim:** Mhm.

[00:28:38] **Ben:** I'll be straight up honest.

[00:28:39] **Ben:** I it.

[00:28:40] **Adam:** Yeah.

[00:28:40] **Adam:** Uh, I don't miss commuting.

[00:28:41] **Adam:** I do occasionally miss being in an office with my co workers.

[00:28:42] **Ben:** Yeah, yeah,

[00:28:44] **Tim:** Yeah.

[00:28:45] **Ben:** yeah, totally.

[00:28:46] **Ben:** And also it's like I have responsibilities now which have been made easier because I am home.

[00:28:54] **Ben:** Um, so like again it's, it wouldn't Be the easiest thing to do to get back to an office.

[00:28:58] **Ben:** But I do miss it.

[00:28:59] **Tim:** Yeah.

[00:29:00] **Tim:** I'm gonna miss a camaraderie sometimes.

[00:29:02] **Tim:** Things are actually.

[00:29:04] **Tim:** I take that back.

[00:29:05] **Ben:** Well,

[00:29:05] **Tim:** Things have been boring in a while, so.

[00:29:06] **Ben:** but that's, but you know, like that's what it is for me.

[00:29:08] **Ben:** It's the camaraderie.

[00:29:09] **Ben:** Do I feel like I was more efficient or more productive in an office?

[00:29:10] **Tim:** Yeah,

[00:29:14] **Ben:** Absolutely not.

[00:29:15] **Ben:** Like uh, the in office conversation for me is not at all about doing better work.

[00:29:15] **Tim:** Yeah,

[00:29:16] **Adam:** Mhm.

[00:29:20] **Ben:** It was about just being with the team.

[00:29:23] **Tim:** Yeah,

[00:29:23] **Adam:** You know what we should do?

[00:29:24] **Adam:** We should start a podcast that's like about, you know, hanging around the water cooler with your co workers.

[00:29:25] **Tim:** there you go.

[00:29:27] **Tim:** Yeah,

[00:29:29] **Tim:** yeah, that's, that's, that's kind of what I was thinking.

[00:29:30] **Ben:** Yo.

[00:29:32] **Tim:** Like, that's sort of the niche that we, that you, you, uh, you know, initially talked about doing.

[00:29:36] **Tim:** And that's true.

[00:29:36] **Tim:** It's like I see the Discord going off during the day and I'm like, that's, uh, awesome for people who are like, have very small teams and they're not connected.

[00:29:43] **Tim:** Like, here's a place they can all talk.

[00:29:45] **Ben:** M.

[00:29:46] **Tim:** Like the water cooler.

[00:29:46] **Ben:** Yeah,

[00:29:47] **Tim:** So.

[00:29:49] **Tim:** Yay.

[00:29:49] **Ben:** um, if I could do a quick, just.

[00:29:50] **Adam:** This.

## [00:29:52] AI, Education, and Doing the Work

[00:29:52] **Ben:** I want to revisit that, uh, the podcast I was listening to about AI and education.

[00:29:56] **Ben:** And this was just a fascinating thing.

[00:29:57] **Tim:** Uh-huh.

[00:29:57] **Adam:** Mhm,

[00:29:59] **Ben:** So there's one guy, he was teaching a course, it was like behavioral economics or something.

[00:30:01] **Tim:** Mhm.

[00:30:04] **Ben:** And the course was advertised as having take home tests and something like 30 people signed up for it.

[00:30:10] **Ben:** He said it's traditionally a very popular class and the first tests and like the midterm were done at home, you know, like in the dorm rooms or whatever.

[00:30:19] **Ben:** And, and he said he looked at the test results and it was like so clearly AI generated answers that he finally said, hey, you know, the final is actually going to be in class.

[00:30:24] **Tim:** Mhm.

[00:30:25] **Adam:** Mhm.

[00:30:30] **Ben:** You know, written final.

[00:30:31] **Ben:** And of the 30, I think he said 24 students immediately dropped the course.

[00:30:37] **Adam:** Nice.

[00:30:38] **Ben:** And, and three of them showed up and got a zero on the final.

[00:30:43] **Tim:** Whoa.

[00:30:43] **Adam:** Wow.

[00:30:43] **Ben:** Yeah.

[00:30:44] **Ben:** And like ah, you know, okay, so this was being discussed by, by two hosts on another podcast and one of the hosts said that this is actually an indictment of the educational system.

[00:30:51] **Tim:** Mhm.

[00:30:56] **Ben:** That, that the educational system isn't addressing the reality of the way kids are, are being educated and kids are using technology.

[00:31:05] **Ben:** And I um, mean maybe this is again just like an old man yells at cloud moment.

[00:31:09] **Ben:** But I feel like

[00:31:11] **Ben:** isn't, isn't part of learning, like just having to show up and do the work.

[00:31:15] **Tim:** Mhm.

[00:31:17] **Ben:** And if someone said hey, you have to show up and do the work for the final and the vast majority of the kids drop out of the class, like that's not an indictment of educational system.

[00:31:28] **Ben:** That's an indictment of people just not showing up and doing the work.

[00:31:31] **Ben:** And I, and like I just feel, it feels crazy to me.

[00:31:35] **Ben:** I feel like I'm, I'm taking crazy pills when I hear people talk about it with such like kid gloves on.

[00:31:36] **Adam:** Mhm,

[00:31:43] **Tim:** Well, I mean, you say that, I'll give you the opposite coin in my opinion on that.

[00:31:48] **Tim:** Uh, so education has become an industry.

[00:31:49] **Adam:** Mhm,

[00:31:51] **Tim:** Right.

[00:31:52] **Tim:** And

[00:31:53] **Ben:** That's true.

[00:31:54] **Tim:** has never.

[00:31:55] **Ben:** Mhm.

[00:31:55] **Tim:** It's true.

[00:31:56] **Tim:** It makes you do things that are hard, it makes you try to learn things, but it does so in probably the most reductive manner possible when it comes to learning how to think.

[00:32:05] **Tim:** And that's the thing.

[00:32:06] **Tim:** I don't think schools have Interesting.

[00:32:08] **Tim:** ever,

[00:32:10] **Tim:** in America at least been designed to actually teach people to think.

[00:32:14] **Tim:** They teach them how to take tests, they teach them how to pass standards.

[00:32:19] **Tim:** And so, and that, and that, I think AI shows up the, the flaws in the system itself.

[00:32:24] **Tim:** You're not training thinkers, you're training people who can regurgitate information.

[00:32:26] **Ben:** M.

[00:32:26] **Ben:** Yeah.

[00:32:29] **Tim:** And AI is going to beat them hands down every day.

[00:32:34] **Ben:** And this, okay.

[00:32:34] **Ben:** And, and this feeds.

[00:32:35] **Tim:** And we're really diverging here, but.

[00:32:37] **Ben:** Yeah, but like this, this feeds back into, you know, conversations that we've had previously where I have questioned how when I hear people say, oh, I love watching the AI write the code because I'm learning so much about how the code should be written or, you know, like I'm learning about all the great techniques that the AI is using.

[00:32:37] **Tim:** Okay.

[00:32:40] **Adam:** Mhm,

[00:32:52] **Adam:** Mhm.

[00:32:59] **Ben:** And then I see something like this with the, uh, with the kids where the second they have to not use AI, it's like they just check out.

[00:33:05] **Tim:** Yep,

[00:33:05] **Ben:** And I'm like, that feels more real to me at least than people claiming that they're learning from what the AI is doing.

[00:33:13] **Ben:** I feel like people are telling themselves that they're learning from what the AI is doing.

[00:33:17] **Adam:** Yeah.

## [00:33:19] Cheating the Technical Assessment

[00:33:19] **Tim:** So, so we had a part like, you know, during the interview, we had a lot of the same thing.

[00:33:24] **Tim:** Repeat the, repeat the job application back to us, uh, word for words.

[00:33:28] **Tim:** Change it up a little bit.

[00:33:30] **Tim:** Don't, don't say anything specific.

[00:33:30] **Adam:** Mhm.

[00:33:32] **Tim:** But then we got to the code part all of a sudden.

[00:33:34] **Tim:** Like they would kind of look at the code and some of them would type, but others were like, very, like, oh, good to keep my hands up here.

[00:33:42] **Tim:** You know, they show us their hands.

[00:33:43] **Ben:** Mhm.

[00:33:44] **Tim:** So they.

[00:33:44] **Adam:** Oh, uh, you, you did mention that they were keeping.

[00:33:46] **Adam:** This was before we started recording you, but you mentioned they were keeping the hands up, but you didn't say that they were like audibly acknowledging.

[00:33:47] **Tim:** Yeah, yeah,

[00:33:50] **Tim:** yeah.

[00:33:51] **Tim:** They, they called, they called it like, I just want you to know I'm not, I'm not, I'm not, I'm not, you know, I'm going to keep my hands up.

[00:33:52] **Adam:** Okay, I'm keeping my hands up.

[00:33:53] **Ben:** Oh, that's funny.

[00:33:57] **Adam:** Yeah,

[00:33:57] **Tim:** You know, if I put them down, I'm not looking, I'm like, okay, cool.

[00:34:01] **Tim:** And then, and all of a sudden their eye would like shift from part of the screen that they were normally looking at over to the right or to the left.

[00:34:06] **Ben:** M.

[00:34:07] **Tim:** And then they became an instant ColdFusion genius.

[00:34:10] **Adam:** Right.

[00:34:11] **Tim:** Because we show them

[00:34:11] **Ben:** I think you mean cloud fusion, Tim.

[00:34:13] **Tim:** cloud fusion.

[00:34:14] **Tim:** Yes, written by the Allaire brothers back in 96, 95.

[00:34:19] **Tim:** But anyway, they'd start like.

[00:34:20] **Ben:** Sa.

[00:34:21] **Tim:** And so, uh, I didn't do this.

[00:34:23] **Tim:** Someone else on the call, she put in one of the coding questions that we had is we had some SQL statements, we had some, you know, combined ColdFusion where you had like a SQL or did a select star from.

[00:34:26] **Ben:** Mhm.

[00:34:34] **Tim:** And there was, you know, no query parameterization.

[00:34:37] **Tim:** And then it did a loop through there and did a query inside the loop.

[00:34:42] **Tim:** And um, if you've ever, you know, ask ChatGPT about that paradigm, it's.

[00:34:46] **Tim:** It loves to call it the N+1 problem.

[00:34:49] **Ben:** M.

[00:34:50] **Tim:** And so like all of a sudden the person went from looking at it to looking off screen and they go, oh yes, this is the N+1 problem.

[00:34:56] **Tim:** Like that's ex.

[00:34:56] **Ben:** Classic classic.

[00:34:57] **Ben:** N plus one.

[00:34:58] **Tim:** Classic N+1 problem.

[00:35:01] **Tim:** Like that is exactly what ChatGPT said.

[00:35:03] **Tim:** Wonder how you got there.

[00:35:06] **Ben:** Um, but it is a waste of your time.

[00:35:06] **Tim:** So,

[00:35:07] **Adam:** Hmm.

[00:35:09] **Ben:** I mean, like, I know you're, you're being very generous, I think, in your perspective here,

[00:35:09] **Tim:** yeah,

[00:35:14] **Tim:** Uh, I am, I'm very generous guy, but I want to.

[00:35:15] **Ben:** but your time is very valuable.

[00:35:16] **Tim:** But, but before we, before I forget if I get.

[00:35:19] **Tim:** So I did have some ColdFusion people that I know are like absolute rock stars.

[00:35:23] **Adam:** Mhm.

[00:35:23] **Tim:** Come on.

[00:35:23] **Tim:** And they looked at the same problems and they struggled,

[00:35:27] **Ben:** Oh, no.

[00:35:28] **Adam:** Oh, wow.

[00:35:28] **Tim:** they struggled.

[00:35:29] **Ben:** Oh,

[00:35:29] **Tim:** They really did.

[00:35:30] **Tim:** It was, it was painful to watch after watching these people who obviously did not know what cloud fusion was, uh, just, just spit out like, oh yeah, this is classic.

[00:35:36] **Ben:** Um.

[00:35:39] **Tim:** You need query parameter there.

[00:35:40] **Adam:** Yeah.

[00:35:40] **Tim:** And it's like I saw someone who legitimately knows it and like there was a lot more friction with their answer because they're like, dude, this is like I forgot more about this than, than, than any one of you people remember.

[00:35:52] **Adam:** M.

[00:35:52] **Adam:** Yeah.

[00:35:54] **Adam:** I wonder if we're gonna see like a new type of job crop up where it's like, I'm, I'm not a subject matter expert.

[00:35:55] **Ben:** M.

[00:35:55] **Ben:** That's funny.

[00:36:01] **Adam:** I don't know cloud fusion all that well, but I know software engineering concepts and I'm good at wrangling the AI and getting it to do this thing.

[00:36:05] **Tim:** I'm.

[00:36:07] **Tim:** Mhm.

[00:36:11] **Adam:** Right.

[00:36:11] **Adam:** Like, I, I could not.

[00:36:12] **Tim:** Yeah,

[00:36:12] **Ben:** Mhm.

[00:36:13] **Adam:** If you didn't let me have, uh, access to AI, I could not take an AngularJS job right now.

[00:36:18] **Adam:** Right.

[00:36:19] **Adam:** I would be terrible at that.

[00:36:20] **Tim:** Yeah.

[00:36:20] **Adam:** I could, I could muddle my way through it, you know, with Google and stuff, but it would, I would be slow.

[00:36:26] **Adam:** I would be just fine doing that with AI.

[00:36:29] **Adam:** I could guide the AI through that, no problem.

[00:36:31] **Adam:** you know, I would probably start with.

[00:36:31] **Ben:** Mhm.

[00:36:33] **Adam:** Okay, tell me about Angular Like, okay, the last time I looked at Angular there was a thing called directives and

[00:36:40] **Adam:** there was just a whole, uh, brain scramble around that.

[00:36:43] **Adam:** And uh, so I'm wondering if, like, that's a new sort of type of job that we write instead of coder and like project manager.

[00:36:49] **Adam:** I wonder if we're gonna have like project manager and AI herder or something.

[00:36:49] **Tim:** Mhm.

[00:36:53] **Tim:** Yeah.

[00:36:54] **Tim:** Well, I mean, that's what felt unnatural, honestly about our interview is because we're like telling them you can't use AI, but if we hire them, the second they get on, what are we going to tell them?

[00:37:02] **Adam:** Right?

[00:37:04] **Tim:** Hey, you need to start using AI, right?

[00:37:05] **Adam:** Yeah.

[00:37:05] **Ben:** Mhm.

[00:37:06] **Tim:** So it's like that's part of the job requirement these days, but yet we treat it like it's a bad word during the interview.

[00:37:11] **Tim:** And we do ask them about their AI experience, but it's like we don't want them using.

[00:37:14] **Adam:** Mm.

[00:37:15] **Tim:** We want you to use AI to cheat to make money, not cheat to get the job.

[00:37:21] **Adam:** Yeah,

[00:37:23] **Adam:** it is.

[00:37:23] **Ben:** It's,

[00:37:23] **Adam:** It's a little, uh, hypocritical.

## [00:37:26] What Makes a Good Hire Now?

[00:37:26] **Tim:** Yeah.

[00:37:26] **Ben:** it's interesting because if you think Back to like 10ish years ago, it felt like

[00:37:35] **Ben:** you couldn't be personal in an interview.

[00:37:37] **Ben:** You couldn't ask people necessarily about their kids or like, oh, it looks like you're pregnant, or you know, like anything, because that.

[00:37:43] **Adam:** You still can't, you very much cannot do that, Ben.

[00:37:43] **Tim:** Still can't,

[00:37:45] **Tim:** uh, you can't try to figure out how old they are, even though they look ancient on the screen.

[00:37:47] **Ben:** All right, right, right.

[00:37:49] **Ben:** Because all of this could indicate bias, discrimination, um, etc.

[00:37:53] **Tim:** Mhm.

[00:37:53] **Adam:** Mhm.

[00:37:55] **Ben:** And the very notion that you would want to find someone who is a quote unquote, team fit is basically just you continuing to poison the well against anyone else who might be.

[00:38:07] **Adam:** Right.

[00:38:07] **Adam:** That's vibes.

[00:38:07] **Ben:** Uh, yeah.

[00:38:08] **Adam:** Yeah.

[00:38:09] **Tim:** Yeah.

[00:38:09] **Ben:** So.

[00:38:10] **Ben:** But it's so fascinating now because in the age of AI, where the technical chops almost feel, to your point, like they're just becoming less of a thing.

[00:38:18] **Ben:** Like what becomes the differentiating factor is like, uh, do you fit on this team?

[00:38:21] **Tim:** Mm.

[00:38:22] **Adam:** Yeah,

[00:38:25] **Ben:** Like, will you show up and be someone we want to work with?

[00:38:25] **Adam:** yeah.

[00:38:25] **Adam:** I mean,

[00:38:28] **Adam:** honestly, if I was hiring right now, the, the number, the first couple of things, uh, that come to mind for me that would be important for me to get in the person that I hire.

[00:38:36] **Adam:** Fantastic communication skills and some sort of technical background where I can, we can discuss technical problems and you can, you know, I can explain a problem and a suggestion or you know, parameters for you to fix and you get that and you can regurgitate it to me in your own words.

[00:38:37] **Ben:** Mhm.

[00:38:38] **Tim:** Mhm,

[00:38:54] **Adam:** Ah.

[00:38:55] **Adam:** And you know, to, uh, to satisfy that I know what you're talking about

[00:39:00] **Adam:** and notice I said nothing about language there.

[00:39:02] **Adam:** I said nothing about years of experience.

[00:39:03] **Ben:** Right.

[00:39:04] **Adam:** Right.

[00:39:04] **Adam:** It's just like I, I, it is an unsolved problem and it's going to be a very interesting few years as these frontier models continue to get better and that, I mean, there are, I, I don't know if you've seen this, Ben.

[00:39:07] **Tim:** Mhm,

[00:39:16] **Adam:** I know there are tools specifically built for cheating on interviews.

[00:39:20] **Adam:** They're like.

[00:39:21] **Adam:** And they advertise themselves as I.

[00:39:23] **Adam:** This is the tool you use to cheat on your job interview.

[00:39:25] **Adam:** Right?

[00:39:26] **Adam:** It's like the, uh, I wish I could remember what it was called.

[00:39:27] **Tim:** Mhm,

[00:39:29] **Adam:** It was a big thing about a year ago, maybe a little longer.

[00:39:31] **Ben:** M.

[00:39:32] **Ben:** Right.

[00:39:32] **Ben:** The guy got like, like Y Combinator money or something, or he got like VC

[00:39:32] **Adam:** Time is.

[00:39:35] **Adam:** Yeah, okay.

[00:39:36] **Adam:** Yeah, yeah, yeah.

[00:39:38] **Adam:** yeah.

[00:39:39] **Adam:** And it's like, you know, it's, it's recording your screen, but somehow it's blocking things from detecting that it's recording your screen so it can like give you answers.

[00:39:45] **Adam:** And it's like a translucent overlay, so it looks like you're looking at your webcam.

[00:39:49] **Tim:** Mhm.

[00:39:49] **Adam:** And yeah, so I mean that I think, honestly, again, if I were hiring right now, that's what I would be looking for is like, I'm not going to, I'm not going to hire somebody for a math job and tell them they can't use a calculator.

[00:39:50] **Ben:** Right.

[00:39:50] **Ben:** It's wild.

[00:40:03] **Adam:** Right.

[00:40:03] **Adam:** Like, this is a tool that's going to be available to you on the job.

[00:40:03] **Tim:** Right.

[00:40:06] **Adam:** If it's, if it's helpful to you in the interview, then use it.

[00:40:09] **Adam:** But use it for the stuff that we would be doing on the job, not for answering a human question.

[00:40:17] **Adam:** Right,

[00:40:17] **Ben:** Would you say that there's value in seeing someone struggle?

[00:40:19] **Adam:** Oh you son of a.

[00:40:26] **Adam:** He got me.

[00:40:26] **Tim:** Good day.

[00:40:28] **Adam:** I've triggered your trap card.

[00:40:33] **Ben:** Oh, uh, man, it is just.

[00:40:33] **Tim:** Uh, and it's just crazy.

[00:40:36] **Tim:** It's like the amount of like qualified candidates who've been looking for so long, it's, it's,

[00:40:40] **Adam:** Yeah, it's, it's disheartening for sure.

[00:40:42] **Tim:** it is very disheartening, honestly.

[00:40:42] **Ben:** Yeah,

[00:40:44] **Ben:** it gives me such anxiety.

[00:40:46] **Ben:** If I can be completely transparent, you know, I'll see people on LinkedIn who say, hey, if anybody has any openings, let me know.

[00:40:54] **Ben:** I've been looking for a job for like eight months and these are people that I, I know and they, you know, they're my age and they've been in the industry for a long time and I see it and it's, it like it gives me gut pain to think that, you know, I'm like, uh, however many arbitrary business decisions away from being that person.

[00:41:06] **Tim:** Mhm.

## [00:41:14] Proving You're Human on a Resume

[00:41:14] **Adam:** Mm.

[00:41:14] **Adam:** Mhm.

[00:41:15] **Adam:** So, okay, that's a very good segue into maybe a, ah, what I hope is kind of our last general topic for this tonight.

[00:41:22] **Tim:** Mhm.

[00:41:22] **Adam:** Um, so if hypothetically I were a, ah, real human being and I'm experienced on the job and I'm applying for jobs and I.

[00:41:31] **Adam:** This is kind of directed at you, Tim, but you know, Ben, whatever.

[00:41:34] **Adam:** If you have stuff to add to, what would you be looking for in my application to help me?

[00:41:34] **Ben:** Mm.

[00:41:34] **Ben:** Mhm,

[00:41:42] **Adam:** I want to use the word stand out, but not just stand out, like prove.

[00:41:42] **Ben:** Mhm,

[00:41:44] **Adam:** Okay.

[00:41:44] **Adam:** I'm a human and I'm, I have actual useful, valuable experience and I am a good fit for this job.

[00:41:50] **Adam:** How do I indicate that without,

[00:41:53] **Adam:** I don't know, being AI?

[00:41:54] **Tim:** I, I would, I'd say a couple things.

[00:41:57] **Tim:** One thing that it's like so many resumes are just template, right?

[00:42:02] **Tim:** It's, you know, job history.

[00:42:02] **Adam:** Mhm.

[00:42:03] **Ben:** Mhm,

[00:42:03] **Tim:** Job history, job history, education, whatever, hobbies.

[00:42:08] **Tim:** But the few ones who stood out kind of told a story.

[00:42:14] **Adam:** Okay.

[00:42:14] **Tim:** And so, you know, human beings love a good story.

[00:42:17] **Tim:** And so if you can kind of have a, I mean, all that other stuff I mentioned is very important.

[00:42:22] **Tim:** You have to have it there because the AI checking tools are going to look for it.

[00:42:26] **Tim:** But if there's like just a section that just tells a story about who you are as a real human being, as a person, that, that comes off.

[00:42:31] **Adam:** Hmm.

[00:42:31] **Adam:** Mhm.

[00:42:36] **Tim:** Don't use AI to write it.

[00:42:37] **Tim:** If it comes off.

[00:42:38] **Ben:** Mhm.

[00:42:38] **Tim:** If it comes off legitimate and like, okay, here's a real person with real struggles, real challenges, but also feels like they have real solutions.

[00:42:46] **Tim:** That's, that's without a whole lot of corporate BS right?

[00:42:51] **Adam:** Yeah.

[00:42:52] **Tim:** Um, and two mistakes.

[00:42:54] **Tim:** So that's, it's almost counterintuitive.

[00:42:56] **Tim:** So I'll talk about this in the after show.

[00:42:58] **Tim:** My son interviewed for the junior position and he learned a lot.

[00:43:02] **Tim:** A lot.

[00:43:03] **Tim:** Uh, number one spell valedictorian correctly on your, uh, resume.

[00:43:06] **Adam:** Oh my God.

[00:43:07] **Adam:** You cannot be the valedictor.

[00:43:09] **Ben:** This.

[00:43:09] **Adam:** I, I, I'm.

[00:43:10] **Adam:** What, uh, what, what is school?

[00:43:12] **Adam:** I'm going to write them a formal request to revoke his valedictor.

[00:43:13] **Tim:** Right,

[00:43:16] **Tim:** Number one, do that.

[00:43:17] **Tim:** But what's funny is we do have a tool that goes through it and grades the authenticity of each of these resumes.

[00:43:24] **Ben:** Mhm,

[00:43:25] **Tim:** To say this is obviously AI.

[00:43:28] **Tim:** It flagged his as being the opposite of what AI does because it was incomplete.

[00:43:33] **Tim:** It has misspelled.

[00:43:35] **Tim:** It had that one misspelling.

[00:43:37] **Adam:** Is he a zoomer?

[00:43:37] **Tim:** Um, yeah, yeah, he's a zoomer.

[00:43:39] **Adam:** Okay.

[00:43:40] **Tim:** I mean he, yeah, graduated like two years after COVID lockdown.

[00:43:44] **Tim:** and it sort of like flagged the fact that all.

[00:43:46] **Tim:** Almost his lack of experience that was listed was almost refreshing and obviously not manufactured.

[00:43:52] **Tim:** So I'm not saying do that to stand out because he's definitely not getting the job,

[00:43:59] **Ben:** Mhm,

[00:43:59] **Tim:** but he did learn a lot.

[00:44:00] **Tim:** But yeah, so, so have a, like have a human connection part of the story and then like, don't, honestly, don't be too perfect.

[00:44:03] **Ben:** Mhm.

[00:44:08] **Tim:** That's, that's the thing.

[00:44:08] **Adam:** Yeah,

[00:44:09] **Tim:** That, that, it's the little

[00:44:12] **Tim:** imperfections, I mean, spell things right.

[00:44:14] **Tim:** But it's the little, the little foibles that kind of make you go, okay, this is real.

[00:44:20] **Adam:** Yeah.

[00:44:20] **Adam:** It used to be attention to detail and getting every little detail perfect on your resume and Your cover letter was like the way to stand out.

[00:44:22] **Tim:** Yeah,

[00:44:27] **Tim:** Yeah,

[00:44:27] **Adam:** And I feel like that's almost a bad thing now.

[00:44:31] **Tim:** yeah, that, that, well, it just gets lost in the noise, right?

[00:44:34] **Adam:** Yeah,

[00:44:34] **Tim:** So it's, it's a good signal, but unfortunately it's, it's lost in the noise.

[00:44:38] **Ben:** I'll tell you, I, uh, have not been in a whole bunch of interviews in my life.

[00:44:42] **Ben:** Um, like, I have, I have not.

[00:44:43] **Tim:** It's because you're awesome and everybody wants you.

[00:44:45] **Ben:** No, no, no, no.

[00:44:45] **Ben:** I mean, I've not, I've not run a bunch of interviews.

[00:44:48] **Ben:** Like, I've not been hiring.

[00:44:49] **Ben:** I, I have historically not been the person who hires people, which I love.

[00:44:49] **Tim:** Okay.

[00:44:53] **Ben:** And uh,

[00:44:54] **Adam:** I love that for you.

[00:44:55] **Ben:** yeah.

[00:44:55] **Adam:** Mhm.

[00:44:56] **Ben:** Uh, but the few that I have been in, one of the things that I always tried to get out of people, which ended up being really challenging, was just getting people to tell me what it is that they're excited about.

[00:45:07] **Tim:** Mhm.

[00:45:08] **Ben:** And.

[00:45:08] **Adam:** M.

[00:45:08] **Adam:** What would you say you are excited about?

[00:45:11] **Ben:** Yeah, yeah.

[00:45:12] **Ben:** And it's.

[00:45:12] **Ben:** I, I, I feel like.

[00:45:14] **Ben:** And you know, I understand that interviews are stressful and you're very much a deer in headlights, I think a lot of the time.

[00:45:15] **Adam:** It's a really great.

[00:45:18] **Adam:** Yeah.

[00:45:23] **Ben:** But the number of times where I was just like, what do you, what are you excited about learning right now?

[00:45:27] **Adam:** Mhm.

[00:45:28] **Ben:** Like, what's, what's the last thing that you came across that you thought was really cool?

[00:45:32] **Ben:** And it was like blank stares basically every time.

[00:45:35] **Adam:** Yeah.

[00:45:38] **Ben:** Which again, I think people are nervous, but also I want you to be excited about stuff.

[00:45:38] **Tim:** That's funny.

[00:45:41] **Tim:** Yeah, well, I don't know.

[00:45:43] **Tim:** I've had, I've had good luck with that.

[00:45:45] **Tim:** That question.

[00:45:45] **Tim:** So that used to be one, uh, that I would ask is like, so you know, when you're not

[00:45:51] **Tim:** at school or working or coding, what do you, what do you, what do you do in your spare time for fun?

[00:45:56] **Adam:** Uh, that's a different.

[00:45:57] **Adam:** I think you're, what I heard was two different things.

[00:46:00] **Adam:** You're talking about what do I do for fun when I'm not at the computer or not coding.

[00:46:05] **Adam:** And I.

[00:46:05] **Adam:** What I heard Ben ask is what part of coding excites you?

[00:46:09] **Tim:** Yeah, well, I mean, so I, I, I think mine is a good icebreaker.

[00:46:09] **Ben:** Yeah, yeah.

[00:46:10] **Ben:** But I think both are good.

[00:46:14] **Tim:** Right.

[00:46:14] **Tim:** So that takes the pressure off because if you're, if it's directly related to like work related stuff, they're like, oh, I need to impress them.

[00:46:14] **Adam:** Yeah.

[00:46:20] **Tim:** But if, like, if you take that pressure off and they answer that, then it's easier to answer the next question, which is, you know, so what little side projects coding do you have?

[00:46:29] **Tim:** And now they're already in the mood of sharing.

[00:46:32] **Adam:** Mhm.

[00:46:33] **Ben:** Oh man.

[00:46:34] **Ben:** I was, I was in an interview on the other side one time and the guy, I think the question that they asked me was like, tell me about a time in which, someone disagreed with you and then you changed their mind.

[00:46:47] **Ben:** And I was like, oh, bro, I don't think I've ever changed anyone's mind on anything.

[00:46:53] **Adam:** And did you get that job, Ben?

[00:46:55] **Ben:** No, I did not.

[00:46:58] **Tim:** Mhm.

[00:46:58] **Ben:** But I told him, I was like, look, I, I'm like, uh, I don't think I've.

[00:47:01] **Adam:** I find that, I find that fascinating, Ben, because I mean, and I mean this in the best possible way.

[00:47:06] **Adam:** I love, I love this about you.

[00:47:08] **Adam:** You love to argue

[00:47:12] **Tim:** Sa.

[00:47:13] **Adam:** like you have an opinion and you love to express your opinion and try to like convince people and like uh, hear other people's opinions.

[00:47:15] **Ben:** Yes, I have strong opinions.

[00:47:20] **Adam:** I think that's an important part of the way that you argue.

[00:47:22] **Adam:** But you're fascinated about the craftsmanship and like you want to see how other people do it and learn why they do it their way and how is it different from your way.

[00:47:31] **Adam:** And that's an important part of growth.

[00:47:33] **Ben:** Fun fact.

[00:47:34] **Ben:** None of that is convincing.

[00:47:38] **Tim:** M.

[00:47:38] **Tim:** He said you love to argue, not that you're good at it.

[00:47:41] **Ben:** Yo.

[00:47:41] **Ben:** Like, I literally don't think I have ever changed anyone's mind at work ever.

[00:47:46] **Ben:** It's.

[00:47:46] **Ben:** I, uh, can't think.

[00:47:47] **Adam:** That can't be true.

[00:47:47] **Ben:** Really, I can't.

[00:47:48] **Adam:** They wouldn't have made you the leader of the Rainbow Team

[00:47:48] **Ben:** I don't think I can think.

[00:47:50] **Ben:** I don't think I can think of a single time

[00:47:55] **Adam:** Maybe that's a failure of your memory.

[00:47:58] **Ben:** Maybe.

[00:47:58] **Ben:** Let's, I'll, let's chalk it up to that.

## [00:48:00] Cover Letters and Following Directions

[00:48:00] **Tim:** There you go.

[00:48:00] **Adam:** Okay, so, we talked about the interview questions that you can ask.

[00:48:01] **Tim:** Mhm.

[00:48:04] **Adam:** Ah.

[00:48:04] **Adam:** As the interviewer, I do want to go circle back to being the interviewee or the, the job applicant.

[00:48:09] **Adam:** We talked about, you know, maybe certain things to include in your resume.

[00:48:13] **Adam:** One thing we touched on earlier that I'm curious about your feelings on is cover letters.

[00:48:17] **Ben:** Mhm.

[00:48:18] **Adam:** And I asked this specifically because I, I posted a job, I don't know what was it a year ago and change.

[00:48:21] **Tim:** Mhm.

[00:48:25] **Adam:** Maybe it was like a year and a half ago.

[00:48:26] **Adam:** And I swear, if I, and I.

[00:48:29] **Adam:** The job application specifically said I want to see this in your cover letter and then also include your resume.

[00:48:34] **Adam:** And if I eliminated everybody who didn't even bother to include a cover letter, then we would have had like two applicants out of like 200.

[00:48:42] **Tim:** Yeah.

[00:48:43] **Adam:** Like so you can't.

[00:48:43] **Ben:** That's wild.

[00:48:44] **Ben:** Uh,

[00:48:45] **Adam:** I know, like, maybe, honestly, maybe that's the signal.

[00:48:48] **Adam:** Maybe it's like, uh, I should just eliminate that 198.

[00:48:51] **Adam:** And uh, if that, if the pool is too small, then it means I haven't cast a wide enough net.

[00:48:55] **Adam:** Right.

[00:48:55] **Adam:** You know, maybe that's the case.

[00:48:57] **Adam:** But I want to hear your opinions on cover letters and other

[00:48:57] **Ben:** Mhm.

[00:49:01] **Adam:** like you mentioned, you know, putting the white text in a white background to, to try and trick AI stuff.

[00:49:06] **Adam:** But like,

[00:49:08] **Adam:** uh, so a similar signal for me is when I have people schedule, for their in person or not their remote interviews.

[00:49:15] **Adam:** I say, um, wear headphones and be prepared to show up on camera.

[00:49:19] **Ben:** Mhm.

[00:49:20] **Adam:** And if they come to that interview and they're not wearing headphones, for me that's like huge red flag.

[00:49:20] **Tim:** Right.

[00:49:25] **Adam:** It's not an immediate disqualification, but it's like you are 99% disqualified at that point.

[00:49:31] **Tim:** Yeah.

[00:49:32] **Tim:** As far as cover letters go, I don't, we've never asked for those and I think a lot of, we use a lot of enterprise HR software.

[00:49:41] **Tim:** I think it strips that stuff out anyway, so, so that's kind of hard to answer.

[00:49:43] **Adam:** Yeah.

[00:49:45] **Adam:** Interesting.

[00:49:46] **Tim:** But I mean, basically what you're doing is you're doing some sort of

[00:49:46] **Ben:** I feel like.

[00:49:50] **Tim:** compliance test, right?

[00:49:52] **Tim:** You're, you're basically asking for a specific.

[00:49:54] **Adam:** Mhm.

[00:49:55] **Adam:** Can you follow directions?

[00:49:56] **Tim:** Right.

[00:49:56] **Tim:** Can you follow directions Which I, I think is good, but it's like,

[00:49:56] **Adam:** M.

[00:49:58] **Adam:** Yeah.

[00:49:58] **Ben:** If there is a company.

[00:50:01] **Tim:** I mean some of the best developers I know don't follow directions.

[00:50:04] **Tim:** So I don't know.

[00:50:06] **Tim:** I mean, you're weeding them out for compliance on the interview, but you might be weeding out people who are actually pretty good at their jobs but just like

[00:50:14] **Tim:** they're like confident they're getting hired.

[00:50:14] **Adam:** Yeah.

[00:50:14] **Adam:** I mean

[00:50:16] **Adam:** the, I think the flip side of that coin is it's attention to detail.

[00:50:20] **Adam:** Right.

[00:50:20] **Adam:** It's a.

[00:50:21] **Adam:** And I'm, I'm not talking about my job interview or my job description was that long.

[00:50:24] **Adam:** It was like three paragraphs, max.

[00:50:26] **Adam:** Right.

[00:50:26] **Tim:** Yeah,

[00:50:26] **Adam:** And one of them is, you know, this is what I want to see in your cover letter.

[00:50:29] **Adam:** And you're like,

[00:50:30] **Tim:** I would think AI would be good at complying with that.

[00:50:32] **Tim:** Honestly, I think AI would do better.

[00:50:32] **Adam:** you would think,

[00:50:33] **Tim:** Yeah.

[00:50:34] **Ben:** Mhm.

[00:50:35] **Adam:** you, you had mentioned, like, you need a, you need to put something in your resume that kind of tells your story.

[00:50:39] **Adam:** And to me, that's what my cover letter has always been in the past.

[00:50:40] **Tim:** Mm.

[00:50:40] **Tim:** Mhm.

[00:50:42] **Tim:** Gotcha.

[00:50:43] **Tim:** Okay.

[00:50:43] **Ben:** Yeah.

[00:50:44] **Ben:** Plus I think in my mind, if I was.

[00:50:47] **Ben:** So, uh, I, uh.

[00:50:49] **Ben:** The companies you apply to, I think, fall into two categories.

[00:50:50] **Tim:** Mhm.

[00:50:52] **Ben:** There's the dream companies.

[00:50:54] **Ben:** These are the ones that I really love to work for and I have actual concrete reasons that I would want to work for them.

[00:50:54] **Adam:** Mm, mhm.

[00:51:00] **Ben:** And then there's the, this is a company I'd be good at.

[00:51:03] **Ben:** And I need a job.

[00:51:05] **Adam:** Mm, mhm,

[00:51:05] **Ben:** And certainly the first category, the, you know, the big swings.

[00:51:10] **Ben:** This is where I want to be.

[00:51:12] **Ben:** Um, I'm 100%, including a cover letter there.

[00:51:14] **Ben:** So I can explain why it is that I truly want to work at this company and why I think I'd be a good fit and why I've wanted to work here for a long time and what is that I love about the company and how, you know, great you guys are at xyz and then for the rest, uh, I don't know.

[00:51:26] **Tim:** Mhm.

[00:51:29] **Ben:** It probably depend on how burnt out I feel at that point.

[00:51:31] **Adam:** Mhm.

[00:51:33] **Tim:** Fair.

[00:51:33] **Adam:** Yeah.

[00:51:33] **Adam:** I mean, these days you're submitting hundreds and hundreds of job applications if you're trying to get a job, from what I hear.

[00:51:38] **Adam:** So uh, writing a cover letter for each of them has got to be the worst.

[00:51:39] **Ben:** Oh.

[00:51:44] **Ben:** Uh, it makes me sick just to think about it.

[00:51:47] **Tim:** Yeah,

[00:51:48] **Adam:** Okay, All right, well then

[00:51:49] **Tim:** We ain't hired nobody, but

[00:51:51] **Adam:** we don't, we don't have any open positions.

[00:51:53] **Adam:** Don't apply.

[00:51:54] **Tim:** okay, okay, fair enough.

## [00:51:54] Patreon

[00:51:54] **Adam:** Um, so this episode of Working Code is brought to you by writing a cloud fusion skill to do your job for you

[00:52:01] **Ben:** Mhm.

[00:52:01] **Adam:** and listeners like you.

[00:52:03] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:52:09] **Adam:** Our patrons cover our, uh, recording, editing and transcription costs.

[00:52:12] **Adam:** And we couldn't do this every week without them.

[00:52:14] **Adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

## [00:52:18] Thanks For Listening!

[00:52:18] **Adam:** And after show, we're going to go record the after show.

[00:52:21] **Adam:** We have some fun stuff to talk about tonight.

[00:52:23] **Adam:** I'm going to do a followup on my Ninja Creami um, which I mentioned on last week's after show.

[00:52:27] **Ben:** Hahaha.

[00:52:27] **Tim:** Mhm.

[00:52:30] **Adam:** Ben, uh, is going to talk about something called The Invite That's all the information that I have.

[00:52:34] **Adam:** And Tim wants to talk about, how his son Max's job interview with Silvervine went.

[00:52:39] **Adam:** So, that's going to be chock full of great information.

[00:52:40] **Ben:** Mhm.

[00:52:43] **Adam:** So if you want to get to after show, it's real easy.

[00:52:45] **Tim:** And why wouldn't you?

[00:52:46] **Ben:** Sa.

[00:52:46] **Adam:** Yeah.

[00:52:47] **Adam:** It's real easy.

[00:52:48] **Adam:** You go to patreon.com/workingcodepod Throw us a few bucks and you'll get the after show for this and all prior shows and all future shows.

[00:52:57] **Adam:** and we greatly appreciate your support.

[00:52:59] **Adam:** That's gonna do it for us this week.

[00:53:00] **Adam:** We'll catch you again next week.

[00:53:01] **Adam:** And until then,

[00:53:02] **Tim:** So I read your cover letter

[00:53:06] **Tim:** and it says you're awesome because your heart matters.
