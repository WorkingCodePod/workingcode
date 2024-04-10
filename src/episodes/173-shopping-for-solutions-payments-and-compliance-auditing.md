---
title: "173: Shopping for Solutions - Payments and Compliance Auditing"
description: "Adam picks Tim's brain searching for the perfect solution for payments and compliance auditing."
date: 2024-04-10
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/5da87fe9-8310-49f0-8c21-e81a729e63bb"></script><div class="redcirclePlayer-5da87fe9-8310-49f0-8c21-e81a729e63bb"></div>

Adam picks Tim's brain searching for the perfect solution for payments and compliance auditing.

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/173-shopping-for-solutions-payments-and-compliance-auditing.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** you are the customer here. I mean, think about how your customers bully you, right? They bully you. They're like, yeah, you need to have, you need a PCI, you know, seven compliance, even though you only need, you know, one, You can do that to them. You can at the, at. Even like if you choose to use the same one, right? Because you at least, you know, how the software should work.

## [00:00:41] Intro

[00:00:41] **Adam:** Okay, here we go. It is show number 173 and on today's show, I have a special guest, Tim Cunningham. Welcome back, sir.

[00:00:48] **Tim:** Hey, long time listener. First time caller.

[00:00:51] **Adam:** and as it turns out, Tim was gone last week because he was sick. And this week, Carol and Ben are not feeling well. So it's, it's the Tim and Adam show tonight. but first as usual, we'll start with our triumphs and fails. Tim, what do you got going on?

## [00:01:02] Tim's Fail

[00:01:02] **Tim:** Well, you already buried my lead. So, uh,yeah, yeah, that's my fail. I was sick for 10 days straight and the first, like, 7 days of that, I just slept. I did nothing but sleep. I barely got out of bed to use the bathroom. I barely ate. I just had absolutely no energy. And then once I was well enough to get out of bed, then, like, the coughing was so bad.

[00:01:27] **Tim:** I was, I would cough until, you know, I would just kind of,

[00:01:32] **Adam:** Pass out from

[00:01:32] **Tim:** yeah, yeah. From exhaustion from coughing. But so today, you know, 10 days later, just the first day I'm still not a hundred percent, I didn't want to miss another show. so you might hear a little congestion in my voice, but yeah, today was the first day I actually did. A full day's work of, worth of work. Now I've been working this whole week. So today's Thursday. So Monday, Tuesday, Wednesday, and today, Monday, Tuesday, Wednesday, it was kind of like work a little bit and make sure nothing's burning. Go lay down, get up, do a meeting, go to bed. but today was the first day I was glued to the computer all day and got actual good stuff done.

[00:02:09] **Tim:** So glad I'm feeling better. I guess it could be a triumph that I'm feeling better today, but my fail is I I had, and I had so much lined up last week and I hated missing it. And the bad thing is I deleted like a bunch of meetings off the calendar and I don't know what those were.

[00:02:25] **Adam:** Oh no.

[00:02:26] **Tim:** I'm just hoping that someone reaches out to me and say, Hey, because I canceled it and said, Hey, I'm sick.

[00:02:31] **Tim:** I don't, no one's rescheduled.

[00:02:34] **Adam:** do you know if you could like look in your outbox, your sent box in your email and see if it sends like cancellation

[00:02:39] **Tim:** Yeah, for the ones I sent, but I don't know if the ones I received, I usually delete the, the invite. So, so anyway, that's my failure, but thus is life. What can you do? And Ben Carroll, hope you feel better.

[00:02:55] **Adam:** indeed.

[00:02:55] **Tim:** Oh, and my wife got it yesterday. So,

[00:02:59] **Adam:** I don't think you have said, do you know what you had?

[00:03:01] **Tim:** it was not COVID. it was just some sort of flu and it was a bad, it was a really bad flu. It's just, I felt the same way back in September when I was in Miami and for a, for a work conference. Got sick there, but yeah, so, but now unfortunately my wife has it and she's in bed and so, and, oh, my, sorry, my poor daughter, it's her spring break this week from high school, it's her last high school spring break and she had so many plans and my wife started feeling bad the beginning of this week.

[00:03:31] **Tim:** So it's pretty much, she's just staying on her computer doing nothing and can't, can't do anything. So I feel really, really bad for her.

