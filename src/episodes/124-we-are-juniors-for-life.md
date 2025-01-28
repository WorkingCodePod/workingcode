---
title: "124: We Are Juniors For Life"
description: "On today's show, we reflect on the YouTube video, 15 Years of Dev in a Nutshell."
date: 2023-04-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/124-we-are-juniors-for-life/id1544142288?i=1000610701075"></iframe>

On today's show, we reflect on the YouTube video, [15 Years of Dev in a Nutshell][15-years]. A few years ago, people were complaining about "JavaScript Fatigue" - this sense that there was a new JavaScript library or framework coming out every day; and, that the race to stay up-to-date in the industry was simply overwhelming. Now, take that feeling, and expand it to include _everything_ in a web development career, from front-end frameworks to databases to server-side rendering to edge-computing. _It's a lot!_ And, it's easy to feel that we engineers are "Juniors for Life": always learning, always evolving, and &mdash; perhaps &mdash; never really mastering anything?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[15-years]: https://www.youtube.com/watch?v=ntzuRtFZ8KM 'YouTube: 15 years of dev in a nutshell'
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/124-we-are-juniors-for-life.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I had a, a moment where I almost fell into the, the shiny hotness trap. it seems like every other podcast will at some point mention VE and how amazing Veit is. And, so I opened it up in a tab and the browser just to, to look into it. I've never tried before and it's a compiler and it does some really crazy stuff and it's super fast.

[00:00:20] **Ben:** And then it, and then I, I left the tab open for a day or two and finally yesterday I came back to it and I'm like, I already have something that compiles JavaScript. and like, I closed the tab and I felt like such a wave of relief.

[00:00:31] **Ben:** I'm like, yeah, that was about to be a huge rabbit hole that probably wasn't gonna yield a whole lot in terms of my day-to-day productivity. So,

[00:00:39] **Tim:** you've gotten older, you've gotten more, more cynical, like just like me.

## [00:01:01] Intro

[00:01:01] **Adam:** Okay, here we go. It is show number 124, and on today's show we are going to talk about how we all are juniors for life. But first, before we do what's usual, I have two announcements. One, I am going to announce that we are going to be suing, century the, the bug Tracking Company because they have a new, a new tagline.

[00:01:23] **Adam:** Uh, it says, working code happy customers, and that I, I cannot let this injustice sand.

[00:01:29] **Ben:** That's our brand.

[00:01:30] **Tim:** Did. Did we trade? Did we trademark it?

[00:01:32] **Adam:** can you do that retroactively? And second, second announcement. I'm starting to GoFundMe to Sue. No, just kidding, just kidding. Love Century not sponsored, but I'm a customer. Very

[00:01:47] **Tim:** Hey, as long as they don't have your heart matters, you know? We'll, which I stole from some child off the internet.

[00:01:56] **Adam:** Some little four-year-old you heartless monster.

[00:01:59] **Adam:** but first as usual, let's start with our tramon fails. Carol can't be with us tonight. She is stuck in traffic in the, apparently pretty bad storms in Georgia right now.

[00:02:08] **Tim:** We're under Tornado watch, so yeah, hopefully she's safe driving around.

[00:02:12] **Adam:** So if Tim goes missing,

[00:02:14] **Tim:** Mm-hmm.

[00:02:15] **Adam:** watch out for flying testicles. it looks like, fresh back from my vacation, it is my turn to go first. I listened to your show last week, guys, by the way, and I enjoyed it. Good job.

[00:02:26] **Tim:** Thanks.

## [00:02:27] Adam's Triumph

[00:02:27] **Adam:** but, yeah, my turn to go first, I'm gonna go with a triumph. in addition to having just returned from a week off of work to take my family out, to the Grand Canyon.

[00:02:35] **Adam:** Nice little vacation. I have just finished, or by the time this airs, I should say, I will have finished, another trip around the sun. so, you know, another year older, another year wiser. but then, you know, yeah, that's the idea. But, you know, the real triumph here is, I back to work, been, you know, doing stuff and, and finally feel like I'm starting to make some actual, like progress that is measurable on compliance stuff.

[00:03:02] **Adam:** Like more than just writing policies and, and like, Figuring out how this crap works. I'm actually like doing things that are checking stuff off the list instead of just making the list longer,

[00:03:12] **Ben:** How long has this been going?

[00:03:14] **Adam:** too long. my, my,

[00:03:16] **Ben:** Not going

[00:03:17] **Adam:** yeah, my, my two words summary of, compliance, for business is, that.

[00:03:25] **Tim:** Quack that.

[00:03:27] **Adam:** Yeah. So, yeah, I mean, look, uug kill me. I hate it, but also it's good for the company and it feels good to get stuff done. So I'm calling it a try.

[00:03:37] **Ben:** at the uh, grand Canyon. Did you go out on that cantilever glass platform? Isn't that something they have there?

[00:03:43] **Adam:** It is something that, that's available at the Grand Canyon. if you haven't heard, it's a pretty big place. it's kind of a large, large hole in the ground. we went to, specifically to the South Rim, there's like a, a, I wouldn't call it a resort, but you know, it's a, it's a, a place there, an official. Touristy spot. and it's not there. I believe that the, the big glass floor that hangs out over the canyon is on the West rim. We, we went to the South Rim. and I, I've got lots of stuff, you know, to talk about there. Maybe we can talk about it some in the after show, but, yeah, no, not there. Not that, not, not this time.

[00:04:20] **Tim:** Your pictures look. Look like you guys had a good time.

[00:04:23] **Ben:** Yeah.

[00:04:23] **Adam:** It was, it was a lot of fun. how about you, Ben? What do you got?

## [00:04:26] Ben's Failure

[00:04:26] **Ben:** I'm gonna go with a failure, which is just that I've been feeling kind of meh lately. I don't even know if I could. Describe it very well. I feel just rushed if that, that's like the closest thing. I feel like I'm rushing from one thing to another thing all the time. Like I haven't had a lot of, it hasn't felt like I've had a lot of free time, which is probably not even true.

