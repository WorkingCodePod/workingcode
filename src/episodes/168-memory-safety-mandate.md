---
title: "168: Memory Safety Mandate"
description: "On today's show, we talk about two major announcements relating to the technology world. First, the government released a report calling on programmers to start using memory safe languages. Second, Apple announced that it will halt work on Titan, its autonomous electric vehicle project."
date: 2024-03-06
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/c4f71e0e-989f-420a-88d4-b8e5643d8cbd"></script><div class="redcirclePlayer-c4f71e0e-989f-420a-88d4-b8e5643d8cbd"></div>

On today's show, we talk about two major announcements relating to the technology world. First, the government released a report calling on programmers to start using memory safe languages (see: [Future Software Should Be Memory Safe][gov-mandate]). Second, Apple announced that it will halt work on Titan, its autonomous electric vehicle project. We also talk about the pros-and-cons of a Computer Science degree in relation to the web development industry.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[gov-mandate]: https://www.whitehouse.gov/oncd/briefing-room/2024/02/26/press-release-technical-report/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/167-everyone-likes-their-own-brand.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** what is the difference between a memory safe language and what is, you know, what, and a not memory safe language? And my initial reaction was like, oh my god, they're saying that JavaScript has to go away, right? Like, Just because when you, when you say, some languages are bad at things, just like that statement alone, immediately my brain goes to JavaScript because there's so many like weird, terrible things about JavaScript.

[00:00:22] **Adam:** as it turns out, at least as far as I understand it, JavaScript is considered memory safe, from the, the terms of this, memo.

## [00:00:50] Intro

[00:00:50] **Adam:** Okay, here we go. It is show number 168. And on today's show, We are going to talk about the new White House mandate on the, on all of our code and, and how we're being oppressed by the man.

[00:01:02] **Tim:** You can't tell me how to code.

[00:01:04] **Adam:** but first as usual, we'll start with our triumphs and fails. Looks like it's my turn to go first. So we're going to start with me

## [00:01:10] Adam's Triumph

[00:01:10] **Adam:** and I'm going to kick us off with a triumph. I, today is Thursday. We're recording Thursday night. tomorrow is Friday. I'll be packing up and then early, early, early Saturday morning, I'm getting on a jet plane and we're going on a vacation for a week, so I will not be on next week's show.

[00:01:26] **Adam:** Um,that, missing next week's show is not the triumph, but the triumph is I'm gonna be on vacation for a week.

[00:01:32] **Ben:** Where are you going?

[00:01:33] **Adam:** taking my family on a cruise, we're leaving out of Long Beach, California, going down to the Gulf of Mexi No, not the Gulf of Mexico, the Gulf of California, which is in Mexico.

[00:01:41] **Ben:** Very

[00:01:42] **Adam:** Um,we're doing, it's, Cabo San Lucas, Mazatlan, and I believe Puerto Vallarta. Puerto Vallarta, sorry for my gringo ease.

[00:01:50] **Ben:** Very cool. Hopefully you see some fun marine life. I don't know if that's an area of the world where dolphins swim, swim alongside the cruise ship or anything like that, but

[00:02:00] **Adam:** Yeah, I don't know. we've, we've always seen dolphins and stuff when we go on cruises. This'll be our second cruise as a big family. I think it'll be my fourth cruise with my wife. and it's always fun. You know, you always see all kinds of fun stuff, so.

[00:02:13] **Tim:** How many cruises without her?

[00:02:15] **Adam:** actually. She's done one without me before we met.

[00:02:18] **Tim:** okay.

[00:02:18] **Adam:** So, easy one for me this week. How about you, Ben?

## [00:02:22] Ben's Triumph

[00:02:22] **Ben:** I'm also going to go with triumph. I've been just digging into some code lately and code that I don't know anything about. I've been, as I talked about on a previous episode, I've been working on some Svelte stuff. I've also been digging into some AlpineJS. AlpineJS is, it's really, there's something very compelling about it because it kind of works off of the existing DOM as opposed to recreating the DOM entirely.

[00:02:47] **Ben:** So it's, it feels more along the lines of a jQuery Progressive enhancement, but it sprinkles in very interesting semantics, like, AngularJS directives. And I don't know, I'm just, I'm enjoying the, I don't know anything about how this works. Having to look at the source code, having to kind of understand how little mechanics within it operate and how do I work with and against those mechanics.

[00:03:11] **Ben:** And it's just fun to be playing in a completely new sandbox for a little bit.

[00:03:16] **Tim:** Ben's learning stuff.

[00:03:18] **Ben:** yeah, yeah, it's good. I mean, part of me, there's always, there's always a little tickling sensation in the back of my mind. Like, what am I doing?

[00:03:26] **Adam:** standing behind you and

[00:03:30] **Ben:** I'm always wondering if this is really a good use of my time. And, and if I put on my maybe more official time management hat, you know, what is the business case for, for this kind of exploration? But for the moment, I'm just. I'm just enjoying it.

[00:03:44] **Adam:** you are revived laid off. you're

[00:03:48] **Ben:** that's how

[00:03:48] **Adam:** free time here

[00:03:49] **Ben:** that's how I'm leaning into it. That this is, I'm just in, in non 100 percent work mode and, and the, the difference between full time Ben and part time full time Ben is, is all the, kind of just fun research stuff I can do. So I'm, I'm enjoying that. I'm leaning in.

[00:04:06] **Ben:** I'm leaning in hard.

[00:04:07] **Adam:** I think, I think the, the value proposition right now is like, they brought you back on because you know these systems and you have, everything you need to know is in your head for like how to keep this, these apps online and running while they wait to shut it down. End. I think as long as you're providing that value, you're doing that job of keeping it online, that's, that's all that they're asking of you, and if you can do that in, you know, 20 percent of your time, then, and you have 80 percent of your time to prepare yourself for the next phase of your career, I think you Owe it to yourself to do that.

[00:04:38] **Carol:** Absolutely, yeah.

[00:04:39] **Ben:** I'm, I'm definitely, I'm, I'm striking a good work life balance. Let's just put it that way.

[00:04:47] **Tim:** You gotta get out a guilt free card.

[00:04:49] **Ben:** Yeah. So I'm going to call it a triumph and feeling good. And, Carol, what about you?

## [00:04:54] Carol's Fail

[00:04:54] **Carol:** Oh man, I hate to, ruin the streak here, but I definitely am on failure mode, guys.

[00:04:59] **Tim:** Oh

[00:04:59] **Carol:** So, I missed last week because I was sick, and it turned out I got really sick, and a lot sicker, and I got so sick that I had to cancel going to one of my best friend's wedding, where I was the matron of honor. So I had to, yeah, call her and tell her I'm way too sick to travel.

[00:05:17] **Carol:** So she's getting married this weekend and I'm not there and I'm sad, but I'm actually recovering. So that's a good thing. I was able to work a little this week and get a few things done. I'm kind of on brain fog and not thinking clearly, but I'm accomplishing a little bit. So that's good.

