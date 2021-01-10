# Entity-mapping model

A [semantic data model](https://en.wikipedia.org/wiki/Semantic_data_model) similar to [entity-relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model), but, much more **easy** to talk about.

## Entity

Just checkout word 'entity' in a dictionary for best explanation.

- [Wiktionary | entity](https://en.wiktionary.org/wiki/entity)
- [Lexico | entity](https://www.lexico.com/definition/entity)

Examples,

- Person entity
- Car entity
- String entity

An entity may admit to some mappings (we'll talk about mappings soon).

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

## Example

The above definitions were just the **fundamentals**. You can define your own definitions on top of the fundamentals.

Below, we'll create data model of a person and we'll try to be creative by specifying some conventions.



For every person, we want to save his/her name, image, parents and children.

Conventions,

- Mappings and entities are referenced by a name.
- A primitive entity is an entity which we expect to be already defined in implementation.
- Common data types are available out of the box as primitive entities. String, Integer, ....
- A super mapping is a mapping which applies a set of other mappings.
- Notation of defining a mapping: `<Name> -> <A/Some> <Associated entity>`.
- Notation of defining a super mapping: `<Name> :> <Applied mapping(s) separated by comma(s)> `.
- Notation of defining an entity: `<Name> : <Admitted mapping(s) separated by comma(s)>`.

So,

- Name -> A String
- Image -> A String (URI of the image)
- Person -> A Person
- Mother :> Person
- Father :> Person
- Parents :> Father, Mother
- Persons -> Some Persons
- Children :> Persons
- Person : Name, Image, Parents, Children