[00:04:47] **Ben:** It's just like, that's just generally how I'm feeling right now. And, yeah, I don't enjoy it. Not loving the feeling, but, I'm gonna

[00:04:54] **Adam:** You sound a little tired.

[00:04:55] **Ben:** I'm, I'm, well it's also 85 degrees here and the air conditioning's not working super well right now. Yeah. Which is like also just frustrating cuz we had people come out like last week or the week before to prep the house, you know, like they looked all the vents and the air conditioning, all that stuff to make sure it was ready to go and, apparently it was not ready to go.

[00:05:14] **Ben:** So it's, it's so tough. You know, I, I know so little about maintaining a house, so people come and they just say a bunch of stuff at you and you're like, well, you're the expert. I mean, I don't know if anything that you're saying is true, but. I don't know how to, how to fact check any of it, so I dunno.

[00:05:34] **Ben:** That's, I'm, I'm, I'm just mad. I'm just mad right now,

[00:05:36] **Adam:** it, it's tough, right? Cuz you know, you're very likely to get, swindled to like, replace your furnace at some point. If you don't know, you know what to check and to get a second opinion. That sort of like, if you get a, a disreputable company to come in and do some service, they're likely to, to try to soak you for.

[00:05:53] **Tim:** Yeah, I would say some of the best advice I ever got about home ownership. since I'm not a fixer upper kind of person, I don't, I'm not a handyman when it comes to that sort of stuff, is to get a home warranty.

[00:06:06] **Ben:** Oh yeah, you've talked about that

[00:06:07] **Tim:** American Home Shields, I use them. And so what's nice is you don't have to worry about like finding a reputable person.

[00:06:14] **Tim:** They're gonna send someone out there and it's their best interest to, to get it fixed, but they're gonna do it as cheaply as possible that they can, cuz they don't wanna spend a whole lot of money either. I think they've, we had a, in our old house, the, before we moved to our house, you know, 2010, the other house we had, I think they like repaired the air conditioner like six, seven times before they finally just realized they just needed to replace it a hundred percent.

[00:06:43] **Tim:** And so it's, yeah, it's just, it's nice not to, like right now our, our, our, our dryer just broke so. Go on their website and they send someone out there, you don't have to worry about it. They schedule the call and they show up and do it. So that, that'd be my advice to you, is like, just get a whole warranty system.

[00:06:58] **Tim:** And they do offer like, like proactive. Like they send me a message every spring and say, Hey, time to like, you know, do some maintenance on your air conditioner and you know, they're, they like doing that kind of stuff cuz that saves them money in the long run. Like if they can, if they can do that correctly and they're not gonna suggest or repair because they don't wanna repair it, they wanna make sure it doesn't need repairing cuz it costs them more.

[00:07:20] **Tim:** So that's my advice to you

[00:07:21] **Ben:** I'll bring it up with the misses. She, she handles all the house maintenance and setting appointments and stuff. She'll do the research.

[00:07:28] **Tim:** I can handle like 60, $70 a month outlay, but it's like $2,000 all at once. Unexpected. No Uhuh, I don't wanna do that.

[00:07:38] **Adam:** is that something that you can do after you've been in the house for a while, or do you kind of have to get it within

[00:07:43] **Tim:** No doesn't, you can do it anytime that there's no, no cool off period or anything. I, I think you sign up and you have to wait a month before you submit your first claim

[00:07:53] **Adam:** That way you're not just waiting until something break.

[00:07:55] **Tim:** right then and canceling. Yeah,

[00:07:57] **Adam:** Yeah.

[00:07:57] **Ben:** All right. Well, that's me, Tim. What do you got?

## [00:08:00] Tim's Triumph

[00:08:00] **Tim:** so I'm gonna go with the Triumph. It's been a busy week. My, my weeks are, you know, usually pretty quiet and pretty steady and just meetings and executive stuff and a bit of programming. But I did a fair amount of programming this week and actually some of it was pretty difficult problems to solve. The problems themselves were, I, I thought at first like pretty involved.

[00:08:23] **Tim:** But then, and, and I'm not saying this to brag, but cuz for years, you know, I dealt with spaghetti code. Some of it I inherited, some of it I wrote and just code that you ha if you need to make a trivial change, it is a big, big deal. Well, I, you know, I had some pretty significant changes to make, but because I followed good software practices like, like having good inheritance patterns and, and you know, just making sure everything has functions and that, you know, they're testable, it, it actually turned out, it's like I thought, okay, this is probably gonna take me three days.

[00:08:58] **Tim:** And I knocked it out in about six hours

[00:09:01] **Adam:** Nice.

[00:09:02] **Tim:** in one day and then just turns around at the customer and said, Hey, it's ready to go. And they're like, wow, okay, thanks. I love it. I love it when they, they think it's gonna be super, super hard and then, and so do I, and then I turn around and it's like, yeah, it's probably gonna take me three days and then six hours later I'm like, okay, it's done.

[00:09:19] **Tim:** Like, oh, this is great. Thanks. So that just, it's a good feeling. But yeah, that's, that's after like decade in. Over a decade of just doing things wrong and then finally figuring out how to do it right.

[00:09:32] **Adam:** Mm-hmm. Yep. Under promise, over deliver.

[00:09:36] **Tim:** Yep. Well, I wasn't under promising. I really thought it would take three days. So, so that's me. That, that just, that's a good feeling when you're like, you know what, I'm, I'm, I, I don't feel like I've gotten better at this, but I guess the results can't lie. I actually probably have gotten better at this in the 20 something years.

[00:09:55] **Tim:** I, I've been doing this.

[00:09:56] **Adam:** Yeah.

[00:09:57] **Ben:** I think that ties into the topic of the show as well.

[00:10:01] **Adam:** Well imagine that.

[00:10:02] **Ben:** Imagine that.

[00:10:04] **Adam:** So, I guess we should say this, episode is inspired by a YouTube video that we saw. it's called 15 Years of Dev in a nutshell. Of course the link will be in the show notes. and, I guess if I could summarize the whole video, it's a guy kind of talking you through his career so far.