[00:05:33] **Ben:** Well, I'm super happy that you're feeling better. And if I can just interject some levity for a moment, I think it, I think it's funny that, literally Carol's failure is something that I have fantasized about myself, where I have to go to a wedding and I think, is there any way I can just get so sick that I don't have to go to this wedding?

[00:05:54] **Adam:** Hey, anybody have a toddler that can come over and breathe in my mouth for a little while?

[00:05:59] **Tim:** I thought your fantasy, you wanted to be a matron of honor.

[00:06:01] **Carol:** I know, that's where I thought this was going, a cute dress and some heels.

[00:06:05] **Tim:** I know,

[00:06:06] **Carol:** Yeah.

[00:06:06] **Ben:** pull it off.

[00:06:07] **Tim:** Slip on those Spanx.

[00:06:09] **Carol:** No doubt. All right. Well, I just had great, great visions in my head. So thanks, Tim. Yeah.

[00:06:15] **Tim:** You're welcome.

[00:06:16] **Ben:** Are you, are you, are you back to a hundred percent or are you still kind of on the mend?

[00:06:20] **Carol:** I would say I'm like probably 80%. I'm still having some pain, but I finished my like multiple rounds of antibiotics now. So I think the next few days should be the final of all of it. So, yeah. Thanks for asking. Yeah, that's me. What about you, Tim?

## [00:06:36] Tim's Fail

[00:06:36] **Carol:** no,

[00:06:36] **Carol:** doing a failure, so you're not alone. no,

[00:06:40] **Tim:** and we tried to record a few days ago, just things didn't work out. I had put, we have a little sheet where we kind of put what we're going to talk about and, and I put still banging my head on voice recognition, using SRGS plus XML, which is kind of an older, more recent, it's kind of an older technology that maybe that's why it's not so fantastic at voice recognition.

[00:06:59] **Tim:** But it's, it's what. The solution I use offers, and it finally had to, finally solved it. I got the issue working and what we're doing is that this company has life insurance policies and they have a lot, some of them, most of their policies have like a million policies. Most of them are just digits, right?

[00:07:17] **Tim:** So that's great for an IVR where you just. Call a phone number and punch in the digits, but they do have a fairly large number of ones that just have like lots of letters in them. And it's a 10 digit alphanumeric thing. And I got it to where I could like say up to the seventh character and we would take it fine.

[00:07:37] **Tim:** But then after that it was, I mean, the accuracy went down. Ridiculously. And it wasn't, there was a no match. So I'm like, this just isn't gonna work. So still the failure, I got past it, but it's still a failure because I had to do a very ugly solution to fix it. So basically you have to say one letter at a time, say yes or no, if it's the right letter.

[00:07:59] **Ben:** Oh no. Oh, that's awful.

[00:08:03] **Tim:** And when it, when it gets to 10 characters, that's your policy number. so it takes about three minutes to say the, which is awful. I, but the good thing is once they enter it and it's found, we can store that and associate it with their phone number. So the next time they call, they just goes, Hey, are you calling about this one?

[00:08:22] **Tim:** Okay.

[00:08:24] **Carol:** so this is going to sound awful, but are the majority of your users like of an older age?

[00:08:30] **Tim:** Yes. It's life insurance policies. Yeah.

[00:08:32] **Carol:** Okay, so I think that's where you may get a little lucky is old people don't mind saying things very slowly and getting confirmation like one character after the other. I'm serious. They don't. If you were to ask me to do that, I would just cancel my policy and find something else.

[00:08:48] **Tim:** Exactly.

[00:08:49] **Carol:** I would. I'd be like, no, I can't do this. I hate you.

[00:08:53] **Adam:** Yeah. And not only would you do that, you'd be, you know, spend three minutes to get it one character at a time. And then you would be like, okay, redirecting you to customer service. And the first thing the customer service person says is, can you give me your policy number? No. F you.

[00:09:05] **Carol:** Yeah, absolutely.

[00:09:07] **Tim:** We'll see how it goes. I'm experimenting with the idea of sending them a text message, you know, because they tell, they'll say, press one if you have letters in your, in your policy number and just sending them a text and say, the text says, could you please type your policy number? So they just type it in.

[00:09:23] **Tim:** Yeah. Yeah. Yeah. But then they'd have to go back to the IVR. I'm still torn on that one because I hate it when I have to take the phone away from my ear, minimize the, the, the, the call screen, go to the keypad, type, type, type of text or something, and then I got to go back to it. And it just seems a lot of channel switching.

[00:09:44] **Tim:** So

[00:09:44] **Ben:** always afraid that I'm going to hang up accidentally if I have to start hitting the home screen. Okay. Can you maybe give people the option to use a, like the army radio talk where they can, you know, like Charlie. Mike,

[00:09:55] **Carol:** Alpha. Bravo. Yeah.

[00:09:58] **Ben:** you're like, hit one if you've been in a, in a war. And

[00:10:02] **Tim:** Right. you know military speak, yeah,

[00:10:06] **Adam:** The natal phonetic alphabet. We did that on the show.

[00:10:09] **Carol:** we did. Yeah. Yeah.

[00:10:11] **Tim:** So anyway, that, that's my failure, but I'm through it what it is.

[00:10:16] **Adam:** Yeah. I can see why you call that a failure.

[00:10:19] **Carol:** Yeah. Yeah. That's not a win.

[00:10:21] **Tim:** uh.I solved the problem, but boy, it feels dirty.

## [00:10:24] Future Memory Should Be Memory Safe

[00:10:24] **Adam:** Yeah, well, okay, so I mentioned it at the top of the show. It's pretty big news right now. The White House put out a press release. the title of it was, Future Software Should Be Memory Safe. And the general gist of it was like, you know, there's a lot of, Cyber security is a big deal right now. Um, I guess, nation state hacking is kind of, continues to escalate.

[00:10:46] **Adam:** And so, as a result of that, they're saying like, we could eliminate a whole class of, vulnerabilities just by changing the languages that people are using the tech stacks. and kind of like how we say, if you switch to TypeScript instead of JavaScript, it kind of eliminates a whole class of bugs from your code, or at least it alerts you that they would be there.

[00:11:05] **Adam:** giving you the little red squigglies in your IDE saying, Hey, you're doing something dumb here. and so we thought we would talk about that. of the three of you, and I'll, I'll throw in mine as well. you know, when you saw this, what was your, your initial reaction?

[00:11:18] **Carol:** Yeah, so for me, number one, this isn't me commenting as a government employee. Let me go ahead and caveat that, right? But I just feel like mandates like this and requirements or even requests coming from this type of level isn't going to have any impact on Commercial companies that have to do nothing.

[00:11:39] **Carol:** It's going to get pushed down to federal applications that are doing work and they're going to be forced to make changes, but you know, I can't see one of you having to make a massive change to your system because this was published.

