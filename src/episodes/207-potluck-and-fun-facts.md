---
title: "207: Potluck and Fun Facts"
description: "In this week's episode, Adam, Ben, and Carol discuss a variety of topics including 'disagree and commit', responsive design, and feature flags."
date: 2025-02-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/207-potluck-and-fun-facts/id1544142288?i=1000696520610"></iframe>

In this week's episode, Adam, Ben, and Carol discuss a variety of topics including "disagree and commit", responsive design, and feature flags. We take a trip through time with some fun facts from internet and web development history.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/207-potluck-and-fun-facts.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** 1996 Is when CSS was introduced

[00:00:04] **Carol:** Oh my god.

[00:00:05] **Ben:** Yo,

[00:00:06] **Carol:** I still don't understand CSS, let's be real. Oh man.

## [00:00:31] Intro

[00:00:31] **Adam:** Okay, here we go. It is show number 207. Tim could not be with us tonight, but we got everybody else

[00:00:36] **Carol:** Oh,

[00:00:38] **Adam:** Boo, Tim. Yay. Tim's not here.but on tonight's show, we're gonna have a little bit of a potluck we're just gonna kind of go around the horn We got a bunch of different little things to talk about so, it's a good time to empty those, coffers of small topics but first as usual, we'll start with our triumphs and fails and ben it is your turn to go first my friend

## [00:00:59] Ben's Programming Paradigm Struggles

[00:00:59] **Ben:** I will go with a failure, which is kind of a, we've discussed before a little bit of a triumph, a little bit of a failure, a little of this, a little of that, as I've talked about in the last couple of shows, I've been exploring and questioning a lot of my programming paradigms and, uh, the, the failure is that it's just really hard to find clean boundaries around things.

[00:01:19] **Ben:** every time I feel like I'm making good progress in one direction. Something gets a little sticky and I find myself in a corner that I can't quite explain, the reasoning for it. My latest one is that I, I felt like I had some really good separation between the, the kind of view oriented stuff and then the business logic, like the core application logic.

[00:01:44] **Ben:** And then, I'm working on this little side project and I had to send out an email and the email has a link to the website, to the app. And I'm like, oh crap, because sending out the email feels like it's part of the core business logic, but how does the core business logic know what URL to put in the email?

[00:02:04] **Ben:** I'm like, I don't want the controller to provide that. That seems crazy. So then I got to the situation where the, the, the concept of routes and the very notion that you're sending people to a web app. Is kind of like a cross cutting concern and I had to start moving stuff around. And in the discord people saw, I had asked questions about moving folders around and kind of bringing everything into this one library umbrella, and then maybe just namespacing stuff under web or view or something to say, this is part of the app, but it's, it's very clearly oriented towards the web.

[00:02:38] **Ben:** And, you know, it's still a work in progress. So the, the failure there is just that it's tricky and it continues to be tricky. but the triumph is that I'm, I'm still have an edit. I'm not giving up. I'm, it is very much a, a vibe driven development. Like I'm just looking for something that feels right.

[00:02:56] **Ben:** Cause it's not like it doesn't work. The app works. It's, it's not easy, but it's, it's to build an app that works is only one point of reference. I want an app that feels good.and maybe I'm just chasing weird objectives at this point, but I'm having fun doing it. But I will say that as I'm continuing to evolve my mindset, , it's nice to find certain truths that seem to remain truthful. And the one that I really stick to and continue to find value in is just no circular dependencies. Obviously there are data structures like linked lists where circular dependencies have to exist.

[00:03:35] **Ben:** This node has to point to that node and has to point back to itself kind of a thing. but I have never felt good about having, let's call them like core business objects, business services have circular dependencies. That has always been a code smell in my mind. You know, like if the user service shouldn't need to reference the permission service, which shouldn't then need to also reference the user service.

[00:04:01] **Ben:** I'm like, okay, somebody made a wrong turn somewhere. These two things shouldn't know about each other in a bidirectional way. Like there's probably some shared piece of logic that should actually be factored out that both those things should be referencing. And I've continued to use this anti circular dependency as a North Star, and I'm continuing to find that to be a very valuable choice, as I, as I wire all my stuff together.

[00:04:25] **Ben:** So I'm pleased about that.

[00:04:27] **Adam:** It's impressive how far you fit your whole head inside your belly button there.

[00:04:34] **Ben:** You know, I think it's, it's, it's exciting to question things and it's exciting to find that some decisions that you've made are, I think, really good. And then some decisions are like. Just incidental and meaningless.

[00:04:47] **Adam:** Do you think that you're on this, like, journey of introspection in part because you're between jobs?

[00:04:53] **Ben:** I mean, I think I'm using that as an opportunity to, it's, it's more like, so I worked on the same app for so long. That all of the patterns that were there were just the patterns that were going to persist, like I'm not going to suddenly change the way the app works fundamentally. So it's just nice to be able to start something new.

[00:05:12] **Adam:** And again, this thing I'm working on, it's just this little side project. It's not even a thing. It's, it's, it's literally for the sake of exploration. green field and you're all you've gone 100 percent into the touch grass

[00:05:22] **Ben:** yeah, yeah, yeah, exactly. So I'm just, you know, I'm, I'm reveling in the. Open endedness of it and trying to find the paths that need to be paved.cause I know that once I pave them, things get much more challenging though. I will say, as I've been doing this exploration, you know, people talk about the really fancy text editors or like IDEs where they can do like auto refactor method to class and like all this stuff where like Jimmy jazz, all your stuff around automatically.

[00:05:55] **Ben:** And, I just, I just do extended find and replace. And it's. You know, obviously a little bit more work, but it's basically not a lot of work. It's pretty great. You know, I could take whole folders and move them around. And then now suddenly all of the paths to these components will break. So you just say, okay, anything that was a client dot view dot lib is now core dot lib dot web.

[00:06:18] **Ben:** And you're like, Oh, done. Just change that in 65 files. And my IDE has a save all and close all. And I'm like, okay, that's, that's a, I just did that with a editor. That's not so impressive.

[00:06:29] **Adam:** Yeah, I mean, it certainly can be done in more simple cases, you know, even using something like a regex search and replace. I just think that, especially when you start to do regex, you're, you're bumping up against some complexity there. So, there, the likelihood for false positive matches is there.

[00:06:45] **Adam:** And then not only are you Like not fixing it, but you're creating new problems with your replace or whatever,

[00:06:52] **Ben:** Yeah. Yeah.

[00:06:53] **Adam:** but then, you know, your, your automated test suite will pick it up

[00:06:55] **Ben:** hundred percent. I always have that safety net. Anyway. That's my failure. Um,let's kick it over to Carol. Carol. What do you got going on?

## [00:07:05] Carol's Triumph: Getting Back to Working Out

[00:07:05] **Carol:** it's not a work related thing. I'll talk about some work stuff later so you guys would be happy to hear about, you know, work. And then I still have a job. I will keep adding that every week until it changes. My triumph is, I am working out again. I have decided to start working out this week.

[00:07:20] **Carol:** You know, my husband inspired me and motivated me to make some changes, but basically since the first of the year, it's been a struggle and really since the, since January 20th, honestly. The day I came back was seeing my parents life just been so crazy and so stressful that I've had zero energy to, to do anything other than just sleep, eat, work, you know, like mentally I've been drained.

[00:07:44] **Carol:** So this week I've gotten back at it and I feel my muscles again, like my arms hurt, my legs hurt. When I squat to go pee, it's pretty painful in my stomach. You know, like all of those things that, that remind you. I'm working out again and it feels good. So I think that's a big win.

[00:08:05] **Ben:** Heck

[00:08:07] **Adam:** congrats.

[00:08:08] **Carol:** Yeah. Thanks.

[00:08:09] **Adam:** about that.

[00:08:10] **Carol:** Yeah. So Tim's not here. What do you got Adam?

[00:08:13] **Adam:** I

## [00:08:14] Adam's AI Experimentation and Frustrations

