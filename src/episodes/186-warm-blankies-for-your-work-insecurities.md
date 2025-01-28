---
title: "186: Warm Blankies For Your Work Insecurities"
description: "In this week's episode Ben and Carol delve into their personal and professional insecurities."
date: 2024-07-10
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/186-warm-blankies-for-your-work-insecurities/id1544142288?i=1000661763218"></iframe>

In this week's episode Ben and Carol delve into their personal and professional insecurities. The discussion includes feeling the need to justify one's value at work, struggles with validations. They also talk about the emotional impact of customer interactions and the importance of human connections. The conversation highlights broader issues regarding job promotions, industry expectations, and the myth of constant innovation.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/186-warm-blankies-for-your-work-insecurities.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** And I know that maybe seems a little toxic, but when you lose touch with, with your guiding principles, I think you need to have something that. That gives you a litmus test as opposed to just like, well, what does my manager feel? just, I guess, reconnecting with my customers has been very powerful in terms of my sense of security slash insecurity.

[00:00:18] **Carol:** Yeah, that sounds wonderful in theory.

## [00:00:43] Intro

[00:00:43] **Ben:** Here we go. This is episode 186 of the working code podcast. And on today's show, we're going to be talking about work insecurities. But as usual, we will start with our triumphs and failures. And today it's just going to be Carol and myself, and I will kick us off. And,

## [00:00:59] Ben's Triumph

[00:00:59] **Ben:** I'm going to start us off with a triumph, which is that, for the last couple of months, I've been building this data bulk export system for our customers, as I've mentioned before on the show, Envision is going to be end of life at the end of 2024, and as a kind of homage to our customers and kind of a quasi,Redemption Song.

[00:01:19] **Ben:** I'm trying to build a way for some of our customers to off board their data so that they can have it for their records and do it in a, in a way where they can kind of experience the prototypes even offline, but not with the kind of same fidelity that they have online. And, some of these customers have literally thousands of prototypes that they can export.

[00:01:39] **Ben:** So. I've been building the system where they can queue documents up in the background, and then I have a background task that will churn through them and generate these zip files, and then I had to create a way for our system to talk to their S3 buckets, and I had to create a way for them to verify that their S3 buckets were set up to provide Envision access to those buckets, and it's been kind of this, Long baby step incremental approach.

[00:02:06] **Ben:** And I was super excited that on, I think it was like Tuesday or maybe Monday of this past week. I ran a full end to end demo internally of going in, setting up an S3 bucket. Adding the right bucket policy to grant Envision permissions, queuing up like 500 and something test prototypes that I've accumulated over the years, and hitting go and seeing them go into the queue in the background, and then seeing the background tasks, start to process them, and then start to see a couple hundred, items show up in my S3 bucket.

[00:02:38] **Ben:** And it was a It was just very, very rewarding to see it to actually come to fruition.

[00:02:46] **Carol:** Yeah. There, there is nothing like that feeling you get when you've been working on something and you finally hit the button and it's running and it's doing its thing, no matter how small or how big it is, it's just that sip your coffee and grin at the sun, you know, cause it's a nice day.

[00:03:04] **Ben:** Yeah, it was so good. And I was, I was really worried that asking the customers to configure an S3 bucket was going to be just really complicated, but I ended up making a demo video of how to do it and walking through and Amazon gives you a pretty generous free tier, you can have something like up to five gigabytes of data in S3 for free for the first 12 months.

[00:03:27] **Ben:** And setting up an AWS account, you know, for someone who's not in technology, I imagine it sounds daunting, but it's literally like putting your name and your email address, your credit card information, because you have to have it up front. And that's it. And then like you go into S3 and you hit create bucket and you put a bucket in and then, you have to create this, a bucket policy, but I provide the JSON that they can copy paste directly from the website.

[00:03:52] **Ben:** And in the demo video, I say, you just go in here, you click this, it gives you a blank form field, just paste this in. and it works. And I think, you know, It's, it's friction for users who wouldn't have that much data to export. But when you have, I think our biggest customer has something like 19, 000 prototypes.

[00:04:11] **Carol:** Holy

[00:04:11] **Ben:** is mind boggling.

[00:04:13] **Carol:** Yeah.

[00:04:13] **Ben:** you know, if they want to get 19, 000 prototypes out of our system, spending three minutes to set up an S3 bucket, you know what? That's not a lot of friction, actually.

[00:04:22] **Carol:** No, it's not that bad. And when you talk about prototypes, these are things that your customers are using to run their business, right? Like it's forms they use, it's workflow models, it's all of that stuff. Like it's, it's core to what they do, right?

[00:04:36] **Ben:** Right. And a lot of it, granted, is probably for historical understanding, you know, that they've also accumulated over the years. but. People love keeping records, especially I, you know, some companies have legal requirements where they have to keep records for a certain period of time. So,I dunno, I'm just happy that, that it sort of came to fruition.

[00:04:58] **Ben:** I actually had a customer reach out to me and say, Hey, I really appreciate that you're working on this, but like, why, you know, what, what's in it for you? It doesn't make any sense if the system is shutting down, why spend so much effort trying to build this bulk export? And, and I, and I had to sit and reflect on it.

[00:05:16] **Ben:** And part of it actually ties into the show. Cause part of it is a little bit just work in security. Like I'm getting paid to be here and I feel like I have to justify my time. And this felt like something I could do to justify my time. But I think more accurately or more at a deeper core, this just feels like the right thing to do, that we have all this data, it's the user's data.

[00:05:40] **Carol:** it is theirs. Yeah.

[00:05:41] **Ben:** about to be destroyed and building a way for them to keep access to it feels like the right thing to do. And it feels like I'm in some, in some small way, making up for all of the missteps and the problems that we've. You know, all of the mistakes that we've made here. And this is just my, my last chance to do something right.

[00:06:03] **Carol:** And it's appreciated. Like you said, they value it. I am, have you watched the show, The Bear?