[00:11:51] **Adam:** probably like maybe contractors, right? So if you're, if you're applying for a, a project or whatever, you might get bonus points for using a, you know, for complying with this. I won't call it a mandate, but,

[00:12:04] **Carol:** Like if you're a vendor trying to sell a software? Yeah. Okay. Yeah. Maybe. Yeah. I could see that. Yeah.

[00:12:14] **Ben:** about a very specific type of memory leak. I don't know if you can call it memory leak in this case, but there are so many ways that a shared variable or a shared chunk of memory can manifest in applications. I'm not entirely sure that the thing that they're even saying is a problem really covers as many problems as, as good programming techniques will handle.

[00:12:40] **Tim:** Don't leave it to the U. S. government to be about 10 years too late.

[00:12:45] **Ben:** I mean, so, you know, the, I use ColdFusion primarily at work and I, and I think ColdFusion is considered a memory safe language.

[00:12:54] **Adam:** How has this never come up before?

[00:12:57] **Ben:** You know, we're almost 170 episodes and I thought I should drop a, drop a, a, a truth bomb there. but, ColdFusion can, for example, share access to the application scope or the server scope, or they can share session scope across requests. You know, every request coming in can access. Shared database records.

[00:13:20] **Ben:** And the security of those access points is dictated by the, the, correctness of the software, and that has nothing to do with, with the memory safety that I think they're talking about. So I'm, I'm, I. It, like, it sounds like it's a good intent, but I'm not sure how much meat is in the intent that they're trying to fix.

## [00:13:43] Memory Safe vs Not

[00:13:43] **Adam:** Well, maybe this is a good moment to just jump in and say, like, what is the difference between a memory safe language and what is, you know, what, and a not memory safe language? And my initial reaction was like, oh my god, they're saying that JavaScript has to go away, right? Like, Just because when you, when you say, some languages are bad at things, just like that statement alone, immediately my brain goes to JavaScript because there's so many like weird, terrible things about JavaScript.

[00:14:09] **Adam:** And so, you see this, this memo from the White House, future software should be memory safe. I'm like, oh my God, there is so much bad JavaScript that's going to have to You know, like go away, be rewritten or something. But as it turns out, at least as far as I understand it, JavaScript is considered memory safe, from the, the terms of this, memo.

[00:14:29] **Carol:** So, the, the whole, the synopsis is like, you know, it's all about cybersecurity and, not leaks. What's the word, like vulnerabilities. Right. Exposures. Yeah.

[00:14:40] **Adam:** Yeah, things that, that could lead to some, sort of hacking, you know, uh, why, why, I'm, I'm terrible at words tonight, sorry,

[00:14:49] **Ben:** it's a leap year day. So I think we're all just a little extra tired. Nice.

[00:14:53] **Adam:** Day, so we're, we're on day 365, okay, by sextile,

[00:14:57] **Tim:** just real quick aside. I learned a really great word to describe leap year bisextile,

[00:15:07] **Carol:** I like that word. Yeah.

[00:15:09] **Adam:** Why?

[00:15:11] **Tim:** yeah, you'd have to go to the Wikipedia

[00:15:13] **Adam:** Google it. Yeah.

[00:15:14] **Tim:** see the, the origin of it. I mean, you would think the number two and the number six really shouldn't have anything to do with it, but it's some, some Roman thing.

[00:15:22] **Tim:** But anyway, word, word for the day today, being today, being a leap day.

[00:15:27] **Adam:** Cool. so memory safe languages, really, I think what it boils down to is if you're using malloc to allocate memory, for, for variables that you want to create, that is a quote unquote not memory safe language, right?

[00:15:40] **Tim:** Malik. So that's like a memory allocation

[00:15:42] **Adam:** right. So if you are writing C or C you'll use malloc to say, okay, I need, I need to create a variable, and so I can put something in it and I want to in 32 or whatever.

[00:15:54] **Adam:** And. and, you know, I think it's been, God, I think the last time that I wrote C or C was in high school or, or not too long removed from high school. So we're talking about a million years ago, but, you know, I think that the danger is if you, you know, you dereference a pointer poorly, or you make, you know, you make a subtle mistake with, with memory like that, then there's the potential for, you know, we've all heard of like buffer underrun or buffer overflow type things.

[00:16:24] **Adam:** I think that that is where those happen, and I'm, you know, I am officially out of my depth at this point, but this is my, my general understanding. And, so if you're not doing that, right, if you don't have to, if you can just say var x equals 32, then that is probably a memory safe language. So, anything on Java, you know, actually I had a whole list, where did that list go?

[00:16:46] **Adam:** So, memory safe languages include Rust, Go, C#, Java, Swift, Python, and JavaScript. My mind explodes on that one. and languages that are not memory safe include C, C++ and Assembly. So, like,

[00:17:04] **Ben:** But I think they've had some buffer issues where you, they, they, they tell you not to use certain buffers anymore because they had some sort of vulnerabilities.

[00:17:12] **Adam:** that doesn't sound specif Like, I'm not recalling that specific thing, but I know that Node is built on V8, and V8 is in, I believe, C++ So totally plausible that there's like a path to memory unsafeness there. but yeah.

[00:17:30] **Ben:** mean, so I am not a language person here. You know, this is something probably someone like Sean Corfield could probably enter,talk about with a little bit more depth here, but my understanding is that we have different generations of languages and the, the later generations, like the fourth generation languages are.

[00:17:50] **Ben:** More abstract and slower because they're giving you better abstractions to work with. And then as you go down lower in the different generations of languages, they become much more efficient, but the trade off of that efficiency is they get much more complicated with all of this stuff, like the memory allocation, the deallocation and, and, and how can you, can you continue to have a world in which have fast languages, if the language is below them?

[00:18:19] **Ben:** Aren't allowed to kind of play a little faster and looser with the rules.

[00:18:23] **Adam:** I think that's what Rust kind of is, right? So Rust was even listed on that list of memory safe languages, but you're, it, it operates sort of at the same it level as C and C++ I think. But it's, it, it has language features that make, especially memory handling, completely safe.

## [00:18:43] SQL Slammer

[00:18:43] **Tim:** know if you guys remember back because the, the article referenced one of these attacks, the, the, SQL Slammer.

[00:18:50] **Carol:** Oh, I don't remember that one.

[00:18:52] **Tim:** so that was 2003. I do, I do remember this one. 2003 is a computer worm that, that basically used, exploited a buffer overflow bug in Microsoft SQL server. And could get in and then it would basically do a denial of service attack and then spread itself from that machine that it's infected to other machines.

[00:19:11] **Tim:** And it got there like 70, 75, 000 SQLs. And all this was just because it was able to overrun the buffer and then inject some of its Stuff into there where, you know, overwrite, more memory than what it was, should have been allocated. So it was, I remember it being pretty bad. So whatever they wrote Microsoft SQL Server in was not memory safe.

[00:19:35] **Tim:** Probably writing in C.

