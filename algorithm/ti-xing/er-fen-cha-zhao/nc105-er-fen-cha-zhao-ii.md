# NC105 二分查找-II

![](../../../.gitbook/assets/tu-pian-%20%2847%29.png)

My code\(23%\):

```text
import java.util.*;


public class Solution {
    /**
     * 代码中的类名、方法名、参数名已经指定，请勿修改，直接返回方法规定的值即可
     *
     * 如果目标值存在返回下标，否则返回 -1
     * @param nums int整型一维数组 
     * @param target int整型 
     * @return int整型
     */
    public int search (int[] nums, int target) {
        // write code here
        if(nums.length == 0)
            return -1;
        return erfen(0,nums.length,nums,target);
    }
    
    private int erfen(int l,int r, int[] nums, int target){
        if(l > r) return -1;
        int mid = (l+r)/2;
        if(nums[mid] == target){
            int first = erfen(l,mid-1,nums,target);
            if(first == -1)
                return mid;
            else return first;
        }
        else if(nums[mid] < target) return erfen(mid+1,r,nums,target);
        else return erfen(l,mid-1,nums,target);
    }
}
```

 

From comment:

```text
public int search (int[] nums, int target) {
        // write code here
        int index = -1;
        int low = 0, high = nums.length-1;
        while (low <= high) {
            int mid = low + (high-low) / 2;
            if (nums[mid] == target) {
                // 在low 到 mid之间找第一个下标
                index = mid;
                high = mid-1;
            } else if (target > nums[mid]) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return index;
    }
```

