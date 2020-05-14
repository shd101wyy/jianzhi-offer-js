---
note:
    createdAt: 2020-05-14T12:43:00.638Z
    modifiedAt: 2020-05-14T14:26:58.375Z
    tags: [考点/树, 难度/4]
    id: ""
---
# 二叉搜索树的第k个结点
#考点/树 #难度/4  [牛客网](https://www.nowcoder.com/practice/ef068f602dde4d28aab2b210e859150a?tpId=13&tqId=11215&tPage=3&rp=3&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
<!-- @crossnote.comment "id":"9d39e378-6bb2-41b0-96ba-4989a34199ca" -->  
## 题目描述
给定一棵二叉搜索树，请找出其中的第 k 小的结点。例如， （5，3，7，2，4，6，8）中，按结点数值大小顺序第三小结点的值为4。

## 答案

```javascript
/* function TreeNode(x) {
    this.val = x;
    this.left = null;
    this.right = null;
} */
function KthNode(pRoot, k) {
  if (k <= 0 || pRoot == null) {
    return null;
  }
  var aid = [];
  function mInorder(pRoot, k) {
    // while(aid.length-1 < k){
    if (pRoot.left != null) {
      mInorder(pRoot.left, k);
    }
    aid.push(pRoot);
    if (pRoot.right != null) {
      mInorder(pRoot.right, k);
    }
    // }
  }
  mInorder(pRoot, k);
  return aid[k - 1];
  // write code here
}
module.exports = {
  KthNode: KthNode,
};
```