+++
title = "Skycoin AMA Log (held at ark.io)"
tags = [
    "Ask the Developers",
]
date = "2017-08-01"
categories = [
    "Ask the Developers",
    "Statement",
]
bounty = 12
description = "Log of AMA with Skycoin held at ark.io/slack/ (from 2017-07-02)"
+++

*この対談は2017年2月に[ark.io slack](https://ark.io/slack/)で行われたものです。*

*synth氏はSkycoinの代表としてAMAに参加しました。*

**boldninja**
Skycoin.netのsynthさん、ようこそ。本日はAMAのお時間をいただき、ありがとうございます。

**synth**
どうも、こんにちは。

**mike**
こんにちは、synthさん。

**jakethepanda**
やあ、synthさん。

**thrice.pi**
どうも、synthさん。

**dr10**
こんにちは。

**boldninja**
さて、いつもどおりにはじめましょうか。1度にする質問は２〜３個までにとどめるようにしてください。

**dr10**
短く、簡単な言葉でSkycoinの良いところを説明してくれますか？例えば、雑誌や暗号通貨に詳しくない人を相手に想定して。

**mgaruccio**
メッシュネットについて説明をお願いします。単なるノード間のMPLSネットワークですか？それとも何か大きな構想があるのでしょうか？ 

**michaelthecryptoguy**
やあやあ、synthさん。

**tranzer**
synthさん、質問があります。流通していないコインは、コールドウォレットに保管してあるのでしょうか？coinmarketcap.comによると、全供給量の部分的にしか現在は流通していないことになっています。あと、Skycoinが持つ、特にユニークな機能はなんでしょうか？

**synth**
Skycoinを説明するのは難しいですね。なにせ６年間も開発が続けられてきた大きなプロジェクトですから、各部分がそれぞれの目的を持っています。 
暗号通貨、コインの部分は、既に存在している合意形成アルゴリズムの問題を解決するために作られました。１秒あたりに300という送金の処理速度を誇ります。分単位ではなく、秒単位の話です。マイナーの役割をなくし、インフレ防止のためにブロック報酬をなくし、51%攻撃や他のマイニングに関する問題を解決しています。 
そして、他にも多数のプロジェクトや実験段階のアイデアがあります (https://github.com/skycoin)。メッシュネットと分散化されたVPNのプロトタイプがあり、ネットワーク参加者はトラフィックを転送することで報酬を得られます。また、分散化されたソーシャルメディアのアプリケーション、P2Pのデータ複製・保管のためのアプリ、その他の実験的なプロジェクトがあります。変更不可なデータ構造に関するリサーつを重ね、次世代のインターネットの構想を実現化しています。このいくつかは革命的なプロジェクトだと思っています。

**dr10**
ネットワーク合意形成アルゴリズムの「Obelisk」はどのような仕組みで、よく知られている他のアルゴリズム（Proof of Work, Proof of Stake）とはどう違うのですか？

**mgaruccio**
実際にどのくらい実用化されていますか?例えば、現時点でSkycoinのブロックチェーン上にアプリを作ることはできますか?

**mike**
進捗状況に関して、プロジェクト発展の最大の障壁になっている要因はなんでしょうか？例えば、資金、人手、技術的な限界点などですか？ 

**synth**

> メッシュネットについて説明をお願いします。単なるノード間のMPLSネットワークですか？それとも何か大きな構想があるのでしょうか？ 

これは単なるメッシュネットのプロジェクトではなく、強力なソフトウェア・ディファインド・ネットワーキングです。全く新しいプロトコルとネームスペースを用いた次世代のネットワーキングのプロジェクトになり、既存のインターネットに頼ることなく成り立つものです。
インターネットがホットポテト・ルーティングを使用している一方、私たちはソース・ルーティングを用いるので、最適化されたレイテンシーが実現されます。
IPv6では不可能な、マルチホーミングにも対応しています。ギガバイトやテラバイトのネットワーキングとマルチ冗長化された帯域幅のパスを確保するのに欠かせない要素です。 
リンク層とE2Eの両方で日和見暗号化がデフォルトとなっています。既存のインターネット異なり、全ての通信はデフォルトで暗号化されています。 
ストアアンドフォワード・ネットワーキングになりますので、レイテンシーが分や時間単位、そしてパケットの損失が大きいアフリカのような地域でも、問題なく動作します。既存のプロトコルでは動作しないような環境でも、私たちのネットワークには影響なしでしょう。IPv4/IPv6やTCP/ipより、さらに安定した確固なネットワークとなります。
プライバシーの問題にも取り組んでいます。パケットが１０の中継地点を通って転送されるとしたら、それぞれの中継地点は直前と直後のノードの情報しか得られません。IPv4のように各パケットが出発と到着地点の情報を持つようなことはありません。このプライバシーのレベルは、現在のインターネットでは不可能です。
IPアドレスは公開鍵に置き換えられ、目的地へのトラフィックは誰にもわからなくなります。それを知るのは、目的地を定めるための公開鍵の秘密鍵を持つ者のみです。このシステムは第三者や認証のための組織を必要としません。革命的なデザインといえるでしょう。

> 流通していないコインは、コールドウォレットに保管してあるのでしょうか？coinmarketcap.comによると、全供給量の部分的にしか現在は流通していないことになっています。

100の異なるアドレスに、１００万個のコインがそれぞれ保管されています。定期的にロックアップが解かれ、段階的に流通量が増えることになっています。
複雑なロックアップと解除の手順があり、これにはデベロッパー全員からのコンセンサスが必要になります。 このグループにいるデベロッパーなら誰でもが、流通量の増加を止める権限を持っています(暗号通貨のNXTはこの対策に失敗しました)。元々の設計により、コインの流通量を増やすのは難しくなっており、決定には事前承認された正当な理由が求められます。

**mike**
ワイヤレスのSkywire(上記のプロトコルの名前)のノードとなるためには、どのようなハードウェアが必要ですか？

**arc-over-water**
nxtは問題なくやっていると私は思いますが。

**synth**

> ネットワーク合意形成アルゴリズムの「Obelisk」はどのような仕組みで、よく知られている他のアルゴリズム（Proof of Work, Proof of Stake）とはどう違うのですか？

PoSとPoWにはマイナーが必要であり、ブロック生成の報酬にマイナーは新しいコインを受取ります。マイナーはたくさんのお金を得ており、自分たちの利益となるようにネットワークを操作しようとするでしょう。新たなコインが生まれるたびにインフレが悪化し、コインのユーザーが被害を被るのです。
Skycoinはマイニングとインフレの問題を解決するように設計されました。ブロック報酬はなく、新たなコインも生まれません。このためには新たな合意形成アルゴリズムが必要で、制約をクリアするには限られた方法しかありませんでした。Michael Ben-Orが考案した、分散化されたシステムで合意形成をとるためのランダム化の手順を改良し、合意形成を邪魔する悪意あるノードを検知する仕組みを加え、「Obelisk」が完成しました。
skycoin.netに詳細が記されたホワイトペーパーがあります。これは「ネットワークコンセンサス」 と呼ばれるべきものです。信頼の環の仕組みを用いて、ブロック生成をする人びとが悪意ある行動をしたときに、その人をネットワークから追放できる仕組みを作りました。同時に、ネットワークをコントロールする人びとも、ネットワークを攻撃する力はありません。できることといえば、処理速度を遅くして邪魔をするくらいなので、悪意ある行動をするノードは追放され、新たな参加者に置き換えられるだけです。

**mike**
Skywireが公開され、ハードウェア上のノードとして機能するのはいつですか (テストネットとメインネットの公開予定日)?

**mgaruccio**
もしブロック報酬がないとすれば、ノードになるインセンティブは何なのでしょうか？

**vega**
Skycoinの実際の機能はなんですか?説明されていた様々なプロジェクトを統合して、価値を保存、交換するために使われるのですか?それとも、もう少し限定的な機能ですか？

**michaelthecryptoguy**
ノードとなるためのハードウェアのスペックはなんですか?初期段階においては?ユーザー数が10000人の段階では?

**synth**

> nxtは問題なくやっていると私は思いますが。

nxtでは3人の人間がそれぞれ供給量の30%のコインを所有していました。このうちの１人がプロジェクトを途中で脱退することを決め、コインを投げ売りしました。NXTは当時1億５千万ドルを超える市場規模でしたが、彼が投げ売りをはじめたせいで、NXTの価格は地に落ちました。 
創始者や早期の参加者が投げ売りをするのを防ぐように、Skycoinの分配計画が作られています。
Skycoinの流通量が供給量の30%になったとき、 残りのコインには計画的なロックアップがされる予定です。毎年最大で5%のコインが解除、分配されることになります。つまり、残りの70% が分配されるまでに最短で14年かかることになります。
残りのコインを今売ることはできません。なぜなら、全体の10%を5ドルの価格で売ると、５千万ドルの資金が手に入ることになり、現時点の私たちにその資金は必要ありません。現段階においては使い道のないお金です。 
Ethereumは3千万ドルから7千万ドルの資金を最初の数年に使い切り、危うく破産するところでした。シリコンバレー並の給料を支払い、綺麗なオフィスを借りたり、といったような使い道です。Skycoinでは保守的な資金の使い方をしており、これまでコストの削減を意識してきました。現在の市場においては、何もプロダクトを発表していない状態で１00億ドルもの資金を調達しようとするEOSのようなプロジェクトもあります。彼らが何にお金を使う予定なのかまるで不明です。マーケティングとPRを目的としたパーティーをタイムズ・スクエアで開催するために350,000ドルものお金を浪費しているという話を聞きました。 

**arc-over-water**
なぜさっさとコインを売ってしまわないのですか?5千万ドルくらいだったら小さい資金額でしょう?
nxtはskyよりも新しいプラットフォームですが、 nxtの時価総額は2億2千万ドルでskyは1億6千万ドルです。あなたの言い分は理解できますが、証拠がないでしょう。nxtのコミュニティは非常に大きく、活動的です。全く崩壊などしていないと思いますが、どうでしょうか？

**synth**

> Skycoinの実際の機能はなんですか?説明されていた様々なプロジェクトを統合して、価値を保存、交換するために使われるのですか?それとも、もう少し限定的な機能ですか？

前者になります。Bitcoinには特に使用価値はありませんでした。アルトコインには２つの機能があります。残高を確認して、他の人にお金を送ること。
コインが価値を持つためには、特定のサービスを利用するために購入される必要があります。実際にコインが使われ、需要が生まれるための価値の源泉がないといけません。
こうして考えると、Bitcoinは完全に投機的な資産です。キャッシュフローはなく、人びとの主観や社会の常識が価値を決めます。
アイデアとしてのSkycoinは「Bitcoinの改良版」としてスタートしました。より速く、安全で、シンプルに、新たなアルゴリズムで。しかし、時間が経つと共に、私たちは1つのエコシステムを作り上げるに至りました。そこにはコインの価値の裏付けとなる使用価値とネットワーク価値が生まれます。
例えば、メッシュネット (skywire) は良い例です。ユーザーは使用するためにコインを手に入れる必要があり、サービスの利用でコインが消費されます。Skywire上のVPNを通してインターネットを利用するとして、おそらく使用料金は驚くほど安いものになりますが、それでも実際の経済活動が生まれていることに意味があります。使用価値に裏付けされたコインと、それを使うコミュニティがあるからです。 そこに投機家はいません。
開発後期になってくれば、プロジェクトの射程はさらに広くなるでしょう。

**arc-over-water**
インターネットの使用時に、SkycoinのウォレットがVPNとして使えるということですか?

**synth**

> nxtはskyよりも新しいプラットフォームですが、 nxtの時価総額は2億2千万ドルでskyは1億6千万ドルです。あなたの言い分は理解できますが、証拠がないでしょう。nxtのコミュニティは非常に大きく、活動的です。全く崩壊などしていないと思いますが、どうでしょうか？

あの出来事がなければNXTは今よりも進んだ状態に発展していたでしょう。Ethereumと比較しても劣らない地点にいたかもしれない。あの分配計画のミスと価格崩壊のせいで、数年の遅れが出たと言っても過言ではない。長期的に見て、大量保有者が価格に与え得る影響を甘く見ていたのです。 

**arc-over-water**
IOTAでも同じようなことがありましたね。リードのデベロッパーで、あれは１００億ドル近くでしたか。
コインを完全に分配し、市場に価格を決定させていました。

**synth**

> インターネットの使用時に、SkycoinのウォレットがVPNとして使えるということですか?

Skywireを経由して帯域幅を使うアプリケーションの1つがVPNです。他にもいくつかのプロジェクトが進められています。
例えば、4chanをモデルとして、CXOによって分散化されたBBSがあります。 https://github.com/skycoin/bbs
Skywire上で機能する、新たなインターネットを私たちは作っているのです。開発されるアプリはプライバシーを重点に置いた、専門的なものです。GitHub上のskycoin/bbsを見てください。BBSの開発に興味がある方は是非協力ください。 

**mike**
Skycoinの価値はProof of Resource、つまり、何かしらのサービスに裏付けされているんですね。この場合はプライバシー保護がされた、安全なネットワークということでしょうか？分散化ストレージ、分散化されたコンピュータ処理能力の提供などのサービスを展開していく予定はありますか？

**arc-over-water**
さっき言っていた、100万個のコインが保管してある100個のアカウントから、どのようにコインを分配していくのですか？100回のICOをやるのか、それとも既に配分プランがコーディングされているのか、デベロッパー次第で決められるのか。どれでしょうか？

**rockyj**
それは計算すればわかりますよ！

**slackbot Custom Response**
https://docs.google.com/spreadsheets/d/1FGo3FkC3uSWXGHatPQyny2brMWjAIJsHFCR-Lhkl_m0/edit#gid=0

**synth**

> もしブロック報酬がないとすれば、ノードになるインセンティブは何なのでしょうか？

合意形成のノードを稼働するのにコストはかかりません。Raspberry Pi上でも動作確認済みです.
重要なのは、もしノードを稼働している人びとが悪意をもった行為をすれば、コミュニティにより追放され、代わりのノードが代替するということです。他に重要な点は、ノードがプロトコルに沿って動作しているかどうか、自動的に監査ができることです。
Skycoinのノードはネットワークを操作する力を持たず、できることは処理速度を遅くすることくらいです。他の人のコインを使うことは秘密鍵がなければ不可能ですから、合意形成のノードがネットワークにもたらす脅威は限りなく小さいものです。Bitcoinの場合はマイナーがネットワークを人質にとり、利己的な行動をとることができます。例えば、自分たちの利益追求のために送金手数料を釣り上げたり、全体にとって有益になり得るbitcoinのアップデートを邪魔したり、ということをマイナーがしています。

> Skycoinの価値はProof of Resource、つまり、何かしらのサービスに裏付けされているんですね。この場合はプライバシー保護がされた、安全なネットワークということでしょうか？分散化ストレージ、分散化されたコンピュータ処理能力の提供などのサービスを展開していく予定はありますか？

私たちは既に分散化されたストレージ、CXOを開発しました。しかし、帯域幅のみがSkywireによってマネタイズされています。それぞれのAPIの動作のために手数料をとるようなことは私たちはやりません。無料のものは無料であるべきです。これが私たち独自の哲学なのです。 
CXO上で動作するソーシャルメディアも開発を進めています (Steemitに類似したもの)。
CXOはIFPSに似ていますが、よりシンプルで私たちの開発環境に合うようにデザインされています。暗号技術に特化した設計です。

**mike**
遅くて働きの悪いノードを避けて、最も速いルートにトラフィックを最適化することはできますか？それはSkycoinの合意形成の安定化につながると思います。

**tranzer**
Skycoinの毎秒のトランザクション数はいくつですか?ブロック生成時間は?

**thrice.pi**
300でしょう? ^

**arc-over-water**
非チューリング完全なLISPのプログラミング言語を使っているとウェブサイトにありましたが？

**synth**

>さっき言っていた、100万個のコインが保管してある100個のアカウントから、どのようにコインを分配していくのですか？100回のICOをやるのか、それとも既に配分プランがコーディングされているのか、デベロッパー次第で決められるのか。どれでしょうか？

分配計画を近いうちにウェブサイトに掲載します。これは複雑で説明が難しいのです。
市場に出回っているコインはSkywireの使用にかかる租税によって回収されていきます。ネットワークの資源を使うために支払う租税により、実質的には自動的にコインが回収される仕組みです。ここで流通量はピークとなり、それから下降曲線をたどっていきます。しかし、ロックアップされたコインが唯一の分配源として残っています。定期的に解除、分配され、流通してから、また供給源に戻ることでしょう。 
ここには２重の経済構造があります。コインを流通から外すための買上げと、ユーザーがコインを保持するインセンティブを与える分配金の配布です。 

**arc-over-water**

つまり、２種類の通貨が存在するということですか。片方を所有することで、他方が付与される。

**synth**

> 遅くて働きの悪いノードを避けて、最も速いルートにトラフィックを最適化することはできますか？

はい、可能です。これはとても重要なことです。
接続をしようとする個人が、接続先へのパスを決められるのです!
例えば、ビデオゲームやSkypeの会話には、レイテンシーの低いパスを選ぶことができます。ビデオのダウンロードには最もスループットの高いパスを選びます。もしくは、特定のノードや機能、国を通るパスを選ぶことができます。これはセキュリティ上の懸念のため、また経由地点の数を最小化するのも選択肢にあります。

**mike**
元々計画にあったように、Skywireのノード参加を促すための報酬を与える予定ですか？

**dr10**
あなたの構想している技術とサービスを消費者に提供するのはいつごろですか？あなたの実現しようとしているものを、いつになったら使えるようになるのですか？

**synth**

> 非チューリング完全なLISPのプログラミング言語を使っているとウェブサイトにありましたが？

それは何かの間違いでしょうね。そのうちに新しいウェブサイトが公開される予定です。
Skycoinのブロックチェーンにスクリプト言語はありません。効率性と安全性を確保しながら、最も速い処理速度とシンプルな設計を可能とするために、各トランザクションは定数時間となっています。
ただ、現在開発中のCXというプログラミング言語があります。Ethereumのスマートコントラクトなる遊びを超えた、次世代のプログラミング言語です。変更不可能なデータ構造を用いており、これは全く新しいものです。Skycoinのスマートコントラクトはオフチェーンまたはプライベートブロックチェーン上で処理され、メインチェーンに全てのデータを突っ込むようなことにはなりません。全員が他の人びとのコントラクトの内容をダウンロードして、ブロックチェーンを混雑させるような状況をわざわざ作るのか？他にもっと良いやり方があるでしょう。 

> 元々計画にあったように、SkycoinはSkywireのノード参加を促すための報酬を与える予定ですか？

はい、そうです。 We are going to get from 20% to 30% distributno of the coins, through network incentives for people running Skywire nodes, consensus nodes and services.
> Will Skycoin still have the node subsidy plan for setting up and registering the mesh nodes like originally planned?
I think this is going to be massive for marketing. And it is the best way to get the coins out to the users, instead of all the coins being held by whales

**samuelvihollandia**
I read how you suggest Skycoin could be used for VPN connections, is this the largest use case you see?

**arc-over-water**
Maidsafe has been working on the redesign of the net for about ten years, what are you doing the same and what different?

**synth**

> I read how you suggest Skycoin could be used for VPN connections, is this the largest use case you see?

No. This is just something easy, that we have working. Its not the largest applicatoin at all.
80% of internet traffic right now is bitorrent and the bitorrent sites are being systematically shutdown and driven off the internet. They wont go away, but will jut go underground. What.cd (largest music tracker, with 800k people) was just shut down, bakabt (largest anime tracker) has gone closed registration, Nyantorrent etc...
User communities of millions of people will be migrating from the clearnet (the existing corporate shit-net) to the "new internet". We are going to see people migrating by the millions, whole user communities of millions of people.

**arc-over-water**
Are you a corporation or foundation or charity? Registered? I am not sure i have seen anything about who you are? What is the dev team size? Background? - Maidsafe is open and clear so is IOTA and Stellar etc. Can you let us know who you and your team are? Especially you are talking about 15 year and up obligations..

**techbytes**
Do we need to hold skycoin to run Skywire nodes or consensus nodes like masternodes from other coins?

**synth**

> Maidsafe has been working on the redesign of the net for about ten years, what are you doing the same and what different?

Maidsafe is in version 2 or 3. Maidsafe will not have a real coin until version 9. Each version takes them about two or three years. Maidsafe will not be "done" or ready for atleast 18 years at this rate.
Skycoin has been in development for ~6 years and the meshnet for 4 years and it will be finished in a few months. To the poin that people can start using it.
Skycoin is similar to maidsafe in the objective, but has a different approach and architecture and primitives. We did not try to do everything, but focused on a smaller, tractable core and got that done.
There will be multiple projects in this space, but few teams are able to plan on the time horizon necisary for building a new internet or able to design each of the components of a system this large, or figure out how to do it so that it is useful at each stage of construction of a project that may take a decade. (edited)

**mike**
Can you see a way for Ark and Skycoin to build on each other in a synergistic manner? I'm all for not reinventing the wheel, especially when it looks like it will be replaced with antigravity like Skycoin.
I see Skycoin as essentially replacing TCP/IP and providing mesh network type functionality at the hardware level, Ark would run on top of it as a top level application layer.

**arc-over-water**
are you up to date on Maidsafe, they are nearly out of Alpha and its more like release early next year? But that being said, Maidsafe says once it is released it is like a virus or AI type, so does Tau Chain, and also Autonomic by HunterMinerCrafter, are we heading towards AI with Maid, Sky Tau and Autonomic?

**dr10**
smartbridge now! :kappa:

**mike**
So Skycoin would act as a sort of global decentralized cloud server to build on top of.
To communicate, it is more like sharing encrypted files to selected recipients than it is sending messages or hosting sites on a specific server.

**synth**

>Are you a corporation or foundation or charity? Registered? I am not sure i have seen anything about who you are? What is the dev team size? Background?

I think there are over ~60 people who have worked on Skycoin or have made major contributions. Its really a project from the darknet.
Many of the contributors are anonymous. Some of them have security clearances and were in the military industrial complex and one of them worked at the San Diego Naval Defence Research Lab and a lot of the idea for the networking protocols came out of public sector academic researched, funded from there.
We also have a lot of very very early Bitcoin people, hardcore crypto people that predate Bitcoin and an Ethereum core developer, etc..
On the Chinese side we have an early investor in Alibaba and telecom investor. And are doing pilot with china aviation group (owns four publicly traded airline companies) and apparently now Sinopec (which is 2nd largest publicly traded corporation in world).
Then we have people who are part of israeli and US intelligence and are probably doing some sort of money laundering or phychological operations background, who just showed up for some reason. This group seems very interested in the "applications" of these coins and how to improve tranaction privacy and the specifics of the CoinJoin protocol implementation. We got a lot of advice from people experienced in forensic accounting and what they wanted to see and where they felt Bitcoin was deficient and where it leaked metadata.
Then a bunch of PHD level people doing research into distributed database consensus algorithms and another group doing programming language research.
Then a lot of people from the deep darknet, anon, frog twitter and cipher punks and bitorrent communities. (really should be listed as two seperate groups). And people from the Russian darknet community. We have like eight Ivans. (edited)
> I see Skycoin as essentially replacing TCP/IP and providing mesh network type functionality at the hardware level, Ark would run on top of it as a top level application layer.

Yes. The key functionality is two things - connecting to people by public key (networking) - distributing self validating, immutble data peer to peer (transactions, blocks etc... content addressible storage)
And you can build almost anything on those two building blocks. The whole internet will eventually be rewritten on top of those primitives and it will replace many of the existing protocols.

**arc-over-water**
Who is the entity that is funding this? I think you have done 2 ICOs? How much did you receive? The first was 10c and the second was @ 50c per coin, released 6 million, is that correct?

**samuelvihollandia**
Are you planning to enter a different exchange market soon?

**arc-over-water**
Have you personally been in Sky from the start? What members have? Who allocates the ICO money etc... I hope you understand that decentralization with investment is a two edged sword, we invest in people but we cannot know these people.... So... we question.. (edited)

**thrice.pi**
with all these outside parties that helped to build skycoin and bring it where it is today who are the main core team who will help to keep all these cool features running. Will these outside parties be recruited for the long haul?

**synth**

> Who is the entity that is funding this? I think you have done 2 ICOs? How much did you receive? The first was 10c and the second was @ 50c per coin, released 6 million, is that correct?

The people who funded the project for the first four years, were early bitcoin and deep crypto people; who were unhappy with the fact that Bitcoin and the other alts did not seem concerned about the core issues at all. They gave us over 1200 bitcoin I think, over several years and did not ask for anything in return.
The early Skycoin devs were doing academic research, architecture and new algorithms. Prototyping and simulation. The later stage people were more project managers and doing implementation.
We did four ICOs for small amounts, to fund development and to allow developers working on the project to buy in. The first ICO I remember was at $0.10 per coin and the price now is about $4.00 per coin, so its up ~35x or 40x, but when you consider the Bitcoin price going from $100 to $3000, the increase has not been so much. lol (edited)

**arc-over-water**
With the price up 35x in about 1 year, is it not now time to cool the run up and release another ICO? At what amount of coins released and what procedure?

**mike**
Would Intel Edison or Joule, or Samsung Artik 10 work well as a Skywire wireless node? They have 2 Gb-8 Gb RAM, 8-64 Gg eMMC storage, 802.11n wireless, bluetooth, and some with Zigbee?

**synth**

>Have you personally been in Sky from the start? What members have? Who allocates the ICO money etc... I hope you understand that decentralization with investment is a two edged sword, we invest in people but we cannot know these people.... So... we question.

I think there wer three different groups that merged together in first three years, that had similar objectives. Because the code was in different language. There was python, C code and then eventually golang and the golang code became the basis for the current codebase.
The way the coin allocations work, is that it requires unamimious consent for releasing coins and it has to be for a specific, ear marked purpose and can be blocked by any of the devs.
Then there is a pool of coins in bitcoin for various project managers to allocate. And that is an operational fund for paying developers, contractors, marketing etc. Then different people have different responsibilities.
Then we also have corporate funding and sponsorship and some companies paying our full time devs etc, which helps a lot.

**arc-over-water**
Silicon Valley (TV SHOW) recently had their decentralized web running on a network or refrigerators? So i would guess, smart phones, smart gadgets? Home gadgets etc could add services and receive rewards from Sky?

**mike**
best would be a totally open source and publicly audited manufactured system on a chip for the nodes to prevent any backdoors. Even chip designers now don't really know what they're putting into the chips since they just drag and drop black boxes known as IP cores into the ASIC designs.

**synth**

>With the price up 35x in about 1 year, is it not now time to cool the run up and release another ICO? At what amount of coins released and what procedure?

I think the Skycoin price has been doubling every 40 days, for as long as I can remember. However, it will still be years before it is in the top 20, its still a long way to climb. It took bitcoin years to go from 0 to $1, even though it was growing at 1% per day the whole time for six years.

> best would be a totally open source and publicly audited manufactured system on a chip for the nodes to prevent any backdoors.

we are going to use arm

**arc-over-water**
IOTA is also working on their own hardware for nodes etc, Trinary asset is JINN

**synth**
all intel and AMD systems have remote management engine backdoors. So they are not safe for storing large amounts of coins.
We also have alpine linux and special version of linux, that is 6 MB and has everything that is needed for running our toolchain. It will not have any binary blobs in the kernel or anything that we cant compile from source. It does not have systemd and does not have gli, but uses musl. And does not have openssl.

**mike**
so looks like the Samsung Artik 5 and 10 can run it no problem, they're ARM based. 25x35x4mm package for the Artik 10, Artik 5 is smaller, less powerful but has 2 separate antenna ports, nice for mesh networking with an omni and a directional antenna.

**earlyarkinvestor**
how does Ark compare to Lisk?

**synth**
uploaded this image: 1923810435.jpg Add Comment

**earlyarkinvestor**
isn't Lisk trying to achieve interoperability between blockchains as well

**synth**
uploaded this image: 1433594905.jpg Add Comment

**synth**
uploaded this image: 1432540863.jpg Add Comment

**synth**
uploaded this image: 2049465686.jpg Add Comment

**mike**
nice! looks like an ARM based server rack
let me know if you need any help with it, see you're on solidworks, which I run as well.

**synth**
this is the skycoin cluster; it has 8 CPU boards; 4 cores per CPU, 2 GB of ram per CPU and 64 bit ARM processor. Only one program will run on each individual board, so there is compartmentalization and a physical gap so that compromising one process on a system does no allow all other processes on the system to be compromised

**mike**
looks like 2 ethernet ports per board.

**synth**
and the hardware does not have the qualcom backdoors and is actually chinese equipment; and the backdoors are normally at the kernel level because they are not at hardware backdoors yet
lol

**mike**
do they have SATA ports, maybe M.2 for storage?

**synth**
and we will hav an ARM openwrt router eventually too
this model does not have SATA, but we have a model with SATA; you could hook up 16 2 TB drives, lol and download half the piratebay to your cluster (edited)
the skycoin infrastructure is cluster based and designed for running across +300 computers, with one "node" deployed per computer. Eithe a CXO storage node, or a skywire SDN/meshnet node, or a VPN end point node or a consensus network, or skycoin node, etc. We have multiple node/application types.
so this is a "personal cloud' by itself
its not like StoreJ where you have other people storing your stuff; you are going to have ~5 clusters and 300 computers and can store your own files, on your own internet, on your own hardware. You do not need to go outside of your own network.

**mike**
Have thought it'd be nice to have a board with an array of M.2 sockets to run SSD arrays without all the cables, have the busses shielded in circuit board.

**synth**
yes, i think there will be m.2 eventually
these actually use a microSSD for storage, and its 48MB/s

**mike**
any idea on the pricing on your ARM boards in quantity? We are looking at Intel for Bitseed V3, but ARM would be good to stay with, especially using your boards if there is SATA.

**arc-over-water**
Do you have a general idea of usable functions to be released next in what order? The first release was the Coin and wallet, then the ICOs and can you give a general future with dates if you can

**synth**
the boards are $30 each and the memory for solid state, is actually more than the the cost of the CPU/RAM/board now. Which is sort of insane.

**mike**
so you have microSSD, what's maximum size? we shipping 1with Tb hard drives right now

**synth**
Bitseed mike is going to help with this; so we can pool the boards and do a custom PCB

**mike**
yes, that's where we see the price jumps, is in RAM and eMMC costs.
and it's hard to find low cost boards with SATA

**synth**
try the orange pi
the price goes up 30% for SATA

**mike**
yes, very nice specs.

**synth**
eventually, we will make one that has custom PCB and is a pluggable blade server, I think.

**mike**
I like the Samsung Artiks for the tiny form factor for drone routers, cubesat/picosat possibilities.
but like the fact that you are controlling much deeper down the supply chain with your boards.

**synth**
we only need ram, CPU, then microSD slot; and that is it. so the wifi and all this other stuff is just crap and its junk. We only have communication, storage and computation. So should be minimialist.

**mike**
yes, we use very few of the ports on the pcduino nano, no need for video, audio, IR

**synth**
there is even open source FPGA toolchain and a one instruction computer with subtract and jump if not zero; and if you have ram and a byte array, could even compile down to that; which is trolling, but for signing transactions or something, you could operate at that level.

**mike**
do you have a link for the FPGA. My favorite has been the ZYNQ 7000 series, but this sounds a lot lower cost.

**synth**
I have to ask about the FPGA

**mike**
Blue Canyon uses ZYNQ 7000 for their Cubesat bus.

**synth**
it is education company in shanghai

**thrice.pi**
i dont want to disrupt this communication u and mike have going on cuz its good to see you two discussing these things so please do continue..but i just a simple question that mike actually asked earlier which i didnt see a reply to..he asked what type of spes is needed to run a node for skycoin

**synth**
how much is it for cube sats for launch? 200 for 3 million?

**mike**
it has dual core ARM with an attached FPGA and both analog and GIO, PWM

**synth**

> he asked what type of spes is needed to run a node for skycoin

We are trying to keep to level where 2 Ghz arm board with 1 GB of ram can run it. ideally

**mike**
50K per 1U satellite was the going rate, but that is coming down a lot.

**synth**
skycoin is very minimalist; it much lower on resource usage than either bitcoin or ethereum; the bandwidth usage is less than 10 Kb/s
*10 KB/s

**thrice.pi**
thank u..yes it doesn't sound like much at all..thank you for your reply @synth
maybe i missed this answer but when is the next ico taking place

**mike**
so current Bitseed V2 can run it no problem. is dual core Arm with 1 Gb RAM, 1G ethernet and SATA, 4 Gb eMMC on board.

**synth**
the next ICO is just marketing event, but is july 20th I think
and it is just run up before largest exchange listings and marketing and PR push etc
oh, the dual core arm can run bitcoin and ethereum; that is amazing; ethereum should be CPU hog

**thrice.pi**
how long is it on for ?

**michaelthecryptoguy**
also techbytes had a good question >>>>>Do we need to hold skycoin to run Skywire nodes or consensus nodes like masternodes from other coins?

**synth**

> Do we need to hold skycoin to run Skywire nodes or consensus nodes like masternodes from other coins?

No. We want to have some kind of freemum thing. If you are not paying coins, the nodes will allocate 20% of bandwidth for the free tier
But you wont have congestion if you are paying, so much better service and speed, but we dont want people not being able to access a service or the network if they have no coins in the wallet
but we need to cap the resource usage of the freemium tier, so that it does not get out of control or clog the network

**michaelthecryptoguy**
:excellent:

**thrice.pi**
@synth the ico in july for marketing purposes that u mentioned ...is that pertaining to what mike asked about when he asked "Will Skycoin still have the node subsidy plan for setting up and registering the mesh nodes like originally planned?" (edited)

**synth**
it is easier to get people on network, without having to do anything; then they wil figure out the rest later and how to optimize it and setup a 32 node cluster and load coins in and learn linux and use a CLI and becoming a mining baron with a 10 Gbps uplink and physical cables to their neighbors and wifi nodes on their roof etc, lol

**thrice.pi**
lol

**mike**
so looks like you're using the Orange Pi PC, one of the connector ports is the USB, the other ethernet. http://www.orangepi.org/orangepipc/ . These are nice cards. orangepi.org orange pi pc - Orangepi

**synth**
eventually, if you have 40 Ghz and directional antennas, satilites or drones make sense for long haul or relaying traffic between cities. I think if we can get this working, the "miners" and hardware innovation will be insane.
We have guy who did PHD thesis on printing phased array and fractal antennas with organic semiconductor ink and he already wants to start companies to do antennas for skycoin "mining" hardware; but the software still needs a lot of work before they can start this insanity.

**mike**
yes, that's what we were waiting for with Bitseed, been doing BTC fullnodes in mean time.

**thrice.pi**
it seems skycoin is one hell of a coin..but it may be difficult to use for the everyday user to wrap their mind around..you think there is potential for something like ark to be used as a gateway to skycoin..so the everyday user can use something easy like arks network to link to something so broad, complex and revolutionary like skycoin ? @synth (edited)

**synth**
i will give you the solid works files, so you can start manufacturing these in bulk; we do not have factory and even assembling 30 units at a time is difficult for us

**thrice.pi**
sorry if this has been addressed..i may of blinked and missed it with all these great questions (edited)

**mike**
the antennas can be printed with graphene ink, have over 200 dB gain on a cubesat compatible form factor if done right.

**michaelthecryptoguy**
This would really help :dancing: people in third world countries turn into a :sun: (self :this:owned) Financial Services and Communications Company :bananadance::goodjob: :hadouken: Now we just need to find a way to get them a smartphone :partysaurus::tophat: (edited)

**mike**
would very much like to do that, maybe come up with packaging which takes a lot less time to assemble, lower cost. though makerbeam is cool...
that's been intent, have stationary nodes with storage, and open source modular mobile with mesh networking, which can achieve global penetration with secure, encrypted networking.

**synth**
yes, stationary, moving nodes creates a lot of problems
skywire only works because its it designed to run over point-to-point segments and not for "mobile adhoc networking" where people are moving around

**arc-over-water**
Do you have a basic program product release? Is it correct at them moment it is just the wallet?

**mike**
so the routing tables don't update that often?

**synth**
https://github.com/skycoin has a lot of different applications
https://github.com/skycoin/bbs works right now
the routing tables only change on new connection; so you make ~10 connections to a pubkey and if some drop you create new ones. so there is redundancy in the path and transit method. "diversity routing"
where as the direct connections between nodes are supposed to change less frequency, such as not more often than 10 seconds. Ideally never changing. any change to underlying physical connectivity, causes update cascade and is a change to network topology (should be minimized).
Where as connection dropping or routes being or connection established, does not change network topology and has no administrative overhead in bandwidth.
short range, mobile ad hoc routing needs to be handled by another protocol like BATMAN, while fixed infrastructure like WIFI hotspots, fiber between cities, ethernet cables etc is handled by the skywire stuff; so if you enter a coffee shop and connect and are there for 30 minutes, then you are fine; but if you are driving down the street connecting to different hotspot every 5 seconds, its not designed for that and needs another protocol layer for "mobile"

**mike**
so nodes can move if the transmission is not interrupted, like a beam forming antenna could do it as long as the beams can be moved fast enough to not interrupt the communication.

**mike**
so nodes can move if the transmission is not interrupted, like a beam forming antenna could do it as long as the beams can be moved fast enough to not interrupt the communication.
see update, they are ok even if some interruption.
makes sense though, works fine for having like mini cell tower and access points, hand held mobile is another protocol if moving from cell to cell.

**synth**
yes, phased array would be fine; or signal interrupted for second or even if signal goes out every hour for and hour and comes back on
but fundamental changes to network topology are more annoying, because everyone involved in routing across the whole network has to get notified; so you actually have to do the updates peer to peer, over CXO; and eventually network has to be segmented so that each node belongs to one or more routing/subscription domains that are partitioned in a sane way
in the current internet the number of hops between two people can be ~40 or 80 or just some insane number; in skycoin it will be 4 or a max of 7. etc, from house to neighborhood, to city, to city/country and then to destination. It wont appear as 40 physical hops, that can each have their own independent congestion
the advantage of phased array, is that you just throw it on your roof and it can scan for whoever it can connect it; and then can connect to different people or best person, without having to climb up on roof and ajust anything; the beam focus is on software control
i like the BBS and VPN, because we do not need to build a physical new internet to run them; we can just tunnel over the existing internet and its useful. It will take years before we see a hardware alternative to the existing internet. Even people are installing 100,000 nodes a month and its growing at 1% per day, it would still take 10 or 15 years until it could replace the existing internet.
There is just so much equipment installed and even if growth rate is massive, it will take forever.

**mike**
yes, this is what i like about it, much easier for automated set-up than pointing antennas, even with motorized directional. had thought of using low frequency for nodes to transmit gps coordinates to locate each other, then point highest possible frequency for range to connect at each other.

**synth**
the VPN will be big application; hardware vpn, whole house VPN; you plug it in and it VPNs your whole house and all your connections
the ISPS are allowed to sell all the data they collect now
and you can start hardware blocking the IP addresses for ad servers and tracking servers and so on; and different vpn end point for each device on the lan and be able to rotate them out automatically
what will happen, is that all the torrent sites and communities will be driven underground; and when that happens, the downloads will eventually be blocked or slowed by ISPS and you will need a "new internet" to really get a lot of the content that is available to people now.
Five years ago, there was no point in doing this. Today the motivations are emerging, that will drive people to something new
and another thing is that reddit has been overrun with bots; controlling all the upvotes and content now. And corporations have completely taken over and subverted facebook and twitter.
People are going to be looking for decentralized platforms and there will be a mass movement to the platforms that can solve the bot manipulation problem, the shilling problem and the company owned by corporate money whore sellout problem.
so there were attempts at a building decentralized twitters and facebooks, but five years ago there was not a need; now people are ready to siwtch and the technology is ready.
the skycoin project is building the base layer, then the communities are building their own projects. We are just giving them the tools.

**mike**
Yes, like as an example, twitter made my sign-up email public, had no idea, was getting spammed all the sudden, finally found out why when I went to twitter to stop getting multiple copies of a privacy notice.
Would very much like to bridge skycoin with Ark, so Ark runs on top of this VPN, and advantage is that your VPN is trustless, or at least much more decentralized than relying on a single VPN provider, which is 100% reliant on trust.

**xano**
How do you feel the incredible potential for illegal activities will affect the future of Skycoin and mass adoption?

**charles**
I also don't quite understand how skycoin solves the bots on reddit

**xano**
Almost everyone loves free movies, series and music, but what if ISIS starts using it for example

**synth**
now, on twitter; for instance hillary clinton campaign paid twitter money for "brand management" and if 300 people you follow said something negative about her, you wont see any of the tweets. And 1 person in 4000 says something positive and everyone in the that persons followers, will see the tweet in the feed!
The companies are controlling what people see and what information is allowed into their feeds. Its not organic anymore. Its not based upon your preferences. It is based upon making the platform friendly to advertisers, who can pull their money out. They are pushing social agendas even and requiring the companies they are giving money to, to censor particular people and movements, to keep the advertising money.
Even Google is being forced to comply with these demands. Fortune 500 pulled out 700 million/year in ad revenue and then google agreed to censor search results to please the advertisers. And then they are threatening them with fines in the EU unless they comply and serve the governments and corporations.
Decentralized social media, means that you own your own data. It means that you control on your computer, the algorithm used to sort and prioritize your feed. Instead of allowing it to be controlled and manipulated by a third party, who is a whore for money trying avoid being fined by the EU and groveling before soap companies threatening to pull their ad money out, unless they censor things.
yes, ARK could use skycoin network for block and transaction distribution. And could use it for networking, to avoid blocking.
And ARK could be deployed as a node in the same framework as skycoin. in the skycoin clusters.
There is https://github.com/skycoin/viscript and we can add ARK here. This is a cross platform CLI, and application launcher and for cluster management eventually.

**mike**
thanks! will post to our devs. we have and are adding a lot of API's and CLIs for different languages.

**synth**

>I also don't quite understand how skycoin solves the bots on reddit

It is outside of skycoin project, but the people building the BBS has a really cool filtering algorithm. Everyone is identified by their public key and can build out a web of trust. And its like page rank for users.
Its a decentralized type of moderation, that is automatic.
is ARK in golang?

**jarunik**
Ark chain is in Javascript but we got a golang api.

**arc-over-water**
Why golang over rust or scala?

**mike**
Ark core is written in node.js , may be ported to go. There is a go api/cli being written, by @chris I believe.

**arc-over-water**
when will there be a lisp coin platform :slightly_smiling_face:

**mike**
golang is done? nice!

**boldninja**
https://github.com/ArkEcosystem/ark-go GitHub ArkEcosystem/ark-go ark-go - Ark GO client for ARK.io blockchain ecosystem #golang #ark #blockchain

**mike**
lisp - that would be fun! Continue to be amazed lisp is still around, but popular for machine learning apps. yes, we need lisp added, can you do it arc-over-water?
lisp seems to have good function for parallel processing but don't know details myself.

**arc-over-water**
now there is Shen.. http://shenlanguage.org/

**synth**

>How do you feel the incredible potential for illegal activities will affect the future of Skycoin and mass adoption?

The people selling drugs will love skycoin. Bitcoin was worthless until people could buy drugs with it, then it was money and it went from $0.01 to $1000 in a year.
When the internet was created, the first thing people were doing was downloading porn. When bitcoin was created the first thing people were doing was buying drugs and guns.
ISIS does not need skycoin, because they are using xbox messanger and facebook messanger. They do not need crypto. Every terrorist attack means budget increases, so the government loves ISIS. Terrorism is big money and the more terror, the more money there is to make. People are making too much money off of ISIS for them to get rid of the problem any time soon.
Pedophiles were also the first ones to adapt stenography, i2p, tor, tails and bitmessage. They are always the first ones testing out any new crypto stuff. You should look at the logos of the stenography apps and you can guess what kind of people wrote these applications.
Even two years, before skycoin was launched the intelligence and money laundering people were already showing up and giving lists of requirements for scrubbing or hiding metadata.
If I was building the next silk road I would be looking at tech like skycoin is building. I think everyone has had that idea.
We really cannot control what people are going to do with this. Its just inevitable progress and its going to happen whether we do it, or maidsafe does it or someone does it. Its going to happen. (edited)

**mike**
looks interesting. have you seen julia, https://julialang.org/ . very impressed with its benchmarks, comparable to go
think the best way to end terrorism is to end foreign interventionism. Last I knew, Switzerland doesn't have a problem with terrorists.

**arc-over-water**
killary and obomba

**michaelthecryptoguy**
Sad but true.

**mike**
and the bushes

**synth**
uploaded this image: Screenshot from 2017-06-29 14:42:25.png Add Comment

**synth**
uploaded this image: Screenshot from 2017-06-29 14:41:55.png Add Comment

**arc-over-water**
fake news on an amazing level... sandy hook.. 911
moon landing... Stephen Hawking...
anyways..

**charles**
North Korea also does not have a problem with terrorism :)

**arc-over-water**
Sky! the limit

**mike**
don't even have to go to that level, just the current ongoing farce about Russian intervention in the election and supposed ties to Trump team members. War is the health of the corporate state.

**synth**
terrorist attacks are now advertising events for nike; they are fighting each other for who gets the product placement in the latest ISIS attack. It keeps people glued to their televisions and otherwise people would not watch the news. Even terrorist attack keeps people on the television and the fortune 500 fight each other, to get the ad spots for the people glued their television.
The governments and companies race in, like sharks with the latest "surveilence" bill to get the governments to buy billions of dollars of useless equipment from them. The government agencies all rush in to influence the press and get budget increases passed.
Its just insanity. They only care about money.

**mike**
it would be very inconvenient to improve relations with Russia for those making money and expanding power over escalating global tensions.

**arc-over-water**
wasnt the first main scandal trump attack that he weed on some prostitutes in Russia. OMG

**synth**
they have oil companies and russia produces oil; so hey want any execuse for "sanctions" to force people to buy their oil instead of russian oil. They would do a war, just to stop any Russian oil pipeline to Europe.
It just about money.

**arc-over-water**
Putin is actually kicking some ass with his speeches the last years.

**synth**
if russia gave me free prostitutes, I would pee on them too, lol. Why not? (edited)

**mike**
don't forget Pussygate - the press sat on the tape for 10 years until 3 weeks before the election, instead of during the primaries.

**arc-over-water**
crazy shit out there...
time for crypto to shine..

**xano**
I just wonder how services like mega would have ended up with Skycoin

**synth**
the "Y2K" was also excuse, to sell tens of billions of dollars of "upgrades" to government and corporations. They told them "give us your money or the sky will fall".
terrorism is the same story, its just turned into a money making scam. 90% of the surveilence crap is just companies finding excuses to lobby the government to buy over priced equipment, so they can make money. They do no even know what to do with the data they collect. They are doing insider trading and rigging markets and all sorts of crap with the data and then panicing when people start using HTTPS because its harder for them to keep making money the same way.

**arc-over-water**
Mega2 is about to show its prototypes

**synth**
you have mom and pop local police departments, buying $150,000 string ray cell phone interception equipment that is NSA level, who could not even afford it, but its paid for out of 10 billion dollar DHS "terror" fund to buy useless equipment for local police. To "fight terrorism". Its really a joke.

**arc-over-water**
Sky list of aims over the next two years?
Next ICO cost and how it will be released?

**synth**
people know that companies like apple and goolge are required to hand over all their data to the government. including messages, so why would anyone use imessanger or icloud?
So they are staging fake events with "police cant break the 4 digit pin on an iPhone and its unbreakable" when they can actually trojan the phone from the carrier, etc and have all sorts of insane mandatory backdoors.
So we are heading towards a decentralized internet and these new apps, as people get sick of being tracked like animals.

**michaelthecryptoguy**
@synth What is your background? Can you tell me a little about your prior experience, regardless of what area it was in? (edited)

**synth**

> Sky list of aims over the next two years?

Get meshnet working Get BBS and first demo apps working Get VPN working and get it to users List on more exchanges Build up community Improve the wallet, fix website, translations into more languages ec

**arc-over-water**
Also the two Chinese guys who wrote the technical whitepaper, the scholars, are part of the team?

**synth**
@synth What is your background? Can you tell me a little about your prior experience, regardless of what area it was in?
I did a lot of things. video games, hedge fund/finance, crypto, investment stuff etc... Now am I a sort of project manager.

**charles**
How will the price of skycoins be determined for the next ICO, I, suppose it cannot be above market price, else people would not buy it, but too far below would depreciate the coin

**arc-over-water**
do they want high price at this point or well even distribution to the best placement of people?

**synth**

> Also the two Chinese guys who wrote the technical whitepaper, the scholars, are part of the team?

One of the chinese guys has nothing to do with it. He is a professor that put his name on paper his graduate student published. And now the professor wants to hide the paper, because he thinks the chinese government is cracking down on bitcoin; but he is wrong and the government doesnt care and the paper is in english so they cant read it anyways.
And the other one is a core ETH developer. Chen was core ETH and wrote the golang implementation of Ethereum. He is not very public and does not want to be in spotlite or bothered.
most of the contributors for skycoin are in the background or hiding actually (edited)
many of the ETH people are all whoring themselves out to advisor boards to various tokens, or dozens of tokens and ICOs; but most of the serious crypto people are very private and hiding themselves. They do not want to be known, do not want to promote or advertise themselves and they are in the background.
Or they have too much money already and just want to hide. They are also lazy because they do not have to work anymore, or they are busy with other things.
they also want to avoid taxes and being targetted for theft and do not want attention from government
skycoin cannot have a "Team" or "Advisor Board" on website, because we asked everyone and no one wants to be public or wants to be in a public position....

**arc-over-water**
yes best to live in a country your not citizen of and earn money from a country your not living in... Been doing it for ten ears, way less stress, (edited)

**synth**
many early bitcoin people, who identified themselves publicly on twitter; they cannot travel to brazil or certain countries without risking being kinapped and ransomed for money
lololol

**arc-over-water**
vitalic knows kung fu maybe,,, well he speaks Chinese..

**charles**
Do you think skycoin not having a public figure will negatively affect adoption?

**arc-over-water**
i think it has.. 6 years on and quiet forums and slack

**synth**
we can buy public figures or an adviser board; but they would not have anything to do with project except to put their name on it to create confidence for public; which is what all these advisor boards really are

**arc-over-water**
in the background assuming tek development.
Next ICO cost and how it will be released?
github is always active...

**synth**
i really do not know
about the next ICO

**arc-over-water**
ok

**synth**
it is around the 20th of next month. and will be 1% to 10% of the skycoin. I am not sure the exact number is set
and it will probably be a fixed price

**dr10**
this ama is a marathon :trollbounce: nice!

**arc-over-water**
how much of the 100 million is obligated to your team and the people who funded it?

**synth**
but then followed by a weekly auction or second priced auction for a fixed number of coins, that will occur every week for 8 weeks; but not sure how many coins or if it will actually happen

**arc-over-water**
so if its a high price it is 1% and low price it could get to 10%

**synth**

> how much of the 100 million is obligated to your team and the people who funded it?

The people who funded skycoin, did not receive anything for it. They have no entitlement to the coins.
they had to buy in at ICO like everyone else. Even the developers working on it, had to buy in.

**arc-over-water**
ok so they have already been looked after in the 10c ICO round

**synth**
i think the next ICO is mostly marketing event, and to "get it over" with. We are in a bubble now, so we should raise money now, before the ICO bubble pops. Is what people are telling us.
we cannot spend more then 50 million, so selling an insane number makes no sense. 10 to 15 million is probably reasonable, for next 3 years. And that is with a really good full time marketing team, and trippling number of developers AND funding several parrallel hardware projects.

**mike**
My approach to Skycoin is regardless how much of a financial return it might provide, it is an investment into producing a future I want to see.
Also look forward to earning it by running nodes.

**arc-over-water**
So that could be you release 10,000,000 coins and get $10,000,000 dollars for your covering expenses next three years

**charles**
Can a person with limited technical capabilities run a node?

**arc-over-water**
or $20,000,000 as it goes

**synth**
the people who are going to pump the coin, want us to sell off as much as possible. They are pressuring us to do that.
However, if we sell fewer coins, then the price per coin will be higher.
If we only sell 10 million in coins, then the price can go up a lot higher than if we sold 500 million in coins.
I think EOS is going to raise a billion dollars and I have no idea what they will with the money, except use it to buy EOS and drive the price up or some scam. They are not going to spend it on development. lol
> Can a person with limited technical capabilities run a node?

eventually, yes. maybe not right now. after tutorials, yes

**arc-over-water**
EOS seems like it is trying to go bear bones and not be as complicated as ETH...

**mike**
I think it is smart to hold a lot for distribution to node operators as a replacement to mining for a good distribution, also selling some to have distribution among those who are interested but not technically inclined to run nodes.

**synth**
So that could be you release 10,000,000 coins and get $10,000,000 dollars for your covering expenses next three years
The coin price is like $4 or almost $5 at high. It will be at $5 by ICO I think, atleast. The market cap has doubled every 40 days, for a while now.
10 million coins at $5 per coin, is 50 million.
We have to distribute coins via the skywire nodes, to make it fair; because ICO is not a good way to get coins into the hands of users. Its only good for fund raising and for whales.
We decided that we will distribute most of the coins to users and just use sales to whales, to fund development.

**arc-over-water**
there must be ways to spread to diverse groups the 10,000,000 coins?

**synth**
the problem is that all ICOs end up going to less than 20 whales

**arc-over-water**
every member of a altcoin slack gets a coupon invite
If an ICO knows their customer that can be prevented..

**synth**
there are people who own a large percentage of ETH and they want to diversify; they can gamble 20 million in an ICO and could make 50x more, but if they lose it, then its a slight loss; they have so much ETH that they cannot even sell it or convert it, without tanking the market

**arc-over-water**
in one day every altcoin slack member of every altcoin could get a btc address used once in their pm, allowed a max amount sent etc..

**synth**
yes, ideally, that might work
we have been doing OTC sales at market price; with a cap of 10 BTC and that works well

**arc-over-water**
do the OTC reflect in the blockchain? (edited)

**synth**
but we have single whales that want to put in 700 BTC and each one individually, is larger than whole individuals doing the OTC sales
OTC is "over the counter", or direct sale; when people private message a developer and ask to buy

**arc-over-water**
ok so private sales are happening

**mike**
uploaded and commented on this image: TEC chart.png 1 Comment Here is a sample method based on power law for pricing I have planned for Ark based Token Exchanges for projects, including funding Ark/Skycoin based nodes. As more as sold, the price increses by a power law so people can enter at the irsk and expected ROI combination they feel comfortable without being pressured into hasty emotional decisions by FOMO.

**mike**
*irsk=risk
so entering on any part of the curve looks the same as any other part.

**synth**
hmmm
how does this work?
the more money you put in, the more you pay?

**arc-over-water**
but as you do these OTC sales it reflects here in distributed? http://explorer.skycoin.net/blocks

**mike**
here is a link to the spreadsheet, has the formulas and table of calculations for the graph, https://docs.google.com/spreadsheets/d/1en9lqzBIuHgp0-Q3ohoq3yJUe1lJcOK9U4bF2TiXZew/edit?usp=sharing
yes, the more that is put in, the higher the price.
it will take some experience to determine the best parameters to prevent instant sell-off while not stalling the exchange indefinitely, and different project might be best suited for different exchange rates over time period.

**synth**
we have a really good strategy now
We can distribute coins to top content producers on the BBS
to people doing bountries (like skycoin logo, sticker design etc)
to people who want to do development (mobile wallet etc, some features for bbs and bug fixes)
Then massive substained distribution, over time to the people running the skywire nodes.
Then disribution also to nodes hosting content on CXO.
Then distribution to people coming on to platform who are bringing user communities with millions of people (we have been talking to these people for years and they do not have real developers, so we have to help them; they only have web designers and curators and community managers but cannot actually develop anything new).

**mike**
like a long term term ArkSpace project for space exploration and development will be sold over a lot longer time frame than funding an index coin bridged to Ark.
yes, and either way, the project can award blocks of tokens to contributors other than just for money.
I'm a fan of the Slicing Pie method.

**arc-over-water**
Ok so your saying it will be between 1%-10% next month to get funding and start the marketing campaign. Then after that distribution then there are monthly small releases of ICO and the majority being bounties for services rendered. and nodes etc

**mike**
http://slicingpie.com/ Slicing Pie Perfect Equity Splits for Bootstrapped Startups Slicing Pie is a formula that allows founders to create a PERFECTLY FAIR equity split between founders, investors, partners and employees. (92kB)
Skycoin is very similar, but doing it manually with adjustment.

**synth**
yes
what i am interested in, is if we can block the BBS up and get alot of users with the incentives
every dollar in coins we sold over OTC, drove the skycoin market cap up $4
we would sell coins, then price explodes the next week; because people promote it on twitter and blog about it
skycoin needs to get on more exchanges

**synth**
I have to sleep now. LMAO. We should end AMA soon

**arc-over-water**
cool thanks for your time... haha 3.17 am here

**synth**
4 hours?

**dr10**
XD

**synth**
is there an archive for the AMA?

**dr10**
reddit hopefully :joy:

**michaelthecryptoguy**
Thank You for taking your time to answer everything in complete detail. It was nice that you cared enough to make sure everything was answer very thoroughly.

**boldninja**
@michaelthecryptoguy can you copy everything and make it reddit friendly?
thanks @synth for taking the time for this AMA it was :mindblown: really interesting stuff

**techbytes**
marathon session today.

**michaelthecryptoguy**
I sure can. As long as jarunik hasn't already started. (edited)

**mike**
Thank you very much for joining us synth, please stop by again.
I will also be continuing to check in on skycoin slack for updates as well,
[skycoin.herokuapp.com](https://skycoin.herokuapp.com)
The closer the integration of Skycoin with Ark, the better.
