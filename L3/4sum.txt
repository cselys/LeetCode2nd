public class Solution {
    public ArrayList<ArrayList<Integer>> fourSum(int[] num, int target) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        ArrayList<ArrayList<Integer>>  ret=new ArrayList<ArrayList<Integer>> ();
        
        Arrays.sort(num);
        if(num.length<4) return ret;
        for(int i=0;i< num.length-3;i++){
          for(int t=i+1;t< num.length-2;t++){
              if(i!=0&&num[i-1]==num[i] || t!=i+1 &&num[t]==num[t-1]) continue;
              int j=t+1, k=num.length-1;
              while(j<k){
                  int diff=target-num[i]-num[t]-num[j]-num[k];
                  if(diff<0) k--;
                  else if(diff>0) j++;
                  else{
                      ArrayList<Integer> temp=new ArrayList<Integer>();
                      temp.add(num[i]);temp.add(num[t]);temp.add(num[j]);temp.add(num[k]);
                      ret.add(temp);
                      while(num[++j]==num[j-1] &&j<k);
                      while(num[--k]==num[k+1] &&j<k);
                  }
              }
            
            
        }  
            
        }
        return ret;
    }
}