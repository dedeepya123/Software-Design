# Coupling

## Definition
- Coupling is the degree to which one module depends on another.

## Key Insight
- Dependencies are necessary.
- The goal is not to eliminate dependencies but to manage them carefully.

## Tight Coupling
- Modules know too much about each other's implementation.
- Changes ripple across the system.
- Harder to test, reuse, and maintain.

## Loose Coupling
- Modules depend only on well-defined behaviour, not internal implementation.
- Internal changes have minimal impact on other modules.
- Easier to extend, test, and maintain.

## Mental Model
- Every dependency is a promise that changes in one module may affect another.
- Good software minimises unnecessary knowledge between modules while allowing necessary collaboration.
