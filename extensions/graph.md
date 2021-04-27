# Graph view

> Based on the [reference name](reference-name.md) extension.

In a directed graph,

Entities be **vertices** and mappings be **edges**. Each vertex/edge is identified by its associated entity/mapping **name**.

if and only if the `x` entity admits to the `m` mapping and the `m` mapping associates with the `y` entity, then there exists an edge named `m` from vertex `x` to vertex `y`.

Visually said,

> Using the [suggested notation](notation.md).

```entity-mapping
x : m
m -> y
y
```

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0eCAtLW0tLT5cblx0eSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)

## Example

Graph view of the [simple](../examples/simple.md) example,

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0c3RyaW5nXG5cdHBlcnNvblxuXHRcblx0cGVyc29uIC0tbmFtZS0tPiBzdHJpbmdcblx0cGVyc29uIC0tbW90aGVyLS0-IHBlcnNvblxuXHRwZXJzb24gLS1mYXRoZXItLT4gcGVyc29uXG5cdHBlcnNvbiAtLWNoaWxkcmVuLS0-IHBlcnNvbiIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)
