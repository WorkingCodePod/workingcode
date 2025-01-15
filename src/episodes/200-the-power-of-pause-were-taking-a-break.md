---
title: "200: The Power of Pause - We're Taking a Break"
description: "In this special episode, we celebrate reaching our 200th show by discussing the critical importance of taking breaks and avoiding burnout."
date: 2024-10-30
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/200-the-power-of-pause-were-taking-a-break/id1544142288?i=1000675032653"></iframe>

In this special episode, we celebrate reaching our 200th show by discussing the critical importance of taking breaks and avoiding burnout.

We share our thoughts on mini-retirements, the differences between sabbaticals and mini-retirements, and the surprising benefits of doing 'drudgery' work. We also delve into the upcoming hiatus for the podcast and what each of us plans to do with our extra free time.

Join us for a candid and insightful discussion on how stepping away can actually help you come back stronger and more motivated.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/200-the-power-of-pause-were-taking-a-break.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** You could also just try,

[00:00:01] **Ben:** quiet quitting for a couple of weeks every year, just,

[00:00:04] **Tim:** Just sit on the bed, only answer emails like, like two days later. Oh, wait, you already do that.

## [00:00:32] Intro

[00:00:32] **Adam:** Okay, here we go. It is show number 200. And on today's show we are going to talk about the importance of taking breaks for no particular reason at all.and, we got everybody on the show. Again. Glad to see you all. and

[00:00:44] **Tim:** Hey, party people.

[00:00:46] **Adam:** Hey, and as usual, we'll start with our triumphs and fails. Ben, it is your turn to go first, so why don't you go first?

## [00:00:53] Ben's Triumph

[00:00:53] **Ben:** So I'm going to kick it off with a triumph and my triumph is that today, it's not really a launch per se, but a couple of months ago, I had started working on a companion piece for my feature flags book. It was a little online application where you could go in and you had some demo feature flags and you could tweak them and see how tweaking feature flag settings would affect serving of different variants to different users.

[00:01:17] **Ben:** And I'm going to go ahead and call that demo playground done as of today. over the weekend, I recorded a bunch of, video commentary about some of the key interfaces within the application so that, you know, it's one of those things where when you're building something. You immediately start to suffer from the knowledge bias, where because I built it, I know exactly how the whole interface is supposed to work and how every little part corresponds to another part in the same page.

[00:01:45] **Ben:** And I realized that not everyone coming to a page is going to have that kind of deep understanding. So I wanted to Give some perspective on how things work and handle people through some of the various workflows. So I did those recordings over the weekend and I wrote up a blog post this morning and I posted it and, you can see the code or one can see the code.

[00:02:05] **Ben:** I'm not saying you guys should go see the code, but one could go see the code on GitHub. The whole playground is, available on GitHub, but I just run it locally in Docker. Anyway, I'm just feeling, I'm feeling good about it. I took it as an opportunity to really try some experimental changes in the way I put an application together.

[00:02:24] **Ben:** And, I'm liking the direction that it's going. So just overall, I feel like it was a learning opportunity. I feel like it's actually a helpful piece of information for people. And I feel like it's a nice companion piece to the book. So it's a. It just feels like wins on top of wins there.

[00:02:40] **Adam:** Yeah, congrats, man. I bet it feels good to, like, call something done.

[00:02:44] **Ben:** Yeah,

[00:02:44] **Adam:** so much in our lives. Yeah.

[00:02:47] **Ben:** you know, I don't know if everyone else experiences this. I think this is probably pretty common. You start a project and you're pretty excited about it and then it ends up being more complicated and it takes longer than you realized it was going to take. So you get into that dip where you feel like, I just want this to be over so bad.

[00:03:03] **Ben:** I don't even care about it anymore. And I kind of got there. I don't know, I'd say like a month ago, I was kind of in that dippy zone, but then I feel, I felt like I started to come out of it as I started to have some additional ideas on ways I could bring clarity into the application and some little tweaks that I think actually added a lot of value and I started to see the light at the end of the tunnel and I was able to get through that dip and, and just muscle through it and, and I'm just, I'm, I'm pretty pleased with the outcome actually.

[00:03:31] **Carol:** Cool, and you're going to send us out a link to that because I am finally starting to get movement on being allowed to implement. And hopefully we'll be able to use LaunchDarkly, you know, some fingers crossed here, everything will get signed off on. And uh,it'd be great if I could do some training with what you've created.

[00:03:51] **Ben:** Yo, heck yeah. Feature flags are awesome. And LaunchDarkly is a super awesome application. I sort of thought of this whole thing, almost like a. Love letter to both Feature Flag generically and LaunchDarkly very specifically, and as I was putting the playground together, I also was thinking of ways that LaunchDarkly could maybe improve.

[00:04:15] **Ben:** I mean, that's like super crazy for me to say, Oh, you know, here's me as an individual saying this massively successful company, but, it's, it was just interesting, like it gave me a different perspective because I was Both about how to build it, but then also how it could be used. And it made me think about the whole interaction model a little bit differently and, and, and there's some things that maybe I feel like could be improved in LaunchDarkly, but it's, it's such an amazing product.

[00:04:39] **Ben:** I'm not trying to throw any shade at it whatsoever.

[00:04:42] **Tim:** So, so educate me, Ben, when you say playground, is that just sort of like a, like a learning tool for feature flags?

[00:04:49] **Ben:** exactly. Basically, if I can give you the quick rundown, When you log in and, but I, when I say log in, you just give your email address. And the only way I use my email address is to, is to generate some sample data for you. Basically, I give you a list of, I don't know, maybe like 10 or 12, sample feature flags, and then I generate about 106 sample users.

[00:05:11] **Ben:** And you can start to tweak the configuration and the feature flags. And you can see across those 106 users in two different environments, the development environment and the production environment, how they can start to get different variants within the feature flags being served up to them. So you can.

[00:05:27] **Ben:** Start to think about how can I incrementally roll a feature out in a production context, and you can actually see the different variants being served to people based on your, on your settings. And,

[00:05:39] **Tim:** Okay.

[00:05:39] **Ben:** so yeah, it's, it's all, and then you can delete all the data. You can reset it. I mean, there's, it's, it's not a very large application, but it just took me a really long time to actually put together.

[00:05:49] **Tim:** Yeah.

[00:05:50] **Ben:** Cause. You know, you can't just build it. You got to build it and play around with different things and experiment and, and gold plate. And there are lilies that need to be gilded sometimes. And, I did some gilding. So yeah, so that's me. Felt like a good triumph. Carol, what do you got going on?

## [00:06:10] Carol's Triumph

[00:06:10] **Carol:** Yeah, I'm gonna follow you up with a triumph then, and it's a triumph that you're going to thoroughly enjoy. After talking about it for so many episodes now, I finally installed Copilot at work. Yeah, so my license got approved. I did the training. I understand how to, handle prompt engineering now and, you know, probably have my degree in it or something because all I've done is, make it write an email for me, but I'm getting there.

[00:06:37] **Carol:** I will definitely be using it for code when I start writing code again. It just happened to be that I installed it and got the approval. During our innovation sprint, so I'm not writing code right now, the, the extent I've had to actually use it on our code base is one of my developers was having an issue with some accessibility code and couldn't get the screen reader to prompt the user back when the button enabled based off like a, I think he's using jQuery.

[00:07:07] **Carol:** We were looking at SignalR, but I think he implemented it just with jQuery, just Is it there? If so, enable it back, but the screen reader couldn't get it working. Like, he couldn't figure out how to get it working with a screen reader. Sorry. And, I just did a quick prompt in Copilot and sure enough, it spit out exactly what we had to add.

[00:07:24] **Carol:** You know, added the one little div to give it a message, which then we put the class on and it enables it and it reads it back. But one tip to anyone who's testing a screen reader is it is very hard to find out if your data is being read when your data is actually valid for the page. Because when it's reading the page, it goes, Hey, I'm looking for create.