[00:19:37] **Adam:** And, and I think that that's a interesting point. So I know that there are people that are doing things with like Rust and Go for the web, and I mean, Rust and Go are on the, the safe memory safe languages list. But like, Ooh, I really don't think that this affects web development all that much, right? Like if you're writing C for the web, you have particularly interesting challenges, I bet.

[00:20:01] **Adam:** And I'd love to have you on the show. Let's talk about why you need to use C for the web. It's, it's, I think Carol kind of nailed it, right? Like the, this is going to probably mostly affect people that work for the government and vendors and, and, contractors. I

[00:20:23] **Carol:** of like a cover your ass kind of situation. So I will say some of the stuff that they brought up kind of later in the actual report itself, the back to the building blocks report, bring up the fact that The engineers writing code should be more responsible for what they release rather than expecting the end user to protect their information, which is currently what our dynamic is, I feel like, that we expect our users to use the system properly and to know what sites not to click on and when to not do bad actions.

[00:20:58] **Carol:** But in reality, the engineers and the CTO and your, Like your cheap information officer people, they should be making the decisions up front to provide a secure software that your end users don't have to worry about.

[00:21:14] **Adam:** think if you're working at a company, if you're writing, I don't know what mainframe software or whatever, and you're writing C and you've been like dying to rewrite your app in Rust, like here's your ammunition, right?

[00:21:23] **Carol:** Send this out to everyone.

[00:21:26] **Tim:** Yeah, I mean, what you say, Carol, it's so true because I mean, prior to 2003, that with that SQL worm, I mean, it was pretty, some people, it was pretty common for them just to leave the SQL server exposed to the internet, you know, port 1433 on SQL server, just out there in the world. And they're like, Oh, it's got a password on it.

[00:21:45] **Adam:** Mm

[00:21:45] **Tim:** Um,

[00:21:46] **Tim:** and then this slammer worm just totally bypassed the password. so that now, now it's like, you know, I, I can't. And I know we don't have any SQL machines that aren't, that, that are exposed to the internet.

[00:21:57] **Carol:** Yeah. It's actually one of our security audit things that we have to remedy before we can do any release. Like most of our services can't have access to the internet and it has to be fixed before.

[00:22:09] **Ben:** For whatever reason that made me think we, we talked, I'm pretty

## [00:22:12] Package Vulnerabilities

[00:22:12] **Ben:** sure about the, the log4j security vulnerability, a couple of, I don't know, it was like six months ago.

[00:22:19] **Carol:** actually call that out in the report.

[00:22:21] **Ben:** they did? So it's, there's such an interesting lesson there because the, my understanding was that the vulnerability in log4j existed because there was some special syntax that allowed the logger to do essentially stuff that it shouldn't do, make calls out to external systems. And, it's, it's also just a reminder to not make your stuff so flexible. It, you know, like your, your, your piece of code should do one thing and should do one thing pretty well. And sometimes flexibility hurts more than it helps. and also apparently it keeps your code more secure because less moving parts, less things to worry about, less exploitation, exploitative surface areas.

[00:23:05] **Carol:** one other thing I will add is that it does call out the fact that we have multiple places that you can go to and look for current, exposures and exploits, and it should be the responsibility of the companies using these languages, using these packages, using these, you know, whatever services they are to patch them and get them fixed, and the majority of bad things happen when they're not.

[00:23:29] **Carol:** No one at a company makes the decision to go fix a problem once it's been released. And I think that there should be some accountability to those people. So like when all of our credit cards are stolen and we lose lots of money, there should be some accountability to a company for why you're not keeping our information secure.

[00:23:47] **Ben:** They've been talking about this a lot with all the automated car stuff, too. You know, like if your automated car hits someone who is Can you, is there a perp walk that can happen at that point? You know, does someone get put in handcuffs and, and who is that? And so many people are involved with making the cars, making the software, delivering the software, wiring it into the motherboards and everything.

[00:24:10] **Ben:** Yeah.

[00:24:10] **Tim:** to the U. S.

[00:24:11] **Ben:** Yeah. Take, take the corporation to jail.

[00:24:13] **Carol:** Mm hmm.

## [00:24:14] Killing Sunk Cost Projects

[00:24:14] **Tim:** You kind of pivoted pretty well into what I want to talk about, talking about automated cars. you know, Apple just announced, I don't know if they officially announced it, but it's the rumor on the street that they're, they've been working for like 10 years.

[00:24:26] **Tim:** on, an electric car, self driving electric car, the Apple car, and they're killing

[00:24:31] **Adam:** flip it over to charge it, right?

[00:24:32] **Tim:** Yeah. Right.

[00:24:36] **Ben:** Oh, burn.

[00:24:37] **Tim:** And after, you know, billions of dollars and lots of work, they they're just killing it. They're just killing the whole project. It's made me think of that happens so much in software projects where company says, here's what the, you know, we're going to do this big initiative. This is really going to make us lots of money and people work on it for a long, long time and then things change or doesn't seem like it's killer app.

[00:25:00] **Tim:** You thought it was, or maybe it wasn't really a feature that you needed. And then after all that time and money, you just kill it. Doesn't go live.

[00:25:06] **Carol:** Yeah. I don't want to be in that role. I get too emotionally attached to my projects and to my code that I invest a lot of heart. So to be like, Oh, it's not working. Kill it. Let's go on to something else. Oh, I'm going to need like meds for that.

[00:25:23] **Adam:** so that means that it's interesting to bring that up. This is something that's come up on our discord several times in the last like week or two about, you know, people working on big projects and then, you know, stuff changes in an industry or just for the business or whatever, you know, the, they were expecting a bunch of money and it goes away and they're like, okay, well, the 10 people that were working on this thing stop because we're not going to do that anymore.

[00:25:46] **Adam:** Even though you've been going on it for nine months, like. And you mentioned Sean, he had posted, I think it was today that I saw, you know, or yesterday I saw that he had posted, you know, that happened to him. He was working on a project and they were pretty close to the finish line and they were told, nope, stop, we're not going to do that anymore.

[00:26:02] **Adam:** And then today he found out like, well, we're going to actually like do a part of it or something. So, not a total waste. and it just makes me think like. Back to the Agile discussion, right? So like, I think the more that we talk about this, the more that I think about the, the risk of taking on big projects, the more it makes me think, like, I, I want to optimize for putting stuff in production as fast as

[00:26:26] **Ben:** Yo, for

[00:26:26] **Carol:** Oh yeah. Yeah.

[00:26:28] **Adam:** Like the, we've talked about feature flags over and over on the podcast and like, just Make changes. So, do you guys ever use the app, what is it called? TripIt, where, like, you, you know, you can make plane and hotel, whatever, reservations and then you just, you get the confirmation email and you forward it to the TripIt email address and they've got an app

[00:26:45] **Ben:** sounds

[00:26:45] **Adam:** and you can, like, and then you just open up the app and it's got all your confirmation details nicely organized or whatever in there, which is fine.

