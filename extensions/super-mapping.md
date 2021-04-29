# Super mapping

A mapping which applies a (non-empty) set of other mappings.

To avoid conflicts with EM fundamentals, super mappings transpile down to fundamentals.

## Transpile

When defining a super mapping, under the hood, **for each** applied mapping a new unique mapping with the same associated entity will be created.

When a super mapping applies another super mapping, it applies under the hood mappings.

When an entity admits to a super mapping, it admits to under the hood mappings.

## Text notation

To be used with the [text notation](text-notation.md) extension.

`<super mapping> :> <set of mappings>`

- `<super mapping>`: Super mapping reference/identifier.
- `<set of mappings>`: Applied mappings.

## Example

> Using the [text notation](text-notation.md) extension.

```entity-mapping
string
person : id, name, parents, children

string -> string
person -> person

# Of course we're over-using the super mapping in here.
id :> string
name :> string
children :> person
father :> person
mother :> person
parents :> mother, father
```

Let's see a **transpiled** version of the above example,

```entity-mapping
string
person : id.string, name.string, parents.mother.person, parents.father.person, children.person

string -> string
person -> person

id.string -> string
name.string -> string
children.person -> person
father.person -> person
mother.person -> person
parents.mother.person -> person
parents.father.person -> person
```
