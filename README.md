5G-CASH integration/staging tree
===========================

What is 5G-CASH?
----------------
5G-CASH (VGC) is a digital currency that enables instant payments to anyone, anywhere in the world. It uses different key features technology to operate with no central authority allowing everyone to operate the way they want to with this hybrid privacy coin using Sigma and Dandelion++ Protocol along with TOR to remain anonymous.

Why 5G-CASH is a Hybrid Project?
-------------------------------
Because it uses POW to allow miners to compete with hashing power but also incentivate holders to mint their balances with POS v3.0 to earn the same reward amount and once holders allocate the necessary coins they can run Masternodes to easily support the consensus to secure the Network.

For more information, read the
[original whitepaper](https://fiveg.cash/wp-content/uploads/2021/09/5G-CASH-Whitepaper.pdf).



### Key Features
    -Privacy (Anonymous and Untraceable)
    -Sigma Protocol 
    -Tor Protocol
    -Dandelion++ Protocol
    -Proof of Work and Proof of Stake (3.0) share 55% of the block reward
    -Masternode gets 45% of the block reward

### Specifications and Block Rewards -----> https://discord.gg/tmQSFV9


Linux Build Instructions and Notes
==================================

Dependencies
----------------------
You can use the "depscript.sh" to automatically install Dependencies to build VGC or manually install them using the syntax below

1.  Update packages

        sudo apt-get update 

2.  Install required packages
        
        apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-all-dev libzmq3-dev libminizip-dev libdb-dev libdb++-dev libminiupnpc-dev && sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqrencode-dev -y

3.  Install Berkeley DB 4.8

        sudo add-apt-repository ppa:bitcoin/bitcoin && sudo apt-get update && sudo apt-get install 
    
5.  Install QT 5

        sudo apt-get install 
        
        

Building 5G-CASH
----------------------
### 1. Static compile
    
    apt-get update -y
    apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev 
    bsdmainutils libboost-all-dev libzmq3-dev libminizip-dev sudo curl libdb++-dev zlib1g-dev -y
    git clone https://github.com/5G-Cash/5G.git
    chmod -R +rwx 5G 
    cd 5G/depends
    make -j8 HOST=x86_64-linux-gnu
    cd ..
    ./autogen.sh
    CONFIG_SITE=$PWD/depends/x86_64-gnu-linux/share/config.site ./configure      --prefix=$PWD/5G-shared-linux --disable-fuzz-binary --disable-bench --disable-tests --with-incompatible-bdb
    make -j8 clean
    make -j8
    make -j8 install
    


#### 2. Shared binary
    git clone https://github.com/5G-Cash/5G.git
    chmod -R +rwx 5G
    cd 5G
    ./autogen.sh
    ./configure
    make
    
### 3.  It is recommended to build and run the unit tests:
    make check


Setting up a Fivegnode
==================================

Read [contrib/masternode-setup-scripts/README.md](contrib/masternode-setup-scripts/README.md) for instructions.
