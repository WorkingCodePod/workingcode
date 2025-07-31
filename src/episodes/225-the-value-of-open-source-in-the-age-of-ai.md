---
title: "225: The Value of Open Source in the Age of AI"
description: "In this week's episode, the crew discuss the relevance and significance of open-source software in the age of AI."
date: 2025-07-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/225-the-value-of-open-source-in-the-age-of-ai/id1544142288?i=1000718835043"></iframe>

In this week's episode, the crew discuss the relevance and significance of open-source software in the age of AI. The open source community offers domain expertise, rigorous testing, responsive bug fixing, and community support. But when AI can generate code with proficiency, how does the value calculus change when deciding to install a new package, generate code with an AI, or simply do it yourself?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/225-the-value-of-open-source-in-the-age-of-ai.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** the, like the, the value of open sources even higher than it was pre ai because it is so easy to, you know, attempt to vibe code something useful, right?

[00:00:08] **Adam:** A, a high availability reverse proxy, I think was the thing that you had said, Maybe. Are you gonna bet your business on that? Or are you gonna bet your business on the project that's been around for 20 years and has a whole bunch of tests and a bunch of community support and people that are actually interested in, in making that work and fixing any bugs that come up

## [00:00:47] Intro

[00:00:47] **Adam:** Okay, here we go. It is show number 225. And on today's show, we are going to talk about what is even the point of open source in the age of ai. so, sorry, not sorry, AI topic, but you know, so we're trying to lean away from it as much as possible, but you know, that's what we wanna talk about.

[00:01:03] **Adam:** So that's what we're gonna talk about. Uh, to talk about it. Let's be honest.

[00:01:06] **Ben:** I think there might be something, you know, this is not something I came up with. This is something I've heard echoed on some other podcasts. So we're

[00:01:14] **Adam:** oh God. It's another, we're

[00:01:15] **Ben:** a little me also.

[00:01:15] **Adam:** podcast episodes. Uh,

## [00:01:18] Adam's Triumph

[00:01:18] **Adam:** but first as usual, let's start with our triumphs and fails. Looks like it is my turn to go first and, it's an easy one for me this week, triumph. I am taking Thursday and Friday off this week and this weekend my family is going down to visit my brother in Maryland.

[00:01:33] **Adam:** So, just easy, super excited. A little, little mini vacation. It's not that far of drive, it's like a three hour drive, taking the dogs. We're bring, we're actually, we're bringing our camper. We have a pop-up camper

[00:01:43] **Adam:** and we're,

[00:01:44] **Carol:** the camper.

[00:01:45] **Adam:** we're gonna, we're gonna like pop it up in his driveway and we'll just basically like, it's, it's a place for us to crash overnight.

[00:01:51] **Adam:** And then, we'll just, you know, go inside during the day.

[00:01:55] **Carol:** I guess he doesn't have an HOA that doesn't allow that.

[00:01:58] **Adam:** He does not, I asked him specifically about that and he's like, yeah, no, that was a top priority on the, the shopping list. Um, just, no, HOA, I don't, I don't think it was actually a top priority, but it was definitely up there.

[00:02:09] **Carol:** Yeah.

[00:02:10] **Adam:** easy one for me. What do you guys got going on? How about you, Ben? What do you got going on?

## [00:02:14] Ben's Fail

[00:02:14] **Ben:** I'm gonna go with a failure. This is a light failure here, but I am just continually surprised. And the failure is that this continues to surprise me, which is that there are things in this world that I feel very strongly about, and people time and time again, prove to feel very strongly about it in the exact opposite direction.

[00:02:35] **Ben:** And, uh, I just forget how, gosh, darn subjective everything is,

[00:02:42] **Tim:** Language.

[00:02:42] **Ben:** I know. Sorry. I, the, the, the, the thing that's top of mind for me was. Sometimes I'll see something in code and it just triggers feelings in my head. And then I say things on LinkedIn, maybe sometimes those things are more cryptic than I intend them to be because half the conversation is, is like playing out in my head.

[00:03:01] **Ben:** And that doesn't necessarily occur to me to clarify as well as maybe I should. But I went in on LinkedIn and I said that it's crazy to me when I open up a class or a component file and the methods are just seemingly in complete disarray in terms of where they are defined. And I've worked on many teams now where people, their default behavior is just to open up the component and add the new method to the end. And I'm like, that's just bonkers. Like how do you live life like that?so I had said that

[00:03:34] **Tim:** Quite easily

[00:03:35] **Ben:** everything should be alphabetical.

[00:03:37] **Carol:** No.

[00:03:39] **Tim:** shut your mouth.

[00:03:40] **Ben:** I feel super strongly about that. And then, okay, then I did go back and I did clarify that it's not. Blanket alphabetical across the board that I do section things like my constructor is always at the top. And then, my lifecycle methods, if they apply, are after that. And then my public methods are after that, and then my private methods are after that.

[00:03:59] **Ben:** But within those sections, those methods,

[00:04:02] **Adam:** for yourself,

[00:04:03] **Ben:** those method, it's not work. I, these files aren't that

[00:04:07] **Adam:** It is work. It takes time to, okay, this method is gonna be named this, and so I have to go find the two methods that it belongs between, but it, it also depends on which section it's in.

