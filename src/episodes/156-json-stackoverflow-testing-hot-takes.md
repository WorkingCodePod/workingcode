---
title: "156: JSON, StackOverflow, Testing - Hot Takes"
description: "On today's show, we cast off the social filters and lay down some hot takes!"
date: 2023-12-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/156-json-stackoverflow-testing-hot-takes/id1544142288?i=1000637671105"></iframe>

On today's show, we cast off the social filters and lay down some hot takes! This journey of spice serves up the separation of concerns, the future of StackOverflow, the value of comments, the necessity of testing, the role of extracurricular coding, the beauty of clean code, the meh of JSON, and the challenge of building truly great products.

Some of these hot takes are clearly wrong; but, _I'll never tell_!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/156-json-stackoverflow-testing-hot-takes.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** People that say Jason suck and people that say JSON are right. Yeah.

[00:00:05] **Adam:** the, so, yeah, basically json5 or json5. is, like, everything that you hate about json or json, json. How about we go with that? Json.

[00:00:15] **Carol:** Jason.

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go, it's show number 156, and on today's show, we are going to talk about our hot takes, share our controversial opinions, it's the only hot takes edition, uh, um,but first, as usual, we'll start with our triumphs and fails, it would be Ben's turn to go first, but, he's got an excused absence because he's feeling a little sick tonight, so, I guess that means Carol, you're up.

## [00:00:57] Carol's Triumph

[00:00:57] **Carol:** Well, lucky for him, I'll start us off with a big win. I'm going to call it a triumph. I had my team kick off in Dallas last week and it went phenomenal. Just to feel like I have the support of so many people with this project and with the changes that are going to be, happening over the next few months to the next two years.

[00:01:15] **Carol:** It's, it's really, really nice to finally get face to face conversation with these people and see that there's potential. And it, it gave me, A nice little, like, boost to, to get in there and get going. So, team kickoff was a huge success and I really enjoyed it.

[00:01:32] **Adam:** And how many people on the team?

[00:01:34] **Carol:** my direct team right now is only three people.

[00:01:36] **Carol:** So, it's me, a product owner, and a BA. But we are opening and have several hiring, like, spots out for three more engineers, another BA, and a Scrum Master.

[00:01:50] **Tim:** Did you say you were in Dallas?

[00:01:52] **Carol:** yeah, we went to Dallas. Yeah. Yeah. I didn't get to do anything. I didn't feel that great. Like when I travel, I just end up like done. Like it's just exhausting.

[00:02:01] **Carol:** So it was pretty much hanging out with them all day and then dinner and back to my room. So I didn't do any sightseeing or didn't venture out. But what I did see, I enjoyed. There were Christmas lights up, but yeah, that's me. What about you, Tim?

## [00:02:15] Tim's Triumph

[00:02:15] **Tim:** Oh, work wise things are, you know, just steady state going, going good. Got the whole team back. We had some people out for extended time over Thanksgiving. Good to have everybody back. we'll be doing a strategy session coming up in a couple of weeks. So looking forward to doing that. We'll talk about that probably in the next.

[00:02:31] **Tim:** A few weeks on the show, but, personally, you know, I'm going to, Adam's going to say, I've got more coat tails to ride on. So

[00:02:39] **Adam:** Switching from one coat to another.

[00:02:41] **Tim:** just changing coats here. super proud of my daughter. She, they have a thing here. It's called star student. And it goes to the person in the senior grade who got the best SAT score.

[00:02:51] **Tim:** And she was selected a star student. Because she had the highest SAT. So she gets to pick a teacher, that, that influenced her the most. And I'd become the star teacher. And then they have like a, a dinner and a ceremony for them. And then, it's sort of like a school by school thing. Each school denominate, yeah, sends people.

[00:03:09] **Tim:** Then they do a little interview process with each of them. And then they do like, it's for scholarship money. They do a thing. They pick one person out of the region. Be the star student for the region. So super proud of her. She's super smart.

[00:03:21] **Adam:** she should get like a letterman's jacket but instead of the letter it just says like nerd.

[00:03:26] **Tim:** Right.

[00:03:27] **Adam:** And I mean that in a good way, like I, I would, I would absolutely be super proud of that.

[00:03:32] **Tim:** Yeah. And I'm glad they, they do that. I mean, the sports guy people, they get all their recognition and honors for sports, but honestly, you know, sports is an important part of school, but the main thing in school is education. So you need to be winning at that. So

[00:03:46] **Adam:** Mm hmm.

[00:03:47] **Carol:** She graduates this year, right?

[00:03:49] **Tim:** Yeah. She graduates this year, so we'll see if, if she's maintained her number one standing and is valedictorian.

[00:03:54] **Adam:** And then what are the, what's the school gonna do next year without a Cunningham ringer

[00:03:59] **Tim:** I don't know. I, I, I don't know. I'm sure they'll survive. They'll

[00:04:03] **Adam:** the bar gets

[00:04:05] **Tim:** Yeah. Just, just close the doors, just shut the whole place down. They're done guys. Anyway, that's me. How about you, Adam?

## [00:04:14] Adam's Fail

[00:04:14] **Adam:** I'm going to go with a fail. so you guys, you were talking about, people taking time off, people were off for around Thanksgiving or whatever. I had a coworker that was out last week for, you know, just his, you know, brain break, really, they didn't go on vacation or anything that I know of, he just like needed a week off.

[00:04:32] **Adam:** and I saw some code. I'm trying to like, what is the short version of this story? So. I needed to add some code to do some data cleanup. And I saw that we had a lambda called data cleanup, and it was like kind of built in a way where it's meant to be like, okay, this is going to run on a pretty frequent schedule.

[00:04:51] **Adam:** If you have data cleanup tasks that you want to do scheduled, add them here. And so I added mine there. And it was already like in lambda, you know, production lambda function. it looked like it was ready to go. it had the code deployed to it and everything already. So I was like, okay, cool. No big deal.

[00:05:08] **Adam:** Add my code. and then I went up and I just kicked it off real quick to get that first one done. And it did not go well. And, long story short, it was not ready for production. It had not yet been run in production. And it was not a good thing that I ran it. it was one of the data cleanup tasks. It, you know, it's one of those situations where like, You come across some code and it was written like a year ago and then kind of forgotten about.

[00:05:35] **Adam:** I don't know that it was exactly a year ago. Actually, I think in this case it was two years ago. that I, I, you know, tried to run it and, and then, then later realized like that was not something I should have done. Basically, you know, I've, I've talked in the past about we have some of these data tables that have millions upon millions of rows in them.