[00:06:09] **Ben:** I love the bear. We actually, we actually, Adam and I talked about it in last week's, after show.

[00:06:14] **Carol:** I've got to catch up on the shows. I'm behind by like two months, so no spoilers. So a little spoiler to The Bear, tiny little sentence that was said that made me think of you and kind of this topic too, when you were talking about it is when you're at like a mom and pop restaurant, you Every day, you know, once a week with your family if you're in a little town, like this is normal for you to just hang out here.

[00:06:40] **Carol:** You tend to forget if the food was bad a day here or there. You always remember how the people treated you. You remember the good service you were given, you remember the conversations, you remember feeling welcomed and valued, and you can overlook some of the problems if you're treated properly. It's easier to forgive those things and just forget them when people treat you right.

[00:07:03] **Carol:** And that's what you're doing to your customers. You're letting them go with that good taste in their mouth that you've done what's right for them. Your company did the best they could for them. Going under wasn't something they planned for. Being bought out wasn't something they planned for. None of these things you expect to happen, but all you can do is, is send them on their way in the best possible way.

[00:07:23] **Carol:** And that's what you're doing by giving them this export.

[00:07:27] **Ben:** A hundred percent. And I, I love the fact that you underscore the human connection part of it, because it really is true. Human connections are so powerful. You know, We're in the middle of this teen mental health crisis and this loneliness epidemic in the United States. And study after study shows that the most meaningful things that we can do for our mental health are just build human connections.

[00:07:49] **Carol:** Agree.

[00:07:49] **Ben:** And I, I know it seems so stupid in a way to think about building connections with your customers because it's not like It's not like a friend I have over for dinner, but it is that, that kind of vitamin B12 injection that I get when I talk to a customer and they say something nice, or they say something even not nice.

[00:08:07] **Ben:** Like, you know, if it's just, we haven't, we're, we're communing and we're talking about something and we're collaborating and it's so. Subtly powerful. And, and I love it. I love it.

[00:08:17] **Carol:** Yep. I seek validation for sure. And those are really great ways for me to feel validated in what I'm doing. Just hearing my customer say, Attaboy, you know, that, that goes a long way.

[00:08:31] **Ben:** Yo, so even, even just to double down on that for a second. So I had one customer reach out to me about this bulk export and they were saying, you know, Oh, we've been using Envision for years. It's so great. We know that it's shutting down and we've been shopping around trying to find other solutions.

[00:08:47] **Ben:** And we really just haven't found anything that dovetails as well with our current workflows as Envision does. And to me, that sounds. Completely insane only because there are other huge competitors in the market, but I'm also like, Oh, that's so great. You know, part of me, it's like, F yeah. Envision was awesome.

[00:09:07] **Ben:** And I'm, and I'm, it's so validating to hear that even at the end here, there are people who, And for whatever reason, feel like it worked the best for the way that they like to think about approaching their product development.

[00:09:20] **Carol:** I love that.

[00:09:22] **Ben:** All right. So that's me. I'm going to leave it there with the triumph. Carol, what do you got going on?

## [00:09:27] Carol's Fail

[00:09:27] **Carol:** Well, since you had such a great triumph, I don't feel bad throwing in a big old failure here. So actually I'm going to go with two failures. Number one, it's monsoon season here, and that means that we get Like crazy downpours and everything floods and then weird things bloom and then you can't breathe if you have allergies.

[00:09:48] **Carol:** So that's why I'm all congested. So that's a big giant failure. I didn't know living in the desert was going to make me sick from rain. No one could have, no one could have told me that and if they would have, I wouldn't have believed them anyways. So yeah, that's,

[00:10:01] **Ben:** never heard of the, I've never heard of parts of the United States as receiving monsoons. That's interesting.

[00:10:07] **Carol:** yeah, monsoon season here is June 15th through the last day of September.

[00:10:13] **Ben:** And just for our listeners benefit, you are in Texas currently.

[00:10:15] **Carol:** Yeah, yeah. We are in, we are touching the Mexico border, so we are very South Texas. Yep. Yep. So we definitely get monsoons. Monsoons also happen in Arizona. The problem is the water has nowhere to go. The ground's really hard. It just sits on top and every, the roads flood. There's no grass to hold water anywhere.

[00:10:36] **Carol:** It's just, it's awful. So we had one last night, but afterwards I had a double rainbow that was really pretty.

[00:10:42] **Ben:** Double rainbow!

[00:10:44] **Carol:** Yeah.

[00:10:44] **Ben:** That's awesome. I, I was talking to someone just the other day who, his wife lives in Mexico, and he's like a seasonal worker, and his wife lives in Mexico, and she's just recovering from dengue fever,

[00:10:57] **Carol:** What? I didn't even know what that is.

[00:11:00] **Ben:** I don't know, it's one of those diseases that happens in other parts of the world, and, But apparently dengue fever is, is on the rise in terms of a number of cases.

[00:11:10] **Ben:** I mean, I don't know where in Mexico they live, but,

[00:11:12] **Carol:** Let's write that down so I can look it up.

[00:11:15] **Ben:** if you're on the border, I don't know if we ever get it here in the United States though.

[00:11:19] **Carol:** Well, if anyone's gonna get it, that's gonna be me with my allergies. That's the B real. So, all right, so let me go into my second big old failure here. You guys recorded Tuesday without me. I was supposed to be on the show, but. Turns out I was stuck online working way late into the night. And that was because, over the weekend we had a certificate expire.

[00:11:46] **Carol:** And suddenly it's become a realization that we don't track when certificates expire. Someone just has to know, someone has to report it, then it goes and gets updated. Well, our SA's are amazing. They do a great job. You know, we have a very

[00:12:01] **Ben:** You're what's your SA's?

[00:12:02] **Ben:** What

[00:12:03] **Carol:** SA's. Yeah. Our system, advance. Yeah. So we do a pretty good job with separation of duty.

[00:12:10] **Carol:** So I can't access the servers. I can't change certificates out. I can't really access any properties of a database. Like I could access the data, but I can't make any configuration changes. So everything has to go through multiple steps for validation so that no one can pose production. And no one can mess up a government system.

