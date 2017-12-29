+++
title = "Telegramログ - ホワイトペーパー、Slavery and Anarchy"
tags = [
    "Ask the Developers",

]
bounty = 20
date = "2017-09-18"
categories = [
    "Ask the Developers",
]
+++

**Artem Kotelskiy**

こんにちは。

Skycoinのテクノロジーの核である「Obelisk合意形成アルゴリズム」に関する論文が、重大な欠陥があったのを理由に「arxiv」から取り下げられたと聞きました。本当ですか？

Skycoinチームの皆さんに確認していただきたいと思います。よろしくお願いします。

**Monty Crypto (Xa no)**

Obeliskに関する論文ですか? 少なくとも5つの論文がObeliskの理論的基礎を主旨に書かれていますが、Obeliskについて直接触れられた論文の存在は確認されていません。

具体的にどの論文が取り下げられたかわかりますか?

**Synth** *[Artem Kotelskiyへの返答]*

取り下げの理由は欠陥ではありません。著者のChen氏が論文を取り下げた理由は、arxivの代わりにACMジャーナルを引用元にしようと決めたからです。学問の世界でACMジャーナルは非常に権威あるジャーナルとして知られていますから。

**Synth**

付け加えると、Chen氏は論文のなかに小さな間違いがあったのを認め、１つの論文を取り下げました。しかし、この修正点は論文の主旨に関わらない、小さなものでした。

その論文に書かれたアルゴリズムは第三世代のもので、私たちは現時点で第５世代にあります。その実装のためのホワイトペーパーが書かれなければなりません。

**Artem Kotelskiy**

https://arxiv.org/abs/1507.03927

このページによれば、論文の欠陥は理論的な性質のもので、致命的だったとあります。

**Synth**

Chen氏は自分が何を言っているか理解してないのではないでしょうか。

**Artem Kotelskiy**

「Opinion Dynamics」に関する論文にも同じようなミスがあったと述べられていますが。

**Synth**

１つの論文にはミスがありました。論文が掲載される何ヶ月か前に、私が指摘しました。

**Synth**

このミスは論文の根幹に関わるものではありませんでした。 エネルギー最小化に関するものであり、統計的物理学の分野です。

Chen氏は全順序集合に基づいた奇妙なハッシング関数を考案しようとしていました。これは機能しませんでしたが。 

**Artem Kotelskiy**

それでは、Skycoinのウェブサイトにあるホワイトペーパーは「arxiv」に掲載されたものではないのでしょうか?

「arxiv」のコメントは個人的に気になります。論文の著者自身が理論の欠陥を指摘しているのは、何かおかしいような気がします。

**Synth**

この理論に関しては全部で８本の論文が書かれています。

最新の論文はACMジャーナル/学会に掲載されています。

**Artem Kotelskiy**

その論文のリンクをいただけませんか？

検索しても見つけることができませんでした。

**Synth** *[Artem Kotelskiyへの返答]*

Chen氏は教授職に就いています。共著者が論文の取り下げを希望したようです。ブロックチェーンに精通していない人物でした。中国政府がブロックチェーンに規制をかけていると彼は思いこんで、論文がトラブルの原因になるのをおそれたようです。

**Synth**

http://njtech.findplus.cn/?h=search_list&query=AR:%22Shu%2C%20Jiwu%22

**Artem Kotelskiy** *[Synthへの返答]*

この点はウェブサイトで明らかに示されるべきだと思います。SkycoinプロジェクトはObeliskのセキュリティにかかっているわけですから、他のコンピューターサイエンスの専門家によってアルゴリズムの理論的基礎が評価されていなければなりません。そして、その事実が人びとにもはっきりわかるようにウェブサイトに書かなければいけないでしょう。

単純に、コンピューターサイエンスの専門家でなければ、論文も理解できませんし、理論的基礎の正当性をチェックすることもできないからです。

