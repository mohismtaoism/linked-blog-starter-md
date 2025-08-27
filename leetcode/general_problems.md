# Minimum Consecutive Cards to Pick Up

You are given an integer array `cards` where `cards[i]` represents the **value** of the `ith` card. A pair of cards are **matching** if the cards have the **same** value.

Return _the **minimum** number of **consecutive** cards you have to pick up to have a pair of **matching** cards among the picked cards._ If it is impossible to have matching cards, return `-1`.

> **Example 1:**

**Input:** cards = [3,4,2,3,4,7]
**Output:** 4
**Explanation:** We can pick up the cards [3,4,2,3] which contain a matching pair of cards with value 3. Note that picking up the cards [4,2,3,4] is also optimal.

> **Example 2:**

**Input:** cards = [1,0,5,3]
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
