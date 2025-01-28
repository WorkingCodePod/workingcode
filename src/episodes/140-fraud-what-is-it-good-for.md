---
title: "140: Fraud, What is it Good For?"
description: "On today's show, we share our own war stories about detecting, preventing, and dealing with the aftermath of fraud on our own web-facing applications."
date: 2023-08-16
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/140-fraud-what-is-it-good-for/id1544142288?i=1000624634875"></iframe>

If a property is exposed on the internet, people will try to take advantage of it. This might be in the form of sending spam through a communications portal, scamming cellular providers via SMS tolling, or using payment forms to validate stolen credit cards. And that's just to name a few possible attack vectors! It appears there's no hurdle too high nor process too tedious for the fraudsters to circumvent. On today's show, we share our own war stories about detecting, preventing, and dealing with the aftermath of fraud on our own web-facing applications.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/140-fraud-what-is-it-good-for.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** Yeah. Isn't AI and large language models, isn't, isn't that supposed to solve all this for us? I mean, I guess the

[00:00:05] **Tim:** It's going to solve everything.

[00:00:06] **Ben:** using a lot of fraud detection, AI

[00:00:08] **Adam:** Ask ChatGPT how we can fix this problem.

[00:00:10] **Tim:** Yeah.

[00:00:11] **Ben:** Can I just pipe people's credit cards into chat GPT and ask if it's valid?

[00:00:15] **Adam:** this legit?

[00:00:16] **Tim:** It's just legit.

## [00:00:17] Intro

[00:00:17] **Adam:** Okay, here we go. It is show number 140 and on today's show, we're going to talk about fraud. Huh. What is it good for? I don't know. Was that a good enough intro?

[00:00:46] **Ben:** I say, go with it.

[00:00:47] **Adam:** Okay, cool. Well, that's what we're going to do. as you might be able to tell, it's just myself and Ben tonight.

[00:00:52] **Adam:** there's a particularly bad thunderstorm going through the South right now. So Tim has no power. Carol's not able to make it. So we may get one or more of them. some point in the middle of the show, but, as we say here in the podcast minds, the show must go on. so, before we get to, fraud stuff, discussions on credit card fraud, we'll start with our triumphs and fails.

[00:01:14] **Adam:** Obviously, Carol and Tim aren't here to participate. It would be Carol's turn to go first, but, gotta go with, the usual flow. So, I guess now it's my turn to go first.

## [00:01:23] Adam's Triumph

[00:01:23] **Adam:** and I'm going to start us off with a triumph. we have discussed in the past my, my team's long term, project to migrate away from pets and toward cattle, and we're not, we're not fully off of pets yet, right?

[00:01:39] **Adam:** So the, I guess I have to explain that. Cattle and pets, when you're talking about like, DevOps or just like infrastructure a pet is, you know, you, you have this, like, you can think of before, in the days before AWS, you had a server and you could like go touch it and you gave it a name like Homer or, you know, or, you know, like Maggie or like, you know, everybody had a theme, whether it was Simpsons or, or whatever.

[00:02:03] **Adam:** and so, you could go touch the server and it had a name and stuff like that. And, and so. When there was an issue, you'd say, Oh, you know, Homer is offline again, sort of thing. That is a pet, right? You can, you, you can go pick that one versus cattle, which is like, I am a cattle farmer. I've got, you know, 800 steer that, that we're growing.

[00:02:25] **Adam:** Right, and, and I don't necessarily know one from the other, and so when, in a DevOps discussion, cattle versus pets, you know, EC2 instance that like has a name and it's this one, you might shut it down and turn it back on if it's QA to save, you know, like if you're not using it, turn it off sort of thing, but it's the same instance, right?

[00:02:46] **Adam:** You shut it down, you turn it back on, it's going to have The little, you know, tweaks that you made, the, the desktop wallpaper you changed or whatever is still going to be there, right? Versus a cattle, which is like, here's my Docker container, create a new instance. Okay, we don't need it anymore. Throw it away.

[00:03:03] **Adam:** Next time I need it, we'll create it again from, from source, basically. that's cattle. So we This week, shutdown, as a matter of fact, this makes me happy too. It happened while I was on vacation, while two of us were on vacation. So we had, one of my co workers was on vacation for the entire week.

[00:03:20] **Adam:** I took off on Thursday and Friday to go camping with my family long weekend. And I think on Friday afternoon, my one remaining full time engineer co worker and our other part time Halftime engineer, halftime CEO, decided to go ahead and pull the plug on that EC2 instance and switch it over to be a container.

[00:03:39] **Adam:** And so now our entire platform is either like lambdas or containers. stuff like that. It's all, it's all,

[00:03:45] **Ben:** very exciting.

[00:03:47] **Adam:** you know, maybe easily identifiable cattle, right? We're not fully at like infrastructure as code, interchangeable instances, right? We still, we still have like a container dedicated to customer XYZ to Benz

[00:04:01] **Ben:** Well, I think the huge part when I think of pets versus cattle, what I think about is having to log into a machine to manually install

[00:04:11] **Adam:** Yes,

[00:04:12] **Ben:** and not having to do that is, is like 99% of the battle.

[00:04:17] **Ben:** absolutely. And also, from a compliance perspective, not having the ability to do that, that like having SSH completely disabled. is a huge win. Saves you so much trouble. That's very exciting.

[00:04:31] **Adam:** it is. It's very exciting. And like, just, you know, it's got all these little, like, long tail effects. For example, for the longest time, for our JavaScript bundles, for for the front end, basically, we have had the bundles themselves committed to the Git repository because we didn't have a good way to like, okay, deploy the code and then cause a build to happen on the server so that you could Just deploy your, your JavaScript source and it gets bundled on the server.

[00:04:58] **Adam:** So we've had the bundles as part of the Git repository, which means anytime anybody makes any change

[00:05:03] **Ben:** Right. And it gets

[00:05:04] **Adam:** it's merge conflict city. It's, it's so painful. and so now we don't have any of those. We haven't made any of the changes yet, but I, it's, it's on my to do list to remove the bundles from source and have creation of the bundles, added to the, the build script.

[00:05:21] **Adam:** So I'm so excited about that.

