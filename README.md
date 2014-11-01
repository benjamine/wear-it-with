# Wear it with proposal

### Product tags

Now product document has a tags array. This array describe the product, for instance we have a product that has the following tags array:

```
{
  tags: ['woman', 'jacket', 'leather', ...]
}
```

To find similar products in orther to fill `similar products list` we run a query that resolve the intersection of the tags arrays, between the current product and the others in the data base. Product that has more matches goes first and the ones that has less matches goes last. 
