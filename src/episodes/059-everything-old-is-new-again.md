---
title: "059: Everything Old Is New Again"
description: "As an industry, we're not 'rediscovering', we're 'Yes, and'ing'. Everything old is new again because the context is always changing and is in need of new consideration."
date: 2022-01-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/059-everything-old-is-new-again/id1544142288?i=1000549050593"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

It's easy to be flippant about how often our industry seemingly "discovers" the programming practices and paradigms that experienced engineers have been talking about for _decades_. But, the truth is more complicated and nuanced. The landscape of the web is evolving at a breakneck speed; processing power and storage capacity are going up while costs are coming down; and, the needs of different applications are beginning to diverge massively.

As an industry, we're not _"rediscovering"_, we're [_"Yes, and'ing"_][yes-and]. We're constantly learning up on timeless techniques and then trying to apply them to the new constraints and pressures of the modern web. Some of these experiments are going to seem familiar; but, each step in this journey is an attempt to answer a new question or speak to a new problem. Everything old is new again because the context is _always changing_ and is in need of new consideration.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[yes-and]: https://en.wikipedia.org/wiki/Yes,_and...
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/059-everything-old-is-new-again.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** So imagine if like, I know Adam, you like doing like woodworking, what if you got like really good using, you had a lay, then you had this and that and whatever.

[00:00:07] **Tim:** You're like, okay, cool. I can really make some cool stuff. And then like five years from now, they're like, okay, take away all these

[00:00:12] **Adam:** Yeah.

[00:00:13] **Tim:** We're going to give you all these other tools that you absolutely don't know how to use and now build

[00:00:18] **Adam:** yeah. And all the directions are written in Japanese and

[00:00:21] **Tim:** Exactly. Right. Yeah. And I just think this is just the nature.

[00:00:25] **Tim:** It's kind of what I find exciting about programming is because it's like, it's always, it's new frontier every single year.

## [00:00:52] Intro

[00:00:52] **Adam:** It is episode number 59. And on today's show, we're going to be talking about the cyclical nature of trends and pressures. But as usual, we're going to start with our triumphs and fails. I guess I should mention up front since I usually forget to mention it. Carol couldn't be with us tonight.

[00:01:05] **Adam:** she just had a scheduling conflict, so it's just the three guys. but, other than that,

## [00:01:09] Adam's Triumph

[00:01:09] **Adam:** I'm going to go first. And, I know last week I said, as my goal or maybe it was two weeks ago, my goal for this year is to take on TypeScript and I dove straight into the deep end. My triumph this week is I've been doing TypeScript for the last two or three days now.

[00:01:25] **Adam:** it was a little bit of a steep learning curve that first like half day day into it. But the last couple of days have been amazing. I'm loving it. For example, the error that I keep finding that I'm making over and over that it is pointing out to me before I ever even think about running the code to test it is when,uh, Use, like call a function, that's returning a promise, but I forget to use the await keyword.

[00:01:53] **Adam:** It's like, oh, Hey, this thing is returning a promise and you're treating it as if it's a variable. That's not a promise. And you need to resolve that. It points that out to me and I'm like, oh yeah. Hey, thanks. Thanks for being a prototype script. So that's my triumphs type script is awesome as AAF.

[00:02:09] **Ben:** Nice. I know in the chat, I had mentioned classes the other day as a modern JavaScript technique. And you had

[00:02:15] **Ben:** mentioned the classes

[00:02:16] **Adam:** I poo-pooed them.

[00:02:17] **Ben:** create as many problems as they solve. And I know a TypeScript, I think you'll find at least on the angular world. I don't know if it's going to be the same in your area is very classic.

[00:02:27] **Ben:** Or at least it seems to be much more class heavy. it'll be interesting to see how you receive that or if maybe in the react world. Cause I know they're very type script-based these days. I guess they're still very functional components, so maybe classes don't even come up.

[00:02:41] **Adam:** Yeah, well, this project isn't even a front end thing. It's a Lambda function. So, it's not even react or anything like that. It is just functions. And I have written most of the types that I've written have been like the interface keyword. I know that there's type and interface, and they're very, very similar, a lot of overlap.

[00:02:58] **Adam:** I don't know exactly what the differences are because I haven't run into any yet. But, yeah, so

[00:03:05] **Tim:** When you say it's awesome. A F I always, I read something that says, if you want to have a laugh, anytime someone says AAF, instead of what, obviously it actually stands for just pretend it stands for as foretold.

[00:03:19] **Adam:** I like that.

[00:03:20] **Tim:** This burrito is great. AAF as foretold, indeed by burrito is awesome.

[00:03:28] **Adam:** Yeah. So if that's I just riding high on the, like beginner gains in JavaScript, right? Like to relate it, to like working out their beginner gains, I'm loving it. So that's me. What do you got going on Tim?

[00:03:41] **Tim:** So

## [00:03:41] Tim's Triumph

[00:03:41] **Tim:** I got two triumphs, one personal one professional has taught with the professionals. So I'm trying to find that balance. I've been sick as, feeling better, but I'm still not a hundred percent. I'm just lacking energy. but it's the beginning of the year. And begin of the year is a lot of kind of administrative stuff that I had to take care of a lot of beginning of the year planning and budgeting and reviews and things like that.

[00:04:03] **Tim:** But, so I struggle with finding the balance of the working on the code, which I want to work on. Right. That's what I enjoy. But at the same time, because it's my happy place. It makes me. Put off the hard stuff, right? The stuff that I find harder, which is those more administrative things that don't give me that endorphin rush, that coding gives me, but I've been working the balance, keeping both sides of my brain happy.

[00:04:27] **Tim:** And, so I've been happy with that. And just getting back to work and actually feeling productive rather than feeling like I want to go back to bed because I've been sick. So that makes me feel good just to that. there's the, things are looking up in that regard and then on the personal, so today my, my son's a senior in high school and his principal called me today and said,I'm like, okay, what do you do? Not these ever done anything. Right. But then the principal calls you and goes, are you the parent of so-and-so? And I'm like, maybe

[00:04:56] **Adam:** It depends.

[00:04:58] **Tim:** depends on what you have to tell me. And she's like, so congratulations, your student is the star student of 2020. To class, which means it's a, I don't know where they do this, but in Georgia, at least maybe it's a national thing, but they have this association where each school nominates one student and the criteria are, they have to have, it's the highest sat score in the school.

[00:05:22] **Tim:** So he beat all his other students in his class, for sat scores. And because he had a really good sat score and, and had also had the highest, grade on an exam, just one exam that beat everyone else out, which he did. And then it has to be in the top 10 students, which he is. And so what they do is they nominate them.

