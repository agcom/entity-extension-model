# Text notation

A text-based notation for TM.

This notation shows how fundamental components, types and mappings, are defined and related to form a data model. If you're going to use this notation directly, you should write using characters and use [identifier name](id-name.md) extension as well.

### Replacement block

A `<note>` block indicates a replacement, and the note inside, describes the replacement type.

A set replacement should be done by writing set members separated using commas. For example, `<set of mappings>`, replaced by `name, mother, father, children`.

## Type

`<type> : <set of mappings>`

- `<type>`: Type reference/identifier.

- `<set of mappings>`: Admitted mappings.

> In case of an empty set of mappings, both following notations are considered correct.
>
> - `<type>`
> - `<type> :`

## Mapping

`<mapping> -> <type>`

- `<mapping>`: Mapping reference/identifier.

- `<type>`: Associated type.

## Comment

`# <comment>`

- `<comment>`: Anything.