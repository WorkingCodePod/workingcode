---
title: "241: Welcoming Our New Robot Overlords"
description: "How do you teach an LLM to write code you can actually trust? Carol's federal government team has been tasked with exploring unattended AI code generation."
date: 2025-12-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/241-welcoming-our-new-robot-overlords/id1544142288?i=1000739974016"></iframe>

How do you teach an LLM to write code you can actually trust? Carol's federal government team has been tasked with exploring unattended AI code generation, so she came to Adam and Tim for advice. Their first piece of guidance: whatever tools you pick today will be obsolete by the time you're done evaluating them. The real goal isn't adopting a specific workflow—it's building the skills to ride the wave.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/241-welcoming-our-new-robot-overlords.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** It's like, giving somebody all three of the first, star Wars books and saying, read all of these. And then when you're done reading them, you ask, okay, what color are Luke Skywalker's eyes? Right? you, it's way too much context for the thing that you're, you're gonna actually want as a result

## [00:00:33] Intro

[00:00:33] **Adam:** Okay. Here we go. It is show number 241, and on today's show we're gonna talk about welcoming our new robot overlords. But first, as usual, we'll start with the triumphs and fails. Ben has an excuse to absence tonight. It's his turn for a week off, I suppose. And Tim, I'm gonna come to you first.

[00:00:46] **Adam:** What's going on, my friend? Mm-hmm.

## [00:00:48] Tim's Fail

[00:00:48] **Tim:** So I'm gonna go with a fail this time. it's not really a failure. I just kind of find it kind of funny. So, you know, every year Spotify does a Spotify rap where they take throughout your past year all the music you listen to and they kinda roll it up into this nice little video slideshow presentation.

[00:01:06] **Tim:** Well, they tell you what your, your listening age is based off the music that you listen to, kind of what they think your listening age is.

[00:01:13] **Tim:** what do you guys think my age would be? So I'm 54 in real life.

[00:01:17] **Adam:** Okay. That's helpful. Thank you. Based on what kind of, well, based on what kind of music I think you listen to. I would say like maybe 50 instead of 54.

[00:01:26] **Tim:** You're very, very close. It was 49. 'cause I listen to a lot of nineties music. So a lot of stuff. Which

[00:01:32] **Adam:** say by the bell theme.

[00:01:34] **Tim:** what's your, what's your age, Carol? I can't see it. It's

[00:01:36] **Carol:** it says 23.

[00:01:38] **Tim:** 23. Well, that's how old you are, right?

[00:01:41] **Carol:** Yeah, definitely.

[00:01:42] **Carol:** My kid didn't just turn 24.

[00:01:45] **Tim:** Yeah. So, but it's funny. So my, my sister-in-law, hers was 70 for some reason. I guess she listens to lots of Nina Simone or something.

[00:01:52] **Tim:** I, I don't know.

[00:01:53] **Adam:** I dunno who that is. Yeah.

[00:01:55] **Tim:** like an old jazz singer, but, uh,

[00:01:57] **Carol:** not. You are not 70.

[00:01:59] **Adam:** Yeah.

[00:01:59] **Carol:** You wouldn't know.

[00:02:00] **Tim:** exactly. So yeah, I was, I was like, I, I don't know if that's really a tri or I feel like it's a fail 'cause it's like my musical knowledge. I was like super, super into music when I was single and I was dating. When we first got married, very, very loved music.

[00:02:15] **Tim:** It was like my whole personality revolved around, you know, what bands I was into at the time, and then you have kids,

[00:02:21] **Adam:** Yeah.

[00:02:22] **Tim:** and then it's all my musical knowledge from when the kids before the, you know, when the kids from were like little, little to like high school, just all my musical knowledge went out the window and so I just got stuck listening to the same stuff over and over again.

[00:02:35] **Adam:** I, I don't know how true this is. I've heard a theory that like when the, the years that are your personal, like formative years, like that particular phase you were in high school where you kind of like graduated from child to young adult. if you are the type of person that listens to a lot of music.

[00:02:51] **Adam:** Then whatever music you were listening to at that time tends to be what you gravitate to for the rest of your life. And that, so the, that's in like your formative music. And so, whatever's popular when you're that age, I feel like is, is likely to be what you carry through the rest of your life.

[00:03:07] **Tim:** Yeah. You see all these videos, like people talk about our generation's music was the best. I don't think I've ever seen one where people are like, yeah, our generation's music sucked, and no one ever says that. Right? So I think it's very, very selective. Like it was very specific to you and your time. And how I know I'm getting old is like when I go to the grocery store, I'm like, every time I'm like, oh my God, I haven't heard this song in years.

[00:03:31] **Tim:** So, so someone, someone has picked that, they're like, okay, you're the prime shopping age at this grocery store. We're gonna play your music for you over and over again.

[00:03:40] **Adam:** man. I don't know about what he would say if it was, if his generation's music was bad, but. I had a buddy, he died a few years back. He was in his eighties when he died. And, until the day he died, he was listening to like heavy metal, you know, Metallica and, guns N Roses and, and Pantera and just like all kinds of heavy stuff.

[00:03:59] **Tim:** interested. I

[00:04:00] **Adam:** out of his era.

[00:04:01] **Tim:** I wanna say my father-in-law's age is, 'cause he's like 84. He listens to like all the new, he knows, I mean he was explaining Kendrick Lamar to me and I'm like, really? You're an 84-year-old Englishman. What, what do you do? What do what's going on here?

[00:04:18] **Adam:** That's awesome.

[00:04:19] **Tim:** It's pretty awesome, but it's also weird.

[00:04:21] **Tim:** So anyway, that's my fail try. I don't care it that, that's just a data point in my life.

[00:04:26] **Adam:** There you go.

[00:04:27] **Tim:** But you, Adam.

## [00:04:28] Adam's Triumph

[00:04:28] **Adam:** I'm gonna go with, I'm gonna call it a triumph. so for officially the first time in my life, I now have a direct report. the freedom to start structuring what I'm gonna call like some actual true engineering management practices. There's sort of things that, for some of these things I've had in my career, but at my current position, I have not had any of these things.

[00:04:48] **Adam:** So, and you know, there's more to come, these are just like top of mind for me, which is like a true, written, published career ladder, regularly scheduled one-on-one meetings, regularly scheduled performance reviews. These are things that like, you know, are quote unquote best practices for engineering management that have, I've had regularly scheduled performance reviews at most of my jobs.

[00:05:08] **Adam:** This one not so much. But, the other stuff that I mentioned never had in my entire career. I guess I've had, I don't think they called it a career ladder back when I was getting started. 'cause I, you know, I am, I am a, a, what are they? Not quite an old, but I am older than a young.and so I, I've been in the industry for a

[00:05:27] **Tim:** that middle age my friend.