[00:05:40] **Tim:** Each school nominates one in all, kind of goes to a competition. They kind of compare their grades and their scores and their achievements. And if you go to the state level and come in first or second, you get scholarship money. And he gets a nominated his favorite teacher, his star, his teacher that inspired them the most.

[00:05:56] **Tim:** And he nominated. one of his teachers. We're here in Georgia. One of his teachers is actually, a great a niece or a great niece of Jimmy Carter.

[00:06:04] **Ben:** Yeah.

[00:06:05] **Tim:** and she was his elementary school teacher and she really helped her. He was going through some confidence issues and some things when he was in elementary school, she really liked just kind of helped them how to deal with stress and how to, not cause he would stress out when things wouldn't go well.

[00:06:18] **Tim:** So yeah, just super proud of him. he's worked so hard then comes along. So made me really happy. Maybe I have to admit, I cried a little bit when on the phone and they throw a dinner for them so that they have all the student, teachers and faculty, they have this, we go to this center and he's the only student being honored and they have like a trout in chicken and just his whole dinner.

[00:06:40] **Tim:** And he has to give a little speech and thank his teacher. And that, I mean, I was like, okay, they're going to have a dinner, his honor. No one's ever given me a dinner in my honor. That's awesome.

[00:06:50] **Ben:** Yeah, that's really

[00:06:51] **Adam:** I'm lucky to get that on my

[00:06:52] **Tim:** Correct.

[00:06:54] **Ben:** Congratulations, Tim. That's awesome. He must be.

[00:06:57] **Tim:** I am proud. Yeah. Very proud. Anyway, so that's me. Kara would normally be talking about something, but like I said, she's not here, but I know she's, she's at an event that, she's excited about. So in what you got,

## [00:07:08] Ben's Triumph

[00:07:08] **Ben:** I'm going to go with a triumph and over the last couple of weeks, I know I've mentioned several times that I've been working on modernizing my blogging platform and I focused primarily on the service side, updating the, ColdFusion stack from ColdFusion, tend to ColdFusion, 2021. And now I'm starting to focus more on the front end stuff.

[00:07:25] **Ben:** And historically I've programmed all of my JavaScript in , which is basically the version that was standardized, like in 20 15, 20 13. I don't know. It's been a really long time.

[00:07:39] **Tim:** certainly no one was alive back then.

[00:07:41] **Ben:** Yeah, like most developers today, we're not programming back then. and,it was compatible with , which actually today at work, I still have to support on the legacy platform.

[00:07:51] **Ben:** I still have to support 11. And, our legacy platform at work is so old that we don't even have a fancy build thing that transpiles code. So I'm actually writing code. And when it gets minified, I mean, minification is really all the build step that we have on the legacy platform. So anyway, my blog sort of follow that same thing, cause obviously I was focusing more on work, but I have made the decision to drop 11 support on my blog.

[00:08:16] **Ben:** I checked my Google analytics and its accounts for like a 10th of a percent or something of traffic. So it's, so it's super,it's super, super marginal. so I'm excited to go on that adventure because I'm very rusty when it comes to the very modern JavaScript stuff. Thankfully, I've been doing angular two plus, modern angular on my own sort of R and D stuff for the past couple of years, which uses TypeScript and TypeScript is a superset of JavaScript.

[00:08:47] **Ben:** So I have a lot of those flavors, but, it's interesting doing manually and then doing TypeScript. It's not always super clear what feature is actually part of the core JavaScript and which part is TypeScript. And then it's getting compiled down to something that's JavaScript. I don't know, I'm just excited to, to start learning some more modern stuff.

[00:09:07] **Ben:** And, there's some books I want to get from a doctor axle rush Mayer. I'm sure I mispronounce his last name. He has a couple of really good JavaScript books and,there's some really good compatibility tables on, can I use.com? I don't know if it I'm sure most people here use those are the Mozilla developer network MDN.

[00:09:23] **Ben:** They've got great compatibility tables. So I'm now like looking at features and then seeing how far back support goes for various browsers before I decide whether or not I want to commit it. It seems like the industry standard is the last two major releases of any browser is what people are committing to supporting these days.

[00:09:38] **Ben:** I don't know how widespread that standard is, but, that's kind of, that's cut on what we're going to do. So, async await arrow functions, string, literals,

[00:09:47] **Tim:** Whew.

[00:09:47] **Ben:** iterators and jazz promises that I don't have to poly fill. It's a brave new world. I'm pretty excited about. Pretty excited.

[00:09:57] **Tim:** He's got a big old grin

[00:09:58] **Ben:** yeah, I'm done just excited to have someone to talk about next Thanksgiving.

[00:10:07] **Adam:** Writing code in that old style by hand. Right? Not using a trans Pilar to go from modern code to less modern. Sounds awful.

[00:10:17] **Ben:** Yeah. It's I mean, you get, it's so interesting. So I was thinking a lot about this it's a little bit, like, I don't want to call it Stockholm syndrome where you're, you fall in love with your captors, but there is, I feel like there's this notion that people get addicted to their own pain and there's a safety in kind of a predictable discomfort.

[00:10:35] **Ben:** The devil, you know,Yeah. Yeah, exactly. Right. So, so I E 11 was this known quantity and it was like, yeah, it sucks that I have to support 11, but at least it's a known thing. I don't have to learn anything new really. Because I know what the set of features is supported by 11 and like, yeah, I can sprinkle in some new stuff.

[00:10:54] **Ben:** It can degrade gracefully and not really break under I 11 or, you I can just, it can just be like a slightly worse experience, but it can't break. So that, so in some ways it's like your brain is freed up to think just about feature development and not necessarily about the technology itself. So there was, there is something very freeing about that.

[00:11:12] **Ben:** It's just, it's a known quantity, but now that I, 11 is tossed aside like so much on needed clothing. it's a, it's like an unknown unknowns now I'm in a, just, even once I learn a syntax remembering to apply it in the places that it could be used in lieu of older of oldest techniques is going to be, just a lot of trial and error and building up my muscle memory and it's going to be good.

[00:11:36] **Ben:** It's going to be good

[00:11:37] **Tim:** I would say, I 11 was, released on October 17th, 2013. I hope you throw away your clothing more often than that. At least most of it, right.

[00:11:49] **Ben:** There's a certain degree of the material has to fall off before it hits the bin.

## [00:11:57] Audible

[00:11:57]

[00:11:58]

[00:12:27]

## [00:12:27] Cyclical Trends

