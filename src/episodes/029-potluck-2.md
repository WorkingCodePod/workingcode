---
title: "029: Potluck #2"
description: "This week on the podcast, the crew discusses various topics, with no advance notice of what they will be!"
date: 2021-06-30
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/029-potluck-2/id1544142288?i=1000527349943"></iframe>

This week on the podcast, the crew discusses various topics: What would you do as an engineer if you knew you couldn't get fired? What conscious and unconscious fears might be holding you back from executing on tasks that you know are important? What does a healthy work-life balance look like after Covid-19? Are you one of the estimated 40% of employees that are considering quitting their job now that they've had the opportunity to work from home? In an increasingly remote-friendly culture, how are you taking care of your employees and making them feel wanted? How do you stays focused at work when you're feeling stuck? What strategies for success can you employ when you hit a wall and can't seem to motivate?

All that _and more_ on this week's show!

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/029-potluck-2.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** And then they articulate, here's why we're doing it. And here's the customer value and here's the need it's going to solve. I'd be like, Oh, all right. Yeah, I totally didn't think about it that way. Or I didn't see what you were saying before and now I'm invested and now I'm, and now I'm excited to do it.

[00:00:15] **Tim:** Kind of like I was telling you to do with other people earlier in the show.

[00:00:20] **Ben:** See, it's all big circle. Communication is important. I don't know, something, something, yada, yada, yada.

[00:00:42] **Carol:** All right. So, uh, today is episode number 29 for us and it's. It's June the 30th and the topic today is going to be our second potluck. Um, I'm filling in for Adam as he is out on vacation with the family, so we'll see how this goes. Should be interesting. And I guess we'll get started with some triumphs and failures.

[00:01:01] **Carol:** So, actually, I'm on the list to go first this week, so let's just keep going with me. Um, so my, uh, triumph or failure this week is going to be a big giant failure. If you're in our Discord with our Patreons, you probably saw some of the messages on the day I was supposed to be coding, but instead had done the laundry, did the dishes, and found baby bird eggs in my backyard.

[00:01:24] **Carol:** So, by 11, I finally had the urge to write some code, but... I've had a couple days like that this week where I just, I can't stay on, I can't stay on track. I can't focus. I just, I don't know if it's because I'm struggling with the task that I'm on, and I know I don't know the best solution for it or what's going on, but everything else just seems way more important than the important work I have to do.

[00:01:45] **Carol:** So, gotta get back on that and figure it out.

[00:01:49] **Tim:** Let me guess. Is that going to be your potluck today? You know,

[00:01:51] **Carol:** I might bring that to the table. Seems like a good one.

[00:01:55] **Tim:** Sounds like coleslaw

[00:01:56] **Carol:** with raisins in it. Terrible. All right. What about you, Ben? Let's head it over to

[00:02:01] **Ben:** you. I'm going to go with a success. I've been working with our security team to rotate the certificates that we use for single sign on, um, which turned out to be fairly tricky.

[00:02:14] **Ben:** Uh, essentially the way certificates work with the single sign on is when we send users from our application to their identity provider, we have to sign the requests, and then when they send the users back from the identity provider to our application, we have to verify that their request was signed properly.

[00:02:31] **Ben:** So we have to have this agreement between public and private keys on both sides. And, uh, rotating keys in general is just fairly challenging, and... Single sign on makes that especially challenging because there's multiple parties involved and lots of different companies have different identity providers that will automatically pick up certificates or not automatically pick up new certificates.

[00:02:53] **Ben:** So there's, we ended up, uh, coming on this solution where we use feature flags. To change the way that we sign the outbound requests, but then we use feature flags. I dabble,

[00:03:07] **Ben:** but it ended up actually, it was like, there was a lot of hand wringing and a lot of how the heck are we going to do this? Um, and then on the security side, they came up with a nice, really clean plan. And then it took us like. A day and a half to implement it. And it ended up being a lot less of a nightmare than I think it could have been.

[00:03:23] **Ben:** So, uh, I was pretty pleased with it overall. Feeling pretty, pretty

[00:03:27] **Carol:** keen on it. So your security team that helped come up with the idea, they're not engineers, right? Or are they some engineer folks as well? Or what kind of team is

[00:03:35] **Ben:** that? Yeah, they're a mixture of engineers that, uh, you know, some of them have more application security where they're more low level in the code and some of them.

[00:03:45] **Ben:** No more about networking security and overall things like, uh, web application firewalls. And actually one of the people on our team is David Epler, who is well known in the ColdFusion world. Yeah. So it took me like two years to get him to come to the company. And I think he just had his So, uh, it's been great having him on board.

[00:04:09] **Tim:** I tried so hard to get him hired as well. I couldn't convince them that we really needed him, but we did. He's worth it.

[00:04:17] **Ben:** Yeah, for sure. It's been absolutely great.

[00:04:20] **Tim:** Talk about certificates. I hate the way ColdFusion deals with, with SSL certificates. You got to go to, you know, go to the command line and manually put it in.

[00:04:30] **Tim:** Sometimes it just works. And other times you got to jump through hoops to get it, whereas Lucy, Lucy just has a place in their, their admin. You can just put the URL and it automatically does it for you. I don't, Adobe needs to

[00:04:41] **Ben:** get on that. And, and in Lucy, there's actually a function that you can give it a URL and it will pull down the certificates and install them, which I assume is what the admin is doing under the hood.

[00:04:50] **Ben:** That's nice. But yeah, I can't tell you how many times this is, I mean, this sounds terrible. How many times I've gone to make a secure request through ColdFusion's CFHTTP tag or HTTP component, and I get a connection failure or something to that effect because it doesn't have the right certificates installed.

[00:05:08] **Ben:** And then you start to think to yourself, uh, does this request really need to be SSL? Which, you know, earmuffs. No one on the security team should hear me say that. Um, uh, what about you, Tim? We'll skip over Adam since he's on vacation. Go to Tim.

