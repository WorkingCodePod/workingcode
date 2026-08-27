---
title: "271: Slop Is the New Clean"
description: "You read code ten times for every time you write it, so you'd better make it readable. This week we discuss who clean code is for now that machines are the ones reading it."
date: 2026-08-27
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/976969c9-20b4-4738-b04e-d1a61696aeb0"></script>
<div class="redcirclePlayer-976969c9-20b4-4738-b04e-d1a61696aeb0"></div>

Uncle Bob wrote the book on clean code, and the whole argument rests on one number: you read code ten times for every time you write it, so you'd better make it readable. His agents write it now, and he doesn't read a line. This week we discuss who clean code is for now that machines are the ones reading it.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Uncle Bob on Software Fundamentals in the Age of AI](https://www.youtube.com/watch?v=zcLPGC-tvgk) — the Matt Pocock interview the whole episode is a reaction to. Yes, he's in a bathrobe.
- [Infisical](https://infisical.com/) — where Adam moved his secrets after a long-running agent read his `.env` and cheerfully told him so.

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/271-slop-is-the-new-clean.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Tim:** basically said he has stopped reviewing agent written code on purpose.

[00:00:04] **Tim:** That blew my mind.

[00:00:04] **Ben:** Yeah,

[00:00:05] **Tim:** All right, so here's a dude who loves the shape of the code.

[00:00:06] **Adam:** Yeah.

[00:00:06] **Adam:** Okay.

[00:00:06] **Adam:** That was pretty surprising,

[00:00:10] **Tim:** He reminds me very much of you, Ben.

[00:00:11] **Tim:** Like, he likes, he wants to see beautiful elegant code and he's like, I don't even want to look at it anymore.

[00:00:37] **Adam:** Okay, here we go.

[00:00:37] **Adam:** It is show number 271.

[00:00:38] **Adam:** And on today's show we're going to talk about clean code in the age of agentic coding.

[00:00:42] **Adam:** Carol's not able to be with us up, tonight.

[00:00:44] **Adam:** She's out sick.

[00:00:45] **Adam:** so it's just the gentleman.

[00:00:47] **Adam:** Say hi, gentlemen.

[00:00:48] **Ben:** Good sir.

[00:00:48] **Tim:** Um, oh, I'm not, I'm no gentleman.

[00:00:50] **Adam:** uh, your suits beg to differ.

[00:00:52] **Adam:** Anyway, uh, but first, as usual, let's start with our triumphs and fails.

## [00:00:56] Tim's Triumph

[00:00:56] **Adam:** And Tim, I'm going to come to you first.

[00:00:58] **Adam:** What's going on, man?

[00:00:59] **Tim:** All right, so I am going for a triumph.

[00:01:04] **Tim:** So I'm calling this drinking from the fire hose when it comes to non programming tasks.

[00:01:10] **Tim:** So one of, one of the things our company does and like everyone, not everyone, but like particularly leadership they're involved in this is the evaluation

[00:01:10] **Adam:** Okay.

[00:01:16] **Ben:** Sa.

[00:01:21] **Tim:** of companies that we choose to target for our continual eating machine that eats companies and rolls them into

[00:01:29] **Adam:** Mhm.

[00:01:31] **Tim:** the Constellation Software

[00:01:35] **Tim:** family.

[00:01:35] **Tim:** Make sure they're a good fit.

[00:01:37] **Tim:** we're not usually looking for profitable companies,

[00:01:40] **Ben:** Mhm mhm.

[00:01:41] **Tim:** but we are looking for companies that have some.

[00:01:44] **Tim:** We don't really look for synergies, but we do look for things that kind of fit into

[00:01:49] **Adam:** Mhm.

[00:01:50] **Tim:** the family of companies that we deal with.

[00:01:52] **Tim:** And we, So we got a whole list, I got a whole list of like 15 different companies that have been on like our target list and they wanted.

[00:02:00] **Tim:** And they're all payment because, um, even though we rolled it down, I'm still sort of the resident payment billing, electronic fintech kind of guru in the company.

[00:02:12] **Tim:** And so they hand it off to me and say, all right, here's 15 companies that we're looking at.

[00:02:12] **Adam:** Okay.

[00:02:16] **Tim:** Can you evaluate them and see?

[00:02:18] **Tim:** You know, because these M and A, M and A guys, M and A guys, they don't really know the business, right?

[00:02:19] **Ben:** That's a lot of companies.

[00:02:21] **Ben:** Mhm mhm.

[00:02:24] **Tim:** They just know, they look at the balance in the ledger.

[00:02:27] **Tim:** They usually look at companies that aren't profitable but do have, uh, a large amount of recurring revenue.

[00:02:32] **Tim:** And so they wanted.

[00:02:32] **Tim:** All right, technology wise, which one of these companies are interesting?

[00:02:36] **Tim:** Like which ones are like, have potential to grow, which ones are like just dealing with old stuff that's probably just going to die and not that that's a bad thing.

[00:02:43] **Tim:** Like technologies that are going to die, you can still make a lot of money over them over the years.

[00:02:48] **Tim:** Um, you just.

[00:02:48] **Adam:** M.

[00:02:48] **Adam:** Just like a ColdFusion.

[00:02:49] **Tim:** Exactly, you just need to know, you just need to know what bucket that is.

[00:02:52] **Tim:** Is that, is there an upside to the growth or is there like, are we just planning to buy this and you know, not spend any money like, uh, trying to grow the product because the product is pretty much destined to die no matter how much.

[00:02:58] **Adam:** M.

[00:03:04] **Adam:** Maintenance mode.

[00:03:04] **Adam:** Yeah.

[00:03:05] **Tim:** Enter maintenance mode, you know, so that completely changes the evaluation of how much you offer to pay for a company.

[00:03:10] **Tim:** There's growth potential, there's more money if there's no growth potential.

[00:03:11] **Ben:** Mhm mhm.

[00:03:11] **Adam:** Mhm.

[00:03:14] **Tim:** But they have a lot of customers, um, you still can possibly buy them.

[00:03:17] **Tim:** So, um, that is usually takes me weeks.

[00:03:21] **Tim:** And so my CEO dropped on me like a list of 15 companies and she's like, yeah, so they want this I'm sorry I didn't get to see sooner, but, uh, we kind of need this by,

[00:03:33] **Tim:** you know, end of next week.

[00:03:35] **Tim:** Crap.

[00:03:35] **Tim:** Okay, great.

[00:03:37] **Adam:** Seem to take like, uh, would you say a week per.

[00:03:41] **Tim:** So it's the beginning of the week.

[00:03:43] **Tim:** So it's like she sent it to me Monday and then it's like she needs it by,

[00:03:48] **Tim:** uh, Friday of not this week, but next week.

[00:03:48] **Ben:** Mhm.

[00:03:50] **Tim:** So basically almost two weeks.

[00:03:51] **Tim:** 20 total,

[00:03:51] **Adam:** Right.

[00:03:52] **Adam:** But you said it used to take you how long to do one of these.

[00:03:55] **Tim:** two to three weeks.

[00:03:56] **Tim:** Right?

[00:03:57] **Adam:** Yeah.

[00:03:57] **Tim:** So, so, but it's like that's me stopping everything and just going, all right, focusing and reading like hundreds of papers and doing Google searches and trying to figure out, right, what's this guy?

[00:04:06] **Adam:** Mhm.

[00:04:08] **Tim:** What are these people's business model?

[00:04:09] **Tim:** Do they have any patents?

[00:04:11] **Tim:** do the, you know, uh, who's their competitors, who they own by things, things like that.

[00:04:16] **Tim:** Um, and kind of AI has been.

[00:04:19] **Tim:** It took me three days to do what I normally takes me two weeks to do.

[00:04:22] **Ben:** Dang.

[00:04:24] **Adam:** Wow.

[00:04:24] **Ben:** Pretty good.

[00:04:25] **Tim:** And most of that was.

[00:04:27] **Tim:** So we buy a lot of subscriptions from like these industry experts, right?

[00:04:27] **Ben:** Mhm mhm.

[00:04:27] **Adam:** Mhm,

[00:04:32] **Tim:** So I download their papers and in the day I would read all their papers and try to assimilate that and then apply it to the list.

[00:04:41] **Tim:** But it's like, I gotta admit, Claude was pretty freaking amazing.

[00:04:45] **Tim:** And like, figuring out, I'm like, I basically ingested all of our, like, here's our best practices for how to acquire a company.

[00:04:48] **Adam:** Mhm.

[00:04:52] **Tim:** Claude's like, cool, great, awesome.

[00:04:54] **Tim:** I'm like, here's these industry research, like, what is on the way in, what's on the way out, what are people looking for?

[00:05:01] **Tim:** What are people like trying to get away from?

[00:05:04] **Tim:** Cool.

[00:05:05] **Tim:** It kind of knows the landscape.

[00:05:06] **Tim:** I'm like, all right, here's these companies.

[00:05:08] **Tim:** And it went out and like found patent filings.

[00:05:09] **Ben:** Mhm mhm.

[00:05:11] **Tim:** It found like, some of people are on the stock market.

[00:05:14] **Tim:** So it found all their SEC filings.

[00:05:17] **Tim:** And I double checked because a lot of times, you know, they do make up references.

[00:05:20] **Tim:** I'm like, you need to give me a link to every single thing that you say you found.

[00:05:24] **Tim:** I need.

[00:05:24] **Adam:** M.

[00:05:24] **Adam:** Mhm.

[00:05:24] **Tim:** And I go click that.

[00:05:25] **Tim:** I read it and like, I'll read it.

[00:05:27] **Tim:** It's usually like a 50 page document.

[00:05:30] **Tim:** Like, all right,

[00:05:30] **Adam:** Mhm,

[00:05:32] **Tim:** what in this document was relevant to this question?

[00:05:34] **Tim:** And it was like, I'm like, give me a quote so I can do a find and search.

[00:05:37] **Tim:** Did a find and search.

[00:05:39] **Tim:** That data's there.

[00:05:40] **Tim:** Cool.

[00:05:41] **Tim:** And so like within three days I was able to like narrow down this huge list of, well, not huge, but, you know, this list of 15 different companies to, to narrow it down to, uh, weed it out.

[00:05:52] **Tim:** Some of these companies have been purchased within the past six months.

[00:05:56] **Tim:** So it's like no point even making.

[00:05:57] **Tim:** Don't.

[00:05:57] **Ben:** Mhm mhm.

[00:05:58] **Tim:** Don't make an offer.

[00:05:58] **Tim:** Right?

[00:05:58] **Tim:** They.

[00:05:59] **Tim:** They just got bought out by a, uh, you know, $2 billion company.

[00:06:01] **Tim:** You're not going to be able to out, you know, you know, it just got bought.

[00:06:02] **Adam:** Mhm,

[00:06:04] **Tim:** You're not gonna be able to buy them.

[00:06:05] **Tim:** Some of them were actually not really companies on their own.

[00:06:08] **Tim:** They were actually parts of other companies and always had been.

[00:06:11] **Tim:** But somehow no one ever caught that.

[00:06:12] **Adam:** Mhm,

[00:06:13] **Tim:** Like, this is not a viable product.

[00:06:16] **Tim:** Unless you want to, like, talk.

[00:06:18] **Tim:** You know, that's just a really hard sell.

[00:06:20] **Tim:** So took this list of 15 companies and boiled it down to 2 companies to pursue, 3 companies to continue to watch.

[00:06:29] **Tim:** And the rest of them just dropped off the list.

[00:06:30] **Tim:** And one was like, it's a good fit for another

[00:06:33] **Adam:** Mhm,

[00:06:34] **Tim:** company inside of our family because it's like healthcare stuff.

[00:06:39] **Tim:** And I'm m not.

[00:06:40] **Tim:** So I make that sound easy because it's.

[00:06:42] **Tim:** But it's still three days.

[00:06:43] **Tim:** It's a whole lot of reading and challenging because a lot of times, like, Claude was wrong 50 times before I got it to be right.

[00:06:51] **Ben:** Mhm mhm.

[00:06:54] **Tim:** You know what I mean?

[00:06:55] **Ben:** Yeah.

[00:06:55] **Adam:** Mhm.

[00:06:55] **Tim:** It would say something and I'm like, uh, I don't really think that's true.

[00:06:59] **Tim:** And it would go, oh,

[00:07:01] **Tim:** yes, you're right.

[00:07:02] **Tim:** I found this link here.

[00:07:02] **Tim:** I'm like, let me.

[00:07:03] **Tim:** Okay, let me read the link.

[00:07:04] **Tim:** All right, okay.

[00:07:04] **Adam:** Sa.

[00:07:04] **Tim:** That just disproved exactly what you said.

[00:07:06] **Tim:** It's like, okay, so, I mean, but that's.

[00:07:09] **Tim:** And that's the thing.

[00:07:10] **Tim:** It's like, it's still my best guess.

[00:07:13] **Tim:** Which it always was.

[00:07:14] **Tim:** Like, anytime I was asked to do this, it was always my best guess, my judgment field.

[00:07:15] **Adam:** Mhm.

[00:07:17] **Tim:** And people are okay with that.

[00:07:18] **Tim:** But it's like, at least it's now my best guess.

[00:07:21] **Tim:** With references that I probably never would have found on my own.

[00:07:24] **Tim:** I would have just looked at their website and go look at their marketing material.

[00:07:24] **Ben:** Mhm mhm.

[00:07:28] **Tim:** And it found, like, contradictions even within their own people's own or marketing material.

[00:07:33] **Tim:** Like, they're like, this is banking, uh, industry software.

[00:07:37] **Tim:** And it says it's non custodial.

[00:07:39] **Tim:** Non custodial basically means that, um, you're dealing with people's money, but you don't actually have control of their money.

[00:07:46] **Tim:** custodial being like, you shift their money out of their account to your account.

[00:07:50] **Tim:** Now you have custody of that money and you're.

[00:07:52] **Tim:** You have to be responsible.

[00:07:53] **Tim:** And there's a whole bunch of rules that's completely different.

[00:07:56] **Tim:** And you're dealing with someone else's money.

[00:07:56] **Ben:** Mhm mhm.

[00:07:58] **Tim:** And have to deal with that some way and move that around versus it's your money.

[00:08:03] **Tim:** All we're doing is giving you ways to move it around.

[00:08:06] **Tim:** That's completely different methodology of software versus and like they're like, this one says that they uh, have this very special non custodial method.

[00:08:07] **Adam:** Right.

[00:08:15] **Tim:** And then I actually go, you know, Claude helped me, pointed to me to their API that says, well, here's actually what their API says, here's actually what they're doing.

[00:08:23] **Tim:** And it says there that it is custodial.

[00:08:26] **Tim:** It is custodial.

[00:08:27] **Tim:** You're actually moving your money to them.

[00:08:27] **Adam:** Mm.

[00:08:29] **Adam:** Right,

[00:08:29] **Tim:** Like so their marketing material and their development material is in conflict.

[00:08:35] **Tim:** Now there's probably a truth there.

[00:08:35] **Adam:** Right,

[00:08:37] **Tim:** And it's not my job to figure out what's true, but at least that's one more thing because it's not my job to figure out who buys what.

[00:08:38] **Ben:** Mhm.

[00:08:43] **Tim:** I just give the, the guys who are guys, girls who are buying it, data to say while you're doing due diligence, while you're talking to these people, find out about this.

[00:08:43] **Adam:** Right.

[00:08:43] **Adam:** Mhm.

[00:08:52] **Tim:** Why do you say it's not custodial while your API references in your document say it's not?

[00:08:58] **Adam:** Custodial.

[00:08:59] **Adam:** Yeah.

[00:08:59] **Tim:** So custodial.

[00:09:00] **Tim:** Yeah.

[00:09:01] **Tim:** So I'm just saying that, you know, it really helps drinking from the fire hose because that would have just overwhelmed me a few years ago and I would just been like, don't know, here's my guess.

[00:09:08] **Ben:** Mhm.

[00:09:10] **Tim:** But now I can create a nice spreadsheet, hand it to the people and go, I sound really smart.

[00:09:16] **Tim:** So.

[00:09:17] **Ben:** That's a win.

[00:09:17] **Tim:** And that's all I really care about.

[00:09:19] **Tim:** So that's me.

[00:09:22] **Adam:** That's a big one.

[00:09:23] **Ben:** What do you got going on, Adam?

[00:09:23] **Tim:** I'm not doing,

[00:09:25] **Tim:** I'm um, not, I'm not biting that joke.

[00:09:27] **Tim:** What do you got going on, Adam?

## [00:09:29] Adam's Triumph

[00:09:29] **Adam:** I, I also have a triumph.

[00:09:30] **Tim:** Mhm.

[00:09:31] **Adam:** and speaking of difficult to say words, this one's maybe not too difficult, but it's, it's written a little weirdly.

[00:09:36] **Adam:** So it's.

[00:09:37] **Adam:** I learned, about a tool product, I don't know what you call it called Infisical today.

[00:09:42] **Adam:** Infisical as in not physical, however it's spelled I N, F, I S I, C, A L, I.

[00:09:50] **Tim:** So, so, so fiscal as in finance?

[00:09:50] **Ben:** Oh, like in fiscal.

[00:09:53] **Adam:** No, no, no, there's an I between the S and the C

[00:09:54] **Tim:** No,

[00:09:56] **Tim:** um,

[00:09:56] **Ben:** Ah, uh, yeah, gotcha.

[00:09:57] **Tim:** I do not know this word.

[00:09:58] **Adam:** I.

[00:09:58] **Adam:** I think it's supposed to be like uh, a pun on not physical, like not physically there or something.

[00:10:05] **Adam:** Right.

[00:10:05] **Tim:** Okay.

[00:10:05] **Adam:** However, by spelling it weird, it makes it easier to Google them.

[00:10:09] **Adam:** I think that that's kind of my guess.

[00:10:10] **Ben:** Okay.

[00:10:11] **Tim:** Mhm mhm.

[00:10:11] **Adam:** So.

[00:10:12] **Adam:** But basically, I guess truly this is a failure.

[00:10:16] **Adam:** Uh, I, I got burned, uh, yesterday I was, you know, been working on some new features for Jump Run.

[00:10:16] **Ben:** Mhm mhm, mhm.

[00:10:22] **Adam:** And I've been playing with.

[00:10:24] **Adam:** This is probably gonna be my triumph for next week.

[00:10:25] **Adam:** But I've been playing with the slash goal in ChatGPT Codex, which.

[00:10:30] **Adam:** That's their like long running.

[00:10:31] **Adam:** You know, like you define the end conditions, these are the, the tests that have to pass and these are the things you have to be able to prove before you're allowed to stop.

[00:10:39] **Adam:** And it'll just run for hours and hours.

[00:10:41] **Adam:** Um, and so I've been playing with that and during one of those runs, you know, it finished its work and at the end it's like oh and by the way, sorry, I also read your file.

[00:10:49] **Tim:** Mhm mhm.

[00:10:50] **Adam:** So I saw all your secrets like you bastard.

[00:10:54] **Adam:** So I went down that rabbit hole today and I ended up finding out about this product called Infisical.

[00:11:00] **Adam:** and basically what it does is you store your secrets on their tool like you could.

[00:11:01] **Ben:** Sa.

[00:11:05] **Adam:** They have self hosting, there's enterprise, a whole bunch of different things.

[00:11:09] **Adam:** But basically the free version, you, you store your secrets in there like cloud environment and then you have a CLI command that you run.

[00:11:11] **Ben:** Mhm.

[00:11:15] **Adam:** So instead of like running npm run dev, you run infisical with some, a couple minor flags or whatever.

[00:11:22] **Adam:** Then dash dash npm run dev.

[00:11:24] **Adam:** And what it does is if you know you're logged into the your Infisical account and it says okay, give me the secrets for this project and it loads them as environment variables just for that one command like in, in the session and then it runs the command.

[00:11:30] **Tim:** Mhm mhm.

[00:11:37] **Ben:** M.

[00:11:37] **Ben:** So

[00:11:40] **Ben:** you have in the past talked about using 1Password for kind of a similar thing.

[00:11:40] **Adam:** So there's no.

[00:11:43] **Adam:** Mm mhm, mm mhm.

[00:11:45] **Ben:** Why not reach for 1Password?

[00:11:48] **Adam:** So a couple of reasons.

[00:11:51] **Adam:** Um, one is that the, the real benefit of the 1Password thing is that the secrets are very.

[00:11:56] **Ben:** Everyone on the team has access to it.

[00:11:58] **Adam:** Yeah, exactly.

[00:11:58] **Adam:** It's, it's very shareable amongst the team.

[00:12:01] **Adam:** and we can have like different vaults and different uh, access levels and that sort of thing.

[00:12:06] **Adam:** And then you can access the secrets from multiple different places, all with one.

[00:12:08] **Tim:** Mhm mhm.

[00:12:09] **Adam:** I'm sorry.

[00:12:11] **Ben:** Mhm

[00:12:11] **Adam:** yeah, with one canonical.

[00:12:13] **Adam:** This is the secret.

[00:12:14] **Adam:** I can read it from a web server, I can read it from my command line, I can read it from a couple of different places.

[00:12:14] **Ben:** sa.

[00:12:19] **Adam:** Um, versus this is, it's a little more simplified and it's a lot easier to set up.

[00:12:23] **Adam:** and it's just I wanted something low stress.

[00:12:25] **Adam:** Right.

[00:12:26] **Adam:** Like the simplest possible thing to set up it actually nicely.

[00:12:30] **Adam:** So.

[00:12:30] **Adam:** I told you this was for Jump Run.

[00:12:32] **Adam:** It nicely integrates with Vercel so that like if I go update a secret in the Infisical website, uh, then it can push that into Vercel for me as well.

[00:12:41] **Ben:** Oh, wow, that's cool.

[00:12:42] **Adam:** Yeah, so

[00:12:42] **Ben:** So it has kind of a background agent, kind of a tasky thing?

[00:12:46] **Adam:** uh, not agentic, but yeah, yeah, it's like a.

[00:12:47] **Ben:** No, no, no, but I mean like it a workflow.

[00:12:48] **Tim:** Mhm mhm.

[00:12:49] **Ben:** It has a background workflow, it can do.

[00:12:50] **Adam:** Yes, it'll it'll push the that out.

[00:12:53] **Adam:** So the, the, the Infisical website becomes the canonical source of my environment variables instead of a dot env file on my computer that I try really hard to not let the LLMs read.

[00:12:56] **Ben:** M very cool.

[00:13:03] **Adam:** So um, I, I, I do still have a few more keys that I have to roll because

[00:13:10] **Adam:** whatever.

[00:13:11] **Adam:** But I finally figured out a way I'm really happy happy with it.

[00:13:11] **Ben:** M very cool.

[00:13:15] **Adam:** So no more env files for my local solo projects.

[00:13:20] **Adam:** So that's it.

[00:13:21] **Adam:** Yeah, I'm happy About that.

[00:13:23] **Adam:** so that's me, Ben.

[00:13:23] **Tim:** Mhm mhm.

[00:13:24] **Adam:** What do you got going on?

## [00:13:25] Ben's Fail

[00:13:25] **Ben:** to go with a failure, but this is like a light philosophical failure.

[00:13:30] **Ben:** Uh, I've talked about the importance of words and people agreeing on what things mean.

[00:13:33] **Ben:** And I, um, you know, many episodes ago I talked about how for years I had a misunderstanding of what a singleton was.

[00:13:40] **Ben:** And I had always thought in ColdFusion, oh, if I just cache a CFC in memory, that's a singleton.

[00:13:41] **Adam:** Mm.

[00:13:45] **Ben:** But that's literally not what a singleton is.

[00:13:47] **Ben:** That's just a long lived cached instance, which is a different thing.

[00:13:52] **Ben:** And uh, you know, there are implications of, of misunderstandings.

[00:13:53] **Adam:** M.

[00:13:56] **Ben:** And adversarial review is another one of these things where I just realized that my understanding in my head has been very different from what the actual term means.

[00:14:04] **Tim:** Mhm.

[00:14:05] **Adam:** You're talking about the, the modern discourse.

[00:14:07] **Adam:** Adversarial review of.

[00:14:09] **Adam:** Of like adversarial, um, agentic code review or whatever.

[00:14:10] **Ben:** Correct?

[00:14:11] **Ben:** Yes, exactly.

[00:14:12] **Adam:** Yeah, okay.

[00:14:14] **Ben:** And, and it's like one of these things where I never knew the definition and I heard someone say the phrase and then I just made up a definition in my mind that sounded right.

[00:14:21] **Adam:** Mhm.

[00:14:23] **Ben:** And I had heretofore, basically, since this morning, uh, or previous to this morning, thought that adversarial review meant you had to have literal different products looking at code like, oh, the code was written by Claude.

[00:14:37] **Ben:** So adversarial review meant it was reviewed by Grok or reviewed by OpenAI.

[00:14:41] **Adam:** Right.

[00:14:41] **Tim:** M.

[00:14:41] **Tim:** I mean that does help.

[00:14:43] **Ben:** It's, it, it's not, so I should say it's, it's not exclusive, to adversarial review.

[00:14:43] **Adam:** Yeah.

[00:14:45] **Tim:** It's not a requirement.

[00:14:46] **Tim:** Mhm mhm.

[00:14:49] **Ben:** It's part of adversarial review possibilities.

[00:14:52] **Ben:** And then I was reading through the Claude Code documentation this morning.

[00:14:55] **Ben:** I'm trying to level up my understanding of how these tools work.

[00:14:59] **Adam:** Mhm,

[00:14:59] **Ben:** And it said that adversarial review is literally just one agent looking at the finished product of another agent with, without the original context.

[00:15:09] **Ben:** Window.

[00:15:09] **Ben:** So it's basically going in blind to what the original intent was.

[00:15:13] **Ben:** And it's just looking at the, the output and judging it on its own merits.

[00:15:15] **Adam:** Mhm.

[00:15:17] **Ben:** Um, but it's, it can be the same product.

[00:15:18] **Ben:** It's, you know, I could literally just have one agent and Claude write it and then a different context, free agent in Claude review it.

[00:15:25] **Ben:** And that's adversarial review.

[00:15:25] **Tim:** Mhm mhm.

[00:15:27] **Ben:** And it's just, uh, I get the failure there.

[00:15:29] **Ben:** Again, it's just that we make up stuff in our heads sometimes, and that made up understanding or let's say misunderstanding or misconstruing can have a negative impact.

[00:15:35] **Adam:** Mhm.

[00:15:43] **Ben:** And I find this also to be the case when we try to create analogies or metaphors that don't quite work, but they kind of sound good on their face, so you just go with it.

[00:15:56] **Ben:** But then having that analogy in your mind changes the way you think about something.

[00:16:01] **Ben:** And this is a little bit tangential, but, um, in the, in the Discord chat earlier today, before the show, we were talking about the var versus const versus let stuff, and we don't need to get into that.

[00:16:07] **Tim:** Mhm

[00:16:15] **Ben:** But,

[00:16:16] **Adam:** Can't imagine why.

[00:16:18] **Ben:** but one of the guys, Sean, uh, I think it was Sean Callahan.

[00:16:21] **Ben:** I don't have my Discord in front of me.

[00:16:22] **Adam:** We have too many Seans.

[00:16:23] **Ben:** You've got a lot of Seans,

[00:16:23] **Adam:** It's one of the Seans.

[00:16:25] **Ben:** his analogy was, I, I've never handled a venomous snake, but why start now?

[00:16:30] **Adam:** Mhm.

[00:16:31] **Ben:** Kind of a thing.

[00:16:32] **Ben:** I don't remember the words offhand, but the reality is, like, there are real reasons to handle a venomous snake.

[00:16:32] **Adam:** Yeah.

[00:16:38] **Ben:** If you want to get venom antidotes, you literally have to milk what's called milking snakes.

[00:16:42] **Adam:** Okay.

[00:16:44] **Ben:** But the point, uh, no, no, no, no, no.

[00:16:44] **Adam:** You don't, you don't need to get var antidotes, Ben.

[00:16:45] **Tim:** Mhm mhm.

[00:16:46] **Ben:** Ah, no, no.

[00:16:49] **Ben:** But, but, but like, like this is the interesting thing here, because his analogy sounds good on its face, but the reality is, again, there are reasons to handle venomous snakes.

[00:16:54] **Adam:** Aha.

[00:16:54] **Adam:** Uh-huh.

[00:16:59] **Ben:** And you do so with the understanding of what the trade off is.

[00:17:03] **Ben:** You're handling something dangerous because you need something from it.

[00:17:04] **Adam:** Mhm.

[00:17:08] **Ben:** Uh, and I think just the var conversation, people look at me and they think, oh, he must have no idea what he's talking about.

[00:17:17] **Ben:** So, so he's saying stupid things.

[00:17:18] **Ben:** But the reality is, is I'm going into my decision making as an educated consumer and I'm weighing the pros and cons and I've chosen something.

[00:17:27] **Tim:** Mhm mhm.

[00:17:28] **Ben:** So it's, it's like, it's sometimes,

[00:17:31] **Adam:** Yeah.

[00:17:31] **Adam:** I mean, even an educated consumer can choose the wrong thing.

[00:17:37] **Ben:** But.

[00:17:38] **Ben:** So the point is that

[00:17:41] **Ben:** sometimes I think we get too,

[00:17:44] **Ben:** anchored to something that isn't a clean analogy or metaphor or definition, and that really can impact the way we think about things going forward.

[00:17:55] **Ben:** And I don't know, it's, I, I don't have a good answer to that.

[00:17:58] **Ben:** That's just a reality of existing in a complex world.

[00:17:59] **Adam:** Yeah,

[00:18:02] **Ben:** And uh, my only, my only antidote is to, bring it up when it happens, to try and be more aware of it.

[00:18:02] **Adam:** for sure.

[00:18:08] **Tim:** Mhm mhm.

[00:18:09] **Adam:** Yeah.

[00:18:09] **Adam:** Yeah.

[00:18:10] **Ben:** that's all I got.

## [00:18:11] Clean Code in the Age of Agentic Coding

[00:18:11] **Adam:** So let's move into the topic we wanted to talk about, clean code in the age of AI, get our own thoughts on it.

[00:18:16] **Adam:** But I guess we should acknowledge up front that this is inspired by a YouTube video that all three of us have seen.

[00:18:19] **Ben:** Mhm,

[00:18:22] **Adam:** That was an interview of Bob Martin, AKA Uncle Bob.

[00:18:27] **Adam:** Um, and the interviewer was Matt Pocock of, TypeScript and more recently AI training fame.

[00:18:36] **Adam:** and I thought the video was really good.

[00:18:37] **Adam:** It's like an hour long.

[00:18:38] **Ben:** Mhm, mhm,

[00:18:38] **Adam:** and he's asking him kind of about this stuff, right?

[00:18:41] **Adam:** Bob Martin is the clean code guy.

[00:18:43] **Tim:** Mhm.

[00:18:44] **Adam:** And more recently, Bob has been, very active in AI discussions.

[00:18:50] **Adam:** And that almost seems at face value, at odds with his software craftsmanship, opinions and his theses.

[00:19:00] **Adam:** And so they got into a good old discussion about, you know, what is it like to try to have opinions on clean code and enforce them, but also step back away from the code a little bit and let the agent do the running.

[00:19:13] **Adam:** And so it was really good video.

[00:19:15] **Adam:** We.

[00:19:15] **Tim:** Yeah, I mean I was super surprised that he like is even on board with this.

[00:19:16] **Ben:** Mhm,

[00:19:19] **Tim:** I thought he'd hate it, but yeah.

[00:19:19] **Adam:** Yeah, yeah, I figured we would just kind of like, go through the high points.

[00:19:20] **Tim:** Um.

[00:19:22] **Tim:** Mhm.

[00:19:24] **Adam:** And I'm sure that there's some stuff in there that uh, want to discuss.

[00:19:29] **Adam:** I, you know, the.

[00:19:30] **Adam:** Toward the beginning of the video, he throws up, uh, an analogy that I really liked, which was that, agentic coding and LLMs.

[00:19:37] **Adam:** I mean, I, I personally am trying to, as much as possible stray away from calling it AI.

[00:19:44] **Adam:** To me, it's not AI.

[00:19:45] **Adam:** You know, it's.

[00:19:45] **Ben:** Mhm.

[00:19:46] **Adam:** I hate that because it's like calling it as AI is, is, like a marketing term.

[00:19:49] **Adam:** It's meant to make you feel like it's smarter and better than it actually is.

[00:19:52] **Tim:** Mhm.

[00:19:53] **Ben:** Right?

[00:19:54] **Adam:** And so I'm trying very hard to just call it LLMs.

[00:19:56] **Adam:** But either way, uh, the agentic coding stuff is fast.

[00:19:59] **Adam:** But to.

[00:20:00] **Tim:** Mhm sam.

[00:20:00] **Adam:** To paraphrase him, he says it leaves little bits of dog do behind.

[00:20:02] **Ben:** Mhm.

[00:20:04] **Adam:** Um, which is.

[00:20:05] **Adam:** I think we could probably all agree with that, right?

[00:20:07] **Adam:** Like, it Writes code, writes a lot of code fast.

[00:20:10] **Adam:** And if you're not careful, it can write bad code.

[00:20:13] **Adam:** Right.

[00:20:14] **Ben:** Yeah, absolutely.

[00:20:15] **Ben:** The phrase that I, I keep hearing people say these days is that it's an amplifier.

[00:20:17] **Tim:** Mhm.

[00:20:19] **Adam:** Okay.

[00:20:20] **Ben:** So if you make good choices, it amplifies good choices and if you make bad choices, it amplifies bad choices.

[00:20:25] **Adam:** Right.

[00:20:27] **Adam:** So, um, you know, I guess then they dig into, How do you recognize the bad parts that are coming out of the LLM, right, the code that it generates.

[00:20:30] **Ben:** Mhm.

[00:20:36] **Tim:** Mhm.

[00:20:38] **Adam:** Um, and that's a really interesting question how, you know, like, it's one of those things that I think we don't truly understand that we're doing a lot of times, right?

[00:20:46] **Adam:** We have this career, and a lot of experience and then we look at something, we go, oh, this is ugly, this is bad.

[00:20:52] **Adam:** This could be better written.

[00:20:53] **Adam:** But we don't truly understand why.

[00:20:57] **Ben:** Well,

[00:20:58] **Ben:** it's so fascinating because it reminds me of the George Carlin bit.

[00:21:02] **Ben:** I think we've even mentioned it on the show before that you ever notice how on the highway everyone who goes faster than you is a maniac and everyone who goes slower than you as an idiot?

[00:21:03] **Adam:** Mm.

[00:21:03] **Adam:** Mhm.

[00:21:06] **Adam:** Hm.

[00:21:10] **Tim:** Idiot.

[00:21:10] **Adam:** Yeah.

[00:21:11] **Tim:** Yeah.

[00:21:11] **Ben:** Yeah, you know, I, to me a little bit, clean code is like that.

[00:21:11] **Adam:** Yeah.

[00:21:11] **Tim:** 100%.

[00:21:16] **Ben:** It's like, do you ever notice that the people who agree with my standards like clean code and the people who don't agree with them are idiots?

[00:21:16] **Adam:** Mm.

[00:21:17] **Tim:** Mhm.

[00:21:22] **Adam:** Yeah.

[00:21:22] **Ben:** You know, like, he talks about things like cyclomatic complexity and function length and you uh, know a bunch of other stuff that he kind of glossed over.

[00:21:31] **Adam:** Mhm.

[00:21:33] **Ben:** And those are all very valid.

[00:21:35] **Ben:** When I think about clean code, one of the things that I nitpick on is, is how the order of the methods are in my components.

[00:21:36] **Tim:** Sam.

[00:21:37] **Tim:** Mhm.

[00:21:42] **Ben:** I uh, like to have my public methods at the top and they have to be alphabetically ordered.

[00:21:45] **Ben:** And I like to have my private methods at the bottom and they have to be alphabetically ordered.

[00:21:49] **Ben:** And so in my mind, if an agent produces code that doesn't adhere to that standard, I'm like, that's a problem because I want clean code and that's not clean in my mind.

[00:22:00] **Adam:** Interesting.

[00:22:00] **Ben:** But he might look at that and be like, well, that's not irrelevant because the code just has to execute properly.

[00:22:01] **Adam:** Yeah.

[00:22:06] **Ben:** And as long as I have the tests and the CRAP scores passed, then it's clean.

[00:22:09] **Adam:** Right?

[00:22:10] **Ben:** So it's like, well, so then your definition of clean is just a little different.

[00:22:14] **Tim:** Mhm.

[00:22:15] **Adam:** Yeah.

[00:22:16] **Adam:** I've never been a super fan of the alphabetical thing, but I do understand why people like it.

[00:22:20] **Adam:** Right?

[00:22:20] **Adam:** When you're trying to find where the function is, it is nice to be able to just know, okay, based on where this is where I am.

[00:22:26] **Adam:** I know either need to go up or down in the file.

[00:22:29] **Adam:** It's.

[00:22:30] **Adam:** It can only be one, uh, if they're in alphabetical order.

[00:22:33] **Adam:** However, you know, with the modern IDEs,

[00:22:34] **Ben:** Mhm.

[00:22:35] **Tim:** In the age of AI, that absolutely matters.

[00:22:38] **Tim:** Zero.

[00:22:38] **Tim:** Right?

[00:22:38] **Adam:** right?

[00:22:38] **Adam:** And even it.

[00:22:39] **Adam:** Even pre.

[00:22:40] **Adam:** AI in modern IDEs, right, you know, you can command click or control click or whatever on the function name when you're trying to.

[00:22:45] **Tim:** Yeah.

[00:22:45] **Adam:** Okay, you know, you, you need to go to that function because it was referenced somewhere and you need to like dig into that.

[00:22:50] **Adam:** Like, what does that do that's important to what my, what I'm debugging or whatever now.

[00:22:54] **Adam:** You know, we've got so much better tooling.

[00:22:55] **Adam:** It'll just jump you right there even if it's in another file, depending on the tooling and the language that you're in and stuff.

[00:22:59] **Tim:** Mhm.

[00:23:01] **Adam:** so I don't think that that is as necessary anymore.

[00:23:03] **Adam:** And I think that, uh, as far as LLMs are concerned, you know, they're just going to grep through the file, you know, give me the line that says function foo and then, okay, it's on line 74.

[00:23:09] **Ben:** Right.

[00:23:10] **Tim:** Right.

[00:23:13] **Adam:** Give me 74 plus 10.

[00:23:14] **Adam:** And if it's not, if that doesn't include the end of the function, then give me another 10 and give me another 10 until it gets to the end of the function.

[00:23:20] **Tim:** Mhm.

[00:23:21] **Tim:** Let me just start with a question for just a general overview question.

[00:23:25] **Tim:** Is There anything he said that surprised you or shocked you?

[00:23:29] **Tim:** Because I have one very specific example in mind that just completely surprised me that he would say because we've read his books.

[00:23:36] **Ben:** I,

[00:23:37] **Tim:** I uh, followed him for years.

[00:23:38] **Adam:** Yeah,

[00:23:40] **Adam:** you, uh, know, I don't know if there's anything that necessarily surprised me.

[00:23:44] **Ben:** I have one thing that surprised me, I think

[00:23:46] **Tim:** I have one thing too.

[00:23:47] **Tim:** Why don't you do yours, Ben?

[00:23:48] **Ben:** me, I, uh, so the, the one thing that surprised me, and this is probably something he maybe didn't even mean or I'm misconstruing, but when he's talking in the beginning about the CRAP scores, basically looking at, he Said like, oh, I Learned about this 20 years ago.

[00:23:49] **Tim:** Yeah,

[00:23:59] **Adam:** Mhm.

[00:24:03] **Ben:** And.

[00:24:03] **Ben:** But I was too complex to do.

[00:24:05] **Tim:** Mhm.

[00:24:05] **Adam:** Mhm.

[00:24:05] **Ben:** And then when the agents came out, they could do all the CRAP scores really quickly.

[00:24:10] **Ben:** And at first I was manually going in and reviewing.

[00:24:12] **Ben:** And then I would take the response and I would go and I would like, I would fiddle with the functions.

[00:24:18] **Ben:** But then that was really challenging because then I would have to fiddle with the test to get the test to pass again.

[00:24:21] **Tim:** Mm mhm,

[00:24:21] **Ben:** And I was like, wait a minute, you're fiddling with the tests to get the code to work.

[00:24:23] **Adam:** Yeah.

[00:24:27] **Adam:** Oh, no, no, no, no.

[00:24:28] **Ben:** I'm like, I thought the whole point was that you don't have to fiddle with the tests and you can refactor internally

[00:24:28] **Adam:** You.

[00:24:29] **Adam:** I think you're.

[00:24:34] **Adam:** I think you're misinterpreting what he said there, Ben.

[00:24:35] **Ben:** and.

[00:24:38] **Ben:** Well, that's what I'm saying is like, that's what I'm saying is I'm.

[00:24:40] **Ben:** I was probably misinterpreting, but my, uh, my.

[00:24:42] **Adam:** Yeah.

[00:24:43] **Ben:** The, the thought that I always had when thinking about clean code was that you're hiding the implementation details.

[00:24:50] **Ben:** So if you wanted to refactor a function to get rid of some of the cyclomatic complexity, theoretically you shouldn't be testing any of those implementation details anyway.

[00:24:55] **Adam:** Mhm.

[00:24:59] **Ben:** You should be testing the boundaries of stuff.

[00:25:02] **Tim:** Mhm.

[00:25:02] **Adam:** Yes and no.

[00:25:03] **Ben:** So the fact that he would have to rejigger tests just because he was refactoring functions, I was like that.

[00:25:07] **Ben:** That's a little smelly

[00:25:09] **Adam:** there, there's, there's a.

## [00:25:10] CRAP Scores and Cyclomatic Complexity

[00:25:10] **Adam:** I think we've, we've started to use several, abstracted words here, and I think we need to take a.

[00:25:14] **Ben:** Yeah.

[00:25:14] **Tim:** Yes,

[00:25:15] **Adam:** Take a break and, uh, define a few things.

[00:25:17] **Tim:** bring it.

[00:25:17] **Tim:** Bring us in Chemo.

[00:25:19] **Tim:** Sabiha.

[00:25:19] **Adam:** Okay, so let's start with CRAP.

[00:25:21] **Adam:** You.

[00:25:21] **Adam:** You've used the word CRAP a couple of times.

[00:25:22] **Ben:** Yes.

[00:25:22] **Ben:** Sorry.

[00:25:23] **Adam:** It's, it's an acronym.

[00:25:24] **Adam:** and I, I didn't.

[00:25:26] **Adam:** I was not previously aware of this.

[00:25:28] **Adam:** Uh, this, this video was the first time I'd ever heard of it.

[00:25:28] **Ben:** No, I had never heard of it either.

[00:25:30] **Adam:** So I looked it up.

[00:25:31] **Adam:** It stands for Change Risk Anti-Patterns, and it's a metric.

[00:25:31] **Ben:** Mhm.

[00:25:36] **Adam:** So Change Risk Anti-Patterns.

[00:25:38] **Adam:** That's the CRAP score.

[00:25:39] **Adam:** And it's, it's just this, like, algorithm that you can run where you plug in a cyclomatic complexity value, which we'll come back to what that is, and your code coverage percentage.

[00:25:48] **Ben:** Sa.

[00:25:49] **Adam:** Right?

[00:25:49] **Adam:** So percentage is a number between 0 and 1.

[00:25:50] **Tim:** Mhm,

[00:25:52] **Adam:** 97% is 0.97.

[00:25:53] **Ben:** Mhm.

[00:25:54] **Adam:** You, you plug those variables in, you get a CRAP score.

[00:25:56] **Tim:** Mhm.

[00:25:57] **Adam:** And then I think the thing that I saw said, like, CRAP score below 30 is generally considered acceptable.

[00:26:04] **Adam:** And you can kind of tweak from there based on your own preferences.

[00:26:08] **Adam:** Um, and.

[00:26:09] **Adam:** Okay, so what is cyclomatic complexity then, right?

[00:26:13] **Adam:** Do one of you guys want to take a stab at describing it?

[00:26:15] **Adam:** I can, I can do it if neither of you want to, though,

[00:26:18] **Ben:** Uh, I have roughly heard it.

[00:26:20] **Ben:** I mean, in my mind it was indentation mostly.

[00:26:23] **Ben:** But I know you.

[00:26:24] **Adam:** Right?

[00:26:24] **Ben:** We talked in the pre show.

[00:26:25] **Ben:** That that's not.

[00:26:26] **Ben:** That's very, very simplistic.

[00:26:28] **Adam:** It's a simplistic, easy way to think about it.

[00:26:31] **Adam:** Yeah,

[00:26:32] **Adam:** I guess that's.

[00:26:33] **Adam:** You're inviting me to define it or.

[00:26:34] **Tim:** Uh, I'll let you, I'll let you do it.

[00:26:35] **Adam:** Go ahead.

[00:26:36] **Tim:** You're very good at that.

[00:26:36] **Adam:** Okay,

[00:26:36] **Tim:** Do you remember that stuff in your head?

[00:26:38] **Tim:** I don't.

[00:26:39] **Adam:** so cyclomatic complexity is a measure of how complex the function is.

[00:26:43] **Adam:** It's right there in the name.

[00:26:43] **Adam:** And so what it's measuring is.

[00:26:45] **Tim:** Oh, uh, what was I thinking?

[00:26:47] **Adam:** What it's measuring is the number of decisions or logic branches that are happening in that function, right?

[00:26:54] **Ben:** Mhm.

[00:26:55] **Adam:** So every if statement, or else, if, or a case statement or a, for loop or whatever, each of these, like, logic branches, counts as, like, a plus one.

[00:26:59] **Tim:** Mhm,

[00:27:03] **Adam:** So when you're evaluating the cyclomatic complexity of a function, you start with one point because the function exists.

[00:27:10] **Adam:** And then if there's a single if else, then that's, I don't know.

[00:27:15] **Adam:** Don't quote me on it.

[00:27:16] **Adam:** I'm pretty sure if then is one point and you have like, if else, then that's two points, right?

[00:27:19] **Tim:** Mhm, mhm,

[00:27:22] **Adam:** You've got two branches of code there.

[00:27:24] **Ben:** Mhm mhm.

[00:27:25] **Adam:** And so anytime you have one of these branching things.

[00:27:27] **Adam:** So if you have if, else, if, like if A, else if, B, else C, then that's three points, right?

[00:27:34] **Adam:** So each of These branches adds a point to the cyclomatic complexity score of the function.

[00:27:40] **Adam:** Now a naive view of this is, okay, well, every time I'm increasing the indentation level, the score goes up once.

[00:27:48] **Adam:** and potentially that's a, that's a, you know, an easy way to estimate the cyclomatic complexity score of the function.

[00:27:55] **Ben:** Mhm mhm.

[00:27:58] **Adam:** because you can look at it and go, okay, it's indented three times and there's like three sections that indent three times each.

[00:28:03] **Adam:** Uh, and so that's a like plus nine.

[00:28:05] **Adam:** So we'll call it a ten or whatever.

[00:28:07] **Adam:** Um, and you know, realistically, it might be a little bit more.

[00:28:09] **Adam:** It might be a little bit less, whatever.

[00:28:10] **Adam:** But it's a, it's a good way to just like kind of gut feel for what is the complexity of this function.

[00:28:16] **Adam:** So that.

[00:28:16] **Tim:** Mhm.

[00:28:16] **Adam:** Okay, we talked about cyclomatic complexity.

[00:28:18] **Adam:** Talked about CRAP.

[00:28:20] **Adam:** Uh,

[00:28:20] **Tim:** Hold on.

[00:28:20] **Tim:** So I'll uh, uh, point out both of you kind of pinpointed on the exact same thing that you talked around it.

[00:28:28] **Tim:** But that's exactly what surprised me the most.

## [00:28:30] The End of Line-by-Line Code Review

[00:28:30] **Tim:** So he basically said he has stopped reviewing agent written code on purpose.

[00:28:30] **Adam:** Okay.

[00:28:37] **Tim:** That blew my mind.

[00:28:37] **Ben:** Yeah,

[00:28:38] **Tim:** All right, so here's a dude who loves the shape of the code.

[00:28:38] **Adam:** Yeah.

[00:28:39] **Adam:** Okay.

[00:28:39] **Adam:** That was pretty surprising,

[00:28:43] **Tim:** He reminds me very much of you, Ben.

[00:28:44] **Tim:** Like, he likes, he wants to see beautiful elegant code and he's like, I don't even want to look at it anymore.

[00:28:51] **Adam:** Right?

[00:28:51] **Tim:** Right?

[00:28:51] **Tim:** It's, it's like, it's like a dude who's like been obsessed with, with women his whole life.

[00:28:54] **Adam:** M.

[00:28:56] **Tim:** He's like, I don't even want to see their shape.

[00:28:58] **Tim:** I just want them to m.

[00:28:59] **Tim:** Put a bag on.

[00:29:00] **Tim:** And I just know that there are women, uh, and that they work.

[00:29:02] **Tim:** You know what I'm like, that's, that just blows my mind.

[00:29:06] **Ben:** Yeah.

[00:29:06] **Ben:** It is very surprising.

[00:29:07] **Tim:** But his reasons, his reasons are sound and I ah, love it because, because.

[00:29:11] **Adam:** So yeah.

[00:29:13] **Tim:** So look, the.

[00:29:15] **Tim:** What everyone says that the AI paradigm is that you have to keep the human in the middle.

[00:29:17] **Ben:** Mhm mhm.

[00:29:20] **Tim:** And most organizations hear that go, well, where do we keep the human code?

[00:29:20] **Adam:** Mm.

[00:29:20] **Adam:** Mhm.

[00:29:24] **Tim:** Reviews.

[00:29:25] **Adam:** Yeah.

[00:29:26] **Tim:** Right?

[00:29:26] **Adam:** On the edges.

[00:29:26] **Tim:** AI writes, AI writes the code.

[00:29:27] **Adam:** Yeah.

[00:29:28] **Tim:** You have a human look at it.

[00:29:29] **Tim:** And I, I will say that our organization is struggling with that.

[00:29:32] **Tim:** I cannot get people to code review

[00:29:36] **Tim:** for real.

[00:29:37] **Adam:** Yeah, it's a, it's tough.

[00:29:38] **Tim:** Right?

[00:29:39] **Adam:** uh, think honestly what has taken the wind out of my sails as a code reviewer is how easy it is to write code now.

[00:29:46] **Adam:** Like I'm, um, uh, I think it's.

[00:29:46] **Tim:** Yeah,

[00:29:47] **Adam:** We talked about recently how it's making us lazy.

[00:29:49] **Adam:** Right.

[00:29:49] **Adam:** Like I feel like

[00:29:51] **Adam:** making it easier for me to write code has made me less willing to put in effort for other aspects of my job.

[00:29:57] **Adam:** Which is weird, but, but true.

[00:29:57] **Tim:** Yeah,

[00:29:58] **Ben:** Mhm mhm.

[00:29:59] **Tim:** yeah.

[00:29:59] **Tim:** So an actual quote from him, he said if these things talk about the LLMs, the, he says if these things are fast and they are, and if I can constrain them to do a good job.

[00:30:07] **Adam:** Mhm.

[00:30:10] **Tim:** So that's a big if.

[00:30:10] **Tim:** You have to have an ecosystem that you built so that they can do a good job code reviewing that I'm not going to improve, impose my slowness upon them.

[00:30:11] **Adam:** Mm.

[00:30:20] **Tim:** They're with the code, I'm slow with the code.

[00:30:22] **Tim:** So I'm going to let Them have the code and I'm going to deal with the stuff around that to make sure it's all okay.

[00:30:28] **Adam:** Yeah.

[00:30:28] **Tim:** That, that is a, that's a big shot,

[00:30:30] **Adam:** So yeah, you're.

[00:30:31] **Adam:** You're absolutely right.

[00:30:32] **Adam:** And that is a surprising thing to come from him.

[00:30:35] **Adam:** I think the reason maybe that, that didn't register for me as a surprise is the way that he framed it.

[00:30:41] **Adam:** Right.

[00:30:42] **Adam:** He didn't just say, oh, now that we have LLMs, I'm not reading the code anymore.

[00:30:42] **Tim:** Right?

[00:30:45] **Adam:** He's like, we had these LLMs and I built these systems around the LLMs.

[00:30:50] **Adam:** You know, you start for him, it sounds like adversarial code review that Ben mentioned was like step one of like seven or eight that he's got in this like, what do they call it?

[00:30:57] **Ben:** Yeah.

[00:30:59] **Ben:** M.

[00:31:00] **Ben:** Workflows.

[00:31:00] **Adam:** gauntlet.

[00:31:01] **Ben:** Oh yeah.

[00:31:01] **Adam:** The word that Matt used in the video was gauntlet.

[00:31:01] **Ben:** The gauntlet.

[00:31:04] **Adam:** Right.

[00:31:04] **Adam:** So you've got this like, basically you're putting in a request and it goes through like a multi step gauntlet where you know, step one might be write the code.

[00:31:12] **Adam:** Step two is like an adversarial code review.

[00:31:14] **Adam:** Step three is like make it, you know, apply Clean code, you know, cleanup stuff and stuff, you know, more and more and more.

[00:31:14] **Tim:** Mhm.

[00:31:17] **Ben:** Mhm mhm,

[00:31:19] **Tim:** Yeah.

[00:31:20] **Tim:** I mean he's, I mean he says he checks CRAP scores.

[00:31:23] **Tim:** Right.

[00:31:23] **Adam:** Yep.

[00:31:24] **Tim:** Uh, he runs a battery of tests against the.

[00:31:26] **Adam:** Yeah, so he's built all these systems around the output.

[00:31:28] **Tim:** Right.

[00:31:29] **Tim:** And he does occasional spot checks just.

[00:31:32] **Tim:** But line by line, human review thing is gone.

[00:31:35] **Tim:** And that's, that kind of blew my mind because I've been building sort of this tool that I've been talking about the past few months that I've been testing out, um, to do these things.

[00:31:46] **Tim:** And uh, but I always felt like, well, I don't want to take away the code review part, right.

[00:31:50] **Adam:** Yeah,

[00:31:51] **Tim:** Because you can't fire the LLM if they mess up.

[00:31:54] **Tim:** But he's like, no, I just need to make the LLM, the architecture around it, smart enough and tight enough that I only have to do occasional spot checks to make sure it's still doing the thing I told it to do.

[00:31:57] **Ben:** Mhm, mhm.

[00:32:07] **Adam:** Right.

[00:32:08] **Adam:** And that's the thing, I think that is maybe implied there and not, you know, hopefully most of the people that watch the video understood.

[00:32:16] **Adam:** Um, but I think that what he's really getting at is like he's not reading the code anymore because he's built up these deterministic systems, right.

[00:32:24] **Adam:** The linting and the test suites.

[00:32:25] **Tim:** Right.

[00:32:26] **Adam:** And, and yes, yeah, very much so.

[00:32:26] **Tim:** Deterministic being the key word.

[00:32:29] **Adam:** Uh, and as a result of forcing the LLM to keep working until all of these deterministic tests pass, I'm just going to refer to them all as tests.

[00:32:38] **Adam:** Right.

[00:32:38] **Tim:** Right.

[00:32:38] **Adam:** You know, validations, whatever.

[00:32:38] **Ben:** Mhm,

[00:32:39] **Tim:** CRAP scores, whatever.

[00:32:39] **Adam:** Um, yeah, yeah, they're all different ways to validate that the code satisfies different requirements.

[00:32:46] **Adam:** Um, but the end result of that is that he's producing something that is, you know, pretty darn close.

[00:32:51] **Adam:** Call it 99% of what he would have considered clean code to write with his meat fingers.

[00:32:57] **Adam:** and

[00:32:59] **Tim:** I like that.

[00:32:59] **Adam:** I'm, and that kind of jumps right into, I think one of their next points was like, you know, messy, uh, code as input.

## [00:32:59] Messy Code and Agent Reasoning

[00:32:59] **Ben:** Mhm, mhm.

[00:33:06] **Adam:** Right.

[00:33:07] **Adam:** If, if you're, if your existing code base is in a garbage state, then you're going to get garbage out, right.

[00:33:07] **Tim:** Yes.

[00:33:12] **Tim:** Mhm,

[00:33:13] **Adam:** Unless you, unless what you're specifically doing is like doing passes to say, okay, this is our code base, that it works, but we need it to be cleaner.

[00:33:20] **Adam:** We need it, you know, to improve the long term maintainability and readability and that sort of thing.

[00:33:22] **Tim:** Mhm, mhm,

[00:33:25] **Adam:** And uh, you know, just like messy code affects a human's ability to reason about the code, it also affects the LLM's ability to reason about the code, which I think was a brilliant insight.

[00:33:36] **Ben:** I, I have feel like I've always kind of intuited, and I'm not saying that that I mean that I'm right.

[00:33:43] **Ben:** I mean I'm intuited that.

[00:33:44] **Ben:** I guess it just made sense to me at a guttural level that the LLMs would do better in an existing code base than on a greenfield code base.

[00:33:48] **Adam:** Mhm.

[00:33:54] **Ben:** And um, I was watching the Primeagen the other day and he was talking about, I think it's called a demo porn.

[00:34:00] **Tim:** Mhm, mhm,

[00:34:01] **Ben:** And he's like, people are, people are getting so blown away by all these standalone demos.

[00:34:02] **Adam:** Okay.

[00:34:06] **Ben:** Like, oh, I told it to, um, to make Fortnite and it Built Fortnite in two hours and look how amazing it looks.

[00:34:12] **Adam:** M.

[00:34:12] **Adam:** Right,

[00:34:12] **Ben:** And, and he's like, yeah, these demos are really amazing.

[00:34:15] **Ben:** The question is, is the demo that came out the thing that was in your head?

[00:34:20] **Adam:** Right,

[00:34:20] **Ben:** And he said, the moment you have a really concrete vision in your head, your demo is going to fall short because the LLM just can't produce out of thin air the thing that's in your head.

[00:34:31] **Ben:** But if you put it into an existing code base and it has a thousand patterns, you know, of prior art that it can follow, it's going to be able to jam those out really easily.

[00:34:31] **Adam:** Yes,

[00:34:40] **Ben:** And that like, that's just the thing that I've always felt, you know, untested.

[00:34:40] **Adam:** Yeah, yeah,

[00:34:42] **Adam:** yeah.

[00:34:43] **Adam:** The code structure for sure.

[00:34:45] **Adam:** Um, and that, that also goes back to something else they were talking about, like we were talking earlier.

[00:34:48] **Adam:** You know, he's, he's doing the code review and the, and the spec going in, right?

[00:34:52] **Adam:** The LLM, M in the middle, writing the code.

[00:34:53] **Tim:** Mhm.

[00:34:54] **Ben:** Mhm,

[00:34:55] **Adam:** That part is, let's call it basically solved.

[00:34:58] **Adam:** Right.

[00:34:58] **Adam:** But there's all this stuff on the edges.

[00:35:00] **Adam:** The spec writing the planning and the code review and keeping it, writing code, uh, in a style that you want to have in your code base, call it clean code.

[00:35:10] **Adam:** Um, that's still where the work lies.

[00:35:12] **Ben:** Mhm.

[00:35:12] **Tim:** I like what he said.

[00:35:13] **Tim:** He said, these agents are fast and relatively smart, but they're as subject as humans are to messy code.

[00:35:20] **Adam:** Yeah,

[00:35:20] **Tim:** Maybe not as subject, maybe there's a difference in threshold, but the threshold's still there.

[00:35:25] **Tim:** So it's like you, you, give a really crappy code set to a very smart AI.

[00:35:30] **Tim:** It just starts going around circles and fixing and breaking stuff, and fixing and breaking stuff, and fixing and breaking stuff until you're like, stop.

[00:35:35] **Adam:** Yeah,

[00:35:38] **Adam:** yeah.

[00:35:39] **Ben:** It's, it's so fascinating though because I feel like in a lot of the conversations that you hear about AI, people will often allude to the yes, it does xyz, but humans also do xyz, but the machines are still better at it.

[00:35:49] **Adam:** Mhm.

[00:35:54] **Ben:** And I, and again, even going back to my triumph and failure, that we have these things that we say in our head and we paint a picture and does that picture, uh, accurate and is its accuracy or inaccuracy harmful in the way we see the world in the long run?

[00:35:59] **Tim:** Mhm,

[00:36:10] **Ben:** And going back to just an earlier statement about the clean code, uh, I like the way certain methods are ordered, you know, alphabetically, public, private life cycle, that kind of stuff.

[00:36:22] **Ben:** I could write a thousand components and never once make a mistake about the ordering of the methods.

[00:36:29] **Adam:** Mm.

[00:36:29] **Ben:** I could have AI write a thousand components and it would probably misorder, you know, some non trivial number of them.

[00:36:37] **Ben:** And you could say, well that's irrelevant.

[00:36:37] **Tim:** Mhm.

[00:36:39] **Ben:** But I'm like, well but it's not irrelevant because you're telling me that the AI makes fewer mistakes than I do.

[00:36:44] **Adam:** M.

[00:36:44] **Adam:** But,

[00:36:45] **Ben:** But it's like different mistakes.

[00:36:45] **Tim:** But is that an important mistake?

[00:36:47] **Tim:** Right.

[00:36:47] **Ben:** But that's, but right, but that's the point.

[00:36:49] **Ben:** It's like we're, we're painting with these very broad strokes and then.

[00:36:53] **Adam:** But if it's that important to you, then Bob's point here is that you should write a tool that evaluates every file and says okay, and uh, it's like a failing test that says, okay, the functions are out of order in this file.

[00:36:59] **Tim:** Make sure it's alphabetical deterministically.

[00:37:05] **Adam:** Fix that.

[00:37:06] **Ben:** Yeah, yeah, I, I agree that there are mechanisms around it.

[00:37:06] **Tim:** Yeah,

[00:37:10] **Ben:** I guess the, the cautionary tale to me is always we make false equivalences.

[00:37:16] **Ben:** I don't know if that's the right phrasing of it.

[00:37:20] **Adam:** It sounds smart.

[00:37:20] **Adam:** Go with it.

[00:37:21] **Ben:** People, people, people.

[00:37:22] **Ben:** Often when I hear people talk about the uh, way like the, the, the bad ways in which people talk about AI, it is often we will make these grand statements, but then if you attack any particular part of it, we say, well, that's not really what we meant.

[00:37:30] **Adam:** Mhm,

[00:37:37] **Ben:** Actually we meant this much smaller, much easier to prove thing but then we use those easier to prove things as evidence of the grand statements again.

[00:37:46] **Ben:** And um, it's just, you know, it's, it's a weird place to have a conversation.

[00:37:48] **Tim:** Well,

[00:37:51] **Tim:** so, so I'll push back.

[00:37:52] **Tim:** Uh, and maybe the context was wrong on what you're saying, but what I heard you say, Ben, was because we were talking about messy code and how like, you know, AI is going to get it wrong.

[00:37:59] **Adam:** Mhm.

[00:38:03] **Tim:** And I don't know if that's you were responding to when you started off, but you said because it's smarter, because AI is smarter.

[00:38:11] **Tim:** I don't necessarily think it's smarter, I think it's faster.

[00:38:11] **Ben:** Well,

[00:38:14] **Tim:** Right.

[00:38:14] **Tim:** And so that's kind of the point that, that Uncle Bob was making.

[00:38:15] **Ben:** yeah,

[00:38:17] **Tim:** He said, um, that the diagnostic that mattered was not seeing the bad code the AI made.

[00:38:23] **Tim:** He was watching the agent struggle.

[00:38:25] **Ben:** M.

[00:38:25] **Tim:** And the reason he could recognize the struggle is because he's been there.

[00:38:29] **Adam:** Right?

[00:38:30] **Tim:** Right.

[00:38:30] **Tim:** And I think that is where

[00:38:33] **Tim:** we as developers who have been through that struggle can recognize that.

[00:38:38] **Tim:** Because a person who doesn't know the struggle.

[00:38:40] **Tim:** Right.

[00:38:40] **Tim:** Uh, because there's tons of people who just do vibe coding and just let it run and they watch.

[00:38:45] **Tim:** Like the AI, like, oh, it's checking this function.

[00:38:49] **Tim:** Interesting.

[00:38:50] **Tim:** What's checking that function again?

[00:38:50] **Ben:** Sa.

[00:38:51] **Adam:** Mhm.

[00:38:52] **Tim:** Huh?

[00:38:52] **Tim:** Uh, interesting.

[00:38:53] **Tim:** Oh, it's checking that function again.

[00:38:55] **Tim:** What's.

[00:38:55] **Tim:** What's.

[00:38:55] **Ben:** Mhm.

[00:38:56] **Tim:** We would go.

[00:38:57] **Tim:** It's struggling, but a person doesn't know.

[00:38:59] **Tim:** Coding is like this thing does not know what it's doing.

[00:39:02] **Tim:** And we would stop it and figure out what's going on.

[00:39:04] **Tim:** And I think that's.

[00:39:06] **Tim:** And a diagnostic signal that we as people who have done this for decades

[00:39:14] **Tim:** are able to interpret and to fix that.

[00:39:17] **Tim:** People who have not done this for decades would not.

[00:39:19] **Adam:** Mm.

[00:39:19] **Adam:** Mhm.

[00:39:20] **Tim:** And until the point that AI gets either fast enough to just blow through that cycle and somehow get out of it, or get smarter where it doesn't get in there in the first place, at least we have a job for a few years.

[00:39:33] **Ben:** Mhm.

[00:39:33] **Adam:** Yeah, you know.

[00:39:34] **Adam:** Okay, so uh, the, they did wind down the video talking about the future of the profession and I was kind of thinking maybe there might be a few more things to discuss before we get there.

[00:39:40] **Ben:** Yeah, I.

[00:39:44] **Adam:** But the, you know, you,

[00:39:49] **Adam:** the, the way you brought it up there,

[00:39:51] **Tim:** I set it up for you.

[00:39:52] **Adam:** you, you did.

[00:39:52] **Tim:** Go ahead.

[00:39:53] **Adam:** but I don't know, like.

[00:39:55] **Ben:** We don't know.

[00:39:56] **Ben:** We don't.

[00:39:56] **Ben:** Uh.

[00:39:56] **Ben:** Do you want to.

[00:39:57] **Ben:** We could put a pin in it if there's other stuff you want to say.

[00:39:59] **Adam:** Yeah, let's come back to it.

[00:40:01] **Ben:** You don't have to contort.

[00:40:02] **Tim:** We don't need to snail the backlog.

[00:40:06] **Adam:** You know what, he's referencing a YouTube video that.

[00:40:06] **Tim:** M.

[00:40:06] **Ben:** What.

[00:40:09] **Ben:** Okay.

[00:40:09] **Adam:** Ah,

[00:40:10] **Tim:** That you didn't watch.

[00:40:11] **Tim:** But he did.

[00:40:11] **Adam:** yeah.

[00:40:12] **Adam:** um, I think it came up as like a short or a TikTok or something for me.

[00:40:15] **Tim:** It was a short.

[00:40:15] **Tim:** Yeah.

[00:40:15] **Adam:** But either way, anyway, so we talked about deterministic checks.

[00:40:17] **Ben:** M.

[00:40:18] **Adam:** Um, yeah, yeah,

[00:40:18] **Ben:** I mean, if there's something specific you want.

[00:40:20] **Ben:** Otherwise I have something specific.

[00:40:21] **Adam:** the, the, the only thing on my mind before we get to, you know, the future of the profession is, is the whole like plan, uh, maxing like spending tons of time writing a spec up front thing.

[00:40:33] **Tim:** Which.

[00:40:34] **Tim:** Yeah.

[00:40:34] **Tim:** He considered like, waterfall.

[00:40:35] **Tim:** Right.

[00:40:35] **Tim:** He's like, don't do that.

[00:40:36] **Adam:** Yeah, yeah.

[00:40:38] **Tim:** Which was interesting.

[00:40:38] **Tim:** I I mean, I agreed with that.

[00:40:40] **Tim:** And he's always fought against that.

[00:40:40] **Adam:** Mhm.

[00:40:42] **Tim:** That just thought that was interesting.

## [00:40:43] Plan-Maxing and Spec-First Development

[00:40:43] **Ben:** But.

[00:40:44] **Ben:** So, okay, this is another one of these places where I just feel like the analogies start to break down.

[00:40:50] **Ben:** So he, he said that.

[00:40:51] **Ben:** I think it was in a course that he used to teach or presentations he used to give.

[00:40:54] **Ben:** He would, he would bring up the thought experiment.

[00:40:57] **Ben:** Imagine that you're building a house and every change to the house costs a dollar.

[00:41:01] **Adam:** Right.

[00:41:02] **Ben:** Would you.

[00:41:02] **Adam:** And you could do that at any moment, right?

[00:41:03] **Adam:** You can say like, you can say they just laid the foundation and you can stand there, look at it and go, you know, no, let's change the shape to this L shape to the contractor.

[00:41:12] **Adam:** And it costs you a dollar to make that change.

[00:41:13] **Adam:** Right?

[00:41:13] **Adam:** He's, it's emphasizing the

[00:41:17] **Adam:** low cost of changes when you're doing it agile.

[00:41:17] **Tim:** The cheapness of, um, you know, changes in you.

[00:41:18] **Ben:** Right,

[00:41:20] **Adam:** Right.

[00:41:20] **Adam:** When you're changing things

[00:41:21] **Ben:** but so it.

[00:41:22] **Ben:** So, so he says, okay, but so if every cost, if any arbitrary cost, change costs a dollar, would you still pay an architect tens of thousands of dollars to draw plans?

[00:41:22] **Adam:** early.

[00:41:26] **Adam:** Mhm.

[00:41:33] **Ben:** But it's not really a good analogy because if you're in the AI world, paying the architect to come up with a really robust plan is kind of also a dollar.

[00:41:43] **Tim:** Mhm,

[00:41:43] **Ben:** And so you could say, well, do I really want to spend a dollar to come up with a really robust plan that might, uh, account for issues before I even run into them?

[00:41:51] **Ben:** Like, I feel like, yeah, why wouldn't you do that?

[00:41:53] **Ben:** That sounds, that seems like a pretty sensible thing to do.

[00:41:56] **Adam:** Yeah.

[00:41:56] **Ben:** So like, uh, and it's again, it's like one of these things where if you don't poke at the analogy a little bit, then you can kind of take it as this grand statement of wisdom and extrapolate.

[00:42:01] **Tim:** Mhm, mhm,

[00:42:09] **Ben:** It's the extrapolation that becomes dangerous because you're extrapolating from a point that wasn't actually the point he was starting from or like, you know what I'm saying?

[00:42:11] **Adam:** Yep.

[00:42:18] **Ben:** Like, it's, it's, it gets weird.

[00:42:20] **Adam:** Yeah.

[00:42:21] **Adam:** No, I mean, uh, so I think, and, and I think the way they framed it in that video was a very useful framing.

[00:42:26] **Ben:** Sa.

[00:42:27] **Adam:** So you know, the first like half or three quarters of the video was really getting into the specifics of running the LLM, and like the deterministic test that Bob is using and stuff.

[00:42:34] **Ben:** Mhm.

[00:42:38] **Adam:** and then the way that they, they framed this next part is like, you know, all of that was talking about how to build the, or how, how to build.

[00:42:38] **Tim:** Mhm, mhm,

[00:42:48] **Adam:** Right, right.

[00:42:49] **Adam:** How do I build software correctly?

[00:42:50] **Adam:** And then the, the more important question is how do I know I'm building the correct software?

[00:42:55] **Adam:** Software?

[00:42:56] **Ben:** Yeah,

[00:42:57] **Adam:** And um, yeah, I think sometimes the, the planning process is a good part of that.

[00:43:03] **Adam:** Right.

[00:43:03] **Adam:** You know, you have to think about the problem in order to

[00:43:07] **Adam:** see around those dark corners sometime.

[00:43:11] **Ben:** I have definitely had the experience several times now.

[00:43:15] **Ben:** And you know,

[00:43:17] **Tim:** Mhm, mhm,

[00:43:17] **Ben:** full disclosure, my experience here is really not that broad or deep.

[00:43:21] **Ben:** Um, where I have gone into plan mode to start, you know, setting up for.

[00:43:23] **Adam:** Mhm.

[00:43:26] **Ben:** I'm going to do this task.

[00:43:27] **Ben:** Let's talk through it.

[00:43:28] **Ben:** How are we going to do it?

[00:43:30] **Ben:** And I will run into some edge case that ends up kind of being a blocker for the thing that I'm about to build.

[00:43:36] **Ben:** And I'm like, you know what?

[00:43:38] **Ben:** I'm going to come back to this because I see that there's this other thing that I actually have to take care of first.

[00:43:41] **Ben:** And I'll go and I'll take care of that.

[00:43:43] **Ben:** And I feel like had I not done at least some planning ahead of time, I probably would have stumbled on that blocker,

[00:43:44] **Adam:** Mhm.

[00:43:51] **Ben:** you know, mid execution.

[00:43:53] **Ben:** And it might not even been very clearly a blocker.

[00:43:56] **Ben:** Like, it may have been just like, oh, tests are failing, or I can't figure out how to do something.

[00:43:58] **Tim:** Mhm,

[00:43:59] **Ben:** And then it asks you for clarity and then you try to give it some clarity by steering in a different direction.

[00:44:03] **Ben:** But you, like, it's almost like you're steering it, but you're on the wrong road at that point, to, you know, mix analogies here.

[00:44:10] **Adam:** Yeah.

[00:44:11] **Adam:** I'll go into a kind of a concrete example.

[00:44:14] **Adam:** you know, I talked about, I've been building some new features into Jump Run.

[00:44:17] **Adam:** I'm a big fan of Matt Pocock's.

[00:44:19] **Adam:** uh, library.

[00:44:21] **Adam:** in particular, I really like his grill me skill skill.

[00:44:24] **Ben:** Hmmmm.

[00:44:24] **Tim:** Mhm,

[00:44:25] **Adam:** it's a nice, it's a nice way to, help me think through a problem.

[00:44:29] **Adam:** Right.

[00:44:29] **Adam:** So I, I knew to build these features.

[00:44:31] **Adam:** I had a rough shape of, you know, these are the, this is sort of a list of features or sub features that I want to be included here.

[00:44:40] **Adam:** uh, I said, I ran it with the grill me skill.

[00:44:42] **Adam:** It ended up asking me like 40 questions.

[00:44:44] **Adam:** Right.

[00:44:45] **Adam:** Uh, to, to clarify.

[00:44:46] **Adam:** Which gets really frustrating.

[00:44:48] **Adam:** Um,

[00:44:48] **Ben:** Right.

[00:44:49] **Ben:** Like just start building.

[00:44:50] **Adam:** yeah, yeah, but it's also like, really useful too.

[00:44:53] **Adam:** And, and I think what's frustrating is like, can't.

[00:44:55] **Adam:** Why can't you just read my mind?

[00:44:56] **Adam:** Like, it makes so much sense to me here.

[00:44:58] **Adam:** Why don't you have it, in there?

[00:45:01] **Adam:** And, and that's, that's the, the, that's where the, the work, I guess, still exists.

[00:45:04] **Ben:** Mhm mhm.

[00:45:06] **Adam:** But, so I went through the process.

[00:45:08] **Adam:** I, you know, I answered all 40 questions.

[00:45:10] **Tim:** Mhm, mhm,

[00:45:10] **Adam:** I think there was just like one or two where I was like, you know, one of the things is like, I wanted to be able to send SMS messages.

[00:45:16] **Adam:** I was like, just build it with the adapter pattern.

[00:45:19] **Adam:** You know, build an interface that makes sense and we'll figure out the guts of that.

[00:45:23] **Adam:** Like, totally out of scope for this.

[00:45:24] **Adam:** It'll be a separate thing.

[00:45:26] **Adam:** The rest of it is like, okay, we're gonna, we're gonna be able to do all of these things, answered all the questions, and at the end of it, I had it, write like the sort of a spec from that conversation that we had.

[00:45:37] **Adam:** Just like, write me a plain HTML document.

[00:45:39] **Adam:** That's.

[00:45:39] **Adam:** That is the result of this conversation as a spec of this project broken up into whatever phases you think make sense.

[00:45:45] **Adam:** And, and it broke it up into three phases.

[00:45:48] **Adam:** and I, that's when I was using the like, slash goal thing in Codex.

[00:45:51] **Tim:** Mhm.

[00:45:52] **Ben:** Mhm.

[00:45:52] **Adam:** And I gotta say, it was both extremely impressive.

[00:45:56] **Adam:** What it was able to sort of like one shot for each phase and also extremely frustrating in how it did exactly what I wanted.

[00:46:05] **Adam:** Or I'm sorry, it did exactly what I asked for and did not at all build like, what I wanted it to feel like.

[00:46:12] **Adam:** Right.

[00:46:13] **Adam:** It's like it built something that satisfied it was.

[00:46:15] **Ben:** Mhm.

[00:46:15] **Adam:** It is the most like, autistic Uh, right.

[00:46:19] **Adam:** Like it built, you know, you, I asked for these, you know, additional features and it builds like on one page.

[00:46:19] **Tim:** Generic vanilla.

[00:46:26] **Adam:** It's just like a div above a div, above a div above a div.

[00:46:29] **Adam:** And each one is like these new features and there's no sense of taste and organization of the information on the page.

[00:46:31] **Tim:** Mhm.

[00:46:34] **Ben:** Mhm mhm.

[00:46:35] **Adam:** It's just like you asked for these five things on the page.

[00:46:37] **Adam:** Here are these five things on the page.

[00:46:39] **Adam:** Right.

[00:46:40] **Adam:** and it's like, well, you know, but what about like a tabbed interface?

[00:46:43] **Adam:** Or what if maybe this thing should be in a modal.

[00:46:45] **Adam:** Right.

[00:46:45] **Adam:** And like, so it built the stuff and the stuff is there and it works, but the labels are weird.

[00:46:50] **Adam:** It's very like tech jargony, not like user friendly.

[00:46:51] **Tim:** Sam.

[00:46:51] **Tim:** Mhm.

[00:46:54] **Adam:** And so I have to, I had to like after each phase I would stop and do another like 30, 40 prompts that are interactive to like apply my taste, uh, and some information organization to the interface.

[00:47:09] **Adam:** Even though it built functionally what I asked for.

[00:47:13] **Adam:** And, and I, I, I've done, I've completed all of that for phase two of three.

[00:47:13] **Tim:** Yeah.

[00:47:13] **Ben:** It mhm.

[00:47:18] **Adam:** And I, I had the, the phase three run overnight last night and took like almost three hours.

[00:47:23] **Adam:** That was great.

[00:47:24] **Adam:** It did the work.

[00:47:24] **Adam:** And then something I'm kind of in the middle of, when I'm not recording a podcast, is um, is going through that cleanup, uh, process on the result of phase three.

[00:47:29] **Ben:** Mhm.

[00:47:33] **Tim:** So you're not.

[00:47:34] **Tim:** You're not running agents while you're doing a podcast.

[00:47:36] **Tim:** I got three running right now.

[00:47:37] **Adam:** No, sir, I'm focused.

[00:47:37] **Tim:** What's your problem?

[00:47:39] **Adam:** I'm here, I'm present.

## [00:47:42] TDD, Thresholds, and Human Discipline

[00:47:42] **Tim:** Again, so it's like, I'm still.

[00:47:44] **Tim:** There's a few things.

[00:47:45] **Tim:** Two other things.

[00:47:46] **Tim:** I'm surprised.

[00:47:47] **Tim:** I'm not really surprised.

[00:47:48] **Tim:** Uh, he just.

[00:47:49] **Tim:** He went back on his, back catalog and revised history in two things.

[00:47:55] **Ben:** Mmm,

[00:47:55] **Adam:** Okay.

[00:47:56] **Tim:** So I'll give you a quote.

[00:47:57] **Adam:** Say more.

[00:47:58] **Adam:** Yeah.

[00:47:58] **Ben:** spicy.

[00:47:58] **Tim:** Say more.

[00:47:59] **Tim:** uh, he said it's probably a mistake to impose human discipline on an agent.

[00:48:05] **Tim:** I get that.

[00:48:06] **Tim:** It's not a mistake to impose human values on the agent.

[00:48:11] **Adam:** Right.

[00:48:11] **Tim:** Okay.

[00:48:12] **Tim:** Say more.

[00:48:12] **Tim:** I don't know what you're.

[00:48:13] **Tim:** Where are you going with?

[00:48:14] **Tim:** But there may be thresholds that we need to change, but the disciplines themselves, the behaviors, I don't think it's wise to impose those.

[00:48:17] **Ben:** Sa

[00:48:19] **Ben:** mhm.

[00:48:21] **Tim:** And there's two.

[00:48:22] **Tim:** Two areas he talked about that.

[00:48:24] **Adam:** I also pulled this as a, as a pull quote.

[00:48:24] **Tim:** one is

[00:48:26] **Adam:** Yeah, keep going.

[00:48:26] **Tim:** one.

[00:48:27] **Tim:** One.

[00:48:27] **Tim:** One of those is kind of esoteric.

[00:48:29] **Tim:** So the thresholds Move.

[00:48:30] **Tim:** Right.

[00:48:30] **Tim:** So he's talking about there's different.

[00:48:32] **Tim:** So it's like you impose a human value on the AI, the LLM, but you change the values because the values.

[00:48:39] **Tim:** And I do kind of see this like a lot of times.

[00:48:39] **Adam:** M.

[00:48:41] **Tim:** Claude will, I was like, give me an estimate how long this would take.

[00:48:44] **Tim:** And Claude would like, this is four days.

[00:48:45] **Ben:** M.

[00:48:46] **Tim:** Like dude, we just built, we just built something that you told me took two days and like 50 minutes.

[00:48:46] **Ben:** Right.

[00:48:46] **Adam:** Yeah,

[00:48:46] **Ben:** Yeah, it's hilarious.

[00:48:51] **Tim:** So.

[00:48:52] **Tim:** Shut up.

[00:48:52] **Adam:** Yeah,

[00:48:53] **Tim:** The thresholds are wrong.

[00:48:55] **Tim:** Um, so thresholds move.

[00:48:56] **Tim:** So agents, they, I mean they have a very.

[00:48:57] **Adam:** I don't think that's what he meant by thresholds.

[00:48:59] **Tim:** No, no, it's not what he meant.

[00:49:00] **Tim:** But I'm just saying that's kind of what, what triggered me.

[00:49:01] **Ben:** Mhm.

[00:49:03] **Tim:** And then he talked about a little more.

[00:49:03] **Adam:** Okay.

[00:49:05] **Tim:** So the CRAP score is particularly what he was talking about there in that section.

[00:49:09] **Tim:** He said, he said below for the CRAP score, below four for a human, six for agents, and he's considering pushing it to eight.

[00:49:16] **Adam:** Yeah, I think his algorithm is different too.

[00:49:16] **Tim:** So moving.

[00:49:19] **Tim:** Yeah.

[00:49:19] **Tim:** Is it?

[00:49:20] **Tim:** It is.

[00:49:20] **Adam:** Yeah.

[00:49:21] **Tim:** And this?

[00:49:21] **Adam:** Because I'm getting values, you know, just like assuming, like I actually did a quick spreadsheet real quick.

[00:49:21] **Ben:** But mhm.

[00:49:26] **Adam:** So with a cyclomatic complexity of 21, which is a very high complexity for a function.

[00:49:31] **Adam:** Right.

[00:49:31] **Adam:** And code coverage of like 97%.

[00:49:32] **Tim:** Yeah,

[00:49:32] **Ben:** But sa.

[00:49:34] **Adam:** that's a, that's a CRAP score of 21 based on that algorithm that we'll put in the show notes.

[00:49:38] **Adam:** But it's a simple algorithm that I, I, the ChatGPT gave me for what is a CRAP score algorithm.

[00:49:42] **Ben:** Mhm.

[00:49:43] **Adam:** But if you, if you bump the code coverage.

[00:49:45] **Adam:** So we're still keeping complexity at 21.

[00:49:47] **Adam:** If we bump the code coverage down to like 45%, this score goes from 21 and change to 94 and change.

[00:49:53] **Adam:** So it's the complex, the code coverage matters a lot in the complexity.

[00:49:55] **Tim:** Yeah.

[00:49:56] **Tim:** So, so our numbers are different because I, I, but, but basically the point is it's like you should expect tighter numbers for an AI because it has a very good short term memory, whereas humans, we don't.

[00:49:57] **Adam:** Right?

[00:49:57] **Adam:** Ruin the CRAP score.

[00:50:05] **Adam:** Mhm.

[00:50:09] **Tim:** The second thing was TDD.

[00:50:11] **Tim:** And Ben, you're going to love this.

[00:50:13] **Ben:** Yeah, no, I know exactly what you're talking about.

[00:50:15] **Tim:** TDD is a human discipline that he no longer forces on agents.

[00:50:19] **Adam:** Well, yes and no.

[00:50:20] **Adam:** He said he make, doesn't make him do it the same way.

[00:50:22] **Adam:** Right.

[00:50:22] **Adam:** So, uh.

[00:50:23] **Tim:** Exactly.

[00:50:23] **Ben:** Sa mhm mhm.

[00:50:23] **Tim:** He lets them, he lets them write the function first because they're good at that, and then write the test.

[00:50:27] **Adam:** Mm.

[00:50:27] **Adam:** Mhm.

[00:50:28] **Tim:** Because the test is not about like getting to the best possible function.

[00:50:32] **Tim:** You assume it's going to write a good function.

[00:50:32] **Adam:** Yeah.

[00:50:34] **Tim:** The test is really there sort of as a safety belt,

[00:50:38] **Adam:** Yeah.

[00:50:39] **Adam:** Also like the, the tools are not built like the LLM is not, the LLMs are good at writing functions.

[00:50:45] **Adam:** They're not good at writing one line of a function.

[00:50:47] **Adam:** Right.

[00:50:48] **Tim:** Right?

[00:50:48] **Adam:** Um, you know, to, it would be I think, very inefficient to be like, okay, we're going to write this function, we're going to do it in a TDD style.

[00:50:53] **Tim:** Mhm.

[00:50:54] **Adam:** So first make a, make an empty function and then write the test that proves the function exists or doesn't exist.

[00:50:58] **Tim:** Mhm.

[00:51:01] **Adam:** And then write the function and, and then make it do one, you know, return.

[00:51:01] **Tim:** Yep.

[00:51:04] **Tim:** That's a waste of time.

[00:51:05] **Adam:** Yeah, yeah, exactly.

[00:51:06] **Ben:** So, but if I can just interject for a second because I, I think this is in that section of the video they allude to some that, that Bob Martin had with John Ousterhout or Osterhound,

[00:51:08] **Adam:** Go.

[00:51:17] **Adam:** Yeah.

[00:51:17] **Tim:** Yeah.

[00:51:18] **Tim:** Ousterhout.

[00:51:18] **Tim:** Yeah.

[00:51:19] **Ben:** saying that John

[00:51:22] **Ben:** always thought that that's how TDD should be done, is that the test should be written after the function.

[00:51:23] **Tim:** Yep.

[00:51:26] **Adam:** Mm, mhm,

[00:51:27] **Ben:** And this is, this is why I find it so fascinating.

[00:51:29] **Ben:** Because yes, he's relaxing his perspective on code, but he's moving it to a perspective that other reasonable people already had.

[00:51:40] **Ben:** And, and I'm, um.

[00:51:40] **Tim:** Mhm.

[00:51:40] **Ben:** But, but I'm not saying that that's not meant to be a dig at him.

[00:51:43] **Adam:** Mhm.

[00:51:46] **Ben:** It's more meant to be like a.

[00:51:48] **Ben:** I think it's.

[00:51:49] **Ben:** I think it's important that when we start relaxing constraints, it's not so much a question of did the tool unlock something new

[00:51:59] **Ben:** or was the constraint that I applied previously really that valuable?

[00:52:04] **Ben:** And I think that's.

[00:52:04] **Adam:** M.

[00:52:04] **Adam:** Well that's the thing.

[00:52:05] **Adam:** I think, I think the value in doing it the way the TDD prescriptive way, right.

[00:52:06] **Tim:** I think.

[00:52:11] **Adam:** First write a test that says the function exists, the function doesn't exist, so the test fails.

[00:52:15] **Adam:** Right.

[00:52:15] **Adam:** And iterating it at that microscopic level, especially when you're first getting into TDD, is useful because it builds the, the way of thinking.

[00:52:21] **Tim:** Mhm,

[00:52:24] **Adam:** Like first I have to make this part, then I have to make this part.

[00:52:25] **Ben:** Mhm mhm mhm.

[00:52:27] **Adam:** Um, I found that uh, to TDD too cumbersome for me.

[00:52:33] **Adam:** But I did like

[00:52:36] **Adam:** the, what I would call the underlying intent of the TDD.

[00:52:41] **Tim:** Mhm.

[00:52:41] **Adam:** Right.

[00:52:42] **Adam:** There has to be a test for every

[00:52:45] **Adam:** code path, every, every decision that's being made, that sort of thing.

[00:52:46] **Tim:** Sa.

[00:52:49] **Adam:** and I think the, the modification that he's making to his standards or the, you know, the way he enforces TDD on his agents is

[00:53:01] **Adam:** not so much because his opinions of um, the right process have changed, but because he's using a different tool and the tool works differently now.

[00:53:09] **Adam:** Right.

[00:53:10] **Adam:** The, the LLM is a tool and an LLM can spit out the entire function at once.

[00:53:14] **Tim:** Mhm.

[00:53:14] **Adam:** So it doesn't make sense to you know, test an empty function.

[00:53:18] **Adam:** Right.

[00:53:19] **Adam:** It doesn't make so.

[00:53:19] **Tim:** Yeah.

[00:53:19] **Tim:** Because it's super quick.

[00:53:20] **Ben:** Mm mhm.

[00:53:21] **Tim:** I mean it's an iterative process for a human brain to do that and they learn stuff along the way.

[00:53:25] **Tim:** It's super cheap for an LLM to just basically spit out some functions, run some tests, discard them.

[00:53:32] **Tim:** They can do that over and over and over again within the extremely quickly versus how long it would take us to do that.

[00:53:36] **Ben:** Right.

[00:53:36] **Ben:** Right.

[00:53:39] **Tim:** And so don't slow it down.

[00:53:39] **Ben:** But I, I guess all I meant, all I meant to say maybe was that like a lot of.

[00:53:45] **Ben:** A lot of stuff is, Is legitimately subjective.

[00:53:50] **Ben:** Um, so if he talks about function length as, as a concrete example, that he's a fan of having very short functions,

[00:53:59] **Adam:** Mm, mhm.

[00:54:00] **Ben:** I have tried,

[00:54:00] **Tim:** Now that it's short, that they only do one thing that's short and one thing are not equivalent.

[00:54:03] **Ben:** okay, so I have tried many times.

[00:54:07] **Ben:** I have tried many times to take a long function and split it up into smaller, more focused functions.

[00:54:13] **Ben:** And I can't tell you how Many times I have gotten through that exercise, looked at it and be like, no, the longer function just reads better.

[00:54:20] **Ben:** And undoing all the changes that I made.

[00:54:23] **Ben:** Kind of like some, sometimes people say, oh, switch, uh, statements are an anti pattern.

[00:54:27] **Adam:** Mhm, mhm.

[00:54:28] **Ben:** And

[00:54:28] **Tim:** And they are.

[00:54:29] **Ben:** one of the uh, workarounds people will say is, oh, well, you should define an object where like each key maps to a function and then you don't need a switch statement.

[00:54:37] **Ben:** You just say, does this key exist in the function?

[00:54:39] **Ben:** If so, execute or uh, in, in this object, execute the function.

[00:54:42] **Ben:** I'm like, yeah, I can do that.

[00:54:45] **Ben:** But like it just doesn't read as well.

[00:54:46] **Adam:** Sam.

[00:54:46] **Ben:** Like I understand what you're saying, but to me personally, and again, this is just where some things are just

[00:54:51] **Tim:** Are you talking human readability or,

[00:54:53] **Ben:** yeah, yeah, yeah, but you know, that's because that's where a lot of these, a lot of these tastes, these taste makers come from.

[00:54:54] **Adam:** Mhm.

[00:54:55] **Tim:** or AI readability?

[00:54:59] **Ben:** Is, is what did it look like to a human?

[00:54:59] **Tim:** Yeah,

[00:55:02] **Ben:** But even in the realm of what did it look like to a human.

[00:55:04] **Tim:** But he's driving toward the fact where no human has to look at the code, including him.

[00:55:08] **Ben:** No, no, no, no, I, I, I know, I know, I know.

[00:55:08] **Tim:** That's what he's driving toward.

[00:55:10] **Ben:** I'm just saying that it's all just very interesting and I,

[00:55:14] **Tim:** Ben looks so uncomfortable, you guys.

[00:55:15] **Tim:** I'm looking at him right now on camera.

[00:55:17] **Tim:** He's like face is flushed.

[00:55:20] **Ben:** It's just, it's, I guess all I'm saying is that when people talk about their changing in perspective, we also have to remember that their perspective is very subjective.

[00:55:32] **Ben:** And the place that they were before and the place that they're getting to are still also very subjective.

[00:55:38] **Ben:** The fact that they're transforming isn't necessarily universal truth because everyone's coming from a different place is all I, I guess is all I'm saying.

[00:55:47] **Adam:** Okay.

[00:55:49] **Tim:** I, I mhm.

[00:55:49] **Tim:** Do have steg issue with the fact he was wearing a bathrobe in the video.

[00:55:53] **Adam:** Just.

[00:55:54] **Adam:** That was a joke.

[00:55:55] **Adam:** It was all for the gram.

[00:55:58] **Adam:** Um,

[00:55:58] **Ben:** It did start out kind of like I'm like, what is going on here?

[00:56:01] **Adam:** yeah, well, they mean.

[00:56:01] **Tim:** Look like old man yelling at sky.

[00:56:03] **Adam:** Yeah, well they explained it at the beginning of the video.

[00:56:05] **Ben:** Yeah, yeah.

[00:56:06] **Tim:** Yeah they did.

[00:56:06] **Adam:** That was, that was just for the meme.

[00:56:06] **Tim:** But yeah.

## [00:56:08] Junior Onboarding and Programming as a Trade

[00:56:08] **Adam:** Um, all right, let's, let's uh, wind this down by going into, you know, what is.

[00:56:08] **Tim:** Yeah.

[00:56:13] **Adam:** Or thoughts on the future of the profession.

[00:56:13] **Ben:** Mhm.

[00:56:17] **Adam:** Right.

[00:56:19] **Tim:** So I don't know if this is the future but I did glom on too because I do have a son who's just graduated with a CS degree who's looking for a job.

[00:56:30] **Tim:** How he talked about how junior language juniors, junior programmers should learn strategic programming and be treated like an agent.

[00:56:37] **Ben:** Yeah, I thought that was interesting.

[00:56:40] **Tim:** It was interesting.

[00:56:41] **Tim:** I mean I'm struggling with it a bit so

[00:56:42] **Adam:** If, if we're going to go back to last week and do Subway Takes, I'm going to go with 100.

[00:56:46] **Adam:** Disagree.

[00:56:48] **Tim:** yeah, ah, I love that.

[00:56:50] **Tim:** I love the disagree so basically says write real code first for a year or something.

[00:56:54] **Ben:** Mhm,

[00:56:55] **Tim:** So you know how what the agents are dealing with.

[00:56:57] **Tim:** I, I get that.

[00:56:58] **Tim:** I maybe we have that.

[00:56:58] **Adam:** Mhm.

[00:57:00] **Tim:** So it's like we can't, I can't go back in time and like erase all the knowledge I have for the past.

[00:57:07] **Tim:** I mean I started coding when I was 13, so a long time ago.

[00:57:11] **Adam:** 700 years.

[00:57:11] **Tim:** Um,

[00:57:12] **Tim:** 700.

[00:57:13] **Tim:** Yeah.

[00:57:13] **Tim:** Methuselah years.

[00:57:14] **Ben:** Mhm, mhm,

[00:57:14] **Tim:** Um, and then you get hired by a company that leans on agents.

[00:57:18] **Tim:** But the, he says the the new graduate should be treated like an agent.

[00:57:22] **Adam:** Mhm.

[00:57:22] **Tim:** Okay.

[00:57:23] **Tim:** Give them the same super narrow task.

[00:57:25] **Tim:** Basically you treat them like you just throw something over to them like you would an agent.

[00:57:28] **Tim:** Have them, hey, code this.

[00:57:31] **Tim:** That makes sense to me but I can't, being in the business world, I can't imagine

[00:57:37] **Tim:** that I would be given the corporate power to say yeah, we're not going to use Claude to do this.

[00:57:45] **Tim:** We're going to give the 23 year old Max Cunningham who's like a really smart kid, but he's going to struggle for about two days where we could just get the same result.

[00:57:51] **Adam:** Well,

[00:57:54] **Ben:** Mhm, mhm.

[00:57:56] **Adam:** In 20 minutes and, and $4 in tokens.

[00:57:57] **Tim:** Exactly.

[00:57:59] **Adam:** Yeah.

[00:58:01] **Tim:** And then, and then you spend the next several months in that state.

[00:58:05] **Tim:** Okay, no, corporate's not going to approve that.

[00:58:07] **Adam:** Uh, yeah,

[00:58:09] **Tim:** It's horribly unproductive.

[00:58:10] **Tim:** But learning a hell of a lot.

[00:58:12] **Tim:** I get that.

[00:58:13] **Tim:** We say we want to invest in our people.

[00:58:15] **Tim:** That's like our corporate motto.

[00:58:16] **Tim:** But at the same time it's like

[00:58:19] **Tim:** end of the day stock price, all that matters.

[00:58:21] **Tim:** Um.

[00:58:21] **Adam:** So I, I have opinions on all this.

[00:58:25] **Adam:** I think

[00:58:27] **Adam:** that a, uh, so two things.

[00:58:29] **Adam:** A, we are in a transition period and the, the next 5ish years, 5 to 10 years of people, uh, onboarding into the profession is going to be the weirdest and most difficult years of onboarding of this profession that we have ever seen and that we will ever see.

[00:58:35] **Ben:** Mhm mhm.

[00:58:41] **Tim:** Mh.

[00:58:46] **Adam:** That's my prediction.

[00:58:46] **Tim:** Yep.

[00:58:47] **Adam:** and, and then B, my take is really, that our profession is about to become a trade.

[00:58:48] **Tim:** I agree.

[00:58:55] **Adam:** Like a, like a plumber or a welder is a trade.

[00:58:56] **Tim:** Mhm.

[00:58:57] **Tim:** It has been coming, it has been coming that but yeah, for 100%.

[00:58:59] **Adam:** Yeah, but, but meaning, and what I mean by that is that to become a programmer you're not going to go to school for a computer science degree.

[00:59:09] **Adam:** You're going to go to a school where they teach you how to use modern coding tools, right?

[00:59:13] **Tim:** A tech school.

[00:59:14] **Adam:** A tech school where they teach you how to use tools.

[00:59:15] **Ben:** Mhm, mhm,

[00:59:16] **Adam:** And you're not gonna, you're not gonna understand how the compiler works and you're not going to understand the different layers of abstraction.

[00:59:23] **Adam:** You're just going to understand this is my tool and this is how I use it to get work done.

[00:59:27] **Tim:** Mhm

[00:59:27] **Adam:** And there will be a need for people who work at the, those at those lower levels.

[00:59:31] **Tim:** sa mhm.

[00:59:32] **Adam:** Right.

[00:59:33] **Adam:** Just like we still need people who write C and who still write assembly today.

[00:59:36] **Adam:** Right.

[00:59:37] **Adam:** There's just not that many of them because there's not a demand for that much, that many headcount of them.

[00:59:45] **Adam:** and so I think that trying to figure out how to do that today is a, is a noble thing to like how do we continue to onboard people.

[00:59:53] **Adam:** But I don't think that what he's describing there is a long term plan or it's not going to be a useful, valuable long term plan for onboarding people into the profession.

[00:59:55] **Ben:** Mhm,

[01:00:02] **Tim:** M.

[01:00:02] **Tim:** Right.

[01:00:03] **Tim:** It may be slightly advantageous in the next six to 24 months but it's not going to be the way going forward.

[01:00:07] **Adam:** So.

[01:00:10] **Adam:** Yeah, yeah,

[01:00:12] **Adam:** I think that.

[01:00:13] **Tim:** It's basically saying, you know, you're hiring someone who's going to do welding and you're like, uh, you need to really learn how to rub sticks together.

[01:00:21] **Adam:** You need to learn like electrical impedance and resistance and.

[01:00:21] **Ben:** Mhm, mhm, mhm,

[01:00:23] **Tim:** Exactly.

[01:00:24] **Tim:** Yeah.

[01:00:25] **Tim:** Whereas

[01:00:27] **Tim:** you're just like.

[01:00:27] **Tim:** No, you just turn on the oxygen.

[01:00:29] **Tim:** Turn off.

[01:00:30] **Adam:** Yeah, you need your shielding gas.

[01:00:31] **Tim:** Yeah.

[01:00:32] **Tim:** Turn on oxy.

[01:00:32] **Adam:** You need.

[01:00:33] **Tim:** Yeah.

[01:00:33] **Adam:** Yeah, yeah, yeah.

[01:00:33] **Tim:** And close your lid down and just start burning.

[01:00:37] **Adam:** Um, so I, it makes me think back, uh, some of the stuff that I learned in college, right.

[01:00:41] **Adam:** I took a compiler's class, I took like, I uh, forget exactly what it's called but it effectively was like a low level networking class where we got into the weeds of like layers of packets, like the, the different envelopes, what does the envelope contain?

[01:00:53] **Adam:** And, and you know, routing and all of that.

[01:00:54] **Tim:** Mhm.

[01:00:56] **Adam:** And it's like

[01:00:56] **Tim:** How long have you.

[01:00:57] **Tim:** How much time have you used that?

[01:00:58] **Tim:** It's zero.

[01:00:58] **Adam:** zero.

[01:00:59] **Adam:** None, not at all.

[01:01:00] **Tim:** Exactly 100%.

[01:01:00] **Adam:** Right.

[01:01:00] **Adam:** Like, and to, to be fair, there are times where I wish I would have remembered more from that.

[01:01:01] **Tim:** Yeah.

[01:01:05] **Adam:** Like, you know, I don't, I don't really fully get iptables and you know, some of the AWS networking, config stuff like I, I kind of get by but I wish I understood it better but you know, there are specialists who do know that and, and you know, we can hire them or whatever but

[01:01:12] **Tim:** Mhm,

[01:01:15] **Ben:** Mhm.

[01:01:22] **Adam:** yeah, like I just think that

[01:01:25] **Adam:** getting the work done is going to become a couple of classes instead of the entire you know, four year degree that it is currently.

[01:01:32] **Tim:** Mhm.

## [01:01:36] Learning by Failing and Strategic Lessons

[01:01:36] **Ben:** I, I, so I don't remember almost anything that I learned in college, to be fair.

[01:01:41] **Tim:** That means you had a good time, my friend.

[01:01:43] **Ben:** Yeah, I, I had a fun time.

[01:01:44] **Ben:** I ate.

[01:01:45] **Ben:** Eating meals every day and watching movies.

[01:01:47] **Adam:** I like to eat meals every day too.

[01:01:50] **Ben:** Um, I, you know, most of what I've learned, I'd say the vast, vast majority of what I've learned I've either learned at work, on the job, or in my fun spare time doing little side projects and exploratory stuff.

[01:01:58] **Tim:** Mhm,

[01:02:00] **Adam:** Mhm,

[01:02:03] **Ben:** The thing that I think falls down a little bit though, in some of the way they were talking about, oh, you know, code by hand at first, that you have a basic understanding of what the code's doing and then you can start doing the agentic stuff.

[01:02:12] **Tim:** Mhm, mhm,

[01:02:16] **Ben:** I don't think that Learning is any one thing, meaning I, uh, think it's easy to take all of the knowledge that you have right now and visualize it as something that you can just learn in a period of time because you already know it and you don't remember necessarily the story that came along with it.

[01:02:21] **Adam:** Mhm,

[01:02:36] **Ben:** But if you think about, uh, all the things that you had to fail at in order to learn, the thing that now seems so obvious to you.

[01:02:42] **Adam:** Mhm,

[01:02:44] **Ben:** You know, I used to write websites and I didn't put indexes on database tables because I didn't know what an index was.

[01:02:50] **Ben:** And granted the AI will do that for you by default now, so that doesn't matter so much.

[01:02:53] **Tim:** Mhm, mhm,

[01:02:55] **Ben:** But you had to be like, oh, why is the site running so slow?

[01:02:59] **Ben:** Oh, it's an index.

[01:03:00] **Ben:** Oh, why do, what are indexes?

[01:03:01] **Ben:** How do they help?

[01:03:02] **Ben:** How do indexes work?

[01:03:03] **Adam:** Mhm,

[01:03:03] **Ben:** Oh, that makes sense.

[01:03:04] **Ben:** And you kind of just keep doing this two steps forward, one step back dance.

[01:03:09] **Ben:** But even once you have some substantial amount of understanding, you're always going to have new problems that you need to fail at kind of before you can

[01:03:19] **Ben:** make sense of them.

[01:03:20] **Ben:** And I don't necessarily think that you'll be able to do that all from the agentic perspective.

[01:03:27] **Ben:** Like, I don't think you'll be able to build that muscle memory.

[01:03:30] **Ben:** Like, I've never really worked in a very distributed system and I, maybe this is just me not yet being AI pilled enough, but like, I have a, uh, trouble believing that I could just AI my way to a stable distributed system,

[01:03:33] **Tim:** Mhm, mhm,

[01:03:41] **Adam:** Mhm.

[01:03:47] **Ben:** uh, without having already tried to build and fail at a distributed system.

[01:03:52] **Ben:** Or like feel all the pains of doing it manually and feel all the pains of like, oh, I have to deploy this service and this service and this service at the same time.

[01:04:00] **Ben:** Otherwise they disagree on API contracts.

[01:04:03] **Ben:** Wow, that really sucks.

[01:04:05] **Ben:** Let's never do that again and then have to then take that knowledge and okay, well now I can build a distributed system with that battle, that battle wound.

[01:04:08] **Adam:** Yeah.

[01:04:13] **Ben:** Uh, so I, you know, when they're talking about this building skills, one of the things Matt Pocock says is that they talk about the difference between tactical coding and strategic coding, that the tactical is like what you're talking about.

[01:04:15] **Tim:** Mhm.

[01:04:25] **Adam:** Mhm.

[01:04:26] **Ben:** Tim, Just give it to the, the intern, the newbie, they're just going to do the implementation and the strategic coding is like, are we building the right thing?

[01:04:35] **Ben:** Are we making the right trade offs?

[01:04:36] **Ben:** Are we using the right technologies?

[01:04:39] **Ben:** And he says now that we have AI, we're going to be able to learn the strategic coding lessons faster and that I don't buy.

[01:04:44] **Adam:** Mhm.

[01:04:49] **Ben:** I think strategic lessons happen over a long period of time.

[01:04:55] **Ben:** That's why they've become strategic.

[01:04:57] **Tim:** But it's the.

[01:04:58] **Tim:** It's people that should be driving strategic lessons.

[01:05:01] **Tim:** AI Is really good at tactical.

[01:05:04] **Ben:** Yes, I agree that people should drive it.

[01:05:05] **Ben:** I guess the thing that I don't buy is that you're going to be able to learn them any faster with AI Uh, because the thing that makes things strategic is it's the coalescing of the people and the platforms and the products and the customers and the support team.

[01:05:15] **Adam:** M.

[01:05:15] **Adam:** So

[01:05:17] **Adam:** yeah, yeah,

[01:05:20] **Adam:** the years of experience.

[01:05:20] **Tim:** M.

[01:05:20] **Tim:** But if you can watch, if you can watch cheaply and quickly tactics fail, then you can build a better strategy.

[01:05:27] **Adam:** I wonder if we need like a, ah, more formal like apprenticeship type system, you know, like to be a.

[01:05:36] **Tim:** Our union.

[01:05:37] **Tim:** We need a union.

[01:05:38] **Adam:** Well that's, that's just true in general before LLMs, anyway.

[01:05:41] **Tim:** And Cory Doctorow.

[01:05:42] **Tim:** Let's start one.

[01:05:43] **Tim:** Come on, let's go.

[01:05:43] **Adam:** All right, um,

[01:05:45] **Ben:** Yeah, Adam.

[01:05:46] **Tim:** Come on.

[01:05:47] **Tim:** Adam Slacker.

[01:05:47] **Adam:** all right, all right, I'll get on it.

[01:05:50] **Adam:** I don't know.

[01:05:50] **Ben:** I mean, like, if you can build a queuing system faster,

[01:05:56] **Ben:** you know, you don't necessarily learn the lessons of horizontally scaled queue consumers and back pressure and dead letter queues until you have sufficient customers and product activity.

[01:06:05] **Tim:** Mhm.

[01:06:11] **Ben:** So like, yeah, you can build the system faster, but you're not necessarily going to learn the strategic lessons, I think, any faster

[01:06:19] **Adam:** Well, but that's uh, to.

[01:06:20] **Ben:** because you have to rely on the rest of the world to happen also.

[01:06:23] **Adam:** I'm going to say some stuff not because I necessarily believe it, but because it's a counterpoint.

[01:06:27] **Adam:** Right.

[01:06:27] **Ben:** Okay.

[01:06:27] **Adam:** So you, so you've gone on and on here about the difficulties of building good distributed systems.

[01:06:28] **Tim:** Sa.

[01:06:34] **Adam:** I think in our hypothetical five years from now scenario the LLMs will know they'll have a good like library of patterns.

[01:06:42] **Adam:** Right.

[01:06:43] **Adam:** I'm building a distributed system.

[01:06:44] **Ben:** Yeah.

[01:06:45] **Adam:** These are the things that I need to make sure I handle.

[01:06:47] **Ben:** Uh, I can't push back against that.

[01:06:52] **Adam:** All right.

[01:06:52] **Adam:** I think that's a good, that's a perfect spot to break it.

[01:06:57] **Tim:** Adam won.

[01:06:57] **Tim:** He's taking his ball and going home.

[01:06:58] **Adam:** That's right.

[01:07:00] **Adam:** so actually let's end it on this note.

[01:07:02] **Adam:** I loved this little moment that they had in their conversation, which was like kind of just a, a fun little ironic moment of, of thinking about LLMs, which is if you write something and give it to them, you're pretty much guaranteeing that they will read it.

[01:07:14] **Adam:** Right?

[01:07:15] **Adam:** But then you take all the, the stuff that the LLM writes for you and at probably at best you're just going to skim it.

[01:07:15] **Tim:** Yep.

[01:07:20] **Adam:** It's like a total one sided relationship, uh, which I found hilarious.

[01:07:26] **Tim:** And true.

## [01:07:27] Patreon

[01:07:27] **Adam:** All right, uh, this episode of Working Code is brought to you by your CRAP score which you can get from my new AI toilet startup, Crapster.

[01:07:34] **Adam:** Uh, and listeners like you.

[01:07:34] **Ben:** Mhm, mhm,

[01:07:35] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:07:40] **Tim:** Sa.

[01:07:42] **Adam:** Our Our patrons cover our recording, editing and transcription costs.

[01:07:45] **Adam:** And we couldn't do this every week without them.

[01:07:47] **Ben:** Sa,

[01:07:48] **Adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

[01:07:49] **Tim:** Mhm.

[01:07:50] **Adam:** You guys rock.

## [01:07:52] Thanks For Listening!

[01:07:52] **Adam:** We're gonna go do the after show.

[01:07:53] **Adam:** looks like we got some, some television topics on deck.

[01:07:57] **Adam:** Uh, and how you know the drill.

[01:07:59] **Adam:** You know, we're gonna keep talking.

[01:08:00] **Adam:** Mics are going to stay on.

[01:08:01] **Ben:** Mhm.

[01:08:01] **Adam:** Uh, and if you want access to that.

[01:08:03] **Adam:** It's really easy.

[01:08:03] **Adam:** You go to patreon.com/workingcodepod and throw a few bucks our way.

[01:08:08] **Adam:** That's gonna do it for us this week.

[01:08:09] **Adam:** We'll catch you next week.

[01:08:10] **Adam:** And until then,

[01:08:11] **Tim:** Hey, listen, when it comes to you guys, CRAP scores are nothing.

[01:08:16] **Tim:** You only get awesome scores.

[01:08:18] **Tim:** Your heart matters.
