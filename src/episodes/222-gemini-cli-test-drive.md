---
title: "222: Gemini CLI Test Drive"
description: "In this week's episode, Adam and Tim delve into Google Gemini CLI, test driving it on real code to find it's capabilities and limitations."
date: 2025-07-04
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/222-gemini-cli-test-drive/id1544142288?i=1000715723815"></iframe>

In this week's episode, Adam and Tim delve into Gemini CLI, a command line interface tool for AI by Google, test-driving it on real code to find its capabilities and limitations.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/222-gemini-cli-test-drive.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** So I actually told Gemini, I said, if you're gonna run an AWS CLI command prefix it with this and that way it will have access.

[00:00:07] **Adam:** And so, and it did, it worked great.

[00:00:09] **Tim:** so it was able to figure out how to go grab the relevant logs itself.

[00:00:12] **Adam:** It tried very hard, and that's kind of where this broke down.

## [00:00:35] Intro

[00:00:35] **Tim:** Okay here we go. It is show number 222 as in pew, pew, pew. On today's show, non patrons are not gonna get that joke. Sorry. Yeah.

[00:00:44] **Adam:** and uh, yeah, and, and on today's show, we got myself and Mr. Tim Cunningham. Ben is out peeing and Carol is out sick. So.

[00:00:55] **Tim:** She's not sick. She had some teeth work done and she can't really

[00:00:59] **Adam:** Yeah. Dental work. I figured, you know, trying to re respect your privacy. We'll just

[00:01:04] **Tim:** HIPAA violation, sorry.

[00:01:06] **Adam:** Yeah. Uh, anyway, uh, and we're gonna talk about, you know, I figure there's not enough content about this on the internet right now, so I thought we should do our part in correcting that. And we're gonna talk about some AI stuff

[00:01:18] **Tim:** What really? Hmm. Haven't heard about this?

[00:01:21] **Tim:** Yeah. I, I have two, AI related topics that I want to dig into a little bit. But first, let's start with our triumphs and fails, with only two of us here, we're kind of, Flip? Flip a coin.

[00:01:31] **Adam:** bowed for it. Yeah. And, uh, Tim, you're gonna go first. So what's going on?

## [00:01:36] Tim's Fails

[00:01:36] **Tim:** so I, I gotta fail. I got two flavors of fails. One is work related, one is home related. so the work related one is, I'm I. You know, been with the company, the payments processing company for a long time, and I've just, you know, it was, it was in the groove, you know, it was just like everyone knew their roles.

[00:01:56] **Tim:** It was super easy. Money was coming in, it was great. But now I'm wearing, I'm helping out with another company within our, within our, uh, portfolio. And it's like, I'm really getting overwhelmed. I, I, I think I, I don't think the. Me 10 years ago would've gotten overwhelmed. ' cause I was just used to being overwhelmed every single day.

[00:02:14] **Tim:** That was just sort of status quo. But you know, when you kind of like can just kind of like coast a little bit, you know, and then you jump back in it, you're like, wow, okay. I don't remember this muscle memory. So it's like having to deal, you know, everyone got ev everyone at Pay Cloud gets along and you know, everyone knows they're staying in the lane.

[00:02:33] **Tim:** And here there's just, I'm not saying things are bad, it's just. There's different personalities and I'm trying to figure them out and trying to, you know,make sure everyone's in their roles and doing what they're good at and not doing what they're bad at, and preventing a, you know, friction between different.

[00:02:49] **Tim:** Personalities, different silos, so that, that gets a little tiring. And then just the level of, of work. On the other hand, I honestly don't get bored these days. I, I was getting a little bored before, you know, it was a little, it was kinda a little boring. It's like, okay, everything was kind of humming along.

[00:03:03] **Tim:** So at the end of the day, the, the, the time just flies by. That's great. I, I, I love that portion of it, but it is, it is getting a little stressful. So I'm gonna have to take some, uh. Some time this, this, we're recording this right before the 4th of July. I'm gonna take this weekend and kind of meditate on what I need to do to do some big muscle movements and some things.

[00:03:27] **Tim:** You know, I've, I've just, this time I've just kind of like laying back a little bit and just kind of getting the lay of land. You don't wanna come in swinging a big bat and then realize you're wrong about everything. So I think I got a pretty good lay of the land. So now I think it's time to start

[00:03:40] **Adam:** Is this, you were doing a bunch of interviews before, so you were kind of, that's where you were surveying, getting the lay of land as you

[00:03:46] **Tim:** Yeah. Yeah. So I've interviewed, yeah, I've, not interviews, but just kind of one-on-ones with everyone within the organization trying to get a feel for things. So I, I think I got a feel for things and I see how things are working and I see what's working well, and I see what's not working well.so I just gotta, you know, gird my loins and get ready to go to battle.

[00:04:04] **Tim:** 'cause you know, some people, you know, some people are entrenched in what they're doing 'cause that's what they're doing. And to get them to shift for the good of the company is can sometimes be a battle. But, so I gotta come up with this three day weekend and with ways to make it at least appear optimally actually be a win-win situation for change.