[00:07:46] **Carol:** I'm looking for update. I'm looking for insert. I'm looking for this key information. And when you're hearing it, since you don't use it all the time, you're not used to, like, you don't know what to pick out from it, right? So I had him just throw my name in there like 12 times. So as soon as it enabled it, he just heard Carol, Carol, Carol, Carol, Carol.

[00:08:04] **Carol:** He's like, Hey, it works. I was like, yeah, I was like, don't forget to take my name out though.

[00:08:09] **Ben:** Very

[00:08:10] **Carol:** so Copilot's installed and running and I'm excited to be able to use it.

[00:08:14] **Ben:** I'm very curious to hear about your experience because I have only heard about Copilot. I have not actually tried it myself. Yeah. My, extent of AI integration is still just having a chat GPT browser tab open and going in and asking it questions. So I'm, I'm very curious to hear more about the actual real time autocomplete functionality.

[00:08:38] **Adam:** have you, have you already explained this, Ben? Why are you not using it other than your curmudgeonly, attitude on life?

[00:08:46] **Ben:** I'm just, I'm in Sublime Text and, and integrating into Sublime Text, I think is not, an easy thing to

[00:08:53] **Tim:** from Notepad and FTP.

[00:08:56] **Adam:** You sure they don't have, Copilot for stone tablets or

[00:09:01] **Tim:** Yeah.

[00:09:02] **Ben:** I mean, you know, if they, so Sublime Text has really good auto complete and I, you know, it has, IntelliSense, I guess it's kind of, and it's kind of doing the same thing, right? It's, it's essentially doing token except, instead of operating on a trillion inputs, it's just operating on, on, you know, like the hundred tokens you've already written into that text file.

[00:09:25] **Ben:** But even that alone is really, really good. I find myself hitting tab quite often when I'm using Sublime Text.

[00:09:32] **Carol:** Couldn't you do that in VS Code?

[00:09:34] **Ben:** I just, I've tried, I've tried VS Code a little bit, and it feels like an uphill battle getting to the point where I feel as comfortable in Visual Studio Code as I do in Sublime Text. I feel like I was lied to. I feel like there were a ton of people who said, Oh, you can just easily switch from Sublime Text to Visual Studio Code and all of the same key bindings work.

[00:09:56] **Ben:** And it's basically the same thing, except with a whole bunch of great stuff. And I felt like none of the key bindings really work very well. and I don't think I'm doing anything crazy. It's just, they're different enough that it's a lot of friction.

[00:10:09] **Carol:** See, I use like Visual Studio and I use VS Code. So I love VS Code for like YAML files. And when I'm like looking at something that's not necessarily like specific to my project, like I enjoy it. I enjoy, if I need to parse JSON, it's going in VS Code every single time. I'm not putting that in Visual Studio.

[00:10:29] **Carol:** But I went from Sublime. To Atom, to VS Code, to Visual Studio, and now back to using VS Code and Visual Studio.

[00:10:38] **Ben:** I'll get there one day, probably.

[00:10:41] **Adam:** Maybe. We'll

[00:10:42] **Ben:** me a couple of years. Someone will have to end of life sublime text and I'll be like, all right, blindly.

[00:10:49] **Adam:** by then, VS Code will be on the way

[00:10:51] **Ben:** Yeah,

[00:10:52] **Carol:** Yeah.

[00:10:53] **Ben:** exactly. I'll be,

[00:10:54] **Adam:** That's what you're waiting for.

[00:10:55] **Ben:** late to the party. Dang.

[00:11:01] **Carol:** Well, that's me guys. what about you, Tim? What you got?

[00:11:03] **Tim:** Three for three. I got to try him for as well. Yeah.

## [00:11:08] Tim's Triumph

[00:11:08] **Tim:** So we got back from, I spent all last week in quadrants. So quadrants is, so kind of the company makeup of the company that owns us. There's CSI, which is Constellation Software Incorporated based out of Canada. And they have. So every other year we alternate between like our big portfolio.

[00:11:28] **Tim:** So it's like all the companies and we could have this huge thing somewhere. And then we kind of go to slightly smaller the next year, which is just kind of our portfolio, which we call Vincoro, which is the insurance and banking financial software. This year was Quadrants. Quadrants is the big one. And, we were in Cancun at a, All inclusive resort for a week, which everyone is like, Ooh, you're not working.

[00:11:52] **Tim:** they always say that and I always feel bad because I, I never worked so hard. And Carol knows she's been to these things. They, you know, you have a keynote at eight, between eight and eight 30 in the morning, every day. You know, we get there on Sunday and it's like Sunday, Friday, Saturday, you know, Sunday, Monday, Tuesday, Wednesday.

[00:12:09] **Tim:** Thursday, Friday, you fly out. So you're there about five days and they jam pack it full of stuff. you have to go to all these seminars and classes, and then they have like, team building things you have to do in the evening and the networking. I mean, on their, on your, on the app, they have networking to like 1130 PM.

[00:12:26] **Tim:** They expect you to be at the bar or be at the restaurant networking with the people.

[00:12:32] **Ben:** Freaking teenagers.

[00:12:33] **Tim:** Don't, don't get me wrong. Don't get me wrong. It's, it's cool to be in Cancun. It was right on the beach. It was Moon Palace Resort. The resort was huge. It was amazing. It was all inclusive. So you go to your room and the, there's a mini bar that is fully stocked and it's like, just take what you want.

[00:12:50] **Tim:** It's not like Vegas or you're paying extra, right? He's got to show up on your expense reports. Bottles of tequila, big, like big bottles of tequila, rum, whiskey, everything's like, you just, yeah, you could sauce yourself up all day long if you want. And I'm not confirming or denying if I did, but I was pretty happy most of the time.

[00:13:10] **Tim:** and like I think I had six, seven restaurants there. Like you just walk in the restaurant, show them your wristband and go eat whatever you want, order everything on the menu. That's great. Had Wagyu. I mean, so the food was fantastic, but yeah, it's super tiring. But. It was very energizing actually to be there, right?

[00:13:27] **Tim:** To just sort of recalibrate your brain, just realize what, what a really cool kind of thing we're a part of. It's like this, I don't know of any company in the world that's like this, where you've got hundreds and hundreds of just these kind of small to medium range size software companies. And even though we're all very different in like the areas that we serve, we all look very much the same, like how we drive revenue and how we basically at the end of the day create revenue.

[00:13:58] **Tim:** For CSI, for CSI or Constellation Software, to continue to buy more companies and just how that continues to, like, drive the stock price up and, and, yeah, it's, know, they make you drink the Kool Aid there and I drank the Kool Aid. I was like, yeah, this is great. Yeah. I went in feeling like, you know, it's like all you see is your own, out your own window.

[00:14:19] **Tim:** And now you start looking out and it's like, I look at some of the people that, that I've known who've kind of grown up in the organization. I'm not the kind of person, I don't want to run 500 companies. I just don't have that energy. I'm not that interested in it, but I'm definitely interested to see what people do and, you know, some of the people that have come in and that, you know, they started out with, they bought, our company and they bought, you know, another small company and now they're in charge of like 150 companies, you know, over a 15 year period.

[00:14:52] **Tim:** Right. So just a huge amount of growth. If you're, that's your life and that's what you're into. There's the sky's the limit as far as growth goes. But so it kind of reminded me that like, it's not just this little part of my world that, you know, I may be getting a little bit bored with, but there's opportunities out there if I need them.

[00:15:09] **Tim:** And that was a good reminder.and then we had a, did a thing, everything's AI nowadays. So we had an AI incubator where they had a, you had to do a pres not even a presentation, you basically came up with an AI idea. Everyone had like sort of the same info they had to supply about it. Had to either create something that saved money, save, save your company money, or could generate money.

[00:15:32] **Tim:** And they gave out like, you know, first, second, and third, first place was a 250, 000 worth of, R&amp; D money that could go if your company won that, that goes to your R&amp; D budget to spend to kind of build that idea out. And there were a hundred, I mean, each company did one and there's probably like 130 to 40, I don't know.

[00:15:54] **Tim:** It was a lot.

[00:15:55] **Ben:** Wait, how many people were there?

