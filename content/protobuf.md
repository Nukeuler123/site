+++
title = "Protobuf is pretty cool"
date = 2023-09-04

[taxonomies]
tags = ["rust","protobuf","protocols"]
+++

# What is a protobuf?
It's essentially a method to explain a protocol in a way that's easily understood by humans. What's particularly fascinating is that the "protobuf compiler" can subsequently generate code for your preferred programming language! This feature makes it completely language-agnostic, which is one of the reasons it's so remarkable.

<!-- more -->

# What I did before
Before stumbling upon the sheer awesomeness of protobuf, whenever I needed to devise a protocol, my go-to approach involved using enums and structs in conjunction with serde, the primary (de)serialization crate for Rust. This approach wasn't all that bad in itself.

However, let's consider a scenario where the project gains popularity, and others wish to create something that communicates using the same protocol. In such a situation, they'd need to unravel how serde (de)serializes those structs. But with protobuf, things have taken a turn for the better. Now, they can simply grab the '.proto' file and let the magic of the protobuf compiler craft their own version in their preferred programming language!

# It can be used to make a file format?
Given that the 'protobuf compiler' generates code that operates with bytes, it's both straightforward and supported to utilize this feature for creating a file format for your program, which can be stored on disk.

# GRPC
Another remarkable feature is the ability to define RPC 'services' within protobuf. The compiler will then take care of generating the necessary code to establish a server and client framework, complete with the defined services. Of course, the actual implementation of the functions is still required, but I must admit, this functionality is quite fantastic for creating straightforward client-server applications.

