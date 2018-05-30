# Architecture of Bunsan

The Web essentially forms a single document network in that
documents can be linked over their server boundaries,
and everyone can use them freely via any route with their browsers.

Bunsan puts a different programming architecture over this fundamental concept.
With Bunsan, both providers and users of programs can 
make freely connectable relationships
on a universal network such as the Web.

A **program** on Bunsan is defined as an entity which can asynchronously 
access other **program**s with their URIs.
To realize these **program**s, one requirement is a mechanism for
interacting with repeated calls with other programs
through hyperlinked URIs in **document**s 
that are also passed by the programs accessed with such URIs.
On Bunsan, to achieve such a mechanism, 
its technologies are designed as an extension of
 standard browser-side Web technologies,
not server-side ones.

For asynchronous entry points that drive these **program**s,
Bunsan offers the **hashnet**; a network of universal events.
On the **hashnet**, event consumers are not restricted by 
specific targets such as event publishers or event queues.
A model of the **hashnet** is only publishing and subscribing to 
the single target; **hashnet**.

Here, these **program**s work on the architecture such as
PUT-ting **event**s to the **hashnet** and GET-ting **event**s from the **hashnet**.
Because one that has GET **event**s processes them depending on these contents,
the relationship between a **program**'s PUT **event**s 
and a **program**'s GET **event**s
is sharing based on information; 
**contexts** state the content of the **event**.

**Hashnet** is realized with cooperated dispersed **peer**s.
Each peer has its own **event** queue.
At first, the **hashnet** is locally established 
as a single **event** queue of a standalone peer.
Any interactions between dispersed peers 
are realized as application systems on the **hashnet** that 
use **event**s on the **hashnet**
which includes information required for these interactions.

Forming a network between peers 
is also the same type of a system based on **event**s on the **hashnet**.
For example, when a new peer is added to the network by a existing peer, 
the existing peer shares information of the newly added peer 
as an event to **hashnet**.
Appropriately processed "following" the new peer by each peer on the network, 
the network also acts as the universal event queue with newly added peers.
In the same manner, the **hashnet** is self-extensible and can be used as a dispersed system,
e.g. a package distribution system,
with introducing new content properties of **event**s and
these processing programs on each peer.

**Event**s are signed and verified with asymmetric keys.
Because the public key for the verification corresponds with 
the identity of the publisher of the **event**,
The contents of an **event** are trusted as being published by the publisher itself.
The linked URIs embedded in contents of the **event**s are also trusted.
To check information from the linked URIs in the **event** 
with the values in the same **event**,
trust to the URI target can be automatically manifested with the **event**.
For example, the order of events sequence would be guaranteed by 
"the former events" URIs in each **event**.

With link relationships over signers of these events,
it provides a chain of trust to URIs started from each event publisher.
Peer interactions over the **hashnet** 
such as "adding a new peer to the network" 
consists of expanding chains of trust. 
Bunsan provides chains of trust on the **hashnet**,
just by sharing embedded links in signed **event**s.
Processing on the chains of trust,
the systems on the **hashnet** can judge any relationship 
dispersed in Resources, including programs, events, data sets, and peers.