[00:15:58] **Tim:** a little under 2000,

[00:16:00] **Ben:** Holy cow.

[00:16:01] **Tim:** Little under 2000. And there's people from all of this, people from South Africa, Europe, Singapore, North America, South America, Australia. I mean, they're from everywhere. and, just seeing a lot of the ideas. One thing that kind of struck me is like a lot of the ideas are kind of the same.

[00:16:16] **Tim:** kind of the same ideas. My, I, you know, my thing that was presented was, you know, The thing I've talked about here in the show, we're basically have an after hours call center and it's smart enough to answer smart questions and make payments and do first notice of loss on insurance. So there's a lot of stuff like that.

[00:16:33] **Tim:** And other things like saving money, like you have a giant ticket, where the AI can summarize the information in the ticket and all the documentation that goes with it and summarize it. So you don't have to read through everything, which I thought was kind of weak. Cause I think JIRA actually does that if you pay for it.

[00:16:50] **Carol:** I think the iPhone does that currently. Yeah.

[00:16:56] **Tim:** Facebook was the very top on Facebook would be this little comment that it says people are saying that they enjoyed the witty repartee between doing so, but point out the, that this actually probably is impossible, that kind of thing, but I thought that's a pretty good thing for a ticket because a lot of times you get like, look in the ticket history, like, do I seriously have to read

[00:17:15] **Adam:** Right.

[00:17:15] **Ben:** Yeah.

[00:17:16] **Tim:** 50, 60 comments on here to figure out, The nugget of truth on this.

[00:17:21] **Ben:** One place, if I can just interject one place that they're doing that, and I find it actually very useful is in the Amazon reviews. So when you're looking at a product, right, and they have 150 reviews, they'll do that little summary where there's say, you know, users like this product because it's easy to use and it's durable and not expensive.

[00:17:39] **Adam:** The, the problem I have with that is that they are incentivized to give me misinformation there, right?

[00:17:45] **Ben:** that's true.

[00:17:46] **Tim:** Right. Amazon does, not Jira.

[00:17:49] **Adam:** right. Yeah. Yeah. So JIRA or whatever, like if it's an internal thing and you're not trying to make money specifically off of, the, the information that you're providing, right. If this is just to summarize the ticket or whatever, that's different, but you know, Amazon's, how often Ben, do you see that?

[00:18:02] **Adam:** And, you know, the summary is like, people are like, do not buy this piece of junk, you know, it's going to break five minutes after you buy it sort of thing. It's,

[00:18:11] **Tim:** One of the things that I, this wasn't even the incubator. This is one of the, there was several, so basically you build your own schedule. It's kind of like a conference that you go to where you have a schedule and like there's tons of different blocks. There was so many different things going on. And you pick the topic you want to go to.

[00:18:28] **Tim:** And one of the ones was, was the AI one AI topic and someone was showing how they at work would take the, and I got to look into this cause I don't understand how that can actually do that, but they can take like the code changes that you've done, your existing documentation, combine the code changes you just did in like shock screenshots of what you're doing.

[00:18:51] **Tim:** And then you import it into like a, text generator and it'll create a script. An AI script that explains, you know, all the stuff that happens, you know, here's, here's the changes or create the documentation. And then they were showing like, you create your own podcast. It creates two fake people that have a conversation that talk, that talk about like, so explain to me, so in this update, so what things do, oh yeah, we got so many cool things.

[00:19:18] **Tim:** And it's like these two AIs talking to each other. So we've added this new feature. This new feature is pretty awesome. And it's like, explain, I'm like, all right, I got to look into this because that looked too good to be true.

[00:19:28] **Ben:** So.

[00:19:29] **Adam:** to start a company making AI listeners that can listen to AI

[00:19:32] **Tim:** Right. Yeah. Yeah.

[00:19:34] **Ben:** you, if anyone, if any of our listeners listens to the Hard Fork podcast from the New York Times, they, a couple of episodes ago, they talked about Google Notebook, which is, is it's the service that can generate the podcast on demand from anything you upload to it. And one of the co hosts uploaded his, like bank statement and the, and the AI, the generated AI starts sort of ribbing him about how much he's spending on Ubers.

[00:20:00] **Ben:** And he should really be cutting back and being more financially responsible. But it's, it is pretty crazy that it'll, it'll make it based on anything. So it's literally a line item of expenses and they turned that into a, you know, quasi meaningful repartee about, financial literacy.

[00:20:18] **Tim:** One of them, I don't remember all the ones I haven't written down. I have to pull it up. But so one of them was, Synthesia. io, which, yeah. Have you used that?

[00:20:29] **Adam:** No.

[00:20:30] **Tim:** Synthesia. io. Yeah. Yeah. That's where you hallucinate. Like you hear, you see sounds and hear,

[00:20:36] **Adam:** Yeah. Hair colors. You

[00:20:39] **Tim:** Synthesia, which create this person who would basically talk and like sell the, like do the podcast or whatever.

[00:20:46] **Tim:** So I'll put it in the link in there. But.

[00:20:49] **Adam:** said it's synesthesia. io? Because I think, I think what you're getting to is, is actually synthesia. io. So like instead of, it's, it sounds awfully similar to synesthesia.

[00:20:59] **Tim:** close.

[00:21:00] **Adam:** But it is different.

[00:21:01] **Tim:** Yeah. You're right. You're absolutely right. So I pasted it in there. And then finally, I don't want to take up too much time, but so like the last day we played, so the day before we basically went to different, we were all forced to go to the same kind of topics and it was about pricing and, marketing and PS.

[00:21:21] **Tim:** And our professional services and a couple other things. But anyway, the next day we played, it was called the hotel management game. And we were, we were also each, we had little small teams of about five to six people, and we're all up against everyone else who's there, right? And we had to manage a hotel, so we had to bid on a hotel, we got the hotel, and then we had to like, you know, set prices, you know, figure out, you know, what we're going to pay, the employees, how many we're going to staff, and it was, you know, it was quite fun.

[00:21:53] **Tim:** We, we lost, our hotel lost 250, 000 after six quarters. They would, so there'd be each quarters and there'd be like crises that happened during each quarter, and you'd look at your bottom line each time. And, but some people actually turned a profit and they, they won prizes, which was, tequila, Petro and

[00:22:11] **Adam:** was the, what was the purpose of this exercise?

[00:22:13] **Tim:** So really just to really, I think it was more working as a team, right. And that was sort of what they were talking about. It's like, you know, in, in your companies, you need to particularly like one of the main things is listen to finance, right. So a lot of times you have people in PS are like, we're just going to build cool stuff and the bean counters can, you know, count the beans afterward.

[00:22:33] **Tim:** And it's like, in this game, it's like, if you didn't do a good analysis of the hotel and you know, the, the profit that was making, and you didn't really know where to invest. So,yeah, so the team that won actually had one first and second had two of the best. Finance people in the business on their team.

[00:22:51] **Tim:** And they figured it out. They, they figured out we were like raising prices and constantly shifting prices around, which apparently in the hotel game, that was not a good thing because they would tell you, we could, we could calculate based off of revenue, how many people. Your room occupancy. And so we started out with 66 percent and then we raised prices up and like, like 4 percent occupancy, but there were several teams that got up and said, yeah, we had like zero occupancy for, for two quarters.

[00:23:20] **Tim:** So a hotel was zero people for six months.

[00:23:23] **Adam:** Yeah.

[00:23:24] **Tim:** So, but it was lots of fun. It actually was quite fun. So I definitely want to play that again, knowing what I know now. Anyway, sorry, I took way too long, but, yeah, I was energized. Like I said,

[00:23:35] **Adam:** you are? Me?

[00:23:36] **Tim:** I'm right, right. I'm energized from Quadrant. So I was energized from it.

[00:23:39] **Tim:** So I'm ready to get back there and get in the game. So how about you, Adam? You're the

## [00:23:44] Adam's Triumph

[00:23:44] **Adam:** I'm going to, I'm going to do my best to keep it short and sweet here. I am also going to go with a triumph.