[00:04:23] **Tim:** So.

[00:04:24] **Adam:** so you're gonna be working over the long weekend,

[00:04:26] **Tim:** It's not necessarily working, it's just more thinking.

[00:04:28] **Adam:** you know marinating?

[00:04:30] **Tim:** Yeah. Marinating that, that's how I approach things, right? I have something, I'm like, I just kind of stick it in the, in the back queue of my brain and percolate on. I don't, you know, I don't sit there and I don't have spreadsheets and write things down.

[00:04:41] **Tim:** If I do have a good idea, I will write things down. I maybe do a, sometimes do a little, a brain map where you just free associate a lot of things and, but eventually it's like the idea just comes to you. That's, I'm very intuitive how I work.

[00:04:54] **Adam:** it's funny, like I feel like I, I can say the same thing about coding work, right? Like I'm the type of person I can just kind of. Get to understand, get to know a problem, and then stop thinking about it. And the, the solution will come to me in the shower.

[00:05:08] **Tim:** yeah.

[00:05:09] **Adam:** But when it comes to things that are not programming challenges, but that are work related, right?

[00:05:13] **Adam:** Like, so some, something more soft skills, you know, dealing with people or, or teams or planning or something like that. Man, I am just so good at compartmentalizing. I, I punch out at the end of the day and work doesn't exist until nine o'clock the next morning, unless I get like a phone call or an on call page, you know?

[00:05:31] **Tim:** That's, that's, that's good. I envy that. I, I wish I could do that. I, I can't, I can't do that.

[00:05:36] **Adam:** I mean, it's a blessing and a curse because like you're saying now, now I don't get that, free background processing of things, right? I have to dedicate time and effort to getting those tasks done and, and now those tasks exist for me. Right now I'm doing compliance work and all this other stuff that's not writing code, so.

[00:05:54] **Tim:** Yeah, sure. So that's, that's my fail for work, just feeling a bit overwhelmed, but I, I see a way forward for home. I'm gonna, you know, I'm just, I'm not gonna make this long. Every a pilot seems to fall apart at the exact same time. I'll talk about on the after show things that, things in the home front, just like, you know, interpersonally is great, but the house just like is driving me insane.

[00:06:17] **Tim:** So

[00:06:17] **Adam:** have the, have all of your appliances been listening to Janet Jackson or.

[00:06:20] **Tim:** I, yeah.

[00:06:21] **Adam:** Did you not?

[00:06:22] **Tim:** They wanna be the ones in control.

[00:06:24] **Adam:** I didn't know if you saw that reference or saw that show up. Uh, so a couple of days ago in our Discord, uh, I believe it was Adrian posted a link to, a news article of sorts, you know, some niche, blog or whatever.

[00:06:35] **Adam:** But, uh, basically long story short, a song that Janet Jackson wrote in like 1989, I

[00:06:41] **Tim:** Oh, I did see that. Yeah. Yeah, yeah. Now I know what you're talking

[00:06:43] **Adam:** like specific frequencies in the recording were causing laptops to just start crashing. It didn't even have to be the laptop that was playing. If, if it was nearby, a laptop that was playing the song, then it would cause the platters and the hard drive to vibrate their resonant frequency.

[00:07:00] **Adam:** And it would

[00:07:01] **Tim:** It's like an electronic brown note.

[00:07:03] **Adam:** yeah, and it would make the laptop crash. That was amazing. I loved reading that.

[00:07:09] **Tim:** Okay. Yeah.

[00:07:10] **Adam:** figure that out, man, the, the kind of sleuth thing that you have to do.

[00:07:15] **Tim:** Craziness. Well, so that's me. How about you, Adam?

## [00:07:18] Adam's Triumph

[00:07:18] **Adam:** I'm gonna go with a triumph. Um, I mentioned last week that we started working on our SvelteKit port, laying the foundation work and doing a lot of inertia building.I it, since then, I don't think that I have personally worked on it at all, which in some ways is good. Right? It means my other teammates are working on it.

[00:07:35] **Adam:** 'cause we are still. Moving the project forward, is, is not great for me because I don't get to write this felt code, but, you know, I'm, I'm, I'm planting seeds that are going to grow into a beautiful garden that I get to enjoy. But the, the bigger triumph here is we're still, you know, a week later we haven't given up on the effort.

[00:07:51] **Adam:** It wasn't like, oh, this was a terrible idea, and abandoned it. The, the team is still, you know, we found, we have found some challenges and hit some roadblocks. It's like, okay, well how are we gonna solve this problem? How are we gonna do this? Because we're coming at this from a very, you know, we're, we're approaching it from sort of a newbie angle on the technology, but we have a very complicated, sophisticated application we're trying to run here.

