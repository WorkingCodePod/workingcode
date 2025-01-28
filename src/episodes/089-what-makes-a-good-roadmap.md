---
title: "089: What Makes a Good Roadmap?"
description: "What goes into a good roadmap? How we can avoid certain pitfalls? We question how far into the future a company should be looking on their roadmap."
date: 2022-08-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/089-what-makes-a-good-roadmap/id1544142288?i=1000577199777"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Like Michelangelo with a block of marble, we engineers often like to dive right into the code and let the application _reveal itself to us_. And while this may work on a very small scale, this extreme bias-towards-action isn't prudent for larger teams or companies with a growing client-base. Mature companies have roadmaps. They weigh the benefits of building one feature against the opportunity cost of not building another feature. Mature companies get buy-in both internally and externally. They then evolve their vision based on that feedback when it make sense; or, they apply grit when it is required.

Or, at least that's the hope. Because, in reality, building a roadmap isn't easy. There are so many competing interests and such a limited amount of time. And then, there are Black Swan events like Covid-19, that force us all to stop and completely _re-evaluate everything_.

This week on the show, the crew talks about what goes into a good roadmap; how we can avoid certain pitfalls; and, we question how far into the future a company should be looking on their roadmap.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/089-what-makes-a-good-roadmap.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** Yeah, no one knows the future in five

[00:00:01] **Tim:** years. That's just a waste of time to even try to

[00:00:03] **Tim:** do that.

[00:00:04] **Carol:** I hate those questions when people are like in interviews and stuff. And they're like, where do you see yourself? In five

[00:00:08] **Carol:** years? I was always like in five years, Peyton will be one year out of college and James will hopefully have his own family. So I'm sure me and the dog will be happy. Like who the hell knows what five years looks like, like ask me what I'm gonna be like in six.

## [00:00:45] Intro

[00:00:45] **Adam:** Okay. Here we go. It is show number 89 and on today, show we're gonna talk about what makes a good product roadmap, but as usual, we'll start with our triumphs and fails.

## [00:00:54] Adam's Triumph

[00:00:54] **Adam:** And I guess it's my turn to go first. So I'm gonna start us off with a triumph. I finally, this week, we had our kickoff meeting for our SOC two, compliance product, usage with our team.

[00:01:06] **Adam:** We picked a product. We, paid the bill and got a couple of people together on a video chat and got to see a little bit of, a tour of the product and actually. Put some real data in there and, and the product is now moving forward. It's no longer just an idea. Now, some things have happened. Um, I've actually, I've actually, done a couple of the integrations.

[00:01:26] **Adam:** So some of the, evidence collection can be automated and I've, integrated for example, like GitHub already. And it will check that our we're using branch protection, to enforce that everything that goes into production is, go, goes through a code review. that's one of the requirements based on our trusts, TCS trust service categories.

[00:01:45] **Adam:** anyway, so SOC two is rolling and still, I managed to get some other like, quote unquote real work done too this week. so.

[00:01:53] **Carol:** So, take a step back. So the Sox audit that I remember doing back in the day was because we worked with a company who were with multiple companies who were publicly traded. So it was certificates that we had to have. Is that what you're working on? Like some type of certifications for you to be like Sox compliant or

[00:02:10] **Carol:** publicly treated data.

[00:02:11] **Adam:** this is specifically called SOC two S O C two. I don't know specifically what you're talking about, but potentially, it's a certification offered by the international association for, CPA's, uh,

[00:02:24] **Carol:** Pancakes.

[00:02:26] **Adam:** public accountants. and basically it's just, yeah, it's,you identify like what type of business you are and what kind of information you deal with, and then that specifies certain rules that you need to abide, and policies that you need to have, and that sort of thing.

[00:02:41] **Adam:** And that creates a list of all these things that you need to do to achieve the. You prepare everything that you need to prepare, gather the evidence that you're actually, encrypting data at

[00:02:51] **Carol:** compliant.

[00:02:52] **Adam:** data in transit, whatever. Yeah. And then you pay an auditor from some, as far as I know, they are a CPA, they're from the IA CPA.

[00:03:00] **Adam:** and they come in and review all your evidence and make sure that you're compliant with all the policies and then you get the certification and some of them are like, there's type one is, you do it. it's just a point in time, like as of this moment, we, everything that we have and are doing is compliant and type two is we are on a continuing basis renewing that we ha are still doing all of the things that we're supposed to be doing.

[00:03:25] **Adam:** and it's like a yearly sort of deal. and then what it is that it, you can go into like a sales meeting with the,the head of it, of the client that you're trying to. Sign and you can show them like, look, we're so too compliant with these particular TCS and that, then they can feel good that you're doing the right thing is the idea. So

[00:03:48] **Tim:** Thing that drives me crazy about those is so really there isn't a SOC two standard. It is, you say, here's what we're doing to make sure that, no one is going in and

[00:04:00] **Tim:** altering your financial data, that we're we have controls in place. so you tell 'em what the rules are and all they do is they tell you if they think those rules are reasonable,

[00:04:08] **Tim:** and then you give documentation to prove that you're doing those rules, but there's really no data audit.

[00:04:14] **Adam:** mm-hmm yeah, it's a, it's kind of an

[00:04:16] **Adam:** attestation.

[00:04:17] **Carol:** what is the audit they do where they come in and they're like, oh, in your non-production environment, we see that you're storing credit card numbers that aren't encrypted.

[00:04:26] **Tim:** It really has nothing to do

[00:04:27] **Tim:** with this sort of, I mean, the ones I've been involved with, it's all about accounting. It's

[00:04:30] **Tim:** who has access to go in and change data that can affect the accounting

[00:04:36] **Tim:** of so where the, where money is. And then also, what are your rules about your software processes and how things are done,

[00:04:44] **Adam:** yeah, I mean, Tim, I'm not surprised that the, that yours has been heavily focused on accounting. You're a financial company. ours is, I'm sure that we will have some of that too, but, we also have the stuff like Carol was talking about. and to my understanding to answer your question, Carol, they don't look at our database and confirm that, names have been masked or changed or whatever.

[00:05:03] **Adam:** What they do is they, there is a requirement that you do X, Y, Z, and you show them that you have a policy that every time that you do a, as you referred to it, I think last week, an NPE refresh on production environment, refresh, part of that refresh includes like a data sanitization.

[00:05:19] **Adam:** And you can show proof that it's on the checklist of things that's supposed to be done.

[00:05:24] **Adam:** and somehow you're supposed to be able to, and, maybe I'll know more about this in the coming weeks and months, but, you're supposed to be able to prove that you're actually following the checklist.

[00:05:32] **Carol:** Oh,

[00:05:32] **Adam:** And if you can prove all these things and provide evidence that convinces your auditor, then they will give you credit for it and you can get the certification.

[00:05:41] **Adam:** So

[00:05:42] **Ben:** don't know if this was for the SOC two compliance that we did or for some other type of audit. But I feel like there were also cases where you could present arguments, why their rules weren't important.

[00:05:55] **Ben:** Like they could say every computer has to be password protected and you could present evidence.

[00:06:01] **Ben:** Well, this computer itself doesn't have to be password protected because it's air gapped and it's inside, you know, bank fault. So therefore that doesn't matter.

[00:06:10] **Carol:** doesn't require

[00:06:10] **Adam:** no, there's there. I think it's a blessing and a curse that they intentionally leave some gray area there because they understand that not every business is gonna run exactly the same as every other business. There's a lot of variation. And, and so, yeah, you're right. The, there's the ability to say that this particular requirement is not applicable to us and you give a reason why, or it's not applicable to this particular chunk of data or this computer, like you're saying, yeah.

[00:06:37] **Adam:** You could just have to provide an explanation that satisfies your auditor.

[00:06:41] **Tim:** So you could tell, I do have a problem with this whole thing, because I think it's a point a pointless exercise is it doesn't solve any problems because the history of this is this came out during, if you remember Iran, WorldCom, Tyco, there was a

[00:06:54] **Tim:** huge, all those, there was conflicts of interest with an incentive practices.

