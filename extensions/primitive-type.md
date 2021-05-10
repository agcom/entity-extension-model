# Primitive type

Ever wondered that a TM data model only consists of some loops which lead to **emptiness**?

## Short story

Well, **YES**. Types with no mappings (leaf types) are sources of emptiness.

But, **NO**, with this extension. Leaf types should be handled by **implementations**.

## Long story

Let's explain using the [text notation](text-notation.md) and a simple example.

```entity-mapping
person : name
name -> string
string
```

Each person has a name. But, **what's** name? It's a mapping to a string instance. Well, **what's** string, is it an empty type (implying that name maps to an empty thing, thus, person is also an empty type)? 

Let's actually define the string type.

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

**What's** bit? An strict type which should be handled by implementations.

It would have been easier and more abstract (in a good way) to say that at the string type.

Imagine it's 2070 and new computers, instead of digital logic, work on top of a new logic; Graph logic. Now to implement this person model ☝️, they should handle the bit type, thus, mimicking logical computers. The model is bound to digital computers.

But, with the following 👇 person model,

```entity-mapping
person : name
name -> string
string
```

They can implement the string type in their optimized way ✅.

> String is a good enough abstraction. Too much abstraction would suffer implementations.

So, **what's** string here? Not emptiness, but a type with clear semantics which should be handled by **implementations**.