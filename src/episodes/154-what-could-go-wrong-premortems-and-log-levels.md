---
title: "154: What Could Go Wrong? Pre-Mortems and Log Levels"
description: "We talk about Premortems; and, about how important it is for a company to create a safe space in which people can talk about failure and about the reasons failure might occur. We also dig into Logging strategies, structured logging, and role of different log levels."
date: 2023-11-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/154-what-could-go-wrong-pre-mortems-and-log-levels/id1544142288?i=1000635670785"></iframe>

On today's show, we continue reflecting on the [4-part series on "Failure"][freakanomics-failure] produced by the [Freakanomics radio podcast][freakanomics-radio]. This time, we talk about Premortems; and, about how important it is for a company to create a safe space in which people can talk about failure and about the reasons failure might occur. We also dig into Logging strategies, structured logging, and role of different log levels. And, how we can best consume logs in a way that makes them valuable without being too noisy.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[freakanomics-failure]: https://freakonomics.com/podcast/how-to-succeed-at-failing-part-1-the-chain-of-events/
[freakanomics-radio]: https://freakonomics.com/series/freakonomics-radio/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/154-what-could-go-wrong-premortems-and-log-levels.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** If you can't find one thing that you would like to see changed about your company, you should be fired.

[00:00:04] **Ben:** I tell my wife five, six times a day. What's wrong with her? Do

[00:00:10] **Tim:** customers, if we could just keep the money and get rid of the customers, things would be great.

[00:00:16] **Carol:** Firewalls.

[00:00:18] **Adam:** DNS. Um,

## [00:00:21] Intro

[00:00:21] **Adam:** Okay, here we go. It is show number 154, and on today's show, we're going to talk about premortems and the lost art of log levels. Or we're going to try to, at least. Once again, we've got the whole crew here. Welcome back, Carol. Sorry you weren't feeling well last week.

[00:00:54] **Carol:** Yeah, lots of traveling, you know, always get sick from that.

[00:00:58] **Adam:** Oh yeah. And Tim, it looks like it is your turn to go first to start us off with our triumphs and fails.

## [00:01:04] Tim's Triumph

[00:01:04] **Tim:** Triumphs and fails. Yeah. So I don't know if this is a, I guess it's a triumph, nothing bad has happened. So it's been very quiet week. You know, everyone's, you know, seems to be gearing up for Thanksgiving. You know, customers really haven't been contacting us. We're, yeah, we're working on stuff, but it's like, it's kind of built, building lots of tests.

[00:01:24] **Tim:** So that makes Adam Cameron very happy.

[00:01:27] **Ben:** Actually, I have a question because you work at a company that's owned by a company that owns lots of companies. Do the holidays get normalized across all the companies or are the companies essentially independent operators within some

[00:01:43] **Tim:** The companies are independent operators, right? So they, they, they don't replace the, I mean, there's definitely layers above us, but yeah, each company runs its own. Like for instance, even within our company, we have two, the people that actually do the, the, bank settlement, their holiday schedule is different from the developers.

[00:02:01] **Tim:** So they have to be at work whenever the banks are working, but when the banks are closed, they get those days off, but it unfortunately means they don't get a, we get a whole week off for Christmas. so they don't get that cause they gotta be. Someone has to be there to settle to the banks each day that they're actually open.

[00:02:16] **Adam:** Type out the flat file to send for over

[00:02:20] **Tim:** good old, good old, good old American financial system.

[00:02:23] **Adam:** FTP with humans in the middle. Yeah.

[00:02:26] **Tim:** Wow. Yeah. so yeah, it's been pretty quiet. and then on a personal front, so I, I, my, I no longer have any minors in the house.

[00:02:35] **Carol:** Awww.

[00:02:36] **Adam:** Got all that cobalt ore out of your basement

[00:02:39] **Tim:** exactly. Yeah. Yeah. Now, my, my daughter, my youngest, my daughter, Lily, she turned 18 Friday.

[00:02:45] **Tim:** So

[00:02:46] **Ben:** And then you just kick her out.

[00:02:48] **Tim:** yeah, exactly. I warned them. I don't know if they'll, I don't know if they'll ever leave. And I'm okay with that. I told him, you know what? It's, you know, life's hard. If you, you always got three hots and a cot. So.

[00:03:03] **Adam:** Yeah, as long as you don't bother me.

[00:03:05] **Tim:** Exactly. Yeah.

[00:03:06] **Adam:** I

[00:03:06] **Ben:** This is something that I always find very fascinating. In my lifetime, the idea of kids growing up and then leaving the house, you know, roughly around 18 or, you know, college or post college, that's, that's always been the sort of status quo, the expectation to a large degree. But, from what I hear on the radio, that's actually a relatively recent concept from a, from a, you know, a human timeline standpoint.

[00:03:32] **Ben:** Like, I think only in the last like 60 or 70 years has that become a thing that multi generational housing used to be like the way to do it. And, the way everyone did it.

[00:03:44] **Tim:** Yeah, that's a hundred percent. Yeah. You look through history, people, you know, stayed with their families a lot longer time, but they would get married and sometimes still stay. yeah.

[00:03:54] **Ben:** when I hear about that, all I can think about is how much money I'd be saving.

[00:03:58] **Carol:** Free daycare.

[00:04:00] **Ben:** free daycare, free room and board that just the cost of everything is divvied up across so many people. It's very appealing, actually. So.

[00:04:08] **Tim:** And I think it, you know, is expensive as things have gotten these days. I think that people might start swinging back toward that. The 20th century, I mean, we saw a huge amount of wealth after World War II that just came into the country. You know, we're, we're spoiled on, super spoiled. That's not the norm throughout history, like you were saying, Ben.

[00:04:30] **Adam:** not to go off on a wild tangent, but I mean, that's a big part of the argument that you hear from, polygamists, but also like people like kind of sharing a house, right? It's like, you know, two or three couples living together as a household, like kind of permanently,

[00:04:48] **Carol:** Yeah, I mean, it'd be great if I only had to cook dinner on Monday nights and Thursday nights, you know? Like, I could easily cook whatever I'm cooking for six people. Instead, I gotta do it every night.

[00:05:00] **Tim:** All right. So you're looking for roommates? Is that what I hear you saying? You

[00:05:05] **Carol:** looking for wives. Let's be clear. Yeah.

[00:05:08] **Tim:** a wife for you, not, not for your husband.

[00:05:10] **Carol:** Oh no, I don't share. I don't

[00:05:11] **Tim:** Yeah.

[00:05:12] **Carol:** Yeah.

[00:05:14] **Tim:** That's cool. Anyway. So that's me. I don't know if that's a, I guess we'll call that a triumph, but yeah. Proud of my girl. And, what you got Adam?

## [00:05:22] Adam's Triumph

[00:05:22] **Adam:** I'm going to go with a triumph. when I first, when this first happened, and I like wrote it down in my list of things to consider for triumphs and fails. I wasn't sure if I was going to call it a triumph or a fail, but as of now, when I decided to use this one, I'm going with it as a big triumph, and that is that, you know, I had this problem and I went to go solve it, and it became an exercise in yak shaving, which, if you're not familiar, is basically like the, the...

[00:05:47] **Adam:** I won't reference the TV show because probably one in five people out there will get it, but, you know, you go to do one thing, but in order to do that one thing, you need to do another thing. In order to do the other thing, you have to do a third thing. In order to do the third thing, you have to do a fourth thing.

[00:06:00] **Adam:** It just becomes this, like, giant sprawling thing when really all you wanted to do was, like, you know, fix a squeaky floorboard, right? And, the triumph here is that I did this. I made not only the small change that I wanted to make, but all of the yak shaving that it encompassed, with zero issues.

