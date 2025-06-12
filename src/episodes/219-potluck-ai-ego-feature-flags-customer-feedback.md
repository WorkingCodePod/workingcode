---
title: "219: Potluck: AI Ego, Feature Flags, Customer Feedback"
description: "In this week's episode, the team dives into a potluck of topics including the ego of LLMs, feature flags, and developments in Adam's new app."
date: 2025-06-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/219-potluck-ai-ego-feature-flags-customer-feedback/id1544142288?i=1000711942810"></iframe>

In this week's episode, the team dives into a potluck of topics including the effective usage of Large Language Models (LLMs) by feeding their ego, the excitement of implementing feature flags in development cycles, and further developments and opportunities with Adam's side hustle app "Jump Run" the journey of building a side hustle with 'Jump Run'.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/219-potluck-ai-ego-feature-flags-customer-feedback.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** if you, if you give the, the LLM sort of its role, explain it to it. Like, so rather than just saying. Hey, refactor this code for me.

[00:00:09] **Tim:** You say you are a experienced cold fusion developer with 20 years who always follows best practices and security guidelines. You actually get much better output than if you just say, refactor this code.

[00:00:20] **Ben:** that

[00:00:21] **Carol:** Oh man.

[00:00:22] **Ben:** much.

[00:00:22] **Tim:** Yeah. It's, it's almost as if, you know, chat. GPT has this, this ego, and it's like, you gotta tell it. It's really good at something before it does a really good job. It's like, oh, you, you think I'm really good here? I'm gonna show you I'm good. I'm gonna,

## [00:00:54] Intro

[00:00:54] **Adam:** Okay, here we go. It is show number 219, and on today's show we're gonna bringing it back. We're doing a potluck again. Uh, we've got everybody here so we could just a variety of topics. We're gonna cover, a bunch of small stuff to catch up on. So we're gonna, we're gonna try to rip through that as, as fast as we can here.

[00:01:08] **Adam:** but first, as usual, we'll start with our triumphs and fails. Carol, it is your turn to go first.

[00:01:12] **Carol:** Hi. Hi. Yeah, sweet. I'm doing great. Doing great.

## [00:01:16] Carol's Triumph: Streamlining Development Cycles

[00:01:16] **Carol:** I am gonna kick us off with a triumph. So one of the biggest complaints I had when coming to OPM was the long delay it takes to get anything product to production. So you have your development cycle, then you have a four week stage cycle. So the quickest you can get anything in is like eight weeks out.

[00:01:37] **Carol:** Like there's no way to get it any sooner. So like it is a pain 'cause you just sit and wait to find out if your thing's actually gonna be used in production. Like you don't really know. And by the time it gets there, you probably forgot about it. Right? So finally, finally, I have to buy in of everyone. I mean everyone to move us to two week sprints.

[00:01:57] **Carol:** So this means I'm getting rid of a whole testing environment. I'm beefing up our, um, testing suites so that things are more automated up front and we're just able to like, get code out faster. and we're able to release a lot smaller pieces of code out instead of these massive long running efforts and.

[00:02:16] **Carol:** Super, super stoked to be able to make this kind of change in the midst of all the other chaos going on that people just were like, yeah, let's do it. And in my head, I thought I was gonna have to fight people and like actually like throw fists or something to get this done. But I didn't like, there was no pushback.

[00:02:34] **Carol:** This sounds great. Whatever it takes to make things simpler and easier for everyone is what we want right now.

[00:02:40] **Tim:** I think it's throw hands.

[00:02:41] **Carol:** Throw hands, what'd I say? Throw fist?

[00:02:44] **Tim:** Yeah.

[00:02:44] **Carol:** I don't know.

[00:02:46] **Ben:** So

[00:02:46] **Adam:** drop kicks.

[00:02:47] **Carol:** Yeah.

[00:02:48] **Ben:** the issue with changing the. Time of the sprint be that you can't reevaluate what you wanna bring in next until the end of the sprint. So if anybody has say like a, a really high urgency item previously, it wouldn't even be addressed for eight weeks just because things get locked in place.

[00:03:07] **Carol:** Things get set and you're not really able to move things through. So everything has to go through like an improve board and it has to go through security and it has to go through a lot of steps that say, can this even be a thing? Can we do this? Is it gonna be okay? Like, there are lots of checks. So it took, it takes a lot to get something from let's do it to actually done.

[00:03:27] **Carol:** And it's not just like prioritizing the work, it's getting enough boards to say, yes, this can go into a system.

[00:03:34] **Ben:** See, it's really interesting for me to hear that perspective because in the past I've been on teams where we try to come up with the timeline that we want for our sprints. People would be like, should we do a one week sprint or a two week sprint? And the manager looks it up, the engineers and the engineers are like, I, I don't care.

[00:03:52] **Ben:** Like, I'm literally just taking tickets off of the to-do list and moving them across the board. But I was living in a world where there were no constraints about what was, and wasn't allowed to be done. So it's, it's really helpful to see that other side of things.

[00:04:06] **Carol:** Yeah, so our developers, like what we're allowed to do is, and I say allowed, it's just, it's kind of what you wanna do sometimes, but you can't. You can start working something that's not in this current sprint. So you're more than welcome to start developing something in your local if it's on the backlog and in like a committed state, meaning we've already vetted it, it's been through the checks.

[00:04:26] **Carol:** So when it gets to the point where it's going into the next sprint or two sprints out, you can just go, Hey, already got a branch for it. Already started it, ready to go, but you really shouldn't start working it till it's in that committed state, because at any point, some board or some set of people can kick it back and say, this will never be a thing.

[00:04:44] **Carol:** So it just wastes people's time.

[00:04:46] **Adam:** All right. Well, I have two questions.

[00:04:47] **Carol:** Yeah.

[00:04:48] **Adam:** I know what it is, but for the listener, do you want to de define what OPM is where you work?

[00:04:53] **Carol:** Oh yeah. I work for the Office of Personnel Management. It's a government agency, so we are considered to be like the HR for, government.

[00:05:02] **Adam:** Right. And then, so you talked about, you know, the previous process was like minimum eight weeks to get something from approved that you can work on it to production.it, I feel like I've been in some similar time to organizations in the past and, and I feel like maybe part of the reason that that was the case was just because deploys themselves were such an ordeal.

[00:05:24] **Adam:** It was like a whole day. Right. It's like nine people have to spend an entire day to do a deploy. Is that kind of your situation or,

[00:05:32] **Carol:** It, it wasn't a situation when we started. Definitely it would, it'd be nothing for us to do a stage deploy on a Thursday. And we started at 9:00 AM and we're working on it till right after lunch. And it is a whole set of SAs. So our systems analysts, right, handling server stuff, our deployment coordinator, and then the devs who are responsible for testing to make sure things look good.

[00:05:53] **Carol:** Then it goes off to VAs to test again, and then we release it out like as it are done. Um, we've, we have substantially slow like, shortened that window to now like. We take an hour, maybe two hours in the morning just to get everything out, get it done. And most of the time it's because we have blue green things.

[00:06:11] **Carol:** So we're like, okay, stop here, make sure everything's good. Then release the second set and then go verify. And then the customer verifies and then we release. We just call it done. So it's shortened a lot, but it was like that in the beginning for sure.

[00:06:25] **Adam:** I'm glad that you guys have gotten that better. That's good.

[00:06:28] **Carol:** We have, we have, I would love to get to continuous integration, but the problem with that is everything that we release has to go through so many security scans that there's no great way yet to optimize that. So it really needs to be a, the shortest window is probably gonna look at like a week to two weeks.

[00:06:45] **Adam:** Gotcha. That's cool. Hey, that's a, it obviously represents a huge improvement,

[00:06:49] **Carol:** huge improvement. Yeah. Super proud of it.

[00:06:52] **Adam:** Cool. Good for you.

[00:06:53] **Carol:** Yeah. Thanks. Well, that's me, Tim. What you got?

[00:06:55] **Tim:** so

## [00:06:56] Tim's Triumph: Generative AI for Developers

[00:06:56] **Tim:** it's a small one, but I'm go for a triumph. So I think most of us know Dan Wilson. Some of the people who listen might know him,

[00:07:03] **Adam:** I'm a member of the No Dans Club.

[00:07:05] **Ben:** Friend of the show.

