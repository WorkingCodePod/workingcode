---
title: "122: Coding Hot Takes"
description: "This week on the show, we talk about stuff we've been working on or thinking about lately."
date: 2023-04-12
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/122-coding-hot-takes/id1544142288?i=1000608593049"></iframe>

This week on the show, we talk about stuff we've been working on or thinking about lately. Adam dazzles us with his use of 1Password's Secrets Automation feature to drive key rotation in his production app. Ben misses the beautiful agony of having to support IE11 (and how it make the web more predictable). And, Carol shares her frustration with React and, especially, with JSX. It turns out, not everyone loves JSX or - _clutches pearls_ - the idea of single-file components!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/122-coding-hot-takes.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I don't know if this is exciting, this is actually, it's not exciting, but I have sort of like a hot take, which is that

[00:00:06] **Tim:** Uh oh.

[00:00:06] **Ben:** I, I, I sort of miss having to support I 11 and I know it sounds crazy cuz I 11 is a,

[00:00:15] **Tim:** It is crazy.

[00:00:17] **Ben:** monkey browser.

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go. It is show number 122. And on today's show, we are gonna talk about that one time at code camp. Uh

[00:00:46] **Tim:** If you know, you know.

[00:00:47] **Adam:** but first, as usual, we're gonna start with our triumphs and fails. And Carol, it looks like it's your turn to go first.

## [00:00:54] Carol's Failure

[00:00:54] **Carol:** Oh yeah, I'm super sorry guys, but I'm kicking us off with a failure. I really, really miss coding on a Mac, but I don't wanna purchase a Mac right now, so I'm gonna keep using my Windows box and my laptop to do everything. But I was, starting some React training this week and just setting up, you know, like I had to install VS code on my PC because I've never used this one for writing code.

[00:01:18] **Carol:** And I hit node dash v. I'm like, what do you mean it doesn't know what the command node is? And I'm like, wait, how do you install node on windows? And I'm like, Googling, which then puts me down rabbit holes of other things I wanna learn. And it's just been sidetracked, kind of hell. But I do have code running, so that's a good thing.

[00:01:38] **Carol:** But I definitely miss my Mac and I think that'll be one of my big purchases whenever everything kicks off.

[00:01:43] **Ben:** Were you always on a Mac or did you start on a PC and then go to Mac and now you're back on pc?

[00:01:49] **Carol:** Yeah, started on Windows, developing CF and then moved to Mac, and I don't think I'll ever enjoy working on the Windows machine again.

[00:02:01] **Ben:** Yeah, it's so interesting. I followed the same thing. I was on a Windows computer for years. I only switched to Mac maybe like 11 years ago. And, and it, I really enjoyed it at, well, at first I didn't enjoy it cause I was so used to how Windows did things and then it was really hard for all the different geek commands for Mac, but, It, it forced me to use the command line in a way that the Windows computer had never done, and I feel like that made me a better developer.

[00:02:31] **Carol:** I agree. Yeah, completely agree. I spent a lot more time in terminal than I ever did on my Windows machine. I think my windows, my windows like limit to terminal. DNS flush, like something would happen, like IP config, dns, flush. That command on the Mac is scary and I do not wanna run it. Every time I look at it, I'm like, pass.

[00:02:52] **Carol:** I know what half of this stuff does. So, yeah, I didn't spend much time in terminal when I was using Windows.

[00:02:59] **Tim:** That's funny. I, I don't use a Mac. I've never, actually, never, never used one before, but, so I've always been on Windows, but ever since Windows came out with, Linux subsystem on Windows, I use my Linux subsystem all the time to do command line stuff. This guy, I mean, that's what I grew up on. I grew up on Command line, right?

[00:03:17] **Tim:** They by, you know, I was doing CPM and Doss before there was any user interface, so everything was command line back now. It was the only option. So that's just kind of comfortable there and a lot, a lot of times it's a lot faster to do stuff than going into some interface and clicking around and, and you can script it too.

[00:03:32] **Tim:** So.

[00:03:33] **Carol:** Yep.

[00:03:34] **Adam:** Well, since we're all telling our our apple versus Windows history, I'll, I'll throw my 2 cents in here. my first Mac was like September of 2000 and. Seven. I bought a used one, uh, and I liked it. but my first one that I bought for myself was, like Black Friday of 2008. And oh, and ever since then, that's been like, if I can't have a Mac, I'm gonna go buy a food truck or something.

[00:03:55] **Adam:** Cause I'm, I'm not going back now. I say that, but I also, I have a, a variety of Windows machines that I have to deal with on the regular, not just servers, but also like, I have a Windows laptop that I use to control my C N C. And, I have a Windows desktop in my office for gaming stuff. Eh, it's enough, that I, I get a taste every now and then.

[00:04:15] **Adam:** I'm like, yep, nope. Still hate it. Going back to Mac.

[00:04:19] **Ben:** I will say one thing that, so my, my VPs for my personal stuff is a Windows computer. And I don't know if this is the remote desktop system or if this is Mac, sorry, or if this is the window server itself, but they do honor the command C and command V instead of control C and control V. And cuz that causes no end of suffering when you can't paste a cross operating

[00:04:41] **Adam:** I think that's whatever app you're using to do the remote desktop is like mapping it for

[00:04:46] **Ben:** Well, thank you. Microsoft Remote Desktop for, for just helping

[00:04:50] **Tim:** that how you deploy your co, deploy your code control C, control V on remote desktop.

[00:04:56] **Ben:** I have a series of ways, sometimes it's just straight up ftp uh, obs and then sometimes I will use Beyond Compare, I dunno if anyone's used Beyond

[00:05:05] **Carol:** Oh, I love it.

[00:05:06] **Ben:** it's such a great, you can compare text files, you can compare directories, you can compare S3 buckets, you can compare local and remote systems.

[00:05:12] **Ben:** So sometimes if I need to be a little bit more pinpointed in my development or my deployment, I'll be on compare between the remote system and my local system. And then I can even patch like individual lines within the file, between my local system and the remote system.

[00:05:27] **Tim:** So old school,

[00:05:28] **Ben:** Oh, it's, yeah, I mean, I know it's the

[00:05:30] **Carol:** done it that way.

[00:05:31] **Adam:** so how is Visual Source safe holding up all these years later? Ben.

[00:05:38] **Tim:** I almost snorted through my nose.

[00:05:42] **Ben:** Oh.

[00:05:43] **Carol:** All right, well that's mean boys. What you got, Tim?

## [00:05:47] Tim's Triumph

[00:05:47] **Tim:** I'm gonna go with the triumph. So last week I talked about, I did a little design work, so to, you know, to be fully transparent, I, I didn't do the initial design. I, we have a customer that come on, we have to kind of imitate their site so when they come make a payment, it's not too jarring of an experience to jump from their site to ours.

