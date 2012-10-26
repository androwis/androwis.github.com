---
layout: post
title: Pushing Boundary
tweet: Here's what I'd like to see from @boundary.
---
Distributed systems really excite me. My time at [Simply Home](http://simply-home.com) taught me how to use information from networked devices to change people's lives. Viewing social media as a distributed system of human sensors lead to an exploration of twitter as an indicator for disease spread at [Fountin](http://fount.in). Both of these projects are the driving motivation for my Ph.D. work.

What I'd like to convince you of through this post is that data aggregration, though important, is really only the first step.

Distributed systems, at least to me, can be viewed as platforms to inform all sorts of decisions. Analytics are really awesome at generating data, but these tools have a hard time automating insights. I haven't seen a system that is able to relieve users from having to constantly search and monitor for trends or edge cases. I believe tools should remove the fatigue associated with that responsibility and replace it with the opportunity to explore the data and augment (read: train) the feedback that the system provides.

![Boundary](http://www.underconsideration.com/brandnew/archives/boundary_logo.gif)
Along these lines, I'd like to use [Boundary](http://boundary.com) as an example since it helps me scale. Essentially, their product allows developers to map the topology of distributed applications fast, so we can focus on harder things. 

#### Here is <font style="color:#D7003E; font-weight:bold">Boundary</font> from a 50k foot view
They do a great job of introducing their product. If you want to monitor the performance of a distributed system, take the time to learn about them [here](http://boundary.com/why-boundary/).
___________________
![Boundray's Workflow](https://boundary.com/wp-content/uploads/2012/05/home-how-it-works-product.png "Boundary's beautiful logo")

In a nutshell you want to use Boundary because distributed systems communicate a lot and that communication is often the bottle neck wrt performance. Boundary enables me to

1. Continuously measure how [much] systems communicate.
2. Identify bottlenecks or edge cases [kind-of] .
3. Handle bottlenecks or edge cases.

Again, Boundary does most of the heavy lifting, leaving you with an organizational task of sifting through the data.


#### Here is how to deploy <font style="color:#D7003E; font-weight:bold">Boundary</font>
___________________

Their product is dead simple. Deploy their tools on the machines you want to analyze (I use [puppet](http://puppetlabs.com/blog/introducing-puppet-labs-boundary-module/) for personal projects, [chef](https://github.com/boundary/boundary_cookbooks/tree/master/apps) for work.)

#### Setup <font style="color:#D7003E; font-weight:bold">Boundary</font> 
___________________
Currently, Boundary is bulit to allow you to take your system and:

1. Monitor
2. Test
3. Scale

What I would love to see happen with the platform is that the data available to Boundary becomes a training bed for all sorts of machine learning to augment system monitoring.


#### <font style="color:#D7003E; font-weight:bold">Boundary</font> with crumbtrails.
___________________
At [Ricon 2012](http://basho.com/community/ricon2012/) Dietrich talked about putting data into context. The knowledge of a system's architecture helps developers understand what's happening, why, where and when. Something I'd really love to see Boundary do is to allow developers to log events in their code (something akin to [Twitter's Zipken](http://engineering.twitter.com/2012/06/distributed-systems-tracing-with-zipkin.html)).

![Twitter's Zipkin](http://4.bp.blogspot.com/-b0r71ZbJdmA/T9DYhbE0uXI/AAAAAAAAABs/bXwyM76Iddc/s1600/web-screenshot.png)

A tool like this, baked into Boundary, would allow the system to learn how the individual connections within the application layers affect network utilizations.  More importantly, with this level of organization comes context that can be shared among teams of developers.

####  <font style="color:#D7003E; font-weight:bold">Boundary</font> Tails.
___________________
![Tail Distributions](https://controls.engin.umich.edu/wiki/images/b/bd/Tails.gif)
From a DevOps standpoint there are a number of ways to configure server clusters. Each configuration gives rise to different interactions for edge cases. This is not fun to debug under load or scale, but they are perhaps the most important metric of a functioning system.  If you can guarantee the edge cases, then everything else is bounded.

Boundary allows you to programmatically define which apps are running on your node, listening to which ports. With this model you're able to capture application specific traffic across clusters (independent of how it's setup), which is pretty fantastic. That got me thinking, wouldn't it be great to get tail distributions?  I'd love to see how different parts of my application are performing (on average) in the 99%, 99.9%, 99.99%, 99.999% cases.

And while those are being calculated, why not have the system automagically alert me of performance wins/loses as those running values change? Provide hooks where I can detect irregular or unresponsive traffic?

####  <font style="color:#D7003E; font-weight:bold">Boundary</font> as an online, machine learning platform.
___________________
![UI for machine learning](/static/images/time-series.jpeg)
We're starting to see the evolution of a well contained eco-system for a machine learning platform. I would love to see a simple selection mechanism like above. 

With Boundary's data, a UI  where users are able to highlight periodicities or patterns and then monitor or search for them would be incredibly valuable. Users could begin to explore their data actively in the future with these patterns and comparisons with these patterns could be used to drive other decisions.

With a mechanism like this, the representation of dynamic systems can evolve with use, be shared between developers or support teams to drive understanding of how software is interacting in the field. 

####  <font style="color:#D7003E; font-weight:bold">Boundary</font> + crowdsourced intelligence
___________________
It's tricky to explain how I envision Boundary working as a crowdsourcing agent w/out screenshots or designs, but there are really two main ideas at play here.

1.By giving developers tools to identify patterns of interest, Boundary is essentially generating a curated knowledge base to validate the ML techniques. With validated models, Boundary can begin driving new initiatives with user experience as they delight their users with clusters of acceptable/unacceptable runtime behavior for a given type of setup.

2.These tools could also drive collaboration (read: engagement in business speak). Given a platform to create content (these patterns that we're looking for) we'd be able to analyze systems together, more importantly share insights through reuse. Just as Github federated code development and made version control enjoyable, I feel like Boundary's pretty well placed to drive the same innovation with system scaling and monitoring.
