---
title: "187: Is it Possible to be a Solo Developer in 2024?"
description: "In this week's episode, Adam and Ben talk about the feasibility of being a solo developer in 2024."
date: 2024-07-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/187-is-it-possible-to-be-a-solo-developer-in-2024/id1544142288?i=1000662506148"></iframe>

In this week's episode, Adam and Ben talk about the feasibility of being a solo developer in 2024, considering industry pressures, tools, and personal strategies for balancing simplicity and complexity in the development process.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/187-is-it-possible-to-be-a-solo-developer-in-2024.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** I have vivid memories of like editing my, my website in the AOL website editor, right? Cause you, you have your own space on there and like, you know, putting in that little animated GIF that I stole off the internet of, you know, like proudly written in notepad, right? No line numbers, no syntax highlighting.

[00:00:20] **Adam:** Did the hard way. And you know, looking back now, like that was terrible. But still, you know, I did

[00:00:24] **Ben:** But it was the joy of it,

[00:00:26] **Adam:** Exactly.

## [00:00:46] Intro

[00:00:46] **Adam:** Okay, here we go to show number 187 and on today's show, we are going to talk about whether or not it's even possible to be a solo developer in 2024.with me, seemingly as always, but, at least as usual, tonight is Mr. Ben Nadel.

[00:01:02] **Ben:** Yo, yo, happy to be

[00:01:04] **Adam:** Carol, yeah, Carol couldn't make it tonight.

[00:01:07] **Adam:** Tim is still, winding his way back to the good old Los Estados Unidos from Ireland.and so it's just the two of us tonight. but first as usual, we'll start with the triumphs and fails. Ben went first last week. I really enjoyed your conversation about insecurities with Carol. Good job.

[00:01:24] **Ben:** Thank you. Thank

[00:01:25] **Adam:** but since you, you went first last week, I'm going to go this week.

## [00:01:28] Adam's Triumph

[00:01:28] **Adam:** And I, I got a, I got a good triumph today, so I'm going to need a drum roll here. my, my triumph is, I got my SOC 2 certification. It is done. 2023

[00:01:40] **Ben:** in the making.

[00:01:41] **Adam:** is officially over. It felt like four years for sure.

[00:01:45] **Ben:** Freaking amazing.

[00:01:47] **Adam:** Yes. it shouldn't, it, it, it should not be that level of, of relief.

[00:01:51] **Adam:** But the sad thing is that it is.

[00:01:54] **Ben:** Well, and don't you immediately now have to hire someone for the next, certification? cause I feel like you were shopping around for a new firm, right?

[00:02:02] **Adam:** yeah, so we were not very thrilled, part of the reason that it took so long, and I, I can't empirically prove this, but I, you know, my gut tells me a big part of the reason that it took so long was our auditing firm, was not a good partner for us. I feel like they were well positioned to work better with like a big enterprise business with tons of people on our side and, institutional knowledge about how the process works and.

[00:02:30] **Adam:** Not so much to be working with like a seven person startup who hasn't never done this before, doesn't know, you know, this from that. And to top that, you know, cake with a nice little cherry, the GRC governance, risk management and compliance automation software that we bought, or, or subscribed to for a year.

[00:02:52] **Adam:** I don't know how, you know, how you want to define that in the year of our Lord 2024, but, It could have been better. You know, I had, I have some gripes. We, we signed

[00:03:02] **Ben:** don't even know what this is.

[00:03:04] **Adam:** It's so okay. for the purposes of completing these big audits, SOC2, PCI, SOX, the Sarbanes Oxley,

[00:03:12] **Ben:** you not just running this out of an Excel document?

[00:03:16] **Adam:** It feels like it sometimes, but there, you know, there's probably.

[00:03:20] **Adam:** If you really dug, you could probably find a hundred of these like big deal certifications that you can get. Some of them are industry specific or whatever, but the one that we're, the two that we're focused on are PCI and SOC2.and both of them have a lot of requirements. It's like, okay. for, for PCI, it's like, you know, First, you have to kind of identify where do you fit into the puzzle of the ecosystem, right?

[00:03:46] **Adam:** Are you a

[00:03:47] **Ben:** Yeah, because

[00:03:48] **Adam:** are you a merchant

[00:03:49] **Ben:** you use, do you use Stripe for payments? I can't remember. Oh,

[00:03:53] **Adam:** well, that's one of

[00:03:54] **Ben:** Well, that's

[00:03:54] **Adam:** places we support. Yeah. Believe me, we would love to be Stripe only, but we would also be out of business because none of our customers would accept that. So, you gotta, for PCI, you gotta figure out, you know, it's a puzzle, right? All the pieces have to click together and you have to figure out which piece you are, and then based on which piece you are, it's like, okay, this is your list of requirements.

[00:04:14] **Adam:** and some of them are gonna be NA, like for us, technically we're considered a service provider because we are not the merchant, we're the, so when you're a merchant, you're like, you're like Ben's Pizza Shop, right, and you've got a little, stripe or, or square checkout terminal. Right at the desk there.

[00:04:31] **Adam:** you have it in order to accept credit cards, you have to like sign up and they give you what's called a merchant ID, which is just this long number or whatever. And that gives you the ability to act as the merchant to, to accept credit cards. Since we are not the ones ultimately accepting the money, we're just kind of facilitating the payment.

[00:04:51] **Adam:** We're technically not the merchant because the merchant ID doesn't belong to us. And if it were not for that one technicality, we would be merchants. And our, our whole. PCI processes would be so much easier, but because that's the way that it is, we're technically considered service providers and there's like, it goes from like a three page report to like an 80 page report.

[00:05:12] **Ben:** yeah, it's ridiculous. And like I said, there's a bunch of NAs, there's a lot of fluff at the beginning and ending of that report. Really, ultimately it's like, I want to say 80 requirements, more or less. And this, this piece of software that you've subscribed to, it helps you

[00:05:26] **Adam:** yeah,

[00:05:27] **Ben:** where you are in this

[00:05:28] **Adam:** lost in the weeds here. You're right. so yeah, there's all these requirements. SOC 2 is very similar, right? SOC 2 kind of breaks things up into categories. Okay, I'm going to do the, everybody has to do the security category. You might also do, we are doing the privacy category, because that's important for our, the data that we manage.

[00:05:45] **Adam:** And So based on those categories, again, there's a bunch of requirements that you have to fulfill in order to achieve the certification. There is some overlap between them, like probably 80 percent of what you have to do for PCI is also required for parts of SOC 2 that we're doing and all that. And so to like, A, just manage the information, right?

