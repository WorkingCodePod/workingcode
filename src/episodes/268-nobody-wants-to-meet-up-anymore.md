---
title: "268: Nobody Wants to Meet Up Anymore"
description: "Nobody went to those conferences for the talks. You went for the hallway, and for a roomful of people who'd made the same odd career bet you had. This week the hosts go looking for what's left of the developer hang."
date: 2026-07-31
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/268-nobody-wants-to-meet-up-anymore/id1544142288?i=1000779334475"></iframe>

Nobody went to conferences for the talks. You went for the hallway, and for a roomful of people who'd made the same odd career bet you had. We didn't know how good we had it. COVID hit, AI is now everyone's best buddy, and now all these meetups and spaces are slowly disappearing. This week the hosts go looking for what's left of the developer hang.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Anthropic's Project Vend](https://www.anthropic.com/research/project-vend-1) — the AI-run shop behind the tungsten cube story

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/268-nobody-wants-to-meet-up-anymore.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Tim:** I think Adam should start a podcast.

[00:00:02] **Carol:** Oh yeah.

[00:00:03] **Tim:** we can all get together and like have a podcast and have a Discord channel and hang out.

[00:00:06] **Tim:** That'd be.

[00:00:07] **Tim:** Wait a minute.

[00:00:07] **Ben:** I think it could work.

[00:00:08] **Tim:** Okay, never mind.

[00:00:10] **Tim:** I think we, I think, I think we already do.

[00:00:11] **Adam:** I'll think about that.

[00:00:12] **Tim:** Yeah, think about that.

[00:00:12] **Carol:** Ring, ring, ring.

[00:00:13] **Tim:** Uh, yeah, it might be a good idea.

[00:00:14] **Ben:** It.

[00:00:34] **Adam:** Okay, here we go.

[00:00:35] **Adam:** It is show number 268.

[00:00:36] **Adam:** And on today's show we're going to talk about language-based communities which you know, I think that's enough said about that.

[00:00:42] **Adam:** We'll come back to that.

[00:00:42] **Adam:** We'll talk about what that means in a little bit.

## [00:00:44] Adam's Triumph

[00:00:44] **Adam:** But first, as usual, let's start with the triumphs and fails Looks like it's my turn to go first, so I'm going to kick us off with a triumph, which is kind of a three part thing.

[00:00:47] **Tim:** Mhm,

[00:00:48] **Carol:** Mhm.

[00:00:52] **Adam:** One, I'm ahead on compliance stuff which is tough this time of year.

[00:00:55] **Adam:** I'm ahead on like policy revisions and renewals and

[00:00:59] **Ben:** Nice.

[00:00:59] **Ben:** Tis the season.

[00:01:00] **Adam:** tis the season as they say.

[00:01:02] **Adam:** and I'm feeling good.

[00:01:03] **Adam:** You know, we got our GRC tool, um, that kind of helps me stay on top of this stuff and it's working really well and I'm ahead and I'm happy about that.

[00:01:06] **Ben:** Mhm.

[00:01:07] **Carol:** Mhm.

[00:01:12] **Adam:** And I'm still really happy with our firm that we contract out the

[00:01:15] **Tim:** Mhm.

[00:01:17] **Adam:** uh, approval process.

[00:01:18] **Adam:** It's like you hire an accountant basically to sign off on your compliance stuff.

[00:01:21] **Adam:** and they've been very helpful, so very happy with that.

[00:01:25] **Adam:** That's part one.

[00:01:25] **Adam:** Part two.

[00:01:25] **Carol:** Mhm.

[00:01:26] **Adam:** I've had several recent vacations with varying degrees of success as we were just discussing before we started recording.

[00:01:30] **Ben:** Mhm.

[00:01:32] **Adam:** but you uh, know, it's given me a chance to rest and relax a little bit, kind of slow down.

[00:01:36] **Adam:** Um, and then.

[00:01:37] **Tim:** the.

[00:01:37] **Tim:** Try out the new EV towing capacity.

[00:01:39] **Adam:** Yeah, yeah, it's been great.

[00:01:40] **Tim:** Yeah.

[00:01:41] **Adam:** Um, and then kind uh, of riding on a little bit of a high for today especially because uh, I had a really good meeting with a customer this afternoon.

[00:01:42] **Carol:** Mhm.

[00:01:48] **Adam:** We we've noticed that they've been doing some things a little bit different than prescribed or than, than we would prescribe.

[00:01:49] **Ben:** Mhm,

[00:01:49] **Carol:** Mhm.

[00:01:53] **Adam:** Um, and so and getting some better results from it.

[00:01:56] **Adam:** Right.

[00:01:56] **Adam:** So they, they use our mail sending tool and they use

[00:02:00] **Adam:** than everybody else at least.

[00:02:02] **Adam:** And so had.

[00:02:04] **Ben:** Mhm,

[00:02:04] **Adam:** And their unsubscribe and bounce rates are low because of the way that they send it, we're pretty sure.

[00:02:04] **Tim:** Mhm.

[00:02:05] **Carol:** Mhm.

[00:02:10] **Adam:** So to them about you know, how they think about this problem and um, if we were to build some tooling to make doing, you know, make working that way easier,

[00:02:10] **Tim:** Sa.

[00:02:21] **Adam:** what would seem intuitive?

[00:02:22] **Adam:** How would they think about it, that sort of thing.

[00:02:23] **Ben:** Mhm.

[00:02:24] **Adam:** and I started working on some sort of UI mockups this afternoon to show off to them.

[00:02:24] **Carol:** Mhm.

[00:02:29] **Adam:** And it's just a, it feels good to come up with something sort of like somewhat innovative and customer facing and it's, you know, it's exciting new feature development.

[00:02:39] **Adam:** So I'm just riding a little high from that.

[00:02:41] **Tim:** You know, it's pretty amazing.

[00:02:42] **Tim:** Most customers tend to be pretty dumb with the system, but you have these few that, that can figure out these workarounds and alternate ways of getting things done that you're like, I never in a million years would have thought of that.

[00:02:46] **Adam:** Mm.

[00:02:46] **Adam:** Mhm,

[00:02:46] **Carol:** Mhm.

[00:02:54] **Adam:** M.

[00:02:55] **Tim:** And they did it within.

[00:02:55] **Ben:** Yeah.

[00:02:55] **Carol:** Yeah,

[00:02:55] **Adam:** Yeah.

[00:02:56] **Tim:** And they do it within a framework that you created yourself.

[00:02:58] **Tim:** And you're like, I never would have thought of that.

[00:02:59] **Carol:** yeah.

[00:03:00] **Adam:** Yep.

[00:03:01] **Carol:** Or the ones who learn to pit until like hit F12 and they're like, oh, I looked at this link and I saw this ID.

[00:03:08] **Carol:** Is that helpful?

[00:03:09] **Carol:** I'm like, get out of our IDs.

[00:03:11] **Carol:** You're not supposed to know those.

[00:03:13] **Tim:** Hacker.

[00:03:13] **Adam:** Oh man.

[00:03:14] **Adam:** I.

[00:03:15] **Adam:** So we have, you know, we, we have our built-in ticketing system in our product and one of the things that I have in there is that like if you.

[00:03:22] **Adam:** So the create a support ticket thing is it's a modal that you can open from any page within admin and whatever page that you're on when you create the ticket, we include the URL of that as like a.

[00:03:25] **Tim:** Sa mhm,

[00:03:36] **Adam:** It's like it's visible to everybody who views the ticket.

[00:03:37] **Carol:** It's helpful.

[00:03:38] **Adam:** It's right there.

[00:03:38] **Carol:** Yeah.

[00:03:38] **Adam:** It's helpful.

[00:03:38] **Ben:** Mhm.

[00:03:39] **Adam:** Like, where were you when you created this ticket?

[00:03:41] **Carol:** Yep.

[00:03:41] **Adam:** And there are so many times that I have to be like, well, okay, I don't know what you're talking about.

[00:03:45] **Adam:** Because not only did they not like provide a link or even mention the specific event they're talking about, they weren't on the page, they, they just like I need help with the thing and it's like not helpful.

[00:03:56] **Tim:** Mm mhm.

[00:03:56] **Ben:** Like it's not working.

[00:03:57] **Tim:** It's not working.

[00:03:58] **Adam:** Yeah.

[00:03:58] **Carol:** Yeah.

[00:03:58] **Tim:** Yeah,

[00:03:59] **Ben:** Your site's broken.

[00:03:59] **Adam:** Um,

[00:04:01] **Adam:** and it's like all you had to do was be on the page with that event or whatever or, or provide the link or give me the ID or.

[00:04:02] **Tim:** thanks.

[00:04:09] **Tim:** Even a screenshot.

[00:04:11] **Adam:** Yeah.

[00:04:11] **Carol:** M

[00:04:11] **Adam:** Least helpful of all, it was like giving me the name because then I have to go take the name and like search for it.

[00:04:13] **Carol:** sam.

[00:04:15] **Adam:** But at least that's possible.

[00:04:18] **Adam:** So.

[00:04:19] **Adam:** Varying, uh, degrees of competence.

[00:04:21] **Adam:** You know, you'd think people that work with the Internet marketing stuff tools would be helpful, would.

[00:04:22] **Ben:** Mhm.

[00:04:24] **Tim:** Mhm.

[00:04:25] **Carol:** Mhm.

[00:04:27] **Adam:** Would be savvy enough to be helpful with the ticket, but

[00:04:32] **Adam:** you'd be surprised.

[00:04:33] **Ben:** It's also tough, uh, until you've worked on the other end of a ticketing system.

[00:04:39] **Ben:** It's like, I think, okay, I can only speak for myself, but I know that when I was younger and I was using other products and the products didn't work, I felt like I was owed something.

[00:04:44] **Tim:** Mhm.

[00:04:50] **Ben:** And so I think when I filed a ticket it was not like angry, but I definitely have a distinct memory of filing a ticket and then someone replying to the ticket and being like, did you try it in Firefox or something?

[00:04:50] **Carol:** Mhm.

[00:04:50] **Adam:** Mhm.

[00:05:04] **Ben:** And I just wanted to be like, yeah.

[00:05:04] **Carol:** Did you clear cache M yeah.

[00:05:05] **Tim:** Mhm.

[00:05:06] **Ben:** And I just wanted to be like, bro, not my problem.

[00:05:09] **Ben:** Like, I, like, I didn't say that.

[00:05:11] **Ben:** I think I probably just never responded.

[00:05:13] **Ben:** But definitely I was like, don't make me test your stuff.

[00:05:17] **Ben:** And like I was, you know, I was young, I was stupid.

[00:05:17] **Adam:** Right.

[00:05:20] **Ben:** uh, so I, know.

[00:05:21] **Adam:** It goes both ways.

[00:05:21] **Ben:** It's made, it's made me much more compassionate now as someone who files tickets, I try to like, uh, like I'll upload screenshots and like the screenshots always include the URL bar.

[00:05:23] **Tim:** Mhm.

[00:05:23] **Adam:** Yeah.

[00:05:31] **Ben:** And like, sometimes I'll even show like, here's the console inspector.

[00:05:32] **Carol:** Yep.

[00:05:35] **Ben:** And like, here's what the element looks like.

[00:05:37] **Ben:** And like, here was the network activity.

[00:05:40] **Ben:** I'm like, here's everything I can possibly give you.

[00:05:43] **Ben:** And then, but then the most frustrating thing is, is then they like someone to reply back with something where like, they clearly did not even read anything that you wrote in the support ticket.

[00:05:44] **Tim:** Mhm.

[00:05:51] **Ben:** And they're like, have you tried restarting your computer?

[00:05:53] **Ben:** You're like, bro,

[00:05:54] **Adam:** Yeah.

[00:05:55] **Adam:** I spent most of the time that you were talking there trying to think of the word to describe the attitude you were saying you used to have.

[00:06:01] **Adam:** And it took me until just uh, a few seconds ago, but I figured it out.

[00:06:04] **Adam:** It was entitled.

[00:06:04] **Tim:** Mhm.

[00:06:05] **Ben:** Yes, entitled.

[00:06:05] **Ben:** When you're younger, you just feel entitled to stuff,

[00:06:06] **Carol:** Mhm.

[00:06:08] **Adam:** Yeah.

[00:06:08] **Adam:** It's like I pay for this product or my company pays for this product.

[00:06:11] **Ben:** right?

[00:06:11] **Adam:** It should just work.

[00:06:14] **Ben:** Good times.

[00:06:14] **Adam:** So well.

[00:06:15] **Adam:** Well, that's it for me.

[00:06:16] **Adam:** So how about you, Ben?

[00:06:16] **Adam:** What do you got going on?

## [00:06:17] Ben's Triumph

[00:06:17] **Ben:** I'm going to go with the quick triumph and a, uh, little bit of a longer failure.

[00:06:21] **Ben:** Triumph.

[00:06:22] **Ben:** Um, maybe this is a failure.

[00:06:24] **Ben:** We got a dog.

[00:06:25] **Carol:** Mhm.

[00:06:26] **Adam:** Yay.

[00:06:26] **Ben:** And uh, that's very exciting.

[00:06:27] **Adam:** A little Ewok.

[00:06:28] **Ben:** So we're a year out from our, uh, little sweet Lucy's passing.

[00:06:32] **Carol:** Sa.

[00:06:32] **Ben:** we were just missing having a little pitter patter in our, in our house.

[00:06:36] **Ben:** So we have a dog.

[00:06:37] **Tim:** Mhm.

[00:06:39] **Ben:** A week and a half now we've had a dog and it's exhausting.

[00:06:41] **Adam:** Mhm.

[00:06:43] **Ben:** And I'm afraid to get up in the middle of the night to pee because I feel like she'll wake up and have to go out.

[00:06:47] **Tim:** M really, really, really selling that dog.

[00:06:47] **Ben:** I've been eating terribly, I haven't worked out.

[00:06:50] **Ben:** Uh, so I just feel like generally awful.

