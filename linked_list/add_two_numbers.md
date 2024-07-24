## Task ✍
You are given two non-empty linked lists representing two non-negative integers. 

The digits are stored in reverse order, and each of their nodes contains a single digit. 

Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

#### Example 1:
Input: ```l1 = [2,4,3], l2 = [5,6,4]```

Output: ```[7,0,8]```

Explanation: 342 + 465 = 807.

#### Example 2:
Input: ```l1 = [0], l2 = [0]```

Output: ```[0]```

#### Example 3:
Input: ```l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]```

Output: ```[8,9,9,9,0,0,0,1]```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on solving this problem were to tackle the quirks that come with addition such as carrying 1 when addition makes the single digit turn into a double digit.

I also thought about placement of the integers when carrying out the addition as there is nothing to stop the addition from being between different length integers which would need 0 placed in front of the shorter integer.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a new ListNode called result that would act as the dummy node that is a placeholder at the beginning of the linked list
2. I created a ListNode called current that references to result, that acts as a pointer as we traverse through the linked list
3. I created a variable called carry which accounts for when addition of a single digit creates a double digit, and initiated it to 0
4. I used a while loop that traverses through the linked list whilst l1 is not equal to null or l2 is not equal to null
5. Inside of the while loop, I used a ternary operator that checked if l1 was equal to null, then the variable currentVal1 is set to 0 as this accounts for the correct placement of a shorter integer during addition, else currentVal1 holds the value of the node at l1
6. Another ternary operator checked if l2 was equal to null, then the variable currentVal2 is set to 0 as this also accounts for the correct placement of a shorter integer during addition, else currentVal2 holds the value of the node at l2
7. currentVal1, currentVal2 and carry are added together and are assigned to the variable called sum
8. sum is divided by 10, as an integer that cannot be divided without a remainder will be a double digit, so is assigned to carry
9. A new ListNode is made next to current, and the value of sum modulo 10 is placed in the node 
10. I used an if statement to check if l1 is not null
11. If so, the pointer at l1 moves forward by assigning the next l1 node to the variable l1
12. Another if statement checks if l2 is not null
13. If so, the pointer at l2 also moves forward by assigning the next l2 node to the variable l2
14. The pointer at current is moved forward to the next node and is assigned to current
15. Outside of the while loop, an if statement checks if carry equals 1
16. If so, a new node is created with 1 inside of it as this accounts for a 1 that still needs to be included, and is assigned to current
17. Finally, result.next is returned and ```.next``` is used to account for the dummy node at the beginning of result that is automatically 0

## Code 📝
My solution to the task.
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result = new ListNode();
        ListNode current = result;
        int carry = 0;
        while(l1 != null || l2 != null){
            int currentVal1 = l1 == null ? 0 : l1.val;
            int currentVal2 = l2 == null ? 0 : l2.val;
            int sum = currentVal1 + currentVal2 + carry;
            carry = sum / 10;
            current.next = new ListNode(sum % 10);
            if(l1 != null){
                l1 = l1.next;
            }
            if(l2 != null){
                l2 = l2.next;
            }
            current = current.next;
        }
        if(carry == 1){
            current.next = new ListNode(1);
        }
        return result.next;
    }
}
```
