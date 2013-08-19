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
    public ListNode rotateRight(ListNode head, int n) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(head==null || n==0) return head;
        
        ListNode p=head, q=head;
        while(n--!=0){
            q=q.next;
            if(q==null)q=head;
        }
        if(q==head) return head;
        
        while(q.next!=null){
            p=p.next;
            q=q.next;
            
        }
        
        ListNode temp=p.next;
        q.next=head;
        p.next=null;
        
        return temp;
    }
}