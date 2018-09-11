Describes various wizards for creating Spring Boot Starter Projects and modifying a project's 'starter' dependencies.

# New Spring Starter Wizard

This Wizard uses the [start.spring.io](https://start.spring.io) webservice to generate a Spring Boot Starter project. The project is imported into your workspace.

This wizard is accessible via menu **File >> New >> Spring Starter Project**.

On the first page you can set various basic project options:

[[/images/screenshot-new-spring-starter-page-1.png|New Starter Wizard Page 1]]

Note that by default, the wizard uses the public [https://start.spring.io](https://start.spring.io)
url which points to a public web-service provided by Pivotal. However, it is also possible to use 
a customised webservice you develop and run in-house. Simply change the url at the top of the page.
The wizard will remember the url and use that service from now on (until you change it again).
This could be useful, for example, if you fork the service [source  code on github](https://github.com/spring-io/initializr) to include your own, in-house developed spring-boot starters).

The second page is the more interesting one, where you search for and choose
various 'Starter' dependencies:

[[/images/screenshot-new-spring-starter-page-2.png|New Starter Wizard Page 2]]

The frequently used section at the top of the page shows up to a dozen or so 
dependencies that you have used most frequently in the past, for easy access.

Hovering over a starter dependencies provides additional information, such as, links
to related documentation and tutorials:

[[/images/screenshot-new-spring-starter-hover.png|Starter Dependency Hover]]

## Known Limitations

Although the wizard has a 'Language' pull-down allowing to choose Java, Kotlin or Groovy, only the Java language is supported by STS out of the box. Projects for Kotlin and Groovy *can* be generated but tooling to work with these languages is not included with STS. You can attempt to install additional Eclipse plugins to work with Kotlin or Groovy. However, the wizard has no specific support for them and does not attempt to configure the imported projects to work with these additional plugins.

# Edit Starters Wizard

If you created a project with the [New Spring Starter Wizard](#new-spring-starter-wizard) and you change
your mind later about which Starter dependencies you wanted. You can use this wizard to remove or add aditional starter dependencies.

The wizard is accessed from the `pom.xml` context menu (i.e. right-click on the `pom.xml` file in the package or project explorer) under **Spring >> Edit Starters**.

[[/images/screenshot-edit-starters.png|Edit Starters Wizard]]

# Import Getting Started Content Wizard

This wizard imports sample projects from a number of [Tutorials](https://spring.io/guides) available at the [spring.io](https://spring.io/) website. The wizard imports the sample code ready for use in your workspace and opens the web-page of the selected tutorial in a web browsers.

This wizard is accessible from menu **File >> New >> Import Spring Getting Started Content**.

There's a detailed tutorial on how to use this wizard available [here](https://spring.io/guides/gs/sts/).

