-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   Glossary

### Glossary

[Action module](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc352831149)

You can create, read, update, or delete data with an action module. Action modules are the most common type of module and can be at the beginning, middle, or end of a scenario. There is no limit to the number of action modules in your scenario.

[Active and inactive scenarios](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc366bb29b7)

There are two ways you can use scenarios in Make depending on how you want your scenario to function:

-   Active scenarios run according to a defined schedule or webhook.
    
    -   For example: to watch a spreadsheet or webhook.
        
    
-   Inactive scenarios execute manually whenever you wish to run them.
    
    -   For example: limited, one-time results such as retrieving data for a specific time.
        
    

You can change between active and inactive whenever you like on the Scenarios tab.

[Aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc367385375)

An aggregator is a type of module that allows you to merge multiple bundles into one single bundle. Aggregators are useful in making data readable for certain modules or generating meaningful output. Make offers:

-   [Array aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620234e1adc0f "Array aggregator")
    
-   [Numerical aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024cf5c7c35 "Numerical aggregator")
    
-   [Table aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202561e8e63a "Table Aggregator")
    
-   [Text aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62025882695d1 "Text aggregator")
    

See Also [Aggregator article](https://www.make.com/en/help/modules/aggregator.html "Aggregator").

[Array](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc3674d3811)

Within a bundle, data items of the same type are sometimes in an array. You can find an array by looking at the details of a bundle.

Depending on the details of your scenario, you can map other modules to a specific item in an array or use iterators and aggregators to manipulate your data into other formats.

When mapping, Make marks arrays with \[ \].

[Array aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620234e1adc0f)

When designing a scenario, use an array aggregator to merge multiple bundles into one single bundle. This may be necessary to format data properly for subsequent modules. The array aggregator also lets you define your target data structure.

See Also [Aggregator article](https://www.make.com/en/help/modules/aggregator.html "Aggregator").

[Auto commit](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620235ce7b544)

The Auto commit option defines how Make process data transactions. Enabling Auto commit switches all operations to the [commit phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202414d111d1 "Commit phase"). In the case of an error, data commits immediately and you cannot restore any lost data.

### Note

If you disable Auto commit, no commit occurs until operations are executed for all modules. Only modules with the "ACID" tag support transactionality.

See Also [Scenario execution, cycles, and phases article](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html "Scenario execution, cycles, and phases").

[Blueprint](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202369a20ca2)

Make lets you import and export scenarios via a blueprint, a file in JSON format. Your blueprint contains all of your modules and settings except for connections. When importing from a blueprint, you must add your connections.

### Note

Blueprints are not compatible between Integromat and Make.

[Break error handling directive](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202371c30dde)

Using a break directive lets you resolve errors manually and helps when you want more human oversight of errors. When an error occurs, the break directive stops execution of subsequent modules and stores the error in the queue of incomplete executions. Then, the break directive creates a separate record for each bundle that causes the error (available under the Incomplete executions tab > Details). Here, you can manually resolve the error and process all unprocessed bundles. The scenario execution history shows the status as Warning.

### Note

You must enable storing of incomplete executions under Scenario settings.

[Bundle](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc3d8b7a84f)

A bundle is a chunk of data and the basic unit for use with modules. A bundle consists of items, similar to how a bag may contain separate, individual items.

[Clone module](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202404e9841e)

When you need a quick duplicate of a module (for example when using data store modules on each branch of a router), use the clone module command to make an exact duplicate of your module. It appears instantly and has the same settings and variables as the original module. You can then drag it to wherever you need it and customize the settings. Changes in the original do not affect the clone and vice versa.

### Note

You cannot clone the trigger module of your scenario.

[Clone scenario](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62023e85e65f1)

You can duplicate a scenario from the Scenario tab by using the Clone option on the drop down menu for the scenario. Possible uses include sales with multiple pipelines. Use Clone scenario to create a duplicate scenario and customize for each pipeline. Changes in the original do not affect the clone and vice versa.

[Commit error handling directive](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202407c59d30)

Use the commit error handling directive when you want to stop the execution of the scenario completely but still have the sent data. When there is an error, the commit directive:

-   stops execution immediately
    
-   does not process the subsequent modules
    
-   ignores all unprocessed bundles
    

The scenario execution history displays the status as Success.

[Commit phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202414d111d1)

Commit is the third phase of a scenario execution. If the operation phase is successful for all modules, the commit phase begins and makes all data changes permanent. This means that Make sends information to all the services involved in the operation phase about its success.

See Also [Scenario execution, cycles, and phases article](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html "Scenario execution, cycles, and phases").

[Connection](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620148dd68c70)

A connection allows Make to communicate with an app/service. When adding an app/service to a Make, you may have to create a connection between Make and that app/service to retrieve or send necessary data. Make asks for only the specific permissions required. As a result, some apps/services may ask for permission multiple times. For more information, see [Connecting to services](https://www.make.com/en/help/connections/connecting-to-services.html "Connecting to services")

[Converger](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620241720fe1e)

A converger is the counterpart to the router module and merges several routes into one route. There is no converger module available in Make, but there is a workaround, allowing you to reduce the duplication of modules in different routes.

See Also [Converger workaround](https://www.make.com/en/help/modules/converger.html "Converger").

[Copy module](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620241d6985e9)

When working with multiple scenarios, use the copy module command to create a duplicate of your module that you can paste to any scenario. It functions similar to cutting and pasting text on your computer. Although cloning a module is faster, copying allows you to paste the module in another scenario. Copying a module will also copy any filters before the original module. You can also box select (shift + drag) several modules and copy them with the ctrl + C shortcut. This is helpful when creating complex scenarios.

[Cycle](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202423503c50)

A cycle is the operation and commit/rollback phases of scenario execution. A scenario may have one or more cycles (one is the default).

See Also [Cycles](https://www.make.com/en/help/scenarios/cycles.html "Cycles").

[Data loss](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620242ebe6f77)

The data loss option enables data to be lost if Make fails to save a bundle to the queue of incomplete executions (e.g. due to a lack of free space). Enable data loss to prevent interruptions in the overall scenario execution, e.g. a scenario where it is imperative the scenario keeps running and the incoming erroneous data is not that important.

See Also [Scenario settings article](https://www.make.com/en/help/scenarios/scenario-settings.html "Scenario settings").

[Data store](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024340bc8f9)

A data store is a built-in database in Make .You can use data stores to store data from scenarios or transfer data between individual scenarios or scenario runs. Your account includes data stores, so you do not have to register at a third-party service.

[Data structure](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620243b690ff4)

When you create a data store, you need to create a data structure that formats your data store in Make. Think of the data store as a spreadsheet and the data structure as the headers. The data structure defines the kind of data (i.e. text, numeric, etc.) that the data store records. You can view and manage your data structures from the data structures page. You can reuse your data structures.

[Data Transfer](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620243da05f1e)

Data transfer is the amount of data transferred through your scenario.

See Also [Pricing parameters](https://www.make.com/en/help/general/pricing-parameters.html "Pricing parameters").

[Diagram](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620149be469ad)

The diagram is a visual representation of your scenario and appears exactly the same way as you see your scenario in the Scenario editor. Use the diagram tab to quickly view:

-   the execution history of your scenario.
    
-   the amount of operations and data consumed.
    
-   the controls to manage the scenario.
    

[Directive (error handling)](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202444678d85)

A directive allows you to control how Make handles errors. There are six error handling directives:

-   [Rollback](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620250d4b41ec "Rollback phase")
    
-   [Commit](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202414d111d1 "Commit phase")
    
-   [Resume](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024f5290445 "Resume error handling")
    
-   [Ignore](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202476383844 "Ignore error handling directive")
    
-   [Break](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202371c30dde "Break error handling directive")
    
-   [Retry](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024faed94be "Retry")
    

[Explain flow](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62014ab633453)

The Explain flow button allows you to see how the data will flow through from module to module before you run your scenario. Clicking the Explain flow button ![Explain_flow_icon.png](https://www.make.com/en/help/image/1621f61c7ba5d0.png) starts an animated visualization of how your bundles flow through your scenario.

[Filter](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620244bda44c3)

A filter helps you select bundles that fit specific criteria. You can add a filter between two modules to be sure that bundles received from the preceding modules fulfill specific conditions. Make offers:

-   Basic operator filters
    
-   Text filters
    
-   Numeric filters
    
-   Date-time filters
    
-   Time filters
    
-   Boolean filters
    
-   Array filters
    

See Also [Filtering article](https://www.make.com/en/help/scenarios/filtering.html "Filtering").

[Finalization phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202452d17469)

Finalization is the fourth and final phase of scenario execution.The finalization phase closes open connections (e.g. FTP connections, database connections, etc.) and marks the scenario as completed.

[Functions](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62014b8dcf6e9)

Functions allow you to create complex formulas when [mapping](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024b83b9e8b "Mapping") items. The functions available in Make are similar to functions in Google Sheets and those in other programming languages. The functions let you perform various transformations of item values, such as converting a text to uppercase, trimming a text, converting a date into a different format, and many others. Hovering over a function gives you a brief explanation and usage example.

See Also [Functions article](https://www.make.com/en/help/functions/using-functions.html "Using functions").

[History](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62014d9c681fb)

Make maintains a history of your scenario and records:

-   Date that scenario execution started
    
-   Status (success, warning, or error)
    
-   Execution duration
    
-   Number of operations spent during the scenario run
    
-   Size of transferred data
    
-   Link to detailed information, where you can inspect all data in that particular execution received and how the data was processed
    

You can view this information by clicking on history in Scenario detail or in the Diagram. Viewing from the diagram allows you to see currently running executions and stop them if necessary.

[Ignore error handling directive](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202476383844)

Use the ignore error handling directive when you want a scenario to continue processing the next bundles if an error occurs. The ignore directive does not process the bundle where the error occurred through subsequent modules. The scenario execution status is marked as Success.

The ignore directive is the default when you use a module instead of an error handling directive.

[Incomplete executions](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620247c07408b)

Sometimes Make cannot successfully finalize a scenario execution due to an error.

Make stores incomplete executions in a folder named Incomplete Executions. Each stored incomplete execution can be resolved either manually or automatically.

[Initialization phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202481bbe4bd)

Initialization is the first phase of scenario execution. During the initialization phase, Make creates all necessary connections (for example, to databases, email services, etc.). The initialization phase also checks if each module is capable of performing its intended operation(s).

[Instant trigger](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620248dd1d16f)

See [Webhook](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62027da527ff5).

[Item](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62014fe89ec2e)

An item is data that is part of a bundle. There are several different types of items: text, number, boolean (yes/no), date, time, buffer (binary data), collections, and arrays. You can find these details by clicking on the inspector at the upper-right of your module.

[Iterator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620249297b361)

When creating a scenario, use an iterator to divide one bundle into smaller separate bundles. Subsequent modules then process the bundles separately. One common use is when automatically uploading email attachments to a cloud drive.

You can find iterators under Flow control of the tools section.

See Also [Iterator article](https://www.make.com/en/help/tools/flow-control.html#iterator-935250 "Iterator").

[Keychain](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N61dc3d81f13d5)

The keychain helps you to administer the keys you have stored in Make. Each key is a unique identifier used for encryption.

See Also [Keys](https://www.make.com/en/help/connections/keys.html "Keys").

[Key (data store)](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620249be6e255)

When creating a new data store, you can assign unique identifiers to that data store. Make will create a key for you if you leave the key field blank. You can also map the value of your key to make it easier to find information in your data store.

[Mapping](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024b83b9e8b)

Mapping links the modules in your scenario. When you map an item, you connected the data retrieved by one module to another module to perform the desired action. For example, you can map the email address and subject lines from the Email > Watch emails module to Google Sheets > Add a row and create a spreadsheet of email addresses and subjects.

See Also [Mapping](https://www.make.com/en/help/mapping/mapping.html "Mapping").

[Module](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024c2a3527c)

Modules are the main building blocks of automation in Make. Modules represent actions that Make performs with an app. Each app typically contains several modules that read, create, update, and delete data.

[Notes](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024c491434b)

Clicking the notes button ![Notes_icon.png](https://www.make.com/en/help/image/1621f61c7c9752.png) lets you add notes to your modules in your scenario. The notes feature is very useful for keeping track of webhook links. You can also use notes to explain scenario routes, which is useful for teams working on complex scenarios.

[Numerical aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024cf5c7c35)

A numerical aggregator lets you to apply functions like SUM or AVG to numerical values. Numerical aggregator then return the results in one bundle.

[Operation](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024d46ab403)

Every time a module in a scenario performs an action, it counts as an operation. For example, when your scenario reads a record from Pipedrive, writes a row into a Google sheet, or posts a tweet, each counts as one operation.

More examples that count as operations:

-   Read data from an app or webhook
    
-   Search for data in an app
    
-   Create data in an app
    
-   Update data in an app
    
-   Delete data from an app
    
-   Transform data using the built-in tools
    
-   Aggregate a row of data into an array or text
    
-   Iterate a row of data
    

Depending on the complexity of the process you’re automating, your scenario can perform anywhere from two operations to thousands of operations in a single run.

### Note

There is a limit for the number of operations according to your subscription.

Don’t worry about using up all your operations before the end of the month or year. You can always buy extra operations or upgrade to a higher tier plan.

See Also [Counting the number of operations](https://www.make.com/en/help/scenarios/counting-the-number-of-operations.html "Counting the number of operations").

[Operation phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024e53799c6)

Operation is the second phase of scenario execution. During the operation phase reading and/or writing operation is performed:

-   The reading operation obtains the data needed by the modules in your scenario.
    
-   The writing operation sends data to a given service for further processing.
    

[Repeater](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024ef2e9148)

When you need a module to perform a task multiple times, for example make an API call, use a repeater. Placing a repeater module before another module makes the subsequent module repeat its task. You can confirm by inspecting the bundles output by the subsequent module.

See Also [Repeater section](https://www.make.com/en/help/tools/flow-control.html#repeater "Repeater") in [Flow control article](https://www.make.com/en/help/tools/flow-control.html "Flow control").

[Resume error handling](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024f5290445)

Use the Resume directive when you want scenario execution to continue even though an error occurs. The Resume directive allows subsequent modules continuing processing as if no error took place. The Scenario execution history displays the status as Success.

[Retry](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62024faed94be)

Make currently does not offer the retry error handling directive, though there are two workarounds that mimic its functionality.

See Also [Retry workaround article](https://www.make.com/en/help/errors/retry.html "Retry").

[Rollback error handling](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62025032dca7b)

Use the Rollback directive when you want to mark the error and return modules to how they were before the scenario ran. The Rollback Directive stops the scenario execution immediately. Then a rollback phase starts on all modules to revert each module back to its initial state. The Rollback directive marks the scenario execution status as Error.

### Note

This is the default behavior if there is no error handler route and the _Allow Storing Incomplete Executions_ setting under Scenario settings is not checked.

See Also [Directives for error handling article](https://www.make.com/en/help/errors/directives-for-error-handling.html "Directives for error handling").

[Rollback phase](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620250d4b41ec)

Rollback is a phase that occurs when there is an error during the operation or commit phase on any module. The scenario execution stops the operation or commit phase and starts the rollback phase, reversing all changes in data.

### Note

Some modules do not support rollback and operations performed by these modules are irreversible.

See Also [ACID modules](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html#acid-modules "ACID modules").

[Router](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62025271a50ba)

A router allows you to add new routes to a scenario so you can branch your flow into several routes and process the data within each route differently.

See Also [Router article](https://www.make.com/en/help/modules/router.html "Router").

[Run Once](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620252c7bd7af)

Once a scenario is configured, you can execute it by clicking the play icon.

This way, you can verify that the scenario runs as you expect.

If everything is working properly, you can activate the scenario. Once activated, thescenario execute according to its schedule.

If everything does not run as expected, you can visit our [error handling article](https://www.make.com/en/help/errors/introduction-to-error-handling.html "Introduction to Error Handling") to learn how to handle errors.

[Scenario](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620253564883b)

A scenario is a series of modules that users create to automate apps/services. Creating a scenario allows you to transfer and transform selected data between apps/services via modules.

[Scenario execution](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620253c0cef76)

Whenever your scenario runs, it constitutes one scenario execution. Make marks the scenario execution as either success, warning, or error. You can find this information on the right hand side of the [Diagram](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620149be469ad "Diagram") or on the History tab.

In technical terms, scenario execution refers to a [sequence of phases](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62027c9dac072 "Transaction processing"). Execution starts with the initialization phase, continues with at least one cycle composed of the operation and commit/rollback phases and ends with the finalization phase.

It is possible to receive emails when errors occur by enabling email notifications from the email notification options tab of the dashboard.

[Scheduling](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620254de821d4)

Make allows you to define when and how often an active scenario runs. Use the Schedule setting panel under the Options tab and choose Scheduling to set your preferred schedule.

[Sequential processing](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620255180b218)

Using the Sequential processing options allows you to monitor and resolve errors in greater detail. If you enable sequential processing, Make stops processing the task sequence until you resolve all incomplete executions. With sequential processing enabled, you can address all incomplete executions in the order in which they occurred.

If you disable Sequential processing, the scenario continues to run according to its schedule with repeated attempts to rerun the incomplete executions.

See Also [Scenario settings article](https://www.make.com/en/help/scenarios/scenario-settings.html "Scenario settings"), [Incomplete executions article](https://www.make.com/en/help/scenarios/incomplete-executions.html "Incomplete executions").

[Table Aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N6202561e8e63a)

You can use a table aggregator to create a table from multiple bundles. The table aggregator merges values based on your specified column and row parameters and outputs into a single bundle. One possible use is compiling blog posts or emails into a single email summary.

[Teams](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620256563857e)

Use teams to control and separate access to scenarios and other Make data. You can assign users to multiple teams and specific roles on each team. Members of a team have access only to scenarios and data that belong to their team and role.

See Also [Teams article](https://www.make.com/en/help/access-management/teams.html "Teams").

[Template](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620258353394d)

A [template](https://www.make.com/en/help/scenarios/scenario-templates.html "Scenario templates") is a pre-developed scenario that you can customize to your specific needs. Make has made many templates for you to quickly create useful scenarios.

Make also allows you to [submit your own templates](https://www.make.com/en/help/scenarios/scenario-templates.html#sharing-templates "Sharing templates") for sharing with the Make community.

[Text aggregator](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62025882695d1)

When a module requires text in a single bundle, use a text aggregator to merge values into a single bundle. You can [map](https://www.make.com/en/help/mapping/mapping.html "Mapping") text aggregators the same way as modules or other tools to create the bundle you need.

[Text Parser](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620258a1acda4)

The text parser tool allows you to add these modules:

-   Match pattern - allows you to find and extract text matching a search pattern. Match pattern uses [regular expression](https://en.wikipedia.org/wiki/Regular_expression)s, a sequence of characters that specifies a search pattern. One example use is extracting email addresses from a document or the body of emails.
    
-   Replace - searches for a specified value or regular expression, and replaces the result with the new value.
    
-   Get elements from HTML - retrieves the desired elements from an HTML code.
    
-   HTML to Text -allows you to convert HTML to plain text.
    
-   Get elements from text - retrieves desired elements from text.
    

[Transaction processing](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62027c9dac072)

Make uses transactional processing to describe the scenario execution cycle. A transaction consists of four phases during which Make creates or updates data in a way that ensures data integrity across apps and services. There are 4 phases:

1.  Initialization - creates all necessary connections and checks that all modules are ready.
    
2.  Operation - performs the reading and writing of data, retrieving and sending data from one service or module to another.
    
3.  Commit/rollback
    
    1.  Commit - verifies all changes across modules and services and makes them permanent.
        
    2.  Rollback - when changes cannot be verified, the scenario ‘rolls back’ all changes, returning all data, modules, and services to their original states. The rollback phase protects data integrity in the event of an error.
        
    
4.  Finalization - closes all open connections (e.g. FTP connections, database connections, etc.) and completes the scenario.
    

See Also [Scenarion execution, cycles, and phases](https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html "Scenario execution, cycles, and phases").

[Trigger](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N620260a1d0c3b)

Every scenario has a trigger, an event that starts your scenario. A scenario must have a trigger. There can only be one trigger for each scenario. When you create a new scenario, the first module you choose is your trigger for that scenario. Create a trigger by clicking on the empty module of a newly created scenario or moving the clock/lightning icon to another module.

There are two types of triggers:

1.  Polling -  routinely monitors a connected app/service ![Trigger_-_clock_icon.png](https://www.make.com/en/help/image/1621f61c8179af.png)
    
2.  Instant - also called webhooks that immediately execute the scenario ![Trigger_-_lightning_icon.png](https://www.make.com/en/help/image/1621f61c81ca73.png)
    

[Webhook](https://www.make.com/en/help/glossary.html#UUID-093a9d1a-680a-bd1d-3485-13e79d573196_N62027da527ff5)

When integrating with third party apps/services, [webhooks](https://en.wikipedia.org/wiki/Webhook) are a way for those apps to let Make know when something happens. A webhook is a notification containing data about an event, sent by one app to another app or site.

Make uses webhooks as instant triggers to immediately execute the scenario. Webhooks create a URL that you can call from an external app or service, or from another Make scenario.