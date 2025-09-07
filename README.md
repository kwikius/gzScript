# gzScript

*A domain-specific language for [Gazebo](https://gazebosim.org) models, units, and simulation scripting.*

---

## Overview

`gzScript` is an experimental DSL (domain-specific language) designed to make working with **[Gazebo](https://gazebosim.org)** easier and more intuitive. `gzScript` aims to provide:

* Strongly typed **quantities and units** (SI-first, safe conversions).
* A clean syntax for describing **models, poses, joints, and animations**.
* An approachable scripting language for simulation experiments.
* A foundation for higher-level workflows (model design, control, testing).

---

## Why?

Gazebo is powerful, but **SDF and plugin code** can be verbose and error-prone.
`gzScript` explores whether we can design a friendlier layer on top, without losing rigor.

Goals:

* Reduce boilerplate.
* Prevent unit errors.
* Enable “sketching” of simulation ideas quickly.
* Stay interoperable with Gazebo ecosystem.

---

## Physical quantities and units
First things first. To model physical systems legibly requires strongly typed physical quantities. Work has been ongoing, notably in C++, for example in 
[pqs](https://github.com/kwikius/pqs), [quan](https://github.com/kwikius/quan-trunk) and [mp-units](https://github.com/mpusz/units), to 
provide a semantic for representing physical quanties in an expressive way.  
gzScript provides an opportunity to enshrine physical quantities in the language itself. 

```
// Declare a unit alias
mph = :mi/h:;

// Quantities
v = 5:m/s:;
t = 2:s:;
d = v * t;      // 10:m:

// Refined quantities
h:height: = 1.2:m:;
w:width:  = 0.3:m:;

// Angle handling
theta = 180:deg:;
phi   = 3.14:rad:;
```

---

## Features (planned)

* [x] Core principles for **units & quantities**
* [ ] Parser / grammar draft (Bison/Flex)
* [ ] Interpreter / compiler backend
* [ ] Gazebo integration (generate SDF / send commands)
* [ ] Example models and control scripts

---

## Status

**Work in progress.** This project is currently in early design stages.
Contributions, ideas, and discussions are welcome.

---

## Related Work

* [Gazebo](https://gazebosim.org)
* [mp-units](https://github.com/mpusz/units)
* [pqs](https://github.com/kwikius/pqs)

---

## License

TBD (MIT or Apache-2.0 recommended).

---
