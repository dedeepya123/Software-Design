# Why Object Creation Becomes a Design Problem

## Core Idea
- Object creation is not always a simple constructor call.
- As systems grow, creating objects becomes a design concern.

## Why Creation Becomes Complex
- Construction logic becomes lengthy.
- Multiple implementations may exist.
- Initialisation order matters.
- Objects may be expensive to create.
- Different objects have different lifecycles.

## Key Design Questions
1. Who should create the object?
2. Is construction simple or complex?
3. Will the implementation change?
4. How many instances should exist?

## Creational Pattern Decision Tree
- One shared instance? → Singleton
- Delegate creation? → Factory Method
- Create related families? → Abstract Factory
- Complex step-by-step construction? → Builder
- Clone an existing object? → Prototype

## Key Insight
- Constructors create objects.
- Creational patterns manage the responsibility of object creation.
