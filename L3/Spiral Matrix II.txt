public class Solution {
    public int[][] generateMatrix(int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        int[][] ret=new int[n][n];
        int start=0,end=n-1;
        int num=1;
        while(start<end){
        for(int j=start;j<end;j++){
            ret[start][j]=num;
            num++;
        }
        
        for(int i=start;i<end;i++){
            ret[i][end]=num;
            num++;
        }
        
        for(int j=end;j>start;j--){
            ret[end][j]=num;
            num++;
        }
        
        for(int i=end;i>start;i--){
            ret[i][start]=num;
            num++;
        }
        
        start++;
        end--;
        }
        
        if(start==end) ret[start][start]=num;
        return ret;
    }
}