[00:06:52] **Adam:** You're.

[00:06:53] **Ben:** But.

[00:06:53] **Adam:** It's like you're a new parent.

[00:06:54] **Ben:** Yeah, but um, but she's.

[00:06:58] **Ben:** But it.

[00:06:59] **Ben:** But then there'll be like 10 minutes where she'll just fall asleep on my chest and it's like the best 10 minutes of my week.

[00:07:03] **Tim:** Mhm.

[00:07:06] **Ben:** And uh, I don't know, it's kind of, Her name is technically Moira Rose.

[00:07:07] **Tim:** What's her name?

[00:07:08] **Tim:** What'd you name her?

[00:07:11] **Ben:** It's a character from Schitt's Creek.

[00:07:13] **Tim:** Huh?

[00:07:14] **Ben:** but I call her Rosie because Moira does not roll off the tongue.

[00:07:15] **Tim:** Rosie.

[00:07:16] **Adam:** Mhm,

[00:07:17] **Tim:** No.

[00:07:17] **Tim:** Rosie.

[00:07:18] **Tim:** Alec.

[00:07:18] **Ben:** So she's Rosie.

[00:07:20] **Ben:** So that's a triumph.

[00:07:20] **Tim:** She is cute.

## [00:07:21] Ben's Fail

[00:07:21] **Ben:** Failure is I feel like I cannot get out of my own way when it comes to agentic programming.

[00:07:25] **Carol:** Mhm.

[00:07:29] **Ben:** So I keep, you know, I use agents.

[00:07:30] **Adam:** Mhm,

[00:07:31] **Ben:** I use agents all day.

[00:07:34] **Ben:** I have feelings about it.

[00:07:35] **Ben:** And I keep hearing interview after interview after interview about people talking about all the code that they're just letting rip and they're not even thinking about it.

[00:07:41] **Carol:** Mhm.

[00:07:45] **Ben:** And like, oh, we're just like recreating Salesforce and we're recreating this SaaS and that SaaS right?

[00:07:50] **Ben:** And I'm like, what is wrong with me?

[00:07:51] **Adam:** Mhm,

[00:07:52] **Ben:** So I tried to, When I think about my website, my personal website, the one missing support beam to my entire infrastructure is syntax highlighting.

[00:07:57] **Tim:** Mhm.

[00:07:58] **Carol:** Mhm.

[00:08:03] **Ben:** It's the one thing that I really lean on GitHub for.

[00:08:06] **Ben:** I actually use the Gist API to essentially every time I, I author a post, I actually take all the uh, fenced code blocks in my Markdown and I post them to the GitHub Gist API and then I read the Gist back and I parse the Gist and I pull out all the syntax-highlighted HTML and it's super complicated and it's error prone because sometimes the Gist API is not available and it only does it for the post.

[00:08:07] **Adam:** Mhm,

[00:08:08] **Tim:** Sa.

[00:08:18] **Tim:** Mhm.

[00:08:19] **Carol:** Mhm.

[00:08:28] **Adam:** Mhm,

[00:08:33] **Ben:** Like it doesn't do it for anybody's comments.

[00:08:35] **Ben:** So I have long wanted to be able to build my own syntax highlighter.

[00:08:39] **Tim:** Mhm.

[00:08:39] **Ben:** So I'm like, oh, okay, this is a perfect thing for agents.

[00:08:40] **Carol:** Mhm.

[00:08:41] **Ben:** I'm just gonna like let them rip.

[00:08:43] **Ben:** And like, I couldn't even do that because I, I start with like, oh, I want to build a syntax highlighter.

[00:08:48] **Ben:** It needs to be at least comparable to what GitHub does.

[00:08:49] **Adam:** Mhm,

[00:08:51] **Ben:** GitHub has a Markdown API which I've considered using, but it has a funky, uh, rate limit because it's content generation.

[00:08:58] **Ben:** So it's lower than the actual rate limit of the API, which is like fine for published posts.

[00:09:01] **Tim:** Mm mhm.

[00:09:03] **Ben:** But then like, what if I Want to backfill all of the posts previous.

[00:09:07] **Ben:** There's issues.

[00:09:09] **Ben:** So I started going down this route and I'm, you know, interviewing Claude, Claude's interviewing me about what we want done.

[00:09:09] **Adam:** Mhm,

[00:09:15] **Ben:** And we start talking about where it should be and like what limitations, like should it run as a Lambda function or like a Netlify function or should it be on DigitalOcean or should it be a container?

[00:09:15] **Carol:** Mhm

[00:09:19] **Tim:** Mhm.

[00:09:20] **Carol:** mhm.

[00:09:23] **Tim:** Sa.

[00:09:24] **Ben:** And then we're talking about pricing.

[00:09:26] **Ben:** And then because syntax highlighting is all based on regular expressions, you can have catastrophic backtracking, which means that if you're on something like the Node event loop uh, you could theoretically have an event loop that gets tied up by catastrophic backtracking and etc.

[00:09:30] **Adam:** Mhm.

[00:09:39] **Ben:** Etc.

[00:09:40] **Ben:** So anyway, I put like three mornings of work into trying to get uh, something done.

[00:09:41] **Carol:** Mhm.

[00:09:46] **Ben:** And like all I've gotten now is like several design documents and it's like I don't know how anyone does it.

[00:09:50] **Adam:** Mhm.

[00:09:53] **Ben:** Like, how do you not think about this stuff?

[00:09:56] **Ben:** And it's so frustrating.

[00:09:58] **Ben:** I feel like I'm my own worst enemy when it comes to just getting code done.

[00:10:01] **Carol:** Mhm.

[00:10:03] **Ben:** But I, I don't know how to stop

[00:10:06] **Ben:** worrying about the little details.

[00:10:10] **Ben:** And so.

[00:10:10] **Tim:** What's funny to me, you actually didn't.

[00:10:12] **Tim:** I don't think you really describe an agentic coding failure That's just vibe coding.

[00:10:17] **Ben:** Well, I would.

[00:10:17] **Ben:** No, no, because I wanted to use the agent to build all the stuff

[00:10:18] **Tim:** Sounds like.

[00:10:20] **Tim:** Okay.

[00:10:21] **Tim:** Uh, okay.

[00:10:22] **Tim:** All right.

[00:10:22] **Ben:** because this is what people, you know, like, oh, I got my agents working while I'm sleeping and building my software and like I'm, you know, 10xing the output of my code and you know, all this jazz.

[00:10:22] **Carol:** Mhm.

[00:10:29] **Adam:** You're comparing yourself to the wrong people.

[00:10:32] **Ben:** I'm just,

[00:10:34] **Ben:** it's like I want that magic and, uh, what I'm realizing is like, I,

[00:10:39] **Ben:** I don't know how you get a clear enough picture in your head to just let an agent rip on stuff.

[00:10:41] **Adam:** Mhm,

[00:10:41] **Tim:** Mhm.

[00:10:43] **Carol:** Mhm.

[00:10:48] **Ben:** I find that I'm constantly discovering as I'm going and you know, maybe that's just the muscle memory of this is how I've always built software, which is the kind of like exploratory, iterative approach and I really just have to sit down, you know, like I hear some people talk about they'll spend like four hours creating a design document, you know, for like spec-driven development kinds of stuff.

[00:10:52] **Adam:** Mhm.

[00:11:02] **Tim:** Mhm.

[00:11:09] **Ben:** I don't know, I'm just, I keep wanting to drink the Kool-Aid and then just feeling like I focus too much on the shape of the glass and what uh, color the Kool-Aid is

[00:11:21] **Ben:** and what temperature it is, but it's so hard.

[00:11:22] **Adam:** I agree.

[00:11:22] **Carol:** Mhm.

[00:11:24] **Adam:** So, all right.

[00:11:25] **Adam:** I, I want to, I want to uh, not that, not to make this all about training Ben on how to use agentic coding,

[00:11:31] **Carol:** I have thoughts too.

[00:11:31] **Adam:** but

[00:11:32] **Carol:** So you're good.

[00:11:33] **Ben:** Yeah.

[00:11:33] **Carol:** Let's just do it it.

[00:11:33] **Ben:** Yeah.

[00:11:33] **Adam:** it like.

[00:11:34] **Adam:** Okay, I, I mentioned in my triumph about uh, UI that I built, right.

[00:11:39] **Tim:** Mhm.

[00:11:40] **Carol:** Mhm.

[00:11:41] **Adam:** they're kind of prototyping and like I got 95% of the way there with one prompt.

[00:11:42] **Ben:** Mhm.

[00:11:48] **Adam:** So I did.

[00:11:49] **Adam:** And it's like three and a half paragraphs.

[00:11:51] **Adam:** Let me read it to you real quick.

[00:11:52] **Ben:** Sure, go for it.

[00:11:53] **Adam:** I know like reading these things since I, I promise you it's not that long.

[00:11:57] **Adam:** So the first thing I did was tag the specific file.

[00:11:59] **Adam:** I like the view file.

[00:11:59] **Tim:** Mhm.

[00:12:00] **Adam:** I wanted it to edit.

[00:12:01] **Carol:** Mhm.

[00:12:02] **Adam:** I said I want to add an experimental feature for increased mail deliver.

[00:12:02] **Ben:** Mhm.

[00:12:05] **Adam:** Mail deliverability via spaced-out sending Use a feature flag.

[00:12:10] **Adam:** Uh, and I like gave it the specific feature flag name.

[00:12:12] **Adam:** I wanted it to use in like backticks to enable some new UI.

[00:12:16] **Adam:** Between the schedule quoted, uh, date and time fields and the conflicts again quoted section of this page when the flag is enabled, new controls appear

[00:12:19] **Tim:** Mhm.

[00:12:27] **Adam:** to select tranche sized tranches.

[00:12:30] **Adam:** T R A N C E is like groupings for people.

[00:12:32] **Ben:** Mhm.

[00:12:32] **Adam:** I don't know.

[00:12:33] **Ben:** For their spaced out.

[00:12:33] **Adam:** It's a minimum.

[00:12:34] **Adam:** Yeah, yeah.

[00:12:35] **Adam:** Minimum 4,000, maximum 10,000 and time gap between tranches minimum five minutes maximum 20 minutes.

[00:12:35] **Carol:** Mhm.

[00:12:40] **Tim:** Mhm.

[00:12:41] **Carol:** Mhm.

[00:12:42] **Adam:** I'm thinking horizontal slider controls with hard tick stops at 1000x intervals for tranche size and 1 minute intervals for gap.

[00:12:43] **Ben:** Sa.

[00:12:52] **Adam:** The UI should update to recalculate number of tranches, total time to send and estimated time of last send based on total list size and selected tranche size and gap values.

[00:13:02] **Carol:** Mhm.

[00:13:04] **Adam:** Use an easily updated single location variable for send throughput.

[00:13:08] **Adam:** Hard code it to 4,500 emails sent per minute for now so we can adjust it later if needed.

[00:13:11] **Tim:** Mhm.

[00:13:13] **Adam:** That's just because that's our current throughput for now just add the flag in flags.json and the UI and we'll worry about adding database columns and sort storing the selections in the database later.

[00:13:15] **Ben:** Mhm.

[00:13:22] **Tim:** Hmm.

[00:13:26] **Adam:** Kind of just emphasizing that we're doing prototyping as well as applying the selections to the data for the flag.

[00:13:32] **Adam:** Set it to on if env equals dev.

[00:13:36] **Adam:** Any questions before you get started.

[00:13:36] **Carol:** Mhm.

[00:13:37] **Adam:** And it did ask me like one tiny.

[00:13:39] **Adam:** That was the end of the prompt.

[00:13:40] **Ben:** M.

[00:13:40] **Ben:** Mhm.

[00:13:41] **Adam:** It did ask one tiny follow-up question about what I mean by estimated time of last send and then it, it pretty much nailed it from there.

[00:13:47] **Adam:** Like, I did a little bit of tweaking on labels and stuff after that, but I think really the way I think about it is like what's the laziest thing I can say that communicates what I want to the agent, right?

[00:13:59] **Adam:** Like I, I need to identify.

[00:14:00] **Tim:** I don't know.

[00:14:00] **Tim:** That sounded pretty well thought out to me.

[00:14:02] **Carol:** No, there's a big words in there.

[00:14:02] **Ben:** Yeah, that did.

[00:14:02] **Ben:** I could picture it in my head.

[00:14:04] **Ben:** Mhm.

[00:14:05] **Carol:** Mm mhm.

[00:14:05] **Adam:** Well, but that's the thing is like, I, I try to be minimal and terse but thorough if that makes sense.

[00:14:13] **Tim:** Yeah.

[00:14:14] **Adam:** You know, tag specific files, give it names for things that are gonna, I care about the names and then just kind of lay out how I would describe this to a junior developer or, or somebody who, you know, knows a little bit about this app and, and knows plenty about coding and just like go.

[00:14:21] **Tim:** Hm.

[00:14:22] **Ben:** Sa.

[00:14:22] **Tim:** Mhm.

[00:14:23] **Carol:** Mhm.

[00:14:24] **Ben:** Mhm.

[00:14:30] **Adam:** And that's a.

[00:14:31] **Adam:** Maybe that's what it is.

[00:14:33] **Adam:** I think you probably think about writing code using agents in a way where you want the output to be correct the first time.

[00:14:44] **Adam:** Just get something to come out and then the more you do that, the more you'll learn how to guide it to what you want on the first try.

[00:14:46] **Tim:** Mhm.

[00:14:46] **Carol:** Yeah, iterate it.

[00:14:47] **Carol:** Right, iterate.

[00:14:48] **Ben:** Well,

[00:14:50] **Ben:** all right, before I respond, I want to hear because I know Carol had some stuff.

[00:14:54] **Carol:** Yeah.

[00:14:55] **Carol:** The one big difference between what you and Adam just said is Adam's taking an existing file, an existing project, and he's iterating over something that's already there.

[00:15:02] **Carol:** It sounded like what you were doing is something brand new, something you wanted a new creation for.

