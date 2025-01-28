---
title: "027: Giving Technical Presentations"
description: "Part deep-dive, part story telling, a compelling technical presentation has to present enough information on a topic so as to deliver meaningful take-aways while, at the same time, keeping the information light enough so as not to overwhelm the audience. This week, the crew discusses presentations that they've given. And, shares tips and tricks for making your presentation a real winner!"
date: 2021-06-16
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/027-giving-technical-presentations/id1544142288?i=1000525722431"></iframe>

As [Jerry Seinfeld joked][seinfeld-joke], when it comes to funerals, most people would rather be the one in the casket than the one giving the eulogy. Because, public speaking isn't easy. And, for many, it's a source of great anxiety. A technical presentation takes that anxiety and compounds it by layering on a need to provide complicated information in an engaging way. Part deep-dive, part story telling, a compelling technical presentation has to present enough information on a topic so as to deliver meaningful take-aways while, at the same time, keeping the information light enough so as not to overwhelm the audience. This week, the crew discusses presentations that they've given. And, shares tips and tricks for making your presentation a real winner!

## Triumphs &amp; Failures

- **Adam's Triumph** - Adam was keen to get into testing as a life-style. And, by golly, he's done it! His current project has 100% passing tests with 95% test coverage! He's also been writing blog posts on the topic of testing in order to help keep this momentum going.
- **Ben's Triumph** - It doesn't necessarily _feel like a "triumph"_ in the moment; but, Ben is excited to be giving his first tech presentation in maybe a decade. He has a lot of social anxiety. But, he wants to feel more connected to the larger programming community and he thinks that giving a presentation will help take him a step in that direction.
- **Carol's Triumph** - _Carol is winning life!_ She was selected to run in the Peach Tree Road Race and she's super excited to crush her previous race times! Go Carol!
- **Tim's Failure** - Tim is struggling to bring operational readiness and predictable performance to a legacy system whose architecture and behavior seem to defy reason. He's at the point where a "big bang" rewrite feels like the most viable path forward. This is generally considered a taboo move in the tech industry; but, he's not sure how else he can stabilize the product and provide a good Service Level Agreement (SLA) to his customers.

## Notes &amp; Links

