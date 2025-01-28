---
title: "172: Building Your Own Standard Library"
description: "In a world where many programmers instinctively reach for an existing solution in 'user land', Ben poses the question: is there value in building out and maintaining your own standard library?"
date: 2024-04-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/172-building-your-own-standard-library/id1544142288?i=1000651298111"></iframe>

In a world where many programmers instinctively reach for an existing solution in "user land", Ben poses the question: is there value in building out and maintaining your own standard library? This would be the collection of commonly-used functions and classes that _you_ enjoy using; and, which are tailored to _your_ use-cases and programming paradigms. Doing so would be a vibrant mixture of pragmatism, vanity, ego, efficiency, and compensation. But, would it ultimately be a net befit?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/172-building-your-own-standard-library.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** you really do learn different things when you're trying to write code and you're, you're bumping up and against new obstacles. And you're thinking about how you want to organize code. And then in order to solve this problem, you got to figure some other little problem out. And it's just, it's, there is a tremendous amount of value from doing it yourself.

## [00:00:38] Intro

[00:00:38] **Adam:** Okay, here we go. It is show number 172. And on today's show, we're going to talk about building your own standard library. But first, as usual, we'll start with our triumphs and fails. Ben, it is your turn to go first, buddy. What do you got going on, man?

## [00:00:50] Ben's Fail

[00:00:50] **Ben:** I'm gonna go with big fat failure. I just had one of those days where I woke up on the wrong side of the bed

[00:00:57] **Carol:** Oh no.

[00:00:58] **Ben:** cranky from moment one and then just everything got on my nerves. The dog got on my nerves and then I got to my desk and I opened my email and my, I, so I, I tried to take my Feature Flags book.

[00:01:12] **Ben:** And submitted for global distribution on Lulu. com as a digital ebook. And it just like hung out in limbo for like two or three weeks. And then it got rejected today with zero information about why it got rejected. And all they do is give you a link to an article about here's like the 50 most common reasons books get rejected.

[00:01:33] **Ben:** I'm just like, are you kidding me? It's,

[00:01:35] **Adam:** That sucks.

[00:01:36] **Ben:** It sucks. And then, I don't know, my day just was like crappy the whole time. I was just angry at nothing in particular, just at everything. And, and, yeah, it sucked. And, and then, I, you know, I've been doing some independent learning, trying to learn some new stuff.

[00:01:51] **Ben:** I've been digging deep into Alpine JS lately. And even on that, I'm feeling stuck. Like, I don't know how much I want to spend time learning this. You know, my problem is I don't have an end goal. You know, I'm learning a bit for the sake of learning. So when you do that, how deep do you go? If I, if I do two days of learning, I can get a sense of what's maybe possible, but I don't really understand how something might get used.

[00:02:16] **Ben:** And I've been looking into it for a couple of weeks now. And doing little, you know, experiments and little R&amp; D projects, you know, like one pager projects. But when you do that, you find a lot of edges, you know, like, okay, I don't, I realized that from reading the documentation, I didn't have a good sense of how this part worked or this part worked.

[00:02:33] **Ben:** I didn't think about how it would have to build in or, you know, like react in this kind of a certain context. So I do think there's value to. Digging below the surface, but I just don't know how deep I want to go. And I think I just don't quite know what question I'm trying to answer. And that's not a dig at AlpineJS.

[00:02:53] **Ben:** That's a dig at my strategy. I don't have a strategy and I think I'm starting to feel angsty about what my path is if I don't have a strategy.

[00:03:02] **Carol:** Yeah, I'm with you. I like learning for a reason and with an end, like an end goal. Like, here's what I'm trying to accomplish. Here's what I need to figure out. When it's just picking up something new and kinda learning it, but never utilizing it, I, I get burnt out real quick on it.

[00:03:23] **Adam:** I mean, I don't think I would even be able to sit down and try to learn it unless I had a reason to learn it. And then that reason is going to, at the very least, I guess, inspire some sort

[00:03:32] **Ben:** right. Yeah, exactly. And AlpineJS is really cool and I kind of do want to find a reason to use it, but Part of this started out because I was dissatisfied with the way Hotwire works. And that's the, that's the framework coming out of Basecamp. And they have a similar thing between Stimulus, their version of Alpine is called StimulusJS, and I've had some issues with it, not quite working.

[00:03:57] **Ben:** And it's just super verbose. Like the attribute names you got to use are really long. And, and because everything is so explicit in the DOM. And part of that is because it's very security minded. And that's where part of my friction then comes back into play because on my blog, I have a pretty strict content security policy.

[00:04:17] **Ben:** And AlpineJS doesn't really work with a strict content security policy. And now that I know that I feel like I have two options. One is. I could build a content security policy compatible version of AlpineJS, which is non trivial, but would allow me to use it. Or I could just not use AlpineJS and try moving on to something else.

[00:04:41] **Ben:** Or I could remove the content security policy from my blog, which, you know, I probably don't need, but I added because it's a quote unquote best practice. so I don't know, but, and I don't know which one of those answers makes the most sense, because. I don't, again, have a real solid understanding of what it is I'm even trying to do other than just learn.

[00:05:02] **Ben:** And anyway, so I'm just frustrated. I woke up angry today. I'm less angry now than I was 12 hours ago, but

[00:05:09] **Carol:** It's cause you saw us.

[00:05:10] **Ben:** yeah, yeah, I still have my cranky pants on and I will try to, I'll try to grin through all of this today.

[00:05:16] **Carol:** Aw, I hope you feel better tomorrow.

[00:05:19] **Ben:** Thank

[00:05:19] **Adam:** For sure. Yeah, I haven't read it, but I know that there's a book called Start. The title of the book is Start With Why. it's supposed to be like a, you know, kind of a way for you to organize your thoughts and move with purpose.

[00:05:32] **Ben:** don't know if that's Simon Sinek's book, but Simon Sinek had a presentation called Start, starting with why. And it's fantastic. I think I've mentioned it before on the show, but it's, it's really, really freaking good. It was a TEDx talk. So this might be his book. Yeah. Yeah. I'll put a link in the, in the show notes.

[00:05:50] **Adam:** Yeah, it is. Simon's the

[00:05:51] **Ben:** Simon Sinek. Yeah. So it's going to be quality. I should check it out. He's very, very good stuff from him, generally speaking. Anyway, that's me, Carol. What do you got going on?

## [00:06:03] Carol's Triumph

[00:06:03] **Carol:** Yeah, Ben, I'm gonna go with a Triumph. I missed you guys last week, so I guess that's, you know, sad. But I had a really great, visit with my customers. So I was in D. C. last week and, you know, also, Great thing the government didn't shut down. So woohoo for us, we keep getting paid. That's a big thing. But, my customer visit went really well and, you know, I've talked about kind of feeling a little isolated right now with delivering this very large effort and being the only developer doing it.

[00:06:33] **Carol:** And. Not really feeling like I could get out of the trenches. Hearing the impact that this is going to have on their business and their day to day operation and how many touch points it's going to remove for them really got me back motivated. So that helped coming into this week going, okay, I'm back, re fired, re energized, and able to get out some more code while I wait for a bigger team.

[00:06:56] **Carol:** So yeah, good to go with a big old triumph. And I got to work with two other customers who aren't, you know, Directly my customers, but our system customers and everyone will you will like benefit from this change. So it was nice to get to work with NASA. Hello, hello. So NASA and then BA was there. So it was great to work with those agencies and hear that they have some of the same struggles as my customer.

[00:07:19] **Adam:** VA meaning Veterans Affairs.

[00:07:20] **Carol:** Yep. Yep. Veteran Affairs.

