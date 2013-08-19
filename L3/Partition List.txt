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
    public ListNode partition(ListNode head, int x) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(head==null || head.next==null) return head;
        ListNode dum1=new ListNode(0);
        ListNode dum2=new ListNode(0);
        ListNode ret=dum1;
        ListNode ret2=dum2;
        
        while(head!=null){
            if(head.val<x) {
                dum1.next=head;
                dum1=dum1.next;
            }else{
                dum2.next=head;
                dum2=dum2.next;
            }
            head=head.next;
        }
        
        dum2.next=null;
        dum1.next=ret2.next;
        return ret.next;
        
    }
}