[00:06:05] **Adam:** There's all these different things you have to be able to say, you have to be able to prove that you can satisfy the requirement. Which in order to just keep it all straight, what, you know, what applies to what, when does it need to be renewed? Right. When do I have to go capture our new screenshot of that thing?

[00:06:18] **Adam:** All that. And then a lot of it can be automated as well. Right. So like,so, GitHub, right. So you can have branch protections on your GitHub repositories. You can say nobody's allowed to merge to master. It always has to go through a pull request. That pull request has to have two people sign off on it.

[00:06:34] **Adam:** Yada, yada, yada, right? And there are requirements for SOC 2 and I think also for PCI that say that you have to, I forget exactly how they work, but ultimately what it means is you have to do code reviews. Like there has to be more than one person, or maybe the way they phrase it is separation between the person who writes the code and the person who deploys the code,

[00:06:55] **Ben:** Okay.

[00:06:55] **Adam:** And so, You can enforce those things in GitHub, and you're required to do them by the different certifications that you're doing. So there's a way for this software to, you give it like credentials to connect to your GitHub account and read settings of repos. It's not reading the contents of your code, but it's reading your repo settings and saying, Okay, you are using branch protection.

[00:07:15] **Adam:** And these are the rules. And so I can just like collect that as a bundle of JSON that describes your settings and attach that to the requirement. And there's the evidence and it automates all that away. And you can do that for a ton of things. Like it automates background checks for new hires and it automates like so much.

[00:07:34] **Adam:** Like, honestly, we, we switched vendors for our GRC software this year. We switched our, like going forward, this is where we're way off the rails here. So. This all started because you were like, didn't you hire new people or whatever? Um,yeah. So it took a long time because I felt like we were too focused on the upfront cost with both our auditing firm and our GRC software.and so moving forward, we've moved up a little bit in price, but we're getting so much in return for that, like better automation, like when we, when I signed into this new product. And like hooked up the automations to look at our GitHub, to look at our AWS configuration, to look at our payroll, to look at all this and that.

[00:08:17] **Adam:** it was like 80 percent already complete for PCI and like 35 percent for SOC 2. And honestly, there was probably another 20 or 30 percent for SOC 2 that's going to be complete easily once, once I get, all of the personnel stuff done. Once we get like personnel onboarded, they agreed to the policies, they do the security training.

[00:08:39] **Ben:** Would you have, so with all of this coming to a head, is there a activity or feature or refactoring that you've sort of held in your mind as this is going to, this is going to be the ice cream at the end of Lent? But I can finally have, now that I have time to indulge,

[00:08:57] **Ben:** That's like, we're going to boycott the gas prices by not buying gas, so we're going to buy it the day before the price goes up, and then we're going to buy it again next week anyway. Like, that's kind of pointless. I don't know. is there anything you've been looking forward to now that you can put this behind you for at least a couple of weeks?

[00:09:12] **Adam:** it does feel like there's a huge sense of accomplishment. It does feel like I've learned a lot and I will be able to carry that with me going forward and hopefully kind of roll that in and accomplish the next full calendar year. So that first one was just for the fourth quarter of 2023. We are now on the treadmill.

[00:09:34] **Adam:** You can check out anytime, check out anytime you like, but you can't ever leave.so we're on the treadmill forevermore for calendar year. SOC 2 and PCI. So there's that.

[00:09:47] **Ben:** So there's that. Can't you just give it to the, the co op? Yeah,

[00:09:54] **Adam:** peace out. Nice knowing you.

[00:09:56] **Ben:** I'm going to go check out, air conditioning and plumbing repair.

[00:10:00] **Adam:** I'm going to go buy an ice cream truck.

[00:10:02] **Ben:** Well, very cool, man. I know, I know it is an ongoing journey, but this is a huge milestone. Congratulations.

[00:10:08] **Adam:** Thank you very much. So that let's, let's just put that to bed. That's my triumph. What do you got going on, Ben?

## [00:10:15] Ben's Triumph

[00:10:15] **Ben:** I will also go with the triumph. So last week when we had Carol, my triumph was that I had been building this bulk export system for customers because the system is going to be end of life. And, my triumph last week was that I had finally done an end to end test. So to see, you know, not test in the traditional testing sense, but like I did it from end to end and it worked.

[00:10:36] **Ben:** And, prototypes as zip files were showing up my S3 buck. It was super exciting. And the follow up triumph this week is that I have actually had a couple of customers, three or maybe four, I can't remember, customers who have gone through. Set up S3 buckets, configured them properly for us to connect to them and have exported.

[00:10:57] **Ben:** I think we've exported in total, something like almost 2000 prototypes or 2100 prototypes, which in the grand scheme of things is, you know, it's three customers or four customers worth of prototypes. But it was, it was just so exciting to actually see it happen. And I'll tell you, man, I am always blown away by how freaking fast computers are.

[00:11:21] **Ben:** I don't know why it's still shocking to me. If you can imagine what an export of a single prototype is, I have to pull all of these screens down from Amazon S3, which is where we store them. Then I have to,

[00:11:33] **Adam:** images,

[00:11:35] **Ben:** yes, exactly. Images, mock ups of, Application interfaces. So I'm pulling all of these images down.

[00:11:42] **Ben:** Then I'm duplicating all of this, JavaScript and CSS into a working directory folder, and I'm, massaging a lot of data and I'm generating a giant JSON JavaScript object notation payload, and I'm taking all of these artifacts and I'm zipping them together, and then I'm pushing them back up to S3.

[00:12:01] **Ben:** And in my mind, especially because it took me like four months to actually build that whole thought process. It feels like it's so much work. And part of how I'm tracking all of this is I have a queue database table and I have a results database table. And in the results, I store the size of the file and the duration it took to actually from end to end, pull everything down, build it together, push it back up to S3, how long it actually takes and a holy freaking Cow.

[00:12:32] **Ben:** It's like, it'll pull down hundreds of megabytes worth of images, zip them together and push them back up. And I swear, it's like six seconds. And it freaking boggles my mind. I mean, I will, I will caveat that I have tried to build it to be pretty efficient. Like it pulls the screens down in parallel using async iteration and coldfusions arrays, and then it does a bunch of things in parallel locally.

[00:12:58] **Ben:** And, you know, I've, I've optimized it as much as I'm capable of optimizing it. But Jesus, the, the speed with which things come out of S3, now granted, this is all on Amazon, right? So S3, I presume is like. The next rack over, or S3 is like the next rack over from all the EC2s. I mean, that's obviously not exactly how it works, but generally speaking, right.

[00:13:17] **Ben:** They're like a building apart,

[00:13:19] **Adam:** just envisioned the, the towers of bodies in the