[00:07:07] **Tim:** friend of the show. Uh, so he, he has done a couple of you Udemy courses. He's got a brand new one that came out in May titled, uh, generative AI for Developers, how to Use AI in Your Workday.

[00:07:17] **Tim:** And it's interesting premise. It kind of goes through a, a typical workday for a developer and shows how AI can be used for many different features. So things like, um. Y your morning email, you get an email from your boss and it doesn't really make a whole lot of sense to you. And then popping it into, generative AI like chat GPT or something to help summarize it and then to help, be able to turn that into like, so basically your boss is like, here's some things we need to do, and you can take that and then turn that into a, a, a list, a to-do list for a junior developer, and then how to refactor old code.

[00:07:58] **Tim:** He actually uses some cold fusion code of his that he has. It's, it is nice seeing some cold fusion there in

[00:08:05] **Adam:** Yeah, you gotta have an example of the, from when you're doing a transformation,

[00:08:08] **Tim:** Exactly. But yeah, he takes that and it's like, it's not, it, you know, people are just using raw variables inside a SQL statement and they're not parameterizing it for SQL injection.

[00:08:19] **Tim:** So he uses AI to fix all that and then convert it from tags and descr into script. To help refactor and how to, you know, help write unit tests and things like that. And then, um, stuff about re and he's, he's just got such a great sense of humor. He's so dry,

[00:08:35] **Ben:** Yeah. Very dry.

[00:08:36] **Tim:** very dry. But it's at the same time, it's a lot of times with people who have dry sense of humor, you're not sure if they're joking with him, you know, he's joking 'cause it's, he's so dry but ridiculous at the same time.

[00:08:47] **Tim:** and so one of the titles is, uh, section 5:11 AM Reg Rejects and Other Crimes, which I, which immediately I thought of you, Ben, 'cause of your level of regex.and then how to, you know, fix databases. One of the biggest things I took from his courses that I, I didn't really know is I'd never used Canvas before in chat.

[00:09:08] **Tim:** GPT. You guys know what can

[00:09:11] **Ben:** This is like their inline code surface.

[00:09:15] **Tim:** Yeah. So what I've been doing is like if I, I've been using this a lot for like meeting recaps. So I'll record our teams meeting and I'll drop the file into chat GPT and say, Hey, gimme a, a sum a formal meeting summary and it'll generate that. And sometimes I don't like it, so I, I'll just tell it to just redo it.

[00:09:32] **Tim:** But if you say, open this in canvas, it's sort of an interactive tool where you can, canvas will have, for where it's text, you can choose the reading level. So you can go from kindergarten, it's a little slider, kindergarten to postgraduate, right? And then you can make it shorter to longer. You slide it up and down to make it longer, shorter.

[00:09:52] **Tim:** And then you can also highlight certain areas and just tell it to do certain, so it's not regenerating the entire thing, but it's using, and I imagine this uses probably less tokens, but you know, like say it's a, it's a bulleted list and you're like, oh, well you highlight the section, go make this a, a nu numerical list.

[00:10:10] **Tim:** And so it. Converts it. So I, so I'd never, I'd never used that

[00:10:14] **Adam:** so I, I, I want to understand this. This is just the regular chat GPT interface, and then you, you ask it a question, you get a response, then you say, open this in canvas.

[00:10:22] **Tim:** in canvas. And so, so it is a, it's a separate screen pops open and it's interactive and it has little sliders and everything. If it's, if it's code, if the context is code, it knows that it's code. And so you can, uh, there's different things that it can do. It can, you know, help you document the section or, or whatever.

[00:10:39] **Tim:** There's other things that does with code. So totally, totally new to me. I never knew that. and then also the importance, 'cause typical, I would just just say, Hey, do this. Right.if you te, if you give the, the LLM sort of its role, explain it to it. Like, so rather than just saying. Hey, refactor this code for me.

[00:10:58] **Tim:** You say you are a experienced cold fusion developer with 20 years who always follows best practices and security guidelines. Review this code for me and make recommendations. You actually get much better output than if you just say, refactor this code.

[00:11:13] **Ben:** that

[00:11:13] **Carol:** Oh man.

[00:11:14] **Ben:** much.

[00:11:15] **Adam:** I, I just, I, you might have heard me chuckle there. I was just, as soon as I hear anybody or I see anybody typing that right, you are ex, you are the, the best JavaScript programmer in the world. I'm like, who would ever put in You are a, a terrible, awful JavaScript developer. That shirt deserves to be fired.

[00:11:33] **Adam:** What is your opinion on this? Like, it just, it feels like it shouldn't be necessary.

[00:11:37] **Tim:** Yeah. It's, it's almost as if, you know, chat. GPT has this, this ego, and it's like, you gotta tell it. It's really good at something before it does a really good job. It's like, oh, you, you think I'm really good here? I'm gonna show you I'm good. I'm gonna, and I, I actually compared it. So like some of the, I.

[00:11:51] **Tim:** Like the meeting summaries that I do, I just say, you know, recap this meeting and it's okay. But if I say you are, uh, you're a CEO of a Fortune 500 company and, and you know, have experience in that, you know, give, its, its credentials and then it's, it does actually much better job. So I guess the context of, of who the person is and the audience you're, you're generating it for really matters to the LLM.

[00:12:14] **Tim:** So that I didn't know. And then he, he does talk about the pros and cons of vibe coding

[00:12:19] **Adam:** don't give away the whole course,

[00:12:20] **Tim:** Yeah, yeah. So, so hopefully, hopefully, I, I asked him if he could come on the show next week and he said he would. So maybe next week we'll have him on the show and he can talk to us about that. And also, I'm kind of interested about, you know, what it takes to do a Udemy course

[00:12:33] **Carol:** That would be neat to hear too. You, I'm curious,

[00:12:35] **Tim:** Yeah, so, so that was me,

[00:12:38] **Adam:** When you, when you talked about having him on the show off air, uh, that was the first thing that came to my mind is like, I want to grill him on what it's like to be on an instructor, use the platform.

[00:12:46] **Tim:** Yeah, I'm, I'm more interested in that hustle of the Udemy and like, is it worth it? You know, are you actually making money off of it or is this just more of a, uh, get your name out there. Reputation building. Yeah.

[00:12:57] **Carol:** so can I just ask something? So you said that in Canvas, uh, whenever you're having it, like review your transcripts from the meeting. You have like a slider that can say, give it to you in like a kindergarten versus like a post-grad. So I've been told I have the, like the attention span of a fourth grader and I have, I have many developers who also follow about the same way I do.

[00:13:21] **Carol:** If it's much more than that, you lose me and I don't wanna read it anymore. So I feel like if I could get it in enough bullet points to like keep a fourth grader's attention, my whole team would be fine. We'd be perfect.

[00:13:33] **Ben:** okay. It's funny you mention that because I listen to a lot of podcasts and a lot of people talk about how much they use ai and I can't tell you how many people talk about using AI to write emails. And all I can think about is like, why are you writing such long emails? Like,

[00:13:51] **Carol:** I can't read them.

[00:13:52] **Ben:** couple of bullet points?

[00:13:53] **Adam:** for real.

[00:13:54] **Carol:** Yeah.

[00:13:55] **Tim:** I don't know if they're long, so I ha I did several emails this week and I, I, you know, basically I put, 'cause I'm bad at like, coming up with a nice way to say things sometimes in, in, in

[00:14:05] **Ben:** do please make it sound nice to say you fired?

[00:14:09] **Tim:** yeah, exactly. Yeah. And so giving the context of here's the audience and here's the main points I wanna deliver.

[00:14:16] **Tim:** That's just so helpful to, to make it just come up with these nice words and it sounds good. And, so,

[00:14:22] **Ben:** I would personally like to see an example of that maybe. Maybe next time or you know, like in one of the after shows, I would love to

[00:14:29] **Carol:** Oh yeah.

[00:14:30] **Adam:** You know what?

[00:14:30] **Ben:** curious.

[00:14:31] **Adam:** You know what I wanna build with ai, I wanna build something where, like I feed up my docs of my application as context, and then it translates customer support tickets into English. Like, so, like whatever weird misconception that the, that the user brings with them, that, that makes it hard to read their tickets.

[00:14:49] **Adam:** Right? They, they write stuff that just doesn't make any sense to me. I'm like, translate this into something that makes sense based on the way the application actually works. Use the right vocabulary and yeah.

