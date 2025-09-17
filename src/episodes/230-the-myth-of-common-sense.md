---
title: "230: The Myth of Common Sense"
description: "Common sense isn't so common, or maybe it's a myth entirely? On this week's episode, Adam, Ben, and Carol discuss common sense in programming."
date: 2025-09-12
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/230-the-myth-of-common-sense/id1544142288?i=1000726514960"></iframe>

Common sense isn't so common, or maybe it's a myth entirely? On this week's episode, Adam, Ben, and Carol discuss common sense in programming.

What may be common sense to a programmer may not be so simple to a user, and it's important, in these contexts, to deploy empathy and understanding rather than frustration. The hosts discuss this and more.

A Hermeneutic of Generosity
https://www.youtube.com/watch?v=ovrzKCQ2JTM

Ten Thousand
https://xkcd.com/1053/

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/230-the-myth-of-common-sense.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** I got a ticket today from somebody who used a tech word, probably because, you know, they'd heard it once or twice and thought it applied in this situation and had nothing to do with what they were talking about, right? So they were asking about like a, was there warehouse sync process working, right?

[00:00:13] **Adam:** But what they asked was, is the web hook working? And I'm like, you are not asking about web hooks,

[00:00:21] **Carol:** Huh?

[00:00:22] **Ben:** Is your refrigerator running?

[00:00:23] **Adam:** right?

## [00:00:24] Intro

[00:00:44] **Adam:** Okay, here we go. It is show number 230. And on today's show we're gonna talk about the myth of common sense. apparently we're gonna bust that myth. but first as usual, we'll start with our triumphs and fails. Tim could not be with us tonight. He's got the Rona. apparently he brought, a goody bag home from Dragon Con and it was not a goody bag he wanted.

[00:01:02] **Adam:** he's out again this week. Hopefully he'll be back next week. Feel better. Tim, he is not gonna hear this anyway.

## [00:01:07] Ben's Triumph: Design System Journey

[00:01:07] **Adam:** He doesn't listen to the podcast, but so Ben, I'm gonna come to you first. What do you got going on, my friend?

[00:01:13] **Ben:** I'm gonna go with a triumph this week. Which of that, I think really for the first time I've been using chat GPT in a way that it feel useful. I've used Chat GPT on and off for things, and I've, I've just been very angry at it most of the time, and I am constantly having this sense that I'm, just not holding it wrong, so to speak, and I'm not seeing a lot of the magic that other people see. but I have been using it lately to help me build a design system set of tokens.meaning these are the CSS custom properties like border width and primary color and spacing and,

[00:01:54] **Adam:** Right,

[00:01:55] **Ben:** the, the things that define the kind of look and feel and vibe

[00:01:59] **Adam:** right. But it's not, you're not using it to come up with the values. You're kind of using it to come up with like the, the list of things you need to do and the names for them.

[00:02:06] **Ben:** Yeah, so because I've looked at other design system token sets, like if you look at, bootstrap, which is what we use at work, they have hundreds of, of CSS custom properties. And then if you look at something like Adam Argyle, CSS Open Props project, which is his kind of, what he, I think he calls it like the subatomic design system, where instead of

[00:02:31] **Adam:** Yeah.

[00:02:32] **Ben:** level, it is the properties that go into the atomic level, which is basically his design system, his design system tokens. and I wanted to try to apply something like that, but it was just too large in scope for me to understand how it's even supposed to be used. There's just so many options and there's no philosophy around how any of it's actually supposed to be applied. It's more just, here's this giant toolbox of things you can use, have at it.

[00:02:57] **Adam:** Mm-hmm.

[00:02:58] **Ben:** So I went into chat GPT and I said, look, I wanna design a simple design system for my app. It's only gonna be used by this app, so it doesn't have to have a lot of the generic flexibility that maybe other design systems have to have. I don't know how to do this. I don't understand how to design systems work. I want to iteratively walk through building up this set of tokens, starting with a single token, and then incrementally adding one token at a time. And it, and it said, oh, you know, obviously this is such a great idea. What a fantastic way to think about it. You know, a typical Chat GPT, it it like, oh, the very first thing that we usually do is set up the spacing token, which kind of sets the, the distance between block level elements like this just sets the overall feeling for the application and the airiness and the amount of white space over.

[00:03:47] **Ben:** I mean I've probably been doing this for the last two weeks-ish. I keep hitting some limits now with chat GPT, but that's another issue. And I've been having it walk through like, okay, well how do I think about this? How do I use it? Well, what about these exceptions? And then we'll get to it. And I say, okay, in my, my spacing token, what's next?

[00:04:05] **Ben:** And they're like, well, that's block spacing. We should think about inline spacing, which is the, the horizontal spacing. And then we do that, and then it's font sizes and line heights and we walk through. And now I have a design system set of tokens, probably like 60 or 70 tokens. and I just feel way more confident in that I understand they work. I understand some of the philosophy and how they're actually being applied and, and how things are being used to keep them consistent and like the padding around buttons and inputs and it, things like that. And, and like when things are helpful to be semantic versus just abstract, like, bootstrap has concepts of primary and secondary buttons, that's very. General, like what does that mean? Like what am I supposed to do with that information? So I was talking to Chat GPT and I said, well, I always have forms, and the forms pretty much always have a submit button and a cancel button. Can I just call those submit and cancel? Like, why would I call them primary and secondary or something to that effect or tertiary? And, I dunno, like we just, it was just, was really helpful to go back and forth and ask it why I should be thinking about some ways, is it wrong to think about other ways? And again, just like for the first time, I really felt like I was actually extracting some meaningful value from chat GPT. So that was a huge win for me.

[00:05:30] **Adam:** Congrats. When can we expect to see your GitHub repo, with your, your design system that you're gonna compete with? Bootstrap.

[00:05:38] **Ben:** I will not be competing with any of that, but, but I, all of this stuff will be online eventually, so, but yeah.

[00:05:46] **Adam:** Is there like a CSS rule that you can apply that forces people to use like way more line breaks than necessary?

[00:05:52] **Carol:** I was just thinking that

[00:05:53] **Adam:** Mm-hmm.

[00:05:54] **Carol:** special for Ben. Yeah.

[00:05:56] **Ben:** Well, I, it, it's, I'll, I'll tell you one of the things that I still struggle with, even with going back and forth with chat GPT is just management of margins in general. And it's just a very challenging thing. And that even the, even Chat GPT goes back and forth on where those things should be done and the pros and cons of like, components shouldn't know about their own margins.

[00:06:20] **Ben:** The containers should know about the margins. And I'm like, well, what if I just want have like pros, you know, like I don't want have to have a special class on every H one and every P tag that I might just have embedded in my. You know, if I have a, a form page and it has a H one and a little paragraph that describes what the form's supposed to do, I'm like, I'm necessarily wanna have special classes for that.

[00:06:40] **Ben:** I mean, I might eventually for certain things, but not generally. And it's like, oh, well then, you know, you can put that stuff in the, in the, basically like a CSS reset where some things have bottom margins and some things don't. And then you can do overrides and I dunno, it's, it's still just very messy it seems like, in terms of margin management, but,

[00:06:58] **Adam:** It's, it's an interesting space. I, I'm no CSS guru, I'm no professional designer, but over the last couple of years, I've kind of find, found myself falling into the well of, it seems like the right solution is to define a, like a wrapper utility, right? So you don't want to have to put a class on every heading, every paragraph tag or whatever, like you were saying.