[00:15:04] **Tim:** Mhm.

[00:15:07] **Adam:** Mhm,

[00:15:08] **Carol:** And it wasn't so much that maybe you got caught in the agent side of it.

[00:15:12] **Carol:** You got caught in implementation, you got caught in the details of where do I host this, who pays for it, how much is it going to cost?

[00:15:19] **Carol:** Instead of just letting it write you something and then figure out if it's viable or not.

[00:15:24] **Ben:** I think.

[00:15:24] **Carol:** M.

[00:15:24] **Ben:** Mhm.

[00:15:25] **Ben:** I sometimes get so distracted by little things that Claude says that then I start having kind of a side quest conversation about some detail of the plan that I almost forget the ingress to the plan itself.

[00:15:26] **Adam:** Mhm,

[00:15:40] **Tim:** Mhm

[00:15:41] **Ben:** So like one thing I wanted to make sure, because we've had all these supply chain attacks recently, the, the community.

[00:15:41] **Carol:** Been there.

[00:15:44] **Tim:** mhm.

[00:15:45] **Carol:** Mhm.

[00:15:47] **Adam:** Mhm.

[00:15:48] **Ben:** Right, the tech community.

[00:15:49] **Ben:** I said, okay, I know that this probably has to be Node based I absolutely never want to run npm install on my host machine So everything that I do locally has to be done inside of a container.

[00:16:02] **Ben:** So then Claude like cements this model in its head, you know, anthropo.

[00:16:07] **Ben:** Anthropomorph.

[00:16:10] **Ben:** No, no, anthropomorph.

[00:16:10] **Adam:** Anthropomorphize.

[00:16:11] **Ben:** Yes, anthropomorphized.

[00:16:12] **Tim:** Mhm.

[00:16:12] **Carol:** Mhm.

[00:16:14] **Ben:** Uh, that like the only option we have here is containers.

[00:16:17] **Ben:** So it starts to talk about how we can deploy it and you're like, well you can only deploy it on something like DigitalOcean or, or EC2.

[00:16:23] **Ben:** Uh, two.

[00:16:24] **Ben:** And I'm like, well it doesn't have to be a container in production.

[00:16:28] **Ben:** Like what if it's just a Node file in production Like that's totally fine.

[00:16:31] **Ben:** I just never want to run npm install locally So like it, we like we end up going down this.

[00:16:37] **Ben:** And I'm like, wait, where were we?

[00:16:39] **Ben:** What did we even come to a decision about how we want to build this thing in the first place?

[00:16:39] **Carol:** Mhm.

[00:16:42] **Ben:** It's like I, I keep getting down all these little distracting rabbit holes.

[00:16:48] **Carol:** Yeah.

[00:16:48] **Tim:** Yeah.

[00:16:48] **Carol:** I like to create action items and to dos.

[00:16:51] **Carol:** And I go, hey, that's a great idea, but this is a to do for after we solve what we're just talking about, let's resurface this.

[00:16:55] **Tim:** Mhm.

[00:16:57] **Carol:** That way I can stay on track.

[00:16:57] **Ben:** Yo,

[00:16:59] **Ben:** 100%.

[00:17:00] **Ben:** And okay, if I can do like one side quest here.

[00:17:03] **Ben:** I can't tell you how many times I've heard people talk about like the ticketing systems are dead.

[00:17:08] **Ben:** Like, oh, we never, we don't need Jira anymore Because you just asked the agent like, why even bother creating a ticket?

[00:17:08] **Carol:** M.

[00:17:13] **Ben:** And I'm like, I can barely remember what I did 20 minutes ago.

[00:17:17] **Carol:** Right.

[00:17:17] **Adam:** Yes.

[00:17:17] **Ben:** Uh, I'm like, I, I'm constantly telling Claude, you know, just create a ticket for this, we'll come back to it.

[00:17:23] **Tim:** Yeah.

[00:17:23] **Ben:** I don't understand the workflow that people have in their world where ticketing is no longer a valuable thing.

[00:17:30] **Tim:** People who hate tickets.

[00:17:33] **Ben:** They're just waiting.

[00:17:34] **Carol:** Sam?

[00:17:34] **Ben:** Waiting for a reason.

[00:17:35] **Tim:** Yeah.

[00:17:37] **Tim:** Yeah.

[00:17:37] **Adam:** Mhm.

[00:17:37] **Tim:** I'm with you on the rabbit hole.

[00:17:39] **Tim:** You know, Claude sometimes gives so much information.

[00:17:41] **Tim:** I'm like, I say do this thing and it comes back with 15 things.

[00:17:45] **Tim:** I'm like, say less.

[00:17:47] **Tim:** I mean,

[00:17:51] **Tim:** you brought up like three things that I wasn't even thinking about.

[00:17:54] **Tim:** Now I'm.

[00:17:54] **Tim:** Now I'm work, you know, I now go down those rabbit holes and I'm like, what was I working on?

[00:17:58] **Tim:** Yeah.

[00:17:58] **Ben:** Oh.

[00:17:59] **Tim:** So I get, I get that it's focusing.

[00:17:59] **Carol:** Mhm.

[00:18:01] **Tim:** The AI is, it's a skill.

[00:18:04] **Tim:** I guess maybe that means we'll still have jobs.

[00:18:06] **Adam:** That's one of the things that I've been liking about the Codex desktop app is you can fork conversations.

[00:18:13] **Carol:** Mhm.

[00:18:13] **Adam:** So you get a response and it makes you go, oh, uh, there's, there's an extra conversation I want to have about this.

[00:18:14] **Ben:** Oh, that's cool.

[00:18:18] **Adam:** And forking kind of has two benefits right now you have two threads that both have that same history thus far, and you can have different conversations like, okay, over here we're gonna talk about the containerization thing and over here we're gonna continue talking about the app or whatever.

[00:18:23] **Ben:** Hmm.

[00:18:23] **Ben:** Mhm.

[00:18:26] **Tim:** Sa.

[00:18:30] **Adam:** And they can still both work in the same folder.

[00:18:30] **Tim:** Mhm.

[00:18:32] **Adam:** Just try not to have them both coding in the same folder at the same time.

[00:18:35] **Ben:** Yeah, that's really cool actually.

[00:18:36] **Adam:** Um, but, uh, and I don't know, like you guys, uh, you guys I think are still using Claude.

[00:18:42] **Ben:** Yeah.

[00:18:42] **Adam:** We, I've, I've moved away from Claude and if you're using Claude, I know they have a,

[00:18:43] **Ben:** Yeah,

[00:18:47] **Adam:** I know they have a desktop app as well, but I don't know if it supports the forking.

[00:18:52] **Adam:** Last time I used the CLI, I don't think it had a forking feature.

[00:18:55] **Adam:** So just food for thought.

[00:18:55] **Ben:** I uh, I'll sometimes just open another tab in the terminal and start a brand new conversation, but I don't have the history.

[00:18:59] **Adam:** Mhm,

[00:19:01] **Ben:** I really like the idea that you can keep the shared history.

[00:19:05] **Ben:** That's very cool.

[00:19:05] **Adam:** Mhm.

[00:19:06] **Tim:** Yeah.

[00:19:06] **Carol:** Yeah.

[00:19:06] **Carol:** I tell Odd Odd, listen to me.

[00:19:08] **Carol:** I've got the auto thing in my head.

[00:19:10] **Tim:** Sorry.

[00:19:10] **Carol:** I tell Claude to spin off several agents and what it will do is it'll go, hey, okay, I see that we are trying to write the same file.

[00:19:16] **Ben:** Mhm.

[00:19:18] **Carol:** So I'm going to make all the in memory and at the end of it we'll compile it together and write to the file at the same time.

[00:19:25] **Carol:** That way everything can be happening on like individual tasks, but it doesn't update the code actually until the end because of conflicts.

[00:19:34] **Adam:** Yeah.

[00:19:34] **Adam:** Worktrees are great until they're not.

[00:19:37] **Carol:** I hate worktrees.

[00:19:37] **Adam:** You know, I realize we're we're like 20 minutes into this and we still haven't finished Ben's, uh,

[00:19:40] **Carol:** I know.

[00:19:41] **Tim:** I know, right?

[00:19:41] **Ben:** All right, all right, I'll.

[00:19:42] **Carol:** Sorry, sorry, sorry.

[00:19:42] **Ben:** Should I just call it there?

[00:19:43] **Ben:** That's my failure.

[00:19:44] **Carol:** Fine.

[00:19:44] **Ben:** I can't, I can't.

[00:19:44] **Adam:** ha.

[00:19:45] **Ben:** I can't stop being my own worst enemy.

[00:19:48] **Ben:** But I'm trying.

[00:19:49] **Ben:** Baby steps.

[00:19:50] **Ben:** All right, Carol, what do you got going on?

## [00:19:52] Carol's Triumph

[00:19:52] **Carol:** All right, so I'm going to go with a big win, you guys.

[00:19:54] **Carol:** Big triumph.

[00:19:54] **Ben:** Tight.

[00:19:54] **Carol:** I'm going to let you guys know that hard work pays off with more hard work, but it pays off, right?

[00:20:02] **Carol:** So.

[00:20:02] **Tim:** You mean you just earn more hard work?

[00:20:04] **Tim:** Uh, when you're done with all the hard work?

[00:20:05] **Tim:** Yeah.

[00:20:05] **Carol:** Yeah, yeah.

[00:20:06] **Carol:** So you guys know I was named the, uh, a, like the Chief AI Ambassador for OPM.

[00:20:10] **Carol:** So for our agency, kind of helping implement AI across the board, trying to get people up to speed, trying to just, you know, help this group of ambassadors who've been set forth to like, share the knowledge and teach others.

[00:20:11] **Adam:** Mm, mhm.

[00:20:12] **Ben:** Okay.

[00:20:16] **Tim:** Mhm.

[00:20:19] **Ben:** Mhm.

[00:20:21] **Adam:** Mhm,

[00:20:24] **Carol:** Well, everything's been going great with that.

[00:20:26] **Carol:** So good that now we've opened up what we're calling as our, AI Forge which I'm helping lead with a bunch of guilds under it that are now open to the entire agency.

[00:20:37] **Carol:** And this is great.

[00:20:38] **Carol:** But also on top of that, I'm also now in charge of getting one of the offices up to speed on AI adoption that are like the lowest AI adopters.

[00:20:49] **Carol:** So I'm talking about the finance office.

[00:20:50] **Ben:** Mhm.

[00:20:52] **Tim:** Of course.

[00:20:52] **Ben:** Oh yes.

[00:20:53] **Adam:** Mhm,

[00:20:54] **Carol:** So it's going great.

[00:20:55] **Carol:** I'm telling you.

[00:20:56] **Tim:** Mhm.

[00:20:56] **Carol:** Like, at first I was hesitant.

[00:20:58] **Carol:** I was like, I don't know if I want to embed with this team.

[00:21:00] **Ben:** Mhm.

[00:21:00] **Carol:** Like, I'm a little scared to say yes to this, but when I said yes, every time I show them something that I have just taken a little bit of time to listen to their workflow, write a skill that just reads files for them and gives them an output, they are just big-eyed going this is amazing.

[00:21:03] **Adam:** Mhm.

[00:21:16] **Ben:** Sam.

[00:21:19] **Carol:** How can we do more, um, of this?

[00:21:21] **Carol:** And I realized that business users don't have the same idea of what they're able to automate versus what engineers do.

[00:21:21] **Ben:** Mhm,

[00:21:23] **Adam:** Mhm.

[00:21:28] **Carol:** Like, since day one of, um, becoming an engineer, I've always looked at problems and went, what can I never repeat again?

[00:21:29] **Tim:** Mhm.

[00:21:35] **Carol:** Even if it's going to take me an hour to create this macro in this Excel sheet so I never have to calculate it again.

[00:21:41] **Carol:** If I would have just selected all the cells and hit one thing, it would have been done.

[00:21:45] **Carol:** I never want to do it again.

[00:21:46] **Carol:** Right.

[00:21:46] **Ben:** Mhm,

[00:21:47] **Carol:** I make it repeatable, but that's been like, you know, 16 years in the work now.

[00:21:47] **Tim:** Right?

[00:21:52] **Carol:** So to see these business users just big-eyed and happy and excited, it's given me another level of excitement and another level of joy that makes me proud to, like, have done the hard work up front and to be given this additional hard work to do because at the end it pays off.

[00:21:59] **Tim:** Mhm.

[00:22:03] **Ben:** Mhm.

[00:22:04] **Adam:** Mhm.

[00:22:12] **Carol:** And as I'm having these conversations with these people, I think of like Ben.

[00:22:15] **Carol:** And Ben going, oh, I love like the customer engagement.

[00:22:18] **Carol:** And now I feel like my customer is just a different end user who I help inside my own agency.

[00:22:24] **Carol:** And it's just, it's very rewarding and I'm.

[00:22:25] **Ben:** Yeah, that's awesome.

[00:22:26] **Carol:** I'm happy.

[00:22:27] **Carol:** Yeah.

[00:22:27] **Tim:** That is cool.

[00:22:28] **Tim:** Congratulations, girl.

[00:22:29] **Carol:** Thank you.

[00:22:30] **Carol:** Yeah.

[00:22:31] **Carol:** But that's me.

[00:22:32] **Carol:** Tim.

## [00:22:34] Tim's Triumph

[00:22:34] **Tim:** We did it, guys.

[00:22:35] **Tim:** Four triumphs.

[00:22:37] **Ben:** What?

[00:22:37] **Adam:** Mhm.

[00:22:38] **Tim:** Four of a kind.

[00:22:38] **Carol:** What?

[00:22:42] **Tim:** so my triumph is that.

[00:22:44] **Tim:** So last week, uh, last Thursday, converted our final customer off of our payments platform onto a different platform.

[00:22:54] **Tim:** And so I'm very close.

[00:22:55] **Tim:** Very, very close.