[00:12:27] **Tim:** Yeah,

[00:12:34] **Tim:** You know, wehave to use that now. Right, Tim? Uh,I'm channeling my inner king George from Hamilton.

[00:12:46] **Adam:** So, Ben, this was,your topic. Do you want to give us a, like the synopsis here?

[00:12:51] **Ben:** Yeah, sure. So I w I listened to a lot of podcasts when I walked the dog and,

[00:12:56] **Tim:** That's not a euphemism. you're actually are walking the dog. Right.

[00:12:59] **Ben:** actually walking the dog and every now and then they'll say something that just tickles me. And, I was listening to a podcast the other day. And, they were talking about a new JavaScript server side rendering framework. I don't know if it or new version, I can't remember. Cause it's not an area of that ecosystem that I really know.

[00:13:17] **Ben:** And they were talking about how great it is, this new version coming out. It's going to allow you to include your database queries, like right inside of your view components. And I said, it struck me as funny because a lot of people in the ColdFusion. Joke about how a long time ago, people used to build these crazy ColdFusion applications where you would put your SQL queries, right at the top of your view file and not encapsulate it into some sort of a data fetching tier, some sort of data abstraction layer.

[00:13:44] **Ben:** And,this is not an isolated incident. I think we continue to see this over and over again where people rediscover something for the first time that is rediscovered every 10 years or so. I mean, even w various JavaScript frameworks come and go, we're focusing on server side rendering, then we're focusing on client side thick, spaz

[00:14:04] **Adam:** Say client versus thin client.

[00:14:06] **Ben:** Now we're going back to server side rendering or, different database technologies. I don't know. It's just, it's a fascinating thing to watch. And I think we've all been lucky enough to be in this industry for a long enough period of time where we get to see these cycles in play. And, I just find it fast.

[00:14:24] **Adam:** it is. I've thought about the cyclical nature of this stuff for a long time. Now, just never very deeply, but just like you notice it repeating over and over. I also had a similar thought about that, like, query or whatever server side code at the top of the view sort of thing. And I feel like I can kind of see both sides of it. Right? Like the, I think the argument against that posture, that, that programming style is probably. I hate to say it, Ben probably comes from a testing viewpoint, right? Like, if you have a bunch of logic and a bunch of queries that are like in response to form submission at the top of view file, right?

[00:15:11] **Adam:** So this is all going back to like, the early days of PHP and CFML and everything else like that, even Pearl and,early web languages, it was pretty common. You'd have, like, the top of your file will be like, if there's a forum posting here, then respond to that forum, post else, show the page that would submit that form.

[00:15:27] **Tim:** Right. It would always post back to itself. And, cause we didn't really know any better. That was just seemed like the obvious thing to do is what everybody else is doing. And going to keep doing that until it's fashionable. Again,

[00:15:38] **Adam:** there you

[00:15:39] **Ben:** Exactly.

[00:15:40] **Tim:** you like that.

[00:15:41] **Adam:** that's see, that's kind of where my head is at. Like. So from a testing perspective, I totally see and agree with the idea that there should be some separation there, right.

[00:15:50] **Adam:** By separating it out into separate files. What that gave us is the ability to isolate the display logic from the form post handler logic, and potentially, further, separate out the query logic and test that separately or whatever. And it's, I agree. I think it's a little amusing that visually we're kind of ending back up where we started a little bit with like these front end frameworks.

[00:16:15] **Adam:** Like for example, my new shiny toy that I've been eager to play with this felt and it's felt is another one of these where it has, basically each view file. Each component is. It's intended to look like an HTML page. It's a, it's got a script block and a style block, and then everything else is just expected to be HTML with this felt DSL sprinkled in for loops and that sort of thing.

[00:16:40] **Adam:** And you can have an extra sort of special script tag and the convention is to put it at the top of the file. but it's like script and then I think it's like type equals module or so there's some, attribute on that script tag. And it's indicates that this script block is what gets run server side and everything else is client side. And so that was, that was the first thing that I thought of when you had mentioned this,pattern coming back up and, I, again, I found it a little amusing, but at the same time, I think that it's, honestly I think it's a move in the right direction because the. You have the testability by being able to separate it out, right. It's felt compiles those things separately. but then you also have the co-location of related functionality, right? It's in the same file. You can look up at the top for the, for the, whatever the form handler or whatever's going on and down at the bottom for, I guess it's not so much foremost handler, whatever it's different, depending on what framework you're using, but regardless logic at the top and a view or display stuff at the bottom.

[00:17:46] **Adam:** And I feel like you get both benefits in the modern take on it, right in the original, when it was just one file with some, an if around it at the top to block certain behavior from running, then that was not as good as the current take. Right? So visually it's very similar, but functional. as if they're separated, if that makes sense.

[00:18:08] **Ben:** I think I sort of understand what you're saying and to be clear, I don't think that there's anything wrong with the trends changing over time. We're constantly experimenting as a, as an industry and trying to find the right way to solve particular problems. if anything, I think what it should teach us is that every approach is sort of right in its own way.

[00:18:28] **Ben:** Like it, it should be humbling that we poopoo something and then 10 years later it becomes all the rage. Again, like, we weren't, we should not have been as confident as we were to poopoo in the first place. and, nor should we be as confident in how great our current choices are.

[00:18:42] **Ben:** we're living in and we're learning

## [00:18:44] CSS in JS and Breaking Up Components

[00:18:44] **Adam:** So. Another thing that I wanted to talk about, there is this whole like CSS and JS thing, I feel like it's related. Right? So, when I don't know how to place it in time, but at some point we started telling everybody like, you have to use class names and IDs and put all your styles in a CSS file.

[00:19:07] **Adam:** And, for separation of concerns here, the, whatever, the markup of the document versus the display or the style of the document, they're two separate things, right? And that's kind of, for people that are against CSS and JS, they, the way that I see that manifesting is they kind of throw that back in the face of the people that are now advocating CSS and JS.

[00:19:29] **Adam:** And they're saying like, well, what happened to this whole separation of concerns thing? And for me, I still feel that it's separate. Like, it's, again, you're getting that co-location. But what it eventually compiles down to is separate. And that the argument for separating it in the first place was for performance reasons.

[00:19:47] **Adam:** mostly I'm sure there's more than one, but for me, the thing that I think of is performance

[00:19:52] **Ben:** the separation of concerns is an interesting one for me because, like I mentioned, at the top of the show, I've been doing angular, modern angular in my just R and D time for funsies for the last couple of years. And the, you can use either approach, meaning that you can have. What would you, what you could call is like a single file component where you have your CSS and your script and your HTML, like all right there, or you can break it out into multiple files that are still co located in the file system.

