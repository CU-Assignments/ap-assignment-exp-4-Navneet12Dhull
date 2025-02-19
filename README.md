PROBLEM 1

https://leetcode.com/problems/longest-nice-substring/description/
class Solution {
public:
    string longestNiceSubstring(string s) {
        if (s.length() < 2) return "";
        
        for (int i = 0; i < s.length(); i++) {
            if (s.find(tolower(s[i])) == string::npos || s.find(toupper(s[i])) == string::npos) {
                string left = longestNiceSubstring(s.substr(0, i));
                string right = longestNiceSubstring(s.substr(i + 1));
                return left.length() > right.length() ? left : right;
            }
        }
        return s;
    }
};


PROBLEM 2
https://leetcode.com/problems/maximum-subarray/description/\

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int max_sum = nums[0];
        int current_sum = nums[0];

        for (int i = 1; i < nums.size(); i++) {
            current_sum = max(nums[i], current_sum + nums[i]);
            max_sum = max(max_sum, current_sum);
        }

        return max_sum;
    }
};

