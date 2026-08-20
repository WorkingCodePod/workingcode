---
title: "270: Hot Takes on Hot Takes"
description: "We're back after a week off and we have some things to get off our chest. This week we have a grab bag of hot takes and hot takes on hot takes."
date: 2026-08-20
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/0fb7353d-c6a7-4bf7-b829-928402445ac0"></script>
<div class="redcirclePlayer-0fb7353d-c6a7-4bf7-b829-928402445ac0"></div>

We're back after a week off and we have some things to get off our chest. Carol's agent doesn't understand auth, Ben explores the nature of performative coding, Adam agreed that meetings are for decisions, then spent two hours writing an email to prove it, and Tim's AI is better than yours. This week we have a grab bag of hot takes and hot takes on hot takes.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Taffy](https://taffy.io/) — Adam's CFML REST framework, the counterexample of a public repo whose product is the API, not the source
- [Subway Takes](https://www.youtube.com/@subwaytakes) — the 100% agree / 100% disagree format the table falls into mid-meeting-takes
- [Adam's dotfiles blog post](https://adamtuttle.codes/blog/2026/getting-my-shit-together-dotfiles-brewfile-1password-ssh-agent/) — the git bare repo trick for tracking a gitignored personal CLAUDE.md, promised on air

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/270-hot-takes-on-hot-takes.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** I think meetings should basically never be recorded.

[00:00:02] **Ben:** I think recorded m meetings make people lazy And,

[00:00:02] **Carol:** Oh,

[00:00:05] **Tim:** 100% disagree 100% disagree, Ben.

[00:00:09] **Ben:** disagree.

## [00:00:29] Intro

[00:00:29] **Adam:** Okay, here we go to show number 270.

[00:00:29] **Ben:** Mhm mhm.

[00:00:29] **Tim:** Mhm mhm.

[00:00:31] **Adam:** And on today's show, we're gonna talk about a bunch of different stuff.

[00:00:33] **Adam:** Got a bunch of little things we want to get at.

[00:00:35] **Adam:** So I uh, we'll get at them but first, as usual, we'll start with our triumphs and fails.

[00:00:39] **Adam:** And Carol, it looks like I'm coming to you first.

[00:00:41] **Adam:** How's it going?

[00:00:42] **Carol:** Awesome.

[00:00:42] **Carol:** Yeah, great, great.

[00:00:44] **Carol:** Just fantastic.

## [00:00:45] Carol's Triumph

[00:00:45] **Carol:** And I'm going to kick us off with a triumph.

[00:00:48] **Adam:** Okay.

[00:00:48] **Adam:** M.

[00:00:48] **Carol:** I have started a new series at work that I am publishing in our OPM AI Forge and it's called Did You Know?

[00:00:58] **Carol:** And it literally is things that I keep showing people over and over again on how to use AI.

[00:01:05] **Adam:** Mhm.

[00:01:05] **Ben:** Mhm mhm.

[00:01:05] **Tim:** Mhm.

[00:01:06] **Carol:** like, not everyone has the time that, that we have to go try things and figure out how to use it.

[00:01:12] **Carol:** And if you're really set in your ways, you kind of just do the same processes over and over again and you don't think to try something else.

[00:01:20] **Carol:** So I've just started this series where I um, post a message and it has a one or two like page PDF with how to do the task.

[00:01:21] **Adam:** Sa

[00:01:24] **Adam:** mhm.

[00:01:24] **Tim:** Mhm.

[00:01:28] **Carol:** And for the first two, the first one was just how to get the inbox zero.

[00:01:33] **Carol:** So it's hey, did you know you can ask Claude to summarize your emails for you and tell you what's important and you can mark everything else as trash, like that's okay, like let it help you get to what you need or create rules.

[00:01:45] **Tim:** Mhm.

[00:01:45] **Ben:** Mhm mhm.

[00:01:49] **Carol:** So you know what, you know what your we were getting to.

[00:01:52] **Adam:** I'm sure it's capable of doing all kinds of useful stuff, but I, I still get the heebie jeebies at the idea of giving my AI access to anything even remotely private.

[00:02:04] **Adam:** Like my email.

[00:02:04] **Carol:** Mhm.

[00:02:05] **Adam:** Right.

[00:02:06] **Adam:** Like, yeah, I'm sure it could help me filter out more spam and stuff.

[00:02:09] **Tim:** Even your work email,

[00:02:10] **Carol:** My work email is not private.

[00:02:11] **Adam:** Yeah,

[00:02:12] **Tim:** your work email is not private.

[00:02:12] **Adam:** I mean it's, it's not private, but it's still.

[00:02:14] **Carol:** Yeah.

[00:02:15] **Adam:** It could contain stuff in it that I wouldn't want leaked.

[00:02:18] **Adam:** Like sometimes our customers will email us like links that they tried and it has an API key in it.

[00:02:22] **Adam:** And I don't want that API key to be something I now have to go roll and get the customer to update their, their crap because they sent it in an email.

[00:02:22] **Carol:** Yep.

[00:02:24] **Ben:** Mhm mhm.

[00:02:24] **Tim:** Mhm.

[00:02:30] **Adam:** Now I mean it doesn't mean it's.

[00:02:31] **Adam:** They're not sending that API key in an email to a thousand other people.

[00:02:35] **Adam:** But hey, at least it's not me that's leaking it.

[00:02:36] **Carol:** You're not the one doing it.

[00:02:38] **Carol:** Yeah, I mean we had that question come up.

[00:02:38] **Adam:** Yeah,

[00:02:40] **Carol:** One of our users responded to my first post and said, hey, I have uh, information from customers that have keys in it and they weren't sent encrypted, too Which we still go.

[00:02:45] **Tim:** Mhm.

[00:02:51] **Carol:** It's still in your email.

[00:02:53] **Carol:** You still have access to it.

[00:02:54] **Carol:** And we're using models that aren't being trained.

[00:02:57] **Carol:** Like nothing is being trained on our data.

[00:03:00] **Carol:** So you're safe to use it because it's our approved tooling and what we are like in house doing.

[00:03:06] **Tim:** Mhm.

[00:03:07] **Carol:** So for my work email.

[00:03:08] **Carol:** Yes.

[00:03:09] **Carol:** For my personal email, I would not connect it.

[00:03:12] **Adam:** Right.

[00:03:12] **Adam:** Kind of the same thing on my calendar.

[00:03:12] **Carol:** It's a big difference.

[00:03:14] **Adam:** Like.

[00:03:14] **Adam:** Yeah.

[00:03:14] **Carol:** Mhm.

[00:03:14] **Adam:** So on my work calendar I put an appointment on 99% of the time.

[00:03:18] **Adam:** It's like I put in an appointment on just as doctor and then on my personal calendar I'll have one in the exact same time slot and it'll be the doctor's name and the address of the office.

[00:03:20] **Carol:** Mhm.

[00:03:24] **Ben:** Yep.

[00:03:26] **Adam:** And why am I going to.

[00:03:27] **Carol:** Yeah.

[00:03:28] **Tim:** Mhm.

[00:03:28] **Carol:** I just put a city.

[00:03:30] **Carol:** I only go to two doctors over here.

[00:03:32] **Adam:** Mhm.

[00:03:32] **Carol:** So I either put Pooler or Savannah because then I know which one I'm going to.

[00:03:35] **Carol:** So no one.

[00:03:36] **Carol:** It doesn't matter to anyone else.

[00:03:37] **Ben:** Can I just say, uh, I think it's awesome that you're sharing information about how to use AI because I will say my own personal experience in the age of AI is I feel like information sharing or skill sharing, and I don't mean skill in terms of like agent skills, but like skills at using these technologies.

[00:03:38] **Carol:** Um,

[00:03:47] **Tim:** Mhm.

[00:03:53] **Carol:** Mhm.

[00:03:57] **Ben:** The sharing feels like it is not obvious how to do it.

[00:04:02] **Ben:** Well, you know, when everything was code, it was easy to see someone deploy a, uh, SQL statement.

[00:04:02] **Adam:** Mhm.

[00:04:03] **Carol:** Yeah.

[00:04:08] **Ben:** And you're like, oh, I didn't know you could do that with SQL or I've never used a common table expression or, you know, I didn't know that this feature was added to the language.

[00:04:08] **Tim:** Mhm.

[00:04:09] **Adam:** Mhm.

[00:04:17] **Ben:** But because we're all in our own little silos, working on our own agent prompting, Unless I'm actively watching something on YouTube, I, I feel like skill sharing has become very rare in my.

[00:04:26] **Adam:** Mhm.

[00:04:26] **Tim:** Mhm.

[00:04:31] **Carol:** Yeah.

[00:04:31] **Carol:** For me in my role, I'm getting to sit with a lot of people at different levels.

[00:04:36] **Carol:** so I have like the people who haven't touched AI phone, haven't opened the apps on their computer, like don't even know which ones are installed to people who are already doing work and just want to know how they get from that entry point to let me do something even bigger.

[00:04:43] **Adam:** Mhm.

[00:04:43] **Tim:** Mhm.

[00:04:51] **Carol:** So it's fun to be able to tell them like these are tasks that you could repeat.

[00:04:56] **Carol:** So the email one, like that's an easy one.

[00:04:58] **Carol:** And I didn't realize people didn't know you can just transcribe your meetings in Teams Because we're a Microsoft shop, right?

[00:05:04] **Tim:** Mhm.

[00:05:06] **Ben:** Mhm mhm mhm.

[00:05:06] **Carol:** So we use Teams, we are Teams for everything.

[00:05:06] **Adam:** M.

[00:05:06] **Adam:** My condolences.

[00:05:09] **Carol:** So you know, just click transcribe at the end of it.

[00:05:13] **Carol:** You know everything you signed up to do.

[00:05:15] **Carol:** You know what everyone's action items are.

[00:05:17] **Carol:** And if it's a recurring meeting, you can then say, hey, we're about to have this meeting.

[00:05:22] **Carol:** What's left over from the last one?

[00:05:24] **Carol:** Like you can keep your, your like agenda going and you don't have to maintain that anymore.

[00:05:25] **Adam:** Mhm.

[00:05:25] **Tim:** Mhm.

[00:05:30] **Carol:** So those are a few that I've put out.

[00:05:32] **Carol:** So far more are coming but I'm just, I'm happy to kind of be sharing some of this information because we keep telling our vendors and our trainers that we need this and it kind of just goes in one ear and out the other.

[00:05:44] **Carol:** It feels like they want to focus on the new tools, the new features, the new workflows.

[00:05:46] **Tim:** Mhm.

[00:05:49] **Carol:** They don't want to focus on just using it every day.

[00:05:52] **Carol:** They want you to do the new thing.

[00:05:55] **Carol:** So I just took it on and was like, I'll just start posting.

[00:05:57] **Carol:** I'll just do a new series and help people.

[00:06:00] **Ben:** It's awesome.

[00:06:00] **Adam:** So this like articles like blog post type thing internally.

[00:06:03] **Carol:** It, yeah, it's just an internal and AI Forge that we've created that's open to the public inside the agency public, so everyone can get to it.

[00:06:10] **Adam:** Gotcha.

[00:06:11] **Carol:** And yeah, it's just a Teams post that has the PDF and some a little blurb about what it is.

[00:06:18] **Adam:** Yeah.

[00:06:18] **Adam:** Okay.

[00:06:19] **Adam:** Yet another reason not to like Teams

[00:06:21] **Ben:** Mhm.

[00:06:22] **Adam:** I don't need my Slack app to have like blog posts in it.

[00:06:24] **Carol:** Uh, anyways, that's me, thank you too

[00:06:25] **Adam:** Thanks.

[00:06:25] **Tim:** Mhm.

[00:06:26] **Adam:** Mhm.

## [00:06:29] Tim's Triumph

[00:06:29] **Tim:** I'm also going for a triumph today so.

[00:06:32] **Tim:** And this isn't work related, I've had a lot of work related ones.

[00:06:33] **Carol:** Sam.

[00:06:35] **Tim:** So I'm going to go personal.

[00:06:36] **Tim:** I think I've talked about this before that I had,

[00:06:39] **Ben:** Sa.

[00:06:40] **Tim:** um, not Claude but ChatGPT my personal account.

[00:06:40] **Carol:** Mhm.

[00:06:43] **Tim:** Create like a layout of a garden.

[00:06:45] **Tim:** Help me build a citrus garden.

[00:06:46] **Adam:** Mhm.

[00:06:47] **Tim:** It's looking great.

[00:06:47] **Tim:** I mean I started it early spring and it's looking fantastic.

[00:06:48] **Ben:** Mhm.

[00:06:51] **Tim:** And so I'm like, all right, let me give it another challenge.

[00:06:54] **Tim:** And so I'm using it to.

[00:06:57] **Tim:** My front yard is extremely shady and I love, would love to grow mushrooms.

[00:07:02] **Tim:** And so I basically did a a Gaussian splat scan of the entire front yard.

[00:07:10] **Ben:** Mhm.

[00:07:10] **Adam:** M.

[00:07:10] **Adam:** I don't know.

[00:07:11] **Tim:** You're mute, you're muted.

[00:07:11] **Ben:** As one does.

[00:07:12] **Adam:** Yeah.

[00:07:13] **Tim:** Carol

[00:07:13] **Carol:** M.

[00:07:14] **Carol:** What does that mean?

[00:07:15] **Tim:** Gaussian splat So Gaussian splat is, it's basically, but the effect is you can basically use your phone to scan and use even the LiDAR and the compass and the, the camera to scan an entire area.

[00:07:19] **Carol:** Mhm.

[00:07:21] **Adam:** Mhm

[00:07:25] **Adam:** sa.

[00:07:29] **Tim:** So I walked around my front yard in a circle and it kind of shows you like a map of what you're looking at and it like lays over like green meshes so you know that you've scanned that area properly and it creates a very, it can render in your browser a very accurate 3D image of the entire area.

[00:07:35] **Carol:** Sam

[00:07:40] **Ben:** Oh,

[00:07:45] **Ben:** Mhm mhm.

[00:07:46] **Tim:** It's like, so I can now scan the entire front yard.

[00:07:46] **Carol:** m.

[00:07:46] **Carol:** What?

[00:07:49] **Tim:** Like I can spin it and turn it around.

[00:07:51] **Tim:** Look from the trees down.

[00:07:53] **Adam:** M so it's a 3D model.

[00:07:54] **Tim:** It's a 3D model Gaussian splat Yeah.

[00:07:56] **Tim:** Um, and so I used that.

[00:07:57] **Tim:** And so based off the sunlight that I told it the time, I actually did it on the summer solstice, just randomly.

[00:08:04] **Tim:** And um, yeah, got lucky.

[00:08:04] **Adam:** Got um, lucky.

[00:08:05] **Carol:** Mhm.

[00:08:06] **Tim:** And so it could like it told the time It could figure out the shadows and where everything is.

[00:08:09] **Tim:** You can see it's.

[00:08:10] **Tim:** I have a very mossy, shady front yard.

[00:08:13] **Tim:** I thought this would be perfect for growing mushrooms.

[00:08:16] **Carol:** Sam.

[00:08:17] **Tim:** And so it is helping me build a uh, design system rather than just kind of gardening a design system for the front yard to like do shiitake mushrooms, red caps, blewits which are like this lavender colored mushroom that looks really cool.

[00:08:18] **Carol:** Mhm.

[00:08:21] **Adam:** Mhm.

[00:08:24] **Ben:** Mhm mhm.

[00:08:33] **Tim:** other mushrooms just for fun and you know, other like really shade loving because everything I've grown so far is like always needs like a full sun.

[00:08:40] **Carol:** A lot of sun.

[00:08:40] **Tim:** Now I'm like creating like yeah, a lot of, I'm doing like a lot of shady stuff.

[00:08:45] **Tim:** That sounds bad.

[00:08:46] **Tim:** I didn't mean it that way.

[00:08:47] **Carol:** With your mushrooms.

[00:08:47] **Tim:** Um.

[00:08:48] **Tim:** Yeah,

[00:08:50] **Tim:** no, yeah, just, just.

[00:08:51] **Tim:** Yeah.

[00:08:51] **Tim:** So that, that's.

[00:08:52] **Tim:** I mean there's so much fun stuff that it's like, it's weird.

[00:08:56] **Tim:** It's like I hate using AI at work all the time.

[00:08:59] **Tim:** Then I get on the weekend, I'm like well let me switch to ChatGPT and like it could tell me how to diagnose a ferment that got stuck and I haven't been able to create this fig wine that I was working on.

[00:08:59] **Carol:** Mhm.

[00:08:59] **Adam:** Mhm.

[00:09:09] **Tim:** So I don't know, I guess it's a triumph.

[00:09:12] **Tim:** We'll see if I get some cool mushrooms.

[00:09:14] **Tim:** I'll let you know.

[00:09:14] **Carol:** Mhm.

[00:09:15] **Ben:** We've been having a lot of rain up near me.

[00:09:18] **Ben:** I don't know if it's all the northeast, but I've just been having just tons and tons of rain here.

[00:09:20] **Adam:** Mhm.

[00:09:22] **Ben:** And uh, our trees out front, underneath in the shade, all manner of mushrooms.

[00:09:29] **Tim:** Really.

[00:09:29] **Ben:** And I, you know, I have this puppy and I asked ChatGPT to talk about like hit and miss.

[00:09:34] **Carol:** Sam.

[00:09:36] **Ben:** I asked ChatGPT if I should be concerned that we have all these mushrooms now on the ground.

[00:09:40] **Ben:** And the puppy is very orally fixated and everything goes in the puppy's mouth And ChatGPT's response are like, mushrooms are generally not a problem.

[00:09:41] **Adam:** Mhm.

[00:09:49] **Ben:** If the dog's just looking at the mushrooms.

[00:09:51] **Ben:** I wouldn't worry about if the dog is smelling the mushrooms.

[00:09:54] **Ben:** I wouldn't worry if the dog is putting the mushrooms in their mouth.

[00:09:57] **Ben:** I wouldn't worry if the dog is swallowing the mushrooms.

[00:10:00] **Ben:** I would be very concerned.

[00:10:02] **Adam:** Mhm.

[00:10:02] **Tim:** M too late at that point.

[00:10:05] **Carol:** Oh my goodness.

[00:10:07] **Tim:** I mean it's not wrong.

[00:10:08] **Ben:** M.

[00:10:10] **Ben:** It's not wrong.

[00:10:11] **Ben:** It's also not helpful.

[00:10:13] **Carol:** No.

[00:10:14] **Carol:** So ours, the youngest, she uh, is obsessed with ant beds because she's never been exposed to ant beds before.

[00:10:19] **Ben:** Yes.

[00:10:21] **Ben:** Oh my God.

[00:10:21] **Carol:** So much so when she got spayed, she ate a big giant bite of um, ant poison because she was trying to eat the ant bed, you know, turn.

[00:10:23] **Adam:** Mhm.

[00:10:26] **Ben:** Oh.

[00:10:28] **Tim:** Oh no.

[00:10:29] **Carol:** Turns out it's the ant poison that's the safest for her.

[00:10:32] **Carol:** It's just like gonna uh, make her mouth water and make her want lots of water so that we didn't have to do anything.

[00:10:37] **Tim:** Wow.

[00:10:38] **Carol:** So what Claude told me to do was put cayenne pepper in with our ant mix and put cayenne pepper on mushrooms and put cayenne pepper on the ant beds themselves because that'll be a deterrent for her.

[00:10:44] **Ben:** Oh.

[00:10:51] **Tim:** What you don't know is your dog is from Mexico and it loves the spice.

[00:10:55] **Carol:** We're about to find out.

[00:10:57] **Ben:** Yeah.

[00:10:57] **Ben:** M Our dog also loves the ants and she gets them stuck in her snout and then she's like,

[00:10:57] **Adam:** We tried that,

[00:11:02] **Tim:** Oh no.

[00:11:05] **Adam:** We tried cayenne pepper to as a deterrent and it didn't make a difference.

[00:11:08] **Adam:** You know, we ended up doing, I think uh, when our kids were little they were thumb suckers and we, to get them to stop sucking your thumbs we got fingernail polish that was like extremely bitter.

[00:11:09] **Carol:** What's that?

[00:11:17] **Adam:** And so we would paint their nail of their thumb extreme with this extremely bitter nail polish.

[00:11:17] **Ben:** Mhm

[00:11:18] **Tim:** Mhm.

[00:11:22] **Adam:** And we started putting that on stuff that we didn't want the dogs to get into.

[00:11:25] **Adam:** And that finally worked.

[00:11:27] **Tim:** I don't know how you nail polish a ant bed, but.

[00:11:29] **Carol:** I ain't bad.

[00:11:30] **Adam:** No, but we did like uh, you know, the remote control and stuff like that.

[00:11:33] **Tim:** Mhm.

[00:11:33] **Ben:** mhm.

[00:11:35] **Carol:** Smart.

[00:11:36] **Adam:** After you buy your third Fire, uh, TV remote replacement, it's time to come up with something.

[00:11:43] **Tim:** So anyway, that's me.

[00:11:44] **Tim:** I'm just using AI to create a shade garden.

[00:11:46] **Tim:** We'll let you know how it works out next year.

## [00:11:49] Adam's Triumph

[00:11:49] **Tim:** How about you, Adam?

[00:11:50] **Adam:** I'm gonna go with the triumph as well.

[00:11:52] **Adam:** I uh, finally got my Level 2 charger installed at home.

[00:11:56] **Adam:** Uh, I've had my Rivian what since May or so.

[00:11:56] **Carol:** Oh, neat.

[00:11:56] **Ben:** Nice.

[00:12:00] **Adam:** and uh, I, you know been living off of Level 1 charging now with the benefit of hindsight and having unplugged the charger or as we say in the, the EV sphere, uh, EVSE the electric vehicle supply equipment.

[00:12:04] **Tim:** Sa.

[00:12:09] **Tim:** Mhm.

[00:12:14] **Carol:** Sa.

[00:12:16] **Adam:** because the charger is built into the car whatever nerd stuff.

[00:12:19] **Adam:** But the uh.

[00:12:19] **Ben:** Mhm

[00:12:21] **Adam:** I had it set to allow up to 16 amps continuous and I was using it on a 15-amp circuit and that's a big no, no.

[00:12:28] **Adam:** and so I had kind of melted a little bit of the outlet and just uh, uh, just a, like an inch of the wire was kind of like darkened.

[00:12:37] **Adam:** So uh,

[00:12:38] **Tim:** Your house was like 45 minutes away from being burned down.

[00:12:41] **Carol:** Mhm.

[00:12:41] **Adam:** pretty much, um, but it didn't burn down.

[00:12:44] **Adam:** And so I'm using an appropriate charger now.

[00:12:44] **Ben:** mhm.

[00:12:44] **Tim:** Mhm.

[00:12:47] **Adam:** That can do great.

[00:12:48] **Adam:** Uh, and I replaced the outlet and the, I cut off the, the wire that was damaged.

[00:12:53] **Adam:** Um, but the.

[00:12:53] **Adam:** So yeah, the, the new a uh, Level 2 charger Right.

[00:12:56] **Adam:** I said I was previously using a 15-amp outlet.

[00:13:00] **Adam:** Now it's on a two 40 volt 50.

[00:13:03] **Carol:** Mhm.

[00:13:03] **Ben:** Mhm.

[00:13:03] **Tim:** Mhm.

[00:13:04] **Adam:** Uh, it's either a 50 or 60amp.

[00:13:06] **Adam:** It's got to be a 60-amp circuit.

[00:13:09] **Adam:** And so the charger is only set to allow up to 48 amps because it's like the 80% rule or whatever.

[00:13:15] **Adam:** But And so it can charge much faster, right?

[00:13:17] **Adam:** It can go from like nearly empty to nearly full in uh, you know maybe four or five hours instead of four or five days.

[00:13:19] **Tim:** Mhm.

[00:13:23] **Carol:** Yeah.

[00:13:25] **Adam:** which is great because now I got to turn on our local electric company has time of use bin based pricing.

[00:13:31] **Adam:** Right.

[00:13:31] **Carol:** Mhm.

[00:13:31] **Adam:** So basically it switches us from our energy cost is flat across the schedule no matter what time of day we're using it and now uh, basically kilowatt hours cost us differently depending on what of day it is.

[00:13:36] **Ben:** Mhm mhm.

[00:13:36] **Tim:** Mhm.

[00:13:42] **Carol:** Sam.

[00:13:46] **Adam:** And so I have a whole, I like they have a whole schedule but basically from I think it's midnight uh, to 6:00am is like super off peak.

[00:13:55] **Adam:** And so I set my truck to only charge during those hours and I'm paying like 5 cents a kilowatt hour whereas before I was paying like almost 20 cents a kilowatt hour.

[00:14:04] **Adam:** So that's super nice.

[00:14:07] **Carol:** Been there, done all that before.

[00:14:09] **Carol:** At our last, at our last house they had um, an RV charger on the outside.

[00:14:09] **Adam:** Uh, yeah,

[00:14:09] **Tim:** Mhm

[00:14:13] **Adam:** yeah,

[00:14:14] **Carol:** So we just had an electrician come in and he just killed the power to that and then put a 240 in the garage and we charged a Tesla with that and we did the exact same thing except the peak out off peak hours were like 10 to 6am so we just had the Tesla set to charge at 10.

[00:14:15] **Ben:** Mhm mhm.

[00:14:15] **Tim:** mhm.

[00:14:28] **Adam:** Yeah.

[00:14:31] **Carol:** Here we're just doing slow charge.

[00:14:33] **Carol:** So it just always charges whenever it's plugged in.

[00:14:36] **Tim:** Mhm.

[00:14:36] **Adam:** The only downside of the time of use based thing is now peak hours are more expensive.

[00:14:41] **Adam:** Right.

[00:14:41] **Adam:** So instead of it being like me?

[00:14:42] **Adam:** Almost 20 cents a kilowatt hour.

[00:14:44] **Adam:** um, it is like 34 cents a kilowatt hour during peak hours.

[00:14:48] **Adam:** So I like, I also reprogrammed our thermostat to just never turn on the AC between 2:00pm and 6:00pm like no, we'll, we'll just.

[00:14:56] **Carol:** We'll just bake, it's fine.

[00:14:57] **Adam:** Yeah, I mean it's not even.

[00:14:58] **Ben:** Well,

[00:14:58] **Carol:** Mhm.

[00:14:59] **Adam:** I you know what, I made the change and neither one of the kids has said a single word about it.

[00:15:02] **Adam:** So ah, don't think they even notice

[00:15:03] **Ben:** I think some people will also kind of deep freeze their house during the off peak hours and then just kind of let it ride.

[00:15:06] **Adam:** Mm.

[00:15:08] **Adam:** Yeah.

[00:15:09] **Adam:** You using your house as a thermal battery?

[00:15:11] **Ben:** There you go.

[00:15:13] **Tim:** There you go.

[00:15:13] **Ben:** Exactly.

[00:15:13] **Adam:** Yeah, absolutely.

[00:15:13] **Tim:** Huh?

[00:15:13] **Tim:** 100%.

[00:15:15] **Adam:** I think that's a very Midwestern thing is like the, you know, the, at the time of use based pricing.

[00:15:20] **Adam:** In the summer you cool your house overnight.

[00:15:22] **Adam:** In the winter you, you warm it up really much.

[00:15:24] **Adam:** really much.

[00:15:25] **Adam:** That's a.

[00:15:26] **Tim:** I think it's kind of why my house is like it's actually cheaper in this summer despite the fact I'm in Georgia to, to cool it because we have a whole lot of uh, stone and tile and marble and granite everywhere.

[00:15:38] **Adam:** Yeah.

[00:15:39] **Tim:** So it gets really cold at night and that those stones kind of hold all that and then throughout the day it just dissipates.

[00:15:43] **Carol:** Mhm.

[00:15:43] **Adam:** Mhm.

[00:15:45] **Ben:** H.

[00:15:46] **Adam:** Yeah, so that's me.

[00:15:48] **Adam:** how about you Ben?

## [00:15:49] Ben's Triumph

[00:15:49] **Adam:** What do you got going on?

[00:15:50] **Ben:** I'll go with a triumph.

[00:15:51] **Ben:** Very mild here.

[00:15:52] **Ben:** Uh, I am um, surviving a puppy.

[00:15:55] **Ben:** And that's a uh, it's pretty good.

[00:15:57] **Carol:** Mhm.

[00:15:57] **Ben:** This puppy is either asleep or needing attention.

[00:16:02] **Ben:** uh, that it's, I, I can hear it in the other room needing very much attention.

[00:16:02] **Tim:** What is it?

[00:16:02] **Tim:** Right now.

[00:16:03] **Adam:** Mhm.

[00:16:06] **Ben:** But my, my day starts at 5am

[00:16:10] **Ben:** with puppy care.

[00:16:11] **Ben:** uh, I'm, I'm, I'm the early riser so I do the early morning stuff and then I do the late at night stuff and then my wife does a lot of stuff during the day and then I try to take my lunch break to, to give her a break.

[00:16:17] **Adam:** Sa.

[00:16:22] **Adam:** Mhm.

[00:16:22] **Ben:** man, puppy is just a lot of work.

[00:16:24] **Carol:** M so much work.

[00:16:24] **Ben:** Just a lot of work.

[00:16:26] **Ben:** And uh, I, I, I know that like the moment she starts to get more cuddly is going to be a total game changer.

[00:16:26] **Tim:** They are.

[00:16:34] **Ben:** But it's a lot.

[00:16:36] **Ben:** But I'm surviving and that's my triumph.

[00:16:38] **Tim:** Hang in there.

[00:16:40] **Ben:** Yeah.

[00:16:40] **Tim:** Hang in there.

[00:16:40] **Tim:** It's funny, it's like once the dog gets older you don't.

[00:16:43] **Tim:** I uh, mean to our two dogs.

[00:16:45] **Tim:** I don't remember those phases.

[00:16:47] **Tim:** I'm like, they're so good.

[00:16:47] **Carol:** M.

[00:16:47] **Carol:** Yeah.

[00:16:48] **Tim:** They're perfect dogs.

[00:16:48] **Ben:** Yeah.

[00:16:49] **Tim:** But yeah, when I really, really scratch my thing back like actually no, they were terrible when they were little.

[00:16:52] **Carol:** M.

[00:16:54] **Tim:** They were awful.

[00:16:55] **Carol:** Yeah,

[00:16:55] **Ben:** Mhm.

[00:16:55] **Tim:** They were little terror.

[00:16:58] **Carol:** that's what our youngest son reminds us.

[00:17:00] **Carol:** We're like, but Ruby is just such a good girl.

[00:17:03] **Carol:** Like we don't remember her ever being bad.

[00:17:05] **Carol:** And Peyton goes, do you not remember her peeing all the way down the stairs?

[00:17:09] **Carol:** Do you not remember her like drawing blood from scratching my back?

[00:17:15] **Carol:** And when she really like jumping on him, right?

[00:17:15] **Tim:** Mhm.

[00:17:17] **Carol:** I was like, no, I don't remember any of that.

[00:17:20] **Ben:** It's crazy.

[00:17:21] **Ben:** She'll literally go out, she will poop, she will pee three times outside, she will walk in the front door and pee.

[00:17:29] **Ben:** And I'm like what?

[00:17:32] **Ben:** None of that makes sense.

[00:17:33] **Adam:** Mhm.

[00:17:35] **Carol:** Mhm.

[00:17:35] **Ben:** So yeah, that's my triumph.

[00:17:36] **Ben:** I'm still alive but I've, I've basically done nothing else except work and puppy.

[00:17:42] **Ben:** And uh, I'm looking very much forward to getting back to having some semblance of a

[00:17:48] **Ben:** non puppy work schedule.

[00:17:49] **Tim:** Uh, post-puppy world

[00:17:52] **Ben:** Yeah, 100% that's mhm me.

[00:17:53] **Adam:** All right, well then let's move into our collection of topics for the day.

[00:17:54] **Tim:** Mhm.

[00:17:58] **Adam:** we just got a bunch of stuff we want to get off our chest.

[00:18:00] **Adam:** So who wants to go first?

[00:18:02] **Carol:** M.

[00:18:02] **Carol:** Oh, I can go first.

[00:18:04] **Adam:** Sure, go for it.

## [00:18:05] When Agents Fight Local Auth

[00:18:05] **Carol:** So I feel like we spend a lot of time talking about everything that AI is doing so good.

[00:18:10] **Carol:** Like it is just like saving the world.

[00:18:13] **Carol:** It's saving development.

[00:18:14] **Ben:** Mhm.

[00:18:14] **Carol:** Like everything is all great.

[00:18:14] **Tim:** Mhm.

[00:18:17] **Carol:** I have been fighting with AI for two working days, granted, on and off, I'm having meetings and stuff.

[00:18:24] **Carol:** I have these projects that uh, in order to test this end to end authentication piece that I'm changing, I need to run these three projects locally.

[00:18:34] **Carol:** Each one of them runs locally just fine.

[00:18:35] **Tim:** Mhm.

[00:18:37] **Carol:** And I can test them out.

[00:18:38] **Adam:** Oh no.

[00:18:39] **Carol:** The minute they need to talk to each other.

[00:18:41] **Carol:** Auth dies.

[00:18:43] **Carol:** And I can't figure out why.

[00:18:43] **Ben:** Mhm.

[00:18:45] **Adam:** Mhm.

[00:18:45] **Carol:** I mean I know why it's Auth and it never works as you want it to work locally, but for some reason the redirects back in aren't happening how they like they should be.

[00:18:49] **Adam:** Sa.

[00:18:55] **Carol:** And I keep landing in our dev environment.

[00:18:56] **Tim:** Mhm.

[00:18:58] **Carol:** So it's telling me that something in the auth layer is still pushing me to dev and doesn't know how to get back to local.

[00:19:01] **Ben:** Sa.

[00:19:05] **Carol:** So I was like, oh, this is probably just a config somewhere.

[00:19:08] **Carol:** This is probably a client set up wrong.

[00:19:10] **Carol:** I'll feed this to AI multiple, multiple commands.

[00:19:14] **Adam:** Mm.

[00:19:14] **Adam:** Mhm.

[00:19:15] **Carol:** Later.

[00:19:15] **Carol:** Hours, hours going, I think we need to undo this piece of code.

[00:19:15] **Ben:** Mhm.

[00:19:16] **Tim:** Mhm.

[00:19:20] **Carol:** We need to undo this piece of code.

[00:19:23] **Carol:** I was like, I don't think we need to undo anything.

[00:19:25] **Adam:** Mhm.

[00:19:25] **Carol:** I think you need to look at what's eating the ports and you also need to look at how the auth is being redirected.

[00:19:33] **Carol:** It took me so long to get it understand like you need to see where the redirect is happening from sign in to know why it's not going to localhost Like what is, what's going on in this piece?

[00:19:37] **Tim:** Mhm.

[00:19:39] **Ben:** Mhm.

[00:19:45] **Carol:** When I signed off today, I think I was pretty close to having it fixed, but it's been a battle.

[00:19:50] **Carol:** Like I uh, feel like if I would have done this myself, I would have just figured out what was dying.

[00:19:55] **Carol:** But I've gotten it uh, in my head that I need to solve the problem with AI and it's actually not able to solve this problem.

[00:19:58] **Tim:** Mhm.

[00:20:03] **Carol:** Like it doesn't understand how these projects relate and it's, it's struggling.

[00:20:05] **Ben:** Mhm.

[00:20:05] **Adam:** Yeah,

[00:20:08] **Carol:** I even spun up one agent and had it then spin up three more agents, an agent for each repo, hoping then they would all have the context of what the other agent was doing.

[00:20:18] **Carol:** That didn't go well either.

[00:20:19] **Tim:** Mhm.

[00:20:21] **Adam:** over here lighting money on fire trying to figure it out.

[00:20:23] **Carol:** I know it's free right now.

[00:20:25] **Carol:** I could use all the tokens I want.

[00:20:27] **Ben:** But that is, I ah, find that um, because we mostly do vibe coding at work, that there's part of the dream that's you just describe the problem and it fixes it and it makes the stuff happen.

[00:20:35] **Tim:** Mhm.

[00:20:38] **Ben:** But then when it runs into real technical issues and needs my feedback about the technical stuff, it's like I'm already so far removed from that.

[00:20:42] **Carol:** Mhm.

[00:20:44] **Adam:** Mhm.

[00:20:48] **Ben:** You know, it'll, it'll, it'll come back and say, well, I don't understand.

[00:20:51] **Ben:** They'll say like hey, I think there's a problem here with the way we're loading data into this ORM session and things are being flushed, but we need this thing to be committed before we do this.

[00:20:56] **Tim:** Mhm.

[00:20:59] **Ben:** And I'm like, uh, I don't know.

[00:21:03] **Ben:** I'm like, I didn't even know we were using an ORM system.

[00:21:08] **Ben:** So it's uh, yeah, once it gets into the weeds it can get very sticky and the farther removed you are from it, the more sticky that gets.

[00:21:15] **Adam:** Sam.

[00:21:16] **Carol:** Yeah.

[00:21:17] **Carol:** I feel like if I would have made the first change and the one system and let it just handle auth both ways and then publish it, the other two would have talked to the version on dev just fine.

[00:21:17] **Tim:** Mhm.

[00:21:22] **Ben:** Mhm, mhm mhm.

[00:21:26] **Adam:** Mhm.

[00:21:30] **Carol:** I wouldn't be dealing with any of this is if I didn't need to run authentication between the apps locally.

[00:21:36] **Carol:** That's where like my whole catch is.

[00:21:38] **Carol:** And it's not really doing a good job fixing it.

[00:21:41] **Carol:** Mhm.

[00:21:41] **Tim:** Are you running the authentication service locally?

[00:21:44] **Carol:** No.

[00:21:44] **Carol:** I'm running it on dev because I don't want to install the certificates to do it because then that goes a whole other way.

[00:21:45] **Adam:** Mhm.

[00:21:49] **Tim:** Gotcha.

[00:21:51] **Carol:** So we have all the clients set up to relay back to your local.

[00:21:55] **Carol:** So as long as I hit from the right port it goes, okay, send me back and it redirects into local.

[00:21:55] **Tim:** Mhm.

[00:22:01] **Carol:** Except for some reason it keeps pushing me into dev

[00:22:05] **Tim:** Yeah, yeah.

[00:22:06] **Tim:** Uh, just kind of wondering if that might be where it was falling apart.

[00:22:09] **Carol:** Yep.

[00:22:10] **Carol:** I even sent it screenshots of the clients.

[00:22:12] **Carol:** I was like, here's the clients.

[00:22:14] **Carol:** Here's two other clients that someone else created because they probably had the same issue and they used different ports and they're like, no, everything's set up correctly.

[00:22:14] **Adam:** Mhm.

[00:22:22] **Carol:** That's exactly how it should be.

[00:22:24] **Carol:** You have everything right.

[00:22:25] **Carol:** I was like, okay, well it's definitely not working.

[00:22:28] **Ben:** It's definitely not DNS.

[00:22:32] **Tim:** It's always DNS, Ben.

[00:22:33] **Tim:** It's always DNS.

## [00:22:35] Personal Claude Files and Includes

[00:22:35] **Tim:** Okay, well I, I'll, I'll jump in.

[00:22:38] **Tim:** Um, so

[00:22:38] **Adam:** M.

[00:22:38] **Adam:** Yeah, go for it.

[00:22:41] **Tim:** sorry your AI is struggling, but I, I kind of, I think I brought this up on that Discord channel.

[00:22:43] **Carol:** M like in it.

[00:22:48] **Tim:** I sort of have this like weird bias toward my LLM.

[00:22:52] **Ben:** What do you mean?

[00:22:52] **Tim:** Like so my local, my local LLM the, the one that I work with every day when someone else would like obviously send me like well, I ran this to Claude.

[00:22:52] **Adam:** M.

[00:22:53] **Adam:** Yeah, yeah, yeah, yeah.

[00:22:53] **Ben:** Towards your LLM um.

[00:22:53] **Carol:** Like in a good like in A good way.

[00:23:00] **Tim:** Here's what it said.

[00:23:01] **Tim:** I'm like, no, I don't, I don't trust, I don't trust that.

[00:23:02] **Adam:** M.

[00:23:04] **Tim:** Get that out of here.

[00:23:05] **Tim:** Get out of here with that.

[00:23:06] **Tim:** I'm like, my LLM, um, you know, brings boys to the yard

[00:23:10] **Ben:** Mhm.

[00:23:10] **Carol:** Mhm.

[00:23:12] **Tim:** is better than yours.

[00:23:12] **Adam:** It's so, it's so wild.

[00:23:13] **Adam:** I think it's because it's so non deterministic like the, it's not just asking your environment with your AGENTS.md um, or your CLAUDE.md versus asking it in mine with my, you know, uh, system context.

[00:23:26] **Adam:** It's also the way that we phrase the question differently.

[00:23:29] **Tim:** Yeah.

[00:23:29] **Adam:** It's like the.

[00:23:30] **Adam:** Seen through the lens of my brain.

[00:23:30] **Ben:** Sa.

[00:23:32] **Carol:** F.

[00:23:32] **Adam:** And, and yeah, I feel I found that, that to be something that makes it difficult to just even talk about you know, like Carol was talking about.

[00:23:35] **Tim:** Mhm.

[00:23:36] **Ben:** Mhm.

[00:23:43] **Adam:** She's given these advice, uh, tips and stuff, and I'm like, I want to do that.

[00:23:48] **Adam:** I want to help out my co workers.

[00:23:49] **Adam:** I think maybe part of it is I feel like, I don't want them to feel like I'm talking down to them.

[00:23:53] **Adam:** Right.

[00:23:53] **Adam:** Like they, they're smart people, they know how to do this stuff.

[00:23:56] **Carol:** M.

[00:23:56] **Carol:** You'd be surprised who doesn't?

[00:23:58] **Adam:** Yeah.

[00:24:00] **Ben:** I don't know how to articulate this exactly, but it feels like the people who design the cascading lookup of where information comes from when an agent is executing a prompt.

[00:24:10] **Tim:** Mhm.

[00:24:13] **Ben:** It feels a little bit like those people have never worked on a team.

[00:24:17] **Carol:** Mhm.

[00:24:17] **Ben:** Because the idea that I could have something affect the agent that then creates code for my project, the idea that that is not very clearly articulated in some file that is hopefully tracked in a repository, like blows my mind.

[00:24:20] **Tim:** Sa.

[00:24:27] **Carol:** Sam.

[00:24:31] **Tim:** Mhm.

[00:24:36] **Ben:** Like.

[00:24:36] **Carol:** Mhm.

[00:24:36] **Adam:** What are you saying, Ben?

[00:24:37] **Adam:** I mean like the, the CLAUDE.md and the AGENTS.md there's a whole like, hierarchy of where it looks for them.

[00:24:43] **Adam:** So you've got it in the.

[00:24:43] **Ben:** No, no, but that's my point.

[00:24:44] **Ben:** That's my point.

[00:24:45] **Ben:** It's like the fact that this mechanism is in place seems bonkers to me that anyone on a team would say, have a personal agents file that affects every prompt that goes into a project that other people are working on.

[00:24:51] **Tim:** M.

[00:24:58] **Adam:** Mhm.

[00:25:02] **Adam:** Oh, I see.

[00:25:02] **Ben:** Seems crazy.

[00:25:02] **Adam:** You, you don't like the shared rules aspect of it.

[00:25:03] **Carol:** Yeah.

[00:25:04] **Ben:** Yeah, yeah.

[00:25:05] **Tim:** Yeah, yeah.

[00:25:05] **Ben:** Like if it.

[00:25:05] **Tim:** That's not, that's, that's an anti pattern.

[00:25:06] **Adam:** Yeah,

[00:25:06] **Ben:** If.

[00:25:07] **Tim:** You don't do that.

[00:25:08] **Tim:** You shouldn't do that.

[00:25:08] **Ben:** No, but that's what I'm saying is like it feels like the people who designed this were like we never worked on teams.

[00:25:13] **Ben:** That's crazy.

[00:25:14] **Adam:** I think, I think the, the.

[00:25:15] **Tim:** Mhm.

[00:25:15] **Adam:** I think you're holding it wrong.

[00:25:16] **Carol:** Mhm.

[00:25:17] **Ben:** Or the fact that there's even memory like that there's.

[00:25:17] **Adam:** you know,

[00:25:19] **Ben:** That there's a memory that can just randomly be written and it doesn't really tell you that that's happening.

[00:25:19] **Adam:** yeah,

[00:25:24] **Ben:** It'll just be like, oh, let me write that to my memory so I know it for next time.

[00:25:26] **Adam:** Yeah,

[00:25:26] **Ben:** You're like, okay, what does that mean?

[00:25:27] **Carol:** I'm um, like wait, is this my memory?

[00:25:29] **Adam:** yeah, I get annoyed by that too.

[00:25:31] **Carol:** Yeah.

[00:25:31] **Adam:** But uh, the, the like CLAUDE.md or AGENTS.md I think you have to have a set of things that you're like, your team has to kind of agree on what goes into that file and then if you want something that the team doesn't want, then you put it in your CLAUDE.md in your home directory or whatever.

[00:25:42] **Carol:** Mhm.

[00:25:49] **Ben:** I know.

[00:25:49] **Ben:** But then it like.

[00:25:51] **Ben:** So I have uh.

[00:25:51] **Ben:** And this is where it gets even crazier to me is in the project at work, the main project at work, we have our, our uh, MD file which is shared and then I have like a uh, what is it Like settings.local.json which is like my preferred settings for the local app.

[00:25:53] **Tim:** Mhm.

[00:26:02] **Adam:** Mhm.

[00:26:08] **Adam:** M.

[00:26:09] **Adam:** Yeah.

[00:26:09] **Carol:** M Like you can bash.

[00:26:09] **Ben:** And I'm doing it and it feels terrible to me.

[00:26:12] **Ben:** Like I'm like, this feels dirty.

[00:26:13] **Tim:** Mhm.

[00:26:14] **Ben:** I'm now, no, I'm not committing a file, so I'm specializing my Claude.

[00:26:15] **Adam:** Are you committing that file?

[00:26:17] **Adam:** Okay.

[00:26:19] **Carol:** Mhm.

[00:26:22] **Ben:** But now I'm like doing it in a way where I'm not uh, up leveling other people.

[00:26:26] **Ben:** Meaning like I'm doing this because I think it works better, but I'm not confident in enough to say that, hey, I think we should all do this.

[00:26:26] **Adam:** Yeah.

[00:26:33] **Ben:** But then who knows what the other people on the team are doing with their own uncommitted rule files.

[00:26:33] **Adam:** Right.

[00:26:34] **Tim:** Mhm.

[00:26:38] **Ben:** I mean it just seems like,

[00:26:40] **Carol:** Have a suggestion?

[00:26:40] **Adam:** Maybe.

[00:26:41] **Carol:** Ask them.

[00:26:43] **Adam:** No.

[00:26:43] **Adam:** Ew.

[00:26:44] **Adam:** Talk to a human.

[00:26:45] **Adam:** Yuck.

[00:26:46] **Carol:** Just ask them.

[00:26:46] **Ben:** Can I just have my agents talk to their agents?

[00:26:49] **Carol:** Sir.

[00:26:49] **Carol:** Do it.

[00:26:50] **Ben:** Sa.

[00:26:51] **Adam:** Uh, I think you're onto something there, Ben.

[00:26:53] **Adam:** Like

[00:26:54] **Adam:** I was, you know, my, my initial feedback there was like, just put it in your CLAUDE.md in your home directory.

[00:26:55] **Tim:** Mhm.

[00:26:58] **Ben:** Mhm.

[00:27:00] **Adam:** But I think where that breaks down is.

[00:27:03] **Adam:** Well, I want it to be specific to this project, right.

[00:27:05] **Adam:** I have 150 different projects on my system.

[00:27:06] **Carol:** Exactly.

[00:27:07] **Adam:** I don't want one file to have to have all the, all my personal rules for all of them.

[00:27:11] **Adam:** And I know they have like a whole hierarchy system where like, it'll go up the file system until it gets to the home directory or something.

[00:27:16] **Tim:** Mhm.

[00:27:18] **Ben:** Yeah, yeah,

[00:27:19] **Carol:** Sam.

[00:27:20] **Adam:** Man, that sounds awful.

[00:27:21] **Carol:** Mhm.

[00:27:22] **Adam:** I'm going to have to have like, uh, a dev folder where I, where I put all my projects.

[00:27:26] **Adam:** And then every project needs to have like a wrapper folder where I can just put my own custom CLAUDE.md that adds onto the one that's committed in the repo.

[00:27:34] **Adam:** And then I have a folder inside that where I check out the repo.

[00:27:37] **Adam:** Like ew.

[00:27:40] **Ben:** Yeah, yeah.

[00:27:41] **Ben:** It's a little, it's a little wild.

[00:27:44] **Tim:** Um, I mean, m.

[00:27:45] **Tim:** My point of it was I feel like I have trained my little dragon or my little Tamagotchi and I just have this affinity for it because I kind of feel like I know what it's going to do and when someone else is like, yeah, I'm going to run this through Claude I'm like o.

[00:27:52] **Ben:** Mhm.

[00:27:58] **Tim:** You probably won't get as good a result as me.

[00:28:00] **Carol:** Mhm

[00:28:02] **Adam:** Actually, I just thought of something.

[00:28:04] **Adam:** so Claude, specifically Claude has like some special syntax for CLAUDE.md and you can say like, I, I don't use Claude, so I don't remember the syntax.

[00:28:06] **Tim:** Sa.

[00:28:12] **Adam:** But there's a way to like basically include another file in your CLAUDE.md right?

[00:28:18] **Adam:** Like a, like a CF include or whatever to speak Ben's language.

[00:28:18] **Tim:** Mhm.

[00:28:21] **Adam:** Um, and so what you could do is you could like gitignore and have like CLAUDE.local.md or whatever.

[00:28:21] **Ben:** Okay.

[00:28:22] **Carol:** mhm.

[00:28:29] **Adam:** Right.

[00:28:30] **Adam:** And include it in your CLAUDE.md And then when Claude runs it actually sees that file as if with the include as if that was the original.

[00:28:37] **Adam:** Right.

[00:28:37] **Adam:** It's not like making an extra hop.

[00:28:39] **Adam:** It's not reading extra files or anything.

[00:28:40] **Ben:** Mhm.

[00:28:41] **Tim:** Right.

[00:28:41] **Adam:** You gitignore it.

[00:28:41] **Ben:** Mhm.

[00:28:42] **Carol:** Mhm.

[00:28:42] **Adam:** So every, every developer can have their own custom additions.

[00:28:46] **Adam:** And then I m initially was like, okay, well that's, that's a partial solution because you get the result that you're looking for, but then you lose the ability to keep track of what's in that file.

[00:28:55] **Adam:** But then if you do like a dot, uh files repo, you can symlink that file in.

[00:29:00] **Adam:** And uh, you don't even have to symlink it, you can pull it in.

[00:29:03] **Adam:** But see my blog post on dotfiles

[00:29:04] **Tim:** He's problem solving right here in life.

[00:29:06] **Tim:** Yeah, exactly.

[00:29:06] **Carol:** Um, let me ask you something Tim.

[00:29:07] **Tim:** He's problem solving on live

[00:29:11] **Carol:** So with everything that you have trained or like everything is learned about how you talk and stuff, is that all stored on your local or is that in the cloud with Claude?

[00:29:14] **Adam:** Mhm.

[00:29:18] **Ben:** Sa

[00:29:20] **Carol:** How is that set up?

[00:29:22] **Ben:** mhm.

[00:29:22] **Carol:** M okay.

[00:29:22] **Tim:** So it's a local, but I do have basically a GitHub repository that I push everything to, to store it to my personal for the stuff that's not.

[00:29:31] **Carol:** Yeah.

[00:29:32] **Tim:** And then, and then if it's really good, we just wind up making a plugin which we have a marketplace for the entire company.

[00:29:38] **Tim:** So anytime something gets approved, we just put it up in the plugin.

[00:29:42] **Carol:** So the, the local setting stuff has gotten us before.

[00:29:42] **Tim:** Uh, repo.

[00:29:46] **Carol:** So some of our users have had laptops die and everything was just in like on their C: drive and now they go back and they're like I don't know how to do any of this because they had gotten so like muscle memory trained with what they had already set up that they were like, I don't remember how.

[00:29:46] **Tim:** Mhm.

[00:29:50] **Adam:** Mhm.

[00:29:50] **Tim:** And they have no local setting.

[00:29:53] **Ben:** Nice.

[00:29:57] **Adam:** Mhm.

[00:30:01] **Ben:** Mhm.

[00:30:04] **Carol:** So now I share like all my Claude stuff is in my OneDrive So if my computer dies I just re-pull it back in so I'm being safe there.

[00:30:13] **Adam:** Yeah,

[00:30:13] **Carol:** Yeah.

[00:30:14] **Adam:** similar to like my dotfiles suggestion.

[00:30:14] **Tim:** Yeah,

[00:30:17] **Carol:** Mm mhm

[00:30:17] **Adam:** Right.

[00:30:17] **Adam:** Like you can.

[00:30:18] **Adam:** It's weird because uh, my initial thought was that I would have to like, okay, have the file in another place and then symlink it to the place in my project where I wanted to be in.

[00:30:19] **Tim:** Mhm,

[00:30:22] **Ben:** Mhm.

[00:30:25] **Carol:** mhm.

[00:30:27] **Adam:** That would probably is kind of going to work, but it's a little clunky.

[00:30:31] **Adam:** The uh, git bare repo.

[00:30:33] **Adam:** Like I go into this in my blog post about dotfiles and I'll link it in the show notes.

[00:30:36] **Adam:** But um, you can use a git bare repo and like just grab random files on your file system and include them in a repository and it knows what the file path was.

[00:30:39] **Tim:** Mhm,

[00:30:44] **Carol:** That's neat.

[00:30:44] **Ben:** Oh, that is cool.

[00:30:45] **Adam:** Yeah.

[00:30:45] **Carol:** I did not know that.

[00:30:47] **Ben:** All right,

[00:30:47] **Adam:** shall we move on?

[00:30:48] **Adam:** Somebody else want to go?

[00:30:49] **Carol:** Yeah.

[00:30:49] **Adam:** I.

## [00:30:49] Performative Code and Public Repos

[00:30:49] **Ben:** uh, I'll jump in here.

[00:30:51] **Adam:** All right,

[00:30:52] **Ben:** Um, I was thinking that at the end of the day, we're all people, and people.

[00:30:57] **Tim:** Mhm.

[00:30:58] **Adam:** Uh, speak for yourself, sir.

[00:31:01] **Ben:** People are performative in nature, I believe.

[00:31:05] **Ben:** I remember when I was a kid,

[00:31:07] **Adam:** You should see me go through the agility course.

[00:31:09] **Carol:** Mhm.

[00:31:10] **Ben:** when I was a kid and I would drive around.

[00:31:12] **Ben:** This was like, just after I learned to drive, and I would drive around by myself and I would play my music.

[00:31:14] **Adam:** Mhm m.

[00:31:16] **Ben:** And definitely part of me wasn't just listening to the music.

[00:31:20] **Ben:** For me, this is gonna sound so stupid, but I think this is like how people are.

[00:31:22] **Adam:** Yeah,

[00:31:23] **Ben:** Part of me was like, oh, when I'm driving by people and they hear the music that I'm playing, like, that's part of this experience that I am.

[00:31:32] **Adam:** How else are they going to know that you're a badass?

[00:31:32] **Carol:** Yes.

[00:31:33] **Ben:** Exactly.

[00:31:34] **Tim:** Exactly.

[00:31:36] **Ben:** You know, like everything that we do in life is

[00:31:39] **Tim:** Mhm.

[00:31:40] **Ben:** experienced by other people as much as it is by ourselves.

[00:31:42] **Carol:** Mhm.

[00:31:45] **Ben:** And this becomes super fascinating in the age of AI, where I feel like, especially for developers,

[00:31:53] **Ben:** I think we're kind of disconnecting ourselves from this idea of things being performative.

[00:31:55] **Carol:** Sam.

[00:31:59] **Adam:** Mhm.

[00:32:00] **Ben:** And I was looking through a repository that someone had just shared recently, and I'm looking at the code and I'm thinking like, this is like, there's some very peculiar choices here.

[00:32:00] **Tim:** Mhm.

[00:32:04] **Carol:** Mhm.

[00:32:10] **Ben:** Uh, in particular spacing around braces and in if blocks was the thing that I was like, this is just weird.

[00:32:16] **Ben:** Uh, and probably what happened is they didn't actually write this code.

[00:32:17] **Adam:** Mhm.

[00:32:19] **Ben:** This code was probably generated by an AI and they didn't care how the spacing worked inside the function bodies.

[00:32:20] **Tim:** Mhm.

[00:32:26] **Carol:** It built.

[00:32:27] **Ben:** Yeah, exactly.

[00:32:28] **Ben:** Um, and that made me think about public versus private repositories because that was on GitHub and GitHub you've been able to have private repositories, like unlimited private repositories on free accounts.

[00:32:29] **Adam:** Sam.

[00:32:36] **Adam:** Mhm.

[00:32:40] **Tim:** Mhm.

[00:32:40] **Ben:** I think since.

[00:32:40] **Ben:** I think Adam, you had mentioned in the pre show, since Microsoft took over, which means that you can have whatever you want behind the scenes, but you're going to make it public because again, part of that public repository is the performative nature of the code.

[00:32:43] **Carol:** Sam.

[00:32:43] **Carol:** Mhm

[00:32:57] **Ben:** Here's something I've built.

[00:32:59] **Ben:** I'm showing it off to the world.

[00:33:01] **Ben:** I'm excited about it, have, have at it.

[00:33:01] **Tim:** Mhm.

[00:33:04] **Carol:** mhm.

[00:33:05] **Ben:** And that starts to feel really weird when the code is AI generated.

[00:33:12] **Ben:** It's one thing when you're building a product and the product is the end product, so to speak, that's the thing that people are experiencing.

[00:33:13] **Adam:** Mhm.

[00:33:17] **Adam:** Sure.

[00:33:20] **Ben:** But when the artifact that you are passing along to other people is the code itself.

[00:33:22] **Tim:** Mhm.

[00:33:25] **Carol:** Mhm.

[00:33:27] **Adam:** I mean, yes and no.

[00:33:29] **Adam:** Right.

[00:33:29] **Adam:** So, okay, let's talk about Taffy.

[00:33:31] **Adam:** Right.

[00:33:31] **Adam:** So for anybody who doesn't know Taffy is a GitHub repo that I have, it's an open source project for creating REST APIs in CFML.

[00:33:40] **Adam:** Um,

[00:33:41] **Adam:** I would say the product of that project is an easy way to

[00:33:43] **Tim:** Mhm.

[00:33:49] **Adam:** create REST APIs.

[00:33:51] **Adam:** The intent is not for you to look at the code and go, ooh, this is so elegantly written.

[00:33:56] **Adam:** It's for you to.

[00:33:58] **Adam:** Oh, this makes writing REST API so easy.

[00:34:00] **Carol:** Mm mhm.

[00:34:02] **Ben:** Mhm.

[00:34:03] **Tim:** I would say that's a fair.

[00:34:04] **Tim:** I mean I, I use the heck out of your API Taffy.io I've never looked at the source code.

[00:34:09] **Ben:** Mhm.

[00:34:10] **Adam:** Yeah,

[00:34:12] **Tim:** Um, I looked at once to fix like some little edge case that I had, but other than that I've never looked at it.

[00:34:15] **Ben:** Sa.

[00:34:18] **Tim:** So I don't really care what your code looks like.

[00:34:21] **Carol:** I do.

[00:34:21] **Adam:** But I, I mean, I will say thank you.

[00:34:24] **Adam:** I will say there are times when you're right, Ben, that the, the code itself is kind of performative.

[00:34:30] **Adam:** Like, you know, it's a.

[00:34:32] **Adam:** If it's just, I don't know,

[00:34:35] **Adam:** it's.

[00:34:35] **Adam:** It's hard for me to think of an example, but I, I do think.

[00:34:37] **Tim:** I, I would say if, if I were looking at it now, I would look at it and say there's a whole lot of CF tags in this.

[00:34:43] **Tim:** And I probably, I wouldn't load it, but I loaded it back then because I knew, I knew Adam.

[00:34:46] **Ben:** I think he just converted it.

[00:34:47] **Adam:** Not anymore.

[00:34:49] **Tim:** Like, I like Adam.

[00:34:50] **Tim:** He's gonna do good work.

[00:34:51] **Tim:** It's gonna be good.

[00:34:52] **Tim:** So I didn't bother looking.

[00:34:53] **Tim:** But today I'd be like, why did Adam use tags?

[00:34:55] **Tim:** And then I realized the date on it, I'm like, okay, it's kind of old.

[00:34:58] **Tim:** I get it.

[00:34:59] **Carol:** Wait, what, who, who converted it?

[00:35:01] **Carol:** You converted it?

[00:35:02] **Carol:** Ad.

[00:35:03] **Adam:** Uh, Claude and I converted,

[00:35:04] **Ben:** Yeah.

[00:35:04] **Tim:** Yeah.

[00:35:05] **Tim:** I haven't updated so.

[00:35:06] **Ben:** Sa.

[00:35:06] **Carol:** Mhm.

[00:35:07] **Adam:** uh, yeah, uh, it's no longer.

[00:35:09] **Adam:** So that was the thing, when I originally created it.

[00:35:11] **Ben:** Mhm.

[00:35:12] **Adam:** I think it was like in the era of either CF9 or CF10.

[00:35:16] **Adam:** and so I was like, okay, well, let's make it CF8 compatible.

[00:35:19] **Adam:** Right.

[00:35:19] **Carol:** Yeah.

[00:35:19] **Adam:** In CF8 there was no, I think you could use a CFScript block.

[00:35:23] **Adam:** But that was it.

[00:35:24] **Adam:** There was no like script components, anything like that.

[00:35:26] **Tim:** Mhm.

[00:35:27] **Adam:** And so ever since then, Taffy has been, CF8 compatible until I think earlier this year, 2026, where I finally was like, you know what, I don't think we need to be CF8 compatible anymore.

[00:35:29] **Carol:** Mhm.

[00:35:40] **Adam:** So, I used Claude to clean up the test suite and make sure everything was still working.

[00:35:44] **Tim:** Mhm.

[00:35:44] **Adam:** And then, committed that and, and then said, okay, now convert all the code to modern script syntax, but don't change any of the tests.

[00:35:45] **Carol:** Sam.

[00:35:46] **Carol:** Mhm.

[00:35:53] **Adam:** And so now the test suite, you know, is, is reinforcing that.

[00:35:56] **Adam:** Nothing functionally changed.

[00:35:59] **Adam:** M.

[00:35:59] **Ben:** here's an interesting thing, right?

[00:35:59] **Tim:** Mhm.

[00:36:00] **Ben:** So Sean Corfield who doesn't listen to the show, so I can call him out here.

[00:36:05] **Carol:** Mhm.

[00:36:05] **Adam:** Sometimes he reads this show.

[00:36:06] **Ben:** So

[00:36:07] **Adam:** We do have transcript.

[00:36:09] **Ben:** I, I believe, uh, this is probably like a year or two ago when I was talking about how I used to.

[00:36:16] **Ben:** I think this is when I, my return statements, I used to have put parentheses around my return expression, so I would have like return open parentheses expression, close a parenthesis.

[00:36:20] **Tim:** Mhm.

[00:36:26] **Adam:** Mhm.

[00:36:26] **Ben:** And I think Sean said in a chat somewhere that if he, if he saw that in code from someone who was applying to a job, he would not hire that person because.

[00:36:35] **Carol:** Oh um.

[00:36:35] **Adam:** Which is really interesting because he's a Lisp developer.

[00:36:40] **Ben:** So, you know, to each their own.

[00:36:40] **Tim:** Mhm.

[00:36:42] **Ben:** This is not, this is not about whether or not that's a sane state.

[00:36:47] **Ben:** But the, the point is that he was experiencing the code again from a performative standpoint, like there wasn't anything technically wrong with the way I was writing code, but in his eyes it expressed something that didn't align with the way that he wanted to see the code, which again, totally fair.

[00:36:48] **Adam:** That's its own show.

[00:36:48] **Carol:** Mhm

[00:36:56] **Adam:** Sure.

[00:37:01] **Tim:** Mhm.

[00:37:03] **Carol:** mhm.

[00:37:07] **Adam:** Yeah, yeah, yeah.

[00:37:08] **Ben:** Um, and there's been a lot of talk as AI has become more popular that, oh, you know, if you want to point the slop cannon at some problem and it's just like a one off script or it's something you're building for your cousin, like, who cares what it looks like because no one's ever going to see it.

[00:37:20] **Tim:** Mhm.

[00:37:21] **Ben:** Maybe it runs once and you throw it away.

[00:37:23] **Carol:** Mhm

[00:37:23] **Adam:** Mhm.

[00:37:23] **Ben:** So we've, we've kind of, we were edging into the AI world, kind of bringing that mindset of, yeah, standards and the way things look, look and feel are still important.

[00:37:35] **Ben:** So if it's a one off script, we don't care.

[00:37:38] **Ben:** But now we're like, well, as long as the code works really well and it has tests and it's not insecure and it gets the job done, like that's really what's important.

[00:37:38] **Adam:** Okay.

[00:37:40] **Tim:** Mhm.

[00:37:43] **Carol:** mhm.

[00:37:47] **Ben:** But then again, going back to the idea, but if the code is public and you are performing as a developer by making it public and you're showing this to the world, I feel like the perspective that the code adheres to some aesthetic,

[00:38:00] **Adam:** Mhm.

[00:38:01] **Tim:** Mhm.

[00:38:04] **Carol:** Mhm

[00:38:06] **Ben:** uh, heuristic.

[00:38:07] **Ben:** Aesthetic level of whatever.

[00:38:11] **Ben:** Like either that never made sense and those were foolish feelings to have, or they still make sense.

[00:38:18] **Ben:** And if you look at publicly available AI generated code, it should look and feel a certain way and you shouldn't just brush it off being like, oh, well, it's AI generated.

[00:38:20] **Adam:** Mhm.

[00:38:21] **Tim:** Mhm.

[00:38:24] **Carol:** mhm.

[00:38:29] **Ben:** Who cares if it has the right abstractions?

[00:38:31] **Ben:** Who cares if this function is triplicate duplicated across the code base?

[00:38:37] **Ben:** Like you, like you either still have to have that standard or that standard never made sense.

[00:38:42] **Ben:** And I feel like the standard still makes sense.

[00:38:42] **Tim:** Mhm.

[00:38:44] **Ben:** I think it made sense when I first had it.

[00:38:47] **Ben:** And I don't know,

[00:38:49] **Ben:** I feel like everybody's wrestling with this sa.

[00:38:52] **Carol:** A lot of people are for sure.

[00:38:54] **Carol:** uh, I don't think it like for me it's not a public versus private thing.

[00:38:58] **Carol:** It's if I'm going to have to maintain it, if I'm going to be the one that has to live with this architecture and the decisions made, that's when I care more about it.

[00:39:01] **Tim:** Mhm.

[00:39:07] **Carol:** But if it's a one off or uh, even a two off, whatever, it's working, it's there.

[00:39:13] **Carol:** I'm never going to touch it again.

[00:39:14] **Carol:** If someone else wants to try to figure it out, have fun,

[00:39:15] **Adam:** M.

[00:39:15] **Adam:** Right,

[00:39:18] **Adam:** so.

[00:39:19] **Adam:** And I have a bunch of repos that are like that too, that it's like, I make it open source, not because I want it to be considered part of my resume, but it's more for me like a charitable donation to the, to the open, the public good, the commons.

[00:39:22] **Tim:** Mhm.

[00:39:22] **Ben:** Mm, mhm, mhm.

[00:39:34] **Adam:** Right.

[00:39:34] **Adam:** Like I made this thing.

[00:39:35] **Adam:** It's useful to me now.

[00:39:37] **Adam:** I probably will never look at it again.

[00:39:38] **Adam:** If you find it in 20 years and it seems like it might be a good base to build something better on, then you're welcome to have it.

[00:39:40] **Ben:** Sa.

[00:39:43] **Tim:** Mhm.

[00:39:45] **Carol:** It's yours.

[00:39:46] **Carol:** Yeah.

[00:39:46] **Carol:** Mhm.

[00:39:47] **Adam:** like that that's part of how I think about some of my repos.

[00:39:50] **Adam:** Um, I was thinking while you were talking, Ben though, there's a couple of other things that, like other angles to look at this by.

[00:39:56] **Adam:** Right.

[00:39:56] **Adam:** So, um, I have a couple.

[00:39:57] **Adam:** I can think of at least one project in particular where I wrote a Safari plugin.

[00:40:01] **Tim:** Mhm.

[00:40:03] **Adam:** Right.

[00:40:03] **Adam:** So Safari doesn't have, uh, extensions like Chrome and Firefox.

[00:40:07] **Adam:** Right.

[00:40:07] **Adam:** So you.

[00:40:08] **Adam:** It works a little differently there.

[00:40:09] **Ben:** Classic.

[00:40:10] **Carol:** Mhm

[00:40:10] **Adam:** I, um, don't know the first thing about how they work, but I was like, I, you know, I can read documentation, I can prompt, I can probably figure this out for a person, uh, who's asking for it.

[00:40:12] **Ben:** Mhm.

[00:40:20] **Adam:** And I was interested in

[00:40:21] **Tim:** Mhm.

[00:40:23] **Adam:** the process of figuring out how to do that.

[00:40:25] **Adam:** Right.

[00:40:25] **Adam:** For me it was an exercise in learning how to use LLMs to get this particular thing done.

[00:40:25] **Carol:** mhm.

[00:40:30] **Adam:** It wasn't like I want to make this extension to be famous or whatever, or plugin.

[00:40:34] **Adam:** Um, and so

[00:40:36] **Adam:** the way I was thinking about that is

[00:40:41] **Adam:** you're asking somebody to install something in their web browser, which is an incredibly sacred space.

[00:40:41] **Tim:** Mhm.

[00:40:46] **Ben:** Yeah, very intimate.

[00:40:48] **Ben:** Uh, mhm,

[00:40:48] **Carol:** Very.

[00:40:49] **Adam:** And so by making it open source, it's, you're, you're asking for that trust and, and saying like, look, if you don't trust me, then you can look at the source code yourself and see if there's anything malicious in it.

[00:40:59] **Adam:** so there, I think that is an interesting angle like, or an interesting foil to your argument that if it's open, it's perform.

[00:41:08] **Tim:** This day and age, if I want to see if

[00:41:11] **Tim:** repo, uh, is safe, I'm just going to point Claude at it and say, is it safe?

[00:41:14] **Carol:** You can ask.

[00:41:15] **Carol:** Yeah.

[00:41:15] **Adam:** Well.

[00:41:15] **Carol:** Yeah.

[00:41:15] **Adam:** Sure.

[00:41:15] **Adam:** But if it's not open.

[00:41:15] **Carol:** Do a security review.

[00:41:17] **Ben:** Sa.

[00:41:17] **Tim:** It's not op.

[00:41:17] **Adam:** If it's not open, then you can't do that.

[00:41:17] **Carol:** Yeah.

[00:41:17] **Tim:** You can't do it.

[00:41:18] **Tim:** Right.

[00:41:18] **Tim:** Yeah, for sure.

[00:41:18] **Carol:** Sam.

[00:41:19] **Carol:** Mhm.

[00:41:19] **Tim:** Yep.

[00:41:20] **Adam:** and then the other thing going through my head while you were talking, Ben, was like, I have, I have these memories from before.

[00:41:27] **Adam:** LLMs were a thing of like looking at somebody's repo and being completely 150% baffled by how they chose to organize their source code and, and like feeling at the.

[00:41:40] **Tim:** Blog.

[00:41:41] **Tim:** CFC

[00:41:43] **Adam:** Hey, let's not call any particular.

[00:41:43] **Carol:** It.

[00:41:45] **Adam:** Raymond Camden's out.

[00:41:47] **Adam:** Um,

[00:41:47] **Tim:** I don't know.

[00:41:48] **Tim:** It was Scott.

[00:41:49] **Tim:** I don't.

[00:41:49] **Tim:** Ray didn't start that one.

[00:41:50] **Tim:** I don't know who started that way.

[00:41:51] **Tim:** Scott eventually maintained it because I remember interviewing him.

[00:41:51] **Ben:** Mhm,

[00:41:54] **Tim:** I had like an early.

[00:41:54] **Tim:** Like,

[00:41:56] **Adam:** I'm pretty sure Ray started it anyway.

[00:41:57] **Tim:** did he already?

[00:41:58] **Tim:** Yeah, it's one giant CFC Huge.

[00:42:00] **Adam:** Yeah, yeah, yeah.

[00:42:01] **Carol:** Mhm mhm.

[00:42:02] **Adam:** so I had this experience of looking at somebody's repo for an open source project.

[00:42:02] **Tim:** Mhm.

[00:42:06] **Adam:** I was like, I wanna, I wanna try to understand how this works or like, can I add this, this feature onto it or whatever.

[00:42:12] **Adam:** And I, I find myself, I have found myself at times kind of wondering am I insane or is this person insane?

[00:42:21] **Adam:** Right?

[00:42:21] **Adam:** Like ah, am I a terrible developer?

[00:42:21] **Tim:** Mhm.

[00:42:22] **Ben:** Mhm.

[00:42:23] **Adam:** And they're just like, uh, so far above me that I, I am not capable of understanding the world from their perspective or, or are they completely unhinged and this is absolute garbage.

[00:42:28] **Carol:** Can't comprehend.

[00:42:30] **Carol:** Yes.

[00:42:35] **Adam:** And I like, you can't tell sometimes.

[00:42:40] **Ben:** No, it's true.

[00:42:40] **Ben:** And, and uh, okay, so if I, if I can make it personal for a second, I, I've mentioned on previous shows that I'm working on this syntax highlighting Lambda function and I will probably eventually push it up to GitHub, um, and I'll make that repository public because,

[00:42:42] **Tim:** Mhm.

[00:42:56] **Ben:** you know, in a, in a very clear way it's performative that this is something I build and it's for me, but I'm proud of the fact that it's working.

[00:42:58] **Adam:** That's your performance.

[00:43:00] **Carol:** Mhm.

[00:43:03] **Tim:** Mhm.

[00:43:07] **Ben:** And the way it works is there's a kind of a Lambda function adapter and then a local Node server adapter so I can use it locally without calling the lambda function.

[00:43:16] **Ben:** And there's a bunch of stuff in the Node server adapter that doesn't need to be there.

[00:43:22] **Ben:** Like there's a lot of real, as Claude would say, belt and suspenders, uh, security aspects where it's checking like, oh, did I pass a malicious URL parameter or did I malform the body on purpose?

[00:43:24] **Tim:** Mhm.

[00:43:26] **Adam:** Mhm.

[00:43:33] **Adam:** Right.

[00:43:34] **Ben:** And I keep going back to it.

[00:43:36] **Ben:** I'm like, I don't need this.

[00:43:38] **Ben:** This is only ever for local development.

[00:43:40] **Ben:** And it'll be like, oh, what if this code ever accidentally ships to production?

[00:43:43] **Ben:** I'm like, it won't.

[00:43:45] **Ben:** And the thing is like, the reason that that's important to me is because when it goes live and someone looks uh, at that file, they will have the knee jerk reaction just like you're saying like, why is this code here?

[00:43:46] **Tim:** Mhm.

[00:43:49] **Carol:** Hm.

[00:43:56] **Ben:** Like, this is for local development.

[00:43:58] **Ben:** Why is he checking for malicious arguments in a dev only server?

[00:44:03] **Ben:** And like, because it's a performance and I don't want that there because it's not just slop the moment it goes live and the moment my name is attached to it.

[00:44:05] **Tim:** Mhm.

[00:44:14] **Ben:** Anyway, I don't, this, I'm, I'm, I don't want to on for too long here.

[00:44:17] **Ben:** I'll just say like, it's.

[00:44:19] **Ben:** I feel like we, at the end of the day and this is the like the big problem I think with LinkedIn is almost like everybody is performing but, but they've like forgotten the fact that they're performing and it's become this like really weird ecosystem.

[00:44:29] **Carol:** I think.

[00:44:32] **Tim:** Yeah, I think, I think LinkedIn's a low bar there, but okay.

[00:44:34] **Carol:** Yeah.

[00:44:35] **Carol:** Yeah.

[00:44:36] **Carol:** I think the problem with LinkedIn is that you're using LinkedIn for information.

[00:44:42] **Ben:** I feel like I'm using it as a, as a signal Not necessarily information, but, but yes.

[00:44:49] **Ben:** Uh, all right, I'm done.

## [00:44:50] Meetings Are For Decisions

[00:44:50] **Carol:** Mhm

[00:44:51] **Adam:** Okay, well then I guess that makes it my turn, right?

[00:44:53] **Adam:** That what we're doing.

[00:44:53] **Tim:** Your turn, Adam Mhm.

[00:44:54] **Tim:** Yeah.

[00:44:54] **Ben:** Hit.

[00:44:55] **Adam:** So I, I was having a conversation with a bunch of people yesterday and we were talking about getting everybody together.

[00:44:59] **Ben:** Mhm.

[00:45:04] **Adam:** This was.

[00:45:04] **Adam:** So I guess I'll give the full context.

[00:45:05] **Tim:** Mhm.

[00:45:06] **Adam:** I um, am on the board of my skydiving club.

[00:45:10] **Carol:** m fancy.

[00:45:10] **Adam:** and uh, and we were discussing the possibility of starting to use some software to do our video editing.

[00:45:17] **Ben:** Mhm mhm.

[00:45:18] **Adam:** It's like AI video editing stuff.

[00:45:21] **Adam:** Um, and you know, the board I forget exactly how it came up, but the board was initially investigating it and we had like a little committee where three or four of us went and saw a demo of this software.

[00:45:24] **Tim:** Mhm.

[00:45:31] **Adam:** And now, you know, we're like, okay, this is definitely interesting and worth continuing to consider.

[00:45:36] **Adam:** Let's bring in all the people that it would affect.

[00:45:38] **Adam:** Right?

[00:45:39] **Adam:** So this is, basically it would affect the Tandem instructors and the people who shoot video and maybe the people who run Manifest, which is like the front desk.

[00:45:43] **Tim:** Mhm.

[00:45:47] **Carol:** Mhm.

[00:45:47] **Adam:** um.

[00:45:47] **Adam:** And so it was like, let's get them all on the same page.

[00:45:51] **Adam:** I started like a group chat, uh, and we started talking about, okay, well, when do we want to get together?

[00:45:55] **Adam:** This is kind of the general idea of what we want to talk about.

[00:45:58] **Adam:** And immediately people started asking a bunch of questions and I'm like, this is why we want to get everybody together.

[00:46:03] **Tim:** Mhm.

[00:46:04] **Adam:** I don't want to have to have.

[00:46:05] **Adam:** There's too much information to hash out in a group chat, right.

[00:46:07] **Carol:** Mhm.

[00:46:07] **Ben:** Mhm yo.

[00:46:08] **Carol:** Yeah.

[00:46:09] **Adam:** And somebody said something that I really loved and it also proved me wrong.

[00:46:15] **Adam:** Right.

[00:46:15] **Adam:** Like I was saying, I don't want to have to discuss all this in a group chat.

[00:46:18] **Adam:** It's too much.

[00:46:19] **Adam:** And this person said, meetings are for making decisions, not for sharing information.

[00:46:24] **Tim:** Mhm.

[00:46:25] **Adam:** And I 100% subscribe to that.

[00:46:25] **Ben:** M.

[00:46:28] **Adam:** Like, I, I believe that is true.

[00:46:30] **Adam:** I love that way of thinking about meetings because it, you know, who among us has not attended a meeting and said that should have been an email.

[00:46:37] **Adam:** Right?

[00:46:37] **Carol:** Yeah.

[00:46:37] **Ben:** Mhm mhm.

[00:46:38] **Adam:** Um, and so as a result of, of that comment, I ended up taking like two hours last night and I wrote down all of, you know, I just brain dumped and organized and rewrote it and reorganized and brain dumped over and over and over until I had this, like, if you print it out, it's probably like three pages, uh, long email, um, of like all this information so that we can get everybody on the same page and so everybody can come to the meeting.

[00:46:38] **Carol:** Sam.

[00:47:00] **Tim:** That's uh, three pages.

[00:47:01] **Tim:** Sounds more like a manifesto.

[00:47:03] **Carol:** Hahaha.

[00:47:03] **Adam:** Well, but it's, this is like, you know, here's how the software works.

[00:47:03] **Tim:** Mhm.

[00:47:06] **Adam:** I'm basically just trying to anticipate all the questions that we're going to get because this is not like a little like, you know, drop your clips here and it renders the video.

[00:47:07] **Carol:** Mhm.

[00:47:14] **Tim:** Sam.

[00:47:14] **Adam:** There's a lot to it, right?

[00:47:16] **Adam:** There's different pricing structures and upsells and selling after the fact.

[00:47:18] **Ben:** Mhm mhm.

[00:47:20] **Adam:** And uh, you know, it affects the way that the videographers work and it affects timing and it affects who gets paid how much.

[00:47:24] **Tim:** Mhm.

[00:47:27] **Adam:** And you know, there's a thousand little things.

[00:47:28] **Carol:** Mhm

[00:47:29] **Adam:** and so, you know, I wrote all that up.

[00:47:32] **Adam:** And I sent out this long email and then I sent a note to the group chat.

[00:47:35] **Adam:** I was like, okay, I sent everybody an email.

[00:47:38] **Adam:** Now we all have all of the information I could possibly think of.

[00:47:41] **Adam:** If you have questions, reply to the email.

[00:47:43] **Adam:** Uh, and let's all come to this meeting on Saturday to be prepared to discuss and go from there.

[00:47:47] **Carol:** mhm.

[00:47:50] **Adam:** But I just really liked that, uh, way of framing it.

[00:47:54] **Adam:** Right.

[00:47:54] **Adam:** Meetings are for making decisions, not for sharing information.

[00:47:57] **Ben:** Mhm mhm.

[00:47:58] **Carol:** Sam.

[00:47:58] **Tim:** M.

[00:47:59] **Tim:** It kind of reminds me of how Jeff Bezos does meetings.

[00:48:02] **Tim:** Not that I'm a fan of his, but one thing he does for meetings is they'll have an agenda.

[00:48:02] **Adam:** Okay.

[00:48:06] **Carol:** Mhm.

[00:48:08] **Tim:** They'll print it out or distribute it some sort of way.

[00:48:11] **Tim:** And then at the beginning of the meeting they'll have enough time and they'll say, they just sit there and read.

[00:48:17] **Adam:** Mm.

[00:48:18] **Tim:** And, and once everyone is done reading, they discuss.

[00:48:19] **Adam:** So.

[00:48:21] **Adam:** Yep,

[00:48:22] **Tim:** Which I think is uh, because that's the main thing.

[00:48:24] **Tim:** Problem with meetings is like you're running from thing to thing to thing and you get into the meeting and you're completely blind.

[00:48:27] **Carol:** Right.

[00:48:28] **Adam:** Yeah.

[00:48:29] **Carol:** Yeah.

[00:48:30] **Adam:** Yep.

[00:48:30] **Tim:** Right.

[00:48:30] **Carol:** I'm like, what is this one?

[00:48:30] **Tim:** You, you probably have, yeah, 80% of the time, 90% time.

[00:48:33] **Carol:** Mhm.

[00:48:34] **Tim:** You've not prepared for this meeting unless you're extremely worried about something.

[00:48:37] **Tim:** And uh, at that point it's probably too late.

[00:48:40] **Adam:** And if you're the type of person that has 10 meetings a day, yeah, I totally see that.

[00:48:43] **Tim:** Exactly.

[00:48:43] **Ben:** Mhm mhm.

[00:48:44] **Adam:** However, my company tried to do that.

[00:48:47] **Adam:** We tried to do that just with our stand up.

[00:48:48] **Carol:** Mhm.

[00:48:48] **Adam:** Right.

[00:48:49] **Tim:** Mhm.

[00:48:49] **Adam:** So like everybody, we had a shared Notion doc and it was your responsibility to go in and write down your, your notes for standup in this Notion doc in advance of the meeting.

[00:49:00] **Adam:** And then we would show up to the meeting and we would just be like, okay, everybody start reading.

[00:49:04] **Adam:** And everybody would read.

[00:49:05] **Adam:** And I think we, our system was like when you unmute yourself in the video chat because it's again, we're fully remote.

[00:49:12] **Adam:** when you unmute yourself, you're indicating, okay, I'm done reading.

[00:49:15] **Adam:** and I mean there was so much pressure to be a fast reader.

[00:49:19] **Adam:** I felt bad.

[00:49:19] **Ben:** Yo.

[00:49:19] **Ben:** I'm such a slow reader.

[00:49:20] **Adam:** I felt like, yeah, I'm a slow reader.

[00:49:21] **Carol:** Such a slow reader.

[00:49:21] **Tim:** You want to be last.

[00:49:22] **Adam:** And, and, and then you're wasting people's time because they're done reading and, and uh, there's still somebody that's still reading, you know.

[00:49:28] **Tim:** Yeah, but what, uh, I mean, you said stand up.

[00:49:30] **Tim:** I don't think stand ups typically have huge decision points.

[00:49:36] **Adam:** No, you're right, they don't.

[00:49:37] **Adam:** But they do.

[00:49:38] **Adam:** It is a, uh, I mean that meeting in particular is maybe a bad example because the whole point is information sharing.

[00:49:43] **Carol:** Yeah.

[00:49:43] **Carol:** It's just.

[00:49:43] **Adam:** But

[00:49:44] **Carol:** What's going on?

[00:49:45] **Carol:** Mhm.

[00:49:45] **Adam:** yeah.

[00:49:46] **Adam:** And you know, I will say we are probably not a good example of how to run a good stand up because ours tend to run for 20 to 30 minutes for like eight people.

[00:49:53] **Carol:** Oh my gosh.

[00:49:55] **Adam:** Well, it's a, there's a lot of information sharing.

[00:49:57] **Adam:** Right.

[00:49:57] **Adam:** We're,

[00:49:57] **Carol:** Huh?

[00:49:58] **Tim:** Yeah.

[00:49:58] **Ben:** Yeah.

[00:49:58] **Ben:** Plus you gotta talk about movies.

[00:50:00] **Adam:** it's like, no, this is, all, all on point on top.

[00:50:06] **Tim:** But I mean, I think the point that you were actually making was that it's like you can't make a decision during a meeting unless you have the information first.

[00:50:14] **Tim:** And a lot of people don't come into the meeting with the information they need to make a decision.

[00:50:19] **Adam:** Mhm.

[00:50:20] **Carol:** Yeah.

[00:50:20] **Carol:** Most of my meetings I leave with action items for the next meeting to make the decision.

[00:50:22] **Tim:** Exactly.

[00:50:25] **Tim:** Yeah, that kind of seems.

[00:50:26] **Tim:** Yeah, but, but I agree with you.

[00:50:27] **Adam:** Yeah.

[00:50:28] **Tim:** I.

[00:50:29] **Tim:** That is the ideal situation where you can go into a meeting and make a decision.

[00:50:30] **Carol:** Yeah,

[00:50:33] **Carol:** I I was in with another team like two weeks ago and the guy started the call and right after we're all like, yeah, we're here, ready to go.

[00:50:40] **Carol:** He goes, okay, well, let me start by saying this.

[00:50:42] **Carol:** If this meeting isn't for you, leave.

[00:50:44] **Carol:** And, and if any point, like during this meeting, this isn't for you, leave.

[00:50:48] **Carol:** No harm, no foul.

[00:50:49] **Carol:** I don't want to waste your time, so just drop.

[00:50:52] **Carol:** I was like, oh, wow, everyone should do that.

[00:50:54] **Tim:** I m.

[00:50:54] **Tim:** Love it,

[00:50:55] **Carol:** Everyone should do that.

[00:50:55] **Ben:** Mhm.

[00:50:55] **Tim:** love it, love it.

[00:50:57] **Adam:** Yeah.

[00:50:57] **Adam:** We, we have a customer that loves to schedule meetings.

[00:51:00] **Adam:** Like, uh, just about every ticket.

[00:51:01] **Adam:** They're like, and can we schedule a meeting to go into this further?

[00:51:03] **Adam:** I'm like, no, that's the whole point of tickets.

[00:51:05] **Adam:** To have a written record

[00:51:06] **Carol:** Mhm.

[00:51:08] **Adam:** and to be able to do it async.

[00:51:08] **Ben:** I will.

[00:51:09] **Tim:** I, I did kill Claude.

[00:51:10] **Tim:** Claude would like, have an automated email generator and at the end it would like, if you'd like to hop on a quick call so we can go over this.

[00:51:19] **Tim:** I'm like, stop that.

[00:51:19] **Carol:** No, no,

[00:51:20] **Tim:** Never global rule.

[00:51:22] **Tim:** Never ever offer me to get on, uh, a phone call because that is not going to happen.

[00:51:27] **Adam:** Mhm.

[00:51:28] **Tim:** I do not want to do it.

[00:51:29] **Tim:** If we can't figure this, I will decide when we need a meeting and it's going to be bad.

[00:51:34] **Carol:** Sam.

[00:51:35] **Ben:** I do like the idea that meetings are for making decisions.

[00:51:35] **Carol:** Mhm.

[00:51:38] **Ben:** I, I, I, I, I also agree with Tim.

[00:51:40] **Ben:** I like to have the reading time up front if, if it's like based on a bunch of information.

[00:51:45] **Ben:** But I can't stand the idea of asynchronous decision making.

[00:51:50] **Ben:** Trying to gather consensus over text is bonkers to me.

[00:51:50] **Adam:** Mhm.

[00:51:52] **Adam:** Right.

[00:51:54] **Tim:** Mhm,

[00:51:56] **Ben:** I, I agree with a lot of what the Basecamp people say, the 37signals people say, but they are huge proponents of asynchronous decision making and I think that's crazy.

[00:51:56] **Adam:** Yeah, yeah, yeah.

[00:52:06] **Ben:** It's worked for them, but I think it's crazy.

[00:52:07] **Adam:** Well

[00:52:09] **Adam:** you, you said you kind of equated asynchronous with text and that's not necessarily true.

[00:52:14] **Adam:** Right.

[00:52:14] **Adam:** Like if you all happen to be sitting there at your Slack or Discord or Microsoft Teams or whatever.

[00:52:15] **Tim:** Mhm.

[00:52:20] **Adam:** Um, then, then it can be live and text based.

[00:52:23] **Adam:** But

[00:52:23] **Ben:** Even so, I just feel like the fidelity of a voice conversation is

[00:52:26] **Adam:** yeah,

[00:52:28] **Adam:** agreed.

[00:52:28] **Ben:** non comparable.

[00:52:29] **Adam:** And, and, and you know, being able to rapidly hear somebody's opinion and think about, you know, how that changes your opinion or, or how you might want to change their opinion or whatever.

[00:52:29] **Carol:** Yeah,

[00:52:37] **Carol:** Yeah,

[00:52:41] **Adam:** Yeah, that's a lot less frustrating over voice than.

[00:52:44] **Ben:** Mhm mhm.

[00:52:45] **Tim:** Uh, and I think it's, I think it's more about, also about focus.

[00:52:48] **Tim:** Right.

[00:52:49] **Tim:** So if I'm on a call and I kind of just hear you go silent, you haven't said anything for two minutes, I'm like, so what you thinking?

[00:52:56] **Tim:** What's going on over there?

[00:52:57] **Adam:** Yeah,

[00:52:58] **Tim:** You know, it's like if you're sitting waiting for an email or a message or a Slack or whatever, you're like,

[00:53:05] **Tim:** you just go, well, you start looking at something else.

[00:53:07] **Tim:** But if it's, if it's voice, you're like, okay, I'm talking to you.

[00:53:08] **Carol:** Yeah,

[00:53:11] **Tim:** I can like nudge you.

[00:53:13] **Tim:** I think that really, that initial instantaneous feedback is extremely important for some things.

[00:53:16] **Adam:** Yeah,

[00:53:18] **Carol:** Yeah.

[00:53:19] **Adam:** I, I do think the pre read is a good idea.

[00:53:21] **Adam:** I just don't like the idea of doing it in the meeting.

[00:53:24] **Tim:** Yeah,

[00:53:24] **Adam:** Like, uh, uh, maybe at a certain level where you are, where Bezos and his, you know, C-suite are in, they do nothing but meetings.

[00:53:26] **Ben:** Mhm mhm.

[00:53:27] **Carol:** Hm.

[00:53:32] **Adam:** You know, that, that makes more sense than uh, than me and my meetings.

[00:53:32] **Tim:** Right.

[00:53:37] **Adam:** Right.

[00:53:37] **Adam:** I have a handful of meetings in a week.

[00:53:40] **Adam:** I have like three meetings in a week.

[00:53:40] **Tim:** I think it depends on the scale of the decision you're making or if it's a really, really big decision.

[00:53:44] **Tim:** You need to make sure everyone's read in.

[00:53:47] **Carol:** Mhm.

[00:53:47] **Tim:** Right.

[00:53:47] **Adam:** Yeah,

[00:53:47] **Tim:** A, uh, stand.

[00:53:48] **Tim:** A, uh, stand up.

[00:53:48] **Tim:** Not that important.

[00:53:50] **Tim:** Like, you know, a retrospective.

[00:53:52] **Tim:** Not that important.

[00:53:53] **Tim:** You, you, you were there, it happened.

[00:53:55] **Tim:** But if this is like, hey, we're planning for all of 2028, what are we going to do?

[00:54:01] **Tim:** You need everyone's focus and attention.

[00:54:03] **Tim:** You need to make sure that everyone is locked in and is on the same page.

[00:54:05] **Adam:** Yeah,

[00:54:07] **Adam:** that.

[00:54:07] **Adam:** I think, uh, that I've been sitting here trying to think about how to bring this point in which is, you know, uh, a meeting or a topic where you want input from multiple people

[00:54:08] **Ben:** Mhm.

[00:54:11] **Carol:** Mhm.

[00:54:15] **Carol:** Mhm,

[00:54:19] **Adam:** versus like.

[00:54:20] **Adam:** So this software, uh, thing I was talking about, I wasn't the only one that attended the demo, but I, I took notes.

[00:54:20] **Tim:** Mhm,

[00:54:26] **Adam:** I, you know, had all the information at hand to be able to share it.

[00:54:29] **Adam:** I, I made my own spreadsheet to look at the pricing and I had links to share and that sort of thing.

[00:54:33] **Adam:** So I took it upon myself to write it all up and I, I left room.

[00:54:36] **Carol:** mhm,

[00:54:36] **Adam:** It's like, you know, if you feel like there's something else that belongs here, then say so.

[00:54:40] **Adam:** But

[00:54:41] **Tim:** Mhm,

[00:54:41] **Adam:** like with our standup doc, right, the expectation is everybody on the team has something to contribute to that document.

[00:54:46] **Adam:** You have, this is what's going on, this is what might be blocking you, this is what's coming,

[00:54:46] **Ben:** Mhm mhm.

[00:54:51] **Adam:** versus uh, you know, like that the thing, or another way to think about the thing I sent out last night was like, you know, potentially it's basically just me writing a document.

[00:54:54] **Carol:** Mhm.

[00:54:59] **Adam:** Here's what's going on, here's the information, and now you have it and you can be prepared for the meeting.

[00:54:59] **Tim:** Mhm,

[00:55:05] **Adam:** Right?

[00:55:05] **Adam:** Like read this, understand it, prepare some questions, whatever.

[00:55:09] **Adam:** It's.

[00:55:10] **Adam:** I think they're slightly different.

[00:55:12] **Adam:** Jumping off points for the meeting.

## [00:55:14] Meeting Recordings and Calendar Hygiene

[00:55:14] **Ben:** I throw in some meeting hot takes see how I see how these land.

[00:55:17] **Carol:** Yeah.

[00:55:17] **Adam:** Sure.

[00:55:17] **Tim:** Mhm.

[00:55:18] **Ben:** I think one, I think meetings should basically never be recorded.

[00:55:23] **Ben:** I think recorded m meetings make people lazy and they believe like, oh, I'll just go back and watch the meeting, it won't be a problem to remember.

[00:55:23] **Carol:** Oh,

[00:55:33] **Ben:** And like also it gives people an excuse to not show up to a meeting because they'll just catch the recording.

[00:55:33] **Adam:** Hm.

[00:55:38] **Ben:** I feel like nobody watches the recordings.

[00:55:41] **Tim:** 100% disagree

[00:55:41] **Ben:** And,

[00:55:43] **Ben:** and if uh, what's the way.

[00:55:43] **Carol:** I agree.

[00:55:43] **Adam:** Are we, are we doing Subway Takes on, on Ben's meeting takes now?

[00:55:46] **Tim:** 100.

[00:55:46] **Tim:** Yeah, it's uh, my car.

[00:55:47] **Carol:** Disagree.

[00:55:48] **Ben:** What's a Subway Take

[00:55:48] **Carol:** Yeah.

[00:55:48] **Tim:** 100% disagree

[00:55:50] **Ben:** Is a Subway Take a meme?

[00:55:52] **Adam:** It's a vertical video thing.

[00:55:54] **Adam:** Uh, this guy sits on the subway and they use, they like clip a microphone to the back of their like subway card or whatever.

[00:55:55] **Tim:** On YouTube.

[00:56:00] **Ben:** Oh, I've, I've seen that.

[00:56:00] **Tim:** That.

[00:56:00] **Tim:** Yeah, they're transient.

[00:56:01] **Adam:** Yeah, yeah.

[00:56:01] **Ben:** I didn't know that was a thing.

[00:56:02] **Adam:** And if somebody says like a hot take and this guy, his first response is always, he thinks about it for a second.

[00:56:03] **Ben:** Okay.

[00:56:07] **Adam:** He goes, Either 100% agree or 100% disagree and then they discuss it and get into the nuance or whatever.

[00:56:11] **Ben:** Mhm, gotcha.

[00:56:12] **Adam:** But.

[00:56:13] **Tim:** Yeah.

[00:56:13] **Ben:** All right, so, so

[00:56:14] **Tim:** So, uh, 100% disagree, Ben.

[00:56:17] **Ben:** disagree.

[00:56:18] **Tim:** And only for one reason.

[00:56:19] **Tim:** And that is AI can summarize your meetings for you.

[00:56:20] **Ben:** Hit it.

[00:56:20] **Adam:** and.

[00:56:23] **Tim:** That's the, that's the reason I record it.

[00:56:23] **Carol:** Yes.

[00:56:25] **Tim:** I attend the meetings.

[00:56:26] **Tim:** I don't skip them because they're recorded.

[00:56:27] **Tim:** I attend.

[00:56:27] **Carol:** Right.

[00:56:28] **Tim:** Attend the meetings, but I hate taking notes.

[00:56:30] **Tim:** I'm not a note taker.

[00:56:32] **Tim:** I want to be focused on.

[00:56:32] **Ben:** Okay, so hot take number two.

[00:56:32] **Adam:** Yeah.

[00:56:34] **Tim:** I want to be focused and engaged with the conversation, not note taking.

[00:56:37] **Carol:** Agree,

[00:56:40] **Tim:** And I don't want to.

[00:56:41] **Tim:** And let's face it, a lot of times it's like, hey, Sarah, will you take the notes?

[00:56:44] **Tim:** It's like it's always a female name.

[00:56:46] **Tim:** It's like, I don't want to be that guy.

[00:56:47] **Adam:** Mhm.

[00:56:48] **Tim:** So like, I have an AI that can take all the notes.

[00:56:50] **Adam:** Sam.

[00:56:50] **Tim:** And then at the end of the day, I have a skill that goes through and says summarize all my meetings, generate to do lists and everything.

[00:56:54] **Carol:** Sam.

[00:56:55] **Carol:** Mhm.

[00:56:57] **Tim:** So yeah, so go ahead.

[00:56:59] **Ben:** All right, so hot take number two feeds directly onto that.

[00:56:59] **Tim:** Do you?

[00:57:02] **Ben:** I feel like there should never be a note taker.

[00:57:05] **Ben:** The person who is driving the meeting, who ultimately is responsible for making whatever decision needs to be made.

[00:57:11] **Ben:** They're the only ones who should be taking notes.

[00:57:13] **Ben:** I mean you could take notes if you want to take notes for your own personal edification.

[00:57:15] **Adam:** Mm mhm.

[00:57:16] **Tim:** Yeah.

[00:57:16] **Tim:** But what meeting is where there's only one person making decision?

[00:57:19] **Tim:** If one person made the decision, they don't need a meeting.

[00:57:20] **Carol:** Right.

[00:57:21] **Tim:** They don't.

[00:57:21] **Carol:** There's not even a meeting Yeah.

[00:57:22] **Tim:** They just do it.

[00:57:22] **Adam:** Well uh, no, every, every decision should have one person who is ultimately responsible.

[00:57:26] **Ben:** Uh,

[00:57:28] **Ben:** a DRI What is it like the directly responsible individual?

[00:57:29] **Adam:** Yeah.

[00:57:30] **Adam:** Directly responsible individual.

[00:57:31] **Adam:** Yeah.

[00:57:32] **Tim:** Are you doing RACI here?

[00:57:33] **Tim:** Okay.

[00:57:37] **Ben:** Uh, yeah, I feel like note taking.

[00:57:39] **Ben:** I don't know.

[00:57:40] **Ben:** I just feel like, I think there is a skill to shorthand and I think the act of writing stuff down and like learning a little bit of shorthand and like you do some little diagrams and you circle some stuff and you draw some arrows and you write some keywords and then like that helps codify it in your head what it is you're talking about.

[00:57:42] **Tim:** Mhm,

[00:57:42] **Adam:** Mhm.

[00:57:58] **Ben:** And it also, I think meaningfully adds some good friction to the meeting.

[00:58:03] **Tim:** Mhm,

[00:58:03] **Carol:** Mhm.

[00:58:05] **Ben:** Slows it down in certain parts where you want to make sure that you got the right thing.

[00:58:05] **Adam:** It.

[00:58:08] **Ben:** And also like you can lean into the idea that if an important thing slips through the cracks, it'll be brought back up by somebody who's like, hey, what happened to that thing we discussed?

[00:58:17] **Ben:** So those are like my two big hot takes.

[00:58:20] **Carol:** As someone who has ADHD I can tell you transcription saves me.

[00:58:21] **Adam:** Mhm,

[00:58:23] **Tim:** Mhm,

[00:58:25] **Carol:** I was in the meeting today and I was taking my own little notes because I didn't have the ability to start transcription because it was an outside meeting.

[00:58:33] **Carol:** I got stuck for several sentences trying to figure out how to spell the word acquisitions.

[00:58:39] **Ben:** Mhm.

[00:58:40] **Carol:** And uh, I was like, wait, I have a letter wrong here.

[00:58:42] **Carol:** And I realized I've been staring at this word like, trying to like, like go.

[00:58:43] **Tim:** Mhm.

[00:58:47] **Carol:** What letter is off here?

[00:58:48] **Carol:** I quit listening.

[00:58:49] **Adam:** Mhm,

[00:58:49] **Carol:** I quit listening.

[00:58:50] **Carol:** So like, I, I asked someone who has ADHD I have to have transcriptions, otherwise you're not going to get the output from me for what the action items are or what I need to do after.

[00:59:03] **Ben:** That's fair.

[00:59:04] **Ben:** And I will say, you know, full disclosure, I have never been in a role where I have to do back to back meetings and I think that would significantly change because I get to the end of a meeting now and I have like a few minutes to debrief and look at my notes and then like write some additional notes.

[00:59:11] **Carol:** Oh, uh-huh.

[00:59:20] **Tim:** Oh,

[00:59:20] **Adam:** Mhm,

[00:59:21] **Tim:** oh, sweet summer child.

[00:59:23] **Carol:** Yeah.

[00:59:24] **Ben:** If I, if I had to go back to back meetings, I feel like that would be much more challenging for sure.

[00:59:24] **Carol:** One.

[00:59:24] **Adam:** Mhm.

[00:59:27] **Tim:** M m.

[00:59:29] **Tim:** Let me show you my calendar from today.

[00:59:32] **Carol:** Yeah, I will tell you there.

[00:59:33] **Carol:** I have a Wednesday.

[00:59:34] **Carol:** Like, Wednesdays are awful.

[00:59:36] **Carol:** Like Tuesdays and Wednesdays are really awful for meetings.

[00:59:37] **Ben:** Mhm.

[00:59:38] **Carol:** For me, every day is super busy.

[00:59:39] **Tim:** For me too.

[00:59:40] **Carol:** But Wednesdays and Tuesdays are just terrible.

[00:59:42] **Carol:** It's gotten so bad that every other Wednesday a meeting will start.

[00:59:46] **Carol:** I show up five minutes late and they now know it's because I haven't left my chair since I started work, which was around 7:15, it's now 11:15 and I have to pee.

[00:59:57] **Carol:** Like, I have to go pee.

[00:59:59] **Adam:** It's not an option.

[00:59:59] **Carol:** So they're like, yeah, they're like, she'll be here.

[01:00:01] **Tim:** I'm peeing right now.

[01:00:02] **Carol:** She'll.

[01:00:02] **Carol:** She'll be here.

[01:00:02] **Ben:** It.

[01:00:03] **Carol:** Like, you know, everybody gets the chance to pee.

[01:00:06] **Carol:** You guys block her off the entire morning and she doesn't get to move.

[01:00:09] **Carol:** So.

[01:00:11] **Carol:** Right, yeah.

[01:00:11] **Carol:** Okay, I'm back.

[01:00:12] **Ben:** Mhm.

[01:00:12] **Carol:** I'm.

[01:00:12] **Carol:** I'm in the meeting now.

[01:00:15] **Adam:** Yeah, I feel like all meeting software should have the ability to have like a little chyron at the bottom, like the little strip at the bottom of the news where you can just be like, uh, Adam colon is peeing.

[01:00:20] **Carol:** Mhm.

[01:00:26] **Adam:** We'll be.

[01:00:27] **Tim:** Mhm,

[01:00:27] **Carol:** Yes.

[01:00:27] **Carol:** Yeah,

[01:00:31] **Tim:** mhm,

[01:00:31] **Ben:** Yo, when you put an event in your calendar where you have to be somewhere, do you then also put a secondary event for traveling to that event

[01:00:37] **Adam:** Oh.

[01:00:41] **Carol:** No,

[01:00:43] **Adam:** I used to not I used to include travel time in the event itself.

[01:00:49] **Adam:** But then I would, then I would find myself looking at it going right, but is my doctor appointment at 2:15 or is it at 2 o'clock and I need to leave at 1:45 to get there by my 2 o'clock appointment

[01:00:49] **Ben:** Oh, gotcha.

[01:00:50] **Tim:** Mhm,

[01:00:55] **Ben:** Yeah.

[01:01:01] **Carol:** I'll tell you how to fix that.

[01:01:02] **Ben:** Mhm.

[01:01:02] **Carol:** I put travel in mine.

[01:01:03] **Carol:** And in the title I put what time my appointment is.

[01:01:06] **Carol:** So it'll say like Dr.

[01:01:08] **Adam:** M.

[01:01:08] **Carol:** And it says 2:15.

[01:01:10] **Carol:** And if I need 30 minutes travel then it's set for 30 minutes back.

[01:01:12] **Tim:** Mhm.

[01:01:13] **Carol:** But then I can just glance at it.

[01:01:15] **Carol:** I don't even have to think about it.

[01:01:16] **Carol:** It says doctor and the time.

[01:01:17] **Carol:** And I go, oh well this got scheduled for.

[01:01:20] **Carol:** And my block says 2:15 So I probably just hit the wrong button when I was standing at the receptionist, you know, and then I go look at it.

[01:01:27] **Carol:** But yeah, I always put the time in the title.

[01:01:30] **Adam:** M, I think I used to do that but then calendar apps started getting like natural language processing where if you write 2:00pm in the, in the title it's like oh okay, let me change the time.

[01:01:30] **Ben:** Mhm.

[01:01:35] **Ben:** Yes, I was just about to say that.

[01:01:37] **Carol:** Mhm.

[01:01:39] **Adam:** I'm like no.

[01:01:40] **Carol:** Mhm.

[01:01:40] **Ben:** Let me fix that for you.

[01:01:42] **Carol:** Yeah.

[01:01:42] **Adam:** Yeah.

[01:01:43] **Tim:** Stop it.

[01:01:43] **Ben:** Yeah, I love having the secondary travel, calendar.

[01:01:47] **Ben:** I don't know why, it just feels

[01:01:48] **Carol:** M.

[01:01:50] **Ben:** like a power move.

[01:01:51] **Adam:** Do any of you guys use any of those tools like Calendly or Cal.com where you can like let people sign up for blocks of time on your calendar without showing them what's on your calendar?

[01:01:59] **Tim:** Hell no.

[01:02:01] **Carol:** Yeah, we.

[01:02:01] **Carol:** I have a blocking one that's part of Outlook Outlook Mhm.

[01:02:04] **Ben:** Mhm.

[01:02:05] **Adam:** Yeah, I do have that and I think I'm um, I don't remember if it's in my email signature or not, but like I'll send out the link to people instead of like trying to send four emails back and forth to schedule.

[01:02:15] **Adam:** I'm like here you can look at my calendar here.

[01:02:18] **Adam:** You can either sign up through the website to, to schedule a meeting with me or you can just use it to find a time and send me your uh, Microsoft Teams meeting link or whatever for that time.

[01:02:29] **Ben:** I don't know if this is a generational thing or if this is just a me thing, but I feel like I grew up where the only way to get a link to somebody was, was to just paste the link into whatever you were sending.

[01:02:29] **Tim:** Mhm, mhm.

[01:02:30] **Carol:** Mhm.

[01:02:43] **Ben:** And so you're like, hey, something, something, something, check out this product colon and then some long ass Amazon URL and like even when I'm in Slack and I'll paste links into Slack and I just paste a long ass URL and usually put some sort of ellipsis in the middle so it's not so long ass.

[01:02:51] **Adam:** Yeah.

[01:02:51] **Tim:** Sa.

[01:02:51] **Carol:** Mhm.

[01:03:01] **Ben:** When I get an email where someone has actually like like linkified a sentence and a lot of times it'll be like grab time on my calendar.

[01:03:09] **Ben:** And the phrase grab time on my calendar is a link.

[01:03:12] **Adam:** Yeah.

[01:03:13] **Ben:** That to me feels like spam.

[01:03:15] **Ben:** It is hard for me.

[01:03:15] **Tim:** Feels like.

[01:03:15] **Adam:** Oh

[01:03:16] **Tim:** Yeah, the unsafe link.

[01:03:18] **Tim:** Yeah.

[01:03:18] **Tim:** You don't know.

[01:03:18] **Ben:** Or it's just like, like, like to me it signals a human didn't write this.

[01:03:19] **Adam:** m.

[01:03:23] **Ben:** Like this is not how humans communicate.

[01:03:26] **Ben:** Humans paste.

[01:03:26] **Adam:** That's so weird.

[01:03:27] **Ben:** L.

[01:03:28] **Adam:** That's so weird because like that's the whole uh, like the whole way the Internet worked before we had Slack and Discord and Twitter.

[01:03:29] **Carol:** Yeah.

[01:03:31] **Carol:** Mhm.

[01:03:36] **Tim:** And bad phishing scams.

[01:03:36] **Ben:** M right.

[01:03:36] **Ben:** But that was like, that was, that was pre canned.

[01:03:37] **Tim:** I mean, you don't.

[01:03:38] **Tim:** I'm, um.

[01:03:39] **Tim:** Mhm.

[01:03:39] **Ben:** You know, like I'm, I built this thing and here's the experience I want you to have to me.

[01:03:44] **Ben:** Like an email isn't an experience.

[01:03:45] **Ben:** It's a conversation.

[01:03:48] **Ben:** And even with Slack, you can, you know, you can highlight text and then paste a link into it, and it'll.

[01:03:51] **Carol:** Sam.

[01:03:52] **Carol:** Mhm.

[01:03:53] **Ben:** It'll linkify the text, but even that, you're like, just paste the text.

[01:03:58] **Ben:** Also, uh, what's on?

[01:03:59] **Ben:** I don't know.

[01:03:59] **Ben:** So.

[01:04:00] **Ben:** So I don't know if that's just a me thing or if that's just, like, the age I grew up in.

[01:04:05] **Tim:** You're all m dead.

[01:04:05] **Ben:** Yeah, yeah, exactly.

[01:04:05] **Adam:** Mhm.

[01:04:06] **Ben:** Schedule a meeting.

[01:04:08] **Adam:** I just so for the people listening, I just shared a screenshot in our, our back channel Discord chat of, of a uh, co workers email signature.

[01:04:09] **Ben:** Oh, yeah, yeah,

[01:04:13] **Carol:** Mhm.

[01:04:17] **Adam:** And it's got their name and our company and their pronouns and stuff.

[01:04:20] **Tim:** Mhm,

[01:04:20] **Adam:** And then at the bottom it says save a loop and schedule a meeting.

[01:04:23] **Adam:** And schedule a meeting is blue and underlined and I'm sure it takes you to their kind of thing.

[01:04:25] **Ben:** yeah.

[01:04:25] **Ben:** But.

[01:04:25] **Ben:** But, like, that's.

[01:04:26] **Ben:** That's what makes me think of it is, like, all of these calendar apps that I've ever received, they all have that same experience where it's a link.

[01:04:33] **Adam:** Yeah,

[01:04:34] **Ben:** Anyway.

[01:04:34] **Ben:** This is more about the Ben's performative experience of the world.

[01:04:35] **Adam:** I,

[01:04:37] **Adam:** I,

[01:04:38] **Adam:** I, I honestly I like the embedded link now.

[01:04:41] **Tim:** Mhm,

[01:04:42] **Adam:** I, I am also extremely careful about it, right?

[01:04:42] **Carol:** I do too.

[01:04:45] **Adam:** I'll hover over it and see where it's going.

[01:04:47] **Adam:** And if I don't like it, then I won't click it.

[01:04:48] **Adam:** But you know, I, I even do that in Discord messages right?

[01:04:52] **Adam:** And you can, you can just paste the link or I, I do it when I have a longer Discord message If I have.

[01:04:58] **Adam:** Or if I have multiple links to paste.

[01:05:00] **Ben:** Yeah, yeah, yeah,

[01:05:01] **Adam:** you know, I don't want to, I don't want to have four big ass links in there and make it hard for you to tell what's between them or, you know, where one stops and one begins.

[01:05:05] **Carol:** Sa.

[01:05:10] **Adam:** So I will like link text and you just use Markdown syntax You can drop the links in there.

[01:05:15] **Ben:** Yeah, yeah.

[01:05:16] **Adam:** But.

[01:05:16] **Ben:** Like, if I'm sharing a bunch of YouTube trailers or something to movies, I will oftentimes use the movie title.

[01:05:21] **Adam:** Do you do any real work or are you just always talking about TV and movies?

[01:05:26] **Carol:** Mhm.

[01:05:27] **Ben:** I want to say yes.

[01:05:28] **Ben:** And.

[01:05:33] **Adam:** All right, I think we, maybe we should wrap it up there.

[01:05:35] **Carol:** Mhm.

## [01:05:36] Patreon

[01:05:36] **Adam:** so this episode of Working Code is brought to you by Tim's LLM.

[01:05:39] **Carol:** Mhm.

[01:05:39] **Adam:** It brings all the boys to the yard.

[01:05:41] **Adam:** The, the, the.

[01:05:42] **Adam:** The dancing reaction doesn't really work on an audio format, Tim.

[01:05:46] **Adam:** Sorry.

[01:05:46] **Tim:** Oh, sorry.

[01:05:47] **Tim:** Yeah, uh, we'll have to sell that one as a GIF

[01:05:50] **Adam:** and listeners like you.

[01:05:51] **Adam:** If you're enjoying the show and you want to make sure that we can continue putting more of whatever this is out into the universe, you should consider supporting us on Patreon.

[01:05:58] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:06:03] **Adam:** Special thanks to our top patrons, Monte, Giancarlo and Peter.

[01:06:06] **Adam:** You guys rock.

[01:06:08] **Adam:** Thank you so much.

## [01:06:09] Thanks For Listening!

[01:06:09] **Adam:** Uh, we're gonna go record our Ted Lasso spoiler free after show.

[01:06:14] **Carol:** Maybe.

[01:06:15] **Tim:** Maybe.

[01:06:15] **Adam:** No, it's gonna be spoiler free or I'm gonna start punching people.

[01:06:20] **Adam:** Um,

[01:06:22] **Adam:** um, anyway, uh, you know what the after show is.

[01:06:24] **Adam:** You thought you support us financially.

[01:06:26] **Adam:** We reciprocate with more of our soothing, wonderful,

[01:06:30] **Carol:** Burps.

[01:06:31] **Adam:** uh, and farts and voices.

[01:06:34] **Tim:** ASMR

[01:06:34] **Adam:** Uh, and if that's.

[01:06:35] **Adam:** If that sounds like something that you want, then you can go to patreon.com/workingcodepod and sign up to be a patron of the show.

[01:06:42] **Adam:** We'd greatly appreciate it.

[01:06:43] **Adam:** That's going to do it for us this week.

[01:06:45] **Adam:** We'll catch you again next week.

[01:06:46] **Adam:** And until then,

[01:06:47] **Tim:** Listen, y'all you're not nearly as stressful as Ben's puppy stuff.

[01:06:51] **Tim:** So your heart matters

[01:07:18] **Carol:** And the after show.

[01:07:18] **Adam:** And

[01:07:20] **Adam:** after show.

[01:07:22] **Adam:** Ah, this.

[01:07:23] **Adam:** The after show has multiple gears.

[01:07:24] **Adam:** Now,

[01:07:24] **Carol:** Oh my goodness.

[01:07:24] **Tim:** It does.

[01:07:26] **Tim:** Sounds like,

[01:07:26] **Carol:** It was kind of having a seizure or something.

[01:07:28] **Tim:** like supercharged,

[01:07:30] **Adam:** I was visiting my brother a couple months ago and we watched some motocross.

[01:07:33] **Adam:** So,

[01:07:34] **Tim:** Uh,

[01:07:35] **Adam:** um, what is Widow's Bay

[01:07:38] **Tim:** Widow's Bay

[01:07:39] **Adam:** A Widow's Bay

[01:07:40] **Carol:** Did I spell it wrong?

[01:07:41] **Carol:** I really can't spell words.

[01:07:41] **Tim:** No, you spelled it right.

[01:07:42] **Carol:** Okay.

[01:07:43] **Adam:** I can't read.

[01:07:43] **Carol:** Widow's Bay is a series that's on Apple TV

[01:07:47] **Adam:** I think I've heard of this.

[01:07:48] **Carol:** We watched it and every episode I was like, we have to watch the next one.

[01:07:53] **Carol:** We have to watch the next one.

[01:07:55] **Carol:** It's one of those that just drags you in.

[01:07:58] **Carol:** And I thought it was, it was just going to be like a thriller kind of,

[01:08:02] **Carol:** kind of like show or serial killer kind of stuff.

[01:08:04] **Tim:** Mhm.

[01:08:04] **Adam:** Mm.

[01:08:04] **Adam:** Mhm.

[01:08:06] **Carol:** It wasn't.

[01:08:07] **Carol:** But it is so good and the characters are really awesome.

[01:08:13] **Carol:** Highly recommend it.

[01:08:15] **Tim:** So I mean, what's.

[01:08:16] **Tim:** Give me like no spoiler.

[01:08:17] **Tim:** But like, what's the.

[01:08:18] **Tim:** What's the premise?

[01:08:19] **Tim:** What's the kind of format?

[01:08:20] **Tim:** What's the genre?

[01:08:20] **Carol:** Yeah.

[01:08:21] **Carol:** There they are on this island, like a uh, New Englandy kind of island.

[01:08:26] **Carol:** And the island kind of comes to life

[01:08:29] **Tim:** What?

[01:08:29] **Carol:** and the island's been coming to life since settlement was there.

[01:08:35] **Carol:** So of course, you know.

[01:08:35] **Adam:** So the, the, yeah, the official like blurb is the mayor of a New England town resolves to turn it into the next tourist hotspot despite local warnings that it's cursed.

[01:08:45] **Carol:** Mhm.

[01:08:46] **Carol:** It's good.

[01:08:47] **Tim:** interesting.

[01:08:48] **Tim:** Okay.

[01:08:48] **Carol:** Really good.

[01:08:49] **Tim:** I mean, Apple TV they re.

[01:08:50] **Tim:** I mean, I don't think they're making money off their shows, but they're really.

[01:08:53] **Tim:** Besides Ted Lasso.

[01:08:55] **Tim:** But they really do some good stuff.

[01:08:57] **Carol:** Yeah.

[01:08:57] **Carol:** Severance.

[01:08:58] **Carol:** I can't wait for that to come back.

[01:08:59] **Tim:** Severance For All Mankind Foundation.

[01:08:59] **Carol:** Severance.

[01:09:00] **Carol:** Oh.

[01:09:01] **Carol:** Oh my goodness.

[01:09:01] **Carol:** Yeah.

[01:09:03] **Tim:** I mean, so much of their stuff is just really premium quality.

[01:09:03] **Carol:** Mhm.

[01:09:08] **Carol:** I wanna.

[01:09:09] **Carol:** Can I tell you guys a big compliment?

[01:09:11] **Carol:** My husband gave me this.

[01:09:12] **Tim:** Yeah, because, uh, you were.

[01:09:13] **Carol:** Yeah.

[01:09:13] **Carol:** Did you see that?

[01:09:13] **Tim:** Yeah, I would.

[01:09:14] **Tim:** Because we didn't talk about in the main show, so that.

[01:09:15] **Carol:** Yeah.

[01:09:16] **Tim:** That looked really sweet.

[01:09:17] **Carol:** So he is starting his MBA and they uh, were going through.

[01:09:21] **Tim:** I didn't know he's that tall.

[01:09:22] **Carol:** Yeah.

[01:09:23] **Carol:** And he's getting an MBA He's.

[01:09:25] **Carol:** He shoots basketballs all day long.

[01:09:27] **Adam:** Mhm.

[01:09:27] **Carol:** But yeah.

[01:09:28] **Carol:** Um, so he's getting his M.

[01:09:28] **Tim:** Oh, business, business.

[01:09:30] **Carol:** Yeah.

[01:09:30] **Tim:** Sorry.

[01:09:30] **Carol:** In MBA He is.

[01:09:30] **Tim:** Yeah.

[01:09:30] **Tim:** Sorry.

[01:09:32] **Tim:** MBA Sorry.

[01:09:32] **Carol:** He's getting his MBA So he went to the orientation and they were talking through like, you know, what the program's gonna offer, kind of what they're gonna do.

[01:09:38] **Adam:** Sam.

[01:09:41] **Carol:** And at one point they said no one's really started a business but while in school.

[01:09:45] **Adam:** Mhm,

[01:09:47] **Carol:** But that's not to say that you can't.

[01:09:49] **Carol:** To which my husband says, you don't have a Carol

[01:09:53] **Tim:** Oh.

[01:09:53] **Tim:** Huh.

[01:09:54] **Carol:** Yeah, I was like that.

[01:09:55] **Tim:** That's awesome.

[01:09:56] **Carol:** I was like, no, you didn't.

[01:09:57] **Carol:** So sure enough, his business plan, like his or, uh, his MBA journey, I posted it up on my wall and he wrote that down.

[01:10:04] **Carol:** He was like, yeah, but you don't have her.

[01:10:06] **Carol:** Like, you don't have someone who motivates you, someone who has the thought to do this.

[01:10:11] **Carol:** So it just, it was super,

[01:10:14] **Carol:** super rewarding and it made me teary just to hear my husband have that kind of confidence in me.

[01:10:17] **Tim:** No,

[01:10:19] **Carol:** So.

[01:10:20] **Tim:** he sounds like a kept man.

[01:10:20] **Carol:** Yeah,

[01:10:22] **Carol:** he is.

[01:10:23] **Tim:** He's totally whipped.

[01:10:25] **Carol:** Yep.

[01:10:25] **Adam:** M m.

[01:10:25] **Adam:** You guys make me sick.

[01:10:27] **Adam:** I can't wait till you're old and you hate each other.

[01:10:27] **Carol:** I know it.

[01:10:29] **Carol:** I know.

[01:10:29] **Tim:** Exactly right?

[01:10:31] **Carol:** I'll, uh, still be in love with you

[01:10:34] **Tim:** That's awesome.

[01:10:35] **Tim:** So Widow's Bay and

[01:10:35] **Carol:** Yeah,

[01:10:37] **Tim:** uh, hubby's awesome.

[01:10:39] **Tim:** That's cool.

[01:10:39] **Carol:** yeah, yeah.

[01:10:41] **Carol:** And Ted Lasso is amazing.

[01:10:41] **Tim:** So.

[01:10:43] **Carol:** Oh my God.

[01:10:44] **Adam:** Shut your mouth.

[01:10:45] **Carol:** Not gonna, I'm not gonna say anything.

[01:10:46] **Carol:** I'm just gonna say it's great.

[01:10:48] **Carol:** We knew it was going to be great.

[01:10:49] **Carol:** It's great.

[01:10:51] **Tim:** It.

[01:10:51] **Tim:** I think it's going to be a slow burn.

[01:10:53] **Carol:** Yeah.

[01:10:54] **Carol:** Um, I'm.

[01:10:54] **Carol:** I'm not gonna be sad.

[01:10:55] **Carol:** It's good.

[01:10:55] **Tim:** I'm um.

[01:10:55] **Tim:** No spoilers.

[01:10:56] **Tim:** I'm just saying my feeling is like, I think they're setting stuff up.

[01:11:00] **Carol:** Yeah.

[01:11:00] **Tim:** First two episodes.

[01:11:01] **Tim:** I'm like, they didn't.

[01:11:02] **Tim:** Nothing made me cry, so.

[01:11:03] **Adam:** I, uh, I did want to ask.

[01:11:05] **Adam:** Actually, Carol, I'm pretty sure it was you that we.

[01:11:07] **Adam:** When we were talking about Ted Lasso stuff a few episodes ago,

[01:11:09] **Tim:** Mhm.

[01:11:11] **Adam:** I had said, you know, it's okay to watch.

[01:11:13] **Adam:** I think I told Ben it's okay to watch the teaser trailer thing.

[01:11:16] **Adam:** And you were like, oh, Steve saw something in here.

[01:11:18] **Adam:** And then he was like, oh,

[01:11:20] **Carol:** Mhm.

[01:11:21] **Adam:** I want to know what was.

[01:11:22] **Adam:** What it was from the trailer that you thought was a spoiler because I didn't see anything spoiled.

[01:11:28] **Adam:** I've seen the trailer like 20 times.

[01:11:30] **Adam:** Didn't see anything spoilery in there.

[01:11:31] **Carol:** That he's coaching a women's team.

[01:11:33] **Adam:** That was like, uh, basically advertised in the last episode of season three.

[01:11:36] **Carol:** Yeah, I.

[01:11:36] **Tim:** Yeah.

[01:11:37] **Adam:** Yes.

[01:11:37] **Carol:** I don't think, I don't think Steve remembered that because he was like, there's a woman's team.

[01:11:42] **Carol:** What?

[01:11:43] **Carol:** So that's what I thought was the spoiler.

[01:11:43] **Adam:** Yeah, at the, at the very end, like in the last five or 10 minutes of the season three, whatever the last season was, Keeley chose, what is her character's name?

[01:11:51] **Carol:** Yeah.

[01:11:56] **Adam:** the woman who runs the club.

[01:11:57] **Adam:** Owns the club.

[01:11:58] **Adam:** Whatever.

[01:11:58] **Carol:** I can't keep names straight, but yes, boss.

[01:11:58] **Adam:** Um,

[01:11:58] **Tim:** Um.

[01:12:02] **Adam:** yeah, boss lady.

[01:12:02] **Adam:** He shows her.

[01:12:03] **Adam:** Keeley shows her a ah, binder and it's like for AFC Richmond women's team or Rebecca.

[01:12:07] **Tim:** Rebecca Ferguson Rebecca.

[01:12:08] **Carol:** Rebecca.

[01:12:09] **Adam:** Thank you.

[01:12:09] **Carol:** There you go.

[01:12:09] **Tim:** Yeah.

[01:12:09] **Adam:** Yeah.

[01:12:09] **Carol:** Yeah, don't remember that.

[01:12:10] **Adam:** Um,

[01:12:12] **Carol:** This normally Steve remembers everything.

[01:12:13] **Tim:** Actually now that.

[01:12:14] **Tim:** Now that you.

[01:12:14] **Tim:** Now that you say it.

[01:12:15] **Tim:** I do remember that.

[01:12:16] **Carol:** Mhm.

[01:12:16] **Tim:** That's interesting.

[01:12:17] **Tim:** Yeah.

[01:12:17] **Carol:** Yeah.

[01:12:18] **Tim:** So I guess they were leaving a.

[01:12:19] **Adam:** And, and that was, I mean I, I might not have remembered it either, except for it was announced like a year ago that this episode, when they said they're going to do another season, it kind of immediately was announced that it's going to be a women's team.

[01:12:27] **Carol:** Yeah,

[01:12:32] **Carol:** Yeah.

[01:12:32] **Carol:** Well, I mean, we hadn't been following any of the other than.

[01:12:34] **Adam:** Yeah.

[01:12:35] **Tim:** There.

[01:12:35] **Carol:** It's coming.

[01:12:36] **Carol:** Yeah.

[01:12:38] **Carol:** Yeah, that's it.

[01:12:40] **Carol:** Short after show.

[01:12:41] **Carol:** Where has Ben been at for this one?

[01:12:43] **Adam:** Right.

[01:12:43] **Adam:** Ben had to leave.

[01:12:44] **Adam:** I guess we should acknowledge that.

[01:12:45] **Carol:** Uh, yeah.

[01:12:45] **Adam:** Ben, Ben was just so puppy wiped he had to go.

[01:12:49] **Tim:** Gotta go take care of the puppy.

[01:12:50] **Carol:** Do you hear mine?

[01:12:52] **Tim:** I.

[01:12:53] **Adam:** Yep.

[01:12:53] **Tim:** I will say so.

[01:12:53] **Carol:** Mhm.

[01:12:53] **Tim:** I'm like three weeks away from Dragon Con,

[01:12:58] **Tim:** so.

[01:12:58] **Carol:** You excited?

[01:12:59] **Tim:** Yeah.

[01:13:00] **Tim:** Super excited.

[01:13:01] **Tim:** Yeah, it's just, it's.

[01:13:02] **Tim:** It's weird now that the kids are like older because it's like they're kind of taking care of all this.

[01:13:06] **Tim:** Used to be like a huge cram to like just get everything done and now it's like, all right guys, where you at in your projects?

[01:13:10] **Adam:** Yeah.

[01:13:13] **Tim:** They're like,

[01:13:15] **Tim:** like Max, uh, hasn't made anything for himself.

[01:13:16] **Carol:** Mhm.

[01:13:17] **Tim:** Lily's done a couple, Michelle's made some and, and.

[01:13:20] **Tim:** But it's like.

[01:13:21] **Tim:** Yeah.

[01:13:21] **Tim:** So there's a lot less pressure.

[01:13:22] **Tim:** I kind of feel like

[01:13:25] **Tim:** I don't know what's going on.

[01:13:26] **Tim:** On Thursday night, we're inviting everyone to a Court of Owls.

[01:13:29] **Tim:** So if you're not into Batman lore, because it's never really been in movies or in the comic books, basically they're called the Court of Owls.

[01:13:37] **Tim:** They're like this evil organization that ran in Gotham prior to the Waynes.

[01:13:41] **Tim:** And they, they wear these like owl white owl masks and they dress like.

[01:13:46] **Tim:** There's the ultra elite.

[01:13:46] **Carol:** Cool.

[01:13:47] **Tim:** They're the, the elite of Gotham.

[01:13:50] **Tim:** Right.

[01:13:50] **Tim:** But they're like shadowy and they have a protector called the Talon, who's kind of like a precursor to Batman, but he's.

[01:13:56] **Tim:** He's on their team.

[01:13:58] **Tim:** Bad guys team.

[01:13:59] **Tim:** And so uh, like for the past couple years, like the whole family, we just wear.

[01:14:00] **Adam:** Mhm.

[01:14:03] **Tim:** We like dress up in like tuxedos and like fancy dress and wear the masks and walk around and just look and look at people.

[01:14:08] **Carol:** I love it.

[01:14:08] **Adam:** Mm.

[01:14:10] **Tim:** Like so you're not supposed to.

[01:14:12] **Tim:** In Gotham, you're never supposed to talk about the Court of Owls.

[01:14:14] **Tim:** Like they're taboo to talk about.

[01:14:15] **Tim:** It's like the secret society And so people will walk around, they'll look at us and like we're always kind of walking around.

[01:14:16] **Carol:** Mhm.

[01:14:21] **Tim:** Like they're really creepy and people are like, oh my God, it's a Court of Owls And would just look, we'll all like turn in unison, look at them and then put our fingers up to our mask mouths and go

[01:14:26] **Adam:** Mhm.

[01:14:33] **Tim:** like, just tell them to shush.

[01:14:34] **Tim:** And they will like some people literally freak.

[01:14:35] **Carol:** Here.

[01:14:37] **Tim:** Oh my God.

[01:14:37] **Tim:** Oh my God.

[01:14:38] **Tim:** So we're trying to get a bunch of like maybe uh, you know, a dozen 25, you know, a big group of people to like do the sort of thing because the easy 3D print, you can buy mask at the store, they're pretty cheap.

[01:14:45] **Adam:** Mhm.

[01:14:51] **Tim:** And just like there's like these areas of the hotels where they have like these overlooks and just to have like all the owls just stand around like over the top.

[01:15:00] **Carol:** Oh, I hope it works out.

[01:15:00] **Tim:** And as people walk in, as people walk in underneath, they see all these owls just staring down at them with their.

[01:15:06] **Tim:** And then people like start freaking.

[01:15:08] **Tim:** They just give them the shush.

[01:15:10] **Tim:** And so.

[01:15:10] **Carol:** I love it.

[01:15:11] **Tim:** Yeah, we'll see.

[01:15:12] **Carol:** Oh, I hope it works out.

[01:15:13] **Tim:** So I, I,

[01:15:14] **Carol:** If so, we need pictures.

[01:15:15] **Tim:** yeah, for sure, definitely.

[01:15:17] **Tim:** So I'm looking forward to that.

[01:15:18] **Adam:** My thing lately is just my, uh, kids are growing up, man.

[01:15:21] **Adam:** And it's weird, right?

[01:15:22] **Tim:** It is weird.

[01:15:23] **Carol:** Been there.

[01:15:23] **Adam:** My, my oldest is 17, will be 18 in just a couple of short months.

[01:15:28] **Adam:** she is looking at buying another car and it's like.

[01:15:34] **Tim:** Mhm.

[01:15:35] **Adam:** She has what she wants and I have opinions on what's practical and, and a good idea.

[01:15:39] **Adam:** And it's like, how much do you put your foot down and say, well like look, you're, you're not 18.

[01:15:39] **Carol:** Mhm.

[01:15:42] **Tim:** Yeah.

[01:15:44] **Adam:** You can't make this decision versus like you still have the safety net of living with mom and dad and we can kind of help you out when you make mistakes and maybe now's a good time to make a mistake if you're going to make a mistake.

[01:15:44] **Tim:** Mhm.

[01:15:46] **Carol:** Yep.

[01:15:55] **Carol:** M.

[01:15:55] **Carol:** Yeah.

[01:15:56] **Adam:** And my, my 15 year old is uh, building a new computer for themselves and uh, I'm, I'm not a Windows PC guy.

[01:16:01] **Carol:** Oh, fun.

[01:16:03] **Tim:** Cool.

[01:16:06] **Adam:** I got into Mac in like Oh God, I don't even know.

[01:16:08] **Carol:** Second grade.

[01:16:09] **Adam:** No, it was probably, it was probably like early on in my job at University of Pennsylvania.

[01:16:14] **Adam:** So like

[01:16:14] **Carol:** Oh yeah.

[01:16:15] **Carol:** A long time ago.

[01:16:16] **Carol:** Yeah.

[01:16:16] **Adam:** yeah, like 20ish years ago.

[01:16:18] **Tim:** 50, 60 years ago.

[01:16:19] **Adam:** 20 to 25 years ago.

[01:16:20] **Tim:** Yeah.

[01:16:21] **Adam:** Uh, and I have never really looked back.

[01:16:23] **Adam:** Like I've had a Windows PC every now and then but like I, you know, it's like never a really good one.

[01:16:25] **Tim:** Mhm.

[01:16:28] **Adam:** Never.

[01:16:28] **Adam:** I have not stayed up with the hardware and so they wanted to you know, build a new gaming PC.

[01:16:35] **Adam:** And I was like, you're gonna have to talk to my brother.

[01:16:37] **Adam:** My brother is, you know, still a Windows PC guy.

[01:16:40] **Adam:** And I showed them PCPartPicker Like here's how you can make sure stuff fits together and find good deals on parts and stuff.

[01:16:42] **Carol:** Yeah,

[01:16:44] **Carol:** it's still valid.

[01:16:45] **Carol:** Yeah, yeah,

[01:16:46] **Tim:** Mhm.

[01:16:47] **Adam:** Um, and it's like get advice from my brother on you know, which, like where is the line between spending uh, the right amount of money on a graphics card and going overboard and that sort of thing.

[01:16:49] **Tim:** Sa.

[01:16:57] **Carol:** Yeah.

[01:16:59] **Adam:** And so now I've got a 15 year old who just dropped like over a thousand bucks on computer parts.

[01:17:04] **Adam:** Which is.

[01:17:06] **Adam:** It makes my heart feel good.

[01:17:06] **Carol:** Really not bad.

[01:17:07] **Carol:** Yeah.

[01:17:07] **Adam:** Well yeah, I mean, who knows, maybe it was over $2,000 because they do it in, you know, here's 400 bucks and here's 800 bucks and.

[01:17:12] **Carol:** Huh.

[01:17:13] **Tim:** Yeah.

[01:17:13] **Adam:** Yeah, yeah, and but it makes my heart feel good because they have been very financially responsible for their entire life life and been, been saving money and it's like, yeah, okay, and you want to do this for yourself now and you just can.

[01:17:21] **Carol:** Yeah.

[01:17:27] **Adam:** And, and that's a, that's a cool thing.

[01:17:29] **Adam:** And it's like.

[01:17:30] **Tim:** Yeah.

[01:17:31] **Carol:** You're at the good age.

[01:17:31] **Tim:** I think, and I think you pointed out like the hardest part of parenting is like this decision Where do you push and where do you let them struggle?

[01:17:38] **Carol:** Mhm.

[01:17:38] **Adam:** Mhm hm.

[01:17:40] **Tim:** Right?

[01:17:41] **Carol:** Yep.

[01:17:41] **Tim:** Because as a parent it's like when they're little, little like they fall down, you want to m.

[01:17:45] **Tim:** You immediately pick them up.

[01:17:46] **Tim:** When they start crying, you immediately soothe them But as they get older, you gotta like, sometimes you're like, you're just gonna have to cry it out for a bit here.

[01:17:48] **Adam:** Yeah.

[01:17:52] **Carol:** Yeah.

[01:17:52] **Tim:** You gotta, I uh, can't come in and swoop and save you all the time.

[01:17:55] **Tim:** And then sometimes you're like, do I need to swoop in and save them?

[01:17:58] **Tim:** Because they seem really stuck.

[01:18:00] **Carol:** Yeah.

[01:18:01] **Tim:** That's really, really hard.

[01:18:01] **Adam:** Yeah.

[01:18:03] **Adam:** The parenting is I think the thing that Megan and I talk the most about.

[01:18:06] **Adam:** Like when the kids aren't around, like when the we're going to dog walk and there's no kids with us or anything.

[01:18:10] **Adam:** We were on a dog walk yesterday and,

[01:18:15] **Adam:** and I've completely lost my train of thought.

[01:18:16] **Adam:** What was I.

[01:18:17] **Carol:** Uh, you said you talk about parenting.

[01:18:18] **Tim:** Pushing, pulling.

[01:18:19] **Carol:** Yeah.

[01:18:20] **Carol:** So the.

[01:18:20] **Adam:** No, don't know.

[01:18:21] **Carol:** See when you heard, went on the dog walk.

[01:18:21] **Adam:** Uh,

[01:18:22] **Carol:** I think you were going to tell us what you talked about on your parenting thing.

[01:18:23] **Adam:** yeah, I, I remember all that.

[01:18:25] **Adam:** I don't remember what it was that we talked about in the dog walk that I was going to mention.

[01:18:28] **Adam:** Oh, well,

[01:18:28] **Carol:** Oh, okay.

[01:18:29] **Carol:** Maybe the car.

[01:18:30] **Tim:** How hard it is.

[01:18:31] **Carol:** Yeah.

[01:18:32] **Adam:** now I don't know.

[01:18:33] **Carol:** Mhm.

[01:18:34] **Carol:** Well, I can tell you it gets a little easier.

[01:18:37] **Carol:** Like right now the oldest moved and he called and he's a lot closer now, but he was like, hey, I just need to talk to you for a minute.

[01:18:44] **Carol:** I was like, oh yeah, what's up, buddy?

[01:18:44] **Adam:** Oh, um,

[01:18:45] **Tim:** Mhm.

[01:18:46] **Carol:** He goes, I'm.

[01:18:47] **Carol:** I'm struggling on what to do.

[01:18:48] **Carol:** He goes, I think I'm thinking about getting an Amazon credit card.

[01:18:51] **Carol:** Because I didn't realize when I moved to my new apartment, it's not furnished.

[01:18:54] **Tim:** Sa.

[01:18:55] **Carol:** And he's like, I don't have a bed and I don't have a dresser.

[01:18:55] **Adam:** Mhm.

[01:18:59] **Carol:** And I was like, I have a bed.

[01:19:01] **Carol:** I have a dresser.

[01:19:02] **Carol:** He goes, uh, you're already giving me a couch and a love seat.

[01:19:04] **Carol:** I can't take that from you too.

[01:19:06] **Carol:** I'm like, we.

[01:19:06] **Carol:** We don't want it.

[01:19:07] **Carol:** We want to get one that matches our other guest bed, right?

[01:19:10] **Carol:** Like, we wanted to get rid of this already.

[01:19:11] **Adam:** Yeah.

[01:19:12] **Carol:** I was like, you're doing us a favor.

[01:19:14] **Carol:** And he, like, just starts crying.

[01:19:16] **Carol:** He's like, yeah.

[01:19:17] **Carol:** He's just like.

[01:19:18] **Carol:** And he's my big teddy bear.

[01:19:19] **Carol:** He's like, thank you so much because I didn't want to open a credit card.

[01:19:19] **Tim:** M mhm.

[01:19:22] **Carol:** I've.

[01:19:22] **Carol:** I've made it, you know, to 25 years, and I don't have a credit card.

[01:19:25] **Carol:** I don't have debt.

[01:19:26] **Carol:** Like, I'm paying my own bills.

[01:19:28] **Carol:** He goes, I just didn't have the money to pay for this right now.

[01:19:31] **Carol:** I'm like, well, now you don't have to pay for it.

[01:19:32] **Carol:** Like, there you go.

[01:19:33] **Carol:** Just call us.

[01:19:34] **Carol:** Call us when you don't know what to do and maybe we can help, you know, Just call.

[01:19:35] **Tim:** Mhm.

[01:19:39] **Adam:** Yeah.

[01:19:39] **Adam:** I mean it's a good feeling.

[01:19:41] **Adam:** I would say not having a credit card is a dangerous way to start your life.

[01:19:46] **Adam:** You know, like, got to have credit.

[01:19:46] **Carol:** No, he.

[01:19:47] **Carol:** He has a.

[01:19:48] **Carol:** He has a.

[01:19:48] **Carol:** He has a great credit score.

[01:19:50] **Carol:** He has.

[01:19:50] **Carol:** He's on my credit cards.

[01:19:50] **Adam:** Okay.

[01:19:51] **Carol:** He just doesn't use them.

[01:19:52] **Adam:** Okay, Gotcha.

[01:19:53] **Carol:** Both of my boys have had credit cards since they were 16, so they have a great credit score.

[01:19:56] **Adam:** Gotcha.

[01:19:56] **Tim:** Yeah.

[01:19:58] **Carol:** Peyton even got his own credit card for something else.

[01:20:01] **Carol:** And he was like, thank you for setting me up to, like, be like, financially stable.

[01:20:05] **Carol:** Like, I have a good credit score.

[01:20:05] **Adam:** Yeah,

[01:20:07] **Carol:** He goes, my credit score is better than my girlfriend's parents.

[01:20:12] **Tim:** Yeah.

[01:20:12] **Adam:** My, uh,

[01:20:12] **Tim:** I did the same thing for my kids and like they, but I told them like when you charge something it immediately notifies me.

[01:20:12] **Carol:** Yeah, yeah,

[01:20:17] **Carol:** yeah,

[01:20:18] **Tim:** So.

[01:20:19] **Tim:** And they, they, in fact they, they still, they've never charge anything without asking first, so.

[01:20:23] **Carol:** Yeah.

[01:20:24] **Carol:** Mine always ask.

[01:20:25] **Carol:** Yeah, but James doesn't even use it.

[01:20:27] **Carol:** Peyton will, though.

[01:20:28] **Carol:** Peyton will use it for everything.

[01:20:30] **Adam:** My father in law, as far as I know is pretty much a self made man.

[01:20:34] **Adam:** You know, he, he, I don't think he inherited a bunch of money.

[01:20:36] **Adam:** I mean, he only lost his mother recently, like in the last couple of years anyway.

[01:20:37] **Carol:** Mhm.

[01:20:40] **Tim:** Wow.

[01:20:41] **Adam:** but he had, he is well to do.

[01:20:42] **Adam:** He has plenty of money.

[01:20:44] **Adam:** to the point where he gave my wife and I and both of our kids and my wife's sister and her family all, every individual got a nice chunk of change from them recently.

[01:20:54] **Adam:** Just like a, uh, here, here's some money.

[01:20:56] **Adam:** Um, and the.

[01:20:56] **Tim:** Nice.

[01:20:56] **Tim:** Mhm.

[01:20:57] **Adam:** I say that to set up Just so you understand, they have money.

[01:21:01] **Adam:** His credit score was terrible because he, you know, they bought a house in like the 70s and the house was like $30,000.

[01:21:05] **Carol:** Yes.

[01:21:09] **Adam:** You know, it was, if you put it on the market today, it's probably half a million dollar house, something like that.

[01:21:13] **Tim:** Oh yeah, probably more.

[01:21:13] **Carol:** Mm.

[01:21:14] **Adam:** and.

[01:21:15] **Adam:** Right.

[01:21:15] **Adam:** But like, you know, and they just, they just, you know, had.

[01:21:18] **Adam:** That was like their only line of credit they've ever had in their entire lives.

[01:21:21] **Adam:** Like they would just buy cars with cash and you know, just pay for all their stuff with cash or checks.

[01:21:24] **Carol:** Mhm.

[01:21:27] **Adam:** And like, you know, at one point he went to go do something.

[01:21:30] **Adam:** I don't remember what it was.

[01:21:31] **Adam:** Maybe it was.

[01:21:32] **Adam:** He was, I don't remember, whatever.

[01:21:34] **Adam:** But he

[01:21:35] **Adam:** didn't need a line of credit.

[01:21:36] **Adam:** But maybe he was curious or whatever and they were like, his credit score was not great because he had never used credit for anything.

[01:21:42] **Carol:** Yeah.

[01:21:43] **Tim:** That's funny.

[01:21:44] **Tim:** Yeah, I open credit and never use it.

[01:21:46] **Carol:** Yeah.

[01:21:46] **Carol:** That's what we've done.

[01:21:48] **Tim:** I probably like ten credit cards.

[01:21:49] **Tim:** I've only used two.

[01:21:51] **Tim:** Um, Visa.

[01:21:52] **Tim:** Um,

[01:21:52] **Adam:** Isn't that bad for your credit too?

[01:21:53] **Tim:** no, that's actually really good because the amount of open credit you have that you don't utilize.

[01:21:58] **Carol:** Ah, the free space.

[01:21:58] **Adam:** But if you never use it, I thought that counted against you like using it and paying it off.

[01:22:03] **Tim:** It doesn't seem to.

[01:22:04] **Adam:** Oh, weird.

[01:22:05] **Carol:** Mhm.

[01:22:05] **Tim:** I'm, like, one point away from perfect.

[01:22:07] **Tim:** So, um, whatever I'm doing is working.

[01:22:09] **Carol:** Yeah.

[01:22:09] **Adam:** Interesting.

[01:22:11] **Tim:** So.

[01:22:12] **Carol:** Wrap it up.

[01:22:13] **Adam:** Sure.

[01:22:15] **Adam:** All right, patrons, thank you so much for your support.

[01:22:17] **Adam:** we will catch you next week.

[01:22:19] **Adam:** Your heart matters more.

[01:22:21] **Adam:** Love you.

[01:22:21] **Adam:** Bye.
