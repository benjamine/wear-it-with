# Wear it with proposal

### Product tags

Now product document has a tags array. This array describe the product, for instance we have a product that has the following tags array:

```
{
  tags: ['woman', 'jacket', 'leather', ...]
}
```

To find similar products in orther to fill `similar products list` we run a query that resolve the intersection of the tags arrays, between the current product and the others in the data base. Product that has more matches goes first and the ones that has less matches goes last.

I think that to fill the `wear it with list` We could run some queries like the used to fill the `similar products list`, and get the first product from each query result. But using some `wear it with tags arrays` instead of the product `tags array`.

### Wear it with rules

To obtain the `wear it with tags arrays` we need to define rules. We've been talking about to create an admin tool to define links between products, to declare wich product could be wear with other. I propose to link tags instead of products. I think this is a better aproach because you are linking "kinds of products" intead of each single product, so the new products get linked automaticaly when they are tagged.
These links or rules could be represented as a JSON document:

```
[
  { with: ["leather", "jacket"], "wear": ["jeans"] },
  { with: ["leather", "jacket"], "wear": ["seneakers"] },
  { with: ["leather", "jacket"], "wear": ["leather", "nubuck", "sandals"] },
  { with: ["leather", "jacket"], "wear": ["silver", "bracelet"] },
  
  ...
]
```
