---
title: "178: Upgrading From Node 0.10"
description: "This week on the podcast, Ben has been incrementally building a data export feature for his customers. Carol has discovered that if she doodles circles with her non-dominant hand, it frees her up to focus on reading. Tim is continuing to improve his AI voice-agent. And, Adam is battling some pretty steamy code rot."
date: 2024-05-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/178-upgrading-from-node-0-10/id1544142288?i=1000655655203"></iframe>

This week on the podcast, we touch on a variety of topics. Ben has been incrementally building a data export feature for his customers; and, he's gotten to a point in which he can see a viable light at the end of the tunnel. Carol has discovered that if she doodles circles with her non-dominant hand, it occupies the ADHD portion of her brain and frees her up to focus on reading. Tim is continuing to improve his AI voice-agent, using a listener-suggested approach to loading Spanish language voice models on demand. And, Adam is battling some pretty steamy code rot; and is attempting to upgrade a series of interconnected Node.js Lambda functions from v0.10&mdash;released in 2013&mdash;to v20.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/178-upgrading-from-node-010.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** so currently I believe that like not LTS, but also not bleeding edge release of Node is 20, And the, the version of Node that is in this particular application that lambda function, is 0.

[00:00:12] **Adam:** 10.

[00:00:14] **Ben:** Oh, chickens.

[00:00:15] **Adam:** it's been, it's been running 0. 10 in production for far too long. because that was the bleeding edge at the time, and that's what we really needed.

[00:00:25] **Ben:** This is like 10 years ago though, right?

[00:00:26] **Adam:** Yeah, something like that.

[00:00:28] **Ben:** Oh my goodness.

## [00:00:49] Intro

[00:00:49] **Adam:** Okay, here we go to show number 178, and on today's show, we have everybody back. welcome back. Wait, you were here last time, Carol. Damn

[00:00:56] **Carol:** Yeah, your calendar's wrong, I think.

[00:00:59] **Adam:** my brain is wrong. know what, we're gonna stick with it. Everybody's here still, and again. and, as usual, we'll start with our triumphs and fails, and Ben, it looks like it's your turn to go first.

## [00:01:10] Ben's Triumph - Exporting User Data

[00:01:10] **Ben:** Yeah, I'm going to kick us off with a triumph and that is, I have been working on this exporting feature at work. So as I've talked about in previous episodes, company is end of life at the end of 2024 and as a sort of hat tip and a thank you to the customers, I'm trying to, Come up with a way for them to more easily get their data out of the system, should they want to keep it.

[00:01:33] **Ben:** And, I didn't really know what this feature was going to look like or how it was going to work, but I just sort of believed that I'd be able to figure something out. So I just started solving a little bit of problem here, building a little bit of UI over there, throwing a database table together over here, and just iterating until something started to take shape.

[00:01:53] **Ben:** And I have gotten to a point where I can see the light at the end of the tunnel. one of the big hurdles for us was going to be the sheer volume of data that some customers have. We have a non trivial number of users that have in the thousands of documents in the system. So we really had zero mechanisms for considering data of that volume, especially since a lot of these data are images.

[00:02:21] **Ben:** And it's not unusual for someone to say generate an export of a document that is a couple of hundred megabytes in size. So how do we do that on a scale where it's thousands across then tens of thousands of customers? So at first I built something that would just generate one export at a time and send it out in an email.

[00:02:41] **Ben:** And that was sort of a proof of concept that I could start to build the underlying logic around. And obviously I knew that wasn't going to scale, but again, I just sort of had this faith that I would be able to figure something out. And, I don't have a perfect solution, but what I'm, I'm going with now is that someone will be able to create an S3 bucket.

[00:03:00] **Ben:** Then they'll obviously have to sign up for an Amazon account and create the S3 bucket themselves. And that sucks. I mean, that's quite a hurdle, but if people really want to get their data out, we can give them a little walkthrough on how they can do that. And they can create a private S3 bucket. So it doesn't have any public access, right?

[00:03:16] **Ben:** People can't read or write their data. but you can, even with a private bucket, you can. Edit the bucket policy and we can say, Hey, here is our Amazon account ID, or, you know, some form of it. All you have to do is copy and paste this one little JSON snippet. And it says, give this account, read and write access to your bucket, and you can keep it entirely private, but we'll be able to write to it.

[00:03:40] **Ben:** And then what they'll be able to do is queue up all of their prototypes. And then we'll just have some background processes that start generating these These exports and sending them from our EC2 nodes over to their S3 buckets. And, I got a proof of concept working. I'm just pretty excited about it.

[00:04:00] **Ben:** It's, it's pretty great to actually see data show up and have all the right error handling when, one of the things that I had to do was, was add a validation step, kind of going back to what we talked about last episode, I don't want to start making requests to a bucket that. I'm not supposed to, and because I'm making it on behalf of an InVision account, I also don't want them to like, give me one of our own buckets.

[00:04:24] **Ben:** And then I just start exporting data from like one production bucket to another production bucket simply because it quote unquote work. So part of what they have to do is they have to just upload a simple text file. Like, kind of, I'm sure everyone here is somewhat familiar with the, The, what is it?

[00:04:39] **Ben:** The cert bot, the, like the Acme cert bot, where you have to have a, a well known location that you can prove through your site before they'll allocate an SSL certificate for you for

[00:04:49] **Adam:** proof you control this

