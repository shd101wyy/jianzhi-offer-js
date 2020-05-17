---
note:
    createdAt: 2020-05-14T12:45:15.404Z
    modifiedAt: 2020-05-17T07:57:02.972Z
    tags: [难度/4]
    id: ""
---
# 最小的K个数
#考点/时间效率 #难度/4  [牛客网](https://www.nowcoder.com/practice/6a296eb82cf844ca8539b57c23e6e9bf?tpId=13&tqId=11182&tPage=3&rp=3&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)

<!-- @crossnote.comment "id":"539702bd-5a60-4cf0-b85b-198f76d0641a" -->  
## 题目描述
输入 n 个整数，找出其中最小的 K 个数。例如输入4,5,1,6,2,7,3,8 这 8 个数字，则最小的 4 个数字是 1,2,3,4,。

## 答案

```javascript
function GetLeastNumbers_Solution(input, k) {
  if (k > input.length) {
    return [];
  }
  var temp = input.sort();
  return temp.slice(0, k);
}
```