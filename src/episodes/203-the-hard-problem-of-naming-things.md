---
title: "203: The Hard Problem of Naming Things"
description: "In this week's episode, the crew discuesses the complexities and nuances of naming conventions in software projects."
date: 2025-01-29
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/203-the-hard-problem-of-naming-things/id1544142288?i=1000686681337"></iframe>

There are 2 hard problems in computer science: cache invalidation, naming things, and off-by-1 errors. (Leon Bambrick)

In this week's episode, the crew discusses the complexities and nuances of naming conventions in software projects. The team reflects on their own practices, shared challenges, and the real-world impact of terminology and structure on software development and maintenance.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/203-the-hard-problem-of-naming-things.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** So I started to put those things in a, in an object called a workflow, which was kind of the orchestration across multiple types of entities, but I don't know, so that's, that's kind of like how I start, I have my models where it's a gateway.

[00:00:12] **Ben:** A validation object and a model object. What's, what's, how do you guys start a project?

[00:00:18] **Adam:** are way too high up in the clouds for me, buddy.

[00:00:23] **Tim:** Yeah, right.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go. It is show number 203, and on today's show, we're going to talk about naming things, because that is one of the only three problems in computer science that's still relevant. That, and, and off by one errors. So, unfortunately Carol's still not with us. She's, stuck in the Philadelphia airport as far as we know, thanks to these winter storms.

[00:01:04] **Adam:** But, so, so no Carol tonight, just the boys. and it looks like it's my turn to go first, because as usual we start with our triumphs and fails.

## [00:01:11] Adam's Triumph

[00:01:11] **Adam:** So, I got a good one today. it's a triumph.

[00:01:15] **Adam:** We received a ticket, requesting some accessibility changes. It's pretty minor stuff, just like some things that would, help screen readers better identify different parts of the pages. On just a handful of pages. And the ticket ended with a little quote that I'm going to read to you. It says, BTW, having so few issues raised by our accessibility team is pretty amazing.

[00:01:36] **Adam:** You guys are doing a great job. Which just warmed my little heart. Yeah, I mean, it's a big deal for us. Like, A, accessibility is important overall. Cheers. However, my company services almost exclusively colleges and universities, and they are bound by law to meet like certain accessibility thresholds. So while it's important for everybody else, it's like mandatory for us.

[00:02:03] **Adam:** So it just feels good to know that we're doing a good job.

[00:02:06] **Ben:** So accessibility, I assume it's, has been a journey, a learning journey for the company or

[00:02:12] **Adam:** yeah, of course.

[00:02:13] **Ben:** cause there's so many little details that,

[00:02:16] **Adam:** I venture to say that probably most accessibility experts, which we have zero of on our team would say, Or would agree with me if I say it is pretty much impossible to be perfect. Like the only perfectly accessible website is the one that doesn't exist, right? It also has perfect performance too.

[00:02:35] **Adam:** but, yeah, so I mean, you're, it's kind of like a, always, there's always something you could do and you get to a point of diminishing returns and, yeah, so it's just, it's just, you, you, you start with the biggest, easiest wins and then you run the tools on it to see what pops out as like, oh yeah, you should probably do that.

[00:02:53] **Adam:** You should probably do that.

[00:02:55] **Ben:** It'd be interesting, I mean, we don't have to talk about it now, but just what kind of tools people use. I mean, really the only tool that I use is the, Google and, Chrome DevTools has some in their, what you call it, Lighthouse scores. You know, there's an accessibility rating, but I know that there's all kinds of other tools you can use and I just have not taken the time to really learn much about them yet.

[00:03:16] **Tim:** I feel bad that has never come up in my career. 25 years, I, companies I've worked for have never worried about that at all.

[00:03:23] **Ben:** on.

[00:03:24] **Tim:** I guess maybe it's a different market.

[00:03:26] **Adam:** it's definitely,

[00:03:27] **Adam:** something that has changed a lot in the, just the, the overall general awareness and discourse over the last maybe 10 years.

[00:03:35] **Tim:** Yeah. I remember going to conferences and like people, talking about accessibility. Like one presenter, I remember she, she actually had a visual impairment, and, and talked about, and I was super impressed, but I was like, no one has ever directed me to make a website accessible. Period. I think that, I think that the consumer base that we're directed toward are already kind of filtering out people that, you know, it's not a general purpose website, right? So that we're writing, we're writing for a very specific niche market and probably people that have that, have those level of disabilities are probably getting filtered out even before they get to our site.

[00:04:23] **Tim:** I don't know, but I just, I just feel bad. Cause I'm like, you know, it's like, I would like to do nice things for people, but it's like, no one's ever asked me to, and no one's ever complained. So

[00:04:32] **Adam:** Yeah. I mean, there's, you're not wrong. Like there is a way to say that, the, the necessity for accessibility things, and there's lots of different types of accessibility as well, but, the necessity could be filtered out before they get to you for a variety of different reasons, but. I would also say the other side of that same coin is no matter what sort of filters, we're talking like social

[00:04:59] **Tim:** yeah, social folks. Yeah.

[00:05:01] **Adam:** whatever, but no matter what sort of filters there are, there's going to be an exception to that rule, right? There's going to be one blind person who would really like to get to your site or whatever. And it's like,

[00:05:11] **Tim:** So kudos to you guys for doing the right thing. Maybe one day we'll catch up.

[00:05:17] **Adam:** thanks. So that's it

[00:05:18] **Adam:** is quick and easy one for me. What do you got

[00:05:20] **Adam:** going on, Ben?

## [00:05:21] Ben's Triumph

[00:05:21] **Ben:** I'm also gonna go with the Triumph. Small one here, but, I've been playing around with a lot of code lately. And, I've been using the, ParcelJSBundler, which I don't know what it uses under the hood. I don't know if it's one of these ones that uses roll up under the hood or something like that, or if other things use this, I don't quite know where all the, the various bundlers, the boundaries are anyway, that's not the

[00:05:42] **Adam:** It's turtles all the way

[00:05:43] **Ben:** Yeah, so it's just the thing that I happen to have been using for the last couple of years. And, I was, I'm working on this little side project and I ran into an issue where when you configure the bundler, you can give it entry points and you can say like this page is the entry point. And then it kind of spiders down and starts compiling JavaScript and CSS files that it can find from the entry point.

[00:06:05] **Ben:** And I was finding that when I had one entry point, everything was working great. When I had two entry points, everything was working great. The second I added a third entry point, and it didn't matter what order they were in or which files they were, the compiler would just start breaking with this weird, like, node should exist error that kept getting thrown. And after like, a couple of hours, cause like, it was really hard to figure out where it was actually coming from, cause it was just, it's some deep bowels of a, of some node process. I found out, I figured out that it was in a less CSS file. If I had a background image that pointed to a URL parentheses and in the parentheses was a inline data URI that pointed to an SVG file or like an inline, you know, like an actual SVG markup.

[00:06:53] **Ben:** if I commented that line out, it would totally work fine. If I change it from a dot less file to a dot CSS file, it would work fine. You know, I had to comment out some stuff that wasn't. CSS valid. So it was something to do with the interaction between the parcel compiler and the less compiler and this background image and the inline data URI.

[00:07:11] **Ben:** I have no idea what the problem

[00:07:13] **Adam:** hmm. I,

[00:07:13] **Ben:** but I, I ended up so go ahead.

[00:07:17] **Adam:** so you said it didn't matter what order they were in or like. Was the, this background image in the third