[00:05:29] **Adam:** Yeah, I guess they do. so, yeah, so, you know, they had job descriptions and, and it was clearly written out a a, an entry level programmer does this, a a programmer level two does this, a senior programmer does this, a architect does this, whatever. but yeah, anyway, so I, I get to be the person to drive that process.

[00:05:46] **Adam:** I have the freedom to make it happen. 'cause it just, I guess it was, you know, when, when it was just me and Steve, you know, a it didn't really matter that much. I was, you know, I'm just the other guy. and b you know, as we grew, he didn't have the, the bandwidth to do stuff like that. He was busy, you know, doing sales and, running HR and accounts payable and accounts receivable and everything else.

[00:06:10] **Adam:** So get to actually kind of. Solidified that, that's not the word I was thinking of, but whatever. Get to Crystalize. No, I don't know. Whatever we, to make this stuff happen.

[00:06:19] **Tim:** Welcome to my world, buddy.

[00:06:21] **Adam:** Not being able to think of the word.

[00:06:23] **Tim:** No, the, the world of doing all that kind of stuff. That's, that's, yeah, that's, I've been doing that for years.

[00:06:28] **Tim:** So, yeah, I'm excited about it. it, it's gonna be fun and interesting. So, It'll be new. That's for sure.

[00:06:33] **Adam:** you know, honestly, I think it will be fun for me. You know, me, I'm, I'm all about ambition. challenging myself with new stuff. I have so many hobbies. I, I've had so many hobbies throughout my life that I've just had to like, choose, okay, I have too many expensive hobbies.

[00:06:46] **Adam:** I gotta pick which ones I'm gonna continue and, and just stop doing some of these other things. I still have a guitar or two behind me. and that's just because I haven't bothered to sell them. I don't, I haven't played guitar in I don't know, 15 years. they don't have a better place to sit, so that's where they go.

[00:07:01] **Adam:** look cool.

[00:07:02] **Adam:** yeah,

[00:07:03] **Carol:** say, yeah, they're good decor.

[00:07:05] **Adam:** Yeah. So,

[00:07:06] **Carol:** Well, I just wanna add with the, with the mentoring thing and with the actually being over someone, I always enjoy the teaching and growing them. I hate the paperwork side of it though, so I enjoy my role now 'cause I get to spend a lot of time helping and just guiding and, you know, participating in someone's growth, but someone else gets to fill out the paperwork.

[00:07:27] **Adam:** Yeah. So, we are coming up on the Christmas, holiday break here. So I've got my copy of Engineering Management for the Rest of Us by Sarah Drasner that I'm planning on rereading over the break. and I, I need to, I know I have a bunch of bookmarks saved, for engineering management stuff that I've just come across over the last several years, and I was like, I'm gonna want this one day.

[00:07:46] **Adam:** So I know I bookmarked it. I just need to go back and find all that stuff and read it again.so that's, that's me. I'm looking forward to sort of this next chapter of my life opening up. So.

[00:07:55] **Carol:** Awesome.

[00:07:56] **Adam:** so like I said earlier, Ben is out this evening excused absence, which means Carol coming to you. What do you got

## [00:08:02] Carol's Triumph

[00:08:02] **Carol:** Hey guys. Yeah. So I'm gonna call this a big win. we have legacy code, we have new code. Like we have a lot of code, I mean just a lot of code for my team. And we had the, I'm gonna butcher this 'cause I butchered it for a week now because Sha Ude, I think is how you say it. and apparently it's a reference to a movie that I have never seen.

[00:08:25] **Carol:** So

[00:08:27] **Carol:** Yeah.

[00:08:27] **Carol:** there's a desert and that's all I know. So the, these attacks came out and, luckily for us, our packages are pinned so we don't have to deal with some of this. And we do go through some extra security. Like our packages are pulled into a proxy anyway, so it's not like we're going directly to NPM.

[00:08:44] **Carol:** So, it's all really, really. Pretty fancy with how we've done things. And I'm happy to report, like we had no incident and nothing happened on our side, but it did prompt me to start doing some digging and find out if something were to hit us, how would I know? do I have to be reliant on a scanning tool that cyber has to report to me, or is there a way I can find some of these upfront and once it happens, how do I respond to it?

[00:09:13] **Carol:** So I spent a few hours and wrote just a couple PowerShell scripts that do a few things. the first one just clones every repository for my org. So we are divided like organizations are by basically projects and teams. So my org has, you know, 40 something repos in it, but the other orgs are smaller or larger depending on what they do in the division.

[00:09:35] **Carol:** So I wrote something, it would just go clone every repo we have and if I had code, it would stash it and then it would check out main and pull. And then I wrote another PowerShell script that goes through and just pulls in the CSV file from the Wiz findings. For that, the list of all of the NPM packages hit, which I think was over 800 today, the last time I looked like it's a lot of packages.

[00:09:56] **Carol:** So it pulls that in, CSVs it, and then loops through my package.json files and finds any reference I have to any of those and lets me know if I should go look at anything. But then on top of that, I did a recursive look to find out if the, I have the GitHub action that was also being created, which is like discussions.yaml, right?

[00:10:14] **Carol:** Those GitHub actions. And then there was a couple other things I found where it was like creating files and looking like at .env.json and your variables.json. So I wrote just a PowerShell script that just does a recursive look on that and returns back whether. I have any findings or not, and gives me a quick little view.

[00:10:33] **Carol:** So I was super happy that I've got that out there now, and when something comes up, I can just point it basically to a new CSV source for where we're being hit from. And all of a sudden I'm like, eh, we're still good. We're still not looking too red. So I was super happy about that. And then today I also saw the, react hit, right?

[00:10:52] **Carol:** So React gets hit and I'm, I'm going, oh my God. I just get through one like review and now what's going on.

[00:11:00] **Adam:** this is the one that's like react. There's a vulnerability in React server components,

[00:11:03] **Carol:** Yeah. Yep. And next

[00:11:05] **Tim:** before we move on to the React, so I'm not familiar with the Socket supply chain attack, so I had to look up, so this is for Node.js packages, the NPM system.

[00:11:14] **Carol:** Yeah, the NPM system, so a bunch of keys and stuff were taken, and packages, like 200 new packages have been pushed since they were thinking it might be kind of getting closed. Like 200 new packages have been pushed up. So they have access to keys and secrets. And if you were doing get latest, you got a problem if you didn't pin your version.

[00:11:35] **Tim:** so, so these, so these people compromise existing legitimate packages that were out there, that people are

[00:11:40] **Carol:** absolutely. Postman.

[00:11:42] **Tim:** Oh, really? Wow.

[00:11:44] **Adam:** Yeah.

[00:11:44] **Carol:** postman, yeah. There's a lot of

[00:11:46] **Adam:** several really, legitimate big packages got compromised,