[00:05:52] **Adam:** and it was. Intended as like some cleanup for that, right? Let's archive old rows out of this table, that sort of thing. That's one of the jobs it was doing. But for whatever reason, I, I don't know, it took a really dumb, naive approach to cleaning up that table and it dropped a very important index on that table.

[00:06:14] **Adam:** And then it was going to like delete a bunch of data and then recreate the index, which it would be totally fine in a very naive, like early stage for our product. But. Since it has millions and millions of rows, that was not a good idea to do that. And it's a table that we're like almost constantly reading and writing.

[00:06:31] **Carol:** Oh,

[00:06:32] **Adam:** Um,

[00:06:32] **Tim:** and so effectively I dropped an important index in production in the middle of a workday, and just because I ran a function because I thought it was safe to run and it was not safe to run. So how long did it take to get that thing to

[00:06:46] **Adam:** for, yeah, fortunately, I realized fairly quickly what was going on, and I was like, okay, well, good, I'm glad, now that explains why this function wasn't actually scheduled, it was just sitting there waiting to be run.

[00:06:58] **Adam:** and, yeah, so, and I was able to, like, manually recreate the index, and there was just degraded performance for the next, like, two hours while the index was recreated. yeah,

[00:07:08] **Tim:** could do about it.

[00:07:09] **Adam:** you know, it's like, sorry, heads up guys, this customer is going to be a little slow for a while.

[00:07:15] **Tim:** out to lunch sticker on the, on the website. Be back at, be back at 2 PM.

[00:07:20] **Adam:** So the, the, you know, that's fail enough to begin with, but there's really like a double secret fail here. which was that, you know, I, I mentioned we had a coworker that was out for that week. And I, for some reason, I had it in my head. Cause I think he's talked about doing this project in the past.

[00:07:38] **Adam:** I could have sworn that was his code. And it didn't occur to me to check, get blame or anything like that. No, it was my code. I wrote this, I wrote this terrible abomination and let it sit there in production, unused and forgot about it for two years, came back, added to it, ran it and

[00:07:54] **Tim:** Bum, bum, bum, bum.

[00:07:58] **Adam:** gun at foot, pull trigger. Yeah. So that was pretty bad.

[00:08:04] **Carol:** Well, did you at least get rid of it so it can't happen again?

[00:08:08] **Adam:** No, because I'm going to fix it. I'm going to, you know, I learned from my mistake and I know at the very least, I know not to run it now. And I informed the whole team, don't run this function. It's not scheduled and that's for a reason. And, I'm going to go through the code and clean it up. The only reason I haven't gotten to it yet is because we're, you know, as the year is drawing to a close, we're trying to like check off a bunch of customer facing things.

[00:08:35] **Adam:** so we have like a big bang end of the year, you know, like a couple of weeks of like all kinds of, customer facing features and stuff to announce. So that they go into the new calendar year feeling good about us. And so my, my personal interest, I think, is more in the infrastructure. How can I make my team more effective and faster and that sort of thing. And so I've kind of had to set a bunch of those tasks aside, like this data cleanup. But, so that was fun, not fun, like, sorry, not sorry.

## [00:09:10] Hot Takes

[00:09:10] **Adam:** Alright, I guess in that case, that brings us to, our hot takes, and, and, you know, when I say hot takes, I'm talking hot, right? Like, Python is a garbage language because it requires the use of spaces, not tabs. That's the kind of heat I want you guys to throw this week.

[00:09:25] **Adam:** I,

## [00:09:25] Separation of Concerns is Dumb and Wrong

[00:09:25] **Adam:** I'll throw, I mean, I just threw a big heavy punch to start, but I got, I got a good thing here to, to kick it off maybe. I'm going to say that at least as, as we think about them right now, separation of concerns is dumb and, and wrong. you know, so typically as web developers.

[00:09:43] **Adam:** Somebody says to you like separation of concerns, usually what they mean is like HTML goes in a file labeled html or whatever the templating language of your stack is, right? If that's a CFM or whatever the view files are for NET and ASP and all those other things. Anyway, and your CSS goes into a CSS file and your logic goes into, you know, your whatever, JavaScript, TypeScript.

[00:10:09] **Adam:** CFCs, et cetera. and I just don't believe that to be true anymore. I think that with modern tools, the better approach is everything co located like by feature, basically. Like, you know, React really changed the way that we write code for the web and made it totally possible to do components and stuff, and I'm not here to trump up React.

[00:10:34] **Adam:** I, I think that, it's time to move on from React, right? I mean, no. bones about the fact that I'm in love with Svelte. and man, just everything about working with Svelte is amazing. You've got a single component and it's got your logic, it's got your templating stuff, and it's got your CSS all right there.

[00:10:52] **Adam:** You decide the component doesn't belong anymore. You delete the component and all three of those things, the logic, the templating, and the CSS, just poof, gone. You don't end up with like a CSS file. That's got 10, 000 unused rules in it or any of that.

[00:11:05] **Adam:** And you guys

[00:11:06] **Adam:** are just silent tonight.

[00:11:08] **Adam:**

[00:11:08] **Carol:** I know, no, I was going to say, I think I'm still really old school because I enjoy opening the code and seeing like a views folder and seeing controllers and seeing models and having, everything broken out separately, because I end up in this very weird, like, spot where I go, where do things stop relating to each other?

[00:11:28] **Carol:** So how do I know when it needs to go outside of this structure and into like, its own new structure? I like to know that every view exists. In the views or that the controllers are all inside the controllers, and then they're broken out by functionality. So what the system's doing, the models are the same way.

[00:11:50] **Adam:** I think to maybe counterpoint that, you know, the, the argument that I'm trying to make here is that you're not, when you're working on a thing, right? You're designing a table or, you know, a certain component within your application. Why should you have to open three files or four files or five files that, that are all sort of related for this component or for this feature?

[00:12:13] **Adam:** When it could just all be in one file,

[00:12:16] **Carol:** Can it always be in one file though,

[00:12:19] **Adam:** in, it depends, right? So there's gonna, even in Svelte, right? So you've got, you've, you've got a clear line between server side and client side for certain things, right? So, you know, you've got the, you can kind of start with, if you only think about the client, you've got your logic, your templating, and your CSS all there in the component.

[00:12:41] **Adam:** And then for data loading, if you're gonna like query a database, you write a loader, like a page. server. ts. and it returns data that gets automatically fed into the page, component or the page object. and that, so there's that clear line between client and server. But that I think is mostly to protect us from ourselves.

[00:13:06] **Adam:** Like, I don't think it would be impossible for Svelte to figure out how to, separate that for us so that you don't have like database connection stuff loaded down on the client. I think that they do that for our benefit. Not for, because of some limitation in the, in the framework. Does that make sense?

