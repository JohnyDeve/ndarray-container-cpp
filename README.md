<p align="center">
  <b>English</b> | <a href="./README.ru.md">Русский</a>
</p>

<p align="center">
  <img src="./readme_assets/NDArray-banner.png" alt="NDArray Banner" width="700">
</p>

<p align="center">

[![C++23](https://img.shields.io/badge/C%2B%2B-20-black?style=flat-square&logo=cplusplus)](https://en.cppreference.com/w/cpp/23)
[![License: MIT](https://img.shields.io/badge/License-MIT-black?style=flat-square)](https://opensource.org/license/mit)

[![CI](https://github.com/JohnyDeve/NDArray/actions/workflows/ci.yml/badge.svg)](https://github.com/JohnyDeve/NDArray/actions/workflows/ci.yml)
[![clang-format](https://img.shields.io/badge/clang--format-checked-black?style=flat-square)](https://clang.llvm.org/docs/ClangFormat.html)
[![GoogleTest](https://img.shields.io/badge/tests-googletest-black?style=flat-square)](https://github.com/google/googletest)

![Repo Size](https://img.shields.io/github/repo-size/JohnyDeve/NDArray?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/JohnyDeve/NDArray?style=flat-square)

</p>

---

# NDArray

Modern C++ header-only multidimensional contiguous container library focused on deterministic memory behavior, standards-oriented container semantics, and explicit low-level object lifetime management.

The project provides a multidimensional abstraction over contiguous storage while preserving predictable traversal, compile-time dimensionality, and STL-style container behavior.

Unlike abstraction-heavy numerical containers, NDArray prioritizes:

- explicit ownership semantics
- deterministic construction/destruction
- contiguous memory guarantees
- low-level allocation control
- constrained compile-time APIs
- iterator/view-based traversal

---

# Features

- Header-only multidimensional container
- Contiguous memory layout
- STL-style container semantics
- Recursive multidimensional initialization
- Custom iterator and view abstractions
- Const-correct multidimensional traversal
- Concepts/requires/SFINAE-constrained APIs
- Explicit manual object lifetime management
- GoogleTest-based validation pipeline
- GitHub Actions continuous integration
- clang-format verification

---

# Quick Example

```cpp
#include <NDArray.hpp>

NDArray<int, 2> matrix {
    {1, 2, 3},
    {4, 5, 6}
};

for (const auto& row : matrix) {
    for (const auto& value : row) {
        std::cout << value << ' ';
    }
}
```

---

# Build

## Configure

```bash
cmake -B build
```

## Build

```bash
cmake --build build
```

## Run Tests

```bash
ctest --test-dir build --output-on-failure
```

---

# Documentation

Detailed technical documentation is available in the `docs/` directory.

* [Architecture](./docs/architecture.md)
* [Memory Model](./docs/memory_model.md)
* [Iterators & Views](./docs/iterators_and_views.md)
* [Initialization](./docs/initialization.md)
* [API Reference](./docs/api_reference.md)
* [Testing & CI](./docs/testing_and_ci.md)

---

# License

MIT License.

See [LICENSE](./LICENSE) for details.

---

# Author

Ivan Kuzyakin

System Programmer · C/C++ · Low-Level Engineering


---