[00:22:56] **Ben:** What?

[00:22:56] **Tim:** There's a few little cleanup things.

[00:22:57] **Tim:** Very close to having one job at my job and, and, and not have.

[00:23:00] **Adam:** Ooh, fancy.

[00:23:02] **Tim:** Not having two jobs being director of payCloud and director of Silvervine.

[00:23:04] **Carol:** Mhm.

[00:23:05] **Ben:** Mhm,

[00:23:07] **Tim:** So, um, just a few little things I got to clean up.

[00:23:09] **Tim:** I spent the whole day trying to.

[00:23:11] **Tim:** There's some databases that we're, you know, paying a lot of money for on AWS that can go away now.

[00:23:17] **Carol:** Sa.

[00:23:17] **Tim:** So just very thoughtfully because there's some things on it that still need to stay for other projects.

[00:23:22] **Tim:** So very thoughtfully cleaning all that up.

[00:23:25] **Tim:** And Claude's made it super easy.

[00:23:25] **Carol:** Mhm.

[00:23:27] **Tim:** I did it the dev today in about three hours got, uh, everything like 17 databases converted over to a new version of PostgreSQL, our Lord and Savior.

[00:23:37] **Ben:** Mhm.

[00:23:37] **Adam:** Mhm.

[00:23:38] **Tim:** And uh, yeah, so tomorrow I'll be doing the live one and then.

[00:23:41] **Tim:** Yeah, pretty much that.

[00:23:42] **Tim:** That wraps it up.

[00:23:43] **Tim:** I'll get my, completion bonus for completing all this stuff that's taken pretty much started back in June of last year.

[00:23:49] **Tim:** So it's been a full year of.

[00:23:50] **Carol:** Wow.

[00:23:50] **Adam:** Wow.

[00:23:53] **Tim:** Full year of, of activity.

[00:23:55] **Tim:** So

[00:23:55] **Carol:** You taking us all out for ice cream?

[00:23:57] **Tim:** You got it.

[00:23:59] **Tim:** You can even get a hot dog too.

[00:23:59] **Ben:** That's awesome.

[00:24:01] **Carol:** Heck yeah.

[00:24:02] **Tim:** Heck yeah.

[00:24:03] **Tim:** So that's me.

[00:24:04] **Tim:** That's my triumph.

[00:24:04] **Tim:** All four of us have triumphs.

[00:24:06] **Tim:** Good job, guys.

[00:24:07] **Tim:** What are we talking about?

[00:24:07] **Ben:** Yeah, there's no.

[00:24:08] **Adam:** Go team.

[00:24:09] **Carol:** So wait, wait, wait.

[00:24:10] **Carol:** I would.

[00:24:10] **Carol:** I want to ask one question.

[00:24:11] **Carol:** So you said something key there that I keep iterating on with my people and I keep kind of reinforcing.

[00:24:17] **Carol:** You said like you were able to meet this deadline that was set on your.

[00:24:21] **Carol:** And part of that sounds like it's because you were able to use AI to do that.

[00:24:26] **Tim:** No, I didn't meet the.

[00:24:26] **Carol:** Do you think if.

[00:24:27] **Tim:** I missed the deadline by six months.

[00:24:28] **Ben:** Mhm,

[00:24:29] **Carol:** Oh, but you're still getting a bonus for it.

[00:24:29] **Adam:** Mhm.

[00:24:31] **Tim:** I'm seeing a completion bonus.

[00:24:32] **Tim:** I missed on the performance bonus.

[00:24:34] **Tim:** Yeah, I missed about.

[00:24:35] **Carol:** Oh, well, dang, forget my questions.

[00:24:35] **Tim:** I missed.

[00:24:36] **Tim:** I missed out on about m.

[00:24:37] **Tim:** I missed out about $15,000.

[00:24:39] **Tim:** Yeah,

[00:24:40] **Carol:** well, do you think AI helps you get it done when you got it done?

[00:24:43] **Carol:** Like, do you think you would be sitting here saying, I could have gotten this accomplished in a year had you not had the AI tools available that have been added to the industry in the last few years?

[00:24:44] **Tim:** yeah.

[00:24:52] **Tim:** No, because none of the problems are programming related.

[00:24:53] **Tim:** They were all contractual and customer really are things that I argue are not my fault and out of my control.

[00:24:56] **Carol:** Okay,

[00:25:00] **Tim:** But the contract's the contract that, you know, like if you're.

[00:25:03] **Adam:** M.

[00:25:03] **Adam:** Somebody's gotta own it.

[00:25:04] **Tim:** If you're done by Jan.

[00:25:04] **Carol:** Things.

[00:25:04] **Carol:** Yeah,

[00:25:05] **Tim:** If you're done by Jan 1st, you get this much.

[00:25:06] **Tim:** If you're not, it's prorated.

[00:25:07] **Ben:** Mhm,

[00:25:08] **Tim:** So you got prorated.

[00:25:09] **Carol:** Interesting.

[00:25:09] **Tim:** So.

[00:25:11] **Carol:** Okay, now to the show.

[00:25:12] **Adam:** Well, yeah, yeah, yeah.

[00:25:13] **Carol:** Where were we?

[00:25:13] **Tim:** Mhm.

[00:25:13] **Adam:** So before we actually, you know, a little bit of business here.

[00:25:16] **Adam:** I just wanted to, I guess, apologize to the listeners since we were off last week, you know, as we mentioned, Ben got a dog.

[00:25:22] **Adam:** Uh, we didn't mention it, but Carol, you had some doggo troubles?

[00:25:22] **Ben:** Mhm.

[00:25:24] **Carol:** Yeah.

[00:25:25] **Adam:** Uh,

[00:25:25] **Carol:** Our poor baby had surgery and she didn't recover well and required 24 hour supervision.

[00:25:29] **Adam:** yeah,

[00:25:31] **Ben:** It's awful.

[00:25:31] **Adam:** yeah.

[00:25:31] **Adam:** I was helping some family deal with car trouble last week.

[00:25:33] **Adam:** It was just a really bad week for us for recording last week, so we took a week off.

[00:25:37] **Tim:** I was good.

[00:25:37] **Tim:** I was.

[00:25:37] **Tim:** I was good.

[00:25:38] **Tim:** But I didn't want to do the show by myself, so.

[00:25:40] **Tim:** Nobody to talk to.

[00:25:41] **Adam:** So selfish.

[00:25:42] **Ben:** Tim, Tim actually doesn't have a start record button on his version of Riverside.

[00:25:42] **Tim:** I know.

[00:25:45] **Tim:** I don't.

[00:25:46] **Tim:** I don't.

[00:25:48] **Tim:** They don't trust me.

[00:25:50] **Carol:** I mean, you could have just signed in and like read a book or some poems to everyone.

[00:25:54] **Tim:** Mhm.

[00:25:54] **Ben:** Yeah, like a dramatic reading.

[00:25:55] **Carol:** You have a nice.

[00:25:56] **Carol:** Yeah, you have a nice voice.

[00:25:58] **Tim:** I Know Why the Caged Bird Sings.

[00:26:02] **Carol:** Exactly.

[00:26:03] **Adam:** Got to do something in the public domain.

[00:26:05] **Tim:** Yeah.

## [00:26:05] The Paradox of Language-Based Communities

[00:26:05] **Adam:** All right, well then, let's move into, the paradox, as Ben put it, of language-based communities And this better not be another backdoor.

[00:26:10] **Carol:** Mhm.

[00:26:13] **Adam:** Um, the, the value of friction.

[00:26:13] **Ben:** Struggle.

[00:26:15] **Ben:** No,

[00:26:17] **Ben:** if anything this is the opposite.

[00:26:19] **Ben:** Um, so, okay.

[00:26:19] **Ben:** When I was early on in my career, I very much associated myself with the technology that I was using.

[00:26:28] **Ben:** I was a ColdFusion developer I was a jQuery developer, I was an Angular developer I found my,

[00:26:30] **Adam:** Mm mhm.

[00:26:35] **Tim:** Tell me you're old without saying you're old.

[00:26:37] **Carol:** I know.

[00:26:37] **Carol:** I just heard it.

[00:26:38] **Carol:** I heard it.

[00:26:40] **Adam:** Mhm.

[00:26:40] **Ben:** I felt like the communities that I could find were centered around a chosen technology.

[00:26:48] **Ben:** And then as my career progressed there was, I.

[00:26:52] **Carol:** Mhm,

[00:26:52] **Tim:** Mhm,

[00:26:53] **Ben:** I'm still very much think of myself as a technology person, but I think there's a striving to be technology agnostic, you know, stretching yourself a little bit to learn, like I learned React, even though I didn't really use React And I've dabbled a little bit in Svelte because Adam has talked about how great Svelte is I've looked into, you know, there's this uh, desire to just broaden your horizons and learn more.

[00:27:12] **Carol:** Mhm,

[00:27:13] **Tim:** Mhm,

[00:27:14] **Adam:** Mhm.

[00:27:18] **Ben:** And now in the age of AI, where we can prompt and Claude or whatever agents you use can just use the most appropriate technologies, it's much less technology centric today than it was 10, 15, 20 years ago.

[00:27:32] **Carol:** Mhm,

[00:27:39] **Ben:** The paradox of.

[00:27:40] **Adam:** I mean, more than it was three years ago.

[00:27:42] **Ben:** Yes.

[00:27:43] **Ben:** Yeah.

[00:27:43] **Ben:** Yeah.

[00:27:43] **Tim:** M.

[00:27:43] **Tim:** Yeah, for sure.

[00:27:43] **Ben:** It's, it's, it's, it's, it's rapidly changing.

[00:27:44] **Tim:** Mhm.

[00:27:47] **Ben:** It's, it's uh, supercharging.

[00:27:48] **Ben:** A change that sort of already felt like was becoming more of a thing.

[00:27:51] **Adam:** Yeah.

[00:27:52] **Ben:** You know, just like the technology world in general has expanded.

[00:27:56] **Ben:** It used to be, you know, oh, if you weren't on MS SQL, you were on MySQL or you know, maybe Ah, and now it's like, you could be,

[00:28:03] **Tim:** So maybe Postgres.

[00:28:06] **Ben:** you know, now it's like you could be on Mongo, or you could be using Redis, or you could be using CockroachDB, or you could be using Firebase, or you could be using Ah.

[00:28:13] **Carol:** Mhm,

[00:28:14] **Ben:** Or you could be using, you know, like any number of SQLite and all kinds of stuff.

[00:28:14] **Tim:** Mhm.

[00:28:19] **Tim:** Sa.

[00:28:19] **Ben:** The number of technologies that we can use to power the stuff that we work on has become so vast and so fragmented.

[00:28:27] **Ben:** It feels like there's not a community to be had that is technology based anymore.

[00:28:34] **Tim:** Mhm.

[00:28:34] **Adam:** Hmm.

[00:28:35] **Adam:** Mhm.

[00:28:35] **Ben:** But we're also in an age where I feel like loneliness is an epidemic and like to some, something like it's.

[00:28:41] **Adam:** Mhm.

[00:28:44] **Ben:** I feel like it's crazy.

[00:28:45] **Ben:** It's like 60% of men report having like no friends at all or like no friends that they consider close friends other than their spouse.

[00:28:52] **Ben:** You know, people are uh, going to church.

[00:28:53] **Carol:** Mhm.

[00:28:55] **Ben:** This is not judgmental.

[00:28:56] **Ben:** I'm not a religious person.

[00:28:57] **Ben:** But like church is falling out of favor for a lot of people.

[00:29:00] **Ben:** Bowling.

[00:29:00] **Tim:** Third.

[00:29:00] **Ben:** Bowling.

[00:29:00] **Tim:** Third spaces.

[00:29:02] **Adam:** Yeah.

[00:29:02] **Tim:** They're called third spaces.

[00:29:02] **Ben:** Mhm.

[00:29:04] **Tim:** So there's.

[00:29:04] **Ben:** Yeah.

[00:29:04] **Ben:** These like shared third spaces where you create these communities.

[00:29:06] **Tim:** Yeah.

[00:29:06] **Tim:** So you got your, you got your family life, you got your, work life, and then you've got a third.

[00:29:06] **Carol:** Mm.

[00:29:09] **Adam:** Work.

[00:29:11] **Tim:** Typically would have a third space.

[00:29:12] **Tim:** Like a, uh, community club, church, something.

[00:29:14] **Carol:** Mhm mhm.

[00:29:15] **Ben:** Yeah, yeah.

[00:29:16] **Tim:** Those are.

[00:29:16] **Adam:** Yep.

[00:29:16] **Tim:** Yeah.

[00:29:16] **Adam:** Uh,

[00:29:17] **Tim:** Uh, they're going away.

[00:29:18] **Ben:** And like uh, and it's.

[00:29:20] **Ben:** And so I was listening to a radio piece just recently about how there are actually reading clubs now in New York City where people literally get together in a cafe and they just read together.

[00:29:30] **Ben:** Like not even read out loud.

[00:29:32] **Ben:** They just get together as a group and they're like, we're just going to read the same book at the same time and it's going to be lovely.

[00:29:32] **Adam:** Right near each other.

[00:29:33] **Carol:** In the same room.

[00:29:34] **Carol:** Mhm,

[00:29:36] **Tim:** Mhm,

[00:29:37] **Carol:** mhm,

[00:29:37] **Adam:** Oh wow.

[00:29:38] **Adam:** I just assumed it was going to be bring what you want to read and it doesn't have to be the same thing

[00:29:42] **Ben:** Oh, uh, maybe.

[00:29:42] **Ben:** Maybe.

[00:29:43] **Ben:** Yeah, maybe I'm misremembering.

[00:29:44] **Adam:** because it wouldn't, it wouldn't have to be.

[00:29:44] **Ben:** But it's, but it is like it just like we just want to be with other people.

[00:29:48] **Ben:** And so I feel like there's this almost like weird paradox now where even though language choice or technology choice, it's not meaningful anymore from a, like a, like a career standpoint.

