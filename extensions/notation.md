# Notation

A **suggested** notation for EM.

This notation shows how fundamental components, entities and mappings, are defined and related to form a data model. If you're going to use this notation directly, you should write using characters and use [identifier name](id-name.md) extension as well.

### Replacement block

A `<note>` block indicates a replacement, and the note inside, describes the replacement type.

A set replacement should be done by writing set members separated using commas. For example, `<set of mappings>`, replaced by `name, mother, father, children`.

## Entity

`<entity> : <set of mappings>`

- `<entity>`: Entity reference/identifier.

- `<set of mappings>`: Admitted mappings.

> In case of an empty set of mappings, both following notations are considered correct.
>
> - `<entity>`
> - `<entity> :`

## Mapping

`<mapping> -> <entity>`

- `<mapping>`: Mapping reference/identifier.

- `<entity>`: Associated entity.

## Comment

`# <comment>`

- `<comment>`: Anything.

## Example

Almost all examples in the repository use this extension.
