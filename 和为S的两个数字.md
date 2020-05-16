---
note:
    createdAt: 2020-05-14T12:40:36.947Z
    modifiedAt: 2020-05-16T13:28:33.422Z
    tags: [考点/知识迁移能力, 难度/3]
    id: ""
---
# 和为S的两个数字
#考点/知识迁移能力 #难度/3  [牛客网](https://www.nowcoder.com/practice/390da4f7a00f44bea7c2f3d19491311b?tpId=13&tqId=11195&tPage=2&rp=2&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
<!-- @crossnote.comment "id":"ca5ff777-3f7c-4911-84f4-e13fc8e6f5b2" -->  
## 题目描述
输入一个递增排序的数组和一个数字 S，在数组中查找两个数，使得他们的和正好是 S，如果有多对数字的和等于 S，输出两个数的乘积最小的。

**输出描述:**

```
对应每个测试案例，输出两个数，小的先输出。
```

## 答案

```javascript
function FindNumbersWithSum(array, sum) {
  var low = 0,
    high = array.length - 1;
  var currentSum = 0,
    result = [];
  while (low < high) {
    currentSum = array[low] + array[high];
    if (sum === currentSum) {
      result.push([array[low], array[high]]);
      low++;
    } else if (currentSum < sum) {
      low++;
    } else {
      high--;
    }
  }
  if (result.length === 0) {
    return [];
  } else {
    return result[0];
  }
}
```