[00:05:23] **Tim:** I'm going to call it a triumph. It's travel time. I finally get to, I mean, it's been a couple of years since I've gone anywhere for work.

[00:05:29] **Tim:** And so we're, we're doing a mid year strategy session and heading down to Florida, right in a big house, all hanging out and. for three days. So it's just, it's going to be weird. It's going to be just so weird being on a plane with a bunch of people. I don't know how to feel about this.

[00:05:44] **Carol:** I will say my first fly out was, um, October right after COVID 2020.

[00:05:51] **Carol:** And walking through the airport with all the people, it was kind of panicky and anxiety. I didn't realize how much I had adjusted to not being in close contact with people that I really didn't like it. I was like, there are way too many humans here. I am not a fan of this. It, it was a little like. I had way more anxiety than I thought I was going to have on that first

[00:06:11] flight.

[00:06:12] **Tim:** Yeah. It's weird. I hired a new yard guy and he shook my hand and I'm like, this is the first hand I've shook in a year and a half. This feels really wrong. I felt dirt. I went inside and washed my hand afterward. I'm like, am I becoming a germaphobe? What's happening

[00:06:29] **Ben:** here? Well, that's my big fear is that I've been so on guard about catching coronavirus that I'm going to let my guard down now, and I'm just going to get regular colds and flus like nonstop.

[00:06:40] **Ben:** Yeah. So I feel like I want to keep a lot of the... Enhanced hygiene going. Uh, just cause I'm, I really actually enjoyed the, I didn't get sick part of the last

[00:06:49] **Tim:** year and a half. Yeah. And none of us had to have a colds or flus or anything. We've all been perfectly healthy. But

[00:06:58] **Carol:** I also have not stopped having contact with people.

[00:07:00] **Carol:** So I brought it on myself. I'm sure to some extent. Yeah. So I'm excited to finally get to travel. Have fun. Enjoy it. Come back and tell us how the flight was. Cause I'm curious to see how you handle it. It's my first

[00:07:12] **Tim:** time flying Frontier, we'll see. Oh,

[00:07:14] **Carol:** just kidding. No,

[00:07:16] **Tim:** oh, yeah, I know, right? No, a friend of mine, she's, she's in our, um, role play group.

[00:07:21] **Tim:** We play Pathfinder D&amp; D and, and she's a, uh, a flight attendant for Frontier. And she told me, she says, well, Good luck. Cause uh, right when COVID hit, Frontier was in the process of changing over caterers. So they had canceled their contract with the old, they didn't renew their contract with the old caterer.

[00:07:36] **Tim:** So they have no, she says, there's no food service. You can have water for 4. That's it. So I'm like, well, I guess I'm buying food at the time. I mean, it's an hour flight between Atlanta and Orlando. It's not that long, but unless there's a storm and it's... So, yeah. So, I'd be picking up some food in the terminal, take it was, they

[00:07:55] **Carol:** weren't doing food, food. They were only doing, here's your little baggie with a tiny bottle of water, some goldfish crackers and something else. Like they, it was kind bars. They don't even have like the cookies anymore. They have like a little tiny kind bar. I'm like. Yeah. Who wants this? I pay for this flight just for the cookies.

[00:08:15] **Ben:** I was listening to an episode of a show on N P R called How I Built This. Oh, I love that one. And oh, it's a great show. And they interviewed the guy who founded JetBlue and. I'm always fascinated by people who break into an industry that already feels saturated, like the energy drink market or the potato chip market.

[00:08:35] **Ben:** And so the guy who founded JetBlue, and I hope I don't get the details here wrong, he was supposed to be the guy who was going to take over Southwest Airlines. And then they fired him cause he was driving everybody crazy. Apparently he has

[00:08:49] **Ben:** like really hectic ADHD and like condense. Yeah. Yeah. Condense is like a three year plan into six months. So they fired him. Then after his non compete wore off, he started JetBlue. And then I, I can't remember if he was asked to leave JetBlue or if he left of his own volition. Then he moved down to South America to start a new airline, I think in Brazil.

[00:09:10] **Ben:** And now he's moving back up to the US and he's going to start a new airline in the Southwest. And I just, it blows my mind that someone looks at the airline industry and is like, Oh, why don't I start three or four different airlines?

[00:09:23] **Tim:** No problem. Crazy. And they compete with your old ones.

[00:09:26] **Carol:** Well, at least you kind of know the inside a little bit to figure out kind of how to compete with them.

[00:09:32] **Carol:** All right. Well, let's get going into today's topic. Um, again, you know, we're talking about a potluck. So with the first one, I think we did pretty good. We just all brought our different topics to the table and treated it like a potluck dinner and, you know, just discussed it all. So, uh, anyone want to go first on what they brought?

[00:09:50] **Carol:** I'll go first. Cool. What you got?

[00:09:52] **Ben:** I've been thinking lately. So I had a, uh, a guy on my team who... Has not moved entirely to another team, but I started to focus more on a, on a different team and it's going to still spend 20% of his time focusing on our team's work. And as excited as I am to see him move to this other team and blossom.

[00:10:12] **Ben:** And I feel like he's really getting his feet wet and grabbing the bull by the horns and other such cliches. I'm, I'm a little bit sad. That I think some of that potential was not unleashed while he was on my team. And when I reflect on it, I think the issue is, is because my team has been sort of constrained in many ways on what we're allowed to work on.

[00:10:38] **Ben:** And that constraint, I always feel like doesn't apply to me as much. Because I'm a co founder of the company. So I feel like in a, in a big way, my superpower is that I'm probably won't get fired. And I embrace that and I lean into it and I leverage that confidence to do a bunch of other things that I think other people on my team don't necessarily have the confidence to do, which, which makes me think about.