[00:13:26] **Carol:** a little, I think I would need to see it to fully understand it.

[00:13:29] **Tim:** I'm kind of struggling with this one because when you say separation of concern, that, that can mean, depends on what level you're talking, right? You can zoom in and zoom out and there's different areas of. Where you're separating concerns. Like for instance, you know, back in the day, HTML, you know, you could do both the semantics and the styling with HTML only, and then later we get CSS.

[00:13:54] **Tim:** And so, so CSS starts to deal with the style. So that's a separation of concerns, right? HTML is doing one job, CSS is doing another. and then JavaScript inject that into there too. It's, it's dealing with. With other, you know, DOM manipulation, potentially. So, I mean, that's a separation of concern. I, I, I can't, I'm not saying, you're not arguing that that's bad, right?

[00:14:15] **Carol:** I think he is. That's what I heard.

[00:14:18] **Adam:** think I am too. I just want to make sure I understand the question, right? Is it, I think that the way that you're describing it, the way I'm hearing it from you is that it's a very old mentality, right? So the, that is the type of separation of concerns that I'm referring to, right? People say you shouldn't put your CSS in your HTML file.

[00:14:37] **Adam:** It should be in a separate CSS file. and I think that that mentality. Is just outdated, right? So the reasons you have to always look at the underlying reasons. Why did people say these things? And, and, I mean, eventually it became a cult of personality. That's just, everybody says it because everybody says it.

[00:14:55] **Adam:** but the underlying reason I think was, you know, the amount of data that had to be transferred and caching, right? So if you have a separate CSS file that changes less frequently than your HTML, then, the CSS file can be cached and.

[00:15:09] **Tim:** And information hiding. I mean, that's the whole point of separation of concern is I don't have to worry about some style I've defined in the HTML page. It just does it. You, I'm hiding all that extra information in another file.

[00:15:21] **Carol:** It makes it so much easier to use.

[00:15:24] **Adam:** see, that's the thing, right? those, I, I, I still think that those mindsets are born out of an era with less capable tools, right? So, If we're, if we're talking about what I was describing where you've got like, okay, the CSS can be cached because it's in a separate file. Modern tools still generate a separate file, but it's based on like, I'm just going to use Svelte as my example.

[00:15:47] **Adam:** That's not the only way to get there, but that's what I know best. And, and, you know, a lot of things use the same sort of model. so if you've got your CSS in your JS and your templating is mixed in with your JS, so that's, that's kind of what I'm talking about, right? Like a JavaScript, modern, you know, all in one templating, or not, not templating language, but like a, application framework.

[00:16:05] **Adam:** the end result is still separate files, right? You get, you, have a server, returns basically flat HTML, says download this JavaScript file and execute it. It says download this CSS file and apply it. And those. External includes are effectively what you're talking about. So you get those same benefits of caching, and, and that sort of thing.

[00:16:25] **Adam:** But the developer experience of having them all together and you're, so I think part of what you're saying is that the, it's too much clutter, right? You've got an HTML file and it's got, you know, the 500 CSS rules that are used on this page right there. And you've got. The 500 lines of JavaScript that are affecting this page and it's a thousand lines of HTML all in one file.

[00:16:50] **Adam:** I agree that that would be garbage and I don't, I don't think anybody should write that. Um,but what I'm saying is like in, in modern tools, you know, you're writing a component and that component has five lines of CSS at the bottom and it might have 20 lines of JavaScript at the top and 20 lines of Templating language, or maybe 50 lines of templating language, and you've got modern IDEs that can say, okay, collapse the JavaScript, collapse the CSS, I only, I only care to look at the templating stuff right now, right?

[00:17:18] **Adam:** And so it's kind of giving you best of both worlds there. There's, I mean, there's other arguments to make too, like the, I think the performance of inline styles, right? So if you had like div style equals and you drop in a chunk of CSS in there, in those older Oldern? In those

[00:17:34] **Carol:** learn.

[00:17:36] **Tim:** ye olde, ye olden days.

[00:17:39] **Adam:** in those days of like, you know, IE6, IE7, whatever, that was a lot harder, I think, for the browser to, parse in a performant way and to apply those styles, so it was just a less performant way, and I think that that is no longer the case. And then the other big argument that I see For, for making this, this hot take is that I think that your code should be organized, like your teams are organized and in some companies, you know, like at a certain scale, it makes a good amount of sense to say, okay, we've got our backend team and we've got our front end team and we've got our designers and there's like three of each, right.

[00:18:19] **Adam:** Or, or something somewhere in that ballpark. but if you are, at. A smaller scale or at a much larger scale, I think in both of those cases, you're going to organize your teams more, or you're just going to organize your teams differently. You're going to have the team that works on the search engine.

[00:18:37] **Adam:** You're going to have your team that works on the product page. You're going to have your team that works on the cart. And they're going to want to follow that all the way through the stack, right? They're going to do the server side. They're going to do the front end. They're going to do the design.

[00:18:47] **Adam:** They're going to do the CSS. They're going to do the logic. And so, having it all together, I think makes a heck of a lot of sense.

[00:18:57] **Tim:** But then yet now you've tightly coupled your organizational structure with your code structure. What happens? If the code needs to change or the organization needs to change, now they're, going to break them

[00:19:10] **Adam:** that's an interesting question. I'm trying not to just dismiss it out of hand as, as

[00:19:15] **Tim:** as you are want to

[00:19:16] **Adam:** is,

[00:19:17] **Adam:** but I do think that, it's a little bit of a contrived question, like, okay, so, you know, what, like the, the product page, you know, there's just, it, it becomes too much of a big thing and so now we have to split that into a couple of different teams and I think that at that point you have like, you know, whatever makes, honestly, What I'm thinking is that whatever sort of separation that you're finding, you need to make in the component because it's too much for one team to handle, you know, whatever that logical break point is where you're going to say, okay, if A, then here's the A stuff.

[00:19:50] **Adam:** And if B, then here's the B stuff. I think you're creating separate teams for those two things. And you're creating separate kind of components in that case. And it still works. It's just, you have to find the right split. I think let's throw it the other way. Let's throw it the other way. The organization that you're saying, where you've got 10, 000 HTML files, 40 CSS files, 150, 000 JavaScript files, and every team has full access to all of those files, and you go, okay, go work on the product page.

[00:20:21] **Adam:** Like, how do I know which JavaScript files, which CSS files, which HTML files? So,

[00:20:26] **Tim:** Well, hopefully you've got a nice naming convention for your folders and stuff. Right? I mean, that was a bit of a straw man argument,

[00:20:32] **Carol:** yeah, I mean, I mean,

