public class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(matrix==null || matrix.length==0) return false;
        int start=0;
        int end=matrix.length*matrix[0].length-1;
        
        while(start<=end){
            int mid=(start+end)/2, midx=mid/matrix[0].length, midy=mid%matrix[0].length;
            if(matrix[midx][midy]==target) return true;
            else if(matrix[midx][midy]>target) end=mid-1;
            else start=mid+1;
            
            
        }
        return false;
    }
}