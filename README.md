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

## Example

The above definitions were just the **fundamentals**. You can define your own definitions on top of the fundamentals.

Below, we'll create data model of a person and we'll try to be creative by defining our own rules.

---

For every person, we want to save his/her name, image, parents and children.

Rules,

- Mappings and entities are referenced by a name.
- Common data types are available out of the box as primitive mappings. A string, an integer, ....
- A super mapping is a mapping which applies a set of other mappings.
- Notation of defining a mapping: `<name> -> <A or Some> <associated entity><s>`.
- Notation of defining a super mapping: `<name> ->: <applied mappings separated by comma(s)> `.
- Notation of defining an entity: `<name> : <admitted mappings separated by comma(s)>`.

So,

- Name -> A string
- Image -> A string (URI of the image)
- Person -> A person
- Mother ->: Person
- Father ->: Person
- Parents ->: Father, Mother
- Persons -> Some Persons
- Children ->: Persons
- Person : Name, Image, Parents, Children