[00:13:22] **Ben:** Yeah, yeah, exactly. But man, it's like, it's like, so I'm constantly worried that when I build something like this, the happy path is going to be fine. Until it gets traction. And then suddenly there's going to be so much load on the database, so much load on the application servers that, that even the happy path is going to become almost malicious in nature with the load that it puts on the server.

[00:13:43] **Ben:** But freaking, you know, I, I can look in the logs to see when this happened. And then I can go to the database graphs to see what happened to the CPU. And I can see the, the read IOPS spike from like nothing to like tens of thousands in, in one minute. And you look at the CPU, zero change. Yeah, the CPU is just, it's just sleeping at like one and a half percent and it freaking blows my mind how, how powerful databases are.

[00:14:13] **Ben:** I, it's just crazy. That's like a meta triumph.

[00:14:18] **Adam:** yeah, I mean, at moments like that, I'm always reminded that, like, the entire, like, recorded and unrecorded human history is, like, Just a blip, just like a, like a half a percent, not even half a percent, like, like just an eye blink at the end of the year of the, in the entire, like the, the amount of time that has happened, right?

[00:14:43] **Adam:** Of all of his existence. And, and to go from banging rocks together to, making electricity dance on silicon, to, to, bend to our wills, it feels pretty magical.

[00:14:57] **Ben:** A hundred percent. It is, it is mind boggling. And now,

[00:15:01] **Adam:** been a couple of hundred years.

[00:15:02] **Ben:** and when they talk about all of this, large language model stuff, and they talk about the number of inputs that go into these models and it's, it's like 15 billion inputs or something, like, I don't even understand what words like that even mean at that point.

[00:15:18] **Ben:** You know, I think back to math and when I could do a matrix multiplication, which at this point in my life. I only know what those terms mean. I don't actually know how they work, but I did at one point, you know, 25 years ago, I mean, just, just mind boggling how amazing computers are.

[00:15:36] **Adam:** Oh yeah. It's like when, when you talk to somebody who actually understands enough to talk coherently about like special relativity, it's like, oh yeah, you're using, you're using a totally different vocabulary for me. We're just not even speaking the same language. Right.

[00:15:49] **Ben:** But it does, it does go ahead. Sorry.

[00:15:51] **Adam:** I was just gonna say like, those are English words that I have no idea what they mean.

[00:15:56] **Ben:** It does always remind me or it makes me, yeah, it, it's a reminder of just how simple things can be sometimes. You know, when I've been putting this thing together, I have in the back of my mind, constantly been worried about handling the load and what is this sad path going to look like?

[00:16:15] **Ben:** And what is that sad path going to look like? And I do think it's very important to consider the sad path when building software, but I'm, I'm very happy with the fact that computers are so powerful that sometimes just worrying about the happy path from a performance standpoint is usually good enough.

[00:16:36] **Ben:** And at least for the foreseeable future, like I think when computers just weren't as good and databases weren't as good, you really had to think more critically about how is this going to perform.

[00:16:49] **Adam:** Yeah, for sure.

[00:16:50] **Ben:** feels like you have to do it. Yeah. It just feels like you got a lot less to worry about these days.

[00:16:55] **Adam:** For sure.so you mentioned, you know, you've had some customers that use this tool and export stuff, and that's freaking awesome. I know that you early on, when you were trying to just sort of like think through this and plan ahead, you knew that there were some customers that were like, you know, the, the, the maximum you would expect to have to deal with, have, have you come anywhere close to that yet?

[00:17:17] **Adam:** Have you done a simulated export of their data?

[00:17:20] **Ben:** I do have one customer who was having performance problems in the application itself, like a year ago, and they added me to their project and because they added me to the project, I have access to export it. And they are the largest customer that I have seen personally. And they have, you know, we talk about these images, these, these mock up screens.

[00:17:43] **Ben:** They have, I think, 3, 100 screens. That's 3, 100 something screens in change. when you export the zip file is about 1. 2 gigabytes in size.and, and when I run it, that freaking computers, man, it takes about 40 seconds. That's

[00:18:04] **Adam:** Not nothing to work to, to worry that much about. You're not going to like. Crash the app

[00:18:09] **Ben:** yeah. And, and, and again, even when I do that one and then I look at the timing and I look at the database and all that stuff, I mean, it's nothing, you don't even see it on the, like nothing spikes, you know, the, I can see the number of rows read on the database. Clearly goes up pretty significantly, no effect on the CPU whatsoever.

[00:18:31] **Adam:** So is the majority of the work being done on your CFML servers? Okay,

[00:18:38] **Ben:** the JVMs, the Java virtual machines for the listeners, it is also like completely unaffected. So the, the, I mean, I, for the, so it's a complicated process, but the parts are really simple. I mean, it's ultimately I'm making HTTP calls to S3. Pulling the images down.

[00:18:59] **Ben:** Then I'm doing a regular bunch of SQL queries, like a whole bunch of SQL queries, and I'm pulling rows and I'm doing some copy files from one directory to another, and I'm dropping down into a CF execute to actually do a zip binary. Like I don't use the CF zip tag. Cause it's. Much slower than, cause it uses the Java zipping libraries.

[00:19:22] **Ben:** But if you just use the zip binary in, I don't know where it's from, whatever, you know, it's like the man pages. If you look up zip and you do an app, get install zip. This is what the, this is the one you get. It's so freaking fast.

[00:19:34] **Adam:** it's probably Zlib, but yeah, go ahead.

[00:19:36] **Ben:** Yeah. Yeah. I mean, so that's it. Like the, the process it's tedious to get the data and to massage it.

[00:19:42] **Ben:** But the, the actual processing is really just the zipping and I, whatever it's doing, it's doing it super fast. Plus also so much of the payload size is the images and you can't really compress images beyond what they are. I mean, PNGs, you can kind of compress a bit, but JPEGs are already compressed.

[00:20:02] **Ben:** That's the whole point of the JPEG, right? So I, you in the, One of the commands that you can give to the zip is only, or like, don't compress files with this extension. So I can say, you know, zip all the JavaScript together and the JSON payload, but don't try to compress the images any more than they already are.

[00:20:22] **Ben:** And I think that, you know, like I say, that helps. Part of me thinks that helps in the mindset of 2000 when things were a lot slower and 2024, you know, it probably doesn't even help that much. I don't know.

[00:20:38] **Adam:** I mean, I imagined by number of bytes, these images probably are a significant majority of that zip file. Right. So by saying, don't bother trying, just concatenate them together or whatever, you know, whatever goes into a zip file, but like just easy mode those files and then just compress this other 8 percent over here, like that probably saves it a lot of, of, processing time.