[00:29:56] **Carol:** Mhm,

[00:29:57] **Tim:** Mhm,

[00:30:03] **Ben:** It's almost like it's at least a place where you can put your uh, flag down and be like, let's, let's center around this fire and have a chat and talk.

[00:30:09] **Adam:** Yeah,

[00:30:12] **Adam:** yeah.

[00:30:13] **Adam:** I mean, I don't know about you guys, but

[00:30:15] **Adam:** I feel like I grew up in the golden age of user groups.

[00:30:17] **Carol:** Mhm,

[00:30:18] **Tim:** Mhm,

[00:30:19] **Adam:** Right.

[00:30:19] **Ben:** Yeah, 100%.

[00:30:20] **Adam:** Um, and like that was what really brought me from

[00:30:26] **Adam:** or, or sort of.

[00:30:27] **Adam:** That's where I learned the most.

[00:30:27] **Adam:** Right.

[00:30:28] **Adam:** I graduated college, I had a good understanding of web development fundamentals, and a subset of tools that might be useful.

[00:30:37] **Adam:** I, I learned way more useful tools on the job than in school.

[00:30:38] **Carol:** Mhm.

[00:30:38] **Tim:** Mhm,

[00:30:40] **Ben:** Mhm, mhm,

[00:30:40] **Adam:** Um, and

[00:30:42] **Adam:** I like, I, I knew enough to get my work done, but I definitely wasn't growing.

[00:30:49] **Adam:** And then I started getting involved with different user groups.

[00:30:51] **Adam:** Right.

[00:30:51] **Adam:** Like the ColdFusion user group I started going to conferences, um, and I learned a ton.

[00:30:57] **Carol:** Mhm.

[00:30:58] **Adam:** Right.

[00:30:58] **Adam:** Like that, that really leveled up my career at least once, if not multiple times.

[00:30:58] **Tim:** Mhm,

[00:31:03] **Adam:** And

[00:31:04] **Ben:** Mhm,

[00:31:05] **Adam:** it does feel like all of those things are, are withering on the vine and dying.

[00:31:09] **Adam:** And maybe that's just because the communities that I was involved with were all niche communities anyway.

[00:31:15] **Adam:** Right.

[00:31:15] **Adam:** Like the ColdFusion community and they, you know, even the, the biggest communities, I'm sure, like Python and JavaScript are struggling now.

[00:31:18] **Tim:** Mhm,

[00:31:25] **Ben:** Mhm,

[00:31:27] **Adam:** and so it's not hard with that in mind, it's not hard to see why smaller niche groups are basically dead at this point.

[00:31:35] **Carol:** Yeah, that's interesting.

[00:31:36] **Carol:** Like I just had a conversation with someone and was trying to get an answer.

[00:31:39] **Tim:** Mhm,

[00:31:39] **Carol:** Like, um, the end of last week, early this week, I believe, and they were on site doing training or at a conference.

[00:31:42] **Adam:** Mhm.

[00:31:47] **Carol:** And it made me realize that by this point in the year, typically I would have already been like signed up to go to a conference.

[00:31:54] **Carol:** I would have had something on my plate.

[00:31:56] **Carol:** I haven't looked for any type of outside training that wasn't brought into me directly.

[00:32:00] **Tim:** Mhm.

[00:32:01] **Adam:** Mhm.

[00:32:02] **Carol:** Like since we've started adopting AI.

[00:32:03] **Ben:** M.

[00:32:05] **Carol:** And that made me realize like, I am

[00:32:09] **Carol:** giving, uh, up on my community a little because I'm not even trying.

[00:32:14] **Carol:** I'm not even like going out to attempt to try to go learn more from people.

[00:32:18] **Carol:** I am trusting AI to do it.

[00:32:22] **Ben:** Mhm.

[00:32:22] **Adam:** I think in addition, the, well has been poisoned.

[00:32:24] **Adam:** Right.

[00:32:25] **Adam:** So, like,

[00:32:27] **Adam:** if you think about those communities, the user groups and the conferences,

[00:32:31] **Adam:** I would say like 30 to 40% of my experience of attending a conference was the conference.

[00:32:39] **Adam:** And the rest was like, networking and talking about this upcoming conference that I'm going to on Twitter and talking about the conference that I just left on Twitter.

[00:32:41] **Tim:** Yeah.

[00:32:42] **Ben:** Right,

[00:32:45] **Carol:** M.

[00:32:46] **Carol:** Yep.

[00:32:47] **Ben:** Right.

[00:32:48] **Adam:** So the, the weeks and months leading up to and after are, are like a big part of the experience.

[00:32:48] **Carol:** So motivating, right?

[00:32:50] **Carol:** Yeah.

[00:32:53] **Adam:** And now Twitter is a hellscape populated by 95% bots that want, uh, you to hate people.

[00:32:59] **Ben:** Yo, that's the other thing is, is it's not.

[00:33:00] **Adam:** But.

[00:33:02] **Ben:** Yeah.

## [00:33:02] Ungated Online Spaces and Generic Meetups

[00:33:02] **Ben:** Like not just the physical spaces, but even I feel like the online spaces.

[00:33:06] **Ben:** Let's call, I'll call the ungated online spaces just feel, I don't want to say awful.

[00:33:11] **Adam:** So you're saying not our Discord.

[00:33:11] **Tim:** Fake.

[00:33:11] **Tim:** Fake.

[00:33:12] **Carol:** Uh, yeah.

[00:33:13] **Tim:** Fake.

[00:33:13] **Ben:** Yeah, yeah, yeah, exactly.

[00:33:13] **Carol:** I was gonna say, what do you, what do you mean by ungated?

[00:33:14] **Tim:** Mhm.

[00:33:15] **Carol:** What does that mean?

[00:33:16] **Ben:** I, I don't know.

[00:33:17] **Ben:** Like,

[00:33:19] **Ben:** I, I guess by ungated I mean like not centered around something

[00:33:23] **Ben:** like Twitter.

[00:33:24] **Tim:** Yeah,

[00:33:24] **Ben:** You know, it's Twitter's a broad platform and it's kind of.

[00:33:27] **Adam:** LinkedIn.

[00:33:27] **Ben:** Yeah.

[00:33:28] **Ben:** And like, even Facebook, I hate to say this, but, like, Facebook is just awful.

[00:33:33] **Tim:** It is awful.

[00:33:33] **Ben:** And, uh.

[00:33:33] **Carol:** You're m the only one that uses it.

[00:33:35] **Ben:** I know.

[00:33:35] **Ben:** Well, and that's the thing is like, even when I go to my.

[00:33:37] **Ben:** Even when I go into feeds and I look at just my friends feeds, it's still.

[00:33:41] **Ben:** Half of it is advertisements.

[00:33:43] **Tim:** Mm.

[00:33:43] **Carol:** Agree.

[00:33:43] **Tim:** Yeah.

[00:33:43] **Adam:** Yep.

[00:33:44] **Ben:** It's crazy.

[00:33:44] **Carol:** Mhm.

[00:33:45] **Adam:** An AI slop.

[00:33:46] **Adam:** And yeah.

[00:33:46] **Tim:** It's the enshittification.

[00:33:48] **Carol:** Yep.

[00:33:48] **Ben:** And, um, I.

[00:33:49] **Ben:** I'll tell you.

[00:33:50] **Ben:** Even.

[00:33:50] **Ben:** And uh.

[00:33:51] **Ben:** I go to some meetups here where I can.

[00:33:53] **Ben:** But they're not.

[00:33:54] **Ben:** None of them are.

[00:33:55] **Ben:** Are specific technology.

[00:33:56] **Ben:** They're technology meetups.

[00:33:58] **Ben:** Right?

[00:33:59] **Ben:** They're.

[00:33:59] **Ben:** They're like.

[00:34:00] **Adam:** Oh, general technology meetup.

[00:34:00] **Ben:** Yeah, yeah.

[00:34:01] **Ben:** It's not like XYZ technology.

[00:34:01] **Tim:** Mhm.

[00:34:01] **Adam:** Gotcha.

[00:34:03] **Ben:** It's just tech.

[00:34:05] **Ben:** And it's.

[00:34:06] **Ben:** It is a very different vibe because, you know, if you walked into a ColdFusion user group or even when I would go to an Angular user group in New York City, which, you know, would have 200 people.

[00:34:07] **Adam:** Computer Club.

[00:34:18] **Ben:** You know, you walk up to any one of those 200 people and you have something you can talk about, whereas I walk into a room with 12 other people and it's hit or miss that we really have anything to talk about.

[00:34:22] **Carol:** Yep.

[00:34:23] **Tim:** Yeah.

[00:34:31] **Adam:** Mhm.

[00:34:31] **Ben:** Sam.

[00:34:32] **Carol:** So funny.

[00:34:32] **Carol:** Tim used to host them back when I lived in Warner Robins.

[00:34:32] **Adam:** Sa.

[00:34:35] **Carol:** And I remember showing up and he has Meta glasses one day But they weren't even Meta glasses back then.

[00:34:40] **Tim:** They were your better glasses.

[00:34:40] **Carol:** What were they like?

[00:34:41] **Carol:** Were they my.

[00:34:42] **Carol:** I don't remember these things.

[00:34:42] **Tim:** They're yours.

[00:34:43] **Tim:** They were mine.

[00:34:43] **Carol:** Details don't matter.

[00:34:44] **Tim:** I never, uh.

[00:34:45] **Tim:** Yeah you have.

[00:34:45] **Carol:** They were Google glasses.

[00:34:45] **Tim:** They were yours.

[00:34:47] **Carol:** And then one day he showed up with caviar on pizza and I was like, this is why user groups are for me.

[00:34:52] **Carol:** They're not just about ColdFusion.

[00:34:55] **Carol:** They're Tim's food choices.

[00:34:57] **Tim:** I am bougie.

[00:35:00] **Tim:** So I got a good idea for the third space problem.

[00:35:03] **Ben:** Yeah, please.

[00:35:03] **Adam:** Okay,

[00:35:03] **Tim:** I think Adam.

[00:35:03] **Carol:** Okay.

[00:35:04] **Tim:** I think Adam should start a podcast.

[00:35:07] **Carol:** Oh yeah.

[00:35:07] **Carol:** Because he's good at new projects.

[00:35:09] **Tim:** Yes.

[00:35:09] **Tim:** Start.

[00:35:09] **Tim:** Start a podcast.

[00:35:10] **Tim:** And that, uh, basically would be a place where people who work from home and remotely, like, since COVID we can all get together and like have a podcast and have a Discord channel and hang out.

[00:35:19] **Tim:** That'd be.

[00:35:21] **Tim:** Wait a minute.

[00:35:21] **Ben:** I think it could work.

[00:35:21] **Tim:** Okay, never mind.

[00:35:23] **Tim:** I think we, I think, I think we already do.

[00:35:24] **Adam:** I'll think about that.

[00:35:25] **Tim:** Yeah, think about that.

[00:35:26] **Carol:** Ring, ring, ring.

[00:35:27] **Tim:** Uh, yeah, it might be a good idea.

[00:35:27] **Ben:** It.

[00:35:28] **Tim:** We could get some patrons.

[00:35:28] **Ben:** It's funny.

[00:35:30] **Carol:** Yeah,

[00:35:30] **Ben:** Has anyone, uh, there.

[00:35:31] **Ben:** There's a meme called I only.

[00:35:33] **Ben:** I only recently learned about this, but it feels very on point.

[00:35:37] **Ben:** There's a meme called the Midwit meme where it's like a bell curve, and on one side is a Neanderthal, and on the other side is a, uh.

[00:35:39] **Carol:** I have no idea what that is.

[00:35:41] **Carol:** No.

[00:35:45] **Ben:** I think it's a Jedi.

[00:35:46] **Ben:** And then in the middle, there's like a very confused person.

[00:35:46] **Adam:** Yeah.

[00:35:48] **Tim:** Mhm,

[00:35:49] **Adam:** Mm.

[00:35:49] **Ben:** And.

[00:35:49] **Carol:** Mhm.

[00:35:49] **Ben:** And it's like.

[00:35:50] **Ben:** It.

[00:35:50] **Ben:** It's like the.

[00:35:51] **Ben:** The person who doesn't overthink anything is right.

[00:35:54] **Ben:** And then the person who only, like, has clarity is right.

[00:35:57] **Ben:** And then there's this, like, real messy middle where you're overthinking everything and you're super unhappy.

[00:35:58] **Adam:** Mhm.

[00:36:02] **Ben:** And I feel like this.

[00:36:03] **Ben:** This is like where I've come.

[00:36:04] **Ben:** Like, my Neanderthal brain was like, me, ColdFusion developer And then like, my super unhappy person is like, no one thing defines me.

[00:36:12] **Ben:** I use any kind of database.

[00:36:14] **Ben:** I can kind of do anything.

[00:36:15] **Ben:** And then, like, my enlightened person is like, yeah, I'm a ColdFusion developer

[00:36:16] **Adam:** Mhm.

[00:36:21] **Ben:** Like, that's just where I'm gonna be happy.

[00:36:24] **Carol:** Mhm.

[00:36:25] **Ben:** But, uh, yeah, I.

[00:36:25] **Tim:** Mhm,

[00:36:26] **Ben:** I don't know.

[00:36:27] **Ben:** It's, um.

[00:36:27] **Ben:** Like.

[00:36:27] **Ben:** And the thing is, is like, you know, when we look in the Discord here we have some new people, obviously.

[00:36:32] **Ben:** But I think a lot of the people in the Discord have ColdFusion roots and, uh, and know us, I think, at least

[00:36:37] **Tim:** Mhm.

[00:36:37] **Adam:** Mhm.

[00:36:41] **Ben:** in large part.

[00:36:41] **Tim:** And there's some outliers.

[00:36:42] **Tim:** There's some people that.

[00:36:42] **Ben:** Yeah, yeah, there's definitely some outliers for sure.