[00:04:50] **Ben:** Yeah, yeah,

[00:04:51] **Adam:** this file on it, and we'll expect it there,

[00:04:53] **Ben:** I'm doing the same kind of thing where you have to upload a text file and I have to be able to read it to make sure that it's there.

[00:05:01] **Ben:** And then I have to be able to write a file that says I've verified that this file exists and that way I can prove. That they both have access and ownership of that bucket and that they've given me the right bucket and I have access to it as well. And once that, yeah, go ahead.

[00:05:15] **Adam:** is there any risk that somebody could figure out or, or give, like, give you a bucket name that they don't have, that they don't own, control.

[00:05:26] **Ben:** the, the way that I'm approaching that now is that the file, the, the validation file that they have to upload is essentially their userid. txt. So you would have to convince someone else to upload a file with

[00:05:41] **Adam:** it's not just Envision. txt. It's,

[00:05:43] **Ben:** Right, right,

[00:05:44] **Adam:** yeah, that makes sense. Okay. That way, like, if I happen to know that Timco is a, is an Envision customer and that they're probably going to be interested in doing this, I can just like,you know, request an export 20 times and, and get, you know, cause the 20 times the bandwidth and all that.

[00:06:00] **Ben:** Yeah. Yeah, a hundred percent.

[00:06:02] **Tim:** can you name the file? Guess what? And have the response file be

[00:06:05] **Ben:** it's chicken, but I'm not against it because we're riding this baby into the sunset, so there are no more rules. But anyway, I'm, I'm, I'm just excited to have actually made some progress where, again, the user experience is not going to be fantastic. It's not like in a perfect world, I think what would have been great is for someone to be able to generate something like a Dropbox share link, and then just paste that Dropbox share links into our system.

[00:06:38] **Ben:** And I'd be able to. You know, send all of the exports over to their Dropbox. Share links don't work that way. Unfortunately, I'd have to do some sort of OAuth dance where they would have to authenticate us against their own Dropbox account and then we have to store OAuth tokens and I, I don't want to do any of that.

[00:06:57] **Ben:** That's just sounds like a lot more work.

[00:06:59] **Adam:** Did I miss where you explained why you can't just like put this in your own S3 bucket and let them download it from there?

[00:07:05] **Ben:** yeah. So the initial proof of concept actually does do that. So. There is one avenue where instead of sending it as an object, we generate it, store it on our own S3 bucket, and then send them an email with a link, and then the email times out, the link in the email times out after. A certain period of time because I'm storing it in a, we have like a little temporary slice within our S3 bucket that we have a background process and it just deletes files that are past a certain date, which

[00:07:36] **Adam:** will self destruct.

[00:07:37] **Ben:** yeah, quick aside, you can actually set bucket policies that do that.

[00:07:41] **Ben:** But this is all in a very old production bucket and everyone at work is 100 percent afraid to simply add a policy, even if it's at the prefix, like anything below this path has a, has a self destruct. Everyone I've talked to is like, can we not do that? That seems like it can only hurt.so the, the, the big issue that we're considering in that case is simply the added cost, like actual dollars and cents cost of.

[00:08:09] **Ben:** Essentially duplicating a lot of our files and storing them back into our S3 bucket. That was the really nice thing about having them enter their own S3 bucket, is that they can keep that data for as long as they want and it doesn't cost us anything. And I'm, and I believe that sending files from our EC2 nodes to their S3 buckets might be no cost as well.

[00:08:35] **Ben:** I know S3 has some, some constraints about like egress costs.

[00:08:40] **Adam:** there's like a bit, a billion rules. And if you do it

[00:08:43] **Ben:** Yeah. Yeah.

[00:08:44] **Carol:** Yeah.

[00:08:44] **Adam:** free stuff. Yeah.

[00:08:46] **Ben:** So that, that was the big factor. Cause cause a hundred percent. If we didn't have to worry about the cost, or I should say, like, if we weren't trying to be vigilant about our cost savings, I would absolutely just be storing them on our own S3 buckets and sending them links. In fact, I could do all of the exports, generate a manifest file or something, and then just send them this giant manifest that they could access or something.

[00:09:09] **Ben:** I don't know. The other thing to consider was just because we can generate the export and store it somewhere, we also wanted to make it. Like that's, that's still not the last mile that gets it to a place where the generated document is persisted, but then they still have to, in theory, get the generated document from the persistence mechanism to their local computers or their local storage drives.

[00:09:35] **Ben:** and the nice thing about them having their own S3 bucket was that S3 can basically act as an FTP server. So you could take something like FileZilla or I use, for something called Forklift, just, you know, it's just an FTP client and I can connect to my S3 bucket, like it's an FTP and just download all those files the same way that they could.

[00:09:56] **Ben:** So there were a lot of benefits to having them be responsible for the storage. It also.

[00:10:03] **Tim:** it's cheap. It's cheaper

[00:10:04] **Ben:** Yeah, it's very, it's a hundred percent cheaper and it's also, we remove all the time constraints because we, you know, we're still going to shut everything down December 31st. So even if they generate the exports, those exports would all be deleted if they don't get them into a place that they own.

[00:10:22] **Adam:** Have I talked on the show about how. I currently get a bill every month from AWS, it's like 11 cents or 7 cents, something like that. Uh, personally or for work.

