# State Pattern

## Problem
- An object's behavior changes depending on its internal state.
- Repeated state-based conditionals make the code difficult to maintain.

## Core Idea
- Represent each state as a separate object.
- Delegate behavior to the current state object.
- Allow state objects to control transitions when appropriate.

## Participants
- Context: Holds the current state and delegates behavior.
- State: Defines the common interface.
- Concrete States: Implement state-specific behavior.

## Recognition Questions
- Does behavior depend on the object's current state?
- Are there repeated if-else checks based on state?
- Can each state's behavior be isolated?

## SOLID Principles
- SRP: Each state encapsulates one state's behavior.
- OCP: Add new states without changing existing ones.
- DIP: Context depends on the State abstraction.
- LSP: Any concrete state can replace another.

## Comparison
- Strategy: Client chooses one of many algorithms.
- Command: Represents an action as an object.
- State: Object changes behavior as its internal state changes.

Key Insight
- State removes state-specific conditionals by turning each state into an object.