[00:07:20] **Adam:** But, so like, one of the things I'll do is I have like a column component. Like I'm gonna put stuff inside of this and I want it organized in a vertical column. And it's, that column component is, I use Tailwind, so it's, I I make it flex box. It's flex and then a gap, right? So I, I get flex box, display, flex box, or whatever that is, and then give it the, the flex gap.

[00:07:41] **Adam:** And that handles, making it a column with a consistent gap, which is kind of nice.

[00:07:46] **Ben:** Yeah, and it's funny, so I mentioned the CSS Open Props project and in that Adam Argyle has a CSS reset example, in his reset he has some sort of a column type thing, or he might just like generically put it on sections, I can't remember offhand. it did the same thing and I was like, oh my God, this is the most amazing thing I've ever seen. I can't believe I had never thought of this. I can't believe I hadn't seen it before. And I started to try and use it. And I think it does work really well in a lot of cases. But then I got to, you know, it's like I have my paragraph, paragraph, paragraph, and then all of a sudden I had a bulleted list

[00:08:21] **Adam:** Mm-hmm.

[00:08:22] **Ben:** oh crap. lists can have paragraphs inside them. And I'm like, well, I can't, do a display flex on a list item. it semantically, I think, changes the meaning of what that list item actually is.

[00:08:37] **Adam:** Okay.

[00:08:37] **Ben:** then, and, and I think also if you do display, flex on a list item, I think in certain browsers it'll actually remove the bullet. I was like, oh, okay. I don't know what to do. Like, 'cause now I feel like I'm just back to my old, like I could, okay, inside of my list item, I could then have a div

[00:08:53] **Adam:** Mm-hmm.

[00:08:53] **Ben:** of colony class

[00:08:55] **Adam:** Yeah.

[00:08:55] **Ben:** then start doing the same thing. But then I'm like, what if I'm grabbing this out of a database and it's, you know, something that I is like user generated content.

[00:09:03] **Ben:** It's like it kept coming back to the thing. Like, I'm ultimately gonna eventually have content that I don't have control over.

[00:09:09] **Adam:** Mm-hmm.

[00:09:10] **Ben:** And so I, as much as possible, I want to have some core. Not reset. Iss not the right word, but it's like some core, this is just generally how I want stuff to look and feel.

[00:09:22] **Adam:** Yeah,

[00:09:22] **Ben:** have to put classs and everything.

[00:09:23] **Ben:** It, it, it, it's, it's murky. I'm not saying I'm confident about it. I'm saying it's a, it's a hard problem.

[00:09:28] **Adam:** it is for sure.

[00:09:30] **Ben:** Anyway, that's my triumph. Let's kick it over. Carol.

## [00:09:33] Carol's Triumphs: Security Concerns

[00:09:33] **Ben:** Carol, what do you got going on?

[00:09:35] **Carol:** Can I go with two wins? Like, is

[00:09:36] **Adam:** Absolutely. You, you were out for a little while. You got, you got some in the bank, right?

[00:09:41] **Carol:** Perfect. Yeah. So last week I mentioned that I went through and was just like hella, I don't care if depend, the bot said it's there. I said, let's go with it. That didn't break. Everything seems to be okay.

[00:09:54] **Ben:** Yeah.

[00:09:54] **Adam:** Wow.

[00:09:55] **Ben:** like 40 updates or something? Crazy.

[00:09:58] **Carol:** 38. I put 38 out and tested enough right to know that it's not gonna be terrible. And they were all minor updates.

[00:10:05] **Carol:** I didn't update anything that was major. I do my full research on the major and if there's any breaking changes, like I'm not gonna apply that, I'm gonna make the fixes. They were all minor, but it all works. So just letting you know, a triumph on the triumph is like, Hey, worked. So

[00:10:21] **Ben:** Heck yeah. Although, hold on. Sorry. Before we move away from this triumph, I have seen I think two separate, separate hacks. that they both involved NPM where someone had snuck sort of, malicious code that was actually trying to execute Claude AI and cursor command line tools as like part of the post install script.Uh, Are you saying you've seen these within the last week or no?

[00:10:51] **Carol:** I

[00:10:51] **Adam:** That's not on my radar,

[00:10:52] **Carol:** Yeah.

[00:10:53] **Ben:** Oh, I'll, I'll put in the, in the, in the, discord later. But yeah, apparently, some like really, really major packages were, were taken over.

[00:11:02] **Adam:** you know what I'm talking about. Okay. So that, that wasn't trying to use ai.

[00:11:07] **Ben:** I think so, I think they're two different big

[00:11:10] **Adam:** The, the, so I, I wrote some stuff down about that one. So the, the guy who was, hacked, he wasn't really hacked, right? His, his, the, he was Spearfished. Yeah. Josh Junan, or he goes by Qix or Kicks Q-U-Q-I-X. but, so yeah, he's a maintainer of a bunch of really popular packages with like billions of downloads a week, aggregated, including chalk and debug and like a bunch of other CLI based tools.

[00:11:37] **Adam:** But, so it was a spearfishing thing. I've seen some analysis on it. Basically, it seems like it was spearfishing, but it wasn't targeted spearfishing, it was just kind of like blanket who has a lot of, repositories on GitHub that we, or, or packages on NPM that we could potentially sneak some malicious code into.

[00:11:55] **Adam:** They managed to get this guy, and the, so like, of the list of packages that he manages that were, that were affected, there was like, I don't know, 19 or something like that. One was a front end package. All the rest were at least, you know, typically backend packages, not something, you know, you don't see a whole lot of command line packages used for front end code.

[00:12:16] **Adam:** Right.and the, the malicious code that was snuck in was to, execute code in people's browsers. So that's how, you know, it was not necessarily targeted, it's just they kind of got a little bit lucky here. whereas execute people's code or execute code in people's browsers so that if they're on a cryptocurrency exchange.

[00:12:36] **Adam:** And they are. okay, I'm outta my depth now. I'm doing my best to recall the details, so don't, you know, not, not a respectable source of truth here. I, I'm, I'm doing my best. but basically if you're on a cryptocurrency exchange and there's like a certain level of security, they're not used like they're doing plain text tokens or something like that.

[00:12:56] **Adam:** I don't, that's where I lose my depth. But, basically they had a whole bunch of like wallet IDs, that were very different in the, in this malicious code. And if you were trying to send money, it would pick one that was like, as close as it could be. Like levinstein distance, I think is the algorithm where it like, looks similar enough to the one that you did.

[00:13:16] **Adam:** So if you're not paying close attention, you wouldn't notice that it swapped in a different wallet. And so you'd sent money to the, to the wrong wallet. Now, from the, the, the reports that I read, a total of like 20 cents was stolen. And it was patched within like eight hours. But yeah, so go ahead.

[00:13:33] **Ben:** that there was another hack, the, i, I skimmed the article for where the post install, the post install script was shelling out to the command line tools for Claude and Gemini and OpenAI it was like scour the home directory and recurs through it and look for tokens that match certain patterns.

[00:13:55] **Ben:** Like there was a, an, and I think that was also in some NPM packages

[00:13:59] **Adam:** Now that you mention it. Yeah, I do kind of vaguely remember that. That must have been like right after we recorded last week. 'cause it seemed so long ago.

[00:14:07] **Ben:** so many days. But this is, I mean, just going back to the idea that the bad guys only have to be right once. And

[00:14:14] **Adam:** Yeah.

[00:14:15] **Ben:** be right every time.

