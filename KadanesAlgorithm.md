# Kadane's Algorithm

## Idea
- Keep adding elements
- If running sum becomes negative, reset it
- Track maximum sum seen so far

Why Reset?

Negative running sum reduces future subarray sum.

Example:

Current sum = -5  
Next element = 10  

Keep negative:

-5 + 10 = 5

Start fresh:

10

## Code

```java
int sum = 0;
int max = Integer.MIN_VALUE;

for(int num : arr)
{
   sum += num;

   max = Math.max(max, sum);

   if(sum < 0)
      sum = 0;
}
```

## Complexity

Time Complexity: O(n)

Space Complexity: O(1)

## Key Intuition

Keep positive contribution.

Remove negative contribution.