[00:06:19] **Adam:** Because we had automated tests, for this, like, particular part of our product. We, you know, I've talked at length about how we don't have good enough tests everywhere, but we're starting to, like, grow, and as we add more pieces, we add more test coverage. And, you know, I needed to make this change, and it was a significant change.

[00:06:36] **Adam:** I was adding config caching. So we have, a bunch of satellite microservices, and one of our more centralized microservices is config, right? So we have a bunch of config saved. And it ex, it's exposed inside of our VPC over an H-T-T-P-A-P-I. It's a lot of letters, um, and, and things, you know, microservices and the monolith and everything hit make HTP requests to that service to get the config settings that they need in order to do their jobs.

[00:07:04] **Adam:** And we realized at one point were like, we are pretty much DDoSing our own config service. In order to make our apps run, like we're, we're getting to the point where we're like,

[00:07:14] **Tim:** The call's coming from inside the building. Get out now.

[00:07:18] **Adam:** yeah. And so we're like, as we're kind of having this discussion, like, should we set up auto scaling or just like have multiple instances of the config service running?

[00:07:28] **Adam:** We're like, you know, what if we just added like a five minute cache on the thing in the module that does the config lookup? So if you're, if it's running, and it's hitting the same stuff over and over, then it'll just. Pull from the cache instead. And again, you know, I had to, a lot of dominoes had to fall to make that happen, but, it's working fantastically.

[00:07:50] **Adam:** And I deployed it on Friday evening with, high confidence because the tests all passed and I didn't have to worry about it. And it was a nice quiet weekend and it was just like triumph on triumph on triumph, man,

[00:08:02] **Ben:** Very cool.

[00:08:03] **Tim:** We did that with the API that you wrote, Adam. Taffy. but rather than five minutes, we have a config call that, you know, it's basically it's a config file reader, but you know, we just do it on framework reinitialization.

[00:08:16] **Tim:** So if we reinitialize it, you know, we know when we're adding to the config file, so you add the config file, push the changes up and then just run a framework reinitialization and it grabs the latest stuff, works good.

[00:08:29] **Adam:** know, once again, tests prove their value.

[00:08:33] **Tim:** Mm hmm.

[00:08:35] **Adam:** Yeah, alright, so that's it for me. how about you, Ben?

## [00:08:37] Ben's Triumph

[00:08:37] **Ben:** I am also going to go with a triumph, which is that I, at this point, have some content for every chapter in my book. Uh, on Feature Flag, so I'm, I'm feeling pretty pumped about that, and to, to the point where maybe I might try to have some sort of a Cyber Monday

[00:08:56] **Adam:** Ooh.

[00:08:57] **Ben:** kind of a thing.

[00:08:59] **Adam:** Now, are you gonna do like a beta release or just pre sell, and people can wait till it's done to

[00:09:05] **Ben:** I, I think I could do a beta release. I, you know, I need to do a read through, yeah, I need to do one or two read throughs of the book to, to make sure that it's not just totally incoherent stuff sliced together chapter wise. but yeah, I think, there could be some value there. So

[00:09:23] **Tim:** How many chapters you got?

[00:09:24] **Ben:** 29, I think is what it was. I mean, you know, it's, it's not a, it's not like a novel. It's not, it's not massive chapters. Some of the chapters are only a couple of paragraphs really.

[00:09:34] **Tim:** Mm hmm.

[00:09:35] **Ben:** But, yeah, I'm pretty excited. I got to start thinking about pricing. I haven't even thought about anything to that degree.

[00:09:41] **Ben:** I, I, I saw, happened to see someone on LinkedIn just recently released a book and they're charging like. 34 or something like that, which is higher than I had thought about charging for my book. so anyway, that, that kind of

[00:09:55] **Adam:** No,

[00:09:56] **Ben:** now

[00:09:56] **Adam:** charge 35 for it. 34. 99, 33. 99. That's a totally fine. Now, if we're talking about like, you know, beta price and early access sort of thing, it's, it's, it's a weird situation because like on one hand, these are the most enthusiastic people, right? They know about it and they're like frothing at the mouth like me to get at it.

[00:10:16] **Adam:** and so I'm more likely to go ahead and spend that 35 than your average schmuck off the street who's like finds it on Google. Right? But at the same time, there's the concession of like, it is early and it is unpolished and like, maybe

[00:10:29] **Ben:** that's the thing too, because there's zero professional polish here, meaning that a lot of the books that I see are being published by. You know, O'Reilly and PactPub and, and Pragmatic Programmers, where they have editors and they have people who advise on how to put stuff together and illustrations and book covers.

[00:10:52] **Ben:** And I don't have any of that. So I'm just like jamming out here as someone who happens to know how to do some stuff programmatically. And, the question then becomes like, how much is that polish worth financially speaking?

[00:11:04] **Adam:** Well, I mean, I'll tell you right now, years into the existence of my book, this is just on total cruise control. I don't even think about it for holidays or anything. I charged 19 for the e book and 29 for the paperback.

[00:11:18] **Ben:** All right. That's actually really helpful. That kind of gives me some sort of a, a gravity, you know, to, to hang around.

[00:11:25] **Adam:** And I mean, to be honest, I, I, you know, having read very little of what I can see in the screenshots of your book. I think yours is going to be more valuable of a book than mine, right? Value based pricing. What is somebody going to get out of it?

[00:11:41] **Ben:** We'll see. All right, cool. Well, so I'm excited.

[00:11:45] **Tim:** you have a name for the book? You have a title?

[00:11:46] **Ben:** I have been calling it Feature Flags. It's Feature Flags from Concept to Cultural Revolution is the subtitle.

[00:11:56] **Tim:** Okay.

[00:11:57] **Ben:** I didn't, I'm not good at naming things.

[00:11:59] **Adam:** it's a good place to start, but hey, listen, the original, original title for my book was RestWebAPIs, colon, the book

[00:12:11] **Carol:** Well, my husband fell in love with your dedication page.

[00:12:15] **Ben:** Thank you. I, so I, for, for people who have not seen it, I was toying around the idea of having a dedication page that said, dedicated to my wife, who reminds me that I can earn it was like dedicated to my wife who tells me that I can do anything to my dog who loves me unconditionally. And to my editor who reminded me that I can't only mention my dog, but I, I, I'm going to in the, in the official one, I'm going to remove the thing about the editor and just keep it wife and dog, you know,

[00:12:45] **Carol:** Oh

[00:12:45] **Ben:** better, better PR that way.

[00:12:48] **Adam:** thus far, you are the only editor, right?

[00:12:50] **Ben:** Oh yeah, it is a, yeah, a hundred percent, a hundred percent. exactly. But, I don't know, I, I would also love to get someone to review the book. I mean, that's a thing people do, right? Like, so have someone review the book and leave notes and then they can be, you know, mentioned in the book as, as a reviewer.

[00:13:09] **Ben:** That's the thing I think,

[00:13:10] **Tim:** this, your beta readers will probably give you a lot of feedback. They're almost like reviewers, editors.

[00:13:17] **Ben:** Yeah. So, so one thing I thought, you know, I have all these random ideas that go through my head. I'm like, one thing that I thought would be, how would it be insane to, so right now it's in Markdown and then I turn it into HTML and I render that on the page. Would it be crazy to then just copy all of that HTML, you know, like Command A, Command C, and paste it into a Google doc?

[00:13:40] **Ben:** And then people who are sort of beta readers give them access to the Google doc so they can literally come in and highlight and leave comments. Is that, is that just asking for trouble?

[00:13:51] **Carol:** I mean, couldn't you do that in the get repo too?

[00:13:54] **Ben:** Well, I don't want to give people access necessarily to the code that's building the site only because I don't know, that feels too much, too much behind the, the curtain. Although I could also, you know, also every individual line in the book, every paragraph is just a single line. And then that gets really weird.

[00:14:17] **Ben:** I think with PRs they look a little strange.

