This page provides some examples for using [Python code steps](https://zapier.com/help/create/code-webhooks/use-python-code-in-zaps). Every example depends on specific `input_data`, which is provided under the "Input Data" field when setting up your code step. [This example screenshot](https://cdn.zapier.com/storage/photos/d91e2085894d7fb402cdc802aba530fd.png) shows three demonstration inputs you can use in your code like this: `input_data['body']`, `input_data['name']`, and `input_data['subject']`. Be sure you read the code examples and provide the right inputs otherwise nothing will work as expected!

Python is an advanced programming language. If you're not familiar with using Python, it's recommended to ask a developer for help.

## [Introductory Examples](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-1)

Each of the four examples below expects a `name` in the "Input Data" field.

A easy example might be something as trivial as:

```
return {'id': 1234, 'hello': 'world!', 'name': input_data['name']}
```

You can also bind the result to `output`—the code above has **exactly the same** behavior as the code below:

```
output = {'id': 1234, 'hello': 'world!', 'name': input_data['name']}
```

An example with an early empty return might be something as trivial as:

```
if input_data['name'] == 'Larry':
    return [] # we don't work for Larry!

return {'id': 1234, 'hello': 'world!', 'name': input_data['name']}
```

___

## [Introductory HTTP Example](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-2)

A more complex example (no "Input Data" needed):

```
response = requests.get('http://example.com/')
response.raise_for_status() # optional but good practice in case the call fails!
return {'id': 1234, 'rawHTML': response.text}
```

___

## [Introductory Logging Example](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-3)

This example expects a `name` in the "Input Data" field:

```
if input_data.get('name'):
    print('got name!', input_data['name'])

return {'id': 1234, 'hello': 'world!', 'name': input_data['name']}
```

Test your action and look at the data to see the `print` result.

___

## [Simple Math - Divide by Two](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-4)

This example expects a `rawNumber` in the "Input Data" field:

```
return {
  'calculatedNumber': int(input_data['rawNumber']) / 2
}
```

___

## [Simple Email Extraction](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-5)

This example expects a `rawText` in the "Input Data" field:

```
import re
emails = re.findall(r'[\w._-]+@[\w._-]+\.[\w._-]+', input_data['rawText'])
return {
    'firstEmail': emails[0] if emails else None
}
```

___

## [Complex Multiple Email Extraction](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-6)

This example expects a `rawText` in the "Input Data" field:

```
import re
emails = re.findall(r'[\w._-]+@[\w._-]+\.[\w._-]+', input_data['rawText'])
return [
    {'email': email} for email in emails
]
```

This will trigger multiple downstream actions—one for each email found! If no emails are found, nothing happens.

___

## [Formatting a Comma Separated List](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-7)

There may be cases where you need to create a comma separated list but you need to eliminate the blank values from the list. This snippet will help you create the list and remove blanks. This example expects a `values` entry in the "Input Data" field like this:

[![](https://cdn.zapier.com/storage/photos/af2f7e1fac9846013a707d4b909fe4ba.png)](https://cdn.zapier.com/storage/photos/af2f7e1fac9846013a707d4b909fe4ba.png)

```
import re
values = re.sub('(^,+|,+$)', '', input_data['values'])
values = re.sub(',+', ',', values)
return [{'values': values}]
```

___

## [Weather JSON API Call](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-8)

This example expects a `zipCode` in the "Input Data" field:

```
zc = input_data['zipCode']
url = 'http://api.openweathermap.org/data/2.5/weather?zip=' + zc + ',us'
response = requests.get(url)
response.raise_for_status() # optional but good practice in case the call fails!
return response.json()
```

\`\`\`

___

## [XML Parsing](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-9)

If you need to parse XML and return it, you can do that with the built in XML libraries:

```
from xml.etree import ElementTree
root = ElementTree.fromstring('''
<parent>
    <child><id>1</id></child>
    <child><id>2</id></child>
    <child><id>3</id></child>
</parent>
''')
return [
    {field.tag: field.text for field in child}
    for child in root.findall('child')
]
```

If you need to do an API call to parse XML, you can combine this portion with the `request` examples above:

```
from xml.etree import ElementTree
response = requests.get('http://yourapi.com/xml')
root = ElementTree.fromstring(response.text)
return [
    {field.tag: field.text for field in child}
    for child in root.findall('child')
]
```

Please note, the part for iterating the data (`for child in root.findall('child')`) will change depending on whatever the API response looks like, it will not be exactly 'parent' or 'child' like our example above! Experiment with it!

___

## [Store State](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-10)

It isn't uncommon to want to stash some data away for the next run, our `StoreClient` can do exactly that. For example, this is a counter that counts how many times it is ran:

```
    store = StoreClient('some secret')

    count = store.get('some counter') or 0
    count += 1
    store.set('some counter', count)
    return {'the count': count}
```

[Learn more about the StoreClient](https://zapier.com/help/create/code-webhooks/store-data-from-code-steps-with-storeclient).

___

## [Generate Unique ID (UUID)](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-11)

When you use a Code trigger to connect to an app that uses polling to retrieve new data, your Zap will only trigger if the ID is unique. This is to prevent duplicates.

In the "'hello': 'world!'" example above, the Zap will trigger the first time it receives "'id': 1234". If a later poll retrieves "'id': 1234" again, it will not trigger for that data.

One way to make the ID unique each time the Zap runs is to use the `uuid` library:

```
    import uuid

    return {
        'unique_id': str(uuid.uuid4())
    }
```

___

## [Only Once Per Hour](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-12)

In conjunction with a [Filter step](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters), you can use code like this to limit the number of times your zap can run per hour (which is configurable):

```
every_seconds = 60 * 60

store = StoreClient('some secret')

import time
now = int(time.time())
last_post = store.get('last_post') or now - every_seconds + 1

output = {'run': 'no'}
if last_post < (now - every_seconds):
    output = {'run': 'yes'}
    store.set('last_post', now)
```

\# don't forget to set up a filter after this that checks if run is exactly yes

Without a follow up Filter step this won't work!

___

## [Bulk Lookup Table](https://zapier.com/help/create/code-webhooks/python-code-examples-in-zaps#step-13)

If you have hundreds of values for lookup, you might not want to use the built-in [lookup table](https://zapier.com/help/create/format/create-lookup-tables-in-zaps) tool! This makes it a lot easier, but you'll want to set up the input values like so:

[![](https://zappy-dev.zapier.com/AF18FAEE-4D2F-4623-9609-5D50382FB036.png)](https://zappy-dev.zapier.com/AF18FAEE-4D2F-4623-9609-5D50382FB036.png)

```
    default = 'some default'
    _lookup_table = '''
    lookup_in1,lookup_out1
    lookup_in2,lookup_out2
    '''.strip().splitlines()
    lookup_table = dict(
        line.split(',', 1)
        for line in _lookup_table.items()
        if ',' in line
    )
    return {
        'out_value': lookup_table.get(input_data['in_value'], default)
    }
```

Now you can use the "Out Value" in later steps!