---
title: "240: Memento Mori with Shawn Oden"
description: "What happens to your digital life when you die? Shawn Oden shares hard-won wisdom about password managers, wills, and the conversations nobody wants to have."
date: 2025-11-27
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/6fda054d-b13e-433c-a31c-8c2af68d5171"></script>
<div class="redcirclePlayer-6fda054d-b13e-433c-a31c-8c2af68d5171"></div>

Remember that you will die. That's the meaning behind "Memento Mori," and it's the theme of this week's episode. Guest Shawn Oden, joins Adam, Ben, and Tim to discuss digital death preparedness for geeks. Inspired by clearing out his grandmother's house and buying his late best friend's computers to protect his digital legacy (and potentially lost Bitcoin), Shawn advocates for documenting passwords, creating wills, setting up power of attorney, and having honest conversations with loved ones. The hosts explore practical steps like using 1Password with shared family vaults, the importance of organ donation documentation, and the philosophical tension between honoring a deceased person's wishes versus meeting the needs of those left behind.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

### Links & Resources

-   [In Case You Get Hit by a Bus](https://www.amazon.com/Case-You-Get-Hit-Bus/dp/1523510471/ref=sr_1_1) (book)
-   [eol-dr](https://github.com/potatoqualitee/eol-dr/blob/main/README.md) - End of Life Digital Resources on GitHub
-   [EOL-RalphHightower](https://ralphhightower.github.io/EOL-RalphHightower/) - Another digital estate planning resource
-   [NOLO - Get Your Affairs in Order](https://www.nolo.com/legal-encyclopedia/affairs-in-order) - Legal self-help resources

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/240-memento-mori-with-shawn-oden.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Shawn Oden:** she had a friend that was a, had a whole bunch of technological stuff what does his wife do with his stuff? And I mean, just even simple things about like, what happens if your router dies?

[00:00:09] **Adam:** Yeah.

[00:00:10] **Shawn Oden:** are you, is she gonna be just without an internet anymore? and that's the hardest part, I guess, is trying to think of everything that you've got that somebody else might need to know how to do if you're not there to do it.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 240 and on today's show, Memento Mori. Remember that you will die,

[00:00:45] **Tim:** is that what they whispered to Caesar's ear when he was

[00:00:48] **Adam:** that's just what I tell my kids every night before they go to bed. I don't know

[00:00:50] **Tim:** Oh, okay. Goodnight Wesley. Great work. I'll probably kill you in the morning.

[00:00:54] **Adam:** exactly.

[00:00:55] **Adam:** but first, as usual, let's start with the tris and fails. Carol couldn't be with us tonight, but we do in her stead. Have a special guest.

[00:01:02] **Adam:** Shawn Oden

[00:01:03] **Adam:** Say hello, Sean.

[00:01:04] **Shawn Oden:** Hi.

[00:01:05] **Adam:** I know. Fail. You're out. I said today. Hello?

[00:01:08] **Tim:** The correct answer was Hello Sean.

[00:01:10] **Shawn Oden:** Hello, Sean.

[00:01:11] **Tim:** There you go.

[00:01:12] **Shawn Oden:** I was not to be

[00:01:14] **Adam:** well.

[00:01:15] **Tim:** There's only one of me. Trust me, you can't beat too much me.

[00:01:18] **Adam:** So our friend Sean, has some history, with this topic. talking about what happens to your digital life after you pass, and what you, leave behind for your, loved ones. So we thought we'd have him on to talk about it 'cause it's an important topic that, that doesn't get talked out about enough.

[00:01:33] **Adam:** But first, as usual, we'll start with our triumphs and fails. Carol's not here with us. so Tim, I'm gonna come to you first. What do you got going on?

## [00:01:38] Tim's Triumph and Fail

[00:01:38] **Tim:** I missed a couple weeks, so I'm going for a twofer. With your permission, captain. My captain.

[00:01:43] **Adam:** I'll allow it.

[00:01:44] **Tim:** Yeah. Thank you, sir. So I'll go with the fail I got. Well, I got a fail to triumph. Which one you want?

[00:01:49] **Adam:** Yeah. You know, start with the bad news. Let's go.

[00:01:51] **Tim:** So there has been a plan for the past, like couple months of plan, like firewall and hardware replacement.

[00:01:58] **Tim:** At the AT work, we have a firewall and a router that are like, well, the firewall's a bit newer, but the router one, there's one router that's like 20 years old, It really needed to be updated and we were getting a new firewall at the same time. So, I mean, I met with the team a couple weeks ago. I'm like, all right, so what's the plan?

[00:02:13] **Tim:** What's the how, what's the outage time? what's the expected outages? how are you gonna verify that things are working? then what's the rollback plan of things go to crap.

[00:02:23] **Adam:** Sounds

[00:02:23] **Adam:** responsible.

[00:02:24] **Tim:** all their answers sound great, right? They absolutely, they must have used ChatGPT or something to generate it.

[00:02:30] **Tim:** 'cause it sounded fantastic. I'm like, all right, so sounds like you guys are prepared. And I really was, I mean, I wasn't leading the effort. I was just an interested party, right? we got a, a infrastructure team, it's their job. But I'm like, I'm obviously invested that this goes well.

[00:02:43] **Tim:** So I did my due diligence beforehand. And then of course, it happened two Sundays ago, I was super sick. I basically slept the entire weekend and all through Monday.and then I wake up to find out that pretty much we were, our company was down all of Monday.

[00:02:59] **Adam:** Nice.

[00:03:00] **Ben:** It sounds like cloud's problem.

[00:03:04] **Tim:** Now of, of course, what, you know, the team is saying that that was a, a Windstream problem, which Windstream is one of our, we have multiple providers, and one of 'em was Windstream that the BGP sessions or something didn't get copied over. I, and it all went over my head with network and maybe, maybe Sean knows about this more than I do.

[00:03:21] **Tim:** But anyway, everything was reporting up. And so the guys who were testing it, they did the smoke test, right? They went through and said, all right, is this up? Is this up? They were testing stuff and everything worked for them, but most importantly, none of it worked for our customers.

[00:03:34] **Adam:** Mm.

[00:03:35] **Tim:** So that was really bad. but fortunately I slept through it all and no one even messaged me or texted me. They all, so somehow people knew. I, I don't know how people knew I was sick, but yeah, I usually, my text messages get blown up every time something goes out and everyone just left me alone.

[00:03:50] **Tim:** So I was appreciative for that, but was not happy that, we cost our customers hundreds of thousands, if not almost millions of dollars

[00:04:00] **Adam:** Wow.

[00:04:01] **Tim:** in, in lost time. 'cause they couldn't write insurance. So

[00:04:05] **Adam:** yeah,

[00:04:06] **Tim:** that was, it wasn't DNS, although BGP is kinda like DNS in a sort of way,

[00:04:13] **Adam:** it's another TLA.

[00:04:14] **Tim:** Yep.

[00:04:15] **Ben:** I feel like, getting hardware changeovers to work well, I almost, I mean, maybe I only hear the nightmares, but it just sounds like it is a particularly hard thing to get right.

[00:04:26] **Tim:** particularly when you don't do it more than like every few years, right? It's not like something you're like, get muscle memory for. So this is another good case for us. It's like, at least when you move to the cloud, 'cause we're, we self-host a lot of people. So we, we, we self a we, we sell the hosting to our customers.

[00:04:44] **Tim:** but it's like, it's constantly trying to keep up and move. It's like, let's just move to the cloud. Is is it gonna be a little more expensive for 'em? Yes, it's gonna be more reliable. Yes. But I think the biggest feature is when it's down, it's in the news it New York Times, the Economist Wired magazine, everyone's gonna report that it's down.

[00:05:02] **Tim:** So you don't even have to tell your customers like, yep, we're down because here's what the Wall Street Journal says about this outage. So what are they gonna, what are they gonna say?

[00:05:10] **Adam:** Well, Tim, I was promised some good news to follow this.

[00:05:13] **Tim:** Okay. All right. So you're not gonna like this. Uh,the good news is, like I, I've spent a lot of the time in the past, I, I got that Claude subscription and I'm wearing it out. just doing a whole lot more AI experimentation and what I like to do, like when I was, like, in my early days when I was young and ignorant and really excited about a new version of ColdFusion that came out, I would create a project, like a little, a little passion project that I would do just to learn it.

[00:05:39] **Tim:** Well, I'm kind of doing that now with AI. So I, I played around, I played Magic: The Gathering online, and, I've been trying to do an AI deck builder and I've been using AI to do it to help me, like a, pull all the information about the cards that, that are available and build a deck and use AI to do it.

[00:05:57] **Tim:** So that's, that's been fun. I. The only reason I say that as a triumph, it's been a long time since I've actually been excited about coding and I've actually, I'm like, this been a long time since I sat down and coded all weekend just for fun.

[00:06:10] **Adam:** No, you're not doing it now anyway. You're making the AI do it.

[00:06:14] **Tim:** But, but I mean, at the end of the day, I just like creating a cool product.

[00:06:18] **Tim:** Right. So it's like the tool that I use is, I mean, I'm not use, I'm not using the code set to do it, but I'm creating the product and it's, it's been a challenge. Definitely. It's, it's not like I just give it a prompt. It wasn't like some of the other projects where I just gave it some prompts and then an hour later it was done.

[00:06:33] **Tim:** This is actually, 'cause there's a whole lot of moving pieces. So it's been fun and I'm still working on it. I, I was working on it right before this call, before we jumped on, so, and I can't wait to hear. Can we make this a short episode so that I can get back to it?

[00:06:47] **Adam:** No, Ben, we can't,

[00:06:48] **Ben:** Uh, I've got TV to watch.

[00:06:52] **Tim:** That's me. How about you, Adam?

## [00:06:54] Adam's Fail

[00:06:54] **Adam:** I'm gonna go with a fail, which is that,you know, I mentioned a couple of weeks ago that I was having some hand pain. I was in wearing a, a brace that like immobilized my wrist. And I've seen several doctors since then. I've had an MR I've had multiple x-rays, a couple of specialists, whatever. And basically at this point, nobody knows what the heck is going on.

[00:07:10] **Adam:** Everybody has ruled out their concerns. the orthopedist was looking for broken bones or, ligament tissue tears or whatever. And no concerns there, nothing they saw on the x-ray, whatever. And my rheumatologist, 'cause that's my autoimmune, stuff, is kind of inflammation rheumatology related.

[00:07:26] **Adam:** So my rheumatologist ordered the MRI and was looking for any signs of anything there and soft tissue. And, you know, he said it checks out everything looks good to him. And it just, everybody's like, no, no, it's not my thing. Go find somebody else. So at this point, nobody knows what's going on with my hand, but I will say, there's a little bit of a triumph here, which is that my hand is starting to feel better anyway.

[00:07:47] **Adam:** So, actually today was the first time in like maybe three weeks that I've actually done a full workout. I've been doing a couple of times a week of what I've been calling my hands free workout, which is basically just, calf raises and, and leg press. 'cause I can do those with very minimal input from my hands, just stacking the weights,

[00:08:04] **Adam:** so yeah, I, I did my first full workout in a while, today, I'm just happy that my hand is starting to feel better. Yeah. Bodies suck.

[00:08:13] **Ben:** I've had pain in my right wrist, like kind of where my thumb inserts for like a solid. 20 years, and I've been to various people. I've had x-rays and physical therapy and nothing like, just certain movements, bending it in weird ways, like it just always hurts a little bit.

[00:08:31] **Tim:** Yeah, don't do that. Just stop it.

[00:08:33] **Ben:** I know.

[00:08:34] **Ben:** It's dumb. I, I actually, I was, I was a texting with my mom and I'm actually going to physical therapy right now for my bicep. I have some bicep tendonitis apparently. And, she was asking me about it and I said, you know, who knows? I said, most of my joints just hurt a little bit, every day. And she was like, yeah, I don't remember the last time.

[00:08:54] **Ben:** I haven't been in pain. Like, yeah, that's just where we are. That's just where we are as a people.

[00:09:00] **Adam:** It's a, it's a privilege to get old, I suppose. but it doesn't come without some negative side effects as well. Anyway, so that's what I like I got going on. How about you, Ben?

## [00:09:10] Ben's Fail

[00:09:10] **Ben:** I'm gonna go with a small failure. I, I've been giving you all updates on my big sexy poems web app, which is just really a playground for me to try out some new stuff. And, it's gotten to the point where I know that the next big challenging thing on the site is to actually make it responsive so that I could use it on a mobile device.

[00:09:30] **Ben:** And, part of me is just super unmotivated to make things responsive. 'cause I just, it doesn't seem like an app I'd want to use on my phone. I mean, I'm sure that's just an excuse. You know, I'm, I'm like talking myself out of it. But it also, the failure is slightly that this is a thing that still frustrates me and meaning that it's 2025 as of today, and the notion of responsive design has been around for, I don't know, 15 years.

[00:09:57] **Ben:** Yeah.and it's just still something I don't feel super competent at, and especially given the fact that a, a bunch of my UIs in this app are data grids. you know, they're very simple data grids. It's more, you know, like a list of poems that has a, collection name and a, and a date and like an add, like an edit link or something.

[00:10:19] **Ben:** I mean, like things that just like aren't super complicated. But even in the things that I have historically made responsive data grids has not really been one of them. And when I've had to do it, I have not done it, I'd say with any kind of a skill. And it's like this, this is supposed to be that thing.

[00:10:37] **Ben:** This is the opportunity for me to dive in and learn it. And I'm just really having trouble motivating I don't know. I just don't, I don't know how to get past that. A little emotional hurdle.

[00:10:46] **Adam:** Well, it's a cheap way out, but the, I've always been kind of a fan of the, the built-in way that, tables are quote unquote responsive and, at least bootstrap three, which is the first one that I still use. which is I think you wrap it in a div, it's like class is table responsive and then it overflows and you can

[00:11:03] **Ben:** it basically just scroll left and right. Yeah. So that's, that's one of the thi I was, so we're using Bootstrap 5 at work and I did see that that is some of the examples that they provide. and this is gonna sound silly because this is, should not be surprising except for the fact that it surprised me a little bit.

[00:11:21] **Ben:** But one of the other techniques that I've seen, the Bootstrap 5 demos use. Is they will below a certain, media query width, they will literally just hide certain tds, certain table. I don't know, actually, I don't know what the D and TD stands

[00:11:38] **Adam:** I believe it's data, table data.

[00:11:39] **Ben:** Table data. All right. They'll, they'll hide certain table data cells I don't know if I intellectually knew you could do that.

[00:11:47] **Ben:** I've, I've definitely hidden whole rows before,

[00:11:51] **Ben:** but I don't think I've strategically hidden subsets of TDS within a row. And that's one of the things that they do,

[00:11:58] **Adam:** I mean, I, I like that in concept because you, you can kind, kind of combine that with like, you know, a, a span or a div or whatever in another column that it only becomes visible at that same break point. So you're kind of like moving the

[00:12:09] **Ben:** what they do. That's exactly what they do. They, they, they essentially duplicate some of the rendering.

[00:12:15] **Ben:** And it's hidden on, on the bigger screen. So it's like, I should be excited. This is a whole different leveling up of that particular skill. And I, I don't know, maybe I'm just intimidated.

[00:12:25] **Ben:** I feel like I'm, I'm, I'm not gonna do it well, so I'm not motivated or it's just gonna be harder than I want it to be,

[00:12:31] **Adam:** Tell

[00:12:31] **Ben:** don't know what done looks like as part of the problem.

[00:12:34] **Adam:** tell yourself that if you don't do this, then you have to do Salesforce integration, so that'll motivate you.

[00:12:39] **Ben:** So anyway, we're going into a holiday, so that'll be a little mental refresher except for it's gonna be people, so that's gonna exhaust me. But,

[00:12:47] **Adam:** Yeah.

[00:12:47] **Ben:** anyway, that's me.

[00:12:48] **Adam:** Sean, do you have a,

## [00:12:49] Shawn's Triumph and Fail

[00:12:49] **Shawn Oden:** All right. My turn.

[00:12:50] **Adam:** for a fail?

[00:12:51] **Shawn Oden:** I can do both. I'll start with the triumph, I guess. I just got back from PASS Data Community Summit in Seattle. It was an extremely exhausting three days. I, I can't believe it was that short, but I made it. I'm back. So far I haven't heard of anybody getting sick, so that's good.

[00:13:09] **Shawn Oden:** Right?

[00:13:10] **Adam:** Yeah. To start.

[00:13:12] **Shawn Oden:** So maybe try if, I'll let y'all know next week.

[00:13:14] **Ben:** this is a conference about

[00:13:15] **Ben:** databases.

[00:13:16] **Shawn Oden:** yes. it's the really big Microsoft SQL Server that they've done, for years. I guess. I've been wanting to go for 10, so at least years, but get anybody to pay for it,

[00:13:29] **Adam:** Yeah.

[00:13:31] **Shawn Oden:** and then, so I, I did what I do best and I just speak at 'em.

[00:13:34] **Shawn Oden:** And they pay for 'em?

[00:13:36] **Ben:** it at Microsoft?

[00:13:38] **Shawn Oden:** No, it was in Seattle, at the big convention center. They're really pretty plays.

[00:13:43] **Ben:** Oh, very cool.

[00:13:45] **Adam:** Cool.

[00:13:46] **Shawn Oden:** So, and then, a fail. I'm gonna blame on your listeners and you, Adam, because. When y'all suggest a book to listen to, you don't suggest a single book. You suggest one that's got like 15 books,

[00:13:59] **Adam:** Sorry. Sorry, not sorry man. I, I go through a lot of books, so I need those long series, man.

[00:14:05] **Shawn Oden:** And yes, and I have an hour, hour and a half community each way every day, so that's perfect time.

[00:14:10] **Adam:** exactly.

[00:14:11] **Shawn Oden:** it's, it's normally perfect time to listen to podcasts and stuff, but again, y'all have called me off on the book tangent, so

[00:14:17] **Adam:** Yeah, it's

[00:14:18] **Shawn Oden:** I admittedly have to catch up.

[00:14:21] **Adam:** Sometimes I have to like force myself. There's, there's a couple of podcasts that I listen to that are like daily ish, but they're short, so I'll let 'em stack up for a week and then I'll blow throw 'em all in a day or something, and,

[00:14:30] **Shawn Oden:** I feel lost. I haven't, I haven't kept up with them. I don't know what's going on anymore.

[00:14:36] **Tim:** Hey, as long as you listen to us, you're good. You don't, you don't need anymore.

[00:14:40] **Shawn Oden:** giving me books.

[00:14:43] **Ben:** I was talking to my wife just last night. We were at our local bookstore and it popped into my head, it'd be kind of a funny TV plot line, almost like a, twilight Zone where, a couple they go on a blind date and one of them is, an academic and she's talking about all the books that she likes to read.

[00:15:00] **Ben:** And he's talking about, oh, I am such a voracious reader and sometimes I read 2, 3, 4 books a week. I just can't help myself. I'm, I, I love it. It's one of my favorite pastimes. And then eventually she goes back to his apartment and it turns out it's all like great school children's books, like little, like coloring books and stuff.

[00:15:19] **Shawn Oden:** Nothing wrong with coloring books.

[00:15:21] **Ben:** I just, I dunno. For whatever reason that am me.

## [00:15:24] Death Preparedness for Geeks

[00:15:24] **Adam:** Sounds, a little bit like a, like a college humor. It's catch. well, then let's move on to today's topic. death, you know, that perennial, happy place. So as I said earlier, Sean, you've done, a couple of, you've presented a couple of times on this topic, not of death itself, but on, you know, what you leave your loved ones when you go and how to, how to do right by them.

[00:15:45] **Adam:** so, what inspired you to start advocating for death? Preparedness for geeks? Yeah.

[00:15:50] **Shawn Oden:** I guess first of all, I need, I do need to throw out my disclaimer here. I am not a lawyer. I did, I did not play one on tv. I did not sleep on Holiday Inn Express last night. So. Please, if you have any questions, especially in this realm, it very much gets into the legal, legal stuff.so, but my experience, what what really got me into it is that, I mean, two things.

[00:16:13] **Shawn Oden:** the first thing was, when my grandmother passed away several years ago, she didn't have any digital stuff, but she had a whole lot of stuff, stuff. and it was just, it was a, it took, pretty much three weeks before we just gave up of trying to organize the stuff that she had.just trying to, trying to deal with, deal with her house.

[00:16:35] **Shawn Oden:** And it was a house that my, my dad and, and, his, siblings had grown up in. So they had it for quite a while and it was a tiny little house, but it still took us three weeks. Every time we opened another door, there was more stuff.

[00:16:46] **Adam:** Oh my.

[00:16:47] **Shawn Oden:** And that, I mean, that was the physical stuff. And then what really got me thinking about the, the geek side of it was that my best friend passed away a few years ago he had a whole bunch of digital stuff.

[00:17:00] **Shawn Oden:** and when, he finally finished up probate, his dad had come in and, and was selling off his stuff and I was like, I, I don't know what he's got. I don't think his computer should be just given away or sold off. So I went, I bought all his computers so that I could make sure that anything that was on there got properly disposed of.

[00:17:18] **Tim:** You're solid, dude.

[00:17:20] **Ben:** Yeah,

[00:17:21] **Shawn Oden:** Thank you. Thank

[00:17:22] **Ben:** this was, this was Brett, Brent.

[00:17:23] **Shawn Oden:** Yes, it was,

[00:17:25] **Ben:** He, I saw a photo of him in your presentation and he looked very familiar. Was he in the

[00:17:30] **Shawn Oden:** there's a picture of you with them,

[00:17:31] **Ben:** Oh, okay. That's.

[00:17:33] **Shawn Oden:** Yes. He was very proud of that.but, yeah, he was, he was in the ColdFusion user group here with me, or he was actually the manager that I was the co-manager to before I suddenly found myself being the manager, for a while. But, yeah, he had a whole bunch of stuff.

[00:17:49] **Shawn Oden:** he also had, when Bitcoin first started.

[00:17:53] **Tim:** I was about to ask this chain for Bitcoin.

[00:17:56] **Shawn Oden:** I, I found evidence that he had had it. I knew from a fact, for a fact that he played with it. I'm glad I did not find any wallets because I did not have any keys or anything like that to it. And that would've been really sad.

[00:18:10] **Shawn Oden:** Or like, oh yeah, I got this wallet, but there is no way for anybody to get ahold of it.

[00:18:14] **Tim:** Hmm.

[00:18:15] **Shawn Oden:** so yeah, there's, just, just thinking about that then I was thinking to myself, I mean, as you can see, all the crap behind me, I've got so much stuff here that if when I pop off, my wife's gonna be in trouble.

[00:18:27] **Tim:** So, so the listeners can't see what's behind him? He really does. I mean, it

[00:18:32] **Tim:** is a packed, it is a packed corner of stuff. I'm trying to take a look at it.

[00:18:36] **Shawn Oden:** Oh, you're actually seeing my bookshelf. The, the, all the computers I've got 1, 2, 3, 4, 5, 6, 7, 8, 9 monitors in this room.

[00:18:45] **Ben:** Oh,

[00:18:45] **Ben:** that's a lot of monitors.

[00:18:46] **Tim:** it's a severed head that we're concerned about.

[00:18:48] **Shawn Oden:** Oh, you like the, you like the severed head?

[00:18:50] **Tim:** that's what's the.

[00:18:54] **Shawn Oden:** That's actually a bank that I've had since I was a little, little kid. My, my, actually my grandmother that I was just talking about was the one, she worked at a bank and she gave me that with pennies or I put pennies in it when I was little that are still in there. So a nice good penny that doesn't exist anymore.

[00:19:10] **Shawn Oden:** No kidding. So, yes, the, the severed head.

[00:19:17] **Adam:** Yeah.

[00:19:18] **Shawn Oden:** But yeah, that, I mean, that was, that was pretty much what got me into just realizing how much stuff that I had and how lost. Everybody would be,

[00:19:26] **Adam:** Right.

[00:19:27] **Shawn Oden:** if, and I would hate for them to just get rid of this stuff. 'cause this is, sadly, it's an embarrassing amount of money that has been invested in this garbage over the years.

[00:19:37] **Tim:** right?

[00:19:37] **Adam:** It does accrue.

[00:19:39] **Tim:** It, it does. So a couple things, you know, George Carlin had a bit talking about, humans and how he just collect all these things in life.

[00:19:48] **Tim:** He says, but you ever noticed that all your things that you have, it's stuff, but everybody else's stuff is junk and houses are just places where you put all your stuff.

[00:20:02] **Shawn Oden:** Oh yeah. That's what most of that is.

[00:20:06] **Tim:** Yeah. Stuff are junk. Well, to me it's junk

[00:20:09] **Shawn Oden:** yes. Sadly to me, it's getting to be junk. It's like, why do I even have this anymore?

## [00:20:14] Getting Started with Password Managers

[00:20:14] **Tim:** But you do bring up an interesting point. Like it, so back in the old days, you know, if you, you know, grandma would leave you her China.

[00:20:22] **Tim:** Physical things, right? They're very easy, they're portable. You could touch them. But now we're in this thing of, all right, so, so and so died and they had this really huge like email list or Facebook following, or Twitter account or all these, everything in this, like even fi all, all your financial stuff is all online, right?

[00:20:43] **Tim:** At least how to access it. and no one thinks, all right, we need to, we can't just say, okay, here's your stuff from grandma. Now it's all like, oh, well, there's digital passwords, there's everything. So yeah, I think it's, quite timely. Your, your topic that you're talking about.

[00:20:58] **Shawn Oden:** Hopefully not timely. Hopefully you don't eat it for a long time.

[00:21:00] **Tim:** I didn't mean me personally. I, I was, I was, I was looking at you.

[00:21:04] **Adam:** Alright. All right. So, you talked about, you know, how stuff accrues and something that, stood out to me when I was watching your presentation was that you mentioned several times about, your grandmother's high school diploma. I, I was just curious, like, was there a specific reason that you mentioned that a couple of times or, like is that it doesn't seem like something that stands out as soup or important to like, have and maintain into the future?

[00:21:29] **Adam:** So I'm just curious what I'm missing

[00:21:31] **Shawn Oden:** So it's, it was kind of one of those things that, that, as, as you get older, you find out things about your family that you never knew. I mean, I had no idea that my grandmother got married at 15 years old. after literally three days of meeting, my grandfather,

[00:21:47] **Adam:** Wow.

[00:21:48] **Shawn Oden:** they, they ran off and then, he was a soldier and, and, he got, he was home on leave.

[00:21:53] **Shawn Oden:** They got married. He went back, to war for another year and then came home and said, and she said, told her parents, I'm gonna go live with my husband right now. And they're like, wait, you're what? So, but that thing, I found out too that when, my dad was born, she had dropped outta high school before I guess the, the first kid came.

[00:22:15] **Shawn Oden:** And so she had never gone back. And then when my dad was born, I guess she just kept being mom for a while until he was in high school and then did not want to graduate or did not want him to graduate without her also being, basically, she just wanted to do it for herself, I guess. But she was secretly going to night school and nobody knew.

[00:22:36] **Adam:** Gotcha.

[00:22:36] **Shawn Oden:** And even, even my dad, they actually found the diploma. when they were cleaning up her stuff, founded in one of her dressers, hidden at the bottom of one of her dressers, and she graduated the same year that my dad did.

[00:22:48] **Tim:** Wow. So, so, yeah. So that's an interesting story, right? That, that there's value. Value in that story. Plus the diploma. The diploma. My diploma. I don't even know where it is. I don't

[00:22:57] **Shawn Oden:** well, and plus those are, those are the kind of things that may just flat out disappear, in the electric world or the electronic world.

[00:23:03] **Adam:** Yeah.

[00:23:04] **Shawn Oden:** So, I mean, I've got tons of documents that are gone. They're going to be gone. They probably already are gone. I haven't opened 'em in forever. And electronic things kind of don't stick around forever.

[00:23:17] **Adam:** sure. Well, so let's assume for the purposes of this discussion that it's an easy sell to the people listening to this, right? Like they already are bought into the fact that like, okay, I need to be prepared for this. We don't have to convince them. So like aside from talking to a lawyer or you know, somebody, that might be a professional, like what's the easy places to start?

[00:23:38] **Adam:** For me, the first thing that comes to mind is like, use a password manager and have a trusted friend who has that, you know, if it's your spouse or whoever that has access to that master password. Mm-hmm.

[00:23:49] **Shawn Oden:** I, I think that's actually probably the best place. That's something that I've tried getting my family on the bandwagon with using 1Password or something like that. and then I try to do my best to share everything, that we do, like our banking logins or our, our, bill paying stuff, the cable company, stuff like that.

[00:24:09] **Shawn Oden:** So that if I'm gone, at least my wife will be able to access it. And I mean, if we're both gone, that's, my kids are gonna have to worry about that, I guess.

[00:24:17] **Adam:** Right.

[00:24:19] **Ben:** I had a, an interesting thing happen to me recently because my wife runs the house and she does all the bills and deals with all the mail, all the utilities and everything. So I, I don't know what happens around here. Heaven forbid if anything happened to her. I mean, like everything would fall apart, but that's not the point of the story.

[00:24:39] **Ben:** I did have to go to the DMV recently to renew my license, and I had to bring with me pieces of mail that proved I live here and like literally nothing is in my name. It was,

[00:24:53] **Adam:** It's got my Blockbuster card.

[00:24:54] **Ben:** I know. I was like, I'm like literally the thing that finally put me over because I have my social security card for reasons I can't even imagine that I, I'm blown away that I still have it and I have my expired passport. But then the thing that put me over the limit of like, you need this many documents for this kind of stuff, was the letter that they had sent me that my ID was expiring, came to this house with my name on.

[00:25:16] **Ben:** I was like, yes.

[00:25:18] **Shawn Oden:** There's something

[00:25:20] **Adam:** Yep.

## [00:25:20] Organ Donation and Medical Wishes

[00:25:20] **Ben:** the thing, actually, when I was listening to your presentation, the thing that struck me was the whole organ donation and the do you wanna be buried or cremated? Because, when I got married, the first thing that people told us to do was at least get a will in place so that, you know, you have shared things.

[00:25:38] **Ben:** Now people know what to do with that. And I don't, I don't even think that's stuff is in there.

[00:25:42] **Adam:** It can,

[00:25:43] **Adam:** be. It depends on what you wrote in there. Yeah.

[00:25:45] **Ben:** yeah, I'm not even sure. I'd have to double check.

[00:25:48] **Shawn Oden:** I'll tell the everybody who's listening right now, if y'all are in the position, I wanna be cremated. They can have whatever pieces they want. I don't want the whole thing gone. But cremate me,

[00:25:59] **Shawn Oden:** I mean, I say this because I, I didn't realize, I mean, I've always known this kind of a big deal.

[00:26:04] **Shawn Oden:** I mean, it's very, it's a very personal decision for somebody. but, again, back to my grandmother again. Another, another thing that happened with her is that, that, she was actually staying at my dad's house, when, she passed away and he was on a cruise. He was in the middle of the ocean. And, my brother and I took her to the hospital thinking that, that she was having an asthma attack.

[00:26:26] **Shawn Oden:** And they basically came back to us about two hours later and said, your grandmother passed away.

[00:26:31] **Shawn Oden:** it says that she's an organ donor, but we don't know which organ she wants to donate. What, what do we do?

[00:26:39] **Tim:** See, I didn't know, so I didn't know. You could specify. I thought you just organ donor, they just take

[00:26:42] **Shawn Oden:** or sorry. No, they, she didn't, they didn't even say no, she did not have it marked at all that, sorry I was wrong.

[00:26:48] **Shawn Oden:** So they said what? Because they have to hurry. That's, that's kind of a time sensitive thing.

[00:26:53] **Tim:** yeah, yeah.

[00:26:53] **Shawn Oden:** And they said the, you know, we need, we would like to, you know, if, if, if she's an organ donor, we need to do what we need to do. And I was like, hold on, let me call my dad and couldn't get ahold of him. 'cause he is in the middle of the ocean.

[00:27:06] **Shawn Oden:** I tried to call my uncle, I tried to call my aunt and neither of 'em were home. So the decision fell on me and I was like, oh God, what do I do? I mean, the, the, I I just had to think, what would she do? I hope I know well enough. And I said, yes, she would want to be an organ donor.

[00:27:20] **Shawn Oden:** And so they did. And then when I finally got ahold of my dad, he was like, yeah, that's, that's what she would've wanted to do.

[00:27:28] **Shawn Oden:** I was like, okay, good God. That was, that was a, a lot of weight off my shoulders because I did not want to make, again, that's a very personal decision. That's really not my decision to make.

[00:27:39] **Shawn Oden:** and I, I didn't know for certain. I just pure guest and I, I was right. So that, that was good. Oh, you don't even want to know how much.

[00:27:51] **Adam:** Yeah, I bet.

[00:27:52] **Ben:** So I recently learned, and when I say recent, I mean, I don't know, maybe in the past like five or six years, that there is a pattern where people will put an ice contact on their phone. And this predates the whole immigration stuff, like a, in case of emergency contact, for, and I think that's maybe something you can access even if the phone is locked.

[00:28:13] **Ben:** I'm not sure exactly,

[00:28:14] **Shawn Oden:** I, I believe so. It show, it'll show up on the, the screen.

[00:28:18] **Ben:** but this makes me wonder. The, I'm, I'm shocked that I have not heard of some sort of a productization of this. Oh, there you go.

[00:28:28] **Shawn Oden:** There you go.

[00:28:30] **Ben:** Like I'm, I'm surprised that there is not like a, you know, you get your phone and like, here's six end of life questions that anyone could access on your phone just in case, or, or, or like something on your Apple.

[00:28:42] **Ben:** Watch it, it just seems like there'd be an easy little, uh, win there. I'm surprised. I've never heard of something like that.

[00:28:48] **Tim:** Well, I, it, so, I mean, I'll confirm for you. So I just went on my iPhone and it's probably different on Android, but I pressed the up volume button and the power, the button on the right side, and it has slide power, slide, the power off medical id, emergency call. If I slide medical id, it has my wife's contact information.

[00:29:08] **Tim:** It has my name, my age that I'm an organ donor, my father's phone number, as well as my height and weight. So yeah, so if you have it done in your phone, yeah. So, so, and you don't need a password to see that. So that's what, that's what emergency responders will do. If they find out like you're, you're not responsive, they'll click find your phone, click that,

[00:29:30] **Ben:** I, I also have stuff in here. I must have filled it out that when

[00:29:34] **Ben:** I got the phone and now I don't even remember.

[00:29:35] **Tim:** one of those things you do once and you forget about it. Right.

[00:29:38] **Shawn Oden:** Uh, again, hopefully you don't need it for a while.

## [00:29:41] The Living's Needs vs The Deceased's Wishes

[00:29:41] **Tim:** Hopefully you don't need it. And, and also in my, my wallet, I carry, a, a durable power of attorney for my medical wishes,

[00:29:48] **Shawn Oden:** Yeah, that, that's another very good thing to have.

[00:29:50] **Tim:** it's, it's a little, it's a card, it's full page, but it folds down to like a little card and I slide it in there, it's right behind my license or with slid up. It says Durable power of attorney so that, you can give your medical wishes if there's certain, procedures you do not want done to you, that they'll, you know, it's a legal document signed by two people, has names and addresses.

[00:30:11] **Tim:** So that's something that you can do as well is do a and you don't really even need a lawyer to do that. It, although it does need to be legal. So maybe to consult a lawyer on that. I was thinking just recently, Sean, so this year my one, one of my aunts. Just suddenly died.

[00:30:28] **Tim:** She was out working in the garden. She was super healthy, we thought, and then had a bad headache. Came inside, sat down, told her husband, she says, or my uncle, she said, my head hurts. That's the last thing she said. She had a massive stroke

[00:30:42] **Ben:** Oh

[00:30:42] **Ben:** my God.

[00:30:43] **Tim:** and her wishes was she did not want to be resuscitated.

[00:30:46] **Tim:** She was a health food, like holistic. She was like, she was the aunt who like didn't give you chocolate. She gave you car. I mean, that was, she was all health food. she didn't believe in a lot of things. She didn't believe in medicine. She didn't believe in she, so, but I, I, I tell the story to say this, that even though you might plan all these things, sometimes the needs of the living outweigh the needs of the dead.

[00:31:12] **Tim:** Because my uncle couldn't let her, he, he knew, everyone knew that my wi aunt did not want to be on a machine, but they tried getting her to lie. They tried bringing her. He, and they're like, they told him like, we need, we have to decide. She, you know, what's, what do you want to do? And he's like, I need time to say goodbye.

[00:31:33] **Tim:** And so they kept her on the machine for about, about five days, so all the family could come, people could come out of town. I drove up and it was an assistant, you know, one of those in, you know, hospice places. Took her off the machine, watched her take her last breath. We all said goodbye. So, I mean, in one hand I was like, I know she would've hated this.

[00:31:57] **Adam:** Mm-hmm.

[00:31:58] **Tim:** But, you know, I, I, I don't know what people, you know, everyone has different ideas about what happens when people die, but in my mind it's like she's not here right now and she can't tell us right now. This is what everyone in the room right now needs. So to just be able to say goodbye. So it's not directly to your point, you're more about like making sure that everybody can access stuff, but just know that once you're dead, you have no control.

[00:32:24] **Tim:** What happens after that stuff's gonna happen. And unless you can ghost yourself back, ain't, you have no control over it.

[00:32:34] **Ben:** That's why you gotta set up a dead man switch to send out all those, the, all those emails you meant to send out.

[00:32:39] **Tim:** Exactly.

[00:32:40] **Shawn Oden:** that's right.

[00:32:43] **Ben:** I,

[00:32:43] **Shawn Oden:** Or you gotta have your trusted friend that will delete the stuff you don't want anybody else to see.

[00:32:47] **Ben:** You know, that's for

[00:32:48] **Adam:** I, I don't think that's as necessary Now that we have, incognito mode browsers.

[00:32:52] **Ben:** Yeah.

[00:32:53] **Adam:** If you, if you have a, if you have a shady search history that's on you.

[00:32:57] **Shawn Oden:** there you go. True. True.

[00:32:58] **Tim:** DuckDuckGo baby.

[00:33:00] **Ben:** going back to something Tim was saying about how sometimes it's for the people who are still here, and I, and I say this, not to make light of anything, but, when my dog died this past August, it was very tough for me. It, I, I have to say it was tougher for me than when my dad died.

[00:33:16] **Ben:** And my dad died like 20 years ago. So I was also very young, and like. I was probably at an age where I would, I thought like nothing bad would ever happen to me. So like my mortality was not, never called into question, but really grieving for my dog actually comforted me in my own mortality. Going back to what Tim was saying, that it kind of put in perspective that the hard part is for the people who are still here.

[00:33:41] **Ben:** Like, I'll be dead and I, you know, that'll suck, but I won't care. And really it's for everyone else. That's gonna be the hard part. And I, I know that's like, sounds weird that that's comforting, but that, that, that gave me a new perspective that really kind of put me at ease with my own mortality. Not that I want to die, but I'm, I'm somehow more comforted by it.

[00:34:02] **Tim:** I think I've mentioned this once before and I'm gonna, but I'm gonna mention again regardless. Stephen Colbert kind of talks to, he'll ask people like some deep questions and I imagine he probably proofs it with the guess beforehand, but sometimes he asks like, what do you think happens to you?

[00:34:16] **Tim:** What do you think happens when we die? And he asked that of Keanu Reeves, who's like,

[00:34:22] **Adam:** That a great answer

[00:34:24] **Tim:** yeah, he had a fantastic answer. He said, he's such a beautiful soul, Keanu. he says, I know that the people we leave behind will be sad

[00:34:31] **Adam:** and miss us. Yeah.

[00:34:32] **Tim:** and miss us. I mean, that's honestly. The only scientifically proven thing we can say about it,

[00:34:39] **Shawn Oden:** That's true.

[00:34:41] **Tim:** people have faith, and whatever your faith is, that's valid.

[00:34:44] **Tim:** You believe it. I, I, you know, no one's gonna argue with that. I'm not gonna argue with that, but yeah, a hundred percent. The people that love you, they're gonna be sad and they're gonna, they're gonna miss you.

[00:34:56] **Adam:** not to be a boy scout about it, but I would like to come back to the idea of preparedness.

[00:35:01] **Adam:** So we talked about passwords and using a password manager and having that trusted friend or spouse or somebody who has access to your password manager. That's good. and I think I already know the answer for myself, but I wanna make sure that we discuss it and, and that is, you know, what about things that aren't passwords, right?

[00:35:16] **Adam:** So, if you're gonna have a network diagram for your home lab or like just a list of like, this is where the family photos are stored, or that sort of thing. Like how do you A, preserve that stuff and B make sure that the right people find it at the right time. And I said, I already had the answer for me.

[00:35:35] **Adam:** You know, I use 1Password as my password manager and it has a nice feature where it holds more than just passwords, right? You can put credit cards in there, you can put your identity quote unquote as an address and stuff in there, and you can just have like secure notes. And so for me, I have a bunch of secure notes with that sort of stuff in it, but.

## [00:35:49] Maintaining Documentation Over Time

[00:35:49] **Shawn Oden:** For me, honestly, I don't do as good of a job as I, I would like to, I've got a couple of, of little notebooks or stuff that I've written some of this stuff in. I've kept some of it in a file cabinet. I, I have done a really bad job of actually getting it all into one place, to where whoever is left behind can find it.

[00:36:09] **Shawn Oden:** Cobbler's children.

[00:36:11] **Shawn Oden:** right.as far, I mean there, there's a couple of good resources. I think that, that, some links that I left at the end of my presentation there of different online resources and there's some other things that I found, afterwards, I'll share those links with y'all later.

[00:36:25] **Adam:** Yeah, we'll put those in the show notes for sure.

[00:36:27] **Shawn Oden:** one of them, especially deals with like, again, geek stuff.

[00:36:30] **Shawn Oden:** What do you do with your electronic stuff? And when she wrote it, that was her whole, her whole. impetus, I guess, was to, she had a friend that was a, had a whole bunch of technological stuff and what does he do with his stuff, what does his wife do with his stuff? And I mean, just even simple things about like, what happens if your router dies?

[00:36:51] **Adam:** Yeah.

[00:36:51] **Shawn Oden:** are you, is she gonna be just without an internet anymore? stuff like that. And I mean, just, and, and it's basically, she just basically tries to think, and that's the hardest part, I guess, is trying to think of everything that you've got that somebody else might need to know how to do if you're not there to do it.

[00:37:09] **Shawn Oden:** I'm like, my, my Plex server sitting right here behind me. Just, just the other day it, we had an electrical issue and it shut off. And so for the entire day, nobody could watch tv.

[00:37:18] **Adam:** Yeah.

[00:37:21] **Shawn Oden:** I mean, that, that's not a big deal until it is a big deal.

[00:37:23] **Adam:** Right. So dad's not around to, to

[00:37:27] **Adam:** restart the Plex server again.

[00:37:28] **Shawn Oden:** Exactly.but yeah, I mean the, the hardest thing is just, just getting it all together, getting it all organized and just again, I guess the big thing is it doesn't have to be done all in one sitting, it would be better if it was done.

[00:37:44] **Shawn Oden:** 'cause if, if you know it and you don't tell anybody, then have no control over what happens.

[00:37:50] **Adam:** Right. Just trying to think of like, so yeah, gathering all that information is gonna be really hard. I think it might be even harder to maintain it. Right? Like, okay. I went through the, the two week exercise of cataloging my entire digital life. Now it's been two years and a whole bunch of stuff has changed, and now

[00:38:07] **Adam:** I have to get that back.

[00:38:09] **Shawn Oden:** Right. And that, that's one, one thing that I definitely suggested was, dating the things when, when you put 'em in there so that at least. Whoever has it knows, oh, well this was written like eight years ago. that might no longer be, valid.

[00:38:23] **Ben:** I'll tell you,I don't even remember how this came up in a conversation with my wife. One time we were talking about someone's house had burned down, I think, or maybe this was during the, the California fires last summer, and,

[00:38:34] **Adam:** Yeah,

[00:38:35] **Ben:** and I was saying that it's just awful, the devastation. I said, but on some level, part of me would kind of love to have everything I own.

[00:38:45] **Ben:** Burn. And, and, and she, she looked at me like I was a total psychopath. And I, and I was like, no. I was like, then, then the

[00:38:52] **Adam:** That's the only way

[00:38:52] **Adam:** Ben's ever gonna get to inbox zero.

[00:38:55] **Shawn Oden:** You

[00:38:55] **Shawn Oden:** know, you could clearly see my office behind me, so I'm, I'm all about to burn it down and start over.

[00:39:00] **Ben:** you, because that's, that's what I said. I said like, how much hand ringing do I do about, like, all the junk I have on my shelves and I have boxes of mementos down in the basement and, and just like little widgets that I've gotten, even just at conferences, you know, the free swag that comes in the bag. And I'm like, I don't really need this little rechargeable battery pack, but I probably shouldn't throw it out.

[00:39:24] **Ben:** Right. I mean, I might need it one day. And like, if it was just all burned, then like, no one would ever have to make that decision.

[00:39:30] **Shawn Oden:** Yeah, I've got some layer books on the shelf back there, so,

[00:39:34] **Adam:** Perfect handling.

[00:39:36] **Shawn Oden:** exactly.

[00:39:37] **Ben:** I sometimes am enamored by the whole, austerity or like brutalist, like the people who live in just like a concrete room with a, with a desk and a bed on the floor. I mean, I, I couldn't do that. I've grown to like all of the amenities that I have in my life, but, there is a certain respect that I have for it. Like the clarity, the cleanness.

[00:40:00] **Shawn Oden:** It would definitely make things easier.

[00:40:02] **Ben:** Yeah,

[00:40:03] **Tim:** the one password stuff even that I, I try, so we have a 1Password family plan and I'm super religious about it because I basically put things in 1Password before I even put them in the site that uses them.

[00:40:15] **Ben:** And, uh, yeah, it's my wife not as good.

[00:40:20] **Adam:** Oh,

[00:40:20] **Ben:** And sometimes she'll be trying to log into something. She's like, ah, I can't remember my password. I say, oh, did you put it in 1Password? And the look that she gives me, she's like this guy.

## [00:40:35] Death Certificates and Legal Processes

[00:40:35] **Shawn Oden:** familiar.

[00:40:37] **Tim:** yeah, so I, I was looking at some things that people recommend that you should do. You we're talking about the prep work, but what actually happens when someone dies? And some of the advice was you need to get the death certificate, right? So get

[00:40:50] **Tim:** the, get the death certificate because with that, it's a legal document.

[00:40:54] **Tim:** And of course you gotta make funeral memorial arrangements, but then you need to notify, there's several key government institutions in the US that you need to notify, like Social Security administration. 'cause you don't want some scammers

[00:41:09] **Shawn Oden:** and they

[00:41:09] **Adam:** their identity. Yeah.

[00:41:11] **Tim:** their identity and using it to, to get loans and things.

[00:41:14] **Tim:** Financial institutions. So, your banks, credit unions, and you need that death certificate to say that they've died. Give 'em their social security number, those things. So you, you definitely need the certificate. You need their social security number, the bank account numbers, inform insurance companies,

[00:41:31] **Adam:** And you send all this information to me?

[00:41:33] **Tim:** right. and then credit bureaus, utility companies, service providers. What I'm noticing about this, this whole process, although we're talking about, because we're a tech podcast, we're talking about all the digital stuff, this whole process of the notification to institutions, it's all paper.

[00:41:51] **Adam:** Yeah.

[00:41:51] **Shawn Oden:** There you go.

[00:41:53] **Tim:** It's all paper.

[00:41:54] **Tim:** So get your paper, get your paper straight. I think all the, the extra stuff of, of like, 'cause you know, it's like I wanna make sure that when I die, like a stock account that I have, that I've been putting away into, I mean, my wife, she's named a beneficiary, but I wanna make sure that my wife and kids get all that stock transferred to them

[00:42:13] **Tim:** so that they have the accumulated wealth that I've worked my entire life for.

[00:42:17] **Tim:** So passwords kind of help make it faster, but I mean, there are slower ways to do it, but it is super slow and super legal and

[00:42:27] **Shawn Oden:** And they have to know that it exists.

[00:42:29] **Ben:** Yeah. So actually speaking of that, My wife, her lineage is Irish. and I think a lot of people in this

[00:42:38] **Ben:** country, that's the best blood. a lot of people in this country are probably of an age where there's a, not a, you know, like a non-zero to actually pretty good chance that you're grandparents or great grandparents.

[00:42:52] **Ben:** Were from a different country and there are a lot of countries, and I'm just finding this out now, where if your, like grandparents were from Ireland, you can apply for Irish citizenship if you get their birth certificates and their death certificate and you can prove the lineage.

[00:43:06] **Ben:** But her parents didn't know that that was a thing. So they were born here, so they had US citizenship. They didn't know that they could get their Irish citizenship. And had they known and had they gotten it, it would actually be much easier for her to do it. She's having to jump through all these hoops now, so that could, that's like another, like a pre-mortem thing you could do now like, 'cause they're like some cool, fun citizenship you have access to that you never thought about asking about.

[00:43:32] **Ben:** Get those birth certificates.

[00:43:34] **Tim:** Yeah, my, my daughter's going through that right now. She, after we got back from Portugal, she immediately repli applied for her British passport, but it really helps to have, 'cause she can get it through her mother, but she, you know, it's also through her grand, they, they need proof of the grandparents' nationality as well.

[00:43:49] **Tim:** so yeah, having them around and go, Hey, can you send a copy of the, your birth certificate? That'd be great.

[00:43:54] **Adam:** It could be super useful for no reason in particular.

[00:43:57] **Tim:** All right.

[00:43:58] **Shawn Oden:** Right.

[00:43:59] **Adam:** definitely remember that if you do, you, everybody should have a will or

[00:44:04] **Shawn Oden:** something like that,

[00:44:06] **Shawn Oden:** no matter how old you are. 'cause again, you never know. but this is definitely something that I didn't even bother to even it. I mean, it was an impossibility until I was probably 40 years old. And it's like, oh God.

[00:44:16] **Ben:** Right.

[00:44:17] **Shawn Oden:** I think that's, that's when you hit the age that you start having friends that, that you are like going, oh man, he was only 40,

[00:44:25] **Adam:** Yeah.

[00:44:26] **Shawn Oden:** so I went to school with him.

[00:44:28] **Tim:**

[00:44:28] **Tim:** I've started saying, Ooh, they're only in their seventies.

[00:44:32] **Shawn Oden:** right. the, the other thing to keep in mind too, yeah, definitely have the will, but, yes, all the power of attorneys and stuff like that because there's also the, you can lose a lot of power to do whatever you wanted to do with your stuff,if you don't have those kind of documents.

[00:44:50] **Shawn Oden:** but also they, they are public documents, so don't put passwords in them. Don't put your social security numbers in them, stuff like that, because as soon as you file 'em, they are immediately available to whoever wants to get 'em. And there are people that. Basically have services that will sit there and scrape those things up as soon as they're available, and they'll either use them to, to help you or they'll use 'em to scam you flat out.

[00:45:14] **Shawn Oden:** so yeah, just be, be very cognizant of that kind of thing.

[00:45:17]

[00:45:17] **Ben:** also, like none of these documents are set in stone. They evolve over time. So I'm assuming that if people were motivated to do so, there's probably like a very low hanging fruit approach. Like they could probably go to a LegalZoom or Zocdoc or something and get like an off the shelf, like, Hey, just gimme a will so that at least I have something.

[00:45:40] **Ben:** And then they could go and get an actual attorney and, you know, work on who gets what and the beneficiaries and the percentages and you know, that stuff can change. It's not like you, it's not a one shot kind of thing.

[00:45:51] **Shawn Oden:** Right. Yeah. I think the, uh, nola uh, nola.com, I think they have a lot of stuff, a lot of free resources. for that kind of stuff. And it, it basically, they set you up to start slow, but just start, I guess is their big, big point. 'cause you're not gonna be able to do it all in one sitting 'cause you'll get bored so fast.

[00:46:12] **Shawn Oden:** You're it's hours and hours and hours of work to get the stuff that's actually needed. More stuff than you probably realize that you even have.

[00:46:19] **Adam:** I don't think you meant nola.com. 'cause that's like a New Orleans news.

[00:46:24] **Shawn Oden:** know, it sounds like it, it sounds like it, but it's, it's like, something legal. But it's N-O-L-A-N-O, sorry. NOLO.

[00:46:32] **Adam:** Ah, okay.

[00:46:35] **Tim:** nolo.

[00:46:35] **Shawn Oden:** close. Nolo, not Nola. Right? Nolo.

[00:46:40] **Ben:** this is gonna sound really ridiculous, but growing up, every time I would watch some sort of a drama piece on TV or a dramatic movie and someone dies, there was always this grand reading of the will and everybody goes to the lawyer's office and they're all, you know, waiting to hear what it is that they get.

[00:46:58] **Ben:** And I literally just assumed that's how every death happened. And then, and then I think I remember, I dunno if it was at my dad's death or someone's death, and I was like, when do they do the reading and the will? And they were like, what are you talking about? I'm like,

[00:47:11] **Ben:** you know, like, yeah.

[00:47:14] **Tim:** Yeah.

[00:47:15] **Ben:** It was just funny.

## [00:47:17] Trusted Persons and Professional Alternatives

[00:47:17] **Tim:** So I, I, I'll point out one hole in all of this. So. A lot of things that we talked about here are based off of having a trusted person to give this information prior, right?

[00:47:28] **Shawn Oden:** Yes.

[00:47:28] **Tim:** So if you're going through a messy divorce, you don't necessarily want your spouse to have it because they could maybe use it to steal your money or get dirt on you. Maybe you don't have good friends. I don't know. So, if you don't have a trusted person, you know, it's, there are legal people, you know, you can go to a lawyer, you know, that deals with this kind of thing and say, Hey, I, I'm gonna send you information maybe once a year we have a, a call or a meeting or something, and give you information so that if I die, that you'll take care of this for me.

[00:48:01] **Tim:** And they're legally obligated to

[00:48:04] **Tim:** to do it for you. It's a little more, it's gonna cost you some money, right? It's not gonna be free. They might, I don't know. I, I don't know how you arrange payment for that. Maybe you pay it per year, but, but anyway, you can use a legal service to do that. It probably has to be a local legal service, and they'll make arrangements to, you know, if you don't check in after a year or whatever, I don't, I don't know how that works, but if you don't have a trusted person in your life, which is a sad thing, I'm sorry for you, but you, you still can do these kind of things and you know, there's probably points into everyone's life where they're like, I don't really know if I want my spouse to have all my information about all my stuff that, that I have.

[00:48:44] **Tim:** So, you know, there's, there's, there is alternatives,

[00:48:47] **Shawn Oden:**

[00:48:47] **Tim:** like it is with planting a tree. Best time to write your will and take care of. This was 10 years ago. The next best time is today. So.

[00:48:56] **Shawn Oden:** That's yes. And you can get on Google pretty much, and every, every state's different. But yeah, get on Google and find an estate lawyer or somebody like that, they'll be able to help.

[00:49:06] **Shawn Oden:** I'm, I'm actually not sure how much they are, but I don't think they're ridiculous. They, they do cost, but I don't think they're, they're ridiculously

[00:49:13] **Adam:** I mean, it's been like 20 years since we did ours initially, and if I'm not mistaken, we just went to like our state's website and they had like a template that you could download and fill out, and it gives you at least the basics and then you

[00:49:23] **Shawn Oden:** Oh, yeah, yeah. You can absolutely do those.I think quick and Will, has, has decent documents that, that you, again, are easy to fill out online. And that, that's just for the will part. I don't, I don't know how deep that gets into how much stuff you've, what to do with your stuff and, and I mean, I guess the, the more stuff you have, the more, much more complicated it can get.

[00:49:45] **Tim:** Great. Through our company. We have, every year we do enrollment. We just did our open enrollment recently and it, they have a legal package. Right. So it's a, it's legal package where you get certain things you can do. I never sign up for it 'cause I use, I use LegalZoom, so,but yeah, it might be available as a per

[00:50:05] **Shawn Oden:** I think most of them do. If you do the, the company legal plans, most of 'em do have estate planning and

[00:50:10] **Shawn Oden:** stuff like that.

[00:50:11] **Tim:** Yeah, they do. A hundred percent. Yeah.

[00:50:13] **Adam:** Well, Sean, before we, wrap up the show, you know, we really appreciate you being gracious with your time and, and come and spend time with us and share your knowledge. Is there anything that you wanna like plug while you're here or,

[00:50:23] **Shawn Oden:** I, I probably left out a ton of information. feel free to watch that, presentation 'cause I hit a lot of links and stuff in there that, of stuff that I've found back then that still is pretty much relevant today. So.

[00:50:35] **Adam:** yeah, we'll, we'll definitely include that in the show notes too.

[00:50:37] **Ben:** Yeah. Stay, uh, tuned to the after show if you have a secret second family that nobody knows about.

[00:50:45] **Shawn Oden:** Didn't even get into that.

[00:50:46] **Adam:** yeah, we're gonna cover that later.

[00:50:50] **Shawn Oden:** I did speak about family surprise earlier.

[00:50:54] **Adam:** about second family surprises?

[00:50:56] **Shawn Oden:** Yeah, I did.

[00:50:58] **Tim:** We've had first family. What about Second Family?

## [00:51:02] Patreon

[00:51:02] **Adam:** Alright, well then this episode of Working Code is brought to you by teaching your mom to use 1Password for the 11th time. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:51:14] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:51:22] Thanks For Listening!

[00:51:22] **Adam:** We're gonna go record the after show, which as I say, every week, is basically just more of the same. After we, after the outro music plays, we're going to pick Sean's brain.

[00:51:31] **Adam:** I'm gonna ask him, which of the books that I've recommended, are his favorites. And we're gonna see where the conversation goes from there.

[00:51:37] **Tim:** Well, it's more the same, but, but we take the ties off.

[00:51:39] **Tim:** It's a lot. It's a lot looser. Yeah.

[00:51:41] **Adam:** It's,working Code after dark.

[00:51:43] **Tim:** There you go. Like it.

[00:51:46] **Adam:** so if you want, yeah. that's why it's a video podcast, but not only for us. if you would like to help us out, you can go to patreon.com/workingcodepod or a few dollars our way.

[00:51:55] **Adam:** We would greatly appreciate it. Also take this opportunity to invite you to join our Discord. You can go to workingcode.dev/discord. It's like Slack, but fun. you know, instead of talking about pull requests with your coworkers, you're talking about, I dunno, books and, and Wordle and, and links of the day and, and whatever's going on in the world with your community members who also like the podcast.

[00:52:17] **Adam:** So we'd love to have you, it's totally free, open to the public workingcode.dev/discord. That's gonna do it for us this week. We'll catch you next week and until then,

[00:52:25] **Tim:** Listeners, gotta be honest with you, our love for you will never die. So we're not writing any documents. No way. 'cause your heart matters.

[00:52:34] **Adam:** ​