[00:11:50] **Tim:** So if you pull that down and run it, it's gonna basically, that's, that's why it's a

[00:11:54] **Adam:** so you didn't have to really do anything to run it. It was, uh, so NPM packages have, lifecycle hooks in them, and there's like pre-installed post install. So things that'll just automatically run because you installed it. it'll, you can say, well, and that's very useful for legitimate things too, right?

[00:12:09] **Adam:** you know, run a script that CES something or whatever that's useful when you install it sort of thing.and so they, they took advantage of that. They put in like code that runs in the pre, or they said pre-install. And the thing I read it would make more sense for post-install to me. I don't know, whatever.

[00:12:24] **Adam:** But they put, they put something into a lifecycle hook.

[00:12:26] **Tim:** as well,

[00:12:28] **Adam:** so they put something into a lifecycle hook that like, okay, you've, you've installed this, Affected package. And so it looks for secrets on your machine, and if it finds any, it tries to a exploit them. okay, I, I now have NPM access tokens.

[00:12:44] **Adam:** What can I do with that? I'm gonna find all the NPM packages that I can publish to with this and publish a new version of the NPM package that I can publish to with the same, exploit added into that package. So it's, it's warming,

[00:12:57] **Carol:** now

[00:12:57] **Tim:** that's how it

[00:12:58] **Carol:** Yep, they sure

[00:12:59] **Adam:** And then in addition to that, it was doing other stuff, like finding other environment secrets and stuff.

[00:13:04] **Adam:** And it would just, if you, if it had, if it could find get credentials, it would create a new GitHub repo, a public repo in your organization or your personal account with, with your secrets in it and just publish it public. And they were, I guess, monitoring and it always had the same name, I think.

[00:13:19] **Adam:** So they were just monitoring

[00:13:20] **Carol:** had the same ones over and over. Mm-hmm.

[00:13:22] **Adam:** Yeah, they were just monitoring for these repos to appear and okay, here's, here's another set of secrets I can have

[00:13:27] **Carol:** Yep.

[00:13:27] **Tim:** Wow. People are so clever.

[00:13:29] **Adam:** Yeah. So,

[00:13:31] **Carol:** it, it was nuts. So yeah, so I wrote something to scam for all of those, created repos and created folders and the GitHub actions that were being created as discussions and stuff like that.

[00:13:41] **Tim:** Cool.

[00:13:41] **Adam:** So you said something about React server components too.

[00:13:43] **Carol:** Oh yeah. Yeah. So I saw the React stuff today and I was like, oh my gosh. We just get through one of me being like, oh, I can breathe and now another one comes out 'cause we have React.

[00:13:52] **Carol:** And I'm like, oh, what's going on? I was like, thank goodness I don't think anything's using next, but now let's go dive into it. And I messaged my supervisor and I said, thank goodness we haven't been using this app for a while, because it's still on version 18 dot something. And I was like, 19 was what got hit.

[00:14:08] **Carol:** So I'm like, oh. I was like, we don't have to patch anything, but we should look at patching that after this is now done.

[00:14:16] **Adam:** Right. That's great. we had a conversation in our, working code discord. You can go to workingcode.dev/discord to join. I was having a conversation there with some of. Community members and talking about that exact same thing. We are similar situation, Carol. We have React apps that are just so old that, you know, we have React apps that predate the existence of Next.js that we haven't upgraded beyond that.

[00:14:37] **Adam:** and we're talking about how, we're just lucky that we didn't get hit and, and I think it was Brian, one of our patrons and, and a community member and anyway, all around good guy. who he was like, yeah, instead of security by obscurity, that's security by antiquity.

[00:14:53] **Tim:** Yep.

[00:14:54] **Adam:** I love that.

[00:14:54] **Adam:** That's so great.

[00:14:55] **Carol:** Yeah, I have to use that one.

[00:14:58] **Tim:** Not too many people are writing Perl scripts, you know, Perl hacks these days. So yeah, if you run Perl, you're probably okay. Or COBOL.

[00:15:05] **Adam:** That's what they used to say about Macs, but now Macs hear viruses too.

## [00:15:08] Carol's AI Mandate

[00:15:08] **Tim:** Yeah,

[00:15:09] **Adam:** anyway, shall we move on to our topic for the day?

[00:15:12] **Carol:** Let's do it.

[00:15:13] **Adam:** so I, you know, I mentioned at the top of the show welcoming our new robot overlords. Really, I think what we're talking about today is, Carol, you've received a mandate that you have to move in the direction of like entirely unattended code generation.

[00:15:27] **Carol:** Yeah. It's, yeah, it's something, something along those lines. It's not fully the mandate, it's more of a discovery phase to see what it would take for us to get there. so if we say this is the end goal, and we say the end goal is fully agent to code, so I give it, A task or an a DO story, right? So we give it a technical story, a, a feature, whatever we feed it in.

[00:15:50] **Carol:** Do we have the ability to then have the LLM create what we want and be able to trust it? And what would it take to get there? And when I started having the conversations, I knew you were using Cursor, so I was like, oh, this is my chance to go get free advice from Adam and, you know, not have to pay a consultant for it.

[00:16:11] **Carol:** So I figured we could chat through that some.

[00:16:13] **Adam:** and Tim uses Claude Code too, right?

[00:16:15] **Carol:** Yeah,

[00:16:15] **Tim:** yeah, I do. So not using it fully ally, not like I'm giving it ticket numbers to run stuff, but it

[00:16:21] **Adam:** Yeah.

[00:16:22] **Tim:** Yeah.

[00:16:23] **Adam:** So, sure. I mean, you said you wanted to come to us for advice. So the, the very first piece of advice I want to offer is that this is gonna be a moving target. Yeah. Second piece of advice I wanna offer is, this is gonna be a moving target, right? So we can talk about things, we can come up with ideas, and, you know, you, like you said, this is gonna be, this is a discovery phase.

[00:16:39] **Adam:** And, and so because of that, it's gonna be at least a year until you get to, you know, somewhat close to this end goal that they're saying you should think about. And I think that by, by the time you get there, any tools that you would've identified at this phase where you are now, we'll probably be obsolete by then, right?

[00:16:57] **Adam:** They're dropping new models like every three weeks now,

[00:17:00] **Carol:** yeah, that's one of the, one of the engineers on another team. 'cause we have this tiger team to do it. Right? So we pulled some people together, some big brains and said, let's go, let's go tackle this. Right? So one of the other guys he mentioned that he was like, I just wanna go into this saying that whatever we do in three months isn't gonna be the same as what we're doing right now.

[00:17:18] **Carol:** this is growing very fast and things are rapidly changing and we just need to kind of understand that whatever we decide on has to be very flexible and can't be like a written in stone. This is how you do it. Because it's not gonna be supported in, you know, three months, six months, a year out. It'll be like you said, obs.

