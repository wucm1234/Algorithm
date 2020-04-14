### Traverse vs Divide & Conquer

> * They are both Recursion Algorithm
> * Result in parameter vs Result in return value
> * Top down vs Bottom up

***


#### 代码
```java
	/*
	    分别用traversal和分治法求二叉树的深度
	*/
	//traversal
	class Solution {
	    int max;
	    public int maxDepth(TreeNode root) {
	        max = 0;
	        traversal(root, 0);
	        return max;
	    }
	    
	    public void traversal(TreeNode node, int curr){
	        if(node == null) return;
	        max = Math.max(max, curr+1);
	        traversal(node.left, curr+1);
	        traversal(node.right, curr+1);
	    }
	}
	//divide & conqure
	class Solution {
	    public int maxDepth(TreeNode root) {
	        if(root == null) return 0;
	        int left = maxDepth(root.left);
	        int right = maxDepth(root.right);
	        return Math.max(left, right) + 1;
	    }
	}
```