[00:07:00] **Tim:** and no one was, there was no real watchdog. and so they passed this Sarbanes Oxley. That's what Sox stands for Sarbanes Oxley act, to like handle this, but what they are actually doing in during the audit, doesn't really, they just say, what are your rules? And you say, okay, here's what we're doing.

[00:07:16] **Tim:** How can you prove that? And he could prove it. And there's really, I mean, there's, they never, you give an answer. They very rarely push back and they don't really dig in deep. So I don't know how any of this will prevent

[00:07:28] **Tim:** what happened with Enron over again.

[00:07:30] **Carol:** is, this is getting this socks thing could be a whole topic for

[00:07:32] **Carol:** It

[00:07:33] **Carol:** totally could be. Cuz I get really confused by it about what they actually reveal and what

[00:07:38] **Tim:** And I'm pretty

[00:07:39] **Carol:** them, right?

[00:07:40] **Tim:** I'm pretty impressed with how much Adam knows about it. Cuz he's like knows all the lingo I'm I

[00:07:43] **Tim:** just know how it affected me. And I'm like,

[00:07:46] **Tim:** so what is the purpose of this?

[00:07:48] **Tim:** And this is what you're doing,

[00:07:50] **Tim:** your purpose and what you're actually doing are two different things. They

[00:07:53] **Tim:** don't match.

[00:07:54] **Adam:** yeah.

[00:07:54] **Tim:** think

[00:07:55] **Tim:** they honestly have expanded it.

[00:07:56] **Adam:** Yeah. It's a good faith effort to try and show that you're doing the right thing. And then. the benefit, the benefit that we are going to get from it, and the reason that we're spending the money to go through the process, on the software and on my time and other people's time to do it is that it's supposed to, and apparently will, reduce a lot of frustration and manual work and, terrible spreadsheet exchanges, of security questions during the sales process, you know,

[00:08:20] **Tim:** And

[00:08:21] **Tim:** that's,that's what it's become. It's a label now. Right? it started out as we're gonna prevent Enron from happening again.

[00:08:27] **Tim:** But honestly, if you're an Enron and you're already cheating people, you don't think you're gonna cheat the socks. Auditor,

[00:08:33] **Tim:** no

[00:08:33] **Carol:** you're gonna bypass it.

[00:08:35] **Tim:** So it's become a good housekeeping stamp of approval. It's what

[00:08:38] **Tim:** it's become and companies, and these auditors make a huge amount of money and spend a whole lot of your time to get this stamp of approval. So you can hand another company and say, Hey, look, we're above board.

[00:08:49] **Tim:** When in fact you could totally not be above board.

[00:08:53] **Carol:** right,

[00:08:53] **Adam:** And I mean, that's the reality of the situation is that like 80 plus percent of the stuff that this is, telling us that we should be doing, there's a really good chance that we're already doing. And the other 20% is either like we didn't know or doesn't apply or,like we just hadn't gotten to it yet or, that sort of thing.

[00:09:12] **Tim:** I mean, the positive will say about it, even though it's wildly expensive and time consuming, it does make you look at your processes.

[00:09:19] **Tim:** It makes you look at what you're storing, what, how you're storing data, particularly financial data and look at it and go, oh, I didn't know we were doing that and fix it.

[00:09:27] **Adam:** yeah.

[00:09:27] **Carol:** So is this the one where you even have to like lay out what your plan is for, if you were to have a breach, like you have to give them like what your response is or is that a

[00:09:36] **Carol:** different audit that we went through?

[00:09:38] **Adam:** there is a part of it that, like one of the TCS that we selected does require that we do penetration testing, but I don't think that it necessarily, again, ask me again in say a month and I'll probably know a lot better,

[00:09:51] **Carol:** answer. May change. yeah.

[00:09:52] **Adam:** yeah. I haven't come across anything yet that, is like, okay, in the event of a breach, this is how we'll handle it,

[00:09:58] **Carol:** this is that response. This is how long we have to respond. Yeah. Okay.

[00:10:01] **Adam:** right. And there's other things like, there's just common sense stuff that I wanna do that may or may not be listed on there, but like, I wanna have a security, responsible disclosure page on our website and in our documentation stuff. And I wanna have,potentially like a bug bounty or something, I don't know.

[00:10:15] **Adam:** But

[00:10:16] **Carol:** I love

[00:10:17] **Adam:** we're like way down a rabbit hole here.

[00:10:18] **Carol:** Oh yeah. Sorry.

[00:10:20] **Adam:** that's okay.

[00:10:21] **Tim:** We

[00:10:22] **Carol:** Let's just go back. This was a triumph, right?

[00:10:24] **Adam:** Yes. Yes. The

[00:10:25] **Adam:** triumph was that I,

[00:10:26] **Adam:** I have started the work here on this SOC two thing, and I've also still managed to get some other work done too. So feeling good about that. some real work, right? this is the

[00:10:35] **Carol:** Great job, Adam. We're proud of you.

[00:10:37] **Adam:** Yeah. This so stuff is just meta work so that we can continue working and I'm managing to get real work done too.

[00:10:42] **Adam:** So I'm happy about that, but let's move on Ben. how you doing?

## [00:10:48] Ben's Triumph

[00:10:48] **Ben:** Me, I'm doing good. And I should say I'm doing much better than I have been doing. The last two shows where I think I was clocking in failures of just feeling overwhelmed.

[00:10:56] **Tim:** good for you.

[00:10:57] **Ben:** I'm, I'm going triumph today. Hard triumph. And, I'm I feel like over the last week or so, I've made some really exciting steps at work.

[00:11:07] **Ben:** So fundamentally at work we deal with prototypes and prototypes are composed of flat. PNG and JPEG files that people upload. And I have for the last few years, been very enamored with this idea of breadboarding, which was presented by the people from base camp about creating super low fidelity, more like brainstorming ideas than actual designs.

[00:11:32] **Ben:** So you can design a screen just by saying what's supposed to be on it instead of being bogged down with design itself. So like, here's the title of the page. Here's a bullet list of what's supposed to be on it. Here's some calls to action and like, that's the extent of just kind of getting what's

[00:11:45] **Ben:** in your head out on paper

[00:11:47] **Adam:** a

[00:11:47] **Adam:** prototype for the P.

[00:11:49] **Ben:** yeah, exactly.

[00:11:50] **Ben:** So that's a great way to put it. and I was like, it'd be kind of cool if we could somehow overlay that concept onto the functionality that we have at work. And, ideally what I'd like to do is create some sort of form where people can start to enter information. And then I snapshot that as a PNG.

[00:12:08] **Ben:** Now there's a really cool library called HTML. I think it's lemme check. It's called HTML to canvas. Yeah. HTML to canvas by this guy, Nicholas, th Herzon. And basically you can just take a screenshot in the browser of the currently rendered page. And he does it by lookingat the runtime styles of all the elements on the page and writing those to canvas and then taking the canvas and creating a blob that he then converts to an image.

[00:12:32] **Ben:** And, it's really cool. And, but we talked about this the other day, I think in the notes to self that, if I need to introduce the third party dependency, now I have to go talk to security.

[00:12:43] **Carol:** So many steps

[00:12:44] **Ben:** you know, and on the H out canvas page in the about me somewhere, I think in the GitHub about me, he says, this is not production ready.

[00:12:50] **Ben:** You should not be using this for production application. So I thought to myself, all right. I understand fundamentally what he's doing. I mean, it's all magic. I don't know how he's doing it, but fundamentally, I understand that he's taking the browser. And calculating things and then writing into canvas, I'm like, let me take a day and see if I can get a proof of concept working, using the same idea.

[00:13:11] **Ben:** And, over the course of, I think it was a Wednesday, I took an entire Wednesday and I basically just got, here's a diviv with a title and here's a diviv with some text and here's a diviv with a button. And can I use things like window dot, get computed styleand element dot, get bounding client wrecked or whatever it's called and essentially say here's the paddings and the borders and the font properties.

[00:13:34] **Ben:** And here's the top left with and height of the element. Can I then do canvas 2d rendering to, to try and render this as an image? And at the end of a day, I had some blocks and some texts doing some things

[00:13:48] **Ben:** and yeah, it was very exciting. So.

[00:13:50] **Carol:** Yay.