[00:05:22] **Ben:** yeah, that, so that was something that a guy at work did for us. Oh, it could have been like five or six years ago. And it was so magical when he did it basically in CodeShip, which is our CI CD system, it runs the builds and then it, so CodeShip uses something called CodeShip steps, I don't quite understand.

[00:05:41] **Ben:** It's like a special set of YAML files that just CodeShip does. And one of the steps is it takes the compiled JavaScript bundle and the compiled CSS bundles, and then it pushes those up to the CDN before the deployment even goes out. And then it takes, so it, it hashes the contents of the files and then it rewrites the file name.

[00:06:01] **Ben:** So it's not just that this is like main. js, it's main. js. You know, a4fc3125.

[00:06:09] **Adam:** Yeah. Oh yeah. It's like fingerprinted.

[00:06:11] **Ben:** Yeah, yeah, exactly. And then it has to rewrite us like, like one file somewhere to put that value in there so that we know to pull it in. But it was, it was always so great because inevitably before that, we were always running into really subtle edge cases where someone would make a request at just the wrong time.

[00:06:31] **Ben:** And, and the URL would actually pull in the old JavaScript file, despite the fact that a new one had just been rolled out. And it was such a pain in the butt. So yeah, once you get that bundle being built in CI, CD, it makes such a huge difference.

[00:06:44] **Adam:** Yes. So that has been huge. so yeah, now all of our platform servers are built on GitHub Actions and deployed from there. And it is a lovely way to start the week, right? To come back from my vacation and find out that that is no longer a nuisance. Been great.

[00:07:03] **Ben:** Very cool. Congratulations.

[00:07:05] **Adam:** Yeah. Thank you. That's my triumph. What do you got going on, Ben?

## [00:07:07] Ben's Triumph

[00:07:07] **Ben:** I'm going to go with another Triumph. Ooh.

[00:07:09] **Adam:** Triumph! Tim

[00:07:10] **Ben:** Yeah, Triumph, DoubleTriumph. What's up, Tim? We're just going through our Triumphs and Fails.

[00:07:15] **Tim:** Hey guys.

[00:07:16] **Adam:** Well, go ahead, Ben. Why don't you finish that one out and then we'll go to Tim.

[00:07:19] **Ben:** sounds good. Tim, get ready. all right. Yeah. So I'm going to go with a Triumph and this is a bit of a fuzzy self growth Triumph, but I was just thinking about this the other day, how when I was younger, I used to be so rigid about solutionizing, meaning I've always felt like I had to have consistency above all else.

[00:07:43] **Ben:** And if I came up with a solution to something, it was a solution that had to work the same for everybody. Otherwise, all I could think about was the reasons that this solution wouldn't work. And I even had feelings like that about user interfaces. I remember having a discussion one time because I thought all modal windows should be exactly the same size.

[00:08:03] **Ben:** And that wasn't based on anything other than I just, I had this undying need for consistency and uniformity. And as I have gotten older, I have just really come to believe in and understand that not everything has to work for everybody and that that's a feature, not a bug, and if I can come up with a solution that helps a bunch of people, but not everyone, that's.

[00:08:29] **Ben:** Totally valid. And I'm going to do that. And then for the people that it doesn't work for, I'm going to try to come up with maybe a different solution that works for them. And I'm just, I'm just okay with that. And, I feel like that's definitely a sign of personal growth or giving up, but I think it's actually personal growth.

[00:08:47] **Ben:** So I'm pretty excited about that. It's not often that you change your mind about things, at least in my experience. So this is actually me having changed my mind and, I, I feel like that's powerful.

[00:09:01] **Adam:** Yeah, you're right. It, you know, providing value for a reasonable chunk or a significant chunk of your user base is the job. Not everybody's going to use every feature and not every feature is going to be perfect for every use case.

[00:09:19] **Ben:** And you know what? I think that that is part of how this evolution has come about because some users just don't like the stuff that you built, period. Like they'll just never like it because it's different from the thing that they had before, and that is enough for them to not like it. And instead of arguing till you're blue in the face about why this feature is great and why you should move over to it, I'm just like, I don't care.

[00:09:43] **Ben:** Then you continue, you know, you have something that works for you. I say, huzzah, keep doing that. And I'm going to try to evolve it in this other way. And other people might find value in that. And it's not, it's not the end of the world that we're not all on the same page. And I'm just, I'm finding that that mindset is adding value to my life and the way I can think about building products.

[00:10:08] **Adam:** Yeah, it's like there's this third state that you've unlocked, right? So things are either helpful or hurtful or neutral, right? So like something can be neutral being the one that you've unlocked, right? So, a feature is either helpful or now neutral and that's fine. You can have a thing that's only neutral for you as a user.

[00:10:27] **Ben:** Yeah. And O. P. As a quick aside, I would love to one day understand that whole. like chaotic evil and neutral evil and chaotic good. I,

[00:10:39] **Tim:** D alignment.

[00:10:40] **Ben:** yeah, I don't know what that comes from, but I've seen it mentioned a bunch of times and it's in a lot of memes and I would just maybe, maybe in the after show, someone can tell me what

[00:10:47] **Adam:** Yeah, let's do it.

[00:10:48] **Tim:** it's pretty simple. Yeah. I explained it to you.

[00:10:51] **Ben:** I want to know

[00:10:51] **Adam:** figure out what your alignment is, Ben.

[00:10:53] **Tim:** Yeah.

[00:10:55] **Ben:** I feel like I'm chaotic good

[00:10:58] **Adam:** or I'm just neutral, neutral. I don't know.

[00:11:00] **Adam:** we'll see, we'll see.

[00:11:02] **Ben:** All right. So Tim, you're just joining us. Have you had time to come up with a triumvirate?

[00:11:07] **Adam:** see your lights are on.

[00:11:08] **Tim:** Yeah, the lights are finally back on. We've had some really, really bad storms here in the Southeast. I think pretty much the whole East coast has had some really, really bad storms. People are out of power. We, our power was just out for about an hour, an hour and a half, but I know some people, Pennsylvania, been out for over a day, so

[00:11:27] **Ben:** Oh man.

[00:11:27] **Tim:** yeah, just crazy storms right now.

## [00:11:30] Tim's Triumph

