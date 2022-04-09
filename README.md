#Qt5 GUI for Focal

#Build instructions

#Debian

These build instructions should work for Debian and derivative systems, such as Ubuntu and Linux Mint.

We have some required packages. You can install these with apt:

apt install qt5-qmake qt5-default qttools5-dev-tools \
    libboost-system-dev libboost-filesystem-dev \
    libboost-program-options-dev libboost-thread-dev \
    build-essential libboost-dev \
    libssl-dev libdb5.3++-dev libminiupnpc-dev

Next build the wallet:

qmake
make

#An executable named Focal-Qt will be built.

#Fedora

These build instructions should work for Fedora and derivative systems, such as Red Hat Enterprise Linux and Oracle Linux.

We have some required packages. You can install these with dnf:

dnf install gcc-c++ boost-devel openssl-devel libdb-cxx-devel \
    miniupnpc-devel qmake-qt5

#Next build the wallet:

qmake-qt5

make

An executable named MintCoin-Qt will be built.

#Windows

#Windows build instructions:

Download the QT Windows SDK and install it. You don't need the Symbian stuff, just the desktop Qt.
Download and extract the dependencies archive [1], or compile openssl, boost and dbcxx yourself.
Copy the contents of the folder "deps" to "X:\QtSDK\mingw", replace X:\ with the location where you installed the Qt SDK. Make sure that the contents of "deps\include" end up in the current "include" directory.
Open the .pro file in QT creator and build as normal (ctrl-B)
[1]	PGP signature: https://download.visucore.com/bitcoin/qtgui_deps_1.zip.sig (signed with RSA key ID 610945D0)
Mac OS X

Download and install the Qt Mac OS X SDK. It is recommended to also install Apple's Xcode with UNIX tools.
Download and install MacPorts.
Execute the following commands in a terminal to get the dependencies:
sudo port selfupdate
sudo port install boost db53 miniupnpc
Open the .pro file in Qt Creator and build as normal (cmd-B)
Build configuration options

#UPNnP port forwarding

To use UPnP for port forwarding behind a NAT router (recommended, as more connections overall allow for a faster and more stable bitcoin experience), pass the following argument to qmake:

#qmake "USE_UPNP=1"
(in Qt Creator, you can find the setting for additional qmake arguments under "Projects" -> "Build Settings" -> "Build Steps", then click "Details" next to qmake)

This requires miniupnpc for UPnP port mapping. It can be downloaded from http://miniupnp.tuxfamily.org/files/. UPnP support is not compiled in by default.

#Set USE_UPNP to a different value to control this:

USE_UPNP=-	no UPnP support, miniupnpc not required;
USE_UPNP=0	(the default) built with UPnP, support turned off by default at runtime;
USE_UPNP=1	build with UPnP support turned on by default at runtime.

Notification support for recent (k)ubuntu versions

To see desktop notifications on (k)ubuntu versions starting from 10.04, enable usage of the FreeDesktop notification interface through DBUS using the following qmake option:

qmake "USE_DBUS=1"
Generation of QR codes

libqrencode may be used to generate QRCode images for payment requests. It can be downloaded from http://fukuchi.org/works/qrencode/index.html.en, or installed via your package manager. Pass the USE_QRCODE flag to qmake to control this:

USE_QRCODE=0	(the default) No QRCode support - libqrcode not required

USE_QRCODE=1	QRCode support enabled



****************************

# Modern Build instructions

Debian

These build instructions should work for Debian and derivative systems, such as Ubuntu and Linux Mint.

We have some required packages. You can install these with apt:

{apt install qt5-qmake qt5-default qttools5-dev-tools \
    libboost-system-dev libboost-filesystem-dev \
    libboost-program-options-dev libboost-thread-dev \
    build-essential libboost-dev \
    libssl-dev libdb5.3++-dev libminiupnpc-dev}
    
Next build the wallet:

qmake
make


# focalpoint
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null

apt-get install apt-transport-https

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

# Extra 3

wget https://gist.githubusercontent.com/darosior/a5d93c6245a32f7a8bed2ac4e33a0011/raw/89c49515febbd55ffb60e4add9d08f299862cde4/install_libdb4.8.sh && chmod +x install_libdb4.8.sh && ./install_libdb4.8.sh amd64 && rm install_libdb4.8.sh
as root

# Estra 4

/root/.focal/focal.conf
rpcuser=users
rpcpassword=qweryuiop

# Extra 5

wget http://download.oracle.com/berkeley-db/db-4.8.30.zip

unzip db-4.8.30.zip

cd db-4.8.30

cd build_unix/

../dist/configure --prefix=/usr/local --enable-cxx

make

make install

compile error fix

sed -i 's/__atomic_compare_exchange/__atomic_compare_exchange_db/g' db-4.8.30/dbinc/atomic.h