[00:03:39] **Adam:** sucks.

[00:03:40] **Tim:** How about you, Adam?

## [00:03:41] Adam's Fail

[00:03:41] **Adam:** I'm also going to go with a fail. I thought I was prepared to have this, co op start. and as it turned out, I was not as prepared as I thought I was. so, you know, we've talked about a little bit about the, the kind of the first assignment I was going to have him do, working off of like a spreadsheet that listed a bunch of, our like background jobs, Lambda functions and things that, needed a specific addition, right?

[00:04:06] **Adam:** So the, we needed to add a dead man's snitch to a bunch of them. Somehow we had gotten this far without ever snitching and a bunch of really important things. And so, you know, I was starting to show him around that and as we got into it, it was like, you know, eight or nine out of ten, needed a lot of like, let's just say yak shaving, right?

[00:04:26] **Adam:** So like in order to add the snitch using the code that I wanted him to do, he had to import this, node module, the TS modules. I've talked about it in the past on the show. and, because of some of the things in that module, it's got a minimum Node 18, version that's required, so, you have to, because it uses fetch, native fetch, so it has to be Node 18 or later, it's all ESM and it's, I guess, written or compiled or whatever in such a way that the code that you're using To consume my module and use it also has to be ESM, meaning not CommonJS, has to be ECMAScript modules that import, export instead of require.

[00:05:07] **Adam:** and a couple of other things, this and that, and as a result, it was like, you know, okay, well, we want to do this one thing that's going to take 10 minutes and we're going to have to do this in 30 places. But in order to do the 10 minute task, we have to upgrade the version of Node and we have to convert everything from CJS to ESM.

[00:05:26] **Adam:** And some of these, you know, some of them are like, okay, a one file, 30 line thing. Some of them are like 15 files, 500 lines, and it's a whole bunch of work. So it's just like, and everything that we looked at was just snowball after snowball after snowball. And I felt really bad, but at the same time, it's like, well, you know, you're getting sort of the real world experience here.

[00:05:45] **Adam:** you know, this is just a fact of life when you're, you know, maintaining a bunch of code that works fine until you need to change it. You know, you don't, you don't change it just because there's new stuff. You change it when you need to change it. And that's, that's the way

[00:05:58] **Tim:** we, we take for granted how much complexity we have in our own systems. We think, Oh, cause particularly the areas you never touch, but there's a whole lot of complexity there. And then when you do have to touch them, you realize, wow, okay.

[00:06:11] **Adam:** Absolutely.

[00:06:12] **Tim:** Yeah.

[00:06:14] **Adam:** So I paired with him pretty much all day, every day this week so far. Today I gave, I did like about a half day on and off with him, you know, spread out over several hours. and then. Hopefully, like, tomorrow, which is Friday, and next week, you know, it'll be mostly hands off. You know, just kind of check in with them in the morning, midday, and end of the day.

[00:06:35] **Adam:** And after that, hopefully it'll just be like, sort of like a, I don't know, mostly hands off sort of thing. but he's getting, he's getting in the lay of the land and he understands what he needs to do. So things are going well so far. It's just, you know, sorry for all the yak shaving. That was not the plan.

[00:06:48] **Tim:** yeah.

[00:06:50] **Adam:** I was so, I won't say that I was confident, but I just, I felt good. Like I felt like I had good work lined up for him and I was like, okay, we're going to start with something easy. That, but that's also, you know, good for the company and important. And it'd be like a good little feather in your cap to start your co op.

[00:07:05] **Adam:** And like,

[00:07:06] **Tim:** Now you understand why when, I brought Carol in to be an intern, the first day I had her, putting together chairs, office chairs.

[00:07:14] **Adam:** Yeah. Well, so, uh, I guess that's that. So, I don't think I mentioned at the top of the show, the, the, the topic du jour. That sounds good. I'll have that. is going to be two questions for Tim. not just because Tim was gone last week, but, Tim and I, where our Venn diagram overlaps tends to be on these two topics, compliance and, payments. And so, you know, we both have a good bit of experience in that, or you certainly have a lot more experience than me in compliance, but, I find myself down that rabbit hole. Anyway, so I have two questions for you.

[00:07:49] **Tim:** Hopefully I can answer them. Otherwise this will be a short show.

