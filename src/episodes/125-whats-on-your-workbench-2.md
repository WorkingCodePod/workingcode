---
title: "125: What's on Your Workbench? #2"
description: "On today's show, the crew discusses a variety of topics around what they've been working on."
date: 2023-05-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/125-whats-on-your-workbench-2/id1544142288?i=1000611578282"></iframe>

On today's show, the crew discusses a variety of topics. By which, I mean, Ben waxes philosophical on the subjective nature of _everything_; and, how he wants to live in a world where those who choose to indent code with 2-spaces may peacefully coexist alongside those who choose to indent code with tabs. Also, Adam body-slams his younger brother into a concrete floor. And then, gets in trouble because he let blood get on the carpet. Be sure to listen for Adam's pro-tips for removing blood stains.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/125-whats-on-your-workbench-2.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I don't think that the FBI will be that upset with you if you call and say, I'm not sure if we're supposed to reach out to you yet or not, but here's what's going on.

[00:00:09] **Ben:** No.

[00:00:10] **Tim:** is, is is running up our SMS bill.

## [00:00:14] Intro

[00:00:14] **Adam:**

[00:00:33] **Adam:** Okay, here we go. It is show number 125, and on today's show, Carol will not be joining us. We were just sitting down to record and water started coming out of her ceiling fan. So, good luck, Carol. Hope that turned out okay.

[00:00:46] **Tim:** An unexpected water feature.

[00:00:48] **Adam:** she had to go. so, that's two weeks in a row. I feel bad for, for going without her, but the show must go on. so as usual, we'll start with our tramps and fails. And Ben looks like it's your turn to go first.

## [00:00:59] Ben's Failure

[00:00:59] **Ben:** Yeah, so last week I talked about just feeling pretty mad in general and my failure is that I'm going to keep being mad. For a while. I just, I'm having almost like a little bit of an existential crisis. I, I think, a a, as you all know, I'm migrating slowly from the old platform at work to the new platform at work.

[00:01:19] **Ben:** And I, and I've started to look through the code and, um, don't love it. Don't love it. And here's the thing, right? It's like if I, let's say I was unemployed right now, and the job that I need to be doing here at work was in a, in a opening, a job opening. And I'm reading it and I'm looking at the technologies.

[00:01:37] **Ben:** I'm like, you know, heavy on react, heavy on Go Lang, heavy on microservices. I feel like I would not apply for this job. Like, it's not, it's not the kind of job I would opt into if I had a pick of a lot of things. And that's like a really weird place to be in.

[00:01:56] **Adam:** mm.

[00:01:56] **Ben:** It's like, you know, we've talked a little bit about, the Peter Principal in the past.

[00:02:00] **Ben:** Where you get,

[00:02:00] **Tim:** Filling up.

[00:02:01] **Ben:** Yeah, yeah. You get promoted to where you become inadequate for the job. And I almost, it's, this is like, this is like some sort of corollary to that. Like I've been moved into a project where I'm no longer effective and, I dunno, it's, it's, it's a weird place to be. I'm feeling very out of sorts and I'm not like a hundred percent confident that I'm gonna, that I'm gonna get there, but it's still early, so we'll

[00:02:28] **Ben:** Do you still feel like you are, are maybe married's not the right word, but like tied to the project and the product in a way that is rewarding? Like you still want to support the same product and, and customers or, I mean, I, I love, I always love our customers. If, if anything, I think the fact that I have not been very customer facing lately has been a big part of my darkness. I do get a lot of energy from, from dealing with customers, if not directly, then at least like, feel like I'm building something for them and that's not really been the kind of stuff that I'm doing right now.

[00:03:06] **Ben:** So that's, you know, we all, we all, we all have our strategies for success and, and my strategy for success is being a little bit more customer facing than I am today. So maybe, maybe getting back to that will be helpful.

[00:03:20] **Adam:** There's always positions open on the help desk.

[00:03:24] **Ben:** Oh man. Yeah. Actually I think some of our help desk people have are like part-time now as QA engineers as well.

[00:03:32] **Tim:** Oh, wow.

[00:03:32] **Ben:** as part of the cost cutting initiative, we, we got rid of all of our, our, our QA people were primarily contractors and, we've unfortunately gotten rid of them

[00:03:41] **Tim:** What is Facebook called that they're the year of, what's the, what's the term that they call it?

[00:03:45] **Adam:** You're

[00:03:45] **Tim:** Year of efficiency.

[00:03:47] **Adam:** layers of layoffs?

[00:03:48] **Tim:** Yeah. Year of efficiency. Yeah.

[00:03:50] **Ben:** I, I had talked, maybe a couple of months ago, I had been listening to a podcast with Chris Coyer and he was doing a 10 year review of the, of CodePen. He was, it was basically the podcast was him and his co-founder and they were talking about all the things that they've learned over the last 10 years.

[00:04:08] **Ben:** And one of the things that they brought up, which feels so timely for me right now, is to only learn one thing at a time. And they talked about moving from, I think it was like Ruby on Rails over to Go Lang for some things. And they weren't building new functionality and learning go at the same time.

[00:04:27] **Ben:** They were taking existing functionality and porting it over to go so that the business logic and the requirements weren't something they had to learn. They were learning the go and they were doing it in a very safe context. And, and there's a part of that that makes a lot of sense to me. so when I look at my transition from the old platform, the legacy platform to the modern platform, it's like I'm learning new architecture, new languages, new permissions models, like I'm learning like a butt lotus new stuff at the same time.

[00:04:56] **Ben:** And it, and it really drives home how that's not, it's not the

[00:05:00] **Tim:** Ideal. Yeah.

[00:05:01] **Ben:** Yeah, yeah. Sub, sub ideal subpar. So that's me. still may hopefully better next week. Tim, what do you got going on?

## [00:05:11] Tim's Status Quo

[00:05:11] **Tim:** Well, I, I don't have a failure or triathlon, which is calling status quo. nothing great, nothing bad. one interesting thing that, we learned today, so we had a, a call organizational white call with our legal council, to talk about how to deal with a data breach. I mean, they're happening more and more.

[00:05:32] **Tim:** I mean, so our, our, we're part of a big multinational company that buys, you know, other software companies and just overall, Around the, you know, around the company, there are data breaches that happen and ransomware and, and you know, there basically the, the whole thing was really to talk about how to communicate with your customers when you're doing this because there is some, legal liability that you need to be aware of when you're dealing with, talking to your customers.

[00:06:02] **Tim:** And, you know, I mean, none of this is trade secret, so I can talk about it, but I mean, basically it boiled down to don't say forward-looking statements about the breach cuz you know, you, you know, you're, you know, email, you're getting constantly emailed or called by your customers and they're like, you know, what's going on?

[00:06:20] **Tim:** How long is this gonna happen? What can I tell? And they always wanna know, when's this gonna be over? Right? Or, or when is this gonna be fixed? Or what's, what's been exposed? And it's an ongoing developing situation. So you really, you have some information at the time, but you rarely have complete information.

[00:06:39] **Tim:** Until after it happens. And even after it happens, you don't necessarily always have a hundred percent insight into what happened. So one of the biggest thing they said was, you know, number one, you, you, you as a team, as a company, you nominate one person, be the source of truth to contact. and that person talks to the customers.

[00:06:59] **Tim:** And then when they ask about forward-looking statements, you never give them any forward-looking statements. You don't say, oh, we think we'll have this fixed, you know, tomorrow. Cuz then tomorrow comes around and it's not fixed. And now you've lost credibility. Now they don't believe you. Now they think you're lying or they're hi, you're hiding something.

[00:07:15] **Tim:** and then you set a, a, a cadence for communication. You don't promise resolution. You say, listen, I will call you every three hours or email you, there will be communication every three hours, in, you know, during working hours that, that will tell you what's going on. What we know to be true. And that's all you ever tell is what you know to be true.

[00:07:34] **Tim:** And if you don't know anything different from the last three hours, you just say that, right? No new information. Still continue to working on it. stuff like that.

