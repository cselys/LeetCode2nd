public class Solution {
    public String simplifyPath(String path) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        if(path==null || path.length()==0) return "/";
        
        Stack<String> stk=new Stack<String>();
        
        String[] splits=path.trim().split("/");
        
        for(String s:splits){
            if(s==null || s.length()==0 || s.equals(".")){
                
            }else if(s.equals("..")){
                if(stk.size()>0)stk.pop();                
            }else 
                stk.push(s);
                
        }
        
        if(stk.isEmpty()) return "/";
        
        StringBuffer strbuf=new StringBuffer();
        while(!stk.isEmpty()){
            strbuf.insert(0,stk.pop());
            strbuf.insert(0,"/");
            
        }
        
        return strbuf.toString();
    }
}