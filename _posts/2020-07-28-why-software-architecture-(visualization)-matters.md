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

<video title="navigation flow of left an right app" controls loop>
<source src="{{site.baseurl}}/assets/videos/leftright.mp4" type="video/mp4">
                            Your browser does not support the video tag.
</video>*navigation flow of left an right app*

So you need more information to compare the software architectures? What software developers would normally do would be to look at the file structures of the programs:

![]({{site.baseurl}}/assets/images/file_structure.png)*file structures of left and right app*

Now, can you tell me which program is better structured? If not, that's totally understandable. I couldn't do it either. An experienced developer could use this file structure to make individual guesses as to how the two programs are structured. For a final analysis, one would have to look at the content of the individual files. But where do you start? It's funny how incredulous non-developers react when I tell them that a lot of my work is looking at hundreds of text files and the constructs they contain, and understanding where and how they refer to other constructs. Constructs, which in turn are described in further text files. Most people think of software development as much more glamorous. And above all, it's not just unglamorous, it's damn draining. The human brain is not designed for parsing text files. That's why computers were invented. But there is one thing that the human brain is very good at: recognizing patterns.

That's why I visualized the structure of the two apps in a different way. Take a look at the images below. I am sure that you can help me afterwards.

![graph of left app showing clean tree]({{site.baseurl}}/assets/images/left_graph.png)*dependency graph of left app*

![graph of right app showing big mess]({{site.baseurl}}/assets/images/right_graph.png)*dependency graph of right app*

So now again: which of the two architectures is cleaner?

...

...

...

You are spot on! The left app is much cleaner. Isn't it fascinating how quickly and intuitively you can recognize this? You don't even need programming experience. Thanks for your help! But while you're at it now, I have a bonus question. Our little app "Left" is about to be released. And as it is, it occurs to the concept designer right now that it feels much more natural for the user when they first see the orange and then the turquoise bubbles. Take another close look at the graph on the left app. In which blue bubble do changes need to be made?

...

...

...

Exactly! Something has to be changed in the blue "NavigationController" bubble. Could that be a little more precise? It may be a very large construct. So let's zoom in a little.

![zoomed graph of left app showing clean tree]({{site.baseurl}}/assets/images/left_graph_zoomed.png)*zoomed dependency graph of left app*

The blue "NavigationController" bubble contains various orange bubbles. In which of these bubbles do I have to make a change if I want to change the order of the screens?

...

...

...

And right again! In the "showNext" bubble. Today seems to be your day. You have just evaluated two architectures and knew straight away where to make an adjustment. The first was a consequence of the visualization of the software architecture. The latter was a consequence of this visualization and the clean architecture itself. And that's why: software architecture (visualization) matters.

Addendum: Of course, the visualization of software architecture is not a silver bullet, but a useful tool. Larger projects rarely stay structured like our small sample app. Some problems are explained quite well [here](https://www.youtube.com/watch?v=QM1iUe6IofM). But just because the perfect software architecture is impossible doesn't mean you shouldn't try. Stay tuned and check back again in the future when I analyze *real* software projects.

Fun fact: The "right" app is not unusually unstructured by iOS standards. Every sample project from Apple was structured like this in the UIKit days. The reason for this is simply the fact that every viewController can access its [navgationController](https://developer.apple.com/documentation/uikit/uiviewcontroller/1621860-navigationcontroller).