[00:23:48] **Tim:** What?

[00:23:49] **Adam:** That's right, 4 for 4 here, and, I'm gonna keep it simple. So, in the last, like, two weeks ish, I've launched two projects to production, which is cool in and of itself, but the real triumph here is the names of these projects.

[00:24:03] **Adam:** So, you know, I just, like, I was, I've gotten to a point where I'm so fed up with Inconsistent naming of things like, you know, even to the point where it's like, some of our lambda functions are Pascal case. Some of them have underscores. Some of them are, you know, with dashes in the names or whatever.

[00:24:22] **Adam:** And it's, and it's, and some of them have like IQ prefix, whether that's underscore or all caps or, you know, whatever. It's like, there's just, can we pick one standard please? And, and stick with that. And so I had these two projects that were getting close to being ready to go to production. I was like, if we're going to.

[00:24:39] **Adam:** Rename these because, you know, this was, neither of them fit any of the existing naming schemas. If we're going to rename these, At any point in their life, now is the time to do it. So like, I'm just going to take 10 minutes, call a pause, time out here, and say, let's talk about this. Let's spend 10 minutes coming up with names.

[00:24:57] **Adam:** And you know, it has to be, you know, I'm not looking for Homer Simpson as the name of a server here. I'm trying to like, I want a name that's descriptive for what it does, but like, let's try to make it fit the naming convention. And then if we can, Fit those criteria and have some fun while we're at it, even better, right?

[00:25:13] **Adam:** And so we, we spitballed a couple of names and somebody realized that we were very close to being able to use the acronym MEH. MEH for one of them,

[00:25:27] **Tim:** I'll say these are internal names.

[00:25:29] **Adam:** yeah, yeah, internal projects. and so it became a, an exercise in fun backronyms for me. So backronym is just like, you come up with the acronym first and then you sort of reverse fit it to, you know, reverse fit the name to, to create the acronym, which is like every NASA project ever, right?

[00:25:46] **Adam:** Like they come up with some, Long term so that it spells satellite or telescope, you know, like whatever.anyway, so, I

[00:25:54] **Tim:** L. Ron.

[00:25:55] **Adam:** yeah, I did, I did ultimately come up with, the, so I did rename both of these projects. The first one got named meh, so it's, the Mailgun event handler, right? So this is a project that, receives webhooks from Mailgun to tell us about delivery of messages, opens, people clicking the spam button or clicking on subscribes, all that.

[00:26:15] **Adam:** and so, that became meh. And then the other one became Meow, is, it's another Mailgun event thing. So we had like ME and, and then, and the W was kind of like one of the things we were considering and I was like, that's awfully close to Meow, like, let's just go for it. And I came up with something.

[00:26:33] **Adam:** And so, yeah, in the last couple of weeks, I've deployed Meh and Meow to production and that makes me happy. And, and they fit like, you know, clean naming schemas. Like this is, forward thinking.

[00:26:46] **Tim:** lot of onomatopoeia going on. Yeah,

[00:26:48] **Adam:** Yeah,

[00:26:48] **Adam:** And I think that, you know, if we could try to continue to, to push that pattern forward, that would make me happy.

[00:26:55] **Ben:** Meow makes me think of, the movie Super Troopers. I don't know if

[00:26:58] **Adam:** Oh, yeah.

[00:26:59] **Ben:** seen that.

[00:27:01] **Adam:** I love that

[00:27:01] **Ben:** for listeners who are not familiar, there's

[00:27:03] **Ben:** a scene where And Carol. For, there's a scene where these state troopers pull over a car and they start saying meow instead of now, when talking to the driver.

[00:27:13] **Ben:** And, you

[00:27:14] **Adam:** Oh, yeah. I mean, let's, let's be real here. The, what it was is, you know, they, the trippers were always screwing around with each other and one of them like challenges the other. He's like, you got to say meow 10 times while you're, while you're in this traffic stop. And so he's like trying to work it into the conversation as much as he possibly can.

[00:27:30] **Ben:** And I think Jim Gaffigan is the, the driver in the

[00:27:32] **Adam:** The driver he is. Yeah.

[00:27:35] **Ben:** So four wins. Amazing.

[00:27:37] **Adam:** Awesome. Cool.

## [00:27:39] We're Taking a Break

[00:27:39] **Adam:** So, I'll just say it like that's a good way for us to go out on our, on our little hiatus here. We're going to take a break, from podcasting. The tentative plan is that we are going to, after this episode is over, we're going to take a break basically through the end of calendar 2024. We're planning on coming back early in 2025, January, you know, January 1st or close to it. We're going to get our heads together and thinking about recording again. And so, knowing that we decided that the topic for this episode should be the importance of taking breaks. you know, we'll talk about what sort of stuff is motivating us, motivating us to take a break.

[00:28:18] **Adam:** And then I thought it'd be fun to talk about like what sort of stuff we're going to do on our break.

[00:28:23] **Carol:** Thanks.

[00:28:24] **Tim:** that's a good idea.

[00:28:25] **Carol:** That's great.

[00:28:26] **Adam:** So, you know, I, I think that there's some low hanging fruit here, right? Like stuff that everybody tends to already know, right? So why, why take a break? You know, obviously to prevent burnout, we've been doing this not non stop, but pretty darn close to non stop every week for 200 weeks.

[00:28:41] **Adam:** That's like four years basically. which is,

[00:28:43] **Tim:** I mean, that like next year coming up in like early March, was it March? Be five.

[00:28:49] **Adam:** yeah, something like that.

[00:28:50] **Ben:** Crazy.

[00:28:52] **Adam:** So, yeah, you know, just like taking some time to reset, right? Taking a break from things if you've been in it for too long, then, Sort of reset your creativity and your motivation, right? come back at it with fresh eyes. It's like, you know, when you've been working on a, on a debugging situation for eight straight hours, and you're like, I need to just go like take a nap and walk my dog and come back with fresh eyes and then 10 minutes back, you've got the solution, right?

[00:29:18] **Adam:** So that sort of thing. anybody else have anything you want to throw in?

[00:29:22] **Ben:** I think that makes sense. Absolutely.

[00:29:25] **Adam:** And I think another, and I think this kind of goes hand in hand with, you know, Tim's trip to Cancun, You know, taking some time, taking some,

[00:29:35] **Carol:** So

[00:29:36] **Adam:** taking some time away, and putting yourself in a fresh, situation can give you a new perspective and kind of help you, reflect and think about what you want to change moving forward.

[00:29:49] **Adam:** Cause you don't want to just stay the same. You don't want to stay stagnant. So, you know, what needs to be changed sort of thing.

[00:29:54]

## [00:29:54] Mini Retirement

[00:29:54] **Tim:** Maybe it's because I knew we'd be talking about this. We kind of planned in advance, you know, so we're gonna, cause I talked to you about, you know, maybe taking a little break a little while I was, I would, I personally was feeling burned out. and just, I keep seeing like articles being recommended to me about taking a mini retirement.

[00:30:11] **Carol:** interesting.

[00:30:12] **Tim:** Yeah.

[00:30:12] **Carol:** What is that?

[00:30:13] **Tim:** So a mini retirement is basically where you take, it's not a vacation, you take sort of an extended retirement where you just absolutely, you're not going to work either. Like maybe decide I'm going to stop a job here and I'm not going to look for a job for another two months and it's just in between.

[00:30:28] **Tim:** Say I'm, say I'm retired. Right.and, and I mean, there's some good benefits of it. It's like, you know, number one, I hate to be morbid here, but none of us know how long we're going to live.

[00:30:38] **Carol:** Right? Agree.

[00:30:40] **Tim:** None of us know how long we're going to live. I go back to my mom, who's, you know, Her health went completely south in her late sixties.

[00:30:48] **Tim:** And it's like, I'm thinking, do I really want to retire at 70? What, what if I, what if, you know, I've inherited bad health from her. And, you know, I started to crash at like late sixties. It's like all that looking forward, I don't get any of it. So, many retirements like taking a micro retirement where.