[00:10:21] **Adam:** He talks about like, he was fresh outta high school. He heard you can make a lot of, make a lot of money, doing development. So he was like, I guess I should do that. And then his journey from there. And how, like, okay. He, he learned some stuff. He thought he was pretty good at it. He, he was like, JavaScript seems easy, so I'm gonna list it as an expert on my resume.

[00:10:39] **Ben:** And then later he realizes like, oh, wow, actually I don't know about So, I'm gonna put that, put that down as a beginner. It was kind of like a JavaScript fatigue except applied to an entire career,

[00:10:52] **Ben:** not just to JavaScript.

[00:10:54] **Adam:** yeah, for sure. So, and like, you know, when you watch the whole video, I was like, he, he, he does a good job of making it like humorous and, entertaining to watch, but at the same time there's a, a very real and true line of like, this is, there's a, it's, it's all based on truth, if not entirely, perfectly true.

[00:11:15] **Adam:** Right? Like you stuff changes every, every year, every. Constantly. You, you are constantly having to learn some new skill. You know, they're releasing new versions of JavaScript. Now the, you know, you know, if you were a Java developer, then they had Kotlin, and you know, there's JavaScript to type script and you've got Angular and React and view and all these other things.

[00:11:35] **Adam:** Like, you know, if you don't try to pay attention and continue to learn throughout your entire career, I think you're gonna, that's the message for me is like, if you, if you don't stay on top of it and continue to evolve with the technology, then you will become obsolete.

## [00:11:53] Redux Anecdotes

[00:11:53] **Ben:** But at the same time there, there needs to be measure to it because kind of what he was saying in the video is he would jump on something and then feel good about it, and then turns out like, oh, actually that thing is not. It's hotness anymore, and they had to go back to do another stuff. if, if I can, if I can throw a little anecdote in here for a moment.

[00:12:12] **Ben:** It mean it's a podcast. That's the whole point.

[00:12:14] **Ben:** it's a podcast. I mean, let anecdote, so this is actually very timely because at work I have been spending the last week or so revamping an area of the application, having to do a database performance. There was a, I've been, I've been examining the slow query logs in our MyQ L instance. And, I kept seeing a couple users who were running queries that were looking at like hundreds of thousands of records.

[00:12:38] **Ben:** And the query was running for like 30, 40, 50 seconds. And that's for a user facing feature. So that was obviously pretty unusable for them. So I went in and I started to refactor some of the queries. And in order to make the queries more performant, I had to sort of change the shape of the data a little bit, which means that I had to go into the front end and start to change the way that the data was being consumed.

[00:12:59] **Ben:** And I had to cut out some stuff and like, We're just gonna quietly remove that from the app kind of a thing, so,

[00:13:06] **Adam:** that was never.

[00:13:07] **Ben:** yeah, yeah, yeah. So this area of the app was built basically right after React Redux, was like at peak hype. And so we were like, oh, we should try to move some redux patterns into this area of the app.

[00:13:28] **Ben:** And the team I was on, we're all looking at each other and like, none of us have ever actually done redux before, but it seems so cool and so exciting. And so I have now been going back into the code, which is at this point, like six years old, I think. And, it's just a freaking nightmare. I, I ended up having to cut out like, so much of this complicated cashing logic and like handler registration and, and optimistic updates.

[00:13:55] **Ben:** And I replaced like hundreds and hundreds of lines of code with just like, oh, something changed. Just re fetch the data from the server. And from a user experience standpoint, it's like basically exactly the same. Maybe there's, you know, 30 milliseconds of delay between the thing that you do and the data that renders.

[00:14:13] **Ben:** And, it just, to me, it feels so kind of on point with this idea where we just sort of blindly jumped on the new hotness, thinking that it was gonna solve all the problems and now revisiting it six or seven years later, realizing that it was only really introducing a lot of complexity, but not really making the app any significantly better.

[00:14:35] **Ben:** And I, I should have just stuck with a much more basic approach to begin.

[00:14:39] **Adam:** Mm-hmm. This is very relatable. We have an application that we wrote, again, sort of at the, on maybe near the peak of, Redux hype on the way up the hill there. and we had it, it took a lot of work for my team to get our heads around the redux patterns, the like, Dispatchers and composing your data into the components and all of that.

[00:15:03] **Adam:** And we, we figured it out and the app works and, and you know, no complaints about that, but it's not an application that we are in there changing on a daily basis or even like a monthly basis. You know, this is an application that is stable and fine, untouched for, you know, minimum of like six months at a time, sometimes a year or two.

[00:15:25] **Adam:** Right? And so to go back after a year or two and look at it, you kind of have to relearn the whole thing all over again because, because we're not using Redux everywhere else. And it is, I, I think for me that was a big lesson from that project was like, if you get to that level of complexity where you're learning like five, six new concepts to just make this one technology work, then it needs to be something that you're going to continue working on, on a daily basis or, or close to daily basis.

[00:15:53] **Adam:** In perpetuity, because if you don't, then those skills are going to regress atrophy, and it'll just, it'll become a maintenance nightmare.

[00:16:04] **Tim:** Hmm.

## [00:16:04] The Learning Treadmill

[00:16:04] **Tim:** So one thing, I watched the video as well and one thing I found alienating cuz his, I guess his life pattern was very much different from mine. Sounds like he outta high school or college, whatever, kind of jumped around a lot, which was, isn't me. I've, you know, I've been in one software company pretty much for my entire life and you know, I'm probably about, 10, 12 years away from retiring.

[00:16:29] **Tim:** So it's like, hopefully, hopefully I can keep, keep on this ride,

[00:16:33] **Adam:** Yeah. You're probably like the very last person on the planet who stays in the same company their entire life.

[00:16:37] **Tim:** yeah, maybe, maybe. So yeah, I, I, I'm, maybe I I'm the odd one out. Yeah. I'm the outlier. I'm the outlier. But yeah. But you know, he was constantly like learning new skills and putting on his resume and then, you know, after a while, either the, the thing he learned, like got two new versions and he is like, oh, I realize I'm no longer an expert in this, so I gotta say a beginner.

