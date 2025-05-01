---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
---


Constraint Programming (CP) is a powerful paradigm for solving complex combinatorial problems across a wide range of domains.  
Over the years, many solvers and tools have been developed, but their interoperability remains limited.

TOOTATIS addresses this challenge by offering a modular ecosystem that fosters integration, experimentation, and ease of use across different solvers, formats, and languages.

Initially centered around the **Universe** library, TOOTATIS has evolved to encompass a broader collection of complementary tools for modeling, solving, and analyzing constraint-based problems.


Our toolset includes solutions for:

- 📦 Solver installation and management
- 📊 Experimentation and performance analysis
- 🛠️ Solver configuration standardization
- 🔗 Integration with modern development environments (e.g., VSCode)


## 📚 Main Projects

### 🗂️ Configuration & Metadata 

- [**metrics-solvers**](https://github.com/crillab/metrics-solvers) — Predefined solver configurations ready for experimentation with metrics and xcsp-launcher.
- [**xcsp-metadata**](https://github.com/CPToolset/xcsp3-metadata) — Repository of instance metadata for the XCSP3 format.

### 🛠️ Tools

- [**xcsp-launcher**](/xcsp-launcher) — Unified installer, builder, and launcher for XCSP3-compatible solvers.

---

### 🌌 Universe — mUlti laNguage unIfied intErface foR conStraint solvErs

[A multi-language library](/universe) providing generic interfaces to interact with combinatorial problem solvers.

- [**Universe (C++)**](https://github.com/crillab/universe) — Unified C++ API for constraint programming solvers.
- [**Juniverse (Java)**](https://github.com/crillab/juniverse) — Java unified interface for solvers.
- [**CSUniverse (C#)**](https://github.com/crillab/CSUniverse) — C# implementation of the Universe API.

---

### 🧩 Parsing


- [**Autis**](/autis/) — A library for parsing combinatorial problems.


<!-- --- -->

<!-- ### 🖋️ IDE 

- [**xcsp-vscode**](/ide) — VSCode extension for modeling constraint problems with [PyCSP3](https://pycsp.org). -->

---

### ⚡ Parallel Solving

- [**Panoramyx**](/panoramyx) — A C++ framework for solving constraint programming problems in parallel.  
  *(Built on top of the Universe C++ library.)*