[00:08:14] **Adam:** am also gonna go with a Emph, because it, you know, it's a, it's just a little bit of both, in the same topic here. So we're just gonna take both sides. I was listening to another podcast and I got inspired to do something. it was a, it was just like a, the, the podcast is called No Dumb Questions.

[00:08:28] **Adam:** It's, the guy from Smarter Every Day and one of his friends that is a retired. pastor preacher or whatever, but just to like, there's like a science guy, humanity, human humanities, that's the word humanities guy. And they just like they're good friends and they chat and it's, it's good, good conversations, right?

[00:08:43] **Adam:** Cause there's like science brain and humanities brain and they tackle problems differently. Anyway, they had a conversation about AI and. they, you know, they, they recognized that they were out of their depth. So they brought in a, person who is a software engineer who uses AI a lot and has their sort of their finger on the pulse of all this stuff.

[00:09:03] **Adam:** And they had a good conversation with him. And one of the things that he said in the podcast was, he basically wrote an entire application just by like consecutively prompting AI, like, Oh, I got an idea for an app, you know, I want you to write a spec document. And then he's like, okay, well, that sounds good.

[00:09:17] **Adam:** So go ahead and, you know, start writing the app. And it's just like a series of prompts over and over. And eventually he had this whole app that like took, his like, you know, he has copies of older public domain books, like, you know, ancient. Whatever historical books and it converts them into audio books for him.

[00:09:35] **Adam:** but the, the reason that he was interested in doing that is because like all these things that, will take do like text to speech for you, they're limited in duration, right? You can only generate like a 30 second clip or something like that, right? So you can't do a full book. So he wanted to automate like, okay, just break it up into chunks and then stitch all those chunks of audio back together.

[00:09:53] **Ben:** So he wrote, he used AI to write an app to do that. So I was inspired by this and I was like, okay, maybe this will get me off my butt and try, that skydiving app I talked about months and months ago. like scheduling planes. That one.

[00:10:06] **Adam:** yeah. Manifest stuff. I, you know, I had some fun initially with it, but then it, you know, stuff started to get hard and I was like, I just don't have time for this right now.

[00:10:13] **Adam:** And it just ended up on the back burner forever phase. And so I was really inspired to try that out. And so instead of asking AI to write the functional spec, just because, you know, I know exactly what I want this thing to do. And it's more complicated than just like do these three things. It's like, here are 20 different specific relationships I need you to manage.

[00:10:33] **Adam:** So I wrote the functional spec. I should have pulled it up before this and gotten a list, but it is not a short document.and I took it to one of these AI, like we'll build your app for you tools. They're like, you know, you just write a prompt and you, you know, make Facebook for penguins or whatever.

[00:10:47] **Adam:** And it, and it does it.

[00:10:49] **Ben:** Which one did you use? Just out of curiosity.

[00:10:51] **Adam:** the one that I used was the one from. I think it's from the stack blitz people. it's a bolt dot new.

[00:10:58] **Ben:** Okay. Yeah.

[00:10:59] **Adam:** I I thought about doing the v0. dev which is from vercel. But I think so I was very specific. I wanted it to generate svelte kit and I think that that one can only do react

[00:11:10] **Ben:** They're like, no, we're doing react and tailwind. Yeah. Yeah. Yeah.

[00:11:15] **Adam:** and that was just a deal breaker for me so, but the the bolt dot new will do svelte kit and I you know, I was surprised it it did initially seemed like it was going to go well. you know, it read the whole thing, it seemed to understand what I was asking for, and it was like working on it in chunks.

[00:11:30] **Adam:** Like, okay, let me get a basic spelt, get up together, does this look good? And then it's like, okay, well, you know, what do you want to do for auth? Like you want to use SSO or use a new password or magic links or whatever. And so we started building stuff out and then It hit the database because I was like, okay, this is kind of the data model in my spec Like these are the different entities and these are the relationships between them and here's some of the fields that are on each oneand I think it understood that but then I guess the that particular product the bolt dot new the way it seems like it has an integration like sort of pre Vetted or like kind of programmed into the intelligence of it.

[00:12:10] **Adam:** That's like, okay, if somebody wants to do a Postgres or my SQL style database, then do it. use super base and there's like, yeah, the responses I was getting back made it very clear that they had in sort of their like system part of the prompt that we will only ever support username and password. We will never support SSO stuff.

[00:12:33] **Adam:** I don't know. And so I was battling that. And then I very quickly ran out of like my daily, AI tokens

[00:12:40] **Ben:** see, like, you're like, Oh, you have 40, 000 daily tokens. You're like 40, 000. That's crazy. And then like, literally 10 minutes later, you're done.

[00:12:49] **Adam:** So, I got real frustrated and I was like, fine, you know, you didn't even do that much for me. Like it was barely more than running the command line to generate a new SvelteKit app skeleton. And I could have done it. It probably installed some stuff on NPM or whatever that I might not have otherwise known about, but very little other actual work.

[00:13:08] **Adam:** So that was frustrating. And then, yeah, and that was the other thing too, is like, you know, you get 800, 000 tokens a month, but it's 150, 000 a day, right? So like, yeah, you can do more, but you have to wait till tomorrow. That's frustrating. So, and then the other thing, like I, I, I got frustrated and I pushed it away and that's the last I did on it.

[00:13:27] **Adam:** Then between then and now, I've gone, you know, I'm paying for copilot. I wonder if the copilot stuff built into VS. Code could do most of the same thing anyway. And if I, if it doesn't have the same limits, or at least the limits might be higher. So I haven't done it yet, but I intend to go back and try that in there.

[00:13:43] **Adam:** Mm-hmm

[00:13:45] **Carol:** Yeah. I think it's Copa can give you if you're already paying for it. Oh,

[00:13:52] **Ben:** I tried. I knew it's the only one that I've tried so far, as far as the like robust auto generation. And I got into, it sounds like the similar path that you got to, where suddenly it was like, please enter your Firebase code. Key or something or super base key. And literally there was no cancel option.

[00:14:14] **Ben:** There was no, like, no, I don't want, because it, at least from, from when I tried it, it's sort of this chat interface and it starts generating stuff in the chat. And once it got to the, please enter your key, there was no like stop generating. There was no even option to enter any more text at that point until I proceeded with the key and I, and I did, I just had to like start a new project, but by then I had already burned through.

[00:14:36] **Ben:** You know, like 80 percent of the credits to start over was very frustrating. But, something, this is not an original thought by me. This is something that I've heard other people express on various other podcasts. This idea that some tools will only build things and react or are clearly much more trained on react.

[00:14:57] **Ben:** And there's this fear of this, kind of self fulfilling prophecy, kind of like when someone enters the, the, the web development ecosystem and they say, Hey, what should I learn? And someone says, Oh, you should learn react. Not because it's the best option, but because that's what people are hiring for. So does it then become, well, you should learn react not because it's the best option, but because what all the AIs are trained on, like, are we like, is this how we want to be choosing tools?

[00:15:23] **Ben:** That seems weird.

[00:15:25] **Adam:** Yeah, I agree. And that's kind of, I do have the good fortune to be in the position to, A, be making that decision for myself, right? I'm sure there's a lot of people that don't get to make that decision, but B, just be able to kind of take a stance and say like, no, you know, me and my team, we just, we did React for a long time and it caused us more grief than pleasure.

[00:15:49] **Adam:** and we, you know, we have a bunch of React apps that we have to maintain and we're not happy about how that maintenance process has gone and we would rather try something new. Either it's going to be similarly horrid over time or it'll be better. But, you know, at least we're giving ourselves a chance at better.

[00:16:05] **Adam:** So, that's a big part of why we are interested in taking a bet on Svelte.yeah, so. Frustrating, but hopefully it'll motivate me to keep, keep pushing.

[00:16:16] **Ben:** I look forward to hearing more about people's various AI experiences, because I'm very slow to get on this train and stops that I've taken are less exciting than I was hoping they would be.

[00:16:31] **Adam:** It was interesting. So I want to go back and just briefly touch on that podcast. so one of the things that I found really interesting, it's funny, cause they kind of danced around it. because they, there's a word that you could, I could kind of tell that they were, implying, but they didn't want to say it's the R word.