[00:16:58] **Tim:** And you know, me knowing, you know, how the hiring process actually works. You, I don't label myself beginner, expert, master or whatever. It's like, has two years experience with X. Right. Without any extra detail. Cuz you know, you do. If you, and like we were saying earlier, if you don't do a thing on a daily basis, you're going to have to. Relearn it. I mean, even sometimes, like there's tags and ColdFusion, which I've, you know, known for years is like, I haven't used this tag in forever. I gotta go look up. I, I don't remember how it works or, or what it does. So gotta look those, I don't think there's anything wrong with that, but I, I do agree with the sentiment that we, because just the nature of our job changes a lot.

[00:17:43] **Tim:** It's not like banking where banking very really changes. Right. It's been, it's been the, been that way since the, the temps were, were moving money from Jerusalem to the, to to England. Right. because it changes so much. It's like, yeah, you're, you're always gonna have to learn new stuff. You're always gonna feel like a junior.

[00:18:01] **Tim:** and that's okay. I don't, I don't think there's anything wrong with that as long as you recognize it. Unless you're lucky like me and just, you know, stay in the same company for until you retire.

[00:18:10] **Adam:** Yeah, I mean, I guess that's kind of the inspiration for this show too, right? Is like we want to normalize that. Like that's a totally normal and expected thing, especially now. Right. I think it was less true when our four Bears were writing cobal. Right. You

[00:18:23] **Tim:** for sure.

[00:18:24] **Adam:** it didn't, there wasn't like, you know, a new version of Cobalt every year, like there is now with JavaScript.

[00:18:30] **Adam:** you know, it's, it's, it's normal. This is, this is life now. This is what you signed up, so, okay. we know that I am, a little too aggressive on the like, side hustle thing. I'm money focused or whatever, and, and, and I'm constantly fighting back ideas of like, things I could do to make a little bit of a extra side cash, right?

[00:18:49] **Adam:** and so one of the things that goes through my mind when I'm considering projects or whatever, like if I were to, we've talked about me possibly doing like a taffy course, right? the, one of the things that turns me off about the idea of doing something like that, or, you know, anything even in that ballpark is, the f basically, when you, when you create something like that, you are stepping onto a treadmill, right?

[00:19:11] **Adam:** It's going to keep moving and you have to continue to put out more content. To, you know, your, that business model is basically like, go give away a bunch of value for free so that people know who you are and they trust you, and they know that they can, they like your teaching style and then offer them something, a, a premium product, like a, a training course or something, and hope that you can make a living on that, right?

[00:19:34] **Adam:** That's sort of like the, the West Boss, business model. And, while the idea of like making a course and, and having potentially passive income, sounds awesome. I don't think that that's the reality. I think that most people that do that end up, you know, like on that treadmill and, you know, every Monday they wake up and they're like, okay, I have to come up with an Instagram post today, and I need something for TikTok and I need to make a YouTube video and I have to have, you know, five interesting tweets.

[00:20:00] **Adam:** And like, and, and for me, I. Would absolutely prior prioritize that after my day job. Like, I'm not, I'm not trying to reach, like, escape velocity on, on side projects, right? I just want beer money, or I want something that'll pay for my skydives.

[00:20:17] **Tim:** All Right?

[00:20:18] **Adam:** and, and it, and, and let me live a, a lavish lifestyle.

[00:20:22] **Adam:** I guess that would be great if we're talking about like what I actually want. but, I, I don't wanna do the work. I don't wanna, I don't do that. But I think that my point after all this rambling is that when you sign up for this career, that's kind of what you're doing. You're, you're signing up for a treadmill of learning.

[00:20:36] **Adam:** And if you don't enjoy the learning part, you're, you're gonna find it difficult.

[00:20:41] **Ben:** Well, and it's very much a career in my experience of sort of two steps forward, one step.

[00:20:47] **Adam:** Mm.

[00:20:47] **Ben:** It's like you're, you're constantly making folies in what you think is a best practice or a best approach or an interesting technology, only to get enough experience with it to realize that it isn't necessarily as great as you had hoped it was, or it's not as applicable as you hoped it was, or just doesn't solve the problems that you had hoped it was.

[00:21:07] **Ben:** And then you, you sort of rebalance where you're like, yeah, but it will be good for this one thing, so I'll keep it in my back pocket, but I'm gonna focus more on something else because it's more of a known quantity. It's, you sort of have to be comfortable with a lot of sort of stumbling, I think, in order to, to stay sane.

[00:21:25] **Tim:** Yeah, and, and, and I, I think kind of age and experience kind of plays into this too. So when you're younger, you don't really know a whole lot. So it's okay that you spend a whole lot of time trying to figure something out. And maybe it works out, maybe it doesn't work out. I mean, I mean, I just think of all the time I killed my teenage years in the early twenties, just messing around with different technologies and really not getting far with them, but the.

[00:21:51] **Tim:** The level, the fear of failure really wasn't there cuz there was no consequence to fail. And then as you get older and you actually are productive, then there's sort of a more conservatism there that, you know, do I really wanna spend a whole lot of time learning, you know, X new hotness and not really sure that it's going to benefit me as much as I know that I have been benefited in the past.

[00:22:16] **Tim:** And so I think that can sort of be a Dr. I, I wouldn't say that I've never shied away from learning new things, but I definitely look at things that are new, more skeptically than I did when I was young. When, when I was young was like, oh, this is cool. I just randomly pick something because it just tickled my fancy at the time and like spent a whole lot of time figuring it out.

[00:22:36] **Tim:** And now that I'm older I'm like, that's cool, but you know, I could probably do this pretty well without learning this thing.

[00:22:45] **Adam:** Mm.

[00:22:46] **Tim:** And that's just kind of the, the benefit or the curse of knowledge and experience.

## [00:22:51] Frontend Frameworks

