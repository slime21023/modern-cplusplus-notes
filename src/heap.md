# heap

**STL Functions for Heap Operations**
1. `make_heap()`: Converts given range to a heap
2. `push_heap()`: Arrange the heap after insertion at the end
3. `pop_heap()`: Moves the max element at the end for deletion
4. `sort_heap()`: Sort the elements of the max_heap to ascending order
5. `is_heap()`: Checks if the given range is max_heap
6. `is_heap_until()`: Returns the largest sub-range that is max_heap

### `make_heap()`
The `std::make_heap()` function is used to convert the given range in a container to a heap.
* By default, it **generates the max heap** but we can use a **custom comparator to change it to the min heap**.
* `std::make_heap(begin_iterator, end_iterator);`
  * The iterators provided must be of **randomAccessIterator** type.

**Example**

```c++
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main()
{
    // Initializing a vector
    vector<int> v1 = { 20, 30, 40, 25, 15 };
 
    // Converting vector into a heap
    // using make_heap()
    make_heap(v1.begin(), v1.end());
 
    // Displaying the maximum element of heap
    // using front()
    cout << "The maximum element of heap is : ";
    cout << v1.front() << endl;
 
    return 0;
}
```

### `push_heap()`
The **std::push_heap()** function is used to sort the heap after the insertion of an element at the end of the heap.
* `std::push_heap(begin_interator, end_iterator);`

**Example**

```c++
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

void print(vector<int> &vc) {
	for (auto i : vc) {
		cout << i << " ";
	}
	cout << endl;
}

int main()
{
	vector <int> vc{20,30,40,10};

	make_heap(vc.begin(), vc.end());
    cout << "Initial Heap: ";
	print(vc);

	vc.push_back(50);
	cout << "Heap just after push_back(): ";
	print(vc);
	
	push_heap(vc.begin(), vc.end());
    cout << "Heap after push_heap(): ";
	print(vc);

	return 0;
}
```

### `pop_heap()`
The **std::pop_heap()** function is used to move the largest element at the end of the heap so that we can safely remove the element without destroying the heap.
* Then we use the **pop_back()** function of std::vector class to actually remove that element.
* `std::pop_head(begin_iterator, end_iterator);`

**Example**

```c++
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

void print(vector<int> &vc) {
	for (auto i : vc) {
		cout << i << " ";
	}
	cout << endl;
}

int main()
{
	vector <int> vc{20,30,40,10};

	// making heap
    make_heap(vc.begin(), vc.end());
    cout << "Initial Heap: ";
    print(vc);

	// using pop_heap() function to move the largest element
    // to the end
    pop_heap(vc.begin(), vc.end());
    cout << "Heap after pop_heap(): ";
    print(vc);
	
	// actually removing the element from the heap using
    // pop_back()
    vc.pop_back();
    cout << "Heap after pop_back(): ";
    print(vc);

	return 0;
}
```

### `sort_heap()`

The **std::sort_heap()** function is used to sort the heap in ascending order. It uses the heapsort algorithm and only works on the heap.

**Example**

```c++
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing a vector
    vector<int> v1 = { 20, 30, 40, 25, 15 };
 
    // Converting vector into a heap
    // using make_heap()
    make_heap(v1.begin(), v1.end());
 
    // Displaying heap elements
    cout << "The heap elements are: ";
    for (int& x : v1)
        cout << x << " ";
    cout << endl;
 
    // sorting heap using sort_heap()
    sort_heap(v1.begin(), v1.end());
 
    // Displaying heap elements
    cout << "The heap elements after sorting are: ";
    for (int& x : v1)
        cout << x << " ";
 
    return 0;
}
```

### `is_heap()`
The **std::is_heap()** function is used to check whether the given range of the container is a heap or not. 
* By default, it checks for **max heap** but we can also **use a comparator to make it work for min heap**.
* `std::is_heap(begin_iterator, end_iterator);`

### `is_heap_until()`
The **std::is_heap_until()** function returns the iterator to the position **till the container is the heap**.

**Example**

```c++
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
 
    // Initializing a vector
    vector<int> v1 = { 40, 30, 25, 35, 15 };
 
    // Declaring heap iterator
    vector<int>::iterator it1;
 
    // Checking if container is heap
    // using is_heap()
    is_heap(v1.begin(), v1.end())
        ? cout << "The container is heap " 
        : cout << "The container is not heap"; // ternary operator
    cout << endl;
 
    // using is_heap_until() to check position
    // till which container is heap
    auto it = is_heap_until(v1.begin(), v1.end());
 
    // Displaying heap range elements
    cout << "The heap elements in container are : ";
    for (it1 = v1.begin(); it1 != it; it1++)
        cout << *it1 << " ";
 
    return 0;
}
```