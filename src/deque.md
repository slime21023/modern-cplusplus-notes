# deque
deque 為 sequence container
* 支援兩端點的push/pop
* 支援random access
* 內部元素的儲存為非連續性的
* Functions:
  * size()
  * = , []
  * front(), back()
  * empty()
  * begin(), end(), rbegin(), rend()
  * insert(), erase()
  * clear()
  * push_back(), push_front(), pop_back(), pop_front()


### Declare and initialize the deque
```c++
std::deque<int> d = {7, 5, 16, 8};
```

### Add elements to the deque
```c++
// adds the value 5 to the end of the deque
myDeque.push_back(5); 
 // adds the value 10 to the beginning of the deque
myDeque.push_front(10);
// adds the value 15 at index 1 in the deque
myDeque.insert(myDeque.begin() + 1, 15); 
```

### Remove elements from the deque
```c++
// removes the last element from the deque
myDeque.pop_back();
// removes the first element from the deque
myDeque.pop_front(); 
// removes the element at index 1 from the deque
myDeque.erase(myDeque.begin() + 1); 
```

### Access elements in the deque
```c++
// gets the first element of the deque
int firstElement = myDeque.front(); 
// gets the last element of the deque
int lastElement = myDeque.back(); 
// gets the element at index 1 of the deque
int secondElement = myDeque.at(1); 
int secondElement = myDeque[1];
```

### Get the size of the deque
```c++
// returns the number of elements in the deque
int size = myDeque.size(); 
```

### Iterate over the elements of the deque
```c++
for (auto it = myDeque.begin(); it != myDeque.end(); it++) {
    std::cout << *it << std::endl;
}

for (auto element : myDeque) {
    std::cout << element << std::endl;
}
```

### example
```c++
#include <iostream>
#include <deque>
 
int main()
{
    // Create a deque containing integers
    std::deque<int> myDeque = {7, 5, 16, 8};
 
    // Add an integer to the beginning and end of the deque
    myDeque.push_front(13);
    myDeque.push_back(25);
 
    for (auto it = myDeque.begin(); it != myDeque.end(); it++) {
        std::cout << *it << std::endl;
    }

    for (auto element : myDeque) {
        std::cout << element << std::endl;
    }
        
}
```