[00:16:48] **Adam:** and, basically the idea is like, you know, these AIs are just like, they're, they're statistical models for like one of the most likely next three characters in the sentence that I'm currently writing, right? And they're trained on all the existing human written content and now it's generating a bunch of additional content that's going out there.

[00:17:08] **Adam:** And then it's going to basically get into this point where it's mostly training on its own output. And so they kind of referred to it as like AI inbreeding. then, you know, just like in, the human, system. You know, you do that long enough and you're going to have, bad outcomes. So it's just very interesting time to be in this field.

[00:17:30] **Carol:** like 11 toes kind of thing.

[00:17:33] **Adam:** Yeah. Or, or, you know, I'm trying to, I'm also trying to be political and dance around it here.

[00:17:39] **Carol:** So hard.

[00:17:40] **Adam:** Yeah. Okay. Well, that's it for me. why don't we move on to our pilot? Who's got something you want to go with first?

[00:17:47] **Carol:** Oh, can I please go first?

[00:17:49] **Ben:** Hit

[00:17:49] **Adam:** I suppose

[00:17:51] **Carol:** Yeah.

## [00:17:51] GitHub Actions Green Light

[00:17:51] **Carol:** So morale has been dead lately at work. It's just

[00:17:54] **Adam:** can't imagine why.

[00:17:55] **Carol:** it's been in the garbage can, like, let's be real. Like our teammates are leaving, you know, we've had some very solid talent be let go because they were on probation and there's nothing you can do to help these people and the constant change.

[00:18:11] **Carol:** It's just. It's disheartening, you know, like we're doing the best we can, but it just feels like we are facing a lot of challenges. We're not giving up. You know, we, we signed up to do a job and we're going to keep doing the best that we can. today I got some really good news or it feels like amazing news on my side.

[00:18:30] **Carol:** we got the green light to, to move forward with using GitHub actions across the board for all of our projects, which means some things that were stalled are moving forward and it just shows that where we were stuck and not able to make progress. We're able to do that now. So we're already using GitHub actions for a few things.

[00:18:49] **Carol:** but today I, worked with one of our DevOps engineers to figure out how we could cache some of our packages a little better so that things don't cost so much across the network. You know, we were actually getting denial of service because our packages are so large that they're like, quit hitting us.

[00:19:06] **Carol:** We're not giving them to you. And I was like, Oh no, this is bad. So, you know, we spent the day kind of investing in how we're going to cash things and it may not be the right step. It may not be exactly what we're supposed to be doing, but we are loving the good news of make progress, go develop, do what you signed up to do.

[00:19:27] **Carol:** And suddenly like today was the first day in a few weeks that it's felt like I'm doing the job I signed up to

[00:19:34] **Adam:** Right. Permission to get some work done.

[00:19:36] **Carol:** Yeah. Right. And it's like things we've been wanting to do, but we're held up and, Oh, we need to negotiate pricing. We need to figure out budgets. We need to know what other options there are.

[00:19:47] **Carol:** So to know that we can completely use GitHub actions from code to deployments, like that's just great. It's just amazing that we actually have the green light to move forward. So I'm super excited about that.

[00:19:59] **Ben:** Very

[00:20:00] **Adam:** Cool. Yeah. I mean, I love GitHub actions. I, you know, we've talked in the past, their, their interface is a little frustrating for like a monorepo situation, but what you get for, from GitHub actions, especially like even just the free tier, like you can get so much stuff done. In the, in the free tier,

[00:20:18] **Carol:** Yeah. I've decided that tomorrow. I'm just going to spend the day learning because I've got a lot to figure out because one of our top engineers left and he was the one that had handled our transition in the GitHub and he was doing all the optimization on our GitHub actions and now I have a DevOps engineer that's undoing some of the work he did and I don't know who's right or wrong because I haven't learned yet, so I get to spend tomorrow kind of figuring out caching in, in, in depth and understanding like how our packages are being handled.

[00:20:51] **Adam:** yeah, the caching stuff is, is one of the harder parts of GitHub actions. And so good luck. I

[00:20:58] **Carol:** Well, good. I'm starting at like level 400 tomorrow. Yeah.

[00:21:05] **Adam:** All right. Well,

[00:21:06] **Carol:** go.

## [00:21:07] UTC, Dates, Times

[00:21:07] **Adam:** yeah, I, I got, I'm going to pepper these in throughout the episode. It might, my, my stuff is just a bunch of fun facts. I've been collecting over the years or over the last couple of months. and I'll start with this one. so we probably all know what UTC is, right?

[00:21:19] **Carol:** Yeah. Universal time code.

[00:21:22] **Adam:** it actually stands for, it actually stands for Coordinated Universal Time.

[00:21:26] **Carol:** Oh, this is so dumb.

[00:21:27] **Ben:** C is silent.

[00:21:28] **Carol:** I, I knew I hated it for a reason.

[00:21:31] **Adam:** yeah, so basically it's, it's the same thing as GMT, except that it doesn't do any daylight saving time or anything, right? It's just like, this is the one canonical time that never changes, never shifts forward or back or anything like that. This is the time that all other times are based on, right?

[00:21:50] **Carol:** UTC. But the, the fun fact here is why is it UTC? I just said it's coordinated universal time, right?is it where we change dates?

[00:22:00] **Adam:** no, it's, it's because, the standards body that like that decided UTC, you know, like this is where it's going to be and this is what it's gonna be called and all that, was multinational, right? There was some, I know for sure that there were Americans and French people. There, I'm almost positive.

[00:22:15] **Adam:** There were a bunch of others as well, but the, the two that I know offhand are Americans and French and, and duh. You know, our languages structure words and phrases differently, right? In America, we say coordinated universal time, but in France, I believe it is UCT or TCU, something like that, right? The way that they would order the words.

[00:22:40] **Carol:** They're wrong,

[00:22:41] **Adam:** well, so the, what they agreed on was let's just pick an acronym that is wrong everywhere.

[00:22:48] **Carol:** I love it.

[00:22:49] **Adam:** so that nobody wins.

[00:22:51] **Carol:** Oh,

[00:22:52] **Adam:** That's why UTC is UTC and not CUT or TUC or TCU or anything like that.

[00:22:58] **Ben:** Always blown away when I hear people talk about storing dates and databases on, on various podcasts and interviews where they UTC.so, so like my default reaction is always, everything should be stored in UTC. I made the mistake of not doing that years ago and it caused nothing but strife. And then you figured out, okay, kind of like how we're misspelling UTC on purpose.

[00:23:25] **Ben:** It's like UTC as a time doesn't make sense for most people who are using the app, but at least we can all agree that it's like makes wrong sense for everybody consistently. And then people will talk about building scheduling systems where storing things in UTC. Really does become a problem, but their explanations never seem sound to me.

[00:23:46] **Ben:** It's they'll say things like, well, what happens if I live in New York and I have to schedule something for 10 o'clock? In California in a week and I scheduled for 10 and then I show up in California, but I'm like three hours too early. Cause I thought it was 10 o'clock, but my phone hadn't changed because it was still on airplane mode.

[00:24:04] **Ben:** I don't know. It's like, I feel like that doesn't seem like a persistence problem. That seems like everything around persistence was causing a problem. And granted, I've never really built a calendar. So maybe I'm just talking out my hiney, but. I just, I find it very hard to believe that there's ever a world where I don't want to store it in UTC, at least.

[00:24:24] **Ben:** As the source of truth, and then maybe store something else additionally to say like this was the user's original intent. It's like flavor, but I don't know. I mean, have you guys ever run into an issue where UTC was not the right idea? Right.

[00:24:41] **Carol:** What I face is logs. It's trying to figure out when things are happening. And I'm like, oh, I'm in Azure looking at app insights and these logs show UTC. Now I go back to the database. Oh, all these logs are written in server time and then some actual error logs are up from the browser.

[00:25:04] **Carol:** Like, Oh, let me know what the user was doing. I'm going to give you the timestamp trying to put those together. Is a nightmare and I hate it so much that whenever I get super deep into it, I end up with like an Excel sheet on the side that does my calculations for me. That's like, if I was UTC here, this is what I was on the East coast and this is what I was on, like, all the American time zones.

