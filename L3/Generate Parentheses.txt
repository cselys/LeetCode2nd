public class Solution {
    public ArrayList<String> generateParenthesis(int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        ArrayList<String> ret=new ArrayList<String>();
        if(n>0)  generate(ret, "", 0, 0 , n);
        return ret;
    }
    
void generate(ArrayList<String> ret, String s, int l,int r,int n){
        if(l==n){
            ret.add(fill(s,n-r));
            return;
        }
        generate(ret,s+"(",l+1,r,n);
        if(l>r) generate(ret,s+")",l,r+1,n);
        
    }
    
    String fill(String s,int r){
        StringBuffer st=new StringBuffer(s);
        for(int i=0;i<r;i++){
            st.append(")");
        }
        return st.toString();
    }
}