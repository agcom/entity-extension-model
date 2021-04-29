# Person

For each person, we'll save his/her id, name, gender, birth date, parents and children.

## Data model

We'll use all available extensions and express the model using the [text notation](../extensions/text-notation.md).

```entity-mapping
# Primitive entities
string
date
gender

person : id, name, gender, birth-date, parents, children

id -> string
name -> string
birth-date -> date
children -> person
father -> person
mother -> person
parents :> mother, father
```