[00:06:05] **Tim:** And our, our, our lead designer, Bonnie, she, she did the initial work. and so then I, and then I went in and kind of put all the, the nuts and bolts and getting the, the site working. had to interact with the design. And, I, I do so much server backend stuff that it's like my front end stuff is so, Choppy as I have to look everything up, right?

[00:06:25] **Tim:** Like, how do I, how do I validate that something's a required field and show, you know, like the little, so I had to look all that up, but I got it all working and it looks, it looks really, really good. It showed the customers yesterday and they, they were just absolutely blown away with it. So I was pretty happy about that.

[00:06:39] **Tim:** So, not something to do often, but when I do it, you know, I always feel, oh wow, I can, I can do it if I have to. That's great. Long as I have help.

[00:06:49] **Adam:** Yeah. we have, yeah, sort of part of one of our products is supposed to be sort of white label ish. Like it's supposed to look like it's part of our customer's website. And so just about every time that we sign a new customer for this product, I get tapped on the shoulder and it's like, okay, here's their website.

[00:07:04] **Adam:** I want you to go. Basically like rip off their website and make, like, make a skin for ours that looks like theirs as much as possible. You know, drop this and drop that. We don't need every little feature, but, and it's fun because it's like, it's a challenge, right? I gotta go take somebody else's design and it's probably on Droople and using, you know, who knows what CSS framework and I'm supposed to, and I get, I do that and I get their style guide and I go in like, okay, how do I make this work with my CSS grid, you know, layout and all that.

[00:07:33] **Adam:** So it's, it's kind of fun. It's, I, I heavily use like, CSS Custom Properties, which is the worst name for a feature ever. And instead of like variables, it's custom. Anyway, we're, we're way off track here. Sorry.

[00:07:45] **Ben:** What were we talking about?

[00:07:47] **Adam:** Triumphs and fails.

[00:07:48] **Tim:** Let's try some fails. Yeah, we do exactly what you said, word for word. Exactly the same thing, Adam. So, yeah. But it's cool where you can, you know, get it looking close and nice and they're like, oh yeah, this is good. So anyway, that's me. How about you, Adam?

## [00:08:02] Adam's Triumph

[00:08:02] **Adam:** So I also am going with a triumph this week. I have talked a lot lately about all this compliance work that I've been doing, and I've been in a lot of meetings and writing policies and just doing like anything but writing code. And so this week I was very excited when it turned out that I got to write some code.

[00:08:16] **Adam:** and it's actually a really interesting project. So basically like my wife got home from work the other day and I was like, I wrote code all day today. And she's like, wow. and, and not only did I write code, I wrote tests for it. This is, you know, like I'm, I'm totally on the testing is good bandwagon, but most of the code that I write is like such a minuscule add-on to a whole system that doesn't have any tests.

[00:08:37] **Adam:** And, and it's, the platform isn't easy to test on and it's just, you know, it's like, Task to try to write tests for that, that product. So I, I kind of just ignore it there, but like, when I'm starting something new, Greenfield with the, like, node type thing, I try to do things as right as possible. So I'm sure we'll get into this in the, the discussion today.

[00:08:57] **Adam:** But basically, I am writing a tool that will automate secret key rotations, which integrates with our one password for our team. and, and, like it'll auto rotate access keys in aws. Im, IM user accounts, and update them in one password for us. and it's written in type script and uses the AWS sdk and it's, yeah, it's like really well tested and I'm super happy with how it's going.

[00:09:22] **Adam:** and yeah, and it's been interesting to work on. So I, I'm excited about all that. That's been great. And then sort of double triumph here. I will not be on the show next week because I'm going on vacation.

[00:09:30] **Tim:** What? Who approved your time off

[00:09:33] **Adam:** I did. I have never been to the Grand Canyon, and our kids are old enough now that they'll be able to remember it.

[00:09:38] **Adam:** So we are taking the family and we are going out to

[00:09:42] **Tim:** the Griswolds? Go on vacation.

[00:09:44] **Adam:** right. We're going to Las Vegas and then, down, up into, I guess Arizona and Utah to go to, grand Canyon. Gonna check it out.

[00:09:51] **Tim:** Cool.

[00:09:52] **Adam:** I already have my dad jokes all like figured out and queued up.

[00:09:56] **Ben:** I I wanna circle back to this one password thing for a second though, because,so how do you have your one password set up in, in, in a way that your script can actually communicate with It is, is there a c l I that comes with one password or something?

[00:10:11] **Adam:** there is. But that is totally, that is totally separate from what I'm doing here. Th just like, you know, so yeah, you sort of like, the gateway drug to one password is like, I need personal password management. Right. I've just, I need a password management in my computer.

[00:10:26] **Ben:** That's my life.

[00:10:27] **Adam:** Yep. And then, and then you get into like, okay, I, there is a one password cli and you can hook it up with a little bit of extra work, so that you can have secrets in your one password.

[00:10:36] **Adam:** That when you, like we have a, our, we, we wrote a wrapper around, so the, the one password, c l i command is op, right? One password. and we wrote a wrapper around that that like pulls in the, the various configs that we would need. So ours is O P iq, right? Cuz our company is on iq. So we do O P iq, N P M install, whatever, right?

[00:10:55] **Adam:** And so what happens is O P IQ runs and it says, okay, well I need to pull in these config files. And so it, it pulls in certain secrets from our one password and makes them available as like, for the duration of this command, they become available as like environment variable. And then, and then different like, so N p m rrc where you would have a session, not a session token, but a, an access token to hit your private N P M repository has just a token there, like a, you know, the, the NPM token in squiggly brackets with a dollar sign in front instead of having the actual token there, and it pulls it out of, the, that environment variable.

[00:11:28] **Adam:** and then, so that's just like, that's just, you know, making developer lives safer and easier and all that. And that has absolutely nothing to do with this secrets, automation, which is what I'm working on for, the auto rotating keys. So, let, let's get through triumphs and fails, then we can come back and talk about that.

[00:11:43] **Adam:** But,

[00:11:44] **Ben:** Very.

[00:11:45] **Adam:** so yeah, I'm, I'm super excited and we leave in like, less than 48 hours to go on vacation, so,

[00:11:52] **Carol:** Well, y'all have.

[00:11:54] **Adam:** Thanks. All right. So that's it for me. How about you?

## [00:11:57] Ben's Failure

[00:11:57] **Ben:** I'm gonna go with a failure. I'm gonna call it a light failure. It's more of a, an emotional failure. So I've been upgrading my site, I mean, upgrading in quotes here, but I'm, I've been evolving my site to use the hot wire framework. And part of the selling point of Hotwire is that it keeps the page in a long running process and intercepts links and form submissions, and then performs those actions via fetch.

