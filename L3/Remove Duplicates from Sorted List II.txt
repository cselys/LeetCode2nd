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
    public ListNode deleteDuplicates(ListNode head) {
        // Start typing your Java solution below
        // DO NOT write main() function
      if(head==null || head.next==null) return head;
         
        ListNode prev = new ListNode(0);
        prev.next = head;
        head = prev;
        
        
        
        ListNode pre=head;

        while(pre.next!=null){
            ListNode cur=pre.next;
          
            while(cur.next!=null && cur.val==cur.next.val) 
                cur=cur.next;
                
                 if(cur!=pre.next){
                    pre.next=cur.next;
                }else{
                    pre=pre.next;   
                }            
            
        }
        
        return head.next;
        
    }
}