[00:12:29] **Carol:** You know, there's lots of separation. Well, our SA is amazing. They do a great job, but he went in and updated our certificates and didn't realize that the name of the certificate mattered because our deployments needed to know the name of the certificate and that in order to use a certificate, our application needs to know the thumbprint for it.

[00:12:51] **Carol:** And it needs to have the certificate. So we have a whole process to kind of go through and do that. And back in the day, it used to be a very manual process. Well, now it's just uploading it. We have an admin system where certain people have the ability to do it and it gets it in the application and we're good to go.

[00:13:09] **Carol:** Well, I didn't really know that whole process yet. So hadn't been in there, was looking around, saw kind of what was going on, went Azure Application Insights saw the error, realized the certificate was failing, got our SAs to roll back the certificate to validate that it was failing, only to find out our other agencies that are using our login had already installed the new certificate on their side.

[00:13:36] **Carol:** So when we did a restart, that certificate was gone. Now they can't log in. Oh my goodness, a day of work gone down the drain, only to just put the certificate back and do the upload process and everything worked good.

[00:13:51] **Ben:** And as far as what these certificates do, is this for like an SSL certificate for inter service communication kind of a thing?

[00:13:59] **Carol:** yeah, it just allows a handshake between, between our applications and between an external. So there's two different certificates. It's just, it's amazing. The same certificate you would see if you're at like an HTTPS site, right? It's just validating that you're good, but we have server to server internal, and then we have our agencies that use our login system. So yeah,

[00:14:18] **Ben:** the certificate stuff is super frustrating.

[00:14:21] **Carol:** it is.

[00:14:23] **Ben:** Exactly to your point, because usually what happens when it goes down, there's only a handful of people who have permissions to touch that area of the

[00:14:30] **Carol:** Yeah.

[00:14:31] **Ben:** And, and for whatever reason, and I know this is just, I feel like certificates never fail, 10 AM on a Tuesday morning, they always fail like, like 7 PM on a Saturday night or, you know, some, or like on Christmas for whatever reason, like that's just when these things, these things fail, we had the same exact thing happen to us, well, very similar.

[00:14:54] **Ben:** So. We use Cloudflare as our content delivery network. And generally speaking, it's just like the outer edge of our network. Cause we have some Cloudflare workers and stuff. And I only just learned this, that part of what we do, or part of how Cloudflare works, is it, we have it set up to rotate.

[00:15:13] **Ben:** Certificates because it has to have a secure connection between the CloudFlare Edge and our origin servers. And it does that over an SSL connection. And it does that, I think, through some sort of like self signed certificates. So it has to, on a regular basis, install certificates onto our system so that it can maintain the secure connection.

[00:15:35] **Ben:** And for whatever reason, that automated process just timed out one day.

[00:15:39] **Carol:** Oh, no.

[00:15:40] **Ben:** And then all of a sudden, all of the traffic just started getting blocked between Cloudflare and our origin servers. And it was also one of those things where we're looking around and we're like, literally no one here in the room today has access to this or knows even where this is happening.

[00:15:55] **Ben:** And then the one, we call them SREs, our site reliability engineers. Like the one guy who knew how to do it, we were paging him, and he is in Argentina, and like just, you know, wasn't around for the day. So I mean, we were down for like, like seven or eight hours. Oh, so frustrating.

[00:16:15] **Carol:** Well, so like two things happen in conjunction with that. We use Akamai. So Akamai then started blocking our traffic because they didn't want to get denial of service. So they start blocking it. So then we don't even really know how bad it is because things are just not coming in anymore for us to see in my logs.

[00:16:32] **Carol:** It wasn't until we looked at the Akamai logs that we're like, Oh, there's lots being blocked. and then once we finally got everything back on, because we got it back on at 3, around 3pm, your time, eastern time, there's a lot of users in the system, and there's a lot of database traffic that was backed up.

[00:16:50] **Carol:** So we're sitting there going, oh gosh, every time we get this right, The databases all of a sudden spiked a hundred percent CPU utilization. So we're like, what the hell do we do right now? So we kept going and going and going. Finally, a couple of restarts and everyone went offline and it stabilized again.

[00:17:08] **Ben:** Oh man. Yeah. That's the, the classic thundering herd

[00:17:11] **Carol:** Yeah. I was like, oh my gosh. So a day lost. Lessons learned and, documentation will now be created on both sides of the house for how this process works, because again, the search don't expire for another five years. So

[00:17:26] **Ben:** exactly.

[00:17:27] **Carol:** unless something happens and we need to replace it for another reason. We won't remember this was a problem in five years and who knows if the same people will be here.

[00:17:35] **Carol:** I change jobs often. Who knows, you know? Oh,

[00:17:39] **Ben:** Oh man, it's

[00:17:40] **Carol:** stuff.

[00:17:41]

## [00:17:41] Work Insecurities

[00:17:41] **Ben:** So where can securities, I guess, I guess, let me kick this off by saying who are you and what do you know about anything?

[00:17:50] **Carol:** right. Where's my blankie, Ben? I just need to like bundle up while we have this conversation.

## [00:17:56] Validation

[00:17:56] **Carol:** So like I kind of mentioned to you earlier when we were talking about this topic, I am struggling a little at work because I don't know my value. I don't know how I'm providing anything for my application other than writing a little bit of code.

[00:18:12] **Carol:** And I'm not even getting a ton out because I'm working on this one project. I can jump in and look at things here and there, but there's no real validation that I'm doing a good job. And I don't want to go to my supervisor and be like, Hey, buddy, can you just, you know, pat me on the shoulder and tell me I'm doing good?

[00:18:28] **Carol:** Cause I need that. Cause I don't want to sound whiny about it. I just, I need to know. What the goal is, like, I need a clear, almost checklist that says, here's how, you know, you're doing good. And I don't think that really exists for adults in the world. It's not like my toddler, you know, I could be like, Hey, did you put your socks on great job, gold star, you know, do your shoes match amazing work.

