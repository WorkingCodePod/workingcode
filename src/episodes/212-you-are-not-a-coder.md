---
title: "212: You Are Not a Coder"
description: "In this week's episode, Adam, Ben, and Tim tackle the intriguing and timely topic of AI and its implications for the future of coding."
date: 2025-04-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/212-you-are-not-a-coder/id1544142288?i=1000702305663"></iframe>

In this week's episode, Adam, Ben, and Tim tackle the intriguing and timely topic of AI and its implications for the future of coding.

They delve into how AI is currently being used, including the hype around LLMs, its perceived threat to coding jobs, and the limitations of AI in professional software development.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/212-you-are-not-a-coder.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** So I thought to myself, okay, everyone's talking about how great this kind of stuff is and, and how it can help with therapy. So I was like, you know what, let me see if I can talk through some of my anxiety with chat GPT, and it was like immediately disappointing because it, it's,

[00:00:15] **Tim:** Just like real therapy.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 212. And on today's show, we're gonna talk about you are not a coder.we'll, I guess we'll dive into what that means. Why, why did I just make that assertion? Uh, if you're, if you're listening to the Working Code Podcast, your life has to do something with code. I bet. So, what does that mean?

[00:00:56] **Adam:** but first, as usual, we'll start with our tris and fails, Carol's not able to be with us tonight. So just the guys again, that, which means, Tim, I'm coming to you first.

## [00:01:05] Tim's Fail

[00:01:05] **Tim:** Hey. okay, well, I've got a, a failure I think I may have mentioned last.

[00:01:09] **Adam:** he's gonna bum us out again.

[00:01:10] **Tim:** Yeah, I've got a, yeah, sorry. So, you know, I, I grew up, my, my cousins were kind of like siblings. Like we all grew, all my cousins, aunts, uncle, we had like a family compound and we all lived next door to each other. So we all grew up together and, and my aunt, who's my cousin's mom, she had a massive stroke last week.

[00:01:29] **Adam:** Mm-hmm.

[00:01:29] **Tim:** and, and when I, we recorded last time, it was Tuesday, we didn't really know what was going on, but. By Friday, they had decided that, you know, she was brain dead. She wasn't coming back. So

[00:01:39] **Ben:** Oh,

[00:01:39] **Tim:** whole family gathered together at a hospice care center. And, and I, I've never in my life watched someone take their last breath, but I mean, you know, she's pretty much gone already.

[00:01:50] **Tim:** I mean, it was machines keeping her alive. They took her off the ventilators and gave her some morphine and did that like every 10 minutes, and in about 30 minutes she was, she'd passed. So it was hard, hard, you know,

[00:02:05] **Adam:** Yeah. I'm sorry, man.

[00:02:06] **Ben:** Yeah,

[00:02:07] **Tim:** but it was at the same time, it's kind of, you know, her husband, my uncle, you know, they'd been married over 50 years and, and he just, you know, he kept having hope, right?

[00:02:19] **Tim:** She's like, she's still breathing because like, they unplug her and we think, you think, well, okay, machine's doing the breathing for her. But it takes a long time. The heart just kind of keeps going even though it's not getting oxygen. And, you know. Which he finally did pass. It was like, I think a weight was lifted off his shoulders that, you know, okay, now I can, you know, now I can start the grieving process.

[00:02:38] **Tim:** There's no longer any hope. Right.

[00:02:40] **Adam:** Yeah.

[00:02:41] **Tim:** So, so that was rough, but it was good to be there for my family and, you know, my cousins and support them and their difficult time because it's a big family. They've got, I mean, they had, my aunt and uncle had four kids, so I have four cousins and they all have children and some of 'em have grandchildren.

[00:02:57] **Tim:** So

[00:02:58] **Adam:** Wow.

[00:02:58] **Tim:** a

[00:02:59] **Ben:** Are they in Georgia?

[00:03:00] **Tim:** They're all in Georgia. Yeah. Yeah. They're all, all still in Georgia, so. Yeah. But anyway, sorry to bum everyone out, but, you know, death is, you know, we, we ain't, we ain't getting out of this, this thing alive. Right.

[00:03:12] **Ben:** Yeah.

[00:03:12] **Tim:** gotta deal with it. I hope you have a triumph, Adam. 'cause let's, let's cheer us up.

## [00:03:17] Adam's Triumph

[00:03:17] **Adam:** so yeah, let's say it's a rollercoaster, but it's a triumph in the end.

[00:03:21] **Tim:** Okay.

[00:03:23] **Adam:** so, uh,a, a recurring theme in my life is that just about all of my stress and frustration, not all of it, but a lot of it comes from compliance. and so we've talked in the past at great length about SOC two and PCI requirements being, a source of frustration for me.

[00:03:43] **Adam:** One of the PCI changes for this year is that something that was formerly just like a, you know, quote unquote best practice, according to PCI has now become a strict requirement, which is that, for, you know, companies like mine that are doing what we're doing. You have to use, CSP content security policy headers on your webpages that embed credit card forms, to secure them. okay. You know, it is a best practice not only from PCI, but also just, you know, in web development in general. and I will say, you know, we were not necessarily using that in all of the places that we needed to be, or that we are now required to be. and so I had to jump through some hoops to make all of that work.

[00:04:29] **Adam:** It was not a fun process and I, you know, very much of, getting that figured out made me compare it very heavily to the TSA. The transit safety administration thing is what it is, in, in the United States. For those that are not familiar, you know, when we walk into the airport now, we have to say to goodbye to our family, pretty much right inside the airport door.

[00:04:51] **Adam:** Like you, there's room to go buy a ticket and check your bag, or not even check your bag yet. oh. Yeah. Yeah. You check your bag at the front door, and then there's a security checkpoint, run by the TSA, and that's where you have to like, take off your belt and your shoes and take your laptop outta your backpack and all that, empty your pockets and go through the metal detector.

[00:05:07] **Tim:** do the hooky pokey.

[00:05:08] **Adam:** Yeah. and a lot of Americans, myself included, call that security theater because if I'm, if I'm correct, even to this date, TSA has yet to prevent a terrorist attack. Like there's, they've never like found a bomb or anything, like they find okay, people trying to bring on knives or whatever, but like, there's never been an actual, like this person was planning to blow up the plane and, and actually got prevented by TSA or whatever.

[00:05:35] **Adam:** so it, it feels like a lot of work for zero gain in a lot of cases. anyway, so I call TSA security theater. I, I certainly appreciate the potential for more security, but I don't, that's not what we're here to talk about anyway. Um,content security policy, is it, it definitely comes from a healthy, correct, like good place, well-intentioned place, and there are, so like, it's basically, it's a header you can turn on and you can say like, okay, so for images, these are the ways that images can be loaded.

[00:06:12] **Adam:** They could be loaded from whatever the current domain is. I don't have to know the domain name. I could just say self. And that includes the domain name. Again, do it by protocol. So you can say like, HTPs colon, anything is allowed, or you can, or you can say, Blob, colon, whatever. So like there's, like, it gets into all of the ridiculous ways that stuff works on the internet.

[00:06:37] **Adam:** Like you start to find, when you implement it, you start to go, wait a minute, like this weird thing I didn't even realize was going on actually does get used in this one weird edge case. And now that's broken because CSP is disabling it. And, and that's, so that's for images, fonts, child frames. So you could say like, frame source has to be within these rules, sorry, images, fonts, frames, scripts, connections, right?

