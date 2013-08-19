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
    HashMap<Integer, Integer> map=new HashMap<Integer, Integer> ();
    public TreeNode buildTree(int[] inorder, int[] postorder) {
        // Start typing your Java solution below
        // DO NOT write main() function
        for(int i=0;i<inorder.length;i++){
            map.put(inorder[i],i);
        }
        
        return buildTree(inorder, postorder, 0,inorder.length-1,0,postorder.length-1);
        
    }
    
    public TreeNode buildTree(int[] inorder, int[] postorder,int is, int ie, int ps,int pe) {
        if(is>ie || ps>pe) return null;
        int index=map.get(postorder[pe]);
        TreeNode root=new TreeNode(postorder[pe]);
       root.left=buildTree(inorder, postorder,is, index-1, ps,ps+index-is-1);
        root.right=buildTree(inorder, postorder,index+1,ie,pe+index-ie,pe-1);
        return root;
    }
}