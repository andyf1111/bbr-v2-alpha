# bbr-v2-alpha

# for debian/ubuntu

dpkg -i XXX.deb

update-grub

reboot


uname -a

sysctl net.ipv4.tcp_available_congestion_control

sysctl net.ipv4.tcp_ecn=1

echo 0 > /sys/module/tcp_bbr2/parameters/ecn_max_rtt_us

# del old one?

dpkg --get-selections|grep linux

sudo apt-get purge XXX



done, enjoy
