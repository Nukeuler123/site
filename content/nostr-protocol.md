+++
title = "My new facination: Nostr"
date = 2023-05-06

[taxonomies]
tags = ["rust","nostr","decentralized"]
+++

# So what is nostr?
It stands for "Notes and Other Stuff Transmitted by Relays" and is a federation protocol. Its wire protocol is dead simple to understand and straightforward compared to ActivityPub. The protocol is also separated into NIPs (Nostr Implementation Possibilities), which are essentially add-ons that a server can broadcast if they support or not. From a programming perspective, this makes it easy to gradually implement parts of the protocol. For example, I'm currently working on a Rust-based Nostr server that only implements NIP-01 for now. Later on, I can easily add support for another NIP without much effort.

<!-- more -->

# What is NIP-01?
Nip-01 is essentially the "base" of the protocol and is required by all relays and clients. All other NIPs build upon this one. 

Here is a nice diagram of the protocol.

{{ image(src="/img/nostr-diagram.png",
         position="left") }}
[Thanks to Melvin Carvalho for the diagram used here](https://dev.to/melvincarvalho/the-nostr-protocol-nip01-5ach)

# Why this over Activity Pub?
This is where I get more opinionated, so maybe I'm missing something, but ActivityPub seems overly complicated to me. Although I understand what's going on, it's just too complex for my liking. That's why I prefer Nostr - it's a simple protocol at its core but can get as complicated as you need it to be. The NIPs allow the Nostr protocol to serve multiple roles while remaining compatible. For example, [NIP-28](https://github.com/nostr-protocol/nips/blob/master/28.md) lets users create public chatrooms similar to IRC or Discord, while [NIP-15](https://github.com/nostr-protocol/nips/blob/master/15.md) enables the creation of a marketplace to buy and sell items.

# Closing words
I see a lot of potential in the Nostr protocol and hope that it gains more adoption in the future."