![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/StickLogoMedium.png)
# 使用手册

### 介绍

有关 Stick Rules 的更多信息请转至项目主目录的 [README.md](https://github.com/GeQ1an/Rules/blob/master/README.md)<br>
<br>
本文件为 Quantumult X 专用规则使用手册，目前 Quantumult X 规则有 “广告&阻止”、“苹果服务”、“中国媒体”、“网易云音乐”、“国际媒体”、“Netflix”、“Spotify”、“YouTube”、“外部网络”、“Telegram”、“PayPal”、“大陆网络”、“微软服务”、“Speedtest” 和 “其他” 规则列表可供选择。

---

### 频道

欢迎 [点击此处](https://t.me/usestick) 订阅 Stick Rules 的 Telegram 频道，及时获取规则更新详情，以及 Apple、iPhone、Mac 等相关信息。

---

### 使用

#### 根据样本文件快速配置
如使用高于 1.0.3(148) 版本的 Quantumult X，且使用 Dler Cloud，请直接查看 [Sample_DlerCloud.conf](https://github.com/GeQ1an/Rules/blob/master/QuantumultX/Sample/Sample_DlerCloud.conf)，填写自己的托管 token 便可以快速配置。<br>
<br>
*我将在近期更新通用型样本配置文件，以方便入门级用户使用。*

#### 方法一  拷贝配置文件 `更适用于初次配置或重新配置`
将 [QuantumultX.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/QuantumultX.conf) 所有内容复制，在 Quantumult X 中选择编辑配置文件，清空后粘贴，修改自己的订阅链接，按需编辑，保存；<br>
[添加节点](#添加节点) 后，可自行 [编辑策略组](#编辑策略组)。
````
正式使用前请打开 MitM 功能，安装并信任证书 (根据提示操作)。
也可使用其他已信任证书，将 “密码” 和 “P12” 分别填写到配置文件中的 “passphrase=” 和 “p12=” 后。
````

#### 方法二  粘贴规则列表 `更适用于仅想更换规则`
默认不启用网易云音乐（包含在 CMedia 内）、Netflix/Disney Plus/Spotify/YouTube（包含在 GMedia 内）、TikTok/Telegram/PayPal（包含在 Outside 内）、微软（包含在 Mainland 内）规则，如需使用请修改 false 为 true，对于完全不需要的规则，删除即可。<br>
复制以下内容：
```
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Special.list, tag=Special (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/AdBlock.list, tag=AdBlock (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Netease%20Music.list, tag=Netease Music (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/CMedia.list, tag=CMedia (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Netflix.list, tag=Netflix (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Disney%20Plus.list, tag=Disney+ (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Spotify.list, tag=Spotify (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/YouTube.list, tag=YouTube (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/GMedia.list, tag=GMedia (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Apple.list, tag=Apple (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/TikTok.list, tag=TikTok (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Telegram.list, tag=Telegram (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/PayPal.list, tag=PayPal (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Microsoft.list, tag=Microsoft (Stick Rules), update-interval=43200, enabled=false
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Speedtest.list, tag=Speedtest (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Outside.list, tag=Outside (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Mainland.list, tag=Mainland (Stick Rules), update-interval=43200, enabled=true
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/LAN.list, tag=LAN (Stick Rules), update-interval=43200, enabled=true
```
粘贴到配置文件 [filter_remote] 中。

#### 方法三  自行引用规则 `不推荐!`
因需要引用的规则地址较多，此方法较为麻烦，不推荐使用，恕不进行详细说明。

````
使用方法二和方法三时，请注意
在配置文件 [filter_local] 处自行添加最终规则 `final, Others`，
在配置文件 [policy] 处添加 Others 策略组 `static=Others, Outside, direct`。
无论使用哪种方式导入规则都应先启用 MitM 功能
````

#### 添加节点
1. 直接在 “节点” 处通过手动/SS URL/扫码添加单个节点，不做过多阐述。
2. 直接通过机场提供的订阅链接批量添加节点，不做过多阐述。<br>
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX01.png)
3. 按节点地区或类型订阅。<br>
如果机场提供 SS 订阅可选项 (如 [Dler Cloud](https://dlercloud.com))，请直接使用；如果没有提供的话，可以使用 [Shawn 的 API](https://github.com/KOP-XIAO/QuantumultX-Surge-API) 对机场提供的 SS 订阅进行过滤、对 Surge list 进行转换，以便添加到 Quantumult X 订阅。<br>
添加好订阅后，可以选择使用 [节点策略组](#节点策略组)。<br>
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX02.png)

#### 节点策略组
添加地区或类型节点订阅后，可在资源列表处 “向右滑动订阅” —— “更多” 创建策略组 (建议选择 “健康检查” 方式，创建后可通过 [编辑策略组](#编辑策略组) 对节点进行排序)。<br>
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX03.png)
````
static 策略是静态策略，需要手动选择节点
available 策略是健康检查策略，将会自动使用策略组内第一个可联通的节点（在触发策略时启动 URL 测试）
round-robbin 策略是负载均衡策略，会轮询对每个节点进行测试，下一个链接使用最优节点（可能出现 IP 频繁变动，导致风险）
````

#### 策略组图标
最新的配置文件内，包含远程图标链接，无需手动添加。当图标有更新时，手动清空本地缓存目录，重新打开 app 即可。<br>
如需手动添加，请按如下操作进行：<br>
在 [Quantumult X 项目主页](https://github.com/GeQ1an/Rules/tree/master/QuantumultX) 下载 “QuantumultX_Images_E*.zip” 解压，放入本地 Quantumult X —— Images 目录下（请注意保证策略组名称和图片名称一致）<br>
![](https://raw.githubusercontent.com/Koolson/Qure/master/Other/Local_Icon.png)<br>
（图片来自 [Qure -- Quantumult X Policy Icon Set](https://github.com/Koolson/Qure)，需要国旗策略组图标或其他图标也可以到这里订阅或下载）

#### 编辑策略组
在 Quantumult X 主页，长按某个策略组即可进入编辑模式，可向某个策略组添加节点或其他策略。<br>
亦可对已经存在的策略组内容进行删减、排序 (如对已经创建的健康检查策略组或负载均衡策略组内的节点进行排序)。<br>
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX04.png)

#### 更新规则
一般重新载入软件时会自动更新引用 (包括节点引用和规则引用)，无需手动操作。<br>
如需手动更新，可长按主页右下角的功能键更新全部远程资源 (需在设置内打开 “长按主页功能键切换模式” 开关)。

#### 替换 GeoIP 数据源 `推荐!`
在 Quantumult X 主页，点击右下角【功能键】进入设置，在设置中下拉到最下方，点击【其他设置】，找到 GeoLite2，点击右侧【来源】，粘贴下方两个链接之一，保存后开启自动更新，选择周期为【7 日】。<br>
<br>
链接 1：[GitHub 直连链接](https://github.com/Hackl0us/GeoIP2-CN/raw/release/Country.mmdb) | 链接 2：[CDN 加速链接](https://fastly.jsdelivr.net/gh/Hackl0us/GeoIP2-CN@release/Country.mmdb)
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX05.png)

感谢 Hackl0us 的 [GeoIP2-CN](https://github.com/Hackl0us/GeoIP2-CN) 项目。

---
该文档基于 Quantumult X 1.0.5 版本编写，部分可选功能已在配置文件中注明，请注意查看。<br>
更多功能还请自己摸索，如有问题请在 [Telegram](https://t.me/GeQ1an) 联系我。
