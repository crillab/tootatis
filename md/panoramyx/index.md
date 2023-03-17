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
      github_project: panoramyx
      slug_name: cpp
      dependencies: 
        - description: This library is designed for simplified use in projects using CMake. To use this project, it is possible to create a sub-module in your project with the following commands
          type: bash
          code: |
            git submodule add https://github.com/crillab/panoramyx libs/panoramyx
            git submodule update --remote --recursive --init
        - description: And then add the following instructions in your CMakeLists.txt file
          type: cmake
          code: |
            add_subdirectory(libs/panoramyx)
            target_link_libraries(your_executable panoramyx)
#tutorial: tutorial.html
#technical_report: tutorial.html
---