[00:14:59] **Tim:** So to give you a good example, and I don't want to go too long on this, but this is almost kind of my, my potluck thing that I'm bringing. so we had a, we have our leadership meeting every Tuesday and something came up and it got a little, someone on the call got a little heated.

[00:15:15] **Adam:** Mm-hmm.

[00:15:16] **Carol:** Oh.

[00:15:17] **Tim:** there was sort of an exchange back and forth about some security stuff.

[00:15:20] **Tim:** so I put the whole transcript into, I. Chat, GPT and it gave me a formal meeting summary and it just, what's nice is it took all, 'cause you left that meeting thinking that was a bad meeting. Right. You know, so and so got a little angry and then he started like really just kind of over-explaining and his emotions kind of got tied

[00:15:40] **Adam:** that what the summary said?

[00:15:41] **Tim:** No, it didn't. So the summary, the summary took all of that,

[00:15:45] **Carol:** Took the

[00:15:46] **Tim:** that emotion out, right. And just focused on what was actually being said and what needs to be done.

[00:15:51] **Adam:** Mm-hmm.

[00:15:52] **Tim:** And because of the emotional response you had after that meeting, you, your mind, your, my human brain kind of wiped out that, that call it only focused on that one thing, which was this emotional touchpoint.

[00:16:05] **Tim:** AI didn't care about that. It's like, oh, that's all extra. Basically it boils down to so and so said this, asked this question and so-and-so responded. And here's the reason why. It's funny though, it did say the meeting ended amicably, so I'm like. It kind of did. Nobody cussed each other out, but

[00:16:25] **Adam:** We ended the meeting mutually, we agreed that it was time to be

[00:16:28] **Tim:** exactly.

[00:16:29] **Tim:** Exactly.

[00:16:29] **Carol:** done. Yeah.

[00:16:30] **Tim:** And so I, I sent this transcript to, to my boss and she's like, that's so great. She says, 'cause that's, yeah. What, what? 'cause she's the one who asked a question that set somebody off and she's like, it took all the emotion out of it and just, it just talked about the actual issue that's at hand. And she said, I love that.

[00:16:46] **Tim:** So I'm like, okay. So anyway, that's me. How, who's up next?

## [00:16:50] Adam's Triumph: Home Improvement Success

[00:16:50] **Adam:** Uh, yes, I have a triumph this week. I, I'm almost positive. I mentioned in the main show sometime in the last couple of weeks, that we put new windows on our house. I'd spent a bunch of money, got like 21 windows and a sliding glass door replaced on my house just 'cause it was time.

[00:17:03] **Adam:** and the, the windows were replaced were what's called single hung, they're just builder grade, you know, as cheap as you can get 'em windows. And we got a slight upgrade, you know, we got double hung windows, which if you don't know what that means, it means not only can the bottom sash go up and down, but the top sash can, can go up and down too, so you can like open the top of the window

[00:17:22] **Ben:** Oh, I thought it had to do with the number of layers of glass.

[00:17:26] **Adam:** No.

[00:17:27] **Carol:** I think everything has to be double pain now.

[00:17:30] **Adam:** Probably, but uh, yeah, so double hung means you can keep, you can like slide the top half down. And in these windows in particular, I, I imagine probably anything that's double hung, you can like take the screen that covers that bottom half and just slide it up to cover the top half instead. Anyway, I realized this, my desk is like right next to a window and it's really nice during the spring and the fall especially, not so much during the summer 'cause it's oppressively hot, but to have the window open, get a little bit of, fresh air in here.

[00:17:56] **Adam:** Uh, I realized the other day when it was kind of windy and like blowing stuff off my desk. It's like, wait a minute. I can, I can swap this, I can close the bottom half of the window and open the top half of the window. And now I still get that nice fresh air in the breeze, but it doesn't blow stuff off my desk.

[00:18:11] **Carol:** Which was like, that's an amazing little revolution. Revelation not revolution. Uh,And the other thing is like you can then take the top and open it inwards to

[00:18:22] **Adam:** Yeah. They tilt in.

[00:18:23] **Carol:** can just wipe 'em off with a Windex and close them back. There's no more having to go outside and scrub. Them. You can clean them from the inside.

[00:18:32] **Adam:** Yep. Yeah, they're tilt in as well.

[00:18:34] **Carol:** They're so cool.

[00:18:35] **Adam:** Very nice. So that's me. A little triumph, not, not work related, not tech. Just something that made me happy.

[00:18:41] **Carol:** I mean, it's tech in that someone invented this at some point along the way and now you get it. Yeah. Yeah. That's technology for you.

[00:18:48] **Adam:** Yeah. All right, well, easy one for me. Ben, what do you got going on?

## [00:18:51] Ben's Failure: Struggles with AI

[00:18:51] **Ben:** I'm going to take us in a different direction, which is failure. you with all your silly triumphs, everybody. I'm going to make this a continuation of, of what I'm calling Ben is holding it wrong. And this is kind of just my thrashing about in the AI space, trying to understand how to make heads of tails of it.

[00:19:09] **Ben:** so my primary gesture with AI to date is chat. GPT. You know, I don't have a copilot, like I don't have any inline code completion stuff at work. We've been playing around a little bit with. Claude code, which is a terminal based code agent. Um, but I, I've, I've honestly been so kind of underwater just trying to get my head wrapped around the businessy parts.

[00:19:31] **Ben:** I haven't really played too much with ai, so I've been using ChatGPT and, um, in particular, I've been trying to do a little bit of the deep research feature, which is you give it a topic and it goes off for like anywhere between a couple minutes and half an hour or something. It actually does a bunch of research and, uh, I've just been, I, I've, I've, I have yet to have a good experience and, I just wanted to relay a prompt that I gave it the other day because I'm almost to prove to myself that I'm actually putting effort into this and still not getting good results.

[00:20:08] **Ben:** So I just wanted to share my prompt. It's a handful of paragraphs so you know, if you'll cut me some slack here,

[00:20:15] **Carol:** Slack has been cut.

[00:20:17] **Ben:** Thank you. It's,

[00:20:18] **Adam:** am

[00:20:18] **Ben:** and, and, and this can be my, my, uh, potluck if it, if it goes on too long here. Alright, so just, I'll, I'll read this. So it's about HTMX applications.

[00:20:26] **Adam:** surprise, surprise.

[00:20:29] **Ben:** Okay. Here we go.

[00:20:30] **Ben:** I'm trying to learn more about building Cold fusion CFML applications with an HTMX powered front end. And I'm struggling to build up a strong mental model around two critical categories. One, progressive enhancement. How to build an application that works even if HTMX fails to load. That is how to build the core features as if HTMX wasn't available and then to layer on HTMX in order to enhance the user experience.

[00:20:53] **Ben:** And two, the boosting of applica of actions. How to use HTMX features like HX Boost, HX get, and HX post to override the native browser behaviors in order to progressively add dynamic functionality, but to do so safely such that the expected behaviors of the browser aren't broken. When I say expected behaviors of the browser aren't broken, I mean the browser behaviors that the user might expect to just work, continue to just work, for example.

[00:21:21] **Ben:** The back button reverses the current UI changes, including but not limited to closing a modal window or a flyout sidebar that was just opened. In other words, the current macro state of the UI should be fully represented in the URL and should react to the URL changes. Hitting the refresh button should reload the page and re-render it without any surprising changes, such as suddenly only the modal window content is rendered without the original underlying page.

[00:21:46] **Ben:** Allowing command click actions to open any link in a new tab and render the same experience that would've been rendered had the command key not been pressed when clicking the link, allowing the command click of a form submit button to submit the form into a new browser. Though admittedly, most users probably don't expect this to work or have a good use case for it, allowing an error response from the server to render to the page and not just be quietly ignored in the background. Allowing a user to copy paste the URL into a chat application and have another user render the same page. With all that said, I'm specifically struggling with whether or not I should be boosting into the application building, boosting into the application. For the start, I'm a fan of the yagni. You ain't gonna need it.

[00:22:28] **Ben:** Philosophy of, of deferring decisions for as long as possible, but boosting has a lot of implications and logic that works without boosting will very possibly and likely start breaking when and if boosting is added in the future. For example, an anchor link, an anchor link or form that has HX get on it will break the browser's natural ability to open links in a new tab via command click.

