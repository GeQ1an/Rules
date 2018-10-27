# 使用手册

### 简介

本规则适合境外小白用户配合国内节点翻回大陆使用，由 [lhie1 Rules](https://github.com/lhie1/Rules) 修改而来。

---
* 支持应用
  * [Quantumult](https://itunes.apple.com/app/quantumult/id1252015438?mt=8)
* [可实现功能](#function)
* 导入方式
  * [URL](#url)
* 使用教程
  * [拥有大陆节点](#购买大陆节点如已拥有请跳过此步骤)
  * [Quantumult](#在-quantumult-中添加规则)
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
- [x] 中国大陆网站、App 代理连接
- [x] 境外网站直接连接

### URL

````
Quantumult：
   FILTER：https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult.conf
   REJECTION：https://raw.githubusercontent.com/lhie1/Rules/master/Quantumult/Quantumult_URL.conf
````

---

### 使用教程

#### 购买大陆节点(如已拥有请跳过此步骤)
* 推荐使用“Dler Cloud”，[点此](https://dlercloud.com/auth/register?affid=7237)注册使用，以下内容针对“Dler Cloud”说明。
````
  注册后，请根据个人需求自行选择套餐，充值、购买，
  购买后请添加中转规则，起源节点选择“要使用的节点”，目标节点选择“不进行中转”，端口选择“所有端口”，优先级大于“1”，
  这样就可以直接连接大陆节点，将节点信息添加到 Quantumult 或 Shadowrocket 中使用。
   
  备注：建议购买成功后先 ping 各个大陆(CN)节点地址，选择最优线路使用。
````

#### 在 Quantumult 中添加规则
1. 打开 Quantumult，点击“Settings”选项卡，点击“Favorites”，点击右上角“+”，选择“Filter”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult01.PNG)
2. 进入的页面中，General 一栏， Name 输入“Stick Rules”，URL 粘贴规则地址 `https://raw.githubusercontent.com/GeQ1an/Rules/master/Quantumult.conf`，在 Option 栏中勾选“Filter Action”，然后点击右上角的“Save”按钮
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult02.PNG)
3. Favorites 界面 Filter 栏多出“Stick Rules”，向左滑动该条目，点击“Replace”，选择 Netflix、PayPal、Apple、微软等服务的特殊政策，如不明白请选择“DIRECT”，点击右上角“OK”。回到 Favorites 界面后，点击右上角“+”，选择“Rejection”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult03.PNG)
4. 进入的页面中，General 一栏， Name 输入“墙洞 Rejection”，URL 粘贴规则地址`https://raw.githubusercontent.com/lhie1/Rules/master/Quantumult/Quantumult_URL.conf`，在 Option 栏中勾选“Including Host Names”，然后点击右上角的“Save”按钮
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult04.PNG)
5. Favorites 界面 Rejection 栏多出“墙洞 Rejection”，向左滑动该条目，点击“Replace”，稍后会弹出“Success”对话框，点击“OK”
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Quantumult05.PNG)
6. [安装并信任证书](#mitm)
7. 规则有更新时，重新进行第 3 步和第 5 步的向左滑动条目，点击“Replace”即可

---

### MitM

简介：MitM（即 Man-in-the-middle attack，用于解密 HTTPS 的流量）

iOS 9 以上的系统都需要在安装证书后到关于本机里信任证书才可使其证书有效。
````
1. 安装：
Quantumult：Settings - HTTPS - HTTPS Decryption

2. 信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任

备注：Quantumult 请在分别应用 FILTER 和 REJECTION 规则后安装；
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

---

### 鸣谢
* [lhie1](https://github.com/lhie1/Rules)

---

### 关于

我是一名在韩留学生，在境外时会需要大陆 IP 来使用国内部分服务，于是修改了 lhie1 规则使用，欢迎在境外的小伙伴使用。平时课程比较多，且并非学习相关专业，完全由课余时间修改，所以无法保证定期更新。现在的规则是代理全部大陆网站、IP，以后会增加只代理视频、音乐等强制要求大陆 IP 服务的规则。如有建议或缺漏，请及时反馈：[Telegram](https://t.me/GeQ1an)。

您的打赏将是我持续完善、更新规则的动力，欢迎扫描下方二维码打赏，感谢。
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Pay.png)
