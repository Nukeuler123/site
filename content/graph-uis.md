+++
title = "Graph UIs"
date = 2023-05-12

[taxonomies]
tags = ["rust","UI"]
+++

Making graph-based user interfaces that look like something straight out of Blender in Rust is no easy feat. I've been working on developing one for my machine learning project over the past few days, and let me tell you, it's been a challenge. The tricky part isn't actually drawing and creating the graph. No, the real challenge lies in executing the code that the graph represents.

<!-- more -->

{{ image(src="/img/shader_graph.png",
         position="left") }}
[Thanks to blender for this image](https://docs.blender.org)

So, what's the deal with this graph-based UI stuff? Well, it's all about dealing with nodes that have different sets of inputs and outputs, all of which can be totally different types. And that's not even the half of it, some of these nodes rely on other nodes to run first, so you have to make sure to run all the dependent nodes in the right order. Before you know it, things start getting real complicated, real fast.

So, you're probably wondering how I've been tackling this whole graph-based UI problem. My solution? Traits, hashmaps, mutexes, arcs, and [Anymap](https://crates.io/crates/anymap). I started by creating a Node trait, which gets held in an Arc+Mutex. This lets the nodes push their computed data to their output nodes. To store all this data, I'm using a Hashmap+Anymap combo. The anymap holds the value while a special "slot" number is used as the key. It's all a bit of a wild ride, but hey, it seems to be working so far!

Now that we've got data flowing smoothly between nodes, the big question is: how do we actually execute the code? And to be honest, I haven't totally figured that out yet. One idea I had was to go through each node and the nodes it depends on, and create a list of nodes to execute one after another. Or, we could have each node run its input nodes, compute, push to output nodes, and then run its output nodes, kinda like recursion. But there's a catch – this approach could easily create a recursion loop unless we keep track of what nodes have already been executed.

So that's where I'm at with this whole graph UI thing. It's been a wild ride, but I'm learning a ton and making progress. As for the best approach to executing the code, I'm still experimenting and exploring different options. But hey, that's all part of the fun, right?....right?