---
title: "101: Error - Error Message Not Helpful!"
description: "Tim has some very practical guidance on handling and presenting errors that he shares with us on this week's show."
date: 2022-11-16
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/101-error-error-message-not-helpful/id1544142288?i=1000586413952"></iframe>

Web application developers are notoriously bad about building resilient applications. All too often, we implement the "happy path" and then forget (or simply ignore) that _many things_ can go wrong for _any number_ of reasons. However, even if we do account for the "sad path", and we do catch and handle errors, it's not always clear how those errors should be presented to the user. Luckily, Tim has some very practical guidance on the matter that he shares with us on this week's show:

> Error messages sent to the end user need to have an appropriate tone, be free of tech jargon and shouldn't pass the blame. They say what happened and why, provide reassurance, be empathetic, tell them how to fix it (if possible) and give them a course for remediation (customer service, support ticket).

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/101-error-error-message-not-helpful.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** How about you, Carol? How do you, How you handle errors?

[00:00:02] **Carol:** Um, well, I just always assume the people using my system are smart enough to not do anything wrong and just let it live. You know, don't worry about

[00:00:10] **Adam:** that working out for you?

[00:00:12] **Carol:** I mean, I don't look at the air log, so I think it's great I don't look at Zend desk tickets that someone else's think. No, no, I'm kidding. I'm kidding.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 101. kind of starting over, kind of keep going, but, either way, here we are continuing on. today on the show we're gonna talk about error messages, cuz that's an evergreen topic, right?

[00:00:53] **Tim:** Mm-hmm. for sure.

[00:00:55] **Adam:** And, I guess as usual we'll start without tris and fails. And Ben, why don't you go

[00:01:00] **Tim:** Oh, before we getting try some fails, I just gonna, Is check in with everyone? Is everyone okay? After the Spice Tacular episode,

[00:01:07] **Carol:** We survived.

[00:01:09] **Tim:** eating all the hot wings

[00:01:11] **Carol:** I don't wanna do it again. Anytime soon,

[00:01:13] **Ben:** No, definitely not.

[00:01:15] **Carol:** I'll pass.

[00:01:16] **Tim:** I'm, I'm actually kind of considering trying to sort of like challenge my neighbor now that I have all the sauces right. I might as well. Throw it at him. you have any of Debo left? Because that's the one that,

[00:01:27] **Adam:** yeah.

[00:01:27] **Carol:** was bad.

[00:01:28] **Adam:** Yeah. I think I use less than half of the, the contain.

[00:01:34] **Tim:** So if you don't come on Discord for a show. So I was so concerned about Ben cuz he was in so much pain after de bomb. He was doubled over and I know how worried he gets. I, I was afraid because I woke up, I woke up the next morning and I, I love hot stuff, but I guess I eaten so much hot stuff.

[00:01:53] **Tim:** My stomach was still kind of burning and I thought, Oh my God. I bet Ben, I bet Ben thinks he has like a bleeding ulcer or something and has gone to the emerge. So I'm trying to message him. I called him like two times. He didn't, he went straight to voicemail. I'm sending him text messages on Discord. I'm sending him message, he's not responding.

[00:02:10] **Tim:** I'm like, Oh my God. He's like in the hospital or something.

[00:02:13] **Ben:** I,

[00:02:14] **Ben:** I appreciate the concern.

[00:02:16] **Tim:** and then, and then about like later in the afternoon, I get this, me get. This message on Discord from men. He goes, Hey, why'd you call me two times in a row? What's up? I'm like, Okay, you're alive. Just making sure that you're okay. And he's like, I know.

[00:02:29] **Tim:** I took the day off. I had the, you know, took the day off today. And I was, you know, I wasn't answering my phone or anything. I was kinda away from everything. I'm like, Okay, okay, cool. Just making sure you're alive, dude. Cause I was seriously, like, all of us, Like Adam was like, Hey Tim. Ha, are you calling Ben?

[00:02:42] **Tim:** Because I don't wanna keep calling 'em too, if you're calling him. I'm like, No, I'm take, I'm, I'm calling

[00:02:46] **Carol:** I, I went on to Facebook and added his wife as my friend. I was like, Ed's wife real quick. Let's message her. for about that time. Ben responded and said, What's up, you guys

[00:02:59] **Ben:** I know I was scrolling up in the chat and I'm like, What are they even talking about?

[00:03:04] **Carol:** The next message is we thought you were dead.

[00:03:08] **Tim:** We thought you were like, checked yourself into a hospital, like or something. The. But, but seriously, you handle it like a champ buddy. For this person who like really doesn't like spice you, you, you did well, you did really well.

[00:03:21] **Tim:** Should be proud of yourself.

[00:03:22] **Ben:** I was pretty surprised at how terrible the bomb was

[00:03:25] **Carol:** It's

[00:03:26] **Tim:** Hmm.

[00:03:27] **Ben:** I was also a little surprised that I didn't throw up. There was a moment there where I thought I was gonna throw up

[00:03:31] **Tim:** Which would've been worse.

[00:03:34] **Ben:** and then it stuck with me. I was uncomfortable until the morning-ish, like seven 30 the next morning I was laying there on the couch.

[00:03:40] **Ben:** I'm like, Oh, this doesn't feel great. But then it, then the sky's parted and, uh, the pain dissipated. And, I had, I had a lovely Friday.

[00:03:48] **Tim:** Awesome. Okay. All right. Start with that detour.

[00:03:51] **Adam:** That's okay. I meant to, I meant to take us there too, so I just, I got sucked into the routine and completely forgot about it and I'm glad that you thought to say something. So now as usual, let's get into our TRAs and fails. And Ben, who is definitely alive uh, not a machine learning algorithm who hates testing and react. Uh, why don't you go first?

## [00:04:11] Ben's Triumph

[00:04:11] **Ben:** I just gonna say, I think, was it you who recommended Resident Alien? The show a while back?

[00:04:17] **Adam:** I think that might have been Tim. I feel like I learned about it here on the

[00:04:19] **Ben:** Somebody recommended he, that's, that's like kind of a mannerism he has on the show all the time where he's like, I'm definitely a human being with regular human hands. All right. I'm, I'm gonna go with a triumph failure, or I'm gonna go failure come Triumph. which is that I looked over at my MacBook Pro 2015 this morning, and I noticed it's in a, it's in a, it's sitting closed in a little clamshell.