[00:36:43] **Carol:** Hello.

[00:36:43] **Tim:** Yeah, yeah,

[00:36:44] **Ben:** But definitely when I look at the list, I select the people I, I guess that I'm most familiar with, I know from ColdFusion.

[00:36:46] **Carol:** Mhm.

[00:36:50] **Ben:** And so I think about how, how does, how would one even find a community like this without the history that we all have and we share

[00:37:01] **Tim:** I don't know.

[00:37:02] **Ben:** and.

[00:37:02] **Carol:** That's called, that's called podcast lookups on like Apple Podcasts and finding.

[00:37:05] **Tim:** Yeah,

[00:37:07] **Adam:** Yeah.

[00:37:08] **Carol:** Mhm.

[00:37:08] **Adam:** Here's your gentle reminder to uh, us five stars on Apple Podcasts.

[00:37:10] **Carol:** Go subscribe.

[00:37:11] **Tim:** Yeah.

[00:37:13] **Carol:** Now that you mention it, Ben.

[00:37:17] **Carol:** No, I think you're right.

[00:37:18] **Carol:** Right.

[00:37:18] **Carol:** Like a lot of our, our support comes from the connections, you know, we've built over the years with people from the CF community.

[00:37:21] **Adam:** Mhm.

[00:37:24] **Tim:** Mhm.

[00:37:27] **Carol:** It's people who've enjoyed seeing Ben's blog.

[00:37:30] **Carol:** You know, I remember reading Ben's blog when I was just a wee little child starting out writing code.

[00:37:35] **Ben:** M just alaska.

[00:37:36] **Carol:** And, and I was.

[00:37:37] **Adam:** So last week.

[00:37:39] **Carol:** And then I um, you know, I was like, I meet Ben in person.

[00:37:42] **Carol:** I'm just like, oh my God, can I take a picture with you?

[00:37:43] **Ben:** Mhm.

[00:37:45] **Carol:** You know, like, like those eyes.

[00:37:47] **Carol:** And we don't, we don't really have that right now.

[00:37:49] **Tim:** No,

[00:37:49] **Carol:** Like, I don't feel like we have people who are leading a tech.

[00:37:52] **Carol:** They're just leading lots of topics.

[00:37:54] **Carol:** There are no big community leaders anymore.

[00:37:56] **Ben:** Sam.

## [00:37:57] Reviving the Dev Conference

[00:37:57] **Tim:** And I think there is a need for it.

[00:37:59] **Tim:** I really do.

[00:37:59] **Carol:** I agree.

[00:38:01] **Tim:** I was talking to Rob, uh, Bilson a couple weeks ago.

[00:38:02] **Ben:** Mhm.

[00:38:05] **Tim:** I just was thinking, thinking about him.

[00:38:07] **Tim:** He was a friend of mine that used to see every year at conferences multiple times a year.

[00:38:11] **Tim:** And he's like, yeah, I miss, you know, the thing you miss the most is like the people that you meet and the connections that you make.

[00:38:16] **Adam:** Mhm.

[00:38:18] **Carol:** Sa.

[00:38:19] **Tim:** And I told him, I was like, I seriously want to just

[00:38:23] **Tim:** start a dev conference because I have experience doing conferences.

[00:38:26] **Tim:** I've done about seven different conferences, um, as an organizer.

[00:38:29] **Adam:** Yeah.

[00:38:31] **Tim:** And just have it.

[00:38:33] **Tim:** I told tongue in cheek, but slightly true.

[00:38:35] **Carol:** Mhm.

[00:38:36] **Tim:** Make it look on paper, super legit.

[00:38:38] **Tim:** So that if you work for a corporation, if you work for a corporation, they'll pay, they'll pay for your travel and everything.

[00:38:39] **Ben:** Right.

[00:38:39] **Ben:** So your boss pays for it,

[00:38:44] **Tim:** But in reality, you know, there'll be some tech talk, but mostly it's a hanging, mostly it's just the hang so that a bunch of, bunch of us can all get together.

[00:38:48] **Ben:** Yo.

[00:38:52] **Tim:** So, uh, if any of you listeners in our Discord and Patreon want to think that's a good idea, if you'd be willing to travel to someplace nice, uh, and you know, during a, maybe a semi nice.

[00:38:56] **Adam:** Mhm.

[00:39:03] **Carol:** M.

[00:39:03] **Carol:** Semi nice.

[00:39:05] **Tim:** During the time, during the time of year, maybe the summer when the kids are out of school, if you still have kids.

[00:39:05] **Carol:** Semi nice.

[00:39:05] **Adam:** So.

[00:39:05] **Ben:** Mhm,

[00:39:08] **Tim:** We all just have like a two to three day conference and hang and talk about AI and just you know, and get your company to pay for it.

[00:39:13] **Adam:** Well, uh, I, Yeah, I have a funny story along this line, actually.

[00:39:15] **Tim:** I'll do it.

[00:39:16] **Tim:** M.

[00:39:18] **Adam:** I don't know if I've ever mentioned this to any of you guys before, so it does actually involve Rob Bilson too.

[00:39:23] **Adam:** so the statute of limitations is up on this, which is the only reason I'm sharing the story.

[00:39:27] **Adam:** Um,

[00:39:28] **Tim:** No one can go to jail now.

[00:39:30] **Adam:** no current employer can get mad at me.

[00:39:31] **Carol:** Sa

[00:39:33] **Adam:** back when I worked at the University of Pennsylvania, um, I had like a training budget.

[00:39:34] **Carol:** mhm.

[00:39:35] **Tim:** Mhm.

[00:39:37] **Adam:** Um, and, um, I, so I was talking to some friends and we were like, it'd be nice to, to have kind of what you were talking about, right?

[00:39:41] **Ben:** Mhm,

[00:39:44] **Adam:** Like just a more general get together.

[00:39:46] **Adam:** It needs to look legit.

[00:39:48] **Adam:** But.

[00:39:48] **Adam:** And we actually do want to learn and share and that sort of stuff.

[00:39:51] **Adam:** But, you know, under the hood, what we're really looking for is networking and just hanging out friends.

[00:39:52] **Carol:** Mhm.

[00:39:56] **Adam:** And so we held an event at Rob's company, and we called it Sand Camp, because he lived in Phoenix, Arizona.

[00:40:00] **Ben:** Mhm.

[00:40:04] **Tim:** Mm.

[00:40:05] **Adam:** and it was like, I think three or four people from his company.

[00:40:08] **Adam:** Maybe five if you count him.

[00:40:10] **Adam:** And then it was like myself, I was working at the University of Pennsylvania at the time.

[00:40:10] **Carol:** Mhm.

[00:40:11] **Tim:** Mhm.

[00:40:15] **Adam:** My current boss, Steve, who at the time was like solo entrepreneur sort of thing.

[00:40:22] **Adam:** Um, and I think that might have been it.

[00:40:26] **Adam:** And, and honestly, you know what, now that I think about it, that was the birthplace of Taffy.

[00:40:28] **Carol:** Mhm.

[00:40:31] **Adam:** I, I had, I kind of had this idea for like, REST Sucks in ColdFusion as like a, as a presentation.

[00:40:37] **Ben:** Mhm.

[00:40:37] **Adam:** and I gave the presentations like, these are all the reasons that the different frameworks suck.

[00:40:40] **Adam:** And then, um, kind of in.

[00:40:41] **Adam:** In the background while listening to every other everybody else's presentations.

[00:40:44] **Adam:** That's where I like kind of started writing the initial code for Taffy.

[00:40:47] **Tim:** That's cool.

[00:40:48] **Adam:** Um, and, but so I had uh, my employer pay for me to fly out to Arizona to attend a mini conference in a conference room at, at a company.

[00:40:48] **Carol:** Let's go.

[00:40:48] **Tim:** I have m not heard that story.

[00:40:55] **Ben:** Heck yeah.

[00:40:58] **Adam:** and it was like eight people in a conference room.

[00:41:01] **Ben:** Well in camp and camp was like a big term back then, like BarCamps and mobile camps.

[00:41:01] **Tim:** That's funny.

[00:41:01] **Adam:** I had a sandwich there.

[00:41:02] **Carol:** Mhm.

[00:41:04] **Carol:** It was.

[00:41:05] **Carol:** Yeah.

[00:41:05] **Carol:** Mhm.

[00:41:06] **Adam:** Yeah, I had a sandwich while I was there that I still remember.

[00:41:06] **Tim:** Yeah,

[00:41:07] **Carol:** Yep.

[00:41:09] **Adam:** It had like, it was just like a deli meat sandwich or something, but it had like a certain type of like green apple.

[00:41:10] **Carol:** Really?

[00:41:16] **Adam:** I don't know exactly which one it was.

[00:41:17] **Adam:** And it had like honey mustard on it.

[00:41:19] **Adam:** Uh, oh man.

[00:41:20] **Adam:** I still think about that sandwich.

[00:41:22] **Carol:** Who the hell puts apples on a sandwich?

[00:41:22] **Tim:** Good catering.

[00:41:24] **Adam:** Right.

[00:41:25] **Adam:** But it was amazing.

[00:41:25] **Carol:** Yeah.

[00:41:26] **Tim:** That's funny.

[00:41:27] **Carol:** Mhm.

[00:41:27] **Adam:** It was a real thin slice.

[00:41:28] **Carol:** So did you guys watch Silicon Valley where they have like the whole like incubator sessions and stuff?

[00:41:31] **Ben:** M of course.

[00:41:31] **Adam:** Oh yeah.

[00:41:31] **Tim:** M m,

[00:41:35] **Ben:** Mhm,

[00:41:36] **Carol:** It's almost like you need the dev conference to be like focused on incubator type work.

[00:41:41] **Carol:** Like let's all get together, let's just talk about what we want to do, what we could do and make it be more about

[00:41:42] **Adam:** Mhm,

[00:41:48] **Carol:** outcome and getting you motivated more than necessarily.

[00:41:53] **Carol:** You're going to learn something brand new and you're going to have to sit through all these conferences.

[00:41:56] **Ben:** Mhm,

[00:41:57] **Carol:** Like let's just all like dedicate a week to, to doing.

[00:42:01] **Tim:** Yeah, because, because I think the problem with, with

[00:42:05] **Tim:** language-based communities is that if they're typically run, if it's a, by the language organizers, if it's a for-profit company like Adobe, it's run by them.

[00:42:09] **Carol:** Mhm.

[00:42:15] **Tim:** If it's not, it's usually, you know, somebody you know, pushing the new release of their latest version of whatever and it's like, it's a very focused agenda, but not necessarily one that's, that's useful to people, particularly if you've been around a long time.

[00:42:17] **Ben:** Mhm,

[00:42:25] **Carol:** Mhm.

[00:42:29] **Tim:** It's like these new features that you've added to this language that's been around 10, 15, 20 years.

[00:42:34] **Tim:** Yeah, I mean they're, they're probably not that amazing and probably don't take that long to understand.

[00:42:36] **Ben:** Mhm.

[00:42:38] **Adam:** Right.

[00:42:40] **Tim:** but yeah, you're right.

[00:42:41] **Tim:** It's like the, the, the paradox of these things is that there is still a need for that, that human connection, that networking, that just getting you re-engaged and excited about, you know, your job and what you do versus actually learning something, that is going to like add, you know, 20% to your bottom line.

[00:42:47] **Carol:** Ma'.

[00:42:47] **Carol:** Am.

[00:43:02] **Tim:** I don't think that actually happens but I think that's where corporate's like, oh yeah, we're going to keep training our people so they keep growing and we keep, you know, making more money.

[00:43:06] **Ben:** Right.

[00:43:09] **Carol:** Mhm.

[00:43:09] **Tim:** I'm like,

[00:43:11] **Adam:** I think part of the difficulty of running an event like that is going to be getting sponsors.

[00:43:13] **Ben:** M well like,

[00:43:16] **Adam:** Right.

[00:43:16] **Adam:** Because it's impossible to know who's going to come and, and what is going to interest them enough to get somebody to sponsor something to get in front of.

[00:43:24] **Tim:** Yeah, yeah,

[00:43:25] **Carol:** We've been there.

[00:43:26] **Carol:** Adam.

[00:43:27] **Tim:** yep.

[00:43:28] **Ben:** I almost feel like it's like we had COVID where everybody was, was quarantined and then it took.

[00:43:34] **Adam:** We're in jail.

[00:43:35] **Adam:** Yeah.

[00:43:35] **Ben:** Yeah.

[00:43:35] **Ben:** Ah, it took people a long time to kind of like want to even get back together.

[00:43:39] **Ben:** It's like everyone was dying for human contact but no one necessarily wanted to travel anywhere to do anything.

[00:43:45] **Ben:** It felt like for a long time.

[00:43:46] **Carol:** M.

[00:43:46] **Ben:** And then it became this sort of catch-22 where people who put on conferences were like, like first of all I need to organize a conference like a year and a half ahead of time.

[00:43:49] **Tim:** Mhm.

[00:43:55] **Ben:** I have to lay out insurance money.

[00:43:55] **Carol:** Oh yeah.

[00:43:56] **Adam:** Mm, mhm,

[00:43:58] **Ben:** I have to get like unions on board so they can move stuff.

[00:44:01] **Ben:** I have to order all the food, like I have to set up the hotel.

[00:44:03] **Adam:** Mhm.

[00:44:05] **Ben:** Like they have to do all this stuff and then they're like I'm not sure anyone's going to show up and I might not know that I'm, you know.

[00:44:08] **Carol:** Mhm.

[00:44:10] **Tim:** Yeah.

[00:44:11] **Ben:** And then they're like.

[00:44:12] **Ben:** And then people put off buying tickets to like a week before sales ends.

[00:44:17] **Ben:** So sometimes like um, almost up until the conference, it looks like no one's going to show.

[00:44:18] **Carol:** Sa.

[00:44:20] **Adam:** Sa.

[00:44:22] **Ben:** And then

[00:44:24] **Ben:** this.

