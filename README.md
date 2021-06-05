# Genshin-Impact-daily-miyobi

![badge](https://github.com/FW27623/Genshin-Impact-daily-miyobi/workflows/Mihoyo%20SignIn/badge.svg)

自动完成米游币任务
- 论坛区签到
- 阅读帖子
- 点赞帖子
- 分享帖子

## 安全提醒  
1 Workflow 是所有注册用户都可见的，包括 log，在旧版本中有一些 log 可能会泄露你们的 cookie string，请所有运行旧版本的及时更换成新版本，
并且修改现有 mihoyo 账户密码！！！

2 目前仅调用了米游币任务所必须的接口，并未 100% 模拟读取帖子点赞的所有流程，存在一定不可知的风险，请使用前务必知晓，下一步的开发会尝试尽可能模拟手动做任务的全部接口调用。

## 快速入门

### 安装依赖
```
yarn
```

### 获取 cookie （一般来说只有初次运行需要，如 token 过期重做此步即可）
1, 登录 https://bbs.mihoyo.com/ys/, 如果已经登录需要退出再重新登录。

2, 在控制台输入以下指令, 取得 login_ticket, 并将结果复制
```javascript
var a=function getCookie(name){var strCookie=document.cookie;var arrCookie=strCookie.split("; ");for(var i=0;i<arrCookie.length;i++){var arr=arrCookie[i].split("=");if(arr[0]==name)return arr[1]}return""};console.log(a("login_ticket"));
```

3, 本地运行 cookie.js, 传入上一步的 login_ticket, 获取用于爬虫的 stoken
```bash
node cookie.js '*******第二步的login_ticket*******'
```

### 本地运行
在运行 cookie.js 的时候，控制台会返回一个 cookie string 的命令，直接拷贝到控制台继续运行即可
```bash
COOKIE_STRING='stuid=*******;stoken=****************;login_ticket=********************;' node index.js
```