[00:10:32] **Adam:** that I'm storing on S3, however, it is on an account that I am unable to log into. And because it's only like seven cents a month, it's just not worth my effort to try and like talk to support and get it sorted out.

[00:10:45] **Adam:** I actually have done a little bit of trying to talk to support, but it's their support stuff is so messy. Like, have I talked about this at all?

[00:10:51] **Tim:** That's why Jeffrey Bezos is a billionaire. Stuff like that.

[00:10:54] **Ben:** 11 cents at

[00:10:55] **Adam:** seven cents.

[00:10:57] **Tim:** Isn't that the plot of Superman 4? Yeah.

[00:11:01] **Adam:** Oh, maybe, maybe we can get into that. I'll put it down as a possible topic for the after show, or if not, maybe we can get into it a little bit on, on, on another show. I

[00:11:10] **Ben:** It's interesting to think about all this end of life stuff because, so S3 for listeners who are not familiar, it's not a flat pricing model. There, there are like a million different pricing options for S3 based on how durable the objects have to be. Like how likely it is that they will get deleted accidentally, whether or not versioning is installed, how often you access thing, how big they are.

[00:11:35] **Ben:** or not they can exist in something like Glacier, which is not really S3, but it's a different type of storage. And so at work we use something called, I think it's called like infrequent access model, which is where things within things that are used frequently have a different price, and then if you haven't accessed them, I think within 90 days, they drop down automatically to a lower infrequently accessed price.

[00:12:01] **Ben:** So in theory, you can store things. Cheaply, even more cheaply if you don't access them. But then the problem is if you then go to access those infrequently accessed objects, it's actually more expensive to access them than it would be normally. So this is one of the things that we're a little bit gun shy about with

[00:12:20] **Tim:** Opaque pricing is brilliant.

[00:12:21] **Ben:** it's, it's crazy.

[00:12:23] **Tim:** for the company. Hmm.

[00:12:28] **Ben:** feature, we, we kind of have a sense of how much, I mean, we have an absolute sense of how much things cost us a day because we get our bill every month, but what happens now when all of these objects, you know, potentially hundreds of thousands of objects of decent sizes, which were infrequently accessed are now being accessed in order to generate these exports, is there going to be suddenly a large unexpected bump in our price? I don't know. I know that we do pay a lot for S3 as is. So,

[00:12:57] **Adam:** know you have mentioned that, you know, you have a significant number of customers that have a significant number of documents. What is the difference in generation time for one of these backups that you're generating between a customer who has, let's, you know, call it minimal to typical data versus one of these like whales who have all the data?

[00:13:18] **Ben:** I mean, so I have a bunch of test documents that are very small and they get processed, like before I can even hit refresh on the page, they've been processed. I do have access to one customer gave me access to a document cause they were actually having performance problems in the app itself. And they have like close to 3000 screens in their prototype, which is, I mean, I don't, I don't, I don't mean this in a dismissive way, but that's like absurd.

[00:13:46] **Ben:** I can't imagine building a prototype that has 3000 screens in it. It's all these little micro interactions, but they're, you know, full size screens. And if I generate the export of that, the document generated document itself is like 1. 2 gigs.which is gigundo and that's, you know, this is the very high end of, of what we would ever expect.

[00:14:09] **Ben:** And even,

[00:14:09] **Adam:** it take?

[00:14:10] **Ben:** even that can be exported in like 20, 30 seconds.

[00:14:14] **Adam:** Man, for 20, 30 seconds, I would not even hesitate to say, your own, your one and only choice is you click export and you wait. And then a zip file downloads in the browser. That's it.

[00:14:28] **Ben:** Well,

[00:14:29] **Adam:** if it's a gig,

[00:14:30] **Ben:** no, no, a hundred percent. the issue though, is that's one document and, and people might have hundreds of documents, if not thousands of documents, they'd have to do that.

[00:14:38] **Adam:** you're writing them separately,

[00:14:40] **Ben:** yeah, yeah. So, and, and when I'm, when I'm generating the export and I'm sending it to their S3 bucket, I'm still doing it one document at a time, but they can queue up in the background, essentially all of the documents that they have access to, or that's, that's the part I haven't quite understood yet is how I want this scoping to work.

[00:15:00] **Ben:** Like the queuing mechanism and the thing that generates the documents, that's all done. But now do I, do I want to use her to say, for example, Be able to look at a list of, Hey, I have 1200 documents. Can I pick and choose which documents I actually want to export? Cause that now that becomes a different kind of user experience problem that I have to solve.

[00:15:19] **Ben:** Or is it you're exporting everything you have access to period. Like if you want to filter it, you're doing it later, not on our

[00:15:26] **Adam:** right?

[00:15:27] **Ben:** But it's tough too, because I have such a range in possible user experiences, meaning the user that owns five documents. They can very easily want to come in and say only export four of them.

[00:15:39] **Ben:** That would make sense from a user experience standpoint, but the same rule just doesn't apply to someone who has 3, documents. It's all fun stuff to solve and to think about. And, and I'll tell you, I love the fact that this was all built incredibly incrementally to the, to the point where I had a database table and I put some indexes on it and I started to write the code that was going to consume that table.

[00:16:03] **Ben:** And I realized those indexes didn't make sense. So I just dropped all the indexes and it was already in production. I just dropped all the indexes and I started adding new indexes. And I just, I get so thrilled when I've sort of let go of all the fear of changing something just because it's reached production already.

