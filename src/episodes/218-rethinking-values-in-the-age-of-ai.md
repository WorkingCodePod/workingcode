---
title: "218: Rethinking Values in the Age of AI"
description: "In this week's episode, the crew is back to discuss and question quickly shifting values in the world and their implications for developers."
date: 2025-05-29
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/218-rethinking-values-in-the-age-of-ai/id1544142288?i=1000710410594"></iframe>

In this week's episode, the crew is back to discuss and question quickly shifting values in the world and their implications for developers. Will AI erode the importance of code craftsmanship? When old values are quickly discarded, what does that say about the legitimacy of the new values? Is human coding obsolescence the elephant in the room?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/218-rethinking-values-in-the-age-of-ai.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** You've got your package js on everything. You run NPM install and you're good to go. And then you write the, the application code. That's, that's the way it should be, right? Like framework getting outta your way. The framework should install itself more or less, I think. Yeah.

[00:00:13] **Ben:** Yeah, there's definitely code that I've never written on my own before.

[00:00:17] **Tim:** Tests.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 218. And on today's show we are going to not play a game, but we're still going to talk about two truths and some value. but first, as usual, we are, gonna start with our transman fails. We've got the whole crew back on site, uh,

[00:00:53] **Carol:** Hey,

[00:00:54] **Ben:** Yoyo,

[00:00:55] **Adam:** in their own sights as usual.

[00:00:57] **Adam:** everybody's here, so, let's get it kicked off. Ben, what do you got going on? My friend

## [00:01:02] Ben's Failure

[00:01:02] **Ben:** I am going to start the show off here with a light failure, which is that I have never been a habitual user of the kind of social sharing sites like Reddit

[00:01:13] **Adam:** that's called a

[00:01:14] **Ben:** News. Yeah, I mean, I've kind of viewed it as a, as a failure over, I mean, as a triumph over the years. But, so I've been digging into HTMX, which is a front end framework.

[00:01:26] **Adam:** don't say

[00:01:26] **Ben:** I say, I say, and there's actually a fairly um,well trafficked HTMX subreddit. Is that the, is that the terminology?

[00:01:37] **Carol:** are correct

[00:01:37] **Ben:** So I've been, I've been just kind of lightly watching this threads come through and reading them to see what people, what kind of issues people are running into. And I've been grappling with some sort of philosophical questions about HTMX.

[00:01:51] **Ben:** So I thought to myself, maybe this is the moment that I actually come in and try to participate on this site. And just,

[00:02:04] **Carol:** inside jokes.

[00:02:08] **Adam:** we're talking about. Reddit. I just, you know, the, the thing about Reddit is. If there's more than one person that is into something, then there will be, sorry, I have a, a beard hair in my mouth. If there's more than one person that's into something, there will be a, a subreddit for it. Don't open the one that I,

[00:02:23] **Ben:** Yeah.

[00:02:24] **Adam:** I posted the maybe disconnect from your work VPN before you open that one.

[00:02:29] **Adam:** yeah, they just have ridiculous names and, and of course, you know, it leans way hard into porn is available if you want it. But,yeah, so I, I posted the, one of the most ridiculous subreddits that I,

[00:02:38] **Ben:** That's funny. Okay, so I find these things through Google, so I don't know what the full landscape of Reddit is. Anyway, so I thought, okay, maybe what I should do is I should log in 'cause I have an account, but I've, I've barely ever used it. I'll log in, I'll post this question, see what happens. So I do that.

[00:02:54] **Ben:** I, I, I think I post a very nice question. It's, it's, well thought through and I think well articulated and some people start commenting, and I'm commenting back and I feel like we're having some nice back and forth. And then, all of a sudden my, all of my comments have been deleted by a moderator and my account has been locked

[00:03:13] **Adam:** So when you say, all of a sudden, was this like in the middle of conversation, you're kind of like going back and forth over the course of a couple of hours or is this like you woke up the next

[00:03:19] **Ben:** is, no, no, this was within the span of a single day.I went back and forth. I probably left about,

[00:03:25] **Adam:** must have left some really nasty comments.

[00:03:27] **Ben:** I, I literally cannot, for the life of me, imagine what the heck happened. and I don't know. And so now I'm, I'm done. I don't care anymore. I, like, I was, I was dipping my toe into the Reddit pool, just out of curiosity to see if there was some value to be extracted.

[00:03:42] **Ben:** And, apparently the answer is a resounding no. There's,

[00:03:45] **Adam:** a theory,

[00:03:47] **Ben:** yeah, go for

[00:03:47] **Adam:** I think that now that, stack overflow is kind of like losing steam and I'll just go ahead and say shutting down. I don't know what the actual goings on over there is, but you know, it, it, it, it's definitely petering out,because of Chat GPT and the, the, the way people are finding answers to think to their questions now.

[00:04:03] **Adam:** But I think because of that, all the jerk hole moderators have had to find somewhere else to go and be a jerk hole. And so now they're all moderating everything on Reddit. That's my theory.

[00:04:14] **Ben:** Oh wow. It was very frustrating. especially 'cause I don't even know if the threads were going anywhere. It, it was one of those kinds of conversations. I'm, I'm sure we've all had some flavor of this experience where you post a question that's really about one thing and then a whole bunch of people respond with a thing that is not about your question at all.

[00:04:33] **Ben:** You know, it'd be like, how do I do this thing and Svelte, and everybody responds with, why aren't you just using React? And you're like, well

[00:04:39] **Adam:** You don't really JQuery.

[00:04:40] **Ben:** yeah. Like, that was literally not my question. it was, there was some of that going on, so it probably wasn't gonna be hugely fruitful, but it was more just a, a failure of social interaction.

[00:04:50] **Tim:** Did you, did you resurrect a thread that was five years old?

[00:04:53] **Ben:** No, I started a new thread. I was so excited.

[00:04:56] **Adam:** threat necromancy.

[00:04:58] **Ben:** So anyway, that's

[00:04:59] **Carol:** here, here's the thing with Reddit, if you wanna keep your account active, you have to post pictures of your boobs like every six months. And then they never delete you. They never delete you. If you do that, that's the secret. You stay active, you can't get deleted.

[00:05:13] **Ben:** See now I gotta just sign up with a new account.

[00:05:15] **Carol:** Yep.

[00:05:17] **Ben:** So anyway, that's me. Carol, what do you got going on?

## [00:05:21] Carol's Failure

[00:05:21] **Carol:** Oh man, I'm gonna go to failure too. I'm just, I feel like I've got like the summer blues or something. Like every year, summer rolls around, I kind of get a little excited, right? Like, we plan something with the kids or there's things going on, but this is like the big year of no kids, no moving, just home.

[00:05:38] **Carol:** Life's been crazy, work's, been crazier, and I feel just, I feel a little lost, not super motivated to do anything other than that, that is absolutely required of me. yeah, just struggling a bit. I,

[00:05:51] **Adam:** I mean, there is a tornado blowing through your org chart right now.

[00:05:55] **Carol:** yeah, it's very demotivating, right? Like to go from a massive team supporting everything to just a few people, trying to just maintain our applications and continue to like, provide value for the government, like. We're not going away. We're gonna keep being here. What we do is, is a key application. So it's just, it's sad to see everyone kind of being kicked out of it, but I really hope that I can conquer some of these things at work and get through some of the personal stuff going on and get back in my groove again.

[00:06:30] **Carol:** 'cause I'm getting tired of just waking up, working, going to bed, you know, like I need to have something more than just this right now.

[00:06:39] **Adam:** Carol needs a new groove. Somebody quick turn her into a llama.

[00:06:42] **Carol:** I know. And even golf, like we're playing golf and even then, like golf is great, but when it's done, I'm like, Ugh, here we go. Back to it again.

[00:06:49] **Adam:** Yeah.

[00:06:50] **Ben:** Are you

[00:06:51] **Adam:** real world.

[00:06:51] **Carol:** Mm-hmm.

[00:06:51] **Ben:** golf or

[00:06:52] **Carol:** Golf, golf,

[00:06:54] **Ben:** Oh,

[00:06:54] **Tim:** He doesn't pronounce the L.

