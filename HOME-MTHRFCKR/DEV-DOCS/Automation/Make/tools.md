-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   Tools

## Getting started with Tools

Our Tools section includes several useful modules that can enhance your scenario.

## Triggers

### Basic trigger

Allows you to create a custom trigger and define its input bundles.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Bundle</strong></span></p></td><td><p>Create custom bundles by adding array items.</p><p>The array consists of the <span><em>name-value</em></span> pairs.</p></td></tr></tbody></table>

You can use it, for example, for contacts or any other list that is scheduled to be sent to a specified email address (_Email_ > _Send an Email,_ _Gmail_ > _Send an Email_ modules), or as a simple reminder to be triggered whenever you want.

## Increment function

Returns a value incremented by 1 after each module's operation. It is possible to configure the module to reset the value:

-   After one cycle
    
-   After one scenario run
    
-   Never
    

**Example**

One of the module's uses is to implement a so-called **Round robin** assignment of tasks/leads/emails/etc. to users in a group. The algorithm chooses the assignees from a group in some rational order, usually going from the top to the bottom of a list and then starting again at the top of the list and continuing until finished (like you would deal a deck of cards).

The following scenario sends an email to the first recipient after every **odd** scenario run, and to the second recipient after every **even** scenario run.

Configure the module to never reset the value:

There are two conditions used after the _router_ module:

1\. Odd – set the condition using the **modulus** math function that equals `1`:

Do not forget to change the _Equal to_ operator from the default _Text operator_ to the **Numeric operator**!

2\. Even – set the condition using the modulus math function that equals `0`:

## Sleep

Allows you to delay the scenario flow for up to 300 seconds (5 minutes).

<table><tbody><tr><td><p><span><strong>Delay</strong></span></p></td><td><p>Enter the number of seconds the <span>scenario</span> will be paused for.</p></td></tr></tbody></table>

This function can be useful, for example, if you want to lower the target service server load or to simulate more human behavior when sending bulk SMS or emails.

If you wish to pause the flow for longer periods of time, we suggest splitting your scenario into two scenarios:

1.  The first scenario would contain the part before the pause
    
2.  The second scenario would contain the part after it
    

