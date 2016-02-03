---
title: Schedule and Syllabus
layout: default
---

## Weekly Schedule

Mondays 2.30pm - 5pm Lecture and Lab. (Both compulsory) Pierce 301

Wednesdays 2.30pm - 4.30pm (Lecture Compulsory, lab highly recommended) Pierce 301

Fridays 11am-1pm (Lecture Compulsory, lab highly recommended) Pierce 301

Monday Labs are compulsory: we'll be doing group meetings then. Wed and Fri labs are highly recommended. The benefit is that with attendance you will at-most have 1/2 hour to 1 hour additional lab work at home.

## Syllabus by week

| Week    | Monday: Systems and Software Engineering | Wednesday: Language                      | Friday: Data Structures and Algorithms   | @home                                    |
| ------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| J25     | [Introduction and logistics](https://github.com/iacs-cs207/cs207/blob/master/lectures/introduction.pdf)               | [Execution model](https://github.com/iacs-cs207/cs207/blob/master/lectures/Execution.ipynb)                          | [Basic algorithms](https://github.com/iacs-cs207/cs207/blob/master/lectures/BasicAlgorithms.ipynb)                        |                                          |
| J25 lab | Lab 1: [Ipynb](https://github.com/iacs-cs207/cs207/blob/master/labs/Lab1.ipynb), [Submit](http://goo.gl/forms/dWWN3zg0wO) | Lab 2: [Frames and Decorators](https://github.com/iacs-cs207/cs207/blob/master/labs/distribute_ExecutionLab.ipynb), [Submit](http://goo.gl/forms/Fyv2PLiJdw) (R)         | Lab 3: [Fibonacci multiple ways](https://github.com/iacs-cs207/cs207/blob/master/labs/distribute_BasicAlgorithmsLab.ipynb), [Submit](http://goo.gl/forms/bLxVGakPLd) (R)       |                                          |
| F01     | [Introduction to C](https://iacs-cs207.github.io/cs207/lectures/f01.html)                        | [Objects](https://github.com/iacs-cs207/cs207/blob/master/lectures/Objects.ipynb)                                  | Lists                                    |                                          |
| F01 lab | Lab 4: [Introduction to C](https://iacs-cs207.github.io/cs207/lectures/f01-lab.html) [Submit](http://goo.gl/forms/LiCRca9CIs) (R)                             | [Lab 5: Time Series Data](https://github.com/iacs-cs207/cs207/blob/master/labs/distribute_ObjectsLab.ipynb)                  | Lab 6: Linked lists (R)                  | Req: basic classes                       |
| F08     | Software engineering basics              | Python sequences                         | Hashing                                  |                                          |
| F02 lab | Lab 7: Documentation                     | Lab 8: Arrays and performance            | Lab 9: Hashing (R)                       | Req: tests and numpy                     |
| F15     | HOLIDAY                                | Programming paradigms                    | Numerical methods                        |                                          |
| F15 lab | HOLIDAY        | Lab 11: Smart interfaces                 | Lab 12: Softmax (R)                      | Req: ts module, simple algorithms        |
| F22     | Testing                                  | Iterators and generators                 | Trees and search                         |                                          |
| F22 lab | Lab 13: Test-driven development          | Lab 14: Online outlier detection         | Lab 15: Trees (R)                        | Req: unit tests, online algorithms       |
| F29     | coverage/ci/refactor                     | operator overloading, obj model, (use bitvectors) | heaps, sort and search, tim-sort         |                                          |
| F29 lab | setup CI, refactor to generators, check CI@home | add ops between TS using operator overloading and multimethods(do synthetic) | multi dispatch TS sort .                 | add between-time series ops including distance |
| M07     | CLIs and setup.py                        | DSLs and ASTs                            | Metadata and Query Languages             |                                          |
| M07 lab | pip, make package                        | start repl for tsdb@home                 | enhance dsl with metadata selection from dicts | add simple query repl on db              |

Milestone 1 evaluation and spring break.

| Week    | Monday: Systems and Software Engineering | Wednesday: Language                      | Friday: Data Structures and Algorithms   | @home                                 |
| ------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ------------------------------------- |
| M21     | DataRepresentation: serialization and Cython | Cython and C API, memproto, fast seq lab | Indexing: dbases/btrees, LSM Trees.      |                                       |
| M21 lab | write simple dbase protocol              | implement a time series based on some c library and list of structs format | implement 2 level external storage for time series | convert dbase to btree dbase          |
| M28     | profiling+perf analysis                  | Cython and numpy with algo in C: speed up | kNN numericals                           |                                       |
| M28 lab | implement knn python and profile(R)      | knn in Cython and numpy (do a sklearn cython implementation)(R) | knn with a faster algorithm still exported to py (perhaps in py only) | implement some KNN numericals         |
| A04     | unix: fd, sockets                        | Concurrency (asyncio or threads) multiprocess? | rtree/vptree                             |                                       |
| A04 lab | split REPL                               | multiple sockets handler with asyncio/threads/multiprocess(R) | rtree/vptree (R)                         | add to meta/index a vptree for kNN db |
| A11     | PROJECT SCOPE/EXTRAS or GUEST: julia     | Functional vs non-functional for concurrency (mutablility,immutability, Monads, CG) | optimizing CG, graph based scheduler, dask |                                       |
| A11 lab | get set on after-class project scope     | take your query language and construct a computational graph | optimize the graph                       | add computational graph to db         |

Milestone 2 evaluation.

| Week | Monday: Systems and Software Engineering | Wednesday: Language   | Friday: Data Structures and Algorithms   | @home |
| ---- | ---------------------------------------- | --------------------- | ---------------------------------------- | ----- |
| A18  | DTW  numericals                          | GUEST (dbases)        | FFT and its optimization(whole lecture: guest) |       |
| A25  | Project work                             |                       |                                          |       |
| M02  | Project work                             |                       |                                          |       |
| M09  | Project due                              | Project presentations | Project grades                           |       |
