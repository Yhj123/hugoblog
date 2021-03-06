---
title: "动态规划"
date: 2020-12-25T15:35:05+08:00
draft: false
---
### 周五笔记:
* 常见动态规划类型
    * 坐标型动态规划
    * 序列型动态规划
    * 划分型动态规划
    * 区间型动态规划
    * 背包型动态规划
    * 最长序列型动态规划
    * 博弈型动态规划
    * 综合性动态规划
* 动态规划题型:  
    * 计数    
      * 有多少种方式走到右下角
      * 有多少种方法选出k个数使得和为sum
    * 求最大最小值  
      * 从左上角走到右下角路径的最大数字和
      * 最长上升子序列长度
    * 求存在性  
      * 取石子游戏,先手是否必胜
      * 能不能选出k个数使得和是sum
* 动态规划思路:  
    * 确定状态(两个意识):  
      * 最后一步
      * 子问题
    * 转移方程
    * 初始条件和边界情况
    * 计算顺序 
* 动态规划例题:
    * coin change
    * Unique Paths
    * Jump Game
    * Maximum Product Subarray
* Maximum Product Subarray
```
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        vector <int> maxF(nums), minF(nums);
        for (int i = 1; i < nums.size(); ++i) {
            maxF[i] = max(maxF[i - 1] * nums[i], max(nums[i], minF[i - 1] * nums[i]));
            minF[i] = min(minF[i - 1] * nums[i], min(nums[i], maxF[i - 1] * nums[i]));
        }
        return *max_element(maxF.begin(), maxF.end());
    }
};

```