[00:08:14] **Adam:** So it's like right out of the gate we're, you know, hitting a lot of, not edge cases, but just very demanding challenges, right? Like the very first thing we're doing. You know, we're, we're setting up, okay, you've got routing, you've got your database access board. It's like, okay, we also have internationalization and accessibility specific challenges, and, we're gonna have dynamic layouts, where like, you know, on the customer gets to control for this particular URL, which template gets used and they can control the colors on it.

[00:08:44] **Adam:** And so it is like gonna be dynamic CSS and dynamic layout inclusion and stuff. So. It's gonna be a lot of fun. Gonna be a lot of work, and I'm excited about it.

[00:08:53] **Tim:** That's cool. You, you remind me of something. I had a conversation with one of our top. Developers and I was just saying, Hey, you know, this is, we have a strategy for 2026. And, you know, I was explaining it and he's just, you know, he's telling, all he does is just throw out all the reasons why it's a bad idea.

[00:09:13] **Tim:** It's too hard, you know, you know, he is like, it's gonna be really, really hard. And then I, I just, I felt like a bit of a jerk, saying this, but at the same time, I think he needed to hear it. I'm like, why do you wanna just avoid what's hard?

[00:09:26] **Adam:** Yeah.

[00:09:27] **Tim:** I mean, yes. It's hard. I, I agree. It's hard, but it's like it's worth doing.

[00:09:32] **Adam:** Yeah. Oh, a hundred percent agree. You know, uh, I've, for the last week, every now and then I'll get like a bee in my bonnet and I'll be like, Ooh, that would be a cool tattoo. Something I, you know, like I, the thing that I'm thinking about right now is like on my forearm, I kind of wanna get the word choose.

[00:09:46] **Adam:** It's just like I, you know, choose the hard thing. The, the, the way that your life proceeds is, is as a result of a series of your choices, you have to make choices. And you could, you get to choose, am I gonna sit on the couch and eat Doritos or am I gonna go down into the gym and, and lift weight, right?

[00:10:01] **Adam:** Like, um, and so, and, and that. And, I had this, it's not really a direct quote, I think it's kind of a bastardization of a bastardization, but. people are like, a lot of people like this when it's the obstacle is the way, right. I think it's kind of adapted from Marcus Aurelius. but the idea being like, only when the obstacle itself seems insurmountable, can you find the motivation and the creativity to overcome it.

[00:10:26] **Tim:** Yeah. My, my daughter was talking. We, I was, we were talking last night and you know, we. She's got these costumes that she wants to do for the, the con that's coming up in September. And, and she, you know, I'm like, so, you know, realize it's like a month and 25 days away. She goes, yeah, well you know, I have an action plan.

[00:10:43] **Tim:** I'm like, that's good, good that you have a plan. We just maybe need a little more action. 'cause nothing's gotten, nothing's gotten started yet.

[00:10:50] **Adam:** Yeah, more action, less planning.

[00:10:52] **Tim:** Yeah, exactly. You got the planning down. That's awesome. But the action's really the important thing. You can't, you can't wear, you can't wear a plan.

[00:11:00] **Adam:** Yeah, you can. It just won't be a very good, uh, costume. The, I think honestly though, that's a good forcing function, right? Like having a deadline, right? The con is gonna happen whether or not you're ready. And sometimes procrastinating a little bit is good because it, it forces you to make decisions, right?

[00:11:16] **Tim:** simplify, focus.

[00:11:18] **Adam:** I, yeah, if I don't make a decision right now and, and go for the, the attainable version, right? So a lot of times if you have too much time to get ready for something like that, you know, you're like, oh, I'm gonna do the big, awesome, you know, 10 times more expensive, 10 times more difficult, 10 times more challenging to put together version versus, you know, oh, I waited too long now, this is the only version I could possibly accomplish, but you get it done.

[00:11:43] **Tim:** Yeah.

[00:11:44] **Adam:** Yeah.

[00:11:44] **Tim:** Well, cool.

## [00:11:46] AI Discussion: Gemini CLI and Debugging

[00:11:46] **Tim:** Let's talk about some ai.

[00:11:47] **Adam:** That's a unique idea. Um, so, um, I, you know, we, we talk a lot about AI and I feel like we very often talk about it in hypotheticals. We've, early on you were talking about how you were hooking it up to phone stuff, your, the menu thing. Yeah. Um, and honestly, that's part of what inspired me to wanna talk to you about this because.

[00:12:12] **Adam:** The two things, well, one of the two things is, more, implementation wise, so I'm very curious to see what inputs you'll have there. But let's start with the other one. so a couple of weeks ago, I think, uh, Google released a free version of Gemini. I don't remember exactly the, the naming around it, but basically it's a Gemini CLI.

[00:12:34] **Adam:** So Gemini is their AI thing, CLI, meaning, command line interface. So it's kind of more directly competing with Claude Code, the, the CLI tool. Basically, you know, you NPM install Gemini, and then you can in your command line, drop into a folder, run the Command Gemini, and it's like, okay, the folder that you're in and all of its sub-folders is the context for what you wanna do.

