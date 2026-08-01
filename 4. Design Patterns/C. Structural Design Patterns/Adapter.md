# Adapter Pattern

## Problem
- Two classes provide compatible behaviour but expose incompatible interfaces.
- We cannot or should not modify either class.

## Core Idea
- Introduce an adapter that translates one interface into another expected by the client.

## Recognition Questions
- Are two interfaces incompatible?
- Is there a wrapper translating method calls?
- Is a third-party or legacy API being integrated?
- Does the client continue using its original abstraction?

## SOLID Principles
- DIP: Client depends on an abstraction, not the third-party implementation.
- OCP: New adapters can be added without changing client code.
- SRP: Translation logic lives in the adapter.
- LSP: The adapter can be used wherever the expected abstraction is required.

## Python Structure
``` text
Client
    ↓
Expected Interface
    ↓
Adapter
    ↓
Third-party Class
```
## Key Insight
- Adapter does not change behaviour.
- It changes how behaviour is accessed by translating between interfaces.
