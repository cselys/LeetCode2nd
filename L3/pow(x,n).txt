public class Solution {
    public double pow(double x, int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(n==0) return 1;
        if(n<0){
            n=-n;
            x=1/x;
        }
        
        double temp=pow(x, n/2);
        if(n%2==0) return temp*temp;
        else return temp*temp*x;
    }
}
