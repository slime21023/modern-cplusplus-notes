# iterator

- Objects that enable **traversal** of containers in some order, for either reading or writing.
  
- Iterators are defined as **templates** and must comply with a very specific set of rules in order to qualify as one of many types of iterators.

- Iterator is a **higher abstraction** for elements used to traverse containers, whereas pointers and integers are special types of iterators, not suitable for every container.

Types of Iterators
1. Input iterator
2. Output iterator
3. Forward iterator
4. Bidirectional iterator
5. Random-access iterator

### Input Iterator
- Only able to read (only accessing, not assigning)
- Only move forward
- Can be incremented (**++it, it++**)
- Only one pass possible
- Least requirement supported by STL
- Suitable for input streams, such as Keyboard buffers or read-only files.
  
### Output Iterator
- Only able to write
- Only moves forward
- Only one pass possible
- Least requirement supported by STL
- Suitable for output streams, such as screen text or write-only files

### Forward Iterator
- It has requirements of both the input and the output iterator
- Able to read and write
- Only moves forward
- Supports multiple passes of container
- Suitable for traversing Singly Linked List

### Bidirectional Iterator
- All capabilities of **Forward Iterators** + **Backward traversal**
- Suitable for Doubly Linked List

### Random-Access Iterator
- All capabilities of Bidirectional Iterators + Random Access by means of indexing
- Suitable for Vectors and similar containers (e.g., array)