[00:07:24] **Adam:** file that you were trying to add?

[00:07:26] **Ben:** It did it's, it was part of a base file system. So it's like it. I was working on this tiny little design system. So if I had the design system and any two other files, and it didn't matter what order that they were configured to be called in, it was crazy. So I did some Googling

[00:07:45] **Adam:** but, but the

[00:07:46] **Adam:** design system and one other file or two or like

[00:07:49] **Ben:** and two other files, any two other files as an

[00:07:51] **Adam:** right. But I'm just, I'm saying it. So if the design system and one other file, would that cause this same

[00:07:57] **Adam:** error?

[00:07:58] **Ben:** No, it's,

[00:07:59] **Adam:** So it's not just a problem with the

[00:08:01] **Ben:** Yeah, yeah, it was like, okay, so I found

[00:08:03] **Ben:** this, I found this, issue on the Parcel GitHub site and, and someone was else was running into something similar. They didn't say it was a background image URL, but they were, you know, they had copy pasted the node error that they were seeing and someone said, oh, it's, it has something to do with an optimization that Parcel is doing behind the scenes.

[00:08:21] **Ben:** And it's creating some sort of a race condition where it's trying to act on two pieces of data at the same time. Anyway, the, okay. So. After four hours of banging my head against the wall, I was like, maybe Parcel is just not the compiler to use. You know, I listened to all these podcasts and everyone's always going on about Vite and how amazing Vite is.

[00:08:38] **Ben:** So I'm like, you know, let me just look at Vite for a second. And I looked at it and, I went to chat GPT and I said, you know, what's a, what's like a super simple entry for, for Vite? How do I get that done? And it gave me some code and I played around with it for like 30 minutes and I was running into some errors and some issues and it doesn't support globbing of imports that, cause it's not a native ES module thing.

[00:09:00] **Ben:** So ultimately what I did, and this is the triumph is that I said, this is crazy. Why am I going off on this rabbit hole to replace out the bundler that I have on this tiny little side project? This seems like such a waste of time. So I ended up just going back to the Parcel. js code and, and finding a workaround, which was to take the inline data URI and basically escape every single funky character, like spaces and quotes and, and anyway, so like I, so my triumph here, I got it to work.

[00:09:32] **Ben:** with the Parcel. js, and because that's the build system that I understand, I have all my files organized to work with it. And so my triumph is that I could have very easily probably gone on this crazy tangent. It may have taken days to figure out to bring in a new compiler. I don't know if it would have worked.

[00:09:46] **Ben:** I would have had to change the way I organize my files because I use this. Globbing mechanism for pulling in multiple files at a single time. And so my triumph was that I didn't do that. And I went back to the tools that I felt a little bit more comfortable with, and I just made it work. And I feel like that is always keeping my eye on the prize and, and not going too far outside things that don't necessarily end up adding value.

[00:10:12] **Ben:** Yes. And,

[00:10:13] **Adam:** did you consider. Just taking that SVG. I used the J word. I'm sorry. Did you consider taking that SVG out of being inline and making it a file and like linking to it? Same problem. Hmm.

[00:10:29] **Ben:** Data UI. It was something, I don't know. It was just crazy. It was just so crazy.

[00:10:35] **Adam:** It was just, it was too many layers deep and that caused a,race condition. Interesting.

[00:10:40] **Ben:** So

[00:10:40] **Adam:** Well, good for you for getting it to work.

[00:10:42] **Ben:** yeah, I was pretty happy about it. And I was, I was happy to be able to just stick with some of the tools that had worked in other projects. Cause here's the thing too, is that If I change the bundler in this little side project, then anytime I go work on another side project, I have to get back in that different mental space.

[00:10:58] **Ben:** Like, Oh, this compiler now works differently. Or what if I want to, if like, I might find a technique that I really enjoy and now I want to copy it over to this other application, the other application uses the older bundler and that technique doesn't work or has issues. I love the idea of having tools that just kind of make sense going from project to project as much as possible. it actually reminds me, we've talked about this years ago, not years ago, episodes, many episodes ago, although it

[00:11:22] **Ben:** could be years. ago.

[00:11:23] **Tim:** been here for years.

[00:11:24] **Ben:** I was listening to an interview and, this one guy on the podcast on this interview said he would, he would always choose consistently bad over inconsistently good.

[00:11:37] **Ben:** And, you know, I think you could interpret that in a whole bunch of different ways, but I kind of look at it in the, even if it's suboptimal, having something that is familiar is just generally better.

[00:11:47] **Tim:** I could, I can think of a language that fits that bill.

[00:11:52] **Adam:** Not to name names.

[00:11:55] **Ben:** Tim, don't shame Scala on our podcast.

[00:11:57] **Tim:** Yeah. sure. For sure.

[00:12:01] **Adam:** Oh

[00:12:01] **Ben:** So that's me. I'm feeling good about that. Carol's not here. So Tim, what do you got going on? Mm

## [00:12:08] Tim's Fail

[00:12:08] **Tim:** a fail. Sorry, guys. I, you know, we started last, you know, last couple of weeks with, I think I'll try them so far, but yeah, I'm going for a fail now. so when it comes to measuring progress in a software project, right. Measuring things.

[00:12:22] **Adam:** are we talking about like measuring performance?

[00:12:24] **Tim:** Measuring like, like, so you just want to measure how much work do we have,

[00:12:29] **Adam:** Okay.

[00:12:30] **Tim:** How much work do we have? And can you're trying to estimate, you know, how much can we get done in the next? Therefore, how much revenue can bring? I just feel like there is a bit of quantum physics going on. at the software level of trying like a Heisenberg uncertainty principle that you cannot know the level of detail of the work being going on without actually affecting the work

[00:12:55] **Adam:** Mm

[00:12:55] **Tim:** so that you can't know like the like in Heisenberg's uncertainty principle you can't know, you can't know The speed of the object and the position at the same time, right?

[00:13:04] **Tim:** And it's just, I think the same thing with software. You can't really get a snapshot of what is actually being done at any given time without actually getting anything done.

[00:13:13] **Adam:** hmm. Mm

[00:13:14] **Tim:** and, and I say this cause I've, I've opted, you know, our company, my group is kind of small, but I've helped, I'm helping out with other companies within the portfolio.

[00:13:26] **Tim:** And, you know, there's some people and they're typically, I don't want to, I don't want to pay to. Broad stroke on them, but they're typically people who are not very technical and they want to measure everything, right? They want to look at the process and say, you know, where is things falling down? So they want to measure every step of the way.

[00:13:46] **Tim:** And then, but ultimately, if you're in a software company that's building software, it's people with their hands on keyboards, writing code. That's it. It's not hard. You're writing code, you're deploying code, you're reviewing code, you're deploying, you know, and. If you put all these measuring points within that process, it affects the actual producing of the code.

[00:14:12] **Tim:** So in an effort to, you know, we need to do things faster, we need to do things more efficient, so therefore we're going to measure all these things, you are actually making things slower, less efficient and you're making the people who are actually doing the work frustrated. And, and so I, I, because of the position I'm in, it's like I'm, I'm torn between I understand upper management's need because they don't really understand the software process.

[00:14:43] **Tim:** They want to say, well, we don't understand why we can't project revenue for the next year. You know, we should be able to get this amount of work done. I get that need. At the same time, if you measure everything, you become a measuring company, not a software company. And the developers tend to, and I'm on the developer side.