[00:04:15] **Ben:** because otherwise

[00:04:16] **Adam:** It take, it adds four minutes to.

[00:04:18] **Ben:** chaos.

[00:04:20] **Adam:** Well, look, I'm gonna speak as somebody who is a reformed person who did very much of the same of what you're describing.

[00:04:27] **Adam:** Like, you know, there were strong feelings about what belongs at the top right. Constructor, or, I don't, I never thought about putting lifecycle methods at the top, but, and then, you know, like Publix and privates separated, and then I started using better tools that make it a lot easier to find the method in the code that I'm looking for.

[00:04:47] **Adam:** You know, if, if you, in VS code, you do like Command P and you start typing

[00:04:51] **Ben:** I use sublime text and Command. P does the same thing. I can jump to a method, but that's the, the accessing of the method is a separate conversation to me than the, than the cleanliness of the file itself.

[00:05:05] **Adam:** you're, I think you're conflating cleanliness with, anal retentive, uh, expressed.

[00:05:14] **Tim:** With a hint of OCD.

[00:05:16] **Ben:** I, I don't know. It's like it because, okay, the, like there's either no strategy, which is to me the same as just always putting it at the top row, always putting it at the bottom. That's, I mean, I guess that's a strategy. Okay. So there are a couple strategies. There's the always put new things at the top or the bottom.

[00:05:33] **Ben:** There's the always alphabetize like I do. And at least those are predictable. Like if I have to add a new method, I know exactly where it's gonna go. In either of those three approaches. The one that seems the most crazy to me, and this is like a lot of people on LinkedIn argued for this approach, is that they group things like, based on how they're used and like the grouping of like, and to me that's the,

[00:06:00] **Tim:** isn't that what Uncle Bob said to do?

[00:06:02] **Ben:** I think that's the most bonkers of all of them.

[00:06:04] **Ben:** 'cause if of all of them that is the most least predictable and like, least repeatable. 'cause. 'cause it just makes no sense.

[00:06:13] **Adam:** I'll, I'll give you the one thing that your system, Ben does do the like, where it could quote unquote save you time. Is that making that decision, okay, where does this belong? Where I want want to create it. It saves you that, you know, it makes the decision for you short of that every other use case, it adds time.

[00:06:32] **Carol:** Yeah, and, and like for me, I like when I open the PR and what you've changed is just at the bottom of the section. So like if you've added a new public piece, then it's at the bottom of all the other public ones. I don't have to go figure out like what you were doing in the middle of the file. I could just be like, okay, new public method, what's going on?

[00:06:49] **Carol:** And then I also know that things at the top probably haven't been touched in a while. Things at the bottom are the newer things, so I kind of can go, where are there problems at the old code functions? Fine. You broke something in this bottom section,

[00:07:02] **Tim:** And it, and it limits, it limits merch commits too, or merch conflicts.

[00:07:06] **Ben:** all crazy. We're just all crazy in our own unique ways. And, and, and that's my failure is like I keep wanting to believe that there is some truth that we can sort of all coalesce around and we're all just banana pants and, and it's like, you know, because you could argue for,

[00:07:26] **Tim:** Well, case in point. Case in point, you're on LinkedIn and actually reading stuff. That's, that's to me was, that was the takeaway for me. I'm like, who actually looks and reads at AT stuff on LinkedIn? LinkedIn is like the most worthless social media. It's ridiculous. Not only there, just so that people know I have a job.

[00:07:43] **Tim:** That's it. I don't care.

[00:07:45] **Ben:** I, okay. So like,

[00:07:46] **Ben:** just to have a more polarizing juxtaposition for a second. To me, the idea of just randomly putting a method randomly, you know, like some crazy subjective set of rules about where you should put a method is like to me saying, well just and paste the indentation that you had in the other file.

[00:08:09] **Ben:** Like, who cares if it's tabbed and you pick cop then like, paste in space, indented things, like you can still get to it, no problem. Like the, the, like there's an inherent,

[00:08:19] **Adam:** gonna fix that for you, automatically prettier is

[00:08:20] **Ben:** like there, there, there's an inherent value in cleanliness and, and to me the location of the method is part of what it means to be cleanliness.

[00:08:32] **Ben:** It's okay. Like another,

[00:08:33] **Tim:** your idea of cleanliness is not another person's idea of cleanliness.

[00:08:37] **Ben:** but it's like, okay, you could have,Fusion, as an example, is a case insensitive language. So you could name your methods one way and you could call them another way. Like you could define them using,

[00:08:51] **Tim:** Like a,

[00:08:51] **Ben:** all caps and you could invoke them using all lower case or, you know, just a random case. But you shouldn't.

[00:08:57] **Ben:** And the reason you shouldn't is not a technical one. It's that it's, it's just cleaner. It's cleaner to keep it consistent. If there's anything that I, I, I haven't liked about ColdFusion, it's, it's the case insensitivity of it. It's like it's really nice at first, but then at some point you're like, ah, I just wish things were consistent

[00:09:16] **Tim:** Mm-hmm.

[00:09:17] **Ben:** because consistency is nice.

[00:09:19] **Tim:** Well, if you like consistency, then ColdFusion is not a language for you.

