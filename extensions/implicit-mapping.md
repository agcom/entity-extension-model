# Implicit mapping

With this extension, each entity will implicitly introduce a mapping.

For each entity, the introduced mapping

- is **identified** among mappings as the entity is identified among entities.
- does **associates** with the entity.

For example, entity `x` will implicitly introduce the mapping `x` which associates with the entity `x`.

> Using the [text notation](text-notation.md):
>
> ```entity-mapping
> x
> y : x
> 
> x -> x # Can be omitted cause it implicitly exists.
> ```