[00:06:56] **Carol:** golf,

[00:06:56] **Ben:** No, no. I didn't know if this was some

[00:06:58] **Carol:** golf.

[00:06:59] **Ben:** fun sport I hadn't heard of.

[00:07:02] **Carol:** Well, it's fun watching me play.

[00:07:04] **Adam:** regional

[00:07:05] **Carol:** Not very good.

[00:07:08] **Ben:** Well, that's a, that, that I, I hate that feeling. I know that feeling. Waking up and just not feeling motivated or, I, I was going through a period where I was just, I would wake up and just have a sense of dread, like just a amorphous, non-specific sense of dread and, and it was awful. So I,

[00:07:24] **Adam:** What you guys are describing just sounds like depression to me.

[00:07:27] **Ben:** yeah,

[00:07:27] **Carol:** is

[00:07:28] **Tim:** It's, it sounds like life Post COVID. You talk about golf, Carol, my, my dad, who's? Rather clean, straight-laced guy. I always had to, he enjoyed his, his dad enjoyed golf and he played, my dad played a bit of golf, but he said, golf is like sex. You don't have to be good at it to enjoy it.

[00:07:48] **Carol:** after enough beers. Everyone's good at it, or at least you think you are. Yeah. So that's me. I'll get back to it. But then what about you, Tim? What do you got going on? Bring us in on the win.

## [00:07:59] Tim's Triumph

[00:07:59] **Tim:** I, I'm bring, I'm gonna turn this thing around, come with a triumph. so our PCI is mostly done and it, it, you know, there's a few new things I, I'm pretty sure Adam knows about the, the

[00:08:09] **Adam:** 4.1

[00:08:10] **Tim:** Yeah, the 4.1 stuff, which is kind of a pain in the butt to, to deal with. I don't know how we're gonna accomplish some of the things that they're trying to do.

[00:08:19] **Adam:** Well, you guys are a service provider, right?

[00:08:21] **Tim:** yeah, we're, yeah, we're a service. A lot of this stuff, fortunately is on the, like, so our. Customers take what we give them and then they stick it in their system. There's a whole bunch of rules about how they implement that so that, you know, they, I have no control over what they put on their page.

[00:08:39] **Tim:** Right. So most of it's that, but there are some things that we have to do as a, as a service provider that it's just, yeah, I, I gotta figure out how we're gonna do that. But, you know, it's, it's funny, the, the auditors are, he is like, yeah, I don't, I don't, this just went active in April and I don't think, you know, I don't, most of the cl our clients really haven't done anything with it.

[00:09:00] **Tim:** So yeah, we're trying to figure out how to do it, but what, what I'd love, we, we've had the same guy for as on our PCI and, and a lot of times, you know, he'll ask a question. I'm not really sure what he's even saying. Right. Because he's so, he's doing this every day in and out, right? It's like, this is just, I'm working on this when he shows up.

[00:09:20] **Tim:** And so he's just spitting out terminology. And I, I learned a trick long ago with him that if I can get him off on a tangent, he will eventually actually tell me the answer that he wants to hear. So he's talking to me about something about these new requirements and like, you know, you know, so how do you do that now and how would you do it?

[00:09:43] **Tim:** And, I'm like, and then somehow we, I got him off on a tangent on ai and then I, I said to him, I said, you know what, in capitalism, how does capitalism work when no one needs to work anymore? When, when you, everything's being done by ai and you got robots that are doing all the physical labor and AI is doing most of the mental labor, how does capitalism even work?

[00:10:05] **Tim:** And so we talked for another, like hour and a half, two hours on that.

[00:10:09] **Adam:** Wow. Sounds like a good use of company

[00:10:11] **Tim:** But during, during the time he basic, you know, I would like ping he, once he gets on a topic that he finds interesting, you gotta know his, like tick TikTok, he, he won't hop off of it. 'cause he's like really, really into Oh, that's a good point. He's like, yeah. So he starts listing off things about AI and then, and I, I tie in the PCI questions, he me, and then he lets the, he lets the answers slip.

[00:10:34] **Tim:** And so I'm like, yeah. So what we're thinking of the doing is I pe parrot back what he just said. He goes, that, that sounds really good. You guys should do that.

[00:10:43] **Adam:** I just take a more proactive approach. You know, the, we meet at the beginning of the year, to kind of make a plan for the year, and they tell me, okay, these are the new requirements. And I'm like, what do I need to do to be in compliance with the these new requirements? What do you wanna see in our policies?

[00:10:56] **Adam:** What do you want to see? You know, like sometimes they're kind of vague about it. They're like, oh yeah, you just need to add something to your security policy about that. And I'm like, okay. Well. Does it need to be? Are we talking, do I need to add six paragraphs or two and a half sentences, right? Like, what is the, what is really the meat that I need to create?

[00:11:13] **Adam:** And he's like, oh yeah, just, just the two and a half sentences sort of thing. Like, okay, cool, thanks. And yeah, so I mean, I don't think that they're trying to catch you so much as just because we use the same company, right? You're using 360. Yeah. Yeah. So, um,yeah, they're, they're just trying to, you know, help you find the right answer and, and be compliant.

[00:11:34] **Tim:** yeah, yeah. But I don't want like clicking dumb. Sorry.

[00:11:37] **Adam:** Yeah. Not me, man. I, I, I just, I come into the meeting and be like, Hey, by the way, remember me? I'm the dumb guy,

[00:11:43] **Tim:** I am dumb. I am dumb. I warned him like, I am the least prepared this year for the PCI I that I, and it's true. I, I really was not prepared at all. Didn't even bring my laptop with me. Like, where's your laptop? You're gonna have to show me code. I'm like, I can come back

[00:11:54] **Adam:** Oh, don't worry. I'll whiteboard it.

[00:11:56] **Tim:** Yeah, yeah.

[00:11:58] **Adam:** Got it. Right here.

[00:11:59] **Tim:** No. So that's mostly done.

[00:12:01] **Tim:** the, you know, the few, few little things we gotta button up, but yeah, it went, went pretty well. So that's me. How about you, Adam?

## [00:12:08] Adam's Triumph

[00:12:08] **Adam:** I have also got a triumph for us. Um,so there's, that's right. that's why we're wearing green 'cause we're winning. a great topic for radio. Good job guys. so I have this service that I wrote a few years back. It's called Key Maker and it's, I mean, the name is inspired by the Matrix. Let's not be kidding here.

[00:12:26] **Adam:** but, basically this, this task or, or this service, its job is to look at our one password vaults and, rotate access keys for things that need to be rotated on a schedule.and for, since its inception, there have been cases where, so for example, we have like, we have GitHub actions that deploy to AWS, right?

[00:12:48] **Adam:** And so. we have access keys that are, are for an I am user in AWS that we have saved as secrets in GitHub so that we can use them from our actions to like push up a container to ECR and run an ECS deploy, for example.and that works great except then, you know, on the schedule the key gets rotated and then it stops working and you're like, oh yeah, crap, that was today.

[00:13:14] **Adam:** I gotta go update the key and GitHub action. So that's, that's super annoying, and it's been like that for years now. They only rotate four times a year, so it's like, it's kind of like, oh yeah, we should really fix that, but we'll, we have time, we'll get to it before the next one. And then, you know, two, three years later you're like, this is getting really annoying.

[00:13:30] **Adam:** So I fixed it. It, it only took me like half a day. and it's been great. basically, I just added some extra fields to the one password entries to indicate like, this is this secret that we are managing here is in a GitHub. organization secret, and here's how you find it and update it. And, and then there's some code that does the stuff to, to make a long story short.

[00:13:54] **Adam:** but it's, it's super nice. I'm so happy to have that done. It actually hasn't landed in production yet. I just submitted the pull request today, but, I'm counting it as a triumph already 'cause it's, it's just gonna make our lives so much easier.

[00:14:06] **Ben:** Nice. Very cool. When you say that there's some code that makes something happen, is that code just in a note in one password or it's actually somewhere that can run?