[00:07:03] **Adam:** So I guess that that probably includes web sockets and some other stuff. and, and probably even more than I'm forgetting, there's like child source. It's, it's ridiculous. There's all of these categories and then within each category you have to specify all the rules that are allowed. And then there's like defaults, right?

[00:07:21] **Adam:** If you don't specify. The image source, but you do specify default. It all rolls up to default, whatever the default rules are. And, and, and there's a hierarchy of roll of roll-ups, and where was I gonna go with this? Okay, so,various

[00:07:37] **Ben:** be. PCI compliant. You had to add a CSP to your checkout

[00:07:41] **Adam:** Yes. And, okay. And so, okay, so now, I, I mentioned one of them is script source, right?

[00:07:48] **Adam:** and so that, that kind of, to me is like the crux of the whole thing. Like, yes, there's ways, just like there, you know, there's ways to hack a computer by embedding bad code in A PDF, right? But the obvious one is scripts, right? yes, you could probably, there's probably vulnerabilities in CSS. There's probably vulnerabilities in images or whatever, but like the, the, the meat and potatoes of the hacking industry, I'm sure is JavaScript, at least on the web.

[00:08:11] **Ben:** So, In case you didn't know, it's the lingua franca of the web callback. Um,Spell kit something or other? I.

[00:08:21] **Adam:** it wasn't me. Um,so, script source, okay? So, you, you have to either like jump through amazingly high and difficult hoops and, and be your own credit card processor, which almost nobody wants to do. Or you have to contract that out to a company like Tim's company or Braintree, Stripe, Spreedly, you know, authorize that net, whatever.

[00:08:43] **Adam:** All these other companies, when you do that, when you contract out to one of these other con companies, basically they give you some JavaScript to put on your page, and you integrate that way so that it minimizes your PCI scope, and pushes most of it over to them. And, but they're giving you scripts, right?

[00:09:01] **Adam:** So that this is third party JavaScript that runs on your page and it's. I would guess 99 and a half times out of a hundred, it's not, here is the literal string of code that we want you to run in a script rock block. It's usually, here's the script, URL, embed this script on your page, and we will update it as necessary when we find a bug or when we wanna make a change or whatever, right?

[00:09:23] **Adam:** Like they just update code and it updates your site and you don't have a say.and so in order to make that, work in your CSP, you have to include a header that says, okay, I'm gonna allow Stripe to embed their JavaScript. Cool. Some of these providers then in that code that you have approved, go on to inject other JavaScript onto the page, right?

[00:09:43] **Adam:** They might run an eval or they might add, you know, like do document, do, add element and add another script tag to your page. Or like, probably a dozen other things that they could do. they might drop in an iframe, you know, who knows what, But, so that, you know, again, it spiders out, right? So you're like, okay, cool.

[00:09:59] **Adam:** There's this one rule that's breaking. When I turned on CSP, I gotta fix that. No, you fix that. You refresh the page and now there's six rules broken and you gotta fix those. And then you refresh the page and there's another nine rules broken. It's, it's incredibly frustrating.so long story, slightly less long, I got through all of those issues, and found that there were some scripts on the page that I was not expecting.

[00:10:23] **Adam:** And I was like, well, how does that work? How is, you know, we don't use Datadog. And we don't use, there's a service, I think it's called Crazy Egg, which is like, I don't even know. Like I looked at it and I was like, the F no, this is not going on our page. Like it's a service. You could pay for it. I think it does like analytics and it's trying to like find ways to make your site better, whatever.

[00:10:44] **Adam:** But it's like, I am not putting that on, I'm not embedding a script from crazy ag.com on my credit card form page. No. That could stay blocked by CSP. and I was like, how did they get that in there? Because, credit card pages, especially, we do not even let them control the skin for, right? Like, we'll, we do a customized version of the skin of the site, right?

[00:11:06] **Adam:** So it looks like it's part of their property. but it's, there's like one version that's within their control and one that's not so that we can use it on things like credit card pages and we have a pretty good guarantee that it's safe, right? It's not gonna have malicious code injected into it. As it turns out, one of the things that we had enabled for our customers was to use Google Tag Manager, which if you don't know, is like the successor to Google Analytics, right?

[00:11:32] **Adam:** It's just a more complicated, more capable platform for tracking analytics. And I only learned like within the last two weeks that apparently one of the features of Google Tag Manager is that it allows you to just inject whatever script you want into whatever pages you've got stuff going on. Yeah. Like, what the heck?

[00:11:54] **Adam:** So, yeah, that was a fun discovery. Like, just like we've got customers injecting their own scripts into our pages. However, even though I just like pooped on CSP and said it can be kind of security theater, now that I know that it's there, I'm really happy that I have CSP on my side. And I just was like, no, you can't load that script.

[00:12:12] **Adam:** No. You wanna load your fonts from, you know, whatever. Random site? No, you can upload 'em to our, you know, we give you a tool where you can upload whatever images and, you know, font files, whatever you wanna load up to S3. And it comes from our bucket and we serve it, we pay for it and, like just use our stuff.

[00:12:32] **Adam:** And so it's like a, like I said, it's a rollercoaster, right. I'm up, I'm down, I'm up, I'm down. But I'm, I'm happy to be able to block stuff, so.

[00:12:41] **Ben:** One of the things that I find very frustrating about the content security policy is that I feel like the terms that they use in the configuration are the most unintuitive possible terms. They could have selected it. It's like they didn't run any of that by anybody who wasn't, I don't know, like a security expert.

[00:13:02] **Ben:** And even when I go to the Mozilla docs to look up what I should be including, I read through it and it just, I feel stupid. I feel like I don't understand what it is and what the implications of the various,

[00:13:16] **Adam:** Yeah,

[00:13:16] **Ben:** you know, I don't know. It just seems like someone could have done a much better job on the words.

[00:13:21] **Adam:** yeah. The, the, the, I guess a big part of the reason that I call it security theater is because, all of the very modern payment, well, I, I'll get to the less modern stuff too, but all of the very modern payment methods that you, the PayPals and Venmos and all of that of the world, you can use and, and they're all made available through Braintree, is how we choose to implement them, right?

[00:13:43] **Adam:** So you just sign up for a Braintree account, plop in your Braintree credentials, and then as long as your Braintree config has all the right stuff set up, you can use PayPal, you can use Venmo, whatever, apple Pay, Google Pay, et cetera.however, those things in particular, for whatever reason. You have to basically open, you have to leave your backdoor unlocked all the time.

[00:14:03] **Adam:** Right? So for in your content security policy, for script source, you're required to use unsafe inline,

[00:14:09] **Tim:** Wow.

[00:14:09] **Adam:** and you are, or, or I think there was no, there wasn't one that I, that was required to use unsafe eval, I don't think. But, and then the other super frustrating part, so when I first started working on this, I was, I was learning the different mechanisms that you can use to sort of like whitelist, the, the scripts that you want to allow, right?

[00:14:27] **Adam:** So you can just, you could do the whole thing where you put all the domains and everything in the header. Or another nice approach is you can say, okay, here's a noz. Here's just a random string of characters that I've created at the beginning of every request. It will change as, as with every request that the S changes.