[00:11:04] **Ben:** The fear of getting fired in general and what kind of a cap that puts on people's enthusiasm and sort of autonomous drive. And I went to not, not the current CTO, but I went to the former CTO one time and I said, Hey, wouldn't it be interesting if we created some sort of a good Samaritan law at the company and we put it in writing that no developer could ever be fired.

[00:11:29] **Ben:** Based on an action in which they thought they were putting the client's interest at heart. And like, what would that allow people to do? And he said, no, we're not going to do that. He said, our culture is already very open to people doing stuff. There's no need to put anything like that in writing. I feel like there is.

[00:11:46] **Ben:** I feel like a lot of people probably are afraid to get fired. If they step out of the bounds a little bit too much. And I just wonder what a culture would be like if it was, you know, like other companies do this, like Zappos, I think has a very customer centric approach and, um, Whole Foods, I think is famous for their, Any person not working on the floor can do anything for a customer kind of a thing.

[00:12:11] **Ben:** And I just, um, I wish that the tech industry was a little bit more

[00:12:15] **Carol:** like that also. That we had that kind of like motivation behind what we're doing and less fear. Yeah. I can see it. It's just

[00:12:22] **Tim:** interesting, but I can see why they would say no. I mean, it's hard to litigate viewpoint,

[00:12:26] **Carol:** right? What you think is best for the customer might not be best for the customer.

[00:12:30] **Carol:** And you do need to have those conversations that say, look, here's where I want to go and let's all make a decision on it. Don't just go, you know, Lone Ranger on it and go do it without having any real knowledge of what the impact

[00:12:44] is.

[00:12:44] **Tim:** Let me ask you though, Ben, I mean, it's interesting you bring up the fear of being fired.

[00:12:48] **Tim:** I can't say I've ever had that fear. I mean, and I've done some egre not like egregious, I've done some egregious things. I've done some really bonehead mistakes that cost money and things like that. And I've never once felt fear of being fired. And I'm just wondering, is that, do a lot of people operate with that kind of fear?

[00:13:08] **Tim:** I

[00:13:08] **Ben:** don't know. And to me, maybe I focus in on that because I, that is a fear that I'm very acutely aware that I don't

[00:13:16] **Carol:** have. Right. And see, I go at it. Kind of the opposite of fearing about being fired. I go, well, I'm going to do it. What's the worst that's going to happen? They're going to fire me. And I keep moving forward.

[00:13:29] **Carol:** I'm like, you know what? If I get fired for doing something that I feel is the right thing to do, I'm okay with that. I would, I would feel justified in the action. I took enough that if consequences arose that it would be okay with me. But I'm sure not everyone operates that way.

[00:13:46] **Tim:** I, I think, I'm sure there's a segment of people who do fear getting fired, right?

[00:13:50] **Tim:** That, you know, are being punished. But I, I think my, my attitude is that I think a lot of people more are unclear of where their area of influence begins and ends, right? They're not sure. They're like, This is a great idea. I think this should be done, but I don't really know if I'm the one who's allowed to do it or if I do this, you know, will someone else say, well, you shouldn't do that because that's so and so's job, you know, I think people don't really fully understand the scope of their, of their abilities and powers.

[00:14:20] **Tim:** And, you know, you being a co founder, you know, you don't have that it. You don't feel bound by that. You're like, well, I'm the co founder of the company and you know, I, if it's, I think it's a good idea. I know, I know the company well enough that it probably is. I'm sort of the same way. I'm not a co founder, but I'm super early.

[00:14:35] **Tim:** You're early in, yeah. 20 years in a company that's 22 years old, you know.

[00:14:41] **Ben:** Yeah. Yeah. I think you do get some sway. Yeah. You get some,

[00:14:44] **Tim:** you get some sway. You've been around, you've done everything, you know, you know, you know where all the bodies are buried. So it's, yeah, I think that that's maybe where people struggle is.

[00:14:53] **Tim:** Helping them understand, is it okay for you to even think about doing this?

[00:14:57] **Ben:** Yeah. And I, and I think ways in which this is, let's call it symptomatic for me. And, and maybe this is me projecting onto other people is I will occasionally go to another team and say, Hey, I need X, Y, Z done. And let's say that as an engineer, I can look at that task.

[00:15:15] **Ben:** And in my mind, I know that's. A 15 minute task. Someone should be able to just knock it out. And I get the response that, yeah, that's on the roadmap for Q3 of 2022. And I feel like, no, maybe you should just stop and do it right now. And I don't mean like not to be a jerk, but like I, I project my enthusiasm for wanting to help people and like wanting to.

[00:15:38] **Ben:** Unblock people. And when I don't see that enthusiasm mirrored in other people, I always take it as a, this person is afraid to maybe step out of line and reprioritize their day based on what they might perceive as important and to me, and again, maybe this is totally off base, but I feel like there's a deep rooted, like maybe not even conscious, but like, you know, scraping the bottom of the barrel here in your emotional gut that people don't want to.

[00:16:08] **Ben:** Anything outside of what's on the roadmap, what their product manager tells them to do, what's already been assigned to them on their JIRA board. And there's a fear there that I can't, I can't make, you know, an audible call at the line of scrimmage. I don't know if that's a sports metaphor that makes any sense.

[00:16:24] **Ben:** Yeah. I don't know. Yeah. Nailed it. Sports ball.

[00:16:30] **Ben:** So I don't know. I, it's, I just wonder. I wonder how many people are constrained in the way they view their, their day to day work.

[00:16:38] **Carol:** But it may not be the, the fear of getting fired, though. Like, you had those people you went to school with who did exactly everything they were told. They never broke a rule.