[00:09:23] **Adam:** So I actually wanna, I, I wanna circle back just a little bit. Tim, you had mentioned that putting everybody always adding new methods at the bottom of the file is gonna reduce the chances of merge conflicts. I think if multiple people are committing to that file, it's gonna increase the chances of merge conflicts.

[00:09:35] **Adam:** However, if you, if that's what you're optimizing for, reducing merge conflicts, everybody should, every time just randomly select a spot in the file,

[00:09:44] **Carol:** No.

[00:09:45] **Adam:** like roll a die, roll a D 20.

[00:09:50] **Ben:** Oh, weird. So that's me. I'm just always surprised at how surprised I am.I will, uh, I'll now

[00:09:57] **Tim:** you're good. You don't need to do the B one.

[00:09:59] **Ben:** yeah, yeah. I'll yield, uh, I'll yield the mic over to Carol. Carol, what do you got going on?

## [00:10:04] Carol's Triumphs

[00:10:04] **Carol:** Oh man. I'm gonna give a two big triumphs this time. Uh, one is a personal one, and that's that I've started working out again. So I am on the street, uh, working out every day for two weeks, and it's, it's a good thing. Well, every workday on the weekend we play golf and that's a workout in itself. But I'm working out every day and I'm very happy.

[00:10:22] **Carol:** I even told my husband today, I was like, today's the first day. I feel like I have more energy in the afternoon just from getting up and working out. Like I know that that's what's causing it. Like everything is just flowing better. Like work is better. I feel better. It's just, it's a good thing.

[00:10:37] **Tim:** Nice.

[00:10:38] **Carol:** And then my second triumph, this kind of a team triumph, for my.

[00:10:42] **Carol:** Like smallish team that we have now, um, we, uh, were forced to migrate to HyperV for our on-prem resources, because our contract with VMware was cut, so that's expiring soon. So when we did the first rollover, it was in the middle of a lot of transition with people and it took us like a solid week to get stage rolled over just because so many unknowns, things we didn't know about.

[00:11:09] **Carol:** People had set things up that we couldn't find and it was awful. well, we did train this week in our training environment. Took, just a little over a workday. So about a day and a half of work, no overtime, no craziness. And half of the day to day was just spent me searching down the problem. I didn't need to search down, like, you know, those rabbit holes you go into, but I'm just super happy that this migration only took, you know.

[00:11:35] **Carol:** A fraction of what the stage cutover did. So yay for us and for my team for getting it ironed out. And now hopefully the production one will be even smoother.

[00:11:44] **Ben:** Heck yeah.

[00:11:45] **Carol:** Yeah, big, big wins.what about you, Tim? What do you got?

## [00:11:50] Tim's Triumph

[00:11:50] **Tim:** So I'm going for a triumph as well.

[00:11:52] **Carol:** Yay.

[00:11:53] **Tim:** so we've been trying to move a specific customer, and I've talked about this customer before. I love them, I love them dearly, but they are special children.that, so we try to move them to another processor because it processes that are on, we've been trying to get off of them for years 'cause they're terrible.

[00:12:10] **Tim:** Their rates are high. And, so finally after two years of negotiation with this guy who's, who runs the company, who's a lawyer, who likes to ask a billion questions and then forgets them and then ask them again, he finally signed today. And so he can finally get 'em off this, this old terrible, old platform that we have and move to the new one.

[00:12:32] **Tim:** So that I was, yeah, I almost took the day off today to celebrate

[00:12:37] **Carol:** Just to celebrate. That's awesome.

[00:12:39] **Tim:** I the stuff to do. So, yeah. So yeah, that was, that was, that was pretty awesome. It just, yeah, just, it was such a slog and I was just tired of it and I was just getting to the point where I just don't care anymore. And I'm like, do what you want.

[00:12:51] **Tim:** Go away. I don't, if you weren't like a, if you weren't like one of our top three customers, I would just tell you to go bye-bye. But yeah, so super happy about that. So, finally got it over the finish line. Now we just gotta actually move them. So

[00:13:08] **Ben:** Heck yeah. Very nice.

[00:13:10] **Adam:** So, okay.

## [00:13:10] Open Source in the Age of AI

[00:13:11] **Adam:** Let's talk about, what is the point of open source in the age of, a one, I mean, ai.

[00:13:18] **Tim:** Yeah. Gotta watch out for a once taking people's jobs.

[00:13:21] **Adam:** Ben, this was kind of your idea. Why don't you get us kicked off

[00:13:23] **Ben:** Yeah. And to be clear, this is not something I came up with. This is, this is something I've heard expressed on several different podcasts, which is the idea that here, two, four, so much of the software world has operated very heavily on open source software, whether it's, web servers like Nginx and Apache, or it's huge server, server lit applications, or even frameworks like, Lucy, CFML, or I, I don't know, I don't know much about that many different worlds, but there's, there's a lot of open source software.

[00:14:00] **Ben:** ImageX, I'm sorry, not ImageX. What's the one that everyone uses? image Magic and, and, I dunno. I mean the list goes on and on there. Like literally you go to npm js dot. And there's like a trillion packages that you can install for free. And one of the questions that's been coming up on various podcasts with regard to AI is when you can just ask the AI agent to generate code for you, what is the incentive for people to build and maintain open source software?