[00:20:33] **Adam:** don't think yours is, sir?

[00:20:36] **Tim:** but my straw man looks better. Well,

[00:20:39] **Carol:** And that's where the assumption comes into you say, like, what did you say? Like, areas of concern, right? Is that the word you

[00:20:46] **Adam:** Separations of, separation of concerns.

[00:20:48] **Carol:** separation of concern. And that's where I go back to, for me, separation of concern is like areas of the system, right? So if I'm in the JavaScript folder, then I'm going to find the folder that says, you know, product or says shopping cart.

[00:21:02] **Carol:** And I'm going to go find what's working inside that area. Not that I go to the product folder and then find all the code for it all together. Like I still would want it separated by What it's doing front end versus back end

[00:21:18] **Adam:** I, I, I still love you guys, even though you're wrong.

[00:21:22] **Tim:** that's why it's a hot take.

[00:21:23] **Adam:** That's right.

[00:21:24] **Carol:** and you're

[00:21:25] **Adam:** We've been on this one for a while. Why don't we move on?

[00:21:27] **Tim:** be interesting to hear what our, our, our listeners think.

[00:21:30] **Carol:** I'll do the next one. Is that cool?

[00:21:32] **Adam:** Yeah, absolutely.

## [00:21:33] Stack Overflow is Dying

[00:21:33] **Carol:** So I personally feel like stack overflow is dying. the amount of questions going in there just don't seem to be where they were. A year ago or before ChatGPT, and I don't know if that is because ChatGPT is now replacing that. I know it is for a lot of people I know, like they don't go look up questions immediately on StackOverflow.

[00:21:55] **Carol:** They're like, hey, let me go hit up ChatGPT and see what it returns. So I like have this feeling that ChatGPT is going to hit a point or all of them where It no longer has questions and answers to help developers keep going, because eventually if we stop putting our questions out in the public, and we stop answering them out in the public, how is the AI model going to learn if there's nothing to learn from?

[00:22:26] **Carol:** So I feel like we're going to hit this big wall at some point where people go. Oh, poo poo, I can't use ChatGPT. I have to go back to the community that supports these things and figure out what to do. And I don't know when that'll be, but I think it's coming. I think it's a coming.

[00:22:43] **Tim:** And that's one thing I've been worried, I'm thinking about that with AI is that it's going to poison its own well,

[00:22:48] **Carol:** It has

[00:22:48] **Tim:** It was, it was trained on, on Stack Overflow kind of questions, particularly for programming and to learn how to answer them. And so that's great. But now what, let's say even Stack Overflow doesn't go away, just rather than people answering the question, they just go to chat GPT and put the answer there to get the bounty points or something.

[00:23:05] **Tim:** and, and now chat. It's like the snake eating its own tail, right? It's not going to learn anything because there's no information being put in. So yeah.

[00:23:15] **Adam:** I mean, there's, there's multiple angles on this, right? So, ChatGPT is not an intelligence engine. It's a language model. It takes your question and says, this sounds like it should be a good answer. That doesn't mean it's right. and I think that, I, I think you're definitely onto something, Carol, in my opinion, right?

[00:23:31] **Adam:** That's what we're doing here is we're, we're sharing opinions and, and poo pooing on my opinions, apparently. but I think you're onto something. I think that, We're definitely, as a result of this, going to see the amount of questions asked on Stack Overflow going down. And I think in some cases that's a good thing, right?

[00:23:48] **Adam:** How many more times can people answer the question, How do you parse HTML with Regex? you know, like,

[00:23:54] **Tim:** Poorly.

[00:23:55] **Adam:** there's only so many ways you can say no. and I think that there's a lot of duplicate stuff and hopefully ChatGPT will, you know, weed out that stuff. I do, I agree with you. I hope that the extremely difficult, the more nuanced stuff continues to get asked there.

[00:24:12] **Adam:** And I think that it probably will because if ChatGPT can't solve it, then that's where people are going to go, right?

[00:24:18] **Carol:** to it.

[00:24:19] **Adam:** I think the, the danger zone is going to be the stuff that ChatGPT can figure out to answer because of the docs it's read or whatever, that isn't already covered on Stack Overflow. And that's the stuff that I think we're in danger of losing, but the docs will still be there.

[00:24:36] **Carol:** But now we have to read the docs if we don't use ChatGPT. Yeah.

[00:24:39] **Tim:** nah, assuming there's still a stack overflow. So back in October, they laid off 28 percent of their staff and they said it was due to chat GPT.

[00:24:48] **Carol:** Yeah, they also sold, I think they sold, right? The owner sold, like, six months or a year ago. Yeah.

[00:24:57] **Tim:** I didn't see.

[00:24:58] **Adam:** Wait, so you're not talking about, Jeff Hatwood. You're talking about, cause he, he sold his share a while back, many years ago. Um,

[00:25:06] **Tim:** It was 2021. Back in June.

[00:25:09] **Adam:** Who sold their share to who?

[00:25:12] **Tim:** They sold to Process, a Chinese gaming, the WeChat company.

[00:25:17] **Adam:** What? Stack Overflow, the company, was sold to

[00:25:20] **Carol:** yeah,

[00:25:21] **Tim:** Yeah, acquired by process for 1. 8 billion, according to TechCrunch back in June of

[00:25:25] **Adam:** Wow. I was not aware of this, but then I haven't been on Stack Overflow for, except for the occasional Google search result for like five years.

[00:25:36] **Tim:** Yeah.

[00:25:36] **Carol:** yeah, I still go in there.

[00:25:38] **Adam:** every now and then I'll hit a problem. I'm like, okay, well, you know, I can't figure this out. ChatGPT can't help me. So I start to like, okay.

[00:25:47] **Adam:** And this, honestly, this is the best thing that Stack Overflow ever did for me is the people there are such That I, I, I've learned to predict what sort of things are going to nitpick on my questions, which makes me write my question really well and produce a reproducible test case. Like, I try to get all of those ducks in a row so I can ask a perfect question, like, so that they can't dock me any points for, for being lazy about anything and like 99.

[00:26:17] **Adam:** 999 times out of a hundred. I find the answer myself because I've done that.

[00:26:20] **Tim:** Right.

[00:26:21] **Adam:** It's like the perfect rubber duck.

[00:26:23] **Carol:** Yeah, well, I had an issue at work and I was trying to work through it and I ended up on Stack Overflow reading what the previous developer posted, which is the same wall I'm at.

[00:26:33] **Adam:** The same, like literally the same person from, that used to have your job or whatever.

[00:26:37] **Carol:** The person that handed this project off to

[00:26:39] **Adam:** Oh,

