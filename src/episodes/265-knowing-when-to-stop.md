---
title: "265: Knowing When to Stop"
description: "Eighteen weeks ago Adam handed his decade-old ORM layer to an AI agent. This week he kills the whole refactor — and the feeling that comes isn't regret, it's relief."
date: 2026-07-02
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/E6e2e66a5-39c5-43b8-8ae1-bb0f2848e198"></script>
<div class="redcirclePlayer-E6e2e66a5-39c5-43b8-8ae1-bb0f2848e198"></div>

Eighteen weeks ago Adam handed his decade-old ORM layer to an AI agent. This week he kills the whole refactor — and the feeling that comes isn't regret, it's relief. Somewhere in the grind he realized he'd only ever weighed two options, push through or admit defeat, and both assumed he had to see it to the end. This week is about sunk cost — how being partway down a road can convince you that you owe it the rest of the way, and how freeing it is to decide you don't.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [249: 10 Years of Tech Debt](https://workingcode.dev/episodes/249-10-years-of-tech-debt/) — where Adam first handed the ORM layer to an agent

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/265-knowing-when-to-stop.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** uh, the real star of this whole process, I think has been git.

[00:00:03] **Adam:** can you imagine trying to take something on like this with subversion branches like that would have just been an absolute nightmare.

[00:00:07] **Carol:** It.

[00:00:08] **Ben:** so

[00:00:08] **Tim:** Subversion for you young listeners

[00:00:10] **Ben:** Okay,

[00:00:11] **Tim:** is pre git.

[00:00:12] **Tim:** Pre git.

[00:00:13] **Tim:** Version control was terrible.

[00:00:14] **Adam:** Yeah.

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go.

[00:00:35] **Adam:** It is show number 265.

[00:00:37] **Adam:** Got the whole gang back.

[00:00:38] **Adam:** Welcome, everybody.

[00:00:38] **Ben:** What?

[00:00:38] **Ben:** What?

[00:00:39] **Adam:** Thank you for allowing us to take last week off.

[00:00:39] **Tim:** Hey, hey.

[00:00:40] **Carol:** Moment.

[00:00:41] **Adam:** we had.

[00:00:42] **Adam:** What did we have?

[00:00:42] **Adam:** Uh, somebody was, uh, at CF Summit in Vegas.

[00:00:45] **Ben:** Yo, don't spoil my triumph.

[00:00:46] **Adam:** Was that you, Ben?

[00:00:47] **Adam:** Okay.

[00:00:47] **Adam:** Okay.

[00:00:48] **Adam:** But, you know, people were away doing things, and, uh, we just decided, you know, schedules being difficult, what they are this time of year.

[00:00:52] **Ben:** Mhm.

[00:00:52] **Tim:** Mhm mhm.

[00:00:55] **Adam:** We took a week off.

[00:00:56] **Adam:** So we're back.

[00:00:57] **Adam:** Anyway, uh, on today's show, we are going to discuss ORM stuff.

[00:01:01] **Adam:** Orm?

[00:01:02] **Adam:** Wtf?

[00:01:02] **Adam:** Lol.

[00:01:04] **Carol:** Mhm.

[00:01:04] **Adam:** but first, as usual, let's start with our triumphs and fails.

[00:01:07] **Adam:** And for no reason in particular, I'm going to start with Ben first.

## [00:01:10] Ben's Triumph

[00:01:10] **Adam:** What's going on, Sir?

[00:01:11] **Ben:** Kick it off with a triumph.

[00:01:13] **Ben:** Which is as you alluded to, I was with people, uh, out in Las Vegas in lovely dry 110 degree weather and went uh, to CF Summit I had a really nice time.

[00:01:17] **Carol:** Whoa.

[00:01:27] **Ben:** I'll say that I was very low energy and uh, I didn't socialize as maybe much as I would have liked to.

[00:01:32] **Carol:** Mhm.

[00:01:32] **Tim:** Mhm

[00:01:35] **Ben:** I didn't take that many photos.

[00:01:37] **Ben:** I sort of just drifted through it a little bit.

[00:01:41] **Ben:** But I.

[00:01:41] **Ben:** That's just been the kind of banner of my last year or so.

[00:01:45] **Adam:** that's the 2026 VI.

[00:01:45] **Ben:** Um, yeah, exactly.

[00:01:48] **Ben:** So I'm excited that despite all of that I went, I got on a plane, flew through Detroit, got to Las Vegas, met people, talked, shook hands, uh, attended some good conference talks and uh, I'm going to call that a win and I am also going to call this a triumph.

[00:01:52] **Carol:** Mhm.

[00:01:52] **Tim:** mhm.

[00:02:07] **Ben:** But it's like a questionable triumph and I need some advice here.

[00:02:10] **Ben:** So on the second day keynote, Ben Forta came and he did the second day keynote and everybody was, yeah, everybody was super excited for the younger listeners in the audience, for those young listeners that are new to ColdFusion Um, Ben Forta was basically the original developer evangelist for the product and he was synonymous with ColdFusion for a lot of our earlier career and then went on to do a whole bunch of other stuff.

[00:02:17] **Tim:** M.

[00:02:17] **Tim:** The man, the myth legend.

[00:02:34] **Carol:** Mhm.

[00:02:34] **Tim:** Mhm.

[00:02:39] **Ben:** And he gave this just kind of retrospective on his career and staying relevant, solving problems.

[00:02:46] **Ben:** And one other thing that he talked about, which I found very inspiring, was just the importance of showing up in public and helping people and putting things out there and not being afraid.

[00:02:54] **Carol:** Mhm.

[00:02:54] **Tim:** Mhm

[00:02:58] **Ben:** And that has kind of inspired me to

[00:03:03] **Ben:** play around with this idea of another book project.

[00:03:07] **Ben:** I've been kicking around this idea, I think probably for like two years now, maybe three years.

[00:03:11] **Ben:** There's a series of books called 97 Things Such and Such Programmers Should Know.

[00:03:15] **Carol:** Mhm.

[00:03:15] **Tim:** mhm.

[00:03:17] **Ben:** I think the first one was Java.

[00:03:18] **Ben:** It was like 97 Things Every Java Programmer Should Know And they've done it for a bunch of other languages.

[00:03:23] **Ben:** And it's an anthology type of project.

[00:03:26] **Ben:** So it's not one person writing the book, it's every chapter is written by another person.

[00:03:31] **Ben:** And they're not necessarily long chapters, you know, they can just be like short things that might not be obvious.

[00:03:31] **Adam:** Okay.

[00:03:35] **Carol:** Mhm.

[00:03:35] **Tim:** Mhm

[00:03:36] **Ben:** And I thought that would be a fun context to put together a ColdFusion book Like here's things that Every Program ColdFusion Programmer Should Know It's not necessarily a Learn ColdFusion book It's like here's all the weird stuff that you might not Realize, or here's the edge cases that you aren't considering.

[00:03:51] **Ben:** Or here's the interesting things you can do with the language.

[00:03:52] **Adam:** Sa.

[00:03:54] **Ben:** You know, kind of like a cookbook, but not so much outcome oriented.

[00:03:56] **Carol:** Mhm.

[00:03:56] **Tim:** mhm.

[00:03:58] **Ben:** Okay, so I'm inspired to give that another thought.

[00:04:03] **Ben:** Here's the conflict that I have that I need some guidance on.

[00:04:09] **Ben:** Do I host that book on my own personal website or do I create a standalone website for it?

[00:04:17] **Ben:** And

[00:04:17] **Adam:** Do you already own a useful domain name for this?

[00:04:18] **Carol:** Okay,

[00:04:19] **Ben:** I do not, but I have to imagine be relatively easy to get one.

[00:04:23] **Tim:** Can I sell you cfml.us?

[00:04:23] **Adam:** Mhm.

[00:04:28] **Ben:** That's funny that you have that.

[00:04:29] **Tim:** Because I own it.

[00:04:31] **Ben:** So, okay, here's my, here's my arguments in both directions.

[00:04:35] **Ben:** Uh, there's a very high likelihood that no one will ever want to participate in this project and I will just end up slowly writing chapters over time because no one cares about books anymore.

[00:04:38] **Carol:** sam.

[00:04:40] **Carol:** Mhm.

[00:04:45] **Ben:** So I.

[00:04:46] **Adam:** That's not.

[00:04:46] **Adam:** Because nobody cares about books anymore.

[00:04:54] **Tim:** M.

[00:04:55] **Tim:** We did you better.

[00:04:56] **Tim:** You broke them.

[00:04:56] **Tim:** You broke them before the main show.

[00:04:58] **Carol:** Mhm.

[00:04:59] **Ben:** Uh, said because people don't care about books anymore, I feel like I should host it on my own site because it'll ultimately be primarily me writing and, and I have all the infrastructure in place already, so what does it matter?

[00:05:03] **Tim:** Sa.

[00:05:06] **Adam:** Mhm.

[00:05:14] **Ben:** the argument for having its own site is that the intention would be that it is, would be a community contribution type of project and for other people to write.

[00:05:16] **Carol:** Mhm.

[00:05:20] **Tim:** Mhm.

[00:05:24] **Ben:** It feels a little

[00:05:26] **Ben:** cringy to host other people's writing on my personal site.

[00:05:31] **Ben:** But uh, you know, going back and forth it's like, yeah, but then if I'm mostly the one who writes it, I feel like I want it more attributed to my domain space, you know, like my personal brand.

[00:05:31] **Adam:** Mm, mhm.

[00:05:44] **Adam:** Yeah.

[00:05:45] **Ben:** So I don't know, I don't know what to do.

[00:05:48] **Tim:** I'd say both.

[00:05:49] **Adam:** So I would say,

[00:05:52] **Adam:** ah, a separate domain makes sense, but I wouldn't

[00:05:54] **Tim:** Mhm.

[00:05:57] **Adam:** go that route unless you get enough early interest.

[00:06:02] **Adam:** Like when we just, when we published the podcast, we didn't say we didn't publish like, okay, this is our first episode and here you go, and we'll be back next week.

[00:06:09] **Adam:** It was, we had I think, uh, like three or four episodes in the can and we knew we wanted to keep going before we publish the first episode.

[00:06:11] **Ben:** Mhm.

[00:06:12] **Tim:** Sa

[00:06:15] **Tim:** mhm.

[00:06:18] **Adam:** And I think you need to have at least five chapters written.

[00:06:23] **Adam:** You know, you don't want to, you don't want to launch this thing with a three paragraph essay and, and you know, okay, add yours because that's not going to drum up interest.

[00:06:28] **Carol:** Mhm.

[00:06:32] **Adam:** Right?

[00:06:33] **Adam:** You want five to ten interesting funny things.

[00:06:36] **Adam:** And, and if you can't get, if you can't get, you know,

[00:06:38] **Ben:** Funny.

[00:06:40] **Ben:** Why are you raising the bar right out of the, right out of the gate?

[00:06:43] **Tim:** If you can't get less, uh, 1, 200 things, you.

[00:06:46] **Carol:** Mhm.

[00:06:46] **Adam:** Uh, if you, if you can't get four to, what is it, nine other people to contribute other chapters, then you have to be willing to write the rest yourself.

[00:06:56] **Adam:** And at that point, yeah, put it on your own website.

[00:06:58] **Adam:** But like, if you get interest, go ahead.

[00:06:58] **Tim:** Well, uh, I'll tell you straight up.

[00:07:01] **Tim:** I will contribute chapters.

[00:07:02] **Ben:** What?

[00:07:03] **Ben:** All right, all right.

[00:07:03] **Tim:** I will contribute chapters.

[00:07:04] **Carol:** What

[00:07:05] **Carol:** are they going to be?

[00:07:06] **Carol:** A.I.

[00:07:06] **Carol:** uh, generated.

[00:07:10] **Carol:** Look at that grin.

[00:07:10] **Ben:** That's, that's uh, that's an implementation detail.

[00:07:10] **Adam:** He's just smiling,

[00:07:11] **Carol:** If you guys could see his grin.

[00:07:14] **Tim:** Yes.

[00:07:14] **Tim:** Yeah, let's not get.

[00:07:15] **Carol:** Mhm.

[00:07:15] **Tim:** This is a strategy meeting.

[00:07:16] **Tim:** We're not.

[00:07:16] **Tim:** We're not getting down to the tactics yet.

[00:07:19] **Ben:** All right, all right, all right.

[00:07:20] **Ben:** I'm, I'll start out as it being an independent thing.

[00:07:20] **Tim:** Mhm.

[00:07:23] **Ben:** So the, the, the way I'm designing it and you know, I've uh, mostly I'm just putting some infrastructure in place for fun each chapter.

[00:07:31] **Ben:** The idea is that you can spin up each chapter as its own set of docker containers.

[00:07:32] **Adam:** Sa.

[00:07:36] **Ben:** And one docker container would be the like.

[00:07:36] **Carol:** Mhm,

[00:07:39] **Ben:** If you want to write sample code, this is a place for you to write that sample code to make sure it actually works.

[00:07:40] **Tim:** Mhm mhm.

[00:07:44] **Ben:** And then the other docker container is a.

[00:07:46] **Adam:** Mhm.

[00:07:47] **Ben:** All it does is take the markdown that you're writing and basically parse it into HTML and kind of render it the way that the book would be rendered so you like, you don't have to do Anything.

[00:07:56] **Ben:** You basically just go into the chapter that you.

[00:07:59] **Ben:** There's going to be a chapter template folder, and then you copy and paste that.

[00:08:00] **Carol:** Mhm.

[00:08:02] **Ben:** And then you go in, you do Docker compose up and like, bloop, bloop, bloop.

[00:08:06] **Ben:** You have your, your content.

[00:08:08] **Adam:** And this is for me as the author or for me as the reader.

[00:08:10] **Ben:** Yes, yes, yes.

[00:08:11] **Ben:** For you as the author of a chapter,

[00:08:13] **Adam:** Why does it need to be anything more than just like a markdown file?

[00:08:16] **Ben:** I feel like, uh, if you're writing, you would want to have some code samples that demonstrate that the thing that you're writing actually works the way you think it does.

[00:08:17] **Carol:** Mhm.

[00:08:26] **Ben:** You don't have to do it.

[00:08:29] **Adam:** I think you're, you are very interested in building this from a fun, uh, fun to play with technology perspective and not so much from a book that somebody wants to read perspective.

[00:08:38] **Tim:** Content.

[00:08:38] **Carol:** Mhm.

[00:08:41] **Ben:** Well, no, uh, one would have to read that stuff.

[00:08:43] **Ben:** That's.

[00:08:43] **Ben:** That's all fades into the background.

[00:08:43] **Tim:** Sa.

[00:08:45] **Adam:** That's what I'm saying is, uh, I don't think that, that you're going to spend a lot of time on that Docker stuff.

[00:08:50] **Ben:** No, no, no, no.

[00:08:50] **Adam:** Uh, okay, uh, maybe I'm wrong, that's fine.

[00:08:50] **Ben:** I think it's that that, that to me is like that.

[00:08:53] **Ben:** That.

[00:08:56] **Adam:** But uh, just hearing the pitch, that's what I'm hearing is I want to play with Docker and come up with this complicated system for authors to write their chapters and have dynamic code execution and.

[00:09:02] **Tim:** Mhm.

[00:09:04] **Ben:** That was after the fact

[00:09:07] **Ben:** that that was after, like.

[00:09:08] **Ben:** Okay, I wanted to move forward.

[00:09:09] **Ben:** Originally, it was basically just going to be markdown file, like two markdown files, one for the chapter and one for the author bio.

[00:09:09] **Carol:** Mhm.

[00:09:16] **Ben:** But then I was like, how do people know that the thing that they're writing looks good?

[00:09:16] **Adam:** Mm mhm.

[00:09:20] **Ben:** Or like par.

[00:09:21] **Adam:** They if, listen, if they are writing CFML like they're contributing to a book about CFML they are well versed in.

[00:09:29] **Adam:** Oh crap, I have to go test the CFML code out.

[00:09:31] **Adam:** Where, where do I go to do that?

[00:09:33] **Adam:** How do I do that?

[00:09:33] **Adam:** They know how to run CFML code.

[00:09:36] **Ben:** I hear you, but I'm trying to make it easy.

[00:09:39] **Carol:** Mhm

[00:09:39] **Tim:** I.

[00:09:40] **Tim:** I would folk.

[00:09:40] **Adam:** Hey, you asked for feedback.

[00:09:41] **Tim:** I, I would.

[00:09:41] **Adam:** That's my feedback.

[00:09:41] **Ben:** All right, that's fair.

[00:09:42] **Tim:** I'd focus.

[00:09:42] **Tim:** I would focus on content and worry about the formatting later.

[00:09:45] **Ben:** All right.

[00:09:46] **Ben:** Okay.

[00:09:46] **Ben:** All right.

[00:09:47] **Ben:** Okay.

[00:09:47] **Ben:** Baby steps is what I'm hearing.

[00:09:49] **Ben:** I'm hearing baby steps.

[00:09:49] **Tim:** Baby steps, definitely.

[00:09:51] **Ben:** Okay.

[00:09:51] **Tim:** Content is king.

[00:09:52] **Tim:** Everything else is implementation details.

[00:09:54] **Adam:** You're gonna have a domain for us by the end of the episode, aren't?

[00:09:57] **Ben:** No, I can't, I can't.

[00:09:57] **Carol:** mhm.

[00:09:59] **Ben:** I'm not a good multitasker.

[00:10:01] **Ben:** All right, I'll call that a triumph then.

[00:10:02] **Ben:** Double triumph.

[00:10:03] **Ben:** And I will kick it over to Carol.

[00:10:05] **Ben:** What do you got going on?

## [00:10:05] Carol's Triumph

[00:10:05] **Tim:** Mhm.

[00:10:07] **Carol:** Yeah, I'm gonna go to the big wins here.

[00:10:09] **Carol:** we have a lot of moving parts going on right now at work and a lot of pieces that are just kind of, they're slowly falling in, but over time they've been very separated.

[00:10:14] **Adam:** Mhm.

[00:10:15] **Ben:** Sa.

[00:10:19] **Carol:** So like my boss got detailed to a new.

[00:10:21] **Carol:** A new role.

[00:10:23] **Carol:** I had a new boss come in and then now, uh, that boss actually isn't my boss.

[00:10:26] **Tim:** Mhm mhm.

[00:10:27] **Carol:** The other boss is now my boss.

[00:10:29] **Carol:** And people management has been interest seeing over the past several weeks, but that's kind of leveling out.

[00:10:35] **Carol:** And a lot of our projects that we were working on have felt very

[00:10:40] **Carol:** unorganized and just coming at us all at once.

[00:10:42] **Ben:** M.

[00:10:42] **Ben:** Mhm.

[00:10:43] **Carol:** But somehow with the people I'm working with and the team I have, we are making a lot of progress.

[00:10:50] **Carol:** And it feels like every day we end up in this very rewarding spot of going, things get accomplished, things get done.

[00:10:53] **Ben:** Mhm.

[00:10:58] **Carol:** And the, uh, pieces that moved off of the team with the other, like the shift in knowledge didn't really stop us as much as I expected it to.

[00:10:58] **Adam:** Sa.

[00:11:07] **Carol:** So I'm just really happy that right now things are moving and progress is being made.

[00:11:08] **Tim:** Mhm.

[00:11:12] **Carol:** And I don't feel like my hands are tied when we have a big like change in management or a change in staff.

[00:11:18] **Carol:** And that's not where we were a few years ago or even, you know, 18 months ago.

[00:11:22] **Carol:** It felt like a change kind of stopped everything.

[00:11:24] **Carol:** So.

[00:11:25] **Carol:** So things are a lot better and I'm happy about that.

[00:11:29] **Tim:** Until the next administration comes in.

[00:11:29] **Ben:** Yo.

[00:11:32] **Ben:** Mhm.

[00:11:32] **Carol:** We cross that bridge then.

[00:11:33] **Adam:** Well,

[00:11:35] **Adam:** yeah, I mean, I guess trending is a, uh, is the only thing you can look at on a day to day basis.

[00:11:35] **Tim:** Mhm.

[00:11:40] **Adam:** So I'm glad it's trending in the right direction for you.

[00:11:42] **Carol:** Thank you.

[00:11:43] **Carol:** Thank you.

[00:11:44] **Ben:** say plus.

[00:11:44] **Ben:** Uh, in my experience, having a sense of

[00:11:47] **Tim:** Mhm

[00:11:48] **Ben:** autonomy is not the right word when you're working for the government, but a sense that you can be somewhat self directed or self reliant, maybe, maybe more thing.

[00:11:57] **Adam:** Mhm,

[00:11:58] **Ben:** I think that is such a freeing feeling and, fights burnout at the very least.

[00:12:04] **Carol:** Oh, yeah, I agree.

[00:12:04] **Ben:** Yeah.

[00:12:05] **Carol:** And it helps right now that our CIO is very much pushing for our agency to be a tech force or a tech first agency.

[00:12:07] **Tim:** mhm.

[00:12:10] **Ben:** Mhm.

[00:12:14] **Carol:** So a lot of what we were doing as an afterthought is now the very first thought we have when we're thinking about what we're doing.

[00:12:17] **Adam:** mhm,

[00:12:21] **Ben:** Sa.

[00:12:21] **Carol:** So I feel like I'm constantly being challenged to improve our processes, to improve our technology stack, um, to push back on like our product timelines and push more on tech timelines of we have legacy apps that need to be rewritten.

[00:12:27] **Tim:** Mhm.

[00:12:35] **Carol:** So now go do it.

[00:12:36] **Carol:** Because the uh, finally we have like, we finally have the people in place that say it's important to have tech first.

[00:12:36] **Adam:** Mhm.

[00:12:42] **Carol:** It's not just about what's being delivered.

[00:12:44] **Carol:** And if it looks okay, that's fine.

[00:12:45] **Carol:** But if the tech isn't there behind it, that's a problem.

[00:12:49] **Carol:** that's me.

## [00:12:49] Tim's Triumph

[00:12:49] **Carol:** What about you, Tim?

[00:12:51] **Tim:** So last week was my 55th birthday,

[00:12:54] **Ben:** Ah, happy birthday.

[00:12:55] **Adam:** Happy birthday.

[00:12:55] **Carol:** Uh, happy late birthday.

[00:12:58] **Tim:** so I.

[00:12:59] **Tim:** So what I did.

[00:13:00] **Tim:** So I think I mentioned this before.

[00:13:02] **Tim:** There's some trauma associated with my birthday that I, uh.

[00:13:06] **Tim:** It tends to be a day where I just sit home and drink and get angry.

[00:13:07] **Carol:** Mhm.

[00:13:09] **Tim:** And I.

[00:13:10] **Ben:** Nice.

[00:13:10] **Tim:** My therapist.

[00:13:10] **Ben:** Nice.

[00:13:11] **Tim:** No, not nice.

[00:13:11] **Ben:** Mhm.

[00:13:11] **Tim:** My therapist.

[00:13:13] **Tim:** My therapist is like, you know, you need to create a new habit.

[00:13:15] **Tim:** I'm like, okay, fair enough.

[00:13:17] **Tim:** So I took off Thursday, Friday, and rented a car.

[00:13:21] **Tim:** And I told ChatGPT, like, here's what I'm into And it kind of knows my context already, my gardening and my cooking and, you know, food things and, you know, handcraft, you know, things where that take craftsmanship and intentionality.

[00:13:27] **Carol:** Mhm.

[00:13:31] **Ben:** Sa.

[00:13:31] **Ben:** Mhm.

[00:13:33] **Adam:** Mhm,

[00:13:36] **Tim:** And I said, all right, here's, uh, where I live.

[00:13:40] **Tim:** Tell me where to go to have an interesting experience that I normally wouldn't have.

[00:13:45] **Tim:** And I kind of told the places I already been.

[00:13:47] **Tim:** It suggested some places up in Macon.

[00:13:49] **Tim:** I'm like, I don't want to go to Macon.

[00:13:50] **Tim:** I want to go.

[00:13:50] **Tim:** I want to go on the, like, the rural southern path of South Georgia that the part of the world that no one ever really sees because nobody lives there.

[00:13:54] **Adam:** Mhm,

[00:14:00] **Tim:** Uh, dead serious.

[00:14:02] **Tim:** And so first it took me, like, some locals.

[00:14:04] **Tim:** It's this camellia garden.

[00:14:05] **Tim:** It's called Massee Lane Gardens It's in Fort Valley, which is actually.

[00:14:07] **Carol:** That's beautiful.

[00:14:09] **Tim:** Yeah, it's.

[00:14:09] **Tim:** My son has been.

[00:14:10] **Tim:** I've never been there and wrong time of year to go, but it was absolutely.

[00:14:14] **Tim:** Had a Japanese garden.

[00:14:15] **Tim:** They have thousands of different varieties.

[00:14:15] **Adam:** mhm,

[00:14:17] **Tim:** Camellias, which is a plant that in Georgia blooms in February.

[00:14:21] **Tim:** So you have, like, beautiful flowers in February.

[00:14:22] **Ben:** Mmm.

[00:14:23] **Tim:** Which is kind of unusual.

[00:14:24] **Tim:** So I plan to go back there.

[00:14:25] **Tim:** And so that was really cool.

[00:14:26] **Tim:** Then it sent me down to Marshallville, which is a little town.

[00:14:29] **Carol:** Mhm.

[00:14:30] **Tim:** And then I went to Andersonville, which is a Civil War, um, prison.

[00:14:35] **Tim:** So the POWs, the Yankees, they imprisoned them all in this huge stockade, this huge, massive.

[00:14:41] **Tim:** And it was awful.

[00:14:42] **Tim:** I mean, just to see the inhumanity that people could do to each other.

[00:14:46] **Ben:** H.

[00:14:46] **Ben:** Mhm.

[00:14:46] **Tim:** I mean basically they just put them in this huge, like the giant telephone pole size walls,

[00:14:49] **Carol:** Mhm.

[00:14:52] **Ben:** Mhm.

[00:14:54] **Tim:** perfectly packed in, two doors, one in, one out, a little creek floor flowing through the middle.

[00:14:55] **Adam:** Mhm.

[00:15:00] **Tim:** And they had, they called the deadline.

[00:15:02] **Tim:** So the deadline was this little barrier inside the walls about probably 20ft from the actual walls of the stockade.

[00:15:10] **Carol:** Mhm.

[00:15:12] **Tim:** And the guards, they didn't, they did nothing for them other than they just watched them and if they crossed the deadline, bang, shot them.

[00:15:20] **Ben:** Crazy.

[00:15:20] **Adam:** Wow.

[00:15:20] **Tim:** And you know, because there's this river, they were drinking the water and they were trying to, they would like do their business downstream.

[00:15:27] **Tim:** But the stockades were blocking the water flow, so it was backing up, the sewage backed up and people were like, I mean they had no cover.

[00:15:34] **Tim:** They were basically out.

[00:15:35] **Carol:** It's awful,

[00:15:36] **Tim:** They're outdoors in the winter, in the summer, with just a, basically like a T shirt sized piece of cloth to make a tent out of.

[00:15:42] **Ben:** Mhm.

[00:15:42] **Tim:** Yeah,

[00:15:43] **Adam:** So this is a triumph for you.

[00:15:45] **Tim:** well, it was, it's just, it's just interesting history.

[00:15:47] **Tim:** But they actually, I mean it.

[00:15:48] **Adam:** Yeah.

[00:15:50] **Tim:** There's only a couple pieces there.

[00:15:52] **Tim:** But what was beautiful, they have a, there is a, it's a veterans graveyard.

[00:15:53] **Carol:** Sam.

[00:15:55] **Tim:** So they have a graveyard of all the people, the POWs that died there, from the Civil War, thousands and thousands of graves and then even like modern graves.

[00:16:00] **Adam:** Mhm.

[00:16:04] **Tim:** So people who serve in the military, if they choose to, they can.

[00:16:07] **Tim:** There's, I guess it's an application process because they were five freshly new dug graves there, uh, of people in service.

[00:16:12] **Ben:** Mhm,

[00:16:14] **Tim:** And just, and it was beautifully manicured.

[00:16:18] **Tim:** Beautiful gardens, beautiful lawn.

[00:16:20] **Tim:** It's just, I mean it was stunning.

[00:16:21] **Tim:** But at the same time you're looking at these little, little tiny markers that represent

[00:16:26] **Carol:** Yeah,

[00:16:27] **Tim:** a human being's life.

[00:16:28] **Ben:** Mhm.

[00:16:28] **Tim:** It just kind of puts life in perspective.

[00:16:30] **Tim:** It's like, yeah, maybe my crap ain't going so great right now, but I ain't, I ain't under there yet.

[00:16:36] **Tim:** So there's still hope.

[00:16:36] **Carol:** Right.

[00:16:36] **Carol:** Mhm.

[00:16:36] **Adam:** Yep.

[00:16:38] **Tim:** And so

[00:16:38] **Adam:** It's still a good day to be above ground.

[00:16:39] **Tim:** it's definitely a good day to be above ground.

[00:16:41] **Tim:** And, and then it took me down to, Americus, Georgia.

[00:16:43] **Carol:** Sam.

[00:16:44] **Tim:** So Americus, Georgia is near where President Jimmy Carter grew up and he was raised in Plains, Georgia.

[00:16:47] **Ben:** Sa.

[00:16:50] **Tim:** And Americus is kind of like a train, ah, side city.

[00:16:50] **Carol:** Mhm.

[00:16:53] **Ben:** Mhm.

[00:16:54] **Tim:** And there was some really cool architecture there.

[00:16:56] **Tim:** But the thing that really got me so, like ChatGPT It's like as I would get closer and closer to the place, I would give more and more specific details about what I've seen and what's nearby.

[00:16:57] **Adam:** Mhm.

[00:17:04] **Tim:** And it's like, oh, there's this farm nearby called.

[00:17:08] **Tim:** I can't pronounce this, it's Greek word, but Koinonia Farm.

[00:17:13] **Tim:** And I don't know if you heard of Habitat for Humanity.

[00:17:16] **Ben:** Sure.

[00:17:16] **Carol:** Yeah.

[00:17:16] **Adam:** Oh yeah.

[00:17:17] **Carol:** Yeah.

[00:17:17] **Adam:** Um.

[00:17:17] **Tim:** Okay, so, yeah, he was, yeah, he was very involved with that.

[00:17:17] **Ben:** That's what Jimmy Carter did, I think, right?

[00:17:21] **Tim:** Habitat Humanity got started in America and it got started from this little farm back in the 1940s called Koinonia Farm Koinonia is a Greek word in the Bible which means fellowship or community.

[00:17:31] **Carol:** Mhm.

[00:17:33] **Tim:** And back in the 40s, you know, early civil rights era, this, uh, white family farm basically integrated their farm with the black local community.

[00:17:35] **Ben:** Mhm.

[00:17:38] **Adam:** Mhm.

[00:17:44] **Tim:** And they had a church.

[00:17:45] **Tim:** It was a very, it was a design Christian community.

[00:17:48] **Tim:** So they had worship together, they worked together on the farm, they sold things together, and they shared all the profits together.

[00:17:55] **Ben:** Mhm.

[00:17:56] **Tim:** And that was actually the start.

[00:17:58] **Tim:** That movement was the, was the.

[00:18:00] **Adam:** Communists.

[00:18:00] **Tim:** I know, right?

[00:18:01] **Tim:** That move.

[00:18:02] **Tim:** It was actually the start of Habitat for Humanity.

[00:18:06] **Tim:** But.

[00:18:06] **Carol:** Oh, that's cool.

[00:18:07] **Tim:** And I'll post a Link, there's a YouTube documentary that used to be on TV here, how it started.

[00:18:13] **Tim:** But like the KKK would like show up and like shoot machine guns all like over the entire farm.

[00:18:17] **Carol:** Mhm.

[00:18:17] **Adam:** Um.

[00:18:17] **Adam:** Wow.

[00:18:18] **Ben:** Jeez.

[00:18:18] **Adam:** Mhm.

[00:18:19] **Tim:** They didn't never killed anybody, um, directly doing that.

[00:18:22] **Tim:** They were just doing it to intimidate them.

[00:18:24] **Tim:** And so I went to that farm.

[00:18:25] **Tim:** And so, yeah, I mean, so I went to, like I said, St.

[00:18:28] **Tim:** Simons Island, which is a cool island and had, ah, seafood, but to distilleries, some.

[00:18:33] **Tim:** An olive farm.

[00:18:34] **Tim:** Like there's a few olive farms in South Georgia.

[00:18:37] **Tim:** So it was a fun.

[00:18:38] **Tim:** Because the worst part about planning a trip is planning the trip for me, but to just take all that pressure off and just.

[00:18:39] **Adam:** Mhm.

[00:18:41] **Ben:** Mhm.

[00:18:41] **Carol:** Yeah.

[00:18:44] **Tim:** I told ChatGPT, I'm like I want to go to some cool places that no one ever sees.

[00:18:48] **Tim:** And it was great.

[00:18:49] **Tim:** It was slow, stress low.

[00:18:52] **Tim:** I came home every night.

[00:18:54] **Tim:** I didn't want to get a hotel, so I came home every night, got up every morning and drove probably about a thousand miles on those two days.

[00:19:00] **Carol:** Wow.

[00:19:01] **Ben:** Mhm.

[00:19:01] **Tim:** So.

[00:19:02] **Tim:** And Toyota Camry's got amazing gas mileage.

[00:19:05] **Carol:** Oh yeah.

[00:19:06] **Carol:** Yeah.

[00:19:08] **Tim:** I drove 400 miles one day and it cost 27 to fill back up.

[00:19:11] **Tim:** Like my My Highlander would not.

[00:19:14] **Tim:** Yeah, it'd be like 70 bucks to fill up my Highlander for the same.

[00:19:17] **Adam:** Oh yeah,

[00:19:17] **Tim:** So.

[00:19:18] **Tim:** Yeah, so it was great.

[00:19:19] **Tim:** It was a good low stress.

[00:19:20] **Tim:** I think that's going to be my new, my new tradition for my birthdays going forward.

[00:19:26] **Ben:** That's awesome.

[00:19:27] **Adam:** I like that.

[00:19:27] **Ben:** Much, much better.

[00:19:27] **Carol:** That's really cool.

[00:19:29] **Carol:** Yeah.

[00:19:29] **Carol:** I'm glad you did.

[00:19:30] **Carol:** I'm glad you had a good time and got out of the house for your birthday.

[00:19:32] **Tim:** Yep.

[00:19:34] **Tim:** So that was me.

[00:19:34] **Ben:** Yo, but, uh, before we go on to Adam, just because that's going to roll into the show, I just want to do one quick callback.

[00:19:40] **Adam:** Dude, don't spoil my.

[00:19:42] **Ben:** Uh, this here, you can't see it if you're a listener, but this is a brown bottle.

[00:19:46] **Ben:** And this was

[00:19:47] **Adam:** Ben is holding up a jar of his diarrhea.

[00:19:50] **Ben:** this.

[00:19:51] **Ben:** Uh, Sean Odin brought a, uh, hot sauce to the conference with the intent to give it out to all of us.

[00:19:57] **Ben:** but since I was the Only one representing a podcast.

[00:20:00] **Ben:** He gave it to me and he said that he.

[00:20:01] **Ben:** I think he said he forgotten about it and it's been, uh, fermenting since the 100th episode, which.

[00:20:07] **Carol:** Uh, what?

[00:20:07] **Adam:** Oh no.

[00:20:07] **Tim:** Oh wow.

[00:20:08] **Adam:** Oh no.

[00:20:09] **Ben:** And so it was like, he was like, you probably shouldn't try it here because your, uh, your insides might end up on your outsides.

[00:20:17] **Ben:** But, uh, I have it.

[00:20:18] **Ben:** It got home safely.

[00:20:20] **Ben:** And will I ever try it?

[00:20:22] **Ben:** I have no idea, but I'll, uh, I'll see if I.

[00:20:24] **Adam:** Well, if we ever get together, we should split that up.

[00:20:27] **Ben:** Yeah.

[00:20:27] **Tim:** Yeah, for sure.

[00:20:27] **Adam:** I still have a little bit, a tiny little bit of, I think of the Adam and of the Carol.

[00:20:27] **Carol:** Yeah.

[00:20:30] **Carol:** Oh, they're so bad.

[00:20:32] **Adam:** I think I, I finished the Ben and the Tim.

[00:20:33] **Carol:** They're so bad.

[00:20:35] **Adam:** Um,

[00:20:35] **Carol:** have you opened it and smelt it?

[00:20:36] **Carol:** Like nothing?

[00:20:36] **Ben:** No, not even, not even gotten that far.

[00:20:38] **Tim:** Yeah, I think that would put you off tasting it for sure.

[00:20:42] **Carol:** Mhm.

[00:20:42] **Adam:** now I feel bad for calling it diarrhea.

[00:20:43] **Ben:** M.

[00:20:46] **Ben:** Well, I mean, your precognition.

[00:20:50] **Adam:** Yeah.

[00:20:51] **Tim:** Anyway, so that's, that was, that was my week.

[00:20:53] **Tim:** That's my triumph.

[00:20:54] **Tim:** How about you, Adam?

## [00:20:55] Adam's Triumph

[00:20:55] **Adam:** Okay, so, uh, we're at 3tr so far.

[00:20:57] **Adam:** So, um, I guess play the,

[00:21:00] **Adam:** uh.

[00:21:01] **Adam:** I'm gonna, I'm going with the triumph here too.

[00:21:03] **Ben:** Mhm.

[00:21:03] **Carol:** Yay.

[00:21:03] **Adam:** Um, uh, as I alluded to in the show topic, uh, we have tabled our ORM migration project.

[00:21:07] **Tim:** Mhm.

[00:21:10] **Adam:** Or I should say my ORM migration project, which, uh, if you're a regular listener to the show, you will have heard me mention.

[00:21:17] **Adam:** I don't even know how long, I don't want to know.

[00:21:20] **Adam:** When I started it, it was A long time ago, something I, I decided to take on because of advancements in AI and LLM stuff.

[00:21:25] **Tim:** Mhm

[00:21:29] **Adam:** And I was like, I kind of was looking for something to push it.

[00:21:30] **Carol:** Mhm.

[00:21:32] **Adam:** Right.

[00:21:32] **Adam:** Push it to the limits.

[00:21:33] **Adam:** How, how close to the sun can I fly?

[00:21:36] **Adam:** And um, yeah, um, push it.

[00:21:37] **Ben:** Something to push it real good.

[00:21:41] **Adam:** Uh, we got to stop there.

[00:21:42] **Adam:** I know that was a real good impression, but I don't think we can get the license for that.

[00:21:44] **Ben:** Mhm.

[00:21:46] **Tim:** mhm.

[00:21:47] **Adam:** Um, and basically I'm calling this a triumph.

[00:21:48] **Carol:** Mhm.

[00:21:50] **Adam:** We.

[00:21:50] **Adam:** I did a whole bunch of work, I spent a lot of tokens and my subscription stuff on getting this stuff done.

[00:21:56] **Adam:** I learned a lot in the process.

[00:21:57] **Adam:** But, um, we have decided to table it.

[00:22:00] **Ben:** Sa.

[00:22:00] **Adam:** which you might think, would be a failure.

[00:22:02] **Tim:** Mhm

[00:22:03] **Adam:** Right.

[00:22:03] **Adam:** But for me, the reason this is a triumph is because

[00:22:07] **Carol:** Mhm.

[00:22:08] **Adam:** when we came to the decision to table it, when it, when we finally were like, okay, yeah, that's the right decision, I felt relief.

[00:22:16] **Adam:** Um, and we can get into that in the show.

[00:22:18] **Adam:** But it's just, you know,

[00:22:21] **Adam:** sometimes when the decision

[00:22:22] **Tim:** mhm.

[00:22:23] **Adam:** is unintuitive, but it's the right decision and you, you get that special feeling like that.

[00:22:27] **Carol:** Mhm.

[00:22:30] **Adam:** That's just, it's.

[00:22:32] **Adam:** It's like the puzzle pieces clicking.

[00:22:34] **Ben:** Can I, can I jump in and just say that I think you're underselling the achievement in so much as since this project has been running, you have several times now said that it is coincidentally uncovering a bunch of bugs that you've then had to fix and move back into the main branch.

[00:22:43] **Tim:** Mhm

[00:22:48] **Carol:** Mhm.

[00:22:50] **Adam:** M.

[00:22:50] **Adam:** Yeah,

[00:22:53] **Adam:** yeah.

[00:22:53] **Adam:** There were something like, oh, 150 or so bugs that it found in the process in our production code.

[00:22:59] **Ben:** I mean, that's pretty good.

[00:23:00] **Ben:** That's pretty good.

[00:23:01] **Adam:** Yeah, yeah, no, that's one of the silver linings, to that.

[00:23:04] **Tim:** mhm.

[00:23:04] **Adam:** Other people were, like, looking at me like, are you sure you want to kill this, darling?

[00:23:07] **Carol:** Mhm.

[00:23:08] **Adam:** And I was like, you know, worst case scenario, if.

[00:23:12] **Adam:** If I do end up feeling bad about it, I will at least get a podcast episode out of it.

[00:23:16] **Ben:** There you, uh, go.

[00:23:16] **Adam:** And so here we are.

[00:23:18] **Adam:** But I don't feel bad about it, and I think that's kind of what we want to talk about today is just

[00:23:23] **Adam:** a little bit of, like, sunk cost fallacy stuff.

[00:23:23] **Tim:** Mhm

[00:23:25] **Adam:** And, you know, why.

[00:23:27] **Adam:** We can dig into more about, like, why we've decided to table it and why that was the right decision, but, yeah, you know, it's just.

[00:23:33] **Ben:** Mhm.

[00:23:34] **Adam:** It was the right decision.

[00:23:36] **Carol:** Before you kick it off, I would like to let you know I did ask Claude to review our episodes and let me know when you started this project.

[00:23:43] **Tim:** mhm.

[00:23:44] **Adam:** Okay.

[00:23:45] **Adam:** Oh, God.

[00:23:46] **Carol:** Turns out you talked about the rewrite.

[00:23:49] **Carol:** February 26, 2026.

[00:23:52] **Carol:** So about four months ago.

[00:23:53] **Ben:** M.

[00:23:53] **Ben:** All right.

[00:23:54] **Adam:** Okay, that's.

[00:23:54] **Ben:** Still, this calendar year,

[00:23:55] **Adam:** Yeah, yeah, yeah.

[00:23:56] **Adam:** I was expecting, uh, you said February, and I'm like, oh, God, February 25th.

[00:24:00] **Carol:** Roughly 18 weeks ago.

[00:24:03] **Adam:** Okay.

[00:24:03] **Adam:** Okay, that's.

[00:24:04] **Adam:** That's really not as bad as I thought, um, about tabling it.

## [00:24:06] Feature Flags and the Shared QA Environment

[00:24:06] **Ben:** Can you set the scene a little bit in so much as

[00:24:11] **Ben:** when did you first start having feelings?

[00:24:13] **Ben:** And then when were these feelings first brought up to the team?

[00:24:16] **Carol:** Oh yeah.

[00:24:17] **Tim:** And show me where they touched you.

[00:24:20] **Adam:** Um, well, so actually, it wasn't my idea, I'll say that.

[00:24:23] **Ben:** Mhm,

[00:24:23] **Adam:** Like, I was just.

[00:24:24] **Adam:** I was on the path.

[00:24:25] **Tim:** Mhm.

[00:24:25] **Adam:** I had the blinders on just making my way down this path.

[00:24:29] **Adam:** Um, and.

[00:24:30] **Adam:** And didn't really put too much thought into it.

[00:24:30] **Carol:** Mhm.

[00:24:32] **Adam:** The furthest it got was, I did.

[00:24:34] **Adam:** I built it all with feature flags, and so we had the code deployed in our QA branch with the feature flag off, meaning, effectively, in theory, zero, change.

[00:24:36] **Ben:** Mhm,

[00:24:42] **Tim:** Mhm

[00:24:46] **Adam:** Right.

[00:24:47] **Adam:** And the.

[00:24:48] **Adam:** The purpose of this period where it was in qa, in this configuration.

[00:24:48] **Carol:** Mhm.

[00:24:52] **Adam:** Um,

[00:24:54] **Adam:** and I guess this is a relevant point to mention.

[00:24:56] **Adam:** Our QA environment we share with our customers.

[00:24:56] **Ben:** mhm,

[00:24:59] **Adam:** So every customer has their own QA environment, and that's where they're welcome to do any training of their new employees or, testing of anything that they want to do that they don't want to be in the, like, permanent record of their production environment.

[00:25:02] **Tim:** mhm.

[00:25:08] **Carol:** Mhm.

[00:25:10] **Adam:** Because there's.

[00:25:11] **Adam:** There's a lot of stuff that we have that it's like.

[00:25:13] **Adam:** You can create an event, but you can't delete an event like that.

[00:25:16] **Adam:** It gets created.

[00:25:17] **Adam:** It gets.

[00:25:17] **Adam:** You can.

[00:25:18] **Adam:** You can totally.

[00:25:20] **Adam:** You know, if there's never been, uh, any registration or anything, like, you can just kind of ch.

[00:25:22] **Tim:** Mhm mhm.

[00:25:24] **Adam:** Change it.

[00:25:24] **Adam:** Right?

[00:25:24] **Adam:** So you can set up Adam's test event and then go, oh, I didn't want this in production.

[00:25:27] **Adam:** Oh, okay.

[00:25:28] **Adam:** This is now the happy hour that we're having next week.

[00:25:29] **Carol:** Mhm.

[00:25:30] **Adam:** You just change all the details, but you can't actually delete it.

[00:25:31] **Ben:** Mhm, mhm.

[00:25:33] **Adam:** So we do encourage them to those more test like activities or just want to see some how something works do that in qa.

[00:25:40] **Adam:** So we have this QA environment that we use for our testing and they use for their testing.

[00:25:44] **Adam:** And that's where we have the, had the ORM branch merged in and configured to be in theory, you know, big scare quotes around that.

[00:25:50] **Carol:** Mhm.

[00:25:54] **Adam:** No, um, changes.

[00:25:55] **Adam:** And of course there was lots of bugs that got introduced because there was like, you know, a bajillion lines of code that got modified.

[00:26:02] **Ben:** Right.

[00:26:02] **Adam:** Um, and so that was kind of the whole point of this period of having it in QA was to find hopefully all of those places, ah, and work through those issues.

[00:26:03] **Tim:** Mhm

[00:26:09] **Carol:** Mhm.

[00:26:12] **Adam:** And you know, the day that I deployed it, there was maybe six things that came up and then the next day there was like two and then the next week there was like two.

[00:26:18] **Ben:** Mhm.

[00:26:22] **Adam:** and so at least the most common hot pads through the application, you know, people were dripping on them and I fixed them and you know, every single one of them was like, paste the stack trace into Codex and it, and it fixes it, no problem.

[00:26:22] **Tim:** mhm.

[00:26:28] **Carol:** Mhm.

[00:26:36] **Adam:** Um, but

[00:26:36] **Ben:** Mhm,

[00:26:38] **Adam:** uh, being the time of year that it is, we have a couple of customers onboarding and I think all of them are, um, on short schedules.

[00:26:41] **Tim:** Mhm

[00:26:46] **Adam:** So for us an onboarding might last as much as like six months to a year.

[00:26:46] **Carol:** Mhm.

[00:26:50] **Adam:** Right, we'll sign the contract, we'll get your environment spun up, do some training, start to figure out the data integration back and forth and bidirectional data integration stuff.

[00:26:55] **Ben:** mhm.

[00:26:59] **Adam:** And then sometime between say six months and a year later, you'll do your first whatever stuff to, to start using it in production.

[00:27:01] **Tim:** mhm.

[00:27:07] **Carol:** Mhm.

[00:27:08] **Adam:** and we've got, I think, if I'm not mistaken, three customers.

[00:27:11] **Adam:** And the far horizon for them is like five, six months.

[00:27:15] **Adam:** And they're like trying to do the whole like, let's get everything up in three months, like, okay, well we could do that.

[00:27:20] **Adam:** You think you can do that?

[00:27:21] **Tim:** Mhm

[00:27:21] **Adam:** That's interesting.

[00:27:22] **Adam:** We'll see if you could live up to your own ambitions there.

[00:27:24] **Adam:** But, um, so it's just really not a good time for things to be unstable in production.

[00:27:25] **Carol:** Mhm.

[00:27:29] **Ben:** Mhm mhm.

[00:27:30] **Adam:** And because of all this, like, because they.

[00:27:33] **Adam:** So before they start in production, their only environment is qa and it would be a bad time to shake their confidence in us if QA is flaky because of these quote unquote, no OP changes.

[00:27:40] **Tim:** mhm.

[00:27:46] **Adam:** and so we, somebody on the team brought that up because of the onboarding stuff and said, is this the time to be doing this part of the process.

[00:27:46] **Carol:** Mhm.

## [00:27:55] The Onboarding Timing That Forced the Call

[00:27:55] **Ben:** Mhm.

[00:27:58] **Adam:** Should we consider going back to qa?

[00:28:01] **Adam:** That's a literal copy of Main.

[00:28:01] **Tim:** Mhm

[00:28:03] **Adam:** Um, and table this for later.

[00:28:06] **Adam:** And so that started the discussion.

[00:28:09] **Adam:** And I think the thing that was most interesting to me about it was like it was not even a possibility that I had considered, right?

[00:28:15] **Adam:** There's all this work I signed up for.

[00:28:17] **Adam:** I was doing the work.

[00:28:18] **Adam:** The thing about it is it wasn't a ton of work on a daily basis, right?

[00:28:20] **Tim:** mhm.

[00:28:22] **Adam:** It's like, rebase the branch on Main.

[00:28:24] **Adam:** Whatever bugs are found, do fix them.

[00:28:26] **Carol:** Mhm.

[00:28:27] **Adam:** Try to poke around and see if I can uh, any more bugs that are there.

[00:28:30] **Adam:** But it's not, not a ton of work.

[00:28:33] **Adam:** Um, but

[00:28:34] **Ben:** Mhm.

[00:28:34] **Adam:** the, the scary part is like, and I, you know, it's kind of jumbled in my head because it was like a half day discussion that we ended up having.

[00:28:40] **Tim:** Mhm

[00:28:42] **Adam:** But I kind of had this realization that is, this project is a plane and I'm building the plane as we're landing it, right?

[00:28:50] **Adam:** And either, stay focused and keep going and keep going and it's going to be terrifying right until the moment of touchdown.

[00:28:51] **Carol:** Mhm.

[00:28:57] **Tim:** mhm.

[00:28:59] **Adam:** And it's either going to touch down smoothly or it's going to crash into a ball of flames.

[00:29:02] **Adam:** Right?

[00:29:02] **Adam:** And those are the two outcomes.

[00:29:03] **Carol:** Mhm.

[00:29:04] **Adam:** We won't know until we get there.

[00:29:07] **Adam:** Good luck, have fun.

[00:29:08] **Adam:** Right?

[00:29:08] **Ben:** Don't die.

[00:29:09] **Adam:** Uh, and so when we had this discussion, I don't think I had ever considered the possibility that it was an option.

[00:29:12] **Ben:** Mhm

[00:29:15] **Tim:** Mhm

[00:29:19] **Adam:** Right?

[00:29:19] **Adam:** It's like one of those invisible third choices, right?

[00:29:22] **Adam:** You get A or B and when really, like C is actually also a choice too.

[00:29:26] **Adam:** And so I never considered, what if we just stop?

[00:29:28] **Adam:** What if we just table this for later or potentially forever.

[00:29:31] **Ben:** mhm.

[00:29:32] **Adam:** and the, having the discussion allowed me to think about it.

[00:29:35] **Tim:** mhm.

[00:29:37] **Adam:** And the more I thought about it, hypothetically just being like, okay, we're done with this, I can walk away from it.

[00:29:42] **Carol:** Mhm.

[00:29:42] **Adam:** The more I started to believe, like, actually that's probably the better idea.

[00:29:47] **Adam:** Like, yes, we fix the bugs.

[00:29:49] **Adam:** And we learned a lot about automating, AI stuff.

[00:29:52] **Adam:** And I learned a lot about our code base in this process.

[00:29:56] **Adam:** But

[00:29:56] **Tim:** Mhm.

[00:29:57] **Adam:** I do think it was too much to.

[00:29:59] **Adam:** Even with the, the AI tools that are available, it was too much to take on in one shot.

[00:30:04] **Ben:** And you had.

[00:30:06] **Ben:** Was this being run via, uh, a RALPH loop?

[00:30:10] **Ben:** I'm getting my, my time artifacts confused.

[00:30:12] **Adam:** It started, it started back in the days of the Ralph.

[00:30:14] **Adam:** Um, Ralph is so antiquated now.

[00:30:16] **Ben:** Uh,

[00:30:17] **Carol:** M.

[00:30:18] **Carol:** Not even valid.

[00:30:19] **Tim:** That is so, uh, six weeks ago.

[00:30:19] **Adam:** We're talking about 18 weeks ago, man.

[00:30:21] **Carol:** Yeah.

[00:30:21] **Adam:** Like,

[00:30:22] **Ben:** Because I, I feel like I remember you had, you had run in phases where the first phase was like, look through every controller and find every call to some sort of entity load.

[00:30:31] **Ben:** And then that came up with a document.

[00:30:31] **Carol:** Mhm.

[00:30:32] **Ben:** And then I feel like you did it like a second phase that did some kind of deeper investigation on that.

[00:30:35] **Tim:** Mhm

## [00:30:36] Controllers-First: Spidering the Codebase

[00:30:36] **Adam:** Yeah,

[00:30:38] **Adam:** you're, you're on the right track, but you've got a spider out.

[00:30:41] **Adam:** Uh, like every, every section of a sentence there can spider out, right?

[00:30:43] **Carol:** Mhm.

[00:30:45] **Ben:** Right, right,

[00:30:45] **Adam:** Like you just said entity load.

[00:30:46] **Adam:** And it's.

[00:30:47] **Adam:** But there's like 21 different ORM functions that you got to look for and.

[00:30:48] **Ben:** right, right, right, right, right.

[00:30:50] **Ben:** But you had come up with some sort of a master document.

[00:30:50] **Adam:** Yeah,

[00:30:53] **Ben:** I think they kind of attempted to outline at least like all of the ingresses.

[00:30:56] **Tim:** mhm.

[00:30:57] **Adam:** Sort of.

[00:30:59] **Adam:** So the initial process, you're right, I did start with controllers because I figured, like, that was a good way to have a very deterministic and very concrete, like, way of sectioning off the application.

[00:31:02] **Carol:** Mhm.

[00:31:11] **Adam:** So it's a a Framework One application, which is an MVC framework And so, the controller seemed like a pretty logical place to start because it gave me discrete chunks that are not too big but not too small.

[00:31:11] **Ben:** Mhm.

[00:31:11] **Tim:** Mhm

[00:31:15] **Carol:** Mhm.

[00:31:26] **Adam:** Right.

[00:31:26] **Adam:** The application is broken up into these modules, and modules have various controllers.

[00:31:27] **Ben:** Right.

[00:31:30] **Tim:** mhm.

[00:31:30] **Adam:** So like, event registration is a module we call EMS Event Management System but then within EMS, there's like, registration and there's setup and there's customer service.

[00:31:36] **Carol:** Mhm.

[00:31:41] **Adam:** Right.

[00:31:41] **Adam:** These are, you know, whatever.

[00:31:42] **Adam:** These are all different chunks, controllers of the, uh, the module.

[00:31:47] **Adam:** And so that felt like a good way to like group a bunch of stuff together that was related.

[00:31:50] **Tim:** Mhm

[00:31:52] **Adam:** Not too big but not too small.

[00:31:54] **Adam:** Does that make sense?

[00:31:56] **Adam:** and it's easy to identify what's a controller because it's just a CFC in a folder called Controllers.

[00:31:56] **Carol:** Mhm.

[00:32:00] **Adam:** Boom.

[00:32:00] **Adam:** M done.

[00:32:00] **Ben:** Sa.

[00:32:00] **Adam:** You can grep that you don't even need AI.

[00:32:03] **Adam:** Um, and so, I was able to do that and identified, I don't know what it was like 120, 150 controllers, something like that.

[00:32:04] **Ben:** Mhm.

[00:32:08] **Tim:** mhm.

[00:32:09] **Adam:** And then from there, you know, you, you spider out and say, okay, well give me all the methods that, that exist in the controller.

[00:32:14] **Carol:** Mhm.

[00:32:15] **Adam:** And then you work on each one of those individually and each one of those calls other methods.

[00:32:19] **Adam:** And so you're just spidering out the whole way, and identifying what it can find and what the interactions are.

## [00:32:26] Entity Sessions and the N+1 Query Massacre

[00:32:26] **Ben:** And just to refresh other people's memories here.

[00:32:27] **Tim:** Mhm mhm.

[00:32:30] **Ben:** Part of the complexity with migrating an ORM system is because

[00:32:34] **Carol:** Mhm.

[00:32:35] **Ben:** ORM is doing a lot of magic under the hood, not just with the way a record loads, but with the way a whole bunch of related records can load within the concept of like an entity session.

[00:32:47] **Ben:** And then sessions get flushed when database records get persisted.

[00:32:51] **Ben:** So just like for those listening, you know, and following along at home here, it's, it's not as simple as.

[00:32:55] **Carol:** Mhm.

[00:32:57] **Ben:** Well, let me just find the first controller call for entity load and replace it with a database call because that entity load had knock on effects to other things that were happening within the same orm session.

[00:33:01] **Adam:** Right,

[00:33:07] **Adam:** Right.

[00:33:09] **Adam:** Yeah, it goes up and down the stack.

[00:33:09] **Tim:** Mhm

[00:33:10] **Ben:** Yeah.

[00:33:11] **Adam:** And because I chose controllers, um, I'm starting from the middle, but yeah, so the, the controllers call services and those can call other services.

[00:33:16] **Carol:** Mhm.

[00:33:17] **Adam:** And at the end of the, you know, when you get to the leaf nodes, effectively you're interacting with the database or something external.

[00:33:23] **Adam:** Um, and, uh, Right, so you.

[00:33:23] **Ben:** Right.

[00:33:23] **Ben:** So it's not a smash and grab job kind of a situation.

[00:33:26] **Adam:** That's going up the stack, right.

[00:33:27] **Adam:** You're doing all the database access and whatnot.

[00:33:29] **Tim:** mhm.

[00:33:30] **Adam:** And then you've got to go down the stack from the controller.

[00:33:32] **Adam:** All the views and the partials and the custom tags, Um, so they have to deal with all this data that's coming from, uh, the controller.

[00:33:35] **Carol:** Mhm.

[00:33:36] **Ben:** Mhm

[00:33:37] **Tim:** Mhm

[00:33:41] **Adam:** And so you have to.

[00:33:43] **Adam:** I, uh, guess I

[00:33:47] **Adam:** mostly let the LLM M do what it wanted to do.

[00:33:49] **Adam:** I kind of gave it some freedom to decide the best path on any given view.

[00:33:53] **Adam:** I was like, sometimes it might be better to have a block at the top of the view that checks the feature flag and massages the incoming data.

[00:33:54] **Ben:** mhm.

[00:33:55] **Tim:** mhm.

[00:33:56] **Carol:** Mhm.

[00:34:01] **Adam:** So it's all.

[00:34:01] **Carol:** Mhm.

[00:34:02] **Adam:** So the view always gets one structure of data.

[00:34:05] **Adam:** Uh, and sometimes it's going to be query based and sometimes it's going to be RM entity based and it'll just switch at the top.

[00:34:11] **Adam:** How it pulls the data from the original source into some structure and then the view just uses that.

[00:34:15] **Ben:** Mhm.

[00:34:17] **Adam:** And sometimes it's like, yeah, but the view is like 9,000 lines long and it's two sections of eight lines each.

[00:34:22] **Carol:** Mhm.

[00:34:24] **Adam:** Like just, just add the switch right there in the middle view.

[00:34:27] **Adam:** That makes more sense.

## [00:34:28] Why ORM Sucks in CFML

[00:34:28] **Adam:** So,

[00:34:29] **Tim:** So can we back up a little bit and remind us why you wanted to do this in the first place?

[00:34:33] **Tim:** I, I mean I know why ORM sucks,

[00:34:35] **Adam:** Yeah,

[00:34:38] **Tim:** that's why.

[00:34:38] **Tim:** But what were your reason?

[00:34:41] **Adam:** I mean, I think you hit the nail on the head.

[00:34:43] **Carol:** Mhm.

[00:34:43] **Adam:** ORM sucks, and especially the way that it's implemented in CFML Um, I do think that there is a time and a place for orm.

[00:34:50] **Adam:** I don't think uh, of the reason is that we did not do a good job with it initially.

[00:34:53] **Ben:** Mhm

[00:34:54] **Adam:** We didn't understand it well enough.

[00:34:56] **Adam:** We were a younger team.

[00:34:58] **Adam:** and um, you know, we just, we made some mistakes and

[00:34:59] **Carol:** Mhm.

[00:35:02] **Adam:** we had gotten to a point with those mistakes where,

[00:35:06] **Adam:** they were at the bottom of a house of cards.

[00:35:08] **Adam:** Right, right.

[00:35:08] **Adam:** And so.

[00:35:08] **Tim:** I think uh, tell me if this is true for you.

[00:35:11] **Tim:** But because I mean I've been down the ORM route and I think the thing that sometimes sells it is is that you don't need to know SQL to do it right?

[00:35:12] **Ben:** mhm.

[00:35:21] **Tim:** You just, oh, you just write some objects and you're familiar with that.

[00:35:24] **Adam:** Yeah,

[00:35:24] **Tim:** If you're object like okay, I don't need to do SQL but you kind of do.

[00:35:28] **Adam:** Yeah,

[00:35:28] **Carol:** Mhm.

[00:35:28] **Tim:** You kind of really, really.

[00:35:30] **Tim:** And when you do need to know SQL, you built this entire house and the fact you don't get to see your SQL at all

[00:35:33] **Ben:** Mhm mhm.

[00:35:34] **Adam:** Right,

[00:35:37] **Tim:** and now.

[00:35:37] **Adam:** yeah.

[00:35:38] **Adam:** No, I mean, ORM is great when you're doing simple crud and you have a simple data model.

[00:35:39] **Tim:** Mhm mhm.

[00:35:41] **Carol:** Mhm.

[00:35:43] **Adam:** Right.

[00:35:43] **Adam:** If you're just doing a to do list, then an ORM is fine because create, read, update, delete.

[00:35:48] **Adam:** You're not talking about like too many related records, that sort of thing.

[00:35:52] **Adam:** Okay, fine.

[00:35:53] **Adam:** If you, if you'd rather use ORM than SQL, that's fine.

[00:35:56] **Adam:** But like some of the, I was talking about, you know, these footguns, these mistakes that we made that uh, ended up kind of holding up the rest of the application, um, we didn't really realize that any complicated data loading, right.

[00:36:01] **Carol:** Mhm.

[00:36:10] **Adam:** When you're talking about joining several tables together,

[00:36:12] **Ben:** Mhm

[00:36:13] **Adam:** or needing to like start from one thing and then go deeply nested off of that, it's just way more efficient to spend the brain power and the time up front to write a efficient query to get the things that you want versus, you know, load this database record, then go load this Database record, then go load this one and this one and this one

[00:36:18] **Carol:** Mhm.

[00:36:21] **Tim:** Right.

[00:36:28] **Tim:** M right.

[00:36:31] **Tim:** So that's the N plus one query massacre.

[00:36:32] **Ben:** mhm.

[00:36:33] **Tim:** Right?

[00:36:34] **Tim:** So you're like,

[00:36:34] **Adam:** kind of.

[00:36:35] **Adam:** Yeah,

[00:36:35] **Tim:** so you're like, yeah, we can like do one record per user, but what if I needed to do something the 100,000 users.

[00:36:39] **Carol:** Mhm.

[00:36:41] **Tim:** Well good luck.

[00:36:42] **Adam:** Yeah.

[00:36:42] **Adam:** And I mean there are ORM functions for doing some of that stuff.

[00:36:46] **Adam:** But like I said, we just, we were a little naive in the way that we wrote it originally and by the time that we realized we had done a bad thing, it was too late.

[00:36:54] **Ben:** Mhm.

[00:36:55] **Tim:** Sa.

[00:36:55] **Adam:** Um, and I don't want to blame the tools too much, but I do think that there are

[00:36:55] **Tim:** Mhm

[00:36:57] **Carol:** Mhm.

[00:37:06] **Adam:** bad decisions in the way that the CFML ORM, um, was implemented And I say that, I say specific, specifically CFML because we originally started on Adobe ColdFusion and transitioned, including our ORM code from Adobe to Lucee which that itself was not easy.

[00:37:13] **Tim:** mhm.

[00:37:18] **Carol:** Mhm.

[00:37:25] **Ben:** M mhm.

[00:37:25] **Adam:** we did that, I don't know, like maybe five years ago, something like that.

[00:37:29] **Adam:** and

[00:37:30] **Ben:** Mhm

[00:37:32] **Adam:** so they both have differing bad choices baked in.

[00:37:36] **Tim:** M.

[00:37:36] **Adam:** Um, yeah,

[00:37:36] **Tim:** but, but what was the business reason?

[00:37:37] **Carol:** Mhm.

[00:37:38] **Tim:** So was it just hard to maintain?

[00:37:40] **Tim:** Was it not non performant?

[00:37:41] **Tim:** I mean what was what was going on in the business?

[00:37:43] **Adam:** so there, there, there was some performance issues primarily I think, just because of our bad decisions.

[00:37:50] **Ben:** mhm.

[00:37:50] **Adam:** Right.

[00:37:51] **Adam:** The, like you were talking about the query mass and plus one query massacre stuff Um, also,

[00:37:53] **Tim:** Mhm.

[00:37:56] **Carol:** Mhm.

[00:37:56] **Adam:** uh, the, the application logic that we ended up writing because of like, oh, we use or, and we don't use SQL queries.

[00:38:02] **Adam:** Uh, it just kind of led us down some bad paths.

[00:38:05] **Adam:** we found it incredibly difficult to write tests.

[00:38:05] **Ben:** Mhm

[00:38:06] **Tim:** Mhm

[00:38:09] **Adam:** Um, and that is not necessarily orm's fault.

[00:38:10] **Carol:** Mhm.

[00:38:12] **Adam:** Again, it kind of comes back to we didn't write the code in a testable way using orm, but it just felt absolutely ridiculous that, you know, you'd have a service and you need to do something with some data in a service and you'd have, okay, I have these ORM entities, but I shouldn't access the ORM entity from the service.

[00:38:24] **Ben:** mhm.

[00:38:27] **Tim:** mhm.

[00:38:28] **Adam:** I should have like a data access layer.

## [00:38:29] Testability and Data Access Layers

[00:38:29] **Adam:** And the data access layer calls the orm, um, so that I can then mock that in the data access layer if I want to.

[00:38:31] **Carol:** Mhm.

[00:38:35] **Adam:** And so we didn't do any of that.

[00:38:37] **Adam:** And we have a bajillion lines of code.

[00:38:40] **Adam:** So it was basically impossible to test our services or data access stuff at all, uh, because the code was not testable because of our naivete in the way we implemented orm.

[00:38:47] **Tim:** Mhm

[00:38:51] **Carol:** Mhm.

[00:38:51] **Adam:** So this has been a chain hanging around my neck for the better part of the last 13 years.

[00:38:56] **Ben:** Mhm

[00:38:58] **Adam:** Right.

[00:38:58] **Adam:** And so hopefully that

[00:39:02] **Adam:** helps, uh, helps you understand why we wanted to get away from it.

[00:39:03] **Ben:** mhm.

[00:39:06] **Adam:** Right.

[00:39:06] **Adam:** When I saw how good LM stuff was getting, it's like, actually maybe this might be the way we can finally get out from underneath this.

[00:39:07] **Tim:** mhm.

[00:39:11] **Carol:** Mhm.

[00:39:14] **Adam:** Um, and I do think that it could have been possible.

[00:39:18] **Adam:** I just don't think that for where we are as a company and for, you know, our day to day needs and for the scope that I chose for this project that it was ever going to work.

[00:39:31] **Tim:** I mean it sounds like a full time job, honestly it sounds like some developers full time jobs do this

[00:39:37] **Adam:** Yeah, for more than 18 weeks, that's for sure.

[00:39:39] **Ben:** Mhm mhm.

[00:39:39] **Tim:** for sure, for sure.

[00:39:41] **Tim:** Because, because we're kind of doing the same thing with, with some SQL parameterization stuff and I mean it's massive project.

[00:39:47] **Tim:** But we're, because we have enough people, we have lots of Developers, we can just break it up over multiple sprints, over multiple years and Edible Bytes.

[00:39:52] **Carol:** Mhm.

[00:39:57] **Tim:** Um, so.

[00:39:57] **Adam:** M right.

[00:39:58] **Adam:** And that's the thing, like, I, I don't necessarily think that the

[00:40:03] **Adam:** intention was misguided here.

[00:40:04] **Adam:** I think I just got a little too greedy with trying to get it all done in one shot.

[00:40:05] **Ben:** Mhm

[00:40:09] **Adam:** Right.

[00:40:09] **Adam:** Like if I had just said like, okay, we're going to do the advanced module and just do that and see how that goes.

[00:40:09] **Tim:** Damn.

[00:40:09] **Tim:** Mhm

[00:40:12] **Carol:** Mhm.

[00:40:14] **Adam:** And you know, maybe if that goes well, we'll do the whole rest of the application in one sh.

[00:40:18] **Adam:** If not, then, or if it's, it feels just right, then maybe we'll do again one module at a time or something.

[00:40:24] **Adam:** But and I do think that that was ultimately

[00:40:25] **Ben:** mhm.

[00:40:27] **Adam:** the, the straw that broke the camel's back is.

[00:40:29] **Tim:** mhm.

[00:40:30] **Adam:** It's, it's kind of in a state where it's all or nothing.

[00:40:32] **Carol:** Mhm.

[00:40:33] **Adam:** Um, and, and everything had been touched.

[00:40:35] **Adam:** Right.

[00:40:35] **Adam:** So a few years ago we did, you know, recognize that ORM was hurting us more than it was helping us.

[00:40:41] **Adam:** And so all of our new code since then has been or free.

[00:40:45] **Adam:** Um, and

[00:40:46] **Tim:** Mhm

[00:40:46] **Ben:** Nice.

[00:40:46] **Ben:** Mhm.

[00:40:47] **Adam:** so, you know, making things more interesting and difficult and fun for the ORM migration that I was doing was not everything is going to be this.

[00:40:56] **Adam:** And so there's another decision to make as we're reviewing this code.

[00:40:57] **Carol:** Mhm.

[00:41:00] **Adam:** Um, sometimes it should just be left alone.

[00:41:02] **Ben:** that's almost the harder emotional hurdle to get over is the idea that in the middle of a project, half the code will be one way and half the code will be the other way.

[00:41:02] **Tim:** mhm.

[00:41:13] **Ben:** You think to yourself or I think to myself, like what if I just stop now?

[00:41:17] **Ben:** Now I'm in this like really weird in between state

[00:41:17] **Carol:** Mhm.

[00:41:20] **Adam:** Mhm.

[00:41:21] **Ben:** and uh, I, I, I, I don't, I don't have like a great follow on thought only to say that that is almost the hardest part about starting is wrestling with this idea that it's going to be in just a weird state for a while.

[00:41:32] **Adam:** Yeah, you know, the

[00:41:33] **Tim:** It's like.

[00:41:33] **Tim:** It's like stopping peeing midstream.

[00:41:35] **Tim:** It's not comfortable.

[00:41:36] **Carol:** Mhm.

[00:41:36] **Adam:** uncomfortable, but it's good for you.

## [00:41:38] Git, Subversion, and Incremental Ports

[00:41:38] **Adam:** Um,

[00:41:51] **Ben:** Yeah, I was I was over like the shots weekend I fired.

[00:41:54] **Ben:** was having a little Jeez.

[00:41:54] **Ben:** chat with uh, ChatGPT about this book project that I was talking about.

[00:41:58] **Adam:** Mhm.

[00:41:58] **Ben:** And I was just trying, I was trying to get advice for like how I should organize the files because it, it'd be multiple authors.

[00:42:00] **Tim:** Mhm.

[00:42:05] **Ben:** And literally ChatGPT said because this is a CFML centric book a lot of your authors probably won't be very familiar with git.

[00:42:14] **Ben:** And I was like, what?

[00:42:16] **Ben:** I was like, you son of a.

[00:42:20] **Adam:** Ha.

[00:42:22] **Carol:** Oh snap.

[00:42:23] **Tim:** How dare you, sir?

[00:42:24] **Tim:** How dare you.

[00:42:27] **Carol:** Oh.

[00:42:29] **Tim:** I built my early career on git

[00:42:30] **Ben:** there's no way that's true.

[00:42:31] **Ben:** Right?

[00:42:32] **Carol:** Now you did.

[00:42:34] **Ben:** Everybody knows git now.

[00:42:34] **Carol:** Mhm.

[00:42:35] **Carol:** That's crazy.

[00:42:36] **Carol:** That's a crazy thought that a developer now, any developer now doesn't know git

[00:42:41] **Tim:** Mhm

[00:42:42] **Ben:** Unacceptable.

[00:42:44] **Carol:** I've been doing this for, I don't know, two years now, been trying to get our rewrite.

[00:42:48] **Carol:** I'm not even going to call it a rewrite.

[00:42:50] **Carol:** It's not a rewrite.

[00:42:51] **Carol:** It is a port forward.

[00:42:54] **Adam:** Don't call it a comeback.

[00:42:55] **Carol:** It's a port forward is what I'm calling it into, um, a more modern framework.

[00:42:56] **Ben:** Mhm.

[00:42:56] **Adam:** Okay.

[00:42:58] **Tim:** mhm.

[00:43:00] **Carol:** So what I want to do is use YARP and have our old code sit there and just port the existing code into C# and .NET Core for at which point as the, uh, functionality is in the new code, the old code just stops taking the traffic.

[00:43:00] **Adam:** Mm.

[00:43:00] **Adam:** Mhm.

[00:43:15] **Ben:** Sa

[00:43:17] **Ben:** mhm.

[00:43:17] **Adam:** Mhm.

[00:43:17] **Carol:** Like all you do is just which path am I going down?

[00:43:19] **Tim:** Mhm mhm.

[00:43:22] **Carol:** And for me, I know Ben was saying like, oh, it's kind of scary to be like, oh, what if I stop right now?

[00:43:27] **Carol:** I'm like, well if I stop right now, I still have two code bases sitting there running.

[00:43:27] **Adam:** Sam.

[00:43:31] **Carol:** It kind of sucks, but one's eventually going to get killed or at least a piece of it's going to get killed.

[00:43:36] **Carol:** And I've done this tiny part that is better and more efficient.

[00:43:38] **Adam:** Mhm.

[00:43:40] **Carol:** I'd much rather have the little pieces at a time that become, um, usable than have to kill a process because we had to do it all at once.

[00:43:49] **Carol:** Like there was no option to do little pieces of it.

[00:43:50] **Ben:** Yeah.

[00:43:50] **Ben:** Mhm.

[00:43:52] **Carol:** So that's one thing I do enjoy with what I do is the technology is there for me to do.

[00:43:58] **Carol:** I can take the controller, I can take an area, I can go.

[00:43:59] **Ben:** Mhm.

[00:44:01] **Carol:** Today we are going to rewrite requests and that's the only thing we're going to touch.

[00:44:01] **Tim:** Mhm.

[00:44:05] **Carol:** And we're not doing any fixes or any improvements.

[00:44:08] **Carol:** It's a one to one port.

[00:44:09] **Carol:** Like literally click the button, says convert from language to new language.

[00:44:10] **Adam:** Mhm.

[00:44:14] **Carol:** Paste in.

[00:44:15] **Carol:** Does it build?

[00:44:16] **Carol:** Good.

[00:44:17] **Carol:** Now just slowly make sure the old code stops taking traffic.

[00:44:21] **Carol:** And that's like.

[00:44:21] **Adam:** Did you say,

[00:44:22] **Carol:** That's so cool.

[00:44:24] **Adam:** did you say YARP?

[00:44:25] **Ben:** That's what I heard.

[00:44:25] **Carol:** YARP?

[00:44:26] **Carol:** Yeah, YARP.

[00:44:27] **Carol:** You've never heard of YARP?

[00:44:28] **Ben:** No.

[00:44:29] **Adam:** No.

[00:44:29] **Carol:** Yeah, YARP is called yet

[00:44:29] **Tim:** M.

[00:44:29] **Tim:** Oh, only from Dead Poets Society

[00:44:32] **Carol:** It's called yet another reverse proxy.

[00:44:36] **Ben:** Ah.

[00:44:36] **Adam:** Oh, um.

[00:44:38] **Carol:** So that's what we do.

[00:44:39] **Carol:** We basically just proxy the uh, the route in and it says, hey, which route do I take?

[00:44:41] **Ben:** Mhm.

[00:44:43] **Tim:** Mhm mhm.

[00:44:44] **Carol:** If the new code base, if the new application has like the controller piece for say request, then it hits there.

[00:44:51] **Carol:** Otherwise it says keep going backwards and you'll eventually get to your home.

[00:44:56] **Adam:** Gotcha.

[00:44:56] **Adam:** Uh, I was really hoping that it was going to be like some secret government thing that you're gonna not be like, you're gonna be shocked that it slipped out and you're gonna make us like bleep it and then we would all make jokes for the rest of the show mentioning it.

[00:45:02] **Carol:** Uh, M.

[00:45:04] **Carol:** I know, like quack.

[00:45:07] **Adam:** That would have to be bleeped.

[00:45:09] **Carol:** Lots of quacks.

[00:45:09] **Ben:** Mhm.

[00:45:10] **Carol:** No, I'm very careful about that.

## [00:45:14] Whether to Revisit, and Sunk Cost

[00:45:14] **Ben:** Mhm

[00:45:14] **Carol:** I don't know if you said this through it, but is there any intention of going back?

[00:45:14] **Tim:** Mhm

[00:45:18] **Carol:** Like I know you said stop, you don't feel bad about it, but.

[00:45:20] **Adam:** Sure.

[00:45:22] **Adam:** it's funny you know, so I had this discussion with Steve.

[00:45:23] **Carol:** Mhm,

[00:45:25] **Adam:** Steve and I have a very interesting and fun dynamic and relationship.

[00:45:28] **Ben:** mhm.

[00:45:29] **Tim:** mhm.

[00:45:29] **Adam:** You know, he.

[00:45:30] **Adam:** So he's the CEO.

[00:45:31] **Adam:** I'm the first full time hire since we started this particular, uh, revision of the company or whatever.

[00:45:37] **Adam:** Uh, he's been solopreneur for a long, long time doing various other things, just consulting.

[00:45:37] **Carol:** Mhm,

[00:45:42] **Adam:** And then we pivoted into these products and so like, this is sort of our company, but I'm not a founder.

[00:45:47] **Ben:** Mhm.

[00:45:48] **Adam:** Anyway, um, so we have this really interesting dynamic where we argue, but.

[00:45:48] **Tim:** Mhm.

[00:45:52] **Adam:** And we argue in a way that sounds very upset with each other sometimes.

[00:45:57] **Carol:** Mhm.

[00:45:58] **Adam:** But at, at the end of the day, we both have a tremendous amount of respect for each other and we know in our heart of hearts that the other person wants what's best for the product and for the company.

[00:46:13] **Adam:** And so.

[00:46:13] **Tim:** M.

[00:46:13] **Tim:** You're an old married couple, basically.

[00:46:15] **Tim:** Yeah.

[00:46:15] **Ben:** Mhm.

[00:46:15] **Adam:** Well, but that's what I'm.

[00:46:17] **Adam:** I guess I'm kind of saying, like, it does sound like mom and dad are fighting sometimes.

[00:46:20] **Adam:** Like, we'll do, we'll have these discussions in discord.

[00:46:22] **Adam:** And sometimes it's like it, it starts out fine and then it gets heated or looks like it's getting heated.

[00:46:25] **Ben:** Mhm.

[00:46:27] **Adam:** Um, and I start to feel bad, like, having these conversations, but they're still going.

[00:46:27] **Tim:** Mhm

[00:46:30] **Adam:** And I'm like, well, okay, fine, I'll respond to you.

[00:46:33] **Adam:** Um, but like I said, you know, at the end of the day, there are no hurt feelings on either side.

[00:46:37] **Adam:** Um, and um, we had one of these discussions, uh, about, you know, what should we do?

[00:46:38] **Tim:** mhm.

[00:46:41] **Adam:** And Steve and I went back and forth in private.

[00:46:43] **Adam:** We had this conversation in private.

[00:46:44] **Adam:** Um, and we came to a decision or we're going to table it for now.

[00:46:47] **Adam:** And then we gathered the rest of the engineering team to discuss it.

[00:46:49] **Adam:** Like, this is the current status, this is why, whatever.

[00:46:52] **Adam:** And Steve kind of intro it all.

[00:46:54] **Adam:** And I, I was kind of laughing to myself because I felt like he was explaining it to the rest of the team in a way to soften the blow to me.

[00:46:55] **Tim:** Mhm

[00:47:03] **Adam:** Right.

[00:47:03] **Ben:** Mhm

[00:47:03] **Carol:** Uh, okay,

[00:47:03] **Adam:** Like, like I felt like he was trying to say, like, all this work that Adam's done, we're just going to throw it away.

[00:47:09] **Adam:** It, uh, doesn't matter.

[00:47:10] **Adam:** We're moving forward, whatever.

[00:47:11] **Adam:** But he, he took like five minutes to say it in a very.

[00:47:13] **Ben:** mhm sa.

[00:47:14] **Adam:** In trying to like, be appreciative of the work that I've done and pointing out the bugs that you guys mentioned that we've gotten fixed and like this and that these other benefits that came from and I'm like, dude, you're trying to make me feel better.

[00:47:15] **Tim:** mhm.

[00:47:26] **Adam:** I'm the one trying to drag you into this.

[00:47:28] **Adam:** Like, let's, let's walk away from it at this point.

[00:47:30] **Adam:** so that was, ah, a little amusing.

[00:47:32] **Adam:** But, so it was Steve that brought uh, up the onboarding issues and the stability need on qa.

[00:47:35] **Tim:** Mhm mhm.

[00:47:41] **Adam:** And so that's kind of what kicked off the discussion.

[00:47:43] **Ben:** Shoot.

[00:47:44] **Adam:** Um, so Steve's opinion was this is a lot of valuable work, we shouldn't just throw it away outright.

[00:47:45] **Ben:** Mhm.

[00:47:48] **Carol:** Right,

[00:47:52] **Adam:** Uh, and my opinion is I learned a lot.

[00:47:55] **Adam:** We got some value out of it, the bug fixes and whatnot.

[00:47:59] **Adam:** I learned a lot about automating LLM stuff, but one of the lessons that I learned is like this is too much, at least in its current form.

[00:47:59] **Ben:** Mhm

[00:48:00] **Tim:** Mhm

[00:48:07] **Adam:** Right.

[00:48:07] **Carol:** Right.

[00:48:07] **Adam:** To try and do the entire application one shot.

[00:48:09] **Adam:** And also one of the things that we talked about during that conversation, the private conversation with him was that

[00:48:16] **Adam:** um, if we walk away even for a week, it's, it's going to be too much to try and come back.

[00:48:18] **Ben:** mhm.

[00:48:20] **Tim:** mhm.

[00:48:20] **Carol:** It is.

[00:48:21] **Carol:** Yeah.

[00:48:22] **Carol:** Yeah.

[00:48:22] **Adam:** You.

[00:48:23] **Adam:** This, this is dead on the vine.

[00:48:25] **Adam:** and so, um, he, I don't think he really believes me when I said that.

[00:48:29] **Adam:** But uh, I, I have zero intention of, of trying to revive this project.

[00:48:34] **Adam:** Um, mhm.

[00:48:34] **Carol:** Well, for me even, you know, we said, what, 18 weeks ago.

[00:48:35] **Ben:** Mhm

[00:48:36] **Tim:** Mhm mhm.

[00:48:39] **Carol:** Where models were 18 weeks ago versus where they're at now is substantially different.

[00:48:44] **Adam:** It's pretty crazy.

[00:48:46] **Carol:** So my thought is, a project you started 18 weeks ago, it was probably a bit daunting for what you were trying to accomplish, but if you wait another, you know, six weeks, there's a good chance, you know, Fable comes back out at some point, you know, or a better Model comes out and suddenly you go, hey, this might not be as daunting as it was in February.

[00:48:57] **Ben:** mhm.

[00:48:57] **Adam:** Nine weeks.

[00:48:58] **Adam:** Yeah,

[00:49:01] **Adam:** well,

[00:49:04] **Adam:** maybe.

[00:49:11] **Adam:** I think the big opportunity, uh, cost here is all the stuff that's going to happen in the main branch now that they have diverged.

[00:49:16] **Ben:** Mhm mhm.

[00:49:17] **Carol:** Yeah, mhm.

[00:49:18] **Adam:** Right.

[00:49:18] **Tim:** Mhm mhm.

[00:49:18] **Adam:** I, I forked from main, I made all these changes, I was rebasing and like, okay, so this PR got merged today.

[00:49:25] **Adam:** So now I need to make sure, I go rebase and make sure that the new ORM code that was added now has a non ORM fork in my branch.

[00:49:32] **Carol:** Right.

[00:49:32] **Carol:** And no, for me, I.

[00:49:34] **Carol:** I'm definitely not saying keep the branch and go do it.

[00:49:36] **Carol:** I'm saying if you wanted to resurface the topic of removing ORM in several weeks, you know, three months down the road, your AI tooling may be significantly improved to where what you felt it wasn't good to do 18 weeks ago.

[00:49:37] **Adam:** Mhm.

[00:49:41] **Adam:** Mhm, sure.

[00:49:51] **Adam:** Possibly.

[00:49:54] **Carol:** It might not be an issue anymore.

[00:49:57] **Adam:** I think you're right.

[00:49:57] **Carol:** It might not be as big of an issue.

[00:49:59] **Carol:** Yeah.

[00:49:59] **Adam:** I think you're right.

[00:50:00] **Tim:** Mhm

[00:50:00] **Adam:** From a technical perspective.

[00:50:01] **Adam:** I think one of the other things I'm taking away from this experience of uh, shelving it or tabling it is that I no longer have the appetite to work on this.

[00:50:01] **Carol:** Mhm.

[00:50:12] **Ben:** Mhm mhm.

[00:50:12] **Adam:** This, this was 18 weeks I could have spent porting over to our new modern stack.

[00:50:12] **Carol:** It

[00:50:14] **Carol:** a lot.

[00:50:14] **Carol:** Yeah.

[00:50:18] **Adam:** Right.

[00:50:18] **Carol:** That's what I thought when you were like, oh, we're stopping it.

[00:50:20] **Tim:** mhm.

[00:50:20] **Carol:** That's just a lot of time that could have been spent elsewhere.

[00:50:24] **Carol:** That's what would, that's what would bother me the most.

[00:50:25] **Adam:** Yep.

[00:50:28] **Adam:** So, um, I'm gonna hate to make this comparison, but I do think that it's uh, fair to acknowledge, uh, when a terrible person does something good, it's, it's fair to say that even Though they are a terrible person, they did something good.

[00:50:37] **Ben:** Mhm

[00:50:39] **Tim:** Mhm

[00:50:43] **Adam:** Um, years and years ago, uh, SpaceX decided to stop development on one particular rocket design because they recognized that it wasn't what they needed to do.

[00:50:49] **Carol:** Mhm.

[00:50:53] **Adam:** And they, they had rockets like half built, to, to test them and, and use them.

[00:50:56] **Ben:** mhm.

[00:50:56] **Carol:** Sam.

[00:50:58] **Tim:** mhm.

[00:50:59] **Adam:** And they said, okay, well we're not doing that design anymore.

[00:51:01] **Adam:** So they literally like scrap these half completed rockets rather than finish building them so they could fly them.

[00:51:06] **Adam:** They were just like, okay, we'll stop wasting money on that project and let's go work on this new design.

[00:51:09] **Carol:** Mhm,

[00:51:11] **Adam:** and you know, in case it's not clear, I think that Elon Musk is uh, the, is like uh, an ingrown hair on a cyst on a hernia on uh, the ugliest dog in the world.

[00:51:26] **Adam:** um, at least in his current form.

[00:51:26] **Carol:** Mhm,

[00:51:27] **Adam:** but I do think that the, his approach to sunk cost fallacy there was actually really smart and effective.

[00:51:33] **Tim:** Mhm

[00:51:36] **Adam:** and so that's, I'm kind of trying to take that same approach here.

[00:51:39] **Adam:** Right.

[00:51:39] **Ben:** Mhm.

[00:51:39] **Adam:** Like yeah, we spent a lot of time and money on that and there were some good things that came out of it.

[00:51:40] **Tim:** sa.

[00:51:44] **Adam:** But I think that

[00:51:46] **Adam:** there's no.

[00:51:47] **Adam:** That just because we have been partway down this path doesn't mean that we need to see the end of it.

[00:51:52] **Adam:** Um, and if we

[00:51:52] **Carol:** Mhm.

[00:51:53] **Tim:** Mhm

[00:51:55] **Adam:** are willing to take on that sort of, let's call it an infrastructure project, uh, if we have time and appetite for that sort of thing, I would rather do other infrastructure projects right now than that one.

[00:52:07] **Carol:** Been there.

[00:52:08] **Ben:** I think uh, if you just pitch it as you threw a bunch of tokens at the site and you found a bunch of bugs, uh, you could, you could infer that you had early access to Claude Mythos and,

[00:52:13] **Tim:** mhm.

[00:52:17] **Carol:** Uh,

[00:52:22] **Ben:** and uh, that was it.

[00:52:22] **Ben:** That was your early access phase.

[00:52:25] **Adam:** Okay, Um, all right, well then.

[00:52:25] **Ben:** Mhm

## [00:52:27] Patreon

[00:52:27] **Adam:** This episode of Working Code was brought to you by

[00:52:32] **Adam:** Uh, uh, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:52:34] **Carol:** Mhm.