[00:31:07] **Tim:** You just, you know, you take an extended period away from work because let's be honest, I work when I'm off, right? When I'm, I'm taking vacation, I have my laptop with me. I'm constantly checking

[00:31:19] **Carol:** It's hard to detach,

[00:31:20] **Tim:** or it's hard to detach, but if, but if you're in a case where you can get away and actually not be working when you're, you know, it's not a vacation, it's actual, I'm not working for two to three months or whatever.

[00:31:32] **Tim:** I mean, you can financially do it. There's a lot of benefits from and I think it can help kind of recenter your focus. keep you from burning out, maybe help you decide, like, do I need a career change? Is this really what I want to do? Like with a lot of times, we just, we're going through the steps, the paces, and other people have told us, here's the path, here's how you move forward.

[00:31:54] **Tim:** And you're like, you believe it. And you just keep chasing the carrots, but you never seem to catch the carrot.

[00:31:59] **Adam:** Yeah,

[00:32:00] **Tim:** And so taking a mini break kind of, helps reset those expectations and see Are you really spending the Biggest limited resource in your life, which is time the best way.

[00:32:14] **Carol:** Yeah. I, I can kind of add to that a tiny little bit. You guys remember, you know, last February, I think it was last February, all the dates start running together when you've done as much as I've done over the past couple of years. like I lost a job at their capital, right? They laid off so many people and I immediately freaked out.

[00:32:30] **Carol:** I'm like, what am I going to do? What am I going to do? But then I ended up going, you know what? I know what I'm going to do. I know what I want to do. And I said, okay, I'm going to take the job with the government and I'm not going to start work until September of that year. So I took like almost seven months off total and just took my kids to Disney World.

[00:32:49] **Carol:** We moved to Arizona. Like we had some big changes going on, you know, and I was like, it actually makes complete sense to just step away from it all. And Like you said, if you financially can afford it and it's not going to, you know, hurt you in the long run or hurt your family, then I think me taking those seven months off was the best thing I could have done because when I did start back working, I, I enjoyed it, right?

[00:33:12] **Carol:** I wasn't burnt out. I wasn't stressed. And the opposite of you, Tim, I've decided I have to detach because like you said, time is the one thing I can't get back with my family. You know, my kids are at college now. They're gone. You know, they're not home anymore. So those, the time I have with them was valuable and precious.

[00:33:31] **Carol:** So my work phone stays on my desk and I only take it with me anywhere if I'm on call, otherwise I'm detached. I'm going to go spend time with my family. And I think it's all because I took that time to reset.

[00:33:44] **Tim:** That's awesome.

[00:33:46] **Adam:** so it sounds to me an awful lot like the idea of a sabbatical and while we've been talking, I've been doing just the tiniest little bit of research about, you know, what is it? What's the difference between a mini retirement and a sabbatical? and if I, if I'm understanding what I'm reading correctly. Sabbaticals started with, in academia, so like professors could have some time away from teaching and that sort of, and their, their research duties. But it's like a paid time, I guess for them it was, or, or it can be. and so mini retirement is basically same, same idea. You're just taking an extended time away from work, but not getting paid for it.

[00:34:26] **Adam:** Is that the primary difference that you're thinking of, Tim?

[00:34:29] **Tim:** Yeah.

[00:34:30] **Adam:** Okay. And then do you, go ahead, Ben.

[00:34:33] **Ben:** I think a sabbatical was supposed to be some, it was, it was like time to work on a research project or something. Like, I don't, I don't think it was like strictly a vacation, or maybe it was, I don't know. I

[00:34:49] **Adam:** you know, article that I found at the top of my Google search results,

[00:34:54] **Ben:** mean, I don't know, I've never had a sabbatical, but I, I, I was under the impression that it was stepping away to do more researchy stuff instead of like teaching a class.

[00:35:05] **Adam:** and I, I've heard it used as a euphemism for, you know, like, what is it, what do they do when, a police officer gets in trouble, they're like, they're on paid leave or whatever, administrative leave sort of thing, so, like, I've heard it used as a euphemism for that too, it, it all gets muddy after a while, but, I mean, I guess what I'm hearing from Tim is just like an ex, a semi extended or somewhat extended, unpaid time off from work.

[00:35:29] **Adam:** The interesting thing for me there with that concept is like, do you negotiate some sort of like optional return with your company before you go? Do you just be like, okay, this is it. I'm retiring and I may or may not be willing to come back in a year , you know, like.

[00:35:45] **Carol:** that's funny because some companies will tell you, they're like, hey, you have six months to return and all your benefits stay where they were. So you still keep that tenure you have, you still keep like however much PTO you were earning. Like as long as you come back in that window, then you're allowed to like, like just start right back off where you left.

[00:36:05] **Ben:** Very cool.

[00:36:07] **Tim:** the greedy capitalist in me realizes that. So if you are not taking a paycheck for like, say six months out of the year and you're, you're taking a little, little break or a little mini retirement, that means your annual income is going to be lower. So you're going to be taxed at a lower rate. So that's a really good time to throw some extra money into a Roth.

[00:36:27] **Tim:** because. Yeah, so, cause Roth is, yeah, so, so that's a, yeah, I would look into that. There, there, there can be some, some tax kung fu that you can play with that. Cause you're getting taxed at a much lower income bracket. It

[00:36:39] **Adam:** It depends on where you fall into the income, the tax brackets in the first place, but yeah,

[00:36:45] **Tim:** I mean, I would think people that are going to take a mini retirement are not living paycheck to paycheck.

[00:36:49] **Tim:** So, these are people that have, or, you know, or

[00:36:53] **Adam:** But if, if you're already at the top of your tax bracket, then it might only drop you to the bottom end of the same tax bracket. So

[00:36:59] **Tim:** right, right.

[00:37:00] **Adam:** anyway,

[00:37:02] **Carol:** is not a podcast for tax advice, you guys, so ignore that.

[00:37:06] **Ben:** You could also just try,

[00:37:08] **Ben:** quiet quitting for a couple of weeks every year, just,

[00:37:11] **Tim:** Just sit on the bed, only answer emails like, like two days later. Oh, wait, you already do that. I mean the email part. I know you work, you work super hard, dude.

[00:37:23] **Adam:** okay. So that's, you know, kind of, the motivation for taking a break. Let's talk about what we are going to do with our break. Does anybody have stuff that you specifically want to talk about?

## [00:37:34] What Carol's Going to Do

[00:37:34] **Carol:** I have one. I'm going to tell you guys. So you remember like a year ago, I bought golf clubs. I haven't really used them. So my husband and I signed up for like lessons and a membership this weekend. So we're going to do golf every single weekend between now and then. So I already have new toys in the backyard to go play with.

[00:37:51] **Carol:** So that's going to be my after work experiment for a while and kind of just try to get better at a sport. I feel like it's a nice way to have like a creative outlet, just being outside doing something physical and something I currently can't do.

[00:38:05] **Adam:** And we're heading into the time of year when it will actually be humane temperatures outside for you

[00:38:10] **Carol:** I mean, where you live, yes. Yeah.

[00:38:13] **Adam:** Well, it's going to be the lowest it'll be down there for the winter.

[00:38:18] **Carol:** Yeah. We're still in the nineties, you guys. It's pretty warm. We're still swimming in our pool. I'll tell you that.

[00:38:24] **Adam:** yeah.

[00:38:26] **Carol:** Which is nuts for Halloween.

## [00:38:28] What Adam's Going to Do

[00:38:28] **Adam:** So my big thing that I'm going to go into this in terms of like how I'm going to spend my personal time. you know, I started working on that, SvelteKit application and I kind of got stuck. I think it was because. I was not in love with the way that I was working with Supabase, which is, and this is going to be obvious in hindsight, but I didn't really realize that it was meant as like an open source, alternative to Firebase, which I'm sure is all over their branding and marketing and their homepage and everything.

[00:38:56] **Adam:** It's just, you know, to me, it was just like, Oh, it's a free Postgres thing. Okay. I don't need to read the homepage. I understand what Postgres is. And.you know, I just kept running into like the sharp edges of that, of like, I don't really want to work that way. I want to work this way. I just wanted a database, and it became demotivating for me.

