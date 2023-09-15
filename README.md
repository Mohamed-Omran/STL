<!--  This document will be pushed to https://github.com/Mohamed-Omran/STL -->
# C++ STL Containers and Functions Summary

- [C++ STL Containers and Functions Summary](#c-stl-containers-and-functions-summary)
  - [VECTORS](#vectors)
  - [LISTS](#lists)
  - [DEQUES](#deques)
  - [QUEUE](#queue)
  - [PRIORITY QUEUE](#priority-queue)
  - [STACK](#stack)
  - [PAIR](#pair)
  - [SET](#set)
  - [UNORDERED SET](#unordered-set)
  - [MULTISET](#multiset)
  - [MAP](#map)
  - [UNORDERED MAP](#unordered-map)
  - [MULTIMAP](#multimap)
  - [STRING](#string)
- [Standard Algorithms in C++](#standard-algorithms-in-c)
  - [Sorting Algorithms](#sorting-algorithms)
    - [`std::sort`](#stdsort)
    - [`std::stable_sort`](#stdstable_sort)
    - [`std::partial_sort`](#stdpartial_sort)
  - [Searching Algorithms](#searching-algorithms)
    - [`std::binary_search`](#stdbinary_search)
    - [`std::find`](#stdfind)
    - [`std::count`](#stdcount)
  - [Mathematical Algorithms](#mathematical-algorithms)
    - [`std::gcd`](#stdgcd)
    - [`std::lcm`](#stdlcm)
  - [Container Manipulation Algorithms](#container-manipulation-algorithms)
    - [`std::copy`](#stdcopy)
    - [`std::fill`](#stdfill)
    - [`std::reverse`](#stdreverse)
  - [Miscellaneous Algorithms](#miscellaneous-algorithms)
    - [`std::unique`](#stdunique)
    - [`std::rotate`](#stdrotate)


## VECTORS

- `vector<Type>(size_type n, const Type& val = Type())`: Constructs a dynamic array that can be resized. Suitable for sequential access and dynamic size changes.
- `vector<vector<int>> vec(5, vector<int>(3));`:  To creat a two dimensional vector of type int, for example, with size [5,3].
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
  - `reference at(size_type pos)`: Returns a reference to the element at position `pos`. **Time Complexity**: O(1)
  - `reference front()`: Returns a reference to the first element. **Time Complexity**: O(1)
  - `reference back()`: Returns a reference to the last element. **Time Complexity**: O(1)
  - `const_iterator cend() const`: Returns a **const_iterator** pointing to the element following the last element. **Time Complexity**: O(1)
  - `const_iterator cbegin() const`: Returns a **const_iterator** pointing to the first element. **Time Complexity**: O(1)
  - `const_iterator rbegin() const`: Returns a **reverse_iterator** pointing to the last element. **Time Complexity**: O(1)
  - `const_iterator rend() const`: Returns a **reverse_iterator** pointing to the element preceding the first element. **Time Complexity**: O(1)

      `for (auto it = vec.rbegin(); it != vec.rend(); ++it) cout << *it << endl; `
- **Element Manipulation:**
  - `iterator insert(iterator pos, const Type& val)`: Inserts an element `val` before the position `pos`. 
  - `void push_back(const Type& val)`: Inserts the element `val` at the end of the vector. **Time Complexity**: O(1). If the vector is full, the vector is reallocated with a larger capacity.
  - `void pop_back()`: Removes the last element from the vector. **Time Complexity**: O(1)
  - **Time Complexity**: O(n).
  - `iterator emplace(iterator pos, Args&&... args)`: Inserts an element constructed with `args` before the position `pos`. **Time Complexity**: O(n)
    - example: `vec.emplace(vec.end(), 10);` inserts 10 at the end of the vector.
    - `iterator erase(iterator pos)`: Removes the element at position `pos`. Returns an iterator pointing to the element following the removed element. **Time Complexity**: O(n)
  - `void clear()`: Removes all elements from the vector. **Time Complexity**: O(n)
- **Capacity and Size:**
  - `bool empty() const`: Returns true if the vector is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the vector. **Time Complexity**: O(1)
  - `void resize(size_type n, Type val = Type())`: Resizes the container to contain `n` elements, setting new elements to `val`. **Time Complexity**: O(n)
  - `size_type capacity() const`: Returns the number of elements that the container can hold. **Time Complexity**: O(1)
  - `void reserve(size_type n)`: Increases the capacity of the vector to at least `n` elements. **Time Complexity**: O(n)

## LISTS

- `list<Type>(size_type n, const Type& val = Type())`: Constructs a doubly-linked list. Suitable for frequent insertions and deletions at any position.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(iterator pos, const Type& val)`: Inserts an element `val` before the position `pos`. **Time Complexity**: O(1)
  - `iterator erase(iterator pos)`: Removes the element at position `pos`. **Time Complexity**: O(1)
  - `void push_back(const Type& val)`: Inserts the element `val` at the end of the list. **Time Complexity**: O(1)
  - `void push_front(const Type& val)`: Inserts the element `val` at the beginning of the list. **Time Complexity**: O(1)
  - `void pop_back()`: Removes the last element from the list. **Time Complexity**: O(1)
  - `void pop_front()`: Removes the first element from the list. **Time Complexity**: O(1)
  - `void remove(const Type& val)`: Removes all elements with value `val` from the list. **Time Complexity**: O(n)
- **List Operations:**
  - `void reverse()`: Reverses the order of elements in the list. **Time Complexity**: O(n)
  - `void sort()`: Sorts the elements in the list in non-decreasing order. **Time Complexity**: O(n log n)
  - `void merge(list<Type>& x)`: Merges the elements of `x` into the list. Assumes both lists are sorted. **Time Complexity**: O(n)
  - `void splice(iterator pos, list<Type>& x)`: Moves all elements of `x` into the list before the position `pos`. **Time Complexity**: O(1)

## DEQUES

- `deque<Type>(size_type n, const Type& val = Type())`: Constructs a double-ended queue that can be resized. Suitable for sequential access and dynamic size changes.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
  - `reference at(size_type pos)`: Returns a reference to the element at position `pos`. **Time Complexity**: O(1)
  - `reference front()`: Returns a reference to the first element. **Time Complexity**: O(1)
  - `reference back()`: Returns a reference to the last element. **Time Complexity**: O(1)
  - `const_iterator cend() const`: Returns a const_iterator pointing to the element following the last element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(iterator pos, const Type& val)`: Inserts an element `val` before the position `pos`. **Time Complexity**: O(n)
  - `iterator emplace(iterator pos, Args&&... args)`: Inserts an element constructed with `args` before the position `pos`. **Time Complexity**: O(n)
  - `iterator erase(iterator pos)`: Removes the element at position `pos`. **Time Complexity**: O(n)
  - `void clear()`: Removes all elements from the deque. **Time Complexity**: O(n)
- **Capacity and Size:**
  - `bool empty() const`: Returns true if the deque is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the deque. **Time Complexity**: O(1)
  - `Type& front()`: Returns a reference to the first element. **Time Complexity**: O(1)
  - `Type& back()`: Returns a reference to the last element. **Time Complexity**: O(1)
  - `void resize(size_type n, Type val = Type())`: Resizes the container to contain `n` elements, setting new elements to `val`. **Time Complexity**: O(n)
  - `size_type max_size() const`: Returns the maximum possible size of the deque. **Time Complexity**: O(1)
  - `void shrink_to_fit()`: Reduces the capacity of the deque to fit its size. **Time Complexity**: O(n)



## QUEUE

- `queue<Type>`: Implements a First-In-First-Out (FIFO) data structure. Suitable for task scheduling, breadth-first traversal, and buffering.
- **Element Manipulation:**
  - `void push(const Type& val)`: Inserts the element `val` at the back of the queue. **Time Complexity**: O(1)
  - `void pop()`: Removes the front element from the queue. **Time Complexity**: O(1)
  - `const Type& front() const`: Returns a const reference to the front element. **Time Complexity**: O(1)
  - `const Type& back() const`: Returns a const reference to the back element. **Time Complexity**: O(1)
- **Queue Size:**
  - `bool empty() const`: Returns true if the queue is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the queue. **Time Complexity**: O(1)
## PRIORITY QUEUE

A `priority_queue` is a container that implements a priority queue using a heap data structure. It is suitable for scenarios where you need to efficiently retrieve elements with the highest (or lowest) priority.

- `priority_queue<Type>`: Creates an empty priority queue where elements are ordered in descending order of their value (highest value at the top). High values have high priority.
- `priority_queue<Type, vector<Type>, greater<Type>>`: Creates an empty priority queue where elements are ordered in ascending order of their value (lowest value at the top). Low values have high priority.
- `priority_queue<Type> pq(vec.begin(), vec.end())`: Creates a priority queue from the elements in the range `[vec.begin(), vec.end())`. The elements are ordered in descending order of their value (highest value at the top). `vec` must be a container that supports random access iterators (e.g. `vector`, `deque`). **Time Complexity: O(n)** where `n` is the number of elements in the range.

**Element Manipulation:**

- `void push(const Type& val)`: Inserts the element `val` into the priority queue. This operation ensures that elements with higher priority are closer to the front **Time Complexity**: O(log n).

- `void pop()`: Removes the highest-priority element from the priority queue. After removal, the next highest-priority element becomes the new top element. **Time Complexity**: O(log n).

- `const Type& top() const`: Returns a const reference to the highest-priority element without removing it. **Time Complexity**: O(1).

- **NOTE:** The `top()`  and `pop()` operations are only valid if the priority queue is not empty. Calling these operations on an empty priority queue will result in undefined behavior. You can use the `empty()` operation to check if the priority queue is empty before calling `top()` or `pop()`.

**Priority Queue Size:**

- `bool empty() const`: Returns true if the priority queue is empty. **Time Complexity**: O(1).

- `size_type size() const`: Returns the number of elements in the priority queue. **Time Complexity**: O(1).

Suppose you are managing a to-do list where tasks have different priorities represented by integers, with lower values indicating higher priority. You can use a `priority_queue` to efficiently manage and retrieve tasks by their priority:

```cpp
#include <iostream>
#include <queue>

int main() {
    // Create a priority queue where elements are ordered in ascending order of their value
    std::priority_queue<int, std::vector<int>, std::greater<int>> min_heap;

    // Add tasks with priorities
    min_heap.push(3);  // Low priority
    min_heap.push(1);  // High priority
    min_heap.push(2);  // Medium priority

    // Retrieve and complete tasks
    while (!min_heap.empty()) {
        int nextTask = min_heap.top();
        min_heap.pop();
        std::cout << "Task with priority " << nextTask << " completed.\n";
    }

    return 0;
}
```

In this example, `min_heap` ensures that tasks are completed in order of their priority, with high-priority tasks (low values) being processed first. The output is as follows:

```
Task with priority 1 completed.
Task with priority 2 completed.
Task with priority 3 completed.
```

## STACK

- `stack<Type>`: Implements a Last-In-First-Out (LIFO) data structure. Suitable for managing function calls, backtracking, and evaluating expressions.
- **Element Manipulation:**
  - `void push(const Type& val)`: Inserts the element `val` onto the top of the stack. **Time Complexity**: O(1)
  - `void pop()`: Removes the top element from the stack, if empty the behavior is undefined. **Time Complexity**: O(1)
  - `const Type& top() const`: Returns a const reference to the top element, if empty the behavior is undefined. **Time Complexity**: O(1).
- **Stack Size:**
  - `bool empty() const`: Returns true if the stack is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the stack. **Time Complexity**: O(1)

## PAIR

- `pair<T1, T2>`: Represents a simple container holding two values of possibly different types. Commonly used for returning multiple values from a function.
- **Structure:**
  - `T1 first`: Holds the first value of the pair.
  - `T2 second`: Holds the second value of the pair.



## SET

- `set<Type>`: Constructs a balanced binary search tree that stores unique elements in a sorted order. Suitable for maintaining a sorted collection of unique values.
- `set<Type, greater<Type>>`: Constructs a balanced binary search tree that stores unique elements in a sorted order. Suitable for maintaining a sorted collection of unique values in descending order.
- `set<Type> s(vec.begin(), vec.end());`: To initialize a set with a vector. Complixity: O(nlogn)

- **Element Access:**
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const Type& val)`: Inserts the element `val` into the set. **Time Complexity**: O(log n)
- **Set Size:**
  - `size_type size() const`: Returns the number of elements in the set. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the set is empty. **Time Complexity**: O(1)
- **Set Searching and Bounds:**
  - `iterator find(const Type& val)`: Returns an iterator to the element with value `val` in the set, if not found returns `end()`. **Time Complexity**: O(log n).
  - `size_type count(const Type& val)`: Returns the number of elements with value `val` in the set. **Time Complexity**: O(log n)
  - `iterator lower_bound(const Type& val)`: Returns an iterator to the first element not less than `val`. **Time Complexity**: O(log n)
  - `iterator upper_bound(const Type& val)`: Returns an iterator to the first element greater than `val`. **Time Complexity**: O(log n)
  - `pair<iterator, iterator> equal_range(const Type& val)`: Returns a pair of iterators representing the range of elements with value `val`. **Time Complexity**: O(log n)


## UNORDERED SET

- `unordered_set<Type>`: Constructs an unordered hash set that stores unique elements. Provides fast constant-time average lookup.
- `unordered_set<Type> s(vec.begin(), vec.end());`: To initialize an unordered set with a vector. **Complixity: O(n)**.

- **Element Access:**
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `pair<iterator, bool> insert(const Type& val)`: Inserts the element `val` into the unordered set. **Time Complexity**: Avg O(1), Worst O(n)
  - `size_type erase(const Type& val)`: Removes the element with value `val` from the unordered set. **Time Complexity**: Avg O(1), Worst O(n)
  - `void clear()`: Removes all elements from the unordered set. **Time Complexity**: O(n)
- **Unordered Set Size:**
  - `size_type size() const`: Returns the number of elements in the unordered set. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the unordered set is empty. **Time Complexity**: O(1)
- **Unordered Set Searching:**
  - `iterator find(const Type& val)`: Returns an iterator to the element with value `val` in the unordered set, if not found returns `end()`. **Time Complexity**: Avg O(1), Worst O(n). 

## MULTISET

- `multiset<Type>`: Constructs a balanced binary search tree that stores multiple elements with equal keys. Suitable for maintaining a sorted collection with duplicate values.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const Type& val)`: Inserts the element `val` into the multiset. **Time Complexity**: O(log n)
  - `iterator erase(iterator pos)`: Removes the element at position `pos`. **Time Complexity**: O(1)
  - `size_type erase(const Type& val)`: Removes all elements with value `val` from the multiset. **Time Complexity**: O(log n)
  - `void clear()`: Removes all elements from the multiset. **Time Complexity**: O(n)
- **Multiset Size:**
  - `size_type size() const`: Returns the number of elements in the multiset. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the multiset is empty. **Time Complexity**: O(1)
- **Multiset Searching and Bounds:**
  - `iterator find(const Type& val)`: Returns an iterator to the element with value `val` in the multiset. **Time Complexity**: O(log n)
  - `size_type count(const Type& val)`: Returns the number of elements with value `val` in the multiset. **Time Complexity**: O(log n)
  - `iterator lower_bound(const Type& val)`: Returns an iterator to the first element not less than `val`. **Time Complexity**: O(log n)
  - `iterator upper_bound(const Type& val)`: Returns an iterator to the first element greater than `val`. **Time Complexity**: O(log n)
  - `pair<iterator, iterator> equal_range(const Type& val)`: Returns a pair of iterators representing the range of elements with value `val`. **Time Complexity**: O(log n)

## MAP

- `map<Key, T>`: Constructs a balanced binary search tree that stores key-value pairs. Suitable for maintaining a sorted collection of unique keys and associated values.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const std::pair<Key, T>& val)`: Inserts the key-value pair `val` into the map. **Time Complexity**: O(log n)
  - `size_type erase(const Key& key)`: Removes the element with key `key` from the map. **Time Complexity**: O(log n)
  - `void clear()`: Removes all elements from the map. **Time Complexity**: O(n)
- **Map Size:**
  - `size_type size() const`: Returns the number of elements in the map. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the map is empty. **Time Complexity**: O(1)
- **Map Searching:**
  - `iterator find(const Key& key)`: Returns an iterator to the element with key `key` in the map. **Time Complexity**: O(log n)
  - `size_type count(const Key& key)`: Returns the number of elements with key `key` in the map. **Time Complexity**: O(log n)
  - `iterator lower_bound(const Key& key)`: Returns an iterator to the first element not less than `key`. **Time Complexity**: O(log n)
  - `iterator upper_bound(const Key& key)`: Returns an iterator to the first element greater than `key`. **Time Complexity**: O(log n)
  - `pair<iterator, iterator> equal_range(const Key& key)`: Returns a pair of iterators representing the range of elements with key `key`. **Time Complexity**: O(log n)



## UNORDERED MAP

- `unordered_map<Key, T>`: Constructs an unordered hash map that stores key-value pairs. Provides fast constant-time average lookup.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const std::pair<Key, T>& val)`: Inserts the key-value pair `val` into the unordered map. **Time Complexity**: Avg O(1), Worst O(n)
  - `size_type erase(const Key& key)`: Removes the element with key `key` from the unordered map. **Time Complexity**: Avg O(1), Worst O(n)
  - `void clear()`: Removes all elements from the unordered map. **Time Complexity**: O(n)
- **Unordered Map Size:**
  - `size_type size() const`: Returns the number of elements in the unordered map. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the unordered map is empty. **Time Complexity**: O(1)
- **Unordered Map Searching:**
  - `iterator find(const Key& key)`: Returns an iterator to the element with key `key` in the unordered map. **Time Complexity**: Avg O(1), Worst O(n)

## MULTIMAP

- `multimap<Key, T>`: Constructs a balanced binary search tree that stores multiple key-value pairs with equal keys. Suitable for maintaining a sorted collection with duplicate keys.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const std::pair<Key, T>& val)`: Inserts the key-value pair `val` into the multimap. **Time Complexity**: O(log n)
  - `iterator erase(iterator pos)`: Removes the element at position `pos`. **Time Complexity**: O(1)
  - `size_type erase(const Key& key)`: Removes all elements with key `key` from the multimap. **Time Complexity**: O(log n)
  - `void clear()`: Removes all elements from the multimap. **Time Complexity**: O(n)
- **Multimap Size:**
  - `size_type size() const`: Returns the number of elements in the multimap. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the multimap is empty. **Time Complexity**: O(1)
- **Multimap Searching:**
  - `iterator find(const Key& key)`: Returns an iterator to the first element with key `key` in the multimap. **Time Complexity**: O(log n)
  - `size_type count(const Key& key)`: Returns the number of elements with key `key` in the multimap. **Time Complexity**: O(log n)


## STRING

- `std::string`: A container representing a sequence of characters.
- **Construction:**
  - `string()`: Constructs an empty string.
  - `string(const char* s)`: Constructs a string from a C-style string.
  - `string(const char* s, size_type n)`: Constructs a string from the first `n` characters of a C-style string.
  - `string(size_type n, char c)`: Constructs a string with `n` copies of character `c`.
  - `string(const string& str)`: Constructs a string by copying another string.
  - `string(iterator first, iterator last)`: Constructs a string from the characters in the range `[first, last)`.
- **Iterators:**
  - `iterator begin()`: Returns an iterator pointing to the first character. **Time Complexity**: O(1)
  - `iterator end()`: Returns an iterator pointing to the position after the last character. **Time Complexity**: O(1)
  - `const_iterator cbegin() const`: Returns a const_iterator pointing to the first character. **Time Complexity**: O(1)
  - `const_iterator cend() const`: Returns a const_iterator pointing to the position after the last character. **Time Complexity**: O(1)
- **Size and Access:**
  - `size_type size() const`: Returns the number of characters in the string. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the string is empty. **Time Complexity**: O(1)
  - `const char& operator[](size_type pos) const`: Returns a const reference to the character at position `pos`. **Time Complexity**: O(1)
  - `char& operator[](size_type pos)`: Returns a reference to the character at position `pos`. **Time Complexity**: O(1)
  - `const char& front() const`: Returns a const reference to the first character. **Time Complexity**: O(1)
  - `char& front()`: Returns a reference to the first character. **Time Complexity**: O(1)
  - `const char& back() const`: Returns a const reference to the last character. **Time Complexity**: O(1)
  - `char& back()`: Returns a reference to the last character. **Time Complexity**: O(1)
- **Assignment and Concatenation:**
  - `string& operator=(const string& str)`: Assigns another string to the current string.
  - `string& operator=(const char* s)`: Assigns a C-style string to the current string.
  - `string& operator+=(const string& str)`: Appends another string to the current string.
  - `string& operator+=(const char* s)`: Appends a C-style string to the current string.
- **String Manipulation:**
  - `string& append(const string& str)`: Appends another string to the current string.
  - `string& append(const char* s)`: Appends a C-style string to the current string.
  - `string& insert(size_type pos, const string& str)`: Inserts another string at the specified position.
  - `string& erase(size_type pos, size_type len)`: Erases a portion of the string starting at `pos` and spanning `len` characters.
  - `string& replace(size_type pos, size_type len, const string& str)`: Replaces a portion of the string starting at `pos` and spanning `len` characters with another string.
- **Searching:**
  - `size_type find(const string& str, size_type pos = 0) const`: Finds the first occurrence of another string within the current string starting at `pos`. Returns `npos` if not found.
  - `size_type find(const char* s, size_type pos = 0) const`: Finds the first occurrence of a C-style string within the current string starting at `pos`. Returns `npos` if not found.
- **Other Operations:**
  - `void clear()`: Clears the contents of the string.
  - `const char* c_str() const`: Returns a pointer to a C-style null-terminated string representation of the string.
- **Comparison Operators:**
  - `operator==`, `operator!=`, `operator<`, `operator>`, `operator<=`, `operator>=`: Comparison operators for strings.


# Standard Algorithms in C++

## Sorting Algorithms

### `std::sort`
- Description: Sorts the elements of a container in ascending order using the quicksort algorithm.
- Time Complexity: O(n log n), where 'n' is the number of elements.
```cpp
template <class RandomAccessIterator>
void sort(RandomAccessIterator first, RandomAccessIterator last);


// Example: Sort the first 10 elements of a vector
vector<int> vec(15) = {4, 2, 5, 1, 3, 9, 8, 7, 6, 0, 10, 11, 12, 13, 14};
sort(vec.begin(), vec.begin() + 10);
// vec = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ...}
```

### `std::stable_sort`
- Description: Sorts the elements of a container in ascending order while preserving the relative order of elements with equal values.
- Time Complexity: O(n log n), where 'n' is the number of elements.
```cpp
template <class RandomAccessIterator>
void stable_sort(RandomAccessIterator first, RandomAccessIterator last);

// Example: Sort the first 10 elements of a vector
vector<int> vec(15) = {4, 2, 5, 1, 3, 9, 8, 7, 6, 0, 10, 11, 12, 13, 14};
stable_sort(vec.begin(), vec.begin() + 10);
// vec = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ...}
```

### `std::partial_sort`
- Description: Partially sorts the elements of a container such that the first 'k' elements are in ascending order.
- Time Complexity: O(n log k), where 'n' is the number of elements and 'k' is the number of elements to be sorted.
```cpp
template <class RandomAccessIterator>
void partial_sort(RandomAccessIterator first, RandomAccessIterator middle, RandomAccessIterator last);

// Example: Sort the first 10 elements of a vector
vector<int> vec(15) = {4, 2, 5, 1, 3, 9, 8, 7, 6, 0, 10, 11, 12, 13, 14};
partial_sort(vec.begin(), vec.begin() + 10, vec.end());
// vec = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ...}
```

## Searching Algorithms

### `std::binary_search`
- Description: Checks if a value exists in a sorted container using binary search.
- Time Complexity: O(log n), where 'n' is the number of elements.
```cpp
template <class ForwardIterator, class T>
bool binary_search(ForwardIterator first, ForwardIterator last, const T& value);

// Example: Check if 5 exists in a vector
vector<int> vec = {1, 2, 3, 4, 5, 6, 7, 8};
bool has_five = binary_search(vec.begin(), vec.end(), 5);
// has_five = true
```

### `std::find`
```cpp
template <class InputIterator, class T>
InputIterator find(InputIterator first, InputIterator last, const T& value);
```
- Description: Finds the first occurrence of a value in a container.
- Time Complexity: O(n), where 'n' is the number of elements.

### `std::count`
```cpp
template <class InputIterator, class T>
typename iterator_traits<InputIterator>::difference_type count(InputIterator first, InputIterator last, const T& value);

// Example: Count the number of occurrences of 5 in a vector
vector<int> vec = {1, 2, 3, 4, 5, 5, 5, 6, 7, 8};
int num_fives = count(vec.begin(), vec.end(), 5);
// num_fives = 3
```
- Description: Counts the number of occurrences of a value in a container.
- Time Complexity: O(n), where 'n' is the number of elements.

## Mathematical Algorithms

### `std::gcd`
```cpp
template <class T>
T gcd(T a, T b);

// Example: Calculate the GCD of 12 and 18
int gcd_12_18 = gcd(12, 18);
// gcd_12_18 = 6
```
- Description: Calculates the greatest common divisor (GCD) of two integers.
- Time Complexity: O(log min(a, b)), where 'a' and 'b' are the input integers.

### `std::lcm`
- Description: Calculates the least common multiple (LCM) of two integers.
- Time Complexity: O(log min(a, b)), where 'a' and 'b' are the input integers.
```cpp
template <class T>
T lcm(T a, T b);

// Example: Calculate the LCM of 12 and 18
int lcm_12_18 = lcm(12, 18);
// lcm_12_18 = 36
```

## Container Manipulation Algorithms

### `std::copy`
```cpp
template <class InputIterator, class OutputIterator>
OutputIterator copy(InputIterator first, InputIterator last, OutputIterator result);
```
- Description: Copies elements from one container to another.
- Time Complexity: O(n), where 'n' is the number of elements to be copied.

### `std::fill`
```cpp
template <class ForwardIterator, class T>
void fill(ForwardIterator first, ForwardIterator last, const T& value);
```
- Description: Fills a range of elements in a container with a specified value.
- Time Complexity: O(n), where 'n' is the number of elements to be filled.

### `std::reverse`
```cpp
template <class BidirectionalIterator>
void reverse(BidirectionalIterator first, BidirectionalIterator last);
```
- Description: Reverses the order of elements in a container.
- Time Complexity: O(n), where 'n' is the number of elements.

## Miscellaneous Algorithms

### `std::unique`
```cpp
template <class ForwardIterator>
ForwardIterator unique(ForwardIterator first, ForwardIterator last);
```
- Description: Removes consecutive duplicate elements from a sorted container.
- Time Complexity: O(n), where 'n' is the number of elements.

### `std::rotate`
```cpp
template <class ForwardIterator>
ForwardIterator rotate(ForwardIterator first, ForwardIterator middle, ForwardIterator last);
```
- Description: Rotates the elements in a container by a specified number of positions.
- Time Complexity: O(n), where 'n' is the number of elements.
