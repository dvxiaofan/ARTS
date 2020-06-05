
# Week02

## Algorithm

### [20]有效的括号

给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。

示例 1:

```JavaScript
输入: "()"
输出: true
示例 2:

输入: "()[]{}"
输出: true
示例 3:

输入: "(]"
输出: false
示例 4:

输入: "([)]"
输出: false
示例 5:

输入: "{[]}"
输出: true
```

**我的实现：**

```JavaScript
var isValid = function (s) {
  let arr = [];
  let len = s.length;

  if (len % 2) return false;

  for (let i = 0; i < len; i++) {
    const ele = s[i];
    switch (ele) {
      case '(':
        arr.push(ele);
        break;

      case '[':
        arr.push(ele);
        break;

      case '{':
        arr.push(ele);
        break;

      case ')':
        if (arr.pop() !== '(') return false;
        break;

      case ']':
        if (arr.pop() !== '[') return false;
        break;

      case '}':
        if (arr.pop() !== '{') return false;
        break;
    }
  }

  return !arr.length;
};
```

**思路:**

按顺序往数组中添加元素, 在遇到右括号的时候, 判断从数组中取出第一个是否是左括号.

## Review

### 文章

[How CORS (Cross-Origin Resource Sharing) Works](https://medium.com/swlh/how-cors-cross-origin-resource-sharing-works-79f959a84f0e)

### 阅读点评



## Tip


## Share

[使用 webpack 搭建一个简单的 React 脚手架](https://xie.infoq.cn/article/5167aad843c88da964b013d0d)