[00:39:12] **Adam:** So eventually I realized like, I'm, I'm kind of making up excuses to not work on my side project, which is bananas. You know, I have multiple technologies that are exciting to me. And an idea that's exciting. And again, look at the person that you're talking to here. I could actually make money from this. And, and to not be motivated to work on it is, kind of crazy for me. So, I did, I took some time recently and kind of reset and, and I, instead of Supabase, I'm going to pursue going at it with MongoDB. Which I feel like should make things a little easier to get started with. And then, I did some research on hosting for that and I think I have something very reasonable to get started.

[00:39:53] **Adam:** And, and if it does start to consume data and get expensive, it at least should be making money to pay for itself. And then if I need to, you know, transition to self hosting on AWS or whatever, then I'll be able to afford that at that point, but that's the, the big thing for me is I want to do that. And of course, as I mentioned, we're heading into.

[00:40:13] **Adam:** The winter, but that also means like winter holidays, right? Cause we've got Thanksgiving coming up and Christmas and getting together with family and stuff. So that's going to be,

[00:40:21] **Carol:** Fun or depressing, depending on how you deal with holidays. Like honestly, holidays are well, I mean like real, like holidays are very bad for a lot of people. And they need something to just take them away from the holidays themselves so they find a hobby to avoid. Seeing Christmas trees and stuff.

[00:40:37] **Adam:** yeah.

[00:40:38] **Ben:** I also have this issue where if I have a big family event coming up, even if it's several weeks away, in my head it's like a mental block where I feel like I can't plan anything else

[00:40:51] **Tim:** Until that's

[00:40:52] **Ben:** thing is coming up. So I almost feel like November and December are just sort of throwaway months, even though the reality is the amount of time I have to spend with the family.

[00:41:02] **Ben:** Have to is not the right phrasing there. Matt, edit that out. The amount of time that I, the amount of time that I have to spend with my family is actually quite minimal. It just feels like, all right, I'm just not going to be productive until January. That's just, that's it. That's just the sense that I get.

[00:41:19] **Carol:** Let me ask you something, Ben, because I think like you in a lot of ways, or I feel like I do. When you're packing for a trip, do you avoid packing until all the laundry is washed and put away, or can you pack if there's dirty laundry? No,

[00:41:37] **Ben:** I don't do my

[00:41:38] **Tim:** That's what I thought. That's what I thought.

[00:41:40] **Ben:** and I actually try to pack as minimally as I can. 'cause I just don't like having a lot of bags. And I always over pack. I'll go to somewhere for a weekend and I'll pack like eight T-shirts because I'm like, I don't know what's gonna happen.

[00:41:53] **Ben:** Like, like I live this alternate. Reality life, where I'm going to go to a wet t shirt contest or something, you know.

[00:41:59] **Adam:** What if I'm on the set of Nickelodeon's You Can't Do That on TV and I get slimed? I'm

[00:42:05] **Ben:** So I am, I'm not the right person to talk to about packing.

[00:42:09] **Adam:** like, how many weeks are we going to be there? Okay, that's the number of pairs of shorts and underwear and t shirts that I need to pack. And then, you know, okay, socks and shoes.

[00:42:18] **Ben:** Yo, for real. I do that. I do like N plus one is kind of my go to.

[00:42:24] **Carol:** I pick out the shoes that I'm going to wear for all the events, like whatever we're doing. Like we were walking around Savannah and I was like, okay, I need tennis shoes and cute shoes for dinner. And then I pack clothes to match the shoes. So I only have to pack so many pairs of shoes. Yeah.

[00:42:38] **Ben:** Yes. I pack my one pair of shoes and, it just works out.

[00:42:42] **Tim:** I, I, I packed the middle of the road shoes. I can wear this with, I can wear this with like a tie and I can wear this with like shorts.

[00:42:48] **Ben:** There you go.

[00:42:49] **Tim:** That's what I was in Cancun. One pair of shoes. Actually, one pair of trousers actually. I brought two. I took like the jeans, there was like a pair of jeans and they just smelled terrible.

[00:42:59] **Tim:** I can't, like something happened in the laundry. They sat a little too long. I'm like,

[00:43:03] **Ben:** Yeah. They get that mildewy smell.

[00:43:07] **Tim:** can't wear these. I'm just wear, okay. I'm wearing khakis the entire time. Hopefully they stay clean. They actually, I got like grease on them, so I took them off and like washed them in the sink.

[00:43:16] **Tim:** And I'm, I got on the sink and then I get the blow dryer and blowing, like, it'll look like a total mess.

## [00:43:23] What Tim's Going to Do

[00:43:23] **Tim:** So I'll, I'll say what I'm gonna do with my day. So, you know, it's like. Two of the shows, it's, it's usually like one evening a night, right? There were, so we're, we're always trying to figure out what night we're doing it.

[00:43:34] **Tim:** Is it a Monday? We're going to do it on a Tuesday, you know, Thursday. So it frees up one evening, which doesn't sound like a lot, but like there's other stuff, like pretty much other evenings, I'm got stuff going on. Some of them move around based off of availability of other people and tiredness. But, Yeah, I, I really want to build my son an Iron Man suit and it's just, I haven't started it, right?

[00:44:00] **Tim:** I just need time to get on the 3D printers and get those printers going and building it and figuring out, because I know there's going to be a lot of tinkering and if I actually do get it completed before September, I'll be very surprised. It might be like a two year project, but I gotta start somewhere.

[00:44:16] **Tim:** Right. I'm just keep looking at, keep looking at the printer going, nothing's printing. Got this cool printer. I need, I need to, need to get the, need to get Iron Man going. So that's, that's where I'm going to spend my evenings where we're not recording for the next two months. Just at least get started.

[00:44:31] **Carol:** Like, I don't know a ton about 3D printing, but I've seen some different printers. And when I think of printing a costume, like, is the box that it prints in, are we talking like, like the torso body area of you? Like, how big is that box? And is it going to be like a bunch of small pieces you have to assemble or can you print any larger pieces at once?

[00:44:52] **Tim:** Typically the model that, I mean, the full size human model, you're going to have to slice it, right? So there's programs that you can slice it. So we'll fit on the build plate and then you glue them together. And that's what you, I mean, I don't have like a huge, super giant one. I mean, you can buy them.

[00:45:07] **Tim:** They're, they're going to be. You know, upwards of seven to 800, but they do have super big ones where you could do a suit like that in full pieces. But I'm not going to do that in the first round unless I completely fail.

[00:45:20] **Carol:** Interesting.

[00:45:21] **Ben:** are there public schematics for a, for Iron Man kind of a

[00:45:25] **Tim:** I have. Yeah. There's several, some people sell them, but I found one guy who sells them who has like a couple of free ones and they're pretty cool, so.

[00:45:33] **Ben:** Very cool. Is this something you could wear to a Comic Con or Dragon Con or whatever you go

[00:45:38] **Tim:** Max could. Yeah. I'm building it for him. you don't, no one wants to see a chubby, chubby iron

[00:45:43] **Adam:** ha ha ha ha ha! You say that.

[00:45:46] **Tim:** he's he's six foot three and weighs 128 pounds. So yeah, he'll fit, he'll fit less material costs.

[00:45:54] **Adam:** I I saw, it must have been a TikTok or something recently, but it was like, a bunch of Iron Man, you know, people dressed in Iron Man suits, leaving a room, right? I don't know if it was like a it looked like a Classroom in a school or something. But it was just like, you know, and you could see like, okay, that's the mark one suit, and then there was a mark three and, and then like somebody had the Hulk buster thing sort of deal.

[00:46:16] **Adam:** And, and the, the, the medium sized one, it's not the Hulk buster size, but you know, you get it. and then the very last one was a guy who came out in an Iron Man suit, but it was like purple and white and he had his helmet off and like under his arm, right. So he was kind of carrying it. Under shoulder, whatever.