[00:12:21] **Ben:** And it's supposed to reduce the amount of stuff that the page has to load. Well, now that I have that up and running, I am discovering that the page request, or I, I say like the asset loading does not appear to be the bottleneck for performance on my site. The actual round trip between. The browser, or as it turned out, the roundtrip between CloudFlare, which is my CDN and my origin server or my v p s, is the bottleneck.

[00:12:49] **Ben:** And, that's a tough pill to swallow because it means that essentially nothing I do on the front end is gonna be able to, to make that feel faster. so

[00:12:59] **Adam:** do you know like what sort of network throughput you're getting to your VPs? Is it on 10, 100 or you got thousand gigabit?

[00:13:05] **Ben:** and, and it seems to be something, it seems to be the fact that I'm routing through CloudFlare, that is the, the point of latency. So to test this, I created another sub-domain on my site and, I added that to my D n s, which is being managed by CloudFlare, but I had CloudFlare not proxy that, subdomain.

[00:13:24] **Ben:** So it's just doing the DNS management, it's not actually managing the traffic itself.

[00:13:29] **Adam:** Mm-hmm. You, you gray arrowed it.

[00:13:31] **Ben:** yes, that sounds right. so when I, if I take that page, that test page on that subdomain, and I hit it through CloudFlare as a proxy, it, the times are all over the place, but it sort of is in the 200 to 250 millisecond range, which is still subsecond, but like you notice that that's a human eye picks up on that pretty easily.

[00:13:54] **Ben:** you know, that's an, that's the speed of an animation. if I do the same request, not going through CloudFlare, then it's usually in the like 50 to 70 millisecond range, which now you're talking about, maybe you don't even notice that, you know, you probably still notice it, but it's not, it's not, you don't feel it the way you feel, 257, 250 milliseconds.

[00:14:18] **Ben:** So, you know, it is like, nothing's really wrong. It's more just like it took the wind outta my sails a little bit to see that.

[00:14:26] **Tim:** You thought you were optimizing stuff and it didn't.

[00:14:29] **Ben:** You know, it's like, not to get on my high horse for a second here, but it, it's like when people talk about languages, right? And they're like, oh, you know, your ColdFusion's so slow. Like, if you switched over to a a go, you could be doing, you know, 50 terra flops in a flow bit amount of time. And then you look at the person, you're always like, dude, it's the database.

[00:14:46] **Ben:** The database will always slow you down. Like, it doesn't matter what you have in front of it, your database is gonna be the, the, the bottleneck. And I feel like I've hit that from the network level. Like the ColdFusion response times on my server are like, you know, usually around five milliseconds. and then if as like I've been tracing it out, and then if you look in the IAS logs, which is what the window server sits on, then it's like that five millisecond response from ColdFusion becomes 70 milliseconds from IIS S'S perspective.

[00:15:14] **Ben:** So that, you know, there's some latency there. And then between that and the cdn, it's like another 180 milliseconds. So it's. Ah, I don't know. I'm just frustrated. I think I might just turn off the proxying. I mean, I didn't have proxying forever and I turned it on cause I thought it would just like, make everything cooler, you know, in quotes.

[00:15:33] **Ben:** And,

[00:15:34] **Adam:** buzzword complaint.

[00:15:35] **Ben:** I, I know, and you know, it's a blog. It's not like I'm, I'm like, even if someone wanted to do something malicious, I don't know how much they could actually do. So anyway, that's me. I'm getting over my frustrations.

[00:15:49] **Adam:** Oh, I'm sorry for your latency.

[00:15:52] **Ben:** Thank you. appreciate that.

[00:15:54] **Adam:** Alright, well, we said we were gonna talk about code. Let's talk about code. It is the Working Code podcast after all.

[00:16:01] **Ben:** Do it. You wanna kick it off?

## [00:16:03] Secret Rotation Automation

[00:16:03] **Adam:** Sure. Uh, it's okay. So I'll, I'll dive into some detail about that. Secrets automation stuff. So, basically here's the use case. we have some IAM users that, we, that represent our customers, right? So, basically a big part of what makes our software work is our customers give us. large files of their data on a daily basis, right?

[00:16:26] **Adam:** So where in the old school days, maybe, you know, they would, you know, use a modem dial in, drop in a flat file of like, okay, the first nine characters are this id, and then the, you've got the next 16 characters are the name and all that, right? Like, instead of that, we've got them uploading files into an S3 bucket.

[00:16:43] **Adam:** and then they hit it in an API to let us know that the file is there and we go consume it, and we import it and all that, right? and so in order to share that S3 bucket with them, we have, IAM users set up for, you know, an individual user for each customer, and that gives them access to their private bucket so that there's all kinds of separation.

[00:17:00] **Adam:** There's no chance of anybody's data going to a different school or whatever like that. And so we have all these users, one for each customer, and as I've been working on the compliance stuff that. Maybe this key is a little stale. Maybe you should think about rotating it. Cuz you know, seven, eight years is an awful long time to not rotate a, a secret.

[00:17:18] **Adam:** so, I started like, okay, we could just do this, but we're gonna get dinged for it again in six months or whatever. Right? So let's, if we're gonna do it, let's do it right from the start. What, what does that look like? We evaluated a couple of different things AWS offers, like a secrets manager sort of thing.

[00:17:33] **Adam:** and that has its pluses and minuses. But where we ultimately landed was using a, a feature of one password called Secrets automation, which is basically, you can, they offer a couple, it's, it's complex and, and whatever, but necessarily complex I think. So you have a vault with some items in it that have like usernames and passwords and stuff in them.

[00:17:59] **Adam:** And you can set up secrets automation. You basically like create a sort of a secrets automation user is how I think of it. And that user, you'd say, okay, can access these vaults. and you pay by the user vault, connection, right? So if you have one user connecting to one vault, that's like one token. If you have one user connecting to three volts, that's three tokens.

[00:18:19] **Adam:** Or if you have three u three users connecting to three volts, that's three tokens. and you, and so the, the free tier is three tokens and after that you have to start paying for it and they come in like bundles. and so let's see, basically we have a one password vault that'll have some secrets in it and you can put like tags on those secrets, right?

[00:18:37] **Adam:** and then I have then to, to be able to access those, access those from within your environment, you have to just basically stand up a couple of docker containers, right? So they give you like one that, will sync itself with your one password. database, I guess is what you would call it. and then another one, that is, REST API for get, like reading and writing those, those secrets from the local cash.

[00:18:58] **Adam:** And the local cash seems to be updated like instantly, so I don't whatever, whatever it is what it is. Yeah. Kind of like a, like a LaunchDarkly, you know, the, they've, you know, your, your server sort of keeps a local copy. and so you, you've got your secrets automation config done. You have your two containers running.

