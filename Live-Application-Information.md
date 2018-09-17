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

## Live Requestmappings

TODO fill this in
- the request mapping hovers + request mapping code lenses

## Live Bean Information

TODO fill this in:

- the bean wiring information that is shown and how that is being shown
- the bean wiring information that is shown as code lenses (with the limitation that this doesn't work in Eclipse and Atom yet)

## Conditional Beans Information

TODO fill this in
* `@ContidionalOn...`: shows information about the conditions and their evaluation at runtime

## Live Active Profiles Information

TODO fill this in 

# Scraping Remote Applications for Live Information 

TODO describe how to enable live hover for non-local app. 
- automatic support via boot dash app deployed to CF
- manual configuration and manual JMX tunneling.

# TODO: this page still needs to be filled with real content...

## Completely Disabling this Feature

Live information is periodically being scraped from running processes automatically. This could affect 
your machine's performance. If you don't want this for whatever reason this feature can be completely 
disabled: 

* Eclipse/Spring Tool Suite 4: via the preferences `Spring -> Spring Boot Language Server`
* Code: regular JSON preference mechanism using the key: `boot-java.boot-hints.on`.
* Atom: regular preference mechanism