[00:07:43] **Ben:** Let me, let me ask a quick question cuz I know Adam's been working on the SOC compliance stuff. is a i, I hesitate to call this disaster recovery, but is this kind of a thing, something that has to be documented as part of SOC compliance?

[00:07:57] **Adam:** I don't necessarily think that exactly what Tim, Tim is describing, like the, the policy for how you will communicate with your customers and, and like, you know, no forward looking statements. That sort of thing is, a requirement. But you have to have a disaster recovery plan. You have to, you know, there are requirements in this ballpark.

[00:08:18] **Tim:** Yeah. I mean this, so this really isn't a disaster recovery kind of thing, right? This is. A data breach. you do, you know, it's either a data breach where someone has exposed your data and you're trying to figure out what's been exposed, or it's an attack that it basically has, disabled your system where it's not available.

[00:08:37] **Tim:** and you know, people are trying to figure out when, when that happens. So, I mean, we do have a policy for that. It's not part of soc. but that is a policy that we have about, you know, who are the people that are allowed to speak to the customers in regard to what's going on. And, you know, honestly, these things, it's like they happen, they happen at the worst possible times. And, and, and I'm, I'm not saying we haven't, we actually have not been through this, this hasn't happened to where I work now, but has worked, happened at companies I've been associated with in the. That are inside the same corporate shell and it's not fun cuz it's like, you know, you got people who can't run their business cuz your stuff is being tied up and a lot of times there's not a whole lot you can tell 'em.

[00:09:28] **Ben:** Yeah, I know at work we have like a, we have security vulnerabilities that are listed by like priority, like there's a high priority, medium priority, low priority, and then we have to have,remediation timelines associated with them. Like a high, high impact vulnerability has to be resolved within. 36 hours or something, and like a medium has to be done in like two weeks and a low has like 60 days or something.

[00:09:57] **Ben:** But I, I wonder, is that kind of stuff, do you think part of a soc or is that just something we have like as an internal standard?

[00:10:03] **Adam:** that's probably a mix. I mean, one of the things that I had to do as we were setting up, I'm not sure if this was part, I guess it was probably part of both PCI and SOC two, was, you know, you have to go through and identify your risks and you have to classify those and you have to say, okay, this is how we are dealing with that risk.

[00:10:22] **Adam:** Some of it you can mitigate, you know, you can buy insurance or you can, take steps to prevent. or, or you can just accept the risk. You can say, this is just part of doing business in this industry or whatever. and, you know, if, if it's bad enough, right? Like there are some things that are like, okay, yeah.

[00:10:42] **Adam:** The risk of that is happening is pretty low, and if it does happen, who cares? Right. You know, we'll, we will rebuild that database from a backup or something. Right? Like, but then there are other things. It's like, okay, well yeah, that technically could happen. And I guess if it did, we would just, you know, declare bankruptcy and shut down shop.

[00:11:00] **Adam:** Like, you know,

[00:11:01] **Ben:** Yo,

[00:11:02] **Adam:** but we're not gonna, we're not gonna spend a hundred thousand dollars in six months to try and prevent it, you know?

[00:11:06] **Ben:** do you ever have those? I have these dark moments where I think about what would happen in a worst case scenario situation. Like, like, let's just say I accidentally dropped really important customer table. Or

[00:11:18] **Adam:** Mm-hmm.

[00:11:19] **Ben:** I, I, I don't know, I deleted the wrong thing, or I exposed something like really, really critical.

[00:11:25] **Ben:** I, I always think to myself, would I just quit immediately? Like would I just resign like Hannah and be like, I'm sorry. This was my fault. I don't deserve to work anymore.

[00:11:33] **Adam:** manager's office with your resignation letter in hand and be like, I have two pieces of bad news for you.

[00:11:38] **Ben:** Or is it like,

[00:11:39] **Tim:** a sum summeri falling on his own sword.

[00:11:41] **Ben:** Right. And then I think, but, or is it somehow more honorable to stay and try to help remediate or it's like,

[00:11:48] **Tim:** And then get fired.

[00:11:49] **Ben:** yeah, well, yeah. Yeah. But like, I, I don't know. I don't know what people would expect if they expect the immediate

[00:11:55] **Tim:** You always wanna get fired that way. Get, get to collect unemployment.

[00:11:58] **Adam:** Mm-hmm.

[00:12:00] **Ben:** you get fired for. Cause I assume, I

[00:12:02] **Tim:** Exactly.

[00:12:04] **Adam:** Yeah. But then you, then, then, like, you can't like use that as a reference or anything. Right? Like if you get fired that, that's a dishonorable d.

[00:12:14] **Tim:** If you get, if you quit, it's under those circumstances, you're not gonna use that as a reference

[00:12:18] **Adam:** you have plausible deniability if you quit.

[00:12:21] **Tim:** Yeah.

[00:12:21] **Tim:** It just wasn't a fit.

[00:12:22] **Adam:** a golden parachute. Yeah.

[00:12:24] **Ben:** One thing that comes up for me, like every single soc round, I think we have to do it annual or biannual. I can't remember what we do at work. And this comes up every single time, which is GitHub. So I don't know if this is a GitHub specific thing. I guess it is. Maybe, we have a rule at work as part of the SOC compliance that all, every code that gets merged into our primary branch and deployed to production has to have a poll request associated with it.

[00:12:52] **Ben:** And that poll request has to be reviewed by someone who is not the author of the code.

[00:12:56] **Adam:** Mm-hmm.

[00:12:57] **Ben:** So the way GitHub works, and I don't know if this is Git or just like, I don't know if this GitHub or get itself, but let's say I'm working on master and I branch and I say this is Ben's feature branch, and then I have a random idea mid feature, and I branch that branch.

[00:13:15] **Ben:** Now I have Ben's feature branch two.

[00:13:17] **Adam:** Mm-hmm.

[00:13:17] **Ben:** And I get to a place on that and I'm like, oh, you know what? This is actually better. I'm just gonna get this secondary feature branch reviewed, someone reviews it, and then I merge it into master. And I deployed a production because the, the Git commit, the Shaw from that first feature branch is technically included in that second feature branch, cuz it's a branch of a branch.

[00:13:39] **Ben:** GitHub will automatically show it as having been merged in because it technically was, it just wasn't part of like the original feature

[00:13:48] **Adam:** But only if you don't add more commits to that branch. Right.

[00:13:51] **Ben:** Yes. Correct. Which is often the case. Like if I'm, if I'm, well not often the, like the once a year that this comes to bite me in the butt, they'll, and then they'll come back to me and they'll say like, Hey, you didn't have someone review this pr but it got merged.

[00:14:02] **Ben:** I'm like, yeah, GitHub did that automatically. Like, it's not me. And then I have to, I have to show them evidence that this was part of another PR and that PR is reviewed. It's so frustrating. I wish GitHub just left it alone. It didn't do

[00:14:14] **Adam:** can, you can take the Shah of any commit on GitHub and search for it in the, like in the, in the list of poll requests, you can drop a sha and even the short sha, like the first eight characters or something like that, and it will return a list of all poll requests that include that Shah.

[00:14:31] **Ben:** Oh, nice. Yeah, I think what I usually end up doing is the code that in question, I have to get blame it in GitHub. I don't actually know how to do that on the command line, but you know, I, I go into the GitHub UI and I go to the file and I go blame and I go down to the lines in question and I look to see which commit they came from and which PR they were from.

[00:14:48] **Ben:** And that's usually how I, I, I get the evidence, but it's just frustrating. Sorry, that's, it's just the end of side rant there.

[00:14:55] **Tim:** That's a good one.

[00:14:56] **Adam:** We talked about this last week. No apologizing.

[00:14:58] **Tim:** There you go. Well, that's me. How about you, Adam?

## [00:15:01] Adam's Triumph

[00:15:01] **Adam:** Well, I'm gonna go with the triumph. I guess we got the whole spectrum here tonight. Yeah. I, I haven't done a ton of coding in the last two weeks since I've, I've been back from my vacation, but I've done some, and most of it has been in support of my PCI and SOC two projects. so, you know, one of the requirements is that you do vulnerability scanning on your software and on your configurations and stuff.

