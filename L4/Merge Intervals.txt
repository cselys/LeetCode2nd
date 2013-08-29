/**
 * Definition for an interval.
 * public class Interval {
 *     int start;
 *     int end;
 *     Interval() { start = 0; end = 0; }
 *     Interval(int s, int e) { start = s; end = e; }
 * }
 */
public class Solution {
    public ArrayList<Interval> merge(ArrayList<Interval> intervals) {
        // Start typing your Java solution below
        // DO NOT write main() function
        Collections.sort(intervals, new Comparator<Interval>(){
        public int compare(Interval a, Interval b) {
        return a.start>b.start?1:(a.start==b.start?0:-1);}
        });
        
        ArrayList<Interval> res=new ArrayList<Interval>();
        
        int i=0;
        while(i<intervals.size()){
          int j=i+1;
          int end = intervals.get(i).end;
          while(j<intervals.size() && intervals.get(j).start<=end){
            end=Math.max(end,intervals.get(j).end);
            j++;          
          }
          res.add(new Interval(intervals.get(i).start,end));
        i=j;
        }
        
        return res;
    }
}