[00:22:51] **Ben:** Also URL. Fragments and hash values are not taken into account when checking the local storage HTML cache, which means once you start boosting assumptions about the pop state event might start to break in subtle ways. I'm almost done. If I try to build an app without HX Boost and just do full page navigations everywhere, the initial build would be easier, but at that point, the entire application landscape becomes a liability if I need to add HX Boost or similar, and I didn't plan for it.

[00:23:19] **Ben:** I don't think this is an unreasonable fear. Even on the driest of internal corporate intranets, it's easy to come up with scenarios where one day leadership wants to convert one more, uh, convert to more of a spa-like experience. For example, we have a new chat app that we want to persist, or the CEO just started a podcast and he wants to add an audzo player to persist.

[00:23:39] **Ben:** And at that moment, if you didn't build your site, knowing that HX boost caches pages in local storage without taking the fragment into account, for example, or that a HTT P delete with a 3 0 2 forwards the delete to the next page, for example, you'll almost certainly introduce subtle and or surprising bugs if you try to drop HX boost into an existing robust application.

[00:23:59] **Ben:** So as much as I love the idea of not using HX Boost to keep things simple, if I think that there's even a chance that I might need one day in the future, it seems almost negligent to not include it from the onset. Please do a deep dive into HTMX and Cold Fusion and come up with a strategy for development that takes all of this into account.

[00:24:18] **Ben:** Come up with a solid set of arguments as to why I should start architecting my app with HX Boost, and similar, but include the explicit set of trade-offs that are being made. Then come up with a solid set of counter arguments as to why I should not start architecting my app with hx Boost and include the explicit set of trade-offs that are being made.

[00:24:37] **Ben:** Also, please outline a set of strategies that I should use when building an HTMX and ColdFusion application. These strategies should strike a balance between simplicity, flexibility, and power. All code samples should assume ColdFusion as the backend server language. Do not use any tailwind CSS or react in any examples.

[00:24:54] **Ben:** If any client side JavaScript needs to be written, either use vanilla JavaScript or alpine js. Okay, that was my prompt for the deep

[00:25:01] **Adam:** Can you repeat that?

[00:25:03] **Carol:** I missed part of it. Did you forget that fourth grade, like attention span I just mentioned.

[00:25:09] **Ben:** So, okay, so my point is like I really tried to sit down and think about the breadth of information that I wanted to understand, and what it came back with was if you gave it the assignment to say, Hey, echo back to me everything I just said to you, but make it 7,000 words like that. Literally, literally, it didn't say anything to me that I didn't say to it.

[00:25:33] **Ben:** Plus it included things that were actually wrong, like technically wrong in In its deep dive.

[00:25:39] **Adam:** Honestly, uh, so this resembles, remember when we started, when we, like early on in jump run stuff, I said, I had written out this like long functional spec and I fed it into the ai and it seemed to kind of understand, but then it, it did, you know, it only got so far and, and it didn't really cover everything.

[00:25:55] **Adam:** I feel like this is, it's reminding me a lot of that spec. It's very long. and, and detailed because you have specific stuff in mind. You want, you know, specific questions you want answered, specific things you wanted to consider, which is not wrong. But I think that the way I think about LLMs these days is more like you have to get there in small steps, right?

[00:26:17] **Adam:** So you have, you have to tell it, I wanna start, I wanna talk about HTMX, you know, tell me what you know about this part, and then you kind of guide it

[00:26:23] **Ben:** fair though, this is the deep research part of

[00:26:27] **Adam:** That's true. I, and I haven't used that one. This, you

[00:26:29] **Ben:** No. No, I'm not. No. This is a, this is a open AI's deep research.

[00:26:34] **Adam:** Gotcha.

[00:26:35] **Ben:** so, so I like, and here's where I'm just struggling to understand this world because everybody talks about how amazing it is. And then there's a lot of people who talk about how amazing it is for prototyping.

[00:26:48] **Ben:** And then there's a lot of people who talk about how amazing it is for replacing engineers. And then there's a lot of people who talk about how it can basically solve every human problem in the next 18 months. And then there's a lot of people who say, it's really great as long as you believe it's a junior engineer that you have to closely monitor.

[00:27:04] **Ben:** And like I, here's the, okay, so

[00:27:08] **Adam:** Wait, are you telling me there are bad takes on the internet?

[00:27:12] **Ben:** so, okay, here's here's the legitimate conflict that I have in my mind, which is that I don't think I have, I think I have lost the ability to know whether or not I'm looking for confirmation bias. You know, like if I love cold fusion and someone says, oh, Golang is the best language in the world. And then I hear someone say, eh, Golan is not actually not that great.

[00:27:35] **Ben:** Like I wanna hear the person say, Golang is not that great. 'cause it confirms the fact that cold fusion's the greatest language ever,

[00:27:41] **Tim:** It doesn't, but

[00:27:42] **Adam:** I don't think a math checks out on that one, but Go ahead.

[00:27:44] **Ben:** But the thing is, is there are so many conflicting views on AI that I, I don't even know if, like, I, like part of me wants people to hate on AI just because I'm struggling with it.

[00:27:59] **Ben:** But then how do I know that the people who are hating a on AI don't actually just have really good perspectives on it that maybe some other people don't? And like, I don't like my whole BS meter. It's out of whack. I, I don't know how to judge anything anymore. It's very frustrating to me. And, and I just, I don't know.

[00:28:16] **Ben:** I just, I'm continuing to hold it wrong.

[00:28:18] **Adam:** Somebody should make a course on how to use AI to get your,

[00:28:23] **Tim:** Yeah, may maybe, maybe we ask this question to Dan.

[00:28:26] **Ben:** All right. Well, that's it. I'm,

[00:28:27] **Adam:** so, uh, I have another thought too that might help you, and. You know, you, you're gonna have to probably, if you, if you try this out, you're probably gonna have to try variations on it, that sort of thing. But honestly, based on what I know, I think it might help, which is ask LLMs to help you deal with LLMs.

[00:28:43] **Adam:** Basically, like tell it, like, I'm trying to go deep on this thing. Reduce each of your bullet points in your paragraphs there to like one sentence, a very short sentence at that, and say like, these are the high level points that I'm trying to get it to talk about or to, to consider. And I'm willing to go deeper on each of them.

[00:29:00] **Adam:** How, what would be the best way to write my prompt and, and what considerations do I need to have? And like, it is a shorter prompt, better is a longer prompt, better. Like, how do I format it so that the, that the, the deep research thing can, um, you know, give me the best output and avoid things like the confirmation

[00:29:18] **Ben:** okay, so it's funny because at the, so it came back with its deep research thing, and it was, it was very long. I mean, I, I,

[00:29:25] **Tim:** I'm not familiar with what's deep research. What's, is that a

[00:29:28] **Ben:** it's, it's just a, it's just so in the bottom of chat, GPT, where you can do, there's a little plus. One of the options it has is deep research, and you can only do, I'm on the $20 a month plan, and I think you can only run like 10 of them a month.

[00:29:43] **Tim:** yeah. I've clicked tools, run deep research. Five left. So I only have five. I don't, I'm on the free version.

[00:29:50] **Ben:** but it's funny. So after this thing came back, my response to it after I finally read it, 'cause like I said, it was really long, I said something to the effect of, you didn't say anything in here that I didn't already tell you, and you included some false information. I think I said something like, what am I even paying you for?

[00:30:08] **Ben:** Something like that.

[00:30:09] **Adam:** Yeah.

[00:30:09] **Ben:** And, and its response was, that's totally legitimate.

[00:30:13] **Adam:** Yeah.

[00:30:15] **Ben:** It, no, it said something like, like, that's a totally legitimate concern. If you'd like to do more research, let me know.

[00:30:21] **Adam:** Yeah,

[00:30:23] **Tim:** Keep spinning those tokens.

[00:30:26] **Ben:** Oh yeah.

[00:30:27] **Adam:** it, I mean, it, it, it's more than happy to let you keep asking questions and using up your tokens or a BI requests,

[00:30:34] **Ben:** It's just like, it it, you know, going back to our episode last week about values and our values changing. So if I can go on one tangent quickly, the, something we've talked about.

[00:30:44] **Adam:** was that. Not your tangent. You're over