[00:16:21] **Ben:** And I, I find that to be very healthy.

[00:16:24] **Adam:** yeah, you sound super chill. is this like, it sounds like you've kind of reached this Zen of like, it doesn't matter. You know, I've got a certain amount of time and stuff's gonna happen. It might be good. It might not.

[00:16:35] **Ben:** Yeah, absolutely. I mean, it, you know, I, I sort of almost started on this project just to like justify my time. I don't want them paying me to be here. I got to be building something. So, but I'm just excited about where it's going. I'm excited that I might actually build something useful instead of, you know, spending a couple of months trying to build something and then it not panning out at all.

[00:16:58] **Ben:** All right. So that's me. Triumph. Carol, what do you got going on?

## [00:17:04] Carol's Triumph - Focus Techniques

[00:17:04] **Carol:** mine's gonna be much shorter.

[00:17:06] **Ben:** Sorry.

[00:17:06] **Carol:** So, uh,no, I'm sure it will be. I am zonked from all the moving and stuff, so words are, are not working very well.I'm gonna go with the Triumph though. I have a hard time reading. whenever I read a book, I tend to just zone out and it's hard to focus, so that's why I usually do, like, Audible subscriptions or audiobooks or I'll listen to YouTube videos because I do that way better than reading.

[00:17:33] **Carol:** Well, I've been trying a couple of different things and I finally found one, one thing I can do that lets me read and pay attention. So, with my non dominant hand, which is my left hand, if I take a pen to a piece of paper and just kind of start drawing circles, I'll slowly stop focusing on what my hand's doing and it'll keep fidgeting and like drawing or whatever, but while I'm reading, I'm actually paying attention.

[00:17:59] **Carol:** And when I stop, that's when I start daydreaming. So I used to do bidget spinners, like the spinny ones, but then I would just end up moving it to my right hand and it's playing with it too much. And then I want to play with the dog and it just doesn't really work so well. So I found that if I take a pen And just start doodling while I read with my left hand, I can focus on the words and get through a lot more before I start daydreaming.

[00:18:23] **Tim:** Did you come up with that on your own? Was that like recommended by some study or paper or something?

[00:18:27] **Carol:** Oh yeah, this is just straight up Googling things. I don't have anything specific. I was just, I, I'm constantly looking at, basically my searches are usually like how to hack your brain when you have ADHD and I look for things that people post, Sometimes it's TikTok videos, sometimes it's Instagram, sometimes it's a post on Reddit that I'll go to.

[00:18:48] **Carol:** It's just different things, nothing official. It was just one of the things I'd saw and I was like, let's give it a try this week. So this weekend I did it and I was like, holy cow, this actually works for my brain.

[00:18:59] **Tim:** That's pretty cool.

[00:19:00] **Carol:** Yeah,

[00:19:01] **Ben:** I, I have heard, several times now that motion helps you focus, like walking or even just kind of,no one can see what I'm doing when they're listening, but I'm sort of like bobbing back and forth a little bit. But apparently there is something about motion that changes the, your ability to focus. I

[00:19:21] **Tim:** Yeah. When I'm on the phone, I have to pace.

[00:19:23] **Carol:** I pace on the phone. Mm hmm.

[00:19:25] **Tim:** me pay attention.

[00:19:26] **Ben:** I sometimes, I feel like I do my best thinking when I'm out walking the dog, and she's kind of doing her thing, and I'm just staring at the cement, and it's moving slow and just kind of letting my mind race, so I totally get that. I mean, I could never try to draw and read at the same time, but, but I can understand where you're coming from.

[00:19:46] **Carol:** The drawing isn't actual things. It's mostly little circles and lots of just lines. Like if you handed a two year old a pen and said, draw a picture, it's pretty much what it looks like.

[00:19:56] **Adam:** the rest of the owl.

[00:19:57] **Carol:** No, no, it just scribbles.

[00:20:00] **Tim:** If little side digits, you called it, you know, looking up. Brain hacks or life hacks. So many, I got to tell you guys, Gen Z, what you call life hacks are just kind of how things are supposed to be done that you just didn't know. Okay, guys, they're not life hacks. You're, you, you haven't broken the matrix.

[00:20:18] **Tim:** You haven't seen the wall behind the code. You just kind of figured something out that pretty much everyone else knew because of life experience. So sorry.

[00:20:26] **Adam:** hack. If you put your soap back on the soap tray, it won't all melt away in the shower.

[00:20:29] **Tim:** Whoa.

[00:20:32] **Ben:** I'll tell you though, I am beginning to fear that I'm losing the ability to read, and I don't mean that I'm not, I don't mean that I can't read words, but that the skill of sitting down and sitting through a book and going from page to page without getting so frustrated that I'm not doing something else.

[00:20:50] **Carol:** Yep.

[00:20:51] **Ben:** because I listen to podcasts so much, because I focus primarily on audible, like you're saying, I, I do feel like I should get a physical book or at the very least get a Kindle book so that I can practice that movement, that I can flex that muscle a little bit.

[00:21:08] **Carol:** Yeah.

[00:21:09] **Carol:** I was gonna say, my whole reason for wanting to get back into reading like actual books, I did the same thing. I bought a new Kindle. it's because I feel like I'm losing a lot of my vocabulary because I don't use it and I don't write it ever. I hardly ever read it. I listen to it and hear it. But then when I go to write out You know, very detailed steps for, like work for technical documents.