[00:22:51] **Adam:** For sure. And I mean, I guess it's worth mentioning too that, there can be a downside to, to learning new things too. Like for me right now, I've kind of jumped into a very deep hole of learnings felt and it's felt kit stuff, and I'm loving it. I'm, yeah. In case I haven't mentioned it.

[00:23:11] **Tim:** You haven't mentioned it. Not today.

[00:23:13] **Adam:** and, and it's great.

[00:23:14] **Adam:** I love it. But what the consequence of that decision is, is now I kind of hate working on React stuff. And so we've got all this React code and I'm like, eh, I really would rather not. Does somebody else wanna work on it?

[00:23:30] **Tim:** Yeah,

[00:23:31] **Adam:** I'll go, I'll, I'll handle tickets or something for the day. Somebody else work on this react crap.

[00:23:35] **Adam:** Ugh.

[00:23:36] **Ben:** Yo, I have such extreme shot in Freuder, right? That's like a enjoyment in other people's suffering because I was such an Angular fan, and I am. I am a huge Angular fan, and because I feel like reacts all the spotlight from Angular. Anytime I hear anyone have any complaints about React, which by the way is like a growing wave of emotion, I'm like, f Yeah.

[00:24:00] **Tim:** Yeah, I, yeah, I, I get that like the new thing that you're super excited about, all you ever see when there's a problem is, how can I fix it with this? Right? So for you, it's like, oh, this react problem. Oh, it'd be so much easier and felt if we were just, if we were just using that, oh, you're not so not a hundred percent.

[00:24:17] **Tim:** So you gotta gotta solve it and react.

[00:24:20] **Adam:** Yeah, I guess, so the thing, one of the things that I like the most about spelt overreact is the simplicity of the syntax. And, and like, so with modern React, you have like hooks, right? So you have to, you know, you like use, use effect, and use state and all. And you know, you might. Use memo to do memorization, caching type stuff.

[00:24:38] **Adam:** And, it, it gets, I guess the prob my problem with hooks is that they are a little bit cryptic, right? Like use effect just means that something is happening outside of the application, right? We could be doing data fetching, we could be doing, you know, updating, you know, side effects, like changing something about the browser window or whatever, right?

[00:25:01] **Adam:** Like, and, and, and so it's not immediately clear while you're reading it. And then plus I feel like it has encouraged this style of like, super long, super deeply nested code, right? So you open up a react component where, you know, five years ago it might have been 50 lines, a hundred lines, and now you look at it and it's 5,000 lines long.

[00:25:26] **Adam:** And maybe 5,000 is a bit of an over exaggeration, but you get

[00:25:29] **Ben:** sitting some beasts.

[00:25:30] **Adam:** and, and, and it's got like 12 levels of indentation with so many, like, inline functions, and you're like, really, this is, this is the best we can do in 2023? I don't know.

[00:25:42] **Ben:** Well, I always felt like. JavaScript is actually a relatively simple language. The, I mean like there's really just not a lot of constructs in it. Yeah, yeah. And it's getting more complicated, but it's like there's functions, there's objects, there's lexile scope, which is probably like the hardest thing for anyone to understand.

[00:26:05] **Ben:** And there's like the this binding, like what is this point to? And like basically all of JavaScript is some combination of those things. And so that was the thing that always drove me crazy when people would talk about how great React was. Cause like you got to get closer to the JavaScript. And I'm always like, the JavaScript is the easiest part of all of this.

[00:26:24] **Ben:** Like all of the complexity is wiring together massive applications and maintaining them over time. Like, I dunno, it just, I felt like people were so focused on the wrong.

[00:26:35] **Adam:** Yeah, I agree with you. I think that, maybe like, so the something, this is something I've been thinking about for a little while, like the kind of the difference between a junior developer and a senior developer specifically when we're talking about JavaScript to me right now, is I would describe it as like a, a junior developer can take frameworks and libraries and glue them together and make stuff.

[00:27:02] **Adam:** Right. A senior developer understands the fundamentals of the language, doesn't necessarily need a framework, but it can be a more productive way to do things or a more, a better way to share code, et cetera, et cetera. and, and like having that knowledge of the fundamentals, which you can carry from framework to framework and from job to job, is so profoundly useful, right?

[00:27:28] **Adam:** Like, and also that's a huge difference between the education that you get going to college for computer science and going to like a bootcamp to learn how to code, right? At a bootcamp, they teach you, here's jQuery, or here's React, and here's how you make it do stuff. Whereas when you go to college, it's like, okay, here's how a computer thinks about memory, right?

[00:27:50] **Adam:** And here, here's what a C P U does. And, you know, let's, let's talk about linear algebra and that kind of

[00:27:56] **Ben:** Oh, no more math.

[00:27:59] **Adam:** I loved it. That was my favorite man.

[00:28:01] **Tim:** My, my son Max, he's talking about his, college courses and he's taken discreet mathematics and he's like, oh yeah, I can count in binary now and I can doing graphing. And then I'm like, okay, that's cool. You learn that. But I don't think I've ever needed to count in binary my entire career.

[00:28:18] **Adam:** Who knows? Maybe he'll be a rust developer.

[00:28:21] **Tim:** There you go. Russ is a good language.

[00:28:24] **Adam:** Yeah. I've looked at it a little bit, like literally just a little bit in, in some people's YouTube videos and stuff. it looks interesting to me. It looks like, see, but more confusing.

[00:28:34] **Tim:** Mm-hmm. Yep. Exactly. Yeah. Yeah, that's, that was my take on.

## [00:28:38] Vite

[00:28:38] **Ben:** I had a, a moment just, just yesterday where I almost fell into the, the shiny hotness trap. So I listened to a lot of podcasts and it seems like every other podcast will at some point mention VE and how amazing Veit is. And, so I opened it up in a tab and the browser just to, to look into it. I've never tried before and it's a compiler and it does some really crazy stuff and it's super fast.

