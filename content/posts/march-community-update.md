+++
aliases = []
bounty = 0
date = "2019-04-09"
image = "/img/march-update-header.jpg"
tags = ["Announcements", "Development", "Community"]
title = "March 2019 community update"

+++

March madness is a good description of the sheer volume of high quality development and progress made across the expanding Skycoin ecosystem. Mainnet launch, hardware wallet updates, and a new CX release were the highlights on the software side of activity. 

Within the Skyfleet, MacSkyver lead the charge with the Skycoin Rewards Program, resulting in a number of fantastic new articles and videos by a host of first-time contributors. The first of the Skyfleet Projects was also announced - Skycoin integration into BTCPay Server - this is huge! Read on for all the Skycoin happenings in March.


### Skywire

After ten months of intensive testing on 10,000 nodes of the Skywire testnet, the first iteration of Skywire mainnet was released in March. The mainnet software has been rewritten from the ground up and is primarily focused as a platform for developers to start building the next generation of distributed apps. All existing apps have been rewritten and optimized for the mainnet, including a distributed and secure chat app, SSH, and a multi-hop tunneling proxy app.

Over the course of the next few months we will be releasing new iterations of the Skywire mainnet software with new features, facilitated by an updater that will provide the ability to conveniently install new iterations. Stay tuned for additional information, technical details, and further updates from the team.