[00:20:20] **Ben:** Like my less CSS files right next to my HTML file, which is right next to my TypeScript file. and I just personally like splitting them up into different files, even if they're right next to each other. And I don't think it's, I think it's one of those things it's like, it's just preference. I know there are people who love having stuff in the same file.

[00:20:40] **Ben:** I think maybe it's also a stylistic preference in that if you write really small components, then have. your style and your markup and your code behinds, for lack of a better term in the same file. And it's like a hundred lines of code. Like that's super easy, but I tend to err on the side of actually rather large components because, I usually, if I'm not going to reuse something, I just try to cram it into one giant component where like here's my page component and It has my form at the top and it has my data grid at the bottom. And I'm never going to reuse that data grid anywhere else. So it's just going to be big. It's going to be like a 600 line market file and I'd rather have that in its own file. And then my TypeScript in a different file, just because it's easier to scan those things and to understand where they are.

[00:21:26] **Ben:** But,I try to combine all of them into something really big, I think would be harder. But again, like, I think it's just a personal preference.

[00:21:35] **Adam:** So I agree with you. I think that the thing that caught my attention was when you said, like, it works better as if you're writing like small components. And for me, I take that as pressure on the outside, pushing in to keep my components.

[00:21:51] **Ben:** It's interesting. I,

[00:21:53] **Adam:** Yeah, there's no right or

[00:21:54] **Ben:** Yeah, yeah, yeah.

[00:21:55] **Adam:** That's like the whole theme of this episode is like, things are cyclical. That trends change.

[00:22:00] **Ben:** It's true. And I'll tell you now, not to go off on a tangent for a second, but going back to clean

[00:22:06] **Ben:** code,

[00:22:07] **Tim:** you will.

[00:22:08] **Adam:** That should be the whole title of this

[00:22:13] **Ben:** the idea that. That an area of your coach do one thing and one thing. Well, to me, that feels like you can interpret that almost any way you possibly want to. and you people twist it to mean whatever it is that supports their style of coding. Right? So I find that people in the react world, and this is just a naive,viewpoint from outside.

[00:22:33] **Ben:** I feel like people in the react world, like over index on creating super small infinitely reusable components. And when I try to edit that reaction and I like, oh, why are you guys breaking this stuff up into such small things? Now I've got to pass these prompts all over the place. Like this could have just been one much larger component.

[00:22:51] **Ben:** So the reactable can look at that. And I'm overgeneralizing here, apologies. The reactive would say, well, yeah, but this is like this XYZ component and it should be nothing but an XYZ component and that's all it should do and it's do it really well. And then on, on my end of the spectrum, I look at and be like, here's my contact form page.

[00:23:08] **Ben:** Like my contact form. Does one thing and does one thing really well and that's accept contact forms. And like, it's going to be one giant component and it's going to have all the market native for it. and I think it's totally reasonable to argue in either direction because I'm never going to take my contact form and use it somewhere else in a way that doesn't mean exactly what it's supposed to mean.

[00:23:28] **Tim:** And I think that's an important thing. The use, right? So w when you were saying that alarms went off in my head, I work on mostly multi-tenant systems. And so what I run into, if you have a function that's doing five or six things, what you find is eventually you're going to run into a case where another tenant is going to need some, one little thing inside that function to do something different, right.

[00:23:52] **Tim:** I needed to produce this result rather than this result. And now I have to refactor that whole thing. So I might as well have just broken it up into discrete individual things that only did one thing. So that. Tenant a needs to do something for different from tenant. B only thing I'm doing is I'm using polymorphism to extend that and overwrite that.

[00:24:13] **Tim:** So that it's doing that now I have, and I've done that today. That's that was one thing I was working on today. I wrote a much too big at my function was way too big. I'm like, oh yeah, this is all kind of doing one thing. It was. But my idea of what kind of one thing was really wasn't correct. And so I had to take one function that wasn't huge.

[00:24:32] **Tim:** It's probably like, 40 lines, but I had to break it up into three different functions and then go back to the, my base class that I have, that all of them use if they don't have, if they're not using polymorphism on it. So like I said, if you're, if you know that in your contact form world, that it will never be anything other than that, Th it's doing one thing, but in my world, it's like that contact form could be used by 50 different clients.

[00:25:01] **Tim:** And so each in discreet part has to be different because each discreet part could possibly need to do a different funk, come up with a different result internally than what the others do.

[00:25:12] **Ben:** Yeah. Yeah. and I think it's interesting. So one phrase that has always rubbed me the wrong way in our industry is that programmers are lazy. I'm like, oh, it's such a stupid phrase. Like programmers, aren't lazy, they're good at their jobs. And they're trying to build awesome stuff. And I don't know, people just throw that around.

[00:25:29] **Ben:** It makes me so angry.

[00:25:30] **Adam:** Well, I think they're like two sides of the same coin, right? There's also people that say like the best programmers are lazy programmers, because they're going to find the most efficient, least amount of work way to get something done.

[00:25:42] **Ben:** right. But I think, but going back to Tim's comment too, is that I feel like to some degree, if you can think of lazy as wanting to defer making decisions, like why make a decision today that I can make to. then I feel like you can build simpler code today and then make it more complex only when it needs to be more complex.

[00:26:03] **Ben:** So you don't build your contact form on day one, thinking that it will be reused in a lot of different ways, you build it to solve the problem. And then later on when it proves to be, not quite so simple and needs to be reused, then you can start to refactor like Tim did.

[00:26:19] **Adam:** Yeah.

[00:26:20] **Tim:** I mean when I feel lazy and proud of it is when someone says, well, I need them. there's a control flow in the program. They're like, we need to change this way. We don't, this is probably going to be difficult and like, Nope, that I know that's exactly one function inside this thing.

[00:26:33] **Tim:** I go change that, extend it, extend the base. Overwrite, what it's doing is done. That's when I feel lazy and proud of it, because it's like, I foresaw that, that, doing what makes, what I did today made me feel lazy and stupid because it's like that PR that function was way too big. It was just way too big.

[00:26:53] **Tim:** It was doing way too many things. and so I really should have broke it up at the time, but, I was trying, I was under a deadline. I was trying to get something done. I would just like, just get it done. That's when I feel lazy, it's like, when I feel like I did this under the constraints of just get it to work.

[00:27:08] **Ben:** Yeah.

