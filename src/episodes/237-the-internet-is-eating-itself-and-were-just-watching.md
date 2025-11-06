---
title: "237: The Internet Is Eating Itself and We're Just Watching"
description: "In this week's episode, we explore the economics of AI search, the death of Stack Overflow, the junior developer problem writ large, and more"
date: 2025-11-06
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/1fccd134-e7f5-42e8-b16f-046ace79ce7e"></script>
<div class="redcirclePlayer-1fccd134-e7f5-42e8-b16f-046ace79ce7e"></div>

When you use ChatGPT instead of Google, you're not just getting a faster answer—you're cutting out the content creators who made that knowledge possible. In this week's episode, we explore the economics of AI search, the death of Stack Overflow, the junior developer problem writ large, and why capitalism keeps pushing moral responsibility onto individuals who have the least power to change anything.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/237-the-internet-is-eating-itself-and-were-just-watching.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** it's one thing to have the traffic numbers.

[00:00:01] **Adam:** It is a thousand percent more. Fulfilling to get a comment or a tweet or something, if that is the reason that you're on the site and you're avoiding the LLM or, or whatever, if you're on the site because you want to, you know, just support, homemade content, whatever, leave a comment, send them a tweet, say, Hey, I read this article, I really liked it.

[00:00:18] **Adam:** Whatever. just don't use an LLM to write it.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go. It's show number 237. And on today's show we're gonna talk about the long-term social cost of using LLMs like they're a search engine.but first, as usual, we'll start with our triumphs and fails.

[00:00:53] **Adam:** And Carol, I'm coming to you first this week.

## [00:00:55] Carol's Fail

[00:00:55] **Carol:** Yeah, sadly, guys, I'm gonna have to throw us off with a big giant failure.

[00:01:00] **Ben:** Uh oh.

[00:01:01] **Carol:** I realized how terrible it is when you move too fast and you break lots of things. So

[00:01:08] **Adam:** don't say.

[00:01:09] **Tim:** Tell that to Google. I kind of made a couple whoopsies. I moved some of our spaces around in Octopus Deploy. when we were first set up, we kind of were like in this default space.

[00:01:19] **Carol:** So we've got things in default,

[00:01:21] **Ben:** what is this space? I don't know what that means.

[00:01:23] **Carol:** Oh, so imagine everything, for everything you deploy. All your deployment stuff should be contained for all your projects. So everything my team touches, however, it was set up like at one big organization level. So in the default space contained every project for all of our organization.

[00:01:43] **Carol:** So when you go in there and look for something, you're having to weed through years of information and through many projects, half of which aren't even valid anymore. And it was just set up poorly with how variables were scoped and what was done. So I've slowly been migrating us into a single space. So whenever our developers or our deployment coordinators go into Octopus Deploy, they go to one single page and then that has everything related to the projects we touch.well, when I was doing the export and import, I didn't quite realize everything that was going to import into the new space until I started getting messages from developers who were creating some new projects and they were trying to understand why all of these old environments are in our space now and what they actually need to scope things to and what environments are real.

[00:02:34] **Carol:** And I'm like, why are people asking me this? I was like, this is the dumbest thing ever. Like, you know, you know what you're doing.

[00:02:41] **Ben:** idiots.

[00:02:42] **Carol:** Yeah. And I clicked the link. Finally, one of our essays sends it to me and says, are you making changes? I click the link and there is this giant list of environments from everyone that, for like everyone to select, there's new variable sets.

[00:02:56] **Carol:** So while the project came over. Great. For the most part, it also brought in everything from what I was trying to get rid of. So I then had to go do a bunch of cleanup and then I felt terrible for everyone who'd been in there for two days trying to set their stuff up. And I just added a lot of confusion, so that was wonderful.

[00:03:17] **Ben:** That sounds so space, is that like a, like a.net kind of a thing or

[00:03:23] **Carol:** No, it's more, no, it's more of like, so when you go into GitHub, you can go to like your organization or you can go to your, your private page, right? It has all your repos. So imagine if every time you wanted to go to your private repos, you had to go to the organization and then find your private repos.

[00:03:42] **Carol:** Um, it's everything that's just contained for our single team and not everything for OPM.

[00:03:48] **Ben:** You know, a couple of episodes ago I attempted to explain my thoughts about quote unquote good friction. And I had this idea years ago that I thought would be good friction, which you sort of mentioned a little bit, I think there for a second, Carol, which is that a team should only have a single page for all of their documentation.

[00:04:10] **Ben:** And I feel like that is a good constraint because you notice very quickly when you're adding stuff to that page that doesn't need to be there. The fact that we can have these just like pages upon pages upon pages of documentation and links to other documentation and links to other sites, just feels like it becomes this sprawl.

[00:04:28] **Ben:** And how do you keep that in check?

[00:04:30] **Carol:** Yeah, I mean, that's how I feel about our Wiki right now. There's folders inside folders inside folders, and I try moving things around, and now there's just things lost. I've given up on some of it, and I just hope no one goes into those folders.

[00:04:44] **Ben:** Right?

[00:04:44] **Carol:** but that's me. That's my failure. I'll move slower next time.

[00:04:49] **Carol:** What about you, Tim?

## [00:04:50] Tim's Triumph

[00:04:50] **Tim:** Well, I'm gonna wipe that failure outta your mouth

[00:04:53] **Carol:** Perfect.

[00:04:54] **Tim:** Go over a triumph. It, it's not a huge one, but you know, it's, it's, I'm happy with it, you know. After talking and just thinking and ruminating or on AI coding and helping agentic coding. I'm really starting to see some good personal payoff with AI coding at work.

[00:05:10] **Tim:** I've gotten more comfortable with it, I think, but, you know, I don't want to, so I've just kind of done it myself in just reading what I read and, and I'm getting pretty good results. But I think I'm gonna set up some calls with some of our developers who really, really use it a lot. Like, like, Ryan Cottingham, well Spiffy Tech,

[00:05:31] **Ben:** Oh.

[00:05:31] **Tim:** and, kind of see how he, some recommendations if he can help me improve my, my workflow on it.

[00:05:36] **Tim:** 'cause I'm getting really, I think I'm getting good bang for my buck now, finally. And I'm not fighting it so much, but I wanna see if there's ways I can like tweak it. So happy with that. On the other hand, it's like I am so tired from daylight savings time.

[00:05:51] **Tim:** I've been going to bed like every night at like nine, nine o'clock.

[00:05:55] **Carol:** Do your dogs wake you up at three?

[00:05:58] **Tim:** Oh, I don't know. The dog. The, the dogs are on the, on, on the other side of the house. I don't, I don't sleep near them.

[00:06:04] **Adam:** Yeah. My dogs have been getting me up early 'cause they're like, I want my breakfast. Where

[00:06:07] **Ben:** it's not time, it's four o'clock

[00:06:09] **Carol:** Yeah.

[00:06:10] **Tim:** Our dogs are lazy. They're used to waking up at noon for breakfast, so yeah, we're, we're good. So they're waking up at 11.

[00:06:16] **Ben:** yo. But for real. As you're becoming more comfortable with AI, please drip some of that sweet honey onto me because I am, I'm feeling like I am very much struggling. To wrap my head around it. Granted, my attempt to do that is from afar, not from a hands-on, approach. So any, anything that you can do to help spark my, my motivation to, to dig deeper.

[00:06:42] **Tim:** Yeah, so I've been using Codex, you know, for several weeks now, and I really like it. It's like t's version of ag agentic coating. Apparently we have like a corporate version of Claude. So I'm looking in to see if I can get a, get that so I can compare. But what that was really cool is like, I just kind of described the problem to, to Codex thing is, I found that being very specific and knowing when I really, really know what I wanna build, it gives me exactly what I want when I'm unsure. It kind of gives me close footnote, close enough. So today it was, I was very specific on like, I, I know I wanna build an endpoint that does this, and I gave it a table description.

