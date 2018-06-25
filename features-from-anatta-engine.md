#  Features split out from the `anatta-engine`

The `anatta-engine` is implemented as an all-in-one runtime package 
for running application systems with node.js.
It can run scripts embedded in HTML,  
these scripts then affect `window`/`document` objects as their states,
even if they perform as Web servers.
The platform functionalities are implemented on backyard.
Some are accessible via asynchronous URI access, 
others are added as extra functions into `window` object 
(e.g. Elliptic-Curve cryptography).

We believe real loosely-coupled network systems come from
URI-based asynchronous browser-side style of programming, 
not from layer-stacked synchronous server-side style programming.
Therefore, the `anatta-engine` is designed as a
Web Browser-side style programming 
for all element in systems not limited to only scripts in browsers.
Its implementation is based on browser-side standards structures
(HTML DOM, CSS query, DOM Events, and 
some standard on these days e.g. `XMLSerializer`).

## Why split out each feature of the `anatta-engine` package

Each individual concept of the `anatta-engine` is useful for the 
decentralization of the Web, not just as a complete package.
The "Bunsan Web" is 
made by combining a number of decentralization technologies.

In the current Web world, there are two directions in conflict.
One is toward centralization, the other is toward decentralization.
Both are populated by technologies
to enhance their directions.

By contributing these decentralized technologies,
we hope the world moves towards the "Bunsan Web".

Now, browsers are much enhanced with standardized technologies.
However, these standard technologies were used to both centralize and 
decentralize the web.
But standard browser technologies are also enough 
to implement the features of `anatta-engine`.

We would implement each feature on the standard browser technologies directory.
They could independently be available on various browser scripts, 
not only for the "Bunsan Web".

## How to use standard technologies

It is important how standard technologies are used.
If a product would completely hide them on the backend, 
the product becomes an opaque mess.
The standard structures should be in front as much as possible,
and implementation structures should also be hidden as much as possible. 

In current standards, there are general useful structures such as
`EventTarget`, `Streams`, `Blob`, `Proxy`, `Request`,`Response`, etc.
Generic objects are provided as is with features injected inside as requested.

One of the benefits of providing an interface using stardard objects is
the ability to easily mix unknown/yet-unborn technologies with existing technologies.
This openness is important to build a decentralized world.

## "Generic Reverse Proxy" as a first decomposition

Programs on `anatta-engine` have the ability to publish their information 
as Web server style request/response. 
The `WebGate`(in `engine/webgate`) is as a transparent reverse proxy to
the `Space` object for real HTTP access.
The `Space` manages Resources that includes 
user programs like `Agent` (in `engine/weaver`).
The `Agent` is loaded from source HTML with JavaScript.
It calls the runtime scripts via DOM `Event` of the `window`
which includes "request" access from managed `Space`.

The "Generic Reverse Proxy"(`grp`) implements the relationship of
the transparent reverse proxy as `WebGate`
and the access event on `window` directly for browser scripts.
The transparent reverse proxy is not processing
request/response messages in the proxy server.
The browser scripts listens for the access `Event` for 
processing each `Request` message to make a `Response` message to respond.

For providing the interface as standard objects,
The `ServiceWorker`'s `"fetch"` event structure is directly applied to 
the `grp` browser-side API. 
It can handle `"fetch"` access with`FetchEvent.respondWith(response)` 
with objects in the standard `fetch()` API: `Request`, `Response`.

The implementation uses `WebSocket` to connect the proxy
because the `WebSocket` can connect any machines not limited to CORS origins.
The proxy server is implemented simply as a node.js HTTP server.

The unique identity of programs is based on 
EC (Elliptic Curve) cryptography public keys from random private keys.
The 3rd party ECC library is used inside the implementation because of the
lack of features of WebCrypto standard (retrieve keys from only random bytes).

The `grp` is the first trial prototype to implement
such standard structures as an interface of features.

## TBD(design of other features)