[00:26:52] **Adam:** it always bothered me, but now, like, I don't know, maybe, maybe In a small way, it's a good thing. So TripIt has been around forever, and I remember many years ago, like, you know, They, it's like you, you would go in and like one page of their app was like totally redesigned. And you're like, oh cool, they're doing a whole redesign.

[00:27:09] **Adam:** And you're like flipping around and like, no, it's just the one page. Okay. That's interesting. It's like they got a whole new thing going on, but it's only on one page of the app. And they're like, you know, six months later, the second page comes and like, okay, there's, there's something wrong here, but at least the app is still running.

[00:27:23] **Adam:** But like, I think that that might be,visually the right approach, right? Do some discrete thing that you can ship and ship the thing, and then work on the next thing that you can ship and ship that thing.

[00:27:35] **Carol:** Iterate, iterate, iterate.

[00:27:37] **Adam:** Yeah, for sure. Like, I'm kind of going through that right now myself with my current project, like, you know, I did that whole, design system build, and we're working on our, our SvelteKit app rewrite slash multi tenant project.

[00:27:50] **Adam:** It's like, why, why do one of these two sort of rewrite ish things, you know, why rewrite twice when you can rewrite once and do two things at once sort of thing. So, we're trying to go to multi tenant from single tenant and we're trying to. fix our tech stack, you know, port over to new stuff. And so, you know, I did the design system.

[00:28:09] **Adam:** That was sort of like the, the, table stake stuff, right? We need, we need a way to be consistent. And so now the next thing is like, okay, I need to get something into production immediately. And how do I do that in a way that's going to be minimally disruptive to current users? And also the thing on my mind is like, I don't want to be burdened by the old design, right? Like I want it to be familiar and similar.

[00:28:37] **Adam:** But also like allow myself the leeway to rethink and reimagine the design a little bit.

[00:28:42] **Ben:** I, I, being burdened by the old design, I mean, we're kind of way off topic now from the killing expensive projects, but, being burdened by design stuff is, is really challenging because especially when you're building a design system, because chances are that the design system has a nice way of building CSS classes and the specificity of the, of the property blocks is relatively low.

[00:29:08] **Ben:** You know, if you're using something like scoped CSS. Where it's like attribute and maybe class name or something like that, right? And you're like, oh, wow, that works really great. And, and everything's scoped and it's beautiful. And then all of a sudden you open up, you know, some area of your application, like an old modal window.

[00:29:25] **Ben:** And all of a sudden you see inputs. Where the selector has like seven things in it. And it's like, if, if not this and not that, and it's inside this other thing and suddenly the specificity of your design system is being blown away by these overly complicated UIs and you're like, I don't even know how to, I don't even know how to deal with that.

[00:29:48] **Ben:** I literally have to rip out that entire old UI in order to get the new UI components to start working properly.

[00:29:54] **Carol:** nothing about that sounded fun.

[00:29:56] **Ben:** No,

[00:29:59] **Adam:** I gotta say working with ScopedStyles in SvelteKit has been super nice, like ergonomically and. It kind of makes me think like maybe the cascade was not the best idea to begin with. Like, I don't know, cascading to a point. Oh, well, I know they're like, they're working on, bringing scope styles to CSS itself.

[00:30:21] **Adam:** And also like donut scoping. You can say like, okay, it starts here. And then when you get to this point, that's when it stops.

[00:30:27] **Carol:** Oh, that's neat.

[00:30:29] **Adam:** very interesting to me too. Like it cascades in, but then, but then stops at a certain selector.

[00:30:34] **Carol:** Oh.

[00:30:35] **Tim:** know we've, we've been 32 minutes in and you finally got onto a Svelte point. So how long it would take?

[00:30:41] **Ben:** I literally. Didn't even know that Apple was working on cars.

[00:30:45] **Carol:** I didn't either.

[00:30:47] **Ben:** that was

[00:30:47] **Tim:** You didn't. Yeah.

[00:30:48] **Ben:** To, to be clear. So I just wanted to put a fine point on it though. I think the idea of being able to kill something, even if you've dumped a ton of money and time into it, that's really healthy as opposed to continuing to spend billions of dollars onto something that you don't think is going to be fruitful.

[00:31:06] **Ben:** That's, I think that is the majority approach that people take. And being able to cut your losses is, is very difficult for people. And it is pretty amazing when you can muster the courage to do something, especially, I don't know what the dollar amounts were, but it's got to be astronomical.

[00:31:23] **Adam:** Oh, I'm This is gonna be huge. Yeah.

[00:31:25] **Tim:** Yeah. So, I

[00:31:25] **Adam:** At least the cost of like three or four iPads. The

[00:31:30] **Tim:** Or those, those, those little

[00:31:33] **Carol:** Goggles.

[00:31:34] **Tim:** goggle things they have.

[00:31:36] **Adam:** Vision Pro, is that

[00:31:37] **Tim:** Yeah. I mean, you don't want to fall into the sunk cost fallacy, right? That, that, well, you know, we spent a billion. What's, what's a few more billion. Well, a few more billion is a few more billion. You can probably do some other stuff with that.

[00:31:48] **Carol:** Yeah.

[00:31:49] **Tim:** But I mean, you know, on our scale, it's like, I've seen initiatives that people have done and, and sometimes they, you know, either they get done and turn out to be not something that turned out to make you any money, so that actually cost you money.

## [00:32:02] Managing Vulnerabilities

[00:32:02] **Tim:** I worked on something, it was like a regulatory thing that my clients should be using, but for some reason they're not interested in buying it. So I, I guess it's, it's, it's one of those regulatory things that no one's enforced against. So they're like, yeah, we're not paying for that until we get, until we get in trouble.

[00:32:17] **Carol:** Yeah. Wipe mine ahead of time.

[00:32:19] **Tim:** yeah, spend months and months, you know, building this thing to help prevent them from getting fined. And they're like, well, we're not getting fined anyway, so we're not paying for it. So I'm like, oh, that was a waste of time.

[00:32:28] **Adam:** Makes me think of, GuardDuty. So, it's just a, it's just, it's a tool you can turn on in AWS and you can say, okay, you know, we're using ECR, which is Elastic Container Registry. So we're pushing Docker containers up to ECR. And you can say, like, scan my lambdas and, you know, it can, it basically, it scans your code and it says, oh, okay, you're using Java.

[00:32:51] **Adam:** And you, you've got code here that's vulnerable to log4j, or you've got, you know, something vulnerable to Heartbleed or whatever. All the CVEs, it'll list them all and say, this is what you've got, this is what you're vulnerable to. And It is overwhelming, right? There's a ridiculous number of vulnerabilities in everything.

[00:33:11] **Adam:** And to be honest, it is not possible to keep up with all of them. And I mean, I mean, okay, how many of us have done like an npm install and you get 700, you know, high critical,

[00:33:25] **Ben:** them at this point.

