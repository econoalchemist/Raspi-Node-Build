# Installing & Compiling BitcoinCore v0.19.0.1

`$cd bitcoin;`

`$sudo git clone https://github.com/bitcoin/bitcoin.git;`

`$sudo apt install build-essential -y;`

`$sudo apt install libtool -y;`

`$sudo apt install autotools-dev -y;`

`$sudo apt install automake -y;`

`$sudo apt install pkg-config -y;`

`$sudo apt install libssl-dev -y;`

`$sudo apt install libevent-dev -y;`

`$sudo apt install bsdmainutils -y;`

`$sudo apt install python3 -y;`

`$sudo apt install libboost-all-dev -y;`

`$sudo apt install libprotobuf-dev -y;`

`$sudo apt install protobuf-compiler -y;`

`$sudo apt install libcanberra-gtk-module -y;`

`$sudo apt install libminiupnpc-dev -y;`

`$sudo apt install libzmq3-dev -y;`

`$sudo apt install libqt5gui5 -y;`

`$sudo apt install libqt5core5a -y;`

`$sudo apt install libqt5dbus5 -y;`

`$sudo apt install qttools5-dev -y;`

`$sudo apt install qttools5-dev-tools -y;`

`$sudo apt install libqrencode-dev -y;`

`$sudo apt install libboost-system-dev -y;`

`$sudo apt install libboost-filesystem-dev -y;`

`$sudo apt install libboost-chrono-dev -y;`

`$sudo apt install libboost-test-dev -y;`

`$sudo apt install libboost-thread-dev -y;`

`$sudo wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz;`

`$echo '12edc0df75bf9abd7f82f821795bcee50f42cb2e5f76a6a281b85732798364ef db-4.8.30.NC.tar.gz' | sha256sum -c;`

`$tar -xvf db-4.8.30.NC.tar.gz;`

`$cd db-4.8.30.NC/build_unix;`

`$sudo mkdir -p build;`

`$BDB_PREFIX=$(pwd)/build;`

`$../dist/configure --disable-shared --enable-cxx --with-pic --prefix=$BDB_PREFIX;`

`$sudo make install;`

`$cd ../..;`

`$cd bitcoin;`

`$sudo git checkout tags/v0.19.0.1;`

`$sudo ./autogen.sh;`

This should take a couple minutes to start running, don't freak out.

`$sudo ./configure CPPFLAGS="-I${BDB_PREFIX}/include/ -O2" LDFLAGS="-L${BDB_PREFIX}/lib/" --with-gui --with-miniupnpc --enable-upnp-default --enable-hardening;`

Note this line reads "-O2" which is the capital letter "O" not zero "0"

`$sudo make;`

This takes a long time to compile, don't freak out.

`$sudo make install;`

`$sudo bitcoin-qt;`


This should launch the BitcoinCore GUI.

When the Bitcoin Core GUI launches for the first time it asks you define the file path for storing the blockchain (~240GB at time of writing).

The default file path that Bitcoin Core chooses is /root/.bitcoin.

If you used a 64GB MicroSD card for your boot disc, then you'll probably only have ~48GB left in that directory.

Change the file path to: `/mnt/ext/bitcoin/bitcoin` and you should have all the remaining room on your external drive to consume.

The first thing your node will do is synchronize with the network. That means that it is going to download all the blocks in the Bitcoin blockchain starting with the genesis block from January 2009. This is roughly a 240GB download and it will take a lot of time and bandwidth. My initial down load took 10 days 9 hours.