[00:14:20] **Adam:** So I love where your heart is at there. and maybe let's have a separate discussion offline so that we don't consume podcast

[00:14:26] **Ben:** Yeah. Yeah. Yeah. Yeah.

[00:14:27] **Adam:** I know of a tool to help with this. And. And, you know, the, the point is, I like, I love the idea, right, of being able to like, give them a, a dynamic commenting place.

[00:14:39] **Ben:** So that's me, Triumph. I'm pretty happy about that. I'm excited and, kicking it over to Carol to bring us home.

## [00:14:46] Carol's Triumph

[00:14:46] **Carol:** Yeah. I'm gonna go with a win to you guys,

[00:14:48] **Ben:** What Fort Way

[00:14:49] **Carol:** I know, right? Well, a way to come back. So, like a week ago at work, I. Kind of made a comment to my supervisor that I don't have any work to do because my new team isn't really spun up yet and we don't know what we're going to be working on or how many people I need to hire.

[00:15:08] **Carol:** So I was like, if you know of anything that anyone's working on that Maybe I could go help with, that would be great. So, I start working with a team who does nothing but Azure projects. And, I get tasked to handle a new chat bot that they're trying to initialize for internal users only. So it's like, Hey, are you having a, like, problem logging in?

[00:15:30] **Carol:** Cool. What kind of user are you? Like,

[00:15:32] **Tim:** Oh, does it have

[00:15:33] **Carol:** little more. Don't you wish? I love Clippy. I miss Clippy.

[00:15:39] **Adam:** It looks like you're trying to log in.

[00:15:40] **Carol:** Yeah, are you? Cause maybe you are. But anyway, so, today after working on this, like I said, like maybe a week or so, I finally have the bot able to talk to the app code and vice versa. We get some messages back and forth. And the big deal is that it has to be on a private network. It can't be publicly exposed anywhere because of controls above me.

[00:16:02] **Carol:** I have no say in lots of things I do now, apparently, which is fine. I'm not going to complain. But, it has to be on a private network, which made it very hard to do any work off the VPN and how to actually handle it. And then whenever I was running the project locally, the, CyberArk or the cyber ops team is like, Oh, you can't execute code.

[00:16:23] **Carol:** It's not allowed. So for the week, I've been testing all of this in Postman because that was all I could do. So today I finally was able to get all of my exceptions through and I can run the code locally and I'm able to get the connection to work. So the next step is when I get back from my work trip is I'm going to work with the, program office and start working on their actual input database through like Cognitive Language, which is another Azure project.

[00:16:51] **Carol:** Or another, like Azure tool, I guess. I don't really know what you call it. Anyways, and they're going to build out more of their dictionary for the, what the replies automatic are and what the AI does and all of that. So it'd be cool learning that too, when I get back.

[00:17:05] **Tim:** Is the, is the bot is, is this an Azure bot

[00:17:08] **Carol:** Yep. It's an Azure bot. Yep. It's an Azure bot, which is an app service, which is just a web interface that I then send my message to and it connects to the bot, sends it over and sends it back to the app service.

[00:17:23] **Tim:** Very cool.

[00:17:27] **Ben:** can't remember what podcast I was listening to just yesterday or the day before. I think it was some, some technology podcast and they were talking about a company where the entire support team in the call center tried to unionize. And so they fired everybody and replaced their entire support system with a chat GPT based language model and, uh, was letting it run.

[00:17:50] **Ben:** And then apparently discovered that it was giving people false advice and they had to shut it down.

[00:17:56] **Carol:** Oh, geez.

[00:17:57] **Adam:** Surprise, surprise.

[00:17:59] **Carol:** Yeah. Yeah. That's me. Winners.

[00:18:03] **Ben:** Good for

[00:18:04] **Adam:** so it's a good week for us. So, Ben, what are you planning on killing?

[00:18:10] **Ben:** right.

## [00:18:10] Pre-Mortems

[00:18:10] **Ben:** So I'm, I'm sure that many of us at work have. Taken a project to completion and then it was successful or it was less than successful. And at the end you have what's usually referred to as a post mortem where you do a retrospective. Yeah. You do a retrospective on how things went and what things.

[00:18:33] **Ben:** You know, better than expected or not as well as expected and what we may have been able to do in hindsight to have improved the outcome of the process. And that's all done after the fact. There is a version of that that actually takes place before any of the work is done at all. And that is, I believe, referred to as a pre mortem or a pre post mortem.

[00:18:55] **Ben:** And the idea is you're getting ready to. Start a project. And before you start, you say, okay, now imagine that we have a crystal ball and we're looking into this crystal ball. And the crystal ball is telling us that in six months or 12 months, when this project is done, it will have failed. And this is not up for debate.

[00:19:16] **Ben:** It a hundred percent sure is going to fail. So now our job in this pre mortem is to explore all the reasons. Why our project failed. And it's a very powerful tool because it frees people up to have negative thoughts. especially this is very freeing for people who are perhaps lower in the pecking order of the organization.

[00:19:43] **Ben:** If you can imagine, you're talking about getting a project going and all of the, the architects and the senior developers are saying, Oh, this is going to be great. This is going to work. And then we'll use this tool and that's going to work. And some new engineer or junior engineer is like, yeah, what about such and such?

[00:19:58] **Ben:** But they don't feel confident about bringing it up. If you can start the conversation by leaning into the idea that failure is guaranteed, it allows people to throw out those negative thoughts without feeling like they're going to be naysayers or reprimanded.

[00:20:15] **Adam:** So is this about, is this about, anticipating what could go wrong so that you can build with that in mind to prevent it?

[00:20:23] **Ben:** absolutely. A hundred percent. It's a, it's kind of, you know, turning over all the rocks and finding all of the, the creepy crawlies that may not have been, apparent. I, I really only have one hands on experience with this. And we've talked many times on this podcast about work and about how there is the legacy product at work, and there is the modern product and I handle the legacy stuff.

[00:20:45] **Ben:** Well, we, you know, we call that V6 and V7 at work, before the. Building a V7 started, we actually did a pre mortem to talk about what could go wrong. And it was a very, very frustrating process for me because almost, almost underscoring the importance of the pre mortem, there were people in the conversation who kept wanting to talk about.

[00:21:09] **Ben:** All of the things that would go right, that we'll do this with Golang and performance will be improved. And we'll do this with microservices and we can scale independently. And I kept arguing with people, why are you focusing on the positive outcomes? Like we've already talked about the positive outcomes.

[00:21:24] **Ben:** That's, that's the reason you guys want to do this in the first place. The reason that we have the pre mortem is to talk about all the that can go wrong. And anyway, that was my personal perspective, but as Tim alluded to in last week's episode, Freakonomics Radio did a recent four part series on failure, the art of failing gracefully.

[00:21:44] **Ben:** And in one of the episodes, they actually interviewed the guy who coined the phrase pre mortem. I think it was He did it for the military or the Navy or something. And he talked very specifically about that, that it is only supposed to be about the reasons things failed. And I just felt so vindicated that my anger at all these engineers who wanted to focus on the positive outcomes, their, their enthusiasm was misguided in this particular context and that it should have been negative and I just.

[00:22:10] **Ben:** I can look back now and laugh at them quietly.

[00:22:15] **Carol:** Well, I had read an article about this not long ago, so I went to go look it up. I'm like, where did I find this at? Because like, my favorite part of it was in the center of it was a picture of a dog, like, wearing glasses. And it was like, what if I told you there were no stupid questions? So it was like, it really is like, imagine going into it as a junior engineer and you're like, Oh, well, how do these connections work?

[00:22:35] **Carol:** Like, how could this even be a thing? Well, it's up to your architects and to your, your top level people to be able to explain the infrastructure to people. So there really are no stupid questions. So if they understand after like, Hey, this is how it's going to work, then they're good. But if now they pointed out a flaw, then you really know there's an issue.

