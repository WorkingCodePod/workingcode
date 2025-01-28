---
title: "033: Software Patents"
description: "This week, the crew - which has absolutely no legal training whatsoever - talk about patents, copyrights, research & development tax credits, building software, job hopping, and best practices."
date: 2021-07-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/033-software-patents/id1544142288?i=1000530270872"></iframe>

Do you write "new and original" code that is "useful" and has a "non-obvious function"? If so, your code may qualify for a patent. A patent can help prevent other people from using or selling your software. That said, which engineer among us isn't write _new and original_ code every day? Software patents are weird and fuzzy and open for way too much interpretation. And, in the software industry, they seem to give "patent trolls" a lot of unpleasant leverage.

This week, the crew - **which has absolutely no legal training whatsoever** - talk about patents, copyrights, research & development tax credits, building software, job hopping, and best practices. And, if you don't care at all about software patents, level-up your view of the world with this quote from Adam:

> People don't burn-out from too much work, they burn-out from too much unfulfilling work.

## Notes & Links

- [Software Patent or Copyright: Everything You Need to Know](https://www.upcounsel.com/software-patent-or-copyright)
- [Legal Notes: What’s the Deal with ReactJS’s Licensing Scheme?](https://www.codemag.com/article/1701041/Legal-Notes-What%E2%80%99s-the-Deal-with-ReactJS%E2%80%99s-Licensing-Scheme)
- [How to Qualify for R&D Tax Credits: The Four-Part Test](https://taxpointadvisors.com/blog/view/how-to-qualify-for-rd-tax-credits-the-four-part-test)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/033-software-patents.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Usually a patent troll is a person or company that buys patents and then goes around and looks for people that are infringing on that patent. And so they might look before they buy, so they know what to buy, but they find people that are infringing on a patent that they own. And then they basically extort you.

[00:00:14] **Adam:** They say, give me a certain amount of money as a licensing fee, or I'm gonna take you to court and I'm going to ruin your business sort of thing.

[00:00:21] **Ben:** It's like ransomware.

[00:00:23] **Tim:** Yeah.

[00:00:24] **Adam:** professional ransomware

[00:00:25] **Ben:** Okay.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 33 and on today's show, we're going to discuss software patents. And maybe also if time allows software engineering unions, who knows, we'll see, maybe we will, maybe we won't, but as usual, we're going to start with our triumphs and fails and it looks like Carol, it's your turn to go first.

[00:00:57] **Adam:** What's the bird update.

## [00:00:59] Carol's Failure

[00:00:59] **Carol:** Well, yeah. So, so have three eggs. They seem to be doing good. Does anyone know how long it takes for eggs to hatch? Cause I feel like they've been in there a very long

[00:01:07] **Adam:** a very long time.

[00:01:10] **Carol:** I mean, at least like four weeks.

[00:01:11] **Adam:** Hmm.

[00:01:12] **Tim:** hot here. Maybe they're cooks now.

[00:01:15] **Carol:** Oh, I'm to go crack one open. Okay. I'm not really going to do that, guys. We're not going to crack an egg open. We're going to wait. Yeah. But for my triumph failure, I'm going to go with a failure. I am currently in the middle of an, a single way for a lack of better word, a hell hole. I have no idea what I have done.

[00:01:38] **Carol:** Everything is going perfect and working so smoothly. And then I found there's this error that happens sometimes with Gmail. If it can't find a label to remove off a message and it's doing that because the message has been deleted. So in the midst of me trying to label these messages, the user is actually removing the message while I am mid trying to work on it.

[00:02:03] **Carol:** So, g-mail actually returns back in air, which is fine. I'm handling it. But I was trying to make a very small tweak to how the labels work and for whatever reason, when I make this adjustment inside this await process. It all bombs out and everything stops. So I've spent a couple hours today trying to figure out where my await is failing.

[00:02:26] **Carol:** And it's just not fun right now. So I've cried a little bit this afternoon. Cause it works fine until it doesn't and I'm like, I know it should be waiting. I want to wait right here. Just finish. But then it's onto the next one. I'm like, oh,

[00:02:41] **Adam:** you're not doing it with RA promises. Async await is so much better.

[00:02:45] **Ben:** So much better.

[00:02:46] **Carol:** it's so much. I mean, it's the right way to go, but I'm just like, what , why, why, why, why? Like my neck itching. I'm like

[00:02:54] **Tim:** to troubleshoot. That's the

[00:02:56] **Carol:** Yeah. It's and I almost want to kind of just ignore it and just let it throw the air and let it do the retry and AWS side because when it picks back up, everything's good to go.

[00:03:06] **Carol:** But I'm like, man, I really want this right too. So I can't just walk away

[00:03:09] **Adam:** Yeah, sleep on it. Maybe you'll get the idea in the shower tomorrow morning or something.

[00:03:14] **Carol:** yeah, hopefully he'll.

[00:03:16] **Adam:** Well, before we, that, I mean, this is important. I Googled it.

[00:03:20] **Adam:** Bird eggs,

[00:03:23] **Adam:** uh, take obviously it varies a little bit between species, but the range I'm seeing is somewhere between like 13 and 35 days. So they could be close.

[00:03:33] **Carol:** oh. They should be close then I haven't seen the mama bird in a while, so

[00:03:40] **Ben:** Yeah,

[00:03:40] **Carol:** a good thing, but it's so hot. I'm wondering if she's even needed.

[00:03:43] **Adam:** Yeah.

[00:03:43] **Tim:** watch.

[00:03:45] **Carol:** Well, other than the feed them, but it's not like she has to sit on the eggs. It's a hundred degrees here, so. All right. We'll see. We'll see. Yeah. You bend your neck.

## [00:03:56] Ben's Triumph

[00:03:56] **Ben:** I'd go with the triumph this week. I , uh, have been sitting on this idea for a small feature inside of our application and for one reason or another, I haven't built. And then two weeks ago, I finally got fed up with not building it and started to put together an MVP and a it's kind of inspired by if anyone uses sublime text.

[00:04:19] **Ben:** I'm sure other IDs have this concept of a command palette kind of, kind of like spotlight on the Mac where there's a key combination that pops up a search and that search then allows you to access various types of things, whether it's entities within the application or actions or locations.

[00:04:36] **Adam:** guys, actually, in some browsers.

[00:04:37] **Tim:** Huh?

[00:04:38] **Ben:** yeah, yeah, yeah.

[00:04:39] **Ben:** It's a really cool concept. And so I put together an MVP and deployed into our application, but it's only discoverable it's based on a key command, but it's not like we have a help page for key commands. And it's only discoverable in this one UI that L that illustrates the key command. So I've got analytics about when it gets opened and whether or not people select options.

[00:05:02] **Ben:** So now I have an amplitude dashboard. Feverishly watching every day to see if anyone happens to stumble upon this feature and uses it. And , uh,

[00:05:11] **Carol:** Are you wanting them

[00:05:12] **Ben:** yeah, yeah, yeah, absolutely. So,

[00:05:15] **Adam:** they.

[00:05:16] **Ben:** yeah, slowly, but, you know, it's , um, I walk a fine line between getting in trouble at work and providing value for my users. So, so I feel like quietly, I do something the less trouble I get into, but I might also then make some users day if they stumble upon this and it, delights them.

[00:05:38] **Tim:** You talked about Amplitude dashboard. What is that?

[00:05:42] **Ben:** Amplitude is a, I don't know. I don't know if it's a analytics or if it's a metrics, I don't know what the right word would be, but essentially the way our application works is we post metrics to segment IO. And then my understanding is that segment. Turns around and post those same metrics to end number of services.

[00:06:02] **Ben:** I think it's sort of like a, if this, then that style thing, but for metrics. So one of the integrations that we have is amplitudes so segment then post those metrics to amplitude and I can create dashboards that showed demographic breakdowns and funnels. I don't actually know how to use it that well, I just, I basically have bar charts.

[00:06:23] **Ben:** I'm at the bar chart level of skill.

[00:06:27] **Carol:** Is it like the

[00:06:28] **Ben:** Yeah, yeah, yeah,

[00:06:28] **Carol:** You're like, yes. Don't change anything.

[00:06:30] **Ben:** like you create a new dashboard, you add an event and it's like immediately a bar chart for you.

[00:06:35] **Carol:** Yeah.

[00:06:37] **Ben:** So that's where I am, but , uh, yeah. Yeah. It's just fun to see something being used. And there is something very magical about watching real-time analytics, because it's like the volume of people doesn't even matter.

[00:06:51] **Ben:** You're like one person discovers that and you're like, oh

[00:06:54] **Adam:** Hmm.

[00:06:55] **Ben:** my people. So,

[00:06:59] **Carol:** Been

[00:06:59] **Ben:** It's good times. Adam, what about you? What do you have going on this week?

## [00:07:04] Adam's Triumph

[00:07:04] **Adam:** I have a very clear triumph this week. I just got back from a week pretty much entirely offline away from internet connection and cell phone signal.

[00:07:13] **Ben:** What is this offline?

[00:07:15] **Carol:** moly.

[00:07:15] **Adam:** Yeah, my family, we went camping for a week. And we just go to state parks. It's nothing like crazy. We're not like backpacking the Appalachian trail or something, but and you know, some places you go, you have cell signal, some you don't.

[00:07:26] **Adam:** And my children are like most children, these days completely screen addicted. I'm not a beyond reproach on that myself. And so, we had preparations, right? I made sure we had podcasts on the kids devices for them to listen to while on the road and a couple of audio books. And I had a bunch of books on my phone ready to go.

[00:07:47] **Adam:** And I had downloaded some video stuff on my tablet, just in case we get reined in or something. And, we survived, I spent a week in a box with my family and we came out with the same number of people we went in with. And that's a triumph, nobody's to Barre.

[00:08:04] **Carol:** Do you guys fish or any.

[00:08:05] **Adam:** We do occasionally fish, but we didn't on this trip. So this one of the places we went this trip was to Ohio pile, state park it's outside of Pittsburgh. And one of the neat features there, and one of the big draws is they have what they call natural water, the slides. So if you imagine a river running down the side of a mountain, it's not too steep, but it's not too shallow.

[00:08:26] **Adam:** And it's got just the right kind of rock that the water can wear it away. And it basically carves out a Waterslide that you can ride down. And there's like pools every once in a while so that you can like take breaks and there's different slides sort of thing. It's really neat. And the water levels has to be just right for you to be able to go if it's too, if the water level is too high, if there was a storm come through or something, then the water just kind of is rushing and it looks a little dangerous and you don't want to go in, but if it's too low, then you can't get going fast enough to actually see.

[00:08:57] **Carol:** You just stick.

[00:08:58] **Adam:** went actually five years ago. I think it was. And the water level, like a storm blew through when we were driving in and it was just crazy. We couldn't get, we were really disappointed. And this year, luckily we went back and it was very rideable and we had a ton of fun. We went there every day that we were in the park.

[00:09:15] **Adam:** It's actually I mean, while we're talking about it, it's real close to the Frank Lloyd Wright, famous falling water house. I'm sure you've seen pictures of this place. And so, yeah, we went and visited that and all kinds of fun stuff and we only have, he had enough cell phone signal, like driving between campgrounds.

[00:09:34] **Adam:** We moved once during the week. So let get to GPS to get us to the next place. And it's like, okay, you're in a cell phone, black hole again. So

[00:09:43] **Carol:** Holy, I can't imagine that, like I'm never detached more than like a few

[00:09:48] **Adam:** it's tough, you get the.

[00:09:49] **Ben:** Yeah.

[00:09:50] **Carol:** Yeah.

[00:09:51] **Adam:** And eventually you get through it, but

[00:09:54] **Ben:** you have one of those backpacks that has a solar panel on the top? So you can recharge your podcast device.

[00:10:00] **Adam:** I don't we have a small pop-up camper and so it has some outlets in it and we try whenever possible to get a campsite that has electric for

[00:10:09] **Ben:** Nice.

[00:10:10] **Adam:** And so I can like recharge my phone every night sort of thing.

[00:10:13] **Carol:** Do you have a generator or something you take when there's no

[00:10:16] **Adam:** The camper has a battery, just like a car battery. And so when it's on battery, the outlets don't work, but like the water pump and the lights in the ceiling word, that's it.

[00:10:28] **Ben:** I remember I was, I went to this presentation one time and this guy was talking about how he had made some decision at his company. And I think he was the CTO and they made some huge decision that they were going to roll out some new piece of software. And then he went on vacation day of, and he was in one of these situations where he was literally out of cell phone range, like he was in a canyon or something.

[00:10:50] **Ben:** And he came out five days later. And I think he said he had something like 1300 voicemails on his phone from all the people that were freaking out about. I think that the system had gone completely down

[00:11:00] **Adam:** right?

[00:11:01] **Ben:** and it was like offline for days. And they were trying to figure out how to get things from backups and they couldn't find data nightmare.

[00:11:08] **Adam:** no, I came back from this vacation with several things that I had, like completed and left, when I left, I, know, we left on Friday. So when my last day was Thursday and there was several projects that I completed at the end of that week.

[00:11:19] **Adam:** And then we just agreed. They're going to sit on the shelf until I get back, because I'm not gonna put anybody else through that.

[00:11:25] **Carol:** don't touch it.

[00:11:26] **Adam:** So,

[00:11:27] **Ben:** Okay.

[00:11:28] **Adam:** well, that's me. So that leaves you, Tim. You've had some time.

## [00:11:31] Tim's Failure

[00:11:31] **Tim:** We'll go with the fail just cause I'm just terribly unmotivated this week and this we're recording on Tuesday. Normally we record on Thursday, but just as Monday and Tuesday, I've just got no drive. I mean, I'm doing stuff, but it's like, I don't know. I gotta get my fire back. So just trying to.

[00:11:50] **Tim:** Force myself to focus and to apply myself and, go get to inbox zero and all that stuff every day. But Yeah.

[00:11:56] **Tim:** it's just like, if there's some, I normally, when I run out of stuff, I'm just very quick to pick something else up that I got on the back burner. And now it's like, I'm done with that. I'm just going, I gotta sit here for 10 minutes. So it ebbs and flows, so I'm sure I'll be fine.

[00:12:14] **Carol:** Yeah. We said today in slack. We're like, man, this Tuesday just feels like Monday part too.

[00:12:21] **Ben:** No.

[00:12:22] **Carol:** Like it's just a long week already.

[00:12:25] **Tim:** And then the last week I took off for I have some, a rental property in our old house that we used to live in a tree, fell on it and had to go up there and check it. That was just

[00:12:34] **Ben:** Oh, Jesus.

[00:12:36] **Tim:** I don't want to deal with.

[00:12:37] **Carol:** Oh

[00:12:37] **Ben:** That sucks. Sorry to hear that.

[00:12:39] **Tim:** So.

[00:12:40] **Carol:** Yeah.

[00:12:40] **Adam:** Well, it sounds a little bit like burnout, and if you need a good podcast episode on burnout,

[00:12:46] **Tim:** Is that good podcast for that?

[00:12:47] **Adam:** can, can, recommend something. Actually. Uh, I saw a quote this week that I really liked about burnout. It was people don't burn out from too much work. They burn out from too much unfulfilling work.

[00:12:59] **Tim:** Hmm.

[00:12:59] **Adam:** So I think, find something to work on that you're like in love with, and maybe that'll help reset. Yeah.

[00:13:07] **Tim:** Good plan.

## [00:13:09] What is a Patent

[00:13:09] **Adam:** Cool. Well, I guess let's talk about software patents. Does anybody have any particular place you want to start? I have one. So I thought before we jump into software patents, it makes sense to kind of just cover real quick. What is a patent? Do any of you guys know

[00:13:26] **Tim:** Yeah.

[00:13:27] **Carol:** So how does a patent differ from a copyright.

[00:13:29] **Adam:** question. A copyright protects you as the owner of something you created race. It's something you wrote a piece of art you created or whatever, and nobody else can claim ownership of it, right? You can't plagiarize the book that I wrote or something like that. And try to profit off of that.

[00:13:48] **Adam:** A patent is a way of granting exclusionary rights. So it gives me if I'm a pharmaceutical company and I develop a new drug to, to treat some disease.

[00:14:02] **Tim:** Okay.

[00:14:03] **Adam:** Only I can use that formula to create the drug for this purpose or whatever. And so even if you could reverse engineer, like if you went and bought some of the pills that I create and you break them up and you figure out what's in them, even if you can figure out what the formula is, you are not allowed to make that drug and sell it.

[00:14:23] **Adam:** Because I have the patent on it. So basically it's an incentive to encourage people to do research and development on hard problems. Right? Like, so these drugs that we need for various diseases, that sort of thing. And inventions in general.

[00:14:38] **Tim:** yep. And I, we probably shouldn't say at the top of this, that none of us are lawyers and none of this is legal advice. So

[00:14:44] **Adam:** Absolutely.

[00:14:45] **Tim:** everything we say, take with a huge grain of salt and talk to your patent attorney, because I think that's the biggest thing is you're going to have to have a patent attorney at some point involved in this.

[00:14:56] **Tim:** Cause it's a very complicated process.

[00:14:59] **Adam:** I mean, I'm coming at this from a very outside in perspective. I have zero patents to my name, although I can say, I know some people that have patents, my father-in-law has I think a couple of dozen patents. He's not a mechanical engineer. He's an engineer of some sort. And he works on a really interesting equipment that does like chemical analysis, like a mass spectrograph sort of thing.

[00:15:22] **Adam:** And basically his company comes to him and he's like, okay, look, this is what we need to do. We need to determine the number of certain types of particles in this compound or whatever. We need a machine that does that, but these are the constraints you have to work in this condition. And so he finds a way to solve that problem and then they can pass it.

[00:15:39] **Ben:** Talking about drugs. So drugs in a way are an interesting parallel with code because drugs are composed of lower level molecular structures, right? But you can't patent hydrogen. You can't patent oxygen, you can't patent nitrogen, but you can patent some complex formulation of, 16 carbons. 12 hydrogens.

[00:16:02] **Ben:** And I don't know anything about molecular biology or anything like that, but, or chemistry but you have to get to some certain level of complexity. I think before you can say, like, this is a thing that's patentable and code, I feel must have to deal with those same type of constraints because you can't patent an if statement, right.

[00:16:23] **Ben:** Everybody has this statement. So, so what, how do you compose code to the point where you can look at something and say, this is so uniquely ours, that if anyone were even to like randomly put this collection of syntax tokens together, it would be a violation.

[00:16:40] **Carol:** So, what I had read was, and I posted the link over to like this page. I was reading earlier when we were talking about this topic, but it basically says that it has to be new and original. The code has to be useful and it has to have a non-obvious piece of code or function to it. So it can't be anything that would be an obvious statement to it.

[00:17:04] **Adam:** I mean, I think it, it kinda goes back to it's an incentive, right? If you can come up with an idea that is not civil enough and useful, then you can get it patented. And that gives you not only the right to be the sole creator of it in the court. Example of medicine, but like you can sell a license to it.

[00:17:28] **Adam:** Right. So, Coke. Doesn't sell the doesn't license, the formula for Coca-Cola. But I think that there are like medicine licenses, if I'm not mistaken, I'm not doctor medical license, but you know what I mean? Like, so you can license the rights to use a formulation to create a medicine sort of thing.

[00:17:51] **Adam:** And so you can profit off of it that way as well. And I think that we've probably covered enough ground here in general. Patents got the idea across, I think that the idea of software patents is interesting to me because I like the idea of there being an incentive to, solve hard problems, do complex things, be useful, be novel.

[00:18:14] **Adam:** And not everybody has the same type of motivation and personality as me, but you know, me personally, I'm I have never once thought, oh, that's an interesting thing I just did. I should see if that's patentable or not. that's just, I create stuff because it's fun and because it needs to be created not necessarily to profit.

[00:18:33] **Carol:** Yeah.

[00:18:35] **Tim:** Yeah.

[00:18:35] **Tim:** I mean, in software, patents particularly are very true. because I kind of the things that Ben was talking about that the, a lot of it is kind of a gray area. Like you can't patent an abstract idea, but that's not always clear what that is. And it's not about the code codes to language, right?

[00:18:56] **Tim:** It's about the process, the design of what you're doing more so than the actual code. And one of the things that I was reading about this is the law requires it needs to pass like the machine or transformation test. so the machine basically means the code has to be tied to to a machine or it has to be a process that turns one thing into another.

[00:19:17] **Tim:** And that process is what's patentable, not necessarily the code that's doing it. I mean, one example of that is the Amazon one-click patent. I don't know if you ever used that on Amazon where you can

[00:19:31] **Adam:** now with one click.

[00:19:32] **Tim:** yeah.

[00:19:32] **Tim:** So it's taking. Yeah,

[00:19:34] **Tim:** It's that process of just having to, you put something in your cart and you one click. and you purchase right.

[00:19:41] **Tim:** Everything. You don't have to go through a bunch of steps and they patent that. Right. So no one for, I forget how long patents last

[00:19:47] **Adam:** Usually it's 20 years,

[00:19:48] **Adam:** but

[00:19:49] **Tim:** So it, until they're their patent wears off, they're really the only one who can do technically do that on our site.

[00:19:57] **Adam:** Hmm.

[00:19:57] **Tim:** So, but

[00:19:59] **Adam:** Yeah. I mean, there are other things that stand out to me is like, obviously this is a patentable idea. And I think that if I'm not mistaken, some types of patents can be granted without a working example, like a reference implementation, but some can't. So like in the world of software, a self-driving car, right?

[00:20:22] **Adam:** Like when they finally get that to be I don't know, there's different, like ways they grade it, like level one or whatever they call it where it's actually fully functional self-driving car. I'm sure they're going to patent that. Or they're going to try yeah, like you said, where's the line and I don't think that it's clear and that's the job of the people that work in the patent office, I guess, is to determine, is there prior art for this and is this submission, does application actually new and novel and useful and everything?

[00:20:59] **Ben:** Do you think you can patent algorithms? Like in a previous episode, we talked about password hashing algorithms like B crypt and eScript and argon too, which as far as I know, at least are licensed so that anyone can use them. But I wonder

[00:21:15] **Adam:** right. Well,

[00:21:16] **Ben:** like, Hey, this is a very novel approach to creating secure hash.

[00:21:21] **Adam:** So, obviously I'm not an expert, but I'm almost certain, there are very few software patents, which is amazing to me because like I did a little bit of reading before we came into this episode. And from what I saw, there's very few software patents, but I mean, when I think of software patents and the idea of patent trolls, like the first thing that comes to mind is like, hasn't Google been fighting Oracle for like the last lifetime over stuff in Java.

[00:21:51] **Adam:** And I guess Android overlap or something, I'm not sure. That's just like, ever since Slashdot was like my homepage in my browser, in I E for, this battle has been in the courts. So, and, there was, I dunno how much truth there is to it, but like apple tried to patent the rounded rectangle.

[00:22:11] **Ben:** no.

[00:22:12] **Adam:** Really, but yeah.

[00:22:16] **Tim:** Okay.

[00:22:17] **Ben:** tricky too, because if you think about the way the industry works in general, we had mentioned this on a previous episode that I've heard that the average tenure for an engineer at a company is about two years, industry-wide so you have people who hop from company to company, to company, and they're bringing ideas with them as they go. is the code that someone's writing today, a violation of something that they brought previously because of looks very similar or is this just the best practice of building this type of thing that they've established in their mind? I mean, because programming is so much this, non-tangible art it's, I don't know where I'm going with that thought, other than just to say.

[00:23:07] **Ben:** It feels like so much of it can be and not necessarily a violation.

[00:23:14] **Carol:** Yeah. Where is the boundary between like intellectual property and just patterns of how we run? So, what is that piece that separates me from disclosing intellectual property from another job versus this is just how you write this function. Every time I write it, this is how I create my methods. This is just my way of coding.

[00:23:34] **Carol:** That isn't part of that. It's just what I do.

[00:23:39] **Ben:** And on top of that, I mean, going back to what Adam was saying about this system of incentives I'm hard pressed to find an example, but I know that I've heard things on the radio where they talk about how there'll be some technical hurdle that then allows for further innovations to happen. and what will end up happening is something new will be created in an industry.

[00:24:00] **Ben:** A whole bunch of people in parallel will come up with very similar ideas because now some kind of general idea has been unlocked. and I feel like they were talking about even the light bulb that when the light bulb was invented, something like, like a whole bunch of people actually tried to file patents for very light bulb, like devices, like, almost at the same point in time. So when you think about these incentives, it's not like one person got the patent on light bulbs, but it's not like they were the only people doing that research and building that technology. They just happened to be the first one to one, get their application in and to get that application approved, probably by some combination, if they got the right clerk and the, and that clerk happened to think this was novel enough.

[00:24:44] **Ben:** So it's tough.

[00:24:45] **Tim:** Okay.

[00:24:45] **Ben:** I don't know. it's all very fuzzy.

[00:24:48] **Adam:** Yeah. It's very much a lawyer game. Right? So if you look at a typical patent application, it's a, it is very much a, an attempt to grab as much land as possible and claim it as your own, right? So you make an invention and every patent application, you have to describe what the invention is. And when the lawyers write up the paperwork, they start with, okay, the universe exists.

[00:25:13] **Adam:** there's an earth sort of, they start from the Y broadest possible thing and they try to claim as much of that as possible. Right. So like, I don't know, whatever we started with a switch statement and then this and that. And that way. However much of that gets granted as part of that patent.

[00:25:31] **Adam:** Even if it's not necessarily a novel portion, if it's the first time the patent office has like recognized it, noticed it, whatever, then you can sort of claim that as part of your patent. And then if you choose to enforce it, you can go around and be a jerk and not let people use switch statements or whatever it is like. Don't give Adam Cameron any ideas.

[00:25:54] **Ben:** Yeah.

[00:25:55] **Carol:** Okay.

[00:25:56] **Tim:** Yeah, I'm kind of ambivalent, I think software patents are too vague and I think they probably do more harm than they do. Good. Because the people at the patent office, they're not going to fully understand the use case that you're putting forward there and they, if they accidentally do something too broad, well now, like you said, that person has a whole lot of power to go through and wreck other people.

[00:26:19] **Tim:** and then to, anytime you try to create something, having to do this exhaustive search, make sure you're not infringing. That's just it's kinda dead. I mean, it made a great, it was great back when I was just mechanical things. And you could do a mechanical diagram. That was, that's very clear and easy to see this it's unambiguous.

[00:26:35] **Tim:** what a mechanical thing does, but software can be very ambiguous. And I mean, I've filed for, to our company that every year they say, Hey, what have you done? That's interesting and unique. That could be patentable. And they beat you up over it. If you don't give anything. So it's like, we put stuff down.

[00:26:51] **Tim:** It's like they never get accepted. But Yeah.

[00:26:55] **Tim:** it could, because at the end of the day, it's like, well, what you're doing is just, it's kind of, it's a known thing. it's not really that unique.

[00:27:02] **Adam:** So you've had two patent applications rejected. Is that.

[00:27:06] **Tim:** Yep. And they never got past legal, so they never even filed them.

[00:27:11] **Adam:** even an application.

[00:27:13] **Carol:** Look, we're not going to tell anyone we're doing this already,

## [00:27:16] Why have a Patent?

[00:27:16] **Ben:** Well, going back to the thing Adam mentioned about Google versus Oracle, and it almost feels like a lot of the value of a patent is defensive more than it is. Offensive Mike, you want to patent something almost so that no one else can then later come and say, Hey, we patented it. And now you're infringing on our patent.

[00:27:35] **Adam:** Yep.

[00:27:36] **Tim:** Yeah.

[00:27:37] **Carol:** Yeah. Like I want to have it first so I can keep

[00:27:39] **Adam:** And then there are also I'm trying to remember the details here. So I know there was, there's this whole kerfuffle about the license that react JS was released under if here, recall that it was maybe about a year or two ago. and the language in license, basically it was frequently interpreted as.

[00:28:01] **Adam:** your application that you write with this code becomes part of Facebook's like property, right. And obviously nobody is going to do that, but that was how people were choosing to interpret the license. And I think that what was intended in that language was an agreement that basically if you have patents and we have patents and we see that we're both infringing on each other's patents, we can just have a net even score, right?

[00:28:30] **Adam:** Like, just like, okay, well, we'll forget our stuff that you're infringing on. You forget your stuff that that I'm infringing on. And that way it kind of becomes a level playing field or something. the whole thing the legalees, all of it is super confusing. You definitely need a lawyer if you're going to get involved in that sort of thing.

[00:28:44] **Tim:** Yeah.

[00:28:44] **Tim:** we wouldn't be doing it if we didn't have a huge legal department in our corporate structure.

[00:28:50] **Adam:** Yeah. And I think that is a big part of why I'm just totally turned off by the idea, like what I like to have a patent on something, whether or not it's truly useful and beneficial and unique and novel. What I like to have a patent on something and, have people pay me a license fee to use it?

[00:29:09] **Adam:** Sure. Why not? but that's a lot of work and a lot of like legal, garbage to go through where I can just like have fun and write open source code and release it for free to the world. Like who cares? that's where that to me is the more interesting way to spend my time.

[00:29:26] **Carol:** I was trying to read through an article real quick while you were talking about the react licensing controversy and everything. And I'm like three fourths away just like threw it, like not really reading it, just picking out keywords. Right. And it's, as if you're confused by the language so far, you should be, I'm like good.

[00:29:46] **Carol:** Because so far, none of this has made sense. So I'm like, all right, good. I'm glad I'm not the only one that doesn't fully understand it.

[00:29:54] **Ben:** documents in general are just completely up to us. It, this is so hard.

[00:30:01] **Carol:** So many extra words in there.

[00:30:04] **Adam:** no offense to any of my lawyer friends, but I think it's a little bit of a case of like, they do that on purpose so that they are needed, right? Like legalees exists so that lawyers are necessary. in not, that's not the only reason, it's useful to be able to be 110% explicitly clear on what the agreement is in a contract or whatever, but still

[00:30:32] **Ben:** But I feel like you can be clear without a lot of the language that they use.

[00:30:37] **Carol:** Yeah, agree.

[00:30:40] **Adam:** pros and cons lawyers.

[00:30:42] **Tim:** Okay.

## [00:30:44] Patent Trolls

[00:30:44] **Adam:** Okay. something we haven't really touched on that I think that we should talk a little bit about would be like patent trolls. Right? So, and not just software patent

[00:30:50] **Carol:** Well, so what is the pattern don't even though the patent troll is you said that earlier and I

[00:30:54] **Adam:** Usually a patent troll is a person or company that buys patents and then goes around and looks for people that are infringing on that patent. And so they might look before they buy, so they know what to buy, but they find people that are infringing on a patent that they own. And then they basically extort you.

[00:31:08] **Adam:** They say, give me a certain amount of money as a licensing fee, or I'm gonna take you to court and I'm going to ruin your business sort of thing.

[00:31:15] **Ben:** It's like ransomware.

[00:31:17] **Tim:** Yeah.

[00:31:18] **Adam:** professional ransomware

[00:31:20] **Ben:** Okay.

[00:31:21] **Adam:** kind of. Yeah. And so, but that is their business model, right? the business exists to buy patents and enforce them as, basically legal extortion sort of thing. And I think you'd be hard pressed to find somebody that thinks that the practice of patent trolling is actually beneficial for the world other than they're extracting capital value.

[00:31:44] **Adam:** If you have that sort of worldview.

[00:31:45] **Ben:** I assume you can also buy companies that own patents

[00:31:49] **Ben:** Oh, yeah. Yeah. those

[00:31:50] **Adam:** there's plenty of companies that get bought simply because they have a patent on something, like, what's a good example. You see that a lot in in tech buyouts, they'll buy some company and the product just gets shut down and you look at it and you go, well, why did you buy it?

[00:32:04] **Adam:** If you wanted to shut the product down? It's because they wanted the people and, or the patents.

[00:32:09] **Ben:** Yeah.

## [00:32:10] Incentivizing Research and Development

[00:32:10] **Tim:** So earlier we, we said that the idea of patents is to encourage innovation, right? Because innovation is hard. And so if you can guarantee that you have exclusive use of it for 20 years and that. it's, it helps offset some of the risks.

[00:32:25] **Adam:** right.

[00:32:26] **Tim:** and then we also talked about some of the drawbacks of it and how it can almost stifle innovation at times. but one thing that in the United States is the United States that the tax law does for companies to encourage them is the R and D tax credit. So I don't know if a lot of people take advantage of that.

[00:32:43] **Tim:** we do this. And the only reason I put it together in my head, the same people that talk to us about patents every year, it also talks about R and D tax credit. So basically the United States, the R and D tax credit is if you're doing research and development, which is coming up with design work, even if you're not like solving a, a novel problem, but if you're solving maybe something that you really haven't done before, and you're building a product, all that work that goes into doing the research, building a prototype, building the MVP It is it's beyond just your normal maintenance kind of thing.

[00:33:14] **Tim:** All those hours can qualify you for tax tax credit, your company for tax credit. So whatever they're paying you, whatever your salary is, you can at a state and federal level get anywhere between 10 to 15% of your salary back as a tax credit. But you do have to keep pretty good documentation of,

[00:33:35] **Ben:** That's what I was going to ask.

[00:33:36] **Tim:** Yeah. So the burden of proof is you need to show, well, we had a design meeting and we created this design document. we had aa meeting with maybe have a focus group or a customer group that's helping you, Build the the product. And so we met with them and here's the results of it.

[00:33:49] **Tim:** Even, just even your tickets. If you have a ticketing system, as long as it's not just maintenance and you're just fixing bugs and an exist, something, this is something new part of it that's never been done before. there has to be a level of uncertainty of how to solve the problem. and if you can prove all that then you submit it and yeah, it's, it can add up to huge amounts.

[00:34:10] **Adam:** I'm trying to see where the line is here between all new development, right? Like you keep saying it doesn't count for maintenance work. Right. So if I'm just writing a new feature, let's just say I'm writing my own ticketing system in my application. Does that count? Or because ticketing systems have been done, that's not interesting.

[00:34:30] **Adam:** Or new enough,

[00:34:33] **Tim:** No, and it has nothing to do with it being new. So I've made it, this is if you've never, your company's never done it before. You're not just refactoring an existing ticketing system then. Yeah. that's as research as R and D. Yeah.

[00:34:46] **Tim:** And if let's say, of course, no one's day is a hundred percent R and D, but if you are up to eight, so if it's 80%, so if 80% of your time is spent just specifically doing R and D work, then you can count a hundred percent of your salary as eligible for the tax.

[00:35:05] **Adam:** Okay.

[00:35:06] **Tim:** And some states are better than others. Georgia is actually very good as it has one of the highest percentages. Some states don't do it at all. The federal level it's the same, but some states are extremely good and Georgia is one of those that has a goodtax credit per state.

[00:35:22] **Carol:** There's actually like a four point test that you can do to find out if your development that you're working on qualifies for this. it's like you have to eliminate uncertainty. So you have to make sure that you've like attempted to show that the development is new and not just an improvement to what you're already working on. You have to like show the experimentation of it, the technology in nature, and then you have to show the qualified purpose.

[00:35:49] **Carol:** So there's actually a pretty good like guideline that you can follow if you follow the test to make sure that what you're doing meets those guidelines.

[00:35:56] **Adam:** Sounds like a lot of software companies should be looking into it.

[00:36:00] **Ben:** Yeah.

[00:36:00] **Ben:** So Carol has been building this whole Gmail integration with her support team and researching

[00:36:07] **Carol:** Hm.

[00:36:07] **Ben:** Google cloud stuff and Amazon stuff. I mean, is that technically all R and D that she's doing? I mean, she's building a new product essentially, or a new facet of her product.

[00:36:17] **Carol:** I can ask. I don't know the answer. I do know I had to track all of my time because we use the software called harvest to track our time too. And depending on if the project is getting billed differently, I just put 40 hours a week on that project or whatever it did go into a whole nother category.

[00:36:34] **Carol:** So I can ask if it's something that they're charging to R and D, which would then be part of the tax process that they do.

[00:36:41] **Ben:** Yeah, I'd be curious.

[00:36:43] **Carol:** I'll find it.

[00:36:46] **Tim:** All right. So yeah, I'm pulling up the stuff that, that we had to take training on this. so qualified researchers develop new or improved products or processes are these found within technical developments, which seek to achieve an improved business component, encountered technical uncertainty at the outset of the development effort regarding the appropriate method design or technical feasibility of the project.

[00:37:11] **Carol:** Yeah.

[00:37:11] **Adam:** So uncertainty about the appropriate way to accomplish the project. That sounds like every project.

[00:37:17] **Tim:** Right.

[00:37:18] **Ben:** So that's every day.

[00:37:20] **Tim:** As pretty much every day. I mean, yeah. And then the main thing is just making sure you have good good documentation of what you've been working, been doing. And it's not just you can also have people who qualify for the credit. You can have direct performance, direct support and direct supervision.

[00:37:35] **Tim:** So if you are the R and D product manager, you're not even writing code, you're just, you're there in the meetings and, working with the teams and they're there, weighing the pros and cons of different ways to solve the problem. you as a direct supervision can do that. So that's project management reviewing project status, but the main thing is that you are working on the product itself, which kind of encourages you to almost build a product department because that way you can kind of segment it out.

[00:38:01] **Tim:** otherwise you gotta keep track of your time. For instance, I'm a hundred. A hundred percent R and D

[00:38:07] **Ben:** Nice.

[00:38:08] **Tim:** my administrative stuff is only is around 20%. So that puts me in the a hundred percent bucket

[00:38:13] **Adam:** To my taxes, pay your salaries.

[00:38:16] **Tim:** and it doesn't pay my salary. I mean, you only get back 10 per about 10 to 10%, 15%. of as a tax credit, but it is a credit, which is nice because, depending on how good your tax people are that, let's say for some reason you were paying zero taxes, which I don't encourage, but if you're paying zero, you would actually would get money.

[00:38:34] **Adam:** wonder how this applies for like freelancers. Right? if you're self-employed and you're contracting or consulting for different companies, I wonder if the company gets to claim it or you get to claim it.

[00:38:46] **Tim:** I believe it's the company,

[00:38:48] **Adam:** Oh, lame.

[00:38:49] **Carol:** It seems like it would fall the other way. Not toward the freelancer.

[00:38:54] **Tim:** but I don't.

[00:38:54] **Carol:** Whenever I got moved to the tiger team, all of my work on the tiger team at my previous job, all that was R and D and that got billed back.

[00:39:02] **Adam:** Okay.

[00:39:03] **Carol:** Yeah.

[00:39:04] **Tim:** I mean, just, I'm just, I just bring that up and say there's different ways to encourage innovation. If that's the point of patents, this, the direct money, that's a good way to push experimentation,

[00:39:15] **Carol:** So you make something new, patent it and get tax credit for it. Look at that.

[00:39:20] **Tim:**

## [00:39:20] Patent Jurisdictions

[00:39:20] **Tim:** I'd like to throw this in. There is that, so in order for you to really have a secure patent, you pretty much have to file in every country because you can fall on America, but those aren't reciprocal in other countries as Well, So it gets pretty, pretty weighty. Yeah. Weighty to be able to do that, which is why, some people just patent in the United States and leave it there and hope that other countries don't steal it. But,

[00:39:45] **Carol:** Well, I think if you're doing industry like mass production things, it's I thought they usually do China and the U S

[00:39:53] **Tim:** There's 151 countries that are part of the burn convention. So, but if they're not in those, then you have to go to those other countries. Patents has no wait that's right. 151 countries. as copyright patents are much more complex. You have to apply for a patent in each country where you want protection.

[00:40:13] **Carol:** Yeah.

[00:40:14] **Tim:** Yeah. that's crazy.

[00:40:15] **Adam:** Once again, lawyers making more jobs for lawyers.

[00:40:18] **Tim:** Right.

## [00:40:21] Patreon

[00:40:21] **Adam:** Well then we'll call it there. So this episode of Working Code is brought to you by the concept of patent trolling and listeners. Like you.

[00:40:30] **Carol:** Yeah.

[00:40:30] **Adam:** If you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. And to say, thanks for your support. We offer some perks to our patrons.

[00:40:40] **Adam:** They all get an invite to our Discord server. And that's just a place where we hang out and chat about the podcast about work stuff, lifestyle whatever's going on. we have other perks available, like early access to new episodes before they come out to the public and our after show, which we'll be going on to record here just in a moment.

[00:40:56] **Adam:** every week we think our top patron and since this week is part of every week, we're sending out a huge thank you to Peter and to Monte and Monte asked us to send a shout out to Code to Inspire. And so this is the little blurb he gave me co code to inspire is the first coding school for women in Afghanistan code to inspire empowers young women in developing countries to drive economic and social progress by teaching them how to code, find programming jobs and launch technology.

[00:41:23] **Adam:** For more information, please go to www dot code to inspire. That's the word? T O inspire.org.

[00:41:31] **Ben:** That sounds awesome.

[00:41:32] **Adam:** Yeah,

[00:41:33] **Carol:** Yeah,

[00:41:34] **Adam:** definitely

[00:41:35] **Carol:** it out.

## [00:41:36] Thanks for Listening!

[00:41:36] **Adam:** if paying for podcasts, isn't your thing. That's cool with us. We appreciate you taking the time to listen and you can help us out without spending any money by sharing the show with your friends and your coworkers.

[00:41:44] **Adam:** You can also leave us a rating and a review on iTunes or wherever you get your podcasts. Please send us your questions and show topics on Twitter or Instagram @WorkingCodePod. Or leave us a message at 512-253-2633. That is 512-253-CODE.

[00:42:00] **Adam:** We'll catch you next week. And until then,

[00:42:03] **Tim:** your heart matters.

[00:42:07] **Ben:** That's a step too far.
