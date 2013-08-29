public class Solution {
    public ArrayList<String[]> solveNQueens(int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        ArrayList<String[]> ret=new ArrayList<String[]>();
        int[] loc=new int[n];
        dfs(ret,loc, 0, n);
        return ret;               
    }
    
    void dfs(ArrayList<String[]> ret, int[] loc, int row, int n){
        if(row==n) printboard(ret,loc,n);
        else{
            for(int i=0;i<n;i++){
                loc[row]=i;
                if(isValid(loc,row)) 
                dfs(ret,loc, row+1,n);
            }
        }
    }
    
    boolean isValid(int[] loc, int row){
        for(int i=0;i<row;i++){
            if(loc[i]==loc[row] || Math.abs(loc[i]-loc[row])==row-i) return false;
        }
        return true;
    }
    
    void printboard(ArrayList<String[]> ret, int[] loc, int n){
        String[] ans=new String[n];
        for(int i=0;i<n;i++){
            String row=new String();
            for(int j=0;j<n;j++) {
                if(j==loc[i]) row+="Q";
                else row+=".";
            }
            ans[i]=row;
        }
        ret.add(ans);
    }
}