[00:07:52] **Adam:** otherwise we'll have to find something to talk about. I'm sure you'll have some opinions or, you know, there'll be something worth talking about.

[00:07:58] **Adam:** Which, where would you like to start? Which one? Compliance or payments?

[00:08:01] **Tim:** You're your choice, sir.

[00:08:02] **Adam:** Dealer's choice? Okay. I feel like this one is going to be the probably easier one to answer. So let's start with the one that I expect to be shorter. so payments wise.

## [00:08:12] Is There a Perfect Payments Solution?

[00:08:12] **Adam:** Is there a company, service, product, something that will do everything, including, so you want, I want, you know, online payments, you know, for every, every type of card, plug and play with various gateways, right?

[00:08:29] **Adam:** I don't want to be tied into just Authorize. net or just whoever else, VeriSign or who, you know, VeriSign is SSL certs, I think, whatever, you know, you get the point. Um,So I want to be able to tie in with multiple gateways. I would need to support credit cards, Google Pay, Apple Pay, PayPal, Venmo. And I want a card, card present payment.

[00:08:52] **Adam:** Like, so, you know, they have those like devices where you come in, you swipe the card and it prints out the receipt and you can tap, tap in your whatever planet. we have found companies that do Subsets of that, and between the companies, we can cover all of it, but we've never found like the one unicorn that does everything and does it securely.

[00:09:10] **Tim:** That's the, that's the question.

[00:09:12] **Adam:** the qu that's the question.

[00:09:13] **Tim:** right. So the first part of the question where you said different gateways, so you wanted to be able to have different gateways.

[00:09:22] **Adam:** Yeah,

[00:09:22] **Tim:** mean by that?

[00:09:24] **Adam:** right, so, we generally, well, how do I put this? Our customers are schools, and they have long established relationships with Gateways. You know, they might be using CashNet, or, you know, or whoever, or BlackBaud or whoever to, to do their, all of like campus wide payments, right? When you swipe your card at the dining hall to when you pay your tuition to everything, it's all done through, this one, Payment gateway.

[00:09:57] **Adam:** And there's not like one standard. It's not like every school uses one thing. I'm sure, I'm sure every gateway wishes that was the case and they wish it were them, but it's not. So there's, we, we have, a custom, we have a diversity of gateways that our customers are pretty much required to use. Well, it would be so, it would be really nice if we could just say, okay, well, we'll do Stripe, And, and then it will funnel it to you or whatever, but that, that puts a lot more compliance, issues on us.

[00:10:24] **Adam:** We don't, and we don't want to be in the middle there. We just want to be like hands off, give us the credentials that we need to hook up to your gateway and it'll, and it'll go. which that's why we use Spreedly. you know, they integrate with everything. Spreedly even now has support for Braintree. So you can just like put in your Braintree credentials and it'll go into your Braintree, whatever accounts.

[00:10:42] **Adam:** So does that answer the question? Yeah.

[00:10:46] **Tim:** the challenge on that and why I would say that requirement right there makes that pretty much impossible because, so gateways are kind of like, they are the tail end of the dog. basically you have, you have a processor, so you have a, you have a processor and a processor will, sub out to, Lots of gateways.

[00:11:08] **Tim:** So right now, our gateway, we're in the process of moving up the food chain to become an actual processor. and so gateways, they're just people that have a relationship with the processor and they can, you know, one processor could have 10, 000, 20, 000 different companies that are being a front end, they're dealing with the actual clients, right?

[00:11:33] **Adam:** And they typically tend to focus on a certain niche market. Like we do, we focus on the insurance market. And so Spreedly, I mean, sounds like one that could be, but it's, if you wanted to say all of them, I don't think that's possible. Maybe not all of them, but like enough of them to say, you know, I could get a list of the ones that are important to us, but I don't have it handy. I mean, CashNet, BlackBaud, probably Authorize. There's probably like maybe another three or four that are really common that we see.

[00:12:06] **Tim:** yeah, there might be some, particularly in a certain sector seat. I've, I've, the only one that I've heard of that you mentioned was Authorize. I've never, never even heard of those other guys. And of course they probably never even heard of PayCloud. Right. So, so that makes it really, really hard. And then, cause what they all do and what, what we do is we, we We take, you know, that processor has a set of APIs and we build a separate set of APIs in front of it.

