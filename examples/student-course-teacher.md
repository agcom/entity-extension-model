# Student, course, teacher

A small learning website. Courses are published and students participate in them and achieve scores.

## Pseudo requirements

- Students and teachers are **persons**.
- Each course is **taught** by a teacher and each teacher **taught** a couple of courses.
- Students can **participate** in courses and be **scored** in them.

## Data model

The following 👇 EM data model is a possible outcome, probably the simplest and the most abstract:

> Uses [identifier name](../extensions/id-name.md), [notation](../extensions/notation.md), [primitive entity](../extensions/primitive-entity.md) and [implicit mapping](../extensions/implicit-mapping.md) extensions.

```entity-mapping
# Primitive entities
string
integer

# Simple mappings
name -> string
id -> string
score -> integer

# Each person has a name and an id.
person : name, id

# Each student is composed of a person (favored composition over inheritance), participated in some courses and got some scores.
student : person, course, score

# Each course is taught by a teacher and has some scores associated with it (scores achieved by students).
course : teacher, score

# Each teacher is a person and taught some courses.
teacher : person, course
```

### How to find out a student's score in a course?

Note that the student entity and the course entity, **both admit to the score mapping** which associates their instances with instances of the integer entity.

To find out a student's score in a course, we should look at **common instances** of the student's scores and the course's scores.

> More formally said, we should look at common integer instances of the student's score's range (mapping's range) and the course's score's range.

You may see the score mapping as a two input function, a student and a course. The output would be as described ☝️; Common integer instances.

This solution works but surely isn't the fastest if implemented as it is. **Optimizing** such queries is an **implementation concern**.