[00:13:51] **Ben:** I was like, okay. So then I created a mold window in our application where you could build this little thing and you could hit publish.

[00:13:57] **Ben:** And essentially what it does again, is it just takes all that jazz that you put together, renders it an image, and then uploads it to the same existing upload image API that we have today. So essentially I'm just creating like a very poor man's sketch application. So then I got that working and then I'm like, yeah, but it kind of sucks that you can't edit it because once I flatten into it an image, there's no data.

[00:14:21] **Ben:** So then I had to build a data table to persist that kind of JSON blob, which meant, okay, now I'm gonna create a, MySQL table that has a JSON column, and I've never done that before. So that was really exciting. and then, I don't know, it was just, I, baby set my way from this. Let me take a day of R and D to see if I can make this happen at all to like a week and a half later, I feel like I have a fairly full-fledged feature in the application running.

[00:14:45] **Ben:** Where people can create these breadboard placeholders, come back, edit them, see how they're overlaid on the screen, create links between them using the existing functionality. And I don't know, I just feel like I took the, this like spark this baby spark of an idea, and I grew it into a adolescent teenager who apparently doesn't wanna learn how to drive,

[00:15:08] **Carol:** so do you have this out being used

[00:15:10] **Carol:** or is it still on develop? Nice,

[00:15:12] **Ben:** I'm on,

[00:15:12] **Ben:** I'm on the legacy platform. I don't wait for anything.

[00:15:15] **Carol:** No. So your development not only is out there. It also does not contain a note that says not production ready yet.

[00:15:23] **Carol:** I think that's a win in itself.

[00:15:26] **Adam:** Ben was just, developing it in production over FTP.

[00:15:30] **Tim:** Yep.

[00:15:31] **Carol:** Nobody knew.

[00:15:32] **Tim:** Checks out can confirm.

[00:15:35] **Adam:** hang on. I wanna confirm something real quick. You're saying breadboards, like the food bread.

[00:15:40] **Ben:** No. So there's a, there's an,I think it's from an electrical engineering term

[00:15:44] **Ben:** there, breadboards arelike a thing you put chips on. I think,

[00:15:48] **Adam:** Yeah. Yeah.

[00:15:48] **Adam:** There's a, yeah. when you're, putting together circuits, you can use a breadboard to, verify you've got everything that it works without like soldering it together. Yeah.

[00:15:58] **Ben:** Yeah. So I, I think that's where they, that's where the 37 signals guys. I don't know if they coin the term from a software engineering standpoint or if they just, or if they borrowed from somewhere else. I mean, clearly they borrowed from the electrical engineering breadboard, but I think that's the idea is it's very rough proof of concept.

[00:16:13] **Ben:** Just seeing if the idea works before you actually pour design effort into it.

[00:16:18] **Adam:** right. No, that makes sense.

[00:16:19] **Carol:** total, like side tangent from that, we got

[00:16:22] **Tim:** we never do that.

[00:16:23] **Carol:** got the email that was like, Hey, while you're doing your career conversations, we think that you guys should totally talk about the four DS of software development and about how design's important. Well, I was like the four DS. I was like, are we talking about some type of like anatomy here?

[00:16:40] **Carol:** I was like, what the hell? And I immediately went off on, this is not a software thing. Right. And I Google it. I'm like, oh, look, it is a real thing. so yeah.

[00:16:51] **Carol:** So

[00:16:51] **Tim:** your mind out the gutter, Carol

[00:16:52] **Carol:** know where things like come from or how they evolve, but calling something, the four DS of what we do is not what

[00:17:00] **Carol:** I

[00:17:00] **Carol:** think of when I hear four DS.

[00:17:03] **Tim:** mm-hmm

[00:17:05] **Adam:** before we move on Ben, and I don't wanna throw a wrench in your gears or anything here, but, talking, hearing you describe how this works, where you're like. sort of trying to redraw HTML elements in the in canvas so that you can get a screenshot from JavaScript. And then I assume that you're like uploading that, image so that can be saved on a server or something.

[00:17:24] **Adam:** So, I mean, if server side, control is in the, is an acceptable path to take, I think that there's an easier way to go about this and you'll get something. And now I get that the whole point here is for it to not be pixel perfect. But if you already have some HTML or if you can easily,throw together HTML to represent what you want to represent, it is really surprisingly easy to use puppeteer, to like pop open a browser instance and tell to take a screenshot and save that.

[00:17:54] **Adam:** So you can just be like, here's some HTML on a file. Gimme a screenshot.

[00:17:58] **Ben:** A hundred percent. And again, if this were not the legacy application, People would not ring their hands at me adding infrastructure because infrastructure, oh my God, we're doing just now, in the light of all of the, to say it nicely, the reorganization that we've done lately at work, we've been doing a lot of cost analysis of the platform and AWS and Lambda and all that stuff.

[00:18:23] **Ben:** Oh my God. Yo,we have petabytes of files stored on S3. I literally have never known anybody who had petabytes of anything. I let

[00:18:36] **Tim:** you have to be in our registry for that?

[00:18:39] **Ben:** I don't it's

[00:18:42] **Adam:** it took him

[00:18:43] **Ben:** took me a second. Yeah. I mean, that's just, sorry. I forgot where I was going off. Oh yeah. Yeah. So the idea of adding additional infrastructure to do anything is like not a conversation that anyone at the organization's gonna have at this time, but yes, I

[00:18:56] **Ben:** agree

[00:18:56] **Adam:** enough.

[00:18:58] **Ben:** Doing it, this was, again, this was the path of least resistance,

[00:19:02] **Adam:** And necessity is the mother of invention.

[00:19:04] **Ben:** the most frustrating thing is, so I took this concept. I got to the R and D I proved it out. I built it, I deployed it. People are using it. I have analytics on it showing clicks and similar actions. So I put it into our internal TV demos channel

[00:19:20] **Ben:** and like one person , it's like one person was like, well, that's cool.

[00:19:25] **Ben:** And it's like, again, I understand no one's on the legacy platform. I'm sure 80% of the people look at my video and wonder why I'm even working on the legacy platform at all. But it's like, it's built up so huge in my mind, and I'm filling all the celebration and I'm seeing the journey and overcoming hardship.

[00:19:44] **Ben:** And then to put it out there and get like almost no feedback. It's very, it's its incredibly demoralizing,

[00:19:50] **Carol:** Listen, we wanna join this thread like this channel, just to give you props because we love. You do

[00:19:57] **Tim:** just.

[00:19:58] **Ben:** saddest thing is like the slack version of sending yourself flowers at work.

[00:20:07] **Carol:** oh man, let's go. Let's hear

[00:20:09] **Ben:** I will post my video and then I'll just put like a whole bunch of my own emoji reaction. Like Christian, like all the reactions on it. I'm like

[00:20:16] **Carol:** Like party Panda.

[00:20:17] **Ben:** Yeah. Yeah. I'm like these are all the things people would put on there if they cared.

[00:20:22] **Carol:** Yeah. Listen, you're just

[00:20:24] **Carol:** making it easier. So no one has to like reply, like they can just click on your automatic, like entry they're like

[00:20:30] **Carol:** party Panda. Yes. Plus one

[00:20:33] **Ben:** There you go. There you go. Paving the path. Oh, all

[00:20:38] **Carol:** great job on winning. Great

[00:20:39] **Carol:** job,

[00:20:40] **Ben:** you. Thank you. Thank you. It feels good to be back. Tim, what about you? What do you got going on?

## [00:20:45] Tim's Fail

[00:20:45] **Tim:** Curse you bin you transferred your fails to

[00:20:48] **Carol:** Yeah.

[00:20:49] **Tim:** Yeah. This,this whole one other whole week. So like of the week, Friday, all of a sudden I was just, I've been in a big brain fog Friday through Tuesday, just in a complete brain fog. I just can't think straight. I don't have COVID.

[00:21:02] **Tim:** just, I just can't think I look at a page and I can't read it's. I don't know. Maybe I have temporary add, I don't know what's going on with me. But yeah, I just, it was had a really rough patch there for several days where I just really couldn't do anything. I tried my best.

