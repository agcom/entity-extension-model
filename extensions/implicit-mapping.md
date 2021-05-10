# Implicit mapping

With this extension, each type will implicitly introduce a mapping.

For each type, the introduced mapping

- is **identified** among mappings as the type is identified among types.
- does **associates** with the type.

For example, type `x` will implicitly introduce the mapping `x` which associates with the type `x`.

> Using the [text notation](text-notation.md):
>
> ```entity-mapping
> x
> y : x
> 
> x -> x # Can be omitted cause it implicitly exists.
> ```