[00:14:31] **Ben:** and I, it's a very interesting question 'cause it also gave me pause to think about the litmus test that I kind of go through when it, when I decide is this something I want to build versus something I wanna just quote unquote buy. But buy in this case might just mean installing off of a, maven for Java packages or NPM for, JavaScript or APT get for, you know, any number of other things.

[00:14:56] **Ben:** Or, you know, home brew, brew install, you know, how many things do I wanna build versus buy? And I don't think that AI at least yet has. Changed my feelings about any of it. Like my instinct today is not to have AI write things that I would historically have installed today. I'm still leaning towards installing everything that I would have before.

[00:15:25] **Ben:** And maybe that's my personal perspective, but I just don't have faith yet that the AI is actually doing that good. And I don't know if it's ever gonna get to a point where I can say like, chat GPT build me, a high availability reverse proxy servers that I don't have to install NGINX,

[00:15:45] **Adam:** Well, yeah, I don't know. For, I'm, I'm trying not to give the answer that's just like a total shutdown. Like, you know, this is a kind of a yes and

[00:15:56] **Ben:** yeah, yeah. Yeah.

[00:15:57] **Adam:** right? But to play the devil's advocate, I think based on what we've seen so far, the, like the, the value of open sources even higher than it was pre ai because it is so easy to, you know, attempt to vibe code something useful, right?

[00:16:14] **Adam:** A, a high availability reverse proxy, I think was the thing that you had said, which, hey, maybe it can do, you know, maybe it can do that with a, with a one sentence low context thing. Maybe. Are you gonna bet your business on that? Or are you gonna bet your business on the project that's been around for 20 years and has a whole bunch of tests and a bunch of community support and people that are actually interested in, in making that work and fixing any bugs that come up for free.

[00:16:41] **Adam:** And, and, that you don't have to pay one of your employees to do. Right. Even if that employee is ai, it still takes time to review the code and, and decide that you're happy with it.

[00:16:53] **Ben:** I, so, I dunno, does anyone ever get ads for masterclass when they're watching their YouTubes and whatnot? So

[00:16:59] **Carol:** no, because some of us pay for YouTube premium, so we never get ads on YouTube.

[00:17:04] **Adam:** That's right. I haven't had ads on YouTube in years.

[00:17:06] **Ben:** oh, it's so jelly. That's

[00:17:08] **Carol:** You do. You wanna join my family, Ben? I have a spot open.

[00:17:13] **Ben:** Steve, my daddy.

[00:17:14] **Carol:** Yeah.

## [00:17:17] The Value of Domain Expertise

[00:17:17] **Ben:** Um.so one of the masterclass ads that I get is for, Neil deGrasse Tyson, and I don't even know, I don't even know what his class is for, but the, the preview of it is him saying like, the greatest hurdle we have is, it's like, it's it's like knowing enough to be confident or like not knowing enough to be confident, but knowing enough to know that we don't know everything.

[00:17:43] **Ben:** And I feel a little bit like the, the AI hype right now is people are getting lost in, like, they feel that, oh, just because I can ask chat GPT to look up something or to find an association, that the value of domain expertise is no longer a thing. And I think that's gonna be dangerous. There are people like Adam's saying that have dedicated so much of their free time to deeply understanding an area and dedicating time to fixing it and looking at the vulnerabilities that come out and pushing updates to fix those vulnerabilities.

[00:18:22] **Ben:** Like it's, I feel like people get very hand wavy about like, oh, the AI will just continue to get better and this just won't be an issue in the future. But it's just really hard to imagine that it, that even if AI can do it, that you as the consumer of AI will have the wherewithal to ask it to do all of the things that it should be doing

[00:18:44] **Adam:** Yeah, I completely agree.

[00:18:46] **Carol:** Okay, old man. Now you should probably sit down for a minute, so. I agree with a lot of like what's been said, however, like the thought of giving up an open source project does not like at all vibe with me. So I think I'm with you a lot. the open source sided thing, like I do love the community. I love that I can go to someone who knows what they've been doing, which is what Adam said, right?

[00:19:10] **Carol:** Like, they have that, those years of experience, they understand it. What I see coming down the road are the projects that get generated using AI that then become open source type platforms that grow that community support. That's when I start trusting the projects more. So once they have the coverage, once they've been vetted, that's when I think that.

[00:19:32] **Carol:** I could then utilize whatever is being generated, but the thought of just generating something new, the time it takes us just to create test coverage, isn't worth it for me to say, Hey, do I think what you're doing is accurate when I can go pull in another library that already has the vetting from the community to know that it's trustworthy?

[00:19:54] **Ben:** Yeah.

[00:19:55] **Adam:** And, to build on that, the, there has been so many cases of people finding direct, like blatant ripoff, of like stolen open source code provided, as answers in, AI generated code. And what that says to me is that it was trained on open source code. Okay? and then the fact that it's trained on open source code, that tells me that training it on the docs isn't good enough, right?

[00:20:22] **Adam:** So the, the tools that we use, the, the frameworks, the platforms, the languages are going to continue to grow and evolve. God, I hope so. I hope we don't get stuck with our current tools forever. but. And so if, if the tools evolve and the docs, you know, get updated with them, but then there's no new open source code, then the, the tool, the AI tools, the models aren't going to be trained on any more code written specifically for those new features, new platforms, new frameworks, et cetera.