[00:17:36] **Adam:** Yeah. So I mean, I think to that end, the goal really shouldn't be like to be using, you know, unintended code generation, but maybe more like to have the staff that have the skills to use unintended code generation

[00:17:51] **Tim:** I, I almost, I almost sort of frame it the same way. Like when a customer comes to me with, they're like, Hey, can you make this thing, do this? Right? The first thing I ask is, what problem are you trying to solve?

[00:18:01] **Adam:** Yeah.

[00:18:02] **Tim:** What, what, what are you trying? Because a lot of times people have in their mind, here's the thing we need to do, and they're like, go see if we can do it.

[00:18:08] **Tim:** Well, the bigger question is, I, I mean, I know why corporate America is, is telling us we need to do this, but I want to know, kind of know you work for the government, so what's the rationale? What are they saying that their objective in doing this is, what are they

[00:18:21] **Tim:**

[00:18:21] **Carol:** just. Increased productivity and better use of what we have available at our fingertips. So typically, if you think of anything written like development wise by the government, you think of anxious, you think of not supported, you think very old. Everything takes so, so long to get out and they're trying to change.

[00:18:41] **Carol:** Yeah, basically. But they're trying to change that mindset a bit and trying to bring in better talent. And you only bring in better talent for your engineering staff if you're moving with current technology. No one wants to come in and be stuck writing VB.NET because they can't convert to C# because it's still not yet approved for government use.

[00:19:00] **Carol:** And that's not a true use case, but I'm just saying you know, you get stuck. Yeah. It's a hypothetical for sure. So you get stuck in this pattern of, of, I hate to say it, but you get some really just okay engineers coming in to do work because. That's what it takes to support just Okay. Software, and they're trying to get out of that.

[00:19:21] **Carol:** They're trying to move us into a, a future that is a lot brighter when it comes to the technology that we're doing.

[00:19:28] **Adam:** That's a good goal.

[00:19:29] **Carol:** Yeah.

[00:19:30] **Tim:** surprisingly, forward looking for

[00:19:33] **Adam:** Yeah. I just expected it to be like, we wanna get all the same work done with zero staff. Pay nobody.

[00:19:38] **Carol:** Nope,

[00:19:38] **Tim:** that's, that's what corporate America is trying to do.

[00:19:40] **Adam:** Yeah.

[00:19:41] **Carol:** it's actually been the opposite. It's been a let's do cost analysis on what new tools will look like. Like let's, let's actually look at what a budget would be. Do we need to bring people in to do training? is the issue the staff we have, do we need to make staff adjustments? They, I feel like they are taking it at a complete different approach than past have done.

[00:20:04] **Carol:** When you're talking about federal product and federal work things. Yeah.

[00:20:08] **Adam:** That's cool.

## [00:20:10] Planning and Agents.md

[00:20:10] **Carol:** So one of the things I wanted to ask you about Cursor and Claude, if you're using it, so are you guys using the plan feature? Like, are you, you're you're going through and, um, so by planning, like what I've found so far is I, I'm doing two things.

[00:20:23] **Carol:** I'm feeding in the current like story as it's written and the ac and seeing what happens. Then I have another time, I'll go spin up almost the exact same thing, but I've built an agent and I built the agent using, what it's learned from my system that I've, I've fed through so far. And I go, okay, using this agent with better story information and more defined specs, what kind of information do I get?

[00:20:50] **Carol:** And if I give it no agent at all and I just give it a prompt to go do it, the code It is the worst thing in the world.

[00:20:59] **Adam:** when you say an agent, are you talking about agents.md, or is

[00:21:02] **Carol:** Yeah. Agents. Yeah. Agents. md. And every time I like end the session, I have started going, okay, now update agents with what you've learned during this session about this specific area. Like we're talking about how you tag something. I'm like, go update how you tag. Because today I was like, just go retire some tags.

[00:21:22] **Carol:** It tried creating an entire retire system to do it. And I'm like, we already have a retire system. Go learn it. Go find out how we retire data. And that's what I want you to use. And now that you understand it, I want you to document it and I want you to put it in your agents.md, right? And I want you to be able to reference back to that.

[00:21:41] **Adam:** yeah. That was a, I think Tim, you shared a link, if I'm not mistaken, that, there was a, a, a nice article we saw recently about optimizing your agents, that md and one of the things, one of the takeaways in there was like, actually shorter is better. So you really wanna like distill and distill and distill, make it clear, but also as terse as possible because it a, it does consume, you know, input tokens for every request you're making.

[00:22:05] **Adam:** But then also, The more information that's in there, like the more instructions you're giving it, the less likely it is to sort of remember that as it's going through and, and following the instructions. It's almost counterintuitive, but

[00:22:18] **Tim:** Yeah. And, and so in the Claude, so I use the Claude.md for, for this to say, you know, one of the things is like a core belief section that says incremental progress over big changes.

[00:22:31] **Adam:** Hmm.

[00:22:31] **Tim:** I want, so I would, I have the, the AI kind of do stuff. I, I don't try to give it everything all at once. I kind of give it incremental, then have it improve itself and then write its own documentation, create an MD file that basically summarizes its learnings.

[00:22:45] **Tim:** I review that and go, okay, that sounds, take some stuff out, add some stuff. Then re iteratively kind of add it. more time consuming. But I think, like you said, if you just say, Hey, go do this, it's, a lot of times the results are less than optimal.

[00:23:00] **Adam:** Also from that same article, one of the things that I took away from that, that I, that I don't know how I've, I haven't used my cursor stuff too much since this change, but I liked the concept, so I'm, I'm trying it, like we talked about, you can have too much context in there, right?

[00:23:13] **Adam:** And actually, I like this metaphor. It's like, giving somebody all three of the first, star Wars books and saying, read all of these. And then when you're done reading them, you ask, okay, what color are Luke Skywalker's eyes? Right? you, it's way too much context for the thing that you're, you're gonna actually want as a result.

[00:23:30] **Adam:** So you gotta try to like, just give relevant information. And so as a result of that, it's like, yes, you wanna have these things available in your agent's file. You wanna know, okay, this is the project structure and these are the tools that already exist, right? This is how we've retire tags or whatever. But you want to maybe have those as separate markdown files and then list what other files are available to have additional context and why you might wanna pull that in. this is, this file has project structure information, this file has this, and that way you kind of condense and let it say, okay, well in this case I don't care about, retiring data, so I'm not gonna pull that file in his context.

[00:24:04] **Adam:** Interesting. So I think, I think I was going about it. Slightly different with how I was building my agents, because I was thinking about a role or a job being accomplished. So I had an agent, have an agent created for API development, which is very focused on where the API code lives and what we're doing for auth and how we test things.