[00:15:24] **Adam:** And we had a bunch of user accounts with stale access keys associated with them. and so I had to go, okay, well where are all these access keys used and what are they used for? And try to shore that all up. You know, like the easy thing to do would just be to rotate the keys and update them in all of the bajillion places.

[00:15:41] **Adam:** We've pasted keys in all the environment variables and things, but. I'm taking this as an opportunity to make things right, if not, or I'm sorry, better if not, right. and so I've been learning a lot about, I never know if I should say I am or I am,

[00:15:59] **Ben:** Mm,

[00:16:00] **Adam:** access management tooling. and from what I understand, it's not just an AWS thing.

[00:16:06] **Adam:** Like to me it's an AWS thing. I've never seen it anywhere else, but I think that it's supposed to be like patterns and, you know, behaviors and things. It's like a whole set of principles and, and AWS just also calls theirs IAM or whatever, but, right. So like, you know, for example, you know, if we had, a Lambda function that would read files and write files on S3 and maybe it needed to interact with SNS and sqs and.

[00:16:29] **Adam:** you know, like contact another server on our vpc, right? Like all of those permissions would've been applied to a user account. Sometimes they would be shared user accounts for various things that are very similar, or sometimes they would be like a unique user account specifically for this Lambda function because the, we were young and naive, and the thing we knew how to do was to like, okay, copy and paste this code snippet, and here's where you drop in your, the, the access key and the secret key and, and it works, right?

[00:16:55] **Adam:** And so we're like, okay, well we'll just figure out the, the do it better later. Well now is later. and so now I'm figuring out, okay, like this is how I say here's the Lambda function and here's all the services that, that it needs to access. And I can create a role in the Lambda function can be executed with that role.

[00:17:11] **Adam:** And the role has access to the things. And there's no like key management involved that's just sort of inherited or assigned access levels. Which is very nice because now I don't have to worry about rotating those keys and all that, but it's very complicated to figure out. or I, I guess I should say it was very complicated to figure out and, and, I'm now getting better and better at it, but I spent the majority of my week just going back and updating old software to like, okay, what was I thinking six years ago when I wrote this?

[00:17:40] **Adam:** you know, and what, what services does it actually use? what did I over provision on permissions? Cause we're trying to do, you know, principle of least access and just trying to, you know, get, do it as close to write as I possibly can, get code reviews, write tests, yada, yada, yada. but you know, it, it's, we're moving in the right direction and it's, it's a lot of those days where you're like, you finish your day and you're like, really?

[00:18:06] **Adam:** That's all I did today was like I submitted like two poll requests to update two applications to, to rip out their, access key and secret key from the environment variables. But you know that it was a lot of work to get there. And so if it's a not depressing, I don't know, just I don't feel like I have a whole lot to show for my work on those days.

[00:18:26] **Tim:** Yeah, I mean the Im stuff is, it's very confusing. Very complex. I, yeah, I, I, so we have like a few like S3 buckets that are public and because we use 'em for like to store, JPEGs and PNGs that, you know, that

[00:18:43] **Adam:** So that you wanna share publicly?

[00:18:45] **Tim:** Yeah. We wanna share, right? Yeah, exactly. But we'll get these emails on a regular basis from AWS going, Hey, this bucket is public.

[00:18:51] **Tim:** Are you sure you wanna do that? This is insecure. And it's because it's like a group email that it's sent to. It's like, I get all these emails from people concerned. I'm like, dudes.

[00:19:01] **Adam:** you hear about the new format of the t p s reports?

[00:19:05] **Tim:** Yeah, dudes, they're images. I don't care if they're public. No one cares.

[00:19:11] **Adam:** Gotta name the bucket. Intentionally public.

[00:19:14] **Tim:** Exactly.

[00:19:15] **Ben:** At work, I have somehow managed to lock myself out of an S3 bucket in a way that not even admins on the account can unblock me. I don't even know. I don't even know what I did. I think it's just cuz my, my access my account is so old. It has some like really weird permission on it.

[00:19:34] **Tim:** Yeah, that's super.

[00:19:36] **Ben:** But there there are, it's, it's super confusing for me as part of this ramping up on the new platform, I had to test a lambda function cuz I had made some changes to, to, to something. And in order to test the Lambda function, I had to be added to an Okta group. Okta is our single sign-on provider at work, so I had to be added to a special Okta group.

[00:19:58] **Ben:** Then I had to log in to AWS using that Okta group. And then I had to use this special Chrome plugin that like switches me over to a special testing account that is somehow only working for that Okta group. And it, I, I'm like, I just have to follow the directions, but I don't actually understand anything that I'm doing.

[00:20:16] **Ben:** Like none of it makes

[00:20:17] **Tim:** did not, I didn't understand anything you just said.

[00:20:20] **Adam:** I know what those words mean, but I don't know what you were trying to explain,

[00:20:24] **Ben:** Yo, that's the, that's like literally the thing I say at work all the time is I'll be like, I understood all the words in that sentence. I have no

[00:20:31] **Adam:** not understand the sentence. Yeah. Alright, well I guess that's, that's our tramon fails.

## [00:20:36] Book Club Update

[00:20:36] **Adam:** So let's, I guess, so we have two things we wanna talk about tonight. We're gonna do sort of like a what's on your workbench, what have you been working on lately, sort of thing. but before that, we figure it's time for another book club. we, and, and I think we.

[00:20:51] **Adam:** Here the hosts of the podcast agree with the sentiment that, Our previous book club on clean code, that's a tongue twister, was not our best work. you know, it was a little, little dry, I think, and we wanna try to do better. So here's what we were thinking. We want to, break the book down into chapters and we will, or not. I mean, the book's already in chapters. We want to read a couple of chapters, per week and discuss those chapters on the show that week. However, to make it a little more interactive, what we're thinking is, okay, so let's just say we're gonna read chapters like one through three.

[00:21:26] **Adam:** and, we record on Thursday. So let's just say like maybe Monday or Tuesday of the week that we would record that we want to have, like a get together, like a meet up with our listeners in our Discord. We'll get together, we'll talk about what was in those chapters. Maybe if we can share lessons learned or, you know, the things that, people took away from those chapters will kind of give us a little interactivity and, and we can learn from you as much as you can learn from us.

[00:21:50] **Adam:** And then, we'll, we'll take what we kind of learn from that discussion and bring it on to the show later that week. and then, you know, we'll just do that week to week to week. So we do tend to record typically two weeks in advance. So you'll be hearing those discussions two weeks after. So really, if you want to, participate in these things, I guess we should probably like, maybe even create a dedicated channel for it in our Discord.

[00:22:16] **Adam:** But that's the idea. we certainly would love to hear your feedback on the idea. We'd love to have you participate in it. the whole, like that, that's basically as far as much as we know at this point, the details of like when we would get together, how long we would get together for. In what way we wanna get together if it's just like through text chat or if we wanna do like a video chat, that's all sort of still up in the air.

[00:22:39] **Adam:** So I guess this is your invitation to join our Discord, which you can join by going to workingcode.dev/discord, and look for the Book Club channel, which I will be creating as soon as I have a moment to, to take my face away from the microphone. And, and we will figure it out there together and we hope you participate.

[00:22:59] **Adam:** So if I'm, if I understand correctly, I think we discussed a little earlier a book idea. It may or may not be the first book that we read in this format, but we talked about, the Phoenix Project, which is a book that we've discussed on the show previously, not, not really discussed, but we've mentioned on the show previously, as being a good book.

[00:23:18] **Adam:** And we've, I think most of us on the show have read it. So, but it'll be, I, I've been wanting to reread it again lately. Anyway, I think it'll be a good reminder. I think I'm at a good point in, where, where my company's multi-tenant efforts are at, where we're kind of like at this, like everything is on fire.

[00:23:35] **Adam:** We have to keep making progress, and we also have to fix the, the problems with our architecture and our systems all at the same time. That's kind of like one of the big themes throughout this book. And so like, seems like it would be a very, relevant time to reread that one. So that's what's going through my head.

