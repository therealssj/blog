+++
title = "Obelisk Konsens-Algorithmus Design-Beweggründe"
tags = [
    "Obelisk",
    "Consensus",
    "Skywire",
]
date = "2017-10-26"
categories = [
    "Statement",
]
bounty = 20
+++

*Dies ist ein archivierter Post aus dem Bitcointalksthread vom 19. Juni 2014.*

> Zitat von: yxxyun am 19. Juni um 02:52:38 morgens

>> Zitat von: skycoin am 19. Juni 2014 um 02:31:59 morgens

>>> Zitat von: FrictionlessCoin am 18. Juni 2014 09:15:07 abends

>>>> Zitat von: skycoin am 18. Juni 2014 um 09:08:56 abends

>>>> Entwicklungsupdate:

>>>> Wir haben einen Weg herausgefunden, wie Sybil-Attacken durch die Verwendung 
     eines hybriden Proof-of-Stake-Systems verhindert werden können.
     
>>>> Um einen Knoten zu erstellen, muss man erst beweisen, dass man Coins besitzt. 
>>>> Sagen wir 10 Coins. Man sendet 10 Coins zu Adresse A. Dann sendet man 10 Coins
>>>> von Adresse A zu Adresse B. Dann führt man eine Signature hinzu, indem man den 
>>>> öffentlichen Schlüssel von A nutzt um die Nachricht in seiner 
>>>> Obelisk-Blockchain zu signieren.

>>>> Alternativ kann man seinen öffentlichen Schlüssel für die Adresse A bekanntgeben
>>>> und dann einfach eine Nachricht mit diesem öffentlichen Schlüssel signieren.
>>>> Der Knoten muss dann in einem bestimmten zeitlichen Intervall, oder innerhalb einer 
>>>> bestimmten Anzahl von bewegten Reserve-Blöcken eine Signatur bekanntgeben, um 
>>>> die Vertrauensbeziehung mit anderen Peers aufrecht zu erhalten.

>>>> Alternativ kann man Proof of Burn erfordern (Beweis durch verbrennen), bei dem
>>>> die Coins von Adresse A zu Adresse B gesendet werden, für welche kein privater
>>>> Schlüssel bekannt ist. Proof of Burn kollidiert aber mit dem Vorsatz, dass niemand 
>>>> die gesamte Blockchain herunterladen muss um einen Knoten laufen lassen zu können,
>>>> ist also eher unwahrscheinlich.

>>>> Dieses System begrenzt die Anzahl von Obelisk-Knoten nach oben und beschränkt
>>>> die Fähigkeit Obelisk-Knoten laufen zu lassen auf Coin-Besitzer.
>>>> Die obere Grenze der Anzahl der Knoten und die Coin-Bedingungen fügen eine 
>>>> weitere Schicht gegen die Sybil-Attacke hinzu.

>>>> Bin mir nicht sicher, wie das eine Sybil-Attacke verhindern soll.
>>>> Fügt ihr nicht einfach nur Kosten für das Hinzufügen eines Knoten zum Netzwerks hinzu 
>>>> und deshalb verursacht eine Sybil-Attacke finanzielle Kosten?

>>>> Dies ist aktuell nur eine Idee. Habe eine Verbesserung gefunden. Jeder Obelisk-Knoten 
>>>> hat einen öffentlichen Schlüssel. Wir hashen diesen öffentlichen Schlüssel
>>>> zu einer Adresse und diese speichert dann 10 Coins in einer Ausgabe, 
>>>> welche von dieser Adresse besitzt wird.

>>>>

>>It does not add a cost. It just proves that you own 10 coins. It proves you
>>know the private key, for a public key, whose address has 10 coins in it. You
>>can still spend the coins.

>>The idea is that it upper bounds the number of nodes. If 10 coins must be
>>held and there are 100 million coins, then it upper bounds the network at 10
>>million nodes. The upper bound does not appear to be mathematically useful
>>right now, but is something we should keep in mind.

>>When a new Obelisk node is run, it will "trust" some random peers. The user
>>can also add a few nodes by hand that it trusts (exchanges or trusted
>>community members). A node is identified by its public key hash and found by
>>DHT. Its not like Bitcoin where nodes are IP:port pairs. You can move your
>>computer around and the identity of the node does not depend on its IP
>>address.

>>We want the network to be secure with random nodes being chosen. We dont want
>>a situation like Ripple, where the three developers nodes control the
>>network. However, we wanted to prevent a situation, where someone runs
>>200,000 nodes and tries to collect the trust relationships from new users.
>>These Sybil attacks nodes, still cannot 51% attack generally, but anything
>>that increases the cost of the attack is still useful.

>>Maybe, we restrict it so that new user will only randomly trust nodes that
>>have a coin balance. Trust relationships wont be severed if the node does not
>>have a coin balance, but they just wont get new random users.

>>The connectivity graph for trust relationships, is supposed to be a fully
>>connected random graph. A few nodes (trusted community members, exchanges,
>>websites, organizations) will have more trust relationships and that helps
>>the convergence time for block consensus a bit. It reduces the network
>>diameter a bit.  Some nodes will be used to verify consensus (you choose a
>>bunch of exchanges or different public keys), these nodes do not affect
>>consensus decisions, but are "consensus oracles" to check if your node has
>>converged with network.

