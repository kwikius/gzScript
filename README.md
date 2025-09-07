# gzScript
A language proposal for a domain-specific language for Gazebo models, units, and simulation scripting, as an alternative to xml

Overview
--------
gzScript is an experimental DSL (domain-specific language) designed to make working with Gazebo Sim easier and more intuitive. 

gzScript aims to provide:

* Strongly typed quantities and units (SI-first, safe conversions).

* A clean syntax for describing models, poses, joints, and animations.

* An approachable scripting language for simulation experiments.

* A foundation for higher-level workflows (model design, control, testing).

Why?
----
Gazebo is powerful, but SDF and plugin code can be verbose and error-prone.
gzScript explores whether we can design a friendlier layer on top, without losing rigor.

Goals:

Reduce boilerplate.

Prevent unit errors.

Enable “sketching” of simulation ideas quickly.

Stay interoperable with Gazebo ecosystem.

Example primitives 
------------------
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
Features (planned)
- Core principles for units & quantities
- Parser / grammar draft (Bison/Flex)
- Interpreter / compiler backend
- Gazebo integration (generate SDF / send commands)
- Example models and control scripts