[00:07:23] **Tim:** I'm like, here's the table. So whatever you call this, API, I want you to take this stuff, pop it in here. But I was building, this is actually for PCI, so PCI is a new requirement. 11.6 I think it is. So you have to do a, a scan, a regular scan of all your scripts. So you have a page and it's like taking credit card data.

[00:07:45] **Tim:** And so that page is made up of multiple scripts. Now we don't do any external third party call outs. Everything is internal.and so what I did was I gave it a like 15 URLs and I said, I want you to scan these URLs, turn it into a SHA-256 hash store that in a database. And I described, here's what the database I, because I had already built the database, so here's the database table.

[00:08:11] **Tim:** I want you to populate that I didn't explain to it because they were named slightly different things. I didn't tell it. I'm like, so you got these things. I want you to populate this table with that data that you get back, and then after you populate it on the next run, you need to compare the previous SHA to the first sha.

[00:08:31] **Tim:** And if it's different, you know, highlight that in a report and email that to me. And I gave it the mail server and I said. My main thing is like, only use CFScript. Please do not use any tags. And I

[00:08:45] **Tim:** did that.

[00:08:45] **Adam:** in Tag Islands.

[00:08:46] **Tim:** No, never, never. And so I did that. I went away and just hit the button and said yes, and then I walked away and then I started working on some emails and like, you know, sending some correspondence and I came back and took about seven minutes to run.

[00:09:02] **Tim:** But when it was, it was done, it was perfect. It was absolutely perfect.

[00:09:04] **Ben:** Dang.

[00:09:05] **Adam:** Yeah, I've, I've had similar experiences, like when I know exactly what I wanted to do, and I, I can, especially if I can describe it simply, right? Like I, I had a thing this week. We had, you know, we, we have all of our error messages sent to one of our Discord channels for our team. and we just, so we were starting to like, see this one appear more and more frequently, and we're like, I don't know why this is happening.

[00:09:27] **Adam:** And, and a lot of our, you know, we have like, we have monolith and then we've kind of extracted microservices out from that. And a lot of those run as node processes either on Lambda or Fargate. And so we have some, like a, a, a collection of modules that is reused among many of these things. And one of the utilities in there was like throwing errors and it's like, okay, well it's, this is coming from the reusable module, but we don't know which app is, is causing the problem, right?

[00:09:51] **Adam:** We're just getting this bug log that says this thing failed, and, and we know it's from DS modules. I'm like, okay, well that thing has a has stuff though. If, if you have an environment variable named like IQ app, then it will include that in the bug log report so that you know, okay, this app is failing.

[00:10:10] **Adam:** So clearly there's an app out there somewhere that doesn't have that environment variable. So I, I've had AI right? A thing. I was like, okay, scan through all of my Lambda functions and all my Fargate services, and if any of them are missing the IQ app environment variable, list them out for me. And, you know, I, it was a little more specific than that.

[00:10:26] **Adam:** Use the AWS SDK and assume this about authentication and stuff and, and it like, yeah, it, one shot at it very easily.

[00:10:34] **Ben:** Dang.

[00:10:35] **Tim:** the, the, the best thing. So coding is good at, I, I, so I'm ambivalent. It's like I could have spent that time actually coding it myself, and I, it would, I'd be happy with it, and I would look at it and I would like, you know, be like Ben and like be super concerned that everything was lined up. You know, I, the variables were named just perfectly.

[00:10:53] **Tim:** I wasn't so concerned about that. I'm like, does it work?

[00:10:56] **Tim:** Okay. It, it worked. It created a, it created a report. It sent me an email. Cool. but the harder thing is like, so is, so I have to submit this to a.PCI auditor. Now the PCI auditor is trying to sell his own tool. They have their own tool that goes through and ignorant of your design or how your stuff works, that it will scan your site and do these kind of checks for you on a weekly basis.

[00:11:22] **Tim:** But they went like $15,000 a

[00:11:25] **Adam:** Yeah.

[00:11:26] **Tim:** right. To do this. And, and like I'm pretty sure the complexity there is that they, they have to do that. They have to create a tool that does it for every site, not just mine. I know exactly where everything is, so I know what to scan so I don't have to like build super smart stuff that goes through.

[00:11:41] **Tim:** I'm like, these are the things that get hit every single time a payment comes through.but I have to, now I have to justify this to the auditor who, who, who's trying to sell me a $15,000 piece of software. Of course, he also very fairly gave us like 10 other options, but they're all super expensive.

[00:11:59] **Tim:** and I'm like, that's just ridiculous to pay that

[00:12:02] **Adam:** Are you still using the same auditor as us?

[00:12:04] **Tim:** Yeah.

[00:12:04] **Adam:** So they'll, they'll be fine. they'll take it, but

[00:12:07] **Tim:** but the best thing was I, I basically said, I told ChatGPT outside of, you know, VS Code. I'm like, here's the thing I built. Here's an example of what it produces and it satisfies the, you know, PCI 11.6, new requirement that is new here. Explain to an auditor why this is,

[00:12:28] **Tim:** you

[00:12:28] **Tim:** know, meets the requirement and it built this beautiful 'cause.

[00:12:31] **Tim:** That's the thing that auditors really wanna see. They wanna see some, like a, a page of text. It's, it justifies your reasons and the reasons are bull crap. And the reasons really are, it's like you're just making a certain statement like, well therefore we have a, a, a safe baseline that we can, well, I mean,

[00:12:47] **Tim:** there's really no way you can prove that in the chat that you do, but you give it to an auditor and they go, okay, that sounds reasonable. That's the best thing LLMs do is like, yeah, it sounds, it sounds reasonable. Even if it's like 90% true, it still sounds reasonable.

[00:13:03] **Adam:** Yeah. Well, I mean, what was it Ben, I think today you had posted something in our discord, like how, oh, the, the A form blocks you from pasting in a

[00:13:12] **Ben:** Oh my goodness.

[00:13:13] **Adam:** can you get soccer or PCI compliance with this? And I'm like, well, it's funny you should mention that There's so many things that are like good practices.

[00:13:19] **Adam:** They just, they just are either completely unaware of or just doesn't reach their bar for like, things that need to be checked and monitored.

[00:13:27] **Tim:** Yeah.

[00:13:28] **Adam:** I'm probably gonna completely misquote this here, but I was listening to the shop Talk Show podcast, I don't know, maybe two weeks ago. And, Dave Ruber was saying that they were interviewing someone. That's what it was. They were interviewing someone and, and the guy was saying that he was a, working on a, like a dark patterns accessibility guidelines.

[00:13:52] **Ben:** So, you know how if you open up the, the dev tools and you can look at say things like color contrast to make sure that it passes certain, Things for accessibility, and if you do the,lighthouse scores, it gives you all the accessibility problems, you know, missing title attributes, that kind of stuff.

[00:14:07] **Ben:** So, the, some of that stuff is dictated by law now in, in, in certain ways. Like I'm sure government websites have to have certain types of compliance for accessibility. Anyway, the guy on the shot talk show was saying that they're working on kind of the next level of this stuff, which is not just the accessibility from a mechanical standpoint, but accessibility from a behavioral standpoint and working on things like, making sure that you always opt into something as opposed to having to opt out, say to like automatic payments

[00:14:37] **Ben:** they're coming up with this new specification for these dark patterns, and from what I gathered that he was saying is that it'll be rolled into the, like the web accessibility guidelines. Set of recommendations and I'm wondering if at that point some of these dark patterns become almost illegal in the way that it becomes illegal to have completely inaccessible sites, which I think would be kind of cool.