[00:27:09] **Adam:** So I wanted to go back in and talk about your, contact form example a little bit, and it made me think of,I'm sure I'm going to butcher it. I apologize in advance, but I know I've seen somebody discussing, it was like a conference presentation or something. The idea of like atoms molecules.

[00:27:25] **Ben:** Yeah.

[00:27:28] **Adam:** I forget the entire heart hierarchy, but I feel like there's organisms and, whatever it goes up from there.

[00:27:33] **Adam:** And I feel like I can see an argument for. Picking a little from column a and a little from column B in terms of like, just do it all as one big component or break everything apart. And I think the way that I would maybe try to get the best of both worlds on day one and refactor later as appropriate is like the things that I have come to realize over the course of my career that are important to be reusable, atoms are like, form fields, right?

[00:28:03] **Adam:** So especially in the day of like bootstrap or whatever your CSS framework is that you're using, you need to have a consistent style for your inputs and all the different form elements that you're using. But then a day is going to come when you need to upgrade to the next version of the framework, or you're going to decide to change the way things look.

[00:28:22] **Adam:** And if you can just update a handful of components and that automatically updates your entire application, that'll, that's a worthy of like a raise, right? Like that saves you so many hours and your boss will love you for it. But at the same time, I totally see what you're saying about like going too deep down that make everything a component rabbit hole.

[00:28:43] **Adam:** And I agree, like certain things need to be Adam's on day one, but if you don't, if there's not a clear and obvious, like this needs to be its own thing, because I know I'm going to be reusing it over and over then. Yeah. I would tend to group things and make a larger. I think that's, again, this goes back to kind of the discussion we had recently about how clean code isn't like, a destination, it's a process and you're continuously making it better and refactoring and improving

## [00:29:17] Dependency Injection

[00:29:17] **Ben:** Oh, just as we're talking about this one thing that strikes me again about cyclical nature. Is the idea of dependency injection. So if you go back, a handful of years, all the established service side languages are using some form of. dependency injection in version of control, in, in ColdFusion, obviously we have DIY and cold box and ColdBox techniques with WireBox and all the Java people, right.

[00:29:42] **Ben:** They use spring or something. Right. So I don't think you could ever mention to a server side developer, Hey, we're going to build an application and we're not going to use some sort of inversion of control. Right. And then node comes around and everyone's just like, oh, I'll just require my arbitrary modules from wherever I need them.

[00:30:00] **Ben:** And then going back to Bob Martin's clean code and the idea of the new operator and constructing objects is like a code smell. Like nothing. She never knew anything else. They should all be nude somewhere else and then inject it as arguments. and now you come back to the. of react and they've really finally, I think, modernize their whole context, right?

[00:30:19] **Ben:** Is it, or no? what's the thing that it's like instead of doing prop drilling where you're passing props everywhere, now you can just define a context and that content can magically make things appear like any layer in your componentry, which is, spoiler alert, the inversion of control dependency injection more or less.

[00:30:34] **Ben:** So it's like all of this stuff, just everything we're constantly learning the same lessons over and over again. I remember an angular has had dependency injection since day one. That's like one of the core principles of the entire framework. And I remember talking to people in react and be like, how are you guys just importing things like that's crazy.

[00:30:53] **Ben:** And people were like, well, dependency checks the stupid, why would you ever need that? Now? It's like, now they're totally in that same camp as well. So it's, it's nice to know that we're all getting.

[00:31:04] **Adam:** I think that you, I mean, I'm not saying that you're wrong, but I think that. It happens for a reason. And the best thing that I can think of as a reason why that might happen is, people come up with an idea to improve on one problem. Like, react is,what's that way that I like to explain react it's oh, it's deterministic.

[00:31:22] **Adam:** Right. You give it data and it spits out your UI. Right. and so they kind of started from that, like how do we build a framework around that? And then they went, oh yeah. What about dependency injection? Now we have this prop drilling problem. so I don't think that necessarily, it was a conscious decision to poopoo dependency injection and build a framework without it.

[00:31:40] **Adam:** It's just like, oh yeah, we kind of, they kind of forgot about it and had to relearn that lesson.

[00:31:45] **Ben:** Yeah, absolutely. Absolutely.

## [00:31:47] Monoliths And Microservices

[00:31:47] **Tim:** another paradigm is the whole,everything should be a service microservice. And now people are like, I know been smiling about that one. And they're like, people like, you know what? The monolith really wasn't that bad. As long as it wasn't too big of a monolith. And so

[00:32:01] **Ben:** Yeah. So

[00:32:02] **Tim:** another lesson that just coming full circle.

[00:32:05] **Ben:** I'm a huge monolith, person. I would, every, every application that I start going forward will always start as a monolith and we'll have services as needed. Cause it just, I mean, I don't know. It's so much easier to me and it, and here's the thing, right. Sometimes you don't even understand the pain until an application gets older and the people who built it, aren't there. And the platform team that has to support it is changing. And the architecture is changing and evolving.

[00:32:33] **Ben:** And you run into these things where someone says to you one day, oh, by the way, we have to rotate some AWS keys or something, right. Like something has to be rotated and you think to yourself, oh, that won't be a problem. I'm working in a monolith. And it's just like one environment variable and like easy peasy, lemon, squeezy.

[00:32:50] **Ben:** but then you turn around and you start to look at the code and you're like, oh, actually the same key is used in like 15 different services. And I can't just rotate it in one because then like, like assigning Cain, one place won't match a decrypting key in another place. Now I have to build a whole key rotation system to make sure that I can deploy these services independently, just so they don't break.

[00:33:09] **Ben:** And you're like, this is ridiculous. Like, and none of the people who built this are here anymore. And now, I don't know. Sorry, I'm just getting angry and rant.

[00:33:18] **Adam:** Old

[00:33:18] **Adam:** man yells at cloud.

[00:33:20] **Ben:** it's people like to say when you build a service small and it does just one thing, like it just maintains itself.

[00:33:25] **Ben:** And like, that's the whole point. It's just easy because it does less until suddenly Amazon landed doesn't support node 12 anymore. And then you have to upgrade your land at a node 16 and like 18 of your dependencies break. And you realize that one of them doesn't even exist anymore.

[00:33:41] **Tim:** yeah, it's like saying, a bike chain is great and it is you could bike chains. Great. Because they're all know interlocking links, but if one of them breaks, you can't ride your bike. Right.

[00:33:52] **Adam:** that's a good metaphor.

[00:33:53] **Tim:** And I mean, this is sort of same thing with all these services. It's like, it's great. Yeah. It's awesome that they're all independent and you can go do cost code changes on maybe one that's, get more than the other one.