[00:21:19] **Adam:** I was just gonna say, I think that, you got, a case of the fog old guy.

[00:21:23] **Tim:** That was good. That was good.

[00:21:29] **Tim:** I'll give you that one.

[00:21:30] **Carol:** Yeah.

[00:21:32] **Tim:** and maybe, the kids did start back to school and on, on previous podcasts I talked about, I sort of have this sort. Mental hangup about going back to school cuz I was bullied, in, in school. so maybe that was it, but yeah, finally by Wednesday it lifted and I was back in the game and today I had an extremely productive day.

[00:21:50] **Tim:** So I'm pretty happy about that. It was

[00:21:51] **Tim:** just like mourning, the was mourning the wasted time. Right.

[00:21:54] **Tim:** it's like all I, even over the weekend I didn't have work to do. I couldn't do anything around the house. I could, I watched, I just watched a binge watch TV pretty much all day long and just barely got outta bed.

[00:22:07] **Tim:** So I just think I a little depressive episode there and, but I'm back baby. I'm back.

[00:22:13] **Carol:** Well, I'm glad you took your

[00:22:14] **Carol:** mental break and now you're back, cuz that's good.

[00:22:16] **Carol:** Yeah,

[00:22:17] **Tim:** Got it. didn'tplan on a mental break, but I guess,my, my mind told me I had to, so,

[00:22:22] **Carol:** do what you gotta do sometimes.

[00:22:24] **Tim:** Yep. For sure. I appreciate that. How about you?

## [00:22:27] Carol's Fail

[00:22:27] **Carol:** Oh man. Thanks Ben. Cuz this is apparently like trickle down effect here. just gonna throw this out there, you know, like some days you have good days and some days you have great days and other days are just like fantastic.

[00:22:40] **Tim:** Can confirm.

[00:22:41] **Carol:** I've had none of those lately. Let's just be clear. I just, I am ending every day with a list of things I need to accomplish tomorrow bigger than what I started with when the day started.

[00:22:55] **Carol:** And it's. Piling up. And I know it's because of the time right now, we're at like a quarter in we're doing reviews. and I'm pretty like serious about when people tell me something, like I take it to heart and I work very hard to resolve issues for my team, because I care about how their success is. So when I'm like reviewing some of these requests, I'm like, okay, let me go into these reviews with the ability to actually answer like what their concerns are, which takes up a lot of time of just being like, okay, let me go find the answers to these questions.

[00:23:28] **Carol:** So then the list of things from yesterday, just do not get accomplished. And then tomorrow's list was just even bigger. So last night I couldn't sleep. So I ended up getting up at like 1130 and was like, I need to write code. Like, this is the only thing I need to do because

[00:23:45] **Carol:** right now laying in bed, I know how to fix this.

[00:23:49] **Carol:** This morning, I didn't know how to fix it. And I had a lot on my plate and I've kind of been thinking through it, but I was like, I know how to fix this right now. So I came in here, got on my computer and like worked till like one o'clock this morning and was like, oh hell yeah, my code works and I'm super happy about this.

[00:24:04] **Carol:** And now I can go to sleep. So then I got this morning, like, 6:00 AM and was like, let's go. And I was like, actually I wanna sleep another hour. But then I was like, let's get up again. And now let's actually get going. So when I was going this morning, I actually felt more motivated because I actually pro like solved one of the big problems it's been lingering around all week, but I still just am ending every day with a to-do list.

[00:24:26] **Carol:** That's just growing and growing. And I hope by next week I can get out from underneath it and actually start making progress on some things. But the good thing is, is the top things that I'm checking off are things that people need for their career and for their growth. So I am proud of what I'm checking off.

[00:24:42] **Carol:** It's just. It is frustrating to not end at some point. So

[00:24:48] **Ben:** is this, do you think, because you've taken much more of a management role the last couple of months, or is it

[00:24:53] **Ben:** just

[00:24:54] **Carol:** it

[00:24:54] **Carol:** absolutely is that's exactly what it is. And it doesn't help that my boss told me I am so happy. You're taking these things off my plate because he's like asking questions. He's like, oh, what about this? I'm like, oh, that's done. That's done. This is done. Like we've hired three new people.

[00:25:12] **Carol:** And he's like, what about all these things? I'm like, I took care of them. We got it covered. Just go back to what you were doing. That was the point of promoting us. Right. So then now when things do pop up, I'm like, oh, I'll take that on. Like, you go do your thing. What you're doing is way more important. So I'll take some of this work off your plate, but then my plate just keeps growing and I'm like, where am I supposed to write code at?

[00:25:34] **Carol:** somebody just let me code again.

[00:25:37] **Tim:** Learn to say no, Carol.

[00:25:38] **Carol:** Yeah. Yeah.

[00:25:40] **Adam:** the stuff that's piling up, is this coding work or is this management work?

[00:25:44] **Carol:** Coding work. That is the thing. I'm letting slide first. The thing that's piling up at a deadlines on the project. So I'm having to like talk to the project owner and be like, Hey, this is still not done. Do you want me to offload it to someone else with where I am? Or do you want me to keep holding it?

[00:25:59] **Carol:** Because here's why I'm not getting done with it. And they're like, oh no, it's fine. It's fine. This isn't like super critical. You're good. Keep going with it. So then, but that is the very first thing I drop now is what I have to do for code. And people work is more important cuz growing teams who are important and getting some code out, cuz everyone I'm growing can write the code.

[00:26:17] **Carol:** Just need to make sure they're growing.

[00:26:19] **Adam:** you're a force multiplier now. Carol

[00:26:21] **Carol:** Trying train my best. But next week I

[00:26:24] **Carol:** plan to have less of a to-do list.

[00:26:28] **Ben:** Heck. Yeah.

[00:26:29] **Carol:** Hey,

[00:26:29] **Adam:** All right. I guess that wraps up tri and fails. So now let's talk about what makes a good roadmap. And Tim, you kind of brought this in. Do you want to, give us the intro here.

[00:26:39] **Tim:** Yeah. Sure. So, so at work we are a company of many companies, constellation software, which is a Canadian company and has. Thousands of software companies, all software companies, and they do these things kind of a best practices thing. So when I was in may, I was at, a conference, not really a conference, sort of like a, justa meeting of different people from different companies and different, positions.

[00:27:04] **Tim:** And they gave us all an assignment. We had to come up with a topic and then we would as a group. And these it's all different roles and different, companies and then come up with the best practices, playbook. And the idea is across all these thousand, over a thousand companies, they can, build these best practices and have them for whenever they cuz they're constantly buying new companies.

[00:27:26] **Tim:** When new company comes on, they can say, here's the best practice for X and here's the best practice for Y. And so one of the things we chose was, product roadmaps. And cuz to be honest, I've been in a product role. Technically I'm getting more into a product manager type role and building a roadmap, both internal and external is really hard.

[00:27:51] **Tim:** And a lot of the roadmaps that I see that come from other companies tend to suck, that they're not truthful. In fact, that's what we're calling it. roadmaps be honest. what we're trying to tackle is how do you build a honest, reliable roadmap?

[00:28:08] **Adam:** okay. So, I mean, maybe we should start with,you sharing some of the stuff that's in your plan already or in your best practice here. I guess for maybe start a little bit from first principles, like for somebody who doesn't really understand what a roadmap is, how is it different from like a project plan or what purpose does it, what, need does it solve?

## [00:28:30] What Is A Roadmap

[00:28:30] **Tim:** All right. So here's how we're defining it. And totally I'm asking for help here. come back to you, Carol. so how we're defining it, is that a roadmap it's, it's a long term development plan that provides all the stakeholders with information they need. Now that means nothing, but basically a roadmap is to say, we have a current product.

[00:28:49] **Tim:** Here's how it is now. Here's how it's going to be in the future. So here's things that we're gonna add. Here's things that, we're gonna add new features, or here's completely new products as a company that we're gonna build. And present that both internally to the company, because you give a lot more detail to inside the company as to the reasons why and things like that.

[00:29:10] **Tim:** And then, and also sort of a marketing thing for your existing customers to say, we know the product is this right now. Or we know that, our product suite is missing these pieces of software, but here's, what's coming down the road. And so that's what we're defining as a product roadmap

