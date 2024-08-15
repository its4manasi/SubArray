# SubArray
1. Maximum Subarray Sum (Kadane's Algorithm)

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

3. Sum of SubArray Minimum

  using System;

  public int SumOfSubArrayMin(int[] arr)
  {
  }
