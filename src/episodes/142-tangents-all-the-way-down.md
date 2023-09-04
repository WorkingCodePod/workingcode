---
title: "142: Tangents All the Way Down"
description: "When Carol's not here to keep us in line, the show quickly flys off the rails. So much so, in fact, that we never made it to the intended topic - it's just tangents upon tangents upon tangents."
date: 2023-08-30
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/142-tangents-all-the-way-down/id1544142288?i=1000626193080"></iframe>

When Carol's not here to keep us in line, the show quickly flys off the rails. So much so, in fact, that we never made it to the intended topic - it's just tangents upon tangents upon tangents. We touch upon "vendoring" of our external libraries, installing dependencies with `apt-get`, dictation app differences between macOS and iOS, the regret of not building features sooner, building the perfect demo for clients, and the "trap" of having to innovate. And that's _not even_ everything! Carol - we need you! You're our only hope!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/142-tangents-all-the-way-down.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** I will correct myself. I am sorry. He is not, he was not fired. He's part of a workforce reduction slash layoff, but obviously he hasn't signed anything yet. So he's actually not fired. He's actually still a full time employee right now. So I, yeah, I don't know what he

[00:00:16] **Ben:** I'm like a Schrodinger's employee,

[00:00:19] **Tim:** exactly exact. That was, I was going to say the exact same thing.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go to show number 142. And on today's show, we're going to talk about moving, and that's going to go in a bunch of different directions. Carol is not with us tonight. She's got an excused absence because she is, wait for it, moving. Without further ado, let's start with our triumphs and fails.

[00:01:01] **Adam:** We've got the rest of the crew here. It looks like it is my turn to go first.

## [00:01:04] Adam's Triumph

[00:01:04] **Adam:** I'm gonna start us off with the triumph. I got a compliment today from a co worker about,my solution to a problem we had.

[00:01:12] **Adam:** I almost said like about code I wrote. It wasn't a hundred percent about code that I wrote, but it was about a solution that I, I, a code, adjacent solution that I came up with. So I guess I'll give you a little bit of a backstory. So we have this tool where our customers can upload an Excel file and we import that basically into a table of data for them, right?

[00:01:31] **Adam:** That's a pretty standard feature. And in order to increase performance and detach it from the main thread, that sort of thing, we do it using a Lambda function instead of like inside of the Lucy monolith and so it depended on this NPM module called Excel Data, and that module just decided to disappear from the internet.

[00:01:58] **Adam:** It's like it was not there at all. It just, it got unpublished as far as I can tell. Like it was there, we had been using it for years, and it's just... Gone now, totally ghosted. It's not on the guy's GitHub anymore. It's not on NPM. There's like zero record of it. So I looked up the, yeah, it's crazy.

[00:02:15] **Ben:** yeah, I thought NPM wasn't allowing people to do that anymore.

[00:02:18] **Adam:** looked into it. their official policy is in very narrow circumstances, you can unpublish your module from public, right? So you have to be the only owner slash maintainer. it has to have gotten less than 300 downloads in the last week at the moment that you want to unpublish it. And. no public projects can depend on it.

[00:02:42] **Adam:** No, like other NPM dependencies can depend on it. But if you have a private project, like your, your business that depends on this module, you know, pound sand, who cares? And like, I get it, 300 downloads a week is, when you're talking about the NPM ecosystem, it's not a high bar to cross, right? Obviously, there's something else out there that people are using or something.

[00:03:03] **Adam:** We found a ton of Excel related modules, but like 99% of them are generating Excel, and we're doing the opposite. We're trying to consume Excel, XLSX specifically. and... The others that are like, maybe this might work. You go look at the readme and it's all in like, Chinese. Like, I, I

[00:03:26] **Tim:** Actual Chinese or?

[00:03:28] **Adam:** well, you know, it's in those symbols.

[00:03:29] **Adam:** Like, me personally, I can't tell the difference between Chinese, Japanese, you know, Cantonese, whatever. But like,

[00:03:35] **Tim:** Non Latin characters.

[00:03:36] **Adam:** for sure. And it's not like Cyrillic or something, right? It's, it's, it's definitely

[00:03:40] **Tim:** Because you could read

[00:03:42] **Adam:** Well, don't tell Putin,

[00:03:46] **Ben:** to each other.

[00:03:48] **Adam:** yeah, so, anyway, I actually kind of, to me, I was a little taken back by this compliment that I received because to me, the solution seemed a little on the obvious side.

[00:03:57] **Adam:** and so not to toot my own horn, just, I want to kind of use you guys as a sounding board to see, how obvious the solution actually is. So this, this NPM module disappeared. And we can't just take time out of our lives to go find a replacement and rewrite the tooling to use it. So how would you solve this problem?

[00:04:20] **Tim:** mean, do you have a local NPM somewhere? A copy of it? Stand up like a mirror of it?

[00:04:27] **Adam:** So we do have it downloaded locally. like, you

[00:04:30] **Tim:** a local

[00:04:31] **Adam:** our local development environment, what's that?

[00:04:33] **Tim:** can't you create a local package management thing to serve it out?

[00:04:36] **Adam:** That's what I did.

[00:04:37] **Tim:** Yeah. Cause we, we sort of have the same. So in our PCI environment, we're not allowed to like getting Lucy packages is extremely hard. So we basically have created our own local package manager that's outside of it.

[00:04:50] **Tim:** That then we create a whitelist to it. It's a, it's a whole mess. So, which is the only reason I even thought of that.

[00:04:56] **Adam:** Right. Yeah. So we, we do have a number of private packages that we published, not even on like, so NPM has like a premium thing where you pay extra, you get a private organization, you can publish stuff to NPM proper, like it's on their same environment as all the public stuff, but it's, it's invisible to people that aren't in your organization.

[00:05:17] **Adam:** We don't use that. We use GitHub's offering, which is very similar. You just have to like add a configuration file that says, okay, this organization name, they're like, at AlumniQ. Means go look in, the, the repository for that is over here on GitHub instead of on NPM. and so we, we've got a bunch of modules that are there.

[00:05:36] **Adam:** So I literally just took out of my local dev environment, my copy of this module, the, the, you know, I went to node modules, Excel data, copied everything out of that folder, created a new project in our GitHub organization, called it Excel data, copy and pasted all the content in, changed the package JSON.

[00:05:53] **Adam:** So now it's like AlumniQ slash Excel data. you know, made a couple, just the, the minorest of changes to make it possible to publish this to our package repo. Did an npm publish, updated the project to, to pull from at AlumniQ slash excel data. Gets to change the require statement that's pulling it in, and, and it just worked.