[00:14:16] **Carol:** Yeah.

[00:14:16] **Ben:** not to, to go from saying, I use GPT well to now hating on it for a second, but this idea that we have generated code and people are reviewing the code and like all you have to do is miss one thing that didn't seem important at the time and then opens up a SQL injection attack.

[00:14:36] **Ben:** Like that's, that's scary. And not to say that people don't make mistakes normally, but when you're in the world of copy pasting code and you know that the code you're copying from is battle tested, then the code you're pasting into is also basically battle tested. You know, I, I'm, I'm saying I'm not, I'm saying like, people make different errors anyway, sorry.

[00:14:57] **Ben:** So Carol, you had a second Triumph.

[00:15:00] **Carol:** I do, I do. I have a second one. but just to go back one second. So I was listening to a podcast this week too, where they were talking about how, the whole, the database of cyber like security vulnerabilities, right? Like

[00:15:11] **Adam:** Mm-hmm.

[00:15:12] **Carol:** don't become like critical early because it takes engineers so long to actually use the vulnerability that they found. However, they've now found that using AI you're able to now exploit those vulnerabilities a lot faster, making the need to recover and patch a lot more critical and happen a lot sooner. And they're expecting like more zero day vulnerability things than we've seen in the past several years. So it's gonna be interesting to see like how

[00:15:43] **Ben:** Oh man.

[00:15:44] **Carol:** out.

[00:15:44] **Carol:** Yeah. 'cause now you don't need 90 to, you know, a hundred days to write a vulnerability exploit. Like you're able to do that. You know, I think they said like 30 minutes I have something that can exploit exactly what the vulnerabilities is finding. So I was like, oh, just another thing I have to fight.

[00:16:01] **Ben:** We just all have to go back to an air world where we just can't trust anything.

[00:16:07] **Carol:** I'm not against it. Yeah.

[00:16:09] **Ben:** So what's your second?

[00:16:10] **Carol:** second, triumph is, I know I've mentioned this a few times, but at work we've lost a lot of people. You know, like a lot of federal people have been let go or decided to leave. a lot of knowledge has gone. well over this past weekend we did a big migration and moved from, VMware to HyperV.

[00:16:28] **Carol:** So we did like a big cutover from where our infrastructure was. And so where it sits now. So those come with things you don't expect. Like all of a sudden these settings just didn't cross over. It's stuff you can't really anticipate 'cause it didn't happen in any other environment. During all of this, like we've ran into some production issues like nothing big, everything has been, has been like super successful.

[00:16:50] **Carol:** Like it's just weird. Like, hey, all of a sudden firewall is blocking this connection to this external vendor that it wasn't blocking on Friday and now it is. But since we've lost the people and the, the knowledge around that, I've had to step in and go learn like how to read firewall logs and how to dig through all of these Azure logs so that the minute they're free, I've given them like as much information as I could to point to this is what you need to go change and configuration.we do the like least trust, I think that's what it's called, like

[00:17:26] **Adam:** The principle of least trust. Yeah.

[00:17:27] **Carol:** principal least Trust. So, well I can change all the code I want. I can't go change anything in the database outside of Dev.

[00:17:33] **Adam:** Mm-hmm.

[00:17:34] **Carol:** Outside of my local in dev, I can't change a thing. I can't even look at server logs. Like there are lots of restrictions on what we're able to see, so my hands get tied and that's fine, but it's just kind of put me in a spot where I've had to go learn a lot and piece together information with what I do have access to. So when our DBA gets done fixing the one problem, I've at least like compiled everything I could find, put it in a handy dandy DevOps story and said, here's what you need to fix based off what I'm finding. So I feel like I've done really well this week on learning things that are outside of my area and outside anything I thought I would need to learn anytime soon.

[00:18:13] **Carol:** So I'm gonna call that a big win. The big being helpful to people and to my team and enabling work to keep moving. Like that's solid. I'll take it.

[00:18:22] **Ben:** the idea of learning has been so top of mind for me, especially not to bring it back to ai, but you know, everybody's talking about ai. So a lot of the conversations revolve around AI and its impact on society at large. And listening to an episode of, hard Fork over the weekend they were talking about how AI is affecting the world of education. it's just so fascinating to hear people talk about some of this stuff and certain things, it's like they're just giving up on like they were, one of the examples they had was that people just don't read anymore and they're not interested in reading long form content. And one of the teachers who was being interviewed was just like, well, we're like, that's just not a thing anymore. I always come back to the idea of, but you're in school, like it's not up to you. What is a thing anymore? Like it's what your teacher says is a thing. Like if a teacher assigns a book and it's up to you to read that book, like AI shouldn't impact that. That's crazy to me. I'm, I'm just blown away at all of these concessions that people feel like they have to make because they feel like they're, things are out of control.

[00:19:36] **Ben:** And I just, I don't understand that. And I've actually started to read a book and I'm not a huge reader and I'm like, I have to read a book just to prove to myself that I can actually do it like that I can sit down and I can focus and get through a book.

[00:19:49] **Carol:** get through it. Yeah.

[00:19:50] **Ben:** Yeah. 'cause it seems I don't want to not be in control anymore of my ability to do things.

[00:19:56] **Adam:** Would you like a recommendation for a nice short book that's somewhat technical to get through?

[00:20:00] **Ben:** Yes.

[00:20:01] **Adam:** Mine.

[00:20:04] **Ben:** Should I rest assured this, uh, recommendation will be good.

[00:20:07] **Adam:** You should.

[00:20:08] **Carol:** Yeah. It's interesting you say that about the like not being able to get through long articles or even like reading a book for school. I feel like students now like do have the opportunity to just kind of breeze by if they choose to do so. Mm-hmm. In a few years, the world's gonna kick 'em in the butt, right?

[00:20:28] **Carol:** Because if you didn't take the opportunity to learn or you're not willing to learn, you're not gonna have, or to engineering anyways for like your science stuff. You're not gonna have any value to a company and they're gonna quickly see that. And you're gonna wish you probably would have them taking the time to learn.

[00:20:45] **Ben:** It is just so crazy. The world is just changing so fast.

[00:20:50] **Carol:** Well, that's my double wins. what about you, Adam?

[00:20:54] **Adam:** I'

## [00:20:54] Adam's Failiumph: Management Aspirations and Challenges

[00:20:59] **Adam:** m gonna go, I. I don't really wanna call this a fail, so I'm gonna call it affiliate. so the, you know, I've been working in this industry for like, well, more than half of my life now. and I've been kind of getting the itch to, to move more toward management, for a couple of different reasons.

[00:21:12] **Adam:** But, you know, it's, it's, it's just on my mind a lot. you know, I got a taste of it when we hired that, co-op last year or the year before. I don't, time is a, is a weird thing, but, maybe, I don't know. Yeah, probably. But, either way, I've gotten a little bit of a bigger taste more recently now we're hiring.

[00:21:31] **Adam:** and the, so the, the process for hiring the co-op was interesting because it's not an unlimited candidate pool, right? They only have so many people enrolled in the program at the college that we were doing this with. and. So there was, you know, we got a lot of applications, but it was, you know, it was like a hundred and something applications, which is a lot, but it's still a finite number.

[00:21:52] **Adam:** for this position that we're hiring for, we had posted the job on ZipRecruiter, and it was like I couldn't keep up, right? I was getting applications in faster than I could read the resumes and make a decision on whether or not I even wanted to like, do a phone screen with this person. And, and, okay, so I did the phone screens and from there made decisions on who we were gonna interview.