[00:16:47] **Carol:** They followed the lines that were drawn for them, and they never strayed from that. I don't think that's a bad way to be. Like, I think that's an okay. If that's how you mentally function, and that's how you do, that's great. But like you said, that's not you. You're like, Oh, I'm going to sway this way and get this other process handled while getting everything else accomplished.

[00:17:07] **Carol:** And that's kind of how I think probably all four of us are on this show that, you know, we typically just get what needs to be done, done. And let the chips lay where they fall kind of thing.

[00:17:18] **Tim:** I agree. And maybe, you know, sometimes Ben, it's like, if they, you're like, Oh, this is just a 15 minute change. And we all know that 15 minute changes.

[00:17:26] **Tim:** It's never

[00:17:27] **Carol:** been. Why did you say 15 minutes? You know, that doesn't exist.

[00:17:30] **Tim:** I told a customer the other day, she's like, wouldn't that just take, you know, just a couple hours? I'm like, nothing of value ever takes a couple hours.

[00:17:38] **Carol:** I have to open the code, read the code, write it, commit it, push it, tell you about it.

[00:17:44] **Tim:** Test it. So, but I think, you know, maybe they don't see the value of it. You see it clearly, right? You see the value of it. And they see it as just another thing that's in their queue, and that they don't necessarily see the value of it as like you do. So I don't know, maybe being able to explain, you know, Here's what I need, but here's why it's of value.

[00:18:06] **Tim:** And here's, you know, what it means to not just us as a team and a company, but also to the customer, you know, and you know, maybe you can shift the, take, take a little time out and do it. So I think a lot of times communicating the importance of something is harder than explaining what to do.

[00:18:22] **Ben:** Yeah, that's true.

[00:18:23] **Ben:** And, and, and to be fair. You know, a company has loads of different, uh, well, let's say loads of different priorities. Maybe that's a bad sign, but competing concerns, you know, they have at the, at the high levels of the organization, they have such a big picture, long term outlook. And I can see basically as far as I can throw.

[00:18:42] **Ben:** And so my perception of what's important. is maybe different, but I think in some ways that's a value add because it allows me to maybe not be clouded by long term judgment. If that's the, if I don't know if that makes any sense, but like, because I don't have to worry about the roadmap, quote unquote, I'm able to be, I think a little bit more agile and a little bit more dynamic in the things that I work on.

[00:19:05] **Tim:** You're, you're dealing at a tactical level, whereas other people might be more the higher strategic level, right?

[00:19:11] **Ben:** And what, and what grinds my gears is sometimes we'll be in a meeting talking about whether or not we should prioritize something and you'll have five or six people in this meeting for an hour.

[00:19:23] **Ben:** So that's, you know, five, six person hours. To decide whether or not we should have prioritized the thing that would have taken someone half an hour to do. Should have just gotten done. That's awful. This

[00:19:33] **Carol:** is terrible. Yeah, that one's terrible. I can't stand those.

[00:19:36] **Ben:** So anyway, that's me.

[00:19:37] **Tim:** So, so I'll go next because it kind of ties in.

[00:19:39] **Tim:** You, you're talking about people's fear of, of getting fired, but I, I'd like to talk about. So. With everyone going back to work, you know, some of them going back to physical jobs and with the, you know, we're in mid 2021. There's been several articles written. I was looking at one on Yahoo News, but the title of the article is The Great Resignation.

[00:20:02] **Tim:** Upwards of 40% of workers are thinking about quitting their jobs. A lot

[00:20:07] **Carol:** are. Yeah.

[00:20:08] **Tim:** And, and I do see this happening. We, we, you know, there's, there's at our company, there's been a lot of churn. Um, people are, I think having stayed at home, a lot of people, particularly in programming, and some of them already were staying from home, but some of them for the first time worked from home realized that maybe their work life balance sucked prior, or they just realized.

[00:20:30] **Tim:** You know what? I don't feel personally connected to these people anymore. And I realized maybe what I was working on really isn't exciting to me. And so you see this huge number of people that are, that are changing jobs. And I think as someone who, you know, employs people, you know, hires people and interviews people, it scares me because I, you know, it's like the idea of people on your team leaving is always scary.

[00:20:53] **Tim:** You don't know how to deal with that. But I do ultimately think it's a good thing. I think, I think, you know, people moving to different areas and, and insisting on maybe working remotely. I, I read, uh, another, actually this was a tweet, someone, someone mentioned at their company that management said that everyone had to come back from working at home into the office and 10% of the company quit immediately.

[00:21:18] **Tim:** So I think, I think companies really need to be careful with how they transition back and give people, and that's what we're trying to do. We're leaving the option open because, uh, right now it's easier than ever to leave your job and go somewhere else because. People are looking and people are hiring.

[00:21:35] **Tim:** People are begging to hire. Well,

[00:21:37] **Ben:** I've worked remotely for the past like eight years. So for me, I can't imagine going back to an office, but I know Tim and Carol, I think both of you are, were thrust into remote work because of the pandemic. Right. I mean, how, how are you two looking at the. Potentiality of going back to the office or like, how do you, how do you feel about it?

[00:21:58] **Ben:** So

[00:21:58] **Carol:** I actually will not be going back to the office when I switch jobs actually right before that I broke my legs So I was working from home when I was working with Tim still But I was hired at Clear Capital as a full time remote engineer, so I won't be going back. However I do miss the interaction with people.

[00:22:16] **Carol:** I miss, um, just like team lunches. I miss the just walking. Soupy Friday. Yeah, those little, those little things. I miss that. And I feel like I work better with the team who I do have those close connections with. I mean, it's not like, since it's not my family connection and I shouldn't compare the two, but I do feel that when I'm working on projects with people, just to have the, that little kind of personal connection with someone does help me.

[00:22:56] **Tim:** Like I said, It's yeah. Any of the, any of the sounds that I heard are because of the tacit minds that you

