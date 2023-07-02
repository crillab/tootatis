---
layout: software
title: Panoramyx
name_description: Programming pArallel coNstraint sOlveRs mAde aMazingly easY
permalink: /panoramyx/
description: >-
    blablabla
badges:
    - img: https://img.shields.io/badge/License-LGPL%20v3-blue.svg
      url: https://www.gnu.org/licenses/lgpl-3.0.en.html
      alt: LGPL3
sources:
    - language: C++
      github_project: autis
      slug_name: cpp
      dependencies:
        - description: This library is designed for simplified use in projects using `CMake` and [`vcpkg`](https://vcpkg.io/en/) (with vcpkg_root is the path to your vcpkg install folder.) 
          type: bash
          code: |
            git clone https://github.com/crillab/panoramyx
            cd panoramyx 
            cmake -S . -B build -D -DCMAKE_TOOLCHAIN_FILE=<vcpkg_root>/scripts/buildsystems/vcpkg.cmake"
            cmake --build build
        - description: You can also used vcpkg for integrate panoramyx to your project. We assume that you have configured the registry of `crillab`, see [here](https://crillab.github.io/tootatis/utility) for more information. Add `crillab-panoramyx` in your `vcpkg.json` file.
          type: json
          code: |
            "dependencies": [
                "crillab-panoramyx"
                .....
            ]
tutorial: tutorial
---

Panoramyx is a `C++` framework for solving constraint programming problems in parallel. 