[00:21:35] **Carol:** I'm finding that words get hard after a while and I use the wrong tense all the time. And yeah, so I'm like, I got to get back into reading just because my brain needs that stimulation and I need to make sure I'm not losing a part of that.

[00:21:52] **Ben:** Yo, can we leverage that to do a little quick tangent on AI? Because that's exactly how I've been thinking about all of the chatbot stuff lately and the, and the code generation stuff. Is. yes, at the end of the day, we have to be producing these products and fulfilling business requirements. There's so much more to me, to, to code and to creating solutions and to thinking through problems than just putting the code on the page.

[00:22:22] **Ben:** And that's one thing that I actually have been quite concerned about is that when we're all becoming these chatbot architects, that we're gonna, we're gonna lose that muscle for having the syntax and for thinking through the deep problems and for. Taking the dog for a walk and letting your brain go on a half hour tangent about solving a particular problem.

[00:22:43] **Ben:** And that's very, in the same way that I feel like I'm losing the ability to read. I feel like our software engineer is going to lose the ability to engineer. And I don't think that's hysterical. I think, I think there's something there. I don't know.

[00:22:59] **Carol:** I feel like the, the more skilled engineers are going to use it, just like in my example is always spellcheck, you know, I write a document. I don't care if it's spelled right. Cause I know spellcheck is going to get that. I'm going to get the swiggly lines and I'm going to go fix it. And for me using something like Copilot or any type of program that's going to help me generate code.

[00:23:22] **Carol:** It's not going to stop me from thinking through it because it's how my brain works and it's what I enjoy. Like I enjoy doing that. So I'm going to keep building on whatever it generates, or I'm going to go learn from what it's done. I wouldn't just say, okay, that looks right. Throw it on the page and move on.

[00:23:39] **Carol:** It would be, let's see how. How this program came up with a solution versus what my solution was. But I do see what you're saying with other people. It may not be that way.

[00:23:50] **Ben:** Well, that's exactly, cause we're of the generation where, you know, We didn't have this before, so we had to build that muscle, and we have so much historical movement around that gesture, that that will never not be part of the process. You know, you see young kids sometimes, and they just seem, just in life in general, like, completely helpless.

[00:24:11] **Ben:** Like, they don't even know how to order their own food at a restaurant. And, and, And, you know, is the next generation of programmer is going to start to become more like that because they didn't have that historical, you had to do it yourself and, you know, walk uphill to school both ways kind of a thing.

[00:24:29] **Tim:** I was about to say, you're starting to sound like a little cantankerous old man here. Back in my day,

[00:24:34] **Ben:** I don't know. And then sometimes I feel like maybe all of that is just me.you know, justifying my lack of interest in the AI stuff,

[00:24:43] **Tim:** didn't have these fancy scripting languages. We wrote in assembler and we liked it.

[00:24:50] **Ben:** I was talking to this old lady one time on the sidewalk in New York city. And, she referred to the phones as the jabber boxes. She's like all, all these kids today walking around with their jabber boxes. I was like, Oh, Oh, Oh, It was like the best thing I'd ever heard.

[00:25:11] **Adam:** Can I, can I pop us a few layers off the stack here and go back to one of the previous tangents in

[00:25:16] **Ben:** do.

[00:25:17] **Carol:** Yeah, yeah.

[00:25:18] **Adam:** yeah, I want to go back to, like the, the Talking about reading a physical book and, and kind of like feeling broken. The way that I feel broken is like, if I'm trying to put my attention on something and I don't have something for my hands to do, like I'm, if I'm really interested in trying to watch a particular TV show with my wife or something.

[00:25:38] **Adam:** I find myself sucked into my phone, right? I'm either scrolling on Facebook or I'm doing a Sudoku or whatever. And like 10 minutes into it, I'm like, why am I doing this? It's making me miss the show. And I actually care about the show, but it's like my, I think I've kind of hacked my brain in a bad way where like by doing podcasts and audio books constantly, when, when I'm doing something that doesn't require My full attention, and I, you know, if I'm moving around, doing the dishes, or going for a walk, whatever, I've kind of trained my body to expect, like, all of the inputs all of the time.

[00:26:13] **Adam:** And so, like, when I'm trying to just, just do visual audio input, it's like, wait a minute, you're not doing anything with your hands. You gotta, you gotta keep yourself busy. And I hate it. I feel broken.

[00:26:23] **Ben:** Yo, a hundred percent. I, I've noticed. So a show is not a hundred percent in your face the entire time, right? The engagement of a show, even within a single episode, it ebbs and flows. There are times that are very exciting. There are times that are, they're just building backstory for the next exciting part.

[00:26:39] **Ben:** And I have felt that so hard where the moment I'm not fully engaged with what's going on, I just absentmindedly reach for the phone. And I think to myself, I can sort of pick up whatever backstory they're laying down in the background while I check my, my Facebook feed. And I, and I do, I have to stop myself.

[00:26:56] **Ben:** I'm like, this is disgusting. Just sit and enjoy the show. That's why you're here. And it's, it's really hard sometimes to do that.

[00:27:04] **Adam:** Did we finish Carol's, Triumph?

[00:27:07] **Carol:** I think so. I think so.

[00:27:09] **Adam:** doing some left hand doodles. Nice.