[00:07:24] **Ben:** Getting in touch with customers is, is one, so great, but it's two, it is also something that I keep hearing on a recurring basis from interviews with people who have had very successful careers. And I was just listening to, the name has escaped me at the moment, but, he was made head of product at a company and the CEO at the time said, I want to make you head of product, but you don't get this promotion until you've gone to 30 customer offices, 15 in North America and 15 in Europe.

[00:07:54] **Ben:** And so he had to travel back and forth across the Atlantic for months to meet with 30 customers, and then he was able to get the promotion, but he said it completely changed the way that he thought about the product, having been in people's office and seeing them use the product and hearing them talk about the things that they like and the things that they don't like.

[00:08:12] **Ben:** It's just such a powerful connector.

[00:08:16] **Carol:** Yeah. I remember being onsite years ago. This was, you know, previous, previous, previous company. And, I was meeting with customer care people, the people who just kind of handled the few things here and there. And every time they printed this document to mail to someone when they called in, they would actually have to take wide out.

[00:08:33] **Carol:** White out bad data we had on there, write it in themselves, make a copy of it so they could scan it into like the person's document folder and then mail them like the copy that they made.

[00:08:46] **Adam:** Wow.

[00:08:47] **Carol:** And it was things that they had never like told us, so we didn't know what was going on, but not when you're there, you realize the pain that these people have and sometimes the right priorities aren't being set for work that needs to be delivered. Customer visits are always great. Well, usually great, unless they're very angry, then they're not so great. But mine were happy. So that's me. I would call it Tim, but he's MIA. So I guess that leaves you, Adam.

[00:09:14] **Carol:** Yeah, fail from Tim. Didn't show up. Jerk face. We love you, though.

## [00:09:20] Tim's Triumph

[00:09:20] **Adam:** to offset Tim, I am going to go with a triumph. super excited, so we're recording on Tuesday, a week from yesterday. So the next Monday, will be my, I'm just going to say intern. I feel like co op just doesn't roll off the tongue.

[00:09:35] **Ben:** No one will know what you're talking about if you say co op.

[00:09:38] **Adam:** my intern starts on Monday. So I'm super excited. We've got a bunch of projects lined up for him. he has his laptop now and I mean, the, the, the frustrating thing is, so this is going to be our first, like onboarding experience since, starting to work with an MDM, a mobile device manager, bit of software that like, you know, locks down your machine and forces that you have full disk encryption on and enforces password rules and all that stuff.

[00:10:06] **Adam:** and so. There's a whole, like, I don't even know truly what to expect with, like, their, his first interaction with the machine, you know, so, one of my coworkers set the machine up and, like, pre installed a couple of bits of software that are, like, you know, sort of assumed or, or pretty much guaranteed he's going to need, so that he wouldn't have to spend time on that, you know, on his first day.

[00:10:30] **Adam:** And, But he had to do that using like a placeholder account. And now the machine is like reassigned to him in the MDM. And so like, I, I don't know like what password he's going to need to sign into this machine. And so I had, I scheduled a meeting for later this week, which is before. and, so I have a scheduled meeting with the intern and with the guy who made the, who did the laptop set up and I'm like, we're just going to get together.

[00:10:52] **Adam:** Hopefully it'll take less than a half hour. We're going to get him signed into the machine and that's it. Like, uh, and then he can go continue enjoying his spring break. But I'm, I'm super excited. We've got a bunch of projects lined up and it's like. As we get closer and closer to the start date, we have, we start noticing more and more like, oh, that can be a Tony project.

[00:11:12] **Adam:** That can be a Tony project. Tony is his name, obviously. So, it's, things are starting to pile up. The ducks are getting in a row. and I'm just excited to see where this goes.

[00:11:23] **Carol:** that's awesome. I'm super excited for you.

[00:11:26] **Adam:** Me three.

[00:11:27] **Carol:** I will say though, when I think of intern, I think of the person who brings coffee. When I think of co op, I think of someone working on a project.

[00:11:35] **Adam:** Yeah, for sure. This is not like, you know, cookie cutter, anybody can do it kind of job. Like we interviewed him like it was a junior developer position. And the, I mean, the project that we're going to have them do first, definitely is like a, a nice gentle on ramp it's what, and it is funny. It's like, here's a spreadsheet of, like some information about different applications.

[00:12:00] **Adam:** So I talked before about our dead man's snitches and how like our applications, some of them are missing snitches that should have them. That sort of thing. And so we, at one point we made a list of all of our Lambda functions and containers and applications and things. And then we just went through that list as a team and said, okay, this one should have a snitch, but doesn't.

[00:12:18] **Adam:** This one should be auditing this, but it isn't, sort of thing. And so, we have this sort of like master list of these are some deficiencies that need to be cleaned up. And it's pretty low stakes. But it'll be a good way for him to like, get a wide, experience with our code and like, how we work, go through the code review process, all that stuff.

[00:12:37] **Adam:** So it seems like a good onramp for him. And, it's, it amuses me because it's like, okay, when you think of an intern, it's like, okay, here's a spreadsheet, I need you to fill it out sort of thing. And it kind of visually is going to be what his first thing is, but it's, you know, functionally, not at all. It's a real like coding thing.

[00:12:56] **Carol:** That's cool. I'm glad you've already got some work lined up for him. Cause that always helps when they get there and there's like a purpose. I know I enjoyed that with him

[00:13:04] **Adam:** We've started

[00:13:05] **Carol:** putting together chairs.

[00:13:08] **Adam:** zing, burn,we, we've started tagging tickets as like, Oh, this is a good one for him. This one's a good one for him. So, I think that'll go nicely.

[00:13:16] **Carol:** Help a lot. Awesome.

[00:13:18] **Ben:** if kids his age know about password managers. Is that a thing that people know at that point in their lives? I mean, I didn't grow up with password managers, so I learned about it as an adult. But when you talk about hard disk encryption, you know, he's going to get a backup key or an encryption key, and he's got to store that somewhere so that.

[00:13:37] **Ben:** I'm, you know, probably eventually it has to be rotated or something. Like where, where do you put that? I mean, I would, I put it in a password manager, but where does a kid put it?

[00:13:46] **Carol:** Well, I will say my kids have had 1Password since 1Password Family came out. So my kids knew about it. I can't tell you how long we've had 1Password. I mean, as long as 1Password Family's been around. So I think kids today do. And then personally, I think a lot of kids have devices like iPhones, or I'm sure Android has some version of it too, where they store your passwords in a password vault automatically.

[00:14:11] **Carol:** So there has to be some knowledge of it. Kydo.

[00:14:14] **Adam:** of IT people are

[00:14:16] **Carol:** Yeah. Yeah. There you go.

[00:14:18] **Ben:** The

[00:14:18] **Adam:** but your average person is going to be like, Oh, I have to reinstall my machine. I'm going to lose all my passwords because they were saved in the browser. You

[00:14:25] **Ben:** Well, that's what it is. You know, especially with the, with the phones, it's gets saved, but then it sort of goes into a black hole. So my wife, for example,

[00:14:34] **Carol:** It's in

[00:14:35] **Ben:** she can log in on her phone, but if she has to log in on her computer, she's like, I don't know what the password is and I don't know how to get it.

[00:14:41] **Carol:** Oh, so all you need to go is enter her settings and have passwords back up to

[00:14:46] **Ben:** Don't make this my problem.

[00:14:47] **Carol:** and then do the same thing on her MacBook.

[00:14:50] **Ben:** I actually just learned via Google that you can configure one password to be the thing that gets prompted for passwords on the iOS device. Now, I will say that that's only half cool because for whatever reason, half the time I do that, it doesn't show me the passwords that are actually in my vault. Like, it'll say like, oh, there is no match for, you know, Dropbox.