[00:25:29] **Carol:** So then, like, piece together the logs for those times, depending on how we sort it.

[00:25:34] **Adam:** So I'm going to give you a website suggestion here, Carol. go to everytimezone. com.

[00:25:40] **Carol:** oh, yeah,

[00:25:41] **Adam:** and it's just like, you can change what day it's on or whatever. So, so that like daylight saving time can be taken into account and stuff. Cause you know, certain areas don't, obey or follow or participate in daylight saving time, all that.

[00:25:53] **Adam:** So time, the differences can shift over time, right? Mm hmm. And so this website, it's just like a stack of time bars and they're kind of shifted at an angle, right? So you can see like, okay, eight o'clock here is nine o'clock here, seven o'clock here, right? but, and then you can, it's got a vertical line and you can drag it around.

[00:26:10] **Adam:** So you can see like, okay, nine o'clock in UTC is this, this on the East coast, this in mountain, this in Pacific, this in England, this in China, whatever. and it's super useful. I use it for exactly that all the time.

[00:26:24] **Carol:** yeah, I definitely need to check it out when I was living in Arizona. We were in 1 of the places that don't observe daylight saving sign. So, at 1 point, I had like a sticky note. On my computer that had, which, which point we were in, whether I was 2 hours off or 3 hours off, because I had to remember when production releases happened.

[00:26:45] **Carol:** So, was I getting up at 5 am or 4 am? Because that's a big difference when you're sleeping.

[00:26:51] **Ben:** Absolutely. That hour makes a big difference.

[00:26:54] **Carol:** huge.

[00:26:55] **Ben:** was just listening to something the other day and they mentioned every time zone. And I think they said it was built by the same woman who wrote the just effing ship

[00:27:04] **Adam:** Yes.

[00:27:05] **Ben:** small world.

[00:27:07] **Adam:** Well, I mean, that's where I got it,

[00:27:08] **Ben:** Oh, gotcha. Gotcha.

[00:27:09] **Adam:** know, I, I kind of follow her, her and her companies and the stuff that they do. So that's where I got it from.

[00:27:16] **Ben:** I'll, I'll go next then.

[00:27:18] **Adam:** Yeah, go for it.

## [00:27:19] Disagree and Commit

[00:27:19] **Ben:** this, this was inspired by something political, but it won't be a political conversation. It's just the impetus. So there's been a lot of talk recently about the way politicians can not agree with something, but state a falsehood out loud. and it's basically so, so then there's a lot of analysis about why things like this happen.

[00:27:43] **Ben:** And, and one of the things that gets brought up in a lot of the. Kind of news oriented podcast I listen to is that it's essentially a way to force people onto your side. If you essentially get someone to state what everybody knows is a falsehood. Out loud, then it kind of takes away your power to disagree in the future.

[00:28:03] **Ben:** It's kind of the, the, the equated often to the, the emperor has no clothes. It's like, once you go down that path, like you've already, you're, you know, your soul has already been crushed. There's no more fight left in you that you have no, you have no, argument. And so that was the impetus of this conversation.

[00:28:23] **Ben:** The rest of it will not be political. But what it made me think about the other day. Was the concept of disagree and commit. And I think we've talked about the notion of disagree

[00:28:33] **Carol:** have, yeah.

[00:28:34] **Ben:** and how what's happening politically feels exactly that it is people disagreeing with something, but committing to doing it anyway.

[00:28:45] **Ben:** And I wondered, and I posit. That all of the,harmful components that go into that gesture in the political world, does it exist maybe to a lesser magnitude, but still exist in a corporate world, meaning let's say we're working on a project and we're trying to decide a technology and let's just make it concrete.

[00:29:09] **Ben:** I say, Hey, we should do a relational database. And someone says, bro, that's so weak. We're going to do a no SQL database. And I'm like, well, I don't think that's a good idea. And they say, well, it doesn't matter if you think it's a bad idea, like that's what the team wants to do. So we're going to move forward with a no SQL database.

[00:29:25] **Ben:** So at that point, you kind of just have to disagree and commit because we have to build a product, people are paying us to do this, but I felt like, okay, now that I've disagreed and commit on that point, like does part of my soul just die, And, and then it's like every other bad decision that I want to push back against.

[00:29:43] **Ben:** Is it like, ah, well, I've already just agreed to do this anyway. So like, is it worth fighting anymore? Is it worth pushing back now that they want to bring this other technology? And I think that's a bad idea, but like. like we've already gone down this path, so do I care anymore? And it's not like I fundamentally, it's not like I don't want to do a good job when I show up at work, but I think like something in my DNA gets altered.

[00:30:09] **Ben:** And I'm just like, I just don't care the way I would have before. And maybe that's a flaw in my personality, but that's why the whole political climate is making me think like there's actually a real power dynamic that's happening that maybe people in the corporate world aren't addressing because It's not so charged.

[00:30:29] **Adam:** I mean I hear what you're saying and I gotta Feel my gut also says that there's an element of truth to this like it's based on something real deep down in there but I I can't help but you know, just draw the distinction that there's there's a difference between Disagree and commit and pledging fealty to dear leader, right?

[00:30:51] **Adam:** Like,

[00:30:51] **Ben:** Yes, but

[00:30:53] **Adam:** when the political distinction that you're, or the correlation that you're drawing is like, you know, these people have said, you know, this is what we believe in. Like, they're going out in public and saying that you're testifying to Congress. Yeah, air quotes around the we there. And, and so that kind of takes away their credibility to disagree with themselves later.

[00:31:14] **Adam:** Right? Whereas I think that the disagree and commit thing that we've talked about in the past when it comes to our work is more along the lines of we just have to agree that we can't argue it out forever. Right? We have to sort of time box the argument and a decision will be made and we all have to accept that that's the process.

[00:31:33] **Adam:** And Some people are going to win and other people are going to not win and we just have to accept that,

[00:31:40] **Ben:** yeah, a hundred percent. But I just, I just wonder if there's some degree of the whatever's happening. At a fundamental level, maybe it's just smaller because the stakes are lower. I don't know. I, I, so I, I was obviously at work, very large proponent of one cold fusion of two monolithic applications, and we would discuss the pros and cons of whether or not we should move to microservices and other technologies and.

[00:32:15] **Ben:** I remember after the decision was made, people would sometimes continue to have debates about it in public channels, you know, Slack channels or on zoom calls. I can only speak for myself here, but I was pulled aside at one point by one of the leadership team and said, Hey, you can't talk about this publicly anymore because it is not good for team morale. And like, there's a, there's a, like what, what they constantly refer to. As a chilling effect, you're like, well, if I don't feel free to talk about this, like, what else should I not feel free to talk about? And I, and I just, I don't know, like, again, maybe I'm making a mountain out of a molehill or whatever.

[00:32:59] **Ben:** The one I've

[00:33:00] **Adam:** Yeah, you said it

[00:33:01] **Ben:** like a tempest in a teapot.but I just, I feel like sometimes we hand wave over things and I, and I think maybe there are. More dynamics at play than we give credit to. And that's all

[00:33:15] **Adam:** it's an interesting correlation for sure definitely something to spend more time introspecting on

[00:33:20] **Ben:** that's what I've been doing a lot lately.

[00:33:24] **Carol:** That's why I've been drinking a lot lately.

[00:33:29] **Adam:** I think I just figured out who this sponsor of this episode is going to be

## [00:33:33] Emojis and Unicode

[00:33:33] **Adam:** okay. Well, let's do another fun fact A lot of these are specifically in here to make us feel old and that's where this one is going to start. so, emoji, right? The little cutesy faces, that, that are so like ubiquitous now.

[00:33:48] **Adam:** they've been around for a while, but did not become like the standardized thing that they are now. Until 2010, which for you, for those of you doing the math at home, as we were recording, this is 15 years ago.

[00:34:03] **Ben:** Like when you, when you say standardized, you mean all the browsers and the operating systems are going to agree that this Unicode character means smiley

