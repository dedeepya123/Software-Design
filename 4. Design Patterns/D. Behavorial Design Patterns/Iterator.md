# Iterator Pattern

## Problem
- Clients need to traverse a collection without depending on its internal representation.

## Core Idea
- Separate traversal logic from the collection.
- Provide an iterator object that manages traversal state.

## Participants
- Collection: Stores the data.
- Iterator: Provides sequential access to elements.

## Recognition Questions
- Should clients be independent of the collection's storage?
- Are multiple traversal orders needed?
- Can traversal state be separated from the collection?

## SOLID Principles
- SRP: Collection stores data; iterator traverses it.
- OCP: Add new traversal methods by creating new iterators.
- DIP: Clients depend on the iterator abstraction.

## Comparison
- Composite: Organizes hierarchical structures.
- Strategy: Chooses among algorithms.
- Iterator: Encapsulates traversal of a collection.

## Key Insight
- Iterator lets clients access elements one by one without exposing how the collection is implemented.