[00:12:30] **Adam:** And then someone like you or whoever, there, I mean, there's probably five, six APIs that are going through this entire chain to get to the, to the actual card processors network. That explains why it's always so slow when I submit my credit card.

[00:12:46] **Tim:** yeah, yeah. And it's all for, I mean, it's, it's a bit of a, not a pyramid scheme, but I mean, it's like, you know, Visa doesn't really care.

[00:12:56] **Tim:** about anything other than they are the network and they're going to take their fees. The bank, there's a sponsor bank that's somewhere, so the processor itself, and the next one down is the processor, the processor themselves, all they really care about is they want to make sure that the money that is being settled while it's in the flux between the coming up, you know, being charged in the card network and actually being Actually settled, which is usually even though you get, they get their money the next day, it's usually two to three days later that they get their money, that the merchant gets their money.

[00:13:29] **Tim:** the bank in the meantime is lending that money at a percentage rate that's called the float. So that's all they really care about. And then you have all these other entities that just are building technology on top of it to sell to the end user. yeah, that's a tough one. I don't know of one, so.

[00:13:49] **Adam:** Yeah. And it's, it's tough because like. You know, they come to us with these requirements, you know, the, the, they, they forget that they are basically stuck with a gateway from 1990 that's like, you know, operated by a dog on the phone and, and that's it. and they come to us and they're like, you know, we need your product to, to do, you know, online payments and Venmo and PayPal and Google Pay and Apple Pay.

[00:14:15] **Adam:** And all that and, and we'll go, we can do that. Does your gateway support that? You know, like our app, we can plug it in and it just works, but it depends on your gateway. And if your gateway doesn't support, you know, Google Pay and Apple Pay, then you're not going to get Google Pay and Apple Pay.

[00:14:31] **Tim:** Yeah.

[00:14:32] **Adam:** And I'm like, you know, there's, there's only so much we can do without.

[00:14:35] **Adam:** Standing up something else in the middle there.

[00:14:38] **Tim:** Yeah. So it sounds to me like what you're doing is you're just saying give us your credentials. And we'll stick it in somewhere like in Spreedly or,

[00:14:46] **Adam:** I mean, it, it is, yes, they go into Spreedly so that we don't have to, like, submit them with the request and we get, like, a, a environment key in secret or whatever from Spreedly that we use to encrypt the, the requests. But then, yeah, they have, like, I mean, it's the same thing. So, you know, if you've put Stripe on a page before, you know, you have, like, your, your public key and your private key, just like anything like that.

[00:15:09] **Adam:** And then, you know, we just provide those. You know, if you've got, Authorized or BlackBaud, you know, you've got a public and a private key, you give those to us and we, we plug it into Spreedly or we can do a couple other things with it. But, it's frustrating because we're stuck in the middle, right?

[00:15:22] **Adam:** Like it kind of makes us look bad, but it's not even our fault.

[00:15:25] **Tim:** no, it's not. And I've had people come up to me at like trade shows, like, who was it? It's a pretty big company. Like it was pretty, pretty, really big insurance company. And they're like, look, here's our problems. So we have like all these different payment providers that, that are having, and, and, you know, we want to be able to move, you know, To do like recurring payments, you know, to set up, to pay their premiums every month where they don't have to re enter their card, we just charged them.

[00:15:49] **Tim:** But it's like, there's, they're all segregated. And I'm like, how, how can we, is there a way we can move? We could, you know, they're, I can't, they're calling them,card tokens. Is there a way we can like, Have a universal card token that works across all of them. Like, no, sorry, that says they've set it up that I mean, everyone, everyone has their vested interest, right?

[00:16:09] **Tim:** And that's the other thing is like once you know, you have this secure card ID, To move it is a whole manual process and that you're not even, if you're the customer, you're not even the part of it that, or if you're the merchant, you basically have to make a request and say, I don't want to use you anymore.

[00:16:25] **Tim:** I want to use someone else. And those two entities have to talk to each other and then securely move it because they actually have to send the physical card number. they decrypt it, send it encrypted, they decrypt it, and then they put it in and destroy it, supposedly.

[00:16:39] **Adam:** Mm mm.

[00:16:40] **Tim:** so.