[00:26:40] **Carol:** he couldn't figure it out. So now I'm to the point where he got stuck and I'm going, huh, guess this is a real problem.

[00:26:47] **Adam:** that stinks.

[00:26:48] **Carol:** Yeah. Oh, well.

[00:26:49] **Tim:** Yeah, so, so I, I, I think it is dying. I, I kind of agree with you. I hope, I don't know where we go from. Where's ChatGP going to learn? Cause it's not a learning engine. Like, like Adam said, it's a, it's a language model.

[00:27:03] **Carol:** Yep. And if the database isn't there for it to pull from, then. We

[00:27:06] **Carol:** may see a wall. It's going to be interesting.

[00:27:08] **Adam:** so there's a couple of angles here, right? So apparently I think if I'm not mistaken, GPT 3 is what chatGPT is based on. And that's what most of us just think of as chatGPT. There is a, I think a GPT 4 either nearly available or recently available, coming soon sort of thing. It feels like it's on the horizon.

[00:27:27] **Adam:** I, I personally haven't touched it. might be, you know, whatever the, the elites have access. but, I, I think that's supposed to be another step up and, you know, closer to actual intelligence. and then the other thing to consider too is we keep hearing about, you know, different products or different companies figuring out how to create a chat interface for their docs, right?

[00:27:52] **Adam:** So, you know, a product that you are trying to use is still going to have docs. And the important ones or the profitable ones or whatever will have, you know, a chat interface to their docs that's at least trained on them. So hopefully you'll be able to use that and you won't have to spend a week digging through the docs yourself.

[00:28:11] **Adam:** You can just ask and get a better answer. and, and honestly, I'm hoping that, sort of the next evolution past that is that you Get sort of a personal, you know, retrainable model where you can say, okay, I, I want to, I want my LL, or what do you call it?

[00:28:29] **Tim:** Large language model.

[00:28:31] **Adam:** Yeah, LLM, whatever it is, you know, I want my, AI thing, my tool here to train itself on, the Java docs overnight, right?

[00:28:39] **Adam:** And I want to come back tomorrow and I want to be able to ask it anything about whatever Java or this particular Java library or whatever. So you kind of, like, just repoint it and it, like, overnight trains itself. Now granted, you know, I, I acknowledge that we're not there in processing power yet, but

[00:28:57] **Carol:** One can

[00:28:58] **Adam:** might be the future, yeah. And I

[00:29:00] **Carol:** because that'd be amazing.

[00:29:02] **Adam:** yeah, like, I, I agree, you're, you're describing a very real problem, but I think that we can't discount that there are going to be solutions to these problems too.

[00:29:09] **Tim:** All right. Well, we done on that one. I got one.

[00:29:12] **Adam:** Yeah, go ahead.

## [00:29:14] Code Comments Are a Waste of Time

[00:29:14] **Tim:** So my hot take is I think that comments are a waste of time. Most

[00:29:18] **Adam:** The way you write them.

[00:29:20] **Tim:** code comments.

[00:29:21] **Adam:** Mm hmm. Mm

[00:29:22] **Tim:** I think that if you're, if you're writing, you know, comments in your code, usually it's just a regurgitation of what's the code is supposed to be doing. You should be writing your code so cleanly and having function names that are so extremely explicit that you know what they are and so single purpose that it's obvious that what it's doing, that really putting a explanation of what the code is doing is really just a, you know, Unnecessary.

[00:29:51] **Tim:** I, I will use like code comments for like explaining what a regex is doing, you know, because most people can't read regex. I can't, I certainly can't. Ben would need it. but, uh, or if you're using bitmask filters or things like that, explain those things that aren't apparently obvious. But otherwise, at the most, I'll put a ticket number so you can at least see what problem they're trying to solve.

[00:30:12] **Tim:** But putting a whole Dissertation of like, here's what I'm doing and here's how, how the system works. And this is what this step is doing is just a waste.

[00:30:21] **Tim:** Oh yeah, for sure. Totally agree. I guess it's not a hot take.

[00:30:24] **Adam:** I will, you know, I still write comments every now and then, but like, so the one that's coming to mind for me right now, I mentioned a while back, I wrote a feature flag rules engine, and there's not a ton of comments in there, but the big one is, I've got a method that, like, takes an object and returns what I'm calling a CRC of that.

[00:30:43] **Adam:** It's just like a, it's a deterministic numeric value that repre represents this, data that you gave it. Right? and I, I kind of just came up with my own CRC algorithm. because, so my, my use case was I was trying to say, okay, you've got these, some inputs, and you need to get a percentage number out.

[00:31:02] **Adam:** Actually, what you really need is true or false, and you use this, a number between 0 and 1, right? Some, some deterministically, but somewhat random number between 0 and 1. and so what I did, basically, was like, take that data that you do as an input, deterministically concatenate it all as one specific string, so always, you know, if you give me the same input, you're always going to get the same string.

[00:31:25] **Adam:** Then I MD5 that string, and then strip out all alpha characters, leaving only the numbers. And then just give me like the first, whatever, six digits of that number. And so that's, how I came up with that, that, you know, and then I put like zero dot before it. And so that's how I came up with, this is how we come up with the number.

[00:31:42] **Adam:** It seems relatively randomly distributed. It works. Is it? You know, mathematically correct, does it have any relation to what actually happens for CRC? I don't know, but it works, you know. And so like, I explained that in the comment. I wrote this like 15, it's funny because the, the function is like maybe six lines of code and it's got this like, I don't know, 20 line comment inside the function body at the top of it.

[00:32:06] **Adam:** It's like, this is what I'm doing. This is why. These are the steps that are being taken and why it's doing it this way. And you know, this was the whole point. And, and like, is this the right way? Probably not. Does it work? Yeah.

[00:32:22] **Tim:** Yeah. I mean, so it sounds to me like it's not readily apparent what it's doing or why.

[00:32:27] **Adam:** Yeah, it, it, like what it's doing, right? Is it, if you know what a CRC is, then it, it's pretty obvious what it's doing. But then like, if you were to look at the implementation without comments, you might go, what the F is this guy thinking? And so that's why I left that big comment there.

[00:32:43] **Tim:** I mean, I say that about you often, so

[00:32:45] **Adam:** Yeah. Yeah.

[00:32:45] **Adam:** I mean, me too. Every time I look in the mirror,

[00:32:48] **Carol:** What about the comments that are above a function or a piece of code that say, I don't know how this works. It shouldn't work, but it does. Don't change it. Like,

[00:33:00] **Tim:** that's awful. That's

[00:33:01] **Adam:** like a, a

