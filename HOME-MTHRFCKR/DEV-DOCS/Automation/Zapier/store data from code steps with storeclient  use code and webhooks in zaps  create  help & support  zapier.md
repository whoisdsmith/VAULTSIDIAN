The StoreClient is a built-in utility available in both [Python](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps) and [JavaScript](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps) code steps that lets you store and retrieve data between Zaps or between runs of the same Zap.

## [Limitations](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#limitations)

## [1\. Set a secret for the StoreClient](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#set-a-secret-for-the-storeclient)

First, you'll need to provide a secret that will protect your data. Your secret should use UUID4 format. We recommend using this [Online UUID Generator Tool](https://www.uuidgenerator.net/version4) to generate your secret.

___

## [2\. Use the StoreClient with JavaScript steps](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#use-the-storeclient-with-javascript-steps)

Instantiating a client is very simple:

```
var store = StoreClient('your secret here');
```

`StoreClient` is a promise-based library and a great time to get familiar with `async` and `await`!

___

## [3\. Get and set values with JavaScript](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#get-and-set-values-with-javascript)

Most likely you just want to `get` and `set` some values - this is the simplest possible example:

```
const store = StoreClient('your secret here');
await store.set('hello', 'world');
const value = await store.get('hello');
return {result: value} // value === 'world'
```

If the value doesn't exist during your `get()` call, it will return a `null` value.

___

## [4\. Bulk operations with JavaScript](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#bulk-operations-with-javascript)

You can also save and retrieve multiple keys and values - a slightly more complex example:

```
const store = StoreClient('your secret here');
await store.setMany({hello: 'world', foo: 'bar'})
const values = await store.getMany('hello', 'foo');
// values === {hello: 'world', foo: 'bar'}
await store.deleteMany('hello', 'foo');
// or, if you want to wipe everything
await store.clear();
```

Note, you can call `getMany` and `deleteMany` in a few different ways:

```
store.getMany('hello', 'foo'); // as arguments
store.getMany(['hello', 'foo']); // as array
store.getMany({hello: null, foo: null}); // as object
```

___

## [5\. Use the StoreClient with Python steps](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#use-the-storeclient-with-python-steps)

When working with StoreClient, as for all Python Code steps, you will need to return a dictionary or an array of dictionaries. Returning a string will result in an error.

```
store = StoreClient('your secret here')
```

___

## [6\. Get and set values with Python](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#get-and-set-values-with-python)

Most likely you just want to get and set some values. This is the simplest possible example:

```
store = StoreClient('your secret here')
store.set('hello', 'world')
value = store.get('hello') # return 'world'
store.delete('hello')
```

If the value doesn't exist during your `get()` call, it will return a `None` value.

___

## [7\. Bulk operations with Python](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#bulk-operations-with-python)

You can also save and retrieve multiple keys and values - a slightly more complex example:

```
store = StoreClient('your secret here')
store.set_many({'hello': 'world', 'foo': 'bar'})
values = store.get_many('hello', 'foo') # return {'hello': 'world', 'foo': 'bar'}
store.delete_many('hello', 'foo')
store.clear() # or, if you want to wipe everything
```

Note, you can call `get_many` and `delete_many` in a few different ways:

```
store.get_many('hello', 'foo') # as args
store.get_many(['hello', 'foo']) # as list
store.get_many({'hello': None, 'foo': None}) # as dict
```

And similarly with `set_many`:

```
store.set_many({'hello': 'world', 'foo': 'bar'}) # as dict
store.set_many(hello='world', foo='bar') # as kwargs
```

___

## [8\. Other Python operations](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient#other-python-operations)

Slightly more complex examples include incrementing a numeric value, setting a value if a condition is met or pushing/popping from lists. These operations also have the benefit that they are _atomic_.

`increment_by` increments a value found under a given key. The value has to be a numeric value in order for this operation to succeed:

```
store.increment_by(key, amount)
```

`set_value_if` sets a value if a condition is met. If the value stored under the given key matches the same value as the given previous value, then the given _value_ parameter will become the new value of the key.

```
store.set(key, 1) # set a value
# sets 2 only if the previous value of *key* is 1
store.set_value_if(key, value=2, previous_value=1)
```

`set_child_values/remove_child_values` can be useful for storing/removing nested values. The value under the given key has to be a dictionary.

````
```python
store.set_child_values(key, {'a': 'b'}) # store under the given key the key `a` with value `b`
store.remove_child_values(key, ['a', 'c']) # remove the keys `a` and 'c' from the mapping found at `key`
````

`list_pop/list_push` can be useful for manipulating lists.

```
store.list_push(key, some_value)
store.list_pop(key)
```

Additionally, `list_push` and `list_pop` accept a `location` parameter.

```
store.list_push(key, value, location='tail') # Push to the tail of the list
store.list_push(key, value, location='tail_set') # Push to the tail of the list only if the value is not already in the list
store.list_push(key, value, location='head') # Push to the head of the list
store.list_push(key, value, location='head_set') # Push to the head of the list only if the value is not already in the list
store.list_pop(key, location='tail') # Pop from the end of the list
store.list_pop(key, location='head') # Pop from the head of the list
```

`list_pop` can also receive a `default` parameter, which will be returned when there is nothing to pop from the given list:

```
store.list_pop(key, default=1, location='tail')
```