[00:15:15] **Ben:** com or, or, you know, Netflix. com. I don't know

[00:15:18] **Adam:** That's usually, if you're using one password, that's because the entry in one password doesn't have like a URL save. If you just have a username and password saved, then it's like, I don't know what this touches, but if it's got like a URL

[00:15:29] **Ben:** but the, but the thing is, is, is so the keyboard pops up and where it would normally say passwords, it'll say like one password. And I click on that and it'll open up one password inside the browser or whatnot. And I can search through the vaults and the thing that I'm searching for doesn't exist.

[00:15:44] **Ben:** But

[00:15:44] **Carol:** in the wrong vault.

[00:15:45] **Ben:** I then go to the 1Password app on the same device, it's there. So I

[00:15:50] **Carol:** Oh, that's bizarre. You should put in a ticket for that.

[00:15:54] **Ben:** Perhaps I will.

[00:15:56] **Adam:** I'm guessing you're just doing it wrong, but that's,

[00:15:58] **Ben:** And some, so I must be doing something wrong.

[00:16:01] **Adam:** it's okay. Your heart still matters, Ben.

[00:16:04] **Carol:** Tim, Tim still loves you.

[00:16:06] **Ben:** Thank you. Thank you too.

[00:16:08] **Adam:** So, I mean, with a modern MDM, you were talking about like needing to do something with your encryption key for your full disk encryption. I mean, A, full disk encryption, I don't know about on Windows, but on Mac, it's just, you turn it on and it's, it's done. Like when you sign into the machine, like after a reboot.

[00:16:25] **Adam:** That's what unlocks the, the full disk encryption.

[00:16:29] **Ben:** I think you still get a backup key so that you could decrypt the disk. I'm almost positive.

[00:16:35] **Carol:** Okay.

[00:16:35] **Adam:** you can like export or something, but

[00:16:37] **Carol:** I was gonna say, I used to use BitLocker on a Windows machine and it forced you to set the encryption key. So you had the key and that was how you decrypted the hard drive. So maybe with certain tools it is, but I don't know about if it's just encrypted with Windows.

[00:16:52] **Adam:** the other thing going through my head too, is, you know, now that we're on the MDM, I do believe I've seen something in there where it like can store the encryption key so that I guess if you lose your password or whatever, you can still files off of the machine. So,

[00:17:11] **Carol:** whole like company policy. I know we're way down a rabbit hole now, but there's the company policy, you know, like I had to send my laptop back in and the day that, you know, Clear Capital let everyone go, our machine's locked. So they don't have my password. Like they had to get back into it.

[00:17:26] **Carol:** So I'm sure that since it's company owned, you have some right to that data that's on the machine. So there should be some setting in there to unlock it as the administrator. I don't know.

[00:17:37] **Adam:** yeah, for sure. yeah, I should know better, but I'm, I'm out of practice. I've been too busy taking screenshots of tables that I build in Notion that claim that we do, we have done a employee access review and, you know, you just backdate it and put your name on it. Okay. We did, we did that.

[00:17:55] **Ben:** The sphere compliance stuff.

[00:17:57] **Adam:** yeah, and here's a list of, you know, our vendors.

[00:18:00] **Adam:** And when we did a security review and that they were compliant, check.

[00:18:04] **Ben:** Good time. So we, I, we had talked about this, I think in the previous episode, where we have a very high ticket customer, like hundreds of thousands of dollars, high ticket customer

[00:18:14] **Carol:** High ticket, you mean value or what they put in, like the number of

[00:18:17] **Ben:** like their contract, their contract value.

[00:18:19] **Carol:** Okay,

[00:18:19] **Adam:** value contract,

[00:18:20] **Carol:** They're a high priority.

[00:18:22] **Ben:** this is the thing where they have now put a new security demand on the company and we either have to fulfill that security demand or they're going to cancel their contract and went to our parent company and we explain the situation to them and they were like.

[00:18:36] **Ben:** Meh, I don't care. They're like, you guys do what you want. That's a lot of money to be very flippin about. I probably can't talk about it.

[00:18:47] **Adam:** Would you, can you say how much money it was? I don't think you've said

[00:18:50] **Ben:** It is nowhere near the cost of what the contract is worth. I mean, it's more the complexity of setting it up and

[00:19:00] **Adam:** talking about the value of the contract. Are we talking 1 million, 10 million, a hundred million?

[00:19:05] **Ben:** It's in the sub million. But it's a lot of money.

[00:19:09] **Adam:** Yeah, yeah, yeah.

[00:19:10] **Ben:** Anyway, I probably shouldn't even be talking about this.

[00:19:15] **Carol:** If Ben doesn't show up next week, we'll know why.

[00:19:18] **Ben:** what we were having. Or we were having our standup today and we, and the guy, our head of tech brought that up. And he was like, I don't know how much money these people are dealing with, but that is a lot of money to us.

[00:19:29] **Adam:** Yeah. Right. All right.

## [00:19:31] What is a Standard Library[00:19:31] Building Your Own Standard Library

[00:19:31] **Carol:** So why don't we move on to our topic for the day? so we're going to talk about like building your own standard library. So, somebody want to explain what is a standard library?

[00:19:39] **Ben:** So I think generally speaking, the standard library is the amount of functionality that is provided by the programming context in which you're using. So if you're. Writing JavaScript, the standard library would be things like the array prototype methods and the object prototype methods and the string prototype methods.

[00:19:59] **Ben:** And if you were in a node, the standard library would be all of the. You know, the FS and the, and the buffer and all the libraries that it provides to you. It's essentially the, the scope of functionality that you neither have to write yourself nor install from a user land module,

[00:20:18] **Adam:** Okay. So there's some really interesting distinctions there. So you specifically called out things on the JavaScript, object prototypes, right? So the array prototypes bring the, slow down Adam, the array prototype, the string prototype. et cetera. And those are built in. You don't have to import or require those.

[00:20:36] **Adam:** They're just always there and you can use them. And then you mentioned, like in Node where you've got FS and,

[00:20:43] **Ben:** right? Like FS is the file system. And then there's crypt, things like crypto and things like path,

[00:20:50] **Adam:** So these are things that are available, but you still have to require them. If you like import them into your project, you don't have to install them. And I think that that is what I, what I think of as like standard library.

[00:21:02] **Adam:** Okay. Cause it's a lot, it's still a library. It's not, when you say like in JavaScript, array methods are,

[00:21:09] **Ben:** mean, I'm just trying to differentiate the, the, the stuff that you didn't have to install from NPM or, or Maven or PIP or AppGet,

## [00:21:17] What is a Personal Standard Library

[00:21:17] **Adam:** I would say in Java, in JavaScript, I think maybe a sort of de facto standard library for the last decade would have been, or maybe, God, maybe I'm dating myself, but, for a certain decade would have been jQuery. Right, like everybody just installed that because it had, it, it did so much and, and kind of standardized everything and made it easy.

[00:21:38] **Ben:** Yes. Okay. So, and, and maybe we're taking the, the, the metaphor too far here at this point, because the, the reason that this was top of mind for me was because I didn't necessarily worry about, I mean, in, in a sense, the concept of building your own standard library is a contradiction in terms, because. The fact that you're building it sort of makes it not the standard library, but, what happened is for the better part of my adult life, I've maintained my blog code base.

[00:22:08] **Ben:** And it was really the only thing that I maintained. And in the last two years, I've started to work on a fitness site, dig deep fitness. And then I had put some foundational stuff together for big, sexy poems for, for writing and storing poems. And now I have. Kind of several sites. I mean, sites in the loosest sense of the, of the word here, but I have several different things that are all distinct, but have extremely high degree of overlap in terms of core functionality.