[00:33:03] **Carol:** yeah, don't touch this. Everything will die. Just trust that. It's right in the wrong way.

[00:33:10] **Adam:** gravestone, one of those comments that's like, when you're done trying to modify this function and you have failed utterly and you return it to its original state, add one to this counter, you know, like,

[00:33:19] **Carol:** and it's sad, but those happen, right? Like there are times when you make a comment to kind of have fun at the fact that something was written poorly and everyone knows it was written poorly, but it's just not in the budget to go fix it as long as it's not fully broken. So maybe do have fun with a comment here and there. Just Don't add a ton of them.

[00:33:42] **Adam:** for sure.

## [00:33:43] Your Company Should Be Pro-Testing

[00:33:43] **Adam:** Okay. I'm going to go now. I think that a career at companies that don't value testing is basically a disability. Like, I almost like to the point where it should be federally recognized, and you should get like extra benefits for it or something.

[00:33:59] **Adam:** I don't know because like some of us, present company excluded, don't think their testing are, is important. and I

[00:34:08] **Tim:** just

[00:34:09] **Tim:** make really small changes. That's all you gotta do.

[00:34:11] **Adam:** and then you got a regression tester. Hold on. Anyway, let's not get into that. Yeah, testing is so important and, and it's such a, like, there are so many companies out there that just do not believe that to be the case.

[00:34:26] **Adam:** And it's, sometimes it makes me go like, am I the one that drank the Kool Aid? Right? Like, but it, you just, I keep coming back to it's, it is important and it is, has a ton of value. and the, the companies that are not putting value on testing are wasting their time doing manual testing, basically.

[00:34:46] **Tim:** Or doing rewrites constantly, constantly. They're like, Oh, this thing is broken and we don't know why. So let's just rewrite it.

[00:34:51] **Adam:** or they're just living with it being broken and losing, you know, money, basically, one way or another.

[00:34:57] **Adam:** and I think that, it If I could go back and do some things about my career differently, it's so hard because, you know, like, there's the whole, like, I don't, if I could go back in time and I move a water bottle six inches to the left, like, it could change the whole course of human history, right? That whole, like, anytime there's time

[00:35:13] **Adam:** travel involved, yeah.

[00:35:15] **Adam:** but at the same time, like, if I could go back and change something about my career and know that it would only have the intended effect, I think the thing that I would change is to, Look for specifically companies that valued testing when I was looking for jobs, because I feel like I've had to learn so much.

[00:35:34] **Adam:** I mean, I've, I've been programming since I was probably 18, been programming professionally since I was probably like 20, you know, like my, my internship starting in college. And then I got an offer to stay at that company when I graduated and I've been programming ever since. And. And I'm 41 now, and so, you know, 20 plus years, and I have had to, in the last 5 to 10 years, basically teach myself everything that I need to know about testing.

[00:36:07] **Adam:** Not that, not that I hadn't had any opportunities prior, you know, there have been conferences, but it like, because of the cultures that I was, you know, quote unquote, raised in as a, as a younger programmer. And the, the way that they just didn't value testing, it made, it gave me, it rubbed off on me, that attitude of like, ah, who cares?

[00:36:25] **Adam:** That's not important to me. and I did myself a disservice there. Yeah,

[00:36:32] **Tim:** That's why it's called growing up. You live and learn.

[00:36:35] **Carol:** Yeah. Working at a company where testing isn't important is very bad for developer life, just overall. Like I know we're supposed to be arguing these points or whatever, but I completely agree that, you know, living where you're constantly fighting fires because small changes cause catastrophic disasters that you had no idea about till it went into production, then trying to figure out how to undo it safely with no test. I don't miss those days.

[00:37:04] **Adam:** no, not at all.

[00:37:05] **Carol:** That aged me a lot.

[00:37:06] **Adam:** Yeah. And, you know, I have talked a lot on this show about, you know, how my company is kind of growing up and I've talked about, you know, how we had almost no tests and then now we're growing more and more tests and like the more. The more that time passes, the more we're writing new code and all, you know, maybe 80 ish percent of that new code is having, is coming with tests, along with it.

[00:37:30] **Adam:** So we've been growing up and we've been adding tests, and, there, there were some decisions made in the past that I think that just put us in a bad place where certain parts of our application are, are not worth trying to test. Like the, the, you could write tests, but they would be so slow and, so fragile.

[00:37:50] **Adam:** That they would be basically not worth having, right? If you have to wait 20 minutes for the test suite to run, to me, that's worse than having no tests because I can do the manual testing of, you know, probably 70 percent of the stuff that the automated tests would catch, in three minutes, you know, while I'm working on the feature.

[00:38:09] **Adam:** And so I think in that case, you know, having automated tests that take 20 plus minutes to run, that's just. A waste of my time.

[00:38:18] **Tim:** Excellent.

## [00:38:19] Coding in Your Spare Time is an Advantage

[00:38:19] **Carol:** So developers who don't code in their spare time will never be as proficient or as great of a developer as those who do code in their spare time.

[00:38:30] **Adam:** Yeah, this is one that I sort of like begrudgingly agree with.

[00:38:35] **Carol:** Yeah.

[00:38:36] **Adam:** you know, it's just a matter of like reps, right? Like, it's almost like saying, you know, people who, if your job was lifting weights and people who lift weights in their free time are going to be stronger than the people who don't lift weights in their free time, right?

[00:38:49] **Adam:** Like, that's just, duh, right? You're, you're exercising a muscle. but at the same time, I, it does create an unfair advantage for those of us that have the time.

[00:38:59] **Tim:** And I somewhat disagree with this. I mean, it's a job, right? It's like you do your job. You try to do it well, you get training on it, you know, to continue to get better. But I think ultimately developing is an intellectual exercise. And some of the smartest people in the world are not, aren't people who are monofocused on a thing.

[00:39:21] **Tim:** They have a very broad, knowledge base and they're able to abstract principles and ideas from other completely unrelated areas. And put it into their, their professional life. And I think that's true with, with development. It's like, sure you could. Spend all your time, free time, you know, doing some, you know, some side projects, some code project, and just your free time is, is constantly just coding.

[00:39:47] **Tim:** But I think maybe if you spent that, some of that time learning philosophy, history, art, different things, you're, it's actually won't have the immediate, I think maybe early in your career, that's true, what you're saying, Carol. But, I think as you get older and older and a little more proficient, it's not going to give you that same bump that it would early on in your career.

[00:40:10] **Tim:** As you get, where you're going to get the bump from is that breadth of knowledge. And that's, that's just my opinion.