[00:27:11] **Carol:** about you, Tim? What you got?

## [00:27:14] Tim's Triumph - Silver Anniversary

[00:27:14] **Tim:** Well, I got a pretty big one, actually two. so this week we're recording, you know, this is middle of beginning of May. this 25th wedding anniversary, my wife and I,

[00:27:25] **Ben:** Oh, congratulations.

[00:27:27] **Tim:** So yeah, the silver wedding anniversary. So. That's exciting. And, we do anniversaries kind of like Christmas around here. So we get presents and kids get presents and the wife gets presents and I get presents and kids give us presents.

[00:27:41] **Tim:** And, but I know what I'm getting. I'm getting a 3d printer. So

[00:27:46] **Adam:** Did you pick it out? Is that why you know? Or?

[00:27:48] **Tim:** They're like, what do you want? I'm like, I want a 3d printer.

[00:27:50] **Adam:** Oh, okay.

[00:27:51] **Tim:** I've wondered what, they're always like, you always buy the things that, that, that you want beforehand. And I'm like, all right, I'm purposely telling you a year in advance.

[00:27:59] **Tim:** I want a 3d printer. And if you don't buy me one this year, I'm buying it afterwards.

[00:28:05] **Carol:** Do you have a big like, Oh my God, I want to do this right now. As soon as it comes out of the box kind of project.

[00:28:11] **Tim:** yeah, just Lily wants to do for her graduation. So this week's super busy. There's graduation award ceremonies and the tomorrow, the United Way does an eagle award thing that she's going to win. And then, so she wants to give. To all her friends that are graduating. Just she wants to 3D print some little tchotchke for them.

[00:28:30] **Ben:** Oh, that's nice.

[00:28:31] **Tim:** as a gift, a memory gift.

[00:28:33] **Carol:** Super sweet.

[00:28:34] **Tim:** And then just to let you guys know, because this will probably affect the podcast, we will be going in the summertime. We'll go, all of four of us will go to Ireland for a month.

[00:28:44] **Adam:** Oh, it's nice of you to invite us.

[00:28:46] **Tim:** Yeah, no, yeah. Come on, come visit.

[00:28:47] **Adam:** The four of us are gonna go to Ireland, huh?

[00:28:49] **Tim:** Yeah. Yeah. Of all four of us, the, the Cunningham, four of us, not the working code, but four of us.

[00:28:55] **Tim:** Yeah. We're going to. Going to Belfast, so visit family. So that'd be nice, but work wise, so I'm still playing around with my AI voice agent. I've been having some fun with that. It's kind of, kind of cool playing with, and I got to, thank some of our patrons because on the early, what's it called?

[00:29:14] **Tim:** Early access channel where they just, I think it got released today. Someone actually gave me some pretty good advice. One of the challenges was having was, Switching to Spanish,

[00:29:23] **Carol:** Oh yeah.

[00:29:24] **Tim:** And someone said, could you play a recording? Cause I can't, if I switch the language, it's just, you'll still use the English voice, but do it saying Spanish.

[00:29:35] **Tim:** It sounds funny. play a recording that says, if you want this call in Spanish, please say. You know, please repeat this in Spanish or please call me in Spanish, in Spanish, obviously not in English. And then if they respond with that, then I can hang up and then just call them back using a full Spanish language model and talk to them in that.

[00:29:57] **Tim:** So I was like, that's a pretty good idea. So thank you. Thank you, patron. I forget who that was, but, that was. I appreciate that. That was a good idea. I've been playing with that today. 'cause I can do a URL to an external, to a a, mp3 audio file, play that, and then tell the, AI prompt that if they say this term in Spanish, hang up and then call back using the other language model.

[00:30:21] **Tim:** Well, actually what it would do, I would do a callback to my API and it would fire off a separate call.

[00:30:27] **Carol:** Oh,

[00:30:28] **Ben:** Very cool.

[00:30:29] **Tim:** I didn't think about that, but they made that a suggestion. I'm like. Yeah, absolutely could do that. That, that sounds good.

[00:30:34] **Ben:** You think all these companies that have telephony services, I think they're all built on Twilio at this point?

[00:30:41] **Tim:** Probably.

[00:30:42] **Ben:** Because I know Twilio had something where you could link to an mp3

[00:30:46] **Tim:** Yeah. I mean, most of them do. I use, we use Twilio. We, we use Plum and we also use, Plivo, which got by Twilio, got bought out by Twilio. So it's Twilio, basically again. So,

[00:30:57] **Adam:** like startup names from Silicon Valley TV show.

[00:31:00] **Tim:** Yeah.

[00:31:01] **Adam:** So. Still playing around with the AI stuff. That's it's pretty fun. And then I've showed it to more people and they're, everyone's pretty impressed with it.

[00:31:08] **Tim:** So just trying to find all those loose corners. So that's me got a 25th wedding anniversary this week, a trip coming up to Ireland and next month, and then,

[00:31:18] **Ben:** you have

[00:31:18] **Tim:** are good.

[00:31:19] **Ben:** a family, like distant family in Ireland? Cunningham, is that an Irish name?

[00:31:25] **Tim:** Yeah. So my. My great grandfather was born in Coleray, Northern Ireland, and then they moved to Scotland when my grandfather was born, but my grandfather was only born in Scotland, he's only there for a few years, so we are, we are Irish, I found the town that we all came from,