[00:34:10] **Carol:** This

[00:34:11] **Adam:** Exactly. Yeah. So prior to that agreement, you might, you know, so it was kind of different browsers, different platforms were implementing, they were using the Unicode space to implement kind of whatever they felt like they wanted, right? So you might do. A happy face and send it to your friend in Tokyo and they're going to see it as a Hanya mask, right?

[00:34:29] **Adam:** Which is like a very different thing and that's just because it what goes what gets sent across is not the pixels of the happy face It's the unicode character that represents or that that is represented by a happy face on your screen and 2010 that they finalized the the shared specification whichis it?

[00:34:50] **Adam:** Yeah, it is. So it's 2025 another. This is unrelated. I just thought of it. But, 1995, would be 30 years ago this year, right? Which is how far back in time. Marty McFly traveled in the first back to the future movie.

[00:35:06] **Ben:** That's

[00:35:07] **Carol:** Whoa, mind blown.

[00:35:08] **Adam:** That would be us traveling back to 19. Like, imagine what you were doing in 1995. That was, now versus then is, is what Marty McFly experienced.

[00:35:16] **Ben:** Yeah, well, at work, not many years ago, maybe like six or seven years ago, I distinctly remember having a conversation where someone wanted to add some emoji interactions inside of the app. And I said something like, is there a, is there a single list of emoticons that we can use? And they were like, Emoticons. What is that?

[00:35:41] **Adam:** Get out of the way, grandpa.

[00:35:42] **Carol:** yeah.

[00:35:43] **Ben:** what they're called?

[00:35:45] **Carol:** That's Ben. Get off my grass!

[00:35:48] **Ben:** and this is for the listener's benefit. emoticons are the, are the like colon open parentheses versions of emojis. They're like the pre emojis. They're the, the cave art.

[00:35:59] **Adam:** emojis. Yeah.

[00:36:01] **Ben:** The art world of the emojis.

[00:36:03] **Carol:** Wow.

[00:36:04] **Adam:** I still use a lot of those. There's, there's like a lot of apps will auto convert them, right? If you do like colon uppercase P it'll do mouth and tongue sticking out or whatever, but like, I just, I still prefer the text ones, in a lot of cases.

[00:36:16] **Ben:** Well, here's something so interesting about that. I definitely use a lot of the. Ones that are easy to type because they're easy to type. Like I know there's a little icon that I can click on, or I can do, what is it? Like control command space bar, no control shift space bar. There's some, there's something that'll bring up the, uh, the, uh,

[00:36:34] **Adam:** command space. Yeah. Yeah,

[00:36:38] **Ben:** doesn't auto go into the thing that I'm trying to do, or I have to click it a bunch of times.

[00:36:44] **Ben:** It's like the, the path of least resistance becomes the path I choose simply because it's less resistance, not because it's the better option. So like all of my reactions, my emotional state has been boiled down to essentially like the sideways smile or the thumbs outs or the, you know, the tongue out smile, because like, that's what I can do on the keyboard.

[00:37:07] **Carol:** And while it's not an emoji, or an emoticon, straight up, I love LOL. I just love LOL. Like, that's my go to for so many things. I'm like, you know what I mean.

[00:37:18] **Adam:** I think

[00:37:19] **Carol:** you anything extra.

[00:37:20] **Adam:** that's the Xenial in us.

[00:37:22] **Carol:** hmm.

[00:37:22] **Ben:** I think it's funny. So I, I listened to a lot of podcasts and Siri, I assume it's Siri. I don't know if that's the right thing will interrupt if I get a text message and it'll read, you know, like so and so sent a text message and they read it out. And if someone types out, ha ha ha ha, like five or six times.

[00:37:41] **Ben:** It doesn't just say it monotonically. It's like, it gives it some flavor. It goes, ha ha ha ha ha.

[00:37:46] **Carol:** huh.

[00:37:48] **Ben:** And I'm like, someone had to make that decision. I think, I mean, that's how, is that how this machine learning stuff works? Like someone had to say that was the better option.

[00:37:57] **Adam:** I'm guessing it's, following like rules of pronunciation, right? Like there's, there are specific rules about like where, when there's this many syllables and like this many vowels in the word or whatever, like you, this is where you put the, the emphasis in the word. always been my, my sort of educated guess as to how that, or why that happens.

[00:38:18] **Adam:** Yeah. Yeah.

[00:38:19] **Ben:** I'll believe it. I can't push back.

[00:38:22] **Carol:** Just one addition to the 2010 thing. So while you guys are very old, and you're very old, we know you're very old, right? 2010 is the, that summer is when Tim hired me as an intern straight out of college. my software engineering, like career aligns with when we standardized, standardized emojis.

## [00:38:47] Responsive Design

[00:38:47] **Adam:** Well, you want to know something else interesting that happened in 2010?

[00:38:50] **Carol:** Yes.

[00:38:51] **Adam:** That's when we kind of, the community sort of standardized around the concept of responsive design. Like it was, it was not a thing before then. It didn't come from a company. It was actually, I'm probably going to get this wrong. I apologize in advance, but I believe it was a guy named Ethan Marcotte that like came up with this idea of like responsive design, do media queries and kind of gauge the size of the The portal or whatever the, the width of the page and use that to adjust CSS.

[00:39:23] **Adam:** That's just, it blows my mind. Like, you know, we've been doing this for so long, this kind of stuff feels, even though it's 15 years ago, or in this case, yeah, 15 years ago. it, it, it feels like it's been there the whole time.

[00:39:35] **Carol:** Yeah.

[00:39:36] **Adam:** It's so hard to remember the specifics of the world before. Yeah.

[00:39:43] **Ben:** The responsive design stuff is so interesting to me because. It feels on one hand, like there's a, a silver bullet that just solves that problem, which I don't understand meaning, meaning like I'm not particularly good at responsive design because I feel like I don't understand the magic, but then I'll listen to people like, Adam Wathen or Chris Coyier and they're like, the secret to responsive design is you just resize the page.

[00:40:10] **Ben:** And when it starts to look like crap, you put in a media query. Like that's the secret. There is no bigger secret than that. And I, I take such solace in that being like, Oh, all right. It's just like, it's just pragmatic. You know, it's not some sort of like calc of 100 VW minus 90 percent plus character with minus something.

[00:40:30] **Ben:** And I'm like, Oh, that's magic. I don't understand magic. What I do understand is I made it this narrow and it looks crappy. So let me add a media query. That I can understand.

[00:40:41] **Adam:** And then, you know, I think so many of us grew up on bootstrap or foundation or these other things that made it easy to fit into certain cookie cutter molds of responsive design, right? Like they give you like large screen width and medium and small and extra small or whatever and say, okay, well like these are the different break points that it has baked in and you can respond to those.

[00:41:03] **Adam:** That was nice. but it's frustrating when your app doesn't necessarily fit into that cookie cutter.

[00:41:11] **Ben:** Yeah. A hundred percent. Ah, I'll get there one day, but it's just feeling old.

## [00:41:17] Feeling Old

[00:41:17] **Ben:** We're on the topic of feeling old. So I recently learned that they're coming out with a Happy Gilmore 2 and I can't remember if I've brought this up previously.

[00:41:26] **Adam:** No.

[00:41:26] **Ben:** so we have a, a young girl, she's in high school, and she comes and she babysits the dog sometimes, like if we're gonna go out to dinner, she'll come over for two hours and, you know, pay her

[00:41:36] **Carol:** I love that.

[00:41:37] **Ben:** It's, it's the saddest thing in the world to admit publicly, but it's true. That's just like, that's the reality

[00:41:42] **Carol:** I love it. Yeah. Yeah.

[00:41:46] **Ben:** I don't know how to relate to teens. So I talk movies. That's all I know how to talk about.

[00:41:52] **Adam:** Hello, fellow teenagers.

[00:41:53] **Ben:** Exactly. So I was like, Oh, you know, I just heard she, she was babysitting the other day.

