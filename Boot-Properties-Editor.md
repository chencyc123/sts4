This describes the Eclipse-based editor support for editing Spring Boot properties files in either `.properties` 
or `.yml` format.

Note that similar support is also provided for vscode and atom. For documentation on vscode/atom support 
please refer to [vscode marketplace entry](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-spring-boot) or [atom package repository entry](https://atom.io/packages/spring-boot) instead.

# Usage:

The Boot properties/yml editor will automatically be used when you edit files with name `application.yml` or `application.properties`. Due to limitations in Eclipse's content-type framework, files with other names like `application-production.properties` will not be automatically opened with the Spring Boot Properties Editor.

There is a somewhat clunky workaround for this limitation:

- Open Eclipse Preferences and Search for **Content Types**.
- Select the **Spring Properties File** or **Spring Yaml Properties File** content type.
- In the **File Associations** section click the **Add** button.
- Enter the name of your file **without path** exactly (glob patterns or paths are not supported). For example `application-custom-profile.properties`.
- Click **Apply and Close** button.

[[/images/editor-customize-content-type.png|Customize Editor Content Types]]

From now on files with the name `application-custom-profile.properties` will be opened with
the Spring Boot Editor.

# Functionality

STS analyzes your project's classpath and parses and indexes any [Spring Boot
Properties Metadata](https://docs.spring.io/spring-boot/docs/current/reference/html/configuration-metadata.html) it finds. Both Maven and Gradle projects are supported.

The data in the index is used to provide validation, code completions and information
hovers while editing Spring Boot Properties in either `.properties` or `.yml` format.

## Validation

[[/images/editor-boot-yml-validation.png|yaml-validation]]
[[/images/editor-boot-properties-validation.png|properties-validation]]

## Code Completions

[[/images/editor-boot-yml-completion.png|yaml-completion]]

## Information Hovers

[[/images/editor-boot-yml-hover.png|yaml-hovers]]
