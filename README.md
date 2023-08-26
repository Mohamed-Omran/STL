# C++ STL Containers and Functions Summary

## VECTORS

- `vector<Type>(size_type n, const Type& val = Type())`: Constructs a dynamic array that can be resized. Suitable for sequential access and dynamic size changes.
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
  - `void clear()`: Removes all elements from the vector. **Time Complexity**: O(n)
- **Capacity and Size:**
  - `bool empty() const`: Returns true if the vector is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the vector. **Time Complexity**: O(1)
  - `Type& front()`: Returns a reference to the first element. **Time Complexity**: O(1)
  - `Type& back()`: Returns a reference to the last element. **Time Complexity**: O(1)
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

- `priority_queue<Type>`: Implements a priority queue using a heap. Suitable for retrieving the highest-priority element efficiently.
- **Element Manipulation:**
  - `void push(const Type& val)`: Inserts the element `val` into the priority queue. **Time Complexity**: O(log n)
  - `void pop()`: Removes the highest-priority element from the priority queue. **Time Complexity**: O(log n)
  - `const Type& top() const`: Returns a const reference to the highest-priority element. **Time Complexity**: O(1)
- **Priority Queue Size:**
  - `bool empty() const`: Returns true if the priority queue is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the priority queue. **Time Complexity**: O(1)

## PAIR

- `pair<T1, T2>`: Represents a simple container holding two values of possibly different types. Commonly used for returning multiple values from a function.
- **Structure:**
  - `T1 first`: Holds the first value of the pair.
  - `T2 second`: Holds the second value of the pair.

## STACK

- `stack<Type>`: Implements a Last-In-First-Out (LIFO) data structure. Suitable for managing function calls, backtracking, and evaluating expressions.
- **Element Manipulation:**
  - `void push(const Type& val)`: Inserts the element `val` onto the top of the stack. **Time Complexity**: O(1)
  - `void pop()`: Removes the top element from the stack. **Time Complexity**: O(1)
  - `const Type& top() const`: Returns a const reference to the top element. **Time Complexity**: O(1)
- **Stack Size:**
  - `bool empty() const`: Returns true if the stack is empty. **Time Complexity**: O(1)
  - `size_type size() const`: Returns the number of elements in the stack. **Time Complexity**: O(1)

## SET

- `set<Type>`: Constructs a balanced binary search tree that stores unique elements in a sorted order. Suitable for maintaining a sorted collection of unique values.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `iterator insert(const Type& val)`: Inserts the element `val` into the set. **Time Complexity**: O(log n)
- **Set Size:**
  - `size_type size() const`: Returns the number of elements in the set. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the set is empty. **Time Complexity**: O(1)
- **Set Searching and Bounds:**
  - `iterator find(const Type& val)`: Returns an iterator to the element with value `val` in the set. **Time Complexity**: O(log n)
  - `size_type count(const Type& val)`: Returns the number of elements with value `val` in the set. **Time Complexity**: O(log n)
  - `iterator lower_bound(const Type& val)`: Returns an iterator to the first element not less than `val`. **Time Complexity**: O(log n)
  - `iterator upper_bound(const Type& val)`: Returns an iterator to the first element greater than `val`. **Time Complexity**: O(log n)
  - `pair<iterator, iterator> equal_range(const Type& val)`: Returns a pair of iterators representing the range of elements with value `val`. **Time Complexity**: O(log n)

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

## UNORDERED SET

- `unordered_set<Type>`: Constructs an unordered hash set that stores unique elements. Provides fast constant-time average lookup.
- **Element Access:**
  - `iterator end()`: Returns an iterator pointing to the element following the last element. **Time Complexity**: O(1)
  - `iterator begin()`: Returns an iterator pointing to the first element. **Time Complexity**: O(1)
- **Element Manipulation:**
  - `pair<iterator, bool> insert(const Type& val)`: Inserts the element `val` into the unordered set. **Time Complexity**: Avg O(1), Worst O(n)
  - `size_type erase(const Type& val)`: Removes the element with value `val` from the unordered set. **Time Complexity**: Avg O(1), Worst O(n)
  - `void clear()`: Removes all elements from the unordered set. **Time Complexity**: O(n)
- **Unordered Set Size:**
  - `size_type size() const`: Returns the number of elements in the unordered set. **Time Complexity**: O(1)
  - `bool empty() const`: Returns true if the unordered set is empty. **Time Complexity**: O(1)
- **Unordered Set Searching:**
  - `iterator find(const Type& val)`: Returns an iterator to the element with value `val` in the unordered set. **Time Complexity**: Avg O(1), Worst O(n)


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




