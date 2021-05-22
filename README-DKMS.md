su -

apt install build-essential
apt install linux-headers
#apt install raspberrypi-kernel-headers
apt install dkms
mkdir /usr/src/ttyebus-1.8
cp ttyebusm.c /usr/src/ttyebus-1.8/
cp Makefile /usr/src/ttyebus-1.8/
cp dkms.conf /usr/src/ttyebus-1.8/
echo "ttyebus" /etc/modules-load.d/ttyebus.conf
dkms add -m ttyebus -v 1.8
dkms build -m ttyebus -v 1.8
dkms install -m ttyebus -v 1.8