[00:22:54] **Ben:** Absolutely.

[00:22:56] **Adam:** Can you, like, give some sort of a hypothetical but concrete example of a type of thing that you might bring up at one of these?

[00:23:04] **Ben:** I think things like the cost of maintenance or the financial component of new architectures or new technologies, or the number of people that might have to be kept on staff in order to maintain. What's been built or, you know, like the number of different technologies that are introduced. I don't know if I can think of anything like super concrete other than to say it's like whatever little Wiggling thought that you have in the back of your head where you're like, maybe this is not a great idea.

[00:23:38] **Ben:** This is the time to bring it up.

[00:23:40] **Adam:** So, okay, it sounds like this is more of a, not so much like a B imaginative, but more of like a If you're having any doubts whatsoever, like, it's an airing of grievances, right? Like, just let's get it out there and, and make everyone aware that somebody's thinking about this.

[00:23:58] **Ben:** Yeah, absolutely.

## [00:24:00] Avoiding Getting Too Imaginative

[00:24:00] **Tim:** I wonder how you avoid getting into, we talked about premature optimization, right? So if you start getting really creative with the

[00:24:09] **Carol:** What ifs?

[00:24:11] **Tim:** You know, it'd be like, you know, you know, what, what if a cosmic ray does a bit flip and, you

[00:24:16] **Carol:** Uh huh.

[00:24:17] **Ben:** flips.

[00:24:18] **Tim:** elects the wrong person? you know, how, how do you avoid getting out of this?

[00:24:23] **Tim:** Cause I've never heard of this, this before. This is my first time hearing about pre mortem. so yeah. How, how, how's that avoided? Do you know?

[00:24:30] **Ben:** That is a great question. I, I would only hazard a guess that the goal is not necessarily to solve all the problems that brought up, that get brought up. I think it's more about making sure that all of the things are at least acknowledged and considered. And then everything becomes a trade off, you know, maybe this is something that gets brought up.

[00:24:52] **Ben:** It's a possibility. It's not worth the effort that it would take to solve that problem, but at least, at least we knew about it and we considered it and we decided not to do it. I, I think that is at least a value add beyond, we didn't even think to consider this in the first place. But I agree with it.

[00:25:11] **Ben:** There has to be a line drawn somewhere. Otherwise you just, you, you, it becomes so overwhelming that you can't take the first step forward.

[00:25:19] **Adam:** this is definitely something that takes some discipline, right? It's so hard when you get an idea and a project in front of you and you're like, okay, let's go. You know, it's like, you want to get that fingers on keyboards and start, you know, producing code. Cause that's what we do, right? We, that is the measurable output of our work.

[00:25:36] **Adam:** And so much of What makes code good is the immeasurable parts of the job.

[00:25:44] **Ben:** And, and also, you know, very much to your point, as I've been, as I've matured in my career, I have begun to see the value of action that we spend so much time as organizations, hand wringing and debating this and debating that, and then not doing anything. And you realize that the people who can just do something are actually.

[00:26:07] **Ben:** quite amazing.

[00:26:09] **Adam:** Yeah. It doesn't have to be perfect. It just, just has to be done.

[00:26:12] **Ben:** Right.

[00:26:14] **Carol:** I feel like it also opens up the door for like a safe environment to speak of things breaking, right? Like we so often, you know, start building our project and it doesn't work. And rather than talking about it, we bang our heads on our keyboard for two days, trying to figure out what could possibly be wrong, or if it was normal to talk about the failures and what could happen.

[00:26:36] **Carol:** Then you ask those questions a lot earlier and you understand that failure is just part of being a developer.

[00:26:44] **Ben:** Yeah.

## [00:26:44] What's the Output?

[00:26:44] **Adam:** if I can throw out an example of maybe something, that I'm thinking of, right? So again, a hypothetical project, but it's a concrete thought, right? So let's just say the, the rough plan, I don't know exactly where this, premortem falls in the timeline of, of decision making, but. You know, let's say we're, we've decided that we're going to build this thing and we're going to do it with a stack of new technologies we've never used before.

[00:27:11] **Adam:** something I might be worried about is like, okay, we're trying three new technologies and we don't know, we don't have any significant experience in any of them. And so the thing that most concerns me there initially. Is, schedule slip, mostly because in my experience, like writing, writing code, learning a language is not that hard.

[00:27:30] **Adam:** What's the hardest part is like, how do I write testable code? And how do I write the tests and figure out the test frameworks and the mocking and stuff that's necessary to, to do that part well, it might take me four hours to write a small feature and another three to four days to figure out how the test should work.

[00:27:49] **Adam:** And work, and, and work them out, get them done.

[00:27:53] **Ben:** I think that's totally valid point. You know, failure doesn't necessarily mean we couldn't do the work. Failure in this case could just be, we didn't meet a specific deadline that we had in mind and why is that? And is there anything we can do to cut scope or to adjust the choices to maybe be able to meet that deadline more effectively, but yeah,

[00:28:14] **Adam:** So, okay, that's, yeah, and that's where I was headed. It's like, okay, so if that is somebody's concern that they bring up at a pre mortem, what, where does the discussion go? Or does that just get written down? Like, we're having a brainstorming session, everybody writes these things down, or you know, somebody writes these things down, and then it's on the wall there to everybody to walk by on your way in and out of the office every day?

[00:28:32] **Adam:** Or what's the,

[00:28:34] **Ben:** That is a great question. I have.

[00:28:36] **Adam:** of this meeting?

[00:28:38] **Ben:** I will tell you that when we did it at work and forgive me, this was like five years ago at this point, it was a Google doc that we were all sort of working on collaboratively at the time. And then, so you would put down your concern and then, you know, you could highlight it and leave comments on other people's concerns and they could do it for yours as well.

[00:28:58] **Ben:** what happened to that Google doc? Who consumed it? How was it used in subsequent decision making? I don't think I know. I do. If you told me that no one ever looked at it again and it added no value to the process whatsoever, I would 100% believe you in our particular case.

[00:29:17] **Adam:** Mm hmm. I mean, at the very least, you know, the people that were there heard what was said, and it, you know, it's almost impossible to not be affected by that, even if it's a small, subtle amount, but...

[00:29:29] **Ben:** Yeah, yeah. so the other, one of the other podcasts that I really enjoy listening to at least, you know, on and off as we talked about in other episodes, is a podcast series called How I Built This. and it is just interviews. Yes, Guy Raz, exactly. It's part of the NPR series of podcasts. And, and all it is, is him interviewing CEOs and leaders in companies.

[00:29:53] **Ben:** Usually these people have just really fascinating stories where they came from, where they get the ideas, how many times they've been at companies that have completely failed or how they've pivoted, you know, three or four times to get the company to where it is. Very interesting stuff. And he was interviewing, I want to say it was.

[00:30:12] **Ben:** The CEO of Kinko's, it was, it was one of the printing company. I think it was Kinko's and, he was saying that what he would do is, Kinko's for the, for anyone listening here, it's a, like a

[00:30:26] **Adam:** Breakfast cereal for adults.

[00:30:30] **Ben:** it's like an on demand print and photocopy shop. and he would call up his store managers every month and say, tell me one thing that you did to improve the process that we gave you. And if you don't have one thing to tell me, it's going to be a problem. And you better have something to tell me next month.

[00:30:48] **Ben:** And it's, it's not a pre morning, but it is him, positioning the conversation from the perspective that the things we tell you to do and the way we organize the store and the way we organize the process. are problematic in some way. And as you, as the person on the ground are going to feel that most directly.

[00:31:07] **Ben:** And you better have one, taken actions to improve upon it. And two, you know, tell me about it so that I can share it with the rest of the store locations. But it's giving people that freedom to feel and do something about the problems that they're seeing. And that's, you know, it's, it's a different take on this kind of thing where we're leaning into the idea that failure is possible and then giving people.