[00:29:29] **Adam:** Are there like dates on this thing?

[00:29:32] **Tim:** typically. Right. And roadmap is we're shooting for Yeah.

[00:29:36] **Tim:** For, yeah, definitely. We're shooting for, to have this done within Q2 of next year or, and I don't without getting too far down the road. that's the part that usually I have a problem with

[00:29:47] **Tim:** is like,

[00:29:47] **Tim:** what happens if you don't hit that?

[00:29:48] **Tim:** Right. Are you saying you

[00:29:49] **Tim:** failed? So how do you deal with that? Right. It's like software always takes a lot longer than you think. so how do you deal with that?

[00:29:55] **Carol:** I was gonna say like what we do. So like for instance, we have a initiative right now, which is to improve our vendor communication. Right? So that's one of our big roadmap at like items right now is to address everything that came back from our, like, State of the user, like survey that we sent out.

[00:30:12] **Carol:** And it's what, they said were problems with the system. So in our roadmap, we have like three quarters worth of work that are addressing how we will improve communication with our vendors. So each quarter there are these big projects. Like the one I was on with the auto responder, for instance, or this last one, I was on where we moved messaging inside the system and took 'em out of email.

[00:30:35] **Carol:** Now there's another one going on where we're changing, how we actually bulk email people. Like there's a lot going on. those are then broken out into very small pieces of work that are then distributed to the team. So while what's presented to the company until like our out facing vendors is, Hey, our roadmap is we're gonna improve communication over the next year.

[00:30:54] **Carol:** We're gonna focus on improving communication, but what. It's like pushed down to the team level to the granular level, to the people doing the work is here is how your work contributes to this big overarching, like roadmap. You are going to make sure that our, communication is reliable and that it's delivered on time and that we respond as needed.

[00:31:17] **Carol:** So while our customer service team is the people responsible for actually responding in a like true, like timely manner, we are responsible for making sure all that's measurable and we are responsible for making sure that there is no delivery failures. So we're able to see like our small, tiny piece of it play into this big giant one line bullet and a roadmap that says we are going to improve overall communication with our vendors.

[00:31:45] **Carol:** So you do have to take like big pieces out and then break them into smaller ones. And we just click up for it. Click ups. Amazing for that stuff. Like breaking it out. Everyone can see what's going on.

[00:31:55] **Tim:** You said Click

[00:31:55] **Tim:** app,

[00:31:56] **Carol:** Click up. Yep. We just click up.

[00:31:59] **Tim:** I'll have to check that out.

[00:32:00] **Carol:** Yeah.

[00:32:01] **Adam:** I feel like this is one of those episodes where I'm gonna be opening a lot of tabs in my browser.

[00:32:07] **Carol:** We love. I actually, like there are several people who do not enjoy working in click up. I love click up because click up gives you the ability to have like your big bullet point. That's like, here's my top level objective, which is improve vendor communication. And then I have all of these, lower level pieces and each one of 'em play into like a quarter level view.

[00:32:28] **Carol:** Right. So whenever we finish a project, we're able to like mark that as done, or I'll go in there and be like, oh, we're halfway done with it because we're getting close to handing this off to QA. So it makes me feel super happy to see like 50%, 75%. And then all of a sudden I see the big goal, like going from nothing achieved to we're 25% like achieved on

[00:32:51] **Carol:** this goal. Like for me I'm numbers and I'm visual. So feeling like we're making progress is something is big for me. Like I can see it. I'm like.

[00:32:59] **Adam:** Yeah. Seeing those product or, progress bars, start to move that's

[00:33:04] **Carol:** It's huge. It's huge. Yes. Yes. I can commit code all day long and I know I'm doing a good job, but if you put a nice little like fourth way, full green bar over on the right hand side, I am way happier than I've ever been all day. I'm getting there. Yay.

[00:33:23] **Tim:** Cool. So, I mean, that's what we consider to be a roadmap. So I mean, folks could argue one way or another, but that's what we're saying. One thing I found interesting in here that we came up with and I wasn't me who came up with this and I, I don't, there's no reference here. I don't know where these numbers come from.

[00:33:40] **Tim:** they talk about how to structure work on a roadmap and they break tasks down into three different types. So they say on your roadmap, you should have 40% new features, products, or models. So anything that would be a significant change to your product, and then 40% customer care bugs, slow down, anything that stops and interferes with your customer's daily business.

[00:34:03] **Tim:** and then 20% technical debt. Of course, we all know what technical debt is. This is a big section explaining that. There's, the group that we're presenting to is, from all different backgrounds, as far as work roles. So a lot of people don't know what technical debt is.

[00:34:16] **Tim:** They would think, oh, that's just customer care.

[00:34:18] **Tim:** Well, we programmers know it's not right. So, I mean, I don't know. I know how those breakdowns come down. I don't disagree with them. I just don't know why they were picked that way. 40, 40, 20 new features customer care technical debt

[00:34:33] **Ben:** I think it's great that you have actually on your roadmap timefor fixings that are broken and for, technical debt, cuz I feel like every roadmap that I've ever seen is all about new features. And I think that causes a lot of contention between the product side of the house and the engineering side of the house.

[00:34:52] **Ben:** Because I oftentimes think that, the product side views life as this sort of zero sum game, meaning that if you're not working towards this one giant awesome, amazing goal, then you're somehow implicitly taking away from it, by

[00:35:09] **Ben:** working on other things with the opportunity costs. And, but that's just not how life works.

[00:35:13] **Ben:** When it comes to complex pieces of software. There's always a lot of multifaceted stuff that has to be taken into account. And, I think it's really admirable that your roadmap is taking that stuff into account. So.

[00:35:25] **Tim:** Well, you say my roadmap, let me be clear. I don't have a roadmap at work. I've not built one. I don't have one. this is not written by, this is not me. I'm not an expert in

[00:35:34] **Tim:** roadmaps. This is like a, this is a collaborative effort from a bunch of people, which is kind of why our parent company does this.

[00:35:41] **Tim:** It's like, we got a lot of smart people. Let's see what you guys say, what best practices are, even if you're not doing them. And then of course, then afterwards, they're gonna say, well, how come are, you're not doing best practices

[00:35:50] **Tim:** whenever we're not. So we were basically,we're basically building our own bomb for ourselves.

[00:35:56] **Adam:** the beatings will continue until morale approve.

[00:35:58] **Tim:** Exactly.

[00:35:59] **Carol:** I will add, I had that exact same conversation today where our product owner was like, oh yeah, you guys pointed that at an eight. So I just assumed it would be done. Like the first week of September, I was like, you just assumed we have resources to put on it.

[00:36:15] **Carol:** No, one's working on this. No, one's going to be working on this till the first week of September. So if you need this prioritized, you need to tell us to bump it up in the backlog. Otherwise it's not getting worked. You can't just assume because we put the eight on it that, yeah, it'll be done by the first week of September.

[00:36:33] **Carol:** That's not

[00:36:34] **Carol:** how this works. There's still people who have to do the job who are. Working on Zendesk who are still maintaining work that they just put out who are developing what they're on. Like we went through this. That doesn't mean it's in work right now. Like you can't just say points equal to date.

[00:36:50] **Carol:** That's not how this works. You wait till we get resources to it. Oh, it's so frustrating. It's so

## [00:36:56] Internal/External Roadmap

[00:36:56] **Adam:** Yeah. So I would really like to go back to the idea of having technical debt on your roadmap.

[00:37:01] **Adam:** well, so, what I think this, brings up is the idea of having an internal and an external or public facing roadmap, at least to your stakeholders versus your team. and like, I think it makes total sense to have technical debt on your internal roadmap, but I.

[00:37:16] **Adam:** In a lot of situations like mine, for example, having, something that says we have done less than perfect work and we need to go back and clean it up on a public facing roadmap, people are just gonna be like, why am I paying you to do less than

[00:37:30] **Adam:** perfect work?

[00:37:32] **Ben:** Can't you just build it right? The first time.

[00:37:34] **Tim:** That. And that's one thing that as we actually are talking right now, I did mark up our document and say, we didn't explicitly say, do these go on the public facing roadmap. Right? So technical debt, I wouldn't imagine you would. Right? Who cares your public, your people using your product.

