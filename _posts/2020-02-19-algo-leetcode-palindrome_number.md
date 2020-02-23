---
title: "[알고리즘-LeetCode] Palindrome Number"
excerpt: "알고리즘 문제풀이 c++"
classes: wide
toc: true
toc_sticky: true

categories:
 - Algorithm
tags:
 - c++
 - LeetCode
 - Easy
---

```cpp
#include <iostream>
#include <sstream>
#include <vector>
#include <limits.h>  

using namespace std;

class Solution {
public:
    bool isPalindrome(int x){
        if(x==0) {return true;}
        int reverse=0;
        if(x<0 || x%10==0) return false;
        while(x>reverse){
            reverse = reverse*10 + x%10;
            x = x/10;
        }
        return x==reverse || x==reverse/10;
    }

    bool isPalindrome1(int x){
        if(x<0) return false;
        string str = "";
        stringstream sstr;
        sstr << x;
        str = sstr.str();
        vector<char> v(str.begin(), str.end());
        int vSize = v.size();
        int halfSize = (vSize/2)+1;
        for(int i=0; i<halfSize; i++){
            if(v[i] != v[vSize-i-1]) return false;
        }
        return true;
    }
};

int main(){
    Solution s;
    int num;
    // cin >> num;
    num = 100;
    bool ret = s.isPalindrome(num);
    cout << ret << endl;

    return 0;
}
```