[00:19:19] **Adam:** and that container like has secret stuff, like you have to, when you create the user account, you have to download, keys and you include that in your container when you start it up in your environment. And so by being inside of your environment, you can make it available to all of the apps and they can go pull secrets through the rest API to, you know, get whatever access they need.

[00:19:37] **Adam:** and then I have, basically the thing that I've been working on is a lambda function. That will, run on a schedule. It'll iterate through the items in the one password vault. It'll look at the tags to say, okay, today's date is March 30th. are there any items in this vault that have a tag that say, rotate me on March 30th?

[00:19:54] **Adam:** and if there are, it will say, okay, well what type is it? And it looks at the, the tags for that. It says, okay, is it a, i like a AWS IAM access key or whatever. You know, like there's, I have type tags defined. And so like that tells it sort of what can, what can do the rotation for this entry. And then, based on that, then I know, okay, I can go out to aws, use the SDK to create a new key, deactivate the old one if I want to delete any old keys, cuz you can only have two and yada, yada yada.

[00:20:23] **Adam:** And then I update the item in one password and push that back up. So that's like all of that. And then the other, sort of, the other piece of this puzzle is we need to be able to not only automate the, the key changes, but we need to be able to communicate those to our customers. So the, the general plan is, so we have a way to schedule using tags on the one password entries.

[00:20:45] **Adam:** we have a way to schedule when they will be rotated. And I used a separate tag to schedule the deactivation so that we can say, okay, we want this secret to be rotated once every quarter, right? So maybe like January 1st, April 1st, whatever the other months are right. rotate the key on the first of the month, and then on say the 10th of the month, their previous key gets deactivated.

[00:21:06] **Adam:** So you've got that like 10 day window where both keys will. But then on day 10, the old one's going away, whether you're ready or not, it's gonna just automatically, so you better be on top of it. You got 10 days to, to get it done and, and sort it out, you know, whatever. and, and then, so that's the, the overlap in time for them.

[00:21:23] **Adam:** And then I'm, I'm thinking two things so far. possibly a third, one of my coworkers says something he wants me to consider, but, the, I'm thinking we need a screen in our admin, cuz we have a lot of very, granular role-based security. So like I can say Ben can access the page that shows the S3 access key, right?

[00:21:42] **Adam:** and so I want to, to like be able to display it on that page. And I'll use the secrets automation rest API to pull it out of one password at the time that you view the page and just show the current the, like the, whatever the two current keys are. Or if the other one has been deactivated and there's only one current key.

[00:21:57] **Adam:** and then. So I'll have it there. And then I'm also thinking like an API so that they could, if they wanted to on the second day of the month, say, okay, well what's the new key? Rotate all of their stuff on their end automatically. So that in theory, all of the key rotation on all sides of everybody is just automatically done and we all stay safe and nobody has to fret about it at all, ever.

[00:22:19] **Adam:** Right. That would be so nice. So like, yeah, like there's always gonna be those users that are like, can you send it to me in an Excel file?

[00:22:27] **Adam:** Uh,you take a screenshot of it and paste it in a Microsoft Word document and print it to PDF and send that to me? Like, no. but yeah, so, so for those people will show it in admin, like for the customers that aren't sophisticated enough to use an api.

[00:22:41] **Adam:** And then for those that can use an api, we'll, we'll offer that. Access to it from, from there. So it's super exciting to work on. Very interesting. I'm writing it in type script. doing, oh, that's the other cool thing about this. So I, you know, of course this is something that has to be super resilient, right?

[00:22:58] **Adam:** So I, I have been very gung-ho about, I wanted to do t d d on this and I wanted to like, have really good test coverage on the features. And so I had, I had a lot of things to figure out, you know, like how do you, how do you mock the AWS sdk, right? You can't, what do you Tim just made the funniest face. He's like, bullwinkle horns at me over here.

[00:23:24] **Adam:** and yeah, like, so I started out kind of, I was just like, I'll put that one aside. and I'll just think about the one password side first. Cause just rest api you have a, a bearer token that you have to include in the request. Pretty simple to to mock right? And so actually, there's this great library called MSW Mock Service Worker, which is for, it works both in the browser and in node.

[00:23:43] **Adam:** And it basically just intercepts, HDP request. So, and, and you can say, okay, if you get a request for this URL for, with like a post or whatever, this is the response. And so like you, the, the code doesn't actually have to mock the one password, sdk, I still use it, but when it makes an H T D P request, I just get to defi define what the response is, and it never actually makes it out to the network.

[00:24:07] **Adam:** So, awesome. Very fast, very well controlled. but then when I got to using it for the A W S sdk, I was like, wait a minute. Now the SDK like signs the requests and you have to have like a signed response. And it's all kinds of like, extra security. How the heck am I gonna do this? Well, like one quick Google search.

[00:24:24] **Adam:** And I found there's a, I guess it's created by somebody. You know, public, but, it's, it's even endorsed and, and, pushed by the aws, whatever team. They have a post about it on their blog. There's a, like an somewhat official, officially unofficial, SDK mox for the AWS JavaScript sdk, which is amazing.

[00:24:43] **Carol:** Yeah, they work really, really well.

[00:24:45] **Adam:** yeah. Super easy to use.

[00:24:46] **Carol:** yep. I used them in Jess when we were testing all of our type script code and it was just the best thing. Yeah.

[00:24:53] **Adam:** Yep. So that's been a, a lot to figure out. I still have some TypeScript stuff. Like I, I, I truly believe that TypeScript is the future of JavaScript for me. I love it. I love writing it, but I'm, I'm struggling a little bit with, like writing type script libraries and like sharing them between applications.

[00:25:11] **Adam:** Although I, I think I might have figured something out with this project. You know, like the last thing I did was like, okay, I've got a bunch of sort of utility modules in a group in this, in this package. And I am compiling the package to like common js. and you know, of course that strips all the type script and stuff out and like it, it works with some projects, like it works in Myel project that I'm working on, but it didn't work when I tried to import it here.

[00:25:35] **Adam:** And it's all just all sorts of like compatibility issues. And there's 11,000 different ways that you can compile your type script, like target this and whatever librarian, or you can do E S M or common Js and all this. It's such a pain. But once we get that figured out type script is definitely the future. If it's not rust, I mean,

[00:25:56] **Ben:** I have heard that building libraries with type script is a whole different kind of adventure as opposed to just building an application with it.

[00:26:03] **Adam:** I feel like I just, marathon talk for a long time. Somebody else go.

[00:26:07] **Carol:** Well, I have a question for you. Are you logging the connections made with the keys as they come in? So you would know if someone continuously like uses the key that should be expiring, or you just wait till day 10 when they can't access anything?

[00:26:21] **Adam:** You, you're talking about like one of my custers drop a file in the S3 bucket. I guess that's probably possible, but No, we're not, you know, they're,