[00:29:04] **Ben:** And then it, and then I, I left the tab open for a day or two and finally yesterday I came back to it and I'm like, I already have something that compiles JavaScript. Like, is that really what's holding me back right now? Is having a slightly faster compiler? Do I really need to be. Spending cycles look into this, and like, I closed the tab and I felt like such a wave of relief.

[00:29:22] **Ben:** I'm like, yeah, that was about to be a huge rabbit hole that probably wasn't gonna yield a whole lot in terms of my day-to-day productivity. So,

[00:29:29] **Tim:** you've gotten older, you've gotten more, more cynical, like just like me. What did you call it?

[00:29:35] **Ben:** ve

[00:29:35] **Adam:** It's a French word, meaning fast.

[00:29:38] **Ben:** it's,

[00:29:38] **Tim:** How do you spell it?

[00:29:39] **Adam:** V i

[00:29:40] **Ben:** i t e.

[00:29:41] **Tim:** Oh, see, I thought you said V E E T. Like the stuff that removes hair off your bikini line.

[00:29:46] **Ben:** Oh, I forgot about that. I haven't heard that in a long time.

[00:29:49] **Tim:** I've Googled it. I'm like, all I saw was like your bikini area Wiki. Ow. Okay. I don't think that's what he was talking about.

[00:29:58] **Adam:** I mean, absolutely there's a time and a place for everything and a and a time that is not worth the investment. I think that it's a lot easier if you have the opportunity to start greenfield on a project or something like some sort of satellite service, or if you're starting a, a company from, from the ground up, whatever, like starting with ve makes a heck of a lot of sense because it is faster by like, at least an order of magnitude, if not multiple.

[00:30:23] **Adam:** and so,

[00:30:24] **Ben:** It's very cool. I'm not trying to downplay it, it just,

[00:30:27] **Adam:** Right. And, and the thing that I like about it, I mean, VE is baked into spelt kit, right? That's what they use as their build tool chain. and one of the, the great parts about Kitt is that, you don't have to do any of that config. Like you just install you, you like, do NPM creates fill.

[00:30:43] **Adam:** Latest or whatever the command is, you just copy and paste it from spell dev. and, and you get ve set up and ready to go. And it, it's really easy to turn on actually, when you run that command, it's like, oh, it gives you a little wizard. Like, do you wanna use type script? Do you wanna use VE for testing?

[00:30:55] **Adam:** Do you wanna do this and that? Do you want yes, lin and prettier and all that? And it'll install it and configure your whole project for all of that. And I think if you, if you have the time to invest in it and you hate use, if you hate your current build chain, like if it's babble and, and you've got a ton of, like if it's frustrating to work on and it's slow, it might be worth looking into ve because of the, like seriously, if you go from like a 32nd build to a one second build,

[00:31:26] **Adam:** it's 29 seconds you're saving, which, okay, who cares?

[00:31:29] **Adam:** It's 29 seconds. But if it's 29 seconds, 150 times a day, plus, plus, you know, every time you run your ci plus times however many developers, right? Like. It adds up fast and and you're also talking about like, okay, if you're talking about running your ci, right, so if you're using GitHub actions or whatever, right?

[00:31:48] **Ben:** So that means that you can run it, you can run 29 times more builds before you have to start paying for it. Cuz you've reduced it 29 times or whatever. It's 30 times. I don't know, math is hard, but Well, you know what, as we're talking about this, and this is maybe a little tangential, but sort of, sort of on point, I think is, it feels to me like it used to be that you could incrementally adopt things, you know, a slightly different kind of database. You could try it in part of your app to see if it matches your, your data model better, or, or like a slightly different JavaScript library.

[00:32:26] **Ben:** Drop in and just start to use it a little bit and see if it helps you. And it feels to me like the technologies that are coming out now are, are like a, like a rip and replace. Like you can't, it's like you, it, it doesn't feel like edge functions. Like I can't just really start to sprinkle in edge functions.

[00:32:46] **Ben:** It's like I start to have to fundamentally rethink the way I'm doing application development. Once I'm distributing processing and I have to think about databases and then I have to think about build steps for static assets. It, it, it's, it feels less and less like I can just sprinkle little changes into my applications and that's, that's a little overwhelming.

[00:33:09] **Ben:** Like it feels like you really have to buy into an approach for it to be a value add. You can't just, you can't just experiment.

[00:33:16] **Tim:** There's a lot of risk there to do that, right.

[00:33:18] **Ben:** I think.

[00:33:19] **Adam:** yeah, I mean I think that you're not wrong that there's a lot of change and, and some would say innovation going on in the space of like this library that you're using or framework, if that's what you wanna call it, kind of owns a certain portion of your stack. And, and so if we're talking about like a, an angular react view, solid, you know, these things spell, gotta get it in there.

[00:33:45] **Adam:** they, they tend to have a very wide, target or, or, or area of effect. But at the same time, and I think that that's just because we are seeing a lot of, of people. Putting together ideas differently or relearning? I feel like I've said this on the show before, but, cyclical.

[00:34:11] **Adam:** Everything seems to be cyclical, right? When I first started, when I got my first job out of high school, actually while I was still in college, a lot of the people that sat near me spent their entire days working on green screens, connected to a mainframe, and they were programming, right? We're not, we're not talking about just like using some old cobalt program to do accounts payable, although that was also going on.

[00:34:34] **Adam:** I'm talking about programmers and that was like after the year 2000, right? 2000, 2005 ish. and. If you think about going from that to like React and, and now React server components and like all the things that have happened between there, right? You've got like Pearl for your c g I pages, you've got PHP and C F M L, you've got C Sharp and all these other things and just goes on and on and on and on.

[00:35:01] **Adam:** And then all the way at the other end of the spectrum, you've got where we are today, right? And I feel like when people come up with new ideas, they're like, I've got an idea for a neat thing and it, it can do 60 40 to 60% of what I did with my previous stack. And I, you know, I just wanna play with it. I'm gonna do the thing and that, so like for example, that's kind of where nodes started, right?