[00:14:15] **Adam:** No. Yeah. So one password for those that are not familiar, I mean, it's just a password manager and you can, you have entries, right? So you say like, this is my AWS password, or this is my Facebook password. Right. And it's got a name and then you've got a, like a username and password field. And then you can have also on that same entry, you can have, I think it's unlimited.

[00:14:34] **Adam:** It's basically unlimited as far as I'm concerned. Number of like key value pairs, right? Here's a field and it's got a, a field has like a name and a value, and you can set different types, right? So you can say, this is A-T-O-T-P, like a one time password, time-based, one type time password where you can say, this is a note, or it's a URL or it's a email address or whatever.

[00:14:53] **Adam:** And so, what I did was I added, some extra fields to, so like, this is, we have a AWS account called GitHub Deployer, and it has access keys, like a access key and secret. And those are saved in one password, all in the same entry. They're, they're, they're both in the same entry. They, the access key ID is the username and the secret access key.

[00:15:17] **Adam:** AWS has terrible naming on these things, is the password. And so I added some extra properties to this entry to say, okay, the GitHub secret name, is this, and this is the, this is where you find the value that should be put in the secret. In the entry, right? So you've got like, it's like GH underscore secrets double underscore, a AWS access key id.

[00:15:40] **Adam:** And then the value for that is username. So then I know to go look in the username field to get the current value outta that and push it into the secret on GitHub. And I've got another one that's GH underscore secrets double underscore, AWS, secret access key. and then that one has password in it.

[00:15:57] **Adam:** So then basically every time I rotate a, a password in one password, I'm gonna be checking for the existence of any properties on anything that begins with GH underscore secrets double underscore. And if I find that, then that's gonna indicate, this is a, there's a GitHub secret for this that needs to be updated.

[00:16:13] **Adam:** And then the, the value tells me where in the one password entry to get the value to put in that secret. So,

[00:16:19] **Ben:** All right. I'm mostly follow that, but it sounds very cool,

[00:16:24] **Adam:** Yeah. And then the, the, I mean, the part that I was worried about being difficult wasn't terribly difficult. So GitHub has like a JavaScript SDK you can use. And really it was just a matter of like trial and error to figure out how to get the appropriate keys to be able to use. It's, it's crazy. It's like API keys all the way down, right?

[00:16:42] **Adam:** So you have to have an OAuth, access token in order to use the SDK. And because I'm updating like Secrets, this is a, a big deal.the account that provides that OAuth token has to be an administrator in your organization. So like we do have an account that's like our help desk at AlumniQ account, and it's a member of our organization and we use it for certain things to like own the key, on an account that doesn't belong to one person.

[00:17:08] **Adam:** So that if that one person separates from the company, it's not a, a big deal. Right?and I. But we don't wanna make that account a, like an administrator of the organization because it gets shared, you know, the, the password for that email address is in our one password and shared amongst the team, that sort of thing.

[00:17:23] **Adam:** So it, it would be a compliance nightmare, I should say, to, to do that. so I created the OAuth account, or the OAuth token on my personal GitHub account to, so that it has admin access to the org. So you gotta plug that into

[00:17:39] **Tim:** What, what was the name of that account? I'm writing it down. Uh.

[00:17:45] **Adam:** anyway, the, so you, you, you have to use this auken to work with the SDK, and then in order to update secrets you have to like cryptographically or I think you have to encrypt them with, a library called lib sodium, which again, this like, sounds very difficult, but it's, once you like read through the steps, they kind of give you 99% of the code.

[00:18:07] **Adam:** It's just a matter of like tweaking it to fit your environment. So I have to like, I pull that OAuth token from one password stuff it in the SDKI use the SDK to get the current public key for our organization and use that as part of, as like one of the inputs to libs sodium to encrypt the value of the secret.

[00:18:24] **Adam:** And then I can push that encrypted value and the key ID with the SDK up to GitHub to, to update the value. Yeah, it's a lot. I know. I'm

[00:18:31] **Tim:** I'll just, I'll just, I'll just stick with security. By obscurity

[00:18:35] **Adam:** Yeah.

[00:18:35] **Tim:** I mean, it, it sounds exactly what you're

[00:18:37] **Adam:** Bunch of ones and lowercase Ls and uppercase i's. and anyway, and, and the, the part that tripped me up for a few minutes was that, the public key for your orgs apparently changes somewhat often.

[00:18:49] **Adam:** you know, like I was like, okay, well it belongs to our org. I got the value two or three times, you know, 5, 10, 15 seconds apart just on a command line running test. And, and it was the same every time. I'm like, okay, so I could probably just get it at the, when the script starts and I don't have to worry about it.

[00:19:03] **Adam:** And I started running it. It seemed to be changing in the middle of my script running like, okay, well then I guess I have to get it at the start of every encryption step. So that was interesting. But yeah, I'm just,

[00:19:17] **Tim:** But you got it working.

[00:19:18] **Adam:** yeah. Yeah. I'm super excited to have this done. It's gonna be one less thing that accidentally breaks every now and then, so.

[00:19:23] **Ben:** I always feel when it comes to security stuff because I, I know very basic security concepts, but I'm not by any means a security expert. So when something feels very complicated, I really have no litmus test or instinct for whether or not it's complicated because there's a security benefit or if it's complicated because someone just wanted to make it complicated.

[00:19:47] **Ben:** And that's not, that's not a comment about what you're doing. It's more comment about, I'm thinking of the AWS because you mentioned AWS, their like signature V four for creating pre-signed URLs. When you create a pre-signed URL, it's, I think it's like you, it's, it's like the, the bucket name and then the resource and then how long it's available for.

[00:20:10] **Ben:** And then I think there's like one other thing that's required. And the way that gets signed, I don't remember all the details quite off the top of my head, but it's like you, you use your secret key to hash part of the code, and then you use the output of that as the input for the next hash. And then you use the output of that for the input of the next hash.

[00:20:27] **Ben:** So you end up having to do this likes. Five level hashed message, authentication code. And, and I just like, I don't know why that's more secure than just doing it once with a secret key, but I have to believe that Amazon is doing this for a reason and that they chose to do this with signature V four versus what they had before, which was, I guess, less secure.

[00:20:48] **Ben:** I don't know. But it's just frustrating just 'cause it's so much more complicated than, than just the standard H

[00:20:55] **Adam:** Job creation.

[00:20:56] **Ben:** Yeah.I hate that though. I hate just having to go with something like just shrugging and being like, well, that's what the documentation says. Not that I would just not do it, but, but I just wish I

[00:21:09] **Adam:** Yeah. You would.

[00:21:09] **Ben:** better anyway.

[00:21:14] **Ben:** Anyway. so let's get into our topic for the day. Ben, this was kind of out of your, your brain hole. Yeah.

[00:21:22] **Adam:** why don't you introduce.

## [00:21:23] Shifting Values

[00:21:23] **Ben:** Yeah, I, I'm gonna struggle here because I don't have all the right words to, to codify. I think the thoughts that are bouncing around in the vast cavernous regions of my, of my skull here,

[00:21:33] **Tim:** It's a big no.

[00:21:34] **Ben:** it's a big n and there's a lot of things going on, and I have been personally struggling with a lot of the AI stuff lately, and by struggling, I mean like struggling to understand how to bring it into my world in a way that feels like it's adding a lot of value.

[00:21:50] **Ben:** That's not the topic, but that is kind of the thing that put me into this mindset, which is the idea that in the last couple of years as the LLMs have been introduced, LLMs being large language models and the whole AI wave that's taken over everything. There's been some conversations that I've heard about companies kind of seeming to abandon strongly held beliefs they previously had because.

[00:22:20] **Ben:** You know, to put it bluntly, those, those beliefs were just no longer very convenient for them. The first time I had heard this was, I dunno, maybe like two years ago, and people started to talk about all these companies that were very public about their green energy and, and how they were offsetting their carbon usage and they were trying to, reduce all of their emissions and carbon neutral, et cetera.

[00:22:42] **Ben:** And then the moment it turned out that we needed a tremendous amount of energy to chart, to train these language models, it was like these companies no longer really cared about these green energy models. And now they were trying to build their own power plants. And and then just,

[00:22:57] **Tim:** baby drill.

