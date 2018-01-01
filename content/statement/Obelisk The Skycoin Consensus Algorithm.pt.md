+++
title = "Obelisk: O Algoritmo de Consenso da Skycoin"
tags = [
    "Statement",
]
bounty = 8
date = "2017-09-08"
categories = [
    "Statement",
]
+++

![Obelisk: O Algoritmo de Consenso da Skycoin](/img/obelisk-the-skycoin-consensus-algorithm.png)

A blockchain da Skycoin faz uso de um novo tipo de algoritmo de consenso chamado 
"Obelisk" que substitui a Prova de Trabalho ("PoW") e a Prova de Participação ("PoS"). 
"PoW" e "PoS" são as siglas inglesas para Proof of Work e Proof of Stake respetivamente.

O objetivo dos desenvolvedores da Skycoin foi corrigir as principais falhas de 
segurança e "tendências centralizadoras" associadas às blockchains em que o 
consenso se baseia em algoritmos PoW ou PoS e a criação de moedas está vinculada 
a um processo de mineração. A Skycoin está, portanto, a tentar criar uma cryptomoeda 
que melhor atenda a visão original de Satoshi de um sistema de moeda digital 
completamente descentralizado.

Ao fazê-lo, a tecnologia Skycoin cria uma rede blockchain sem requisitos de 
mineração, suprimentos fixos de cripto tokens, tempos de transação de 10 segundos 
e maior segurança. Num sistema no qual a conexão entre criação de moeda e 
controle sobre a rede é interrompida, os cripto tokens perdem sua função 
política e começam a agir mais como uma forma de propriedade digital no 
sentido direto.


## Prova de trabalho e sistema da Bitcoin

Foi um erro de cálculo fundamental na programação inicial da Bitcoin que
o processo de mineração produziria uma estrutura de incentivo económico que
promoveria a descentralização. Na verdade, a ligação entre consenso e hash 
power incentiva a compra de capacidade de processamento cada vez maior para
controlar a rede de consenso.

The Bitcoin network, for instance, is de facto controlled by three for-profit
mining pools which have been able to concentrate a large part of the network’s
hashing power on its servers. These pools have begun to act as a cartel,
splitting hashing power among each other by agreement. The link between mining
and control of the network was already identified by Satoshi as the main
non-cryptographic threat to the stability of the network. It allows actors who
accumulate sufficient processing power and achieve a majority hash rate to
falsify or revert transactions on the network in a 51% attack. Some argue that
this vulnerability has become less pressing in an environment where hash power
is highly centralized with actors who have invested large sums in the Bitcoin
network and depend for their survival on the high value of the coin. Yet the
power to influence the network is still highly concentrated, defeating the
purpose of a distributed ledger-based cryptocurrency.

A rede Bitcoin, por exemplo, é de facto controlada por três pools de mineração com 
com fins lucrativos que conseguiram concentrar uma grande parte do hashing power 
da rede nos seus servidores. Essas pools começaram a atuar como um cartel,
acordando dividir o hashing power entre si. A ligação entre mineração e o 
controlo da rede já foi identificado por Satoshi como a principal ameaça 
não criptográfica para a estabilidade da rede. Permite a atores acumular potência 
de processamento suficiente e atingir uma taxa de hash maioritária para
falsificar ou reverter transações na rede num ataque de 51%. Alguns argumentam que
esta vulnerabilidade tornou-se menos urgente num ambiente onde o poder de hash
é altamente centralizado com atores que investiram grandes somas na rede Bitcoin e 
dependem do alto valor da moeda para a sua sobrevivência. Ainda assim o poder de 
influenciar a rede está altamente concentrado, derrotando o propósito de uma 
cryptomoeda baseada num livro-razão.

The Bitcoin network’s PoW algorithm thus introduces security and monopoly
problems by placing power over the network with the actor capable of
mobilizing enough economic resources to control the mining process.

O algoritmo PoW da rede Bitcoin, portanto, introduz problemas de segurança e  
de monopólio, colocando o poder sobre a rede do lado do ator capaz de mobilizar 
recursos económicos suficientes para controlar o processo de mineração.

This also implies that the operation of the network is both economically and
environmentally inefficient. The continuous input of processing power required
by the mining process uses up large amounts of electricity, incurring monthly
costs in the tens of millions. These costs can only be offset with an
exponentially growing influx of new capital along with new users. Only a very
small number of well-established coins, like Bitcoin and Ethereum, will be
able to attract enough users to achieve such a continual flow. In the case of
most other PoW/PoS-based coins, the cost
of PoW/PoS mining is paid for in a lower market valuation as money is bled
out of a coin by mining costs until the coin is abandoned.

Isto também implica que a operar a rede é ineficiente tanto econômica como ambientalmente. 
A entrada contínua de potência de processamento requerida pelo processo de mineração 
usa grandes quantidades de eletricidade, implicando custos mensais na ordem das dezenas de milhões. 
Estes custos só podem ser compensados com um influxo exponencialmente crescente de novos 
capitais junto com novos utilizadors. Apenas um pequeno número de moedas bem estabelecidas, 
como a Bitcoin e Ethereum, será capaz de atrair utilizadores suficientes para alcançar tal fluxo. 
No caso da maioria das outras moedas baseadas em PoW/PoS, o custo da mineração PoW/PoS 
é paga em uma avaliação de mercado mais baixa à medida que o dinheiro é sangrado de uma moeda 
por custos de mineração até que a moeda seja abandonada.