[00:31:44] **Ben:** Oh, very cool.

[00:31:46] **Tim:** yeah, but, Yeah, Michelle's, my wife's family, they all live in, well, live, so her sister lives in Belfast, her mom and dad live in, the Republic of Ireland, and she's got aunts, uncles, cousins, all in Wales, Scotland, some in London. Nice to visit them. It's been about five years since we've seen them.

[00:32:03] **Ben:** Very cool. have a great time. When are you doing this?

[00:32:07] **Tim:** next month.

[00:32:08] **Ben:** Fantastic.

[00:32:09] **Carol:** Awesome. Oh,

## [00:32:14] Adam's Fail - Upgrading Old Code

[00:32:14] **Adam:** I am going to go with a fail.

[00:32:15] **Tim:** Oh, one of us had to do it.

[00:32:18] **Adam:** Yeah. Yeah. Today was one of those days, man. It's just been kind of a rough day. I had a couple of, you know, important things to do. And then by the time that I got around to. Writing code stuff. I had kind of gotten pushed off on this other little project.

[00:32:31] **Adam:** you know, so, AWS Lambda updates node versions that are available every so often, and for the longest time, they've been like super far behind, to the point where at one point we, wanted to use a new version of node in Lambda. And it was not available. So we packaged the binary in our upload, like in the code that we send.

[00:32:54] **Adam:** And, and we would just start off with whatever version of Node was available. And then we would do like child process. spawn, call Node. exe and run this other file. And so I am, basically where I am is I'm fixing CodeRot, right? So we've got this code, it's super old, and I'm just trying to like, not only is it super old and, and, you know, I need to make sure that it can run on newer versions of Node, but also like while I'm here, there's just some things about it that need fixing, right?

[00:33:21] **Adam:** It's using some of our older libraries that we've kind of deprecated and, and need to be replaced with newer stuff. And it's written with JavaScript classes, which I just, Can't stand. That's just a personal thing. Like it, it gets on my nerves. I hate the way they work. I hate the way they look. It feels so verbose.it just, it doesn't, it's, it's not my vibe. and so like, I, I'm fixing this code rot and, I mentioned that, packaging the version of Node thing because, so currently I believe that like the current, not LTS, but also not bleeding edge release of Node is 20, if I'm, if I'm not mistaken. And the, the version of Node that is in this particular application that lambda function, is 0.

[00:34:03] **Adam:** 10.

[00:34:05] **Ben:** Oh, chickens.

[00:34:06] **Adam:** it's been, it's been running 0. 10 in production as like a child process for far too long. because that was the bleeding edge at the time, and that's what we really needed.

[00:34:18] **Ben:** This is like 10 years ago though, right?

[00:34:20] **Adam:** Yeah, something like that.

[00:34:22] **Ben:** Oh my goodness.

[00:34:23] **Adam:** It's, it's crazy. and it just, it's a, it's a rat's nest, right? So it's like, it's these two sort of communicating applications. One's a lambda function, one's a container running on Fargate, and the container will spin up a couple of threads and, and manage those threads in lambda.

[00:34:43] **Adam:** and, and like they're, they are what does the work. The container is just sort of like driving the bus. And, So there's, there's a lot of code sharing between them because they need to be able to kind of work with the same services. So the, the person that originally wrote this code was like, Oh, you know, since we're going to have a lot of overlap here, I'll just like have one services folder in the repository and it gets copied into both projects as they get deployed and then, and then, so you've got like.

[00:35:12] **Adam:** A class with like 70 methods on it and maybe 20 of them are used for, for one of them and 30 of them are used for the other application. And then there's all these other methods that like get called by one or the other or both sides. It's just, it's a rat's nest and you've got, so you've got classes that are then using instances of other classes.

[00:35:32] **Adam:** This is where you start to think like, Oh, dependency injection, like Ben was talking about last week. But. And if you write your code this way, I can see why you need it. But if you write code like I like to write it in Node, it doesn't feel so necessary. but man, it is driving me nuts. I, so it's like, I was trying to come up with a strategy for how am I going to get this done?

[00:35:53] **Adam:** So my, my idea was I'm going to work like the, the CPU. I'm going to open up the, the root file and I'm just going to start, okay, this is the file that I need to process. I'm going to start reading lines of code and say, okay, can I. Can I, convert this file from old and busted to new hotness? And if, what the, the things that would make it a no is it's got these dependencies that it's using, or it's got, it's instantiating, instantiating other classes, that, you know, have to take arguments and, and create instances of themselves.

[00:36:26] **Adam:** And then they, they load other classes and they load other classes. So I'm trying to like work my way down the stack here, fix something, fix a leaf node and work backwards. And then I'll, you know, I have to like back up and I get to do a little bit more and then I go, okay, now I'm going down the tree again,

[00:36:42] **Adam:** another leaf node and then work my way back up the tree.

[00:36:45] **Adam:** And it is very frustrating, but I can't think of a better way to do it.

[00:36:49] **Ben:** you're going to run into the situation that Carol had the other week where she's tinkering, tinkering, tinkering, and then she has a PR with 97 files of this.

[00:36:56] **Adam:** I don't think there's going to be another way to do it. Honestly. I mean, this thing, it's not that much code, you know, we're talking about something that like.

