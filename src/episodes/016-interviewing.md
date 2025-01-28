---
title: "016: Interviewing"
description: "This week, the crew sits down to talk about interviewing, both from the side of the interviewer and from the side of interviewee. What are we looking for? What are the red flags? What kinds of questions should we be asking?"
date: 2021-03-31
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/016-interviewing/id1544142288?i=1000515163247"></iframe>

This week, the crew sits down to talk about interviewing, both from the side of the interviewer and from the side of interviewee. What are we looking for? What are the red flags? What kinds of questions should we be asking? Are we putting too much faith in the sanctity of the interview process? And, why the heck does [Zappos offer to pay you $2,000 _not to work there_][zappos-quit]?!

This discussion is particularly insightful because Carol shares her perspective as a female which includes things most men will have never considered. For example, did you know that you can ask ahead of time who will be interviewing you? And, that it's even OK to ask for a woman to be present on the interview panel? This underscores the importance of creating and hiring for a diverse team: everyone's perspective is different; and, everyone's perspective is valuable. And, when we only hire people that look and act like us, we only see the human experience through a small window.

Each week, our top Patreon supporters get a sponsored shout-out. And, today's shout-out goes to [Girls Who Code][girls-who-code], an organization who's mission it is to close the gender gap in technology and to change the image of what a programmer looks like and does.

### Triumphs &amp; Failures

- **Adam's Triumph** - In 2014, he wrote [REST Assured][rest-assured], a no-nonsense ebook about architecting RESTful APIs. Now in 2021 - by _popular demand_ - this digital work is finally coming to a paperback near you! And of course, we're all demanding signed copies!

- **Ben's Failure** - this past week just left him feeling _destroyed_. Between the "Spring forward" clock change, an absurd number of meetings, and the abysmal performance of his ColdFusion custom tag DSL inside a Docker container, this whole week has felt like a kick in the gut. Not every week is going to be a winner; and, he just hopes that next week is better!

- **Carol's Triumph** - she bought a daily-planer to help her keep track of what she's done _today_; and, what she needs to get done _tomorrow_. Part optimization, part self-care, writing everything down allows her to see a clear record of what she's accomplished; which, in turn, allows her to embrace her own success and feel good about stepping away from her desk when she needs to take a break.

- **Tim's Triumph** - his plan is really coming together! After months-and-months of consulting with customers, writing business plans, organizing marketing campaigns, collecting testimonials, obtaining budgets, running things by Legal, and working with Quality Assurance (QA), all the pieces are falling into place. And, for him, it's been a truly humbling experience. As engineers, we can be lulled into thinking that we are the _center of the universe_; but, when one see just how many people are involved in bringing a product to market, it becomes clear that we are just small cogs in a massive, harmonious machine.

### Notes &amp; Links