[00:21:01] **Ben:** So it's been a huge triumph. I've, I've felt very rewarded by the fact that this actually worked. Like it actually did the thing I hoped it would do when I started this in like February or something. I don't remember when I started, but it was quite a while ago.

[00:21:17] **Adam:** Nice. Congrats,

[00:21:18] **Ben:** Yeah. Thank you.

## [00:21:19] Is it Even Possible to be a Solo Developer in 2024

[00:21:19] **Adam:** Alright, cool. So let's move on to our topic for the day, which is, Is it even possible to be a solo developer in 2024? Which, I feel like we're gonna take in a bunch of different directions, but, you know, let's just start with that.

## [00:21:31] The Standard for MVPs

[00:21:31] **Ben:** Yeah. So this is top of mind for me because of the podcast that I listened to. And so I will fully. Come to this conversation with the caveat that this might be very much an echo chamber kind of a conversation. Yeah, because I listened to a lot of podcasts about product development. I listened to a lot of podcasts.

[00:21:52] **Ben:** Are interviews with companies that have been super successful. You know, your Airbnbs and your, I can't even think of things off the top. My head. GitHubs and, and all, you know, Ubers and your Lyfts, right?

[00:22:05] **Adam:** survivor

[00:22:06] **Ben:** Yeah, yeah, yeah. These are people who are talking about, what is it? You know, they're reflecting on how did we create a $15 billion company, let's say, you know, let's draw facts from that.

[00:22:18] **Ben:** And a lot of these conversations are being had at least in part by venture capitalists whose whole world revolves around. Trying to predict unicorn companies and then reap the benefits. So I will fully admit that maybe I'm heavily, influenced by this. Weirdly, weirdly, yeah, yeah. Weirdly specific world.

[00:22:40] **Ben:** But one of the things that they keep talking about is, is like, how is the error of the MVP, the minimum viable product is the error of the MVP dead. That because the bar of experience. In these super successful applications, because it is so high now for customers, it almost feels like you can't produce anything that drops below that.

[00:23:04] **Ben:** You won't, like, people will be angry. They won't want to use your product. They'll, they'll, you know, unless you're doing something completely revolutionary, they have so much choice. And what it makes me feel like these days is Unless you have a team of very talented people and you're doing revolutionary stuff and everything is super polished and you have designers and beautiful, design systems and, and everybody really knows what they're doing.

[00:23:29] **Ben:** It, it's starting to feel like, can you even build an application anymore? I don't know. It, I don't, it just,

[00:23:37] **Adam:** a team of four to do a Hello World?

[00:23:39] **Ben:** yeah, it's making me very anxious as someone who enjoys trying to build little things on the side just as, as experiments. And granted, I build them as experiments, so it's not like I'm trying to spin off a business from my side project idea. It's very, it's very intimidating to think that even if I wanted to do that, it would be impossible.

[00:24:03] **Adam:** Right.

[00:24:04] **Ben:** But again, I don't know if I'm just in this weird little echo chamber of podcasts being hosted by V Venture Capitalists.

[00:24:11] **Adam:** Well, I think that the first thing that comes to mind in response to that is target audience, right? So a venture, a VC funded, company, it's probably B2B. They're very unlikely that they're direct to consumer, right? Like they're the number of companies that are successful at getting a hockey stick growth and or revenue slash profit.

[00:24:35] **Adam:** Chart at selling directly to consumers is probably way lower than the number of companies that sell to other companies, right? Cause companies have money to

[00:24:45] **Ben:** Right. They got budgets.

[00:24:46] **Adam:** right? that changes what those companies are looking for, right? If you are, if you're in charge of finding a GRC automation software, you know, vendor for, for your company, You're going to be looking with different eyes than if you were trying to, you know, spend a little bit of money to save money to make money for your own little side project, or to try and run an Etsy shop, or just because you want to do a thing.

[00:25:13] **Adam:** Right? Like if you're, sometimes we spend money on things like I, I've gotten a lot looser with my 1 here, 2 there for like, iPhone apps than I was 15 years ago when the thing came out. Right. Like when it came out, I was like 99 cents for an app. No way. Because I know that in a year I'm, if, if I buy this one, then I'm gonna buy 15 more.

[00:25:33] **Adam:** And before you know it, I'll have spent $40 on apps. And granted, you know, I was making a lot more than $40 a week and my job, but still, you know, it just, it felt like a bigger deal 15 years ago. And now that I'm more mature, I have, you know, more income and I have my kids that I take care of and just life is different.

[00:25:51] **Adam:** Right? And, and now I'm like. You know, a dollar a month for, for that, for that app, no problem. You know, 5 a month for the New York times thing, like no problem. and, and so it's, it's different, right? It, your, your target audience affects what those people are looking for. And so like, I think me as a person, like if I'm, if I'm just looking to buy a piece of software that I need or that I feel like will make my life Knowing that like the person who's building it, especially if, you know, if I find something, I'm like, okay, well, let me look into this company and I go, okay, it's a solo developer, but this is a person who has the same core beliefs as me.

[00:26:37] **Adam:** Like, if this is a, like, if we're talking about dig deep fitness, right, this is somebody who cares about the product, works out the same way that I do, has the same needs. And so like, when I come to him and I say. Look, you're, you're, the way that you're doing streak tracking in your fitness app is killing me, man.

[00:26:54] **Adam:** And you're like, this is the problem. And here's the solution. Like, I'm a developer too.

[00:26:57] **Ben:** Yeah, yeah,

[00:26:58] **Adam:** I know we're going to have that genuine connection. And to me, that's worth a lot more than a fricking SOC 2 report. Right? Like,

[00:27:05] **Ben:** Right, right. I follow you.

[00:27:07] **Adam:** so yeah.

[00:27:09] **Ben:** It's also, as you're saying, I'm going to go out in a slightly different direction, but as you were talking, this popped into my head that I think part of the residue that I'm, that I'm feeling from all of the conversation is if you think the error of the MVP is dead, then working backwards from that, that has a lot of implications.

[00:27:34] **Ben:** Meaning if I want to try to release a product and it has to be super polished and super professional. Then how does that actually get done? Well, it gets done because I have a team of very talented people who are willing to put in the time to build this product, maybe before it's released, maybe before we're making any money.

[00:27:51] **Ben:** And you're like, well, then how do you do that? You're like, well, I do that by having a butt ton of money to spend on these people to begin with. And maybe that's. A core part of the resentment that I'm feeling in the whole MVP is dead mindset is that then, then the only way you can build software now is to venture capital and that doesn't seem

[00:28:11] **Adam:** was, I've been like biting my lip over here because VCs killed the MVP. If the MVP is dead, VCs are the ones who pulled the trigger, right?

