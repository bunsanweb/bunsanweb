#  About decomposing features of `anatta-engine`

The `anatta-engine` is implemented as all-in-one runtime package 
for running application systems with node.js.
It can run scripts embedded in HTML,  
then these scripts affect `window`/`document` objects as their states,
even if they perform as Web servers.
The platform functionalities are implemented on backyard.
Some are accessible via asynchronous URI access, 
others are added as extra functions into `window` object 
(e.g. Elliptic-Curve cryptography).

We believe the real loosely-coupled network systems come from
URI-based asynchronous browser-side style of programming, 
not from layer-stacked synchronous server-side style.
Therefore, the `anatta-engine` is designed as 
Web Browser-side style programming anywhere
for all element in systems not limited only scripts in browsers.
Its implementation is based on the browser-side standards structures
(HTML DOM, CSS query, DOM Events, and 
some standard on these days e.g. `XMLSerializer`).

## Why decompose each feature of `anatta-engine` package

Not only total package, 
but each concept of `anatta-engine` is also useful to 
decentralization for the Web.
It is to say that the "Bunsan Web" is 
made on union set of decentralization technologies.

On the current Web world, there are two directions of struggles.
One is toward centralization, the other is toward decentralization.
Both are formed with populating technologies
to enhance their directions.

Contributing decentralized side with applying these technologies,
it also becomes closer to the world towards the "Bunsan Web".

Now, browsers are much enhanced with standardized technologies.
However, these standard technologies were used both centralize or 
decentralize directions.
But the standard browser technologies are also enough 
to implement the features of `anatta-engine`.

We would implement each feature on the standard browser technologies directory.
They could independently be available on various browser scripts, 
not only for the "Bunsan Web".
Using these technologies  approaches to the "Bunsan Web".

## How to use standard technologies

It is important how to use standard technologies.
If a product would completely hide them on its backyard, 
they are just messy one.
The standard structures should be in front as much,
and implementation structures should also be hide as mush. 

In current standards, there are general useful structures such as
`EventTarget`, `Streams`, `Blob`, `Proxy`, `Request`,`Response`, and so on.
Features are provides as some of these generic objects
injected implementations inside.

One of profits providing interface as stardard object is
easily mixable to unknown/yet-unborn technologies.
The openness is important to build the decentralized world.

## "Generic Reverse Proxy" as a first decomposition

Programs on `anatta-engine` has ability of publishing their information 
as Web server style request/response. 
The `WebGate`(in `engine/webgate`) is as a transparent reverse proxy to
the `Space` object for real HTTP accesses.
The `Space` manages the Resources that includes 
user programs as `Agent` (in `engine/weaver`).
The `Agent` is loaded from source HTML with JavaScript.
It calls as the runtime scripts via DOM `Event` to the `window`
which includes "request" access from managed `Space`.

The "Generic Reverse Proxy"(`grp`) is implementing the relationship of
the transparent reverse proxy as `WebGate`
and the access event on `window` directly for browser scripts.
The transparent reverse proxy is not processing
request/response messages in the proxy server.
The browser scripts listen the access `Event` for 
processing each `Request` message to make a `Response` message to respond.

For providing the interface as standard objects,
The `ServiceWorker`'s `"fetch"` event structure is directly applied to 
the `grp` browser-side API. 
It can handle `"fetch"` access with`FetchEvent.respondWith(response)` 
with objects in the standard `fetch()` API: `Request`, `Response`.

The implementation uses `WebSocket` to connect the proxy
because the `WebSocket` can connect any machines not limited to CORS origins.
Proxy server is implemented simply as node.js HTTP server.

Unique identity of programs is based on 
EC(Elliptic Curve) cryptography public keys from random private keys.
The 3rd party ECC library is used inside implementation because of 
lack feature of WebCrypto standard (retrieve keys from only random bytes).

The `grp` is the first trial prototype to implement with the manner
such starndard structures as an interface of features.

## TBD(design of other features)