[00:22:11] **Adam:** We did interviews, and overall that went pretty good. You know, we've, we've narrowed it down to a couple of candidates and we're still, you know, in the process here. I, I can't, I won't say anything, especially, because, we have a listener in the, in the running. but, yeah, just like, I guess it was it, two weeks ago, Tim said he hired somebody from, he didn't hire somebody from our podcast Discord, but a, a listener, was, was his newest hire anyway.

[00:22:33] **Adam:** So long and short of it is that, you know, I've been doing a lot of work. that's not my typical individual contributor, hi, you know, writing code type work or leading the dev team type work. It's more touchy feely, like, get to know a person, should we interview them, that sort of thing. And I, I, I, I don't know, part of me wants to believe that this is like, maybe the softest, squishiest, like weirdest, hardest thing about management.

[00:23:00] **Adam:** I don't know. I bet you firing people is even harder. But,

[00:23:03] **Carol:** well fight.

[00:23:03] **Adam:** if, if hiring is like the second hardest behind firing than maybe it's not that bad, but this, the sense I'm getting so far is like, hmm, maybe I don't want to go into management because this is, it's so, it, it's like, it's not demoralizing, but it just kind of puts a different spin on my day.

[00:23:19] **Adam:** It makes me feel less productive, I think.

[00:23:22] **Carol:** Yeah, I, I agree. Like when I have to deal with people or when I used to be a supervisor right? And I had to deal with people. There were so many times I just wanted to go back inside my turtle shell and write code,

[00:23:33] **Adam:** Yeah.

[00:23:34] **Carol:** Code, like made my heart happy and being able to solve a problem just felt nice.

[00:23:39] **Carol:** Instead, I had to fix everyone else's problems, and I didn't like that so much. Mm.

[00:23:45] **Ben:** I, I totally agree. This is why I've heard time and time again that you, you sort of can't live in both worlds because you always feel like you can retreat to the thing that makes you more happy.

[00:23:56] **Adam:** Mm-hmm.

[00:23:57] **Ben:** It's so hard. I don't envy that situation at all.

[00:24:01] **Adam:** Yeah. I mean, it'll be, it'll be interesting to see what happens over the next couple years. I think we are definitely in a position where we're gonna be growing a little bit more rapidly than we have in the past. Right. So we, we have, when I first started, right, we had a bunch of customers for this one product, and we, a few years later invented another product and now.

[00:24:20] **Adam:** Those are our two mainstays of income. And so my product that I invented, or you know, whatever, Steve and I kind of built it together. But, my product that I kind of manage is, we have, we're, for the longest time, it was like three customers, five customers, seven customers that, that were, you know, these are all universities.

[00:24:36] **Adam:** So it's not just like one little thing. But, and now we're up to 20 and, and we still only have a team of like three people supporting this product, which is cool, but it's like, okay, we are starting to hit like real growing pains, right? Like tickets, all of our tickets. It's built into the, the product, like the, you know, if they wanna do a support ticket, it's not like they go out to a separate website to do, it's built.

[00:24:58] **Adam:** Which is a pretty good user experience for them doing the support. But then for us managing that, right now we have 20 different sites that we have to kind of stay on top of. So we have a dashboard where we aggregate all that data via API so we can keep, keep track of it all, but it's still a little bit onerous.

[00:25:14] **Adam:** And then in addition, every comment, every, you know, like ticket closing or priority change or, you know, when they attach a spreadsheet that contains a screenshot that they want us to see or whatever, you know, all of those events funnel into one of our team chat rooms, right? So like a Slack room or a discord room or whatever.

[00:25:33] **Adam:** and that just, that one channel is so noisy and it's, I find it a little overwhelming and distracting. So I kind of have learned to tune it out, which is a bad thing because then I'm not paying attention to the tickets. So it's just, we're definitely experiencing growing pains. We're hiring because we want to continue to be able to scale like our product is well-liked.

[00:25:54] **Adam:** and we've done like basically zero marketing for it. And, and we have a really solid lead pipeline, which is great. So we're growing the team to be able to support that. And I just see even more growth in our future. And so I feel like there's a possibility, a real possibility that I'm gonna get more into management, less into coding, which I want to believe is gonna be a good, fruitful path for me.

[00:26:16] **Adam:** but I'm just not convinced yet.

[00:26:18] **Ben:** So you're just gonna have to take more and more time out of your, PCI and Soc two compliance time to, start doing managerial stuff.

[00:26:26] **Adam:** well, no. So you know how they say like, other duties as assigned.

[00:26:30] **Carol:** Yeah.

[00:26:31] **Adam:** That's, that's my other duties as assigned. And, for lack of a better place to put it, I think that does kind of qualify as like. That's the, that's the easy filler work for management stuff, right? Like when you're not running between meetings and you have that half hour of empty space in your schedule, it's like, oh yeah, I can run that pen test thing, or I can go work on this PCI document for 20 minutes.

[00:26:52] **Adam:** That's something that's easy to pick up and put down, versus like a coding task where you've got like so much context that you unpack into your head and then it's like, oh, time for my next meeting. Oh, well,

[00:27:04] **Carol:** Hope you wrote it down.

[00:27:06] **Adam:** yeah. So it's a little bit of, little bit of triumph, a little bit of fail. I'm just, I don't know how I feel about it yet. So it's right there in the middle.

[00:27:13] **Carol:** So, I wanna add one thing please. Super

[00:27:16] **Adam:** please. Mm-hmm.

[00:27:17] **Carol:** really a secret, right?

[00:27:18] **Ben:** Hmm.

[00:27:18] **Carol:** podcast can know, but don't tell my boss. We have a new supervisor and he sent out an email the day, or it may have been late yesterday. I'm like working 12 hours behind because so many people need things. Let's be real. So at some point he sent out an email and he was trying to get an understanding of how we handle our help desk rotation, which I looked at the email saw. He's looking for a schedule and a list of people to be on help desk. And I just hit archive on the

[00:27:46] **Adam:** Oh, no.

[00:27:48] **Carol:** and said, not my problem. Don't put me in the rotation, I hope, and we'll see what happens.

[00:27:53] **Adam:** Mm-hmm.

[00:27:54] **Carol:** is not fun.

[00:27:55] **Adam:** Yeah. I think that we, maybe in another year we'll be at the point where we'll have to have somebody that's like dedicated to support. Right now, it's just like we, that's part of the reason that we have it all come into that chat room so that we're, it, it makes noise on all of our computers and we go, you know, somebody, whoever's not.

[00:28:14] **Adam:** Deep into something can, can take a 20 minutes or whatever to look at the ticket and try to deal with it. And we'll pass it off if we have to. But, yeah, it's, it's a whole thing.

[00:28:24] **Carol:** I think you need to change notification settings on that channel to only be if they at you.

[00:28:29] **Adam:** yeah, I don't know that that would happen with the tickets. So one thing that we do have, which is kind of nice, since it is homegrown and we can do whatever integrations we want, we have it set so that, like on the ticket there's a priority, right? You're creating a support ticket. and you can say, okay, this is

[00:28:43] **Carol:** Critical

[00:28:43] **Adam:** they, it it's numbers, right?

[00:28:45] **Adam:** It's, it's one through 11, of course. and,

[00:28:48] **Carol:** makes sense, right.