[00:23:51] **Adam:** Any, any of you guys have anything you wanna add?

[00:23:54] **Ben:** No, I think that makes sense. I like the idea of breaking it up into weekly segments so that it's not a, a, a big giant review at the end. That's, you know, it's hard to remember stuff.

[00:24:06] **Adam:** yeah, exactly. And also in doing that, I think that we can keep the discussion about the chapters relatively short. We can make that like a 10, 15 minute part of every show.

[00:24:16] **Ben:** It's also less pressure on people who wanna follow along, you know, like they don't have to be done with the entire book at the same time.

[00:24:23] **Adam:** Yeah. Okay. so, what's on the work match? I mean, I've, I've mentioned a little bit earlier I've been, pretty heads down on PCI and SOC two stuff. I could give a brief update on where things are with that, but, I dunno that, that would be super interesting. Does anybody else have anything you wanna throw out there?

[00:24:38] **Tim:** Unfortunately, I'm working on pci.

[00:24:40] **Adam:** It's that time of year I.

[00:24:41] **Tim:** Yeah. Yeah. We do ours around every May. We just had our, our PIN test, which, you know, it's always fun to have a white hat hacker going after your stuff, but yeah, we, we, I mean, we passed with flying colors. We had one little minor vulnerability that wasn't even, I mean, it was like a low level, so they just passed at, they were even like, you know, good job guys.

[00:25:00] **Tim:** Well done.

[00:25:02] **Ben:** Nice. Nice.

[00:25:03] **Tim:** yeah.

## [00:25:04] Twilio DoS Attack

[00:25:04] **Ben:** Well, I know that you have talked about adventures with Twilio, recently,

[00:25:09] **Ben:** and, um, and we have an update on our Twilio adventures, which is that, as I think I've mentioned before in the

[00:25:15] **Tim:** For, for sms.

[00:25:16] **Ben:** Yeah, yeah. as I think I've mentioned this on the show, that we have someone who is just

[00:25:22] **Ben:** spamming people.

[00:25:24] **Ben:** They're two factor authentication codes, which literally has no value for them other than it's forcing us to spend money. And, it's, it's just. It's so aggressive. in the last attack, the, security engineers were following it and, and, you know, evaluating the attack vectors through, our cloud flare WAF and looking through logs and everything.

[00:25:46] **Ben:** And it was something like at one point they were signing up with like 500 unique IP addresses, like they were signing up user accounts and doing all this stuff. And it's, it's gotten to the point where like, we don't really have a great solution and our, our midterm goal is actually just to remove Twilio from the product.

[00:26:05] **Adam:** Wow.

[00:26:05] **Ben:** Like we just, we don't know what to do about it.

[00:26:08] **Adam:** So I mean, you're using Twilio to send SMS with people's two factor off codes. Are you planning on taking it out by offering a different alternative? Like email and,

[00:26:19] **Ben:** through email, which, I mean, I don't know, it seems like that opens up other vectors, but at least, at least the vectors don't cost money or that's not even true. They do cost money, but. In what it is, like people were sending SMS messages to, to like Uganda and places where, and this is something I learned as part of this whole process.

[00:26:40] **Ben:** I thought, you know, when you, when you sign up for Verizon or at and t and they're, and they're like an SMS costs, you know, a penny. I thought that was a worldwide phenomenon, like anywhere as a penny to send. Totally not true at all. In fact, sending it to some countries is stupid expensive

[00:26:57] **Tim:** Can't you block where it

[00:26:59] **Ben:** so, yes.

[00:27:00] **Ben:** So in Twilio you can go in and there's geocoding, there's like geo permissions and they list like all these, like hundreds of regions around the globe. And like, we've literally just been turning off regions after they get attacked. And it's just, it's you know what it is, like we're understaffed and, and we just wanna, like, the easier solution is just to remove SMS from the product.

[00:27:22] **Adam:** You said you're using CloudFlare. I wonder if they could do anything for you, like that's kind of their whole business, or that's their, I think that's their premier offering, right. Is they're like, you know, you're being DDOSed. Okay. We can help you with that.

[00:27:36] **Ben:** So it's crazy. These, so that, that was my thought. As someone who doesn't know that much about CloudFlare and, and, and, and I'm, the security engineers are like, they're looking into all of this stuff. these attacks are, are like really sophisticated. We've been tweaking our rate limiting and, and all kinds of logic.

[00:27:53] **Ben:** And the attackers find they're continuing to find the, the, like cadence that will fall under the bars that get tripped.

[00:28:03] **Adam:** Mm-hmm.

[00:28:03] **Ben:** And it just, I mean it's like I I it's costing them money, right? Like it's costing them money to spin up these Amazon instances, I assume, like of Amazon, I guess is so cheap.

[00:28:14] **Adam:** mean, if it's been going on this long, it's, I doubt it's Amazon, right? Somebody, somebody is, it sounds like somebody is doing this because they got a vendetta or they wanna harm you and, and they're like a competitor that want to wanna take you out. It, you know, it's whatever the Russian version of Invision is, or South Korea or North Korean,

[00:28:33] **Tim:** I mean, you did just lay off a whole bunch of people, so

[00:28:38] **Ben:** Oh man. It's just, it's just crazy.

[00:28:41] **Tim:** Yeah. That's that's weird. Yeah, I haven't thought about that. I mean, they, people can like spam your, your texting ability and just like run your rate up.

[00:28:50] **Tim:** I don't know what we do in that case.

[00:28:51] **Adam:** So are they, are they like signing up for new accounts and, and requesting two factor off through that? Or are they trying to do this for like existing accounts?

[00:28:58] **Ben:** it's, I, I believe the vector is primarily, they're signing up for new accounts, but they're doing it from hundreds of different IP addresses over periods of time. Like again, they're finding all these rate limiting ceilings, and then they're adjusting their approach to, to take advantage of the, the limit.

[00:29:19] **Ben:** It's crazy. Like it just boggles my mind that someone's figuring this

[00:29:22] **Tim:** Because, because cuz I do know that spamming people for like an authentication is, is a way to try to like, I forget what company it was, but recently a company got breached and it was because they kept spamming them with, with author request to, for a login for the V P N and eventually someone accidentally hit yes and now they got it, they got into the vpn.

[00:29:45] **Tim:** but yeah, it's a little bit different of a tag vector.

[00:29:48] **Ben:** and then, and then my question. So when we discuss these things internally, I'm always like, at what point do you get law enforcement involved? Like, and people are like, well, I don't know if any rules are being broken, or like, any laws are being broken. I'm like, I'm, I don't know. They're spending our money.

[00:30:06] **Ben:** They're spamming people. They're using, you know, this is happening over international networks. Like that's, it feels like something illegal's happening, but I'm not a, not a

[00:30:16] **Tim:** I mean, it was years ago. It's probably about 10 years ago, but the, the FBI called me and told me that, so that we were like an attack vector target that someone was, was trying to hit. And I don't know how they, we got on their radar, but they did. I'm like, okay, thank you. And then we like handled the issue That was like the vulnerability that was there, but it's like I never expected in my life I would get a call from the FBI for something that I wasn't doing illegally.

[00:30:44] **Adam:** You expect those?

[00:30:46] **Tim:** expect those. Yeah.

[00:30:48] **Adam:** That's interesting. yeah. I mean, so I have called 9 1 1, I think twice in my life.

[00:30:55] **Ben:** No.

[00:30:56] **Adam:** the first time was when my brother and I were playing football in the house I busted his head open and he was bleeding. And my, should I tell the whole story? It's not that long. my, my parents. young. I don't remember the exact ages.

[00:31:11] **Adam:** I would say probably I, I'm the oldest. I would guess I was probably like 12 or 13,

[00:31:17] **Tim:** Mm-hmm.

[00:31:18] **Adam:** you know, with plus or minus, say three years, mostly minus, my, my parents had just gotten their first cell phone because this was back in the day. and they decided they were gonna go out and they, they went to a, like a Home Depot type store.