[00:28:19] **Ben:** Well, that doesn't, I don't know. That just doesn't sit right with me. You know, everything's becoming so complicated. You know, we've talked about this on the show before, just even the, the spinning up a server and building some CSS and deploying it to a, to a running publicly available URL, like even that's in some ways it's become much more simple.

[00:28:39] **Ben:** Like I can push to Git and Git will somehow magically make Netlify happen, but, or probably more in reverse, Netlify magically makes that happen. But. There's so much, like the low level stuff has become so much more complicated with your webpacks and your Vue and your Sveltes and your compilers.

[00:28:59] **Ben:** Well, you're talking about layers of abstraction here, right? Like, Well, like you, you were talking about the, was this in the pre show? I can't remember.

[00:29:09] **Adam:** the conversation in Discord?

[00:29:10] **Ben:** Yeah, yeah, yeah, yeah,

[00:29:11] **Adam:** Yeah, that's okay. This is a good segue. So, we had, a listener of the show, Peter, hello,mentioned in our Discord that he is trying to beef up his resume to improve his employability. And he was, you know, working on, or maybe just in the planning phase, I forget, of a side project and he was going to build it in, Oh, God, I should go look.

[00:29:31] **Adam:** I wanna say it was, Java. Let me just scroll up here a little bit. so yeah, he's chosen Angular, Java, springing and Postgres. he read a book about spring, and he wants to practice using it and like, and, and he goes on to talk about like, building off, right? That's kind of like the, the first problem he's trying to tackle.

[00:29:52] **Adam:** And it can, like, I, I absolutely do not blame him for this because they've. This is kind of exactly what I feel like you were saying from a different angle, right? You, like you, when you look at the ecosystem of development today, it feels like you have to be using these 20 different products, right? I have to be using a, a front end framework, like an angular or a reactor or apel or whatever, and I have to be using, you know, dependency injection framework.

[00:30:19] **Adam:** I, I assume that's what spring is. I'm, I don't know for sure. Well, I say that because I used to be a ColdSpring user and my understanding

[00:30:27] **Ben:** Right. And that was

[00:30:28] **Adam:** DI framework for CFML. Was inspired by Spring, the DI framework for Java. That was my understanding. Could be totally wrong. Anyway, and so like you've got, it can feel like you have to snap all these Lego bricks together.

[00:30:41] **Adam:** Like that's a requirement of building software today in 2024. And for me, that was like the The thesis of the show title, right? Is it possible to be a solo developer because you have all these different things that you have to click together, but it's not necessarily apparent how they click together and like what does and what, which piece of the sculpture does what job, right?

[00:31:02] **Adam:** So like he was talking about using Spring, but also I think it would be considered a, a plugin for Spring that does like auth, I think it's called Spring Auth. it's a long post, so I'm, it's, I'm having trouble skimming it here in the conversation, but, and like, okay, to do OAuth and all that, and my advice to him was like, you are biting off way too much, for your first like real project.

[00:31:22] **Adam:** Like, let's go back to basics here, intentionally write it with bad security and like fix one thing at a time and like, kind of like just speed run my career. Right. So like, go ahead.

[00:31:33] **Ben:** So, so you, we've talked about the show, The Bear, the yeah, it's called The Bear, right? Yeah. Yeah. The TV show, The Bear. I'm not gonna give any spoilers to people who haven't watched it yet, but as we're thinking about this, I can't help but think of, there's a, one of the chefs that's portrayed in the show is a, what's the guy from TalkSoup, Joe, Joe McHale, I think is his name.

[00:31:53] **Ben:** He's the really condescending chef, in one of the flashbacks, it's like in all these little flashbacks

[00:31:58] **Adam:** Oh,

[00:32:00] **Ben:** where the main guy is cooking and. Matt,

[00:32:03] **Adam:** see him that much, but yeah, yeah.

[00:32:04] **Ben:** you're going to have to bleep here, but where he's standing behind the main character and he's like, you're a piece of like, what are you even doing here?

[00:32:10] **Ben:** Why don't you give up? Should we have everyone stop so that you can catch up with them? You disgust me, you piece of you're disgusting. He's literally just standing behind him while he's trying to cook, and I feel a little bit, and then they'll have other

[00:32:24] **Adam:** that would, just to be clear, that was like the master hovering over the apprentice trying to like influence him. Yeah,

[00:32:30] **Ben:** Yeah. And then, but then they have other flashbacks to other chefs who I think are actually fun side note, are actual real chefs in the real world running these real restaurants and they're much calmer and they're much more self controlled and they're talking about the joy of cooking and the, and, and the, and how great it is to prepare food.

[00:32:46] **Ben:** And they're talking about the finer points of, you know, wrapping chick chickens together for rotisserie. And it almost feels a little bit like. That condescending chef is the venture capital world where I'm like, like, Oh, Oh, you don't have a design system, you piece of Like, Oh, you're not going to have like full, you know, whatever integration with all this other stuff you just discussed me.

[00:33:08] **Ben:** And then there's like, then there's the, you know, like the, the more controlled conversation that we're having. We're like, Oh, just start simple and like, enjoy programming and. You know, solve, solve the problem that's right in front of you and learn how to incrementally improve your software. And, you know, if you look at the cooking world, and again, this is based on a, on a drama TV show, so take that with a grain of salt, but it's like both of those people can exist and both those people are kind of right in their own little worlds and they don't negate each other, but you can have either.

[00:33:39] **Ben:** And I, and I think I bring so much insecurity, you know, touching back on a previous show that like. I'm so much more thinking about that VC perspective on the world, especially as I'm about to shutter a company, which sucks. And I forget that there's like, Oh, there's this calmer, more mature, more, controlled way of looking at software development that isn't so negative. Oh, sorry. I got a lot off my chest there.

[00:34:07] **Adam:** You feel better? So, yeah, I was kind of getting into like my advice for him and this is, I'm only realizing this now, but like my advice for him was basically try to speed run my career. Right. So starting out as a nobody in the burgeoning days of the internet, you know, I, and I was mostly self taught and went to, I did go to school for computer science, but it was, it was more computer science and less software engineering, right.

[00:34:32] **Adam:** They taught us. How computers work, not how to write good software. And, so, so yeah, my advice was like, write the terrible in terms of security application, right? Write a login that has clear text, username and password in the database, and then go back and once that's functioning, go back and make that password MD5 hashed and like understand why you need to do that, right?

[00:34:52] **Adam:** Because it's a one way hash. so it can't be decrypted if somebody were to get it. And then you know, make that functional with your application. And there's some stuff, there's like processes you have to change in order to make that work. And then once you've got that working now, okay, here's what's wrong with MD5 hash.