[00:14:42] **Adam:** And I'll just include that as an attribute on all my script tags. And that gives that script tag permission to run. And I just include the knots and the CSP header. And that way the CSP doesn't have to be six pages long, it's just here's the knots. which is great. But then, and you can even, like, there's ways to say, okay, I'm here.

[00:15:00] **Adam:** I'm gonna include Stripe and here's the knots that gives Stripe permission. And there's even a way in CSP to say, if I've given a script permission, then any scripts that it tries to add to the page are also, they like inherit that permission. Right.however, like I said, certain things require like unsafe inline and I don't, there's probably a good reason for it.

[00:15:23] **Adam:** It's above my pay grade, but you cannot use unsafe inline and nons at the same time. You have to choose one or the other.

[00:15:29] **Ben:** Oh, interesting.

[00:15:31] **Adam:** Yeah. Now, okay, so that's the, that's the new school being a pain in the neck. Right. Here's the old school being a pain in the neck. I believe 3D Secure is way more popular in like Europe where they do a lot of like just straight up bank transfers.

[00:15:44] **Adam:** Um.Yeah, so like in Europe, I think it's really common where like you just give your, your bank information to the website and they like charge, just like wire transfer sort of thing. I, I'm not a hundred percent clear on it, but that's my understanding right now.

[00:15:58] **Tim:** like Swift? Yeah.

[00:16:00] **Ben:** Sure. Yeah. Maybe that's a word. It's

[00:16:03] **Tim:** What the, that's what the banks use for their transfers. They don't use a CH network, they use a SWIFT network. It's more, it's, it's a lot faster. It's almost instant.

[00:16:10] **Adam:** Okay. Well, in order for 3D Secure to work, you have to have Frame source, star, like you just a big, and I understand why that is. It's because they're gonna open up a frame to the bank's website. So I guess for you to log into your bank and, and like approve the transaction or whatever. But still it's like. We couldn't come up with a better solution. Like, I don't know. It just, it feels so dumb. It's like, okay, well we're, we're doing all the security, but as long as it fits in this narrow criteria, we don't give a what you do.

[00:16:47] **Ben:** I was.

[00:16:47] **Tim:** It, it's, I find it actually kind of funny. Well, odd. I kind of question if you need to be doing that, right? I mean, you're not actually handling the card data right.

[00:16:56] **Adam:** You're right. We are not. However, if somebody were able to inject JavaScript onto our page, then through the magic of being on the page, they would be able to like watch other content on the page, including the, the content of iframes. Right. So even though it's,

[00:17:14] **Ben:** it's also not even necessarily that they can watch the content of the iframe, but they could, if they could inject content, then they could do an overlay over your iframes to do like click jacking or whatever the right term is.

[00:17:28] **Adam:** Yeah. So because we are quote unquote wrapping, I'd say quote unquote, that's me, me quoting, because we're kind of wrapping the credit card form and we are responsible for the page on which it renders. We have some security responsibility just for that page, to, to have an inventory of the scripts that are run there and to,

[00:17:48] **Ben:** I listened to an interview, it was last week, and I, I can't remember if it was Shopify or Stripe. I think it was Shopify. I think it was like the chief researcher at Shopify was talking about having them, them having to upgrade from PCI, version three to version four compliance. And a lot of the version four stuff is the kind of stuff you're talking about

[00:18:11] **Adam:** Yep.

[00:18:12] **Ben:** and the way that they're solving it is crazy.

[00:18:15] **Ben:** I mean, like it's, it's very complex. Basically what he was saying that they do. 'cause of things like Google Tag Manager and people wanting to have all these analytics and, and heat maps of where mice go and on the screen and like where people are hesitating and that kind of stuff. 'cause they wanna work on their conversions.

[00:18:32] **Ben:** The approach that they're taking, and I think this is still a work in progress on their end, is they lock the page down to a single script that they wholly own. Then they render like a virtual dom into a web worker that you can then run your scripts inside of. So when you're interacting or when the user is interacting with the payment form, it's actually replaying all of those events across the web worker divide inside that safe context that's not connected to the dom.

[00:19:06] **Ben:** You know, like they're still working on it, but he said it, it's like,

[00:19:10] **Adam:** this isn't in production, it's, it's just what they're working on or

[00:19:13] **Ben:** I think he said parts of it are in production, but they're, they're.

[00:19:17] **Tim:** sounds like witchcraft.

[00:19:18] **Ben:** I think it was, I think it was all like the event replay stuff they're, they're still working on, but there is, I think a web worker based separation of concerns between what they own versus what they, the customer can sort of Google tag manager into.

[00:19:33] **Adam:** Yeah, yeah,

[00:19:34] **Ben:** but I mean, he was, you know, just case in point about how complicated this kind of stuff gets. And I mean, you know, clearly their whole business is building e-commerce sites, so they're, you know, heavily, heavily, heavily invested in it, but it's just sounded terrifying.

[00:19:48] **Adam:** It is. It absolutely is. So that's my rollercoaster of a, of a week. what do you got going on, Ben?

## [00:19:56] Ben's Triumph

[00:19:56] **Ben:** I'm gonna go with a little triumph and a little failure. my triumph is that last week I wasn't on the podcast because I actually went down to DC District of Columbia for the CF Summit East Conference, which was just a one day free conference hosted at Caresoft, but. I think it was like run by Adobe, but it was hosted by Caresoft, quite understanding the separation there.

[00:20:18] **Ben:** And you know, but I did people stuff. I talked to people and, yeah, people pretty hard in the context of a 24 hour window. And, I, I, like, on the way there, I was really regretting going 'cause I've been, I just, I've, I've been like a little, a little depressed and a little anxious lately. And I was on the plane and I'm flying there and I'm like, the plane's getting lower and lower as we're getting closer to DC And I was just like, what am I doing?

[00:20:43] **Tim:** Oh,

[00:20:43] **Ben:** I don't want to be here. This is such a mistake. And, you know, once I was able to get there and then start talking to people, kind of decompressed a little bit and I was able to, to really to, I had, I had a good time and I saw people I haven't seen in a long time. So that was, that was pretty nice.

[00:20:59] **Ben:** But the, you know, the kind of dovetailing thought there is that I've just, I. I, I mentioned this on the previous show. I think that, I've just been very anxious lately and, and I think that like anxiety has kicked over into some depression and that depression has had some physical components. Like I'm, I've been very achy lately, and I think that's very much tied to the stress of the,

[00:21:20] **Adam:** Ha, have you tried chemicals?

[00:21:21] **Ben:** I I, yes.

[00:21:23] **Ben:** So I did start, I did just start taking something called Cymbalta, which is, like an anti-anxiety thing, but it also apparently has like a nerve pain component. So I'm hoping, I don't think it's doing anything per se. but maybe it is. I mean, maybe it could be much worse.

[00:21:41] **Adam:** Right.

[00:21:41] **Ben:** I've, I've, I've also been wondering, so there's a, a cannabis dispensary opened up just near me a little while ago, and I'm like, maybe could that help?

[00:21:49] **Ben:** Could I be taking gummies to sort of even my keel out? I don't know. I've, I've never really been a, I've never taken drugs before, like those kind of drugs.but I'm not against it. Like I don't have a moral issue. I'm just,

[00:22:02] **Adam:** right. Yeah, I, I wonder about that sometimes too. Like maybe like just CBD without the THC or something. Like, I wonder if there would be any

