# Super mapping

A mapping which applies a (non-empty) set of other mappings.

## Text notation

Defining a supper mapping in the [text notation](text-notation.md) extension:

`<super mapping> :> <set of mappings>`

- `<super mapping>`: Super mapping reference/identifier.
- `<set of mappings>`: Applied mappings.

## Transpilation

We'll show how super mappings can transpile down to the **fundamentals**, hence proving that they won't introduce any **conflicts**.

When defining a super mapping, **under the hood**, for each applied mapping a new unique mapping with the same associated entity will be created.

When a super mapping applies another super mapping, it applies under the hood mappings.

When an entity admits to a super mapping, it admits to under the hood mappings.

### Example

```entity-mapping
string
person : name, parents

name -> string
father -> person
mother -> person

parents :> mother, father # A supper mapping.
```

**A transpiled version** of the above data model 👇:

```entity-mapping
string
person : name, parents.father, parents.mother

name -> string
father -> person
mother -> person

parents.father -> person
parents.mother -> person
```