[00:34:03] **Tim:** it doesn't need any code changes cause it's doing fine and that's awesome. And you don't ever break that other one, but when one of those links break, the whole mechanism stops running.

[00:34:13] **Ben:** Yeah. Yeah. It's like, I think I heard someone just talk about microservices. Like if one of your services goes down and it takes down your entire ecosystem, like it's not a microservice, it's a distributed monolith.

[00:34:24] **Tim:** Exactly.

[00:34:25] **Ben:** Or like when people

[00:34:26] **Ben:** talk about

[00:34:26] **Tim:** the quote I remember from Ben. That's the

[00:34:28] **Ben:** Or people talk about caching. They're like, like, if you flush your cash and your system gets crushed by the incoming traffic, like it's not just a cash, it's a critical part of your infrastructure.

[00:34:38] **Ben:** You can't just be like, oh, it's just a cash.

## [00:34:40] What Drives Cyclical Trends?

[00:34:40] **Tim:** I think what's more interesting is kind of talk about what drives this whole fact that we see this cyclical nature. I don't even know sickle. It's just, it's sort of like people are rediscovering or trying the same things that have done before, but thinking it's new. What, I mean, what do you think in the industry drives that?

[00:34:59] **Ben:** I'm sure. Part of what goes into it. As we've discussed recently, how, I forget the exact numbers, but it's like every five years, the number of developers double, so 50% of people, don't have that history, don't know those lessons, unless they were lucky enough to have come from a program, whether that's a bootcamp or school or wherever that they learned, use dependency, injection, or whatever the thing is, Yeah. It's tough.

[00:35:21] **Adam:** that's definitely only part of it though. There's gotta be more to it than that.

[00:35:24] **Tim:** I was thinking just having programming has only really been around as a real occupation, not just a experiment since the sixties. Right. I mean, the sixties is when, IBM and all those companies, people started really doing things with computers and then programming became a thing. And then the hobbyist got involved in the seventies and eighties, in the eighties is when I started learning programming as a kid.

[00:35:49] **Tim:** That is an extremely infant tile industry. I mean, it, we're just starting

[00:35:55] **Adam:** We were so lucky to be there. Yeah.

[00:35:57] **Tim:** right. w I don't want to say we're like, I'm just saying these are all just the growing pains of, you have an industry that has been around, they've been established for hundreds of years, there's become patented.

[00:36:07] **Tim:** There's just become a way of doing things. We are still figuring

[00:36:10] **Adam:** Um,

[00:36:11] **Tim:** how to program

[00:36:12] **Adam:** we don't have the benefit of a hundred years of history to draw on. We

[00:36:15] **Adam:** have 40,

[00:36:17] **Tim:** the technology that we're, the tools that we're using are constantly changing every couple of years. So, not only do you not have a depth of knowledge, but you have a constantly changing toolset. So imagine if like, I know Adam, you like doing like woodworking, what if you got like really good using, you had a lay, then you had this and that and whatever.

[00:36:37] **Tim:** You're like, okay, cool. I can really make some cool stuff. And then like five years from now, they're like, okay, take away all these

[00:36:43] **Adam:** Yeah.

[00:36:44] **Tim:** We're going to give you all these other tools that you absolutely don't know how to use and now build

[00:36:49] **Adam:** yeah. And all the directions are written in Japanese and

[00:36:51] **Tim:** Exactly. Right. Yeah. And I just think this is just the nature.

[00:36:56] **Tim:** It's kind of what I find exciting about programming is because it's like, it's always, it's new frontier every single year.

[00:37:04] **Adam:** it definitely fits my personality. Cause I feel like I'm, I like to say that I'm a lifelong learner. Like I

[00:37:09] **Adam:** just, part of what I enjoy about something, I don't know how to do yet is learning how to do it. The processes.

[00:37:16] **Ben:** also, even within our industry, there are so many different styles of application that have different stresses on them that require different techniques. So I think part of it too, is just adapting things that we see other people doing, and then trying to understand how they apply to the type of work that we do, whether they apply, because things don't always apply and then making it your own and then evolving it as the needs within your own area of expertise change.

[00:37:45] **Ben:** And it's all so dynamic.

[00:37:48] **Tim:** I mean, think about, so when we got started guys, I mean, we're, I mean, I'm older than you guys, but like we're all kind of in the same generation. I think of programming when we started out is like, you had a server that was hosted somewhere a machine. Right. And so then. Yeah, you could touch that this is where my code resides, or you could touch the machine.

[00:38:10] **Tim:** And so that kind of directs how you build applications, right? And now today you have like Amazon services and you're like, have, you can spin up like 15, 30, a hundred, however many different, virtual computers in the cloud. That totally changes the paradigm of how you build things, because just that way of.

[00:38:30] **Tim:** Computing, it's all just a voice of computing that way it computing is going to change. That's how microservices came about, because it's like, well, I just can spin up this service and this service in the cloud. And it doesn't really cost me that much. And it's fast and people rationalize why that's better and who knows what's going to be the next thing in 10 years.

[00:38:48] **Tim:** Right. I mean, so that's what I kind of think drives this sort of thing as technology changes as the cost of things changes. Because I mean, there's no way back when we got started that we would spin up, Hey, let's do this one web application. Let's spin up 15 different machines like techno.

[00:39:05] **Tim:** Yeah. How much money that costs no way, but you can do that now. Easy-peasy like, just do some microservices on, some micro instances, up on Amazon or Azure or wherever you're doing it. Like, it doesn't even cost you anything, if you don't go over a certain limit.

[00:39:19] **Tim:** And that definitely will inform how you approach.

[00:39:22] **Adam:** and even better you can provision a resource, use it, get what you need from it and deeper vision.

[00:39:29] **Adam:** Yeah,

[00:39:29] **Tim:** Yeah, exactly.

[00:39:31] **Ben:** it's really interesting too, because even that mentality doesn't necessarily scale for everyone. I was watching a presentation. I want to say it was from draft Kings, the online betting site, and they have problems because their spikes and traffic are so focused around, like a 90 minute sports.

[00:39:51] **Ben:** That they can't, they don't have time to ramp up. It goes from like nothing to way too much traffic. And so they actually have to plan ahead of time for big sports games ramp up way early, and then essentially eat the cost of having too much infrastructure, absorb the traffic and then spin down. So it's even in this highly dynamic world, there, there are still scenarios and types of companies where it's still just really tricky to support the kind of traffic that you need to support.

