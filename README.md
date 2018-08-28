# This Idiot Repo :)) Use It.<br/>
It's very Hard to Remember how to compile Fucking Pos Driver for Raspberry Pi. So i write all steps here for you. maybe when you want to install it the version of Rasbian changed! don't worry update your raspberry and enjoy!<br/>
<br/>

### A. Update your raspberry:
1. sudo apt-get update
2. sudo apt-get dist-upgrade
3. uname -a

I attached C files of the driver so clone them:<br/>

### B. Clone Repository
1. git clone https://github.com/Mohammadpch/pos
2. Extract Linux Driver_ttyPos V314.zip
3. cd ttyPos_V314_20170802
4. make

you see this Error:
make[1]: *** /lib/modules/4.14.50-v7+/build: No such file or directory.  Stop.
Makefile:9: recipe for target 'all' failed
make: *** [all] Error 2
Don't worry you read these to solve these fucking problem.

### C. Clone linux raspberry and Hard link it 
1. cd /usr/src
2. git clone --depth 1 https://github.com/raspberrypi/linux.git<br/>
3. ln -s linux linux-4..18-v7+
4. ln -s /usr/src/linux /lib/modules/4.1.18-v7+/build

Now Go to C files and Make adn install them.
### D. Make Drive and Install
1. Cd ttyPos_V314_20170802
2. sudo make
3. sudo make install

### E. Check module insertet or Not:
1. lsmod
2. try to find ttPos :)

if it's not inserted insert it manually:
### F. Insert kernel module
1. cd /lib/modules/4.14.62-v7+/ttPos
2. insmod ttyPos.ko
3. and Check E2 again.

Good Luck
