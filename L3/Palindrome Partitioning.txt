public class Solution {
    public ArrayList<ArrayList<String>> partition(String s) {
        // Start typing your Java solution below
        // DO NOT write main() function
        ArrayList<ArrayList<String>> ret=new ArrayList<ArrayList<String>> ();
        ArrayList<String> tmp=new ArrayList<String>();
        dfs(ret,tmp,s);
        return ret;
    }
    
    void dfs(ArrayList<ArrayList<String>> ret, ArrayList<String> tmp, String s){
     if(s.length()==0)
      ret.add(new ArrayList<String>(tmp));
      for(int i=1;i<=s.length();i++){
        String subs=s.substring(0,i);
        if(isPalindrome(subs)){
            tmp.add(subs);
            dfs(ret,tmp,s.substring(i));
            tmp.remove(tmp.size()-1);
        }
      }
     
    }
    
    boolean isPalindrome(String s){
        if(s==null ||s.length()==1) return true;
        int i=0, j=s.length()-1;
        while(i<j){
    {    if(s.charAt(i++)!=s.charAt(j--)) return false;}       
        
        }
        return true;
        
    }
}