[00:22:11] **Ben:** Yeah. I, from everything that I've Googled, it says that there's basically no research on it in, in this capacity. You know, it's been, it, everything's been so illegal for so long.

[00:22:22] **Ben:** Um,

[00:22:23] **Tim:** Yeah.

[00:22:24] **Ben:** so, yeah,

[00:22:25] **Adam:** so I, I wanted to make a joke about, you know, so pretty infamously right now. Cory Booker, just held the house floor or the Senate floor for, for 24.

[00:22:36] **Ben:** right?

[00:22:37] **Adam:** it 25 or 24 and a half.

[00:22:39] **Adam:** Okay. It, whatever it was. He, he, he beat the record by a half hour. and I, I read an yeah, Strom Thurmond,

[00:22:46] **Tim:** Yeah.

[00:22:47] **Adam:** which is good.

[00:22:48] **Ben:** I'm glad that that's the record now. but, I read an AP article about like the, the, what he did to prepare. Basically he, like, he fasted for a couple days and like, was super dehydrated so that he wouldn't have to go to the bathroom while he was up there. I just assumed he had a diaper on or something.

[00:23:05] **Adam:** little bottle in his pant leg.

[00:23:06] **Tim:** I'm sure that's what Strom did.

[00:23:09] **Ben:** Yo, I can't go like half an hour without peeing, so it blows my mind.

[00:23:13] **Adam:** yeah, it's 'cause I drink like a gallon of water a day too, so, but, I wanted to make a joke, like, well, you know, to prepare for this, were you like, you know, trying to be super antisocial, right? Like. Put in, you know, build up some extra spoons that you have 'em to spend on the, the people.

[00:23:29] **Adam:** And then I was like, Hmm, that's just kind of Ben's baseline is like no interaction with anybody.

[00:23:34] **Tim:** Yeah.

[00:23:35] **Ben:** yo, it is totally my baseline.

[00:23:37] **Adam:** You can't have negative interactions.

[00:23:40] **Tim:** So, so how much did you talk about working Code Dev while you were out there?

[00:23:44] **Ben:** Well, I did see, Monty, uh, and Monty gave a presentation. I took a picture of him. So that was pretty exciting. And he, and he had a working code, sticker on his laptop during

[00:23:53] **Tim:** Yay.

[00:23:55] **Adam:** Way to go Monte.

[00:23:56] **Ben:** Yeah. He talked about, ai, like GitHub co-pilot and that kind of stuff,

[00:24:01] **Tim:** That's cool.

[00:24:02] **Ben:** which I think dovetails what we're talking about.

[00:24:04] **Tim:** I know,

[00:24:05] **Adam:** Oh, interesting that you bring that

[00:24:07] **Ben:** Nice transition, Monty.

[00:24:10] **Adam:** Good job. so yeah, I mean, basically, how do I wanna bring this in?

## [00:24:13] AI and the Future of Coding

[00:24:13] **Adam:** Like basically, you know, there's obviously AI is just continuing to grow and grow in popularity and people vibe. Coding has been a big thing lately, which is where like, people who have no experience coding or perhaps just choose not to use their experience, just rely entirely on like, giving directions to the ai, let it figure it out, do the thing.

[00:24:35] **Adam:** and I like this is not to say that Vibe Coding doesn't have a place. Like, we can get into that later if you want, but really I think that more what I wanted to talk about is like people being kind of panicked or overconfident and, and, saying like, a lot of engineers are gonna be replaced. I, I just don't think that's the case.

[00:24:55] **Adam:** I don't think that we are. You know, like a, a, a Lego brick that is a coder. I don't think that you just need a certain amount of coders and you tell 'em what to do, and your product pops out the other end. I think that we are a very critical part of the product development, process.

[00:25:12] **Ben:** I definitely agree with that and I, I'm definitely someone who's had a lot of anxiety about the AI stuff, which I do think actually has been contributing to the general angst that I've been feeling lately. But as someone who has been mostly watching from the outside, meaning that I use chat TPT from a chat interface perspective, but I haven't really dove into any of the co-pilot or kind of cursor AI or windsurf or all these other ones.

[00:25:40] **Ben:** I haven't, I haven't used it at that level yet, but just from what I've been hearing on podcasts, I, I do get the sense that the hype curve is, is starting to even out a little bit. It's not, it's not skyrocketing as much as I think it has been for the last year or so. I, I, there are a lot of people who are still extremely bullish on the AI and, and, but.

[00:26:07] **Ben:** I am seeing just some of those people pull back ever so slightly and be like, and, and talk more in moderation and more like, it's a, it's a tool. It's not a, it's not gonna revolutionize the industry per se. It's gonna revolutionize maybe the way you do work, but it's, so, I'm, I'm, I'm happy to see that. I'm happy to see some bit of measure, I think brought back to the conversation slowly,

[00:26:33] **Adam:** Yeah.

[00:26:34] **Ben:** and that makes me

[00:26:35] **Adam:** so yeah. One of the things that I mentioned kind of to bring this in is like, not that.

[00:26:44] **Adam:** Doesn't have a place. Right? So, a, a perfect example of this, west Boss from Syntax, said he vibe coded a game like a math game for his kids, right? If you're just making something for yourself and you don't wanna have to learn game development and you just wanna be like, make a 3D environment where you do math problems and blah, blah, blah, and like, you don't have to have tho that particular skillset, but it's not critical that it not have security flaws and not, you know, whatever have the potential to make your machine crash.

[00:27:12] **Adam:** If that's, if those are not requirements, then I think vibe coding is a totally fine thing to do, right?

[00:27:18] **Ben:** you think you could just vibe code your way to PCI version four? Compliance?

[00:27:22] **Adam:** I would like to see you try, honestly, and I mean, you and I were going, when we kind of proposed this topic earlier, you and I were going back and forth a little bit on like the ways that a human is just still, I. several orders of magnitude better than LLMs at, at, even the things that LLMs are doing, right?

[00:27:40] **Adam:** So an LLM is, is just a predictive text with certain parameters, right? A certain amount of context that you're giving it. and, and the ability to iterate, like, to, to be very specific. Like, oh, okay, I don't like that shade of blue. Change it. You know, you give that to an LLM and there's like a four in 10 chance that's gonna change that shade of blue and make other changes, right?and so like, there's just, I, I feel like there's so many things that, you know, I saw a video this week that based on the news of OpenAI getting more financing and, and the financial position that that puts them in basically suggesting or, or, predicting that, that based on that information, they think that.

[00:28:26] **Adam:** Sam Altman and OpenAI believe that they are on the cusp of AGI because they kind of have to be, or they're gonna be financially screwed. It was the thesis of this video.

[00:28:38] **Ben:** Interesting.

[00:28:38] **Adam:** and hypothetically if AGI does turn out to be a thing, and, and I, I guess for me, when I think of AGI we're talking about something that can hold a conversation has basically infinite context that it can hold.

[00:28:55] **Adam:** Right? You can say just, okay, start collecting context. Everything we talk about, don't forget it, and, and can iterate and, and learn and improve itself, right? That's kind of, I guess for me, what I'm thinking about as the, the baseline for what I would consider AGI. and crap, I forgot where I was gonna go with that.

