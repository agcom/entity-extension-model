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
String
Person : Name, Parents, Children

String -> String
Person -> Person

Name :> String
Children :> Person
Father :> Person
Mother :> Person
Parents :> Mother, Father
```

Let's see a **transpiled** version of the above example,

```
String
Person : Name.String, Parents.Mother.Person, Parents.Father.Person, Children.Person

String -> String
Person -> Person

Name.String -> String
Children.Person -> Person
Father.Person -> Person
Mother.Person -> Person
Parents.Mother.Person -> Person
Parents.Father.Person -> Person
```



