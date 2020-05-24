
# Week01

## Algorithm

> 先从最简单的算法题开始了， 以后看情况选择其他难度！

### 坐旋转字符串

字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。

**示例 1：**

```JavaScript
输入: s = "abcdefg", k = 2
输出: "cdefgab"
```

**示例 2：**

```JavaScript
输入: s = "lrloseumgh", k = 6
输出: "umghlrlose"
```

**限制：**

- `1 <= k < s.length <= 10000`

**我的实现：**

```JavaScript
var reverseLeftWords = function(s, n) {
  let str1 = s.slice(0, n);
  let str2 = s.slice(n)
  return str2 + str1
};
```

**思路:**

通过给定的数字来把元字符串截取成两部分,然后再把两部分位置调换拼接在一起

## Review

### 文章

[How CORS (Cross-Origin Resource Sharing) Works](https://medium.com/swlh/how-cors-cross-origin-resource-sharing-works-79f959a84f0e)

### 阅读点评

本文主要讲述了什么是浏览器跨域以及如何使用cors解决跨域问题。

#### 跨域的概念

简单来说， 跨域就是浏览器为了安全采用的一种同源访问策略， 如果协议、域名、端口号有不一样的， 则该请求会被拒绝。例如API接口地址是`https://api.github.com`, 但你从客户端去访问另一个地址， 如`https://example.com`，浏览器就回拒绝该请求。

#### CORS 如何工作

`Access-Control-Allow-Origin:` 后面写上需要跨域访问的URL地址， 也就是设置为白名单。

**在项目中使用CORS:**

1. 安装

   ```node
   npm install cors
   ```

2. 在服务端进行配置

   ```js
   // 引入cors
   var cors = require('cors');
   // 配置使用
   app.use(
     cors({
       origin: "*",
       methods: "GET,HEAD,PUT,PATCH,POST,DELETE",
       preflightContinue: false
     })
   );
   ```

其中‘*’是个通配符， 代表允许所有域名进行访问

## Tip

### 通过nvm管理电脑上的Node版本

有时候因为运行不同的项目需要选择不同的Node版本,通过nvm可以很容易的安装需要的Node版本和选择对应的版本使用

#### 基本用法

- 安装

```Node
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

- 查看所有可以安装的LTS版本（长期支持版）

```Node
nvm ls-remote --lts
```

- 安装指定版本的 node

```node
nvm install v9.5.0
```

- 查看已安装的node

```Node
nvm ls
```

- 切换版本

```Node
nvm use v6.9.0
```

## Share

[使用 webpack 搭建一个简单的 React 脚手架](https://xie.infoq.cn/article/5167aad843c88da964b013d0d)