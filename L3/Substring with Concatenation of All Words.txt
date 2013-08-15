public class Solution {
    public ArrayList<Integer> findSubstring(String S, String[] L) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        ArrayList<Integer> res= new ArrayList<Integer>();

        if(S==null || L==null || L.length==0 ) return res;
        
        HashMap<String,Integer> map = new HashMap<String,Integer>();
        
        for(int i=0;i<L.length;i++) {
            if(map.containsKey(L[i]) )
                map.put(L[i],map.get(L[i])+1);
            else
                map.put(L[i],1);
        }
        
        int sz=S.length();
        int m=L[0].length();
        int n=L.length;
        
        for(int i=0;i<sz-n*m+1;i++){
            HashMap<String,Integer> temp= new HashMap<String,Integer>( map);
            for(int j=i;j<i+n*m;j+=m){
                String t=S.substring(j,j+m);
                if(temp.containsKey(t)){
                    int x=temp.get(t);
                    if(x==1) temp.remove(t);
                    else temp.put(t,x-1);
                }else{break;}
            }
            if(temp.isEmpty()) res.add(i);
        }
    return res;
        
    }
}