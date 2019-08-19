### 描述


给定一个整数数组和一个整数 k, 你需要在数组里找到不同的 k-diff 数对。这里将 k-diff 数对定义为一个整数对 (i, j), 其中 i 和 j 都是数组中的数字，且两数之差的绝对值是 k.

### 思路

一个Map，时间复杂度O(n)，使用一个。注意k<0 || k =0的边界情况。不需要去重。

```
    var findPairs = function(nums, k) {
        // 一个map可以解决
        var map = {}
        var res = 0
        for (let i = 0; i < nums.length; i++) {
            if (map[nums[i]] === undefined) {
                if ( map[nums[i] + k]) {
                    res ++
                }
                if (map[nums[i] - k]) {
                    res ++
                }
                map[nums[i]] = 1
            } else map[nums[i]] ++
        }
        if (k === 0) {
            for (let j of Object.keys(map)) {
                if (map[j] > 1) res ++
            }
        }
        if (k < 0) return 0
        return res
    };
```