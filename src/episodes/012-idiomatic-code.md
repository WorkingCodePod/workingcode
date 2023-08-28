---
title: "012: Idiomatic Code"
description: This week, the crew talks about idiomatic code, what they think it really means, and how it can serve to both help and hurt a programming community.
date: 2021-03-03
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/012-idiomatic-code/id1544142288?i=1000511417937"></iframe>

Many programming languages have a sense of **idiomatic code**: the "blessed way" to solve a particular set of problems with a language's native constructs. These patterns exist to help people work more effectively together; and, to help new developers adapt to the language. But, unfortunately, the expression of idiomatic code in some communities shifts [from "carrot" to "stick"][carrot-and-stick], getting used to separate the "right" way from the "wrong" way, thereby creating an implicit division between the "good developers" and the "bad developers".

The ColdFusion / CFML community has never had a sense of "idiomatic code". And, ColdFusion developers are never burdened by the homogeneity of solutions that bubble up to the surface (such as they do in other languages). This can lead to a kind of **"beautiful chaos"** in which teams find the right tool for the job and spend their time focusing on the needs of the customer rather than worrying about any particular standard.

Is that a good thing or a bad thing?

This week, the crew talks about idiomatic code, what they think it really means, and how it can serve to both help _and hurt_ a programming community.

### Triumphs &amp; Failures

-  **Adam's Triumph** - He's not on call this week! And that feels like a sweet, sweet triumph!

-  **Ben's Triumph** - The moment he realized that he was going to miss a deployment deadline, he took a step back and figured out how to properly "descope" the work such that he could meet his deployment deadline by releasing a smaller - _yet still meaningful_ - set of features. He saw this as a victory in the agile development mindset.

-  **Carol's Triumph** - She's going on vacation to Lake Tahoe for some fun in the snow - something she rarely has a chance to do in hot, hot Georgia.

-  **Tim's Triumph** - For his entire life, Tim has been parting his hair left-to-right. But, in a recent moment of brashness, he threw caution to the wind and tried parting his hair right-to-left. This seemingly small tweak ended up being a _total game changer_! And, just as [Clark Kent transformed into Superman with a change in part][superman-hair], so has Tim transformed into a more stunning, beautiful version of himself!

-  He also figured out why his Redis code wasn't working. [Ironically][working-code-009], it had to do with how his tests were running (and how they were mutating the shared data).

### Notes &amp; Links

