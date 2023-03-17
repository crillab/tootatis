---
layout: software
title: Universe
badges:
    - img: https://img.shields.io/badge/License-LGPL%20v3-blue.svg
      url: https://www.gnu.org/licenses/lgpl-3.0.en.html
      alt: LGPL3
    - img: https://github.com/crillab/universe/actions/workflows/cmake.yml/badge.svg
      url: https://github.com/crillab/universe/actions/workflows/cmake.yml
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
        - description: This library is designed for simplified use in projects using CMake. To use this project, it is possible to create a sub-module in your project with the following commands
          type: bash
          code: |
            git submodule add https://github.com/crillab/universe libs/universe
            git submodule update --remote --recursive --init
        - description: And then add the following instructions in your CMakeLists.txt file
          type: cmake
          code: |
            add_subdirectory(libs/universe)
            target_link_libraries(your_executable universe)
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
                <version>0.1.16</version>
              </dependency>
        - description: Gradle
          type: gradle
          code: "implementation group: 'fr.cril', name:'juniverse', version: '0.1.16'"
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