[00:44:24] **Ben:** So people are nervous to put anything on and then people don't have stuff to go to and it becomes this like self-fulfilling prophecy.

[00:44:29] **Carol:** Mhm.

[00:44:30] **Ben:** And then AI shows up and now it's like it destroys almost the idea of having again like these community-based events to begin with because communities just feel like less of a thing.

[00:44:42] **Ben:** Plus like the web is kind of dying now uh, I, I don't know.

[00:44:45] **Ben:** It's just.

[00:44:46] **Ben:** Yeah, it's all, it's, it's became this one-two punch

[00:44:50] **Ben:** COVID going into into agentic programming.

[00:44:54] **Ben:** All the,

[00:44:54] **Adam:** I don't think you're wrong.

[00:44:56] **Ben:** all the.

[00:44:56] **Tim:** Yeah,

[00:44:57] **Ben:** Yeah.

[00:44:58] **Tim:** maybe I'll just have AI like help me do the conference.

[00:44:59] **Ben:** M.

[00:45:01] **Tim:** We can just, we just.

[00:45:02] **Adam:** There you go.

[00:45:02] **Carol:** Yeah.

[00:45:02] **Tim:** There you go.

[00:45:03] **Tim:** It run the whole thing like it runs a soda machine.

[00:45:05] **Tim:** I'm sure I can't lose any money that way.

[00:45:08] **Adam:** I understood that reference.

[00:45:11] **Ben:** I actually looked up tungsten cubes to see how much they were.

[00:45:11] **Tim:** Mhm.

[00:45:14] **Ben:** They are very expensive.

[00:45:15] **Ben:** I was, I was shocked.

[00:45:17] **Carol:** M have no idea what y' all are talking about.

[00:45:19] **Adam:** Mhm.

[00:45:22] **Ben:** There was.

[00:45:22] **Ben:** Who was it?

[00:45:23] **Ben:** OpenAI.

[00:45:23] **Ben:** One of the.

[00:45:24] **Ben:** Which company?

[00:45:24] **Ben:** So one of the companies as an experiment had a uh, a vending machine.

[00:45:30] **Ben:** Like a, like a vending machine that could be customized in their office.

[00:45:33] **Ben:** And it had AI run it to prove that AI could run a business.

[00:45:38] **Ben:** And I think the AI started responding to user requests and a user said, you should start selling tungsten cubes.

[00:45:45] **Ben:** Tungsten's a, I think it's like the densest metal.

[00:45:47] **Adam:** M.

[00:45:47] **Adam:** It's a very heavy metal.

[00:45:47] **Ben:** Is that what it is?

[00:45:48] **Adam:** Yeah,

[00:45:48] **Tim:** It's what the filament in old, light bulbs.

[00:45:49] **Ben:** And

[00:45:49] **Carol:** Wedding bands.

[00:45:51] **Ben:** oh, I didn't know that.

[00:45:53] **Carol:** Did mhm.

[00:45:53] **Tim:** Mhm.

[00:45:53] **Carol:** Not know that either.

[00:45:54] **Ben:** So I think the vending machine started selling tungsten cubes for like, for like pennies on the dollar or something.

[00:46:02] **Tim:** But the actual cost is a lot more.

[00:46:02] **Carol:** I love it.

[00:46:04] **Ben:** Yeah, yeah.

[00:46:07] **Carol:** Yeah.

[00:46:08] **Carol:** I feel like in my conversations with AI is AI wants to please me.

[00:46:13] **Carol:** At the end of it it just bows down to my object.

[00:46:16] **Adam:** Yeah,

[00:46:16] **Tim:** Mhm.

[00:46:20] **Adam:** there's.

[00:46:20] **Adam:** I want to make a comment on that and I don't want it to come across as intense, entirely negative.

[00:46:23] **Ben:** Mhm.

[00:46:26] **Adam:** So I think that, that.

[00:46:28] **Adam:** Well, so it could be because I'm making an assumption.

[00:46:31] **Adam:** Carol, when you say that, is that your impression of all the different uh, and model providers, companies?

[00:46:38] **Carol:** Yeah.

[00:46:38] **Carol:** Even with Fable right now, like I will challenge it.

[00:46:40] **Adam:** Well,

[00:46:41] **Carol:** And it goes.

[00:46:42] **Carol:** Oh yeah, you know what, let me go reevaluate my assessment and get back to you.

[00:46:44] **Tim:** Mhm.

[00:46:45] **Ben:** Right.

[00:46:45] **Ben:** It, it overstated something.

[00:46:47] **Ben:** Like uh, I overstated my objection.

[00:46:48] **Carol:** Yeah,

[00:46:50] **Ben:** You're m.

[00:46:50] **Carol:** I shouldn't have made those assumptions.

[00:46:52] **Carol:** Let me be factual here.

[00:46:54] **Tim:** Classic mistake.

[00:46:56] **Carol:** Yeah.

[00:46:56] **Adam:** So I, to me, I feel like I get less of that.

[00:47:00] **Adam:** Not none, but a lot less of that with ChatGPT, Codex whatever you want to call it.

[00:47:04] **Ben:** Mhm.

[00:47:05] **Adam:** The worst named of all of the AI products.

[00:47:08] **Adam:** Um, but so my impression is that that is a training thing.

[00:47:13] **Adam:** I feel like Anthropic really wants people to believe that Claude is closer to AGI and so they train it to spe speak more like a human.

[00:47:13] **Tim:** Mhm.

[00:47:22] **Adam:** And whether it's my agents file or the underlying training or whatever, I just feel like I get a lot less of that through ChatGPT, specifically the way I use it for coding stuff.

[00:47:23] **Ben:** Mhm.

[00:47:34] **Adam:** Um, so.

[00:47:34] **Carol:** Interesting.

[00:47:35] **Tim:** That's funny that that's my exact opposite take as of right now.

[00:47:38] **Adam:** Oh,

[00:47:40] **Tim:** Of course I don't use, I don't, I don't use, I don't use ChatGPT for any coding It's my personal and I only use the chat feature.

[00:47:40] **Adam:** interesting.

[00:47:40] **Carol:** M elaborate.

[00:47:46] **Adam:** Mm,

[00:47:47] **Tim:** I don't use code.

[00:47:48] **Ben:** Yeah.

[00:47:48] **Ben:** I use chat.

[00:47:48] **Adam:** okay.

[00:47:50] **Tim:** Um, and so I find it to be a lot more sycophantic.

[00:47:54] **Tim:** Claude.

[00:47:54] **Tim:** I guess maybe because I only use it for code is realized I'm here to work, I'm not here to make friends.

[00:48:02] **Tim:** So yeah, maybe it's just usage or training like you said.

[00:48:06] **Adam:** Right.

[00:48:06] **Adam:** Mhm,

[00:48:07] **Ben:** Well it's funny, I think I'm the exact opposite of you because when I use ChatGPT chat, I'm not really having a probing conversation.

[00:48:13] **Carol:** Mhm

[00:48:16] **Carol:** mhm.

[00:48:16] **Ben:** It's more like high level.

[00:48:18] **Ben:** How does something work?

[00:48:19] **Ben:** Is there something I can install on my VPS to do something It's not like I'm never challenging it.

[00:48:19] **Tim:** Yeah.

[00:48:23] **Tim:** Mhm.

[00:48:24] **Ben:** Whereas Claude, because you know, again, I'm my own worst enemy, I'm constantly being like, well why did you say this?

[00:48:26] **Adam:** Mhm,

[00:48:31] **Ben:** And like why do you make that assumption?

[00:48:32] **Ben:** And I don't think that's right.

[00:48:33] **Ben:** And that's when it's constantly coming back with, let me double check.

[00:48:36] **Tim:** Mhm,

[00:48:37] **Ben:** You're right, I overstated it.

[00:48:38] **Carol:** M.

[00:48:39] **Carol:** Yeah.

[00:48:39] **Ben:** I held an assumption as a fact and it's not true.

[00:48:42] **Ben:** You know, like all that jazz.

[00:48:44] **Carol:** So uh, let me tell you what happened with Claude today So I'm in Claude Cowork and I have this project going on.

[00:48:47] **Adam:** Mhm.

[00:48:49] **Carol:** I mentioned in the triumph, right.

[00:48:50] **Carol:** Like this like whole like getting another office up, uh, with AI and we were working on something together, you know, Claude and I, um, and I was like, hey, okay, let's just pause.

[00:48:57] **Tim:** Mhm.

[00:49:01] **Carol:** Like this isn't going to get done today but remind me Monday to get back at it.

[00:49:06] **Carol:** And its response was yes, I see that we're not going to get done with that.

[00:49:09] **Ben:** Mhm.

[00:49:10] **Carol:** You go relax, have a great weekend and I'll be here Monday when you're ready.

[00:49:15] **Carol:** And I'm like, you are way too personal right now.

[00:49:18] **Carol:** I don't like this, like I feel like I have to respond with thanks, yes, I plan to relax.

[00:49:21] **Adam:** Yeah.

[00:49:24] **Carol:** And that's not like you're not a person.

[00:49:28] **Tim:** You say thank you to it and you just wasted a half a gallon of water at some data center.

[00:49:29] **Adam:** Mhm,

[00:49:30] **Carol:** Uh, yeah.

[00:49:32] **Carol:** Cut some trees.

[00:49:34] **Ben:** Yo, can I, I just want to circle back to the language community stuff for, for one second.

## [00:49:34] Language Specialization and the Fracturing of Communities

[00:49:34] **Carol:** Yeah.

[00:49:39] **Carol:** Oh yeah, this, this like topic, right?

[00:49:39] **Ben:** Um,

[00:49:39] **Tim:** What m.

[00:49:40] **Tim:** What is the main top?

[00:49:41] **Carol:** Hm.

[00:49:41] **Carol:** Yeah.

[00:49:42] **Ben:** I, I, so the thing that

[00:49:46] **Ben:** cuts very personally for me is I think a big part of finding programming and the programming community was like I felt people, I felt like I had found people that I could connect with in a way that was very comfortable for me and my social peccadilloes.

[00:49:49] **Adam:** Mhm,

[00:50:01] **Carol:** Mhm.

[00:50:05] **Tim:** Mhm.

[00:50:05] **Ben:** And I know that there are many social things that I could go out and do.

[00:50:10] **Adam:** Mhm,

[00:50:10] **Ben:** I know like board game nights are a huge thing.

[00:50:13] **Ben:** I know people love to get together for book clubs and uh, like speed dating and writing workshops and like there's a lot of stuff.

[00:50:22] **Carol:** Mhm.

[00:50:23] **Ben:** If I go to meetup.com and I look in my area, there's loads of stuff and like, but none of it is stuff I want to do.

[00:50:30] **Ben:** And it's, and it's not that they're bad things.

[00:50:31] **Adam:** Mhm.

[00:50:32] **Ben:** It's just like programming was such a sweet spot.

[00:50:36] **Ben:** It was the kind of people I liked the kind of topics I liked.

[00:50:36] **Tim:** Mhm.

[00:50:40] **Ben:** It was the right environment, you know, like I didn't have to be at a bar or somewhere loud.

[00:50:43] **Carol:** Mhm.

[00:50:47] **Ben:** Uh, you know,

[00:50:49] **Ben:** dovetailed nicely with my social anxiety.

[00:50:53] **Adam:** I wonder too if this is kind of a symptom of languages getting extremely specialized.

[00:50:53] **Ben:** You know,

[00:51:00] **Adam:** Right.

[00:51:00] **Adam:** So like 10 years ago, 15 years ago.

[00:51:03] **Adam:** languages were getting really specialized.

[00:51:03] **Ben:** Mhm.

[00:51:04] **Tim:** Mhm,

[00:51:05] **Adam:** Back in the day there was just Computer Club and like, yeah, some people might program in VB or BASIC or C or you know, Fortran or whatever, but like you all just went to the Computer Club and maybe there would be like little breakout groups.

[00:51:07] **Carol:** Mhm.

[00:51:13] **Ben:** Sa

[00:51:16] **Ben:** mhm,

[00:51:21] **Adam:** You know, we would go over in our corner and talk about

[00:51:25] **Adam:** BASIC while another corner was a Fortran group or whatever.

[00:51:25] **Tim:** Mhm,

[00:51:28] **Carol:** Mhm.

[00:51:28] **Adam:** But like, I feel like the more a.

[00:51:32] **Adam:** Well a.

[00:51:32] **Adam:** We have more stuff now, right?

[00:51:34] **Adam:** We have JavaScript and TypeScript and Ruby and Python and a thousand other things.

[00:51:37] **Ben:** Mhm,

[00:51:40] **Adam:** and so that kind of fractures communities and then even within those groups I think that there's additional fracturing and I think everybody is exhausted.

[00:51:45] **Tim:** Mhm.

[00:51:49] **Adam:** And so like when I was, for a long time I was a manager of the Philadelphia ColdFusion user group Philly CFUG.

[00:51:55] **Adam:** Um, and I watched the decline.

[00:51:57] **Adam:** I presided over the decline of the Philly CFUG, which was depressing.

[00:51:59] **Ben:** Mhm.

[00:52:02] **Adam:** and then brief, funny story, shortly after I finally, it was like, okay, well, we have like two people coming to meetings every month, so we're just not going to do this anymore.

[00:52:06] **Carol:** Mhm

[00:52:07] **Carol:** mhm.

[00:52:11] **Adam:** I ended up getting drafted to be the Scout, uh, Master Cubmaster for my kids Cub Scout Pack.

[00:52:18] **Adam:** and like the next year that died too, under my stewardship.

[00:52:23] **Ben:** Uh, I feel like maybe it's under your orchestration.

[00:52:26] **Adam:** Man.

[00:52:27] **Tim:** You're the volunteer of last resort.

[00:52:27] **Adam:** Uh,

[00:52:29] **Adam:** well, what organization wants me to lead now

[00:52:32] **Carol:** Mhm.

[00:52:33] **Tim:** Can you go run the GOP?