[00:24:26] **Carol:** And then I had one for database changes, whether they be migrations through Entity Framework, or they were straight SQL updates that could be added to the folder as well. And then there was one, I think I started for UI, but I didn't go very far with it. So I, I've kind of stopped there. So I was thinking I broke them out by roles.

[00:24:44] **Carol:** So depending on what type of work was coming through, someone would be able to use that agent. But it sounds like maybe I should do it slightly different by system area.

[00:24:53] **Adam:** That might be a really interesting and, and insightful way to organize the information, though I haven't seen that suggested. And it, you know, a similar I was gonna ask you, you say you've got all these different agents, which implies different files.

[00:25:06] **Adam:** My understanding is you have one file, it's called agents.md with that name, and, and it gets sucked in automatically for every agentic request that you make

[00:25:17] **Tim:** For, for cursor.

[00:25:18] **Adam:** for Cursor.

[00:25:19] **Adam:** Yeah. And, and most IDEs that have this AI stuff built in, they're specifically looking for agents md I know Claude uses Claude md. I'm pretty sure Claude will also use agents that MD if Claude, if Claude MD doesn't exist. But anyway,so Carol, are, are you saying that you have these different files and you just swap in whichever one you wanted to use?

[00:25:37] **Carol:** I've been pointing for, now I've been telling it which one I wanted to reference, like I'm doing it in the prompt itself. But the way it generated with Codex was through like a, agent folder. It was like agent, and then it had Claude and then it had the different ones in there and it seemed to kind of pick them up pretty seamlessly without me having to do much work.

[00:25:58] **Carol:** So I don't know if it's just because my prompt includes which one I want. but the other thing is I was using like a template I'd created, which is YAML, and I'm telling it whether it's like feature requests or it's a database request, and that then points to the correct type of agent it needs to pull in.

[00:26:13] **Adam:** I was thinking instead of splitting your markdown, your agent's, that MD file by, you know, like other files that you want to pull in based on like, area of the project or whatever. What if you had your list of all your different agent files and you said, okay, if you're making a API changes, pull in this role, or if you're making testing changes, pulling this one, whatever, that might be a useful way to go about it too.

[00:26:35] **Adam:** I think that's really, potentially really insightful. 'cause you,I feel like that might be simpler for it because, you know, if it's API stuff you could put in, okay, this is how we test the API and this is where the relevant file structure is and this is the coding standards for the API stuff and it's

[00:26:49] **Carol:** Oh eight compliance in there. Yeah.

[00:26:50] **Adam:** right.

[00:26:51] **Adam:** Yeah. And so instead of the thing, the agent having to figure the. The coding agent, the the, the LLM, let's call it that, instead of the LLM having to figure out, oh, I need this file and I need this file, and I need this file. It just has to make one, you know, make a decision of which one of these things I'll pull in.

[00:27:08] **Adam:** And it's probably more likely to get that right. Although you're probably gonna end up with a little bit of duplication between the files, but you sounds like you already do anyway.

[00:27:15] **Carol:** That's what I was seeing was several things were duplicated, but I don't know if that's necessarily a bad thing.

[00:27:21] **Tim:** One bad pattern I saw recently, so a developer work showed me. He went and got like all the ColdFusion tags and scripts and put it in an agents.md file. I'm like, why are you doing that? It knows how to code,

[00:27:34] **Tim:** right?

[00:27:35] **Tim:** You don't have to teach how

[00:27:35] **Carol:** It knows how to, yeah, it has access to the internet,

[00:27:38] **Tim:** like, well, he's like, well, he was using some things incorrectly.

[00:27:40] **Tim:** I'm like, well, you just, just

[00:27:42] **Carol:** Tell

[00:27:42] **Tim:** a single line.

[00:27:43] **Tim:** it kept using HTTPService rather than CFHTTP. I'm like, just, you have one line that says use CFHTTP.

[00:27:50] **Adam:** Yeah, I mean that is kind of the, it's, it's a outdated way of thinking about it, but that is, that was a, a recommended approach for a while.

[00:27:57] **Tim:** it's already been trained on all that stuff. Right. So I mean, it maybe it just doesn't know what version you're on or

[00:28:02] **Tim:** I'm sure it knows, I'm sure it knows JavaScript pretty well. I dunno if it knows ColdFusion pretty well. seems to use it pretty good. I, I mean, I, I've been using it every day, so

[00:28:11] **Adam:** that's

[00:28:12] **Carol:** it over. Just send it over to the docs and say, go learn.

[00:28:15] **Adam:** but yeah, I mean, for a while there was a, a thing kind of a, a, a spec, I guess you could say, or a proposed spec where different like languages and frameworks and tools could provide their own, like LLMs txt file that would be like basically all their documents.

[00:28:29] **Adam:** It's still down to a markdown file that could be consumed by an LLM. And some people had you know, micro versions that are like absolute minimum, just so that it can know, okay, this is the function you need to call for this scenario or does this, and, and the, maybe the longer one says these are the arguments and this is the types and all this stuff.

[00:28:48] **Adam:** So it gives it more context depending on how much you're willing to spend on those input tokens. But like I said, I think that's kind of the outdated approach at this point, to the best of my

[00:28:56] **Adam:** knowledge.

[00:28:57] **Tim:** I think so.

[00:28:58] **Carol:** Yeah. The last thing I wanna do is store more historical information for it to use. Like, I want it to stay current.

## [00:29:05] MCP Servers: Pros and Cons

[00:29:05] **Adam:** Yeah. And you know, it's funny, at this point, my opinion of MCP servers is also starting to turn negative,

[00:29:13] **Adam:** um,

[00:29:13] **Carol:** what does that mean?

[00:29:14] **Adam:** master control program. No, that's a,

[00:29:17] **Tim:** that's tr that's a, that's a tron. That's a tron reference

[00:29:20] **Adam:** yeah, I know. model, model context, protocol, right.

[00:29:23] **Tim:** Yep.

[00:29:24] **Adam:** So basically it's a, it's a way to connect an LLM up to an API and, and it's like a standard for the way that, that API works and it can say, it can hit this API and say, okay, what tools are available? And then it returns a list of what tools are available and, and how to access them and, and what each one can do for you.

[00:29:43] **Adam:** So for example, there's a Svelte MCP server, and it will, you can actually look at the responses that it generates. And it's, and, and we happen to know that most LLMs are not great at the most recent changes to the Svelte language. So it's like, you know, anytime that you're doing Svelte code, you have to call the Svelte MCP.

[00:30:03] **Adam:** You have to pass at the code that you're generating. And if you get a response that says that you're generating the wrong code, then you have to try again. You just, it like forces it to loop until it gets it right. it hallucinates specific things wrong very often. So it's trying, it's trying to avoid that.

