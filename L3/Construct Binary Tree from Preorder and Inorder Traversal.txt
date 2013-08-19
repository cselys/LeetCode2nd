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
    HashMap<Integer,Integer> map= new HashMap<Integer,Integer>();; 
    public TreeNode buildTree(int[] preorder, int[] inorder) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        for(int i=0;i<inorder.length;i++)
            map.put(inorder[i],i);
        
        return preO(map,preorder,inorder,0,preorder.length-1,0,inorder.length-1);
    }
     
    
     TreeNode preO(    HashMap<Integer,Integer> ma, int[] preorder, int[] inorder, int pi, int pe, int ii, int ie){
        if(pi>pe || ii>ie ) return null;
    
    TreeNode root=new TreeNode(preorder[pi]);
        
        int index=map.get(preorder[pi]);
       int iLen=index-ii;
        

        root.left=preO(map,preorder,inorder,pi+1,pi+index-ii,ii,index-1);
        root.right=preO(map,preorder,inorder,pi+index-ii+1,pe,index+1,ie);
     
     return root;
    }
}