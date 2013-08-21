public class Solution {
    public int maxProfit(int[] prices) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(prices.length==0||prices.length==1) return 0;
        
        int ret=0;
        
        for(int i=0;i<prices.length-1;i++){
            if(prices[i+1]>prices[i])
            ret+=prices[i+1]-prices[i];
        }
        return ret;
    }
}