[00:12:56] **Adam:** And then you can ask it questions or you can say, make these changes or whatever in it. We will ask for more permission to do more things along the way. And, uh, you know, I played with a little at first. and one thing I have found that I really like is that the free tier seems to be very generous. Uh, you know, I, they say they give you a certain number of tokens per month or whatever.

[00:13:16] **Adam:** Uh, and as you're using it down in the, like, the sort of the footer of the CLI, it stays fixed along the bottom, but it shows you like this is the percentage of your contexts that you have remaining in the current period or whatever. I don't think I've ever seen it go below like 97%. In, in all the stuff that I've been doing.

[00:13:34] **Adam:** So I found it very generous.So the, the project that I started playing with, we have this, lambda function.

[00:13:41] **Adam:** It's as so many things in our stack are, you know, it starts out simple and then a couple of years into it you're like, wow, this got really complex, really fast. so we have a lambda function that we use that is building dynamic SQL statements to select data outta the database. And, and so for each one of those SQL statements that it runs, we'll call that like a population, right?

[00:14:01] **Adam:** It's building these populations, and then it's basically doing like Venn diagrams to find the intersections of these populations.

[00:14:07] **Tim:** Ah, interesting.

[00:14:08] **Adam:** and that way, you know, you can say, okay, I need all of the engineering graduates with a, that also have a master's degree that graduated between these years that live in this zip code that are married.

[00:14:21] **Adam:** Right. That sort of thing. and, uh, so it'll, it'll do the work to pull all that out and that's great. It works gangbusters like 95 to 99% of the time, and then every now and then it just kind of poops the bed.and so, you know, it is been one of those things that it's like, well, you know, it's fine if it fails, you know, you just rerun it and, and you're good like 99% of the time.

[00:14:45] **Adam:** So, it hasn't really arisen to the point where it's like, we've invested a bunch of effort into debugging this. But, uh, I was like, okay, well, you know, I can, this is an interesting opportunity. I can just pull up Gemini in this folder and say, here's the problem.and see if you can figure it out. And, and I was like, you know, this is kind of how the program runs, what it's doing.

[00:15:06] **Adam:** I, I gave it some, some information. You know, it's a lambda function, and this is the file that it starts in. So it figures out based on that, those two clues. Right. Okay. I know it's a AWS Lambda, so it's gotta have some sort of a handler function and this is where it is. Then it can kind of spider out from there.

[00:15:22] **Adam:** It's like, okay, well you're importing this function from this file. Can I go read that file? It asks for permission and you, you give it permission and it goes and reads that file and it understands more and understands more. And it, and it kind of came back with a list of like three or four potential problems it could see.

[00:15:36] **Adam:** And I was able to tell it like, oh, I've ruled out that one case, but it maybe it's one of these other ones. And I said, you know, well, you know, what should we do next? How? How can I help you debug this? And it asked for logs. I was like, well, you know, it's on CloudWatch. The, the AWS lamb does by default, if you just do like console log from a node application, it lands in CloudWatch, which is generally pretty great.

[00:15:58] **Adam:** And we, for compliance reasons, I happen to know that we hold onto all of our Lambda logs for exactly 12 months. 'cause that's the requirement now. and so I was like, okay, well I definitely

[00:16:06] **Tim:** Who wrote that requirement?

[00:16:08] **Adam:** well that is the, the minimum for whatever,certification that we're getting. yeah, uh, I initially, I had written it much shorter.

[00:16:16] **Adam:** I think it was gonna be like three months or something for production logs, but then I ran across that requirement anyway. Um, so I had to go back through some of our chat history and our team chat and find a time when we knew that, one of the list things failed so that I could say, okay, it was this particular list id, and it happened at roughly this timestamp.

[00:16:37] **Adam:** And I said, okay, cool. So I'll use the A-W-S-C-L-I and, okay, so here's another really interesting cool thing is I've told you guys in the past about the way that my team has like a custom wrapper around the one password, CLI, we call it OPIQ. and and we have to like, we have to call that. So instead of just saying like AWS Lambda.

[00:17:00] **Adam:** Whatever to get the, to get information about Lambda. We say OPIQ space AWS space, Lambda, blah, blah, blah. Right? So it, it kind of prefixing the command sets up some environment variables to give it permission to do what it's doing. So I actually told Gemini, I said, if you're gonna run an AWS CLI command prefix it with this and that way it will have access.

[00:17:21] **Adam:** And so, and it did, it worked great. I was very impressed with that. yeah.

[00:17:25] **Tim:** so it was able to figure out how to go grab the relevant logs itself.

[00:17:29] **Adam:** It tried very hard, and that's kind of where this broke down. honestly, I, I'm not, I'm not gonna go dig through the logs my, there. I have another coworker who is like a zen master at digging through CloudWatch, finding a very specific thing that's not me. You know, he's, he, he like somehow groks the, the syntax, the special syntax for searching through CloudWatch logs.

