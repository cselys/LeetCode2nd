public class Solution {
    public ArrayList<String> restoreIpAddresses(String s) {
        // Start typing your Java solution below
        // DO NOT write main() function
       
        ArrayList<String> ret=new ArrayList<String> ();
         if(s==null || s.length()<4||s.length()>12) return ret;
        
        
        dfs(ret,"",s,0);
        return ret;
        
    }
    
    void dfs(ArrayList<String> ret, String tmp,String sub, int count){
        if(count==3 && isValid(sub)){
            ret.add(tmp+sub);     
            return;
        }
        for(int i=1;i<4 && i<sub.length();i++){
            String substr=sub.substring(0,i);
            if(isValid(substr))
            dfs(ret, tmp+substr+'.',sub.substring(i),count+1);
            
        }
    }
    
    boolean isValid(String s){
        if(s.charAt(0)=='0') return s.equals("0");
         
        int num=Integer.parseInt(s);
        return num<=255 && num>0;
    }
}