[00:04:45] **Ben:** Holder and, Yeah, yeah, yeah, exactly. So I look over it this morning and I noticed that the cover is, is is away from the body. And I'm like, oh, that's not good cuz I replaced the battery on my, on the 2015, like a year and a half ago or something cuz it had started to swell. So I looked, I took it out of its case and indeed again the battery is starting to swell, which is terrifying cuz you apparently can, you know, catch on fire and stuff.

[00:05:11] **Ben:** So that's the failure. But then the triumph there is that, as I've maybe mentioned before in the show, I actually bought a new. MacBook Pro 2022 Apple M one, like in August. And I still had not gotten it set up for work because of all kinds of issues. so I took the day and I kind of rounded out the rest of the configurations and I was able to get the, the 2022 M one to a point where I was actually able to file a pull request and, run my system locally.

[00:05:44] **Ben:** So I feel pretty triumphant about that. That's, that's like actually a tremendous amount of weight off of my shoulders. Cause I feel like I can now really start to adopt the new machine. and I'll tell you for everyone on Twitter and Facebook who's like, I don't, like Docker just works on M one.

[00:05:59] **Ben:** I don't know what you're talking about. It's just been so many hurdles. one of the steps in our docker file is installing Node 10 x, which node 10 x like hasn't been supported in like nine years or something, but hey, that's what powers Gulp three. And, apparently you can't even install . You can't even install Node 10 anymore.

[00:06:18] **Ben:** and fun fact, Gulp three doesn't work with anything higher than Node 10 because it monkey patches the node file system. So I had to, it, it was just like, it's just like a lot of trial and error in getting things to work. But, uh, I, I'm at the point now where I can do work. the downside is that my system is not a exact mirror of what goes to production, which is kind of terrifying.

[00:06:40] **Ben:** Like I have a slightly new version of, Lucy Cfml running locally and I have a slightly newer version of Rabbit mq and I have a slightly newer version of, a couple of things I'm sure like, because I basically, My entire docker file, cash layer, everything was invalidated because I had to start building new stuff from the top.

[00:06:59] **Ben:** So I'm sure every app get install installed completely new

[00:07:04] **Carol:** New Persians. Mm-hmm.

[00:07:05] **Ben:** So, so that's terrifying. I'm like, now it's just gonna be a crap shoot. It works on my machine. Does it actually work in production? But, hey, I will cross that bridge when it starts throwing errors in production but I'm calling it a Triumph so that's me. Absolutely. But I am gonna go to Best Buy tomorrow to see if they can, help me replace the battery on the 2015. Cuz there is still stuff on that, that I want slash need and would be a pain in the butt to get off of a backup. But, yeah,

[00:07:36] **Tim:** so you have to turn in your old laptop when you're done with.

[00:07:39] **Ben:** Uh, I don't think so. I mean, no, I don't, if I were to. They probably want something back, but as a matter of course, they don't ask for the computers back anyway. That's me. Carol, what do you got going on?

## [00:07:57] Carol's Triumph

[00:07:57] **Carol:** Hi man. I'm gonna go to the Triumph. I have, started working out again. I actually started last week with like the before workout week, which is a lot lighter routine and just kind of getting back in the hang at things, but working out again, following a schedule. And I'm just kind of getting my life back to normal with like up bedtime and time I start making coffee and the time I start working.

[00:08:21] **Carol:** Because having my schedule completely out of whack has not been good. And it also makes me be less productive during the day cuz I just feel like I'm spinning in circles trying to catch back up for the missing time. So I'm just happy to say I'm getting back on schedule and day and nights are normal and yeah, working out

[00:08:41] **Ben:** Heck.

[00:08:43] **Carol:** Yep.

[00:08:44] **Ben:** I'm

[00:08:44] **Ben:** all about schedule.

[00:08:45] **Carol:** Yeah. Schedules are good.

[00:08:47] **Carol:** So about you Tim?

## [00:08:48] Tim's Fail

[00:08:48] **Tim:** Yeah, so I forgot to work. Yesterday morning that makes like 20 years in a row. So, so I, I'm have to break our little triumph train here and go with a fail.

[00:09:00] **Carol:** no.

[00:09:02] **Tim:** Yeah, unfortunately. So I, I, I've had, I had a, this is used to kind of be my job before, like, before I moved over to payments where I was always like cleaning up data cuz stuff was breaking. And I had that day today and it was, did not feel good.

[00:09:16] **Tim:** I spent the whole day just doing like data cleanup kind of stuff in the same time trying to take meetings while I'm also kind of looking at the data outta the corner of my eye. and it

[00:09:25] **Tim:** was exhausting.

[00:09:27] **Ben:** where are you? cleaning data up? Is it like in Excel files or in

[00:09:30] **Ben:** a

[00:09:31] **Tim:** sql, so it's in database. So we have a, a customer, they're kinda like a one off kind of legacy kind of customer.

[00:09:38] **Tim:** They have their own specialized process. They, they do, it's a life insurance company and they. Do a lot of payments like on the second and third day of the month because most of their, people are, on social security and they're using their social security little credit card that they get from the government to, to pay all their, their bills and stuff at the beginning of the month.

[00:10:00] **Tim:** And our client wants to like go as soon as possible and try to get that money because it's like, seems like on the third, second or third of the month, like everyone's going in, getting their card. So if it, and when it's empty, it's empty. It's like, so they, they wanna get that as fast as possible and it runs one of these processes that runs absolutely perfectly most of the time.

[00:10:20] **Tim:** But today it just, it fell over. I, I think the, the credit card process that we were talking on the back end didn't respond quickly enough. And that kind of set off this cascaded. And what sucks is I really have as much logging as I have. I really don't understand why it did what it did. And so, Was having to clean up, you know, basically rerunning some of the, some of the payments that failed, but then they got wrong policy numbers on them, so I had to go clean those up so that like, the reporting worked and just, yeah, just spent all day and it's like, it's like 6:00 PM I was done.

[00:10:56] **Tim:** I'm walking away from my computer. I realized I hadn't gotten up from it all day, pretty much. And that used to be my life. That used to be, you know, pretty much what I did day in, day out. I was like, Oh man, I, I have not missed this at all. And I I gotta figure out a way to, to put some better logging in on that so that, if this happens again, I can figure out why the underlining cause is and stop it from happening.