[00:17:50] **Adam:** And it just, the four or five times he's tried to show me, it just has not managed to sink into my brain.so, I, I had a rough timestamp and I, and I told Gemini how to do it. And I think initially it was, I, it was, I don't remember exactly what it was doing, but it was looking through the logs one way and it, it couldn't find anything relevant.

[00:18:07] **Adam:** and so it was like, okay, well can you gimme, a timestamp? And that's when. I gave it that timestamp and it's, so then it kind of narrowed down, or that's what it was. Instead of just starting with the most recent logs and working its way back, which was its initial attempt, it's like, okay, well I can't get to the logs that I need.

[00:18:23] **Adam:** That way, I guess just 'cause it was, it was months ago that this happened. So instead what it did was it, on the second pass, it like got a list of all the log streams that are available for that function and, and the, I guess that. When it lists those from AWS, I think it gets like minimum and maximum timestamps on 'em.

[00:18:41] **Adam:** So then it was able to like iterate, just like skip over all these more recent log streams and then it dug through the relevant log streams, which was cool to see it do. and

[00:18:50] **Tim:** how do you see it? How do you see it? Do it? Does it show up in the, in the CLI.

[00:18:53] **Adam:** It tells you what it's doing, it kind of explains what it's doing as it's, as it's doing it. You don't get to see the, the, I think that if you were watching the inputs and outputs, like the commands that's running and the stuff scrolling by on the screen or whatever, it would probably go too fast to be able to make sense of it.

[00:19:06] **Adam:** But it, instead, it's like, okay, I'm gonna, you know, list all of the log streams and, and go back until I find the right, the one that's at the right time or whatever, and then now I'm gonna, I found that one. Yeah.and so it does that. And I think it was initially looking for specific keywords in the error message, like it was looking for the word error or the word timeout.

[00:19:27] **Adam:** I think there was a third one, but I forget what it was. Uh, and it couldn't find anything there. So maybe if I spent more, I get kind of at this point, I was super impressed with how deep it was able to go just on its search, but I was like, okay, well this isn't gonna be as easy to resolve as I had kind of hoped, so I'm just gonna walk away.

[00:19:45] **Adam:** I was be able to just kind of shove it, but. I was super impressed, like how far it got. So it didn't resolve it, but it, it was very neat to watch and, and really made me wanna continue, using it in that way. So I, I wanted to spread the good news, like, this is available, it's free. Uh, it's a generous tier.

[00:20:04] **Adam:** It's capable, you know, I guess

[00:20:06] **Tim:** Yeah, I like that. I, I think I. Now I've heard you explain it 'cause I've heard about it. The CLI, and I've tried with GitHub, but unfortunately our repositories are in like a different GitHub mode or billing cycle or something. And I don't wanna mess with that. But if I can, if maybe if I can pull down Gemini and just point it toward our, our, uh, you know, local folder where the repo is and have it look at it, that'd be cool.

[00:20:31] **Adam:** And it was really easy to install. Like you, I think you can like download it and compile it from source if you want to, but why would you bother when it's as easy as like NPM install Global Gemini? So, yeah, yeah, that's really kind of all I had to say about that. Like I was just impressed and I, I wanted to share that really interesting discovery, for lack of a better word.

[00:20:53] **Tim:** Yeah, it'd be interesting like, so like Brian. What's his name on our

[00:20:59] **Adam:** Tech.

[00:21:00] **Tim:** Spiffy tech. Yeah, spiffy tech. Yeah. Brian, uh, he seems to know everything about like doing, um, AI stuff, so I'd be interested to hear what his, his takeaway is from our conversations about this. He'll probably have some input about that.

[00:21:13] **Tim:** I always respect that guy when it comes to his take on the ai 'cause he seems to use it a lot.

[00:21:18] **Adam:** Yeah.

[00:21:19] **Adam:** Seems

[00:21:19] **Tim:** working, so I, I dunno what, yeah, I, I actually interviewed him for a job, but, but unfortunately it just didn't work out.

[00:21:26] **Adam:** yeah, I think we call, is it, available? That's the right word. That's the PC word. He's available.

[00:21:31] **Tim:** he's available. Yeah. Yeah. Yeah. It's crazy. The job market's so crazy right now. It's like everyone keeps complaining that a business is like, no one wants to work. And yet, you know, my daughter, she's reapplying, she's applying to tons of jobs and no one ever gets back to her.

[00:21:45] **Adam:** Yeah. I think, you know. Okay. So, Relevant ish to this moment of this discussion. I don't think I've mentioned this on the show. My oldest daughter, my only daughter, uh, got her first job recently. I don't know if I mentioned that to you guys. Yeah, I mean, she's, she's working at the PA Renaissance Fair.

[00:22:02] **Tim:** okay. Very cool. Oh man, I'm jealous. I'd love that. That that's right up my family's alley. We too, we live too far away. Otherwise we'd be working there for sure.

