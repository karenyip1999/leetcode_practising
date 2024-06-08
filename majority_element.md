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