[00:15:02] **Ben:** 'cause there's definitely a lot of dark, shady stuff out there.

[00:15:04] **Tim:** so that's pretty interesting, Ben. I dunno how you got to where I started to where you got, but cool. how about you, Adam?

## [00:15:11] Adam's Triumph

[00:15:11] **Adam:** so, before we, uh, move on to me, I, I just want to kind of, pile on yours a little bit too. the, you were talking about, you know, getting better at using the LLMs and, so I, I mentioned last week I have been kind of taking a little bit more of a personal interest in using Cursor and, and trying to like see how well I can tax it.

[00:15:30] **Adam:** And the, the sad truth is so far I, I have not done a good job of taxing it. I have been using it. That was like the, the thing that I built that, one shot, you know, tell me what my, which, which things are missing, the environment variable.but that was not a, a large problem, you know, it was a, a brief prompt and, and like three or four files are built.

[00:15:49] **Adam:** So one of the neat things about Cursor is you can like go in and, and look at your usage and like, I've only been using it for less than a week now. but it's like every single day my total usage for the day is like, less than 5 cents worth of prompts. Like, now I think I'm on like a, a free trial.

[00:16:08] **Adam:** I guess it, it does include like unlimited tab completion, that sort of stuff. But I'm, I'm specifically talking about like prompt based ag agentic stuff. so I mean, it is a, it is a cheap model and I'm sure that has a, some effect, but it also, I think it's, it's also telling of like the type of work I'm doing lately.

[00:16:25] **Adam:** You know, I've been bouncing around on a lot of different things, helping get our new hire up to speed. So I'm kind of spending some time mentoring her here and there, and preparing things, you know, doing compliance stuff. So I'm kind of all over the place. I'm not just like coding all day, but. it's really kind of opened my eyes and like, okay, well, you know, a lot of people are spending a buttload of money on this stuff, so maybe I need to be trying harder to find the right places to use this stuff.

[00:16:50] **Adam:** Like maybe it's, maybe there's opportunities that I'm just not seeing, so that's on my mind. Mm-hmm.

[00:16:56] **Ben:** Here, here's a question for you. 'cause I've been struggling with something. I, I, I keep wanting to dip my toes into this world. And when I, when the Claude code was introduced at work, I tried to get it working for me locally. Now, here's the issue that I ran into all of my development I do inside of Docker containers these days.

[00:17:19] **Ben:** And it feels like, you know, it's, it's configuration is code. I have all the operating system and the volumes mapped. And when I do NPM install, it's doing it in the confines of the docker containers. and what I tried to do was create a docker container essentially that would house Claude code so that if I ever accidentally had CLO code run like an RM dash r slash.

[00:17:50] **Ben:** It would blow away everything inside the Docker container and that's it, you know, it would keep it, under lock and key a little bit. and I was not really able to do that. Like I wasn't able to get it to work. It was super janky. Like the whole screen would often come up red, I think because Claude Code uses like all these asky colors and these animations and just getting it to work inside of the Docker putty terminal.

[00:18:15] **Ben:** I'm saying words that I don't really mean or I don't understand. So my question then becomes to you,

[00:18:20] **Adam:** the polarity on the flux capacitor.

[00:18:23] **Ben:** do you just like yolo, I'm gonna run cursor with like on my host machine, or does cursor run inside of a container? How does it

[00:18:33] **Adam:** no, I just run it on my machine. A lot of these newer tools have a lot of stuff built into them where it's like, okay. You give it the prompt, and then it's like, especially the first time it says, okay, this is what I'm gonna do. I need to create a file, or I need to, I need to read these files in this folder.

[00:18:48] **Adam:** Is that okay? And you give it permission and you can say, like, always ask, or it's o it's always okay in this folder or whatever.

[00:18:55] **Ben:** Yeah, but then I wonder like, is that just a nicety that they've coded into their agent? Like, can the agent actually go and do all kinds of crazy stuff, even, you know, that that's always my concern. Like I just, it feels weird at this point to run things on my host computer when I don't understand what it's doing.

[00:19:13] **Ben:** I mean, I'm sure like 90% of the software I run is that, you know, running on the host computer and I don't know what it's doing, but.

[00:19:20] **Adam:** the, I, I, you know, I don't give it much thought, but now that you mention it, the, like Mac os pretty regularly ask me like, Hey, is it okay for this application to make changes in your downloads folders, trying to access your desktop or whatever, right? So it's like, okay, the OS is gonna protect me a little bit too.

[00:19:36] **Ben:** You know, like once a week I get a prom that says Google Chrome would like to find other devices on the network. And I'm like, I don't know why it needs to do that, but okay.

[00:19:46] **Adam:** Yeah,

[00:19:46] **Ben:** I'm like, I guess that's what it needs to do.

[00:19:49] **Adam:** is a little bizarre.

[00:19:51] **Ben:** I mean, why would it be asking me? I don't understand.

[00:19:56] **Adam:** it's a good question. Yeah. I don't know. But anyway, to, since Tim threw it over to me,

[00:20:00] **Tim:** A long time ago.

[00:20:01] **Adam:** Yeah.

[00:20:02] **Tim:** I've grown a beard

[00:20:03] **Adam:** that, so this, this is a, a talk show. We talk, I'm gonna go with a triumph. And my triumph is that, phase one of, you know, precisely 123,764, of our SvelteKit migration is 90% done. you know, leaving only the, the remaining 90% of this phase one, as we say.

[00:20:24] **Adam:** which is just, just to say like, you know, we're, we're making good progress. We are, I have done like a test deploy to qa. We're not like. Continuously deploying it to qa, but, you know, we've got that sort of pipeline built and, getting that stuff together. So we're, we're getting really close and it's getting exciting that we might, like conceivably hit our goal of having this thing in production by the end of the calendar year.

[00:20:45] **Ben:** Nice.

[00:20:46] **Adam:** and I don't get to write Svelte code all day, every day, but I do get to write more than I was before and that makes me happy.

[00:20:54] **Ben:** Love it.

[00:20:55] **Tim:** So, who else on your team does Svelte.

[00:20:58] **Adam:** so primarily it's myself and one other developer. we have, so we are, our team right now is four. We just hired another developer, I think two weeks ago, or three weeks ago, two weeks I think. Sounds right. and, the, that person will be eventually coming up to speed and, and helping out with Svelte stuff.

[00:21:16] **Adam:** after they get better acquainted with our, our code, our, you know, we have.10 plus years of, of work in this repo. And it's a lot to, to wrap your head around. And we have a lot more repos too, so, yeah, they'll, they'll be helping out there. But, so primarily right now it's myself and this one other guy, and we have our fourth guy.

[00:21:36] **Adam:** he does a lot of our infrastructure and he's also our, sort of our lead guy on the Salesforce efforts. So we're spread pretty thin.

[00:21:44] **Tim:** Gotcha.

[00:21:45] **Ben:** Now I know. In the past, you have said that you take kind of a YOLO mindset when it comes to new CSS features, and I know, was it last week or the week before, I think you were talking about, container queries and you started to play around with that. have you adopted, the has CSS selector stuff yet?

[00:22:05] **Ben:** I'm, I'm super excited to play around with that, but I feel like I can't, I can't pull the trigger yet.

[00:22:10] **Tim:** Has cheese, has cheeseburger.

[00:22:14] **Ben:** ICAN has CSS selectors.

[00:22:16] **Tim:** Oh, there we go. That's even better.