[00:23:05] **Tim:** talk about. That's for sure. They were thinking, you know, when things get back to normal, what are you thinking? And, um, my response was, well, none of my direct reports are even in the state, right? So Florida, Massachusetts, Arizona, uh, and then I have a team in India. So it was like, no one, no one's even in.

[00:23:21] **Tim:** The same town as me. So I'm like, there's no point now. A lot of management are in the same town me. So if there's me, you know, I won't have an office anymore. It's just fine. I won't have a dad, but you know, I'll go in for meetings and customer meetings and things like that in person if need be. But yeah, I don't, I don't see any need to do that.

[00:23:39] **Tim:** I've. And the

[00:23:43] **Carol:** good thing with Silvervine is they had, um, added like this little collaboration room. Like there's two of them. One has a big table in it. The other one has a couch and some chairs and you know, you can put people on video conference if you want. But so when Tim does have to go into the office, he doesn't need a desk to sit at.

[00:24:00] **Carol:** He's literally going to be in one of the collaboration rooms working. So, I mean, it gives you that kind of low key, but the, the feel of getting stuff done, I guess it's just comfortable. But, um, with the going back to the office, the people, you know, quitting and resigning and changing jobs to me, I feel like if you have skilled people as a company, you should do whatever it takes to keep them.

[00:24:25] **Carol:** If they are getting the job done, you shouldn't care about their location any more than you care about their gender or, you know, where they're from. You should just see it as skilled talent and be grateful that you have that and keep them on board. So if it means letting them work a third shift or split shift or working from home, whatever it takes, work with them because You're not going to find good people all the time.

[00:24:49] **Carol:** You're going to get people sitting in the office who took the job because they're in the area. That doesn't mean they're good. It's just because they're local and they match some skillset that you said you had to have. And that doesn't get you talent every time. Except for you. I

[00:25:04] **Ben:** am special. Well, and it's funny too, because Tim talks about having people at the office.

[00:25:11] **Ben:** That he slacks with in the office. And when Envision started, that was one of the things that, uh, there was always a point of contention between the company, which was remote from day one and the board of directors who kept saying, all right, remote is fun at the beginning, but eventually you'll want to have satellite offices, you know, where people can congregate.

[00:25:31] **Ben:** And, and we kept bringing up this idea that if you're in an office, the person on the floor above you, it's basically like being remote because you're not going to go to the next floor to talk to them. You're going to send them a message. You're going to jump on a video call like they might as well be in a different state.

[00:25:46] **Ben:** And

[00:25:47] **Carol:** the time wasted, like it takes me less time to hit. To like just start, hangout in Slack and start like a Google Hangout with my team than it does to walk up that flight of stairs, get everyone to the same point, and move 'em around and be like, okay, let's all go right now. I literally hit two buttons.

[00:26:06] **Carol:** Mm-hmm. and it's like, Hey, what's going on? Yeah, we're here. Let's talk.

[00:26:09] **Tim:** And also, what's crazy, so we had a beginning of the year, we had a, a strategy session and I was the, they all went and rented a house and I, you know, I told 'em I wasn't going to, you know, I was gonna maintain. Proper quarantine protocols.

[00:26:23] **Tim:** And so they all rented a, a place up the mountains and I was the only one remote. So it, that was frustrating, like mm-hmm. Trying to be on a zoom call when everyone else is, and they're having side conversations and chatter and you're missing it all. Yes. And uh, yeah, and I can't, and, and it's just noise in, in the headphones, but, uh, I think it's a point if, if you have one person who can't be on a meeting live, it kind of ruins the whole meeting.

[00:26:45] **Tim:** So sometimes it'd be like, yeah, we're all in the same building. Let's just go ahead and have a video chat just because the experience is better than having two people in a room and two people on, you know, a video call. It's just, it doesn't work. It's all or nothing for

[00:26:58] **Carol:** me. And that's my fear of when Clear Capital actually takes everyone back because they're starting a phased in approach of bringing people back in the office.

[00:27:06] **Carol:** But the tech team, the engineering side of the house, has apparently been on a 3 2 kind of work schedule. Where they're in the office three days a week and they remote work two days a week is kind of the, the norm for everyone. And on those three days in, that's when we do story planning. That's when we have all the big meetings and I've gotten like the virtual side of it from everyone.

[00:27:29] **Carol:** So I'm, I'm wondering how it's going to differ when they have to still do the video call to get me in on it or start the audio call because I'm going to be the only one not there other than like when someone's. Kids' sick or something and they need to work. You know, there may be one or two offs here and there, but I'm gonna be the one on everyone.

[00:27:46] **Carol:** So, may may prove to be a challenge there too, that I hadn't thought about that until you just said it. I'm gonna miss a lot of those side conversations that are happening and a lot of the communication is just not gonna be there.

[00:27:58] **Tim:** And I, I mean, I feel for HR right now, it's, it's, it's, oh yeah. Across the board.

[00:28:02] **Tim:** It's a struggling time for them. Yeah. Feel for the, and, and what's weird, I didn't even think about this. We, we had a meeting with hr and you have all these people now working from home. And if you, if you're working from home and your home is your official office and you hurt yourself, you can still file for worker's comp.

[00:28:20] **Carol:** I had read a post about that. Someone had basically like asked the question somewhere in a forum was like, you know, I got injured on my desk. Like while doing something is that workers comp because my company has forced everyone to remote work until COVID is over. And the answers were mostly technically, yes, that's your workplace.

[00:28:40] **Carol:** And yeah. Yeah.

[00:28:42] **Tim:** And what's crazy is like, you know, when you're salaried and you don't have defined hours, um, you, you know, you, you're walking up the steps at midnight, a little tipsy and you break your leg. Technically you could still file for, for, for workers comp on that. I mean, so it's, it's kind of weird.

[00:28:59] **Tim:** It's kind of a crazy, crazy world there.