[00:06:12] **Adam:** And so, I, okay, I'm, I'm kind of glad to see, Tim, that you thought of that almost instantly. You know, cause to me, like I said, to me, that was an obvious solution. I was like, okay, that's, this is just the easy thing to do.

[00:06:22] **Tim:** It's just a delivery mechanism. We don't have to reinvent everything here. Yeah.

[00:06:27] **Ben:** Yeah, see, my mind immediately went to much more complicated solutions, like could you somehow spin up OpenOffice and create a Docker container for that or something? I don't know. Maybe there's some sort of Docker container that does this kind of stuff, but definitely publishing the package itself is way much, way more simple.

[00:06:46] **Adam:** You're a try hard Ben.

[00:06:49] **Ben:** Cause I, you know, I've never done a private repository for, or private package for node modules. I'm not super embedded in the node systems. So that

[00:06:58] **Adam:** Yeah. If you don't have experience with it, it's, it's excusable to not

[00:07:02] **Ben:** there you go, much appreciated, much appreciated.

[00:07:05] **Adam:** You're excused.

[00:07:06] **Tim:** I'm just glad I got it. I was like, Oh, I'm going to kind of eat it here. I'm pretty sure.

[00:07:10] **Adam:** No, man, you were right about, see, that's the obvious solution. I don't know what anybody else is thinking about on my team, but I was just like, it literally took me like 10 minutes. Like, okay, I'll just do this.

[00:07:18] **Tim:** Yeah.

[00:07:19] **Ben:** You know, part of me often wrestles with the idea of just, we use the term vendoring, I don't know if that's a widely used term, but

[00:07:28] **Adam:** That's

[00:07:29] **Ben:** taking what would ordinarily be an external module and committing it to your code source. Yeah, I often kind of wish we did that with more things. If for no other reason, I sometimes find the NPM install step of a build process to be the slowest part of the entire build.

[00:07:50] **Adam:** Yeah, it can be for sure.

[00:07:52] **Ben:** And to, if we could somehow just completely get rid of that and make that part of the Git pull, that'd be awesome.

[00:07:59] **Adam:** It's a trade off though. I mean, you're right. It can be super slow and annoying, but like the trade off, if you're going to, you know, commit your node modules to the Git repo, then you're adding, you know, whatever, 200 megs of crap that's getting downloaded every time anybody does a pull or, you know, that sort of thing.

[00:08:18] **Ben:** Yo, can I side rant for a second on package managers?

[00:08:20] **Adam:** We don't do that here.

[00:08:22] **Tim:** He does. He does all the time.

[00:08:24] **Ben:** Heheheh. So, I know very little about package managers. And certainly I know next to nothing about package managers outside of the Node ecosystem. And, recently we had to upgrade a version of Lucy that we were using at work. And if you think about the Docker file that outlines how the Docker image is going to get created.

[00:08:45] **Ben:** The Lucy part is the very first line in the entire Dockerfile and everything else comes after that. So if you change your base image, essentially it invalidates everything else, which means that you lose all of the cached layers from the Docker build, which usually is not a problem, except for it takes a little bit longer for the next build.

[00:09:07] **Ben:** But in my case, it was hugely problematic because at some point after that base image, there were a bunch of apt get and apt install or apt get install calls. And I don't really know what apt get is. From what I've been told and what I've seen, it's basically the package manager for Debian and, and Ubuntu. but it, it, it seems to be just a god awful package manager, and I don't know if, I just don't have any experience with it. It's horrible. First of all, it's almost impossible to find a list of things that are actually available if I just Google for, like, show me the list.

[00:09:48] **Tim:** lists,

[00:09:48] **Adam:** you're standing on the shore of the beach saying, show me the water,

[00:09:54] **Ben:** No, but then,

[00:09:55] **Tim:** right?

[00:09:55] **Ben:** but then it gets crazy too. So the problem is, is that one of the cache layers that we have in our apt get install is from, from like a 0. 97 version of some library. And when I go to invalidate it, none of our versions were pinned. It's all just like install Redis, install this, install that, you know, none of them are at versions like you would.

[00:10:15] **Ben:** Typically having a node lock file or a yarn lock file.

[00:10:19] **Tim:** It's getting the latest and

[00:10:20] **Ben:** Yeah. So it's getting the latest and the latest version was like five point something. Yeah. So I went from a zero point something to a five point something in one particular library and it, it completely broke. So I'm like, okay, I had to, first of all, just figuring out how do you pin the version of a package in apt get?

[00:10:38] **Ben:** It's like, you literally can't find that on the internet. I don't know if I'm just. Googling for stupid things, but I finally had to ask people at work and they just said, Oh, it's just package equals version in your, in your list. So I said, okay, great. So I do, it was rdiff is the library we were looking for.

[00:10:52] **Ben:** So I said, rdiff equals 0. 97. And then it says, Oh, that package doesn't exist anymore at that

[00:10:59] **Tim:** There's a, there's a mirror somewhere. There's always a mirror.

[00:11:01] **Ben:** But I'm like, that's such BS. Like the whole point of the package management is so that you don't have to worry about crap like this, like it should just work. And then I was starting to, you know, Google for how do you get older versions of stuff, which again, maybe I'm just an idiot and I don't know how to Google.

[00:11:18] **Tim:** no, this is why Linux hasn't taken over. Stuff like this, honestly.

[00:11:23] **Ben:** even just figuring out how to pin things and how to get older versions. Like nothing was coming up except like, like, like, not stack overflow. It was like, you know, server, server overflow or like server. Serverfault. Yeah. Like, I didn't even know that. I don't even know what that is or why it still exists.

[00:11:40] **Ben:** And they were like, Oh yeah, we only keep like the last one or two versions of stuff in the, in the master list of all the packages. I'm like, it's just, it's bonkers. It's bonkers that that's how they're running it. It's crazy.

[00:11:52] **Tim:** They think, they think it's bonkers. You're running a 0. 5 version. Let's be honest.

[00:11:58] **Adam:** yeah. so much, so many different ways I could take this. The, the,

[00:12:04] **Tim:** That's a lot to unpack.

[00:12:06] **Adam:** like it's so many things I forgot. Jesus.

[00:12:08] **Ben:** like, could you imagine if you just went to install a version of a node module and they were like, Oh yeah, that's just not supported anymore. Constantly, you know, it's one thing to do it where someone actually unpublished something, but. Oh,Axios version four came out, so we just don't even expose version three anymore.

[00:12:26] **Adam:** Yeah, I, I, I think, well, so, okay, there's two things immediately top of mind, I'm going to say them both up front so that I don't forget, that's not how people used to use Linux for the longest time and then, storage, right? So, we'll do the first one first, and remind me storage if I forget, the, you know, Linux has a thousand years of history of people like trying to make it work as a workstation slash server, but it's always been the like pet configuration as a server, right?