[00:22:39] **Ben:** You know, how I'm, doing my dependency injection, how I'm organizing my files, utility methods, like how many times do I have to write a, you know, an index by method that takes an array. And returns, struct with keys in it kind of a thing. And when it was all just my blog, I never really thought about it, but now that I have multiple things, I have begun sort of copy paste, modifying a lot of stuff from one site to the next site.

[00:23:06] **Ben:** And then as I'm building it in one site, I realized that I want to make some tweaks to it. So I'll make the tweaks in the new site. And then I go and I have to copy those changes back to the old site so that I can use those tweaks if I really wanted to. When it made me start to think of. Should I have a sort of factored out representation of this code as sort of like, here's the, the Ben's standard lib.

[00:23:30] **Ben:** And then when I go to create a new site, or when I want to update all the sites, I would first update the standard lib and then use that almost like my own private package manager, so to speak, or like my own private NPM JS, sort of a metaphor here, and then be able to have a source of truth. and I don't know, I've never thought about that before.

[00:23:53] **Ben:** I don't even know how I would organize it or where I would put it.

[00:23:55] **Adam:** Carol, did you want to say something?

[00:23:57] **Carol:** Well, no, it just sounds like you would still run into the same issues of things being able to be defined in multiple places unless you don't have a language behind it. So would this be the language that you write? Is bins, you know, perfect language?

[00:24:14] **Ben:** No, no, like it would still be, you know, this is all for ColdFusion based stuff.

[00:24:19] **Carol:** Okay.

[00:24:19] **Adam:** be a CFC, a collection of methods basically,

[00:24:22] **Ben:** Yeah, yeah. Or, you know, a collection of CFCs or Java JAR files that then get consumed in a CFC. Things of that nature. But, you know, there's I, I think, okay, so there, there's the tendency to just search NPMJS and say, Hey, is there an existing module that does the thing that I want to do? And when things get very complicated, I think that that makes a lot of sense.

[00:24:48] **Ben:** I don't want to go necessarily and invent ExpressJS or

[00:24:53] **Carol:** brand new odd.

[00:24:54] **Ben:** yeah, exactly. You know, there's, there's the, there's lifting that I want to do and there's lifting I definitely don't want to do. And I find that there's a lot of stuff that I just enjoy doing, you know, little utility functions that I know is only going to be five or six, you know, 10 lines of code.

[00:25:09] **Ben:** I want to write that. I don't want to install it. And I want a place to put that stuff and reuse it. And part of what I also react to is when you use a community based implementation of anything, typically what happens is the person who's authoring that. Has to make it flexible enough for a lot of people.

[00:25:33] **Ben:** So if you guys have heard, you've heard of FizzBuzz, right? Where it's like. I forget the FizzBuzz is some sort of a programming test where you have to like output evens and odds or something.

[00:25:44] **Adam:** know exactly what it is, but I want to make you squirm. So why don't you explain it for the listener?

[00:25:49] **Ben:** I, I don't even remember what it is, but I think it's, it's a programming test where you have to, I think just print even, like you have to say, like go from zero to 20 and print out even whether each number is either even or odd, something like that. Something very trivial

[00:26:04] **Carol:** Whether it's divisible by something, right?

[00:26:07] **Adam:** right, so you, it's like loop over, you know, one to a thousand for every number that is. Divisible by two, print Fizz. If it's divisible by three, print Buzz. And if it's divisible by both, print FizzBuzz.

[00:26:21] **Ben:** Oh, okay. All right. So, so there's FizzBuzz. And then people have made a quote unquote enterprise FizzBuzz, which is like, how can I take the FizzBuzz concept and make it as complicated? Yeah. Yeah, exactly. Make it as complicated as possible. And I feel a little bit like user land modules are kind of the enterprise FizzBuzz version of, of functions, because, you know, it's like, I want a function that does one tiny thing.

[00:26:49] **Ben:** And then I go to the GitHub repository that does it. And here's the readme and here's the contributing doc and here's the license doc and here's the ESLint doc and here's my dot configs for my editor and then here's my, Karma test files and then here's my other test runner and here's my TS config because I write in TypeScript even though I'm exporting it in JavaScript and it's like for the one file, yeah, it's like, it's like there's a 1 to 30 signal to noise ratio for libraries.

[00:27:21] **Ben:** And, and I know you could, you know, you squint your eyes hard enough and you say, well, I'm just installing that. So who cares? And that's kind of true in the node modules world where that's really hidden from you. But if you're in something like ColdFusion, which has like a less mature module system, you know, a lot of that is I'm, maybe I'm going to a GitHub repository and I'm literally pulling that down as a zip file and I'm putting it in my own vendor folder in my ColdFusion.

[00:27:49] **Ben:** And like, now I don't want all your crap files. And then I don't want to look in the code and see like, well, I have this code, in case it has to work with command bar or cold, cold box. And then I have this code in case it has to work with framework one and DI one. And I have this code in case it has to work with this other, you know, CF wheels.

[00:28:07] **Ben:** And you're like, I don't, I like, I'm not getting enough value. For all of this cruft, you know, I just want to have my own, you know, spicy take on what I think this function should do. And I want to have that source of truth somewhere where I have total control over it.

[00:28:23] **Adam:** I hear you and I want to jump in

[00:28:25] **Ben:** Yes, please

[00:28:26] **Adam:** so, and I've only just like, as you were talking there, come up with this sort of theory. So this may not pan out, but I'm going to say it

[00:28:34] **Ben:** explore, explore the

[00:28:35] **Adam:** in front of my face and that makes me an expert. Um, so, I I'm coming up with this thought of like atoms, molecules, and organisms, right?

[00:28:43] **Adam:** And so you were talking about the situation where you've got like a 10 line function and then the, the GitHub repository of all the supporting. infrastructure around that 10 line function and making it a community accessible thing. it might be 5x or 10x, the, the lines of code, or if you include the configuration and the readme and all that. and I, I, there because it is a lot of work. It seems a bit ridiculous to do all that for something so simple as a quick little 10 line function, right? It's a, it's a very particular thing that you do frequently with, array. reduce, right? It's like this one special case of reduce that you're going to use all the time. And. I see some value in that, but where I personally see the most value is when somebody makes the effort to make like a collection of those things all in the same theme. So you may have heard the name Cindersaurus. he's pretty well known in the JavaScript, community. He's got a ton, I mean, a, a, a, unreasonable number of, modules on NPM and GitHub.

[00:29:47] **Ben:** Is the new, TJ Holloway, Chuck?

[00:29:50] **Adam:** I mean, and then some. He's like ten TJs.

[00:29:54] **Ben:** Oh, my brain exploded.

## [00:29:56] The Problem with Collection Libraries

[00:29:56] **Adam:** Yeah. but like, so just to, to throw one example out there, he has a bunch of these libraries that are like P dash something, right? So like P dash throttle or P dash debounce or whatever. And they're all, they're all P dash something in that P means promise. So these are all like, do something with a promise, right?

[00:30:13] **Adam:** And he's got like 30 or something, 50 libraries, that'll do something with promises. And what I love about that is I know, okay, there's this weird thing that I'm trying to do. This feels like it should be a pattern. And I want to be able to do this thing with a promise. I bet you he has a function for it.

[00:30:30] **Adam:** And I know it's going to be well tested and community, you know, like battle tested, performant, that sort of thing. And so that in that case, I love that. And I know that I can just go download and install that one, you know, P throttle or whatever. Right. And I know it'll, it'll be what I'm looking for, no bloat, and like well done.

[00:30:50] **Adam:** And so for that reason, I think that it can be good to have those little atomic. But I think when you're talking about building your own personal library, I feel like, the next step up, what I say, Adam's Molecules is the next step up, right? So, I sent you guys a screenshot in our Discord, that's a screenshot of the readme of, a, I guess I would call it like the AlumniQ standard library.

