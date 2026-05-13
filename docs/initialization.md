
# Recursive Initialization

NDArray supports recursive multidimensional initialization using nested initializer lists.

Example:

```cpp
NDArray<int, 2> matrix {
    {1, 2, 3},
    {4, 5, 6}
};
````

---

# Recursive Construction Model

Recursive initialization is implemented using nested dimensional construction semantics.

Simplified representation:

```cpp
std::initializer_list<NDArray<T, N - 1>>
```

This enables:

* recursive dimensional composition
* compile-time dimensional consistency
* natural multidimensional initialization syntax

---

# Dimensional Consistency

Initialization preserves:

* compile-time dimension count
* deterministic storage layout
* contiguous allocation semantics

The recursive model allows higher-dimensional arrays to be constructed from lower-dimensional NDArray instances.

---

# Why Recursive Initialization Matters

The implementation avoids runtime-shaped nested containers.

Instead, dimensionality is encoded directly into the type system.

This enables:

* stronger compile-time guarantees
* more predictable traversal
* safer multidimensional composition

---