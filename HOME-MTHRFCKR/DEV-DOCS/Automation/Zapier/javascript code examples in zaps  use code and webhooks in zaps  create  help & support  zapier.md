This page provides some examples for using [JavaScript code steps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps). Every example depends on specific `inputData`, which is provided under the "Input Data" field when setting up your Zap. [This example screenshot](https://cdn.zapier.com/storage/photos/07a37cd88d3c9de7949dd9fcf5070b13.png) shows three demonstration inputs you can use in your code like this: `inputData.body`, `inputData.receivedDate`, and `inputData.subject`. Be sure you read the code examples and provide the right inputs otherwise nothing will work as expected!

JavaScript is an advanced programming language. If you're not familiar with using JavaScript, it's recommended to ask a developer for help.

## [Introductory Examples](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-1)

Each of the four examples below expects a `name` in the "Input Data" field.

A synchronous example might be something as trivial as:

```
return {id: 1234, hello: 'world!', name: inputData.name};
```

You can also bind the result to `output`—the code above has **exactly the same** behavior as the code below:

```
output = {id: 1234, hello: 'world!', name: inputData.name};
```

A synchronous example with an early empty return might be something like:

```
if (inputData.name === 'Larry') {
    return []; // we don't work for Larry!
}
return {id: 1234, hello: 'world!', name: inputData.name};
```

If Code by Zapier is the Zap's trigger and you return an empty array `[]`, we will not trigger any actions downstream. It's as if you said "never mind" in code. This does not apply when Code by Zapier is used as an action, only when it is the trigger.

An asynchronous example might be something like:

```
callback(null, {id: 1234, hello: 'world!', name: inputData.name});
```

___

## [Introductory HTTP Example](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-2)

As of June 2018, Node.js version 8 is available in Code steps. That release made `async // await` available for general use, greatly simplifying asynchronous javascript code. You can read more about `await`[here](https://javascript.info/async-await).

A more complex asynchronous example (no "Input Data" needed) is:

```
const res = await fetch('http://example.com/');
const body = await res.text();
return {id: 1234, rawHTML: body};
// or
// output = {id: 1234, rawHTML: body}
```

For older Code steps, you can do the same with promises:

```
fetch('http://example.com/')
  .then(function(res) {
    return res.text();
  })
  .then(function(body) {
   var output = {id: 1234, rawHTML: body};
    callback(null, output);
  })
  .catch(callback);
```

Be sure to use `callback` in asynchronous code that uses `.then()`!

___

## [Introductory Logging Example](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-3)

This example expects a `name` in the "Input Data" field:

```
if (inputData.name) {
  console.log('got name!', inputData.name);
}
return {id: 1234, hello: 'world!', name: inputData.name};
```

Test your action and look at the data to see the `console.log` result.

___

## [Simple Math: Divide by Two](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-4)

This example expects a `rawNumber` in the "Input Data" field:

```
return {
  calculatedNumber: Number(inputData.rawNumber) / 2
};
```

___

## [Simple Email Extraction](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-5)

This example expects a `rawText` in the "Input Data" field:

```
return {
  firstEmail: (inputData.rawText.match(/([\w._-]+@[\w._-]+\.[\w._-]+)/gi) || [])[0]
};
```

___

## [Complex Multiple Email Extraction](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-6)

This example expects a `rawText` in the "Input Data" field:

```
var emails = inputData.rawText.match(/([\w._-]+@[\w._-]+\.[\w._-]+)/gi) || [];
return emails.map(function(email) {
  return {email: email};
});
```

Because this returns an array like `[]` instead of a single object like `{}` this will activate follow up actions multiple times, one for each email found! If no emails are found, nothing happens.

___

## [Weather JSON API Call](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-7)

This example expects a `zipCode` in the "Input Data" field:

```
const res = await fetch('http://api.openweathermap.org/data/2.5/weather?zip=' + inputData.zipCode + ',us');
const json = await res.json();
return json;
```

For older Code steps, you can do the same with promises:

```
fetch('http://api.openweathermap.org/data/2.5/weather?zip=' + inputData.zipCode + ',us')
  .then(function(res) {
    return res.json();
  })
  .then(function(json) {
    callback(null, json);
  })
  .catch(callback);
```

___

## [Store State](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps#step-8)

It isn't uncommon to want to stash some data away for the next run, and our `StoreClient` can do exactly that. For example, this is a counter that keeps track of how many times it is run:

```
const store = StoreClient('your secret here');
const count = await store.get('some counter')
const newCount = (count || 0) + 1;
await store.set('some counter', count);
return {count: newCount}
```

For older Code steps, you can do the same with promises:

```
var store = StoreClient('your secret here');
var outCount;
store
 .get('some counter')
  .then(function(count) {
    count = (count || 0) + 1;
    outCount = count;
    return store.set('some counter', count);
  })
  .then(function() {
    callback(null, {'the count': outCount});
  })
  .catch(callback);
```

Learn more about [StoreClient](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient).