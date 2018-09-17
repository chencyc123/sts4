STS4 automatically detects JVM processes for running boot applications on your local machine and
scrapes them for 'live' runtime information about beans, requestmappings amongst other things.

When a running app is detected, STS 4 automatically shows hints in the source code where data from the running app can be inspected. Then hovering over that area (with the mouse pointer), the data from the running app shows up.

If there are multiple instances of the app running on your machine, the live data from all those instances will show up in the hover information.

TODO: Replace with an Eclipse-based screenshot.
[[/images/screenshot-live-hovers.png|live data from running apps as hover on source code]]

## Application Requirements

TODO: describe how to enable live hover support on local apps. 

This includes:

- what is required from the app/process: 
  - actuator dependency
  - app is running

- support can be completely disabled in the editor via preferences.

## Live Information Details

This section provides an overview of the different types of live information that are currently
supported and how each of them can be accessed from the editor.

### Live Requestmappings

TODO fill this in
- the request mapping hovers + request mapping code lenses

### Live Bean Information
Live Beans information is displayed for a running Spring Boot application. Live Beans data is fetched from the application process. The data is mapped right onto the source code. Namely at the source code pieces where beans are injected or defined. Typically such places in the source code are Spring annotations but there are other places such as Component constructors, Spring Data repositories etc. These spots in the source code are highlighted with light green background. Live Beans information is also available for apps running on the Cloud Foundry if SSH Tunnel is enabled when the app is deployed to Cloud Foundry via Boot Dashboard.

#### Hovers
Live Beans hover is displayed when hovering over green highlights in the source code where beans are injected or defined.
Typical Live Bean hover displays the following:
- List of beans current bean is injected into. Short summary list of beans in a single line followed by the detailed beans list
- List of beans wired into the current bean. Short summary list of beans in a single line followed by the detailed beans list 
- Process information from which Live Beans data has been fetched from

Detailed list of beans provides for each bean the following:
- Bean ID
- Bean Java type (hyper-link)
- Resource defining the bean (hyper-link)

[[/images/live-bean-hover-eclipse.png|Live Bean information hover in Eclipse]]

A hover can display Live Beans information for more than one running app as you can see below:
[[/images/live-bean-apps-hover-eclipse.png|Live Bean information hover for multiple running apps in Eclipse]]

#### Code Lenses
Code Lens is displayed on a dedicated line right above the green highlight in the source code. The Live Bean information displayed by the Code Lens is a short one line summary list of wired in beans and injected into beans for the current bean. 
[[/images/live-bean-codelens-eclipse.png|Live Bean Code Lens in Eclipse]]

### Conditional Beans Information

TODO fill this in
* `@ContidionalOn...`: shows information about the conditions and their evaluation at runtime

### Live Active Profiles Information

TODO fill this in 

## Remote Applications

TODO describe how to enable live hover for non-local app. 
- automatic support via boot dash app deployed to CF
- manual configuration and manual JMX tunneling.

## Completely Disabling this Feature

A background thread is used to periodically scrape running processes for live information. This could negatively affect your machine's performance. This feature can be completely disabled: 

* Eclipse/Spring Tool Suite 4: via the preferences `Spring -> Spring Boot Language Server`
* Code: regular JSON preference mechanism using the key: `boot-java.boot-hints.on`.
* Atom: regular preference mechanism