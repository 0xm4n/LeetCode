```cpp
/**
 * Definition of Interval:
 * classs Interval {
 *     int start, end;
 *     Interval(int start, int end) {
 *         this->start = start;
 *         this->end = end;
 *     }
 * }
 */

class Solution {
public:
    /**
     * @param airplanes: An interval array
     * @return: Count of airplanes are in the sky.
     */
    static bool cmp(pair<int, int> p1, pair<int, int> p2) {
        if (p1.first != p2.first) {
            return p1.first < p2.first;
        }
        return p1.second < p2.second;
    }
    int countOfAirplanes(vector<Interval> &airplanes) {
        // write your code here
        vector<pair<int, int>>  arr;
        for (int i = 0; i < airplanes.size(); ++i) {
            arr.push_back(make_pair(airplanes[i].start, 1));
            arr.push_back(make_pair(airplanes[i].end, -1));
        }

        sort(arr.begin(), arr.end(), cmp);

        int res = 0;
        int cur = 0;

        for (int i = 0; i < arr.size(); ++i) {
            cur += arr[i].second;
            res = max(cur, res);
        }
        return res;
    }
};
```