[00:26:28] **Adam:** yeah, no, I mean, we do, have like things that monitor to make sure that the tables that we're building from those files are getting updated. So if, you know, if a table starts to be stale for like a week on end, we're like, Hey guys, your thing's not working.

[00:26:42] **Adam:** What's going on? Do you need some help? But, no. Other than that we just kind of like, you know, let them shoot their own feet if they would like to.

[00:26:51] **Carol:** you just wait for them to yell and say, my key doesn't work anymore, and then point them to how to get the new key, the new secret, and say key. The new secret.

[00:26:58] **Adam:** well, the. I don't know, like we, we, we haven't rotated their keys on them very much. Like every now. So, you know, like any eight software project we kind of started naively and, and had to figure it out as we go. And like, you know, six or eight customers in, we were like, ah, okay, this is the way we should be organizing them.

[00:27:16] **Adam:** We have like, now we do it like they all are a very consistent naming pattern and we have a policy that we just, a single policy that we apply to all the users and it looks at the username and that determines what S3 bucket that they can use. Cuz it's like the bucket is same name as the user sort of thing.

[00:27:31] **Adam:** And so the policy is like a reusable policy in that case. and so like once we figured that out, then we rotated the, the old ones that didn't have, the, the right username to be able to do that. But yeah, it's been several years since then, so we haven't really rotated 'em since then.

[00:27:45] **Carol:** so it's gonna be an inventor. When it actually starts happening,

[00:27:49] **Adam:** Yeah. Yeah. So, you know, when we get there, basically sort of the, I haven't really thought through the entire rollout plan yet, but it's something along the lines of, I'm just gonna take all the current secrets and put them in the vault that would auto rotate them. But I'm not gonna have any, like, rotate me tags on them, or, or deactivate tags.

[00:28:07] **Adam:** And then I'll be like, okay, these secrets are here available to you and on, you know, the, the first day of the next quarter, they're going to change and you will have 10 days. So I, you know, I'm giving you three months notice. You need to be ready cuz you're, then you're gonna have a 10 day window where your key is gonna change sort of thing.

[00:28:24] **Adam:** and, and I can always, you know, that's the nice thing about the way that we did it. Like, instead of building the rotation dates into the software, doing it by tag means like, oh, I've got one customer that's like, we're not ready. We're not ready. I can just be like, okay, I'll, I'll remove the tags from yours and you can have an extra month or two months or whatever.

[00:28:41] **Adam:** And. yeah,

[00:28:42] **Carol:** User adoption's hard, so hard.

[00:28:44] **Adam:** is.

[00:28:46] **Ben:** This is somewhat tangential, but just talking about all these keys being used reminded me of this thing I saw, or I heard about one time on a podcast, and I don't know if this was Amazon doing this or if this was another service, but you can create these honeypot alerts where people will generate fake credentials and store them in their source code so that in the event that the source code has ever leaked and someone tries to use those credentials, it'll set off a bunch of alerts and said, someone tried to use these credentials that that aren't supposed to be used.

[00:29:17] **Ben:** Which I dunno, I feel like that's such a clever thing to do.

[00:29:20] **Adam:** it is, but also like how do you, how do you do that in a responsible way, right? Because, so you don't wanna put a comment right next to it that says, this is a honey pot. Don't use these keys, don't erase them.

[00:29:31] **Ben:** do you make it look real?

[00:29:33] **Adam:** Right. But how do you, and how do you communicate that to the team? Like, it's here to be a honeypot.

[00:29:37] **Adam:** Don't remove it. Don't, you know, don't try to change it. You know, like, it sounds very tricky. I'm, I'm, yeah, that's a, that's a human communication problem, which is the hardest part of software. But, yeah,

[00:29:49] **Ben:** your stuff sounds really cool.

[00:29:50] **Carol:** It

[00:29:50] **Adam:** it's been super exciting to work on and, and I've only been working on it for like two and a half days, so,

[00:29:55] **Carol:** Yeah. I can see it in your face. You look super eager about it.

[00:29:58] **Tim:** And I wish I had something cool to work on.

[00:30:01] **Carol:** Right.

[00:30:02] **Tim:** Same old stuff.

## [00:30:05] IE 11 Support

[00:30:05] **Adam:** So, anybody else got something exciting? You wanna.

[00:30:09] **Ben:** I don't know if this is exciting, this is actually, it's not exciting, but I have sort of like a hot take, which is that

[00:30:15] **Tim:** Uh oh.

[00:30:15] **Ben:** I, I, I sort of miss having to support I 11 and I know it sounds crazy cuz I 11 is a,

[00:30:25] **Tim:** It is crazy.

[00:30:26] **Ben:** monkey browser. But what I appreciated about having to support I 11 was that work had a known quantity to it.

[00:30:35] **Ben:** Meaning that there was this static bar. That you could look at a feature and say, does I e 11 support it? And if they don't support it, at least can I degrade gracefully in a way where an I 11 user could still use the feature, even if it's not, it doesn't have all the, the razzle dazzle that, that a more modern browser would have.

[00:30:54] **Ben:** And what I'm feeling now post i e 11 days is this, just big question mark always around, can I use this? I'm looking at my user analytics and I don't understand all the browser versions, and Mozilla doesn't even list I 11 anymore, but I maybe I don't even care about I 11, but it's not, like not every browser supports everything all the time.

[00:31:20] **Ben:** And, and I feel like we a little bit act like, well, now that I eleven's not here, everything's just good to go. And, and that's not the case. And I, and I don't, I don't know how to move forward without the kind of bumper guardrails that I 11 gave me.

[00:31:36] **Adam:** What sort of web features are you using that you have to, like, we're not talking about rounded corners here. We're talking about like, you know, webcam access or P2P type stuff, like, doesn't work.

[00:31:47] **Ben:** I, I don't know. Like I, I guess, and maybe that's just that I'm not yet familiar with, with what features are available in all the browsers. So I, I still use, I use parcel to compile my JavaScript right now in my personal work. And you put a little browser compatibility thing and I just have it said to defaults.

[00:32:06] **Ben:** I don't even really know what that means. I think it's like last two versions of each browser or something. But, you know, then you want to throw in something like,safe navigation operator in dots or, or like the null coalescing operator. The question mark, question mark, can I throw in the, the pipe operator?

[00:32:23] **Ben:** Is that even a real thing yet? It, and like, at what point do I have to say, well, this works. Chrome 97 plus, but anyone who's on an old iPad, as I for sure, you know, like probably still on Chrome 78 and won't be able to access this feature. And, and I don't know, I just like, it, it just, it's, it does, I don't have the confidence that I used to have when I had, when I had to live in a world where I 11 had to work.

