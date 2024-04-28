# Extra Credit

If you made it this far, congratulations on proactively participating in the Bitcoin network and empowering yourself to eliminate trust by verifying your own bitcoin transactions!

You can do some cool things with Remote Procedure Calls (RPC) like check transactions, network status, and various statistics. You should exercise caution and skepticism when working with any RPC, scammers have instructed unsuspecting users in ways that compromised their funds.

If you want to turn your node into your own blockchain explorer, you need to index your copy of the blockchain. I did this by opening the bitcoin.conf file by running $ sudo nano /mnt/ext/bitcoin.bitcoin.conf; and adding the line $ txindex=1; under # Miscellaneous options then I restarted BitcoinCore with the command $ bitcoin-qt -reindex; the initial indexing took about 5 hours and as of this writing, I'm on day 5 waiting for the blocks on disc to process.

Further instructions can be found in 'Mastering Bitcoin' 2nd addition by Andreas Antonopoulos starting in chapter 3, page 43. I highly recommend this book.

[@peterjdurham](https://twitter.com/peterjdurham) put together a really cool article on building your own API using BitcoinCore's RPC functionality. I'm trying to implement this on my system currently. https://medium.com/@peterjd42/build-your-own-bitcoin-api-using-node-js-and-bitcoin-core-251e613623db