>Right now the Bitcoin economy consists of new users putting their money in
and then the money being thrown in a pit and burned in a sacrifice ritual to
the mining electricity costs. If the average user had to pay the miners’
electricity cost directly as transaction fees, instead of it being robbed from
them through inflation by the creation of new coins, then each Bitcoin
transaction would cost more than $50. It would be more expensive than an
international bank transfer.

>Neste momento, a economia da Bitcoin consiste em novos utilizadores a colocar o seu 
dinheiro na rede e o dinheiro a ser lançado num poço e queimado num ritual de sacrifício 
para os custos de eletricidade da mineração. Se o utilizador médio tivesse que pagar aos 
mineradores os custos da eletricidade diretamente como taxas de transação, em vez de 
lhes ser roubada através da inflação pela criação de novas moedas, então cada transação 
da Bitcoin custaria mais de $50. Seria mais caro do que uma transferência bancária internacional.


## A tendência centralizadora da Prova de Participação

Although Proof of Stake algorithms tackle the security issue of 51% attacks,
they are arguably even more vulnerable to centralization than PoW networks. In
PoS, the size of network participants’ holdings of the cryptocurrency in the
network determines their authority and voting power to implement technical
changes in the network. Participants are able to mine an equivalent portion of
their stake regardless of processing power.

Apesar de os algoritmos de Prova de Participação resolverem a questão de segurança
de ataques de 51%, eles são, sem dúvida, ainda mais vulneráveis à centralização do 
que as redes PoW. Em PoS, o tamanho das participações em criptomoeda dos participantes 
na rede determina a sua autoridade e poder de voto para implementar mudanças técnicas
na mesma. Os participantes podem minerar uma parcela equivalente à sua participação, 
independentemente do poder de processamento.

This principle significantly increases the economic barriers to launching a
51% attack because the financial cost of acquiring the majority of tokens on
the network in the open market is very likely to exceed the potential gain. If
an attacker ends up as the majority stakeholder in the network, he will suffer
most from the impact of the attack on the stability of the network or the
external value of the cryptocurrency.

Este princípio aumenta significativamente as barreiras económicas para lançar 
um ataque de 51% porque o custo financeiro de adquirir a maioria dos tokens 
na rede no mercado aberto é muito provável que exceda o ganho potencial. 
Se um atacante terminar como o participante maioritário da rede, ele sofrerá 
mais do impacto do ataque na estabilidade da rede ou do valor externo da cryptomoeda.


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

No entanto, apesar de aumentar as barreiras aos ataques dirigidos por humanos na
rede, o PoS cria um impulso centralizador que é tão forte, se não mais forte, 
como no caso da PoW. Tal como Joseph Young resume na sua comparação dos dois sistemas
em [coinfox.info] (http://www.coinfox.info/), "Um sistema em que o titular principal  
goza de um controlo e autoridade extensivos sobre os aspectos técnicos e económicos 
da rede cria um grande problema de monopólio. "Enquanto num sistema PoW a votação sobre
a implementação de mudanças técnicas na rede" é dividida entre mineradores, desenvolvedores
e outros membros cruciais da comunidade", num sistema PoS", os titulares principais 
têm a capacidade técnica para fazer quaisquer mudanças que eles queiram, sem considerar 
a vontade da comunidade, das empresas, dos mineradores e dos desenvolvedores. Essa 
centralização do poder de voto e, essencialmente, do controlo da rede derrota o propósito 
de uma cryptomoeda baseada em livros-razão, uma vez que contradiz todo seu princípio de 
distribuição de todos os elementos da rede para evitar a presença de uma autoridade central".

## Obelisk: O Algoritmo de Consenso distribuido da Skycoin

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

Para enfrentar este problema de centralização, a Skycoin move-se além da PoW/PoS. 
Usa um algoritmo de consenso distribuído, chamado Obelisk, que distribui influência
sobre a rede de acordo com uma "rede de confiança". Essencialmente, cada nodo possui 
uma lista de outros nodos aos quais se inscreve e a densidade da rede de assinantes 
de um nodo determina a sua influência na rede. A cada nodo é atribuída uma blockchain 
pessoal que atua como um "canal de transmissão público" no qual todas as ações de um 
nodo são visíveis e gravadas publicamente. À medida que todas as decisões de consenso 
e comunicação ocorrem através das blockchain pessoais de cada nodo, a comunidade pode 
facilmente auditar os nodos que fazem batota ou conluio. As decisões na rede e quais 
os nodos que influenciam essas decisões são completamente transparentes.

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

O registro público deixado pela blockchain pessoal de cada nodo permite que a rede 
reaja às deserções cortando conexões com nodoa menos confiáveis ou maliciosos, 
contraindo a rede para um núcleo menor e mais denso de nodos confiáveis. Portanto, 
em princípio, se a comunidade não confia nos nodos que os representam ou sentem 
que o poder dentro da rede está muito concentrado (ou não está concentrado o suficiente), 
a comunidade pode mudar coletivamente o equilíbrio de poder na rede alterando 
coletivamente as suas relações de confiança na rede. A responsabilidade dos nodos 
para a comunidade e as auditorias de terceiros, bem como a transparência do consenso, 
fortalecem a tomada de decisão coletiva e, portanto, introduzem um elemento altamente 
democrático e descentralizado na rede.

Este sistema providência um sistema de moeda digital com tempos de transação significativamente 
reduzidos, nenhum requisito de mineração e maior segurança.

*Consulte Mais informação:*



* *[Skycoin Consensus Algorithm Whitepapers](https://www.skycoin.net/whitepapers)*
* *[Obelisk The Skycoin Consensus Algorithm | Information Pages](/overview/obelisk-skycoin-consensus-algorithm-information-pages/)*
