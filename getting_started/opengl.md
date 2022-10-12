# OpenGL
- opengl is not an API; rather a specification
- then who's implementing such a specification?: the graphics card manufactureres

## Core-profile vs Immediate mode
- skim through this part

## Extensions
- opengl supports extensions
  - each extension is implemented in the drivers, and HW must support it if it is to be run on that HW
  - some popular extensions become parts of future opengl versions

## State machine
- opengl is itself a large state machine
- **state machine**: a collection of variables that define how opengl should currently operate
  - opengl **context**: the state of opengl
  - we change the state, and then opengl renders based on the current state that has changed

- **state-changing** functions: changes the context
- **state-using** functions: performs operations based on the current state of opengl

## Objects
- the opengl libraries are basically written in C
- **object**: a collection of options that represents a subset of opengl's state

- a typical workflow
1. create an (general)object, and store a reference to it as an id
2. bind the object(using the id) to the target location of the context
3. set the options
  - the options set are stored in the object referenced by the object id
  - can be restored if we rebind the object back to the target
4. unbind the object by setting the current object id of the target to 0

- we can define more than one objects, so that we don't have to redefine options everytime we render

