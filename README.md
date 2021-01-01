# Entity-extension model

A [semantic data model](https://en.wikipedia.org/wiki/Semantic_data_model) alternative to [entity-relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model), but, much more **easy** to talk about.

## [Entity](https://www.lexico.com/definition/entity)

A data model is called an **entity**. For example,

- Person
- Car

An entity can have zero or more unique **extensions** (we'll talk about it later). An entity without extensions is an empty entity.

### Instance

An entity when full-filled with **data**, is called an instance of that entity.

- Alireza Ghasemi is an instance of Person entity.
- Tesla Model S is an instance of Car entity.

Every entity can have multiple instances.

> If you're familiar with [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming), 'entity' is similar to 'class' and 'instance' to 'object'.

## Extension

As clear as its name suggests; Something that **manipulates** instances of an entity.

For example, when we're adding a name attribute to the person entity, we're manipulating every instance of person. The name attribute is an extension that we just assigned to the person entity. We can also reuse it on other entities if the extension allows.

The **manipulating operation** is something that the extension itself or the implementation specifies.

There are no limits to extensions (except that they're not entities),

- Extensions can use other extensions.
	- An extension can apply a group of other extensions.
- Extensions can use entities.

### Primitive extensions

A primitive extension is something that the **implementation should handle**.

In other words, we may define some primitive extensions and expect them to be already defined in implementation.

For example, we can define string, integer and double as primitive extensions.

All other extensions are based on primitive extensions.

## Examples

This semantic data model is so simple that it doesn't need a notation. However, you may define your own rules or notation to even simplify it more.

We'll to create data model of a person. For every person, we want to save his/her name, image, parents and children.

---

Primitive extensions (expected to be already defined in implementation),

- String: Maps every instance of the extended entity to a string.
- Integer: Maps every instance of the extended entity to an integer.
- ...

With these primitive extensions present, clearly, we would only have one entity, which is the person entity.

Extensions,

- Name extension: Uses string extension.
- SSN extension: Uses string extension.
- Image extension: Uses string extension (URI of the string).
- Person extension: Maps every instance of the extended entity to an instance of person entity.
- Mother extension: Uses person extension.
- Father extension: Uses person extension.
- Parents extension: Uses father and mother extension.
- Persons extension: Maps every instance of the extended entity to zero of more instances of person entity.
- Children extension: Uses persons extension.

Entity,

- Person entity: Extended by name, gender, SSN, image, parents and children extensions.