[00:15:03] **Tim:** I hate, I hate having to account for all of my time and measuring everything, but I, On the other hand, I do understand the need for it. So trying to find that balance between getting stuff done and being able to tell people like, here's what we're going to get done is a really difficult,

[00:15:23] **Tim:** paradox.

[00:15:25] **Adam:** so yeah, I mean, I completely agree with you there. It's it's like orthogonal Not requirements like goals or something, right? Trying to do better at one necessarily makes it harder or impossible to do the other measuring versus getting done

[00:15:40] **Tim:** And I, I always fall on the side of getting stuff done, right? Cause ultimately that's what you want, but it's like other folks are like, no, no, we have to understand how it's getting done. And I'm like, I get you want that, but you know what? Maybe we just get stuff done. You can just judge it by the results.

[00:15:57] **Adam:** Yeah. You mean you work at a conglomeration of a lot of companies and I can't imagine that your company is the only one within Constellation Software that is a primarily tech company.

[00:16:09] **Tim:** All of them are.

[00:16:10] **Adam:** Right. So like, how is this, like, it sounds like this is kind of a unique problem within your company. Right. Is that what we're hearing about?

[00:16:21] **Adam:** Or is this across the whole company,

[00:16:23] **Tim:** No, not my company, but across several companies, you know,

[00:16:27] **Adam:** your group or

[00:16:28] **Tim:** that they were helping out. Right. So it's like, everything is very financially driven. So they want to be able to have very good projections for the stockholders. Right. But it's like, I get that, but it's like the same time we are, I feel like sometimes we are at the sacrifice of getting stuff done, telling people what.

[00:16:46] **Tim:** They want to hear and then not measuring up.

[00:16:51] **Tim:** Because they're like, well, why did you fail? Like, well, because we spent 25 percent of our time measuring stuff. Well, you know, rather than building stuff, I mean, what do you

[00:16:58] **Tim:** expect? So

[00:17:00] **Ben:** This is the, thing that, this is the issue that I always had when we were doing OKRs at work, which was objective, objectives and key

[00:17:08] **Ben:** results. When they talked about how you pick the OKRs for your team, and I might be getting some of this wrong here. They would always say that you should be picking things that you know you're not necessarily going to be able to complete.

[00:17:20] **Ben:** That if you are able to achieve all of your OKRs. Then you weren't being ambitious enough. And I'm like, that's, but isn't the whole point to create a predictability around what you're going to do. The idea of picking something that you think you're not gonna achieve doesn't seem like it serves any purpose.

[00:17:39] **Ben:** It feels like planning theater, not actually planning strategy.

[00:17:44] **Tim:** Yeah. And, and, and the rationale behind that, because trust me, I've been on the other side of those where they're like, well, you know, we're, we're trying to reach this goal here, but don't tell them that. Tell, tell their goal is a bit more and hopefully, because, because, I mean, there's an assumption that people, people are only going to do the least amount they need to do and not go beyond.

[00:18:05] **Tim:** And I get that. There probably are people like that. and there's probably times in my career when I've been like that, but for the most part, I'm not, right? I'm, I don't want to just, I just don't want to hit the, I want to blow it out the water, right? I want to, I want to walk in the room and everyone wants to smell me cause I, it's been like success. So, so, but to assume that everybody in your organization is like, yeah, we're, we're, yeah, you, you tell me 20, you tell me 30, I'm going to get, you know, I'm going to get 20 and they're like, yeah, that's good. We really wanted 20. That's what we wanted. We wanted 20 the whole time, buddy. fooled you.

[00:18:39] **Adam:** Yes.

[00:18:41] **Tim:** So I don't know that that's my favorite.

[00:18:43] **Tim:** I I'm, I'm having a hard time bridging those two worlds. Cause I, I do get both sides of the equation. I really, really do. But it's like at the end of the day, I think most people just want to work. And when you put friction into their work, they just go, all right. If I can't work, just, just tell me what you want me to do.

[00:19:02] **Tim:** You want me to go measure this stuff and clock all these tickets and say, you measure how much time I'm doing and everything and estimate things that will never ever hit fine, I'll do that. You're paying, you're paying me. And now it just becomes a paycheck rather than, you know, you doing a job that empowers you.

[00:19:22] **Adam:** so take this with a grain of salt. I'm just kind of talking out of my butt here because I have zero experience in like leading a large organization and that like level of planning and forecasting and stuff, but here's a random thought I had. Um,what if you could kind of treat it like a Kickstarter?

[00:19:37] **Adam:** Like this is what we want to get done. And we believe that this is attainable and perhaps, perhaps, you know, like there's some corners we can't see around or whatever, so it may be, we'll get there and it'll be a little bit easier and we'll have room and we can have some stretch goals. Right? Like this is the big thing and we'll be satisfied if the big thing is all that we get done this quarter or, or, you know, whatever planning period, but then if we get there and we have another six weeks or, or we have another two weeks, like these are some things that we're going to also add on like ways to make that one big goal better, or like little things that people have been wanting that we just can't prioritize, whatever.

[00:20:13] **Tim:** Hey, I agree with you. I don't, I don't know how to get there because that's the beauty of like the startup, that's the magic of the story of the startup, right? They just, they, they, they congeal around a single goal. It's usually not big. Well, maybe it is big, but it's a single goal that everyone can wrap around their head very, very simply.

[00:20:31] **Tim:** And that's early in the organization and everyone works toward it. And you know, it's like, sometimes you don't even ask people, but they're going to show up and they're going to work extra hours To get that goal. As an organization becomes more mature, that goal becomes less defined. We already have the thing, right?

[00:20:51] **Tim:** We're doing the thing. We're just trying to do the thing better. And doing things better means a whole lot of different things to different people. And so that becomes a less more unifying rallying cry than the startup cry, right? So I 100 percent agree with what you said, but it's like, I don't know how to do that with a very Mature software company.

[00:21:13] **Tim:** How do you get that same startup drive and, and, and goal and unified vision when really the vision is, Hey, you know what? We're making really, really good profit. When do we keep doing that? how do we do that? Some people are like, Oh, we need to innovate and do all this stuff. But innovating is, you can't catch lightning in the bottle too many times.

[00:21:31] **Tim:** Honestly.

[00:21:31] **Adam:** Yeah.

[00:21:32] **Tim:** And so it's like, what does innovate mean? Does innovate mean, you know, let's just get 20 percent more net revenue and 10 percent more organic growth year over year.okay. But what does that actually mean in solid terms? It becomes harder.

[00:21:46] **Adam:** Right. I think the only way that I can wrap my head around it and have it make sense is to work backwards, right? Instead of this is what we want you to do. How much money do you think it'll make for the company over the course of the next year or whatever? What if they say, we want you to increase revenue by 20 percent by the end of next year, you know, and then you just work backwards from that, what can we do that will cause that or better?

[00:22:11] **Adam:** Right. And

[00:22:12] **Tim:** well, to be honest, that's actually what we do. Right. They're like, here's your target. Here's your financial target. The conversations behind the scenes about how to get there become very complex because everyone has a very different idea what that means. Like, oh, we need to replatform everyone every few years.

[00:22:26] **Tim:** It's like, oh, we need to replatform everything. That never works.

[00:22:31] **Adam:** It doesn't contribute to the bottom line, but it certainly contributes to keeping your employees.

[00:22:36] **Tim:** right. So anyway, I don't want to take too much time. I

[00:22:39] **Tim:** could do a whole episode on this, but yeah, so I'm dealing with

