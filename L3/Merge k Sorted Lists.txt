/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode mergeKLists(ArrayList<ListNode> lists) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(lists.size()==0) return null;
        
        PriorityQueue<ListNode> q = 
        new PriorityQueue<ListNode>
        (lists.size(),new Comparator<ListNode>()
        {public int compare(ListNode a, ListNode b)
        {return a.val>b.val?1:(a.val==b.val?0:-1);}});
        
for(ListNode n:lists){
if(n!=null) q.add(n);
}      

ListNode head=new ListNode(0), prev=head;

while(q.size()!=0){
    ListNode temp=q.poll();
    prev.next=temp;
    if(temp.next!=null) q.add(temp.next);
    prev=prev.next;
}

return head.next;
    }
}