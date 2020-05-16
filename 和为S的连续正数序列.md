---
note:
    createdAt: 2020-05-14T12:30:56.928Z
    modifiedAt: 2020-05-16T13:26:48.666Z
    tags: [考点/知识迁移能力, 难度/3]
    id: ""
---
# 和为S的连续正数序列
#考点/知识迁移能力 #难度/3 [牛客网](https://www.nowcoder.com/practice/c451a3fd84b64cb19485dad758a55ebe?tpId=13&tqId=11194&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
<!-- @crossnote.comment "id":"cd750afe-dff0-4035-8561-b6b249f4b627" -->  
## 题目描述
小明很喜欢数学,有一天他在做数学作业时,要求计算出 9~16 的和,他马上就写出了正确答案是 100。但是他并不满足于此,他在想究竟有多少种连续的正数序列的和为 100 (至少包括两个数)。没多久,他就得到另一组连续正数和为 100 的序列:18，19，20，21，22。现在把问题交给你,你能不能也很快的找出所有和为 S 的连续正数序列? Good Luck!

**输出描述:**

```
输出所有和为S的连续正数序列。
序列内按照从小至大的顺序，序列间按照开始数字从小到大的顺序
```

## 答案

```javascript
/*
*初始化 low=1，high=2;
*low 到 high 序列和小于 sum，high++;大于sum，low++;
*当 low 增加到(1+sum)/2是停止
*
 */

function FindContinuousSequence(sum) {
  var results = [];
  var low = 1,
    high = 2;
  // 从1，2开始
  var currentSum = low + high;

  while (low < high) {
    // 如果满足条件，进栈
    if (currentSum === sum) {
      var result = [];
      for (var i = low; i <= high; ++i) {
        result.push(i);
      }
      results.push(result);
      // 从最小的右边重新出发
      currentSum -= low;
      low++;
    } else if (currentSum < sum) {
      // 总和不满足则继续增加数组数量
      high++;
      currentSum += high;
    } else {
      // 超过总和,减去最小的值
      currentSum -= low;
      low++;
    }
  }
  return results;
}
```