[00:41:58] **Ben:** And I was like, Oh, I just heard that they're making a happy Gilmore two. Have you seen happy Gilmore one? And she's like, I had never even heard of it. So I looked up the date. It came out and it came out like 16 years before she was born

[00:42:12] **Carol:** That hurts, right?

[00:42:14] **Ben:** I was like, what? Oh, that hurts me so hard.

[00:42:19] **Adam:** are so young.

[00:42:20] **Carol:** Yeah, I am. I made the realization that one of the doge people like they publish a bunch of their dates of births and like how old they were and stuff. One of them was born after my youngest was born.

[00:42:34] **Ben:** man. It is

[00:42:36] **Carol:** like, are you kidding me? I feel so old.

[00:42:39] **Ben:** Well, it's funny 'cause the, the thing that takes me out of some TV shows, so what's the, you know, like the, the, what they call the suspension of disbelief. You know, you gotta go in just sort of putting reality on hold. And the one thing that I feel like I can never get past is when I'm watching a show where Secret Service or the FBI is involved.

[00:43:01] **Ben:** And they have like a 22 year old woman leading a team on the FBI. And I'm just like, Oh, 22 seems really young to be leading a team at the FBI. What I want to see is some old mature person has been, you know, doing this beat for 40 years, and now they're tracking down a serial killer like that makes sense in my head.

[00:43:22] **Ben:** But like, now I'm like, Oh yeah, like you're just out of high school. You could be running a department of education or something. That's just, that's just the reality now.

[00:43:32] **Carol:** All right, next topic.

[00:43:33] **Adam:** Yeah, please.

## [00:43:34] Feature Flags and LaunchDarkly

[00:43:34] **Carol:** Yeah, so I have some good news. So, through all of our evaluations and. Through everything going on, we were finally able to officially schedule a demo with launch darkly. some of the changes that we've been doing, and the, the constant need to release to, handle changes in executive orders and just what's coming down, like.

[00:43:59] **Carol:** We've never seen things flow this fast, so we have to constantly hot fix our production environment. And that's not something we've had to do in the past. So it's really brought to light the need for feature development and for feature flags and for release flags and things that we can control when they go on.

[00:44:17] **Carol:** So like, Oh, we'll go ahead and release it, but we won't turn it on yet. And through that, you know, we've found a, like an internal application that's written their own. But ultimately, we definitely want to go with LaunchDarkly, but we're on a spending freeze, you know, we are cutting a whole bunch of people, the government across the board is just cutting everywhere they can.

[00:44:38] **Carol:** So we're on a full on spinning free. So I know we aren't going to be able to purchase LaunchDarkly anytime soon, or I have zero expectations of it, but we are looking to invest developer time into building our. Own feature flag, like, um,module to handle some of this in the, in the ground in between before we can make the purchase.

[00:45:01] **Carol:** So we know, like, we need to handle contacts and we know we need to handle users, but outside of doing it and like a table in the database, I really don't know a really, like, a good way to handle these flags that would allow us to, like, port forward. Okay. And I know that, you know, Ben, you've done a lot with LaunchDarkly and LaunchDarkly even gave you kudos for your book and our, you know, interview.

[00:45:25] **Carol:** Like they, they knew what we were talking about when we were, when we mentioned that we'd all read that. And, just kind of curious if you have any insight on, if you could do a few, a few small things and your homegrown feature system that would port forward or would be helpful. Do you have any?

[00:45:43] **Ben:** Well, Adam built his own feature flag system.

[00:45:46] **Adam:** I did. It's in CFML, which I don't know if that helps you.

[00:45:49] **Ben:** Heck yeah. Very.

[00:45:51] **Carol:** yeah. And so it's funny because I built this thing because I wanted to understand feature flags better and, and have the, be able to use them in our apps. And I was struggling, you know, like LaunchDarkly is, is spendy. It's expensive. Yeah.

[00:46:05] **Adam:** it's very expensive.

[00:46:06] **Adam:** and, and other systems, like you had found one Carol, I forget what it was called, but, and I tried for like a half hour to. I don't know, maybe a couple of hours. and I just couldn't get it working. And I was like, it shouldn't be this hard. I shouldn't have to fight it. So I'm giving up. and I, I just wrote my own.

[00:46:22] **Adam:** but I, so I went down this path and I started with like sort of the rules engine, right? So like you have a rule, like this applies to people on this environment or whatever. and, that turned out to be very, that's like the most interesting part. But that's like the for lack of a better word I'll call it like the client side of the feature flag server client relationship, right?

[00:46:43] **Adam:** Like your application server is the client of the feature flag server. so we have like a I have this thing that I wrote. I think it's called semaphore. It's on github. I can send you a link um,and it it even if you don't use it as is it would be Potentially useful just to like port the code over to whatever language you wanted to because it's got you know, like a rules engine Basically you you give it The long and short of it is you give it like the flag data, right?

[00:47:09] **Adam:** Like this is the flag I'm applying. This is the user is the flag on or off. Right.and it applies all the rules from the flag and, let you know, and that's interesting. But that, that CFC, when you look at it on GitHub, it's like, this is just the rules evaluation engine. The whole like storage and management of your flag data itself is entirely left to you.

[00:47:33] **Adam:** Like there's, there's no, it's not part of it. So that was like a separate thing that I didn't even realize I was taking on when I

[00:47:39] **Ben:** Very.

[00:47:39] **Adam:** writing that rules and just like, okay, now what, okay, now I have to have the data has to come from somewhere. I have to have an API. It's got to like push out updates.

[00:47:47] **Adam:** It's got to store the data over time. So that was a whole separate thing, but yeah, I'll send you a link.

[00:47:52] **Carol:** Yeah, I'd like that. Yeah, I think the big selling point to my customers. well, my customer is the user interface is their ability to manage it, but where we struggled kind of with the initial kind of view is. Doing a single feature view isn't super helpful. So like they want to make sure that they have the ability to see all their features and one view and like how they're applied.

[00:48:18] **Carol:** So I think our user interface for it is going to be our, our big time sink, honestly, and making it useful to our customers.

## [00:48:26] Exploring Cloudflare's Durable Objects

[00:48:26] **Ben:** If, if I can cross pollinate shows for a second. so I was just listening to syntax FM.

[00:48:32] **Adam:** Who's

[00:48:33] **Ben:** maybe, maybe it was this morning and they were talking about, or maybe it was last night, they were talking about full stack cloudflare development,

[00:48:40] **Adam:** I'm halfway through that episode.

[00:48:42] **Ben:** Yeah. It's a very interesting episode because I use cloudflare as CDN and I've started to use it as my domain registry and that's basically it, but they have so many.

[00:48:50] **Ben:** Other things now. And, one of the things that they mentioned, which sounded very interesting was something called durable objects. And I didn't fully understand what it was, but it sounds like it's some kind of in memory object that just seamlessly syncs via web sockets to a bunch of locations. And I don't know if you have to be like in a web worker for that to work, or if it could sync to anything, but it, it struck me that feature flags and durable objects somehow could be interesting together.

[00:49:24] **Adam:** That is a really interesting, I wonder if a durable object would be an interesting use case for, or I'm sorry, feature flags, if that would be an interesting use case for a durable object. So, I mean, obviously, I agree with you. If somebody's interested, go look for that episode of syntax. It's called, I think it's called full stack Cloudflare. So what I took from it is like, it's, it's its own sort of separate product that CloudFlare offers and it, it works with a bunch of their different things. you know, web workers or CloudFlare workers and, and a bunch of different stuff, but you can just connect directly to it. And so if you push an update to the durable object, not only will it automatically sync to anything that's listening, but then like that durable object just continues to exist.

[00:50:06] **Adam:** Even if your app like shuts down, right. You've got your CloudFlare workers. And you, you push data into this durable object and then nobody visits your website for two weeks and you get another hit and it comes back online and the data that you pushed into the CloudFlare or the durable object is still there as if it was in memory the whole time, which is pretty neat.

[00:50:25] **Ben:** Yeah. It sounded very cool. I have trouble visualizing what that actually means without looking at some code, but it just sounds like they're the Cloudflare stack is getting very impressive.