[00:18:54] **Carol:** This is straight up like, I bringing in money? Yes. Are customers happy? Yes. But what am I doing?

[00:19:03] **Ben:** Yo, absolutely. And I think this has always been the hardest part for me, if I ever thought about moving from a individual contributor position into more of a management position. Cause at least when I'm writing code, can convince myself that I'm doing something valuable because there is a physical, so to speak, output from my time.

[00:19:25] **Ben:** But when I think about managing people. It's all theoretical and the, the lag time between the changes that you implement at work and the return on investment for those changes is, is much larger. It's not like I wrote code, the code's there. I push a production and now I can see database performance change or, you know, endpoint activity change.

[00:19:46] **Ben:** It's like, are the one on ones that I'm doing right now affect, employee retention over the next two years? And that's a lot of just. Hand wringing and questioning in my mind. And I don't even do these things. It's like just the thought of having to do these things fills me with so much anxiety. Yeah.

[00:20:11] **Carol:** when you push it, you think it's going good and there's no change in production. Like it looked great in your local, but nothing got better. Then I just feel frustrated that maybe I'm not doing a good enough job.

[00:20:23] **Carol:** Or right now, kind of like what I'm dealing with is I did all this local development. I don't think I've told you, I have an engineering team now. Yay. I have people on my team, so I can't get my code to them because I don't know how to push to NuGet. And in order for them to run my code, they need to update two packages.

[00:20:45] **Carol:** So Monday, I have a meeting with another architect to explain to me how we get our packages in NuGet. Because I don't know, I've never done this, and the build doesn't do it automatically. So I'm like, if it's not in a build step to publish a package, Or any way for me to upload it, how do I get it up there so someone can go download it?

[00:21:03] **Carol:** Like this, this is not working in my head. So the two days of trying to figure that out, only to find out I can't figure it out and someone's gonna have to help me do it.

[00:21:13] **Ben:** Now, now Nougat is a package manager,

[00:21:15] **Carol:** It is, yeah.

[00:21:16] **Ben:** but you guys must have like a privately hosted.

[00:21:19] **Carol:** Mm hmm. Yeah, we use ProGet. Yeah, ProGet does like our corporate one, so that's where all the government, our government packages are in ProGet. And you, that's by login, obviously. You can't just get to the

[00:21:30] **Ben:** Do government agencies share packages or, or it's just interesting.

[00:21:35] **Carol:** Yep, so we have like some design system stuff that we use. I'm trying to think of any other. We have some login ones. I can't think of any more off the top of my head. Most of ours are in, in our own, like, agency.

[00:21:49] **Ben:** Hmm.

[00:21:49]

## [00:21:49] Keeping Customer Needs in Mind

[00:21:49] **Ben:** Over the years, I think earlier on in my career, I was super customer focused and always thinking about what problem I'm trying to solve for the customer. And then I think when I started working at Envision, we were still very much that customer centric, customer focused, View on the world. But then as the company grew, I kind of lost touch with the customers and I stopped thinking about what am I doing for the customer and more about what am I doing for the company and what does the company want me to do and am I living up to my job title and are my teammates getting value from what I'm doing?

[00:22:28] **Ben:** And when I stopped thinking about the customer, I think I lost my, my, my true north, so to

[00:22:35] **Carol:** Oh, yeah.

[00:22:36] **Ben:** And it was only in the last couple of years where I have now circled back and, and reconnected with the customer and the customer needs, and that has. In a way, removed a lot of the insecurities that I was having for a long time because it was, everything could always roll up to the customer.

[00:22:56] **Ben:** I, if I ever had to stop and think to myself, am I doing the right thing? I could ask, is this going to solve a problem for my customer? Or is this going to remove a friction for my customer? And as long as I could say yes to that, I feel like I, I was justified in what I was doing almost regardless of what the people around me felt.

[00:23:19] **Ben:** And I know that maybe seems a little toxic, but when you lose touch with, with your guiding principles, I think you need to have something that. That gives you a litmus test as opposed to just like, well, what does my manager feel? And as somebody, I know I'm talking to a manager here, so that's probably not the right thing to say, but, just, I guess, reconnecting with my customers has been very powerful in terms of my sense of security slash insecurity.

[00:23:45] **Carol:** Yeah, that sounds wonderful in theory.

[00:23:49] **Ben:** Now, but a customer doesn't have to be someone who's paying for a service. You know, a customer could be. The people in the next department and I'm building this thing for them and I can commune with them and understand what they're trying to do, you know, that's, that to me is just as much customer as is the, you know, Joe Bob public who sign up for an account and give me a credit card.

[00:24:10] **Carol:** yeah. See, I see customers, anyone who uses the system,

[00:24:13] **Ben:** Right,

[00:24:14] **Carol:** but I guess in reality, that could also extend to anyone who you have impact on throughout your day. Like it's not just the users of your system, but like you said, the other departments who you may be able to help. Like our SA's document how to rotate certificates and name them correctly.

[00:24:31] **Carol:** It gives them the right context so we don't have another day lost due to cert errors.

## [00:24:36] Innovating

[00:24:36] **Ben:** I think as an industry, we have done ourselves a disservice by taking the notion of innovation, And creating this mythology around it where innovation is so powerful and it's what changes markets and it's what changes business verticals. And I think the reality is, is that 99 percent of the work that we do Isn't innovative and it doesn't have to be innovated.

[00:25:02] **Ben:** It has to be like, Oh, the user, it takes three clicks to perform this task and it could only take one. And now I'm going to spend a week moving it from three clicks to one click. And that's not innovative, but it's going to be really powerful for the people who use the system. And I think because we have put this notion of innovation on such a high pedestal, anytime we're doing something that doesn't feel revolutionary and innovative, makes sense.

[00:25:30] **Ben:** People feel like they're wasting their time or they're not living up to their potential. I think that's just super detrimental.

[00:25:36] **Carol:** Oh man. I just had this conversation. Just had this conversation. I feel like as I've gotten older, I no longer have that drive that I used to have to just do everything new and fancy. And like you said, the innovation's still there a little, but I really want to take what I have and make it solid. And I want to keep growing a great foundation for what other people can, can use.

[00:26:03] **Carol:** Right. And I know like my kids in college, right? He's coming out with a great degree and he wants to innovate. He wants to be the next big designer for quantum computing. You know, he is, he's going to do great things. I feel like so many people are coming behind me that now need a solid foundation to innovate, that it's my job at where I am in my career.

[00:26:25] **Carol:** To build a ground for them to, to do that, which means maybe I do keep maintaining so other people can innovate. My brain's not there now, you know, my brain's not as quick as a 21-year-old. Like, I can talk through problems with you and I can, you know, troubleshoot anything, but I'll create a solid, solid foundation so you have somewhere to do some really cool, innovative work, and I'm okay with that.

[00:26:51] **Ben:** Yo, I'll tell you, it, it has taken me a long time come to grips with the fact that I'm not a genius and I know that sounds like a really weird statement to say out loud, but I think part of this mythology around innovation, I always in a way wanted to be that person who came up with some sort of breakthrough idea or created a library that, you know, gets used by a hundred thousand developers or something like that in.

[00:27:18] **Ben:** And I'm, and I'm just not that person. And I don't think that that's the way I think. I'm, I'm much more a, how do I use the tools in front of me to get work done? And not, how do I completely rethink the way work gets done, period, kind of a person. And. I'm still in the process of becoming more comfortable with that person, but the more I embrace it, the more I'm kind of enjoying the work that I'm doing. And then again, you know, I, going back to the customer, I keep trying to hold that customer front and center of my mind and think to myself, am I doing something right for the customer? If I am, it doesn't have to be innovative. It just has to be the right thing to do. And I'm, I'm becoming more comfortable with that concept.

[00:28:04] **Carol:** You know how you said create the package or create the library that you know, 100, 000 people use every day and in their tools. For me, I guess this is one area that I don't have any insecurities and I know that if one person gets joy or can learn from something I've done, I'm happy. I am so happy. It definitely doesn't have to be some big grand thing.

[00:28:29] **Carol:** Whenever I teach someone something at work and they just say, thank you. I'm like, again, I'm at that moment where I'm sipping my coffee, looking at the side, just being happy because I help someone. I help someone. And for me at my core, helping people is just kind of like my nature. It's. I'll do whatever, like I'm a caregiver.

[00:28:47] **Carol:** I'm a, I nurture usually, like that's where I grow at. So anytime I have the opportunity to help someone and not having a team for so long, I haven't had that. My opportunities to help, like I would, I'd volunteer. I'd be like, Hey guys, to the other architects. I'm like, Hey guys, do you guys need help with this?

[00:29:06] **Carol:** So like, no, I take hours just to explain where we're at with it. So we're just going to keep going. I'm like, okay, fine. Like, I'm going to go mope away sad that I don't get to help someone today.

[00:29:18] **Ben:** Well, that's why I get so much pleasure out of writing. Cause I, I mean, I half, half of my writing I do for myself, but definitely half of it I do because I'm hoping that it helps someone and someone every now and then will drop by and say, Hey, great. This was exactly what I was looking for. And I'm like, ah, yes.

[00:29:33] **Ben:** And now ChatGPT is taking that all away from me, but whatever. No worries.

[00:29:37] **Carol:** just let it steal your stuff and then you get credit, right? So I will tell you, when I was writing ColdFusion, your stuff helped me tremendously.

[00:29:48] **Ben:** Well, thank you. That's very nice.

[00:29:50] **Carol:** Yes, I will go to it as much anymore because I'm not writing cf, but I will go to it every now and then and look for just theory things like, oh, how do you do this in cf?

[00:29:59] **Carol:** Because if I can remember how to do in cf, I can adapt it to what I'm doing now, because still in my head, CF is the easiest language I've ever written.

[00:30:08] **Ben:** It's so easy. It's so great. I, it drives me crazy when, I don't know, people hate on it. It feels, it seems, yeah. Adam, what are you doing?

[00:30:17] **Carol:** why Adam? Why bad Adam?

[00:30:19] **Ben:** Bad Adam.

[00:30:22] **Carol:** Yeah, definitely. No, you're, you definitely were a huge help to me. And starting out early, learning it, I went to your site often. You didn't even know me then. And I was like, Ooh, this Ben guy, he's so cool. He's my hero.

[00:30:36] **Ben:** Well, I appreciate that,

[00:30:38] **Carol:** Yeah.

[00:30:39] **Ben:** but

## [00:30:40] Insecurity from Change

[00:30:40] **Ben:** I don't know. I also feel so much insecurity just because so much stuff is changing all the time now

[00:30:46] **Carol:** Mm hmm.

[00:30:46] **Ben:** and Even when I don't need those things to get my work done, it feels, I feel insecure that I don't know them anyhow. And it's, it's a, it's such a, it's such a hard insecurity to deal with because. get good at the things that you do a lot, and you get good at the things that you practice. And if I were to take time to just dabble in something, I don't even know if it would do anything to ease my insecurities. It would do something to ease the, I don't know anything about this, and maybe I can know thing one about it after doing some research, but it wouldn't really satisfy the, I don't actually know how to do that.

[00:31:27] **Ben:** To use that technology to any productive ends, because it's not something that I'm going to do every day.

[00:31:33] **Carol:** Completely agree. I struggle with the wanting to learn something if I'm not going to use it, because then I'm just going to be angry that I can't go deeper in it. Cause I really have to keep my. Well, this is, they say, like, keep my knife sharp or keep my tool belt strong for what I'm doing. Like I have to make sure what I do for my job is the focus of what I'm learning so that I can keep Making that application better and that my customers are, you know, getting the best quality I can provide them.

[00:32:00] **Carol:** So to just go learn something completely new off the rails that isn't gonna apply to my everyday feels like space I'm just going to take up in my brain that I shouldn't. It feels like I'm cheating someone along the way. You

[00:32:13] **Ben:** more I think about it, the more I come to the conclusion that you can't even really learn how to do anything until you are required to do it at work. And then part of me is also insecure that that's just a cop out. That, oh, now you're just justifying it. Not spending a whole lot of extra time learning other stuff, but I, I don't think that's true because you really need that to build up that muscle memory and not only to build up the muscle memory to run into all the weird edge cases and the problems, you know, it's one thing to do 12 sample apps that all follow the happy path.

[00:32:51] **Ben:** But then to not have any idea how to cope with the sad path that happened constantly. And the moment anything makes contact with a customer and they don't know how to use it, or they're using it wrong, or, you know, a certificate expires. And now what? I don't know. I just, you know, it used to be, there was so few technologies, relatively speaking, that you did kind of use all of them at work,

[00:33:16] **Carol:** Yeah. Yeah.

[00:33:17] **Ben:** you know?

[00:33:18] **Carol:** agree. You got to keep your, your fingers in a little bit of all of it. Now there's so many.

[00:33:23] **Ben:** Yeah. And it's,

[00:33:24] **Carol:** many, people tell me things that they know, I haven't even heard of them. I was like, is this like a brand new thing? And they're like, yeah, like it's been out like five years. I'm like, how did I not know about this thing?

[00:33:36] **Carol:** Sometimes you and Adam talk about something and I'm like, I need to go look that up because I'm so in my NET, straight on, only the script languages, like mindset. Then I'm like,

[00:33:48] **Ben:** half the stuff I say is just regurgitating what I've heard on other podcasts.

[00:33:52] **Carol:** I love it. I love it.

## [00:33:55] Happy Paths

[00:33:55] **Carol:** So a little, can I do a little side tangent here?

[00:33:57] **Ben:** tangent away.

[00:33:58] **Carol:** Cool. You talked about happy path. I just had a BA meet with me, who I love, my favorite BA. He's

[00:34:05] **Ben:** is a business analyst.

[00:34:07] **Carol:** analysts. Yeah, they're the ones that write our story, write our acceptance criteria, do a lot of our testing. Like, they're just amazing.

[00:34:14] **Carol:** They are like what keep, what keep our development flowing. So they keep work coming in and they get it out the door. So I just met with one of our BAs and we were looking at some of the stories we have and making sure that they're ready for the other engineers to pick up and work. And We got to one and he was like, we're just going to worry about HappyPath.

[00:34:32] **Carol:** I was like, you mean HappyPath as whatever the application does, it's just going to do? And he's like, yeah, I guess so. I guess that's HappyPath. I'm like, well, can we talk about what the HappyPath is? So he and I chat and ultimately HappyPath is when we hit save, whatever you have the application doing right now.

[00:34:50] **Carol:** Is the happy path. I was like, so what's the unhappy path? Well, yeah, yeah. The unhappy path is we'll figure it out when we start testing.

[00:35:00] **Ben:** Yo,

[00:35:01] **Carol:** I was like, that's legit. I mean, sometimes you don't know what, what is unhappy. Sure. Like. You put in the wrong type of data, that's easy to validate. You put in too much data, like, you don't give us enough information.

[00:35:12] **Carol:** There are some easy things there to validate, but what are other unhappy things? Like, can you have duplicates of data? Can you not have duplicates of data? Like, are there unique constraints for things? Those are the type of stuff that will figure out the unhappy path after they start testing. And I was like, you know what?

[00:35:29] **Carol:** I was like, I really like that way of thinking. I don't want to have to design the whole thing pre and then figure it out. Let's just do the smallest amount we can and iterate, continuously iterate on it. Like that's how we keep things moving and that's how you don't burn people out. Cause if you give me a story with a hundred unhappy paths, I have to check.

[00:35:47] **Carol:** like just start with a try catch. And make sure that you're logging whatever you catch in your catch block. And then, then code the happy path. And then you're at, you know, at the very least. You're going to know when something bad happens and you're going to be able to iterate it on it later.

[00:36:04] **Carol:** yeah. Completely agree. Yeah.

[00:36:06] **Ben:** You know, just speaking about sad paths and had paths. So I was considering talking about this in the triumphs and fails, but I've been spending way too much time thinking about code that takes two data structures in CodeFusion and compares them just to say, are these the same data structures?

[00:36:23] **Carol:** Okay. Big data structures.

[00:36:25] **Ben:** like, like nested objects kind of stuff.

[00:36:28] **Carol:** Okay. So the data and the, the like model for it.

[00:36:31] **Ben:** yeah. So, and, and the issue is. This is in CodeFusion and CodeFusion is a fairly. Loosely typed, dynamically typed language. I don't quite understand the difference between loosely typed and dynamically typed off the top of my head, but you know, you could have a variable that is a string in one moment and a number in the next moment, or you could have this, you could have the string, yes.

[00:36:53] **Ben:** And you could have the Boolean true. And you can compare those two when they're the same thing.

[00:36:58] **Carol:** That's so bizarre now that I've went to type languages.

[00:37:01] **Ben:** exactly. So there's probably, I would imagine in, in C sharp, there's probably native, are these two objects equal? I mean, at least in Java, there's like every object has an equals to, and then they have a bunch of utility classes for saying these two nested structures are equal and it, and it does this like based on all these hash codes of things.

[00:37:22] **Ben:** But the problem is, is that. At least in Java, the int for 12 and the double for 12 are two different things and have two different hash codes. So from a Java perspective, they're not the same thing.but from a ColdFusion perspective, there's a difference between an int and a double and a float and, and just

[00:37:42] **Carol:** It's all basically a number. Yeah.

[00:37:44] **Ben:** So circling back to this happy path, sad path thing, I don't even know what the sad paths are because it's so completely random sometimes how ColdFusion represents these values. And I was doing some testing and I had my happy path working. And then all of a sudden I hit a sad path where it was taking these two values and saying that these were not actually the same, but they were clearly the same.

[00:38:06] **Ben:** And I started dumping out, metadata about the data that I was looking. And then suddenly some number that I was typing in was being represented as a Java big decimal, which is a totally separate type of class. I'm like, I didn't even know that was going to come up. And now I have to have an edge case that deals with that.

[00:38:22] **Ben:** And I, I don't know, I don't exactly know where I'm going with this thought other than to say, I know that there are edge cases where it can fail, but I don't even know what those are. So they're hard to define and you kind of just have to get your sad path in place and start iterating until you find all the, the, the sad, or get your happy path in place and then just keep iterating until you start finding more and more sad paths and then yeah, dealing with them, continue testing, hit a sad path, deal with it, and then continue iterating.

[00:38:51] **Ben:** So.

[00:38:52] **Carol:** you just have to follow up, you have to be, proactive and following up on those errors and following up on, on the SAD path and not move on to something else just super quick.

[00:39:02] **Ben:** Yeah. All right.

[00:39:03] **Carol:** your story reminds me of a few episodes back when I had the unit test failing and couldn't figure out what was going on because, you know, type language, int long, not the same, even though they both are three.

[00:39:15] **Carol:** It failed, failed, failed. I was like, what do you mean? It's three. You expect three. It's three. I see three. It's three. No, int, not same as long.

[00:39:27] **Ben:** it's so frustrating.

[00:39:28] **Carol:** I'm like, is number? Yes. Is number, same number? Yes. Done.

[00:39:34] **Ben:** It's really,

[00:39:35] **Carol:** simple.

[00:39:36] **Ben:** it's hard to think about normalizing data because, Especially when you want, say, like, the string of 12 to not be the same as the number 12. So, if

[00:39:49] **Carol:** Explain that.

[00:39:50] **Ben:** like, like, in ColdFusion, if you have a string with the digits 1, 2, it's the same as the number 12, essentially. Not the same, but like, if you say,

[00:39:59] **Carol:** It can evaluate the same.

[00:40:01] **Ben:** the same.

[00:40:02] **Ben:** but then, You think, well, how do I come up with a representation that says this value is different than this value? And then you have to start to normalize numbers, but then you can run into these weird edge cases where in your normalization, you accidentally make two numbers equal that are not supposed to be equal.

[00:40:17] **Ben:** I don't know. I mean, it's hard to mouth blog as they say this, this concept, but it's just. It's hard to, it's like you, every time I go to fix an edge case, I feel like I probably just broke a previous, like I just added a regression to something that I had fixed the, the, you know, the last sad path.

[00:40:36] **Carol:** So true. So true. In this code that I just recently did, there are three different blocks of main application code I changed with it because I realized it was never written to, to expect the database to be using this data at the same time. So it was written to be ran in. Parallel is at the same time, or is that one after the other?

[00:40:59] **Carol:** Parallel is at the same time,

[00:41:00] **Ben:** Yeah. Yeah. I think

[00:41:01] **Carol:** So it wasn't expecting it to be random parallel. So it was expecting if I queried the database, no one else was going to query this again for this exact same record until this one finished because it was in a loop. Right? So it was like, go get one, go get two. So it changed.

[00:41:13] **Carol:** I was like, why are we getting all this data? I just want to know if the data exists. So I'm just going to get, if there is a record. We don't need to insert anything new. We're done, right? But because I'm so terrified of breaking why someone may have put that there, the thing I never do, but I did, I put a comment explaining like why I changed it.

[00:41:34] **Carol:** I even left the old code, commented out so they could see what it looked like before, because I'm so worried that someone's going to come behind and go. This was working, it was inserting fine, now it's not, and we don't know why, and like, at least now you have a big block. Granted, I have a note to go take it out in a few months if no errors happen, but I'm so worried that I'm just not gonna get something and that I'm gonna fix one thing only to break two things that were done previously. Scares me.

[00:42:02] **Ben:** I, and to me, that's the perfect place for a comment when you're really nervous about something and you want to say why you changed it. I think that makes total sense. I know. So we talked about comments a couple of episodes ago and, and, I dunno, I'm just a fan of comments most of the time.

[00:42:18] **Carol:** I don't know. I, I like being able to easily see when something big happened. If I have to go, Oh, it's here, but now I have to go annotate or do a get blame on it and even with get blame, like maybe it was changed twice and now I only see the one, so I still have to kind of go back a bit. It's a lot easier if there's a small comment that's like, Hey, I updated this.

[00:42:40] **Carol:** I know it's a big change or, you know, it could cause a problem, but you know, here it is.

## [00:42:45] Not My Job Syndrome

[00:42:45] **Ben:** You know, so circling back to insecurities again for a second though, another insecurity that I always have at work is kind of a not my job syndrome. Where something will come up and let's make it concrete. So someone had posted something on Facebook the other day about some open SSL or no open SSH vulnerability, some zero day vulnerability that was just reported, not to us, but generally out in the wild.

[00:43:17] **Ben:** And. We have a guy at work who does security stuff. That's his job. And I took this article and I posted it in the security chat room at work. And I said, Hey, I just saw this. Is this a thing that we should be worried about? And just doing that made me feel kind of crappy because part of me. Says that's this guy's job.

[00:43:41] **Ben:** He's the security expert. He's the one who should read up on this and weigh in on whether or not this is relevant to the company. But the other half of me is like, why are you foisting work on someone? Like you should read the article. You should build a better understanding of the security implications of what's been exposed.

[00:44:00] **Ben:** You should do some thinking about how it pertains to the company and you shouldn't just defer to other people. But I'm like, that's. That's not a good use of my time. Like I'm not the security guy. That's why we have a security guy. But I, I, I, I wr I wrestle all the time in my head with feeling comfortable deferring to people who have more domain expertise.

[00:44:25] **Carol:** So I'll go back to something you said earlier about building those connections and having human connections. Whenever you make a post like that, maybe try to think of it as a way to just build a connection with someone and have a conversation.

[00:44:38] **Ben:** Hmm.

[00:44:39] **Carol:** Like, Hey, I saw this article. Can you talk to me about it?

[00:44:42] **Carol:** Like, do you think this is something we have going on? Like, is it something we could chat about? Cause then you do broaden your knowledge a little bit outside of what you do. You don't have to dive deep into it, but you get a little more understanding and you get to then socialize with someone that maybe 364 days a year, you don't socialize with until this one vulnerability comes out.

[00:45:05] **Ben:** No, that's true. It's a good way to build up bonds.

## [00:45:08] Promotions

[00:45:08] **Ben:** If I can add another layer of insecurity to it

[00:45:11] **Carol:** Yeah.

[00:45:12] **Ben:** when I often hear people talk about promotions. They'll say things like, you get promoted to the job you're already doing, not the job you want. And by that, what people mean is, if you want to have a job with more responsibilities, you just go and start doing those things. then eventually you get recognized for doing them, and they're like, oh, you can, you're capable of this job now, so you should just get to do this job. So,

[00:45:37] **Carol:** a struggle.

[00:45:38] **Ben:** Yeah, so, so then part of me is like, I, I mean clearly not clearly, but the, the insecure part of me is always, this is what people expect. That if you wanna excel at a company, you just have to start doing the things that are almost not even your responsibility again.

[00:45:53] **Ben:** Like, that's not my job, and I have, I have plenty of other stuff I should be doing. Not the, it, it, it's like sometimes I think that that messages like that are geared somehow to people who don't already have enough to do.

[00:46:07] **Carol:** Yeah.

[00:46:07] **Ben:** already have too much to do,

[00:46:09] **Carol:** it's, I think that's, okay. So if you were talking about someone coming in as day one out of school, right? So say they've been hired at a level of number five and the levels of engineers in your company are like a five to a 10, five being junior, 10 being the highest. So you're like, Oh, you came in as a five.

[00:46:27] **Carol:** You're now working as a five, but to get to a six, there, there are things you need to learn. Like in order to do a six job, like you need to understand some of these things. And once you understand them, then you can be promoted. But when we're talking about like a level 10, which is senior engineer becoming like super duper senior engineer, then I don't think that's right.

[00:46:45] **Carol:** I think it's you should just take the people that are doing the best that they can, and they're making your company great. And you just promote them because you see what they're capable of at their current position. Like, we're not talking about those junior people who are just trying to figure out what CSS is, and how you change colors, or how you write some simple JavaScript stuff, we're talking about the people who keep your application running.

[00:47:08] **Carol:** Like, do they keep it running? Can they get it back online? What more do you need them to learn to be promoted? They should do their job great, and you should keep promoting them to keep them. Not make them go learn security things. You have a guy for that. Let him do his job.

[00:47:22] **Ben:** I'll tell you, the more we talk about this, the more angry that statement makes me about

[00:47:27] **Carol:** bad. Yeah.

[00:47:28] **Ben:** because it, like, I'm going to, I'm going to make a blanket statement.nobody is getting all of their work done, just like period. Like that's, that is not possible. No one gets to the end of the day and they're like, well, everything on my to do list is done.

[00:47:42] **Ben:** So the idea that you're going to take someone who is already not getting their work done and then say, and they've taken it upon themselves to take on all these extra responsibilities, I'm like, you know what, you're now doing a crappier job of the job you were supposed to be doing. Why would we promote you?

[00:48:01] **Ben:** I don't know. Now, now it just makes me angry that the more I think about it.

[00:48:04] **Carol:** Yeah. It makes me angry too. If you want me to take on more responsibilities, you got to take some responsibilities off my plate first. Like you've given me a job to do with a lot of responsibilities already, and those are what I'm going to do well. And that's what I'm going to focus on. If you need me to do more for the company, that's great.

[00:48:21] **Carol:** You need to tell me that, and we need to talk about what responsibilities are changing.

[00:48:26] **Ben:** I think it'd be fun. I would love to revisit that statement. The, the, you get hired for the job you're already, or you get promoted to the position you're already doing. when we have all four people on the show, I want to, I want to revisit that because now it's just making me angry.

[00:48:40] **Carol:** Topic ideas going in the sheet. Okay.

[00:48:42] **Ben:** Oh, all right.

[00:48:44] **Ben:** Anything else you want to talk about in terms of insecurities?

[00:48:47] **Carol:** I like my blankie. That's okay, Ben.

[00:48:51] **Ben:** You're doing a great job, Carol.

[00:48:53] **Carol:** Thank you, and so are you, Ben. I'm proud

[00:48:55] **Ben:** you very much. We are awesome.

[00:48:59] **Carol:** All right, well, I hope that this helps someone along the way with their insecurities, and I think we're going to call it there.

## [00:49:06] Patreon

[00:49:06] **Carol:** This episode of Working Code was brought to you by soft, warm blankies that keep you secure when your job is giving you some insecurities. And listeners like you, of course. If you're enjoying the show and you wanna make sure we can keep putting more of whatever this is out to the universe, you should consider supporting us on Patreon.

[00:49:23] **Carol:** Our Patreons cover, our recording, editing, internship, transcription costs I can't read today, Ben and my nose is very congested and we can't do it every week without them. And a special thanks goes to our top Patreons Monte and Giancarlo.

## [00:49:39] Thanks for Listening!

[00:49:39] **Carol:** We're going to skip the after show since it's just Ben and I, and we will catch up when the other guys get back on here, and we'll do a few more with you guys.

[00:49:47] **Carol:** If you want to help us out, I suggest that you tell a friend about us, have them listen to the show, and if you like what you're hearing, you can leave us a review at workingcode. dev slash review. That's it for this week, we'll catch you next week, and until then,

[00:50:00] **Ben:** Remember folks, your heart matters, even if you don't think you

[00:50:06] **Carol:** aww, love you guys!

[00:50:08] **Ben:** matter. Love y'all.