[00:28:49] **Adam:** it, this one goes up to 11. Yeah. and, the, the, they have text labels on most of them too, which like one is before the heat death of the universe. I forget what 11 is. But you know, like, you know, it kind of give them an idea of like, how are we thinking about these numbers?

[00:29:03] **Adam:** and. I think if it's a 10 or an 11, it might be nine, 10, or 11, either way. but if it's, if it's one of those top priorities, every event in that ticket sends a notification to our on-call developer 24 hours a day, seven days a week. So the, like, when they select it, the, the, you know, it's a dropdown or whatever you select, okay, yeah.

[00:29:23] **Adam:** This is a priority 11. You choose 11 and before you even submit the ticket, you just get this big red warning, like this is going to send a notification immediately to the on-call developer. This is a big deal. Are you absolutely certain you want to do that right now? You know, this is like for issues that deal with the board of trustees at the university or a big financial problem, right?

[00:29:44] **Adam:** This is not so and so wants their, their name changed or whatever, right? This is not something that needs to wake somebody up at 2:00 AM

[00:29:51] **Ben:** it hasn't arrived yet.

[00:29:53] **Adam:** Yeah. So, that's, yeah. That, like, that's one of the things that I think that our customers. Really appreciate about us is that we do try to be super responsive and we, like, we, you know, we say we show up for them, and that's both, metaphorically and, factually or, or non metaphorically.

[00:30:11] **Adam:** you know, like when they have events, sometimes we just show up and, and help out or whatever. and, but you know, we try to, try to just be super responsive and, and do what's best for them, you know? So anyway, that's my failure. Let's move on from that, since we're 30 minutes into Yeah, go ahead.

[00:30:29] **Carol:** So one more thing.

## [00:30:29] The Myth of Common Sense

[00:30:29] **Carol:** So we're talking about common sense, right? Like that's gonna be like

[00:30:33] **Adam:** That was the idea. Yeah.

[00:30:34] **Carol:** where we're going. What in your mind, made you think to make nine, 10, and 11? The most high priority thing, like number one is the problem. Like number

[00:30:44] **Adam:** Hmm.

[00:30:46] **Carol:** critical thing.

[00:30:46] **Carol:** Like, that's like

[00:30:48] **Adam:** I was thinking about it like a,

[00:30:49] **Carol:** a problem.

[00:30:50] **Ben:** can

[00:30:50] **Adam:** yeah,

[00:30:51] **Ben:** Defcon is higher.

[00:30:52] **Adam:** right.

[00:30:53] **Carol:** is the worst, right? Like critical one, do it now. 11. I'm like, I'll see you next year.

[00:30:59] **Adam:** I hear you. I mean, that's why we put the text labels on it too, right? So that it's, it's clear what we're thinking about. to answer your question, it, I could see it going either way. I wanted to make the, crap, why can't I think of it? The, it's not twisted Sister. the joke, the 11, this one goes up to 11.

[00:31:17] **Adam:** spinal Tap. Thank you. Yes. I wanted to make the Spinal Tap reference and so I wanted it to go to 11 instead of 10. And so that's why 11. 'cause this one goes to 11.

[00:31:27] **Ben:** I love it.

[00:31:28] **Adam:** So

[00:31:28] **Ben:** So, common sense.

[00:31:31] **Adam:** what's that about?

[00:31:31] **Ben:** this has been on my mind a lot lately and increasingly so. I see a lot of stuff that happens in the world that, that just befuddles me.I struggle to explain why people do the things that they do, and I'm sure I've ranted about a lot of this stuff, and I'm sure I've gotten, raked over the coals for, for certain things.

[00:31:53] **Ben:** Like I, I just have a lot of strong feelings that seem obvious to me. Like, you should never call someone after 10:00 PM Like, to me, that's just common sense. Or like, you probably should stop eating your nacho chips once the movie has started. Like no one wants to hear you crunching on your chips. That, to me feels like common sense. If you're walking down the sidewalk and you get something on your phone, you don't just stop because there's probably people walking behind you. That's, that's just common sense to me. If you park in a parking space and you get out and you see that you're over the line, you should just get back in the car and fix your car alignment.

[00:32:31] **Ben:** Like that's just common sense to me. And,

[00:32:33] **Adam:** I think you're mistaken. Common sense for common courtesy.

[00:32:36] **Ben:** so, okay, so. These are just all the things that are going through my head all the time as I'm trying to make my way in the world. And right now, it's coming up on election season. I think it's not midterms yet. November I think is like local elections. I don't know, but I've seen a lot of political signs popping up in my little village area and the one that has gotten me thinking about this, especially after last week's episode, we talked about how subjective so many things and programming are.

[00:33:04] **Ben:** And I think this dovetails quite heavily with that.the Republican party, and this is, this is not gonna be a political conversation, this is just a, a point of interest. The Republican party has put out signs, let's say something to the effect of vote Republican common sense. And I don't connect with that in any way whatsoever.

[00:33:26] **Ben:** And I don't mean the Republican part. I mean this idea that. A political party is based on common sense or just more broadly the idea that any specialization has common sense baked into it.political leaders spend their whole lives mastering politics and interpersonal relationships. Doctors go to school for years to master, you know, medicine. goes through these specialization phases. The idea that we would want to be able to relate to our leadership bonkers to me. It'd be like going into your doctor and being like, I love my doctor. I can really relate to him. 'cause like me, he also did not go to medical school. be like, that's really problematic.

[00:34:14] **Ben:** You should not, you should immediately stop going to that doctor.if I could share a, a, a vulnerable story for a second. So I was in college when, September 11th happened, which is actually.

[00:34:26] **Carol:** today.

[00:34:27] **Ben:** coincidentally is, is the, is the today anniversary. And I think prior to that I had never really thought of Middle Eastern people as problematic. all of my action movies before that, all of the bad guys were mobsters really.

[00:34:45] **Adam:** Hmm.

[00:34:46] **Ben:** and I remember getting on a plane sometime after nine 11 and seeing a Middle Eastern person line, and it made me a little nervous. And, and, and that's disgusting. And I am embarrassed to say that, but like it's human nature.

[00:35:01] **Ben:** I was

[00:35:02] **Adam:** Yeah.

[00:35:02] **Ben:** feelings,

[00:35:04] **Adam:** It's how you process the, the, the information. Yeah.

[00:35:07] **Ben:** you and, and I bring it up because what I want in a moment like that is for people in leadership to not have my common sense. My common sense would be to indulge that feeling. What I'd want in my leadership is for people to say, actually that's not the feeling that's appropriate to be having. And we're gonna on all of our worldly knowledge and our decades of political experience to figure out how we're gonna make our way in this world. And again, I don't mean for this to be a political conversation, I'm just saying that I think we have this sense that there are things that should just be obvious to us.

[00:35:49] **Ben:** And I'm, the older I get, the less convinced I am that anything is common sense. And I was thinking to myself, okay, well what would, like, is there any one thing I could boil down? Like that is just a, a truth? And I kept trying to come back to the golden rule, do unto others as you would have others do unto you. And I'm like, is that even common sense? It, it's common

[00:36:14] **Adam:** Yeah.

[00:36:14] **Ben:** me. But I grew up in a household where I was deeply loved and wanted for nothing. And you look at people who grew up in a household. Where they were abused or they had alcoholic parents. then a lot of times grow up to repeat that cycle of abuse.

[00:36:33] **Ben:** And you think to yourself, okay, well then it's, it's not common sense for them. And I know not to touch on, on touchy subjects and some of this is closer to home for, for people, but like people do break that cycle, but that's not an obvious thing to do. So is even the golden rule, common sense.