[00:32:49] **Adam:** I guess I understand what you're saying is that instead of knowing that everything sucks all the time now, you just don't know because sometimes it could suck and some, sometimes

[00:32:57] **Ben:** Yes, exactly. The, the suck, you know, is better than the suck. You don't know, I guess,

[00:33:03] **Tim:** I,

[00:33:04] **Adam:** This is not that kind of show, Ben.

[00:33:06] **Tim:** uh,yeah. I, I don't want to know the kind of person that's like, Hey, my, I 11 stopped working. Can you fix it? I don't want that per, I don't wanna know that person.

[00:33:15] **Adam:** yes, I can fix it. Here's a stick of dynamite. Put this in your CD ROM Drive.

[00:33:19] **Tim:** Yeah.

[00:33:20] **Ben:** but like, so, so

[00:33:21] **Tim:** Browsers are free. No one has ever paid for a browser.

[00:33:25] **Ben:** So like, as an example, I look at my, my JavaScript error logging for my site, and I have loads of errors where it says something like, I ex like the browser expected an expression beta dot instead. And it's probably me using something like a safe navigation operator and whatever's hitting that site, which, you know, for all I know, 90% of the time it's some sort of bot that doesn't know how to do it for some reason.

[00:33:53] **Ben:** But it's just, I, I don't know. The, the error log not very insightful.

[00:33:59] **Tim:** So, so let me ask you, so lemme show my ignorance. So how do you log a client side error so that you can see it?

[00:34:06] **Ben:** There's a global error handler in the browser, then people would typically override that and then, and then push that stuff up to a, a log repository or, you know, you could email it to.

[00:34:19] **Adam:** Yeah. So like, tools like, like Reg or Century or, you know, Rollbar, all these not sponsored, tools, that's what they do.

[00:34:26] **Ben:** No, in fact, I'm using Rollbar and I don't pay for it. So I feel very limited in how I can complain about it, but it's, it's not very good. I, I, I wanna look for something else. I wanna look for something else that has a free tier.

[00:34:39] **Adam:** Yeah. I'm reasonably happy with Century that we use for work, but I, I don't know what the free tier is. Like we, yeah. Okay.

[00:34:45] **Ben:** cuz they, they have a lot of like really advanced stuff. Right. C's the one that has the replay and stuff.

[00:34:50] **Adam:** They just added replay. Yeah. Log Rocket, I

[00:34:52] **Carol:** so

[00:34:52] **Adam:** is the one that had, session replay for a long time now.

[00:34:55] **Carol:** Yeah.

[00:34:56] **Ben:** So, yeah, so I, I don't know, you know, like I'm, I use Flex Box for a lot of stuff and again, I 11 supported Flex Box, so it was a, I love

[00:35:05] **Adam:** I'm just, I'm just saying that it's a very on brand for Ben

[00:35:08] **Carol:** Oh.

[00:35:09] **Tim:** Flex

[00:35:10] **Ben:** You know, and, and like I want to start embracing CSS grid where it makes sense, but like, can I just throw CSS grid everywhere now?

[00:35:19] **Adam:** Oh, hell yeah, dude.

[00:35:20] **Ben:** support it?

[00:35:21] **Adam:** I don't know, but I, it, it's great. I, I've been using CSS grid with, with, with, is it with abandoned? Without Abandoned? I don't, whatever. I don't, my, I, I, I deploy my CSS grid and then I throw my hands in the air, like I just don't care. Right. Like

[00:35:36] **Adam:** it's,

[00:35:36] **Ben:** Carol looks shocked. I think it's just cuz she has a pen in her mouth.

[00:35:41] **Carol:** No, not shocked

[00:35:43] **Ben:** All right.

[00:35:43] **Ben:** So yeah, maybe I just have to not worry so much. I, yeah,

[00:35:49] **Tim:** Wor worrying is very on brand for you

[00:35:51] **Ben:** yeah, totally. That's my, that's my move.

[00:35:54] **Tim:** That's, yeah. Total mood.

[00:35:56] **Carol:** poems and worrying.

[00:35:58] **Adam:** How about you,

[00:36:00] **Adam:** Carol?

## [00:36:01] JSX

[00:36:01] **Carol:** yeah, I can jump in. so I am learning React, so that's the code thing I'm doing right now. And I'm doing that because I signed some work. So I, I need to, I need to write, react, I didn't realize that I don't like J S X, like I am not a fan of my script looking like H T M L. Like I, I don't know why I enjoy when I'm like writing like my, divs that I go in there like with Angular and I like double curly bracket and pass through my variable to get the information.

[00:36:32] **Carol:** And when I'm in a script file and I'm looking at these script files and the, the H t HTML look is inside these files, I'm like, do I have to do this with React? Like, is this required that you have to write code like JSX in order to like be a cool React developer because the internet seems to think you do and I don't appreciate that.

[00:36:52] **Adam:** I

[00:36:52] **Tim:** Feels very, very cold. Fusion five.

[00:36:54] **Adam:** you, you

[00:36:54] **Carol:** feels so awful.

[00:36:55] **Adam:** you don't have to, but if you don't, if you try to do it like with just like, okay, you know, what is the react dot or is like react dom dot create element or

[00:37:04] **Carol:** Yeah. It's

[00:37:05] **Carol:** oh my God, it is awful. Like to try and like that's what's happening under the hood when you use jsx, but But to me, it's way easier to read, react, dot, create element than it is to look at dibs insight script files. I

[00:37:21] **Adam:** Well, you said you're learning this. How long have you been doing it? Like is this just your like day one reaction or?

[00:37:27] **Carol:** this is, yeah, probably my day one, because yesterday I was very angry trying to get windows set up to, you know, write codes. So I quit and had a drink and, you know, clean the pool. So this is just, this is my day one. Like, why would anyone wanna write script like this? I can't, I, I can't make myself want to look at.

[00:37:45] **Ben:** I, I'll, I'll take that one step even further, and this is an even spicier take, which is that I don't even like the idea of a single file component. I, I would much rather have my HTML in one tab and my CSS and another tab, and my code behind another tab. If for no other reason, I don't want to have to constantly be scrolling up and down on the same file to find the things that relate.

[00:38:08] **Ben:** I could, I, it's much easier for me to, like, what it's muscle memory. What is it? It's like all com or like control alt left and right to get between the tabs and my editor, I, I, I know it's a hundred percent subjective and I know that there are people who hun percent are like single file components.

[00:38:28] **Ben:** Finally,

[00:38:29] **Carol:** Heck yeah.

[00:38:30] **Ben:** land is here and, it's really hard for me to embrace the idea that it's all subjective, but it is all subjective.

[00:38:36] **Adam:** Well, I'm glad we have a diversity of opinions on the podcast. It's nice to know that somebody on here is representing the wrong opinion.