[00:22:10] **Adam:** I'll put it on the, the list of things we can bring up in the after show. We

[00:22:13] **Tim:** That's cool. That's really cool. Yeah. That's awesome. Yeah, so she's like trying for State Farm and some local banks 'cause she was working at Cracker Barrel, but her knee, she, her knees, she has like joint issues with her joints and just, she was, I mean, couldn't she'd work three days and she couldn't walk for the next two. So she just had to, had to quit. She's making good money, so it's ridiculous. I mean, yeah, they get less than minimum wage, but man tips. I have a hold of respect for people who live, who work off tips. 'cause she knew how to

[00:22:45] **Tim:** work those people at Cracker Barrel. The old people would come in and they'd be like, we want the manager to know Lily did a great job and they'd leave like a $25 tip on a $50,

[00:22:56] **Adam:** Wow.

[00:22:57] **Tim:** Yeah, so she was making good money, but it's just too painful to work. But it's like everyone says they're working and now she, like, she puts all these apps in and never hears anything. Of course I say that I've got about 50 apps I need to look at right now for an entry level job at work, but, uh,

[00:23:11] **Adam:** So you're part of the problem, Tim.

[00:23:13] **Tim:** I, part of the problem, problem is I look at all these and I'm like, some of them just like, I don't think any of these are, some of these are not real.

[00:23:20] **Tim:** Some of these are ai,

[00:23:21] **Adam:** Yeah. That's a, a whole new can of worms to deal with.

[00:23:25] **Tim:** definitely.

## [00:23:26] AI in Fundraising and User Interaction

[00:23:26] **Adam:** Well then, so I have this other one. I mentioned I have kind of a use case for AI stuff. and I want to, I wanna pick your brain. So we have

[00:23:34] **Adam:** these,

[00:23:34] **Tim:** I don't, know how much is there, but whatever is there, you can, you can pick.

[00:23:38] **Adam:** well, you might be able to point me in some interesting directions. This, I, I think this is kind of kind, I think this is kind of gonna go similar to when I ask you guys for help with my side project stuff. Right. You kind of just make suggestions and, and they tend to tend to be pretty good. So, we have these giving forms and when you make a gift to a college, generally, you kind of have two choices. You can either specify, you know, I want this, this gift to, to. Support the, the engineering school, you know, they have like a, they're trying to build a new building or it's for their lab equipment or something, right?

[00:24:11] **Adam:** Like they have these big campaigns that they run and they each have something called a designation, right? This is a specific bucket that they're collecting money for. And then if you are not like targeting your donation like that, they just have like a unspecified or, or a general fund, sometimes they call it.

[00:24:31] **Adam:** Just like, I just wanna give money to the school and let the school decide where to spend it, sort of thing.but those designations, there tend to be, especially bigger schools, there tend to be a ton of them, right? And, and everybody has opinions on how they should be organized and presented, and they're all wrong.

[00:24:47] **Adam:** Like there's, there's no such thing as a right opinion, right? 'cause they're all so often they're like diametrically opposed. People are like, uh, they should be organized by school. So that. You know, I know I, I, I can either go look at the School of engineering or the school of philosophy or the school, you know, whatever the School of Basket weaving, and, and make

[00:25:06] **Tim:** When you say school, do you mean like schools within the university?

[00:25:09] **Adam:** Yeah. Yeah.

[00:25:10] **Tim:** so not like a separate institution, but

[00:25:12] **Adam:** correct. Yeah. Um, yeah, so I. I didn't know this was a thing until I got to college, but apparently, yeah, that's, it's like, you know, the, I went to whatever university and it's like within the university it was like the Alfred J Learner School of Computer Science or something like that.

[00:25:28] **Adam:** Right. and so it's like a, it's a sub-organization or whatever, and honestly it, it feels a lot like na like naming a stadium. Right. They're just selling the, the naming rights probably, but. Whatever. and yeah, so like some people's opinion is like, it needs to be very hierarchical, right? Like, I know I may not know exactly where I want my money to go, but I know I wanted to go to this department, or I know I want it to be used for athletics stuff or whatever.

[00:25:52] **Adam:** Right? And then some other people are like, but it should be alphabetical so that I can just kind of scroll and get a rough idea or,

[00:25:59] **Tim:** But I mean, how do you know what the, how the schools are named? Right. It could be,

[00:26:03] **Adam:** or, or.

[00:26:04] **Tim:** it could be, you

[00:26:05] **Adam:** Right? Or what if it should be poli politically aligned, or maybe it should be like the, the ones with the most need go to the top or whatever, right? So there's like all these different views of ways it should be organized.

[00:26:16] **Adam:** And so this, this is very fresh, right? I just kind of had this thought like midday today. It's like, well, what if we could for lack of a better word, I'm just gonna plug in LLM here. You tell me if there's maybe a better tool available, but. What if I could say like, have a system prompt that says, okay, these are all the designations that are available.