[00:22:18] **Adam:** So, me personally, I don't think I've used CSS has. but that's just, that's primarily because I don't do a ton of CSS work right now, and haven't for a few years. I do a little dapple here and there, but most of what I've done is been tailwind stuff. And so there might be stuff under the covers that it's doing, that's, that's using has or specific features, but I haven't jumped on that.

[00:22:41] **Adam:** You, you know, the way you phrase it there made it sound like I'm out here. Oh, a new feature was added to Chrome yesterday. Let me get that in my app on every page. That, that's not the case. Like container queries. That's gotta be what, like four or five years old now.

[00:22:53] **Ben:** Yeah. Is it, I don't know, but I,

[00:22:56] **Adam:** let me look, let me look.

[00:22:57] **Adam:** Container queries, wrong search box here,

[00:22:59] **Ben:** so this is interesting. Do you go to Google for searching for whatever you're searching or are you going to ChatGPT?

[00:23:06] **Ben:** right now I'm looking on MDN. Right, so that's what I do is I open up Google Chrome, I mean, Google search and I do MDN and then the thing I'm looking for,

[00:23:16] **Adam:** so interesting. I mean, my, my usual pattern is broken here because MDN my, my pattern is, okay, this is a web feature. It's usually built into browsers or whatever. What's the support for it? Right? And I guess I could go to like, was it, can I

[00:23:29] **Ben:** Can I use,

[00:23:30] **Adam:** or whatever that, that might be the second place I look.

[00:23:32] **Adam:** But,I go to N page for it, and then I just scroll down to the bottom and it gives you like a little grid of, you know, what supports it and what doesn't. And I found the page for it really quick container queries, but at the bottom it's just like a, there's a c also for a bunch of like, related stuff.

[00:23:46] **Adam:** So I'm gonna go to the container at rule, maybe it'll be on there. Okay. Yeah. Now I got the grid. And so like, safari on iOS doesn't have support for it. Web view on iOS doesn't have support for it. Firefox on Android doesn't, safari desktop doesn't. And Firefox desktop.

[00:24:04] **Ben:** does

[00:24:05] **Adam:** these are, these are, there's different pieces of it, like I guess it's partial support on all of these things, but those are the things that don't, and then everything else has it container queries.

[00:24:15] **Adam:** So, and you know, the container queries in particular, it's like, and the way you develop a tailwind, it's like, okay, this is what I want it to be by default, and then I can kind of modify if I detect different situations.

[00:24:27] **Ben:** Yeah. Yeah. I, and to be clear, when I say yolo, I did not mean that in a derogatory way. I meant that in a fearless I'm okay throwing myself out of planes and like, you know, live moss kind of way.I'm, you know,

[00:24:41] **Adam:** mos,

[00:24:41] **Ben:** definitely on the other end of

[00:24:43] **Tim:** just co-mingled like 13 memes.

[00:24:46] **Adam:** that's right. I eat a lot of Taco Bell because of the implication.

[00:24:52] **Adam:** So. Yeah, I'm just excited. Spel Kit. it makes me happy to, that's like one of the highlights of my day usually when I get to work on Svel code.

[00:25:00] **Ben:** it.

[00:25:01] **Adam:** So that's what I got going on. Ben, how about you?

## [00:25:04] Ben's Triumph/Fail

[00:25:04] **Ben:** Uh, I'm gonna go with a, like a triumph that is also partial failure. So my triumph is that I've been spending not a lot of my free time, but my morning free time before work, working on my big sexy poems app. And it's just been a lot of fun and I am using it to generate ideas for new blog posts. And I'm also

[00:25:23] **Adam:** us your couplets.

[00:25:25] **Ben:** exactly,

[00:25:28] **Ben:** and I've been using it to feel the friction in the code as I'm writing stuff that's very new, I'm trying to keep my mind focused on what are the parts of writing this code that feels friction full. What does that mean? Can I approach this in a different way? Can I just rename things a little bit to remove some friction?

[00:25:47] **Ben:** And I've been really enjoying that self-exploration as much as it is like application exploration

[00:25:54] **Adam:** Behind locked doors, Ben. I mean, be decent.

[00:25:57] **Ben:** You know, in the, the privacy of my own home here. but the, the flip side to that is that I feel like, and this is where the failure comes in, I feel like I'm now coming to this show less prepared.

[00:26:08] **Ben:** Meaning that I used to have a lot of these thoughts just bouncing around in my head. And I would get to this call and I'd be, here's all this stuff that's been going on in my head. And now that I'm kind of more actively channeling some of that angst into my code, I'm feeling that I'm just, I feel let more empty almost now when I get here to do the recording.

[00:26:31] **Ben:** And, and I don't like that. I, I feel like I wanna, continue to come ready to talk about stuff and I'm trying to come up with some sort of mechanism to make that a little bit more mechanical, you know, like a little like,

[00:26:44] **Adam:** maybe the friction's not so good after all.

[00:26:46] **Ben:** yeah.

[00:26:46] **Tim:** yeah, don't, don't you have like a whole, like your own channel on Discord.

[00:26:50] **Ben:** know and right, and, and like, and I think be, so I had started that. Ben needs a minute, Ben overthink stuff. Channel to prepare for the show. And the irony is, is that I feel like I have to challenge myself to, to defend some of the thoughts that I'm having or to, or to, you know, alter some of the thoughts that I'm having and evolve them.

[00:27:10] **Tim:** And then by the time I get here, instead of feeling more prepared, I feel like mentally drained.it could be a good thing. It's good like you're getting your therapy before the show rather than coming on the show and getting your therapy here.

[00:27:21] **Ben:** I hear you. I hear you. I don't know. It's weird. It's weird. I'm, I'm, you know, I'm finding a, I'm finding my new place in the world here,

[00:27:28] **Tim:** Yeah. It's a whole new world.

[00:27:30] **Ben:** that's me.

## [00:27:30] The Morality of Using LLMs as Search Engines

[00:27:30] **Adam:** So speaking of it being a whole new world, one of the big things that's changed recently, I think, you know, for better or for worse, me personally, I have kind of noticed this habit of myself where I. I want an answer fast. Instead of like Googling it, I will use an AI tool, an LLM, and ask my question there.

[00:27:49] **Adam:** Right? so it brought up this question of like, you know, what is the morality of using LLMs like as a search engine? You know, like even setting aside the fact that, sometimes it could hallucinate an answer, that sort of thing. But just like, you know, there, there's so many different ways we could look at this, right?

[00:28:04] **Adam:** So, there's the amount of energy used to do that text generation for you, right? Like literally energy, power off the grid and, and other angles as well. So I'm just curious, like where do you guys, what's the first thing that comes to your mind?

## [00:28:21] Paying Homage to Content Creators

[00:28:21] **Ben:** Uh, so as someone who writes, I feel particularly conflicted because I wanna go to other people's sites if they have the information that I need. If for no other reason other than to almost pay homage to the fact that someone has put in the effort. So I still, my default is to Google for things. And I, you know, part of that is because I think Google is still very useful for the things that I'm looking for.

[00:28:48] **Ben:** And part of it is certainly this part of my brain that wants to fight the AI pay homage to the, to the people who put the blood, sweat, and tears into writing. but, but I am finding that I go to Google for certain types of questions and I do go to AI for things that feel like they wouldn't be available in a single blog post or article that someone has written.

[00:29:13] **Adam:** Do you use an ad blocker, Ben?

[00:29:15] **Ben:** No, I do not.

[00:29:16] **Adam:** Oh wow. We

[00:29:17] **Adam:** found him. We found

[00:29:18] **Adam:** the one

[00:29:19] **Tim:** the one

[00:29:19] **Adam:** that