[00:31:32] **Adam:** I don't remember the name of it, but it was, you know, they, they had a green logo, I remember that. And it was like, you know, two miles from our house, not that far. And so they leave, they leave me in charge of my brothers and we start playing football in the house, which, when I say we're playing football in the house, you know, we're lining up at the, the line of scrimmage in a doorway and like tackling each other through the doorway. And our house was basically made outta concrete.

[00:32:01] **Tim:** Mm.

[00:32:02] **Adam:** my brother and just like the, the pressure of like smacking down on the floor popped open the back of his head, the skin

[00:32:08] **Ben:** oh,

[00:32:09] **Adam:** And so he started breed bleeding profusely.

[00:32:12] **Ben:** oh.

[00:32:13] **Adam:** And we also happened to live within like a mile or so of the fire department.

[00:32:18] **Adam:** So, oh, and, and because my dad is a huge nerd as well, we had two phone lines, which was almost unheard of at the, at the time, this was, you know, early nineties maybe. and so, I told my brother, my youngest brother, cuz it was the middle brother that got hurt, I told my youngest brother to call mom and dad and tell them to come home.

[00:32:37] **Adam:** And while he was doing that on the, like, the line that the, the modem would use, I called 9 1 1 and I. My, I, my brother hit his head and he's bleeding. I need an ambulance or something. I don't know what exactly what I said. so the, you know, the, the firetrucks are coming. and my youngest brother called my parents.

[00:32:54] **Adam:** He's like, you need to come home. Justin's hurt real bad. And they're like, what happened? and, you know, he was, he had to have been like seven, something like that. He's like, Justin's head broke open and he is bleeding to death.

[00:33:07] **Ben:** Oh my God. Oh my

[00:33:10] **Adam:** was just this, it was like, you know, a one centimeter cut, right? Like, not even half an inch. maybe a little bit bigger than half an inch. But, so the paramedics come, it, it ends up not being that big of a deal, you know? I had gotten him, I laid him down on the floor. I had put like a towel under his head to, to soak up the blood and make him comfortable.

[00:33:29] **Adam:** And just in case he was going into shock, I lifted his legs and whatever

[00:33:34] **Tim:** Oh, paramedic Adam. Okay,

[00:33:36] **Adam:** Yeah, well, I was a boy scout. and, so my parents get home and of course there's already an ambulance in the driveway. And,

[00:33:42] **Tim:** Wow.

[00:33:43] **Ben:** Oh man.

[00:33:44] **Adam:** and I guess the ambulance people like, stop them on the way in and like, everything's fine. It's okay.

[00:33:49] **Adam:** So my dad comes in and he's mad because I put my brother on the carpet in the living room instead of on the linoleum in the kitchen. We were, we were like, between the kitchen and the living room, there's carpet in the living room. Linoleum in

[00:34:02] **Tim:** Do you know how hard it is to get blood outta carpet?

[00:34:05] **Adam:** Exactly. Well, you know what, pro tip, it's not peroxide.

[00:34:08] **Adam:** We'll take it right out of the carpet and, and, doesn't discolor the carpet. So there you go. There's your, your blood pro tip.

[00:34:14] **Ben:** good to

[00:34:14] **Tim:** the more you know.

[00:34:15] **Ben:** Keep that one in my back pocket.

[00:34:17] **Adam:** Yeah. how did we get on this?

[00:34:20] **Tim:** I don't

[00:34:20] **Ben:** I don't remember,

[00:34:22] **Adam:** Tim was telling a story, I think, and, and it reminded me of that. Oh man. Now I feel

[00:34:26] **Ben:** 9 1 1. I think calling law

[00:34:30] **Tim:** No. Fbi. FBI called me f, FBI called

[00:34:33] **Adam:** Yes. And the, the second time that I ever called law enforcement, or called 9 1 1, was because, I wanted to just like call the police and report people setting off fireworks at like 2:00 AM on New Year's Eve when it was like, you know, Monday night and my tri my baby is crying and, you know, whatever.

[00:34:49] **Adam:** And like, I, I, I spent like half an hour trying to find the number for the local police on their website and stuff, and I just, I couldn't find anything where anybody would answer. And finally I was just like so fed up. I called 9 1 1. I said, look, I'm just calling about noise. I'm sorry. I don't ha, I don't have anywhere else to call.

[00:35:05] **Adam:** I tried the number. It didn't work, whatever. So they're like, no, it's fine. You can call us for that. And, yeah, so I, I do all that to say I don't think that the FBI will be that upset with you if you call and say, I'm not sure if we're supposed to reach out to you yet or not, but here's what's going on.

[00:35:23] **Ben:** No.

[00:35:23] **Tim:** is, is is running up our SMS bill.

[00:35:28] **Ben:** Oh man.

[00:35:29] **Adam:** So, I mean, yeah.

## [00:35:30] SMS Regulations

[00:35:30] **Adam:** Does anybody have any, Twilio slash SMS updates on, on, the new regs that are coming down and,

[00:35:37] **Tim:** I mean, so ba basically what I've done is I've converted all of our long code numbers, which are the local numbers, to tollfree numbers, and that's just kind of handled it.

[00:35:48] **Adam:** Hmm.

[00:35:48] **Tim:** So, so you, you cover 'em, those, and then you, so when you convert, when you use a 800 number, because even if it's unregistered, they do allow, I forget the numbers.

[00:35:57] **Tim:** I, I posted it to someone on Discord or Discord channel. But, once you register it, and it's not, honestly, I don't think they even check the registration because they, they wanna know like, what are you using it for? are you doing, is this for advert unsolicited a advertising, which is, ours is not, you know,

[00:36:16] **Adam:** Isn't that illegal? Like,

[00:36:20] **Tim:** I mean, that's what, that that's what

[00:36:21] **Adam:** called spam.

[00:36:22] **Adam:** yeah. That's what they're trying to stop. Right? So who's gonna answer? Yes.

[00:36:26] **Tim:** right. Exactly. Who's gonna answer yes. And then they want, they like, they wanna see your privacy policy and different things on your website. And it's like, I'm doing this on behalf of my customers.

[00:36:37] **Tim:** And some of my customers don't have a privacy policy and I ask them to put one up for this reason. And they, they say they, they never do it cuz they're lazy. and so I just put like a random page on their website, the About us,

[00:36:51] **Adam:** Here's a summary

[00:36:52] **Tim:** Yeah. Which, yeah, we've been in business for 150 years and blah, blah, blah.

[00:36:56] **Tim:** And we sell insurance and, and they've all gone through, I don't, I don't think they even check. I honestly don't think they even check. But yeah. So you, you fill out this form and you submit it. Basically I give like the, the, the body of the general texts that we're sending. So, cuz I guess they do some pattern matching when the texts go through.

[00:37:15] **Tim:** But even then, now that we're registered and verified, they still block some stuff as spam and I don't know, I have no way of knowing what they're filtered out. It's a super small, portion of the texts that we send out, but they'll block some of 'em as spam. So, so what I do is I just, I log the callback.

[00:37:32] **Tim:** So we, you know, the, we use, Plivo for our, for sms and Plivo has a callback function. It calls backer. And so I log that and say, okay, this text got blocked for spam. I just resend it like two hours later and it goes through. So, because some of these texts aren't like immediate, it's not like, of them aren't. Trying to log into something. It's just like we're sending you a copy of your receipt or just to notify you that your policy's, you know, expiring or canceled or whatever and urging you to pay. So, yeah, the second time I sent it through, it goes through, so,

[00:38:04] **Tim:** but it costs me to send it twice. Even, even, it's not even, it's not delivered. It cost me. So that's what I'm doing. I'm just making everything toll free numbers.

[00:38:12] **Adam:** Yeah. So you said a, a long code. Is that just like a 10 digit phone number? A random, okay.

[00:38:17] **Tim:** a local 10 digit, and then you have short codes, but like short codes are stupid expensive. I mean, they're, I mean, tens of thousands of dollars.

