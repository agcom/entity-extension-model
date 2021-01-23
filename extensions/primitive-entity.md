# Primitive entity

Ever wondered that an entity-mapping data model only consists of some loops which lead to **emptiness**?

## Short story

Well, **YES**. Entities with no mappings (leaf entities) are sources for emptiness.

But, **NO**, with this extension. Leaf entities should be handled by **implementations**.

## Long story

Lets explain with a [simple example](../examples/simple.md),

```
Person : Name
Name -> String
String
```

Each person has a name. But, **what's** Name? It's a mapping to a string instance. Well, **what's** String, is it an empty entity (implying that name maps to an empty thing, thus, person is also an empty entity)? 

Let's actually define the string entity.

```
String : Character
Character -> Character
Character
```

An string instance consists of some characters. **What's** Character?

```
Character : Byte

Byte -> Byte
Byte : Bit

Bit -> Bit
Bit
```

**What's** Bit? An strict entity which should be handled by implementations.

It would have been easier and more abstract (in a good way) to say that at the string entity.

Imagine it's 2070 and new computers, instead of digital logic, work on top of a new logic; Graph logic. Now to implement this person model :point_up:, they should handle the bit entity, thus, mimicking logical computers. The model is bound to logical computers.

But, with the following :point_down: person model,

```
Person : Name
Name -> String
String
```

They can implement the string entity in their optimized way :white_check_mark:.

> String is a good enough abstraction. Too much abstraction would suffer implementations.

So, **what's** String here? Not emptiness, but an entity with clear semantics which should be handled by **implementations**.