[00:20:54] **Adam:** And so the, the AI just won't be able to give decent answers, I don't think. Yeah, that's speculative, but sure. Why don't we go with it?

[00:21:03] **Tim:** I mean, in the current state of things, I, I see AI is very myopic. It's, it, it's very tactical. It doesn't really have a strategy, right? So it's, it's a problem you set before and it solves that immediate problem. It doesn't think beyond that problem, right? And so with open source, you have people who are thinking about not just the problem you're trying to solve, but also, you know, how do we make this secure?

[00:21:28] **Tim:** How do we make this, do we make this easy to maintain throughout the life cycle? Now, not saying that AI won't get there, but right now it seems very much about you give it a problem, it solves that immediate problem, but it doesn't really care about anything else. It doesn't take those other things into consideration.

[00:21:45] **Tim:** So I, I see that as a problem.

## [00:21:48] The Value of Packages

[00:21:48] **Ben:** Well, speaking about making things easier to maintain and, and this is where I do diverge from my original thought a bit, which is. For large projects that do require, let's say a substantial amount of domain expertise. I do continue to want to defer to the experts and hopefully to the expertly curated packages that they've built.

[00:22:08] **Ben:** Where I don't care so much is for the very small things that people may have historically installed. I know Adam, I think you've mentioned a couple of times previously, some guy named, cinder Sous or there's some guy who has like a million packages. And I'm, I, from what I've heard you explain, it sounds like a lot of those packages are probably like 10 lines long

[00:22:32] **Adam:** Or one. Yeah, like tiny.

[00:22:34] **Ben:** So things like that I could very much see, ah, you know, I'd kind of rather just own that code in my repository so that I don't have to worry about someone else updating it if there's an issue or I just like to be able to look at it like, I'd like to be able to open that file and not have to dig through a node modules folder to find it that I can understand.

[00:22:53] **Adam:** Well, I don't,

[00:22:55] **Ben:** Push back. Push back.

[00:22:56] **Adam:** yeah, yeah, yeah. Lemme push. So, yes, the, the module itself might be one or, or you know, let's say less than 10 lines long, which. A lot of people look at that and they scoff and they're like, why don't you just copy and paste that code from a blog into your thing? Or why don't you just write it yourself?

[00:23:11] **Adam:** Well, the answer to those questions is because yes, it's five code lines of code, but it also comes with 30 different test cases and this guy who is paying attention to it, you know, if somebody files an issue and when he does release an update, you'll be notified that there's updates 'cause you're using depend upon and you know, like maybe there was a zero day that was found in the code and nobody knows until somebody shares it with the community.

[00:23:35] **Adam:** Mm-hmm.

[00:23:36] **Ben:** Ah, it's, it's a good point. I have no, I have no like, and, and I guess that kind of loops back and, and, and touches on the whole topic itself. It's just that. I, I, to me, there's nothing yet today that I really want to have the AI right, that I would have historically wanted to install. I still feel very strongly that the things I don't feel confident in are gonna continue to be the things I want someone else to write for me.

[00:24:00] **Ben:** And when I say someone else, I don't mean ai. I

[00:24:03] **Adam:** So, I wanna, I kind of want to go against myself here just very briefly. You know, the, the thing I just said, defending the, like one line modules. I do believe in that. I also believe that there is a lot of value in low or no dependency libraries, right? So those, those one line things, those are usually no dependency things.

[00:24:22] **Adam:** Or, you know, if I'm choosing between two different libraries, that that both might solve my problem. All other things being equal, I'm gonna go with the one that has fewer dependencies.

[00:24:31] **Ben:** Yeah. I tend to agree with that as well. I'm, I'm a big fan. Well, I don't know. Like, I've never been, I can't even say, I was gonna say I've never been a huge installer of things, but that's, that's not true. I think there are swaths. It's like, when it comes to the JavaScript world, I think I'm much more apt to install something because of the, the ease of NPM and the prevalence of packages.

[00:24:54] **Ben:** But when it comes to the cold fusion world, you know, specifically the server side world, I'm very slow to install things just because I don't know that much about the Java world. I mean, yeah, there's no package manager and it just feels like, I don't know, more complicated. And,

[00:25:12] **Adam:** I tried to solve that problem. Nobody wanted to participate.

[00:25:16] **Adam:** do you guys remember Ramen?

[00:25:18] **Tim:** I do.

[00:25:18] **Ben:** remember. What is

[00:25:19] **Adam:** So I, I had created this open source library a million years ago. it was a, it was A-C-F-I-D-E extension, so it only worked on a CF, which might have been part of the problem. I don't know, but that was what I was using at the time.

[00:25:30] **Adam:** Right. But, so if you're not familiar, A-C-F-I-D-E extension is, is a, it's like a, a library or a plugin you can drop into a specific folder and then it adds a link in the CF administrator sidebar, right? It adds navigation stuff and it like will load a page in the CF administrator, where you could do stuff.