[00:38:46] **Ben:** Well here I have a question. So, you know, what do they say? It takes like 21 days to form a habit, something like that, right?

[00:38:54] **Adam:** I, I believe that my, my life coach and gu personal guru Ben Nadel said

[00:38:58] **Adam:** that.

[00:38:58] **Tim:** mm-hmm.

[00:38:59] **Ben:** like that. And I wonder, how many days, like just as a litmus test, how many days of doing something that you don't enjoy because it is unfamiliar? Does it take for it to become pleasurable because it's finally familiar? Or can you draw a line in the sand and say like, Hey, I've been banging my head against this for 21 days.

[00:39:20] **Ben:** I didn't like it on day one. I still don't like it on day 21. It's not just me not being familiar with it, it's just not enjoyable. And like, you know, how do you find, how much time do you give?

[00:39:31] **Adam:** That's a good question. I, I, So I was, I was sitting here as you were asking the question, thinking about, my journey with flossing, which is, uh, somewhat

[00:39:41] **Ben:** The dance he's talking about,

[00:39:42] **Adam:** No, not at

[00:39:43] **Adam:** all. No, I'm talking about oral health. you know, I, I didn't grow up flossing and, so, you know, as an adult, I've just had to get in the habit of it.

[00:39:52] **Adam:** And so I used an app that like, you know, it gave me, it showed me my streak, right? So I would like, you know, I've been flossing every day for a week or, you know, don't break the streak sort of thing. And when I hit the, like, one year mark, I think I had like one or two days throughout that year that I missed, but I'm like, okay, it's good enough, right?

[00:40:08] **Adam:** Like when I hit the one year mark, I was like, okay, now I can stop using the app. I've built the habit and like, I still do it. You know, like, so that, for me, that was it. Like, you know, I, it, until I hit the year mark, I felt like, okay, I, I still have to try, right? And, and now it has, now it feels weird when I don't floss.

[00:40:27] **Ben:** Yeah, but so, so just to, to fine point the conversation there. I also floss, I don't enjoy flossing, but I do it because I know it's good for my oral health.

[00:40:38] **Adam:** Yes.

[00:40:39] **Ben:** it's, but, but what I'm saying is

[00:40:41] **Adam:** right now.

[00:40:42] **Ben:** so Carol's on day two of J

[00:40:44] **Carol:** A flossing. Oh yeah, sorry. Yep. Yeah, yeah.

[00:40:48] **Ben:** you know, and there are people who saw J S X and loved it, and there are people who saw J S X and hated it, and then they grew to love it. You know, at how many days or weeks does Carol have to give herself to say, look, just keep doing it.

[00:41:03] **Tim:** I mean, is that even an option?

[00:41:05] **Adam:** was just gonna say like

[00:41:06] **Carol:** As long as the money comes. Yeah. As long as the money comes, I'll learn to love it. Right. Or I'll hate it and still keep doing it.

[00:41:13] **Adam:** I think you, you are not alone, right? A lot of people when they saw this, they were like, Ew, why no, yuck. But then, you know, over the years, people have come to accept it and, you know, maybe it doesn't feel a hundred percent natural, but when you use it day in and day out, it, it starts to at least be familiar, right?

[00:41:32] **Adam:** And, and you start to understand what's happening. And so it doesn't, so it's like, you know, when you are eating dinner and you get thirsty, you don't think, okay, I need to sit down my fork and then I need to reach you over there and grab my cup and I need to lift it. You're just like, I need a drink. So you pick up your glass and you do it right?

[00:41:47] **Adam:** It becomes muscle memory and second nature, you don't have to think about the steps. You just do it, right? So then eventually you'll get to that point in the code when you're working on the code, where you're just like, okay, you know, I'm, I'm looping, and then, okay, here I'm outputting this diviv with this stuff in it.

[00:42:00] **Adam:** And it's just like, it's, it becomes second nature where it's, it's, you don't have to think about what's going on. It just is apparent to you.

[00:42:08] **Carol:** I think reading it isn't the problem. Like it's not like looking at it, right, like it's just the way that it looks. I don't like it. I don't like how it looks. It's not pretty.

[00:42:16] **Adam:** Too many pointy brackets.

[00:42:18] **Carol:** come on. And then the other thing I'm not liking is this community likes two spaces for a tab instead of tabs.

[00:42:27] **Ben:** Gross.

[00:42:29] **Tim:** Oh

[00:42:30] **Carol:** this?

[00:42:30] **Carol:** Who, who? If you're gonna use spaces, at least make it four. You know, like what the heck is two?

[00:42:36] **Ben:** Two is the

[00:42:36] **Tim:** summer child.

[00:42:37] **Carol:** Yeah,

[00:42:38] **Adam:** Oh, my condolences.

[00:42:40] **Carol:** thank you. I am probably gonna get in trouble for checking in code with bad spacing, so we'll see.

[00:42:47] **Tim:** So I assume that this, the client you're working for, that they're on React and they want you to just kind of work on can't, you don't really have a leeway on what you're doing.

[00:42:55] **Carol:** Oh, they told me I had options for change, so we'll see how that all

[00:42:59] **Carol:** works. But

[00:43:00] **Carol:** yeah,

[00:43:01] **Adam:** dis.

[00:43:02] **Carol:** it is government, so I doubt there's very much option for change.

[00:43:07] **Tim:** yeah.

[00:43:09] **Ben:** I'm surprised the wrong react. I always pictured the government as being more of an angular group.

[00:43:13] **Carol:** This is their only react. Yep.

[00:43:16] **Adam:** The whole government,

[00:43:18] **Carol:** The whole

[00:43:18] **Tim:** that's why they're hiring her.

[00:43:20] **Carol:** Yeah, I could, I could tell you more in the after show about that.

[00:43:23] **Ben:** sure. Sure.

[00:43:24] **Adam:** Ooh, secrets

[00:43:26] **Tim:** Spicy.

[00:43:27] **Adam:** nuclear launch codes.

## [00:43:28] State Management

[00:43:28] **Adam:** Well, so on the subject of React, I, I have found that now that I have really kind of completely dove into the pool with felt where like I'm, I'm really working on an application that would be like an evolution of our product. and trying to get that baseline figured out.

[00:43:45] **Adam:** I, when I have to go back and write React now, and I, I'll just finish what my original thought first before I come back to it, but, I, I really don't like it. Like I'm, I'm. Frustrated, going back to React because felt is just so much better in so many different little ways, right? It's like death by a thousand paper cuts sort of thing.

[00:44:03] **Adam:** And I get really annoyed having to go back and I, I really honestly think that it's mostly the fault of next js, which is a weird thing for me to say, or weird, weird thing for me to feel, because for the longest time I was like, if you are going to write, and I guess I still feel like this way, if you're going to write a, a React app, I think Njs is the way to go, right?