[00:38:25] **Adam:** honestly, I believe that, telecom companies, phone companies are just gonna continue to come up with these features that they can charge you for because they're new, right? Like when texting came out, it was like 25 cents per received and 25 cents per cent text message. Yeah.

[00:38:43] **Tim:** I, I remember. So I mean, a lot of our listeners would know Char, Charlie Earhart early in the days of texting, he didn't have texting on his phone. So if, if you, well, he did have it, it just cost him, he didn't pay for it. And so if you sent him a text, I got like this long email, like everything from Charlie is long, uh, whatever he, when he retypes a

[00:39:03] **Adam:** it's, it's the thing with his keyboard, it won't allow him to send a short email.

[00:39:07] **Tim:** yeah, yeah. He, that's why he doesn't tweet. So I got this long email because I texted him a message. I was trying to get in touch on him. He wasn't responding. So I like sent him a message and he sent me this long email explaining why it's important that I not text him because he doesn't, cuz he gets charged for it.

[00:39:23] **Tim:** And I'm like, Jesus dude, just pay for the texting. It's the few of the future your computer programming, old man.

[00:39:31] **Ben:** Oh man.

[00:39:32] **Tim:** But what's funny is you could still, so there is an E, you could send text through email. And I do, I do this for like just some like alert services I wrote years ago and I haven't bothered to change 'em, which costs

[00:39:43] **Adam:** Mm-hmm.

[00:39:44] **Ben:** I

[00:39:44] **Ben:** played around with that years ago.

[00:39:46] **Tim:** yeah, you can do the phone number and then like at, you know, Verizon

[00:39:51] **Tim:** something.

[00:39:52] **Tim:** Yeah,

[00:39:52] **Tim:** verizon net. And it's some sort of, and, and it's like, I don't know, and you can only send it to people on those

[00:39:57] **Adam:** Mm-hmm.

[00:39:58] **Tim:** but it's like, I just have a cf, you know, I just send it to all of them.

[00:40:01] **Tim:** I don't, I don't know what network they're

[00:40:03] **Tim:** on. Yeah. I just send it to all of 'em and it's like cost nothing.

[00:40:06] **Tim:** And they haven't stopped that, so I don't know what's going on with that.

## [00:40:11] SMS, Voice and Email

[00:40:11] **Ben:** You know, one of the podcasts I listen to is how I built this, and they have a couple of flavors, like some is like wisdom from the top. There's a couple different versions of that show, but one of the most recent ones was an interview with the guy who founded Twilio. And on the show, the guy was asking him, he's like, this is, it's crazy that it took a third party to come up with this system.

[00:40:31] **Ben:** Like, why is at and t and Verizon not creating APIs to allow you to send text messages? And it just, it's just interesting the scale of business. So the guy who found a Twilio was like, well, they absolutely did, but they ran them for a year. And then they look at their bottom line and they're like, you know, we make whatever, tens of billions of dollars from voice, and we make almost nothing from providing these APIs to developers, so we're just gonna stop doing that because it really doesn't make us any money.

[00:41:02] **Ben:** But to a startup like Twilio, they're making all of their money from SMS messaging and voice messaging, so it, it makes sense for them, but it is crazy like the opportunity that they didn't do just because they make so much money doing other things.

[00:41:16] **Tim:** Yeah. that's, I, I was thinking about this the other day. Like, I, I think that really big companies, of course, you know who, what do I know? I'm just, you know, a small business operator, but I, I think really big companies shouldn't start, like internal initiatives. They should like fund a startup that they own majority in, right?

[00:41:34] **Tim:** And then if it fails, just kill it. But I mean, yeah, there's a lot more init, there's a lot more desire and drive. If you have a, a bunch of people that are in a startup, they're being funded by a big company. Big company's like, okay, we'll see if it, what happens, we'll experiment. And then if it works, you know, it can still be its own company.

[00:41:54] **Tim:** If it gets really big, we'll buy it. I just merge it, you know, back into us. But I don't know why they do, don't do that because there's so much. Nimbleness with a small company versus like a giant behemoth. You can't turn that big ship

[00:42:09] **Ben:** well I, another podcast that I was listening to and I can't remember which one it was, unfortunately. But this guy was, it wasn't a scathing review, but it was like a pointed review about Google and he was saying if you look at, at them over the last 25 years, he's like, they've basically made one product, which is an advertising system and every other product that they have is either slightly reinventing an existing product like Gmail or buying another product.

[00:42:38] **Ben:** And they talked about like Google Analytics and Google Docs and all of that stuff. These were all companies that were purchased?

[00:42:44] **Adam:** chat platform.

[00:42:46] **Tim:** Yeah.

[00:42:46] **Tim:** Voice. I still don't know how Google Voice makes money. I mean, how do you give away free phone calls from the

[00:42:52] **Ben:** Is that still a thing? I didn't even know that was a

[00:42:54] **Adam:** Yeah, I never used it for

[00:42:55] **Tim:** I, I use it all the time. I have like two different voice.

[00:43:00] **Ben:** I know that there were people who were using it cuz they could, it, it had like automatic number forwarding I think. So you could, you could have your Google number, which was not your personal number, but it would just turn around and call your.

[00:43:11] **Adam:** Yep. My wife has a therapist and she gives that Google Voice number to her clients if they need to text her or call her or whatever. And that way she can just like turn it off when she's on vacation or stuff like that.

[00:43:23] **Tim:** Yeah, I do the same. All of our customer service people use a Google Voice number, so that way they don't have to give out their cell phone number at home. I, I don't know how they make money off that. Obviously it costs 'em something to do

[00:43:34] **Tim:**

[00:43:34] **Ben:** yeah, I, I think everything for Google is like, how do we drive more people to search and more people into viewing AdWord? Or ad whatever ads they're doing, if they can find, like, if there's like one way where like half a percent of people who use Google Voice are looking at ads occasionally, that probably makes them enough money to cover the cost. So like there's so much good that has come out of Google building better versions of everything. Like, I, I can't imagine going back to a world without Gmail, right? Like if I had to go back to Yahoo Mail or Hotmail. Yeah. And like, oh my God, I, I've never said this to their faces, but I judge all of my friends that have Yahoo Mail and Hotmail accounts, and, and let's be real, even if your email domain is@likeoutlook.com, still judging you, but uh,I always

[00:44:33] **Tim:** the the real ballers are the people that have like their own personalized name domain as.

[00:44:39] **Adam:** I did that for a long time and I just hooked it up to Gmail back when that was free. I still have that one, but I don't like that domain anymore, so I'm kind of screwed.

[00:44:48] **Ben:** Well, I always thought it was funny when people had email addresses that were tied to their ISPs, so they'd have like, so and so@cox.net or, I mean, I'm not

[00:44:58] **Tim:** my, my, my

[00:44:59] **Ben:** I'm just Yeah, Yeah,

[00:45:01] **Adam:** SBC Global Comcast.

[00:45:03] **Ben:** yeah.

[00:45:03] **Tim:** aol.com. We're aging ourselves.

[00:45:08] **Ben:** It's

[00:45:08] **Tim:** Yeah. Yeah. I pay, I pay, I pay the $4 a month. My son has, me@maxwellcunningham.com. I'm like, you know what,

[00:45:15] **Adam:** So what, what service are you using for that?

[00:45:17] **Tim:** Gmail?

[00:45:18] **Adam:** Okay, so you're just paying for

[00:45:20] **Tim:** Yeah. Just

[00:45:20] **Adam:** Suite for, is it you pay by the

[00:45:22] **Adam:** user or something?

[00:45:23] **Adam:** Yeah.

[00:45:24] **Tim:** So,

## [00:45:25] Subjectivity in Programming

[00:45:25] **Ben:** I, I wanna, I wanna throw a question out here to the peanut gallery. when, when we had Nolan I, on the show, it, I think it underscored at the very end there how subjective music tastes are. I dunno if this was part of the show or part of the after show.

[00:45:40] **Ben:** It was the after

[00:45:41] **Ben:** show. So for those who

[00:45:42] **Adam:** still wrong for not liking the Beatles. Ben

