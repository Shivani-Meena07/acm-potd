/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (!head || !head->next)
        return false;  // empty list or single node

        ListNode* slow = head;
        ListNode* fast = head;

        while (fast && fast->next) {
            slow = slow->next;          // move one step
            fast = fast->next->next;    // move two steps

            if (slow == fast) {
                return true;            // cycle detected
            }
        }
        return false;  // no cycle  
    }
};