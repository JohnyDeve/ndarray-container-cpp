
# Iterators & Views

NDArray implements a dedicated multidimensional traversal system based on reusable iterator/view abstractions.

---

# General View Abstraction

Traversal behavior is centralized inside:

```cpp
template<typename T, size_t N, bool IsConstClass>
class GeneralNDArrayView;
```

This abstraction provides the foundation for:

* mutable multidimensional views
* const multidimensional views
* recursive dimensional traversal
* iterator-compatible navigation

---

# NDArrayView

`NDArrayView` provides mutable access to multidimensional subregions.

Characteristics:

* lightweight abstraction
* non-owning traversal interface
* recursive dimensional access
* contiguous traversal semantics

---

# NDArrayConstView

`NDArrayConstView` provides const-correct traversal behavior.

The implementation shares the same generalized traversal model while restricting mutation.

---

# Traversal Model

Traversal recursively descends through dimensions while preserving contiguous storage guarantees.

Example:

```cpp
for (const auto& row : matrix) {
    for (const auto& value : row) {
        std::cout << value << ' ';
    }
}
```

---

# Design Motivation

The view system exists to:

* avoid duplicated traversal logic
* preserve const correctness
* centralize iterator semantics
* minimize abstraction overhead

---