[00:11:30] **Tim:** I'm cool with a triumph. So a few weeks ago, we tried for, to be in compliant with our PCI compliance for credit card handling. You can't have, any software or even hardware. Which is no longer supported. So if we had a firewall that is getting up in years, you know, had to go to the bathroom pretty regularly, kept forgetting stuff.

[00:11:54] **Tim:** So, and there's no longer any firmware updates or updates for it. So in order to complete our, our PCI, we had to, remove that, put a new one. So we got the exact same brand, just the most recent model, tried to. Tried upgrading it a couple of weeks ago, just did not work at all. So we enrolled it back, but this Sunday we got it, updated, you know, there's several thousand rules, you know, that we imported into that.

[00:12:19] **Tim:** It wasn't me. I wasn't actually doing the work, but I was just making sure that everything did work afterward. And, you know, for the most part, it went pretty smooth. There were a few machines that, for some reason couldn't talk out. In PCI, you can't, you have to, any machine inside the environment. You can't just let it, you know, talk openly to the world.

[00:12:37] **Tim:** You have to specify by rule what it's allowed to talk out to. And there's just one machine that just, it wasn't like a major machine. It had just a few things on it and it couldn't talk to anything. It couldn't even talk to GitHub where it pulls its code repository from. So

[00:12:56] **Adam:** your

[00:12:56] **Tim:** finally, finally figured all that out and got all that working.

[00:12:58] **Tim:** So that's good. It's nice to know we'll be good for another, probably eight to 10 years now on, on this device. So.

[00:13:06] **Adam:** CDE, as they would say in the PCI industry has to be separated. Your cardholder data

[00:13:12] **Tim:** Yeah. Some reason our guy, he calls it the CHI, the card holder environment, C H E, but C D E I think is more correct. So he's just

[00:13:22] **Adam:** There there's, well, there's also CHD, cardholder data. Right. CHD, but then there's like cardholder data environment CD.

[00:13:29] **Tim:** I can

[00:13:30] **Adam:** I know way more than I want to. Yeah.

[00:13:31] **Tim:** Yeah. Yeah. Yeah. So, so do I. So yeah, we're, we're, we're, you know, we're on compliance now and just getting our, our, our signatures buttoned up on the, on the yearly audit. So that's good. We can stay in business another year.

[00:13:45] **Ben:** Very nice. Congratulations on that.

[00:13:47] **Tim:** Thank you.

[00:13:48] **Adam:** man.

[00:13:49] **Ben:** that, that reminds me of something just as a quick aside. I was listening to, I think it was a news piece about. Cars and how much, how so much of what makes a car a car today is all of the software that's installed on it. And in this country, and it's not the same in every country, there is a certain amount of, age that the software is allowed to be.

[00:14:09] **Ben:** Like you can't have now in this country, a car. Where it had, the software hasn't been updated in, in more than like two or three years. It's not considered, road ready at that point in this country. It's not, it's not the same in every country. And the, the news piece was talking about how car companies now have to commit to essentially promising to create software updates for cars for a certain number of years, because if you buy a car and then they stop producing the software, it essentially end of life's that car, even if from a physical standpoint, the car is completely fine. And, I know, I mean, just when you're talking about having to keep things up to date in order for, PCI compliance, it's just, so what they end up doing just as part of the news piece is they'll, you have to sell that car essentially to another country where they don't have those regulations, which seems

[00:14:58] **Tim:** Sounds like a business opportunity. We can start, like, yeah, I read that, someone basically, rooted a Tesla. You

[00:15:07] **Ben:** That means, that means like you take root control

[00:15:11] **Tim:** So basically Tesla can push out. So if you want like the self driving feature and you don't have it, it's, that's, that's not a hardware thing. That's a software upgrade. And, so they rooted it and they were able to like get the self driving to work. They were able to, all these hidden features that are in there that haven't been publicly announced or messing around.

[00:15:27] **Tim:** You know, I see like, you know, your car's the end of life. Don't worry. We can add another, you know, we'll just, we'll just, we'll just root it and make it so that it's compliant now.

[00:15:38] **Adam:** Jailbreak it.

[00:15:38] **Tim:** Jailbreak it, basically. Yeah.

[00:15:41] **Adam:** That's funny.

[00:15:42] **Tim:** This is really, really far aside just because you said that now, but I do think, and I think I've talked about this before, the podcast that eventually, I don't think anyone will own cars. Cars will be a service. You'll subscribe to a car service and you know, particularly when, when the self driving stuff gets even better, because you'll just subscribe and say, look, here's my times when I typically need to go, I need like, I'll, I'll buy.

[00:16:07] **Tim:** You know, each month, like a couple extra bonus, just run around minutes, but I'll commit to this many minutes of driving per month. So you subscribe to that. A car, a car, yeah, a car shows up at your house and you use it. And then when, you know, you go to the office or go wherever and while you're at work at the office, you know, it drives around and is an Uber and picks other people up and uses their time.

[00:16:31] **Tim:** And so you, no one will have a car. It'll all be subscription based.

[00:16:35] **Adam:** I mean, while we're going down tangents here, this is software related. I'm not sure if it was in our Discord for the podcast or if it was like work or something, but I saw an article recently about how. Oh, now I remember it was an email that my boss sent me, but about how, cars are getting these touch panels and nobody really likes them, because, you know, they bury features, the UX is pretty terrible, but the manufacturers continue to like, just pump more and more stuff into these, touchscreens.

[00:17:03] **Adam:** And if you believe the article, the guy kind of makes a solid case that. Basically, the reason is so that they can start charging you a subscription. Like you want a subscription for air conditioning? We can turn that on. You know, you want your brake pedal to work? We can turn that on.

[00:17:20] **Ben:** man.

[00:17:21] **Adam:** yeah, I mean, they called it a digital feudalism, just like, man, here we go.

[00:17:27] **Adam:** Oh, that's a, this is like, what is it? end stage capitalism. Hmm.

[00:17:31] **Tim:** Yeah. I mean, I'm fine with that. If I don't own the car, if I didn't pay for the car, right. There's this feeling of ownership. If I'm subscribing to the car and that's an extra feature and I'm paying like, you know, 50, 75 a month or however much it is to subscribe to a car. And I just want an extra bonus. I got no problem with that, but don't tell me, give me a title to a vehicle.

