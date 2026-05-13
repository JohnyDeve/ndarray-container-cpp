# Memory Model

NDArray uses explicit low-level object lifetime management instead of delegating construction semantics to higher-level container abstractions.

---

# Allocation Strategy

The implementation allocates raw memory for the storage region and manually constructs objects using placement new.

Construction follows a deterministic sequential initialization model.

Simplified construction logic:

```cpp
for (const auto& elem : source) {
    new (&data_[cnt_constructed++]) value_type(elem);
}
```

This approach allows:

* explicit construction ordering
* precise lifetime control
* exception-safe rollback
* partial construction cleanup

---

# Exception Safety

If object construction throws during initialization:

* already-constructed elements are destroyed manually
* allocated memory is released
* ownership state remains valid

This prevents:

* partially initialized storage leaks
* undefined ownership states
* inconsistent destruction order

---

# Why Placement New Is Used

The project intentionally separates:

* raw memory allocation
* object construction
* object destruction
* memory deallocation

This provides behavior similar to allocator-oriented STL implementations.

---

# Ownership Model

NDArray fully owns its memory.

The implementation guarantees:

* deterministic destruction
* contiguous storage
* explicit object lifetime
* predictable traversal semantics

---