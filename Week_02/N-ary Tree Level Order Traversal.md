# N叉数的层数遍历

```python
class Solution:
    def levelOrder(self, root: 'Node') -> List[List[int]]:
			ans=[]
			if not root :return ans

			queue=[[root]]
			while queue:
				nodes = queue.pop(0)
				if not nodes :
					break

				ans.append([node.val for node in nodes])
				queue.append([child for node in nodes for child in node.children])

			return ans

```