[00:31:28] **Ben:** The opportunity to express and consume and to fix it, if possible,

[00:31:35] **Adam:** I like it.

[00:31:36] **Ben:** you know, it's, you could imagine doing something like that, certainly in a meeting at work where it's one thing to say, Hey, does anybody have any suggestions for stuff we can change and everyone's sort of like, you know, no, it's just, that's kind of, kind of fine, whatever. it's very different than saying, okay, you have 15 minutes.

[00:31:54] **Ben:** Everyone has to come up with at least one thing that they would fix about this company. And then we'll talk about it and you don't, there's, there's no longer. I don't want to call it the excuse, but there's no longer an opportunity for someone to just shrug and be like, no, things are fine. Like you have to embrace the idea that there is stuff that is wrong and I'm giving you permission to now talk about it.

[00:32:14] **Adam:** If you can't find one thing that you would like to see changed about your company, you should be fired.

[00:32:19] **Ben:** Yo, I tell my wife five, six times a day. What's wrong with her? Do

[00:32:27] **Tim:** customers, if we could just keep the money and get rid of the customers, things would be great.

[00:32:33] **Carol:** Firewalls.

[00:32:34] **Adam:** DNS.

## [00:32:36] When Should You Do One?

[00:32:36] **Adam:** Um,cool. Well, oh, I actually did have one other question and maybe, maybe it's not the time or the place to ask it, but I'll ask it anyway. is, is there a clear and or obvious... Minimum threshold of some sort when this becomes a useful exercise, like, you know, Hey, I need you to change the shade of blue on the submit button, right?

[00:32:59] **Adam:** Should we have a premortem for that? Probably not. Like, so where's the line?

[00:33:03] **Ben:** That's a great question. I have no idea other than to say, I think when the. Path to a successful outcome feels unsure or is, is farther away than what we would normally consider. But, I don't really have a concrete way to articulate that.

[00:33:22] **Carol:** Yeah, I would like to think if projects have failed over and over again, it should be the norm that you start talking about your failures at the beginning of any big project. Like if you're constantly missing deadlines and you're constantly running into issues with your systems admin people with how you get IPs assigned for subnets to what you need to be running.

[00:33:44] **Carol:** You should start talking about what could go wrong at the beginning of every big project to prevent those big impacts to timelines.

[00:33:51] **Ben:** That's an excellent point. And it makes me think of the Phoenix project. I feel like maybe those meetings he was having with the crazy, what was his name, Eric or whatever. Yeah.

[00:34:01] **Adam:** Where he would like take him a little bit further down the process of like figuring out how to run this thing. Like maybe that was premortems for like where he was at in the process.

[00:34:08] **Adam:** I don't know. Just a random thought

[00:34:09] **Ben:** Well, and I also love the idea that we've talked about this a couple of times. Amazon has this concept of one way doors and two way doors, a two way door being a decision that you can reverse if it doesn't work out. certainly I think if you're going down a one way door where you're going to make a decision and that decision is not easily reversible, that that feels definitely like something where you want to game out all the possible things that can go wrong.

[00:34:34] **Adam:** for sure. That was a good topic.

[00:34:39] **Tim:** Yeah.

## [00:34:40] Log Levels

[00:34:40] **Adam:** So, I guess that brings us to the other topic, which was my idea, the, the lost art of log levels, which is not so much like, let's talk about this awesome thing and more of a, Adam has questions and he's going to rely on the wisdom of his peers here, so, it,

[00:34:56] **Tim:** Could be a short one.

[00:35:00] **Adam:** It's been weighing sort of heavily on my mind for like years now that, I feel like maybe we've sort of lost a little bit of the wisdom gained from our computing forebears, so I don't have a whole lot of experience, mostly just in school, writing like C and, you know, those low level languages, old school stuff.

[00:35:22] **Adam:** and I know that there's probably some tooling that we've, you know, reinvented or maybe we haven't yet reinvented, but basically log levels, right? So, probably most of us are familiar with, you know, spitting out an error message or something and, you know, you say maybe this one's fatal or it's not, you know, and you've got like, info and trace and warning and error and fatal and, and debug.

[00:35:47] **Adam:** Yes. So these are all examples of log levels. and the, my understanding, which admittedly upfront is half baked, is like, basically you have all these logs that you're spitting out from your application because eventually they could be useful. And then where the real sort of magic comes in, in my head, this is not a real thing that I'm aware of.

[00:36:11] **Adam:** anymore, or at least with modern technologies, you have a log viewer and you say, okay, only show me the fatal things, or show me error and fatal, or show me warning, error, and fatal, right? So, it's like, you're like, descending into the depth, and the further down you go, the more information you're getting, and you're always like, adding, you're never like, show me only the info, you're like.

[00:36:31] **Adam:** Info and everything prior to that, right? and if you, and I've run into this in at least the macOS console, right? If you use whatever your app launcher of choice is and you launch the console app, you can see in there, you know, there's a bunch of log messages constantly being spit out of various applications.

[00:36:53] **Adam:** And, and then like, so you record for a couple of seconds and then you hit the stop button and then there's like little ways to say, okay, show me. The, the more recent versions of Mac, I played with it a little bit recently and it, it doesn't seem to have as much depth or I haven't found it, you know, maybe it's hiding from me, but there is, you know, there's like messages that you see by default and then you can go deeper or something like that.

[00:37:15] **Adam:** You can say, show me the errors too, or something. and I feel like that is kind of missing. So for my purposes, specifically, the two things, the two platforms that I use the most right now are. JavaScript, and CFML. CFML, you kind of just have like standard out, basically. That's, or that's kind of how we're doing it.

[00:37:36] **Adam:** you know, we have, CFML running in Docker containers, and we have it set up in such a way that all of the important Lucy log files are being piped to standard out, and then that gets piped into CloudWatch. So that all those logs that are relevant to us Become available through CloudWatch, which is nice, but then you just kind of get like vomit, right?

[00:37:59] **Adam:** You just get here's the 6, 000 lines of logging that were spit out in the two minutes that you pulled up and it's painful and it reminded me especially so there's this great module that I love called debug in JavaScript, Node. js and you can use it in the browser and you can use it with anything JS adjacent, right?

[00:38:21] **Adam:** Svelte or Vue or Angular, React, whatever. Works in a browser, works on server side, et cetera. And basically it is, you know, you use it and you call function, you give it a string and it will return a function that you can then use to log things, right? So the string that you give it is like the log stream name.

[00:38:41] **Adam:** So you say, okay, I'm going to create a debug function. I'm going to create a trace function. I'm going to create a fatal function. And those are the strings that you pass in and then you save it as a function. You might call the function name debug and the function name fatal, et cetera. And then you just call those functions with whatever message that you want to log out and that's in JavaScript parlance.

[00:38:59] **Adam:** It's not blocking, right? It happens off the main thread. And, there's a lot of niceties about that particular module. And the way that they talk about it in their readme and the way that I see people using it is often with these log levels, right? Debug, trace. Et cetera. But I think, and also a very nice thing about debug is that the, the module is that it references an environment variable.

[00:39:24] **Adam:** So you say like debug equals error or star, right? If you do star, then all of the, statements that get logged, not only by your code, but if you're using any modules and they're using the debug module, like ExpressJS uses debug. And so if you, if you turn on your application with the debug environment variable set to star, It spits out a ton of information about the various requests that are being made to your server, which can be interesting and useful in some cases, but it can also be a distraction and noise.

[00:39:55] **Adam:** And so you can be very selective. You can say, only show me the ones from my application based on that string that you're using to create the log streams. And I feel stuck. And this is where you guys come in. you know, I, I, Want to get to that point where we have sophisticated logging that is always on, but then we can selectively drill down into to show more detail. and I, I don't feel like I have the tools for it or the knowledge. I feel like something's missing.

