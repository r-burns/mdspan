Reference `mdspan` implementation
==========================================

The ISO-C++ proposal [P0009](https://wg21.link/p0009) will add support for non-owning multi-dimensional array references to the C++ standard library.  This repository aims to provide a production-quality implementation of the proposal as written (with a few caveats, see below) in preparation for the addition of `mdspan` to the standard.  Please feel free to use this, file bugs when it breaks, and let us know how it works for you :-)

[Try it out on Godbolt](https://godbolt.org/z/ehErvsTce){: .btn }

Using `mdspan`
--------------

A [tutorial-style introduction](https://github.com/kokkos/mdspan/wiki/A-Gentle-Introduction-to-mdspan) to the basic usage of `mdspan` is provided on the project wiki.  More advanced tutorials to come.

Features in Addition To C++ Standard
------------------------------------

- C++17 backport (e.g., concepts not required)
- C++14 backport (e.g., fold expressions not required)
  - Compile times of this backport will be substantially slower than the C++17 version
- C++11 backport
  - Compile times of this backport will be substantially slower than the C++14 backport
- Macros to enable, e.g., `__device__` marking of all functions for CUDA compatibility

Building and Installation
-------------------------

This implementation is header-only, with compiler features detected using feature test macros, so you can just use it directly with no building or installation.  If you would like to run the included tests or benchmarks, you'll need CMake.

### Running tests

TODO write this

### Running benchmarks

TODO write this

Caveats
-------

This implementation is fully conforming with a few exceptions (most of which are extensions):

- the `layout_stride` mapping comparison operators work as expected, rather than the (typo) specification in the proposal

Acknowledgements
================

This work was undertaken as part of the [Kokkos project](https://github.com/kokkos/kokkos) at Sandia National Laboratories.  Sandia National Laboratories is a multimission laboratory managed and operated by National Technology & Engineering Solutions of Sandia, LLC, a wholly owned subsidary of Honeywell International Inc., for the U. S. Department of Energy's National Nuclear Security Administration under contract DE-NA0003525.