>>If two large exchanges have different consensus for a particular, block, that
>>is a problem. It could indicate a netsplit or an attack on the network.
>>Exchanges may want to suspend trading until the issue is resolved.

>Obelisk is skycoin's distribute consensus node? I was think the skycoind is
>the node...

Yes.

Skycoin has a blockchain. The blockchain is in
https://github.com/skycoin/skycoin/tree/develop/src/coin. This parses the
blocks and deals with unspent outputs and transactions.

Skywire is the daemon and has a "service architecture". It can run services,
such as blockchain syncing service and other things. The meshnet is currently
being implemented as a service on top of Skywire (although this may need to
change).

The consensus mechanism is outside of the blockchain. Obelisk nodes (which will
probably will be implemented as a Skywire service) have a blockchain.
Each node has a public key. The public key identifies the Obelisk node.
Each Obelisk node has its own blockchain (there are no coins in this chain).
The node creates a new block and signs it with its private key.
The Obelisk blockchains are used to negotiate consensus (determining the head
block in the Skycoin blockchain). Obelisk uses Ben-Or's for randomized
consensus. Each Obelisk node has a list of other nodes it subscribes to.
Those nodes influence consensus and voting decisions for the local node.
For non-pathological network topologies, the local consensus provably converges
in to a global consensus.

Each node votes on the next block in the chain. A node proposes the next
block and the nodes vote on the successor. The votes are published in the
blocks in the Obelisk blockchain for each node. Your node votes randomly
between the alternative and flips its vote every once in a while. Once 40% of
your peers (the nodes you are subscribed to) have reached a consensus, you
switch to that candidate. The network can vote on multiple forks at once, it
does not slow down waiting for a consensus. The forks are pruned to a single
chain over time. Splits of two or three block are normal, but after a few
confirmations the probability of the block being reverted decreases
exponentially to zero. If a transaction has been executed on all candidate
chains, then it is essentially executed, even if the particular consensus chain
has not been decided yet.

That is binary Ben-Or's and Skycoin will use something slightly more advanced,
that is faster when there are multiple successor blocks to choose from in the
consensus set. Randomization is important to keep sub-graphs of the network
from getting stuck. The voting process is a form of "annealing" where each
node will arrive at the global consensus independently, only from its local
information.

The consensus process happens in public. A node publishes blocks, signs them
with their private key and the blocks are replicated peer-to-peer between
subscribers of the chain. Then there are "consensus oracles" which are nodes
that are used to verify consensus but do not influence consensus. So you might
choose the public keys of a few exchanges and a few trusted community members
and your node will use those to detect if something is wrong. This is used to
detect netsplits. This also protects against an attack, where a hacker
controls your router and can control the peers you are able to connect to.

If a node shows up to network and tries to get the network to accept a
different chain (51% attack, reverting transactions), it usually gets ignored.
Most 51% attacks require malignant node behavior which is automatically
detected and results in a subscribing node removing the malignant node from
their trust list. The easiest 51% attack strategy is easy to detect and prove
with mathematical certainty that it was intended as an attempt to revert
transactions, because it require backdating block consensus decisions.
It requires publishing two signed blocks with the same sequence number,
so we just made this an automatically bannable offence for a node.

We are trying to eliminate the last possible 51% attack, which is when a
subnetwork of nodes goes offline (netsplit attack) and then rejoins the
network with a different blockchain consensus and tries to force this on the
network to revert transactions. Most of these attacks will fail, because the
subnetwork will not have enough influence.

This attack is still very difficult to pull off. In case there is
a successful 51% attack, one solution is to freeze the network and let each node/user
individually choose which chain is the valid one and let people ban the attacking
nodes manually. The consensus oracle allows each node, with high probability, to
know if the state is synced and if global consensus has been reached or if
they are part of a netsplit subgraph. We think its possible for each node to
know with a high probability of correctness from local information, whether a
node was offline during a consensus decision and then ignore nodes that
were offline who suddenly appear and try to force a chain fork on the network.

In Bitcoin, if you have the most hashing power, you can revert transactions
whenever you want.

In Skycoin, to revert transactions:

- You much control a large number of nodes
- The nodes you control must be "influential" and trusted within the network
  topology
- Your nodes need to exhibit extremely blatant pathological attack behavior
  without the behavior being detected, because detection would result in losing
  the trust relationships you need to attack the network.
- Your nodes need to be in a pathological attack topology, without it being
  detected (most bot nodes will be trusted by very few humans and be very obvious)
- You must be able get the nodes you control to collude in a way that results
  in a successful attack (this is not very straightforward)
- If the attack succeeds, you must prevent the network from reverting the
  attack by hand (very difficult if people lost coins or money because of the
  attack)

To prove it iss 51% attack proof, you have to write down the assumptions you are
making and then create a simple mathematical model and then prove the
conditions under which things can and cannot happen in the model. Once you
know the conditions that an attack is possible under, you try to eliminate
them and if you cant eliminate them, you make them as difficult as possible.
You increase the cost of an attack and you reduce the probability that a
specific attack will succeed. Then you reduce the payoff and incentives for
the attack.

The consensus process is simple and easy to model, but unintuitive without
seeing it. There will be a javascript site eventually that has an animated
consensus process you can play with.
