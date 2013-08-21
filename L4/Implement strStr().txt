public class Solution {
    public String strStr(String haystack, String needle) {
        // Start typing your Java solution below
        // DO NOT write main() function
     if(needle==null) return haystack;
     
     int start=0;
     int index1=0,index2=0;
     
     while(index1<haystack.length() && index2<needle.length()){
         if(haystack.charAt(index1)==needle.charAt(index2)){
         index1++;index2++;
         }else{
         start++;
         index1=start;
         index2=0;
         }
     }
        if(index2==needle.length()&& index1-start==needle.length()){
        return haystack.substring(start);
        }
        return null;
    }
}