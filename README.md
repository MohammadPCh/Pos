This Idiot Repo :)) Use It.
It's very Hard to Remember how to compile Fucking Pos Driver for Raspberry Pi. So i write all steps here for you. maybe when you want to install it the version od ubuntu changed! dont worry update your raspberry and enjoy!

A. Update your raspberry:
A1. sudo apt-get update
A2. sudo apt-get dist-upgrade
A3. uname -a

I attached C files of the driver so clone them:
B.  Clone Repository
B1. git clone https://github.com/Mohammadpch/pos
B2. Extract Linux Driver_ttyPos V314.zip
B3. cd ttyPos_V314_20170802
B4. make

you see this Error:
make[1]: *** /lib/modules/4.14.50-v7+/build: No such file or directory.  Stop.
Makefile:9: recipe for target 'all' failed
make: *** [all] Error 2
Don't worry you read these to solve these fucking problem.

C. Clone linux raspberry and Hard link it to /lib/modules/4.14.50-v7+/build
C1. cd /usr/src
C2. git clone --depth 1 https://github.com/raspberrypi/linux.git
C3. ln -s linux linux-4..18-v7+
C4. ln -s /usr/src/linux /lib/modules/4.1.18-v7+/build

Now Go to C files and Make adn install them.
D. Make Drive and Install
D1. Cd ttyPos_V314_20170802
D2. sudo make
D3. sudo make install

E. Check module insertet or Not:
E1. lsmod
E2. try to findttPos :)

if it's not inserted insert it manually:
F. Insert kernel module
F1. cd /lib/modules/4.14.62-v7+/ttPos
F2. insmod ttyPos.ko
F3. and Check E2 again.

Good Luck