[00:12:54] **Adam:** You know, the, the whole concept of cattle type servers, is probably, I don't, I don't know for sure when it was born, but I'm guessing it's within the last 10 years. You know, or, or at least close to that. So there's a limited history, especially compared to the, like the, the history of the internet begins kind of with Linux stuff, right?

[00:13:16] **Adam:** So like the, the span of, the history of the of Linux history on the internet is the span of the history the internet. And so,

[00:13:24] **Adam:** I'm not surprised that there's not a lot of well organized information on how to do this kind of thing because nobody, when they're trying to set up their server is like, oh yeah, I want to go download Redis version 0. 2, right? They're like, just, I want the current version. it makes a ton of sense in today's environment where you're like, okay, I need this specific version because I rebuild my server 120 times a day and I want it to be this specific version every single time.

[00:13:49] **Adam:** And so there's, like you said, there is a way to do it, but it's, not obvious and not well documented, I guess. I will say, let me throw this in there in the middle, apt get is my favorite of the Linux package managers. I, I never got

[00:14:02] **Ben:** terrible. Is

[00:14:02] **Tim:** yum. Yum is

[00:14:04] **Adam:** yum and, and, what was the other one that I was trying to think of?

[00:14:07] **Adam:** I don't know, whatever the,

[00:14:08] **Ben:** for Python, right.

[00:14:10] **Adam:** that's pip, but that's not Linux. That's, that's

[00:14:12] **Ben:** Okay. That's specifically Python.

[00:14:14] **Adam:** Yeah. Like it's, it's the NPM to Python.

[00:14:17] **Ben:** Gotcha. Okay.

[00:14:18] **Adam:** anyway. So storage, you know, like I was saying, you're, you're standing on the shore of the ocean going, show me the water. Well, there's like a bajillion pack versions of a bajillion packages out there.

[00:14:27] **Adam:** Like it's got to cost an insane amount of money to store and make, available all that stuff and make the, the, what do you call it? Whatever the services that are exposing that the registry performant to, you know, okay, you want to go dig up a specific version of a specific package that nobody's touched in the last eight years,

[00:14:46] **Ben:** Hmm. Yeah, that's true. I guess I didn't really think, because, you know, it is, is like, I don't understand how the, the technical implementation. Of a package manager. I don't understand how that works. I mean, you bring up storage and cost. I don't know how NPM does it. I mean, they must have a massive amount of

[00:15:02] **Adam:** They're VC funded.

[00:15:04] **Ben:** Are they?

[00:15:05] **Adam:** Yeah.

[00:15:06] **Ben:** That's how you, that's how you gotta do

[00:15:07] **Adam:** now they have like premium stuff. Like I was talking about earlier.

[00:15:09] **Tim:** yeah, I don't know. I feel like there was something else I wanted to say about package managers, but we can move on.

[00:15:14] **Ben:** Yeah.

[00:15:15] **Adam:** We'll move on.

[00:15:17] **Ben:** Love it.

[00:15:18] **Adam:** Okay, perfect.

[00:15:18] **Adam:** So, that's me. How about you, Ben?

## [00:15:21] Ben's Triumph and Failure

[00:15:21] **Ben:** I want to go with a failure and a triumph mostly. 'cause I don't wanna just have a failure. my failure this week is that my repetitive stress for my arms, my wrist and forearms has just been really, really aggravated the last couple of weeks and has really ramped up. and it's a little terrifying because this is what I do for a living and feeling pain when I do that thing is, is very scary.

[00:15:48] **Ben:** and I've been icing my arm a lot. I found that if I cut, one of my socks in half, so it's just a tube. Basically, like I cut the foot part off and then I have the leg part. That's the tube. I can put that around my arm and I can put an ice pack under there so I can hold the ice pack to my arm while I'm typing or just while I'm laying in bed, watching TV.

[00:16:06] **Ben:** And

[00:16:06] **Adam:** I don't know if this is a big or brag that you're. Your arms are as big as your legs or that your legs are as big as your arms?

[00:16:12] **Ben:** Oh, it's

[00:16:12] **Tim:** elastic. It's

[00:16:13] **Ben:** Yeah, yeah, yeah, yeah. and that's been helping and I've been doing some stretches and, and some PT, some physical therapy kinds of exercises. But, it sucks. It sucks, and it's really scary, and, I'm hoping that really what it is is just stress from work has, like, flooded my body with cortisol and other stress hormones, and that's just throwing everything out of whack, including, including my wrists, so I'm hoping that...

[00:16:39] **Ben:** When the stress of work and employment, when that settles down a bit more, then I think my body will hopefully just bounce back because I have not really been doing anything unusual.

[00:16:50] **Tim:** Well, fortunately Copilot has your back.

[00:16:52] **Ben:** Well, so, okay. So that, that brings me to another point because I thought to myself, Hey, I've been trying more and more to use the dictation feature on my iPhone on the bottom of the keyboard, the virtual keyboard, this little microphone, you hit it and you can just dictate into your text messages, which is really where I use it.

[00:17:09] **Ben:** And it's really, really good, the dictation on the phone. It's like spot on, it'll go back and it puts in the right, punctuation and it'll capitalize things and it'll change words. As your sentences are getting fleshed out and it like realizes that it didn't interpret something properly, it go back, it'll go back and fix it automatically in a lot of cases.

[00:17:27] **Ben:** Anyway, it's really impressive. so I'm like, Oh, you know what? The Mac probably has that also. And there is in fact a dictation feature on the Mac. If you go into the keyboard settings in the, in the keyboard preferences, and you can turn on dictation. But it's awful. It's so bad. It will, it will literally, so I'm, I'm watching it as it's transcribing what I'm saying and I'll see it start to type out exactly what I just said, and then it'll just erase the last three words. And then it'll just pick up where I left off, missing things. It's constantly missing punctuation. I'll say something to myself like, oh, it isn't clear in my mind. And when it hears the word clear, it just completely clears all of the text it just transcribed. And I, I don't understand, I assumed it would be the exact same product, but apparently it is not the exact same product.

[00:18:22] **Ben:** And the one on the Mac is just awful. And I was, I was hoping I could use it to reduce some of the typing that I was doing in emails and Slack, but

[00:18:29] **Adam:** okay. I was gonna ask are you trying to use this for code

[00:18:32] **Ben:** no, no, no. But I thought, you know, every little bit might count.

[00:18:38] **Tim:** Because what someone on our Discord was talking about, they posted a link to Copilot Voice,

[00:18:44] **Adam:** Mm hmm.

[00:18:45] **Tim:** which is a new product they're launching that you can, if you're already on Copilot, you can sign up for it where you just speak and it will, you know, you speak the code and it. Ushers forth like you're a wizard or something, off to be the wizard.