[00:40:21] **Tim:** Yeah. And I think that's one thing I don't personally think about a lot. I don't, because I don't have to, but it's like, I worry about like the customer situation and how I'm coding, but when you're dealing at that level, it's actually, what can the technical, what can the hardware support at the end of the day, cloud, whatever, it's all hardware, it's all it is, right.

[00:40:43] **Tim:** You can call it whatever you want. It's all hardware. where are the compute cycles coming from and how those things happen is definitely going to drive how you build things. And I think that sort of people keep learning those lessons over and over again.

## [00:40:57] Knowing It All vs Specialization

[00:40:57] **Ben:** You know what drives me crazy. And this is my imposter syndrome kicking in hardcore when we have conversations like this is back when we started, which was a while back,companies and applications were just smaller development teams were smaller there weren't you, there weren't any, there wasn't a dev ops team right there wasn't really a platform team in most places.

[00:41:17] **Ben:** And so you sort of had to know a little bit about how servers work and a little bit about how databases scaling and, and now that's still to some degree the sort of foundational perspective that I have when looking at all of the new landscape of architecture. So when we talk about. Companies where they have platform people and they have predictive models in terms of traffic and they budget things out and figure out cost efficiencies.

[00:41:43] **Ben:** Like to some degree, I always feel like I have to know how to do all of that. and I still feel very uncomfortable. This idea that, oh, well, there's just going to be platform people who are doing a whole bunch of stuff that I don't have any idea how it works. There's going to be a bunch of machine learning.

[00:41:57] **Ben:** People that know how to train models that tell the platform team when to scale up based on traffic patterns or whatnot. Like it's very, a part of me is always very uncomfortable talking about that because I feel very much like, I don't know any of it.

[00:42:10] **Tim:** And I get that because back in the day it was like, we were the ones we had to handle all that. Right. It was like, that was our concern. And now it's grown beyond the complexity of scale that we, that one person can have that. And now you have teams dealing with that. And I get that, you're like, well, I would really like to know how they're doing that and be part of that.

[00:42:30] **Tim:** But it's like, I don't have time for that because that's a full-time job now. That's why you're taking on like four or five different full-time jobs that you use to kind of take care of because technology was simpler than.

[00:42:45] **Adam:** And I think that business in general, like as a rule of thumb has really started to awaken over the last five, 10 years to the value that they can extract from. The internet and from computers and from developers and as a result, the number of people, the number of jobs has like skyrocketed, which means that there's a lot more opportunities to specialize.

[00:43:12] **Ben:** Yeah. Yeah, yeah, yeah. I want to know it all

[00:43:17] **Adam:** Yeah.

[00:43:18] **Ben:** I will say, going back to the cyclical nature of things, there's nothing wrong with things being cyclical. Like it's funny to observe, but I don't think there's anything wrong with it. I just wanna put that out there. it's when the pendulum swings the other way, it can be a correction, but it doesn't necessarily mean that the other direction was wrong.

[00:43:34] **Ben:** It just means that we were reacting to some, we were reacting to a problem and maybe we're solving it with measure. We were solving it with overreaction, but there's nothing wrong with things being cyclical. We're all learning and evolving. And sometimes you got to lean into it. Don't throw a, I was going to say don't throw good money after bad, but I guess that's the wrong metaphor.

[00:43:57] **Tim:** Don't throw the baby out with the bath water. your heart matters been,

## [00:44:01] Personal Preferences

[00:44:01] **Ben:** another thing just to mention, I guess, is our own personal techniques in terms of programming are very cyclical list. I find with myself, right? Or we've talked about this before that the novice programmer comes in and they want to just use simple data structures because that's all they know.

[00:44:19] **Ben:** And then they start to learn about design patterns and dependency, injection, and object oriented programming, and suddenly their applications become a lot more complicated and usually tightly coupled because they don't know what they're doing. and then over time you get more experienced and then you start to simplify and break things apart.

[00:44:35] **Ben:** And then you realize that, those data structures that are were using 15 years ago, those were actually pretty powerful and very easy to use. I'm going to start to use data structures a lot more. So even the way we solve problems individually tends to be cyclical in my experience.

[00:44:49] **Tim:** yeah, no, I definitely agree with that. I'm like, when Oren first came out, I'm like ORM, all of the.

[00:44:53] **Ben:** Yeah. Yeah. Yeah.

[00:44:54] **Tim:** Yeah. So you get a new tool where like, oh, this is so cool. So probably in like you go to a conference and everyone's like, extolling the value of nature of it. And you're like, oh cool. You start using it, but use it too much.

[00:45:05] **Tim:** And then you're like, now the thing that I thought was helping me is causing me problems. And so I don't abandon it, but I dial it back a little bit, I don't need that. I don't need arm for everything. and so I think, yeah, I agree with you that if we kind of go to these things where we get really excited about something and we think it's the panacea for our problems.

[00:45:26] **Tim:** It's not. And we figured that out and we dial it back and we learn we're wiser.

[00:45:32] **Ben:** I think the bouncy act that I often have trouble with. Where can I be, slow to change so that I'm not just jumping on every bandwagon that comes along. but when, and then how do I not become old and curmudgeonly and never changing because I never want to adapt something new. I feel like we talked about the, like early adopters and the, I forget what the names of all the segments are.

[00:45:57] **Ben:** If like how fast you adapt new technologies.

[00:45:59] **Adam:** The Rogers curve of adoption.

[00:46:01] **Ben:** I'm very heavy on the laggard side. I change very slowly, and I remain very happy with my slow choices. So it's,I feel like I sometimes get left behind. and then to some degree I have to double down on my curmudgeonly newness, to explain a way my choices, but, I know if that's a, it's a balancing act.

[00:46:21] **Adam:** Is that a coded message? Ben

## [00:46:22] Source Code vs Tests Thought Experiment

[00:46:22] **Ben:** Can I go off on like a total tangent for a second.

[00:46:28] **Adam:** I a tangent to the tangent. To the tangent? Yeah. Sure. Why not?

[00:46:32] **Ben:** So I was listening to, I want to say it was the bike shed podcast and, they were discussing a tweet from Dan Abrams who, who famously created Redux and is now a core member of the react team. Apparently had a tweet about if some nefarious actor stole all of your source code, but you could get either the tests back or the source code without the tests back.

[00:46:55] **Ben:** Which one would you want?

[00:46:57] **Tim:** Well, I know the answer for you because you don't write any

[00:47:00] **Ben:** Do I want all the source code or none of the source code,

[00:47:04] **Tim:** tests you ever wrote.

