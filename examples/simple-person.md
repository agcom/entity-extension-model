# A simple example

We'll create a simple data model of a **person**. For every person, we want to save his/her id, name, parents and children.

To express the model, we'll reference each entity/mapping by a **name** and use the following simple writing **notation**:

> `<   >` blocks indicate replacements.

|  Type   |            Notation             |
| :-----: | :-----------------------------: |
| Entity  | `<name> : <admitted mappings>`  |
| Mapping | `<name> -> <associated entity>` |
| Comment |          `# <comment>`          |

> We'll actually use the [identifier name](../extensions/id-name.md), the [text notation](../extensions/text-notation.md) and the [primitive entity](../extensions/primitive-entity.md) extensions.

## Data model

```entity-mapping
person : id, name, mother, father, children

# String is a primitive entity (has no mappings).
string :

id -> string
name -> string
mother -> person
father -> person
children -> person
```