[00:36:52] **Adam:** it's a, I think it's an interesting and valid question to ask. A lot of the stuff that you brought up, the golden rule and, and other stuff seem, I, I think we take it for granted as common sense because it is, once you are taught it, it seems so obviously correct, right. That it should be something that's common.

[00:37:14] **Adam:** I, I think that that one in particular, you know, probably was born out of philosophy. It's probably too old to, to know the true etymology of it. But, I think that, you know, like you were saying, people, people's upbringings color, a lot of their, of what we, what we then go on to consider common sense.

[00:37:32] **Adam:** And if you aren't taught those things then, then it's just not common sense for you. So I think. It's an interesting question, I think, because it, it brings up the question of what really is the definition of common sense, and I think that

[00:37:46] **Ben:** Well, okay, so, so you've talked about before, I think you've made this statement before, which I agree with that every act is political. There's no such

[00:37:53] **Adam:** Yes.

[00:37:53] **Ben:** apolitical act.

## [00:37:55] The Concept of Common Sense

[00:37:55] **Ben:** An apolitical act is just something that happens to align with your own politics kind

[00:37:59] **Adam:** Right?

[00:38:00] **Ben:** And I feel that. In that vein, common sense is the same outlook that things that are common sense are common because they align with the way that I see the world. So it's not that it's common, it's that it's familiar almost.

[00:38:18] **Adam:** Sure.

[00:38:19] **Ben:** so I, wonder if common sense as a notion is actually more harmful than it is beneficial it allows you to dismiss people. Like how do you, you know, common sense dictates that you shouldn't cut people in line. You'll be like,

[00:38:38] **Adam:** Yeah,

[00:38:38] **Ben:** I don't know. That's, that makes sense to me. But there's probably people who that doesn't make sense to, we've all been in, traffic and you're in that slowly moving line because you have to get off on the exit. And then just as you get to where the

[00:38:51] **Adam:** yeah,

[00:38:52] **Ben:** happens, some guy comes up at 60 miles an hour and cuts in the front.

[00:38:55] **Ben:** You're like, okay. I wanna believe that that guy is a jerk.

[00:38:59] **Adam:** yeah.

[00:39:00] **Ben:** believe that everyone behind me hopes that he's a jerk and something terrible happens to him and his whole family. I think that's

[00:39:04] **Adam:** Right.

[00:39:07] **Ben:** I, I don't know.

[00:39:08] **Carol:** opposite. Like dad. My parents said Josh, right? So my dad taught me differently. He is like always assume whatever they have going on in their life is so much worse than what you're dealing with right now. That they don't have the ability to wait five seconds. So be grateful that you can just sit here, that you get to, you know,

[00:39:26] **Ben:** I, yeah,

[00:39:27] **Carol:** in the car and hear your song while you drive home.

[00:39:30] **Carol:** Like realize that nothing in your life is that chaotic, that you have to make those kind of decisions.

[00:39:36] **Adam:** Yeah.

[00:39:37] **Ben:** and I think that's wonderful. And, but, but, and to my point, like, I think so much of what we think is common sense is just how we were happened to be raised. You know, how we were luckily raised in cases where it's good and how we were unfortunately raised in cases where it's not good.

[00:39:51] **Adam:** Yeah.

## [00:39:51] A Buddhist Proverb

[00:39:51] **Adam:** so what you were just talking about, Carol reminded me of, I'm gonna call it a proverb. I don't know if that is the correct term, but like, it, it kind of comes out of Buddhism. I, I wish I could remember where I heard this. It was, you know, within the last month. and so I, I apologize to whoever I'm stealing this from, but basically, it's like a old Buddhist proverb that, you know, somebody is holding, a cup of water and, and walking, and somebody else bumps into them and the water comes outta the cup.

[00:40:15] **Adam:** And the question is, why did you spill the water? And so the person. Holding the cup says, well, because somebody bumped into me. And the the Buddhist says, well, no, it's because water is what you had in your cup, right? And the lesson is supposed to be whatever it is that you're carrying around with you.

[00:40:34] **Adam:** When you get thrown off of your, your path, right? You get shaken up or something stressful happens, or whatever, whatever you're carrying is gonna spill out of you. So if you're walking around just full of rage, full of hate, that you're kind of suppressing doing that work to, to try and make yourself better or whatever, but like, you know, it's kind of bubbling under the surface, then when you get stressed, that's what's gonna come seeping out through the cracks.

[00:40:57] **Adam:** Versus if you train yourself to have love and empathy in your heart, right? When somebody cuts you off on the highway, you're like, oh man, I hope that, you know everything's okay. I hope that guy isn't rushing on the way to the hospital. You know, like, yeah.

[00:41:12] **Ben:** I can't even imagine having that mindset. It's so nice though. It's so nice to hear that.

[00:41:17] **Adam:** I, I, it's funny because I, I have never noticed the switch in myself, but there was a time not that long ago, like I'll say approximately 10 years ago, where I thought exactly like you're talking about Ben. Like I would just, everything was annoying to me. If somebody was in my way, then they were wrong and they were annoying.

[00:41:33] **Adam:** And now it's like, and maybe, maybe it was becoming apparent or something. I, but now more often than not, I'm, I've got the, oh, I, you know, the, the, what, what Carol was talking about, just the, the love in my heart. I, a an H of GI know, I, I know who I can attribute that one to. John Green, the author, he, hermeneutics of generosity.

[00:41:56] **Adam:** basically it's your, your worldview, right? What, how do you, what through what lens do you interpret what you see in the world? And if you interpret everything through a generous lens, then you're trying to think like, okay, well obviously that person needed to be in front of me for some reason, right?

[00:42:13] **Ben:** I, I feel like I'm very generous in certain ways, but then very unforgiving in many other ways. Like if I'm walking down the street and my dog passed, but if I was walking down the street with my dog someone oncoming, the audacity to not even look at my dog, to just walk by in their own world, I just, I'm like, well, this is obviously a miserable person.

[00:42:38] **Ben:** 'cause who would not wanna at least glance at my dog? You don't have to smile, but like, it's, she's gonna brighten your day. She's adorable.

[00:42:46] **Adam:** Right.

[00:42:47] **Ben:** like, there's just like so many of those little things that just get under my skin, but I try to be a good person. But,

[00:42:54] **Adam:** Being the type of person your dog believes you are.

[00:42:56] **Ben:** I know, right? Uh,that's, that's the high bar. So, so I, not to bring it back to AI again, but, so, okay.

## [00:43:06] AI and Common Sense in Technology

[00:43:06] **Carol:** should talk about text something. Yeah.

[00:43:08] **Ben:** But this is another one of those things where I keep saying that I'm holding AI wrong, and, and I feel like there are a lot of people talking about how, in a sense, like, use of AI is just common sense at this point. It feels like, I mean, that's not, that's not necessarily the

[00:43:26] **Adam:** I don't think we're quite there yet, but I get what you're saying.

[00:43:29] **Ben:** and then I'm also not sure if I can take people at their words.

[00:43:33] **Ben:** I was listening to an interview just yesterday with this guy, Justin Sils. I don't know him very well. I know he's very well known in the Ruby world. He, he started a company called Test Double, which is, I think is like a consulting agency. And this is not necessarily about anything related to him, but they were talking about ai. made a comment to the effect of, it used to be that you would need a team with 12 people on it, and now in the morning I can wake up and I can spawn 12 AI agents and do that work. And like, to me, that seems bonkers that that's even possible. And is he joking or is he exaggerating? Is he spinning up two agents and he's just making the, the exaggeration that you could have 12 to replace a team?