**Synth** *[Artem Kotelskiyへの返答]*

実装と詳細に関する、４０~６０ページの第三世代のホワイトペーパーの掲載が予定されています。しかし、他の仕事との兼ね合いのため、完成には時間がかかる見込みです。

シミュレーションは成功して、相互評価も機能しています。第一世代の実装を近いうちに行い、現実でどう機能するかを公表していく予定です。

**Synth** *[Artem Kotelskiyへの返答]*

ちなみに、Chen氏はEthereumのGo実装を行った人物です。

**Artem Kotelskiy**

Chen氏、つまり、Jiwu氏ですか?

その情報もウェブサイトに掲載するべきだと思います。遅れましたが、丁寧に質問に答えていただき、ありがとうございます。 

**Synth**

論文は学会でトップ２のジャーナルに掲載されました。分散型データベースの合意形成のためのACMコンピューターサイエンスジャーナルで、 もちろん他の研究者による相互評価もされています。

他の研究者に相互評価された論文とシミュレーションを基礎にしているのは、数ある仮想通貨のなかでもSkycoinだけです。

**Synth**

はい、Ethereumの開発に携わっていのたはChen氏です。

**Artem Kotelskiy**

それは知りませんでした。

Chen氏がEthereumの開発に携わっていた証拠はありますか？

リンクを教えてください。

**Synth**

Chen氏の要望により、ウェブサイトに情報を掲載することはできません。Skycoinの開発に携わる人々の８割から、アドバイザーやデベロッパーとしてウェブサイトに名前を掲載しないようにとお願いされています。様々な理由から身元を明かしたくないようです。

**Artem Kotelskiy**

それはまた別の問題ですね。

わかりました。

しかし、何故ですか？

**Synth**

中国の場合はbitcoin規制の可能性を懸念して、また、アメリカの場合は税金や雇用の理由からだそうです。 

**Artem Kotelskiy**

それは何だか怪しいですね。（笑）

スイスに行けばいいのではないですか？

検索してみたところ、チェン氏とEthereumの関わりの証拠を見つけることができました。

**Monty Crypto (Xa no)**

数ある仮想通貨の中でも、レポジトリ、開発記録、論文などの資料が揃っているのはSkycoinくらいでしょう。何の役にも立たない顔写真や名前がないからという理由でSkycoinを怪しいというのはどうなのでしょうか。

**Synth**

Chen氏の公開鍵はEthereumデベロッパーのレポにありますよ。彼のgithubを確認してみてください。 

**Monty Crypto (Xa no)**

私からすれば、製品に関するコードの一行も公開していない数多のICOの方がよほど怪しいと思うのですが。

**Synth**

ウェブサイトやアドバイザー欄に名前を掲載できない約束になっていますが、coinbaseトランザクションが重複してアウトプットされる問題を発見したbitcoinのデベロッパー、その他２人の主要なbitcoinデベロッパーもSkycoinの開発に深く携わっています。 

これには色々と事情があるのです。

例えば、bitcoin初期デベロッパーの情報が漏れた際、オーストラリア政府は情報漏れから８時間以内に家宅捜索を行いました。

また仮想通貨のデベロッパーの多くは国家機密情報に触れる立場の人物で、雇用契約があるために仮想通貨の開発が公にされることを望んでいません。

**Artem Kotelskiy** *[Monty Crypto (Xa no)への返答]*

「怪しい」と言ったのは冗談ですよ。（笑）

**Synth**

githubに本名で登録しているのは運用上のセキュリティ概念のない素人だけでしょう。加えて、Skycoinプロジェクトの関係者は、アドバイザーというタイトルや売名行為に興味のないデベロッパーです。

Chen氏が自身のメイン/パブリックgithubアカウントを使っている理由もわかりません。そうしないようにとアドバイスされたはずですが。

**Artem Kotelskiy**

納得しました。説明をいただきありがとうございました。

**Monty Crypto (Xa no)**

