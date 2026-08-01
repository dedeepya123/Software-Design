# Template Method Pattern

## Problem
- Multiple classes follow the same overall algorithm, but a few steps differ.
- Copying the entire algorithm leads to duplication.

## Core Idea
- Define the algorithm skeleton once in a base class.
- Let subclasses implement or override only the varying steps.

## Participants
- Abstract Base Class: Defines the template method (algorithm skeleton).
- Concrete Subclasses: Customize specific steps.

## Recognition Questions
- Is the workflow largely identical across classes?
- Are only a few steps different?
- Is there duplicated algorithm structure?

## SOLID Principles
- SRP: Base class manages workflow; subclasses manage variations.
- OCP: Add new variations by creating new subclasses.
- LSP: Any subclass follows the same overall algorithm.

## Comparison
- Strategy: Replace the entire algorithm.
- Template Method: Keep the algorithm structure and customize selected steps.

## Key Insight
- Separate the invariant structure of an algorithm from its variable steps.