[00:52:37] **Ben:** mhm.

[00:52:38] **Tim:** Mhm.

[00:52:40] **Adam:** Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them.

[00:52:45] **Adam:** Special thanks as always to our top patrons, Monte and Giancarlo You guys rock.

## [00:52:49] Thanks For Listening!

[00:52:49] **Adam:** We're gonna go record the after show, which regular listeners will know, uh, is outro.

[00:52:55] **Adam:** MUSIC PLAYS and then we come back, we talk about more stuff.

[00:52:57] **Adam:** And sometimes it's books, sometimes it's tv, sometimes it's more code stuff, Um, you never know what you're going to get.

[00:52:58] **Tim:** Mhm.

[00:53:01] **Ben:** Mhm.

[00:53:02] **Adam:** Uh, but if you'd like to find out what you're going to get, this is A real easy way to do it.

[00:53:02] **Carol:** Um.

[00:53:06] **Adam:** You go to patreon.com/workingcodepod and throw a few dollars our way and we'll hook you up.

[00:53:12] **Adam:** That's going to do it for us this week.

[00:53:14] **Adam:** We'll catch you next week.

[00:53:15] **Adam:** And until then.

[00:53:17] **Ben:** mhm.

[00:53:17] **Tim:** Hey you all, it's me, Tim, and I'm here to say I love you, but not in an ORM way.

[00:53:23] **Tim:** Your heart matters.