Developers are encouraged to install the mainnet software from the [Skywire GitHub](https://github.com/skycoin/skywire/tree/mainnet) on a new Pi node and begin testing. Bug reporting should be done through the repo, with steps taken to reproduce the bug, and include any feedback. Details of the process will be available in the README.md and CONTRIBUTE.md. Documentation can be found at the [Skywire GitHub Wiki](https://github.com/skycoin/skywire/wiki). General discussion and support for mainnet happens on [Telegram](https://t.me/SkywireMainnet).

Upcoming features for Skywire mainnet include:

- A new and intuitive UI for developers and users to easily interact with the mainnet
- Bandwidth monetization will be coming soon that will allow users to earn Coin Hours through bandwidth sharing
- Coin Hours bank
- Skycoin transactions utilizing CoinJoin
- Remote management of unlimited nodes
- Port the CXO protocol onto Skywire for distributed data storage in preparation for the Obelisk consensus implementation

Skyfleet, do not install the the developer Skywire mainnet software on your testnet whitelisted Skyminer nodes, as you will stop receiving testnet rewards. If you are thinking of building a DIY miner or buying an official Skyminer, now is a great time. You will help to build out the network and will receive testnet rewards until mainnet bandwidth metering is implemented. The more nodes online, the more robust the network!

### CX

CX is Skycoin’s native programming language. March saw the release of CX version 0.6.2. Check out the [CX GitHub release page](https://github.com/skycoin/cx/releases/tag/v0.6.2) for more details.  

CXFX is a graphics library created by _2dbug_ that aims to facilitate games development in CX by providing a library that allows developers to focus on building their apps instead of having to write everything from scratch. This month it was merged into the official Skycoin repository. 

At first, [CXFX](https://github.com/skycoin/cxfx) will be a library-only environment, allowing access CXFX functionalities from within a CX program. The eventual goal is to have something like a [WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG) (what you see is what you get) game editor, like Unity.

To learn more about CXFX, check out the articles about [creating a blockchain game engine](https://medium.com/skyfleet-captains-log/creating-a-blockchain-game-engine-5d4481b0b788) and the future of [blockchain gaming](https://medium.com/skyfleet-captains-log/blockchain-gaming-anyone-23593ebc3545). Also make sure to follow [CXFX on Twitter](https://twitter.com/SkycoinCxfx). To contribute to the project, join the [CXFX Telegram group](https://t.me/Skycxfx),  visit the [CXFX GitHub repository](https://github.com/skycoin/cxfx) and read some [CXFX tutorials](https://github.com/skycoin/cxfx#tutorials-). Skycoin is allocating resources to help progress the engine, however this is a community project at heart and will require contributions from the Skyfleet.


### Skywallet 

The Skywallet is our own first-party hardware wallet. This month, the Skycoin devs made the Skywallet daemon feature-complete. The daemon will enable Skywallet integration with any future wallet distribution, such as the upcoming web wallet, as well any third-party wallets that choose to do so. 

### Ledger support for SKY

A major milestone was reached integrating Skycoin within the Ledger brand of third-party hardware wallets - the first Skycoin transaction has been signed with a Ledger Nano S device!

Stay tuned for more updates as we work hard on both hardware wallet projects, as ensuring security is our highest priority before we will enable use of these devices.

![Ledger support for Skycoin is a currently being worked on as we strive to give the Skyfleet as many options for secure coin storage.](/img/ledger-ui.png)

For detailed developer updates on Skywire, CX and hardware wallet progress, follow the [Skyblog](http://www.skycoin.net/blog). For real time updates on major Skycoin milestones, follow Skycoin on [Blockfolio](https://blockfolio.com/coin/SKY).

### Synth Speaks

[Synth chatted to YouTube interviewer Keith Wareing](https://www.youtube.com/watch?v=BT9_6KJIetA), answering questions on a wide range of Skycoin topics including McAfee, the progress on Skywire Mainnet and his vision for Skycoin as a future blockchain platform for many of the current internet uses. 

The Synth Tapes Volume II and III were released in March. [Volume II](https://www.youtube.com/watch?v=H84nuTWbYu8) has Synth discuss cyberbalkanization, the importance of owning your own data and how Skywire makes this possible. In [Volume III](https://youtu.be/BUNxpDJIeak), Synth talks about how draconian internet censorship is laying siege to free speech around the world.
Synth’s March telegram talks were compiled and posted on YouTube. Listen to Synth discussing Skywire mainnet [here](https://www.youtube.com/watch?v=jewqjAl8lfQ) and [here](https://youtu.be/e3hUan4cCds?t=1666). 

{{< youtube id="jewqjAl8lfQ" autoplay="true" >}}

<br>

### Official Articles

On Medium, [The Justification for Skywire: A Technical Explanation](https://medium.com/skycoin/the-justification-for-skywire-a-technical-explanation-704b080a5eb5) takes a look into the protocol and monetary problems that Bitcoin and other cryptocurrencies experience and explains how Skywire solves these problems. 

The [February 2019 Community Update](https://medium.com/@Skycoinproject/february-2019-community-update-324df8191a16) was also published. 

Developer updates are posted on the Skyblog, where you can read all the updates described above in-depth. There was the [Skywire Mainnet Public Testing Announcement](https://www.skycoin.net/blog/posts/skywire-mainnet-public-testing-announcement/), the [CXFX Graphics Library](https://www.skycoin.net/blog/posts/cxfx-v0.1/), a March 8th [Skywire Dev Update](https://www.skycoin.net/blog/posts/skywire-mainnet-development-update/), the [CX 0.6 & 0.61 Dev Update](https://www.skycoin.net/blog/posts/introducing-cx-v0.6-and-0.6.1/), an update on [Skycoin’s Integration into Ledger](https://www.skycoin.net/blog/posts/skycoin-ledger-integration/), and a [March 29th Dev Update](https://www.skycoin.net/blog/posts/skycoin-development-update-week-13/). 

### Official Videos

[Using Skycoin with your customers](https://www.youtube.com/watch?v=ueVKQunXsXk) showed how Skycoin will be implemented into a customer rewards program. An official video summary of the [San Francisco Developer Week](https://www.youtube.com/watch?v=9AXn6Y7A8O4) was also released. 

### Skycoin Jobs

If you are interested in working directly on various aspects of Skycoin with the dev team, check out the [jobs listed on the official site](https://www.skycoin.net/jobs/). We are currently looking for a Mechanical Engineer, Circuit Engineer, Go Programming Language Engineer, C Programming Language Engineer, Marketing Manager, Operations Manager and Technical Writer.

### Skyfleet Content

The Skycoin Rewards Program spearheaded by MacSkyver (see below), has had an immediate impact on the amount of quality Skyfleet content released this month. We saw a spike in Skycoin-themed content, with a range of awesome articles and videos. 

### Community articles

[Lawrence Qholloi](https://medium.com/@lawrenceqholloi) came through with a trio of strong articles. He helped put the [final nail in the kidnapping FUD coffin](https://medium.com/skyfleet-captains-log/driving-home-a-final-nail-in-the-skycoin-kidnapping-fud-coffin-the-court-papers-8e02aaaa8fc5?source=---------2------------------), he explained the latest in the [McAfee saga](https://medium.com/skyfleet-captains-log/skycoin-terminates-their-relationship-with-mcafee-7191e089678d) and told the world how to pick a winner in the [post-shitcoin shakedown cryptoverse](https://medium.com/skyfleet-captains-log/picking-a-winner-in-the-post-shitcoin-shakedown-cryptoverse-d5a66f1e07ce). 

[Christian Ott](https://christianott.co/skycoin) updated his go-to explainer on [Skycoin Distribution](https://christianott.co/skycoin_distribution_en/) with the latest information. He also performed a superb [Skycoin liquidity analysis](https://twitter.com/footballelixir/status/1110629353812119553), showing Binance to have the deepest orderbooks for buying and selling SKY. 

[MacSkyver](https://medium.com/@skyfleet) continues his sterling job of building the Skycoin community with [Creating a Blockchain Game Engine](https://medium.com/skyfleet-captains-log/creating-a-blockchain-game-engine-5d4481b0b788), which outlines our plan to develop blockchain gaming applications written in our CX programming language. He followed it up with [Blockchain Gaming Anyone?](https://medium.com/skyfleet-captains-log/blockchain-gaming-anyone-23593ebc3545) an overview of the CXFX gaming engine currently being developed by rd2dbug. His last piece was an announcement of the impending [support of Skycoin within BTCPay Server](https://medium.com/@skyfleet/sky-x-btcpay-skyfleet-project-1-acce514d278e), a self-hosted, censorship-resistant payment processing platform. 

[Marco Casino](https://medium.com/@macrobusinesstv) reminded us again why [the World Needs Skywire More than Ever](https://medium.com/skyfleet-captains-log/now-more-than-ever-the-world-needs-skywire-73aaacd7b346), explaining how ISPs in Australia and New Zealand used national tragedy as an excuse to block access to websites that they can’t censor. He also exposed the [Anti-Skycoin Paid-FUD](https://medium.com/skyfleet-captains-log/anti-skycoin-paid-fud-exposed-2d4685c9a4e2) and wrote an explainer article on the [official Skyminers](https://medium.com/skyfleet-captains-log/free-skyminers-if-held-for-2-years-61dde7ba636c). 

[Fray](https://medium.com/@cryptofray) enjoyed a breakout month with the release of several fantastic articles. He explained [Why Skycoin is Still Under the Radar in 2019](https://medium.com/skyfleet-captains-log/why-skycoin-is-still-under-the-radar-in-2019-e7d310361cd7), and how [Skycoin is an ecosystem](https://medium.com/skyfleet-captains-log/skycoin-is-an-ecosystem-wait-what-aed0d546f6c1). These provide another great community explanation of the project. He also authored [How to Buy Skycoin in 2019](https://medium.com/skyfleet-captains-log/how-to-buy-skycoin-in-2019-35b9bc1d2155?source=---------7------------------), [how to send your newly bought Skycoins](https://medium.com/skyfleet-captains-log/sending-skycoin-like-a-pro-3987e5375502) and [how to engage with the Skycoin community online](https://medium.com/skyfleet-captains-log/i-bought-skycoin-now-what-b519b0321777).

[Blevenec](https://medium.com/@agbanoublevenec), one of our strongest Skyfleet ambassadors in West Africa, also made his writing debut. For all you Francophone SKY fans, read [Pourquoi j’ai décidé d’investir dans le Skycoin?](https://medium.com/@agbanoublevenec/pourquoi-jai-d%C3%A9cid%C3%A9-d-investir-dans-le-skycoin-d053236fcbca?source=---------3------------------) (Why I decided to invest in Skycoin) and his two follow-up pieces on the [Skycoin ecosystem](https://medium.com/@agbanoublevenec/skycoin-le-meilleur-projet-que-lunivers-des-crypto-monnaies-a-pu-m%C3%A9riter-2789e20e6ea7) and [how to use the Skycoin wallet](https://medium.com/@agbanoublevenec/comment-poss%C3%A9der-la-crypto-monnaie-du-si%C3%A8cle-b028f8913c72), explained in French. 

**Spencer Daemore** of cryptocurrency mining outfit CryptoKings published his complete [DIY Skyminer Build Guide](https://medium.com/@spencerdaemore/diy-skycoin-miner-build-guide-b9ba9aaf77ac). This is an in-depth guide with many photos and concise explanations of every step. 

There were also articles from new contributors including [Frahane Bio](https://medium.com/@frahanebio) with [Avec Skycoin nous pouvons désormais vaincre le chômage et la pauvreté dans le monde](https://medium.com/@frahanebio/avec-skycoin-nous-pouvons-d%C3%A9sormais-vaincre-le-ch%C3%B4mage-et-la-pauvret%C3%A9-dans-le-monde-3bb265ece4c5) and RaneVagora on [Synth‘s beef with Upwork](https://medium.com/@ranevagora/skycoins-synth-declares-upwork-com-2f589d00f6e3). 

All of the Skyfleet articles are published on Medium for everyone to read and share. The [SkyFleet Captain's Log](https://medium.com/skyfleet-captains-log) collates the highest quality Skycoin community content in one place. It features prolific Skyfleet writers who have contributed the most so far to Skycoin with their writing skills. Follow all the Skyfleet writers and support them with your claps.

### Community videos

Skycoin supporters Larry and Joe did an excellent [round-table video discussion](https://www.youtube.com/watch?v=U8v_CCrdzcw) with lead CX developer Amaury, community manager MacSkyver and Skyfleet members Fray, golfmike. They cover a heap of interesting topics, and demonstrate the strength of the support for Skycoin.  

**CryptoRich** did a [video reading of the February 2019 Update](https://www.youtube.com/watch?time_continue=1&v=4y85pMc5KaY), which also covers the great new website [SKYFUD](http://www.skyfud.com/). MacSkyver did his usual awesome [monthly video summary](https://www.youtube.com/watch?v=e3hUan4cCds), which includes a pre-view of the Skycoin rewards event on April 7th. 
  
{{< youtube id="U8v_CCrdzcw" autoplay="true" >}}

<br>

Loyal Skyfleet member and proficient coder **BigOokie** released two excellent walkthroughs for the [installation of Skywire mainnet on MacOS](https://asciinema.org/a/232357) and installing [CX Language on MacOS via Homebrew](https://asciinema.org/a/233371). These have been re-posted to YouTube on the Skyfleet channel [here](https://www.youtube.com/watch?v=HJFP4RoQgsE) and [here](https://www.youtube.com/watch?v=HNuJQzNJFlE). 

[Fray](https://www.youtube.com/channel/UC41FZquwlKSIVxgMhwJrsiw/videos) matched his writing work with the fantastic narration and production of four videos to help newcomers to Skycoin. Check out [Intro to Coin Hours](https://www.youtube.com/watch?v=-syucOO5JAc), a [Roadmap to the Skycoin Community](https://www.youtube.com/watch?v=yvnL_nDE1MA), [Sending Skycoin like a Pro](https://www.youtube.com/watch?v=NvK12rR9AC8) and [How to Buy SKY in 2019](https://www.youtube.com/watch?v=jEzi4t8WANA). 

**Casino** released several videos on his new YouTube channel - [Skywire Revolution](https://www.youtube.com/watch?v=NSJnrHw_Qw4) and the hilarious subtitled parody [Skycoin Synth interview](https://www.youtube.com/watch?v=JXdVzLekp4o). 

{{< youtube id="jEzi4t8WANA" autoplay="true" >}}

<br>

### Skycoin Rewards Program

The Skycoin Rewards Program (SRP) incentivizes the Skyfleet to create Skycoin content through raffle tickets to win Skycoins, Skywallets and other merchandise. The higher the quality of content you produce, the more chances you will have to win a prize. 

Writing an article, making a YouTube video or hosting a Skycoin meetup are some of the eligible categories. For complete details on how the program works, read [this article](https://medium.com/skyfleet-captains-log/starting-with-skycoin-rewards-6e9ce6effbd2) and join the [SRP Telegram group](https://web.telegram.org/#/im?p=@SkycoinRewards). For ideas on what type of content to make, read [this article](https://medium.com/@skyfleet/skycoin-rewards-content-ideas-22fc32b7d783). 

Winners will be announced on a game-show style YouTube livestream, to be held on the first Sunday of every month. Once you have produced content and earned entry tickets, tune in to the [Skyfleet YouTube channel](https://www.youtube.com/channel/UCsWgASci1NzCtSNU25w8qPg?sub_confirmation=1) to watch the game show each month! The first show was held on April 7th at 01:00 UTC. Read the results [here](https://medium.com/skyfleet-captains-log/skycoin-rewards-monthly-recap-and-results-1-f420fd357034). 

### Skyfleet Projects I - Skycoin vs BTCPay Server

BTCPay Server is an open-source, self-hosted payment processing platform that allows merchants and individuals to receive payments of Bitcoin and a range of altcoins in a censorship-resistant manner. Integration into BTCPay Server will be a huge step towards expanding the transactional use of Skycoin. This will be the first of the Skyfleet Projects, which we encourage the community to help build. Start by reading [this summary article](https://medium.com/@skyfleet/sky-x-btcpay-skyfleet-project-1-acce514d278e), head over to the [Skyfleet GitHub account](https://github.com/Skyfleet), and contact @BigOOkie, @moe_narrow or @MacSkyver on Telegram to lend a hand!

![BTCPay Server overview](/img/btcpay-overview.png)

### Other community news

- There is a new hub for CX Game development on reddit. [r/CX_Language](https://www.reddit.com/r/CX_language) is a great place to discuss all things CX and to update the community with your latest project written in the Skycoin programming language. 
- For Vietnamese Skycoin fans, check out [Skywirex](https://www.skywirex.com/), a blog filled with news and Skywire tutorials written in Vietnamese.
- Thanks to Sudo’s infographic competition, we saw a slew of amazing new infographics explaining various aspects of Skycoin. These have been compiled into a memes and graphics pack, which can be downloaded from the [Monster Memes and Image Pack](https://drive.google.com/drive/folders/1l0-6cg14n7V_u9gnDSJkhrj3yO7hjylq). The winners will be announced soon. 

### Skycoin Meetups

Joel the Man hosted a meetup discussing Skycoin and MDL Talent Hub, one of our Fiber partners. 

![Hamburg meetup](/img/hamburg-meetup.png)

There are several meetups around the world scheduled for April. Olemis Lang hosted a Skycoin developer hackathon on April 6th in Havana Cuba, details [here](https://www.meetup.com/CubanTech/events/259974015/).

{{< tweet 1114360994636021760 >}}

### Skycoin Telegram Groups

It can be hard to keep track of the all the different Telegram groups in the Skycoin project. Here are some groups that you may not yet have joined: 

- [Skywire Mainnet](https://t.me/SkywireMainnet) - a place for interested devs who are exploring the first versions of Skywire mainnet, and for support and to discuss features/issues
- [Skywire Antenna Group](https://t.me/SkywireAntenna) - discussion and support for Skyfleet working on building out the Skywire wireless mesh network
- [Skycoin Game Dev](https://t.me/skycoin_game_dev/4738) - discussions on game development written in CX
- [Skycoin CXFX](https://t.me/Skycxfx) - a Telegram group for those building and using the CXFX game engine
- [Skycoin 3D Print](https://t.me/Skycoin3DPrint) - the place to go for all Skycoin 3D-printing-related discussion
- [Skycoin Meetups Worldwide](https://t.me/MeetupsWorldwideSkycoin) - the place for posting/announcing your Skycoin meetup
- [Skyfleet News](https://t.me/SkyfleetNews) - only Skyfleet news links, no chat. Great for keeping up to date with the growing amount of ecosystem development and content.
- [Skycoin Rewards Room](https://t.me/SkycoinRewards) - for submitting Skyfleet content and claiming your tickets to the monthly Skycoin Rewards Program (SRP) raffle run by MacSkyver
- [Skycoin Sticker Blast](https://t.me/SkycoinStickerBLAST) - the Skyfleet continue to plaster the cities of the world with Skycoin stickers. Jump on here to access sticker templates to print yourself or message Daken to get some stickers sent out to you. 
- [Skycoin memes](https://t.me/skycoinmemecontests) - the dankest Skycoin memes live here 

![](/img/sticker-2.jpg)

That’s everything from March, another incredibly busy month of building and development. Stay engaged with across Telegram, Twitter, Medium, Reddit and YouTube and GitHub and get your entries in for the first Skycoin Rewards Program raffle. Onwards and upwards, Skyfleet!

![](/img/skywire-graphic.png)