[00:30:19] **Adam:** but the thing that I'm learning about MCP is while it can be useful in a very, isolated situation, right, if I, if I'm writing Svelte code and I just give it the MCP and nothing else, then that could potentially be really useful. But everybody seems to be providing MCPs now, right? There's a Sentry MCP, you can give it tools so that it, you can say, okay, here's a bug number from Sentry.

[00:30:42] **Adam:** Go fix it. Right? And that might be all you need if you have Sentry and all of that, right? Because you can say, here's the Sentry bug number. It goes into it, it has tools in the Sentry MCP to get the details of the bug, maybe a stack trace and whatever other relevant information there might be, and it can fix it.

[00:30:57] **Adam:** And then maybe it knows how to run your tests. And it does that and it's like, tries to use that information to fix the bug. Sounds really useful. But then, you know, you've got 20 MCPs, you're now stuffing all this information into the context and it maybe starts making useless tool calls, which is costing you extra money.

[00:31:13] **Adam:** And it's also filling up the context. Like we're talking about, you know, three, three books of Star Wars to ask what color are Luke Skywalker's eyes like, you know, there, it, it starts to get absurd at some point. And I think we haven't, we, the larger programming community haven't figured out what the right solution to this problem is yet.

[00:31:33] **Adam:** It's still evolving.

[00:31:35] **Carol:** Yeah, I, I will say, what you just said makes me kind of smile though, because what I said earlier, you know, it feels good to finally be in a position where I feel like as a federal employee, I am working to solve solutions that the rest of tech are working to solve too. I'm not so far behind that. I'm five years out going, Hey, now I know what you were talking about five years ago.

[00:31:58] **Carol:** You know, like I, I'm involved, so

[00:32:01] **Adam:** It feels good to be close to the bleeding edge. Yeah.

[00:32:03] **Carol:** Yeah. do you keep your agent that you've created, do you keep it in source? Do you check it in like with your repository and you have one single agent for everything you do, or is it by repository, by

[00:32:17] **Adam:** It's by

[00:32:18] **Carol:** by project.

[00:32:18] **Adam:** Yeah. So I have a, the agents MD file at the root of the project, and I have seen cases where, you know, we put a, an agent inside MD file, like in a mono repo type situation, right? So like inside that individual project, inside the repo, you might have an, a dedicated agent instead MD file.

[00:32:33] **Adam:** And you say okay, when you're working in this folder, use this file. Like you, you, man, I guess manually associate it with your prompt or whatever. but yeah, so I, I keep mine in source control and I do

[00:32:43] **Carol:** Is it locked? Because I, I saw GitHub has the ability to have agents and they can lock it down so people can't change it. I just haven't really dug too deep into that.

[00:32:52] **Adam:** That's the first I've heard of that feature. Yeah.

[00:32:54] **Tim:** Yeah, I, me.

[00:32:56] **Carol:** You guys don't have solutions though, do you? In your repos? So you don't like open visual studio and then open a solution and it gives you a subset of the repo you have?

[00:33:04] **Carol:** Just the repo is the repo.

[00:33:06] **Adam:** I don't know what a solution is.

[00:33:08] **Carol:** Okay.

[00:33:08] **Tim:** like a, sounds like a very visual

[00:33:10] **Tim:** studio

[00:33:11] **Carol:** it's a, I think, I think it's a.net kind of thing to you and the way different programs work, I don't know what other languages have it. I'm assuming lots of languages have it, but, I have the ability to have a solution and the solution will take like my big giant repo and break it down into like the four projects I need when I'm working this individual area.

[00:33:29] **Carol:** So say I'm working like an interconnection thing. I don't want everything in the interconnection, doesn't need everything. It's just these few projects and it pulls it into that view and it looks like I can create an agent per solution if I wanna go that route. And I think even then that would condense me down on what it has to know about.

[00:33:49] **Adam:** Yeah, that sounds really useful. I immediately, I was mapping that in my brain onto, Docker Compose, I think they're called profiles, so Right. I can say Docker Compose to start the, the profile for giving stuff and then make sure that the API server is running and that the React app is running and that the

[00:34:05] **Carol:** Yeah. Pretty much the same thing. Yeah. Yeah. It's the same, same type of concept.

[00:34:09] **Adam:** So, yeah, I mean, you, you asked about planning. I will say, in, in Cursor specifically, I like the new update to their ui. it, it really kind of pulls that forward. It makes it more like of a first class citizen of the process. it's got three modes. I think there's a plan agent and ask are the three modes, if I'm not mistaken.

[00:34:30] **Adam:** so ask is you know, treats it like kind of ChatGPT, it's not allowed to do anything. It just, you, you give it

[00:34:35] **Carol:** it's like a read only,

[00:34:36] **Adam:** yeah, it, it, it can answer questions or whatever. and then plan and, and agent are about getting stuff done. So, the way I think about plan is you know, it, it allows me to be a little bit more lazy in what I'm asking for and then it basically takes my prompt and rewrites it as a much more thorough spec of what we're gonna be accomplishing.

[00:34:57] **Adam:** And it gives me the opportunity to then review that spec. Then say, okay, I might modify the, the plan or whatever. And then from there I can say, okay, now build to this spec. And you can see it step through. Right? I think every plan ends with a checklist. First I'm gonna do this, then I'm gonna do this.

[00:35:14] **Adam:** And as it's running through that plan, in the in the build process, it is checking those items off of the list as it does them, which is nice. Mm-hmm.

[00:35:22] **Carol:** So right now Visual Studio doesn't support most of this, so I have to do it through, they just support, ask and edit I believe, which I think just edits context, I haven't even used edit. But they don't support, or sorry, they, they support agent and ask, they don't support edit or plan. so in Visual Studio, I've been having to use the CLI, so I've been having to get back into how the heck do you actually use like a GUI to do anything?

[00:35:49] **Carol:** 'cause I'm so used to clicking buttons. So now I'm like typing in the command and I'm like, okay, but I can't figure out how to make it save the files. So I've bounce between VS code because the interface is easier to use because once it builds the plan, I then just click the open an editor. And then I have this nice pretty markdown file that I can change myself and go, I don't want you to do this step.

[00:36:11] **Carol:** Here's what I want you to change. And then I tell you to reevaluate the plan. But the fact that it doesn't do

[00:36:16] **Tim:** it

[00:36:16] **Tim:** to write it to a file.

[00:36:18] **Carol:** probably, I didn't know I could.

[00:36:20] **Tim:** I, I, that's what I do. I'm like, that, that sounds good. Write it to a file.

[00:36:24] **Carol:** Oh, nice. Okay. I'm gonna try that in Codex tomorrow. I'm gonna see if it'll write it to the file immediately.

[00:36:30] **Adam:** before we move on from planning, I wanted to ask Tim if you could explain how cloud code might be different from the like plan and build

[00:36:37] **Tim:** So it's pretty similar. It, it, there's less options. So you have like plan mode, which basically is sort of the same thing where it won't actually write anything. You's just you kind of having a, a conversation. It, it's coating and giving you its information. And then you have ask before edits, which is okay, go do the thing, but I wanna review every single step.and then there is edit automatically, which is like a per file kind of thing. So, so even if you say edit automatically, it's it'll say, can I read this file? You go, you can say yes. Yes. And don't ask again, and then it don't ask that again, but it needs to write something to that file. You'll ask that the first time and the second time you can say yes and don't ask again.

[00:37:17] **Tim:** So if you think it's kind of got, you know, the checklist and you're like, all right, I, I'll, I'll, I'll trust it to just go run through this checklist. You can say yes to everything and it goes through.

[00:37:27] **Carol:** So pretty much it seems like the same. So I'm

[00:37:30] **Tim:** very, very similar.

[00:37:31] **Carol:** I'm using chat, the chat like Copilot's chat functionality inside Visual Studio Code. And I just bounce between the models of the Codex preview, which I think is ChatGPT-4o, don't hold me to that. And now I'm using Claude Sonnet 4 and 4.5. So I think I'm using the same kind of models.

[00:37:49] **Carol:** I just feel like the interface is different for how we're executing.

[00:37:53] **Adam:** Yeah.

[00:37:54] **Tim:** So you had, do you have a question about like tech requirements up front?

[00:37:57] **Carol:** Oh yeah. So that's where we're kind of going with this. As my initial like views on things are changing and we're kind of learning. I'm seeing now that in order for us to be able to feed requirements directly into any type of model, like the tech requirements have to be very clear. There can't be ambiguity.

[00:38:18] **Carol:** 'cause it doesn't know what to do with ambiguity. It says,

[00:38:21] **Tim:** Well, it does. It

[00:38:21] **Tim:** just makes it up.

[00:38:23] **Carol:** yeah, it did. So that's what happened today is it said, okay, I think you wanna change this table. Well, this table exists in two different databases. The projects are together 'cause the way they're, they're coded, right? But it just picked the top level and it said, I found this table first, so this is the one where I'm gonna go change your model at.

[00:38:42] **Carol:** And that's where it tried creating an entire retire system because that. That program doesn't need retires, right? Like it just has fleets on everything. So I was like, where, like, how did you even end up in here? And I had to explain to me like how it actually chose that table and didn't go to the correct one.

[00:38:59] **Carol:** And I'm like, Ugh, I need better requirements. Like it has to lay out program level information. And I don't know that I can expect a BA or a product owner to do that. So I'm kind of thinking that we're gonna have to have a middle layer that helps build the specs before we even write the plans to make sure the specs are usable.

[00:39:19] **Tim:** So I, I see kind of two sides of this. One. If it's a, if I'm building the requirements, I usually kind of know what the AI needs to know. I, I have this table, here's the schema, I have this API and I I need you to create a logging system. Anytime this happens to do that, that's pretty straightforward.

[00:39:35] **Tim:** Where it gets harder is like if, if someone else is giving, like a customer's giving you requirements or you have like a, a business analyst, they're giving you requirements. Ideally they should all be using AI to figure out that their requirements are good. But no, most of the time it's not. So I, my first pass is kind like whitelist versus blacklist.

[00:39:58] **Tim:** So I run the blacklist first on the requirements. Requirements come in, they gimme some PDFs and some API specs and everything. So I point, you know, Claude to all of those and I say, here's the requirements on this. You know, this markdown file has these requirements and this is the API spec from the swagger page over here.tell me what I need to know in order to write good requirements and then use that information to basically generate an email to the, you know, the, the party that is giving me the requirements to say, Hey, I can't get started on this until you answer these questions. Which is a little bit reiterative iterative, but you know, it's don't waste your time on generating code if you don't have complete, but if it, if it, and, and AI tries to please you.

[00:40:37] **Tim:** So if you just, just ask it to do the thing for you, it'll just do the thing. But if you ask it to stop you from doing the thing 'cause you don't have enough information, it does a very good job of yeah, we need this, this, and this. Now some of it is like information that may, may not even be relevant, but you know, at least you can kick it back to someone and say, Hey, I, I need this before I can

[00:40:57] **Carol:** Fill in the

[00:40:57] **Tim:** requirements.

## [00:40:58] Prompt Engineering as a Skill

[00:40:58] **Tim:** Yeah.

[00:40:59] **Carol:** Yeah, I think that's gonna be kind of our starting phase for this is how we build requirements like that feels like the immediate solve that needs to be worked on by a larger group. And then it's going to be how we actually planned from said requirements.

[00:41:12] **Tim:** Yeah.

[00:41:13] **Adam:** I mean, ultimately I think where you're headed is like a, a program to teach your programmers to be prompt engineers at

[00:41:21] **Carol:** It kind of feels that way, doesn't it?

[00:41:23] **Adam:** Yeah.

[00:41:23] **Carol:** Like that's, that's where my brain's been for

[00:41:26] **Tim:** Even the business analyst. I mean,

[00:41:27] **Tim:** that's the ideal world for me. I, I think, I hate it when you get some sort of like epic or story and it, it comes to you and it's there's two PDFs and some vague instructions to say, make the thing work. And you're like, this really, I mean, there's a whole bunch of work.

[00:41:45] **Tim:** Why am I, you know, as a developer, why do I have to go get all this information? You should be giving this to me. So when I pick it up, I can do my job, but that's not the way things go. So in an ideal world, it's like your, your business analysts, your people that are dealing with the customer, they should run this through the AI themselves to say, what else do we need to know

[00:42:03] **Tim:** before they even create the ticket to give it to you?

[00:42:05] **Tim:** But, you know, I realize that's not always gonna happen. They, they're not technical people. They may not even be aware necessarily that something to ask, but I would hope the AI would prompt them to that. But that would be ideal. Yeah.

[00:42:19] **Adam:** There should be. Yeah. There needs to be like a, a step in the middle where there's an LLM involved where like they go, okay, I want my developer to implement this. And they give it the PDF and the LLM comes back and says okay, well these are some questions your, your developer is gonna have that you can probably answer.

[00:42:33] **Adam:** what are the answers to these questions? And then that's what gets put into your ticket or whatever

[00:42:37] **Carol:** Right. That was one of the things I talked about with a couple of the guys today. I was like, can we create this? can I just create a prompt for them automatically that's, Hey, I need to answer these things. as the architect of the the system, I'm gonna wanna know these basic things depending on what path they're going with the work.

[00:42:53] **Carol:** if it has security related information, I need to follow these security paths. If it's database, like I need to follow these paths and if I could get some of those questions up front, then I get the right people tagged and yeah. So we'll see. We'll see.