[00:33:26] **Adam:** yeah. It's, it's a problem, because, and honestly, it's like, there's a, there's a weird fine line between like something that is actually critical because it affects you and something that could be critical if you're using it in the, the specific way, right?

[00:33:45] **Adam:** So like, there's a lot, a lot of those things in NPM warnings, it's like, oh yeah, such and such module is vulnerable to, buffer underrun attack or whatever, or DDoS, you know, prototype pollution is

[00:33:56] **Ben:** Catastrophic regex backtracking.

[00:33:59] **Adam:** Yeah, and it's like, okay, sure, but, you know, this is a command line utility app and so it's never exposed to the public and, you know, like, just, I wish there was some way to, to tighten that down to say like, okay, this is how we're using it.

[00:34:18] **Adam:** This is a sort of a class of things that might be possible attack vectors or something. Because there's way too much noise. And that's kind of what I was getting at in GuardDuty as well. It was right. Like, you know, just because I have a ColdFusion container, right. It's like, okay, all these Java vulnerabilities and, not so much in ColdFusion, but then it like, it looks at your JavaScript too.

[00:34:42] **Adam:** And it's like, oh, you're using jQuery three dot whatever. Well, there's, here's a whole bunch of things that are in jQuery. Like there's, it's just not. possible to stay on top of it all. And it's, it's incredibly overwhelming. And then you have to play the whole, you have to do the whole song and dance for compliance reasons of like, okay, these are the vulnerabilities that we're aware of and we're choosing to ignore them because we, you know, we personally classify them as low risk or no risk because of the way that we're using the library. it's incredibly annoying, like red tape. It feels like pointless work. You know what I mean?

[00:35:16] **Carol:** So. Can I, can I go back to where we started this conversation though? If you, as your CTO of the company, that's your title, I think, choose to ignore these vulnerabilities and something happens, who's, who's responsible?

[00:35:31] **Adam:** Oh yeah, my name is on the document. I'm signing saying, you know, like we're, we're accepting the risk here. I mean, that's what it is. It's a risk assessment document that you have to do. and at the end of the day, I mean, you know, when you put up a building, somebody has to sign off and say, this building is safe for people to live in, and some of those buildings fall down and people die and bad stuff happens, you

[00:35:51] **Carol:** I shouldn't have laughed at that.

[00:35:56] **Adam:** but like, you know, bad stuff happens and people's heads have to roll and yeah, that's how they identify whose head has to roll, who signed off on this.

[00:36:05] **Ben:** I'll tell you one thing that I really enjoyed, which is granted, I think a more expensive option is to run some sort of a bug bounty where you have, I don't know, you don't have to have an isolated version of your application running, but I think that's probably recommended. But essentially for those who aren't familiar, you have some version of your application running in production somewhere.

[00:36:26] **Ben:** And you open it up to people to come and ask them to try and find vulnerabilities, to try and hack it, to run scans against it, and then anyone who finds a vulnerability can submit it, usually through some sort of a official pathway, and then they get paid, you know, depending on the severity of the bug, you know, oh, you discovered a cross site scripting attack, here's, you know, 300, or you discovered a tiny bug, and here's 100 kind of a thing.

[00:36:55] **Ben:** And,

[00:36:55] **Tim:** You know, there's, there's companies that do that for you.

[00:36:57] **Ben:** Yeah, yeah, yeah, yeah. 100%. but, but, the nice thing about that as opposed to something that automatically lists out all the security vulnerabilities is that these are people who are actually attacking and finding vulnerabilities. They're not theoretical. They are, they are actualized and, and,reproducible.

[00:37:15] **Ben:** And

[00:37:15] **Adam:** Right. So they're, they're not hitting you because you have a certain version number of a certain library. They're saying you have this open hole in your defenses.

[00:37:23] **Ben:** Right. Here's how I took advantage of it. Here are the reproduction steps. Here's the screenshot of the network activity. You have to fix this.

[00:37:31] **Tim:** We, we get that. So on a quarterly basis, that's part of our PCI scans. It does a scan and try it basically tries all those things. And then it tells you what it finds and generates a report and you go fix them. I just got one today. We, we passed without any issue. So, I mean, that's kind of a piece, kind of a better peace of mind.

[00:37:49] **Tim:** You know, you can still get those kinds of things that saying, Oh, this library that you're using is, is out of date. You're not using the latest one, but you know what, if I try it, trying to actively attack it and exploit it, it doesn't give it up, then like you said, Adam, it's, it's okay to sign off on that and say, yeah, that they.

[00:38:07] **Tim:** We know that's there. That's a hidden room inside the house. That's locked inside a cave, you know, with buried under 200 feet of concrete. They're not getting in.

[00:38:19] **Adam:** Yeah. I mean, I wish I could remember the details. I spent the last 30 seconds trying to recall this, but I can't. I, what I can recall is that we got an email from somebody from who was like a, you know, white hat hacking company. They were like, this is what we do. You know, we found this vulnerability in your app.

[00:38:34] **Adam:** and. We hope that you will be willing to pay us for it. Like they, they gave us all the details up front. It wasn't like a, a ransom type situation. You have this vulnerability. Here's the details, by the way, we're a company and this is how we make money. would you mind please paying us something, whatever you think it's worth for us to have made this discovery and, and tell you about it.

[00:38:54] **Adam:** And we did fix the vulnerability and we paid them, I think like three or 500 bucks or something like that. And yeah, I mean,

[00:39:02] **Adam:** I don't know what you do.

[00:39:03] **Ben:** what these people find. People are so freaking creative. I mean, I, I know that there is stuff that you can find with an automated scanner. But there's stuff that clearly took a lot of elbow grease where they're like, yeah, I looked at this network activity and I saw that this user ID was being passed in the URL.

[00:39:20] **Ben:** So I created this team over here. And then I added a different user to my team and I saw their user ID. And then I tried to take that user ID and substitute it over here. But I had to change these different permissions in order for it. And I'm like, Whoa, like I know how the code works. And that would not have occurred to me.

[00:39:37] **Ben:** And these people are just, it's amazing what they, what they figure out.

## [00:39:41] Is Computer Science Useful?

[00:39:41] **Adam:** You know what I think? This is, this interestingly ties to a topic that was kind of requested in our Discord recently, which was, Is it valuable to have any sort of, formal computer science education? Right. That's not exactly how the question was asked, but it was like, you know, when you're hiring, do you, maybe I should go look it up, but like, you know, you know what I mean?

[00:40:02] **Adam:** Like people applying without a computer science degree, like, how do you think about that? How do you feel about applying without a CS major or engineering? I think is how it was listed. And I think that coming from that formal computer science background, not necessarily software engineering, but computer science, like how computers work, how software works, can give you that perspective to, Be able to analyze or understand where these problems come from.

[00:40:27] **Carol:** Yeah. I feel like I rely heavily on the people I work with who have the CS degrees to better understand the back of everything that's happening. Like I can make it work. I can kind of understand what's going on, but when I get into some of the deep level, it just doesn't make sense to me because I don't have that, that information.