[00:29:19] **Ben:** dude, I'm like the laziest least number of tools person that exists. I like the only web extensions I have are my one password. and actually, I was gonna say a cookie editor, but I think I actually got rid of my cookie editor and I just used the dev tools. Now I think that's it. I think I have my one password or the only extension I have in my te in my IDE, the only extension I have installed is my CFML syntax highlighter.

[00:29:48] **Ben:** I just use the basic terminal that ships with the a with the computer. Like I'm, I am such a non tools guy.

[00:29:55] **Adam:** You got like notepad exe tattooed on your

[00:29:57] **Ben:** You,

[00:29:58] **Adam:** my

[00:29:58] **Ben:** I have a pad of paper right next to me.

[00:30:02] **Adam:** I was gonna say like, you know, is it really paying homage to the developer if you have your ad block on and they're not getting their ad revenue from your page impressions, but uh,you're not using ad blocks, so you totally undermine my argument. Thanks.

[00:30:14] **Ben:** No worries.

[00:30:15] **Adam:** So, I mean, yeah, there, there's that, right? So, you know, it depends on what kind of information you're looking for, right?

[00:30:20] **Adam:** If you're looking at the news, if you're looking at, you know, guides for things, a lot of times people write this content specifically for the purpose of making money, right? They're posting tutorials or whatever, and they're running ads on that, and they're making money. And then, you know, the, these LLM AI companies come by and they scrape all the, the whole internet and train their models on it, and then they're, they're cutting out the primary source and just making it, you know, you get the information directly from them, which can be nice.

[00:30:48] **Adam:** It's a great user experience. for me, you know, it saves me the time of having to find the right article and it just gets formatted how I like, and there's no other garbage on the page and it loads relatively quickly. these are nice things about it, but the, the people who put the content up aren't getting the benefit from it.

[00:31:04] **Adam:** And then. Like I'm, for me, this is very close to the argument of, that we've talked about recently. if we're being incentivized to treat AI like a junior developer, then what we're doing is killing the path to future senior developers. And so when all the senior developers retire, there's just no juniors that have been working their way up through the ranks, and now all of a sudden we're like, a, the whole industry is gonna be in a crisis.

[00:31:30] **Adam:** so that, that seems like a pretty clear and fairly obvious argument for not using it as your exclusive, source of junior developers.and, and I think it's a very similar parallel to writing content, right? Like, so if people aren't writing because, there's no incentive to write, then new information isn't getting shared.

[00:31:50] **Adam:** Mm-hmm.

## [00:31:53] The Calculator Analogy

[00:31:53] **Carol:** Yeah, I saw something talking about the junior side of things, right? And it compared it to when do you give a student in like a math class, a calculator? Like you don't give 'em access to the calculator till they have the funded. Fundamentals. And the reason is because once you give 'em the calculator, they stop learning the fundamentals behind it.

[00:32:11] **Carol:** So it's the same way when I think of like what a junior engineer does versus what they just read on AI, whenever they generate, a response from some question they posed, like for me, the thing that always kept me engaged was going to multiple sources. It was getting to an answer based off of everything I found myself.

[00:32:36] **Carol:** And now I feel like I ask the question and then the question comes back to me. So polished and so pretty, and so we're refine that I no longer question the source. I just assume it's right where in reality I should still be going to all the sources to find like, is this real? Like, is my judgment the same as what this polished answer is?

[00:32:59] **Carol:** Mm-hmm.

[00:33:00] **Adam:** Fact checking is still a very important skill, or it's even more important now that we're having the answer generated for us instead of finding the answers for ourselves. Yeah. So if it says like, oh, you could just use this function, you, you could go try it. And that's, that's a low stakes thing, right? If it says, if it generates some code for you and hallucinates a function, then you're gonna get an error and you're gonna find that before you go to production, usually.

[00:33:21] **Adam:** and, okay, well that doesn't exist, so I'll have to go fix it, or write it or whatever.when you're looking for, you know, maybe something a little more nebulous, a little less technical, then yeah, that fact checking, you gotta be on point with that skill.

[00:33:36] **Tim:** So I'll throw my two bits in here. So I, I take issue with talking about. In terms of when you're dealing with companies capitalistic endeavors and using the word morality,

[00:33:50] **Tim:** right? Because morality never, I not won't say never. Morality is not the prime driver of the economy of a capitalistic society.

[00:34:00] **Ben:** for sure.

[00:34:01] **Tim:** It, it's profit, right?

[00:34:02] **Tim:** So, so when you talk about morality, you know, ver, you know, we almost set it up at the beginning, and I, and I'm gonna reframe it, but we said at the beginning of LMS versus like search, right? These are two concerns of multi-billion dollar companies, right?

[00:34:19] **Tim:** I don't care, there's no morality on either one of those companies, right?

[00:34:23] **Tim:** It's only, it's only profit. The morality, I think comes from, is it okay to take the output of people that are spending time creating content? Scraping that for free, putting that in an LLM and then reselling it.

[00:34:42] **Adam:** Right?

## [00:34:43] The Napster Parallel

[00:34:43] **Tim:** I mean, so think back in the early two thousands in the Napster days

[00:34:47] **Adam:** Mm-hmm.

[00:34:48] **Tim:** we, we as a society were,

[00:34:50] **Adam:** I mean, uh,what's Napster?

[00:34:52] **Tim:** yeah.

[00:34:53] **Tim:** What Napster, so for you kids at home who did on Napster is that was like an early kind of bit torrent kind of thing where you could like just put in a song name and you could go download a song

[00:35:03] **Tim:** digitally. This was back in the day when, when cassettes were still very much alive. CDs were very

[00:35:10] **Ben:** There was no music streaming services.

[00:35:11] **Tim:** There was no music streaming services. So if you wanted digital music for free, you would go to Napster, put in the song, download it, and it was completely a hundred percent illegal, right? there was no legal basis for doing it, but it was being done.

[00:35:25] **Tim:** And companies, Such as record companies were suing teenagers for millions of dollars

[00:35:31] **Tim:** for downloading copyrighted material. All right. Capital in the Law worked together to solve that problem. So now fast forward, we have these multi-billion dollar companies who are like, oh, well we should just be able to scrape the internet for free.

[00:35:48] **Tim:** It doesn't matter if it's like paywall or whatever. We just, you know, copyrighted. We'll just take it and scan it and we'll put it in our lms. And they're getting away with it because Cap, the law follows capital. That's all the capital is in, is in AI right now. So I, I, I'm, I don't want talking about the morality of it.

[00:36:10] **Adam:** I think we just need to throw out the window.I disagree.

[00:36:13] **Tim:** okay. Go.

[00:36:15] **Adam:** Well, so like we've said on the show before, like I personally have said, I'll, I'll take responsibility for this. Every action is political in some way, right? If I choose to use an LLM as my search engine, I'm choosing the method that cuts out that content creator. I, I don't really love that term, but like, let's just use that, right?

[00:36:34] **Adam:** The person who wrote the blog post, either because they're running ads on it or because they're trying to build their personal brand, now what we're doing is we're taking away their opportunity to get that ad revenue or to, get to know them as a person who I might maybe want to hire one day. and, so we're robbing them of that opportunity.

[00:36:51] **Adam:** They get no compensation, right? There's a lot of people that are advocating that these AI companies that are scraping the web for, training data need to compensate the authors of the data that they're scraping. I'm not here to say one way or the other, but it's an interesting concept, and I think that it at least attempts to answer the question of like, well, what, you know, what's fair?

[00:37:15] **Adam:** Right? You're, you're taking this data. I want it to be freely available to people on the web because maybe my goal is not to run ads, but just to, to be well known. I'm the guy who likes Svelte right, and I want to do that. And so that should I ever need a job in the future, it'll make it easier for me to get a job doing Svelte sort of thing.

