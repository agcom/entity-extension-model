# Entity-mapping model

A [semantic data model](https://en.wikipedia.org/wiki/Semantic_data_model) similar to [entity-relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model), but, much more **easy** to talk about.

## Entity

Just checkout word 'entity' in a dictionary for best explanation.

- [Wiktionary | entity](https://en.wiktionary.org/wiki/entity)
- [Lexico | entity](https://www.lexico.com/definition/entity)

Examples,

- Person entity
- Car entity

An entity may admit to some mappings. An entity which admits to no mappings, is an **empty entity**.

### Instance

A specific example of an entity, is called an **instance**.

- Alireza Ghasemi is an instance of Person entity.
- Tesla Model S is an instance of Car entity.

An entity may have multiple instances.

> If you're familiar with [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming), 'entity' is similar to 'class' and 'instance' is similar to 'object'.

## Mapping

In mathematics, mapping is an operation that associates each element of a given set (domain) with one or more elements of a second set (range).

- [Wikitionary | mapping](https://en.wiktionary.org/wiki/mapping)
- [Lexico | mapping](https://www.lexico.com/definition/mapping)

When an entity admits to a mapping, the mapping associates each instance of the entity with a set of instances of an(other) entity.

- Domain: Instances of the entity
- Range: A set of instances of an(other) entity

In other words, a mapping **associates** each instance of the admitted entity with a set of instances of an(other) entity.

For example, every person may have some child. We should define a children mapping which maps each instance of the person entity with a set of instances of the person entity.

To make implementation of entity-mapping model practical, it needs base cases, which we'll call **primitive mappings**.

### Primitive mapping

We expect primitive mappings to be **handled by implementation**.

For example, we can define a string mapping as a primitive mapping (a simple case).

Without any primitive mapping, the model falls into an infinite loop.

## Examples

This semantic data model is so simple that it doesn't need a notation. However, you may define your own rules or notation to even simplify it more.

We'll to create data model of a person. For every person, we want to save his/her name, image, parents and children.

---

Primitive mappings (expected to be already defined in implementation),

- String: Maps every instance of the extended entity to a string.
- Integer: Maps every instance of the extended entity to an integer.
- ...

With these primitive mappings present, clearly, we would only have one entity, which is the person entity.

Mappings,

- Name mapping: Uses string mapping.
- SSN mapping: Uses string mapping.
- Image mapping: Uses string mapping (URI of the string).
- Person mapping: Maps every instance of the extended entity to an instance of person entity.
- Mother mapping: Uses person mapping.
- Father mapping: Uses person mapping.
- Parents mapping: Uses father and mother mapping.
- Persons mapping: Maps every instance of the extended entity to zero of more instances of person entity.
- Children mapping: Uses persons mapping.

Entity,

- Person entity: Extended by name, gender, SSN, image, parents and children mappings.