[00:29:15] **Ben:** I, one of the things that I find so fascinating, just kind of reflecting upon my own experience with AI is how fast the razzle dazzle wears off for me.Um, and I remember when I first got an Alexa, and I don't have an Alexa anymore. I, I, I, I'm not, I'm not a big automated workflow kind of person, just generally in my life, but we got, everyone at work years and years ago, got an Alexa dot or something like that.

[00:29:43] **Ben:** and I remember turning it on and you ask it what the weather is and it tells you, and you're like, oh my God, this is crazy. And then I asked something, I'm like, oh, you know, tell my wife how attractive she is. And it was like, I don't understand the question. And I was like, all right, I'm done. Like, this is like no longer fun anymore.

[00:29:59] **Ben:** It's like back when you were a kid, you were getting like the, like the spelling speaks to try and curse, you know, and then it won't do it. And you're like, I'm done. I, so, so fast forward to the Chat GPT and, and all of the stable diffusion stuff, like the first time you see a generated image, it's like mind blowing that, that worked so well.

[00:30:20] **Ben:** And, and like you, and then I, like, I can only speak for myself here, I'll generate a couple of images. And it's slow enough in the image generation that I basically lose interest. Like I have to flip away to some other tab to go do something else. And I'll just literally forget that I was in the middle of generating an image for hours, and then I come back to the tab like, oh, right.

[00:30:41] **Ben:** I totally forgot I was even trying this. And I, I, it's, it, it's the same with the, with the text-based chat, like the first time you try it, you know, there was that guy who got fired from Google, right. Who, who was like, oh my God, it's, it's sent in. And it's aware because like, it's just so mind boggling. The first couple of times you see it and then once it starts to make a couple of mistakes, you're like, nah.

[00:31:04] **Ben:** Yeah. You're like, it's, it's a very specific kind of thing. And I don't, I don't know, I'm just, I'm blown away at how fast I think I return to a state of like, it's interesting, but it's not mind blowing anymore.

[00:31:21] **Tim:** I, so here's my thoughts on it. So I think large language models are probably the, in my opinion, one of the worst applications of ai, right? One. So, I mean, what's faster to, to go to, like some sort of AI service and say, what's the weather? Versus you have an app on your phone, you just press a button and it tells you the weather comes up.

[00:31:45] **Tim:** Right? That, that's a lot more efficient, right? To press a button for an app that, that, or just even look at your phone. It'll sometimes, you know, in my background it would be like, you know, 92 degrees sunny, it's Georgia. It's always that way. Uh, um. Yeah, it's just an image. You don't,

[00:32:00] **Tim:** Yeah, it does, it actually change. So I, I think large language model and they're really reaching the limits on how much they can scrape.

[00:32:09] **Tim:** Where I think AI does its best work is things that humans are really bad at. Like,

[00:32:17] **Ben:** Hmm.

[00:32:18] **Tim:** so huge number crunching, looking for relations and then what seems like seemingly random information and, you know, drawing conclusions that a human just wouldn't come to. Like the whole protein folding, I think we talked about this before, it's a YouTube video about how they were trying to create these new protein folds to solve problems.

[00:32:38] **Tim:** And it's like they've been doing it manually for decades, and all of a sudden AI came along and just like blew it away. You know, like

[00:32:45] **Ben:** Yeah, that sounds awesome.

[00:32:46] **Tim:** in, you

[00:32:47] **Adam:** just it's like, okay, here. I did all of them. Do you want anything else?

[00:32:50] **Tim:** So, I mean, if the fear is that AI is gonna take our jobs, it's always the fear with new, with new things, I think will it take some people's jobs?

[00:32:58] **Tim:** Yeah. I mean, you're, you're kind of an artist who's kind of a hobbyist, who's like, has a side gig who's gonna create, you know, little cute graphics for you. They're probably not gonna have a good stream of income because like you can just go to a, a, an image generator and give it a prompt and go, oh, that's good enough for me.

[00:33:18] **Tim:** But, but I mean, it's not gonna replace artists, real artists. Right. same thing for like some con you know, content generation. I read, I read, you know, in a corporate world I see a lot of marketing generated crap and I, and it's like, oh, that's just marketing speak. They, they, they don't really know the product.

[00:33:36] **Tim:** They're not the closest to it. They, you know, you know, they're trying to sell it and they don't wanna, they don't wanna lie. At the same time, they also don't wanna, like, I. Tell people like, yeah, we're really good at this, but not so good at this. So they, you know, there's marketing speak,

[00:33:49] **Ben:** Sure, sure.

[00:33:50] **Tim:** large language model is actually pretty good at that because they don't, they're in the same boat.

[00:33:53] **Tim:** They don't seem to know anything about the product either. They're just like, they're just like, eh. In general, what do you usually say about a product? That sounds good.

[00:34:01] **Adam:** Right.

[00:34:01] **Tim:** So it's, it's, I think it will take some marketing jobs. uh. I think about so much of, so, so much of the hype is, is all about either content generation or what feels like with the vibe code and stuff. The sort of zero to, to say zero to one is almost like maybe overselling the step. It's like zero to 0.5. But so much of the work that I think so many of us do is, is in the like back end years of maintenance of an application.

[00:34:32] **Ben:** Like this isn't, I'm not just testing an idea. I actually have, you know, years worth of an application built and I'm maintaining it, I'm involving it and I, I can't tell you how many times in my work. I sit and I just kind of stare at the screen and think about what it is that I'm even trying to do. Like forget about even trying to articulate it in a well-crafted prompt to an AI engine.

[00:34:56] **Ben:** I'm like, I'm, I'm almost not always clear on what the problem solution space is, and I have to think about it from the user's perspective, and I have to think about it from a technical's perspective. And I don't know, there's just like a lot of thinking that goes into building an application and maintaining an application that I, I, I, it doesn't, it doesn't feel like it dovetails really well with, with everything that people seem to be excited about.

[00:35:21] **Adam:** Yeah, I agree.

[00:35:22] **Ben:** Which I think, you know, one of the things when I talked about the kind of hype cycle starting to crescendo, I don't know if that's the right metaphor there. one of the things that I have heard some people say is that they're continuing to find the best use case for it is in the kind of. Very powerful auto complete because especially in a large existing application, it can't just willy-nilly make a lot of changes, but within the confines of one or two files, it is nice to just have some really powerful auto complete for functions that you're writing and, and like that's still good.

[00:35:59] **Ben:** It's not revolutionary, but it's still better than they had before.

[00:36:03] **Adam:** Yeah. I mean there's different, like it's got a different skill level for different types of tasks, right? Things that are obvious but tedious. It's really great at,

[00:36:11] **Ben:** Yeah. Yeah.

[00:36:12] **Adam:** yeah, I, I did kind of think about what, or, or remember what I was. Where I was headed with the comments about AGI. Right. So, before we started recording, you and I had thrown back and forth a couple of ideas, like ways that, we are better than LLMs.

[00:36:27] **Adam:** And the reason I was heading into AGI was like, you know, potentially it could catch up to humans, but like, we haven't seen any evidence of AGI actually being anywhere close to possible yet. and I thought maybe we could riff on, you know, just some of the ways, like the, the, maybe, maybe some of 'em are obvious, some of them are less obvious, but the ways that, we still beat LLMs, at our jobs.

[00:36:49] **Adam:** Right.

[00:36:50] **Ben:** Well, if I could riff for a second and 'cause this dovetails with my kind of mental state right now.

