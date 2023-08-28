---
title: '023: Book Club #1: Clean Code by "Uncle Bob" Martin (pt2)'
description: 'This week, the crew meets to finish their review of Clean Code: A Handbook of Agile Software Craftsmanship by Robert Martin (aka, "Uncle Bob"). This book is filled with so much thought-provoking information that it took us two episodes to get through it! And, while some of the practices in the book didn''t quite connect with the programming languages that we use or the types of applications that we build, our general consensus is that most of the suggestions in this book are spot-on.'
date: 2021-05-19
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/023-book-club-1-clean-code-by-uncle-bob-martin-pt2/id1544142288?i=1000522335297"></iframe>

This week, the crew meets to finish their review of [Clean Code: A Handbook of Agile Software Craftsmanship][clean-code] by [Robert Martin][robert-martin] (aka, "Uncle Bob"). This book is filled with so much thought-provoking information that it took us two episodes to get through it! And, while some of the practices in the book didn't quite connect with the programming languages that we use or the types of applications that we build, our general consensus is that most of the suggestions in this book are spot-on.

All-in-all, I'd say that our first attempt at a book review was a smashing success!

## Triumphs &amp; Failures

-  **Adam's Triumph** - He took a SQL query that was running for over 3-minutes, refactored it, and brought the execution time down to _30 milliseconds_. For those of you following along at home, that's a "4 orders of magnitude" improvement! There's nothing quite as thrilling as query optimization! But, anytime you get to describe an improvement in terms of "orders of magnitude", you are already winning!

-  **Ben's Triumph** - After spending weeks of his personal time building a ColdFusion custom tag DSL (Domain Specific Language) for generating HTML emails; and, then using said DSL in a company Hackathon to rebuild a bevy of transactional emails; he finally starting applying the approach at work! And, it's all going very smoothly!

-  **Carol's Failure** - She was so focused on putting together the mother's day plans (for her mothers) that she completely forgot that her son was coming home from his Freshman year of college. So, instead of going to get him, he had to rely on his friends (and their parents) to help him move back home. Of course, isn't a big part of going to college all about becoming more independent and self-reliant?

-  **Tim's Failure** - He is terrible at negotiating. And, the very act of "countering" an offer makes him feel like a bad person. In a contentious situation, his primary goal is to figure out exactly what he can say to bring the situation to an end. This is something he always wishes he was better at.

## Notes &amp; Links

