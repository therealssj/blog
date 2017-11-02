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

>>>> Es werden keine Kosten hinzugefügt. Es beweist nur, dass man 10 Coins besitzt. 
>>>> Es beweist, dass man den privaten Schlüssel für einen öffentlichen Kennt, 
>>>> wessen Adresse 10 Coins aufweist. Man kann diese Coins immernoch ausgeben.

>>>> Die Idee ist, die obere Grenze der Anzahl von Knoten zu begrenzen. Wenn 10 coins 
>>>> gehalten werden müssen und es gibt insgesamt 100 Millionen Coins, begrenzt es das Netzwerk 
>>>> nach oben auf 10 Millionen Knoten. Die obere Grenze scheint aktuell mathematisch nicht 
>>>> nützlich zu sein, aber sie ist etwas, was wir im Hinterkopf behalten sollten.

>>>> Wenn ein Obelisk-Knoten betrieben wird, "vertraut" dieser zufälligen Peers. 
>>>> Der User kann einige Knoten von Hand eingeben, welchen vertraut werden soll (Exchanges oder 
>>>> vertrauenswürdige Community-Mitglieder). Ein Knoten wird mit dem Hash seines
>>>> öffentlichen Schlüssels identifiziert über DHT gefunden. Es ist nicht wie bei Bitcoin,
>>>> wo Knoten IP:Port-Paare sind. Man kann seinen Computer herumbewegen und die Identität
>>>> des Knotens beruht nicht auf der IP-Adresse.

>>>> Wir wollen, dass das Netzwerk sicher ist, indem zufällige Knoten gewählt werden. 
>>>> Wir wollen keine Situation wie bei Ripple, in der drei Entwickler das Netzwerk 
>>>> kontrollieren. Jedoch wollen wir auch eine Situation verhindern, in der jemand
>>>> 200,000 Knoten betreibt und versucht die Vertrauensbeziehung mit neuen Usern einzugehen.
>>>> Diese Sybil-Attacken-Knoten können immernoch, im Allgemeinen, keine 51%-Attacke ausführen, 
>>>> aber alles Mögliche, dass die Kosten der Attacke erhöht ist sinnvoll.

>>>> Vielleicht werden wir es so begrenzen, dass neue User nur zufällig gewählten Knoten vertrauen, 
>>>> welche eine Coinbilanz aufweisen. Vertrauensbeziehungen würden nicht getrennt werden, wenn der Knoten 
>>>> keine Coinbilanz aufweisen kann, aber sie würden keine neuen zufälligen User erhalten.

>>>> Der Konnektivitätsgraph für Vertrauensbeziehungen sollte vermeintlich ein komplett 
>>>> verbundener Zufallsgraph sein. Einige Knoten (vertrauenswürdige Community-Mitgleider, Exchanges, 
>>>> Webseiten, Organisationen) werden eine höhere Anzahl an Vertrauensbeziehungen haben, was
>>>> der Konsenszeit für den Block-Konsens unterstützt. Es reduziert den Netzwerkdurchmesser 
>>>> ein wenig. Einige Knoten werden verwendet werden um den Konsens zu verifizieren (man wählt
>>>> ein Haufen von Exchanges oder verschiedene öffentliche Schlüssel), diese Knoten beeinflussen
>>>> den Konsensprozess nicht, aber fungieren als "Konsensorakel" um zu überprüfen, ob der Knoten 
>>>> mit dem Netzwerk übereinstimmt.

>>>> Wenn zwei große Exchanges zu einem unterschiedlichen Konsens für einen bestimmten Block kommen,
>>>> ist das ein Problem. Dies könnte auf einen Netzwerkspalt hindeuten oder auf eine Attacke auf 
>>>> das Netzwerk. Exchanges könnten den Handel bis zur Behebung des Problems aussetzen.

>>>> Obelisk ist Skycoins verteiter Konsensknoten? Ich dachte immer der Skycoind ist der Knoten...

Genau. 

Skycoin hat eine Blockchain. Die Blockchain ist auf 
https://github.com/skycoin/skycoin/tree/develop/src/coin.
Diese gliedert die Blöcke auf und kümmert sich um unausgegebene Ausgaben und Transaktionen.

Skywire ist der Daemon und hat eine "Service-Architektur". Es kann auf Services laufen, 
wie Blockchain synchronisierenden Services und anderen Dingen. Das Meshnet (vermaschtes Netz) ist 
zurzeit auf Skywire aufbauend implementiert (obwohl dies sich dies ändern könnte).

Der Konsensmechanismus findet unabhängig von der Blockchain statt. Obelisk-Knoten (welche 
vermutlich als ein Skywire-Service implementiert werden) haben eine Blockchain. Jeder Knoten hat
einen öffentlichen Schlüssel. Dieser öffentliche Schlüssel identifiziert den Obelisk-Knoten.
Jeder Obelisk-Knoten hat eine eigene Blockchain (es gibt auf dieser Chain keine Coins).
Der Knoten erschafft einen neuen Block und signiert diesen mit seinem privaten Schlüssel.
Die Obelisk-Blockchain wird verwendet, um den Konsens zu verhandeln (den neuen Head in der
Skycoin-Blockchain bestimmen). Obelisk verwendet Ben-Ors für den zufälligen Konsens. Jeder Obelisk-Knoten 
hat seine Liste von anderen Knoten, die er abonniert hat. Diese Knoten beeinflussen den Konsens
und die Abstimmungsentscheidungen für den lokalen Knoten. Für nicht-pathologische Netzwerktopologien
passt sich der lokale Konsens nachweislich dem globalen Konsens an.