[00:35:22] **Adam:** Like it can do, yeah, you can do an HTTP server, we'll we'll figure out the rest, right? and then, you know, we just kind of let go of things from our, our PHP days or whatever that like lessons learned and we have to sort of relearn those lessons. And I feel like everything in this. Career is so cyclical.

[00:35:40] **Adam:** You know, we went from, from heavy client, I'm sorry, heavy server light client to heavy client light server. And now it's kind of going back and you're getting good mix and it, it, it reminds me so much of like, thin client access to a mainframe and then switching to a, a thick client where you had these like heavy client server applications.

[00:36:01] **Adam:** This is before, you know, web apps, right? We're just talking desktop applications. and

[00:36:06] **Tim:** Hello. These days thickest smell with two Cs.

[00:36:09] **Adam:** or three, three, if you're good. yeah, it's just, it, it blows my mind. and I think that we see a lot of these frameworks and tools coming out that are trying to figure out the best way to do this. Like wide view of the stack of, you know, like I, I want to allow you to make a web application that does all the best practices.

[00:36:34] **Adam:** And they're, they're mixing and matching ideas and there's a lot of cross pollination going on. And I don't think that there's, that's wrong. I think that we as web developers are not great at not getting hyped, right? We, if we could take a little bit more of a, a measured approach to the way that we respond to these things and be like, okay, yeah, that's cool.

[00:36:56] **Adam:** You know, let me know when it can do X, Y, and Z too, right? If that was how we thought about things, then I think that the ecosystem would be very different. But instead we're like, Ooh, react shiny. Let me go, let me go do that. I wanna make a, I wanna make a a native mobile app with React too. Can we do that?

[00:37:12] **Adam:** Sure, sure. We'll create React native, right? Like, and, but at the same time, so, so that is my, you're right, Ben, right? That that is definitely happening. But at the same time, I think that we're seeing. Continued evolution and innovation in the small modules space as well. Right. So you, like we had moment js was the, the sort of def facto date handling library for a very long time.

[00:37:41] **Adam:** and now it's really fallen outta favor. There's a couple of different options. The one that stands out in my mind is date FNS

[00:37:47] **Ben:** Right date functions. Yeah.

[00:37:49] **Adam:** And now there's the, isn't there like a new one coming down the spec? Like the

[00:37:54] **Adam:** you're talking the one that's, that's gonna be like baked into JavaScript, the temporal

[00:37:58] **Ben:** yeah.

[00:37:58] **Adam:** thing is what it's called? Yeah. yeah. Yeah. And, and like, so, so stuff is changing there too. And I think that those, are those better fit what you were talking about where you can kind of like mix and match, try something out a little bit, see if it works.

[00:38:11] **Adam:** I think, and the longer time goes on, the more people we have working in this industry, The more, different, not differentiation, what specialization Right. So 10 years ago, I dunno, maybe 10 is not the right amount of time. I don't know. Like,

[00:38:28] **Tim:** 2013.

[00:38:29] **Adam:** well, yeah, whatever. DevOps right. Has not always been a thing.

[00:38:33] **Adam:** It used to be you had a, a guy sitting in a closet and you called him the assisted admin. And when the, the website would go offline. You'd call his phone, right. And now we've got DevOps, which is like a whole career path in its own

[00:38:43] **Tim:** Yep.

[00:38:44] **Adam:** and

[00:38:46] **Tim:** AWS, OpsWorks and all these other things, you gotta figure out how to deploy.

[00:38:49] **Adam:** Infrastructure as code and all that. Yeah.

[00:38:51] **Tim:** Yep. Well, the, well, the good news is that, you know, general AI is just pretty much gonna all write it for us soon so we don't, sorry, made Adam joke.

[00:39:02] **Adam:** Almost spit out my beer.

[00:39:06] **Tim:** And don't waste it. Yeah. AI will take care of all that for us.

[00:39:11] **Ben:** Easy peasy.

[00:39:12] **Tim:** We'll, we'll, we'll just describe what we want and they'll figure it out. They'll write it in something.

## [00:39:16] YAML

[00:39:16] **Ben:** The, oh, yo, sorry. Quick side tension about Yammel.

[00:39:23] **Adam:** Yeah. Wait, wait, wait. I wanna establish something now. Never apologize for a tangent. That's just, that's what we do.

[00:39:31] **Ben:** I was listening to an interview with, I think he was a guy from Google, and he was talking about Go Lang and. About it Yammel and how suddenly people were using Yammel all over the place to configure Docker containers. And he was saying something like, the original intent of yammel was never actually to be used by people.

[00:39:51] **Ben:** It was supposed to be the data format that the machines would generate so they could talk to each other and like you were supposed to use an interface or some sort of higher level language that would eventually generate yammel. But he's like, no one was actually supposed to use it. Not, that's not what it was meant for.

[00:40:06] **Adam:** I believe that.

[00:40:09] **Ben:** It's a, it is a bizarre syntax.

[00:40:11] **Adam:** Yeah. The, the thing is, you know, honestly, I think that the best thing that I've found would be j s o five, but like

[00:40:19] **Ben:** Jason five, what is that?

[00:40:20] **Adam:** yeah, exactly. It's not really supported by

[00:40:23] **Ben:** with comments?

[00:40:24] **Ben:** basically. Yes. Right. You just wanna leave a comment in a file. Why should that be so complicated?

[00:40:30] **Adam:** Exactly.

[00:40:31] **Ben:** Right. I will

[00:40:32] **Adam:** you can't, you can't eval it.

[00:40:34] **Adam:** That's why

[00:40:35] **Ben:** Hmm. one thing, I dunno if it's West Boss Scott Linsky, one of them on, on the Syntax Show will always bring up this idea that until the tooling makes a best

[00:40:47] **Ben:** practice,

[00:40:48] **Adam:** I just gotta get that out there. I can say it

[00:40:53] **Ben:** that's a good one. that until the tooling will make a best practice easy, it people just won't, won't apply it. And, and to your point about how you need these sort of all encompassing frameworks in order to make some of those things possible because individually on their own, some of these things just really are very, very non-trivial.