[00:22:42] **Ben:** I, I do want to, I do want

[00:22:43] **Ben:** to, I kind of want to just go off

[00:22:45] **Ben:** on an, on an adjacency for a second, to not use the word tangent for a moment,

[00:22:50] **Tim:** Hey, nice word.

[00:22:52] **Adam:** You just did it.

[00:22:53] **Ben:** but so what you're, what you're talking about, this idea that there's a lot of friction that can be added to developers lives, it, it's making me think of a lot of what I've been hearing lately.

[00:23:05] **Ben:** So at the time of this recording, the TikTok ban in the U. S. went into effect yesterday. Is that, is that what

[00:23:12] **Ben:** happened?

[00:23:12] **Tim:** whole hours.

[00:23:13] **Ben:** Oh, is it, is there a moratorium on it already?

[00:23:16] **Tim:** Oh, you didn't see

[00:23:17] **Ben:** I haven't, I haven't listened to the news

[00:23:18] **Ben:** today. but so in the lead up to this, basically every news and news adjacent podcast that I listened to have been talking about the TikTok ban that was pending and interviewing legal scholars about.

[00:23:33] **Ben:** Whether or not there are merits, can you block stuff like this? Is there any, you know, are there any implications? And the one thing that keeps coming up in all of these conversations is how much the Supreme Court and courts in general put thought into what are the downstream implications of what we're about to do.

[00:23:53] **Ben:** That when we put a new law in the books, like we set a precedence and this precedence is going to have for years to come influence on many other decisions. Put a lot of weight into all of the things that they're, that they're, go ahead. Yeah, yeah, yeah, yeah, yeah, there's supposed to, you know, in, in an ideal world, people take this stuff very seriously.

[00:24:19] **Ben:** And, you know, when they talk about the TikTok ban, that, and how it pertains to free speech, people are arguing that, oh, you can get rid of TikTok because it doesn't impede free speech because people could go elsewhere. And they're like, well, that's not really the way free speech works. That'd be like saying the government can force the New York Times to shut down because people could always go to the Washington Post.

[00:24:38] **Ben:** And that's just, that's not the, That's not the point of the argument. We can't be, we can't be validating things in that way. Anyway. It felt to me, and this is looping back to what Tim is talking about here, is that in project management and product management and the way companies work, it almost feels like they go hard in the opposite direction, where they're like, what is all the stuff we can put in place, regardless of the implications that this might have down the road?

[00:25:05] **Ben:** It's like, you know, people, when they talk about the innocent until presumed guilty, or, you know, presumed innocent until found guilty, that we'd rather have. Guilty people go free than have one innocent person accidentally put in jail. Whereas I feel like in the corporate world, it's like, we'd rather just lock up a bunch of people and hope that most of them are guilty.

[00:25:25] **Adam:** hmm.

[00:25:25] **Ben:** And I don't know. It's just, it, it struck me as why it's so different. I don't understand. And I don't know if it's like a death by a thousand cuts, so you don't feel it happening. So, you know, it doesn't get called out in such a four function, like four step function kind of way. And I was,

[00:25:42] **Tim:** Because at the end of the day, I mean, if you're working at a place like that, you're still getting paid, but you know, if you go to prison, you

[00:25:48] **Tim:** know it.

[00:25:51] **Ben:** what'd it be like? So take Shopify, for example, Shopify's build process from what I heard on an interview, is like 75 minutes long. And you have to imagine that a lot of decisions have been put in the place over the years in an effort to improve the product, obviously. But were people along the way saying, Hey, do we realize that if we put this next little thing in place, it's going to make it longer, and then the next person's going to come and put something else in place and it's gonna make the build stuff even longer and almost feels like people just don't care.

[00:26:24] **Ben:** They're like, that's not the thing that we're trying to optimize for. Whereas it's like, they want to optimize for just a different pain point of, I don't even know how to describe it. It's like, they want to err on the side of most pain sometimes or different pain. I don't know. I, I, I'm trying, I'm, I'm, I'm failing to like really.

[00:26:44] **Ben:** really.

[00:26:46] **Adam:** uh,

[00:26:46] **Adam:** incentives are misaligned

[00:26:48] **Adam:** with developers incentives.

[00:26:51] **Ben:** Yeah, I can't, but I don't, I think developers do it to themselves too. I don't know. I don't know. I don't know.

[00:26:59] **Tim:** Maybe it's

[00:27:00] **Tim:** because they don't know how to name things.

[00:27:03] **Ben:** All right. You want to talk about naming?

[00:27:04] **Tim:** Yeah. Let's talk about it.

[00:27:07] **Adam:** Really awesome transition

[00:27:08] **Adam:** guys.

[00:27:09] **Tim:** you said get right

[00:27:10] **Tim:** into it.

[00:27:11] **Ben:** There you go.

## [00:27:12] The Hard Problem of Naming Things

[00:27:12] **Ben:** All right. Well, this is, this is, so the naming things, obviously we've all heard the, there are two hard things in computer science, naming things and cache invalidation and off by one errors. Right.

[00:27:22] **Adam:** Yeah. You

[00:27:28] **Ben:** but

## [00:27:29] Ben's System

[00:27:29] **Ben:** One of the things that I've been doing as of late is just experimenting a lot more with little ideas, little side projects.

[00:27:35] **Ben:** And what that has afforded me the ability to do is basically start over every couple of weeks. I just kind of start typing application CFC and define my, my application settings, then I create my models folder and I start creating components in there. And then I start creating, data access gateways and all this stuff.

[00:27:56] **Ben:** And. It feels weird to me that after doing this work for like 25 years, I still don't have a great instinct on how to name things. Like I have some things that I kind of like, and they're sort of my go to's. I don't know if I can always name them. Justify why I use those names, and they don't always sit well with me, and I've been trying to play things, play like, play around with things, and it's really hard to find meaningful advice on this, because, for example, I, like I'll Google for something and it'll say, never put the word manager in a class, like a session manager or a file manager, cash manager.

[00:28:42] **Ben:** And I'm reading these really long threads where people are saying, Oh, this is so garbage. Like you should never have a manager because you shouldn't have verbs. And things, and then they say like, Oh, you're clearly now you're writing procedural code and you're not combining your data with your business logic.

[00:28:57] **Ben:** I don't know. Like, I don't understand, but then I realized they're talking about this like really hardcore OO object oriented. Paradigm type programming where everything is an object. And really what I do is I have some objects, but mostly they're just sort of wrappers around procedural code because I really like procedural code.

[00:29:14] **Ben:** And my business logic isn't that crazy. It's it's, you know, take this thing, validate it, put it in a database, you know, for the most part, or like sometimes I have to create multiple database records, but it's still, it's still pretty procedural. So I, I don't even know if I can really apply a lot of the quote unquote best practice naming conventions.

[00:29:34] **Ben:** that I see on the web because I just feel like they're talking about different things. So it's just been really challenging and I'm very frustrated and I thought maybe we could talk about some of the naming conventions that we use because I'm sure that you, we've all created patterns of, of naming things in our applications. and, and so typically when I'm starting a new application, obviously it's a very incremental evolutionary process. So I will start with Usually the least amount of modeling code that I need to kind of log in and log out and maybe manage a session or two. And so typically what I do now, and this has been evolutionary of course, is I have a models folder and inside that I usually have little subdivisions of the types of things I'm talking about, like a session and a user.

