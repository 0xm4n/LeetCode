```cpp
// heap sort
class Solution {
public:
    vector<int> sortArray(vector<int>& nums) {
        int n = nums.size();
        for (int i = n / 2 - 1; i >= 0; --i) {
            heapify(nums, n, i);
        }
        for (int i = n - 1; i >= 0; --i) {
            swap(nums[i], nums[0]);
            heapify(nums, i, 0);
        }
        return nums;
    }
    
    void heapify(vector<int>& nums, int n, int i) {
        int left = i * 2 + 1;
        int right = i * 2 + 2;
        int largest = i;
        if (left < n && nums[left] > nums[la	rgest]) {
            largest = left;
        }
        if (right < n && nums[right] > nums[largest]) {
            largest = right;
        }
        if (largest != i) {
            swap(nums[largest], nums[i]);
            heapify(nums, n, largest);
        }
    }
};
```

