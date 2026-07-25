# Encapsulation

## Definition
- Encapsulation is the practice of keeping an object's state and the behaviour that operates on that state together, while controlling how the state is accessed and modified.

## State
- State is the data representing the current condition of an object.

## Purpose
- Protect the object's correctness.
- Prevent invalid state.
- Keep business rules inside the object.

## Invariant
- An invariant is a condition that must always remain true for an object to remain valid.
- Encapsulation helps preserve invariants.

## Abstraction vs Encapsulation
- Abstraction: Defines what behaviour is exposed.
- Encapsulation: Protects how behaviour and state are implemented.

## Key Insight
- Encapsulation is not about making data private.
- It is about ensuring that an object's state changes only through valid operations.

## Mental Model
- Restaurant:
  - Menu = Abstraction (what you can request).
  - Kitchen = Encapsulation (how it is prepared and protected).
