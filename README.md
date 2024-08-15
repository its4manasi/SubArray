# SubArray
1. Maximum Subarray Sum (Kadane's Algorithm)

Problem: Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
Example:
text
Copy code
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: The subarray [4,-1,2,1] has the largest sum = 6.


  using System;
  
  public int MaxSubArraySum(int[] arr)
  {
      int n = arr.Length;
      int maxi = int.MinValue;
      int sum = 0;
      for(int i = 0; i<n; i++)
      {
          sum = sum + arr[i];
          maxi = Math.Max(maxi, sum);
          if(sum < 0){
              sum = 0;          //Remove negative numbers as they appear to prevent them from decreasing the value of the next positive numbers.
          }
      }
      return maxi;
  }


--------------------------------------------------------------------------------------------------------------------------------------------------------------------

2. Minimum SubArray Sum

Problem: Given an integer array nums, find the contiguous subarray which has the smallest sum and return its sum.
Example:
text
Copy code
Input: nums = [3, -4, 2, -3, -1, 7, -5]
Output: -6
Explanation: The subarray [-4, 2, -3, -1] has the smallest sum = -6.


Hint: This is similar to the maximum subarray sum problem but instead of tracking the maximum, you track the minimum.
   
  using System;

  public int MinSubArraySum(int[] arr)
  {
      int n = arr.Length;
      int sum = 0;
      int mini = int.MaxValue;
      for(int i=0; i<n ; i++)
      {
        sum = sum + arr[i];
        mini = Math.Min(mini, sum);
        if(sum > 0)
        {
          sum = 0;
        }
      }
      return mini;
  }
  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

3. Maximum Product Subarray
   
Problem: Given an integer array nums, find the contiguous subarray within an array (containing at least one number) which has the largest product.
Example:
text
Copy code
Input: nums = [2,3,-2,4]
Output: 6
Explanation: The subarray [2,3] has the largest product = 6.

  using System;

  public int SumOfSubArrayMin(int[] arr)
  {
      int n = arr.Length;
      int prefixMax = 0;
      int suffixMax = 0;
      int maxi = int.MinValue;
      for(int i=0; i<n; i++)
      {
        if(arr[i] == 0) prefixMax = 1;
        if(arr[n-1-i] == 0) suffixMax = 1;      
        prefixMax = prefixMax * arr[i];
        suffixMax = suffixMax * arr[n-1-i];
        maxi = Math.Max(maxi, Math.Max(prefixMax, suffixMax));
      }
      return maxi;
  }

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

4. Longest Subarray with Sum K
   
Problem: Given an array arr of integers and an integer k, find the length of the longest subarray that sums to k.
Example:
text
Copy code
Input: arr = [1, -1, 5, -2, 3], k = 3
Output: 4
Explanation: The subarray [1, -1, 5, -2] sums to 3 and is the longest.