[00:31:16] **Adam:** it's called TSModules because we used to have this, library called, AlumniCubePlatformModules, which was just a bunch of things that I had, sort of refactored out of applications as we were like, okay, we started with a monolith, and we were growing and growing and growing, and to deal with different challenges like scaling or multi tenant or whatever, we branched things off into microservices.

[00:31:39] **Adam:** And then in order to share functionality between things, we needed to have like a single, implementation so that our, so that we're not copy pasting or, or whatever. And then the real thing is like, okay, well, but if we find a bug in the thing, in the, in this particular function, we don't want to have to go update 12 libraries.

[00:31:57] **Adam:** We want to just update it in one place. Then redeploy and they all get the latest thing. and so, and then sort of the next evolution of that was like when we dove into TypeScript, we were like, okay, and we're gonna, we're gonna rewrite it in TypeScript and we're gonna apply all the lessons that we learned from things that we did with the original library that, turned out to not be good ideas.

[00:32:19] **Adam:** Right. So like, one of the things, and this is maybe it sounds obvious, but one of the things that the original platform modules. library included was a way to get a connected, configured, everything's ready to go database connection, right? So you would just say, I want a database connection, here's the customer and the environment, right?

[00:32:38] **Adam:** So customer X in production, give me a database connection, and it would return that for you. And you didn't have to know anything about any of the connection string configuration, connection limit, none of that. You just, I would like it please, and it gives it to you. Which is,

[00:32:53] **Carol:** And the problem was

[00:32:55] **Adam:** and the problem was that by putting that in our modules, in our like standard library.

[00:33:01] **Adam:** Now, anytime that anybody installs the standard library into any application, it's including the MySQL library, which you may not need. Right? And it's got, you know, and the promises wrapper around that and, you know, a bunch of other stuff. And, that, you know, when you make that same mistake five times, now you've got a lot of stuff, right?

[00:33:20] **Adam:** You've got the MySQL library, you've got the Redis library, you've got all this other stuff and it becomes like a, oh man, I really wish we didn't do this to ourselves.

[00:33:29] **Ben:** Yo, if, if I can just relate for two seconds, we ran into that so hard at work. We had a, a early technical leader, who shall remain unnamed, who was just like itching to get in and write some code. And ended up creating these shared libraries for Node. And the problem is exactly what you're saying. That they included things that not every service used, but it was supposed to be this sort of application boilerplate that everyone would start with.

[00:33:58] **Ben:** But the problem was, you know, in order to get the MySQL to work, MySQL had to depend on an environment variable that would define the database and the user and like the encoding and the idle timeouts. But if you're writing an application that is just, for example, reading from a message queue and doesn't actually need the database, well, you know, tough You still got to define all those environment variables. Otherwise the node package crashes when you try to import it kind of a thing. And it took us forever to pull all those things apart.

[00:34:31] **Carol:** Yeah, it's actually interesting because we're talking about some of this right now at work. You know, we're not using NPM. We're using NuGet because, you know, we're cool like that. But, we are trying to break out some of our services and call them like APIs. In reality, they're just going to be a different project in a NuGet package that is in the main core application.

[00:34:52] **Carol:** However, we've realized that these services each have dependencies on some of the same services. So, The question is, is with the next one, do we end up with like a circular dependency issue and nothing is going to work? So we're about to find out.

[00:35:08] **Adam:** Yeah. I remember dealing with that as well. And it's, it is very awkward. You're like, okay, but now I find myself in a little bit of a chicken and egg situation. You kind of have to like, if you're like disable automations until you get the new library up and then you can turn stuff back, stuff back on or whatever.

[00:35:24] **Adam:** Yeah. It gets weird. and so, so just to sort of deal with the, like, how did I codify the lesson learned there, right? So, this is not a hard and fast rule, but it is like a, a warning flag, right? So, when somebody wants to add something to this new TSModules library, if they add anything to the dependencies list.

[00:35:44] **Adam:** That's like a, okay, we need to make sure we talk about this. Is this something that we want every project to install? Cause like 90 percent plus of our projects install this TS modules. And, so it has very few dependencies and it's like date functions, you know, pretty printing stuff. I, A thing for debug output that like pretty much every project is going to use that sort of thing. So the vast majority of the functionality in this TS modules is, it's functions that have no dependencies, but they do something useful, right?

[00:36:15] **Adam:** So, one of the things in there is, talking to deadman snitch. You know, I've talked about how we use the service to keep an eye on our services and make sure that they're running as often as we expect and let us know if they go down. Instead of reinventing that in every project or copy pasting, it's like, okay, well that, and that's just as simple as like, receive a request, like make a function call.

[00:36:35] **Adam:** into this module, and it sends a HTTP request. It's like a fetch, right? And so it doesn't have any dependencies. That's easy enough. And it's, we can kind of reduce the API, quote unquote, that you have to learn to check into a snitch down to import this module, make a function call. and that's, that's nice.

[00:36:55] **Adam:** Or like checking the status of a feature flag. Right? Again, that's, that's at most it's doing some caching, but at most it's doing a fetch request, right? That sort of thing. So, and then, so the, the lessons learned from that, right? So I decided putting the database, connection thing into the standard library was a bad idea.

[00:37:17] **Adam:** So what I did from that was make the database connection thing its own separate module entirely. Like that it only does the database and it does everything you need to work with the database. Thanks. Do one thing and do it well, right?

[00:37:29] **Ben:** Absolutely. And then, you know, so you're, you're in a, In a more advanced world that I am in that you actually have a whole bunch of different, not replicas, but you, you have a lot of code base or I know you've been slowly kind of merging everything into kind of a mono repo, multi tenant kind of a situation, but, but I know that you had and continue to have at least things where you are copying pasting.

[00:37:55] **Ben:** And then this was in part to counteract the copy paste.

[00:37:58] **Adam:** So if my application had a Facebook account, it's relationship status with everything you just said would be, it's complicated.

[00:38:04] **Carol:** yeah.

[00:38:05] **Ben:** so I'm living in a world where I'm significantly less complicated. I have, you know, where your N is in the dozens, maybe my N is in the three. And so I do wonder a little bit if I'm fighting an unnecessary tide, meaning

## [00:38:22] The Motivation for a Personal Standard Library

[00:38:22] **Ben:** I'm generally speaking, a pretty big fan of copy, paste, modify. That's, that's like literally how I do 50 percent of my programming is I open up the last file that I worked on that I was most satisfied with and I copy it.

[00:38:35] **Ben:** And then I strip out a lot of stuff that I don't need. So generally that's a good strategy for me in terms of productivity. And I, and I do question myself in that. Is my desire to have a standard lib, maybe an unnecessary gut reaction to this copy paste modify. Like, you know, to, to your point, okay. If I have a bug in some cold fusion component and it only manifests in one of the three sites, like, is it really a problem in the other two sites?

[00:39:05] **Ben:** Do I, should I, should I really be stressing at this latent bug that doesn't, you know, create any issues yet and go and fix it in the one place and not worry about the other two places where it might exist? You know, maybe that's just good enough. And maybe I'm, I'm fighting an enemy that isn't really there.

[00:39:23] **Ben:** I, I go back and forth on

[00:39:26] **Carol:** psychologist Carol here.

[00:39:29] **Adam:** hmm. Welcome,

[00:39:31] **Ben:** How does this make you feel about

[00:39:32] **Carol:** Hello, hello. So perhaps is this in part because you will eventually lose access to this code and this data and everything that you've worked on for years. So by creating this library, you've retained some of the knowledge for yourself down the road. Or like, do you think that's playing into it at all for why you might want to do it?