[00:16:41] **Adam:** I'm not sure how much I believe that, but that's what they're supposed to do.

[00:16:44] **Tim:** no, no. So yeah, it's a, it's a, it's a, it's a nice racket.

[00:16:52] **Tim:** If you're part of the, if you're part of the process.

[00:16:54] **Adam:** If you're the one collecting.

[00:16:56] **Tim:** Yeah, exactly. If you're, if you're one of the people getting your little piece of the stream of the river, it's pretty good.

[00:17:04] **Adam:** Alright, well, you know, that was a bust, so maybe, maybe you can help me with my other question, my compliance question.

## [00:17:10] Finding the Right Compliance Auditor

[00:17:10] **Adam:** I would say that I am not completely happy with the vendor that we picked, as our auditing. we have some software that we also pay for. So there's like a vendor for the, the compliance, like management or organization software, you know, it's like, helps us stay on top of making sure everybody's agreed to our policies on time.

[00:17:30] **Adam:** And, you know, let's just know, okay, it's time to recollect the evidence that says, you know, everybody's computers are using full disk encryption, that sort of thing. That's the software end of it. And we're reasonably happy with that. I mean, You'll always want to spend less money on anything. So I wouldn't be mad if the price went down, but functionality wise, we're reasonably happy.

[00:17:51] **Adam:** What we're less happy with is the auditing firm that we picked. and I'm, I'm trying my best not to like name and shame. You know, I certainly don't want to do that. or even

[00:18:00] **Tim:** were they the ones I talked, I did a conference call with you and them.

[00:18:02] **Adam:** yes, I think so.

[00:18:05] **Tim:** Okay. I know, I know there.

[00:18:07] **Adam:** yeah, and, I'm just like, What, how do I not fall into this trap again next year? So assuming we're going to pick somebody else for next year, what questions do I need to be asking during the sales process where like I'm the customer and I'm going around trying to find the right. How do I not fall into this trap again? So the, the, the things that are most frustrating to

[00:18:31] **Tim:** Yeah. I was going to ask, I was going to ask what's your friction points right now?

[00:18:34] **Adam:** Yeah. So, you know, we have this software and not only does it do things for us, like it monitors our AWS account and it says, okay, you, you have an IAM user that has a access key. That's more than 90 days old.

[00:18:46] **Adam:** So that needs to be rotated sort of thing. you know, it does all this stuff for us. Not only does it do that, but, there's like a way to comment on stuff and like tag people. You can reassign tasks, right? So it's kind of like you can think of it as like GitHub issues, but made specifically for the market of compliance, right?

[00:19:04] **Tim:** You can reassign stuff, you can whatever. And let me, for context, which. Compliance audit? Is it Soc

[00:19:12] **Adam:** yes, this is for specifically for SOC2.

[00:19:15] **Tim:** SOC2. Okay.

[00:19:16] **Adam:** and I mean, to be honest, I think that the process that we went through for PCI was similar. It just was a easier bar to clear. So,

[00:19:24] **Tim:** PCI is actually, yeah. Compared to Sox. Yeah. It's definitely

[00:19:28] **Tim:** well, let's, I, we, we got some comments last time that the, that we made this,had a similar conversation. Yes. It's not Sarbanes Oxley, not S O X, S O C, SOC2. I'm, I'm, I'm on the page with you.

[00:19:39] **Adam:** yeah, yeah. Anyway, so we've got this software and it's got like a communication and organization built into the software. And I specifically, when I was, I don't know what term to use other than like interviewing, like talking to sales firms, auditing firms.

[00:19:55] **Adam:** I was like, okay, and you can work with this software, you'll be able to do that. And they're like, oh, yeah, yeah, no problem. And now we're, you know, we've collected all our data, our review period ended on December 31st, it's April 4th, and we still haven't completed the audit because, you know, like, they needed a month or two to review the data, and then she went out for a week, and then I was gone for a week, well, you know, okay, but that was, you know, the first week of March, so I would have figured we would have been done or close to done by then.

[00:20:23] **Adam:** every time that they send us you know, like a request for more information or whatever, it always comes in the format of a Word document containing a table and in those, in that table is like a requirement number and, and like a description of what it is that they want. And I'm like, well, if you're going to send me a table, why didn't you make it an Excel spreadsheet?