[00:25:48] **Adam:** And so I had made one, I called it ramen 'cause I was naming everything after food at the time, taffy Ramen. And, the idea was very much like a, almost like a kind of NPM inspired, but no CLI. It was just like, people can register, you know, you just make a pull request. There's like a, it was probably an XML file actually, it was probably a JS file, but you know, like a, just a listing of all the packages that were available because let's face it, there's not gonna be that many packages in A-C-F-M-L ecosystem that a single JSON file is gonna get to unwieldy.

[00:26:19] **Adam:** and. To, it's a like, announce the existence of your package or whatever, and then it could like, it would download and install it through, like download it from GitHub or whatever. You just like single click to download and it, you know, I of course made it work for Taffy and I think there were like two or three other things that got added but never went anywhere.

[00:26:37] **Adam:** And that's fine. I'm not sure about it at

[00:26:40] **Carol:** No clearly.

[00:26:41] **Tim:** Clearly

[00:26:42] **Ben:** That's cool though. Good.

[00:26:45] **Tim:** has something similar to that.

[00:26:46] **Ben:** Yeah. For box,

[00:26:48] **Tim:** Yeah, ForgeBox.

[00:26:48] **Ben:** but, I dunno. I, I just. I'm not an AI skeptic because I do get, I get value out of it from a conversational standpoint. I have, it helped me brainstorm things. I just, I have not yet had the aha moment of, of like code level do this kind of thing in, in a way that feels repeatable. You know, it feels like so many magical incantations when it, when it works and it does exactly what I want, it's still a surprise. I'm like, oh, wow, that was cool. It's not like, oh, yeah, of course it would do that because that's what I told it to do. Yeah.

[00:27:26] **Adam:** I would say that like, you know, a, a very high percentage, 80, 90%, something like that of my usage of AI for writing code is the like auto complete style, right? I'm, I'm in the IDE, I'm typing, I pause to think and it's like, oh, here's what you're thinking about as code. Like actually, yeah, that's exactly what I was looking for.

[00:27:43] **Adam:** That boom done, tab accepted, you know, like so single keystroke to write five lines of code. Great. The other thing that I really am enjoying is the, I feel like the models are getting better at noticing you making changes that are repetitive, right? Like, I'm adding this variable to a struct in five different places.

[00:28:02] **Adam:** After the second one, it's like, Hey, just hit tab and I'll, I'll make it in the other three 'cause I can see this what you're doing and boom. Done.

[00:28:10] **Carol:** I just usually hit the tab, take its variable name, and then write my own code.

[00:28:14] **Adam:** Hmm.

[00:28:15] **Tim:** Yeah.

## [00:28:16] AI Tools and Human Collaboration

[00:28:16] **Tim:** I, I mean, I, I think because we call it ai, we, we assume it's intelligent because that's what the eye stands for, but it, it seems to work better in the process of assisting a human as of right now, right? So you have to have a human intelligence and, and even, you know, we're talking about open source.

[00:28:35] **Tim:** You know, I, I think it would accelerate people who are working in open source to work with AI to add to their open source projects quicker, but. As of right now, it's like, it's, it's not a replacement for an intelligent human being. It, you know, maybe you'll get there and then yeah, we'll have a very, very different society once that happens.

[00:29:00] **Tim:** 'cause that's gonna be, an inflection point in human history when that actually happens. But as of right now, it's, it's just a tool that kind of helps you do thing, helps a smart person do smart things more quickly, and helps a dumb person do sometimes dumb things even quicker.

[00:29:19] **Carol:** So I, I would tell you something, and this is a secret, so nobody tell anyone. I, um,

[00:29:24] **Tim:** No one listens, so we're good.

[00:29:26] **Carol:** I looked at Target. I looked at our GitHub commits and I was like, oh. So many people have been like, oh, right, I am. Like who's actually committing code? It's like number one, committer. It's me. That's not good. 'cause I spend a lot of time doing a lot of other stuff.

[00:29:40] **Carol:** Second committer, it's like authored by GitHub and I was like, uhoh. I was like, go by. Liz producing a lot of information for us right now, so,

[00:29:50] **Ben:** Is Carol literally running the government right now?

[00:29:53] **Tim:** I know, right? I think she is.

[00:29:55] **Carol:** it's not a good day for you guys.

[00:29:57] **Tim:** Hmm. I'd rather have you than other, than other people whose initials, whose initials are em.

[00:30:03] **Carol:** you. Thank you.

[00:30:04] **Ben:** you know what's crazy though, though, even? Even though I know that the AI is just a statistical model and it doesn't have feelings, and I know that every single time I prompt it, it's so easy to fall into this sense that it knows what it's talking about.

[00:30:20] **Tim:** Mm-hmm.

[00:30:20] **Ben:** And like, I took a screenshot of something. What was, I was, I was, you know, having a conversation with it and asking it to push back I, I said like, oh, I kind of wanna do this, yada, yada, yada, yada.

[00:30:31] **Ben:** And I said, please push back if you think this is a bad idea. And it responded with no pushback at all. This is a great idea, and you're building a very solid control layer.

[00:30:40] **Carol:** Oh my God. Is your yes, man.

[00:30:42] **Ben:** I know. I was like, oh, I even, I even asked it

[00:30:46] **Carol:** Mm-hmm.

[00:30:46] **Ben:** and it idea so good. I'm like, no, no.

