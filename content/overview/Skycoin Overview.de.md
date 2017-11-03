+++
title = "Skycoin Overview"
tags = [
    "Skycoin",
]
bounty = 15
date = "2017-08-26"
categories = [
    "Overview",
]
+++

<!-- MarkdownTOC autolink="true" bracket="round" depth="1" -->

- [Einführung in Skycoin](#skycoin-introduction)
- [Innovation und Fehler von Bitcoin und den gegenwärtigen Blockchain-Protokollen](#innovations-and-flaws-with-bitcoin-and-the-current-blockchain-protocols)
- [Innovation erzeugt von Bitcoin](#innovations-produced-by-bitcoin)
- [Größte Fehler von Bitcoin](#major-flaws-of-bitcoin)
- [Gewünschte Eigenschaften für Systeme des verteilten Konsens für digitale Konten](#desirable-properties-for-systems-of-distributed-consensus-for-financial-ledgers)
- [Skycoins Sicherheitsphilosophie](#skycoin-security-philosophy)
- [Transparenz und Sicherheit: Obelisk und öffentliche Verbreitungskanäle](#transparency-and-security-obelisk-and-public-broadcast-channels)
- [Obelisk](#obelisk)
- [Einfacher binärer Konsensalgorithmus: Auswählen zwischen zwei Blöcken](#simple-binary-consensus-algorithm-choosing-between-two-blocks)
- [Konsens auf mehreren konkurrierenden Zweigwahlen (branch choices)](#consensus-on-multiple-concurrent-branch-choices)
- [Consensus On Multiple Concurrent Branch Choices](#consensus-on-multiple-concurrent-branch-choices)

<!-- /MarkdownTOC -->

# Einführung in Skycoin

Skycoin basiert auf einer Technologie, welche neue kryptographische Primitive einführt, 
bekannt als ein öffentlicher Verbreitungskanal. Er führt ebenso die Implementation eines
neuen Konsens-Algorithmus ein, genannt Obelisk, welcher die verbundenen Probleme, die aus
dem Proof-of-Work-Konzept und dem Miningprozess entstehen, entschärft und eine Heerschar 
der, aus dem Mining resultierenden Sicherheitsprobleme, adressiert.
Obelisk ist nicht nur ein einfacher Algorithmus, sondern viel mehr eine Implementierung,
welche mittels mehrerer Techniken spezifische Sicherheiten garantiert.

# Innovation und Fehler von Bitcoin und den gegenwärtigen Blockchain-Protokollen

Bei Bitcoin werden neue Transaktionen in einem Block untergebracht, 
welcher dann an die Blockchain angeknüpft wird. Jeder Peer des Bitcoin-Netzwerkes
kann neue Blöcke generieren. Jeder Block hat deshalb genau ein Elternteil, aber mehrere
valide Nachfolger (Kinder). Die Kette (chain) formt einen Baum und das Kernproblem das Bitcoin
gelöst hat ist, dass sich alle Knoten im Netzwerk einig sind, welche der prospektiven Kette
dem Konsens entspricht.

Bitcoin nutzt eine Technik des Names Proof-of-Work (PoW) um eine eindeutige Blockchain zu 
bestimmen. Ein valider Block erfordert einen Hashwert, welcher unterhalb eines Zielknotens liegt. 
Knoten fügen Transaktionen zu einem neuen Block hinzu und wählen zufällig Nonces bis ein valider 
Hash für einen Block gefunden wurde.

Eine Funktion wird verwendet um absolute Ordnung unter den Ketten des Blockbaums zu schaffen. 
Die Kette mit der höchsten Schwierigkeit und die die meisten Hashingoperationen benötigt,
ist die "längste Kette" und formt die Konsenskette. Die Vorstellung der "Blocktiefe" und 
"Schwierigkeit" schaffen eine totale Ordnung über alle linearen Ketten des Blockbaumes und 
nur die ressourcenintensivsten Kette wird zur Produktion der Konsenskette akzeptiert.

Bitcoin-Knoten bauen Verbindungen untereinander zufällig auf, jeder Knoten übermittelt die
schwierigste ihm bekannte Kette seinen Peers. Wenn ein Knoten eine schwierigere Kette als ein
anderer verbundener Peer hat, dann erhält der Peer die Blöcke der Reihe nach in der richtigen 
Reihenfolge. Der Peer wird die Funktion evaluieren und entscheiden, ob die erhaltene Kette 
schwieriger zu produzieren ist und potentiell seinen Konsens für dieser Kette treffen.
Der Peer wird dann anschließend diese Kette seinen Peers anpreisen. Auf diese Weise wird der
Konsens durch das Netzwerk hindurchpropagiert und alle Knoten kommen zu einem Konsens.

Bitcoin geht nicht davon aus, dass die Knoten Identitäten haben und ehrlich sind.
Knoten dürfen anderen Knoten Daten senden und es kann den Konsens nicht beeinflussen,
denn die Konsensentscheidung ist etwas, dass unabhängig, alleine durch ihren eigenen Wert
getroffen werden kann.

# Innovation erzeugt von Bitcoin

### * Die Blockchain

Eine einzelne Datenstruktur die jeder besitzen kann.

### * Öffentliches Konto für Transaktionen

Speichern der finanziellen Transaktionen auf der Blockchain.

### * Nutzen von PoW und wiederholende Schwierigkeitsausrichtung um eine konstante Rate der Blockerschaffung zu gewähren

### * Nutzen der Hashes von öffentlichen Schlüsseln als Adresse

Öffentliche Schlüssel werden nicht bekanntgegeben, bis sie benutzt werden.

### * Nutzen der "Ausgaben" für Bilanzen

Es ignoriert den Versuch, teilbares digitales Geld zu erschaffen: 
Um $20 aus einer $25 Ausgabe zu bezahlen, sendet man $20 Dollar 
zu der Person und $5 zurück zu sich selbst.

### * PoW Schwierigkeitsfunktion und Blocktiefe

Erste Verwendung einer Funktion, welche eine totale Ordnung auf Blockbäumen 
definiert. Das öffentliche Konto umgeht das Problem der doppelten Ausgaben von 
traditionellem digitalen Geld.

# Größte Fehler von Bitcoin

Es gibt Probleme, welche bei der Entwicklung neuer Lösungen 
für kryptographische Währungen adressiert werden müssen.
Bitcoin sollte als Cryptowährung im Embryostadium betrachtet werden, 
bei dem sich die zukünftige Entwicklung verbessern muss. Die Technologie
auf der Skycoin basiert adressiert die großen Unzulänglichkeiten von Bitcoin, 
indem man sie das komplette System der verteilen Konsensfindung neu gestaltet.

### * Konsensentscheidungen in Bitcoin sind nicht endgültig und können umgekehrt werden

Eine Person oder Organisation, welche genügend Hashpower mieten kann, 
hat die Möglichkeit Transaktionen umzukehren.

### * Bitcoin erreicht Netzwerkkonsens aber individuelle Bitcoin-Knoten sind höchst gefährdet durch Gegner, welche den Router kontrollieren, durch den die Pakete wandern

Ein routerkontrollierender Gegner hat absolute Kontrolle über die Sicht 
eines Knotens und kann willkürlich die Konsensentscheidung des Knotens
beeinflussen.

### * Bitcoin-Exchanges sind hoch anfällig gegenüber Attacken geworden

Erfahrene Angreifen können 51%-Attacken durchführen und 
durch das Kaufen und Verkaufen von Altcoins auf Bitcoin-Exchanges
dieses in die Insolvenz treiben.

### * Banken und Wettseiten sind hoch anfällig gegenüber 51%-Attacken geworden

### * Sowie sich Bitcoin entwickelt, sind die Optionsscheine gegen Bitcoin und Attacken gegen das Netzwerk profitabler geworden

In der Zukunft könnten erfolgreiche Attacken gegen Bitcoin,
mit dem Handel von Optionsscheinen, Profite in der Höhe von 
hunderten Millionen Dollar erzielen.

### * Staaten mit hoher Kapitalverkehrskontrolle, sowie konkurrierende Unternehmen könnten das Bitcoin-Netzwerk direkt attackieren um ihre finanziellen Interessen zu wahren

Solche Instanzen können die Kosten für eine Netzwerkattacke 
mit Leichtigkeit stemmen und die Sicherheit von Bitcoin
untergraben.

### * Services welche "Cloud-Hashing" und das Mieten der Hashpower von Drittparteien anbieten sind zunehmend erfolreich

Viele große Pools haben nun die Möglichkeit Hashpower 
für eine Mehrheitsattacke zu mieten.

### * Hacker können zahlreichen Sicherheitslücken in Routern und Netzwerkequipment nutzen um Coins von Banken und Exchanges zu stehlen

Ein Angreifer kontrolliert die Peers die mit einem Bitcoin-Knoten
verbunden sind und kann sicherstellen, dass die Verbindung nur mit 
den von ihm kontrollierten Knoten aufgebaut wird. Zum Beispiel kann ein 
Angreifer eine Einzahlungstransaktion auf eine Seitenkette (side chain) 
einer Bank einbringen und die Bank dann dazu bringen, eine Abhebtransaktion 
auszugeben, welche anschließend an das Hauptnetzwerk weitergeleitet wird.

### * Bitcoin kann keine kostengünstige Sicherheit bieten

Das Bitcoin-Netzwerk nutzt eine immense und exponentiell 
wachsende Menge an Elektrizität. Bitcoins Sichheit beruht 
bewusst darauf, soviel Elektrizität als nur möglich zu verschwenden. 
Da die Sicherheit mit den Kosten verbunden ist, welche notwendig sind 
um die Mehrheit der Hashingpower zu erreichen, werden diese Kosten, das 
Bitcoin-Netzwerk zu betreiben, konstant nach oben getrieben.
In einem gut entworfenem System kostet $1 an Sicherheit $1000 um diese 
zu umgehen. Bei Bitcoin ist das Verhältnis $1 zu $1. Zusätzlich dazu ist
die ganze Sache umwelttechnisch unverantwortlich.

### * Bitcoin ist es grundlegend nicht möglich die Transaktionszeiten zu senken ohne die Sicherheit zu kompromittieren

Bitcoin-Transaktionen brauchen im Schnitt 10 Minuten um in einen 
Block integriert zu werden und mehr Zeit wird für höhere Sicherheit benötigt.


# Gewünschte Eigenschaften für Systeme des verteilten Konsens für digitale Konten

Die Kriterien, in welchen Bitcoin verbessert werden kann, sind folgende:

### * Keine doppelten Ausgaben

Sobald eine Transaktion ausgeführt ist, sollte es unmöglich sein den Konsens
rückgängig zu machen. Der Konsens sollte so unumkehrbar wie nur möglich sein.

### * Effizienz

Die Kosten ein perfekt abgesichertes Konto zu betreiben
sollten extrem niedrig sein.

### * Speed

Das System sollte Transaktionen innerhalb von Sekunden bestätigen.

### * Transparenz

Es sollte einfach sein bösartige Knoten zu überprüfen und zu identifizieren.

### * Routerattackensicherheit

Knoten sollten in der Lage sein zu erkennen,
ob ihr Konsens sich von dem des Netzwerks unterscheidet.

Einige Sicherheitseigenschaften sollten auch dann aufrechterhalten bleiben,
wenn die große Mehrheit der Knoten des Netzwerks bösartig und konspirierend ist.

Auf einem fundamentalen Level sind viele der angeborenen Sicherheitsprobleme
des Bitcoin-Systems verbunden mit dem Proof-of-Work-System und dem Miningprozess.
Seine Sicherheitsprobleme repräsentieren die generell auch real-vorkommende
byzantinische Problematik. Anreize existieren für Teilnehmer die Verifikationsprozesse zu 
manipulieren, beispielsweise mittels Bestechung und Hacking.
Angreifer werden den Systemtakt manipulieren, die Router kompromittieren, Hashkollisionen 
erzeugen, das Netzwerk mit hunderten und tausenden von Bots fluten um die 
Signaturgestaltbarkeit auszunutzen.

Ein sicheres System muss nicht nur gegen jede bekannte Attacke geschützt sein,
sondern auch robust genug sein um sich gegen zukünftige Attacken weiter zu entwickeln.
Einige der Problem von Bitcoin können behoben werden, wie etwa die Signaturgestaltbarkeit.
Andere Probleme sind fundamental und können nicht adressiert werden, ohne dass ein komplett
neuer Rahmen definiert werden muss, wie etwa die Verlässlichkeit von Proof-of-Work und den Minern.

# Skycoins Sicherheitsphilosophie

Sicherheit ist ein Prozess der kontunierlichen Identifikation und Befestigung gegen Bedrohungen.
Ein gutes System erreicht "tiefgehende Verteidigung", hat mehrere redundante Systeme und wird
das totale Versagen individueller Maßnahmen überleben. Gute Sicherheit benötigt die Unerscheidung
zwischen Bedrohung, welche existentiell sind und solchen, welche nur Belästigungen sind.

Während es offensichtlich ist das kein einzelnes System alle Sicherheitsrisiken eliminieren kann 
und gleichzeitig alle oben genannten Zielsetzungen erfüllen kann, repräsentiert Skycoin den nächsten 
Schritt in der Technologie der Cryptowährungen, denn es nutzt den bausteinförmigen Ansatz zum
Erreichen von Sicherheit und verwendet verschiedene Systeme, um diverse spezielle Garantien
geben zu können. Skycoins Sicherheit fokusiert sich auf die Adressierung der exisitierenden Bedrohungen,
welchen Bitcoin sich gegenübergestellt sieht, und dem Schutz der User vor alltäglichen Bedrohungen, 
im Versuch den höchsten Grad an Sicherheit gegen die Klasse von Attacken zu gewährleisten, welche
Stakeholdern, Insitutitionen und Usern den größten Schaden zufügen würde. Dies benötigt ein
komplettes neu gestalten von Bitcoin an beiden Enden, von der Walletgeneration zum Blockchain-Konsens 
und von den fundamentalen Innovation in zahlreichen anderen Gebieten.

Die meisten Verluste in Bitcoin resultieren aus den Unzulänglichkeiten des Designs,
ein Mangel an Usability, und Fehler der Endnutzer, nicht etwa aus fundamental technischen 
Attacken auf Softwareebene oder der Mathematik. Skycoin muss beides adressieren, die sich 
abzeichnenden mathematischen Bedrohungen und die Sicherheitsrisiken, welche die schlecht 
überlegte Nutzerfahrung von Bitcoin für alltägliche Nutzer kreiert hat. Die schlechte Usability
und das Design hat die User gezwungen die Sicherheitsvorkehrungen zu kompromittieren, was dazu 
geführt hat, dass Millionen von Dollar gewohnheitsmäßig auf unsicheren Webwallets liegen. 
Trotz der regelmäßigen Bedrohungen und massiven Diebstählen, über welche täglich von den 
Medien berichtet wird, wurden durch schlechte Usability mehr Bitcoins verloren, als durch all die 
Bemühungen der Kriminellen.

Fast die Hälfte aller existierenden Bitcoins wurden nie aus ihrer initialen Adresse bewegt und
werden dies auch nie, weil sie, als unwiderherstellbare Walletdateien verloren sind, 
als Wallets verloren gegangen sind, oder über Missverständnisse, was tatsächlich beim Backup eines
Wallets gespeichert wird verloren gegangen sind. Mt.Gox hat kürzlich gemeldet, dass sie 
200,000 Bitcoin in einem Wallet "gefunden" haben, von dem sie sich nicht bewusst waren, dass
es überhaupt Bitcoin hält. Das Wallet wurde bisher ignoriert und hätte leicht durch einen Fehler 
gelöscht worden können. Wallets werden regelmäßig für leer gehalten, weil Computersoftware 
nicht fähig war das Wallet, was mit einer "zu alten" Software erstellt wurde, zu laden.
Deshalb treten viele der Sicherheitsrisiken bezüglich Bitcoin auf dem Level der Usability, 
der Endnutzer und der Exchanges auf.

Der Rest dieses Abschnitts behandelt einige der neuen Techniken die wir, in Kooperation mit 
unseren Partnern entwickelt haben, um Sicherheitsrisiken auf Netzwerklevel zu adressieren und
um die Skycoin-Blockchain sicherer als vorherige Netzwerke zu machen.

Wir haben mathematisch bewiesen das unser System einen Konsens erreicht, die 
geforderten Sicherheitseigenschaften hat und unter normalen Netzwerkbedingungen
gut operiert. Wir haben einige aufregende neuen Datenstrukturen, welche bisher
in noch keinem anderen Coin oder Stück Software gesehen wurden. Im Moment
arbeiten wir an einem Prototypen des System für den Einsatz. Die Skycoin-Entwicklung
ist iterativ. Es wird, während wir uns durch die Details arbeiten, bekannte Fehler adressieren 
sowie Feedback erhalten und das System testen, Änderungen, Verbesserungen und Verfeinerungen geben.

# Transparenz und Sicherheit: Obelisk und öffentliche Verbreitungskanäle

Um die mit dem Bitcoin-System verbundenen Probleme zu adressieren, implementiert die
Skycoin zugrundeliegende Technologie die Blockchain in der Form 
eines öffentlichen Verbreitungskanals. Jeder kann die Kette lesen, aber nur der Besitzer 
kann Blöcke für sie prägen. Damit ein Block für eine persönliche Kette valide ist, muss er
mit dem privaten Schlüssel des Besitzers signiert sein. Jeder Knoten in diesem System des 
Konsens-Algorithmus (Obelisk) hat eine persönliche Blockchain und diese ist der Kern-Primitiv 
des Obelisk-Systems.

Der öffentliche Verbreitungskanäle stellt verhängt mehrere Einschränkungen:

### * Sobald ein Block veröffentlich wurde, kann er nicht mehr unveröffentlicht werden

Blöcken werden von Peer-zu-Peer zwischen allen Abonennten kopiert. Sobald ein Block
veröffentlicht wurde, verbreitet er sich zu allen Abonennten. Man müsste alle Peers
die den Block erhalten haben zerstören, um den Block aus dem Internet zu löschen.

### * Ein Knoten kann keine andere Version eines vorangegangenen Blocks ohne Detektierung veröffentlichen

Blöcke sind nummeriert und würden detektiert werden, wenn ein Knoten zwei Blöcke mit derselben
Sequenznummer signiert hätte.

### * Ein Knoten kann den Zeitstemptel des Erhalten eines Blocks nicht rückdatieren, ohne die Veröffentlichung des Block zu verzögern

Zeitstempel zählen nur nach oben, Zeitstempel erhöhen sich monoton mit der Blocksequenznummer.

### * Ein Block in der Mitte der Kette kann nicht geändert werden, ohne dass jeder andere nachfolgende Block ungültig wird

In einer Hashkette enthält jeder Header eines jeden Blocks, den Hash seines Vorgängers.

# Obelisk

Each Obelisk node (Skycoin Consensus Node)
has a public key (an identity) and personal blockchain
(a public broadcast channel). Consensus decisions
and communication happen within the personal
blockchains of each Obelisk node. This is a public
record of everything a node does. This allows the
community to audit nodes for cheating and collusion.
It gives the community a way to identify nodes which
are participating in attacks on the network and
it makes public how decisions in the network are
being made and which nodes are influencing those
decisions.

Each node has a list of other nodes that it
subscribes to. Nodes with more subscribers are more
“trusted” and yield more influence in the network. If
the community does not trust the nodes representing
them or feels that power within the network is too
concentrated (or not concentrated enough) the
community is able to collectively shift the balance of
power in the network by collectively changing their
trust relationships in the network.

Node subscription relationships can be
random and/or can be formed through web of trust
(subscribe to nodes of people you know and people
in the community you trust).

When a node receives a new block from a chain
it is subscribed to, it publishes the hash of the block
it publishes. This is a public acknowledgment of the
receipt of the block. Each block is timestamped
and counter-references blocks from other chains.
This creates a dense interlinked chain of block
acknowledgments. These chains establish causal
relationships and can act as a distributed time
stamping system as described in the next section.
This allows the network to prove that data did not
exist or was not published to the network or establish
that particular nodes were active or offline during a
particular time interval.

The current Obelisk consensus algorithm
is based upon Ben‐Or’s randomized consensus
algorithm.

A Sybil attack in a random graph (worst case)
allows the Sybil nodes to control consensus, but the
nodes are unable to revert transactions, removing the
only economic incentive to attack the network. In real
world graphs the Sybil resistance of the network is
actually very high and running a node is moderately
costly in terms of bandwidth, which makes large
botnets prohibitive.

Trust relationships are scarce and can be
rescinded. In the event of an attack, the network
reacts by severing connections to less trustworthy
nodes and contracting to a smaller core of trusted
nodes. The public record left by each node’s personal
blockchain makes it very easy to identify the nodes
participating in an attack. As attacking nodes are
identifed, individuals sever relationships with those
nodes, reducing their influence. Therefore, the major
benefits of the Skycoin network are:

- Skycoin consensus is democratic and nodes are run by the community
- Skycoin node consensus is public
- Every node is accountable to the community and 3rd party audits
- Influence within the skycoin consensus system is democratic and transparent (but unequal)

# Simple Binary Consensus Algorithm: Choosing Between Two Blocks

Each voting decision is a hash pair (A,B). A is
the hash of the parent of the block and B is the hash of
the block. Each node votes on the next block
it believes should be the consensus block. If 40% of
the nodes it is subscribed to have the same candidate
for consensus, the node changes its consensus to that
block. The node flips randomly between candidates
until consensus is reached.

# Consensus On Multiple Concurrent Branch Choices

A more advanced system publishes (A,B,P),
where P is a value from 0 to 1. P values across all
successors to block would sum to 1. This allows for
concurrent consensus decisions on multiple chain
branches.

If the majority of nodes in the network are
honest, they will also converge to the same consensus.

Skycoin also has a limited form of Proof of
Stake. We bias voting in favor of blocks with a larger
transaction fee.

If there are only two possible consensus
choices for a given parent and both blocks execute
your transaction, then the transaction is effectively
executed regardless of which of the two blocks end up
chosen by the network. The probability of reversion
of an early consensus decision declines exponentially
with block depth.
