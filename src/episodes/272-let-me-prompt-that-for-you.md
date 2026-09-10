---
title: "272: Let Me Prompt That For You"
description: "Can a model ever bring a career's worth of experience to a decision, or is human wisdom overrated to begin with? Are we really more productive than ever, or have we all just hired a ghostwriter? This week we discuss the abdication of opinion."
date: 2026-09-03
---

<iframe
	allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write"
	frameborder="0"
	height="175"
	style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;"
	sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation"
	src="https://embed.podcasts.apple.com/us/podcast/272-let-me-prompt-that-for-you/id1544142288?i=1000787886735"
></iframe>

LLMs have read everything, but they haven't spent fifteen years at the company learning which rules actually matter. Can a model ever bring a career's worth of experience to a decision, or is human wisdom overrated to begin with? And now that every answer starts with "let me ask Claude", are we really more productive than ever, or have we all just hired a ghostwriter? This week we discuss the abdication of opinion.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Matt Pocock's skills](https://github.com/mattpocock/skills) — grill-me and Wayfinder.
- [cron-job.org](https://cron-job.org/) — the cron host Adam landed on.
- [openblack](https://github.com/openblack/openblack) — the open-source Black & White engine Tim is vibe-coding on.
- [The Trevor Project](https://www.thetrevorproject.org/) — where Adam's thirty dollars from Infisical went.

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/272-let-me-prompt-that-for-you.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** the way I feel today is like Adam runs up to my door, he knocks on it, he's like, hey, Ben, you want to come out and play?

[00:00:00] **Tim:** Mhm.

[00:00:05] **Ben:** And I'm like, I got to go ask my wife.

[00:00:07] **Ben:** And then I go inside and I ask my wife and like, that's how work feels to me right now.

[00:00:07] **Adam:** Mhm.

[00:00:10] **Ben:** People are like, hey, Ben, can you do this ticket?

[00:00:12] **Ben:** I'm big.

[00:00:12] **Ben:** Let me go ask Claude.

[00:00:13] **Ben:** Really what I should say is, of course I can do this.

[00:00:15] **Ben:** And then privately I close the door and say, hey, honey, can I go and play with Adam?

[00:00:21] **Tim:** Sounds about right.

## [00:00:42] Intro

[00:00:42] **Adam:** Okay, here we go.

[00:00:42] **Adam:** It is show number 272.

[00:00:44] **Adam:** And on today's show, we're going to talk about abdication of opinion.

[00:00:47] **Adam:** Sorry to use big words, but we're going to do it.

[00:00:51] **Adam:** unfortunately, Carol is once again not able to join us.

[00:00:54] **Adam:** She, uh, got called into the office, but not just any office.

[00:00:57] **Adam:** She got called into the office.

[00:00:58] **Adam:** She's in D.C.

[00:00:59] **Adam:** this week.

[00:00:59] **Adam:** So,

[00:01:00] **Tim:** As in Washington D.C.

[00:01:02] **Adam:** So no Carol this week.

[00:01:04] **Adam:** Once again, just the boys.

## [00:01:05] Adam's Triumph

[00:01:05] **Adam:** but first, as usual, let's start with our Triumphs and Fails And it looks like it's my turn to go first.

[00:01:06] **Tim:** Mhm,

[00:01:10] **Adam:** so I'm gonna go with a little triumph.

[00:01:12] **Adam:** you know, I.

[00:01:13] **Adam:** I could try to explain it away, but it's just a fun little thing.

[00:01:17] **Adam:** earlier today, I happen to be checking our Working Code email address, uh, and I saw a note that I got from the people at Infisical Right?

[00:01:23] **Tim:** mhm,

[00:01:27] **Adam:** So if you guys recall, last week I mentioned that service that I found and I started using for managing my secrets, for Jump Run And, you know, I mentioned I liked it, and I still like it a week later.

[00:01:37] **Adam:** So that's good news.

[00:01:38] **Adam:** I haven't already turned tail on it.

[00:01:40] **Adam:** and.

[00:01:41] **Adam:** But I received an email from them saying, hey, or we.

[00:01:41] **Tim:** Mhm.

[00:01:43] **Adam:** The podcast received an email from them saying, hey, we heard you on the podcast.

[00:01:46] **Adam:** Thanks for mentioning us.

[00:01:47] **Adam:** Can we send you something to say thanks?

[00:01:49] **Adam:** And I assumed it was going to be like a T shirt or some stickers or something, right?

[00:01:53] **Adam:** So I gave them my personal email address that.

[00:01:54] **Adam:** Sure, send it here.

[00:01:55] **Adam:** and, um, they sent me $30 through a.

[00:01:59] **Ben:** Boom.

[00:02:00] **Adam:** uh, website.

[00:02:00] **Adam:** What is it called?

[00:02:01] **Adam:** Uh, Tremendous.

[00:02:02] **Adam:** tremendous.com Tremendous.

[00:02:04] **Tim:** Okay,

[00:02:05] **Tim:** we're splitting that three ways, right?

[00:02:07] **Tim:** Carol's not here.

[00:02:07] **Adam:** uh, no, sorry, I already spent it.

[00:02:10] **Adam:** but that's the thing.

[00:02:11] **Adam:** Right?

[00:02:11] **Adam:** So, uh, you know, this is uh.

[00:02:13] **Adam:** I guess this is going to double as some full disclosure, right?

[00:02:16] **Adam:** Podcasts and money has traded hands, and I just want to be fully upfront.

[00:02:19] **Adam:** I had no idea they were listening.

[00:02:22] **Adam:** Had no idea this could or would happen.

[00:02:25] **Adam:** They just reached out after the fact.

[00:02:26] **Tim:** You, sir, have failed the emoluments clause.

[00:02:26] **Adam:** Um, and so.

[00:02:29] **Adam:** Well, hang on, hang on.

[00:02:31] **Adam:** This is going good places.

[00:02:32] **Adam:** So, they sent me this money via Tremendous, which was, you know, very kind of them.

[00:02:35] **Ben:** Mhm.

[00:02:36] **Adam:** That's great.

[00:02:37] **Adam:** and I opened it up and I was like, I wonder if I can transfer this to my PayPal or to my Venmo or something like that.

[00:02:41] **Tim:** Mhm.

[00:02:42] **Adam:** So I started to look into it and right there on the page it's like, okay, you know, here's your.

[00:02:46] **Adam:** We sent you this money.

[00:02:47] **Adam:** You can have it as like one of these kinds of gift cards.

[00:02:50] **Adam:** Or down at the bottom it's like.

[00:02:51] **Adam:** Or you can donate to a charity.

[00:02:52] **Adam:** I'm like, oh, let me see what charities there are.

[00:02:54] **Adam:** and there's, you know, I don't know, maybe 20 in the list.

[00:02:55] **Ben:** Mhm.

[00:02:57] **Adam:** Um, and one of them stood out to me was the, the Trevor Project, which you may or may not be familiar with.

[00:03:01] **Adam:** It's a suicide, ah, prevention, charity for LGBTQ+ youths, young people.

[00:03:10] **Adam:** and you know, it's one I'm very familiar with.

[00:03:12] **Adam:** dear, near and dear to my heart.

[00:03:12] **Tim:** Mhm.

[00:03:13] **Adam:** And to top it off, they are very, very well reviewed on Charity Navigator, which just means that they're responsible with the donations that they receive, basically.

[00:03:23] **Adam:** So I donated that 30 bucks to, um, the Trevor Project and I, I posted a screenshot of it in our Discord as well.

[00:03:23] **Ben:** Very lovely.

[00:03:29] **Adam:** Just so you know, full transparency.

[00:03:32] **Adam:** they did send me money, but I donated it.

[00:03:34] **Adam:** And m.

[00:03:36] **Adam:** Thought was very nice of them.

[00:03:37] **Adam:** I thought, you know, I would return the favor in kind and, and donate it.

[00:03:40] **Tim:** Yeah, fantastic.

[00:03:40] **Adam:** So

[00:03:42] **Tim:** Tell them thank you.

[00:03:44] **Adam:** thanks there.

[00:03:45] **Tim:** Thanks.

[00:03:45] **Ben:** Mhm.

[00:03:46] **Adam:** Apparently they're listening.

[00:03:46] **Tim:** Read our transcripts.

[00:03:47] **Adam:** So yeah,

[00:03:49] **Tim:** I'd still like a T shirt though.

[00:03:52] **Adam:** Tim can be purchased.

[00:03:54] **Tim:** I can, I can be bought quite easily.

[00:03:54] **Adam:** Um,

[00:03:56] **Tim:** I'm corrupt Senator number two.

[00:03:56] **Adam:** does it, does it have to be a linen T shirt or.

[00:04:03] **Adam:** I know all you're wearing these days is linen.

[00:04:05] **Adam:** Anyway, so that's it.

[00:04:06] **Adam:** that's going to be it for me.

## [00:04:07] Ben's Fail

[00:04:07] **Adam:** what do you got going on, Ben?

[00:04:09] **Ben:** I'm gonna go with a failure not to be a Debbie Downer here after your very lovely kind of double win triumph.

[00:04:13] **Tim:** Sa.

[00:04:15] **Adam:** A dolly downer?

[00:04:17] **Adam:** Mhm.

[00:04:18] **Ben:** Yeah, I, I just, I'm feeling very sad lately.

[00:04:21] **Adam:** Yeah.

[00:04:21] **Ben:** I feel,

[00:04:23] **Ben:** I don't know, like very little is sparking joy in my life.

[00:04:28] **Ben:** Full disclosure, I do have a puppy and that is a shocking amount of work.

[00:04:30] **Tim:** Mhm.

[00:04:33] **Ben:** And uh, it has.

[00:04:35] **Ben:** She's getting better every day.

[00:04:36] **Adam:** Mhm.

[00:04:36] **Ben:** You know, a little less required, hands on, a little less bitey, a little less pee pee in the house every day.

[00:04:42] **Ben:** So, uh, that'll get better.

[00:04:43] **Ben:** But just I feel a little, uh, what's the phrase?

[00:04:47] **Ben:** Anhedonic Like that's just the joyness.

[00:04:50] **Ben:** The joy of things is kind of gone.

[00:04:53] **Ben:** Uh, I feel like podcasts I all listen to lately have gotten, I don't know, very boring, you know, and hopefully

[00:04:54] **Adam:** Mhm.

[00:04:59] **Tim:** Uh, I mean, I know this one has.

[00:05:02] **Ben:** I just.

[00:05:03] **Ben:** So when we said we were starting this podcast five or six years ago, however long that was, someone had as a joke sent, I hope it's not like this.

[00:05:12] **Ben:** And they sent me a clip to people mocking podcasts.

[00:05:15] **Tim:** Thought that was me.

[00:05:15] **Adam:** M.

[00:05:15] **Ben:** And it's just like 60 seconds was, uh, it's just like 60 seconds of people going, oh, I'm so glad we're talking about this.

[00:05:15] **Adam:** Oh yeah, yeah.

[00:05:16] **Tim:** I.

[00:05:16] **Tim:** I sent you that.

[00:05:21] **Ben:** Yeah, like this is really a topic people need to be covering.

[00:05:23] **Adam:** And they're all like constantly adjusting the mics as they do it.

[00:05:24] **Ben:** Yeah.

[00:05:24] **Ben:** It's like, yeah,

[00:05:27] **Ben:** yeah,

[00:05:27] **Tim:** I mean, that is so top of mind.

[00:05:28] **Tim:** I'm so glad you brought that up.

[00:05:29] **Ben:** right,

[00:05:30] **Tim:** Let me circle back because it kind of dovetails what I was talking about.

[00:05:33] **Tim:** Yeah, they never say anything for like five minutes.

[00:05:33] **Ben:** yo.

[00:05:34] **Ben:** And I just like a little bit,

[00:05:37] **Ben:** A little bit.

[00:05:38] **Ben:** I feel like I get to the end of so many podcasts these days and I just feel like I have zero takeaways.

[00:05:46] **Ben:** It's all people just talking about

[00:05:46] **Adam:** M.

[00:05:46] **Adam:** Mhm.

[00:05:49] **Ben:** kind of the meta nature of building software and how do you think about building software and how do you think about designing the guardrails that help you build the software?

[00:05:54] **Tim:** Mhm,

[00:05:59] **Ben:** And I get to the end of it, I'm just like, uh, I don't think I learned anything from this.

[00:06:02] **Ben:** This was just, it just felt like people talking and you know.

[00:06:06] **Adam:** Well, thanks for, thanks for setting up a nice high bar for us to clear in this podcast episode.

[00:06:08] **Ben:** Yeah.

[00:06:11] **Ben:** And also I also just feel like, and this is maybe just a transitional period in the age of AI.

[00:06:15] **Tim:** Mhm,

[00:06:18] **Adam:** Mhm.

[00:06:18] **Ben:** I'm so suspicious of everything that I read these days that I feel like I'm not connecting with people.

[00:06:26] **Ben:** Um, if I look at people's code, like someone will say that they posted something and I said, oh, that sounds really interesting.

[00:06:30] **Adam:** Sa.

[00:06:32] **Ben:** I go to look at it and it feels very much like it was just AI generated code.

[00:06:34] **Tim:** mhm,

[00:06:37] **Ben:** And that's not necessarily a judgment on the quality of the code.

[00:06:37] **Adam:** Mhm.

[00:06:40] **Ben:** That is more a judgment of the.

[00:06:42] **Ben:** I came to this code, uh, in some sense to connect with you as an author.

[00:06:48] **Ben:** And I'm looking at the code now and it's like I might as well just be looking at compiled code, right?

[00:06:52] **Ben:** Like the code itself no longer expresses

[00:06:55] **Tim:** Mhm.

[00:06:56] **Ben:** any deep seated feeling you had about the way code should be done.

[00:07:00] **Ben:** It's just maybe you had an idea for something and that's great, but I'm just like, I'm not connecting with people.

[00:07:06] **Ben:** Same thing.

[00:07:07] **Ben:** If I see anything written on LinkedIn, if it even smacks slightly of AI,

[00:07:13] **Ben:** verbiage, you know, load bearing seams, it's not this, it's that I'm like, ah, uh, like I, I.

[00:07:15] **Adam:** Mhm.

[00:07:17] **Adam:** Right.

[00:07:20] **Adam:** Slopspician.

[00:07:21] **Ben:** Yeah, like I'm exactly slop spishing.

[00:07:23] **Ben:** I love that.

[00:07:24] **Ben:** I've never heard that before.

[00:07:24] **Ben:** Did you just come up with that?

[00:07:25] **Adam:** I just coined the term.

[00:07:27] **Ben:** Oh, I love that.

[00:07:28] **Tim:** You heard it here first.

[00:07:29] **Ben:** Yeah.

[00:07:29] **Ben:** And it's, and it, it's um, I just feel like I'm not connecting and it makes me feel very sad and actually, very lonely.

[00:07:36] **Ben:** Which is, you know, it's so nice that I get to talk to you beautiful people once a week.

[00:07:37] **Adam:** Mhm.

[00:07:41] **Tim:** M.

[00:07:41] **Tim:** Oh, butter is up now.

[00:07:42] **Tim:** Okay,

[00:07:44] **Ben:** But, but anyway, that's, um, I don't know, I'm hoping that it's mostly just, uh, exhaustion from having a puppy and I'll get past it, but I don't know, I'm just, I'm not feeling very joyful these days.

[00:07:57] **Tim:** Hang in there, man.

[00:07:58] **Ben:** Yeah.

[00:07:59] **Ben:** Thank you.

[00:08:00] **Adam:** It'll get better.

[00:08:00] **Adam:** Sooner or later she'll start humping something and you'll just.

[00:08:01] **Tim:** Yep.

[00:08:02] **Ben:** Yeah, yeah.

[00:08:03] **Adam:** All your joy will come running back.

[00:08:04] **Tim:** All those Facebook photos.

[00:08:07] **Ben:** anyway, that's me.

[00:08:09] **Ben:** out.

## [00:08:09] Tim's Triumph

[00:08:09] **Ben:** So Tim, what do you got going on?

[00:08:11] **Tim:** Um, um, well, Debbie Downer, I have a triumph.

[00:08:14] **Tim:** Although it seems related to the things that's depressing you.

[00:08:17] **Tim:** So.

[00:08:20] **Tim:** So I don't know if you guys remember, uh, there was a game in the early 2000s, like 2001, called Black and White.

[00:08:27] **Adam:** Oh, I love that game so much.

[00:08:28] **Adam:** Peter.

[00:08:28] **Adam:** Molyneux.

[00:08:30] **Tim:** Yeah.

[00:08:30] **Tim:** That goes.

[00:08:30] **Tim:** Look fantastic for Lionhead's game.

[00:08:32] **Tim:** Lionhead's game.

[00:08:33] **Tim:** Fantastic.

[00:08:34] **Tim:** So basically you're God and um.

[00:08:36] **Ben:** Can relate.

[00:08:37] **Tim:** Exactly.

[00:08:39] **Ben:** Mhm,

[00:08:39] **Tim:** So basically you're a God and you have like a little pet God and there's a village in the world.

[00:08:45] **Tim:** And like, there's all these different concerns and stresses on the world, but basically the main thrust of the game is as God.

[00:08:48] **Adam:** Mhm.

[00:08:52] **Tim:** You watch this little pet kind of walk around and do things and maybe pick up a villager, like eat the villager.

[00:08:59] **Tim:** And if you think that's a bad thing as a God, you slap the creature around and it learns that that's a bad thing.

[00:09:04] **Ben:** Mhm, mhm,

[00:09:07] **Tim:** Or if you think that's a good thing as a God, you pet the creature and it goes, oh, I'll eat more villagers and m.

[00:09:09] **Adam:** Mhm.

[00:09:12] **Tim:** You know, make them fall in line.

[00:09:14] **Tim:** So it's really nice.

[00:09:15] **Tim:** Like there's not like a.

[00:09:16] **Tim:** You could play pretty much a spectrum of different types of, uh, of interaction with the world.

[00:09:21] **Tim:** But just the whole animal interaction thing with it was really, really super cool.

[00:09:26] **Tim:** And it's, it's abandoned where I guess the company went out of business.

[00:09:29] **Tim:** But anyway, I say all that to say this.

[00:09:30] **Adam:** Mhm.

[00:09:30] **Tim:** I have like this ChatGPT,

[00:09:34] **Tim:** subscription that I don't really use is just my personal one.

[00:09:35] **Ben:** Mhm, mhm.

[00:09:36] **Tim:** And I now actually have a personal laptop.

[00:09:39] **Tim:** And so I'm like, well, you know, let me just set up a Ralph loop and just like see if I can Create this game.

[00:09:46] **Tim:** And to top it off I found a source project called Open Black and White, which is a C++ or.

[00:09:53] **Tim:** Yeah, C++.

[00:09:54] **Tim:** Um, rendering of this game but it's not fully complete.

[00:09:58] **Tim:** So it has like the world as the hand has the map and everything, but doesn't really have the creatures.

[00:10:03] **Adam:** Hmm.

[00:10:03] **Tim:** So I've been vibe coding.

[00:10:04] **Tim:** I'm just asking, can I vibe code this?

[00:10:07] **Tim:** Like just, just vibe code?

[00:10:09] **Tim:** I don't, I don't know how to create 3D assets.

[00:10:11] **Tim:** My son does.

[00:10:12] **Tim:** I'm not good at it.

[00:10:13] **Tim:** But um, yeah, can I just vibe code this?

[00:10:15] **Ben:** Mhm M.

[00:10:15] **Tim:** Let's see what it turns out.

[00:10:16] **Tim:** It will probably be hilariously bad,

[00:10:20] **Tim:** but at least I'll get to see what is the possibility here.

[00:10:23] **Tim:** So.

[00:10:24] **Adam:** Yeah.

[00:10:25] **Adam:** Man, I have so many hours playing that game.

[00:10:25] **Tim:** Right.

[00:10:27] **Adam:** I.

[00:10:28] **Adam:** I used to, I don't know if I ever necessarily cut class when I was in college specifically to play that game, but if I wasn't in class, I was probably playing that game.

[00:10:36] **Tim:** I think it was so much.

[00:10:37] **Tim:** I was like newly married.

[00:10:38] **Tim:** My wife and I, we played the game all the time.

[00:10:40] **Tim:** Like what'd your creature do?

[00:10:41] **Tim:** What'd you teach it to do?

[00:10:42] **Tim:** So yeah,

[00:10:42] **Adam:** Yeah,

[00:10:43] **Ben:** Can't believe I never heard of this.

[00:10:46] **Tim:** it wasn't a huge game, but it's like it was, I mean,

[00:10:50] **Tim:** I think I remember I read like uh, some computer game magazines back in the day and I was like, it was like one of the top 10.

[00:10:56] **Tim:** It just seemed like fun because it's not like, it's not so stressful like Age of Empires where you're constantly fighting things.

[00:11:01] **Adam:** Yeah,

[00:11:02] **Tim:** You're just basically grooming this God, the demigod, basically to manage your villages and yeah, so it was kind of fun.

[00:11:12] **Tim:** I guess it was a prelude to child rearing, so.

[00:11:15] **Ben:** Mhm, mhm,

[00:11:16] **Adam:** It was like a, you know, Tamagotchi, uh, for grown ups,

[00:11:20] **Tim:** Exactly.

[00:11:20] **Tim:** And very much like a Tamagotchi for grown ups.

[00:11:22] **Tim:** Yeah.

[00:11:24] **Tim:** So anyway, that's me.

## [00:11:25] Abdication of Opinion

[00:11:25] **Tim:** What we talking about today?

[00:11:26] **Tim:** Abdication.

[00:11:27] **Tim:** What we abdicating?

[00:11:28] **Adam:** Uh, opinions Like I said, uh, we don't.

[00:11:30] **Adam:** We, we.

[00:11:31] **Adam:** So this is going back to a little bit of like, you know, we Talked about how LLMs are making us lazy, and other stuff.

[00:11:36] **Tim:** Mhm

[00:11:36] **Ben:** Mhm.

[00:11:39] **Adam:** And, and you know, before we, before we started recording this show, we were kind of going on about

[00:11:46] **Adam:** how you know, this podcast is ostensibly about programming, uh, and

[00:11:53] **Adam:** all of us, the four of us, uh, at least.

[00:11:54] **Tim:** mhm.

[00:11:56] **Adam:** And I guess we get the sense that the community at large, um, the majority of our time spent programming is actually spent working with AI.

[00:12:03] **Adam:** So that's why we sometimes feel a little weird about discussing AI on the podcast.

[00:12:08] **Adam:** Like A, it is very applicable because it's pretty much all we do all day, but B, it's also, it feels weird because it's topical.

[00:12:12] **Ben:** Yeah.

[00:12:12] **Ben:** Mhm.

[00:12:14] **Tim:** Mhm

[00:12:16] **Adam:** Right.

[00:12:16] **Adam:** It's non programming podcasts also cover AI a lot.

[00:12:19] **Adam:** And so it feels like we're trying to capitalize on a moment when actually it's, it's ours, we're taking it back.

[00:12:25] **Ben:** It mhm, mhm sa.

[00:12:26] **Adam:** but yeah, so, uh, LLM stuff.

[00:12:29] **Adam:** Uh, the big thing for me this week, has been the feeling that I'm starting to see the difference.

[00:12:31] **Tim:** mhm.

[00:12:34] **Adam:** Like see the gap between the intelligence that the system might actually have, that the, that the LLM can kind of represent and what, what, what I would call wisdom.

[00:12:45] **Adam:** Right.

[00:12:45] **Adam:** Like I, I'm willing to say that if you squint your eyes just right, an LLM has intelligence.

[00:12:52] **Tim:** Mhm

[00:12:53] **Ben:** Mhm.

[00:12:54] **Adam:** It can

[00:12:56] **Adam:** synthesize

[00:12:58] **Adam:** coherent thoughts based on information that it can find for itself based on me asking a question.

[00:13:03] **Adam:** Right.

[00:13:04] **Adam:** That I would say that's intelligence.

[00:13:06] **Adam:** but I

[00:13:09] **Adam:** can give it all kinds of parameters about what I'm thinking and

[00:13:13] **Tim:** mhm.

[00:13:14] **Adam:** ask it a question and have it do some research and still not like the decision or the suggestion that it comes up with, um, for reasons that I maybe gave or other like sort of nuanced reasons that maybe it didn't pick up on from the parameters that I discussed.

[00:13:30] **Adam:** You know what I mean?

[00:13:32] **Ben:** Yeah, absolutely.

[00:13:32] **Tim:** Mhm

[00:13:33] **Ben:** Life is just so complicated and messy and so many of the decisions that we make both in our day to day life and our professional life are not made in a vacuum and are very much grounded in bias and in the pragmatic realities and in the other people that we have to deal with, uh, or get to deal with.

[00:13:45] **Adam:** Mhm.

[00:13:45] **Adam:** Yeah.

[00:13:53] **Tim:** mhm.

[00:13:56] **Ben:** You know, I don't want to paint that in a negative way.

[00:13:58] **Ben:** Um, and the AI knows none of that.

[00:14:01] **Adam:** Yeah, the AI, the.

[00:14:02] **Adam:** I'm gonna go back to what I mentioned last week.

[00:14:04] **Adam:** I try really hard not to call it AI, but the LLM, um, hasn't been working for the company for 15 years and have all that institutional knowledge and domain knowledge and experience to draw on.

[00:14:13] **Tim:** Mhm

[00:14:15] **Adam:** We're expected, I think, to represent that experience and our wisdom in our prompts and in the way we steer the results that we get.

[00:14:24] **Ben:** It's also, I find that the AI, unlike a human,

[00:14:29] **Ben:** doesn't really have a sense of what it should remember and what it's okay to forget.

[00:14:32] **Tim:** mhm.

[00:14:35] **Ben:** You when we were talking about the Robert Martin interview from last week, one of the things that Robert Martin said is that the AI has flawless short term memory.

[00:14:45] **Ben:** Um, and it, it reminds me of, uh, there was an episode of House M.D.

[00:14:49] **Ben:** many, many years ago.

[00:14:50] **Ben:** for our younger listeners, that was a medical drama.

[00:14:52] **Tim:** Mhm

[00:14:52] **Ben:** With Hugh Laurie

[00:14:53] **Adam:** A TV show was.

[00:14:56] **Ben:** that you watched on the Talkie box.

[00:14:59] **Ben:** Um, and one of the episodes had these two sisters, and one of them was very sick.

[00:15:03] **Ben:** I don't really remember the whole story, but one of the sisters had photographic memory and essentially never forgot anything that ever happened to her.

[00:15:12] **Ben:** And when she would get together with her sister, she was always so angry at her sister because she could remember every single slight, every single offense that the other sister couldn't even remember those things happening.

[00:15:12] **Tim:** mhm.

[00:15:24] **Ben:** So the other sister just kept wanting to reconcile, like, oh, why can't we just be friends?

[00:15:25] **Adam:** Mm, mhm,

[00:15:28] **Ben:** And the sister with the photographic memory would try, and then something would trigger her and she'd be like, I just can't deal with you.

[00:15:33] **Tim:** Mhm

[00:15:34] **Ben:** You know, like, all I can do is remember all the things you've ever done me wrong by.

[00:15:38] **Adam:** Mhm,

[00:15:38] **Ben:** And I feel like dealing with the AI is sometimes like that.

[00:15:41] **Ben:** It's like it gets hung up on so many little which feel like very inconsequential details, but they're inconsequential to the human because the human is bringing a lifetime of experience to everything that gets stated in a conversation, whereas the AI is bringing almost like equal weighting to everything that's said.

[00:15:54] **Tim:** mhm.

[00:16:02] **Ben:** And so again, going back to the idea that wisdom and.

[00:16:05] **Ben:** And knowledge are, uh, not the same thing.

[00:16:07] **Adam:** Mhm.

[00:16:08] **Ben:** The AI has a tremendous amount of knowledge.

[00:16:11] **Ben:** It can remember everything, it knows everything, but it doesn't have the wisdom to discern which of those things are actually important sometimes.

[00:16:15] **Tim:** Mhm.

[00:16:18] **Ben:** And I find myself cursing, like, why you keep bringing that up.

[00:16:19] **Adam:** Right.

[00:16:22] **Ben:** And then people say, oh, you just have to constantly be resetting the context and, and starting a new conversation once it starts to make mistakes over and over again.

[00:16:30] **Ben:** You're like, that's like, my dog can practically hold a conversation better than that, though.

[00:16:37] **Tim:** Uh, which is why you can't sleep.

[00:16:41] **Adam:** So, there's.

[00:16:42] **Adam:** I know I probably mention him every episode.

## [00:16:42] Matt Pocock Skills and Wayfinder

[00:16:42] **Ben:** M.

[00:16:44] **Adam:** So, sorry for sounding like a shill but I've been getting really into the LLM skills provided by Matt Pocock.

[00:16:52] **Adam:** Are you guys familiar with his skills?

[00:16:53] **Adam:** The like grill-me?

[00:16:54] **Tim:** Entered them.

[00:16:54] **Tim:** Yep.

[00:16:55] **Ben:** I know of them.

[00:16:55] **Adam:** Uh, yeah.

[00:16:56] **Adam:** So there's a bunch of um, them he's got, you know, he's got this repository.

[00:16:59] **Adam:** It's pretty, it's.

[00:17:00] **Adam:** I think it's probably one of the Most starred, GitHub repositories of LLM skills.

[00:17:03] **Ben:** Mhm mhm,

[00:17:06] **Adam:** But there's.

[00:17:07] **Adam:** And it's a whole collection, right?

[00:17:08] **Adam:** There's some that are specifically for writing code, there's some that are just for thinking in general productivity, that sort of thing.

[00:17:13] **Tim:** Mhm.

[00:17:17] **Adam:** Um, and

[00:17:19] **Adam:** something he's been saying more recently is that, you know, a newer development is that no problem is now too large to

[00:17:29] **Adam:** deal with, via uh, LLMs.

[00:17:31] **Tim:** Mhm

[00:17:31] **Adam:** Right?

[00:17:32] **Adam:** It used to be that you kind of had to do the human work upfront to think about the problem and go, okay, this is a huge thing.

[00:17:39] **Adam:** There's no way I can get all this information into the LLM.

[00:17:40] **Ben:** Mhm.

[00:17:43] **Adam:** And so like, as a practical example, right when I first started working on Jump Run, I told you guys I'd spent like days, not, not consecutively, but you know, across several days I spent maybe

[00:17:51] **Tim:** mhm.

[00:17:55] **Adam:** 4, 5, 6 hours writing a spec document, hoping I could just feed that into the machine and it would write the whole app for me in one shot.

[00:18:01] **Ben:** Right.

[00:18:01] **Adam:** Right?

[00:18:02] **Adam:** And that was uh, a laughable exercise back.

[00:18:06] **Adam:** But you know, these days, with the more m.

[00:18:10] **Tim:** Mhm

[00:18:10] **Adam:** With the advancements that the LLMs have been making and with the skills that are available now, in particular some of his skills, problem, like the process of that pre-work the breaking down large problems into smaller problems and breaking those down into even smaller problems and then breaking those down into like user stories that you can implement one at a time, can not necessarily be automated, but the LLM can kind of hold your hand through that process and keep the information organized.

[00:18:17] **Ben:** Mhm mhm,

[00:18:28] **Tim:** mhm.

[00:18:36] **Adam:** Right?

[00:18:36] **Adam:** So, a big part of the problem of dealing with those big problems is keeping that information organized in your head and making sure that your decisions all agree with yourself.

[00:18:44] **Adam:** Right?

[00:18:46] **Adam:** and so he's got a skill.

[00:18:47] **Tim:** Mhm

[00:18:48] **Adam:** I, I think I usually start with like a grill-me session.

[00:18:52] **Adam:** and, and then so you say like, okay, this is what I want to work on.

[00:18:55] **Ben:** Mhm, mhm,

[00:18:55] **Adam:** And you, you brain dump a couple of paragraphs or whatever of like some, some basic context and you have it grill you and it starts to ask these like leading questions or, or exploratory questions that expand the scope of the conversation.

[00:19:07] **Tim:** mhm.

[00:19:08] **Adam:** And you, you just keep Answering questions.

[00:19:11] **Adam:** And it does the work of, uh, figuring out, well, well, what you said here kind of contradicts with, you know, your answer to number 23 contradicts with your answer to number 7.

[00:19:18] **Adam:** And so we have to like, talk about that more.

[00:19:21] **Adam:** and ultimately, you know, it tries to get you to this place where you have a shared understanding with the, the context window that you're chatting about.

[00:19:29] **Adam:** And then it can write that to a spec, and it can break that spec down into tickets, and it can organize the tickets by like, okay, well, this one blocks this one and this one blocks this one.

[00:19:30] **Tim:** Mhm.

[00:19:37] **Ben:** Mhm, mhm,

[00:19:37] **Adam:** So you kind of get this like, waterfall of ticket dependencies.

[00:19:41] **Adam:** and then you can just have it start churning through those tickets one at a time.

[00:19:45] **Adam:** You give each ticket a fresh context window to implement because it's been broken down into a tiny little problem with, you know, a spec and acceptance criteria.

[00:19:54] **Adam:** And it says this is what's out of scope and stuff.

[00:19:56] **Adam:** So, all of that to say,

[00:19:59] **Adam:** the, the process of like, breaking down these really huge, problems is where I have started to notice the gap between intelligence and wisdom.

[00:20:04] **Tim:** Mhm

[00:20:09] **Adam:** Right.

[00:20:09] **Adam:** So, for example, I've got this app I've been working on called Jump Run.

[00:20:13] **Ben:** Mhm, mhm,

[00:20:14] **Adam:** It's a skydiving manifest management, uh, application, I guess you could say, or organization tool.

[00:20:20] **Adam:** and I, I have started on sort of a new phase or a new module of it where I'm going to be importing data from a external service.

[00:20:23] **Tim:** mhm.

[00:20:29] **Adam:** Right?

[00:20:29] **Adam:** It's a service we use to do like, online bookings and waiver collection, that sort of stuff.

[00:20:34] **Adam:** And they have an API and they have web hooks and like, okay, cool, I can, I can integrate with that.

[00:20:38] **Adam:** And so I tell it what I want to do and I say this is kind of the general gist of what I'm trying to accomplish.

[00:20:43] **Adam:** And this is what I can already tell.

[00:20:44] **Tim:** Mhm

[00:20:45] **Adam:** I know I'm going to have to make modifications to this part of the data model, and I want to change the UI this way to support that.

[00:20:52] **Adam:** That's kind of the.

[00:20:53] **Adam:** I'm kind of visualizing an end point and I, the, the, the path in the middle.

[00:20:58] **Adam:** That's what it is.

[00:20:59] **Adam:** The skill that I'm thinking of is called Wayfinder.

[00:21:02] **Adam:** Right?

[00:21:02] **Ben:** Mhm mhm.

[00:21:02] **Adam:** So you, when you can visualize the goal, but you can't really think of everything down the middle of the path between where you are and that goal, you use his Wayfinder skill.

[00:21:05] **Tim:** mhm.

[00:21:11] **Adam:** anyway, that Wayfinder skill will ask you questions to help you figure out and break down the process of Getting from where you are to where you want to be.

[00:21:19] **Adam:** And

[00:21:21] **Adam:** it, it is intelligent, right?

[00:21:23] **Adam:** I can say, okay, oh, I need, you know, this is a, serverless application, right?

[00:21:23] **Tim:** Mhm

[00:21:26] **Adam:** It runs effectively on a collection of Lambda functions.

[00:21:29] **Adam:** And so there's not a server running.

[00:21:30] **Adam:** I can't just do a set timeout or use Cron on the, the server itself to run background tasks.

[00:21:31] **Ben:** Mhm, mhm.

[00:21:36] **Adam:** I have to use something external to the server to trigger any background processing that I want to do outside of user interaction requests, right?

[00:21:43] **Tim:** mhm.

[00:21:47] **Adam:** And so I'm like, you know, I know what CRON is, but I don't know what services might be out there.

[00:21:53] **Adam:** you know, and I ask it, like, do some research and tell me what you think I should use to, to manage Cron like

[00:22:01] **Adam:** necessities for my application.

[00:22:02] **Tim:** Mhm

[00:22:03] **Adam:** And it can go, okay, well, I see you're using Vercel and I see you're using Upstash as you're like, Redis session storage and, and a couple of other things.

[00:22:10] **Adam:** And so it goes and does research on do any of those companies have similar products and what other things are out there in the world?

[00:22:16] **Adam:** And it comes back and it's like, okay, these are what I looked at.

[00:22:19] **Adam:** This is what I don't think is a good fit because of xyz.

[00:22:22] **Adam:** Like, the Vercel.

[00:22:22] **Tim:** mhm.

[00:22:24] **Adam:** Vercel has a Cron like feature.

[00:22:27] **Adam:** But I'm on the free tier of Vercel, and the, the free tier doesn't include Cron any more frequent than, I think, like once a day or maybe it's once an hour or something like that.

[00:22:37] **Adam:** But like, it's You can't go any more frequent than a certain amount.

[00:22:40] **Adam:** And I need the jobs to be more frequent than that.

[00:22:42] **Adam:** and so, like, for that reason, Vercel gets eliminated, uh, from the list.

[00:22:45] **Ben:** Sa mhm.

[00:22:45] **Tim:** Mhm

[00:22:46] **Adam:** So it does this and it makes, you know, five or six suggestions.

[00:22:49] **Adam:** And it says based on all this information that I found, this is my suggestion.

[00:22:52] **Adam:** And I look at it, I'm like, okay, well that's a reasonable suggestion.

[00:22:55] **Tim:** mhm.

[00:22:55] **Adam:** But I just, it doesn't feel right.

[00:22:57] **Adam:** Like it's suggesting a product that's really new and unproven and has no SLA.

[00:23:03] **Adam:** And it's like, this doesn't feel like something I want to

[00:23:07] **Adam:** build into a system that people are depending on me for, right?

[00:23:10] **Adam:** And so I go and I do some additional research on my own and I land on a service called cron-job.org and if you guys want to send me 30 bucks, I'll donate that to charity too.

[00:23:16] **Tim:** Mhm

[00:23:19] **Ben:** A little on the nose.

[00:23:21] **Adam:** Uh,

[00:23:22] **Adam:** but apparently this was.

[00:23:23] **Adam:** I'd never heard of it before, but apparently this thing has been around for a very long time.

[00:23:26] **Adam:** Cron.

[00:23:27] **Adam:** cron-job.org and um, it's totally free to use.

[00:23:31] **Adam:** There's like no limit.

[00:23:31] **Ben:** Sa.

[00:23:32] **Adam:** You can have unlimited Cron jobs as long as you're not abusing the service.

[00:23:35] **Tim:** mhm.

[00:23:35] **Adam:** they also don't offer an SLA, but they have been around forever.

[00:23:39] **Adam:** And you know, obviously, to a reasonable extent they seem to be pretty stable and stuff.

[00:23:44] **Adam:** So I think that's what I'm going to build on.

[00:23:48] **Adam:** But it just like the, the part that was missing the wisdom was like understanding the human preference for or like risk tolerance.

[00:23:53] **Tim:** Mhm.

[00:23:58] **Ben:** Mm mhm.

[00:23:58] **Adam:** And you know, I guess for whatever reason it just didn't, it didn't ask me the right questions to

[00:24:05] **Adam:** eliminate the, the one that it did suggest,

[00:24:09] **Adam:** or the one that it suggested I ended up not liking because I don't think it asked me the right questions to

[00:24:16] **Adam:** get my.

[00:24:17] **Adam:** What I would think about that particular thing.

[00:24:19] **Adam:** Does that make sense?

[00:24:20] **Tim:** Mhm.

## [00:24:20] Overestimating Human Wisdom

[00:24:20] **Tim:** So I'm going to push back here.

[00:24:22] **Tim:** I think we greatly overestimate human wisdom.

[00:24:27] **Adam:** Certain humans, sure.

[00:24:28] **Tim:** Certainly I mean, okay, so

[00:24:31] **Tim:** you know, back in the day, you know, as I was growing up

[00:24:33] **Ben:** Mhm mhm.

[00:24:35] **Tim:** uphill both ways in the snow, um, barefoot.

[00:24:37] **Adam:** Barefoot.

[00:24:37] **Adam:** Mhm.

[00:24:38] **Tim:** Yeah.

[00:24:39] **Tim:** I mean we thought, well, you know, it's like a lot of people just don't have enough information.

[00:24:44] **Tim:** Right.

[00:24:44] **Tim:** Like if your family couldn't afford the encyclopedia set, you know, that cost a lot of Money, you just didn't have good access to educate, you didn't learn a lot, right?

[00:24:52] **Tim:** So getting cram a whole lot of facts in your head, therefore you're not smart or you didn't get wise.

[00:24:57] **Tim:** And then the Internet came out and we had access for free to all the world's knowledge that had been indexed and people weren't getting any smarter or any wiser.

[00:25:07] **Tim:** Um, I think the definition, my definition of wisdom is

[00:25:12] **Tim:** the application of knowledge, right?

[00:25:13] **Tim:** You can know something, you can even understand it, but if you don't know how to actually apply that, that's not, you don't, you lack wisdom, you have a lot of knowledge, you understand a lot of things.

[00:25:15] **Ben:** Mhm mhm.

[00:25:15] **Adam:** Mhm.

[00:25:25] **Tim:** Do you know how to actually do anything with it?

[00:25:25] **Adam:** Mm mhm.

[00:25:27] **Tim:** Then you don't really have any wisdom about it.

[00:25:30] **Tim:** Um, I'll push back that one thing I think surprisingly, um, AIs are good at or LLMs are good at is inference.

[00:25:35] **Adam:** Mhm.

[00:25:40] **Tim:** So I had, I can't remember the exact thing, but basically I gave, I asked a question to the AI, to, to Claude and it said, it answered the question directly at first, right?

[00:25:50] **Tim:** Said, it said, no, this thing is not there.

[00:25:53] **Ben:** Mhm.

[00:25:53] **Tim:** But a better question is like, was it ever there or was it there?

[00:25:57] **Adam:** Mhm.

[00:25:58] **Tim:** Just it doesn't show.

[00:25:59] **Tim:** I forget what it was.

[00:26:00] **Adam:** Yeah, you were asking.

[00:26:01] **Adam:** Yeah, you posted this in our Discord and I remember.

[00:26:03] **Tim:** Yeah,

[00:26:03] **Adam:** So you, you were asking like, are there any linked tickets to this ticket that, that, the.

[00:26:07] **Tim:** yeah.

[00:26:07] **Tim:** and it said, no, there's no links.

[00:26:09] **Adam:** Right,

[00:26:09] **Tim:** But the better question is, are there other tickets that address this?

[00:26:12] **Adam:** right,

[00:26:13] **Tim:** I'm like, yeah, you're right, that's actually what I meant.

[00:26:15] **Tim:** It inferred that I've dealt with programmers, human programmers, where I face to face said, are there any link tickets on this ticket here that would affect this?

[00:26:24] **Tim:** And they're like, nope, there's no link tickets

[00:26:25] **Adam:** Right.

[00:26:25] **Adam:** M.

[00:26:26] **Adam:** Yeah, it's kind of the more autistic reading versus the, the thoughtful.

[00:26:27] **Ben:** Well, this is why.

[00:26:27] **Tim:** done.

[00:26:29] **Tim:** Yeah, exactly like they answered the question, they didn't infer that I, what I was really looking for.

[00:26:31] **Adam:** Yeah.

[00:26:34] **Tim:** And I was like pretty surprised about the inference that, that LLMs can do.

[00:26:37] **Adam:** Mhm.

[00:26:38] **Tim:** And I know why.

[00:26:39] **Tim:** They, it's a word trick, right?

[00:26:41] **Tim:** They, their context window is big and humans have other things going on in their head.

[00:26:46] **Tim:** They're not just thinking about what you asked, they're thinking about, I'm really hungry, my wife yelled at me this morning, the dog peed on the floor, all this other background processes going on.

[00:26:50] **Ben:** Mhm

[00:26:56] **Tim:** Whereas the computer is like, it's only answering you.

[00:26:59] **Tim:** And so it doesn't cloudy that with all that other stuff.

[00:27:00] **Adam:** M.

[00:27:00] **Adam:** Yeah, I, I should have said.

[00:27:02] **Adam:** Literally I said autistic there.

[00:27:03] **Adam:** I should have said.

[00:27:04] **Adam:** It's very literal translation of the question.

[00:27:05] **Tim:** Literal, I mean could be autistic, but yeah, very literal.

[00:27:06] **Adam:** Reading of the question.

[00:27:06] **Adam:** Yeah,

[00:27:08] **Ben:** mhm.

[00:27:08] **Adam:** yeah,

[00:27:09] **Tim:** That's a better, better phrasing.

[00:27:11] **Tim:** So I mean, yeah, I get where we're coming from that, you know, intelligence is not wisdom.

[00:27:17] **Tim:** And I do agree with that.

[00:27:18] **Tim:** But I think there's intelligent systems that don't have wisdom and I think there's intelligent humans who don't have wisdom.

[00:27:25] **Ben:** Mhm.

[00:27:26] **Adam:** well, sure.

[00:27:27] **Adam:** Yeah, I, I don't disagree with that.

[00:27:30] **Adam:** but I guess my point in saying that is more like, you know, the, the whole marketing hype around this is they're, they're aiming at artificial intelligence and

[00:27:30] **Tim:** Mhm.

[00:27:40] **Adam:** maybe they're making meaningful steps towards that.

[00:27:42] **Adam:** That's not for me to say.

[00:27:44] **Adam:** But I think what I at this moment am more interested in is artificial wisdom.

## [00:27:50] Skills Versus npm Packages

[00:27:50] **Tim:** Mhm.

[00:27:50] **Ben:** Well, it's so interesting that the, uh, skills that you're talking about are Matt Pocock's.

[00:27:57] **Ben:** Again, going back to the interview that we just watched together between Matt Pocock and Robert Martin, because in that,

[00:27:57] **Adam:** Mhm.

[00:28:01] **Adam:** Yeah.

[00:28:03] **Adam:** Yeah,

[00:28:06] **Ben:** I forget what skill Robert Martin was talking about.

[00:28:08] **Ben:** Maybe he was talking about m like building a Mutation test or something.

[00:28:12] **Ben:** And Matt Pocock was like, oh, how do we get that kind of a skill?

[00:28:13] **Tim:** Yeah.

[00:28:13] **Tim:** Mutation.

[00:28:13] **Adam:** Yeah.

[00:28:16] **Ben:** How can people get a hold of that?

[00:28:18] **Adam:** Mm mhm.

[00:28:18] **Ben:** And Robert Martin said, well, you don't.

[00:28:20] **Ben:** You might point your agent at my skill and say, how can I build a skill like this that works for the type of stuff that I do?

[00:28:26] **Adam:** Right.

[00:28:28] **Ben:** And I thought that was one.

[00:28:30] **Ben:** That's one of those things I feel like is just much easier to say than it is to actually do in a, uh, in a meaningful way.

[00:28:35] **Tim:** M.

[00:28:35] **Tim:** But I did it this week.

[00:28:36] **Tim:** I did it this week, Ben.

[00:28:38] **Ben:** Okay, so, so Tim aside, who's obviously, you know, a stellar rock star here, um, but I think even the idea of, like installing people's skills, like I've even heard people refer to using npm to share skills like you can npx install other people's skills kind of stuff.

[00:28:38] **Tim:** I did it.

[00:28:50] **Tim:** Mhm.

[00:28:54] **Adam:** Mhm.

[00:28:57] **Adam:** Yeah.

[00:28:59] **Ben:** And again, going back to this abdication of opinions, it's easy, I think, to equate, oh, well, someone made an Axios, uh, AJAX client.

[00:29:10] **Ben:** How is that any different from someone building a skill that helps me craft software?

[00:29:11] **Tim:** Mhm

[00:29:16] **Ben:** And it's like it.

[00:29:17] **Ben:** On one hand, I get that that seems like the same thing.

[00:29:19] **Adam:** Mhm.

[00:29:21] **Ben:** It is a packaging of information that someone is providing and you are taking it and using it to build.

[00:29:27] **Ben:** But I feel like it's, it's the opinion part that really is the differentiator.

[00:29:31] **Tim:** mhm.

[00:29:33] **Ben:** Yes.

[00:29:34] **Ben:** A, uh, library like Axios or React or Svelte, they have opinions on how software should be built.

[00:29:43] **Ben:** But those opinions, aren't fuzzy.

[00:29:46] **Ben:** Uh,

[00:29:47] **Ben:** they're very concrete, they're very well articulated in the code.

[00:29:50] **Tim:** Mhm

[00:29:51] **Ben:** You run a Svelte application and it does the same thing every single time.

[00:29:55] **Ben:** It's very different than installing a skill that is very fuzzy and might depend on the model you're running and the amount of effort that's being put in place and the agent that you're actually using.

[00:29:55] **Adam:** Mm mhm.

[00:29:59] **Adam:** Mhm.

[00:30:06] **Ben:** And uh, you're like, okay, now I'm just blindly.

[00:30:10] **Ben:** And I don't mean blindly in a, uh, pejorative way, I mean blindly in that you, someone said this is the way you should build software.

[00:30:11] **Tim:** mhm.

[00:30:18] **Ben:** And I'm just taking it and I'm installing it and I'm running it.

[00:30:21] **Ben:** And that feels very different to me.

[00:30:22] **Ben:** And I, and maybe that's just an emotional difference, but again, it feels like I have such an aversion to that because it feels like I'm abdicating,

[00:30:31] **Adam:** Mhm.

[00:30:32] **Ben:** uh, strong opinions about how software should be built.

[00:30:35] **Ben:** And the thing is like, I don't.

[00:30:35] **Tim:** You know, Ben, you were just caught.

[00:30:36] **Tim:** You, you're just calling out every single person in the 2000s who went to your blog and copy and pasted all your stuff and ran it in their system.

[00:30:45] **Ben:** But at least they saw the thing, you know, at least they see the code you know, even if you go to Stack Overflow and you copy and paste the code, you're seeing it, it's not, it's not being downloaded as a uh, an opaque binary that you're just executing.

[00:30:51] **Tim:** Did they though?

[00:31:00] **Ben:** And I know you can go in and look at the skills.

[00:31:00] **Tim:** I mean it, it passed by their eyes.

[00:31:02] **Tim:** Do you think they read it?

[00:31:03] **Adam:** So are

[00:31:04] **Tim:** I promise you that, uh, there's tons of, there's tons of functions you wrote back in the day that I cargo culted 100% never read one bit.

[00:31:12] **Adam:** Oh, are uh, are you arguing that npm modules are bad?

[00:31:13] **Tim:** Mhm.

[00:31:15] **Adam:** Ben,

[00:31:16] **Ben:** No, no, no, I'm saying that, I'm saying that

[00:31:19] **Adam:** did you never see the code?

[00:31:20] **Ben:** it,

[00:31:21] **Ben:** no, I'm um, I'm saying that I think an npm module is a, a category difference from something like a skill because it, it will do that.

[00:31:29] **Adam:** Okay, go on, say more.

[00:31:33] **Ben:** It, it's because it has such a clear contract.

[00:31:35] **Tim:** Sa.

[00:31:38] **Ben:** It is less a, uh, it's deterministic, but it's even more so than deterministic.

[00:31:40] **Adam:** It's deterministic.

[00:31:42] **Adam:** Mhm.

[00:31:46] **Ben:** It's like.

[00:31:47] **Ben:** It's just much more clear what its intentions are.

[00:31:51] **Ben:** You know, even if I don't understand how Axios is implemented under the hood, I can see that it has get, ah, post put patch, delete methods and it takes these arguments and it returns promises and it has ways to serialize and deserialize JSON.

[00:31:54] **Tim:** Mhm.

[00:32:02] **Adam:** M.

[00:32:06] **Ben:** Like it has a, it has a concrete set of contracts that, yeah.

[00:32:10] **Adam:** Got an interface.

[00:32:11] **Adam:** Yeah,

[00:32:12] **Ben:** That dictate this is how you do it.

[00:32:13] **Ben:** So it's.

[00:32:14] **Ben:** While the implementation might be opinionated.

[00:32:15] **Tim:** But it's deterministic and it's deterministic and you trust it.

[00:32:19] **Tim:** I think the issue you're saying is you don't trust the AI to come to the same spot.

[00:32:20] **Adam:** Yeah.

[00:32:23] **Adam:** M.

[00:32:24] **Ben:** yes.

[00:32:25] **Ben:** And so uh, and because of that it feels weird to

[00:32:29] **Ben:** see a skill that someone has said, hey, I get value out of this skill.

[00:32:33] **Ben:** And then for other people to just be like, install that skill.

[00:32:33] **Tim:** Mhm

[00:32:37] **Ben:** And now I have that.

[00:32:38] **Ben:** You know, I know kung fu.

[00:32:41] **Adam:** Yeah.

[00:32:41] **Adam:** I mean it is and it is.

[00:32:43] **Adam:** I mean it both is and isn't that way.

[00:32:45] **Adam:** Right.

[00:32:45] **Adam:** Like, uh, so I installed a skill that I really like.

[00:32:45] **Ben:** Right,

[00:32:49] **Adam:** It's called Unslop.

[00:32:50] **Adam:** It is not a Matt Pocock skill.

[00:32:52] **Adam:** uh, why can't.

[00:32:53] **Tim:** mhm.

[00:32:53] **Adam:** Why can't I remember who created?

[00:32:55] **Adam:** I feel really bad for not remembering who created.

[00:32:57] **Adam:** I'm sure if you just Google Unslop, you'll find the right one.

[00:33:00] **Adam:** But either way, basically it's just.

[00:33:02] **Adam:** It's a skill that like, tries to teach the LLM, um, to remove all of the giveaways of its writing style and, and also to like, tighten up the writing to make it sound more human.

[00:33:12] **Ben:** Right.

[00:33:13] **Ben:** Mhm.

[00:33:14] **Tim:** Mhm

[00:33:16] **Adam:** Right.

[00:33:17] **Adam:** And the, the

[00:33:20] **Adam:** metadata in the skill that like, it uses to determine when to turn itself on and, or that the harness uses to determine when to include the skill in the request or whatever is of this particular skill says like, you always have to use it.

[00:33:34] **Adam:** If you're, if we're generating text, you have to use it so that it even like, unslops the responses that it gives you in your session.

[00:33:35] **Tim:** mhm.

[00:33:40] **Adam:** It's not just about like, oh, we're writing a, uh, a webpage.

[00:33:43] **Adam:** I need to make sure that the content that I put on this web page is not slop.

[00:33:46] **Adam:** It's like when I answer your question, I have to not give you slop back.

[00:33:48] **Ben:** Sa.

[00:33:50] **Adam:** So, um, and you can just, you can.

[00:33:53] **Adam:** It's.

[00:33:53] **Adam:** It's not a tiny skill.

[00:33:55] **Adam:** Like.

[00:33:55] **Tim:** Mhm.

[00:33:55] **Adam:** Right, so, uh, there was a skill.

[00:33:57] **Adam:** It may not have even been a skill.

[00:33:59] **Adam:** I think there was just this line that I had advocating for

[00:34:03] **Adam:** in your, your CLAUDE.md or your AGENTS.md ah, a while back.

[00:34:07] **Adam:** And I still have it in mind.

[00:34:08] **Adam:** It's sacrifice, ah, grammar for the sake of concision,

[00:34:12] **Ben:** Mm.

[00:34:12] **Ben:** Mhm, mhm, mhm,

[00:34:13] **Adam:** which is just basically a, ah, nice concise way of saying, um.

[00:34:18] **Adam:** I don't care if you have to make sentences that don't sound good.

[00:34:22] **Adam:** I want you to give me less content back.

[00:34:24] **Adam:** Right.

[00:34:25] **Adam:** Say the same thing, but say it more concisely.

[00:34:27] **Tim:** Caveman.

[00:34:27] **Adam:** Um, yeah, almost exactly like that.

[00:34:30] **Adam:** Yeah.

[00:34:30] **Adam:** and.

[00:34:31] **Adam:** And it worked pretty well.

[00:34:31] **Tim:** Mhm

[00:34:32] **Adam:** Right.

[00:34:33] **Adam:** And a.

[00:34:34] **Adam:** I think that it worked well at reducing the amount of tokens that were generated.

[00:34:37] **Adam:** So it kept quota usage down and money usage down, which was nice, but also it was less frustrating to work with the bot at that point.

[00:34:46] **Adam:** But, you know, other skills.

[00:34:47] **Adam:** Going back to your point, Ben, about it not being deterministic and not.

[00:34:50] **Ben:** Mhm mhm.

[00:34:50] **Tim:** mhm.

[00:34:51] **Adam:** And not feeling

[00:34:53] **Adam:** uh, like it's putting something between yourself and the, the bot or the machine.

[00:34:57] **Adam:** Right?

[00:34:57] **Adam:** Like, and you, you are getting even further away from understanding and appreciating how it works.

[00:35:02] **Adam:** You know, the, These Matt Pocock skills, I think are A good example of how to write skills.

[00:35:05] **Adam:** Well and that's why they're popular because like the grill-me or the wayfinder stuff, if you use it a couple times, you start to pick up on very specific patterns in the way it works.

[00:35:08] **Tim:** Mhm

[00:35:14] **Adam:** Right.

[00:35:14] **Adam:** Like it always formats the questions the same way.

[00:35:17] **Adam:** And I haven't necessarily read the skill content itself deeply, I've skimmed it.

[00:35:23] **Adam:** But like you know, it always asks questions and it puts the little, was it a little red question mark emoji before the question and that helps it stand out and like visually identify.

[00:35:28] **Tim:** mhm.

[00:35:32] **Adam:** Okay, this is where the next question starts.

[00:35:34] **Adam:** And then it always gives you a suggestion, like this is my suggested answer.

[00:35:34] **Ben:** Mhm mhm.

[00:35:39] **Adam:** And that way you, if you're parsing through a list of 10 questions you can just go 1 colon yes.

[00:35:45] **Adam:** 2 colon yes.

[00:35:46] **Adam:** 3 colon oh actually no, this is how I disagree.

[00:35:48] **Adam:** Blah blah blah.

[00:35:48] **Tim:** Mhm

[00:35:49] **Adam:** 4 colon yes.

[00:35:50] **Adam:** 5 colon, yes.

[00:35:50] **Adam:** 6 colon, yes, whatever.

[00:35:51] **Adam:** So it makes it real easy to just accept those decisions or suggestions.

[00:35:57] **Adam:** and, and there's lots of little things that you can do that make the experience of using a skill more deterministic.

[00:36:03] **Adam:** Even though the the result of the skill is still going to be stochastic or non-deterministic right.

[00:36:07] **Tim:** mhm.

[00:36:10] **Adam:** Like it's still a next token generation machine, but you're just kind of running it through a filter that says you have to format it this way or it has to do this particular thing.

[00:36:14] **Ben:** Right.

[00:36:21] **Adam:** You have to ask me a minimum of 10 questions or whatever it's going to be.

[00:36:23] **Adam:** Right?

[00:36:24] **Ben:** So.

[00:36:25] **Ben:** Okay.

[00:36:25] **Tim:** Mhm

[00:36:26] **Ben:** Yes, I.

[00:36:27] **Ben:** Okay.

## [00:36:27] Confidence and Load-Bearing Tokens

[00:36:27] **Ben:** I just have like so many random thoughts.

[00:36:30] **Ben:** Right.

[00:36:30] **Adam:** Yeah.

[00:36:30] **Ben:** So if you think about this thing as a next token generator predictor,

[00:36:35] **Ben:** every token to some degree is a variable.

[00:36:39] **Ben:** So the bigger your context window is essentially the more variables you have.

[00:36:46] **Tim:** mhm.

[00:36:46] **Ben:** And

[00:36:48] **Ben:** the problem is that I don't feel like I have confidence.

[00:36:54] **Ben:** And this is so much of the abdication of opinion for me comes back to my own insecurities and my lack of confidence in my own understanding of how any of this works.

[00:37:04] **Ben:** So uh, let's just say as a thought experiment,

[00:37:08] **Ben:** I install this skill that somebody has and I look at it and you know, let's say it's four pages of markdown for whatever that means.

[00:37:16] **Ben:** I don't know what in that is to quote Claude, load-bearing or what you know, or what is just fluff.

[00:37:24] **Ben:** You know, it could be that there's four pages of markdown and the last sentence is and if you don't get this right, you're fired.

[00:37:30] **Adam:** Mhm.

[00:37:31] **Ben:** And like uh, maybe that was actually the most important part of that entire skill.

[00:37:35] **Ben:** And the rest of it was just sort of fluff.

[00:37:38] **Tim:** Mhm.

[00:37:38] **Ben:** And because I don't really have a good sense of how any of it works, I don't realize that that four pages could have been use best practices or you're fired, and maybe that would have been enough to get the job done.

[00:37:43] **Adam:** Sa.

[00:37:51] **Adam:** Mhm.

[00:37:52] **Tim:** It's an easy experiment to figure that out.

[00:37:52] **Ben:** And.

[00:37:54] **Ben:** But is it though, because the models are constantly changing, uh, the context that it's pulling in is constantly changing.

[00:38:00] **Tim:** Sa.

[00:38:02] **Ben:** Right.

[00:38:03] **Ben:** You could ask a question one day

[00:38:05] **Ben:** and the token machine in the sky gives it a tool to run and that pulls in one file and then you ask it the same exact question the next day and the token machine in the sky tells it to run a different tool.

[00:38:10] **Tim:** Mhm.

[00:38:16] **Ben:** And now suddenly that context window is completely different.

[00:38:19] **Adam:** Mhm.

[00:38:20] **Ben:** And so like, did, uh, like which of the, you know, 300 tokens in my original prompt, which is the one that went wrong today?

[00:38:28] **Ben:** I don't know.

[00:38:29] **Adam:** I, I doubt it would have anything to do with your original prompt.

[00:38:29] **Tim:** I

[00:38:31] **Adam:** I think it has everything to do with, you know, what it, how did they change the model overnight and you know what new context is available.

[00:38:39] **Adam:** Right.

[00:38:39] **Adam:** Like what, Part of what it's doing is you know, let, for lack of a better word, let's say it's doing Google searches, right.

[00:38:45] **Adam:** And so you know, it gets slightly different search results back.

[00:38:45] **Ben:** Right.

[00:38:48] **Adam:** And that could not even be the fault of the LLM provider or the LLM itself.

[00:38:53] **Tim:** Yeah,

[00:38:54] **Adam:** It could just be like the Internet writ large.

[00:38:56] **Tim:** I mean 100%.

[00:38:58] **Tim:** Everything you're saying, Ben, is you have trust issues.

[00:39:01] **Ben:** Well, m.

[00:39:01] **Tim:** You have trust issues with LLM, which.

[00:39:01] **Ben:** It's.

[00:39:02] **Ben:** I have confidence.

[00:39:02] **Ben:** I have confidence issues.

[00:39:04] **Tim:** Exactly.

[00:39:05] **Tim:** Um, but, but that's not a bad thing.

[00:39:06] **Tim:** It's like the thing is so new and it hasn't proven itself and there's evidence that it just does weird stuff all the time, but sometimes it does really, really good stuff.

[00:39:14] **Adam:** Mhm.

[00:39:16] **Tim:** So it's like, uh, the tools like become a thing that we have to use.

[00:39:19] **Tim:** But it's like we don't trust it.

[00:39:21] **Tim:** And we're not going to trust it until it, you know, has proven itself.

[00:39:24] **Tim:** And the AI we're using today is the worst AI we'll ever use.

[00:39:30] **Tim:** It's only going to get better just the way computers have gotten better.

[00:39:30] **Ben:** Mhm.

[00:39:34] **Tim:** Does that mean it's going to get general intelligence?

[00:39:34] **Ben:** Did anyone,

[00:39:36] **Tim:** No, I, I don't know.

[00:39:38] **Tim:** But it's definitely going to get a whole lot more effective and a whole lot more trustworthy over time.

[00:39:43] **Ben:** Did anyone ever see, I think maybe like 25 years ago, 30 years ago, there was a movie called Mumford where a guy pretends to be a psychotherapist in a small town like middle America.

[00:39:53] **Adam:** I was five years old, Ben,

[00:39:56] **Tim:** I was older than that.

[00:39:57] **Adam:** 25 years ago.

[00:39:59] **Adam:** No, I'm not 25, but I wish I was.

[00:40:01] **Adam:** And that's where I mentally keep myself.

[00:40:04] **Tim:** No, I've never.

[00:40:04] **Tim:** Mumford.

[00:40:05] **Tim:** I just know Mumford and Sons.

[00:40:06] **Adam:** Yeah, same.

[00:40:07] **Ben:** So the high level premise of the movie is this guy, he's not a trained therapist, he just shows up in this town and starts pretending that he's a therapist and starts treating people.

[00:40:12] **Tim:** Mhm.

[00:40:18] **Ben:** And it's actually a very touching movie.

[00:40:20] **Ben:** Um, and he has this one patient, let's just call him a very average looking character, non, uh, you know, and he has these extensive fantasies, sexual fantasies, but in his fantasies he's this like stud porn looking kind of a guy.

[00:40:31] **Tim:** Mhm.

[00:40:35] **Adam:** Mhm.

[00:40:39] **Ben:** And at one point the therapist is having a conversation with another person, you know, violating HIPAA.

[00:40:45] **Ben:** And that's part of the comedy of it all.

[00:40:47] **Ben:** It says like, I just, all I want this guy to do is get to a point where he's in his own fantasies.

[00:40:54] **Ben:** And that would be a huge breakthrough.

[00:40:56] **Ben:** And I feel like that's the point that I'm at now is I, all I want to do is get to a point where I can stop telling people that I'm using Claude, even though I'm using Claude.

[00:41:04] **Tim:** M.

[00:41:09] **Tim:** Oh, I thought you may want to be in porn.

[00:41:11] **Adam:** Mhm.

[00:41:13] **Ben:** You know, it's like every time I talk about the work that I'm doing, it's this is what Claude said.

[00:41:17] **Adam:** Mhm.

[00:41:18] **Ben:** Or I'll have Claude do some research.

[00:41:20] **Ben:** Or let me, I'll, I'll, I'll debug this with Claude.

[00:41:25] **Ben:** I, I'm

[00:41:27] **Ben:** right now feeling very much Like

[00:41:30] **Ben:** I'm an operator of a machine that is more powerful than me, and because of that I have to constantly reference the machine, whereas historically I've never had to do that.

[00:41:32] **Tim:** Mhm.

[00:41:37] **Adam:** Mhm.

[00:41:42] **Ben:** I never talked about, uh, let me, you know, let me Google that.

[00:41:43] **Tim:** Sa.

[00:41:47] **Ben:** I mean, I might, maybe I'll say Google that.

[00:41:49] **Ben:** Like I might, I would probably say, like I'll do some research or I'll look at the code, or I'll look at the database to see if I can figure out what's going on.

[00:41:55] **Tim:** Mhm.

[00:41:57] **Ben:** And in any of those statements, I could be using Claude under the hood, but the people that I'm talking to don't need to know that.

[00:42:04] **Adam:** Mhm.

[00:42:04] **Ben:** It's just an implementation detail on my end.

[00:42:07] **Ben:** But right now I feel like I have, uh, so much insecurity about my

[00:42:14] **Ben:** ability to understand what's going on that I'm constantly pulling Claude into the conversation as a way to almost abdicate the responsibility of coming to a successful outcome.

[00:42:23] **Adam:** M.

[00:42:23] **Adam:** Right.

[00:42:25] **Adam:** Yeah.

[00:42:26] **Adam:** It's not my opinion, it's Claude's opinion.

[00:42:27] **Adam:** So if you don't like it, then blame Claude.

[00:42:28] **Ben:** Right.

## [00:42:32] Naming Claude and Culpability

[00:42:32] **Tim:** Which brings up culpability.

[00:42:36] **Tim:** Um,

[00:42:36] **Ben:** I don't know, I mean, how much do you guys reference Claude Code or, you know, whatever agents you're using when you talk about the work?

[00:42:37] **Adam:** Did you want to.

[00:42:41] **Adam:** You know, honestly,

[00:42:43] **Adam:** I'm Glad you mentioned that, because I think I used to do that more back when I was using Claude.

[00:42:50] **Adam:** and I do it less now that I'm not using Claude and I'm using Codex or ChatGPT or whatever you want to call it from OpenAI.

[00:42:56] **Tim:** Uh, is that because it's not like a person's name?

[00:42:59] **Adam:** Yes.

[00:42:59] **Adam:** I 100% think that that is a psychological effect of giving the LLM a

[00:43:00] **Ben:** Oh, interesting.

[00:43:07] **Adam:** name that is also a name we're used to using for humans.

[00:43:12] **Ben:** Mhm.

[00:43:12] **Ben:** It's almost like it turns into an oracle.

[00:43:12] **Adam:** Um,

[00:43:14] **Adam:** right.

[00:43:15] **Adam:** It makes it feel like a person.

[00:43:17] **Adam:** Right.

[00:43:17] **Adam:** Even if subconsciously, even if momentarily in that conversation, it makes you think of it more like a person and makes it feel smarter.

[00:43:26] **Adam:** I think it's a brilliant and devious move by Anthropic.

[00:43:29] **Tim:** Mhm.

[00:43:32] **Adam:** So, uh, yeah, like, that's where I'm at.

[00:43:35] **Adam:** I mean, to answer your question, uh, it did, but don't.

[00:43:35] **Ben:** Mhm.

[00:43:35] **Tim:** I mean, doesn't the name Anthropic I mean being human like

[00:43:40] **Ben:** I think you might be right.

[00:43:41] **Tim:** Anthro.

[00:43:42] **Tim:** Anthro is human.

[00:43:43] **Adam:** You're.

[00:43:44] **Adam:** I think you're thinking anthropomorphic.

[00:43:46] **Ben:** Well, we have anthropomorphize,

[00:43:49] **Ben:** but anthropom.

[00:43:49] **Ben:** Yeah, like there's a, there's a, uh, genealogy, an etymology.

[00:43:50] **Tim:** Let me, let me ask Claude.

[00:43:51] **Tim:** Hold on.

[00:43:52] **Ben:** Is that the.

[00:43:52] **Adam:** You don't have to ask Claude.

[00:43:53] **Adam:** We have dictionaries involving or concerning the existence of human life, especially as a constraint on the theory.

[00:44:00] **Adam:** On theories of the universe.

[00:44:01] **Tim:** Yep.

[00:44:02] **Adam:** So, yeah, you're pretty much right there.

[00:44:03] **Tim:** Yeah.

[00:44:04] **Tim:** So human like basically.

[00:44:05] **Ben:** Sa?

[00:44:05] **Adam:** Or caused by human beings, which would be anthropogenic.

[00:44:09] **Tim:** Gotcha.

[00:44:09] **Adam:** But.

[00:44:10] **Tim:** So I mean even their company name is kind of leaning into that humanish.

[00:44:14] **Adam:** Yeah,

[00:44:16] **Tim:** I mean at least ChatGPT was just like we're a chat bot.

[00:44:20] **Adam:** Yeah,

[00:44:21] **Tim:** We're just a chatbot.

[00:44:22] **Tim:** Which is what they are.

[00:44:24] **Tim:** Amazing, um, chatbots.

[00:44:25] **Tim:** But yeah.

[00:44:25] **Adam:** Yeah, it was a total accident.

[00:44:26] **Adam:** There's.

[00:44:26] **Adam:** They did a great interview.

[00:44:28] **Adam:** I forget who it was, but somebody from OpenAI did a great interview on a podcast from the Verge, which is like a news

[00:44:36] **Ben:** I love the Verge.

[00:44:36] **Tim:** Mhm.

[00:44:36] **Adam:** organization.

[00:44:36] **Adam:** Uh, uh, the.

[00:44:37] **Tim:** Yeah.

[00:44:38] **Adam:** The podcast I'm thinking of is Decoder, which is the, What is he?

[00:44:42] **Adam:** The, the

[00:44:44] **Adam:** editor in chief type person of the Verge.

[00:44:47] **Adam:** His name is Nilay, Patel.

[00:44:49] **Adam:** Yes, thank you.

[00:44:50] **Adam:** I think he's just the editor or whatever, but like, he's the main guy at the Verge, at least editorially or, or, uh, journalistically.

[00:44:51] **Ben:** Sa.

[00:44:51] **Tim:** Mhm.

[00:44:57] **Adam:** it was his podcast and they had somebody on from OpenAI and they were talking about, like, yeah, you know, uh, the whole chat interface for using this thing was a total accident.

[00:45:01] **Ben:** Mhm, mhm.

[00:45:07] **Adam:** Right.

[00:45:07] **Adam:** They had this thing and you could give it.

[00:45:09] **Adam:** It was like a command line tool.

[00:45:10] **Tim:** Mhm

[00:45:10] **Adam:** I think you.

[00:45:11] **Adam:** You could, like, run the tool and give it an input and it would generate some output and.

[00:45:14] **Adam:** Okay, that's cool.

[00:45:15] **Adam:** But then, like, somebody just had this, like, wild idea internally, like, what if we hooked this up to.

[00:45:19] **Adam:** To be more of like a chatbot?

[00:45:21] **Adam:** You know, it just goes back and forth with you automatically.

[00:45:24] **Adam:** And then, like, they loved it internally and they shared it, uh, externally, not thinking it would be as popular as it was, and it like, exploded overnight.

[00:45:31] **Tim:** mhm.

[00:45:32] **Adam:** So.

[00:45:33] **Adam:** Yeah.

[00:45:33] **Tim:** Crazy.

[00:45:34] **Ben:** It is, it is bonkers how this stuff and, and the, and Claude Code wasn't really a product.

[00:45:39] **Ben:** Right?

[00:45:40] **Ben:** That was just what's his name's.

[00:45:40] **Tim:** Sa.

[00:45:41] **Ben:** I can't remember his name.

[00:45:43] **Adam:** Boris Cherny.

[00:45:44] **Ben:** Yeah, that was just like a little fun thing he tried.

[00:45:48] **Adam:** Yeah, I don't remember the.

[00:45:50] **Adam:** The.

[00:45:50] **Adam:** The.

[00:45:50] **Adam:** That far back.

[00:45:51] **Adam:** In the history of Claude Code, I was not an early, early ad.

[00:45:51] **Tim:** Mhm.

[00:45:55] **Ben:** So all I'll say is the way I feel today is like Adam runs up to my door, he knocks on it, he's like, hey, Ben, you want to come out and play?

[00:46:04] **Ben:** And I'm like, I got to go ask my wife.

[00:46:07] **Ben:** And then I go inside and I ask my wife and like, that's how work feels to me right now.

[00:46:07] **Adam:** Mhm.

[00:46:11] **Ben:** People are like, hey, Ben, can you do this ticket?

[00:46:12] **Ben:** I'm big.

[00:46:13] **Ben:** Let me go ask Claude.

[00:46:16] **Ben:** Really what I should say is, of course I can do this.

[00:46:18] **Ben:** And then privately I close the door and say, hey, honey, can I go and play with Adam?

[00:46:24] **Tim:** Sounds about right.

[00:46:26] **Adam:** Dude.

[00:46:26] **Adam:** Yeah, you just, you're, you're having a crisis of confidence.

[00:46:30] **Ben:** Yeah,

[00:46:32] **Ben:** yeah.

[00:46:32] **Adam:** I, I still act like I'm hot at work and then I make, make the LLM do all the work.

[00:46:38] **Adam:** I am still hot.

[00:46:39] **Adam:** S**t.

[00:46:39] **Adam:** I just, I, I have abstracted myself a layer above what I previously was working.

[00:46:44] **Tim:** Mhm

[00:46:44] **Adam:** That's all.

[00:46:45] **Ben:** Mhm.

[00:46:46] **Adam:** All right, well, uh, I think that's about all we have to say on this for, for tonight at least.

[00:46:49] **Adam:** I'm sure we'll have, some good friction on this topic again next week.

## [00:46:54] Patreon

[00:46:54] **Adam:** but in the meantime, this episode of Working Code is brought to you by today's takeaway, Ben's wife, who I, I got permission in advance.

[00:47:02] **Adam:** This, she said we could talk about this.

[00:47:04] **Adam:** So, um,

[00:47:04] **Ben:** Thanks.

[00:47:05] **Ben:** On.

[00:47:06] **Tim:** Thanks.

[00:47:08] **Adam:** and, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:47:11] **Ben:** Mhm.

[00:47:16] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:47:21] **Adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

[00:47:25] **Adam:** You guys rock.

## [00:47:26] Thanks For Listening!

[00:47:26] **Adam:** We are going to go record the after show and that is a special perk just for our patrons.

[00:47:31] **Adam:** So, basically we keep the mics on, we keep talking.

[00:47:33] **Adam:** We're talking about all kinds of random stuff.

[00:47:35] **Adam:** I learned a new sorting algorithm today that I want to share with you guys.

[00:47:38] **Tim:** Mhm.

[00:47:39] **Tim:** Interesting.

[00:47:39] **Adam:** Um, and we're gonna talk about that.

[00:47:40] **Ben:** Sa.

[00:47:41] **Adam:** So see, sometimes it can be coding related, um, but sometimes it's like totally random stuff.

[00:47:43] **Tim:** Yeah.

[00:47:43] **Tim:** Yeah.

[00:47:46] **Adam:** Sometimes we talk about TV.

[00:47:47] **Adam:** You never know what you're gonna get.

[00:47:49] **Adam:** Um, but either way, uh, if you would like to get access to all past and all future after shows, all you have to do is go to patreon.com/workingcodepod and start throwing a few bucks per week our way.

[00:47:51] **Ben:** Mhm.

[00:48:01] **Adam:** Or you can even pay yearly at it and get a slight discount.

[00:48:04] **Adam:** Anyway, that's going to do it for us this Week.

[00:48:06] **Adam:** We'll catch you again next week.

[00:48:07] **Adam:** And until then,

[00:48:09] **Tim:** So you guys, you know who our favorite non-deterministic machines are?

[00:48:13] **Tim:** You guys, your heart matters.

[00:48:15] **Ben:** Nice.

[00:48:16] **Ben:** I like that.

[00:48:16] **Adam:** Nice.
