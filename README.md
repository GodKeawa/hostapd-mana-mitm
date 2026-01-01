# hostapd-mana-mitm
本项目为archlinux AUR PKGBUILD的fork，如果你使用archlinux，那么直接makepkg即可
如果你使用其他发行版，那么请将`hostapd-mana-peap-mitm.patch`应用到原始的hostapd-mana仓库中
hostapd-mana：https://github.com/sensepost/hostapd-mana

本项目需要配合wpa-sycophant进行中间人攻击，请前往修改版的wpa-sycophant获取支持MitM的sycophant以及网络桥接脚本
wpa-sycophant-mitm：https://github.com/GodKeawa/wpa_sycophant-mitm

提供了MitM功能，通过读取并转发sycophant获取的MSCHAPV2的peer_challenge的Response实现，过去的sycophant不会进行转发，而是直接拒绝连接，当前版本将支持连接Rogue AP
提供了更好的eap_server的eap_user解析功能，现在能够查询条目，优先使用有配置密码的条目，然后使用通用条目