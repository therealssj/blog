+++
title = "Obelisk: Der Skycoin Konsens-Algorithmus"
tags = [
    "Statement",
]
date = "2017-09-08"
categories = [
    "Statement",
]
+++

![Obelisk Der Skycoin Konsens-Algorithmus](/img/obelisk-the-skycoin-consensus-algorithm.png)

Die Skycoin-Blockchain nutzt einen neuartigen Typ eines Konsens-Algorithmus des Namens "Obelisk", welcher Proof of Work ("PoW") und Proof of Stake ("PoS") ersetzt.

Das Ziel der Entwickler von Skycoin war es, die wichtigen Sicherheitslücken und die "zentralisierenden Tendenzen", welche mit Blockchain-Netzwerken, die mit PoW oder PoS-Algorithmen funktionieren, verbunden sind und bei denen die Coinerschaffung mit einem Mining-Prozess verbunden ist, zu korrigieren. Skycoin versucht somit, eine Cryptowährung zu erschaffen, welche Satoshis originale Vision, eines absolut dezentralen digitalen Währungssystems, besser erfüllt.

Auf diese Weise schafft Skycoin ein Blockchain-Netzwerk, dass kein Mining-Erfordernis hat, feste Menge an Cryptotoken, zehnsekündigen Transaktionszeiten und besserer Sicherheit. In einem System, indem die Coinerstellung und die Kontrolle über das Netzwerk getrennt sind, verlieren Cryptotoken ihre politische Machtposition und beginnen mehr als eine Art unkomplizierter, digitaler Besitz betrachtet zu werden.

## Proof of Work und das Bitcoin-System

Es war eine fundamentale Fehlkalkulation in der frühzeitigen Programmierung von Bitcoin, dass der Mining-Prozess eine ökonomischen Anreiz bieten würde, der die Dezentralisierung vorantreiben würde.
Tatsache ist, dass die Verbindung zwischen Konsens und Hashing die Machtanreize, für das Kaufen der, sich stets-erhöhenden, Verarbeitungskapazität
Fakt ist, dass die Verbindung zwischen Konsens und Hashing dazu geführt hat, die Machtanreize, das Konsens-Netzwerk über die, sich stets-erhöhende, Verarbeitungskapazität zu kontrollieren erhöht hat.

Das Bitcoin-Netzwerk zum Bespiel ist de facto unter der Kontrolle von drei profitablen Mining-Pools, welche es geschafft haben eine große Menge der Hashpower des Netzwerks auf ihren Servern zu konzentrieren. Diese Pools haben begonnen, sich wie ein Kartell zu verhalten und die Hashpower untereinander über Vereinbarungen aufzuteilen. Die Verbindung zwischen Mining und der Kontrolle über das Netzwerk wurde bereits von Satoshi, als nicht-kryptographischen Hauptbedrohung der Stabilität des Netzwerks, identifiziert. Es erlaubt denen, welche genügend Rechenkraft ansammeln können, die Mehrheit der Hashrate zu erlangen und somit Transaktionen zu fälschen oder rückgangig zu machen - die 51% Attacke. Einige behaupten, dass diese Schwachstelle weniger dringend ist, da die Teilnehmer mit großer Hashrate glechzeitg großen Summen in Bitcoin investiert haben und ihr Überleben somit von dem hohen Wert des Coins abhängig. Dennoch ist die Fähigkeit, dass Netzwerk zu beeinflussen, stark konzentriert, was den Zweck einer, auf verteiltem Kontobuch (distributed ledger) basierenden, Cryptowährung verfehlt.

Der PoW-Algorithmus des Bitcoin-Netzwerks führt also zu Sicherheitsproblemen und zur Monopolisierung, durch das Verknüpfen der Macht über das Netzwerk mit der Person, die genügend ökonomische Ressourcen hat um den Mining-Prozess zu kontrollieren.

Dies impliziert, dass der Betrieb des Netzwerks betriebswirtschaftlich und ökolisch ineffizient ist. Die kontinuierliche Hinzuführung von Rechenkraft, die der Mining-Prozess verlangt, kostet große Mengen an Elektrizität, sowie monatliche Kosten in der Höhe von zweistelligen Millionenbeträgen. Diese Kosten können nur mit einem exponentiellen Zufluss von neuem Kapital zusammen mit neuen Usern gedeckt werden. Nur eine kleine Menge der fest etablierten Coins, wird es schaffen solch einen kontinuierlichen Zufluss zu generieren. Im Falle der meisten anderen PoW/PoS-basierten Coins, werden die Mining-Kosten durch das Abwerten des Coins gedeckt, solange bis aufgegeben wird.

