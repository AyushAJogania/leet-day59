# leet-day59

# Group the People Given the Group Size They Belong To

## Problem Description

You are given an integer array `groupSizes`, where `groupSizes[i]` is the size of the group that person `i` is in. The goal is to group people based on their group sizes and return a list of groups such that each person `i` is in a group of size `groupSizes[i]`. Each person should appear in exactly one group, and every person must be in a group. If there are multiple valid solutions, return any of them. It is guaranteed that there will be at least one valid solution for the given input.

## Example

**Input:**

```
groupSizes = [3,3,3,3,3,1,3]
```

**Output:**

```
[[5],[0,1,2],[3,4,6]]
```

**Explanation:**

- The first group is `[5]`. The size is 1, and `groupSizes[5] = 1`.
- The second group is `[0,1,2]`. The size is 3, and `groupSizes[0] = groupSizes[1] = groupSizes[2] = 3`.
- The third group is `[3,4,6]`. The size is 3, and `groupSizes[3] = groupSizes[4] = groupSizes[6] = 3`.
- Other possible solutions are `[[2,1,6],[5],[0,4,3]]` and `[[5],[0,6,2],[4,3,1]]`.

## Approach

We can solve this problem using a greedy approach. The idea is to iterate through the `groupSizes` array, keep track of the people based on their group sizes, and form groups when a group reaches its specified size. Here are the steps of the approach:

1. Initialize an empty vector `result` to store the final groups.

2. Create an unordered map `groups` where the key is the group size, and the value is a vector of person IDs in that group.

3. Iterate through the `groupSizes` array, and assign each person to their respective group based on their group size.

4. Check if the current group size has reached its maximum size. If it has, add the group to the `result` vector and clear the group in the `groups` map.

5. Finally, iterate through the remaining groups in the `groups` map and add them to the `result` vector.

6. Return the `result` vector, which contains the desired groupings.

## Complexity Analysis

The time complexity of this solution is O(n), where n is the number of people. We iterate through the `groupSizes` array once to form the groups.

The space complexity is O(n) as well, considering the space used for the `result` vector and the `groups` map.

## How to Use

You can use the provided C++ code to group people based on their group sizes. Simply input the `groupSizes` array and call the `groupThePeople` function. The function will return the list of groups as described in the problem statement.

Feel free to test the code with different inputs to explore various groupings.

```cpp
Solution solution;
vector<int> groupSizes = {3,3,3,3,3,1,3};
vector<vector<int>> result = solution.groupThePeople(groupSizes);
```
