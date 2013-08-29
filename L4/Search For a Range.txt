public class Solution {
    public int[] searchRange(int[] A, int target) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        int[] ret=new int[2];
        ret[0]=search(A,target,0,A.length,true);
        ret[1]=search(A,target,0,A.length,false);
        return ret;        
    }
    
    int search(int[] A, int target, int start, int end, boolean leftmost){
        if(start==end) return -1;
        
        int mid=(start+end)/2;
        
        if(A[mid]>target)
        return search(A,target, start,mid,leftmost);
        else if(A[mid]<target)
        return search(A,target, mid+1,end,leftmost);
        else{
            if(leftmost){
                if(mid==0 || A[mid]!=A[mid-1]) return mid;
                else return search(A,target, start,mid,leftmost);
            }else{
                if(mid==A.length-1 || A[mid]!=A[mid+1]) return mid;
                else return search(A,target, mid+1,end,leftmost);
                
            }
            
        }
        
    }
}
