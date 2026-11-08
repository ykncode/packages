# 📦 Yukinary (YKN) Official Package Registry

Official package repository and registry for the **Yukinary Programming Language** ecosystem.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE-MIT)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE-APACHE)
[![Compiler: Yukinary](https://img.shields.io/badge/Compiler-Yukinary-brightgreen)](https://github.com/ykncode/yukinary)

---

## 🚀 How to Use Packages in Your Project

Yukinary uses `yukinary.toml` to manage project dependencies. You can easily add packages hosted here directly:

### 1. Add via CLI
```powershell
# Add a package to your yukinary.toml
ykn add sayac
ykn add net/http
ykn add math
```

### 2. Manual Configuration (`yukinary.toml`)
```toml
[package]
name = "my_app"
version = "0.1.0"
main = "main.ykn"
output = "build/app.exe"

[dependencies]
sayac = { git = "https://github.com/ykncode/packages", path = "sayac" }
http = { git = "https://github.com/ykncode/packages", path = "net/http" }
math = { git = "https://github.com/ykncode/packages", path = "math" }
sha256 = { git = "https://github.com/ykncode/packages", path = "crypto/sha256" }
json = { git = "https://github.com/ykncode/packages", path = "data/json" }
colors = { git = "https://github.com/ykncode/packages", path = "terminal/colors" }
```

### 3. Build & Run
```powershell
ykn build
```

The package manager resolves paths, prevents circular dependencies, verifies lockfiles (`yukinary.lock`), and compiles directly to native binaries.

---

## 📁 Repository Directory Structure

```text
packages/
├── registry.json             # Central registry metadata and version manifest
├── sayac/                    # Example stateful counter
│   ├── mod.ykn
│   └── yukinary.toml
├── math/                     # Extended arithmetic, clamp, min/max, powers
│   ├── mod.ykn
│   └── yukinary.toml
├── net/
│   └── http/                 # Native HTTP headers, status codes, and request models
│       ├── mod.ykn
│       └── yukinary.toml
├── crypto/
│   └── sha256/               # Hardware-accelerated SHA-256 primitives
│       ├── mod.ykn
│       └── yukinary.toml
├── data/
│   └── json/                 # JSON tokenization and key-value parser
│       ├── mod.ykn
│       └── yukinary.toml
└── terminal/
    └── colors/               # ANSI 256-color and terminal styling helpers
        ├── mod.ykn
        └── yukinary.toml
```

---

## 🛠️ Package Guidelines & Contributions

1. **Pure YKN Preferred:** Where possible, write packages in pure Yukinary for zero-overhead native execution.
2. **FFI Modules:** When interfacing with external C libraries, use `harici isv` and document runtime `.dll` / `.so` prerequisites.
3. **Semantic Versioning:** Follow `MAJOR.MINOR.PATCH` in `yukinary.toml`.

---

## 📜 License

Dual-licensed under either of:
* Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE))
* MIT license ([LICENSE-MIT](LICENSE-MIT))

at your option.