いえいえ、けっこうですよ。

**Artem Kotelskiy**

Skycoinに関して引き続き情報を集めていこうと思います。

デベロッパーの身元はいずれ公に明かされることになるのでしょうが。

**Synth** *[In reply to Artem Kotelskiy]*

８年も続く開発の歴史です。映画も作れるような濃い内容ですよ。

**Synth** *[In reply to Artem Kotelskiy]*

身元が割れることはないでしょう。いまだbitcoinの初期デベロッパーの身元すらわかっていないのです。

**Artem Kotelskiy**

そう願いましょう。

しかし、なぜスイス移住は選択肢にないのですか？

また、SkycoinもEthereumのように透明性の高い開発環境にすればよいのではないですか？

**Synth** *[In reply to Artem Kotelskiy]*

なぜスイスなのですか？

プロジェクトに携わる８０人をスイスに移住させるのですか？

**Artem Kotelskiy**

そうですね、組織の本部をスイスに移せば、保護を受けられるのかなと思いました。

**Synth**

開発はgithubで行われているので、本部の場所は問題になりません。

何からの保護ですか？Skycoinの開発チームが攻撃を受けた例はまだありませんが。

**Artem Kotelskiy**

Skycoinとの関わりを公にすることをデベロッパーは避けていると言っていたので、保護が必要なのかと思いました。

しかし、なぜ身元を明かさないのですか。

**Synth**

税金の関係です。

**Artem Kotelskiy**


いや、半ば信じがたいですね。

なぜ税金を払いたくないのですか？

**Vadim 🛌**

なぜ税金を払いたいのですか？

**Monty Crypto (Xa no)**

そうですね、みんな税金を払いたいと思っているでしょう。（笑）

**Artem Kotelskiy**

Skycoinのプロジェクト発展と税金を払わないことに何の関係があるのですか？

説明をお願いします。

**Monty Crypto (Xa no)**

脱税と節税は異なります。

節税は合法であり、世界中の企業が行っています。

**Synth**

例えば、あなたが800万個のbitcoinを持っているとしましょう。それを公に明かしたいと思うでしょうか？

国家機密情報保護義務や秘密情報保護契約にある人々がウェブサイトに顔と名前を掲載したいでしょうか?これらの人びとはフェイスブックアカウントを持つことも許されず、他の顧客の名前や情報を明かすことができません。

また、雇用主との知的財産権の問題があります。ある企業の例では、従業員が勤務時間外に作成したものでも、企業に所有権があるとされています。 

このためデベロッパーの身元を明かすと、雇用主や企業がオープンソースのプロジェクトに関する所有権を要求できてしまいます。

これとは別に、でまかせや複雑な人間関係があります。能ある鷹は爪を隠します。逆に、売名行為に働く人びとは往々にして実質が伴っていません。

Bitcoinの初期デベロッパーの全員が、アメリカ政府の理不尽な介入を懸念していました。その懸念は現在もなくなっていません。

仮想通貨の世界に最近入ってきた人びとは、19９０年代の仮想通貨抑圧の歴史を知らないのです。

**Vadim 🛌**

人びとが仮想通貨に関わる人びとの匿名性を問題にするのが、逆に私には不思議に思えます。

**Artem Kotelskiy**

秘密情報保護契約は個人的に気に入りません。

有能な人びとは秘密情報保護契約など結ばないと思っていました。

しかし、私が間違っていたようです。

企業との契約がありましたか。

つまり、デベロッパーと研究者は自分の金が心配で、Skycoinやその他の大規模なプロジェクトは決まりを押し付けているわけでしょう。 信じられません。

**Synth** *[Vadim 🛌]への返答]*

世の中はなんとも不思議なものです。

そして、数学や暗号の専門家は、全員と言っていいほど政府や軍のために働いている事実も忘れられているようです。

**Synth** *[In reply to Artem Kotelskiy]*