[00:40:25] **Ben:** Well, let me ask you one question initially, cause you talked about taking the CFML logs and piping them to the standard output. so those are logs that you don't necessarily. Control meaning, you know, when the, the server is bootstrapping, it writes to a lot of logs, and when it checks the, you know, SMTP spool, it writes to logs, that kind of stuff.

[00:40:46] **Ben:** But then there is logging that happens inside of your business logic. You know, I, I made a call to this API and it returned a 404 and it should have returned a 200. So now I'm going to log that because that was an unexpected response. are you logging that as like a JSON payload? Like, so typically what we'll call like structured logging, as opposed to just a comma delimited list of field values.

[00:41:12] **Adam:** So it's a really good question in our CFML specifically, no, because we have two other outlets that we use to, to push that sort of stuff out. we, we use a bug logging tool, right? Like Bugsnag or Sentry or any of these other things, that. you know, are, are built for pushing errors into, and, and so we, we pushed that, when we have errors that we want to be logged for later.

[00:41:40] **Adam:** you

[00:41:40] **Ben:** Interesting. Okay. So you, so just. If I can say back to you what I think you just said to me, you have essentially differentiated system logging versus error logging as two separate means of recording information.

[00:41:55] **Adam:** Yeah, I think so. And honestly there's not a whole lot and, and this is probably a, a symptom of the problem, right? So there's not a whole lot that we push into the Lucy logs. Mostly it is logs automatically generated for us by Lucy occasionally. There's, stuff that we spit out just as like reference for if the really hits the fan, we need to be able to go and see exactly what happened.

[00:42:21] **Ben:** But that's pretty rare. So when you're logging though to something like Bugsnag or whatever, Cameron, which one you mentioned?

[00:42:28] **Adam:** we use BugLogHQ, which is a CFML project, but yeah,

[00:42:32] **Ben:** I think, and typically with things like that though, you can You can give it a log level associated with the payload that you're sending. You're saying Record this and it's an error.

[00:42:41] **Ben:** Record this, and it's a warning

[00:42:42] **Adam:** That's a really interesting thought. You're right. You can do that. the thing. And maybe I need to investigate this more because the thing that, I think the mental block for me there is that the, the minimum atom of ATOM, not ADAM, the minimum atom of something that you can push into bug log, again, this is my current understanding, and I think I might be wrong about this, is an exception object, right?

[00:43:07] **Adam:** You have to have an exception to push into bug log because it's an exception logging tool. now, granted, There are already plenty of instances where I wanted to log something because it is an exceptional case. It's not that an exception was thrown, but, you know, whatever. And so I create an exception object and then we have, it, it, so BugLog will look for a property on your exception called extra info and, print that out nicely for you at the bottom of that bug report.

[00:43:40] **Adam:** And so I will trump up my own little exception and then attach some data to it and log that as a way to push data into our bug log. Like, you know, we tried to pull this file off of S3, S3 says it's missing. Here are the credentials, you know, here's the context for why we were looking for it.

[00:43:59] **Ben:** I can certainly relate to this pain because, when we started logging stuff within our application, we started logging with the intent, intent of error tracking. So everything that you log has to have an error type and an error message. As, as like a minimum possible thing, but over time you're like, not everything I want to log to your point is an error

[00:44:21] **Adam:** hmm. Mm

[00:44:22] **Ben:** this day.

[00:44:23] **Ben:** Every, no matter what you log, you have to call it an error message. And that's how it shows up in all of the log aggregations. Even if it's just a, you know, someone just upgraded to a paid plan or someone made a recurring donation of 10, 000. I want to put that in the logs just in case.

[00:44:41] **Adam:** Right. And that's another example of a way that we... Kind of rolled our own solution because we had specific needs. So those types of things that you're describing to me sound like audit events. Right? So we need to, they're, they're useful to us, but they're also useful to our customers, the users, the primary users of this, we've got like two different layers, right?

[00:45:01] **Adam:** So our customers are users of the admin layer of the system and then their customers. are users of the public facing side. And so it's useful for them to be able to look at that audit trail and say, okay, you know, so and so tried to upgrade their membership and their credit card payment failed, and then they tried again and it succeeded, sort of thing.

[00:45:20] **Adam:** And so we can capture all those audit trail events in a database table and we, you know, try to cross link them to all of the relevant records as appropriate. You know, this is the membership they were trying to do, this is the transaction that failed, this is the transaction that succeeded, and all that.

[00:45:36] **Adam:** and so that's just, that is at the end of the day, just a database table and a couple of different functions that make it easier to push data into that table and some tools for viewing the data that's in there. so that's auditing, which I would say is like sort of a special version of like maybe info log level, right?

[00:45:56] **Adam:** These are things happened that are interesting, not just like, so that's the thing. Maybe we should talk about that a little bit, right? So you've got like, Oh goodness, I need to pull up the, there's a, a really nice,

[00:46:08] **Ben:** I was trying to get it to do it also, but it doesn't

[00:46:10] **Adam:** Yeah, the, so we're, we're giggling over here because every time I, like, make a hand gesture that's even remotely, like, thumbs up, my camera does this, like, stupid thought bubble of a thumbs up icon.

[00:46:21] **Adam:** I hate it. I need to

[00:46:23] **Ben:** Is it just Adam? Is that the,

[00:46:25] **Tim:** Yeah, it doesn't,

[00:46:27] **Adam:** Everybody thumbs up! Woo! anyway, what was I saying?

[00:46:32] **Ben:** things that are not specifically errors? You know, there's like a different type of gesture of what

[00:46:37] **Adam:** Right, right, yeah, so there's this, I said I've been ruminating on this for like years. There is a stack overflow, that I've got like bookmarked here and I've got it, I've already found it again and pulled it back up. I'm, I'm gonna drop in our team chat, our discord for just us. there's this flowchart of like when to use which log level.

[00:46:56] **Adam:** Right, so you start with For whom am I writing the logline? And if the answer is developers, that takes you to another question. Which is, do I need to log the states of variables? Yes or no? If it's no, then you're doing trace, right? I'm just saying, I'm at the beginning of this method. I'm about to leave this method.

[00:47:10] **Adam:** I'm at this point in the while loop, whatever. Those are trace, but if you are logging the state of variables, then they go into debug. And then... so that was for developers, if you're logging, if you're logging for system operators, which I think that this is a little bit, we're, we're switching paradigms in terms of, the, the way that applications run anymore, right?

[00:47:27] **Adam:** So like, you know, raise your hand if you've got, a team of people whose job it is to sit in the NOC and watch the logs scroll by and look for errors, right? Like nobody's raising, you know, okay, Carol.

[00:47:40] **Tim:** the government, don't

[00:47:42] **Adam:** Yeah. It's, it's a pretty, not modern web dev approach to things, I think. but anyway, so you've got, in this flowchart, system operators, if you, if you're logging for system operators, then it's, do I, am I logging because of an unwanted state?

[00:47:57] **Adam:** If no, then info. If yes, then you go to the next question, which is, can the process continue with the unwanted state? If yes, then it's a warning. If no, then you move to the next question. Which is, can the application continue with the unwanted state? If yes, then error. If no, fatal. Right, so if, if the reason that you're logging is because the application is about to die and crash, and you're going to have to restart it, or it'll automatically restart, whatever, that's fatal.

[00:48:19] **Adam:** If it's not that, then, but it was an error, then it goes in error. Right, so those are, those are the log levels. Go

[00:48:24] **Ben:** It, it, I don't mean to dominate the conversation here. So I don't want to, let me just say my piece and then I'll, and Carol and Tim can jump in. However,

[00:48:32] **Tim:** have a whole lot to say.

