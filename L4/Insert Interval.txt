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
    public ArrayList<Interval> insert(ArrayList<Interval> intervals, Interval newInterval) {
        // Start typing your Java solution below
        // DO NOT write main() function
        Interval temp=newInterval;
        ArrayList<Interval> ret=new ArrayList<Interval>();
        
        for(Interval i:intervals){
        if(i.end<temp.start)
        ret.add(i);
        else if(temp.end<i.start){
        ret.add(temp);
        temp=i;}
        else{
        temp=new Interval(Math.min(temp.start,i.start),Math.max(temp.end,i.end));
        }               
    }
    ret.add(temp);
    return ret;
}}