[00:22:58] **Ben:** just recently I heard, one person on a podcast complaining that their legal department and their compliance departments were preventing them from really adopting AI as quickly as they would like to internally to the company and how frustrating that was.

[00:23:12] **Ben:** And the guy on the podcast was saying that the legal department should essentially just get outta the way. And allow developers to really get on the wave of this AI stuff. And how that struck me as very strange because if you didn't believe that your legal departments and your compliance departments were adding value, then why did you have them to begin with?

[00:23:31] **Ben:** Like, just because now it's a little inconvenient. You want to get rid of it. And, and those are kind of, I think, much more concrete examples. But then there's been a whole bunch of other stuff that's, that's sort of bounced around in my head. Like the idea I, I'm sure people have heard this phrase or a phrase like it, that code is meant to be read by other humans and only incidentally run by machines.

[00:23:56] **Ben:** The idea, the idea being that there's a, there's a craftsmanship to coding

[00:24:01] **Adam:** Mm-hmm.

[00:24:01] **Ben:** and that you wanna build code that is understandable to you and to other people. And the fact that the machines can run it and they can run it in high performance and their optimizations that you can do, like, that's an afterthought almost, even though, you know.

[00:24:14] **Adam:** it's like the, the code is the act of really drilling down and understanding the requirements. Like we talk about requirements, but we don't really truly talk about them or think about them that deeply until it's like, well, but I have to make a decision.

[00:24:28] **Ben:** Yeah. Yeah. So

[00:24:30] **Adam:** to make it black and white here.

[00:24:31] **Ben:** in light of all of this kind of vibe, coding and AI stuff, I wonder do people, I mean, I'm not saying that everyone even believed that as an idiom previously, but, or even the people who believe that now maybe tossing that aside a little bit, being like, ah, it really doesn't actually matter what the code looks like, because if I need to refactor it, I just tell the AI to refactor it and it doesn't, like, it doesn't even matter how much I can understand it.

[00:24:54] **Ben:** yeah,

[00:24:55] **Tim:** Can I, you gave lots of examples there. Can I try to distill what I think you're saying just to

[00:25:00] **Ben:** yeah, yeah, yeah. Please, yeah. Focus me.

[00:25:03] **Tim:** Yeah. For, to, to chart the course here. So some of those things you're talking about, like, sounds like company's core values, right? So most organizations will have a exercise where they're talking about their big, hairy, audacious goal that they want to, you know, bring world peace or what, whatever their goal is.

[00:25:20] **Tim:** But then you have the core values, like we have like stated core values about what are your principles as a company and, and many companies, the past, you know, 10 years have, you know, the green going green is like, has been a core principle that they put in there with other things, you know, like making good software, making things easy for people to do X, Y and Z or, you know, Making a more fair and equitable world with DEI, things like that. And then reality sorts of happens to your core principles and then you gotta decide are alright. Was that ever really a core principle? Do we need to keep fighting for this? Or is this something that we just said and didn't ever really believe?

[00:26:07] **Tim:** Or, or, or don't have the, we just don't have the, internal fortitude to stand up for and we're just gonna let it slide because it's convenient. Is that, is that kind of what you're talking about

[00:26:20] **Ben:** just to interject, Adam, before you jump in, but I wanna say that I, I think it applies more broadly than to just high minded principles. And if I could do like one very non-value, like very meaningless thing when I was learning TypeScript and using it heavily in Angular, I was like, oh, typescripts so amazing.

[00:26:44] **Ben:** Like, I love how it makes me think this is so great and like everything's typed and I totally get it. And then I, when I started to do little personal projects, I found myself not wanting to actually pull in TypeScript. And I was surprised by that. I'm like. I seem to really like it, so why am I not feeling the urge to pull it in on small projects?

[00:27:06] **Ben:** Like I, I didn't know how to reconcile that. So it's not even like, you know, let's

[00:27:11] **Tim:** So your mind, there was great value to typing, having strongly type things, but in practice, your, your body was like, your mind was like, eh,

[00:27:18] **Ben:** eh, maybe some other time. And, and I wonder, are there questions that we can pose to ourselves to help us maybe better understand what is and what isn't actually valuable? And so, sorry Adam, I know I cut you off there, but I just, I wanted to say that it wasn't, it wasn't just like high-minded philosophical things.

[00:27:38] **Ben:** It was also just very mundane

[00:27:40] **Tim:** That's me. You know, I'm a very high-minded

[00:27:42] **Ben:** Very, very, you're, you're very academic, very intellectual.

[00:27:47] **Tim:** Called me a nerd. You hear that guys? He called me a nerd.

[00:27:50] **Adam:** If the shoe fits. I almost said it the other way around.yeah, I mean there, I, there's a lot swirling around in my head. It's gonna be hard to go point for point. So I'll just say a couple of things that, that are standing out to me. You talked about, you kind of used green energy as an example, right?

[00:28:06] **Adam:** Companies, being very vocal about their commitment to. Carbon offsets and carbon emissions reduction and just using green sources of power, that sort of thing. And then letting that go, when AI became a thing that a lot of companies have started to do because the, the two are kind of diametrically opposed, right?

[00:28:27] **Adam:** You, you can't be a huge proponent of ai. And also, just because of the power requirements, you can't also be like, eh, yeah, yeah. We're, we're gonna run the world's only, wind turbine powered AI data center. Yeah. And nobody's gonna use it because it's just not gonna have enough power sort of thing.

[00:28:45] **Adam:** Right. I do think that there's an element of, survival has to come first for a company, right? You, you, it's great to live your ideals, and, and be the kind of company that you want to be. But as a company, if you don't survive, then you can't live those ideals. Right? You have to. You have to continue making money before you can spend it how you want to spend it.

[00:29:07] **Adam:** so

[00:29:08] **Ben:** It's kinda like a, like a Maslow's, is it Maslow

[00:29:11] **Adam:** Yeah. Maslow's hierarchy of needs.

[00:29:13] **Ben:** Yeah. Where it's, you know, survival and safety is that base layer.

[00:29:17] **Adam:** Yep. and so I, I, and now I'm not trying to defend anybody in particular with that. I'm just saying like, it's a possibility, right? Like the, I I do think that there are plenty of companies out there that said the whole green energy thing, because it was politically expedient, you know, maybe it got them some attention or whatever.

[00:29:36] **Adam:** And now that it's not politically expedient, they're equally happy to let it go. but I, but that doesn't mean that the other side of the, the coin isn't also there.the other thing that's kind of swirling around in my head is like,again, along the lines of political expedience, right? So you've got all these company, Tim, you mentioned DDEI stuff, you've got all these companies that for years have been super vocal.

[00:29:58] **Adam:** About their DEI practices and, you know, being very progressive in their hiring stuff. Target for Target is a great example. I think. you know, for for years they've been known as a very, LGT, L-G-T-B-Q-I-A plus, friendly, hire or place like employer or place to work. and under the new administration that has changed.

[00:30:23] **Adam:** It does seem to be store by store. It's kind of a little bit more up to the manager now, I think. I think that honestly, it, it's almost like the federal government pushing stuff down into the states. It's like the, the, the corporate, the, the national level company is just being like, well, the state, the, the stores can figure it out.

[00:30:42] **Adam:** Right.so it kind of depends on the, the manager of the store that you're applying to. What, what life as a, non Non cisgendered, you know, straight, white male is gonna be basically, so yeah, it's, there's, there. I don't think that there's a way that we can nail this down to a single

[00:31:00] **Ben:** Right.

[00:31:00] **Adam:** or, or point of inflection.

[00:31:02] **Adam:** Yeah.

[00:31:02] **Ben:** I guess, I guess what has me curious is just, is there. Is there something I could have asked myself or a, or, or a thesis that I could have proposed or something that I could have challenged the thought and said, I, I don't know. I like, I don't know. You know, in, in the, in the, like, if it's not a hell yes, it's a no.

[00:31:20] **Ben:** Kind of a mindset. Like, is there something I could have said, like, this is just not that important.

[00:31:25] **Adam:** You're talking about AI in general, or, or

[00:31:27] **Ben:** I don't, I don't know, just in this, generally speaking, I have something that I feel is a value or a principle, but is it really,