[00:19:01] **Tim:** But, yeah, I was like, my response was like, oh my God, I don't even want to talk to people during the day. Why would I want to talk to my computer? And he's like, well, you know, I, I just, I'm just glad to know that if something happens to my fingies, I can still do my job. I'm like, okay, that's, that's a legitimate concern.

[00:19:15] **Ben:** So, so that's my failure, but I do want to just close out with a small triumph here, which is as we discussed on last week's episode. My employment at Envision has, I don't want to say ended, but it's come into question. I've been, I've been redundant, redundantized from a full time employee to at least a part time employee, but I'm still waiting to hear details on what that actually means.

[00:19:40] **Ben:** And it's, it's been a bit of a frustrating that I feel like I'm hanging

[00:19:43] **Adam:** been like a whole week now.

[00:19:44] **Ben:** Yeah, it's, it's a little frustrating and it, but my triumph is in this fog of war, I feel like I'm still doing my best to stay motivated at work and figure out what I can do to improve the product and make a better customer experience, hopefully.

[00:20:04] **Ben:** I know that there are certain things that I can't do in my state of mind. Like, it's very hard for me to think long term, how can I radically improve a feature or how could I create a new feature? Like my brain, my brain's just not there right now.

[00:20:17] **Adam:** Yeah, you're not gonna take on a project It's gonna take six weeks.

[00:20:20] **Tim:** hmm.

[00:20:21] **Ben:** like, my brain won't even let me think about that without freaking out.

[00:20:24] **Ben:** So I'm trying to focus on cleaning up tasks. Like what, where's the baggage that I can remove from the application? Where's some of the older, cruftier technologies that I can replace with some, maybe newer stuff. And I'm, I'm at least proud of myself that I am continuing to put one foot in front of the other and maximize whatever time I have left.

[00:20:46] **Ben:** I know that one option would have been to just. Watch YouTube all day. And, you know, no one at work would have batted an eye, honestly. but I'm not

[00:20:56] **Tim:** a good mindset, that's a good mindset. Although I have to say, when you first started saying that, I was like, my image was of the meme of the dog with the hat and the flames in the background and going, this is fine, this is fine. He's just doing his work, he's calm, he's like, this is fine.

[00:21:14] **Adam:** Did you work 40 hours this week Ben?

[00:21:16] **Tim:** Does he

[00:21:17] **Ben:** I mean, I'm, I'm technically still a full time employee until I sign a contract, I think, that says I'm not. Which, you know, I expected, I expected last week. So I'm, they keep saying that they're figuring out what, what the contract should look like.

[00:21:32] **Tim:** maybe it'd be like office space and they just never fixed the glitch. Carol, that's a movie reference. When you, when you, when you read this back on the transcription.

[00:21:45] **Ben:** Anyway, so I've, I've taken up enough of our time.

[00:21:48] **Tim:** No, no. So I got to say though, I got a lot of flack in last week for saying that you got fired, our, our, our listeners like, no, he didn't get, I mean, cause it's like, to me, it's like, you have a job where you don't have a job. It's like, you know, are you getting a paycheck or not? Doesn't matter. You call it laid off or whatever, but okay.

[00:22:08] **Tim:** I will correct myself. I am sorry. He is not, he was not fired. He's part of a workforce reduction slash layoff, but obviously he hasn't signed anything yet. So he's actually not fired. He's actually still a full time employee right now. So I, yeah, I don't know what he

[00:22:25] **Ben:** I'm like a Schrodinger's employee,

[00:22:27] **Tim:** exactly exact. That was, I was going to say the exact same thing. He's in that quantum's entanglement right now with his employment.

[00:22:38] **Ben:** I remember back when, when I went to Scotch on the Rocks conference, which I think was in like 2008 or 2010. I mean, it was a long time ago. I had never heard the term redundant before. I guess that's a European term,

[00:22:52] **Tim:** Yeah. Yeah. Yeah.

[00:22:53] **Adam:** as a In the context of being

[00:22:56] **Ben:** of being employed.

[00:22:57] **Tim:** Let go, yeah,

[00:22:57] **Ben:** And I remember one guy I was talking to at the conference. Was really upset that he had been made redundant in work.

[00:23:03] **Ben:** And I was like, why are you so upset? Like, so they brought in some other people who do the thing that you do. Like, I didn't realize he meant that he no longer had a job,

[00:23:17] **Tim:** yeah, it's, it is sort of like a, a weird way to say it made redundant. It makes it sound like, you know, someone else is doing your job, but if you're like basically cutting the company down, like 80%, you're not redundant. There's no one taking your job. You're gone. And they're not filling that position anymore.

[00:23:39] **Ben:** Alright, well, normally I would go to Carol, but as Adam mentioned at the top of the show, Carol is currently moving, hence the topic of the show, so I'm gonna go over to Tim. What do you got going on?

[00:23:52] **Tim:** Good luck, Carol moving. Hopefully you don't use pods again. Um,cause that was not sponsored and they probably will never sponsor us now. yeah, I hope everything goes smoothly with your move out to Arizona.

## [00:24:06] Tim's Triumph

[00:24:06] **Tim:** So for lack of a better, I'm going with a triumph. I mean, we're adding new product features. I kind of feel disconnected from it.

[00:24:13] **Tim:** Cause all I've kind of done is like come up with the ideas and add, you know, add the product features and they're getting built and I check in on it and they're doing great customers looked at it. We've demoed it. Things look great. yeah, so it's like, it's, it's nice when you add new product features and you're like, why didn't we add this sooner?

[00:24:30] **Tim:** That's, that's kind of my thing. Well, I mean, this was so easy. Some of the stuff we're adding, it's like. People kind of asked for it. And I thought, eh, I never really, but you know, we created it. I'm like, now that I see it in practice, I'm like, wow, this, and this is kind of what we talked about last time about building the thing to build the thing, we, we did that after we built it.

[00:24:52] **Tim:** I'm like, you know what, this actually, we can sell this, this could be a product in itself. It's, it's, you know, another extra tool.

[00:24:59] **Ben:** Cool.

[00:25:00] **Adam:** bread.

[00:25:00] **Tim:** So yeah, it was like, you know, we need to keep doing more of this kind of stuff. So it just feels good when you add new product features and you get good feedback on it. hopefully it leads to some sales.

[00:25:11] **Tim:** We'll see. right now we're doing it for a customer that's a new customer. It's sort of a slightly, we mostly have dealt with property casually, you know, insurance, kind of the, insurance of covering things and this is workers comp. And so they have sort of a different use case with stuff. so with payments, so attacking that thing for them, it's like a whole new kind of, customer base we can go after.

