# Super mapping

A mapping which applies a (non-empty) set of other mappings.

To avoid conflicts with EM fundamentals, super mappings transpile down to fundamentals.

## Transpile

When defining a super mapping, under the hood, **for each** applied mapping a new unique mapping with the same associated entity will be created.

When a super mapping applies another super mapping, it applies under the hood mappings.

When an entity admits to a super mapping, it admits to under the hood mappings.

## Notation

To be used with the [suggested notation](notation.md).

`<super mapping> :> <set of mappings>`

- `<super mapping>`: Super mapping reference.
- `<set of mappings>`: Applied mappings.

## Example

> Using the [suggested notation](notation.md) extension.

```
string
person : name, parents, children

string -> string
person -> person

name :> string
children :> person
father :> person
mother :> person
parents :> mother, father
```

Let's see a **transpiled** version of the above example,

```
string
person : name.string, parents.mother.person, parents.father.person, children.person

string -> string
person -> person

name.string -> string
children.person -> person
father.person -> person
mother.person -> person
parents.mother.person -> person
parents.father.person -> person
```