[00:37:31] **Adam:** And when you take away my opportunity to be well known, it disincentivizes me from writing on the web. That's, that's kind of why I feel like it's a moral choice, right? Me, as the person doing the search, I, I have to try to keep that in mind because I'm making a moral decision.

[00:37:49] **Tim:** And it says, I have issue with that. Right. So it's very analogous to

[00:37:55] **Tim:** recycling.

[00:37:57] **Adam:** Okay.

[00:37:58] **Tim:** So recycling, we, we put the onus, capitalism pushes morality to the individual in a situation where they are the least impactful. So,

[00:38:07] **Adam:** totally agree with you on that.

[00:38:08] **Tim:** right. So, and I think

[00:38:10] **Tim:** there's a

[00:38:10] **Adam:** recycling is like a

[00:38:11] **Adam:** drop in the

[00:38:12] **Tim:** Yeah. I mean, home recycling is complete crap.

[00:38:15] **Tim:** Most of what you put in the recycling bin winds up in the landfill. 90%. Right. I just made that up on the spot. But it's, it's a high, it's a high,

[00:38:23] **Ben:** I think it is pretty close though.

[00:38:24] **Tim:** yeah, I mean, it's like recycling is a joke as an individual. It's the corporations, it's the companies that are creating things. They're the ones who could really push that, but there's no benefit for them for that.

[00:38:35] **Tim:** Capitalism does not reward them for that. And it's the same thing, I think with AI. It's like, because you, I think they could, but

[00:38:42] **Tim:** it's

[00:38:42] **Adam:** currently. Yeah.

[00:38:43] **Tim:** So you're saying you're making a decision as a consumer of AI to do a moral thing when in fact the individual users of AI, that should not be their decision because their decision ultimately doesn't matter.

[00:39:00] **Tim:** They, they're not the ones building these huge power stations everywhere that are raising up electric costs. It's the multi-billion dollar companies, not the individual.

[00:39:09] **Adam:** I wanna build on your, your recycling, metaphor or touchpoint or whatever we're gonna call it here. so this is exactly the, speaking specifically about recycling. This is a perfect example of one of the reasons that I think government should exist and like one of their primary functions is to incentivize the things that the free market wouldn't itself incentivize, because it's like the free market is only interested in profit, right, like you said.

[00:39:34] **Adam:** And so unless it is inherently profitable to incentivize doing the thing that's better for the planet and society in the long term, it's not going to be incentivized by the free market.

[00:39:47] **Tim:** Agreed.

## [00:39:48] Government's Role in Incentivizing Good Behavior

[00:39:48] **Adam:** in my view, government should exist and one of gen government's jobs, should be to force incentives that are for things that are good for society and for our planet and for generations to come that would not otherwise be incentivized, like recycling and like reg, you know, using regulation to say you have to, do you have to meet certain minimums for recycling and if you don't, then we're just going to financially penalize you and we're gonna use that money and like, earmark it for, you know, pulling, you know, paying people to pull plastic outta the trash or whatever it is that like, kind of like, okay, if we can't get you to do it on the front end, we're gonna come behind you, make you pay to go do it on the back end.

[00:40:29] **Tim:** Mm-hmm. I'll

[00:40:30] **Tim:** apply That, to a I A

[00:40:32] **Adam:** so and so how does that apply to AI? I think that the government should be adding regulation to incentivize, the behaviors that would. Like, you know, best treat society and, and, you know, avoid things like not having junior developers later or, so. The other, another angle I'm looking at this through is like, you know, we talk a lot, occasionally, about, like, me personally, I have, a, a ever decreasing attention span, right?

[00:41:03] **Adam:** So

[00:41:03] **Adam:** like, it's, it, I, my my attention span is getting

[00:41:06] **Ben:** he was

[00:41:06] **Adam:** and smaller by the day. I, yeah, yeah. I got it after I started my sentence. the, but like, you know, it's, it's that inability to just sit and watch a TV show. I have to sit and watch a TV show and play solitaire on my phone at the same time, right?

[00:41:18] **Adam:** Or I can't just take a shower. I have to take a shower and listen to a book or a podcast at the same time. there are times where I'm like, I get kind of burnt out on that. I'm like, okay, this one drive I'm gonna drive for an hour with no music, no radio, just like, yeah, dude. and, and. Just like, just marinated my thoughts and it, it's boring at first, but then, you know, maybe a third of the way through the drive or whatever, it starts to become this like, awesome exercise.

[00:41:41] **Adam:** And my brain starts churning on stuff and it's like, I should do this more often.

[00:41:44] **Tim:** I just wind up, my verbal Tourettes just starts

[00:41:47] **Tim:** popping out.

[00:41:48] **Adam:** And, and, but so it it's the, it, but it's exactly what I was talking about before. Like the benefits are also negatives, right? So the, the fact that I don't have to read 10 different pages on the internet to get the answer that I'm looking for, and I don't have to scroll past, you know, the backstory of why this recipe is so great to get to the recipe.

[00:42:08] **Adam:** You know, like these are things that make it, that, that are positive reinforcement to continue using the LLM to do this kind of search, but they are also contributing to making my attention span worse, right? They're reinforcing that negative behavior, and making me worse as a person. And so that's a, it's not necessarily a moral thing.

[00:42:28] **Adam:** I don't know. I'm

[00:42:29] **Ben:** Well, so

[00:42:30] **Adam:** but I, I imagine it could be twisted to, to be considered a moral thing.

[00:42:33] **Ben:** you, you mentioned this concept of doing what's good for society. And to me it, it almost resonates with the concept of the shop local movement

[00:42:45] **Adam:** Yeah.

[00:42:45] **Ben:** where people wanna shop at local stores. And a lot of that stuff that you could shop locally, you could just buy from Amazon or Walmart. But why do we shop locally?

[00:42:55] **Ben:** We shop locally to support the local community, to help support local vendors and artisans. Same way we go to like a farmer's market. and, and it's like none of that stuff we have to do, but we do it because ultimately there's a value in, in cultivating a sense of connectedness with other living human beings that, that experience the world in different ways.

[00:43:18] **Ben:** And, and to me, you know, even if you're not communing with people on other websites, I feel like just going to their sites and consuming their content, you know, in some ways is good for society. In the way that the shop local movement is good for society. And I, you know, I don't think I can articulate it any better than that, but that's, that feels parallel

[00:43:40] **Adam:** so let me throw this out there for any, for you, particularly Ben, and I mean, anybody who kind of is feeling like yeah, that, that if they, they're feeling like you're speaking their truth, as somebody similar to you who I don't do it as much anymore, but like spend a lot of time blogging over the years, it's one thing to have the traffic numbers.

[00:43:59] **Adam:** It is like a thousand percent more. Fulfilling to get a comment or a tweet or something, right? So like if you, if that is the reason that you're on the site and you're avoiding the LLM or, or whatever, if you're on the site because you want to support the person or you want to, you know, just support, DIY or, or, you know, homemade content, whatever, leave a comment, send them a tweet, say, Hey, I read this article, I really liked it.

[00:44:24] **Adam:** Whatever. just don't use an LLM to write it.

[00:44:31] **Tim:** So, all right, so you kind of sidestepped Mike.

[00:44:37] **Adam:** Did I? I, I

[00:44:38] **Tim:** you kind, you

[00:44:38] **Adam:** hit it Face

[00:44:39] **Adam:** on what?

[00:44:39] **Tim:** You, kind of did, but that's fine. Here's my real concern. So today when I was talking about my great success that I had with using LLM,

[00:44:49] **Tim:** what I noticed was, you know, it tells you the site is going to look at,

[00:44:53] **Tim:** right?

[00:44:53] **Tim:** So it's like Stack Overflow,

