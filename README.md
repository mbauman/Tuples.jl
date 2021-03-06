# Tuples

[![Build Status](https://travis-ci.org/mbauman/Tuples.jl.svg?branch=master)](https://travis-ci.org/mbauman/Tuples.jl) [![Coverage Status](https://coveralls.io/repos/mbauman/Tuples.jl/badge.svg)](https://coveralls.io/r/mbauman/Tuples.jl)

This package explores an interface to work with `Tuple{}`s.  See
https://github.com/JuliaLang/julia/pull/11547

It provides the following methods to work with Tuples as though they are containers of their parameters.  It does not export these methods as they would clash with the Base methods of the same name.  As such, they must be called fully-qualified with the module name.

* `Tuples.length(T)`: The number of component types in a Tuple T.
* `Tuples.collect(T)`: Returns the component types inside the Tuple T as an iterable container
* `Tuples.getindex(T, i::Integer)`: Returns the i-th component of the Tuple T
* `Tuples.getindex(T, Is)`: Returns an iterable container with each element set to the i-th component, for each i in Is.

Additionally, it provides a convenience method for constructing Tuple types by calling `NTuple`, akin to the base method `ntuple`:

* `NTuple(f, n::Integer)`: Construct a Tuple{} such that the i-th component is the result of f(i).