[00:29:02] **Carol:** Yeah. The things they're having to deal with right

[00:29:04] **Ben:** now. One thing that I always forget. And I, I'm sure a lot of companies have something along this lines is you get some amount of dollars every year that I think you can put towards your home office and freshening up equipment or freshening up a desk chair, that kind of stuff, always forget that that's available.

[00:29:22] **Ben:** I've never taken advantage of it. I feel like I need to. To mark that down

[00:29:26] **Tim:** and actually do something. And you can also, I mean, you can write part of it off on your taxes, you know, have the, uh, home. Oh, hold on. Office

[00:29:33] **Carol:** tax credit. Take that back. They actually, they changed the guidelines for this. I think it was this year they changed the guidelines or the, or 2020.

[00:29:40] **Carol:** Yeah. Basically, uh, the only way you get to claim it, I have to remember, I don't, don't hold any of this to me, you know, don't, don't look up your own tax law, obviously, but you had to have your own business. If you are working remote. And the company didn't have an office maybe, but if there was an office, you can't claim it.

[00:29:58] **Carol:** So you just need to go figure that out. You may or may not be able to, but yeah, we have the same thing. We have the, you know, you get money to like, go, you know, get a new chair, do something to your office. Um, and, but they just automatically sent it to us. They're like, here, go, here's 250, go do it. But the other thing that they did when this started is they give everyone, um, an internet.

[00:30:21] **Carol:** Like they basically are giving you, I think it's like 37 a month or something or a check that maybe 37 every check to help cover the cost of your internet home usage since you're working from home. Oh, that's awesome. I don't know how they came up with that number, but. It was like, here, you're having to use your own stuff, so we'll help you.

[00:30:42] **Tim:** I don't know. So, I mean, I don't think there's a whole lot people can do to try to convince people to stay. Even if they go back to the office, they might realize that things have changed, right? So, if it's a hybrid model, they're like, well, this isn't the same office I used to come to anymore, right? It feels dead in here.

[00:30:57] **Tim:** Or that my favorite person who was here, they're now working from home. And so, I mean, ultimately, firms can't do much to hold on to employees, but I think once the churn is done, hopefully there'll be a lot more people in jobs that they like better.

[00:31:10] **Carol:** Not to say that there was something good from COVID because, you know, there's been a lot of bad from COVID, but I think the good thing that I've seen in my friends and in my family is that.

[00:31:21] **Carol:** The focus of loving work so much that it's your full time, like, let me do this all the time has shifted to let me do my family things now. And I am way more motivated to sign off at five o'clock and go cook dinner than I have ever been in my life. And I value the time with my mom and dad more than I've ever valued time with them because it made me feel like I wasn't going to have them.

[00:31:44] **Carol:** Like it scared. The craft out of me thinking that they were going to catch this and something was going to happen. So I think the value to family has become more important. So if you're working in a job, that's taking away any of that time. I could see people being like, F this, I'll go find a job that focuses on my family.

[00:31:59] **Carol:** I'm good. So that's

[00:32:01] **Ben:** nice though. I have a question for Tim. As someone who. Has been in a company for 20 years and I think is either in the past or currently in a position where you hire other people. I've always been told that in the tech industry, the average tenure at a company is like two years.

[00:32:19] **Ben:** What's your perspective on that? If you, if you're looking at someone's resume and they, They've been here for a year, there for two years, another place for two years. Is that problematic in your perspective at all? Or is that just, that's how the industry works? It's not an

[00:32:32] **Tim:** issue. Mike Lugino I think that's how the industry works.

[00:32:35] **Tim:** Um, but I mean, we tend to have pretty long, I don't know why people tend to stay when we, you know, I haven't done a lot of hiring in the past few years. I did a lot more earlier on. Um, now HR kind of handles all that. But I, what I find the group that jumps around the most are salespeople. Salespeople, like if they stop, if they stop making those sales, man, they're, they're gone.

[00:32:58] **Tim:** It's like, you know, I got to get my commission check. But as far as tech people, yeah, you do see some that have moved around a lot and that. Is it a red flag? It just depends if the quality of their work is really, really good and you can justify, you know, the salary for that. You're like, you know, we'll just, we'll definitely just make sure that we get the most out of them for those two years.

[00:33:18] **Tim:** Cause some people just do, they, they like to move around. The second they get an offer that's better, they're gone. I

[00:33:24] **Carol:** want to throw in something here. So mine's not, mine's not about getting a better offer. It's about getting bored and suddenly feeling like I'm not learning anymore and I'm not getting any better at what I'm doing.

[00:33:36] **Carol:** So I want to switch to a new application, to a. Start up to a new company to where I can go learn new things and I can better myself and better my skills. Because once I get stale, I'm bored and I can't be bored. And I'm one of those that switch jobs about every five years because I get bored. So either put me on a new project.

[00:33:55] **Carol:** Five years is a pretty significant

[00:33:56] **Ben:** amount of time.

[00:33:57] **Carol:** Yeah, that's fine. I mean, five's about what I've been doing. You know,

[00:34:00] **Tim:** I mean, and you're only like

[00:34:01] **Carol:** 22. Yeah. I don't have a kid that's about to be 20 or anything this year. He will be 20. 20. That's crazy. Yeah. So it's, to me, it's boredom. I, if I look at someone's resume and they're like, Hey, I have switched jobs.

[00:34:15] **Carol:** Well, did you do a good job there? Do you have references from those companies? Cause usually they do. They have like good references. It's just boredom.

[00:34:23] **Tim:** Well, I mean, that kind of goes into your potluck

[00:34:25] **Carol:** topic. Oh yeah, yeah, yeah. So I guess I'll go next then. I mean, I am last cause Adam's not here to bring anything.