[00:48:33] **Ben:** so you mentioned, something about changing in paradigms in, in programs. And, and I think that is. In some degree where so much of the confusion feels like it stems from, because when I see a flowchart like this, it, it feels very much like an application that's running as a service somewhere.

[00:48:55] **Ben:** And it has all this asynchronous processing and threads and stuff's happening in the background, which, Like you talked about opening up the console in the Mac and you have all these applications that are just running constantly and spewing state into the logs, and you're not even using these applications or you're not, you know, interacting with them actively at any one moment.

[00:49:17] **Ben:** That to me feels so very different than a web application where I make a request. The request comes in, it gets processed in a very deterministic fashion, and it gives me some sort of outcome. And the, the state and the reaction to state during that is so different from how a installed application might work.

[00:49:37] **Ben:** You know, you're going through this flowchart and we have a variable that's in an unexpected state. Can I do something about it? I think about something like I went to S3 to grab an object and it's supposed to be there, but it gives me a 404. I'm not going to crash the web server. That's clearly the wrong move.

[00:49:54] **Ben:** And I can't fix it, meaning I can't magically make this object appear, but I can certainly proceed and tell the user that either something unexpected went wrong, or we looked for a file and it wasn't there. Can you please try to re upload it? Web applications just feel like a completely different philosophical approach to control flow than some of these older types of programming paradigms.

[00:50:18] **Ben:** And I think. A lot of the thinking that goes into the logging doesn't make as much sense for web application development.

[00:50:27] **Adam:** Okay. I have a response, but you're right that, you and I have been kind of domineering the conversation here. So I want to give the others a chance to jump in before I,

[00:50:35] **Carol:** my only response is I keep working for companies who have lots of people handling all this, so they just give me access to Sumo Logic or other log aggregates, and I just go find what I'm looking for or ask them to write me a query. So.

[00:50:47] **Adam:** of the questions in my head is like, is it just because we're not using like a Datadog or a Sumo to, you know, do they have this sort of thing built in and that's why I'm just not familiar

[00:50:58] **Carol:** from yeah, from previous jobs where we did a lot of manual looking through logs and going through Fusion Reactor to figure out where things were and trying to like open up application logs and see if we could throw something together for where something crashed at. I don't have to do that anymore because it's already put together for me in a nice view. So every log is already there.

[00:51:21] **Tim:** yeah. And our, a lot of our stuff runs as a kind of like a, what Ben was saying, sort of like a service. So we use this exact same. Model here that you're referring to with the trace and debug and info, warn, error, fatal. Because, you know, it's someone makes a request, we answer their request and, you know, we, we log what came in, we log what came out.

[00:51:40] **Tim:** And if it's, if it's an error or if it's, you know, unexpected, we do a warner or an error. So it works exactly like this. It's just, it's just a file, right. That gets zipped up every night to save space, every, every day. So if it was two days ago, you got to go grab it from unzip it from two days ago.

[00:52:00] **Adam:** yeah, the, so you're saying you use this. Is it, but what is the end result? Do you just have like a text log file that has all these things in the, each line is prefixed with trace or debug or info? Okay.

[00:52:14] **Tim:** each, each slide is prefixed with that. Yeah.

[00:52:16] **Adam:** And, and do you have a good way to filter down to like say, okay, only show me info or show me debug and error and warning, or

[00:52:23] **Tim:** Yeah, I forget the name of the tool we use, but it is basically you can treat the file like it's a SQL query and you write SQL statements in a bit to look at stuff.

## [00:52:33] Retroactive Detail

[00:52:33] **Adam:** if you would do me a favor, you know, obviously not urgent, but just like look into what that tool is and let me know that would be possibly useful. I mean, I, I doubt it because we're just, I don't think we're going to give up CloudWatch, but it would be good to know, you know, a good jumping off point for research.

[00:52:48] **Adam:** So, let me take this back a little bit and kind of respond to what you were saying, Ben. I think you did a good job articulating how I'm not explaining this well. so, let me come at it from a different angle. Say we have a lambda function, and it gets invoked 30, 000 times a day, and most of the time it's fine.

[00:53:07] **Adam:** but every now and then, or in certain scenarios that we don't quite fully understand why, It doesn't do the thing we want it to do. And so what we would love to be able to do is always leave this highly detailed logging on. In such a way that we can retroactively go back and look at the detailed logs, but that also when we're just kind of checking in, you know, like what are our runtimes like and what are, you know, I don't know, whatever summary information you might want to look at in the logs more frequently, the, the two experiences should be different.

[00:53:48] **Adam:** And I don't have a good way to separate those out right now.

[00:53:54] **Ben:** Yeah. Okay. I, I totally understand what you're saying.

[00:53:57] **Adam:** we can, we could go in and for that particular lambda function, we could say, okay, you know, we know when we upload this file, it's going to cause it to be a problem. So we go in, we change the log level in the environment variables to say, okay, now I want you to start spitting out the total vomit of, of logs.

[00:54:14] **Adam:** And then we upload the file and then we turn the, the environment variable back to normal and then paw back through the logs. That's fine. But what that doesn't do is retroactive. Detailed logging.

[00:54:24] **Ben:** So I will, I will say that I, I don't have a specialized error oriented logging strategy, meaning that, we just spew stuff into, we use at work, something called Loggly, which I think is just a vendor on top of. ElkStack, what elk, what is it, Elastic, ElasticSearch, something, Kibana,

[00:54:51] **Adam:** Kibana. Yeah.

[00:54:52] **Ben:** and it's just a, it's basically just a, I think a document indexing system.

[00:54:57] **Ben:** So we just throw these JSON payloads into this giant system and then we tell it to index certain keys within those payloads. So looking for things like log level and user ID. And anything else that we want to be able to then filter on. but to your point, we don't send things like trace and debug, and info logs in an ongoing way.

[00:55:24] **Adam:** We usually typically only include warning error and fatals. We do have a way to turn on some of the lower level logging, but again, to your point, it's not retroactive. It's from when you turned it on to when you turned it off. we do, like I said, we use CloudWatch pretty heavily. And, to go back to your earlier question, we do in a lot of places, and we're getting better about doing this in more and more places, use structured logging, where we'll log a JSON object out, especially because in CloudWatch there's tools, I forget if this is what's called, there's too many damn things inside of AWS,

[00:55:57] **Ben:** yeah, that's,

[00:55:58] **Adam:** so maybe this is CloudWatch Insights, maybe this is a different thing.

[00:56:03] **Adam:** But there's a neat tool where you can, kind of, it looks a lot like SQL to search through your CloudWatch logs. You can say, okay, I want you to search this log group, and I want you to look for an object containing, you know, customer equals x, y, z. And, you know, you could say, you know, log level equal trace.

[00:56:20] **Adam:** or whatever, you know, depending on how you log that out. and that's been very helpful for us. We're still, like I said, getting better about that, but, in the places that we've got it, it's been fantastic.

[00:56:32] **Ben:** login. Super, super helpful.

[00:56:35] **Carol:** although I will throw out one warning about your logging. Don't log any PII. That

[00:56:41] **Adam:** yeah, yeah,

[00:56:42] **Carol:** could get you in some trouble.

[00:56:44] **Ben:** this

[00:56:44] **Adam:** We do our best.

[00:56:46] **Ben:** information. PII. Yeah.

[00:56:48] **Adam:** Yeah. We, we do our absolute best to not have any of that to begin with, but some of it is just unavoidable and you've got people's names and, addresses and stuff from, from having their billing info for their credit card or, or whatever, or for their membership or for, you know, we've, we deal it to some respects, In PII, that is like our business.

[00:57:09] **Adam:** But yes, we do jump through a lot of hoops to try and make sure it never appears in any of our logs.

