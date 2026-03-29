/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = nullptr;   // previous node
        ListNode* curr = head;      // current node
        
        while (curr != nullptr) {
            ListNode* nextNode = curr->next; // store next node
            curr->next = prev;               // reverse pointer
            prev = curr;                     // move prev forward
            curr = nextNode;                 // move curr forward
        }
        
        return prev;
        
    }
};