[00:26:34] **Adam:** This is what I know about them, right? This one is part of this school and it, it's this many dollars behind its goal or whatever. And you know, maybe there's some other interesting metadata that I can provide about each one. And then. We provided, I hate to call it a chat interface, but some little way, like a sort of an interactive search where they could specify like, okay, tell me what you're looking to give to, and if you just say like a fund name.

[00:27:02] **Adam:** Then I'll say like, did you mean this one? And or I want it to say, did you mean this one? Okay. You click on it and boom, you've selected the thing. You can specify your dollar amount, put in your address and your credit card info and you're done. Or if you're like, well, I don't really want know what, I wanna give it to you.

[00:27:15] **Adam:** Like I can. Have the LLM or the, the AI tool provide, a very donor-centric, right? Like how do you wanna look at the data, right? What, how do you wanna make

[00:27:26] **Adam:** your

[00:27:26] **Tim:** would you, would you like to support, like something that's really, that needs immediate help right now? Or is there a certain passion that you know, you wanna.

[00:27:34] **Adam:** right?

[00:27:34] **Tim:** Yeah. Yeah. I, I like that. I don't know how you do that,

[00:27:38] **Adam:** Yeah. There's a big, big old question mark for user

[00:27:41] **Tim:** 'cause, 'cause I mean, it's all about making sure that the, the context window that, that you have for the AI knows everything about, you know, the organization. That'd be a fun prompt to build.

[00:27:56] **Adam:** Yeah.

[00:27:56] **Tim:** it's, I definitely think it's doable though. I

[00:27:58] **Adam:** yeah, you think so? Well, so, okay. Let's just say that that was what, kinda what we settled on. We'll, we'll call it a chat ish interface. Right. And, and the, the. User interface bits of like, how do I hook it up to, I'm sorry. No, that, that's what I kind of wanna solve for is like, okay, what, what tool do I use and how do I use it?

[00:28:17] **Adam:** Right.

[00:28:19] **Adam:** Is there, is there a tool that I can just say like, I wanna use GPT-4 oh, or I wanna use Gemini, or I wanna use Claude. Probably not Claude that's code, or primarily code. But you, you get my point, right? I wanna use this model and. I want to be able to plug in a prompt, like a, a, for lack of a better word, I'll say system prompt.

[00:28:38] **Adam:** 'cause I'm, I don't know enough about this stuff yet, but, and, and then open that up to the end user to then make use of,

[00:28:47] **Tim:** Yeah,

[00:28:47] **Adam:** want it, you know, I'm definitely gonna wanna lock it down, right? Like, you, you are not here to do math. You are not here to, you know, calculate betting odds.

[00:28:55] **Tim:** That, that's the hard part. 'cause that's what I found when I was doing the thing with the, where I would feed the information, I gave it as much information about the insurance policy that the person was calling about. But, and it did a great job if it had the information, it was very accurate on information it had.

[00:29:13] **Tim:** Right. But when it didn't have the information, AI is so people-pleasing

[00:29:19] **Tim:** that it would lie about things it could do or that it knew.

[00:29:23] **Tim:** Right. And so that, that actually, I mean, we abandoned that project 'cause I just, I really didn't see a whole lot of demand for it with our customer set. But that I, that's what I saw to the big be the big challenge was, was I had to give it all the relevant data, but then I had to put these guardrails around to say, all right, here's what you know.

[00:29:46] **Tim:** Here's the things you shouldn't ever do, right? And, and, and thinking creative, and you don't know until you expose it to actual human beings what people are gonna ask. So it's like, yeah, I can sit here and think, okay, 50 things that you shouldn't do, and then I start watching people use it. I'm like, oh, I never thought about that.

[00:30:06] **Tim:** Right? So that, I think that's the challenge right now with that is, is keeping AI from being overconfident about what it knows and what it doesn't know.

[00:30:13] **Adam:** I think, you know, if we do go down this road, I'm definitely gonna have to set aside some money to like pay somebody to red team it and, and really see what they can get it to do.

[00:30:23] **Tim:** Yeah. So it's, it's like a recommendation engine. And I think, I mean, those have been around for a while, right? So it's like you put in, you, you wanna find a, a good restaurant, so you, you know, you say what you're looking for, price range. And they, it's a recommendation. And some of that was literally done before ai, but. I think AI could, this could be a good use for this. This would be interesting. That'd be a fun one.

[00:30:44] **Adam:** Thanks, you've, you've been very helpful.

[00:30:47] **Tim:** I, I, I don't have any good answers. I mean, I'm, I, my, my, my big experience with that was, like I said, where you basically feed a bunch of policy data toward a person. But, and, and the main, the, the big challenge was stopping it

[00:31:00] **Tim:** when it didn't know something.

[00:31:02] **Adam:** Yeah.

## [00:31:02] Exploring AI Tools and AWS

[00:31:07] **Adam:** I guess my next steps are probably gonna be, because I'm lazy, I'm gonna ask an LLM what, uh,