[00:37:50] **Tim:** It's not gonna fix anything. It's just gonna make the code more maintainable. My other question is customer care ones, bug slowdowns, anything that stops or interferes with your customer's daily business? I. We also didn't explicitly say, does that go on the only the internal one? And I would say yes, it only goes on the internal one because, if you publish out there one, you're emitting your flaws in public, which, for marketing

[00:38:16] **Tim:** reasons, isn't great.

[00:38:16] **Tim:** and two it's like, they're gonna say, well, you're gonna spend, why don't you spend 80% of your time or 90% of your time on, on these bugs and slowdowns that affect my daily business. I don't care about this new X widget or whatever, if you can't even get this right. So I think that, yeah, the 40, 40, 20, the customer care ones and the technical debt,

[00:38:35] **Tim:** They only show up on your internal facing, one. And so that's to let people know, Hey, we know we're gonna be building new stuff, but we're not gonna stop trying to fix the stuff that we already know is an issue. And therefore we can budget time.

## [00:38:48] Justifying a Public Roadmap

[00:38:48] **Adam:** when you're showing off your public roadmap to stakeholders and they ask you like, this is all you're planning on doing for the next year, why aren't you doing more? Right. It seems like you should be able to get that done in less time than a full year. How do you justify? I mean, certainly, you can say, well, look, if you guys would stop filing support tickets, then we would be able to spend more time working on new stuff.

[00:39:09] **Adam:** but you have to handle. Customers and their expectations with a certain grace, right? You can't just be like, this is part of the software thing. This is the way the world works. Sorry, you don't like it, but that's, you can't be, you can't give 'em the blunt truth that technical debt happens and customer care work is necessary.

[00:39:29] **Tim:** Yeah. So one of the things that, that we talk about is that, so you spend a lot of time on your roadmap and you wanna share it. but you should share your roadmap at a high level and just use it to show the direction. and so, you showed at a high level, you give, and, I need to make a note of this too.

[00:39:45] **Tim:** We don't cite this, but I would think a good practice would be the internal roadmap. You set certain dates, right? And then you pad out those dates on your. Public facing

[00:39:55] **Tim:** one. Right? So that if you deliver early, you look like a rockstar and it, first starting out, people are gonna complain. But if you just consistently do this year after year,they're gonna start to believe that your roadmap is accurate.

[00:40:06] **Tim:** even though you're kind of padding it internally, which is totally necessary, but yeah. talk, and then for those kind, the question that you gave Adam. So I think, these are things that kind of become discussions with the customer, depending on how big you are, we don't have millions of customers, we have under a hundred, so those can be conversations with you, discuss the roadmap with them.

[00:40:30] **Tim:** And then when those things come up, they say, well, why is this the only thing you're doing, then you just kind of explain, well, we recognize that there are, current bugs, there's current issues. And those are also, we're working on those as well at the same time. And also, Computers, we, you kind of explain technical debt to them, codeover the years.

[00:40:46] **Tim:** It, even though it doesn't change, it kind of there's assumptions that were made before that are no longer valid and things really need to be, refactored or re are changed in a way that they're more efficient to maintain. And so we're spending also a portion of time in that. So yes, we would like to spend a lot more time on these new features that you want.

[00:41:05] **Tim:** But, in the reality we have to do both, you can't, you have to continue to clean your house while you're putting on an addition.

[00:41:12] **Carol:** Yeah, you actually have, some points in there that I love. It's like, basically when you're talking about this, you have quality cost and time, right? So it's. Simply said you will not get a quick high quality solution for a low cost. You must pick two of the three points, do it quick and cheap, but with poor quality or do it high in a short amount of time, but you're gonna spend a fortune paying for that like lower time.

[00:41:40] **Carol:** Right. And it makes sense because when you put more money on it to get it done faster, you put more resources on it. And I'm not saying that more resources always means better quality because we've all seen situations where you throw more resources at a project and it just burns to the ground because nobody can communicate with what's going on.

[00:41:59] **Carol:** Like it, it happens. But typically that's what happens. Like you're like, okay, high quality, short time doesn't happen. High quality means it takes time to develop, to design, to deliver like those things. Aren't quick. And you have to just kind of figure out what are your important things? Do you want quality or do you want out the door? That's how tech debt happens because people decide that I wanna out the door and I don't want quality. What's more important is that it's here on Monday. Not that it's here in seven Mondays from now when you've designed it correctly.

## [00:42:34] Buy-in

[00:42:34] **Tim:** And I mean, I think the portion of it that I agree with most is getting buy-in internally.

[00:42:40] **Carol:** Oh, huge. Right.

[00:42:42] **Tim:** yeah, because I have in the past tried to build product roadmaps and I didn't do this step well enough. And it led to all my efforts pretty much being wasted. Right. So, and depending on the size of your company, you have different people.

[00:42:56] **Tim:** And if it's a small company, multiple people, a couple people, two, three people could fulfill all these roles, but you need buy in from your leadership team. And by buyin, if you're the person in charge of product, you build a roadmap, get with your team and you say here's all the new products and features.

[00:43:11] **Tim:** and you kind of build that part of it. Cuz typically you'd probably know that, but you talk to your leadership team and say, all right, what new products do we do? We need, what things do we need to fix? and do you get buy from them on that? You talk to your customer facing teams and you say, all right, what are the things that your customers are complaining about the most?

[00:43:28] **Tim:** what would do you know, we really need to shore up here, talk to your development teams and say, okay, what, here's our new features? here's the bugs cuz and here's the technical, what technical debt, do you think needs to be added in here? And do you agree with all these other things and also legal?

[00:43:43] **Tim:** A lot of times, if you have a legal

[00:43:45] **Tim:** department they're for yeah,

[00:43:47] **Tim:** they're forgotten, right? Compliance, how's this gonna affect, contracts, existing

[00:43:50] **Tim:** and then. We list human resources. I'm struggling to find out, figure out what they could add to this. I don't know, human resources tends to deal with the employees that you have, but that's what we're saying, but so the thought is get all your stakeholders involved as early as possible act for feedback, react on it, get confirmation and approval from all of them, and then communicate on a regular basis, internally, about how the roadmap is progressing so that you can explain any sort of issues or things that are coming up with it.

[00:44:23] **Carol:** So for human resources, I think it's important for us because when we are asking our teams to deliver something, if our people, we call them the people team, right? So if our people team don't have a clear understanding of where the company's going, it's hard for them to protect the people, right?

[00:44:37] **Carol:** So you need their buy-in because they're the ones that have to protect your employees. They're the ones that help keep people happy who help understand the market, who help understand like hiring all of that stuff. So they need to have an understanding of what you're requesting of your people before they can protect them.

[00:44:54] **Tim:** Yeah. Okay. Yeah. I could see that. Yes. I was thinking, so maybe you're going in a direction and it's gonna require new technology, which requires new hires.

[00:45:00] **Tim:** Right? So human resources like, oh, I need to start thinking about recruiting.

[00:45:04] **Carol:** Or you're about to force some people onto some overtime who haven't been on overtime before. And you're like, look, we know there are deadlines. And somehow our people team can just say things way nicer than I can cuz I'm like, dude, it sucks. We have to work at 6:00 PM tonight. Suck it up buttercup, we're getting through this.

[00:45:23] **Carol:** And for some reason, the people team just make it sound off flowery and nice. And you're like, okay, cool. I would do that

## [00:45:29] How Often Should You Update The Roadmap?

[00:45:29] **Adam:** So How often should you be updating your roadmap? And like, I've, I could think of like, okay, we're gonna release a new update to the roadmap every year, right. Or every quarter. or I feel like I've seen some companies that just have a continually updating roadmap.

[00:45:43] **Adam:** It's like, okay,

[00:45:43] **Adam:** time is passing all the time.

[00:45:45] **Adam:** And, you know, even even like weekly or daily, like, the roadmap is just this, like continuously think of it like a Trello board, right? Like, so we've got done planned and in progress. And you're just moving stuff between columns. Well, you can imagine that as the roadmap out planning into the future, and then as things get done, you're moving them through.