[00:25:35] **Tim:** So yeah,

[00:25:36] **Ben:** That's exciting.

[00:25:37] **Adam:** yeah, it's looking positive. So, but, and it was super easy, barely any inconvenience. that's a YouTube reference. didn't get it.

[00:25:45] **Tim:** it's, it's so sorry. So side rant. So there's a YouTube channel called, Meeting. So it is basically, it's a guy, he does this thing where he pretends to be a guy pitching the movie to the studio executive and

[00:26:01] **Ben:** I like it. I can see where

[00:26:02] **Tim:** yeah, and every single time it's like, he'll come up with a plot point that actually makes no sense.

[00:26:08] **Tim:** The guy, the executive's like, wow, that's going to be really hard for them to get off. And he'll be like, no, super easy, barely an inconvenience. And. It was just true. Cause typically there's always some point in the movie, it's like, how do they get out of that? That's just stupid. But anyway, yeah. So my point is that the product features we were building really worked that hard.

[00:26:30] **Tim:** And I'm like, why didn't we do this sooner? We should have done this sooner. We could have been selling this, but I didn't know. There was a use case there. So once you find the use case, you gotta.

## [00:26:41] Feature Development

[00:26:41] **Ben:** I always felt like there should be more engineering input into roadmap decisions. I mean, obviously this is going to vary widely from company to company, but I have found at our company. It always felt like the roadmap was almost entirely product and design driven and never engineering driven. And there are so many things exactly like you're talking about that would, I think, have been huge value ads, but they were never prioritized because product didn't have any sense of how easy those things might be to build.

[00:27:16] **Tim:** I get what you're saying.

[00:27:19] **Ben:** End of conversation.

[00:27:20] **Tim:** No, no, I'm going to have to come at you at a different angle here. I've been on product a long time and development a long time. And a lot of times the stuff that I wanted to build, I built it and then no one bought it.

[00:27:32] **Ben:** Yeah, we'll add that too.

[00:27:33] **Tim:** And so now it's like, I'm more dealing with the customer a whole lot.

[00:27:37] **Tim:** And they're like. They'll tell me something and I'll, once I really understand it, and I think honestly the biggest change, cause I did sales for a while and that I didn't really enjoy that, but one thing I learned is that before you do a sales call as a salesperson, particularly when you're going from, so they're interested, they want to see your product. Now they're asking for a technical demo. one of the best things you can ask. Is to say, all right, so when we do this technical demo, what in your mind would be the best thing for you to see? And if, if you can get that information out of them to say, what we'd really like to see is to be able to do A, B, and C, and then move money from this point to this point, and then at the end, we get the report that looks like this. Sounds super simple, but those questions, honestly, in the past couple of years have been so informative that now I go back to the engineers and say, here's what they want to see, because a lot of times just you tell a person a problem and they build, they build a solution that doesn't necessarily do the story that the customer wants.

[00:28:48] **Tim:** They build the story that they think they want. and so that, that has honestly made the biggest difference in the past couple of years of just asking that question before any, I won't, I won't do a demo anymore, unless I know that either myself or the salesperson has asked that question of what is it you're wanting to see?

[00:29:07] **Tim:** Describe to me the perfect demo for you.

[00:29:10] **Ben:** I

[00:29:11] **Tim:** then, and then you can,

[00:29:12] **Ben:** standpoint, especially,

[00:29:14] **Tim:** right. And then sometimes you'll, you'll find out like, okay, you asked for a perfect demo, we maybe do 60% of that. And you just tell them up front, look, so we can show you one, two, three, four, but we're not going to show you five, six, and seven because we, you always say that's on our roadmap.

[00:29:30] **Tim:** Right?

[00:29:31] **Adam:** yeah,

[00:29:32] **Tim:** That's our roadmap. And then you actually wind up eventually working on that. And then you go back to them, you know, cause a lot of times it takes a long time to make a sales decision. You come back to them and say, all right, so last time we showed you one through whatever. Now we've done this. Now, we think we've done your perfect demo.

[00:29:48] **Tim:** If we show you all those things. Would that be like the perfect demo for you? And then by that time they probably have some other stuff they want to add, but whatever, it's kind of rid of, but you're getting closer and closer to their dream goal.

[00:30:02] **Adam:** I mean, that, that ties in nicely. I was going to say, like, when you're going to, if you're going to ask those questions to, to prepare for a sales meeting and demo, you have to be really honest with yourself and not say, show me what you want to, or tell me what you want to see so that I can go make, you know, mock ups that don't actually have any functionality to just do what you want to see so I can make the sale.

[00:30:21] **Adam:** And then it's somebody else's problem to build it and make it work. You have to be honest with yourself, like, can we actually do this? Is this a reasonable thing to add to our product? Is it germane with our vision for the future of the product?

[00:30:32] **Tim:** And sometimes, honestly, we, we have done an,MVP, like, like, well, give us three to four weeks and we'll, we'll show you that demo. And you actually do kind of somewhat prototype it and build it. And then the contracting terms, they always take a long time. So in the meantime you build it, but you know, sometimes it's a much bigger ask.

[00:30:50] **Tim:** And you're like, okay, well, we can't do that now, but can we check back in with you in six months and show you that? You know, will we be out of the deal if you do that?

[00:30:59] **Ben:** so with all my work stuff, I've been doing a lot of reflecting and a lot of looking back at decisions that I've made in the past and things I regret, things I'm proud of. Got to update that LinkedIn profile. and.

[00:31:13] **Tim:** What's LinkedIn?

[00:31:16] **Adam:** That's where olds go to find work.

[00:31:18] **Tim:** Yeah.

## [00:31:19] Innovation

[00:31:19] **Ben:** and I keep, for whatever reason, this phrase keeps popping into my head and it's, I think it's often attributed to, Henry Ford, although I think maybe there's, I don't, he may have never said it, which is that,

[00:31:29] **Adam:** If I asked people what they wanted, they would have told me a faster horse.

[00:31:32] **Ben:** Right, exactly. And I think that gets thrown out there a lot because I think product teams want to think like one, that we're constantly have to be making these massive innovations in order to be adding value to people's lives.

[00:31:48] **Ben:** And then two, our insights into the product are just better than the customer's insights into the product. And I'll tell you, if I've had one really big regret, it's that I think. Maybe I allowed that story to play out too much at the company. were so many times where customers came to us with actual points of friction that they were having on a daily basis.

[00:32:16] **Ben:** Hey, I want a button to do this. Hey, there's a bug here that should be fixed. And we just like blew it off. And we're like, that's just not important to us, like, we have to be innovating in these big product areas and these little frictions that you're having just. They're just not important. And, you know, maybe I'm being a little overly flippant about that, but

[00:32:37] **Adam:** Be careful, you're still technically employed