[00:35:07] **Adam:** You have to salt it because of rainbow tables and well known hashes and passwords and stuff. like, okay, here's, you know, here's a problem. Here's how we solved it back in the day. And you know, each of these steps is like a day or two, right? but then you're like, you're, you're taking a lesson that turned out to be like a year, right?

[00:35:22] **Adam:** Maybe I got these lessons each like a year or five years apart and you're getting them a day apart, two days apart.

[00:35:28] **Ben:** You know,

[00:35:29] **Adam:** And so like, I feel like somebody coming into the ecosystem now, graduating school, if they, if they can find other advice that like, kind of takes the same approach to learn the different things that are important these days, like, I don't know what the steps would be, but again, like, just the idea of like, you graduate college and somebody is like, okay, you have to pick React or Angular or Svelte, like, go pick one, like, how do you even make that decision, right?

[00:35:53] **Adam:** You kind of have to like, experience the pains, understand what the problems are. And then, then you have some sort of touchstone from which you can compare the different solutions that are available to you and like, how do you pick one

## [00:36:08] The Joy of Software

[00:36:08] **Ben:** it almost feels a little bit like when you're watching a karate movie, and, as, as one does, and the person who is more of the novice, they're getting, kind of like, too, too mired in all of the technique stuff, and at some point the sensei does something where it's like, you just have to connect with your roots, and like, listen to the wind, and look at the water, and listen to the leaves.

[00:36:33] **Ben:** And then It's almost like we've forgotten just the joy of software and the fact that there was a time in my life that I didn't know this was possible and you could take a text file and you could push it to a server. And holy it was live to the world. And I just did that with my hands and now it's available to a billion people.

[00:36:53] **Ben:** Like that's freaking amazing.

[00:36:55] **Adam:** Yes. I, I, I very, I have vivid memories of like editing my, my website in the AOL website editor, right? Cause you, you have your own space on there and like, you know, putting in that little animated GIF that I stole off the internet of, you know, like proudly written in notepad, right? No line numbers, no syntax highlighting.

[00:37:18] **Adam:** Did the hard way. And you know, looking back now, like that was terrible. But still, you know, I did

[00:37:22] **Ben:** But it was the joy of it,

[00:37:23] **Adam:** Exactly. It was the, the, it wasn't the work that felt good. It was like the, the accomplishment that felt good.

[00:37:31] **Ben:** Yeah. So I think when, when I start to stress out too much about can an individual build a piece of software, It's, I've almost become too concerned with the race and not enough with the joy of the thing I'm doing. But you know, there's the world that you wish existed and there's the world that does exist.

[00:37:51] **Ben:** And so I don't know if part of that is me being nostalgic for simpler times or if Or if that's still just a, you know, that is still possible. And there is going to be an, an echelon of world class software where maybe MVPs, that's just not a thing. Like you, you can't, you know, not, not to be extreme about it, but it's like, you can't launch a rocket and have MVP software on the dashboard.

[00:38:15] **Ben:** That's the, but there's definitely a world where you can launch a product and it can be MVP. And it's, you know, we talk about, we we've talked about this often in the context of testing where. There's just nuance and some products just don't require much testing because like not a lot happens yet.but some products require a lot of testing because literally people die if you get, if you get it wrong.

[00:38:40] **Adam:** The stakes can be

[00:38:41] **Ben:** Yeah. The stakes are very different. And I think the, the nature of the MVP, you can have the same conversation when it comes to the level of polish in software. I mean, I remember using, this is going to be really old school here, but when I was using, Macromedia home site, which was an IDE, a text editor, basically, there was a bug where if you double clicked on one of the folders in the file tree, it would collapse all of the folders. And like that sucked. It was awful. It was so frustrating. And you know what, I just worked around it. I just didn't double click folders. And like, you could say, Oh, this is such crappy software. Like that would never exist. I'm like, well, I used it though. Like I had options. I could have used notepad. I could have probably developed it with notepad without syntax highlighting.

[00:39:28] **Adam:** You could have that gift right next to

[00:39:29] **Ben:** Yeah.

[00:39:30] **Adam:** viewed and Netscape navigator.

[00:39:33] **Ben:** And I, I sometimes think that we get so obsessed with creating software. We forget that we are often software consumers ourselves and we forget how much. Compassion, I think we extend to the people who build stuff.and we don't extend that compassion to ourselves. But then I, then again, I'm like, is that skewed because I build software?

[00:39:58] **Ben:** It's like when you work at any kind of customer service oriented business and you realize how awful a lot of people are and then you're like, okay, now I can never be rude to customer service people again in my life because I've seen how the sausage is made. You know, maybe that's the software, the software side of that is I've built software.

[00:40:16] **Ben:** I know how hard it is. I know how many moving parts there are. I know how many competing priorities there are. So now I'm just going to be more compassionate when it comes to using software. You know, maybe that is part of that too. I don't even remember what point I'm making. Other than to say, I, I, I just like, you get, it's, it's, there's so much survivorship bias and experience bias, and it's just so hard to know what's actually real anymore.

[00:40:44] **Adam:** Well, so let's let, then let's, take a moment to refocus the conversation.

[00:40:47] **Ben:** Fair enough.

[00:40:49] **Adam:** Is it possible to be a solo developer in 2024? I think obviously the answer is yes. People are doing

[00:40:55] **Ben:** Right, right. Point of

[00:40:56] **Adam:** I think that you're right. And so the, the question is not so much, is it, but like, you know, what are the trade offs, what do you have to do in order to make it possible?

[00:41:07] **Adam:** I think. There's also a lot of different paths, right? Like there are people coming out of bootcamps that are doing a solo dev thing, you know, now and finding some level of success with it. Right. And there's also people that are doing a nights and weekends solo project. That happened to also be, you know, like super senior engineer, platform engineer, platform architect or whatever at their day job.

[00:41:30] **Adam:** And so they have a lot of experience to draw on. Right. So like if I were to go start a side project right now, depending on what the application needed, like I would have no difficulty at all, like doing what you talked about, like set it up so that I pushed a GitHub and Netlify auto deploys it if it's a simple,

[00:41:46] **Ben:** Right. Staticky kind of thing.

[00:41:48] **Adam:** or a staticky thing, yeah, no problem. Or if I wanted to, I could have it like. You know, I pushed a GitHub and then instead of Netlify doing the thing, GitHub actions does a thing and it builds a container and it pushes it up to AWS ECR and then it tells ECS to restart the cluster and do a deployment

[00:42:04] **Ben:** too

[00:42:04] **Adam:** you're like, all that, right?

[00:42:07] **Adam:** I need my, my Steven Soderbergh, like cut the screen in