[00:45:43] **Ben:** Yeah. I said The Beatles are not my cup of tea.

[00:45:48] **Adam:** you said they're trash

[00:45:49] **Ben:** And, and that's obviously an opinion that varies from, I'd say a lot of people. but music I think is very, very subjective. I remember there was a time where on my Pandora. Without fail a music, a musical selection would come on. And I would think to myself, this is absolutely awful.

[00:46:10] **Ben:** Who is this? And I would flip to it, and I swear it nine times out of 10, it was Tori Amos. And again, nothing against Tori Amos, but like, whatever, it sounds like, nails on a chalkboard to me. But there are people who love Tori Ames. That's not the point. The point is music is super subjective. And I started to think about that and I started to think about how many things in this world are super subjective, like food tastes.

[00:46:31] **Ben:** Obviously Tim likes the cat, the, the Carolina Reapers, and I think

[00:46:36] **Tim:** Mm-hmm.

[00:46:37] **Ben:** like some spicy tests and and I don't, and or, or like movie preferences, right? I love a good action movie. If I can go into an action movie and turn my brain off, I'm a happy man. my wife could not care less about action movies.

[00:46:51] **Ben:** And, and I think there are these genres of experience. That are totally subjective. And as a society, I think we're very okay with them being totally subjective, right? It's okay that someone likes heavy metal. I don't get it, but like, I'm not against them liking heavy metal. I'm bringing this to a point. my point is, yeah, so my point is programming.

[00:47:15] **Ben:** I, I think there's this sense for a lot of people in the programming world that, that, like, not that, there's nothing subjective about programming, but there's this like, weird guilt or like close-mindedness that if I don't find something enjoyable either it's, I'm just not familiar with it.

[00:47:34] **Ben:** So I'm pushing it away because I'm not familiar with it and like, oh, I only wanna know stuff that I already know. But I, I, I think that there is just genuinely certain things that excite people about certain types of programming and certain types of languages and certain types of databases, And And I feel like n I feel like now as an adult, that like, that's just okay.

[00:47:59] **Ben:** And I, and like I don't wanna feel guilty about that. I don't wanna make other people feel guilty about that. And I don't know, I guess I'm just asking like what y'all think.

[00:48:08] **Tim:** Sounds like you're asking

[00:48:08] **Tim:** for

[00:48:09] **Adam:** Can you

[00:48:09] **Adam:** gimme an

[00:48:10] **Adam:** example?

[00:48:11] **Ben:** Well, like, take for example the like list languages, lisp, like closure. I, I don't, I don't really know anything about Lisp, but I, I had to, I took, yeah, it's, it's just like a series of parenthesis and, I took a class in college and like, it's just not for me. I don't think I, I could do it at the time, like I could do little programs in Lisp, but it was, it's just like my brain didn't work that way.

[00:48:35] **Ben:** And

[00:48:36] **Tim:** it

[00:48:36] **Tim:** didn't have tag islands.

[00:48:37] **Ben:** the same, it's the same with functional programming. Like I, granted I'm not great at functional programming, so there is a, a knowledge gap for sure. But I look at the way people write functional programming, and it's like, it's just not the way that my brain works. And you talk to people who really love functional programming and they're like, oh my God, it makes the code so much easier to read.

[00:48:59] **Ben:** And it's like, so atomic and all these great things about it. And I look at it, I'm like, this is, this is awful. Like I just, I, I look at it and like my brain glazes over, but then I'll look at something like very procedural code and I'm like, oh my God, that procedural code's so easy to reason about. It's amazing.

[00:49:16] **Ben:** And then someone else will look at and be like, oh, how do you even manage this? It's so outta control and disgusting and ugly. And

[00:49:21] **Adam:** Yeah.

[00:49:22] **Tim:** I think a lot of that's just experience,

[00:49:24] **Tim:** right?

[00:49:25] **Ben:** see that's, that's what I have, that's what I have internalized. But I, I don't think that's true.

[00:49:31] **Adam:** Okay. Here's, here's another angle on it. I think that it is possible to do anything poorly.

[00:49:36] **Ben:** Yes,

[00:49:37] **Adam:** Okay. Whether we're talking about cooking or making movies or writing code. And so you can write terrible, hard to read poor performing, ugly, functional code, just like you can write terrible, hard to read, poor performing, ugly procedural code.

[00:49:56] **Adam:** And so it's tough to judge a, a, is it a style or genre, whatever, of like code by the code that you've been exposed to. Right. For me, I like functional programming, but the things that I like about it are the, the way that it can compose things together, right? So like you've got these concepts of like, map and reduce and whatever, all of those things.

[00:50:24] **Adam:** And they're so, they're patterns and then you can write things, okay, this is something I can pass to a reducer and it does this thing, right? It sums and you give it a column or whatever, right? and it, it can be very composable that way, right? You can, you can write a, a series of different functions that can be used as like, sort of like a plug-in ecosystem sort of thing.

[00:50:43] **Adam:** but it, you can absolutely write trash functional programming code as well. And I think that, I don't wanna throw anybody under the bus, but I've, I've certainly seen more than my fair share of trash FP code as well.

[00:50:56] **Tim:** Yeah.

[00:50:56] **Adam:** And I've written my fair share of Trash FP code to be, perfectly honest.

[00:51:01] **Tim:** And, and, and I think, so you're talking about from a developer experience, right? So I mean, honestly, my take is that software is meant to be used by the people that are using it. The, the actual end user, the customer. They don't care about your experience in writing the code. They have ab absolutely no idea about your ethos, your, your artistic ability, what the code looks like at the end of the day.

[00:51:28] **Tim:** Does it work? Does it work well? And when it's broken, does it get, get fixed quickly? And if, if you can tick all those boxes, what does it matter? Right?

[00:51:39] **Ben:** Well, but, but look, I think that's, I think we're, that's two different conversations. I'm, I'm specifically asking about the developer experience. Like, so, you know, we, we, the canonical example, of course is to argue about spaces versus tabs, and we've talked about all the reasons that tabs are actually technically more accessible.

[00:51:58] **Ben:** And so that's kind of a moot argument at this point, I think. But like, there are people who literally like two spaces for indentation, like they've chose that they started a new project. They said, I know all the options that exist. And I've decided to use two spaces to end in, which to me

[00:52:14] **Ben:** is like the

[00:52:15] **Adam:** just wanna see the world burn,

[00:52:16] **Ben:** Right.

[00:52:17] **Ben:** But like,

[00:52:18] **Ben:** they like that they, they wanted that. And I don't think that there's,

[00:52:23] **Tim:** Yeah, and some people like to write tests.

[00:52:25] **Ben:** well, but,

[00:52:27] **Adam:** Crazy people.

[00:52:28] **Ben:** I guess wrong, I'm saying

[00:52:29] **Adam:** Some people wear sunglasses.

[00:52:32] **Ben:** it's o I guess it's o I wanna say that, I guess it's okay. I that I guess it's okay that, that they like two spaces. I don't get it. But I wanna, I, I like, I, I wanna start living in a world where it's okay for someone to like two spaces.

[00:52:46] **Ben:** As long as it's okay for me to like tabs and to

[00:52:49] **Ben:** not.

[00:52:49] **Tim:** But listen, listen, listen guys, 10 years from now, AI will be writing all the code for us, so we won't really have jobs.

[00:52:58] **Adam:** We weren't gonna talk about ai, AI tonight. That was off the

[00:53:00] **Tim:** Oh, sorry, sorry, sorry, sorry.

[00:53:03] **Adam:** I, I, I see where you're going, Ben. Something you were thinking I was thinking about. I, I don't, I don't know if you were thinking about this. something I was thinking about while you were kind of broaching this topic was that, there was this like, period sort of, you know, I'm, I've been working professionally in web development for about 20 years now, and I think roughly halfway through my career I started feeling very strongly like this is an art, right?

