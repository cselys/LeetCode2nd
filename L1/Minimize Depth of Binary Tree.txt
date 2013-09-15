/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public int minDepth(TreeNode root) {
        // Start typing your Java solution below
        // DO NOT write main() function
        return getLen(root);
    }
    
    int getLen(TreeNode root){
        if(root==null) return 0;
        
        if(root.left==null && root.right!=null) return 1+ getLen(root.right);
        
        if(root.left!=null && root.right ==null) return 1+ getLen(root.left);
        
        return 1+ Math.min(getLen(root.left),getLen(root.right));
    }
}