[00:31:38] **Ben:** I,

[00:31:38] **Adam:** I mean.

[00:31:39] **Ben:** I,

[00:31:40] **Tim:** I mean, when everything's important, nothing's important, right? So,

## [00:31:43] Code Craftmanship and AI

[00:31:43] **Ben:** just so the AI stuff brings up a lot for me because it is a, it is a huge challenge to my outlook on life and, and one of the things that is challenging very much is just the inherent value add of elegant code.

[00:32:00] **Ben:** I've spent my career just trying to become philosophically better at programming and thinking about how I organize and how I name, and how I put things together and dependency injection and, and file organization. And like all of that served a purpose. It wasn't just, it wasn't just hand for the sake of hand wringing.

[00:32:21] **Ben:** It was, I've felt pain in the past, and I think a lot of that pain comes from my lack of experience. And by gaining experience, I can reduce pain in the future. And there is, there is a, a, a, you know, a craftsman, a journey to it.

[00:32:36] **Tim:** So, so craftsman that you, you hit the word there that I was looking for. I, I think, and I, I, I've read lots recently. Many people feel that our industry, what we do is all of us are coders, is possibly heading toward an inflection point where it's moving away from craftsmanship to where, you know, you had the early days, Carol, you will not get this reference at all.

[00:33:03] **Tim:** Maybe Ben won't even, maybe none of you will. I'm I'm older than all of you. But there, there was an episode of, of Little House in the Prairie. Hold, stay with me. Here I I there's a point here. There's a point here. So, so, so Paul was like a really skilled carpenter. He had lots of skills, but he was really good carpenter. And so this episode, it focused on him and his carpentry business, right? He's making these really nice ch and it, it's craftsmanship to it, right?

[00:33:35] **Tim:** He's making beautiful chairs. He's worked years to hone his skills. He has all the right tools and he is, he is making beautiful work and he can't sell them. Because like this was the days when, when mass labor industry, repetitive factory type things were coming out. And so he finds these chairs, like, all these chairs are crap.

[00:33:55] **Tim:** You know, they're not nearly, look, look at this terrible hand turning on this, this, this spindle or whatever. I dunno.

[00:34:02] **Adam:** That's a word. Yeah. Go

[00:34:02] **Tim:** He, he's, he's crapping on it, but it's like, what can he do? 'cause they're, they're like a 10th of the price of his stuff. And so many people think that coders that we are heading toward that thing where AI being the super tool that they think is going to be will eventually you can take pretty much anyone who has a amount of logic and reason in their head can sit down with an AI and through trial and error, write a halfway decent program. And so it's no longer about craftsmanship. It's about let's just get these people. Trained up to use the AI well enough where we can just put a whole bunch of these people together with enough compute resources to build complex software. It's not about, it's not about craftsmanship anymore, it's about just churning it out and now we've become factories for code.

[00:34:51] **Tim:** and so I think that's, it's kind of where that dichotomy that you're feeling of, 'cause your new role, you're like, let's use the ai. And the AI is not really giving you the experience you want 'cause you don't wanna be a factory worker.

[00:35:06] **Ben:** I don't want to be a factor worker, but but also. I mean, the, the furniture stuff is an interesting thing only because in modern times now there is, there is kind of a dichotomy of man mass manufactured versus kind of artisanal, handcrafted thing. You know, it's why you can go to Dunkin Donuts and get coffee for 99 cents and you can go to another store and get that same coffee for 7 99 and, or, or you can buy a pair of sneakers at, DSW for 80 bucks.

[00:35:38] **Ben:** Or you can go in and buy an Italian pair of loafers for like $2,000. I mean, there's, there's, there is still a value in the handcrafting and the mastery of something, but not at the, you know, it's niche, I

[00:35:53] **Adam:** It's not a volume business.

[00:35:54] **Tim:** Yeah. But, but, so we're at the point in, in the. History of coding to where we've never seen that, there's never been mass produced coding. Right. There's, it's always been smart people with talent working really hard to come up with, with a good, a good product. And now people are looking on the horizon going, well, maybe that's not gonna be my job in the future.

[00:36:17] **Tim:** I mean, my, my son's about to graduate with a CS degree and I'm worried is like, is he gonna just be a factory worker when it comes to coding now? 'cause I'm sure he's not gonna be happy with that.

[00:36:27] **Ben:** He's got that forging he can fall back on.

[00:36:30] **Tim:** Yeah, yeah,

[00:36:32] **Adam:** It's gonna be blacksmith,

[00:36:34] **Ben:** Well, I mean, so you mentioned his CS degree, but that's, I mean, education right now is also one of those things where I think there are a lot of people having this very type of discussion where, what was actually important? Is it important that someone, a kid, can go home and do three hours of homework a night?

[00:36:50] **Ben:** Like was that actually the thing that we needed that person to do or. Or was that a proxy for the thing that we thought we were trying to teach? You know, whether it's like reasoning and, and the ability to do deep thinking and, and understanding and reading comprehension. Like how do we, like, may maybe the things that we thought were important were in the same type of important.

[00:37:10] **Ben:** I, I don't know. You know, I don't know how to articulate any of this. It's just a lot of feelings right now.

[00:37:14] **Adam:** I think we're definitely experiencing some disruption, a shakeup, if you will. and at least in the short, I don't wanna make long term predictions, but I think at least in the short term, it's still pretty clear to me that you have that, that people who are paying to have code written, right, whether they're spending money to do vibe coding, or they're paying a professional like us, they have a choice right now.

[00:37:38] **Adam:** They can get their code from Temu or, or they can pay a professional who's got years of experience and, and, And contribute to the, the craft of the code. Right. So like, again, only thinking short term. You just cannot drop an AI into a 25, 30-year-old code base and expect it to make sensible changes in a non-disruptive way.

[00:38:06] **Adam:** yeah. You just, it just can't happen, in, in the way that it can with a person. Right. Yeah. Yeah. It, it's a very interesting thought to think further. I don't, I don't know what to make of that.

## [00:38:17] Short Term vs Long Term

[00:38:17] **Ben:** I was listening, I think this was the ABOARD podcast, which they've changed their name a couple of different times. I'm not sure if that's actually the name of it anymore. but they were talking about how software companies right now are having an issue where they're actually producing a ton of features very quickly, but they make the point on the show that.

[00:38:38] **Ben:** Creating software is only a really small part about the whole product development and selling lifecycle. And people are a huge part of it. And just because you build something that's new and fancy doesn't mean that people are gonna adopt it. I mean, you know, sublime text user over here can verify, you know, can confirm I'm not changing things all the time just for funsies.

[00:38:58] **Ben:** But if you're using a piece of software, you know, like alumni Q and you come out with a new feature, that doesn't necessarily mean that every university is suddenly gonna jump on that new feature. They have a way of doing things that might not be relevant or they might just not, you know, they might just not want to change.

[00:39:14] **Ben:** People don't want to change. So now what these huge companies are having is they have a vastly increased landscape of code they need to maintain and it's not necessarily getting broad adoption. So it's basically they have more, overhead to maintaining their business empire. But for less payoff because the people who who would normally be flocking to a feature are much more thinly spread, you know, across the feature landscape.

[00:39:43] **Ben:** And so they're saying, I don't know if this was more theory or if this is actually feedback that they're hearing. I feel like it was feedback that they're hearing that people are saying like, well, wait a minute, maybe we shouldn't actually be producing software this quickly. That it's actually, it's actually gonna have a mid to long-term burden on us.

[00:39:59] **Ben:** And, and the, the benefit upfront has actually not been that great.

[00:40:03] **Adam:** yeah, I mean, again, going back to short term versus long term, there might be some short term gains available in the near future, right? Where we can just be like, oh, well, I don't have to pay a coder. I can, I can just get 90% of the way there. with the, the vibe coating stuff, if, and if that is possible, then perhaps that's a good thing.

[00:40:23] **Adam:** However, when you need to close that final 10% gap and you need a coder, you need a coder who has the experience of, of, you know, coming up through the ranks, starting out as a junior and working your way up. And if you just don't invest in that workforce, it's not gonna be there. At some point. We're all just gonna.