[00:43:06] **Adam:** you. You know what we should do? There's probably like a repository online. There's probably like a, an awesome dash agents MD repo or something, right? people sharing their agents files. But, you know, maybe just we can start with in our, in our Discord, you know, listeners to the podcast, if you have an agents MD file or Claude MD that you're really proud of, let's share those in a way that like people can look at them and maybe crib things for, for their own and, and learn from each other.

[00:43:32] **Tim:** Yeah, so just be aware though. I posted some of mine and, Adam Cameron either hi, either himself responded and basically, you know, gave it the sniff test and poo-pooed on a lot of it, which I'm used to. Yeah, that's what he's, that's what

[00:43:45] **Tim:** he's really good at. Yeah, he's my hater. But you know, his hate is actually beneficial 'cause, you know,

[00:43:49] **Carol:** I was gonna say, it's usually pretty good.

[00:43:51] **Tim:** it's usually pretty good.

[00:43:52] **Tim:** and then he also has like his own, I don't know how he's created this version of, he calls it Claudia.

[00:43:57] **Adam:** Mm-hmm.

[00:43:57] **Tim:** He has this LLM version that is the most snarky, rude, misanthropic.

[00:44:04] **Adam:** Cursing.

[00:44:05] **Tim:** ever met. Yeah.

[00:44:05] **Tim:** Kurt. Yeah. It's hilarious. But but yeah, so yeah, please share, please share your stuff if you, if you found benefit out of it, but I, 'cause I'd be interested to compare.

[00:44:14] **Carol:** I cannot share mine. I'm so sorry. Nothing I write can be shared, but I could peek at someone else's.

[00:44:22] **Adam:** Yeah. Did you have any other questions before for us, before we wrap up?

[00:44:27] **Carol:** No, I think we're good. I think that's a good, good calling it spot. You guys have been helpful and, and I sometimes it's just good to feel validated that I'm on the right track and that the places I'm feeling lost other people are too. And we'll kind of just all figure it out together.

[00:44:43] **Adam:** Yeah.

[00:44:43] **Adam:** for sure. We're

[00:44:44] **Tim:** And I, I, yeah. And I think we're all in the same spot. So, you know, within our company, our corporate parent has an, we've created these. AI cohorts. So, I mean, a lot of it's just to please the stock market. So I was telling you guys earlier, our, our stock just took a huge tank, like cut in half.

[00:45:02] **Tim:** So, the main reason for that is like the, the president of the, the company of Constellation, he retired due to, health issues. another thing that Wall Street brings up is they don't know that our business model will support the, AI revolution, how we're dealing with that, right? So we, the earnings calls, we haven't talked about AI enough, so they're penalizing us for that apparently.

[00:45:25] **Tim:** So it's like we have these cohorts that are basically going through and saying each company, how are we gonna utilize this? And how can we like, demonstrate to the world and to Wall Street that, that, you know, we're gonna use this in a way to, to, you know, generate value for the shareholders. so we're all kind of this, this step of trying to figure the very same things you were talking about that that AI cohort was.

[00:45:45] **Tim:** You know, they, they generated, I saw the document yesterday. it's a pretty good, pretty good work product that they're doing, but it's as you said, it's it's good for now, but

[00:45:52] **Carol:** it's gonna

[00:45:53] **Carol:** change six months from now. Six months from now is gonna be

[00:45:56] **Tim:** from now.

[00:45:57] **Carol:** Yeah. And then I had someone even mention oh, they feel like this is a bubble and a waste of time anyways, so they may not be wrong. I mean, we don't really know what's gonna happen and

[00:46:07] **Adam:** it often feels like it. It's on the verge of collapse. Yeah. That's the thing is like these are useful tools for us as developers. I don't know that they have as much use outside of developing, outside of writing code.

[00:46:21] **Carol:** Mm-hmm.

[00:46:22] **Adam:** So, but there, the hype train is that it's gonna solve all of the world's problems.

[00:46:25] **Adam:** And so if it can't live up to that and, and become profitable, then it's all gonna come tumbling down because there's way too much money invested in all of

[00:46:33] **Tim:** and and they're, and they're way oversell. People are saying, oh yeah, we're gonna have a, in the next 10 years, we're gonna have a two day work week.

[00:46:41] **Adam:** yeah.

[00:46:42] **Tim:** aren't gonna have to work anymore. You know,

[00:46:44] **Tim:** saying anytime they're selling you utopia, you know, there's some BS going on.

[00:46:49] **Carol:** Yeah, and if history repeats itself, everything I know about working is when my schedule gets cleared, someone finds something else for me

[00:46:57] **Carol:** to do. It doesn't, I don't just, I don't get three days off. I just get three days worth of more work.

[00:47:02] **Tim:** yeah. No work some

[00:47:03] **Carol:** Yeah.

[00:47:04] **Tim:** So.

## [00:47:05] Patreon

[00:47:05] **Adam:** Alright, well then this episode of Working Code is brought to you by Security, by Antiquity. Actually, maybe don't update your code and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe. So you should consider supporting us on Patreon.

[00:47:19] **Adam:** Our patrons cover our recording, editing, and transcription costs. We couldn't do this every week without them. Special thanks of course, as always to our top patrons, Monte and Giancarlo, and actually,a call out I wanna throw out here, we have a new patron this week. George Hemel. I think it's how it's pronounced.

[00:47:35] **Adam:** George, welcome to the team. Glad to have you.

## [00:47:37] Thanks For Listening!

[00:47:37] **Adam:** we're gonna go record the after show. I got a bunch of stuff I wanna talk about tonight. we're not like a topical podcast. We don't do stuff on the news of the day too much.

[00:47:45] **Adam:** You know, we've talked about these hacks and stuff that's relevant. That's kind of like a evergreen topic, right? There's always gonna be something, some sort of threat, but. but I do have some stuff that's in the news that I wanna talk about, today as we're recording this. December 4th is JavaScript's 30th birthday.

[00:47:58] **Adam:** and I've got a new nerd tool that I'm kind of obsessed with right now. I want to get into, it's called Aerospace. and, and other stuff we were talking about, Spotify wrapped, in the, in the trams and fails. And, at the suggestion of one of our listeners, I created jump, run, wrapped.

[00:48:13] **Carol:** That's really cool.

[00:48:15] **Tim:** Yeah.

[00:48:16] **Adam:** so we'll talk about all that stuff and more in the after show. If you wanna get that, all you have to do is go to patriot.com/working code pod, throw a few dollars our way. We greatly appreciate it. You'll get access to the full back catalog of, episodes with after shows and, and all the future ones too.

[00:48:31] **Adam:** that's gonna do it for us this week. We'll catch you next week. And until then.

[00:48:35] **Tim:** Hey. Hey, listen. Listen. If you don't know the color of Luke's Skywalker's, eyes doesn't matter. Your heart matters.
