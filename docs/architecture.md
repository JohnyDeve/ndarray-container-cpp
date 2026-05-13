# Architecture

NDArray is implemented as a header-only multidimensional container designed around contiguous storage semantics and deterministic ownership behavior.

The library provides:

- compile-time dimensionality
- recursive multidimensional traversal
- contiguous memory guarantees
- explicit object lifetime management
- STL-oriented iterator semantics

The implementation intentionally avoids runtime-polymorphic container abstractions and instead relies on:

- template specialization
- compile-time dimensional recursion
- constrained generic APIs
- zero-overhead iterator/view abstractions

---

# Design Goals

The primary design goals of the project are:

## Predictable Memory Layout

All elements are stored inside a contiguous memory block.

This enables:

- cache-friendly traversal
- deterministic iteration
- compatibility with low-level algorithms
- explicit pointer arithmetic

---

## Compile-Time Dimensionality

Dimensionality is encoded in the type:

```cpp
NDArray<int, 2>
NDArray<float, 3>
````

This removes runtime dimension ambiguity and allows compile-time API constraints.

---

## Explicit Ownership Semantics

The container owns its storage and manually manages object lifetime.

The implementation prioritizes deterministic destruction and exception-safe partial construction rollback.

---

## STL-Oriented Semantics

The container API follows common STL conventions:

* iterators
* begin/end traversal
* contiguous storage access
* const-correct APIs
* predictable traversal behavior

---