[00:40:38] **Tim:** I think we're gonna retire and then we, we go over a bridge. I think it's like made of rainbows and there's a farm.Only if you're a good boy or girl.

[00:40:46] **Adam:** yeah. All coders go to heaven. and, anyway, yeah, you get what I'm saying?

[00:40:53] **Ben:** Well, so, okay, here's another thing, Doug, going back to the idea of there was some value that

[00:40:58] **Tim:** Is Carol, come on. Carol's been quiet the

[00:41:01] **Ben:** sorry. Sorry, Carol. Did I, did I speak over you?

[00:41:03] **Carol:** so hard. Every time I go to say something, you guys talk

[00:41:06] **Ben:** sorry, sorry, sorry, sorry. Go, go, go, go,

[00:41:08] **Carol:** No, no, you can finish with

[00:41:09] **Tim:** No, you, no. Carol. Shut up in Ben's talked way too much.

## [00:41:13] AI and User Empathy

[00:41:13] **Carol:** So like, I have a thought though that the, the fact that we're all using AI to help us build, like this initial way of thinking is fine, but what these models lack is user empathy.

[00:41:26] **Carol:** And that's where we're gonna be valued at. they can take a question and get an answer, but they don't act like this model doesn't actually understand like what your user is trying to accomplish. So you can say, Hey, here's A, here's B, but my users don't want any of that, right? Like they want it displayed and they want it given to them in a way that makes sense to them.

[00:41:47] **Carol:** And that's not what is being produced by chat GPT. So whenever I'm using copilot and these tools, it's great for saying, okay, here's my framework. Like, here is my value, like your value add right now is just a framework. It's just showing me how to get going. What I deliver isn't what you're putting out.

[00:42:06] **Carol:** It's the whole empathy map of my customer. It's understanding what I'm delivering. It's putting a lot more into it than just a, a tech solution. It's a full blown like piece of art in my opinion.

[00:42:20] **Ben:** Okay, so you struck on something that has also been bouncing around in my head, which is this whole using AI to summarize things. And I haven't been on a tremendous amount of customer calls in my career. The ones that I have been on I have very much enjoyed. And a huge part of that joy for me has been that subtle human empathy aspect where I could be talking to Tim about PCI version four compliance, and we're two hours into a conversation.

[00:42:52] **Ben:** And then he says some tiny, random thing about the software, like, oh, wouldn't it be great if I could do this? It just make my life so much easier. And I'm like, whoa, what? Let's now tangent on that for another half an hour, because that came out of left field. I wasn't expecting it. And if you try to take that two hour call.

[00:43:08] **Ben:** Have AI reduce it into, you know, gimme the top 10 bullet points from this call. Like chances are that was not gonna come up. And I would not have gone down that rabbit hole and I wouldn't have felt this random pain point that Tim was feeling. And, and that's, I, I get very nervous every time I hear people talk about using AI to, to summarize and extract value from larger things.

[00:43:33] **Adam:** I, I just wanna expand on what you're saying there a little bit, Ben. the, I think one of the best experiences of my career, like that made me feel valuable and, and empowered was, taking similar client meetings, but putting the software in their hands, right? So I'm, we're like running it on a dev server on my local machine, and we're sitting across the conference table from each other and they're running it, that, you know, they're the one driving on their machine.

[00:43:59] **Adam:** And like you said, they're just like, oh man, I really wish I could do this. And I'm like, hang on one second.

[00:44:03] **Ben:** Yo.

[00:44:04] **Adam:** Okay. Refresh the page because it's got hot module reloading, right. So I'm like, look at it now. and, and they're like, you just saved me an hour a week for the rest of my life. I'm like, heck yeah, I did.

[00:44:14] **Ben:** Oh, it's the best. it's the best and, and I feel like we're losing or we can lose that magic, that interpersonal magic.

[00:44:22] **Adam:** It's easy to give it up. Yeah.

[00:44:24] **Tim:** yeah. But you know, every industry feels like, oh, it's, it's our people that make everything special. And capitalism basically has proven to us that it really isn't. I'm, I'm sorry. It's like, you know, they're like, well, you know, our customers, no, people are gonna leave for the things that's newest, fastest, and cheapest.

[00:44:41] **Tim:** And you only get that economy by, by doing things quicker and cheaper. And, and that's what, that's what the market is looking for for ai. That's why there's an earnings call in in twenty twenty four, twenty twenty five. They, and they're doing software, or even if they're not, I don't care, they're doing shoes.

[00:44:59] **Tim:** They'll use the word AI 50 times in the earnings call, just so that the market feels that they're actually. You know that there's, there's magic there.

[00:45:08] **Adam:** Keeping

[00:45:08] **Tim:** and that magic equates to, yeah, we laid off 20% of our people and we're getting higher efficiency from the people that we've got. That's just unfortunately when the reward system is capitalism, that's how things work.

[00:45:21] **Ben:** So, okay. If I can, if I can kind of steer back though for a second onto the Oh yeah, go ahead. Go ahead.

[00:45:29] **Adam:** so.

[00:45:30] **Adam:** I, I'm really hoping that this is cyclical. I don't know that I've seen that it is yet, but it, you know, if you think back to when we were younger, you, there was this trope, especially in movies and tv, but I think in, in real life I've experienced it as well where, people of the previous generations would see the younger generations focusing on the new and the hip and the, you know, the disruptive new thing.

[00:45:55] **Adam:** And, you know, when we were getting so excited, invest, investing all our attention in this new shiny thing, and then the, but the people from the previous generations would see, oh, well that, that's gonna burn out. Right? That's the, that's a cheap plastic piece of junk from China. I'm gonna stick with my tractor, my John Deere that I've had for, I.

[00:46:13] **Adam:** 50 years and it's still gonna be here and I can still fix it and that sort of thing. I do hope that we are in that like, sort of negative part of that cycle with the, the way that people are thinking about investing in our career path and our industry and that people will kind of snap out of it and go, you know, if we don't invest in these people, then when we need them, there won't be any Right.

[00:46:38] **Adam:** If we throw away all our tractors.

[00:46:40] **Carol:** Mm-hmm.

[00:46:41] **Ben:** Well, and in the tractor world, the whole right to repair and people wanting to build things with fewer moving parts and and 3D printing parts. I mean it did. It is very interesting in the manufacturing space how people talk about, oh, I bought a refrigerator in the 1950s and it still runs today. Versus like, I bought a refrigerator three years ago.

[00:47:01] **Ben:** Now it's broken.

[00:47:02] **Adam:** Yep.

[00:47:03] **Tim:** That, that 1950s refrigerator is terrible for capitalism. It absolutely

[00:47:09] **Carol:** If you don't, if it doesn't break, yeah. If

[00:47:11] **Ben:** Yeah,

[00:47:12] **Carol:** you don't replace it.

[00:47:15] **Ben:** Okay, so to steer back for a second to this whole idea of something we held as a value or a belief, and then maybe that didn't turn out to actually be true, were a couple years ago where. This was at Envision, but I also heard this type of conversation and happening elsewhere where people were, would say things to the effect of, I would love to hire junior engineers, but we just have too much work to do and we can really only afford to hire senior engineers right now.

[00:47:42] **Ben:** And now you fast forward a couple years and people talk about AI as it's really great. It's like you have five junior engineers under your control. And I'm like, okay. So a couple years ago we couldn't afford to have junior engineers because it wouldn't be good enough to get the work done. And now having a whole bunch of junior engineers, that's somehow easier to get work done.

[00:48:03] **Ben:** Like

[00:48:04] **Tim:** but they don't need health insurance.

[00:48:06] **Ben:** I know we like, like somehow the math doesn't make

[00:48:08] **Carol:** babysit.

[00:48:10] **Tim:** Yeah.

[00:48:11] **Adam:** I, I do think there's an element of truth to that. I think you're right, Carol. Like the, a junior engineer that's got two years of experience is very different than a junior engineer that's got two weeks of experience, right? A two week experience engineer is gonna know the way around their code editor, and that's about it.

