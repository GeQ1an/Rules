![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/StickLogoMedium.png)
# 使用手册

### 简介

本规则适合任意地区使用 Quantumult X、境外使用 Quantumult 和 ClashX 的 “小白/懒人” 用户配合相关节点使用，最初通过 [lhie1 Rules](https://github.com/lhie1/Rules) 修改而来，目前参考了众多优秀规则，详见 [鸣谢](#鸣谢)。

### 频道

欢迎 [点击此处](https://t.me/usestick) 订阅 Stick Rules 的 Telegram 频道，及时获取规则更新详情，以及 Apple、iPhone、Mac 等有关信息。

---

* 支持应用
  * [Quantumult X](https://apps.apple.com/app/quantumult-x/id1443988620)
  * [Loon](https://apps.apple.com/app/loon/id1373567447)
  * [ClashX](https://github.com/yichengchen/clashX)（已停止更新）
  * [Quantumult](https://itunes.apple.com/app/quantumult/id1252015438)（已停止更新）
* [可实现功能](#function)
* 导入方式
  * [URL](#url)
* 使用教程
  * [拥有中国大陆节点](#购买大陆节点如已拥有请跳过此步骤)
  * [使用 Quantumult X](https://github.com/GeQ1an/Rules/blob/master/QuantumultX/README.md)
  * [使用 Loon](https://github.com/GeQ1an/Rules/blob/master/Loon/README.md)
  * [使用 ClashX](#在-clashx-中使用规则)
  * [使用 Quantumult](#在-quantumult-中添加规则以添加-quantumultconf-为例)
* [证书的安装及信任](#mitm)
* [常见问题](#qa)
* [鸣谢](#鸣谢)
* [关于](#关于)

---

### Function
- [x] 自动代理 / 全局代理
- [x] 解决本地 DNS 可能带来的干扰
- [x] 解决部分网站跳转问题
- [x] 可突破部分内网限制（公司、学校）
- [x] 拦截部分挖矿 JS 插件
- [x] 拦截常用应用程序及网页的行为分析
- [x] 拦截常用应用程序及网页的数据统计
- [x] 拦截常用应用程序及网页的隐私跟踪
- [x] 拦截各大购物网站的运营商劫持
- [x] 拦截 Content Security Policy 劫持
- [x] 拦截 CNNIC 根证书劫持
- [x] 屏蔽部分应用程序的启动广告
- [x] 屏蔽部分运营商劫持网页弹出的流量统计
- [x] 屏蔽部分运营商劫持网页弹出的漂浮球广告
- [x] 屏蔽常用视频广告
- [x] 屏蔽常用网站广告、其他流媒体网站广告
- [x] 屏蔽法轮功等反华势力网站
- [x] 境外网站直接连接
- [x] 中国大陆网站、App 代理连接
- [x] 仅中国大陆媒体代理连接 `New!`

### URL

Quantumult（长按复制链接即可）:
* [Quantumult.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult/Quantumult.conf): 代理所有中国大陆链接，同步 [lhie1 Rules](https://github.com/lhie1/Rules) 的广告拦截
* [Quantumult_lite.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult/Quantumult_lite.conf): 代理所有中国大陆链接，同步 [ConnersHua Profiles](https://github.com/ConnersHua/Profiles) 的广告拦截
* [Quantumult_media_only.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult/Quantumult_media_only.conf): 仅代理中国大陆媒体链接，同步 [lhie1 Rules](https://github.com/lhie1/Rules) 的广告拦截
* [Quantumult_media_only_lite.conf](https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult/Quantumult_media_only_lite.conf): 仅代理中国大陆媒体链接，同步 [ConnersHua Profiles](https://github.com/ConnersHua/Profiles) 的广告拦截
* [链接阻止 REJECTION](https://raw.githubusercontent.com/ConnersHua/Profiles/master/Quantumult/Rejection.conf): 请直接使用 [ConnersHua Profiles](https://github.com/ConnersHua/Profiles) 内的 Rejection

ClashX（下载配置文件到本地）:
* [Clash.yaml](https://raw.githubusercontent.com/GeQ1an/Rules/master/Clash/Clash.yaml): 使用前请参考文件内相关说明配置节点信息，并将节点信息加入到策略组

---

### 使用教程

#### 购买大陆节点（请自行寻找，下方服务已停止提供大陆节点）
* 推荐使用“Dler Cloud”，[点此](https://dlercloud.com/auth/register?affid=7237) 注册使用，如需邀请码可通过 Telegram 联系我获取。
````
  请根据个人需求自行选择套餐，充值、购买。
````

#### 在 Quantumult X 中使用规则
* 详情请转至 Quantumult X 目录的 [README.md](https://github.com/GeQ1an/Rules/blob/master/QuantumultX/README.md)

#### 在 Loon 中使用规则
* 详情请转至 Loon 目录的 [README.md](https://github.com/GeQ1an/Rules/blob/master/Loon/README.md)
#### 在 ClashX 中使用规则
（也适用于其他基于 Clash 内核的客户端，如 Clash for Android、Clash for Windows）
1. 打开下载好的 Clash.yaml 文件 (可使用`文本编辑`打开)，按照说明添加节点信息并编辑策略组节点，存储
2. 将配置文件放入 “$HOME/.config/clash/” 目录 (可通过 “点击状态栏 ClashX 图标 —— 配置 —— 打开配置文件夹” 来打开该目录)
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/ClashX01.png)
3. 应用配置文件 (方式为 “点击 ClashX 图标 —— 配置 —— 重载配置文件”)
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/ClashX02.png)
4. 点击 ClashX 图标选择各个策略组节点
#### 在 Quantumult 中添加规则（以添加 Quantumult.conf 为例）
1. 打开 Quantumult，点击“设置”选项卡，点击“订阅”，点击右上角“+”，选择“分流”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult01.PNG)
2. 进入的页面中，输入“名称”（如“Stick Rules”），粘贴规则地址 `https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult/Quantumult.conf`，在“高级”栏中勾选“个性化”，然后点击右上角的“保存”按钮
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult02.PNG)
3. “订阅”界面“分流”栏多出“Stick Rules”，向左滑动该条目，点击“替换”，选择 Netflix、PayPal、Apple、微软等服务的特殊政策，如不明白请选择“DIRECT”，点击右上角“保存”。回到“订阅”界面后，点击右上角“+”，选择“链接阻止”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult03.PNG)
4. 进入的页面中，输入“名称”（如“lhie1 Rejection”），粘贴规则地址`https://raw.githubusercontent.com/lhie1/Rules/master/Quantumult/Quantumult_URL.conf`，在“高级”栏中勾选“包含主机名”，然后点击右上角的“保存”按钮
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult04.PNG)
5. “订阅”界面“链接阻止栏”多出“lhie1 Rejection”，向左滑动该条目，点击“替换”，稍后会弹出“成功”对话框，点击“好”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult05.PNG)
6. [安装并信任证书](#mitm)
7. 规则有更新时，重新进行第 3 步和第 5 步的向左滑动条目，点击“替换”即可

---

### MitM

简介：MitM（即 Man-in-the-middle attack，用于解密 HTTPS 的流量）

iOS 9 以上的系统都需要在安装证书后到关于本机里信任证书才可使其证书有效。
````
1. 安装：
Quantumult：设置 - HTTPS 解密 - 打开

2. 信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任

备注：请在分别应用 FILTER 和 REJECTION 规则后安装；
     只需安装并信任一次，升级规则不会影响证书，无需重新安装。
注意：不要自己去生成新证书，会导致规则与证书不匹配使 MitM 失效，致使出现无法加载的问题。
````

---

### Q&A

#### 广告屏蔽未生效
````
绝大多数广告在未开启 Quantumult 时已经缓存到本地，广告屏蔽非立即生效，一般清理缓存就可以，部分应用需要卸载重装。
````

#### 耗电
````
当开启此类应用之后，由于所有的网络通信都被此类软件接管，所以所有的网络通讯耗电（如 WiFi、4G）都被计算在了此类应用上，使得此类软件在电量统计中占比很高。
但实际上，开启此类应用对电量消耗不会有显著影响。
````

#### 规则数量会对耗电、内存、速度产生影响吗？
````
不会，此类应用每次加载规则时都会生成一棵搜索树，可以理解为对主机名从后往前的有限状态机 DFA，并不是逐行匹配，并且对每次的匹配结果还有个哈希缓存。换句话说，2000 行的规则和 50 行的规则均为同一量级的时间复杂度 O(1)。
````

#### MitM 是什么？
````
用于解密 HTTPS 流量（即 Man-in-the-middle attack 简称 MitM）。
````

#### 为什么需要开启 MitM 功能？
````
屏蔽部分广告（如：新浪微博的启动广告）需要解密其 HTTPS 流量才可获取广告请求并进行拦截。
````

#### MitM 会影响安全（购物/网银/隐私）或性能/速度吗？
````
MitM 仅仅对预设的 Hostname 名单（公开/开源）内的地址进行 HTTPS 流量解密，不会造成安全问题，也几乎不会对性能/速度造成影响。
MitM：https://zh.wikipedia.org/wiki/中间人攻击
````

#### 打开某些应用（如：知乎、即刻等）无法连接？
````
检查证书，请确保已经安装证书并信任。
````

#### 为什么只支持 Quantumult 和 ClashX 这两款软件？
````
个人认为 Quantumult 的稳定性要好于 Shadowrocket，所以推荐使用。至于 Surge，有很多大佬（如 lhie1）的规则已经有了各种策略组，直接选择即可。macOS 上除了 Surge 和 ClashX 也没有什么别的好用的代理软件了。
````

---

### 鸣谢
* [lhie1 Rules](https://github.com/dler-io/Rules)
* [DivineEngine Profiles](https://github.com/DivineEngine/Profiles/tree/master)
* [Hackl0us SS-Rule-Snippet](https://github.com/Hackl0us/SS-Rule-Snippet)
* [Dler Cloud](https://dlercloud.com)

---

### 关于

我是一名在韩留学生，在境外时会需要大陆 IP 来使用国内部分服务，于是修改了 lhie1 规则使用，欢迎在境外的小伙伴使用。平时课程比较多，且并非学习相关专业，完全由课余时间修改，所以无法保证定期更新。现在的规则有了四个版本，应该能满足大家的需求。如有建议或缺漏，请及时反馈：[Telegram](https://t.me/GeQ1an)。

您的打赏将是我持续完善、更新规则的动力，欢迎扫描下方二维码或复制吱口令打赏，感谢。<br>
`#吱口令#长按复制此条消息，去支付宝首页进行搜索粘贴即可给我打赏9Rgv0b74jI#`
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Pay2Me.png)
