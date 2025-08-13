# Leetcode-169.-Majority-Element
# **Description**
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.
# Solution
In the given problem , we have been given an array nums of length n . And we have to find the majority element which has frequecy greater than n/2 times .

This problem can be done by using a hashmap which instantly stores the key value pairs of number and the corresponding frequency of the number.

Example:

Input: nums = [2,2,1,1,1,2,2]

Output: 2

If a number which has frequency greater than n/2 ( 7/2) == 3.5 . Then we can return  that number , which in this case is 2 becuase 2 has a frequency of 4 and 1 has a frequency of 3.


# Algorithm
1. Initialize an empty hash map freq to store the count of each element.
2. Count frequencies for each number num in the input array nums, Increment freq[num] by 1.
3. Find majority element for each (key, value) pair in freq,
4. If value > n/2 (where n is the size of nums), Return key as the majority element.
5. If no element meets the condition, return -1.
# Code
class Solution {

public:

    int majorityElement(vector<int>& nums) {
        unordered_map<int,int>freq;
        for(int num:nums){
            freq[num]++;
        }
        for(auto& pair:freq){
            if(pair.second>nums.size()/2){
                return pair.first;
            }
        }
        return -1;
    }
    };
# Complexity
Time Complexity:

Counting frequencies with the for loop → O(n)

Iterating over the hash map to find the majority element → O(n) in the worst case (when all elements are distinct).

Total = O(n) + O(n) = O(n)

Space Complexity:

The unordered_map stores at most n key-value pairs → O(n) 
