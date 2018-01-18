+++
title = "次世代インターネットの基盤: Skyminer"
tags = [
    "Skywire",
    "Skycoin Mining",
    "Meshnet",
]
date = "2017-08-11"
categories = [
    "Skywire",
    "Statement",
]
bounty = 4
+++

*Skyminerの最新ニュースを受け取るためにはメールリストに登録: http://eepurl.com/c4DyAv*

どうすれば真に開かれた、自由なインターネットを作れるのでしょう?私たちはこの疑問から出発して、
新たな、別の形のインターネットであるSkywireを開発しました。Skywireは既存と異なる、新たな
技術を発明することで、インターネットを所有する権利をインターネットサービス・プロバイダ（ISPs）
企業からユーザーに移行します。P2Pの形式で作られるSkywireはネットの中立性を守り、ブロック、
遅延、監視なしにコンテンツの共有を可能にします。このネットワークはプライバシーを保護し、人びと
の自由な主張を守ります。インターネットの未来を形作るのがSkywireの使命です。

[Skywire](https://github.com/skycoin/skywire)の革新的なネットワーキングプロトコルは、
私たちの考えるインターネットの姿を既に大きく変えています。Multi-Protocol Label Switching 
(MPLS)を基礎にSkywireは作られています。MPLSの特徴は速度が速く、質が高く、動作も安定しており、
セキュリティが高いことです。SkywireはMPLSの水準以上に、速く、質の高いネットワークを提供します。
最高のパフォーマンスとプライバシーのために設計され、ユーザーはISPの企業を経由することなしに、
自らインターネットを所有することができます。

SkywireではSkycoinが通貨として使われ、電子通貨の役割を超えた実用性が付与されることになります。
ユーザーがトラフィックの転送やネットワークのリソースを提供するとき、ユーザーはSkycoinを受けとること
ができます。同じように、ネットワークのリソースやメディアを消費するとき、ユーザーはSkycoinを支払うこと
になります。Skycoinの使用用途には２つあります。回線が混雑しているエリアで高い帯域を得るか、または
需要の高いコンテンツを消費することです。

![Skyminer](https://i.imgur.com/ASFEeYi.jpg)

Skyminerは、次世代のインターネットSkywireの根幹となるマイニング機器で、精巧に設計されています。
Skywireのために作られた独自の機器で、最大限の出力とパフォーマンスのために作られました。Skywire
はSkycoinのマイニング装置として機能する、下記の仕様を備えた特別なVPNです。

- 8 CPUボード
- 2 GBのRAM (各ボード)
- 4 CPUコア (各ボード)
- 64 GBの要領 (各ボード)
- 64-bit Linux (Alpine Linux)
- Gigabit ethernet, 8+1 port switch

ARMプロセッサー、2 GBのRAM、32~256GBのフラッシュストレージを各ボードに搭載しています。この
機器は内部が複数部分で構成されており、１つの部分に不具合が生じても、他の部分が正常に動く
ように設計されています。厳重なパケットの転送ルールとアクセスコントロールを備えたOpenWRTの
ルーターを搭載して、セキュリティに更なる強化をしています。CPUボードを４の倍数で調整すること
も可能です。

![Skywire miner](https://i.imgur.com/2zj4CUV.jpg)

ユーザーはノードを主導でセットアップすることができますが、自動設定の実装も開発中です。公共鍵
を[Sky-Messenger](https://github.com/skycoin/net)のchatbotに入力すると、ユーザー
はクラスタにピア接続されます。メータリングとセトルメントが実装された後、Skywireはネットワークの
参加者に通貨を配当するようになります。

第二世代の機器の設計も既に始まっています。RAM/CPU/帯域と時間あたりのSkycoinsの報酬を表示
するOLEDスクリーン、OpenWRTルーター, 少なくとも4つのCPUボードにSATAポートが搭載され、32ビット
と64ビットのモデルが作られます。ネットワークは内部のインターネットにて動作します。将来的に、上記
の機器はワイヤレスのメッシュネットワークをサポートするために拡張される予定です。

他の選択肢に比べて、Skywireでは匿名性の高い、速いネットワークでコンテンツが通信されます。この
ネットワークには２つの構成要素があります。AetherとSkynetです。AetherはP2Pの複製オブジェクトの
システムで、匿名性と安全性に高いウェブのコンテンツ配信のためのものです。従来のウェブで使われる
ようなビデオストリーミングやメッセージのアプリはAether上で機能します。第二の構成要素のSkynetは
分散型のネットワークシステムの根幹です。ソースルーティングに基づく、パブリックのMPLSネットワークで、
独自の名前空間内と新たなプロトコル・スタック上に作られています。要するに、Skynetのユーザーは自ら
がISPとして機能できることになります。

AetherとSkynetはそれぞれ独立した機能を持ちますが、Skywireは２つを統合して、頑強なネットワーク
を作り上げました。Skywireにより、 ローカルキャッシュは外部のインターネットとの接続なしにリソースを
収容することができます。ダウンロードされたファイルは直接ローカルキャッシュに保存されます。Skywire
の他の参加者がそのファイルにアクセスしたい場合は、ネットワークを通して転送ができます。P2Pの技術
を活かして、Skywireは安全で、速く、持続可能なインターネットの次の姿を作り上げています。

インターネットの未来は２つの勢力が保つバランスにかかっています。一方にはインターネットのアクセスを
利益のために制限するISPの企業があり、他方にはユーザーにインターネットの権利を戻そうとする最新の
テクノロジーがあります。Skywireはこの革命の先駆者です。私たちはインターネットを使うのにISPの企業
に頼る必要などなくなるのです。Skywireのネットワークプロトコルにより、自由でグローバルな、分散型の
インターネットが可能になるからです。Skywireのビジョンは現在の市場に限定されず、変革以上の未来を
作り上げることにあります。インターネットを変えるのではなく、全く違うものとして発明するのです。

### Skyminerの詳細

Skyminerは今後６ヶ月以内にリリースされる予定です。３ヶ月以内を目標としていますが、検証だけにでも
少なくとも数ヶ月を要することがわかっています。また、流通に関して、組み立てと発送の仕組みを整えな
ければなりません。

Skyminerは今後６ヶ月以内にリリースされる予定です。３ヶ月以内を目標としていますが、検証だけでも  Ideally it would
６ヶ月以内というのは確約した数字ではありません。ハードウェアとソフトウェアが完全に検証されるまでは、
正確な発表日時について告知ができません。実用化が確認され次第、注文を受け付ける予定です。

*[Skycoin Telegram](https://t.me/Skycoin)に加わるとSkyminerに関する情報が得られます*

第一回目の注文個数は300になります。注文を受け付ける準備ができ次第、ウェブサイトに登録フォーム
が公開されます。

価格は１台につき1BTC(bitcoin)です。購入者は次の:
が公開されます。. When we are ready to take orders,

* Skywire miner
* An amount of Skycoin equal to 1 BTC minus the hardware cost (estimated to be around $600), based on market rates at the time of purchase.

Nodes operating on the Skywire network will be receiving a network incentive reward
to help build out the network, in addition to traffic forwarding payments.
For the Skywire miners, we'd like to increase this network incentive reward.
However, we're still working out a mechanism for distinguishing the Skywire miners
from other nodes, which could be any machine on the network.

The value and structure of the general network incentive reward is not yet specified.
More information on this will be in a future release.

### Errata

- *[More pictures of the Skywire miner](https://imgur.com/a/mpnzh)*
- *[Skywire Github](https://github.com/skycoin/skywire)*
- *[Sky-Messenger Github](https://github.com/skycoin/net)*
