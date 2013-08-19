public class Solution {
    public int maxSubArray(int[] A) {
        // Start typing your Java solution below
        // DO NOT write main() function
        int max=Integer.MIN_VALUE;
        int sum=0;
        for(int i=0; i<A.length;i++){
            sum=sum>0?sum+A[i]:A[i];
            max=Math.max(max,sum);            
        }
        return max;
    }
}