[00:44:56] **Adam:** Yeah.

[00:44:57] **Tim:** Exchange. It went through like 15 different sites. And, and in my mind I thought, that's great. It's collecting all these answers. I would normally Google these to find the answer to my problem. And I think, well, what's the motivation now for anyone to go post an answer there or a

[00:45:13] **Ben:** Right.

[00:45:13] **Adam:** Yeah.

[00:45:14] **Tim:** right?

[00:45:15] **Tim:** So at some point the snake is eating its own tail and there's no new data coming in, and the LLMs are gonna, the companies that have sunk literally hundreds of billions of dollars into this are gonna have to figure out how to solve that problem.

[00:45:33] **Adam:** They're gonna have to monetize. Well, yeah, yeah, yeah.

[00:45:37] **Tim:** Good content. Good content at some point has to be encouraged. And the encouragement is either recognition. Like Ben, I don't, I I imagine you don't make a huge amount of money off your blog. You

[00:45:48] **Ben:** I, I don't, I took ads off a while back 'cause.

[00:45:51] **Tim:** Yeah. So

[00:45:51] **Tim:** you're not doing it.

[00:45:52] **Tim:** You're not. It's a, it's a passion project. You're do it 'cause you love it, and that's great.

[00:45:56] **Tim:** And the LLMs are gonna continue to scoop it up and eat it, and yum, yum, yum, yum. But other folks, they're not so altruistic as you. And so there's gonna have to be some mechanism in order to encourage original content. Otherwise, we're gonna be stuck in 20 24, 20 25. Technology forever. A hundred

## [00:46:14] The Race to AGI

[00:46:14] **Adam:** uh, I completely agree with you, but I think that the impression that I get from the way that the, not from what they say, but from the actions that these companies, these AI companies are taking, because I think actions speak louder than words, is that they don't care. They are 100% invested in, we have to be the first ones to a GI and we have to

[00:46:38] **Adam:** be,

[00:46:39] **Adam:** the, the ones to become profitable first

[00:46:42] **Tim:** And that's the thing, right? If they can get a GI, so a GI, you don't need, you don't need all this learning model. You can just, it can learn on its own. But if you, they've missed that. If they, if they shoot short and they don't hit a GI and they find out it's a lot. I mean, we've been saying cold fusion, you know, the energy, not the programming language.

[00:47:02] **Tim:** It's been

[00:47:02] **Tim:** 20 years, 20 years in la, 20 years away since 1940. It's like if, if, if a GI turns out to be that kind of problem, we're in a world of hurt. 'cause all that capital, all that

[00:47:14] **Tim:** expenditure is going

[00:47:16] **Adam:** Well, I mean, there's a lot of

[00:47:17] **Adam:** people think that this, all this AI hype is a big bubble, and, and it's like, it feels to me very much like it is a bubble and that it's on the verge of popping now, you know? I'm not a professional. This is not financial advice, blah, blah, blah. But like, it feels to me like it's on the verge of popping, but it, it also feels like it could continue to be on the verge of popping for the next five years.

[00:47:40] **Adam:** Right. Like,and it's

[00:47:42] **Tim:** lot those words. I've sold all my stock and anything tech related in the past month.

[00:47:47] **Ben:** Interesting.

[00:47:47] **Adam:** And that is financial

[00:47:50] **Tim:** I'm not saying do that, I'm just saying I I don't trust it at all. I think it, we are, we are on the verge of a bubble. Not, not a, I

[00:47:57] **Tim:** don't think it's a, I don't think it's a failure. I, it, I mean, we talk about the bubble

[00:48:01] **Adam:** It's just over, over invested or

[00:48:03] **Tim:** the internet bubble back in what? The early two thousands. Right? It popped but didn't go

[00:48:09] **Adam:** Wait a minute. Are you telling me my pets.com account is not worth anything?

[00:48:13] **Tim:** yeah. So.

[00:48:15] **Ben:** sorry to go off on one tangent quickly. I was listening, I think maybe it was on the media podcast. I can't remember exactly which one, and they were saying that when people talk about previous bubbles, and they often talk about the housing market crisis and the.com boom, that those aren't really the same level of bubble that we could be in.

[00:48:36] **Ben:** And they're saying that really the most relevant one is the railroad industry. When the railroads were being built across the country for the first time. There were lots of competing railroad companies and they were actually building competing roots between cities. So as an example, like going from New York to Boston, there might be two parallel railroad tracks

[00:49:00] **Adam:** Mm-hmm.

[00:49:00] **Adam:** do you know if they had the same standard, like if they were the same width and same gauge tracks, or.

[00:49:04] **Ben:** I don't know. That's an interesting question. But

[00:49:06] **Ben:** they,

[00:49:07] **Tim:** that's been standard for, since Roman Times,

[00:49:09] **Ben:** but the, so, so the point the guy was trying to make is that, that is kind of akin to what we have now with OpenAI and Grok and, and, Anthropic. We have all of these giant,

[00:49:21] **Ben:** companies that are putting massive infrastructure into essentially building the exact same thing

[00:49:27] **Adam:** Mm-hmm.

[00:49:27] **Tim:** Yep.

[00:49:27] **Ben:** and that.

[00:49:28] **Ben:** In the same way that you don't need two railroad tracks that go from New York to Boston. There's gonna be a winner take all situation. And it's not like some companies will kind of do poorly. It's like, like, you know, 60% of that industry is just gonna disappear then that's gonna have a massive knock on effect.

[00:49:47] **Adam:** maybe initially you didn't need two sets of tracks from New York to Boston, but like now that that, no, and I mean this a hundred percent seriously, like initially there just wasn't enough railroad traffic to necessitate it. And I know they have methods for dealing with this, like sidings and stuff where they have the ability for trains to pass each other or whatever.

[00:50:07] **Adam:** But like, here it is, what, let's just say a hundred years later, whatever, there, like rail is such a commodity and there's so much traffic that like if there were, even if they were just parallel tracks from, you know, all these different routes, they would probably be more heavily used. Right? Like, and I, I think, I think that that is where the metaphor breaks.

[00:50:30] **Adam:** I don't think that we need nine different Agis, right? So

## [00:50:35] Serendipitous Learning

[00:50:35] **Ben:** One of the things that I keep coming back to in my mind is this notion of serendipity that when I look at. Sites and resources externally to Google, to ChatGPT I feel like there's a lot of serendipitous learning. I might go to a page looking for something and as I'm scrolling down I see references to other things where I'm like, oh, that's interesting.

[00:50:59] **Ben:** Lemme check that out. I open it up another tab or like, there'll be a code example. And in that code example is something that I've never seen before. I'm like, oh, whoa, that's crazy. I didn't know we could do that. And I go down that rabbit hole a little bit. I find that with ChatGPT I don't get any of that serendipity.

[00:51:16] **Ben:** It gives me exactly what I am asking it about. And unless I then go in and say, okay, now assume that everything you told me is wrong, why would that be? And then it can give me like a lot of competing perspectives. Like, unless I'm actively trying to, to sort of force that serendipity, I, I don't find, I get that happy accident learning with any of the things that I'm getting outta ChatGPT.

[00:51:41] **Ben:** I don't know if anyone else has similars.

[00:51:44] **Carol:** I was gonna say, I feel like with that, I get that, trust me, I am the internet kind of vibe. Whenever I put something in like ChatGPT, it's like I have compiled everything for you. So just trust it. But yeah, no, I, I love going to, like I said, the earlier, you know, like my, my favorite way to learn is to just find all the sources and go through it and look at what people have commented, look at other people's problems.

[00:52:07] **Carol:** Like ChatGPT doesn't do that for me.

