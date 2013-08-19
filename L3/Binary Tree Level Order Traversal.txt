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
    public ArrayList<ArrayList<Integer>> levelOrder(TreeNode root) {
        // Start typing your Java solution below
        // DO NOT write main() function
         
        ArrayList<ArrayList<Integer>> results = new ArrayList<ArrayList<Integer>> ();
         if(root==null) return results;
      ArrayList<TreeNode> siblings = new ArrayList<TreeNode> ();
      
      if ( root != null)
          siblings.add(root);
          
      while(!siblings.isEmpty()){
              ArrayList<Integer> tmp = new ArrayList<Integer> ();
           int length = siblings.size();
           for(int i=0;i<length;i++){
               
               tmp.add(siblings.get(i).val);
               
               if(siblings.get(i).left != null)
                siblings.add(siblings.get(i).left);
                
                if(siblings.get(i).right != null)
                siblings.add(siblings.get(i).right);
                
           }
           for(int j=0;j<length;j++)
           siblings.remove(0);
           results.add(tmp);
      }
          
    return results;
    }
}