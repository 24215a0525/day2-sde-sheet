# Sort Colors (0s, 1s, 2s)

## Problem

Sort an array containing only:

0s, 1s, and 2s

without using extra space.

Example:

Input:

[2,0,2,1,1,0]

Output:

[0,0,1,1,2,2]

---

## Approach

Use 3 pointers:

low → position for 0

mid → current element

high → position for 2

This technique is called:

Dutch National Flag Algorithm

---

## Logic

If arr[mid] == 0

- swap low and mid
- low++
- mid++

If arr[mid] == 1

- mid++

If arr[mid] == 2

- swap mid and high
- high--

Do NOT increase mid here because swapped element needs checking.

---

## Code

```java
class Solution {
    public void sortColors(int[] nums) {

        int low = 0;
        int mid = 0;
        int high = nums.length - 1;

        while(mid <= high)
        {
            if(nums[mid] == 0)
            {
                int temp = nums[mid];
                nums[mid] = nums[low];
                nums[low] = temp;

                low++;
                mid++;
            }

            else if(nums[mid] == 1)
            {
                mid++;
            }

            else
            {
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high] = temp;

                high--;
            }
        }
    }
}
```

## Complexity

Time Complexity:

O(n)

Space Complexity:

O(1)

## Key Intuition

Left side → only 0s

Middle → processing area

Right side → only 2s

Move elements to correct regions using pointers.