[00:47:08] **Ben:** but it was actually on the bike shed. it was a very, it was a fascinating talk because. It's sort of, they sort of both started out. I felt saying, well, of course I don't want my test back so that I could prove out the functionality. But then as they got into the discussion, they started to talk about how I have, but there's so much that it doesn't actually get tested in application.

[00:47:28] **Ben:** Then there's all the visual UI stuff. Then you can't really test. And there's all like the weird little edge cases and tweaks that people bake in that they forgot was even part of the software over time. and starting out saying, oh, well of course we want the test. They sort of ended up with yeah.

[00:47:43] **Ben:** But we probably just want the source code and we could always rewrite the tests. so I don't know. I want to throw that on. Cause I know you guys are very testy heavy.

[00:47:51] **Adam:** mean, I follow Dan. I saw that tweet and I saw, I did read a little bit through the replies. I mean, he's one of those people that gets, probably a thousand replies to everything he tweets. But, one of the things that I thought was interesting in that discussion was somebody, it might've been Dan might've been, somebody else made a distinction. If you're talking about an application, your answer might be different or maybe should be different than if you're talking about a library. So like from Dan's perspective, they're talking about like react. And I think one of the points that he made was that they completely rewrote react. I don't know what version number, but let's just say, like from version 15 to 16 or 16 to 17, they like started from scratch and they wanted to build something that was backwards compatible, but that had incorporated a bunch of lessons.

[00:48:37] **Adam:** They had learned along the way. And so they kept their tests, but they started from scratch on the source code of the library. And that way they knew they didn't break anything. And, they were able to write the code again, using whatever, organizational or coding, technique, style, whatever lessons.

[00:48:55] **Adam:** and I thought that made a whole lot of sense. And I think that, The other side of that same coin, right? I guess what that implies is that if you're what you have as an application where you've encoded a whole bunch of domain logic, when this happens, in my business, I need this other thing to happen.

[00:49:14] **Adam:** As a result, it's probably more valuable to have the code itself.

[00:49:18] **Tim:** At least the code runs.

[00:49:20] **Adam:** the other thing that I was thinking about as you were describing that whole situation then was, do I get the choice between my source code and the tests that I wrote or do I get the choice between an ideal situation of what my app should be? And, and the tests that I should have been writing, right?

[00:49:39] **Adam:** So like for example,your app, if you did, let's just say you were perfect at TDD and you had written tests for every little thing. You had a hundred percent code coverage. And even though I want to point out code coverage is about lines of code. And that's not necessarily the same thing as, testing all the features, but there's a lot of overlap there anyway.

[00:50:00] **Adam:** I feel like that changes it, right? So if it's about the test, certainly if I know that my tests are imperfect in a significant way, then I'm going to choose my app code. But if I knew my tests were perfect or that the test that I got back would be perfect. I might choose the tests over the app code.

[00:50:22] **Ben:** Interesting. I'll tell you, I obviously would want the source code because I don't have tests, but I felt like that aside, my reasoning, I feel like you would be proud of because my thinking was in reality, a very large portion of your application is probably never going to be touched again. It's been built, it mostly works and that's not miss or the area that makes us money, et cetera, et cetera.

[00:50:49] **Ben:** It's going to be very slow moving.

[00:50:50] **Tim:** I'm thinking from the money per second to yeah.

[00:50:52] **Ben:** So you could treat it then like a legacy application that you had to start writing tests for. So you have your source code, less any tests. Now you have to change a feature. And the first thing you do is try to build some simple tests around the behaviors that you're going to change so that when you change them, you can run those tests to see if they work and you can incrementally build tests back up.

[00:51:15] **Ben:** and then, you might have a large swath of your application. That's has no tests, but it's also never getting worked on ever. So it's sort of like a best of both worlds in a way that's not the right phrase, but,I think, you know, what.

[00:51:27] **Adam:** Yeah. Yeah. I mean, I see what you're saying. I'm not sure I a hundred percent agree because, so for a couple of reasons, the first one, the most obvious one to me is that I feel like on average, my lines of code that I write to test something is probably two to three times more code than the actual application code that I'm testing.

[00:51:49] **Adam:** Just because you have to do the data setup and tear down and all of that usually. But, so just in terms of the amount of work it's going to take to get back to a fully tested app, if you were going to pursue that is going to be greater. If you take the app code than if you were to take the test, right?

[00:52:04] **Adam:** If you take the test, then the larger jerk of chunk of the work is already done. The other thing, that situation that you described where you've got an app and that it's in reasonably good working order and you need to refactor it. And so you write those tests so that you can make those changes. And it's funny because like, do you write tests that I guess you would have to do both, right. You'd have to write tests that show that the current code is working as designed, and then you'd write additional tests to show the changes that you want to happen.

[00:52:36] **Adam:** And I guess it depends heavily on what kind of change you're making, right? If you're intentionally breaking old functionality, that's different than adding on. you, one of the dangers of not having tests is that you're going to make a change and the change you make works, but you unknowingly break something else.

[00:52:52] **Adam:** And so if you don't have that, those tasks and that other stuff, then you don't know that you've broken it until somebody screams.

[00:52:59] **Ben:** Right, right. That's true.

[00:53:01] **Adam:** So there's yeah. I mean, I think this is a, it's like a Sophie's choice of software, right? there's no right answer.

[00:53:07] **Tim:** Which child do you want to die?

[00:53:09] **Adam:**

## [00:53:09] Patreon

[00:53:09] **Adam:** So this episode of Working Code was brought to you by thick clients. That's thick with three C's and a peach emoji and listeners like you. If you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod.

[00:53:24] **Adam:** all patrons get early access to an ad free version of new episodes and our after show. And we really appreciate all of their support, but of course our biggest things go out to our top patrons, Monte and Peter

## [00:53:35] Thanks For Listening!

[00:53:35] **Adam:** did you know that we tweet clips of the show every time we release a new episode. And did you know that it would warm our IC jaded developer hearts if you gave those a retweet because we do, and it would, you can find us on Twitter @WorkingCodePod. Do you have a topic you want to hear us discuss on the show?

[00:53:51] **Adam:** You can send it to us on Twitter or Instagram @WorkingCodePod, or you can record a voice memo on your phone or your computer and email it to us@workingcodepodatgmail.com. You can also join our Discord to hang out and chat with other listeners. It's a great little community, and we'd love to have you.

[00:54:05] **Adam:** You can joinat workingcode.dev/discord. that's it for this week. We'll catch you next week. And until then,

[00:54:10] **Tim:** and remember guys and gals your heart matters. Even if you're an old grizzled veteran from the code wars from 1988.