[00:11:23] **Tim:** And then on a personal life failure, So last week I didn't bring this up in our show cuz we were having a good time eating hot wings, but last week my grandmother died.

[00:11:34] **Carol:** Oh, no,

[00:11:36] **Tim:** Yeah. She, I mean, but she was 96 years old. I mean, she really, you know, 96 years old up until a month ago, she was living on her own, or li at home.

[00:11:46] **Tim:** Right. She went

[00:11:46] **Carol:** Oh.

[00:11:47] **Tim:** Yeah. And so, yeah, I mean, she, she lives a very full life. She was an amazing woman and just really, I mean, just such a talker and the life of the party and just, yeah, she was, she was amazing, but it's like the last few years she'd had a stroke and, you know, she really couldn't talk too much.

[00:12:04] **Tim:** So it was just, it's kind of sad to see her kind of there. So, as sad as it is that she's no longer with us, it's, you know, at the same time she hadn't been with us for a little while. So, yeah, So,

[00:12:15] **Tim:** we got a funeral, we got a funeral coming up on Saturday and. Sad to say is actually pretty awesome. Cause I get to see cousins and second cousins that I haven't seen for 20 years.

[00:12:24] **Tim:** So it's like everyone's coming in and it's like it's gonna be a huge party. So I'm really looking forward to the weekend. I'm really looking to the, It's be a blast.

[00:12:32] **Adam:** Bitter.

[00:12:34] **Tim:** Yeah, it's bittersweet. Bittersweet. Love you, Grandma will,

[00:12:37] **Ben:** I, I mean, dying in your nineties today, The, just the, the life, the, the world changes that she lived through. Mind-boggling. I mean, world Wars and many other wars, unfortunately, and the internet and awesome television. I mean, just, it's crazy.

[00:12:56] **Tim:** Yep. So that's me. How about you, Adam?

## [00:12:59] Adam's Triumph

[00:12:59] **Adam:** I'm gonna go with a triumph. I, I mentioned last week that I'd had a rough week and, you know, a lot of, a lot of issues going on and things have calmed down a bit and I've been able to, you know, when things come up, just kind of take care of them, put them to bed, and, and go back to the thing that I've got as my primary objective right now, which is working on, some spell code, which is a lot of fun and I'm really enjoying it.

[00:13:22] **Adam:** learning. And I mean, I'll, I'll say right now, you know, this code that I'm writing is garbage. You know, it's, it's terrible, but I'm, I'm intentionally going into it that way, right? Like I'm, I'm trying to learn, the right way. If there is an idiomatic way to writes felt, I'm trying to, to learn the ins and outs of that.

[00:13:38] **Adam:** and I'm choosing to just kind of put, it's a, it's kind of a, I would say on the large end of small scope, right? It's a, it's a single like modal dialogue, but it has a ton of functionality within it. so you could say it's, you know, one small component, but there's a lot of functionality in here. And, so I'm choosing to write it all in one big's fault file and like get it all working and then like, I'll be able to just commit that once it's done.

[00:14:01] **Adam:** I'm, I'm doing commits along the way too, but when I get to that point where it, where everything that I need it to is working and done and, and I'm happy with it, and then I will go back and I will make the code clean. and I'm actually kind of hoping that I'll be able to like talk somebody who has a bunch of felt experience into like, Pairing with me on the refactor and kind of teach me like, okay, here's a here's how you wrote some bad code that's like, you know, non performant or something like that and, and how to make it better, but also b, like this is the, the right way to organize this code.

[00:14:31] **Adam:** That would be awesome if I could find somebody to do that.

[00:14:34] **Ben:** Yeah.

[00:14:35] **Carol:** Tim, I mean, he's been learning it. There you go.

[00:14:39] **Adam:** he

[00:14:39] **Carol:** tired.

[00:14:39] **Adam:** learning it. Yeah. He had, uh, one of his, not juniors, but, reportees, I guess one of his employees, looking into it. that's all I got.

## [00:14:50] Error Messages

[00:14:50] **Adam:** Okay. So our, our topic today is error messages. And I guess we just thought we would talk about what makes a good error message, what makes a bad error message,

[00:14:58] **Tim:** When to throw an error message?

[00:15:00] **Adam:** Yeah.

[00:15:01] **Tim:** Yeah.

[00:15:02] **Adam:** We'll see where this takes us. I'm sure that there's plenty to talk about here. So who wants to go first?

[00:15:06] **Tim:** Well, I'll say, I mean, this was, I suggested this topic because I had put in our little notes to self that Ben does. I don't do as many as he, he does, but so, so I put the error messages sent to the end user. Need to have an appropriate tone. That's one. Be free of tech jargon. That's two. Shouldn't pass the blame.

[00:15:27] **Tim:** That's three. Say what happened and why. Four, provide reassurance. Six, be empathetic and tell them how to fix it if possible, and give them a course of remediation.

[00:15:40] **Adam:** You skipped five

[00:15:42] **Tim:** Yeah,

[00:15:42] **Adam:** You went from four to six.

[00:15:44] **Tim:** I mean, I'm from George, I can't count that high.

[00:15:48] **Ben:** this is great, but this is, a hard set to adhere to

[00:15:52] **Tim:** Right? I mean, I, I do, I think this is sort of a, a goal to attain, right?

## [00:15:55] Appropriate Tone

[00:15:55] **Tim:** So I'll say initially that when, when I first moved over the payment side of the, the, the company, they had a, an error message, a custom that obviously someone spent a lot of time on, right? And it was like a, a pencil drawing of Charles Dickens, and it says, What the Dickens, It's a ColdFusion error.

[00:16:18] **Tim:** And it's like, it really, it was just silly and it didn't give any actionable information, didn't explain anything whatsoever, and just says someone's looking at it.

[00:16:27] **Carol:** Not helpful at all.

[00:16:29] **Tim:** No, not a help at all. I'm like, All right, stop that. Immediately, take that down. Right now we're not doing that. I mean, because last thing you want, you get an error is just someone going, Ha ha, ha.

[00:16:43] **Tim:** You got an error in our stuff that we wrote, but it's an error and it sucks for you, so bye

