---
layout: post
title: "Why software architecture (visualization) matters."
date: 2020-07-28 12:00:00 +0000
categories: [software architecture]
post_image: "assets/images/architekkt_modules.png"
---
So you have no idea about software architecture? Perfect. I need your help. I'm trying to figure out which of the two apps below is better structured. Watch the video to understand what we're talking about here. At the beginning, both display an introductory screen with the appicon. A screen with three turquoise bubbles follows. Everyone loves turquoise bubbles. And finally there is the last screen with an orange bubble. This navigation flow could represent any introduction to any app. In the real world, this could be all sorts of things that happen when you first open an app. A nice animation, short tutorials, asking for the push permission, the location permission or the phone number. In short any screen is possible. In order not to distract ourselves further (and because I already had the assets prepared for the main page), we stick to the appicon, the turquoise bubbles and the orange bubble.

Did you see the video? Then you might ask yourself the following questions:

- How the hell should I use the video to decide which app is better structured?
- And can such a small useless program be structured differently well, i.e. better and worse?

Regarding the first question: You are right there. Just keep reading. Regarding the second question: Definitely. Of course, the effects of poor architecture on a very small program are mostly not tragic. But all the big, impenetrable software hells that developers deal with in their everyday lives were once small, innocent programs. So again, just read on.

<video title="left app and right app video" controls loop>
<source src="{{site.baseurl}}/assets/videos/leftright.mp4" type="video/mp4">
                            Your browser does not support the video tag.
</video>
So you need more information to compare the software architectures. What software developers would normally do would be to look at the file structures of the programs:

![]({{site.baseurl}}/assets/images/file_structure.png)

Now, can you tell me which program is better structured? If not, that's totally understandable. I couldn't do it either. An experienced developer could use this file structure to make individual guesses as to how the two programs are structured. For a final analysis, one would have to look at the content of the individual files. But where do you start? It's funny how incredulous non-developers react when I tell them that a lot of my work is looking at hundreds of text files and the constructs they contain, and understanding where and how they refer to other constructs. Constructs, which in turn are described in further text files. Most people think of software development as much more glamorous. And above all, it's not just unglamorous, it's damn draining. The human brain is not designed for parsing text files. That's why computers were invented. But there is one thing that the human brain is very good at: recognizing patterns.