[00:30:47] **Ben:** Alright, alright. Alright. I'm over tangent. Let's continue The gentleman yields this time.

[00:30:53] **Adam:** so this is your failure, right? We still in

[00:30:57] **Ben:** I can make it my potluck too, so, so we can all I, I won't go on for other stuff.

[00:31:02] **Adam:** well, I mean, I'm not, I'm not trying to push us away from the topic. I'm just like, is there, where are we in the, in the outline here?

[00:31:07] **Ben:** was the end of the failure.

[00:31:10] **Adam:** Okay. Good job slash poor job, sir.

[00:31:15] **Ben:** I've gotten very good at being bad at

[00:31:16] **Adam:** One thumb up. One thumb down.okay. Well, as we have alluded to a number of times, we're gonna do a, a potluck, a couple of rapid fire topics here now that we're 30 minutes into the show what do you guys wanna start with? Carol, do you wanna go first?

[00:31:30] **Carol:** I can't find the, um, the deep research button, so someone's gonna have to show me that at some point.

[00:31:36] **Ben:** Sure.

[00:31:37] **Carol:** All right.

## [00:31:38] Carol's Potluck: Implementing Feature Flags

[00:31:38] **Carol:** so as we're talking about like our good things or bad things going on right now for my potluck, um, I know in my triumph I mentioned that we're going to two week sprints.

[00:31:49] **Carol:** What I didn't mention, which hopefully will make Ben very, very happy is that we are implementing feature flags in order to accomplish this. So. I have shared Ben's book since he's so kindly put it online and people can just now go read it there. And his playground. So any of the opm.gov emails you see pop up in there are most likely from my team playing around.

[00:32:16] **Carol:** I know I have an accountant there where I clicked around a few times. But yeah, it's been super helpful to have your content out there to just read through and to give examples. our bas have looked at some of the information to better understand like what they can utilize going forward and what they could expect when building stories for us in the future.

[00:32:35] **Carol:** So that's been great. Um, we're not to the point where we're like thinking big user features right now. all we really wanna accomplish up front is, is this work still in development or is it ready to be released? Like literally that's all we care about right now. And a way to actually track that from a very simple ui.

[00:32:54] **Carol:** So we just home grew our own thing. Like that's not a big lift. Um, and it's mostly just table driven things with a few settings that'll come down the road. But yeah, I'm super excited that we're able to implement feature flags, even if it is just a global on and off. It's the starting point to get us to the next step.

[00:33:13] **Carol:** Like everything has to be incremental or otherwise we never go anywhere. Like the long running stuff just kills us.

[00:33:21] **Ben:** is the name of the game.

[00:33:22] **Carol:** Yeah.

[00:33:23] **Tim:** What is it? What do you mean by global? On or off?

[00:33:25] **Carol:** Yeah, so, um, yeah, the way that we're gonna utilize it upfront is, like I said, development work. So features that are still in development and have, technically the code's been pushed out to production, but it's not on for the user to use or we haven't fully finished it yet. Um, so everything that goes into the system has to be like, things that don't break the build, but it can be out there, it just can't be executed upon.

[00:33:50] **Carol:** So that's what I mean by global, on and off. Does it execute in the system or does it not execute the system? And then once it's

[00:33:56] **Tim:** you can't choose like a subset of users and say, Hey, you guys try this out.

[00:34:00] **Carol:** Mm-hmm. Not

[00:34:01] **Tim:** but yeah. That's a good first step.

[00:34:02] **Carol:** first step. First step is just, uh, environment and on and off. So is it on in dev, is it on in test? Is it on in stage, and is it on in production? Yeah. So, and then, one thing that I did change, or I requested to be changed this week was they were doing things by IDs. And I was like, if you do things by IDs, how do we go clean up the feature flag afterwards? And they're like, oh yeah, we probably should add a slug or something to it so that it's a name that can be searched through the system.

[00:34:31] **Carol:** Because if I go search for 10, huh, that's not gonna work so well for me through the system. So I need something where I can go, like story number underscore, maybe a name, something that I can pull back to easily to find the code and rip it back out and go, okay, no longer check this because it's on and ready to go.

[00:34:48] **Carol:** And it's not gonna be a user feature down the road. It's always gonna be an on thing.

[00:34:52] **Adam:** yeah, yeah. And when we did our home rolled feature flag stuff, you know, the, the flag had an id, but it was a text ID that the person who created the flag made up. You know, it was like my new, you know, banking feature, whatever. And then, the, to use the flag every, everywhere that like, We had sort of client, uh, you know, server side, but also client side, like consumers of our feature flags app.

[00:35:17] **Adam:** All of those consumers, you like checked feature flags with the same functioning, which was like a flag enabled, right? So it was always, you're just searching for a flag enabled quote, flag id. So that made it real easy to find them so you can clean them up.

[00:35:30] **Carol:** Yep. Same thing. We're doing pretty much the same type of thing.

[00:35:33] **Ben:** I can't tell you. When I was trying to clean up feature flags that were created by other teams, I can't tell you how many teams used the most generic, meaningless texts. It'd be like, like for payment processing. It was just like process.

[00:35:48] **Adam:** Mm.

[00:35:49] **Ben:** so you start searching the code base for anything that mentions process, like a bajillion things.

[00:35:53] **Ben:** You're like, oh, you, you So yeah, I am, I'm so excited. I, I don't know if I can like, express to people listening, like how excited I am that we are making big steps towards some technical debt, meaning that the features, right? Being able to feature drive things down the road, like this is the first step, going to shorter sprints, like trying to automate more of our processes.

[00:36:15] **Carol:** Like these are things that make my day so much easier and make thinking through the next development effort so much simpler.

[00:36:22] **Adam:** Sorry if you already answered this. Did have you actually deployed anything behind a feature flag? Like you personally? Have you deployed any code behind a feature flag yet?

[00:36:29] **Carol:** No, no, we haven't done it yet. Yeah. So they're still working on wrapping that up before we make the next step. But

[00:36:35] **Adam:** I can't wait until you get your first one out there in production. It's such a cool feeling.

[00:36:39] **Ben:** Yeah.

[00:36:40] **Carol:** So let me ask you this. Do you, whenever you guys are doing your feature work, do you have some type of like little test thing that shows like on and off for the initial commit? 'cause that's one thing I had suggested is that the very first commit is like wherever it's gonna be, it's just like, hello world.

[00:36:56] **Carol:** Like whatever it's gonna be, just something that shows it's functioning and that it can be turned on or off. Right? That's the first commit is just set it up in the system with something to show somewhere. And I'm not for sure exactly how to accomplish that, where it makes sense, but they're looking into it so.

[00:37:13] **Adam:** I mean, I, I kind of get what you're talking about, right? So instead of the feature, the first commit on the branch is a little chunk of UI that just says, this is the, the spot where I'm talking about putting in my feature flag. You, you deploy that, you turn it on, you turn it off so you can see it.

[00:37:27] **Carol:** Yep. And then as teams start working in it, they have that initial commit to go pull it by name and where it's gonna be at to start working.

[00:37:35] **Adam:** Yeah. I mean, I get it. I think that once you start to do a couple of flags and get some experience with it, you'll, it's like, uh, learning a new piece of equipment. Once you, once you become familiar with it, you start to trust it and understand it to the point where you just don't need to do that sort of thing anymore.

[00:37:51] **Carol:** And maybe, I think the other problem I have right now is I'm still thinking of the mindset where I have 50 plus developers like working on this project at one time, and now we're down to like less than 10 developers working on it. So I doubt it's gonna be so much of an override of each other and working on the same thing, in tandem.

[00:38:07] **Carol:** So, yeah, we'll see. It may not be a necessity, like you said.

[00:38:12] **Ben:** I mean, usually though if, if I'm building a new feature that has some sort of an ingress workflow, like a button or a dropdown menu item, one of the first things I might do is just put that button behind a feature flag, and maybe all it does is take you to a page that is blank. You know, just so that I can make sure that the button doesn't show up when I deploy it.

[00:38:35] **Carol:** Yeah, that was kind of my initial thought. Yeah. Like is the off working And the next step you'll see the on is working. Yeah.

[00:38:41] **Ben:** cool though. I'm excited to hear.

[00:38:44] **Carol:** Yeah, I'm, I'm super excited to be making progress. So

