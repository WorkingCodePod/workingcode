---
title: "247: Trust Me Bro - LLM Security"
description: "Adam builds a Claude Code skill and stumbles into an uncomfortable realization: we're back to storing passwords in plain text."
date: 2026-02-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/247-trust-me-bro-llm-security/id1544142288?i=1000748358887"></iframe>

Adam built a Claude Code skill for his Taffy REST framework and wanted to share it with the CFML community. Simple enough—create a GitHub repo, add some markdown files, done. But somewhere between "this is cool" and "anyone can install this," a familiar chill crept in. These skills are just text files. No checksums. No digital signatures. No verification that the thing you're installing won't quietly exfiltrate your code to some server in Eastern Europe. Sound familiar? It should. We've been here before—back when passwords lived in plain text and "security" meant hoping nobody looked too hard.

The hosts dig into the unsettling parallels between today's LLM plugin ecosystem and the wild west of early internet security.

### Links

- [Adam's Dotfiles Blog Post][adam-dotfiles] - Getting his shit together with dotfiles, Brewfile, and 1Password SSH agent
- [CF Community LLM Marketplace][cf-marketplace] - Adam's community marketplace for CFML-related Claude skills
- [Steve Yegge's Google Platforms Rant][yegge-rant] - The infamous accidentally-public Google+ post
- [Vibe Coding by Gene Kim & Steve Yegge][vibe-coding] - The audiobook Ben's been enjoying
- [Socket.dev][socket] - Supply chain security for npm dependencies

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/247-llm-supply-chain-attacks.md
[adam-dotfiles]: https://adamtuttle.codes/blog/2026/getting-my-shit-together-dotfiles-brewfile-1password-ssh-agent/
[cf-marketplace]: https://github.com/CFCommunity/llm-marketplace
[yegge-rant]: https://gist.github.com/chitchcock/1281611
[vibe-coding]: https://www.audible.com/pd/Vibe-Coding-Audiobook/B0DQJPB5VT
[socket]: https://socket.dev/

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** Maybe, I mean, honestly, I don't wanna throw anybody under the bus, but like, I noticed, the CLAUDE.md file in our repo was like, 14,000 lines long with, with like, oh, I mean, it's just

[00:00:10] **Adam:** I don't know what the process was that created it, but I looked at that and, and based on what I knew, I was like, okay, this is not it. This is not what we need to be doing. So.

## [00:00:38] Intro

[00:00:38] **Adam:** Okay, here we go. It is show number 247 and on today's show we're gonna talk about LLM Supply Chain Attack. Worries. I got some and I wanna talk about 'em. But first as usual, we'll start with our triumphs and fails. Carol's back. got the whole team here.

[00:00:51] **Carol:** Ooh,

[00:00:52] **Adam:** apologies in advance if you hear any, uh, puppy barking in the background.

[00:00:55] **Adam:** Uh,Carol's got a new puppy

[00:00:57] **Carol:** husband. Oh yeah. Just my dog.

[00:01:00] **Adam:** she's got him, uh, on a leash tied, tied to the wall behind her, the husband, not the puppy. yeah. Anyway, so some of that might sneak through.

## [00:01:06] Adam's Triumph

[00:01:10] **Adam:** Looks like it's my turn to go first on trys and fails. I'm gonna make it real quick and easy. I don't really wanna get into too much detail on this just 'cause I feel like it's not gonna be great over an audio format.

[00:01:14] **Adam:** basically I put a blog post out and I think that it works much better in that medium. So we'll have a, a link to this in the show notes. But basically like over the weekend, I had Claude teach me the right way to do like dot files as like a, a repo that you can share or that you just.

[00:01:29] **Adam:** Publish so that you can pull it in on your next machine when you get a new machine sort of thing. Help transfer your config from machine to machine. This is a concept I've been vaguely familiar that people were doing for years and years and years. And then I, I thought I understood like, oh, you're, you know, you just download your dot files repo and then you sim link from that, you know, place where you clone it and then, similarly get to where the app expects it to be.

[00:01:53] **Adam:** And I guess that kind of works, but that's not really a great way to go about it. And so I had Claude teach me about like, how to use a bare git repo, and, there's a whole bunch of stuff in there and it's just like, it feels good to have that figured out and feel like I'm doing something smart to preserve the, preserve, the config of my machine.

[00:02:12] **Ben:** I'll tell you one thing that I'm feeling the, I don't know what the right word here is, but historically, and this is gonna shock all of you, but I've never been a big tools person, whether it's,

[00:02:22] **Tim:** Besides

[00:02:23] **Ben:** know, CICD, the, the editor, the DOT files. Like my sublime text to this day, I think has one plugin installed, which is the CFML syntax highlighter.

[00:02:34] **Adam:** you can just stop it. Sublime text

[00:02:37] **Adam:** that says it all.

[00:02:38] **Ben:** like, I use the default spotlight that comes with the Mac. You know, I never, I've never done Alfred or you know, long story short, I'm not a tools person and I feel like I was able to be very productive for the longest time and coming into this AI era, I feel like the tools people are finally just winning.

[00:02:57] **Ben:** and I do feel like I'm gonna have to start adopting tools that to me, don't have a ton of value except for the fact that they're gonna work really well with ai. And that's just the reality now.

[00:03:07] **Adam:** Hmm,

[00:03:08] **Ben:** And I, I don't know, I don't love that. I get it, but it also frustrates me anyway. So I've never been a person who has a lot of dot files,

[00:03:16] **Ben:** so I'm fascinated by this, but it's like also probably one of these things that I probably have to learn about.

[00:03:21] **Adam:** Yeah, I mean, like the, the very first thing that kind of comes to mind for me, like the, one of the things that I have in my dot files is, the config file for the GH command line access to GitHub.

[00:03:33] **Adam:** and, I've been adding a lot of Claude stuff to it as well. And there's a bunch of other stuff that, you know, like my Z-S-H-R-C config, all that, or like .bashrc, if you're more familiar with that.

[00:03:43] **Adam:** or zsh as, as the people say,

[00:03:46] **Tim:** As Sean Corfield would say, I would like to say I do commend you for what I think is probably the best way to use. This fascinating tool that we've had the past few years of learning something. So many people use AI to not learn stuff and just to do stuff without thinking and to, and that is super helpful to, to learn stuff.

[00:04:07] **Adam:** Oh man, I, I've been, it's a, it's a crazy like paradigm shift. I've been, I, I, I wrote two blog posts within the last seven days, which is crazy considering, I think I wrote two within the last, like, 14 months prior to that. and, and I have another one like bubbling away in my head that's, that's gonna come out soon once I finish thinking about it.

[00:04:25] **Adam:** But basically like, yeah, so not only did I have Claude teach me how to do dot files better or at all, I did it while I was riding in the car. So over the weekend we went and visited my wife's. Yeah, I went, we went and visited my wife's grandfather who's 103 years old.

[00:04:41] **Ben:** Dang.

[00:04:41] **Carol:** Wow.

[00:04:41] **Carol:**

[00:04:41] **Adam:** yeah. And you know, in the car, you know, one of the kids was like, Hey, can I ride up front?

[00:04:46] **Adam:** And I'm like, actually, yeah. So I, I sat in the back and, just sat on my laptop tethered to my phone. And, you know, there was spotty connections that was often kind of slow to get a response, but I was tethered and getting responses from Claude Code and just be like, okay, now, okay, well, you know, help me make sense of this part.

[00:05:04] **Adam:** Or what does that mean? And it was super interesting and fun. Like great way to make the time pass on a like an hour plus long car

[00:05:10] **Adam:** ride.

[00:05:12] **Ben:** Very cool, very cool. not to make this about me, but I'll make it about me for a second. I do think I'm gonna have Claude try to teach me how to add some tests to an existing project.

[00:05:23] **Ben:** Yeah, I know, I know I have. It's like I have zero interest in it, except for the fact that apparently to trust the AI to do stuff, it needs to be able to verify that it's done the right thing.

[00:05:35] **Ben:** And I, you know, I can't just depend on my, you know, wit and good looks anymore. I have to.

[00:05:41] **Carol:** Yeah, it's funny you say that. My boss is getting big on trying to see what he can accomplish, and he's tech, he was a developer before and now he's a supervisor. So he's trying to see what he can use AI for to take things off my plate. And the very first thing he took on was rewriting an entire application

[00:05:59] **Tim:** Oh wow.

[00:05:59] **Carol:** had to kind of circle him back a little bit and go, did you know this, that most of the tests are commented out?

[00:06:05] **Carol:** so how do you even know if this is working? So he, I met with him today and a few of, the other people that work this project and he has like 17 files to push up that have integration test that just have, it's all testing and changing some of, um, how we, use dependency injection and make. It actually be testable and sending some configs that'll allow for like logging to remain in place.

[00:06:29] **Carol:** So I kind of pulled him back and did the same thing and went first use it to learn to write the test. Once you have the system working and testable, now let's talk about improvements.

[00:06:39] **Adam:** Honestly, it's a great teacher on like how to write better tests too. Be like, just go into this project and be like, I know the tests are crappy or non-existent for this project. help me understand how to write testable code.

[00:06:50] **Ben:** Yeah. Okay. So I know this is gonna sound terrible, but I think that's a little bit why I'm okay with this, with the giving in is because I feel like if I can just have it show me how to get the tests in place, then I can have it write the tests and it's like, I, not that I can stop caring, but it's like I can look at what it's doing

[00:07:09] **Adam:** Right,

[00:07:10] **Ben:** and not stress about doing it right myself.

[00:07:13] **Ben:** As long as, you know, I can tell probably if the test makes sense. I mean, I'm not, it's languages that I know. So it's not like it's writing some esoteric, arcane language that doesn't make any sense. So I feel like if I can just do that, I'm hoping it's the 80 20 rule where like 20% of the effort to get the tests in place and, and that's gonna be 80% of the value.

[00:07:33] **Tim:** I know this is a side quest off of Adam's side Quest, off of Ben's side quest, but I'm very, I'm very proud. So my son is his final semester of college

[00:07:43] **Adam:** Wow. Already.

[00:07:44] **Tim:** finally, finally getting an entire class about testing

[00:07:49] **Ben:** Dang.

[00:07:49] **Adam:** Hmm.

[00:07:50] **Tim:** finally. So I was like, okay, good,

[00:07:52] **Tim:** good,

[00:07:53] **Adam:** Glad it at least came up. Yeah.

[00:07:55] **Tim:** Well, I, I don't know, because I kept telling him, I'm like, so are you writing tests for this?

[00:07:59] **Tim:** And he's like, no, the teacher will give me. I'm like, no, no, not those kind of tests. So yeah, he's finally, they're finally doing unit testing and TDD.

[00:08:09] **Adam:** So, to, to pop one tangent off the stack here. going back to Ben, debated whether or not to tell you this, Ben, 'cause I think it could reinforce some bad habits, but. I have the idea that instead of writing tests or it would be a good compliment to writing tests, is tell the AI to look at the code, look at the tests and infer what the spec would be for the app or for the feature or whatever.

[00:08:31] **Adam:** And like it writes it out in human language. And then you can look at that. 'cause that's a lot easier than reading 9,000 lines of test files. If you just get like a two page markdown document and, and you parse it and you go, oh wait a minute, that's put backwards. Or, you know, that sort of thing kind of like translates all the code into English so that you can read it and, and understand what the

[00:08:51] **Ben:** Well, it's funny because when we were sort of at the dawn of this AI era, everyone was joking about, okay, so now we've built tools that can make the emails that I write really long, and then the people who are receiving it, they can use it to make those emails really short and bullet points. And I'm like, in a way that's awful for business stuff, but it seems to be a superpower for code and specifications documents. So just interesting.

[00:09:19] **Adam:** All right. Are we all, all the way back down at the stack of

[00:09:21] **Ben:** Yeah,

[00:09:21] **Adam:** here? Okay, so that's it for me. Ben, what do you got going on?

## [00:09:25] Ben's Triumph

[00:09:25] **Ben:** I, I'll go with a Triumph, which is that I am doing some AI stuff I don't know. Okay. So, we're using Claude Code at work and I'm getting my feet wet with Claude Code and trying to understand how it works. And,my boss, Peter, has given us permission to use Claude in our non-work stuff as an opportunity to get used to it.

[00:09:45] **Ben:** So I'm on a business plan essentially, and I'm playing around with it in my personal life here. I had to build some things, so I. at the show last week, I think it was, I was asking everybody, should I start on something greenfield or should I start on something? Brownfield? Carol said, brownfield, everyone else said greenfield.

[00:10:02] **Ben:** I did a little bit of both and I was excited about that. So the, the Greenfield one was, something that I knew that I would never be able to do in a million years, and that kind of made me feel fine about it 'cause I didn't care what the code looked like and I could just throw it out.I had it build me a video downloader, so I subscribed to some, Patreon channels and some of those are video content stuff.

[00:10:26] **Ben:** And, and I wanted to be able to, oh, can I give it just a Patreon detail page and have it look at the iframe in embed and see what it's doing? And I was so blown away. By not just that it could do it, but you can watch the reasoning on how it works. So it, I would give it a, a a page and it would say, oh, okay.

[00:10:46] **Ben:** Grabbing that page. And then it would say, oh, that page requires authentication. Oftentimes that requires an encryption key. Let me do a, a web fetch of that page to get the content. And it gets the content. It's like, let me look at the, the JavaScript that's embedded in that page. Oh, I see this special encryption key.

[00:11:02] **Ben:** Let me use that to generate the URLs. And then it started generating these URLs and it was making fetches and, and it was like, oh, I can make the fetch now, but it's still getting a rejection, so it probably needs additional HTTP headers. So it started adding HTTP headers from the referring page. And I mean, I'm just sitting here not doing anything and watching it and it, and then at the end it's okay, we're done.

[00:11:23] **Ben:** Video downloaded and stitched together with FFmpeg. And I was like, mind blown. And then I tried to give it another video and said, oh. This video is actually being served up by a different CDN with different requirements. And it basically did the whole same thing. And then it said, oh, I'll do this switch statement internally to figure out which platform we're targeting.

[00:11:40] **Ben:** And then it had stuff I, I don't know, I was just so blown away that it could actually do that.

[00:11:46] **Adam:** it is cool that it could do that, that kinda stuff. And it's fun to read through the, the sort of transcript of its thinking. it write code that makes this a, a repeatable thing that you can do, you know, go download my latest Patreon videos.

[00:11:58] **Ben:** here, here's the funniest thing.

[00:11:59] **Adam:** one time thing,

[00:12:00] **Ben:** it's, it, I, so I, I had it start building a dockerized container 'cause I'm trying to do everything in Docker as much as possible. 'cause I just, like, I'm on the docker train. I like containers.so

[00:12:10] **Adam:** new technology.

[00:12:13] **Ben:** It is, it is a docker container and, but it's Python scripts internally, and it's only like three or four Python scripts.

[00:12:19] **Ben:** And it started out with just the, let me give you the iframe embed, URL. And then, there was one where, I forget what the thing was. It, it's like it, each thing had a little different constraints and then we finally hit one video that it just couldn't do it all and it couldn't figure out even after all of its thinking.

[00:12:34] **Ben:** And I said, well, what if I just watched the video and then I save the network activity as a HAR file? I don't know what HAR stands for. It's like a network archive thing in your chrome dev tools, and it'll spit out like a 350 megabyte stack trace of every network request that it's made while the network activity is open.

[00:12:54] **Ben:** I said, can I just give you that and have you just replay the actual URLs from the network? so yeah, I'll totally do that. So that's,ended up being actually the most convenient thing for me to do. 'cause I'm, I'm watching the videos anyway. Well, it's, it's ASMR stuff, so I actually just have it on in the background.

[00:13:11] **Ben:** I'm like, not even really watching, so I'll just play it with the network tab open and then I'll just drop the har file in a folder and it bbo and zips it all together. But, um but

[00:13:22] **Adam:** solutions indeed, my friend.

[00:13:23] **Ben:** yeah, it's repeatable. It's, it's, uh, I was, I was pretty impressed. So that's, that's the greenfield. And then I'll just finish up really quickly with the Brownfield.

[00:13:29] **Ben:** Which is that I, I've talked in the past about my big sexy poems app for poem authoring, I'm, I just, this morning I started to try and play around with getting Claude to add a new feature. And I'm slow goings because now I actually care what the code looks like, which may be a party foul.

[00:13:46] **Ben:** I'm unclear yet if I'm supposed to care anymore. so yeah, just all around and I'll, and I'll say just one other footnote here. I downloaded and I've been listening to an audio book by Gene Kim of Phoenix Project slash Unicorn Project Fame. He and this guy, Steve Yegge, have an audio book called Vibe Coding and I've been quite enjoying it.

[00:14:07] **Adam:** Uh, way to bury the

[00:14:08] **Adam:** lead there. The,

[00:14:11] **Adam:** the,

[00:14:12] **Tim:** No, the lead is, he's doing testing

[00:14:14] **Ben:** yeah.

[00:14:16] **Adam:** Well, just about the book in general. Uh, you know, gene Kim. Okay, fine. Steve Yegge. Okay, now you have my attention. Right? That sort of thing.

[00:14:24] **Ben:** Yeah. Steve Yegge, I, I don't know the name, but

[00:14:27] **Adam:** so he's a, he is a pretty well-known Googler or former Googler.

[00:14:31] **Ben:** And Amazon, I think too.

[00:14:33] **Adam:** yeah. he worked in Amazon too. when he kind of came into, or when I first learned about him, it was Google Wave, like when they were, was it Google?

[00:14:41] **Adam:** No, the, what did they call it? Not Wave. They're like Social Network, Google Plus. Is that what it was?

[00:14:46] **Ben:** Google Plus.

[00:14:48] **Adam:** Yeah.

[00:14:48] **Adam:** Um, and

[00:14:49] **Tim:** That that was a thing.

[00:14:50] **Adam:** yeah, and they, they were like, so Google was making all of their employees like, use this. It was like the Google version of Facebook or

[00:14:56] **Adam:** whatever, right.

[00:14:57] **Adam:** and they were making all their employees use it.

[00:15:00] **Adam:** And so I guess there was like settings on each post. You could post stuff internal only or external. As a Googler.and he wrote this big long rant about everything Google was doing wrong and, you know, it was just like, it, it, it was infamous and he accidentally published it publicly and whoops, and it went viral.

[00:15:21] **Adam:** And, for what? I don't, you know, I don't remember the details. This was like 10 years ago, but, they were like, they ended up being cool with it. They were like, okay, fine. Leave it up. You know, you know, it was probably like, uh, all news is good news or, or no such thing as bad news sort of thing.

[00:15:32] **Adam:** Attention for Google Plus. But yeah, so that's when I started paying attention to Steve Yegge.

[00:15:37] **Ben:** So, yeah, so it's a, it's a good book. I mean, if you're deep into the AI stuff already, I, I don't think it would be super helpful. I mean, I'm only like halfway through it, but he's walking through the why AI is important and how vibe coding works and doing the specification stuff and having AI help you write the specifications and then feeding it back into the AI and doing a lot of commits.

[00:16:00] **Ben:** Where I'm seeing maybe the book aging a little bit. So I think this book was only released like in, in August or something of this last year, which you know, is like actually a million years ago at this point.

[00:16:13] **Adam:** In AI

[00:16:13] **Ben:** yeah.

[00:16:14] **Ben:** yeah. He's talking about, you know, do really small stuff. At the end of the day, you're, you're responsible for the code.

[00:16:21] **Ben:** It's your responsibility. You have to understand what it's doing. And, I feel like a lot of the people I'm hearing today are like, never look at the code. As long as the test pass and the specifications are well defined, they're like, just let it rip. So, you know, I, I don't know if, if, if that's just that it ages differently or that's the, that's the, fun.

[00:16:44] **Ben:** You can build tremendous things with low effort versus you actually have to run a business and be responsible. I.

[00:16:49] **Adam:** Yeah. I, I mean, I hear people saying like that, but it doesn't strike me as somebody who is in charge of an important business using it as their business. Right. It's, it, it strikes me as like, oh, you know, I vibe coded an alternative to whisper flow, the, the voice dictation app. okay, cool.

[00:17:08] **Adam:** You know, like if that breaks, you know, whatever, it's, it, he, if I coded it and it's open source and like, okay, so it is not working for you. Sorry.

[00:17:17] **Ben:** right. Where do I send my support tickets?

[00:17:18] **Adam:** Right. Yeah. So,yeah, I mean, I think there's a time and place for both approaches.

[00:17:24] **Ben:** Right. I agree. I agree. And I'm all very much still learning here anyway. I don't wanna take too much time.

[00:17:30] **Adam:** Yeah. We're 20 minutes in and, and two people down.

[00:17:33] **Ben:** Carol, what do you got going on, girl? I.

## [00:17:36] Carol's Fail

[00:17:36] **Carol:** Oh my goodness. I'm gonna go with a failure you guys. So a couple weeks ago, one of my bas mentioned that for some time now, they haven't been able to use an internal tool that we have created for them. So we have this consumer that basically allows them to mimic the process for what our API would be doing.

[00:17:56] **Carol:** So it's like interconnections, they go, Hey, like,requests are updating, these things are changing. Like what is the, agency gonna get? what notifications are we sending them? So we have, our own like connection that we allow the bas to hit and lower environment so they can test everything.

[00:18:13] **Carol:** Well, it turns out, a few months ago, stopped working. I didn't know about it, didn't know that they've been banging their heads because they can't test anything. So it got brought up a few weeks ago and I went, oh crap. I'm like, all right. They're like, we already have put the bug in. It's just not been prioritized.

[00:18:28] **Carol:** And I was like, Ugh, now I feel bad. So I'm like, okay, I'll, I'll get around to it. Like we're gonna put it in the backlog. So, Finally one of the, bas on this project, she was like, I'm just gonna set up a meeting so I can show you everything. So she set up the meeting for tomorrow. So I just went in real quick and was like, lemme just see, like get, get a head start.

[00:18:47] **Carol:** Right. I finally have a moment to look at it. Turns out IIS had been stopped on the server, so it just wasn't taking traffic

[00:18:56] **Tim:** Just

[00:18:56] **Ben:** Oh no.

[00:18:57] **Carol:** Oh.

[00:18:58] **Tim:** you just turn IIS back on and it starts

[00:19:00] **Carol:** Yeah, and since it was in a non-prod environment, the alerts were in place to be like, oh, this site's down. everyone just kind of assumed this was a test site, it would redeploy in a day and it'd fix itself.

[00:19:11] **Carol:** Turns out we never deploy it unless we change it. Right. So it's just been sitting there. So I had that moment of telling them, had I taken just like 30 seconds and looked at this when you mentioned it, we probably would've had you testing three weeks ago. Or you know, when you knew about it instead. I didn't take the time to do it, and I feel bad about that, but we get busy.

[00:19:29] **Carol:** Things happen and it's fixed now, so they're happy with it. I don't think they're too upset that it was that.

[00:19:35] **Ben:** Oh, that's the worst. That's the worst. And, and that's, I've always wanted engineers to be more involved with customer communication. And it's specifically for things like this where if you just heard it as an engineer, you might be like, oh, that's, there's probably something really obvious happening that just no one's thinking about, oh, that's, sorry.

[00:19:54] **Ben:** That's awful.

[00:19:55] **Carol:** Yeah, I, my first thought was, we're gonna have to get firewall involved. It's now being blocked by our VPN, like for some reason, all of our traffic's being aborted. No, turns out it's just not able to take any traffic at all from anywhere, anytime. So.

[00:20:10] **Ben:** well, we at work, just like last night we had the age old problem where an SSL certificate expired like at 11 o'clock at night

[00:20:19] **Carol:** the year.

[00:20:20] **Ben:** Yeah.

[00:20:20] **Tim:** Geez,

[00:20:22] **Ben:** I'm like, oh, how are we still doing this?

[00:20:25] **Tim:** I, it just certificate's driving me nuts. 'cause I don't know how we keep getting surprised by that. It's You know, when they expire, I told one of the guys, I'm like, just vibe code a thing that just goes out and checks the cert. Right. Look at the JKS and figure, I mean, seriously, we can't be keep getting surprised by this stupid stuff.

[00:20:44] **Carol:** Yeah. I do the thing where I go old school and I, if I ever have to update a sir or I send it over to the SAZ update, I look at the expiration date and I go ahead and put a calendar invite on my calendar for three years out, or you know, 10 months out. 'cause it's gonna expire again and then I can go, oh, okay.

[00:21:01] **Carol:** Do we know, are we good? I don't wanna be down in prod 'cause we didn't update it.

[00:21:06] **Tim:** I do that for our customers. Even though it's not our site, it's I, I remind, Hey, by the way, your SSL certificate for this thing that you registered, you need, it's gonna go out oh, thank you.

[00:21:16] **Ben:** CloudFlare has a feature now where you can, it will generate an origin certificate, like a self-signed origin certificate that doesn't go, that doesn't expire for 15 years. So if we're still doing the show in 15 years, guaranteed will be like, oh, you will not believe my SSL certificate expired last night.

[00:21:37] **Tim:** Wow. What number episode would be on by then?

[00:21:39] **Carol:** Oh,

[00:21:39] **Tim:** now. I mean, we're what, six we're, we're coming up on six years on this,

[00:21:44] **Tim:** this

[00:21:45] **Carol:** this is 247.

[00:21:46] **Ben:** All right. Tim will be dialing in from Portugal

[00:21:49] **Tim:** Yeah,

[00:21:49] **Ben:** being like, what's up people?

[00:21:52] **Tim:** Well, lemme tell you, SHA,

[00:21:53] **Carol:** All right, well that was my failure. What about you, Tim? You gonna win for us?

## [00:21:57] Tim's Fail

[00:21:57] **Adam:** Ah, I'm in the sailboat with you. Sorry, Carol. it's kind of two things. So we're doing a lot of interviews. We're hiring two new people, two new developers. It has some really excellent interviews, but the job market is so weird right now. It's like post COVID 2022.

[00:22:13] **Tim:** It's like people would just come in and name their price exorbitant rates, right? They're like, you're like, okay. But everyone was asking for that and you know, we, we paid it and now it's like people are coming in going, look, I just need a job. Just, I just, I just need to work. Please. I, you know, I, I was making $170,000 a year and I'll just do anything right now and I'm like.

[00:22:35] **Tim:** It's really weird. I, I feel it's kind of nice 'cause I, I mean, I love a bargain, but at the same time I kind of feel bad 'cause it's like people are hurting out there right now and it makes you worried. Like, you kind of wanna do whatever you can to keep your job. 'cause it's like, I, I don't wanna go out there right now while things are like, and I don't know why that is.

[00:22:54] **Tim:** I mean, I'm sure there's a whole lot of reasons why, maybe it's just a bounce back from that, you know, post COVID, overcorrect and a bit, a little bit of ai,

[00:23:03] **Adam:** Yeah, I think we're in the, the downswing of ai, like people get losing their jobs to ai. Like peop, a lot of people have been laid off for AI reasons, whether their, their job is being replaced by AI or, or whatever else. But I feel like a lot of that is gonna come back when companies start to realize actually, wait, we're, were way worse off now.

[00:23:24] **Adam:** so but, but in the meantime, there's a bunch of people that got screwed, so.

[00:23:28] **Tim:** but fortunately we need to hire a lot of people. We'll probably be hiring two more people in the next three to six months. So, yeah. So, but anyway, and that's, that's one. The other is, so we had two, so Claude was down today and ChatGPT was down today. So I don't know how I got anything done,

[00:23:44] **Adam:** Yeah.

[00:23:44] **Ben:** Yeah,

[00:23:45] **Tim:** but fortunately I was, I was mostly in meetings all day.

[00:23:47] **Tim:** So,

[00:23:48] **Ben:** I went to down detector 'cause I was all of a sudden Claude Code returned a 500. I was like, Hmm, that's weird. And went to down detector and it's like flatline, flatline, flatline like shoots up into the sky

[00:24:01] **Adam:** right.

[00:24:02] **Ben:** and a bunch of things went down. So I don't know what the ultimate cause was.

[00:24:05] **Ben:** Like FedEx was reported as down and T-Mobile or something, Verizon.

[00:24:09] **Tim:** I was thinking that DeepSeek finally reached sentient and has taken out its rivals one by one.

[00:24:16] **Adam:** Maybe, you know what I did while Claude was down, I had to find something productive to do. I added a subdomain to my domain. So if you go to status dot, Adam tuttle.codes, it redirects you to status.claude.com because that is my status as well.

[00:24:33] **Ben:** That's

[00:24:34] **Ben:** funny.

[00:24:34] **Tim:** Anyway, that's me. So what are we talking about today again? I forgot. It's been like

[00:24:37] **Adam:** Yeah, it's been like a almost a half hour that we've been going already.

## [00:24:40] LLM Supply Chain Attacks

[00:24:40] **Adam:** so, I did a thing today and it, and it gave me some feels, and I just kind of wanted to dig into that a little bit. The, the thing that I did was, you know, we've been talking about all this AI stuff and I've been wanting to learn, the Claude skills.

[00:24:55] **Adam:** So this is a, it is like a spec that's open, and I guess multiple LLMs are starting to add support for it. But basically like you can write a markdown file and you put it, you name it just right, and you put it in the right folder or whatever. And that markdown file can have, front matter at the top of it.

[00:25:10] **Adam:** It's just like YAML section at the top of the file. And it gives it like a name and a, and a brief description of like, what is the skill and when would you use it? and that way just that little bit, that what is the name and when would you use it gets included in every prompt that you send. And then the AI decides oh, okay, based on the prompt, the rest of the prompt, right?

[00:25:28] **Adam:** You ask me to do X, Y, Z. I either do or don't think I should load this skill. And, and then depending on that, it may or may not read the rest of that markdown file. So that's what skills are in a nutshell. and, so I, I wrote one, mostly used AI to generate one. Let's be real. that's based on the documentation for taffy, my CFML, rest API framework, which was real easy to do because the documentation is written in markdown.

[00:25:54] **Adam:** So I basically just handed it the current documentation. I was like, okay, we're gonna make this a, a Claude Code skill, and I want you to use the, like, progressive, disclosure, I think is what they're calling it. Where you like, you know, the, the root. Skill file is extremely minimal, right?

[00:26:09] **Adam:** My, I think mine is just like 40 lines or something like that. And, and it, and all of those lines are very short. and it's just like, okay, if this is, if, if you're doing this type of task, then go read this file. If you're doing this type of task, go read this file. And it kind of breaks, it breaks the documentation down into different chunks, right?

[00:26:25] **Adam:** So if you're doing something in application C, f, C, you should read this file. If you're doing something in a resource, C, FC, you should read this file sort of thing.and that it was all very interesting. And, I guess there's two parts to this. So one is I made this, my first thought was like, okay, now what, like, how do I share this with other people, right?

[00:26:40] **Adam:** I kinda wanna make this open source. Do I just put it in the taffy repo, whatever? So I did a little bit of research and I guess apparently there's not like one. Open, central hub or, or resource for sharing skills. There is like the, the built-in, blessed Claude repo of skills. I think they call it a marketplace,

[00:27:00] **Adam:** but I doubt that they would like just let anybody send, pull requests of their skills into this thing. It would get, it would get huge ridiculously fast. so they're not gonna do that. But you can have your own custom quote unquote marketplace. And that marketplace is just like a GitHub repo that has some specific files in it, that tells it how to find other stuff.

[00:27:18] **Adam:** So I, I created a marketplace in the CF community. GitHub organization. 'cause I don't want to be the, like gatekeeper. I want this to be like an organization where multiple people can approve, pull requests and, and all that sort of thing. I, this is not me looking for, I'm not like trying to, you know, get the glory or anything like that.

[00:27:36] **Adam:** I just, I wanted a place to put this. I created a thing. I'm more than happy to add contributors to manage the pull requests and to have people add their own skills or whatever. But it, it's, the CF community is the organization on GitHub, and then it's like, LLM dash Marketplace is the repo name.

[00:27:53] **Adam:** And basically I figured out like how you can, it's just like a slash command. You paste into Claude Code to add the marketplace, and then once you're in there, you can either like browse and find the Taffy skill plugin that I added, or you can, there's a slash command you can add that'll install it from that marketplace.

[00:28:09] **Adam:** Now that you've got the marketplace added, which is interesting and fun to figure out.

## [00:28:12] Skills and Plugins Architecture

[00:28:12] **Ben:** so just to take one step back. So skills are just one of the several things that you can have in your .claude file or your .claude folder.now, .claude folder can exist in multiple levels. It could exist in the project and the repository that you're working on. It can also exist in your user's home directory and then would be applied to all of your projects.

[00:28:39] **Ben:** And this is a philosophical question.

[00:28:42] **Adam:** more places than that too.

[00:28:43] **Ben:** Uh, is there, okay. Yeah. So I, to me, my whole life has existed around repositories there. This, the, everything I wanna share with other people that are related to this project, it goes in the repository. So for me, the idea of having anything stored globally seems weird.

[00:29:02] **Ben:** And not even just like going back to something like NPM, like, I always hated having to install NPM modules globally because I'm like, it pertains to this project. It should be version to this project.

[00:29:13] **Adam:** when you had to like install Grunt

[00:29:15] **Adam:** globally to,

[00:29:15] **Ben:** Oh, my goodness. And then it's, yeah, totally. And then like, sometimes you, it's impossible to upgrade 'cause like it doesn't wanna override the global install anyway.

[00:29:23] **Ben:** When you think about things like this, do you think that skills, and this almost relates back to your dot files triumph in a way. what would you suggest as best advice? If I have a skill. I know I'm probably going to use it in multiple projects. Is it still better just replicate it into every single repository that needs it, or would you go with the global personal repository, you know, folder.

[00:29:48] **Adam:** so this is a really good question that everybody should be asking themselves. And the answer is, it depends, right? So,

[00:29:54] **Ben:** of,

[00:29:57] **Adam:** if, if it is something that you are going to be using on basically every project, then yeah, put it in your, your home folder. The other thing is you would put it in the repository if you want it to be shared with other people working on the project, right?

[00:30:09] **Adam:** If it's just, if it's big, sexy poems and nobody else is ever gonna be contributing to that, then it doesn't matter either way, except that if you put it in your home folder, then it's gonna be pulled in and, and reference at least the, you know, 80 tokens for the name and description, on every single prompt for every single project you do.

[00:30:25] **Adam:** Versus if you put it local to that project, then it's only pulled in when you're prompting in that project.

[00:30:30] **Ben:** So, so just to paint a picture for people, when you go in Claude Code and you go into the plugins command, I

[00:30:38] **Adam:** the slash plugin

[00:30:39] **Ben:** Yeah.

[00:30:39] **Ben:** And then it gives you like the different marketplace options and you say, here's the Taffy plugin, I wanna install, install it, and then it, it prompts you right away. Do you wanna install this just for your user,

[00:30:51] **Ben:** for all users?

[00:30:53] **Ben:** And I feel like there's a third option, but I don't remember what it's

[00:30:56] **Adam:** It's like project local, your home folder. I think there might be a way to install it that is in the project folder, but in a way that's not gonna be committed, right? Like, I want this in this project for me. Right. Is it is like Claw Local or something like that where

[00:31:11] **Carol:** Yeah.

[00:31:12] **Adam:** there's, there's project shared with the rest of the team and then there's Project Local where it is just me.

[00:31:17] **Ben:** So the first time I saw that I was super confused. I had no idea. I'm like, for one user, all users. I'm like, I don't wanna mess anybody else up. But in real, like in retrospect, it probably would've just made sense for me to put it in the folders that everyone could use it

[00:31:30] **Adam:** Maybe, I mean, honestly, I don't wanna throw anybody under the bus, but like, when we first started using, it was even before I was using Claude, like one of my coworkers started using Claude, and I noticed, the CLAUDE.md file in our repo was like, I don't know, 14,000 lines long with, with like, oh, I mean, it's just tremendously hu It was obviously like AI just like spat a, a ton of garbage into this file.

[00:31:54] **Adam:** And maybe it was like, okay, tell me everything you know about this repository and figure it out and, and keep going. Go again. Add more, Add more, add

[00:32:00] **Carol:** it. Add to it.

[00:32:01] **Adam:** Right? I, I don't know what the process was that created it, but I looked at that and, and based on what I knew, I was like, okay, this is not it. This is not what we need to be doing.

[00:32:09] **Adam:** So.like the thing we need to be thinking about, I think is there's, there's an aspect of like hygiene or etiquette in what we share with the rest of the team. we really need to be thoughtful and careful about what we're putting in that context that's gonna be shared with every prompt, with every person who's, who's prompting in this folder.

[00:32:29] **Adam:** Right.

[00:32:30] **Ben:** it's tough because it's like, there are some tools that people like, I always thought it was crazy if someone put a dot editor config file in a shared repository. 'cause I'm like, bro, why are you coming at me? Like, your editor is my editor? That's nuts. but there are definitely tools that everyone should just be using, right?

[00:32:46] **Ben:** If we have a testing framework, throwing that out as an example, like everyone's using the same testing framework. It's not like you're for funsies bringing your own testing framework. And it's, it's like, I don't know where these tools fall on that continuum yet. Is this just you bringing your own swagger or is this no, this is how we develop features.

[00:33:05] **Adam:** Yeah. And depending on the type of project or whatever, it can be really useful to have like in your CLAUDE.md a breakdown of like, okay, this is where the service files are and this is where the controllers are and this is where the views are. And you know, we do our JavaScript over here. Whatever.

[00:33:18] **Adam:** Right? just so that

[00:33:19] **Carol:** in this one case where we do it over there. Yeah,

[00:33:26] **Adam:** Two real

[00:33:26] **Carol:** sorry.

[00:33:28] **Ben:** Oh, good times.

[00:33:29] **Carol:** That's why you have 14,000 lines in your markdown file.

[00:33:33] **Adam:** It's funny because it's true.

[00:33:35] **Ben:** So what other feelings are you having?

## [00:33:37] Security Concerns with LLM Tools

[00:33:37] **Adam:** Well, so, okay. I said this was a two part thing and astonishingly, I actually remember what the second part is. So part one was I did the, the whole like, marketplace thing, right? Which was interesting to figure out. And, and I do, part of it is I just wanna spread the word so that other people can contribute their stuff to it as well.

[00:33:53] **Adam:** but the other part is this whole thing, like the, the skills, the plugins, the MCP, all this stuff we're figuring out feels to me very much like early days on the internet in terms of like security, right? We were so, yeah, yeah, we were so naive in the early days of the internet, right? I mean, like, if you didn't just hard code, like the one password to get into whatever tool, into the code, right?

[00:34:22] **Adam:** If you had like individual user account passwords, that wasn't like encrypted, that wasn't one way hash, that wasn't salted, it was just like clear text in a text file or in a, in a database column. Something. If you were that, if a database column was, if you were doing real good. Right. Like we were so naive, and I feel like we are kind of like we're re we're right back there.

[00:34:44] **Adam:** We're resetting the clock on that because we've got this new paradigm of thinking and sharing and working. And it's very much like just text files, which is interesting because I think it makes it even easier for somebody with bad intent, but no skills, right? Like before it, it, you know, if you were trying to, if it was 1985 and you're trying to break into some system, you could just go in and type God love whatever in the password box.

[00:35:09] **Adam:** So you get in, and, now, but, but that, to do any, any more than that at that time took some level of skill, right? You had to have some understanding of computer programming. Now, to be a, a person with a malicious intent, all you really have to do is like edit a markdown file. You know, send all. Of the, the nude selfies that this person takes to this email address.

[00:35:32] **Adam:** Right. And it'll figure out how to do it. I dunno. But, it, it's scary. It's scary times. and the things that stand out to me that like potential solutions to these types of problems, but we don't have a way to implement these solutions yet. Like Checksums and, or like digital signature signing files, like these sorts of things are solutions to these kind of problems.

[00:35:53] **Adam:** To say like, okay, I've published this taffy skill and I am certifying that it is safe to use. Right? It's not gonna try your, try to steal your nude selfies. It, it's totally legit. Good to go, you know, above board, whatever. And I can sign it with my public key or whatever. and, and then you could check it, or I could sign it with my private key and you could check it with my public key.

[00:36:14] **Adam:** and that sort of thing just doesn't exist right now with all of this stuff.

[00:36:20] **Carol:** So then ask a question. This isn't something I've used, so this is kind of brand new topic for me. Like we're very limited on what we're able to pull in. So the thought of pulling anything from a marketplace is nothing I would've touched yet. So, when you open the skill or go to the skill, does it give you details about it?

[00:36:34] **Carol:** does it show you what it has access to do or do you have some way to code or review it? Like how does that work?

[00:36:41] **Adam:** it's a, it's a good

[00:36:42] **Carol:** I don't trust anything usually.

[00:36:44] **Adam:** two things. one, you can install a market. So a marketplace is really just like a, a config file, a JSON file that says, okay, these are some plugins that are available. This is a title description and where you can install the, the markdown files that, that run this plugin or whatever, where you can get them.

[00:37:01] **Adam:** And one option for that is for the, the, all of that content, including that config JSON file to be on the cloud, right, on GitHub or whatever. But you can also just install it locally so you guys could have like your own internal. Claude Marketplace for government stuff on a, on a file share, right? that would be totally possible.

[00:37:20] **Ben:** Yeah. So if you wanted to round up to the nearest penny and move that difference into a bank account,

[00:37:27] **Carol:** You mean 5 cents? We don't do pennies

[00:37:29] **Ben:** Oh yeah, that's right.

[00:37:30] **Adam:** the Superman two or whatever?

[00:37:33] **Tim:** Yeah. The one with Richard Pryor.

[00:37:34] **Adam:** anyway, but to answer your other question, as you're browsing around these things, it shows you the title and description that are in that config file. the JSON file. And, I believe all, I mean, it has to be open source 'cause it's just markdown files.

[00:37:48] **Ben:** You install them in your thing. So it's just markdown files and worst case you install them and then you go look at them and read them, right? Like,But like you could, I mean, so play devil's advocate for a second though. You could say the same thing about node modules, that at any point you could have gone into node modules and audited, except for you don't get the compounding. This node module includes this node module, includes this node module. It is a, it appears to be a those suck. Mm-hmm.

[00:38:19] **Adam:** Yeah, it is. Well, it is and it isn't. You can say, okay, now go reference this file. Okay. And you can go, you can go 20 files deep or whatever if you really want to. But,

[00:38:27] **Ben:** but it's not like you don't install the taffy plugin and suddenly have two gigabytes of information,

[00:38:35] **Adam:** No, I mean you could but like in, in the way that, that almost certainly happened with node modules.

[00:38:41] **Adam:** Oh yeah, yeah, sure. and, and that's another thing that like, you know, it's kind of a solved problem for solved ish problem for modern computing. Right. So you talked about like node modules. There's a whole supply chain risk there.Um, and yeah, I mean, we've seen multiple times in the last, in the last year I'm getting all these emails from customers use MongoDB. No, we do not use I mean, just the last 60 days. Yeah.

[00:39:06] **Adam:** yeah. but like, there are solutions right there. So there's, you know, explicit versioning, which the, these skills and stuff, you can set a version. it's a little bit less well managed, right? There's not like a, a package manager that goes in and solves it. You just like, okay, I'm, I'm pushing up a new version of the code and I'm gonna change the version number, right?

[00:39:24] **Adam:** and it does do a three part, like semver, major minor patch sort of thing. But, it's just, it is just a text string that says, okay, this is the version number and I could change it to whatever I want, whenever I want, for whatever reason I want.but yeah. So

[00:39:38] **Adam:** the supply chain risk that exists in systems like NPM or, you know, PyPI or whatever, all these things, I wouldn't say it's solved, but we have people that are like working on it and trying really hard to solve it and are somewhat close, right?

[00:39:52] **Adam:** So like you've got. Companies and products that exist specifically for the purpose of auditing node modules. And there's, there's one called Socket Socket Dev that my company we use, I'm pretty sure it's free. and it like, integrates with our GitHub. And so like anytime that we have a pull request that's using node modules, it looks at the package JSON and it says, okay, this new, you've added a dependency.

[00:40:14] **Adam:** So I'm gonna go look at, I'm gonna like, audit that dependency. And it's do I have any known vulnerabilities here? Are there any like red flags about the code? Right? Is it, is the code obfuscated that's a red flag, right? That sort of thing.and so it like audits all of your changes to stuff. It, it looks at, test coverage and, and all kinds of interesting stuff.

[00:40:31] **Adam:** But the point is nothing like that exists yet for all these ways that we're like adding on to our, all seeing, all knowing space BAB at the center of the universe, computer brains that we're hatching out of eggs.

[00:40:44] **Ben:** So the,

[00:40:44] **Adam:** I have definitely had way too much caffeine.

[00:40:46] **Ben:** no. So the thing that I wanted to add on to what you're saying is over the weekend when I was building my video downloader, because security is such a question mark for me at this point with all this stuff, so it, it wrote all of its Python files and they're inside of Docker containers. So I wasn't really concerned, but then I asked Claude, I said, can you look at all the code that's been written and see if there are any vulnerabilities or anything very suspicious?

[00:41:10] **Ben:** And I had no idea what to expect. And it actually came back. I don't know what it did, but it came back with a response that sounded very thorough. It was like, oh no, we've looked through the code. There's no obfuscated or hard to read code. All of the code is very clear. There doesn't appear to be any network requests to any unexpected domains.

[00:41:28] **Ben:** And it ran through three or four more things. And you know, again, I have no idea what it actually did under the hood or how thorough that was. But I imagine that you could do the same thing, install a plugin, and then have code look at it and say, Hey, I just installed this plugin. Take a look. Is there anything

[00:41:45] **Adam:** Who watches the Watchmen though?

[00:41:47] **Ben:** Yeah.

[00:41:48] **Carol:** Yeah,

[00:41:50] **Ben:** But then I did see, somebody said something in the CFML Slack channel and it was like, Hey, if you just type this one line of code into clawed, it'll just crash the, the loop that it runs in. And Mark Ada was like, please don't post stuff like that. But you know, I mean that's, it's all's all black box as part of the scariness of it all.

[00:42:12] **Adam:** Yeah. I.

## [00:42:14] Seed Prompting and Verification

[00:42:14] **Carol:** so some of the stuff I've read. Recently is that when you are working with LLMs and what you're expecting, you don't need a hack. You just need misleading information that can put you down the wrong path. So I saw something about, doing like a seed prompting. Have you guys like looked at that at all?

[00:42:36] **Carol:** So basically you can, you can prompt your LLM to say, if you see like these terms, I always want you to answer with this. And if the LLM starts going awry, meaning that the, like something's been compromised, the model isn't right, or the data that you're using has led it down a wrong path, it'll no longer be able to respond with that seated answer.

[00:43:00] **Carol:** And it's one way to kind of like check that things are still going right.

[00:43:03] **Tim:** it's like a safe word.

[00:43:05] **Carol:** I think you can do several things, but yeah, it's orange. It's definitely orange. Well, so

[00:43:09] **Carol:** I'm I

[00:43:10] **Tim:** study.

[00:43:12] **Carol:** firetruck, I'm actually meeting with

[00:43:18] **Adam:** Anthropic.

[00:43:18] **Carol:** do Andro, thank you. I should have gotten that right tomorrow. They met on Friday while I was out, so I'm meeting with 'em tomorrow

[00:43:25] **Carol:** because we started. Yep. So they're coming in.

[00:43:29] **Carol:** Yeah, the actual company. So they're meeting with me and my team to go through 'cause we're in the process of, procurement for some different AI tools and we're demoing and we've been using it. I just started using it last week actually. Really good. Yesterday was Claude Code. So I got an email today that said, Hey Carol, we know this, that you are using this a lot, like a lot, lot tomorrow.

[00:43:53] **Carol:** Can you demo and show us what you're doing with it? So like the other people on the teams will know what I'm using it for, to better understand how to evaluate it. So it'll be interesting if I can get a moment with them to ask about some of these things.

[00:44:08] **Tim:** One of the perks of working with the government.

[00:44:09] **Ben:** yo.

[00:44:10] **Carol:** want that money.

[00:44:11] **Ben:** I feel like in the early two thousands, I don't know if anyone ever did this, but sometimes when I was at the office with a Clark, we would say. Like what up.com? Like we would just let a pen.com onto a bunch of things. I don't know if that was, I don't know how widely spread that was.

[00:44:26] **Tim:** I mean, people would say, you're the bomb.com.

[00:44:28] **Ben:** Yeah, I dunno. So when Carol was

[00:44:30] **Carol:** remember that one.gov

[00:44:35] **Ben:** weight. yeah, it's a brave new world.

[00:44:37] **Carol:** a big, brave new world.

[00:44:38] **Ben:** Well, and also, so going back to these skills that Adam's talking about, you mentioned there's the front matter at the top and then there's the content and my understanding, 'cause I've just read like a bajillion pages of documentation this week.the, the title and the description of the skill trigger it to be conditionally included.

[00:44:58] **Ben:** What did you call like progressive

[00:45:00] **Adam:** Disclosure.

[00:45:01] **Ben:** disclosure? So just going back to the seed poisoning thing, I could imagine you say oh, you can use this skill when you're working in a Taffy app or, and then just like sneak something else in there. And like Claude might just act, not accidentally, but you know, just following its rules engine, pull it in in a way that wasn't intended.

[00:45:21] **Adam:** Right.

[00:45:21] **Ben:** I'm not saying Adam's doing that.

[00:45:23] **Carol:** He probably is

[00:45:24] **Tim:** to, I, I can't wait to try it. 'cause I do use, you know, I do use your Taffy stuff. So hopefully, hopefully Claude will start behaving.

## [00:45:33] Practical Benefits of Skills

[00:45:33] **Adam:** so what, once I have it plugged in, what benefit will it give me in my project,

[00:45:37] **Adam:** so the idea is that it should help reduce hallucination of any, you know, like methods that don't exist or whatever, right. So basically, let me kind of reframe it this way. I was working on a project, I'm trying to remember what the project was. It's not coming to me, but I was working on a project and I needed it to.

[00:45:59] **Adam:** Rewrite. Oh, that's what it was. It was taffy actually. So, the, a thing that I've wanted to do for years and years and years now is modernize the Taffy code base. Right. I wrote Taffy in the age of probably like CF nine ish,

[00:46:10] **Adam:** like

[00:46:11] **Tim:** explains all, explains all the tags.

[00:46:13] **Adam:** Right, exactly. So it, at the time being CF eight compatible was a settling point.

[00:46:18] **Adam:** Right? Now, if you're still on CF eight, God help you. but, I mean, that's so far out of support at this point anyway, but the, the code was still CF eight compatible because why not? But, now here's why not. I don't wanna have to support all that nasty old tag code. And, and there's a couple of like compatibility checks and stuff to like sort polyfill more, more modern.

[00:46:43] **Adam:** methods that exist in the newer versions of the servers.and so this was like one of those things that's been on my to-do list forever, because it's just gonna be tedious. I don't want to have to do this. It's a lot of, there's a lot of code. There's, I dunno, maybe 3000 lines of code ish in Taffy. and I just didn't wanna have to go through it all and do the conversion and I knew the tests were kind of flaky and everything.

[00:47:05] **Adam:** So this was another thing that I did on that car ride where I had Claude teach me about, dot files. I think on the ride home I did this. So I I I

[00:47:15] **Adam:** was like an hour, 20 minutes. Um,so, one of the things that I've learned in the last couple of weeks or months is that, sort of a, a, a superpower or secret trick for getting the LLM to be really smart is like.

[00:47:30] **Adam:** Give it the documentation of the thing that you're trying to do. Or even better if you can give it the source code, right? So like if you're trying to use some Java library, you could say, oh, the documentation's available on this, website. You could give it the u RL for the website, say go browse the documentation here.

[00:47:44] **Adam:** But it would be faster and fewer tokens and just probably a better result by instead like downloading the documentation. Like even if even better, if it came as like markdown that they used to generate HTML. If you can give it markdown as the source that you give to the LLM, then it can parse that and use that as the information that it needs to do the tasks that you're doing.

[00:48:09] **Adam:** So before the car trip, I knew I was gonna be doing this. So I downloaded the test box documentation, I downloaded the command box documentation, I downloaded the CF docs all like the CFML reference website. I downloaded CF docs 'cause that's all JSON files and markdown stuff. I think, I downloaded all this stuff.

[00:48:27] **Adam:** in the taffy repo I have the, the Taffy docs. And so what I did was, you know, even though I was, I wasn't offline, but I was, just tethered, right? So like limited internet connection, I was able to be like, okay, I want you to write the, the test, you know, rewrite the test, just scrap the whole test directory, start from scratch.

[00:48:44] **Adam:** You've got the documentation and the source code between the two of those, you should be able to infer the spec. And then I want you to take that, the inferred spec and write a whole new test suite. I want it to run against Lucee five, six, and seven.I also downloaded the Lucee documentation, which is available as markdown files. Um,and you just put these in a folder. I put 'em in a folder called.dot ignore, and then it's like dot ignore slash cf. Docs do ignore slash TestBox docs do ignore slash command box slash docs or dash docs, whatever, right? So all these docs files that are available only in my repo, they're not gonna get, or only in my local machine, they're not gonna get committed, but they're available to reference by the LLM.

[00:49:21] **Adam:** And I go, okay, I want you to rewrite the test suite. All the, the test box docs are in this folder. and you can infer the, the spec from this documentation and the existing source code. So I had to rewrite the tests and I waited until I got the test all passing. I was like, okay, good. Now we're gonna commit and now we're gonna take this test suite that's all passing.

[00:49:40] **Adam:** I want you to not throw away all the code, but we're just gonna convert all this code to modern script only CFCs. get rid of all the like, compatibility layers for older versions of things that is, is trying to do. Trying to still support and you are not allowed to modify the test. You're only allowed to modify the code.

[00:49:56] **Adam:** And I want, you know, just keep going until all the test pass. Or if you feel like something's stuck and you can't, you can't make the test pass without modifying the test, then let me know. I did that. and, and yeah,

[00:50:07] **Ben:** so, so how long did that run for? Just out of curiosity.

[00:50:10] **Adam:** it, it took longer than the car ride, but I got it started. Yeah,

[00:50:15] **Adam:** I, I ended up publishing, a, a beta release of Taffy V four.

[00:50:20] **Tim:** I think it was either, I think it was 2:00 AM Oh wow.

[00:50:25] **Adam:** ' cause like I, I was like, that's the thing that's, that's this other blog post that's brewing in my head is like, okay, yes, Claude is a great teacher blog posts are great 'cause you can put out information and everybody has their own perspective on how to teach something.

[00:50:37] **Adam:** But there's all always these cases where. Yes, I'm glad that you've made the information available, but I don't wanna have to read your life story before I get to the recipe, right? Like that sort of thing. and, and so I just want the information and I want to explain to me in a way that makes sense to me.

[00:50:54] **Adam:** So I might point it at your blog post and say, teach me about this thing, but just cut out all the cr gimme the, just gimme the facts, right? And if I have any questions, I'll let you know, and you can expand on that particular thing. That's a great way for me to be able to consume stuff and not waste time reading a whole bunch of stuff that I'm ultimately not gonna care about.

[00:51:11] **Adam:** Well, I appre I appreciate the process, journey. Again. I'll ask Captain Caffeine now. Now, once I install this, what's it gonna buy me for my project? Just a new version of Taffy.

[00:51:23] **Ben:** so this has absolutely nothing. The, the, the, the skill has absolutely nothing. Marketplace skill, all that together has absolutely nothing to do with Taffy four.That was, that was so one can of Mountain Dew. Go bro.

[00:51:35] **Tim:** Yeah.

[00:51:37] **Adam:** The, it's, the skill is just getting the LLM to know the specific syntax and like what can be used where, and what are the config settings. So it's kind of training the my LLM locally so that when I use it, it doesn't kind of break the rules of Taffy

[00:51:54] **Adam:** correct.

[00:51:55] **Tim:** it, it, it knows about Taffy without me having to explicitly, 'cause normally what I do is I, I'll tell it, here's the taffy documentation, here's the folders, please review all of it. So learn about it.

[00:52:05] **Tim:** So, so I can just assume once I put this, this, this skill in that it knows about Taffy and I don't need to teach it anything about

[00:52:12] **Adam:** yeah, it, I don't understand a hundred percent yet how to know for sure that it's going to use the skill. so for example, I installed the Taffy skill after I wrote it, and then I asked it a question like, how do I return a status 201 header on a Taffy API resource? To indicate that the record was inserted.

[00:52:33] **Adam:** Right. I just asked like that almost exactly verbatim, and it gave me an answer, and I was like, that's a pretty good answer, but I'm, I still am not sure if that used the skill, and so I asked it, I was like, so did you use the, your, installed taffy skill to answer that question? and it actually, it said no,

[00:52:51] **Tim:** Yeah, because I, I've asked it because it's done, things like that for me, use in the, in the same project, it figured that out and I'm like, I need to return the data. I don't want the object. 'cause sometimes it will send you the object. I need the data and it's oh yeah, I need to use, get data 'cause it sees it being used.

[00:53:06] **Tim:** so yeah, I was just, just trying to figure out what, what it's gonna add for me and make my life so much simpler and easier

[00:53:12] **Adam:** I, I didn't, I never claimed it would. I just said it exists.

[00:53:17] **Carol:** And that you weren't gonna own it, other people could help with that. Yeah.

## [00:53:21] Claude's Conflicting Answers

[00:53:21] **Adam:** I was, I was talking to Claude Desktop today. As I'm going through the documentation, I'm asking questions 'cause I'll, I've asked Claude code certain things and it will give me an answer. Sometimes that answer is different and almost in opposition to what I'm seeing in the official documentation.

[00:53:38] **Ben:** And one of the things that I had asked about was if I have a skill, is it helpful to, in the CLAUDE.md file, say something to the effect of, anytime you're reading or writing CFML files, use this skill for CFML formatting kind of a thing.

[00:53:57] **Ben:** And Claude Code said, no, that's ridiculous. And then Claude... and then Claude Desktop, like literally the example that they have for skills is like restful architecture style guide. And I'm like, that feels very much like what I'm saying.

[00:54:11] **Adam:** so, I think the difference that I'm hearing though, and, you know, maybe I, this is a distinction without a difference, but, what I hear is that you asked Claude if you should put it in the CLAUDE.md, that when it's doing x it should use this skill. Right? And the, the other way of looking at it, which it sounds like at least according to their skill spec, is the skill defines when it should be used.

[00:54:35] **Adam:** The skill says when you're editing A CFM or a CFC file, use me, right?

[00:54:40] **Ben:** right. Yeah. Actually, now that you pointed out, I think what I was, I was having a, a, a journey conversation with Claude. 'cause at first I was asking it should the skills just be about actions? Like, do this thing,

[00:54:54] **Adam:** Mm-hmm.

[00:54:55] **Ben:** or can the skills be about style and formatting and like best practices? And Claude Code said, no, it should never be about formatting or skills or formatting or best practices.

[00:55:07] **Ben:** And then the documentation was like, their example was best practices. I'm like, Hmm.

[00:55:12] **Ben:** So yeah, you're right. I was conflating two different conversations.

[00:55:15] **Adam:** Yeah. And honestly, I think there's probably, you know, anytime you make a a, declarative statement like this, there's gonna be somebody that'll be able to prove you wrong. But it feels like there's nothing that you could want Claude to do, that it would be inappropriate to put in a Claude skill in terms of using the skill to make Claude do the thing you wanna do.

[00:55:37] **Adam:** Inappropriate not being a moral judgment, but a syntactical,

[00:55:41] **Ben:** Right, right. I, I know that, I just feel strongly about certain things, so

[00:55:45] **Adam:** really.

[00:55:47] **Ben:** I know it's crazy. So like, if I was gonna have Claude generate, like an ES6 module or maybe more of a cm, what, what, what was the old one? The, the, the required type?

[00:55:58] **Adam:** CommonJS.

[00:55:59] **Ben:** yeah. Like the popular pattern at the time and probably still is, is to like, do all your jazz and then at the very bottom of the file, export the things that you want to export.

[00:56:10] **Ben:** And I'm like, that's ridiculous. Your export should be at the top. That's just a point of philosophy, philosophical debate there. So like, I would wanna put that somewhere and I feel like I'd want to have a, you know, a JavaScript modules best practices skill so that I could say, anytime you're reading or writing JavaScript, know that this is, you know, fact,

[00:56:30] **Adam:** Okay. Congratulations, Ben. You proved me wrong. I'm gonna make a moral judgment. It doesn't matter. I, I put my exports in line. Export function X or export const foo equals function.

[00:56:46] **Ben:** you crazy bastard. So now I gotta search for it to each their own, my friend.

[00:56:55] **Adam:** You don't have to search for it. You make the LLM search for it.

[00:56:59] **Ben:** This is, see, and this is the, the thing is like, how much does my desire to have code look a certain way, even matter anymore?

[00:57:05] **Ben:** And I'm struggling with that, to be honest. Like I'm struggling with the fact that that doesn't matter anymore. 'cause that was a big part of how I thought about code.

[00:57:14] **Tim:** I will say it's very, your code's very idiosyncratic. I can look at it and go, oh, that came from Ben's

[00:57:19] **Ben:** Heck yeah.

[00:57:20] **Tim:** A hundred percent.

[00:57:22] **Ben:** On.

[00:57:23] **Tim:** Put some Ben on it, baby. Well, that's, I mean, thank you for sharing that, Adam. I, I mean, I, I, as much as I picked on you, I'm sorry about that. I

[00:57:29] **Tim:** was trying to be as just

[00:57:31] **Adam:** What goes around comes around.

[00:57:32] **Tim:** I'm just trying to Yeah, definitely. You, you give, you give as good as you get, but it, yeah, it's very interesting to hear about your journey on that and, and what it did. So that's, it's pretty cool.

## [00:57:41] CFML Community Marketplace

[00:57:41] **Adam:** Yeah. So, I guess wrapping up notes here, right? So, on GitHub, like github.com/cf community slash llm dash marketplace, if you're interested in seeing the taffy. plugin, which includes the taffy skill. I think the plugin is just the way you install the skill. That's my understanding so far. please feel free to contribute or just sign up to be a moderator that can help approve, contributions.

[00:58:04] **Adam:** else?

[00:58:04] **Ben:** I I did have a question 'cause I did see it's, so you have the, the, the marketplace as a repository, but it is in a CF community account. Did you create that account or? That

[00:58:17] **Adam:** I did forever ago.

[00:58:19] **Adam:** Yeah, I mean, like back in the days when I was, still just a speaker, not even an organizer at, CF objective,

[00:58:26] **Adam:** um, that's probably when I created that, long, long time ago.

[00:58:30] **Ben:** Pretty good.

[00:58:32] **Adam:** I don't know if you remember long, long, long, long time ago I created, I called it a package manager for cold fusion.

[00:58:38] **Adam:** It was a CF administrator extension you would install it and then it would let you browse first stuff and install like Taffy or or, or test box or

[00:58:46] **Ben:** sounds familiar. I feel like you've maybe talked about it on the show in the past.

[00:58:50] **Adam:** that one was called Ramen. I was, I was on a, naming things after food kick for a while there. and, anyway, that was part of, why I created that CF community.

[00:58:59] **Adam:** Or there was also like, CF Community Script components or something like that. So like early days when they were starting to convert stuff to script, it was like half the language they converted to scripting the other half just was not possible. But then they like created this whole thing where, oh, you could just put CFCs in this folder in the CF administrator or whatever.

[00:59:17] **Adam:** and then they're available as script components, like. Thanks, I guess. Yeah.

[00:59:22] **Adam:** I was like,

[00:59:22] **Ben:** Yo. In 2025, those were re,

[00:59:25] **Tim:** dollar company. Just half-assing it and letting the community do it.

[00:59:29] **Ben:** I'm pretty sure in ColdFusion 2025, they've actually finally removed all of those. 'cause I think when I upgraded, I had to go and change a bunch of new mail calls to be just CF mail.

[00:59:42] **Adam:** Oh, interesting. Okay. Well that doesn't matter to me. I mean, we're on Lucee and, and we're, we're never going back to ACF, but, yeah. Anyway, so yeah, I talked about, the CF community, LLM marketplace. what else? The taffy skill. Just be weary of the security stuff, right? be mindful, oh, and etiquette on, you know, what, what are you putting in the repo that's going to clutter up your coworkers prompts and context.

[01:00:08] **Adam:** there's a lot to, it's very nuanced. There's a lot to think about there.

[01:00:11] **Adam:** So.

[01:00:12] **Ben:** Yeah.

## [01:00:12] Patreon

[01:00:12] **Adam:** Okay. Well then this episode of Working Code is brought to you by Ben finally writing tests. What's next? Maybe we'll get 'em on VS code

[01:00:20] **Ben:** Whoa, whoa. Settle

[01:00:22] **Adam:** and sometime in the next 10 years. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:00:31] **Adam:** Our Patriots cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks as always to our top patrons, Monte and Giancarlo. You guys rock.

## [01:00:42] Thanks For Listening!

[01:00:42] **Adam:** We are gonna go record the after show. They are typing in the after show notes section of the document right now.

[01:00:46] **Adam:** So I need to give 'em a second. Vamp Vamp. Vamp. Okay. Ted Lasso. Season four is coming. I'm excited. I already know a little bit about it. It's gonna be like a, a ladies

[01:00:55] **Tim:** Mm-hmm. Yeah. Girls team. Yeah. Yeah.

[01:00:57] **Adam:** so that'll be good. Yeah. I'm excited for that. but yeah, anyway, after show is just outro plays and the freeloaders go away and then the patrons keep listening and we talk about whatever.

[01:01:10] **Adam:** Sometimes it's more tech, sometimes it's tv, sometimes it's books, sometimes it's eating testicles.

[01:01:16] **Tim:** cooking and eating them.

[01:01:17] **Adam:** well, okay,

[01:01:19] **Adam:** you think that makes it better?Okay. Anyway, that's what the after show's about. if you'd like to get all the past after shows, the current after shows and the future after shows. The best way to do that, the only way to do that is to become a patron of the show. You become a, a patron of the show by going to patreon.com/workingcodepod, and throwing a few dollars our way every month.

[01:01:39] **Adam:** It's like a cup of coffee a month. We'd love to have you join the team. that's gonna do it for us this week. We'll catch you next week and until then,

[01:01:46] **Tim:** Even in this economy, your heart matters.