[00:32:41] **Ben:** yeah. but I don't know. I just, I'm, I'm hearing Tim talk, talk about asking customers what they actually want to see. And it just feels like that's a, that's a skill that I think maybe a lot of startup-y type companies have, have. I don't know, maybe they, they, that gets thrown to the background too often and, and should be more in the forefront of how people are thinking.

[00:33:09] **Tim:** I know you don't follow the Discord too religiously Ben, but so I think Sean posted a link about why Envision kind of lost

[00:33:19] **Ben:** yeah, yeah. I've seen that. That post a couple of years old.

[00:33:22] **Tim:** And it's something about screens. I don't know what that means, but it's like,

[00:33:26] **Adam:** It's a prototyping app. It's just

[00:33:27] **Ben:** Yeah, yeah,

[00:33:28] **Adam:** you can click on.

[00:33:30] **Tim:** yeah, but yeah, so some users, like I used it and it was like, I thought, okay, this is great if it only had X feature, I don't, I don't know what it was called it was screens or something, but anyway, folders, and then it took, and then it was never added

[00:33:45] **Tim:** so this chart just kind of just dives where you guys had like major market share and then your competitors just took over.

[00:33:52] **Adam:** Figma ate everybody's lunch.

[00:33:54] **Tim:** Figma. Yeah. That's why Adobe bought 'em

[00:33:56] **Ben:** folders is a perfect example of, of exactly what we're talking about. For years, people said, hey, I just want to be able to organize my stuff so I don't have it as like one giant list. All I want is folders. And we just refused. And I can't even tell you why. We just refused to give it to them.

[00:34:18] **Ben:** And I think it was because if I had to guess, it's like we wanted to have a better solution. The folders was too simplistic. It wasn't like, it wasn't the, yeah, it's like, it wasn't the five wise, you know, digging, digging, digging to get to the underlying cause of what actually kind of solution, you know, you you're coming to us with the solution of folders and that's, you know, don't come to us with the solution.

[00:34:43] **Ben:** Come to us with the problem. Like what's the actual problem. And like, at the end of the day, the problem was. They didn't have folders and they wanted folders, right? Like it's, and I think that's the perfect example of the hubris of feeling like you have to innovate when really the most obvious option is probably the one that people actually need.

[00:35:05] **Tim:** I honestly believe that innovation is a trap, right? I mean, innovation is one of those lightning in a bottle kind of things, right? Everyone works for it. Everybody wants it. If it happens. Fantastic. Good for you. Go reap your billions in stock options. But most people, being the first to do something is not the biggest advantage that people think it is, you know, the, the, the, the first mover is not always the person who wins.

[00:35:33] **Tim:** I mean, you think about.

[00:35:34] **Adam:** it is a big advantage in some circumstances.

[00:35:37] **Tim:** it can be, it can be, but a lot, I mean, we only remember the first movers that, that really shifted the needle and like, you know, Apple, things like that, but even in those cases, like a lot of times these are people that it's the second person, the third person, the fourth person who does the innovation, but does it just a bit better.

[00:35:57] **Tim:** They're the ones who win.

[00:35:59] **Adam:** Yeah, I mean, there's a little bit, we could go on and on about this. The, the main thing I wanted to say is we've now talked about both sides of this, right? So it's easy to be flippant and say, well, you're asking, you're giving me a solution. I'm going to try and find the real problem and solve that. Versus, you know, you can just go ask the customer, what do you want?

[00:36:18] **Ben:** And I can go build it. And, and both of those you can take to extremes and they go bad. And it's, it may not be the finest of line to walk, but there is a, it's a balance, right? You got to stay in the middle there somewhere. Yeah,

[00:36:30] **Adam:** my brain, I just want to, I want to go on a tangent here. My turn.

[00:36:33] **Ben:** I know. Come on.

[00:36:34] **Adam:** so we were talking, we were talking about like first mover advantage and, and that sort of thing. So maybe there's an element of that here or not. so I, I'm thinking of

[00:36:42] **Tim:** Moving, it has the word move in it.

[00:36:45] **Adam:** I'm thinking of SpaceX and their landing rockets, autonomously

[00:36:50] **Adam:** Is

[00:36:50] **Ben:** that Amazon or Elon?.

[00:36:52] **Adam:** That's Elon

[00:36:53] **Tim:** He's

[00:36:53] **Adam:** Musk. Amazon Jeff Bezos is Blue Origin.

[00:36:57] **Ben:** Gotcha.

[00:36:58] **Adam:** So, yeah,

[00:36:59] **Tim:** giant phallic rocket.

[00:37:00] **Adam:** yeah, it's the one that,

[00:37:01] **Ben:** Gotcha.

[00:37:02] **Tim:** hmm.

[00:37:03] **Adam:** anyway, it's been something, I remember reading this recently, it's been something like nine years, or, or, you know, whatever, some, some ridiculously long amount of time, given the idea of like, a rocket could land itself and you could just clean it up and reuse it, and nobody else has successfully done it yet.

[00:37:21] **Adam:** Right? Like, they're not the first movers in rockets, but they are the first movers in that. And, and it's, it's an idea. Like other people are trying different methods. and it's just like, you could be the first mover in like your, your twist on it.

[00:37:35] **Tim:** hmm. That being said, they're not that ridiculously profitable right now.

[00:37:40] **Adam:** Well, no, but they are the only, human capable launch service from the United States to the ISS. So, they can kind of charge whatever the hell they want to the government.

[00:37:51] **Tim:** they've already plowed that field and now someone else can come out and do it cheaper, better, and faster and totally eat their lunch. You know what I'm saying? I say,

[00:38:00] **Adam:** Yeah. No, I mean, listen, I'm the last person to stand here and try and defend Elon Musk and, and all that,

[00:38:05] **Ben:** you're, you're, you make a good point. And I was listening to an interview with the guy who created WordPress, I don't know, maybe like six months ago. And he worked at a company where there

[00:38:15] **Adam:** that was episode... Go ahead, sorry,

[00:38:21] **Ben:** he worked at a company that had already an in house content management system, and he built what became WordPress in house and people started using it. And other people at the company who had worked on the content management system said, I don't understand why people are using your system. It's awful.

[00:38:41] **Ben:** Like, if you look at our CMS, it has all these really advanced features. It can do loads of stuff that your system can't do. I don't understand why anyone's using it. And he said, you're right. Your system is way better in all the ways, except for the one that really matters, which is that mine's very easy to use.

[00:38:59] **Ben:** And, and it's like, you, you can get that, that one differentiating feature that's so differentiating in such an important way that it doesn't matter how much prior art there is another system.

