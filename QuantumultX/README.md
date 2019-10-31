![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/StickLogoMedium.png)
# 使用手册

### 介绍

有关 Stick Rules 的详细介绍请转至项目主目录的 [README.md](https://github.com/GeQ1an/Rules/blob/master/README.md)<br>
<br>
本文件为 Quantumult X 专用规则使用手册，目前 Quantumult X 规则有 “广告&阻止”、“苹果服务”、“中国媒体”、“国际媒体”、“Netflix”、“YouTube”、“微软服务”、“PayPal”、“外部网络”、“大陆网络”、“Speedtest” 和 “其他” 列表 (策略组) 可供选择。
````
策略组的出现是为了更为便捷地切换节点
应本着 “保质” 而非 “保量” 原则
而并非策略组的数量越多越好
````

---

### 使用
#### 方法一  拷贝配置文件 `更适用于初次配置或重新配置`
将 [QuantumultX.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/QuantumultX.conf) 所有内容复制，在 Quantumult X 中选择编辑配置文件，清空后粘贴，保存；<br>
分别同步 “分流规则” 和 “Rewrite” 的 “引用”；<br>
添加节点后，可自行[编辑策略组](#编辑策略组)。
````
正式使用前请打开 MitM 功能，安装并信任证书（根据提示操作）。
也可使用其他已信任证书，将 “密码” 和 “P12” 分别填写到配置文件中的 “passphrase=” 和 “p12=” 后（注意删除前面的 ; 符号）。
````

#### 方法二  粘贴规则列表 `更适用于仅想更换规则`
复制以下内容：<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/AdBlock.list, tag=AdBlock (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Apple.list, tag=Apple (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/CMedia.list, tag=CMedia (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/GMedia.list, tag=GMedia (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Netflix.list, tag=Netflix (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/YouTube.list, tag=YouTube (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Microsoft.list, tag=Microsoft (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/PayPal.list, tag=PayPal (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Outside.list, tag=Outside (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Mainland.list, tag=Mainland (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Speedtest.list, tag=Speedtest (Stick Rules), enabled=true`<br>
`https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/LAN.list, tag=LAN (Stick Rules), enabled=true`<br>
粘贴到配置文件 [filter_remote] 中。

#### 方法三  自行引用规则 `不推荐!`
因需要引用的规则地址较多，此方法较为麻烦，不推荐使用，恕不进行详细说明。

````
使用方法二和方法三时，请注意
在配置文件 [filter_local] 处自行添加最终规则 (final, Others)，
在配置文件 [policy] 处添加 Others 策略组 (static=Others, Outside, direct)。
````

#### 添加节点
1. 直接在 “节点” 处通过手动/SS URL/扫码添加节点，不做过多阐述。
2. 直接通过机场提供的订阅链接添加节点，不做过多阐述。
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX01.png)
3. 按地区或类型订阅。如果机场提供 SS 订阅可选项，请直接使用；如果没有提供的话可使用 [Shawn 的 API](https://github.com/KOP-XIAO/QuantumultX-Surge-API) 对机场提供的 SS 订阅链接进行过滤、对 Surge list 进行转换，添加到 Quantumult X 订阅。订阅后，可以选择使用[节点策略组](#节点策略组)。
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX02.png)

#### 节点策略组
添加地区或类型节点订阅后，可在资源列表处 “向右滑动订阅” ———— “更多”，创建策略组 (建议选择 “健康检查” 方式，创建后可通过[编辑策略组](#编辑策略组)对节点进行排序)。
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
![](https://raw.githubusercontent.com/zealson/Zure/master/Other/Local_Icon.png)<br>
（图片来自 [Zure -- Quantumult X Policy Icon Set](https://github.com/zealson/Zure)，需要策略组国旗图标或其他图标也可以到这里订阅或下载）

#### 编辑策略组
在软件主页，长按某个策略组即可进入编辑模式，可向某个策略组添加节点。<br>
亦可对已经存在的策略组内容进行排序 (如对已经创建的健康检查策略组或负载均衡策略组内节点进行排序)。
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/QuantumultX04.png)

#### 更新规则
一般重新载入软件时会自动更新引用（包括节点引用和规则引用），无需手动操作。<br>
如需手动更新，打开 “分流” 中的 “引用”，点击右上角 “全部同步” 即可同步最新规则。

---
该文档基于 Quantumult X 1.0.2 版本编写，部分可选功能已在配置文件中注明，请注意查看。<br>
更多功能还请自己摸索，如有问题请在 [Telegram](https://t.me/GeQ1an) 联系我。
