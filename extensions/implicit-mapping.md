# Implicit mapping

With this extension, each entity will have an implicit mapping;

For each entity, the implicit mapping

- is **identified** among mappings as the entity is identified among entities.
- does **associates** with the entity.

By an example, using the [suggested notation](notation.md), entity `x` will have the implicit mapping `x`:

```entity-mapping
x
y : x

x -> x # Can be omitted cause it's implicitly applied.
```

### Handy with super mappings

This extension is very handy beside the [super mapping](super-mapping.md) extension.

With this extension, the example in the super mapping document shrinks down to the following :point_down:.

```entity-mapping
string
person : name, parents, children

name :> string
children :> person
father :> person
mother :> person
parents :> mother, father
```

