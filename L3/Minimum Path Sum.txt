public class Solution {
    public int minPathSum(int[][] grid) {
        // Start typing your Java solution below
        // DO NOT write main() function
        int[][] ret=new int[grid.length][grid[0].length];
       
        ret[0][0]=grid[0][0];
       
        for(int i=1;i<grid.length;i++)
        ret[i][0]=ret[i-1][0]+grid[i][0];
       
        for(int i=1;i<grid[0].length;i++)
        ret[0][i]=ret[0][i-1]+grid[0][i];
       
        for(int i=1;i<grid.length;i++)
        {
            for(int j=1;j<grid[0].length;j++)
        {
            ret[i][j]=Math.min(ret[i-1][j],ret[i][j-1])+grid[i][j];
       
       
        }
        }
        return ret[grid.length-1][grid[0].length-1];
    }
}