[00:20:45] **Adam:** Because that's way more usable. Right? Like I got one, the, one of the requirements is to send them a list of every change that you've made to your code. and then from that list, they will make a random sample request. They'll say, okay, you sent us these thousand changes. We want to see the detail view of A, B, C, and D, right?

[00:21:06] **Adam:** They'll just pick them at random. And you send like the full. So they can see that it got approved and that it ran tests and all that stuff. and she sent me a Word doc that contained a table and in the table was the URLs of the pull requests, but they weren't clickable. They were just text. And there was enough of them that I wasn't going to like, highlight each one and say, okay, you know, command K to make it a link and then go do the next one, go do the next one.

[00:21:33] **Adam:** So I could then click on them. So what I ended up doing was I copied and pasted that word table into Excel so that then I could copy just the column that contained the URLs. And I pasted that into VS Code, and I told VS Code, this is a markdown document, so then it would, I could just like click in each of the, click on each of the links and it opened them all as tabs.

[00:21:55] **Adam:** But it was like bananas. And really what they should have done is left a comment on that particular, you know, evidence collection task is what it is in the system, right? And it says, You're required to do this. Here's the schedule that you're supposed to do it. And you can like go in and physically attach screenshots or PDFs or whatever right there to the thing.

[00:22:15] **Adam:** And instead of replying and saying, okay, these are the detailed ones that I want. She sends, she emails me a word document containing a table. I'm just like ripping my hair out. Like use the tool you told us you would use. And, and everything, I feel like I have to explain everything three times too. Like they're just not, I don't know if they're spread too thin or what, but

[00:22:36] **Tim:** I mean, I'm sure, I'm sure they're working on more than one project, right?

[00:22:38] **Adam:** yeah, oh,

[00:22:39] **Tim:** lag, a lag in time between response and getting info. I wish I could tell you, cause we use multiple auditors. The experience is similar for all of them, but the, the only positive thing I could tell you, the advice I could give you is, I mean, 'cause this is like one of the first times you've done this.

## [00:23:00] Making Customer Demands

[00:23:00] **Tim:** So knowing this, now you are the customer here. I mean, think about how your customers bully you, right? They bully you. They're like, yeah, you need to have, you need a PCI, you know, seven compliance, even though you only need, you know, one, I'm making up this. That's not a real thing. People like, I'm, I've heard stories where, where customers are like making you do things which are completely ridiculous because it's important to them.

[00:23:25] **Tim:** You can do that to them. You can at the, at. Even like if you choose to use the same one, right? Because you at least, you know, how the software should work. You could see how it should work. You make that a requirement of the next contract that comes up and says, here's what we want from you next time.

[00:23:43] **Tim:** We want you to use the tool.

[00:23:44] **Tim:** We don't want to receive Word documents attachments. You know, if there's a link, it needs to be clickable. use, use the tool that you, you know, told us to use to do this rather than, you know, a bunch of these, these work because it makes it difficult for us. If you don't do that, we're going to talk to another vendor.

[00:24:03] **Tim:** Oh, no, if you don't, we are talking to another vendor and, and they've said they will do that for us.

[00:24:09] **Adam:** Right. Yeah, absolutely.

[00:24:11] **Tim:** So,

[00:24:12] **Adam:** Yeah, there was another vendor early on that you had suggested to me that I talked to, and the only reason that we didn't go with them, I really liked, the guy that I talked to, the sales guy, and. He seemed really knowledgeable, seemed to be, you know, Could understand the words that are coming out of my mouth.

[00:24:28] **Adam:** and, the only reason that we didn't go with them was because they were significantly more expensive.

[00:24:33] **Tim:** that we continue to use them just because they kind of do things the way we want to.

[00:24:38] **Adam:** Yeah.

[00:24:39] **Tim:** so that, that would, that would be my advice. Just remember, you're the customer here. If you're not getting the product you want, tell them the product you want. If they can't give it to you, go somewhere else. But then, but then that means you got to learn new software, which is the pain.

[00:24:52] **Tim:** So we, we, we've stuck with some for years just to see if it got better. And then if, if it didn't, we're like, okay. We have a luxury, we have like a whole team of people that do this for us. And you're just one guy with another job, right? So we have like a compliance department with I think about five, six people.

[00:25:09] **Tim:** And this is all they do for us.

