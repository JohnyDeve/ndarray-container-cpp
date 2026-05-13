# API Reference

# Container

```cpp
template<typename T, size_t N>
class NDArray;
````

---

# Constructors

## Default Constructor

Creates an empty container.

---

## Dimensional Constructor

Constructs NDArray using explicit dimensions.

---

## Recursive Initializer Constructor

Constructs multidimensional arrays from nested initializer lists.

---

## Copy Constructor

Performs deep copy construction.

---

## Move Constructor

Transfers ownership without element duplication.

---

# Assignment Operators

## Copy Assignment

Performs deep-copy replacement.

---

## Move Assignment

Transfers ownership semantics.

---

# Element Access

## operator[]

Provides recursive dimensional access.

---

## data()

Returns pointer to contiguous storage.

---

# Iteration

## begin()

## end()

Provides STL-style traversal.

---

# Capacity & Dimensions

## size()

Returns current logical size.

---

## count()

Returns dimension-local count.

---

## total_count()

Returns total element count.

---

## getDimensions()

Returns dimensional metadata.

---
