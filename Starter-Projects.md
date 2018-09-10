Describes various wizards for creating Spring Boot Starter Projects and modifying a project's 'starter' dependencies.

# New Spring Starter Wizard

This Wizard uses the [start.spring.io](https://start.spring.io) webservice to generate a Spring Boot Starter project. The project is imported into your workspace.

This wizard is accessible via menu **File >> New >> Spring Starter Project**.

On the first page you can set various basic project options:

[[/images/screenshot-new-spring-starter-page-1.png|New Starter Wizard Page 1]]

The second page is the more interesting one, where you search for and choose
various 'Starter' dependencies:

[[/images/screenshot-new-spring-starter-page-2.png|New Starter Wizard Page 2]]

## Known Limitations

Although the wizard has a 'Language' pull-down allowing to choose Java, Kotlin or Groovy, only the Java language is supported by STS out of the box. Projects for Kotlin and Groovy *can* be generated but tooling to work with these languages is not included with STS. You can attempt to install additional Eclipse plugins to work with Kotlin or Groovy. However, the wizard has no specific support for them and does not attempt to configure the imported projects to work with these additional plugins.

# Edit Starters Wizard

If you created a project with the [New Spring Starter Wizard](#new-spring-starter-wizard) and you change
your mind later about which Starter dependencies you wanted. You can use this wizard to remove or add aditional starter dependencies.

The wizard is accessed from the `pom.xml` context menu (i.e. right-click on the `pom.xml` file in the package or project explorer).

[[/images/screenshot-edit-starters.png|Edit Starters Wizard]]

# Import Getting Started Content Wizard

This wizard imports sample projects from a number of [Tutorials](https://spring.io/guides) available at the [spring.io](https://spring.io/) website. The wizard imports the sample code ready for use in your workspace and opens the web-page of the selected tutorial in a web browsers.

This wizard is accessible from menu **File >> New >> Import Spring Getting Started Content**.

There's a detailed tutorial on how to use this wizard available [here](https://spring.io/guides/gs/sts/).