The **first scenario** would end up storing all the necessary information in a [Data store](https://www.make.com/en/help/tools/data-store.html "Data store") together with the current timestamp. The **second scenario** would periodically check the Data store for records with a timestamp older than the intended delay, retrieve the records, finalize the processing of the data, and remove the records from the Data store.

## Set Variable

Creates a variable that can be mapped by other modules in the route or by the [Get Variable](https://www.make.com/en/help/tools/tools.html#get-variable "Get Variable") module for every route in the scenario.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Variable name</strong></span></p></td><td><p>Enter the variable name. This name will be displayed when mapping the variable in other modules.</p></td></tr><tr><td><p><span><strong>Variable lifetime</strong></span></p></td><td><p>One cycle</p><p>The variable is valid only for one cycle. Useful when multiple webhooks in one <span>scenario</span> run are received (more webhooks = more cycles).</p><p>One execution</p><p>The variable is valid for one execution. One execution can contain more cycles.</p></td></tr><tr><td><p><span><strong>Variable value</strong></span></p></td><td><p>Enter the value of the variable.</p></td></tr></tbody></table>

## Set Multiple Variables

Creates multiple variables that can be mapped by other modules in the route or by the [Get Multiple Variables](https://www.make.com/en/help/tools/tools.html#get-multiple-variables "Get Multiple Variables") module for every route in the scenario **within a single operation**.

The main benefits of the _Set multiple variables_ module are:

-   one _Set multiple variables_ module can replace a whole series of [Set variable](https://www.make.com/en/help/tools/tools.html#set-variable "Set Variable") modules
    
-   one _Set multiple variables_ module consumes just a single operation
    

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Variables</strong></span></p></td><td><p>Add multiple variables you want to set.</p><div><table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Variable name</strong></span></p></td><td><p>Enter the variable name. This name will be displayed when mapping the variable in other modules.</p></td></tr><tr><td><p><span><strong>Variable value</strong></span></p></td><td><p>Enter the value of the variable.</p></td></tr></tbody></table></div></td></tr><tr><td><p><span><strong>Variable lifetime</strong></span></p></td><td><p>One cycle</p><p>The variable is valid only for one cycle. Useful when multiple webhooks in one <span>scenario</span> run are received (more webhooks = more cycles).</p><p>One execution</p><p>The variable is valid for one execution. One execution can contain more cycles.</p></td></tr></tbody></table>

Possible uses of the **Set/Get (multiple) variable(s)** modules:

-   To store a calculated value for later use, even in a different route. Especially in cases when the value is used in multiple modules and the formula to calculate the value is overly complex.
    
-   To debug a formula. If a formula used in a module does not seemingly provide a correct result, copy the formula and paste it into a **Set Variable** module that you insert before the relevant module. Disconnect the module(s) after the **Set Variable** module and execute the scenario. Verify the **Set Variable** module's output, adjust/simplify the formula, execute the scenario again, and continue to do so until the issue has been resolved.
    

## Get Variable

Retrieves a value that was previously created by the [Set Variable](https://www.make.com/en/help/tools/tools.html#set-variable "Set Variable") module.

Note that this module can read a variable that was set **anywhere in the scenario**. The only requirement is that the **Tools > Set Variable** is executed before (in time) the **Tools > Get Variable** module. See the documentation for the [Router](https://www.make.com/en/help/modules/router.html "Router") module for information about the order in which routes are processed.

## Get Multiple Variables

Retrieves values that were previously created by the [Set Multiple Variables](https://www.make.com/en/help/tools/tools.html#set-multiple-variables "Set Multiple Variables") module **within a single operation**.

The main benefits of the _Set multiple variables_ module are:

-   one _Get multiple variables_ module can replace a whole series of [Get variable](https://www.make.com/en/help/tools/tools.html#get-variable "Get Variable") modules
    
-   one _Get multiple variables_ module consumes just a single operation
    

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Variables</strong></span></p></td><td><p>Add multiple variables you want to get.</p><div><table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Variable name</strong></span></p></td><td><p>Map the variable name of the variable you want to get.</p></td></tr></tbody></table></div></td></tr></tbody></table>

Possible uses of the **Set/Get (multiple) variable(s)** modules:

-   To store a calculated value for later use, even in a different route. Especially in cases when the value is used in multiple modules and the formula to calculate the value is overly complex.
    
-   To debug a formula. If a formula used in a module does not seemingly provide a correct result, copy the formula and paste it into a **Set Variable** module that you insert before the relevant module. Disconnect the module(s) after the **Set Variable** module and execute the scenario. Verify the **Set Variable** module's output, adjust/simplify the formula, execute the scenario again, and continue to do so until the issue has been resolved.
    

## Aggregators

### Table Aggregator

Merges values from the selected fields of received bundles into a single bundle using a specified column and row separator (which allows you to create a table).

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Source module</strong></span></p></td><td><p>Select the module you want to aggregate fields from.</p></td></tr><tr><td><p><span><strong>Aggregated fields</strong></span></p></td><td><p>Select the fields from the module selected above whose values you want to aggregate into one bundle.</p></td></tr><tr><td><p><span><strong>Column separator</strong></span></p></td><td><p>Select or enter the type of separator that will separate the field value columns in the resulting bundle.</p></td></tr><tr><td><p><span><strong>Row separator</strong></span></p></td><td><p>Select or enter the type of separator that will separate the field value rows in the resulting bundle.</p></td></tr><tr><td><p><span><strong>Group by</strong></span></p></td><td><p>Define an expression containing one or more mapped items. The aggregated data will then be separated into Groups with the same expression's value. Each Group outputs a separate bundle containing a Key with the evaluated expression and the aggregated text. By doing this, you can use the Key as a filter in subsequent modules.</p></td></tr></tbody></table>

### Text Aggregator

Merges values from the selected fields of received bundles into a single bundle.

**Example**

You can use the text aggregator tool to insert more values (e.g. customer names or notes) into a single bundle and send an email containing all the values in the email body or the email subject.

### Numeric Aggregator

This module allows you to retrieve numerical values, then apply one of the selected functions (SUM, AVG, COUNT, MAX,...), and return the result in one bundle.

**Example**

The module sums up values under the _number_ parameter.

## Transformers

### Compose a String

Converts any value to a string data type (text). It makes the mapping easier when mapping e.g. binary data.

### Convert the Encoding of the Text

Converts entered input text (or binary data) to the selected encoding.

<table><tbody><tr><td><p><span><strong>Input data</strong></span></p></td><td><p>Enter the content you want to convert.</p></td></tr><tr><td><p><span><strong>Input data codepage</strong></span></p></td><td><p>Enter the input data encoding type. This is important for the binary form of data.</p></td></tr><tr><td><p><span><strong>Output data codepage</strong></span></p></td><td><p>Select the target encoding of your data.</p></td></tr></tbody></table>

### Switch

Checks the input value for a match with the provided list of values. Returns output based on the result.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Input</strong></span></p></td><td><p>Enter the expression you want to evaluate.</p></td></tr><tr><td><p><span><strong>Cases</strong></span></p></td><td><p>If the <span><em>input </em></span>contains a value entered to the <span><strong><span><em>Pattern</em></span></strong></span> field, then the value entered to the <span><strong><span><em>Output</em></span></strong></span> field is returned. If the condition is not met, then no output is returned OR the value from the <span><em>Else</em></span> field (below) is returned.</p></td></tr><tr><td><p><span><strong>Else</strong></span></p></td><td><p>Enter the value that is returned when the criteria set in the <span><em>Cases</em></span> field are not met.</p></td></tr></tbody></table>

### Execute a Scenario

Status: `PLANNED` - see the Workaround section below.

### Workaround

Employ the [HTTP > Make a request](https://www.make.com/en/help/tools/http.html#make-a-request "Make a request") module in the main scenario to call the other scenario. Employ the [Webhooks > Custom webhook](https://www.make.com/en/help/tools/webhooks.html#creating-custom-webhooks "Creating custom webhooks") module in the other scenario to receive the call. Employ the [Webhooks > Webhook response](https://www.make.com/en/help/tools/webhooks.html "Webhooks") module in the other scenario to return the response.

### Stop / Throw (an error)

In some cases, you may want to forcibly stop the scenario execution after the [rollback](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html "Scenario execution, cycles, and phases") or [commit](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html "Scenario execution, cycles, and phases") phase or to stop the processing of a route and optionally store it in the queue of [incomplete executions](https://www.make.com/en/help/scenarios/incomplete-executions.html "Incomplete executions").

Status: `PLANNED` - see the **[Throw](https://www.make.com/en/help/errors/throw.html "Throw")** module.