[00:41:13] **Ben:** Like, even, even something that sounds like it should be simple like critical css, the idea that you would inline CSS that's used above the fold in a page so that it doesn't have to fetch it. But like to do that manually and maintain it over time, it'd be crazy. You'd have to have some sort of a build process that knows how to do that for you.

[00:41:33] **Ben:** Or even, you know, serving up multi density images so that you're, you're one, you're at one X devices have a different image than you're at two X than your 4K and you're eight Ks. But like, the reality is, is no one's generating multiple images by hand. And so you have to either have a framework that does it, or you have to have a, a CDN that does it on the fly for you, or something like the, there, there's so much in the way of, of adhering to best practices.

[00:42:02] **Ben:** That's just not feasible. I think from a, let me sprinkle it into the way that I already do stuff. Like you really have to buy into a holistic application or delivery mechanism or build system or something.

[00:42:16] **Tim:** Yeah, it's hard to convert something existing to the whole new paradigm. In fact, it's so hard you probably shouldn't do it.

[00:42:25] **Adam:** and that is why we are juniors for life.

[00:42:27] **Ben:** Yeah.

[00:42:28] **Adam:** Always learning, always evolving.

[00:42:32] **Tim:** Not, not a bad thing, but hey, if you can just do one thing all your life, lucky.

[00:42:38] **Adam:** All right.

## [00:42:40] Data is Simple

[00:42:40] **Ben:** I'll tell you one thing, that, one piece of advice that I had learned, and this is from a, oh my God, his, his name just went outta my

[00:42:46] **Adam:** It's called a book

[00:42:49] **Ben:** Who's the, uh, the guy who did, closure.

[00:42:52] **Adam:** who created closure.

[00:42:54] **Ben:** Yeah. Yeah. And he has a, he has a whole series of, of YouTube videos. One is like, simple, simple, made

[00:43:00] **Adam:** Oh, rich.

[00:43:01] **Ben:** Yes, rich Hickey. Thank you. in one of his talks, he, he drives home the point that data is simple. And, and like objects are complicated, but data is simple and it's really easy to consume data and pass data around.

[00:43:17] **Ben:** And I have, I have leaned into that hard and that feels like a decision that just continues to pay off, where I use simple data structures instead of over architecting something that could represent that data, I just use the data. And I feel really good about that in TypeScript. Like that's like the, the bread and butter of TypeScript is basically saying, Hey, this object should always look like this thing.

[00:43:41] **Ben:** There you go. You don't have to build anything around it, but even

[00:43:44] **Tim:** You just, and you just pass the date in the URL the whole time.

[00:43:47] **Ben:** just my entire application state right there in the, in the, in the fragment. But yeah, that's, that's something. There's like little things like that where just you learn it once and you're like, ah, yes, taking that with me

[00:44:01] **Adam:** Honestly, like, I, I feel like that might be one of the, as the kids would say, that's a big brain move, right? Like having the entire application state in the, the query string.

[00:44:12] **Tim:** It's, you know, everything old is new again. That'll probably be the next thing.

[00:44:16] **Adam:** Yeah. I mean, it, it's something I've seen Swix talking about Sean Wang, we had him on the show and, and, you know, whatever. He's a, a good guy, smart guy. you know, it, like, why, why do something more complicated than that when you can just, you know, whatever, basic forward or something like that and throw it in the url.

[00:44:34] **Tim:** I was joking, but

[00:44:37] **Adam:** well, sometimes, sometimes that's where good ideas come.

[00:44:40] **Tim:** yeah.

## [00:44:41] Patreon

[00:44:41] **Ben:** Alright, well then this episode of Working Code was brought to you by our GoFundMe to Sooth Pants off of Century for stealing our name and using in their tagline. Your heart does not mess.

[00:44:52] **Adam:** there just, there doesn't, and of course, listeners like you, if you're enjoying the show and that you wanna make sure we can keep putting more of content like this out into the universe, then you should consider supporting us on Patreon.

[00:45:05] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks. Go out to our top patrons, Monte and Giancarlo. Of course, our patrons get our after show. And what is that? That is basically, we're gonna keep the mics on after the show ends, and we're just gonna keep talking about stuff.

[00:45:20] **Adam:** Sometimes it's more tech stuff, but most of the time it's just like life stuff. for example, on tonight's after show, I'm gonna ask Ben how things are going, with, does he still work on the legacy platform

[00:45:32] **Ben:** Oh, I got

[00:45:32] **Tim:** Mm.

[00:45:33] **Adam:** okay. Looks like, is that Tim, put this in here, the project Wolverine. We're gonna talk about that.

[00:45:39] **Adam:** Can AI heal your bugs? So that's a little technical thing, or we'll probably just poke fun at ai.

[00:45:45] **Tim:** Or Wolverine.

[00:45:46] **Adam:** yeah, and well, we actually won't get to either of those things because as I said, I went to the Grand Canyon and I have photos, so I'm going to make my co-host sit through a slideshow.

[00:45:55] **Tim:** Oh Joy. Yay.

[00:45:59] **Ben:** Good radio.

[00:46:00] **Adam:** so if, if that's the type of content that you want, then you can get that by helping us out, and you can do that by going to patreon.com/WorkingCodePod. All of our patrons get the after show, and they get all of our episodes, early, which I would, I would guess is probably like a week and change early.

[00:46:17] **Tim:** For sure. Yeah.

[00:46:18] **Adam:** that's a pretty good deal.

## [00:46:20] Thanks For Listening!

[00:46:20] **Adam:** and your homework this week, I would like you to tell a friend about the show. You know, a friend, an enemy, you know, your pick based on how you feel about the show.

[00:46:31] **Tim:** Have you heard about our Lord and Savior working code?

[00:46:34] **Adam:** Anyway, that's gonna do it for us this week.

[00:46:36] **Adam:** We'll catch you next week and until then,

[00:46:39] **Tim:** Remember guys, girls, your heart matters really, really matters unless you steal our taglines.
