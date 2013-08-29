public class Solution {
    public int trap(int[] A) {
        // Start typing your Java solution below
        // DO NOT write main() function
        int iL=A.length;
        
        int[] left=new int[iL], right=new int[iL];
        
        int lMax=0;
        for(int i=0;i<iL;i++)
        {
            left[i]=lMax;
            lMax=Math.max(A[i],lMax);            
        }
        
        lMax=0;
        
        for(int i=iL-1;i>=0;i--)
        {
            right[i]=lMax;
            lMax=Math.max(A[i],lMax);            
        }
        
        int sum=0, height=0;
        
        for(int i=0;i<iL;i++){
            height=Math.min(left[i],right[i])-A[i];
            sum+=height>0?height:0;
        }
        return sum;
    }
}