[00:25:11] **Adam:** I, I, do not envy those people. You know, like,

[00:25:14] **Tim:** They are people that oddly love it. There are a lot of ex, several ex military. That, that love filling out the checklists and you know, they just get off on that.

[00:25:24] **Adam:** So there's a, there's a thing I'm trying to like, something about like, you know, rearranging the deck chairs, right? Like there's that person on, on the coding team who like gets off on just making sure the readme is perfect and wanting to make sure everything is documented and all the tests that you get, like a hundred percent code coverage or whatever, like they're, they're working, but they're not actually like making the product better.

[00:25:50] **Adam:** They're just working.

[00:25:51] **Tim:** they're not creators. They're like accountants.

[00:25:53] **Adam:** Yeah. And, and like, oh man, I, that, I, it couldn't be me. God bless them. I'm glad that they love their work, but

[00:26:03] **Tim:** No, I mean, I've dealt with it just enough. I'm like beside it because I'm part of the process, but I am not the person in charge of it. And thank God, cause I could not, I could not handle that as my day to day job. But there's a certain personality type that love it.

[00:26:19] **Adam:** I guess it takes all kinds.

[00:26:22] **Tim:** Yeah,

[00:26:22] **Adam:** if, if you got any that are looking for another place to work,

[00:26:25] **Tim:** right.

[00:26:26] **Adam:** let me know.

[00:26:27] **Tim:** chairs the ones we got. I'll do a slide aside because you just made me think of something. So a problem that I've been dealing with is like trying to do some banking contract and our lawyers are just scared to death. Our lawyers are just scared to death of like committing to it. It's because they're not comfortable.

[00:26:43] **Tim:** They don't really understand it. And so we got a new CFO recently, a couple levels, a couple levels of companies above us. And, it was, I was talking to him about the problem and he's like, you know what? It sounds to me like what you, we need to do is get you a professional bureaucrat. To help out. He says, because all of this stuff that the banks ask you are BS.

[00:27:05] **Tim:** So I was like, yeah, that makes sense. And that's, that's another different mindset, this sort of bureaucrat that understands, yeah, you're asking me to do all this stuff and I understand why you're asking. But I also understand that, you know, what you're asking is impossible. So I'm going to kind of dance, we're going to give you the answer you want, and I'm like, I can't do that.

[00:27:23] **Tim:** I absolutely can't do that. I wish, I,

[00:27:25] **Adam:** dance there and that, that just, it's the perfect way to describe it.

[00:27:28] **Tim:** yeah, I just want to point out how absurd it is, right? I just want to fight on that hill, and the bureaucrat's like, I'm not, I'm not fighting on that hill. I'm just going to tap dance around it and say, yeah, we're going to do it, but in a way that also says, if we don't do it, you really can't hold us accountable.

[00:27:42] **Tim:** So,

[00:27:42] **Adam:** Makes me think about like politicians, right? Like they're, they have to, they have to find a way to work within the system and, and get stuff done. That's the idea anyway. but they're, you know, but the system is constantly fighting them and asking them to do ludicrous things.

[00:27:58] **Tim:** yeah.

[00:27:59] **Adam:** And you're right. Like, I just want to be like, You don't understand.

[00:28:03] **Adam:** That's not the way our business model works. We don't have that data. Like, I can't show you evidence that we don't have something that we don't have.

[00:28:12] **Tim:** Yep.

[00:28:12] **Adam:** You want me to screenshot every bit of data in my database to prove to you I don't have credit card numbers? I don't have a credit card number. yeah, it's ridiculous.

[00:28:21] **Tim:** that all you got?

[00:28:22] **Adam:** Yeah, that was all I came prepared with.

[00:28:24] **Tim:** I hope it was a helpful at all.

[00:28:26] **Adam:** no,

[00:28:27] **Tim:** No. Okay. Well, there we

[00:28:28] **Adam:** yeah, no, I mean, absolutely. The, the, it's disappointing that there's not like, oh yeah, you just need to use this vendor sort of thing.

[00:28:37] **Tim:** Now there may be one out there. I just knowing what I know, I imagine that's pretty impossible to keep track of because there's new gateways popping up, they pop up like mushrooms.