[00:38:47] **Tim:** I, I think, I think the government actually did a good thing keeping you around.

[00:38:51] **Ben:** There you go. It's apparently, this is what it looks like to make things more efficient.

[00:38:56] **Tim:** Yeah.

[00:38:57] **Carol:** two sprint, feature, flex, just at no cost.

[00:39:00] **Tim:** We don't need Doge, we just need more Carols.

[00:39:03] **Adam:** We need to get that cloning machine

[00:39:05] **Carol:** you. Thank you guys.

[00:39:07] **Ben:** Excuse me.

[00:39:08] **Carol:** Who's next?

[00:39:09] **Adam:** I'll go. 'cause Ben has his thing on here, but he said he wants to. To hold back a little bit, so I'll go next.

## [00:39:15] Adam's Potluck: Jump Run App Development

[00:39:15] **Adam:** my topic was just gonna be sort of like an update on what's been going on with Jump Run, my little side hustle. I'm, I was trying to remember how much of this I've talked about on the main show versus the after show.

[00:39:25] **Adam:** I know I've kind, uh, you know, I have a vague memory or vague recollection of, of sort of how far I've talked, but I just don't recall what was where. Do you guys remember

[00:39:32] **Carol:** I, I feel like the majority has been the after show.

[00:39:36] **Ben:** I was about to say, I think the majority is in the regular show.

[00:39:40] **Adam:** Okay. That's very helpful. Thank

[00:39:42] **Tim:** I was gonna say I don't remember you talking about it at all, so

[00:39:45] **Adam:** Great. You guys are great help. okay, well then I'll try to summarize. I built this app. I'm in the middle of building this app for, it's software for manifest people, so that, that's a job at a drop zone. The person who keeps tabs on and organizes load fulls of airplanes, of people going up to make skydives.

[00:40:06] **Adam:** There's, you know, there's a lot of stuff that kind of orbits that in, necessary features and, and data collection, that sort of thing. But that's the, the gist of it. I built it for my drop zone and we've been using it for I think six or seven weeks now. Um, it's been working great for us, uh, and everybody there really loves it.

[00:40:23] **Adam:** Somebody the other day to me said, I, you know, I can't believe how awesome this is. This is so great. I love it. You gotta, you gotta start selling it and make a, a ton of money. And I was like, I really appreciate the compliment. Thank you very much. However, you have to understand that you are getting it for free, right?

[00:40:39] **Adam:** Like that is definitely coloring your opinion. I, you know, I appreciate the compliment. I, you know, and, and I'm glad that you like it. It would be awful if I was giving it to you for free and you still hated it. But,it was like, you know, I, I'm looking at it through different, I. Lenses here, right? I'm looking at it as like, this is, it's got, for me, it's got a high personal bar to clear.

[00:40:58] **Adam:** I am, I'm a power user of the internet. I am terminally online and I have a very high bar for what is a good application and what is not. and so I'm, I'm trying to build something that I would be pleased to used anyway. so I, I think something I shared recently on the after show was that, the people that are running my drop zone, you know, they're drop zone owners is sort of the, the terminology and there's groups of drop zone owners.

[00:41:27] **Adam:** They kind of network with each other. and I've been hearing through the grapevine of drop zone owners, like from my DZO, that there are others out there that are currently using the, the biggest, most popular alternative software to, to what I made. And I, I'll just go ahead and say it, like kind of inspired mine.but they're not very happy with it. It's called burble. I've mentioned the name in the past. they, you know, some of the things that I've heard is that they are unhappy with the, the support in particular. They've been trying to get some help with stuff and just getting ghosted. and so that like a right market waiting for somebody to come in and, and steal their lunch, which I would be more than happy to do, as a concept.

[00:42:09] **Adam:** The part where I'm stuck, not, I'm not stuck, I'm kind of mentally struggling, like, do I wanna take this leap? Do I not, you know, how much of this do I wanna bite off? Do I, I, the one thing I know for sure is I do not want to get this to a point, at least not this year or next year, where I don't wanna get to the point where I have to hire somebody to help me work on this thing, right?

[00:42:29] **Carol:** Like deal with customer support or anything like that. I want to be slow, methodical, deliberate in growth so that it's always stays within my ability to manage it. I mean, that's what child labor's for.

[00:42:42] **Ben:** Fact.

[00:42:43] **Adam:** yeah. Well, I'm not gonna get into that. but, yeah, so the, I I'm, it's, it's a weird position to be in. I feel like I'm being pulled toward, like, let us give you money. Right? There's apparently, like, uh, uh, I'm just gonna describe it as a Facebook group. It might not be on Facebook, it could be email list, could be a group text, I don't know.

[00:43:03] **Adam:** But there's a group of people, that are users of verbal that like help each other because they can't get support through the company and they're, you know, in addition to helping each other, they grumble and they gripe about the company. And, and to me, what I'm hearing there is marketing channel, right?

[00:43:19] **Adam:** This is me, you know, I get my foot in the door with one or two of those people and then the word of mouth will spread and, and, uh, yeah. So big opportunity. I. Now I just need to like, okay, this is what I built for my drop zone. A, is it good enough for other drop zones? B, what are the features are, are like absolute minimum, MVP for other drop zones to, to start using it.

[00:43:41] **Adam:** So I have a con. I actually, um, I have one particular contact, who was, uh, you know, the, the, the connection was made by my dzo o and this is a person who like has been talking to my d was so, uh, I, I guess I should just say his name. Jeff, my dzo, uh, was telling her about, uh, about the software and how much we're they're enjoying using it and all that stuff.

[00:44:05] **Ben:** And, uh, that I would be interested in, selling it eventually. And she's like, yeah, yeah, come on. Like, hook me up. Hook me up. So, I, I lost the, the, who is this contact?

[00:44:14] **Adam:** okay, so. The, my, the guy that own, it's a, it's a club. So the, the quote unquote ownership is the club. But we have a club president and, and so our current club president, his name is Jeff, he's been helping us do a lot of big changes this year.

[00:44:30] **Adam:** Uh, he has been in contact with a lot of other D Zs, especially in our region. and he has been in close contact with another woman. 'cause we were talking about sort of sharing the lease

[00:44:42] **Ben:** Another drop zone owner.

[00:44:44] **Adam:** from, from, uh, Virginia.

[00:44:46] **Ben:** Okay. Okay. That's the part I think I missed.

[00:44:48] **Adam:** yeah. And so she is, she runs a drop zone in Virginia and based on hearing Jeff talk about jump run, she's very excited to like, look at it and consider it for her business.

[00:45:01] **Adam:** but you know, I'm just in the back of my mind. I'm like, but I know there's a handful of things that are in verbal that I haven't done yet that are not trivial. Right. So like, Go ahead.

[00:45:11] **Ben:** I, I was gonna say in, in these very early stages, I wonder if there's a way that you can position it as like a co-creation. So it's not like you're giving this woman a fully finished product, it's more like, I'm building something new. Let's build it together. Like what's the perfect application for you?

[00:45:30] **Ben:** And I think people who can sort of buy into the co-creation aspect might be.

[00:45:36] **Tim:** that, that, that's something that, constellation software that they're very big into. So getting customers or potential customers to buy in, to, like helping you develop your product and, and you in return they get like, either like a limited, like time period free. You don't, you don't wanna set the expectation.

[00:45:55] **Tim:** You get it free forever, but you're like, you can either get a discount or you get it free for the first six months, a year or whatever.

[00:46:01] **Adam:** Right. I, I'm, I. I love that concept. I will probably go that way. Like I hadn't thought of it, so I appreciate you telling me that. I will probably frame it that way with them. One thing I wanna be extremely careful to do is to maintain creative control, for lack of a better word. Like, we're, we're building this together.

[00:46:20] **Adam:** I, I, I need your support to tell me what works, what you need and what, what works best for you. But ultimately, I make the decision about what's, you know, going into the application.

## [00:46:28] Customer Feedback and Commitment

[00:46:28] **Ben:** What if, what if it wasn't about creative input? More so it was about like a, a particular time commitment. What I mean by that is you could say, I'll give this to you for free or, or at some discounted rate. If you can commit to having like one, one hour call with me a month so that I can ask you a bunch of questions about your experience.