[00:46:05] **Adam:** and instead of maybe like Q2 of 20, 23, you just say like next quarter and, like quarter now, quarter plus one quarter plus two quarter plus three, whatever. and that way it's things are just constantly moving in one direction.

[00:46:19] **Adam:** I guess what I'm saying is like, is there a good piece of advice that anybody has.

[00:46:25] **Tim:** There's nothing in here on that. That's a good question.

[00:46:27] **Ben:** and then sort of dovetailing with the idea of how often do you update it? How far out into the future do you look.

[00:46:33] **Carol:** not bar

[00:46:35] **Carol:** like, like I get, there are some big pictures, right. But the state of like, for what I do, our software is all about the state of mortgages. Home cells inspections, like all of that's what my software does. So ours is fluctuating based off of, things like refinances things like home cells, homes available.

[00:46:58] **Carol:** So as that changes, like our roadmap has to change to match the market. So we are in a market that isn't quarter to quarter, there are big changes, so we have to change what we're doing. So like right now, our initiative is to be the number one provider for products that digitize like modern appraisals.

[00:47:15] **Carol:** So of course there's a ton of efforts under that, but that's where we're trying to go is somewhere that takes you more modern and digitizing what we do. So it's great. But. If in six months, everything crashes, then our roadmap has to completely change from what it is like. COVID completely changed our roadmap.

[00:47:34] **Carol:** We went from trying to be more in house and more people focused to now we're doing everything via point of contact, taking pictures of their own homes. So I think part of your roadmap planning depends on what your market is and what's available to you and where you're going with it. So five years is great, but three months is really important sometimes.

[00:47:54] **Tim:** Yeah, no one knows the future in five

[00:47:56] **Tim:** years. That's just a waste of time to even try to

[00:47:58] **Tim:** do that.

[00:47:59] **Carol:** I hate those questions when people are like in interviews and stuff. And they're like, where do you see yourself? In five

[00:48:03] **Carol:** years? I was always like in five years, Peyton will be one year out of college and James will hopefully have his own family. So I'm sure me and the dog will be happy. Like who the hell knows what five years looks like, like ask me what I'm gonna be like in six.

[00:48:21] **Carol:** I'm gonna be

[00:48:21] **Carol:** trying to be the best version of myself. I can be like, I don't know, like, I don't know, five years. That's weird. Sorry. Didn't mean to go off there.

[00:48:30] **Tim:** Yeah, I, II think you made a good point there before you went on your end.

[00:48:33] **Tim:** Um,

[00:48:33] **Tim:** it does kind of depend on your,

[00:48:35] **Carol:** your market.

[00:48:36] **Tim:** on the, your market.

[00:48:37] **Tim:** that you're dealing with. Right? I mean, the rate of change for, a company that's servicing the insurance and banking sec sector is gonna be very different from,

[00:48:46] **Tim:** trying to think higher ed.

[00:48:48] **Tim:** And I'm trying to think of something that's really fast-changing what would be a

[00:48:52] **Tim:** people that are constantly making updates. Yeah. But I mean, stock market software itself, I don't know if it would be changing often.

[00:48:59] **Adam:** Yeah, I Don.

[00:49:00] **Tim:** mean, you

[00:49:01] **Carol:** So

[00:49:01] **Carol:** for us, We went from focusing on like home sales, because that's what was happening a few months ago to all of a sudden the government's like spiking interest rate. So now all of our products that we're focusing on are refinances are helos, you know, your home equity line of credits. Those are the things now where we're putting more of our focus on because the market has taken a dip in new cells and we're onto people trying to use equity that they've already built in their home.

[00:49:30] **Carol:** So we constantly have to change based off what the market's doing, where we put our money to our products.

[00:49:35] **Tim:** Yeah, I would think, depending on, like you said, the customer space that you're playing in and the rate of change that is expected, your roadmap, could be very short or very, or, over a year, maybe two years. I think the important thing is that you need to make sure it's and help your customers understand it's also flexible.

[00:49:53] **Tim:** You don't want to like some new, COVID hits and now all of a sudden priorities change, there's a new need. Now software needs to react to that. You're not gonna say Nope. Nope, Nope. our roadmap said we're not, doing anything

[00:50:04] **Tim:** like

[00:50:05] **Carol:** stuck here for three good years, boys.

[00:50:07] **Tim:** Right. Yeah.

[00:50:08] **Tim:** Yeah. So you react and say here's, but you have good reasons.

[00:50:11] **Tim:** Here's why we're changing this. we're adding this new feature because it makes sense right now we're pushing this one further down the road, but it's still on the roadmap. Sothe roadmap really needs to be a dynamic living document. I think.

[00:50:23] **Ben:** for whatever reason, that's just reminded me way back in the day. I think I used to watch shark tank. I don't know if it was shark tank or precursor to shark tank

[00:50:31] **Carol:** Like that's where the, where they come home with their ideas.

[00:50:33] **Carol:** They're like, Hey, buy

[00:50:35] **Ben:** And sometimes

[00:50:37] **Ben:** people come on with a product and it's just clearly a terrible idea. Like, like you can't wrap your head around how anyone would think it's a good idea.

[00:50:47] **Ben:** And the judges would be asking you, oh, how much effort have you put into this? And they'd be like, oh, I've poured the last 20 years of my life into this. And I've refinanced my home and I've taken loans from all of my family members. and it just, at some point you have this vision of what you want a product to be, and no amount of evidence will convince you that it's the wrong path and it's, and it's like, you have the roadmap has to be a guide, not a master.

[00:51:15] **Ben:** And sometimes I feel like people get tunnel vision, Intel. This is what's on the roadmap. So we can't deviate. and no matter what our customers are saying, we can't deviate, no matter what our engineers are saying, we can't deviate, but it's so hard to know because like, there is something to be said about great and determination.

[00:51:33] **Ben:** and there are people who win by sticking to their guns. But clearly there are people who have no sense of reality and ruin their lives by sticking to their guns. it's hard to, it's hard to know.

[00:51:46] **Tim:** I, I thinkwith the roadmap that when you communicate with your customers, there's. Three things that can happen. One, they just go, oh, that's nice. Which means they're ambivalent to it.

[00:51:55] **Tim:** Or they don't even say anything two. they say, Hey, do you think you could move this feature up sooner?

[00:52:01] **Tim:** And now, they're interested or they're like, oh, we can't wait for that. all right, this is a legitimate idea or three, they'll be like, we have no idea why you're working on that. Who's gonna use that. And so that feedback is invaluable

[00:52:12] **Tim:** because otherwise, if everyone is like, okay, that's nice.

[00:52:16] **Tim:** You might go ahead and build all these things. And eh, it doesn't really increase revenue or increase performance or increase happiness at all. So I think it's a good tool. And that's why it has to be dynamic. if people are like, no, we hate that idea. Or they're like, we don't care about that idea.

[00:52:34] **Tim:** You, you take it off or you move it further down the road and put something else that, that they're more interested in.

[00:52:39] **Carol:** And we like to take the information given back. We're like, okay, it sounds like you probably want this, so we're gonna pilot it. So like, we are going to develop this very slim version of what we think could be the product. And we're gonna just open this up in Idaho or in Florida because everybody loves Florida.

[00:52:58] **Carol:** Right. So we're gonna open this up in Florida. And then if Florida and Idaho give us back great results, then we're gonna actually invest the time to full market this and then open it up to the company. So I think first, like you said, you get the buyback from the people who are using your system, who are your market, who are the people who know what's going on in it.

[00:53:16] **Carol:** And then you're like, okay, sounds like it's doable. And then either you decide to do it or. Create a very slim version of it and create a pilot and see how it goes and then grow it.

[00:53:28] **Tim:** That's cool. That's a good idea.

[00:53:30] **Tim:** No, you guys are giving me fantastic feedback. This is great.

[00:53:33] **Ben:** this is mostly unrelated, but some, sometimes I think about it work. we, people on the product side of the house, I feel like sometimes have, I wanna call it a strange a version to just doing things for our most high money clients, like, I, I probably can, you know, likeAcme corporation, let's say theoretically Acme corporation has a 2 million a year contract

