# TODO: this page still needs to be filled with real content...

Here are some notes about what should really go in this page:

In this section we need to talk about:
- the hovers in general
- the bean wiring information that is shown and how that is being shown
- the bean wiring information that is shown as code lenses (with the limitation that this doesn't work in Eclipse and Atom yet)
- the request mapping hovers + request mapping code lenses

Then a specific section for remote apps with:
- how to configure remote apps for live information (boot dashboard, manual tunnel setup, manual ls configuration for remote apps)

Need to mention what happens in the background (polling the apps), so users can disable this when it consumes too much resources on their machines)

# Old content, to be reworked and/or deleted:

## Live application information hovers
Show information from running Spring Boot apps on your machine in the source code. This allows you to run the Spring Boot app locally on your machine and visualizes information from those running apps in your source code.

### Visualization
Once the tooling detects a running Spring Boot app on your local machine, it automatically shows hints in the source code where data from the running app can be inspected. Then hovering over that area (with the mouse pointer), the data from the running app shows up.

If there are multiple instances of the app running on your machine, the live data from all those instances will show up in the hover information.

[[/images/screenshot-live-hovers.png|live data from running apps as hover on source code]]

### Examples
* `@Profile`: shows information about the active profiles on the running apps
* `@Component`, `@Bean`, `@Autowired`: shows detailed information about the beans and their wiring from the live app
* `@ContidionalOn...`: shows information about the conditions and their evaluation at runtime
