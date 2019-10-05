### 描述

在大小为 2N 的数组 A 中有 N+1 个不同的元素，其中有一个元素重复了 N 次。

返回重复了 N 次的那个元素。
### 思路

```
  var repeatedNTimes = function(A) {
    // 找到一个重复的数
    let map = {}
    for (let i = 0; i < A.length; i++) {
      if (map[A[i]]) return A[i]
      else map[A[i]] = true
    }
  };
```