- [The MEGA Interview Guide](https://github.com/danieldelcore/mega-interview-guide) - a humble guide to give developers the tools they need to nail technical interviews!
- [Awesome Interview Questions](https://github.com/DopplerHQ/awesome-interview-questions) - a curated list of lists of technical interview questions.
- [Cracking the Coding Interview](https://github.com/careercup/CtCI-6th-Edition) - the 6th edition of the book's crowd-sourced solutions guide.
- [MOVA](https://www.theregister.com/2021/03/10/fake_mova_programming) - a fake programming language created to help weed-out nefarious recruiters and engineers.
- [How to Deal with Difficult People on Software Projects](https://www.howtodeal.dev/) - a breakdown of different work personalities and how to work effectively with them.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[girls-who-code]: https://girlswhocode.com/
[rest-assured]: https://restassuredbook.com/
[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[zappos-quit]: https://www.businessinsider.com/zappos-tony-hsieh-paid-new-workers-to-quit-the-offer-2020-11
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/016-interviewing.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:12] **Adam:** Okay, here we go. It is show number 16 for March the 31st, and on today's show we're going to talk about interviewing. And I think, if I understand correctly, we're going to talk about that from both sides of the table.

[00:00:22] **Adam:** But first, let's get to our triumphs and fails, and I'm going to steal the spotlight here. I'm, I've had some fails that I would like to talk about soon, but I have to, I have to talk about this triumph from this week. As we've mentioned a few times, I've written a book, and, and it is now in my hand in dead tree form.

[00:00:39] **Adam:** Listen to this. Ooh. Pretty. Um, yeah. Is it

[00:00:44] **Carol:** on recycled

[00:00:45] **Adam:** paper? Um, yes. Question mark. Yes, I'll buy one then . Um, it's so, I mean, it's, it's self-published, but it's gonna be available soon as print. The, the one that I was just flipping through is a proof for me to make sure that the graphics all line up right.

[00:00:59] **Adam:** And I'm happy with the way it looks on the inside and stuff, so I'm just super excited about that. It's, it's a book I wrote in 2014 and I've had several people over the years ask me for a print. And I've always just said, you know, I'd love to, but don't hold your breath. And so finally those people can stop holding their breath.

[00:01:16] **Adam:** Well, that's awesome. So what

[00:01:17] **Carol:** one? I love print copy. So I'm that person. Yeah. I

[00:01:20] **Adam:** want an autographed copy. Yeah. Yeah. I'm trying to figure out how I can make that work. Yeah. Like it's got my name on the spine here. Um, I think the only way I'm going to be able to make that work is to like order them and have them sent to myself.

[00:01:32] **Adam:** And then, uh, Autograph them and mail them out. So, you're gonna add a bunch of time to your order for that? Sure, that's fine.

[00:01:40] **Carol:** I still want it. Hey, I'm down. My son,

[00:01:41] **Tim:** Adam, he's a published author.

[00:01:45] **Adam:** You're adding a lot of kvetch to my mom's accent there, but, uh, Is that not what they sound like in Philly? We're not Philly, we're from all over, but, uh, That is exactly the words that she would use, but that is totally not her accent.

[00:02:00] **Carol:** Well, congratulations. That's awesome. I'm so proud

[00:02:02] **Adam:** of you. Thank you guys. Um, so I guess, uh, Tim, let's go to you next.

[00:02:07] **Tim:** Well, so my triumph is it's all coming together. I can't wiggle my fingers. Excellent. It's all coming together. I've been working so hard. I mean, I don't think if you're a coder, whose job is to come in and write code 24, you know, come in at eight, leave at five, doing code all day long.

[00:02:31] **Tim:** I don't think you realize how hard it is to get a new product to market. It is so amazingly hard. There's so many moving parts. Um, there's so many agreements that need to be done so much legal review that needs to be done so much sales and marketing research that needs to be done. There's so many people.

[00:02:50] **Tim:** That need to be involved. And I, I myself, I was ignorant of it for years. I didn't realize how many hands it took to lift a project like that. You know, you come in, you get a ticket, you get, you know, it's just part of an overall epic and you're working it and you understand what's asked of you, but you don't even realize how much stuff is going on behind the scenes.

[00:03:14] **Tim:** I have been doing all of it for this project. I've been writing it. I've been, you know, consulting on it. I've been hiring people to work on it. I've been working with the sales and marketing team to, to build it, uh, build the assets for it and working with customers to, you know, to get, uh, some sanity checks and, you know, quotes about, you know, how they like using it.

[00:03:37] **Tim:** It's so much involved and it's, I feel like I've been Swimming in molasses for the past nine months. And finally, finally, I looked at my board and all my tickets were done. I looked at the proof copy of what was coming from marketing and it's like everything just all is now coming in. I'm like, Oh my God, this is actually going to happen.

[00:04:01] **Tim:** And so I'm just. Elated that this is going to happen. Now, my big fear is that we'll launch it and it will just not scale and fall over. But that's just, that's just Tim fear. I don't think that's going to happen.

[00:04:16] **Carol:** Face that down the road. Don't worry about it now. Yeah. That's tomorrow. Yeah.

[00:04:19] **Adam:** Celebrate

[00:04:20] **Tim:** now.

[00:04:21] **Tim:** Yeah. So I'm just happy to see stuff coming together. It's, it's, it's humbling how many people are involved in getting a product to launch.

[00:04:30] **Carol:** It sounds overwhelming from my point of view. I don't, I don't know how I, I don't know how I would deal with that. You

[00:04:37] **Tim:** just keep kicking your legs under the water and go.

[00:04:41] **Tim:** I'll tell

[00:04:42] **Ben:** you one of the consistent themes that I've been hearing a lot in various podcasts is people bringing up the idea that ideas are worthless. Like there's nothing special about your idea because the distance between idea. And shipping a product that becomes successful is so massive that you could tell people all of your ideas and you're not actually giving anything away because just giving someone an idea doesn't give them anything

[00:05:04] **Adam:** really.

[00:05:04] **Adam:** Yeah. Yep. Execution matters way more than the idea. And your

[00:05:10] **Tim:** heart matters.

[00:05:15] **Tim:** Carol, how about

[00:05:16] **Carol:** you? Um, so I'm going to go with the Triumph this week. I went to Hobby Lobby and bought a planner. A daily planner and I only did it because I am not doing so well at kind of, um, keeping track of just my injects throughout the day. So, then when I wrap up my day coding, I feel like, you know, I've been working 8 hours, but I don't feel like I've produced 8 hours of work and I don't like the feeling.

[00:05:43] **Carol:** Of not doing enough or feeling like I'm not excelling where I need to be excelling at. So, I've started just kind of and this is the 2nd week of it total. So, this week was actually very successful, because I've been able to go, okay, this is every time I had to change tasks from what I was doing, and just the constant kind of moving around between looking at this, looking at that, to looking back at this, to having to stash my code, to trying to get it back onto the branch I was on, because I didn't commit it.

[00:06:11] **Carol:** I just stashed it. So, now I have to get it all back in place. I was like, okay, now I'm seeing like. That it's okay to walk away when I need to walk away because I really did a lot today, even though not a ton got finished. So I just feel better about my days. And so I've kind of gotten it organized a little better on paper, not on the computer, not on my phone.

[00:06:31] **Carol:** It's actually in a notebook. in front of me all the time.

[00:06:35] **Adam:** So this is more of a more of a reactive thing than a proactive thing. You're not planning out your days. You're taking notes on how the day is going sort of thing.

[00:06:43] **Carol:** Yeah, I'm pretty much taking notes on how it's going. But the one thing I do is if I had something I needed to get done, like yesterday, I had something I needed to get done, but it didn't get finished.

[00:06:50] **Carol:** So it's on the very top of the list for today. So it's already on the list. So whenever I open my notebook in the morning, it's there waiting on me. So I do that first as opposed to starting anything that I was already involved in or that I've gotten asked to look at. So yeah.

[00:07:06] **Ben:** Nice. I'm a huge fan of paper.

[00:07:08] **Ben:** I keep a little sticky note. It's next to my thing.

[00:07:12] **Carol:** It helps too with standup. Um, whenever I'm going through everything I've been working on, I'm like, cause usually I go into standup, I'm like, I'm still working on that thing. Well, in reality, there's like 10 other things that I'm also touching, but I forget about them because it's just in and out so quickly.

[00:07:26] **Carol:** So yeah, my sticky notes were good for that. But the notebook's helping a lot, the daily planner.

[00:07:31] **Adam:** That's interesting. I've started doing something similar. Um, on January 1st of this year, we started a Google Doc for just kind of having notes to kind of encourage us to have clear thoughts going into a stand up and to keep track of that stuff over time.

[00:07:47] **Adam:** And, uh, it's I found it really helpful to have that list because I can refer back. Oh, you know, I know I worked on that last week. What was that pull request or where was that ticket or whatever makes it easier to find it because you've got a much smaller list of things. And so because of that, actually today I started, um, taking notes for just like a personal journal of like what's going on daily notes.

[00:08:08] **Adam:** And I'm, I'm day one into it, but I'm really liking it so far. Yeah.

[00:08:12] **Carol:** I hope I can stick with it. Cause it seems to be very helpful. It even has a bunch of stickers in the front of it. So I can put stickers on things. I

[00:08:18] **Tim:** mean, Adam, you are a published author, so writing comes natural to you. It's just good

[00:08:23] **Adam:** for you.

[00:08:25] **Adam:** I have no response to that.

[00:08:27] **Carol:** Humble brag. All right. What about you, Ben? Uh,

[00:08:31] **Ben:** this week I'm going with failure. Um, first of all,

[00:08:36] **Tim:** first

[00:08:36] **Ben:** of all, regardless of whether or not the clock is falling back or springing forward, it just kills me for an entire week, just physically and mentally, I don't know what it is about the subtle difference, but I just get, I just get messed up.

[00:08:52] **Ben:** Um, and then on top of that, I've been doing a lot of research into using ColdFusion custom tags to generate HTML emails. Which has been going very successfully until I moved all of it into a dockerized container. At which point the file IO overhead of being inside a container, at least on my local development environment, which is going to be worse than it would be in production, is worse than I feel like I'm comfortable deploying just yet.

[00:09:21] **Ben:** Um, and part of it is also what I consider a bug in the Lucy runtime that actually performs more file IO with custom tags than it should be doing. It really took the wind out of my sails because I've been putting weeks, really, of personal time into this research and seeing it perform poorly inside of a Docker container was really kind of a kick in the gut.

[00:09:43] **Ben:** And, uh, now I'm sort of regrouping and seeing if I can come up with a way to do kind of a compile time and then a runtime version. That has compiled away some of the custom tag stuff, but I don't know. I'm deflated. I'll put it, I'll put it that way. I was, I was flying high and now I'm, I don't know what the opposite of that is.

[00:10:05] **Carol:** Not flying high, not flying

[00:10:07] **Ben:** high.

[00:10:09] **Tim:** Do you think maybe the lack of RAM available to the VM could be causing it to just write to file first, like swap disks?

[00:10:16] **Ben:** Well, I think I'm on a Mac and I'm using Docker for Mac, and I'm, I'm not a very low level computer person, but what I've been told is that there's Docker for Mac, which actually runs its own VM, and then that VM has a file system, but then it's on top of the Mac's file system, which is itself on top of the Linux file system, I guess, under the hood, and there's, there's a lot

[00:10:36] **Tim:** of layers there, and I don't

[00:10:38] **Ben:** have a lot of, yeah, and it's, and it's not a dedicated, uh, uh, the machine is, Primarily my host and then there's the VM for the development, whereas in production, it's a hundred percent dedicated machine for production and it's much more powerful and it's more native Linux.

[00:10:57] **Ben:** So you got, you're cutting out the whole Mac version of the file system and then the VM running on top of that, I guess. Um, so I, you know, the reality is I could probably deploy it as is and in production, the performance would likely be. Sufficient, but I'm just, I'm not ready to take that leap yet.

[00:11:17] **Tim:** That's not good enough for Ben.

[00:11:19] **Tim:** Good enough for Ben.

[00:11:20] **Carol:** Do you have an environment outside of that you could deploy to and give it more like a production type test and find out?

[00:11:26] **Ben:** Yeah, I have a testing environment, but, um, I, I, I've, I've had, I hit such a mental block, so that's me.

[00:11:37] **Carol:** Boo. I'm sad for

[00:11:39] **Tim:** you. You'll get past it. I'll get past it. I know you

[00:11:42] **Ben:** will.

[00:11:42] **Ben:** I just gotta, I gotta find, it's, it's sometimes, I don't know if you guys ever write code this way, but sometimes I will start just writing as if there was an API that I could use, and I'm trying to find what the API should look like by writing the code that consumes it. Absolutely. And then start to work backwards.

[00:11:59] **Ben:** That's kind of what I'm trying to do right now, is I'm... I'm writing what I think the acceptable syntax would look like and then kind of jumping. I'm jumping back and forth between that mode of execution and then trying to do a little bit under the hood to fulfill what that API would look like and then going back to consuming it and trying to find this happy medium between elegance and usability and performance.

[00:12:23] **Ben:** Next week will be a triumph,

[00:12:25] **Carol:** I'm sure. If nothing else, your schedule will have adjusted. Yeah,

[00:12:29] **Adam:** 100%. I mean, I think we talked about this last week at some point, sometimes you have to do things the wrong way a bunch of times to find the right way. Yeah. Yeah.

[00:12:40] **Ben:** I've also, for whatever reason, this week, I just had a bunch of meetings and I'm not a meeting person.

[00:12:47] **Ben:** I can do like two meetings a day and feel fine, but anything more than that, I'm just destroyed. And I had like five meetings today and like five meetings yesterday. It's just been a tough

[00:12:58] **Tim:** week.

[00:12:59] **Adam:** Yeah, those are the worst.

[00:13:00] **Tim:** And yet I saw you advocate that an engineer should be on every call with.

[00:13:06] **Adam:** Right, and they're supposed to be reviewing pull requests while they're there.

[00:13:09] **Adam:** I'm not saying

[00:13:10] **Ben:** every engineer should be on every call.

[00:13:12] **Tim:** No, no, an engineer should be on every discovery

[00:13:16] **Ben:** call. But not the same engineer all the time.

[00:13:20] **Tim:** So not you. It's scalable. There's a way.

[00:13:26] **Adam:** You're being obtuse, Tim.

[00:13:29] **Tim:** I just saw him advocate for that. I'm like, Ben is asking for more meetings? That does not sound like the

[00:13:34] **Adam:** Ben I know. True. Okay. Well, I guess let's talk about interviewing. Where do you guys want to start? You want to start on the interviewee or the interviewer side? Let's

[00:13:43] **Tim:** start with the interviewee.

[00:13:45] **Tim:** I think most people have done that, right? In a smaller section than it would have been the interviewer.

[00:13:51] **Adam:** Right.

[00:13:52] **Carol:** Yeah, I mean, I feel like we've all had to be interviewed at some point unless you were lucky enough to just land where you're at and you've been there and stayed there and didn't really have to move around.

[00:14:02] **Carol:** So, I guess I can get going. So, I have interviewed a few times. We'll just say a couple times. I, um, kind of get burnt out pretty easy. So, I worked with TEMP for about six years and then I went and did a government job for, you know, almost Two years and then went back to work with Tim for about two years, and then I moved to Clear Capital, which is where I'm at now, and I love it.

[00:14:26] **Carol:** And all the jobs have been great. I, I haven't left for bad reasons. It's just needing change, needing a new code base, needing a new code base, needing something different. So, you know, I've Kobe. I like Kobe. Kobe. What's up, Kobe? Yeah. I don't know. It sounds like a cow for some reason in my head. Kobe beef.

[00:14:44] **Carol:** Yeah, yeah, right? Kobe beef.

[00:14:47] **Adam:** So, um This is going to edit.

[00:14:49] **Tim:** Sorry. Leave it all in.

[00:14:52] **Carol:** So, I've been interviewed a few times. So, going into an interview, I found that, um, I get really nervous. And I get in my head and I worry about a lot of things. And one of those is being a female engineer. And it's, um, not knowing what kind of room I'm going to walk into.

[00:15:11] **Carol:** Am I going to walk into a room of angry men, engineers who hate their jobs? Or am I going to be walking into people who are just super happy and upbeat? And not knowing that can really, like, mess with me. Personally, just having those, like, it messes with how I prepare for it, I guess. For the most part, so I've found that if I talk to the recruiter and I'm like, Hey, can you give me the names of who I'm going to be interviewing with?

[00:15:39] **Carol:** I go ahead and build these people up in my head as like really good people so that I'm walking into it, making the assumption that, you know, these four guys who are interviewing me are just super sweet guys and we're just going to have normal conversation. So I'm not so nervous going into it. So I don't know what other people do to prepare for it, but that's.

[00:15:58] **Carol:** That's kind of, like, one of my things. It's finding out who I'm going to be talking to, so I know, you know, what the room is going to look like when I get there. But the other thing is this whole digital approach to interviewing. There's nothing more stressful than getting, like, sitting in front of your computer, waiting for people to join a video call, and you know they're about to just start questioning you, and you're shaking.

[00:16:20] **Carol:** So, um, a few things that we had talked about previously with some other friends of mine was how, how, like, stressful it is to do that. And all of a sudden your camera doesn't work or, like, your headphones don't work or you don't know how to connect to anything through zoom. So I highly suggest anyone who's, like, going on an interview, get with a friend and make sure your software works.

[00:16:44] **Carol:** Make sure that someone can hear you speaking, because if you're trying to speak to three people who are interviewing you and they can't hear you, you're going to be fumbling through everything. Yeah, absolutely. Did that happen to you? No, no, it hasn't happened to me. I'm good at this stuff. Are you kidding

[00:16:59] **Adam:** me?

[00:16:59] **Adam:** Well, but no, I mean, that just made me think, like, absolutely, there's going to be an unconscious bias. They're going to have a bias against that person. It just needs a taste. Yeah, yeah. So, being prepared.

[00:17:15] **Carol:** So, it didn't happen to me, but my ex had to do a Webex call with a hospital that was interviewing him.

[00:17:23] **Carol:** And, uh, he was like, I have no idea how to use Webex. He goes, can I just call them from my phone and just talk? I'm like, they want to do a video call with you. It was like, you're just going to hold your phone in front of you. He goes, I don't know what I'm going to do. So I like. I had to set everything up on his computer for him, show him how to use it, and then push the button when they call.

[00:17:41] **Carol:** He was like, how do you answer this thing? So I was like, I met a lot of people deal with this with getting into these situations where they used to be interviewed in an office, sitting at a table with people, and now they're having to do it on a computer and. Most of them don't even know if their camera is not working how to make it work.

[00:17:58] **Carol:** Like, how do you enable that driver? They're like, I don't got a clue what's going on with it. So definitely do a test beforehand. It's funny, there's a,

[00:18:05] **Ben:** uh, I think maybe it's an XKCD comic where you can tell how old people are by which email host they use, like AOL versus Yahoo versus Hotmail versus Gmail.

[00:18:17] **Ben:** I feel like the same could be said about screen sharing. Like, whether you, it's a Zoom link, or it's a Skype link, or it's a Google Hangouts, or it's a GoToMeeting, or it's a Webex. When you mentioned Webex, I was like... What is this person, like 80 years old, who uses WebEx?

[00:18:34] **Tim:** With their GOC

[00:18:39] **Carol:** email address. It's just the hospital enterprise, you know. Once they pay for that license, they're not going to go off of it. Kind of like people who use Teams. They're not going to let you use Slack. Because man, that's built into what they're already using. So don't ask for that.

[00:18:50] **Ben:** Well, let me ask you this.

[00:18:51] **Ben:** Uh, when you go into an interview, I have not done a whole lot of being interviewed. What are the kinds of things that will throw you off in an interview? Have you ever been met with people who just rub you the wrong way? Or you get asked questions that totally take you out of your game? What, what, what trips you up?

[00:19:11] **Carol:** So. Things don't usually trip me up because I'm very honest. If you ask me something and I don't know what it means, I'm going to tell you that. I'm going to go, hey, I don't exactly know, I think this is what you're asking me about, but I'm not for sure, and if I'm wrong, say so. I'll jot down a note, I'll look it up, and I'll tell you later either, oh yeah, I do know that, I just didn't know that's what it's called.

[00:19:33] **Carol:** Because I'm terrible talking tech most of the time just because I don't know names of things. So I'm like, I don't know if that's what you're talking about, but here's what I think you're asking me. Or can you bring it down to another level and I'll explain it how I think it is, but I think the things that typically.

[00:19:49] **Carol:** Mess people up are those technical questions that are can you tell us how to do something and they're just not thinking about. Either a quick and easy approach and they try to like over complicate it. So then they're sitting there explaining and rambling on things that were probably going to be very

[00:20:06] **Adam:** simple.

[00:20:08] **Adam:** Yeah. I think that when I think about things throwing me off, the first thing that comes to mind is, uh, I think a pretty popular interviewing technique for the interviewer is to ask like increasingly difficult questions or something that they. Even just start with something that they have a reasonable assumption that you have no idea how to do or very little idea how to do.

[00:20:26] **Adam:** And the point of that would be to get a sense for how you deal with a problem when you don't know what to do. Right? Like, what are you going to Google? Or, you know, where are you going to look for answers? And I think that it's important to realize that that could happen in the interview and to be prepared to say, I don't know, but here's how I would tackle not

[00:20:48] **Carol:** knowing.

[00:20:49] **Carol:** It's actually funny you said that because when Tim interviewed me for the internship, I don't know if he's going to say any of this or not, but I'll say it. So he asked a couple questions. He was like, do you know what ColdFusion is? I was like, That's like radioactive something science. I don't know, like, it's definitely not a language.

[00:21:06] **Carol:** I have no idea what you're talking about. He's like, no, it's actually a language. He's like, okay, he's like, so what if you get stuck on something? Like, how are you going to find, like, your answer to whatever the problem is? I was like, that's what Googling's for. I was like, that's when I go to Stack Overflow.

[00:21:20] **Carol:** I said, if that doesn't work. There are people here who have solved the problem already, so hopefully I am on a team of people who I can then approach with questions. And if not, all my friends are engineers, so I will then ping one of them and say, hey, I found the problem I can't solve. My team can't solve.

[00:21:35] **Carol:** Can you help me solve this? I was like, so it's just all about being able to ask a question in a way that you can find an answer.

[00:21:43] **Adam:** And that got you hired. Yeah, that's a good answer.

[00:21:45] **Tim:** Nice. It got you. Because I can't tell you how many people who had worked there many years before you would come in and ask me a question that could easily be Googled and or go into Stack Overflow and then find an answer that I wrote five years ago.

[00:22:00] **Carol:** Yes. So. So then I look up code and I look up ColdFusion and I'm like, oh, bend the dough. Yep. Everything about break and then done. I've got names now. Now I know who to go to for things. Yes. So, yeah, and then, um, I think that's pretty much, like, some of my key things. Know who you're going to be talking to.

[00:22:20] **Carol:** Have an idea of what kind of room you're going into. Be prepared for that. If you're not comfortable with it too, like as a female, um, I've been on the opposite side too. So I've interviewed people as well. And we've been put in the position where, you know, someone has said, hey, I'm not comfortable being interviewed by a room full of men.

[00:22:40] **Carol:** And you adjust for that. So then have a female engineer in there so that someone is feeling more comfortable with the interview and not so isolated off into their own little Right. Yeah. You know what

[00:22:52] **Tim:** I mean? It could be intimidating. Yeah. I imagine. I'm not aware.

[00:22:56] **Carol:** It totally can be. Like, this interview I did for Clear Capital, my first interview, I asked the recruiter, I'm like, you know, who's, who's, who am I going to be meeting with?

[00:23:05] **Carol:** And she tells me the name. So then when I came into it, I'm like, all right, I know I'm going to be sitting at my desk on a Zoom call, or actually, I think it was Google Hangouts. And it's going to be for Senior software engineers from that team and they're all going to be guys and it was already made clear.

[00:23:21] **Carol:** It's casual dress. Don't feel like you have to dress up like they'll be in T shirts. Feel free to be in a T shirt so that I'm not standing there in a dress completely dressed up and then they're in T shirts and jeans and. Then I feel completely out of place too. Uh,

[00:23:36] **Adam:** the last job that I had an interview for, uh, I, the final phase of the interview was with like 15 people, which was, seems kind of crazy, but we were like, yeah, we were basically, it was like, they were pretty sure they wanted to hire me, but I guess that it was like, okay, last chance for people to veto.

[00:23:53] **Adam:** Right. So they got the whole team together and like the department director and it was just like, you could consider it a meeting room, but there was no walls, right? It was just like this room sort of attached to a hallway and they just like had a bunch of tables pushed together in a big circle and they were like, have everybody sit down and me on, uh, sort of like a buffer between me and the group and people ask questions.

[00:24:12] **Adam:** And that's where I got one of those questions that was like, you know, just off the wall. Something I had no idea how to handle, but it was, you know, how is he going to handle not knowing? Right. And just knowing that you're going to have to meet with 15 people at once is going to be big. And knowing, you know, these people are going to think better of you if you wear a suit, even though they do, uh, you know, business casual or whatever.

[00:24:34] **Adam:** Like, these are important things to know going in. Sometimes I

[00:24:39] **Ben:** just wonder if, if we just take interviewing way too seriously.

[00:24:44] **Adam:** Sometimes I think we do.

[00:24:45] **Ben:** Uh, I mean, you know, you're gonna hire people. The chance that you fire them is, you know, not negligible. The chance that they leave on their own volition is not negligible.

[00:24:58] **Ben:** Is the, is the difference in quality of people so vast that you can't train people up? I don't know. Sometimes it just seems like we put too much effort into

[00:25:09] **Carol:** it. One of the things that we do is, um, and I think I've said this before, is we hire nice people. Like that is one of the key things is to hire nice people.

[00:25:19] **Carol:** So if you don't mesh well with the team on the interview, you don't get hired. Like you have to be a people person and a team player. So that part of the interview, I think is key, but I think if you read too much into someone being nervous. And to not being able to answer because they're fumbling over their words, most engineers are introverted.

[00:25:39] **Carol:** So you've now put them in front of people that they don't know. So they're not going to want to talk to them. They're not going to want to have conversations, so you have to expect that it's going to impact their ability at times to. Be a very good interviewee, like, you shouldn't let that judge your ability to hire them.

[00:26:01] **Tim:** On the side of interviewing, um, I would say I've only interviewed once in my life. That's for the job I'm at currently. Um, before that I worked for my dad. My dad had a company, uh, a cleaning chemical company that is, he was a chemist and made car wax and soap. And I worked for him as my origin story. I talked about a little bit.

[00:26:23] **Tim:** Um, and then after that I worked for myself, um, doing a similar kind of adjacent. I became a distributor. I basically Anyway, it doesn't matter. I And then I interviewed at the company I'm at now. And I would say the two things that I would say were most important is one research, well, okay, three things.

[00:26:48] **Tim:** One, research the company you're looking at, right? Make sure it's actually something you want to do. So, uh, I did know some ColdFusion, so I was excited about that. Um. I knew what I wanted is number two. I wanted to be part of a company whose plan was eventually to, this was during the com, early com days, right?

[00:27:08] **Tim:** Everyone was like going IPO and selling and that's what I want. I want to be part of a company that did that. Now, it took a lot longer than we expected, but we did do that. Uh, and I would be able to get stock and everything in that. Um, so, so do your research. Make sure you know what you want out of the position.

[00:27:29] **Tim:** Third, don't take no for an answer. Because I was told no the first time by the interviewer. And I went above his head to go to the person who actually owned the company just to say, look, I'll do this job for free. Because I had a position where I could do that. You know, I was, my origin story, I was kind of doing a one day a week job and just doing programming for fun on the side.

[00:27:52] **Tim:** I'm like, I need to shift here and get a real job. And, uh, and so yeah, I made, I, I didn't take no for an answer.

[00:28:00] **Adam:** Mm-hmm. Yeah. I mean, if they've already told you no, what's the worst they're gonna do? Tell you No again, again,

[00:28:04] **Tim:** no, again. Right. Yeah. And they told me yes, and I said, I work for free. And they're like, no,

[00:28:08] **Adam:** we'll pay you.

[00:28:09] **Adam:** Yeah. I mean, not everybody can do that. That one's a bit of a stretch to suggest as a Yeah. Yeah. I'm just saying don't limit yourself, man. Yeah. No. Find a way. Right. Find a way or make one.

[00:28:19] **Tim:** Or if it's, you know, if it's not a right fit. Just find another. But for me, it's like, I knew that's what I wanted to do.

[00:28:25] **Tim:** So yeah, I went after it.

[00:28:28] **Adam:** So Ben had said something about, um, is there that much of a difference between people? Are we putting too much effort into this? And I think that I want to circle back on that for when we do the other half of this discussion about the other side of the table. But I think that a common topic of discussion among interviewers is the cost of hiring the wrong person.

[00:28:48] **Adam:** Yeah. And so let's come back to that. Um, and then, I mean, the only other thing I can think of for this first half that I wanted to talk about was like, kind of along the lines of what Tim was saying, you know, research the company, but have, have questions for the interviewers. Like, you should know if it's not already obvious, maybe some, you know, sometimes these companies have a public persona.

[00:29:09] **Adam:** There's just information about the way their company runs. That's public knowledge. But if it's not, you should know who's going to be on your team, how many people are there, what's the um, advancement, uh, I want to say ladder, that's not the right word. Career path. Yeah, what's the career path like, and what sort of projects are you going to be working on.

[00:29:30] **Adam:** There's a bunch of questions that I'm failing to remember here that are good. Actually, now that I think about it, I'm sure I can find it again. Um, there is a GitHub repo of, like, prompts for you to, like, think about to come up with good questions to ask in an interview. Yep, I've went through that. Like, questions for you to ask yourself where the answer is, what's the, the answer is a question that you can ask in the interview.

[00:29:53] **Tim:** In the show notes. Yep. I would say honesty is the most, so being completely honest. Obviously, you're trying to sell yourself, but you don't, people who lie will get found out. Oh yeah, for sure.

[00:30:05] **Adam:** Very quickly. Very quickly.

[00:30:07] **Tim:** So, don't lie, because if you feel you have to lie to get the job, it's not a job you're going to be able to keep, and you're going to be getting You know, a, a dismissal notice within three months if, if you do that, because it will be obvious that you don't belong there.

[00:30:21] **Tim:** So be completely honest and don't feel that, like Carol said, saying, I don't know, is not a wrong answer. That actually show shows a sense of humility and, and, and acknowledging you don't know something that you, you can find out. 'cause you can't teach someone who thinks they know everything.

[00:30:35] **Adam:** Right. And also saying, you know, I, I don't have the skills level that you're looking for in that program and language or whatever, but I'm eager to learn.

[00:30:41] **Adam:** That's a great answer, right? Mm-hmm.

[00:30:43] **Carol:** Yeah, that was 1 of the things I had to write it down was that, um, ask about the tech stack was to find out what tech they're actually using. So, if it's not something that you don't, if it is something that you don't know. You can take the time to at least go research, like, high level about it.

[00:31:00] **Carol:** So, when you do go into the interview, you know, you can communicate a little bit. Even if it's to say, I don't understand it, but the recruiter told me, you know, you guys are using Oracle. So I did go pull up Oracle and have been looking at how it differs from just T SQL. Like I was kind of looking at how you write it differently so that they see your motivation to learn what they're doing.

[00:31:22] **Adam:** I think having a

[00:31:22] **Tim:** recruiter actually is, is helpful because it is in their best interest to find out and discover things. For both parties, I've been on both sides of it. Um, and having a recruiter find out things about the candidate is extremely important and, and having been recruited several times and just went after it for a lark, uh, it's interesting to find out what you can learn about the company.

[00:31:45] **Tim:** Um, so yeah, having a recruiter is great, but if you're not, if you're just answering an ad, A lot of times that's not available to

[00:31:52] **Adam:** you. I think having a good recruiter is good. There's a, there's a lot of them out there that are just playing the numbers. They'll take every applicant they can find and, and supply them to every job that they can find and hope something

[00:32:01] **Carol:** sticks.

[00:32:02] **Carol:** We have an internal recruiter, so it's in her best interest that she hires good people.

[00:32:09] **Ben:** Going back to Tim's don't take no for an answer, I have, I've really only interviewed once in my entire life because I happen to stay at jobs for a long time. And I interviewed at this one place, I never heard back from them.

[00:32:23] **Ben:** And then like six or seven months later, I saw they posted the same position again. And I reapplied and I was like, Hey, I applied last time. Never heard from you guys, but I'm still excited. I still want to come work here. And then they, and they, and they hired me that time. So I, I guess my learning lesson there is don't be deterred by being turned down from a company.

[00:32:45] **Ben:** Like being turned down from a company doesn't take that company off the table forever. That was just that moment in time.

[00:32:52] **Tim:** That's funny. I. I put out an application one time and someone applied and he came in and he didn't get paid. It wasn't a bad, it's just, he didn't get the job. I only had one spot, right?

[00:33:04] **Tim:** So then later, like a few months later, we're hiring again. And, and he comes in, I'm like, did I interview, interview you before? He goes, yeah, you didn't hire me. I'm like, okay, I hired him that time. And he worked there for, for many years. It was even funnier. It's like my, my current, our current GM, She interviewed with me and I didn't hire her.

[00:33:28] **Adam:** And now she's my boss. She's everybody's boss.

[00:33:31] **Tim:** She reapplied for another position. And uh, yeah. And now she's, now I answer to her, so. It just, she didn't fit the position I was looking for. And sometimes people don't. Yeah, I mean, I was looking more for a coder and she was really more project management type material.

[00:33:47] **Ben:** I think, and maybe this is now swinging more towards the other side of the table for the interviewers, but what I look for and what I try to project It's just excitement and passion. And that to me is if you're interviewing someone and they don't seem to be excited, and I know that they're probably nervous, but if they just don't seem to be excited, I find that to be just like a big turnoff, especially if you point blank, ask them.

[00:34:18] **Ben:** Why are you excited about the languages you use? Or like, what's an exciting project you're working on and they don't have something ready to go that my, my gut reaction to that is this person's just not excited about being a programmer. Like that's, that's

[00:34:32] **Adam:** just not

[00:34:32] **Ben:** the

[00:34:32] **Adam:** person I

[00:34:32] **Carol:** want to work with. Yeah. I want people who love it enough to go home and do it.

[00:34:38] **Carol:** We may not all have time to do it, but I want you to love it enough to like, want to do that.

[00:34:45] **Tim:** Yeah, I mean, I, I hesitate to say that, that it was always one of my questions was what, what projects do you do in your free time? Um, and you know, one of them, he told me he, I mean, he was a terrible interview. You, you know, I'm Carol, he's a terrible interview.

[00:35:06] **Tim:** He was scared to death. But the second I asked, what are you working on your free time? He started telling me about this JavaScript library. He was working to figure out some unsolvable math problem. And then, you know, he got, I mean, he lit up. I'm like, all right, you're hired, dude. Yeah. You're so hired. I mean, if that's what you're doing your free time, I didn't understand what you just said.

[00:35:24] **Tim:** So that's cool. But. Got to step back from that a little bit. Some people, I mean, that, that's a, it's a very privileged position to be in, to have enough free time to do. Right. Absolutely. Some, some people can't do that. So if their answer is, you know what, I really want to go, I just don't have enough free time right now to do it because I'm trying to make ends meet.

[00:35:42] **Tim:** That's a totally legitimate answer and I accept that. I don't count points against that. Oh

[00:35:46] **Carol:** no, not at all. I mean, if you were to ask me, what are you doing in your free time? I'm like, what the hell's free time? Have you tried raising teenage boys? That doesn't exist. Like, there is none.

[00:35:58] **Adam:** I just thought of something.

[00:35:59] **Adam:** Let's talk about red flags. Um, this is something that hasn't, hasn't been a topic, like, in the Zeitgeist lately, but I remember, I just, a strike of lightning just kind of went through me here. I, I just recalled, not that long ago, people were talking about interviewers who wanted, like, Your Facebook password to like go on your Facebook and see what kind of things you're posting.

[00:36:19] **Adam:** Yeah, seriously. Red flag, red flag. Absolute red flag. Like, hell no. I don't want to work for a job that, that wants to go through my private life. And

[00:36:28] **Carol:** nope. Cause you know, they're going to be like that at work.

[00:36:31] **Adam:** Yeah, absolutely. Exactly.

[00:36:33] **Carol:** Micromanaging to like a whole new level.

[00:36:36] **Ben:** I definitely wouldn't want to work somewhere where in the interview, they're already preparing you for the additional work you'll have to do.

[00:36:44] **Ben:** You're like, you know, we're looking for people who just have grit and, and know how to, you know, work hard when they need to work hard. You're like, don't, don't paint it like this is going to be a difficult company to be at. Paint it like it's going to be an exciting company to be at.

[00:36:58] **Adam:** Yeah. Well, I mean, I appreciate the honesty from the interviewers at that point.

[00:37:02] **Adam:** I think they're maybe trying to pull a curtain over that a little bit, like hide it a little bit, but also like, you know, tell you what's going on and set the expectations. So, I mean, I appreciate that honesty, but at the same time, like you're right, like. Ideally that's not the situation that you're putting your candidates into.

[00:37:20] **Carol:** What about if they're like, oh man, we need like a rockstar engineer to come in and like handle these projects. Like it's gonna take extra hours and you know, you may have to work some but you'll be a rockstar doing it. to me like that's pay me rock our money problem. Yeah. Like I don't wanna be the only person capable of doing the work so much that I am the only person capable of doing the work.

[00:37:41] **Carol:** That does not sound appealing to me.

[00:37:44] **Tim:** I think another red flag is, If in the interview they seem determined to trip you up to make you make you feel bad and look bad just to see how you react because I've I've not done that but I've heard of people that have gone through that where they're obviously trolling to see at what's your breaking point.

[00:38:05] **Tim:** That's strange. I wouldn't be interested in a position like that. I would say red flags from the other side.

[00:38:11] **Adam:** Okay. Yeah. Yeah. Let's use this as our pivot point. So red flags from the interviewer's perspective.

[00:38:15] **Tim:** From the interviewer's side. So I've had some really good hires. Carol was one of my better ones.

[00:38:20] **Tim:** Thank you. And, uh, she was a rock

[00:38:22] **Adam:** star.

[00:38:22] **Carol:** Aw. Wait. Hang on. That's bad. No. Okay. Okay. I don't know. I'm confused now. We're good. Yeah.

[00:38:29] **Tim:** I hired this one guy. He looked so good on paper and I interviewed him and he was like charming and. He hit, but he was like, told me he had like 12 kids. Like, okay, that's kind of interesting.

[00:38:38] **Tim:** And he, and he at one point used to be a minister. I'm like, all right. Um, not anything wrong with that, but it's like, okay. So, but he did have like credentials and coding and everything and like, okay. So, you know, he was working in a remote area. So I, I bought him a laptop and everything. He never showed up for work ever.

[00:38:58] **Tim:** Not once,

[00:38:58] **Adam:** not even the first day. Wow.

[00:39:01] **Tim:** Not even the first day. Bananas. And so looking back, I realized he was, he was on unemployment and had to go look for a job and he didn't expect to get, he just put his resume too good and he interviewed too well and he got hired. And, uh, and he's like, yeah, I mean, yeah, you've got 12 kids and you're not, he wasn't married.

[00:39:23] **Tim:** So he's paying the child support for all those kids. The last thing he wanted was a job where they're going to garnish his wages. Holy moly. And, and the other one, this is really hiring, but this is, uh, well, it is hiring. 'cause I, I was trying to directly hire in India for a while and I I did, I did do that for, for a bit.

[00:39:41] **Tim:** Um, there's, um, a website called Freshers World. I think it's Freshers there. I don't know what it's, I, we'll, I'll figure out what that is for the show notes, but, Basically, you can see people that are graduating out of India, um, and, and hire them directly. And I found a company that would handle payroll and all that stuff for them.

[00:40:01] **Tim:** Uh, and so I interviewed a bunch of them, but it's like, what I found with, with hiring people in India is like, asking questions about their family was extremely important. Because if, you know, if someone was going to get married or a mother was going to die, I found that, this is just me, maybe this is just my experience, but if, if something family came up and they were just out of college, a lot of times they would just.

[00:40:22] **Tim:** Disappear from their job. Right. And go back to the village that they came from. They take care of their family. To take care of their family. Right. Which I get. I get it. But they wouldn't say anything. They would just ghost. Yeah. Um, so I got, when I started hiring people from India, I would, uh, ask a lot of questions about their family situation and how old their mother was and how old their father was and.

[00:40:43] **Tim:** You know, was anyone planning on getting married soon or, you know, things like that.

[00:40:47] **Adam:** You got to be careful with that though, especially here in the United States. There's some of those questions you can't even ask. Like you have to find out. I wouldn't do

[00:40:54] **Tim:** that. I wouldn't do that at all with someone in the

[00:40:55] **Carol:** United States.

[00:40:55] **Carol:** Yeah. No, I saw a post recently. Um, I'll see if I can find it so we can link it, but it was a mom who was talking about being interviewed and basically the recruiter got back with her and was like, they decided to pass on you because, you know, if you can't focus. During the interview 'cause her kids were running around mm-hmm.

[00:41:14] **Carol:** and was distracting her, then you're not gonna be able to focus during the day while you're working. So she felt like if she hadn't had her kids there, like they wouldn't have even known, she didn't have kids like that. She had kids. Mm-hmm. and she probably would've gotten the job. Mm-hmm. So, but you can't ask questions like that here.

[00:41:30] **Carol:** You can't be like, how's your family life? You know, are you going to have any distractions going on? Whereas if, you know, over there, it's okay. I mean, I don't even know if it's okay over there to ask those questions.

[00:41:40] **Adam:** They have

[00:41:40] **Tim:** very little super loss over there.

[00:41:43] **Ben:** Yeah, that even, but even more than a legal constraint.

[00:41:46] **Ben:** I, when I first started interviewing, I didn't think I was a very good interviewer. I still don't think I'm a very good interviewer. Um, but I, I sort of over-indexed on trying to connect with people on non-technical things. So I was always asking people if they had pets or they had a dog and we could talk about our dogs or, you know, what do you like to do in your free time?

[00:42:05] **Ben:** And then we all had to take unconscious bias training at work a couple years back. And it was all about, don't ask people about their family, don't ask people about their hobbies because like, then what you end up with is a whole team of people who like the same stuff and all have dogs and all have the same hobbies and you don't get the diversity of perspective that you really want on a team.

[00:42:27] **Ben:** And I was like, Oh, this is, this is all of the stuff that I asked. This is terrible. I don't know what to talk about. Now.

[00:42:33] **Adam:** Yeah. Code. Yeah.

[00:42:36] **Ben:** Apparently you're supposed to ask them about the thing you're hiring them for.

[00:42:39] **Adam:** Who'd

[00:42:40] **Carol:** have thought? I don't know. On the flip side, as an interviewee, you want to make those connections, so you do look for those things and people interviewing you to get the conversation rolling, so there is a connection there.

[00:42:51] **Carol:** So, like, one of the guys that recently interviewed me, like, is, if you look at Adam right now, he's got, you know, his flags behind him. So, this guy had, like, a baseball flag behind him. I'm like, oh, you like baseball? I'm like, I love going to the Braves games. I don't like baseball. I don't really like sports.

[00:43:08] **Carol:** There's nothing like going to a Braves game and eating a hot dog and just having a beer. I'm totally cool with that all day long. I'm not a sports fan, but it then just got the conversation going. And then the two other guys chimed in and talked about how much they missed it during COVID. So then it totally was a really good icebreaker though, to get you to feel like you're connected.

[00:43:27] **Carol:** So from an interviewee side, those conversations are great to start having. Yeah, from the other side, you can't really start those conversations because like you said, you get that bias again, or bias for the person because you have some connection with them, or, you know, you then cross the boundary of asking something that they answer that really you shouldn't have been

[00:43:47] **Adam:** asking.

[00:43:48] **Adam:** Yeah, so what I'm hearing is, lying about technical ability, bad. Lying about social interests, good.

[00:43:54] **Carol:** Well, I didn't necessarily say I loved baseball. I said I like going to baseball games, which I like going and having a hot

[00:44:00] **Adam:** dog. Own the gray area. Yeah, yeah. Carpe Grisio. Yeah,

[00:44:04] **Carol:** there you go.

[00:44:05] **Adam:** Done. On it.

[00:44:06] **Tim:** I do think it's important for interviewers to try to make the interviewee comfortable.

[00:44:09] **Tim:** I agree with that. Yeah. Because you're not going to get the best out of them. Some people like to interview and they like to like be, try to catch them out. Um, I don't, I personally don't feel that benefits anyone. It just makes them nervous. You're just going to get reactive, combative people. If that's, that's that, if that's your technique, make them comfortable, make them feel that it's a safe space to say whatever they want.

[00:44:35] **Tim:** And to be honest, that number one thing is, is encourage honesty.

[00:44:41] **Adam:** Yeah. And maybe even, you know, if, if it's true, say something like, you know. Yes, these are the technical skills that we're looking for, but we are also very willing to find a person who is not already knowledgeable in these things, but has a demonstrated ability and eagerness to learn.

[00:44:58] **Adam:** And, you know, I, I personally would much rather hire somebody who always learning new stuff, who, uh, is excited about learning, than somebody who already knows the thing that I am hiring for. But Has no interest in anything. Like I come in, I do my job, I don't talk to anybody, and then I go home like, that doesn't

[00:45:21] **Tim:** work.

[00:45:22] **Tim:** Yeah. Yeah. So, so I don't know if it, there was a, it was a ColdFusion Facebook group and one of the guys I, I put in the show notes, he posted, so back in the day, back in the.com day, uh, bubble, he was a, Headhunters would constantly, like, be sending people and, and, and grooming people to, to interview with them.

[00:45:45] **Tim:** And so they would tell the recruiters that they, they were looking for people who were, uh, fluent in MOVA, which was a completely made up programming language. Did you guys see this? I saw

[00:45:55] **Adam:** this, yeah. I have not

[00:45:55] **Tim:** seen this. So they even came up with an O'Reilly book cover. Like, you know, the O'Reilly, they always have like an animal.

[00:46:01] **Tim:** So it was like a lion. Uh, with a, with a crown on its head, it was MOBA. It was, uh, uh, multiple object versionless.

[00:46:13] **Tim:** Uh, architecture was what It sounds so fancy. Yeah, it's a completely made up language. And they did that so that, um, they, they, they would, you know, if someone came in, they're like, yeah, you know what? I'm dabbling around with Mova. Kind of enjoy that. I'm kind of interested in, you know, learning more about that.

[00:46:29] **Tim:** They're like, okay, this, this person is completely full of BS. And they would, they, they, they, That's an

[00:46:34] **Adam:** interesting tactic.

[00:46:36] **Tim:** Uh, but what's funny is like, so everyone on the thread started re responding and I was like, oh yeah, I remember I spoke at Movic Con back in the day. , best thing about Mova is the, is their community and, uh, a newspaper in England picked it up the register.

[00:46:49] **Tim:** Do Coda UK picked up the, and they picked up the whole article. They even quoted me in the article, uh, about, about this whole, you know, fake language. But he used that as a, as a way to filter out candidates that are lying. So, yeah, so don't lie, don't lie during your interview,

[00:47:05] **Adam:** you'll get caught out. Yeah.

[00:47:07] **Adam:** Yeah. It's not worth it.

[00:47:09] **Ben:** This is kind of meta to interviewing itself, but the one thing that drives me crazy that I hear in the background a lot is people talking about wanting to work on their diversity initiatives, and then they'll say things like, of course we want a more diverse team, but we also want to hire the best person for the job.

[00:47:30] **Ben:** And I always think to myself. But you can't in one breath say that having a diverse team leads to better solutions. And then say, but we'll of course hire the right person for the job. Cause you're sort of negating the thing that you just said about having a diverse team. Like how can you have the best person for the job if having a diversity makes your solutions better?

[00:47:50] **Ben:** Like it's, um, it just drives me crazy. Because like people are always hedging their bets.

[00:47:57] **Adam:** Diversity is a tough topic. I mean, we're coming out of the word, the mouth of a white guy talking to two other white guys and a white girl, uh, I'm sorry, white woman, um, like I, I totally a hundred percent recognize the importance and it is a hard thing to do.

[00:48:15] **Adam:** Right. I think that that is the important thing to say is like, it takes effort and you have to believe in it and you have to understand. You're not going to be perfect out of the gate, but you have to just commit yourself to doing better next time, doing better next week and better than that the week after that.

[00:48:30] **Adam:** But,

[00:48:30] **Ben:** and I think part of also what drives me crazy about those statements about we want diversity, but of course we also want to hire the right person for the job, I think is this sort of impossible belief that you're going to hire the person who can come in and just crush it constantly. Yeah. Yeah.

[00:48:48] **Ben:** Because the reality is most of the people you hire are going to be fine. And they're not going to be amazing, and they're not going to be terrible, they're going to be fine, and they're going to learn on the job, and they're going to get better as they go. This idea that you're going to miss this opportunity to hire the proverbial, you know, right person for the job, I think is, you're setting yourself up for disappointment anyway.

[00:49:13] **Tim:** I get what you're saying. It's like they're saying. Yeah, of course we want to do that. But, you know, if, if no one that's followed, you know, is, we consider diverse applies or we consider, you know, we're just going to go ahead and hire what we normally hire. Right. Right. It's, they're giving themselves a pass.

[00:49:29] **Tim:** Yeah. Yeah. One thing I've learned that anything after the but in a sentence, yeah. Totally negates the

[00:49:35] **Carol:** thing that worked. That, that first part doesn't matter anymore. You just wiped

[00:49:38] **Adam:** out the first part of your sentence. Especially if the second part should be assumed from the beginning. Like, of course you want the best person for the job.

[00:49:45] **Adam:** Right.

[00:49:45] **Tim:** Yeah. Who says, hey, let's hire the not best person for

[00:49:49] **Adam:** this job. Right. Let's hire someone who's just We want somebody mediocre. Yeah. I

[00:49:52] **Tim:** mean, you hire on potential, honestly. I mean, no person comes in just because they haven't been in the company and they don't know how you work. You're hiring on potential always.

[00:50:07] **Tim:** It's just some people's potential. The gap is bigger than others. And so you're, you're taking a risk, but I mean, sometimes you take a risk, you, you get really good rewards. So don't be afraid of that gap. Don't be afraid of that risk. One of

[00:50:22] **Ben:** the guys on our, uh, on our board, this guy, Amish Johnny, years ago, he said something, I can't remember the exact quote, but it was, he said, you have to build a company with the assumption that everyone you hire is going to be mediocre.

[00:50:38] **Ben:** Because hiring rock stars is not a sustainable business model. Nope. That you have to have processes in place and structures and organization that allows people who are mediocre to thrive and a business built on mediocre people to thrive. I agree. Cause you can only get so far with

[00:50:55] **Tim:** rock stars. And there's sort of like a recipe.

[00:50:58] **Tim:** I mean, I see that human beings are very complex and if you have a team of people and you're hiring someone for a specific team. And you have a very strongly opinionated person who's working on the architecture. The last thing you want to do... Assuming they're performing well, last thing you want to do is pull in some other highly opinionated person who's concerned with architecture.

[00:51:27] **Tim:** Right? Because, I mean, there's certain people that that's just, they have very strong opinions about how things should be done. And if someone disagrees with them on a bike shedding type topic, they will waste tons of time.

[00:51:41] **Carol:** Everybody's time.

[00:51:43] **Tim:** Everybody's time going over this one thing. And so, you know, if you're hiring for this role, you know, we're going to put them on this team, and this person's on this team, and this person's on this team.

[00:51:52] **Tim:** We kind of really need a person who maybe is like a go along to get along kind of person who they do quality work, but they're like, you know what? They're, they, they believe there's multiple ways to do the right thing. And so there's more than one way to skin a cat. So you, you, you're like, is that your personality?

[00:52:07] **Tim:** You kind of figure that out through questions. Like, yeah. Okay. You can go on this team. If someone comes in and goes, no, the only way to do JavaScript is to this, and you gotta do this, and this, and this, and you're like, yeah, you're not gonna fit in on that team, well, we'll, we'll, we'll, we'll, we'll put you in the back burner, and maybe the next time we're building another team, you can come on and start that one, but.

[00:52:25] **Tim:** Yeah, not, not with, not with this other person on the team. It's just going to be head butting.

[00:52:29] **Adam:** That actually reminds me of something that one of our patrons, Mingo, shared in our Discord. Um, it's a website, howtodeal. dev, and it's basically how to deal with difficult people on software projects and it lists out, okay, so it breaks down into categories, product managers, designers, project managers, development managers, developers, and quality assurance.

[00:52:49] **Adam:** And then within each of those categories, there's a bunch of different like personality types, right? So like, let's talk about developers. Here's the, the. Here's the list for developers. The Rockstar, the Aspiring Manager, the Bull in the China Shop, the Diva, the Extreme Overestimate, oh, Extreme Overestimator, the Extreme Underestimator, the Hostage Taker, the Idealist, the Incompetent, the Soldier, which I think is kind of what you're talking about, the, what was it, uh, The one that goes along and just go along to get along.

[00:53:14] **Adam:** Yeah, the Soldier. The technology enamored and the legacy maintainer. And so the whole, uh, I think I didn't spend a ton of time on this website, but I think that the impression that I got is that the whole point is to kind of tailor your discussion to find a way to work with each of these types of people.

[00:53:30] **Adam:** Like there, you have to treat everybody sort of uniquely and individually for their personality. Everybody has different goals, but at the end of the day, you need to build a team that can work together to reach your company goals.

[00:53:43] **Ben:** One thing that I struggle with a lot when interviewing is at the end of the interview someone will inevitably come to me and say, what do you think about this person?

[00:53:53] **Ben:** Do they raise the level of quality at this company? Should we hire them? Are they better than this other person we interviewed? And I feel like I'd never know how to answer that question. I'm, I can tell you that I enjoyed interviewing someone. I can say that they hit a couple of points that maybe I was looking for.

[00:54:09] **Ben:** If But I can't, I feel like I never have the ability to become more definite about whether or not this person's really a value add or it would be a mistake. I'm like, I either enjoyed the interview or I didn't enjoy the interview. That's, that's my. And that's, it's terrible because it's not, that doesn't help anybody who wasn't in the interview decide on what the next

[00:54:30] **Adam:** step should be.

[00:54:31] **Adam:** That speaks way more to like culture. And I think that when it comes to interviewing, the idea of a culture fit is a trap, right? So like company culture is a big topic right now. And I think that I don't know enough about it to speak authoritatively. I'll just say that things that come to my mind, are a trap, right?

[00:54:50] **Adam:** Like if you go into an interview trying to pick a person that you want to hang out with that weekend, you're going to get somebody that you would like to hang out with that weekend and maybe that person is going to be a good fit for your company technologically. Maybe they're not. Right. Culture though, gosh, we, we, maybe we should try to find like somebody who actually knows a lot about that and bring them on for our discussion.

[00:55:12] **Adam:** But, uh, yeah, I think that the idea of interviewing for culture, there'd be dragons here. Well, and,

[00:55:20] **Ben:** and so I work in an entirely remote company and I know that that's a different context than a lot of people work in, but I oftentimes wonder if the idea of a cultural fit is almost blown way out of proportion because really I have meetings with people and then I disappear down into my coding hole and then I come up and I have a meeting with people and then I disappear again and it's, you know, I'm, I'm not going out to lunch with these people.

[00:55:47] **Ben:** I'm not grabbing a bite to eat. After work, we're not going to movies together. We have meetings and we're generally congenial. Yeah. But like, I don't, you know, if you're passionate about your work and you love what you do, that's sufficient. I don't, I like. The idea that there has to be more than that, I almost feel like is overblown.

[00:56:10] **Adam:** I agree, but I think that there's a few more things that I would put on that list. So like communication ability and style, right? You want to be respectful, but also, uh, you don't want to take away too much of somebody's time by over communicating and, or just like, you know, not being able to summarize.

[00:56:26] **Adam:** That sort of thing. There are other soft skills involved there that are important to look into, but I don't, I don't want to try to speak authoritatively on them because I'm going to do a bad job and the things that like, again, when, when I think about trying to interview for culture, it's tough because instinctually I go to, do I like this person?

[00:56:51] **Adam:** And that's not, that's not culture. No. Yeah, exactly.

[00:56:54] **Tim:** Yeah. Yeah. How are you going to get that out of, you know, um, Maybe at most you're going to interview, if you do two, three interviews. Hour apiece, three hours. You know, they're putting on a show, you're putting on a show. All you're getting is window dressing.

[00:57:07] **Tim:** You're not getting any idea of, of

[00:57:09] **Adam:** culture. And apparently they lie about liking baseball and , right?

[00:57:14] **Carol:** Hot dogs are good.

[00:57:16] **Tim:** Beer's good. They lie about, they actually want the, if they actually want the job. And, you know, don't, don't wanna come off unemployment.

[00:57:22] **Ben:** I was listening to an interview on a podcast actually just a couple of weeks ago.

[00:57:27] **Ben:** I can't remember which one at all, but one of the hot takes that the guy in the interview threw out was this idea that interviewing people for jobs is basically a ridiculous way to hire. That you fool yourself into believing that you've learned anything about this person. In the hour, two hours or three hours that you got to talk to them, that really the only thing you should be doing is looking at their work and basing your decision almost entirely on the work and that you'd be much more successful that way.

[00:57:55] **Adam:** I think it's tough. Like interviewing is such a tough thing to do, right? Because again, you know, there's things like that. There's truth in what you just said, right? But I think that people try to take those bits of truth. to some sort of logical extreme, and that's when you end up with, you know, write me the algorithm for bubble sort on this whiteboard.

[00:58:17] **Adam:** With, you know, without using Google and you have 10 minutes, go . Like . That's not a good interview question.

[00:58:26] **Carol:** Uh, I would just share, I would share, I would just stare at the expo marker and be going, oh, take, take a

[00:58:32] **Adam:** lid off and start puffing it.

[00:58:33] **Carol:** Smell. Yeah. Like you can't put someone on the spot like that.

[00:58:37] **Carol:** That's not. No one's going to achieve and no one's going to excel in a

[00:58:42] **Adam:** situation like that. Unless the job is to code at gunpoint, like, that's not a realistic interview question. Yeah. I think

[00:58:49] **Tim:** for both sides, both should be able to, you should ask, and if you're interviewing people, you should tell them.

[00:58:57] **Tim:** What does success look like for me at six months?

[00:59:00] **Adam:** That is a great question to ask. You know how I was asking, I talked about, you know, having questions to ask your interviewer. Yes. What does

[00:59:07] **Tim:** success look like for me at 12 months? Right. So. And to make it clear as, you know, to be objective, because hiring is a complete crap shoot.

[00:59:16] **Tim:** Yeah. I mean, it totally is. Let's, I've gotten lucky. I've, I've had more successes than failures, um, but the failures I've had, I've just been so incredibly embarrassed about. I mean, like they were just bad. Um, So, it's like, make it apparent, like, if you haven't told them up front, look, at six months, here's what I expect you to be able to do, and at 12 months, here's what I expect you to be able to do.

[00:59:42] **Tim:** And if you're not there at six months, you're gonna get a warning, and possibly fired sometime after that. And at 12 months, if you're not doing it, you're definitely getting fired. Because the worst thing you can do is just, just, string them along. Keep, keep failing, right? I mean, you gotta, failing early is a good thing.

[00:59:59] **Tim:** Failing early as possible is a good thing, but giving someone a chance at the same time is also a good thing. So it's a crapshoot. Just make sure you have your expectations clear on both sides.

[01:00:09] **Adam:** So actually, that's a, that's probably a good segue into the topic that I mentioned earlier that I wanted to come back to, which is the cost of hiring the wrong person, um, which, and now that I bring it up, I thought of another sort of related thing, which is, um, Zappos, the shoe company, pretty sure it's shoes.

[01:00:23] **Adam:** Um, they, I don't know if they still do this, but they had for a long time and they were famous for this policy of like on your one month anniversary or something like that, they offered you. And not insubstantial amount of money, like 1, 000. They would say, here, if you quit today, here's 1, 000. Like

[01:00:40] **Carol:** it didn't work.

[01:00:41] **Carol:** That's okay.

[01:00:43] **Adam:** The whole idea is you've been here for a month. You know, better than anybody else right now, whether or not you are going to enjoy your time here, whether or not you are going to be able to contribute to this team. And it costs us less to give you a thousand dollars and send you on your way right now than to have you stay on for another six months and do poor work and hate your work and have the rest of the team dislike working with you.

[01:01:07] **Adam:** Like it's just opportunity cost. I really

[01:01:11] **Carol:** like that idea.

[01:01:12] **Adam:** Fail early.

[01:01:13] **Tim:** Yeah. Better than failing way late.

[01:01:15] **Adam:** Right. And so that, that kind of brings me around to the other topic, which was the cost of hiring the wrong person. So I, I. Again, I think that there was a nugget of truth in what you were saying there, Ben, about, um, when you take all of the potential candidates that are out there in the world looking for jobs, there's the spectrum and there's a bell curve.

[01:01:33] **Adam:** There's a lot of people toward the middle of that bell curve. where, you know, they're, they're going to be fine and some will be a little bit on the lower end of fine and some will be on the higher end of fine. And then you're going to have a few rock stars where you'll get lucky and you're going to have no matter how hard you try, you're going to have some people that just don't work out.

[01:01:48] **Adam:** Right. And I think the goal is to not, not hire the people on the low end of the bell curve as much, as much as you can. Because, like that, uh, story with the thousand dollar offer to leave illustrates, like, the cost of hiring the wrong person is, you have to spend the time not working, not getting the work done, uh, that you were hoping to get done by hiring this person.

[01:02:10] **Adam:** You've been paying them to not do the work. And they're potentially dragging down the team. And then you had a bunch of other people's work to onboard them, right? All the HR and paperwork and payroll and blah, blah, blah, to deal with all that. It seems

[01:02:23] **Ben:** like as an industry, we should somehow be trying to find ways to make that more friction free.

[01:02:31] **Adam:** The process of onboarding? Yeah. Like what

[01:02:33] **Ben:** if we could make the cost of making a mistake just much lower? I don't honestly know what actually goes into onboarding and then offboarding people. But if you can

[01:02:43] **Adam:** move that towards zero. I think that the, the problem is that it's going to be vastly different.

[01:02:50] **Adam:** Yeah. For almost every company. Yeah. So yeah, trying to generalize that. That's a very developer answer, Ben.

[01:02:59] **Carol:** We should be able to automate this.

[01:03:02] **Ben:** Developing my salt passing machine. It's an XKCD comic. Um, there, there is something to be considered though about the cost of person hours when it comes to interviewing.

[01:03:14] **Ben:** I mean, if you have an interview process, multiple tiers of people and each tier has. Multiple people on your side in the interview and then you're talking to other people after that and you're filling out forms about evaluating this properties and that properties of the interview and like how many tens of thousands of dollars did it go in to try just to find

[01:03:35] **Adam:** the right person?

[01:03:37] **Adam:** That reminds me a lot of, uh, some interviews that I did at my last job at, uh, University of Pennsylvania. This was not their normal approach, but, uh, we had a younger, uh, supervisor and he wanted to, like, bring in some fresh new ideas and stuff. So we were hiring for my team and what we did was what he did.

[01:03:55] **Adam:** I don't want to take any of the credit. He scheduled all of our potential candidates that gotten through the initial screening to come in on the same day. For the entire day and he's scheduled everybody on the team as well as a couple of directors and a couple of people from other teams that are just like they've been with the company a long time and they know the organization well.

[01:04:14] **Adam:** Or maybe they have like a, a good, uh, bit of technology knowledge to be able to assess that person for what we're looking for real well. And so we did basically like a round robin of, um, all of our candidates. So say we had like eight candidates come in, we broke up all of these, uh, interviewers into eight teams.

[01:04:31] **Adam:** And so you would go sit, the, the candidate would go sit with one group of people. For half hour, 45 minutes, whatever. And then we take a quick break and then they would do it again and again and again and again all day, which is a frigging marathon. But personally, I really liked it. And at the end of the week, like you have this Monday all day, you spend interviewing everybody on the team.

[01:04:53] **Adam:** You know, you've got 15, 20 people participating in this interview process and all of them spend the entire day interviewing. And then maybe you take a day off to just sort of Relax and let it ruminate. And then you come back on Wednesday and you have like a half day just get together and discuss things and, and then like Thursday you make a decision and Friday you send out an offer like one Oh wow.

[01:05:13] **Adam:** One week to interview like Nice. It was intense speed dating. Yeah, yeah, yeah. It really was. It was intense, but it was kind of awesome. I kind of like that a lot. Interesting idea.

[01:05:26] **Carol:** Yeah. 'cause usually it takes a while 'cause they have to interview multiple people and you have to wait for them to decide if you're the candidate or not.

[01:05:32] **Tim:** Yeah. Yeah. It's almost like the Hunger Games,

[01:05:35] **Adam:** because all of them are going. Yeah, yeah. And that was another really awkward thing about it, right? So, like, we get They

[01:05:39] **Carol:** saw their competition, yeah.

[01:05:40] **Adam:** Yeah. Because

[01:05:41] **Tim:** they're all competing, but

[01:05:42] **Adam:** they have to be nice to each other. We had all the interviewers and the candidates in the same room at the same time to start the day, and we're like, this is how it's gonna go.

[01:05:50] **Adam:** So they saw each other, they saw who their competition was, and From District

[01:05:53] **Tim:** 13, Katniss Eberdeen. Welcome to Thunderdome. Yeah, right? Are we still talking about, uh, the

[01:06:00] **Adam:** cost of hiring wrong? Are we talking about... Sure, if you got something. Yeah, go ahead. So I, I got both

[01:06:05] **Tim:** actually. So, so cost of hiring them wrong.

[01:06:08] **Tim:** Um, so one time we, we, we used a headhunter to hire a very expensive person that came from a A very large, well known company that is many multiples times bigger than our company at the time. And you know, his was a person, he wasn't a developer. He's the kind of person that would be in front of customers and unbeknownst to us, he didn't, he passed a background check, but he had a very bad substance abuse problem.

[01:06:32] **Tim:** And we were like, well, something's weird about this guy. We didn't really know what it was. Uh, but eventually we figured it out and, but we were so. It took us a long time to get to wrap our arms around because it's like, you know, we paid a lot of money for this guy. And he came highly recommended, but, you know, maybe we're just misconstruing the situ no, no, he's a crackhead.

[01:06:52] **Tim:** And, uh, yeah, but, but, but at that point, you know, it's like with recruiters, typically there's like a, a break in period where you, you know, if you fire them within that period of time, then you get your money back or get to use it again for someone else. We'd already passed that, so. All that money was just burned up and, you know, he'd already killed goodwill with customers and people that he'd been I thought you were going to say he

[01:07:13] **Adam:** killed a man.

[01:07:15] **Adam:** I don't know. Whatever. That was our competition.

[01:07:17] **Tim:** Yeah. So, yeah. So that, that can be the cost of hiring badly. So like, like I said, failing quickly is important in that. If you, if you feel early on, wait, this is a complete failure and that's why having those objective goals are important. So you can say that rather than just saying it's my feeling, right?

[01:07:33] **Tim:** So that's, that's one of the costs of, of hiring. Hiring poorly, but the opposite side of it, you know, what you were saying, I think one of the things I was most proud of, we don't do this now. Hopefully, we'll do it again sometime, but like when I hired Carol, that was, she mentioned she was an intern. So, we were, I was going to colleges, actively recruiting, asking for professors from coding classes, who are your best and brightest?

[01:07:56] **Tim:** I got jobs for them. And so, you can't really do this with people who are experienced, this is people who are just starting, you know, no person who's already has a mortgage and kids are going to take a paid internship. But someone just starting out might, right? Take care. Yeah, working part time and, and that is, it's good for both, right?

[01:08:15] **Tim:** So I think it is. So we got to know Carol and I think probably like six, seven other people that we eventually hired, you know, got to get to know them, got to see how they worked, got to see their work ethic and they got to see how our company worked. There was, there was no, a lot of times there's so much shadow play going on during an interview on both sides of the table, you know, company might be trying to make themselves look better than they really are and the interviewees trying to make themselves look better than they really are.

[01:08:38] **Tim:** Yeah. She was there, right? She, she saw warts and all what, what we were and, you know, she's decided to stay for a good long time until she didn't. So I was most proud of that. Cause I think it really, we got some really good quality hires. You can't obviously do it with everyone, but. I think it, you know, that's a way to pursue.

[01:08:59] **Tim:** And it's

[01:08:59] **Adam:** good for the ecosystem or the industry in general too, right? I mean, there's so many jobs out there now that are like entry level job and it requires five years of experience. Like, eh, hey, that's kind of a crappy thing to do. That's not entry level. That's low level, but it's not entry level, but like growing your own developers, you know, taking on interns or, or hiring college kids, whatever.

[01:09:19] **Adam:** Some way to take on people who need to build experience and giving them experience. Unpaid

[01:09:26] **Tim:** interns, I, I don't even know how that's even legal. Yeah, it shouldn't be. If it is, uh, but I, I don't think it's, there's, there's, there's nothing to lose on their part and there's nothing, you know, you gotta pay an intern if they're gonna be working for you.

[01:09:39] **Tim:** Right, you have some skin

[01:09:40] **Adam:** in the game. Yeah, both sides

[01:09:42] **Ben:** do, yeah. One of the things that we used to do historically at work, which drove me crazy, We would hire people and then immediately have them start building business critical software. And I'm like, no, you don't do that. Have them work up, have them start on, you know, really menial stuff.

[01:10:02] **Ben:** Get the lay of the land, understand how the systems work, understand the teams. Then maybe have them build something mission critical. But like time and time again, it became kind of this running joke internally on the engineering team is you would just hire people. And on day one. Tell them, oh, by the way, you're now building this next really huge system.

[01:10:21] **Ben:** Good luck.

[01:10:22] **Tim:** Right.

[01:10:23] **Adam:** That said, like, I completely agree, but also the other side of that coin is you do want them, if possible, to deploy on day one, like something small and relatively inconsequential, but you know, get the ball rolling early, get that momentum started. I'm all for that. Cool. Well, we've been recording for a little bit over an hour.

[01:10:40] **Adam:** Does anybody have any pressing thoughts as you want to get out before we wrap up? I only

[01:10:45] **Carol:** have one thing to add. There's a book called Cracking the Coding Interview, and if you get tripped up on questions, on technical questions, Um, there's actually a GitHub repository that you can go open and it's got the answers in multiple languages.

[01:11:01] **Carol:** So you can just find it in JavaScript, like, so if you do find that you're getting tripped up on questions, go read some and then go look at how someone else solved the problem and go at it backwards and see how they solved it to figure out where you got tripped up at. Just to kind of give you a little confidence boost when you do go in and you start hearing these technical questions, you're not so kind of during the headlights.

[01:11:22] **Adam:** Yeah,

[01:11:23] **Tim:** and always do background check. Always do background check. We had 1 guy, 1 guy, we did the background, he started working and then the background check came in and then ice came and picked him up and put him in jail. But do that background check before you hire them.

[01:11:41] **Adam:** Well, uh, we don't have any new reviews, but we have been steadily climbing in ratings, so thank you guys for that.

[01:11:48] **Adam:** And it looks like all of our ratings so far have been five stars, so thank you doubly for that. Heck yeah. Hey! What? No haters. No haters. Sorry, Tim. If you think we've earned it, please consider supporting us on Patreon. You can find us there at patreon.com/WorkingCodePod. We've got a bunch of people supporting us on Patreon and we want to say thank you to all of them.

[01:12:08] **Adam:** And our new patron this week is Chuck, who I don't know if you guys know, is my former boss from a long time ago that I talk about. Like, I go have lunch with him and still consider him a friend and a mentor. Uh, so, hey Chuck, I know you're out there listening and thank you. What up, Chuck? Thank you! Yay! We also have what we call our top tier on Patreon for people who want to pay a little bit extra for some reason and in exchange they get what we're going to call a sponsored shout out.

[01:12:33] **Adam:** So if you've been listening for the last few weeks then you probably remember who our top supporter is and we have to say this whole pivot to Sponsored shoutouts was his idea. So thank you, person who wanted to pay extra and also pay that spotlight forward. You know who you are and you're a legend. So this week's sponsored shout out is going to go to GirlsWhoCode, which is at GirlsWhoCode.

[01:12:53] **Adam:** com. And we know that that is a cause near and dear to the heart of our very own Carol Hamilton.

[01:13:00] **Carol:** Yes, yes, definitely go support them. Um, 1 thing that people don't realize is how I mean, probably people do realize this. How few female engineers there are out there in my department. I went and looked the other day.

[01:13:14] **Carol:** There's 75 engineers and there are 7 females. So, if you have the time, you know, you can volunteer with them. Or, you know, your company can sponsor or you can go, you know, donate some because diversity brings good solutions. So bringing females into the industry is just going to help us grow the industry further.

[01:13:34] **Carol:** So go

[01:13:35] **Adam:** support. And, and like you do, Carol, there's opportunities to volunteer too. So you don't have to just support with

[01:13:41] **Carol:** money. Absolutely. Yeah, go, um, just reach out to local chapters. Um, you can donate hardware if you don't want to go teach in the classroom or you don't want to go help. You can, um, like I said, donate hardware.

[01:13:53] **Carol:** You can sponsor trips. You, there's lots of things you can do with them. Awesome. They like food too. Yeah.

[01:13:59] **Adam:** That's great. So each tier on our Patreon has different perks like a lifetime invite to our Discord server, early access to new episodes, and our after show where we keep the microphones running for another 10 to 15 minutes after the show ends.

[01:14:12] **Adam:** And even if that's not your thing, thank you for listening. There's no podcast without listeners. So don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:14:26] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod. We'll catch you next week. And until then, your heart matters.

[01:14:53] **Tim:** So every time I hear you say the booster signal, I think about fire, the Firefly movie, the Serendipity movie, uh, Serenity, Serenity, Serenity. Yeah. At the very end, the guy's dying. Can't stop the signal!

[01:15:05] **Adam:** Such a good show. I, I think I heard somewhere that they're trying to bring that back? They tried, like, reboot it?

[01:15:10] **Adam:** Yeah, they're gonna re, yeah,

[01:15:11] **Tim:** reboot it, yeah. Nice. Or not reboot it, kind of like restart it, because it would be like some, some of the same cast, like, um. Okay. Nathan Fillion and What's the redheaded guy's name? Wash. He's dead. The actor? The actor's not dead, but his

[01:15:23] **Adam:** character died. Okay, I was gonna say, yeah.

[01:15:26] **Adam:** Spoiler

[01:15:26] **Tim:** alert. Sorry. How do you, how do you clean your spears? Run them through the wash. You only get that if you watch the movie.

[01:15:34] **Adam:** Yeah, yeah. I

[01:15:35] **Carol:** assume you got speared to

[01:15:36] **Adam:** death. At this point, it's only been like 20 years, so there's no excuse.
