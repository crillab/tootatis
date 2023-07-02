---
layout: default
title: Utility
permalink: /utility/
registry: https://github.com/crillab/vcpkg-registry
---

<a class="btn btn-success tootatis-software-tutorial-btn" href="{{ page.registry }}"><i
            class="fas fa-folder fa-fw"></i>Browses packages</a>

The `vcpkg-registry` of `crillab` is a [`vcpkg` registry](https://vcpkg.io) of the C/C++ software developped at CRIL as well as the libraries on which they depend.

For using this registry you must add a `vcpkg-configuration.json` file at the root of your project. 

```json
{
  "$schema": "https://raw.githubusercontent.com/microsoft/vcpkg-tool/main/docs/vcpkg-configuration.schema.json", // ignore this line if you have already a vcpkg-configuration.json
  "registries": [
    {
      "kind": "git",
      "repository": "https://github.com/crillab/vcpkg-registry",
      "baseline": "84239a54fd9dc658f85ee982096521811692d9d9",
      "packages": [
        "crillab-*",
        "xcsp*"
      ]
    }
  ]
  // other registries.... 
}
```