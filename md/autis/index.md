---
layout: software
title: Autis
permalink: /autis/
name_description: A library for parsing combinatorial problems
badges:
    - img: https://img.shields.io/badge/License-LGPL%20v3-blue.svg
      url: https://www.gnu.org/licenses/lgpl-3.0.en.html
      alt: LGPL3
    - img: https://github.com/crillab/autis/actions/workflows/ci.yml/badge.svg
      url: https://github.com/crillab/autis/actions/workflows/ci.yml
      alt: CMake build
sources:
    - language: C++
      github_project: autis
      slug_name: cpp
      dependencies:
        - description: This library is designed for simplified use in projects using `CMake` and [`vcpkg`](https://vcpkg.io/en/) (with vcpkg_root is the path to your vcpkg install folder. ) 
          type: bash
          code: |
            git clone https://github.com/crillab/autis
            cd autis 
            cmake -S . -B build -DCMAKE_TOOLCHAIN_FILE=<vcpkg_root>/scripts/buildsystems/vcpkg.cmake"
            cmake --build build
        - description: You can also used vcpkg for integrate autis to your project. We assume that you have configured the registry of `crillab`, see [here](/utility) for more information. Add `crillab-autis` in your `vcpkg.json` file.
          type: json
          code: |
            "dependencies": [
                "crillab-autis"
                .....
            ]
---


## Description 

`AUTIS` library allows parsing combinatorial problem instances for different common formats. 
Currently, the following are supported:

- [Dimacs CNF](https://people.sc.fsu.edu/~jburkardt/data/cnf/cnf.html)
- [OPB](http://www.cril.univ-artois.fr/PB16/format.pdf) 
- [XCSP3](https://xcsp.org) based on the [XCSP3-CPP-PARSER](https://github.com/xcsp3team/XCSP3-CPP-Parser)

`AUTIS` can feed any solver implementing [the Universe interface](/universe).


## Examples 

For each of these examples, we consider that you have your own implementation of the `ISolverFactory` interface 
from the [Universe library](/universe). 

> The paths to the .h files must be adapted.

### Dimacs CNF

If you want to parse a CNF file like [this one](https://github.com/crillab/autis/blob/main/examples/example.cnf), you may use something similar
to the following example.

```c++
#include <string>
#include <iostream>
#include "../libs/universe/universe/include/utils/ISolverFactory.hpp"
#include "../autis/core/parser.h"

int main(){
    std::string path ="examples/example.cnf";
    Universe::ISolverFactory* factory= new YourFactoryImplementation();
    auto solver = Autis::parse(path,*factory);
    auto result = solver->solve();
    auto solution = solver->solution();
    switch(result){
        case Universe::UniverseSolverResult::SATISFIABLE:
            auto solution = solver->solution();
            std::cout<<"SATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSATISFIABLE:
            std::cout<<"UNSATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNKNOWN:
            std::cout<<"UNKNOWN"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSUPPORTED:
            std::cout<<"UNSUPPORTED"<<std::endl;
            break;
    }
    return 0;
}
```

### OPB 

If you want to parse an OPB file like [this one](https://github.com/crillab/autis/blob/main/examples/example.opb), you may use something similar
to the following example.

```c++
#include <string>
#include <iostream>
#include "../libs/universe/universe/include/utils/ISolverFactory.hpp"
#include "../autis/core/parser.h"

int main(){
    std::string path ="examples/example.opb";
    Universe::ISolverFactory* factory= new YourFactoryImplementation();
    auto solver = Autis::parse(path,*factory);
    auto result = solver->solve();
    auto solution = solver->solution();
    switch(result){
        case Universe::UniverseSolverResult::SATISFIABLE:
            auto solution = solver->solution();
            std::cout<<"SATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSATISFIABLE:
            std::cout<<"UNSATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNKNOWN:
            std::cout<<"UNKNOWN"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSUPPORTED:
            std::cout<<"UNSUPPORTED"<<std::endl;
            break;
        case Universe::UniverseSolverResult::OPTIMUM_FOUND:
            auto solution = solver->solution();
            std::cout<<"OPTIMUM_FOUND"<<std::endl;
            break;
    }
    return 0;
}
```

### XCSP

If you want to parse an XCSP3 file like [this one](https://github.com/crillab/autis/blob/main/examples/example.xml), you may use something similar
to the following example.
```c++
#include <string>
#include <iostream>
#include "../libs/universe/universe/include/utils/ISolverFactory.hpp"
#include "../autis/core/parser.h"

int main(){
    std::string path ="examples/example.xml";
    Universe::ISolverFactory* factory= new YourFactoryImplementation();
    auto solver = Autis::parse(path,*factory);
    auto result = solver->solve();

    switch(result){
        case Universe::UniverseSolverResult::SATISFIABLE:
            auto solution = solver->solution();
            std::cout<<"SATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSATISFIABLE:
            std::cout<<"UNSATISFIABLE"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNKNOWN:
            std::cout<<"UNKNOWN"<<std::endl;
            break;
        case Universe::UniverseSolverResult::UNSUPPORTED:
            std::cout<<"UNSUPPORTED"<<std::endl;
            break;
        case Universe::UniverseSolverResult::OPTIMUM_FOUND:
            auto solution = solver->solution();
            std::cout<<"OPTIMUM_FOUND"<<std::endl;
            break;
    }
    return 0;
}
```
