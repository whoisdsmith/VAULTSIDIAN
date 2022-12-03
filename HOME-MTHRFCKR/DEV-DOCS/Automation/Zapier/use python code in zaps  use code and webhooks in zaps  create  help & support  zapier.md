Code steps allow Zaps to run small snippets of Python or JavaScript. This tutorial is for Python code steps, but you can also learn how to [use JavaScript code in your Zaps](https://zapier.com/help/create/code-webhooks/use-javascript-code-in-zaps).

Code steps can be used as both triggers and actions.

Python is an advanced programming language. If you're not familiar with Python, it's recommended to ask a developer for help. Zapier does not offer email support for code steps. If you encounter a problem, we recommend asking questions on [StackOverflow and tagging them with "Zapier"](https://stackoverflow.com/questions/tagged/zapier).

For tips and inspiration, check out [Python code examples](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps).

## [1\. Add a code trigger](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#add-a-code-trigger)

___

## [2\. Set up your code step](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#set-up-your-code-step)

___

## [3\. Test your code trigger](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#test-your-code-trigger)

If your code is valid, the step will show it was successful and display the data. Once the trigger is set up, you can continue to add your action step.

___

## [4\. Add a code action](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#add-a-code-action)

The Code action step allows you to write code that will interact with data coming from the trigger, or a previous action step.

___

## [5\. Set up your code action](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#set-up-your-code-action)

___

## [6\. Test your code action](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#test-your-code-action)

## [The Python environment](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#the-python-environment)

The environment is vanilla Python 3.7.2 (2.7.10 for Zaps created before January 24, 2019). Your script is sandboxed and can only run for a limited amount of time and within a limited amount of memory—the [exact limits](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#limitations-with-code-steps) depend on your Zapier plan.

Dates and times in Code actions use the UTC timezone, even if a different one is set for the account or the Zap.

## [Input data for Code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#input-data-for-code-steps)

In your code step, you have access to the `input_data` dictionary variable where all values will be strings. Since the amount of data that might feed into your script might be large or highly dynamic, you'll need to define an `input_data` mapping via Zapier’s GUI by providing a key and value.

[![The fields `item`, `name` and `currency` defined on the `input_data` dictionary, based on trigger data.](https://cdn.zappy.app/41f26b2e24f655aee43e7b7ad3952a40.png)](https://cdn.zappy.app/41f26b2e24f655aee43e7b7ad3952a40.png)

It's not possible to map `input_data` in Code by Zapier triggers.

## [Output data from code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#output-data-from-code-steps)

Code steps return a single `output` variable, which is a dictionary or list of dictionaries that will be the result of this step.

If you use Code by Zapier as the Zap's trigger and an empty array is returned, nothing will happen. The behavior will be similar to a polling trigger that did not get any results in the HTTP response. This functionality is exclusive to triggers.

## [Utilities in Code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#utilities-in-code-steps)

There are a few utilities available in Code steps:

## [Testing and debugging Code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#testing-and-debugging-code-steps)

Running your Zap via the [dashboard](https://zapier.com/app/dashboard) is the canonical way to confirm the behavior you expect. Your [Zap History](https://zapier.com/app/history) will have all relevant details around the Code step's `input_data`, `output` and logs. The test step in the editor can be used for a tighter feedback loop.

## [Limitations with Code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#limitations-with-code-steps)

## [How floats and integers are handled](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps#how-floats-and-integers-are-handled)

The Zapier web UI does not distinguish between integers and float values—they are all presented as numbers. For example, if your Python code step returns a value like this:

```
return {'result': 1.0}
```

This may appear as `1`, rather than `1.0`, in your Zap history and test results. This is an artifact of the Zapier UI. You can use `int(aNumber)` or `float(aNumber)` in your Python code step to convert the value to the data type you require.