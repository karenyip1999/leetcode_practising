## Task ✍
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. 

You may assume that the majority element always exists in the array.

#### Example 1:
Input: ```nums = [3,2,3]```

Output: ```3```

#### Example 2:
Input: ```nums = [2,2,1,1,1,2,2]```

Output: ```2```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts about resolving this problem was to define in code the majority element, which could be found as the element which appeared one more than the length of the array halved. 

I also thought that it would be easier to check for frequency of an occurrence of an element by sorting the array as I could check for the same elements which would be next to each other.

I also thought about when iterating through the array, counting the occurrences of each element, I would need to keep track of the element that has the highest occurence so I would need to create a variable.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I began by creating a variable that defined majority, which for this question was more than half the size of the array
2. I created a variable called counter that kept count of the occurrence of an element
3. I created another variable called val which was initialised at 0 that held the value that was being kept count of in the counter variable
4. I then sorted the array to make it easier to keep count of the frequency of occurrences of each element
5. I created an if statement to check for arrays shorter than the length of 2 so that I could set val to the 0th element and then return this straight away as the array only held 1 element
6. I then created a for loop that started at index 1
7. Inside of the for loop was an if statement that checked if the current element was the same as the previous element
8. If the element before it was the same then the val was set to the current element and the counter was incremented
9. Another if statement checked if the previous element was not the same as the current element
10. If the element before it was not the same then the val was changed to the current element and the counter was reset back to 1
11. If the counter ended up being the same as the value of majority then val was returned
12. Finally, val is returned if it had not been returned before

## Code 📝
My solution to the task.
```java
class Solution {
    public int majorityElement(int[] nums) {
        int majority = nums.length/2 + 1;
        int counter = 1;
        int val = 0;
        Arrays.sort(nums);
        if(nums.length < 2){
            val = nums[0];
            return val;
        }
        
        for(int i = 1; i < nums.length; i++){
            if(nums[i] == nums[i - 1]){
                val = nums[i];
                counter++;
            }
            if(nums[i] != nums[i - 1]){
                val = nums[i];
                counter = 1;
            }
            if(counter == majority){
                return val;
            }
        }
        return val;
    }
}
```

In hindsight, as the majority is defined in this task as an element that appears more than half the size of the array, I could have sorted the array and then returned the element at the position of ```nums[nums.length/2]```
```java
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length/2];
    }
}
```
