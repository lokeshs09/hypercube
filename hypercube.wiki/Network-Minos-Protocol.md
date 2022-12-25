# Minos Protocol

When communicating with nodes in the control plane, the Minos Protocol (MINO) is used as a gateway. The service is used by miners to ensure that information is available to all other nodes in a cluster of computers. The MINO protocol is used by the service to disseminate information.

## Protocol Overview

It is necessary for nodes to transfer signed data objects among themselves in order to run a cluster on an ongoing basis. They may, for example, share their contact information, ledger height, and voting preferences with others.
Every tenth of a second, each node transmits a "push" message and/or a "pull" message to the rest of the network. It is possible that push and pull messages will elicit answers, and that push messages will be forwarded on to other nodes in the cluster as well.
MINO runs on a well-known UDP/IP port, or on a port in a well-known range, and it is easy to remember. Once a cluster has been booted up, nodes communicate with one another about where to find their MINO endpoint (a socket address).

## MINO Records

It is not necessary to sign or version (with a date) records shared over MINO in order for them to be understandable by the node that is receiving them. Whenever a node receives two records from the same source, it replaces the oldest record with the most recent record with the latest timestamp.

## Protocol Interface

### PUSH Message

A node sends a push message to tells the cluster it has information to share. Nodes send push messages to PUSH_FANOUT push peers.

### PUSH Peers, PRUNE Message

A nodes selects its push peers at random from the active set of known peers. The node keeps this selection for a relatively long time. When a prune message is received, the node drops the push peer that sent the prune. Prune is an indication that there is another, higher stake weighted path to that node than direct push.
The set of push peers is kept fresh by rotating a new node into the set every PUSH_MSG_TIMEOUT/2 milliseconds.

### PULL Message

A node sends a pull message to ask the cluster if there is any new information. A pull message is sent to a single peer at random and comprises a Bloom filter that represents things it already has. A node receiving a pull message iterates over its values and constructs a pull response of things that miss the filter and would fit in a message.

A node constructs the pull Bloom filter by iterating over current values and recently purged values.
A node handles items in a pull response the same way it handles new data in a push message.

### PURGING

Nodes retain prior versions of values (those updated by a pull or push) and expired values (those older than MINO_PULL_BLCKTHRD_TIMEOUT_MS) in purged_values (things I recently had). Nodes purge purged_values that are older than 5 * MINO_PULL_BLCKTHRD_TIMEOUT_MS.

