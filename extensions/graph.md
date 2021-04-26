# Graph view

> Based on the [reference name](reference-name.md) extension.

In a directed graph,

Entities be **vertices** and mappings be **edges**. Each vertex/edge is identified by its associated entity/mapping **name**.

if and only if the `X` entity admits to the `A` mapping and the `A` mapping associates with the `Y` entity, then there exists an edge named `A` from vertex `X` to vertex `Y`.

Visually said,

> Using the [suggested notation](notation.md).

```
X : A
A -> Y
Y
```

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0WCAtLUEtLT5cblx0WSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)

## Example

Graph view of the [simple](../examples/simple.md) example,

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0U3RyaW5nXG5cdFBlcnNvblxuXHRcblx0UGVyc29uIC0tTmFtZS0tPiBTdHJpbmdcblx0UGVyc29uIC0tTW90aGVyLS0-IFBlcnNvblxuXHRQZXJzb24gLS1GYXRoZXItLT4gUGVyc29uXG5cdFBlcnNvbiAtLUNoaWxkcmVuLS0-IFBlcnNvbiIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)