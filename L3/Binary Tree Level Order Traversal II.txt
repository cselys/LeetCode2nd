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
    public ArrayList<ArrayList<Integer>> levelOrderBottom(TreeNode root) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
    
        ArrayList<ArrayList<Integer>> levels = new ArrayList<ArrayList<Integer>>();
        if (root == null) return levels;
        
    	int curr = 1;
    	int next = 0;
        
        Queue<TreeNode> q = new LinkedList<TreeNode>();
        ArrayList<Integer> level = new ArrayList<Integer>();
    	q.add(root);
        
        while(!q.isEmpty()){
            TreeNode n=q.poll();
            curr--;
            level.add(n.val);
            if (n.left != null) {
        		q.add(n.left);
    			next++;
    		}
    		if (n.right != null) {
    			q.add(n.right);
    			next++;
    		}
            
            if (curr == 0) {
        		levels.add(level);
    			level = new ArrayList<Integer>();
    			curr = next;
    			next = 0;
    		}
            
        }
        
        ArrayList<ArrayList<Integer>> reverselevels = new ArrayList<ArrayList<Integer>>();
        
        for(int i=levels.size();i>0;i--){
            reverselevels.add(levels.get(i-1));
        }

return reverselevels;
    }
}