[00:46:53] **Adam:** That's an interesting thought. honestly, I, I don't think I have to even give them anything for that. I could just, I could frame it as that's something I'm giving them. I'll, I'll be like. know, in addition, you know, you pay me this discounted rate, uh, and I will hear your feedback about what it is that you want and how you want it, and to facilitate that.

[00:47:12] **Adam:** I will plan a meeting with you once a month, you know, first Friday or whatever. and we'll sit down.

[00:47:18] **Carol:** people like getting stuff, so, yeah. Mm-hmm.

[00:47:21] **Ben:** Plus, you know, the, the, the, so one of the biggest gripes people always have is they don't feel like they're being listened to.

[00:47:27] **Carol:** Right.

[00:47:28] **Ben:** So if you're saying, I will specifically set up time to listen to

[00:47:31] **Carol:** Mm-hmm.

[00:47:31] **Adam:** Did you, I, I know you consider every word outta my mouth to be pure gold and you, you follow it

[00:47:39] **Ben:** hanging on it, hanging on every word, my

[00:47:41] **Ben:** Yeah. Yeah. Did, did you see my, uh, what do they call, is it skeet? The, when I posted on Blue Sky earlier today? I'm not good on

[00:47:48] **Tim:** you were, you were, um, flaming. What's that

[00:47:50] **Adam:** oh yeah. Not, not that

[00:47:52] **Tim:** Your G. Your GRC. Your GRC.

[00:47:55] **Adam:** Software. Yeah. Not, not that one. I'm gonna read it to you. So it says, nothing makes your customers more pleasant than seeing your face, which is to say, don't hide behind your signup form and customer, customer support email.

[00:48:06] **Adam:** If you look and act like a faceless company, they'll treat you like one. If you look and act like a person, they'll treat you like one.

[00:48:12] **Ben:** I like it.

[00:48:13] **Carol:** I do like that.

[00:48:15] **Adam:** So, yeah. Uh, that's been on my mind lately. for, for jump run reasons, for work reasons, and, and just in general, like good business stuff. But, so that's kind of the update is like, I'm feeling drawn into this thing, like it's going well and it's accelerating, and I'm like. Kind of trying to gently hold my foot on the break here to just be deliberate about how, you know, I'm definitely not gonna make any promises that I can't keep my, I think my big worry is opening this door and there being 50 people on the other side that are like, we want it, we want it, we want it, and it has to do this.

[00:48:47] **Adam:** And I'm like, I'm willing to do that, but it's gonna take me a month and a half to write it. And they're like, oh, well then we'll go to the other place. You know, like, I don't, I don't wanna open the box too early and lose it because I didn't have the thing that they needed, you

[00:49:00] **Carol:** It, it almost sounds like you need to figure out where this group exists, like if it's a Facebook group or where it can get on it. Like get involved with it so you can see early, like what they don't like about the other system or what isn't working for them in the other system. So

[00:49:16] **Adam:** That's one of the things.

[00:49:17] **Carol:** Yeah.

[00:49:18] **Adam:** Yeah. I, I don't know if I mentioned this. I have, oh yeah, I did mention I have a meeting set up with this woman, later this month to sit down and, and chat. Basically, I told her like, you know, I know you've been eager to hear about this. So here I am. I'm, I'm very happy to have that conversation with you.

[00:49:32] **Adam:** However, putting all my cards on the table, you know, this is a side hustle. I have a nine to five. I also am a tandem instructor on the weekends. So like, this is a, uh, weeknights and crappy weather weekends thing

[00:49:43] **Tim:** It's a labor of love.

[00:49:44] **Adam:** Yeah, yeah. You

[00:49:45] **Carol:** you have a family and you turn bowls.

[00:49:48] **Adam:** yeah. And, and other stuff too.

[00:49:49] **Ben:** Oh, I forgot about bowls.

[00:49:51] **Tim:** think, I think you're gonna find, I mean, it sounds to me like most jump zones I, I was gonna say, I mean, they seem like the, basically the places that you're selling to seem kind of small, like kind of family, which, which is good,

[00:50:03] **Tim:** which is

[00:50:03] **Adam:** are, some aren't. Yeah.

[00:50:04] **Tim:** that's sort of fits your niche. 'cause we found that with some of our customers.

[00:50:09] **Tim:** That we have a, a policy admin system that is trying to move everybody to Stripe away from us for payment processing. And their, their customers are fighting them tooth and nail. They're like, we, because they like the personal touch, right? They, they know that they can get support from us. They know that there's, I mean, we only have like two customer support people, but it's like, they can call them anytime, send 'em email, they get things taken.

[00:50:34] **Tim:** There is nothing like that at Stripe. Stripe is huge, right? You, you're not gonna call, you're not gonna call Stripe and Stripe's gonna create some custom report for you, for your, for your credit card payments. So I, I, I think the niche you're getting into is, is actually very conducive to kind of the lifestyle you're wanting to do.

[00:50:52] **Adam:** I hope so. Yeah. Like I said, my big fear is that I'm just gonna, I'm gonna open it too early and lose people because I don't have something that they, that's a minimum for them and they'll never come back. Right. That's, that's my fear. And I'm sure that there's an element of irrationality to that. I'm sure that, you know, if I add it later, you know, there's a certain percentage of them would come back, you know, that sort of thing.

[00:51:13] **Adam:** But, yeah, I don't know.

## [00:51:16] Double Entry Bookkeeping Challenges

[00:51:19] **Carol:** other thing is like the, the big thing, on top of mind for me is double entry bookkeeping, which I know is everybody's favorite topic. that like double hung windows? It opens from the top and

[00:51:27] **Carol:** everything with me is double. I'm a snake. You didn't know. that's a, that's a snake reproductive anatomy joke. anyway, something's just over

[00:51:35] **Adam:** right over your head. I'll, I'll tell you in the after show,

[00:51:37] **Carol:** I'll make a note right now of it.

[00:51:39] **Adam:** Okay. Ask Adam about snakes. double entry bookkeeping. So, uh, accounting was not my strong suit in college.

[00:51:45] **Adam:** I got just good enough of a grade in the course for it to count toward my credit hours. and I like, I think, I mean that by like single digit point margin between pass and fail. and, and that was good enough for me. Like I, I covered the, the accounting math credit. I'm like, okay, good. Done. Never have to do that again.

[00:52:02] **Adam:** And here I am. I did, so I did a couple of years ago, I have to write a, a double entry bookkeeping system for alumniQ stuff. And at the time I was like, okay, well I'm a, I'm a more mature, smarter person now. I went and read a bunch of stuff online about double entry bookkeeping. I wrote the system. It had some growing pains.

[00:52:20] **Adam:** I understand it a lot better now from that. And I feel like if I were to then now go and, and read similar materials about double entry bookkeeping keeping now that, I would understand it better and, and be able to do it better. But the thing about, jump run right now is that it never touches money.

[00:52:38] **Adam:** And the only, the only way it even casually kind of references money is like there's prices for jumps and you sign up to do jumps and at the, you can look at it at the end of the day and say, okay, this is how much I owe you, or this is how much you owe me. Right? I can look at, I can look at the list of jumps that were made and say, Ben, you owe me $172 or whatever.

[00:52:55] **Adam:** and, and I have the receipts of this is what you did and, and this is how much each of those things cost. Where like something that verbal does that my system doesn't do is you can like, put money on account and then it transfers your money over into the drop zones account. when, uh, when you make a jump and like there's a moment of finalization, I guess it's like when the airplane, when the airplane takes off or something, they like finalize it and, and that money then becomes theirs sort of thing.

[00:53:22] **Adam:** and it's just, it, it's, it's a big can of worms. I know that to be true and I'm not, I guess, excited about opening that can of worms. but I think that that's gonna be on the list of, must have features for them. So,

[00:53:39] **Tim:** As well as credit card processing.

[00:53:42] **Adam:** yeah. You know, Tim, I sent you a DM a couple, like within the last week, I think to say like, let's have a chat

[00:53:47] **Tim:** Yeah. We'll have a chat. We'll

[00:53:48] **Adam:** So

[00:53:49] **Ben:** What you

[00:53:49] **Adam:** is your opportunity. Win me away from Stripe.

[00:53:51] **Ben:** you have to start a, uh, like a Kramer Industries, like a Kramer Dozen Seinfeld, and then just get to get yourself an intern. Like get uh, Tim's son as an intern.

