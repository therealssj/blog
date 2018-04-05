+++
title = "March Skycoin Ecosystem Technical Report"
tags = [ "Announcements", ]
bounty = 0
date = "2018-04-05"
categories = [ "Statement", ]
+++

##### During the month of March, our development teams have made tremendous progress on many projects within the Skycoin ecosystem:
---

**Skycoin**

-   Completed command-line interface documentation and overall testing.

-   Based on BIP21's Skycoin URIs, "hours" will now be displayed to show the quantity of Coin Hours. For example `Skycoin:2hYbwYudg34AjkJJCRVRcMeqSWHUixjkfwY?amount=123.456&hours=70`

-   Using a new [logging module](https://github.com/sirupsen/logrus) to replace the [old module](https://github.com/op/go-loggin) to ensure compatibility with future projects.

-   Completed Skycoin Exchange Integration's [documentation.](http://github.com/skycoin/skycoin/blob/develop/INTEGRATION.md)

-   Tested the newest Go implementation v1.10.

**Skycoin wallet**

-   Released wallet v22. Completed both the front-end and fixed vulnerabilities.

-   Added a [signature](http://github.com/skycoin/skycoin#release-signing) to the newest version of wallet in order to proof its authenticity.


**KittyCash**

*KittyCash Verification Service - utilizing email subscription service to verify the customer's purchase in IKO*

-   KittyCash purchase verification service implemented and tested.

-   Added a docker file to the verification service.

*KittyAPI*

-   Created a command-line interface "ikocli" that can be used to generate Kitty data for IKO.

-   Created a command-line interface "testcli" that can be used to test KittyAPI using personal data.

-   Upgraded the foundation of KittyAPI to integrate with the Teller cashier function and trading market API function.

-   Added docker file.

*KittyCash's Teller service*

-   Strengthened the reservation system to stabilise Kitties reservation during IKO.

-   Integrated the verification services into the cashier function.

-   Integrated KittyAPI into the cashier function.

*KittyCash wallet function*

-   Upgrade the wallet and tested.

-   Implemented the trading market function into the wallet.

*KittyCash Trading Market*

-   Upgraded the basic trading market function.

-   Integrated the verification service into the trading market.

*Kitty Auction Bot on Telegram*

-   Completion of a Kitty auction record robot (untested).

*Official KittyCash website*

-   Released new website.

-   Added a KittyCash game on the website.

-   Improved the scoreboard within the game.

**CXO**

-   Implemented the splitting function in order to allow splitting of large files for simultaneous integration into Merkle-tree.

-   Implemented a large file enumeration feature that allows for listing of recently used objects in the database, improving the listing function.

-   Implemented multiple features to increase the speed of data exchange for a single node's MaxObjectSize especially during slow network and reducing the need of requests and responses between server and node.

-   Added a new method of BoltDB storage based on the original BoltDB.

-   Completed the function of exporting the database as a JSON file or into binary.

**Hardware development**

-   Custom OpenWRT routers tested with a double sided PCB and antennas.

   ![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-1.jpg)

![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-2.jpg)

![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-3.jpg)

![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-4.jpg)

![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-5.jpg)

**SPO Miners development**

-   Miners for decentralised storage with 1TB hard discs are being tested by the SPO team. Skycoin team and SPO will continue collaboration and develop a version with custom chips and m.3 SSD form factor for Skycoin.

   ![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-6.jpg)

![](https://raw.githubusercontent.com/skycoin/blog/master/content/img/tech-report-7.jpg)

**Miscellaneous**

-   A brand new website revamp and a [new business white paper](https://www.skycoin.net/skycoin_whitepaper.pdf) were released.

-   OTC function for direct Skycoin purchase implemented into the website with CryptoWolf (<https://www.skycoin.net/buy/>).