[00:50:35] **Adam:** I agree. Yeah. I, as I was listening to that, I was like, maybe I need to like, start thinking about, you know, build something here just to understand it all and how it all clicks together and whether it would be a good choice for me for some of my side projects in the future.

[00:50:49] **Carol:** Yeah. It's got my interest for sure. Yeah. I put a link in the notes. Is that the right podcast? It's.

[00:50:56] **Adam:** full stack Cloudflare. That sounds right. I'm going to click on it, but that sounds right.Yeah, that's it.

[00:51:02] **Ben:** the one thing that I always go back to though, and this is probably more just old man yells at cloud kind of a thing is I'm so used to in Docker having containers that represent systems that I understand, meaning I understand what ColdFusion is.

[00:51:18] **Ben:** I can spin up a ColdFusion container. I understand what Redis is. I can spin up a Redis container. I understand what MySQL is. I can spin up a MySQL container. But then when you have to deal with these worlds that are so deep and so abstracted, like Amazon's AWS or cloud flare, or like any of these just rich ecosystems, I feel like you're no longer in this world of, I'm just going to spin up a container from Docker hub.

[00:51:45] **Ben:** It's like, I have to install. The CloudFlare CLI, and then it just magically does what a web worker would do, but it's actually just mocked out locally because it's using like 90 percent of the same code that CloudFlare workers use. And there's just, I don't know if it's just like the control freak in me or something, but there's, there's like a, a inconsistency that I, that I don't love about it.

## [00:52:14] CSS

[00:52:14] **Adam:** Well, then is it time for another fun fact?

[00:52:16] **Ben:** let's do fun facts.

[00:52:17] **Adam:** Okay, we're going to continue moving backwards in time here to feel older and older. 1996 Is when CSS was introduced

[00:52:25] **Carol:** Oh my god.

[00:52:27] **Ben:** Yo,

[00:52:28] **Carol:** I still don't understand CSS, let's be real. Oh man.

[00:52:34] **Adam:** of one of those things that like we've had it for so long now. It just feels like Like intellectually I knew, and I kind of vaguely remember life developing stuff for the internet pre CSS, you know, using font tags and like

[00:52:52] **Ben:** table, like table with, with like no borders, but it has like one pixel padding with a background color.

[00:52:59] **Adam:** Yeah.oh man. And just like, so 1996, that would have been either, I guess it depends on when in the year, but like that would have been either my freshman or junior year of high school.

[00:53:12] **Carol:** 6th grade for me. Yeah, my, my years follow the year of 90, so it works out. Great. I can always know where I was. So, yeah, I was in 6th grade then, depending on where I may have been in 5th. Yeah.

[00:53:27] **Ben:** you know,

[00:53:28] **Adam:** It's just, we're so old. Oh,

[00:53:31] **Carol:** and

[00:53:32] **Ben:** I think back in these days. If you had a table, like a table tag to literally render data, it's like there were certain browsers where tables wouldn't inherit the CSS properties of the parent page. So like you might have Arial font on the body, but then inside of a table would still be like Times New Roman or something.

[00:53:55] **Ben:** So you'd have to, there was no inheriting.

[00:53:57] **Adam:** didn't cascade.

[00:53:58] **Ben:** yeah, it didn't cascade and it's just, it's one of these things like you live long enough and you, you no longer have a good sense of what's real and what's not real anymore because you can say, well, everything cascades, but then you put a, a button on your page and your button doesn't inherit.

[00:54:15] **Ben:** Your font family. It's still like a weird times, new Roman or a mono space kind of font. But will that be,

[00:54:22] **Adam:** You're not talking about now, are you?

[00:54:23] **Ben:** yeah,

[00:54:25] **Adam:** No, it does.

[00:54:26] **Ben:** maybe, maybe buttons do, but like text areas, if you put a text area on your page, it's not good. It doesn't inherit your font.

[00:54:32] **Adam:** There are, yeah. Inputs like form control inputs, are weird. They're like their own special use case thing, but

[00:54:40] **Ben:** But like maybe one day there'll be weird the way the data tables were weird. And people would be like, why are you setting a font on your input? You're like, bro, cause you need it. And they're like, bro, you haven't needed it in 12 years. I didn't know. CSS.

[00:54:55] **Adam:** got another one, Ben,

## [00:54:56] Testing and Real-World Analogies

[00:54:56] **Ben:** Yeah, I'll go with something that occurred to me the other day, and this is, let's call it Testing adjacent. So a hot button

[00:55:03] **Adam:** right in your

[00:55:03] **Ben:** the show. Yeah. Right. My strengths. So, I live in a, in a town that is near a river and you often have to go across a

[00:55:13] **Adam:** You said you live in a van down by the river

[00:55:17] **Carol:** I was going to say that

[00:55:19] **Ben:** funny. So. You have to get on this bridge to go across to the next town, which is where a lot of the shopping centers are, and the road that leads up to the bridge is single lane in each direction. And then when you get to the bridge, it remains single lane in each direction, but the speed limit goes from 55 miles an hour on the regular road to 35 miles an hour as you're crossing the bridge.

[00:55:42] **Adam:** because they don't want you to do sick wheelies as you go over the bridge.

[00:55:46] **Carol:** or die

[00:55:47] **Ben:** And it, it, it seemed like a wonderful metaphor and I'm not going to have the right words exactly to explain what I'm feeling. It seemed like a messy real world acknowledgement that certain parts of life are just more dangerous. And there's something about crossing a bridge that is inherently more dangerous, maybe the, you know, the margin for error.

[00:56:11] **Ben:** Not only do you kill yourself accidentally, but you kill like a bunch of people who hit you and then flip off the side of the bridge, like that kind of stuff. Like, there's like It's just, it's just a bigger chance that errors have a larger impact. So we're going to say, okay, you can go slower across this bridge.

[00:56:27] **Ben:** And it made me think about testing and how I think sometimes in the world of testing, we don't always acknowledge that there are parts of an app that are just less likely to break. Or if they do break, it's just less likely to cause harm. And the same way that when you go across the bridge, we know that's more dangerous.

[00:56:47] **Ben:** We're going to tell you to slow down. It's like in an app you say, okay, here's the really critical parts of the app. Okay. Let's put some tests around that. Because if you do hurt yourself, you might hurt other people too. So we're going to have different constraints and we're not going to say blanket statement.

[00:57:03] **Ben:** We have to reach 80 percent test coverage cost or code base. Cause like that doesn't acknowledge anything practical. That's just like a meaningless number. Anyway, the, the, the, I love when the world is messy and it teaches us things about how sometimes the digital world should also be messy, or we should acknowledge that the digital world is messy.

[00:57:27] **Ben:** And we have to lean into that sometimes instead of fighting it so hard.

[00:57:30] **Adam:** I agree. I have similar feelings. Like you're talking about the, you know, when the world is messy. the thing that that immediately brings to mind for me is like, anytime we try to categorize stuff, what is an amphibian, right? Like as soon as you try to say like, this is an amphibian and this isn't like the universe finds a way to like,you know, twist it so that like your, your rules become invalid

[00:57:58] **Ben:** right. Well, it's like, it's like what separates us from the animals. Like, well, it was thumbs. Well, what about all these animals that have thumbs? Well, it's using tools. All right. What about all these animals that use tools? You're like, well, it's doing social things. You're like, well, what about all these animals that clearly do social things?

[00:58:12] **Ben:** You're like, ah, we're, we're still great somehow, but

[00:58:16] **Adam:** yeah We're the only ones that managed to change the climate

[00:58:21] **Carol:** poorly.

[00:58:23] **Ben:** it is, it is fascinating. When you have to take a real world situation and model it digitally. And it's just, it's like, you want so hard to have all these absolute truths in the digital world. And there's just so many things can go wrong. Anyway.

[00:58:41] **Carol:** I don't know if it quite relates, but this is what I'm thinking of.

## [00:58:45] Pet Peeves and User Experience

