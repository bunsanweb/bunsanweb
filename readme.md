# bunsanweb: the decentralized Web 

## About bunsanweb

bunsanweb is a decentralized web born in Tokyo which forms an open network of
individual programs that freely share information between them.
Its foundation is built on standard browser-side web technologies.
After years of private development we're finally ready to show the world what we've created.
We hope that you can help bunsanweb take a major step in its development.

### Special: Decentralized Web Summit 2018

We'd attending the
[Decentralized Web Summit 2018](https://decentralizedweb.net/science-fair).

We're working hard to prepare explanatory material about bunsanweb.
But we'd love for you to check out what we’ve created and leave any questions or comments you have.
We'd be happy to answer any questions on the [issue comments](../../issues/1).

## Resources

Source code repositories of bunsanweb:

- [hashnet](https://github.com/bunsanweb/hashnet/)
- [anatta-engine](https://github.com/bunsanweb/anatta-engine/)
- [grp](https://github.com/bunsanweb/grp/)

At first, technologies of "programming for the Web" concept is 
made as a single integrated package on node.js: `anatta-engine`.
We decompose it as each feature on direct browser-side standard technologies
to be available for a paradigm of any end-to-end style computing on the Web, 
not only for `hashnet` requirements. 
The `grp` is the first decomposed feature from `anatta-engine`. 

See more detail at: 
[features-from-anatta-engine.md](features-from-anatta-engine.md).

### hashnet

The `hashnet` is a system designed for building the foundation network
where "events" for asynchronous programs can be  published and consumed 
by everyone on the Internet in a decentralized manner.

Events on hashnet are different from those of traditional event systems.
They are universal persistent data with no subscription to 
specific publishers or channels.

These events contains `contexts` that represents the means of 
their contents.
For programs, the `contexts` provides the structure of its contents.
Publishers can `PUT` events with some `contexts` onto the `hashnet`.
Consumers can asynchronously `GET` events 
from the `hashnet` filtered with required `contexts` for their usage.

Each event publisher on the Internet has asymmetric key pairs
and their identities are based on their public keys.
All events are signed by their key when they are `PUT` onto `hashnet` 
therefore events are considered valid based on this signature.

On the `hashnet`, 
everyone has the range of the valid events as itself as center.
A decentralized network is formed by merging the valid ranges with each other.
The network peer itself is also an application system
built on the events on the `hashnet`.

This repository contains prototype implementation of a `hashnet` peer 
structure, simulation codes for events on inter-peer network and 
their result statatistics.
The peer implementation spawns a REPL UI with core objects
for calling methods to execute peer functionalities.
It also contains a "bookmark-sharing" event example and 
an Electron GUI app.

### anatta-engine

The `anatta-engine` is a runtime environment for building systems on
a set of tiny asynchronous programs with
structuring based on URI and interacting via REST messaging.

An HTML DOM is applied as a primitive data structure of programs for
messages and their states.
It also adds an interface for accessing with the metadata instead of 
structured locators.
The engine realizes a program centric URI-space freely allocated by itself.
It enables seamless hyperlink access of their data and programs,
via local systems such as files or storage, to the universal Web.

This repository contains a runtime implementations on node.js and its examples.
The 
[anatta-engine-potluck](https://github.com/bunsanweb/anatta-engine-potluck/) is an example application of an `anatta-engine` systems which
provides a comment sharing system for webpages.

### grp

The `grp` is a prototype implementation of the 
"Generic Reverse Proxy infrastructure" for tiny programs.

"Generic Reverse Proxy infrastructure" is available independently
from the `anatta-engine` functionality of URI accessed programs.

It can access programs as a script on browser tabs with URIs.
It makes needless to implement specific brokers for each application 
structures on the cloud servers.

This repository contains a reverse-proxy server on node.js, 
JavaScript library interface as the ServiceWorker's 
["fetch" event style client](https://developer.mozilla.org/docs/Web/API/FetchEvent#Examples) implemented with WebSocket,
and its examples.

## Contact us

We want to hear from you about bunsanweb. We have an open thread in Issues which we are actively monitoring where you can leave [your questions and comments](../../issues/1)..We look forward to hearing from you!

## Architecture of bunsanweb

See: [architecture.md](architecture.md)

## Mission of bunsanweb

See: [mission.md](mission.md)

## A History of bunsanweb

See: [history.md](history.md)