[00:30:49] **Carol:** Mm-hmm.

[00:30:51] **Tim:** I, I, it, it was out of context and I really need to ask Adam Cameron about it. Maybe you guys saw it on Discord. Somehow he got his AI to like curse at him,

[00:31:02] **Adam:** Oh yeah,

[00:31:03] **Carol:** Oh, I

[00:31:03] **Tim:** like, that's pretty amazing. Only

[00:31:06] **Adam:** some of them, some of the tools like, let you specify, this is how I want you to interact with me. You know, I want you to be gruff. I want you to do whatever. Like, treat me this way.

[00:31:18] **Tim:** Abuse me, baby. pay extra.

[00:31:21] **Adam:** Be my hater.

[00:31:23] **Tim:** Exactly.

[00:31:24] **Adam:** so I wanna, I wanna kind of talk about something too. Like, so I was, it's, this started from thinking about like, o of course the people that write open source software are going to leverage the AI tools to get more done, right? They're gonna, maybe it'll be easy for them to like, fix bugs that come in, maybe like easier to implement features, whatever.

[00:31:41] **Adam:** Like that's how we're all using it. have listened to several podcasts in the last like week that all kind of talk about, maybe it's not the podcast. Okay. So there's like. There was a thing Sam Altman said not that long ago where he's like, I can't wait for the day where I can just wake up and AI has already read my inbox and my to-do list, and like pre, pre-prepared a bunch of email replies.

[00:32:05] **Adam:** I just have to like proofread them and hit yes, yes or no. Whether or not this is something I want to go with, maybe make modifications, whatever, that sort of thing. But like where AI is kind of like, pre-running his morning day or his morning routine and that and, and other similar things. And what it, what it strikes me as is, what is the, there's a word.

[00:32:25] **Adam:** I don't know. It's not coming to me. Basically, this is a promise that's been made over and over and over throughout life, right? Like when we, when we got cars, it was like, oh yeah, you'll have so much more free time because now you don't have to spend three weeks traveling across the country. You can get there in three days.

[00:32:39] **Adam:** Well, no, now you're just gonna get there in three days and you're gonna start your job two and a half weeks earlier. Right? Like.

## [00:32:45] Efficiency Gains and Workforce Impact

[00:32:45] **Adam:** The, the ai and we've, we're seeing this already, like AI tools are here, we're expected to use them, and we're expected to get work done faster because we're using them. So this like fallacy of additional free time and the ability to relax and have a better life because these tools are working for us, it's, it never has arrived and I don't think it ever will.

[00:33:07] **Adam:** Like whenever there are efficiency gains, we're just going to expect more

[00:33:11] **Tim:** companies, companies are just gonna keep laying people off. Like, well, we, we don't need 10% of our workforce now because everyone's getting done 10% faster, so let's just keep cutting people.

[00:33:20] **Carol:** I mean, you'd be like, we were told like, Hey, yeah, we're gonna implement more AI things, but that doesn't mean you're gonna see like a decrease in work. Actually. We're just gonna make sure that we're producing more than we can right now. Like we're just gonna make sure that we are getting more out the door.

[00:33:35] **Tim:** Doing, doing more with less people.

[00:33:36] **Carol:** Mm-hmm.

[00:33:38] **Ben:** Let me throw something crazy out here and, and feel free to immediately shoot this down

[00:33:43] **Carol:** Done

[00:33:43] **Ben:** after I say it.

[00:33:44] **Tim:** Out. Okay.

## [00:33:46] The Value of Meaningful Code

[00:33:46] **Ben:** So one thing that people keep bringing up, and it's never quite, it's, it's never quite connected with me. They'll say something to the effect of, I really like doing the interesting coding, but I like letting the AI do the crufty coding for me.

[00:34:06] **Ben:** I don't like to do the grunt work. And if I can go off and do a a, a parallel for a second years ago, Clark and I, Clark Valberg and I were talking to his rabbi and we were talking about, moral quandaries. And I remember saying, asking the rabbi something to the effect of like, sure, that makes sense for regular questions, but like, what about questions of morals?

[00:34:32] **Ben:** And the rabbi said there, there's no such thing. There's no difference between a moral and moral questions. Every question is one about right and wrong.

[00:34:41] **Adam:** Mm-hmm.

[00:34:42] **Ben:** and like there's nothing special about what you think a moral question is, and

[00:34:47] **Adam:** A hundred percent agree

[00:34:48] **Ben:** to bring that back into this, like crufty gruy code versus regular code, I, I don't think it connects with me because I feel like all of the code I write is meaningful.

[00:35:02] **Ben:** And if it's not meaningful, there's meaning in the fact that it's not meaningful. Meaning like, if I'm doing something and it feels like, oh, this is just a lot of friction, like, I wanna understand why I'm feeling that friction. And maybe that's a symptom of something that maybe, okay, maybe that's an architectural problem and now I have to refactor the code so that it's, it's less frictional.

[00:35:23] **Ben:** Like, who is it? Kent Beck or someone said, make the make the hard change easy. No, what is it?

[00:35:29] **Adam:** make, make the change easy, then make the easy change.

