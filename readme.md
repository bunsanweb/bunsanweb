# Bunsan Web: the decentralized Web 

## About Bunsan Web

"Bunsan Web" is a decentralized web that forms an open network of
individual programs for freely sharing their information
with a foundation derived from browser-side standard technologies of the Web.

## Sources of Bunsan Web

Source code repositories of Bunsan Web:

- [anatta-engine](https://github.com/anatta-project/anatta-engine/)
- [Hashnet](https://github.com/anatta-project/hashnet/)
- [grp](https://github.com/anatta-project/grp/)

### anatta-engine

The `anatta-engine` is a runtime environment for building systems on
a set of tiny asynchronous programs with
structuring based on URI and interacting via REST messaging.

The HTML DOM is applied as a primitive data structure of programs for
messages and their states.
It also adds an interface for accessing metadata instead of 
structured locators.
The engine realizes a program centric URI-space freely allocated by itself.
It enables seamless hyperlink accessing from data and programs,
via local systems such as files or storage, to the universal Web.

This repository contains a runtime implementations on node.js and its examples.
The 
[anatta-engine-potluck](https://github.com/anatta-project/anatta-engine-potluck/) is an example application of the `anatta-engine` systems such as
comment sharing system for each Web pages.

### hashnet

The `hashnet` is a system designed for building the foundation network
where "events" for asynchronous programs can be published 
in a decentralized manner and be consumed by everyone on the Internet.

The events on hashnet are different from those of traditional event systems.
They are universal persistent data with no subscription to 
specific publishers or channels.

These events contains `contexts` that represents the means of 
their contents.
For programs, `contexts` provides the structure of its contents.
Publishers can `PUT` events with some `contexts` onto the `hashnet`.
Consumers can asynchronously `GET` events 
from the `hashnet` filtered with required `contexts` for their usage.

Each event publisher on the Internet has asymmetric key pairs
and their identities are based on public keys.
All events are `PUT` with sign by the keys, then 
events verified its sign with publisher key are valid on anywhere
for processing.

On the `hashnet`, 
everyone has the range of the valid events as itself as the center.
A decentralized network is formed by merging the valid ranges with each other.
The network peer itself is also an application system
built on the events of the `hashnet`.

This repository contains a prototype implementation of a `hashnet` peer 
structure, simulation codes for events on inter-peer network and 
their result states.
The peer implementation spawns a REPL UI with core objects
for calling methods to executing the peer functionalities.
It also contains "bookmark-sharing" event example and 
its GUI app on Electron.

### grp

The `grp` is a prototype implementation of the 
"Generic Reverse Proxy infrastructre" for tiny programs.

"Generic Reverse Proxy infrastructre" is available independently
of the `anatta-engine` functionality of URI accessed programs.

It can access programs as a script on browser tab pages with URI.
It makes needless to implement specific brokers for each application 
structures on the cloud servers.

This repository contains reverse-proxy server on node.js, 
JavaScript library interface as the ServiceWorker's 
["fetch" event style client](https://developer.mozilla.org/docs/Web/API/FetchEvent#Examples) implemented with WebSocket,
and its examples.


## Architecture of Bunsan

See: [architecture.md](architecture.md)

## Mission of Bunsan

See: [mission.md](mission.md)

## A History of Bunsan

See: [history.md](history.md)

