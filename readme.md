# Bunsan Web: the decentralized Web 

## About Bunsan Web

"Bunsan Web" is decentralized web that forms an open network of
individual programs for freely sharing their information
with a foundation derived on the browser-side standard technologies of the Web.



## Sources of Bunsan Web

Source code repositories of Bunsan Web:

- [hashnet](https://github.com/anatta-project/hashnet/)
- [anatta-engine](https://github.com/anatta-project/anatta-engine/)
- [grp](https://github.com/anatta-project/grp/)

### hashnet

The `hashnet` is a system designed for building the foundation network
that the "events" for asynchronous programs can be 
decentralizedly published and consumed by everyone on the Internet.

The events on hashnet are different from ones of traditional event systems.
They are universal persistent data with no subscription to 
specific publishers or channels.

These events contains the `contexts` that represents the means of 
their contents.
For programs, the `contexts` provides the structure of its contents.
Publishers can `PUT` events with some `contexts` to the `hashnet`.
Consumers can asynchronously `GET` the events 
from the `hashnet` filtered with required `contexts` for their usage.

Each event publisher on the Internet has asymmetric key pairs
and their identities are based on the public key.
All events are `PUT` with sign by the keys, then 
events verified its sign with publisher key are valid on anywhere
for processing.

On the `hashnet`, 
everyone has the range of the valid events as its center is themselves.
A decentralized network is formed with merging the valid ranges each other.
The network peer itself is also an application system
built on the events of the `hashnet`.

This repository contains prototype implementation of a `hashnet` peer 
structure, simulation codes for events on inter-peer network and 
their result stats.
The peer implementation spawns a REPL UI with core objects
for calling methods to executing the peer functionalities.
It also contains "bookmark-sharing" event example and 
its GUI app on Electron.

### anatta-engine

The `anatta-engine` is a runtime environment for building systems on
a set of tiny asynchronous programs with
structuring based on URI and interacting via REST messaging.

The HTML DOM is applied as a primitive data structure of programs for
messages and their states.
It also adds an interface for accessing with the metadada instead of 
structured locators.
The engine realizes a program centric URI-space freely allocated by itself.
It enables seamless hyperlink accessing from their data and programs,
via local systems such as files or storage, to the universal Web.

This repository contains a runtime implementations on node.js and its examples.
The 
[anatta-engine-potluck](https://github.com/anatta-project/anatta-engine-potluck/) is an example application of the `anatta-engine` systems such as
comment sharing system for each Web pages.

### grp

The `grp` is a prototype implementation of the 
"Generic Reverse Proxy infrastructre" for tiny programs.

"Generic Reverse Proxy infrastructre" is independently available 
from the `anatta-engine` functionality of URI accessed programs.

It can access programs as a script on browser tab pages with URI.
It makes needless to implement specific brokers for each application 
structures on the cloud servers.

This repository contains reverse-proxy server on node.js, 
JavaScript library interface as the ServiceWorker's 
["fetch" event style client](https://developer.mozilla.org/docs/Web/API/FetchEvent#Examples) that implemented with WebSocket,
ant its examples.


## Architecture of Bunsan

See: [architecture.md](architecture.md)

## Mission of Bunsan

See: [mission.md](mission.md)

## A History of Bunsan

See: [history.md](history.md)