[00:39:12] **Adam:** for sure. Okay, well, now we're 40 minutes in, do we actually want to cover our topic or should we just make this the Tangents episode? Anybody got else? Anybody else got something random you want to talk about?

[00:39:27] **Tim:** we had to go back and record the introduction

[00:39:29] **Adam:** Nah, nah, let's, let's leave that as a surprise ending, right?

[00:39:35] **Tim:** or it's just a cliffhanger, like, you know what? We've talked so much about this. We're just, we're moving on. We'll talk about moving later.

## [00:39:44] Javascript, Typescript, CJS/ESM Modules

[00:39:44] **Adam:** So, I did have, something that, that's been chafing me lately that I wanted to talk about, but it was, it'll be, I think, a relatively short topic, so maybe we'll dive into that. You guys cool with that?

[00:39:53] **Ben:** Let's do it.

[00:39:54] **Tim:** Yeah,

[00:39:54] **Adam:** Okay, so, It's no surprise, I'm sure I've mentioned to you guys, that I love TypeScript, right? I love the experience of writing TypeScript and the experience of using a well written TypeScript library, right?

[00:40:09] **Adam:** It just solves a whole class of problems. It finds bugs in your code for you that you don't even notice are there, that it probably would have been four years until it actually happened, and then you're like, you spend a week trying to debug it sort of thing. And it just gives you a red squiggly in advance and you're like, Oh yeah, I just need to consider that this might be undefined in, in some rare cases.

[00:40:28] **Adam:** And, and that fixes the problem. Anyway, I love TypeScript and there's, you know, different ways to use it. There's the, the vanilla TypeScript or there's the JS doc thing we've talked about recently, but. and I think it gets a little funky when you start to do TypeScript plus ESM, ECMA script modules that like import and export instead of, module that exports and require, right?

[00:40:53] **Adam:** So that, that module, that exports and require, that's called Common JS or CJS and then the, the newer more like, ECMAScript six or whatever it is beyond that, that, where they added import and export. so now you've got like two ways of doing the JavaScript of the module stuff, and now you've got two ways of doing types or, or no types, right?

[00:41:15] **Adam:** And so when you try to make various things work together, it can be... A hellscape.

[00:41:21] **Ben:** Hahaha.

[00:41:24] **Adam:** You get strange error messages. You're trying to like follow people's tutorials, and you're like, okay, build your library like this. And you, you know, you need to build or you're writing your library in TypeScript, but you maybe you want it to be consumable from regular JavaScript.

[00:41:36] **Adam:** So you've got to compile it so that it is, you, you're spitting out a common JS, what is it? A compatible version. And you've got a, ESM compatible version. Right. and you've got typings for both and it's, it's a nightmare and I hate it. And it's like the worst possible thing about TypeScript.

[00:41:54] **Ben:** This would, does this only matter if you're publishing a library for other people to consume, or is this something that matters even if you're just creating files internally?

[00:42:06] **Adam:** I think I can best answer that question with a brief story. Um,we have, you know, we have our products and we, we heavily use JavaScript in a butt ton of lambdas and small containers that do things. And so in order to share common functionality, like make a connection to Redis that, you know, I want to make, I want to say it's customer A in production.

[00:42:29] **Adam:** And just get back a connected database client, right? Or a connected Redis client, whatever. And so we've got modules that are like that, and, and a bunch of utilities and stuff. And they're all, all sort of grouped into this one package. And we just called it like, AlumniQ modules. We'll just call it that.

[00:42:44] **Adam:** and we struggled a lot with that. We learned a lot of lessons about like, what should and shouldn't go in there and how it should be organized. And, you know, what, what are the pros and cons of, of including certain things. And, so I tried to take those lessons and rewrite it from scratch. The whole collection of utilities, it's not even that much, right?

[00:43:04] **Adam:** The, the database and the Redis are like the two biggest things, and those are just wrappers around the public Redis and MySQL, clients, right? And so I'm like, okay, I'm going to, I'm going to rewrite the whole project, this whole, repository from scratch with TypeScript, and I'm going to like go look the tutorials from like this week that are like, this is the way you write a TypeScript module and it's got to cross compile to both CJS and ESM, and it's going to have types and it's going to be great, and I did that, and like every time we try to use it, it's just pain, pain, pain, pain, pain in our own projects, And, like, everything, like, so this was, you know, around the same time that I was spending a whole bunch of time working on what I was hoping would become our Svelte kit, sort of like our new backbone that our new rewrite of our application would go into.

[00:44:00] **Adam:** And I was like, okay, great. So we'll put it, well, I'll, you know, another like lesson learned. Let's, let's try to do this as like a monorepo sort of thing. Right. So you've got that, the application, the monolith and one thing, and then you've got all these little packages that you're publishing, but they're in the same repository.

[00:44:12] **Adam:** Well, let's just like combine it all in there. And. That, too, was a pain in the neck. I want to use much worse words than that, but I don't want to have this just be bleep, bleep, bleep.

[00:44:23] **Ben:** Maybe I missed some of this. So the issue or part of the issue is that you want to be able to use this code in both TypeScript and non TypeScript contexts,

[00:44:32] **Adam:** Yeah, so we have a lot of, we've been writing JavaScript code for, I don't know, like, 8, 9 years, right? And so we've got, now, obviously we've been writing JavaScript for a lot longer than that, but I'm specifically talking about the things that are in production today on, like, AWS Lambda or running on a container.

[00:44:51] **Adam:** in our, in our infrastructure. These are projects that are, we're still using them, they're still being updated, and we need to be able to keep them moving forward. And so, yes, I'd love it to be TypeScript, and I would love to be able to import that into a JavaScript only project, because I don't have time to go and upgrade all 17 Lambdas to all be TypeScript based now

[00:45:14] **Ben:** Well, I know, I feel like this was you, maybe it was another podcast. I think it was you a couple of months ago. Were you the one talking about how you were excited about the typing you could do in JS docs? At least coming, you know, coming down the pipe, that would certainly sound like it would solve some of these problems.

[00:45:32] **Adam:** yeah, and I just haven't had time to dive into that pool. I do, I do believe it would solve some of these problems. I completely agree because then you just, you, you remove, you take the two by two problem, right? The ESM versus CJS and the types versus not types thing. And you, so when you do that, you've got a two to the power of two.

[00:45:50] **Adam:** So you have four problems or four potential outcomes, right? And by, getting rid of the TypeScript thing, right? It's just JavaScript with some comments and the IDE can read the comments and, and feel like, okay, I can be helpful here. that in and of itself would cut the, the potential, outcomes in half.

[00:46:08] **Adam:** And so I feel like that is very, probably a good idea. And I did tell, I have one small project that I built, that I, I did the JSDoc approach for, and it was a little funky here and there, but I made it work. And, the TypeScript stuff, you know, it does the type checking in its project. Oh God, it's been too long now, right?

