# A simple example

We'll create a simple data model of a **person**. For every person, we want to save his/her name, parents and children.

## Conventions

- Entities and mappings will be referenced by their assigned **name**s.
- A **primitive entity** is an entity which we expect to be already defined in implementation.

### Notations

> `<...>` blocks should be replaced by its described thing.

|       Type       |            Notation             |
| :--------------: | :-----------------------------: |
|      Entity      | `<Name> : <Admitted mappings>`  |
| Primitive entity |      `<Name> : Primitive`       |
|     Mapping      | `<Name> -> <Associated entity>` |

## The example

```
String : Primitive

Name -> String
Mother -> Person
Father -> Person
Children -> Person

Person : Name, Mother, Father, Children
```

