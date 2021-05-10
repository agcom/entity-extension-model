# A simple example

We'll create a simple data model of a **person**. For every person, we want to save his/her id, name, parents and children.

To express the model, we'll reference each type/mapping by a **name** and use the following simple writing **notation**:

> `<   >` blocks indicate replacements.

|  What   |            Notation            |
| :-----: | :----------------------------: |
|  Type   | `<name> : <admitted mappings>` |
| Mapping | `<name> -> <associated type>`  |
| Comment |         `# <comment>`          |

> We'll actually use the [identifier name](../extensions/id-name.md), the [text notation](../extensions/text-notation.md) and the [primitive type](../extensions/primitive-type.md) extensions.

## Data model

```type-mapping
person : id, name, mother, father, children

# String is a primitive type (has no mappings).
string :

id -> string
name -> string
mother -> person
father -> person
children -> person
```