[00:48:30] **Adam:** versus the two year person is gonna another way around the code and maybe they're not ready to take on a project with no supervision, but you know, they're gonna, they'll pick, they'll perform at least as good as ai.

[00:48:40] **Carol:** And the problem I have with people who commit code directly from generated code is I look at it and I go, well, it looks very smart. Like it looks like you know, what you were trying to accomplish

[00:48:55] **Adam:** I didn't even know that method exists.

[00:48:56] **Carol:** I mean, like.

[00:48:57] **Adam:** Spoiler alert, it

[00:48:58] **Carol:** how you can close it? Oh no, you can't. Like all of a sudden you're committing something and in your pull request chat, GPD is then telling me your copilot is that your pull request is wrong and you can't explain to me like how you even got this code.

[00:49:13] **Carol:** So I'm like, my babysitting just went from like one to now everything, so it's so much worse. I would much rather have someone who's asking questions than just committing code because it looks like it's probably fine.

[00:49:28] **Ben:** Yeah. Well, and, and people have self-reported, and this is all, what's it called when information is based on stories, not on science. Yeah, yeah, yeah. This is, this is purely anecdotal, but I have heard people self-report that they feel like they are losing some degree of skill in terms of deep thinking

[00:49:51] **Adam:** Well, you know that the plural of anecdotes is evidence, right?

[00:49:53] **Ben:** Yeah. Well, and they say like, you know, oh, when I'm on a plane and I don't have access to chat GPT or, or something to that effect, they're like, I suddenly feel like I don't know how to write the code, or I have to really stop and think about what it is that I'm trying to do. Yeah. And

[00:50:07] **Carol:** You're not an engineer,

[00:50:09] **Ben:** yeah, it, it, it, it, this is one of those things where, to me, that seems like there is a value that is being violated at that point, but I can't tell if that's just a false belief.

[00:50:21] **Ben:** You know, I, I feel like I don't have the tools to challenge my own assumptions at this point, or if I'm just being that, you know, old man yells at cloud kind of situation.

## [00:50:31] AI For Boilerplate

[00:50:31] **Carol:** So I will say, like for me, if I start writing something new, I never can remember like how to set up a new TypeScript project or how to knit something in Node or NP, I don't know. So I just type it in, it gives it to me. I hit yes accept, and then I start playing. Right? So there are those things that I use in constant when testing and trying that.

[00:50:53] **Carol:** I'm like, I don't wanna muscle memory this anymore because it's at my fingertips, but I'm definitely not asking it to write like Pure's JavaScript for me. Like I'm not asking it how to debug my code. All I'm saying is give me a place to hit start and then I'm off and running

[00:51:11] **Adam:** Speaking of references that Carol probably won't get, do you guys remember using Yeoman? Did you ever use Yeoman?

[00:51:18] **Ben:** This was the one from Google,

[00:51:19] **Carol:** a biblical thing,

[00:51:21] **Adam:** It was a, a tool. right. It came out I think, very similar in time to like version one of Bootstrap. It was, oh, right around that same time.

[00:51:30] **Ben:** I think ADD Ani, wrote Yeoman it. It was like an NPM competitor,

[00:51:37] **Adam:** like browser client, like script tag type level stuff. Yeah. It was, it, it was kind of a code generator slash dependency installer, I think.

[00:51:50] **Adam:** Anyway. like Carol was saying, you know, I, I, I could not. Sit down and, and start a TypeScript project from scratch. You know, you've got your TS config and you've got your bundler stuff to set up and, and

[00:52:01] **Carol:** blah, blah, blah,

[00:52:03] **Adam:** I could, figure it out given a couple of hours with the, with Google, but I'd rather not.

[00:52:08] **Adam:** And I think, and that's what made me think of Yeoman is, is you, I, I never used yeoman 'cause I was like, I don't get it. I understand how to save a, a JavaScript file to my machine and then drop a script tag on the page. Like I, that's not hard to me. but, there are like code generators that I, I freaking love, like starting a news Svelte kit project.

[00:52:28] **Adam:** There are so many file, I mean, not to, not to sound negative, but there, you know, there's somewhere around like half a dozen to a dozen, you know, metadata files that have to get started, right? You got your ES limp config, your TS

[00:52:40] **Tim:** be negative about Svelte. It'd be a refreshing change on this show.

[00:52:44] **Adam:** Any mention of Svelte is a good mention. No press is, or all press is good press. Right? How does that go? anyway, yeah, but like, you know, there's a, there's a NPX SV create, right? and, and it does all of that for you so that you just have to answer a couple of questions, and it spits out all the metadata files that you need.

[00:53:01] **Adam:** You've got your package js on everything. You run NPM install and you're good to go. And then you write the, the application code. That's, that's the way it should be, right? Like framework getting outta your way. The framework should install itself more or less, I think. Yeah. And, and there's, you know, there's room for a thousand different types of frameworks, whether it's a CLI app or a web app or, or whatever else.

[00:53:23] **Adam:** Yeah.

[00:53:24] **Ben:** Yeah, there's definitely code that I've never written on my own before.

[00:53:29] **Tim:** Tests.

[00:53:32] **Carol:** They usually live in that project.

[00:53:34] **Ben:** Oh.

[00:53:35] **Tim:** kind of, you know, maybe we deserve this.

[00:53:40] **Carol:** What did you do wrong?

[00:53:41] **Tim:** I feel like this is coming full circle 'cause you think about like. In my career, like over 25, 30 years being in software, I've disrupted lots of people's jobs,

[00:53:53] **Adam:** Mm.

[00:53:55] **Tim:** right? I, I tell the story. We went to a, an insurance company. It's here in middle Georgia, Macon, and you walk in and everything was paper.

[00:54:05] **Tim:** There's like rooms and rooms of filing cabinets for insurance policies. And there are, there's this pool of typists who will take a file that's in the morning. There's this cart. The lady, there's a lady, her whole job is, she pushes the cart, she grabs the files that are relevant, that need like endorsements and changes in new business and whatever, and underwriting, she puts 'em in a huge pile on her cart and she drives along the aisle and she takes the appropriate folder and drops it on the table of the typist or the underwriter.

[00:54:37] **Tim:** Right. And

[00:54:38] **Adam:** takes the requirements from the customers to the developers.

[00:54:42] **Tim:** then, and then, so the typist gets this and all, all she does is she's taking some of the base things that were on the original estimate of the quote to the actual deck sheet, the declarations of what there is. And you know, and she, and she asked me, so we're, I'm looking at all this.

[00:54:58] **Tim:** And she asked me, she says, so she explaining her work. So I'm asking everyone what their job is, what do you do? And she's like, well, I take this over here and I type this. And she goes, so will the new system make this easier? And I didn't have the heart to tell her. I mean, the answer was yes, this new system will make this easier.

[00:55:14] **Tim:** But the actual answer was, yes, you won't be needed anymore. And

[00:55:17] **Adam:** Yeah.

[00:55:18] **Tim:** I just drove past that place the other day and it is shut down. They're all, all a hundred percent remote now. There's no, and like all those people that was, this is 20 something years ago, are all gone and it's, and so now I think it's come full circle now AI's coming for our jobs apparently.

[00:55:33] **Tim:** Right.

[00:55:35] **Ben:** Uh, it gives me a knot in

[00:55:36] **Tim:** our turn to be disrupted. And I think that's sort of the, the, the dissonance that you're feeling is like, this is being sold to all of us as this great cure for all of our software problems. When it, it might just be, it might replace us.

[00:55:51] **Adam:** Have you guys tried being a billionaire and pulling yourself up by your bootstraps?

[00:55:54] **Tim:** I know, right? Just give a small loan of, you know, a hundred million dollars and I'll be good.

[00:55:59] **Ben:** Oh brother.

[00:56:01] **Adam:** So, before we wrap it up, I, there was something that you had said before we started recording, Ben, that I kind of want to go back to. I feel like that would be a good place to end it if it, if I did hear you correctly. So I'm gonna say it, you tell me if I'm on the right path.

[00:56:12] **Carol:** are

[00:56:13] **Adam:** had me, oh, darn it.

[00:56:15] **Carol:** Sorry.