[00:39:54] **Carol:** Cause you're like, Oh, I know I used to do it this way, but what was it? And you can't just go pull up this repo and remember how you did it. You're going to need a history of it.

[00:40:02] **Ben:** Yes. Because I will 100 percent delete all of the code that I'm not supposed to have anymore. That is official. Um, I, I, I get what you're saying. I think, I think most of the code that I'm concerned with is code that I'm actively using. And so I

[00:40:18] **Carol:** Okay.

[00:40:19] **Ben:** I think part of what I'm reacting to is like a little bit of shame.

[00:40:24] **Ben:** You know, when you discover that the choices that you've made are subpar. And you can fix them in one place, you feel a little guilty. Like, okay, I fixed it here, but now I know that it is subpar elsewhere and I have it within my power to do something about it, but I don't necessarily have it within my time or motivation to do something about it.

[00:40:47] **Ben:** And, and maybe part of the desire to have a standard library is it would make solving the shame problem, maybe a little bit more tractable. I don't know. You know, I'm, I'm, I'm thinking, I'm thinking on the fly here.

[00:41:03] **Adam:** Botanist Adam here.

[00:41:05] **Carol:** Welcome to the show, Botanist Adam. Have you been to Mars?

[00:41:09] **Adam:** not recently. it's interesting that you make, you bring up shame because the thing that I was thinking about was, I, I wonder if this is something that you want to do because it sounds like fun.

[00:41:19] **Ben:** Well, that's also definitely part of it for sure. And, and, and, you know, a part of me also thinks that there is a vanity aspect where if I have this cool collection of things, maybe I just make it public on GitHub and for no other reason that I can sort of, you know, flex a little bit and say like, Hey, cool, check out my standard library of functions that I use.

[00:41:38] **Ben:** No one will ever care, but you know, the back of my mind, I'll be proud of it kind of a thing. So I think that. It's like, that's definitely a non zero portion, I think, of my motivation.

[00:41:51] **Carol:** Yeah, definitely ego is the reason why I do everything.

[00:41:56] **Ben:** But then there's also, now that I have potentially three different places where I'm making mistakes, I, when I want to pull something forward, Like, Oh, I remember doing this in one of the other sites. Let me pull it forward into this new site. I'm not sure which one I'm supposed to pull from. Like, was the blog version, the one that was good, or was the dig deep fitness version, the one that was good?

[00:42:19] **Ben:** Cause that's the thing I actually most actively work on at this point. And, and, you know, I don't, I don't know. So again, I think there would be some value, but

## [00:42:28] Dependency Injection

[00:42:28] **Adam:** Do you have specific functionality in mind that you would, like, what's the first thing that you were, if you, if you decided, okay, I'm definitely going to do this, what is the very first thing that you would do that wasn't like the shell around the outside that makes it possible to do

[00:42:41] **Ben:** well,

[00:42:42] **Carol:** Great question.

[00:42:43] **Ben:** so the thing that I think has brought it most top of mind for me recently is the dependency injection. So I wrote my own little. InjectorCFC, which, you know, it's like,

[00:42:55] **Adam:** of shame.

[00:42:58] **Ben:** it's, it's, it's a 200 line cold fusion component and, and all it does is it does some meta analysis on the component and pulls in the property tags and then sees if it has some cache and if it doesn't and instantiates and it, and it, and it does some injectable stuff. I mean, it's, it's, it's not magical.

[00:43:15] **Ben:** It's magical to me because I wrote it and I had never written anything like that before. So there's, there's a lot of, you know, pride magic. Involved. so definitely putting that in the injector itself, I think becomes the first thing that makes almost the rest of it possible. And, and here's where, again, talking about having to build something more flexible than it necessarily has to be in user land.

[00:43:41] **Ben:** If I have my own injector, then it means that every ColdFusion component that I write after that can use that injector and the syntax that that injector is expecting, and I don't have to worry about. You know, DI1, I don't have to worry about how, Wirebox does its dependency injection, and I can start to simplify once I have my injector in place.

[00:44:01] **Carol:** So I, I know like the whole conversation is building your own library to do these things, but does ColdFusion not have a solid dependency injection, like, process or tool that you could use that you feel like you have to write your own?

[00:44:16] **Ben:** Well, there, there's the concept of accessors. So you can define properties and you can say whether or not these are settable and gettable, and that can put in the mechanics. Of how dependency injection can be implemented, but there's nothing inherent to CodeFusion that will then wire things together for you.

[00:44:35] **Ben:** That's, that's all to date been done in, in user land.

[00:44:39] **Carol:** Okay.

[00:44:40] **Adam:** used or seen DI1?

[00:44:42] **Ben:** Yeah. I mean, at work we use Framework 1 and I think it comes with DI1. So, so, you know, in the, in the grand irony of so much of this stuff, right. It's like you, so much of programming in my experience is like taking 10 steps forward. And then nine steps back when you realized that the one thing you were missing was just like one of those 10 steps.

[00:45:04] **Ben:** So DI1 to me, it has been really, really great. And Framework 1 has been really, really great. The one thing that it doesn't have is, at least the version that we have, maybe the newer versions do, and I should look into them, but you know, you get lost in your own tangents. And, you can say like, I want, here's my user service.

[00:45:26] **Ben:** And please inject it. And the type is components. lib. myuserservice. userservice, kind of a thing. And, DI1 does not do that. As far as I know, DI1 is like, you called it user service. So you can only look for things that are called user service. I don't care where it exists

[00:45:44] **Adam:** are you doing this via a constructor method or via properties and accessors?

[00:45:50] **Ben:** properties and accessors.

[00:45:52] **Adam:** Yeah, I mean,

[00:45:54] **Ben:** So, so like command bot, not command box.

[00:45:56] **Adam:** so the pro, if I'm hearing you right, the problem is that you can only have one thing named profile service.

[00:46:01] **Ben:** Yes. I mean, yes. So, so yes, I mean, that's, that is that if you want to boil it down exactly a hundred percent, I don't necessarily want to have things that are name conflicts, but sometimes it happens

[00:46:15] **Carol:** Sometimes you do want that.

[00:46:16] **Ben:** Yeah, sometimes you do. And, and, and, and more than that, it's like,

[00:46:21] **Adam:** Well, I mean, I, I have a very specific use case. So I have a, you know, in my monolith application, we have a public facing side and a, and a admin facing side, and they, the, Admin facing side gets all of the same services from the public facing side because a lot of that functionality is also useful, right?

[00:46:41] **Adam:** If you're going to register for an event in the public, you might as well use that same function to create a registration from admin, right? But then, There are additional features that I don't want available in the public services because I don't want somebody to accidentally, you know, use that same method from within the service or whatever.

[00:47:00] **Adam:** And so you end up with a profile service from public and a profile service in admin. And it, so what did it, I forget what I did. I think I might've like aliased it or called it, you know, admin profile service or something like that, but.

[00:47:13] **Ben:** yeah, I've, I've, I have a couple of places in the older code where I had to do something where I have a component and I call it something unique. And then if you open it up, all it does is turn around and extend. A different component that's not unique, you know, just so that it could be used as a, as a dependency injection token, for sure.

[00:47:33] **Ben:** So, you know, to, to, to burn this whole concept to the ground that, you know, if DI1 had this one little tweak, then would I be a hundred percent happy with DI1? you know, yes ish until, until you open up DI1's code and you find that it has a little sprinkle of logic for this framework and a little sprinkle of logic to work with that framework and, and, you know, from a purely philosophical standpoint, I'm just like, ah, I could just write it myself.

