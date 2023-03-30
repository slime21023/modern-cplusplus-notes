# priority_queue

**Container adaptor** that provides constant time lookup of the largest (by
default) element, at the expense of logarithmic inserting and extraction.

- A user-provided **Compare** can be supplied to change the ordering

### Container

- The type of the underlying container to use to store the elemenst.

- Must satisfy the requirements of **Sequence Container**, and its iterators
  must satisfy the requiremensts of **LegacyRandomAccessIterator**.

- The container must provide the following functions with the usual semantics:
  `front(), push_back(), pop_back()`.

- `std::vector` and `std::deque` satisfy these requirements.

* Functions:
  - size()
  - =
  - top()
  - empty()
  - push()
  - pop()

### Example

```c++
#include <iostream>
#include <queue>
#include <vector>

int main() {
    std::priority_queue<int, std::vector<int>, std::greater<int>> Q;
    
    std::vector<int> v = {8, 1, 6, 4, 0, 7,2, 9};
    for(int x: v) Q.push(x);
    while(!Q.empty()) {
        std::cout << Q.top() << "\n";
        Q.pop();
    }
    return 0;
}
```
