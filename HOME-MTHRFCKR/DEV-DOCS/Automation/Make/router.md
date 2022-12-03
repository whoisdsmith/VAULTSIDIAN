-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Router

The **Router** module allows you to branch your flow into several routes and process the data within each route differently. Once a **Router** receives a bundle, it forwards it to each connected route in the order the routes were attached to the **Router**.

### Tip

To verify the order of the routes, you can click the [Auto-align](https://www.make.com/en/help/scenarios/scenario-editor.html "Scenario editor") icon ![auto_align_icon.png](https://www.make.com/en/help/image/1621f615ae7966.png), which will arrange the routes according to the order from top to bottom.

To change the order, just remove the **Router** module and re-connect the routes in the desired order.

### Note

Routes are processed sequentially, not in parallel. A bundle is not sent to the next route until it has been completely processed by the previous route.

## Template

See our scenario template for the [Controlled distribution of data flow](https://www.make.com/en/templates/2952-controlled-distribution-of-data-flow).

## Adding a router to a scenario

A **Router** can be added to a scenario in one of the following ways:

1.  If you wish to connect the **Router** after a module, click on the module's right "ear" and choose **[Flow Control](https://www.make.com/en/help/tools/flow-control.html "Flow control") > Router** from the list of modules.
    
2.  If you wish to insert the **Router** between two modules, click on the wrench icon below the route connecting the two modules (or right-click the route) and choose "Add a router" from the menu.
    
3.  A **Router** can also be inserted automatically in the case when you try to connect module `A` to module `B` to which another module is already connected. Just drag the left "ear" of the module `A` and drop it on to module `B`.
    

## Filters

You can place a [filter](https://www.make.com/en/help/scenarios/filtering.html "Filtering") on a route after the **Router** to filter bundles as on any other route: just click on the route, add conditions and click on the "OK" button to save the filter setup:

## The fallback route

The filter setup on a route after a **Router** contains a special option: _The fallback route_:

When enabled, this route is used in the case when a bundle cannot continue on from the **Router** via any other route because the filters on the other routes filtered it out. The Fallback route is distinguished with a different arrow sign inside the **Router** module:

### If/Else

A typical use case of the fallback route is to continue the flow with route `A` if the condition is met and with route `B` if it is not. This can be achieved with the following steps:

1.  Insert a Router in your scenario.
    
2.  Connect both routes (`A` and `B`) to the Router.
    
3.  Click on the route `A` and specify a condition:
    
4.  Click on the route `B` and enable The fallback route option: