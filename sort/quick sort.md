```cpp
// quickSort
class Solution {
public:
    vector<int> sortArray(vector<int>& nums) {
        quicksort(nums, 0, nums.size() - 1);
        return nums;
    }
    
    void quicksort(vector<int>& nums, int left, int right) {
        if (left >= right) return;
        int mid = left + (right - left) / 2;
        swap(nums[mid], nums[left]);
        int pivot = nums[left];
        int i = left + 1, j = right;
        while (i <= j) {
            if (nums[i] > pivot && nums[j] < pivot) {
                swap(nums[i++], nums[j--]);
            }
            if (nums[i] <= pivot) ++i;
            if (nums[j] >= pivot) --j;
        }
        swap(nums[left], nums[j]);
        quicksort(nums, left, j - 1);
        quicksort(nums, j + 1, right);
    }
};
```

