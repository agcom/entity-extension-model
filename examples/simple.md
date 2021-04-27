# A simple example

We'll create a simple data model of a **person**. For every person, we want to save his/her name, parents and children.

To **express** the model, we'll reference each entity/mapping by a name ([reference name](../extensions/reference-name.md)) and use a simple writing notation ([suggested notation](../extensions/notation.md)),

> `<   >` blocks indicate replacements.

|  Type   |            Notation             |
| :-----: | :-----------------------------: |
| Entity  | `<name> : <admitted mappings>`  |
| Mapping | `<name> -> <associated entity>` |
| Comment |          `# <comment>`          |

## The example

```entity-mapping
person : name, mother, father, children

# String is a primitive entity (therefore has no mappings).
string :

name -> string
mother -> person
father -> person
children -> person
```

> Checkout the [primitive entity](../extensions/primitive-entity.md) extension.