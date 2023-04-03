# search

* `template <class ForwardIterator1, class ForwardIterator2> ForwardIterator1 search (ForwardIterator1 first1, ForwardIterator1 last1, ForwardIterator2 first2, ForwardIterator2 last2);` 
* `template <class ForwardIterator1, class ForwardIterator2, class BinaryPredicate> ForwardIterator1 search (ForwardIterator1 first1, ForwardIterator1 last1, ForwardIterator2 first2, ForwardIterator2 last2, BinaryPredicate pred);`

**Search range for subsequence**
* Searches the range `[first1,last1)` for the first occurrence of the sequence defined by [`first2,last2)`, and returns an iterator to its first element, or **last1** if no occurrences are found.

```c++
#include <iostream>
#include <algorithm>
#include <vector>

bool mypredicate (int i, int j) {
  return (i==j);
}

int main () {
  std::vector<int> haystack;

  // set some values:        haystack: 10 20 30 40 50 60 70 80 90
  for (int i=1; i<10; i++) haystack.push_back(i*10);

  // using default comparison:
  int needle1[] = {40,50,60,70};
  std::vector<int>::iterator it;
  it = std::search (haystack.begin(), haystack.end(), needle1, needle1+4);

  if (it!=haystack.end())
    std::cout << "needle1 found at position " << (it-haystack.begin()) << '\n';
  else
    std::cout << "needle1 not found\n";

  // using predicate comparison:
  int needle2[] = {20,30,50};
  it = std::search (haystack.begin(), haystack.end(), needle2, needle2+3, mypredicate);

  if (it!=haystack.end())
    std::cout << "needle2 found at position " << (it-haystack.begin()) << '\n';
  else
    std::cout << "needle2 not found\n";

  return 0;
}
```