[00:17:53] **Adam:** Right.

[00:17:54] **Tim:** And then tell me, you know, Oh, it's an extra so much a month. No.

[00:17:58] **Adam:** Yeah, yeah, yeah. The, the first one that I remember being, and this might not be the first one that it actually was, but the first time this came across my radar was, I think it was either BMW or Mercedes, it came out that they were going to start charging a subscription to use the heated seats. Which is so asinine, like the equipment is there, it costs you nothing on a monthly basis for me to be able to use it like I get it when the software is online and I, and you have to keep your servers up and stuff like that.

[00:18:26] **Adam:** Like when you have a cost, it makes a certain amount of sense for me to continuously support that cost. But when it's a piece of hardware that's in a device that you're never gonna see again,

[00:18:37] **Tim:** And you're just triggering a feature flag.

[00:18:39] **Adam:** yeah, that's, yeah. Price gouging. For sure. So, yeah, let's, let's talk about software. so as I mentioned at the top of the show, we're going to talk about fraud today.

[00:18:49] **Adam:** We didn't know that Tim was going to make it. We had another topic planned for, for with Tim. So I don't know, as a credit card guy, Tim, I'm sure you'll have plenty to contribute to this conversation, conversation.

## [00:18:58] Card Verification Fraud

[00:18:58] **Adam:** so basically Ben and I were discussing and found out that we both have a very similar problem, which is that we have people who, Appear to be behaving as humans.

[00:19:10] **Adam:** Like there is a human at a keyboard going through a stack of stolen credit cards, trying to find one that's working. And then when they find one that's working, then they go off and they use it for what they really want to use it for. But in the meantime, what they're doing is they're submitting dozens or hundreds of, in my case, you know, like online gifts to the, to a university.

[00:19:31] **Adam:** They go, here's a 5 gift. Oh, and it failed. Okay, well, here's another 5 gift from the same name. you know, it's got, the, the CAPTCHA has been redone, right? There's definitely a human sitting there at the machine doing the CAPTCHA. same name, same amount, new CAPTCHA token, but a different credit card, right?

[00:19:48] **Adam:** Or sometimes it's like just garbage, right? Like it's like six characters just matched on a keyboard for the first name, same thing for the last name and then whatever. And it's like, there's, there's some stuff that you can do to prevent automating this, but I feel like it's almost hopeless to prevent. to, to detect and block somebody that is determined to sit there and use your payment form that's open to the world, because you want it to be, right, this is a, a donation thing, right?

[00:20:20] **Adam:** You wouldn't go to Kickstarter and have to, and expect to have to pay, or to, to jump through 11 hoops to, to pay for the thing you want to pay for, right? And so it's, it's infuriating.

[00:20:32] **Tim:** True. But I mean, honestly, Etsy, you do have some form of verification, right?

[00:20:39] **Adam:** Well, but the, so in my case, we have, it's an online giving form and there's, we have two, you know, there's one that's like, we want to collect a little bit more information about you. We call it our legacy giving because we have a newer version that is. We call it GiveNow. The idea is like slim it down as little as possible.

[00:20:53] **Adam:** We need your name so we know who to credit. We need your credit card information, which is not part of what we're collecting. That's the PCI thing. But, you know, we like name, email. I think phone number might be optional and like amount. That's like basically it on that form. And then the CAPTCHA, which we use ReCAPTCHA, from Google.

[00:21:11] **Adam:** And I think that from my understanding, the vast majority, like 70, 80% of users don't even see the CAPTCHA. Like if it can detect that it's running in a human in the loop scenario, it tries to not show you a CAPTCHA. But then if it thinks that you might not be a human, then it'll show you the challenge

[00:21:29] **Ben:** Yeah.

[00:21:30] **Tim:** the same problem, Ben?

[00:21:31] **Ben:** yeah. And ours is behind ours is behind a login system. So people have gone into the system. They have created a team, which I believe actually uses email verification to create the team. And then once they're in the logged in state, they go to the upgrade payment form. And they do exactly what Adam's talking about.

[00:21:54] **Ben:** They just start trying different credit card numbers. Now, the thing that we've seen is that they go as far as actually making sure that a lot of these requests are coming from separate IP addresses. So they're creating... Hundreds of different teams, hundreds of different users, and then basically just hammering the system trying to find valid credit cards.

[00:22:18] **Adam:** and they're doing all that with a login step

[00:22:20] **Ben:** Yeah, it's crazy. Peeps are nuts. I mean, I don't work in that part of the system, so I don't know if maybe there's, maybe we're making it easier than we captcha.

[00:22:34] **Ben:** But again, it's in a logged in system behind something that I'm almost certain they had to click on some sort of email verification in order to even get through.

[00:22:43] **Adam:** Right.

[00:22:44] **Ben:** So we're, we're, we have rate limiting, but the rate limiting is usually based on the team ID or the IP address. And again, they're just,

[00:22:55] **Tim:** Well, but they have a login. I mean, how many times with a login would you want to, would a person typically pay?

[00:23:01] **Ben:** right. Well, well, but it's because if, if you sign up and you, you have a free account. And then you want to upgrade to a paid account. You know, we want to, we want to let people do that anytime they have a free account. So there's no, they're doing it from a volume standpoint too. It's not, it's from a, for IPs and different teams.

[00:23:21] **Ben:** It's really, it's the same, it's essentially the same issue that we had with Twilio, which we've talked about previously on the show, that people will just sign up for loads of accounts from various IP addresses, literally hundreds of different IP addresses and just start using the features in a way that they're not supposed to.

[00:23:39] **Adam:** So it sounds like you're saying that they'll register, like they completely automate this. They register for a free account, which requires them to receive an email and click the link in the email. And then once they're in, they start trying to upgrade that to a paid account with a series of stolen credit cards until they get a good one.

[00:23:56] **Adam:** And then, okay, now this is a paid account, but, but I've verified that this card information works so they can go use that elsewhere.

[00:24:02] **Ben:** Right.

[00:24:03] **Adam:** And then they just start over. You know, the, the rest of the credit card list on another free account and keep going until they get more.

[00:24:10] **Ben:** Yeah. And, and I don't, because I don't work in that part of the system. I'm not quite sure what the constraints are and how many times they can try a payment, you know, different credit card or if there's a time period in which it can be constrained, and I think we have been evolving it once we realized that this was happening.