[00:34:32] **Carol:** He, uh, said he was coming and it didn't show up. Such a dad thing to do. So, uh, with my failure, I kind of wanted to use it into my, um, potluck for the day. I really wanted to talk about staying focused and figuring out kind of like what you guys do when you are struggling with either motivation or you're struggling to just stay on task.

[00:34:56] **Carol:** Like, how do you handle that? Because I find myself, if I end the day, On a task that I couldn't resolve, I hate starting it the next day. And I don't know if it's the challenge of doing it, or if it's... I don't want to feel like a failure again. Like I finished the day, I couldn't resolve it. Now I have to open this back up knowing I'm going to open code I couldn't figure out yesterday.

[00:35:19] **Carol:** Or I'm going to open a problem I couldn't solve yesterday. So why even start it today? So then I go... Watch the dishes or do the laundry or watch a TED Talk. Like, I'll do anything other than start that task. And sometimes it's just... My mind's not in it to code. My mindset just isn't there. And I just can't get on tasks.

[00:35:38] **Carol:** So I know other people struggle with it. Just how do you guys stay focused? What do you do to stay focused? Or what do you do when you can't focus? What are like things that you...

[00:35:48] **Ben:** I'll say that I think I'm very lucky in that I don't get distracted by a lot of stuff. Like I, I don't have a lot of stuff that interests me.

[00:35:56] **Ben:** So I'm not a person who likes to scroll on Twitter or Facebook. I don't know how to use Instagram.

[00:36:04] **Carol:** So the key is to be lame. Okay, got it. The

[00:36:08] **Ben:** key is to be an old man, I think. I have an old man scrolling. You're bored at old

[00:36:15] **Ben:** age. I've always been, just my whole life, I've been very Um, narrowly focused in, in terms of the things that even vie for my attention. When it comes to work stuff, I definitely relate to the idea of hitting a wall and then feeling like I can't focus on the current task. In that case, I have two strategies for success.

[00:36:37] **Ben:** One is I either. Take the task that's frustrating me and finding the smallest possible part of it that I feel like I can solve and just putting faith in the idea that if I can get that done, then there'll be some other thing after it that I can figure out. And I can just, I don't know, like that's, that can sometimes be enough to just get me to keep moving forward.

[00:36:59] **Ben:** Sometimes if I'm feeling just completely blocked, I'll just work on a different task and, and I, and what I like to do is have a whole bunch of little random tasks that I've created that may be months old that are just sitting there in my backlog and I put them in a special Epic or I give them a special label and I know that this is sort of a.

[00:37:21] **Ben:** A list of tasks that are feel good tasks, like things, even just deleting a file. Every now and then I'll be going through the application and I'll come across a component and I'm like, where the heck is that used? And I'll search for it in the code base and it's not referenced in a year, uh, anywhere. So I'll just create a task to delete it.

[00:37:37] **Ben:** And then I put it on the backlog. Nice. That little gem, I'm coming back to you. Yeah. I'm going to delete you one day.

[00:37:44] **Carol:** So rather, yeah, I mean, I like that. I like rather than doing it right then. Cause then it's into the work you're doing and that's just a giant mess itself. But you get to then come back to it and have that tiny little thing to work on to kind of break up your mind block.

[00:37:56] **Carol:** That's a good one. I

[00:37:57] **Tim:** do. Sometimes I get distracted. What I find the things that work for me most is I, the first thing in the morning I try to get to inbox zero. Okay. First thing I do is get to inbox zero, you _(quack)_.

[00:38:09] **Carol:** I know, right? Mr. Ben's sitting there with a thousand unread texts

[00:38:13] **Tim:** right now. That would drive me insane.

[00:38:16] **Tim:** I have to get to inbox zero before I, I have to, cause I got to get all those things out of the way. Even if my response is to acknowledge I got the email and to acknowledge that I will give you an answer. I'm fine with that. I'll, I'll do that. I was like, got your email. I'll, I'll spend some time looking into it.

[00:38:31] **Tim:** Get back to you later. And that, you know, I may not necessarily, or sometimes I do have the answer that they need or set up a meeting or whatever. So, number one was Inbox Zero. Number two is I have this, uh, notebook, paper notebook that I write down things that I need to do and I just put a little check box next to it and that just helps me track it.

[00:38:54] **Tim:** I will look and see, all right, what haven't I checked off? Um, and then the third biggest thing is I ask myself, what am I avoiding? What am I avoiding?

[00:39:02] **Carol:** There's always something I'm avoiding. Yeah.

[00:39:05] **Tim:** There's always, there's something I'm, I'll ask myself, what, what am I avoiding? And why am I avoiding it? And my kids do this when it comes to dinner.

[00:39:12] **Tim:** They eat the thing they like least on the plate first and then work their way to their favorite, to their favorite food. I do that. So they have something to look, yeah. And I kind of do that with tasks. I'm like, all right, I'm avoiding this. I need to stop avoiding this and just, you know, if it's like a particular piece of code, I don't work in my, having opened my code editor yet, I'll open it and start looking at it.

[00:39:35] **Tim:** And then eventually I find myself just, just the pattern of like, kind of like Ben says, take the next step, fix something about it. A lot of times the things I avoid, they aren't necessarily code related. They're like contract discussions or. Working on, um, you know, marketing needs some bullet points for this product.

[00:39:51] **Tim:** And it's like, I avoid that. I don't know why, but I avoid that. So like, what am I avoiding? And I work on the things that, that are, I'm avoiding the most. And then I slowly get to work on the things that I really want to work on. The kind of like Ben said, those little nuggets where you can. Have a task and you're like, oh, go delete this.

[00:40:08] **Tim:** Cool. We delete that. So that's how I do it. So I don't have a d h ADHD that tells .

[00:40:13] **Carol:** Yeah, I do. I do have a d h ADHD and I am actually medicated for it, but some days even medicine doesn't help. It's not enough. Yeah, I still just can't do. But like on Friday, I uh, had to go to the chiropractor 'cause my hip flex are locked up on my run Thursday, which I was so happy to get to do.

