# Introduction
These instructions are meant for people interested in running a Bitcoin node. However, this only covers how to build a very specific configuration of a Bitcoin node: Built on a Raspberry Pi4 hardware, with a mini HDMI monitor, BitcoinCore v0.19.0.1 with the GUI, TOR enabled, wallet enabled, external SSD, and fully validating meaning that the node will accept incoming requests.

Before starting this project, I had no experience with Command Line Interfaces (CLI), Linux, or single-board computers. If you have a similar background and you want to run a Bitcoin node configured like this, then these instructions should be helpful to you. I made a lot of mistake and had to gather information from several different sources, so hopefully this saves you some time & effort. If you are a more advanced user, then these instructions may be too basic for you, or you may be looking for a more advanced configuration that is not covered here. However, there are links to informative resources that you may find useful. I may have some steps in here that you find unnecessary. For example, I prefer to load my library files one at a time, other people like to do several at a time. However, these are the steps I took to build my node. Again, I had no experience with this stuff before hand and I do not know exactly what a lot of these steps are doing. But this is how it worked for me.

Other helpful links:

https://www.amazon.com/gp/product/1491954388/ref=as_li_tl?ie=UTF8&tag=aantonop-books-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=1491954388&linkId=7169748691b8f67179587330063190d6

https://download.qt.io/official_releases/qt/5.12/5.12.6/qt-opensource-linux-x64-5.12.6.run

https://bitzuma.com/posts/compile-bitcoin-core-from-source-on-ubuntu/

https://github.com/bitcoin/bitcoin/blob/master/doc/build-unix.md

https://hackernoon.com/a-complete-beginners-guide-to-installing-a-bitcoin-full-node-on-linux-2018-edition-cb8e384479ea

https://stadicus.github.io/RaspiBolt/raspibolt_20_pi.html

https://medium.com/@peterjd42/build-your-own-bitcoin-api-using-node-js-and-bitcoin-core-251e613623db

https://github.com/MrChrisJ/fullnode

https://www.youtube.com/watch?v=SGh3X2e8J2Y
