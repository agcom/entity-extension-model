# Entity-extension model

A [semantic data model](https://en.wikipedia.org/wiki/Semantic_data_model) alternative to [entity-relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model), but, much more **easy** to talk about.

**Entities and their manipulations** are completely distinguished. Thus, maximizing their re-usability.

## [Entity](https://www.lexico.com/definition/entity)

A data model is called an **entity**. For example,

- Person
- Car

An entity is described by only a **name** and can have zero or more unique **extensions** (we'll talk about it later).

### Instance

An entity when full-filled with **data**, is called an instance of that entity.

- Alireza Ghasemi is an instance of Person entity.
- Tesla Model S is an instance of Car entity.

Every entity can have multiple instances.

> If you're familiar with [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming), 'entity' is similar to 'class' and 'instance' to 'object'.

## Extension

As clear as its name suggests; Something that **extends instances of an entity** is called an extension. Or briefly said, something that extends an entity.

The **extend operation** is something that the extension specifies or becomes clear in implementation details.

Example,

```
String primitive entity.

Name extension:
	Maps the extended instance to a String instance.
	The String instance can be referenced by 'name' key or whatever way the extended entity defines.
	BTW the String instance should be at least 4 characters.

Person entity:
	Uses Name extension.
```

## Usage

Relieving the extend operation is what makes this semantic data model simple.

The semantic data model doesn't specifies any notation. You can define the extensions and entities in any way you want.

For example, we can describe `Person` entity like this,

```
Rule #1: Every entity is an implicit extension which maps the extended entity instance to an instance of itself.
Rule #2: '<Entity> : <Extensions>' defines a new entity. Its name is <Entity> and <Extensions> is its set of extensions.
Rule #3: Everything else other than the entity definition lies inside its implicit extension; In that case, the entity is extended by its implicit extension.
Rule #4: Common collection types can be used freely.
Rule #5: Common-sense words are accepted.

---

String is a primitive entity.
Name : String. Should be at least 4 characters.
SSN : String. Must be 9 digits.
Image : String. Should be a valid image file name in our images directory.
Gender is an entity with only three instances, male, female and other.
Father : Person.
Mother : Person.
Parent : Father, Mother.
Children : A set of persons.

Person : Name, SSN, Image, Gender, Parent, Children.
```

Or do it the hard way,

```
0 primitive entity.
1 primitive entity.

Bit extension:
	Maps the extended entity instance to 0 or 1 entity instance.
	The extended instance specifies which entity to use; 0 or 1.
Bit entity:
	Extended by Bit extension.

Integer extension:
	Maps the extended entity instance to 32 instances of Bit entity.
	The order of bits matter and they're referenced that way; First bit, Second bit, Third bit, ..., 32nd bit.
Integer entity:
	Extended by Integer extension.

Character extension:
	Maps the extended entity instance to an instance of Integer entity.
Character entity:
	Extended by Character extension.

Array extension:
	Maps the extended entity instance to n sequential instances of any entity.
	The instances are referenced by their ordinal integer in range [0, n).
	n should be non-negative.
Array entity:
	Extended by Array extension.

CharArray extension:
	Maps the extended entity instance to an instance of Array which only maps to instances of Character entity.

CharArray entity:
	Extended by CharArray.

String extension:
	Maps the extended entity instance to an instance of CharArray entity.

String entity:
	Extended by String.

Name extension:
	Maps the extended entity instance to an instance of String entity.
	The String.CharArray.Array.n should be at least 4.

Name entity:
	Extended by Name.

SSN extension:
	Maps the extended entity instance to an instance of String entity.
	The String.CharArray.Array.n must be 9 digits.

SSN entity:
	Extended by SSN.

Image extension:
	Maps the extended entity instance to a String instance.
	The String should be equal to a valid image file name in our images directory.

Image entity:
	Extended by Image extension.

Gender extension:
	Maps the extended entity instance to an instance of Integer.
	The Integer instance can only be only 0, 1 or 2. 0 for male, 1 for female and 2 for other genders.

Gender entity:
	Extended by Gender extension.

Person extension:
	Maps the extended entity instance to a Person entity instance.

Mother extension:
	Maps the extended entity instance to a Person entity instance.

Mother entity:
	Extended by Mother.

Father extension;
	Maps the extended entity instance to a Person entity instance.

Father entity:
	Extended by Father.

Parent extension:
	Maps the extended entity instance to a Father entity instance and a Mother entity instance.

Parent entity:
	Extended by Parent extension.

Children extension:
	Maps the extended entity instance to a set of Person entity instances.

Person entity:
	Extended by Name, SSN, Image, Gender, Parent and Children.
```

So, to wrap up, if it **makes sense** then it's valid.