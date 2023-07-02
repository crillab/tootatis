---
layout: software
title: Universe
badges:
    - img: https://img.shields.io/badge/License-LGPL%20v3-blue.svg
      url: https://www.gnu.org/licenses/lgpl-3.0.en.html
      alt: LGPL3
    - img: https://github.com/crillab/universe/actions/workflows/ci.yml/badge.svg
      url: https://github.com/crillab/universe/actions/workflows/ci.yml
      alt: CMake build
    - img: https://github.com/crillab/juniverse/actions/workflows/build-jar.yml/badge.svg
      url: https://github.com/crillab/juniverse/actions/workflows/build-jar.yml
      alt: Java Build
    - img: https://github.com/crillab/csuniverse/actions/workflows/ci.yml/badge.svg
      url: https://github.com/crillab/csuniverse/actions/workflows/ci.yml
      alt: CSharp Build
    - img: https://img.shields.io/nuget/v/Fr.UnivArtois.CRIL.CSUniverse
      url: https://www.nuget.org/packages/Fr.UnivArtois.CRIL.CSUniverse
      alt: nuget badge
permalink: /universe/
name_description: mUlti laNguage unIfied intErface foR conStraint solvErs
sources:
      - language: C++
      github_project: universe
      slug_name: cpp
      dependencies:
        - description: This library is designed for simplified use in projects using `CMake` and [`vcpkg`](https://vcpkg.io/en/) (with vcpkg_root is the path to your vcpkg install folder. ) 
          type: bash
          code: |
            git clone https://github.com/crillab/universe
            cd universe 
            cmake -S . -B build -D -DCMAKE_TOOLCHAIN_FILE=<vcpkg_root>/scripts/buildsystems/vcpkg.cmake"
            cmake --build build
        - description: You can also used vcpkg for integrate universe to your project. We assume that you have configured the registry of `crillab`, see [here](/utility) for more information. Add `crillab-universe` in your `vcpkg.json` file.
          type: json
          code: |
            "dependencies": [
                "crillab-universe"
                .....
            ]
    - language: Java
      github_project: juniverse
      slug_name: java
      dependencies:
        - description: Maven
          type: xml
          code: |
              <dependency>
                <groupId>fr.cril</groupId>
                <artifactId>juniverse</artifactId>
                <version>0.2.13</version>
              </dependency>
        - description: Gradle
          type: gradle
          code: "implementation group: 'fr.cril', name:'juniverse', version: '0.2.13'"
    - language: C#
      github_project: CSUniverse
      slug_name: csharp
      dependencies:
        - type: bash
          code: dotnet add package Fr.UnivArtois.CRIL.CSUniverse
implementations: 
    - title: Aceurancetourix (<a href="https://github.com/xcsp3team/ace/">ACE</a>)
      name: Aceurancetourix
      github_project: aceurancetourix
    - title: Jolitorax (<a href="https://gitlab.ow2.org/sat4j/sat4j-csp-pb">Sat4j-CSP-PB</a>)
      name: Jolitorax
      url: https://gitlab.ow2.org/sat4j/sat4j-csp-pb/-/tree/juniverse?ref_type=heads
# publications:
#  - type: Technical Report
#    year: 2023
#    title: Universe
#    id: tr-2023-universe
#    abstract: >-
#     blablabla
#    bibtex: >-
#     blablabla
#    pdf: http://pdf.com
---


`UNIVERSE` library proposes generic interfaces for combinatorial problems solvers. 

- SAT Solver
- PB Solver
- XCSP Solver

These interfaces are described in the following diagrams :

![Solvers Interface](https://raw.githubusercontent.com/crillab/universe/main/doc/diagrams/solverinterface.svg){:.center}

`Universe` offers an interface for create Solver. This interface follows the factory design pattern and is described
in the following diagrams: 

![factory](https://raw.githubusercontent.com/crillab/universe/main/doc/diagrams/factory.svg)