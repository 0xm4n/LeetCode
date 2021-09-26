```cpp
// quickSort
class Solution {
public:
    vector<int> sortArray(vector<int>& nums) {
        quickSort(nums, 0, nums.size() - 1);
        return nums;
    }
    
    void quickSort (vector<int>& nums, int lo, int hi) {
        if (lo >= hi) return;
        int pivot = nums[lo], i = lo + 1, j = hi;
        while (i <= j) {
            if (nums[i] > pivot && nums[j] < pivot) {
                std::swap(nums[i++], nums[j--]);
            }
            if (nums[i] <= pivot) ++i;
            if (nums[j] >= pivot) --j;
        }
        std::swap(nums[lo], nums[j]);
        quickSort(nums, lo, j - 1);
        quickSort(nums, j + 1, hi);
    }
};
```