[00:16:51] **Ben:** I've been guilty of that as well. We actually, years and years ago, when you entered the wrong username and password too many times, there was like a, you could do it 10 times or something within an hour. And the message, the rate limiting message essentially that I would put up was, you, you poked the bear one too many times

[00:17:10] **Ben:** and I

[00:17:10] **Ben:** just

[00:17:11] **Tim:** it's blaming you. It's blaming the user.

[00:17:14] **Ben:** cause I just sort of assumed like, who's gonna forget their password 10 times?

[00:17:17] **Ben:** So I, I assumed this message was gonna be primarily shown to people who were trying to do something malicious, which is why I didn't really think too much about the attitude. But, apparently a user who doesn't know their password will gladly enter many passwords trying to figure out what it is. And, we got many a zenes ticket being angrily asking us to change the tone of our error messages.

[00:17:40] **Carol:** Yep.

[00:17:41] **Carol:** Mm-hmm.

[00:17:43] **Tim:** And I, and I bet you, I bet you your login said wrong. You know, user credentials or something, please try again. And they're like, You told me to try again. I tried again 10 times. I mean, to be fair, I had an issue with the Google. We had, I set up a Google business account and we had like a, some Google voice, numbers associated with it.

[00:18:02] **Tim:** I was trying to add a new user. That's all I was trying to do. We had a new guy, he came on. I didn't wanted to give him a phone number, so I'm adding him a phone number and it goes, added him, and it's like there was issue setting up the phone number. Please try again. So I did five times and then they banned my account the entire, and there was no, and their whole recourse platform is so terrible.

[00:18:23] **Tim:** I'm like, Please tell me what I did wrong. They're like, No, you, you broke, you broke one of these rules, and they give you this page of like 15 to 20 things. And like, it could be any one of them like, Well, which one? Like, you broke one of these. I'm like, I, You told me to try again. I tried again five times and then you just shut my account off and then kept billing me for three months.

[00:18:42] **Ben:** Yo can I, if I, if I can do side ran here on a related note at the

[00:18:46] **Ben:** self checkout counter, at the, at the supermarket. I don't know, I assume everyone has self checkouts where they are.

[00:18:53] **Ben:** Um,

[00:18:53] **Tim:** yeah,

[00:18:54] **Ben:** I will go and I'll start checking out my stuff. He's usually, you know, like 12 items and under kind of a thing. And at some point it'll just say, Please wait for assistance.

[00:19:04] **Ben:** And someone has to come over and they do like some bloop, bloop, bloop on the screen. They swipe their, their, you know, employee card and then they walk away. And I have literally asked them, I'm like, What did I do so that I know not to do it again because there's no error message on the screen at all. And they're just like, Oh, don't worry about it, and walk away.

[00:19:20] **Ben:** And I, and I drives me so crazy cause it's not telling me what I did wrong and I have no idea how to not do it in the future.

[00:19:29] **Tim:** yeah, yeah. So having an appropriate tone I think is really important with, with your error message. we talked about, you know, some bad tones, but I think you need to provide reassurance in your air message, right? So, Let's say that you do something and you're trying to save something and it, and there's an error, and then you say there's, you tell them there's an error.

[00:19:50] **Tim:** Well, is my stuff saved? Do I need to do it again? And there's like just maybe an okay button. What does the okay mean? Am I, am I, am I recent? Particularly if it's like financial, Am I resubmitting again? Am I, is it resubmitting or is it canceled? I mean, explain to me what, what this error means in the process of, of give me some reassurance that I'm not by clicking something, I'm not doing further damage to myself.

[00:20:19] **Carol:** Yeah, I feel like I usually find the, it's either far left or far right? Like I get the, something went wrong, please try again. Or it's the error online 10 times. Put a bunch of numbers semi invalid like in able to like map object and it's like some data type at the end. And I'm like, well that helped me.

[00:20:40] **Carol:** None

## [00:20:45] Technical Jargon

[00:20:45] **Adam:** so I, I think That,

[00:20:46] **Adam:** a couple of these are kind of at odds with each other, right? So you have, Don't be free of tech jargon, right? But then you also say, give course for remediation customer service or support ticket. And I, I believe they can coexist, but I think that the way that we try to do it is, you know, we try to, if, if we can, if we can predict this way that the application will fail, then we will explain the situation or do our best to explain it.

[00:21:12] **Adam:** And then at the bottom of that error message, we'll put like a little notes, like, details for the nerds. Like, here, put this in your support ticket. Right? And then we give the whatever useful error message might, might be in there. And I mean, the truth of the matter is that 99 times out of a hundred, we've already logged that error message to our

[00:21:30] **Carol:** Right. It's already there. Mm-hmm.

[00:21:33] **Adam:** yeah. But at least it'll help correlate their ticket to the bug report.

[00:21:38] **Tim:** Well, I mean, I, I, I think what I meant when I talked about big free of tech jargon is, you know, saying there's the five 16 error.

[00:21:46] **Carol:** Nobody knows what that

[00:21:48] **Tim:** Right. Or, you know, there was another message that we used to have. It was like a teapot error. Now if, I mean, if you're in tech, you probably know what a tea, Yeah, yeah.

[00:21:58] **Tim:** Four 18 a teapot era. You know what that is? You have a WF or something that's blocked the blocked it, but I mean, people will put in a ticket and go, What do you mean a teapot era? My kettle is not even on what? Right.

[00:22:12] **Tim:** So I would say tech jargon with that regard, what I do, like, what I do like is whenever you just give them a, what I'll do is kind of hash the error message and take that hash and display it and say, Here's your error code.

[00:22:25] **Tim:** This is an error code. please, you know, Report this to, this has been reported to our support team. you can use this as a reference, you know, to find out the status of it. so I, I think that's a good message. and also explaining, you know, also if, you know, if you want them to call customer service or put in a support ticket, things like that.

[00:22:42] **Tim:** Or even like maybe a, a link to a knowledge base. Let's, let's say it's a, they did something wrong that caused this error and you for some reason know about it, you can give them a knowledge base reference that they can go to and look at and to see maybe they can fix it themselves. I don't have a whole lot of those.

[00:22:58] **Tim:** Usually they're just hard errors.

