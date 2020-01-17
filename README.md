
# [bbr2 kernel for debian/ubuntu](https://github.com/qwerttvv/bbr-v2-alpha/releases "bbr2 kernel for debian/ubuntu")

### how to install

`dpkg -i XXX.deb`		分别安装两个文件，XXX.deb是文件名

`dpkg --get-selections|grep linux`		检查是否已经全部安装完毕

`apt-get purge XXX`		（可选）删除bbr2以外版本的内核，XXX是包的名字。如果提示内核正在使用也可以删除

`update-grub`		更新启动器

`reboot`		重启

`uname -a`		检测内核版本是否正确

`sysctl net.ipv4.tcp_available_congestion_control`		检测模块加载

`echo "net.ipv4.tcp_congestion_control=bbr2" >> /etc/sysctl.conf`		设置为bbr2算法

`reboot`		重启

`sysctl net.ipv4.tcp_congestion_control`		看到bbr2就成功了 / If you see bbr2, congratulations, you succeeded


------------








[bbr-v2-alpha from google](https://github.com/google/bbr/tree/v2alpha "bbr-v2-alpha from google")


最后，那个ecn模式我不建议添加，似乎那个是DCTCP支持，你加了也没有用


## done, enjoy