[00:40:15] **Carol:** Yeah, I can see that. Like for me, I, I teeter kind of on this one, right? Because I know what it was like being a single mom and I didn't have free time to do anything outside of work. It was work and raise kids and hopefully you didn't fail at both of them in the same day. Like you did the best you could.

[00:40:32] **Carol:** So now that I have free time and can spend time learning another language that I'm not writing for work. It's given me the opportunity to see things slightly different so I can come at things from a different approach than if I was only focused on how do you do this in CF or how do you do this in .NET?

[00:40:51] **Carol:** Then I get to go, okay, well there's another way to do this in another language, so how can I take that into what I'm doing? But also to piggyback on what you said, Tim. I am also picking up photography because I feel like I have no creativity in me right now and all I can do is write code and try to survive and all of everything going around in the world.

[00:41:15] **Carol:** So I'm going to start doing some photography stuff to try to see if I can spark that side of my brain a little bit to see if that helps with my design side at work.

[00:41:27] **Adam:** So, I heard this great thing recently. I apologize that I can't give credit because I forget where I heard it. it really resonated with me. I love it. It's, people that work with their minds have to rest with their hands, and people that work with their hands have to rest with their minds. Right? So, what we do is knowledge work.

[00:41:43] **Adam:** We're like, in our head all day, stressing out, thinking. You know, trying to solve those problems, just mental, gymnastics. And that's why I think that, you know, it's a contributing factor to why I think that like so many, programmers love like woodworking or, you know, like,

[00:41:59] **Tim:** gardening,

[00:42:00] **Adam:** yeah,

[00:42:01] **Adam:** or like, you know, even like skiing, snowboarding, or,

[00:42:04] **Tim:** weightlifting,

[00:42:05] **Adam:** weightlifting, cooking,

[00:42:07] **Tim:** and

[00:42:07] **Adam:** all these things as hobbies

[00:42:09] **Tim:** then writing a weightlifting app,

[00:42:12] **Adam:** as you do.

[00:42:13] **Tim:** as you do.

[00:42:14] **Carol:** As Ben does.

[00:42:15] **Adam:** All right. Anybody got anything else?

## [00:42:17] Clean Code Over Design Patterns

[00:42:17] **Tim:** I got one. so I think writing clean code is more important than design patterns.

[00:42:22] **Carol:** Elaborate.

[00:42:23] **Tim:** so design patterns, I mean, I think they're fine, but there's so, I think there's so many design patterns and people can really only kind of get good at a handful of them, right? And then even then they're probably not going to implement them. The most, you know, clean way. and then sometimes you just have a design pattern you like, and you try to make everything fit that design pattern.

[00:42:44] **Tim:** And it may or may not be the best. and then sometimes, particularly have a team where everyone has different opinions on how the design pattern is supposed to be implemented. You get into these bike shedding arguments of, you know. As if it's almost a religious argument about, you know, well, the design should be worked this way.

[00:43:02] **Tim:** That's, you're not following the proper principles, but ultimately is it clean and does it work and does it make sense? I mean, I think that is more important than worrying about, you know, if you're following the design pattern the best way.

[00:43:15] **Adam:** I think that that's a good example of the thing we've talked about in the past about like disagree and commit, right? Like we could spend all day arguing over should we do functional programming or classes, but like at the end of the day, you just kind of have to pick one and the team rallies around it and does the thing.

[00:43:31] **Carol:** Agree. There is something to be said, though, about design patterns when you're talking about porting over a project to another language. So, when everything's, everything's written in a way that it followed the design pattern, then it's so much easier to take that and move it than it is to try to figure out which way is.

[00:43:50] **Carol:** Written differently from the previous process you just change.

[00:43:54] **Adam:** It's an

## [00:43:55] XML, UML, JSON Suck

[00:43:55] **Tim:** When one, one, that's not a hot take, no one should disagree, XML sucks. And, and UML is a waste of time.

[00:44:04] **Adam:** Ooh. You know what, I'll throw this one out there, I'll pile on that. JSON sucks.

[00:44:09] **Tim:** Really?

[00:44:09] **Adam:** only because, there are better things like JSON5, which allows you to have, like, comments. and,

[00:44:16] **Tim:** So it's just, it's just not your grandfather's JSON.

[00:44:18] **Adam:** yes.

[00:44:19] **Carol:** people that say Jason suck and people that say JSON are right. Yeah.

[00:44:25] **Adam:** I flip flop, I go back and forth, whatever sounds right as my mouth bits are flapping. That's what comes out. the, so, yeah, basically json5 or json5. is, like, everything that you hate about json or json, json. How about we go with that? Json.

[00:44:42] **Carol:** Jason.

[00:44:43] **Adam:** Everything that you hate about it is fixed, right? You don't have to quote the key names in objects.

[00:44:47] **Adam:** You can have comments. Right? You can have like line breaks and stuff. it's, it's, just better. But the problem is we'll never get it. Because JSON, is not just for the JavaScript language. It has become this lingua franca of the web.

[00:45:04] **Adam:** Every programming language ever would have to be updated. Not ever, right?

[00:45:08] **Adam:** Nobody's, God, I hope, help, God help you if you are consuming JSON in assembly. But. Like, you know, basically every modern language would have to be, updated to support this because the, the biggest selling point of JSON is that, you can just basically do an eval on it. That's not a safe way to parse it, but it is a way to parse it.

[00:45:33] **Adam:** You just eval it and you get an object back and there you go. and that's not going to be the case with comments and unquoted, key names and all the other. Improvements. yeah, it's still better. It's a, it's a better that we'll never have, probably.

## [00:45:48] Creating a Software Product is Harder Than Most Other Things

[00:45:48] **Adam:** All right, I got one. I think it is harder to make a great software product than it is to do just about anything Like, non technical, right?

[00:45:59] **Adam:** I'm talking like, make a meal, or build a piece of furniture, and I'm not talking like, put together a kit you got from Ikea in a flat pack box, I'm talking about like, make a piece of furniture, or other, you know,

[00:46:11] **Tim:** from nothing to end product, right?

[00:46:14] **Adam:** I'm talking, I'm comparing, you know, building a very nice to do app, and I'm comparing that to like, cut down a tree, slice it up into boards, dry the boards properly, cut up those boards and make pieces, turn those pieces into a piece of furniture, finish the piece of furniture so that it's usable.

[00:46:33] **Adam:** Those are the two things that I'm contrasting, and I still think, even though probably 99 percent of the people that just heard that have no idea what half of the things I just described are, you, I still think writing software and doing it well is harder.

