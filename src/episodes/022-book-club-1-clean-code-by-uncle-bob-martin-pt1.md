---
title: '022: Book Club #1: Clean Code by "Uncle Bob" Martin (pt1)'
description: 'This week, the crew talks about Clean Code: A Handbook of Agile Software Craftsmanship by Robert Martin aka "Uncle Bob". Recommended to us by friend-of-the-show Adam Cameron, this book outlines a series of best practices that programmers can use in order to create applications that are easy to understand and easy to maintain.'
date: 2021-05-12
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/022-book-club-1-clean-code-by-uncle-bob-martin-pt1/id1544142288?i=1000521443309"></iframe>

This week, the crew talks about [Clean Code: A Handbook of Agile Software Craftsmanship][clean-code] by [Robert Martin][robert-martin] (aka, "Uncle Bob"). Recommended to us by friend-of-the-show [Adam Cameron][adam-cameron], this book outlines a series of "best practices" that programmers can use in order to create applications that are easy to understand and easy to maintain. Just imagine if applications became easier to understand over time - not harder; that is the goal of this book.

A lot of the approaches feel obvious _once you see them articulated_. However, they're not always easy to apply in your own applications. And, some of the practices feel at odds with each other. For example, sometimes we want small, reusable classes that "do only one thing"; and, sometimes, we want a large mama-jama class that has 2,000 lines of code in it because _it's the very collocation of the logic_ that makes that class maintainable.

And, of course, we don't all agree on all the concepts. But, that's what makes the discussion so much fun!

## Triumphs &amp; Failures

-  **Adam's Triumph** - Adam's son broke both of his wrists (what the doctors refer to a "bilateral ouchie") while playing on the monkey-bars. Thankfully, his family has great insurance and lives very close to one of best children's hospitals in the country: the Children's Hospital of Philadelphia. So, while it has been (and will likely be) a rough recovery period, Adam feels like he has much to be thankful for.

-  **Ben's Triumph** - His big hairy goal for 2021 was supposed to be learning about "Design Systems". But, in the first 4-months of the year, he didn't follow-through on that goal in any way whatsoever However, in just the last few weeks, he's finally started to piece together some reusable components for his AngularJS application. Eventually, he might move to something like Google's Material Design; but, he feels like he needs to "fail first" before he can truly understand the problem that robust Design Systems are solving.

-  **Carol's Failure** - Despite what felt like an effortless start in her adventure with Amazon AWS, Carol hit a brick-wall while trying to get AWS Lambda to communicate with GMail. After struggling for 3-days to no avail, she finally got in touch with her Google Cloud Account support; and, _not even they can figure out_ why it's not working.