[00:54:00] **Ben:** and their admin comes and says, Hey, it'd be really great.

[00:54:04] **Ben:** If I could hit a button and generate a report. For something that no one else will need. and the product people look at that and go like, oh, well, that's not really generally applicable. I don't think that'll help anyone. And I look at that conversation. I'm like, that's a $2 million year contract. I don't care if it helps anyone else.

[00:54:19] **Ben:** Like, I feel like it would be cost effective to literally dedicate an engineer full time to them and just build them whatever they want, because there's no way we're paying an engineer 2 million a year.

[00:54:31] **Ben:** So like,

[00:54:31] **Ben:** why not just throw resources at it?

[00:54:34] **Carol:** sometimes they make terrible decisions and back themselves in the holes that you have to support for years down the road. So

[00:54:42] **Tim:** she,she talks in a place of

[00:54:44] **Carol:** that might not be the best idea. Like sometimes you do need the expertise of everyone using the system to understand that what they're requesting is dumb.

[00:54:53] **Carol:** Like you don't want to use the system that way. Like, do you understand like how

[00:54:58] **Carol:** you're trying to achieve this is not smart. Let me show you how to achieve it

[00:55:03] **Carol:** correctly. And then if it doesn't work for you, let's talk about why this doesn't work for you. Instead you assign an engineer to it and they're like, okay, I've been told to do everything you say to do.

[00:55:14] **Carol:** So I'm just your yes, man. And now I am introducing problem after problem, because

[00:55:20] **Tim:** You triggered her, you

[00:55:21] **Carol:** meant to be used.

[00:55:24] **Carol:** Bad idea. This is a bad

[00:55:25] **Carol:** idea.

[00:55:26] **Tim:** and that's why you don't let your customers be your product

[00:55:29] **Carol:** You do not. There needs to be a very clear like line between the two because otherwise bad things happen.

[00:55:36] **Ben:** I totally get that. I totally get that. I think it's easy to go hard in the other direction where you basically don't treat your special customers special. I mean, frankly, I mean, it depends on the type of industry you're in, but we definitely have special customers that,their vote is like a thousand times more important than a lot of other people's votes, voting with

[00:55:58] **Tim:** and you know, your,

[00:55:59] **Tim:** your competitors are going after them

[00:56:01] **Tim:** first. Right? Your competitors are going after big guys, not the little

[00:56:03] **Ben:** yeah. And like sometimes yeah, you just wanna make them happy and, to Carol's point, and I totally agree with this. If they're asking for stuff that is gonna be hard to maintain or it's gonna cause problems like, yeah, you can have a conversation, but a lot of times people want something that you can really build in a fairly isolated way.

[00:56:20] **Ben:** And you could even with cough feature flags, cough,uh, you know, only turn it on for them.

[00:56:26] **Carol:** them.

[00:56:27] **Ben:** And you're like, let's just do it. Let's like not even have a conversation about it. Let's just make it happen for them. It's gonna make them really happy and maybe it'll help them with a contract.

[00:56:37] **Carol:** Like, as you're saying that, I'm thinking about how many places through the code base we have right now, where it says, if this customer this way else, everyone else. Right. Because we're like, okay, you are a big fish, so yeah. You get some custom logic in here. So I get it does happen. And you do what you can to try to keep your big customers happy and, coming back,

[00:57:00] **Carol:** but don't dedicate an engineer to them. Okay.

[00:57:02] **Tim:** Yeah.

[00:57:04] **Tim:** Yeah. I've,I've heard of companies where, they just kind of say, Hey, here's a bunch of developers. Do whatever you want with them. And then you think that makes them happy. And it does for a little while. And then years later, they're not happy because they ask for a lot of things that were kind of really, yeah,

[00:57:18] **Tim:** I've seen it. So you

[00:57:20] **Tim:** gotta have a, you gotta have a product team making sure the product has to

[00:57:23] **Tim:** come

[00:57:23] **Carol:** the products first.

[00:57:24] **Ben:** But it is interesting because. Big customers. And a lot of companies can have special support contracts where they get either dedicated support personnel or, they get phone support or something that not everyone else gets because they've paid for it. So it is interesting. Clearly we treat them special in some ways, and it does feel like there's, I think it would be great to have a little bit more wiggle room sometimes and treating them in more technical ways as well.

[00:57:47] **Ben:** But

[00:57:48] **Tim:** right.

[00:57:48] **Ben:** I'm off my soapbox.

[00:57:51] **Tim:** right. So I mean, as far as roadmaps, that's kind of really what we have so far. I don't, we didn't cover all of it, but I mean, one thing since here I totally agree with is when it comes to the external view is a high level roadmap. Can't be used to pin you down on a specific pointer feature and you have to make that clear when you present it to your customers.

[00:58:12] **Tim:** It's like, this is a roadmap.

[00:58:14] **Tim:** And as you know,

[00:58:15] **Tim:** sometimes there's detours, it's a plan, right? So, we're, this is what we're working toward. This is what our resources going toward until,we need to make a change and We'll let you know, the most important thing is to communicate when you make that change, don't do it in silent.

[00:58:28] **Tim:** And then like, it's six months later and like, Hey, you said so, and so will be, oh yeah, we changed your mind. We're doing this well. That makes it look like you didn't communicate with them. Then it makes it look like you. You're not trustworthy.

[00:58:41] **Tim:** And that's

[00:58:43] **Ben:** All you gotta do is put all dates, subject to change piece of cake.

[00:58:47] **Carol:** No questions. Ask

## [00:58:51] Patreon

[00:58:51] **Adam:** All right. That seems like a good place to stop. So this episode of Working Code is brought to you by doing literally anything that a high paying customer wants. That's a surefire path of keeping them happy and those contract renewals

[00:59:01] **Adam:** coming in and listeners like you, sorry, Carol. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:59:14] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them special. Thanks to our top patrons, Monte Gavin and Sean, you guys rock. if you'd like to

[00:59:23] **Adam:** join our, our patron squad, you can, go to patreon.com/WorkingCodePod. all of our patrons get early access to new episodes and our after show tonight on the after show, they're still typing in the document.

[00:59:35] **Adam:** So I gotta. Decipher as they type, it looks like, we're gonna discuss is Ben's MacBook pro a $3,000 paperweight. why are teenagers not wanting to learn how to drive and, flying down to support a high paying customer in a hurricane? that sounds like it's gonna be a good one.

## [00:59:49] Thanks For Listening!

[00:59:49] **Adam:** so your homework this week, you know what, based on this discussion, I just have to feel there's gonna be a whole bunch of people listening that wish they could have been part of this discussion that could have given us advice or, shot down some of the things that we said, if you're one of those people, the place that you want to go is to our Discord.

[01:00:06] **Adam:** You go to workingcode.dev/discord. It's a chat it's just like slack or anything else. You can join our Discord and, discuss all of those things and more with, not only with us, but with the rest of the podcast, listening community out there. So

[01:00:21] **Tim:** They're they're a chatty bunch.

[01:00:22] **Adam:** Oh yeah, it's a great place to

[01:00:23] **Adam:** hang out.

[01:00:24] **Carol:** keep up.

[01:00:24] **Adam:** So, let's see, send us your topics and questions. If you got those, you can find us, @WorkingCodePod on Twitter or Instagram. Like I mentioned, our Discord. That's a great place to bring 'em to us. You can email them to us at WorkingCodePod@gmail.com. or you can send us a voice memo to WorkingCodePod@gmail.com.

[01:00:41] **Adam:** That's another great idea. we have one I meant cush, uh, this week. We forgot again, Gavin. I know. I'm sorry. it's totally my fault. I keep forgetting to bring it up when we have our quick catch up discussion before we start recording. we will, so Gavin sent this nice, voice memo. We will, I'm committing, we'll play it next week.

[01:01:02] **Adam:** I hope

[01:01:04] **Tim:** put it in our notes.

[01:01:05] **Adam:** right. Okay. So that's gonna do it for us this week. We'll catch you next week. And until then

[01:01:10] **Tim:** Remember your heart matters. And our patrons even more.

[01:01:14] **Carol:** That guys