[00:30:28] **Ben:** And those are typically folders. And then inside those, I often have multiple components. And I'm in, I'm in the ColdFusion world here. So they're ColdFusion components and I have a, a gateway object. So like a user gateway, and this is really just an abstraction over my SQL. Some people might use an ORM instead of a gateway.

[00:30:46] **Ben:** I think that would be a reasonable equivalence there. so I have my gateway, which is the IO abstraction, and then I have my, I have a validation. Objects. So I have a, for example, a user validation object, which just has a bunch of methods for testing and normalizing things like a name, email address, things like making sure that there aren't any funky encodings inside of strings.

[00:31:12] **Ben:** And then I have what I used to call a user service object, which is kind of the thing that wraps together the gateway and the validation stuff, which would have more CRUD methods, create user, update user, delete user. I've, as of this latest side project. I've changed from calling that user service to calling it user model.

[00:31:32] **Ben:** Just trying something new. Because what I was noticing is that I have components that deal with a single type of thing. I have my user component and I have my session component, or I might have a project component or a team component, but I don't necessarily have a good thing to describe what happens when I have to, Mess with multiple of those at the same time.

[00:31:54] **Ben:** So for example, when you create an account, maybe I have to create a user record and a team record and associate those two. Well, who does that? I've never wanted to put all of that logic into the controller layer. Cause I'd always felt like the controller would be getting too meaty. So I started to put those things in a, in an object called a workflow, which was kind of the orchestration across multiple types of entities, but I don't know, so that's, that's kind of like how I start, I have my models where it's a gateway.

[00:32:24] **Ben:** A validation object and a model object. What's, what's, how do you guys start a project?

[00:32:32] **Adam:** are way too high up in the clouds for me, buddy.

[00:32:35] **Tim:** Yeah, right. Yeah.

## [00:32:42] Adam's System

[00:32:42] **Adam:** the application I've been working on for the last 10 years is a, my CFML monolith is a framework one app. so that provides these buckets of like, here's what I'm we call it and, and roughly what goes where, right?

[00:32:57] **Adam:** So you've got your views, you've got your controllers and you've got services is what framework one calls them. and so, and then we kind of break things down just a little bit within services, like we'll have, we have, DAOs because we, we want, we basically just put a bunch of different stuff

[00:33:12] **Adam:** in the services folder that we might want to auto wire together,

[00:33:15] **Ben:** right?

[00:33:15] **Ben:** And a DAO for

[00:33:16] **Ben:** this scenario is a data access object.

[00:33:19] **Adam:** Right, which you could, if you squint hard enough, you could

[00:33:22] **Adam:** say a gateway and a DAO are kind of the same thing.

[00:33:25] **Ben:** I've definitely called my gateways

[00:33:27] **Ben:** DAOs in the past.

[00:33:28] **Adam:** Sure.and, and so, To use the terminology you were just using, I would say, like, my services

[00:33:35] **Adam:** are, like, the,

[00:33:38] **Ben:** Well, you don't have to use my terminology. Use your terminology. I mean, you know, let's, let's cross

[00:33:41] **Ben:** pollinate here.

[00:33:42] **Adam:** well, I, I think explaining it this way would kind of, like, help bridge the gap. So, what you were describing as, like, a model, I would just say that's my services, right?

[00:33:49] **Adam:** This is the thing that, is the, the entry point for business logic, right? Like, go here to, to do a thing or to get some data or whatever, and that thing understands, All the pieces I need to bring together, or all the places I need to go to get the information that I need to do the thing.and that might require other services.

[00:34:06] **Adam:** It might require DAOs. It might require, wrappers around third party APIs.

[00:34:12] **Adam:** It might require database connection. I guess

[00:34:14] **Ben:** So this is like a real orchestration

[00:34:17] **Ben:** layer.

[00:34:18] **Adam:** yeah, I mean, this is like, you know, save, gift pledge, right? Which is like, okay, so we're getting a donation. We need to save all the details about that.

[00:34:26] **Adam:** That A, that's a database record, but we also need to charge the credit card. We need to, not only are we saving the, the, the record of the pledge itself and all the details, which are many, but we also need to like write to our accounting tables, right? We have a journal and postings, which if you're not familiar with accounting, I'm

[00:34:46] **Adam:** jealous of you,

[00:34:47] **Ben:** Journaling is like the, you can never edit stuff. You can only, you can only up. Yeah.

[00:34:53] **Adam:** Anyway, so like there's a lot to that like

[00:34:56] **Adam:** save pledge, right? And

[00:34:57] **Ben:** But, but so like what would that

[00:34:58] **Ben:** component be called?

[00:35:01] **Adam:** that's part of the gift pledge service. It's like that's one method save pledge in the gift pledge service. And that one, because of like the, the way that a lot of our services are kind of, clustered around our database tables, right?

[00:35:16] **Adam:** So got the gift pledge and a pledge, it can be made up of multiple gifts. So in addition to the pledge service, we also have a gift service, which has a bunch of methods in it specifically about, Crud and other things you might do with a gift and multiple gifts are part of a pledge, right?and and you know, just it turtles all the way down from there, right?

[00:35:36] **Adam:** A gift has payments and it has a schedule and blah blahand So yeah, I mean for me the way I think about it It's just like I just start writing the code, right? You can start in a variety of different places, but something And I, it changes for me, you know, day by day, right? Maybe Monday, I prefer to start with the view.

[00:35:56] **Adam:** Tuesday, I might start with the controller. Wednesday, I might start with the service. Doesn't matter, but I just start. and it's like, okay, this is, this is the most obvious piece of code that I need to write for, for whatever I'm doing. Like, this is what, this is the code that's falling out of my head now.

[00:36:08] **Adam:** I need to get it into the editor, right? And then the, once it's done gushing out of me, then I go, okay, well, how do I connect it to the view or how do I connect it to the service layer or whatever, right? Like fill in the gaps. and yeah, so it's just like, I've got code coming out of my head and I need to fit it into the buckets in a place that makes sense.

[00:36:27] **Adam:** And I will tell you, That it's not perfect. It is far, far, far from perfect. We have several, I mean, I would, I would put money down that we have more than 10. I would not be at all surprised that we have more than a hundred services that are more than 5, 000 lines

[00:36:44] **Adam:** each, right?

[00:36:46] **Ben:** I've been

[00:36:47] **Adam:** tend to grow in those, these complexity things.

[00:36:50] **Adam:** Just like we've talked about the laws of software, right? A complex system is invariably have, It's invariably found to have evolved from a simple system that works.

[00:37:00] **Ben:** 100%. John Gall's Law.

## [00:37:04] Clean Code Naming

[00:37:04] **Tim:** So I'll go back to, you know, Uncle Bob, when we read his book about clean code. I mean, his, his point about naming, cause he talked about that a fair amount, was that it's not a technical issue. It's not a business issue. It's not a management issue. He said the hardest thing about choosing good names requires good descriptive skills and a shared.

[00:37:25] **Tim:** Cultural background. What does he mean by cultural background? I take that from, so each company is going to have a different culture, right? You're going to come into a new, new company and you're going to learn that we say gateways versus DAOs, right? And so you're going to, that's going to be shorthand for things. But then he also says that you need to focus that whether it reads like your code reads like paragraphs and sentences or at least tables and data structure. So, I mean, to the extreme basics, you know, setting an integer to D or X or I, that's just awful. But that tells you nothing, right? But naming things with more very intention revealing names is really helpful.

