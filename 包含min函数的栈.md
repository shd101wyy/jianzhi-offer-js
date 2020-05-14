---
note:
    createdAt: 2020-05-14T12:45:52.637Z
    modifiedAt: 2020-05-14T14:39:56.754Z
    tags: [考点/举例让抽象具体化, 难度/4]
    id: ""
---
# 包含min函数的栈
#考点/举例让抽象具体化 #难度/4  [牛客网](https://www.nowcoder.com/practice/4c776177d2c04c2494f2555c9fcc1e49?tpId=13&tqId=11173&tPage=3&rp=3&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
<!-- @crossnote.comment "id":"2ecaa338-f2f3-4ecf-96d9-d74ac07f21ff" -->  
## 题目描述
定义栈的数据结构，请在该类型中实现一个能够得到栈中所含最小元素的 min 函数（时间复杂度应为 O(1)）。
注意：保证测试中不会当栈为空的时候，对栈调用 pop() 或者 min() 或者 top() 方法。

## 答案

```javascript
//用一个辅助空间，保存每次推入时的最小值情况，同时伴随弹出这个辅助空间的栈顶最小值也会弹出
function createStack() {
  let dataStack = [],
    minStack = [];

  const pop = function () {
    minStack.pop();
    return dataStack.pop();
  };

  const push = function (value) {
    dataStack.push(value);
    const len = minStack.length;
    if (len === 0 || minStack[len - 1] > value) {
      minStack.push(value);
    } else {
      minStack.push(minStack[len - 1]);
    }
  };

  const min = function () {
    return minStack[minStack.length - 1];
  };

  return {
    pop,
    min,
    push,
  };
}

let stack = createStack();
stack.push(5);
```