[00:35:32] **Ben:** Yeah, it's like if something is hard, let me figure out why it's hard, try to see if I can come up with a way to make it easy so that going forward, it's just easy. And so I, if you asked me today like, oh, articulate the Grunty code that you don't wanna do, I don't have a good answer for that. I don't know what I would articulate there.

[00:35:51] **Carol:** Because you don't write tests.

[00:35:53] **Ben:** Yeah,

[00:35:56] **Carol:** I'll tell you almost everything I write, I highlight. I say pound, sign, hashtag, whatever you wanna call it, right? I say section, and I say generate tests for this.

[00:36:06] **Ben:** so the moral of the question, the moral of the story there is just don't write tests. That's what I'm hearing. And all of your code stays

[00:36:13] **Tim:** that, that is what you would hear, but that's not what she said.

[00:36:16] **Ben:** So I don't know. Okay. So, so Carol says the test is the, is the crufty. Coach doesn't wanna write. Like, what do you guys consider the Crufty code? You don't want to do? Is it, is it more just the repetitive stuff? Like you're saying, oh, I need to rename this variable in a bunch of places, and like, why should I have to locate those?

[00:36:32] **Adam:** No, because I have tooling. That's not AI that does that for me.

[00:36:36] **Carol:** Yeah, it's easy enough.

[00:36:38] **Adam:** tools, right? Rename this variable. But I, I get what you're saying. I don't have an answer that's immediately jumping to mind. But there, like, there are tasks that when they land at the top of my to-do list now I go, okay, this is an easy, like, I'm gonna ask AI to do this, and I'm trying to, to figure out what the delineation between, I'm gonna do it and I'm gonna make AI do it is, and I, if I figure it out, I'll let you know, but I, I don't know.

[00:37:05] **Ben:** All right. Let, let, then let's plant that seed then, and maybe next week it'll

[00:37:09] **Ben:** have

[00:37:09] **Carol:** up with some.

## [00:37:11] Challenges with AI and Monitoring Tools

[00:37:11] **Carol:** I will say one, for me, it's not really like a task that pops up, but I will get the like, Hey, go review all these logs. And I'm like, oh, well they all have all these different timestamps and I'm trying to compare things. I'm like, oh hey, what's the Reg X to go give me like to find anything that looks like a timestamp.

[00:37:29] **Carol:** And I'm like, just generate that for me. And then I just find and replace everything. And now my compare is a lot simpler. Or if it's like a, like a, I'm trying to find, I'm like, find me everything. Just get rid of it all. Call it test. And now let's see what the logs compare look like.

[00:37:44] **Ben:** And I'll tell you the, the domain of logging and let's, let's call it like monitoring in general. That also feels to me where I. I would love it if a monitoring and logging tool like a Datadog or a Century, or a New Relic, if they want to build AI into their anomaly detection, for example, like I am all for that because their domain experts and what it means to monitor a system, and they're gonna have the best understanding of how AI can maybe be used to enhance that thing.

[00:38:19] **Ben:** What I feel like I never wanna do is have to use AI to write a tool to better understand my monitoring tools.

[00:38:27] **Ben:** Like I'm not a monitoring expert, you know, I don't understand anomaly detection and statistical models. Like, and this is where it's like, I don't want the AI in the same way that I didn't want Kubernetes to make me a DevOps person.

[00:38:41] **Ben:** Like I don't want AI to make me now a, you know, a monitoring

[00:38:45] **Adam:** Vibe Ops.

[00:38:46] **Ben:** Yeah. Like experts are still experts. I still wanna have a guy. I say guy in like the comical sense, like I got a guy for that. like I want a guy for things. I don't wanna have to be that guy. Anyway, that's all I got.

[00:38:59] **Adam:** Should we wrap it there?

[00:39:00] **Ben:** Let's wrap it there. Keep it short as

[00:39:02] **Ben:** I am prone to do.

## [00:39:04] Patreon

[00:39:04] **Adam:** then this episode of Working Code is brought to you by LinkedIn, the only social network where Ben actually participates and listeners like you. if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:39:17] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks of course to our top patrons, Monte and Giancarlo. And I just wanna point out, you know, it's rarely mentioned, it's an accessibility thing that we do. We do have transcripts of all of our episodes.

[00:39:32] **Adam:** They're right there in the show notes pages. so if that's something that would, be beneficial to you, that's where you can find it. And that is thanks in part, in large part to our lovely patrons. So thank you guys so much for helping us make that possible.

## [00:39:46] Thanks For Listening!

[00:39:46] **Adam:** Yeah, we're gonna go record the after show, which is one of the perks of becoming a Patron.

[00:39:51] **Adam:** so tonight on the after show, somebody checked in some code with a different encoding, and that also is a crime. So, you know, we're just gonna continue the, the theme of crimes in the after show. and, we're gonna talk about smart home stuff among other things. Anyway, If you wanna help us out, you can go to patreon.com/workingcodepod.

[00:40:10] **Adam:** We'd love to have you join the team.we'd also love to have you come join our Discord. It's, just a great place to hang out, and chat with like-minded developers. you can do that by going to workingcode.dev/discord. That's gonna do it for us this week. We'll catch you next week.

[00:40:24] **Adam:** And until then,

[00:40:25] **Tim:** You are not crufty, awesome and your heart matters.