[00:37:04] **Ben:** could you literally, so you have the services folder. Would it be crazy to step one is literally just duplicate that entire folder into each repository. And so you can at least create a clean break and then just start pruning it at that point.

[00:37:18] **Adam:** not a bad idea, right? So like, then I can just work on one of the two applications at a time. Yeah, I mean, the other thing is because it's all classes and stuff, like, it's not real easy to, like, break out of that, right? There's no good escape hatch. So I was just, you know, with there being, you know, so many strikes against this stuff, I kind of am trying to do not a full clean sheet, like rewrite, but like, you know, okay, I'm taking this class and I'm just kind of copying the methods.

[00:37:47] **Adam:** Okay. They're out of the class. You know, the thing that kind of maybe rubs me the wrong way is like in a lot of ways, a node module. Acts like a class, right? You can have private methods cause they're not exported. You can have private global variables that are available to the whole file. Like that's, that's kind of what a class is.

[00:38:07] **Adam:** And then, so then you build a class inside it and you just export that class. You're like doubling up. that's one of the things that, that gets on my nerves about it.

[00:38:14] **Tim:** Classes all the way down.

[00:38:16] **Adam:** Oh my God. Anyway, so it's, it's just, I've got a headache. I was very impatient with my family at dinner. It's just, it's been that kind of a day, you know, like

[00:38:26] **Ben:** Mm hmm.

[00:38:30] **Adam:** That's just normal

[00:38:32] **Tim:** That's normal.

[00:38:32] **Carol:** my dog growled when you said that. Jesus.

[00:38:35] **Adam:** I said what.

[00:38:36] **Carol:** Yeah, she was like, you were like, Oh, I was just kind of like grumpy with my family at dinner or whatever, and she goes, Oh, and

[00:38:44] **Tim:** dog.

[00:38:45] **Adam:** So yeah, I mean, that's that's really all I got. It's just been a rough day. and while I It's that's the other thing. It's like, I've got all these, I'm, I'm keeping so many balls in the air, right? I'm still got a couple of things to go on the compliance thing. I've got the, the junior dev that I'm mentoring and supervising project managering, and, and I've got a couple of different dev projects.

[00:39:10] **Adam:** And so like, I know I have to work on this thing, I probably won't be working on it tomorrow. Or if I do not, definitely not all day tomorrow. Right. And so this is going to be something that's just going to be backburner.

[00:39:21] **Ben:** All

[00:39:25] **Carol:** I don't know about you, but whenever I context switch off of something like that, where I'm just kind of frustrated with it, when I have to go back to it, I just start getting in a bad mood before I even start the project, I'm like, Oh, I have to get back into that, Oh, it's not going to be a good afternoon now.

[00:39:42] **Adam:** It's, it's such a weird thing because like, when I think about, especially before I started any work on it, you know, I could feel the anxiety building, the knots in my stomach twisting, the headache coming on, but at the same time, like the idea of having this work done and having it completed and coming out the other end with like good tests and maintainable code and all this other stuff, that concept makes me happy.

[00:40:08] **Adam:** So like, I'm so torn and just like, I don't even know.

[00:40:15] **Tim:** Dumb question. cause I'm good for those. so one of our developers, he is working on, we're moving some stuff over from Scala to ASP. net because most of the teams more familiar with ASP. net than Scala at this point, but what he was doing, he was actually had a I don't remember what tool it was, but it was an AI tool that he could put Scala code in and it would export out, print out, the equivalent in ASP.

[00:40:41] **Tim:** net. And it really helped. Is there anything like that you could do to like, say, take this version of Node and make it this version of Node? Or do you have to really re architecture the whole thing?

[00:40:52] **Adam:** Honestly, the things that are different from version, one version of Node to the next would be super simple for me to clean up once I got rid of all the other things that I hate about this code, the, the classes and all that stuff. But you raise a good point. Like, I wonder if I could figure out a way to just drop this into chat GPT and say, like, take this code, convert it to this and this and this.

[00:41:14] **Adam:** It might just be too much, right? Cause like there's, there's so many classes, there's so much context that's kind of getting passed around. I don't know that it's going to be able to. Do that cleanly and I, I mean, I might give it a shot, but I

[00:41:29] **Carol:** I use Telerik. I think it's Telerik, the people who make Fiddler. They have one that will convert VB to C sharp. So when I'm in the old VB code, I'll go in and throw it in and it converts it all over to C sharp for me.

[00:41:42] **Adam:** mean, that would be, that'd be the golden goose, right? Like I would love that, but, I, I have my doubts. I like where your head's at though.

[00:41:51] **Ben:** we're excited to see how it turns out.

## [00:41:53] Patreon

[00:41:53] **Adam:** Alright, well then this episode of Working Code is brought to you by Kids These Days and their Jabberboxes. Listeners like you.

[00:41:59] **Carol:** Yeah,

[00:42:02] **Adam:** more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:42:06] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons

[00:42:13] **Ben:** Monte and Giancarlo.

## [00:42:16] Thanks For Listening!

[00:42:16] **Adam:** if you want to help us out, you can go to Patreon.com/WorkingCodePod, throw a few dollars our way, and it helps keep the mics on, and we would greatly appreciate it. going to do it for us this week. We'll catch you next week, and until then

[00:42:29] **Tim:** Remember, even if Adam's grumpy with you, your heart matters.

[00:42:33] **Adam:** Okay,

[00:42:34] **Tim:** To at least the three of us.
