
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

本周是准备开始阅读 JavaScript权威指南第七版 英文版这本电子书， 这次先读了第一章的序言， 讲述了JavaScript的前世今生， 以及和NodeJS的配合。 

自己主要是梳理记录了一些不认识的英文单词

```JavaScript

majority
大多数

familiar
熟悉

dynamic
动态的

serious
严肃严谨的

trademark
特征

functionality
功能

environment
环境

embedded
把什么嵌入

obtain
取得

alternative
可替代的

advanced
进步
```

## Tip

### JS数组去重方法

#### 使用ES6中的 Set 方法

```javascript
let testArray = [1, 2, 2, 3, 4, 3, 5, 6, 5];
let result = [...new Set(testArray)];

console.log(result);	// [1, 2, 3, 4, 5, 6]
```

#### 使用数组filter和indexOf()方法



```javascript
let testArray = [1, 2, 2, 3, 4, 3, 5, 6, 5];  

function filterArray(oldArray) {   
  let newArray = oldArray.filter(function(element, index, array) {     
    return array.indexOf(element) === index;   
  })      
  return newArray; 
}  

console.log(filterArray(testArray)); 
```




## Share

[修改git里commit信息用户名](https://xie.infoq.cn/article/43c7833acbc45c0ccde52a90c)