[00:23:00] **Adam:** The thing that's been biting us a lot lately is, so I've talked a little bit recently about how our current production databases don't support emoji in text fields and how that will be changing soon. but, it, it's been happening with increasing frequency that somebody will try to include an emoji in some, you know, in their support ticket comment or in an email subject or something like that.

[00:23:20] **Adam:** And it just, I think it's, the database just kind of like throws up its hands and it's like, error. I don't know what to do with this.

[00:23:26] **Ben:** Yeah. It's like incorrect character set.

[00:23:28] **Adam:** Right. Yeah. The, the error message that we get back from the database is not always the same. I think it might have to do with the type of column that they're trying to insert it into, and then it doesn't, there's nothing about the error message that says like, you know, invalid input or anything like that.

[00:23:43] **Adam:** It's just random garbage. And so it's, I think it would be exceedingly difficult for us to catch these and say like, Oh, okay, you, you put in some texts that we don't support sort of thing. So we have been dealing with those tickets. I'll be very glad to get that monkey off our back. That monkey emoji. I don't know off our

[00:23:59] **Carol:** Yeah,

[00:24:01] **Ben:** Yeah. We, we have some workflows like that where we. We run it through this thing that finds the very high KY characters. So the, so the not all emojis fail inside of the old UTF eight encoding. It's like only emojis that are in the, the astro plane, whatever that is exactly. I don't, I don't quite know. so it's like, I think a regular smiley face will work, but like a poo emoji will break, or like a snowman emoji will break and like a bunch of others.

[00:24:31] **Ben:** and, and, we'll we have this method that we call that we'll pass some of our strings through that that looks for certain hes and coatings, like anything over a certain, unique code value. And it will like replace it with a question mark, which, you know, is a terrible user experience. But to your point, if you don't do that, it just blows up and gives nothing helpful.

[00:24:53] **Carol:** Yep.

[00:24:54] **Ben:** to be fair, we do do in a lot of cases, I'm not saying we're good all over, but in certain, in certain scenarios, we, we try to fix it somehow.

[00:25:02] **Adam:** Yeah, actually I'm, I'm, very familiar with the code that you are talking about because I stole it off your blog and I tried to implement it at one point, and I think we might, like, I tried to, this is how, how, annoying this problem is. I am almost certain I put it in like application CFC in like on request start or something to just all form inputs, clean 'em up, you know.

[00:25:24] **Adam:** and I, I feel like I had to pull that out for some reason at some point. I dunno if it was performance or, or what, but yeah, I know exactly what code you're talking about.

## [00:25:34] Security

[00:25:34] **Tim:** How about you, Carol? How do you, How you handle errors?

[00:25:36] **Carol:** Um, well, I just always assume the people using my system are smart enough to not do anything wrong and just let it live. You know, don't worry about

[00:25:44] **Adam:** that working out for you?

[00:25:46] **Carol:** I mean, I don't look at the air log, so I think it's great I don't look at Zend desk tickets that someone else's think. No, no, I'm kidding. I'm kidding. We don't, I feel like, we try our best to give back enough information that we don't expose too much of the technology, right?

[00:26:03] **Carol:** Like, I don't want you to know that you have a valid user, but you don't have a valid password, right? So like, just a simple example, like, but I will return back to you that what you've entered doesn't match somewhere, right? Like, we can't validate you, try again. but when it comes to like the, we are in the system working and there's a code error, then we just returned back, hey, during this process, this is the step that failed.

[00:26:34] **Carol:** So, you know, during approval, We weren't able to get documents and something happened. So submit a Zendesk ticket with this link. Provide the property you were on and what document like you were trying to retrieve. So we give them information to put in the, the ticket as well. So when the ask does come to us, the ask is more clean, right?

[00:26:56] **Carol:** So it's not just, it's an error and I don't know what happened. At least this way when the engineers get it, they have some, context to what was being done, on the user, like by the user during that time.

[00:27:12] **Tim:** That's good.

[00:27:13] **Ben:** Well, one thing that, Carol said that made me think about error messages from a security standpoint that certain, compromises have to be made in the name of security. So from entering credentials as an example, you don't necessarily want someone to perform an iteration attack and iteration attack.

[00:27:31] **Ben:** I think in this case would be they're just trying a bunch of random, emails, for example. Until they get one that says like, Oh, the email was correct, but the password was wrong. and then they say, Okay, well now I've identified a valid email within the system. So you can't tell them that their email's right and their password's wrong.

[00:27:47] **Ben:** You just have to tell 'em that their credentials are wrong, and you sort of have to hide which one it is, not because it's a good user experience, but because it's hiding a, a vulnerability

[00:27:58] **Carol:** You don't want them to know.

[00:28:00] **Tim:** The absolute worst thing you can do. because we're doing payments for other people and they, they put our code in their systems. A lot of times we'll get an error message, a screenshot or something from a user, and it's just, it tells you the line number. It tells you the part of the code that air, I mean, just, that is just food for hackers, right?

[00:28:20] **Tim:** There.

[00:28:21] **Tim:** Do, do not, Yeah. That, yeah. That says, Hey, you just, you just exposed your, your underbelly when you do that. So, and honestly, it's like, They send it to me and I'm like, like, Oh, this, this payment didn't go through. I'm like, Look at this error. And I'm like, Good at the error. And it's like, Yeah, that's your ASP code.

[00:28:39] **Tim:** I have no clue. I mean, that means nothing to me. So send it back to the system that you were, you were trying to make the payment on because their, their stuff broke. I have no idea what line 10,000 on a S P X, whatever is, is, is airing on because yeah, that means nothing. So don't do that. Don't do that at all.

[00:28:58] **Tim:** That, that, that is a huge security risk.

## [00:29:01] Form Validation

[00:29:01] **Carol:** Well, one silly one that gets me every time. If I'm on a, like on a site and I'm filling out a form, right? So I've went through and put in my name, my date of birth, but I forgot something like on my address or whatever it was. If I hit submit and you've returned back to me that I have an invalid input and you only tell me like one of my inputs is wrong and I hit submit again, and I'm missing another one, I'm furious.

[00:29:27] **Carol:** At this point, I'm like, I don't wanna use your site. I'm done. I'm off of it. I'll go register somewhere else. I don't like you anymore. Like validated all. Give me it all. Let me handle it one time and fix it. Like, don't make me keep going. Click, click, click. That's, that's frustrating.