[00:48:00] **Adam:** So if it was typed, right. If you were able to say com. services. bigsexypoems. com. Oh, um, service or whatever. does that confer benefits or is that just like a personal idiosyncrasy that you would prefer to see that for your own, to make the connection in your brain or for some other reason? Or does that give you IDE hints of some sort or anything like that?

[00:48:23] **Ben:** I have the most bare bones IDE set up. I get no benefits. I don't get, I don't get. Like the only IntelliSense that I get is the IntelliSense for tokens that I have already typed into the same page. I don't think I

[00:48:38] **Adam:** You use Sublime Text.

[00:48:39] **Ben:** Yeah.

[00:48:40] **Carol:** He uses Notepad.

[00:48:45] **Ben:** I mean, I'm sure I get, I, I think it has JavaScript like a, like a, like, I think it does have some sort of language environments that run in the background. So I do get some syntactical stuff, but. It,

[00:48:57] **Adam:** then why, why are you hung up on this? Like typing of the services thing of the injectables?

[00:49:04] **Ben:** only for the, because it has been a roadblock in the past for the unique naming of stuff. And, and so I, I at work, I had wanted to say, Oh, if only I could have a full path and my type here, all of my problems would be gone. And in my personal life, where I have an opportunity to actually do something about that.

[00:49:28] **Ben:** I wanted to do it and, and, you know, 90 percent of it is for fun and, 10 percent of it is for value add, if that makes sense.

[00:49:38] **Adam:** I do think that it is classic nerd, I'm hung up on something that doesn't matter,

[00:49:45] **Carol:** Yeah, a hundred percent.

[00:49:47] **Adam:** because it matters to me. And I'm not, I'm not trying to shame you for that. No, no judgment.

[00:49:53] **Carol:** No.

[00:49:54] **Ben:** you, you know, you could, part of it too is

[00:49:57] **Ben:** it's like when you, when you first start, let me not paint with too general brush. When I first started programming. Everything just went one folder, like here were my components folder. And it's like, now I have 70 components in it. And because of the constraints of the file system, the files have to be unique, uniquely named, so dependency injection really doesn't matter from a uniqueness standpoint, because you're already battling the file system.

[00:50:23] **Ben:** You don't have to battle the dependency injector, but yes. You want to interject?

[00:50:29] **Adam:** and no. So I'll just do it quickly. ColdSpring. Go back to ColdSpring. You can write everything in XML. You can inject whatever you want into whatever you want. Problem solved.

[00:50:37] **Ben:** So as I've gotten older. And I've, I've wanted to start exploring different types of file organization. And now I have components in this folder and I have components in that folder. And I'm trying to, to maybe like co locate some components around a piece of functionality or a feature subset. You know, it's not crazy to think that, okay, well now I have a component called validation in one folder and I have another component called validation in another folder.

[00:51:07] **Ben:** And they just happen to be relating to two different features. And if the whole thing has to work together with dependency injection, one component is going to say, give me this thing, I want to call it validation internally from the outside world. It's actually, you know, lib. featureA. subfeatureB.

[00:51:26] **Ben:** validation. And this other component, I also want to call it validation, but it's actually lib. featureZ. validation, kind of a thing. Yeah. Zed for our Canadian friends.

[00:51:36] **Adam:** have, did we answer the question?

[00:51:40] **Ben:** I think so.

[00:51:40] **Adam:** you build a standard library?

[00:51:42] **Ben:** I think at this point, no,

[00:51:44] **Adam:** No, we didn't answer the question or

[00:51:45] **Ben:** no, no, no. I think, I think, no, I should, because I think the value add, I think I'm, I'm trying to scratch an itch that isn't really a value. I think my, the itch that I'm feeling is this lack of consistency and this some quasi fear of copy paste and, and this general.

[00:52:05] **Ben:** sense that I won't know where the right version of something is, but the reality is I don't have an ecosystem where that really matters and, and copy and pasting is fine and gradually improving things as I have time to, I think that's fine also. And I, you know, I don't think it makes sense for my particular context.

[00:52:27] **Adam:** I wonder if part of the pain that you're experiencing is the fact that CFML doesn't have a fantastic, like a community package manager experience. I know there's Forgebox and CommandBox and all the box things. And I know it's possible to get an experience that somewhat resembles like NPM. I haven't used it a ton.

[00:52:53] **Adam:** I've used it a little bit. And the sense that I get is that it was kind of inspired by the experience of NPM. if you're willing to do that and if that jives with your, your, the way you like to work, that's probably fine. If it doesn't align with the way that you like to work, then you're probably like me and you're like, I'm just not going to bother with this.

[00:53:10] **Adam:** And then you find yourself in a situation where. You have this need to sort of externalize something and share it between projects. And really, at that point, you don't have an option other than copy and paste, right? even with NPM. So before, before Microsoft bought GitHub and made private repositories and like package management and that sort of stuff free.

[00:53:37] **Adam:** the only way to do, or maybe it's not the only way, but what my company was doing was we had the, the, like the initial version of that platform modules, module, for lack of a better word, project, was, it was a GitHub repo set up entirely like it was an NPM package, but then instead of installing it, through npm because we didn't want it to be public.

[00:53:59] **Adam:** you could like npm package json supports like git colon and then a git url and it would when you did npm install it would go and pull it and you would you'd have to jump through some hoops to say okay here's the an OAuth token or a username and password to have access to this private GitHub repository to be able to install the thing.

[00:54:19] **Adam:** and that worked reasonably well for us. I mean, of course, you're gonna, as you scale up more projects and, more module or more packages that you're installing and more projects using those packages, it becomes a pain in the butt. And so I'm really glad that we're good to use packages for free now.

[00:54:35] **Adam:** I don't understand how it's profitable. I'm probably just because there's enough. Enterprise customers

[00:54:40] **Ben:** Right. I used to have a paid account on, on GitHub because I had like three private repositories and then they made that free. I was like, what, how is that possible? This is amazing. And it's like unlimited private repositories or something. Right.

[00:54:53] **Adam:** Oh yeah.

[00:54:55] **Carol:** No, wait, when did, when did they change that? Cause I'm still paying the 4. 99 for it.

[00:54:59] **Carol:** you need to stop doing that. I mean, the only thing you should be paying for through GitHub is, is Copilot. cause everything else you can get a ridiculous amount for free. Like even GitHub Actions, there's like a, it's like 5, 000 minutes a month or something like that for free. Interesting. I should go look. It's just been auto renewing for like

[00:55:17] **Adam:** You know what though? Now, now that I think about it, I believe my, yeah, I mean, I know for a fact that my company is paying for a private organization so that we can have, you know, our teams and we have packages that we share. So maybe that's the, maybe it wasn't free packages, but maybe that's when we just decided to like bite the bullet and pay the 7 a month or whatever it is for a private organization

[00:55:38] **Carol:** Yeah, we have GitHub, GitHub Enterprise. So I don't know what that means, but there's lots of repos.

[00:55:45] **Adam:** Oh yeah.

## [00:55:46] Benefits of DIY Packages

[00:55:46] **Ben:** Yo, this is, so one thing that's a little bit tangential, but it's still kind of on topic. The, the nice thing about writing stuff yourself. Is that because you don't have to live in this generic world, it's very clear whether or not a particular library or component or file is still needed. There aren't these abstract hoops that the build steps or the injections are going through to find stuff and make it available.

[00:56:18] **Ben:** Yeah, I find it incredibly frustrating and maybe the tooling has gotten better since the legacy projects that I work on. But if you look in a package JSON file, you say, Oh, I have this, you know, Billy Bob, util file. Like, do I need that? I don't know. You know, the best I feel like I can do is delete it or, you know, NPM uninstall it.

[00:56:42] **Ben:** Yeah,

[00:56:42] **Adam:** nothing breaks, then you know it's