Fortune500やGoogleのような企業で働いていれば、秘密情報保護契約は常識です。 開発記録を見ればわかりますが、GoogleやAmazonで働くデベロッパーもSkycoinのプロジェクトに関わっています。

**Artem Kotelskiy**

研究者が本当に気にしているのは自身の身の安全のみでしょう。

GoogleもAmazonも大した企業だとは思いませんが、従業員はたしかに優秀かもしれません。

なんにせよ、要点は理解しました。

しかし、数学の専門家については誇張が入っていると思います。 私の知る限り、純粋数学の研究を離れて軍に入る人びとが最も優秀なわけではありません。

**Synth** *[Artem Kotelskiyへの返答]*

Googleをはじめとして、大企業は従業員と次のような契約を結びます。「我々はあなたを所有しています。勤務時間内外にかかわらず、あなたの労働は私たちの所有物です。」

これはFortune500の企業に例外なく当てはまります。 これらの企業で働き始めると、デベロッパーはオープンソースプロジェクトに関わるのをやめてしまいます。

**Artem Kotelskiy**

なるほど。それは残念ですね。

**Synth**

加えて、アメリカでは情報や研究が一般に公開されたあとでも、機密情報として分類することが可能になっています。

例えば、研究者が政府から助成金をもらってソース・ルーティングの研究を行い、研究成果が発表されたとしましょう。後のプロジェクトでこの研究成果が使われた場合、研究者は機密情報保護に関する法的責任の範疇にあります。

また、大学で働いている場合、研究者が開発したアルゴリズムに大学が知的財産権を要求することもできます。

このため、アメリカ市民は弁護士を怯えながら生きているのです。

**Artem Kotelskiy**

なるほど、アメリカの大学や企業がそんなことをするとは驚きです。

説明をいただきましたが、それでも私は自らの論点を譲りません。

Skycoinのホームページで、デベロッパーの身元が明かされていない理由を説明すべきです。

**Synth**

例をあげれば、Stanford、Cisco、Googlerなどでしょう。

**Artem Kotelskiy**

しかし、説明をホームページに掲載すると注目を集めてしまいますね。

**Artem Kotelskiy** *[Synthへの返答]*

それらの大学や企業での知的財産権問題に関するリンクや、キーワードを教えてください。

**Synth** *[Artem Kotelskiyへの返答]*

githubに開発記録は残っているので、実際は身元が隠されているわけではないのですが。人びとはgithubを調べる能力もないのでしょう。

Skycoinは著名なデベロッパーをアドバイザーとして雇っているなどと広報する必要はありません。

ウェブサイトはコインと技術の情報が掲載される場所です。アドバイザーの有名度で競い合うのは無駄なことです。

**Artem Kotelskiy**

Lol, account on github also doesn't add anything, although I admit that there are accounts there which have other social media

You know, I don't advice you to advertise yourself

Not at all

In fact I hate all these bright "team" pages and stuff

But here is one simple thing

I like the project

The future of the project is in hands of developers completely

So it would help if I know who they are, and what are their values

For me to decide, if I am going to be the sky node, or simply sky hodler

But I get it, you think that code and execution speaks to itself, fair enough

**Synth**

You go dox yourself and report all your stuff to the government and go pay your taxes to the central bank that owns you. All human cattle, please line up for bar coding.

Its the exact opposite of why bitcoin was created.

**Artem Kotelskiy**

Yeah well, there are different degrees of being crypto anarchist

**Vadim 🛌**

being one in words and in reality?:D

**Artem Kotelskiy**

I tend to believe that declaring a war to the previous governors doesn't help pieceful transitioning to a better system.

I might be wrong, guys, so don't push

Just an opinion :)

**Synth** *[In reply to Artem Kotelskiy]*

The central bank creates money out of nothing. Then the government taxes the money back from the slaves.

You are either a slave or you are free. People working for other peoples money, are not working for themselves. They are slaving for for their master/owner.

