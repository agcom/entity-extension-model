# Primitive entity

Ever wondered that an entity-mapping data model only consists of some loops which lead to **emptiness**?

## Short story

Well, **YES**. Entities with no mappings (leaf entities) are sources for emptiness.

But, **NO**, with this extension. Leaf entities should be handled by **implementations**.

## Long story

Lets explain with a [simple example](../examples/simple-person.md),

```entity-mapping
person : name
name -> string
string
```

Each person has a name. But, **what's** name? It's a mapping to a string instance. Well, **what's** string, is it an empty entity (implying that name maps to an empty thing, thus, person is also an empty entity)? 

Let's actually define the string entity.

```entity-mapping
string : character
character -> character
character
```

An string instance consists of some characters. **What's** character?

```entity-mapping
character : byte

byte -> byte
byte : bit

bit -> bit
bit
```

**What's** bit? An strict entity which should be handled by implementations.

It would have been easier and more abstract (in a good way) to say that at the string entity.

Imagine it's 2070 and new computers, instead of digital logic, work on top of a new logic; Graph logic. Now to implement this person model ☝️, they should handle the bit entity, thus, mimicking logical computers. The model is bound to logical computers.

But, with the following 👇 person model,

```entity-mapping
person : name
name -> string
string
```

They can implement the string entity in their optimized way ✅.

> String is a good enough abstraction. Too much abstraction would suffer implementations.

So, **what's** string here? Not emptiness, but an entity with clear semantics which should be handled by **implementations**.