Jeder Knoten stimmt über den nächsten Block in der Chain ab. Ein Knoten schlägt
den nächsten Knoten vor und die Knoten stimmen dann über diesen Nachfolger ab. 
Die Stimmen werden in den Obelisk-Blockchains eines jeden Knotens veröffentlicht. 
Dein Knoten stimmt zufällig zwischen den Alternativen ab und wechselt seine Entscheidung
nach einer Weile. Sobald 40% deiner Peers (die Knoten, die du abonniert hast) einen Konsens
erreicht haben, wechselt man zu diesem Kandidaten. Das Netzwerk kann auf mehreren Abzweigungen 
auf einmal abstimmen, dies verlangsamt nicht das Warten auf einen Konsens. Die Abzweigungen
werden mit der Zeit auf einzelne Chains zurechtgestutzt. Aufteilungen von zwei oder drei Blöcken sind normal,
aber nach einigen Bestätigungen wächst die Wahrscheinlichkeit, dass ein Block zurückkehrt
exponentiell gegen 0. Wenn eine Transaktionen auf allen Chains der Kandidaten ausgeführt wurde, 
dann ist sie im Wesentlichen ausgeführt, selsbt wennsich die betreffende 
Konsens-Chain noch nicht entschieden hat.

Das ist binäres Ben-Ors und Skycoin wird etwas verwenden, dass ein wenig schneller und weiterentwickelter ist, 
wenn mehrere potentiell nachfolgenden Blöcke aus dem Netzwerk zur Auswahl stehen. Randomisierung ist wichtig
um die Teilgraphen des Netzwerk am feststecken zu hindern. Der Abstimmungsprozess ist eine Form des "Glühens", 
bei der jeder Knoten unabhängig voneinander zum globalen Konsens findet,  ausschließlich bedingt
durch seine lokal verfügbaren Informationen.

Der Konsensprozess findet in der Öffentlichkeit statt. Ein Knoten veröffentlicht Blöcke, signiert diese mit 
seinem privaten Schlüssel und diese Blöcke werden Peer-zu-Peer zwischen den Abonnenten der Chain repliziert. 
Es gibt dann keine "Konsensorakel", was Knoten sind, die genutzt werden um den Konsens zu verifizeren,
diesen aber nicht beeinflussen. Man wählt also den öffentlichen Schlüssel einiger Exchanges und einigen
vertrauenswürdigen Community-Mitgliedern und dein Knoten wird diese verwenden um zu bestimmen, 
falls mal etwas nicht ganz richtig sein sollte. Dies wird verwendet um Netzwerkspalte zu verhindern. 
Dies schützt ebenso vor einer Attacke, bei der ein Hacker den eigenen Router kontrolliert 
und somit auch die Möglichkeit zu Verbindung der Peers, zu denen man eine Verbindung aufbauen möchte.

Wenn eine Knoten im Netzwerk auftaucht und versucht das Netzwerk zur Akzeptanz einer anderen Chain 
zu bekommen (51%-Attacke, umkehren der Transaktionen), wird er üblicherweise ignoriert.
Die meisten 51%-Attacken benötigen bösartiges Knotenverhalten, was automatisch erkannt wird und darin endet, dass 
abonnierte Knoten diesen bösartigen Knoten von ihrer Vertrauensliste streichen. Die einfachste Strategie der
51%-Attacke ist mathematisch simpel zu beweisen, nämlich das versucht wird Transaktionen umzukehren, denn 
dies erfordert das Rückdatieren von Block-Konsensentscheidungen.
Es erfordert das veröffentlichen von zwei signierten Blöcken mit derselben Sequenznummer, wir haben daraus also 
eine automatisch verbannende Straftat für einen Knoten gemacht.

Wir versuchen die letzte Möglichkeit der 51%-Attacke zu eliminieren, welche so funktioniert,
dass ein Teilnetzwerk der Knoten offline geht (Netzaufspaltungsattacke), sich dann 
wieder mit einer anderen Konsens-Blockchain anschließt und versucht diese dem Netzwerk aufzuzwängen 
um Transaktionen rückgangig zu machen. Die meisten dieser Attacken werden fehlschlagen, weil das 
Teilnetzwerk nicht genug Einfluss haben wird.

Diese Attacke ist schwierig zustande zu bringen. Im Falle einer erfolgreichen 51%-Attacke ist eine Lösung, 
das gesamte Netzwerk einzufrieren und jeden User/Knoten individuell auswählen zu lassen, welche Chain 
die valide ist und die attackierenden Knoten manuell bannen zu lassen. 
Das Konsensorakel erlaubt jedem Knoten mit hoher Wahrscheinlichkeit zu wissen, ob der Zustand synchronisiert ist 
und ob der globale Konsens erreicht wurde oder ob sie ein Teil des Teilgraphen der Netzaufspaltung sind. 
Wir glauben, dass es für jeden Knoten möglich ist, mit hoher Wahrscheinlichkeit und gegebenen lokalen Informationen, 
zu wissen, ob ein Knoten während eines Konsensprozesses offline war - ist dies der Fall, so soll dieser Knoten, 
der offline war und plötzlich aufgetaucht ist und versucht dem Netzwerk eine Chain aufzuzwängen, ignoriert werden. 

Bei Bitcoin ist es so, dass wenn man die meiste Hashingpower hat, kann man Transaktionen umkehren, wann auch immer man es für richtig hält.

Bei Skycoin muss folgendes erfüllt sein um Transaktionen umzukehren:

- Kontrolle über eine große Anzahl von Knoten
- Die Knoten, welche man kontrolliert, müssen "einflussreich" sein und vertraut sein innerhalb
  der Netzwerktopologie
- 
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
