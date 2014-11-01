# Wear it with proposal

### Product tags

Now product document has a tags array. This array describe the product, for instance we have a product that has the following tags array:

```
{
  tags: ['woman', 'jacket', 'leather', ...]
}
```

To find similar products in orther to fill `similar products list` we run a query that resolve the intersection of the tags arrays, between the current product and the others in the data base. Product that has more matches goes first and the ones that has less matches goes last.

I think that to fill the `wear it with list` We could run the same query as used to fill the `similar products list`, but using a calculated `wear it with tags array` instead of the product tags array.

### Wear it with rules

To calculate the `wear it with array` we need to define rules. We've been talking about to create an admin tool to define links between products, to declare wich product could be wear with other. I propose to link tags instead of products. I think this is a better aproach because you are linking like a "kinds of product" intead of each single product.

```

...
...
```
