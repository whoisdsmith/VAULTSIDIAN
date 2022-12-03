Code steps allow Zaps to run small snippets of Python or JavaScript. This tutorial is for JavaScript code steps, but you can also learn how to [use Python code in your Zaps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps).

Code steps can be used as both triggers and actions.

JavaScript is an advanced programming language. If you're not familiar with JavaScript, it's recommended to ask a developer for help. Zapier does not offer email support for code steps. If you encounter a problem, we recommend asking questions on [StackOverflow and tagging them with "Zapier"](https://stackoverflow.com/questions/tagged/zapier).

For tips and inspiration, check out [JavaScript code examples](https://zapier.com/help/create/code-webhooks/javascript-code-examples-in-zaps).

## [1\. Add a code trigger](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#add-a-code-trigger)

___

## [2\. Set up your code step](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#set-up-your-code-step)

___

## [3\. Test your code trigger](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#test-your-code-trigger)

If your code is valid, the step will show it was successful and display the data. Once the trigger is set up, you can continue to add your action step.

___

## [4\. Add a code action](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#add-a-code-action)

The Code action step allows you to write code that will interact with data coming from the trigger, or a previous action step.

___

## [5\. Set up your code action](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#set-up-your-code-action)

___

## [6\. Test your code action](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#test-your-code-action)

## [The JavaScript environment](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#the-javascript-environment)

The environment running JavaScript is vanilla Node v10.x.x. Your script is sandboxed and can only run for a limited amount of time and within a limited amount of memory—the [exact limits](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#limitations-with-code-steps) depend on the plan you are using.

Dates and times in Code actions use the UTC timezone, even if a different one is set for the account or the Zap.

## [Output data from Code steps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#output-data-from-code-steps)

Code steps return a single `output` variable, which is an object or array of objects that will be the result of this step. You can explicitly return early.

If the output is an array of objects, subsequent steps will run multiple times, once for each object in the array.

```
[
    {
        "product_id": 123,
        "name": "world",
        "price": 5.50
    },
    {
        "product_id": 234,
        "name": "planet",
        "price": 11.00
    }
]
```

In this example, each object in the array is returned separately. Subsequent actions will run once for each object.  
![Example of first object returned](https://cdn.zappy.app/a6c994ac80143d6a5b6934b74764fb93.png)

[![Example of second object returned](https://cdn.zappy.app/6895699b1974db91266a18f7edc55f19.png)](https://cdn.zappy.app/6895699b1974db91266a18f7edc55f19.png)

To return the whole array as [line items](https://zapier.com/help/line-items) instead, you can add `line_items` as the parent key for the output.

```
{
    "first_name": "Zap",
    "last_name": "Zaplar",
    "invoice_id": 123456,
    "total_price": 55.50,
    "line_items" : [
        {
            "product_id": 123,
            "name": "world",
            "price": 5.50
        },
        {
                "product_id": 234,
                "name": "planet",
                "price": 11.00
        }
    ]
};
```

In this example, the array is returned as a set of line items. Any subsequent actions will only run once.  
![Example of line items returned](https://cdn.zappy.app/9eb2bfc2a5893c1c7f2591970e5cebe8.png)

If you use Code by Zapier as the Zap's trigger and an empty array is returned, nothing will happen. The behavior will be similar to a polling trigger that did not get any results in the HTTP response. This functionality is exclusive to triggers.

## [Utilities in Code steps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#utilities-in-code-steps)

There are a few utilities you have access to in Code steps:

Invoking `callback(err, output)` tells Zapier that your task is done executing. If you have multiple asynchronous calls, each invoking `callback(err, output)` with their desired responses, only the first one to execute will count. Subsequent invocations to `callback(err, output)` will be picked up by the next execution of your Zap, but will not affect that task's execution, other than side effects like `console.log()` calls.

## [Testing and debugging Code steps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#testing-and-debugging-code-steps)

Running your Zap via the [dashboard](https://zapier.com/app/dashboard) is the canonical way to confirm the behavior you expect. Your [Zap History](https://zapier.com/app/history) will have all relevant details around the Code step's `inputData`, `output` and logs. The test step in the editor can be used for a tighter feedback loop.

## [Limitations with Code steps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#limitations-with-code-steps)

## [Troubleshooting errors](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps#troubleshooting-errors)

Some common error messages you might encounter include:

If you're using a linter, you can safely ignore warnings about unused variables for `inputData`, `output`, `fetch` or `callback`. Those are provided for your convenience, but you don't need to use them. If you see something else listed, you may need to debug your code.