[00:24:29] **Ben:** And, and the most frustrating part of it all is like at first, I hate to say this, but my first gut reaction was. Should we even care? I mean, I don't want people's credit cards to be stolen and I don't want to be part of the problem. But at first I just thought, yeah, that sucks. But is it really even a problem for us? Uh, because we're not technically doing anything wrong. You know, we're not breaking the law. We're doing our due diligence. They're, they're validating their email, all that jazz. But then the guy who's mostly working on this problem right now, he's saying, yeah, it doesn't hurt us right now. But then what happens is the customers But we're like, Hey, why did Invision charge our car?

[00:25:07] **Ben:** Then they ask, they either report fraud or they require, what is a clawback or, or there's something where, yeah. And then that can really hurt our standing with the payment processors. And I think we get charged money for that as well, some sort of fee. And so it does actually hurt us. So,

[00:25:24] **Adam:** Yeah. And well, but the, that's another, and that's another thing, service providers, the, the companies that are doing the credit card charging for you, like Tim's company or your Braintree, your, you know, all of those companies, PayPal, Stripe, et cetera. they. Are supposed to be doing some fraud detection and prevention for you.

[00:25:45] **Adam:** And like, they'll return different error statuses when, when they detect fraud. So they're, whatever these people are doing, it's obviously getting around all of that too.

[00:25:53] **Ben:** so frustrating.

[00:25:54] **Tim:** I mean, you mentioned us, us doing that. I mean, we don't do that either because that's, that's really the card network's job.

[00:26:01] **Ben:** We're all just

[00:26:02] **Adam:** maybe that's what I meant, it's like, yeah, yeah, we're all passing the buck, but eventually, I think, you know, Visa, MasterCard, et cetera, they are trying to do that, and then, you know, they return that status to you, and you return it to us, right?

[00:26:15] **Tim:** So, I mean, there are, yeah, we, we pat, we just pass on the status that comes from the card network. So, I mean, there's one that's suspected fraud, which comes through a lot.

[00:26:24] **Adam:** Mm hmm, mm

[00:26:25] **Tim:** I mean, what's happening in practice is there, you can go. On the dark web

[00:26:30] **Adam:** hmm.

[00:26:31] **Tim:** and buy a list of credit card numbers, you know, credit card numbers, CVV codes.

[00:26:37] **Adam:** The dark web, that's AOL, right?

[00:26:39] **Tim:** Yeah. Yeah. That's, that's AOL. That's AOL. so you just, just, just put that disc in that you got that, that you got back at, back in 1998, you know, you got about 500 of them. Yeah. Just, just find that three and a half inch floppy drive and stick it in there, load it up and get that, you know, 6, 400 bond modem going.

[00:26:57] **Tim:** No, but you, so I mean, people buy these lists and it's probably, like you said, there probably is some human, right? It's these, these shops that just have a bunch of, you know, very poorly paid people that are sitting in a machine. All they do is they crank through these numbers and just try to find a number that's good.

[00:27:13] **Tim:** but I mean, the card networks, then they know the numbers that are exposed. So they, they do take some effort to try to, if your card's exposed. to contact the people whose cards are exposed and get them to change their card and to invalidate their card. So, I mean, it's their job to do that, but I mean, we do some things, right?

[00:27:32] **Tim:** So, typically, with us, what we see is like... A person who's trying to validate a card, all they really want to do is charge a small amount. So it's not noticed if, if your system, like some systems you can't, like maybe Invision it's like a, you know, 69.95 upgrade. You, it's, you know, you can't just choose a dollar.

[00:27:52] **Tim:** But in ours, like insurance premiums, it could be anywhere from, you know, a couple bucks to a couple thousand dollars. So we don't do that, but it's like, if it's a small amount, it's like under $5. And you have a 4. 95 processing fee. It's probably not a smart business decision as a user. So we do flag those and try to, and try to stop those.

[00:28:13] **Tim:** but we don't actually, we don't see a whole lot of those. I'm just surprised that Ben said it's a login type system. We do track like if it's the same, same user, because like typically a person has to know about their policy information. If it's the same policy over and over and over again, that's, that's a red flag.

[00:28:32] **Tim:** And that gets. That gets blocked, until we, we can take a look at it,

[00:28:36] **Ben:** I'm wondering now, because it is a logged in system, but I think that our rate limiting, so, so there's a bunch of ways that you can do rate limiting. And one of the ways in which the new platform does rate limiting is it does it at the firewall. And the firewall is, I think, the rules, it uses IP addresses.

[00:28:55] **Ben:** So I'm wondering if maybe what's happening is someone is logging into the system, entering the credit card, and then that triggers some sort of a network request. And maybe they're copying that network request, and then trying to replay it from a bunch of different IP addresses. Though that said though, I mean the way that we handle the credit cards is like we don't actually touch the credit cards.

[00:29:19] **Ben:** I'm, I'm almost certain that we have some sort of weird embedded form where we don't actually use a credit card. We get a token and then we're managing the token. It's like, yeah, so I don't even understand. So maybe they are actually just scripting this somehow.

[00:29:33] **Adam:** So it sounds like we have very similar end results, but, but kind of different paths to get there. Like my, my gift form is more accessible, easier to get through. You don't have to go through a login or anything like that. We're trying to like reduce friction as much as possible there so that, you know, somebody who maybe just graduated and, and you're, you, catch them at the right time and you can get them to give five bucks and that might start a journey of lifelong giving to their alma mater sort of thing.

[00:30:02] **Adam:** That's the. The, approach that they're trying to take. so we want that friction to be as low as possible. And then you've got some people who are like, okay, you know, I'm, I'm 80 years old. I'm trying to get rid of all my money cause I can't take it with me. so I'm going to give 90,000 to this cause over here and 40,000 this cause over here and 2,000 this cause over there.

[00:30:24] **Adam:** And. In order to keep the complexity of the interface down as much as possible, we just have them do that as like separate sort of GIFs, like make a GIF, pay for it, make a separate GIF, pay for it, make a separate GIF, pay for it. We initially kind of, prototyped it out as like a multiple GIFs thing, and it worked great, but it was more complex than your average non technical person would be able to navigate without frustration, so we simplified it.

[00:30:50] **Adam:** But the end result of that is we... Want to allow, and we need to support the use case where you make a gift, and then you immediately go back, and you make another gift. Maybe, it could potentially be the exact same dollar amount to a different cause. It could be to the same cause. There's no reason you couldn't donate 500 to the basketball team and then go, Oh wait, I meant it to be 1,000, so I'm gonna make 500 again.

[00:31:15] **Adam:** Right? and... So, like, the opportunities to detect what appears to be fraudulent behavior are very slim for us, I feel like. Like, for example, something that we see, and we talked about it a bit this morning, is often these charges that are, it's, it's like the Supreme Court porn thing, right? Like, I can't, it's hard to define what it is, but I know it when

[00:31:39] **Adam:** I see it, yeah.

[00:31:41] **Adam:** like. You're looking at these fraudulent payments and going, okay, well, what are the, what are the patterns that we can pull out of this? First name and last name match. They're exactly the same. So if it's like Fred Fred, okay, that's not super likely. But then I went and I just, the, that was actually a pattern that was suggested to us by one of our customers, right?

[00:31:58] **Adam:** The IT guy at one of these universities. And I took that guy's data. I went into his database and I said, here's your list of all of your, your constituents that you know of. Let me pull out a list of all of them where the first name and last name are identical. And I gave them, and it was like 50 people or something like that, and I'm like, do you, you know, it's not a huge percentage of your constituency, but do you really want to tell these people that they, they're not allowed to donate because their name matches?

[00:32:20] **Adam:** Like,

[00:32:21] **Tim:** after he changes his name. You want to get his money, right?

[00:32:25] **Adam:** seriously.

## [00:32:26] Possible Solutions &amp; How Card Charging Works

[00:32:26] **Adam:** So, like, I, I, it feels like I kind of know what the... Right answer is at our scale, right? We need a review queue, right? So you can say, okay, this looks fraudulent. We need a human to come take a look at this before we finalize it or whatever. And that way it never hits the card and, and there's no, whatever, there's basically no record of the charge.

[00:32:47] **Tim:** Well, it doesn't hit the card. It does hold on the card.

[00:32:51] **Ben:** wait, wait,

[00:32:51] **Tim:** just sometimes almost as painful.

[00:32:53] **Ben:** Yeah, if we can just wind up for a second, cause this is a part of the technical implementation of charging a credit card that I don't really understand. Are you saying that when I submit a payment form, my card is not charged right away? There's some sort of intermediary period where there's wiggle room?

[00:33:11] **Tim:** yes and no. I mean, from my perspective as the guy in the middle accepting the charge, right, so my company accepts your charge. As far as my company is concerned, the charge has been collected. Now, the service provider, Tim's company, or Stripe or whoever might come back and say, well, actually this one was charged back or, you know, the, basically they give you like a, a very, A high probability of success. Like when there's a high probability of success, they're like, okay, this one's going to be fine. And then in that extreme minority of cases, they'll be like, well, it didn't work. How it works. So, so to answer your question, Ben, so for like particularly bank cards, debit cards. So when you first do the initial, you authorize the amount. So basically what it is, you're telling the bank, Hey, I need a hundred bucks. I just need to make sure you got a hundred bucks and that this is a valid card number.

[00:34:10] **Tim:** So it says, yeah, it's a valid card number. And yeah, this bank has a hundred bucks. You'll see a pending, if you have like online banking, you'll see a pending transaction sitting there. that, and it, and then there's different types. So let's say you're in a service industry where, you know, you charge your car, but they're also, they've come back to the table to let you do a tip.

[00:34:32] **Tim:** That, even though it's pending a hundred bucks, it could still be even more because you could add a tip

[00:34:37] **Ben:** Oh, interesting.

[00:34:38] **Tim:** So that can be, that can be altered. The amount can be altered afterward. So that shows up. If you look in your bank account, that shows up as it's no longer something you can withdraw at that point.

[00:34:51] **Tim:** Now, if some

[00:34:52] **Adam:** on that money.

[00:34:52] **Tim:** there's a hold on that money, it's still in your balance. They haven't debited it from your account. But if you, you know, let's say you have 200 in your account, you charge the card. It's authorized for a hundred and you try to spend 200 somewhere else. It's going to decline because you don't have 200 right now.

[00:35:07] **Tim:** You have a hundred available. So, and then, yeah, exactly dibs. And then once it's, it's finalized, you do the final sale that it shows up as an actual transaction, but the actual money doesn't get transferred from one person to another until the next day is usually like a day settlement time where me, the merchant shows up in my account as a deposit.

[00:35:31] **Tim:** typically that there's usually no issues there. Once, once they, the, the MasterCard Visa Networks promise that that's good. It's covered.

[00:35:39] **Ben:** So are you saying, so Adam mentioned having a review process where a human actually looks to see if the charges look fraudulent. Are you saying that In that sort of maybe 24 hour period, someone in the middle could say, actually, you know, I'm not sure that Lead Haxor, is actually a real person. let me

[00:36:01] **Ben:** let me cancel that. yeah,

[00:36:03] **Adam:** yeah, basically, yes. So, and maybe I can illustrate this a little bit better or more fully with another example too. So another thing that we do is event registrations and you sometimes have to pay for those events and. if you make a charge, right, sign up for an event, you pay for it, and then two hours later you go, you know what, something just came up, I can't make it, you call to cancel, they cancel your reservation.

[00:36:28] **Adam:** if they try to refund that charge, and it hasn't settled yet, then... Then we get an error, basically, because the charge hasn't settled, so there's actually nothing that can be refunded because it hasn't been charged. And settling is kind of like an end of day batch sort of thing, right? So all your charges from the day settle out, like they settle the books, balance the checkbook at the end of the day.

[00:36:53] **Adam:** and so we have to like make a sort of a best guess and then sort of try catch sort of things to say, okay, it's only been an hour since, the charge, you know, you click the refund button, but it's only been an hour since it was charged and it's 1 p. m. So has it, is there a chance it's settled yet?

[00:37:13] **Adam:** Probably not. And, so instead of a refund, we'll do a void. Which is basically the same thing. It's just makes the credit card, the service provider happy that we're doing a void and not a refund,

