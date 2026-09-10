---
title: "273: Ethical Lines and Career Crossroads - Listener Questions"
description: "This week the hosts answer listener questions on ethical lines, career pivots, and the future of software engineering."
date: 2026-09-10
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/41311ce1-9e8d-4709-bf00-cd9cca3749ea"></script>
<div class="redcirclePlayer-41311ce1-9e8d-4709-bf00-cd9cca3749ea"></div>

What would you do if your manager asked you to make the audit trail editable? Why would Carol rather be evil? And would you still want to be a software engineer in five years, or is it finally time to buy the ice cream truck? This week the hosts answer listener questions on ethical lines, career pivots, and the future of software engineering.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [starry-night](https://github.com/wooorm/starry-night) - the syntax highlighter behind Ben's new blog API.
- [DEF CON](https://defcon.org/) - the hacking conference behind the red-teaming and social-engineering discussion.
- [271: Slop Is the New Clean](https://workingcode.dev/episodes/271-slop-is-the-new-clean/) - the earlier discussion of Uncle Bob and Matt Pocock's interview that Ben revisits.

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/273-ethical-lines-and-career-crossroads-listener-questions.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** mhm.

[00:00:00] **Carol:** if you could pivot to a different specialty in tech, what would it be?

[00:00:03] **Carol:** I think I've told you guys before, I just want to be evil.

## [00:00:28] Intro

[00:00:28] **Adam:** Okay, here we go.

[00:00:28] **Adam:** It is show number 273.

[00:00:30] **Adam:** And on today's show we are going to take some listener questions.

[00:00:34] **Adam:** Questions.

[00:00:35] **Adam:** but first, as usual, let's start with our triumphs and fails.

[00:00:37] **Adam:** And Tim is not able to be with us this week.

[00:00:40] **Adam:** Uh, he is, uh, as far as I understand, at one of his glorious work planning retreats.

[00:00:40] **Carol:** Oh.

[00:00:45] **Adam:** So don't feel too bad for him.

[00:00:46] **Adam:** so Ben, I'm going to come to you first.

[00:00:48] **Adam:** What's going on, my dude?

## [00:00:50] Ben's Fail

[00:00:50] **Ben:** I am going to start us off with a bit of a failure, a little bit of a double edged sword right now.

[00:00:56] **Ben:** So I've mentioned several times on various podcasts recently that I've been working on this syntax highlighting API that's powered by Lambda function and just a, uh, quick backstory, uh, for years now I've been relying on GitHub's gist API essentially as a way to color code the code, the fenced code blocks on my blog.

[00:01:06] **Carol:** Mhm,

[00:01:18] **Adam:** Mm, mhm.

[00:01:18] **Ben:** Basically when I'm done authoring a blog post, I create a gist.

[00:01:22] **Ben:** I embed all the files, um, all the fenced code blocks as files in the gist.

[00:01:26] **Carol:** Mhm, mhm,

[00:01:27] **Ben:** And then when I go to render my blog I get the gist data and interpolate it into the blog rendering.

[00:01:33] **Ben:** It's.

[00:01:34] **Adam:** Wait, wait.

[00:01:35] **Adam:** So I want to make sure I understand correctly.

[00:01:37] **Adam:** You're creating a gist, a secret, private, gist whatever with your, with the code samples in it.

[00:01:39] **Ben:** Yeah,

[00:01:41] **Adam:** And then you are like what GitHub does with that is they create HTML that represents your code, but it's got like spans around all the different, what is the word?

[00:01:50] **Ben:** Yeah, yeah,

[00:01:51] **Adam:** Like tokens or whatever in it.

[00:01:52] **Adam:** Like your curly braces and

[00:01:54] **Ben:** Exactly like the entity encoding.

[00:01:55] **Adam:** et cetera.

[00:01:56] **Ben:** Like this is a, this is a function call, this is a string, that kind of stuff.

[00:01:56] **Adam:** Right.

[00:01:58] **Adam:** Okay, so you're, you,

[00:02:00] **Adam:** you're letting them do the work of encoding it so that it can be syntax highlighted and, and taking their HTML and CSS

[00:02:07] **Ben:** Exactly.

[00:02:08] **Ben:** And then uh, when I render my blog post I get the gist, I parse it using jsoup I extract the uh, the DOM that represents the fenced code block that they've now encoded, I rip it out of the gist and I replace it into my blog post rendering where I have my fenced code block And

[00:02:08] **Adam:** Okay.

[00:02:13] **Adam:** Thief.

[00:02:16] **Carol:** Mhm.

[00:02:28] **Adam:** And you do this at render time every time I request a post.

[00:02:31] **Adam:** Right?

[00:02:32] **Ben:** yes, but the, the, the whole.

[00:02:33] **Adam:** Oh really?

[00:02:34] **Ben:** No, no, it is.

[00:02:35] **Ben:** And that's one of the things I want to write.

[00:02:37] **Ben:** It gets cached.

[00:02:38] **Ben:** So it's not like I'm calling

[00:02:38] **Adam:** Okay.

[00:02:41] **Ben:** GitHub's, uh, API all the time.

[00:02:42] **Adam:** Mm mhm.

[00:02:43] **Ben:** Um, but it is a point of friction.

[00:02:45] **Ben:** But mostly the color

[00:02:47] **Adam:** But you like friction.

[00:02:49] **Adam:** Mhm.

[00:02:49] **Ben:** I like.

[00:02:49] **Ben:** Good friction.

[00:02:51] **Ben:** Um, m.

[00:02:51] **Carol:** Adam, let the guy talk.

[00:02:52] **Carol:** Come on.

[00:02:53] **Ben:** Mostly it's the thing that I have not liked for years is that it's really the one piece I think of my, my blog platform that I feel like I don't wholly own.

[00:03:03] **Ben:** And I'm dependent on GitHub's API for this.

[00:03:06] **Ben:** And it's not terrible.

[00:03:07] **Ben:** I mean I've been using it for years and it's, and it's mostly fine.

[00:03:08] **Carol:** Mhm.

[00:03:10] **Ben:** but they make breaking changes every now and then and then for a couple of hours I'll realize that my blog stopped rendering the fenced code blocks properly or they changed the name of some something or other, some class they're using and suddenly the, not the syntax highlighting part, but they also wrap it in this table that has line numbers and sometimes that just kind of goes wonky and I have to fix it.

[00:03:18] **Carol:** Sam,

[00:03:22] **Adam:** Sa.

[00:03:30] **Adam:** Mhm.

[00:03:31] **Ben:** Anyway, I'm trying to take ownership of the, of the syntax highlighting.

[00:03:37] **Ben:** So I've, I'm using something called starry-night which is also I think in part what GitHub uses and I uh, don't know how to use it.

[00:03:45] **Carol:** that sounded familiar.

[00:03:47] **Ben:** Yeah, yeah, like they use Pygments or.

[00:03:49] **Carol:** Hmm.

[00:03:50] **Ben:** No, I think starry-night might be an open source reimplementation of Pygments

[00:03:54] **Carol:** Okay.

[00:03:54] **Ben:** um, by this guy,

[00:03:54] **Adam:** M.

[00:03:54] **Adam:** I thought starry-night was like the theme, the colors.

[00:03:57] **Adam:** But anyway.

[00:03:58] **Ben:** something like that.

[00:03:58] **Ben:** I'm not exactly sure.

[00:04:00] **Ben:** But basically I'm using some open source projects to power this.

[00:04:04] **Ben:** But I'm having Claude Code build basically the whole thing.

[00:04:06] **Ben:** and the, the triumph is that not only does it work, but I'm actually fixing bugs in my local implementation in some of these grammars where I notice like oh, this, this token doesn't color code correctly.

[00:04:22] **Ben:** I asked Claude why is that and it says oh, because it's getting short circuited by this one uh, portion of the grammar.

[00:04:23] **Carol:** Mhm, mhm.

[00:04:25] **Adam:** Mhm.

[00:04:27] **Ben:** If you move this up and then I do these like monkey patching in my version to move some things around so that the color coding works properly.

[00:04:35] **Ben:** Um, so it's like, it's kind of exciting that I'm actually getting it to work and I'm going to start to try to tease it into my blog to replace the uh, GitHub stuff.

[00:04:45] **Adam:** Mhm.

[00:04:45] **Ben:** The failure here is, is that I'm like so far out over my skis in terms of technical capabilities that there's no way I can maintain this if I don't have AI to maintain it.

[00:04:56] **Adam:** Mhm.

[00:05:01] **Adam:** I love that metaphor being out over your skis.

[00:05:02] **Ben:** Uh, being out of your skis.

[00:05:03] **Carol:** Yeah.

[00:05:04] **Ben:** Yeah,

[00:05:04] **Adam:** Yeah.

[00:05:05] **Adam:** Yeah.

[00:05:05] **Adam:** You hit one bump and you're just going to face plant.

[00:05:07] **Adam:** Yeah, I know that feeling all too well.

[00:05:07] **Ben:** yeah.

[00:05:07] **Ben:** And, and uh, I, I kind of get that that's just where we are as a people.

[00:05:09] **Carol:** Mhm,

[00:05:15] **Ben:** But it's really uncomfortable and I hate the fact that

[00:05:17] **Adam:** Mhm.

[00:05:20] **Ben:** it's, it's magical and it's also terrifying because what happens if AI becomes more expensive?

[00:05:27] **Ben:** You know, right now I'm basically using overflow from work.

[00:05:28] **Carol:** Mhm.

[00:05:31] **Ben:** I have Claude Code for work and I'm allowed to use it on personal stuff kind of as a learning, kind of as a.

[00:05:31] **Adam:** Mm.

[00:05:38] **Ben:** Just like this is a perk of the job and if that goes away, I have to ask myself,

[00:05:46] **Ben:** is this something that I want to maintain and pay for in the future?

[00:05:49] **Carol:** Yeah.

[00:05:50] **Ben:** And now do I have to get into a game where um, like just for, as a thought experiment maybe the complexity of having AI deal with these crazy TextMate grammars like it's literally going in and like debugging the regular expressions and, and bisecting the regular expression, the collections to see which things are causing evaluations to short circuit.

[00:05:54] **Carol:** Mhm,

[00:06:05] **Adam:** Mhm.

[00:06:11] **Carol:** Mhm, mhm,

[00:06:11] **Ben:** Like it's pretty complicated stuff.

[00:06:12] **Adam:** Mhm

[00:06:13] **Ben:** I mean it's far beyond anything I can really understand.

[00:06:15] **Adam:** sa.

[00:06:16] **Ben:** And like, does that require an expensive model?

[00:06:19] **Ben:** And am I going to have to pay for this expensive model every time I want to maintain it.

[00:06:23] **Ben:** If I don't have, you know, access to a uh, to a job that, that gives me that kind of a thing.

[00:06:29] **Ben:** And

[00:06:31] **Ben:** I don't know, I mean that's just where I am.

[00:06:32] **Ben:** That's the, the failure there is that it's, that's just a terrifying place to be.

[00:06:33] **Adam:** Mhm.

[00:06:36] **Ben:** Everything else in my little blog ecosystem I roughly understand.

[00:06:42] **Ben:** I might not necessarily be an expert, but like it's either something that I've already paid for or it's like something that there's open source projects and like I'm not really the one maintaining it anyway.

[00:06:53] **Carol:** Mhm.

[00:06:53] **Ben:** I'm just the one consuming the project.

[00:06:55] **Ben:** This is something I'm building and now I have to maintain it and it freaks me out a little bit.

[00:06:58] **Adam:** Mhm.

[00:06:58] **Adam:** Yeah.

[00:07:00] **Ben:** And uh, and it is a reminder to myself about.

[00:07:03] **Ben:** When I hear everyone talking in the world about all this crazy stuff that they're building,

[00:07:10] **Ben:** no one seems terrified about the fact that everything that they're building becomes a maintenance property.

[00:07:16] **Adam:** Burden.

[00:07:16] **Adam:** Mhm.

[00:07:16] **Ben:** And uh, yeah, and nobody, uh, nobody seems terrified.

[00:07:17] **Adam:** Yeah.

[00:07:17] **Carol:** We're all terrified.

[00:07:18] **Carol:** M.

[00:07:19] **Ben:** Everyone's talking about like, oh, I'm having the most fun I've ever had my entire life and all I can think about is like, is this going to come back to bite me

[00:07:29] **Ben:** anyway?

[00:07:29] **Carol:** Yeah.

[00:07:29] **Carol:** For me, it's not the writing.

[00:07:31] **Carol:** It.

[00:07:31] **Carol:** The writing.

[00:07:31] **Carol:** It isn't the scary part.

[00:07:33] **Carol:** Like, I've kind of been there a lot in my career where I go, oh, I don't understand this new way of doing something or like this new language I'm picking up.

[00:07:41] **Carol:** But over time I figure it out.

[00:07:43] **Carol:** And anything that gets created that I don't fully get right now, I treat it as any other new project I would be stepping into that's already been created, I'm going to have to have time to ramp up and learn it.

[00:07:55] **Carol:** Should AI not be available.

[00:07:57] **Adam:** Mhm.

[00:07:57] **Carol:** That doesn't change like, anything in my outlook on how it's being created.

[00:08:02] **Carol:** Like, I definitely want solid architecture and security to be considered, but other than that, I'm like, I figured out things for 15 years now.

[00:08:05] **Ben:** Mhm.

[00:08:09] **Carol:** I think I can keep doing it if this tool isn't here.

[00:08:12] **Carol:** The scary part for me is when AI is doing all the work behind the scenes.

[00:08:17] **Carol:** So if suddenly every request has to go through some type of AI function to do the work.

[00:08:18] **Adam:** Mhm.

[00:08:24] **Carol:** Now, if that cost skyrockets, how do you replace that?

[00:08:27] **Carol:** That's the piece that scares me more.

[00:08:27] **Ben:** Yeah,

[00:08:29] **Carol:** And right now it's just kind of a, uh, free for all.

[00:08:32] **Carol:** And it's, go figure it out, do it how you want, enjoy it.

[00:08:36] **Carol:** Until like, now we start paying more.

[00:08:38] **Carol:** And then suddenly we're like, oh, what does it actually cost to do this?

[00:08:39] **Adam:** Mhm.

[00:08:42] **Carol:** So I'm more scared of the behind the scenes than the code generation up front.

[00:08:48] **Ben:** Right there is.

[00:08:48] **Ben:** So, so the one saving grace is that because I'm generating code that I own, meaning like it's committed to my repositories, it's, it can't just arbitrarily go away.

[00:08:49] **Carol:** Mm, mhm.

[00:09:00] **Adam:** Mhm.

[00:09:02] **Carol:** Right.

[00:09:02] **Ben:** So even if AI went away, at least kind of the frozen version of the world is something I still have.

[00:09:02] **Carol:** Mhm.

[00:09:08] **Ben:** And, and unless no like bumping Node versions eventually breaks whatever I have, theoretically I've got a lot of time even if nothing else ever fixes or gets changed.

[00:09:19] **Carol:** Sam.

[00:09:19] **Carol:** Mhm.

[00:09:19] **Ben:** But what, there, what there was a phrase that, that kind of had uh, a lot of popularity maybe like two, three years ago where it was like,

[00:09:28] **Ben:** it was like code is,

[00:09:30] **Ben:** is harder to understand than it is to write.

[00:09:34] **Ben:** So if you're writing the most clever code you've ever thought of, there's no way you could possibly, by definition you'll never be able to maintain it.

[00:09:40] **Adam:** Yeah.

[00:09:42] **Ben:** And a little bit like that's how I feel like uh, my world is right now with this Lambda function The code in there is in my, you know, from my perspective because it's so foreign, it's incredibly clever.

[00:09:43] **Carol:** So true.

[00:09:46] **Adam:** Mhm.

[00:09:52] **Ben:** With all this monkey patching and, and doing this funky manipulating of the existing TextMate grammars I'm like, I, I already don't understand what they're doing.

[00:10:02] **Ben:** There's no way I'm going to understand it.

[00:10:03] **Ben:** If I have to do something technical, I mean just reading the code, I don't get it honestly.

[00:10:09] **Ben:** And if I ever have to update it like forget about it.

[00:10:12] **Ben:** So anyway, yeah,

[00:10:12] **Carol:** There's a rewrite.

[00:10:14] **Carol:** Rewrite.

[00:10:14] **Adam:** Yeah.

[00:10:15] **Adam:** I mean a slight preview to my triumph or fail is I've been feeling similarly.

[00:10:20] **Adam:** So we'll, we'll get there though.

[00:10:21] **Ben:** All right, well then I'll, I'll, I'll stop it there.

[00:10:24] **Ben:** Uh, that's my failure.

[00:10:25] **Ben:** Carol, welcome back.

[00:10:26] **Ben:** What do you got going on?

[00:10:28] **Carol:** Thank you.

[00:10:28] **Carol:** Thank you.

## [00:10:29] Carol's Triumph

[00:10:29] **Carol:** Yeah, I'm gonna go with a big giant win.

[00:10:31] **Carol:** Uh, unlike you slackers, I'm helping people learn AI and happy about it.

[00:10:37] **Ben:** Nicely done.

[00:10:37] **Carol:** Um, I've just been, I've talked about it a few times on the show, like the Catalyst program that I'm in and like the AI ambassadors for the agency.

[00:10:41] **Adam:** Mhm.

[00:10:45] **Carol:** And it's nice, um, to sit shoulder to shoulder with someone and help them and to immediately get that feedback and the reward.

[00:10:50] **Ben:** Mm, mhm,

[00:10:53] **Carol:** It's just, it's something I hadn't really experienced yet.

[00:10:54] **Ben:** mhm,

[00:10:56] **Carol:** Like, I've been on lots of calls, lots of, you know, screen sharing, lots of clicking through.

[00:11:02] **Carol:** But this past week I was able to sit next to people at their desk and show them and it's so silly, but it's like, click a button, install a skill now hit slash or just hit plus and your, um, skills loaded.

[00:11:16] **Carol:** Now tell it what to do.

[00:11:17] **Carol:** And to just see their immediate response to it and to see it saving them time and to see them m interacting with it.

[00:11:21] **Adam:** Mhm.

[00:11:25] **Carol:** It just gave me a lot of reward this past week and it made me feel like I'm doing a good job.

[00:11:25] **Ben:** Mhm.

[00:11:30] **Carol:** Even though what I feel like I'm doing is very small.

[00:11:34] **Carol:** It's that, uh, they haven't had the time to go do the small things to get the big win yet.

[00:11:39] **Carol:** So I'm very happy.

[00:11:41] **Carol:** I wasn't really feeling like going on this work trip and then once I was there, I was very happy I went because it, it definitely motivated me to keep doing what I'm doing.

[00:11:51] **Adam:** M.

[00:11:51] **Adam:** Nice.

[00:11:52] **Adam:** Sounds like they really appreciate the, the work that you're putting.

[00:11:52] **Ben:** Yeah.

[00:11:52] **Carol:** Yeah,

[00:11:56] **Carol:** they do.

[00:11:56] **Carol:** They absolutely do.

[00:11:57] **Carol:** I'm getting a lot of positive feedback.

[00:12:00] **Carol:** I get cornered now, like in the hall, cornered.

[00:12:03] **Carol:** Like, stop to say, like, oh, I saw this thing you're doing.

[00:12:06] **Carol:** Uh, can you show me how?

[00:12:08] **Carol:** Or the CFO pulled me in her office and she's like, I just want to thank you.

[00:12:11] **Carol:** Like, everything is going so much smoother and how can I help you?

[00:12:15] **Carol:** How can I make sure you have everything you need?

[00:12:15] **Ben:** Mhm.

[00:12:15] **Ben:** Nice.

[00:12:17] **Carol:** I'm like, just call my B.O.

[00:12:19] **Carol:** tell him I'm doing a good job.

[00:12:20] **Carol:** You know, like that's, is, that's what you can do.

[00:12:21] **Adam:** Yeah.

[00:12:23] **Carol:** Let him know I'm doing good because I like getting money at the end of the day.

[00:12:26] **Carol:** I mean, we all want our paycheck.

[00:12:27] **Adam:** Mhm.

[00:12:28] **Carol:** So yeah, it's, it's a good feeling.

[00:12:32] **Ben:** I'd be curious to know I haven't done like too much pair programming in my life but I was a many uh, years ago I was a teaching assistant in school and when you try to describe how a very deterministic system works and can answer questions about deterministic systems, you know, if someone's, if we're walking through with someone how variables work or what happens when you use a, an object or an array and like why would you choose one or the other?

[00:12:40] **Carol:** Same?

[00:12:41] **Adam:** Mhm.

[00:12:44] **Carol:** Mhm.

[00:12:59] **Ben:** I feel like I have a toolbox of answers that I can reach into because the understanding feels very concrete to me.

[00:13:02] **Adam:** Mhm.

[00:13:08] **Ben:** But when it comes to the AI stuff I assume that people will have a lot of questions where maybe your best responses, I don't know.

[00:13:17] **Ben:** Let's try it and see what happens.

[00:13:19] **Ben:** Are you finding like you have very deterministic kinds of questions and answers or is there a lot of open ended stuff?

[00:13:19] **Carol:** That is a lot.

[00:13:23] **Adam:** Mhm.

[00:13:26] **Carol:** The, the answers that are easy to give are, is it secure and am I allowed to use it?

[00:13:33] **Carol:** That's kind of the biggest question I get.

[00:13:35] **Carol:** Being in a government agency.

[00:13:36] **Ben:** Nice.

[00:13:36] **Carol:** That literally is the question.

[00:13:37] **Ben:** Yeah yeah.

[00:13:38] **Carol:** It's is it secure and can I ask it?

[00:13:40] **Carol:** I'm um, like, yes.

[00:13:42] **Carol:** Our rules are use the approved tools, use your approved account, and own what is delivered.

[00:13:43] **Adam:** Sa.

[00:13:44] **Adam:** Mhm.

[00:13:47] **Carol:** Like, Those are our 3 AI like rules for using, for using anything inside the organization.

[00:13:53] **Carol:** So I'm like, yes, you can.

[00:13:55] **Carol:** The other things are, let's try it.

[00:13:57] **Carol:** I do a lot of, let's try it.

[00:13:57] **Ben:** Mhm mhm.

[00:13:59] **Carol:** Like, even if I know what the outcome's going to be, I want them to experiment and I want them to feel empowered to ask the question question that they just asked me themselves.

[00:14:05] **Adam:** Mhm.

[00:14:10] **Carol:** I will even take their entire chat, like from Teams I will pull it out, paste it in and send them a screenshot and go, it is okay to ask exactly what you asked me in the same language.

[00:14:23] **Carol:** It's okay if you didn't spell a word right.

[00:14:25] **Carol:** It doesn't care.

[00:14:26] **Carol:** Like just ask it and let's see.

[00:14:26] **Ben:** Mhm.

[00:14:28] **Carol:** And if you feel like you're getting a bad answer, then we'll talk about it.

[00:14:31] **Carol:** Like let's figure out like why you aren't getting the outcome that you expected.

[00:14:35] **Carol:** But, but once I can get them having the conversation, usually they adopt a lot faster.

[00:14:40] **Adam:** So you have seemly, you seem, you seem to have found yourself in a place where.

[00:14:44] **Adam:** Let me prompt that for you.

[00:14:46] **Adam:** is actually like a legitimately appreciated response.

[00:14:46] **Carol:** Yeah,

[00:14:49] **Ben:** Mhm.

[00:14:50] **Carol:** it is, it is.

[00:14:50] **Ben:** It's a, it's a Carol as a service.

[00:14:51] **Carol:** I uh,

[00:14:53] **Adam:** Yeah,

[00:14:53] **Carol:** it's, it's so strange to see people who've had fear to even like open the apps on their computer.

[00:14:56] **Ben:** Sa.

[00:14:59] **Carol:** Multiple people this week had not Even clicked the ChatGPT app or the Claude app.

[00:15:00] **Ben:** Mhm.

[00:15:05] **Adam:** Well.

[00:15:05] **Carol:** The only thing they had done was open Microsoft's Copilot.

[00:15:09] **Carol:** And that's because it's built into every tool we have.

[00:15:11] **Carol:** You know, we're a Microsoft shop.

[00:15:12] **Adam:** Mhm.

[00:15:13] **Carol:** So if you open Word, Copilot's there.

[00:15:14] **Carol:** If you open Outlook, Copilot's there.

[00:15:16] **Carol:** So those are the only ones they had even used.

[00:15:19] **Carol:** So the thought of scheduling something to run every morning was beyond what they had comprehended they could do.

[00:15:21] **Ben:** Mhm.

[00:15:26] **Carol:** I was like, don't run this report.

[00:15:27] **Carol:** Just tell Claude to do it at 7 a.m.

[00:15:30] **Carol:** every day you tell to do it and it'll kick it off for you.

[00:15:31] **Adam:** Mm.

[00:15:33] **Carol:** And for them, that's outside of anything they thought they could do because they're, they're very manual.

[00:15:39] **Carol:** Like their processes have always been very manual.

[00:15:41] **Carol:** Very pulled data from one sheet to another and yeah,

[00:15:42] **Adam:** Right.

[00:15:45] **Ben:** It's so funny the idea of using a scheduled prompt as a way to run a.

[00:15:48] **Adam:** Mhm.

[00:15:50] **Carol:** Sam.

[00:15:52] **Carol:** Mhm,

[00:15:52] **Ben:** I don't mean to, I don't intentionally keep using the words deterministic and non deterministic but, but to have something run daily that like if you squint is deterministic but you're using a very non deterministic harness to run it.

[00:16:07] **Ben:** This is something that I have a lot of struggle with.

[00:16:09] **Ben:** I will often ask Claude, hey, pull down the main branch and rebase it on it so that I make sure I have my up to date code and that's a very fuzzy way to ask the agent to do something that I know how to do, you know from, from Git.

[00:16:09] **Adam:** Mhm.

[00:16:19] **Carol:** Mhm.

[00:16:25] **Ben:** And

[00:16:26] **Ben:** uh, like I kind of like it but I also struggle with the

[00:16:30] **Adam:** Mhm.

[00:16:31] **Ben:** I feel la.

[00:16:33] **Carol:** Yeah, I'm the opposite.

[00:16:34] **Carol:** I do not let it uh, pull down any of my code.

[00:16:38] **Carol:** I don't know why.

[00:16:39] **Carol:** I enjoy working in the terminal.

[00:16:41] **Carol:** So for me I'm like, hold on, let me get this branch ready for you.

[00:16:45] **Carol:** And I love to just open Bash and do git co branch git fetch all like git prune and then check out new branch.

[00:16:51] **Adam:** Mhm.

[00:16:54] **Carol:** To me it's like my little piece of ownership.

[00:16:56] **Carol:** I don't want to give up.

[00:16:57] **Carol:** So I have my things too that uh, I enjoy.

[00:17:00] **Ben:** I understand.

[00:17:01] **Ben:** I had a moment where I tried to do an interactive rebase the other day which uh, I, which I'll often do if I have a bunch of like uh, why isn't this working?

[00:17:10] **Ben:** Working on it.

[00:17:11] **Carol:** Yeah.

[00:17:11] **Ben:** Uh, this should do it and I want to squash those down to one commit and I'll do an interactive rebase.

[00:17:16] **Carol:** Mhm,

[00:17:17] **Ben:** And I went to do it the other day and I, and I couldn't remember exactly how it worked.

[00:17:22] **Ben:** And I got to the thing where, where it gave me like, here's the six commits.

[00:17:26] **Ben:** So I just tried to squash all of them.

[00:17:28] **Ben:** And then it was like, oh no, you have to have at least one commit.

[00:17:30] **Ben:** And I was like, that's what I'm trying to do.

[00:17:32] **Ben:** What do you mean?

[00:17:34] **Ben:** Like, it was, it was the first time I felt like I was actually getting dumber.

[00:17:35] **Adam:** Yeah.

[00:17:38] **Adam:** Yeah.

[00:17:39] **Adam:** Well, that I, I've run into the same thing that, that particular thing is like you have to have the ones that you're marking squash get removed and they get like combined with the one that comes after them, I think.

[00:17:39] **Carol:** mhm.

[00:17:45] **Ben:** Yeah,

[00:17:47] **Adam:** And so you have to have something after that that is not squashed in the list.

[00:17:47] **Ben:** yeah, yeah, yeah.

[00:17:51] **Adam:** But yeah,

[00:17:51] **Ben:** But like, it's literally something I used to do constantly and then I haven't done it in months and atrophies, man.

[00:17:57] **Adam:** mhm.

[00:17:58] **Adam:** Well that, that Feeds right into me.

[00:18:01] **Ben:** Well then, uh.

[00:18:01] **Ben:** Or it's not my triumph and fail anymore.

[00:18:02] **Carol:** Well then let's go.

[00:18:02] **Carol:** What do you.

[00:18:03] **Adam:** Yeah, yeah, yeah.

[00:18:03] **Carol:** Yeah, I'm good.

[00:18:04] **Carol:** What do you got?

## [00:18:05] Adam's Fail

[00:18:05] **Adam:** Uh, so I'm gonna go with a fail, which is surprising nobody.

[00:18:08] **Adam:** I am, uh, definite if, you know, if you're listening to the show, you know exactly what I'm about to say.

[00:18:12] **Ben:** Mhm.

[00:18:13] **Adam:** I am definitely hopelessly addicted to LLMs.

[00:18:16] **Adam:** I, I, I have bounced back and forth a couple of times within the last week between

[00:18:22] **Adam:** being depressed about my addiction to LLMs and being like, this is amazing, and I'm so productive, and I'm, you know, I love it.

[00:18:26] **Carol:** Mhm.

[00:18:26] **Carol:** Yay.

[00:18:31] **Adam:** And, you know, honestly, I think, uh, those happy moments are,

[00:18:36] **Adam:** like, right after OpenAI does a quota reset.

[00:18:38] **Carol:** Mhm.

[00:18:39] **Adam:** And so I've got, like, 100% out ahead of me.

[00:18:42] **Adam:** Like,

[00:18:44] **Ben:** That's funny.

[00:18:44] **Adam:** um, but, uh, like, so, uh, uh, kind of a low moment recently was, Sean Corfield, listener of the show, past guest, uh, had said, like, I think I posted a screenshot of my quota reset.

[00:18:58] **Carol:** Sam?

[00:18:58] **Adam:** Like, because I happened to be sitting at the desk when it happened.

[00:19:00] **Adam:** I saw, like, the app that I used to monitor my quota.

[00:19:04] **Adam:** Like, there's a setting I have turned on that, like, covers my screen in confetti when a quota reset happens.

[00:19:09] **Ben:** That's funny.

[00:19:10] **Adam:** And so I happened to be sitting at the desk when it happened, and I saw the confetti.

[00:19:12] **Adam:** I was like, ooh.

[00:19:13] **Adam:** And I took a screenshot and shared it in our Discord.

[00:19:16] **Adam:** And Sean was like, yeah, this is, uh, why drug dealers give you the first one for free.

[00:19:16] **Carol:** Mhm,

[00:19:20] **Adam:** Like, you're not wrong, Sean.

[00:19:22] **Ben:** Yes.

[00:19:23] **Adam:** Uh, yeah.

[00:19:23] **Adam:** And so, like, the depressed moments, it's like, part of me wonders if I should take a month off, right?

[00:19:25] **Carol:** mhm.

[00:19:28] **Adam:** Like, just, just uh, my subscription and go back to the old way of, like, chiseling my code out of stone with a hammer and chisel.

[00:19:31] **Ben:** Mhm,

[00:19:37] **Adam:** Um, and just, like, to remind myself that I still have some ability here.

[00:19:43] **Adam:** It sounds like it would be a healthy, uh, exercise, and it also sounds like I would hate every minute of it.

[00:19:50] **Adam:** You know what I mean?

[00:19:50] **Carol:** Yeah,

[00:19:51] **Adam:** It's like eating your broccoli.

[00:19:53] **Adam:** Like, I don't really want to, but it's.

[00:19:54] **Adam:** I know it's good for me sort of thing.

[00:19:56] **Adam:** I don't, I'm very conflicted.

[00:19:58] **Ben:** Mhm,

[00:19:59] **Carol:** See for me I would be fine giving up the coding side of it if I was like, oh, I have a feature I need to develop and I'm just going to go write the code for it.

[00:20:07] **Adam:** Yeah.

[00:20:08] **Carol:** To me, that's fine.

[00:20:09] **Carol:** I don't want to give it up for all my other tasks.

[00:20:12] **Carol:** Like I never, like, you guys know me you know me, I hate writing stories.

[00:20:13] **Adam:** H.

[00:20:13] **Ben:** Mhm,

[00:20:18] **Carol:** Like, don't ask me to document anything about a tech story I'm working or any feature you want created because it's going to say do work, Dash Carol in repo and Mark done.

[00:20:30] **Carol:** Like it's not going to have any context to it.

[00:20:30] **Adam:** Right.

[00:20:32] **Carol:** I hate writing stories.

[00:20:33] **Carol:** It's like if you were to take away everything I use it for as like my assistant or like the things I hate doing, I would be very angry with you.

[00:20:34] **Ben:** Mhm,

[00:20:42] **Carol:** But for coding I would be fine.

[00:20:44] **Carol:** I'd be like, cool.

[00:20:45] **Carol:** You know what, I'll just get back to my roots, right?

[00:20:47] **Carol:** Like I need to type a little more.

[00:20:49] **Carol:** Like my fingers don't hurt as much as they used to, you know, like I don't spend quite as much time on the keyboard.

[00:20:55] **Adam:** Yeah.

[00:20:56] **Adam:** When I, when I fart, started to consider, uh,

[00:20:59] **Adam:** this, like, exercise of taking some time off of it and doing it the old way, I immediately started, like, coping and trying to, like, cheat my way out of it.

[00:21:02] **Carol:** M.

[00:21:07] **Adam:** I was like, okay, what?

[00:21:08] **Ben:** Mhm.

[00:21:08] **Adam:** I'll turn off the subscription LLM coding machine, but I'll keep the, like, the autocomplete I'll use that kind of AI, but not,

[00:21:16] **Adam:** not the Full generation agentic coding.

[00:21:16] **Ben:** There you go.

[00:21:19] **Carol:** You just go back to the original Copilot that we thought was like

[00:21:23] **Adam:** Right.

[00:21:24] **Carol:** the bee's knees, right?

[00:21:25] **Carol:** Where it was like, oh, I'm gonna hit, hit tab and it's gonna autocomplete a tag for me or it's gonna give me a suggested attribute.

[00:21:25] **Adam:** It was mind blowing three years ago.

[00:21:34] **Adam:** Yeah.

[00:21:34] **Carol:** Yes.

[00:21:35] **Adam:** You write a little comment and it writes your function for you.

[00:21:38] **Carol:** Mhm

[00:21:39] **Adam:** Yeah.

[00:21:40] **Ben:** There's a, um, there's an old movie called Trains, Planes and Automobiles.

[00:21:44] **Ben:** This may have come out before Carol was born.

[00:21:45] **Carol:** mhm

[00:21:45] **Adam:** Mhm.

[00:21:46] **Ben:** I'm not sure.

[00:21:47] **Carol:** Sa.

[00:21:48] **Adam:** Probably.

[00:21:48] **Ben:** It's, it's quite an old movie with uh, Martin and John Candy.

[00:21:52] **Ben:** And the premise, the premise is really not important, but Steve Martin is trying to get home for Thanksgiving and he's running late and he, he's in Chicago, I think, and he steps out into the street, he's trying to hail a cab and a guy hails a cab next to him and Steve Martin asks to get the cab.

[00:22:08] **Ben:** The guy's like, give you, I'll give you a cab for 100 bucks.

[00:22:12] **Ben:** And Steve, I was like, fine.

[00:22:13] **Ben:** I think I goes, well, anyone who would pay $100 for a cab would surely pay $200.

[00:22:19] **Adam:** Mhm.

[00:22:19] **Ben:** And uh, and I, when I think about the AI stuff again, because I am using the account that I have been granted access to for work, I'm not paying for it.

[00:22:24] **Carol:** Mhm.

[00:22:31] **Ben:** So the question then becomes, if I don't have that, what in this world am I willing to pay for?

[00:22:38] **Ben:** Um, I have a ChatGPT account, a, you know, free one, which I use as essentially a glorified Google, where I ask it, oh, you know, why is my dog making this coughing noise?

[00:22:41] **Adam:** Mm.

[00:22:44] **Carol:** Mhm

[00:22:48] **Ben:** Or, I don't know, like, is this mushroom safe for the dog to eat?

[00:22:51] **Ben:** That kind of stuff?

[00:22:53] **Ben:** Uh, I don't pay for it.

[00:22:54] **Ben:** And I can't imagine a world

[00:22:56] **Ben:** where a better Google is something I would pay for when Google is just giving me a better Google now at the top of its search results

[00:23:03] **Adam:** Right.

[00:23:03] **Adam:** It's built into Google Yeah.

[00:23:04] **Carol:** mhm.

[00:23:05] **Ben:** with the coding stuff, I would pay for It.

[00:23:08] **Ben:** I don't know how much I would pay for it.

[00:23:10] **Ben:** If you said I could do some amount of AI programing for $100 a month, I'd be like, all right, yeah, uh, I could see that that's, that's reasonable.

[00:23:19] **Ben:** But then like, if it went up to $300 a month, I'm like, I don't know.

[00:23:23] **Adam:** Yeah.

[00:23:24] **Ben:** That's more than I pay for basically anything except for the mortgage.

[00:23:28] **Adam:** Right.

[00:23:28] **Ben:** I'm um, like, is that, like, is that worth automating this code stuff?

[00:23:33] **Ben:** I, I don't know.

[00:23:33] **Ben:** I don't know where my, my, like the value has gone past what I'm paying for it now that I have the pain of having to pay for it.

[00:23:35] **Adam:** It's an interesting point,

[00:23:41] **Adam:** Right?

[00:23:42] **Carol:** So if um, if it were a tool that was uh, making you money.

[00:23:46] **Adam:** Mhm.

[00:23:46] **Carol:** So say if you were like Adam skydiving software, right?

[00:23:48] **Ben:** Mm,

[00:23:50] **Adam:** Sa.

[00:23:50] **Carol:** Like hopefully at some point, if it's not already, it will make money for him.

[00:23:55] **Carol:** At that point that's when I go, okay, now I'm willing to pay more because it's a cost for that to operate.

[00:24:01] **Carol:** But me still have time with my family because anything I'm doing on the side outside of work is to me a uh, cost that I'm taking away from the other part of my life I still want to live.

[00:24:05] **Adam:** Mhm.

[00:24:06] **Ben:** Yeah.

[00:24:06] **Ben:** Mhm.

[00:24:12] **Carol:** And that's how I justify any costs like that.

[00:24:14] **Ben:** Sa.

[00:24:15] **Carol:** It's what, what do I consider the time saved and what I'm going to be getting back with my family versus what I would have spent sitting at the computer doing something to make sure that was so profitable.

[00:24:22] **Ben:** Mhm.

[00:24:28] **Carol:** Mhm.

[00:24:28] **Adam:** Yeah.

[00:24:28] **Adam:** I think there's a number.

[00:24:29] **Adam:** I have a number.

[00:24:30] **Adam:** I don't know what it is.

[00:24:31] **Adam:** It's.

[00:24:32] **Adam:** I might be willing to pay 100 bucks a month even if I'm like, I'm not getting paid for anything from Jump Run yet.

[00:24:37] **Adam:** Uh, and even if I don't for the foreseeable future, I would probably be willing to pay 100 bucks a month.

[00:24:42] **Adam:** Like $1200 a year seems within reach more than that and I'm going to start to question it.

[00:24:48] **Adam:** So

[00:24:49] **Adam:** anyway, why don't we move on and answer some, some questions from our listeners.

[00:24:50] **Ben:** Yeah, it's in.

[00:24:51] **Ben:** Yeah, yeah, yeah, sorry, sorry.

[00:24:53] **Carol:** Uh, oh yeah.

## [00:24:54] Ethics and Audit Trails

[00:24:54] **Adam:** this first question comes from Sean.

[00:24:56] **Adam:** Sean writes.

[00:24:57] **Adam:** Dear Meat Proxies, I ran into an ethical coding dilemma today.

[00:24:59] **Ben:** Mhm,

[00:25:00] **Adam:** A A manager asked me to make the date created field editable in a system used for customer audits.

[00:25:03] **Carol:** Mhm.

[00:25:06] **Adam:** That could allow someone to alter the historical record.

[00:25:09] **Adam:** So what responsibility does a programmer have when asked to build something that might undermine an audit trail?

[00:25:15] **Adam:** It also raised some broader questions for me.

[00:25:16] **Adam:** Programmers can collect enormous amounts of information from users, but which data should we collect and store?

[00:25:22] **Adam:** Where should we draw that ethical line?

[00:25:24] **Adam:** And how long should data be kept before it's permanently deleted?

[00:25:27] **Ben:** Mhm, mhm,

[00:25:28] **Adam:** Holding Sean to my principles.

[00:25:30] **Adam:** Sean,

[00:25:31] **Carol:** Mhm mhm.

[00:25:32] **Adam:** uh, that's a.

[00:25:33] **Adam:** Oh man.

[00:25:34] **Adam:** So this question immediately makes me think back to a story my dad told me.

[00:25:39] **Adam:** So when I was growing up, um, my dad like when I was late, adolescent, you know, teenage, that sort of thing, my dad was in computers.

[00:25:47] **Adam:** But when I was really young my dad worked, you know, odd jobs.

[00:25:48] **Carol:** Sam.

[00:25:49] **Adam:** He was in construction, he worked at RadioShack for a while.

[00:25:52] **Adam:** He was in the Navy that sort of thing.

[00:25:53] **Adam:** And when he was in construction he liked to tell me this story that know his boss wanted him to sign off on some blueprint or some work log or something that he uh, knew for a fact, that my dad knew for a fact was not done correctly.

[00:25:57] **Ben:** Mhm,

[00:26:02] **Carol:** Mhm mhm.

[00:26:07] **Adam:** And he's like, I'm not.

[00:26:08] **Adam:** No, I refuse.

[00:26:09] **Adam:** You know, you have to have a line you won't cross.

[00:26:12] **Adam:** And, and this was like, you know, if I sign this and then the building falls over and people die, then I'm responsible and I'm not going to be, I'm not going to take the fall for somebody because they didn't want to do the, the work correctly.

[00:26:18] **Ben:** Mhm.

[00:26:23] **Adam:** Uh, I feel like that immediately

[00:26:26] **Adam:** is uh, that's the thing that I immediately think of when asked this question.

[00:26:32] **Ben:** It's a tough one.

[00:26:33] **Ben:** And this is not like a cop out answer, but to some degree I like that things like GDPR and a lot of the regulations in California and other states now, uh, a little bit have like forced my hand, meaning that if I collect data then I have the friction of telling the user that I'm collecting that data or I don't want to do that friction.

[00:26:44] **Carol:** Mhm mhm.

[00:26:47] **Adam:** Mhm,

[00:26:58] **Ben:** And so that forces me to say like, uh, I don't really need this data then.

[00:27:02] **Ben:** Whereas in a world where I didn't have to have any of these, legal requirements that I, that I adhere to or like, I'm sure SOC compliance from what I remember, has stuff like what you're storing and where it's stored and who has access to it.

[00:27:13] **Adam:** Mm, mhm.

[00:27:16] **Adam:** And how long you can store it.

[00:27:17] **Adam:** Yeah,

[00:27:17] **Ben:** Yeah, like if there's some sort of legal requirement that just sort of m makes that decision for you, I kind of, I kind of just let that happen or I let that influence the way that I implement stuff.

[00:27:26] **Adam:** Yeah.

[00:27:26] **Carol:** It's m easier, right?

[00:27:28] **Ben:** Yeah.

[00:27:29] **Carol:** Yeah.

[00:27:30] **Ben:** where it gets a little fuzzy for me, and this is not so much the ethical stuff, so much, uh, but in a lot of these things there's, there's like, well, you don't have to tell people as long as it's um, driving a fundamental part of how the application works.

[00:27:30] **Carol:** William.

[00:27:41] **Carol:** Mhm.

[00:27:44] **Adam:** Mhm.

[00:27:44] **Ben:** And I'm like, yeah, I feel like if you squint you can actually get a lot of, a lot of stuff in that umbrella.

[00:27:50] **Carol:** Sam.

[00:27:52] **Ben:** like I, I don't know, I, I think of IP addresses as, as a thing that like it goes into every log statement and all kinds of stuff so you can cross correlate, you know, potentially malicious activity.

[00:27:59] **Adam:** Mhm.

[00:28:01] **Carol:** Mhm.

[00:28:03] **Ben:** And you're like, well, if you're doing malicious Activity monitoring.

[00:28:08] **Ben:** That's a fundamental to how the application works, right?

[00:28:11] **Ben:** Uh, that's like the security and the safeguarding of the application.

[00:28:14] **Ben:** I shouldn't have to disclose then that I'm tracking people's IP addresses.

[00:28:18] **Ben:** That's just a fundamental part of how it works.

[00:28:21] **Ben:** You know, I think there's a lot of hand wavy stuff in there probably also

[00:28:25] **Adam:** Yeah.

[00:28:25] **Ben:** don't have, I don't have a grand unifying thought there.

[00:28:27] **Ben:** Sorry.

[00:28:28] **Carol:** I want to go back to the very first part of it.

[00:28:30] **Carol:** Like, let's just talk about the date created piece of it.

[00:28:33] **Ben:** Mhm.

[00:28:34] **Carol:** Like if, if I am giving user data that is being audited and something that my customers use for audit, I don't think that I would want them to be able to edit the date created field.

[00:28:43] **Ben:** Mhm.

[00:28:48] **Carol:** I would most likely have a second field that stores the actual date created field.

[00:28:54] **Carol:** And then when the user changed the date created field, I guess a new one and the new date created field.

[00:29:02] **Carol:** Right.

[00:29:02] **Carol:** Because I feel like that original date matters and you shouldn't be modifying anything that's being audited.

[00:29:04] **Ben:** Mhm.

[00:29:05] **Adam:** Mhm.

[00:29:09] **Carol:** Like that's the whole point of logs and the audits.

[00:29:11] **Adam:** Of audits.

[00:29:12] **Adam:** Yeah, I agree.

[00:29:12] **Carol:** Yeah.

[00:29:13] **Carol:** So I mean, if they're going to change it, you have to have change tracking on that record that tells you what they changed, when and how it changed, so you can get back to it.

[00:29:21] **Carol:** So I would be raising the same questions if someone asked that of me.

[00:29:25] **Ben:** Mhm.

[00:29:25] **Adam:** Yeah.

[00:29:25] **Adam:** I have another similar example and also kind of a more philosophical viewpoint on this.

[00:29:31] **Adam:** Like pure coding versus uh, impure coding.

[00:29:35] **Adam:** so the other example I can think of is like like so I've mentioned on the show in the past we have our own rolled ticketing system built into our application.

[00:29:43] **Ben:** Mhm.

[00:29:43] **Adam:** And one of the features of that is like if you are subscribed to a ticket, right.

[00:29:43] **Carol:** Mhm.

[00:29:47] **Adam:** If you've ever left a comment on it, or if you created it, or if you were tagged by somebody in that ticket, then anytime anybody does anything with that ticket, you get an email notification so that you can go look at it if you want.

[00:29:58] **Adam:** And the, the

[00:30:01] **Adam:** thought has come up multiple times over the years.

[00:30:03] **Adam:** Like it would be really nice if we could close this ticket without sending notifications.

[00:30:07] **Adam:** Kind of just like a sweep it under the rug.

[00:30:09] **Adam:** Like yeah, we've said it's deferred and now we just kind of want people to forget about the ticket.

[00:30:14] **Adam:** Like we're never gonna do it, but we don't want to send out notifications that say we have decided to never do your thing.

[00:30:21] **Adam:** And uh, yeah, like uh, it's so, it's so tough.

[00:30:21] **Carol:** So naughty.

[00:30:22] **Carol:** So naughty.

[00:30:24] **Carol:** Mhm.

[00:30:25] **Adam:** Like it's, it's one of these gray ethical things.

[00:30:27] **Adam:** Like it's not really doing anything wrong.

[00:30:29] **Adam:** But also like we're there, there's a little bit of like a, a contract or a guarantee of like this is the way the system works and you're asking me to change it and like it makes me a little uncomfortable.

[00:30:38] **Ben:** Mhm

[00:30:40] **Adam:** So that viewpoint, uh, thing I was talking about, I saw this in a LLM focused article about um, pure programming versus I think it was impure.

[00:30:43] **Ben:** mhm.

[00:30:44] **Carol:** Mhm, mhm.

[00:30:50] **Adam:** It might have been some other term I forget, but basically it was like there's two different ways to think about code.

[00:30:55] **Adam:** Like there's the uh, like if you're writing a framework like React, or if you're writing an open source project where you, you try to get the code perfect, right?

[00:31:05] **Adam:** Like you, you don't want to cut corners, you don't want technical debt, you don't want, you want it to be just right.

[00:31:08] **Ben:** Mm mhm.

[00:31:10] **Adam:** You want the documentation to be good, you want to the implementation to be elegant, not too clever, that sort of thing.

[00:31:15] **Adam:** Right?

[00:31:16] **Adam:** And then sort of the opposite side of that coin is not.

[00:31:19] **Adam:** Not something, uh, a product where the code is sort of the, uh, product.

[00:31:22] **Ben:** Mhm

[00:31:23] **Adam:** But, like, I'm writing code to get work done, right?

[00:31:26] **Adam:** I'm getting paid to write code to get stuff done for other people.

[00:31:30] **Adam:** And they don't care that there's no technical debt.

[00:31:32] **Adam:** They don't care that the code is elegant.

[00:31:33] **Ben:** sa.

[00:31:34] **Carol:** My.

[00:31:34] **Carol:** Mhm.

[00:31:34] **Adam:** They care that it does what they want, that they.

[00:31:37] **Adam:** They met the budget and the timeline.

[00:31:39] **Adam:** Right.

[00:31:40] **Adam:** And, so that's the, like, quote, unquote, impure, uh, way of thinking about code.

[00:31:42] **Ben:** Mhm.

[00:31:43] **Carol:** Sam.

[00:31:43] **Carol:** Mhm.

[00:31:45] **Adam:** And

[00:31:46] **Adam:** it just.

[00:31:48] **Adam:** The.

[00:31:48] **Adam:** The idea of being able to edit things like this.

[00:31:52] **Adam:** I think you have to decide which side it falls on.

[00:31:55] **Adam:** Like, uh, like we're talking about ethically.

[00:31:58] **Adam:** If this audit trail is important, then probably don't allow editing it.

[00:32:03] **Adam:** But at the end of the day, if it's just a log of some stuff that happened and it's 99.9% of the time editing it would be used for legitimately

[00:32:13] **Adam:** m.

[00:32:13] **Adam:** Good reasons, then maybe it's okay to do it.

[00:32:14] **Carol:** Mhm, mhm.

[00:32:19] **Ben:** Well, and I also wonder, Carol made me think about whether or not it's a semantic issue that people are running into in this case that Sean's running into, meaning that maybe they're editing the date created field because that's the only field they have to edit.

[00:32:34] **Ben:** But maybe if there was a when was this record created versus another field which is like, when did this action take place?

[00:32:43] **Ben:** Because you could imagine, let's say that I'm migrating records or I'm back filling records because, hey, I'm uh, you know, we just added the ability to audit the system, but now we have four years of data that we want to backfill.

[00:32:43] **Adam:** Hmm.

[00:32:43] **Carol:** Right?

[00:32:56] **Adam:** Right.

[00:32:57] **Ben:** So maybe the date that those records are created is different from the date that the action that you're backfilling took place.

[00:33:03] **Carol:** Mhm.

[00:33:04] **Adam:** Right.

[00:33:05] **Ben:** So maybe one possible answer here is he wants to edit the date created

[00:33:11] **Ben:** not because it's nefarious, but because that's a date that's rendered somewhere and he wants that date to be different, but he doesn't necessarily understand

[00:33:20] **Ben:** the implications

[00:33:22] **Adam:** Yeah.

[00:33:22] **Ben:** of, of changing that date.

[00:33:24] **Ben:** and maybe that's just because there's not enough flexibility.

[00:33:27] **Ben:** And I don't mean that in a diminutive.

[00:33:29] **Ben:** Diminutive like a poor planning way, like you just didn't realize you would need this type of separation of concerns and what that date.

[00:33:36] **Adam:** Right.

[00:33:37] **Adam:** Yeah, I agree.

[00:33:38] **Adam:** I think we've pretty much answered this question while we move on to the next one.

[00:33:39] **Carol:** Yep,

[00:33:41] **Carol:** Dear Humans in the Loop, if you could pivot to a different specialty in tech, what would it be?

## [00:33:41] Career Pivots Into Security

[00:33:41] **Ben:** mhm.

[00:33:46] **Carol:** By specialty, I mean things like system admin, InfoSec, data analyst, CIO management, etc.

[00:33:54] **Carol:** Yours in hypothesizing, Brian.

[00:33:59] **Adam:** That's, uh, a good question, Brian.

[00:33:59] **Carol:** I got a really good.

[00:34:00] **Adam:** I.

[00:34:00] **Adam:** Go ahead.

[00:34:02] **Carol:** No, I got mine.

[00:34:03] **Carol:** I have two.

[00:34:03] **Carol:** I think I've told you guys before, I just want to be evil.

[00:34:05] **Adam:** Uh, I'm

[00:34:09] **Adam:** I was gonna say I'm really interested in your answer, Carol, because you are.

[00:34:09] **Carol:** I just want to be evil.

[00:34:14] **Adam:** You still write code, but you're in more of a management leadership role than I think the rest of us.

[00:34:19] **Carol:** Yeah.

[00:34:20] **Adam:** I guess Tim's not here, but, uh, it's.

[00:34:20] **Ben:** There.

[00:34:21] **Adam:** It's interesting to see it, like, when you.

[00:34:22] **Ben:** Mhm.

[00:34:24] **Adam:** One of the.

[00:34:25] **Adam:** The options available to me is the position you have so to see.

[00:34:31] **Adam:** Like.

[00:34:32] **Adam:** Okay, once I get into that role, would my.

[00:34:34] **Adam:** My, uh.

[00:34:35] **Carol:** Would it change?

[00:34:36] **Adam:** Yeah, Would.

[00:34:36] **Adam:** Would my.

[00:34:37] **Carol:** Yeah.

[00:34:37] **Adam:** Would that change my mind?

[00:34:39] **Carol:** Well, just so you know, I.

[00:34:39] **Adam:** So you just want to be evil,

[00:34:41] **Carol:** Yeah, yeah, I absolutely want to be evil.

[00:34:43] **Carol:** Like, put me on the dark side of security, let me find everything you've done wrong, yell at you and move to the next problem.

[00:34:44] **Ben:** Mhm,

[00:34:52] **Carol:** Like, I just want to be the one that finds things it doesn't have to deal with, it doesn't have to fix, it doesn't have to explain why it was done wrong.

[00:34:55] **Ben:** Sa.

[00:34:59] **Adam:** Right?

[00:35:00] **Carol:** I just want to find it, poke a hole in it and say, hey, I burst your bubble.

[00:35:04] **Ben:** Mhm.

[00:35:05] **Carol:** Now you have to fix it because I've told you about it and I'm on to my next little like, adventure.

[00:35:11] **Carol:** To me, those people have the best jobs ever.

[00:35:11] **Adam:** You want to be a red teamer?

[00:35:15] **Carol:** Like, I know it's their job to keep things secure, right?

[00:35:18] **Carol:** Like if something falls through the cracks, they're in trouble too.

[00:35:21] **Carol:** But I always feel like they come in, they get to be like all fancy and show us all the tools they've used to find everything we've done wrong.

[00:35:29] **Carol:** And then they just hand me a ticket that says fix it and move on.

[00:35:33] **Adam:** Mm,

[00:35:33] **Carol:** So that's what I would want to do.

[00:35:36] **Ben:** I'm um, a little bit surprised.

[00:35:38] **Ben:** I feel like as a community we've now had one DEF CON.

[00:35:44] **Ben:** Is that the big security conference in Vegas?

[00:35:46] **Adam:** Yeah.

[00:35:46] **Adam:** M.

[00:35:46] **Adam:** DEF CON is a big, like, hacking security conference.

[00:35:47] **Carol:** Mhm.

[00:35:49] **Ben:** I feel like we've had one since the agentic programming has come out.

[00:35:49] **Adam:** Yeah.

[00:35:50] **Adam:** Cyber security.

[00:35:54] **Adam:** Oh, yeah.

[00:35:55] **Adam:** They.

[00:35:55] **Adam:** They do it every year.

[00:35:56] **Adam:** It's in Vegas.

[00:35:57] **Ben:** Uh, and I feel like I've heard very little about it.

[00:35:59] **Ben:** You know, usually I'll hear fun stories on various podcasts about oh, they hacked an ATM or people did this and that kind of fun stuff.

[00:36:00] **Adam:** You're.

[00:36:00] **Adam:** Then,

[00:36:08] **Ben:** I can't recall anybody talking about anything wild that happened at DEF CON this year or last year since the agentic dev.

[00:36:15] **Carol:** They're all trying to hack A.I.

[00:36:16] **Carol:** uh, it's not as fun as like

[00:36:18] **Adam:** I mean, stuff is still happening there.

[00:36:20] **Carol:** the elevator keys, right?

[00:36:22] **Carol:** Wasn't that there where they realized you could get the emergency key if you just ordered it online and you could take over any elevator you want?

[00:36:30] **Carol:** And they used to just sell this key online?

[00:36:31] **Ben:** That's Crazy.

[00:36:33] **Carol:** You could Just order it.

[00:36:34] **Adam:** Yeah, there's all kinds of stuff.

[00:36:35] **Carol:** Mhm.

[00:36:36] **Adam:** They have, uh, social, uh, engineering competitions at DEF CON every year.

[00:36:36] **Carol:** Mm.

[00:36:39] **Adam:** Right.

[00:36:40] **Adam:** You have to, like, you go up into this, like, it's like a phone booth on the stage so that it's blocking out the noise of the crowd.

[00:36:46] **Adam:** Uh, and so the person that you're talking to on the phone can't, uh, hear you.

[00:36:49] **Adam:** But basically, you have to, like, social engineer your way to access a system.

[00:36:49] **Ben:** M.

[00:36:52] **Adam:** Right.

[00:36:52] **Adam:** You have to, like, get on the phone.

[00:36:54] **Adam:** You can do whatever Research you want, you can, you know, you have access to a computer and stuff in there.

[00:36:54] **Ben:** That's awesome.

[00:36:57] **Adam:** You just.

[00:36:58] **Adam:** But you have to like gain access into a system via social engineering.

[00:37:01] **Adam:** Live on stage in front of people.

[00:37:03] **Adam:** It's wild.

[00:37:04] **Ben:** Yo.

[00:37:04] **Ben:** It's like a scene right out of Hackers.

[00:37:06] **Adam:** Yeah.

[00:37:06] **Carol:** Yeah.

[00:37:06] **Adam:** Uh, the other thing I was going to point out is a big thing at DEF CON every year is like puzzles.

[00:37:06] **Carol:** uh.

[00:37:08] **Ben:** Mhm.

[00:37:12] **Adam:** I don't know of a better way to describe them.

[00:37:14] **Adam:** They have these like big, uh, not encryption.

[00:37:16] **Adam:** They're just like weird cipher puzzles.

[00:37:19] **Adam:** Right.

[00:37:19] **Adam:** Like, uh, the last one was they gave you a photograph of a dress that had a bunch of beads on it.

[00:37:19] **Carol:** Mhm.

[00:37:26] **Adam:** Um, like, like beadwork, you know, decorative beadwork looking stuff.

[00:37:29] **Adam:** But it turned out that the beads were in like specific patterns and that was like a message encrypted.

[00:37:34] **Adam:** And like the key was one of the sections of the dress and the message was in another section on the dress.

[00:37:42] **Carol:** M.

[00:37:42] **Carol:** Yeah,

[00:37:42] **Adam:** All you got was this picture and you had to figure it out.

[00:37:45] **Adam:** And people were using LLMs to

[00:37:45] **Carol:** I.

[00:37:48] **Adam:** break these puzzles.

[00:37:49] **Carol:** Yeah, that's the thing, right?

[00:37:51] **Carol:** Like a lot of people are getting to the answers faster now because you don't require that special one person in your group that has the mindset for it.

[00:38:00] **Carol:** So now you do have tools that help you get there quicker.

[00:38:00] **Adam:** Mm mhm.

[00:38:03] **Carol:** But what about you?

[00:38:04] **Carol:** So I'm going to be evil.

[00:38:06] **Carol:** Just each is evil just in general.

[00:38:07] **Adam:** H.

[00:38:07] **Adam:** Uh, I think the thing that interests me the most is also infosec, which is, I mean it's kind of what you're talking about, Carol.

[00:38:09] **Ben:** Mhm.

[00:38:14] **Adam:** Like be on the red team, try to.

[00:38:15] **Carol:** Mhm mhm.

[00:38:16] **Adam:** Try to break stuff.

[00:38:17] **Adam:** Try to break into stuff.

[00:38:18] **Adam:** I, I do feel like I have a little bit of a penchant for that.

[00:38:22] **Adam:** I've told you guys in the past about our, the other side of our business where we go on site to these large events and we have technology that we run for the events and stuff.

[00:38:27] **Ben:** Mhm.

[00:38:30] **Adam:** And uh, one of the things that we do for some of the largest events that we run is we have these like small little handheld computers.

[00:38:38] **Adam:** It's like the size of a phone, but it's like the thickness of like half ish of a brick.

[00:38:43] **Carol:** Mhm.

[00:38:43] **Adam:** Right.

[00:38:43] **Adam:** Because it's, it's a phone, but it's got a full keyboard and it's got like a scanner, like a laser barcode scanner in the back of it and it's got all kinds of crazy stuff in it.

[00:38:52] **Adam:** and

[00:38:53] **Adam:** um, you know, we have a MDM on it to control the software and control the settings and MDM M Mobile Device Management.

[00:38:58] **Ben:** What?

[00:39:01] **Ben:** Oh, uh, this is like where you manage many devices at the same time.

[00:39:01] **Adam:** It's just, it's

[00:39:05] **Adam:** Right.

[00:39:05] **Adam:** So there are all the devices are registered with our group or whatever and then we can say, okay, here's the settings now flash all 400 devices and they all get updated and we don't.

[00:39:13] **Carol:** Like you can't install an app or anything on it.

[00:39:15] **Carol:** Like everything's very locked down.

[00:39:15] **Adam:** Right.

[00:39:16] **Adam:** You can't browse Facebook on it because we have the settings locked down, that sort of thing.

[00:39:17] **Carol:** Yeah.

[00:39:19] **Carol:** Mm.

[00:39:20] **Adam:** And uh, the last Time I was at one of these events, Steve handed me one of them.

[00:39:24] **Adam:** He's like, all right, this is the latest, you know, setting.

[00:39:26] **Adam:** See if you can get into anything.

[00:39:28] **Adam:** And I handed it back to him in like two and a half minutes.

[00:39:30] **Adam:** I'm like, all right, here's what I did.

[00:39:32] **Adam:** I, I have maybe not quite root, but I definitely have more access than you want me to have.

[00:39:36] **Adam:** Like, here you go, here's what I did.

[00:39:37] **Carol:** Yeah,

[00:39:38] **Adam:** And it's just fun to try and break the rules.

[00:39:41] **Ben:** For whatever reason.

[00:39:42] **Ben:** My brain just, I feel like it doesn't work that way and I don't, I don't even like games that require too much strategy.

[00:39:49] **Ben:** I'm just, I feel like hacking is some sort of uh, concrete version of subclassing of strategy and I just, I can't, I'm not, I'm not a three dimensional chess kind of person.

[00:39:58] **Adam:** Mhm.

[00:39:59] **Carol:** It is.

[00:40:00] **Carol:** Absolutely.

[00:40:03] **Ben:** I, I need to do like one step at a time and I just have sort of faith that I'm going in the right direction.

[00:40:07] **Carol:** Mhm.

## [00:40:08] Management and Systems Administration

[00:40:08] **Adam:** I, I do have a second answer too though.

[00:40:10] **Ben:** Sa.

[00:40:10] **Adam:** Now I think about it a little bit more.

[00:40:12] **Adam:** You know, I said infosec and I do really enjoy that.

[00:40:15] **Adam:** But also I think that like, sort of management appeals to me.

[00:40:21] **Adam:** I have had some really good managers in my career and I've had some really bad ones.

[00:40:24] **Carol:** Same.

[00:40:24] **Adam:** And I.

[00:40:25] **Carol:** Mhm.

[00:40:25] **Adam:** So I know what it feels like to have a good manager and I would love to be able to do that for somebody else.

[00:40:28] **Ben:** M mhm.

[00:40:30] **Adam:** Um, and

[00:40:33] **Adam:** it just feels like a natural evolution for me.

[00:40:35] **Adam:** Right.

[00:40:36] **Adam:** I kind of am feeling maybe it's because of the LLMs, you know, kind of changing the way we work with code.

[00:40:42] **Adam:** It just doesn't feel

[00:40:44] **Adam:** as promising of a career as it used to.

[00:40:47] **Adam:** Does that make sense?

[00:40:49] **Carol:** It does.

[00:40:49] **Adam:** Um, and so like, I feel like the management side offers me more opportunities for the future.

[00:40:49] **Carol:** Yeah.

[00:40:56] **Ben:** Uh, I can relate to that.

[00:40:59] **Ben:** I don't think I've ever really wanted to be a manager, but when I hear about the stories people tell of times that they've had great managers, I always think to myself, I bet I could do that.

[00:41:08] **Adam:** Mhm,

[00:41:12] **Ben:** Like I keep this card on my desk from InVision Times, uh, customer empathy.

[00:41:12] **Carol:** Yeah.

[00:41:18] **Ben:** And I think about that in terms of product development.

[00:41:22] **Ben:** But there's no reason that another engineer couldn't be my customer if I were a manager.

[00:41:27] **Ben:** And like what are the, what are the dare to be great situations where I could shield them from terrible things or help build them up?

[00:41:27] **Adam:** Mhm.

[00:41:28] **Carol:** Agree.

[00:41:36] **Ben:** I, I don't know if I have the right tooling to do that, but there is something very attractive about being that person for sure.

[00:41:44] **Adam:** So is that what you're picking?

[00:41:46] **Ben:** I, I, well I, I didn't even consider the management until you just said it.

[00:41:50] **Ben:** The thing that I think I was leaning towards was system administration because to me the once you get below the code syntax, it's such a black box to me.

[00:42:03] **Adam:** M mhm,

[00:42:03] **Ben:** Um, I have, you know, the vaguest understanding of how Docker works.

[00:42:08] **Ben:** I have even less of an understanding about how Kubernetes works.

[00:42:09] **Carol:** Mhm.

[00:42:12] **Ben:** I have even less of an understanding about the machines that are running Kubernetes, you know, that Kubernetes is running on and the, and I'll say words that I don't understand, like the control plane that makes all that work together and Um, and I would love to just get a lot better at that stuff and kind of understand the lower level machinery of how it all works.

[00:42:16] **Adam:** Mhm.

[00:42:23] **Carol:** Mhm.

[00:42:34] **Adam:** So it sounds like what pulls you in that direction is the opportunity to learn.

[00:42:39] **Carol:** Mhm

[00:42:40] **Ben:** Yeah.

[00:42:40] **Ben:** And also just to compare and contrast to the red teaming stuff, it, it's stuff that I would have to learn but also feels very deterministic and it's not like me just pushing a bunch of random buttons to see what will break?

[00:42:57] **Ben:** You know, um, it's so.

[00:42:58] **Carol:** mhm.

[00:42:58] **Adam:** Yeah,

[00:43:00] **Ben:** It's like, it's in my wheelhouse of comfort in, in the kind of concreteness of it.

[00:43:06] **Ben:** But it is something that I know very little about.

[00:43:09] **Ben:** So I think it would be the.

[00:43:10] **Ben:** It would, it feels like the right type of challenge for the way that I see the world.

[00:43:16] **Carol:** Yeah.

[00:43:16] **Carol:** Whenever we deploy code, say something goes wrong.

[00:43:19] **Adam:** Mhm,

[00:43:19] **Carol:** I get on the phone with our DevOps team and our SAs.

[00:43:23] **Carol:** I'm like, hey, I push the button.

[00:43:25] **Carol:** After I push the button, it's outside of my knowledge.

[00:43:28] **Carol:** I can't tell you how it gets from me pushing the button to.

[00:43:32] **Carol:** It's on that machine.

[00:43:33] **Carol:** You all have wired that up.

[00:43:35] **Carol:** You know the network, you understand the firewall, you know what's at Akamai.

[00:43:39] **Carol:** Like you understand the layers in between it.

[00:43:42] **Carol:** I can tell you it didn't get to the end result.

[00:43:44] **Carol:** It's not on the machine.

[00:43:46] **Carol:** You have to help me figure out why.

[00:43:48] **Carol:** And it's the same thing.

[00:43:49] **Carol:** It's the uh, I don't know all of that middle ground.

[00:43:52] **Carol:** I know just enough to say some words that make them like go look in a place.

[00:43:52] **Ben:** Yeah,

[00:43:57] **Adam:** Mhm.

[00:43:58] **Carol:** But other than that,

[00:44:01] **Carol:** I'm going to stick in my wheelhouse and write code.

[00:44:04] **Ben:** Yeah, exactly.

[00:44:06] **Ben:** I know a couple of the right words to use when I'm having a conversation so that I think we can.

[00:44:06] **Carol:** Mhm.

[00:44:11] **Ben:** I can talk with people about it, but I don't necessarily understand everything that's being said.

[00:44:17] **Ben:** Sa.

[00:44:17] **Carol:** Adam, you mentioned being a manager, right.

[00:44:20] **Carol:** So I was just uh, in D.C.

[00:44:22] **Carol:** and my manager was there, my supervisor was there and he mentioned to me that he's reading a new book to help make our one on ones more productive and so that he can have more follow through and so he can like be a better leader.

[00:44:32] **Adam:** Okay,

[00:44:35] **Carol:** And I told him I was going to go home and put like four books on hold at the library because I used the Libby app for everything.

[00:44:42] **Adam:** Yeah,

[00:44:42] **Carol:** So then I could tell him how to be a better manager too.

[00:44:45] **Carol:** So we're going to teamwork this and make him better.

[00:44:49] **Adam:** That's funny.

[00:44:50] **Adam:** Did he tell you what the name of the book was that he's reading?

[00:44:51] **Ben:** Mhm.

[00:44:52] **Carol:** He did.

[00:44:52] **Carol:** And I was uh, trying to remember what it was.

[00:44:56] **Carol:** I will tell you next week.

[00:44:58] **Carol:** He's on vacation this week.

[00:44:59] **Adam:** Okay,

[00:44:59] **Carol:** Or I would, I would text him and ask, but.

[00:45:01] **Carol:** And I'll also add, um, the four I've added to mine because I really did add four because I've just wanted to get better at managing and Better at just leading people.

[00:45:05] **Adam:** Yeah,

[00:45:09] **Carol:** So I'll let you know what I'm looking at.

[00:45:11] **Adam:** Yeah, uh, I'm looking forward to that.

[00:45:13] **Carol:** All right, next one?

[00:45:14] **Adam:** Shall we move on to another question?

[00:45:15] **Carol:** Yeah, let's go.

[00:45:15] **Adam:** Yeah,

[00:45:16] **Ben:** All right.

## [00:45:17] Software Engineering in Five Years

[00:45:17] **Ben:** This is from uh, Cunningham.

[00:45:20] **Ben:** Dear Working Code AI is changing the activities and responsibilities of SWE which I assume is software engineer.

[00:45:28] **Ben:** Uh, do you think you'll still want a software engineering role in five years?

[00:45:33] **Ben:** Staring into my crystal ball the other.

[00:45:36] **Ben:** Brian.

[00:45:38] **Ben:** Um, this is an interesting one because I think that we are all in a time of great change and great upheaval.

[00:45:39] **Carol:** What do you think, Ben?

[00:45:46] **Adam:** M mhm.

[00:45:47] **Ben:** Um, and I keep thinking back to what I enjoy most about this job historically, outside of the actual bits and bytes of writing the syntax, it has always been

[00:45:54] **Carol:** Mhm.

[00:46:01] **Ben:** talking to people about their problems and then coming up with solutions to their problems.

[00:46:07] **Ben:** And as long as that can continue to be part of this role, I think that I can find a way to

[00:46:15] **Ben:** make it joyous.

[00:46:15] **Carol:** Mhm.

[00:46:17] **Ben:** Um, but the thing is, is like,

[00:46:21] **Ben:** not like your whole team can't be the person necessarily who talks to the customers.

[00:46:26] **Adam:** Right.

[00:46:26] **Ben:** Uh, so I don't know how well that scales

[00:46:31] **Ben:** and

[00:46:33] **Ben:** I don't know, I don't know what that looks like.

[00:46:34] **Ben:** But I, but I do know if I can be in the path of communication and feel like I have a, uh, say in what gets done and how communication happens and directions that things move, I think I would be happy still.

[00:46:39] **Adam:** M sure.

[00:46:48] **Adam:** So I uh, I like this question because it's similar to the last question.

[00:46:52] **Adam:** Right.

[00:46:52] **Carol:** Mm, mhm, mhm,

[00:46:53] **Adam:** You had to pick a different specialty, but this one is like, do you still want to do software engineering in five years?

[00:46:57] **Adam:** So it leaves that on the table.

[00:46:58] **Adam:** And I think that like, like you said, Ben, if,

[00:47:05] **Adam:** If it met certain criteria.

[00:47:07] **Adam:** Yes, like almost exactly what you were saying, Ben.

[00:47:09] **Adam:** Like when M.

[00:47:09] **Adam:** I think about Jump Run, right.

[00:47:11] **Adam:** Like I haven't written any code for jump and months and months.

[00:47:13] **Carol:** Mhm.

[00:47:14] **Adam:** But I've written a lot of code for Jump Run recently.

[00:47:17] **Adam:** Right.

[00:47:17] **Adam:** I've had LLM, uh, write it and a lot of that has been hearing feedback from the customers and you know, trying to kind of think about how can I make their problem not a problem at all.

[00:47:17] **Ben:** Mhm,

[00:47:20] **Ben:** mhm,

[00:47:29] **Adam:** Right.

[00:47:30] **Adam:** How can I just, like, remove it so it doesn't.

[00:47:31] **Adam:** It's not even a thing that they have to think about.

[00:47:33] **Carol:** Sam?

[00:47:33] **Adam:** And, and that can be very rewarding and fulfilling to like, have somebody tell you you're a genius because you,

[00:47:40] **Carol:** Mhm.

[00:47:41] **Adam:** uh, make their life easier.

[00:47:42] **Adam:** But at the same time, there are.

[00:47:45] **Adam:** It's like every time stuff is on fire at work, I'm like, I should have bought an ice cream truck.

[00:47:50] **Ben:** Mhm,

[00:47:50] **Adam:** You know,

[00:47:52] **Carol:** Oh my goodness.

[00:47:53] **Carol:** I'm the opposite.

[00:47:53] **Adam:** just.

[00:47:54] **Carol:** When things are on fire, I'm like in my zone.

[00:47:57] **Carol:** I'm like, shit's at the fan, let's go.

[00:48:00] **Carol:** Like this is the part where I go, let's just problem solve.

[00:48:01] **Adam:** M.

[00:48:02] **Carol:** Let's problem solve.

[00:48:03] **Carol:** Let's get to the root of it.

[00:48:05] **Carol:** It's the feature work I don't like.

[00:48:07] **Carol:** It's the new development I enjoy the problem solving.

[00:48:08] **Ben:** Mhm,

[00:48:11] **Adam:** I think what's challenging about it right now is

[00:48:14] **Ben:** Sa.

[00:48:15] **Adam:** like, it's become sort of a technical writing job.

[00:48:18] **Adam:** Right.

[00:48:18] **Adam:** Like, the prompting, uh, is.

[00:48:19] **Carol:** Mhm.

[00:48:20] **Ben:** Mhm.

[00:48:20] **Carol:** Absolutely.

[00:48:21] **Adam:** Yeah.

[00:48:21] **Adam:** You, like, you have to describe the problem and you have to describe the constraints that you want to be kind of in context or in.

[00:48:29] **Adam:** In mind when the problem is getting solved.

[00:48:32] **Adam:** You have to do that in a way that the LLM is going to understand and interpret correctly.

[00:48:36] **Adam:** And that's, uh, still a pretty dark art, I think.

[00:48:41] **Adam:** And in five years, God, who knows what's going to happen?

[00:48:43] **Adam:** Right?

[00:48:43] **Adam:** Like, think about the last five years in 2021.

[00:48:47] **Adam:** God.

[00:48:48] **Carol:** Unless there's a burst.

[00:48:48] **Ben:** You know,

[00:48:50] **Ben:** going back to the several episodes ago when we talked about the interview with Robert Martin and Matt Pocock, and he brought up the analogy of, uh, if you're building a house and every change that you make to the house costs a dollar.

[00:48:55] **Carol:** Mhm,

[00:49:05] **Ben:** I think when we first talked about that, I was always imagining in that scenario me building a house for me.

[00:49:14] **Ben:** And like, here's the vision I have of the house.

[00:49:16] **Ben:** Build it.

[00:49:17] **Ben:** Oh no.

[00:49:17] **Ben:** But the, the basement over here with the foundations like this.

[00:49:20] **Ben:** Oh no, let's move the walls over here.

[00:49:22] **Ben:** And that feels very fluid and exciting because the picture of the house is in my Head

[00:49:28] **Adam:** Mm.

[00:49:29] **Carol:** Mhm.

[00:49:29] **Ben:** but in the context of software engineering is still exciting because I'm talking to a customer and helping them solve problems.

[00:49:34] **Adam:** Mhm,

[00:49:37] **Ben:** The vision of the house isn't in my head, it's in their head.

[00:49:41] **Carol:** Right.

[00:49:41] **Ben:** And even if a change costs a dollar, am I showing them a completely different house every time we get on a call to discuss the changes that have been made?

[00:49:49] **Ben:** And I feel like that has a very different feel now in that thought experiment.

[00:49:56] **Adam:** Mhm,

[00:49:56] **Ben:** And This is, this is where I think the the abilities of the AI and the realities of dealing with an organization have some conflict.

[00:50:07] **Ben:** As much as the AI moves very quickly, people don't.

[00:50:10] **Ben:** And just because someone has a vision and you can be like, oh, no problem, I'll build an entire application for you by tomorrow.

[00:50:13] **Adam:** Mhm.

[00:50:17] **Ben:** Like, when is that person gonna have time to review it?

[00:50:20] **Ben:** Or how do you get on a Zoom um, call and say let's work through this together?

[00:50:23] **Ben:** Or well, you asked me to change this button, but it looks like you completely rebuilt that UI Uh, that, like that doesn't seem

[00:50:28] **Carol:** Mhm.

[00:50:31] **Ben:** in accordance with the.

[00:50:33] **Ben:** I can now move with a hundred x productivity.

[00:50:36] **Ben:** 100 x productivity if you're building the vision in your own head.

[00:50:41] **Ben:** But what happens when you have to build the vision in someone else's head?

[00:50:44] **Adam:** M.

[00:50:44] **Adam:** Yeah, that's the dark art is understanding it and.

[00:50:45] **Ben:** I don't, uh, know,

[00:50:45] **Carol:** Definitely much harder.

[00:50:47] **Adam:** And explaining.

[00:50:49] **Ben:** But that's the fun stuff too.

[00:50:50] **Ben:** Like that, uh, you know, going back to the idea of like, do I still want to be a software engineer?

[00:50:53] **Ben:** Uh, uh, if I get to revel in the excitement of coming up with a solution and then presenting it and then proving that that solution works for the customer, if I can still do that,

[00:51:06] **Ben:** that's where, that's where the secret sauce is.

[00:51:08] **Ben:** M.

[00:51:09] **Carol:** So, um, I have a slightly different opinion.

[00:51:13] **Carol:** So I've been, yeah, I mean I've been doing this for 15 years.

[00:51:13] **Adam:** Okay,

[00:51:16] **Carol:** Right.

[00:51:16] **Carol:** Like, and I know you guys are like, oh, that's nothing.

[00:51:19] **Carol:** You know, we've been doing this for 40, you know,

[00:51:23] **Adam:** Ouch.

[00:51:23] **Adam:** M.

[00:51:23] **Ben:** Whoa, whoa.

[00:51:23] **Adam:** How old do you think I am?

[00:51:23] **Ben:** Tim's not on the call.

[00:51:27] **Carol:** So I've been doing this for 15 years.

[00:51:28] **Carol:** A lot of people have invested into me and they have also invested into the space around me to make sure what I'm doing now is possible.

[00:51:34] **Ben:** Sa.

[00:51:36] **Adam:** Mhm.

[00:51:38] **Carol:** So I see myself in five years not being a software engineer, but one of those people that are making sure that software engineering is still a thing and that it can still be maintained and that, uh, there are people doing the work and that they have the support that they need to move forward board.

[00:51:53] **Adam:** Sa.

[00:51:56] **Carol:** So in 15 years they can transition into those type of roles.

[00:51:57] **Adam:** Mhm.

[00:52:00] **Carol:** So I don't see myself being an engineer in five years.

[00:52:04] **Carol:** I see myself supporting the industry more by helping with policy, helping with big tech changes, helping with how we, um, adopt AI in a way that doesn't have a negative impact on people and the products around us.

[00:52:04] **Ben:** Mhm.

[00:52:11] **Ben:** Mhm.

[00:52:22] **Carol:** So no, I don't see myself being a software engineer in five years.

[00:52:25] **Carol:** I think it'll be time for me to make a change in my career by then.

[00:52:30] **Adam:** M.

[00:52:30] **Adam:** Well, let us know which ballot you're on and I will go cast my vote for you.

[00:52:35] **Carol:** Thank you.

[00:52:35] **Carol:** Thank you.

[00:52:36] **Carol:** Yes, yes, I will run for mayor or something, you know, not at all.

[00:52:40] **Ben:** No, but that's really great.

[00:52:40] **Adam:** Yeah, city council or.

[00:52:42] **Adam:** Yeah,

[00:52:42] **Carol:** Yeah, yeah, all those things.

[00:52:43] **Ben:** I love,

[00:52:44] **Ben:** I love you wanting to pay it back and be supportive of other people.

[00:52:48] **Carol:** Mm, mhm.

[00:52:50] **Ben:** Uh, I always want to do that in theory, but I, I just find, I think I have a mixture of extreme self centeredness with uh, an underlying foundation of deep insecurity.

[00:53:02] **Ben:** And I think that the idea of helping other people, it's one of the things like how do you, how can you expect to love other people if you don't love yourself?

[00:53:12] **Ben:** I don't know how to support other people until I believe more deeply in my own convictions.

[00:53:17] **Adam:** You have to put on your own oxygen mask before you can help others.

[00:53:18] **Carol:** I,

[00:53:19] **Ben:** Yeah.

[00:53:20] **Carol:** yeah.

[00:53:21] **Carol:** But I don't get that from you at all.

[00:53:23] **Carol:** Ben, just so you know, you are, to me, you are the ideal teammate to have.

[00:53:29] **Carol:** You are willing to mentor and teach and you go out of your way to publicize like information that maybe nobody is consuming.

[00:53:29] **Adam:** Mhm,

[00:53:37] **Carol:** Right.

[00:53:38] **Carol:** Like you don't publicize like your blog for other people.

[00:53:41] **Carol:** You do it.

[00:53:42] **Adam:** Mhm.

[00:53:42] **Carol:** I know you're self centered, right.

[00:53:43] **Carol:** So you do it for Yourself.

[00:53:43] **Ben:** M.

[00:53:43] **Ben:** No, no.

[00:53:44] **Ben:** Well, yeah.

[00:53:44] **Ben:** Like, it's in a very safe way.

[00:53:45] **Carol:** But

[00:53:45] **Ben:** Everything's in a very safe way.

[00:53:46] **Carol:** yeah, but you put it out there, right?

[00:53:49] **Carol:** And to me, like, you're a great team, like a great teammate.

[00:53:51] **Carol:** Like you're someone that builds up a team and makes it better.

[00:53:55] **Ben:** I appreciate that.

[00:53:56] **Ben:** Thank you.

[00:53:56] **Carol:** Mhm.

[00:53:57] **Ben:** Try.

[00:53:58] **Ben:** uh, I, you know, it's, it's good to have a mixture of People on a team.

[00:54:02] **Ben:** I know that I can't be everything to everybody and I, and I appreciate that there are other people who can fill those vacuums that I leave behind.

[00:54:03] **Carol:** I agree.

[00:54:09] **Carol:** Yep.

[00:54:11] **Carol:** Agree on that.

[00:54:13] **Adam:** All right, so let's wrap it up there.

## [00:54:14] Patreon

[00:54:14] **Adam:** This episode of Working Code is brought to you by Ethics.

[00:54:17] **Adam:** They Exist.

[00:54:18] **Adam:** Sometimes, uh, listeners like you.

[00:54:19] **Ben:** Mhm,

[00:54:19] **Carol:** Mhm.

[00:54:21] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:54:28] **Adam:** you can go to patreon.com/workingcodepod.

[00:54:30] **Ben:** Mhm, mhm,

[00:54:30] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:54:35] **Adam:** Special thanks to our top patrons, Monte, Giancarlo, and Peter.

[00:54:38] **Adam:** We We really appreciate you guys.

## [00:54:40] Thanks For Listening!

[00:54:40] **Adam:** Uh, since we did questions, I want to throw this out there.

[00:54:40] **Carol:** Mhm

[00:54:43] **Adam:** Uh, if you have a question for us, you can get in touch with us a couple different ways.

[00:54:47] **Adam:** You can, go on our Discord.

[00:54:49] **Adam:** I'll probably create a New channel specifically for submitting questions for the show.

[00:54:50] **Ben:** Mhm,

[00:54:53] **Adam:** If Discord is your thing.

[00:54:54] **Adam:** If Discord is not your thing, you can email us at workingcodepod@gmail.com.

[00:54:58] **Adam:** We're going to go record the after show.

[00:55:00] **Adam:** You know how the spiel goes.

[00:55:01] **Ben:** Mhm,

[00:55:01] **Adam:** Mics stay on.

[00:55:02] **Adam:** We keep talking.

[00:55:03] **Adam:** I have no idea what we're gonna talk about.

[00:55:05] **Adam:** but, uh, actually I do know a couple of things.

[00:55:07] **Adam:** We're going to talk about yellow, uh, in AI generated images.

[00:55:11] **Adam:** I can't.

[00:55:12] **Adam:** It's like a dead giveaway now almost.

[00:55:14] **Carol:** let's talk about white text too.

[00:55:14] **Adam:** uh,

[00:55:17] **Adam:** yeah, okay, let's do that.

[00:55:19] **Adam:** Uh, but, uh, you know, after show, if you want access to that, you got to go to patreon.com/workingcodepod, throw a few dollars our way.

[00:55:19] **Ben:** Mhm.

[00:55:25] **Adam:** We'll give you a special link that you can use in your podcast player to get all the same episodes, but more, more longer episodes.

[00:55:28] **Carol:** Mhm.

[00:55:33] **Adam:** so, uh, we greatly appreciate it if you do that.

[00:55:36] **Adam:** that's going to do it for us this week.

[00:55:38] **Adam:** We'll catch you again next week.

[00:55:39] **Adam:** And until then.

[00:55:40] **Ben:** Remember folks, your heart matters, no questions asked.