[00:44:19] **Ben:** Or is he actually waking up in the morning and spinning up 12 agents and I'm only bringing that up. 'cause in his mind it's very clear the intent of his statement because he's so mired in that world that it's like, you know, if I said I'm so hungry, I could eat a cow and I'm talking to someone who's never seen a cow, they wouldn't have any idea if I was joking or not.

[00:44:41] **Ben:** But to someone who's what a cow looks like, you'd be like, oh yeah, you're probably just hungry for a burger. Right? Like, you're not actually gonna eat a a two ton animal. So. I feel like when I hear people talk about ai, I feel like they're talking about cows and I've never seen a cow in my life, I don't know what's common sense to them what they're just saying as exaggeration or metaphor. I think that, again, like it's just, it's all about what you're familiar with and, and if you're not familiar with it, it's so important that we agree on the meaning of things and the names of things and what terms mean and

[00:45:19] **Adam:** Oh my God.

[00:45:19] **Ben:** are being used and just.

[00:45:22] **Adam:** I mean, naming things or, or agreed. A shared vocabulary is so important. I got a ticket today from somebody who used a tech word, probably because, you know, they'd heard it once or twice and thought it applied in this situation and had nothing to do with what they were talking about, right? So they were asking about like a, was there warehouse sync process working, right?

[00:45:42] **Adam:** like they, they send us data every night. They put it in a file on S3 and we ingest it. But what they asked was, is the web hook working? And I'm like, you are not asking about web hooks,

[00:45:55] **Carol:** Huh?

[00:45:56] **Ben:** Is your refrigerator running?

[00:45:57] **Adam:** right? So yeah, let's, let's, let's use, more basic terminology here so that we can actually have a meaningful conversation.

## [00:46:05] Common Sense in Programming

[00:46:09] **Adam:** So, yeah, I, I do wanna kind of bring this back a little bit toward, let, let's take common sense and our, our, our locus for the podcast here, tech, and put them together. So,I, I feel like there are some things, some concepts or, or techniques in technology and programming in particular that we probably take for granted as common sense that, especially somebody who's maybe like self-taught or came up through a bootcamp where they just don't have a long, I, I, I'm gonna use the word professional because I can't think of a better one, but like a long specific, like a, a syllabus that they learned, right?

[00:46:41] **Adam:** They didn't go to four years of college for computer science, right? They, one way or another bootcamp, or, or self-taught or whatever, they, they just don't know what recursion is, right? That sort of thing. Like, I'm very curious if you, if we can come up with some things that seem like they should be so obvious to us that, that we would consider them to be quote unquote common sense.

[00:47:00] **Adam:** Um. I am always shocked when people have not heard of things. That seem like they're in every other conversation that I've ever heard. Like people will say, oh, you know, the mythical man month has taught us this. And

[00:47:15] **Adam:** Yeah.

[00:47:16] **Ben:** mythical man month. What's that?

[00:47:18] **Adam:** So,

[00:47:19] **Ben:** like the, the dry, dry principle and you're like, dry principle.

[00:47:22] **Ben:** What's that? I'm like, what?

[00:47:25] **Adam:** yeah, so,

[00:47:27] **Ben:** myth. Sorry.

[00:47:28] **Adam:** no, I was gonna do the same things. You, Carol, you, you said you don't know what the mythical man month is. It, it's,

[00:47:34] **Carol:** Yeah, no, go ahead. We

[00:47:37] **Adam:** uh,the, the, basically you can't make a baby arrive faster by using two or three women to do the pregnancy. You can't spread that work out. Right. Some things just take as much time as they take the, it's a lot more nuance that there was like a big scientific study, that sort of thing. And it was just about like, you can't just always throw more people at the team and expect work to go up.

[00:48:00] **Carol:** 'cause it adding more people adds overhead of coordination and planning and all that. So, uhYeah.

[00:48:06] **Ben:** I keep getting, you know, I, I, I try not to walk, go through my, the YouTube shorts or the Facebook reels too much. 'cause I know it, it, it sucks my

[00:48:14] **Adam:** mm-hmm.

[00:48:15] **Ben:** But there's this one female programmer, and she does a lot of comedy. I think it's actually pretty funny. she had one today where someone coming to her and say, Hey, we wanna build this app.

[00:48:24] **Ben:** How long do you think it'll take? And she says, I think it'll take about three months. She's like, well, what if we got you an intern? And she goes, oh, okay. Then it would take four months. She goes, oh.

[00:48:33] **Adam:** Mm-hmm. Yeah.

[00:48:43] **Carol:** been there.

[00:48:44] **Adam:** So, Ben, you were saying like, you're, you're taken aback when people mention these things that seem so commonplace. Like you've, you've been hearing them for years and years, that, that they don't know that. Are you the type of person I'm gonna reference an XKCD comic here, but are you the, the, oh, you're one of today's lucky 10,000.

[00:49:01] **Adam:** You know what I'm talking about?

[00:49:04] **Ben:** I, it's like it's in the back of my mind, but I can't quite conjure it up.

[00:49:08] **Adam:** Okay, I'll, I'll find the comic. But basically like, it, it's just, is it, it goes back to like an H of G, right? Like, instead of belittling people for not knowing a thing that, that seems so like normal and common to us. It's like basically statistically, there's gonna be 10,000 people learning about. So, oh, that's what it was.

[00:49:28] **Adam:** So if you take a topic that quote unquote, everybody knows there's more people being born every day, more people entering the field every day. And so statistically there's like 10,000 people a day that are learning. A topic that quote unquote, everybody knows, right? Because there's always more people coming that just haven't been exposed to it yet.

[00:49:46] **Adam:** So there's 10,000 people per day that are learning it. And so instead of being like negative about the fact that they don't know it and, and gatekeeping or, you know, othering them, you instead you can be like, oh, congratulations. You're one of today's lucky 10,000, and you get to be the one to like teach them about this thing or, or show them where to find out more.

[00:50:05] **Ben:** To be clear, I don't. I ever belittle people for not knowing things, but I, I, I take your point.

[00:50:11] **Adam:** So, we'll, we'll definitely, I'll put the, the link to that XKCD comic and, the H of G is more information on that in the show notes for sure. Right.

[00:50:22] **Ben:** the other one, talking about common sense and programming that I've always struggled with is people will reference an Einstein quote, which, you know, who knows if he ever actually said this, he said something to the effect of Why would I memorize something? I could just look up in a book? And people will often, I think, parlay that into why should I bother remembering syntax for programming or the in a sequel statement if I could just look 'em up. And I feel like. Common sense dictates that I can move faster if I know the things already.

[00:50:58] **Carol:** Yes,

[00:50:59] **Ben:** like it's, it's one of those things where like, I don't know how to argue with you because I feel like the basis of your argument is nonsensical.

[00:51:06] **Adam:** Mm-hmm.

[00:51:07] **Ben:** If I, if like the words are already in my head and all I have to do is type them, is there any chance I can go slower than you by having to look them up?

[00:51:14] **Ben:** That's just, I feel like common sense dictates that's,

[00:51:17] **Adam:** Yeah.

[00:51:18] **Ben:** of light problem