[00:46:34] **Adam:** and, and he is got like the long green hair and his face is painted white and it's, he's the joker, but it's like he's in an Ironman suit as the joker and the, the suit is purple and, and white and green stuff. It was awesome.

[00:46:47] **Tim:** I think I've seen that. I think I've seen the photo you were referring to actually.

[00:46:50] **Adam:** Yeah, and, and then, you know, honestly, right after that, I would, even better, would have been, you know, like, super chubby Iron Man come out, and the, you know, the, the suit doesn't really fit him, his belly sticking out between the sections, and that would have been awesome.

[00:47:04] **Carol:** I don't know why, but when you said purple and giant, all I could think about was Barney.

[00:47:10] **Tim:** Man.

[00:47:11] **Carol:** was waiting to see where this was going.

[00:47:13] **Tim:** The Iron Barney.

[00:47:14] **Carol:** Yeah.

[00:47:16] **Tim:** you say you're a spin?

## [00:47:18] What Ben's Going to Do

[00:47:18] **Ben:** I don't have anything specifically other than I want to do more tinkering. I think building this companion app for my Feature Flags book, got me excited about the idea of just building things in general. and I, and I think one of the big mental breakthroughs that I had, and, and this kind of relates back to what Adam was talking about was when I first started to build the companion app.

[00:47:42] **Ben:** I had this grand idea of I was going to build an API and then I was going to build an Angular 18 front end to it. And I would consume that API. And I did start to go down that road and I got kind of ways through it. And it just felt like it was becoming more complicated to build the UI. And I, I think a lot of that was because I didn't really know what I wanted it to look like.

[00:48:03] **Ben:** And when you don't really know what it's going to look like, having a Really robust client side application actually feels like friction because you're not as dynamic in how you can build stuff. And so what I ended up doing was just simplifying it and going back to just having a, a route based ColdFusion application and, Just some simple CSS and Alpine JS JavaScript on the front end.

[00:48:27] **Ben:** And I just felt like I could move much faster and it felt like a really nice proof of concept, if you will, that I could build a somewhat robusty experience without having to have a really deep technology stack for the application. And that inspired me to try to do some other things that I think I've been putting off because I didn't want to, I don't know, bite off more than I can chew, but now that I feel more confident that I can keep things simpler, I want to try to build some more stuff.

[00:48:56] **Ben:** And keep it simple so that I can, you know, be more in that MVP mindset where I only build as much as I need to build to kind of prove out a concept. So nothing specifically, but just general sense of excitement.

[00:49:10] **Adam:** Sounds like fun, and definitely a good way to flex those muscles, which I know is something that you'd love to do.

[00:49:18] **Ben:** Can I, can I go off on a tangent for two seconds? Related, heavily related, heavily related though.

[00:49:25] **Adam:** I guess.

## [00:49:27] AI and Productivity

[00:49:27] **Ben:** So obviously everyone is talking about AI these days and a lot of what I hear Various podcasts is that AI allows you to move 10 times faster because it removes all of the drudgery and allows you to just focus on that high level, complex, important work. And I was listening, I think this was on Lenny's podcast, I think they were interviewing someone who was a head of product somewhere or head of design.

[00:49:55] **Ben:** And one thing that she pointed out, and it gave me a lot of pause. was that she actually really enjoys doing the drudgery work because it gives her a break mentally and she can allow the deeper topics kind of in that hammock driven development type of mindset where she has a lot of stuff marinating in the back of her head.

[00:50:15] **Ben:** And then she can go and just do the rote work and give her brain time to relax and to process things in the background and help her be more creative. And it did make me think about whether or not this notion of offboarding all of the drudgery work is actually going to be counterproductive in some cases.

[00:50:36] **Ben:** I mean, even just from a physical standpoint, I get a lot of repetitive stress in my wrists, and I know that that gets worse when I'm more stressed. And I have to imagine that when I'm doing kind of brainless work, it's actually helping me de stress because it's giving me kind of a mental pause where I have to get stuff done, but I don't have to think too hard. If I was for eight or nine or 10 hours straight, just doing the hardest possible mental work and offloading the simple stuff to AI, I feel like. It would just grind me down eventually. I don't think I would end up being more productive. I think it would actually make me less productive because it would just destroy me a little bit. I mean, this is all theoretical, but it definitely gave me some pause.

[00:51:25] **Adam:** Yeah, I've been thinking a little bit, not exactly the same line of thought, so I don't want to pull too far away from your thread, but just a little bit, I have similarly been thinking about like how AI is going to change the future of work. and you know, it occurred to me that like every time that there is any sort of advance, you know, whether it's going from horse drawn buggies to cars or, you know, anything like that, these significant advances, like not, so that was actually, I don't, it must have been a Newspaper article or something that I was reading.

[00:51:57] **Adam:** It was like, you know, it used to be, it would take you three weeks to, to move from the East coast of America out to the West coast. And the, the dream of the car was like, Oh, you know, now you can get there in three days and have this long vacation before you have to start your job or whatever, and that's not at all what happens, right?

[00:52:14] **Adam:** Now you just get there faster and you start work faster. and so we've just been like squeezing the stone of life for Tighter and tighter and tighter until there's no blood left to squeeze out of the stone. And I feel like the same thing is going to happen with AI, right? Like, so it's not going to make our jobs as coders easier.

[00:52:31] **Adam:** It's just going to make it easier to do 20 percent more work than we're already doing, or make it possible to do 20 percent more.

[00:52:39] **Tim:** Hey, I'm, I'm way ahead of you. I'm worried. So in the movie, The Matrix, the whole reason humans existed was that we supplied energy. But now it's like Google and all these guys, they're hooking their AI up to nuclear power. So they're making us redundant as batteries.

[00:52:57] **Adam:** I guess that's, that's either, it means they're not getting enough juice out of us, or we don't have to worry about becoming juice, so.

[00:53:03] **Tim:** Yeah. It was just, they'll just, just get rid of us. Yeah. They'll just have their own nuclear power, power plants.

[00:53:08] **Adam:** I mean, I know what you're talking about, so, I'm pretty near Three Mile Island pretty regularly, like, when I go skydiving, I

[00:53:14] **Tim:** Oh yeah.

[00:53:15] **Adam:** I can see it from the ground as well as, obviously, from the air, but, we're, I'm pretty close to it. and they are, you know, it's been in the news around us recently a good bit, because they're reopening it.

[00:53:25] **Adam:** Microsoft, right? Didn't they Yeah. Yep. So I think it?

[00:53:29] **Adam:** was cons not constellation. I don't know. there's some company that's, that is, you know, the, the energy provider or whatever, and they, they made a deal with

[00:53:37] **Tim:** No, no relation to the company I work for.

[00:53:39] **Adam:** yeah, no. and that's why I paused on that. I was pretty sure it was constellation energy or something like that, but I don't know, I could be entirely wrong there.

[00:53:47] **Adam:** It could have been poisoned by Tim's chat earlier, but anyway, yeah, so there, Microsoft is going to be the only customer getting power out of Three Mile Island, which will be interesting. but they're, yeah, they're opening it back up. So,

[00:53:59] **Tim:** Yeah, what could go wrong? Give AI access to nuclear power. Sure. It'd be great.

[00:54:05] **Adam:** so

[00:54:06] **Ben:** If I could riff for one more second on AI and

[00:54:11] **Adam:** It's your last chance for a couple of months, man.

[00:54:13] **Tim:** Get it out of your system

[00:54:15] **Ben:** one thing that I've been feeling and maybe this is not a valid thought, meaning that I think maybe my logic is flawed, but when I hear people talk about other technologies, historically, it feels very much more like a, I don't know what the right word here is, like a community effort. Like, Angular or Svelte or React.

[00:54:38] **Ben:** It's all going to come in. It's going to make our lives so much easier.

[00:54:41] **Tim:** days of the internet.

[00:54:42] **Ben:** It felt more like we're all in it together. And when I hear people talk about AI, it feels much more like fear mongering. Like anyone who doesn't know AI, like they're just going to be left behind. You know, like people don't talk about other technologies like that.

