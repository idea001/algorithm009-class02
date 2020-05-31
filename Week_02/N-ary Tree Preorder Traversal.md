# N叉数的前序遍历

```python
class Solution:
    def preorder(self, root: 'Node') -> List[int]:
        s = bool(root) * [root]
        r = []
        
        while s:
            root = s.pop()
            r.append(root.val)
            s += root.children[::-1] or []
        
        return r
```

