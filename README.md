
# [bbr2 kernel for debian/ubuntu](https://github.com/qwerttvv/bbr-v2-alpha/releases "bbr2 kernel for debian/ubuntu")

### how to install / 一步一步来，亲测两台debian10，完美

`dpkg -i XXX.deb`		分别安装两个文件，XXX.deb是文件名，就是你从我这儿下的俩文件

`dpkg --get-selections|grep linux`		检查俩文件是否已经全部安装完毕（并且为下一个步骤的可选项目做准备）

`apt-get purge XXX`		（可选）删除bbr2以外版本的内核，XXX是包的名字（上一步列表里的旧内核）。如果提示内核正在使用也可以删除（会问你是否终止，选否）

`update-grub`		更新启动器

`echo "net.ipv4.tcp_congestion_control=bbr2" >> /etc/sysctl.conf`		设置为bbr2算法

`reboot`		重启

`uname -a`		检测内核版本是否为刚刚安装的bbr2的版本

`sysctl net.ipv4.tcp_available_congestion_control`		检测模块加载里是否有bbr2

`sysctl net.ipv4.tcp_congestion_control`		这一步执行完，看到bbr2就成功了 / If you see bbr2, congratulations, you succeeded


------------








[bbr-v2-alpha from google](https://github.com/google/bbr/tree/v2alpha "bbr-v2-alpha from google")


最后，那个ecn我不建议添加开启，似乎那个是DCTCP支持，一个改进的TCP，你加了也没有用


## done, enjoy