[00:53:27] **Adam:** This is a creative process. And I think I felt that way because it was only then really occurring to me like before then I was just like, okay, you know, I, I'm given a, a requirement and I find a way to make the machine do that. And I, and I do the thing, and I'm not even talking about a visual thing like, yes, css, and I've gotten better at that over the years, but I'm still thinking like, okay, maybe it's because I've gotten to the point now where like, I'm, I'm not given, add these seven things to the list of check boxes.

[00:53:56] **Adam:** I'm, I'm given, here's a thing that we need to happen. Figure it out. Right? And it's like, it's a very open-ended, you know, here's your budget, here's, here's how much time you can use and go. And, and that is a very, it's, it's a strange thing to think about it as a creative process because at the end of the day, we're typing on a keyboard, right?

[00:54:17] **Adam:** And I guess like, okay, a poet, it also can type on a keyboard, but it doesn't feel like the same thing. Unless you're really kind of thinking about like the process that you go through to get there. And that was sort of an awakening for me. And so I agree. I think that there is a very subjective, creative way to take on this kind of work.

[00:54:42] **Tim:** And it's funny you say that cuz I had a customer probably like nine years ago, tell me that. And I never thought of it that way. So he, he was a business owner lawyer, very analytical thinker and hi. In his, in his mind he thought like, programmers were like these people that just took, you know, these little digital boxes and, and drew circuits together and, you know, there was a very linear kind of way to build things.

[00:55:09] **Tim:** And, and then as you know, we dealt with him for many years. He eventually was like, he's like, I finally realized that. So you guys are more. I thought you guys were really just kind of very logical thinkers, but you're really more creative types. And I was like, yeah, we are, we're, we're creating something out of nothing there.

[00:55:29] **Tim:** There's, when you start with that idea, there's nothing, there's no, and you, so you build it, you, you kind of massage it, you work with it, you refactor it, you, you know, you iterate it and then the thing's

[00:55:41] **Adam:** Right? You, you, you produce a baby and that baby has to be secure and performant and usable and accessible and yeah, just like.

[00:55:52] **Ben:** Well, so talk about producing babies for a second, and that made me think of something, which is every

[00:55:57] **Ben:** now and then,

[00:55:58] **Tim:** made, I made two.

[00:56:00] **Ben:** Good on you, sir. Every now and then

[00:56:03] **Ben:** you'll hear these. You'll hear

[00:56:05] **Adam:** but to

[00:56:05] **Tim:** Not my babies. You better not have.

[00:56:10] **Ben:** So every now and then you'll, you'll hear in these interviews stories where someone will be like, oh yeah, I was in medical school training to become a doctor and in my third year I just couldn't stand it anymore. And I dropped out of medical school and now I do woodworking for a living, and I can't imagine being happier.

[00:56:28] **Ben:** And you, you hear stories like that and you're like, oh, wow, this person found something that they're really excited about and like, how lucky are they? And, and then if you took that same idea and someone said, oh, you know, I was writing Ruby on Rails for years, and then I switched to ColdFusion and like suddenly everything made sense and I was so happy.

[00:56:49] **Ben:** You know, like people could

[00:56:50] **Ben:** hear.

[00:56:51] **Tim:** That's, that's that. That's fan, that's fanfic.

[00:56:54] **Ben:** But like people would hear that story and I think there are people in this world who would hear that story and be like, that doesn't make any sense. Like, it's just, it's just the programming language. Like, it, it shouldn't matter. But you could look at seven at at, at a surgeon who switches to woodwork and it be like, that doesn't make any sense.

[00:57:07] **Ben:** Like you're just doing stuff with your hands, like why would one be more satisfying than the other? But I think that there is just something intrinsic to the way people experience the world, that you just, you can't, you can't take the subjective nature out of it. And I think that there's a lot in programming that that adheres to that.

[00:57:28] **Ben:** And I think, I think we are often not open-minded enough about that.

[00:57:33] **Tim:** Ben, Ben, you missed your calls. A philosopher. I mean, you really, you really have,

[00:57:39] **Tim:** honestly,

[00:57:39] **Ben:** Love.

[00:57:41] **Tim:** you're like, you're like the Plato of ColdFusion.

[00:57:45] **Ben:** I mean, ColdFusion is just great. ColdFusion was not my first program in language. It's

[00:57:51] **Ben:** just,

[00:57:52] **Ben:** I think I, I did a s p classic

[00:57:55] **Adam:** did you ever do anything that was pre-web?

[00:57:58] **Ben:** I did Q basic. Q basic was kind of fun actually. That was the Q basic, I think was the first language I really tried. I think I did like QBasic and then asp, and then some php and then some asp.net.

[00:58:13] **Ben:** And then ColdFusion

[00:58:14] **Tim:** Yeah, I did. basic apple basic fork. Tran, pearl,

[00:58:20] **Tim:** and then as P Assp, A A A A S P classic. And then ColdFusion. Yeah,

[00:58:27] **Adam:** Do I have to do mine now? Is that what we're doing?

[00:58:30] **Ben:** do

[00:58:30] **Tim:** so.

[00:58:31] **Adam:** I started out by making screensavers with Visual Basic,

[00:58:35] **Ben:** Heck yeah.

[00:58:36] **Adam:** and then I got my family kicked off of AOL a bunch of times. We talked about this,

[00:58:42] **Adam:** uh,

[00:58:42] **Tim:** you did.

[00:58:45] **Ben:** You're like, yada, yada, yada. I'm not allowing certain states.

[00:58:48] **Adam:** Yeah. yeah, ColdFusion was my first web language, I guess. Well, so I did, Pearl via cgi, I guess is how you would explain that.

[00:59:00] **Tim:** Yeah. Yeah.

[00:59:01] **Tim:** and then, then ColdFusion. I dabbled very briefly with P H P after I had been exposed to ColdFusion because it was free. And I was like, well, I wanna do this in my free time, but I'm not buying a license. So, Yeah.

[00:59:12] **Ben:** I think I tried Python briefly for like three days, and I, the white space, like

[00:59:19] **Ben:** the, the, the white space just didn't jive with me.

[00:59:22] **Adam:** yep. Two spaces.

[00:59:24] **Ben:** can't do it.

[00:59:25] **Tim:** I cannot work this way.

[00:59:28] **Adam:** All right. All right. All right. Let's kill it

[00:59:30] **Ben:** Yeah, yeah, yeah. Done.

## [00:59:31] Patreon

[00:59:31] **Adam:** So this episode, Working Code is brought to you by brain surgery by woodworkers. I've got a chisel and I will take your money and listeners like you, if you are enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:59:46] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks. Go out to our top patrons, Monte and Giancarlo. You guys rock. We really appreciate your long time and continued support. and you know what, just as a blanket also, thank you to all of our patrons at every level.

[01:00:05] **Adam:** Having you all on board makes us a super stable, thing. Oh crap. We have a new patron. I, I know. I like to, say thank you when you join up and I, I, saw you this week. let's see. You are Adrian. Adrian Breman. Thank you for joining. happy to have you. Welcome to the Party Pal. And uhoh, you did it wrong.

[01:00:27] **Adam:** You're fired. Anyway, where, where was I? After Show, all of our patrons get access to our after show and they get early access to all of our episodes. We record on Thursdays. You usually patrons have that episode in their podcast app on Monday, the following after our recording, and then it goes out to public like two weeks, just a day shy of two weeks after we record.

[01:00:52] **Adam:** So if you wanna get early access, and our after show, then you should support us on Patreon. and you can do that for as little as $4 a month and actually cheaper if you sign up for a whole year at once. what did I say? Oh yeah, patreon.com/WorkingCodePod, in case I didn't already say that.

## [01:01:08] Thanks For Listening!

[01:01:08] **Adam:** hallmark this week.

[01:01:09] **Adam:** I'm just gonna throw this out there. Again, we're talking about the Book Club. It's something that we really wanna do again soon. join our Discord, look for the book Club channel and help us get this thing started. So you can go to workingcode.dev/discord to do that. That's gonna do it for us this week.

[01:01:24] **Adam:** We'll catch you next week. And until then

[01:01:27] **Tim:** Remember, your heart matters. You beautiful subjective code artists