[00:29:44] **Tim:** Mm-hmm. , I've seen sites where you will fix it, but it will still, they'll give you a red. Right. So it'll be red. The, the input box will be red with something saying, you know, Correct. This, you correct it, it doesn't change color. And you submit it and it's like, Yeah. It just, that's just annoying.

[00:30:02] **Adam:** You talking about like real time, you know, so you're, you're, creating an account and that your password wasn't long enough or whatever, and so you go and you,

[00:30:10] **Adam:** you you type it. And so as you're typing the, the best experience will be like, Okay, once you get to the minimum length, the error goes away

[00:30:17] **Adam:** as you're typing.

[00:30:18] **Carol:** good. Mm-hmm.

[00:30:19] **Adam:** But you're, So that's what you're saying is you'd, you'd like to see, Okay. Yeah.

[00:30:22] **Adam:** So it's like they're only

[00:30:23] **Adam:** doing server side validation.

[00:30:25] **Tim:** I'm sitting there like, Okay, what, What password do you want here? I just, You said I needed an uppercase character, lowercase and a number and a special character, but one of those characters can't be a pound sign, so, Alright. And I fixed that. It's still red.

[00:30:41] **Tim:** I'm like, I don't know what's gonna happen here.

[00:30:43] **Adam:** gotta turn green and plus outta your shirt.

[00:30:46] **Tim:** Yep.

[00:30:47] **Carol:** I have a silly like validation thing. It's not about errors, but I use one password for everything and it drives me crazy when I'm on a site and I hit auto feel and the password or the username requires a physical click to be activated. Like I can't click login or I can't click submit because it requires me to click on the input and I have to like click in there and then click out.

[00:31:10] **Carol:** I'm like, Oh, why Why just take it empty and then tell me it's wrong? Right? Like,

[00:31:19] **Adam:** Talking about one password, things that are frustrating. This is not one password's fault, but I think it was, I was booking up a flight and I had to put in my credit card information right to, to purchase the plane tickets and the form for the credit card, like the expiration date, it had a dropdown for month, right?

[00:31:35] **Adam:** So you have month and year you have to do, and so you've got 12 possible values in there from one to 12. Well, it wasn't working. It told me my credit card was invalid, and I'm like, how could that possibly be? I use this credit card all the time. I'm filling it using one password. How could it possibly be wrong?

[00:31:49] **Adam:** Well, I happened to be a web developer, so I was able to look at it a little bit. I looked at the source code there, select for the month field was, so like January, the, the label for that option in the select was one, but the value was zero and February was value. One label. March was Value two Label

[00:32:12] **Carol:** Oh, I

[00:32:12] **Adam:** I'm like, Are you freaking kidding me?

[00:32:14] **Adam:** So it was selecting the wrong

[00:32:16] **Carol:** How, Yeah.

[00:32:18] **Tim:** Um,

## [00:32:19] Passing The Blame

[00:32:19] **Tim:** so here, so here's one that I struggle with. So I talk about that in that my little note to myself, there shouldn't pass the blame.

[00:32:27] **Ben:** Hmm.

[00:32:28] **Tim:** So, we deal,

[00:32:30] **Adam:** User is idiot.

[00:32:32] **Tim:** no, not, no, I don't mean blaming the, the user in our, in our worlds, like we're, we're sometimes the victim of, we send a payment request to, you know, a, a payment processor and for some reason, Visa, MasterCard just doesn't get back to us in time, right?

[00:32:49] **Tim:** and so it's really hard to write an error message that basically says, I don't you, you don't wanna blame like some third party that says, Oh, so and so's, API wasn't, you know, didn't return in a timely manner, therefore this timed out or an error from whatever. But it's like, it's kind of what happened,

[00:33:09] **Tim:** right? You don't wanna make it sound like, Hey, someone else screwed up. It's not our fault, not our problem. Walk away, right? So you need to take some responsibility for it because, I mean, you're, you're, they're using your product. They're not using whatever products you have, like baked into your, to your code, whatever, APIs and things.

[00:33:29] **Tim:** So that, that's kind of a hard one for me to, to write. I try to just basically say that, you know, there was an issue, here's here's the ticket number and you know, we're working on it. if there's nothing they can actually do on it, just say, Yeah, I don't know. I struggle with that one because

[00:33:45] **Adam:** Please wait by your mailbox for further information.

[00:33:48] **Carol:** Try again in an hour. Like it's easy to like put a rate limit, error message in, right? Like, okay, we've hit something too many times. We are going at this too fast. Whatever it is. Like, okay, come back in an hour, try it again an hour. If you want to put in a ticket, put in a ticket, that gives them the ability to kind of just wait for your connection to be fixed with this third party.

[00:34:10] **Carol:** Or they can just put in a ticket and you can notify everyone who submitted a ticket about not being able to connect all at once, once the connection's back up.

[00:34:18] **Tim:** Yeah. Yeah. I mean, if it's a, if it's a, an API that sort of has a status uptime kind of thing, they'll say, You know, we know that you hit this error because this system is down right now, some process that we're calling is not available will publish the link and say, you can't do this right now because this is down.

[00:34:40] **Tim:** Here's the link to check the status. Next, you know, check when you check the status and say that it's up. You can resubmit your, request and your request, you know, and assure them that you haven't already done the transaction that you've done. You can do it again without fear of duplicating, the same twice. But that's a lot of work.

[00:35:01] **Adam:** Yeah. Yeah,

[00:35:03] **Tim:** That's a lot of work.

[00:35:04] **Ben:** and things can break at really weird times too, and it's not always clear in the workflow what's breaking.

[00:35:10] **Tim:** All right?

[00:35:11] **Carol:** So,

[00:35:11] **Tim:** some, and sometimes they're up, but they still throw an error.

[00:35:15] **Carol:** um, do you guys use any budgeting software at all? Like anything to help try? Oh, just

[00:35:21] **Adam:** Actually, Google Sheets now used to be Excel. Excel.

[00:35:24] **Carol:** use, I use, you need a budget. Like I've been using it for several years. I love it. One of the things that they have is this really cute, I say cute cause I like it. Cute status page. So if, I have this gear icon next to my American Express card, it's like, Oh, I'm not able to get the transactions.

