---
title: "[알고리즘-LeetCode] Two Sum"
excerpt: "알고리즘 문제풀이 c++"
classes: wide
toc: true
toc_sticky: true

categories:
 - Algorithm
tags:
 - C++
 - LeetCode
 - Easy
---


```cpp
#include <iostream>
#include <vector>
#include <unordered_map>


using namespace std;

namespace aa {
    int a;
}

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {

        for(int i=0; i< nums.size(); i++){
            cout << nums.at(i) << endl;
        }
        return {};
    }
};

int main() {
    Solution s;
    vector<int> nums;
    nums.push_back(1);
    nums.push_back(2);
    nums.push_back(3);
    s.twoSum(nums, 3);
}
```