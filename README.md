# Pos
This Idiot Repo :)) Use It.
It's very Hard to Remember how to compile Fucking Pos Driver for Raspberry Pi. So i write all steps here for you. maybe when you want to install it the version od ubuntu changed! dont worry update your raspberry and enjoy!

A. Update your raspberry:
A1. sudo apt-get update
A2. sudo apt-get dist-upgrade

I attached C files of the driver so clone them:
B.Clone Repository
B1. git clone https://github.com/Mohammadpch/pos
B2. Extract Linux Driver_ttyPos V314.zip
B3. cd ttyPos_V314_20170802
B4. make

you see this Error:
make[1]: *** /lib/modules/4.14.50-v7+/build: No such file or directory.  Stop.
Makefile:9: recipe for target 'all' failed
make: *** [all] Error 2
Don't worry you read these to solve these fucking problem.
cd /usr/src
git clone --depth 1 https://github.com/raspberrypi/linux.git
ln -s linux linux-4.1.18-v7+
ln -s /usr/src/linux /lib/modules/4.1.18-v7+/build
cd linux
