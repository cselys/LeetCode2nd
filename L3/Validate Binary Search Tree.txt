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
    public boolean isValidBST(TreeNode root) {
        // Start typing your Java solution below
        
        return isBST(root, Integer.MIN_VALUE, Integer.MAX_VALUE);        
    }

boolean isBST(TreeNode root, int min, int max){
        if(root==null) return true;
        //if(root.left==null && root.right==null) return true;
        if(root.left!=null && (root.left.val>=root.val||root.left.val<=min)) return false;
        if(root.right!=null &&( root.right.val<=root.val||root.right.val>=max)) return false;
        return isBST(root.left,min, root.val)&&isBST(root.right,root.val,max);

}

}