[00:38:09] **Tim:** So I think, you know, you know, Ben jumped in very kind of deep into the naming pool. Right. But, you know, he's using one word, you use another. It sounds to me like you kind of name saying, you know, name the same things slightly differently.

[00:38:26] **Adam:** Arose by any other

[00:38:27] **Tim:** exactly.

[00:38:28] **Ben:** Well, but

[00:38:28] **Tim:** my background is I use a lot. So. Honestly, one of the things I work on the most is, taffy.

[00:38:34] **Tim:** io. And I, I guess it was your convention. I use this for everything, you know, naming things, either a collection or a member, it's one of the things that taffy. io does. So you have an API. If it's going to return multiple, if you've got an array of things, I call it a collection. If it's just going to, you know, you pass an ID, it's going to give you the member, it's going to bring you back one thing typically in my case, a structure.

[00:38:59] **Tim:** I call it that, where I get confused is like, you know, like you were talking about the, save member, what was it? Save donation or,

[00:39:08] **Adam:** Oh yeah. Yeah. Say pledge. Yeah.

[00:39:09] **Tim:** so what if rather than, is that an insert or an update or both?

[00:39:14] **Adam:** Uh, that one in particular is an insert. We have a separate update pledge or whatever, but, and that's the thing, it's

[00:39:21] **Tim:** so what if you're updating the pledge? What's that called?

[00:39:24] **Adam:** update pledge.

[00:39:25] **Tim:** update it. There you go. All right. Okay. Yeah. Okay.

[00:39:28] **Adam:** Yeah. Yeah. So, and that's the thing is like, very few things in our stack are. one thing, right? So save pledge tends not to be create a, create a pledge record. It tends to be create the pledge record and all of the ephemera that goes with it. Right. And then when you like update pledge, isn't updating that whole stack of stuff, it's, I'm just updating the pledge record. So it tends to be like, think of it as like the outcome of a wizard. There's, there's all, almost all creates are just like, here's a whole bunch of stuff that I needed to create. And then almost all updates are, here's one little thing I need to update. I, I do want to come back to this idea. Ben, it sounded like you were trying

[00:40:08] **Adam:** to say something there.

[00:40:09] **Ben:** I think I was just agreeing with you. Now I don't remember all of a sudden. Yeah.

[00:40:13] **Adam:** Mission accomplished.

[00:40:13] **Tim:** Take the win, Adam. Yeah.

## [00:40:16] Variables

[00:40:16] **Adam:** I want to come back to the idea of, like you were talking about naming files and versus variables. When you told us you wanted to talk about naming things, my head went straight to variables, just totally skipped files. Because for me, that's such a, like a muscle memory thing now, right?

[00:40:29] **Adam:** Like I don't even think about it. It just happens. I was preparing myself to have this conversation thinking like, you know, I, just like you were saying, I, I'd rather have the consistently bad thing rather than the inconsistently good thing. I would Any day of the week, I would take an extremely long variable name that is descriptive and tells me, you know, what is, what it contains and, and whatever else is useful to know about that variable.

[00:40:57] **Adam:** over a hundred lines of comments that tell me the same thing, or 10 lines of comments or two lines of comments, right? Like variable names are in particular, are something that I have been focusing some of my attention on for the last like five years. Like, I've This is a thing that a lot of people are going to read and parse mentally and like, understand what is trying to be expressed by this, this variable name.

[00:41:24] **Adam:** The thing I keep coming back to over and over and over because I do it, it makes perfect sense to me now. It's like, it's, I had my aha moment, I will never do it quote unquote wrong again, is if a, if a variable, now this is very US centric because I haven't had to work outside of US currencies yet. If a variable contains Dollars, then the suffix of the variable name is dollars.

[00:41:50] **Adam:** And if it contains cents, then it contained the suffix is cents. And never ever will I have one that doesn't have one of those two things. Like amount wrong. You're doing it wrong and you should either be put on a PIP or

[00:42:04] **Adam:** fired. Like, you.

[00:42:07] **Ben:** This is how I feel about duration. All of my durations are either duration in seconds or duration in milliseconds. Cause I can't tell you how many times I have had to put something in a cache and there's an argument for duration and I have to look in the cache code to see what does that duration mean?

[00:42:25] **Ben:** So yeah, duration in milliseconds for sure. Or days or something.

[00:42:29] **Adam:** Something. Yeah. And I think honestly, that goes, that's probably goes back to,what is the, what is it called? the, the guy from Excel, something

[00:42:38] **Adam:** typing or something.

[00:42:39] **Adam:** Principle of least surprise. I don't no, no, no. It's like a specific like way. A lot of people misinterpreted this concept or this,

[00:42:47] **Ben:** Hungarian

[00:42:48] **Adam:** Hungarian notation.

[00:42:49] **Adam:** Yes. and people thought it was like, oh, you put an I at the beginning because it's integer. Like, no. You put dollars because it's dollars, you know?

[00:42:58] **Ben:** Yeah.

[00:42:59] **Tim:** But, but yeah, but what if you're in a, a system that's multi currency?

[00:43:02] **Adam:** Yeah. I mean, I, I, I feel bad for my

[00:43:05] **Adam:** future self who has to solve those problems one day.

[00:43:08] **Ben:** know, when you're a multinational conglomerate, that'll be a good problem to have.

[00:43:14] **Adam:** We do have a couple of schools that are in Canada, but fortunately, I think they, well, I think they, yeah, I think that they, what's the word that I'm looking for? Like they're, they're casual conversation. They just call it dollars, like Canadian dollars. I

[00:43:29] **Ben:** Gotcha.

[00:43:29] **Adam:** officially they're called loonies or whatever,

[00:43:32] **Adam:** but like they just, it's the Canadian dollar.

[00:43:34] **Adam:** Oh,

## [00:43:36] Domains and Concepts

[00:43:36] **Ben:** I think kind of what we were talking a little bit about was the culture of the team, but there's also the concept of just domain names that like, for example, Tim's in the insurance world, they have policies. But policy is often in programming a kind of an access permission.

[00:43:57] **Ben:** So you could imagine a world where Tim has an object. That's like a policy policy. And you're like, maybe we should just choose a different word.

[00:44:03] **Tim:** Yeah.

[00:44:04] **Ben:** So it's not confusing.

[00:44:06] **Tim:** Yeah. Even some of my customers confused because like some insurance companies, they don't call them policies. They call them files.

[00:44:12] **Ben:** Classic. They're like,

[00:44:14] **Adam:** ambiguous at all.

[00:44:15] **Ben:** it needs to be future

[00:44:16] **Ben:** extendable.

[00:44:17] **Tim:** early in my day is like, she's like the files wrong. Like what file are you talking about? Yeah. This is dot, dot TX, dot, you know, CSV. I don't know what you're talking about. It's like, no, the file, the file. I don't know what you're talking about. Yeah.

[00:44:31] **Adam:** have those little moments every once in a while. We have a table in our database and the name of the table is transaction because we're talking about financial transactions. But and you know, it actually hasn't been as much of a nightmare as you might assume working with like MySQL or SQL Server that a transaction is a reserved word.

[00:44:52] **Adam:** And, and so you have to. Jumped through a couple of hoops, but it was like, I mean, maybe you could like prefix it, like, you know, like FX or financial or something transaction. But like, we just went with that transaction and it really has

[00:45:04] **Adam:** not been that much trouble.