[00:56:16] **Adam:** you had mentioned something along the lines of like, is this even a valuable, pursuit, right? The, the, the idea of like, is this AI stuff even worth investing in? Like, because a lot of what it does generate is kind of slop garbage

[00:56:35] **Ben:** Yeah, I mean that's certainly one of the things that goes through my mind for sure.

## [00:56:39] Basic Research

[00:56:39] **Adam:** So are you familiar with the concept of, I, forgive me if I'm getting this wrong, other smarter people than me, basic research. So there are, there are scientists around the world who get grants or whatever to, study things that sound completely inane and useless to you and me. Like the, the eating habits of the three anus sloth, right? Like, how is that gonna benefit humanity? We have no idea, but we, we, we fund with taxpayer dollars a certain amount of quote unquote basic research.

[00:57:12] **Ben:** fo show. Sorry, this is like top of mind for me.

[00:57:16] **Adam:** Yeah. Yeah. And so some of it, yes, the eating habits of the three anus sloth may be not super important in the, in the grand scheme of things, but you know what might end up being one day? so

[00:57:29] **Ben:** Can I, can I, can I jump in for a second? So, Radiolab, which is a podcast, they just had an episode, I, it may have been a replay, I'm not sure, from, from literally like a week ago or two weeks ago. And it was all about exactly this, that there was a guy in the seventies who went on some expedition to Yellowstone National Park to study organisms at the edge of the geysers to see, because they're extreme temperatures.

[00:57:57] **Ben:** And there was a. Forever this belief that life couldn't exist above the boiling point.

[00:58:04] **Adam:** Mm-hmm.

[00:58:04] **Ben:** they went and they found these little bacterium and bugs that were living in the boiling point of this water. And they went and they studied them and they found that the reason those bugs could survive were because there was some type of protein that prevented the DNA from basically decomposing at these high temperatures.

[00:58:24] **Ben:** And they, they were like, oh, that's interesting. And they put it on a shelf and literally nothing was done with it for like two or three decades. Then suddenly there was a need for somebody to do something with DNA, but they couldn't figure out how to get this thing to work at a high temperature. They're like, oh, this guy discovered this organism back in the seventies.

[00:58:41] **Ben:** They can do that. And I'm, I'm not explaining it very well, but suddenly, 30 years later, this discovery was now the basis for basically everything that we do with DNA today, whether it's mRNA, vaccine generation, and, and DNA testing and, and like, everything, everything that you do with DNA is basically made possible because of this one guy's random science trip to Yellowstone National Park to study these high temperature organisms.

[00:59:09] **Ben:** And you're like, you don't even know. And, and, and not to get political for a second, but it, it's like you can't, there was, um,

[00:59:18] **Tim:** You can't cut funding

[00:59:19] **Ben:** you, you can't, like there was okay, so like, I don't know, maybe like 10 or 15 years ago, I don't know if it was college humor, probably it wasn't college humor, but it was, it was someone talking about.

[00:59:28] **Ben:** They made this humorous video and it was, it was these people, these like young people sitting in this apartment talking about like, oh, how terrible Jews are. And then someone was like, oh, you don't like Jews. Well then I guess you don't like televisions. And it talked about all the like components that were invented by Jewish people and the TV disappeared and they were like,

[00:59:47] **Adam:** Is this Adam ruins

[00:59:47] **Tim:** like. Yeah. It sounds like Adam

[00:59:49] **Ben:** they, that they have made, that may have been it.

[00:59:51] **Ben:** And they just went down like this huge list of things that like all had been invented by by Jewish scientists. It's the same kind of,

[00:59:57] **Adam:** the way.

[00:59:59] **Ben:** and it's the same kind of thing, but they're like, oh, we don't need the government to do all of this funding. And then you're like, oh, you like all of the stuff that's in your life?

[01:00:06] **Ben:** Well, guess what? That was funded by a government grant back in the eighties, or like, that was based on research that was funded by the government in the nineties or like that was funded by government in the sixties. Like basically everything was originally from some sort of grant that the government gave out.

[01:00:21] **Tim:** So both of those cool stories, but what does it have to do with their whole topic, Adam?

[01:00:24] **Ben:** I don't remember.

[01:00:28] **Adam:** I just wanted to go back, like we've been talking about AI stuff a lot, and I just wanted to kind of circle back and say like, while we may see a lot of slop coming out of AI right now, and it does seem to have noticeable already noticeable negative effects on people's lives, right? People have been losing jobs and, that sort of thing.

[01:00:51] **Adam:** Like you're talking about earnings calls. Yeah.I like, I don't think that that necessarily means it's not a topic worth continuing to explore and, and learn more about. I think it just, it's gonna take some maturity and discipline that, let's be frank, this country doesn't seem interested in right now, as a whole in order to do it well.

[01:01:16] **Adam:** And that's scary. But, but I do think that it's important that we continue to go down this

[01:01:21] **Tim:** Yeah. 'cause when you have a shiny new toy, you want to use it on everything. I mean, you look how, how AI actually did a huge amount of fantastic work in the AI folding,

[01:01:31] **Ben:** Yeah, the protein folding.

[01:01:33] **Adam:** Yeah.

[01:01:33] **Tim:** space, right? It went from being an almost insolvable problem to being solved.

[01:01:38] **Adam:** Yep.

[01:01:39] **Adam:** Totally

[01:01:40] **Tim:** ai. So may maybe, maybe, hopefully for our sakes and for my children's sakes, who want to go into coding that, you know, maybe the LLM and the code is not really the problem worth solving with this.

[01:01:54] **Tim:** There's other things that'd be better at, we'll see, we don't know.

[01:01:57] **Adam:**

## [01:01:57] Patreon

[01:01:57] **Adam:** Alright, well then this episode of Working Code is brought to you by the, the TV show that was better than Little House on the Prairie, which would be the Waltons, and they want me to pass on this message.

[01:02:06] **Adam:** Goodnight John Boy, and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[01:02:20] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:02:24] Thanks For Listening!

[01:02:24] **Adam:** So we have, a a couple of things here that we're gonna talk about in the after show, the, the after show. If you're uninitiated, if this is your first episode of Working Code, welcome.

[01:02:32] **Adam:** Nice to have you. the after show is basically the outros gonna play, and then for those of you that, throw a few dollars a month hour away, we're gonna keep talking. And apparently tonight we're gonna go talk about Lilo and Stitch in the theater. and, I don't know what an SP is in this context.

[01:02:47] **Adam:** somebody sent a store procedure that's hard coded to have email addresses for alerts. So, that, that's gonna be a fun conversation. but yeah, we just talk about whatever's on our minds. Sometimes it's, podcast related, sometimes it's not. Sometimes we talk about tv. Those are the fun ones I finished, we'll talk about later.

[01:03:03] **Adam:** We'll talk about later. Um,

[01:03:05] **Adam:** uh, don't get away the sauce.

[01:03:07] **Adam:** yeah, so if you want that and more, you can go to patreon.com/workingcodepod, throw a few dollars a month our way. We'll throw a few extra minutes a week of audio your way. Speaking of extra minutes of audio a week, I did want to acknowledge that we did not put out an episode last week.

[01:03:21] **Adam:** I was out of town for work and these three cretins couldn't manage to find time to get together and talk. So, uh, Life.

[01:03:28] **Tim:** Yeah.

[01:03:29] **Adam:** just to throw them under the bus. Well and truly, in case you were wondering where it went, we just didn't do one last

[01:03:34] **Tim:** Sure is, is legitimate, but all of ours, yeah, I

[01:03:36] **Tim:** get it. Okay.

[01:03:37] **Adam:** I was, I,

[01:03:38] **Tim:** how it works.

[01:03:39] **Adam:** I was working like 20 ish hours a day for four or five days in a row, like including Saturday and Sunday.

[01:03:45] **Adam:** So I have an excuse excused absence. Anyway, that's gonna do it for us this week. We'll catch you next week. And until then,

[01:03:53] **Tim:** Hey, listen guys, even if you're a three anis sloth, your heart matters.

[01:03:57] **Adam:** and matters and matters,

[01:03:59] **Tim:** Exactly. It's like a doctor who sloth.
