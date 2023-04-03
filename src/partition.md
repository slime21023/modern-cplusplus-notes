# partition
Partition operations:
* `partition(beg, end, condition)`:  This function is used to **partition the elements** on **basis of condition** mentioned in its arguments.
* `is_partitioned(beg, end, condition)`: This function returns boolean true **if container is partitioned** else returns false.
* `stable_partition(beg, end, condition)`: This function is used to **partition the elements on basis of condition** mentioned in its arguments in **such a way that the relative order of the elements is preserved**.
* `partition_point(beg, end, condition)`: This function **returns an iterator pointing to the partition point** of container.

### Example
partition & is_partitioned

```c++
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;

int main()
{
    // Initializing vector
    vector<int> vect = { 2, 1, 5, 6, 8, 7 };
    
    // Checking if vector is partitioned
    // using is_partitioned()
    bool p = is_partitioned(vect.begin(), vect.end(), [](int x) { return x%2==0; });
    if(!p) 
    {
        cout << "Vector is not partitioned"<< endl;
    }
    
    // partitioning vector using partition()
    partition(vect.begin(), vect.end(), [](int x) { return x%2==0; });
    p = is_partitioned(vect.begin(), vect.end(), [](int x) { return x%2==0; });
    
    if(p) 
    {
        cout << "Vector is partitioned"<< endl;
    }
    
    // Displaying partitioned Vector
    cout << "The partitioned vector is : ";
    for (int &x : vect) 
        cout << x << " ";
     
    return 0;
}
```

stable_partition & partition_point

```c++
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;
int main()
{
    // Initializing vector
    vector<int> vect = { 2, 1, 5, 6, 8, 7 };
     
    // partitioning vector using stable_partition()
    // in sorted order
    stable_partition(vect.begin(), vect.end(), [](int x) { return x%2 == 0; });
     
    // Displaying partitioned Vector
    cout << "The partitioned vector is : ";
    for (int &x : vect) 
        cout << x << " ";
    cout << endl;
     
    // Declaring iterator
    vector<int>::iterator it1;
     
    // using partition_point() to get ending position of partition
    auto it = partition_point(vect.begin(), vect.end(), [](int x) { return x%2==0; });
     
    // Displaying partitioned Vector
    cout << "The vector elements returning true for condition are : ";
    for ( it1= vect.begin(); it1!=it; it1++)
        cout << *it1 << " ";
    cout << endl;
     
    return 0;
}
```