[00:52:33] **Adam:** anyway,

[00:52:36] **Adam:** if they'll have me?

[00:52:37] **Adam:** but anyway, yeah, like, uh, I feel like it's a, it's a perfect.

[00:52:41] **Tim:** Mhm.

[00:52:41] **Adam:** Not, maybe not a perfect storm, but it's a, It's a lot of bad things coinciding, right?

[00:52:44] **Carol:** Mhm.

[00:52:45] **Adam:** Like people getting burnt out and the continued fracturing of different technologies and the specialization.

[00:52:48] **Ben:** Mm, mhm.

[00:52:52] **Adam:** And like, everybody thinks it'd be a great idea to have like, let's have a conference just for Next.js within JavaScript within web development.

[00:53:01] **Adam:** Like, and then all of a sudden there's just not enough people to go around, not enough excitement to go around.

[00:53:07] **Adam:** And I feel like that's contributing to the death of these, this particular type of third space.

[00:53:08] **Ben:** Yeah.

[00:53:10] **Ben:** Sa

[00:53:12] **Ben:** mhm,

[00:53:14] **Carol:** Yeah.

[00:53:14] **Carol:** It feels like the ones that still win out are the big enterprise level like solutions, like .NET, you know I can go to Microsoft stuff, like stuff anytime I want.

[00:53:25] **Carol:** Like they're constantly hosting things, but it's not just about .NET, like they have all their, their Azure pieces in there.

[00:53:31] **Carol:** They have everything else as part of it.

[00:53:33] **Ben:** Mhm,

[00:53:33] **Carol:** Like it's a massive week-long event in Orlando.

[00:53:36] **Carol:** Usually like AWS does everything like in Vegas for a week, you know, for four days.

[00:53:40] **Tim:** Mhm.

[00:53:41] **Adam:** Mm, mhm.

[00:53:41] **Carol:** And it's not just language.

[00:53:43] **Carol:** It exposes you to so much more.

[00:53:45] **Carol:** And I think those are the only ones that are really surviving.

[00:53:47] **Carol:** So.

[00:53:49] **Tim:** What's funny is those big corporate ones tend to be the biggest boondoggles ever.

[00:53:53] **Tim:** Right?

[00:53:53] **Tim:** You have all these topics that sound really great, but it's like a lot of them are very.

[00:53:54] **Ben:** Mhm.

[00:53:58] **Carol:** They're just sales pitches.

[00:53:58] **Adam:** Yeah.

[00:53:59] **Tim:** Yeah, they're sales pitches.

[00:54:00] **Carol:** Yeah,

[00:54:01] **Tim:** Right.

[00:54:01] **Tim:** So.

[00:54:01] **Carol:** they feel like sales pitches.

[00:54:03] **Carol:** Yeah.

[00:54:03] **Carol:** And there's just a lot of events after where all they're trying to do is convince you to like sign a contract to like join some piece of an application they have and it doesn't feel so much like a community and more like, hey, you're selling a car to me.

[00:54:13] **Tim:** Yeah,

[00:54:17] **Tim:** exactly.

[00:54:18] **Ben:** And also, uh, I don't know if this is broadly true, but I have found that when I have tried to look up some more of the modern conferences that still exist, the ticket prices are kind of wild.

[00:54:18] **Carol:** Mhm.

[00:54:18] **Tim:** Exactly.

[00:54:20] **Adam:** Mhm,

[00:54:21] **Adam:** mhm,

[00:54:32] **Ben:** Like, I'm, you know, you know, if I think back,

[00:54:35] **Ben:** I would go to cf.Objective(), and I think maybe it was like a 250 ticket or something.

[00:54:37] **Tim:** Mhm.

[00:54:41] **Ben:** And

[00:54:41] **Carol:** We like to keep it at 199.

[00:54:42] **Adam:** Mhm,

[00:54:43] **Ben:** was it?

[00:54:43] **Carol:** Thank you.

[00:54:44] **Ben:** Yeah, yeah.

[00:54:44] **Ben:** You know, and it's like the CF Summit in Vegas I think was 199.

[00:54:44] **Tim:** Yeah.

[00:54:49] **Carol:** Mhm.

[00:54:50] **Ben:** Um, jQuery I used to go to, you know, is probably kind of in the same ballpark.

[00:54:54] **Ben:** I tried to look up ng-conf a couple of years ago That's the Angular conference.

[00:54:58] **Ben:** And I think the ticket was like, like eighteen hundred dollars or something.

[00:55:02] **Tim:** Wow.

[00:55:03] **Ben:** I'm like, I'm not spending that kind of money.

[00:55:06] **Ben:** And then also buying a plane ticket and getting a hotel room.

[00:55:09] **Adam:** Mhm,

[00:55:10] **Tim:** Mhm.

[00:55:11] **Ben:** uh, so I don't know what these, like, AWS and the.

[00:55:14] **Ben:** And the Microsoft ones, I don't know if they're pricey or not, because maybe they're subsidized.

[00:55:17] **Carol:** Very pricey.

[00:55:19] **Carol:** No, they're very pricey.

[00:55:19] **Ben:** Yeah.

[00:55:19] **Ben:** Like, it's like the only conferences that are left are conferences where people are assuming that everyone who's going is being paid to go essentially, you know, like, like by their corporation.

[00:55:28] **Tim:** Yep.

[00:55:28] **Tim:** Hmm.

[00:55:31] **Carol:** Yeah.

[00:55:31] **Carol:** These big enterprise solutions are, are like supported by enterprise companies that have the money to then send people to it.

[00:55:39] **Ben:** Yeah.

[00:55:40] **Ben:** So that feels like that's a.

[00:55:42] **Ben:** That's a big barrier to entry.

[00:55:44] **Carol:** Agree.

[00:55:45] **Tim:** For sure.

[00:55:46] **Tim:** Don't know how to fix it though, other than run our own.

[00:55:47] **Ben:** I know.

[00:55:49] **Ben:** Ah.

[00:55:49] **Ben:** Uh, well,

[00:55:50] **Carol:** A few of us have experience.

[00:55:52] **Tim:** Mhm.

[00:55:52] **Tim:** We did.

[00:55:53] **Tim:** Yeah, I think.

[00:55:53] **Ben:** if nothing else, you guys let me vent, so.

[00:55:54] **Tim:** Yeah, I think.

[00:55:56] **Ben:** I appreciate that.

[00:55:59] **Carol:** I think it's been a great topic.

[00:56:00] **Carol:** Like, I think it's very valid with where we are right now and trying to keep our communities alive.

[00:56:04] **Carol:** And AI is kind of getting in the way of that a little.

[00:56:07] **Tim:** Yeah.

[00:56:09] **Tim:** You know, you have.

[00:56:10] **Tim:** AI is doing the works.

[00:56:11] **Tim:** It's.

[00:56:11] **Tim:** It's taking the humanity out of work

[00:56:14] **Adam:** Mhm,

[00:56:14] **Ben:** Yeah.

[00:56:15] **Tim:** in many aspects of.

[00:56:16] **Tim:** Of life and you.

[00:56:18] **Tim:** Where you start to feel like.

[00:56:20] **Tim:** I mean, like today I.

[00:56:20] **Adam:** Mhm,

[00:56:21] **Tim:** I just feel like a Claude babysitter pretty much most of the day.

[00:56:24] **Carol:** Yeah.

[00:56:25] **Ben:** Yo, it is.

[00:56:25] **Tim:** Mhm.

[00:56:26] **Ben:** It's overwhelming.

[00:56:27] **Ben:** Like, I want to be someone who, uh, exercises good judgment and feels like I understand what I'm doing.

[00:56:34] **Ben:** But at some point, the conversation gets so long and takes so many turns.

[00:56:39] **Ben:** I.

[00:56:39] **Adam:** Mhm,

[00:56:40] **Ben:** At the, uh, at uh, some point, you just go like, whatever, just fix it.

[00:56:40] **Carol:** Oh my God.

[00:56:43] **Tim:** Mhm,

[00:56:43] **Ben:** Like, I don't care.

[00:56:46] **Ben:** Like, whatever you can do to make sure that the review bot doesn't flag it.

[00:56:49] **Ben:** Just do that.

[00:56:51] **Carol:** All right.

[00:56:51] **Carol:** I have a thing to tell you guys and then we can wrap up if you'd like.

[00:56:52] **Ben:** Yeah.

[00:56:54] **Carol:** All right.

[00:56:55] **Carol:** So we got dinged with these weird all of a sudden like 27 findings by security for code flaws.

[00:56:57] **Ben:** Mhm.

[00:57:03] **Carol:** These are things that seven of them are like a repo that's not even active M anymore that just needs to be flagged as archive because it's gone.

[00:57:03] **Tim:** Mhm.

[00:57:11] **Carol:** So like there were some things, but I was like, these are so silly.

[00:57:11] **Adam:** Mhm,

[00:57:13] **Carol:** But okay, fine.

[00:57:15] **Carol:** I could see it maybe being valid, but instead of me doing exactly what you said, which was trying to find time to go babysit an agent to go do it, uh, I explained to my supervisor how to do it and now he has went in and created all of these like code reviews.

[00:57:21] **Adam:** Mhm.

[00:57:24] **Tim:** Mhm.

[00:57:27] **Ben:** Mhm.

[00:57:34] **Carol:** Like his PRs are out there And he sent me every one of them and I went, yeah, that's exactly what you need to do.

[00:57:41] **Carol:** Merge it.

[00:57:41] **Carol:** Like the test passed.

[00:57:43] **Carol:** Uh, everything is right.

[00:57:44] **Carol:** I just didn't have time to sit and like have that conversation

[00:57:49] **Carol:** over and over about, go fix this one.

[00:57:49] **Ben:** Yo.

[00:57:51] **Carol:** Now go fix that one.

[00:57:52] **Carol:** Like I needed someone else to babysit the agent to get it done.

[00:57:55] **Carol:** So I literally have my supervisor doing that so I don't have to touch it.

[00:57:59] **Tim:** That's funny.

[00:57:59] **Adam:** Nice.

[00:58:00] **Carol:** Yeah.

[00:58:00] **Carol:** Yeah.

[00:58:01] **Ben:** Well, maybe.

[00:58:02] **Ben:** Maybe that's a triumph.

[00:58:03] **Ben:** Maybe that'll be a failure.

[00:58:03] **Carol:** I think it's a win.

[00:58:04] **Ben:** We'll see.

[00:58:05] **Adam:** Again.

[00:58:06] **Adam:** If they report back.

[00:58:06] **Carol:** We'll see in two weeks.

[00:58:07] **Tim:** Your supervisor's like, yeah, we don't need Carol anymore.

[00:58:07] **Carol:** Yeah.

[00:58:08] **Ben:** Sa.

[00:58:09] **Tim:** I got this.

[00:58:10] **Carol:** No.

[00:58:13] **Carol:** Mhm.

## [00:58:14] Patreon

[00:58:14] **Adam:** All right, well, then this episode of Working Code is brought to you by the original third space doomscrolling on the toilet

[00:58:21] **Tim:** Sa.

[00:58:21] **Adam:** and listeners like you.

[00:58:22] **Carol:** No.

[00:58:23] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:58:24] **Tim:** Mhm.

[00:58:29] **Adam:** Um, our patrons cover our recording, editing, and transcription costs.

[00:58:32] **Adam:** And we couldn't we couldn't do this every week without them.

[00:58:32] **Carol:** Mhm.

[00:58:34] **Adam:** Special thanks to our top patrons, Monte, Giancarlo, and Peter.

[00:58:37] **Adam:** We really tonight.

[00:58:38] **Adam:** We really appreciate you guys.

## [00:58:40] Thanks For Listening!

[00:58:40] **Adam:** we are gonna go record the after show, and it looks like we got some TV stuff we want to talk about.

[00:58:45] **Adam:** We.

[00:58:45] **Adam:** I gaffed earlier a couple of weeks ago and mentioned Ted Lasso, but it's finally close enough that we have the official trailer we can talk about now.

[00:58:47] **Carol:** Mhm.

[00:58:52] **Ben:** It is nigh.

[00:58:53] **Adam:** It is nigh.

[00:58:54] **Ben:** Oh, there's a trailer.

[00:58:54] **Adam:** Um, there's an official trailer.

[00:58:55] **Ben:** I haven't seen a trailer yet.

[00:58:56] **Tim:** Yeah.

[00:58:56] **Tim:** It's a trailer.

[00:58:56] **Adam:** It's like a teaser, right?

[00:58:57] **Adam:** It's just.

[00:58:57] **Ben:** Okay.

[00:58:58] **Adam:** It's a bunch of clips with some, you know, a few lines get said here and there, but mostly it's just clips.

[00:59:02] **Ben:** All right.

[00:59:03] **Ben:** Hm.

[00:59:03] **Ben:** All right.

[00:59:04] **Adam:** and we're gonna talk about some Star Trek stuff.

[00:59:07] **Adam:** And yeah, that's.

[00:59:07] **Carol:** Mhm.

[00:59:08] **Adam:** That's what the after show is about.

[00:59:09] **Adam:** Sometimes it's more code related stuff.

[00:59:11] **Adam:** Sometimes it's just fun people being people.

[00:59:13] **Adam:** if you want to help us out, you can go to patreon.com/workingcodepod.

[00:59:16] **Adam:** you throw us a few bucks, we will throw you a few after shows and, and, and all of our love.

[00:59:20] **Ben:** Mhm.

[00:59:21] **Tim:** And all our love.

[00:59:23] **Adam:** Uh, but anyway, that's gonna do it for us this week.

[00:59:25] **Adam:** We'll catch you again next week.

[00:59:26] **Adam:** And until then,

[00:59:27] **Tim:** And remember our favorite third space is you.

[00:59:31] **Tim:** Your heart matters.

[00:59:31] **Ben:** Yo, it's true though.

[00:59:32] **Adam:** It.

[00:59:33] **Tim:** It's you.