[00:40:29] **Carol:** 'cause typically Thursday nights I can't run far 'cause we have the podcast. So I ran far Thursday night. My hip flexor locked up. So Friday morning, I get back and rather than starting to code, I walk in the backyard to go look at said baby bird eggs, right? Because I found them the day before. So I was like, let's go check on the bird eggs.

[00:40:46] **Carol:** And as I'm walking across the yard, I stopped myself and I'm like, No, don't go look at the eggs. The eggs aren't important. What is the important thing that you should be working on right now? And it's like, okay, go back inside. Just turn around. The eggs may or may not be there, but you can find out after work if the eggs are there.

[00:41:05] **Carol:** That'll be your important thing at like 530. So, um, go back in the house. I open the code and I open Slack because, you know, this is where we were actually doing some production stuff on Friday. So, I should kind of know once I dive in. I'm in it and I'm pretty good. It's just getting going. It's that everything else feels more important.

[00:41:24] **Carol:** And until I step back and go, okay, like, like Tim said, what is the thing I'm like avoiding? What is that important thing? And go do it. Like just open it, let it be there and then kind of get going. But getting there is a challenge some days. It's not, not easy for me.

[00:41:41] **Ben:** So my kryptonite is when I don't agree with a task.

[00:41:46] **Ben:** That's the worst. Like, I don't want to do it. Yeah, I'm not sold on it. I'm not. I don't think it's the right move. I don't think it's the right priority, or I hate to sound like boastful, but I don't think it's a good use of my time. That's not boastful. I

[00:42:00] **Carol:** mean, it's just.

[00:42:01] **Ben:** You know, like, Oh, there's more important things I could be doing.

[00:42:04] **Ben:** Well,

[00:42:04] **Carol:** there's more important things we all could be doing.

[00:42:06] **Ben:** Right, right, right. But yeah, it makes sense. Do you know who I am,

[00:42:09] **Tim:** sir? I

[00:42:10] **Ben:** am Ben Mattel. And, and every, sometimes I don't think there's anything I can do about that. There's just stuff that has to get done. And I don't think it's the right thing to do, but management does.

[00:42:21] **Ben:** But sometimes. If I give someone the opportunity to sell me on the task, like, why should I care about this? And then they articulate, here's why we're doing it. And here's the customer value. And here's the, the need it's going to solve. I'd be like, Oh, all right. Yeah. I totally didn't think about it that way.

[00:42:37] **Ben:** Or I didn't see what you were saying before. And now I'm invested. And now I'm, and now I'm excited to do it.

[00:42:42] **Tim:** Kind of like I was telling you to do with other people earlier in the show.

[00:42:47] **Ben:** See, it's all big circle. It has been a big circle. Communication is important. I don't know. Something, something, yada,

[00:42:53] **Tim:** yada,

[00:42:54] **Carol:** yada.

[00:42:55] **Carol:** Do you guys listen to music when you are actually trying to focus like on code? Or is there, do you turn on like background stuff? Cause one of my friends had mentioned that he turns on shows that he's watched in the past that he loves. So like he just turned on, uh, CSI or something. One of those, like that has 15 episodes, I mean, 15 series or something.

[00:43:13] **Carol:** And he's just been background playing those. I was like, I can't do that. I can do music only if it's like Hamilton, like musicals, I can't do actual music. Cause then I want to like listen to the lyrics. So yeah.

[00:43:25] **Ben:** Yeah. Yeah. I've been doing, uh, operas. I enjoy an opera. Yeah. Cause I don't know any of the, you know, it's all in Italian.

[00:43:31] **Ben:** I think it's

[00:43:32] **Carol:** easier to just kind of let it go without a lot of focus.

[00:43:35] **Tim:** No, I can't do it. Noise. Distracts me. So I have to have quiet.

[00:43:40] **Ben:** I have a, someone who you all know who shall remain nameless to protect the innocent. We used to listen to audio books while programming. Who does that? And I was, I'm just like, there's no way that's working out for

[00:43:56] **Carol:** you.

[00:43:57] **Carol:** Please tell me it was Adam. Please tell me it was Adam.

[00:44:00] **Ben:** I'll tell you in the chat.

[00:44:03] **Carol:** I can't do that. I can't listen to a book and write code. I have to focus. I wish I could do that.

[00:44:09] **Tim:** I don't think you're doing either one's service, right? You're not, you're not, you're not, it's not helping your code. It's not helping you take in that book.

[00:44:17] **Carol:** All right. Is that our potluck? We're done with dinner. I think it's a

[00:44:20] **Tim:** potluck. Tasty. Tasty.

[00:44:22] **Carol:** Time for dessert. All right, well, let's bring this thing home then. So if you like what we're doing here, you might want to consider supporting us on Patreon. You can find out more if you visit us over on over at patreon.com/WorkingCodePod. Every Patreon gets an invite to our Discord server, and we have other perks available like you Get the early access and you get to come play games with us sometimes. And we have aftershows and pew, pew, pew aftershows. Hey, that's a secret. And of course our top tiers on Patreon get a little bit extra.

[00:44:59] **Carol:** One way we like to repay them is to give them a little shout out. Uh, so our two top Patreons right now are Peter and Monte. Thank you guys for being awesome. All right. And to everyone who listens to the show, um, thanks for listening. Please, please share the show with a friend, coworker, because there's no better way to support us than a word of mouth referral, tell the algorithms to boost our signal by leaving us review and rating us on iTunes or wherever you get your podcasts.

[00:45:23] **Carol:** And of course you can always send your questions and topic suggestions on Twitter or Instagram at @WorkingCodePod, or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next time. Until then,

[00:45:39] **Tim:** remember your heart matters.
