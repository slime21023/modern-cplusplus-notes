# random order

### rotate
`template <class ForwardIterator>  ForwardIterator rotate (ForwardIterator first, ForwardIterator middle, ForwardIterator last);`

Rotates the order of the elements in the range `[first,last)`, in such a way that the element pointed by **middle** becomes the new first element.

**Example**

```c++
#include <iostream>
#include <algorithm>
#include <vector>

int main () {
  std::vector<int> myvector;

  // set some values:
  for (int i=1; i<10; ++i) myvector.push_back(i); // 1 2 3 4 5 6 7 8 9

  std::rotate(myvector.begin(),myvector.begin()+3,myvector.end());
                                                  // 4 5 6 7 8 9 1 2 3
  // print out content:
  std::cout << "myvector contains:";
  for (std::vector<int>::iterator it=myvector.begin(); it!=myvector.end(); ++it)
    std::cout << ' ' << *it;
  std::cout << '\n';

  return 0;
}
```

### shuffle

`template <class RandomAccessIterator, class URNG>  void shuffle (RandomAccessIterator first, RandomAccessIterator last, URNG&& g);`

**Randomly rearrange elements in range using generator**

Rearranges the elements in the range `[first,last)` randomly, using `g` as **uniform random number generator**.
* The function swaps the value of each element with that of some other randomly picked element. The function determines the element picked by calling `g()`.

```c++
#include <iostream>
#include <algorithm>
#include <array>
#include <random>
#include <chrono>

int main () {
  std::array<int,5> foo {1,2,3,4,5};

  // obtain a time-based seed:
  unsigned seed = std::chrono::system_clock::now().time_since_epoch().count();

  shuffle (foo.begin(), foo.end(), std::default_random_engine(seed));

  std::cout << "shuffled elements:";
  for (int& x: foo) std::cout << ' ' << x;
  std::cout << '\n';

  return 0;
}
```

### Other operations
- [next_permutation](https://cplusplus.com/reference/algorithm/next_permutation/)
- [prev_permutation](https://cplusplus.com/reference/algorithm/prev_permutation/)
- [reverse](https://cplusplus.com/reference/algorithm/reverse/)