## [00:36:55] The Role of AI in Therapy and Personal Efficiency

[00:36:55] **Ben:** So one of the things that I have heard people say, or at least theorize is that the LLMs could be good, especially with the voice synthesis, to replace therapists. And so when I, maybe replace isn't the right word, but like augment the pool of therapists, when I was starting to feel very anxious and I,

[00:37:16] **Adam:** This is, this is straight out of her, isn't

[00:37:18] **Tim:** Mm-hmm.

[00:37:19] **Ben:** so, so chat GPT, at least on the mobile device, I assume the desktop as well, but you can start a voice based chat on the chat GPT app.

[00:37:27] **Ben:** So I thought to myself, okay, everyone's talking about how great this kind of stuff is and, and how it can help with therapy. So I was like, you know what, let me see if I can talk through some of my anxiety with chat GPT, and it was like immediately disappointing because it, it's,

[00:37:43] **Tim:** Just like real therapy.

[00:37:48] **Ben:** you know, what you, what you, the, the very first thing that you realized, or at least that I realized was, is that it's talking to you like it's chatting with you. Like, like it's, it's, it's putting voice to a text chat, but the text chat doesn't have any human cadence to it. Whereas if you're talking one-on-one with a human being, you can, one, you can read the room, and two, you have an understanding of, of the acceptable back and forth cadence in a normal conversation.

[00:38:17] **Ben:** And the, the spoken Chat GPT did not understand any of that. It was basically, you know, it's like, help me work through some of my anxiety here. And it would gimme like, here's 10 things you might wanna consider and it would gimme 10 bolded lists. I'm like, whoa, maybe just talk through one of them.

[00:38:33] **Tim:** Thanks, Buzzfeed.

[00:38:35] **Adam:** that's

[00:38:35] **Ben:** Yeah, yeah.

[00:38:36] **Adam:** I was heading to. Yeah.

[00:38:37] **Ben:** And, and so yeah, I feel like it's, it doesn't, there's no, there's, I don't wanna say like it's so,

[00:38:45] **Adam:** and more like trying to One shot the answer.

[00:38:49] **Ben:** but yeah. Yeah, but it's not, it's like, Tim, I think a couple of weeks back had posted, I forget, I think you said you had took a transcript from the show and ran it through the Google notebook

[00:38:59] **Tim:** No, no, I, I asked it to create like a Black Mirror episode.

[00:39:03] **Ben:** was it, it was

[00:39:03] **Tim:** Oh, no, no. You This show, this show.

[00:39:05] **Ben:** Yeah. Yeah, yeah, yeah. And, and I went and I listen to it and it's just, it, it's like it's soulless. Like it, it sounds like people, but it's not people. And you can feel it,

[00:39:16] **Adam:** Mm-hmm.

[00:39:17] **Tim:** Right. But that's now, I mean, what if they get better?

[00:39:20] **Ben:** I guess.

[00:39:21] **Tim:** that's the question.

[00:39:23] **Adam:** So you were talking about marketing stuff. I guess it was you, Tim, saying how it, like, that's, that's kind of where it shines. And honestly, I think that's because it's like 80 ish, 60% of what it scrapes off the internet. Like that's what the internet has become. It's just like marketing of all the things.

[00:39:40] **Tim:** Well, let's, let's assume that using large language model in like in our job, in coding makes you more efficient by some percent, right? I don't know what that is right now. I've not seen, you know, chat GPT and co-pilot. I mean, they're can be pretty good, but a lot of times you gotta work on things. Let's say it gets better and it gets, like, makes you, you know, 10 times more efficient.

[00:40:08] **Tim:** I mean, in the natural order of things, when something gets more efficient, that just, that's no longer like a superpower anymore. That's just is the level, right? That's the baseline. And so, you know, people are like worried what they're gonna, it's gonna take their job. But no, I, it's still gonna need to be people who are working with the large engine model and the tools, basically, it's just, it becomes a tool that you use to code, but you're, but you're still gonna have to, whenever it can't give you the right answer or it's answer has holes in it, you still gotta fix it.

[00:40:38] **Ben:** Yeah,

[00:40:39] **Tim:** And so that you, you, I don't think you'll ever gonna get around that. I hope not, but, you know, but that's gonna become the standard's. Like you could, can assume that a project that would maybe take 10 developers now might take five for the same time period. And so you just become, as a company or as a, you know, institution needs to become more efficient.

[00:40:59] **Tim:** And that just becomes the baseline. And then, you know, people create new things and make it even better.

[00:41:05] **Ben:** I have a lot of anxiety about like, the efficiency stuff that am I missing out? I don't feel more efficient When I, even when I go to Chat GPT and I ask it questions, I feel like it's interesting and it helps me think through stuff, but I wouldn't, I don't yet feel like it makes me more efficient.

[00:41:27] **Ben:** It's more like. I dunno. It helps me think, but I, I, I don't know if it makes me more efficient. I don't know yet. I, I think a lot of that comes from the auto complete stuff and I haven't gotten to that point yet. And I think maybe I'm, I haven't felt that magic yet.

[00:41:41] **Tim:** There's, there's really no standard for it now. It's like I've read articles where people are explaining how they'll do a, a greenfield project using AR or how they'll take like a legacy, code base and run it through cursor AI and now it's learned on your code and it can answer questions and like, how would I refactor this?

[00:41:57] **Tim:** Or how would I, you know, create unit tests for these functions? And it, it'll help with that. But it's like, it all still seems so fragile right now. I don't really wanna spend a lot of time creating. 'cause if I do it for me, I, I would've to do it for the whole company. Like, here's the process, here's how we use AI to code, here's our coding standard.

[00:42:16] **Tim:** Well, I, I have no confidence that six months from now that standard would be even be valid. It would be have moved on or be irrelevant or the product is no longer there. That, that, that, that the AI product. So yeah, it, it's all just. Still a whole lot in flux for me to, to be able to hang my hat on it and say, yeah, here we need to add this to our toolbox.

[00:42:40] **Adam:** th

## [00:42:40] The Skill of Choosing the Right AI Tool

[00:42:40] **Adam:** at I think that is the skill that's gonna become very necessary as a developer. Right? You, you, the skill is knowing which AI to use and being versed in interacting with it and getting it to do what you want. Right? And that's, that's just like, you know, before we had Stack Overflow, we had ex expert sex change.com, where we could go to get our, our code.

[00:43:08] **Tim:** Experts exchange, is that what you said?

[00:43:10] **Adam:** oh, is that what it is?

[00:43:13] **Tim:** Okay. Rebek

[00:43:17] **Adam:** yeah. I mean, that's, you type it in. That's what it, that's where it goes.

[00:43:20] **Tim:** and don't island too.

[00:43:24] **Adam:** but you know what I mean, like the tools that we use change over time, and that's part of our job is like understanding what the current tools are and understanding how to use them to our benefit. And some of us are better at it than others, and that, you know, is often not always, reflected in the jobs that we get and, and what we get paid to do those jobs, right?

[00:43:45] **Tim:** Mm-hmm.

[00:43:46] **Ben:** That's the thing that worries me a little bit is that I think historically the idea of picking the right tool for the job has been like 80% picking the tool that you're most familiar with and like 20% actually picking the right tool for the job. Because just knowing the tool sufficiently makes you pretty effective in it.

[00:44:10] **Adam:** Mm-hmm.