[00:44:22] **Adam:** It's the best meta framework available. but there's things about NEX that just piss me off. So like, I, I'm, I'm smitten with Felt, and nobody's gonna change my mind.

[00:44:37] **Ben:** I do wanna watch a course on spelt because I am fascinated by the, by what people are talking about. I just, I know so little

[00:44:43] **Adam:** They, they have a really great, like a self-guided tutorial on their website.

[00:44:48] **Ben:** I, I think I've tried the tutorial and I got overwhelmed with it. It has like 78 sections in it or something. I'm like, I'm like, I just wanna know how it works. Like, I don't wanna know the syntax yet.

[00:45:02] **Adam:** I'll, I'll send you some video links

[00:45:04] **Adam:** like conference stocks.

[00:45:05] **Ben:** But I, the thing that I get hung up with react all the time, is it, it feels to me like so much of it came from this idea.

[00:45:17] **Ben:** Maintaining state is hard. I have this count variable over here and I don't wanna do count plus plus because then some other thing that might have to check on that count is gonna get outta date eventually. So they, they took away the state or they took away the state in a way that I felt was very easy to manage, which is mutable state.

[00:45:37] **Ben:** And they built this huge, huge infrastructure around workflows that facilitate unidirectional data flow and, and the, and hooks. And now pulling in like used state. And I'll tell you like if I, if I look at a React component from eight years ago, that was a, that had like a, the render function and some used state.

[00:46:01] **Ben:** And then I look at some of the stuff that people are building today, it's. I'm like, ha, it's so complicated looking. It's so complicated looking with the hooks and the dependencies and things have to be in a special order. I'll, sometimes I'll do a pull request at work and someone will send me a PR and I open up the PR and it's a component, and I swear it has like 37 used statements at the top of the function, and I'm like, really?

[00:46:27] **Ben:** This is easier for you people to reason about it does not feel easier.

[00:46:32] **Adam:** it's easier than learning reds. Jesus.

[00:46:36] **Ben:** I, I don't know. I guess I'm, I, I never had a problem with mutative, mutable state. It just seemed to be pretty

[00:46:43] **Adam:** Yeah. So I, I, I totally feel you. And I think that maybe the distinction is that React came out of Facebook. So you have to remember that this came out of, like probably the website that has the longest running single page app sessions on the planet, right? Like, and, and so mutable state there. and, and side effects.

[00:47:04] **Adam:** And you know, like things, it's exactly the same reason that like, it's just smart to reboot your computer at least once a month, if not like once a week, right? Like so many of us just like closed the lid on the laptop and oh, all of a sudden I've been running for six months and I have like three security updates I need to apply.

[00:47:20] **Adam:** And you know, it's the exact same thing with, with a single page app in the browser. Like there are benefits available to you to just refresh the page, right? It'll clear up so much cruft if it's a, especially with mutable state. And I think that that's what they were solving for.

[00:47:36] **Ben:** I guess, and then I get so jaded because I'm an angular fanboy. So I've been loving an angular for a decade or, or however long.

[00:47:44] **Adam:** Thank you for bringing the diversity of opinions.

[00:47:46] **Ben:** and I, so, and I saw, and the problem is, is like I saw a wave of people leave Angular and go to React because. They're like, oh, react makes everything so simple.

[00:47:57] **Ben:** It's so bare metal, and I can learn JavaScript. And now I see this like wave of people now moving away from React towards things like selt and View, and they're like, oh, how great is Swollen View? You can just increment a variable when you need to increment. I'm like, yeah, that's what you had 10 years ago.

[00:48:13] **Carol:** And you went to React,

[00:48:15] **Adam:** What's the, oh, I remember when I was trying to learn Angular, the thing that was like, took me so long to, for, to remember, I forget what it was called. like a deckler directive. Yes. Thank

[00:48:25] **Carol:** ah.

[00:48:25] **Ben:** Yeah,

[00:48:26] **Adam:** Those were a lot, very difficult to wrap my

[00:48:28] **Ben:** directives. Yeah. You gotta wrap your head around them for sure. But everything is a directive in Angular, but

[00:48:35] **Adam:** yeah. And I was on like Angular 1.2 or 1.1, something like that. It's a long time.

[00:48:41] **Ben:** oh, I'm good.

[00:48:44] **Adam:** You all right over there, Ben?

[00:48:46] **Ben:** I'm good.

[00:48:47] **Tim:** Are we boring you?

[00:48:48] **Ben:** No. I just get so frustrated by people.

[00:48:51] **Adam:** I'm sorry.

[00:48:52] **Ben:** No, not you guys. Obviously.

[00:48:55] **Adam:** All right. Is that it? Have we beat, this horse to death?

[00:48:59] **Tim:** Yeah, I mean I've got no, nothing interesting to code, talk about, yeah, just been doing some ColdFusion, some Scala and some HTML and yeah, nothing, nothing exciting.

[00:49:09] **Carol:** H L you say,

[00:49:10] **Ben:** ColdFusion's

[00:49:11] **Carol:** tell me more.

[00:49:12] **Ben:** bro.

[00:49:13] **Carol:** Css. Ooh.

[00:49:14] **Tim:** Mm-hmm. And just dealing with the, upgrade to Java 11 and they don't have the XML bind. They deprecate, they deprecate it now, they actually removed it from, Java 11.

[00:49:25] **Tim:** So I'm trying to figure out how I can get that back. So

[00:49:27] **Ben:** I don't understand anything you just said, but that sounds good.

[00:49:30] **Tim:** That's alright.

[00:49:31] **Carol:** know what.

## [00:49:32] Patreon

[00:49:32] **Adam:** Alright, well I guess that's gonna do it for us this week. this episode of Working Code was brought to you by a diversity of wrong opinions. And listeners like you, you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:49:52] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. If you'd like to help us out, you can go to patreon.com/WorkingCodePod and all of our patrons, every single one of them, gets access to our after show, which is after we stop the recording for you guys, we are gonna go, and tonight we're gonna talk about the business side of creativity.

[00:50:10] **Adam:** Carol wants to talk about React for her new gig, and apparently you can't copyright generative art. That was a mouthful. but that's on the after show, and if you wanna find out more, you're gonna have to pay for it. Sorry. but that's on the after show. And, if you wanna find out more, I guess you're just gonna have to become a patron.

## [00:50:27] Thanks For Listening!

[00:50:27] **Adam:** Your homework this week is to, once again, leave us a review, go to workingcode.dev/review, and if you've already left a review, do another one. Just do it. that's gonna do it for us this week. We'll catch you next week, and until then

[00:50:41] **Tim:** Remember, your heart matters. No joke this time. Seriously, you guys, your heart matters. Take care of yourselves. We love.

[00:50:47] **Carol:** Oh,
