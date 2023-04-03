# sort

By default, the sort() function sorts the elements in **ascending** order.

**Example**

```c++
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

template<typename T>
void print (T t) {
	for (const auto& e : t) cout << e << " ";
	cout << endl;
}
  
int main()
{
    vector<int> v = { 2,3,4,1 };

	print (v); // outputs 2 3 4 1
	sort (v.begin (), v.end ());
	print (v); // outputs 1 2 3 4
}
```

### Sort in descending order
```c++
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

template<typename T>
void print (T t) {
	for (const auto& e : t) cout << e << " ";
	cout << endl;
}
  
int main()
{
    vector<int> v = { 2,3,4,1 };

	print (v); // outputs 2 3 4 1
	sort (v.begin (), v.end (), greater<int>());
	print (v); // outputs 1 2 3 4
}
```

### Sort in a particular order
```c++
#include <algorithm>
#include <iostream>
using namespace std;
  
// An interval has a start
// time and end time
struct Interval {
    int start, end;
};
  
// Compares two intervals
// according to starting times.
bool compareInterval(Interval i1, Interval i2)
{
    return (i1.start < i2.start);
}
  
int main()
{
    Interval arr[] = { { 6, 8 }, { 1, 9 }, { 2, 4 }, { 4, 7 } };
    int n = sizeof(arr) / sizeof(arr[0]);
  
    // sort the intervals in increasing order of
    // start time
    sort(arr, arr + n, compareInterval);
  
    cout << "Intervals sorted by start time : \n";
    for (int i = 0; i < n; i++)
        cout << "[" << arr[i].start << "," << arr[i].end
             << "] ";
  
    return 0;
}
```