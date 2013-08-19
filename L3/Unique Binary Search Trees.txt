public class Solution {
    public int numTrees(int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(n==0 || n==1) return 1;
        
        int sum=0;
        
         int[] f = new int[n+1];
        f[0] = 1;
        f[1] = 1;
        
        for(int i=2;i<n+1;i++){
            for(int j=1;j<=i;j++){
                f[i]+=f[i-j]*f[j-1];
            }
        }
        return f[n];
    }
}