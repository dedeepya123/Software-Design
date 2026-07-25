# Question 1

## So the building blocks of software are classes and objects?

Almost. Let's make it more precise.

There are two levels.

- Design Level

When you're writing code, you define:

Modules/packages
Classes
Functions
Interfaces (or abstract base classes/protocols in Python)

These are your design-time building blocks.

Runtime Level

When the program executes, what actually exists?

Objects
Function calls
Data
Threads/processes (if applicable)

The objects are what actually collaborate to solve the problem.

So I would say:

Classes are design-time blueprints. Objects are the runtime building blocks of an object-oriented system.

This is why experienced engineers think more about objects than classes.

# Question 2 How they should be organised and communicate is where concepts like encapsulation, cohesion, modularity come?


Exactly.

Think of Phase 0 as the laws of good design.
``` text
Objects exist.
↓
How should they be organised?
→ Modularity
↓
How focused should each object be?
→ Cohesion
↓
How much should they know about each other?
→ Coupling
↓
What should they expose?
→ Abstraction
↓
How should they protect their state?
→ Encapsulation
↓
How should they survive future changes?
→ Managing Change
```
Notice these are principles, not language features.

## Question 3 How objects interact or relate is where relationships come?
``` text
Relationships answer:

How are these objects connected?

Examples

Customer
      │
places
      │
Order
Car
     │
uses
     │
Engine
Hospital
        │
employs
        │
Doctor

Relationships describe the structure of the collaboration.
```

## Question 4 Aggregation and all we don't use? We only use inheritance and composition?

This is one place where many books create confusion.

The short answer is:

No. We absolutely use association, aggregation, dependency, and composition.

The important point is that they are not alternatives to each other in the same way inheritance and composition are.

Let's organise them properly.

Relationships

Think of "relationship" as the umbrella term.
``` text
Relationships

├── Dependency
├── Association
├── Aggregation
├── Composition
└── Inheritance
```
These describe different kinds of connections.

### Dependency

"I temporarily use you."

printer.print(document)

The printer doesn't own the document.

### Association

"I know about you."

Doctor ←→ Patient

They are related.

Neither owns the other.

### Aggregation

"I contain you, but you can live without me."
``` text
Team

↓

Players
```
If the team disappears,

the players still exist.

### Composition

"I own you."
``` text
House

↓

Rooms

The parts belong to the whole.
```
### Inheritance

"I am a specialised version of you."
``` text
Dog

↓

Animal

Notice inheritance is a different kind of relationship because it models type specialisation, not ownership.
```

### Question 5 If one entity is using another entity then it's composition, right?

Not always. This is a very important distinction.

The word "uses" is too broad.

Let's see the different possibilities.

#### Case 1 — Temporary Use (Dependency)
``` text
class Printer:
    def print(self, document):
        ...
The printer receives a document,

prints it,

and forgets it.

It doesn't store it.

This is dependency, not composition.
```
#### Case 2 — Keeps a Reference (Association)
``` text
class Order:
    def __init__(self, customer):
        self.customer = customer

The order knows its customer.

The customer exists independently.

This is association.
```
#### Case 3 — Whole-Part with Independent Lifetime (Aggregation)
Team

↓

Players

Players can join another team.

The team doesn't own their existence.

#### Case 4 — Strong Ownership (Composition)
``` text
class Car:
    def __init__(self):
        self.engine = Engine()
```
Here, the car creates and owns its engine.

The engine is considered part of that car.

This is composition.

### A Better Way to Decide

Instead of asking:

"Is A using B?"
``` text
Ask these questions:

1. Does A merely use B for a task?

→ Dependency

2. Does A know B exists?

→ Association

3. Does A contain B, but B can exist independently?

→ Aggregation

4. Does A own B's lifetime?

→ Composition

5. Is A a specialised form of B?

→ Inheritance
```
One More Important Point

**In practice, many programming languages (including Python) do not have special syntax for aggregation.**

For example:
``` text
class Team:
    def __init__(self, players):
        self.players = players

This could represent aggregation—or composition—depending on the design intent.

That's why many developers don't explicitly say "this is aggregation." They simply reason about ownership and lifetime.

By contrast, inheritance (class Dog(Animal):) has dedicated language syntax
```
``` text
Software System
│
├── Modules
│
├── Classes (design)
│
└── Objects (runtime)
       │
       ├── Own state
       ├── Provide behaviour
       ├── Have identity
       │
       └── Collaborate through relationships
              │
              ├── Dependency (temporary use)
              ├── Association (knows about)
              ├── Aggregation (contains, independent lifetime)
              ├── Composition (owns the parts)
              └── Inheritance (is-a relationship)
```
