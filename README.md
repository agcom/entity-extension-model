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

Every entity may have multiple instances.

> If you're familiar with [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming), 'entity' is similar to 'class' and 'instance' is similar to 'object'.

## Mapping

As clear as its name suggests; Something that **manipulates** instances of an entity.

For example, when we're adding a name attribute to the person entity, we're manipulating every instance of person. The name attribute is an mapping that we just assigned to the person entity. We can also reuse it on other entities if the mapping allows.

The **manipulating operation** is something that the mapping itself or the implementation specifies.

There are no limits to mappings (except that they're not entities),

- Mappings can use other mappings.
	- An mapping can apply a group of other mappings.
- Mappings can use entities.

### Primitive mappings

A primitive mapping is something that the **implementation should handle**.

In other words, we may define some primitive mappings and expect them to be already defined in implementation.

For example, we can define string, integer and double as primitive mappings.

All other mappings are based on primitive mappings.

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