[00:40:45] **Carol:** Like I still lack that. So I rely on them to answer questions.

[00:40:49] **Adam:** For sure.

[00:40:50] **Adam:** I don't know. I have a CS degree and like my big takeaway is like nested loops are bad. You know, like that's, that's four years of education right there. as much as I remember of Spanish.

[00:41:04] **Carol:** Let's you know, degree's in IT, so I mean, I thought I was going to go into hardware. I thought I was going to be doing help desk, or I was going to be working a network admin kind of job. Like, I didn't know I was going to be going into software until I met Timmy Boy.

[00:41:19] **Ben:** yeah. And actually on that note, you know, if I had done more courses along the lines of operating system design, networking, compilers, I think that would have been actually way more valuable than taking. Algorithms and databases. And cause that's all the stuff that I learn at, on the job really anyway. And I don't have to have that background and how does an operating system work and how does a CPU work and what is, you know, like on chip caching mean?

[00:41:49] **Ben:** And like, you know, all of that stuff is just words I hear and it doesn't actually connect. But if I had been formally educated in that, I feel like I'd have a little bit of better, secret magic that I could have dipped into. When, when I was on the job,

[00:42:02] **Adam:** it sounds an awful lot like you're describing the difference between a software engineering major and a computer science major.

[00:42:08] **Ben:** Oh, maybe, yeah, that could be, I don't, I don't know where the lines draw cause I, I was actually, I applied to computer science through the liberal arts college at my university and I was somehow mistakenly accepted into the engineering school and they also have a computer science degree. And that's how I became an engineer. Cause I did, I was like, well, what's the difference? And they were like, well, you don't have to take a language requirement. Like you don't have to take French, but you will have to take four more credits in the engineering side of things. And I was like, done, sign me up. That's great. Done with French.

[00:42:43] **Tim:** Wee

[00:42:43] **Ben:** Yeah. but it was still very much computer science, even though I had to do things like digital logic and some, some like NAND and AND gate. Design

[00:42:53] **Adam:** man. Yeah. See, now you're getting into like my favorite courses from college. The one course that I never got to take that I was like expecting to have to take and, and excited for was, compilers, right? Like how to write your own compiler sort of situation. And I was, I was. Pretty, yeah, I was pretty disappointed that that never happened.

[00:43:10] **Adam:** but I did take like operating systems, file systems, discrete math. Like I took linear algebra and we, we wrote like, the math that makes a computer work, right? Like, you know, look behind and look ahead, like finite state machines, all that.

[00:43:27] **Carol:** Nerd, nerd, nerd, nerd,

[00:43:29] **Adam:** was so much fun. I still, I think I still have my, my linear algebra textbook on my shelf over here behind me somewhere.

[00:43:35] **Ben:** I mean, maybe I just took the wrong classes. You know, I took the classes I had to, to satisfy the degree. And then all of my electives were essentially geared towards web development. And if I had taken maybe more electives that were more hardcore, let's put that in quotes. You know, then, then maybe I would have had more long term value from them.

[00:43:56] **Ben:** I don't know.

[00:43:57] **Adam:** You should work your brain as hard as you work your biceps, Ben.

[00:44:01] **Ben:** To me, the, the most valuable thing in college was just learning how to be one independent and to work with other people. That was, that was like easing into the, to the work world. You know, when you're in high school, you just, it's just you and you're living at home and then suddenly you're in a totally different world and that was the most education,

[00:44:22] **Adam:** For sure.

[00:44:22] **Ben:** but

[00:44:23] **Adam:** Yeah, I mean, to go back to that question though, like, hiring people without, like a formal CS or even a software engineering degree, I personally don't have a problem with that. I think that, like, anybody can, have the aptitude for computer programming stuff without a formal degree. I think you're gonna have to You know, do the work to learn how it works, but like, you know, anybody can go to scratch.

[00:44:47] **Adam:** mit. edu and learn how programming works in conceptual Lego block style and then learn the syntax. It's not that hard, I guess. but like, I guess it's different things, right? So like, you know, anybody can get in the door, but I guess a degree will help you get into certain departments of the building of the computer science career will be a lot harder without a degree, right?

[00:45:16] **Adam:** If you want to get into like cyber security stuff, red, white hat hacking and red team, blue team type stuff. you know, that having those CS fundamentals I think would go a lot

[00:45:27] **Carol:** a long way.

## [00:45:29] Diversity and Inclusion

[00:45:29] **Carol:** And there's something too about diversity, right? Like it's great to have those people that have the CS degrees, but then I feel like I bring a lot to the table without having that specific knowledge taught to me. It's something I've learned over time. So I think that. Adding people without the CS degree helps, but I do feel like you need a few people that have the CS degree to make sure your architecture is set up correctly and that you have a solid foundation and a ground to build off on.

[00:45:58] **Adam:** Oh yeah, for sure. I mean, I was just, listening to a podcast now. I mean, not even 10 minutes before we got on here about, how, higher education in a way was started as a way to like re like recreate the class system. That was sort of like. You know, everybody, there was a equalization was happening, you know, people in the industrial revolution and stuff was, was all, you know, people were, were becoming more equal or whatever.

[00:46:26] **Adam:** And then, higher education happened as a way to be like, okay, well, if you have the ability to get into one of these schools, then that unlocks these potential futures for you that not everybody would have access to. So it, it again, creates this like social

[00:46:40] **Ben:** Yo, it, it, it's so fascinating. so I was listening to a, I think maybe it was Freakonomics a couple of months ago. And they were talking about how, symphony orchestras had started doing this blind tryouts where you would, you'd play a piece and you're behind a curtain or some sort of divider. And the idea is that the people there pick you solely based on your.

[00:47:04] **Ben:** On the way you sound and not on who you are, what you look like and what, what they have discovered now is that it really made no difference at all. And exactly to Adam's point, because the problem isn't that you're a woman trying out and I'm seeing you, or you're a person of color trying out and I'm seeing you.

[00:47:20] **Ben:** It's that 30 years ago, you didn't have all the advantages you'd need to reach the level of playing that we expect in this orchestra and that having a barrier. Doesn't change that to, to a significant degree. It's, it is, um,

[00:47:35] **Adam:** Yeah, it's not that that couldn't be a problem, it's that we're controlling for that problem well enough already.

[00:47:41] **Ben:** Yeah, it's, it didn't change it to the degree that they were hoping. And, and, and I think that's, you know, in the age here of diversity, equity, and inclusion, whatever we can do, I think oftentimes to remove gates from the application process is helpful. And if you can remove a CS degree, that just opens the door to more people.

[00:48:03] **Carol:** Completely agree. Yeah. Yeah, I like the, the process for hiring where the resumes have names removed, have their addresses removed, you know, so you don't have that information of he, she, they, them, or what street they live on to know their income bracket or like where they may be at financially. Remove that stuff.