[00:54:58] **Ben:** You know, like, Oh, if you don't know React, like forget it. You're just not going to have technology job anymore. And I don't know, it feels really weird. It feels like there's a lot of othering happening. I don't know if that's the right word. It's like you're either in the group that knows AI or you're going to be in the group that gets replaced. And I'm not saying that's not true. I'm just saying that it, it doesn't, it just feels really weird. Some of the sentiment that's developing around it. And I, I don't care for it. I feel like we should be in the, like a rising tide lifts all boats kind of a mentality where like, how can we bring everybody into this tent as opposed to,

[00:55:36] **Adam:** But that means less profit for the

[00:55:38] **Tim:** Exactly. I I, I kind of get what you're saying, Ben, and it, what, what I'm thinking is, so like the early days of the internet felt very grassroots, democratically led, like this is, it was very power to the people in the early days of the internet, right? Like that this is gonna like democratize knowledge and this is gonna be great for everyone.

[00:56:00] **Tim:** People, you know, in, in poor countries will have access to things that they couldn't before. 'cause the cost. You know, of delivering it electronically is going to be a whole lot cheaper than doing it on paper.

[00:56:11] **Adam:** And then JavaScript ruined everything.

[00:56:12] **Tim:** exactly. As, but I mean, there wasn't, there was a very, very low barrier of entry, like the early days of the internet, you know, cause like the public, you know, the government was supplying, like, you didn't know where those rails were going, right, they were just there and you got on them and you did some HTML and some CGI scripts and some Perl or whatever, and there you were, you're on it, but it's like.

[00:56:35] **Tim:** Because of just the power that it takes to do AI, it's, it's a very specific group of billionaires and trillionaires that own it all. And so it's in their best interest to make sure that everyone feels like. This is relevant to them because they're hoping they're going to be the people that get general AI.

[00:56:53] **Tim:** Right now they're, they're working, you know, the person who gets general AI wins. That's, that's what the markets are betting on. Right. And so they're, they're putting their money on the horses and it just feels like that sort of thing. It's like, we're all just standing on the sidelines watching and kind of playing along, but it doesn't feel like we're a part of it.

[00:57:13] **Tim:** Or maybe that's just part of the fact of getting older. I don't know.

[00:57:16] **Ben:** don't know.

[00:57:16] **Carol:** your days on the internet, Grandpa.

[00:57:19] **Tim:** Exactly.

[00:57:20] **Ben:** No, because it's true. I think there's a, like a timeline skewing that happens in people's minds. When you picked up something like jQuery for the first time, or even, you know, more complex front end frameworks, maybe I'm misremembering, but it felt like you could play around with it for. A week, two weeks, and you could actually feel like you're making meaningful progress and you could start to see a path forward, like, Oh, this is actually going to really change the way that I do stuff.

[00:57:50] **Ben:** And when I hear people talk or when I hear people who claim to have these massive productivity boosts, they're like, yo, AI has made me 10 times more productive. And then they start to reveal some of the details about what it is they're doing. It's like, oh yeah, I've been working on this AI framework internally for the last four years.

[00:58:07] **Ben:** And it's gone through a lot of iterations and it Does a very specific type of code. And you're like, yeah, if you spent four years building any kind of code generation tool, I'm sure it would make you 10 times more productive. It just, I don't know. It feels like the scale of everything is not inclusive. Like kind of, kind of what you're saying is it's just, there's groups that will be able to leverage this easily and maybe most effectively, and then there are groups that will just have it in minor ways. Maybe.

[00:58:38] **Adam:** I do feel like the whole, you know, pushing us, the general populace, the have nots, off to the sidelines is kind of what the point of the original structure of OpenAI, the company, was supposed to kind of prevent or minimize. And, you know, that's out the window now.

[00:58:57] **Carol:** Yeah,

[00:58:58] **Tim:** They're like, we're not open AI anymore. We're for profit ai.

[00:59:01] **Carol:** yeah.

[00:59:02] **Ben:** It also feels like the scale of it. The scale of the learning that needs to be done, that it has to be done at an organizational level. It doesn't feel feasible that you could have an individual spend all of their free time learning about this and then bring it into a company in the way that someone could say, Hey, I just tried Panda CSS and it's pretty amazing.

[00:59:26] **Ben:** Maybe we should have a lunch, a lunch and learn about it. And maybe some people could get excited about it. The, the amount of effort it must take to train models and then make sure that they're delivering accurate information. They make it sound like it's a grassroots thing, but I can't imagine that anyone is really doing this as effectively.

[00:59:49] **Ben:** As a company that says, you know what, let's create an AI department and an ops team and a machine learning team. And let's put, you know, 5 million into it annually to see if we can boost productivity.

[01:00:02] **Tim:** why Nvidia just outpaced. Apple is the most expensive company in the world.

[01:00:07] **Ben:** Like I

[01:00:07] **Ben:** was talking, I was I was listening to some interview the other day and someone said, Oh, isn't it, isn't it a problem that the AIs can just hallucinate and give you bad information? And the answer was like, Oh yeah, of course. But all you need to do is have a totally separate AI that you can validate the output of one AI against.

[01:00:25] **Ben:** And I'm like, come on, people are not doing this as hobby projects. I have to imagine that that's, it's crazy. Not, not that the idea is crazy, but they're, they're, they're like hand waving over all of the, what I assume is actually immense amount of complexity.

[01:00:41] **Tim:** Sounds like you should work on that during your break.

[01:00:46] **Adam:** with your one night a week,

[01:00:47] **Tim:** You, you're one, one extra night a week where Yeah. We keep you up past your bedtime of like 8:00 PM

[01:00:54] **Carol:** No, what's really gonna happen is all the AI listening bots are gonna listen to this and downvote us and we're gonna get removed from all the podcast apps now. Thank you, Ben. Thank you. Uh huh.

[01:01:05] **Ben:** I for one would like to welcome our AI overlords.

[01:01:10] **Adam:** Alright, I think that's, enough of that. Let's, let's move on to the after show. So before we get to the after show, I gotta do the whole dismount thing.

## [01:01:18] Patreon

[01:01:18] **Adam:** So that's the part where I say this episode of Working Code is brought to you by Curvy Ironman, brought to you by Brondo. It's got electrolytes

[01:01:26] **Tim:** Prodo,

[01:01:26] **Adam:** you. I don't know why I just have, um,Uh, Idiocracy on the brain, yeah. and listeners like you, if you're putting, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. , our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:01:46] **Adam:** Special thanks, of course, to our top patrons, Monte and Giancarlo. You guys rock.

## [01:01:50] Thanks For Listening!

[01:01:50] **Adam:** As I said, we are going to go to the aftershow. We actually have quite a bit planned for the aftershow for once. I think it's this whole like taking a couple of weeks off here and there, is just like let personal stuff pile up.

[01:02:00] **Adam:** And so we have a bunch of personal stuff to, to discuss.kind of like, so let me, let me, Let me give you some teasers, right? So, I have a podcast recommendation, which is, which is, kind of somewhat Star Wars related even. I have, some, like, health stuff, shoulder injury and some other positives and negatives, going on to discuss there.

[01:02:19] **Adam:** I have a podcast. Yeah, and then like, personally, like this week I've gotten into Blue Sky, so I want to get into that a little bit.and then Tim has some stuff he wants to talk about, like what, I guess some strangers told you some fun stuff on an

[01:02:33] **Tim:** it's amazing what a stranger would tell you on a plane about their personal life. It's, it's absolutely ridiculous.

[01:02:38] **Adam:** If you want to help us out and get access to that sort of discussion, then you can go to Patreon.com/WorkingCodePod. Throw a few dollars our way, helps keep the lights on around here. and in exchange we provide you with more banter. That's gonna do it for us this week. We'll catch you, not next week, but again soon.

[01:02:56] **Adam:** And until then,

[01:02:57] **Tim:** Come in close, guys. Come in close. Come in. Listeners, even though we're taking a break, it's not, it's not forever. It has a beginning. It will have an end, but we'll never take a break from knowing that your heart matters.