[00:46:48] **Carol:** So I think that with some of the improvements that we're seeing in technology, like the chat GPDs and the automation of creating code, it is making it easier for people to start projects and then grow them. Than it ever has been in the past. So I think that while yes, making a great product doesn't sound like, and yes, while making a great product does sound hard, if we're talking about just spinning up a website that I can go sell my new shoes on, that's not that difficult anymore, and it's so much simpler than it has been in the past.

[00:47:27] **Adam:** Yeah, well, and it's true. You're right. And I'm taught, it's like, well, so that's the thing. Okay. What you're talking about It could potentially be reduced to the point, and I'm talking reduced like mathematics, right, where you're reducing fractions or whatever. You can reduce that problem space that you're discussing.

[00:47:42] **Adam:** I need, I'm trying to sell shoes, so I need a website for it. In that case, you don't have to make a website. You just have to find a tool like Shopify or whatever to, to do it. And, and what I'm saying is building Shopify,

[00:47:56] **Adam:** right, to, to

[00:47:57] **Carol:** building the great product. Yes. Yeah. I agree. I agree with you there. If you, if you emphasize great product,

[00:48:04] **Tim:** What made you think about how many great products still wind up having some major zero day bug or some other thing that. You know, they obviously had a team of very smart people and they still didn't do it completely right. Right. It's, it's always, it's always a continuing work in progress. I read, I forget where it was.

[00:48:23] **Tim:** I think it was on Quora. So

[00:48:25] **Adam:** read that?

[00:48:26] **Tim:** I do, the question was why is it that, open source, like open source photo editors, like, like GIMP is so bad compared to how good Adobe Photoshop is. And they, they're, I don't know if their reasoning is right, but one of the answers was that because GIMP is written by developers, right?

[00:48:48] **Tim:** So it's written by developers that are trying to make some, make a, a Photoshop type app, and they're really good at the basic stuff, but all the, all the, all the other more artistic things like the getting colors, right. And, and pan print out all the other stuff. They're terrible at it. Photoshop is actually written by developers, but it's a developer team.

[00:49:08] **Tim:** That's all. Creative people that are, actually have used the traditional tools in the past, and that's why they're so much better. I don't know if that's true. I think maybe it's because Adobe's, you know, billion, multi billion dollar company, their, their counterargument was that, well, Wireshark is like the best, network, you know, analyzing thing out there.

[00:49:27] **Tim:** That's because it's developers writing a thing that's sort of useful for development. But then again, I think wire analyzing is probably a whole lot easier than,

[00:49:35] **Tim:** than Photoshop.

[00:49:37] **Carol:** And see, there's something to be said to you about. Doing, like a design first approach, right? So we take our UI team and we go meet with our customers and we say, how are you going to use the system? What do you need it to do? And then from understanding how they plan on using it, then we develop backwards from that.

[00:49:56] **Carol:** Where I think GIMP was created in the, let's just start with what people do with pictures and make it do that. And there's some expectation that whoever's using that tool. Has a technical background or is somewhat technical because it doesn't play well. It's not user friendly at all. Like I've messed with it.

[00:50:15] **Carol:** And I'm like, I think I'm just going to pay my 30 and get Photoshop and be done with it. But there is something to be said about the people who have the opportunity to do design first approach for development. And I'm seeing that now with the projects I'm working on and it makes things so much better.

[00:50:31] **Adam:** Yeah. I think, I wonder if there's like a, an ROI element to this, like the, the way that it is right now where it's less usable, it's less pretty, it's good enough for, for some people, right? Like

[00:50:46] **Tim:** for free.

[00:50:47] **Adam:** for free, right. And, and sure they would get higher adoption. Maybe even like more, you know, donations, support, Patreon, whatever, by investing the time and the effort into better design for the interface, better organization of the tools and the, you know, functionality.

[00:51:07] **Adam:** But, you know, just like we say with code, right? Like good enough is good enough. maybe they're kind of being a little more utilitarian about it.

[00:51:16] **Carol:** Maybe.

[00:51:16] **Adam:** and the other side of that coin for me in my head, maybe the two are unrelated, but in my head, the other side of that coin is the people that have the skills to do that are spending their time getting paid to do that.

[00:51:28] **Adam:** Right? To, to design it well and to organize it well. And then they, they come home from their job at Adobe making Photoshop and they're like, I do not want to look at another interface for the next 16 hours before I go back to work. Leave me alone. And, and I'm gonna sit here and play my video games and sculpt things out of clay or whatever.

[00:51:49] **Adam:** and then, then tomorrow I'll go back and get paid for it again. Alright.

[00:51:54] **Tim:** Well, those, those are some hot takes

[00:51:55] **Carol:** Yeah.

[00:51:56] **Carol:** Yeah.

[00:51:57] **Adam:** Some, some more controversial than others.

[00:52:00] **Carol:** No,

[00:52:01] **Tim:** how you pronounce Jason.

[00:52:02] **Carol:** Yeah, Jason, so we need to have Ben do a recap on his views of all of them.

[00:52:09] **Adam:** can do that like when, next time he's on, we'll have him do that on the after show.

[00:52:12] **Carol:** yeah, so we should do it. It'd be good.

[00:52:15] **Adam:** Well there you go, that'll, that wraps it up nicely, so if you're wondering what the after show is Listen to the things that I'm about to say.

## [00:52:21] Patreon

[00:52:21] **Adam:** So this episode of Working Code is brought to you by Olden Times, which is when Tim started coding, and listeners like you.

[00:52:28] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more content like this out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:52:42] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:52:45] Thanks For Listening!

[00:52:45] **Adam:** The after show that I mentioned is basically We're going to wrap this up, say goodnight to you guys. You'll hear the outro play. And then for those of you that, support us on Patreon, you'll get to keep listening and, I have no idea what we're going to be talking about.

[00:53:00] **Tim:** the notes document still says the stuff from last week. I don't, unless we're talking about barbershops again. Ben, Ben's not here to rant on Barbershop. So I guess we'll have to come up with something

[00:53:09] **Adam:** yeah, anyway. so we just rant, we talk about whatever. Sometimes it's related to the show. Sometimes it's barbershops. So, you know, you get what you get. But if you'd like to get that, check that out, then you can go to patreon.com/workingcodepod. Yeah, support us for as little as, I believe it's 4 a month, even lower if you pay for a year at a time, that's like less than a dollar a week.

[00:53:31] **Adam:** and, become a supporter of the show. We'd really appreciate it. And so that's going to do it for us this week. We'll catch you next week. And until then,

[00:53:37] **Tim:** Remember, your heart matters unless you pronounce JavaScript notation object as Jason,

[00:53:42] **Adam:** Jason,

[00:53:43] **Tim:** Jason.

[00:53:44] **Adam:** I don't, I say je sens.

[00:53:47] **Tim:** français? Oh,
