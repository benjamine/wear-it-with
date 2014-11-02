# Wear it with proposal

### Product tags

Now product document has a tags array. This array describe the product, for instance we have a product that has the following tags array:

```
{
  tags: ["woman", "jacket", "leather", ...]
}
```

### Similarity query

To find similar products in order to fill `similar products` list we run a query that resolve the intersection of the tags arrays, between the `current product` (the one that we are viewing its detail) and the others in the data base. Product that has more matches goes first and the ones that has less matches goes last. Lets call this query `similarity query`.

I think that to fill the `wear it with` list We could run some queries like the `similarity query`, between `current product`, a set of `wear it with` rules, and the products in the database.

### Wear it with rules document

We've been talking about to create an admin tool to define links between products, to declare which product could be wear with other. **I propose to link tags instead of products**. I think this is a better approach because you are linking "kinds of product" instead of each single product, so a new product get linked automatically when it is tagged.
These links or rules could be represented as a JSON document:

```
[
  { with: ["woman", "leather", "jacket"], "wear": ["jeans"] },
  { with: ["woman", "leather", "jacket"], "wear": ["leather", "nubuck", "sandals"] },
  { with: ["woman", "leather", "jacket"], "wear": ["silver", "bracelet"] },
  
  ...
]
```

### Wear it with list

We could run the `similarity query` between the `current product` tags array and the `with` array of the rules, and get the first N rules. Then we have a set of N `wear tags` arrays. In order to obtain the `wear it with` list for the `current product`, we could run the `similarity query` between each `wear tags` array and the tags arrays of the products in the data base. Then we could get the first product of each query result, and fill the `wear it with` list.
