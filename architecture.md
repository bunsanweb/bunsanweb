# Architecture of Bunsan

Essentially the Web forms single document network on that
documents can be linked over their server boundaries,
and everyone can freely use them via any route with browsers.

Bunsan put a different programming architecture on its fundamental.
With the architecture, 
both providers and users of programs can 
make relationships freely connectable 
on a universal network such as the Web.

**Program** on Bunsan is defined as an entity which can asynchronously 
access to other **program**s with their URIs.
For realizing these **program**s, it is required a mechanism for
interacting with repeatedly callings other programs
through hyperlinked URIs in **document**s 
that also passed by the programs accessed with such URIs.
On Bunsan, to achieve the mechanism, 
its technologies are designed as extended of
the browser side standard Web technologies,
not server-side ones.

For asynchronous entry points of driving these **program**s,
Bunsan offers the **hashnet**; network of universal events.
On the **hashnet**, event consumers are not restricted by 
specific targets as event publishers or event queues.
A model of the **hashnet** is only publishing and subscribing to 
the single target; **hashnet**.

Here, these **program**s work on the architecture such as
PUT-ting **event**s to the **hashnet** and GET-ting **event**s from the **hashnet**.
Because one that has GET **event**s processes them depending on these contents,
the relationship between **program**s PUT **event**s 
and **program**s GET **event**s
is sharing based on the information; 
**contexts** that state what content of the **event** is.

This **hashnet** is realized with cooperated dispersed **peer**s.
Each peer has a self **event** queue.
At first, the **hashnet** is locally established 
as a single **event** queue of a standalone peer itself.
Any interactions between dispersed peers 
are realized as such application systems on the **hashnet** that 
use **event**s on the **hashnet**
which include required information for these interactions.

Forming a network between peers 
is also the same type of a system based on **event**s of the **hashnet**.
For example, when a new peer is added to the network by a existing peer, 
the existing peer shares information of the new peer addition 
as an event to **hashnet**.
Appropriately processed "following" the new peer by each peer on the network, 
the network also goes well as the universal event queue with new added peers.
As same manner, the **hashnet** is self extensible as dispersed systems,
e.g. a package distribution system,
with introducing new content properties of **event**s and
these processing programs on each peer.


The **event**s are signed and verified with the asymmetric key.
Because the public key for the verification is correspond with 
the identity of the publisher of the **event**,
The contents of **event** are trusted as published by the publisher itself.
The linked URIs embedded in contents of the **event**s are also trusted.
To check information from the linked URIs in the **event** 
with the values in the same **event**,
trust to the URI target can be automatically manifested with the **event**.
For example, order of event sequence would be guaranteed by 
"the former events" URIs in each **event**.

With link relationships over signers of these events,
it provides a chain of trust to URIs started from each event publisher.
Peer interactions over the **hashnet** 
such as "adding a new peer to the network" 
consist on the expanded chains of trust. 
Bunsan provides chains of trust on the **hashnet**,
just as sharing embedded links in signed **event**s.
Processing on the trust chains,
the systems on the **hashnet** can judge any relationship 
in dispersed Resources, including programs, events, data sets, and peers.


