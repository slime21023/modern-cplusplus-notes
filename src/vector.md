# vector

vector為sequence container
* Dynamic Array、 Array List
* Size可以動態地收縮或增加，不需要在compile time提供size
* Element access:
  * at()
  * []
  * front()
  * back()
  * data()
* Modifiers:
  * insert()
  * emplace()
  * push_back()
  * emplace_back()
  * pop_back()
  * resize()
  * swap()
  * erase()
  * clear()

### Declare and initialize the vector
```c++
// creates an empty vector of integers
std::vector<int> myVector; 
```
Using the constructor with a size argument:
```c++
// creates a vector of integers with 5 default-initialized elements
std::vector<int> myVector(5); 
```
Using the constructor with a size and value argument:
```c++
// creates a vector of integers with 5 elements, each initialized to 10
std::vector<int> myVector(5, 10); 
```
Using the initializer list constructor:
```c++
// creates a vector of integers with 5 elements initialized to 1, 2, 3, 4, 5
std::vector<int> myVector = {1, 2, 3, 4, 5}; 
```
Using the copy constructor:
```c++
std::vector<int> myVector1 = {1, 2, 3, 4, 5};
// creates a new vector of integers with the same elements as myVector1
std::vector<int> myVector2(myVector1); 
```

### Iterate over the elements of the vector
```c++
for (int i = 0; i < myVector.size(); i++) {
    std::cout << myVector[i] << std::endl;
}

for (auto element : myVector) {
    std::cout << element << std::endl;
}
```

### Example
```c++
#include <iostream>
#include <vector>


int main() {
    std::vector<int> myVector = {1, 2, 3, 4, 5}; 
    
    for (int i = 0; i < myVector.size(); i++) {
        std::cout << myVector[i] << std::endl;
    }
    
    for (auto element : myVector) {
        std::cout << element << std::endl;
    }

    return 0;
}
```