-  [Getting To Yes: Negotiating Agreement Without Giving In](https://www.amazon.com/Getting-Yes-Negotiating-Agreement-Without/dp/0143118757/) - Offers a proven, step-by-step strategy for coming to mutually acceptable agreements in every sort of conflict.

-  [Never Split the Difference](https://www.amazon.com/Never-Split-Difference-Negotiating-Depended/dp/0062407805) - A former international hostage negotiator for the FBI offers a new, field-tested approach to high-stakes negotiations.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[robert-martin]: http://cleancoder.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/023-book-club-1-clean-code-by-uncle-bob-martin-pt2.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Uh, you know what we should do? We should just totally skip the section on tests just to piss off Adam.

[00:00:07] **Adam:** I was, uh, okay. If you want to do that, we'd piss him off.

[00:00:25] **Adam:** Okay, here we go. It is episode number 23 for, uh, I said 23, didn't I? Is it? Let me double check. Is it 23 or is it 22? It is 23. I only updated it in one of the two places. 22B. On today's show, we're going to continue our discussion on Clean Code by Uncle Bob, Bob Martin. But as usual, we're going to do our triumphs and fails first.

[00:00:45] **Adam:** And Tim, I'm coming to you first. What do you got? All right.

[00:00:48] **Tim:** Well, I've had a series of triumphs and the streak stops today.

[00:00:59] **Tim:** I suck at negotiation. I just got to come out and say, I suck at it. You would think, you'd think I'd be good. You know, I would like to be good at it, but I really bad at it. And I know this because, um, so every year our company, we have these things go by different names, but it's an annual. Cause we're a collection of companies.

[00:01:19] **Tim:** We're owned by a big parent company that has hundreds of software companies and they bring us together every year. Normally we go to really cool places like Lisbon or the Swiss Alps or Arizona or Las Vegas or whatever. Anyway, of course we stay, well, for the Europeans, Arizona was, they love it. But, uh.

[00:01:37] **Tim:** Yeah, so we Singapore, but this year we stay at home because of COVID and, uh, they send us a swag package. I'm thinking, Oh, cool. All the money they're saving, right? They're going to give us great swag. I got a insulated little thermos tumbler, a notepad, a pen and socks. Like I'm Dobby and they're just letting me

[00:01:58] **Adam:** go free.

[00:01:59] **Adam:** Everybody loves socks. Anyway, socks

[00:02:02] **Tim:** with the, with the little logo for this year's thing on it. Like awesome. Thanks. Uh, but anyway, so I had the sessions. We took these sessions on negotiation that we had to take. And I mean, it was extremely engaging, very interesting, a lot of role play and figuring stuff out, but I just realized just how bad at it the whole time I'm negotiating.

[00:02:21] **Tim:** I'm just like, how do I make this stop? I just want to agree so I can be done. And I realize in life that is the way I normally am when it comes to negotiation. I just get tired of negotiating and I feel, I realize I feel if I do a counter offer, I feel like I'm a bad person. Right? Like I'm saying, Oh, you're a liar.

[00:02:39] **Tim:** You didn't give me your best offer. I know you can do better. So how about this? And they come back and I'm like, well, I still think you're a liar. How about this? I know it's supposed to be, you know, the whole point of it was it's collaborative and you find the way your common ground is. But at the day, I don't like countering.

[00:02:55] **Tim:** I hate it. Yeah. Yeah. I just give my best offer and I'm like, take it

[00:02:58] **Adam:** or leave it. Yeah. I don't know for sure that this would help because I haven't read the book yet, but it's on my to read list is a book called Getting to Yes, which is kind of about negotiations and like trying to find things that are mutually beneficial.

[00:03:10] **Adam:** Yeah.

[00:03:11] **Tim:** The one thing that stood out with me that made me feel a little bit better, the lady who was running it, she said, You've heard the phrase, meet me in the middle, where you're like, all right, I'm at, I'm at a hundred. You're, I say 200, you say 100, meet me in the middle, 150. Really what they just told you is that they're willing to pay 150.

[00:03:28] **Tim:** So that's actually where you start in the negotiation. All right, we're in between 150 cause you're willing to pay that. We're in between 150 and 200. Can we come to an agreement? I'm like, okay,

[00:03:38] **Adam:** I get

[00:03:39] **Carol:** that. So you actually need to read Never Split the Different. It's by Chris Voss. He is an ex FBI negotiator and it's a book he wrote.

[00:03:49] **Carol:** He talks about salary negotiations, he talks about buying a car, he talks about like negotiating actual like hostage situations like with banks, robberies and stuff. So it's a really, really good book and it's on Audible, so I listened to it on the way back home. Like I've listened to it twice now in full, like from start to finish because I really,

[00:04:08] **Adam:** really loved the

[00:04:09] **Tim:** book.

[00:04:10] **Tim:** Cool. Well, I'll have to listen back to this podcast later and write that

[00:04:12] **Adam:** down. I'm going to add that to my reading list right now. I'll put it in the show notes. Never

[00:04:17] **Carol:** split the difference. It's good.

[00:04:19] **Adam:** Well, that's me. How about you, Carol? I have a

[00:04:20] **Carol:** big giant failure for this week. Um, as we're recording this, you know, we record a tiny bit early to get editing and stuff done.

[00:04:28] **Carol:** It's actually, you know, Mother's Day weekend this weekend coming up. Um, yeah, right. Happy Mother's Day to me as a great mom that I am.

[00:04:38] **Adam:** Kind of. Happy Mother's Day, Carol. Happy

[00:04:40] **Carol:** Mother's Day, me. So, I got really focused this week on getting my moms, I have two moms, so getting their presents ordered and shipped to them because I have to ship everything because we're not going back home this year.

[00:04:51] **Carol:** Um, I kind of forgot that right now, as we're recording this show, my son's moving out of his dorm at college, um, and his friends and their parents are moving all his stuff back home because he called and was like, Hey, are you coming to help me move out? I was like, when's that? He's like, uh, tomorrow? I was like, I'm busy.

[00:05:15] **Carol:** I'm

[00:05:15] **Adam:** sorry. You're on your own, kid. Welcome to the real world. I was like,

[00:05:19] **Carol:** I have to podcast. I'm like, why didn't you tell me sooner? He's like, you always know everything. I was like, Oh, crap. I've trained him to know that I'm on top of everything, so he doesn't think to tell me anything.

[00:05:32] **Adam:** Time to adult, son.

[00:05:33] **Carol:** Yeah, he's moving home without me. So he'll be back home for two months, I think, two and a half months, and then he's got an apartment back in August, so he'll go back to college

[00:05:42] **Adam:** in August. And this is his freshman year, right? Yeah, this is his freshman year. Yeah. So this is when it gets hard, right? Yeah. You know, you've been away at college.

[00:05:48] **Adam:** Now you come home and you're like, ugh. Yeah. Living at home sucks.

[00:05:53] **Carol:** Well, it's gonna suck for me because I'm gonna have two people here. I'm not excited about that. I've enjoyed having the house all to myself. Yep. That's me. Failures. I'll do

[00:06:03] **Adam:** better next year. How about you, Ben?

[00:06:05] **Ben:** I know I've had a couple of failures over the last few episodes, but I'm swinging back around to a triumph this week.

[00:06:11] **Ben:** And, uh, I think on previous episodes, I've probably mentioned that I had been working on a ColdFusion Custom Tag DSL domain specific language for building HTML based emails. And, uh, I had built that in my personal time and then I used it in a hackathon at work to rebuild like 16 different emails, uh, that we send out as part of our transactional email system.

[00:06:35] **Ben:** And, um, today I just finally deleted my Hackathon Git branch because I have been slowly merging it into our production work. And I've, yeah, I'm, I'm super excited that I've taken this thing that was total proof of concept and I've, and I've brought it through and, and polished it and, and hardened it and, uh, and now it's in production serving up, uh, Git.

[00:06:59] **Ben:** Customer emails. So, yeah, there's still a lot of emails in our system that, that don't use this approach. Um, but I'm, you know, I'm going to be dribbling in some effort to slowly get those moved over if I, uh, if I can. So pretty excited about that. How about you, Adam? What do you have

[00:07:14] **Adam:** going on? Minor win for me this week.

[00:07:16] **Adam:** I mean, it's gonna sound huge, but it really didn't take that long to figure out and it's okay, it's whatever. Um, I took a query. I just got frustrated, right? I was working on something and the page took forever to load and I went and looked at it and the query is very dynamic. It's pulling in lots of different SQL from different things and kind of squishing them together.

[00:07:35] **Adam:** And the query that it's running Ended up taking over three minutes to run. Dang. Um, and so I just took it off to the side and pulled it into the database management system and started trying to think about what I could do to improve it. And I got it down from the point where actually it took, it took a lot longer than three minutes to run.

[00:07:53] **Adam:** It was just at three minutes is when I decided, okay, cancel, you know, that we're well past the point of reasonability here. So some point after three minutes was the starting point. And I got it down to about 30 milliseconds. Nice. Holy cow. If I, if my math is correct, that's about a four orders of magnitude improvement, so I'm, I'm happy with that.

[00:08:12] **Adam:** I think that's totally acceptable and something to be happy with, so. Mm-hmm. , that's my triumph for today. I love query

[00:08:17] **Tim:** optimization. Yeah. Hundred percent. It's about, I just love

[00:08:19] **Adam:** it so much. I like seeing it. Yeah. I also

[00:08:21] **Ben:** love when something improves to the point where I can describe it in orders of magnitude.

[00:08:25] **Ben:** Yeah. , there's, there's definitely like a special, you're like, wait, is that. Yes, that's an order of magnitude

[00:08:31] **Adam:** better. Yeah. Yeah. So I did the math, right? So three minutes is 180, 000 milliseconds. And, uh, I got it down to the ballpark of 30 milliseconds. So I'm just saying that's two, two digits of milliseconds.

[00:08:43] **Adam:** So we chopped off four digits there. Four orders of magnitude. All right, well, uh, hopefully we moved through that relatively quickly because we wanted to save a bunch of time and try to spend as much of this episode as possible getting back into clean code. Yeah, let's finish this book. Come on. Yeah. Gosh, please.

[00:08:59] **Adam:** Can we? I really don't want this to turn into a six part series. Okay, so I think where we left off was artificial coupling. And Tim, you had mentioned, uh, a pretty good definition of that. Did you want to say that again?

[00:09:11] **Tim:** Yeah, I mean, I was just reading what the book said, so it, it's typically a result of putting a variable or constant or a function in a temporarily convenient place.

[00:09:20] **Tim:** So you put it there because at the time you're working on it, that's where you're working, but it's in an inappropriate location. Uh, so it kind of causes you to have to couple that, uh, class with perhaps another class. So, um, yeah, it's just, it's, the point is it's kind of lazy and careless. Figure out where these functions, constants, variables need to go and be declared.

[00:09:41] **Tim:** If they need to be in a separate class or just don't just toss them in wherever

[00:09:46] **Adam:** it's convenient. Yeah. I've been thinking about this concept, I think, indirectly a lot over the last week because um, I've kind of realized that I've gotten a little bit lazy, right? I've been working on the same product for, uh, six or seven years now.

[00:10:00] **Adam:** And when I, you know, when we first started out, everything was like very regimented. I had, I was trying to do TDD and, and everything was very cleanly laid out. And as you grow a product and you've been working on it for five plus years, it grows and it grows and it grows and things start to just kind of have a default place to go even though there might be a better organization.

[00:10:19] **Adam:** And so I, you know, I have some services that just have like hundreds of functions and I'm and it's like, well, okay, maybe that should be split into two or three or five services. So like Tim was saying, you know, that's, it's just out of being lazy, right? I've got, I've already got the dependency injection wired up and, or I would think to look for it.

[00:10:37] **Adam:** So that's where I've been putting it. And I think ultimately it just comes down to, to doing what is clean, right? That's the whole book, right? They'll do what's clean, not what's easy.

[00:10:49] **Tim:** And this actually bit me in this, my butt this week. Yeah. This, this, yeah. So project I've been working on that I talked about that I released all of a sudden, and I don't know why, maybe it's a.

[00:10:59] **Tim:** This was written in Lucy, ColdFusion, but I put something in the application scope and it really probably shouldn't have been there looking back now. But I'd done it early on, like it was super early in the project. I really wasn't sure where I was going. So I'm like, you know what, I'm just gonna stick this application scope.

[00:11:14] **Tim:** And some change basically triggered it so that... If I restarted the server, I have an event route handler. So the event comes in and it bubbles through it, figures out what the event is, and it will kick off an appropriate prompt based off that. Well, it didn't matter what I passed in. It always was the ending prompt.

[00:11:33] **Tim:** And I would think that restarting the service or, you know, restarting the application would, would have killed that variable. But it was basically holding on to that application variable, even if I restarted the application. So that the very last thing that had ran would be the only thing it put out, if that makes any sense.

[00:11:51] **Tim:** Kind of, yeah. So it was, it was, it was basically the in, in closing statement of the, it was, it was a process you go through and there's a last thing that happens. And that was the only thing that I'd pass something in, it would say, nope, I'm giving you the last thing. So I took it out of application scope, and it worked.

[00:12:06] **Tim:** So I kind of coupled that scope with... The whole process, I got to the point where I really thought I really should quit my job and go and just become a cook or,

[00:12:17] **Adam:** you know. Hey, at least you're good at cooking. Yeah.

[00:12:20] **Tim:** Go become a chef or something. I'm like, I am not good at this. I am obviously a terrible programmer because I don't understand how

[00:12:26] **Adam:** this is happening.

[00:12:27] **Adam:** It's a joke that I use more often when I'm frustrated than when I'm feeling not good at my job. But I often fall back to the, I should have been an ice cream man. Yeah.

[00:12:37] **Ben:** Is that, is that a reference to something?

[00:12:39] **Adam:** No. It would have been a lot easier job, drive, turn on the music, serve the ice cream. When I think about,

[00:12:46] **Ben:** uh, some of this coupling stuff, one of the things that I come back to is circular references, which if you're wiring components manually.

[00:12:55] **Ben:** That becomes a lot harder to do, but a lot of dependency injection frameworks make it relatively trivial to create a circular dependency because they'll instantiate a component first and then they inject all the dependencies afterwards. And I'm so on the fence about this. I tend to think that a circular dependency is some sort of a code smell, that you have these two things that are coupled together in a way that probably shouldn't be coupled together, like they know too much about each other.

[00:13:20] **Ben:** And I, and I often think that it's a sign that there should have been a layer of orchestration above those two things. So like if class A depends on class B and class B depends on class A, there should have been something that was making calls to both class A and class B in the right order, the right timing, and then orchestrating something that, so that they don't actually have to know about each other.

[00:13:41] **Ben:** But that's, it's easier to say, and then you start to build more complicated stuff. And you're like, uh, I really just want to reach over to that other thing. I hold strong to this idea that there should be an orchestration layer when I have circular dependency. All

[00:13:53] **Adam:** right, are we ready to move on? Sure. Next one is Feature Envy.

[00:13:57] **Carol:** I was going to say, moving on to that, the kind of opening to it. That's something that Ben just mentioned. So what is code smells,

[00:14:03] **Ben:** Ben? Code smell to me is something that just kind of triggers red flags in the back of your mind. That you look at it and you're like, that just doesn't feel right or doesn't smell right.

[00:14:13] **Adam:** It's like when you walk into a room and you go, oh, there's garbage somewhere in this room. What is

[00:14:16] **Carol:** that? Yeah. Okay. And it starts with that. It's like one of Martin Fowler's code

[00:14:20] **Adam:** smells. And the feature Envy in particular, I think the way that I think about this is it talks about, or the way that it's described looks to me like method chaining, right?

[00:14:31] **Adam:** So I need, uh, you know, BeanFactory. getFooService. getBarService. getWhatever. getWhatever and then do the thing that you want to do. And so you're, you're kind of traversing through your classes because the one class that you're in wants to do something with something for And that's the way that I understood what they were explaining there.

[00:14:52] **Adam:** That makes sense to you guys? Do you agree? Yeah. But then he also says it's a necessary

[00:14:55] **Tim:** evil and that you can't always get away from Petri Embry. Yeah. Which I agree with because sometimes, I mean, you have a function and it needs to do something another function does, which is... Why you call that other function, right?

[00:15:06] **Tim:** So it's not, you know, doesn't necessarily envy it, but it's using

[00:15:09] **Adam:** it. But then the sort of the other side of the same coin is like, if the thing that you're looking for is method chaining as the, as your data smell, then you have to be careful that it is actually doing the wrong thing. Because if you have like data structures, right?

[00:15:22] **Adam:** I know in CFML, we don't typically have like data structure classes that have like other, you know, getters and setters that return other classes type of thing. That's not super common. But in other languages, it could be. And if it's a strict data structure and not a service method sort of thing, then I think he specifically says that that would be acceptable.

[00:15:43] **Adam:** Not, that's not feature envy. Right. Moving on. Yep. Selector arguments. Is there anything more abominable than a dangling false argument at the end of a function call? What does it mean? What would it change if it were true? I totally agree. Like I get that visceral, what the heck is this? Yeah. Um, the, I guess the one place that I would tend to argue with that is yes, it is, I completely agree if the purpose of that true or false is sort of a switch in that function and, and the way that like it chooses between branches of logic, the time that I would say it's totally fine to have that as if you are like calling a data access object and that false is a value that you're recording.

[00:16:22] **Adam:** Right? Like this is, this is data. It's not a flag to indicate a decision. Yeah,

[00:16:27] **Carol:** but that's different. I think, okay, good. See, I like, I, I am a fan of breaking it out into separate functions. So like the example they give with calculate weekly pay. Well, if I want to get the overtime, I want a function that calculates overtime as overtime.

[00:16:42] **Carol:** I don't want to have a piece in that function that says if I'm overtime, I really need it to be 1. 5 multiplicative. If it's not, it's just one multiplicative. But I'd much rather have two functions than have

[00:16:55] **Adam:** it be

[00:16:55] **Ben:** one. One thing that I think of when I have these false arguments in the JavaScript world, just to take it to the client side for a second, is the addEventListener function, which takes typically the name of the event, the handler, and then a boolean.

[00:17:09] **Ben:** And I think you can also pass in an object in some cases, but that's neither here nor there. But the boolean there is whether or not you're in the bubbling or the capturing phase, which... It's like a radically different way to handle events. And it just feels like one of those things. Probably a Boolean felt like the weird way to do that.

[00:17:27] **Ben:** And then you run into a situation where most people, I would guess, probably don't even know what that Boolean is doing, which to me is like the worst possible scenario where people put it in because they don't understand why it should be there or shouldn't be there. Just like, that's what MDN said.

[00:17:42] **Adam:** So, I mean, I guess it sounds like we agree, right?

[00:17:44] **Adam:** Select arguments is just a bad idea. Okay, so the next one is obscured intent. Yes. Uh, hundred times yes. Hungarian notation is one of the things in here, and magic numbers. Magic numbers are

[00:17:57] **Tim:** so bad. I hate them with a passion. If I could just stamp out all magic numbers in the world, I'd, I'd, I'd. I could die a happy man.

[00:18:06] **Tim:** Right. And it's just sheer laziness, you know, why people do that. Like, oh, well, this is 0. here. Well, you know, where,

[00:18:14] **Adam:** where did that number

[00:18:15] **Tim:** come from? Why is it 0. 5? And what happens, what happens when 0. 5 changes? Yeah. What, what do you do? What, what, what does this number mean? Is that a percentage is, I mean, what is this?

[00:18:24] **Tim:** What, what are you, what

[00:18:25] **Adam:** are you doing here? Yeah. And then I think the, the biggest part of that chapter that I remember is that like it costs nothing to have a long variable name versus a short, variable name. Nothing. Do

[00:18:34] **Carol:** it be descriptive.

[00:18:35] **Tim:** You don't hurt the compiler's

[00:18:36] **Adam:** feelings. Yes. Yeah. Yeah, so, but we tend to, somewhere along the line when we're learning how to program, we learn to value short variable names for some reason.

[00:18:47] **Adam:** So, I,

[00:18:47] **Carol:** uh, have been helping my son every now and then with projects that he's working on in school. And, uh, the examples are like the instructions from the teacher. We'll have double A, double B, double C, so I'm trying to help him figure out, I'm like, what the heck is A? He was like, a double. I'm like, but what are you trying to do with this?

[00:19:08] **Carol:** I was like, and then he's passing A all over the place. I'm like, can we name these something else, anything? I can't do the A, B, C, D variables. No, give it a name. It's got to do something. It's got to

[00:19:19] **Adam:** describe what it is, right? Yes. Be explicit. Here's

[00:19:22] **Ben:** a subtle one that gets under my skin and it's probably very personal, but I think of numbers as, as being truthy falsy values where zero is a falsy and anything not zero is a truthy value and um, where this really trips me up.

[00:19:37] **Ben:** is when someone will have a variable name that is maybe not super obvious what the variable is supposed to be doing. And then they'll have like, if variable greater than zero, where in my mind, it would be a variable or if not variable because it's zero or some other not zero value. But when someone has a greater than zero condition, it always makes me think, can this number be negative?

[00:20:00] **Ben:** Like what happens if this number is negative? Cause it's like that, um, the concept of the exception that proves the rule. Like, if you're using a greater than, now you're making me think of less than, and that may have not been your intent at all. But the fact that you're treating it as a range and not as a yes no value, now makes me, it, it, it really obscures not only the intent of the code, but the, like, how well did the person writing this understand what the valid...

[00:20:26] **Carol:** Yeah, because if it's greater than zero, you should just be looking for, is it positive? It's less than, then it's negative. Nothing else should be evaluated. Like, it doesn't make sense.

[00:20:34] **Adam:** So, I mean,

[00:20:34] **Tim:** if you did, if you think of zero as false and anything else is truthy. Negative 10

[00:20:40] **Carol:** is truthy. Yeah, and truth and false.

[00:20:42] **Carol:** Yes, yes. But it should be false. Yeah. So I get it. I've never thought about it before. Like, I've never. But when you say that, I'm

[00:20:50] **Adam:** like, oh, yeah. So this all reminds me kind of of the robustness principle, which is be conservative in what you do and be liberal in what you accept from others. And so I guess for me, it kind of depends on where in the application we're talking about, like if this is in an API that somebody outside my company is going to be interacting with, you know, I might be more willing to accept a 1 or a 3 as truthy, and 0, minus 1, whatever, as Falsy, but in my own code and within my own systems, I would, if I'm dealing with integers, I'm going to tend to cast that to a Boolean as I'm evaluating it.

[00:21:25] **Adam:** Like, not, not whatever the number is in order to cast it to true or false. Well, and actually,

[00:21:29] **Ben:** and combining with the idea of magic numbers, and you see this a lot in, in things like Java and JavaScript, where negative one means something. And that's especially where when you have a greater than, it trips me up because I'm like, zero means something and greater than zero means something, but then I'm like, do you have some sort of magic negative one or negative two value that would actually change this logic that's not being obvious in the way you're dealing with the

[00:21:53] **Adam:** values?

[00:21:55] **Adam:** Everybody ready to move on? Misplaced responsibility? Yeah, I mean, his example

[00:21:59] **Tim:** of where should the constant I go, right? So you're going to put it in math, you're going to trigonometry or circle. Putting something somewhere, it needs to make some sort of sense logically that a programmer can look at it and go without knowing or, you know, with these days with code editors, you can just do a search, but to say where would this most logically be?

[00:22:21] **Adam:** It kind of all

[00:22:22] **Carol:** ties together with a couple of the

[00:22:23] **Adam:** other ones. Use explanatory variables. Uh, was this again kind of going back to the just use long variable names? Oh, uh, break calculations up into intermediate values that are held in variables with meaningful names. Right, so instead of having a one liner that's long, complex, you know, a bunch of calculations, break it up into chunks.

[00:22:43] **Adam:** Give those chunks names so that they make sense in what you're doing and then pull those chunks back together in the final calculation. I mean, I get

[00:22:50] **Tim:** that, but it kind of goes against, you know, he wants the functions to be as small as possible, right? So if you're doing that, it's going to make it necessarily bigger.

[00:22:56] **Tim:** But I mean, I guess the key here is the biggest thing I took from his book is make sure your code is explicit enough that when someone comes behind you, they know exactly what it's doing. Right. From that viewpoint, I totally agree that you want it to be a bit longer. If you're doing a whole bunch of manipulation on something.

[00:23:14] **Tim:** You need to break those steps down from a giant one liner that you've got to sit there mentally parsing for 10 minutes to figure out what it's doing. into steps. Right. And I just naturally do that because, I mean, honestly, I can't figure out how to get to those steps without breaking it down. But then a lot of times I will think, well, I'm supposed to do it in one step so there's less lines of code in this function and I will refactor it into the, back into the middle.

[00:23:40] **Adam:** I'm gonna stop doing that. Yeah, I was gonna say, I think that the goal should be to sort of refactor it out, right? If your instinct is to start with something complex and mush together, then the whole point of the refactoring is to come back and go, well, this part is a little confusing. Why is it, why is it the way that it is?

[00:23:56] **Adam:** So I'm going to break this up. Okay, this long regex, I'm going to give that a name. That's the email address regex or whatever.

[00:24:04] **Carol:** They can be reused too. Yeah. So, um, when I worked with Tim, a lot of what I did was like rating algorithms and it was all with just how, how things rated. Insurance rating. Yeah.

[00:24:14] **Carol:** Insurance rating. It was all with just how math works. It's just every step in the process and how it all tied together, like you're talking about rounding, you're talking about factors that get applied to it. There's just a lot to it. Mm hmm. And I realized when doing that, if I could break it out into the smallest piece possible.

[00:24:30] **Carol:** It was much easier the next time there was a change to, for someone else to pick it up and change that one little piece without having to redo everything over again. So then you were able to take out, you know, a small, tiny subset of it and see exactly what it was, where prior it was so massive that you pretty much just had to copy it all.

[00:24:50] **Carol:** And go figure out where all it was used against. The smaller you make it, the easier it is to maintain long run.

[00:24:56] **Adam:** Speaking of financial stuff, I guess this is probably a good place to talk about this one. Um, sort of a lesson learned for me over the last seven ish years. Um, so we do a lot of financial data and Something we decided early on that has worked really well for us is that we store all currency amounts as cents.

[00:25:18] **Adam:** Um, and then if we need to talk about dollars, then we convert it from cents to dollars. Something that we didn't do great early on that kind of bit us a few times and that I've started to be that squeaky wheel that, uh, forces everybody to update their code. Every variable that contains an amount of currency, I refuse to accept a code review with, for it.

[00:25:39] **Adam:** if it doesn't include a suffix of either dollars or cents. So that you is, it stands out like a sore thumb when you're trying to pass in cents to a function that's expecting dollars or you're dividing dollar, you know, you're adding dollars and cents or something like that. Like. That's kind of this next one.

[00:25:56] **Adam:** Is it? Yeah. Yeah. Yeah. Function names should say what they do. Good point. Okay. Well then we'll do that. Function names should say what they do, which I'm gonna, as the guy who always screws with his friends by turning on his left turn signal when he wants to make a right turn. I'm going to say no. Yeah, I

[00:26:13] **Tim:** totally, their example here is really great.

[00:26:15] **Tim:** So if you have a function called date. add5, what is that adding? Right. Five minutes, five seconds, five days, five weeks, five years. So it needs to be explicit, you know, increase by days, add days.

[00:26:26] **Adam:** Add minutes. Minutes. Yeah. Mm-hmm. , you

[00:26:30] **Carol:** just say what it does. Okay. And only do that. Yeah, exactly. It shouldn't add five days and then also go check to see if it is the current date, like the function, if it's called add five days, should only add five days and do nothing else.

[00:26:43] **Adam:** Okay. I don't think there's anything more to say on that one. You guys. No. Okay. I understand the algorithm.

[00:26:48] **Carol:** I think it's saying that you don't just want to. Make sure that the function is right. You need to also make sure that at the end, the result's correct too,

[00:26:58] **Adam:** right? It means just saying like. There's a difference between, it looks like it works, I think it works, and I know it works.

[00:27:05] **Adam:** And, you know, I know it works because I know exactly what it should be doing and I can see that it's doing that. Right? Like, you understand the math that it's trying, in your example of the math equations that you were doing before, you know, you could, if it's some complex trig formula and you have to go look up what the formula is, you've got the formula right there, is the function doing all the steps of that formula, yes or no?

[00:27:26] **Adam:** Understand what it has to do and make sure it's doing that.

[00:27:29] **Ben:** One of the places where I think I see this being symptomatic. In JavaScript code, when people just add a timeout, they're like, something's not doing what it should be doing. So I'm just going to put in a set timeout, 10 milliseconds, and now it works.

[00:27:43] **Ben:** And they're like, I don't know why it works, but like, you'll see comments in the code literally where people are like, I don't know why this is working, but without the set timeout, it didn't work. Yep. And you're like, oh, that's, that's not good. Waiting for the page

[00:27:58] **Adam:** I'm sure that there are many of those with my, my signature on them from earlier on in my career. Prefer polymorphism to if else or switch slash case. Someone explain

[00:28:11] **Carol:** to me what polymorphism is, means.

[00:28:14] **Adam:** Polymorphism

[00:28:15] **Ben:** is the idea that you can have multiple classes that are all subclasses of a, of a common set of properties and behaviors.

[00:28:25] **Ben:** And the typical one would be like, Animal, and then you have cat and dog both extend animal. So you can pass cat and dog, yeah, you can pass cat and dog to anything that expects animal. Okay.

[00:28:40] **Adam:** Yeah, it's object

[00:28:41] **Ben:** oriented. Yeah. I'll tell you there is like a deep hatred of switch statements in the world of programming and it has never connected with me whatsoever.

[00:28:51] **Ben:** And maybe it's just because I don't do a ton of like real object oriented programming. So I do a lot of procedural code that uses hella switch statements and it just works. I've

[00:29:03] **Adam:** never, um. I don't understand the hate form either. Yeah.

[00:29:07] **Carol:** They work for me. I mean, in times where I've used them, it's because I had a need for it.

[00:29:12] **Adam:** I don't think that I've ever encountered the code that this is probably trying to prevent. Yeah. Like, I'm trying to understand how an if else or a switch could be replaced with polymorphism, and it's just not coming to me. I mean, I guess polymorphism is sort of at the layer of a class, and the if else or a switch statement is kind of more inside of a function.

[00:29:34] **Adam:** So I'm trying to, I'm struggling to see the difference there and this chapter just doesn't stand out in my mind. Like, I think we've already kind of covered and agreed that like having a function that operates in two, three, four different ways depending on the inputs, not great idea. And if, oh, you know what, I bet you this is, so like, this is sort of like, um, you have this reusable class and You're passing it sort of a, a context or a, you know, this is how I'm using you right now, you're a dog, or versus right now you're a cat, then that would be more appropriate to replace it with a, a cat subclass.

[00:30:10] **Adam:** So

[00:30:10] **Carol:** I, I googled while you were talking because, you know, , it, it sometimes helps me a little bit to see something. Mm-hmm. So the example I found is actually on refactoring duck guru. Okay. And I'm gonna have to check this site out because it's kind of cool looking. So, it says the example is like, if you have a bird class, and you want to get the speed of that bird, the switch statement would be, if European, then get baseSpeed.

[00:30:37] **Carol:** If African bird, then get baseSpeed minus the load factor times something. If Norwegian, do is nailed, all this stuff. Where if you extend it out to a class and you do get speed, then you return the base speed. So then whenever you're adding to it, then the next time you need to do get color, you have the one call to it instead of having to have a switch everywhere.

[00:31:01] **Carol:** So now you have the one class of European that contains all of it, rather than a class always has it.

[00:31:10] **Ben:** I, I just feel like that. I don't write those type of applications and I think it's just maybe a skill level or maybe it's a classification of applications, but like, I'll do a lot of stuff in my code where in the applications that we write, we have enterprise clients and then we have non enterprise clients.

[00:31:29] **Ben:** And I definitely have all over the code base. Like if this request is from an enterprise client, do this thing. Otherwise do this other thing. And oftentimes that's calling different queries that return different types of data that are like somewhat overlapping, but not entirely overlapping. And the idea of creating some sort of polymorphic object that exposes a similar set of method signatures, but has different implementation under the hood.

[00:31:56] **Ben:** I almost feel like that would create. Um, incorrect coupling, like now those two method signatures have to change and like what happens down the road if actually the enterprise version and the non enterprise version have to have different arguments and now it's, or, or I guess you could do that in some cases, but I, I don't know, it, it, this just doesn't connect with me.

[00:32:18] **Ben:** No, I

[00:32:18] **Tim:** mean, actually now seeing what I found with,

[00:32:21] **Adam:** um,

[00:32:22] **Carol:** Carol, my name's Carol.

[00:32:23] **Adam:** Yeah. Sorry.

[00:32:25] **Tim:** That chick over there.

[00:32:26] **Adam:** That chick over there.

[00:32:28] **Tim:** Sorry. Um, yeah, I'm just seeing the code you're talking about, that makes sense to me. I could totally do that. I wouldn't have a problem doing that at all. I like that. So

[00:32:37] **Adam:** this is

[00:32:37] **Carol:** typically how we write things.

[00:32:39] **Carol:** Um, so I mean, I didn't even realize it until I'm looking at it. So we'll have our base class that is Animal, and then we'll have the form set of it, like the pieces of it. And then in base, we actually add something called, um, we have like a, an error handler that basically is not implemented. So if you do go into one of the, the function or one of the classes and you call something that's not actually applicable, then it'll throw a not implemented and you can't call it from this class so that you don't actually end up in error.

[00:33:10] **Adam:** Yeah,

[00:33:10] **Tim:** I'm, I'm, yeah, I'm doing something similar. So we have a multi tenant system, so I have a, sort of a base class, but then, you know, I extend it and really I'm, I'm calling the same function, but because it's a different tenant, it may need to do something differently. That's the way ours does, yep, yep. So that's, uh, yeah, I totally do this.

[00:33:30] **Tim:** Without even knowing it. Without even, I mean, I knew it was doing OO. I just realized it was polymorphism versus a switch class because yeah, a giant if statement in a multi tenant system would just be a nightmare. Yeah.

[00:33:42] **Adam:** All right. We are definitely gonna have to pick up the pace. Okay, okay. All right.

[00:33:46] **Adam:** Thanks, dad. Follow standard conventions. So basically use prettier and ESLint and bad and you're wrong. Just need them now.

[00:33:57] **Adam:** Uh, I'm not gonna argue with that one. I like, you know, I think Ben would even agree that there are good conventions and stuff to have and, and it's just whether or not you want a tool to enforce it for you, right? He's nodding his head. Sounds good. Replace magic numbers with named constants. We already discussed that.

[00:34:13] **Adam:** We already said yes. For God's sake, yes. Encapsulate conditionals. Yeah, a lot

[00:34:16] **Tim:** of times you have a whole string of Boolean conditions in a chain together with ands and ors and you, it really bends your brain to try to figure that out. Yeah. Creating perhaps one simple conditional even if it has to call other functions to figure it out.

[00:34:30] **Tim:** Yep.

[00:34:30] **Adam:** It totally makes sense. Combine all of those different aspects that you're checking in each conditional. Like if a and b and c or d and e and f. Combine all those into one method call or one function. Yep. Yeah.

[00:34:43] **Tim:** So their example is, if should be deleted and you're passing timer into it is better than if timer has expired and not timer is recurrent, right?

[00:34:52] **Tim:** And you're like, okay, what are these two things doing? You got to figure both those out, whereas it's very clear should time should be deleted timer. Yep. Okay. You know, it's doing one

[00:35:02] **Adam:** thing.

[00:35:03] **Carol:** Right. And it's reusable. Reusable.

[00:35:06] **Adam:** Reusable code. Avoid negative conditionals. I

[00:35:09] **Ben:** try to follow this one, but sometimes it's not that the negative reads better, but the opposite feels really awkward.

[00:35:16] **Ben:** Yeah.

[00:35:17] **Tim:** Mm hmm. Well, I think probably the thing that makes the hardest to be readable is when you have a double negative. So, uh, should not delete, right, is your, is your function name and you're doing not. Right. So, not should not delete. It's a double negative. Does that

[00:35:30] **Adam:** guess it? No. Yeah,

[00:35:32] **Tim:** okay. You're having to do mental gymnastics to figure out, all right, what are we doing here?

[00:35:36] **Tim:** Are we deleting it or not? Right. I totally agree with that. That's better to should delete. Should delete is pretty clear.

[00:35:42] **Adam:** Right. True, Paul. Yeah, you should delete and then you can throw a not before that if you want, but then, yeah, avoiding that double negative, that makes a lot of sense.

[00:35:49] **Ben:** Sometimes I'll create two functions, one that's positive and one that's negative, and the implementation of one is literally the not and then a call to the other function.

[00:36:00] **Ben:** So I can essentially choose which one reads better in a particular condition.

[00:36:05] **Adam:** Yeah, that's the thing that I just said some people do to try and get extra lines of code attributed to them. Functions should do one thing. Heck no, put everything in one function.

[00:36:17] **Carol:** No, Adam. Bad Adam.

[00:36:20] **Adam:** Function should descend only one level of abstraction.

[00:36:24] **Adam:** Maybe that was what I was thinking about with the, uh, method chaining.

[00:36:27] **Ben:** Yeah, this is an interesting one. Cause I, uh, this relates back to the idea that a function should do one thing. And, uh, I know in the book he talked about, you can sort of tell if a function's doing more than one thing if it has multiple levels of abstraction inside of it.

[00:36:43] **Ben:** Um, like it has both low level and high level calls, I think he was saying. I don't know, this one was very hard for me to wrap my head

[00:36:49] **Adam:** around. All right, moving on. Names. Okay, yeah, here we go, let's talk about names. Choose descriptive names. Don't be too, don't be too quick to choose a name. Think

[00:37:00] **Carol:** of it as naming your first child.

[00:37:03] **Adam:** God, I'm not having that long of a discussion to name every variable. So, I

[00:37:09] **Carol:** actually sent this to, I didn't send this to my boss, but I sent that to my director because, um, the DevOps team asked me what to name the Google Cloud Platform service user that I created. They're like, what name do you want this service user to have?

[00:37:24] **Carol:** I sat there like 60 seconds and then sent that exact message to my director of engineering and said, what name do you want this to have? And then I told him, don't forget, I named both of my children the same thing because I hate naming things. He was like, noted. I was like, naming is not my friend. I spend way too much time trying to like figure out what to name something so that it's good

[00:37:46] **Adam:** forever.

[00:37:47] **Adam:** Yeah. I mean, I don't think there's a whole lot to say here. You know, it's, it's like one of those. What's the saying, um, there's only two hard things in computer science anymore, caching, validation, naming things, and off by one errors. Yeah.

[00:37:59] **Tim:** Honestly though, this, this section was transformative for me. Cause like I think I said in the last podcast, I tried my best to like have short names.

[00:38:08] **Tim:** It just felt like. That was required of me. But yeah, I'm totally naming everything very descriptive from

[00:38:13] **Adam:** now on. Because it just is a good reminder. Good refresher.

[00:38:16] **Tim:** Yeah, totally. But naming, naming things is hard because once you start naming something, you're like, wait, this is really similar to another name.

[00:38:23] **Tim:** I named something else. So how is it different? That's really where it gets hard is thinking. Alright, I have two names, two things that are doing something very similar. What is this one doing that the other one isn't and how do I represent that in a name?

[00:38:37] **Ben:** I struggle a lot with that one when I have a function that does nothing but transform its input.

[00:38:44] **Ben:** So imagine that someone submits a search and I want to normalize that search by maybe like lower casing it or like removing punctuation or something. So maybe that function is called normalizeSearch. And then the variable that I store, the return value is normalized search. And people will stare at that and be like, well, how are you assigning a function to a function?

[00:39:04] **Ben:** I'm like, no, that other one has a D in it, but I never, I just, I really struggle to come up with a better name for what that thing is supposed to be. But I

[00:39:13] **Carol:** like that because it. It is what the function is. Like, it is the return of that is the normalized string. Like, it is the normalized input. And the function is normalizing the string.

[00:39:26] **Carol:** To me, it makes sense.

[00:39:28] **Adam:** Something that maybe might keep it easy to think of, but then also still make that same amount of logical sense, is to swap it. You've got a normalized search string function, right? And so you're, what you save the result of that to, instead of calling that normalized search string, I would call it search string normalized.

[00:39:45] **Adam:** So you're doing search string normalized equals normalized search string. So it's a little bit more clear that they're different things. Oh, that's not bad. Use standard nomenclature where possible.

[00:39:55] **Tim:** I like how he dates himself with his example. Auto hang up modem

[00:40:00] **Adam:** decorator. Hey, we're talking about modems.

[00:40:02] **Adam:** They're still relevant. 1998's coming, bro. Use long names for long scopes. So that's like, um, if you're doing a for loop and it's got one or two lines in it, it's probably okay to call your variables in that for loop I or J. But if you're, you know, for a long function or for a for loop that is 40 lines long, then It's probably better to say...

[00:40:25] **Adam:** for item in collection, whatever sort of thing. Yeah. I mean,

[00:40:30] **Tim:** honestly, he totally maybe questioned everything I do and have ever done. And so when he's talking about the long names, like, does that mean, so I'm doing a for loop and all I'm, I mean, I've always used I for the index, right? It's good. Does that mean I have to name it something?

[00:40:46] **Tim:** And then I got to this and I'm like, oh,

[00:40:48] **Adam:** okay. Right. But then, you know, who among us hasn't had a, like a long loop in a view where you're looping over like a, to create table rows and there's 40 columns and you name it I, and you're like, oh, okay. Um, avoid encodings. So that's like prefixes like F for function or A for array sort of thing.

[00:41:10] **Adam:** Like, yeah. Yeah. This dude hates Hungarian pollution. Yeah. Pollution. I guess there was a phase in my career when I kind of favored Hungarian notation. Cause I. I was a big fan of Joel Spolsky's blog back when he was like still writing it. And he made a decent case for why it was useful at the time. It was like for doing Excel, like formula math.

[00:41:30] **Adam:** So you would know like, you know, it wasn't so much like int or array prefixes. It was more like row and column prefixes. So that you would know, okay, I'm I think I'm in the context of columns here or the context of rows instead of data type.

[00:41:43] **Ben:** It's funny, sometimes you get into conversations with people who are like, die hard against Hungarian notation, but then you'll point out something that they do that's Hungarian notation.

[00:41:53] **Ben:** And they're like, well, no, I mean, in that case, it makes total sense. Right. Like, um, like in the jQuery world, people used to use the like a dollar sign after a variable that was a jQuery collection. Or, um, in the reactive world, they'll put like a dollar sign at the end of something that's an event stream.

[00:42:09] **Ben:** And you're like, you realize that's like, now you're building the type into the variable name. And they're like, yeah, but that's so people know it's, it's a stream. And you're like, yeah, that's what Hungarian notation is.

[00:42:20] **Adam:** Yeah, I hadn't thought about that, but actually, yeah, I still do that. I put a dollar sign.

[00:42:24] **Adam:** I usually put it at the beginning of my jQuery collection variable names. But stop pointing out my failures, Ben.

[00:42:31] **Ben:** Although, and sometimes if you have an algorithm that transforms data again, I think sometimes having a type to, to show the transformation makes sense. So a lot of times I'll have. An array of IDs, and I'll call it UserIDs, and then I'll do a toList on it, and the variable that stores that is UserIDList.

[00:42:51] **Ben:** So now I have UserIDs and UserIDList, and I use those in two different ways. And I'm saying that it's a list, but I want to differentiate it from the fact that it was just an array, you know, a line ago. Uh, you

[00:43:01] **Adam:** know what we should do? We should just totally skip the section on tests just to piss off Adam.

[00:43:09] **Tim:** Okay, if you want to do that, we piss him off. But I mean, that was sort of the whole point of him telling us to read this book, was it was about, it was a reaction to art. All of us saying

[00:43:18] **Adam:** that, uh, we don't do enough

[00:43:19] **Tim:** testing. We don't do enough testing. Some don't do any. And, uh, some of us don't do enough.

[00:43:24] **Tim:** Ben. And I'll get there. I'll get there, Adam. I'll get there. Your hate, your hate will motivate me to be, be a good tester. To build tests. I do build tests. I just don't build enough.

[00:43:33] **Adam:** Yeah. I think that's true for most of us. And I build them in the wrong order usually. Mm hmm. Alright, let's just talk about, let's go through, like, list all the testing topics and then that'll be the easiest way to discuss them.

[00:43:43] **Adam:** We'll just list them all and then have a quick chat. So insufficient tests, using a coverage tool, don't skip trivial tests, an ignored test is a question about an ambiguity, test boundary conditions, exhaustively test near bugs, patterns of failure are revealing, test coverage patterns can be revealing, and tests should be fast.

[00:44:03] **Adam:** Now that one. That's where I want to start. Tests should be fast because when we had our testing show, that was the reason that I said I kind of backed away from testing. That was the reason I let myself give myself permission to back away from testing. I can't make this sound good, but the tests were slow.

[00:44:21] **Adam:** Yeah. Um, actually, so In intervening months since we did that show and now I've kind of had this revelation that I think a big part of the reason that my tests were slow is because they were integration tests and some end to end tests and they were doing a lot of database work because that's this is a very data heavy app and we are using the ColdFusion ORM in this application and the the revelation that I had was that even though we're using ORM we should have written our code using data access objects.

[00:44:53] **Adam:** To do the ORM calls and having that layer of abstraction to, to interact with the database. would have made it a lot easier, or should I say possible, to do mocks for those data calls, which would have made the tests faster and a lot easier to use. That's just like something I've learned in the last few months about testing and ORM and it makes me hate ORM just a little bit less.

[00:45:19] **Ben:** Let me ask you a question because I don't, I don't do a lot of testing as we've discussed. Really? When I hear people talk about tests, They'll often talk about mocks and I often hear a lot of opinions about how you should try to avoid mocks as often as possible because then you're not really exactly sure that the system is doing what you intend to be doing.

[00:45:40] **Ben:** And I, and I guess my question is, I don't understand the difference between a polymorphic implementation versus a mock. Meaning, if I have an object that it takes a data access, another, you know, has a dependency on a data access component, and that data access component exposes methods, and one implementation of it writes to a database, And another implementation of it just writes to an in memory object because it's not doing database I.

[00:46:07] **Ben:** O. Like, is that, is that what people are calling a mock or is that just a non database implementation of that data

[00:46:14] **Adam:** access interface? I would say that that is a very basic and, I mean, I hesitate to call it naïve, but maybe a naïve mock. Um, a lot of the more interesting mocking tools that I've seen, you, you do that, right?

[00:46:27] **Adam:** You, you start with a class that mimics the API of your actual DAO, and then in your testing, uh, code, you, you wire that into the component under test to use the testing term, and, Then you make, you, you run the method that you're testing and afterwards you run some special methods on the mock that assert certain things have happened, right?

[00:46:52] **Adam:** You expected the function to be called with these arguments and you, you know, number of times or that sort of thing. So it, it kind of adds a little bit of expectations to what happens to the other side of that function call. Okay. That makes a little bit. And it also allows you to Another, where was this?

[00:47:13] **Adam:** I did something with mocks that I was really happy with not terribly long ago, um, that, um, you, and actually I'll, I'll give a shout out. I used mockbox, which I really like their way for, um, doing, uh, like mock query objects. They have this sort of a DSL for creating a quick query that you're going to return in a response.

[00:47:33] **Adam:** And, Everybody's probably real familiar with trying to create test data within your tests. Like, okay, when you get this back, this is what we would expect, right? And so you can have a couple of different Predefined responses in your mock and say, okay, call the method and get this one back. And that way you can test every use case without having to put the database in a specific context or you know what I mean?

[00:47:59] **Adam:** Like set the data up the way that you want it to run the test, then run the test, then put the data back to some other way or whatever. Right, right. You just kind of have the data in the way that you need it in order to run the test as part of the mocks. Anyway, this whole testing stuff in general, I think we would all agree this a great ideal to strive toward.

[00:48:17] **Ben:** So one thing that I will add, and this is not in the book, but in subsequent interviews that I've heard with Uncle Bob, and he talks about the developer's oath, like the Hippocratic Oath, but for engineers. Yeah. He talks about being able to quickly and accurately prove that a system does what it's supposed to do.

[00:48:36] **Ben:** He says, and using tests is probably the best way to do that. But I think it's interesting that he almost talks about The provability of the system as an abstraction and the test is an implementation detail of

[00:48:48] **Adam:** that. No, I, I totally agree. And actually, that testing section was the last. That was it. That was the end of the book.

[00:48:55] **Adam:** Um, so I was thinking we're a little bit long, but if we try not to, there's a lot of pauses there. I

[00:49:02] **Tim:** think it's probably going to cut down a lot. So if we maybe want to kind of do an overview, just kind of general

[00:49:08] **Adam:** takes on the book. Yeah, that's kind of where I was headed to. Like I have a few notes, but not, not anywhere near as much as Ben wrote in the document there.

[00:49:14] **Ben:** No, no, I didn't really write anything. I just copied and pasted a bunch of quotes.

[00:49:18] **Carol:** So there was one section that I really liked and it was talking about threading. Okay. And, uh, he was talking about just testing that. And when you have a failure with something that threaded, way often people go, oh, it's just a one off.

[00:49:31] **Carol:** Oh, yeah. When in reality, it's actually a problem. And you should definitely spend time looking into it because it's going to happen again. Oh, yeah. you know what, we do that all the time. Like, just in general, not... Now, but I've done that a lot. I've been like, oh, that's just a one off. It's fine now. It's not happening again.

[00:49:47] **Carol:** And I don't know how to duplicate it. So I'm like, oh, if I were to actually spin up tests with multiple threads, I probably could then see what's going on with it. Threading is tricky. It

[00:49:56] **Adam:** is.

[00:49:57] **Ben:** I, I like hard agree with everything that he says about threading and about error handling and typically about.

[00:50:05] **Ben:** Separating out the asynchronous code from the non synchronous code and separating out the error handling from the business logic. Um, I read that. I'm like, yeah, all day, all day. Let's do

[00:50:17] **Adam:** that. Like high five. Yeah.

[00:50:20] **Ben:** I'm also a huge fan of throwing exceptions and I'm, I'm happy that. He is also a fan of throwing exceptions and, uh, and, and, and will even, you know, has it illustrates that returning error codes and having to bubble error codes up through various call functions help, uh, hurts the readability of the code, which I a hundred percent agree.

[00:50:41] **Ben:** Yeah.

[00:50:42] **Adam:** I, I, I agree with you. Throwing exceptions is a very useful thing because they can bubble up. Right. As far up the stack as you need them to go, I will say I, for a while there, I got out of the habit of doing that because, and this was earlier on in my career, um, you know, somewhere around the like ColdFusion eight, nine days because I saw some information that throwing exceptions was expensive in terms of performance.

[00:51:08] **Adam:** And just returning, you know, a result that explains this is a, you know, bad case or whatever was significantly faster. But I think in more recent versions, it's probably not the same, right?

[00:51:20] **Tim:** And one would hope you wouldn't have a system that just is returning exceptions all day

[00:51:24] **Adam:** long. Need to fix them.

[00:51:26] **Ben:** I'll tell you, one of the phrases that I think is the most unvaluable statement.

[00:51:31] **Ben:** is when people say that exceptions are for exceptional cases. And I'm like, no one knows what you mean when you say that. And like, if you call a function and you don't give it the right arguments, that's an exceptional situation. And, and, you know, like, ah, I just bothers me. Yeah. People say really abstract things

[00:51:50] **Adam:** like that.

[00:51:51] **Adam:** Most of the things that I wrote down here were just interesting nuggets, nothing like that I think we're going to dive deep into. So I just want to go through a couple of these things. So early on in chapter one. He makes a comparison to martial arts to make the point that it's not necessary to follow all the rules of the book to be a professional programmer, just that it's kind of necessary to be correctly practicing.

[00:52:13] **Adam:** the aspects of professional coding, like your flavor of martial arts, right? Jiu jitsu and taekwondo are very different. Right. But, and so you, you know, you wouldn't expect the person doing jiu jitsu to do all the same practice as the taekwondo person. So I thought that was a really good way to explain the difference, um, and how not everything applies in every situation.

[00:52:36] **Tim:** You know, I think when you're exposed to something new and, you know, he exposes to a lot of new things, you know, probably 50 things. I probably can only take on 10, maybe five, honestly, at this point. And so the things I'm taking on to adopt, and then later I can adopt the rest, is be extremely explicit in the naming of my functions and my variables, make my functions extremely small, and make my classes discrete and concise and in the right place.

[00:53:04] **Tim:** And cohesive, yeah. Those are the things I'm taking on. Um, and And test. Adam. I'm going to try my

[00:53:10] **Adam:** best at test. Another one that I have written down here, I just wrote Java Ugg. Which

[00:53:16] **Tim:** is funny because you're writing ColdFusion, which is basically a Java engine. Yeah.

[00:53:20] **Adam:** Yeah. But you don't see it. Although I did, something about it.

[00:53:24] **Adam:** I think it's just because it's a funny name. I kind of enjoyed when he was talking about pojos, plain old Java objects. Uh huh. Like, uh, you know, I enjoyed that. One,

[00:53:33] **Ben:** uh, I want to read one quote from the book that connected with me a lot and, and has not this quote specifically, but this mentality has really changed the way I program I think in the last two years.

[00:53:44] **Ben:** And it's this. It is a myth that we can get systems right the first time. Instead, we should implement only today's stories, then refactor and expand the system to implement new stories tomorrow. This is the essence of iterative and incremental agility. Test driven development, refactoring, and clean code they produce make this work at the code level.

[00:54:05] **Ben:** And the idea of, of just... Solving today's problems today and tomorrow's problems tomorrow. I know early on in my career, I stressed a lot about future proofing things way more than they probably needed to be. And now. I just solved today's problems today, and if it comes up tomorrow, I solve tomorrow's problems tomorrow.

[00:54:25] **Ben:** And it's, it's really removed a lot of the complexity from my code because it starts out a lot more simple when you solve just the problems you need

[00:54:33] **Adam:** to solve. I totally agree. And also, if you're focusing on just solving today's problem today and doing it in a clean way, that's going to probably set you up for You know, the problem that you thought you were going to have tomorrow, but it's actually six months later to where you want to reuse something, it makes it a lot more reusable.

[00:54:51] **Adam:** And I'll zoom out

[00:54:53] **Tim:** a little bit here from just the hands on keyboard developer perspective and zoom out to. Make sure that you have a revenue model that allows you to have incentive to work on continuing to improve it. Yeah. So if your revenue model is, we'll build this for you once and we'll give it to you and deliver it to you and there's no future hope of revenue other than just an engagement where, you know, we do some big, uh, professional services contract, it's not going to work, get worked on.

[00:55:22] **Tim:** So some sort of revenue model where there is constant maintenance that's built in. I know this goes beyond the scope of the. Of the book. But from a business perspective, the only way you're going to get people to work on something to make it better over time because you're gonna have to, is to make sure that you are making money and profit over time.

[00:55:44] **Tim:** Mm-hmm. to pay those people to do that. So if you don't have a model for that, then your model's broken, and then whatever you're writing is gonna get stale. Yep. It's gonna get old. No one's gonna fix it. It ain't gonna break because no one's touching it. 'cause no one's getting paid to touch it. But it's not going to get any better.

[00:55:59] **Adam:** Yeah, this is, this is like the classic argument for writing tests in the first place, right? Like, this is the... Having tests keeps us from having regressions and makes it easier and faster to develop a new feature or, you know, fix a small little bug and just slam it through the test process and out the door into production versus having to go through a lot of manual testing.

[00:56:24] **Adam:** But like, I think when you just described that, people tend to agree, but then when you say, okay, but now I want I want to pad out my estimate, you know, I said it was going to take a week to write this feature. Now I want to have two weeks so I can do all the testing too. That's where people start to balk, right?

[00:56:39] **Adam:** And like you said earlier, Tim, testing tends to be something that gets cut early. Um, I think probably just because it is. A huge upfront investment, even though it pays dividends for a long time. It is a big investment. I think my point was more

[00:56:56] **Tim:** to the fact that unless you have a revenue stream to encourage you to continue to improve your product, you're not going to improve your product, regardless of testing, if you're

[00:57:05] **Ben:** testing or not.

[00:57:06] **Ben:** There's always a conversation about just general return on investment for so many things. I mean, I can't tell you how many times I'll open a really old piece of code. And I'm just like, Oh, this is garbage. And I really want to refactor it. But then I have to remind myself that no one's touched this code in five years.

[00:57:24] **Ben:** And like, probably no one will touch it again for another five years. And I'm just here to fix some like really obscure bug that someone happened to run into. And like, there'd be very little return on investment to, to like spend a day refactoring code that would have taken me five minutes just to fix and move on.

[00:57:41] **Tim:** And sometimes it's hard for, I mean, if you have customers who understand, why am I paying this? Well, you're paying this because if you want this to continue to get better year after year, then that's why you're paying this. If you just want this to be what it is right now and it will never ever change, then yeah, sure, go ahead.

[00:57:59] **Tim:** But don't

[00:58:00] **Adam:** ask me to do it. Yeah, that's the thing. It's like, I think the naive assumption is when you're buying software from somebody, right, your customer buys software from you, they expect it to be perfect and it never will be. And so there, there's going to be some expectation of some bugs and things will have to improve and add features later.

[00:58:17] **Adam:** And if they're not willing to pay for those, then they should be willing to accept the fact that those bugs are going to be there and they're not going to get fixed. Yeah. And that's the

[00:58:27] **Tim:** conversation I typically have with customers. Like, why are we paying for this? Well, that you're paying for this because if you want to continually get better, then we have a motivation to do so.

[00:58:36] **Tim:** I mean, businesses understand, they'll understand. There is no, if I'm making money off you now, in the current state, and I have no opportunity to make any more money, then I'm going to keep it at the current state. Yeah. So, there's

[00:58:49] **Adam:** incentives. Okay. I only have two other little things here in my notes, um, one is, and this was, I was reading the audiobook, or I was listening to the audiobook, and I don't know if this was specific to the audiobook, or if it came up in the written section, too.

[00:59:03] **Adam:** But, uh, at one point, I think it was toward the end, the plural of schema, as in like database schema, was given as Schemi, which just, a huge eyebrow raise from me. Octopi? Yeah. Octopus, octopi? Yeah. S C H E M double I, excuse me, what? Not Schemas? Right. I was like, eh, I don't know about that one. And then, uh, the other thing I wrote down here, this was actually something I didn't even see in the book, but I, you know, I was, I had my head in Clean Code Mindspace and I happened to catch this post on Twitter, um, that was to somebody's blog post talking about a, a thing that Martin Fowler wrote about refactoring, and in the blog post, and this was the call out that somebody had put on Twitter, uh, and pardon my French, I'm going to curse here, but, uh.

[00:59:52] **Adam:** My virgin eels. He said, uh, you're not refactoring, you're just changing _(quack)_.

[01:00:00] **Tim:** I've done that. Yeah.

[01:00:02] **Adam:** I've totally done that. Like

[01:00:03] **Tim:** if you're... I look at it and I'm like, yeah, it

[01:00:05] **Adam:** doesn't look any better. Yeah, I think the context is more like, you know, if you're not, if you don't have tests, whether that's manual tests with a script or, or what, but... If you're not doing testing, real rigorous testing after you make changes, then you're not actually refactoring, you're just changing _(quack)_.

[01:00:20] **Adam:** And you should think of it that way, right? Like, oh, you know, why was this, why'd you make this change? I was just changing some _(quack)_.

[01:00:27] **Tim:** But overall, great. I mean, I'm, I

[01:00:29] **Adam:** really glad. Oh yeah, absolutely. I feel like a much better programmer. I'm so

[01:00:33] **Carol:** happy Adam sent it.

[01:00:36] **Adam:** I think it

[01:00:36] **Tim:** should be require, require reading for every dev.

[01:00:39] **Tim:** I, I, like, I

[01:00:40] **Adam:** agree, but only now having finished it, do I agree? Like going into this, I was kind of reading it begrudgingly, like, oh, fine. I hate reading nonfiction. I'm glad I did.

[01:00:52] **Tim:** Thank you, Working Code Dev, for making me read a book.

[01:00:55] **Ben:** I think it's like halfway through the book. He's more explicit about the idea that a lot of things are oftentimes Uh, at odds with each other and that you, to Tim's point earlier, you can't have all the patterns all the time.

[01:01:09] **Ben:** Uh, I think that people who are earlier on in their career, maybe I can only speak for myself here, like that's the thing you don't get. Like that's, you don't have enough experience to understand that a lot of these things are at odds with each other. And that oftentimes you have to make a calculated decision about which thing you're going to use and which thing you're purposefully not going to use in order to keep the code clean.

[01:01:33] **Ben:** And then by trying to do all of them all the time is not clean. And that's, that's something I think just comes with experience.

[01:01:39] **Tim:** I mean, this is definitely the viewpoints of a grizzled veteran who's been in the trenches of war for years. You know, a person just coming out of college with a CS degree, they're going to read this and they're still going to make the same mistakes we made.

[01:01:53] **Tim:** Oh yeah. But if they really take this to heart, they might make less over a shorter period of time. So,

[01:02:00] **Adam:** God bless

[01:02:01] **Carol:** you. Or they may be able to appreciate what they're looking at for the people who've written it before. Yeah. Like, okay, I can tolerate this and make

[01:02:11] **Adam:** it out. All right. We finished the book. Yeah.

[01:02:15] **Adam:** Does anybody else have any other notes you want to talk about before we go into the after show? All right, well then I guess that means it is time for me to thank our patrons. So there are a bunch of people that like what we're doing here enough to support us on Patreon and we really appreciate them.

[01:02:31] **Adam:** Our current funding goal is to be able to pay an editor so that I don't have to do all the editing every week. And I think that we're about halfway to that goal. Uh, so thank you to everyone helping us get there. Uh, if you can't support us financially, but you want to help out, the best thing that you can do is to help spread the word about the podcast.

[01:02:48] **Adam:** The more people there are listening, the more there are that are willing to kick in a couple of dollars per month to help us reach those goals. So if you think we've earned it, you can support us at patreon.com/WorkingCodePod. Every patron gets an invoice. Every patron gets an invite to our discord server, which is where we hang out and also where we organize fun stuff like the game night we talked about last week.

[01:03:09] **Adam:** And we have other perks available like early access to new episodes and our after show that we're getting ready to record. Um, our top tier on Patreon is for people who want to pay a little bit extra and to repay their favor, we thank them by name or shout out something, uh, in their honor. So we have two top patrons so thank you very much to Peter and also this week's sponsored shout out is

[01:03:31] **Ben:** Black Girls Code.

[01:03:33] **Ben:** Which is an organization that hopes to provide young and preteen girls of color opportunities to learn in demand skills in technology and computer programming at a time when they are naturally thinking about what they want to be when they grow up. That is BlackGirlsCode.com. I'll tell you, just on a personal note, I know I didn't get into computers when I was in my late teens and it just, it felt super empowering.

[01:03:57] **Ben:** There's something so wonderful about being able to have an idea in your head. And then being able to actually build something and, and turn that idea into reality and it, uh, it's empowering in a way that, that I think few professions are and, uh, the more people we can get involved, I think the, the more diversity of ideas we bring into the community and the better things will be for, for everybody.

[01:04:22] **Adam:** Absolutely. For sure. Okay, and to everyone that just listens to the show, thanks for listening. Uh, please share the show with your friends and your co workers because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:04:39] **Adam:** Send us your questions and your topic suggestions on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until then,

[01:04:52] **Tim:** your heart matters. And especially you, Adam Cameron, you're my number one hater and it makes my heart so happy.

[01:04:59] **Tim:** So, so happy.

[01:05:26] **Carol:** The recovery runs. So you basically just run at a have fun, don't stress, make sure you're, like, feeling loose and relaxed, so. It's a 40 minute headspace recovery

[01:05:36] **Adam:** run. It's a, it's a take it easy run instead of a push yourself run.

[01:05:40] **Carol:** Yep. I run those after my speed runs, which are fartlicks. Isn't that a great word?

[01:05:45] **Carol:** Fartlicks? Fartlicks. It's Swedish for, um, speed play. So it's intervals. So I do like my mile pace for a minute and then 60 seconds of recovery speed and then the mile pace, which is like seven

[01:06:01] **Adam:** minute miles.

[01:06:02] **Tim:** It's, you know, my, my wife living in Sweden, when I met her, she, you, when we go to visit, the signs, instead of like, there's an entrance and an exit, and it says, it's in fart and out fart.

[01:06:15] **Adam:** Nice. I think we're gonna give ourselves a PG 13 rating here. Who burned a popcorn in the microwave? That actually

[01:06:22] **Carol:** smells good to

[01:06:23] **Adam:** me. Ugh, ugh, ugh, you're fired.
