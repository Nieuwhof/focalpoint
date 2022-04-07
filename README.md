# focalpoint

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

apt-get -y install ccache git libboost-system1.58.0 libboost-filesystem1.58.0 libboost-program-options1.58.0 libboost-thread1.58.0 libboost-chrono1.58.0 libssl1.0.0 libevent-pthreads-2.0-5 libevent-2.0-5 build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev libdb4.8-dev libdb4.8++-dev libminiupnpc-dev libzmq3-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqrencode-dev python-pip

pip install construct==2.5.2 scrypt

# other

sudo apt-get update

sudo apt-get install build-essential gcc make perl dkms

reboot

sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler

sudo apt-get install openssl1.0

sudo apt-get install libssl1.0-dev

sudo apt-get install libboost-program-options-dev

# QT Gui
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

sudo apt-get install libqrencode-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install build-essential libtool autotools-dev automake pkg-config bsdmainutils python3

# Portainer
sudo docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer

# Extra
for i in $(docker ps -q); do docker exec $i /focalpoint/src/focalpoint-cli  getblockchaininfo; done

for i in $(docker ps -q); do docker exec $i /focalpoint/src/focalpoint-cli  generate 2  & done

# Extra 2
Generate 11 blocks to myaddress:

bitcoin-cli generatetoaddress 11 "myaddress"

If you are using the Bitcoin Core wallet, you can get a new address to send the newly generated bitcoin to with::

bitcoin-cli getnewaddress