[00:46:28] **Adam:** it's been, I don't know, two, three months and I've been 100% on compliance brain, so, I, I don't remember there. I was struggling for a few weeks, with it, or maybe for a week with it where like, I was doing all the TypeScript stuff, and I, and the IDE would just like behave like it wasn't TypeScript.

[00:46:47] **Adam:** And I don't know if that was like when I was trying to import these files that had the comments, or the project, or maybe I just needed to reboot my computer, or you know, like it's just, it was that kind of like pokiness where it's like, I, I'm not sure what's going wrong, but something, it doesn't feel right.

[00:47:02] **Ben:** That's frustrating. I know that feeling.

[00:47:07] **Tim:** Your heart matters.

[00:47:08] **Ben:** You know, it's just while we're on the topic of JavaScript modules for a second, I remember this was like a year ago or two years ago. My sense of time here is not good. when suddenly you could do top level await calls inside of your module, you know, cause normally, normally you have to do an async function and then inside the async function, that's where you can do awaits.

[00:47:32] **Ben:** And people were super excited about the fact that you could just do these top level awaits. And I remember hearing that and thinking to myself, well, that's just going to break and do it exciting ways. Like people are not going to understand the implications of that. And not, I'm not saying that I understand the implications of that, but I was not so long ago hearing someone discuss it on a podcast.

[00:47:49] **Ben:** And they were saying that when you have a top level await, it actually fundamentally changes what the module is. It turns it from a synchronous module into an asynchronous module. And then like every module that an asynchronous module gets included into automatically also becomes an asynchronous module.

[00:48:05] **Ben:** And like, I don't know what that means exactly, but it probably means that it's going to break at some point in some way that you don't fully understand. I don't know, it was just, it was just funny to like, see all these people racing to use this. And when, like, my mind immediately went to Red Flags.

[00:48:22] **Adam:** You've been burned too many times, Ben.

[00:48:24] **Ben:** Yeah.

[00:48:25] **Tim:** Yeah.

[00:48:25] **Adam:** The, the, the other thing that like with all these TypeScript woes I've been having, the other thing going through my mind is like, maybe we should try Deno. Maybe just going first class TypeScript would, would just solve these problems, right? Then we wouldn't have to worry about compiling.

[00:48:39] **Adam:** It's got ESM out of the box. I think it probably supports CJS and you know, you can run, you can run non typed JavaScript code on Deno. It's just like,

[00:48:50] **Tim:** Deno, like, like from the Flintstones.

[00:48:53] **Adam:** if you, if you look at the logo, it does look a lot like Dino from the Flintstones, but, you've not heard of this, Tim?

[00:48:58] **Tim:** No, I've not heard of it.

[00:48:58] **Adam:** Okay. So, Ryan Dahl, the guy who created NodeJS,

[00:49:02] **Adam:** you know, stepped away from the project for many years and then kind of came back out of the woodwork, a few years back. And he's like, so. I've, I've been gone all this time and one of the things that I did after reflecting on the things that I ultimately didn't like about Node, like, he was like, okay, I made, I made Node.

[00:49:19] **Adam:** And then, you know, with hindsight, I was like, I don't like this, I don't like this, I don't like this, I don't like this. So he came back and he's like. I've made this new thing, which is very node like, except, you know, it's TypeScript. So, no compiling, none of that. It just supports TypeScript out of the box.

[00:49:34] **Adam:** it's got, top level of weight, since we just mentioned that. it, everything, like, anything security wise is off by default. It has no disk access. It has no network access. It can't do anything. You have to give it a flag on startup of the application to give it permission. You can, and you can go.

[00:49:52] **Adam:** Star, you can say like allow network equals star, whatever the command is, the flag. Or you can say it's only allowed to access the Pirate Bay or whatever. Right? Like, you know, that sort of thing that you can lock it down as tight as you want. and there's like a bunch of other things and they have like their own, so you know how like Vercel, the author, the creators of NextJS, they have their own platform now and, and, you can deploy your, your NextJS projects to the Vercel platform or whatever, like Deno has their own, it's called Deno Deploy, I think. and it's like their own sort of cloud. it's probably a layer on top of AWS or whatever, but you know, it's their own cloud edge thing and it's supposedly really fast and, and really easy to use.

[00:50:35] **Adam:** And I mean, I have not touched any of this, but

[00:50:37] **Ben:** Yeah. No, me

[00:50:38] **Adam:** all very interesting to me.

[00:50:40] **Tim:** Interesting.

[00:50:41] **Ben:** It's funny. So Deno is spelled with all the same letters that Node is spelled with, right? It's just, it's remixed. And for whatever reason, that made me think of, we were talking a couple of episodes ago. Maybe this was on the after show about the, the Dennis system on It's Always Sunny.

[00:50:58] **Ben:** And in this last season, season 16, he talks about the SIND system and, and he's talking to Mac and Mac's like, Oh my God, what are the chances

[00:51:08] **Adam:** Yeah.

[00:51:08] **Ben:** have been Dennis backwards? He goes, a hundred percent. I made it up.

[00:51:19] **Tim:** Well, thank you for that education.

[00:51:21] **Ben:** Oh man.

[00:51:22] **Adam:** Okay, well this was fun.

[00:51:24] **Tim:** Yeah. So we didn't really get to talk about moving on a whole lot. So we'll be moving on from this topic and we'll maybe move on to it later again.

[00:51:31] **Adam:** Yeah, maybe next week.

[00:51:33] **Tim:** Sorry for the swerve.

[00:51:35] **Adam:** Sorry, not sorry.

## [00:51:37] Patreon

[00:51:37] **Adam:** Alright, well then that's going to do it for us this week. This episode of Working Code was brought to you by macOS Dictation, which is,

[00:51:43] **Ben:** It

[00:51:43] **Adam:** not anywhere good as iOS Dictation, but hey, still, still trying.

[00:51:47] **Ben:** makes no sense.

[00:51:48] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure that we can continue putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:51:56] **Adam:** Our patrons cover our recording and editing and transcript costs, and we couldn't do this every week without them, so special thanks to our top patrons, Monty and Giancarlo. We are going to go record the after show, which is a perk for our patrons. You have to become a patron or you can get a free trial of our patron.

[00:52:13] **Adam:** Go to Patreon.com/WorkingCodePod. Give it a listen and maybe you'll stick around, support us and support, whatever this is that we're doing.

## [00:52:24] Thanks For Listening!

[00:52:24] **Adam:** That's going to do it for us this week. We'll catch you next week. And until then,

[00:52:27] **Tim:** Remember your heart matters, even if you plan to move on and then just talk about whatever this was.