[00:56:43] **Ben:** But like, you know, it's terrifying. It's terrifying to remove things from a package JSON file. I could, because I could run the tests, I could load the application and everything looks like it works great until what I realized is that one function is being included in a place that I didn't see, or didn't even remember was part of the application and now it breaks in production.

[00:57:05] **Ben:** And

[00:57:06] **Adam:** tests.

[00:57:08] **Ben:** that is right, your test, right test. But you know, if you write everything yourself and I know this is like stupid, especially If you, if you have a way to explicitly provide file paths, like in the dependency injection or, you know, component paths. You literally say, Oh, does, KablamoUtilityCFC, do I actually still need that?

[00:57:27] **Ben:** Well, let me just search my code base for KablamoUtility, and if it's not being referenced anywhere, I'm a hundred percent sure I can delete this file. And

[00:57:36] **Carol:** is not so easy with NuGet packages.

[00:57:38] **Ben:** right. It's,

[00:57:39] **Carol:** Yeah.

[00:57:40] **Adam:** I wanted to ask you, Carol, I know it's word tangent on a tangent on a tangent,

[00:57:44] **Carol:** Oh my goodness. So many rabbit holes.

## [00:57:46] NuGet

[00:57:46] **Adam:** What is NuGet? So I've, it's, I've heard of it before. I know it's a package manager, but I feel like it's for Java or

[00:57:52] **Carol:** NET.

[00:57:53] **Adam:** okay, that, that was going to be the second thing I said.

[00:57:55] **Carol:** very specific to NET.

[00:57:58] **Ben:** and it's, it's like their equivalent of AppGad or kind of a thing.

[00:58:03] **Carol:** I mean, honestly, it's just our package manager. So that's how we install packages. That's how we pick which version. So like I can go into the interface for it and be like, okay, this, this project has this version, this project has this version, here's where I update it at. So like our. Other repositories that we're breaking out into these, we're calling it like a vertical slice API architecture.

[00:58:27] **Carol:** So where we're pulling out these, pieces of the code, they each are their own project. So they're deployable independently. Deployable on their own. Words are hard to do, you guys. So they're deployable on their own, you know, they're maintained on their own, but they, every time you do a build on it, it creates a new NuGet package.

[00:58:45] **Carol:** And then when we deploy to production, that NuGet package, gets referenced back to the main site application, that the core application.

[00:58:52] **Ben:** Interesting. So I'm sorry, maybe, maybe I'm missing. Are you, you're defining your own NuGet packages or you're just installing? Okay. Okay.

[00:59:02] **Carol:** No, we create our own. Yeah. So our, instead of doing like an API call to this project, so say we have a project called cars and we have a project called drivers, rather than saying, you know, in the code, I want to go hit this hosted URL with my API endpoints. It's actually just a NuGet package for the project as it currently is for production. Does that help?

[00:59:24] **Ben:** Yes. Yes.

[00:59:25] **Carol:** Yeah. Okay.

[00:59:26] **Ben:** Yeah. You're basically creating your own module library.

[00:59:30] **Adam:** Yeah, this, this startup, the US government, you know, when, when they get some money, they'll get GitHub Enterprise.

[00:59:35] **Carol:** Yay,

[00:59:36] **Ben:** Oh

[00:59:37] **Adam:** All right. That seems like a good place to wrap it. Any, any final thoughts before I do my thing?

[00:59:42] **Ben:** I just love programming. I'm sorry. You know, and,

[00:59:45] **Adam:** Shame. Shame on you. Where's the lady from, from Game of Thrones when I need her?

[00:59:51] **Ben:** I, I mean,

[00:59:54] **Adam:** Which actually, did you know, I'm sorry, I have to interject here. That, that woman, shame, that is, the, the owner in, in Ted Lasso, the team owner, what is her name? It's, it's slipping my mind,

[01:00:09] **Ben:** tall, the tall lady.

[01:00:10] **Adam:** yeah, yeah. It's all blonde.

[01:00:11] **Carol:** She did a Christmas spe like a Christmas special.

[01:00:14] **Ben:** That's this year. That's funny. I didn't realize that. Oh, just to go back to pre interjection there. I mean, programming is just a lot of fun and I, and I think I end up wanting to program more things than should is not the right word, but as maybe a value add. But the value add for me is that it's fun.

[01:00:35] **Ben:** And, and you really do learn different things when you're trying to write code and you're, you're bumping up and against new obstacles. And you're thinking about how you want to organize code. And then in order to solve this problem, you got to figure some other little problem out. And it's just, it's, there is a tremendous amount of value from doing it yourself.

[01:00:58] **Ben:** And, and the only reason that I really want to underscore that is because I do think sometimes In the broader programming world, there is a little bit of a resentment that gets placed on people who want to, you know, invent it and like reinvent the wheel. And there's this concept, well, instead of reinventing the wheel, shouldn't you just pick an open source project and contribute back to it so that we can all get value?

[01:01:24] **Ben:** And I definitely think there's a time and a place for that, but I don't think, I don't think it's ever wrong to want to build it if you're motivated and it's exciting.

[01:01:35] **Carol:** And you understand the solve.

[01:01:37] **Ben:** Yeah. Yeah,

[01:01:41] **Adam:** you explained it and I want to rephrase because that'll help solidify it for me and maybe it'll help the listener. writing code because you want to. Even though there's something else that already does it and might do it better is not inherently a bad thing because what you're doing, because it's motivation, because you have the motivation to do it, you're practicing, right?

[01:02:03] **Adam:** Like in martial arts, you have katas, right? You do the same movements over and over. You're just practicing those movements. You don't go to take your test for the next belt and do a kata there. You take the test. So don't build your business on the code that you're writing for fun and for practice. You know, right.

[01:02:20] **Adam:** Do something that's well tested and community battle tested or whatever, but, to, to sum it, to sum it up clearly. Yeah.

[01:02:31] **Carol:** Yep, yeah.

[01:02:32] **Ben:** absolutely. Well, this is good. I

## [01:02:37] Patreon

[01:02:37] **Adam:** This episode of Working Code was brought to you by Tuff Ben's new dependency injection library.

[01:02:41] **Ben:** feel like I have to build something called that now. Is

[01:02:46] **Adam:** available at Dollar Tree and Dollar General.

[01:02:50] **Ben:** that domain available? Let me just see. I'm curious.

[01:02:54] **Adam:** Dot

[01:02:54] **Carol:** Nobody else Google this,

[01:02:56] **Ben:** it's, it's registered, but there's nothing there. It's just a parked page.

[01:03:00] **Adam:** And listeners like you, if you're enjoying this show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:03:13] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock!

## [01:03:18] Thanks For Listening!

[01:03:18] **Adam:** We are going to go record the after show, and if you're not familiar with the after show, where have you been all this time? I explain it every single week. But just in case this is your first episode, welcome, hello. After show is the freeloaders.

[01:03:32] **Adam:** You're going to hear the outro music, and then you're going to hear an objectively worse podcast in your, in your queue. Those of you that support us on Patreon, you'll hear the outro music, and then we'll come back and we'll talk about Random stuff. And sometimes the after show lasts for five minutes, sometimes like an extra half hour.

[01:03:49] **Adam:** It's just whatever comes out of our mouths. And then when we get to another good stopping point, we'll stop it again. and if you want that and other perks, like you get a special gold, your, your name in Discord shows up in gold because you're a supporter, then, all you have to do is support us on Patreon.

[01:04:05] **Adam:** You can go to patreon.com/workingcodepod to do that. Join our Discord workingcode.dev/discord. That's gonna do it for us this week. We'll catch you next week. And until then,

[01:04:15] **Carol:** Even if you aren't brave enough to create your own standard library, your heart matters.