- [Patrick Winston: How to Speak](https://www.youtube.com/watch?v=Unzc731iCUY) - this talk, 40-years in the making, is intended to improve your speaking ability in critical situations by teaching you a few heuristic rules.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[seinfeld-joke]: https://www.goodreads.com/quotes/170523-a-recent-survey-stated-that-the-average-person-s-greatest-fear
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/027-giving-technical-presentations.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I have two, two, uh, presentation routines. One is I go get my fear poop out of the way. Oh, man. Wow. And, and two is I remind myself that the adrenaline that I'm feeling is there so that if I see a lion coming, I can run faster than the other people in the room, right?

[00:00:36] **Adam:** It is show number 27 for June the 16th and on today's show we're going to be talking about giving technical presentations and as usual we're going to start with our triumphs and fails and this week it's my turn to go first so I'm going to swing it back around and I'm going to the triumph this week.

[00:00:50] **Adam:** Last week I talked about how I had started getting, I, yeah, I did. I, I used that exact phrase. I said I was starting to get started doing TDD, uh, and it wasn't going well. Um, well, the pendulum has started to swing back in the other direction. Uh, I wouldn't say that I'm fast, but I am doing fine. I'm kind of killing it with this project that I've been working on.

[00:01:11] **Adam:** Uh, I have 100% passing tests right now with 95% code coverage and I am just feeling great. So, I mean, it's, hey, every day is frustrating because I'm learning as I'm going, and... Um, you know, there are, it's fits and starts, right? Everything's going great for an hour. And then I spend three hours stuck on something and it was great for two hours.

[00:01:31] **Adam:** All right. So that's me. Uh, Tim, what do you got? Uh oh.

[00:01:38] **Carol:** That sounds pretty. It sounds like you just won

[00:01:40] **Adam:** something.

[00:01:41] **Tim:** No, today sucked. Oh my God. Today sucked so bad. The week was, so we have a legacy system that's just been around like 10 years. And every time you reboot it, the system, it does weird stuff.

[00:02:02] **Carol:** That's

[00:02:03] **Adam:** not a good

[00:02:03] **Tim:** thing.

[00:02:03] **Tim:** No, it's not a good thing. And it's like, it's just, and it's only for one customer. So we have. Lots of customers, but for some reason, people before me decided to create this one off thing for this one customer. And all it does is it just, it batches payments and makes the, I mean, it's not hard what it's doing, but it's weird.

[00:02:24] **Tim:** So it, it's all asynchronous and it like. Jobs, aren't you? They reboot it. Jobs won't fire and then sometimes all the jobs will fire at once. and yeah, it was, so they're dealing with like life insurance payments and most of their people are older, so most of their payments are made on the third when their, you know, social, social security check comes in and um, yeah, so today just sucked really bad 'cause.

[00:02:51] **Tim:** rebooted this thing. It just, it didn't work.

[00:02:53] **Carol:** Oh, that's why it was bad. Cause there was a reboot that happened.

[00:02:57] **Adam:** Yeah.

[00:02:57] **Tim:** The reboot happened. It's on a limited, I don't know, the CRON jobs don't work. I don't, I don't know. And so it's like, I've been wanting to rebuild and refactor and just. And that's it. That's all I have to say.

[00:03:11] **Tim:** I hope you enjoyed this video. If you do, please give it a thumbs up. If you want to see more videos like this,

[00:03:17] **Carol:** please subscribe to our channel. And if you're new to the channel, please hit the bell icon so you don't miss out on

[00:03:23] **Adam:** any

[00:03:24] **Tim:** future videos. We will see you next time. So someone at some point in time told them they can't send a batch of payments more than 26 at a time.

[00:03:35] **Tim:** I have no idea where that

[00:03:36] **Adam:** number came from.

[00:03:37] **Carol:** See, any number that's not like a nice even number, you think someone actually thought about it. So then they're like, okay, 26

[00:03:44] **Adam:** is accurate. Yeah, just send us 26. It would say 26. Yeah, I don't know.

[00:03:47] **Tim:** So their biggest concern is we would really like, earlier in the year, I had a meeting that like, we'd really like to like make it so they could just send you the entire batch at once and you just process the payments.

[00:03:57] **Tim:** I'm like, yeah, cool. We can do that this year. But it's like, they're, they're a good customer, but they're not like the top 10, right? So it's like, I haven't made time for it, but it's like, now it's like, all right, I'm making time for this. But now they're

[00:04:08] costing

[00:04:09] **Carol:** you money though, by being down and not working.

[00:04:11] **Carol:** They're

[00:04:12] **Adam:** costing me time.

[00:04:13] **Tim:** Yeah. Time is money. I'm spending, yeah, I've spent the last three days like worrying about this. So I'm definitely, I have a meeting with them to where I'm like, I need to understand, we send them stuff. I need to understand what they get and do with that stuff when we send it to them.

[00:04:27] **Tim:** And after that, I'm just going to just rebuild the whole thing. I honestly don't think rebuilding it will take long. Um, probably like two, three days total. Um, I just need to understand. Each part of the process that they're on. So it's like, today was just awful. 'cause that's the only thing I worked on.

[00:04:45] **Tim:** It's like there's so many other things I need to be doing. Mm-hmm. ,

[00:04:49] **Carol:** somebody please send hugs to Tim. He needs hugs. Thank you.

[00:04:53] **Adam:** He needs hates. Yeah.

[00:04:54] **Tim:** No. Yeah. I'll take haters. I'll tell totally. Adam, I'm good.

[00:04:59] **Adam:** So, so going back to the idea of people like teaching random things and they just kind of get stuck in the, the, the user base for no reason at all.

[00:05:09] **Adam:** I worked at a company that it was common to do, like paging over the, the entire, uh, campus, like intercom sort of thing, right? You know, like, Adam, please come to you, call. Yeah, yeah. Or come, come to the front office, or you have a call online, whatever. Yeah. Sort of thing. But the person who installed the phone system and like hooked it up to do this.

[00:05:26] **Adam:** liked the sound of somebody pressing a button after it had like started the recording of what they were going to say. So he, he, you know, it was like, you, it was like press, you know, pound 33 to, to make a broadcast announcement, but he would teach them pound 33 pound. So that, that pound ended up in the recording because he liked the sound of that tone as part of the message.

[00:05:47] **Adam:** And I could not train people not to do it. It drove me so bananas.

[00:05:52] **Carol:** You know, that doesn't have to be there.

[00:05:54] **Adam:** I get it. Going back to my like type A personality that if there's a right way to do it, do it the right way. Yeah. Last week's episode.

[00:06:02] **Tim:** So yeah, that's me. How about you, Carol?

[00:06:06] **Carol:** Yeah, I'm, uh, well, I'm sorry.

[00:06:08] **Carol:** Your day suck, but I'm winning over here. You know, you can come enjoy my triumphs with me. All right. Um, so I got selected to race the Peachtree Road Race, so July 4th. I will be competing with a whole bunch of people in a 10 K through Atlanta. So I'm super excited because not only did I get in it, I'm also in the second heat in the morning.

[00:06:30] **Carol:** So I will be out early and done early and hopefully some of the faster sets and faster results. So I'm super excited. So now to get out and. Make sure I get that time, you know, shortened up a little bit and get my legs broken in. How

[00:06:46] **Adam:** do you get selected for something like that? So,

[00:06:48] **Carol:** I had to submit my race results.

[00:06:50] **Carol:** So, I had to submit times and then they do like lotteries and then there's a couple different ways. Um, I'm not really for sure what. Criteria got me into it, but I ended up getting, getting a spot. So I was super excited. The, there's two days of it. There's the July 3rd day and July 4th is actually like the big day.

[00:07:09] **Carol:** So I'm super excited. I'm on the July 4th race, so.

[00:07:13] **Tim:** I'll look for you on the local

[00:07:14] **Adam:** news.

[00:07:15] **Carol:** Yeah, right. So that's me. Yay. I'm gonna go run. All right. How

[00:07:19] **Adam:** about you, Ben?

[00:07:20] **Ben:** I'm gonna go with a triumph this week, although it doesn't necessarily feel like a triumph emotionally, but I have agreed to do a presentation at the upcoming Adobe developer week.

[00:07:32] **Ben:** Yeah, I don't give a lot of presentations. Mostly I just sit in my office all day every day. And, uh, but I'll tell you being on this podcast and talking to you and, uh, I've been feeling more connected to my people. Good. Me like, conversely, made me feel less connected to a lot of other people. And I, and I feel like stepping out of my comfort zone and giving a presentation, uh, will help me get back into that, uh, feeling of connectedness with the, with the broader community.

[00:08:05] **Ben:** But, uh, you know, I think you guys have actually really inspired me and made me want to put myself out there. That's cool. I'm excited about

[00:08:11] **Adam:** that. That's awesome. I'm stressed as heck.

[00:08:15] **Tim:** And, uh,

[00:08:16] **Ben:** overwhelmed, but, uh, but I, but I think it'll be

[00:08:19] **Adam:** okay. That's your body preparing you like that adrenaline, uh, that fear that's your body helping you be prepared to do a good job, right?

[00:08:27] **Adam:** That, that adrenaline, that's what I tell myself before I go on stage. Right. And this is kind of getting into our topic for the day is like. Um, you know, giving presentations, I think a lot of people feel that, that fear of public speaking and that they get that adrenaline rush, especially right before they go on stage.

[00:08:42] **Adam:** Me personally, I have two, two, uh, pre presentation routines. One is I go get my fear poop out of the way.

[00:08:54] **Adam:** Wow. And, and two is I remind myself that the adrenaline that I'm feeling is there so that if I see a lion coming, I can run faster than the other people in the room. Right. And, and I mean, that's both literal and metaphorical because that's, that's, you know, where that evolutionary thing comes from. Right.

[00:09:12] **Adam:** It's like when your senses are heightened, you're able to perform better. And that's what that adrenaline is all about, right? It's, it's heightening your senses and making you more aware of how often you say, um, and. Um,

[00:09:28] **Adam:** and, uh, and just seeing, you know, and sort of time slows down for you. So you feel like you're taking a long time speaking. That's whatever. Yeah. Now,

[00:09:36] **Tim:** Ben, you, you've spoken before, right? I, I, that many years ago. So I'm pretty sure I saw you present, I think it was a CF United. I think they've all been at CF United.

[00:09:48] **Tim:** Yeah. Yeah. And I was super impressed. I mean, I was seriously super impressed. And I never would have imagined a million years that you have. The, uh, the anxiety. So

[00:10:02] **Ben:** anxious.

[00:10:04] **Carol:** Was this the like love story when y'all talk about all the time?

[00:10:09] **Adam:** That was a lightning talk. Yeah, that was a, I think that was a dev objective.

[00:10:12] **Tim:** That was the objective. Yeah. All right. But he did, he did a technical presentation, I think, in. Something like that.

[00:10:19] **Ben:** Oh man. Custom tags. Yeah. Custom

[00:10:21] **Tim:** tags. Yeah. Yeah. Yeah. Um, I was like, dude, this guy's awesome. I, I, cause I, and I read your blog. You were at that point in my life, you were like my hero because everything, everything I Googled was like, you know, yeah, Bindadell, Bindadell.

[00:10:34] **Tim:** Everything I found was Bindadell and, and you got up there and like gave an awesome presentation. Then I got to know you. I didn't really get to meet you that year. I got to hang out with you. And I was like, wow, he's really. Kind of insecure. He's a

[00:10:49] **Adam:** human like me.

[00:10:51] **Ben:** I, I, um, I think part of it, I mean, obviously I have some social anxiety.

[00:10:56] **Ben:** Uh, I don't think I have like an extreme social anxiety, but I have, I, I'm much more comfortable in smaller groups, but I also, when I think about my technical abilities, I feel like I tend to focus on very low level things like. Here's what this six lines of code is doing, and it solves this very particular problem.

[00:11:16] **Ben:** And I feel like when people give presentations, they tend to be telling a story and, and here's a, you know, meta set of problems and here's how it fits together. And, and here's how it, uh, you know, pertains to you at your job. And I've never felt like I had the ability to like formulate those level of thoughts.

[00:11:38] **Ben:** Um, so my presentation is going to be on feature flags and I, and I feel like feature flags is one of the first things in a really long time where I have, I think maybe just because I've experienced it from, from nothing to how I view it now is like this revolutionary idea that I can tell that story at least.

[00:11:59] **Ben:** Whereas most of the time I just don't have, I don't have that. Uh, I don't have that narrative kind of on

[00:12:06] **Tim:** hand. So

[00:12:10] **Adam:** you're

[00:12:10] **Carol:** not speaking specifically about anything Adobe related. You are actually doing just kind of the overall, this is how feature flags work or

[00:12:19] **Adam:** how is that going?

[00:12:20] **Ben:** Yeah. I mean, so it'll be about feature flags, but then hopefully with ColdFusion

[00:12:25] **Tim:** based Samples.

[00:12:27] **Adam:** Okay. I gotcha. To show how

[00:12:28] **Tim:** implementation. Yeah. Yeah. Okay. Yeah. You know, I do, I do think that, so how much you could learn in a one hour presentation typically is very high level. Oh yeah. Yeah. I agree with you there that. If you're a very detail level oriented person, there is a struggle there to, to like kind of raise that up.

[00:12:53] **Tim:** You know, if, if what you're really interested in is the low level stuff, you got to bring it up there because you're not going to be able to get to that in one hour. Yeah.

[00:13:01] **Adam:** You need like

[00:13:01] **Carol:** a workshop to get that

[00:13:03] **Adam:** going. So you said something about like telling a story and I have to say the times that I have felt most at comfort.

[00:13:11] **Adam:** Or at ease on stage giving a presentation is when I was telling a story because having that sort of mental timeline of the story that I'm telling. These are the high notes that I need to make sure that I hit and this is where I'm going and having just some details to fill in in between helps keep me like.

[00:13:29] **Adam:** On track. Mm-hmm. and know where I'm going. So I say, um, less and I, Hmm,

[00:13:38] **Carol:** you just switched it to, um, from, um,

[00:13:40] **Adam:** yeah, yeah, yeah. That was on, on purpose, I see. Now you got me all flustered. I, having the story helps me. Uh, know where I'm going and, and just have a plan and help me feel at ease telling that story because it's something that I know.

[00:13:58] **Adam:** Plus there's

[00:13:58] **Carol:** like this personal connection to it as well that helps keep you on track where when you're just talking straight up tech and I'm just talking about how technology works and there's no real relation to how it's been implemented or how it functions and what I'm doing every day. It's a lot less connected, so I can stray off a lot easier.

[00:14:18] **Carol:** So when I do have that personal connection to it, it's kind of like, okay, here's the flow of it. Here's how it was. And that, that does kind of track along easier.

[00:14:26] **Adam:** I can remember one presentation that I gave that I very artificially put in a story, but it worked really well, which was like, I gave a presentation about not sending error, like exception logs over email.

[00:14:38] **Adam:** And, um, the, the story that I put in was like, I took some pictures of my son and like said that, you know, this is Dylan and this is his inbox. And I had like a screenshot of Gmail that I had like artificially inflated to have thousands of unread emails in the inbox sort of thing. Um, and, and, you know, I sort of unfolded the story of like how using these tools for exception logging can, um, save your inbox and give you useful data to, you know, be able to debug your app in a useful way, I guess, you know, whatever it is, just how they can be helpful to you and how, like, at the end, it kind of all unfolds with him, you know, being Um, Awesome.

[00:15:17] **Adam:** And you know, he's got like a bunch of smashed soda cans on his little desk that we put out in the backyard and he's wearing sunglasses and leaning back with his feet up on the desk. And he's got my laptop there. It was cool. Cause it like, I think it made, it was an element of, um, levity, right. It was something cute and fun, but it also helped like tell the story, like the purpose of this presentation is to help you be a better developer and help you be more relaxed at work and that sort of thing.

[00:15:45] **Tim:** So Ben, let me ask you, so When I give presentations, I try to come up with at least one or two takeaways. How do you come up with yours?

[00:15:54] **Ben:** Well, I think, I mean, not to give away the presentation here, obviously. I

[00:15:59] **Adam:** mean, duh. Ben is very anti feature flags. Uh, duh. You guys are about to find out. The, the,

[00:16:05] **Ben:** the criticality with feature flags is the separation between the deployment of code and the release of the feature that those.

[00:16:13] **Ben:** Represent that code represents and when you can create this bifurcation in, in what it means to put code into a production server, then you enable a whole bunch of other things. And that's, I mean, I'm not to iterate over those today, but, but, uh, I think the power comes from that separation and then what that separation enables you to do.

[00:16:42] **Tim:** And the reason I asked that is because it's like, that's the thing I look for when I, when I do a presentation is what's the hook, right? What's, what's the one or two things I want them to take away and go back to work and say, I heard this talk and they talked about this and I think this is awesome. And because, I mean, you sit through, if it's an eight hour, I don't know how long with the Adobe.

[00:17:06] **Tim:** is, but um, you sit through a bunch of presentations, it's like you maybe will take one or two things away from Right. Each presentation. Right. So you really have to decide what is the one thing that you want them to, to take home. Mm-hmm. Yeah. And so, and you have to drive their home. And that's, and that is a skill that, that's hard.

[00:17:27] **Ben:** I, no, this is a, it's, it's good to frame it that way. 'cause I think that'll help me. Put my slides together because I can think in terms of creating that sort of an outcome.

[00:17:37] **Carol:** You don't want to overload because then it's just kind of a lot of information all at once from a lot of different places. And you're like, man, I want to take it all in.

[00:17:47] **Carol:** But after lunch, I'm like, I'm done. Like my brain's. So full of stuff I've just taken that I didn't know about that I can't really consume much more.

[00:17:57] **Adam:** I

[00:17:57] **Tim:** think some of the most successful presentations I've seen talk about a problem. They talk about the options to the problem. They talk about what they tried with the problem.

[00:18:10] **Tim:** They talk about what failed with the problem and they talk about what succeeded with the problem. And so just having that kind of, and that in itself is kind of like what Adam said, a story, right? It's a story of, look, here's what we faced, here's what we thought about, here's what we chose, here's what happened.

[00:18:29] **Tim:** And Here's the results. Um, that story in itself is in our, I mean, I know you, you came to my, um, database source control talk years

[00:18:41] **Ben:** ago out of your time.

[00:18:43] **Tim:** Yeah, totally, totally, totally ahead of my time. But I mean, and, uh, I wasn't giving that talk as an expert. I was giving that talk as an explorer, right? So I think a lot of times we think that when I'm giving it, I'm giving a talk, I'm the expert, right?

[00:18:59] **Tim:** And that if someone is smarter than me in the audience, they can stand up and like prove me a fraud. I don't ever approach a presentation that way. I approach it as it's a conversation with the audience and here's what I'm going through. Here's what I tried. Here's what worked. Here's what didn't work.

[00:19:19] **Tim:** What do you guys think? And some of the best talks I've ever given, I've just kind of walked around the audience and just. Got feedback from them. And it was more like a conversation than a presentation. If it, you know, you're in a room, well, you're doing it virtually virtual. So

[00:19:35] **Adam:** virtual, you're in a virtual room, it's all the same.

[00:19:37] **Adam:** Yeah. You're in a virtual

[00:19:37] **Tim:** room, but they can ask questions. Yeah. So, uh, yeah, so think of it less as a. An adversarial

[00:19:47] **Adam:** thing. And nobody's going to stand up and be like, this guy sucks. Yeah, right.

[00:19:51] **Carol:** Well, I mean, unless you have like Dave Ferguson or like one of your friends sitting in the front row heckling you, then you're

[00:19:57] **Adam:** fine.

[00:19:58] **Adam:** I mean, they're not going to heckle you.

[00:20:00] **Ben:** No, this is all really good. I think, uh, I'm, I'm, I've started my slides. So my. Methodology for putting a presentation together, which, you know, I do once a decade, so it's not very finely tuned. is, uh, I will just in a notepad, you know, like a text file. Yeah. I'll just write down anything that comes to my mind about that topic that I think might be interesting, like not in any particular order or of any particular level of importance.

[00:20:28] **Ben:** And then I sort of look at all of that. And I start to formulate higher level thoughts and maybe think about things that I might want to talk about first, or how do you frame it and then lower level things. And then I started to just siphon that off into slides, trying to, trying to tell some sort of a story to Adam's point.

[00:20:47] **Ben:** And we'll see, we'll see how it works

[00:20:49] **Carol:** out. Yeah. And I tried making it so that my slides, when I send them out, so like people have them after, right. That. They're relatable, that they're able to take what I've created and actually use that. And they're not just slides that make no sense to someone. So they actually are able to go, okay, I can actually remember what was going on here based off what's happening and actually use this to build something going forward.

[00:21:11] **Ben:** That's actually like one of the funniest things I'll see after. And then I'll see someone post, like, Oh, here's my, uh, slides, my presentation. And it's just like 10 different photos of waterfalls. And I'm like, well,

[00:21:23] **Adam:** that didn't help.

[00:21:24] **Carol:** That's not relatable. Like I need this actually be kind of, you know, my little handbook to it.

[00:21:29] **Adam:** Yeah. And so kind of what Tim was talking about, where you kind of tell that story of, of solving a problem. I think that's a really. Good style of presentation, but it's obviously not the only way to do one. And I think that the ones he said that those were the ones that he's had a lot of success with or been, uh, most impressed with for me, I think the ones that, um, stick with me that live in my brain, rent free.

[00:21:54] **Adam:** Are the ones that are super inspirational. Um, and so I was trying to think about like, what makes for a really inspirational, uh, presentation. And I think that, um, it's a, it's very similar to the outline that Tim gave, but it's like an abbreviated form of that, you know, kind of tell that problem solving story, but get that done.

[00:22:14] **Adam:** If you're talking about like an hour presentation, get that done in like the first half of the presentation or less. And then the rest of it is all like. If you were to do the thing that I'm proposing you do here, like if you're, were to start using feature flags, these are the, the opportunities that then lay before you.

[00:22:31] **Adam:** And these are the things you can explore and the possibilities. For sure.

[00:22:37] **Ben:** Yeah. I like it. I mean, cause I've been using feature flags now. I work pretty heavily for about five years and there was definitely a ramp up time in terms of understanding how I even wanted to use them or how they made sense or at first they sort of just felt like a lot of more work.

[00:22:54] **Ben:** Um, which I learned over time that that was not true, but, uh, it took me a while to understand the trade offs.

[00:23:01] **Adam:** Yeah. That's the other thing is too, is like, I feel like you kind of need to do two things in that presentation as well. You need to help people understand, like help, help them recognize the challenges that they're going to face starting to, to use feature flags.

[00:23:17] **Adam:** Yeah. This is where you're likely to get stuck and how to get past that. Yeah. And then. I guess the other one would be more like, these are sort of the advanced techniques. Like once you get past that basic, okay, I have a flag, I can turn it on and turn off and I switch between SQL or whatever. Like, I don't know what that is.

[00:23:35] **Adam:** I'm not a feature flag user, but something, you know, go from 101 to the 400 level here. Yeah. So the under the cover,

[00:23:44] **Tim:** that's one thing I like. So I watched a lot of, uh, cooking videos and I hate the ones who don't show their failures.

[00:23:53] **Adam:** Yeah. they got it wrong.

[00:23:54] **Tim:** Right. Yeah. They, they worked on that recipe. Try and try and try.

[00:23:57] **Tim:** A bunch of times. Right. So, so I, I think being honest about your failures and say, look, we tried this. It didn't work. Yeah. Here's why. I think being very honest about that is extremely important in a talk because it lets people know. All right, I think a lot of times I talk, all you give is like, take feature flags, everything's shiny, everything's going to be great, and then they try it and stuff fails, they think, well, I'm a bad

[00:24:25] **Carol:** developer.

[00:24:25] **Carol:** Yeah, clearly I couldn't figure this out, so I'm just going to stop now. I'm not going to try anymore.

[00:24:30] **Adam:** Yeah, this is too

[00:24:31] **Tim:** hard. Yeah. But if you say, you know what, we tried this. And this didn't work, this didn't work, this didn't work, but then this worked. And then people are like, okay, well, if Ben struggled with this portion of it, then...

[00:24:45] **Adam:** I'm

[00:24:45] **Carol:** expected to struggle with 90% more than he did.

[00:24:48] **Adam:** Exactly right.

[00:24:50] **Ben:** This is great. I think, uh, the idea of maybe starting not lower level, but smaller scale. Yeah. Like here's the, here's the... Here's the least amount of work you can do to get some value out of this approach. And then start to talk about it and how do I now apply this in larger and larger ways?

[00:25:09] **Adam:** Yeah.

[00:25:09] **Carol:** How do I grow this now that I'm able to actually see it going, see it working?

[00:25:13] **Adam:** Yeah. I like that. And then if we're, if we're like ready to sort of move on topic wise a little bit here, um, I was thinking maybe a good thing to spend some time on would be like. What are the pitfalls of giving a technical presentation?

[00:25:27] **Adam:** What are the things that people do commonly that are terrible?

[00:25:31] **Carol:** Live coding.

[00:25:33] **Adam:** Okay. I mean, I've seen that go really well too. Like if you, if you practice it and you have it down pat and you know exactly what you're doing, and it's

[00:25:42] **Carol:** simple coding. Simple, simple. And you cannot rely on any networking. So you need to make sure that everything you're running is locally on your machine because suddenly when you can't connect to the internet and you can't get to anything because you don't have internet.

[00:25:56] **Carol:** Well, you've just wasted my hour. There's 500 people on the conference Wi Fi. Yep. So you need to make sure that if you're going to live code that you can live code with no network or you have your phone or whatever. So, yeah, live coding spelled, but just make sure it works before you do

[00:26:10] **Adam:** it. Yeah. The one I had in mind was, uh, like writing a book on every slide.

[00:26:15] **Carol:** Yeah. For sure. Yeah. That's what the comment section's for to me, like on slide decks. If you want to add something in there for the people later on, add those in like some of the comments on there so they can have it to read as like information, but don't make it so that you have it all up there. The whole time you're talking, they're just

[00:26:32] **Adam:** reading.

[00:26:33] **Adam:** So. Yeah, Keynote has a field for presenter notes underneath every slide.

[00:26:38] **Tim:** Carol, a lot of times my live coding is just videos.

[00:26:41] **Carol:** Yeah, and that's fine. I'm totally okay with that. Like, I will record to you and be like, here, this is what it looks like. I'm just going to show it to you because I ain't going to risk having to fat finger this because you know, when someone's looking over your shoulder, you get it wrong.

[00:26:54] **Carol:** It never goes right. So I'm like, I'll just do it right by myself with no one looking and you'll never know.

[00:27:00] **Adam:** One

[00:27:00] **Ben:** thing that I struggle with As a consumer of presentations, especially in a live space with a projector, is dark themes. I'm much better with black text. On a white background. And then sometimes I'll see people do live coding or, or recordings of codings and it's, and it's like that, you know, gray, blue with, with orange text and my eyesight's not terribly awesome.

[00:27:27] **Ben:** And, uh, and that can be hard to see on a projector.

[00:27:30] **Adam:** Yeah, that's a good point. Yeah. So, I mean, while we're on that theme, um, if you are going to do live coding or, or anything like that, uh, font size large enough to be able to see from the back of the room. Yeah. A thousand percent. Yes. A

[00:27:44] **Carol:** thousand percent zoomed in for Ben.

[00:27:48] **Ben:** No, no joke. So I got glasses, but I didn't get glasses until I was. In my like late 20s. And I remember distinctly being in a presentation at a conference, probably a ColdFusion conference. And I'm sitting there at the table and, and I was like in the back of the room or something. And the screen just looks so fuzzy to me.

[00:28:08] **Ben:** And I mentioned to someone else at the table next to me, I was like, what is wrong with the projector? Like I can barely make any of that text out. And the guy was like, What are you talking about? It's totally fine. And I was like, Oh, maybe I should get my eyes

[00:28:23] **Carol:** checked. I should

[00:28:23] **Adam:** probably go to the eye doctor.

[00:28:25] **Ben:** And then when I finally got glasses and they, and they put it on, it was like a whole new world opened up. You're like, Oh, edges are sharp. Look at

[00:28:33] **Adam:** that.

[00:28:35] **Carol:** I'll never forget driving to the stoplight and being like, Oh, there's only one red light, not two.

[00:28:45] **Tim:** I was going to say a little bit of humor in a presentation goes a long way. I mean, it helps. Number one, it breaks the ice for you. Yeah. Right. So if, if people laugh after you do something funny. It helps you relax and it also engages them and makes you know that they're engaged. So I think trying to add, you know, not being overly like silly, but just adding something that's humorous can be extremely helpful.

[00:29:15] **Carol:** Here, I'll give you a joke. You can tell them and it'll help get it going. Okay. You can be like, dudes, like, don't you just feel so bad for the calendar? Do you guys feel bad for the calendars? Why

[00:29:27] **Adam:** would I feel bad for the calendar, Carol? Their

[00:29:29] **Carol:** days are numbered.

[00:29:31] **Adam:** Oh, God.

[00:29:37] **Adam:** Get out. Sorry. I

[00:29:41] **Carol:** laugh way too hard at that joke every

[00:29:43] **Adam:** time I tell it. You know it's the best when you laugh at your own joke more than anyone else does. I

[00:29:49] **Carol:** laughed at it and, uh, Peyton and his girlfriend just laughed at me laughing. They didn't laugh at the joke, they laughed at me. So, anyways, yeah. There you go.

[00:29:55] **Carol:** Now you got, you got your icebreaker. I've helped you. There you go. Yeah. Yeah. But yeah, I agree with that. Something to just kind of lighten the mood a little bit because for me, like feeling tense makes it way worse. I need that moment of like clarity where it's like, okay, I can just breathe. Like the easiest presentation I ever did was with Kev McCabe in, um, Vegas.

[00:30:16] **Carol:** And we were just talking about CFBuilder and it was just It was an easy talk because he just lightens the mood with everything he does. Like he's just an easy guy to work with. So that's one of my favorite ones.

[00:30:29] **Adam:** All right. Well, I'm excited. Break a leg. Thank you. So I do have one link that I wanted to throw out there.

[00:30:36] **Adam:** Um, there is this, uh, YouTube video that I really like. It is a pretty famous It's this pretty famous talk that's given at MIT. I think it's been going like every year for 40 years. It's called How to Speak by Patrick Winston. We'll of course link it in the show notes, but it's, it's a, it's basically a presentation on how to give a presentation and it's really good.

[00:30:59] **Adam:** I mean, it's an hour long, but it's, you know, it's an MIT presentation on how to give a presentation. So, you know, it's good. Yeah.

[00:31:05] **Ben:** I'll check it out for sure.

[00:31:07] **Adam:** The

[00:31:07] **Carol:** show stuff like that during like bath time. Cause it's easy to just kind of lay and listen to him watch

[00:31:11] **Adam:** and

[00:31:12] **Tim:** relax. I love public speaking. I'm. Not that much a people person, but I do, I am a performer.

[00:31:19] **Tim:** I, I like being on stage and I just, I, yeah, so I, I know that's kind of the opposite of you, Ben . So I took, and I don't mean that in a bad way. I mean, no, no, you, you are, I'm not a blogger. I'm not a researcher. You're, I think if you, like, you, you have a beautiful way with words. Who delves in deep and like puts his thought out and perfectly, you know, I have to wing it, right.

[00:31:43] **Tim:** I have to get up there and just kind of like showboat. And so, yeah, I totally admire that you are putting yourself out there to give a talk because I know it's not your comfort zone. But you have so much to give.

[00:31:56] **Ben:** Well, it's very nice of you. Thank you.

[00:31:58] **Carol:** I've realized I'm not a big fan of public speaking, but I am totally a fan of organizing it all.

[00:32:04] **Carol:** Like I had a ton of fun organizing the conferences, like helping people come up with topics. Like you have people who want to present. But aren't really sure on topics or you're not fond of their topics. So then you help them come up with other ideas and suggestions. That's all great to me. And then I'll go and listen and enjoy all of it.

[00:32:23] **Carol:** But I definitely prefer that side of it over the actual speaking at it.

[00:32:30] **Tim:** Yeah, most people would rather, uh, so people's fear of public speaking is greater than fear of death. So, the person giving the eulogy is more scared than the person who's dead.

[00:32:41] **Adam:** Well, of course they're more scared. Can't be scared when they're dead.

[00:32:45] **Carol:** All right, we round it out.

[00:32:46] **Adam:** Sure. Let's do this. So this podcast is made possible by the Corporation for Public Mayhem and listeners like you. I'm going to keep the pitch short and sweet this week. Just like last week. You're smart people. You know how this works. We could really use your support. And if that's something you're interested in, you can find us on patreon.com/WorkingCodePod. We have a top tier on Patreon and we have two top patrons right now, so a special thank you goes out to Peter and Monte. Thank you guys very much. To everyone that just listens to the show, thank you for listening. Please share the show with your friends and co workers because there's no better support than a word of mouth referral.

[00:33:21] **Adam:** Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts. Send us your questions and topic suggestions on Twitter or Instagram at @WorkingCodePod. Or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until then,

[00:33:42] **Tim:** your heart matters guys, particularly if you speak at conferences.
