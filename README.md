# Wear it with proposal

### Product tags

Now product document has a tags array. This array describe the product, for instance we have a product that has the following tags array:

```
{
  tags: ['woman', 'jacket', 'leather', ...]
}
```

### Similarity query

To find similar products in orther to fill `similar products` list we run a query that resolve the intersection of the tags arrays, between the `current product` (the one that we are viewing its detail) and the others in the data base. Product that has more matches goes first and the ones that has less matches goes last. Lets call this query `similarity query`.

I think that to fill the `wear it with` list We could run some queries like the used to fill the `similar products list`, and get the first product from each query result. But using some `wear it with tags` arrays instead of the product tags array.

### Wear it with rules

To obtain the `wear it with tags` arrays we need to define rules. We've been talking about to create an admin tool to define links between products, to declare wich product could be wear with other. *I propose to link tags instead of products*. I think this is a better approach because you are linking "kinds of product" intead of each single product, so the new products get linked automaticaly when they are tagged.
These links or rules could be represented as a JSON document:

```
[
  { with: ["leather", "jacket"], "wear": ["jeans"] },
  { with: ["leather", "jacket"], "wear": ["leather", "nubuck", "sandals"] },
  { with: ["leather", "jacket"], "wear": ["silver", "bracelet"] },
  
  ...
]
```

### Wear it with list

In order to get the `wear it with tags` arrays we could run the `similarity query` between the `current product` tags array and the `with` array of the rules, and get the first N rules. Then we have a set of `wear tags` arrays, so we could run the `similarity query` for each `wear tags` array against the tags arrays of the products in the data base. Then we could get the first product of each query result, and fill the `wear it with` list.