[00:45:07] **Ben:** this is, I ran into this. Literally this morning. So this little side project I'm working on is just kind of a way for people to organize some files and the people who use the system have clients, but client is a reserved word in ColdFusion because there's the client scope and, and, and. I, I wrestled with the same thing.

[00:45:28] **Ben:** Do I call the table client or do I call it like user client or customer client, something like that. Or I call a customer, and this is where I've been finding the most value out of chat GPT is, I just have a really long conversation with chat GPT about this kind of stuff. You know, what's a better name for client?

[00:45:46] **Ben:** It gives me a bunch of suggestions and I, I don't know, that's where I've been finding AI to be the most valuable is this. Just throw a bunch of stuff at the wall and see what feels like it sticks. but I did wanna circle back. Because Tim brought up, Uncle Bob, and one of the things that Uncle Bob talked about in a, I don't know if it was in clean code or if it was just something I read about one time, where he talked about modeling changes to the system as individual command classes.

[00:46:14] **Ben:** So, whereas we're talking about gift donations or whatever, I can't remember the term.

[00:46:20] **Ben:** Right. That's where you have like a create pledge and an update pledge and maybe a delete pledge. And it's all methods within a single class. Uncle Bob outlined an approach where each of those three things is actually a separate class where you have the, you know, a create pledge class and the delete pledge class and the update pledge class.

[00:46:40] **Ben:** And I've always been tempted to try that because it, Feels very fancy, but every single time I try to approach it, it feels like I'm going to have to be repeating the same kind of dependency injection code all over the place, and I'm going to have to. Take like the one or two private methods that were being shared across all of those and factored out into some other kind of utility class or other type of semantic class that I can inject in.

[00:47:07] **Ben:** And I don't know, it just feels like it's going to be a lot of extra work and I'm not sure that I'm sold on the value of it. One thing that I am trying right now though, is I have historically had a single email service class. Which basically has a method for sending every type of email that the system can send, you know, send welcome emails and comment emails and invoice email, that kind of stuff. I am going to try to break those out into individual classes, like a welcome email CFC and a, you know, comment CFC and an invoice CFC and have like a send method on each one of those. It's, it's just to sort of dabble in this because, you In theory, there's an unlimited number of types of emails that can be sent out, whereas something that's more organized around an entity, like a, like a gift pledge, it feels like there's a finite number of things that you'd theoretically be associated with it, so it feels much more organized.

[00:48:08] **Ben:** More logical to have it all in one place. I don't know if I'm actually going to like this because again, it's like now I'm going to have to inject an email kind of gateway or an email client into each one of these instances. And any time I have repeated code, I'm going to have to try to factor that out to a place that makes sense. Naming stuff is hard, but architecture is hard.

[00:48:29] **Tim:** to tell on myself a little bit though. So, I mean, one bad practice. So like, let's say Uncle Bob says you need to pick one word per concept. Right. So, you know, use the same. It's a concept across the entire codebase. So get value, right? You have a function called get value, and then it's all like, Oh yeah, that's what I'm going to do and use.

[00:48:48] **Tim:** Get value. I use, get value and get value. And then one day I hear a podcast or I talk to you guys. I'm like, no, I'm going to use the word fetch now because I'm making fetch happen.

[00:49:01] **Tim:** And then

[00:49:01] **Ben:** when you listen to this, that's a movie reference.

[00:49:04] **Tim:** yeah, Carol. That was me. That was mean girls. quit trying to say make fetch happen. It's not going to happen. yeah. And then I use fetch for like two weeks and I'm like, no, that's stupid. I'm going back to get, and then, but I never go delete fetch. And then every time I see fetch, I feel like such a loser.

[00:49:21] **Tim:** I'm like, yeah, I had a moment. I had a moment of weakness. I was sticking to a concept. I was sticking to a concept. And then just one day I woke up and I was like, you know what? I've. I just don't feel confident that the Git was a great idea and I used Fetch for a while, and now I just have this inconsistency across my code base and I really should, you know,

[00:49:41] **Tim:** be a greeter at Walmart.

[00:49:44] **Ben:** Well, okay. So I do want to push back a little bit here and say that one of the, one of the freeing things that I've really embraced in the sort of latter half of my career. Is this strong notion that nothing is set in stone, that you don't necessarily have to live with any bad choice that you make for the most part.

[00:50:04] **Ben:** You know, once you get a lot of infrastructure in place, there's only so much wiggle room with your budgets. I do like the idea of not having to do too much hand wringing about anything because you can always go back and change it, you know, full caveat. This whole episode is all about hand wringing. So, you know, take that with a grain of salt, but I actually, I did read, one piece of advice years ago.

[00:50:26] **Ben:** Where someone was saying, when you have trouble naming things, just like start out by calling it And like, you just use it a bunch of times until you realize what it should be called, and then you rename it to the thing that it should be. And you know, I've not done that yet. I have not deployed any code that has references to MonkeyBalls, but.

[00:50:43] **Adam:** know, in good languages that give you really good refactoring tools. So I know this isn't something you're familiar with from CFML, but.

[00:50:51] **Tim:** snap.

[00:50:53] **Adam:** but, even in something as lowly as JavaScript, you can just right click, refactor, and give it a new name, and all the references, it'll spider out and find them, and, it just does it, rename it, once, one, not even like a regex find and replace, just, Boom.

[00:51:09] **Adam:** Done.

[00:51:10] **Ben:** I'll tell you, and I do, so one of the things that I do is I, at the top of the show, I talked about how I have a gateway object and a validation object and a model object as sort of this aggregate of, of a single concept. And so I'll have a new concept that I need to work on. So I literally just go to, like, I go to my user model folder and I copy those three things That's it.

[00:51:33] **Ben:** And then I paste them and then just start renaming files and renaming all the variables and renaming all the method names to point to the new entity. I do sometimes long

[00:51:42] **Ben:** for that to be a little bit easier. And then I start to go down this rabbit hole in my head of like, well, maybe is there some sort of an abstraction that I could create? Like, I think Adam, in the past, you've talked about how your data access objects, you have base methods for doing all of the like get by filters and creates and deletes and stuff.

[00:52:01] **Adam:** I mean, I can't take credit for any of that. It was a majority of the work on that was done by one of my coworkers, but he came up with this idea. Like, you know, DAOs are like 90 percent

[00:52:08] **Adam:** the same code. You just have to tell it, this is the structure of the

[00:52:11] **Ben:** I know that's how I feel. It's like, uh, it's, uh, so I do feel like maybe I want some better abstractions there that, that would just. Cut down on, on a lot of the kind of copy, paste, modify work that I do. I mean, it's all fast. It's just tedious and it's a little bit error prone or, you know, what ends up happening is you look at a file years later and it, it has 99 references to a user and like one comment that says this create user method creates a new time zone and you're like, ah, it's cause I copied it from something that referenced time zone and I missed that one

[00:52:46] **Tim:** So you're saying you got 98 comments to a user. But a comment

[00:52:51] **Tim:** ain't one.

[00:52:54] **Ben:** Oh man, stuff is hard. And then, then there's like lines that are a little bit blurry. So you talk about your gift pledge, where some of it is, is messing with entity kind of data, but then you might also put an email SNS or something. And you're like, then like, what is it? I don't know. Like now it just feels like stuff starts to get a little fuzzy.