[00:57:15] **Carol:** Yeah. Our logs are kind of cool. Cause it'll be like, Oh, we weren't able to validate. And it says like, click this link to go find out why this information wasn't logged and it's like, because it was PII, it was like not able to work. And I'm like, well, I'll never know what that was. It's gone forever.

## [00:57:34] Bad Error Handling

[00:57:34] **Ben:** Can I, can I throw out a spicy take? yeah, let's get spicy here. I think the root of so many logging issues is people just not handling errors very well. I think if people caught errors and log them appropriately, you basically wouldn't need trace and debug and probably info logs at all. I find, so it work.

[00:57:59] **Ben:** And again, this kind of ties back into this idea of different, different types of system paradigms and how they've changed over time. I think if you get people who were like systems thinkers, like working on old installed systems, and then they move into the web application space, that's, those are the people who I think are.

[00:58:20] **Ben:** Most guilty of putting tracing statements all over the place because they didn't have a browser. They could refresh and then look at the logs or look at the, the output of the page. So, so the logs where that was their interface. Um,and, and so you see things like, you know, request received. Method started, method completed, request process.

[00:58:43] **Ben:** And when you, when I see that in a web application, I'm like, what the F were you doing? And it, and I'm telling you like 99 percent of the time, somebody put that in because somewhere deep in the code, they caught an error and didn't log it properly. And now they have like stuff just stopped working and they have no idea why.

[00:59:00] **Ben:** So now they just start putting all these logs in all over the place. And if they had just logged the error instead of catching it and then having a comment that said something went wrong, oh. You know, they wouldn't need all

[00:59:11] **Tim:** That's, that's their, that's their version of a CFDump, CFAbort and hit F5. You

[00:59:18] **Carol:** Yeah.

[00:59:19] **Ben:** So that's my spicy take. Bad error handling is the root of so many logging issues.

[00:59:25] **Adam:** I think you're right in, in at least some way, right? Like the, there's an element of truth here. And I think that If I, if I can turn that log over, in addition to what you're saying, it probably is also an indication of missing tests, right? If, if, or, or code that is not very testable, right?

[00:59:48] **Ben:** So you're, you're leaning on the

[00:59:49] **Adam:** Ooh, I feel like, yeah, I feel like I am more inclined to do console.

[00:59:55] **Adam:** log driven development. When I'm working on code that, you know, especially if it's like 10 years, 10 years old, 10 years old. and I got to stop holding my hand up that stupid thumbs up.

[01:00:06] **Carol:** Does

[01:00:07] **Adam:** if I'm working on old code and it's not testable and, and I don't have time to refactor it to be testable and don't have time to write the test, you know, like.

[01:00:17] **Adam:** That's, I think that's when I lean into this whole, like, sort of trace based debugging. Hmm.

[01:00:24] **Ben:** Well, yeah,

[01:00:24] **Adam:** if it was testable code and you could just be like, Okay, here are the inputs that you might get, and these are the expected outputs, then

[01:00:30] **Carol:** it work? Yes.

[01:00:34] **Tim:** find the error from the broken test, not having to look through the logs.

## [01:00:37] Metrics

[01:00:37] **Ben:** I think there are also. And this is, this is a technology issue as much as it is a people issue, but I think logs existed far before the prevalence of widespread use of metrics. so, you know, right now, let's, let's say that, you have a, a message queue and you have a worker pulling messages from a message queue.

[01:01:02] **Ben:** In, in a more modern context, and I'll say modern in quotes because it's, I don't mean it as a judgment. I mean, in terms of like the technology that we have at our fingertips. In a more modern context, you might log a StatsD metric that said, I pulled something off of a queue and then you process it. And whether you're going to ACK it or NACK it or whatever the terminology is, you might log another metric that I have a message that was processed properly or a message that failed.

[01:01:28] **Ben:** And then you can aggregate that in, in. Graphite or, or, or Datadog and you see it as a graph. And I think that's a more appropriate way to log that kind of stuff. But before we had things like StatsD, you might throw that into a trace or a debug log method because you literally didn't really have another good strategy for handling that kind of stuff.

[01:01:52] **Ben:** And so I think some of this is also just not. Replacing older paradigms with newer paradigms in terms of system health.

[01:02:02] **Adam:** Lots of food for thought.

[01:02:04] **Ben:** I have another one more spicy take. Uh, and this is something that I can't

[01:02:08] **Adam:** to get Sean Evans in here, or?

[01:02:10] **Tim:** I know, right? You from the guy who can't handle spicy.

[01:02:15] **Ben:** One thing that I cannot stand, and this is, I am definitely fighting against the currents here. I. I do not like the idea of using numbers for log levels, like 10 is

[01:02:27] **Adam:** Oh, no,

[01:02:28] **Ben:** info, and 30 is warn. It's, it's so, yeah, it's totally, yeah, good point. It's a magical number. Clean code says do not use this.

[01:02:38] **Ben:** And, I don't know if it's maybe because I've been in the node world a lot, and maybe, the, a lot of the common node loggers happen to use this, and it, maybe it just feels more prevalent than it actually is. I just. I cannot stand it. I would much rather just use a string that says debug or trace or info or warn.

[01:02:57] **Adam:** You got a microphone in front of you. Do you want to throw anybody under the bus? These particular node modules.

[01:03:04] **Ben:** I mean, I,

[01:03:04] **Adam:** just kidding,

[01:03:05] **Ben:** no, I, I, I don't think it's any particular one. I think it, I think it's a very, very common way to handle logging that when you call warn or debug in, in the methods that you're generating under the hood, it's saying it's translating those into numbers and that's what's getting persisted in the log data.

[01:03:24] **Ben:** Most often that I've seen, and it just drives me bonkers.

[01:03:29] **Tim:** Good take.

[01:03:30] **Adam:** yeah, no, I can't, can't disagree with that. I guess, sort of like a, if I can wrap my own thoughts up here, it sounds to me like, I'm too focused on the, the concept that maybe we've lost something to, in the rush to innovate. Right, maybe, maybe it doesn't exist because we don't need it anymore. And, and maybe it's also, like, these, these places where we need the logs is a symptom of a different and more important problem. I'm getting nodding heads. Okay.

[01:04:04] **Ben:** think that sounds right.

[01:04:07] **Tim:** I'm sure our listeners will have something to add to it for

[01:04:11] **Adam:** Indeed. And

[01:04:12] **Ben:** Come at me, bro.

[01:04:16] **Adam:** they can add us in our Discord.

## [01:04:18] Patreon

[01:04:18] **Adam:** All right. Well, I guess this episode of The Woodsman's Code was brought to you by elks and yaks and logs and bots. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:04:33] **Adam:** Our patrons cover our recording and editing costs and transcription. I still haven't added that to the notes. And transcription costs, and we could do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:04:45] Thanks For Listening!

[01:04:45] **Adam:** we are going to go record our after show, which is a perk for our patrons.

[01:04:50] **Adam:** the outro's gonna play, maybe some bloopers, there's been a few flubbed lines tonight, so, maybe some bloopers, and then we're gonna do the aftershow, and tonight on the aftershow we're gonna talk about, uh, Ben's gonna rant about people at gas pumps, apparently, and, oh, and we, we can't, not talk about the OpenAI news, Sam Altman, and all of that stuff that's been going on,

[01:05:10] **Carol:** O, M. G.

[01:05:12] **Adam:** yeah, we'll, we'll have some thoughts there.

[01:05:14] **Adam:** So if that sort of thing interests you, then you should go to patreon.com/workingcodepod, become a patron of the show and you get to keep listening with the rest of the patrons. If you have thoughts on these problems, these topics, and you would like to share them with us and the rest of the community, you can go to discord, to our discord, at workingcode.dev/discord. It's just like slack except better for communities. Um,so we'd like to see you there. That's going to do it for us this week. We'll catch you next week. And until then,

[01:05:44] **Tim:** Remember, your heart matters, even if you're yak shaving.
