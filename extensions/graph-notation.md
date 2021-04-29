# Graph notation

In a directed graph, entities be **vertices** and mappings be **edges**. Each vertex/edge is associated with its entity/mapping **identifier**.

if and only if the `x` entity admits to the `m` mapping and the `m` mapping associates with the `y` entity, then there exists an edge labeled `m` from vertex `x` to vertex `y`.

Visually said:

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0eCAtLW0tLT5cblx0eSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)

> Equivalent in the text notation:
>
> ```entity-mapping
> x : m
> m -> y
> y
> ```

## Example

Graph view of the [simple](../examples/simple-person.md) example:

![Mermaid SVG](https://mermaid.ink/svg/eyJjb2RlIjoiZ3JhcGggTFJcblx0c3RyaW5nXG5cdHBlcnNvblxuXHRcbiAgICBwZXJzb24gLS1pZC0tPiBzdHJpbmdcblx0cGVyc29uIC0tbmFtZS0tPiBzdHJpbmdcblx0cGVyc29uIC0tbW90aGVyLS0-IHBlcnNvblxuXHRwZXJzb24gLS1mYXRoZXItLT4gcGVyc29uXG5cdHBlcnNvbiAtLWNoaWxkcmVuLS0-IHBlcnNvbiIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)
