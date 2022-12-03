-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Converger

### Note

This article describes alternatives and workarounds to the Converger module, often requested by our customers.

Please note that there is no Converger module available in Make. At the moment, it is just a concept that provides a counterpart to the Router module, allowing you to reduce duplication of modules in different routes.

## Solution

To implement the Converger concept, use one of the following workarounds to avoid the duplication of the common sequence.

### Data store

1.  Add an extra filter-free route to the **Router** to connect the common sequence (the one you would put after a **Converger** module).
    
2.  Add **[Data store](https://www.make.com/en/help/tools/data-store.html "Data store") > Add/replace a record** modules at the end of each **Router's** route (except the new extra route) to store the data outputted by the modules on the route that should be passed to the common sequence. The Data store would contain just one record, the record's key can be e.g. "MyKey".
    
3.  Add **Data store > Get a record** module at the beginning of the common sequence to obtain the previously stored data.
    

### JSON

If you wish to avoid the use of the Data store you can:

1.  Instead of the **[Data store](https://www.make.com/en/help/tools/data-store.html "Data store") > Get a record** module use **[JSON](https://www.make.com/en/help/tools/json.html "JSON") > Create JSON** module followed by **[Tools](https://www.make.com/en/help/tools/tools.html "Tools") > Set variable** to store the resulting JSON in a variable (e.g. "MyBundle").
    
2.  Instead of the **Data store > Get a record** module use **Tools > Get variable** to obtain the previously stored variable followed by **JSON > Parse JSON**.
    

Please note that if no route is executed, the **JSON > Parse JSON** will throw the following error:

To avoid this, you may employ the `ifemtpy()` function as show below:

### Set a variable

If it is just a single value that you need to pass to the common sequence (e.g. ID), you can employ only the **Tools > Set variable** and **Get variable** modules.

Make also allows you to use the **Set multiple variables** module.

### A separate new scenario

You may also place the common sequence to a separate new scenario and then:

1.  Employ **[HTTP](https://www.make.com/en/help/tools/http.html "HTTP") > Make a request** module at the end of each route to pass the data to the new scenario.
    
2.  Employ **[[[Webhooks]]](https://www.make.com/en/help/to[[Webhooks|ols/[[Webhooks|webh]]oo]]ks.html "Webhooks") > Custom webhook** module at the beginning of the new scenario to receive the data.