> Aktuell besteht das Bitcoin-Wirtschaftssystem darin, dass neue User ihr Geld reinschmeissen und dieses Geld wird in einer Grube gesammelt und in einem Ritual den Elektrizitätskosten des Minings geopfert. Wenn der durchschnittliche User die Elektrizitätskosten der Miner direkt als Transaktionskosten bezahlen müsste, würde jede Bitcoin-Transaktion mehr als $50 kosten. Es wäre teurer als ein internationaler Banktransfer.

## Die zentralisierende Tendenz von Proof of Stake

Obwohl der Proof of Stake-Algorithmus das Sicherheitsproblem der 51%-Attacke angreift, sind sie sogar noch gefährdeter zur Zentralisation als PoW-Netzwerke. Bei PoS bestimmt der prozentuale Besitz einer Cryptowährung eines Partizipienten über dessen Authorität und Stimmgewalt bezüglich der Implementierung von technischen Veränderungen im Netzwerk. Partizipienten haben die Möglichkeit eine äquivalente Portion ihres Anteils zu minen, unabhängig ihrer Rechenkraft.

Dieses Prinzip erhöht die ökonomische Barriere eine 51%-Attacke zu starten signifikant, weil die finanziellen Kosten, eine Mehrheit der Tokens zu erwerben, sehr wahrscheinlich die potentielle Gewinne übersteigt. Wenn ein Angreifer es schafft die Mehrheit der Coins als Stakeholder zu besitzen, dann wird er am größten unter den Auswirkungen der Attacke, bezüglich der Stabilität des Netzwerkes sowie des externen Werts der Cryptowährung, leiden.


Yet, although raising the barriers to human-led attacks on the network, PoS
creates a centralizing impulse which is as strong as, if not stronger than, in
the case of PoW. As Joseph Young summarizes in his comparison of the two
systems at [coinfox.info](http://www.coinfox.info/), “A system where the major
stakeholder enjoys extensive control and authority over both technical and
economic aspects of the network creates a major monopoly problem.” While in PoW
voting on the implementation of technical changes to the network “is divided
among miners, developers and other crucial members of the community,” in a PoS
system “major stakeholders have a technical ability to make any changes they
like without considering the will of the community, businesses, miners and
developers. This centralisation of voting power and, essentially, control of
the network defeats the purpose of a distributed ledger-based cryptocurrency
since it contradicts its entire principle of distributing all elements within
the network to avoid the presence of a central authority.”

## Obelisk: Skycoin's distributed consensus algorithm

To tackle this centralization problem, Skycoin moves beyond PoW/PoS.
It uses a distributed consensus algorithm, called Obelisk, which
distributes influence over the network according to a “web of trust”. In
essence, every node has a list of other nodes that it subscribes to, and the
density of a node’s network of subscribers determines its influence on the
network. Each node is assigned a personal blockchain which acts as a “public
broadcasting channel” on which all of a node’s actions are visible and
publicly recorded. As all consensus decisions and communication occur through
the personal blockchains of each node, the community can very easily audit
nodes for cheating or collusion. How decisions on the network are made and
which nodes influence those decisions is completely transparent.

The public record left by each node’s personal blockchain allows the network
to react to defections by severing connections with less trustworthy or
malicious nodes, contracting the network to a smaller and denser core of
trusted nodes. Hence, in principle, if the community does not trust the nodes
representing them or feels that power within the network is too concentrated
(or not concentrated enough) the community is able to collectively shift the
balance of power in the network by collectively changing their trust
relationships in the network. The accountability of nodes to the community and
3rd party audits as well as the transparency of consensus strengthens
collective decision-making and thus introduces a highly democratic and
decentralizing element to the network.

This system provides for a digital currency system with significantly reduced
transaction times, no mining requirement, and greater security.

*Read more:*

* *[Skycoin Consensus Algorithm Whitepapers](https://www.skycoin.net/whitepapers)*
* *[Obelisk The Skycoin Consensus Algorithm | Information Pages](/overview/obelisk-skycoin-consensus-algorithm-information-pages/)*