-  [Guido van Rossum](https://gvanrossum.github.io/) - author of the Python programming language; and, a big proponent of idiomatic code (in Python).
-  [Rick Waldron: Principles of Writing Consistent, Idiomatic JavaScript](https://github.com/rwaldron/idiomatic.js/) - an opinionated guide to writing JavaScript.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[carrot-and-stick]: https://en.wikipedia.org/wiki/Carrot_and_stick
[superman-hair]: https://www.reddit.com/r/MovieDetails/comments/6khyt8/in_superman_when_christopher_reeve_portrays_clark/
[working-code]: https://workingcode.dev/
[working-code-009]: https://workingcode.dev/episodes/009-testing/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/012-idiomatic-code.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:17] **Adam:** Okay, here we go. It's show number 12 for March the 3rd. Can you guys believe we've been doing this for, what, this is episode 12, so that's three months now? We've been doing this every week? And today on the show we're going to be talking about idiomatic code. We're going to find out what that is, and then we're going to talk about it.

[00:00:33] **Adam:** So, I guess, let's jump right into our triumphs and fails. Tim, what do you got?

[00:00:38] **Tim:** Alright, so listen, not all triumphs and fails have to be something technical or code related or job related. Yesterday, I solved a problem that I've had my entire life. I've been doing something wrong all the years of my days.

[00:00:58] **Tim:** So curious. So... Alright, this is a podcast, so unless you guys have met me in person, you don't know really what I look like, but I have dark hair, dark graying hair, and I've always combed it from the left to the right, all my life. And every time I get a haircut, the left side of my hair sticks straight out.

[00:01:21] **Tim:** Always. And I would like slap it down with tons of gel. And it always, I have, I guess I have a cowlick or something there. I just always, every hairdresser, everyone has always just combed my hair that way. So that's. Just the way I've always done it. And so I'm getting a haircut yesterday. My wife is can finally cut hair again.

[00:01:38] **Tim:** Cause she's had surgery and she's better now and she's cutting my hair. And I'm like, you know, what would happen if I comb my hair from the right to the left? She's like, I don't know. I'm like, you know what? It's just hair. Let's try it. Like, you know how it always sticks out? I'm thinking, so my theory is if I just comb my hair the other way, the swoop, you know, will lay over that side that sticks out and give it some weight and lay it down.

[00:02:06] **Tim:** And look, you can't see it, but it's, it's not, it's the best haircut of my life. I've been doing it wrong

[00:02:13] **Adam:** all these years. And it only took 75 years.

[00:02:18] **Tim:** But interesting. I was like researching hair parts. And yeah, cause you know, I'm the kind of person who researches things like that. Did you know that Christopher Reeve in the movie Superman, whenever he was Clark Kent, he parted his hair from left to the right.

[00:02:37] **Tim:** Like I used to, like a nerd. And when he was Superman, he parted it right to left. Like I am now, Superman. So this is a total life win. This is a game changer,

[00:02:50] **Carol:** guys. I mean, it looks really

[00:02:51] **Tim:** good. Thank you. I wasn't fishing for compliments, but I know it looks good.

[00:02:57] **Carol:** Well, when you signed on, I was like, something looks different, but I thought maybe it was just your headset or you just had a haircut.

[00:03:02] **Carol:** I was like, yeah.

[00:03:04] **Tim:** I just had a haircut and it's not sticking straight out like, like alfalfa.

[00:03:07] **Adam:** So your headset, it looks like it has another, uh, skin graft on it over there on the other side. I had

[00:03:14] **Tim:** the cheap headsets. I keep having to stick them together, but yeah, that that's, that was a big deal. Just for me.

[00:03:21] **Tim:** Personal win. Winner. Very nice. How about you, Kara? I'm sure you can

[00:03:25] **Adam:** beat that.

[00:03:27] **Carol:** Oh yeah, mine's way better. Uh, I'm going on vacation, you guys. That is like a triumph. I mean, it has to be. So I'm taking my kiddo, my youngest one, the oldest is at college and obviously cannot go away for any time off. So I'm taking the youngest out to go snowboarding in Lake Tahoe for a few days.

[00:03:48] **Carol:** We're going to go do some snowmobiling and we're actually going to enjoy cold weather. Cause it's something we don't get in Georgia. Nice. Yeah. Super excited. So peace out, you guys. I won't be here next week. Have fun without me. A vacation sounds

[00:04:03] **Adam:** awesome. Yeah.

[00:04:04] **Ben:** Very cool. You will be missed, but enjoy yourself.

[00:04:08] **Ben:** What about you,

[00:04:08] **Carol:** Ben? What you got going on?

[00:04:11] **Ben:** So, this is a small win, but I enjoy thinking about the way I work. And, uh, typically my daily routine is that, like the first hour of the day I allocate to the more passion y type projects at work. Early morning is when I'm my most creative. And most passionate about doing random stuff.

[00:04:33] **Ben:** So it's usually my kind of side hustle work work. Um, so I was coming up on the hour of work that I have allocated this morning. And what I realized is that the thing that I wanted to get done, I wasn't going to have enough time to do. So in what I feel is typical agile mentality, instead of pushing the deployment to a later date, instead of what I did was de scope.

[00:04:59] **Ben:** The work that I actually wanted to deploy. So when I knew I wasn't going to get to a point where I was going to be happy deploying what I originally wanted to deploy, I stepped back and I thought to myself, What's the smaller piece of work that is still kind of cohesively complete? Let me aim for that and then deploy that.

[00:05:18] **Ben:** And then I can do the remaining features at a later date. But I just like the idea that I focused on getting the deployment out and not so much about worrying on. The actual, I don't wanna say the functionality, but I wasn't so married to the original concept that I needed to push the deployment back.

[00:05:36] **Ben:** And I think that sort of keeps me focused on always keeping that drum beating and always moving forward and keeping things moving to production. That's pretty

[00:05:44] **Carol:** impressive. Yeah. I'm not so good at that. ,

[00:05:48] **Ben:** it's, I, I mean, I think, you know, working in increments helps a lot because, Nothing is so big that it can't be pared down at least a little bit.

[00:05:59] **Ben:** And then obviously working behind feature flags, there's not this inherent fear about, well, I'm going to push out something but it isn't 100% complete and I don't want people to see it because no one's seeing it anyway, but I want to get it into production just so that the PRs are smaller and people don't have to worry about giving so much feedback on what's going out into the production.

[00:06:19] **Carol:** Yeah, I'm feeling that right now on that big effort we're working on. I had to nudge everyone this morning. I was like, we're releasing this Tuesday. Could you guys go review some more? Cause it's, I mean, there's like pull requests after pull requests. We've, we've broken it out, but there's still a lot to review.

[00:06:34] **Carol:** So if we could have gotten smaller chunks out, it wouldn't have been so much on everyone. Be nice

[00:06:40] **Tim:** to get there. But the important thing is, did you change your hairstyle?

[00:06:45] **Carol:** No, but I'm going snowboarding and you're not.

[00:06:50] **Tim:** Touche.

[00:06:51] **Ben:** What about you, Adam? What do

[00:06:52] **Adam:** you got? Well, before we go into that, I would love to, I think, be a fly on the wall for some code reviews or something.

[00:07:00] **Adam:** on your team because I still can't wrap my head around these small incomplete projects going out piecemeal into production sitting behind a feature flag like I get the concept of okay you know I did a part of it and that's out there behind a feature flag that's turned off but To me, when I'm doing a code review of something, I'm looking at the thing as a whole.

[00:07:23] **Adam:** And so to consider that part of it is already deployed, do I need to go look at that whole thing? I feel like we need to maybe do a show about feature flags, and so we can talk about this more in depth. I would absolutely love that. I thought,

[00:07:35] **Carol:** so the last time we talked about this sounds awesome.

[00:07:38] **Ben:** I mean, so just to give you specifics about what I was working on this morning, uh, I was taking data, uh, task list data, and I was re rendering it in a different view.

[00:07:48] **Ben:** So it's broken down by task lists are associated with screens within our product. And then each task list can have a number of tasks, you know, checkbox tasks checked or unchecked. I was hoping to have an MVP, like a completely functioning MVP, rendering all the lists, and you can check and uncheck and maybe add new tasks in this morning's deployment, but it was just, I'd bitten off too much.

[00:08:13] **Ben:** And so, instead of worrying about the interactivity of unchecking or checking a task, what I decided was that this morning's deployment was just going to be getting the data and rendering the lists with no checkboxes, so you could essentially see all the tasks that you have. But you can't check anything off, but from a data fetching standpoint, it's, it's feature complete.

[00:08:35] **Ben:** So now what's going to be happening is that the next deployment is going to be just adding the ability to mark tasks as complete. So it's, it's, you know, you could look at a list of tasks and say, well, that's not functionally complete if it's tasks and you can't check them off. But from a, from a sort of workflow standpoint, you can fetch data and render it as one.

[00:08:57] **Ben:** Okay. Gesture and then checking that data off as a

[00:09:00] **Adam:** separate gesture. So you're not deploying anything that is not functional in itself. It might not be useful without the rest of the project, but it's the feature that you're deploying is not gonna... Nothing

[00:09:15] **Ben:** breaks. Right. Yeah. Nothing breaks. Nothing renders in a crazy way.

[00:09:19] **Ben:** It's all, it's all meaningful. It's just not complete. Yeah. I think, I

[00:09:24] **Tim:** think we should dedicate a show to that. That sounds, I'd like to learn about that too. Don't do it next week. I want

[00:09:30] **Carol:** to be,

[00:09:31] **Adam:** pick a new topic. I guess. Well, I'm going to go here. I'm not on call this week, so no sad trombone on the podcast.

[00:09:39] **Adam:** And I'm just going to go ahead and call that a triumph. Nice.

[00:09:43] **Tim:** Oh. I will say, so I, I got so excited about my hair.

[00:09:50] **Adam:** I forgot. So you remember my

[00:09:53] **Tim:** failure last week was, or my triumph was, I just was kind to myself and gave up on my issue that I was struggling with with reddis. Yeah. So I came back to that today.

[00:10:05] **Tim:** And I realized that the problem was not Redis, which I assume was probably

[00:10:09] **Adam:** not the problem. Problem between the keyboard and the chair? Yeah,

[00:10:13] **Tim:** well, my testing. So it's almost like, you know, we have that big thing about testing. So my testing suite that I wrote, it was not doing one important thing. Problem I was getting when I would never would have got in production.

[00:10:27] **Tim:** I've only would have got with my testing harness that I built because what I'm doing is I'm building a large JSON struct that I stick into Redis and then I retrieve it in Redis and I'll update it from time to time. Problem is that my testing suite never would get rid. I was using the same. UUID just for testing.

[00:10:49] **Tim:** I'd use it over and over again because I have to have that, that I have to pass that to another API. So I mock the data. And so I constantly had this same UUID I was using over and over and over again, which was changing the state of what was stored in Redis. And every time I would do a new series of calls, I wasn't clearing it out because at the beginning of a real flow process, it would clear out.

[00:11:13] **Tim:** Anything in the Redistore that was there already for that UUID and build it from scratch. Well, I was taking one that was halfway built already and then grabbing stuff out of it and then making assumptions off of what was in it or it wasn't in it. And it was throwing me all these weird missing data.

[00:11:29] **Tim:** The data really wasn't missing. The problem was the way I have my code, my test suite set up, wasn't really simulating a real life functional process of it. And so as soon as I figured that out and I said at the beginning of my test call, Go delete any existing, uh, UUID that's there for this, uh, object inside of Redis.

[00:11:50] **Tim:** Delete it. All of a sudden, everything worked. Hmm. Nice. Nice. Yeah. How's it going? Tests, man. Tests, right? That's why you don't test.

[00:12:02] **Adam:** No.

[00:12:03] I

[00:12:03] **Carol:** mean, that's like the thing we talked about, I think it was a couple weeks ago. It may have been on this week's release of the show where I wrote all that code and my team was like, yeah, or my two design buddies were like, yeah, not really needed.

[00:12:16] **Carol:** And it was all because my test data said I needed it. So, yeah. Totally get it.

[00:12:22] **Adam:** So what are we talking about there? Well, if we're done discussing Tim's hair. Well, I mean, we could always come back to the hair. Then maybe we should find out what idiomatic code is and talk about that for a while.

[00:12:36] **Ben:** Awesome. So this is something I've been thinking about for a really long time, mostly because I listened to a lot of other podcasts and when you hear people talk about Java code or Ruby code or Python code or Golang code, people often.

[00:12:53] **Ben:** Toss around this idea of writing idiomatic code, and I couldn't tell you exactly what the definition of idiomatic code is, but my understanding is, is that within a particular programming community, there's a, uh, a blessed way to do some set of tasks. So, for example, in Ruby, doing data access, maybe idiomatic Ruby data accesses with active record.

[00:13:18] **Ben:** End. I can't give you a lot of other examples because I don't write a lot of idiomatic code, I don't think, which is, which is sort of where I wanted to go with this conversation, which is when I think about the ColdFusion community, I don't think a lot about idiomatic code. And we mentioned Adam Cameron's post the other, in one of the other episodes, and in the comments of Adam's post, Sean Corfield was mentioning that he always felt that the ColdFusion community was a little bit.

[00:13:48] **Ben:** Immature I I in the sense that they didn't have necessarily the mechanics that that larger programming communities have. Mm-hmm. in terms of your continuous integration and your T D D methodologies and so on and so forth. And I guess when I think about the ColdFusion community and the ColdFusion programming language in general, what I love about it is that there's such a diversity of approaches and ways to solve problems and.

[00:14:18] **Ben:** And I and I, and I don't know if that, maybe that just doesn't exist in other communities. So there tends to be this, this sort of bubbling to the top of the one true way to do a particular thing. Whereas in ColdFusion, you have a bunch of different ways to accomplish whatever you want. I mean, just take looping, right?

[00:14:36] **Ben:** You have four in loops. You have each loops, you have the CF loop tag. You have data access, right? You have script based queries, you have tag based queries, you have ORMs, you have people writing raw SQL. There's just a variety of different ways to do things and I don't know if that represents an immaturity or it's stunted the growth of the community in any way or if it's more like there's just been a lot of opportunity to find the right way to do something in a particular context and not worrying about necessarily shoehorning.

[00:15:09] **Ben:** One particular way into every context. Does any of that make any sense? I

[00:15:15] **Adam:** get it. Um, I, I still haven't decided whether or not I agree with you. Um,

[00:15:22] **Ben:** well, like, like take JavaScript, for example, if you're going to start a new JavaScript project right now, I mean, chances are you have, uh, like a prettier JS and an editor dot config file and.

[00:15:38] **Ben:** You know, a bunch of other things that maybe every JavaScript program uses. Whereas in the ColdFusion world, I think those standards don't necessarily exist. Because everybody has a different way of doing things. And I think that that's actually kind of great. Like, I love the idea that everybody finds the way to solve their problem and they're not necessarily...

[00:16:03] **Ben:** I don't want to say it's like you're burdened by this... By this homogeneity of approaches, it's, uh, it's that there's this beautiful chaos, if you will. Sure. And from this chaos, you know, births these wonderful solutions.

[00:16:22] **Adam:** So, I like that you used the word homogeneity because I feel like heterogeneity is a good thing in so many cases.

[00:16:32] **Adam:** I think that to look at it from a different... different lens for a second. I think that what you're describing is homogeneity. How do you pronounce that? Homogenous. What you're describing as a homogenous setup in coding projects, I think is, um, another way to say that would be sort of like community.

[00:16:59] **Adam:** Standards? And I think standards even might be a bit of a hard word. And I'm thinking specifically about your example in JavaScript about like, you know, people using Prettier and ESLint and whatever other tools to, um, have kind of like this boilerplate for a project, right? Um, and I think that the way that I see those tools being used in JavaScript is like it.

[00:17:24] **Adam:** It kind of gives you the ability to start up a new project and not have to, you've got like, these are the way I like to do things, right? I like my prettier, I can pull in my prettier config from my last project and my ESLint config and, and my editor config and whatever. And so those things follow me from project to project.

[00:17:41] **Adam:** Um, I don't know that that necessarily is what idiomatic code is. I'm,

[00:17:48] **Ben:** let me, let me, let me, okay, go ahead, Carol. No, I

[00:17:50] **Carol:** was just going to say, I think it's a lot of,

[00:17:55] **Carol:** So when I'm thinking about idiomatic code, I'm thinking about code that is uniform and is not necessarily, I mean, I know that if you kind of look it up, it's for that specific language, so maybe it is language driven by the language, but I just think it's kind of, it's not a standard. Like you said, it's not a standard.

[00:18:14] **Carol:** It's just more of the consistency of once you agree on what you're going to do, here's what it should look like.

[00:18:19] **Adam:** It's kind of like a style guide sort of thing. So, uh, yep. I know you're doing a lot of CFML code, Ben, so let's put it this way. So, a relatively recent addition to CFML would be member functions in a lot of the primitives, right?

[00:18:32] **Adam:** So, like array. map sort of thing is a relatively recent addition. Um, and... Since it is a relatively recent addition, a lot of people are really familiar and have muscle memory to not use those things. And so you might have some people that would really strongly prefer to use them because they like, they come from maybe a functional programming background or, or they use other functional languages and they want to do that sort of thing.

[00:18:57] **Adam:** Or you might have an agreement on your team not to use, um, member functions. And I think my understanding of idiomatic code is that somehow the community agrees on what the best is. And that's not to say that you can't deviate from what that standard is, but that by adhering to those standards, it makes it easier for somebody else from the community at large to participate in your project.

[00:19:24] **Adam:** So say it's like an open source project or you're hiring people from the community sort of thing. And if you're going to, if you have a good reason to deviate from that, then deviate. But, that it's, it's there to sort of provide that gentle on ramp for other people.

[00:19:39] **Ben:** Well, let me, let me just reposition it with a question.

[00:19:45] **Ben:** I don't think that I ever look at anyone else's ColdFusion code and think to myself, this isn't how ColdFusion developers would solve this problem. I might look at code and be like, this is not necessarily the way that I would write it or syntactically it uses a different style than I would, than I would write it.

[00:20:02] **Ben:** But, but I don't think I've ever looked at ColdFusion code and thought to myself, like, Oh, this is a Java developer trying to write ColdFusion code, or this is a Python developer trying to write ColdFusion code. And clearly they don't understand the idiomatic approaches that we have in our language. I just never feel that way.

[00:20:19] **Ben:** And that seems to be something that people have in other languages. I would

[00:20:22] **Tim:** say that's because there is no.

[00:20:31] **Carol:** I think that's what Ben said up front, was that he feels like our community or the CFML community doesn't have that.

[00:20:40] **Tim:** Is that a good thing

[00:20:40] **Ben:** or a bad thing? Well, and I guess that's the question being begged is, is I look at that and to me, that's a beautiful thing because it's, it's, it's a bunch of people finding.

[00:20:53] **Ben:** And the thing that solves the problem and ultimately allows them to deliver value to their customers.

[00:20:59] **Adam:** Okay, so let me, let me throw this, let me turn this around though. Um, so if that's your position, does that still hold true when you come into somebody's project and it's got... Nothing but CFMs, and it's a query at the top, and then an if statement, like if a form was posted to this CFM, then we're going to do a query to handle that form post, and then we'll, you know, have the view at the bottom, and like, that's one way of solving the problem, Ben, is that the beautiful...

[00:21:29] **Adam:** Here's the thing, though,

[00:21:30] **Tim:** I still... Welcome to

[00:21:32] **Ben:** 2001, baby! I still maintain some code that is like that, and yes, I look at it and I think to myself... This could be refactored, it could be cleaner, but it, it doesn't, it doesn't feel wrong. Yeah, it doesn't feel,

[00:21:46] **Carol:** see, I would look at it and say, it feels wrong. Yeah.

[00:21:50] **Carol:** I'm torn. I would have a hard time sitting there going, let's just leave it as is.

[00:21:54] **Adam:** Yeah. So I, I agree. With everybody, including the people that are not on podcasts, So I think the truth is somewhere in the middle, um, the concept of idiomatic code maybe gets a little bit of a bad rap because of some of the people who have been championing it for such a long time.

[00:22:11] **Adam:** So for me, the concept of idiomatic code, you know, uh, appeared in my life through Guido Van Rossum and Python, and the concept of Python. Programming and doing things, you know, the Pythonic way. So similarly to CFML, there are more than one way to skin a cat, you know, more than one way to append items to an array in Python.

[00:22:33] **Adam:** But there's like a Pythonic way, which is just sort of the Community agreed upon best way to do it, or I think in the case of Python, the guy who invented the language is more than happy to tell you, no, this is the way you should do it. And so that's why it has become sort of the, the Pythonic way. He literally wrote the language.

[00:22:52] **Adam:** He literally wrote the book on the language. And so he's telling you like, this is the way you should do it. And I think that that's what I think of when I think of Pythonic and idiomatic code. And so I think that the people who are. Turned off by that are probably right like just because the guy who invented the language Says that this is the best way to do it doesn't mean that there isn't a good reason to Do it another way, right?

[00:23:22] **Adam:** But then

[00:23:22] **Tim:** the flip side is I mean you can get this lava cake of code where people Adopt a certain pattern, and then a few years later, they realize, oh, there's, we should be doing it this way, and now you have this next layer, and then, like, let's take Ben's CF example, then they introduce CFScript, and now everything goes away from tags, and they have this CFScript layer, and, and, and then you, you add member functions, like Adam said, now you have this other, and you have this lava cake of, of code, it's, that's not idiomatic in any way, that's the opposite of it, and, To someone who comes in for the first time looking at this, it looks like a jumbled mess.

[00:24:04] **Carol:** That's because it is. Yes, yes, because they're, they're correct.

[00:24:08] **Adam:** But, but it works, right? Oh yeah, yeah. It does work. Messy code can work.

[00:24:12] **Carol:** But you also don't want to not adapt new things as they develop in your technology just because you can't change it all, because you can't change it all at once. You do have to, you know, start with new things with the new way in order to get it in there and get it working.

[00:24:28] **Carol:** I was just going to

[00:24:29] **Tim:** say that I think the have. That, uh, ColdFusion doesn't have is that they, many of them have very popular frameworks that are actually sometimes more popular than the base language itself, and a framework itself is going to be more dogmatic. Mm-hmm. about how things are done. I love the word dog.

[00:24:50] **Tim:** Yeah. And that's gonna lead to more idiomatic looking code. Mm-hmm. people can still make it look different. I mean, I've never gone to a That's true. A sample Java page. And that's using, um, what's a popular Java framework? Uh, grails Spring. Spring, yeah. I've never looked at a, a spring page and thought, what language is this?

[00:25:07] **Tim:** I look at it and go, oh, I can see this is, this is a Java based language. It's spring. Right. And a lot of times I've seen open source, like, other languages and I have no idea. I have to really look and go, what language is this? Because it doesn't conform to a certain style. I'm not saying that's good or bad, but...

[00:25:26] **Tim:** It does help the immediate recognition of issues.

[00:25:30] **Carol:** So I sent you guys a, um, a GitHub post, I guess, or I don't know what it is, actually. It's a repository. There you go, that's the word I'm looking for. Uh, it's Rick Walden, but basically it just has like a layout, it's like idiomatic JS. And it doesn't, it's, there's a spot in there I had read where it's like, look, this isn't the dog one for it.

[00:25:52] **Carol:** This is not how you have to do it. This is just what makes sense between a lot of people that do it, so that you can easily adapt and come into code and start reading it and know what's going on. And if it's all written uniformly and consistently, it's easy for people to come in and start learning on it and help you with projects.

[00:26:12] **Carol:** Like, one of the things is like, Who cares if it's quote, if it's single quote or double quotes? The key is you just pick one and do that every time. Don't mix it. I mean, that's an easy one.

[00:26:23] **Adam:** And I think to, to go back to something Ben has said on a previous episode about how much he hates prettier, uh, I think that that is the whole point of that project is like, you know, the decision gets made and you could, there is no right answer, right?

[00:26:39] **Adam:** Single quote, double quote, whatever. You make a decision and then you have a tool that makes it consistent for you. I think

[00:26:45] **Carol:** if you don't like it, don't write it that way and they'll fix

[00:26:47] **Adam:** it for you. Yeah. Um, I like that Tim talked about different frameworks and kind of the framework teams or authors. And it's kind of defining what is indicomatic for that framework and I mean I don't want to toot my own horn here, but as a as a framework author, you know, I've created TAFI We'll do it for you.

[00:27:07] **Adam:** Thanks And uh it's funny because I have Sort of subconsciously made an effort not to look at people's code that they write with Taffy because I know it would get under my skin. Um, you know, it's, it's tough to see people doing things in a way that you wouldn't do it. Um, and not that there's anything wrong with it.

[00:27:28] **Adam:** I'm, I'm super happy that people are using it, that they like the framework and that they're productive with it. And I would probably have an itwitch if I saw the way that some people use it. Um, so I just try not to, if I can, uh, you know. Look at it or look at it and then put it out of my mind. And I like the concept of, so I think maybe you're both right.

[00:27:52] **Adam:** So like the language, ColdFusion, the shepherds of the language, the various corporate shepherds it's had over the time, over its lifetime, haven't specified what would be considered idiomatic CFML, but the different Frameworks, whether that's like MVC frameworks or, you know, in my case, a REST framework or whatever, they kind of do.

[00:28:13] **Adam:** And I'm okay with that. Like, you know, you, when you move between a model glue application to another model glue application, or, or when you're using Cold Spring in one place or another, they, they look similar. And that convention.

[00:28:29] **Tim:** I would, I would take the other side, you know, of what I just said and say that, that people who insist on code being, I like to see, you know, I try to see both sides.

[00:28:39] **Tim:** People that try to be open minded. overly idiomatic who really, you know, buy into that, it really can just become the ultimate bike shed, right? Absolutely. Yeah. Ultimate triviality. You're like, well, you know what? We used to do it that way, but you know, this guy released a book about this and it's really much better to do it this way for dah, dah, dah, dah, dah.

[00:28:59] **Tim:** So now we're, now we're all going to do this, right? And it doesn't really buy you a whole lot. So you don't want to, you know, Blowing with the winds of whatever is fashionable at the day, because then you're going to, that would be another lava cake problem, where you're just adding layer and layer there because every time some really smart person comes up with a much more elegant way to do a certain thing.

[00:29:23] **Tim:** And now you're arguing that you have to do it that way. So it's got to. Ultimately, you want it to work, you want it to be readable, and you want it to be testable and be bug free.

[00:29:34] **Ben:** Right? There's something that you're saying in there, which reminds me of something else that I hear occasionally on podcasts, and it's this, it's, it's this feeling that people don't want to have five waves, five ways to solve the same problem.

[00:29:48] **Ben:** I've actually heard people on podcasts say, I don't want to have five waves to do the same thing. I want the one way to do it, and I just want that to be the way that I do it. And... I look at that and it's, that's not, I can't relate to that at all. I mean, half of the stuff that I do turns out to be worthless garbage, but it's an interesting experiment and maybe I never revisit it again.

[00:30:11] **Ben:** But some of the stuff that I do, I end up finding interesting patterns and stuff that I actually do refer back to and think about, oh, this is actually a new and interesting way that I could solve. This problem, like, uh, so in ColdFusion in the last few releases, they allow you now to iterate over things using parallel threads.

[00:30:30] **Ben:** And so I start to look at that and think, well, how can I use that to maybe parallelize data access in a way that we haven't been able to do historically in ColdFusion? And you could look at that and say, well, that's not how you're supposed to do data access, but well, maybe it is if I'm going to have long running queries and I want them to run in parallel.

[00:30:47] **Ben:** And I don't know, I, I just love that there's so much flexibility in the language and that flexibility to me has never felt like a paradox of choice. That flexibility has always felt like opportunity. and new and interesting ways to

[00:31:03] **Adam:** solve problems. Sure, I'm with you there. I, the, the ability to do things multiple ways has never made me uncomfortable.

[00:31:11] **Adam:** No, it's

[00:31:11] **Carol:** like amazing. It gives me opportunity to see it multiple ways. To look at how you get there using two different approaches.

[00:31:20] **Adam:** I think maybe though, thinking about it a little bit, maybe there's a little bit of like a paradox of choice situation here. So think about the junior developer, just fresh out of boot camp or college, and they're trying to learn the language and the tools, and now they have to learn Docker and Kubernetes and all that.

[00:31:37] **Adam:** And then also, oh, by the way, there's seven ways to add stuff to an array. You gotta pick which one is best for you. So

[00:31:45] **Carol:** good. I want to see what you do. I like, I want to see how you go down that route.

[00:31:49] **Adam:** Like ultimately I agree, but I think that the, it can be overwhelming to somebody who has to take all of this on at the same time.

[00:31:59] **Adam:** But I think

[00:32:00] **Carol:** if you threw them into just some front end JavaScript, they're still going to be faced with some of those same challenges. They're going to see multiple, you know, which package are you going to use? Like what version are you going to use? What are you going to do with it? So, they're going to have to be making these choices the rest of their life.

[00:32:18] **Adam:** I feel like this whole episode is just going to be, uh, we're for it, we're against it, we're for it, we're against it, we're for it, we're against it.

[00:32:26] **Tim:** I don't have a strongly held opinion on it

[00:32:28] **Carol:** at all. I'm not saying I'm for or against either. And to say that we, to say that the CFML community doesn't have, um, a true idiomatic way of doing it, I would say...

[00:32:42] **Carol:** It's a lot of what other people have posted. So if you go look at work Ben has posted in his blogs, you see that just copied back in. You see people just reusing what's already been designed and it's not, from my experience, it's not often thought of new ways. It's just how has someone else already solved this and I'm just going to redo that.

[00:33:03] **Tim:** Yeah, cut and paste is not programming.

[00:33:05] **Adam:** No. Careful there.

[00:33:08] **Ben:** Shots fired.

[00:33:10] **Adam:** I know you're always after your haters, but

[00:33:16] **Tim:** it's not.

[00:33:20] **Adam:** It's not as difficult as coming up with the algorithms on your own, but just, just because you found it online and, and you're like, oh yeah, that should solve the problem. I'm not saying like, I'm

[00:33:31] **Carol:** good with, try it, pull it in there and see how it works

[00:33:33] **Adam:** for you. Yeah. I mean.

[00:33:35] **Carol:** But you should understand what the code's

[00:33:37] **Adam:** doing.

[00:33:37] **Adam:** I just think we need to be careful not to categorically say, if you copy and paste a single line of code from Stack Overflow, then you're a bad programmer. Like, that's, and I don't think that's what you're trying to say, but I think if we're not careful to... I'm lazy. Tim's over there like,

[00:33:50] **Ben:** oh, he's... Wait a minute.

[00:33:51] **Ben:** Hold on. You

[00:33:54] **Adam:** are a programmer.

[00:33:55] **Tim:** But you're not programming right there. You're copying

[00:33:58] **Adam:** and pasting.

[00:33:59] **Carol:** We've talked about, like, me being lazy before. I don't want to type it out, so I'm going to copy and paste it and then just tweak a few things. Like, I don't want to sit and type out the whole line. I understand what it's doing.

[00:34:11] **Carol:** That doesn't make me bad, Tim.

[00:34:13] **Adam:** I'm not saying you're bad, I'm just saying it's not programming.

[00:34:17] **Ben:** So, here's maybe one other thought that I have. And maybe this is the last, like, real concrete thought I have on the topic, which is that

[00:34:25] **Tim:** Somebody wants to go to bed.

[00:34:29] **Ben:** When you're in a community... When there's a blessed way to do something and it's looked down upon to deviate from that course, then it feels to me like there's almost an elite group of people whose job it is to now evolve the language because everyone else has to be writing the idiomatic code and you have to have this, you know, Ivory Tower Architects, who eventually come in and say, Well actually, we've been trying some other stuff, and now this is the new idiomatic code that everyone should be writing.

[00:35:02] **Ben:** I don't know if that's, if that's a reality, but when I hear people talk about idiomatic code, that's where my brain goes.

[00:35:08] **Carol:** Okay, well if that's what it is, I don't want it. I vote no. Oh, I

[00:35:13] **Adam:** didn't realize we were voting. I want secret ballot. Off the island. Who's off

[00:35:18] **Tim:** the island? I mean, best practices always evolve.

[00:35:21] **Tim:** What is best practices today is not going to be best practices five years from now. Can we agree on that? Oh, absolutely. Right. So therefore, what's idiomatic today is not going to be idiomatic five years ago. So the idea of idiomatic code, to me, sounds like it's always going to be a moving target. So the...

[00:35:41] **Tim:** So, what is the purpose of it? I always ask what is the function of something that people are pushing and it seems to be readability, understandability, uh, being able to debug something, uh, being able to train new people into it. Without having to have like the, the gurus from on high, you know, bless a certain style, you know, if you do follow those things, you can say your code is idiomatic enough without being.

[00:36:14] **Tim:** The one true source, right? Because even, even the docs change, right? I mean, I mean, Java, Java's, uh, time date thing used to have like a bunch of mutators for the hour, day, second. Now we have like time zone, something or another that totally replaces it. So. You know, that all changes constantly, so I think idiomatic code is the ultimate bike shedding argument.

[00:36:38] **Adam:** Yeah, I agree. I agree. Totally agree. But you just listed off a whole bunch of... Potentially positive things that could come from having what, you know, would go quote unquote idiomatic code style guide, right? But I think where this becomes problematic is that it becomes, so you've got this thing that exists.

[00:36:59] **Adam:** This is the idiomatic code.

[00:37:04] **Adam:** And it exists for good reasons and then people take it and they co opt it for the purpose of creating us and them and like Ben was saying, and um, the people who want to feel superior, they can, they go, Ooh, I can become absolutely perfect at doing everything on this list exactly to spec. And then anybody who does anything that's That all deviates from this idiomatic code spec.

[00:37:29] **Adam:** I can point that out to them and that makes me better than them. And I think that that, where you see people enforcing like the iron fist of idiomatic code, that is the negative. Like the code standards themselves exist for the purpose of helping people. And for creating good things. All that stuff you just listed, Tim.

[00:37:53] **Tim:** But does it make the product better? It doesn't make my job

[00:37:55] **Adam:** easier. But it makes it easier for your team to work together. And their jobs too. Yeah.

[00:38:03] **Adam:** Uh, yeah, so I think those two things, what Tim just said and what Ben just said, I want to match those two together and that is the whole, thing, right? So you've got Okay, now I'm for it. Done.

[00:38:13] **Tim:** A Tim Ben baby. Yay! Oh God. Great

[00:38:16] **Ben:** hair. Oh,

[00:38:16] **Carol:** I know, right? Oh, wait,

[00:38:17] **Adam:** would it have hair? It would have your muscles and my hair.

[00:38:21] **Adam:** Or maybe it would have Ben's hair and your muscles. Oh no,

[00:38:25] **Tim:** that's not so good.

[00:38:29] **Adam:** This just got real weird real fast. I know. That's

[00:38:33] **Tim:** all right. All right. Meme Lords. We need some memes for that.

[00:38:36] **Adam:** Oh God. Terrifying. Well, I think

[00:38:39] **Tim:** it's been an interesting discussion. Well, I'm interested to see what, um, people out, out podcast think. What's your thoughts on idiomatic code? Is something you've thought about?

[00:38:47] **Tim:** Is something you care about? Do you think it's great? Do you think it's stupid? Are we right? Are we wrong? And what would Ben and I's baby look like? Oh my god.

[00:38:56] **Adam:** Yes, uh, I want to see some of those. Mmmmm, maybe. Maybe I don't. I don't know.

[00:39:04] **Carol:** I just feel like it's going to be

[00:39:05] **Adam:** a watermelon. It's like a train wreck.

[00:39:07] **Adam:** I'm sure that I want to see them, but I also don't want to see them. Um. Okay, so yeah, if you got, uh, thoughts on idiomatic code, or terrible photoshops of Ben and Tim, send them to us on Twitter or Instagram @WorkingCodePod. Um, so it sounds like we're basically done. You guys want to wrap it up there?

[00:39:28] **Adam:** Sounds good. So, before we get out of here, let's talk about our patrons on Patreon. We have, uh... not only a contractual obligation, but uh, overflowing heart that we want to thank Monte Chan, our top patron. Much love. And, uh, so Monte, thank you so much for your continued support and of course, thank you to all our patrons and all of our listeners because you are all supporting us in your own ways and we love you for it.

[00:39:51] **Adam:** If you're interested in supporting the podcast financially, you can check us out on Patreon at uh patreon.com/workingCodePod. Uh, and we have some different perks there for our different, uh, support tiers, so check them out. One of them is, uh, Discord access. I think everybody, all of our patrons get Discord access.

[00:40:07] **Adam:** So they get to come hang out and participate in discussions and we got early access to shows and stuff like that. So it's, it's a lot of fun over there in the, in the Discord talking to each other. Oh, and the after show, baby. Oh yeah, the after show. That's where we're, that's where we're heading after this.

[00:40:21] **Adam:** That's where the magic is. So, uh, thanks everybody for listening. Don't forget to share the show with a friend because, uh, word of mouth referrals are the best referrals. Uh, tell the algorithms to boost our signal by leaving us a review or rating on iTunes. Send us your topic suggestions on Twitter or Instagram @WorkingCodePod.

[00:40:39] **Adam:** We'll catch you next week, and until then, your heart matters.

[00:41:03] **Adam:** Ready Seti Spaghetti. Here we go. It's uh, An episode of our podcast that we do on days for topics.

[00:41:12] **Ben:** Nailed it.

[00:41:13] **Adam:** It's

[00:41:14] **Carol:** the best one

[00:41:14] **Adam:** you've done so far. Okay, here we go. Today. Damn it.

[00:41:19] **Tim:** Now you're just in your own head.

[00:41:21] **Adam:** I am. I'm good at this, right? Top tier podcast hosting.

[00:41:30] **Carol:** You get what you

[00:41:31] **Adam:** pay for.

[00:41:35] **Ben:** I shoveled snow today for the dog. That's not, not that she does it normally, but I had to, I shoveled an area in the back so that she could go pee.

[00:41:51] **Tim:** She's like, Ben, my tiny paws can't hold this shovel no

[00:42:00] **Tim:** more. I mean, one inches is a lot more than people think.