[00:44:11] **Ben:** And I'm worried is the right worried is, is, you know, a personal choice here. I'm worried for myself that that will no longer be the case. That just being comfortable with a tool is no longer sufficient to make it the right tool. ' cause if there are tools that are genuinely better, like significantly better then, then actually knowing those tools and being comfortable with them gives you, or could give you a much better advantage.

[00:44:43] **Tim:** Yeah. Think that's what all these companies are spending these billions of dollars for. They wanna be, they wanna be that person at the top at the end of the day, right? But I mean, some are gonna win, some are gonna lose. Some will be the VB scripts of the world and some will be the JavaScripts.

[00:44:57] **Ben:** and then I wonder too, kind of, how much of this do I need to actually care about? Or do I just wait for the industry to pick a winner and then just go with that? Like, I don't know much about compiling JavaScript and packaging JavaScript. Like there are just really bright people who have figured this out and have said, you know, you should have to just use.

[00:45:18] **Ben:** Parcel or roll up or roll down or, or vet or es build or you know, like just really bright people have, have kind of paved the cow paths and like, I still don't know anything about it, but I'll use the tools that they build and reap the advantages. And is there a way that I can like not have to think too deeply about which AI tools are the best for now and just kind of wait for winners to emerge and then just draft on their tail tailwinds.

[00:45:47] **Ben:** Is that a, I dunno if that's the right metaphor. Something like that.

[00:45:50] **Tim:** coattail.

[00:45:51] **Adam:** Yeah, no. Neither of those is right, but okay. Let's just move on.

## [00:45:58] The Hype Cycle of AI

[00:45:58] **Tim:** Well, I mean, in the, in the, you talk about the hype cycle. So part of that whole cycle is, you know, buildup, the, the hype, and then there's the, the pit of despair. Like they go into afterward and then after afterward that

[00:46:10] **Adam:** wait, I thought it was the, it's the trough of disillusionment,

[00:46:13] **Tim:** Yeah, that's tr Yeah. Yeah. I was, I I, I was quoting, I was quoting Princess Bride, sorry.

[00:46:18] **Tim:** yeah, the trough

[00:46:19] **Adam:** see how you get them mixed up.

[00:46:20] **Tim:** Yeah. And then, and, and then it kind of plateaus up a little bit. Profit, and then things kind of level out. So I think, you know, we're probably, like you said, we're, we're past like the peak hype part of the curve. We're sliding toward a little, toward the, disillusionment because, you know, unless something really major happens, but eventually we're gonna hit that, that that level plateau of profitability, and that's when you buy in. Unless you just want to be, unless you wanna stake your claim and say, I'm gonna be an AI expert, I'm gonna be the one at the forefront. You know? Unless you're like that early adopter kind of person who really wants to stake your name like you did on Cold Fusion way back when

[00:47:01] **Ben:** well that hype cycle's still going up, so I'm pretty

[00:47:03] **Tim:** is, is it really I I think it's very well in the profit category according to Adobe, the boring old prophet.

[00:47:10] **Ben:** Oh man.

## [00:47:12] The Role of AI in Software Development

[00:47:12] **Ben:** I mean, at the end of the day, people need to talk to people in order to get software built and, and you'll never be able to replace that, I don't think.

[00:47:21] **Adam:** I mean, honestly that was the entry point for my thought process on, you know, okay, so hypothetically if they replaced all of us with LLMs, right? So your manager, instead of coming to you saying, I need you to build this feature and here's a rough idea of what I want you to build, you know, gimme a rough draft so that I can kind of alter your, you know, point you in a better direction than where you start.

[00:47:44] **Adam:** That's kind of my process at work, right? Like, here's a rough idea of what I need, figure it out and gimme a rough draft in three days. instead of that, what is your manager gonna say to the LLM? Right? They're gonna have to get really, really good at prompting the LLM just to get that first draft and then the whole iterative process begins, right?

[00:48:03] **Adam:** And like, I think that honestly.even just as a rough starting point for a discussion, like go, it's almost like a scene at a office space, right? I take the specs from the managers and I bring them to the LLMs. Like just translating from manager speak to LLM speak and being able to get something useful out of it is gonna be a useful skill.

[00:48:24] **Adam:** and then, and then there's a lot to build on from there.

[00:48:28] **Tim:** Yeah,

[00:48:28] **Adam:** you know, like the three of us, I think each of us has at least 10, if not more years in the industry. and, and like that's a lot of context that we're bringing into those conversations, right? Like there are things about me that were shaped from my internship while I was still in college that affect how I think about code today, right?

[00:48:48] **Ben:** And that's, that's for me, that's a lot more than 10 years ago. You have more than a hundred thousand token window is what you're

[00:48:55] **Adam:** exactly. And you don't run out in a day.

[00:48:58] **Ben:** One of the, one of the things that I hear people talk about on podcasts now regarding the AI stuff is that. It's, it's almost not so much that they're iterating on a single solution, it's that they're completely blowing away a solution that doesn't work and starting over. And that the AI can do that process so quickly in quote, so

[00:49:19] **Adam:** Like going from V zero to V one.

[00:49:22] **Ben:** Yeah. And then, and then like, or you don't like V one, then just like completely scrap it and start again, and then you don't like that. Completely scrap it and start again. And I don't, maybe it's just 'cause I haven't seen it in action, but that feels like a, like a multiverse where you're just randomly opening doors to see what that multiverse looks like.

[00:49:42] **Ben:** And if you don't like it, choose the next one. But there's an infinite number of multiverses.

[00:49:47] **Tim:** And all of them have problems.

[00:49:48] **Ben:** yeah. Like, like how do you know which is the right one that you hit without building it up from, you know, we, we've talked on this show a couple times about, GA's law. I think it is, where it's like a. A complex system has to be built from a working simple system, more or less, and the whole AI generating the V one of something feels very much like it is the antithesis of that.

[00:50:16] **Ben:** And maybe it just proves it, but it doesn't, like my gut says that starting simple and evolving still makes the most sense, but

[00:50:26] **Adam:** I honestly think that as things stand right now, no LLM is capable of building software at the level that we need it to be built as a professional today. Right? There's just so many aspects of it, right? Like, yes, you can write the code, but can you mail also make sure that it is PCI compliant and doesn't have any SQL injection vulnerabilities and is performant against the database and.

[00:50:51] **Adam:** Has good user experience and good accessibility properties

[00:50:54] **Tim:** And

[00:50:55] **Adam:** on, on and on and on. Yeah. there's so many different aspects that like, we're just expected to be able to do. Right. Right. Outta the box on V one. and it has automated tests.

[00:51:07] **Tim:** Right.

[00:51:08] **Ben:** That's the one that I don't understand.

## [00:51:10] Challenges in Automated Testing with AI

[00:51:10] **Ben:** People talk about the, do you, you know, you mentioned that the AI is really good at doing the predictable but tedious stuff and writing automated tests is the thing that gets brought up a lot. And I, I have, you know, you know, I have one, not a lot of experience with automated tests and I have zero experience with having AI generate tests, but.

[00:51:34] **Ben:** I will say that I've heard enough people over the years talk about how subtly hard testing is and how designing the right types of tests to test the right types of things is actually quite challenging. I have trouble in my head understanding how an AI can just do that for you.

