```cpp
// quickSort
class Solution {
public:
    vector<int> sortArray(vector<int>& nums) {
        quickSort(nums, 0, nums.size() - 1);
        return nums;
    }
    
    void quickSort(vector<int>& nums, int left, int right) {
        if (left >= right) return;
        int pivot = nums[left], i = left + 1, j = right;
        while (i <= j) {
            if (nums[i] > pivot && nums[j] < pivot) {
                std::swap(nums[i++], nums[j--]);
            }
            if (nums[i] <= pivot) ++i;
            if (nums[j] >= pivot) --j;
        }
        std::swap(nums[left], nums[j]);
        quickSort(nums, left, j - 1);
        quickSort(nums, j + 1, right);
    }
};
```

