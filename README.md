# This Idiot Repo :)) Use It.<br/>
It's very Hard to Remember how to compile Fucking Pos Driver for Raspberry Pi. So i write all steps here for you. maybe when you want to install it the version od ubuntu changed! dont worry update your raspberry and enjoy!<br/>
<br/>
### A. Update your raspberry:<br/>
#### A1. sudo apt-get update<br/>
#### A2. sudo apt-get dist-upgrade<br/>
#### A3. uname -a<br/>
<br/>
I attached C files of the driver so clone them:<br/>
B.  Clone Repository<br/>
B1. git clone https://github.com/Mohammadpch/pos<br/>
B2. Extract Linux Driver_ttyPos V314.zip<br/>
B3. cd ttyPos_V314_20170802<br/>
B4. make<br/>
<br/>
you see this Error:<br/>
make[1]: *** /lib/modules/4.14.50-v7+/build: No such file or directory.  Stop.<br/>
Makefile:9: recipe for target 'all' failed<br/>
make: *** [all] Error 2<br/>
Don't worry you read these to solve these fucking problem.<br/>
<br/>
C. Clone linux raspberry and Hard link it to /lib/modules/4.14.50-v7+/build<br/>
C1. cd /usr/src<br/>
C2. git clone --depth 1 https://github.com/raspberrypi/linux.git<br/>
C3. ln -s linux linux-4..18-v7+<br/>
C4. ln -s /usr/src/linux /lib/modules/4.1.18-v7+/build<br/>
<br/>
Now Go to C files and Make adn install them.<br/>
D. Make Drive and Install<br/>
D1. Cd ttyPos_V314_20170802<br/>
D2. sudo make<br/>
D3. sudo make install<br/>
<br/>
E. Check module insertet or Not:<br/>
E1. lsmod<br/>
E2. try to findttPos :)<br/>
<br/>
if it's not inserted insert it manually:<br/>
F. Insert kernel module<br/>
F1. cd /lib/modules/4.14.62-v7+/ttPos<br/>
F2. insmod ttyPos.ko<br/>
F3. and Check E2 again.<br/>
<br/>
Good Luck<br/>
