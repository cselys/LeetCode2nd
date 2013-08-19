public class Solution {
    public ArrayList<ArrayList<Integer>> combine(int n, int k) {
        // Start typing your Java solution below
        // DO NOT write main() function
       ArrayList<ArrayList<Integer>> rel = new ArrayList<ArrayList<Integer>>();    
       ArrayList<Integer> temp = new ArrayList<Integer>();    
       comb(rel,temp,n,k,0);
        return rel;
    }
    
    void comb( ArrayList<ArrayList<Integer>> rel,  ArrayList<Integer> temp, int n, int k, int s)
    {
        if(temp.size()==k){
            rel.add(new ArrayList<Integer>(temp));
            return;
        }
     
        for(int i=s; i<n; i++) {  
            temp.add(i+1);
            comb(rel,temp,n,k,i+1);
            temp.remove(temp.size()-1);
        }
        
    }
}