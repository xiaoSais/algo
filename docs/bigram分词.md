### 描述

给出第一个词 first 和第二个词 second，考虑在某些文本 text 中可能以 "first second third" 形式出现的情况，其中 second 紧随 first 出现，third 紧随 second 出现。

对于每种这样的情况，将第三个词 "third" 添加到答案中，并返回答案。

### 思路
```
  var findOcurrences = function(text, first, second) {
    let arr = text.split(' ')
    let res = []
    if (text.length === 1) return res
    for (let i = 1; i < arr.length; i++) {
      if (arr[i - 1] === first && arr[i] === second && arr[i+1]) {
        res.push(arr[i+1])
      }
    }
    return res
  };
```