[00:51:54] **Adam:** Yeah, I mean, I don't think it's ever gonna, what we have today is not capable of capturing all of that nuance For sure. however, I don't think that that nuance manifests itself in 99% of your tests, or, that's not to say that it is definitely not at all used in 99% of your tests. And only that 1% has the nuance, I'm just saying. What am I saying? I'm saying that, you can get by, you know, you can get 80% of your testing done with pretty rote, just like basic mechanical. Here's a function, here's its inputs. I need to be, you know, it needs to take a positive number, a zero and a negative number and, and be able to pro produce valid output based on any of those inputs.

[00:52:33] **Ben:** Right. Okay, so may maybe what I don't understand is the level of prompting that people are using to generate the automated tests, so that, that, that's a blind

[00:52:43] **Adam:** a lot from, from tool to tool.so I, you know what, I, I will promise you a trip report. S

## [00:52:49] Skydiving App Update

[00:52:49] **Adam:** o I've been working on this skydiving app. It's actually, the working on it part is going really well. I've been, I, I created a, like a, I'll call it a small group, of people from the drop zone, like basically people on the board, the president, our, our former treasurer, and somebody else.

[00:53:05] **Adam:** And, I'm just like, I, I have a little Facebook group with them. I sent them a link to AGItHub gist that has like, this is my to-do list. And I was like, if there's anything on here that you don't think that we need on day one, then point it out and I'll defer it and we will, you know, I can manually make those data adjustments as needed.

[00:53:22] **Adam:** In the meantime, whatever. Like, I, I wanna focus on just the things that we need. 'cause there's a specific event that's happening that we wanna be able to use this for. and so I'm like, if, if you don't think we are gonna need it on that day, if I can, if I can hard code that data in or whatever, like I'll do that in order to make, make the, the deadline here.

[00:53:40] **Adam:** So I said, I've got the small group, I've sent 'em a to-do list and I've been sending basically nightly, not always every night, but you know, it'll be like three nights on one night off, two nights on, two nights off, one night, whatever. but I, I'll just send 'em updates like, okay, here are the things that I did.

[00:53:54] **Adam:** This is what I'm planning on working on next. And it's been going really well. Because I'm on a little bit of a tight deadline. I have been skipping the automated testing. So, but I do wanna have it, do wanna have it. I do see the value, and I am like, that might be something that I try to do when I don't feel like I have the energy to like, sit down and focus on it and, or, you know, maybe, so when we, when my wife and I were watching severance, like I wanted to give a more significant portion of my attention to severance than I would for an old episode of Top Chef or whatever, right?

[00:54:26] **Adam:** Like, and so, those nights I would not be working on the project, but that night maybe I could have said, Hey, here's a, a, a data access object. Write me tests for this. Right? And I, I could have let it do its thing and like checked in on it when we would take breaks to tuck the kids in or, or go to the bathroom or whatever.

[00:54:45] **Adam:** And I, I, I think that'll be a useful thing to do. And then also, I do fully intend to have tests once this thing is quote unquote, like V one.and so if what I have to do at the end is just circle back and like add test in mass, then that's what I plan on doing. And I plan on testing out the, the prompting to generate the test as much as possible.

[00:55:07] **Adam:** I know I started this whole project trying to like get as far as I could, with only coding via prompting, which I, I'm not sure I would consider vibe coding because I was, I had very specific requirements. It's like, I want you to do it this way. I want you to use this library. I want it to be SQL injection proof, I want, you know, all these things.

[00:55:26] **Adam:** and I, I feel like that's just vibe coding is like, make it cooler,

[00:55:30] **Ben:** Yeah, yeah, yeah.

[00:55:31] **Adam:** so, I, I will definitely continue to work on this and I will follow up with how it does it test generation in particular. I did, I felt

[00:55:39] **Ben:** curious. I'll be

[00:55:40] **Adam:** Yeah. Yeah. I felt like I hit a wall pretty early in the process. Like it was able to get all the scaffolding in, right, okay, let's get all the library, you know, getting Tailwind and TypeScript and V and cell kit and all these things, like all hooked up together, get the config files.

[00:55:56] **Adam:** All right. It did a great job at all that, which was super nice to not have to like, worry about getting all that configured. Not that it's that hard on Spel kid in the first place. Let me just be honest. Uh,but

[00:56:06] **Tim:** you, you made it about 30, 40 minutes into the show before you brought up Simul Kit.

[00:56:10] **Adam:** hey, Ben did it first.

[00:56:12] **Ben:** Yeah. I dropped it early.

[00:56:16] **Adam:** but yeah, I mean, like I said, I'll give a trip report. I'll let you guys know. So I did hit that wall and basically from there I've just been doing everything manually and I will circle back and try to start over, not start over the project, but start over the, the prompt only approach to testing when I get there.

[00:56:33] **Tim:** That'd be, yeah. I look forward to hearing about that. Did you hear about they, they ran, a Meta Llama AI on a Windows 98 machine with only 128 megabytes of ram. Did you see that article

[00:56:45] **Adam:** not hear that. No.

[00:56:47] **Tim:** They took an old 98 Windows 98 machine and ran, it was a very modified, llama AI version, but yeah, they got it, got it working.

[00:56:55] **Tim:** So yeah, back in 1998, we could have been doing ai. We had the power, we just didn't know how.

[00:57:01] **Adam:** Did it answer every question with Dude? You're getting Adele.

[00:57:07] **Ben:** All right. Should we,

## [00:57:08] Patreon

[00:57:08] **Adam:** Alright, le, let's wrap it there. so this episode of Working Code was brought to you by the pit of Despair. Anybody want a peanut

[00:57:15] **Ben:** What that feels like. Two different references.

[00:57:19] **Adam:** from the same

[00:57:20] **Tim:** Same, same movie.

[00:57:22] **Ben:** Anybody want a peanut?

[00:57:24] **Tim:** That's

[00:57:24] **Adam:** not gonna spell it out for you. We'll get into it in the after

[00:57:26] **Ben:** Okay. Okay.

[00:57:27] **Adam:** to. And listeners, like you also brought this episode to you anyway, it's like PBS but better. and listen, if you're enjoying this show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon.

[00:57:41] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our, top patrons, Monte and Giancarlo. You guys rock. and if you'd like to help us out, you can go to patreon.com/workingcodepod, send a few dollars our way. We will reciprocate and send a few after shows your way.

[00:57:59] **Adam:** And when I say a few, I mean all of them.I guess this is a good time to mention too. the, Patreon after show, that whole like podcast feed is moving thing hasn't changed at all since last week or last couple weeks. I've been focusing on this guy to having app super hard and have not had a chance to look at it.

[00:58:15] **Adam:** We again, we haven't until like May to get that figured out, so we got time. But it is coming. Keep your watch this space,

## [00:58:22] Thanks For Listening!

[00:58:22] **Adam:** after show. I mentioned that, looks like, I don't know who's that typing. That's Ben. Ben wants to talk about TV and the collective consciousness, so I guess we're gonna get into that and I, yeah, there's, there's all kinds of fun stuff we talk about in the after show, and if you wanna know about it, you're just gonna have to buy the after show.

[00:58:38] **Adam:** You do that by going to patreon.com/workingcodepod. That's gonna do it for us this week. We'll catch you next week and until then,

[00:58:46] **Tim:** Remember, you're special. You are a coder, and doggone it, your heart matters.