[00:42:10] **Ben:** Yeah.

## [00:42:12] Gatekeeping

[00:42:12] **Adam:** anyway, yeah, so like there's, there's, there's a million different paths and, and I think that really, okay, here, this has just occurred to me. I think the question itself is gatekeeping. think that if you want to do something and you're making it work, right?

[00:42:30] **Adam:** Like, and we, all we should be trying to do is help each other. Yeah.

[00:42:34] **Ben:** And I, and I think that's a big part of the resentment that I feel is that when you say things like the MVP is dead, all it does is shut doors. It doesn't help anybody. And I, and I think that's maybe so much of the anger that I feel when, when I hear people say things like that, don't, you know, you're not yes anding, you're, you're knowing.

[00:43:00] **Adam:** That feels like a terrible place to stop, but I don't know that I have more to say.

[00:43:04] **Ben:** lot of people make the joke that some company is an overnight success, 10 years in the making. Like, so Figma, who was one of our primary competitors and who is now the clear market winner, you know, they didn't have their first customer from what I think I've heard in interviews for like five years or three years or something.

[00:43:25] **Ben:** And like, they didn't make their first dollar or something for like five years. Some, some like crazy, you know, they were sitting there working and iterating on this product for years. And so you could say, Oh, it sounds like, you know, it feels like they just came out of nowhere. You're like, well, they came out of nowhere after three to five years of complete dedicated focus to solving this problem.

[00:43:46] **Ben:** And. And I, I wish that story was celebrated more. Yeah. Sorry. I don't know.

[00:43:54] **Adam:** the jokes just went right over your head. Yeah.

[00:43:58] **Ben:** Those are the, is that the ship that just appears out of nowhere? Kind of

[00:44:01] **Adam:** Yeah. So in Star Trek, the K Clingons were the remember wharf. it's a TNG reference, but it, do you know who wharf is?

[00:44:06] **Ben:** Yeah. Yeah. He's the, yeah. The

[00:44:08] **Adam:** on his face? Mm-Hmm. and yeah, so his race was the Clingons and then the, the K Clingons were the ones who were like always employing stealth. Other, other races had stealth ability, but K Clingons and, and the Romney lands, I guess too.

[00:44:19] **Adam:** Were always employing stealth and being like secretive and, and attacking from there, whatever.

[00:44:25] **Ben:** But I think if, if these overnight success, 10 years in the making kind of stories were more widely celebrated as the, here's what actually happened, Then it would, it would normalize this idea that you have to start small and you have to build things incrementally. And the first. Seven versions of your product are probably going to be kind of but that's just that you, that's the dues you pay when you build successful software.

[00:44:53] **Ben:** And I think if you could make that okay, then it would allow more people in the door.

[00:45:00] **Adam:** Yeah, yeah, the, I think, so you, you're kind of hinting at, the concept from a comic that I've seen. It's like how to build an MVP. And, and I think it's kind of like the VC funded mindset of like, you know, you come into this project thinking I need to build the best car or whatever, like I've got this like great idea and the, my understanding having never done a VC funded company, Is that, you know, they, they want you to take the approach of like, well, okay, you think you want to build a car, but start with the thing you can build today, like get it done today sort of thing.

[00:45:31] **Adam:** And so that's a skateboard or a scooter, right? And then you like iterate on that and you move in sort of the general direction of where you want to go, but you follow the market. And, that's my understanding of it. Probably fatally flawed, but, Right.

[00:45:47] **Ben:** sentiment that you never know as little about the product as you do right now. And the idea that you're going to build this perfect product without having put it in front of people and have them give you feedback on what works and what doesn't work and have it be successful is crazy.

[00:46:04] **Ben:** You know, you, you have to be building a cache of evidence that something works or doesn't work. And, and I think you can only do that iteratively with, with MVPs and whatnot.

[00:46:17] **Adam:** Yeah, and I guess kind of where I was headed with that little anecdote about the comic was more like, it is so easy to see something that, that like, you understand, it's almost like when, once you kind of understand something like that little comic, you know, you see it, you're like, oh, this is interesting, you, you look at it and you're like, okay, I think I get it, it's, it's tricky to not let that become, that makes it true for me, right?

[00:46:43] **Adam:** Like, just because this is a, a. Statement or a worldview that makes sense doesn't mean that it applies to me, right? Like that doesn't, that doesn't mean that that's the best way for me to make my product.

[00:46:56] **Ben:** Right. Absolutely.

## [00:46:58] Making Trade-Offs

[00:46:58] **Adam:** And I feel like that applies to this conversation too, right? It's like, there's a million ways to make an app.

[00:47:03] **Adam:** There's a, and, and some of them are solo developer, you know, doing your thing. And, and I think going back to some of our previous shows, like if you're going to be a solo developer, you need to be intentional about that. If you want to stay solo and you're not trying to grow into a big company or whatever, There's, there's just trade offs you're going to have to make.

[00:47:19] **Adam:** Like, do I want to be really good at infrastructure and whether it's GCP or AWS or whatever, and like nail all that and then just try to keep my product maybe a little simpler. But, but then the selling point is the, a hundred percent uptime reliability, you know, amazing infrastructure, or maybe slightly, you know, a little bit of downtime here and there, but the product itself is worth it sort of thing.

[00:47:44] **Adam:** Like you've got to kind of pick and choose where you're going to specialize. And that thought reminded me of the innovation token conversation that we had a while back. and just like, you know, you can only pick, you can only pick a couple of things, right? You can't be a solo developer and do, you know, be like super angular

[00:47:59] **Ben:** Spring boot and Java.

[00:48:01] **Adam:** and Java and, and, you know, infrastructure. Did I already say infrastructure? I don't know. Whatever. Yeah. You can't go all the way down all of the paths by yourself.

## [00:48:11] Pivoting

[00:48:11] **Ben:** Absolutely. And the, the other thing that I was just thinking about too, talking about when you talked about how someone's worldview doesn't necessarily have to be the worldview that works for my product, the other thing that I'm always shocked by is. It's how many super successful products didn't actually start out as that thing.

[00:48:29] **Ben:** Something, it's something crazy. Like 80 percent of the most successful products started out as a different product altogether, or a different, you know, sub straight of that product. And you think about things like Slack, which is, you know, dominating chat. And it used to be. It was just like the chat inside of another game engine or something, whatever it was.

[00:48:47] **Ben:** You know, so how do you have these two worlds coexist? And on the one hand, saying that MVP is dead. And then on the other hand saying, oh, and also 80 percent of the most successful pieces of software didn't start out as the thing they started out as, or as the, you know, didn't start out as the thing they are today.

