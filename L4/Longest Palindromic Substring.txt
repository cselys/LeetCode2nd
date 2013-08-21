public class Solution {
    public String longestPalindrome(String s) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        int iLen=s.length();
        int start=0, imax=1;
        
        boolean[][] map=new boolean[1000][1000];
        
        for(int i=0;i<iLen;i++)
        map[i][i]=true;
        
        for(int i=0;i<iLen-1;i++){
            if(s.charAt(i)==s.charAt(i+1)) {map[i][i+1]=true;
            imax=2;
            start=i;
            }
        }
        
        for(int len=3;len<=iLen;len++){
            for(int i=0;i<iLen-len+1;i++){
                int j=i+len-1;
                if(s.charAt(i)==s.charAt(j) && map[i+1][j-1]){
                    map[i][j]=true;
                    imax=len;
                    start=i;
                    
                }
            }
        
        }
        return s.substring(start,start+imax);
    }
}