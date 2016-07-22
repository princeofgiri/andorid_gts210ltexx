# Installing Dependencies, build only in 64 bit system (I'm using Debian Jessie)

aptitude install bison build-essential curl flex git gnupg gperf libesd0-dev liblz4-tool libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop maven pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev g++-multilib gcc-multilib lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev lib32readline6-dev libwxgtk3.0-dev openjdk-8-jdk

# Create Directories

mkdir -p ~/bin  
mkdir -p ~/android/system  

# Install the repo command

curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo  
chmod a+x ~/bin/repo  
source ~/.profile  

# Getting sources

repo init -u https://github.com/princeofgiri/android_gts210ltexx.git -b marshmallow-release

repo sync

# Building sources
./build.sh <device> <clean/noclean>

./build.sh chagalllte noclean