[00:49:03] **Ben:** Well, that sort of makes that whole MVP is dead concept not make any sense because How does that make sense? If the original product is not actually the product that was successful, didn't that kind of, in a way, make it? An MVP for the thing that became successful. Like maybe it was very polished, but it still wasn't successful.

[00:49:21] **Ben:** It was still just a prototype or a diving off board, a springboard for what became. I'm just saying like, you, you can't have at the same time, this idea that you have to have the perfect design. Upfront and also say that so much of the most successful products started out as completely different products.

[00:49:43] **Adam:** I feel like there's a slight, I'm sorry to not yes

[00:49:45] **Ben:** No, no, no, no, no, no. I'm I'm, it's not a perfect analogy, but I'm, I'm just saying that it, the fact that those two can coexist means that something is not entirely right.

[00:49:56] **Adam:** Agreed. Yeah. There's, I think there's an art to, to knowing when to pivot, right? So you've got an app and you've got, you know, you don't really care that much about it, but it's got this little chat feature in it and that seems to be doing well and nobody cares about the rest of your app, then, okay, well, let's focus on the chat thing and make that the product.

[00:50:13] **Adam:** Like

[00:50:13] **Ben:** Yeah. It's like,

[00:50:15] **Adam:** Yeah.

[00:50:16] **Ben:** it's like, so grit is a very important personal characteristic, I think, generally speaking.

[00:50:21] **Adam:** Mm

[00:50:23] **Ben:** So it'd be like, it'd be like trying to say. That grit is super important.but also some of the most successful people in the world are on their seventh career. You're like, well, like it's hard to reconcile those two things.

[00:50:36] **Ben:** And I'm not saying that like either I'm making up that number about seven careers, but I'm just saying like that world can exist where both those things can kind of be true, but it, it adds color and

[00:50:48] **Adam:** I think, I think they both can, I think taking a single career and gritting it out until you make success out of, out of all your failures versus trying seven different careers until you find the one that makes you successful are just different kinds of grit, right? It's a, it's a different finish line

[00:51:07] **Ben:** All right. Maybe it's a terrible analogy. That's that's that's

[00:51:10] **Ben:** I think it illustrates your point just fine. Like, you know, it's a different kind of grit, right? It's the grit of finding a way or making one, right? God, who said that? I don't know. It's lost to time. There's a really famous, like, almost like, Indiana Jones.

[00:51:29] **Adam:** no, I wanna say like, ancient Greece type people. I don't know. Whatever. Like, whoa. like, oh, the name is on the tip. My tongue.

[00:51:36] **Ben:** something like Sophocles, I'd be like, yeah, that sounds right.

[00:51:38] **Adam:** No,

[00:51:39] **Ben:** I don't know. who that is.

[00:51:40] **Adam:** like, I wanna say like, oh. I.

[00:51:42] **Ben:** Marcus Aurelius,

[00:51:45] **Adam:** It's one of those things where the name is on to my tongue. I'll probably think of it tomorrow. But anyway, he said, you know, we'll find a way or we'll make one, right? Like we're going to get this done. Right. And I feel like find a way is I'm going to just keep trying jobs until I find the one that clicks or make one is like, I'm going to, this is the thing that I care about, right?

[00:52:03] **Adam:** I am going to conquer the world and I'm going to push through one city at a time until I conquer the whole world. Right. Like that's, you know, and you can be successful either way.

[00:52:14] **Ben:** also say,

[00:52:15] **Adam:** Yes.

[00:52:16] **Ben:** feel like you can build software with one person. You just, you know, you just have to be managing your expectations of what that means, I guess.

[00:52:24] **Adam:** And yeah, being intentional, you know, or, or take some time to self reflect, right? If we're trying to answer the question here, is it possible to be a solo developer in 2024? It's possible. The question, you're sort of answering a question with a question. Are you sure that's what you want to do? Have you even thought about it?

[00:52:40] **Adam:** Right? If you haven't thought about it, think about it. Are you sure that's what you want to do? And if it is what you want to do, Be intentional about. the things that you choose to take on and the things that you choose to let go. And that's honestly, part of that whole B2B discussion we were talking about, which stands for business to business since we're, this is an episode where we're, spelling out, spelling out all of our, Acronyms and, and the other thing that's initialisms, those are, you know, that's the time when it makes sense to spend the money, right?

[00:53:06] **Adam:** If I'm, I can buy a, like, there's a, there's a couple of companies now that are like, we are the modern day, Heroku, right? Like, but it's like in your own private cloud sort of situation, right? So instead of, it's like, you know, You give us your config and you say, I want two of these servers and three of these or whatever.

[00:53:25] **Adam:** And like, you just push to get, and it spins up all of the stuff in your own AWS cloud, VPC or whatever. Like there's a bunch of different companies that do that. And if that's not something that you want to learn how to do, but it is important to you to be able to do, then yeah, spend a little bit of money on that so that you can focus on your product and remain a solo developer so that you only have one mouth to feed or whatever, like more power to you. So to sum up, yes.

[00:53:49] **Ben:** Go, go forth and build software.

[00:53:51] **Adam:** Cool. Cool. Cool.

## [00:53:52] Patreon

[00:53:52] **Adam:** Okay. So this is the part where I say this episode of Working Code is brought to you by Netscape Navigator, the cool new browser on the block and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:54:06] **Adam:** Our patrons cover our recording, editing, and transcription costs. And we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:54:15] Thanks for Listening!

[00:54:15] **Adam:** after show tonight, we, I have two things that I want to talk about. I'm going to just gonna, I'm going to keep it simple and, and somewhat cryptic.

[00:54:23] **Adam:** First one is Whiskey7 at Niagara Falls. And the second one is how to clean your eyeglasses. Okay. So if you're not sure what the heck we're talking about, the after show is Pretty much the only actually useful perk of being a patron of the show, other than the, the warm feeling in your heart that you get for supporting us.

[00:54:45] **Adam:** we, the show will end, and people who are not patrons will hear the outro, and people who are patrons will then just hear us transition into the after show, where we'll keep the mics on, and we'll just keep talking about whatever we want for as long as we want, usually somewhere between like 10 and 20 minutes.

[00:54:58] **Adam:** And sometimes as short as five, who knows, but, we just keep talking until we're done until we don't have anything else we want to say into the microphones. and then we deliver that straight to your ear holes.so if that sounds interesting to you and you want to help, you want to get a copy of that, you want to help us out, you can go to patreon.com/workingcodepod. We would really appreciate it. That's going to do it for us this week. We'll catch you next week. And until then,

[00:55:21] **Ben:** Remember folks, your heart matters, even if you're a developer of one working on an MVP.