[00:35:41] **Carol:** Like, here's why I'm not able. And it pops up exactly what Tim's saying. It's like, here's all of our connections that are currently good or that are currently failing, and here's what's going on. Like if you go right now, it says, Oh, we're updating, or like, we're investigating a problem with connecting the Kohl's credit cards.

[00:35:57] **Carol:** So if you have a Kohl's card, your transactions aren't coming through. And here's why. I think giving them that visibility, like you were saying Tim, is, is very helpful when you have a lot of public facing users who are asking the same question. So,

[00:36:12] **Tim:** hmm. That's good. I, I, I think having your branded page rather than just sending 'em to their, because otherwise you're exposing what APIs you're using is better, way to go.

[00:36:23] **Carol:** Yeah.

## [00:36:24] Personality

[00:36:24] **Adam:** So, sort of on the same topic, how do you guys feel about error pages with, let's say, personality? . So I'm thinking of, I'm thinking of the fail whale, right? Twitter in its, in its early days

[00:36:37] **Adam:** would go down and you'd get the fail whale.

[00:36:38] **Carol:** Mm-hmm.

[00:36:40] **Adam:** Yeah. I, I mean, personally I like it. I would rather that than, you know, just a, a plain text page says, you know, 500 we're, we're broken.

[00:36:50] **Tim:** I I think Twitter,

[00:36:53] **Tim:** Well,

[00:36:53] **Adam:** So I, I think it could be done poorly, but I also think it can be done well. Right? Like you can't have acute graphic and none of the other things on this list. Right. You still have to explain what happened and why, and you still have to be empathetic and tell them how to fix it and all that. But I think it's, there's room for personality.

[00:37:13] **Carol:** I feel like it depends on your, like your customer base too. So when you're talking about GitHub, sure. Throw something cheesy up there cuz we probably can figure out what's going on, right? Like it's tech, it's tech focused. But if you're, Yeah, your audience matters. But if we're talking about my software, I write every day.

[00:37:32] **Carol:** I want my customers to have the best experience possible. So I wanna give them a branded error page that says the quality of work you get daily is what you're gonna get from us handling this error as well. I don't want some cute unicorn or monkey sitting out there going, I don't know what happened.

[00:37:51] **Carol:** Like, I want it to feel like that they're being treated with respect and that we're, we're taking this seriously.

[00:37:58] **Tim:** Yeah. So provide reassurance, right?

[00:38:00] **Adam:** Yeah. And I think you can't only have this personality in your error pages, right? If the only place that you're being cute and cheeky is on your error pages, then it's gonna feel, maybe not disingenuous, but it's gonna feel like you put more effort into making it cute than into

[00:38:16] **Adam:** trying to prevent the problem.

[00:38:17] **Adam:** Yeah.

[00:38:18] **Carol:** Yeah, and that's my view. I'm like, prevent the problem. Don't make the error page Cute.

[00:38:23] **Adam:** Yeah. I, I guess the thing that I like about these cute pages, and again, I think if it's just cute, then it's, then that's not a good enough solution. But it, I think it contr can contribute to turning a negative experience into a positive one. Right? So there's an error. I'm not getting the page that I want, get hubs down or whatever, but if like, okay, so Chrome, if you're offline, you get the little dinosaur jumping over stuff game, right?

[00:38:48] **Adam:** Like it's an error page, but it also gives you something to do

[00:38:51] **Ben:** that's

[00:38:51] **Adam:** if you're not aware, if you like, disconnect your, you know, turn off your wifi on your laptop, open up a tab in Chrome, type in google.com, and you'll get the error page with the dinosaur on it

[00:39:00] **Adam:** and just look

[00:39:01] **Adam:** static. Hit the, Yeah. Yeah. So you hit the space bar and that starts the.

[00:39:05] **Tim:** Yep,

[00:39:05] **Adam:** So turn a negative into a negative experience into a positive one if you can.

[00:39:09] **Tim:** Yeah. But that's that. I mean, honestly, that's one that you can't, The fact that you can't connect to the internet is, I mean, there's nothing else you can do, right? So give 'em a game. Right. So that, I mean, that's a, that's a good use case. But I, I just tried to pay for, you know, my jacuzzi and it's like $3,000 and I got an error and I, you, you give me a little cutesy thing, I'm like, Did, am I getting, you know, do I resubmit?

[00:39:35] **Tim:** Do, am I gonna get charged $6,000 now? So explain, explain to me what, what just happened. Did I or did I not just pay $3,000 on my guard or

[00:39:47] **Adam:** But if, if the page that said, Don't worry, we got your money. The, the error happened after we saved your payment. it's just in the, the we. We got an error when we tried to send you your confirmation email.

[00:39:59] **Tim:** right.

[00:39:59] **Adam:** page that you saw had that information on it, and it also had a picture of like, a bunch of cats enjoying your jacuzzi.

[00:40:06] **Adam:** Like, or you know, like the raccoons loading it onto the truck or something like your shipments on the way. We just had this problem, right? Like, you know,

[00:40:14] **Adam:** there's

[00:40:15] **Adam:** turn a negative experience

[00:40:16] **Tim:** that's provide reassurance, be empathetic. I mean, that's, that's exactly, exactly what I'm talking about. But I still, it's just really hard because sometimes it's like you're not really sure when you do get an error, you have to know what that error, how that's gonna affect the end user.

[00:40:31] **Tim:** You gotta really, really think hard about that. step. 10 out of 11 happened. And if 11 didn't happen, what does that mean? Well, if they didn't get a receipt or something, that's maybe trivial. Right? So just explain to them, like tell them what happened and why, and then, you know, explain to them like, Yeah, we, so yeah, we, we charge your card.

[00:40:51] **Tim:** We can't give you a receipt right now because, you know, Sin grid is down or whatever the issue is. Don't blame Sin Grid, but just say, you know, we can't see the receipt, So

[00:41:02] **Tim:** Yeah,

[00:41:03] **Adam:** blaming them, but they're down.

[00:41:05] **Tim:** but they're down, right? Yeah, exactly.

## [00:41:06] Form Validation Language

[00:41:06] **Ben:** I always struggle with the, the, the wording for errors relating to form inputs. so like if someone's trying to enter their email address, I never quite, and, and let's say they leave it blank. I never know if I want to go with, Please enter your email address, or email address is required, or email address cannot be blank.

