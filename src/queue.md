# queue

**container adapter** with functionality of a **queue**

- Pushed elements at one end (**front**) and pops from other end (**end**) of
  underlying container.

* Functions:
  - size()
  - =
  - front(), back()
  - empty()
  - push(), pop()

### Declare and initialize the queue

```c++
std::queue<int> myQueue ({1, 2, 3, 4, 5});
```

### Add elements to the queue

```c++
// adds the value 5 to the top of the stack
myQueue.push(5);
```

### Remove elements from the queue

```c++
myQueue.pop();
```

### Access elements in the queue

```c++
int front = myQueue.front();
int back = myQueue.back();
```

### Get the size of the queue

```c++
int size = myQueue.size();
```

### Check if the queue is empty

```c++
bool isEmpty = myQueue.empty();
```

### Example

```c++
#include <iostream>
#include <queue>

int main() {
  std::queue<int> myQueue ({1, 2, 3, 4, 5});

  std::cout << myQueue.front() << " " << myQueue.back() << "\n";

  myQueue.pop();
  myQueue.pop();

  std::cout << "size = " << myQueue.size() << "\n";
  return 0;
}
```
