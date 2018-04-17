# 使用手册

### 简介

本规则适合境外小白用户配合国内节点翻回大陆使用，由 lhie1 [墙洞 Rules](https://github.com/lhie1/Rules) 修改而来。

---
* 支持应用
  * Quantumult
  * Shadowrocket
* [可实现功能](#function)
* 导入方式
  * [URL](#url)
* [证书的安装及信任](#mitm)
* 使用教程
  * [拥有大陆节点](#使用教程)
  * [Quantumult](#使用教程)
  * [Shadowrocket](#使用教程)
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
Shadowrocket:
   远程文件：https://raw.githubusercontent.com/GeQ1an/Rules/master/Shadowrocket.conf
````

---

### MitM

简介：MitM（即 Man-in-the-middle attack，用于解密 HTTPS 的流量）

iOS 9 以上的系统都需要在安装证书后到关于本机里信任证书才可使其证书有效。
````
1. 安装：
Quantumult：Settings - HTTPS - HTTPS Decryption
Shadowrocket：设置 - 证书 - 安装证书

2. 信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任

备注：Quantumult 请在分别应用 FILTER 和 REJECTION 规则后安装；
     Shadowrocket 请在下载并使用配置后安装。
     只需安装并信任一次，升级规则不会影响证书，无需重新安装。
注意：不要自己去生成新证书，会导致规则与证书不匹配使 MitM 失效，会直接导致无法加载的问题。
````

---

### 使用教程

1. 购买大陆节点（如已拥有请跳过此步骤），推荐使用“墙洞云服务”，[点此](https://xn--nos809b.com/auth/register?affid=7237)注册。
````
  注册后，请根据个人需求选择套餐，充值、购买，
  购买成功后请添加中转规则，起源节点选择“要使用的节点”，目标节点选择“不进行中转”，端口自行选择，优先级大于“1”，
  这样就可以直接使用大陆节点，将节点信息添加到 Quantumult 或 Shadowrocket 中使用。
   
  备注：建议购买成功后先 ping 节点地址，选择最优线路使用。
````

2. 在 Quantumult 中添加规则。
````
  ① 打开 Quantumult，点击 Settings 选项卡，点击 Favorites
````


---

### 鸣谢
* [lhie1](https://github.com/lhie1/Rules)

---

### 关于

我是一名在韩留学生，平时课程很多，且并非学习相关专业，完全由课余时间修改。在境外有时需要大陆 IP 来使用国内部分服务，于是修改墙洞规则以自用，同时也欢迎境外小伙伴使用，如有缺漏，请及时反馈。[微博](http://weibo.com/lixin19940325) 、[Telegram](https://t.me/GeQ1an) 。