[00:51:19] **Adam:** Well, so yes and no. I don't disagree with what you're saying, but it, there's only so many complex things that you can hold in your head.

[00:51:26] **Ben:** HA hundred percent. And I know that, that there, that there's a limit and I, and I do have to look up a lot of stuff. I think it's the, the general I think didn't diminishment that some people take towards that it's, that it's like they wanna, instead of just saying, it would be great if I could remember that stuff.

[00:51:49] **Ben:** It's like, they wanna say, well, memorizing stuff is just stupid.

[00:51:53] **Adam:** Right?

[00:51:53] **Ben:** And I'm like, I don't think that's true though.

[00:51:56] **Adam:** Hmm.

[00:51:56] **Ben:** And then I get worried. I'm like, you sh you should remember things. You know? It's like, it's, it's, it's one of those things where like, imagine if you walked into every room and every room you walked into, you forgot why you walked into that room.

[00:52:11] **Adam:** Oh, you're talking about my life.

[00:52:12] **Ben:** you know, like, I feel like that would be a problem that if

[00:52:15] **Adam:** It is.

[00:52:16] **Ben:** writing stuff in programming over and over again, you know, the concepts, the, the, the context is always different, but a lot of the syntaxes are the same.

[00:52:24] **Ben:** Like, if you're writing that stuff over and over again and you're not remembering it, like, I don't know that, that doesn't seem right either. Like, that seems like a, like, you're, you're not engaged or something. I mean, I, I don't know. But again, like this is where, to me that's just common sense that that would happen.

[00:52:41] **Ben:** You would just remember stuff. But maybe it's not common sense. Maybe

[00:52:43] **Adam:** Hmm.

[00:52:44] **Ben:** maybe I am blessed that my brain works that way, that

[00:52:47] **Adam:** Yeah.

[00:52:48] **Ben:** thing over and over again, it sinks in.

[00:52:50] **Adam:** It does sound a little bit like, it goes back to what we were talking about last week where you very much come at this profession. From a, a software craftsman perspective, the, the craft of the task matters to you at least as much as the, the task itself.

[00:53:06] **Ben:** Right. Hence me walking through token design systems with chat GPT

[00:53:10] **Adam:** Yeah.

[00:53:10] **Ben:** two weeks.

[00:53:13] **Carol:** But successfully, don't forget to add that.

[00:53:15] **Ben:** Well, remains to be seen, but I'm feeling successful in my endeavors.

[00:53:21] **Carol:** So when we talk about common sense, I also think about like our user's common sense as well. Like our users like think things like drag and drop should just work,

[00:53:30] **Adam:** Mm-hmm.

[00:53:31] **Carol:** things just happen. But then our developers tend to want to make things work, how their brains work. So then there's usually a big disconnect. So that's like where I see common sense hitting a roadblock. It's where. I think very logical, and I know like I should click all these buttons to make this action happen. However, I need to tell my user that you can't just continue without filling in information.

[00:53:59] **Carol:** Like, I can't assume that they're going to have the common sense to, to know that they're gonna have to put in their first name and their last name and their password can't be password. Right. But for me, I know those things that I don't need to be told that. 'cause for me, that's common sense for my user.

[00:54:15] **Carol:** That's not common sense it. So I feel like there's like a, a middle layer there that someone always has to solve for me.

## [00:54:23] Malice and Incompetence

[00:54:23] **Ben:** Let me, if, if we can maybe end on a philosophical note that I think like common sense adjacent,

[00:54:30] **Carol:** Mm-hmm.

[00:54:31] **Ben:** is the statement that, what is it? Like never chalk up to malice, which you could chalk up to.

[00:54:38] **Adam:** Attribute. Yeah.

[00:54:39] **Ben:** yeah. Never attribute to malice that, which you could attribute to incompetence. And I have never liked this statement and I, and I was talking about this with my wife 'cause we, I was talking a little bit about the topic for the show and, and just trying to formulate my thoughts and she was lovingly sitting there letting me just talk at her. And, and I was, yeah,

[00:55:02] **Carol:** Yeah.

[00:55:03] **Ben:** she's. And she said, well, sometimes people have willful ignorance that they're, they're just like choosing not to better themselves. said, I don't know if that's practically different than malice. That if you're going through life and you're choosing not to learn and you're choosing not to better yourself, and you're choosing not to figure out how to handle your emotions better and to navigate through the world in a more loving way, like that's, that's malicious. You live in a society that's

[00:55:39] **Adam:** Or at least selfish. Yeah.

[00:55:40] **Ben:** I, I Like, I don't, I think it, it's like one of those distinctions without a difference.

[00:55:46] **Adam:** Yeah. Could be.

[00:55:47] **Ben:** like you have decided, you have chosen violence as I think the, the kids say.and I don't know, to me that's, I, I think people have in some sense a responsibility to, to try to be better.

[00:56:04] **Adam:** So,I, I don't know what the official wording of the, the phrase is, but I, the, I thought of something when you were saying it, so never attribute something to malice when you could attribute it to, what was the word you used? Incompetence. Yes. And, the thought I had was, let's swap that out for ignorance.

[00:56:22] **Adam:** And for me, that works because I think of ignorance, not as, a character flaw as just a, a state of being. Right. You, you don't know this yet, right? And now there's, like you were talking about, there's willful ignorance, which is a different thing, but,

[00:56:37] **Ben:** it, it's, it's a, yeah. And like where do you, you know,

[00:56:39] **Adam:** right. Mm-hmm.

[00:56:40] **Ben:** to a doctor and my doctor said, oh, you don't look so good. Have you tried drinking this Mercury? And, and you're like, ah, I'm pretty sure that's gonna kill me. And you're like, oops, I didn't study. The Mercury is bad to drink chapter in my medical book. You're like, well, but that's, your job to know this stuff.and I'm not saying that, that everyone has the job to know all the facts, but like, know. I'm, I'm just saying that, that I think we are sometimes too lenient on ignorance and people just have to take some responsibility.

[00:57:19] **Adam:** And on that positive note,

[00:57:22] **Adam:** uh,

## [00:57:23] Patreon

[00:57:27] **Adam:** this episode of Work Code is brought to you by Bootstrap Ear, Ben's new design system. I, I just, yeah, I just named it for you.and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the, into the universe, then you should consider supporting us on Patreon.

[00:57:40] **Adam:** Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them. Special thanks of course to our top patrons, Monte and Giancarlo. You guys rock.

## [00:57:50] Thanks For Listening!

[00:57:50] **Adam:** We are gonna go record the after show, which you've heard me describe a thousand times as the thing that happens after the show ends and the people that support us get to, to hear more of us babbling.

[00:57:59] **Adam:** Sometimes it's on topic, sometimes it's off topic. I think tonight we're gonna be talking about TV stuff. Ben mentioned a TV show he wants to talk about. I got one I wanna talk about. So it's probably gonna be heavy TV related this week, but you won't know 'cause you're not listening to the after show.

[00:58:13] **Adam:** Or are you? I don't know. You'll you, maybe you will, maybe you won't, I don't know. But if you would like to get that and all of the past and future after shows, you can go to patreon.com/workingcodepod, throw a few dollars per month our way cup of coffee, and we would greatly appreciate it.you can also join our discord.

[00:58:32] **Adam:** Go to WorkingCode.dev/Discord. it's totally free, open to the public and a great place to hang out, and we'd love to have you join. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:58:42] **Carol:** even if you park the ally across two spots, your heart matters.

[00:58:47] **Ben:** bold statement.