[00:31:08] **Tim:** right.

[00:31:09] **Adam:** what tools I should use and stuff. And then I'll start digging around like, I'm sure that AWS probably has like this as a service that I could just use. That would be nice, but.

[00:31:19] **Tim:** What, what, so what A AWS, what is their AI engine?

[00:31:24] **Adam:** Honestly, I don't know. I don't think that, I haven't heard that they have released any specific models of their

[00:31:29] **Tim:** Seems odd. It seems like everybody's in that game now.

[00:31:32] **Adam:** Yeah, that's a really interesting point. They're like the biggest player that doesn't have an AI model that I can think of here.

## [00:31:39] Amazon's AI Models

[00:31:44] **Adam:** Let's ask chat, GPT. Does Amazon have. Its own AI model that they've released.

[00:31:49] **Adam:** See, you don't even have to ask good, like well phrased questions. No, it says a Amazon does have its own AI models. They introduced a, a model named Nova, which is designed to answer the, it is designed to enhance the efficiency of its robotic fleet.

[00:32:05] **Tim:** Oh, but that made, that doesn't sound useful for what you're doing.

[00:32:08] **Adam:** no.

## [00:32:09] Robots in Amazon Warehouses

[00:32:09] **Tim:** I was reading an article that that AI robots are gonna, are now outnumber the actual human beings working at Amazon delivery warehouses.

[00:32:19] **Adam:** Interesting,

[00:32:21] **Tim:** So robots are doing half the, more than half the work.

[00:32:24] **Adam:** huh? That's, I don't know how I feel about that.

[00:32:27] **Tim:** I don't either. It, it's, it's the question that I, I use to put my auditor off. PCI auditor off, like, how does capitalism work when no one has to work? How does I, I dunno how that works.

[00:32:38] **Adam:** Well, somehow the billionaires will continue to get richer.

[00:32:42] **Tim:** For sure. So all just have to live off their, they give us handouts.

[00:32:47] **Adam:** Okay.

## [00:32:47] Wrapping Up the Episode

[00:32:47] **Adam:** Well, I'm trying to think, is there anything more to say about on this? Yeah. All right, well then why don't we, yeah, why don't we wind this up and, uh, and we'll just go ahead and move on to the extra, it's, it's not bad. Little 30 minute episode.

[00:33:00] **Tim:** We didn't have Ben here to, to side Quest us

[00:33:02] **Adam:** no tangents.

[00:33:03] **Tim:** No tangents on top of tangents.

[00:33:05] **Adam:** poor Ben. He's out

[00:33:06] **Adam:** people-ing,

[00:33:07] **Tim:** I love Ben.

[00:33:08] **Adam:** All right.

## [00:33:09] Patreon

[00:33:09] **Adam:** Well then this episode of Working Code is brought to you by. PA Renaissance Fair, go there and spend money and make sure that my daughter stays employed, uh, and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on.

[00:33:26] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. It, it really does feel like we're finishing super early tonight. I know we like, you know, this is roughly half of our usual length, but man, like the, the sun's still shining.

[00:33:44] **Adam:** Hey, I'm ready to get the 4th of July on. Got some beers and some grilling and some swimming. Let's

[00:33:48] **Adam:** yeah, buddy. It. Yeah, it's just, I think especially with just the two of us, it, it just, it flew by anyway.

## [00:33:55] Thanks for Listening!

[00:33:56] **Tim:** Uh, we're gonna go record the after show. Tim and I are gonna talk about, uh, Dennis e Taylor's new book. the bob over guy.

[00:34:02] **Adam:** Yeah, and, and, uh, I told you I'd talk a little bit more about the pa Renn fair stuff, so my daughter working there.

[00:34:08] **Adam:** So we'll get into that if you would like to get that and early access to new episodes and,

[00:34:15] **Tim:** And to get the the PPP joke.

[00:34:19] **Adam:** And, and, you know, all kinds of other fun stuff too. You get a special role in our Discord, which grants you access to some secret rooms where we discuss the new episodes when they come out early and stuff. you know, it's real easy.

[00:34:29] **Adam:** You just go to patreon.com/workingcodepod, throw a few dollars hour away. it's even cheaper, right? So the, I think the minimum is $4 a month, but you can, if you pay for a year at a time, it can be even cheaper than that. so we'd love to have you help out the team and, and, uh. We hope you do that. anyway, uh, that's gonna do it for us this week.

[00:34:48] **Adam:** We'll catch you again next week and until then,

[00:34:50] **Tim:** Remember, living off your teet is a treat and your heart matters.

[00:34:56] **Adam:** okay.was that directed

[00:34:58] **Tim:** It was a

[00:34:59] **Adam:** Mr. Musk directly?

[00:35:01] **Tim:** No, no. I don't

[00:35:02] **Adam:** Is he a listener? If he is, he better be a patron.

[00:35:05] **Tim:** he's like a $4 Patriot. He's a cheaps skate.