[00:28:45] **Adam:** Yeah. Yeah. And that's the thing. It's like, you know, we see some that they're like, oh yeah, we do, you know, the, the card present device and Venmo and PayPal and Apple Pay and Google Pay, but they don't do online or, you know, they do, we do online and Google Pay and Apple Pay. no card present or, yeah, and it's just like, or there, there might be some that do it all, but it's like, like, for example, I think Stripe might do everything.

[00:29:14] **Adam:** I think Stripe even has a card present device that you can get from them. Or maybe they're like, they have an agreement with another company that can kind of hook the two together, but either way, but it's only on Stripe, right? You can't, hook it up to somebody else's gateway. And I think that that Therein lies the rub, which is infuriating.

## [00:29:36] Meeting Customer Demands on Payment Gateways

[00:29:36] **Tim:** I hate to circle back, but I just thought of something. I mean, it'd be a bit hard sell probably, I guess, to your customers because they already have a relationship, but would they be willing to sign up with a. Gateway of your choice and get a merchant account with them just for that. You tried that out.

[00:29:52] **Tim:** Oh yeah.

[00:29:52] **Adam:** we've tried to make that a case and I think we've come pretty close a couple of times. Like with, you know, maybe not with my product in particular, but we have a couple of other products and like, you know, the reunion thing where it's a little bit more siloed off, you know, it's just like once a year for a couple of weeks out of the year that they're spending and making money.

[00:30:13] **Adam:** So it's easier for them to, to wrap their heads around. Like, this is just like a temporary thing. and. And be willing to, you know, I guess, you know, route that, okay, it's, it's all done in this little bubble and then we put it in our accounts receivable or whatever, and we have to go through all the accounting for all that.

[00:30:30] **Adam:** yeah, I don't know. I mean, maybe that's the future to, you know, because it is very much, you know, that, that video, that's like the expert, right? We want you to draw six perfectly perpendicular lines. and you know, we want you to, we want them to be blue, but you have to use red ink and that, all that stuff.

[00:30:48] **Adam:** that, it very much feels like that, right? They're asking us to do something that is impossible and they're the ones making it impossible.

[00:30:56] **Tim:** Well, if you've ever seen a credit card merchant application, you understand why they want, they want like the principal owners, social security number, copies of their bank statements, tax returns. I mean, they want, they want a lot of information and that's, if, if you do that once because you have to, you don't want to do it again.

[00:31:15] **Tim:** It's a very. Invasive process to get a merchant application. I'm surprised anyone does it, but they have to, if they don't take cards.

[00:31:23] **Adam:** Right. Yeah. Okay. Well, I mean, it was a relatively short show, but, that's what we got for you tonight. So I guess

[00:31:29] **Tim:** I mean, there's half the people here. It's half as long, so

[00:31:33] **Adam:** There you go.

[00:31:33] **Tim:** it's proportional.

[00:31:34] **Adam:** but, so yeah, I guess we'll wrap it up there.

## [00:31:36] Patreon

[00:31:36] **Adam:** Okay, this episode of Working Code is brought to you by this new company that takes payments and they do everything. all you have to do is wait, until the heat death of the universe.

[00:31:44] **Adam:** I'm pretty sure it will exist by then and be ready. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:32:01] **Adam:** Special thanks, of course, and as always, to our top patrons, Monte and Giancarlo. You guys rock.

## [00:32:07] Thanks For Listening!

[00:32:07] **Adam:** we're going to go do the after show, which I'm sure by now, you know what that means, today, tonight on the after show, Tim, you are auditioning for a movie. You're going to, you're like up against Tom Cruise.

[00:32:17] **Tim:** no, no, no, no. It's not that it's, you know, it's back, it's background work, but I'm hoping I applied for something and hopefully I get it. It sounds like a cool project. Yeah, I'll, I'll, I'll, I'll say what I say. Yeah. I'm going to meet Tom Cruise. 250, 252. 57. Two 50 year old men going up against each other.

[00:32:33] **Tim:** I wonder who

[00:32:34] **Adam:** as height. If you'd like to help us out, you can go to patreon.com/workingcodepod and throw a few dollars our way to keep the lights on around here. that's going to do it for us this week. Well, we'll catch you next week and until then.

[00:32:47] **Tim:** Remember your heart matters. Even you tap dancing bureaucrats.
