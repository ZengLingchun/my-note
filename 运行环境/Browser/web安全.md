### 前言
在互联网时代，网站的数据安全与个人隐私受到了前所未有的挑战，各种新奇的攻击技术层出不穷。如何才能更好地保护我们的数据？本文记录一下几种常见的攻击与防御方法。

#### web攻击方式
- XSS (Cross-Site Scripting)，跨站脚本攻击
- CSRF(Cross Site Request Forgery)，即跨站请求伪造
- 点击劫持, 这是一种视觉欺骗的攻击手段
- SQL 注入，利用服务器漏洞插入非法数据
- OS注入
- 请求劫持
- DDOS

##### XSS攻击
> Cross-Site Scripting 跨站脚本攻击
XSS (Cross-Site Scripting)，跨站脚本攻击，因为缩写和CSS有冲突，所以改成XSS。跨站脚本攻击是指通过存在安全漏洞的Web网站注册用户的浏览器内允许非法的HTML标签或Javascript进行的一种攻击。

**跨站脚本攻击可能会造成一下影响**：
- 利用虚假输入表单骗取个人信息。
- 利用脚本窃取用户的Cookie值，被害者在不知情的情况下，帮助攻击者发送恶意请求。
- 显示伪造的图片或文章

> XSS攻击分类
- 反射性 - URL参数直接注入
- 存储型 - 存储到DB后读取时注入

**XSS的危害 - Scripting能干啥就干啥**
- 获取页面数据
- 获取cookie
- 劫持前端逻辑
- 发送请求
- 偷取网站的任意数据
- 偷取用户个人信息
- 欺骗用户

**XSS防范手段**

- HEAD
```javascript
res.header('X-XSS-Perotection', 1) //开启XSS过滤
```
- CSP 设置白名单
- 转义字符
- 黑名单 
> 用户输入的永远不可信，对用户输入的引号、尖括号、斜杠进行转义，
- 设置HttpOnly cookie
```javascript
res.header('Set-cookie', uuid=1; HttpOnly)
```
##### CSRF
> CSRF(Cross Site Request Forgery)，即跨站请求伪造，是⼀种常⻅的Web攻击，它利⽤⽤户已登录的身份，在⽤户毫不知情的情况下，以⽤户的名义完成⾮法操作。

- ⽤户已经登录了站点A，并在本地记录了cookie
- 在⽤户没有登出站点A的情况下（也就是cookie⽣效的情况下），访问了恶意攻击者提供的引诱危险站点B (B站点要求访问站点A)。
- 站点A没有做任何CSRF防御

**CSRF攻击危害**
- 利⽤⽤户登录态
- ⽤户不知情
- 完成业务请求
- 盗取⽤户资⾦（转账，消费）
- 冒充⽤户发帖背锅
- 损害⽹站声誉

**CSRF防御**
- 禁⽌第三⽅⽹站带Cookie -有兼容性问题
- Referer Check - Https不发送referer
- 验证码
