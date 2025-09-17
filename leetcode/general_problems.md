# Minimum Consecutive Cards to Pick Up

## Desciption

You are given an integer array `cards` where `cards[i]` represents the **value** of the `ith` card. A pair of cards are **matching** if the cards have the **same** value.

Return _the **minimum** number of **consecutive** cards you have to pick up to have a pair of **matching** cards among the picked cards._ If it is impossible to have matching cards, return `-1`.

 **Example 1:**

> **Input:** cards = [3,4,2,3,4,7]
   **Output:** 4
  **Explanation:** We can pick up the cards [3,4,2,3] which contain a matching pair of cards with value 3. Note that picking up the cards [4,2,3,4] is also optimal.

 **Example 2:**

> **Input:** cards = [1,0,5,3]
   **Output:** -1
   **Explanation:** There is no way to pick up a set of consecutive cards that contain a pair of matching cards.

## Solution 1 (Slow version)

```c
class Solution {
public:
    int minimumCardPickup(vector<int>& cards) {
        int i;
        int j;
        int minimum = 100000;
        bool inner_loop_continue = true;
        for (i = 0; i < cards.size(); i++) {
            int start = cards[i];
            int local_width = 1;
            inner_loop_continue = true;
            for (j = i + 1; j < cards.size() && inner_loop_continue; j++) {
                if (cards[j] == start) {
                    local_width++;
                    inner_loop_continue = false;
                } else {
                    local_width++;
                }
            }

            if (local_width < minimum && inner_loop_continue == false)
                minimum = local_width;
        }

        if (minimum == 100000)
            return -1;
        else
            return minimum;
    }
};  

```

# 167. Two Sum ll - Input Array Is Sorted

## description

Given a **1-indexed** array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be `numbers[index1]` and `numbers[index2]` where `1 <= index1 < index2 <= numbers.length`.

Return _the indices of the two numbers,_ `index1` _and_ `index2`_, **added by one** as an integer array_ `[index1, index2]` _of length 2._

The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.

Your solution must use only constant extra space.

 **Example 1:**

> **Input:** numbers = [2,7,11,15], target = 9
   **Output:** [1,2]
   **Explanation:** The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].

**Example 2:**

> **Input:** numbers = [2,3,4], target = 6
   **Output:** [1,3]
   **Explanation:** The sum of 2 and 4 is 6. Therefore index1 = 1, index2 = 3. We return [1, 3].

**Example 3:**

> **Input:** numbers = [-1,0], target = -1
   **Output:** [1,2]
   **Explanation:** The sum of -1 and 0 is -1. Therefore index1 = 1, index2 = 2. We return [1, 2].


**Constraints:**

- `2 <= numbers.length <= 3 * 104`
- `-1000 <= numbers[i] <= 1000`
- `numbers` is sorted in **non-decreasing order**.
- `-1000 <= target <= 1000`
- The tests are generated such that there is **exactly one solution**.


## Solution

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int start = 0;
        int end = numbers.size() - 1;
        vector<int> result;

        while (start < end) {
            if (numbers[start] + numbers[end] > target) {
                end--;
            } else if (numbers[start] + numbers[end] < target) {
                start++;
            } else {
                result.push_back(start + 1);
                result.push_back(end + 1);
                break;
            }
        }
        return result;
    }
};
```

简单思路：所谓双指针法，就是最初，将双指针指在数组首末，然后通过一些条件判断，左右指针的移动，要么左指针右移，要么右指针左移。