-  **Tim's Triumph** - While reading [Clean Code][clean-code] in preparation for this episode, he's already feeling more cognizant of the way that he's writing his applications. And, things are feeling pretty, pretty, pretty clean.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-cameron]: https://blog.adamcameron.me/
[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[robert-martin]: http://cleancoder.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/022-book-club-1-clean-code-by-uncle-bob-martin-pt1.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:16] **Adam:** It is show number 22 for May the 12th, and our topic today is going to be our first ever book club. We're going to discuss Clean Code by Uncle Bob Martin. But, as usual, we're going to do our triumphs and fails first, and I'm going to go first, um, and I'm going to just start by saying thank you guys for being flexible.

[00:00:31] **Adam:** Um, we are not recording on our normal day today, and that is because my son fell and... broke both of his wrists. He has bilateral, I don't even know what they call it. Your arm down near the wrist, you have two bones. He broke both bones in both arms near his wrists and they were compound fractures, dislocated.

[00:00:50] **Adam:** It was pretty much as bad as you can get for wrist fractures. Um, and he's 10 years old and so yeah, we had a rough, uh, couple of days there and Well, how's he doing now? I have a lot to be thankful for because he's in good spirits. He's in casts now, everybody, everything seems to be healthy and happy. His doctors are happy with, uh, what they see.

[00:01:10] **Adam:** It was a bad break, but all things considered, you know, we have good insurance and we are very fortunate to live. Uh, within driving distance of one of the best children's hospitals in the world, Children's Hospital of Philadelphia. And so, just sort of, if you're going to do this, it's one of the best places to do it.

[00:01:28] **Adam:** So, yeah, just tons to be thankful for. And that includes you guys. Thank you for being flexible. Anytime.

[00:01:34] **Carol:** Family first. Family first.

[00:01:36] **Tim:** Yeah, he sounded miserable

[00:01:37] **Adam:** the other night. He did. He was.

[00:01:39] **Carol:** Poor guy. Kids are resilient.

[00:01:41] **Adam:** He's a side sleeper. And so imagine trying to sleep on your side with both of your arms in splints because you haven't even got your cast yet and he's stuck on his back, can't get comfortable.

[00:01:51] **Adam:** That's

[00:01:51] **Carol:** terrible. I'm glad he's doing better. I'm glad to hear the whole family's doing good. We are.

[00:01:56] **Adam:** Yeah. Last night was surprisingly, like I came upstairs and was, you know, mentally preparing myself to help out and to be patient and to do whatever I could to help out. And like, Nothing. Not a peep. Not a single scream.

[00:02:11] **Adam:** So, uh, that's a positive. That's a win. Yes.

[00:02:14] **Carol:** Awesome. We're glad he's doing

[00:02:15] **Adam:** better. Thank you. So, Carol, why don't you go next?

[00:02:19] **Carol:** Oh, yeah. Man, it's been a couple weeks. You know, I started the new project with AWS and, um, getting everything set up and I was super stoked last week because everything's just going great with it.

[00:02:30] **Carol:** But then I hit a wall this week, um, I've spent three days total trying to get an authorization to work between my AWS Lambda and Google, and it does not like it. So I can authenticate my service account and create my JWT, my JSON web token, so I can create everything. My signatures are all there, but for whatever reason, um, that token will not work for Gmail.

[00:02:57] **Carol:** So actually getting to the mail service isn't working for it. So we got on a call with our Google Cloud Platform reseller, and they are pretty much stumped too as to why this doesn't work. So it made me feel better that not only can I not figure it out, our resellers tech people can't figure it out. So they're reaching out to their people to see if they can help me figure it out.

[00:03:18] **Carol:** So if, um, by, you know, Monday, we haven't got a resolution to it, I'm just going to switch over and do a different process and probably create like a delegate account and then authorize a delegate account that doesn't have access. So yeah, it's been fun but also stressful because I just keep reading the same thing over and over again going, it should work.

[00:03:39] **Adam:** This should work. Fun in air quotes there. Yeah.

[00:03:42] **Carol:** Total air quotes around fun. Because I mean you read, oh, oh, and the reseller. Mm hmm. We'll say nicely responded to our meeting, to our meeting with email to the API docs for Gmail and says, maybe your should developer should take a look at this. Oh, rude. I was like, uh, my key works.

[00:04:06] **Carol:** My key authenticates, but not to Gmail. So yeah, we'll see how it goes. It's just been stressful.

[00:04:13] **Adam:** That's like

[00:04:13] **Ben:** when you reach out to a support system and you're like, Hey, my, you know, device XYZ isn't working. I've tried rebooting it. I've tried reinstalling the drivers and nothing seems to work. And then they respond with, have you tried rebooting it?

[00:04:25] **Ben:** Have you tried reinstalling the drivers? And you're like, you're reading a script. Did you even read what I just said?

[00:04:29] **Carol:** I literally told you I created the token. I

[00:04:33] **Tim:** know what I'm doing. I feel the same way. Anytime I call my, my. Internet provider, right? I've already done all the things. I know, I know probably just as much as the person answering that phone.

[00:04:42] **Tim:** And like, look, I did all that. I did. Yep, yep, yep, yep. And I'm waiting for the moment to get in their script where I'm finally trying something I haven't tried yet. Like, okay, here we go. Here's the gold.

[00:04:51] **Carol:** This is the new piece. Or they're like, hey, tier two for you. Thank you. New support. Make it out. I'll get there.

[00:04:58] **Carol:** What about you, Tim? Where you at? Triumph, failure?

[00:05:01] **Adam:** I'm gonna say a

[00:05:01] **Tim:** triumph. I think probably because of this book that we're reviewing. Um, I'm building, so the thing I've been working on the past year, I'm building a helper package. I don't know what to call it. Like a library? Yeah, a library for other people so that they can...

[00:05:17] **Tim:** In their system, consume it and use it. And, and so I was taking very much to heart the, uh, making sure that a function only does one thing kind of thing that we'll get into later. And, uh, yeah, I mean, I got to agree with, with, uh, with uncle Bob. I mean, it, it made the code a whole lot cleaner. I, I'm, at first I felt like.

[00:05:36] **Tim:** I'm just, I'm typing a whole, I can just do this in two if statements. Now all of a sudden I've got four functions, right? And now I have to name all four of those functions, but I stuck to it. And at the end of it, I looked and go, you know what? This looks pretty darn clean. This looks good. And it's

[00:05:50] **Adam:** readable.

[00:05:51] **Adam:** Right. It is for other

[00:05:52] **Tim:** people. So I was very concerned about it looking good, right? My code, if only I'm looking at it, maybe I'll be like, uh, meh. But yeah, so I was very proud of myself for doing

[00:06:03] **Carol:** that. Kudos to you. I will say this book and I'm not going to try to jump ahead, but it has done that. It's like you've opened the door to this knowledge and now you can't unsee it.

[00:06:12] **Carol:** So you have to use it.

[00:06:15] **Ben:** How about you, Ben? I'm going to go with the triumph. And, uh, 2021 was supposed to be a year of learning about design systems. I feel like I'm good at front end development and I understand JavaScript and I understand HTML and I understand CSS, but I don't necessarily have any concept of how design systems work other than super abstract reusable components and methodologies.

[00:06:42] **Ben:** And, um, for the first couple of months of the year, I didn't really do anything with that goal. And, uh, finally this past two weeks, I've sat down and started to build out the seedlings of a design system that I might be able to use in my AngularJS applications. Uh, I know that there are other design systems already for Angular.

[00:07:02] **Ben:** Google's Material UI obviously is probably the big player in that area. But sometimes I just need to feel the pain of doing something first before I buy into someone else's solution. I'm sure a lot of developers are like that. So, I want to try to build at least a small set of reusable components that I can use to build some other.

[00:07:21] **Ben:** interfaces and then see how I might be able to use those to build some other interfaces and and get a sense of the problem set that's being solved and, uh, and use it just to understand things at more of a theoretical level and then maybe eventually go over to something like Uh, material UI, but you know, gotta, gotta fail myself first before I can understand the, uh, the elegance of someone else's solution.

[00:07:43] **Tim:** And appreciate the, the problem they're solving

[00:07:45] **Ben:** for you, right? Yeah, absolutely. So I'm pretty excited about that.

[00:07:49] **Adam:** So Carol. I think you were the only one of us that was able to attend our first ever game night with our patrons. Yeah, cause you guys are lame. Sorry. You scheduled it intentionally when we couldn't make it.

[00:08:03] **Adam:** That's what you did. Don't tell them. Make us look

[00:08:05] **Carol:** bad. Listen, you can't tell them that.

[00:08:07] **Adam:** The first

[00:08:07] **Tim:** time in over a year I'm able to go out to eat after getting the Fauci Ouchie. And you want to schedule a game night. Yeah, I couldn't explain that to my wife.

[00:08:15] **Adam:** Sorry.

[00:08:16] **Carol:** I mean, you know, the people on the, uh, two.

[00:08:19] **Carol:** Two of the people on game night said they totally would have cancelled on their wife to play board games with us. So...

[00:08:26] **Adam:** I would cancel on their wife to play board games with you too, but uh, not my wife. Exactly.

[00:08:32] **Carol:** One of them might have been my son.

[00:08:36] **Adam:** So, what did you guys do? I want to know.

[00:08:38] **Carol:** Yeah, so we got on and originally we were going to try playing D&amp; D, but I could not figure out.

[00:08:46] **Carol:** The Kroll, what is it? Is it Roll? Oh, Roll20. Roll20. There you go. I just knew it kind of looked like my username on everything, and that was kind of cool. Um, yeah, I couldn't figure out Roll20, I couldn't figure out how to set maps, like, I gave up and was like, one day we will have a DM, which will be Tim, show up and, um, we'll play a D&amp; D round.

[00:09:06] **Carol:** But instead, um, one of our Patreons, actually, Nate, gave us access to his Jackbox, Jack, is that what it's called? Jackbox Party Games. Yeah. Yeah, so we all just played it. Um, I wish I could remember the names of the games. I don't. I might have had some adult beverages during it, so. Well, you're an adult. Yeah, I'm an adult.

[00:09:24] **Carol:** It's totally fine to do it. Yeah. Yeah. But we played like trivia games and we played one where you create a t shirt to which the winning t shirt is Little guys praising or like praying to a volcano and under it, it says like NPM run build. So, you're like, yeah, you know that that builds about to bust.

[00:09:46] **Adam:** I actually ordered that t shirt.

[00:09:47] **Adam:** Did you? I did. I was hoping it would be here in time for the recording but it hasn't come yet. That's funny that you described it as like they're praying to the volcano. When I saw it, because I had, I, you know, I saw the... The stuff posted after you guys were done and I went and looked at it and I interpreted that totally differently.

[00:10:03] **Adam:** I thought that it was like, the volcano was erupting and everybody's running away. See,

[00:10:07] **Carol:** that one works too. Either is good. So that was the, the like, catchphrase was mine. And then, yep, and then no, uh, Nate, sorry, Nate had done the volcano. And then Monte actually combined them together to make the shirt. Nice.

[00:10:21] **Carol:** So then yeah, it's pretty cool. And then the other one was an image of CF and under it it said, Did I do that? I think it said, Did I do that? Yeah. So it was pretty cute. We had a really good time. We played for about two hours. And just chatted. I mean, we got to know each other a little better too. We talked about what we do and just, you know, had fun.

[00:10:40] **Carol:** I really enjoyed it. I mean, we're definitely going to do it again. I'm trying to figure out a time when you guys are available to do it with us because that's more fun.

[00:10:47] **Adam:** Cool. Yeah. I just wanted to throw that out there because I know we mentioned the perks every week when we record about, you know, why would anybody want to be a patron?

[00:10:56] **Adam:** And I just, you know, throw a little incentive out there. Other things that we've learned this week, uh, I found out that Apple, which seems to be the only place you can leave a review for a podcast, they segregate podcasts by the country of origin. So, if you happen to be in the Netherlands and you leave a review on our podcast, we don't see that if we're looking at American iTunes.

[00:11:18] **Adam:** Um, and so... Um, I went through and I, Tell

[00:11:22] **Carol:** me we have reviews in

[00:11:23] **Adam:** other countries. We do. And they're all in English. So, like, Yes. Um, we have a couple, um, and internationally

[00:11:30] **Tim:** known, we're

[00:11:32] **Carol:** famous, we're like James Bond now.

[00:11:35] **Adam:** Uh, I don't know if I'd go that far.

[00:11:37] **Carol:** Uh, Josie Wells, so good I started paying for it. This is great and entertaining.

[00:11:43] **Carol:** Hold on. I really should put my glasses on you guys. Can I start over? We're going to

[00:11:46] **Adam:** do it again. Absolutely not. This is the

[00:11:50] **Carol:** one take club. I gotta get back to the screen. Okay. All right. So Josie Wells says, so good. I started paying for it. This is just a great and entertaining tech podcast, which covers issues and interests to web professionals without getting too techie.

[00:12:02] **Carol:** Yeah, we do, uh huh. Each of, uh, each subject is covered as a discussion between four developers who each have their own views, but very seldom professionals, but very seldom profess to having the one true answer, which is a great way to, uh, involve the listeners. Recommended. Five stars.

[00:12:20] **Adam:** So that's actually Seb, one of our patrons.

[00:12:23] **Adam:** That's what he means by he started paying for it.

[00:12:30] **Adam:** And then does somebody want to read the one from Mingo? So he

[00:12:33] **Tim:** says, this podcast is giving me the opposite of imposter syndrome. Listening to these four pros talk honestly about their triumphs and fails is really helping me recognize and deal with mine. I hope that they keep up the really strong start because they moved to the top of my podcast playlist.

[00:12:50] **Tim:** Booyah! Oh

[00:12:50] **Adam:** wow, I

[00:12:51] **Carol:** just got chills.

[00:12:52] **Ben:** Oh wow. These are giving me all kinds of fuzzies. I

[00:12:55] **Tim:** got feelings. I got real feelings on

[00:12:57] **Adam:** these. So sorry we didn't find those earlier, but thank you guys Sab and Mingo for your reviews. Uh, and, uh, thanks Obama for segregating the, the review marketplace.

[00:13:09] **Tim:** You blame lots of people for segregation, but Obama ain't one.

[00:13:17] **Adam:** All right. Well, shall we get into working code? Not working code. That's us. That's us. We already do that. Yeah. Welcome. Shall we get into our, uh, book club of clean code? Yes.

[00:13:29] **Carol:** Absolutely. All right. So I would like to say that of all of the episodes we've done, we always start with, we're not experts on this, right?

[00:13:37] **Carol:** Or we do it often, you know, we're not the best at this. I have found something I'm an expert at. And it's writing not clean code. I'm very good at this. You're not alone. This book confirmed I am an expert at it.

[00:13:52] **Ben:** One of the things that I do really like about the book is that he talks about writing clean code is a process.

[00:13:59] **Ben:** Yeah, absolutely. It's, it's not something that's one and done and people aren't just good at it right away. And even people who are really good at writing code, clean code is typically not the first version that they do write. And I enjoyed that. I enjoyed that sort of, we're all people and we're all making mistakes and we're all sort of figuring out as we go and it's a, and it's a learning process for everybody.

[00:14:17] **Ben:** Yeah,

[00:14:17] **Carol:** I mean, I think, um, the best way to think about that is whenever you're writing a paper, you have a rough draft, right? You usually go through your outline of it, and then you write your rough draft, and then you read it, and then you write a better version of it, and then you proofread it, or have someone else look at it, and then you finally have a good copy of it.

[00:14:35] **Carol:** Like, it's okay that when you're writing code, your first version probably should not be the final version. You should have, like, an outline, and then your rough draft, and then the cleanups, and edits, and then have a version that makes sense.

[00:14:47] **Tim:** So, I don't know, I know we're going to do, like, a format here, but I just got to say...

[00:14:51] **Tim:** The absolute spiritual, emotional gut punch of reading the topic entitled, The Total Cost of Owning a Mess. Page 40 on my PDF. I, I sent the PDF to my GM and I sent it to her and I said, read that section called The Total Cost of Owning a Mess because it totally describes what I've seen over and over again happen where code is not clean.

[00:15:21] **Tim:** Slowdown significant over the span of several years. Teams are trying to move fast, but they're moving at a snail's pace because code is just not clean. Anytime they make a change in one place, it breaks stuff in two other places. No code is trivial. No change is trivial. Uh, no one understands it. It's twisty and turny and it's a twist.

[00:15:41] **Tim:** It's a swamp. You know, everybody loses sleep, uh, because. They don't see any way to get out of it. So they build some sort of tiger team, right? And we're gonna, we're gonna fix the mess, right? Yep. And everybody wants to be on the tiger team. And then the tiger team, you know, tries to make all these changes.

[00:15:57] **Tim:** And eventually, 10 years down the road, you're back

[00:16:01] **Adam:** exactly where you were before.

[00:16:03] **Tim:** Maybe not even 10 years. Because the tiger team wasn't making it clean either. So yeah, I'm like, wow, I've seen this happen. You talk about patterns and anti patterns. Well, this is sort of, this is like a cultural pattern. Yep.

[00:16:15] **Tim:** You see that pattern and you go,

[00:16:16] **Ben:** my God. The part of that section that really, uh, hit home for me was when he's talking about the Tiger team, when they're getting like three years into it, the original Tiger team is actually no longer even part of the company and the people who are now working on that project don't even remember why that project was started in the first place because they weren't here.

[00:16:36] **Ben:** And I'm like, oh, that's uncomfortably close to home.

[00:16:40] **Carol:** I was put on the Tiger team to go do the work. And then my other team is sitting there just colliding with me because they're trying to get their work done and they're trying to write on top of bad code. We're trying to fix code. It was a giant mess, and it was the worst thing I think we did in a very long time, was ever having that Tiger Team.

[00:17:00] **Adam:** Alright, so everybody has to have said Tiger Team, so now I've said it, too. Um, but I wanted to ask you guys, is that, that's very clearly a phrase that's used in the book, right? He calls it the Tiger Team. But is that something that you guys had heard of before? Oh yeah. I was on the Tiger team. I've never heard of that before.

[00:17:16] **Adam:** Yeah, it was an official

[00:17:17] **Tim:** designation. She was Tiger, Team Tiger. Yeah,

[00:17:20] **Carol:** and then we got in trouble for calling it Tiger Team.

[00:17:24] **Adam:** But this isn't just a random like, Ben's team is the Rainbow team. So what is the, what is the significance of Tiger Team to being

[00:17:30] **Carol:** the rewrite thing? Yeah, so the Tiger Team is you take your top people, Who can get the most work out and the most, like, effective way.

[00:17:38] **Carol:** And you put them together, isolate it off from the rest of the company and you say, get this problem fixed now. Oh, okay. And the problem is that it doesn't come with quality necessarily. Because the, the understanding up front is Tiger Team's gonna do this work and they're gonna do it right and they're not gonna take no for an answer.

[00:17:57] **Carol:** They're gonna do it the way they want it. But then suddenly on Friday, hey, here are all these deadlines. Did you get all this done? And we're going, what happened to the no, taking no for an answer? We get to do it right. Yeah, well, it costs money and we need to keep moving on it. So it doesn't always work, but Tiger Team is definitely a real thing.

[00:18:14] **Carol:** It is, they pull a team together of people to

[00:18:17] **Adam:** do it. I found it interesting because you guys all seemed very comfortable using that term and it was new to me. And he doesn't really explain it in the book. I, other than to just say that this is what that, you know, give it a name, like a tiger team and like, okay, sure.

[00:18:29] **Adam:** It

[00:18:29] **Tim:** evokes the image of like, you know, there's United States, it's some country and there's some huge issue in some country. They send some Navy SEAL tiger team to go in and fix the problem, right. To extract the hostages and then come back, you know, they fix the problem, come back in and out. Right. And that's, uh, That whole idea of a tiger team is really antithetical to the entire process that Bob, Uncle Bob here is talking about.

[00:18:51] **Tim:** It's like every developer's goal should be to write clean code. You just have a tiger team and everyone else is just gonna... You got 50 people making a mess and 2 people, 3 people who are supposed to clean it all up. It ain't gonna work. Yeah,

[00:19:03] **Adam:** yeah. So I wanted to kind of take a step back here. If we look at the cover of the book, on the front it says, Clean Code, a handbook of agile software craftsmanship.

[00:19:12] **Adam:** Which is a mouthful and it feels very loaded. But when I think back on that title after having read the book, it feels very appropriate. Like, I feel like if that's the goal that they set for themselves in writing this book, that they kind of reached it. Sounds like a beer I'd like to drink. Um, so Adam Cameron was the person who had suggested that we read this book, right?

[00:19:33] **Adam:** And when he was suggesting that, He was saying things along, I'm probably, I'm paraphrasing, so I'm probably not going to get it perfectly. Oh, he'll correct you. Don't worry. Yeah, yeah. But, um, he was saying things like, you know, in order to consider yourself a professional, you have to do certain things, right?

[00:19:49] **Adam:** And so for one of the things for him is like, you have to have automated tests, right? And that's just, that's table stakes for being considered a professional software craftsman. According to the cover of this book. And just because of how loaded those terms are and how confrontational a discussion like that can feel, whether or not it's intended, I think I was a little standoffish when Adam had suggested that.

[00:20:13] **Adam:** But again, now having read the book and looking back at it, I agree. I feel like Doing the things in this book, which we'll get into and we have some opinions on, but doing things in this book, by and large, if you, if you aim to be a software craftsman and you aim to write clean code, whatever, even if your definition of clean disagrees slightly with what the book says, that's going to make you a better programmer and it's going to make your code easier to maintain for you and for others.

[00:20:38] **Adam:** I feel like it's kind of a controversial thing to say to somebody like this code is unclean and you need to do better and this is how you do it, right? But If you sit down and you put in the work of reading and, and, and again, I don't think there's any huge surprises in this book, right? This is all stuff that we all knew.

[00:20:53] **Adam:** We knew this, yeah. Right. But having it laid out in an organized way, and given the evidence of like what makes this better than the other approach. Um, I think it makes a lot of sense. So I just wanted to zoom out for a second there and comment on that. Having

[00:21:07] **Carol:** it given to us in a clean manner. Yeah. It's so much better.

[00:21:11] **Carol:** And so it's really good.

[00:21:13] **Adam:** So I think one of the things that's really beneficial about the way the book is written, like he goes through chapter by chapter and talks about a lot of different things and dives deeply into them. But then at the very end of the book, he's got this section called smells and heuristics where he basically summarizes the entire book and like each section of the book gets a, a paragraph basically to summarize the whole thing and sort of remind you of it all on your way out the door here, which is amusing to me because there's still like, I don't know, three quarters of an inch of the book left after you read that chapter with the appendixes and stuff.

[00:21:43] **Adam:** But so I thought maybe a good way for us to do this would be to kind of go through that, that conclusion chapter. And we're not going to, you know, read every part of the book here to you, but the, the interesting sections, the ones where we feel like maybe there's some discussion worth having. We would go through them.

[00:22:00] **Adam:** I

[00:22:00] **Carol:** would like to throw out this book is on Audible. Yeah. So, I actually listened to it. I don't have time to necessarily sit and read a whole book because I have so much going on, but I listened to it while I was cooking dinner. I listened to it while I was driving and running. So, I mean, I found time to get through it, but the Audible version is really good and I, I liked it a lot.

[00:22:18] **Adam:** I agree.

[00:22:19] **Tim:** I did both. I had the PDF and I listened

[00:22:21] **Adam:** to it as well. Yep. I got it from my library and I also listened to it. What about you, Ben? I

[00:22:27] **Ben:** read it on my Kindle app on my iPad. Okay.

[00:22:31] **Tim:** Digital paper. Look at Mr. Digital. Digital paper.

[00:22:35] **Adam:** Saving the trees. So the first section of the book was kind of about comments and there's a bunch of different ways to use comments to write unclean code.

[00:22:47] **Adam:** And the one that stood out to me, I mean, there's obvious things, right? Like a redundant comment where you write, like, write a comment above I that says, this is incrementing I, like, duh. No _(quack)_. Right. So the, but the one that stood out to me, um, was commented out code. Why? So I actually wrote a whole blog post on this myself, um, and I called it dead code.

[00:23:09] **Adam:** Um, and basically, let me see if I can summarize that blog post. Like, in general, rule of thumb, I completely agree. Delete the code, it's in your source control, you can go back and look at it. In my case, I had this one use case that I wrote about in that blog post, which was that we had this difficult to solve performance challenge, and we tried something like half, somewhere between half a dozen and a dozen different approaches.

[00:23:31] **Adam:** Some of them wildly different to try and, you know, squeeze the most performance that we possibly could out of this stone. And the one that we landed on, because it had the best performance, might not seem that obvious of a thing to try. And I was a little bit worried about somebody coming behind me, whether that's me in 5 or 10 years, or somebody else, you know, maintaining this code, looking at it and go, Why the heck would you do it that way?

[00:23:53] **Adam:** You know, why wouldn't you just do it the obvious way? And so what I did was I left those function definitions, so each, each, um, iteration of the attempt to get the most performance out of this algorithm was implemented using a different function, and so it's, you know, to, to try the different implementations, it was just switch which function you're calling, which I think Uncle Bob would say is probably a good approach to being able to try different things.

[00:24:15] **Adam:** But what I did was I commented out those blocks of code, And, or those functions, and I left a comment above them that says, like, these are all the things that we tried. So, if you're, if you want to try and squeeze more performance out of this, then be my guest, but these are, this is what we've tried, and we're using the one above because it was the most performant.

[00:24:31] **Adam:** And that makes sense. Yeah, and so what I call, I consider them to be gravestones. Like, this is dead code, but it's dead here, and I want you to see these gravestones because they are worth seeing. Yeah. You know, they're, Warnings to weary travelers who may think that they know better.

[00:24:46] **Carol:** And see, I've been in that position before where I've tried to solve a problem, and I go to someone and I'm like, hey, I really can't figure this out, and here's everything I've tried.

[00:24:54] **Carol:** And then I get the backstory of, oh yeah, I tried that, and that, and if you're thinking of this, I also tried that too. Well, you could have put in there why you got to this solution so that I wouldn't have just wasted a day trying all these different things to, to only find out you'd already tried this once and it didn't work.

[00:25:10] **Carol:** Those are really helpful.

[00:25:11] **Adam:** Depending on the situation, you could probably get the same effect by really good comments. Like just write a couple of paragraphs in a comment that explains what's going on. But I really wanted the details of the implementations that we tried to be available. Like maybe, maybe I did it wrong.

[00:25:27] **Adam:** Maybe there, you know, maybe there, there is a better way, you know, using one of my earlier algorithms, but I just did it poorly or

[00:25:34] **Ben:** something. I've also occasionally commented out pieces of business logic that were causing performance problems or had some sort of additional complexity that for whatever reason the application couldn't afford to take on at that moment.

[00:25:47] **Ben:** And I didn't want to delete them because they were supposed to be there, but I didn't want to run them either. So I would comment them out and then I would leave a big comment about this is supposed to run, but we're making a, you know, calculated decision to not run it right now because we hope to fix this in the future.

[00:26:01] **Ben:** Uh, I mean, he also makes jokes about any comment that says, I hope to fix this in the future. Cause that future never comes, but, um, You know, it's, it's easy to look at a line of code that is running and then go into GitHub and do a blame and see who wrote this and why it was written. But when code is deleted, it's a lot harder to look at the history of a file and figure out why code's not there that should be there.

[00:26:24] **Ben:** So just leaving that hook that you can go in and do a blame and see why that code's been commented out is very helpful sometimes.

[00:26:31] **Adam:** Yeah, I was thinking about that too. So, I mean, like you said, when you delete code, there's no indication that the code has been deleted. It's just not there anymore. So, I think if I was going to delete something, knowing that somebody might come looking for it, I would leave a comment in the place where that code was that says, this has been deleted, go look at the GitBlame for it or whatever.

[00:26:49] **Adam:** And now you have a line to fire. Because then you can, yeah, you can see that you'll have a diff from that commit that says, okay, this comment was added and these lines were deleted. I mean, a lot of his

[00:26:58] **Tim:** comments about code, uh, comments.

[00:27:02] **Adam:** His comments about code comments, yep. Comments about code comments.

[00:27:04] **Adam:** Yeah, okay.

[00:27:05] **Tim:** Words. Good. Um, have to do with naming, right? So I know we'll talk about naming a little bit later, but if you name something well, lots of comments aren't needed, right? His example was a comment to say, check to see if the employee is eligible for full benefits, and then there's an if statement.

[00:27:24] **Tim:** And then another one where there is no comment, it says, if employee. isEligibleForFullBenefits. Well, you don't need a comment because you have a very good name for that variable. So, I mean, that perfectly makes sense. I just needed someone to tell me it was okay to have long variable names. My whole life, I've tried to have shorter ones.

[00:27:43] **Tim:** Make it short. Yeah. I want to make it short, right? Like, like I'm getting, you know. Like, the code won't run as well if I have too many letters. I'll hurt the compiler's feelings if there's too long of a word. I don't know why. I've always felt that way, that I need to make it a little bit shorter because it looks...

[00:28:00] **Tim:** smarter. But yeah, I mean, he fully embraced the idea of it's okay if it's a longer variable name, that's perfectly fine. And with CodeComplete and things like that that you have now, it's not even a typing burden hardly anymore. Yeah. If you name it right.

[00:28:16] **Adam:** I think I did find that a little bit at odds with his suggestion that, you know, that there is A maximum line width that makes sense, like for in his day, it was 80 characters.

[00:28:24] **Adam:** I think now 120 or something is more common, but still like, you know, he's on one hand, he's advocating you should use variable names that make sense, even if they're 50 characters long. And on the other hand, he's saying, but, you know, in my day, 80 characters now, maybe 100, 120 is max. So like, you could have, you have two variable names on the same line.

[00:28:42] **Adam:** That could be your entire line width.

[00:28:43] **Ben:** Yeah. I use 90 characters, by the way. That's my, that's my traditional vertical

[00:28:48] **Adam:** rule. Okay. I don't

[00:28:50] **Carol:** have a vertical rule. I just go as long as it needs to be. Yep. Yeah. Make it make sense. Cause I'm like Tim. I used to be very, okay. Is rule true that, that you should know is a rule true.

[00:29:01] **Carol:** But in reality, yeah, but what role are we actually talking about here? Are we talking about all rules? Or is this specific to like a service fee type rule? Or is this jaw rule? Yeah, we don't have a clue. So then, you know, when my very first, my very first pull request here was. It's okay to make long variable names.

[00:29:20] **Carol:** This isn't going to help us in the future. So take your comment out and change that to a longer name. And I was like, holy cow, this is the best PR feedback I've ever gotten.

[00:29:29] **Adam:** Yeah,

[00:29:29] **Ben:** nice. I leave a lot of comments in my code and, uh, part of it is for two reasons. One is I think that I often think about telling a story.

[00:29:39] **Ben:** And that the code tells a story and that the comments tell a story. And I, and I know one of the feedback items is that sometimes the story that the comments tell and the code story start to diverge and that becomes problematic. Um, but, but I also, one of the analogies that I have in my head is the idea of a turning lane at an intersection.

[00:29:59] **Ben:** Sorry, you have four roads coming together and there's one lane that can say only turn left. And to the person who's in that lane, that's super obvious. They think to themselves, I have to turn left, I'm in the left turn only lane, that there's absolutely nothing confusing about that. Because that's their perspective of the world.

[00:30:17] **Ben:** But to all the other people on all the other lanes of these roads coming together, they might not realize that you're in the left turn only lane, which is why you also should have your left turn signal on. Because you're signaling to everybody else, I'm in the left turn lane, I'm making a left turn, even if that's legally the only thing I can possibly do right now.

[00:30:36] **Ben:** And, and I look at comments a little bit like that, that as you're writing code, it's very obvious to you what that code is doing. And there's only one possible interpretation because it's the interpretation that your brain just created, but to the next person who's coming, that might not be obvious to them, or they might not be as experienced a developer, they might not understand all of the reasons that the code can only be doing this one thing.

[00:30:58] **Ben:** So I like to leave a comment, hopefully not a terribly redundant comment, but a explanatory comment that says, and here's why this code is doing this type of thing, not necessarily why it's being implemented this way, but, but generally speaking. This is the left turn signal to your left turn only lane.

[00:31:15] **Tim:** Yeah, but Uncle Bob would tell you, you should just have better named variables and functions that are only doing one

[00:31:20] **Carol:** thing. And your code should read in a way that if you were to read the comment, you'd get the same thing from your code, so.

[00:31:25] **Ben:** Maybe it's um, it's a journey. Maybe I'll get there eventually. I

[00:31:30] **Adam:** agree.

[00:31:31] **Adam:** I'm there with you, bro. Something I wrote in that blog post about the dead code. It was a

[00:31:35] **Carol:** good post, by the way. I will say that. Thank you. I really enjoyed it, yeah.

[00:31:38] **Adam:** I think something that resonated with a few people that read it was this comment I had at the very end that knowing what the rules are can be beneficial because then you can follow the rules but also knowing what the rules are is useful because then you can better understand when it's appropriate to ignore the rules or to break the rules.

[00:31:56] **Adam:** Yeah. Because, you know, it's one thing to know the rule. It's another thing to know why the rule exists and, you know, what is it actually trying to do to help you. Rules are like guardrails, right? They keep you from driving off the side of the road. But you can still do it. But right, yeah, sometimes there's, you know, that metaphor totally broke down.

[00:32:15] **Adam:** Whatever.

[00:32:16] **Tim:** Well, I mean, if your enemy, your nemesis is on the other side of the guardrail, sometimes you just have to go over there. Jump

[00:32:21] **Adam:** the rail. Yeah.

[00:32:22] **Carol:** You still get out of it. You just don't want to.

[00:32:25] **Ben:** I will say, and this goes, I guess, beyond the comments conversation, but he did make a comment that, that if you need to leave a comment, sometimes it is a failure of the language itself to be sufficiently expressive.

[00:32:39] **Ben:** And that to me feels a little bit, I don't agree with that because I think there are perfectly fine, um, semantics within a language that don't necessarily tell you why you need to do something. And then one of the things that pops in my mind is this idea, I have an array of items and I can push items onto the end of the array, or I can prepend items or unshift items onto the front of the array.

[00:33:00] **Ben:** And semantically speaking, those things are really easy, whether it's in JavaScript with unshift and push or in CodeFusion with append and prepend. But there might be real algorithmic reasons why you're appending versus prepending. And the language doesn't know that. And I think sometimes you got to have a big juicy comment that says, Hey, I'm doing an append here and not a prepend, or maybe more specifically, I'm doing a prepend very specifically because I need to do a certain type of algorithm that's processing these items in a very particular order.

[00:33:30] **Ben:** And like, I feel like no, No name of a variable or name of a function is going to make that obvious.

[00:33:36] **Adam:** Maybe. Yeah, I mean, it would, it would depend entirely on the algorithm that you're implementing and what's going on, that story that you're telling. But I think that if we had Uncle Bob in here right now, he would probably tell you like that one little action that you're doing in some method.

[00:33:53] **Adam:** You need to refactor that out into another method. Mm-hmm. , then you name it, whatever that method name is, should explain why. Right. The, the method should kind of give you, I don't, I'm not saying I agree, but I think that that's the impression that I got from reading. And the other thing is like, that is a perfect example of the type of opinions that you will find in this book.

[00:34:11] **Adam:** They are, yeah. Sometimes you go what? Really? Like, yeah. He has no shortage of hot takes.

[00:34:19] **Ben:** And I tell you, and I think there also is a breakdown in terms of. the type of languages that I use versus the type of languages that he use. Yeah. So for example, he talks about the, and I know we're kind of wildly off topic at this point, but, but in terms of like the number of arguments That's the show.

[00:34:37] **Ben:** Nobody's surprised here. In terms of the number of arguments that you, should pass to a function.

[00:34:42] **Adam:** Oh, we'll get there. Oh, we're gonna get to that. That's actually coming soon. It's gotta come.

[00:34:46] **Ben:** But just as, as like a point of illustration. So he talks about, oh, if you have too many arguments, probably a number of them have to be refactored out into another data structure class that you would then pass in.

[00:34:56] **Ben:** But then I program traditionally in, in CodeFusion, where CodeFusion, one of the beautiful things about CodeFusion is that you can invoke a function with both ordered And named arguments. Not at

[00:35:07] **Adam:** the same time, but the same function. Right,

[00:35:09] **Ben:** right. Either way. Same function can be invoked in two different ways.

[00:35:12] **Ben:** So sometimes if I do have functions that have five, six, seven arguments, which is entirely not unheard of, to be honest. Then I switch from ordered invocation to named invocation. Yes. Suddenly it's very clear how I'm invoking that thing. So I wouldn't need to break out a separate data structure just to make arguments more clear because of the language that I happen to be using.

[00:35:33] **Ben:** Yep. And, and so some of those things to me, as I'm reading the book, I feel like I can do a little checkbox or no checkbox in my head as like it does apply to the languages that I use.

[00:35:43] **Adam:** Right. Yeah. Something I was kind of saving for a time that it made sense to bring it up was that this is a very Java centric book.

[00:35:51] **Adam:** And you can tell that a lot of the opinions in here are formed by the way that C and Java are written. And I think if Java had that feature where you could take the same method with 20 arguments that are defined in it and call them positionally or... with named arguments. Or argument collection. Or an argument collection.

[00:36:10] **Adam:** Kid's favorite. My favorite. Then, then that would have influenced his opinion, right? And I think that knowing your language is an important thing too, right? Like, what is the goal of saying there should only be so many arguments or, you know, whatever the thing is. And I think we won't get into that here soon, but like, again, there's the rule, but why is the rule?

[00:36:33] **Adam:** What he's suggesting here. Right. And it's in order to keep readability up so you don't have to remember, oh, the 16th argument was the one that I care about here, right? It's, you know, the whatever foo controller or whatever. One

[00:36:45] **Tim:** thing, one thing he said that you should comment, which I totally agree with.

[00:36:49] **Tim:** Is if you have like some sort of pattern matching or regex, just put a comment there and say, what are you checking for?

[00:36:54] **Carol:** Yeah, because it doesn't make sense when you read

[00:36:56] **Tim:** it. I'm like, you probably spent, unless you're Ben Nadell and like dreaming regex, you probably spent 15, 20 minutes, maybe a couple hours building this regex to do it.

[00:37:06] **Tim:** Why should I

[00:37:07] **Adam:** just look at that? And it's just 20 characters. What are you

[00:37:09] **Tim:** comparing here? Star backslash N. Open bracket. GLD. Open bracket. Close bracket. A through Z. I don't know what you're looking for, dude. Just put it in the comments. I've never ever in a code seen someone say. I'm matching here

[00:37:23] **Carol:** for this.

[00:37:23] **Carol:** I'm just trying to see if it's a com or net. Like, you know, that's all I'm trying to get here. Yeah.

[00:37:28] **Adam:** What I do to get around that, instead of a comment, is in languages that support it, I will create a variable that contains that regex. type, or in ColdFusion, you can do regex in a string. And I'll create a variable name that describes what this regex is looking for.

[00:37:42] **Adam:** And it's like email address regex, if that's what you're looking for. And then you, okay, match against email address regex.

[00:37:48] **Carol:** So then you almost could do like a, like a custom function for it or whatever, and be like, go find, go find, at, this is my regex for at domain. So when I'm looking for my domains, I would just always call the domain function.

[00:37:59] **Adam:** Yeah. All right, let's move on, because we've been on comments for a long time already. This

[00:38:04] **Carol:** is why Ben said, this is going to take multiple episodes.

[00:38:06] **Tim:** One episode on comments.

[00:38:08] **Adam:** Oh, it's going to take us a year to get through this whole book.

[00:38:12] **Tim:** Because I have a feeling functions is

[00:38:13] **Adam:** going to get funky. Yeah, so functions is the next section.

[00:38:16] **Adam:** Functions are fun. And it's the first three letters. The, the very first one is, uh, functions have too many arguments. And this to me was, it screamed Java, right? So like his, he's got the rule. Functions should only have, um, well, he says best would be no arguments. Then you have one. Yeah, yeah. Best would be zero.

[00:38:37] **Adam:** Uh, followed by 3. And more than 3 is very questionable and should be avoided with prejudice. And to me, when I was reading that, I just had like a klaxon going off in my head. And I was thinking like, this is a Java person saying that you need to have like a factory that creates a class where you fill in your data and you pass this class.

[00:38:59] **Adam:** Class instance into the method and that's your one argument. I'm like, no, I'm not doing that. I'm not going to that, that world. That's just, you know, to me that was like, that was the, the, the Java flag went up and I'm like, nope. I took,

[00:39:12] **Tim:** I felt like I passed this one, but only out of failure, because like I said, I only pass one argument usually, and that's usually the argument collection.

[00:39:21] **Adam:** I hate that. That's cheating. Yeah, it's sort of cheating. I'm like, what's in this thing? Right, yeah, it's like

[00:39:26] **Tim:** if, you know, there's an error, it's probably just something you needed to add to your argument collection, so yeah. I realized that I wasn't following this principle at all. Um, and I tried this, this past week, I've definitely tried my best to do that.

[00:39:40] **Tim:** And then with, with some success, but yeah, that forces you. And I think the intent here is it forces you to continually stop having a function do more than one thing. Yeah. Right. If you need a whole bunch of, you need a whole bunch of parameters and arguments being passed to it, it's obviously having to do multiple things with those.

[00:39:57] **Tim:** So. If you aren't doing that, then...

[00:40:02] **Adam:** My mind goes to like a data access object, right? Where you're updating a database table and you've got... You know, 30 columns, you're going to be updating those from 30 form fields. Like, yeah, I could put all that into a class instance and pass you that class instance, but why not just make them arguments to the function?

[00:40:17] **Adam:** And here you go, update these. And then it just puts them in the query. Like, why should I go through the trouble of defining and creating a class instance, using the extra memory for that and the extra time to, to keep that and maintain it? Versus like, here, here's the primitives and you know, just dump them.

[00:40:33] **Carol:** Update that down the road. They have to then define the same arguments. If you made it a class, it's now shareable.

[00:40:39] **Ben:** But there's a degree of indirection, which I think can almost add more confusion. Yeah. Where instead of passing eight arguments, you're passing one instance of something, but now you have to go look up what that one instance of something

[00:40:51] **Adam:** is.

[00:40:52] **Adam:** Yeah, it's like argument collection is only worse. I hate

[00:40:56] **Carol:** argument collection. Do not. Don't get me started there.

[00:40:59] **Ben:** But I, I mean, generally speaking, all things being equal and other such cliches, uh, I do like smaller arguments lists if possible,

[00:41:09] **Adam:** but. I'm not advocating for a hundred argument. You know, functions here.

[00:41:14] **Adam:** And, and I think

[00:41:14] **Ben:** about even just the kind of the perimeter of my application. So one of the things that Uncle Bob talks about, not necessarily in this book, but in other things about this idea of an application core, and then there's the web app as sort of the delivery mechanism for the app core. And things like the views and the controllers are kind of just routing data into this app core.

[00:41:36] **Ben:** Like sometimes a lot of data has to come inside that perimeter. And I think about the application that I work on a lot where every request into the app core has to pass in like the current user ID. And the company context in which this is being called and maybe an IP address. And that's like, before you even get into the reason that method is being called in the first place, like that's just the data that requires identification of the current authenticated user.

[00:42:04] **Ben:** And I, and I go back and forth. I'm like, I could wrap that up into some sort of like requesting identity or something, but again, I just come back to this idea that one, probably not every single request in my application is going to have that same exact structure need. And now I just have to go and look that up again to see what it's being, what it includes.

[00:42:24] **Ben:** Instead, I can just have the arguments right there. And it just feels like sometimes the, the co location of data is more important than the elegance of the data.

[00:42:35] **Adam:** Yeah. I feel like sometimes best practices can be at odds with one another. When you were describing that, I was thinking about Um, Encapsulation versus, so like what you're saying, you know, you have these, let's just say like four arguments you need to pass in just to set the context of the request and then you need to make the request as well.

[00:42:56] **Adam:** Right. And the sort of visceral, immediate, like, okay, well, if we wanted to avoid putting those four arguments to most functions, then let's put it in request scope or session scope or something like that. But then you're breaking encapsulation and, and so, you know, you kind of have to figure out what is the right balance or which rule doesn't make the most sense to break here.

[00:43:15] **Ben:** Absolutely. And I, going back to the request scope, which is a ColdFusion concept, but I think Java has a concept of, of session scope or something. And like Node has a concept of domains, which I believe is very similar. I have such a love hate relationship. I fought against it for so long, but now I'm like, But did I make a lot of bad decisions because of wanting to avoid the request scope?

[00:43:37] **Ben:** Like, would request scope actually made my life a lot easier in certain ways? And I think probably it would have, but I don't know, it just feels dirty somehow.

[00:43:44] **Adam:** So the next one in here is output arguments. And I don't think that your average CFML developer is going to be familiar with what those are. I don't ever use them.

[00:43:53] **Adam:** Um, where I'm familiar with this from is, if I remember correctly, in C. Or C You could pass an argument into a method, and either the function definition, or maybe it was both, you could add like a special character to say this is going to be passed by reference instead of by value, and then I'm going to modify it in the function, and when I do that, the modification is available to the call and code.

[00:44:18] **Adam:** It doesn't have to be returned or anything like that. I'm modifying that variable in place, and that's it. But it

[00:44:23] **Carol:** has to be defined, it has to be defined as the output for that to happen?

[00:44:26] **Adam:** In some languages. I don't

[00:44:28] **Ben:** think it's that it's defined as an output, more so is it's, it's like the calling context provides an argument to which that method is going to write data.

[00:44:38] **Adam:** Okay. Did that make sense? Um, in, in ColdFusion, if you pass an array to a function, that array gets copied for the lifetime of that function, and the, the function operates on that copy of that array. Okay. But if you pass a structure... That structure, it like passes the function in the memory location of that structure.

[00:44:58] **Adam:** And if you make a modification to that structure in the function, you don't return it, you don't do anything special. You just modify that structure. It is modified in the code that was running before and now running after that function. That's called passing by reference instead of by value. And so, If you know about that, you can use it to your advantage.

[00:45:17] **Adam:** I had that as a bug in one of my earliest attempts, failed attempts at an open source project. And it beguiled me for maybe months before I figured out that was what was going on. I had no idea that ColdFusion supported passing by reference. Struck copy. Yeah. Um, anyway, uh, I agree with what he says in the book that, you know, output arguments is just a dumb idea asking for trouble.

[00:45:42] **Adam:** I don't see any reason to use that.

[00:45:44] **Tim:** It's not terribly explicit, right? And that's sort of his thing about clean code. Your code has to be

[00:45:48] **Carol:** explicit. Yeah, I want to see what it's doing. I don't want to have to figure out because it was an output argument that it changed there.

[00:45:55] **Adam:** Right. Like going to Ben's, um, storytelling, uh, metaphor, like you're, it's not clear.

[00:46:02] **Adam:** If you're writing the code in a way that tells a story, this is, I'm running this function, this is the data that I'm giving it, it's not clear that I'm giving it this data, but it's also getting data from that function in that same spot of code. And I think that that's, that's what makes it bad. Uh, anything on flag arguments or dead functions?

[00:46:18] **Ben:** Yeah, I think so. I, I generally agree with, I try to avoid flag arguments, but every now and then.

[00:46:24] **Adam:** I use them. So he says flag arguments, boolean arguments, loudly declare that the function does more than one thing. They're confusing and should be eliminated. And I think that that is true as long as the boolean is indicating that there's a fork of code of, you know, potential fork in the code inside the method.

[00:46:38] **Adam:** But sometimes there's a reason to pass a boolean. That's not because the function does two things. Sometimes it's because you need to put a true or false in the database. Right, right.

[00:46:47] **Ben:** Well, I think about, um, in one of the other chapters, he talks about error handling and, uh, one of the ways that I've seen this come up in my particular code base, which I honestly can't stand is this idea of passing in a Boolean that will suppress errors.

[00:47:02] **Ben:** And I would much rather have seen two different functions. And one is like, do the thing. And then the other function is like, do the thing and suppress errors. And that way they take the same exact argument list and one very explicitly catches and logs errors instead of letting them bubble up or something.

[00:47:18] **Ben:** Yeah. And

[00:47:18] **Tim:** flag arguments tend to lend to a system that has lots of magic numbers. Because, you know, if you can do more than one thing, well, what are they? Is it one thing? Is it five things? Is it

[00:47:29] **Ben:** ten things? It's interesting. Like, even Lucy CFML has, uh, It's system output function, which will write to the standard output.

[00:47:38] **Ben:** And then it has two Boolean arguments. One is for whether or not it should add a new line. And then another one for whether or not it should use the standard error instead of the standard output. And I could just as easily see, like a lot of Java code will have a print function and then a print line function, which explicitly adds the new line.

[00:47:54] **Ben:** And I, you know, I have these little mental gymnastics in my head where I'm like, how could I rename the system output function to be more clear? So it doesn't have to have two Boolean functions. But. You know, again, sometimes, sometimes it just feels like it's easier to have Boolean values.

[00:48:08] **Adam:** Okay, I think this next one is going to be interesting.

[00:48:11] **Adam:** Multiple languages in one source file. So to me, when I was reading this section of the book, what was screaming in my head was the modern CSS in JS thing that people are talking about a lot. What do you guys think? I

[00:48:23] **Ben:** personally like separate files, but I get, I mean, I understand the appeal of having multiple languages in a single file for front end components, but it's not my personal preference.

[00:48:33] **Ben:** I like the

[00:48:33] **Adam:** separation. Yeah. So, I'm, I'm a fan of CSS and JS specifically because... I maintain a ton of CSS that I have no idea if it is actually being used or not. And the idea of, Oh, we don't need this component anymore. We delete the component and it takes the CSS with it. Super appealing to me.

[00:48:52] **Carol:** See, that's good.

[00:48:53] **Carol:** I do like that idea. Well,

[00:48:56] **Ben:** not, not to get too off the rails, but there are, there's a difference between technical implementations and for example, Vue. js, which you can have a template at the top of the file and a style block at the top of the file. I think you can also in Vue. js, instead of having those in line, you can have like a template tag with a URL and a style tag with a URL so that the, it would be three physically separate files, but they all act as a single component.

[00:49:22] **Ben:** And then to your point, then you can just delete all these together. Yeah, take out the whole section. So I think there are, there are. Technical implementations that don't necessarily have everything together, but now we're kind of off the rails.

[00:49:34] **Adam:** Yeah, I mean, I think it's a discussion worth having though.

[00:49:37] **Adam:** So like the, the CSS and JSS thing, it looks like css, you know, it, it, there's a lot of different ways you could take this. The, it looks like c s s, but really it's just JavaScript that's affecting the style. I don't know.

[00:49:48] **Ben:** Well, the one that he brings up I think very specifically is the, um, H T M L inside of the comments that are at the tops of functions that sort of act as.

[00:49:57] **Ben:** In code

[00:49:58] **Adam:** documentation, like in the Java doc

[00:50:00] **Ben:** stuff, um, which I don't know, I, I don't write Java and I don't document a lot of stuff.

[00:50:07] **Tim:** Okay. I mean, this just yelled to me what it was kind of designed that way from the beginning. So I honestly don't know how you get around it, but I mean, a CF, a traditional CFM page from back in the day was really a mix of CFM and HTML.

[00:50:20] **Tim:** And JavaScript and CSS. I mean, yeah, you got four or five languages going on this one. cfm page, but I mean, that's the way it was designed. So I don't know how you get around that, uh, in that case, but in general, I definitely agree that, you know, having, it just confuses things when you have too many

[00:50:37] **Ben:** languages in one file.

[00:50:38] **Ben:** Well, and, and I think this sort of actually dovetails with one of the other things, which is where he says. Clean code is code when you open it, and it does kind of exactly what you expected it to do. And to me, to Tim's point, that ColdFusion was sort of built for this idea of being this delivery mechanism for a lot of things.

[00:50:55] **Ben:** When you open a CFML template and it has some ColdFusion code that's interlaced with HTML code that it's rendering, to me, that's like, that's what you expected it to do. Where it gets really weird for me is when I include a JavaScript file and then suddenly there's, uh, like a link tag in the head of my HTML output.

[00:51:13] **Ben:** I'm like, where'd that happen? Yeah. Yeah. Like to me, that feels really weird because that is not at all what I expected to happen. So, so I guess it, it sort of depends on, on whether it's surprising to me. Okay.

[00:51:25] **Adam:** Uh, overridden safeties.

[00:51:27] **Carol:** Oh, I loved listening to that section. Yeah? Yeah. Because of the Chernobyl references?

[00:51:31] **Carol:** Chernobyl melted down because they overrode the safeties. If the safeties are there, abide

[00:51:37] **Ben:** by them. I don't really have anything to add though. Yeah. Safeties seem good.

[00:51:41] **Adam:** Yeah,

[00:51:41] **Carol:** safeties are there for a reason. Yeah.

[00:51:43] **Tim:** Compiler warnings, he talked a lot about that. And you know, in Scala there, and unfortunately I'm not as good enough in Scala right now to understand why, but there's one, it gives me every time I compile and I've never had a problem because of it, I don't think, it's a warning, right?

[00:51:58] **Tim:** It's just a little warning. Not a failure because it still compiles, but basically it's saying that the match case on a certain statement is not exhaustive enough, so there's probably a case that it's

[00:52:07] **Adam:** not being accounted for. So you're, what you're telling us is that you are not an agile software craftsman, Tim.

[00:52:12] **Adam:** Yeah, I, I, yes. Because you're ignoring compiler warnings. You're an expert

[00:52:15] **Carol:** at that with me.

[00:52:16] **Tim:** Yeah. Yay. Yeah, right? So, and I look at that every time and I go, gee, I wonder what that's like. But I've been looking at that same message for every time I compile on our Scholar Project. Five, six years now. I'm like, one day I'll figure it out

[00:52:28] **Adam:** or it'll just go away.

[00:52:30] **Adam:** Yeah. Suddenly

[00:52:30] **Carol:** that match will be there.

[00:52:32] **Adam:** Magical thinking. Somebody else will fix it. Don't worry. All right. Next one is duplication. So, you know, dry code. I mean, I don't think anybody's going to argue with that one. Right? Don't think.

[00:52:47] **Ben:** Okay, so early on in my career, when I heard the concept of DRY, Don't Repeat Yourself, I took it to heart before I feel like I fully understand what it was trying to explain. And I ended up making a lot of bad decisions in the way that I organized code in honor of DRY. And it ended up making my life harder.

[00:53:07] **Ben:** Oh

[00:53:07] **Adam:** yeah, I've been there.

[00:53:08] **Carol:** So like you tried making it too inclusive?

[00:53:11] **Ben:** I, I think the thing is, I didn't understand what DRY was talking about in terms of duplication. Okay. I think, to me, when I think about DRY, I think about business logic, and I don't want to necessarily have the implementation of business logic in too many places, because then they can fall out of sync.

[00:53:32] **Ben:** But code that looks the same to me is not necessarily Always duplicated. And I sometimes find if I try to err too much on the side of refactoring things out, then it can make the code much harder to understand and maintain sometimes. So I guess I do like dry, but with lots of caveats.

[00:53:51] **Adam:** If you take a naive approach to it, and you're just like, Oh, I've been told I can't repeat anything ever.

[00:53:55] **Adam:** Then it's easy to dig yourself into a really bad hole. Yeah. Awful code that it's impossible to maintain. And again, going back to, you have to understand that this rule is here for a reason. And what is that reason? And it's to prevent you from getting code that's... actual duplicates of logic out of sync from each other.

[00:54:13] **Adam:** And, you know, if, if that is what you keep dry, then you're fine. If you have the same logic to sort two or three or five different tables differently, and it doesn't matter if they get out of sync with each other because they're not related to each other, then that's fine.

[00:54:25] **Carol:** Well, one of the examples he gives is like, if you have this big if else block or this case statement, the switch on it.

[00:54:32] **Carol:** Um, that, if you're seeing that duplicated everywhere, like if I am this user type or I'm this user type or I'm that user type, maybe you should just pull that out to its own block of code that's always executed rather than having it duplicated throughout the system.

[00:54:47] **Adam:** Right.

[00:54:48] **Tim:** I actually, you know, had this thought when I was this past week when I was building this helper function.

[00:54:53] **Tim:** My helper function was calling the API that I built. Of course, every API is going to be doing some gets, some posts, some patches, and some puts. And I found myself rewriting a block of code that was kind of doing the same thing over and over again. I'm like, wait, this should just be a function, right? A function that can take whatever I pass it in multiple circumstances and do the correct get.

[00:55:14] **Tim:** Push, not push, put, pull, whatever. Um, and so I, I did that. I broke that out and then made it so much simpler. All of a sudden, then I realized, well, all these, they're really doing the same thing. This should really just be a separate file in itself. And now, now that it's a separate file, it's inheritable, you know, or it can extend it.

[00:55:31] **Tim:** And so now I'm using polymorphism to make sure that. And after I did that, I found that I was deleting other sections of code. So I was deleting, and all of a sudden, some functions that were like maybe 10 lines of code got down to like, I was honestly just calling the function, passing an argument, and then my return line was calling the thing I just wrote.

[00:55:49] **Tim:** And that's what I love when it's just a three line function, it actually does something. I think

[00:55:53] **Adam:** that's the goal with this block.

[00:55:54] **Ben:** One of the places where I think over indexing on DRY has caused a lot of problems at work. is with the idea that database queries that look the same are repetitive. And I think this is one of those cases where you have to understand not just what the database is getting, but the context in which it's actually getting that data.

[00:56:11] **Ben:** And if you take just a made up example of something like a user table or an account table and just say it has 30, 30 columns in it, just for the sake of discussion, I might have a user interface that's administrative where I need all of those columns. And I might have another interface in my application that only displays like the ID and the name and the sign up date for that user.

[00:56:31] **Ben:** Mm hmm. I don't necessarily want that UI to pull back all 30 columns. Agree. And I certainly don't want to start creating database methods that start taking Boolean flags where it's like, get me this user. But don't get me these columns or like get me this user and then a Boolean for like, get me extended data because now it becomes a total nightmare to what that's supposed to be doing.

[00:56:51] **Ben:** And the person who put that in quits the company. Now, no one understands what extended information is. So queries, SQL queries or database queries in general are one of those things where I will actually prefer duplication over dryness because oftentimes those queries, while they look the same, have very different intents, especially in terms of performance.

[00:57:11] **Ben:** Metrics and like this one can pull from a primary database because it can't possibly have stale data. But this one can pull from, say, a read replica because staleness would be okay if it gives us better performance and doesn't have to have up to the millisecond accuracy. So those two queries, I might have two queries that have the same exact SQL statement, but have different implications in what it means if those data is returned.

[00:57:35] **Ben:** In different performance characteristics or different staleness characteristics.

[00:57:39] **Carol:** So I just recently did something with that. Um, I duplicated an entire get function only because I don't want the data. I just want to know if the data exists. And I was worried if I did a top on the query just to see whenever it came back that someone wouldn't understand that I don't want the data, that down the road there would be some confusion.

[00:57:58] **Carol:** So I would kind of like talk to my guys and like, what do you think about just duplicating it and this being rather than get the data, this is, does data exist? So now you can always call it and just say, does this record exist? Do I have any children of this type? If so, all I care about is yes or no. I don't want to pull back all the data that you're getting.

[00:58:17] **Carol:** I'm just going to say yes or no to it. So we kind of did the same thing and we decided it was better to duplicate rather than Just getting the top on it and seeing if it was there.

[00:58:25] **Ben:** Totally. I've, I definitely have a does exist type functions that just return a select one,

[00:58:31] **Adam:** oftentimes. Okay. Have we beat that horse enough?

[00:58:36] **Adam:** Sure. Vertical separation. If

[00:58:38] **Ben:** this is the one he's talking about, where like functions that call other functions to be right next to each other in the code, I, I hard pass on that. I find that to be very...

[00:58:47] **Adam:** Yeah, so he says local variables should be declared just above their first usage and should have a small vertical scope, meaning like they shouldn't be declared on line 30 and used on line 3000, even if they were also used on line 32.

[00:59:00] **Adam:** I,

[00:59:01] **Ben:** I do agree with local variables being declared right near their usage. So maybe this is a different one. There's one where he's like if one function calls another function, that that second function should be defined right below the first one. And I'm just

[00:59:14] **Adam:** like. They just say private functions should be defined just below their first usage.

[00:59:18] **Adam:** Private functions belong to the scope of the whole class, but we'd still like to limit the vertical distance between invocations and definitions. Right, so as you're reading the code, right, as I'm coming behind you and reading your code, I see a UDF here function for something. Like, what does that do? I should be able to scroll down, it should be one of the first few functions after the current function.

[00:59:36] **Adam:** Not always. That's what he's saying.

[00:59:38] **Ben:** So here's my thing is that's one of those organizing code within a file, I think is very challenging to do over the long term. So I've sort of just decided I will never be good at that. So I said like, okay, now my public functions will be at the top and my private functions will be at the bottom and everything will be listed alphabetically.

[00:59:57] **Ben:** Because I will never have to make a decision about

[00:59:59] **Adam:** that it's consistent, right? Yeah. If you're consistent across the whole code base, like, okay, yeah, it's not right underneath this, but you know exactly where to find it. Yeah. And

[01:00:06] **Carol:** see, I don't even do alphabetical. I just go to the last one so that it's always the newest function added to the bottom that you can see whenever you're looking at it.

[01:00:13] **Carol:** It's not, why did I pick it in between the middle of these? Why did I put it there? It's just... And

[01:00:19] **Adam:** who doesn't have CTRL F or CTRL R, right, to be able to find a function by name. CTRL R. Hover

[01:00:26] **Carol:** over it, find

[01:00:27] **Adam:** references. Yeah.

[01:00:29] **Tim:** Just because my habit has been, I declare all my

[01:00:32] **Adam:** local variables at the top. Yeah. Well, there was a time when that was absolutely necessary in CFML.

[01:00:36] **Adam:** Right. I would

[01:00:38] **Tim:** do it. Maybe that's just a vesicle tale of doing that, right? So I, you know, if I got my function, I got my arguments being passed as a function right below there. If I'm creating any local variables, I just do it right there at the top and then I use them later. But I mean, if you're practicing what he says here, your function shouldn't be that big anyway, right?

[01:00:56] **Tim:** So, you know, what's, what's, what's the harm if you got a 10 line function and you're at the very, you know, Very top, you're creating a local variable. What's the harm in it being on line eight when it's used, right? So it's small. So I, but yeah, if it's a bigger one, I could see that, but yeah, the, I, I, I'm with you, Ben, I do the same thing.

[01:01:13] **Tim:** All my public functions are at the top. I have a comment that says private below and down the bottom are all my private functions. And I think probably my, my reason for doing that is because I think my private functions are the functions that really. only matter to the things at the top that are using it.

[01:01:34] **Tim:** And those public functions, they're what I'm exposing to the, to the introspection in the world. I mean, that those are the things that can be used. Right. And so that's typically what another program is going to care about. It's like, Oh, here's my function. That's doing this thing. I'm going to look at that first and then it's like, oh, it's calling this other function.

[01:01:51] **Tim:** Where's that? Oh, it's at the bottom. It's private. So I get it. I can agree with

[01:01:56] **Adam:** it, but it's like,

[01:01:57] **Carol:** I was going to, I feel like if I open the file right now in my code base and it was like public, private, public, private, I'd be very annoyed. Because it's not the way we structure it. I mean, it's just not what makes

[01:02:07] **Adam:** sense to us.

[01:02:08] **Adam:** I indent all of my private functions an extra three levels. Just three tabs. No, I'm just screwing with you. Three more tabs. That way you can tell by, by at a glance that they're private.

[01:02:21] **Carol:** I'm sweating now.

[01:02:24] **Ben:** I do think, so one of the things that he mentions, maybe like halfway through the book or something, um, when he's talking about, uh, the law of Demeter, where you're not supposed to call.

[01:02:34] **Ben:** methods that call other methods. Like you're not supposed to chain methods yourself. He does clarify that there is a difference between classes and data structures. And then classes expose behaviors in addition to data and data structures just expose data. They have no behaviors whatsoever. And that the whole reason for being for a data structure is to expose its own structure.

[01:02:57] **Ben:** And so he's like, if you have a data structure and you have to like top level node in this tree dot something else, dot something else, dot something else, like as long as that's all contained within the data structure, it's not violating the law of Demeter and, and kind of along the same lines. He also talks about sometimes writing procedural code just makes sense.

[01:03:14] **Ben:** I agree. That there's this, I think he even says like in the book, every object oriented programmer understands that not everything should be an object, and that object oriented code is not always the easiest thing to do. And that sometimes you just need data structures, and you just need procedures that work on those data structures.

[01:03:30] **Ben:** And I almost wish that that was presented earlier in the book, because I think that's actually a really important context in which to think about a lot of this stuff. And this is something I also really wish I had thought about earlier in my career. That sometimes you're just taking data out of the database and jamming it into a data structure that I can render on the page.

[01:03:50] **Ben:** And it has very little to do with business logic and it has very little to do with constraints around mutating state. And like, I just want sometimes a component that's like 600 lines long because all it's doing is taking data and putting it into the right format and aggregating it in the right way for a very specific view.

[01:04:07] **Ben:** And this is not going to be reused anywhere else. And I'd rather have that all in one place. I'm not sure if people are going to use that, but it's a really, really good resource. Thank you for having

[01:04:23] **Adam:** me. That's awesome. And

[01:04:26] **Ben:** I'm going to stop sharing my screen. Bye. And, and I think small makes sense sometimes and really big also makes sense sometimes.

[01:04:37] **Ben:** Agreed. I think it's two different styles of programming and, and one is not inherently better than the other. Fight. Like I, I have, I have a component somewhere that is taking a bunch of rows out of the database that have a parent child relationship and it's turning them into this tree of data. Mm hmm.

[01:04:58] **Ben:** And then it's cross linking nodes within that tree. And it's. only ever going to be done in one particular view inside the application, and it's really complicated to do, and I think that component is like 2, 000 lines long. Oh, wow. And I don't think, if I'm very honest, like I don't think breaking that up into several classes would have helped me solve that problem in any way that was more elegant, because it's just like brute force data aggregation.

[01:05:22] **Ben:** Sorry, now I'm getting emotional.

[01:05:24] **Adam:** Yeah, it reminds me of our method that we use to... Submessages for delivery email messages, it's, it's a big thing, you know, go from a list of people to a bunch of emails that need to be sent and you got a rendering and exclusions for unsubscribes and all kinds of other stuff.

[01:05:39] **Adam:** You know, there's just. A lot of steps in the process. And yeah, you could break each thing down into a bunch of individual methods. But then instead of being able to read the code linearly, you find yourself jumping around. Okay, like this is the next function I have to go read. Like, okay, what does that do?

[01:05:52] **Adam:** Okay, maybe that's not the problem. Okay, what's the next function that it calls? And so sometimes there's benefits to just having the code all right there in one long function. Okay, next up, inconsistency. Boo. I like inconsistency. Keep it exciting. Do things every different way. Put your public and private classes

[01:06:09] **Carol:** together.

[01:06:09] **Carol:** I don't care.

[01:06:11] **Adam:** No, I don't think anybody's gonna poo poo on... Asking for more consistency.

[01:06:15] **Carol:** No, always. Like I said, if I open up a file, I want it to look like the other files I look at. I want to be able to read it the way I read something when I open the other file. Yep,

[01:06:25] **Adam:** yep. Clutter. I think everybody is going to go ahead and say that that's a good thing to get rid of.

[01:06:30] **Adam:** Yep. But you know,

[01:06:31] **Tim:** some people are scared of deleting. They are. Honestly, they are. I agree. They're like, oh, I don't want to delete this. It might be used. And that's usually just. I mean, a result of cargo gulping and not understanding how the code works. Like, well, maybe it gets called somewhere. But that one place, I don't know about.

[01:06:47] **Tim:** Did you do a search for it? Is that function being used anywhere? No, I couldn't find it. All right. Why are you gonna not delete it? Well, I don't want to get in trouble.

[01:06:56] **Ben:** Yo, to, to his point, he does have a section about using searchable names. Yes. And I was like, I almost cried when I read it. I love it. I

[01:07:05] **Carol:** love it.

[01:07:05] **Ben:** I'm like a thousand percent. Yes.

[01:07:07] **Adam:** Yeah. So, okay. So that was a lot. Uh, we've only really kind of scratched the surface here. We're definitely going to have to break this up into at least one more episode because we are. Only up to G, what, 12 out of It is a good book. There's a lot of stuff here. Yeah. So, uh, at least one more episode coming your way on this topic.

[01:07:28] **Adam:** Uh, but for now, I guess we're going to have to call it a night. So, uh, before we get out of here. Uh, there are a bunch of people that like what we're doing here enough to support us by sending us a few dollars every month on Patreon, and we really appreciate them. You should know that every dollar we've received through Patreon, we're reinvesting in the show and we have a goal that we're working toward, which is that we really want to be able to pay an editor so that I don't have to do the editing every week.

[01:07:52] **Adam:** Um, I would guess that we're going to need at least twice what we're bringing in every month right now to be able to afford to do that. So, uh, another way of putting that would be that we're halfway to that goal, right? Yay, you guys rock. Yes, thank you. Um, uh, so yeah, we need more people to jump on. If you like what we're doing, then please help us out there.

[01:08:12] **Adam:** Um, we have other goals for the future as well. So we're going to require even more money. Like one of the things that I would love to be able to provide for people, um, maybe people that are hard of hearing or something is transcripts. I think that that would be a nice thing that we could do if we had the money for it.

[01:08:24] **Adam:** Cool. Um, so, uh, if you would like to kick in a few dollars, if you think we've earned it, you can find us on patreon.com/WorkingCodePod. Uh, we do have a new patron this week, so Peter, thank you for coming aboard. Um. Peter! You're going to do that to the man after he gave us a bunch of money?

[01:08:43] **Carol:** Peter, why did you spend the money?

[01:08:46] **Carol:** Oh dear. He's a top level patron,

[01:08:47] **Adam:** right? He is, he's top tier. Yeah, yeah. So, our patrons get perks, like an invite to our Discord server, early access to new episodes, the after show, and like I mentioned earlier, we get together and play games sometimes. And, you know, whatever else random stuff, hey, come on, we're working on it, uh, we're working on it.

[01:09:04] **Adam:** And, and we would like to get together more often, but it's just kind of random and whatever else we might think of along the way, you know, that is our, that's our, our tight knit community sort of thing. And that's who we, uh, focus on most of our extracurricular activities. Outside the podcast energy on so our top tier on Patreon is for people who want to pay a little bit extra and in exchange we'll say almost anything they want us to say.

[01:09:25] **Adam:** Uh, I was trying to convince Peter to, uh, force Ben to say that feature flags are dumb, but he didn't want to put him through that trauma. Thank you. But, uh, so right now we have one, uh, sponsored shout out and, uh, that would be womenwhocode.com. Yeah. And, uh, so to everyone else that's just listening to the show, thanks for listening.

[01:09:46] **Adam:** Uh, don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review, you know, wherever, whatever country you're in, we'll try and find it. And a rating on iTunes or wherever you get your podcasts.

[01:10:00] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until then, your heart matters.

[01:10:34] **Tim:** Internationally known, but I'm known around the microphone. I think it's

[01:10:38] **Ben:** rock the microphone. Yeah. What's that from?

[01:10:40] **Adam:** Sounds like a Beastie Boys reference. Definitely not James

[01:10:43] **Carol:** Bond, I know

[01:10:43] **Adam:** that. So, I mean, you can, some, at the where, mm, ramble, ramble, ramble, stumble, stumble, stumble. Tim, we lost your video. He's picking his nose, or his butt.

[01:10:56] **Adam:** Both, with the same finger. That's deep. I hope not, geez. Did

[01:11:03] **Tim:** we skip obvious behaviors unimplemented?

[01:11:05] **Adam:** Oh, I guess I did. Good

[01:11:06] **Carol:** job, Adam.

[01:11:09] **Adam:** Did you have something to say about that one? No, I just, I don't know if I can

[01:11:13] **Tim:** skip it.