[00:41:30] **Ben:** Or your email is, Yeah, your email is not valid. and, and then like sometimes I have, error messages that start with, please like, please enter an email address, but then I have many error messages that don't start with please and an action. Then it feels like it's inconsistent. And then I get nervous that I never really know what I'm.

[00:41:47] **Adam:** Yeah, I, I think form validation can count as error messages. And I, I really wanna touch on this real quick and then I'll let you go, Carol. you have to be extremely careful about exactly what you're saying. So you said email address is invalid and I'm, that caught my attention because I've seen people say like their, their name input field has a, a minimum length of three characters.

[00:42:06] **Adam:** Well, there's a heck of a lot of Asian people with a name that's two characters or, you know, maybe even non-Asian people. That's just the first one that's, that came to my mind. And if you tell somebody your name is invalid, oh man, that is like a terrible thing

[00:42:17] **Adam:** to say to somebody.

[00:42:20] **Tim:** Now it's just saying that I realize that we don't accept payments from people that have a name that's less than four characters.

[00:42:26] **Adam:** do

[00:42:26] **Adam:** you see? I just opened up a whole new

[00:42:27] **Adam:** market

[00:42:27] **Ben:** Yeah,

[00:42:28] **Tim:** you.

[00:42:29] **Tim:** Yeah. We also don't, if, if your name is all numbers, we don't, Don't take it either. Because a lot of people will put their credit card number in the name field.

[00:42:38] **Adam:** I guess you don't want money from Elon Musk's kid.

[00:42:40] **Tim:** Exactly.

[00:42:41] **Carol:** So with what Ben said, I like to put a banner like at the top of the page that says like, Please correct your inputs, or like, please correct the problem. And then under the input, or we'll, you know, turn it red, whatever we need to do. Like under, I'd be like, a valid email is required, or you know, you can't leave your first name blank.

[00:43:01] **Carol:** But I like to put the please message at the top because my Southern Raisin makes me, you know, say please. Thank you. Yes, ma'am. No ma'am. So I'm like, I can't tell them to go do this. I have to say please. And I probably should put thank you by the submit button or something. I don't know.

[00:43:18] **Tim:** He's a little side, side discussion. So this week we had a customer who responded to, it wasn't me, it was our customer service, representative. He responded to an email to her. He said, Yes, madam. I'm like, Who Is

[00:43:32] **Tim:** this? Is this? And like multiple times he called her mad. I'm like, Is he like Foghorn Leghorn?

[00:43:38] **Tim:** I mean, who says that anymore? He's like, From Tulsa. But I, I don't . You just madam. You just madam we are trying to process his credit. All payments you.

[00:43:48] **Adam:** I said, I said, I.

[00:43:50] **Tim:** Right?

## [00:43:51] Remediation

[00:43:51] **Tim:** So I mean, I think the last thing is give him a course for remediation and contact a little bit about that. you. Direct them to customer service if they feel like they need to. And, and we do that as well. So it's like some, sometimes people will make a payment, and then they'll for some reason, maybe make another one immediately.

[00:44:07] **Tim:** We try to block dope, duplicate payments, a message will pop up and say, Hey, call customer service, just cuz we're not always a hundred percent sure if they paid twice. and so give 'em a phone number they call and yeah, so just kind of prevent them from, from doing it twice. or submit a support ticket.

[00:44:24] **Tim:** If it's like a relationship where it's like a, you have a software service that you're giving, selling to a customer and there's an error, encourage them to do a support ticket. So just have some, some sort of course of remediation other than just like, Hey, there's an error

[00:44:40] **Tim:** by,

[00:44:41] **Carol:** Huh

[00:44:41] **Carol:** Ha

[00:44:42] **Adam:** I think you, you're absolutely right, but I think that it's important to say, like, put the phone number for customer support on that error page, or, or, you know, the link to create a support ticket or whatever it's gonna be.

[00:44:53] **Tim:** Yep, for sure.

[00:44:55] **Ben:** Links is a tough one because out of habit, whenever I have to display an error message, I usually encode it for html. So I escape special characters that might allow for some weird path that facilitates a cross site, you know, a cross site script attack. And then, which is fine because in 99% of cases the error message is just plain text.

[00:45:19] **Ben:** And it doesn't matter if it's encoded. But then the support team will say something like that, like, Oh, well in this, in this error message, can you include a link? and some other stuff and I'm like, Ah, not generically, cuz everything's gonna be escaped. So then I have to do some special, like in this case, if there's this flag turned on, show this additional link action.

[00:45:39] **Ben:** But I don't, I don't have a good way to handle that across the board. So I do a lot of one-offs for that kind of a stuff.

## [00:45:46] Patreon

[00:45:46] **Adam:** All right. Well, I guess that's gonna do it for us tonight. We're gonna go record our after show, tonight. I, I dunno about the rest of you guys, but I wanna talk about merch. We're gonna have podcast merch soon. I've got some, some information about that that I'm gonna share. Uh, if you're a patron and you're gonna listen to the after show, you might even hear where you can go get some merch. so, this episode of Working Code was brought to you by,

[00:46:07] **Ben:** What about the undefined variable reference on line 10 of your aspx page?

[00:46:12] **Carol:** There you

[00:46:12] **Adam:** let's go with that. I was gonna say fail Well, but Leia sure. Let's go with that. and listeners like you, just like pbs, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe than you should consider supporting us on Patreon.

[00:46:25] **Adam:** of course. Special thanks to our top patrons, Monte, Sean, and Giancarlo. if you'd like to help us out, you can go to patreon.com/WorkingCodePod homework this week. I'm gonna keep it the same as last week.

## [00:46:36] Thanks For Listening!

[00:46:36] **Adam:** Please leave us a review. You could go to workingcode.dev/review and that'll drop you right in the right spot.

[00:46:43] **Adam:** Leave us a review and we would greatly appreciate that. you could send us topics or questions @WorkingCodePod on Twitter. you can join our Discord at workingcode.dev/discord. You can email, text or voice memos to WorkingCodePod@gmail.com. Send us your voice memo and we'll play it on.

[00:46:58] **Adam:** That's gonna do it for us this week. We'll catch you next week. And until then,

[00:47:01] **Tim:** Hey, your heart matters even if your error messages are funny and ironic, but honestly, you know you can do better.

[00:47:08] **Ben:** Yeah,