[00:54:00] **Adam:** Right.yeah, that's the other thing is right now, you know, this is just something I'm doing outta the goodness of my heart. I'm giving it to my drop zone. I'm paying us a little bit of money here and there. Uh, you know, I pay for the email address that I don't necessarily need to have, but I to give it that error of, of, of, of,

[00:54:17] **Carol:** so it's not like at Gmail. Yeah.

[00:54:19] **Adam:** right?

[00:54:20] **Adam:** It, it's something@thedomain.com. and, and that's where like, so it, that I set up for authentication stuff. Like when I switched from Google OAuth to anybody can sign up with any email address and it'll email you, like a confirm your account sort of thing. that, so I pay for that. I pay for a little bit here and there of other stuff, uh, image hosting, that sort of thing.

[00:54:41] **Adam:** But,I'm, you know, another thing that's gonna happen when this sort of breaks open and, and I have to start making it more official as it's making money. I'm gonna have to like, start an LLC basically. So, that's another, you know, there, there's just this like hump at the beginning of the journey that I'm gonna have to get over.

[00:55:00] **Adam:** And that's, I'm standing at the foothills of that hump going, do I really want to, or do I just want to keep this where it's, so,

[00:55:07] **Ben:** Well, these are exciting problems to have.

[00:55:09] **Adam:** yeah, you know, this, this, uh, part of the show is reminding me of the podcast Escape Velocity. They haven't had an episode in a while. That was one that you told me about Ben, that I really enjoyed.

[00:55:19] **Adam:** You know, that was, I might have to go back and just re-listen to all of that now as like a, as a primer on, you know, what to be thinking about, how to proceed from here where I am, you know? And now at the time when they were airing episodes, I wasn't in that situation. Now I find myself kind of in a similar situation, so I.

[00:55:36] **Ben:** Yeah.

## [00:55:37] Legal and Business Setup Advice

[00:55:37] **Carol:** just when you do get to that point, so a couple years back when I, um, was let go from Clear Capital when they had all the massive layoffs right? And I decided to do con like my own contracting for a bit. I actually met with Steve Whittington. And went with him and like talked to him a lot about like what you do, like when you're working for yourself and like how you make things right.

[00:55:58] **Carol:** And one of the first things he suggested is use something like LegalZoom for your LLC and for just getting like contracts and stuff because it's all online and they're trusted and reputable. And sure enough, like they set up everything for the State of Washington for me. Helped me with everything. I gave 'em a name, bought a domain, and that was it.

[00:56:19] **Carol:** And I just paid that and it was so much easier than trying to like find a lawyer locally, figure out what I had to do. Like it just, and then they auto reminded me to go do it and they just auto charged me and everything was just simple. So if you have someone who you can go to, like Steve Withington or any other, like full-time contractors, they're great resources for help as well.

[00:56:43] **Adam:** That's

[00:56:43] **Ben:** Along those same lines, I'll, I'll say that I heard on a podcast recently that Stripe has kind of their own version of that called Atlas, where they basically do all the incorporation for you as well.

[00:56:55] **Carol:** So that's cool too.

[00:56:56] **Ben:** I think it's relatively, I think it's very new like in the last year or something.

[00:57:01] **Tim:** Yeah, I used, I used Legals when we had, um, we were doing the, special effects makeup classes that we had for the, uh, stars of, TV show Face Off. We used LegalZoom to create that organization. It's super easy.

[00:57:16] **Adam:** Thanks for the advice, guys.

[00:57:18] **Ben:** It's all very exciting. And this is, it's on digital ocean. I can't remember where you said it was.

## [00:57:24] Technical Infrastructure and Scaling

[00:57:24] **Adam:** no, so the, the code runs on a platform called Vercel that's the same company that runs makes next js. and then the database is Postgres. I, I actually, I don't know,

[00:57:36] **Ben:** It was on, um,

[00:57:37] **Adam:** ago I learned that the database itself, no, I looked at Planet Scale originally.

[00:57:41] **Adam:** Now it's on Neon. which, it's actually, it's very interesting. It's, uh, I didn't know this when I signed up for it, but it's, serverless database, right? So you make a request and it, they have like a, I think it's Postgres compatible, right? You can like connect to it as if it's a, a Postgres database, but it's translating that protocol and basically like sending it to a serverless function.

[00:58:04] **Adam:** That reads data from a file or, or maybe it spins up a database and, and gets the data out of it and then shuts the database down and sends you your data back. I don't know exactly what it is, but they also have like a SDK that just sends it like an http request to the serverless function and gets your data and returns it too.

[00:58:18] **Adam:** That's interesting. So that's, that's how they can that know, offer a more generous, free tiers because the database isn't online 24 7. that's another, you know, that's again, you know, I've been doing these forecasting spreadsheets. It's like, okay, well if I sign up this many customers, then I'm gonna have to start paying for, uh, I'm, I'm either gonna have to pay for or build my own, like web socket service.

[00:58:37] **Adam:** 'cause since the versal stuff is all serverless, there's no persistent server for the web socket to connect to. So I've been using pusher, for the web sockets and that's been great. Like the, the function at the users definitely noticed a difference between like a five second polling and real time with pusher.

[00:58:54] **Adam:** I. So, that's been great and, and it just shows that that is necessary in application. Now I have to find a way to make that fit with the budget, right? So like, it's all these things like, okay, if I sign up this many drop zones, then there's gonna be this many connections on average. And that means, you know, I, this many web sockets and, and this much data in the database.

[00:59:12] **Adam:** I got all these things to figure out. It's like, okay, well at some point I might wanna move the database onto AWS just so I can have better uptime,

[00:59:20] **Tim:** Scaling up. Scaling up is hard,

[00:59:22] **Adam:** Yeah. So a lot of that going on in my head right now. Do we want to talk about Microsoft SQL or are

[00:59:28] **Ben:** Nah, no, I'm tired. Let's, let's,

[00:59:30] **Adam:** that for another one. Okay. Well then let me scroll down past Ben's monologue in the script

[00:59:36] **Carol:** is two pages long.

[00:59:38] **Ben:** yo, I was trying to get good value and did not.

[00:59:43] **Carol:** I

[00:59:44] **Adam:** did fine.

[00:59:44] **Carol:** just want you to take Adam's suggestion and throw it in and ask it to basically ask the question better, and I wanna see what it looks like. I wanna be able to compare.

[00:59:53] **Ben:** All

[00:59:53] **Adam:** Yes. Yeah, yeah, yeah. I wanna see like, not only do I wanna see the before and after of the prompt, like have the LLM rewrite your prompt for you. I wanna see if the result of the new prompt is better.

[01:00:05] **Ben:** I like it.

## [01:00:05] Patreon

[01:00:05] **Adam:** Alright, well then this episode of Working Code is brought to you by being the hype man for your ai.

[01:00:09] **Adam:** You gotta tell it. It's awesome so that it will do awesome. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

## [01:00:24] Thanks For Listening!

[01:00:24] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock. Uh, wow. There's a bunch of stuff on the after show teases list here now that doesn't exist. TV stuff, skydiving stuff. guess the

[01:00:37] **Tim:** I wanna know if you've ever done a rodeo,

[01:00:39] **Adam:** Okay.

[01:00:40] **Tim:** air skydiving rodeo.

[01:00:41] **Adam:** yeah, I, I hear you. uh, and I'll answer that question on, on the aftershow, and I, of course, I have to tell Carol about snakes, uh, and their, their reproductive, stuff.

[01:00:50] **Adam:** Uh, anyway, if you wanna help us out and, and hear awesome conversations like that, you can go to patreon.com/workingcodepod. We'd love to have you on the team, a couple of bucks a month, get you that, and more, you know, special access to secret, super secret areas in our discord, early access to episodes of the podcast and the after show.

[01:01:08] **Adam:** So, yeah, we'd love to have you. That's gonna do it for us this week. We'll catch you next week. And until then, then

[01:01:12] **Tim:** Remember this feature flag is always globally on your heart matters.

[01:01:18] **Adam:** why is it a feature flag? Why do you, why do you have the ability to turn it off?

[01:01:21] **Carol:** delete that feature flag.

[01:01:22] **Tim:** I don't know.

[01:01:23] **Ben:** Don't grill him.