[00:52:10] **Ben:** Yo, it's even the same with, so we've talked about MDN, Mozilla Developer Network, I think several times on this show already. like meaning this episode. And that's another thing where I could very easily go to ChatGPT.

[00:52:25] **Adam:** did you just call it Microsoft Developer Network?

[00:52:27] **Ben:** did I, I meant Mozilla Developer Network.

[00:52:30] **Ben:** If,

[00:52:30] **Ben:** I, if I, if I wanted to. You know, write some code for some browser, API or, or a JavaScript API, I could very easily go to ChatGPT and say, Hey, I'm trying to use the scroll event handler.

[00:52:44] **Ben:** How do I do that? But I still prefer going to MDN to look at the event because I know that as I'm going down, it's gonna show me little caveats about browser support, or it's gonna be like, and for performance reasons. You know, maybe you wanna put on the, you know, this flag in your object binding and, and link to this other thing about, oh, here's a new CSS thing.

[00:53:06] **Ben:** Maybe you wanna do scroll driven animations. Like, when, when people have the passion to curate content, they, I think, think more about how people are gonna consume it. But with ChatGPT, there's no curation. It's, you know, it doesn't care about the things that it's saying, it doesn't care about how it's presenting it to you.

[00:53:26] **Ben:** So you don't, you don't just. That passion comes through and, and that passion oftentimes brings with it a lot of cross-linking and serendipitous, references. And I don't know. So I still, whenever I have the option to go to documentation, I will definitely try to do that first.

## [00:53:46] The Decoupling of Labor and Capital

[00:53:46] **Tim:** So another big swerve here,

[00:53:48] **Ben:** Swerve away my friend.

[00:53:49] **Tim:** sir. I'm gonna swerve. So when, talk about, I think about morality with capitalism, which they're, they're almost antithetical, but sometimes they work together, is that the capital and labor work together, right? So you, you, you have capital that you're gonna employ. That capital is going to create labor.

[00:54:10] **Tim:** So in ai, it's gonna hire programmers, data scientists, people that are gonna build, you know, factories that generate electricity, power, plants, solar, whatever. I mean, so I, I, I think that's moral, right? You're using money to pay people to do stuff so that they can live their life and you get something, the company gets something in return. So today there was a very, TLDR had a very interesting article about the decoupling of labor versus capital. I don't know if you of you guys saw that?

[00:54:46] **Adam:** Now I have like four TDRs

[00:54:48] **Tim:** Yeah, I read 'em every day. I read 'em every day. And, and this one was super interesting. So Alphabet, which is Google, right? So to get to their first a hundred billion dollars in revenue, they needed 76,000 employees. Okay? So that's, I

[00:55:05] **Adam:** a lot of employees.

[00:55:05] **Tim:** that's a lot of employees.

[00:55:06] **Tim:** right? To get to 200 billion, they only needed to add 64,000 employees. Now they're 400 billion that they're about to be, they only needed to add 11,000 employees.

[00:55:21] **Ben:** Dang.

[00:55:21] **Adam:** Interesting.

[00:55:22] **Tim:** So you can see this graph. If you imagine that graph in your mind of the amount of labor versus the amount of capital being produced, they're going opposite, right?

[00:55:33] **Tim:** So labor's going down, and this is all pre AI stuff. This, you can't blame most of this on AI maybe a little bit this year, but labor's going down,

[00:55:43] **Adam:** Mm-hmm.

[00:55:45] **Tim:** revenue's going up. And so that's where I think it gets to what happens when labor is unimportant to capital.

[00:55:56] **Ben:** Just call it a day.

[00:55:57] **Adam:** up.

[00:55:58] **Tim:** is upside down world,

[00:55:59] **Tim:** right?

[00:56:01] **Tim:** And, and, and that is the goal of a GI, right? So a GI

[00:56:04] **Tim:** with with intelligent working is to get rid of the labor costs, which is the most, the highest cost of everything. You get rid of that you're, you're almost at a hundred percent, you know, you have some people make sure the

[00:56:17] **Adam:** We're all gonna end up like pushing it. Was it back in the old day before they had like even water wheels, they would have like ox oxen push a, a grinding wheel to like grind the, the, the millstone to grind the, the wheat. We're, we're

[00:56:30] **Adam:** gonna be doing that. We're gonna be pushing a

[00:56:32] **Adam:** turbine to, to generate electricity for the a GI.

[00:56:35] **Adam:** That's how we're gonna earn our, our lunch money.

[00:56:37] **Tim:** And I, I think that's, that's when the real questions of morality happens. 'cause what's the per purpose of a company? If they have all this capital, none of it goes to paying labor. Mm-hmm.

[00:56:51] **Adam:** So it's an interesting thought, an interesting perspective. I just want to build on that and point out that like nothing happens in like a perfect bubble and that, and you know, we already use the term bubble. I'm just saying like there's other, confounding variables, right? So like.yes. This all happened before AI, and yes, it's, you know, profit going up with, the acceleration of employment decreasing, if I'm kind of interpreting that right.

[00:57:19] **Adam:** The, the, the, the graph of employment is not, directly, well, it's probably correlated, but it's not linear along with profit. Right. It, it's kind of, it seems like it's kind of heading for an Asim tote. but there's other things at play like, economies of scale and monopoly stuff. Right. You know, Google building themselves and monopoly in various markets and that sort of thing.

[00:57:41] **Adam:** So, and, and I'm sure a thousand other variables too,

[00:57:44] **Tim:** But if you, but if you look at every other company within those big tech companies, even Amazon, which has huge labor costs, they're all falling the same trend.

[00:57:54] **Adam:** yeah.

[00:57:55] **Tim:** So

[00:57:55] **Ben:** also about to lay off a bunch of people.

[00:57:58] **Ben:** Amazon

[00:57:58] **Tim:** they did?

[00:57:59] **Tim:** Yeah. Which was, I mean, this was after this article, 'cause this article came out today. But the trend is you can do a whole lot more profit

[00:58:11] **Tim:** with a whole lot less human beings.

[00:58:14] **Adam:** Which is great as long as we get a universal basic income.

[00:58:18] **Tim:** Right.

[00:58:20] **Adam:** So

[00:58:21] **Ben:** Oh man.

[00:58:22] **Adam:** shall we wrap it there?

[00:58:24] **Ben:** Yes.

[00:58:24] **Carol:** Sounds

[00:58:25] **Carol:** good.

[00:58:26] **Adam:** Well then

[00:58:26] **Tim:** just, I just don't wanna end. No, wait, wait. I wanna end with one statement.

[00:58:29] **Adam:** Yeah.

[00:58:30] **Tim:** Let's eat the rich.

[00:58:32] **Adam:** Oh heck yeah. Eat the Rich. This

## [00:58:34] Patreon

[00:58:38] **Adam:** episode of Working Code is brought to you by Attention Deficit to sort squirrel, and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:58:45] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo.

## [00:58:54] Thanks For Listening!

[00:59:01] **Adam:** We are about to go record the after show, which is just the outro plays, and we keep talking and it may or may not be on topic. and, I think one of the things we're gonna be discussing in After Show today is, our kids and how they are interacting with AI, and seeing how like that might be what sort of tra trajectory that puts society on.

[00:59:15] **Adam:** but like I said, sometimes it's on topic. On topic. Sometimes we talk about tv. You never know what you're gonna get.and so if you wanna get access to this and every after show, including the whole back catalog, you can go to patreon.com/workingcodepod, throw a few dollars our way, and you'll get that post-haste.

[00:59:35] **Adam:** that's gonna do it for us this week. We'll catch you next week. And until then.

[00:59:38] **Tim:** We would never decouple our labor from your hearts. 'cause your hearts matter.

[00:59:45] **Carol:** Good one.
