---
note:
    createdAt: 2020-05-14T12:45:36.643Z
    modifiedAt: 2020-05-14T14:38:16.659Z
    tags: [考点/代码的鲁棒性, 难度/4]
    id: ""
---
# 链表中倒数第k个结点
#考点/代码的鲁棒性 #难度/4  [牛客网](https://www.nowcoder.com/practice/529d3ae5a407492994ad2a246518148a?tpId=13&tqId=11167&tPage=3&rp=3&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
<!-- @crossnote.comment "id":"68075386-ff51-454c-9130-00b5a6fdc228" -->  
## 题目描述
输入一个链表，输出该链表中倒数第k个结点。

## 答案

```javascript
/*function ListNode(x){
    this.val = x;
    this.next = null;
}*/
function FindKthToTail(head, k) {
  if (!head) {
    return;
  }
  var temp = [];
  while (head) {
    temp.push(head);
    head = head.next;
  }
  temp = temp.reverse();
  return temp[k - 1];
}
module.exports = {
  FindKthToTail: FindKthToTail,
};
```