[00:48:23] **Carol:** Don't have anyone Googling. Don't have them looking it up. Look at the resume, pick it off the resume and start interviewing.

[00:48:30] **Adam:** Yeah. Oh, it's, it's crazy how just like prejudice can come from anywhere. Like, okay, granted, I'm going to, I'm going to expose one of my own biases here. I live in Pennsylvania. Okay. I live in Southeast Pennsylvania and I think primarily from like sports, but you know, there's, it's all, the whole social cultural thing, we tend to kind of gentle, playful rib, New Jersey people just like, you know.

[00:48:58] **Adam:** Oh, oh, okay, you're from New Jersey, that's why you suck at

[00:49:01] **Ben:** I feel like the rest of the country does that also with New Jersey

[00:49:05] **Adam:** right, but like, you know, the most innocuous thing, right? Your home address happens to be from New Jersey, like, that just creates prejudice about you, potentially, right?

[00:49:15] **Ben:** I feel like Florida is the best thing that's happened for New Jersey.

[00:49:19] **Adam:** probably, but like, yeah, yeah, so, it was interesting going through this process with the, the co op program that I just did. I was, I, I went into it thinking, I have to come up with a system that is going to take my own personal biases out of it, I have to like, find a way to make sure that I, don't let, allow unconscious bias to, to make it so that 90 percent of the people that get through phase 1 are straight white males, because I'm a straight white male, and that's probably what would happen, right?

[00:49:49] **Adam:** Well, I got lucky, because for whatever reason, I think we had one white person apply for our job and like everybody else was a variety of other things. We had, we had women, we had, Asians and, and,black people and, and, Filipino and, and all kinds of like just everything.

[00:50:07] **Carol:** of diversity. Yeah.

[00:50:08] **Adam:** yes. And it was awesome.

[00:50:10] **Adam:** I was so happy about that because it was like fantastic. Now I don't even have to worry about my own biases. It's just because I just know that, that that's not even going to be a thing. So

[00:50:19] **Tim:** And then you, and then you pick the whitey.

[00:50:23] **Adam:** no, that did not happen.

[00:50:26] **Carol:** Yeah. Imagine trying to write a system that removes bias from hiring. Yeah.

[00:50:32] **Adam:** Yeah. Yeah. I mean, it was, it was difficult. I like, I, I, so I showed you guys that,form that I used. I sent to my coworkers to use as like a rubric for our interview process. and, you know, we have to pick the, the candidate so that I can filter the results appropriately. But, the whole point of that, of having that rubric was to just have some, to like, level set, right?

[00:50:52] **Adam:** So everybody's thinking about things in the same way, and none of it was anything that hopefully should have been biasable, right? None of it was like, do you like this person? It was all, can they communicate clearly? What is their strength with HTML? What is their strength with CSS, right? Like, their, their level.

[00:51:10] **Adam:** And, so yeah,

[00:51:11] **Carol:** Wait, they had to know HTML and CSS? I would not have made it through your interview. Let's just be rel.

[00:51:19] **Adam:** I mean, we didn't, it wasn't like, you know, name seven selectors that, that don't use it. I don't know, whatever. But like, no,

[00:51:26] **Carol:** I'm like, do I have a, do you not have a design team I could use for this stuff?

[00:51:30] **Adam:** nope.

[00:51:32] **Tim:** had to, I had to Google that. I couldn't remember how to, you know, you have a link that's an email address and you want to do them in the

[00:51:38] **Carol:** The mail too.

[00:51:39] **Tim:** I'm like, I can't remember how to do that. This is so bad. I'm going to have to Google that.

[00:51:44] **Ben:** Well, and it's funny too.

[00:51:47] **Ben:** They're there. I think I'm pretty sure I've talked about this before. but Seth Godin, who I've plugged his podcast so many

[00:51:53] **Adam:** Yeah. Nobody knows who he is.

[00:51:55] **Ben:** Seth Godin, Kenbo podcast, check it out. Anyway, he talks about a company or companies that do open hiring, which the way he describes it.

[00:52:03] **Ben:** Is there's just a list of people and you put your name on the list and when they go to hire, they literally just take the next name off the list and they put you through training. And if you pass training, you get the job. And I think there's like a, there might be a probationary period after that, but if you don't work out, then they just move on to the next person in the list,

[00:52:24] **Ben:** which is fascinating.

[00:52:25] **Carol:** expensive though.

[00:52:26] **Adam:** yeah.

[00:52:28] **Ben:** Plus also I do, I do wonder about, You know, people, people complain about what are the, what's the dating app? We swipe left and swipe right Tinder that it turns out that like men will go on and they'll just, I don't know which direction is the,

[00:52:43] **Carol:** Right. Rights to good.

[00:52:45] **Ben:** Yeah. They'll just like swipe right on everybody.

[00:52:48] **Ben:** So that any woman who swipes left becomes an automatic match. And then I wonder, do you, do you eventually just run into that same kind of problem where you just go and you put your name on every single list available and, and you're sort of polluting the, the ecosystem and taking away opportunity, but it's a fascinating idea.

[00:53:05] **Adam:** I mean, this isn't the hiring show, but that, that sounds incredibly expensive.

[00:53:10] **Ben:** Oh, I think, and I wonder if it only works for certain types of jobs. Like, I think the jobs that he was talking about are more,labor jobs where the training is more hands on kind of stuff. I'm not entirely sure, but, it's, I don't know. It's interesting.

[00:53:25] **Adam:** We take the specs from the customers and we bring them to the developers with people skills. Oh, well, it seems like we're pretty much at a good place to wrap it up. Anybody disagree?

[00:53:36] **Ben:** No, let's do

[00:53:37] **Tim:** Sounds

[00:53:37] **Carol:** no. No, good show.

[00:53:39] **Ben:** Let's, deallocate, the show.

[00:53:42] **Adam:** Dammit,

[00:53:42] **Carol:** Memory dump time.

[00:53:46] **Adam:** Oh, dammit.

## [00:53:47] Patreon

[00:53:47] **Adam:** Alright, this episode of Working Code is brought to you by listeners like you, because Ben already stole my good joke.

[00:53:55] **Carol:** Oh,

[00:53:56] **Adam:** And if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo, you guys rock.

## [00:54:10] Thanks For Listening!

[00:54:10] **Adam:** we are gonna go record the after show. it looks like we got a couple of things on the, on the list here. Something is broken. I think Carol, I saw your cursor down there, moving that one around. And Tim, of course, testicles.

[00:54:23] **Carol:** he is?

[00:54:26] **Tim:** No, I'm going to tell you what testicles, the type of testicles I'll be cooking this weekend.

[00:54:30] **Adam:** and if you, for some reason, want to put that in your ear hole, you can go to patreon.com/workingcodepod and give us some money and we will inflict that upon you. that's going to do it for us this week. We'll catch you next week. And until then,

[00:54:47] **Tim:** Remember, we officially mandated Your Heart Matters.

[00:54:51] **Adam:** nice.
