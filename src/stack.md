# stack

**Container adapter** with the functionality of a stack.

- Pushes and pops element from one end of underlying container (**top** of the
  stack).

### Declare and initialize the stack

```c++
std::stack<int> myStack ({1, 2, 3, 4, 5});
```

### Add elements to the stack

```c++
// adds the value 5 to the top of the stack
myStack.push(5); 
// adds the value 10 to the top of the stack
myStack.push(10);
```

### Remove elements from the stack

```c++
myStack.pop();
```

### Access elements in the stack

```c++
// gets the top element of the stack
int topElement = myStack.top();
```

### Get the size of the stack

```c++
int size = myStack.size();
```

### Check if the stack is empty

```c++
bool isEmpty = myStack.empty();
```

### Example

```c++
#include <iostream>
#include <stack>

int main() {
    std::stack<int> myStack ({1, 2, 3, 4, 5});

    while (!myStack.empty()) {
        std::cout << myStack.top() << " ";
        myStack.pop();
    }

    return 0;
}
```