[00:37:25] **Tim:** we do this, we do the same thing. We, we try to refund first. And if it errors, we just do avoid it just because you never know exactly when the network you're, you're using is going to settle. But, but, but what you were saying, Ben, it's like, so yeah, you could, if you're not... Finishing the sale. You could do an authorization of an amount, say it's a hundred dollars.

[00:37:44] **Tim:** It's early in the day. Someone does a hundred dollars, check that. And then you don't actually do the final sale until maybe end of the day. Once you review the entire queue and go, Oh, Bobby dropped tables. It's probably not legit. I'm not gonna, I'm not gonna sign off on this one. And that one just gets voided.

[00:38:03] **Ben:** Interesting.

[00:38:04] **Adam:** right? So the, the review queue. Would allow us to bring somebody from, in our case, our customer, you know, like the, tell their IT department, look, you've got these three gifts that came in that look like they're fraudulent to us from, you know, the, the robots think that they're fraudulent. You go in and you look at it and you can either allow it to continue or you can void it now and we'll just like save our, save everybody the trouble. And the problem is. Getting people to do their jobs is like pulling teeth.

[00:38:35] **Tim:** Well, particularly when it means denying money, right? Who wants to do that?

[00:38:38] **Adam:** We've had, so we've talked about sending email, right? and my company sends a lot of email and we've had cases where things go, things go awry, right? Somebody's email address, you know, it's missing the at symbol or it's got a dot on the end or things that are. Obviously not valid email addresses, but we may or may not know what it actually should be.

[00:39:00] **Adam:** Like, you might see a bunch of letters, something something dot com. Like, okay, there's supposed to be an ad in there somewhere, but we don't know exactly where it's supposed to go, whatever. and so when there's these cases that we don't know how to resolve, we can't automatically resolve them. The system will send the right person an email.

[00:39:19] **Adam:** On a consistent and intentionally aggravating schedule. Hey Ben, there's this email that you tried to send nine hours ago that I've been reminding you about every 30 minutes for the last nine hours. Here is how you can make these emails stop. All you have to do is go in and click one of these two buttons or, you know, fix the email address or whatever.

[00:39:38] **Adam:** Like, here's the link, click this button, do what it says on the screen, and the pain will stop. And we've had people that will let that go on for, like, weeks and then file tickets complaining that it's annoying. And I'm like, it's intentionally annoying. Do your goddamn job.

[00:39:57] **Ben:** Man,

[00:39:57] **Tim:** got added to their spam filter.

[00:39:59] **Ben:** you know, as a, as a very quick aside, just because we're talking about humans in the loop and, and doing things kind of mechanically, my wife heard a radio piece about Amazon's Mechanical Turk. And for listeners who might not be familiar with that, Mechanical Turk is essentially trying to mechanize large scale human activity.

[00:40:20] **Ben:** So you might say, Hey, I need to identify, is there a person in this photo and I have a million photos and I'm just going to send one to a bunch of people and people will get paid like two pennies to say yes or no, this is a human anyway. So she was fascinated with this idea that this is even a service that exists.

[00:40:37] **Ben:** And, she went to look at it and it turns out you have to apply for it. I've never looked at it before, so I wasn't sure. So she had to fill out the whole form about. Like who she is and why she's interested in it. And then they get back to you and, and they rejected her. They say, we reviewed your information and basically we're going to hard pass.

[00:40:55] **Tim:** Yeah.

[00:40:55] **Tim:** They're looking, they're looking for people in like African countries that, yeah, they're looking, yeah,

[00:41:01] **Adam:** They want people that'll work for peanuts.

[00:41:03] **Ben:** Hmm, gotcha, gotcha, gotcha.

[00:41:05] **Adam:** But what she needs to do is pay somebody on Amazon Turk to fill out Amazon Turk applications.

[00:41:18] **Ben:** Oh, that's great. Oh, good times.

[00:41:24] **Tim:** So talking to what you said earlier, but people don't want to do it. There is, I've noticed there's a reluctance. They're like, all right, someone paid me. And you're saying I have to take an action here that could possibly make them not pay me. Then they're doing the calculus in their head. Well, you know, a 500 gift, what are the chances that the person that actually owns this credit card will notice?

[00:41:46] **Tim:** Maybe they won't, you know, free money. Um,and what's interesting with your use case is like, so there's no goods and services really being,

[00:41:56] **Adam:** No, you're right.

[00:41:57] **Tim:** is no gifting. I mean, what I see, well, not with us either. The insurance is the same. It's not like you're getting a, a thing, right. But it's like.

[00:42:07] **Adam:** It is a tax deductible donation, but other than that, yeah.

[00:42:09] **Tim:** when I've, you know, when my cards have been compromised, you know, people are like going to these high end designer watch places and Gucci and all these, you know, designer play and ordering stuff online.

[00:42:21] **Tim:** But those places seem to be very good about figuring out, Oh, wait a minute. Some person did this big purchase on a card whose address was in, you know, Georgia, you know, Byron, Georgia, and then mailing it to someplace else, another city, it gets flagged immediately. So.

[00:42:37] **Ben:** Yeah. Isn't AI and large language models, isn't, isn't that supposed to solve all this for us? I mean, I guess the

[00:42:43] **Tim:** It's going to solve everything.

[00:42:44] **Ben:** using a lot of fraud detection, AI

[00:42:46] **Adam:** Ask ChatGPT how we can fix this problem.

[00:42:48] **Tim:** Yeah.

[00:42:48] **Ben:** Can I just pipe people's credit cards into chat GPT and ask if it's valid?

[00:42:52] **Adam:** this legit?

[00:42:53] **Tim:** It's just legit.

## [00:42:56] reCAPTCHA

[00:42:56] **Ben:** I'm curious to know a little bit more about this reCAPTCHA because I've, I'm, I've heard of it, but I've not used it. Is it, is it just a library that you put in or is it a service that you pay for? How does that work?

[00:43:07] **Adam:** It's free. and so you have, I'm sure that you have used it, right? So if you go to a website and it's like,

[00:43:13] **Ben:** which square has sailboats in it? That kind of

[00:43:16] **Adam:** Yes, or like, you know, identify all the, the photos in this grid that have cars in them