There is no degrees. You are either owned and are a slave and have a slave tracking number and live under a massive surveilence, police state central bank run slave plantation OR you are free. Slave or Free. There is no degrees.

**Artem Kotelskiy**

I see. I think the next thing to discuss is if the government is good or not (let's say US). And I know I will lose this one, so let's not go into this. I completely understand your pov. It differs from mine in that I believe in kindness more, and think that there is a spectrum of freedom. But could be I am just young and inexperienced.

**Synth**

"Freedom to masturbate to porn", "freedom to smoke marijuana", "freedom to have anal sex", "freedom to shoot up heroin", "freedom to run around in the 'free market' laboring like a slave for someone elses money", "freedom to shop!".

Slavery is not about free or slave. Its about independent (free) or dependent (slave).

You make people dependent upon you for survival, then you give them fake "freedoms" so they dont revolt. That is how you turn a society into a labor camp and then give them enough free porn, prozac and zoloft until you have domesticated "happy slaves" that cannot even imagine what an alternative would look like.

Look how free those people are with their $750,000 in student debt they wont pay off until they die! Lol. Its just a mockery.

**Artem Kotelskiy**

Everyone makes his own choices

Some people just grow food and live off that

I am from the country where half of the population lives like this, it's just fine

And I think if one really wants, he can be free

**Vadim 🛌**

let me guess, belarus?

**Artem Kotelskiy**

No, it's harder to guess

**Synth**

Anyone who does not want to be a slave is an anarchist now! Lol

"Whoa. Whoa. Whoa. I dont want to be an anararchist. I mean a little slavery is ok, but the masters should be nicer to the slaves." Lol.

**Artem Kotelskiy**

Anarchist is someone who declares a war on the government

Loool

**Synth**

Anarchist.

An-archon

An means without.

Archon means "master" or "ruler".

Anarchy means "without masters" or without rulers. All of the words are inverted to mock the public and the illiterate.

**Artem Kotelskiy**

Anyway

Keep up the skycoin guys, I sincerely hope it will allow more people not to have masters

**Artem Kotelskiy** *[In reply to Synth]*

Ok

**Synth**

Lol

matthieu *[In reply to Synth]*

👍🏾agree completely

**Synth** *[In reply to Artem Kotelskiy]*

No. The problem is human nature.

You cannot free slaves. They will just find another master. They *want* and choose to be slaves. They just want a slave driver with a softer whip.

Look at how people spontaniously elect leaders to tell them what to do and tell them how they should live and what they should fear. Because they refuse to do it themselves.

matthieu *[In reply to Artem Kotelskiy]*

Actually maybe it would serve the coin more to put forward the ideology behind as synth put it rather than having a few faces....

matthieu

Synth So far I didn't know what were your motivations/values and  deep ideology. Now I am an even bigger supporter of the coin. This is important to remind the final aim of all of this... Loads of ppl forget and just want to be overnight millionaires by buying into ICOs...

**Synth** *[In reply to matthieu]*

Trillionaires lol. Worlds first trillionaires. Briefly until this bubble bursts.

Millionaire is so 1994

matthieu

😂😂

**Synth**

Bitcoin gets pushed up to $5000 but if even 1% of holders sold it would be back at $2000. So very high price increase vs the market depth.

I think we could see trillionaires or people worth more than Billgates briefly, before they start moving money out and it implodes.

Altcoins, unlike real estate and stocks, have no price ceiling. There is no fundamental economics or mathematics keeping the price from going up to infinity.

There is no revenues or loss and no objective way to determine that a buggy "smart contract" platform no one uses, should not be worth $250 billion dollars.

**Steve**

A Distributed Consensus Algorithm for Cryptocurrency Networks
https://github.com/skycoin/whitepapers/blob/master/whitepaper_skycoin_consensus_v01_jsm.pdf

Is the most recent consensus algorithm whitepaper
