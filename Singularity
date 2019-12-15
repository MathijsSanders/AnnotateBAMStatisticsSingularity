BootStrap: debootstrap
OSVersion: xenial
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%labels
MAINTAINER MathijsSanders

%runscript


%post
sed -i 's/$/ universe/' /etc/apt/sources.list
apt-get update
apt-get -y install build-essential git zlib1g-dev
apt-get clean
cd /tmp/
git clone https://github.com/MathijsSanders/AnnotateBAMStatistics.git
cd AnnotateBAMStatistics
make all
cp /tmp/AnnotateBAMStatistics/dist/Release/GNU-Linux/AnnotateBAMStatistics /usr/bin/
mkdir /code
cp /tmp/AnnotateBAMStatistics/runScript.sh /code/
chmod u+x /code/runScript.sh
rm -rf /tmp/AnnotateBAMStatistics	

%environment
export PATH=$PATH:/usr/games
export LC_ALL=C