[00:43:21] **Ben:** Yeah. Yeah. Like I've definitely

[00:43:23] **Adam:** That, that's the one that drives me the nuts, nuts the most, right? It's like, which one, which of these photos has a stoplight in it?

[00:43:28] **Adam:** And it's all, it's all one photo, but it's broken down into a grid. So you're identifying like what area, and it's got like, One little corner, one picture has one little corner of the metal part of the stoplight and like, now do I, is it going to yell at me and not think it's right if I do include that or if I don't include it? I hate it so bad.

[00:43:47] **Ben:** Okay. So, so the thing that you're using is the thing that I see anytime I see that. Is it, I didn't know if maybe you were using like a special business service version of one or

[00:43:57] **Adam:** No, I mean, there are a couple of different, providers out there, but we just use the Google one, it's reasonably intelligent and able to stay out of the way for the vast majority of good people, right? Like, people on the happy path. And so... that's why we like it instead of having to make everybody do, you know, if it, I'm just going to make it up cause I don't know who else provides it, but like, instead of having everybody do a CloudFlare, Captcha, yeah, so it's free.

[00:44:24] **Adam:** It's, I don't, I guess it's probably not open source because they, then, you know, you would know how to defeat it. yeah, you get like minimal stats on like, you know, how many are being, how many people are actually seeing the capture versus how many people are flying under the radar enough that they don't see it, how many people are failing and passing, that sort of thing.

[00:44:43] **Adam:** You can, you can kind of tweak the sensitivity of it a little bit. You don't have a whole lot of control over it.

[00:44:48] **Ben:** What's the, graceful degradation story? Like if

[00:44:53] **Ben:** the

[00:44:53] **Adam:** mean for like accessibility?

[00:44:56] **Ben:** Like, I assume it loads on some sort of js URL, you know, like a script tag or something like, what if, what if that URL is blocked? Can people submit the form or the basically that deactivates the form entirely?

[00:45:08] **Adam:** I think in our case, it would probably deactivate the form entirely, but that would, you wouldn't even get that far in our case, right? Like if you don't have JavaScript, you're not, you're not getting through anything because effectively 99. 9% of the world is okay with JavaScript now. So we're, we're just like, okay, we're not going to fight that.

[00:45:25] **Adam:** That's not the hill that we choose to die

[00:45:27] **Ben:** Right.

## [00:45:28] Fraud Story

[00:45:28] **Tim:** So to talk about fraud stories, I got, I got a, I got a good one. So in the credit card world, you're supposed, so if someone asks for a refund, you're supposed to refund them in the same manner, which they paid. So if they paid on a credit card, you, you're supposed to charge back to that, that card, right? And you should be able to, right?

[00:45:46] **Tim:** You've tokenized it and you have that information. So it should be. Relatively simple to, to token it back, but we had a customer for some reason, their business policy, there was an insurance company. They're no longer in business. and probably because not just because of this, but because of things like this.

[00:46:02] **Tim:** So people would go on to their insurance policy and make a, I don't even know if their insurance policy, but they would make a payment on a card. Obviously it's a stolen card. Like 6, sometimes 10,000. And then they would overpay. So an insurance, if you overpay an insurance policy, they, they need to refund you.

[00:46:22] **Tim:** Well, they weren't refunding them via the card. They were funding them with a check. So they, they would take a stolen card, charge 10,000. They would send him a check for 10,000. Then they, next few weeks later, another 10,000. They get a check for 10,000 and then, and I probably saw like 60, 70,000 worth of transactions that just a few of these policies that I'd saw had, they'd asked about that, I'm like, yeah, you guys shouldn't be doing, and then later, later whoever's card it was, they're like, Oh, this is not my card.

[00:46:55] **Tim:** They, they did a charge back on it. So not only have you spent out 70,000, now you owe the card network 70,000 because, so 140,000 out completely. Cause you weren't following the rules.

[00:47:09] **Adam:** It's a, sounds like an effective way to launder money.

[00:47:13] **Tim:** That too.

[00:47:14] **Ben:** I know, we will sometimes get a gift card from the CVS. CVS is just a drugstore up here. Convenience store. Or like Walgreens and that kind of thing. You know, you, you can get a gift cards for Amazon or Chipotle or, or, you know, whatever they visa prepaid cards. Apparently you cannot buy those cards with credit cards.

[00:47:37] **Ben:** Those have to be either bought with cash or with debit cards. And I, and I think that has to do with fraud. I don't, I don't remember exactly why, but.

[00:47:44] **Tim:** Cause you're taking, you're taking unsecured credit and turning it into real

[00:47:49] **Ben:** Yeah.

[00:47:50] **Adam:** Interesting. Yeah. I'm not, I don't usually buy. Credit cards. Just like, here's money. At VenmoU.

[00:47:57] **Tim:** Like an Amazon card. Those are great.

## [00:47:59] Patreon

[00:47:59] **Adam:** Well then, I guess this is where we wrap it up, so I tell you that this episode of Working Code was brought to you by using MechanicalTurk to ask ChatGPT to commit credit card fraud to buy gift cards. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:48:22] **Adam:** Special thanks, of course, to our top patrons, Monte and Giancarlo. You guys rock. If you would like to help us out, you can go to patreon.com/workingcodepod. We are, I think, starting to get close to the point where we can afford to do transcripts for every episode. Thank you. And I think we'll be able to make transcripts from all the back episodes as well.

[00:48:44] **Adam:** So like, not just going forward, but the back catalog too. The last 139 weeks of our psychobabble.

## [00:48:51] Thanks For Listening!

[00:48:51] **Adam:** Anyway, our patrons get, after we're, after the outro plays, our patrons are going to continue listening and they will hear the after show. And on the after show tonight, we're going to figure out Ben's D&D alignment after he figures out what D&D alignment is.

[00:49:05] **Adam:** And then, he's dropped some hints in our private chat about being on a new team and I want to poke him and ask him about his feelings. About being on the new team. So we'll see about that. And then maybe soon, hopefully we'll discuss that on the main show. Anyway, that's going to do it for us this week. We'll catch you next week. And until then,

[00:49:24] **Tim:** Remember, your heart matters.

[00:49:26] **Adam:** even if your power's out,

[00:49:28] **Tim:** yeah. Even if your power's out.