[00:58:45] **Carol:** last week we lost internet at home and from that it caused a cascading problem of everyone who has AT&amp; T now also can't use data on their phones because the tower that services us. It's down because of too much traffic, right? So these sites and these apps that typically, you know, require so much data to load are being, you know, hit with no data availability to them.

[00:59:11] **Carol:** And there was no thought put into what happens on low data users. So I'm trying to just find out if AT&amp; T has an outage. And the first thing that's trying to load is this giant image and map of the United States they have. Where had they been? Oh, low data users probably shouldn't start with. Give me a map of the United States showing all the outage, right?

[00:59:35] **Carol:** Like low data, you should know we need to go a different route because they're never going to be able to load this page.

[00:59:41] **Adam:** Let's load a 20 meg looping video of our smiling customers,

[00:59:45] **Carol:** so sad. It's so sad. We just assume that things are going to be able to move fast now and we don't put any thought into what happens when we can't move fast and when things need to slow down.

[00:59:56] **Ben:** This is such a pet peeve of mine, specifically. So I live in an area where we do lose power occasionally, and we only have one internet provider and we're in a cellular dead zone. So this is a very real thing for me. And it makes my blood boil. It's not just that we. Expect everything to work. It's that there's just no nuance at all.

[01:00:16] **Ben:** Like how is the page that people have to look at to check to see if they have an outage, how is that basically not only like, not just a text only page, like it doesn't even load styles. Like it's just times new Roman enter your zip code. Yes or no. Like. It's crazy because someone was like, Oh, well it has to adhere to the brand.

[01:00:37] **Ben:** And then it has to fit in this template and you know, whatever reasons, but Oh, that one hits home. So freaking hard.

[01:00:44] **Carol:** Oh, and just to add to it, on AT&amp; T, if you want to look up your address, they don't let you type it in. You have to do one of their suggested values. So as I type in my full address, I still have to wait for them to return back a value to match my address. Angry. 48 hours of pure anger.

[01:01:03] **Ben:** this is like when there's a form where you have to enter a phone number or a credit card and you type it in with dashes

[01:01:09] **Ben:** and then it, and then you submit the page, it says like, please enter your credit card in a valid format. And you're like, bro, just take out the dashes.

[01:01:15] **Carol:** Yeah. You know. You

[01:01:17] **Ben:** Yeah, you know, dude, be, be better.

[01:01:20] **Adam:** Have I talked on the show about the pit of success

[01:01:25] **Ben:** I mean, I think so, but let's do it again.

[01:01:28] **Carol:** me.

[01:01:28] **Adam:** Well, maybe we'll I mean we're we're over an hour at this point so maybe we'll come back and talk about it on another episode, but basically, it's just this concept that we have at work that we've developed and the whole team uses it and it's just like Uh, you know, anything that we can do for the user, we should, and anytime the user does something wrong, it's our fault because we let, you know, we left that opportunity in the software for them, right?

[01:01:53] **Adam:** Like, if, if they brought down the whole database because they tried to run a gigantic, like, you know, 10, 000 column wide report over 30 years worth of data, what idiot let them do that, right? Like, that's our fault, not their fault. They were just doing what the software let them do. So we call it the pit of success.

[01:02:13] **Adam:** Push, push users into the pit of success. Set up boundaries, do things like the phone number, right? You can see it's 10 digits, just format it the way you want it formatted, right?

[01:02:24] **Ben:** Yo.

[01:02:24] **Carol:** Worse than getting to the submit and then not working as you type it in and suddenly you can't type any more numbers because you've used your space for dashes. That makes me very angry too.

[01:02:39] **Ben:** one more fun fact?

## [01:02:41] Browser History

[01:02:41] **Adam:** Sure, I got one. so early web browsers were just text based, right? I don't know if you ever, like, were on an old Linux server or anything, and you used Lynx, L Y N X. You could, this was like a text based web browser, right? It would, it would render the text of the page and it would have links and you could, you know, like push the number to go to that link, sort of thing.

[01:03:00] **Adam:** It was pretty interesting, but like, the first, what I would say is modern browser, like the browser, as we currently think of it, where it's, you know, it's got some window Chrome with features in it, but then there's just like a box in the middle that has the content of the page that you're looking at.

[01:03:12] **Adam:** And it's very mouse, friendly. That was the mosaic browser. and that happened again in our lifetime, 1993,

[01:03:21] **Ben:** Oh man. And mosaic, I think became, Mozilla, right?

[01:03:26] **Adam:** right? that's my understanding is, yeah, through some, some twists and turns became Mozilla and then Firefox.

[01:03:34] **Ben:** And then 30 years later, founder mode, cause, cause I think it was Andreessen Horow, Mark Andreessen wrote the first browser and he's the one who did the founder mode paper, I think. Right. I

[01:03:48] **Adam:** I, I don't know for sure. And I don't want to, you know, we, you know, how much we respect the, the, the truth and correctness on this podcast. So I don't want to spread misinformation.

[01:03:58] **Ben:** Oh

[01:03:58] **Carol:** I just say I miss Clippy?

[01:04:02] **Adam:** I have a, an error page in my, so like the, the 404 page in our app, just only in the admin view, cause you can only get away with so much like fun cheekiness in the public eye, but like our, our admin view, which is for our customers. Right. So, there's probably at any given school somewhere between 10 and a hundred people.

[01:04:21] **Adam:** That have access to this applicationand so if they flub up a url something like that, right the 404 view in admin it's this awesome really high quality animated gif of Clippy and it's like he's got that he's standing on the corner of the little yellow piece of paper and he's like spinning It's really it's it's sweet.

[01:04:41] **Adam:** And then the the text I put on the page is like, you know 404 reality failure the page you've requested doesn't exist in this reality. Would you like to try other realities?

[01:04:51] **Carol:** Perfect.

[01:04:52] **Ben:** Oh, clippy.

[01:04:53] **Carol:** Yeah,

[01:04:55] **Adam:** yeah, so mosaic 1993 I feel old I I need to go lay down now. So I

[01:05:01] **Ben:** You know, and it's, it's,

[01:05:02] **Carol:** it's my bedtime. Wow.

[01:05:04] **Ben:** I could just end on one thing, it's people keep saying on podcasts that AI is like the most revolutionary thing that's ever happened in our lifetimes and I'm like, I don't know. So many crazy things have happened, like really smart auto complete. I just don't, I feel like people keep saying it's the most amazing thing since sliced bread and I, and I just don't feel it.

[01:05:30] **Adam:** i'm i'm gonna have to go with like, Uber Eats or DoorDash or something. I can just, on my phone, I can just push some buttons and and Taco Bell will come to me.

[01:05:42] **Ben:** See. There you go. Heh heh

## [01:05:44] Patreon

[01:05:44] **Adam:** Alright, well then I guess, this is the part where I say this episode of Working Code is brought to you by Carol's new office mates Jim, Jack, and Johnny, listeners like you. enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon.

[01:06:00] **Adam:** Our patrons cover our recording editing and transcription costs and we couldn't do this every week without them special Thanks, of course to our top patrons Monte and Giancarlo. You guys rock. We really appreciate your support

## [01:06:10] Thanks For Listening!

[01:06:10] **Adam:** We're gonna go record our after show I'll try to make it quick, but I gotta for whatever reason as we've been having the show tonight I've had a whole bunch of different ideas of stuff.

[01:06:17] **Adam:** I want to talk about on the after show So quick teasers quick teasers. I'm gonna talk about my 1, 000 skydive, which I did this weekend

[01:06:23] **Ben:** What what? Heh heh

[01:06:24] **Adam:** Yeah, I have a really cool genus of frogs. I want to talk aboutUm, and there's a bunch of other stuff too. So if you want that and all kinds of other fun content, you can just go to patreon.com/workingcodepod, throw us a few bucks a month and that and more will be available to you. We'd love to have you. you can go to our discord workingcode.dev/discord, just a community. Totally free to join fun place to hang out. Like minded cool people. we'd love to have you. That's going to do it for us this week.

[01:06:55] **Adam:** We'll catch you next week. And until then.

[01:06:57] **Carol:** Even you guys who were born after emojis became official in 2010, your hearts matter.