[00:53:21] **Adam:** Well, so I'll tell you what happens, right? So we do, we send a confirmation email. We might send a tax receipt separately. you know, there's, we might send alerts internally. Like if this is a gift from somebody. who has a gift manager or what do they call it? A gift officer, I think, right? So there's, when you become a high net worth individual that a college, like multiple people on the staff know who you are and they recognize you when you're out in an event and they come over and shake your hand.

[00:53:45] **Adam:** Those type of people, there, there's a person whose job, or there's a, there's a job called a gift officer. And your job is to like, know who those people are and go just butter them up and like, make them feel like they're on top of the world. and. and so they need to know like, Oh, they're, they just made a gift or they're at this event or whatever.

[00:54:03] **Adam:** Right. and so we do stuff like that. And so, yeah, I mean, we do have a transactional email service, right. And, and I wired that transactional email service into the gift pledge service with auto wiring. And then it's just, okay. One of the things on the gift pledge is like, okay. you know, it might call another method.

[00:54:20] **Adam:** Within the gift pledge service, that's like send necessary

[00:54:23] **Adam:** transaction emails for this gift.

[00:54:26] **Ben:** So then, then I feel like, so

[00:54:29] **Adam:** And that one figures out which one should go. And that calls the transactional email service and

[00:54:33] **Adam:** like queues up four different emails that need to go or whatever.

## [00:54:36] Boundaries

[00:54:36] **Ben:** So, and then like, here's where I start to bang my head against the wall because historically those were all something service. So it's like a user service might turn around and call the email service to send a particular email, but then I start to do my hand wringing. And I'm like, well, the email service doesn't really refer to businessy logic so much as it is like just infrastructure concerns.

[00:54:56] **Ben:** Like I'm taking this data and I have to push it into this queue where I have to, you know, interpolate into this template and then put it on a queue. And then, so I'm like, maybe it's not so much a service as it is like a manager. Like maybe this is the email manager. And it's like these, these just arbitrary decisions that because it's containing a little bit of different flavor of logic that I have to start calling it something else.

[00:55:16] **Ben:** And maybe that's really my problem is I'm just. I'm trying to create delineation for the sake of delineation.

[00:55:23] **Adam:** I think you're allowing too many things in one where you should just have one, right? For me, it's services. And a service can do four or five different types of work, but it's all, you know, very similar, versus, you know, like a service for me might be an API wrapper. We have an S3 service and its job is to just like accept a function call and do something, right?

[00:55:46] **Adam:** It might delete a file on S3 or push a file to S3 or whatever.

[00:55:50] **Adam:** And I

[00:55:53] **Ben:** the one that I also struggle with is when you're really dealing with the external API. So it's like I, I might internally call something, for example, bug snag client. So bug snag is a bug tracker application. So I might have a Bugsnag client component

[00:56:10] **Adam:** bug log service

[00:56:12] **Ben:** yeah, so the, okay, so

[00:56:13] **Ben:** then. So ridiculous it gets. So I have my Bugsnag client, which internally uses a like Bugsnag gateway, which is really just kind of the semantics over the HTTP call itself, where it takes all the parameters, you know, it's like, it's just in the way that the data access object wraps the SQL. My Bugsnag gateway just sort of wraps the HTTP semantics.

[00:56:39] **Adam:** but yeah,

[00:56:42] **Ben:** But then I also, so Bugsnag ultimately is just, kind of an implementation of a logger so that I have a, I have a logger component, which takes the Bugsnag client, but then sort of transforms the calls. I mean, it makes sense when you see it on paper,

[00:56:59] **Adam:** Sure.

[00:57:00] **Tim:** To you.

[00:57:01] **Ben:** but it's just, I don't know. It's hard. It's like naming stuff is really hard because naming stuff would be easier if it was very clear where the boundaries were.

[00:57:10] **Ben:** But I think that's a big part of where I'm struggling is where, where do I draw the boundaries properly?

[00:57:16] **Adam:** If I were, if you were

[00:57:17] **Adam:** asking for advice, which I don't think that you are,

[00:57:20] **Ben:** I mean, I, I, I am, and I am, and I'm not, I'm, I'm sharing, but I'm also, I'm sharing in an effort to think about this stuff more effectively. So any feedback is, is helpful.

[00:57:30] **Adam:** yeah, you're, you're

[00:57:31] **Adam:** commiserating with optional feedback.

[00:57:35] **Ben:** Yeah, yeah, yeah,

[00:57:35] **Adam:** I think that you were talking about boundaries, the thing, the place, and I, I was also thinking about boundaries, but I didn't come up with that word, so I liked that you used it. the thing that makes me want to use a name other than service is like, What am I going to be thinking about when I'm trying to remember what this one is called, right?

[00:57:53] **Adam:** I know I'm, I want to find the file that manages database records for this type of record, right? I want to find the gift pledge DAO, or I want to find, you know, whatever the email service, because I know it's like this thing is managing emails. It's not writing them to the database or it's not sending them.

[00:58:14] **Adam:** It's just like the thing that contains the business logic. So for me, that's a service and services can do a thousand different types of things, but they're, they're, they do not, I don't know, I don't, now that I say that, they,

[00:58:27] **Tim:** but I mean, that's, that's exactly what Uncle Bob says. It's like one word per concept. So like, you call it a feature manager or a feature controller, manager or control, just pick one. Just be consistent when you use it or

[00:58:37] **Tim:** service, right? Just be consistent. You're like, okay, I need a thing that is managing this process that is much bigger than, than the rest of it.

[00:58:46] **Tim:** So is it a manager? Is it controllers? Is it a service? Pick one and go with it and stay with it. Don't be like

[00:58:51] **Tim:** me and Waffle.

[00:58:52] **Ben:** I'm trying, trying to be a better man.

[00:58:55] **Adam:** All right.so I, I has some sport ball to get to.

[00:58:59] **Adam:** I think we've pretty much said everything that we have to say about this. I think we're starting, we're starting to walk in circles. So,

[00:59:05] **Tim:** That's all I have to say about that.

[00:59:07] **Adam:** indeed.

## [00:59:08] Patreon

[00:59:08] **Adam:** This episode of Working Code is brought to you by Tim's new cologne. It's success. It's two parts, chili pepper, two parts, chili pepper, one part monkey

[00:59:15] **Tim:** hmm.

[00:59:16] **Tim:** Yeah.

[00:59:16] **Ben:** That's on brand.

[00:59:17] **Ben:** Fightin

[00:59:19] **Adam:** if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:59:29] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. We really appreciate you guys. We're gonna do a probably really quick after show, because Tim wants to go watch the football.

[00:59:40] **Tim:** I want to go watch. I want to go watch Notre Dame and Ohio state play. I don't care who wins because George is out of it, but yeah, I just want us to fight an Irish. Yeah. Whoever, I don't care.

[00:59:48] **Tim:** I want to watch football.

[00:59:49] **Adam:** cool. Ballsports. anyway, Aftershow is what you get if you support us on Patreon, and you can go to Patreon.com/WorkingCodePod. We'd really appreciate your support.you've heard me say all the other things a bunch of times, so I'm just gonna skip it. That's it for us this week.

[01:00:03] **Adam:** We'll catch you next week, and until then

[01:00:05] **Tim:** Remember once it's done gushing out of Adam, know that your heart matters.

[01:00:31] **Ben:** point to the new entity. Oh, um, lost my train of thought there,

[01:00:37] **Tim:** Sorry.

[01:00:42] **Tim:** we're,

[01:00:43] **Tim:** making, we're, we're we're making

[01:00:45] **Tim:** notes in the Google Doc, cracking him up
